- tags:: [[$PRX.AS]], [[Prosus]], [[enterprise-AI]], [[agents]], [[AI-productivity]], [[inference]], [[model-routing]], [[MCP]], [[SaaS]], [[automation]], [[e-commerce]], [[open-source]], [[governance]]
  file-created-at:: 2026-05-13
- **Source**: Prosus, [The Coming Age of AI Colleagues](https://www.prosus.com/~/media/Files/P/prosus-corp-v2/documents/the-coming-age-of-ai-colleagues.pdf), May 2026
- **Evidence base**: Prosus analyzed adoption across more than **40,000 employees** and **60,000 internally created agents** on its Toqan platform over roughly 18 months. The portfolio spans food delivery, e-commerce, travel, payments, and other consumer-internet businesses.
- **Thesis**: Enterprise-agent value follows a steep power law. Broad experimentation is necessary, but a tiny group of deeply integrated, widely adopted agents creates most of the measurable value. The likely winners are companies that own proprietary workflows and data, plus platforms that discover, govern, evaluate, and route agents—not vendors selling undifferentiated access to a single model.
- ## Bottom line
	- Prosus presents unusually large-scale evidence that agent adoption can move from individual productivity to material operating outcomes: revenue creation, order growth, retention improvement, booking conversion, and labor-time savings.
	- The strongest signal is concentration. Only about **2%** of active agents are classified as outliers, while another **13%** have high potential. Agent count therefore overstates economic progress unless accompanied by adoption, quality, and business-value measures.
	- The report is positive for Prosus as an operator: its portfolio can reuse a common AI platform across data-rich commerce businesses while preserving local experimentation. The potential moat is the feedback loop among proprietary data, workflow integration, employee adoption, and measured outcomes—not the underlying foundation model.
	- The read-through for model vendors is mixed. Frontier models retain value for complex, long tool chains, but most routine tasks are already served by several "good enough" models. Centralized model routing should increase price competition even as model stickiness slows switching.
	- Rising usage, longer contexts, and sequential tool calls support continued inference demand. However, caching, compaction, parallel tool execution, and cheaper model routing can reduce compute per completed task, so token growth does not translate mechanically into supplier margins.
- ## Scale and adoption
	- Prosus says Toqan expanded from zero to **60,000+ agents** in about **18 months**, with adoption accelerating in the second half of 2025.
	- Employees built agents for **54 distinct tasks** rather than converging on one dominant use case.
	- The three largest departmental categories were **data analytics and market intelligence at 18%**, **operations at 15%**, and **personal assistants at 14%**.
	- High- and low-complexity agents each accounted for roughly half of daily active usage in early 2026. Simple assistants remain useful, but complex agents are not a niche experiment.
	- More capable agents reached more people:
		- **Senior** agents: **19,500 employee users**.
		- **Mid-level** agents: **8,120 employee users**.
		- **Junior** agents: **7,529 employee users**.
		- **Intern-level** agents: **2,360 employee users**.
	- Prosus defines intern agents as low-complexity workflows using zero to three tools; mid-level agents use four to ten tools; senior agents use eleven or more tools and/or handle very complex work.
- ## What employees actually automated
	- | Task | Share of agents | Why it matters |
	  |---|---:|---|
	  | Review large datasets | 9.6% | Self-service analysis is the largest single use case; data access and governance become key control points |
	  | Review or triage messages, reviews, and feedback | 7.8% | High-volume unstructured text is an early automation wedge |
	  | Produce marketing content | 4.3% | Content creation is common but relatively commoditized |
	  | Personal document or text assistant | 3.5% | Horizontal assistants create broad usage but may be hard to value precisely |
	  | Vendor-facing assistant | 3.2% | Agents extend beyond employees into partner workflows |
	  | Product-lifecycle automation | 3.2% | Workflow integration matters more than standalone chat quality |
	  | Coaching and employee growth | 3.1% | Internal knowledge can become an interactive service |
	  | SQL and Databricks support | 3.1% | Natural-language access increases the value of governed data platforms |
	  | Financial forecasting and scenario planning | 2.8% | Higher-value analytical work is entering the agent stack |
	  | Scheduling and meeting management | 2.5% | Basic assistants remain a meaningful part of demand |
	- Prosus observed **20 default use cases** emerging independently across businesses and geographies, including demand forecasting, churn prediction, customer-loss analysis, sales assistance, fraud detection, supplier risk, contract and invoice review, competitor monitoring, internal research, coding, onboarding, and product management.
	- This convergence suggests that enterprise agent platforms can productize reusable templates, but local data, permissions, and operating context still determine whether a template becomes valuable.
- ## The power law of agent value
	- Prosus divides active agents into four groups: roughly **2% outliers**, **13% high potential**, **71% limited growth potential**, and **14% low value**.
	- Most active agents served fewer than **100 users** and processed fewer than **10,000 requests**. A small number reached thousands of employees or hundreds of thousands of requests.
	- At Prosus's scale, the high-potential group still contains about **1,600 agents**, which creates a portfolio-management problem: management must identify which agents deserve integration, engineering support, and production controls.
	- Prosus ranks high-potential agents using **45% business value**, **35% adoption**, and **20% quality and consistency**, with a cap preventing any one dimension from dominating the score.
	- This framework is strategically important because raw activity can be misleading. A heavily used assistant may save little money, while a narrowly used revenue or fraud agent can create disproportionate value.
- ## Reported operating outcomes
	- | Agent or workflow | Reported outcome | Evidence interpretation |
	  |---|---:|---|
	  | AI-operated third-party affiliate marketplace | **$83M projected annual revenue** | Forward estimate rather than audited realized revenue |
	  | Support for long-tail small restaurants | **119% more orders** and **73% higher retention** | Material marketplace outcome; causality and control-group design are not disclosed |
	  | Vacation-rental customer Q&A | Users who chatted had a **138.3% higher booking rate** | Strong correlation, but self-selection may contribute |
	  | Grocery insights agent | Average employee saved **46 workdays per year** | Large productivity claim; depends on time-saved methodology |
	  | Portfolio-wide productivity agents | More than **1,000 FTE-equivalents** of time saved | Time capacity is not identical to cash cost reduction |
	- Among productivity agents, **82%** saved less than **20 hours per month**, **17%** saved between **20 and 173 hours**, and fewer than **1%** generated the equivalent of thousands of hours per month.
	- Among directly monetized agents, most generated less than **\$1M** of annual value, a middle tier generated **\$1M–\$10M**, and only a few reached tens of millions.
	- The distribution reinforces the central conclusion: average-agent economics are not a useful proxy for portfolio value.
- ## Prosus read-through
	- The common Toqan layer gives Prosus a way to spread platform engineering, model access, security, and training costs across multiple portfolio companies while leaving business-line leaders responsible for ROI.
	- The portfolio is well suited to agents because food delivery, travel, payments, and e-commerce contain repeated decisions, high-volume support interactions, supplier relationships, transaction data, and measurable conversion funnels.
	- Prosus recommends bottom-up business-line ROI rather than a centrally imposed model. That aligns accountability with the managers who can verify revenue, retention, cost reduction, or time savings.
	- The highest-value opportunity is not necessarily headcount removal. Agents can extend service to previously uneconomic customer segments, as illustrated by the long-tail restaurant example.
	- The key diligence issue is conversion from time saved to economic value. Capacity released by an agent benefits shareholders only if it raises output, avoids hiring, improves service, or reduces actual expense.
	- Prosus's disclosures are strategically encouraging but not sufficient to quantify group earnings impact. The report does not provide total platform cost, portfolio-wide incremental revenue, agent-level contribution margins, or independently audited ROI.
- ## Model and infrastructure economics
	- Toqan offers **10 models** to more than **40,000 employees**, making Prosus an enterprise-scale multi-model buyer rather than a captive customer of one lab.
	- Prosus calls Claude Sonnet 4 the only recent "big bang" model introduction on its platform and reports diminishing practical gains from subsequent releases.
	- Its conclusion is that most leading models are good enough for most agent tasks; frontier performance matters mainly for complex workflows with many sequential tool calls.
	- Prosus found Kimi K2.5 broadly competitive in tool chains but weaker at code execution. This supports the view that open and Chinese models can pressure pricing without fully replacing frontier models in every workload.
	- Employees rarely switch models after an agent works, even when a cheaper model could handle the task. This behavioral stickiness supports incumbent model economics, but an enterprise routing layer can eventually make substitution invisible to the user.
	- Open-source inference is not automatically cheap: 24/7 reliability, redundancy, scaling, and operations can offset lower model-access costs.
	- Token consumption is trending upward, yet Prosus found no simple relationship between tokens per question and cost per million tokens. Model mix, caching, context management, and workload complexity all matter.
	- Toqan's cost controls include parallel tool calls, within-conversation caching, and context compaction when a session reaches **60%** of the model's maximum input.
	- Investment read: inference volumes can grow rapidly while price per task falls. Infrastructure demand remains supported, but value capture may shift toward the orchestration layer and the lowest-cost reliable capacity provider.
- ## Workflow SaaS and systems-of-record read-through
	- Prosus integrates company-controlled MCP connections for tools including Attio, Linear, Miro, and Monday.com.
	- This is a mixed signal for application software. Agents can reduce the value of an application's user interface, but the underlying system of record, permissions, structured data, and transaction APIs become more important.
	- Vendors that expose safe, granular, auditable tools can remain essential infrastructure. Vendors that rely mainly on human seat engagement or workflow friction face greater disintermediation risk.
	- Prosus warns that vendor MCPs are often too broad and community MCPs can be unsafe. Its internal MCP engine can expose only a few approved tools from a much larger schema.
	- Governance therefore becomes product functionality: least-privilege access, approval gates, audit logs, evaluation, and rollback are prerequisites for production deployment.
- ## Architecture lessons
	- Prosus argues that multi-agent systems are unnecessary for most use cases because errors compound, evaluations become harder, and autonomous sub-agents may bypass access controls.
	- Its preferred pattern is a lead agent that treats sub-agents as tools and aggregates approvals. This favors explicit orchestration and observability over unconstrained agent swarms.
	- A first long-term-memory implementation using Mem0 failed after about a month because it stored too much, memory grew rapidly, and users preferred prompt or reference files.
	- Prosus then built PropMem, which extracts durable facts from whole sessions and uses a second model to verify them. The lesson is that memory quality and deletion policy matter more than raw retention.
	- Existing databases and ERP systems can become orchestration layers, strengthening platforms that already own clean enterprise data and permissions.
- ## Adoption playbook
	- Prosus attributes rapid adoption to CEO sponsorship, company-level objectives, and tying outcomes to bonuses and promotions—not merely making a chat tool available.
	- Each department needs internal ambassadors plus roughly **one to three full-time technical support specialists**, depending on organizational size.
	- Internal peers and power users were more effective adoption catalysts than outside consultants because they understood local workflows and could demonstrate credible examples.
	- At iFood, a co-creation assistant helped **1,300 employees** build more than **10,000 agents**.
	- Other mechanisms included prompt training, video walkthroughs, a marketplace of reusable agents, biweekly executive reviews, and contests with prizes ranging from **\$1,000 to \$25,000**.
	- The report's implicit message is that distribution and change management are part of the product. Model quality alone does not produce enterprise adoption.
- ## Evidence quality and unanswered questions
	- Prosus is both the platform operator and the report author. The data is valuable first-party evidence, but the financial outcomes are self-reported and not independently audited.
	- The analysis covers Prosus's own portfolio, which is unusually digital, transaction-rich, and centrally influenced. Results may not transfer directly to regulated, asset-heavy, or less digitized companies.
	- Agent classifications and ROI estimates depend on internal methodologies. The report gives useful scoring weights but limited detail on baselines, control groups, confidence intervals, and persistence of gains.
	- Some headline outcomes are projections or correlations rather than realized causal results. They should inform hypotheses, not be inserted directly into an earnings model.
	- The most important future disclosures would be production-agent survival rates, realized revenue versus projected value, cash-cost savings, inference cost per completed workflow, and portfolio-company margin impact.
- ## Research process insight
	- Prosus used GPT-5-mini to decompose prompts and OpenAI's text-embedding-3-small model with **1,536-dimensional embeddings** to cluster agent use cases.
	- The first automated taxonomy performed poorly on specialized tasks. Human researchers first defined categories, then used AI to classify agents within them.
	- This is itself an enterprise-AI lesson: human-designed structure plus machine-scale classification can outperform fully automated discovery when domain context is specialized.
- ## Links to related notes
	- [[2026-04-13-enterprise-ai-agents-field-notes]]
	- [[2026-05-03-critical-steps-for-implementing-ai-agents-in-large-enterprises]]
	- [[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]]
	- [[2026-06-12-agent-clearinghouse-thesis-source-of-permission]]
	- [[2026-07-30-ontologies-ai-agents-semantic-web]]
