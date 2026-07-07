- tags:: [[DRAM]], [[HBM]], [[NAND]], [[SSD]], [[CXL]], [[HBF]], [[AI infrastructure]], [[inference]], [[data-center]], [[semiconductor]], [[memory]], [[super-cycle]], [[$MU]], [[$005930.KS]], [[$000660.KS]], [[$AMD]], [[$AAPL]], [[$MRVL]], [[$SNDK]], [[SK-hynix]]

- **Source**: 《天下苦DRAM久矣》, L晨光, 半导体行业观察, July 4, 2026. Extracted from local PDF: `/Users/hc/Downloads/天下苦DRAM久矣.pdf`.
- **Thesis**: The DRAM shock is no longer just a component-price cycle; it is forcing a systems-architecture response. HBM demand is cannibalizing standard DRAM wafer capacity, pushing server DRAM into extreme scarcity and making pure DRAM scaling economically untenable. The industry response is to push warm/cold data, model weights, and lower-frequency inference state down into NAND/SSD/CXL/HBF tiers, making NAND and memory-controller architecture increasingly strategic.

- ## Core Argument
	- Data centers are facing a new bottleneck: not insufficient compute, but unaffordable and scarce memory.
	- DRAM used to be a standard server component. It is now one of the most expensive infrastructure resources because AI inference, in-memory databases, and HPC workloads are expanding faster than supply can respond.
	- The constraint is being amplified by HBM: memory makers are shifting premium wafer capacity toward high-margin HBM, which tightens supply for standard server DRAM, PC DRAM, and mobile DRAM.
	- The resulting pressure is pushing the industry away from "just add more DRAM" and toward hierarchical memory systems that blend HBM/DRAM with NAND flash, SSDs, CXL pooling, hardware compression, and new on-package flash tiers.

- ## Key Data Points

	| Data Point | Value / Claim | Investment Read-through |
	|---|---|---|
	| 64GB DIMM price increase | Counterpoint: 64GB DIMM prices rose **3.5x** from 3Q25 to 1Q26; expected to reach **5x** cumulative increase by 3Q26. | Server DRAM inflation is severe enough to alter system architecture and cloud economics. |
	| DRAM contract pricing | TrendForce: 1Q26 DRAM contract prices rose **93-98% QoQ**; 2Q26 expected to rise another **58-63% QoQ**. | Confirms supply/demand imbalance is flowing through contracts, not only spot markets. |
	| Global DRAM revenue | TrendForce: 1Q26 global DRAM industry revenue rose **81% QoQ** to **USD 97B**. | Memory maker revenue leverage is extreme when both volume allocation and ASP move together. |
	| Server DDR5 RDIMM spot price | Current spot price cited at **USD 27-37 per GB**. | DRAM is becoming a major line item in server BOM and capex planning. |
	| 12TB memory pool cost | 12TB of server DRAM hardware costs nearly **USD 500K** at current spot pricing. | Creates large economic incentive for compression, pooling, and NAND-tiering alternatives. |
	| HBM share of DRAM wafer capacity | HBM rose from **2%** of DRAM wafer capacity in 2020 to an estimated **25%** in 2026. | HBM is structurally crowding out conventional DRAM supply. |
	| HBM wafer-start share | HBM share of total DRAM wafer starts: **18% in 2025**, **22% in 2026**, roughly **30% in 2027**. | Standard DRAM tightness may persist as memory makers prioritize HBM mix. |
	| HBM capacity burden | One HBM wafer is cited as consuming about **3x** the capacity of one DDR5 wafer. | HBM demand has a multiplier effect on conventional DRAM scarcity. |
	| Supply growth | Jefferies: excluding Chinese suppliers, 2026 global memory bit supply growth only **7-8%**. | Supply response is too slow for AI demand growth. |
	| Supply shortfall | DRAM + NAND combined shortfall could reach **150K-200K wafers/month**. | Shortage is broad across memory categories, not isolated to HBM. |
	| DRAM in server BOM | DRAM was about **50%** of server system cost in 2023; by mid-2026 it reached **60-90%**, averaging about **75%**. | Memory now dominates server economics; CPU price changes are secondary. |
	| Memory utilization | Meta-like hyperscaler measurements: only about **half** of data-center memory capacity holds active "hot data." | Huge theoretical TAM for tiering/pooling if cold data can be moved off DRAM without unacceptable latency. |
	| Xbox / consumer spillover | Xbox executive Asha Sharma said memory costs rose about **5x** over two years, limiting console supply. | Memory inflation is spilling from AI infrastructure into consumer hardware availability and pricing. |
	| Apple spillover | Article states Apple is raising prices across iPhone, Mac, and iPad products. | Supports Apple passthrough / memory-cost shock thesis. |

