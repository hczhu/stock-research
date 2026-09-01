tags:: [[OpenAI]], [[$NVDA]], [[$AVGO]], [[$AMD]], [[Cerebras]], [[Celestica]], [[Samsung]], [[$TSM]], [[$ANET]], [[custom-silicon]], [[ASIC]], [[inference]], [[HBM]], [[networking]], [[perf-per-watt]], [[TCO]], [[semiconductor]]

- ## SemiAnalysis on Jalapeño: the primary source — spec tables, TCO, and why the win is bandwidth per watt, not FLOPs
	- **Source**: SemiAnalysis, **"OpenAI Jalapeño: Better Than Nvidia Blackwell"**, Bryan Shan, Myron Xie, Jordan Nanos and three others, **August 25, 2026** (paywalled). OpenAI invited SemiAnalysis to its lab to benchmark the chip with **InferenceX**.
	- **Why this file exists**: two memos already on file — [[2026-08-28-semi-doped-openai-jalapeno-hot-chips-teardown]] and [[2026-08-28-stratechery-mac-refresh-memory-pricing-and-jalapeno]] — cover Jalapeño **secondhand**. This is the primary source with the actual comparison tables, and it **resolves the load-bearing dispute those memos left open.**
	- **Thesis**: The headline "better than Blackwell" is true but framed to flatter. **Jalapeño does not beat Rubin on raw performance — Rubin has 2.6× the FP4 FLOPs.** What Jalapeño has is **roughly 2× Rubin's HBM bandwidth per watt**, and since decode is bandwidth-bound, that is the entire result. The correct claim is narrower and more durable than the title: **a first-generation ASIC matched the incumbent's next-generation part on the axis that determines inference economics, at a third of the power.**
- ## The chip comparison table — as published
	- | Chip | FP16 | FP8 | FP4 | HBM capacity | HBM bandwidth | TDP |
	  |------------|-------------|--------------|--------------|--------------|---------------|-----------------|
	  | H100 | 0.989 PFLOPS | 1.979 PFLOPS | — | 80 GB | 3.35 TB/s | 700 W |
	  | H200 | 0.989 PFLOPS | 1.979 PFLOPS | — | 141 GB | 4.80 TB/s | 700 W |
	  | MI355X | 2.3 PFLOPS | 4.6 PFLOPS | 9.2 PFLOPS | 288 GB | 7.987 TB/s | 1,400 W |
	  | GB200 | 2.5 PFLOPS | 5 PFLOPS | 10 PFLOPS | 192 GB | 8 TB/s | 1,200 W |
	  | GB300 | 2.5 PFLOPS | 5 PFLOPS | 15 PFLOPS | 288 GB | 8 TB/s | 1,400 W |
	  | **Jalapeño** | — | **3.4 PFLOPS** | **13.4 PFLOPS** | **216 GiB** | **15.4 TB/s** | **700 W** |
	  | Rubin | 4 PFLOPS | 17.5 PFLOPS | 35 PFLOPS | 288 GB | 20 TB/s | 1,800–2,300 W |
	  | MI450X | 10 PFLOPS | 20 PFLOPS | 40 PFLOPS | 432 GB | 23.347 TB/s | 2,500 W |
	- **The derived efficiency columns, also as published:**
	  | Chip | HBM bandwidth per W (GB/s/W) | FLOPs per W (TFLOP/W, FP4) |
	  |------------|------------------|-------------------|
	  | H100 | 4.79 | 2.8 |
	  | H200 | 6.86 | 2.8 |
	  | MI355X | 5.71 | 6.6 |
	  | GB200 | 6.67 | 8.3 |
	  | GB300 | 5.71 | 10.7 |
	  | **Jalapeño** | **22** | **19.1** |
	  | Rubin | 11.1 – 8.7 | 19.4 – 15.2 |
	  | MI450X | 7.86 | 16 |
	- **I recomputed every cell from the raw specs and the table is internally consistent** — 15.4 TB/s ÷ 700 W = 22.0; 13.4 PFLOPS ÷ 700 W = 19.1; Rubin's ranges correspond exactly to its 1,800 W and 2,300 W configurations.
