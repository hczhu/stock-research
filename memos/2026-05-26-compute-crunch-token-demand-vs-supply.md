- tags:: [[$NVDA]], [[inference]], [[AI]], [[compute]], [[Blackwell]], [[GB200]], [[semiconductor]], [[Epoch-AI]]
  file-created-at:: 2026-05-26

- ## Is a Compute Crunch Coming? Token Demand vs Supply Analysis
	- **Source**: Gradient Updates (Epoch AI) — "Is a compute crunch coming?", Luke Emberson and Jaime Sevilla, May 26, 2026
	- **Thesis**: Global token demand is growing ~10×/year while supply grows ~3.4×/year; a compute crunch for large-model inference is likely near, particularly for long-context agentic workloads.

- ## Table 1: Global Token Demand — Current and Observed Proxies

	| Metric | Value | Notes |
	|---|---|---|
	| Google platforms (total) | ~1.2B tok/s | Input + output combined, all platforms |
	| Google estimated output only | ~130M tok/s | Assumes 8,000:1,000 input:output ratio |
	| All providers combined (Exponential View) | ~5B tok/s | ~40 quadrillion tokens/quarter; input + output |
	| SWE demand estimate — low | ~200M output tok/s | 14M daily AI users × Meta intensity (1M out tok/day/user) |
	| SWE demand estimate — high | ~4B output tok/s | 14M daily AI users × Apple intensity (25M out tok/day/user) |
	| Meta internal usage | 60T tokens/month | 85,000 employees total; ~1M output tok/day/employee (at 25K:1K ratio) |
	| Apple power-user allowance | up to $300/day/engineer | ≈ 5M out tok/day (Opus 4.7 pricing) or 25M out tok/day (Kimi K2.6 pricing) |
	| Global software engineers | ~30M (range: 20–50M) | 2025 estimate |
	| SWEs using AI daily | ~47% (~14M) | Stack Overflow 2025 developer survey |
	| Token demand growth rate | ~10×/year | Based on Google and Exponential View proxies |

- ## Table 2: Global Token Supply — Current and Forecast

	| Metric | Value | Notes |
	|---|---|---|
	| GB200 GPUs deployed (Q4 2025) | 1.9M individual GPUs | In NVL72 rack configurations |
	| GB300 GPUs deployed (Q4 2025) | 1.5M individual GPUs | In NVL72 rack configurations |
	| Blackwell share of total FLOP/s | ~40% | GB200 + GB300 combined |
	| Calibrated throughput per GB200 NVL72 | ~400,000 tok/s | Kimi K2.6-like model, 8K:1K profile, w/ speculative decoding |
	| Total Blackwell output capacity (8K:1K) | ~500M–2B tok/s | Low end calibrated; high end theoretical |
	| Total Blackwell output capacity (all context) | 500M–20B tok/s | Range across short to long context lengths |
	| Compute capacity growth rate | 3.4×/year | Long-term ceiling (compute-bound) |
	| Memory bandwidth growth rate | 4.1×/year | Short-term driver while bandwidth-bound |
	| Overall inference capacity growth | ~3.4×/year | Conservative long-term estimate at fixed model size |
	| Supply vs demand gap | Demand ~10×/yr vs supply ~3.4×/yr | Crunch likely near, especially for long-context agentic workloads |

