- tags:: [[semiconductor]], [[inference]], [[AI infrastructure]], [[data-center]], [[HBM]], [[HBF]], [[DRAM]], [[NAND]], [[packaging]], [[$NVDA]], [[$TSM]], [[$MU]], [[$MRVL]]
  file-created-at:: 2026-06-07

- **Source**: "Challenges and Research Directions for Large Language Model Inference Hardware," Xiaoyu Ma and David Patterson (Google), arXiv PDF: https://arxiv.org/pdf/2601.05047

- ## Bottom line
	- The paper's core investment message is that **LLM inference bottlenecks are shifting away from raw FLOPS and toward memory capacity, memory bandwidth, and interconnect latency**.
	- That is bullish for the parts of the semi stack that solve the **decode-phase memory wall**: HBM, advanced packaging, low-latency networking, and potentially a new on-package NAND tier via **High-Bandwidth Flash (HBF)**.
	- It is also a warning that the current "more giant reticle dies + more FLOPS" framing is incomplete. Future AI hardware spend may tilt further toward **memory architecture, 3D integration, and communication fabrics**, not just accelerator compute silicon.

- ## Main arguments from the paper
	- **Inference, not training, is the economic problem**:
		- The authors argue the cost of inference determines economic viability as model usage scales.
		- They cite forecasts for **AI inference chip annual sales to grow 4x-6x over the next 5-8 years**.
	- **Decode is fundamentally memory-bound**:
		- Transformer inference has two phases:
			- **Prefill**: parallel and often compute-bound
			- **Decode**: sequential/autoregressive and therefore memory-bound
		- The practical implication is that scaling compute alone does not fix the hardest part of serving large models.
	- **The workload is getting harder in exactly the wrong way for current hardware**:
		- **MoE** increases memory and communication demands
		- **Reasoning models** increase latency and memory strain through long "thinking" token sequences
		- **Long context** and **RAG** expand KV-cache and retrieval requirements
		- **Multimodal** inference raises data movement requirements
	- **Current AI hardware is mismatched to decode inference**:
		- The paper explicitly argues that the current hardware philosophy of **full-reticle die + many HBM stacks + bandwidth-optimized interconnect** is a poor fit for decode-heavy inference.
		- Their proposed focus areas are:
			- **HBF** for much more memory capacity
			- **PNM / 3D memory-logic stacking** for higher effective memory bandwidth
			- **Low-latency interconnect** for multi-chip inference systems

- ## Decode bottleneck matrix
	- The table's most useful contribution is that it separates **what future inference trends stress** from **which hardware directions might relieve that stress**.
	- The headline is simple: for transformer decode, the bottlenecks are overwhelmingly **memory capacity, memory bandwidth, and interconnect latency**, while **compute is only the primary bottleneck for diffusion-style workloads**.

	| Decode feature / research direction | Memory capacity | Memory bandwidth | Interconnect latency | Compute |
	|---|---|---|---|---|
	| Conventional transformer decode |  | primary | primary |  |
	| MoE | primary | primary | primary |  |
	| Reasoning models | primary | primary | derived / likely |  |
	| Multimodal | primary | primary | derived / likely |  |
	| Long-context | primary | primary | derived / likely |  |
	| RAG | primary | primary | derived / likely |  |
	| Diffusion |  |  |  | primary |
	| High Bandwidth Flash | helps |  | helps indirectly by shrinking system size |  |
	| Near Memory Compute |  | helps | helps indirectly by shrinking system size |  |
	| 3D Compute-Logic Stacking |  | helps | helps indirectly by shrinking system size |  |
	| Low-Latency Interconnect |  |  | helps directly |  |

	- **Conventional transformer decode** is already constrained by bandwidth and hop latency, which means simply adding more FLOPS does not solve the dominant inference pain point.
	- **MoE** is the harshest generalization of the problem because it stresses all three: capacity, bandwidth, and communication. That is a strong read-through for HBM, packaging, and networking at the same time.
	- **Reasoning, multimodal, long-context, and RAG** all primarily worsen memory capacity and bandwidth needs, and then create a *derived* interconnect problem if the larger working set forces the model across more chips or nodes.
	- **Diffusion is the exception** in this table. The authors explicitly treat it as the case where more compute is the main answer, unlike transformer decode.
	- The bottom half of the table is essentially a ranking of where money can go if the industry wants to improve decode economics **without relying on more compute alone**:
		- **High Bandwidth Flash (HBF)** attacks capacity first
		- **Near Memory Compute** and **3D compute-logic stacking** attack bandwidth first
		- **Low-latency interconnect** attacks hop cost directly

