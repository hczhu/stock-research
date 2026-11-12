tags:: [[$NOW]], [[ServiceNow]], [[ITSM]], [[SaaS]], [[enterprise-software]], [[customer-experience]], [[implementation]], [[pricing]], [[Freshservice]], [[HaloITSM]], [[ManageEngine]], [[Jira Service Management]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-10
file-updated-at:: 2026-11-10

- ## ServiceNow ITSM: what practitioners say about running it
	- **Source**: two user-supplied Reddit threads, captured Nov 10, 2026. Ages are relative to capture.
		- Thread 1: "Rolling out ServiceNow soon, what should I expect from my techs? (manager to manager)", about 4 months old. The poster is a healthcare organization starting with Incident and Request Management, with a consulting partner included in the deal.
		- Thread 2: [r/ITManagers, "ITSM - Service Now"](https://www.reddit.com/r/ITManagers/comments/1pjmfe1/), about a year old, with replies up to 3 months old. A small organization (under 40 IT, dev and field staff) is choosing between ServiceNow, Freshservice, Zendesk and ManageEngine.
		- Related: [[NOW-2026-Q3]], [[2026-11-09-saas-turf-wars-incumbents-invading-adjacent-markets]], [[2026-10-27-servicenow-repvue-sales-sentiment-and-retention]].
	- **Evidence standard**:
		- Only comments describing the writer's own deployment, administration, use, purchase or migration are included.
		- Verdicts without a reason, vendor posts, broker posts, AI-written replies and advice without a stated experience were removed. Usernames are omitted.
		- All claims are self-reported and unverified. The threads invite complaints, and Thread 2's question ("is it overkill for a small team?") selects for that answer.
	- **Thesis**: practitioners describe the same trade-off across many companies.
		- **ServiceNow is only as good as the team running it.** Organizations that staff it with dedicated admins and developers (teams of 5–10 were reported) use it to automate work across the company. Organizations that staff it thinly or customize it badly end up with "a very expensive ticketing system."
		- **Running costs are high but keep customers in place.** The cost of running it is the most common complaint. It also explains the stickiness: years of customization, sunk staff investment and top-down purchasing keep customers on the platform even when users dislike it.
		- **The stock read**: these accounts don't suggest the enterprise base is at risk. They do show where ServiceNow is exposed: small and mid-size buyers, implementation quality, and resentment of the upsell. ServiceNow's Q3 moves (paying for deployments, Sweep, Flow) target exactly these complaints.
- ## The running cost: admin teams and implementation
	- | Context | Experience |
	  |---|---|
	  | ServiceNow developer since 2013; manages **10 ServiceNow developers** | A trained person "can create applications and automations very quickly." The team is always busy building Service Catalog flows that automate processes and integrations across the organization |
	  | Enterprise | A team of **7 just for ServiceNow**, always swamped |
	  | Enterprise | Multiple large teams run it, "never quite enough." It becomes "one of your **top 5 vendor spends**," and "a very costly necessary evil that never quite delivers" |
	  | Organization with a **5-person admin team** | Basic changes take months; one request has been open 18 months. Executives' report requests change fields techs depend on, so notes have to be entered in several places |
	  | Deployment done years ago | "Flows are all a mess." Three teams tried to fix it; now **5 ServiceNow developers plus an outside consultancy** are on attempt number 4 |
	  | Organization with a **one-person** team | "No real automation, just a very expensive ticketing system." Management customized it heavily instead of using it out of the box |
	  | Several employers | At most of them, at least one person spent "a big chunk of their time just maintaining it" |
	  | Fan of the platform | Worth it only with an IT team of **at least 100 people**, outside implementation help and a dedicated admin |
	  | Fan of the platform | "Takes an army to maintain … poor ROI for most organizations." As a ticketing tool, alternatives "save hundreds of thousands of dollars every year" |
	  | User | Without ServiceNow-trained staff or expensive contractors, it's "a super expensive spam email generator" |
	  | Admin (dissent) | "Not that hard to administer," but managed service providers tell customers otherwise |
	- **Implementation decides the outcome**:
		- A tech during one switch, now a manager, called it "awful." Causes: poorly defined processes, the cheapest implementation, teams in several countries with different needs, hasty training, poor documentation, and slow fixes with no budget.
		- A veteran of **three rollouts** said it is "configurable, but not customizable." As with an ERP system, the company has to change its workflows to fit the software. Without a full-time team, it accumulates technical debt.
		- A customer that went live about **10 years ago** migrated all legacy data with 1–2 hours of weekend downtime. Its new hires take ServiceNow University courses and are productive in 1–2 weeks. Users hate it at first, then forget why.
		- A rollout participant found that a test system with practice tickets before go-live helped. Features differing between releases "was a pain."
- ## Product and usability
	- An engineer who has used it at **5 companies** reported "5 completely different experiences." It is "incredibly unintuitive," and customization makes it worse.
	- The veteran of three rollouts called the interface "beyond terrible," with a CMDB that is "almost impossible to navigate."
	- Two users said the three-level request structure (request item, catalog task, SCTASK) is "annoying and confusing."
	- A long-time IT tech described early "labor pains": workflows not working, and the help desk not understanding the process. Another user found it "designed for extreme bureaucracy," which leads to burnout.
	- A user at an organization with dedicated ServiceNow staff described "loads of functionality we never use," and prefers Jira + Confluence.
	- A recent deployment described an "extremely expensive basic ticketing system … so far," disliked by end users and IT alike.
	- **One favorable comparison**: a team coming from ConnectWise found ServiceNow's built-in dashboards and reporting better, with reports staff can build themselves. They called ConnectWise "like an access database with a skin."
- ## Commercial practices: upsell, SKUs and licensing
	- **Upsell**: the veteran of three rollouts said the account team pushes implementation to a partner and "show[s] up for the upsell." Delivering what was promised to decision-makers "require[s] a new SKU," and "almost everything is a net-new add to the agreement." Costs rise "super-expensive very quickly."
	- **Modules go unused**: the same commenter said customers rarely budget for modules beyond the ITSM licenses, so they use little of the platform.
	- **Blame and sell**: one user said ServiceNow "blames 'your implementation' and then just sells you features."
	- **License true-ups**: a customer using a managed service provider said quarterly true-ups are in the contract but never done. After about 2 years the license compliance call comes, so customers should budget for an overage bill.
	- **Read**: these complaints are the customer's side of the multi-product metrics ServiceNow reports (19 of the top 20 Q3 deals included six or more products, per [[NOW-2026-Q3]]). The upsell works, but it leaves resentment that competitors can exploit at renewal.
- ## Leaving, or never buying
	- | Context | Experience |
	  |---|---|
	  | Used ServiceNow about 5 years at a previous job | Hated it, "mainly because it was supplied via an MSP and they were rubbish at actually setting up properly." At a new job, ServiceNow was never considered; chose **Halo** |
	  | Previous employer | Ran it "without a dedicated team … Went cheap. Was awful." Migrated to **Freshservice** |
	  | Recent ITSM purchase | **ManageEngine quoted 1/10th of ServiceNow's price** |
	  | Freshservice customer | ServiceNow "licensing alone is close to an ERP system for IT staff" |
	- **Bad experiences follow people to their next job**: the five-year user ruled ServiceNow out at the next employer without evaluating it.
	- **The alternatives are mostly mid-market ITSM tools**: Freshservice, Halo and ManageEngine. Atlassian JSM appears only as a personal preference (Jira + Confluence), which is weak support for the JSM point in [[2026-11-09-saas-turf-wars-incumbents-invading-adjacent-markets]].
- ## What this means for ServiceNow
	- **Running costs keep customers in place**: dedicated teams, years of customized flows and integrations, and trained staff are sunk investments. They help explain a 98% renewal rate despite poor user sentiment. The 10-developer team building flows across the organization is the expansion case working as designed.
	- **Implementation quality decides whether customers succeed**: nearly every negative account blames a cheap or poor implementation, too much customization, or no dedicated team. In Q3, ServiceNow started including deployment engineers in large AI deals, acquired Sweep to shorten implementations, and is building AI implementation agents ([[NOW-2026-Q3]]). These moves respond directly to the most common complaint. If AI cuts the admin and configuration burden, ServiceNow's biggest weakness with buyers shrinks.
	- **The low end is where ServiceNow is exposed**: small and mid-size buyers see it as overkill, and a 10× price gap with ManageEngine is hard to justify for basic ticketing. Flow, ServiceNow's self-serve service desk for teams not ready for full ITSM, targets this segment. These threads predate it or don't mention it, so they can't show whether it works.
	- **Commercial friction is a renewal risk to watch**: complaints about new SKUs, unused modules and surprise true-up bills could lead to harder renewal negotiations. They fit the declining seller sentiment in [[2026-10-27-servicenow-repvue-sales-sentiment-and-retention]], though these comments come from customers, not sellers.
- ## Limits of this evidence
	- Two threads, about 30 usable comments, all self-reported. Reddit selects for complaints.
	- Thread 2 asks whether ServiceNow suits a small team, which says little about the large enterprises that make up most of ServiceNow's ACV.
	- Thread 2 is about a year old, before Flow, AI Specialists and the Q3 deployment program.
	- Comments don't give company names, contract values or dates, so they can't be tied to churn or growth figures.