- ## The single most important reading of that table
	- **On compute per watt Jalapeño is not ahead.** 19.1 TFLOP/W against Rubin's **19.4** at Max-Q. The article says so directly — "comparable to the 1,800 W Rubin Max-Q config." **Jalapeño only beats Rubin on FLOPs/W when Rubin is run at full 2,300 W power**, where Rubin drops to 15.2.
	- **On memory bandwidth per watt it is not close.** **22 GB/s/W versus 11.1 at Rubin Max-Q (1.98×) and 8.7 at full power (2.53×).** Jalapeño roughly doubles the best merchant silicon on this metric and is **3–4× every shipping Blackwell and MI355X part.**
	- **This is the whole thesis, and the article never states it this plainly.** Decode is memory-bandwidth-bound, not compute-bound — each generated token must stream the weights and the KV cache. A chip with 2× the bandwidth per watt and merely comparable compute per watt will win decode throughput per megawatt and lose nothing that matters. **The design is not a general-purpose accelerator that happens to be efficient; it is a decode engine that bought bandwidth with the power budget it saved on FLOPs.**
	- **The corollary is the risk.** Jalapeño's advantage is specific to bandwidth-bound serving. **On prefill — which is compute-bound — Rubin's 2.6× raw FP4 advantage is real and Jalapeño has no answer.** That OpenAI runs a single fungible pool means it must serve prefill on this silicon too, and no prefill benchmarks were shown.
- ## System TCO and power — the table that actually decides deployments
	- | Chip | All-in power per chip | TCO \$/chip/hr |
	  |---------------|-----------------------|---------------|
	  | H100 | 1.37 kW | \$1.55 |
	  | H200 | 1.37 kW | \$1.59 |
	  | B200 | 1.71 kW | \$2.07 |
	  | B300 | 1.9 kW | \$2.52 |
	  | GB200 | 1.87 kW | \$2.26 |
	  | GB300 | 2.12 kW | \$2.79 |
	  | VR200 | 3.3 kW | \$3.61 |
	  | MI300X | 1.39 kW | \$1.16 |
	  | MI325X | 1.69 kW | \$1.32 |
	  | MI355X | 2.09 kW | — |
	  | RTX 6000 PRO | 0.975 kW | \$0.75 |
	  | **Jalapeño** | **1.125 kW** | **\$1.56** |
	- **Jalapeño costs about the same per chip-hour as an H100 while carrying 15.4 TB/s of HBM4** — and **one third the all-in power of a VR200 at 43% of the cost.**
	- **But on performance per TCO dollar, Vera Rubin and Jalapeño are head-to-head** — "almost the same output tokens per \$." The perf/W gap does not translate into a proportional perf/\$ gap, because Nvidia's part delivers more raw work per chip.
	- **And the comparison is not like-for-like in OpenAI's favour**: Jalapeño's results use **single-token prediction with no speculative decoding**, while the Vera Rubin numbers include it. **SemiAnalysis puts speculative decoding at a 3–5× reduction in cost per token.** Read literally, that headroom belongs to Jalapeño — but it is unrealized, and unrealized headroom is not a benchmark.
	- **Part of the TCO advantage is simply margin arbitrage** — trading Nvidia's gross margin for Broadcom's lower (though still high) one. The article is careful that this is not the whole story, since Meta MTIA and Microsoft MAIA had the same arbitrage available and never got off the ground.
- ## The nine-month question is now resolved — and my earlier caution was right to be cautious
	- [[2026-08-28-semi-doped-openai-jalapeno-hot-chips-teardown]] flagged the "nine months" claim as **measured on the flattering boundary** (RTL freeze to tapeout) and noted the impressive metric would be *concept* to tapeout. **The primary source supplies it.**
	- | Milestone | Date |
	  |------------------------------|-----------|
	  | Design work begins / hiring | mid-2024 |
	  | Architecture concept | Oct 2024 |
	  | Initial RTL | Feb 2025 |
	  | RTL freeze | Jul 2025 |
	  | **Tapeout** | **Nov 2025** |
	  | First silicon | May 2026 |
	  | Codex running on Jalapeño | May 2026 |
	- **So: ~16 months from initial team hiring to manufacturing tapeout, ~13 months from architecture concept, and 9 months from first RTL.** The nine-month figure was the narrowest of three defensible framings — **but the 16-month concept-to-tapeout number is the genuinely remarkable one, and it holds.**
	- **Two details that make it more impressive than the headline**: the November tapeout was of **the full CoWoS design**, not just the top die; and there were **only three months of bring-up on real silicon** before these benchmarks.
	- **The comparison SemiAnalysis draws is the sharp one**: **Rubin's CoWoS tapeout completed October 2025 — one month earlier than Jalapeño** — yet the only public results are CoreWeave engineering samples. "Nvidia has not let us test and release benchmarks in the same way OpenAI has, indicating their chip software is still immature." **A first-time ASIC team reached production-grade software faster than Nvidia did on a contemporaneous part.**
