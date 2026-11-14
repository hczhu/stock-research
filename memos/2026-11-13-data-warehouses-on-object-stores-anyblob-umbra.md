tags:: [[$AMZN]], [[$SNOW]], [[$MSFT]], [[$GOOGL]], [[cloud]], [[database]], [[storage]], [[data-center]], [[ai-model:GPT-6 Astra]], [[ai-effort:medium]]
file-created-at:: 2026-11-13
file-updated-at:: 2026-11-13

- ## Object storage becomes the warehouse’s working data source
	- **Source**: Dominik Durner, Viktor Leis and Thomas Neumann, *Exploiting Cloud Object Storage for High-Performance Analytics*, PVLDB 16(11), 2769–2782, 2023. [Paper](https://www.vldb.org/pvldb/vol16/p2769-durner.pdf) · [AnyBlob implementation](https://github.com/durner/AnyBlob). The user-supplied screenshot reproduces Table 1. Prices and benchmark results below are historical observations from this paper, not November 2026 quotes; its longitudinal measurements include July–August 2022.
	- **Thesis**: High-bandwidth networks, parallel object retrieval and efficient query scheduling make inexpensive object storage practical for active analytical workloads. This expands the scope for elastic warehouses whose compute can start, resize or shut down without first populating a large local data cache. The commercial opportunity is to deliver reliable query performance and lower total operating cost on top of a shared storage foundation.
	- The paper identifies Snowflake, Databricks and AWS Redshift as already using object storage as their durable source of truth. Its advance is a blueprint for reducing dependence on local SSD caches: **AnyBlob** efficiently downloads objects, while **Umbra**, a SQL query engine, overlaps retrieval with computation. This was demonstrated by 2023; it should not be presented as a newly invented 2026 architecture.
	- Three layers remain distinct: **object storage** holds durable bytes; **table formats/catalogs** organize files, schemas and consistent table versions; **query engines** optimize and execute SQL. Storing files in S3 alone does not supply warehouse semantics.

- ## Why this architecture became technically and economically feasible
	- | Enabler | Evidence and mechanism | Consequence for warehouse design |
	  | --- | --- | --- |
	  | Faster networks approach local storage bandwidth | AWS introduced 100 Gbit/s instances in 2018, a fourfold bandwidth increase in the paper’s comparison. The paper contrasts about 12 GB/s network bandwidth with 16 GB/s local reads on an i3en.24xlarge. | Remote scans can feed CPUs at useful rates; repeatedly copying the full dataset to local storage becomes less necessary. |
	  | Networking becomes affordable | Comparing c5n.18xlarge with c5.18xlarge, the authors estimate a roughly 22% networking-related price increase after accounting for about 30% more DRAM. | High bandwidth need not erase object storage’s capacity-cost advantage. This is a historical instance comparison. |
	  | Many independent reads can overlap | An analytical scan can issue hundreds of requests across distributed storage servers. | Slow individual requests can still produce high aggregate throughput; this works best when sufficient independent scan work exists. |
	  | Efficient asynchronous operating-system interfaces | Linux io_uring, available since kernel 5.1, lets a small number of threads manage many concurrent operations. | High request concurrency no longer requires an equally large number of blocked threads. |
	  | Columnar layout and compression | Read only required columns, prune blocks with min/max metadata, and compress transmitted data. | Lower bytes scanned and fewer requests improve both performance and cost. |
	  | Stronger storage consistency and table metadata protocols | S3 introduced strong GET/PUT/LIST consistency in December 2020; snapshot-based table formats add atomic table-version changes. | Readers can discover completed writes reliably and use consistent datasets, while compute remains independently replaceable. |
	- The network and S3 milestones are confirmed by AWS’s [C5n launch announcement](https://aws.amazon.com/blogs/aws/new-c5n-instances-with-100-gbps-networking/) and [strong-consistency announcement](https://aws.amazon.com/blogs/aws/amazon-s3-update-strong-read-after-write-consistency/).
	- **Broader trend beyond this implementation**: Iceberg tracks data files through snapshots and commits changes by atomically replacing the current metadata reference. Concurrent writers use optimistic concurrency and retry conflicting commits. This enables multiple engines to operate on shared tables without treating a directory listing as a transaction protocol. S3’s per-object consistency does not itself provide multi-object transactions. [Apache Iceberg reliability documentation](https://iceberg.apache.org/docs/latest/reliability/)
	- Cloud storage supplies durable capacity independently of compute allocation. In the paper, S3’s stated durability is 11 nines per year. This is a durability metric, not a query-availability or latency guarantee.

- ## Screenshot extraction: multi-AZ object-storage pricing
	- **Table 1, PDF page 2 / printed page 2770**: default zone-redundant replication across multiple availability zones within one region. Region names are transcribed as printed, including GCP’s `us-east-1` label. All amounts are USD; 1 TiB = 1,024 GiB. These are the paper’s historical prices.
	- | Cloud provider and region shown | Storage, USD/TiB/month | GET, USD per 1 million requests | PUT, USD per 1 million requests |
	  | --- | ---: | ---: | ---: |
	  | AWS — us-east-2 | 23.55 | 0.40 | 5.00 |
	  | GCP — us-east-1 | 20.48 | 0.40 | 5.00 |
	  | IBM — us-east | 23.55 | 0.42 | 5.20 |
	  | Azure — East US 2 | 23.55 | 0.40 | 6.25 |
	  | OCI — us-ashburn-1 | 26.11 | 0.34 | 0.34 |
	- **Pricing favors batching**: request charges are based on request count, so small reads can be expensive relative to the data retrieved. OCI’s very different PUT price also shows why a read-optimized design and a write-heavy ingestion pipeline can have different cloud economics.
	- The paper’s tested services do not charge separately for transferred bytes in its same-region retrieval setup; its AWS cross-region example costs $0.02/GB. Neither statement should be generalized to all storage classes, network paths or current contracts. Capacity, requests, compute and any applicable transfer charges must be modeled separately.

- ## High throughput requires deliberate request sizing and concurrency
	- The paper models retrieval as `concurrent requests ≈ target throughput × (base latency + request size × per-MiB latency) / request size`. Use consistent units: throughput in MiB/s, request size in MiB and latencies in seconds. The measured S3 inputs are roughly **30 ms base latency** and **20 ms/MiB**; saturating a 100 Gbit/s instance requires approximately **200–250 outstanding requests**.
	- Over eight weeks, individual-request bandwidth varied roughly from **25 to 95 MiB/s**, with a median around **55–60 MiB/s**. With parallel requests, the AWS experiments usually reached median aggregate bandwidth of **80–90 Gbit/s** in eu-central-1. Parallelism exploits many storage servers at once; it does not make each object respond with local-memory latency.
	- **Figure 8, PDF page 4 / printed page 2772**: labeled aggregate throughput by request size on AWS eu-central-1, c5n.18xlarge. Values are transcribed from the chart; the underlying cost bars use historical instance prices of \$3.88/hour on demand and \$1.28/hour spot.
	- | Request size | Aggregate retrieval throughput | Interpretation |
	  | --- | ---: | --- |
	  | 0.5 MiB | 23 Gbit/s | High request overhead and low effective throughput |
	  | 1 MiB | 33 Gbit/s | Larger transfers begin to amortize overhead |
	  | 2 MiB | 51 Gbit/s | Still materially below the throughput plateau |
	  | 4 MiB | 67 Gbit/s | Approaches useful scan bandwidth |
	  | 8 MiB | 75 Gbit/s | Within the authors’ preferred range |
	  | 16 MiB | 81 Gbit/s | Highest labeled throughput in this experiment |
	  | 32 MiB | 80 Gbit/s | Doubling size provides no additional throughput |
	- The authors identify **8–16 MiB as the cost/throughput sweet spot for these OLAP experiments**. Larger requests reduce request fees but delay completion and limit useful parallelism for smaller tables. This is a measured design choice, not a universal optimum for point lookups or every provider.

- ## How AnyBlob and Umbra address the bottlenecks
	- | Engineering challenge | Paper’s mechanism | What it improves |
	  | --- | --- | --- |
	  | Hundreds of requests compete for CPU time | AnyBlob uses io_uring submission/completion queues, batched operations and event-driven connection state machines; multiple requests share each thread. | Avoids one-thread-per-request oversubscription and reduces system-call/context-switch overhead. |
	  | DNS overhead and uneven storage endpoints | Cache multiple endpoint IPs, track throughput and replace poorly performing endpoints. An AWS-specific resolver also seeks larger path MTUs. | Avoids repeated DNS round trips and reduces per-packet CPU work where jumbo frames are available. |
	  | Downloads contend with SQL execution | Umbra’s worker pool switches among query processing, request preparation and retrieval. The scheduler uses observed processing/retrieval rates to adjust the mix. | A compute-heavy query receives more processing workers; a scan-heavy query receives enough retrieval capacity to feed execution. |
	  | Network workers run out of prepared work | The scheduler prepares requests ahead, allowing up to 2× the required outstanding bandwidth. | Keeps retrieval busy without dedicating a fixed oversized pool to downloads. |
	  | Excess bytes and poorly sized objects | Immutable column-major blocks, per-column min/max metadata, column projection and range GETs; oversized columns are split into retrieval-sized requests. | Skips irrelevant data and aligns the on-disk layout with economical network transfers. |
	  | Memory-copy and decoding overhead | Receive data into prepared buffer space; use frame-of-reference/dictionary encodings, integer bit packing and LZ4 compression where appropriate. | Reduces user-space copying and transferred bytes while retaining efficient decoding; this is not a claim of zero copying throughout the network stack. |
	  | Provider APIs differ | AnyBlob exposes a common retrieval interface with provider-specific authentication and endpoint handling. | Simplifies multi-cloud engine integration; underlying cloud performance and pricing remain different. |
	- The column format targets **16 MiB chunks**, but equal row counts across columns mean different encoded byte sizes. During construction, the implementation aims to keep encoded columns above roughly **2 MiB** and splits overly large retrievals. This is why selecting a universal object size without considering schema and compression is inadequate.
	- Data and schema metadata reside in object storage. A list of block headers identifies the active data; atomically replacing that list supports consistent snapshots. The paper focuses on **append-only analytical data** and does not demonstrate a complete high-update-rate transactional database.
	- **Measured downloader gains, Section 3.4 / PDF page 7**: against the tested AWS C++ SDK 1.9.140 alternatives, AnyBlob reaches the same maximum throughput using **0.7× the CPU resources**, or up to **1.5× throughput at a fixed CPU budget**. Its specialized AWS resolver reduces CPU usage by another **10%**; a Graviton test reaches **180 Gbit/s** on a 200 Gbit/s instance. These are version- and environment-specific comparisons.

- ## Query evidence: when remote retrieval is close to in-memory execution
	- **Table 2, PDF page 11 / printed page 2779**, selected rows. TPC-H scale factor 500; AWS c5n.18xlarge with 72 vCPUs, 192 GiB RAM and 100 Gbit/s networking. Remote tests deliberately re-fetch columns instead of reusing previously cached column data. They still require working memory and buffers.
	- | TPC-H query / summary | In-memory runtime | Remote-only runtime | Remote/in-memory factor, as reported | Remote bandwidth |
	  | --- | ---: | ---: | ---: | ---: |
	  | Geometric mean across all queries | 2.03 s | 4.94 s | 2.42× | 49.80 Gbit/s |
	  | Q1 | 1.14 s | 3.52 s | 3.08× | 75.00 Gbit/s |
	  | Q6 | 0.52 s | 2.47 s | 4.78× | 77.73 Gbit/s |
	  | Q9 — compute-heavy example | 10.61 s | 13.34 s | 1.26× | 40.67 Gbit/s |
	  | Q18 — compute-heavy example | 18.91 s | 22.20 s | 1.17× | 15.41 Gbit/s |
	  | Q19 | 0.74 s | 3.82 s | 5.15× | 76.87 Gbit/s |
	- Computation can absorb much of the retrieval time when execution is expensive. Queries with little work per byte remain network-limited even when bandwidth utilization is high. **The paper does not establish universal parity with in-memory execution.** Reported factors use underlying measurements and can differ slightly from ratios of rounded runtimes.
	- In the integrated engine comparison at SF1000, replacing the asynchronous AWS SDK retrieval layer with AnyBlob improves geometric-mean performance by up to **1.2×**, improves compute-heavy queries by up to **40%**, and reduces mean CPU usage by up to **25%**. These compare retrieval implementations within Umbra, not remote storage against local memory.
	- In Figure 20, the authors also compare uncached Umbra against Spark and warm/cold Snowflake configurations at approximately **100 GiB and 1 TiB**. They report performance comparable to a warehouse using local SSD caches. However, Snowflake’s underlying hardware is inferred rather than controlled, and query engines differ: this does not isolate a storage-only advantage or establish current vendor rankings.

- ## What a production object-store warehouse still must solve
	- **Small random reads and strict latency targets**: concurrent bulk retrieval hides latency only when enough independent work exists. Highly selective queries, interactive lookups and repeatedly accessed hot data may still benefit from indexes, metadata services and local caches. The paper’s cold-scan results support elasticity without proving that caches have no value.
	- **Tail latency**: the paper observes fewer than 5% of 16 MiB requests taking over 600 ms, and fewer than 5% exceeding 200 ms to first byte. It proposes hedging/restarting slow requests; these thresholds describe its measurements, not a service-level guarantee. Production hedging also needs controls on duplicate traffic and request charges.
	- **Security consumes resources**: Figure 9 reaches approximately 73 Gbit/s over HTTP, 75 Gbit/s with client-side AES and 74 Gbit/s over HTTPS, but HTTPS uses more than **2×** the CPU of HTTP; client-side AES adds about **30%**. Much of the retrieval study uses HTTP, and the final engine experiment includes compression and AES. Deployment estimates must include the actual TLS/authentication configuration; payload encryption does not replace transport authentication.
	- **Write maintenance and concurrent changes**: immutable objects simplify readers but introduce file rewriting, compaction, small-file management and metadata coordination. Iceberg-style snapshots address table commit correctness; AnyBlob’s efficient download path does not by itself solve ingestion latency, concurrent-update conflicts or garbage collection.
	- **Elasticity requires operational engineering**: avoiding a warm-cache dependency makes resizing and spot instances more attractive, but interrupted queries, recovery, admission control, tenant isolation and predictable p99 latency still need implementation. Object durability alone does not preserve an in-flight query’s progress.
	- **Instance and cloud limits matter**: the paper’s smaller-instance example falls from burst performance to its baseline after about **45 minutes**. Short tests can therefore overstate sustained capacity. Multi-cloud support also does not remove regional performance differences or data-transfer charges.

- ## Where value can accrue in the data platform stack
	- **Investment interpretation**: object storage can consolidate durable data while query engines compete through execution efficiency, workload management, governance and developer experience. Open table formats can make engine substitution easier, increasing pressure to justify a premium through measurable performance and operational value.
	- For AWS, Azure and Google Cloud, a growing object-store data foundation can support both storage consumption and adjacent compute demand. For Snowflake and other managed warehouses, lower infrastructure cost can support margins or lower customer prices, depending on competition and contract structure. The paper supplies engineering evidence, not a forecast of vendor revenue or pricing power.
	- The relevant economic comparison is **total cost per completed workload at the required latency**, including compute time, request fees, retained storage, cache resources, encryption and transfers. Lower storage cost does not guarantee a cheaper query, and using fewer resources per query does not automatically mean lower aggregate consumption if workloads expand.
	- Related: [[2026-06-23-viktor-leis-s3-ssd-disaggregated-storage-economics]]. This paper shows how existing object storage can support high-throughput analytics through parallelism and careful software design. Leis’s later essay explores faster SSD-backed primitives for workloads where per-request latency and small random updates remain limiting.