- ## Why the DRAM Crisis Is Happening
	- **HBM cannibalization**: Samsung, SK Hynix, and Micron are shifting high-quality capacity toward higher-margin HBM.
	- **Hyperscaler pre-commitments**: Large cloud and AI customers are signing multi-year long-term agreements that lock future wafer output before standard server DRAM buyers can access it.
	- **Capex lead times**: Advanced DRAM depends heavily on EUV lithography; a single EUV tool costs roughly **USD 200M**, and modern memory fabs require multi-year buildouts and tens of billions of dollars.
	- **Demand velocity**: AI inference, memory databases, and HPC are scaling faster than bit supply can grow.
	- **Capacity mix discipline**: Suppliers are actively cutting or deprioritizing lower-margin mobile and PC orders to chase AI/HBM demand.

- ## Architecture Response: Four Paths Away From Pure DRAM Scaling

	| Company / Path | Mechanism | Claimed Benefit | Stock / Sector Read-through |
	|---|---|---|---|
	| [[$AMD]] / MEXT | AI-driven memory tiering moves cold pages from DRAM to NAND flash and prefetches likely-needed pages back to DRAM. | Effective memory capacity **2-4x**; infrastructure cost down about **50%**; DRAM+flash 1:1 config can reach about **95%** of pure-DRAM throughput in some workloads. | Positive for AMD full-stack AI infrastructure positioning; validates NAND as an active memory tier. |
	| [[$AAPL]] / AFM 3 Core Advanced | Store a 20B-parameter on-device model in NAND; route per prompt and load only a 1B-4B parameter working set into DRAM. | Peak DRAM use held to **2GB-8GB** for a 20B model; builds on "LLM in a Flash" work showing **4-5x CPU** and **20-25x GPU** speedups versus naive loading. | Apple mitigates device DRAM constraints through model architecture; NAND performance matters more for on-device AI. |
	| [[$MRVL]] / Structera CXL | CXL memory controllers with inline hardware compression and decompression. Structera X expands memory; Structera A accelerates near memory. | Physical DRAM effective capacity **2-3.64x** depending on data; mixed database compression ratio cited at **3.64:1**. | Positive for CXL controller / memory-pooling silicon if cloud buyers need capex relief. |
	| [[$SNDK]] + SK Hynix / HBF | Standardize High Bandwidth Flash: NAND physically closer to GPU/AI accelerator, between HBM and SSD in the hierarchy. | HBF targets **8-16x** HBM capacity at lower cost; first samples planned 2H26, AI inference use targeted early 2027; market could reach **USD 12B by 2030** per Shinyoung Securities. | Positive for NAND optionality and advanced packaging, but technical risk remains high. |

- ## AMD / MEXT: Software Memory Tiering
	- AMD acquired MEXT in June 2026 to add AI-driven memory tiering to its data-center stack.
	- MEXT's Predictive Memory Engine continuously monitors application memory-page access patterns, migrates cold pages to NAND flash, and uses AI models to prefetch pages back into DRAM before applications request them.
	- The article cites flash cost per bit at roughly **1/55** of DRAM.
	- Deployment is described as software-only, transparent to OS and applications, and deployable in minutes without dedicated hardware.
	- Test scenarios include Neo4j graph databases, EDA simulation, and film rendering; a 1:1 DRAM-to-flash setup reportedly reaches about **95%** of pure-DRAM throughput at materially lower cost.
	- Risk: NAND and DRAM have a real latency gap. The architecture works only if prediction accuracy is high enough to hide flash latency at scale.

- ## Apple: On-Device Models Stored In Flash
	- Apple's AFM 3 Core Advanced is described as a 20B-parameter on-device model that cannot be fully loaded into consumer-device DRAM.
	- Apple uses sparse activation and prompt-level routing:
		- Full model weights live in NAND flash.
		- Each inference selects the required expert modules once per prompt.
		- Only a 1B-4B parameter working set moves into DRAM.
		- Shared experts stay resident in DRAM to reduce flash-memory traffic.
	- This avoids traditional MoE's token-by-token expert switching, which would create too much flash/DRAM traffic on-device.
	- The result is claimed peak DRAM consumption of **2GB-8GB**, allowing a 20B model to run on iPhone-class devices.
	- Investment read-through: on-device AI may increase NAND performance and capacity value even when DRAM content is constrained by cost, thermals, and device BOM.

