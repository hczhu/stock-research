tags:: [[SaaS]], [[enterprise-software]], [[agents]], [[$CRM]], [[$NOW]], [[$HUBS]], [[$MSFT]], [[$GOOGL]], [[$AMZN]], [[$SNOW]], [[AI]], [[valuation]], [[bear-case]]

- ## "Software's Tollbooths" — Why Agent-Era SaaS Pricing Won't Compound (geninnov.ai)
	- **Source**: geninnov.ai/blog/softwares-tollbooths. All facts/arguments from this article only.
	- **Thesis**: Enterprise software vendors are erecting **new pricing "tollbooths"** — charging customers to let AI agents access data/workflows they *already license* — but this is permission-based revenue, not new functionality, and it faces structural headwinds that prior SaaS cycles didn't. "Some will land… None looks likely to compound the way 2018-vintage SaaS economics compounded."
	- **Note (same author as the memory de-commoditization memo)**: explicitly contrasts software (collapsing cost, proliferating substitutes → weak pricing) with silicon/memory (supply-constrained → strong pricing) — see [[2026-06-05-memory-de-commoditization-permanent-plateau-geninnov]].
- ## What a "Tollbooth" Is
	- "Software vendors have begun charging customers for letting AI agents access the data and workflows that the customer already pays to use" — **paying twice for the same data**
	- Examples by vendor:
	  
	  | Vendor | Tollbooth mechanism |
	  |---|---|
	  | Salesforce ($CRM) | Per-action and per-conversation pricing |
	  | ServiceNow ($NOW) | Metering via "Action Fabric" |
	  | SAP | Agent-authorization restrictions |
	  | Zendesk | Charging for successful resolutions |
	  | HubSpot ($HUBS) | Charging only for resolved conversations |
	  | GitHub Copilot ($MSFT) | Usage-based metering |
- ## Key Data Points
  
  | Metric | Value |
  |---|---|
  | 2026 hyperscaler capex (4 largest US) | **>\$725bn** this year (~2× prior year) |
  | Broader infrastructure envelope | approaching **\$1 trillion** |
  | Enterprise apps with task-specific AI agents by end-2026 | **40%** (up from a low-single-digit base) |
  | GitHub Copilot weekly operating cost | **nearly doubled** in the first months of 2026 |
  | GitHub Copilot bills | former \$10/\$39-a-month subs → "bills running into hundreds" |
  | Historical SaaS valuation | market paid **15× revenue for products, 1–2× for services** |
  | Software gross margins | high-70s → "drifting toward levels pure-play software has not traditionally accepted" |
- ## Three Structural Pressures on the Tollbooth Strategy
	- **1. Hyperscaler / model-maker competition**: AWS (Bedrock AgentCore), Google (Gemini Enterprise Agent Platform), Microsoft (Copilot Studio), Databricks (Mosaic), Snowflake (Cortex) ship equivalent agent-governance at modest-or-zero cost. "The application vendor charging for permission is competing against a free version of the same capability, shipped by a company that has every incentive to make it free and no incentive to make it expensive."
	- **2. Products–services boundary collapse**: SaaS firms build consulting capacity faster than planned; consulting firms package AI tools as products; model-makers (OpenAI deployment arm, Anthropic) embed engineers in clients. Margins compress industry-wide. Recall the old split: **15× revenue for products vs 1–2× for services** — the blend is moving toward services economics.
	- **3. Customer build threat**: "The cost of building software has fallen sharply in the past eighteen months… the skill floor for building meaningful enterprise tooling has dropped by an order of magnitude." Customers can build **thin orchestration layers** instead of paying tollbooths.
- ## The Governance Layer Has Three Competing Occupants
  
  | Layer | Motivation | Pricing stance |
  |---|---|---|
  | Application vendors ($CRM, $NOW, SAP…) | **Need revenue** | Want premium pricing (weakest position) |
  | Hyperscalers / model-makers ($MSFT, $GOOGL, $AMZN…) | Want workload + adoption | Price near-zero |
  | Customer's own engineering | Avoid lock-in/double-pay | Build viable alternatives |
	- **Only the first layer requires premium pricing** — making it the weakest competitive position in the stack
- ## Added Customer Leverage
	- **Shorter contracts**: customers sign limited-term deals expecting the landscape to shift every ~6 months
	- **Regulation**: the **European Data Act (effective Sept 2025)** grants enforceable rights to access your own data and **limits switching charges through January 2027**
	- **Coalition effect**: principle-based objections ("paying twice for the same data") spread faster than cost arguments and attract regulators
- ## Why Software Differs from Silicon & Models
	- **Silicon**: supply constraints → genuine pricing power
	- **Model-makers**: exploding TAM despite competition
	- **Software**: "The cost of producing software is collapsing. Substitutes proliferate." No supply shortage to anchor pricing discipline
- ## Investment Implications
	- **Bearish on agent-era SaaS pricing power**: tollbooths yield near-term revenue but "fail to compound like prior SaaS eras." Pressure shows up as "renewals at lower terms… pricing power that fades quarter by quarter rather than crashing" — a slow grind on multiples, not a cliff
	- **Multiple-compression risk for app-layer SaaS** ($CRM, $NOW, SAP, $HUBS): the enterprise software multiple was built on pure-software margin expansion now facing structural erosion (consistent with [[2026-06-03-nikesh-arora-ai-saas-bear-case-by-category]] and [[2026-06-03-foundation-model-pricing-power-bear-case]])
	- **Hyperscalers are the structural winners** of agent governance: $MSFT/$GOOGL/$AMZN can give it away to win workloads — bullish for infra/cloud, bearish for the app vendors trying to toll on top
	- **Disintermediation by customers + frontier labs**: the "skill floor dropped an order of magnitude" point reinforces the coding-agents disintermediation theme ([[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]]) — buyers (and labs) build thin layers instead of paying middlemen
	- **The cross-asset framing is the punchline**: same author rates *memory/silicon* a mispriced franchise (supply-constrained pricing power) while rating *app SaaS* a fading toll (cost collapsing, substitutes proliferating) — a relative-value steer toward hardware chokepoints over application software in the AI buildout
	- **Caveat**: this is a pricing-power argument, not a demand argument — agent adoption (40% of apps by end-2026) is still growing fast; the bear case is about *who captures the value*, not whether AI agents get used