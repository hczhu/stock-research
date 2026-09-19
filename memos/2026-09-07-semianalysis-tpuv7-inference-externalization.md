- tags:: [[$GOOGL]], [[$NVDA]], [[TPU]], [[ASIC]], [[inference]], [[AI infrastructure]], [[TCO]], [[agents]]

- ## TPUv7 Inference Externalization - Google Takes Aim at Nvidia's Software Moat
	- **Source**: Alec Ibarra, Cam Quilici, Bryan Shan, and four others, SemiAnalysis, "TPU Inference Externalization Full Steam Ahead - InferenceX", September 7, 2026; user-provided PDF.
	- **Thesis**: Ironwood's first third-party inference results suggest Google's TPU advantage can travel beyond internal workloads: TPUv7 offers competitive raw performance and lower modeled cost than FP8 Blackwell across much of the measured curve. The larger strategic change is TorchTPU making TPUs native to PyTorch, vLLM, and SGLang. If Google converts this preview into broad model coverage and production-grade disaggregated serving, TPU becomes a credible external merchant accelerator and weakens CUDA's distribution advantage; the current evidence remains narrow, model-specific, and dependent on SemiAnalysis TCO assumptions.

- ## InferenceX Preview Results
	- The benchmark uses **Qwen3.5-397B in FP8**, an 8k-input / 1k-output workload, aggregated serving, and no multi-token prediction. TPUv7 Ironwood runs through a preview native TorchTPU vLLM stack and is compared with B200 and B300 running SGLang.
	- | Operating point | TPUv7 Ironwood | B200 | B300 | TPU read-through |
	  |---|---:|---:|---:|---|
	  | 100 output tok/s/user, external TCO | \$0.181/M total tokens | \$0.222/M | \$0.276/M | TPU cost is 19% below B200 and 34% below B300 |
	  | 20 tok/s/user, throughput | 9,364 tok/s/chip | 8,903 | About 8,900 | TPU delivers about 5% more raw throughput |
	  | 20 tok/s/user, external performance per dollar | Baseline | 50.4% lower | 96.0% lower | Maximum headline advantage occurs at a high-throughput point |
	  | 20-second median response time | \$0.098/M total tokens | \$0.106/M | \$0.132/M | TPU cost is 8% below B200 and 25% below B300 |
	- At Google's modeled internal cost of approximately **\$1.03 per TPU chip-hour**, Ironwood's performance-per-dollar advantage at concurrency 256 rises to **76.7% over B200** and **130.2% over B300**.
	- That operating point carries worse first-token latency: mean TTFT is **5.41 seconds on TPU**, versus **3.75 seconds on B200** and **2.40 seconds on B300**. The report's 50-96% external advantage is therefore not representative of every service-level target.
	- B200 still wins part of the cost-latency curve around a 30-second median response time. Ironwood regains the modeled cost lead at longer response times and remains below B300 across the overlapping range shown.

- ## Benchmark Boundaries Matter
	- The clean comparison is **FP8 versus FP8** because Ironwood lacks native FP4. Nvidia retains an advantage where FP4 quality is acceptable; TPUv8i is expected to add native FP4 and permit an FP4-to-FP4 comparison with Rubin.
	- The external TPU stack does not yet have optimized prefill-decode disaggregation or speculative decoding. Against disaggregated GB300 NVL72, aggregated TPUv7 trails by about **30% on performance per dollar in the middle of the latency curve**, although it is competitive at the low- and high-latency ends shown.
	- SemiAnalysis expects TPU disaggregation to close that gap, but this is a forecast rather than a measured result. The preview also covers one model and one request shape, so it does not establish broad production superiority.
	- The cost curves rely on SemiAnalysis's estimated bill of materials and TCO. Its model places external TPUv7 at **\$1.21 per chip-hour**, B200 at **\$1.73**, B300 at **\$2.26**, and Google's internal TPU cost near **\$1.02-\$1.03**; capex represents 66.5% of modeled internal TPU TCO.

