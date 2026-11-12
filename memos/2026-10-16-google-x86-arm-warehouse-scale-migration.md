tags:: [[$GOOGL]], [[$ARM]], [[$INTC]], [[$AMD]], [[$AMZN]], [[$MSFT]], [[CPU]], [[x86]], [[ISA]], [[hyperscalers]], [[data-center]], [[semiconductor]], [[agents]], [[developer-tools]], [[Axion]], [[Google-Cloud]], [[AI-coding]], [[$NVDA]], [[Graviton]], [[Cobalt]], [[market-share]]
file-created-at:: 2026-10-16
file-updated-at:: 2026-11-12

- ## Google Makes ARM a Fleet-Wide Software Option

	- **Source**: Eric Christopher et al., *Instruction Set Migration at Warehouse Scale*, Communications of the ACM, September 23, 2026; user-provided PDF. First-party study of Google's multiyear x86-to-Arm migration, including 38,156 migration commits and a separate AI-agent benchmark. Page references below use the 18-page PDF.
	- **Thesis**: Hyperscalers are reducing the software barrier to ARM server adoption. Google's evidence suggests x86 compatibility is becoming less binding as build, testing, and rollout infrastructure becomes multi-architecture; actual CPU purchases still depend on hardware economics and workload performance, which this study does not quantify.
- ## Migration Evidence and Measured Results

	- | Measure | Reported result | What the number establishes |
	  | --- | --- | --- |
	  | ARM-compatible software coverage | About **60,000 packages**, representing **75% of Google's server CPU cycles** | Multiarch binaries are available for these workloads; **not** ARM's installed-base share or actual share of CPU execution. pp. 5, 12. |
	  | Workload concentration | Top **50 binaries** represent about **60% of running compute**; the long-tail migration spans more than **100,000 packages** | Porting only the largest services leaves substantial compute outside the eligible workload pool. p. 5. |
	  | Build/configuration changes | About **84% of migration commits**, but only **19% of lines changed** | The dominant task by commit count is configuration, not rewriting application logic; counts do not measure engineering effort. p. 7. |
	  | Application-code changes | About **1% of commits** and **less than 4% of lines changed** | Code adaptation is a small share of the measured changes, although individual fixes can be difficult. p. 7. |
	  | Conventional automation | **83.82% of commits**, representing **14.15% of lines changed** | Most commits were automated without AI; the dataset largely predates agentic coding. pp. 5, 8-9. |
	  | Automated deployment qualification | Arm-qualified applications rose from **4.8% to 78.89%** within a release-management system covering **49.6% of Google's binaries** | A scoped rollout result, distinct from fleet-wide CPU-cycle coverage. Application rollback rates fell from **1.8%** in early testing to **below 0.8%** in the final phase. p. 10. |
	  | CogniPort AI-agent benchmark | **73.5% best-of-two success** across **234 historical commits** | Each task was attempted with internally fine-tuned Gemini 3 Flash and off-the-shelf Gemini 3.1 Pro; not a single-model success rate or full-migration automation rate. p. 11. |
	  | Hardest evaluated AI category | **56% success** on test-execution-environment fixes | Environment and contextual knowledge remain bottlenecks even when local code edits are tractable. p. 11. |