- ## Why the interconnect column matters
	- The table makes a subtle but important point: interconnect latency is often a **second-order bottleneck caused by memory limits**.
	- If a model or KV cache no longer fits within fewer accelerators, the system expands across more chips and racks. That raises hop count, which turns a memory-capacity problem into an interconnect-latency problem.
	- The reverse is also true: if HBF, near-memory compute, or 3D stacking lets the same inference workload run on fewer accelerators, the system shrinks and hop count falls. That means some "memory" solutions are also hidden interconnect solutions.

- ## Key data points worth carrying into semi work
	- **Performance and cost trends**
	
	  | Topic | Data point | Why it matters |
	  |---|---|---|
	  | Compute vs memory scaling | NVIDIA GPU FP64 FLOPS rose **80x** from 2012 to 2022; memory bandwidth rose only **17x** | The inference bottleneck shifts toward memory bandwidth rather than raw compute |
	  | HBM bandwidth progression | HBM stack bandwidth rose from **128 GB/s** in 2013 to **2,048 GB/s** for HBM4 in 2026 | HBM is still improving aggressively, but not enough to close the memory-wall gap |
	  | HBM capacity progression | Max HBM stack capacity rose from **4 GiB** to **64 GiB** | Capacity growth exists, but remains small relative to the needs of giant inference models |
	  | HBM economics | Normalized HBM **$/GB** and **$/GBps** both increased **1.35x from 2023 to 2025** | Supports pricing power for HBM suppliers, but also creates incentive for substitution |
	  | DDR economics | DDR4 normalized capacity cost fell to **0.54x** and bandwidth cost fell to **0.45x** from 2022 to 2025 | Commodity DRAM keeps getting cheaper, widening the economic gap vs HBM |
	  | DRAM density scaling | A **4x** gain from 8Gb DRAM dies introduced in 2014 will take **more than 10 years** vs historical **3-6 years** for prior 4x gains | Reinforces that memory scaling is slowing structurally |
	- **HBF vs incumbent memory tiers**

	  | Memory type | Capacity (GB) | Bandwidth (GB/s) | Power (W) | GB/s per W | GB per W | Read latency (ns) | Bytes per read | Write endurance |
	  |---|---:|---:|---:|---:|---:|---|---:|---|
	  | **1 HBF stack** | **512** | **1,638 (read)** | **<80** | **>20.5** | **>6.4** | **1,000s** | **4,096** | **low** |
	  | **1 HBM4-6400 stack** | **48** | **1,638** | **40** | **41** | **1** | **10-100** | **32** | **high** |
	  | **1 DDR5-6400 64GB module** | **64** | **51** | **12** | **4** | **5** | **10-100** | **64** | **high** |
	  | **1 LPDDR5-6400 16GB module** | **16** | **51** | **3** | **17** | **5** | **10-100** | **64** | **high** |
	  | **1 flash card** | **4,096** | **4 (read)** | **50** | **0.1** | **82** | **10,000s** | **4,096** | **low** |
	- **Read-through**:
		- HBF is presented as roughly **10x the capacity of HBM at similar bandwidth**, which is why the paper treats it as a serious answer to decode-phase capacity pressure.
		- HBM still wins clearly on **latency, bandwidth per watt, and endurance**.
		- DDR and LPDDR remain much cheaper and lower-latency than HBF, but their bandwidth is nowhere close to accelerator-class memory needs.
		- Flash cards win overwhelmingly on raw capacity, but miss by orders of magnitude on latency and by hundreds of times on bandwidth.
	- **Why the authors think HBF is attractive**:
		- It combines near-HBM bandwidth with flash-like capacity by stacking flash dies in an HBM-style form factor.
		- The paper's economic claim is that this can deliver **10x memory capacity per node**, which reduces total system size, power, TCO, CO2e, and network overhead.
		- It also gives HBF a better long-term scaling story than DRAM because flash capacity is still described as doubling roughly every **three years**, while DRAM density growth is decelerating.
	- **Why HBF cannot replace all HBM**:
		- **Limited write endurance** means HBF is best for infrequently updated data such as model weights or slow-changing context, not constantly rewritten working memory.
		- **Page-based reads with high latency** mean flash reads happen at larger granularity and materially worse latency than DRAM. Small reads reduce effective bandwidth in practice.
		- The system implication is that HBF is a **bridge tier**: it expands capacity dramatically, but normal DRAM / HBM is still required for latency-sensitive and write-heavy data.
	- **The paper's HBF use-case framing**:
		- **10x weight memory**: HBF can hold much larger frozen model weights during inference, which is especially relevant for very large MoE-style models.
		- **10x context memory**: HBF is not appropriate for per-token KV-cache writes, but it can hold slow-changing context stores such as web corpora, code corpora, or paper databases used for search, coding, and tutoring.
		- **Smaller inference systems**: higher capacity per node can shrink the number of accelerators required to host a model, which helps communication overhead, reliability, and resource allocation.
		- **Greater resource capacity**: HBF reduces dependence on pure HBM-only architectures and could alleviate some pressure on the global supply of mainstream memory devices.
	- **PNM vs PIM matters commercially**

	  | Dimension | PIM | PNM | Winner |
	  |---|---|---|---|
	  | Examples | Samsung HBM-PIM; SK Hynix GDDR-PIM; UPMEM logic die on DIMM | Compute on HBM base die; AMD DRAM-logic 3D stacking; Marvell Structera CXL-PNM | — |
	  | Data movement power | Very low (on-chip) | Low (off-chip but nearby) | PIM |
	  | Bandwidth (per watt) | Very high (**5x-10x** of standard) | High (**2x-5x** of standard) | PIM |
	  | Memory-logic coupling | Memory and logic on one die | Memory and logic on separate dies | PNM |
	  | Logic PPA (performance, power, area) | Slower and higher-power logic if built in a DRAM process | Logic in a logic process helps performance, power, and area | PNM |
	  | Memory density | Worse since shared with logic | Not affected | PNM |
	  | Commodity memory pricing (per GB) | No. Lower volume, fewer suppliers, lower density vs memory without logic | Yes. Not affected | PNM |
	  | Power / thermal budget | Logic has tight power and thermal budget on a memory die | Logic is less constrained by power and thermal limits | PNM |
	  | Software sharding | Bank parallelism needs sharding workloads to banks (e.g. **32-64 MB**) | Less restrictive on sharding (e.g. **16-32 GB**); no need to shard to memory banks | PNM |
	- **Read-through**:
		- PIM wins on **raw efficiency** because data movement stays on-chip and bandwidth per watt is higher.
		- PNM wins on **commercial scalability** because it preserves commodity memory economics, avoids forcing logic into a DRAM process, keeps memory density intact, and is much easier to program around.
		- The practical conclusion for datacenter inference is that PNM looks more deployable at scale even if PIM looks better on narrow efficiency benchmarks.
	- **3D memory-logic stacking**
	
	  | Claim | Data point | Why it matters |
	  |---|---|---|
	  | Bandwidth | Compute-on-HBM-base-die can keep **HBM-level bandwidth** | Memory-adjacent compute does not require sacrificing bandwidth |
	  | Power | Power can be **2-3x lower** because of shorter data paths | Important for inference TCO, rack density, and thermals |

