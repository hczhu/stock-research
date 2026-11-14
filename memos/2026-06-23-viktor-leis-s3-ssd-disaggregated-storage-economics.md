tags:: [[$AMZN]], [[storage]], [[SSD]], [[HDD]], [[NAND]], [[data-center]], [[cloud]], [[database]], [[ai-model:GPT-6 Astra]], [[ai-effort:medium]]
file-created-at:: 2026-06-23
file-updated-at:: 2026-11-13

- ## S3’s architectural dominance creates an opening for faster shared storage
	- **Source** — Viktor Leis, June 23, 2026. The memo preserves the article’s hardware numbers and architectural argument, with AWS specifications and dated pricing context checked on November 13, 2026. [S3 Is the Future, S3 Is the Past](https://btrblocks.com/blog/s3_is_the_future_and_the_past/)
	- **Thesis** — S3’s inexpensive, durable shared storage underpins modern data software. Leis argues that cheaper SSDs and fast networks could support a new shared-storage service that reduces the caching, batching, metadata and rewriting costs imposed by today’s object-store interfaces. The investment opportunity depends on turning hardware performance into an economical, durable service.

- ## Why S3 became the default foundation
	- S3 offers effectively unlimited capacity, high durability, low capacity cost per GB and high aggregate bandwidth when applications use large objects and parallel requests. Its shared durable namespace lets compute remain largely stateless and scale independently of storage.
	- | Architecture cited in the article | Role of S3 |
	  | --- | --- |
	  | Iceberg + Parquet + S3 | Foundation for the open data lake analytics stack, combining table organization, columnar files and object storage. |
	  | WarpStream | Kafka-compatible streaming built over S3. |
	  | Turbopuffer | Vector storage built over object storage. |
	  | General cloud data systems | System of record, long-term store, backup target and durable source of truth beneath replaceable compute. |
	- S3 launched in 2006, approximately **20 years** before the article. Leis describes its disk-oriented model as “a million hard disks behind an HTTP API,” a characterization of the architecture rather than a disclosed fleet count.

- ## Hardware numbers behind the proposed transition
	- The following figures are Leis’s stated comparisons. SSD device latency and network latency describe components of a system; a complete cloud storage request adds software, queuing and durability overhead.
	- | Dimension | Figure preserved from the article | Architectural significance |
	  | --- | --- | --- |
	  | S3 throughput per individual request | **Less than 100 MB/s** | High aggregate throughput requires concurrency across requests. |
	  | S3 request latency | **Tens of milliseconds** | Small dependent reads are expensive even when bulk throughput is high. |
	  | SSD access latency | **~100 microseconds**, or **0.1 ms** | Approximately **two orders of magnitude** below the S3 latency described by the author. |
	  | SSD I/O rate | **Millions of IOPS per device** | Supports large numbers of small random operations, subject to workload and queue depth. |
	  | Small random SSD access | **Down to 4 KB** reads and writes | Makes fine-grained data and metadata access practical. |
	  | Datacenter network link rate | **100+ Gbit/s** | Provides substantial bandwidth between compute and disaggregated storage. |
	  | Network latency within a datacenter | **Below 100 microseconds** | Could preserve much of the benefit of fast media when compute and storage are separated. |
	  | Network latency across datacenters in the same region | **Below 1 millisecond** | Makes regional replication more practical, while adding latency to operations that wait for remote durability. |
	  | SSD versus HDD capacity cost | SSDs cost **roughly 3×** as much per byte | A smaller hardware premium may be offset by reduced software and compute overhead in suitable workloads. |
	  | Early-2026 price shock, article footnote | The author says **SSD, DRAM and disk prices roughly quadrupled**, broadly together | The long-term SSD cost trend coexists with a sharp cyclical price increase. The article supplies no category-level price series to independently establish that magnitude. |
	- Leis cites a VLDB performance study for the S3 figures and his 2024 LeanStore paper for the hardware economics. The comparisons describe the article’s evidence base and should retain those dates when used in a model. [S3 performance reference](https://www.vldb.org/pvldb/vol16/p2769-durner.pdf) · [LeanStore paper](https://www.vldb.org/pvldb/vol17/p4536-leis.pdf)

- ## What slow object access forces applications to build
	- | Constraint identified by Leis | Current architectural response | Proposed change with fast shared SSD storage |
	  | --- | --- | --- |
	  | High request latency | Cache frequently accessed data closer to compute. | Make latency-hiding caches optional for more workloads. |
	  | High overhead per small request | Batch small writes into larger objects. | Allow efficient small random operations with less mandatory batching. |
	  | Inefficient small random metadata lookups | Maintain a separate metadata database, such as **DynamoDB or FoundationDB**. | Serve metadata and bulk data from one storage system. |
	  | Object-level replacement | Rewrite an object to change a record, with associated reorganization or compaction. | Expose fine-grained logical updates and reduce rewrite amplification. |
	- **Technical interpretation** — SSD media alone cannot provide the new API semantics. The service must expose suitable fine-grained operations and implement replication, concurrency and recovery. Leis’s claim that compaction and reorganization become unnecessary describes the opportunity to eliminate particular object-store workarounds. Caching and maintenance can still serve other purposes. His SSD-focused LeanStore design itself includes caching, indexing, concurrency control, logging, checkpoints and recovery. [LeanStore paper](https://www.vldb.org/pvldb/vol17/p4536-leis.pdf)

- ## S3 Express One Zone illustrates the gap between media and service economics
	- **Leis’s assessment** — Launched in **2023**, Express One Zone still has multi-millisecond latency, a capacity-price premium and per-GB access charges that discourage intensive access. He regards its single-zone protection and pricing as limiting its ability to become a general-purpose S3 replacement.
	- | AWS specification | S3 Standard | S3 Express One Zone |
	  | --- | --- | --- |
	  | Access latency | Milliseconds | **Single-digit milliseconds** |
	  | Availability Zones | **At least three** | **One** |
	  | Designed durability | **99.999999999%**, or 11 nines | **99.999999999%**, or 11 nines |
	  | Designed availability | **99.99%** | **99.95%** |
	  | Resilience to physical loss of an Availability Zone | Designed to withstand it | Exposed to loss of the selected AZ |
	- AWS replicates Express data across devices within its selected zone. The protection difference concerns failure domains and availability as well as the shared headline durability target. These are design targets. [AWS storage-class comparison](https://docs.aws.amazon.com/AmazonS3/latest/userguide/storage-class-intro.html)
	- **Pricing context already available before the article.** AWS cut Express prices on **April 10, 2025**. Its US East (N. Virginia) announcement lists the following rates. These are dated announcement figures.
	- | Billing dimension | Announced price after reduction | Reduction |
	  | --- | --- | --- |
	  | Storage | **$0.11 per GB-month** | **31%** |
	  | PUT requests | **$0.00113 per 1,000 requests** | **55%** |
	  | GET requests | **$0.00003 per 1,000 requests** | **85%** |
	  | Data upload | **$0.0032 per GB** | **60%** |
	  | Data retrieval | **$0.0006 per GB** | **60%** |
	- Per-GB upload and retrieval charges began applying to **all transferred bytes**, replacing the earlier treatment of only request portions above **512 KB**. A high-throughput workload therefore has both request-count and byte-volume economics. [AWS price-reduction announcement](https://aws.amazon.com/blogs/aws/up-to-85-price-reductions-for-amazon-s3-express-one-zone/)
	- Express also supports appending data to an existing object, which extends the object API for logs and streaming workloads. Arbitrary record-level mutation would require further semantics. [AWS feature and pricing announcement](https://aws.amazon.com/blogs/aws/up-to-85-price-reductions-for-amazon-s3-express-one-zone/)

- ## Where a new storage service could capture value
	- **Total system cost matters.** The relevant comparison includes media capacity, replication, requests, byte-volume fees, networking, compute spent caching and rewriting, metadata infrastructure, and engineering operations. A roughly 3× media premium can be economical where the avoided costs are large. Low-access archival workloads have less overhead to eliminate.
	- **Hardware demand and software value could shift together.** Wider use of shared SSD storage would increase opportunities for NAND and SSD suppliers while putting pressure on software layers whose value comes primarily from hiding slow storage. The underlying application still needs data models, indexes, transactions and operational tooling, so the effect depends on which costs a new service actually removes.
	- **Incumbent incentives are the author’s explanation.** Leis argues that hyperscalers’ installed HDD fleets and existing revenue models weaken the incentive to cannibalize S3 economics. AWS’s Express launch and price reductions show ongoing investment, while leaving open the commercial question of how quickly providers will offer broader failure protection and lower-latency, fine-grained storage at attractive prices.
	- **The proposed product is a demanding combination.** It must combine fast random access, shared capacity, durability, availability and economical billing. The investable claim is that savings across the full application can finance that service; its feasibility at S3-like scale and pricing remains an engineering and commercial thesis.
