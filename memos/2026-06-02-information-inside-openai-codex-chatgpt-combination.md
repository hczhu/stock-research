- tags:: [[OpenAI]], [[Codex]], [[ChatGPT]], [[Anthropic]], [[Claude-Code]], [[Claude-Cowork]], [[agents]], [[coding-agents]], [[SaaS]], [[product-strategy]], [[The-Information]]

- **Source**: Stephanie Palazzolo, "Inside OpenAI's Decision to Combine Codex and ChatGPT" (Exclusive), The Information, **June 2, 2026**. On-record: Thibault Sottiaux (now head of "core product and platform") and Alexander Embiricos (head of enterprise product, ex-Codex product lead); plus developer interviews (Basis, Cisco, Notion). This is the primary source behind the superapp coverage in [[2026-07-16-openai-superapp-chatgpt-codex-whither-chat-stratechery]] (Thompson's Jul 14 commentary on the shipped result). Companion to [[2026-07-06-gpt56-sol-hn-cerebras-inference-economics]] and [[2026-07-16-dylan-patel-podcast-ai-infra-memory-cpu-optics-power]].

- **Thesis frame**: The inside story of OpenAI reorganizing its entire product company around Codex after conceding that **"Codex works better for many tasks than ChatGPT."** The growth and revenue numbers here are the hard data behind the coding-agent land war: **Codex 3M→4M→5M+ WAUs in ~6 weeks, enterprise revenue +50% week-over-week, usage +5% day-over-day** — against **Anthropic at >\$47B annualized revenue (5× since January), propelled by Claude Code**, vs OpenAI's ~\$30B. Coding agents are now the primary revenue engine *and* the primary org-design forcing function at both labs.

- ## Key Data Points
	- | Metric | Value | Source/date |
	  |---|---|---|
	  | Codex weekly active users | **3M → 4M (~a month later) → 5M+ (end of May 2026)** | Company |
	  | Codex WAU composition | **Majority paying**, large portion still free | Person with knowledge |
	  | Codex enterprise revenue growth | **+50% week-over-week** | Brockman to staff (May) |
	  | Codex overall usage growth | **+5% day-over-day** | Altman, all-hands |
	  | **Anthropic annualized revenue** | **>\$47B as of May 2026 — 5× the start-of-year level**, propelled by Claude Code | The Information |
	  | OpenAI annualized revenue | \$25B (last disclosed, March) → **passed \$30B** | The Information reporting |
	  | ChatGPT consumer base | **900M+ users** (the superapp distribution target) | Article |
	  | Google search volume | Codex searches **spiked past Claude Code mid-May** (peak ~100 vs ~60 indexed) | Google Analytics chart, Jun-25→May-26 |
	  | Claude Code / Cowork users | Not disclosed; **paying users only** (no free tier) | Article |
	  | Anthropic coding-product revenue | "Likely greater than Codex's today" | Article's judgment |

- ## The Timeline (how OpenAI lost, then chased, coding)
	- **Fall 2024**: Claude "pulled ahead of OpenAI's models by some internal measures" — alarming because OpenAI long believed **AI-for-coding speeds up the research process key to superintelligent AI** (coding = the recursive-self-improvement input, not just a product).
	- **Jan 2025**: Operator (browser-clicking agent) ships; leaders quickly realize **"having an AI click around a browser was too slow"** — writing code is the more efficient way for AI to navigate a computer. (The GUI-agent → code-agent pivot in one sentence.)
	- **Early 2025**: Claude Code research preview (February) confirms the gap; OpenAI stands up a dedicated coding team.
	- **Dec 2025**: GPT-5.2 makes Codex better at long-running tasks. **Feb 2026**: Codex desktop app ships — the switching catalyst for many developers. **Apr 2026**: GPT-5.5 — "first time OpenAI incorporated a new base model in its flagship since its **forgettable GPT-4.5**" — and the moment "the gap became impossible to ignore" (Basis). **May 2026**: Codex mobile app; 5M WAUs; superapp announced.

- ## Why Codex Won Inside OpenAI (org-design insights)
	- **"Startup within a startup"**: the Codex team built **model and product in tandem** — unlike OpenAI's applied org, which built products separately from the research org. Employees credit this coupling for Codex's edge.
	- **Open-sourced the Codex harness code** — "a rare choice at most companies" — to harvest user feedback and contributions (Embiricos).
	- **Codex's superior harness** (the tool-use/action software) is a key stated reason for merging it with ChatGPT — the harness, not the model, is the asset being scaled to 900M users.
	- **The reorg cascade**: January memo — couple product teams tightly with the researchers on their underlying models; May — ChatGPT + Codex + API teams combined into one org **under Sottiaux ("core product and platform")**. OpenAI has organizationally rebuilt itself around its #2 product.
	- **Architecture challenge**: ChatGPT runs in the cloud; **Codex runs locally with file access**. Near term: Codex-vs-ChatGPT choice inside ChatGPT; long term: **"the model will decide whether to execute tasks on a user's device or in the cloud"** (Embiricos) — the routing-as-product endgame.
	- **Growth hack worth noting**: Codex leaders **reset usage limits on every WAU milestone and every outage** ("didn't matter whether it was five minutes, an hour, four hours — we would make up for that and reset everyone's rate limits" — Sottiaux). Deliberate goodwill-loop mechanics behind the WAU curve.

- ## Codex vs Claude Code — The Developer Consensus (differentiation texture)
	- | Dimension | Codex | Claude Code |
	  |---|---|---|
	  | Best when | Engineer has a **specific plan/spec to execute** | **Junior engineers / solution unknown** — anticipates intent without much context |
	  | Style | **"Relentless"** — auto-fixed a recurring bug on every server spin-up for weeks (Notion's Rau only discovered the bug via another agent) | Thinks for itself — but "goes down rabbit holes or fails to follow instructions" |
	  | Failure mode | Pursues many bugs when asked for a small change | Ignores the spec |
	  | Interface history | Desktop app Feb 2026, mobile May 2026 | Terminal-first; desktop redesign only in April (announced Nov) |
	- The Basis anecdote (sentiment texture): engineers who hit the Codex credit-card limit **bombarded the founder with Slack complaints** despite still having paid Claude Code access — one shared a GIF of "a soldier handing a gun to a monkey" (monkey = Claude Code). But "some engineers at Basis who use Claude Code frequently didn't mind" — preference is real but split.
	- Cisco (DJ Sampath, SVP/GM AI software): GPT-5.5 "significantly better… at long-running tasks without needing much guidance."
	- App-vs-terminal matters: apps win for **nontechnical users and multi-agent parallel workflows**; Notion's head of product runs tasks on his desktop and checks in from the Codex mobile app.

- ## Investment Read-Throughs
	- **The revenue asymmetry is the headline**: Anthropic **\$47B ARR growing 5× YTD** on *paid-only* coding/agent products vs OpenAI ~\$30B with 900M mostly-free consumers — quantifying the "verifiable work > consumer chat" monetization gap and explaining the superapp gambit (convert the free 900M with the Codex harness). Both need the IPO capital pools "for buying AI chips and hiring researchers."
	- **Consistent with the Dylan Patel read** ([[2026-07-16-dylan-patel-podcast...]]): SemiAnalysis stays majority-Anthropic for human-in-loop work while giving overnight tasks to Codex — matching the spec-execution vs anticipate-intent split developers describe here. The category is differentiating, not winner-take-all (same conclusion as the NBER substitution data, [[2026-07-13-emerging-market-for-intelligence-nber-llm-pricing]]).
	- **The moat is shifting to the harness + local execution**: Codex's local-with-file-access architecture and harness quality are the stated merger rationale — supports the view that application-layer scaffolding, not raw model quality, is where lab differentiation now accrues (and complicates the commodity-model thesis in [[2026-07-13-benedict-evans-token-pricing-commodity-infrastructure]]).
	- **Coding = superintelligence input**: OpenAI's fall-2024 alarm was about research velocity, not product revenue — both labs treat coding leadership as strategically existential, which explains why neither will price-discipline this category (see GPT-5.6/Sol priced at half of Fable).
	- **Watch items**: Codex WAU trajectory post-superapp (does the 900M funnel convert?); Anthropic's response on free tiers/desktop UX (its April redesign was reactive); paying-mix disclosure ahead of either IPO; whether GPT-5.6 re-widens or Claude's next release re-closes the "impossible to ignore" gap.
