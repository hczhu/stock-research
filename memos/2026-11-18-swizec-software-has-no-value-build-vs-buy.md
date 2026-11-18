tags:: [[SaaS]], [[enterprise-software]], [[vibe-coding]], [[coding-agents]], [[MCP]], [[switching-costs]], [[moat]], [[developer-tools]], [[Swizec-Teller]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Swizec Teller: software has no value, and its production cost is collapsing
	- **Source**: Swizec Teller, "[Software has no value](https://swizec.com/blog/software-has-no-value)," swizec.com, November 14, 2026. The evidence comes from the author's own team.
	- **Thesis**: Customers buy what software helps them do, not code. SaaS vendors earned their moat because software was expensive to build. As AI collapses that cost, a buyer's team can increasingly build the small slice of a vendor's product it actually uses, so the author's default becomes **buy first, then build your own as customization needs grow**.

- ## Why SaaS has worked
	- **Software is a tool with no intrinsic value**: nobody admires a bag of software. Its high production cost "bamboozled many of us into thinking code intrinsically has value."
	- **What customers actually pay a SaaS vendor for**, mapped to the sales maxim that people buy only time, money, approval or peace of mind, and status:
		- | What the buyer gets | What it saves |
		  |---|---|
		  | Moving faster by buying existing code | Time |
		  | Paying less than building their own | Money |
		  | Trusting the vendor to keep innovating | Peace of mind |
		  | Saving on training through standardized tools | Time and money |
		  | Trusting the vendor to maintain the product and keep it running | Peace of mind |
	- In the author's earlier framing, users "buy your service, not your code." Software rarely delivers status.

- ## Evidence from the author's team
	- **Build vs. buy is now a daily question**: the author looks at the team's vendors every day and asks whether to "just build the 10% of features we actually use." So far building still feels like a distraction, but the team's capacity keeps growing.
	- **Personal tools replace vendor UIs**:
		- At least **4 people** built their own tiny GitHub clone because GitHub "doesn't do PRs just the way I like."
		- Others do everything through **MCP** and never look at a vendor's UI.
	- **Output per engineer**: the team ships features every month that "a few years ago would be a whole-ass startup." One good engineer with autonomy "can out-ship entire departments" of solid engineers doing workmanlike work.

- ## Implications
	- **Stated by the author**:
		- **New sourcing default**: buy first, iterate quickly to a working solution, then build your own as customization needs grow.
		- **Integration stays hard**: "You still can't buy integration, but if you can cheaply create just what you need ...". The trailing thought implies that a custom build sidesteps the work of integrating someone else's general-purpose product.
	- **The memo's reading of the author's evidence** (interpretation, not the author's words):
		- **Feature breadth matters less**: if a buyer uses only about 10% of a product's features and that slice is cheap to rebuild, a vendor's broad feature set stops justifying its price.
		- **The UI stops being a lock-in point**: users working entirely through MCP touch a vendor's data and actions without ever seeing its interface.
		- **Pressure lands on the post-purchase stage**: the threat comes when customization needs grow after buying, which puts renewals at risk more than new sales.

- ## Related views in the repo
	- **The same author's counterweight**: in January, Teller argued that cheap code shifts value to running software, with uptime, security and accountability, which favors SaaS vendors ([[2026-01-24-swizec-future-of-software-engineering-is-sre]]). This post's "trust you to do maintenance and stay up" is that same service value.
	- **Build attempts that reverted**: a startup that vibe-coded a Jira replacement returned to Linear. AI collapsed the cost of building the interface but not the recurring cost of operating it ([[2026-07-26-vibe-coded-jira-replacement-reverts-to-linear]]).
	- **Moats outside the core feature**: DocuSign alternatives fail on edge cases and lawyers' habits, not on signing itself ([[2026-11-16-kevin-rose-signudoc-docusign-edge-cases-vs-entrenchment]]).
	- **Vendor economics**: how AI-lowered build costs change the horizontal-SaaS cost advantage ([[2026-11-11-horizontal-saas-build-vs-buy-in-the-ai-era]]).
