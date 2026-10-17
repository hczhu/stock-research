tags:: [[$MSFT]], [[$OKTA]], [[GitHub Copilot]], [[AI]], [[coding-agents]], [[developer-tools]], [[enterprise-software]], [[AI-productivity]], [[software-engineering]]
file-created-at:: 2026-10-16

- ## Copilot at Okta: Individual Efficiency Is Not Organizational Throughput

	- **Source**: Fei Liu and Todd McKinnon, *Beyond the Hype: The Efficiency-Throughput Gap with GitHub Copilot*, Communications of the ACM, September 17, 2026; user-provided PDF. Page references below use the 15-page PDF.
	- **Thesis**: AI coding tools can improve the developer experience without producing measurable delivery gains. Enterprise value capture depends on training, workflow integration, and organizational redesign, not license deployment alone; this study does not establish the effectiveness of current autonomous coding agents.
- ## Study Design and Evidence Boundary

	- Okta compared engineering metrics from **April-June 2024** with **September-November 2024**, following license assignments in July-September. A retrospective survey recruited 261 license holders, received 97 responses, and yielded **95 valid responses, 74 complete for before/after analysis**. Samples vary by measure. pp. 3-6.
	- This was a **single-company observational before/after study**, not a randomized experiment. Survey participants used Copilot significantly more than the overall licensed population, potentially biasing findings upward. Time savings and skill improvements are self-reported, whereas PR and code metrics come from engineering systems.
	- The evaluated features were **autocomplete and chat**. Agent mode, enterprise-code retrieval, and deeper workflow integrations require separate evaluation; the 2026 publication date must not be mistaken for a study of 2026 agents. p. 12.
- ## Measured Results

	- | Measure | Before / after or finding | Interpretation |
	  | --- | --- | --- |
	  | Weekly working hours | **44.77 → 40.83 hours**; a calculated reduction of **3.94 hours / 8.8%** | Statistically significant self-reported reduction, not measured payroll savings. p. 7, Fig. 2. |
	  | Coding and testing time | Coding saved **1.06 hours/week**; testing saved **1.56 hours/week** | Both significant; context shifting and documentation also declined significantly. p. 7. |
	  | Monthly PR output | **9.76 → 10.27 PRs**, p = **0.32** | No statistically significant throughput gain. p. 8, Fig. 3. |
	  | PR cycle time | **4.06 → 5.27 days**, p = **0.42** | No significant change; the numerical increase does not prove a slowdown. p. 8, Fig. 3. |
	  | Monthly PR reviews performed | **12.96 → 16.14 reviews** | The only PR metric with a statistically significant increase; review activity is not equivalent to shipped output. pp. 7-8. |
	  | Lines of code | No significant change in either raw or filtered LOC measures | The result persisted after filtering large, potentially non-authoring changes. pp. 8-9. |
	  | Where work time goes | About **30% coding**, **10-15% testing**, and **over 50% other activities**; juniors spent **50-70%** coding/testing versus **under 30%** for seniors | Coding acceleration addresses only part of engineering work, with exposure varying by role. p. 7. |
	  | Perceived productivity | Average **3.95/5**, from **94 respondents**; motivation and perceived skills also improved significantly | Positive sentiment coexisted with unproven output gains. pp. 7, 9. |
- ## Conclusions: What Improved and What Did Not

	- **Observed benefit accrued mainly to individuals**: Participants reported less time working and improved motivation and perceived skills. The authors interpret this as early efficiency gains and better work-life balance, rather than demonstrated organizational throughput gains.
	- **Human and process bottlenecks remained**: Communication, waiting for decisions/dependencies, company and engineering processes, and infrastructure inefficiency did not show significant time reductions. Faster code generation did not automatically remove these constraints.
	- **Task fit matters**: Users found Copilot most useful for boilerplate, function templates, queries, configuration, and testing; less useful for complex algorithms, front-end/back-end development, and human-centric work. Accuracy concerns and insufficient time/knowledge to learn the tool impeded adoption. pp. 9-10.
	- **Time alone did not close the gap**: Follow-up monitoring from **December 2024 through May 2025** still found no statistical improvement in PR or LOC output. The authors hypothesize three stages: individual efficiency, deliberate workflow-led productivity gains, and organizational optimization; the later stages were not demonstrated by this study. pp. 11-12.
	- **No significant effect is not proof of no value**: The sample may lack statistical power; PR counts ignore task complexity, and LOC mixes feature work with configuration, dependencies, and refactoring. Quality, customer outcomes, and time to market were not directly established. The study cannot justify either automatic headcount cuts or the claim that AI coding tools never improve productivity.
- ## Future Actions to Improve Adoption and Capture Value

	- | Action | Authors' recommendation or reported response | What remains to be established |
	  | --- | --- | --- |
	  | Lower access friction while tracking use | Okta removed management approval for Copilot and monitored usage | Broader access is not itself evidence of utilization or ROI. |
	  | Build task-specific skills | Share best practices, upskill developers, and teach the tool's strengths and constraints | Whether training converts perceived usefulness into measurable delivery improvements. |
	  | Redesign workflows | Align development processes and productivity expectations with AI-assisted work | Whether gains survive review, testing, dependency, and decision bottlenecks. |
	  | Reduce coordination overhead | Explore more autonomous teams, broader individual scope, and effective human-AI teaming | Proposed organizational changes, not experimentally validated remedies. |
	  | Make measurement continuous | Embed AI impact assessment in regular engineering processes; improve repository labeling, PR sizing, and identification of AI-generated code | Combine usage and sentiment with meaningful output and business outcomes rather than optimizing raw LOC. |
	  | Evaluate the next tool generation separately | Okta introduced agent mode and vibe-coding tools; the authors call for research on enterprise-code RAG, deeper integration, and longitudinal studies across organizations | The paper reports no proven throughput benefit from these newer capabilities. |
	- **Practical extension for agent rollouts (analytical inference)**: Test agents on real end-to-end workflows and track accepted work, review/rework burden, defects, and delivery lead time alongside adoption. Compare similar tasks or teams over time; do not treat generated-code volume or a favorable survey as a complete ROI measure.
- ## Software Business Economics

	- **Microsoft/GitHub - analytical inference**: Okta expanded adoption despite the output findings, illustrating that developer satisfaction can support deployment before measurable throughput gains emerge. Sustainable pricing power still needs evidence of customer value; the study provides no license-cost or renewal analysis.
	- **Okta and enterprise software - analytical inference**: Reduced reported hours are not automatically lower R&D expense or higher operating margins. Financial leverage requires translating saved effort into better business outcomes or lower actual costs, neither of which this study quantifies.
	- **Industry trend - analytical inference**: The next competitive step is integrating agents into the whole delivery process, not just improving suggestion quality. Workflow and measurement capabilities may become important complements, but the proposed adoption actions are hypotheses to test rather than guaranteed productivity gains.
