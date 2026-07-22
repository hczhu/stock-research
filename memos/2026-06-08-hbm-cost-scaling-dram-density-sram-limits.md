- tags:: [[HBM]], [[DRAM]], [[SRAM]], [[GPU]], [[semiconductor]], [[capex]], [[inference]], [[$NVDA]]

- **Source**: User-provided screenshot, 2026-06-08, showing HBM generation specs and excerpts on HBM cost inflation, DRAM density deceleration, and SRAM-only inference limits.

- ## HBM Generation Data
	- The table is useful because it separates pin-level progress, stack-level bandwidth, die count, capacity per die, stack capacity, and NVIDIA GPU attachment.

	| Metric | HBM | HBM2 | HBM2E | HBM3 | HBM3E | HBM4 |
	|---|---:|---:|---:|---:|---:|---:|
	| Year introduced | 2013 | 2016 | 2019 | 2022 | 2023 | 2026 |
	| Max pin bandwidth (Gb/s) | 1.0 | 2.4 | 3.6 | 6.4 | 9.8 | 8 |
	| Number of pins | 1,024 | 1,024 | 1,024 | 1,024 | 1,024 | 2,048 |
	| Stack bandwidth (GB/s) | 128 | 307 | 461 | 819 | 1,254 | 2,048 |
	| Max dies / stack | 4 | 8 | 12 | 12 | 16 | 16 |
	| Max capacity / die (GiB) | 1 | 1 | 2 | 2 | 3 | 4 |
	| Max stack capacity (GiB) | 4 | 8 | 24 | 24 | 48 | 64 |
	| NVIDIA GPU generation |  | Volta V100 | Ampere A100 | Hopper H100 | Blackwell B100 | Rubin R100 |
	| HBM stacks / GPU |  | 4 | 5 | 5 | 8 | 8 |

- ## Derived Metrics
	- HBM's bandwidth and capacity compounding is real, but the source text argues the cost curve is worsening because stacking, packaging, and DRAM density growth are getting harder.

	| Comparison | Change | Read-through |
	|---|---:|---|
	| HBM stack bandwidth: HBM → HBM4 | 128 GB/s → 2,048 GB/s, **16x** | Bandwidth per stack has scaled dramatically over 13 years |
	| HBM stack capacity: HBM → HBM4 | 4 GiB → 64 GiB, **16x** | Capacity per stack has scaled with bandwidth, but via higher die count and density |
	| HBM3E → HBM4 pins | 1,024 → 2,048, **2x** | HBM4 bandwidth gain relies on wider interface and packaging complexity |
	| HBM3E → HBM4 pin bandwidth | 9.8 Gb/s → 8 Gb/s, **-18%** | Pin speed is not the sole bottleneck; physical interface width matters |
	| V100 → Rubin HBM stacks/GPU | 4 → 8, **2x** | Accelerator value/cost increasingly shifts toward memory subsystem and packaging |
	| HBM cost trend | Capacity and bandwidth cost both **1.35x higher from 2023-2025** | HBM is not following commodity DRAM deflation |
	| DDR4 cost trend | Capacity cost **0.54x**, bandwidth cost **0.45x from 2022-2025** | Commodity DRAM still deflates structurally outside HBM bottlenecks |
	| DRAM density cadence | Fourfold scaling now **>10 years** vs **3-6 years** previously | Slower density growth supports tighter supply and higher value for advanced memory |

- ## Investment Implications
	- **HBM is de-commoditizing DRAM**: the product is increasingly defined by stacking yield, interface width, thermal constraints, and packaging, not just bit supply. This supports the thesis that SK Hynix, Samsung, and Micron can earn structurally better margins in AI memory than in legacy commodity cycles.
	- **HBM4 is a packaging and interface transition**: doubling pins makes advanced packaging more important. Value may accrue not only to memory makers but also to packaging ecosystems, interposer capacity, and accelerator vendors that can qualify stable HBM4 stacks.
	- **AI accelerator BOM keeps moving toward memory**: NVIDIA moving from 4-5 HBM stacks per GPU to 8 reinforces that memory capacity/bandwidth are central to accelerator performance and cost.
	- **SRAM-only is a niche, not a full substitute**: Groq/Cerebras-style SRAM-heavy designs may serve latency-sensitive tiers, but external DRAM/HBM appears unavoidable for large LLM capacity. This weakens the bear case that novel inference ASICs can simply bypass the HBM bottleneck.
	- **Long-term memory cost divergence matters**: if HBM capacity and bandwidth costs keep rising while DDR-class DRAM deflates, HBM suppliers can have a premium AI product cycle even if commodity memory remains cyclical.

- ## Questions to Track
	- Can HBM4 yields ramp without recreating the severe supply shortage and qualification bottlenecks seen in HBM3E?
	- Do Rubin/R100-class GPUs actually ship with 8 HBM4 stacks broadly, or do supply and packaging constraints segment the product line?
	- Does HBM's cost per bandwidth keep rising after 2026, or does packaging learning eventually flatten the curve?
	- Are SRAM-heavy inference vendors adding external DRAM as a permanent architecture change or only as a workaround for specific workloads?
