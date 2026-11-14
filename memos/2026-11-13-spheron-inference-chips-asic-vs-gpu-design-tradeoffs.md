tags:: [[$NVDA]], [[$AMZN]], [[$GOOGL]], [[$MSFT]], [[$META]], [[$AMD]], [[$QCOM]], [[Etched]], [[Groq]], [[Cerebras]], [[Tenstorrent]], [[Trainium]], [[TPU]], [[Maia]], [[MTIA]], [[ASIC]], [[GPU]], [[custom-silicon]], [[inference]], [[HBM]], [[SRAM]], [[CUDA]], [[GPU-pricing]], [[Spheron]], [[semiconductor]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-13
file-updated-at:: 2026-11-13

- ## Inference chips in 2026: how far each design gives up programmability, and what it gets back
	- **Source**: two Spheron blog posts by Mitrasish (Spheron co-founder and CTO), both last updated Oct 19, 2026, with rental prices quoted as of Nov 14, 2026 (user-provided PDFs):
		- "Etched Sohu vs NVIDIA: Transformer ASIC vs GPU (2026)," first published May 1, 2026.
		- "Hyperscaler Custom AI Chips in 2026: Trainium 3, Google TPU, Maia 200, and Meta MTIA vs NVIDIA GPU," first published Jun 22, 2026.
	- **Bias**: Spheron rents out NVIDIA GPUs, and both posts end by recommending its GPU cloud. Read the "rent GPUs instead" conclusions as marketing. The chip specs and the design trade-offs are the useful part.
	- **Thesis**: every inference chip trades flexibility for efficiency. The choices run from programmable GPUs, through captive hyperscaler ASICs and SRAM dataflow chips, to hardwired transformer chips and model-in-silicon chips. The more a chip hardwires, the more it depends on model architectures holding still. MoE, multimodal and diffusion models are the current evidence that they don't. HBM bandwidth and capacity are the shared constraint across almost every design.
	- Related: [[2026-07-10-etched-inference-chip-rack-architecture-podcast]], [[2026-09-07-semianalysis-tpuv7-inference-externalization]], [[2026-08-09-semianalysis-tilert-inferencex-gpu-vs-dataflow-asic]], [[2026-05-21-toms-hardware-custom-ai-asic-state-of-play]], [[2026-07-20-google-frozen-v2-gemini-in-silicon-inference-chip]].
- ## Technological directions and their trade-offs
	- Ordered from most flexible to most specialized:
	- | Direction | Chips | Bet | What it gives up |
	  |---|---|---|---|
	  | **Programmable GPU** | NVIDIA H100, H200, B200, B300; AMD (ROCm) | Any model, plus training, on one stack. The CUDA software ecosystem (vLLM, SGLang, TensorRT-LLM, FlashAttention) is the advantage | Peak efficiency on any one workload. Spheron frames CUDA less as NVIDIA's moat than as a migration cost for anyone leaving |
	  | **Merchant alternative accelerators** | Tenstorrent (open-source TT-Metal, MIT license), Intel Gaudi 3, SambaNova SN40L (RDU, a reconfigurable dataflow unit), Rebellions ATOM (backed by the Korean government) | Selling to anyone, with an open or portable software hedge | Scale and ecosystem; each needs its own SDK |
	  | **Captive hyperscaler ASIC** | AWS Trainium 3, Google TPU Ironwood, Microsoft Maia 200, Meta MTIA, OpenAI Jalapeño | Tuned to the owner's workloads (Gemini API at large batches, Copilot and OpenAI traffic, Meta ranking) on 3nm | The external market. Each has its own stack (Neuron SDK, JAX/XLA, Maia SDK) and only runs in its owner's cloud. "The lock-in is not incidental. It is the product." |
	  | **Memory-capacity bet** | Qualcomm AI200 and AI250 (merchant) | **768GB of LPDDR5X per card**: fit large models and long contexts on fewer cards | Raw FLOPS, and bandwidth per GB (*my note*: LPDDR is much slower than HBM) |
	  | **SRAM dataflow** | Groq 3 LPU (licensed to NVIDIA for \$20bn), Cerebras WSE-3 | **500MB on-chip SRAM at 150 TB/s per chip** for very fast decode, with a deterministic compiler | Capacity: limited context windows and many chips per model. Only partial MoE support |
	  | **Fixed-function transformer ASIC** | Etched Sohu | Attention hardwired as circuits, with no kernel-launch, memory-allocation or scheduler overhead | All programmability. Spheron says it can't run MoE, vision encoders, diffusion, SSMs or training. A change in model architecture strands the hardware |
	  | **Model-in-silicon** | AMD's Taalas HC1 (acquired Aug 2026); Google "Frozen v2" | A specific model's weights fabricated into the chip | The ability to change the model at all |
- ## Which workloads each design can run (Spheron)
	- | Workload | Etched Sohu | Groq 3 LPU | H100 / B200 |
	  |---|---|---|---|
	  | Dense transformer inference | Yes | Yes | Yes |
	  | MoE inference (DeepSeek V4, Qwen3-235B-A22B) | No | Partial | Yes |
	  | Multimodal (vision encoder plus language model) | No | No | Yes |
	  | Diffusion image and video generation | No | No | Yes |
	  | SSM / Mamba | No | No | Yes |
	  | Training and fine-tuning | No | No | Yes |
	  | Risk from future architectures | High | Medium | Low |
	- **Spheron's counter-evidence**: DeepSeek V4 (a 671B MoE) was Hugging Face's most downloaded model in early 2026, and Qwen3-235B-A22B is also MoE, so "a significant fraction of current production inference workloads cannot run on Sohu at all." Diffusion language models are another compute pattern a transformer-only chip can't serve.
- ## Memory is the axis everyone competes on
	- | Chip | Maker | Memory | Bandwidth | Process | Can outsiders rent it? | Software stack |
	  |---|---|---|---|---|---|---|
	  | Trainium 3 | AWS | 144GB HBM3E | 4.9 TB/s | 3nm | AWS EC2 Trn3 only | Neuron SDK |
	  | TPU Ironwood (v7) | Google | 192GB HBM3E | 7.37 TB/s | 3nm (est.) | GCP only | JAX/XLA |
	  | Maia 200 | Microsoft | 216GB HBM3E | 7 TB/s | TSMC 3nm | No | Maia SDK (internal) |
	  | MTIA 500 (roadmap) | Meta | Not published | Not published | 3nm (roadmap) | No | Internal only |
	  | Etched Sohu | Etched | 144GB HBM3E | About 1.8× H100, so about 6 TB/s | Not given | Not yet | Etched compiler |
	  | Groq 3 LPU | NVIDIA (licensed) | 500MB SRAM | 150 TB/s | Not given | Early access | Groq compiler, via Dynamo |
	  | Qualcomm AI200/AI250 | Qualcomm | 768GB LPDDR5X per card | Not given | Not given | Sold as racks | Not given |
	  | B300 SXM6 | NVIDIA | 288GB HBM3E | 8 TB/s | TSMC 4nm | GPU clouds | CUDA |
	  | H200 SXM5 | NVIDIA | 141GB HBM3E | 4.8 TB/s | TSMC 4nm | GPU clouds | CUDA |
	  | H100 SXM5 | NVIDIA | 80GB HBM3 | 3.35 TB/s | TSMC 4nm | GPU clouds | CUDA |
	- **Other confirmed specs**:
		- **Ironwood**: 4,614 FP8 TFLOPS and 9.6 Tb/s of chip-to-chip interconnect. Generally available since late 2025, and positioned for inference more than training.
		- **Maia 200**: native FP8 and FP4 tensor cores, about 750W, with a datasheet published Jan 2026.
		- **Trainium 3**: multi-node UltraServers connected over NeuronLink.
	- **Sohu's edge is not a new memory type.** It uses the same HBM3E as GPUs; any advantage comes from hardwiring attention. Groq takes the opposite route, swapping HBM capacity for SRAM bandwidth.
- ## Etched Sohu: claims vs evidence
	- | Item | Data |
	  |---|---|
	  | Funding | About **\$800M** over four rounds, including a reported \$500M round at a **\$5B** valuation |
	  | Signed customer contracts | Over **\$1B** |
	  | Status | Came out of stealth Jun 30, 2026 with working A0 silicon and an 8-chip rack. First racks were due summer 2026 |
	  | Throughput claim | **500,000 tok/s** on Llama 70B per 8-chip server, so about 62,500 tok/s per chip. Spheron describes it as measured at or near batch 1 |
	  | Missing | No independent benchmarks, no public pricing, no way to rent one |
	- **Spheron's GPU baseline and cost per token** (Llama 70B on vLLM, prices as of Aug 2, 2026):
		- | Chip | On-demand \$/hr | Tok/s at batch 1 | Tok/s at batch 32 | Tok/s at batch 256 | Cost per 1M tokens at batch 32 |
		  |---|---|---|---|---|---|
		  | H100 SXM5 | \$3.38 | ~700 | ~5,000 | ~45,000 | ~\$0.188 |
		  | B200 SXM6 | \$7.50 | ~1,200 | ~9,000 | ~80,000 | ~\$0.231 |
		  | B300 SXM6 | \$10.21 | — | ~16,000 (est.) | — | ~\$0.177 (est.) |
		  | Sohu (per chip) | Not available | ~62,500 (claimed) | Not published | Not published | Can't be calculated |
	- **When the ASIC bet pays off**, according to Spheron, all three conditions must hold:
		- cost per token clearly below GPU cloud at your batch profile
		- the toolchain rewrite costs less than the savings
		- the model architecture stays stable long enough to pay back both
	- None of the three can be verified for Sohu today.
- ## Hyperscaler ASICs: real, but captive
	- **The demand shift**: inference is "roughly two-thirds of AI compute spend," and 60–80% of AI GPU spend for teams in production. Hyperscalers run even more inference, from Copilot, Gemini API, Alexa and recommendations. At their scale, "a 30% efficiency gain on inference silicon pays for itself in months."
	- **The projection**: NVIDIA's inference share falls from **90% to about 20–30% by 2028** (no source named). Spheron argues the shift happens mostly inside the hyperscalers' own workloads.
	- **Chip by chip**:
		- **Trainium 3** matches or beats H100 on throughput per dollar for batch-heavy dense transformers inside AWS. AWS's Trn2 figures for Llama 2 70B were competitive with H100.
		- **TPU Ironwood** serves Gemini API traffic at very large batch sizes.
		- **Maia 200** runs Copilot and OpenAI API traffic, with no VM type that customers can provision.
		- **MTIA**: the 300 is in production for ranking and recommendation, the 400 is in testing, and the 450 and 500 are roadmap only. Meta's benchmarks cover recommendation models, not LLMs.
	- **Porting cost**:
		- Moving from vLLM to Neuron takes 2–6 weeks, plus extra time for unsupported models. Neuron updates also lag vLLM releases.
		- Moving to TPU and JAX/MaxText takes 2–8 weeks.
		- Either way the ported stack loses portability to other clouds. Neither Trainium nor TPU has a spot-pricing tier.
- ## Rental prices: Blackwell up, H100 down (Spheron on-demand)
	- | Chip | Aug 2, 2026 | Nov 14, 2026 | Change |
	  |---|---|---|---|
	  | H100 SXM5 | \$3.38/hr | \$2.98/hr | −12% |
	  | B200 SXM6 | \$7.50/hr | \$10.17/hr | +36% |
	  | B200 SXM6 (spot) | \$2.74/hr | \$5.22/hr | +91% |
	  | B300 SXM6 | \$10.21/hr | \$11.47/hr | +12% |
	- H200 SXM5 was \$4.79/hr on Nov 14. *My note*: at the November B200 rate, cost per 1M tokens at batch 32 rises to about \$0.31 (my math, using Spheron's 9,000 tok/s).
- ## My notes
	- **The throughput figures don't fit memory-bandwidth limits.** At batch 1, every token has to read all the weights. Llama 70B is about 70GB in FP8, so an H100 at 3.35 TB/s tops out near **50 tok/s**, not 700.
		- An 8-chip Sohu server at about 6 TB/s per chip tops out near **700 tok/s** at batch 1, not 500,000.
		- So Etched's figure must be total throughput at a large batch, not batch-1 speed. *My math, assuming FP8 weights split evenly across chips.*
		- On Spheron's own batch-256 GPU estimates, Sohu's claimed 62,500 tok/s per chip is about **1.4× an H100 and about 0.8× a B200**. Sohu's edge at matched conditions may be small or absent until independent benchmarks exist.
	- **Spheron's MoE verdict may be dated.** Etched's founders described MoE and dynamic routing across chips as directions their rack design targets ([[2026-07-10-etched-inference-chip-rack-architecture-podcast]]). The two sources also disagree on Etched's founding year (2022 here, 2023 in the interview).
	- **For $NVDA, the captive share is the number that matters.** Spheron calls hyperscaler ASICs irrelevant to outside teams. But hyperscalers are about half of NVIDIA's revenue, and the Economist cites custom chips at about 40% of the AI processor market, heading to about 50% ([[2026-09-03-economist-nvidia-central-bank-of-ai-vendor-financing]]).
		- A fall from 90% to 20–30% inside hyperscaler inference would be a large revenue risk even if the GPU rental market is untouched. TrendForce's shipment data (in-house ASIC servers +44.6% vs GPU servers +16.1% in 2026) points the same way ([[2026-05-21-toms-hardware-custom-ai-asic-state-of-play]]).
	- **"Captive" is already eroding for TPU.** Spheron says vLLM has no TPU port. SemiAnalysis tested Ironwood on a preview TorchTPU vLLM stack ([[2026-09-07-semianalysis-tpuv7-inference-externalization]]). Google also sells TPUs to outside customers with repurchase guarantees ([[2026-10-29-google-tpu-repurchase-guarantees]]), and an expert sized external TPU revenue at about \$104B by 2028 ([[2026-10-26-expert-call-nvidia-hyperscaler-concentration-external-tpu-amd-v10]]). Of the four hyperscaler chips, TPU is the most direct competitor to NVIDIA's merchant business.
	- **NVIDIA is absorbing specialization instead of fighting it.** The \$20bn Groq license puts an SRAM decode chip inside NVIDIA's Dynamo disaggregated serving. And TileRT shows a software "speed tier" on stock B200s ([[2026-08-09-semianalysis-tilert-inferencex-gpu-vs-dataflow-asic]]).
		- The likely pattern is heterogeneous racks under NVIDIA's software, with specialized chips handling decode. That limits how much single-purpose ASICs can take.
	- **HBM wins in nearly every direction.** Trainium 3, Ironwood, Maia 200, Sohu and every NVIDIA part run on HBM3E. Only Groq (SRAM) and Qualcomm (LPDDR5X) avoid it, and both pay in capacity or bandwidth.
		- The bandwidth range runs from 4.9 TB/s (Trainium 3) to 8 TB/s (B300) per chip. Ironwood and Maia 200 are already at 7–7.4 TB/s, close to B300, on 3nm against NVIDIA's 4nm.
	- **Blackwell rental prices rising while H100 prices fall** is a demand signal. Frontier-class capacity is getting scarcer even as older GPUs depreciate, which supports both the new-generation upgrade cycle and the depreciation debate in the Economist memo.
