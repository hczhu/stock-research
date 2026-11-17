tags:: [[$META]], [[Sierra]], [[Muse]], [[agents]], [[agentic-commerce]], [[MCP]], [[identity]], [[$SHOP]], [[$WMT]], [[Stripe]], [[OpenAI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-17
file-updated-at:: 2026-11-17

- ## Personal Agent Protocol — Meta and Sierra's open standard for personal agents dealing with businesses
	- **Source**: Sierra blog, "Introducing Personal Agent Protocol," Bret Taylor and Clay Bavor, October 6, 2026; the October 9 update; and Sierra's follow-up post on how the protocol works, with a live demo at Sierra Summit ([demo video](https://x.com/SierraPlatform/status/2108245197440307584)).
	- **Thesis**: Meta and Sierra want a sanctioned, authenticated channel between personal agents (such as Meta's Muse) and businesses, replacing slow and failure-prone browser automation. Businesses keep control of what agents can do, and consumers control what access they grant.
	- **Participants**: an open standard anyone can implement. Meta and Sierra are developing it with Genesys, Instinct, Rocket, Shopify, Stripe and Walmart. On October 9 Sierra published a draft and added **35 design partners**, including Bank of America, OpenAI, Visa and United Airlines.
	- **Context**: Meta previewed the protocol on its Q3 call as the way a personal Muse transacts with merchants' agents. Susan Li expects authenticated APIs and approved integrations to support these interactions, with many interactions staying assisted while integrations mature ([[META-2026-Q3]]).

- ## Stakeholders and their desires
	- The post's premise: the connection is adopted at scale only if it works for every party. **Everyone wants security**, but each party also wants something different, and the protocol divides control accordingly.
	- | Stakeholder | Named participants | What they want | What the protocol gives them |
	  |---|---|---|---|
	  | **Consumers** | End users of personal agents | **Speed, dependability and trust**: the job done right the first time by an agent they can count on to act in their best interest | They decide what access their agent gets: guest only, or signed in with **read-only or write** access. Tasks that take minutes of clicking or a support call could finish in seconds |
	  | **Brands and businesses** | Walmart, United Airlines, Bank of America, Rocket (mortgages) | **Visibility and control**: knowing when a personal agent is acting for a customer, and deciding for themselves what it can do. Companies want to respect consumers' choices while protecting their privacy and security | They **set the parameters** for what agents can do and choose which routes to open (website, APIs or their own agent). They see what agents do across those routes |
	  | **Personal-agent builders** | Meta (Muse), OpenAI | **Efficiency and access**: a direct, consistent way to work with participating companies | One standard way to discover, authenticate with and act at any participating company, instead of navigating each site's pages and forms |
	  | **Commerce, payments and customer-service platforms** | Sierra, Genesys, Shopify, Stripe, Visa | The post does not state their goals separately | They sit between agents and businesses: company agents and contact centers (Sierra, Genesys), storefronts (Shopify) and payments (Stripe, Visa) |
	- The posts do not describe the role of founding partner Instinct.

- ## The problem it targets
	- Most personal agents today use websites and apps the way people do: loading pages and clicking through forms. When that fails, they call the company's support line or open its web chat. That is slow and may not finish the task. Sierra says a direct connection could do the same task securely in seconds.

- ## How it works — five building blocks
	- The protocol's short name is **Poppy**. Governing principle: customers decide what access their personal agents get, and companies set the parameters for what agents can do.
	- | Building block | Technical detail |
	  |---|---|
	  | **1. Discovery** | Each company publishes one file at a standard address, **`/.well-known/poppy.json`**. It tells agents how to interact with the company, how customers can sign in, and what the agent is allowed to do |
	  | **2. Sessions** | The agent starts a session on its customer's behalf, optionally as a **guest**, which can be enough to check stock or ask about a returns policy. **The agent always identifies itself**, so the company knows when an agent is acting for a customer |
	  | **3. Sign-in** | For account tasks, the customer signs in on the company's page through **OAuth**. If the company permits it, the agent can sign in for the customer with a **session token scoped to only the access the customer approved** (read-only or write) |
	  | **4. One session across every channel** | **The same token works for the company's APIs, its website and conversations with its agent**. A question asked before sign-in and an order change made afterward are one visit, so the customer doesn't start over and the company sees the whole journey instead of disconnected fragments |
	  | **5. Getting the job done** | The company decides which channels to offer (below) |
	- **Channels the company can offer**:
		- | Channel | How the agent uses it | Technical notes |
		  |---|---|---|
		  | Website | Browses the company's regular pages | The company applies the customer's permissions on each page |
		  | APIs | Connects through standard interfaces | Built on **OpenAPI and MCP** |
		  | Company agent | Agent-to-agent conversation for tasks that need dialogue, such as a warranty claim or an exchange | Replies can **stream** as they are written, and the company can **hold a request open** until there is news to share |

- ## Examples
	- | Channel | Scenario | What it shows |
	  |---|---|---|
	  | Website | A customer asks their agent to return a jacket. The agent finds the retailer through the protocol, identifies itself, and the customer signs in once. The agent then uses the regular returns page | The retailer knows an agent is acting for a signed-in customer, and allows it to start a return but **not change the payment details on file** |
	  | APIs | A customer's flight is canceled. The agent connects to the airline's booking tools through **MCP** with the customer's approved access and finds the next available flight | The agent **confirms the seat with the customer before booking** |
	  | Company agent (live demo) | At Sierra Summit, Rocket VP of Product Alex McGillis asked Meta's **Muse** to get him pre-approved for a mortgage. Muse went to Rocket's website, found Rocket's agent through Poppy, and asked for permission to connect. He signed in to share the credit and income details a mortgage needs. The two agents worked through purchase price, down payment and interest rate, and a **pre-approval letter was ready within moments** | A full agent-to-agent transaction between Meta's agent and a business's agent. The customer stays in control at each step while the agents do the work |
