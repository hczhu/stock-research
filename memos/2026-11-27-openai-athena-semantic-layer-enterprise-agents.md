tags:: [[OpenAI]], [[Anthropic]], [[$SNOW]], [[Databricks]], [[$PLTR]], [[semantic-layer]], [[ontology]], [[enterprise-AI]], [[agents]], [[MCP]], [[data-analytics]], [[switching-costs]], [[The Information]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-27
file-updated-at:: 2026-11-27

- ## OpenAI's "Athena": a semantic layer to make its business agents accurate and harder to leave
	- **Source**: The Information, Kevin McLaughlin and Laura Bratton, "OpenAI Preps 'Athena' Data Tool to Make its Agents More Accurate," November 24, 2026 (user-provided text). It is based on a customer and three other people who spoke with OpenAI. OpenAI had no on-the-record comment.
	- **Thesis**: OpenAI's data-analysis agent in **ChatGPT Work** isn't yet accurate enough for widespread use, at least for one customer. OpenAI is building **Athena**, a data-management platform resembling a **semantic layer**.
		- **What it does**: gives agents standard definitions of business metrics up front, such as gross vs. net revenue or active vs. paying customers, so they guess less.
		- **Competitive effect**: Athena would compete with the semantic layers of **Snowflake and Databricks**, where many enterprises currently build OpenAI agents, and with **Palantir's** ontology.
		- **A moat**: a consultant calls it an attempt to "build a bigger moat," because semantic layers are much harder to move between providers than models are.

- ## What the article reports
	- | Item | Detail |
	  |---|---|
	  | **The problem** | OpenAI launched a data-analysis agent in **ChatGPT Work** (its counterpart to Anthropic's Claude Cowork) this fall. At least one customer found it **not accurate enough** for widespread use |
	  | **Athena** | A data-management platform with "similarities to" a **semantic layer**: standard definitions of business metrics, often with plain-English descriptions |
	  | **How it works** | OpenAI is building **agents that gather, write down and keep up to date the guidance other agents need**. Agents can then follow the same business rules without working them out each time, and companies don't have to build a formal model of their business |
	  | **Not an ontology** | Different from a traditional ontology, and "isn't meant to replace one where a formal model is needed" |
	  | **Status** | Early development. No release timeframe or pricing has been given to customers |
	  | **Why it matters to OpenAI** | More accurate agents could win large deals for work such as **supply-chain management** and **finance automation** |
	- **Why agents fail on business data** (Jason Strimpel, Andersen Consulting): agents "have to work out on their own what the data means and how it fits together." "A semantic layer gives the agent that context from the start… so the agent has to guess less and [can work] faster and more accurately."

- ## OpenAI's enterprise push
	- **Business sales**: OpenAI's sales to businesses **doubled in Q3 2026** and are now **a majority of its revenue** (Greg Brockman, earlier in November).
	- **Pricing**: OpenAI is undercutting Anthropic with **bigger discounts** and **more flexible licensing**.
	- **Frontier**: OpenAI has said little about its agent development and management platform since unveiling it in February.
	- **Related**: OpenAI data points are tracked in [[2026-11-19-OpenAI-numbers]]. On the gateways, OpenAI holds about 16–22% of proprietary-model spend vs. Anthropic's 65–74% ([[2026-11-25-ai-gateway-model-mix-spend-vs-tokens-databricks-vercel-openrouter]]).

- ## The competitive landscape for business context
	- | Player | Approach | Status in the article and repo |
	  |---|---|---|
	  | **Snowflake** | Semantic layer and business-context tools. **Cortex Sense** captures business definitions and institutional knowledge for agents ([[SNOW-2026-Q2]]) | Many companies, including regulated ones, build OpenAI agents **on top of Snowflake data**. Athena could pull that business away |
	  | **Databricks** | Semantic layer and business context | Same exposure as Snowflake |
	  | **Palantir** | **Ontology**: a formal model of everything in a company and how it relates. Customers include Nvidia, Cisco and Kirkland & Ellis | Athena is explicitly "not meant to replace" a formal ontology. See [[2026-11-15-palantir-user-experiences-databricks-compute-layer]] |
	  | **Anthropic** | Gets context through **MCP** (connecting to customers' internal systems) and **Skills** (task instructions) | Puts context in the customer's existing systems rather than in an Anthropic-owned layer |
	  | **OpenAI (Athena)** | **Agent-maintained** business guidance: agents write and update the rules other agents follow | Early; no timeline or pricing |

- ## Memo's reading
	- **The lock-in strategy**: models are easy to swap, as gateway data and the Neon episode showed ([[2026-11-23-google-gemini-neon-vs-opus-rauch-personal-eval]]). Business semantics are not. Whoever holds a company's metric definitions holds the switching cost. Athena moves OpenAI from model vendor toward owning the **context layer**, the same ground Snowflake, Databricks and Palantir defend.
	- **Snowflake and Databricks**: Athena threatens their move up from storage into "helping agents understand data." But an Athena layer still has to sit on top of governed data that mostly lives in Snowflake or Databricks. The likely result is a fight over **who owns the definitions**, not over where the data is stored. That is the same issue as Snowflake's Iceberg-era fear of losing workloads while keeping the data ([[Snowflake-SNOW-thesis]]).
	- **Palantir**: Athena's "no formal model needed" pitch targets the lighter use cases where Palantir's ontology is often criticized as heavy. Palantir's deep, formal deployments are less exposed.
	- **The accuracy problem is real**: agents writing SQL against enterprise data still struggle, as text-to-SQL benchmarks show a big gap on real enterprise schemas ([[2026-10-15-text-to-sql-benchmarks-spider-bird-enterprise-gap]]). Semantic context is the standard fix, so this is a necessary product, not just a moat play.
	- **Anthropic's different bet**: MCP plus Skills leaves context in customers' systems and in portable instructions. That is easier to adopt but builds less lock-in for Anthropic. Atlassian's Teamwork Graph is a third model, a context layer owned by the work-management vendor ([[2026-11-25-atlassian-jira-system-of-record-when-agents-do-the-work]]).
