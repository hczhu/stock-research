- tags:: [[Anthropic]], [[OpenAI]], [[AI training]], [[compute]], [[$NVDA]], [[AWS]], [[Trainium]], [[GB200]], [[VR200]], [[FP4]], [[AI infrastructure]]
  file-created-at:: 2026-06-04

- ## FP4 Training and the Anthropic–OpenAI Compute Gap
	- **Source**: User-provided analysis, June 2026
	- **Question**: If FP4 training is viable, how much compute disadvantage does Anthropic face vs. OpenAI given Anthropic's reliance on Trainium 2 (no FP4 support)?

---

- ## Table 1: Per-Chip Compute (PFLOPS)

	| Chip | FP4 (PFLOPS) | FP8 (PFLOPS) | FP4 / FP8 ratio |
	|---|---:|---:|---:|
	| Trainium 2 | — (none) | 1.3 | — |
	| Trainium 3 | 2.5 | 2.5 | 1.0× |
	| GB200 | 10 | 5 | 2.0× |
	| VR200 | 35 | 17.5 | 2.0× |

	- GB200 and VR200 deliver 2× more compute in FP4 than FP8 — the full FP4 gain is only accessible to chips that support the format
	- Trainium 3 has FP4 support but at only 2.5 PFLOPS — flat vs. its FP8 throughput, suggesting a different architecture trade-off

---

- ## Table 2: Largest AI Training Clusters

	| Cluster | Chip | Chip count | FP4 (ZFLOPS) | FP8 (ZFLOPS) | Operator |
	|---|---|---:|---:|---:|---|
	| Rainier | Trainium 2 | ~1,000,000 | — | 1.3 | Anthropic (via AWS) |
	| Abilene | GB200 | ~220,000 | 2.2 | 1.1 | OpenAI (via Microsoft) |
	| Fairwater | GB200 | ~300,000 | 3.0 | 1.5 | OpenAI / Microsoft |

	- In FP8, Anthropic's Rainier cluster (1.3 ZFLOPS) is roughly on par with each individual OpenAI cluster
	- In FP4, Rainier has zero usable compute; Abilene has 2.2 and Fairwater has 3.0 ZFLOPS

---

- ## Table 3: Anthropic Compute Disadvantage if OpenAI Trains in FP4

	| Comparison | OpenAI FP4 (ZFLOPS) | Anthropic FP8 (ZFLOPS) | Deficit |
	|---|---:|---:|---:|
	| Rainier vs. Abilene | 2.2 | 1.3 | **1.7×** |
	| Rainier vs. Fairwater | 3.0 | 1.3 | **2.3×** |

	- The 1.7–2.3× range represents the effective compute gap if OpenAI adopts FP4 training and Anthropic remains on Trainium 2
	- This gap translates directly to: longer RL runs, larger models, or faster iteration cycles for OpenAI

---

- ## Table 4: Trainium 3 FP4 Gap vs. GPU Generations

	| Chip pair | Trainium 3 FP4 (PFLOPS) | Competitor FP4 (PFLOPS) | Gap |
	|---|---:|---:|---:|
	| Trainium 3 vs. GB200 | 2.5 | 10 | **4×** behind |
	| Trainium 3 vs. VR200 | 2.5 | 35 | **14×** behind |

	- Trainium 3 (already deploying in 2026) is 4× behind GB200 on FP4 per chip
	- By 2027, when VR200 clusters are dominant, the per-chip FP4 gap grows to 14×
	- Amazon's largest clusters would need ~4× more chips than an equivalent GB200 cluster in 2026, or ~14× more chips vs. a VR200 cluster in 2027 — neither is likely to be built at that scale

---

- ## Table 5: Large Model Deployment Feasibility (2026)

	| Scenario | System | Memory | Max Model Size |
	|---|---|---:|---:|
	| Single NVL72 rack (GB300) | GB300 NVL72 | 20 TB | ~20–30T parameters |
	| VR200 cluster | VR200 | TBD | significantly larger |

	- A 20–30T parameter model can be deployed on a single GB300 NVL72 rack (20 TB HBM)
	- OpenAI could train a 20–30T model in 2026 and deploy it on a single rack — a qualitatively new scale-efficiency milestone

---

- ## Analysis: Is Anthropic Compute-Mog'd by 2027?
	- **2026 (FP8 parity)**: Rainier's 1.3 ZFLOPS FP8 is roughly matched against a single OpenAI cluster; Anthropic is competitive if training stays in FP8
	- **2026 (FP4 shift)**: If OpenAI uses FP4, Anthropic falls 1.7–2.3× behind immediately — no Trainium 2 upgrade path exists for FP4
	- **2027 (VR200 era)**: The per-chip FP4 disadvantage of Trainium 3 vs. VR200 is 14×; even a much larger Trainium cluster cannot close this gap at plausible build scales
	- **Most likely outcome**: Anthropic pivots to Google TPUs or NVIDIA VR200 clusters for frontier training in 2027 — the Trainium dependency becomes a ceiling, not a floor
	- **The deeper question**: Whether FP4 training degrades model quality enough to negate the FLOPS advantage — if FP4 introduces unacceptable precision loss for frontier-scale training, Anthropic's FP8 parity on Trainium may be sufficient

- ## Cross-References
	- [[2026-06-03-frontier-labs-gpu-compute-capacity-share]] — broader GPU capacity share across frontier labs
	- [[2026-06-02-microsoft-slide-claude-mythos-training-compute]] — Microsoft's view on Claude training compute
	- [[2026-05-26-compute-crunch-token-demand-vs-supply]] — token supply vs. demand dynamics
