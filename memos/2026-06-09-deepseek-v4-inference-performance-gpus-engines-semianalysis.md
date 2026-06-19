tags:: [[DeepSeek]], [[inference]], [[$NVDA]], [[$AMD]], [[Huawei]], [[GPU]], [[GB300]], [[B200]], [[MI355X]], [[vLLM]], [[SGLang]], [[TensorRT-LLM]], [[CANN]], [[token economics]], [[tokens-per-watt]], [[SemiAnalysis]], [[MoE]]

- ## DeepSeek V4 1.6T — Inference Performance by GPU / Engine / Setup (SemiAnalysis InferenceX)
	- **Source**: SemiAnalysis InferenceX, "DeepSeekV4 1.6T Day 0 to Day 43 Performance Over Time — Huawei, GB300 NVL72, MI355X, B200" (Bryan Shan, Cam Quilici, Kimbo Chen + 4), Jun 9 2026. Open-source tracker: `github.com/SemiAnalysisAI/InferenceX`.
	- **Model under test**: **DeepSeek V4 Pro, 1.6T-param MoE**; native checkpoint = **FP4 MoE + FP8 Attention** mixed quant; **hidden size 7,168** (vs 4,096 for prior DeepSeek / V4 flash). H200 & MI355X used **FP8** non-native on Day 0.
	- **Benchmark**: **Token Throughput per GPU (tok/s/gpu) vs Interactivity (tok/s/user)**, **8K input / 1K output**, FP4/FP8. Tracking **Day 0 (2026-04-24) → Day 43 (2026-06-08)**, **35 dates, 321 configs**. Higher interactivity = faster per-user output but lower per-GPU throughput (the two trade off along a pareto frontier).
	- **One-line takeaway**: Day-0 performance is a weak signal — it's an *engineering starting line*. Over ~6 weeks, the same hardware gained **3×–100×** via kernel/parallelism work; **rack-scale GB300 NVL72 + WideEP** dominates throughput and cost, and only **two stacks (Nvidia CUDA and Huawei CANN) had working Day-0 support** (AMD did not).
- ## Day-0 Stack / Engine Support
  | Stack / engine | Day-0 status on DeepSeek V4 Pro |
  |---|---|
  | **Nvidia CUDA — vLLM & SGLang** | Worked **out of the box** at release (incl. B200/B300 recipes); Dynamo vLLM GB200 disaggregated recipe near Day 0 |
  | **Huawei CANN (Ascend 950DT)** | **First-class Day-0 support**; part of DeepSeek's official API served on Ascend since Day 0 |
  | **Nvidia TensorRT-LLM (TRT)** | **Broken Day 0** — hardcoded `FHC_HIDDEN=4096` vs V4 Pro's 7,168; Nvidia removed the guard (→ corrupted generations), SemiAnalysis fixed via PR (~Day 9) |
  | **AMD ROCm — vLLM / SGLang** | **Did not work well**; only an FP8 WIP SGLang recipe ran, "unusable" at 1–2 tok/s/user; native FP4+FP8 checkpoint broke; distributed inference still broken |
  | **AMD ATOM** | Ran only **conc=1** Day 0 (KV cache pinned to 1 slot); **zero production customers** |
	- Contrast: for **DeepSeek v3/R1 last year, only the CUDA stack worked Day 0** — now two stacks do. "CUDA moat": distributed inferencing tends to be supported near Day 0 for the latest open models.
- ## Day-0 Peak Throughput by SKU + Engine (tok/s/gpu, chart-read)
  | SKU + engine | Precision | Day-0 peak (tok/s/gpu) | Max interactivity reached |
  |---|---|---:|---:|
  | **B300 (vLLM)** | FP4 | **~8,000** | ~70 tok/s/user |
  | **B300 (SGLang)** | FP4 | **~6,000** | ~90 |
  | **GB200 NVL72 (Dynamo vLLM)** | FP4 | **~5,000** | ~72 (highest reach) |
  | **B200 (vLLM)** | FP4 | **~5,000** | ~76 |
  | **B200 (SGLang)** | FP4 | **~2,050** | ~68 |
  | **H200 (vLLM/SGLang)** | FP8 | **~700–1,000** | ~78 |
  | **MI355X (SGLang, FP8)** | FP8 | **~57** @ ~0.75 tok/s/user (**1–2 tok/s/user only — unusable**) | ~2 |
  | **MI355X (ATOM, FP4)** | FP4 | **~3** (conc=1) | ~3 |
	- **GB200 NVL72 Dynamo vLLM** (disaggregated prefill + WideEP, NIXL KV-transfer): SemiAnalysis replicated it to **up to 5× better than a B200 run** at lower-interactivity configs.
