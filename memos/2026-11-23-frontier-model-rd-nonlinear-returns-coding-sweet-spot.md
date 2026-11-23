tags:: [[OpenAI]], [[Anthropic]], [[frontier-models]], [[AI-ROI]], [[R&D]], [[coding-agents]], [[software-engineering]], [[biotech]], [[tokenomics]], [[pricing]], [[$GOOGL]], [[$META]], [[Isomorphic-Labs]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-23
file-updated-at:: 2026-11-23

- ## The nonlinear returns of frontier-model R&D: a "spindle" of global R&D and the coding sweet spot
	- **Source**: a Chinese-language infographic, "前沿模型研发的非线性回报：全球 R&D 纺锤型结构和 Coding 甜点" ("Nonlinear returns of frontier-model R&D: the global R&D spindle structure and the coding sweet spot"). It is user-provided, its author is unknown, and it is translated here.
	- **Legibility**:
		- The only copy is a low-resolution image (480×2000). Small text was read from zoomed crops.
		- Figures that reconcile arithmetically (NSF R&D shares, the generational ROI table) are reliable. Partly legible values are marked "≈", and illegible ones are left out.
	- **Thesis**: frontier-model capability needs **exponentially rising R&D**: OpenAI plus Anthropic annual R&D goes from about **\$25B in 2025** to close to **\$100B in 2026**. The commercial return per generation, though, follows an **inverted U**.
		- **Coding is the peak**: it sits at the widest part of the "spindle" of global R&D labor, with a fully digital, automatically verifiable feedback loop. That makes it the highest-ROI sweet spot, and the 2026 generation earns about **9.1×**.
		- **Beyond coding, returns collapse**: the next generation costs about \$100B and targets frontier science such as biopharma, where the AI-replaceable R&D labor pool is far smaller.
		- **No network effects**: competition leaves only a **6–12-month** window of pricing power before open-source and rival models catch up.
		- **Result**: the next generation's lifetime ROI falls to about **0.8×**. Past high ROI can't be extrapolated linearly.

- ## 1. From the internet to LLMs: from distribution channels to intelligence
	- **The market moves from S&M to R&D**:
		- | Line on the global consolidated corporate P&L | Approximate share | What AI does to it |
		  |---|---|---|
		  | Cost of goods sold (COGS) | **About 60%** of revenue | Mostly physical manufacturing, logistics and in-person services, which models can't directly replace |
		  | General and administrative (G&A) | ≈4–6% | HR, legal, finance and so on. Limited by private, non-digital context |
		  | Sales and marketing (S&M) | **About 5–7%** | **The internet era's core TAM**: ad budgets |
		  | R&D and engineering | **2.7–3.5% of global GDP**, about **\$3.0–3.5T a year** | **The LLM era's TAM**. Shaped like a spindle, with software engineering the largest, fully digital part |
	- **Opposite margin paths**: internet platforms monetized S&M budgets through ads. LLMs mainly target corporate **R&D** budgets.
		- | | Internet platforms | Large models |
		  |---|---|---|
		  | Moat | Network effects | None |
		  | Gross margin over time | Rises from about 20% to a **winner-take-all 80–85%** | Starts near **80%** during the release window, then falls to about **15–20%** as open-source and rivals arrive |
		  | Pricing power | Durable | Only in a **6–9-month window** after a frontier release |
		  | Price of equivalent capability | — | Falls about **285× a year** (≈) |
	- **The three windows don't agree**: the chart's 6–9-month window, the subtitle's 6–12 months, and the conclusion's 4–6 months differ. The model's default setting is 8 months.

- ## 2. Why coding is the biggest profit pool
	- **The method**: the infographic sorts work into five task tiers, a salary pyramid, and runs each through three filters: total R&D spend, then replaceable labor, then value replaceable by tokens. The model R&D needed to address each tier gives an **inverted-U ROI curve**.
	- | Task tier | Model R&D to address it | ROI shape |
	  |---|---|---|
	  | Frontier science and innovation | About **\$100B+** | ≈0.8×, a **loss** |
	  | Professional decisions and complex engineering | ≈\$40B | ≈6× |
	  | **Software and digital knowledge work (coding)** | About **\$25B** | **Peak**. The fullest R&D structure plus a fully digital closed loop |
	  | Administration, operations and back office | Lower | ≈4.5× |
	  | Offline services and manufacturing execution | Low | Low; constrained by COGS and the physical world |
	- **Partly illegible**: the per-tier dollar pools in the source chart can't be read reliably and are left out.

- ## 3. Four quadrants: digital context × cost-effectiveness of replacement
	- **The axes**:
		- **X**: how much of the context is digital, and whether results can be verified in a closed loop.
		- **Y**: how cost-effective it is for the model to replace the work (token cost vs. labor cost).
	- | Quadrant | Examples | Why |
	  |---|---|---|
	  | **I, the gold quadrant** (digital context and high cost-effectiveness) | **Coding and software engineering**; digital finance and quant engineering | Code, compile and CI tests are fully digital with automatic verification, and engineer pay is high (≈\$200K+). Tokens replace expensive labor |
	  | **II, high value but blocked by context** (high cost-effectiveness, private context) | Enterprise back office (G&A: HR, legal, finance); **biotech drug and materials R&D** | Valuable labor, but its context is private, physical or experimental. That is a "context wall" |
	  | **III, physical constraints** | Offline services and manufacturing execution | Bound to COGS and the physical world; not digitally replaceable |
	  | **IV, sensitive to compute cost** (digital, but low labor arbitrage) | BPO customer service; **search and social ads (Google AI Mode, Meta Muse)** | Context is digital, but the human or ad revenue being replaced is cheap per unit. For AI search, inference cost per query is said to be a large multiple of ad revenue per query (≈10–30×), which squeezes margins |
	- **Related**: on AI Mode's monetization penalty, see [[2026-11-20-mdm-seufert-alphabet-q3-ai-mode-monetization-penalty]].

- ## 4. Evidence: software engineering vs. biopharma R&D
	- **Data source**: NSF NCSES Business Enterprise R&D (BERD) 2024. Two scopes are given: strict corporate R&D budgets, with a **4.9×** gap between software and biopharma, and all-industry R&D labor, with an **18.7×** gap.
	- **Panel A, three filters on corporate R&D budgets**:
		- | Step | Software/ICT | Biopharma | Ratio |
		  |---|---|---|---|
		  | 1. Global R&D spend | **\$700B** (ICT hardware plus software) | **\$300B** | 2.3× |
		  | 2. Internal R&D labor share | about 75% → **\$525B** | about 50% → **\$150B** (the rest is outsourced or clinical) | 3.5× |
		  | 3. Digital AI-replaceable share | 70% → **\$367.5B a year** | 50% → **\$75B a year** | **4.9×** |
	- **Panel B, labor share of US business R&D** (NSF BERD 2024, Table 10):
		- | Industry | In-house R&D labor share | Labor cost / total |
		  |---|---|---|
		  | Software publishing | **81.3%** | \$67.5B / \$83B |
		  | Data processing and hosting | 79.5% | \$61.3B / \$77.1B |
		  | Computer and electronic products | 70.0% | \$91.5B / \$130.7B |
		  | All industries | 65.2% | \$479.8B / \$736.4B |
		  | Pharmaceuticals and medicines | **54.5%** | \$75.5B / \$138.5B |
		- In pharma, **45.5%** of R&D goes to outsourcing and clinical trials, which tokens don't replace.
	- *Memo calculation*: all the ratios above recompute from the stated dollar figures.

- ## 5. Diminishing returns by generation: exponential R&D, shrinking windows
	- **Model defaults**: an 8-month lead window; Gen 4 R&D at 4× Gen 3; and a 15% gross margin once followers catch up.
	- | Generation | R&D | Lead-window gross profit (8 months) | Gross profit after catch-up | Lifetime ROI | Net return |
	  |---|---|---|---|---|---|
	  | Gen 1 (chatbot) | \$2.0B | \$5.6B | \$5.4B | **5.5×** | +\$9B |
	  | Gen 2 (generalist) | \$7.5B | \$25.6B | \$24.5B | **6.7×** | +\$43B |
	  | **Gen 3 (coding sweet spot, 2026)** | **\$25B** | **\$116B** | **\$110.9B** | **9.1×** | **+\$202B** |
	  | Gen 4 (ultra, biotech; 2026E+) | **\$100B** | \$41B | \$39B | **0.8×** | **−\$19B** (about −\$20B by memo calculation) |
	- *Memo calculation*: ROI = (lead-window gross profit + post-catch-up gross profit) ÷ R&D. All four rows reproduce, within rounding.
	- **Why Gen 4 loses**: R&D quadruples, but its target markets, frontier science and biotech, have small token-replaceable pools and private-context barriers. Coding, the largest pool, was already won by Gen 3.

- ## 6. Core conclusions
	- **Investment and returns don't scale together**: frontier capability needs exponential capital (OpenAI plus Anthropic R&D from about \$25B in 2025 to about \$100B in 2026), but returns follow an inverted U. The chatbot generation spent little and earned little. Coding is the sweet spot of moderate-to-high spend and high return. Pushing into ultra domains such as biopharma means very high R&D against low direct commercial returns.
	- **The market moves from S&M to a "spindle" of R&D**: the internet monetized ad budgets (S&M at 5–7% of revenue). LLMs target R&D (2.7–3.5% of GDP, about \$3.0–3.5T a year). COGS is mostly physical, and G&A is limited by private context.
		- Coding (**81.3%** labor share, **100% digital environment**, compiler-checked closed loop) is the largest monetizable pool.
	- **Margins fall over time, and ROI doesn't carry over to the next generation**:
		- Internet margins rose to 80–85% on network effects. LLMs lack network effects: open-source and rival competition compress the exclusive lead to **4–6 months**, and the price of equal capability falls about **285×** a year (≈).
		- With next-generation R&D heading to **\$100B+**, AI-replaceable R&D labor in biopharma and similar fields is only about **\$75B a year**. That is under one-fifth of tech's \$368B and under one-eighteenth of the all-industry pool (≈\$1.4T).
		- So the prior generation's full-lifecycle ROI **can't be extrapolated linearly** to the next.

- ## 7. Risks and counterarguments
	- | # | Counterargument | Mechanism |
	  |---|---|---|
	  | 1 | **Coding becomes a general execution medium** (TAM expands) | Through "code-as-action" agents and MCP access to enterprise context, AI moves beyond R&D into G&A, S&M and even COGS |
	  | 2 | **Biotech changes the business model** | Pricing shifts from "tokens for labor hours" to **drug-patent royalties**. Example: Isomorphic Labs' pharma deals with Lilly and Novartis, with upfront payments plus up to ≈\$2.9B in milestones and royalties (≈). If AI raises clinical success rates, IP-sharing could add a new revenue layer |
	  | 3 | **Inference-cost collapse brings a Jevons effect and transaction take rates** | Inference costs fall about 70–90% a year (≈), so volume can make up for price. Agentic commerce could also earn commissions on large transaction volumes |
	  | 4 | **Reusable compute capex and AI self-improvement** | About 60–70% of cluster capex is GPUs that can be reused for the next generation's training and inference. AI-assisted chip and algorithm design (for example, DeepMind's **AlphaEvolve recovering about 0.7% of compute**) lowers next-generation training cost |