- ## What matters for semi investors
	- **Memory remains the first-order bottleneck**:
		- This paper reinforces the existing bullish case for HBM and server DRAM: inference scaling pushes memory harder than consensus still appreciates.
		- It also strengthens the case that **NAND/flash becomes more strategic**, not just cheaper bulk storage, if HBF or related near-flash architectures become real.
	- **HBM scarcity should persist, but HBM may not capture every dollar of future memory growth**:
		- Bullish: the paper is explicit that HBM is capacity-constrained and increasingly expensive.
		- Nuance: if HBF emerges, some future inference memory spend could shift from incremental HBM content toward **on-package or near-package flash tiers**.
	- **Advanced packaging value increases**:
		- The proposed solutions all depend on tighter integration between logic and memory:
			- HBM-style stacking
			- TSV-based 3D stacking
			- base-die compute
			- possibly flash stacked like HBM
		- That is supportive for the packaging layer of the stack, especially foundry/platform vendors with leadership in **CoWoS / SoIC / Foveros / hybrid bonding / interposer-style integration**.
	- **Networking/interconnect becomes a bigger part of the AI bill of materials**:
		- The paper argues inference cares more about **latency than bandwidth** for many small messages.
		- It explicitly highlights:
			- high-connectivity topologies
			- in-network reduction / processing-in-network
			- placing compute closer to the NIC
		- This is bullish for low-latency AI networking and switch silicon, not just GPUs.
	- **Commercially, PNM looks more investable than PIM for datacenter inference**:
		- The authors are clear that PNM is the better datacenter fit because it preserves commodity memory economics and is much easier to program.
		- That is important because it favors solutions that extend or augment the current ecosystem rather than requiring a full bespoke memory-compute redesign.

