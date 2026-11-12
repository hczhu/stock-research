tags:: [[$GS]], [[Goldman-Sachs]], [[Anthropic]], [[Claude-Code]], [[$MSFT]], [[GitHub-Copilot]], [[$JPM]], [[banks]], [[enterprise-AI]], [[AI-coding]], [[vibe-coding]], [[AI-costs]], [[Bloomberg]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-02
file-updated-at:: 2026-11-11

- ## Goldman limits Claude Code and GitHub coding tools to engineers
	- **Source**: Bloomberg, Todd Gillespie, "Goldman Restricts Traders and Bankers From Using Some AI Tools," Nov 2, 2026. It is based on internal guidance updated in October, a person familiar, and a Goldman spokesperson.
	- **Thesis**: a large enterprise is rationing access to agentic coding tools, for cost and risk reasons, after months of letting non-engineers use them. It is a counterweight to the view that coding agents keep spreading beyond developers. At this customer, the market for Claude Code and GitHub shrinks back toward the engineering headcount.
- ## What changed
	- **Before**: for months, bankers and traders could use **Anthropic's Claude Code** and **Microsoft's GitHub** tools for work.
	- **Now**: use is limited to **engineers**. "Strats" (the staff who straddle trading, quant research and software engineering) are exempt.
	- **Reason given**: "After a period of experimentation where we assess a variety of factors including productivity and risk management, we put them in the hands of those who are best suited to leverage them for the long term." (spokesperson Nick Carcaterra)
	- **What traders lose**: monitoring client trading flows, modeling market changes and positions, and producing written and graphic content. Some are "frustrated."
	- **A reversal of the CIO's own pitch**: as recently as July, CIO Marco Argenti promoted "vibe coding" by traders and bankers. Their prototypes were handed to one of Goldman's **12,000 engineers** to finish.
	- **Second restriction this year**: in April, Goldman cut Hong Kong staff's access to Claude, a location-specific move.
- ## Industry context in the article
	- **Banks are managing AI costs**:
		- In July, JPMorgan asked staff to match models to tasks, so the most expensive model isn't used to summarize an analyst report.
		- Bloomberg separately reports that Wall Street executives are "grappling with soaring AI bills."
	- **Goldman avoids depending on one model maker**: its in-house AI assistant combines models from OpenAI, Anthropic and Alphabet.
	- **Goldman also earns fees from AI**: it is lead underwriter on Anthropic's IPO and arranges large debt deals with Nvidia.
	- **Management still frames AI as automation**: in May, President John Waldron called Goldman a "human assembly line" that was ripe for automation.
- ## My notes
	- **The likely driver is cost, since Claude Code is now billed by usage**:
		- Since April 2026, enterprise Claude Code and Codex have been billed at list API price for usage, not as discounted seats ([[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]]).
		- At usage prices, a trader running an agent loop to watch client flows costs far more than a chatbot seat. The cost lands on budgets that never planned for it, as when Uber "maxed out its full-year AI budget just a few months into 2026."
		- *My note*: the spokesperson cited productivity and risk. Cost is my inference from the usage billing and the AI-bills context in the article.
	- **Fits the Anthropic Q3 slowdown debate**:
		- [[2026-11-10-circuit-anthropic-s1-q3-slowdown-compute-constraint]] argues Anthropic's slowdown to about 45% sequential growth came from a lack of compute, not of demand.
		- Goldman's October restriction is the other kind of evidence: enterprise buyers rationing demand on cost and risk.
		- One bank doesn't settle the debate. But if other large customers follow, Q4 growth could stay slow even after more compute comes online.
	- **Engineers keep access**:
		- Goldman's 12,000 engineers and the strats still have the tools. The narrowing affects how much the market can expand beyond developers more than current core usage.
		- Coding agents are still being treated as engineering tools at banks, not as general-purpose tools for knowledge workers.
		- Products that bring agents to non-engineers in governed, cheaper forms (Microsoft Copilot, Anthropic Cowork, Goldman's own multi-model assistant) are better placed for those users than raw coding-agent access.
	- **Microsoft and Anthropic are both affected**: GitHub and Claude Code were restricted together. This rules on the category, not on one vendor, so it isn't a share loss for Anthropic against Microsoft.
	- **Goldman's two roles**: Goldman is rationing Claude Code as a customer and underwriting Anthropic's IPO as a banker. Expect investors to raise it during the roadshow, since it bears on the quality of enterprise demand rather than on compute.
	- Related: [[2026-07-27-vibe-coding-demand-destruction-vs-saas-operating-cost]], [[2026-06-24-microsoft-copilot-cowork-usage-based-pricing-deepseek-bundling]].