- ## Measured performance, and the four caveats that constrain it
	- **DeepSeek R1**: **over 700 tok/s/user at concurrency 1**, on an eight-chip system, using **single-token prediction with no speculative decoding and no prefill-decode disaggregation.**
	- **GPT-OSS**: **~1,400 tok/s/user**; at iso-interactivity, throughput per MW is **nearly double GB200's best throughput point and more than 50× GB200's concurrency-1 point.**
	- **Kimi K2.5** (the base for Cursor Composer 2.5): nearly 700 tok/s/user, and **more than 9× the next best chip at 100 tok/s/user.**
	- **Jalapeño's STP throughput per MW surpasses Vera Rubin's July MTP results** — a single-token-prediction configuration beating a speculative-decoding one. GSM8K accuracy on par with Nvidia parts.
	- **The caveats are stated by the authors and should be carried with every number above**:
		- **All numbers were supplied by OpenAI.** SemiAnalysis witnessed InferenceX runs in person but **did not run the full suite.**
		- **No AgentX results** — SemiAnalysis's own preferred suite covering long context, multi-turn, and cache behaviour. Their explicit warning: *"frameworks that perform well on 8k1k may perform worse on AgentX."* **Every headline figure here is 8k input / 1k output.**
		- **The Blackwell comparison is "somewhat incomplete and unfair."** Jalapeño's real competitor is Rubin, which also uses HBM4. Vera Rubin NVL72 delivers **5.4× the perf/MW of GB200 NVL72** — so beating GB200/GB300 is beating a generation-old target.
		- **The models tested are not on the open frontier.** Nvidia and AMD have published on larger models (DeepSeek V4 Pro, Kimi K3) using AgentX.
	- **Net**: this is a vendor-supplied, single-shape, generation-favourable benchmark set, verified only by observation. **The directional result is credible; the magnitudes are the ceiling, not the expectation.**
- ## Silicon and system details worth keeping
	- **All published results are from the A0 stepping.** **B0 is already in fab with a claimed ~25% perf-per-watt improvement** — meaning the table above understates the shipping part.
	- **13.4 PFLOPs MXFP4 on a single reticle-sized compute die on TSMC N3P**, against **17.5 PFLOPs dense NVFP4** for a similar-size Rubin die on the same node — at **700 W versus Rubin's 900–1,150 W per compute die.**
	- **HBM4 at 10 Gbps pin speed, against the 9.6 Gbps Nvidia is getting in Rubin — likely supplied by Samsung.** OpenAI is an early HBM4 adopter after only Nvidia and AMD, **ahead of both TPU and Trainium.** This is a concrete read-through for [[Samsung]]'s HBM position, which has been the weakest of the three vendors.
	- **I/O chiplet on N3E**: 32 lanes of 800G SerDes — **24 lanes (600 GB/s) local scale-up, 8 lanes (200 GB/s) global scale-up** to the 2,048-XPU domain. PCIe Gen 5 to an x86 host.
	- **Architecture**: weight-stationary systolic array using MXFP formats, TPU-like, **but supporting small matrix shapes** — avoiding the performance cliffs that force TPUs, Trainium, and Etched into large batches or exactly-divisible dimensions. **64 core slices paired to 64 HBM slices**, each with a low-latency local view of its own slice, synchronized over a dedicated collective network. **Out-of-order cores with an L1 cache** rather than the software-managed scratchpad plus async DMA every other accelerator uses.
	- **AI-assisted design delivered an 8% reduction in SIMD area and 10% in matrix-engine area**, with AI-generated blocks improving on human timing and power.
	- **Rack system**: 16 **"Katsu"** host trays (2 Turin AMD EPYC, 1.5 TB DRAM each) paired to 16 **"Vindaloo"** ASIC trays of 8 chips = **128 Jalapeño per rack**, plus 8 **"Chana"** switch trays (6 local Tomahawk 6, 2 global at 204.8T). **Host rack ~50 kW provisioned (31 kW in production), ASIC rack 130 kW, ~160 kW total — "basically a double-wide GB300 rack."** System design with **Celestica**.
	- **Scale-up fabric**: 4.8 Tb/s per XPU unidirectional locally (6,144 differential pairs of passive copper per rack); **1.6 Tb/s per XPU globally over an 8-rail rail-only architecture with optical circuit switches**, reaching **2,048 XPUs across 16 racks**. **Scale-up networking is only ~10% of system cost** — cheap optionality for **10–20 trillion parameter models or 2–4 million token contexts.**