- ## 8. What to track over the next 12–24 months (the infographic's list)
	- | Signals that confirm diminishing returns | Signals that refute them (a second growth curve) |
	  |---|---|
	  | Frontier labs' R&D tops \$100B a year while enterprise ARR stays concentrated in coding (≈>60%) | Enterprise agents break through private context (supply chain, legal, finance) at meaningful penetration (≈30%) |
	  | Open-source matches new frontier models within **4–6 months**, and API prices fall **more than 70%** | Enterprise memory and knowledge layers mature enough for agents to use private context |
	  | AI-drug deals stay mostly small upfront payments, with royalties not yet realized | AI-driven efficiency keeps next-generation frontier training cost below ≈1.5× the current generation |

- ## How this fits other repo data (memo's reading)
	- **Coding as the revenue engine**: consistent with Anthropic's S-1, where Claude Code and API coding use dominate growth ([[2026-10-26-anthropic-s1-financials-compute-economics]]), and with CodeRabbit's per-engineer AI coding spend ([[2026-11-18-coderabbit-ai-coding-spend-per-engineer-agent-built-ci]]).
	- **Margin decay vs. reported margins**:
		- The claim that model margins fall to 15–20% conflicts with Anthropic's reported **85% gross margin** on serving models, and with the argument that cache reads make agentic inference unusually profitable ([[2026-11-20-kv-cache-reads-llm-inference-gross-margin]]).
		- The infographic's model treats margins after catch-up as commodity-like. So far the reported data hasn't shown that.
	- **Counterargument #1 echoes Damodaran**: his point that disruptors expand their markets ([[2026-11-19-damodaran-uber-tam-case-study-disruptors-expand-markets]]).
	- **Related**: [[2026-11-19-OpenAI-numbers]], [[2026-11-20-yao-shunyu-tsinghua-talk-model-hierarchy-rl-safety-org]], [[2026-11-19-solow-productivity-paradox]].
