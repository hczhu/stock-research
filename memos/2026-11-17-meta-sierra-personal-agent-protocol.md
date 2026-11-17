tags:: [[$META]], [[Sierra]], [[Muse]], [[agents]], [[agentic-commerce]], [[MCP]], [[identity]], [[$SHOP]], [[$WMT]], [[Stripe]], [[OpenAI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-17
file-updated-at:: 2026-11-17

- ## Personal Agent Protocol — Meta and Sierra's open standard for personal agents dealing with businesses
	- **Source**: Sierra blog, "Introducing Personal Agent Protocol," Bret Taylor and Clay Bavor, October 6, 2026, with an October 9 update.
	- **Thesis**: Meta and Sierra want a sanctioned, authenticated channel between personal agents (such as Meta's Muse) and businesses, replacing slow and failure-prone browser automation. Businesses keep control of what agents can do, and consumers control what access they grant.
	- **Participants**: an open standard anyone can implement. Meta and Sierra are developing it with Genesys, Instinct, Rocket, Shopify, Stripe and Walmart. On October 9 Sierra published a draft and added **35 design partners**, including Bank of America, OpenAI, Visa and United Airlines.
	- **Context**: Meta previewed the protocol on its Q3 call as the way a personal Muse transacts with merchants' agents. Susan Li expects authenticated APIs and approved integrations to support these interactions, with many interactions staying assisted while integrations mature ([[META-2026-Q3]]).

- ## Stakeholders and their desires
	- The post's premise: the connection is adopted at scale only if it works for every party. **Everyone wants security**, but each party also wants something different, and the protocol divides control accordingly.
	- | Stakeholder | Named participants | What they want | What the protocol gives them |
	  |---|---|---|---|
	  | **Consumers** | End users of personal agents | **Speed, dependability and trust**: the job done right the first time by an agent they can count on to act in their best interest | They decide what access their agent gets: guest only, or signed in with **read-only or write** access. Tasks that take minutes of clicking or a support call could finish in seconds |
	  | **Brands and businesses** | Walmart, United Airlines, Bank of America | **Visibility and control**: knowing when a personal agent is acting for a customer, and deciding for themselves what it can do. Companies want to respect consumers' choices while protecting their privacy and security | They **set the parameters** for what agents can do and choose which routes to open (website, APIs or their own agent). They see what agents do across those routes |
	  | **Personal-agent builders** | Meta (Muse), OpenAI | **Efficiency and access**: a direct, consistent way to work with participating companies | One standard way to discover, authenticate with and act at any participating company, instead of navigating each site's pages and forms |
	  | **Commerce, payments and customer-service platforms** | Sierra, Genesys, Shopify, Stripe, Visa | The post does not state their goals separately | They sit between agents and businesses: company agents and contact centers (Sierra, Genesys), storefronts (Shopify) and payments (Stripe, Visa) |
	- The post does not describe the roles of founding partners Instinct and Rocket.

- ## The problem it targets
	- Most personal agents today use websites and apps the way people do: loading pages and clicking through forms. When that fails, they call the company's support line or open its web chat. That is slow and may not finish the task. Sierra says a direct connection could do the same task securely in seconds.

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