- ## TorchTPU Lowers the Adoption Tax
	- TPUv7 is the first TPU generation Google is positioning for external inference through both outright sales and Google Cloud rental. SemiAnalysis says Anthropic has committed to more than **1M TPUs**, including over 400,000 direct purchases and over 600,000 rented through GCP, mainly for training but also for inference.
	- The existing TorchAX path translates PyTorch operations into JAX, adding framework boundaries and integration friction. **TorchTPU exposes an ordinary `torch.Tensor` on `device="tpu"`**, routes PyTorch operations directly to the TPU backend, and uses `torch.compile`, StableHLO, and XLA for compiled execution.
	- The user-facing stack becomes PyTorch-native, but performance remains hardware-specific: XLA still compiles the executable and Pallas/JAX-backed custom kernels remain necessary. This is compatibility convergence, not hardware abstraction eliminating optimization work.
	- Inferact, RadixArk, Red Hat, Google, and the vLLM/SGLang communities are building native backends. At publication, TorchTPU was in private beta with open sourcing targeted for mid-October 2026.
	- Qwen3.5-397B is the initial bring-up model. The planned sequence includes Kimi K3, GLM5.3, and Gemma4; the strategic threshold is whether TPU can move from bespoke model ports toward near-day-zero support in vLLM and SGLang.

- ## Software Headroom Is Still Large
	- Moving communication work from TensorCore to SparseCore and overlapping intra-chip and inter-chip reductions improved measured 8k/1k throughput by **4.1-14.2%** across concurrency 64-512 and lifted 1k/8k throughput by **26.1%** at concurrency 512.
	- Compact recurrent-state allocation reclaimed about **76 GiB of HBM**, expanded the attention block pool by **71%**, and improved 1k/8k output throughput by **18%** at concurrency 64.
	- A sequence-on-lane KV layout doubled usable pages from **5,141 to 10,283**. At concurrency 128 on 8k/1k, the additional capacity raised throughput **16.5%** and reduced median TTFT **95%** by eliminating waits for KV-cache space.
	- Splitting paged-attention fetch and compute block sizes raised decode throughput from **64.9k to 96.3k tokens/s**, a 49% kernel result on Qwen3-0.6B. These gains show substantial software runway, but many are workload- or kernel-specific and should not be added together.

- ## Hardware Co-Design Creates Both Advantage and Friction
	- Ironwood uses two independent compute dies per chip, with two TensorCores and four SparseCores. It has about **6x the HBM capacity of Trillium** and is Google's first TPU with native FP8 hardware.
	- The MXU widened from 128x128 on older TPUs to **256x256**, providing 4x as many multiply-accumulate cells per cycle. Poorly matched model dimensions waste that capacity: a 128-wide attention head caps the relevant matmuls at 50% utilization, while a 64-wide head caps them at 25%.
	- This makes external model support uneven. Models aligned to TPU tile geometry may take weeks to optimize; architectures with awkward attention heads, KV-head counts, or expert widths can require new kernels before reaching parity. GPUs tolerate a wider range of shapes with less penalty.
	- Ironwood's 3D-torus ICI scales to a **9,216-chip superpod with 42.5 FP8 exaflops**. The report says upcoming results show the torus can beat single-hop NVSwitch latency for some small expert-parallel messages, but those measurements are not included here.

- ## TPUv8i Extends the Inference-Specific Bet
	- Google is separating TPUv8 into training-focused **8t** and inference-focused **8i** designs for the first time. TPUv8i replaces the 3D torus with the flatter Boardfly fabric.
	- At roughly 1,024-1,152 chips, Boardfly reduces network diameter from about **16 hops to 7**, more than a 50% reduction. TPUv8i also provides **19.2 Tb/s of ICI bandwidth**, double the prior generation, and **384 MB of on-chip SRAM**, triple the prior generation, targeting lower collective latency and more on-chip KV cache for reasoning and agentic workloads.
	- The remaining externalization roadmap is as important as the silicon: speculative decoding, production prefill-decode disaggregation, TPU-Sync zero-copy KV transfer, Mooncake-based DRAM/NVMe pooling, hybrid-model prefix caching, and AgentX validation on long-context multi-turn traces.

- ## Competitive Read-Through
	- **[[$GOOGL]]**: External TPU sales and rentals can monetize silicon economics directly, improve GCP inference margins, and turn a captive accelerator into a platform. Native participation in PyTorch, vLLM, and SGLang matters more for adoption than another internal Gemini benchmark.
	- **[[$NVDA]]**: The near-term threat is not that Ironwood wins every raw-performance point; it is that a second ecosystem can offer acceptable open-model support at structurally lower acquisition cost. Nvidia retains FP4, mature disaggregation, broad day-zero model coverage, and fungibility across workloads.
	- The decisive proof point is broad, public, reproducible performance after TorchTPU open-sources and after both systems use FP4, speculative decoding, disaggregation, and agentic request traces. Until then, the report demonstrates credible direction and meaningful software progress rather than a completed erosion of CUDA's moat.