- ## Software is the real story, and it is the one with the widest read-through
	- **OpenAI writes Jalapeño kernels like assembly** — hand-tuned, some **~3,000 lines**, backed by correctness checks and a custom sanitizer. Internal serving engine is called **"Teacup"**; a simulator called **"chilisim"** is accurate to within 5% of measured hardware.
	- **The programming language is Gluon**, built on Triton, preserving SPMD but exposing low-level abstractions. Its distinguishing feature is **the layout**, formalized via **Linear Layouts**, a layout algebra OpenAI invented — enabling provably correct layout conversions and optimal memory swizzling. Each Gluon program maps to a persistent thread.
	- **The most telling single fact in the article**: **OpenAI had no internal MLA kernel implementation at all until they benchmarked DeepSeek with InferenceX. Codex wrote functional and efficient kernels quickly, without the kernel engineering team intervening.**
	- **The stated design philosophy follows from that**: (1) design for the highest upper-bound performance across all workload shapes, (2) **let Codex do the tedious work of finding kernels that reach it.** Hence the out-of-order-plus-L1 choice — less predictable than a scratchpad, but tolerable when a model with detailed tracing is doing the tuning.
	- **SemiAnalysis's conclusion is the one to carry**: *"If Jalapeño is a success, it will be a strong signal that the industry's obsession over programming models and perfect, universal compilers are invalidated by frontier AI models."* And more bluntly: **"The CUDA moat is potentially dead given how fast OpenAI can bring up new models on their silicon."**
	- **This is the mechanism, and it generalizes past OpenAI.** CUDA's moat was never the ISA — it was the accumulated human-years of kernel engineering. **If a frontier model collapses that cost, the moat's depreciation schedule changes for every accelerator vendor simultaneously**, and the beneficiaries are whoever has silicon but not software: AMD, the ASIC programs, and the neoclouds. It is consistent with the TileRT argument in [[2026-08-09-semianalysis-tilert-inferencex-gpu-vs-dataflow-asic]] that the software layer, not the die, is where inference economics were being lost.
	- **The irony the authors name**: **GPT 5.6 Sol, running on Nvidia GPUs, was used to design the chip threatening the CUDA moat** — "NVIDIA's own GPUs are helping usher in their potential successor in real time."
	- **Development velocity as evidence**: **>2× throughput improvement at certain interactivities in under two weeks**, and **TP32 rack-scale configs enabled in 8 days** building on TP8. Codex-written demos include **Doom at 36 FPS**, ported with two prompts.
- ## Why OpenAI rejected prefill-decode disaggregation — the decision with the biggest read-through for Nvidia
	- **PDD looks attractive only when the workload is frozen.** Input and output lengths, concurrency, cache-hit rates, speculative-acceptance rates, and latency targets **all move through the day**. A fixed split is efficient only near its design point.
	- **The failure mode is asymmetric and expensive**: once devices are partitioned, too much prefill demand leaves decode chips idle while requests queue, and vice versa. **In a disaggregated system an entire chip sits idle because it belongs to the wrong pool. Local utilization looks better; global utilization can be bad.**
	- The same argument applies twice more: **context length shifts the attention/FFN balance**, and **speculative decoding requires draft and verifier to share a low-latency fabric** — separating them "turns a tightly coupled decoding loop into a distributed protocol" whose coordination cost can consume the latency drafting saved.
	- **The concession**: disaggregation still wins where demand is large, stable and predictable, particularly when conventional GPUs need large phase-specific batches. **But it is not free lunch.**
	- **The commercial consequence for Nvidia is the sharpest point in the article.** **Nvidia's Dynamo stack is built on splitting prefill and decode across separate GPU pools, with compute-dense Nvidia GPUs handling prefill.** That architecture assumes Nvidia keeps the prefill pool **even if specialized chips like Cerebras or Groq win decode.** **Jalapeño rejects that assumption entirely — one homogeneous pool, no dedicated prefill fleet.** If the fungible-pool design wins, Nvidia loses not just decode share but the fallback position its software strategy was built to defend.
	- This connects directly to the fabric contest in [[2026-08-31-nvidia-mediatek-convertible-nvlink-fusion]]: NVLink Fusion concedes the die to defend the rack. **A homogeneous non-Nvidia pool concedes nothing.**
