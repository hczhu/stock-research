- tags:: [[OpenAI]], [[GPT-5.5]], [[Codex]], [[AI]], [[reasoning-models]], [[post-training]], [[reinforcement-learning]], [[pre-training]], [[mid-training]], [[inference]], [[test-time-compute]], [[agents]], [[coding-agents]], [[evals]], [[continual-learning]], [[enterprise-AI]], [[AI infrastructure]], [[$MSFT]], [[$NVDA]], [[$ORCL]], [[$CRM]], [[$NOW]], [[$SNOW]], [[$DDOG]], [[$GTLB]], [[$TEAM]]

- ## OpenAI Post-Training: From Competition Benchmarks to Useful Agents
	- **Source**: [The MAD Podcast with Matt Turck — “OpenAI's Yann Dubois: Why AI Progress Suddenly Feels Real”](https://pod.wave.co/podcast/the-mad-podcast-with-matt-turck/openais-yann-dubois-why-ai-progress-suddenly-feels-real), published 21 May 2026; user-supplied transcript.
	- **Guest**: Yann Dubois, co-lead of OpenAI's Post-Training Frontiers team and a co-author of Stanford Alpaca.
	- **Source-quality note**: Dubois provides first-party technical context about OpenAI's model-development process but avoids nonpublic implementation detail. Benchmark figures near the end are raised by the host rather than independently validated by Dubois. The automated transcript contains model and benchmark transcription errors; only sufficiently clear claims are retained.
	- **Thesis**: AI progress feels discontinuous because reliability crossed the level required for real delegation, even though underlying capability improvement remains continuous. The next economic wave comes from applying reinforcement learning and test-time compute to messy user work, not only math and coding contests. This increases training-rollout, inference, and evaluation demand while preserving a large market for vertical applications that solve permissions, connectors, workflow context, and other last-mile constraints.

- ## Executive Takeaways
	- **Reliability is the adoption threshold**: Dubois believes OpenAI crossed an important line around December 2025, after which models became trustworthy enough to perform much of researchers' and developers' work.
	- **Small error reductions compound over long tasks**: if an agent has some probability of failure every two minutes, extending the task rapidly lowers end-to-end success. Reliability per step—not peak benchmark intelligence—is the critical long-horizon metric.
	- **The RL frontier moved from verifiable competitions to real work**: techniques developed for math and code problems with objective answers are now being used on ambiguous coding, computer-use, knowledge-work, and scientific tasks.
	- **GPT-5.5 combined capability with efficiency**: Dubois says most tasks can be performed approximately 2x faster. Gains came jointly from model thinking efficiency and serving optimization.
	- **Test-time compute remains useful but has logarithmic returns**: Pro modes can think for one to two hours or overnight, improving the probability of correctness, but doubling compute often yields only a small gain.
	- **Pre-training still matters**: larger base models can require fewer reasoning tokens and may serve more efficiently than intuition suggests because their computation parallelizes better.
	- **Post-training is scaling dramatically**: the transcript contrasts approximately 50,000 Stanford Alpaca supervised examples with public RL efforts approaching one million examples.
	- **RL is both a compute and credit-assignment problem**: systems must sample many expensive rollouts, while a long agent trajectory may reveal success or failure only at the end.
	- **Evals are becoming the training frontier**: every strong evaluator can generate or select training data. Better models become judges and teachers, creating a self-improvement flywheel while quickly saturating static benchmarks.
	- **Continual learning remains unsolved**: models can start more useful than new employees but do not reliably improve with company experience. Memory helps, but persistent weight-level learning, privacy, and permissions remain open problems.
	- **Applications still have room**: Dubois expects OpenAI to focus on horizontal capability while startups solve vertical permissions, connectors, data, and workflows. The last mile—not raw intelligence—is often the commercial bottleneck.

- ## Key Data Points and Disclosures
	- | Data point | Dubois disclosure or interview example | Investment relevance |
	  |---|---|---|
	  | Reliability threshold | OpenAI crossed it around **December 2025**, in Dubois's judgment | Explains why agent adoption can accelerate suddenly after gradual model progress |
	  | Error framing | Agent reliability can be viewed as a probability of failure every **two minutes** | Small per-step improvements have exponential value on long tasks |
	  | Model iteration cadence | Upstream training can take **months**, while late post-training iterations can take **days** | More value and release speed move toward the downstream training stack |
	  | GPT-5.5 speed | Most tasks can be performed approximately **2x faster** | Better capability need not mean proportionally higher latency or cost |
	  | Pro reasoning time | High-value academic tasks may run for **one to two hours** | Reasoning products create premium, variable inference demand |
	  | Overnight reasoning window | A user may allow approximately **eight hours** when latency does not matter | The upper bound on inference per task expands with autonomous workflows |
	  | Test-time scaling | Approximately **2x more compute** can produce only a small performance gain | Returns are positive but logarithmic; routing by task value is essential |
	  | Stanford Alpaca data | Approximately **50,000 supervised fine-tuning examples** | Early post-training was small and primarily behavior cloning |
	  | Public modern RL scale | DeepSeek/Kimi-style efforts were described as approaching **one million data points** | Post-training data and rollout demand expanded by roughly an order of magnitude or more |
	  | Continual-learning delay | Still unsolved roughly **three years after ChatGPT** | Memory and personalization products are intermediate substitutes, not final solutions |
	  | Harness uplift example | A vertical harness might move reliability from approximately **80% to 85%** | Five percentage points can be commercially decisive despite rapid base-model progress |
	  | Finance-agent benchmark | Host cited automation of **88.5% of internal investment-banking modeling tasks** | Directional evidence that structured professional workflows are entering the addressable set |
	  | OfficeQA Pro | Host cited approximately **51.1%** | Office knowledge work remains much less solved than narrow finance modeling |

- ## Why Progress Feels Like a Step Function
	- Model capability can improve smoothly while product utility remains near zero below a reliability threshold.
	- An agent that is correct 99% of the time at each step can still fail frequently over hundreds of steps. Once per-step error falls enough, the same architecture becomes useful for entire tasks rather than isolated suggestions.
	- Crossing the threshold creates a feedback loop:
		- Researchers use agents to write code and build training tools.
		- Better internal tooling accelerates experiments and model development.
		- Stronger models improve the next generation's training data, graders, and infrastructure.
		- External users generate more difficult workflows and feedback.
	- The observed discontinuity is therefore adoption and task length, not necessarily a discontinuity in underlying intelligence.
	- **Investor implication**: benchmark curves can understate revenue inflections. Usage may accelerate when reliability clears a workflow-specific minimum even without a dramatic benchmark jump.

- ## GPT-5.5: Integrated Vertical and Horizontal Progress
	- OpenAI uses vertical teams to improve specific use cases such as agentic coding, computer use, knowledge work, and scientific research.
	- The Post-Training Frontiers team integrates those improvements into one model and smooths differences so the system does not feel excellent in one vertical and erratic in another.
	- Horizontal capabilities include:
		- Instruction following.
		- Function calling.
		- Choosing how long to think.
		- Memory behavior.
		- General reliability and calibration.
	- Orthogonal teams can make progress simultaneously, but only a subset of improvements may be stable enough to enter any one final run.
	- **Organizational implication**: frontier-model production resembles a complex platform integration program, not a single research breakthrough. Coordination and final-run judgment are scarce capabilities.

- ## Efficiency, Latency, and Test-Time Compute
	- Dubois frames reasoning economics as a curve with compute or latency on the horizontal axis and task performance on the vertical axis.
	- Research moves the curve left by teaching a model to reach the same answer with fewer thinking tokens or to choose promising paths earlier.
	- Serving engineering converts tokens into wall-clock latency through batching, kernels, parallelism, memory management, and hardware utilization.
	- Pro mode extends the curve to the right: the system spends much longer for a higher probability of correctness when the task value justifies it.
	- Expert-like efficiency comes from reducing search:
		- A novice explores ten directions over one or two days.
		- An expert recognizes the likely path immediately.
		- RL teaches the model which reasoning branches are promising and when to backtrack.
	- **Pricing implication**: providers can segment by latency and confidence. Routine tasks use fast modes; research, code migration, finance, and science can purchase much more inference.
	- **[[$NVDA]] read-through**: lower tokens per task are a headwind, but longer premium tasks and far more delegated work can overwhelm efficiency. Aggregate compute depends on the distribution of task value and reasoning duration.

- ## Why Larger Base Models Can Improve Inference Economics
	- A larger pre-trained model embeds more computation in its weights and may need fewer generated reasoning tokens to reach the same result.
	- Larger models also offer more parallel computation per token, which can use GPUs efficiently compared with a smaller model generating a very long serial chain of thought.
	- The correct comparison is therefore system latency and cost at a fixed quality level—not parameter count or tokens in isolation.
	- This creates two viable serving strategies:
		- Larger expert-like model with fewer reasoning steps.
		- Smaller model with longer inference, sampling, and verification.
	- Workload, hardware, batch size, and latency requirements decide which is cheaper.
	- **Infrastructure implication**: continued pre-training scale and inference-time scale are complements. A stronger base shifts the reasoning curve while post-training and serving decide how the capability is consumed.

- ## The Training Stack
	- | Stage | Function | Cadence | Primary economic input |
	  |---|---|---|---|
	  | Pre-training | Learns broad world knowledge from internet-scale data | Months | Large GPU clusters, data quality, distributed training |
	  | Mid-training | Overweights high-quality, representative corpora such as Wikipedia and code | Between base and product stages | Curated data, domain mix, context and representation choices |
	  | Supervised fine-tuning | Clones desired human or teacher demonstrations | Fast relative to pre-training | Expert demonstrations and synthetic answers |
	  | Reinforcement learning | Optimizes rewards and can exceed the demonstrator | Days to large production runs | Rollout compute, graders, environments, reward design |
	  | Integration/final run | Combines vertical and horizontal improvements into a coherent model | Product-proximate | Coordination, evals, infrastructure, model judgment |
	- Pre-training resembles acquiring a library. Post-training turns the library into an expert who understands the user's question and applies the information.
	- Mid-training addresses the fact that much internet text is low-value. High-quality sources receive disproportionate weight before the product-specific phase.

- ## Supervised Fine-Tuning Versus Reinforcement Learning
	- Supervised fine-tuning learns to imitate a supplied answer. Its ceiling is the quality and coverage of the demonstrator.
	- Reinforcement learning does not require the perfect answer in advance. It needs a method to score or compare outcomes, then increases the probability of higher-reward behavior.
	- Public pipelines often use both:
		- SFT brings the policy near useful behavior efficiently.
		- RL searches around that policy and can move beyond human demonstrations.
	- Starting with RL alone is inefficient because the model must stumble onto successful behavior before it can reinforce it.
	- Modern post-training scale suggests RL is no longer the small “cherry on top.” Once base models developed strong priors, RL became stable enough to create visible reasoning, checking, and backtracking behaviors.

- ## From Verifiable Rewards to Messy Economic Work
	- Math and code competitions are convenient because success is objectively testable and all relevant information is normally contained in the prompt.
	- Real work is different:
		- The task is underspecified.
		- Relevant data sits across the web, files, and enterprise systems.
		- There may be several acceptable answers.
		- Quality depends on unstated preferences and downstream consequences.
	- OpenAI's recent progress comes from removing simplifying assumptions and optimizing for user utility rather than benchmark correctness alone.
	- Capabilities transfer when the underlying skill is shared across domains. A model trained to search, verify, or admit uncertainty can apply that behavior in finance, law, coding, and other fields.
	- Narrow competition intelligence does not automatically transfer to messy work. Research and consulting require finding evidence, judging source quality, resolving ambiguity, and discovering which question to answer.
	- **Application implication**: vertical companies can create value by specifying objectives, curating domain data, building rewards, and defining acceptable outcomes.

- ## Why Cybersecurity Improved Quickly
	- Cybersecurity has real-world complexity but unusually verifiable outcomes: an exploit succeeds or fails, a vulnerability can be reproduced, and a patch can be tested.
	- This makes cyber a natural bridge from code competitions to economically valuable work.
	- Similar categories likely progress earlier when they offer:
		- Objective execution feedback.
		- Cheap simulation or sandboxing.
		- Automated tests.
		- Many repeated tasks.
		- High value for small accuracy gains.
	- **Security read-through**: automated offensive and defensive research can expand both incident volume and remediation speed. Security platforms need agent telemetry, isolation, identity, and verification rather than only signature detection.

- ## RL Scaling Bottlenecks
	- **Rollout cost**: the model must sample many answers or trajectories, often with a large model, before rewards can identify better behavior.
	- **Long-horizon credit assignment**: an agent may act for hours and receive one success/failure signal at the end. The trainer does not know which intermediate decision caused the outcome.
	- **Sparse feedback per token**: as trajectories lengthen, useful reward information becomes diluted across more tokens and tool actions.
	- **Infrastructure reliability**: distributed generation, environment execution, checkpointing, and training must remain synchronized across large GPU fleets.
	- **Data and environment construction**: real-world tasks need realistic systems, permissions, state, and outcome checks.
	- **Human bottleneck**: relatively few researchers can design and integrate frontier training runs, and fewer still understand specialized legal, medical, or financial work deeply enough to define quality.
	- **Compute implication**: agentic RL can consume substantial inference-like compute during training because each update depends on many generated trajectories.

- ## GRPO and the Preference for Scalable Simplicity
	- Dubois does not disclose OpenAI's internal algorithm. In the open-source ecosystem, he views GRPO as a simple method that has converged into broad use.
	- The general loop samples many responses, scores which ones work, and updates the model toward the successful group.
	- Machine learning repeatedly favors methods that are simple enough to scale with compute over theoretically elegant systems that are operationally fragile.
	- New techniques often begin as craft: researchers try many ideas and develop intuition. Once a behavior works, controlled experiments turn it into science.
	- **Moat implication**: the published algorithm may commoditize, but data, environments, evals, infrastructure, and integration craft remain difficult to copy.

- ## Hallucinations and Calibration
	- Supervised fine-tuning can inadvertently reward hallucination. If the model does not know a paper but is trained to reproduce a human citation, it learns to state information it cannot internally support.
	- In RL, unsupported guesses are unlikely to receive a positive reward if citations or answers are checked. Repeatedly penalizing false confident output can improve calibration.
	- The important capability is horizontal: knowing when evidence is missing and seeking it or admitting uncertainty.
	- Explicit and implicit instruction following can conflict:
		- A literal model follows a mistyped file name exactly.
		- A context-sensitive model infers the intended file and may violate the explicit text.
	- Product reliability depends on balancing obedience, initiative, and clarification according to task risk.

- ## Evals Become Training Infrastructure
	- Evaluation becomes harder as tasks move from “find this bug” to “build a good website” because many outputs are acceptable and quality is multidimensional.
	- Models now exceed most humans on some axes, reducing the pool of evaluators able to judge them.
	- Every useful eval can become training data or a reward function. Once developers optimize related tasks, the benchmark saturates rapidly.
	- Model-as-judge is therefore central to both training and evaluation:
		- Strong models score answers from weaker or specialized models.
		- Judges generate preferences, critique, and synthetic training examples.
		- A better frontier model becomes a better teacher for the next model.
	- **Risk**: judge bias, shared failure modes, and reward hacking can create apparent improvement without real-world quality.
	- **Infrastructure opportunity**: domain evals, replay environments, human escalation, observability, and audit trails become critical enterprise layers.

- ## Continual Learning Remains the Missing Curve
	- Dubois describes utility over time:
		- A model may be more useful than a new employee on day zero.
		- Its usefulness remains mostly flat because it does not learn company context and improve through experience.
		- A human starts lower but learns quickly, potentially producing more cumulative value.
	- The desired system improves monotonically as it works in an environment.
	- Codex memory is helpful but not equivalent to continual learning; it stores context without reliably updating the model's core behavior.
	- Barriers include permissions, privacy, cross-user data sharing, incorrect feedback, and maintaining capability while learning new information.
	- Dubois is surprised the field has not solved even single-user continual learning three years after ChatGPT.
	- **Enterprise implication**: memory, retrieval, skills, and periodic tuning remain valuable substitutes. A true continual-learning breakthrough could disrupt those layers.

- ## Harnesses: Necessary but Perishable
	- A well-designed harness can materially improve current models through tools, prompts, memory, routing, verification, and retries.
	- For a focused vertical, moving reliability from 80% to 85% may decide whether the product works economically.
	- The tradeoff is maintenance. Every stronger base model changes optimal prompting, tool policies, reasoning budgets, and failure handling.
	- Dubois is skeptical of a timeless general harness but strongly supports vertical harnesses built for concrete near-term value.
	- He argues that if today's models were frozen and the industry optimized harnesses aggressively, many domains could already experience something resembling AGI-level utility.
	- **Startup implication**: build the harness, but assume continuous retuning and avoid confusing temporary scaffolding with a permanent moat.

- ## The Last Mile Preserves Application Value
	- Foundation labs prioritize broad horizontal capability. Vertical products can specialize in:
		- Permissions and identity.
		- Connectors to systems of record.
		- Proprietary data and workflow context.
		- Domain-specific rewards and evals.
		- Human approvals, exception handling, and audit.
		- Outcome ownership and customer support.
	- Host-cited benchmark results show uneven readiness: structured investment-banking modeling appears far more automatable than broad office question answering.
	- The gap is investable. Vertical companies can convert a capable but general model into a reliable economic workflow before a foundation lab chooses to prioritize it.
	- Long-run survival requires more than prompting. The application should accumulate data, feedback, distribution, transactions, trust, or regulatory integration.

- ## Predictions
	- | Prediction | Dubois stance | Industry implication |
	  |---|---|---|
	  | Coding's reliability inflection spreads to other verticals | High confidence over the next 12–24 months | Agent adoption broadens through finance, legal, support, research, and office work |
	  | Frontier progress remains continuous | High confidence | Apparent step functions will come from local reliability thresholds rather than one singular event |
	  | Pre-training continues improving | Medium-high confidence | Large training clusters remain economically relevant alongside RL and inference scaling |
	  | Larger models improve reasoning efficiency | High confidence | Parameter growth can coexist with lower tokens and latency per task |
	  | RL expands beyond verifiable domains | High confidence | Domain data, graders, and environments become strategic assets |
	  | Evals and model judges gain importance | High confidence | Evaluation becomes both a bottleneck and a self-improvement mechanism |
	  | Continual learning is eventually solved | High enthusiasm, uncertain timing | Could create persistent enterprise agents and disrupt static memory/RAG stacks |
	  | General harnesses remain unstable | Medium-high confidence | Model upgrades repeatedly commoditize generic orchestration |
	  | Vertical last-mile products retain room | High confidence | Application value persists in context, permissions, tools, and outcomes |

- ## Stock Read-Throughs
	- **[[$MSFT]] — distribution and OpenAI exposure, with application cannibalization risk**
		- GPT-5.5 reliability and speed improve Codex, Microsoft 365 agents, GitHub, and Azure model consumption.
		- Test-time compute, RL rollouts, and model-as-judge expand infrastructure usage beyond ordinary chat.
		- The same horizontal progress can compress traditional Office and developer-tool interfaces if users delegate outcomes directly.
	- **[[$NVDA]] — multiple scaling axes support demand**
		- Pre-training larger base models, generating RL rollouts, running judges, and spending one to eight hours on valuable inference all consume accelerators.
		- Efficiency and logarithmic returns limit chips per fixed task. The bull case requires task volume and value to expand faster than tokens per answer decline.
	- **[[$ORCL]] and AI infrastructure providers — long-running work broadens serving demand**
		- Frontier labs need large, reliable fleets for training and inference. Agent rollouts blur the boundary because training increasingly resembles massive inference generation.
		- Concentration and utilization remain risks if a model generation fails to produce user value.
	- **[[$CRM]], [[$NOW]], [[$TEAM]], and [[$GTLB]] — last-mile assets versus interface risk**
		- Bull case: authoritative data, permissions, workflow state, and enterprise distribution are exactly what general agents lack.
		- Bear case: foundation models and external harnesses take over the user interaction while incumbents become lower-value back-end databases.
		- Critical response: expose reliable agent actions and domain evals while retaining transaction and governance control.
	- **[[$SNOW]] — governed data and agent context**
		- Messy real-world reasoning requires finding and joining enterprise evidence before reasoning begins.
		- Snowflake benefits if it remains the governed context and execution layer; it is pressured if agents bypass warehouses with application-level connectors and files.
	- **[[$DDOG]] — agent and eval observability**
		- Long trajectories make failure attribution harder. Traces, tool calls, latency, cost, judge output, and reproducible environments need monitoring.
		- Model providers can internalize some observability, so independent value depends on cross-model and cross-application visibility.

- ## Scenario Framework
	- | Scenario | Technical path | Economic result | Relative beneficiaries |
	  |---|---|---|---|
	  | Reliability diffusion | More verticals cross their minimum success threshold | Adoption and inference rise sharply after gradual model gains | Model labs, clouds, accelerators, vertical agents |
	  | Efficiency dominates | Models perform tasks 2x faster and routing suppresses long reasoning | Unit costs fall faster than new usage grows | Application customers; pressure on infrastructure intensity |
	  | Test-time compute boom | High-value tasks regularly run for hours with judges and tools | Revenue and compute shift toward outcome-priced premium work | Frontier labs, [[$NVDA]], clouds, research and finance agents |
	  | Harness commoditization | Base models absorb prompting, routing, memory, and checking | Generic agent infrastructure loses differentiation | Foundation models and strong systems of record |
	  | Vertical last-mile wins | Domain data, permissions, and accountability remain difficult | Applications retain pricing and distribution | Vertical SaaS, governance, data and observability platforms |
	  | Continual-learning breakthrough | Agents improve persistently inside each organization | Switching costs and personalization rise; static memory stacks reset | Model/platform controlling the learning loop and enterprise data owner |

- ## Key Tests for the Thesis
	- **End-to-end reliability**: success probability versus task duration, not only single-step accuracy.
	- **GPT-5.5 efficiency**: realized latency and cost at fixed quality across coding, computer use, and knowledge work.
	- **Reasoning elasticity**: how often users choose Pro or overnight modes and whether higher success supports premium pricing.
	- **RL compute mix**: rollout generation, judge-model usage, and post-training share of frontier-cluster demand.
	- **Vertical adoption**: finance, legal, support, scientific, and office workflows crossing production thresholds.
	- **Last-mile economics**: gross retention and pricing for applications whose base-model capability improves rapidly.
	- **Harness maintenance**: engineering effort required after each model upgrade versus the reliability gained.
	- **Continual learning**: measurable improvement from repeated use without catastrophic forgetting or privacy leakage.
	- **Eval integrity**: refreshed tasks, human expert agreement, reward-hacking rates, and production correlation.

- ## Bottom Line
	- The important GPT-5.5 signal is not one benchmark. It is the combination of reliability, real-world RL, and approximately 2x faster execution that allows users to delegate longer and messier work.
	- AI demand now compounds across pre-training, post-training rollouts, model judges, test-time reasoning, and agent tools. Efficiency reduces the cost of each unit, but higher task volume and longer premium work can expand the total market.
	- Applications remain investable because intelligence is only one input. Permissions, connectors, context, evaluation, accountability, and workflow design determine whether a model creates economic value.
	- The most durable companies will either own the horizontal intelligence/infrastructure loop or control a vertical last mile with data, distribution, and measurable outcomes.
