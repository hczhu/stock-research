tags:: [[SaaS]], [[enterprise-software]], [[AI]], [[pricing]], [[$DDOG]], [[$NOW]], [[$TEAM]], [[ai-model:gpt-6.1-sol]], [[ai-effort:medium]]
file-created-at:: 2026-11-11
file-updated-at:: 2026-11-12

- ## Why horizontal SaaS can still beat building in-house with AI
	- **Source**: User's ten-company build-versus-buy example and the follow-up discussion. Cost and pricing scenarios are illustrative. Product examples draw on vendor documentation linked below.
	- **Thesis**: A horizontal SaaS vendor can spread development and operating costs across customers. As AI lowers the cost of an equivalent internal tool, buyers gain a cheaper alternative. Vendor cost savings can cushion the effect on profit, and competition determines how much of those savings buyers capture.

- ## Ten companies, one shared capability
	- Assume ten competing companies need the same tool for a non-core function. The tool delivers equivalent service in both scenarios, and the cost figures are all-in annual costs.
	- | Annual economics | Each company builds in-house | All ten buy from one vendor |
	  |---|---|---|
	  | Spend per customer | \$100K in internal costs | \$50K subscription |
	  | Total customer spend | \$1M | \$500K |
	  | Resources used to operate the tool | \$1M across ten internal teams | \$200K at the vendor |
	  | How the savings are split | Baseline | \$500K retained by buyers and \$300K earned by the vendor |
	- **Shared delivery creates \$800K of annual savings.** With ten buyers, prices above \$20K and below \$100K let both sides gain under these assumptions. Low incremental cost per customer widens that range. Meaningful hosting, support, or onboarding costs can still fit the model if sharing the common work saves enough.
	- **Entry and switching are separate decisions.** With \$200K of fixed annual costs and a \$50K subscription, four customers cover the vendor's costs. Before a credible vendor exists, all ten companies can keep building independently. Once it exists, each buyer has an incentive to switch if its avoidable internal costs exceed the subscription, integration and migration costs, and the value of any additional vendor risk. Prior build spending is sunk, while some internal operating costs may persist after switching.

- ## Pre-AI and post-AI cost scenarios
	- Figures are annualized and shown in **thousands of dollars per customer**. Build includes initial development spread over the tool's useful life and ongoing development. Run includes hosting, maintenance, security, and support. The vendor spreads its costs across ten buyers. Each row assumes equivalent functionality and service.
	- The pre-AI vendor earns \$30K of the \$80K in savings per customer, or **37.5%**. The illustrative post-AI subscription preserves that split wherever buying still creates savings. This assumption shows the effect of changing costs before changing bargaining power.
	- | Scenario | In-house cost (build + run) | Vendor cost (build + run) | Savings available to split | Illustrative subscription | Vendor profit per customer |
	  |---|---|---|---|---|---|
	  | Pre-AI baseline | 100 (30 + 70) | 20 (8 + 12) | 80 | 50 | 30 |
	  | Post-AI: both cut costs in half | 50 (15 + 35) | 10 (4 + 6) | 40 | 25 | 15 |
	  | Post-AI: vendor saves more in dollars | 84 (24 + 60) | 4 (1 + 3) | 80 | 34 | 30 |
	  | Post-AI: buyer saves more in dollars | 44 (12 + 32) | 12 (4 + 8) | 32 | 24 | 12 |
	  | Post-AI: internal team can run a focused tool on existing infrastructure | 12 (3 + 9) | 15 (5 + 10) | −3 | No price benefits both sides | — |
	- **A lower price can coexist with stable profit.** In the vendor-led case, the subscription drops from \$50K to \$34K, but the vendor still earns \$30K per customer because its cost falls by the same amount as the price. If buyer costs fall faster in dollars, the savings pool shrinks and the vendor's profit falls at the same split.
	- **Competition can shift the split.** In the vendor-led case, suppose a comparable rival offers \$18K after accounting for differences in migration and integration. If the incumbent matches that offer, it earns \$14K per customer even though building in-house still costs \$84K. In-house cost is one ceiling on price. A credible vendor alternative can set a much lower one.
	- **The comparison can apply to one workload.** An account can keep its core platform and bring a specific workflow in-house. For example, a Datadog customer evaluating one high-volume workload would compare the charges it can avoid with the cost of operating that workload internally. That decision can shrink the account's spend before it puts the renewal at risk.

- ## Where AI shifts the build-versus-buy decision
	- AI lowers the cost of creating a dashboard, workflow, or interface. Compare the full cost of running it, including maintenance, integrations, security, reliability, and staff time. A buyer can build the parts specific to its business while paying for the shared capabilities underneath.
	- | Company | What becomes easier to build internally | What an internal replacement would need to operate |
	  |---|---|---|
	  | Datadog | Custom dashboards, alerts, and analysis | Reliable collection, storage, and correlation of metrics, traces, and logs. At high telemetry volumes, the bill can justify a team to run selected workloads internally. [Datadog docs](https://docs.datadoghq.com/opentelemetry/correlate/) |
	  | ServiceNow | Forms, approval steps, and internal agents | Service and asset records, their dependencies, and the cross-team change and incident processes that use them. [ServiceNow docs](https://www.servicenow.com/products/change-management.html) |
	  | Atlassian | Custom views, lightweight trackers, and team automations | Shared work items and documents, with consistent relationships and permissions across teams and connected tools. [Atlassian docs](https://developer.atlassian.com/platform/teamwork-graph/what-is-teamwork-graph/) |

- ## Who captures the savings
	- AI can lower delivery costs for incumbents and development costs for new vendors. When a buyer can move a costly workflow in-house or switch it to a competitor, that option can improve its negotiating position even if most of the platform stays in place.
	- The investment question is how much customers will pay for the capabilities that remain shared. A vendor can keep winning the build-versus-buy decision while retaining a smaller share of the savings if competition improves or customers can move expensive workloads off the platform piecemeal.
