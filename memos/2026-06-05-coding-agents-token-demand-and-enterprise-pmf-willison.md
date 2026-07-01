tags:: [[coding-agents]], [[token economics]], [[inference]], [[Anthropic]], [[OpenAI]], [[$MSFT]], [[enterprise-AI]], [[agents]], [[LLM]], [[AI infrastructure]]

- ## Coding Agents' Token Demand & the Enterprise PMF Inflection (Simon Willison)
	- **Source**: Simon Willison's Weblog, "I think Anthropic and OpenAI have found product-market fit," May 27 2026 (+ adjacent posts). All facts from the article.
	- **Thesis**: Coding agents (Claude Code/Cowork, Codex) **burn vastly more tokens** than chatbots and are becoming daily drivers for highly-paid professionals. In April 2026 both labs raised frontier-model prices *and* moved enterprise customers from deep-discounted seats to **API-price-for-usage** — the moment agentic token consumption turns into real, scaling revenue. ChatGPT's huge user base monetizes poorly by contrast; the money is in high-token enterprise agents.
- ## Coding Agents Burn Tokens — One Power User's Bill
	- Author pays **$100/mo Anthropic Max + $100/mo OpenAI Pro = $200/mo**
	- Via `ccusage`, his **last-30-day usage at API token prices** would have cost:
	  
	  | Tool | 30-day token cost at API prices |
	  |---|---:|
	  | Anthropic Claude Code | $1,199.79 |
	  | OpenAI Codex | $980.37 |
	  | **Total** | **$2,180.16** |
	- ~$2,180 of tokens consumed for $200 paid — a **~11× value gap** under the subscription, and he's only a "moderately heavy" user (not running agents 24/7)
	- Implication: subscription plans massively under-charge heavy agent users vs. true token cost → the economics only work once usage is priced at API rates
- ## The April 2026 Pricing Shift (enterprises now pay API prices)
  
  | Change | Detail |
  |---|---|
  | Anthropic Enterprise | Switched from "seats include enough usage for a typical workday" (Aug 2025) to **$20/seat/mo + API pricing for usage**; change made Nov 2025 (per spokesperson), surfaced via The Information Apr 14 2026; customers learn at renewal |
  | OpenAI Codex | **Apr 2, 2026**: pricing aligned to **API token usage** (not per-message) for new+existing Plus, Pro, ChatGPT Business, new Enterprise; **Apr 23, 2026** extended to all existing ChatGPT Enterprise (Edu, Health, Gov, Teachers) |
  | Net | As of April 2026, Enterprise cost for both Codex and Claude Code/Cowork = **listed API price** (no more extreme discounts) |
  | Model price hikes | **GPT-5.5 (Apr 23) = 2× the API price of GPT-5.4**; **Opus 4.7 (Apr 16) ≈ 1.4× Opus 4.6** (incl. new tokenizer) |
	- Both labs released higher-priced frontier models *and* locked enterprise customers (year-long deals) at API prices, not the prior deep discounts
- ## ChatGPT's Numbers — Scale ≠ Monetization
  
  | Metric | Value |
  |---|---|
  | ChatGPT weekly active users (Feb 2026) | **900M+** |
  | Paying consumer subscribers | **50M (5.6% of WAU)** |
  | Consumer plan price | $10–20/mo/user |
  | Subscribers needed (4 yrs) to cover $1T infra | **1–2 billion** |
	- **The monetization problem**: $10–20/mo consumer subs is "an OK business," but covering ~$1T of infrastructure would need 1–2B subscribers for 4 years — implausible
	- **The fix is high-token enterprise agents**: companies spending **$200+/mo/user** get there far faster; the author alone runs ~$1,000/mo in API cost *per vendor* as a power user
	- Coding agents are the wedge: daily drivers for well-compensated engineers now, extensible to "anything you can do by typing commands into a computer" — a much wider knowledge-worker TAM
