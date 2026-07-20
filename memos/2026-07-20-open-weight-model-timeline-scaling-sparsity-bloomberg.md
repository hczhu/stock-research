- tags:: [[open-weight-models]], [[DeepSeek]], [[Kimi]], [[Moonshot]], [[Qwen]], [[GLM]], [[Llama]], [[$META]], [[MoE]], [[sparsity]], [[HBM]], [[DRAM]], [[China]], [[Thinking-Machines-Lab]], [[commoditization]], [[inference]]

- **Source**: Bloomberg "Open Weight Model Timeline" table (Dec 2024 – Jul 2026), compiled from Moonshot, DeepSeek, Meta, Alibaba, Artificial Analysis, Thinking Machines Lab, NVIDIA. Total/active parameters, MoE sparsity ratio, and Artificial Analysis (AA) Intelligence Index. Investment framing is mine. Companion to [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]], [[2026-07-13-benedict-evans-token-pricing-commodity-infrastructure]], [[2026-07-13-semianalysis-meta-superintelligence-1yr-update]], [[DRAM-memory-ssd-index-thesis]], [[2026-07-18-napkin-llm-inference-cost-serving-economics]].

- **Thesis frame**: Three trends jump off the table. (1) **Total parameters are exploding** — from ~671B (DeepSeek V3, Dec-24) to **2.8T (Kimi K3, Jul-26)** — while (2) **active parameters stay tiny (13–50B)** because (3) **MoE sparsity is climbing fast (18× → 56×)**. Open-weight *intelligence* nearly tripled (AA index ~13–20 in 2025 → **40–57 in 2026**). The competitive punchline: **the open-weight frontier is now almost entirely Chinese** (DeepSeek, Kimi/Moonshot, Qwen/Alibaba, GLM/Zhipu); Meta's Llama 4 is the laggard and the only credible US entrant is TML's Inkling.

- ## The Table (extracted)
	- | Model | Released | Total params (B) | Active params (B) | Sparsity ratio | AA Intelligence Index |
	  |---|---|---:|---:|---:|---:|
	  | DeepSeek V3 | Dec 2024 | 671 | 37 | 18× | N/A |
	  | DeepSeek R1 | Jan 2025 | 671 | 37 | 18× | 20 (est.) |
	  | Llama 4 Maverick | Apr 2025 | 400 | 17 | 24× | 14 (est.) |
	  | Qwen3-235B | Apr 2025 | 235 | 22 | 11× | 13 (est.) |
	  | Kimi K2 | Jul 2025 | 1,000 | 32 | 31× | 44 |
	  | DeepSeek V4-Flash | Apr 2026 | 284 | 13 | 22× | 40 |
	  | DeepSeek V4-Pro | Apr 2026 | 1,600 | 49 | 33× | 44 |
	  | GLM-5.2 | Jun 2026 | 753 | n/d | n/d | 51 |
	  | TML Inkling | Jul 2026 | 975 | 41 | 24× | 41 |
	  | Kimi K3 | Jul 2026 | **2,800** | 50 | **56×** | **57** |
	  | Qwen3.8 Max | Jul 2026 | 2,400 | N/D | N/D | pending |
	- N/D = not disclosed. TML = Thinking Machines Lab (Mira Murati). GLM = Zhipu/z.ai. Qwen = Alibaba.

- ## What the Data Shows
	- **Total params ~4× in 18 months** (671B → 2.8T); two models now ≥2.4T (Kimi K3 2.8T, Qwen3.8 Max 2.4T) — the [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]] "largest open model" point, now with the trajectory behind it.
	- **Active params stay flat-to-low (13–50B)** across the whole period — even as total balloons 4×. This is the **decoupling of capacity from per-token compute**: MoE lets you grow the knowledge/skill store (total params) without proportionally growing the FLOPs per token (active params).
	- **Sparsity ratio is the lever, and it's rising**: 18× (DeepSeek V3) → **56× (Kimi K3)**. Higher sparsity = more total capacity per unit of active compute. Kimi K3's 56× (2.8T/50B) is the extreme; DeepSeek V4-Pro 33× (1.6T/49B); Llama 4 24×.
	- **Intelligence roughly tripled**: 2025 open models clustered at AA index **13–20** (Llama 4 14, Qwen3-235B 13, R1 20); 2026 open models hit **40–57** (Kimi K3 57, GLM-5.2 51, DeepSeek V4-Pro/Kimi K2 44). The open frontier closed most of the gap to closed frontier in ~a year.
	- **Efficiency divergence within DeepSeek V4**: Flash (284B/13B, index 40) vs Pro (1.6T/49B, index 44) — a **6× total-param, ~4× active-param jump buys only +4 index points**, quantifying diminishing returns at the top and why cheap "Flash" tiers are attractive (ties to the value-per-token debate in [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]]).

- ## Competitive Landscape
	- **Chinese labs own the open-weight frontier**: DeepSeek (V3/R1/V4), Moonshot/Kimi (K2/K3), Alibaba/Qwen (3-235B, 3.8 Max), Zhipu/GLM (5.2). Kimi K3 (57) and GLM-5.2 (51) are the top open scores — consistent with the "open-source as national strategy" read in [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]].
	- **Meta's Llama is the laggard and fading**: Llama 4 Maverick (Apr-25) scores just **14** and has no 2026 successor on the list — corroborating "**since Meta abandoned Llama, the US has no leading open model**" from [[2026-07-13-semianalysis-meta-superintelligence-1yr-update]].
	- **TML Inkling (Jul-26, index 41)** is the notable **US open-weight entrant** — Thinking Machines Lab (Mira Murati) putting a credible, if not frontier, open model on the board; the only non-Chinese 2026 model here.

- ## Investment Read-Throughs
	- **Bullish HBM/DRAM ([[DRAM-memory-ssd-index-thesis]])**: sparse MoE **still loads *all* total params into memory** even though only active params compute per token. So a 2.8T model = **~2.8TB of weights (at FP8/8-bit) resident in HBM** regardless of the low 50B active count — total-param growth is a **direct memory-content driver** even as it keeps compute cheap. The "big total / small active" trend is *the* mechanistic bull case for memory over logic (echoes the memory-bound conclusion in [[2026-07-18-napkin-llm-inference-cost-serving-economics]] and [[2026-07-07-interconnect-first-inference-latency-over-bandwidth-lpddr]]).
	- **Sparsity = the commoditization enabler**: rising sparsity keeps *inference compute* cheap while intelligence climbs, which is exactly what lets open-weight models undercut closed labs on price-per-capability — reinforcing the labs-margin-pressure / "no durable moat" thesis in [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]] and [[2026-07-13-benedict-evans-token-pricing-commodity-infrastructure]]. But the huge total-param footprint means **self-hosting still needs >1TB-VRAM boxes** — so the beneficiaries are neoclouds/enterprises with scale, not laptops.
	- **$META**: Llama's stall (index 14, no successor) is a concrete negative for Meta's open-model standing and validates the MSL-memo framing that Meta's edge is now compute + RL-data, not an open model.
	- **US vs China gap**: a table where 9 of 11 rows are Chinese is the clearest single artifact of the open-weight leadership shift — a geopolitical/policy variable (export controls, model gating) as much as a technical one.
	- **Watch items**: Qwen3.8 Max's pending AA score (does Alibaba match Kimi K3's 57?); whether any US lab besides TML ships a frontier open model; whether sparsity keeps rising (60×+) — each additional turn widens the total-param/HBM footprint while holding compute flat.