- ## Read-through by name
	- **Nvidia** — the threat is negotiating leverage as much as displaced volume. A custom ASIC built in ~16 months that matches its flagship on inference economics, at one of Nvidia's largest customers, replacing part of the inferencing fleet. **But demand is the offset**: Codex growth is strong enough that "OpenAI will need all the NVIDIA, AMD, TPU, Trainium, Cerebras, and Jalapeño chips they can get." Nvidia's supply-chain dominance remains intact. *"NVIDIA isn't about to rollover. After all, they're not a car."*
	- **The most cynical and most useful line in the article**: *"Regardless of whether Jalapeño is actually deployed at scale, it is clearly a good idea for Nvidia customers to start an ASIC program, spend hundreds of millions on R&D, present at Hot Chips, deploy some stuff, scare Nvidia, get some more money and backstops from Nvidia on the order of billions of \$. **OpenAI wins even if their chip loses.**"* **This is the correct frame for every hyperscaler ASIC announcement from here** — the option value against Nvidia pricing is realized on announcement, independent of silicon success. It is the same off-margin-price-cut mechanism described in [[2026-08-21-ben-thompson-ilb-risk-relocation-commodity-logic]], viewed from the buyer's side.
	- **AMD** — "alarm bells should be going off." OpenAI could own **more than 10% of AMD if it and its partners buy 6 GW of GPUs**, yet **a custom program delivered in 9 months what AMD has not achieved in the 4 years since ChatGPT: outperforming Nvidia GPUs.**
	- **Cerebras — the most quantified competitive threat in the piece.** OpenAI guides **3–5× from MTP** on internal models; applied to the 700 tok/s/user baseline that implies **~2,000–3,500 tok/s/user**, against **Cerebras's claimed 4,000 tok/s/user on CS-4** — "in the ballpark."
		- **The cost comparison is brutal and worth reproducing.** A Cerebras wafer holds just **44 GB of SRAM**, so an FP4 copy of a 1.6T-parameter model like DeepSeek V4 Pro (~800 GB of weights) **spreads across 20 wafers — \$20M+ of capex and about 1 MW of power before the first forward pass.** An **eight-chip Jalapeño node carries ~1.7 TB**, holds the same model with room to spare, costs **less than a single WSE**, and draws **~11 kW.** That is a **~91× power ratio for equivalent model residency.**
		- **The contractual stake**: OpenAI has a **firm obligation for 750 MW of Cerebras compute**, with an **option for an additional 1.25 GW**. **If Jalapeño delivers fast tokens at better throughput and cost, that incremental 1.25 GW may never materialize.** That option is the majority of the Cerebras story.
		- **The structural argument against Cerebras is the one that survives**: past a point, faster tokens stop being worth paying for — end-to-end latency becomes dominated by tool calls and network round trips. **Jalapeño need not match Cerebras token-for-token; it needs to get close enough while being fungible**, which a wafer-scale decode-only part cannot be.
	- **Broadcom, Celestica, Samsung** — direct beneficiaries as ASIC partner, system integrator, and likely HBM4 supplier respectively.
	- **Anthropic, Meta, Microsoft** — **Anthropic is building its own ASIC team, "including some of the very people that worked on Jalapeño,"** which puts its compute suppliers on notice. But **Meta MTIA and Microsoft MAIA have struggled for years and never shown anything close to these numbers.** A program is not a result.
- ## What to watch, and the honest bear case
	- **Production ramps gradually over 2027 with most output at the end of the year** — the shipment chart (Titan 1 / Nexus 1) shows negligible volume through 4Q26 and a step change in 4Q27. **The next goal is 100 MW.** Nothing here is deployed at scale today.
	- **The remaining hurdles are explicitly hardware, not software**: production volume, datacenter deployment and operation, monitoring, resiliency. *"The software is already proven."* **That is the inverse of every previous ASIC program's failure mode**, and it is why this one deserves different priors than MTIA or MAIA.
	- **The bear case, assembled from the article's own caveats**: every number is OpenAI-supplied, at a single 8k/1k shape, on non-frontier models, against a generation-old Nvidia part, without the agentic benchmark SemiAnalysis itself considers decisive — and on **A0 silicon with three months of bring-up and no production deployment.** **Perf/TCO against Rubin is a tie, not a win.**
	- **The falsifiable tests, in order of value**: (1) **AgentX results on long-context multi-turn workloads** — the shape that matters commercially and the one deliberately absent; (2) **prefill throughput**, where Rubin's 2.6× FLOPs advantage should bite and the fungible-pool design is most exposed; (3) whether **B0's claimed 25% perf/W** materializes; (4) whether OpenAI **exercises the incremental 1.25 GW Cerebras option** — the cleanest market-priced verdict on whether Jalapeño delivered.
	- **What to carry forward regardless**: the 22 GB/s/W figure and what it implies about where inference silicon is actually differentiated; the \$1.56/chip/hr TCO at H100 cost with HBM4 bandwidth; the 16-month concept-to-tapeout benchmark now set for every ASIC program; and the "OpenAI wins even if their chip loses" frame for reading the announcements that follow.