- ## Marvell: CXL + Inline Compression
	- Marvell's Structera CXL controller family uses a Compression-Decompression Block with custom LZ4 lossless compression.
	- Compression/decompression occurs inline on the memory link, without host CPU cycles and without application changes.
	- Depending on data type, **1GB** of physical DRAM can behave like **2GB-3.64GB** of logical capacity.
	- Structera X also supports DDR4 memory, allowing older DDR4 to be reused in CXL memory pools instead of buying expensive DDR5.
	- CXL pooling breaks the one-CPU / one-memory-domain model and lets multiple servers share idle capacity.
	- At a 3x compression ratio, the article estimates a 12TB pool can cut physical DRAM purchases by two-thirds, saving more than **USD 300K** per pool at current spot prices.
	- Investment read-through: CXL adoption becomes more likely when DRAM pricing turns memory waste into a visible capex problem.

- ## SanDisk + SK Hynix: HBF As A New Tier
	- SanDisk and SK Hynix are pushing High Bandwidth Flash standardization.
	- The proposed architecture places high-capacity NAND under or near the GPU/AI accelerator, surrounded by HBM stacks, reducing data travel distance and improving flash access bandwidth.
	- HBF is positioned between HBM and SSD:
		- HBM handles immediate ultra-low-latency working data.
		- HBF holds larger, read-intensive data such as long-context inference state, KV-cache spillover, and streamed model weights.
		- SSD remains cold storage.
	- The article says HBF aims for physical compatibility with HBM4 and **8-16x** HBM capacity at lower cost.
	- SanDisk and SK Hynix began the HBF standards alliance in February 2026, with first samples targeted for 2H26 and AI inference-device adoption in early 2027.
	- Risks: high thermal density under compute, hybrid-bonding yield, routing complexity, and software scheduling for hot/warm/cold data all remain unresolved.

- ## 3D XPoint Lesson
	- Intel and Micron's 2015 3D XPoint attempted to create a memory tier between DRAM and NAND: byte-addressable, faster than NAND, cheaper than DRAM.
	- It failed because process development lagged, costs approached DRAM, performance was only several times faster than ordinary flash, and Intel's closed Xeon-tied strategy limited adoption.
	- Lesson for HBF/CXL/tiering: the demand is real, but a new memory tier must hit cost, performance, openness, and ecosystem requirements simultaneously.

- ## Investment Implications
	- **DRAM/HBM suppliers remain near-term beneficiaries**: Pricing data and HBM wafer crowd-out support the memory super-cycle thesis for [[$MU]], [[$005930.KS]], and [[$000660.KS]].
	- **NAND is being pulled up the hierarchy**: AMD/MEXT, Apple flash-resident models, SanDisk HBF, and KV-cache/model-weight offload all make NAND more than passive storage.
	- **Memory optimization becomes a stock theme**: CXL controllers, compression engines, predictive tiering, and software schedulers become more valuable as DRAM cost rises.
	- **Substitution is partial, not total**: These approaches reduce waste and lower DRAM intensity, but they do not eliminate HBM/DRAM for hot, latency-sensitive, write-heavy data.
	- **High DRAM prices create their own demand destruction**: If memory tiering works at scale, it can cap some future DRAM/HBM demand per workload; this is a medium-term bear-case variable for pure DRAM extrapolation.
	- **NAND winners may be more diverse than DRAM winners**: Value can accrue to NAND makers, SSD vendors, controller vendors, CXL silicon, packaging providers, and accelerator platform owners.

- ## What to Monitor
	- Whether 64GB DIMM pricing reaches the cited **5x** cumulative increase by 3Q26.
	- HBM share of DRAM wafer starts moving toward **30%** in 2027.
	- Cloud customer adoption of MEXT-like predictive memory tiering and real-world latency/performance results.
	- Apple's on-device AI memory footprint and whether future iPhones emphasize NAND bandwidth/capacity alongside DRAM.
	- Marvell Structera design wins, OCP standardization progress, and CXL memory-pooling deployment at hyperscalers.
	- SanDisk/SK Hynix HBF samples in 2H26 and whether early 2027 inference-device adoption materializes.
	- Any evidence that memory tiering slows DRAM/HBM bit growth per AI workload, versus simply enabling larger workloads and increasing total memory consumption.