- ## Performance-Over-Time Gains (the real story)
  | SKU / setup | Gain | Driver |
  |---|---|---|
  | **MI355X (AMD ROCm/SGLang)** | **>100× throughput, Day 0 → Day 26** | AITER/Triton/TileLang/FlyDSL kernels replacing PyTorch fallbacks; native **FP4 (MXFP4) MoE**; HIP graphs; concurrency sweep → 1,024. By 05/31 **~2.15k peak, beat H200** at low interactivity for the first time |
  | **B300 (SGLang, DeepGEMM MegaMoE)** | **3× iso-interactivity, <1 week** | Grouped FP4 MoE GEMM (experts resident, one mega-dispatch); tuned **EP4 instead of EP8**. ~9k peak |
  | **B300 (SGLang + MTP)** | **>7× iso-interactivity** | **Multi-Token Prediction** (first MTP support, Day 3 from SGLang); helps memory-bound small-batch decode |
  | **B200 (vLLM) — tokens/MW** | **~300k → ~500k tok/s/MW (~1.7×)** @ 50 tok/s/user (Day 0 → Jun 5) | Pure software gain (B200 all-in power fixed at 2.17 kW/GPU): MegaMoE FP4 GEMMs, wider EP, scheduler tuning |
  | **GB300 NVL72 (Dynamo SGLang + MTP)** | **~11k → ~13k peak; interactivity reach to ~240** | **WideEP**: decode topology rewrite EP=8→**EP=16**, concurrency 16,384→**21,504**; W4A4 (MXFP4) MegaMoE |
  | **ATOM (MI355X)** | conc=1 point → full frontier, some points **beating H200** | AITER fix #2916; FP4 experts on fused MoE; batching conc=1→512 |
	- **MTP caveat**: speculative decoding helps memory-bound decode but **hurts at high throughput** (compute-bound large-batch decode — draft-token cost outweighs benefit).
	- **TRT-LLM** (once fixed): superior at **high batch / low interactivity**, falls behind at **high interactivity**; still not out-of-the-box.
- ## Cost per Million Tokens — TCO (Owning · Hyperscaler, @ 40 tok/s/user, MTP)
  | SKU + engine | $ / 1M total tokens | tok/s/gpu |
  |---|---:|---:|
  | **GB300 NVL72 (Dynamo SGLang, MTP)** | **$0.062** | 11,827 |
  | GB300 NVL72 (Dynamo SGLang) | $0.099 | 7,349 |
  | B200 (TRT, MTP) | $0.164 | 3,260 |
  | MI355X (ATOM, MTP) | $0.256 | 1,507 |
  | B300 (TRT, MTP) | $0.308 | 2,141 |
  | B300 (SGLang, MTP) | $0.353 | 1,929 |
  | B200 (SGLang) | $0.523 | 1,033 |
  | MI355X (SGLang, MTP) | $0.619 | 788 |
	- **GB300 NVL72 is the cost leader** — ~**$0.062/M tok** (≈ **10× cheaper** than B200 SGLang at $0.523). The rack-scale **NVL72 single-NVLink-domain** keeps DeepSeek V4's MoE all-to-all on NVLink (not the slower scale-out fabric) and amortizes expert-weight loads across 72 GPUs. GB300 cost/M **output** token hits **$0.156 at 50 tok/s/user**.
	- B200/B300 in **8-GPU NVLink islands over InfiniBand** hit the scale wall earlier; **MI355X sits further back** on scale-up domain size and collective-stack maturity.
- ## Power & TCO Reference (all-in per GPU)
  | SKU | All-in power (kW/GPU) | TCO ($/GPU/hr) |
  |---|---:|---:|
  | H100 | 1.73 | 1.30 |
  | H200 | 1.73 | 1.41 |
  | B200 | 2.17 | 1.95 |
  | B300 | 2.17 | 2.34 |
  | GB200 | 2.10 | 2.21 |
  | GB300 | 2.10 | 2.65 |
  | MI300X | 1.79 | 1.12 |
  | MI325X | 2.18 | 1.28 |
  | MI355X | **2.65** | 1.48 |
	- **Tokens per all-in utility MW** is SemiAnalysis's preferred fleet-ROI metric (captures PUE/datacenter overhead). Because power per GPU is fixed, throughput gains drop straight through to power efficiency. (TCO source: SemiAnalysis Market Aug-2025 Pricing Surveys & AI Cloud TCO Model.)
