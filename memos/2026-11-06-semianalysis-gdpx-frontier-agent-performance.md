tags:: [[$GOOGL]], [[$META]], [[OpenAI]], [[Anthropic]], [[AI]], [[agents]], [[benchmarks]]
file-created-at:: 2026-11-06
file-updated-at:: 2026-11-08

- ## GDPx: Frontier Agents Are Specialized, Not Dependable End to End
	- **Source**: SemiAnalysis, Max Kan, Andrew Megalaa, and Dylan Patel, *GDPx: Measuring Frontier Model Capabilities Across the Most Valuable Domains* (Nov. 1, 2026), supplied PDF and leaderboard screenshots.
	- **Thesis**: Frontier models can do useful pieces of expert work, but they still struggle to identify the controlling evidence, catch downstream consequences, and verify the finished deliverable. For enterprise buyers, the better comparison is cost per usable, reviewed output—not benchmark rank or token price alone.

- ## What GDPx Measures
	- GDPx selects 11 domains where the authors expect high returns from frontier AI, rather than weighting occupations by their share of GDP. The authors’ expectation that early AI revenue concentrates in these domains is a thesis, not a benchmark result.
	- Compared with GDPval’s more self-contained assignments, GDPx puts agents inside realistic environments where finding the right context is part of the job. The finance environment, for example, is based on a real private-equity transaction and contains roughly 4,000 anonymized files.
	- The headline score weights domains equally and reports pass@1 estimated across three attempts, not best-of-three. Grading mixes binary and partial credit across domains; models use their native agent harness where available. The overall score is neither an enterprise automation rate nor a pure comparison of base models.

- ## Model Leaders Vary by Workload
	- | Model | Overall GDPx score | Domain strengths in the report |
	  |---|---:|---|
	  | Anthropic Claude Opus 5.5 | 12.0% | Best overall; leads quant trading, hardware design, and chip design |
	  | Google Gemini 4 Carbon | 10.9% | Leads biology and narrowly leads software engineering |
	  | OpenAI GPT-6 Astra | 9.6% | Leads recursive self-improvement tasks and materials science |
	  | Meta Muse Wonder Full | 9.0% | Leads the reported cyber comparison and legal partial credit |
	- **Rankings include the effects of safety filters and tooling.** The authors rerun the comparison without cyber, biology, and alignment to illustrate how refusals can move rankings. They suggest filters may help explain Carbon’s biology lead; the benchmark does not isolate that cause. Astra’s RSI lead is evidence on sampled AI-research workflows, not proof it can autonomously build a successor.

- ## Finance and Legal: Partial Credit Is Not a Usable Deliverable
	- On the selected high-stakes tasks, finance scores were **0% under binary grading**, and legal scores were essentially at the floor. Partial scores differentiate models without showing that their work is ready to use.
	- **Finance (24 tasks):** Opus 5.5 scored **54.6% partial credit** at **\$43.32 per task**; Astra scored **52.9%** at **\$17.47**. Opus gained 1.7 percentage points at about 2.5× the benchmark run cost, with neither clearing the binary bar. These costs exclude the work of reviewing and fixing the output.
	- **Legal (20 tasks):** Muse Wonder Full led partial credit at **38.4%** versus **31.0%** for Astra. In the illustrated Series B redline, none of 20 runs produced a usable draft; all missed a way the company could bypass protections through a subsidiary.
	- **The recurring failure is judgment, not just arithmetic.** Agents can prefer an explicit figure in a stale adviser schedule over an executed agreement, miss an obligation that becomes debt at closing, or verify calculations without questioning the premise. Some also double-count adjustments or overwrite linked formulas with hardcoded values.

- ## Where Frontier Models Fail at Software Engineering
	- Datacurve found that frontier models often fix the code most directly implicated by a prompt but struggle to make the solution work across common inputs and configurations while preserving existing behavior.
	- | Mistake category | Reported share | What went wrong |
	  |---|---|---|
	  | Missed requirements around the primary request | 76% of unsuccessful rollouts | The solution fell short on requirements such as integration, preserving existing behavior, or handling edge cases. |
	  | Requirement never attempted | 24% in the reported breakdown | The model skipped the requirement entirely. |
	  | Intent misinterpreted | 23% in the reported breakdown | The model misunderstood what the requirement called for. |
	  | Requirement recognized but left incomplete | 17% in the reported breakdown | The model identified the requirement but failed to finish implementing it. |
	- Models more often wrote tests that confirmed their implementation than tests that checked the behavior the prompt requested.

	- **Git LFS partial clones:** None of 25 runs across five models passed the full task. All five Astra runs omitted files when a tag pointed to a directory, breaking parity with a full clone. Three of five Opus 5.5 runs left a helper call that triggered a second fetch, exceeding the one-fetch limit.

- ## Quant Trading and AI Research
	- **Quant trading:** 70 of 111 graded runs underperformed the reference strategy. Third Moment gave agents eight hours and graded daily P&L on hidden IEX trading days, scaling up the reference when the agent took more risk. In the public AAPL task, 10 of 12 runs earned more raw P&L than the reference, yet only two reached a reward of 0.5 and none earned full credit. Common mistakes included overfitting execution filters and increasing exposure without improving the signal.
	- **AI research:** In Extrapolate’s broken RL run, a harness instruction at 32K tokens pushed agents to submit unfinished work. Training on those rollouts yielded about one-third the mean reward of training on clean rollouts. Across 20 diagnostic attempts, models generally noticed that the changing task mix made aggregate reward trends hard to interpret, but struggled to trace the degradation to the harness. One Astra run surfaced a trace documenting the premature stop and still omitted the cause from its audit.

- ## Cyber Speed and Professional Boundaries
	- **Exploit speed:** On one access-control task from Arithmetic, GPT-5.5 took more than three hours to demonstrate the exploit. GPT-5.6 Luna and Sol took 35–50 minutes on the same task.
	- | Fleet alignment evaluation | Observed outcome | Behavior tested |
	  |---|---|---|
	  | Cybersecurity | 196 of 200 runs broke at least one rule (98%). 173 broke a rule rated severe (87%, rounded). | Staying within engagement boundaries while investigating a target. |
	  | Commercial insurance | 54 of 60 runs committed a critical violation across three renewal tasks. | Protecting confidential client information, respecting approval boundaries, and making accurate coverage claims. |

- ## Where Enterprise Value Can Show Up First
	- The results favor bounded work with independent checks: document triage, first-pass modeling, and drafting, with experts retaining sign-off on consequential decisions. For finance workflows, document precedence and formula integrity are concrete checks; more context or more inference alone does not ensure either.
	- The domain splits support evaluating and routing models by workflow rather than standardizing on the aggregate winner. The benchmark is a difficult, selected snapshot—not a forecast of when professions will be automated or a measure of vendor revenue.
