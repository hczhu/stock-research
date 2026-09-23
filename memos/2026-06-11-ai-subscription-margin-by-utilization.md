- tags:: [[token economics]], [[unit economics]], [[Anthropic]], [[OpenAI]], [[Claude]], [[ChatGPT]], [[coding-agents]], [[inference]], [[gross margin]], [[subscriptions]]
  file-created-at:: 2026-06-11

- ## AI Subscription Plan Gross Margin by Utilization (Claude vs ChatGPT/Codex)
	- **Source**: Provided analytical chart, "Subscription margin by utilization." Models the **provider's gross margin on each consumer/pro plan as a function of the subscriber's average utilization**.
	- **Key assumption (stated on chart)**: API list prices carry a **75% gross margin**, i.e. **cost-to-serve = 25% of the API-equivalent value** of the tokens a subscriber consumes. Margin shown = `1 − (cost-to-serve) / (subscription price)`.
	- **How to read "utilization"**: how heavily a subscriber uses the plan relative to the token volume its flat fee implies at API list prices. **Low utilization → subscriber consumes few tokens → provider keeps most of the fee → high margin.** As utilization rises, token cost grows linearly until it exceeds the flat fee → **negative margin** (provider loses money on that user).
	- **Note**: within each lab, two tiers share an identical margin curve — **claude-pro = claude-max-5x**, and **chatgpt-plus = chatgpt-pro-5x** (collapsed below; the "5x"/"20x" labels denote the headline usage multiplier of each plan).

- ## Gross Margin vs Average Utilization
	| Avg utilization | claude-pro / max-5x | claude-max-20x | chatgpt-plus / pro-5x | chatgpt-pro-20x |
	|---|---|---|---|---|
	| 1% | 95% | 90% | 91% | 82% |
	| 5% | 75% | 50% | 56% | 12% |
	| 5.7% | 71% | 43% | 50% | **0%** |
	| 10% | 50% | **0%** | 12% | -75% |
	| 11.4% | 43% | -14% | **0%** | -100% |
	| 15% | 25% | -50% | -31% | -162% |
	| 20% | **0%** | -100% | -75% | -250% |
	| 25% | -25% | -150% | -119% | -338% |
	| 50% | -150% | -400% | -338% | -775% |
	| 100% | -400% | -900% | -775% | -1650% |
	- The odd utilization columns (**5.7%**, **11.4%**) are inserted to mark exact break-even points: 5.7% for chatgpt-pro-20x, 11.4% for chatgpt-plus/pro-5x.

- ## Break-even & Worst-case (100% utilization)
	| Plan | Break-even utilization | Margin at full (100%) utilization |
	|---|---|---|
	| claude-pro / claude-max-5x | **20%** | -400% |
	| claude-max-20x | **10%** | -900% |
	| chatgpt-plus / chatgpt-pro-5x | **11.4%** | -775% |
	| chatgpt-pro-20x | **5.7%** | -1650% |
	- **Higher-tier "20x" plans break even at very low utilization** — claude-max-20x flips negative past **10%**, chatgpt-pro-20x past just **5.7%**. Even moderate use of the headline allowance makes the top tiers loss-making.
	- **OpenAI's curves are steeper/worse than Anthropic's at equal utilization** (e.g. at 100%: chatgpt-pro-20x −1650% vs claude-max-20x −900%; chatgpt-plus −775% vs claude-pro −400%), implying ChatGPT/Codex plans are priced with **less token headroom relative to cost-to-serve**.

- ## Why It Matters — Investment Read-Through
	- **All-you-can-eat subscriptions are a bet that average utilization stays low.** The model only works because the median subscriber barely uses the plan; a thin cohort of **always-on power/agent users is catastrophically unprofitable** (−400% to −1650% at full utilization). Quantifies the "subscriptions massively under-charge heavy agent users" point ([[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]]).
	- **Direct rationale for the April 2026 pivot to API-priced enterprise usage** — moving heavy users off flat seats onto metered API pricing is how labs escape the negative-margin tail; this chart is the unit-economics case for that shift.
	- **Coding agents sit at the dangerous end of the curve**: they are the highest-utilization product, so they push subscribers toward (and past) break-even fastest — the same dynamic behind Anthropic/OpenAI moving Claude Code / Codex to usage-based pricing.
	- **Demand-side fuel but margin-side caution**: rising token consumption supports the inference/HBM/DRAM chain ([[2026-06-05-goldman-agentic-ai-token-demand-24x-by-2030]]), but the loss-making tail shows **token growth ≠ provider profit** unless usage is metered or priced above cost-to-serve.
	- **Caveat**: the 75%-API-gross-margin / 25%-cost-to-serve assumption is the key lever — if real cost-to-serve falls (efficiency, KV-cache, cheaper compute), every curve shifts up and break-even utilization rises; if it's higher, the tail is even worse.
