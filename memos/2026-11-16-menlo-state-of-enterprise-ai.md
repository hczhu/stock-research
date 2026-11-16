tags:: [[enterprise-AI]], [[agents]], [[Anthropic]], [[OpenAI]], [[Databricks]], [[$GOOGL]], [[$MSFT]], [[$AMZN]], [[$SNOW]], [[$NOW]], [[SaaS]], [[inference]], [[ai-model:GPT-6 Astra]], [[ai-effort:high]]
file-created-at:: 2026-11-16
file-updated-at:: 2026-11-16

- ## Menlo Ventures: 2026 State of Enterprise AI

	- **Source**: Menlo Ventures, [2026: The State of Enterprise AI](https://menlovc.com/perspective/2026-the-state-of-enterprise-ai/), November 3, 2026; supplied 34-page PDF. All figures and findings below are attributed to the report.
	- **Basis**: Nearly 400 U.S. enterprise decision-makers overseeing more than $4B in AI spending; Morning Consult survey, September 8-26, 2026. Market sizes are Menlo's modeled **annualized revenue run rates**, not realized full-year totals. Prior years were reclassified to match the current taxonomy. Menlo invests in multiple companies discussed, including Anthropic, Databricks, and OpenRouter. (PDF pp. 25-27)

- ## Spending: usage expands faster than enterprise adoption

	- | Metric | Reported figures and context |
	  |---|---|
	  | Enterprise AI deployment market | \$1.7B in 2023; \$8.5B in 2024; \$33B in 2025; \$176.8B by September 2026, up 5.4x YoY. |
	  | Deployment split, 2026 | \$99.5B infrastructure, including \$94.2B foundation models/inference and \$5.3B other AI infrastructure; \$77.3B applications. |
	  | Model development, 2026 | \$102.5B, up 5.3x: \$87.2B training compute and \$15.3B training data/services. Deployment is approximately 1.7x development spending. |
	  | Enterprise adoption | 55% in 2025 to 65% in 2026. |
	  | Actual versus planned spending | Mean: 4.7x prior-year spending versus 1.9x planned; median: 2.2x versus 1.8x planned. Menlo attributes the gap to heavy-spending power users. |
	  | Funding incremental AI spending | 55% new budgets; 22% existing software budgets, comprising 13% retained by incumbents and 9% moving to AI-native vendors. |
	  | SaaS displacement | \$12.6B shifted to AI-native vendors; Menlo estimates a roughly 2-percentage-point growth headwind for the \$600B+ application SaaS market, from 13% to 11% growth. |
	  | Frontier-lab cloud demand | Anthropic and OpenAI together estimated at more than 25% of AWS, Azure, and Google Cloud revenue collectively; much of this spending supports training. |
	- **Menlo's finding**: Agents tie spending to work performed rather than headcount. The study found limited replacement of core systems such as Salesforce CRM, Workday HRIS, or NetSuite; it characterizes AI as expanding the software market while modestly slowing traditional SaaS growth. (pp. 3, 7-10)

- ## Models: frontier labs capture dollars; open-source gains tokens

	- | Metric | 2025 baseline → 2026 result |
	  |---|---|
	  | Anthropic / OpenAI / Google enterprise API spend shares | 40% / 27% / 21% → 55% / 31% / 9%; Anthropic and OpenAI combined rise from 67% to 86%. |
	  | Three frontier labs' share of all deployment spending | 50% → 69%, or $122.7B; includes their APIs and first-party apps, not only frontier-tier models. |
	  | Frontier-tier models, Q3 comparison | Share of model spending: 35% → 63%; token share: 18% → 42%. |
	  | Open-source, September comparison | Token share: 11% → 19%; spend share: 6% → 4%. Volume grows 22.5x to 2.9 quadrillion tokens/month, versus 12.1x growth for closed models. |
	  | Average token prices | Open-source falls approximately 3.3x to \$0.13 per million; closed-model blended price falls 24% to \$0.70. |
	  | Small closed models | Token share falls from 29% to 13% despite price cuts of at least 80%. |
	  | Chinese open-source models | 89% of open-source spending in 2026, per Menlo; Kimi leads at 61%. |
	  | Post-training | Adoption among AI builders: 6% → 10%; 91% of adopters use outside partners. |
	- **Menlo's finding**: Buyers prioritize capability over price at the frontier, while open-source competes more strongly for cheaper workloads. Agent caching also lowers blended token prices: cache reads can account for 95% or more of an agent's tokens. (pp. 5-14)

- ## Applications: coding leads; incumbents retain established workflows

	- | Application market / competitive measure | 2026 result |
	  |---|---|
	  | Coding | \$34.0B, up 7.7x; AI-native providers capture 96%. Claude Code and Codex together account for 70%; the rest of the market still grows 2.9x to approximately \$10.1B. |
	  | Enterprise chatbots/productivity | $25.0B, up 3.0x; enterprise Claude, ChatGPT, and Gemini capture 62%. Together with coding, this category represents 76% of application spending. |
	  | Healthcare / legal | Healthcare: \$3.7B, up 2.5x, or 37% of vertical AI; legal: \$1.8B, up 2.8x. |
	  | Customer success / sales | Customer success: \$2.7B, up 4.3x; sales: \$1.4B, up 3.6x. |
	  | IT / HR / marketing | IT: \$1.6B, up 2.3x; HR: \$0.9B, up 2.5x; marketing: \$1.2B, up 1.8x. |
	  | AI-native share | 77% of application spending versus 63% in 2025; 90% of infrastructure spending versus 44%. Excluding frontier labs, startups still capture 61% of application spending. |
	  | Incumbent category shares | IT 91%, data science 88%, HR 68%; examples include ServiceNow, Databricks/Snowflake, and Workday. These are category-wide incumbent shares, not individual company shares. |
	- **Menlo's finding**: Agents succeed where they can act in connected systems, access sufficient context, and verify outcomes. AI-native products lead workflows rebuilt around agents; incumbents remain stronger where AI fits into existing systems of record. (pp. 14-22)

- ## Agents create new infrastructure demand

	- | Usage / adoption measure | Reported result |
	  |---|---|
	  | OpenRouter agent traffic | 80% of tokens, or 130.9T/week; up 37x since overtaking human traffic in February, versus 5x growth in human traffic. This is one gateway, not all enterprise usage. |
	  | Agent use among builders | 74% use agents; 32% use multi-agent systems. The report's 2025 comparator is 27% of startup deployments, a differently described population. |
	  | Code sandboxes / search / browser infrastructure | Builder adoption, 2025 → 2026: 11% → 40%; 5% → 30%; 4% → 14%, respectively. |
	  | Databases / evaluations and observability / orchestration | Builder adoption reaches 91% / 84% / 54%, up 2 / 4 / 9 percentage points, respectively. |
	- **Menlo's finding**: Agent workloads favor parallel execution and temporary, task-specific resources, including databases, code sandboxes, search, and browsers. OpenRouter's sample skews toward individual developers and startups rather than the enterprise buyers surveyed. (pp. 4, 22-26)
