tags:: [[$META]], [[Sierra]], [[Muse]], [[agents]], [[agentic-commerce]], [[MCP]], [[identity]], [[$SHOP]], [[$WMT]], [[Stripe]], [[OpenAI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-17
file-updated-at:: 2026-11-17

- ## Personal Agent Protocol — Meta and Sierra's open standard for personal agents dealing with businesses
	- **Source**: Sierra blog, "Introducing Personal Agent Protocol," Bret Taylor and Clay Bavor, October 6, 2026, with an October 9 update.
	- **Thesis**: Meta and Sierra want a sanctioned, authenticated channel between personal agents (such as Meta's Muse) and businesses, replacing slow and failure-prone browser automation. Businesses keep control of what agents can do, and consumers control what access they grant.
	- **Participants**: an open standard anyone can implement. Meta and Sierra are developing it with Genesys, Instinct, Rocket, Shopify, Stripe and Walmart. On October 9 Sierra published a draft and added **35 design partners**, including Bank of America, OpenAI, Visa and United Airlines.
	- **Context**: Meta previewed the protocol on its Q3 call as the way a personal Muse transacts with merchants' agents. Susan Li expects authenticated APIs and approved integrations to support these interactions, with many interactions staying assisted while integrations mature ([[META-2026-Q3]]).

- ## The problem it targets
	- Most personal agents today use websites and apps the way people do: loading pages and clicking through forms. When that fails, they call the company's support line or open its web chat. That is slow and may not finish the task. Sierra says a direct connection could do the same task securely in seconds.
	- Adoption at scale requires the connection to work for all three parties:
		- | Party | What it wants |
		  |---|---|
		  | Consumers | Speed, dependability and trust: the job done right the first time by an agent acting in their interest |
		  | Brands | Visibility and control: knowing when an agent acts for a customer, and deciding what it can do |
		  | Personal-agent builders | Efficiency and access: one direct, consistent way to work with participating companies |

- ## How it works
	- **Governing principle**: consumers decide what access their agents get, and companies set the parameters for what agents can do.
	- **Session flow**:
		- 1. **Discovery**: the agent starts on the company's website to learn what it offers and how to reach it.
		  2. **Guest session**: the agent opens a session for its user. Guest access can cover tasks such as checking product availability or asking about a returns policy.
		  3. **Authenticated session**: tasks that need the customer's account require sign-in, either on the company's page or with credentials already set up with the personal agent. The customer chooses **read-only or write access**.
		  4. **Continuity**: the session is built on **OAuth** and carries across channels, so a question asked before sign-in and an order change made after it belong to the same visit.
	- **Execution routes**: the company chooses which routes to expose, and the agent connects to them the same way at every company:
		- | Route | How the personal agent uses it |
		  |---|---|
		  | Website | Navigates the company's regular web pages |
		  | APIs | Connects through interfaces built on standards such as **MCP and OpenAPI** |
		  | Company agent | Works through tasks that need conversation with the company's own agent, such as a warranty claim |
	- **Business visibility**: the protocol is designed to handle authentication and give companies visibility into what personal agents do through their websites, APIs or company agents.
