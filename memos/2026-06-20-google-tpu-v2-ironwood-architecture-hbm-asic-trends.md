- tags:: [[AI-ASIC]], [[TPU]], [[Google]], [[HBM]], [[DRAM]], [[semiconductor]], [[AI-compute]], [[datacenter]], [[training]], [[memory-bandwidth]]

- **Source**: Jouppi, Lakshmanamurthy, Young, Patterson (Google LLC) — "Google's Training Supercomputers from TPU v2 to Ironwood: Architectural Stability, Scale, Resilience, Power Efficiency, and Sustainability Across Five Generations." To appear in IEEE Micro, Jul/Aug 2026.

- ## Headline Scaling Summary (TPU v2 → Ironwood, 2017–2025)

	- **Terminology**: A **node** = one TPU chip (the physical silicon die with its attached HBM stacks). A **pod** = the full supercomputer formed by connecting many nodes over a high-speed custom interconnect (ICI) in a 3D Torus topology. One pod is what Google calls the training unit: all nodes share a single flat address space across their HBM, so the pod-level HBM is directly addressable as one giant memory pool. Each CPU host connects 4 TPU nodes; an Ironwood pod of 9,216 nodes therefore has 2,304 CPU hosts. The pod is the unit of training job scheduling — a "slice" is a subset of the pod (e.g., 64, 128, 2,048 chips) allocated to a single job.

	- | Dimension | Change over 8 years |
	  |---|---|
	  | HBM capacity per node | **~10x** (16 GiB → 192 GiB) |
	  | HBM bandwidth per node | **~10x** (700 GB/s → 7,300 GB/s) |
	  | Peak node performance (BF16 TFLOPS) | **~50x** (46 → 2,307) |
	  | Peak node performance (FP8 TFLOPS) | N/A → **4,614** (Ironwood new) |
	  | Performance per Watt (TDP) | **~30x** |
	  | Supercomputer (pod) size | **~36x** (256 → 9,216 nodes) |
	  | Pod bisection bandwidth | **~39x** (1,984 → 76,800 GB/s) |
	  | Pod HBM capacity (shared, addressable) | **~400x** (4 PB → 1,769 PB / 1.77 EB) |
	  | Peak pod performance (BF16 ExaFLOPS) | **~2,100x** (0.01 → 21.3) |
	  | Peak pod performance (normalized FP8) | **3,600x** relative |
	  | Carbon intensity (CCI, gCO₂e/ExaFLOP) | **~4.3x better** (339 for v4 → 79 for Ironwood) |