- ## Earlier snapshot: Google Cloud blog, Oct 21, 2025

	- **Source**: Parthasarathy Ranganathan (VP, Engineering Fellow) and Wolff Dobson, "At Google, the future is multiarch; AI and automation are helping us get there," Google Cloud Blog, Oct 21, 2025 (user-provided PDF). It summarizes the paper's preprint, about 11 months before the CACM version above, so it shows how fast the migration and the AI agent progressed.
	- **Progress between the two snapshots**:
		- | Measure | Oct 2025 (blog) | Sept 2026 (CACM paper) |
		  | --- | --- | --- |
		  | Software migrated to Arm | **More than 30,000 applications** | About **60,000 packages**, 75% of server CPU cycles |
		  | CogniPort benchmark | **30% success** on 245 historical commits, with "no special prompts or other optimizations" | **73.5% best-of-two** on 234 commits, using fine-tuned Gemini 3 Flash plus Gemini 3.1 Pro |
		  | Hardest category: test execution environment | About **12%** (11 of 89) | **56%** |
		- *My note*: these aren't like-for-like comparisons. "Applications" and "packages" may be counted differently, and the later benchmark uses best-of-two, different models and a slightly different task set. The direction is still clear: coverage roughly doubled in under a year, and the agent's success rate more than doubled.
	- **Demand signal**: "Arm hardware fully-subscribed and more servers deployed each month." YouTube, Gmail and BigQuery were already served on Arm and x86 at the same time.
	- **Axion economics (vendor claim)**: Google's first custom Arm CPU offers "up to 65% better price-performance" and is "up to 60% more energy-efficient" than comparable instances on Google Cloud. These are marketing "up to" figures, not measured fleet cost of ownership.
	- **Default going forward**: all new applications are designed to be multiarch by default, so x86-only code stops growing.
	- **What took the time**:
		- The team expected to spend its time on floating-point drift, concurrency, intrinsics and performance. Instead, modern compilers and sanitizers had "shaken out most of the surprises."
		- Most time went to tests that overfit to x86 servers, old build and release systems, and production rollout configs. One engineer: "The majority of the difficulty was configs and boring stuff."
	- **Commit mix by group** (Figure 1; Gemini Flash classified the 38,156 commits into 16 categories; group totals and shares are my sums):
		- | Group | Commits | Share of commits | Lines changed | Share of lines |
		  | --- | --- | --- | --- | --- |
		  | Code adaptation (categories 1–5) | 378 | 1.0% | 25,392 | 3.5% |
		  | Test adaptation (6–7) | 1,579 | 4.1% | 50,835 | 6.9% |
		  | Build, deployment and infrastructure config (8–10) | 33,342 | 87.4% | 198,351 | 27.0% |
		  | Supporting processes and tools (11–16) | 2,840 | 7.4% | 458,715 | **62.4%** |
		- **Most lines went to work around the port, not the port itself**: rollbacks and cleanup (163,042 lines, 22% of the total), migration tooling (125,536) and monitoring and performance analysis (115,343).
		- **Automation was concentrated in build config**: 95% of build-config commits (63% of their lines) were automated, against 0–3% for most code-adaptation and supporting categories.
	- **CogniPort's early results by category** (Figure 6; read from bar lengths):
		- | Category | Success / attempts | Rate |
		  | --- | --- | --- |
		  | Platform-specific conditional code | 25 / 57 | 44% |
		  | Intrinsic and assembly code | 3 / 11 | 27% |
		  | Data representation and alignment | 6 / 9 | 67% |
		  | Memory model and concurrency | 0 / 1 | 0% |
		  | Performance-driven code | 0 / 1 | 0% |
		  | Test logic, data and assertions | 28 / 77 | 36% |
		  | Test execution environment | 11 / 89 | 12% |
		  | **Total** | **73 / 245** | **30%** |
		- **Design**: three nested agent loops. An orchestrator calls a build-fixer agent and a test-fixer agent. Each one edits files until its target builds or its test passes, or it gives up.