- ## "AI-Cost-Alarm" Stories Are Thin (and actually bullish)
	- **Uber**: CTO said it "maxed out its full-year AI budget just a few months into 2026," mostly from Claude Code; COO noted **25% of code commits via Claude Code last quarter** but said the productivity→shipped-features link is "hard to draw." Author: a 2025 budget simply failed to predict 2026 Claude Code demand
	- **Microsoft** canceling Claude Code licenses (push engineers to its own Copilot CLI) — partly financial, timed to its June 30 FY-end
	- Author's read: both are the "suck air through teeth, then say **yes**" pricing signal — i.e. evidence of strong demand, not failure
- ## Inference Spend Is Enormous
	- **SpaceX S-1**: in May 2026, SpaceX signed Cloud Services Agreements with Anthropic for compute across **COLOSSUS and COLOSSUS II**; Anthropic pays **$1.25 billion/month through May 2029**
	- Anthropic said the deal lets it "increase usage limits for Claude Code and the Claude API" → implies Colossus capacity is for **inference, not training**
	- Anthropic already has vast compute elsewhere; $1.25B/mo from *one* vendor signals how large inference budgets have become
- ## Anthropic Revenue Trajectory & Enterprise Pivot
  
  | Metric | Value |
  |---|---|
  | Run-rate revenue (Feb 12 2026, Series G) | $14B; growing >10× annually each of past 3 years |
  | Run-rate revenue (late May 2026) | **crossed $47B** |
  | Rumored Q2 revenue | **$10.9B** — potentially first-ever profitable quarter |
  | Historical API concentration (Aug 2025) | Cursor + GitHub Copilot = $1.2B of then-$4B revenue |
	- Run-rate definition (Reuters Breakingviews): (last 28 days consumption sales × 13) + (monthly subscription × 12)
	- **Pivot to enterprise = cutting out the middlemen**: Claude Code competes directly with Cursor and GitHub Copilot (its own former largest API customers) — "no wonder Cursor are investing in their own models"
- ## Two Inflection Points
	- **November 2025**: GPT-5.1 + Opus 4.5 + their coding harnesses got *good enough* to reliably do useful work — agents became daily drivers
	- **April 2026**: the *revenue* implications land — higher model prices + enterprise API-price lock-in convert agent usage into real revenue
	- Real audited numbers will come with the **Anthropic and OpenAI IPO S-1s**
- ## Investment Implications
	- **Coding agents are the highest-token-intensity AI product with proven willingness-to-pay** — direct fuel for the inference/token-demand → HBM/DRAM chain ([[2026-06-05-goldman-agentic-ai-token-demand-24x-by-2030]], [[2026-06-03-ai-memory-wall-agentic-ai-dram-demand]], [[2026-05-26-compute-crunch-token-demand-vs-supply]])
	- **Enterprise API-price lock-in is the monetization unlock**: counters the bear-case "unproven unit economics" pillar ([[2026-06-02-memory-cycle-bear-case-arguments]]) — labs are now capturing true token value from year-long enterprise deals
	- **Consumer chat is a weak monetizer; high-token enterprise agents carry the model**: 5.6% ChatGPT paid conversion vs $200–1,000/mo/seat agent spend — the revenue mix is shifting to per-token enterprise consumption
	- **Inference capex is massive and contracted**: Anthropic's $1.25B/mo SpaceX/Colossus inference deal validates sustained compute/memory demand (neocloud read-through — [[2026-06-04-neocloud-supply-demand-ai-infra-restructuring-kenny-zhang]])
	- **Disintermediation risk for app-layer middlemen**: Claude Code/Codex competing with Cursor/Copilot pressures the wrappers; Cursor building own models in response — a margin/positioning warning for AI-application companies
	- **Caveat**: ROI-to-output link is still unproven (Uber's COO: hard to tie 25% AI commits to shipped value) — token spend is real, but durable enterprise budgets require the productivity case to hold