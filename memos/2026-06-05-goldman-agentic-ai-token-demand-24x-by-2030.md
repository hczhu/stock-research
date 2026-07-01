tags:: [[AI infrastructure]], [[agents]], [[inference]], [[token economics]], [[compute]], [[DRAM]], [[HBM]], [[Morgan Stanley]], [[forecast]], [[demand]]

- ## Goldman Sachs — Agentic AI Token Use to Multiply ≈24× by 2030
	- **Source**: Goldman Sachs Research, "Token use by AI agents is expected to multiply 24 times by 2030" (estimates as of May 2026)
	- **Thesis**: Estimated monthly token count for agentic AI applications grows ≈**24×** to ≈**117 quadrillion tokens/month by 2030**, with the surge driven overwhelmingly by **agents** (consumer + enterprise) rather than legacy non-agent workloads. Enterprise agents are the single largest and fastest-growing slice.
	- **Note**: Figures below are read from the stacked-area chart (values approximate); the exact published series is not provided.
- ## Estimated Monthly Token Count — Total (quadrillion tokens/month)
  
  | Year | Total (≈ quadrillion/month) |
  |---|---:|
  | 2024 | ~2 |
  | 2025 | ~2.5 |
  | 2026 | ~6 |
  | 2027 | ~30 |
  | 2028 | ~47 |
  | 2029 | ~73 |
  | 2030 | **~117** |
	- Headline: **≈24× growth by 2030**; chart y-axis tops at 120 quadrillion
	- Curve is convex — the inflection is ~2026→2027 (≈5× jump), i.e. agentic adoption is the accelerant
- ## 2030 Breakdown by Segment (stacked)
  
  | Segment | 2030 monthly tokens (≈ quadrillion) | Share |
  |---|---:|---:|
  | Enterprise agents | ~56 | ~48% |
  | Consumer agents | ~45 | ~38% |
  | Non-agent workloads | ~16 | ~14% |
  | **Total** | **~117** | 100% |
	- **Agents = ~86% of 2030 tokens** (enterprise + consumer); non-agent (chatbots/legacy inference) shrinks to a minority share
	- Enterprise agents grow from a near-zero 2024 base to the largest segment — the steepest curve on the chart
- ## Approximate Segment Trajectory (quadrillion tokens/month)
  
  | Year | Non-agent | Consumer agents | Enterprise agents | Total |
  |---|---:|---:|---:|---:|
  | 2027 | ~7 | ~8 | ~15 | ~30 |
  | 2028 | ~10 | ~17 | ~20 | ~47 |
  | 2030 | ~16 | ~45 | ~56 | ~117 |
	- Non-agent workloads grow only modestly (~2→16); the entire story is agentic token expansion
- ## Token Multipliers by Interaction Mode (Anthropic internal data)
	- **Source**: Anthropic (cited in multi-agent systems research, June 2026)
	- Measured against a single-turn chat interaction as the baseline (1×):
	  
	  | Interaction mode | Token multiplier vs. chat |
	  |---|---:|
	  | Chat (single-turn) | 1× (baseline) |
	  | Single agent | ~**4×** |
	  | Multi-agent system | ~**15×** |
	- **Why agents use more tokens**: Agentic workflows require tool-call sequences, intermediate reasoning steps, multi-turn context accumulation, and result verification loops — all of which inflate total token count per task relative to a one-shot chat query.
	- **Why multi-agent compounds further**: Each subagent carries its own system prompt and context window; coordination messages, status updates, and result hand-offs between agents add tokens on top of each individual agent's workload. Coordination complexity grows rapidly with the number of agents.
	- **Connection to the 24× forecast**: If chat is 1× and multi-agent is 15×, a shift in the workload mix from mostly-chat (today) to mostly-agent (2030) mechanically drives token volume up even with *flat* query counts. Goldman's 24× figure is the aggregate of this mix-shift plus outright query volume growth — the Anthropic multipliers are the per-query engine behind the macro curve.
- ## Why It Matters — Investment Implications
	- **Demand-side fuel for the memory super-cycle**: Token volume is the proximate driver of inference compute and HBM/DRAM demand. A 24× token increase by 2030 is the demand leg under the memory and AI-infra theses (see [[2026-06-01-memory-super-cycle-five-arguments]], [[2026-05-26-compute-crunch-token-demand-vs-supply]], [[2026-06-03-ai-memory-wall-agentic-ai-dram-demand]]).
	- **Agents are the multiplier, not chatbots**: Agentic workflows (multi-step, tool-calling, long context, KV-cache-heavy) consume far more tokens per task than single-turn chat — exactly the workload mix that lifts DRAM/HBM intensity per query. The chart quantifies the "agents eat tokens" thesis.
	- **Enterprise is the prize**: Enterprise agents being the largest 2030 slice supports the enterprise-AI monetization case (recurring, high-value, data-resident) — read-through to hyperscaler capex, neoclouds, and inference infra ([[2026-06-04-neocloud-supply-demand-ai-infra-restructuring-kenny-zhang]]).
	- **Caveat — efficiency offset**: Token *count* ≠ proportional hardware demand. Model efficiency, quantization, KV-cache compression, and falling cost/token can decouple tokens from memory/compute growth (the bear case — see [[2026-06-02-memory-cycle-bear-case-arguments]]). A 24× token rise with 10× efficiency gains is a very different capex outcome than 24× with flat efficiency.
	- **Monetization gating**: 117 quadrillion tokens/month only converts to revenue/compute demand if priced above cost. The forecast assumes agentic AI is monetized at scale — the key unproven variable.