- ## Arm's share of top-hyperscaler servers: Q2 FY27 results, Nov 4, 2026

	- **Source**: Arm, Q2 FYE27 results (quarter ended Sept 30, 2026), published Nov 4, 2026; user-provided excerpt, checked against Arm's newsroom post. These figures are Arm's own and are not independently audited.
	- ^^**"Arm-based server market share at the top hyperscalers more than tripled—from 15% in calendar 2024 to more than 50% in calendar 2025. Based on current ramps across Google Axion, AWS Graviton, Microsoft Cobalt, and NVIDIA platforms, we expect that share to exceed 60% by the end of calendar 2026."**^^
	- | Period | Arm-based share of servers at the top hyperscalers |
	  | --- | --- |
	  | Calendar 2024 | **15%** |
	  | Calendar 2025 | **More than 50%** (more than 3×) |
	  | End of calendar 2026 (Arm's forecast) | **More than 60%** |
	- **Royalties**: data center royalties **doubled year over year**. Total royalty revenue for the quarter was \$670 million.
	- **Named drivers**: Google Axion, AWS Graviton, Microsoft Cobalt and NVIDIA platforms.
	- *My note*: Arm doesn't define the share. It doesn't say which hyperscalers count as "top," or whether it counts units, sockets, cores or new deployments rather than the installed base. A 15% to 50%+ jump in one year looks more like a share of new server shipments than of the installed fleet.
	- *My note*: including "NVIDIA platforms" means part of the gain is Grace CPUs shipped inside GB200/GB300 racks. That share rides on AI accelerator purchases and isn't x86 being displaced in general-purpose compute. Arm doesn't split the two.
	- *My note*: this is the market-share data the CACM paper lacks. Google's 75% of CPU cycles with Arm-ready software shows the software barrier falling. Arm's numbers suggest hyperscalers are already buying on that basis.
- ## From x86 Dependence to Mixed-Architecture Fleets

	- **Broader trend, narrower measurement**: The authors identify Amazon, Google, and Microsoft as hyperscalers migrating large codebases from x86 to ARM. Only Google's migration is quantified here; this is not an industry market-share survey. For Arm's own share figures, see the Q2 FY27 section above.
	- **Coexistence rather than a one-time replacement**: Google enables simultaneous x86 and ARM support. Its scheduler can place eligible workloads on either architecture, preserving flexibility rather than forcing every service off x86.
	- **Utilization requires breadth**: An ARM server can remain underused if only a few large applications can run on it. Porting smaller workloads lets the scheduler pack jobs across available capacity; software eligibility is therefore part of the hardware-utilization equation.
	- **Shared fixes have leverage**: Early migrations of Spanner, BigQuery, and Bigtable exposed common dependency and configuration issues. Fixing a shared dependency could unblock many applications at once, making subsequent migrations more scalable.
	- **The first transition builds reusable infrastructure**: Multiarch build/test support, release tooling, and qualification systems can support future platforms. The authors expect later ISA migrations to require less manual work; this is a forecast, not a measured cost reduction for a second migration.
- ## Automation Reduces Switching Friction, Not the Need for Validation

	- Google chose source recompilation over binary translation to maximize performance and efficiency. Mature compilers were generally not the main obstacle; failures included brittle floating-point tests, x86-specific flags and intrinsics, memory-ordering assumptions, unsupported dependencies, and stale scheduling constraints.
	- **Safe rollout is as important as code generation**: CHAMP compares ARM instances with x86 instances for errors and crashes, increases ARM exposure gradually, and removes unhealthy jobs from ARM eligibility. Combined with automated configuration changes, this eliminates manual qualification for every binary.
	- Existing sanitizers, broad tests, and a centralized monorepo made automation practical. These are important enabling conditions: organizations with fragmented repositories, weak tests, or unavailable source code cannot assume Google's results transfer directly.
	- **AI handles exceptions to fixed automation**: CogniPort uses build and test feedback to repair failures that conventional pipelines cannot resolve. Most measured migration work was already done without it; AI is an incremental accelerator rather than the demonstrated cause of the migration.
	- **Benchmark boundary**: Tasks were selected for clean reversibility and identifiable test/build targets. The authors caution that passing tests can miss incorrect fixes, and historical context or training-data overlap may make tasks easier. Deep optimization, vector code, obscure platform bugs, and hardware-provisioning judgments remain difficult.
- ## CPU Vendor Competition and Cloud Bargaining Power

	- **ARM - analytical inference**: A larger pool of portable production software reduces adoption friction and broadens the workloads ARM hardware can serve. The study does not disclose ARM licensing economics, royalties, server shipments, or resulting revenue.
	- **Intel and AMD - analytical inference**: Lower porting friction weakens x86's software-compatibility advantage and exposes more workloads to architecture-level competition. It does not establish inferior x86 performance or imminent replacement: Google's stated operating model supports both architectures.
	- **Hyperscalers - analytical inference**: Multiarch scheduling and reusable migration tools create more supplier and platform choice, potentially improving negotiating leverage and capacity utilization. The paper provides no CPU price, power-efficiency, TCO, or margin comparison, so no financial uplift can be calculated from these results. The Oct 2025 blog adds only Google's vendor claims for Axion (up to 65% better price-performance and up to 60% better energy efficiency), and says Google's Arm capacity was fully subscribed.
