- tags:: [[AI]], [[agents]], [[evaluation]], [[EBR-bench]], [[Epoch-AI]], [[continuous-learning]], [[reinforcement-learning]], [[post-training]], [[inference]], [[human-in-the-loop]], [[enterprise-software]], [[OpenAI]], [[Anthropic]], [[Google]], [[$MSFT]], [[$GOOG]], [[$AMZN]]

- ## EBR-Bench — Frontier AI Does Not Yet Learn Reliably From Experience
	- **Source**: [Epoch AI, “AI Doesn't Get Better at This Board Game With Practice”](https://epoch.ai/publications/earthborne-rangers-benchmark), Benjamin Ou and Greg Burnham, July 1, 2026; user-provided PDF. [Benchmark methodology](https://epoch.ai/benchmarks/ebr-bench).
	- **Core thesis**: Frontier models can start unfamiliar tasks at a respectable level, but repeated execution, persistent notes, explicit performance feedback, and large inference budgets do not necessarily produce on-the-job learning. On EBR-Bench, newer models score better than older ones because they begin stronger—not because their improvement curves are steeper.
	- **Investment takeaway**: The result is bearish for near-term claims that general-purpose agents can be deployed into novel workflows and autonomously improve through experience. It is comparatively bullish for curated post-training, domain data, human supervision, eval/observability tooling, workflow software, and continued training compute: capability gains still appear to be baked into model weights and harnesses before deployment rather than reliably discovered during inference.
	- **Evidence boundary**: This is one obscure board game run through a simple ReAct harness. It is a strong counterexample to broad claims of reliable experiential learning, not proof that AI cannot learn from experience in any environment.

- ## What EBR-Bench Measures
	- Earthborne Rangers is a relatively obscure, mostly text/card-based campaign game requiring both strategic deck construction and tactical turn-by-turn resource management.
	- The game was selected to reduce training-data familiarity, minimize vision/spatial reasoning as the bottleneck, and force long-horizon decisions across layered strategy and tactics.
	- One evaluated five-day segment takes experienced humans approximately **2–4 hours per playthrough**; mastering the full game can require dozens of attempts.
	- Models play **10 or 30 times**, depending on the setting. They receive a compressed rulebook, full rule references, a card database, a map, pathfinding support, and a persistent notes directory.
	- Agents are told that only the **final 20% of playthroughs** determine their score, leaving the first 80% explicitly available for exploration and learning.
	- Each playthrough can earn up to **21 objectives**. The best human result observed by Epoch was **20/21**.
	- Most models compact context every **250K tokens**. Epoch found that larger compaction thresholds made little difference.
	- The primary score is the average result over the final 20% of a run—for the standard ten-playthrough setup, the final two games.

- ## Key Results and Data Points
	- | Finding | Measured result | Interpretation |
	  |---|---:|---|
	  | Repeated practice | Scores remain roughly flat across as many as 30 playthroughs | Models do not convert experience, errors, or persistent notes into sustained improvement |
	  | Expert benchmark | 20 objectives out of 21 | Frontier agents remain far below expert performance |
	  | Model progress over time | GPT-5.5 and Opus 4.8 outperform GPT-5 and Opus 4.1 | Progress comes from higher starting competence, not stronger in-run learning |
	  | Expert fatigue | Approximately 0.6 fatigue per round | Supports roughly 15 playable rounds per in-game day |
	  | Random fatigue | Approximately 3.5 per round | Supports roughly 5.3 rounds per day |
	  | GPT-5.5 / Opus 4.8 fatigue | Approximately 2.1 per round | Closer to random than expert; supports only about 7.7 rounds per day |
	  | Deck construction | 24-card deck; at least 32 coarse archetypes | Starting strategy can change maximum achievable score by roughly 2× |
	  | Strategic exploration | Many agents concentrate on a small subset of archetypes; some use one archetype for nearly all trials | Models underinvest in the highest-value source of information |
	  | Explicit strategy guide | Adds approximately 2–3.5 objectives, depending on model | Even an “answer key” closes only a modest fraction of the expert gap |
	  | Stronger scaffolds / tools | Ad hoc code execution, Claude Code, and Codex trials showed no significant gains | Harness quality alone did not obviously solve the limitation, though testing was not exhaustive |

- ## The Central Result — Better Models, Same Learning Curve
	- GPT-5.5, Claude Opus 4.8, and Gemini 3.1 Pro show volatile playthrough-to-playthrough scores but no convincing upward trend over 30 attempts.
	- Frontier systems are not uniformly incompetent: Epoch expects their first-play performance to exceed that of many novice humans.
	- The distinction is between **competence embedded before inference** and **competence acquired during deployment**:
		- Newer models arrive with better priors, rules comprehension, and general reasoning.
		- They do not reliably update their strategy from the local history of wins, losses, notes, or objective scores.
	- This suggests current scaling improves the level of the capability curve more readily than its within-context slope.
	- **Variant perception**: Long context, memory, and repeated attempts are not equivalent to online learning. A transcript can preserve experience without the model extracting and applying the correct policy update.

- ## Failure Mode 1 — Poor Tactical Resource Management
	- The game's “fatigue” mechanic simultaneously represents health, remaining time, and card resources: taking fatigue moves cards out of the deck, and the day ends when the deck is exhausted.
	- Expert players prioritize cost-efficient removal of fatigue sources before pursuing objectives.
	- Agents frequently chase visible objectives too aggressively, fail to neutralize threats, accept unnecessary fatigue, and leave useful resources unspent.
	- At approximately 2.1 fatigue per round, GPT-5.5 and Opus 4.8 are materially nearer the 3.5 random baseline than the 0.6 expert benchmark.
	- Because excess fatigue shortens each day, weak tactics reduce the number of actions available to pursue objectives. The tactical error compounds over the entire horizon.
	- **Enterprise analogue**: Agents can understand a stated goal yet repeatedly consume budget, time, permissions, or API calls inefficiently because they fail to manage intermediate constraints.

- ## Failure Mode 2 — Underexploration of Strategic Options
	- Deck selection is the most consequential choice in each run: the best deck may support approximately twice the maximum score of the weakest.
	- With 80% of trials explicitly reserved for learning, an effective learner should test meaningfully different strategies, compare outcomes, and exploit the best result late in the run.
	- Instead, agents often reuse a narrow set of deck archetypes. The benchmark finds no clear trend toward broader exploration in newer models.
	- This resembles a failure of experimental design rather than a lack of raw knowledge:
		- The agent does not allocate attempts to maximize information value.
		- It does not separate exploration from exploitation.
		- It does not build a reliable causal model of which choices drove outcomes.
	- **Scientific and business analogue**: Autonomous discovery requires proposing diverse hypotheses, running controlled tests, attributing outcomes, and updating the next experiment. Strong answer generation alone does not supply this loop.

- ## Externalized Knowledge Helps, but Not Enough
	- In the basic setup, models must generate and use their own notes. Epoch's “max elicitation” condition instead supplies detailed tactical and strategic advice from an experienced player.
	- The guide improves results by approximately 2–3.5 objectives out of 21, but all tested models remain far below the expert score of 20.
	- This separates at least three capabilities:
		- **Lesson generation**: deriving the right rule from experience.
		- **Lesson retrieval**: surfacing the relevant note at the right decision point.
		- **Policy execution**: consistently acting on the rule under a changing state.
	- Providing a strategy guide largely bypasses the first problem, yet retrieval and execution still fail often enough to leave a wide gap.
	- **Implication**: Retrieval-augmented generation and enterprise knowledge bases can improve agents without making them reliable. Knowing the correct procedure is not the same as following it across a long workflow.

- ## Why More Inference Compute Did Not Solve It
	- Each 30-playthrough run provides a substantial inference budget, explicit scoring, repeated feedback, and persistent notes, yet returns to practice remain minimal.
	- More tokens can extend reasoning, retry actions, or preserve history without changing the underlying policy-update mechanism.
	- Inference scaling works best when a model already has an in-distribution search or verification procedure. EBR requires discovering which experiments to run and how to interpret them in a novel environment.
	- The benchmark therefore challenges a simple view that sufficiently long agent traces automatically converge on good behavior.
	- **Infrastructure nuance**: This is not necessarily bearish for token demand. Weak learning can increase retries, monitoring, supervisor calls, ensemble sampling, and external evaluation—raising compute per completed task even while limiting task autonomy.

- ## Training Distribution Still Dominates
	- Epoch interprets the result as evidence that frontier systems remain constrained by their training distributions.
	- Focused training on Earthborne Rangers could likely improve performance. If so, success would demonstrate task acquisition through offline training or post-training—not general inference-time learning.
	- Billions of dollars of training data make distribution boundaries difficult to observe on popular tasks. An obscure game exposes the boundary because memorized strategies and familiar tool patterns are less available.
	- The benchmark suggests an important moat distinction:
		- **General reasoning** transfers enough to make models decent novices.
		- **Expert improvement loops** still depend on targeted data, reward design, environment simulation, and repeated weight updates.
	- Model labs with proprietary interaction data, RL environments, and fast post-training pipelines retain an advantage even if base-model capabilities become more widely available.

- ## Stock-Market Read-Throughs
	- | Exposure | Read-through | What would change the view |
	  |---|---|---|
	  | Frontier model labs | Positive for proprietary post-training and environment-data moats; negative for claims of autonomous self-improvement at deployment | A model shows consistent positive learning slopes across unfamiliar tasks without weight updates |
	  | [[$MSFT]] / OpenAI | Codex can be valuable because its coding behavior is trained and scaffolded in advance, not because a generic model will learn any workflow after launch | Reliable transfer from Codex into novel tools and domains with minimal customization |
	  | [[$AMZN]] / Anthropic | Claude's economic value remains strongest in familiar coding/knowledge-work distributions; Bedrock customers still need domain integration and evals | Claude autonomously discovers and retains superior policies from production feedback |
	  | [[$GOOG]] / Gemini | Google's proprietary environments, product telemetry, simulation, and domain data are strategic assets for post-training | General Gemini agents learn novel workflows as effectively as domain-trained systems |
	  | Enterprise SaaS | Supports incumbents that own workflows, permissions, outcome data, and human feedback; generic agents cannot instantly absorb every domain | Model-only agents match incumbent workflow reliability without integrations or domain data |
	  | Agent observability / evaluation | Positive: flat or unstable learning curves require trace analysis, regression testing, supervisors, and explicit outcome measurement | Agents become self-correcting enough that external evaluation becomes less important |
	  | AI infrastructure | Training and post-training compute remain important; inference demand may rise through retries and scaffolding rather than autonomous productivity | Online learning substitutes for frequent retraining and reduces total compute per successful task |
	  | Robotics / autonomous systems | Caution: novel environments require safe exploration and stable policy improvement, which EBR does not demonstrate | Reliable continual learning under distribution shift with bounded safety risk |

- ## Implications for Enterprise Agent Adoption
	- **Narrow deployment wins first**: Agents should perform best where tasks resemble their post-training data and workflows can be expressed through familiar tools.
	- **Process redesign beats passive exposure**: Simply letting an agent repeat a job may not improve it. Enterprises need explicit examples, evaluators, reward signals, curated failure sets, and model/harness updates.
	- **Human experts remain training infrastructure**: Domain professionals must identify strategy, label failure modes, design experiments, and verify whether apparent improvements are real.
	- **Memory is necessary but insufficient**: Persistent notes help only if the system knows what to record, when to retrieve it, and how to translate it into action.
	- **Closed-loop products have a moat**: Vendors observing actions and ground-truth outcomes can periodically retrain or refine the system; chatbot-style products without outcome data cannot.
	- **Benchmarks should measure slopes, not just levels**: Enterprise buyers should test whether an agent improves across repeated similar cases, not merely whether it completes a curated case once.

- ## Safety Implications
	- Weak on-the-fly learning makes pre-deployment capability evaluations more informative: a deployed model may be less likely to acquire a qualitatively new dangerous skill solely through experience.
	- The result is not a safety guarantee. Agents can still use tools, retrieve external knowledge, copy successful traces, or be embedded in systems that update weights.
	- A future inflection in EBR-Bench-like learning curves would matter beyond productivity because models could become materially more capable after release than static evaluations indicate.
	- Monitor both **self-generated learning** and **learning from supplied demonstrations**; the latter may improve first and still enable rapid capability acquisition from human or agent-generated traces.

- ## Predictions and Falsifiable Checks
	- | Prediction | Expected development | Falsifiable signal |
	  |---|---|---|
	  | Offline post-training remains the main improvement engine | Labs continually refresh models using production trajectories rather than relying on frozen models to learn in context | Frozen deployed models show durable policy improvement across novel tasks |
	  | Domain agents outperform general autonomous agents | Vertical products with curated workflows and outcome data achieve better reliability | General models match them without fine-tuning, domain examples, or specialized scaffolds |
	  | Agent memory products disappoint without policy machinery | Storing every interaction produces limited gains unless paired with evaluators and lesson extraction | Larger memory alone creates consistent upward learning curves |
	  | Human supervision persists longer than benchmark extrapolations imply | Experts remain responsible for experimental design and strategy updates | Agents independently explore, diagnose, and improve unfamiliar workflows |
	  | Test-time compute keeps growing despite weak learning | Multi-agent critique, retries, judges, and verification increase tokens per task | Better online learning sharply reduces retries and supervision compute |
	  | Learning-from-demonstration improves before self-discovery | Agents use expert transcripts effectively before they can generate equally good lessons themselves | Self-generated notes match supplied expert guides first |
	  | A learning-slope benchmark becomes strategically important | Labs and buyers report improvement over repeated attempts as a separate capability axis | Topline static benchmarks remain sufficient predictors of agent performance |

- ## Risks and Counterarguments
	- **Single-domain risk**: Earthborne Rangers may expose game-specific planning weaknesses rather than a general inability to learn from experience.
	- **Harness limitation**: The main experiments use a simple ReAct scaffold. Better memory, hierarchical planning, search, or explicit optimization algorithms may produce a different result.
	- **Limited trials**: Ten or thirty attempts may be too few for a game that humans can take dozens of playthroughs to master.
	- **Weak human baseline**: The expert line reflects a top observed score, not a large controlled distribution of novice and expert human learning curves.
	- **Compaction effects**: Notes persist, but context compaction may discard tacit information that a human would retain.
	- **Objective mismatch**: Optimizing a delayed final-20% score may be harder for models than receiving dense rewards after each tactical choice.
	- **Elicitation remains open**: Epoch explicitly acknowledges that code execution, multi-agent setups, richer scaffolds, or expert playthrough transcripts deserve more systematic testing.
	- **Fast capability change**: A new model or online RL mechanism could invalidate the conclusion quickly; the benchmark's value is its ability to detect that transition.

- ## What to Monitor
	- Learning-curve slope across playthroughs—not only final EBR-Bench score.
	- Whether newer models explore a wider set of deck archetypes before exploiting successful strategies.
	- Fatigue per round and resource utilization as concrete tactical indicators.
	- Performance with expert playthrough transcripts versus abstract strategy guides.
	- Results from stronger scaffolds, code execution, multi-agent experimentation, and explicit planners.
	- Whether lessons discovered in one run transfer to a fresh context, new game segment, or related unfamiliar task.
	- Model-lab product disclosures around continual learning, trajectory-based post-training, and automated weight updates.
	- Enterprise evidence that agents improve from production outcomes without repeated human prompt engineering or model retraining.

- ## Bottom Line
	- Current frontier agents look more like **strong pretrained novices** than autonomous employees who reliably learn a new job through repetition.
	- Their weakness is not only knowledge. They fail to manage resources, explore high-value alternatives, extract causal lessons, and consistently execute supplied strategies.
	- This slows the path to fully autonomous, general agents but strengthens the economic value of domain data, post-training infrastructure, human expertise, workflow ownership, and evaluation systems.
	- The most important future signal is not another increase in first-attempt benchmark scores. It is a repeatable positive slope showing that a frozen model can turn experience into better policy on a genuinely unfamiliar task.
