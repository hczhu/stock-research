tags:: [[$DDOG]], [[SRE]], [[AI-SRE]], [[observability]], [[incident-management]], [[on-call]], [[agents]], [[MCP]], [[reliability]], [[Rootly]], [[incident.io]], [[Resolve-AI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-19
file-updated-at:: 2026-11-19

- ## AI SRE today: on-call is changing, not disappearing
	- **Source**: user-provided newsletter excerpt, "What is changing for on-call engineers?", November 2026, based on interviews with AI SRE vendors (Rootly, incident.io, Resolve AI). The newsletter's name was not given. Rootly's figures come from a vendor whose product is the AI SRE, so they likely run ahead of the broader industry.
	- **Thesis**: Fully autonomous AI SREs are not here yet. On-call rotations remain, incidents are rising (especially AI-related ones), and agents are starting to absorb the easy incidents and the alert noise. What reaches engineers will be the hard incidents, which raises a de-skilling risk. Engineers still cannot count on a full night's sleep.

- ## Incidents are rising, led by AI systems (Rootly data)
	- Growth in incidents over two years, by category:
		- | Incident category | Growth over two years |
		  |---|---|
		  | All incidents | **2.5×** |
		  | AI-related | **4.5×** |
		  | Model-provider-related | **13×** |
		  | MCP-related | **14×** |
	- **What it implies**: production AI systems need to plan for model providers going down, and MCP integrations need more attention to reliability. With pull-request frequency and outages both rising, **pages are currently going up** for most teams.

- ## Early results from automation (Rootly's own team, last 12 months)
	- **Alerts**: **7 of 10 alerts** were closed without human intervention.
	- **After-hours pages**: down about **half**.
	- **Postmortems**: AI-drafted postmortems **more than doubled** from May to September 2026, and **81%** include at least one section written by Rootly's AI. All three AI SRE vendors draft postmortems with AI.
	- **Caveat**: Rootly sells the AI SRE and is far more experimental than most companies, possibly months or years ahead of the industry. The source expects every AI SRE vendor to prioritize reducing noisy alerts and to automate "simple" incidents, so engineers should get fewer pages eventually.

- ## What changes for on-call engineers
	- | Change | Detail |
	  |---|---|
	  | On-call stays | All the AI SRE startups say on-call rotations remain at their customers, much as engineering teams persist at heavy AI users like Anthropic |
	  | Orchestration beats raw technical skill | Chris Evans (incident.io): on-call "skews towards people who are good at managing and delegating." Writing the right PromQL query becomes "undifferentiated," while knowing what to query and how to interpret agents' answers matters more |
	  | Humans keep the judgment calls | Steven Karis (Resolve AI): choices such as five minutes of hard outage vs. 30 minutes of degraded performance are business decisions about customer impact |
	  | Only hard incidents reach engineers | Rolling back a bad deploy or undoing a feature-flag rollout is easy for agents too. What is left are the gnarly incidents and those where the AI SRE found no fix |
	  | De-skilling risk | With AI handling the easy incidents, engineers lose practice. Sylvain Kalache (Rootly AI Labs): you can't learn tennis only by watching. Rootly Academy simulates incidents in Slack with AI personas, and Uptime Labs sells incident-response training simulations |
	  | Postmortems lose learning value | AI drafts them, so engineers may learn less, while AI SRE systems may use postmortems to improve their own root-cause analysis |
	  | No full night's sleep yet | A 2025 Microsoft BUILD demo of agents fixing production while engineers slept was "somewhat smoke and mirrors." Where downtime costs money, users and credibility, agents are still too risky to be given full control |

- ## Related in the repo
	- **Datadog's AI SRE**: Bits AI SRE had **1,000 trial customers** in Q4 2025, and AI SRE monetization is a value driver in the Datadog thesis. Pricing friction is a listed risk ([[DDOG-2025-Q4]], [[Datadog-DDOG-thesis]]).
	- **More telemetry to investigate**: AI coding increases the volume of software to operate, and cheap monitoring agents widen the set of events worth investigating ([[2026-11-09-ben-congdon-agentic-monitoring-observability]]).
	- **The ironies of automation**: automation leaves operators with the rarest and hardest problems while eroding the skills needed to solve them. That matches this source's de-skilling point ([[2026-11-13-bainbridge-ironies-of-automation-ai-agents-human-oversight]], [[2026-11-15-reddit-senior-engineer-microsoft-outage-ai-system-knowledge]]).
	- **Model-provider reliability**: frontier labs' self-declared API uptime is far below the cloud standard, consistent with the 13× rise in model-provider incidents ([[2026-11-18-frontier-lab-api-uptime-vs-cloud-four-nines]]). Code is getting cheap, so value shifts to running services ([[2026-01-24-swizec-future-of-software-engineering-is-sre]]).
