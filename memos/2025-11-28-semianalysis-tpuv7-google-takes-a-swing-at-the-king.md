tags:: [[$GOOGL]], [[$NVDA]], [[$AVGO]], [[Anthropic]], [[TPU]], [[ASIC]], [[TCO]], [[neoclouds]], [[guarantees]], [[OCS]], [[optics]], [[$WULF]], [[$CIFR]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## TPUv7: Google Takes a Swing at the King
	- **Source**: Dylan Patel, Myron Xie, Daniel Nishball and nine others, SemiAnalysis, ["TPUv7: Google Takes a Swing at the King"](https://newsletter.semianalysis.com/p/tpuv7-google-takes-a-swing-at-the), subtitle "Potential End of the CUDA Moat?, Anthropic's 1GW+ TPU Purchase…", November 28, 2025. Only the free portion was read. The paywall starts at "What does this mean for Nvidia?", so the Nvidia implications and the TPUv8 vs. Vera Rubin roadmap comparison aren't covered here.
	- **Thesis (SemiAnalysis's view)**: Google is now selling TPUs externally, and its TPU stack is a credible challenger to Nvidia because "systems matter more than microarchitecture." Ironwood is "a strong chip inside an excellent system." It trails GB200 on paper by about 10%, but its all-in cost is far lower, and good kernel engineers can reach higher realized utilization on it. The remaining gap is software: Google should open-source XLA:TPU, its runtime and MegaScale.
	- Later follow-up from the same firm: [[2026-09-07-semianalysis-tpuv7-inference-externalization]]. Related: [[Google-GOOGL-thesis]], [[2026-06-20-google-tpu-v2-ironwood-architecture-hbm-asic-trends]], [[2026-10-29-google-tpu-repurchase-guarantees]] and [[2026-09-11-nvidia-backstop-universe-credit-support]].
- ## The Anthropic Deal and the Externalization Push
	- **Size**: Anthropic's TPU demand is "at least 1 million TPUs," more than **1GW**. Meta was flagged as a TPU customer on Nov 7.
	- | Phase | Volume | Route | Value |
	  | --- | --- | --- | --- |
	  | 1 | **400k TPUv7 Ironwood** | Sold directly by **Broadcom** to Anthropic as finished racks; Anthropic is Broadcom's fourth referenced XPU customer | ~**\$10B** |
	  | 2 | **600k TPUv7** | Rented through GCP | ~**\$42B** of RPO, most of GCP's **\$49B** Q3 backlog increase |
	- **Partners**: Fluidstack handles on-site setup and operations. TeraWulf (WULF) and Cipher Mining (CIFR) supply data center infrastructure.
	- **Google's investment terms in Anthropic**: no voting rights and a **15% cap** on ownership.
	- **Credit backstop**: Google's constraint is power, and its Master Services Agreements can take up to three years to sign. Its workaround is an off-balance-sheet "IOU" backstopping Fluidstack's data center rent.
- ## How Google Reshaped the Neocloud Market
	- **Financing mismatch**: GPU clusters have a **4–5 year** economic life, but data center leases run **15+ years** with roughly an **8-year** payback. SemiAnalysis says a hyperscaler backstop closes that gap.
	- **Who hosts TPUs**: Nvidia-backed neoclouds (CoreWeave, Nebius, Crusoe, Together, Lambda, Firmus, Nscale) have incentives to avoid TPUs. That leaves an opening for crypto miners and Fluidstack.
	- **Pricing leverage**: "OpenAI hasn't even deployed TPUs yet and they've already saved ~30% on their entire lab wide NVIDIA fleet." Nvidia's public response was to tell people to "keep calm and carry on."
- ## Ironwood vs. Blackwell: Specs and TCO
	- **Specs**: Ironwood has **8-Hi HBM3E**, matching GB200's capacity but below GB300's 288GB of 12-Hi HBM3E. It is about **10% short** of GB200 on peak FLOPs and memory bandwidth, and arrived roughly a year after Blackwell. The predecessor, Trillium (TPUv6), doubled peak FLOPs by moving from 128×128 to 256×256 systolic arrays, but had only 2 HBM3 stacks.
	- | TCO comparison (SemiAnalysis estimates) | Ironwood advantage |
	  | --- | --- |
	  | Google's all-in TCO per chip (3D torus) vs. a GB200 server | ~**44% lower** |
	  | External customer TCO per hour vs. GB200 | Up to ~**30% lower** |
	  | External customer TCO per hour vs. GB300 | Up to ~**41% lower** |
	  | Anthropic's cost per effective PFLOP vs. GB300 NVL72, at 40% MFU | ~**52% lower** |
	  | Cost per effective training FLOP, at 40% MFU | ~**62% lower** |
	- **Anthropic's price**: estimated at about **\$1.60 per TPU-hour** from GCP. Break-even vs. GB300 is about **19% MFU**. If GB300 runs at 30% MFU, the TPU breaks even near **15%** MFU.
- ## Why Anthropic Is Betting on TPUs
	- **Realized utilization**: the training rule of thumb is about 30% utilization. Peak-test GEMM utilization is about 80% on Hopper, in the 70s on Blackwell and in the 50s–60s on AMD MI300. SemiAnalysis says "TPUs can reach higher realized Model FLOP Utilization (MFU) than Blackwell," because Anthropic's engineers write their own kernels.
	- **Multi-hardware training**: Claude Opus 4.5 and Gemini 3 run most training and inference on Google TPUs and Amazon Trainium. Anthropic trained Sonnet and Opus 4.5 on multiple hardware types.
	- **Opus 4.5 economics**: a ~**67%** API price cut. It needs 76% fewer tokens to match Sonnet's best score and 45% fewer to beat it by 4 points. Sonnet is over 90% of Anthropic's token mix.
	- **Google's margins**: "Google can still eke out far superior margins and returns" than commoditized GPU leasing deals, even with "sweetheart pricing" for a flagship customer. SemiAnalysis puts Nvidia's markup at roughly **4×** (~75% gross margin). Broadcom takes a significant share of the TPU BOM. Microsoft's struggling ASIC program leaves it with "more mediocre" leasing returns.
- ## System and Network Architecture
	- **Rack**: 16 TPU trays plus 16 host CPU trays (liquid-cooled, 1:1) or 8 (air-cooled, 2:1). Each tray holds 4 chip packages. Google has run liquid-cooled TPU racks since TPUv3 in 2018.
	- **ICI scale-up**: the building block is a **4×4×4 3D torus of 64 TPUs**. Each TPU links to 6 neighbors, using DAC copper or optics depending on its position in the cube. That averages about **1.5 800G optical transceivers per TPU**.
	- **Optical circuit switches (OCS)**: OCSs route light without electrical conversion, so they are lower-latency and lower-power than packet switches. A CWDM8 FR transceiver with an optical circulator puts 800G on a single fiber strand.
	- **Pod size**: up to **9,216 TPUs** (144 cubes, 13,824 ports, 48 144×144 OCSs), versus 64–72 GPU scale-up domains for merchant accelerators. Google currently offers slices from 4 to 2,048 TPUs. Very large slices are less useful because failures cut slice availability. OCS reconfiguration allows topologies beyond multiples of 64 and needs fewer switches and ports, which offsets the cost of FR optics.
	- **Data center network (DCN)**: scales to an estimated **147,456 TPUs**, 16 ICI pods across 4 aggregation blocks, using 256 OCSs in 32 racks.
- ## Software Strategy
	- **PyTorch and vLLM**: Google is building native PyTorch support for TPUs, announced in October, plus TPU backends for vLLM and SGLang. vLLM contributions rose from March, and the tpu-inference repo was created in May. Meta's earlier PyTorch/XLA contracts (2020–2023) were cancelled in 2023. Google's "all-fused MoE" kernel reportedly delivers a **3–4×** speedup.
	- **Benchmarks**: SemiAnalysis disputes a benchmark showing TPUv6e with 5× worse performance per dollar than Nvidia. The benchmark used Artificial Analysis's **\$2.7/hr/chip** list price, which SemiAnalysis says no major customer pays.
	- **Missing piece**: the XLA compiler, runtime, networking libraries and MegaScale multi-pod code aren't open source. "Google should open source it and the increased user adoption will outweigh all the software IP they will make public."