- ## Huawei Ascend 950DT (the second Day-0 stack)
	- **CANN** (Compute Architecture for Neural Networks) open-sourced Aug 2025 to chip at Nvidia's dominance inside China (US CUDA export restrictions). DeepSeek V4 was the **first major open model with first-class Day-0 Ascend support**; architecture **co-designed in part for Ascend inference**.
	- **Ascend 950** (codename **"David"** vs Nvidia "Goliath"): **950PR** (Prefill + Recommendation; lower cost, better cost-perf) vs **950DT** (Decode + Training; higher memory bandwidth/perf). Same die, **dual-die UMA**; **AIC** (matrix/tensor cube core, 16×16×16 FP16) + **AIV** (vector core); dedicated **CCU** comms engine (remote-read+reduce+local-write) avoiding the old AICore→AICPU→SDMA path.
	- Decode profile: **16-rank DP/EP**; **MC²** merged compute-communication operators (`MoeDistributeDispatchV2/CombineV2`); value-dependent scheduler + LightningIndexer pushed onto the on-device **AI CPU** (ARM64). MTP benchmarked as **time-per-decode-step** (user multiplies by their acceptance length).
- ## Monetization Context — DeepSeek V4 Pro API Pricing
	- DeepSeek made a **"75% off, now permanent"** cut → **officially 1/4 of original price**:
		- Input (cache hit): **$0.003625** (was $0.0145) per M tok
		- Input (cache miss): **$0.435** (was $1.74)
		- Output: **$0.87** (was $3.48)
	- Cross-check vs InferenceX TCO: GB300 owning-cost ~\$0.062/M total tokens vs **$0.87/M output** API price → large gross margin headroom for the best-optimized rack-scale serving, and a brutal squeeze for sub-scale (MI355X SGLang $0.619/M) or older setups.
- ## Investment Implications
	- **Day-0 benchmarks materially understate a chip's value** — software maturity moves performance **3×–100×** in weeks. Snapshot comparisons (esp. AMD-vs-Nvidia "Day 0") are misleading; track the *frontier over time* ([[2026-05-20-deepseek-r1-token-throughput-per-gpu-vs-interactivity]]).
	- **Rack-scale (NVL72) + WideEP is the structural moat** for trillion-param MoE serving: GB300 NVL72 is both the **throughput and cost-per-token leader** (~$0.062/M, ~10× cheaper than 8-GPU-island B200). Bullish for GB200/GB300 NVL72 demand and the NVLink/scale-up domain ([[2026-06-09-whale-rock-sacerdote-ai-stack-s-curve-framework]], [[2026-06-07-ai-inference-hardware-semi-investment-memo]]).
	- **CUDA's ecosystem lead is the durable edge** — vLLM/SGLang Day-0 support + the speed of community kernel work; TRT-LLM and AMD lag at launch. **AMD is closing fast on single-node** (MI355X >100× in 26 days, beat H200 at low interactivity) but distributed/ROCm vLLM still broken and **ATOM has zero production customers** — software, not silicon, is AMD's gating issue.
	- **Huawei is the credible China alternative**: only the 2nd stack with Day-0 DeepSeek V4 support; CANN + Ascend 950 co-design is a genuine sovereignty hedge inside China (export-control read-through).
	- **Token economics**: optimized GB300 serving (~$0.062/M total) vs DeepSeek's $0.87/M output API price shows where inference margin concentrates — and why the permanent 75% price cut pressures less-optimized providers. Ties to the broader token-demand/efficiency theses ([[2026-06-11-ai-subscription-margin-by-utilization]], [[2026-06-05-goldman-agentic-ai-token-demand-24x-by-2030]]).
	- **Caveat**: per-GPU throughput figures for disaggregated configs (Dynamo SGLang/TRT) are computed per decode-GPU or per prefill-GPU, **not per total GPU** — not apples-to-apples with aggregated configs. Many SKU values are chart-read approximations.