- ## Table 3: NVIDIA GB200 NVL72 Specs and Inference Performance

	| Spec | Value | Notes |
	|---|---|---|
	| GPUs per rack | 72 | NVL72 configuration |
	| HBM bandwidth (per NVL72) | 576 TB/s | Inferred from decode bandwidth calculations |
	| Weight precision | FP4 | 0.5 bytes/parameter |
	| KV cache precision | FP8 | 1 byte/value |
	| Model weight footprint (Kimi K2.6) | ~500 GB | 1T parameters × 0.5 bytes |
	| KV cache size per user (8K ISL) | ~265 MiB | Per NVL72 read per decode step |
	| Theoretical throughput (8K:1K, no calibration) | ~640,000 tok/s | Before applying real-world efficiency factors |
	| Calibrated throughput (8K:1K) | ~400,000 tok/s | After efficiency adjustments |
	| Compute efficiency (calibrated) | 65% | Fitted against SemiAnalysis InferenceX data (111 runs) |
	| Bandwidth efficiency (calibrated) | 30% | Includes inter-GPU communication overhead |
	| Per-step latency (calibrated) | 5ms | Captures kernel scheduling, routing imbalance, etc. |
	| Speculative decoding throughput boost | 1.6–2× | Effective at bandwidth-bound batch sizes |
	| Compute-bound batch threshold (8K:1K) | ~870 concurrent users/NVL72 | Beyond this, adding users reduces per-user speed |
	| Compute-bound batch threshold (25K:1K) | ~130 concurrent users/NVL72 | MLA quadratic attention cost shrinks crossover point |
	| Aggregate theoretical throughput (all Blackwell) | ~36B tok/s | 1.9M GB200 GPUs, before calibration |

- ## Table 4: Inference Setting Parameters

	| Parameter | Value | Notes |
	|---|---|---|
	| Reference model | Kimi K2.6 | 1T total params, 32B active, MoE, 256K context, MLA attention |
	| Min acceptable output speed | 35 tok/s | Threshold for acceptable user experience |
	| Short-context profile | 8,000 : 1,000 | Input:output tokens; general use (OpenRouter median: 6K:800) |
	| Medium-context profile | 25,000 : 1,000 | Agentic coding (OpenRouter/ArtificialAnalysis empirical) |
	| Long-context profile | 128,000 : 1,000 | Extended coding sessions; frontier models support up to 1M ctx |
	| Attention mechanism | MLA (Multi-head Latent Attention) | Stores low-rank latent vectors instead of full KV; ~4× more attention FLOP vs MHA but saves KV bandwidth |
	| KV projection trick | Absorbed at load time | Up-projection matrices folded into Q/O projections; avoids recomputation per decode step |
	| Chunked prefill | Enabled | Overlaps idle compute (decode phase) with prefill work; equalizes utilization |
	| Speculative decoding | Enabled | Draft model proposes N tokens ahead; main model verifies in one pass; ~3× decode throughput at fixed batch |
	| Weight format | FP4 (0.5 B/param) | Lower precision reduces bandwidth load during weight reads |
	| KV cache format | FP8 (1 B/value) | Stored in HBM; dominant bottleneck during decode at large context |
	| Real-world API output speeds | Kimi K2.6: ~35 tok/s | Moonshot API spot check |
	| | GPT-5.5: ~30–35 tok/s | OpenRouter data |
	| | Claude Opus 4.7: ~40–45 tok/s | OpenRouter data |
	| | Gemini 3.1 Pro: ~50–60 tok/s | OpenRouter data |

- ## Investment Implications
	- Demand growing ~10×/yr vs supply ~3.4×/yr implies persistent pricing power for inference compute — bullish for NVIDIA and HBM suppliers (SK Hynix, Micron)
	- Long-context agentic workloads (coding agents) are the most bandwidth-constrained — HBM density and bandwidth are the limiting resource, not raw FLOP/s
	- Anthropic already managing demand via quotas and off-peak incentives — confirms supply is binding at the frontier
	- Efficiency gains (speculative decoding, MLA, FP4) are real but ~2× in magnitude; they slow but do not close the 3× annual demand/supply gap
	- Small models benefit structurally: as large-model tokens get priced up, everyday use cases shift to cheaper models — not a regression in user capability given rapid small-model improvement
	- Per-GPU calibrated throughput is ~60% of theoretical (400K vs 640K tok/s) — real-world deployments underperform datasheets substantially, primarily due to bandwidth inefficiency and inter-GPU communication