- ## Per-Generation Data Table

	- | Metric | TPU v2 (2017) | TPU v3 (2018) | TPU v4 (2021) | TPU v5p (2023) | Ironwood (2025) |
	  |---|---|---|---|---|---|
	  | Peak BF16 TFLOPS / node | 46 | 123 | 275 | 459 | 2,307 |
	  | Peak FP8 TFLOPS / node | N/A | N/A | N/A | 459 | 4,614 |
	  | MXU systolic arrays | 2× 128×128 bf16 | 4× 128×128 bf16 | 8× 128×128 bf16 | 8× 128×128 bf16 | 4× 256×256 bf16 + 4× 512×512 fp8 |
	  | VMEM (on-chip SRAM, MiB) | 32 | 32 | 32 | 128 | 128 |
	  | HBM version | HBM2 | HBM2 | HBM2 | HBM2E | HBM3E |
	  | HBM stacks per TPU | 2 | 4 | 4 | 6 | 8 |
	  | HBM capacity per TPU (GiB) | 16 | 32 | 32 | 96 | 192 |
	  | HBM bandwidth (GB/s) | 700 | 900 | 1,200 | 2,765 | 7,300 |
	  | TensorCores per TPU | 2 | 2 | 2 | 2 | 2 |
	  | SparseCores per TPU | 2 | 2 | 4 | 4 | 4 |
	  | Cooling | Air | Liquid | Liquid | Liquid | Liquid |
	  | ICI links per node | 4 | 4 | 6 | 6 | 6 |
	  | ICI BW per link (GB/s) | 62 | 70 | 50 | 100 | 100 |
	  | Pod topology | 2D Torus | 2D Torus | 3D Torus | 3D Torus | 3D Torus |
	  | Pod size (# TPUs) | 256 | 1,024 | 4,096 | 8,960 | 9,216 |
	  | Pod bisection BW (GB/s) | 1,984 | 4,480 | 25,600 | 64,000 | 76,800 |
	  | Pod HBM capacity (PetaBytes) | 4 | 33 | 131 | 851 | 1,769 |
	  | Pod peak BF16 ExaFLOPS | 0.01 | 0.13 | 1.1 | 4.1 | 21.3 |
	  | Relative pod TFLOPS/W (TDP) | 1 | 1.8 | 4.9 | 5.2 | **29.3** |
	  | Relative pod TDP (power) | 1 | 5.6 | 20 | 67 | 123 |

- ## Long-Term Trend: Memory Is the Dominant Scaling Lever

	- **HBM stacks doubled from v2 to Ironwood** (2 → 8), with each generation upgrading to higher-bandwidth HBM versions (HBM2 → HBM2E → HBM3E).
	- **Capacity trajectory**: 16 GiB (v2) → 32 GiB (v3/v4) → 96 GiB (v5p) → **192 GiB (Ironwood)**. Capacity roughly doubles every ~2 generations with a larger jump at v5p/Ironwood.
	- **Bandwidth trajectory**: 700 → 900 → 1,200 → 2,765 → **7,300 GB/s** — a 10.4x increase, disproportionate to FLOPS growth in early gens (bandwidth-bound workloads drove this).
	- **Supercomputer-level shared HBM memory** (directly addressable across the whole pod) grew ~400x: 4 TB (v2) → **1.77 petabytes (Ironwood)** — a new record for AI supercomputers.
	- **Why memory matters more than FLOPS at scale**: Transformer models require enormous activations, KV caches, and weight tensors that don't fit in on-chip SRAM (VMEM barely grew: 32 → 128 MiB). HBM is the effective working memory for all large model training; the pod-level addressable HBM is the practical bound on model size without offloading.
	- **VMEM (on-chip SRAM) grew slowly** — SRAM density scales more slowly than logic density. VMEM was flat at 32 MiB for v2–v4 and only doubled to 128 MiB in v5p/Ironwood despite much larger die areas.

- ## Architecture: Stable Core, Scaled Components

	- The TPU v2 microarchitecture block diagram is **unchanged through Ironwood** — the same two TensorCores, MXU, Vector Unit, SparseCore, DMA, and HBM layout persists. Scaling comes from component upgrades, not new microarchitectural paradigms.
	- **Key original design decisions that proved durable (adopted broadly by competitors):**
		- 1. Systolic arrays (MXU) for matrix multiply
		- 2. **Range-oriented narrow floating point** (BF16, FP8, FP4) vs. precision-oriented wide IEEE formats — TPU v2 was the first DNN accelerator to diverge from IEEE FP standard
		- 3. **HBM as main memory** (standard DRAM was a bottleneck in TPU v1; v2 improved bandwidth 30x by switching)
		- 4. Custom high-speed chip-to-chip interconnect (ICI) for multi-chip supercomputer assembly
		- 5. Software control of memory hierarchy via DMAs (scratchpad SRAM, not CPU-style caches)
		- 6. Vector Units for non-matrix operations
	- **Two features that remain unique to TPUs**: Optical Circuit Switches (OCSes) for interconnect topology management; SparseCores for embedding tables and collective ops.
	- **MXU scaling**: 2× 128×128 arrays (v2) → 4× 256×256 bf16 + 4× 512×512 fp8 (Ironwood). Ironwood added FP8 support and a redundant MXU row (yield/cost improvement mirroring DRAM redundant rows).
	- **Floating point precision trend**: BF16 → FP8 → FP4 (each generation adding lower precision support to increase throughput per Watt at acceptable accuracy). Ironwood's FP8 peak is 2× its BF16 peak (4,614 vs 2,307 TFLOPS).
	- **ICI topology upgrade**: 2D Torus (v2/v3) → 3D Torus (v4+), enabled by adding 2 more ICI links (4 → 6). This is what made 3D torus pods possible and scaled bisection bandwidth 39x.
	- **SparseCores** scaled from 2 (v2/v3) to 4 (v4+); performance grew 2.4x from v5p to Ironwood. Originally built for embedding tables (advertising, search, YouTube), now also serves as AllReduce/Scatter/Gather/Broadcast engines for Transformer collective ops.

- ## DNN Workload Mix Shift (2016–2026)

	- | Year / TPU | MLP/DLRM | RNN | CNN | Transformer | Diffusion |
	  |---|---|---|---|---|---|
	  | 2016 (TPU v1) | 61% | 29% | 5% | 0% | 0% |
	  | 2019 (TPU v3) | ~26% | ~25% | ~23% | ~25% | ~0% |
	  | 2020 (TPU v4 lite) | ~26% | ~25% | ~18% | ~28% | ~0% |
	  | 2022 (TPU v4) | 24% | 2% | 12% | 57% | ~0% |
	  | 2026 (Ironwood, internal) | 11% | <0.5% | 3% | **74%** | 6% |
	- Transformer paper published Dec 2017; by early 2019 it was already 21% of Google's production workload.
	- RNNs have practically disappeared (<0.5%). Diffusion models are now larger than CNNs (6% vs 3%).
	- The stable TPU architecture accommodated this complete DNN topology change without microarchitectural redesign — validating the bet on generalized systolic arrays + HBM over workload-specific designs.

- ## Resilience Innovations

	- **Goodput** (good throughput = fraction of time the system makes useful training progress) is the key training-system metric.
		- Gemini 1.0 on TPU v4: **97% goodput**
		- Gemini 2.5 on TPU v5p (synchronous data-parallel across multiple 8,960-chip pods, multiple data centers): **93% goodput**
	- **Optical Circuit Switches (OCSes)**, introduced in TPU v4: millisecond-switching 3D MEMS mirrors that enable modular installation (each 64-chip cube goes live independently), fault isolation, and scheduler flexibility (can select cubes from anywhere in the pod without requiring contiguous idle chips).
	- **Ironwood hardware reliability additions**:
		- **Functional Built-In Self-Test (FBIST)** inside the MXU — catches silent data corruption (SDC) during manufacturing burn-in and during operation.
		- **Hardware replay unit** in the VPU — samples vector bundles and replays odd-lane operations on even lanes (zero performance overhead, negligible power); catches intermittent errors from voltage/temperature/data-pattern stressors that pass all other screening.

- ## Power Efficiency

	- Relative pod TFLOPS/W (TDP): v2=1 → v3=1.8 → v4=4.9 → v5p=5.2 → **Ironwood=29.3** (~6x jump from v5p to Ironwood alone).
	- The large Ironwood jump reflects: (1) FP8 arithmetic doubling throughput per operation; (2) process node improvements; (3) liquid cooling enabling higher power density without thermal throttling (liquid cooling adopted from TPU v3 onward).
	- **Performance per Watt is now the primary design objective** — power is the binding constraint for new data center capacity, not silicon area or rack space.

- ## Carbon / Sustainability (Compute Carbon Intensity, CCI)

	- **CCI = CO₂e per utilized floating point operation** (gCO₂e/ExaFLOP). Combines operational emissions (electricity) + embodied emissions (manufacturing), amortized over 6-year chip lifetime.
	- | Generation | Operational CCI | Embodied CCI | Total CCI | vs. v4 |
	  |---|---|---|---|---|
	  | TPU v4 | 249 gCO₂e/EFLOP (73%) | 90 (27%) | **339** | baseline |
	  | TPU v5p | 224 (77%) | 68 (23%) | **292** | 1.2x better |
	  | Ironwood | 61 (77%) | 18 (23%) | **79** | **4.3x better** |
	- Operational CCI is ~75% of total for all three — energy dominates over manufacturing for data center AI (opposite of smartphones where 87% is embodied).
	- Example: training GPT-3 took ~3.14×10²³ FLOPs; TPU v5p CCI is 265×10⁻¹⁸ gCO₂e → ~83 million metric tons CO₂e.

- ## Investment Implications

	- **HBM is the constrained resource in AI ASIC design, not compute.** Every TPU generation added more HBM stacks and upgraded HBM generation; the pod-level memory grew 400x while pod-level compute grew 3,600x — memory bandwidth and capacity are the bottleneck, not FLOPs. This validates the HBM supply/demand thesis.
	- **HBM3E is now standard** for frontier training ASICs. TPU Ironwood uses 8 stacks of HBM3E at 7,300 GB/s — matching or exceeding NVIDIA H100 and B200 specifications. The next frontier (HBM4) will determine who has the compute-per-Watt lead in the next generation.
	- **Precision deflation is ongoing**: BF16 (TPU v2, 2017) → FP8 (Ironwood, 2025) → FP4 implied next. Each halving of precision doubles throughput per Watt for training-tolerant workloads. This means effective TFLOPS growth per generation substantially exceeds what HBM bandwidth growth would support — creating increasing pressure on memory-to-compute ratio.
	- **Google's vertical integration is a moat** — architectural stability means software/compiler optimizations carry forward immediately when new hardware ships, vs. external developers who start optimization from scratch after general availability.
	- **3,600x supercomputer performance growth with ~100x CAGR** despite end of Dennard scaling and slowdown of Moore's Law — driven by HBM scaling, interconnect scaling (ICI), chip count per pod (36x), and numerical precision shrinkage. This rate of improvement is the baseline for AI model scaling cost curves.

