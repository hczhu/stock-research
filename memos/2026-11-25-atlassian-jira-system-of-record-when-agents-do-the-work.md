tags:: [[$TEAM]], [[Atlassian]], [[Jira]], [[Teamwork Graph]], [[Rovo]], [[MCP]], [[agents]], [[coding-agents]], [[system-of-record]], [[usage-based-pricing]], [[SaaS]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-25
file-updated-at:: 2026-11-25

- ## Where Jira fits when agents do the work: an Atlassian insider's view
	- **Source**: an X thread by someone who works on Atlassian's agent products, replying to questions after joining the platform (user-provided text, November 2026; the author's name isn't shown). The author acknowledges the bias: "not biased at all, right?"
	- **Thesis (the author's)**: when every engineer runs several agents, **teams** need a **system of record and coordination**: what work is prioritized, plus organization, tracing and compliance.
		- **Jira provides that whether or not anyone opens its UI**, even when all traffic goes through **MCP**.
		- **The Teamwork Graph (TWG)** accumulates shared context, so the next person or agent does better.
		- **Solo engineers** need little of this, now as before the agent era.

- ## What the author describes
	- | Topic | Detail |
	  |---|---|
	  | **Agent "factories" for maintenance work** | Much of Atlassian's own run-the-business (keep-the-lights-on) work already runs through automations and factories (**AutoDev**). Ticket-creation processes already existed for **flaky tests** and **feature-flag cleanup**, so setting up a factory was "very straightforward" |
	  | **Jira's role for teams** | A **system of record**, evolving and carrying context, plus **coordination**: "What work has our team prioritised?" Once everyone on a team runs a few agents, they need organization, tracing and compliance |
	  | **Use without the UI** | Jira's value holds "whether or not anyone opens the UI (and even when everything goes through MCP)" |
	  | **Solo engineers** | "May not need much (and didn't really need much before the agentic era either)" |
	  | **Ways in** | Some teams use the **TWG CLI** heavily, creating work items via MCP, which covers many use cases **outside Atlassian** too. Others use **Planner** for **spec-driven development from Jira** |
	  | **Shared context** | Much shared context lands in the **Teamwork Graph**, which "improves the outcome for the next person or agent" |

- ## How it fits earlier repo data
	- **Atlassian's Q3 FY2026 numbers** ([[TEAM-2026-Q3]]):
		- The **Atlassian MCP Server** has over **2M monthly active users**, up 8× since March, nearly half from enterprise customers.
		- **MCP tool calls** exceed **15M a day**, up 15× since March.
		- After adopting MCP, users create **50% more in Jira** and **75% more in Confluence**.
		- **Rovo agent automations** are up 9× YoY, and **human–agent interactions** exceed 10M a month.
		- The CEO's argument matches this thread: generated work creates more coordination work, not less.
	- **Pricing follows usage, not screens**: usage-based pricing enforcement starts in **early December 2026**. Its meters include automation, Rovo credits, indexed objects and **Teamwork Graph queries**. Management assumes no meaningful usage-based revenue in FY2027 ([[TEAM-2026-Q3]]).
	- **Earlier field notes**:
		- Jira is repositioning as the delegation, governance and audit layer for human and agent work ([[2026-07-23-atlassian-jira-rovo-agentic-workflows-field-notes]], [[2026-09-14-atlassian-governed-agents-rovo-pricing-product-expansion]]).
		- A vibe-coded Jira replacement reverted to Linear, which shows the ongoing cost of running a tracker ([[2026-07-26-vibe-coded-jira-replacement-reverts-to-linear]]).

- ## Memo's reading
	- **What it means for seat pricing**: "Whether or not anyone opens the UI" is the bull case for Jira's relevance but a risk to **seat-based** revenue. If agents do the work through MCP and the TWG CLI, value capture has to move to usage: TWG queries, automations and Rovo credits. That is why the December usage-based pricing launch matters more than the MCP user count.
	- **Team vs. solo split**: the author concedes that solo developers don't need Jira. Jira's defensible ground is **multi-person, multi-agent teams** with compliance needs, where it is already strongest. Small teams and individuals are where tools like Linear, or no tracker at all, compete.
	- **Context as the moat**: the claim that the Teamwork Graph helps "the next person or agent" is the data-gravity argument. Context that builds up across work items, specs and outcomes is harder to rebuild than a ticket UI. The TWG CLI serving use cases **outside Atlassian** shows Atlassian is willing to be an open context layer, not only a destination app.
	- **Maintenance work comes first**: flaky tests and feature-flag cleanup are repetitive, ticket-shaped, verifiable work. They are natural first targets for agent factories, consistent with coding being the sweet spot for agents ([[2026-11-23-frontier-model-rd-nonlinear-returns-coding-sweet-spot]]).
	- **Related**: [[Atlassian-TEAM-thesis]].
