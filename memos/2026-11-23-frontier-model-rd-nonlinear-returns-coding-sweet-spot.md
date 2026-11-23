tags:: [[OpenAI]], [[Anthropic]], [[frontier-models]], [[AI-ROI]], [[R&D]], [[coding-agents]], [[software-engineering]], [[biotech]], [[tokenomics]], [[pricing]], [[$GOOGL]], [[$META]], [[Isomorphic-Labs]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-23
file-updated-at:: 2026-11-23

- ## The nonlinear returns of frontier-model R&D: a "spindle" of global R&D and the coding sweet spot
	- **Source**: a Chinese-language infographic, "前沿模型研发的非线性回报：全球 R&D 纺锤型结构和 Coding 甜点" ("Nonlinear returns of frontier-model R&D: the global R&D spindle structure and the coding sweet spot"). Author unknown; translated here.
	- **How it was read**: the user first sent a low-resolution full image, then zoomed screenshots of every section. The figures below come from the screenshots, and the arithmetic checks are memo calculations.
	- **Thesis**: frontier-model capability needs **exponentially rising R&D**: OpenAI plus Anthropic annual pure R&D goes from about **\$25B in 2025** to close to **\$100B in 2026**. The commercial return each generation unlocks has a clearly **asymmetric, inverted-U** shape.
		- **The market is R&D, not payroll**: today's LLMs target corporate **R&D budgets**, which form a "spindle" shape, not the whole payroll pyramid.
		- **Coding is the peak**: it sits at the spindle's widest part with a fully digital closed loop, making it the highest-return "golden sweet spot."
		- **Beyond coding, the pool shrinks**: in biopharma and other frontier science, the AI-replaceable R&D labor pool narrows sharply.
		- **No network effects**: rivals catch up in **6–12 months**, and the existing market faces strong price deflation.
		- **Result**: the prior generation's high ROI can't be extrapolated linearly to the next.

- ## 1. From the internet to LLMs: from distribution channels to intelligence
	- **The shift**: the market moves from **S&M** to **R&D**, and the margin path flips from "climbing on network effects" to "deflating without them."
	- **The global consolidated corporate P&L, and how far technology reaches each line** (Figure 1A):
		- | P&L line | Share of revenue | What it is | Status for AI |
		  |---|---|---|---|
		  | **COGS** | **About 68%** (**\$20T+**, offline and manufacturing labor) | Physical manufacturing, logistics and in-store service, which a purely digital model can't replace | **A long-dated option**, years out |
		  | **G&A** | About **6–8%** (internal long-tail functions) | HR, finance, cross-department approvals. Limited by non-standard processes and tacit knowledge, so deployment is slow | **Trapped by tacit context** |
		  | **S&M** | About **5–7%** (S&P 500 average about **6.2%**) | Channels and ad spend, already captured by search and social. AI replacements face inverted compute economics | **The previous internet era's core TAM** |
		  | **R&D and engineering** | About **3–4%** (globally about **\$3.0–3.5T**) | Naturally matched to intelligence. Shaped like a spindle: software engineering is the largest part and fully digital | **★ The native TAM for today's LLMs** |
		- The text box puts R&D at **2.7–3.5% of global GDP, about \$3.0–3.5T a year**. Benchmarked on R&D, the market is "narrow at both ends, wide in the middle." Reaching into corporate COGS is a long-dated option, years away.
	- **Margins: internet vs. LLMs** (Figure 1B, a "scissors" chart from month 0 to month 36):
		- | | Internet platforms | Large models |
		  |---|---|---|
		  | Starting gross margin | Low, **about 20%** | High, **about 80%** at launch |
		  | Path | Two-sided network effects → winner-take-all → margins climb and settle at **80–85%** | No network effects + open-source catch-up → margins fall to **15–25%** |
		  | Exclusive window | — | **6–9 months** of exclusive high margins after launch |
		  | Why | Pricing power and scale effects | No two-sided network-effect moat. Once rivals catch up, standardized tokens face a homogeneous price war |
		- **Token price**: the price index for equal capability falls about **285× cumulatively over two years**.
		- **The crossover**: on the chart, the two margin curves cross between month 12 (competitors catch up) and month 18.
	- **Inconsistent windows**: the exclusive window is 6–9 months in Section 1 and 6–12 months in the subtitle and Section 5. The conclusion says 4–6 months. The Section 5 model defaults to **8 months**.

- ## 2. Why coding is the biggest profit pool
	- **The method**: once the market benchmark switches from "the whole payroll pyramid" to "global corporate R&D," five task tiers form a spindle that is wide in the middle and narrow at both ends. Each tier then passes through a **replaceability filter** (labor share × digital closed loop) and a **cost-effectiveness filter**. Software and digital engineering in the middle becomes the largest capturable profit pool. Matching that against model companies' exponentially rising R&D gives an **inverted-U marginal ROI curve**.
	- **Three-stage funnel by task tier**:
		- | Task tier | Stage 1: global R&D spend | Stage 2: replaceable | Stage 3: profit pool after the cost filter | Model R&D | ROI |
		  |---|---|---|---|---|---|
		  | **Frontier science and innovation** (biotech drugs, materials science) | About **\$300B** pharma R&D (top-tier science budgets are narrow) | **\$75B** replaceable R&D (54.5% labor; wet-lab constrained) | **\$8–15B a year** (limited by long clinical-approval cycles) | About **\$100B+** | **About 0.8× (declining)** |
		  | **Professional decisions and complex engineering** (high-end hardware, complex systems) | About **\$900B** complex engineering (expert decisions and hardware R&D) | **\$240B** (high liability; human-review friction) | **\$22–30B a year** (high ticket, slow deployment) | About **\$40B** | **About 3.2×** |
		  | **★ Software and digital knowledge work (coding)** | **\$1.35T+**, the spindle's widest point (software R&D plus programming across all industries) | **\$368B–1.4T** (81.3% labor; 100% digital loop) | **\$55–80B a year** (North American \$200K salaries vs. a few cents of tokens) | About **\$25B** | **Peak 10–18×** |
		  | **Administration, operations and long-tail functions** (G&A processes, customer service and knowledge BPO) | About **\$350B** enterprise IT and digitization (mostly G&A; low R&D share) | **\$65B** (tacit context and permission walls) | **\$10–14B a year** (pressure from \$4–8/hour labor in developing countries) | About **\$8B** | **About 4.5×** |
		  | **Offline services and manufacturing execution** (COGS physical labor; free consumer tier) | **Under \$80B** of purely digital R&D (sunk in COGS) | **Under \$10B** (physically constrained; models can't act in the physical world) | **Under \$3B a year** (compute for AI search and social ads is underwater) | About **\$2B** | **Under 1.0× (underwater)** |
	- **The infographic's conclusion**: the bottom tier belongs to COGS and has no digital R&D. The lower-middle tiers are held back by tacit context and cheap labor. The top tier, pharma research, is held back by a small base and wet-lab cycles. **Only coding in the middle passes all three stages.**
	- **Two different ROI bases**: the tier chart puts coding's peak ROI at **10–18×**, while the Section 5 generational model gives the coding generation **9.1×**. The infographic doesn't say what horizon each uses.

- ## 3. Four quadrants: digital context × cost-effectiveness of replacement
	- **The axes**:
		- **X**: how complete the digital context is, and whether results can be verified automatically in a closed loop.
		- **Y**: how cost-effective it is for the model to replace the work (token cost vs. human or traditional alternatives).
	- | Quadrant | Example | Detail |
	  |---|---|---|
	  | **★ I, the golden sweet spot** (full digital loop, very cost-effective) | **Coding and software engineering** | The spindle's widest point (**\$368B–1.4T**). **81.3%** pure labor, zero-cost verification by the compiler, **ROI 10×+** |
	  | I | Quant finance and standard digital engineering | Highly paid specialists plus complete structured data. High willingness to pay and high revenue per customer |
	  | **II, high pay per unit, but blocked by tacit context or physical experiments** | Enterprise long-tail functions (G&A: HR, operations, finance) | Limited by Polanyi-style tacit context and siloed systems. Deployment is slower than the rate at which each model generation loses value |
	  | II | Biotech drugs and materials R&D | AI-replaceable R&D labor is only about **\$75B a year**. Nearly half of spend goes to wet labs and **6–10-year** clinical approval |
	  | **III, off limits: physical actions** (sunk in COGS) | Offline services and manufacturing (**COGS \$20T+**) | Sunk in operating costs with very little R&D; depends on physical interaction that a pure model can't replace |
	  | **IV, compute underwater, or low-wage arbitrage** (highly digital but uneconomic) | Entry-level knowledge BPO in developing countries | Entry-level hourly pay in India and Southeast Asia is only **\$4–8**. Labor costs less than multi-step agent tokens plus human review |
	  | IV | Free consumer ads (**Google AI Mode, Meta Muse**) | Generative compute costs **10–30×** traditional retrieval, but ad eCPM hasn't risen in step, eroding existing gross margin |
	- **The infographic's three explanations**:
		- **Why coding owns the top-right**: zero context friction plus an automatic closed loop. Codebases, Git history and terminal logs are 100% digital, and compilers and test suites give millisecond-level, zero-cost, objective verification. Add the gap between a North American engineer's \$200K+ salary and a few cents of tokens, and coding is the only large, very high-profit sweet spot.
		- **The "cost-effectiveness trap" in the bottom-right**:
			- Google AI Mode and Meta Muse cost **10–30×** more per generation than traditional retrieval or recommendation, but ad monetization hasn't risen by multiples.
			- Entry-level white-collar workers in developing countries (**\$4–8 an hour**) are still cheaper than complex multi-step reasoning tokens plus human review.
		- **The "context and physical walls" in the top-left**: enterprise G&A is held back by non-standard processes and permission silos. Biopharma R&D is only about **\$300B** in total, of which AI-replaceable labor is about **\$75B**. Nearly half the budget goes to reagents, materials and 6–10-year trials, and even very capable models can't skip physical verification cycles.
	- **Related**: on AI Mode's monetization penalty, see [[2026-11-20-mdm-seufert-alphabet-q3-ai-mode-monetization-penalty]].

- ## 4. Evidence: software engineering vs. biopharma R&D
	- **Sources**: NSF NCSES BERD 2024 and the **EU Industrial R&D Investment Scoreboard**. AI-replaceable R&D in tech and programming is **4.9× to 19×** the size of pharma R&D, depending on scope.
		- **Scope 1**: strict corporate R&D budgets, a **4.9×** gap.
		- **Scope 2**: programming labor across all industries, an **18.7×** gap.
	- **Panel A, three filters on strict corporate R&D (scope 1)**:
		- | Step | Tech (ICT) | Biopharma | Ratio |
		  |---|---|---|---|
		  | 1. Global annual R&D | **\$700.0B** (ICT software plus hardware R&D) | **\$300.0B** (global pharma R&D) | 2.3× |
		  | 2. × in-house R&D labor share (tech about 75%, pharma about 50%) | **\$525.0B** (pay for in-house R&D staff) | **\$150.0B** (excluding consumables and outsourced clinical work) | 3.5× |
		  | 3. × digital AI-replaceable share (tech 70%, pharma 50%) | **\$367.5B a year** | **\$75.0B a year** (limited by wet-lab validation) | **4.9×** |
	- **Panel B, pure labor share of in-house US R&D** (NSF BERD 2024, Table 10):
		- **Formula**: (R&D wages + benefits + stock compensation) ÷ the industry's in-house US R&D spending.
		- | Industry | Labor share | Labor cost / total R&D |
		  |---|---|---|
		  | Software publishing | **81.3%** | \$67.5B / \$83B |
		  | Data processing and hosting | 79.5% | \$61.3B / \$77.1B |
		  | Computer and electronic products | 70.0% | \$91.5B / \$130.7B |
		  | All US industries | 65.2% | \$479.8B / \$736.4B |
		  | Pharmaceuticals and medicines | **54.5%** | \$75.5B / \$138.6B |
		- **The finding**: 81.3% of software R&D budgets go directly to programmers. Only 54.5% of pharma R&D is labor; the other **45.5%** goes to physical experiments and materials.
	- *Memo calculations*:
		- All the ratios recompute from the stated dollar figures.
		- Scope 2's **18.7×** is \$1.4T (the top of coding's replaceable range in Section 2) ÷ \$75B.

- ## 5. Diminishing returns by generation: exponential R&D, shrinking windows
	- **The claim**: frontier-model profit depends on the **6–12-month** lead window before rivals catch up. When R&D heads toward **\$100B** while the newly replaceable market narrows, Gen 4's return falls off a cliff.
	- **Model settings** (adjustable sliders):
		- **Lead window**: 8 months.
		- **R&D multiplier from Gen 3 to Gen 4**: **4×** (2025's \$25B to 2026E's \$100B).
		- **Gross margin kept after followers catch up**: 15%.
		- **Counter-scenario switch**: biotech patent royalties. The default is pure token and seat sales.
	- | Generation | Description | Frontier R&D | Lead-window gross profit (8 months) | Gross profit after catch-up | Lifetime ROI | Net return | Infographic's note |
	  |---|---|---|---|---|---|---|---|
	  | **Gen 1 (chatbot)** | Basic chat, free Q&A | \$2.0B | \$5.6B | \$5.4B | **5.5×** | \$9B | Low input, low return: little B2B willingness to pay, and consumer ad compute is underwater |
	  | **Gen 2 (generalist)** | General office work, basic assistance | \$7.5B | \$25.6B | \$24.5B | **6.7×** | \$43B | Medium input, medium return: capped by cheap labor in developing countries |
	  | **Gen 3 (coding sweet spot)** | Software engineering sweet spot (**2025**) | **\$25.0B** | **\$116.0B** | **\$110.9B** | **9.1×** | **\$202B** | Medium-high input, very high return: the spindle's widest point plus a fully digital loop |
	  | **Gen 4 (ultra, biotech)** | Frontier research and the complex long tail (**2026E+**) | **\$100.0B** | \$41.6B | \$39.8B | **0.8×** | **−\$19B** | Exponential input, collapsing return: AI-replaceable R&D shrinks to \$75B, plus wet-lab barriers |
	- *Memo calculation*: ROI = (lead-window gross profit + post-catch-up gross profit) ÷ R&D. All four rows reproduce; Gen 4 is (\$41.6B + \$39.8B) ÷ \$100B = 0.81×, and a net of −\$18.6B.

- ## 6. Core conclusions
	- **R&D investment and commercial return diverge nonlinearly**:
		- Frontier capability needs exponentially rising compute and R&D capital: OpenAI plus Anthropic pure R&D goes from about \$25B in 2025 to close to \$100B in 2026. But the profit unlocked at each level follows an **inverted U**.
		- Basic chatbots cost little and earn little. **Coding is the golden sweet spot of medium-high investment and very high return.**
		- Pushing into ultra tiers such as biopharma brings very high R&D spending mismatched with low-to-medium direct commercial returns.
	- **The market benchmark moves from "the payroll pyramid" to "the R&D spindle"**:
		- The internet's market was corporate S&M (5–7% of revenue). Today's LLMs target corporate **R&D** (2.7–3.5% of global GDP, about \$3.0–3.5T a year).
		- Manufacturing and offline services are sunk in COGS, where purely digital models can't replace physical actions. Enterprise G&A is held back by tacit context. Free consumer search and social ads face inference compute that is underwater.
		- Only **coding**, at the spindle's widest point (**81.3% pure labor, a 100% digital environment, a zero-cost compiler loop**), becomes the largest monetizable profit pool.
	- **Margin scissors, and no extrapolation across generations**:
		- Internet platforms used two-sided network effects to win markets, and margins climbed with scale to 80–85%. LLMs are the opposite: the token layer lacks network effects.
		- Open-source distillation and rival competition compress the exclusive lead to **4–6 months**. The price of equal capability falls **285× in two years**, and existing-market margins keep sliding from their launch highs.
		- With the next generation's R&D heading to **\$100B+**, AI-replaceable R&D labor in pharma and similar fields is only about **\$75B a year**. That is under one-fifth of tech's \$368B and under one-eighteenth of all-industry programming's \$1.4T, and it is constrained by wet labs and clinical cycles.
		- So **the previous generation's high lifetime returns can't be extrapolated linearly to the next.**

- ## 7. Risks and counterarguments
	- **Four ways around the "diminishing marginal returns" thesis**:
	- | # | Counterargument | Type | Detail |
	  |---|---|---|---|
	  | 1 | **Coding becomes a general execution medium, breaking into SG&A and eventually COGS** | TAM expansion | Highly capable models won't stay inside the narrow programmer budget. Software engineering is moving from code completion to cross-repo refactoring and autonomous operations, and frontier agents already handle financial audits, data analysis and supply-chain scheduling by writing and running code in the background ("code-as-action"). If MCP and visual agents open up enterprises' tacit context, AI will move from the R&D line into G&A, S&M and, years out, COGS |
	  | 2 | **Biotech business model shifts from "selling tokens to save labor hours" to "royalties on drug patents"** | Business-model change | Measuring the ultra tier's ceiling by the pharma R&D wage pool (\$75B) may understate what scientific breakthroughs can capture. **Isomorphic Labs'** deals with **Lilly and Novartis** include **\$82.5M upfront**, up to **\$2.9B in milestones**, and royalties on post-launch sales. If the next generation materially raises clinical success rates or finds \$10B-class blockbusters, IP royalties break through the wage ceiling |
	  | 3 | **Inference-cost deflation triggers a Jevons effect, plus transaction commissions** | Price elasticity and monetization upgrade | Lower prices per task need not shrink the total profit pool. If hardware and algorithm gains cut delivery cost in step, and low prices expand task volume **3–5×** or more, total gross profit can still grow. Inference costs fall **70–90% a year**, so AI will eventually undercut the **\$4–8 an hour** labor floor in developing countries. If search and social AI shift to transaction commissions (**agentic commerce**), the underwater compute economics could reverse |
	  | 4 | **Compute hardware reusable across generations ("fungible capex"), and AI improving its own efficiency** | Flatter cost curve | About **60–70%** of a \$10B-scale investment is data-center and GPU hardware. When a model's weights lose value after 6–12 months, the cluster can move to inference on a **4–6-year depreciation** schedule, or to training the next generation. AI-assisted chip and algorithm design (for example, DeepMind's **AlphaEvolve freeing up 0.7% of compute**) could markedly slow the exponential rise in per-generation training cost |
	- **One factual nuance** (memo's note): the infographic says AlphaEvolve freed 0.7% of "global" compute. DeepMind's claim was about **0.7% of Google's worldwide compute** fleet.

- ## 8. What to track over the next 12–24 months
	- | Signals that confirm the thesis (marginal R&D ROI keeps falling) | Signals that refute it (a second growth curve) |
	  |---|---|
	  | Leading labs' annual R&D passes **\$100B+**, but new enterprise ARR stays concentrated in software and programming (coding **above 60%**) | Autonomous agents open up enterprises' tacit context, so finance, legal, supply chain and operations contribute **more than 50%** of net profit |
	  | After each new flagship launches, open-source models match it cheaply within **4–6 months**, forcing existing API prices down **more than 70% within six months** | Locked-in workflow state (memory, private evaluation sets, toolchains) markedly extends retention, so customers don't churn or demand price cuts even when open-source models match benchmarks |
	  | AI-drug commercial returns stay at upfront payments of tens to hundreds of millions of dollars, without a jump in clinical success rates or royalties at scale | Breakthroughs in architecture and hardware efficiency bring annual growth in next-generation frontier training cost **below 1.5×** |

- ## How this fits other repo data (memo's reading)
	- **Coding as the revenue engine**: consistent with Anthropic's S-1, where Claude Code and API coding use drive growth ([[2026-10-26-anthropic-s1-financials-compute-economics]]), and with CodeRabbit's per-engineer AI coding spend ([[2026-11-18-coderabbit-ai-coding-spend-per-engineer-agent-built-ci]]).
	- **Margin decay vs. reported margins**:
		- The claim that model margins fall to 15–25% after catch-up conflicts with Anthropic's reported **85% gross margin** on serving models. It also conflicts with the argument that cache reads make agentic inference unusually profitable ([[2026-11-20-kv-cache-reads-llm-inference-gross-margin]]).
		- The 15% post-catch-up margin in the infographic's model is an assumption. Reported results haven't shown it so far.
	- **Counterargument 1 echoes Damodaran**: his point that disruptors expand their markets ([[2026-11-19-damodaran-uber-tam-case-study-disruptors-expand-markets]]).
	- **Related**: [[2026-11-19-OpenAI-numbers]], [[2026-11-20-yao-shunyu-tsinghua-talk-model-hierarchy-rl-safety-org]], [[2026-11-19-solow-productivity-paradox]].