- ## Company-level read-through
	- **Memory Big 3 (Samsung, SK hynix, Micron)**:
		- Positive on the existing HBM/DRAM thesis because the paper reinforces the memory wall, HBM cost pressure, and DRAM density slowdown.
		- Incrementally positive on NAND optionality because **HBF reframes flash as a future inference-memory tier**, not just SSD storage.
		- Samsung looks especially well positioned conceptually because it spans NAND, DRAM/HBM, and advanced packaging / logic integration.
	- **TSMC / Intel packaging ecosystem**:
		- Beneficiaries if the architectural roadmap shifts toward more 3D integration and more memory-logic co-packaging.
		- The paper is effectively a vote for more value migrating into the packaging/integration layer.
	- **NVIDIA and AI-networking vendors**:
		- Positive for $NVDA not only as GPU vendor but as a networking / system-architecture vendor.
		- The paper's interconnect section aligns with the importance of **NVLink, InfiniBand SHARP, and in-network acceleration**.
		- It also supports the view that full-stack AI system design matters more than chip-level FLOPS leadership alone.
	- **Marvell / CXL-memory-expansion style players**:
		- Positive read-through because the paper explicitly cites **Marvell Structera CXL-PNM** as an example of a more software-friendly near-memory approach.
		- If inference systems become more heterogeneous, memory-expansion and memory-fabric controllers could capture more value.
	- **Cerebras / Groq-style SRAM-first approaches**:
		- The paper is skeptical that SRAM-only architectures can carry the full workload as model sizes grow.
		- That does not kill the thesis for niche latency-sensitive systems, but it weakens the idea that SRAM alone can route around external memory indefinitely.

- ## Most important sections to feed back into existing memory work
	- **For [[DRAM-memory-ssd-index-thesis]]**:
		- Strong support for the claim that AI is turning memory into a strategic bottleneck rather than a commodity
		- Strong support for HBF as a real architectural possibility that can **expand NAND's role in inference**
		- Good evidence that **HBM economics worsen as technical complexity rises**, which supports pricing power but also motivates architectural substitution
	- **For [[2026-06-06-nvidia-cmx-kv-cache-flash-storage-tier]]**:
		- HBF is a more aggressive version of the same idea as CMX: flash moving up the memory hierarchy toward active inference
		- The common theme is that **NAND becomes a performance memory tier**, not just archival storage
	- **For packaging / networking work**:
		- The paper strengthens the idea that future AI semi winners include not just compute and memory vendors, but also **advanced packaging** and **low-latency interconnect** suppliers

- ## What is still speculative / what to watch
	- This is a **research agenda**, not a proof that these architectures are commercially imminent.
	- The biggest open questions are:
		- whether **HBF** can overcome endurance and read-latency issues well enough for real deployment
		- whether value accrues to **memory vendors** or instead to **system integrators / foundries / accelerator vendors**
		- whether **PNM** can move from promising demos into standard datacenter deployments
		- whether low-latency interconnect wins are enough to materially change cluster-level economics
	- The right monitoring variables:
		- HBF prototypes turning into product roadmaps
		- more commercial **compute-on-memory-base-die** announcements
		- growth in **CXL memory expansion / near-memory controllers**
		- evidence that hyperscalers optimize for **latency-per-token** and **performance-per-watt**, not just raw training-class FLOPS
