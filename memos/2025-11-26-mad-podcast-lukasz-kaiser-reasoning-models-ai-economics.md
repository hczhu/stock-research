- tags:: [[OpenAI]], [[GPT-5]], [[Codex]], [[AI]], [[reasoning-models]], [[reinforcement-learning]], [[pre-training]], [[post-training]], [[distillation]], [[inference]], [[agents]], [[multimodal]], [[generalization]], [[robotics]], [[GPU]], [[AI infrastructure]], [[$NVDA]], [[$GOOG]], [[$MSFT]], [[Anthropic]], [[human-in-the-loop]]

- ## Łukasz Kaiser: Reasoning Models, AI Economics, and the Next Scaling Stack
	- **Source**: [The MAD Podcast with Matt Turck — “What's Next for AI? OpenAI's Łukasz Kaiser (Transformer Co-Author)”](https://open.spotify.com/episode/7anXK3XmTcAfi5ZHE38j8V), published 26 November 2025; user-supplied transcript.
	- **Guest**: Łukasz Kaiser, OpenAI research scientist working on reasoning models, former Google Brain researcher, and co-author of “Attention Is All You Need.”
	- **Source-quality note**: Kaiser's technical descriptions and firsthand observations are primary-source commentary. The supplied transcript contains automated-transcription errors, including model names and some quantitative wording; ambiguous figures are labeled approximate rather than presented as precise disclosures.
	- **Thesis**: The AI scaling story has broadened from one pre-training curve into a compounding stack: frontier teacher models, RL-based reasoning, synthetic data, inference-time compute, tools, distillation, and product-specific post-training. This increases aggregate compute demand even as serving cost per task falls. The main constraint is no longer evidence of progress but uneven generalization, multimodal weakness, long-horizon reliability, secure access to external systems, and the economics of serving roughly a billion users.

- ## Executive Takeaways
	- **AI capability still looks like a smooth exponential from inside frontier labs**: individual techniques follow S-curves, but new paradigms, compute, data, and engineering sustain the aggregate trend.
	- **Pre-training still scales; its marginal economics changed**: loss continues to improve log-linearly with compute, but reasoning/RL currently offers larger capability gains per dollar because it is earlier in its S-curve.
	- **Reasoning changes both training and inference demand**: models generate internal thinking tokens, use tools, verify work, and can spend more compute on difficult tasks. Longer thinking can raise capability faster than equivalent pre-training spend for supported domains.
	- **Distillation makes giant models economically useful even when users cannot afford them directly**: large models become teachers for smaller serving models, linking frontier training spend to mass-market inference efficiency.
	- **Product scale redirected research toward cost**: once ChatGPT reached roughly one billion users, labs could no longer serve only the smartest model. Matching quality with smaller, cheaper models became a first-order research objective.
	- **Reasoning remains jagged**: frontier models can reach Olympiad-level math performance yet fail a visual counting puzzle intended for a five-year-old. Multimodal reasoning and transfer from prior reasoning remain undertrained.
	- **Long-running agents are an engineering, model, memory, and security problem**: compaction extends context across millions of tokens, but agents still loop, lose goals, and lack safe access to GPU clusters and other real-world systems.
	- **Foundation models do not eliminate application value yet**: reliability, domain context, workflow integration, verification, security, and trust preserve room for vertical products and human review.
	- **Robotics could become the most visible next interface shift**: Kaiser expects strong progress when multimodal perception and general reasoning transfer into physical domains, but hardware safety may slow commercial deployment.

- ## Key Data Points and Disclosures
	- | Data point | Kaiser disclosure or example | Investment relevance |
	  |---|---|---|
	  | Reasoning-model maturity | OpenAI began working on the paradigm roughly three years before the interview; the public preview was only about 13 months old | Reasoning was still early relative to pre-training, leaving substantial engineering and training headroom |
	  | Pre-training law | Loss still declines approximately log-linearly as compute increases | Frontier training remains productive even if marginal capability per dollar has slowed |
	  | ChatGPT scale | Kaiser referred to roughly **one billion users** | Serving economics and inference capacity now influence model architecture and research priorities |
	  | Cost improvement | GPT-4-to-GPT-5 economics improved by orders of magnitude; the transcript references roughly **1,000x** but the wording is ambiguous | Model efficiency can expand usage dramatically, but does not remove aggregate infrastructure demand |
	  | Hidden reasoning | ChatGPT shows users a summary produced from the full chain of thought rather than the raw internal trace | Reasoning observability and faithfulness remain separate product and safety questions |
	  | Reasoning control | GPT-5.1 can be steered to think longer; more reasoning tokens increase capability on supported tasks | Creates variable inference cost and opportunities for tiered pricing/routing |
	  | Jagged visual reasoning | GPT-5.1 and Gemini 3 solved one dot-counting example but failed a nearly identical follow-up | Benchmark strength does not guarantee local generalization or workflow reliability |
	  | High-compute workaround | GPT-5 Pro could spend roughly 15 minutes and run Python to solve a task a child handles in about 15 seconds | Test-time compute can brute-force capability but may be economically or operationally inefficient |
	  | Codex Max context | Compaction supports operation across multiple context windows totaling millions of tokens | Long-horizon agents expand token, memory, retrieval, and verification demand |
	  | Desired agent horizon | Research implementation tasks can require a week of running experiments, reading results, and fixing bugs | Autonomous knowledge work needs persistence far beyond current chat sessions |
	  | OpenAI agent ambition | Kaiser interpreted the goal as reaching an “AI intern” around the end of the following year | Concrete near-term aspiration, not a guaranteed product milestone |

- ## Why the “AI Slowdown” Narrative Is Misleading
	- **Aggregate progress can stay smooth while individual techniques saturate**: pre-training may be on the upper part of its scientific S-curve, while reasoning is on the steep early section of a newer curve.
	- **Scaling laws were not falsified**: Kaiser says frontier labs still observe predictable loss improvement from larger pre-training runs. The issue is the capital required for each incremental gain.
	- **Reasoning unlocked a higher-return frontier**: RL teaches models to search, verify, correct mistakes, and use tools before answering. These behaviors create capabilities that pure next-token prediction reached less efficiently.
	- **Tools make superficially similar chat products fundamentally different**: a current model can know the date, browse an official site, cross-check multiple sources, and synthesize an answer rather than hallucinating from stale weights.
	- **Adoption lags capability**: Kaiser argues users underestimate what existing frontier systems can already do—from diagnosing a broken object from a photo to completing college-level work.
	- **Coding is the leading indicator**: software developers shifted within months from occasional completions to delegating whole tasks to Codex-like agents. Kaiser expects similar workflow changes to spread into other domains.

- ## The New Scaling Stack
	- | Layer | Function | Primary bottleneck | Compute effect |
	  |---|---|---|---|
	  | Pre-training | Builds broad world knowledge and base capability from large corpora | Capital, data quality, distributed systems, diminishing marginal gains | Larger frontier training clusters remain valuable |
	  | Reasoning RL | Reinforces thinking strategies that lead to correct or preferred outcomes | Reward quality, verifiable tasks, rollout stability, sparse feedback | Multiplies training attempts and post-training compute |
	  | Synthetic data | Generates targeted examples from stronger models | Teacher quality, diversity, contamination, and verification | Converts inference from teacher models into training input |
	  | Distillation | Transfers frontier capability into smaller models | Capability loss and difficult edge cases | Justifies large teacher runs while lowering cost per served query |
	  | Inference-time compute | Lets a model think, browse, run code, and verify before responding | Latency, token cost, routing, and task-specific returns | Creates elastic demand tied to problem difficulty |
	  | Product post-training | Tunes safety, tone, refusal behavior, instruction following, and use cases | Diverse feedback and avoiding reward hacking | Enables more frequent releases without a new base-model run |
	  | Agent harness | Maintains state, tools, permissions, compaction, and execution loops | Long-horizon reliability and secure external access | Adds context, retrieval, tool, and repeated-evaluation workloads |
	- **Complementarity matters**: reasoning works better when placed on top of a stronger base model, while distillation distributes the stronger model's knowledge into affordable products. The layers reinforce rather than replace one another.
	- **Release cadence decouples from pre-training**: capability-based names such as GPT-5 and GPT-5.1 can combine progress from multiple projects through post-training and distillation without waiting for a months-long new base-model run.

- ## Reinforcement Learning and Reasoning Economics
	- A reasoning model generates internal tokens before producing the user-visible answer and may browse the web, run Python, or invoke other tools during that process.
	- Training treats the reasoning trace as a behavior to improve: attempts leading to correct answers receive reinforcement, and the model learns strategies such as checking work and revisiting suspected errors.
	- **Best-supported domains are verifiable**: coding tests, math answers, and some scientific problems provide rewards that are easier to score reliably.
	- **General-domain RL is the next expansion**: Kaiser expects reasoning training to broaden beyond narrow science and code into less directly verifiable text and multimodal tasks.
	- **Preference optimization remains fragile**: early RLHF could learn to exploit a preference model if trained too long. Stronger graders and more constrained domains support longer, more useful RL runs.
	- **Reasoning tokens create a pricing knob**: providers can route easy tasks to short thinking and reserve long inference for premium or high-value problems.
	- **Unit economics are task-dependent**: a 15-minute reasoning path may be justified for research, code, or a high-value decision but irrational for routine consumer queries.
	- **Infrastructure implication**: aggregate token demand depends on task mix, not just user count. As users delegate harder work, tokens per successful task can rise even while cost per token falls.

- ## Pre-Training, Distillation, and GPU Demand
	- Early OpenAI could allocate nearly all GPUs to training because the API product had modest serving demand. ChatGPT's mass adoption forced a permanent competition between training and inference.
	- **Why smaller models became essential**: many users would not pay enough to cover routine access to the largest possible model, so labs optimized for similar quality at lower serving cost.
	- **Why large models return to the roadmap**: a frontier model can teach an entire family of smaller models through distillation. Its value is distributed across massive downstream volume rather than captured only through direct usage.
	- **Capacity timing matters**: announced GPU investment does not instantly become usable training capacity. Kaiser suggested new capacity coming online could support a perceived resurgence in large pre-training runs.
	- **GPU allocation is structurally competitive**: pre-training remains the largest consumer, RL is growing, video models require substantial compute, and product inference serves enormous daily demand.
	- **[[$NVDA]] read-through**: efficiency does not imply falling compute demand when it unlocks cheaper mass inference, larger teacher models, more RL rollouts, synthetic-data generation, video, and long-running agents simultaneously.
	- **Key falsifier**: if model families stop improving from larger teachers, reasoning tokens fail to produce economic value, or user/task growth cannot absorb efficiency gains, the stacked-compute thesis weakens.

- ## GPT-5 and GPT-5.1: Product Progress Beyond Base Models
	- Kaiser attributes the largest GPT-4-to-GPT-5 capability change to reasoning RL and synthetic data; much pre-training work during the period targeted cost reduction.
	- GPT-5.1 was described mainly as a post-training improvement rather than proof of a new base-model run.
	- Product feedback now shapes safety, helpfulness, refusal behavior, uncertainty, and tone because the system serves diverse users, including people in distress.
	- Custom response styles are post-training behaviors: models learn to map an instruction such as “professional” or “nerdy” to a preferred response distribution.
	- Naming moved from internal training chronology to user-facing capability because multiple research streams can be combined asynchronously into one release.
	- **OpenAI read-through**: product quality depends increasingly on feedback data, routing, safety research, post-training, and serving economics—not only possession of the largest base model.
	- **Competitive implication**: model labs can leapfrog on different layers. One may lead pre-training, another coding RL, another multimodal data, while end-user quality reflects the integrated system.

- ## Jagged Intelligence and the Generalization Gap
	- The dot puzzle illustrates failure to transfer a just-demonstrated visual rule into a nearly identical second example.
	- Kaiser attributes much of the failure to undertrained multimodal reasoning and weak learning from reasoning shown in context, not necessarily a fundamental architectural ceiling.
	- More test-time compute can overcome some errors through tool use, but the solution may be absurdly inefficient relative to a human.
	- **Pre-training expands knowledge and scale together**, so it does not cleanly test sample-efficient generalization. A model may solve more cases because it has seen more surface patterns rather than learned a reusable concept.
	- **Reasoning may improve generalization**, but current RL data is concentrated in math, coding, and science. The decisive experiment comes after training broadens and obvious multimodal/engineering gaps are fixed.
	- **Investor implication**: broad benchmarks can overstate automation readiness. Deployment decisions should depend on error distribution, exception frequency, and verification cost in the exact workflow.
	- **Application moat**: domain-specific evals, proprietary examples, constraints, workflow state, and escalation paths can turn a jagged general model into a reliable product.

- ## Long-Running Agents, Compaction, and Security
	- A week-long research task requires repeated cycles of coding, running experiments, waiting, interpreting output, debugging, and changing direction.
	- Models were not trained on many week-long trajectories, so they can loop, lose the objective, or behave strangely as the task extends.
	- Transformer attention and memory grow with context length; retaining every prior token becomes prohibitively expensive.
	- **Compaction** asks another model to summarize the important state, starts a fresh context with that summary, and discards lower-value history. Repeating the process allows millions of cumulative tokens.
	- **Compaction risk**: forgotten details, mistaken summaries, and lost causal history can corrupt later decisions. Durable agents need external artifacts, tests, checkpoints, and resumable state—not summaries alone.
	- **Tool-access bottleneck**: an AI research agent needs GPUs, clusters, code execution, data, and credentials. Connecting models to those resources expands the security blast radius.
	- **Infrastructure opportunity**: secure sandboxes, secrets management, permissions, observability, state stores, evals, and rollback systems become core components of agent deployment.
	- **Timeline implication**: an “AI intern” is a more realistic near-term product than a fully autonomous researcher because humans can assign bounded work and review checkpoints.

- ## Will Foundation Models Eat Applications?
	- Kaiser's answer is constrained by current model failure modes: systems that miss a child's visual rule still require application logic, testing, and human review.
	- The translation industry is his counterexample to simple displacement. Machine translation automated much of the task, yet translation demand and compensation reportedly grew as more content became economical to translate.
	- High-scale publishers still pay for human review because a small verification cost is rational when output reaches millions or a billion users.
	- **Automation can expand the market**: lower production cost increases translated content, generated software, analysis, and personalized services faster than it eliminates all human work.
	- **Trust preserves a paid layer**: regulated, high-reputation, high-scale, or safety-critical outputs require accountable review even when baseline generation is nearly free.
	- **Application value migrates** from raw generation toward context, workflow, distribution, policy, security, verification, and responsibility for outcomes.
	- **SaaS risk** is highest for thin interfaces whose only value is prompting a foundation model; it is lower for products with proprietary data, transaction systems, domain feedback, and embedded approvals.

- ## Multimodal AI, Alternative Architectures, and Robotics
	- Kaiser says multimodal capability still lags text substantially and may require retraining an entire base model, involving months of work and major capital.
	- Models do not yet reason naturally across perception and context, which limits robotics and physical-world generalization.
	- Alternative approaches inspired by ARC, small structured-reasoning models, and non-transformer research remain active, but scaling experimental systems beyond one machine is an engineering bottleneck.
	- Coding agents can democratize architecture research by implementing ideas across eight- or hundred-machine clusters, though they were not yet reliable enough for this autonomously.
	- **Robotics sequence implied by Kaiser**:
		- Improve multimodal perception.
		- Generalize reasoning into physical domains.
		- Pair capability with hardware already being developed or teleoperated.
		- Solve household safety, reliability, and scalable deployment.
	- **Timing range**: model progress could arrive within a year or take several years; safe commercial deployment may lag capability.
	- **Hardware read-through**: physical AI adds persistent inference, sensors, edge compute, simulation, and training demand, but accident liability and hardware economics are stronger constraints than in software.

- ## Predictions and Falsifiers
	- | Prediction implied by the interview | Evidence that would support it | Evidence that would weaken it |
	  |---|---|---|
	  | Aggregate AI progress remains near-exponential | Continued capability gains from new base models, RL, tools, and post-training across successive releases | Broad benchmark and real-work progress flatten despite growing compute and data |
	  | Large pre-training runs regain emphasis | New capacity supports larger teacher models that materially improve distilled families | Frontier teachers stop transferring meaningful gains to smaller models |
	  | Reasoning expands beyond math and coding | Stronger results in law, finance, writing, multimodal tasks, and economic-work benchmarks | RL remains confined to easily verified domains or degrades taste and flexibility |
	  | Inference-time compute becomes a standard product tier | Adoption of variable thinking budgets, premium modes, and task-based routing | Users reject latency/cost or longer thinking yields little incremental success |
	  | Distillation expands rather than shrinks GPU demand | Smaller models drive much higher volume while frontier teacher runs continue growing | Serving efficiency rises faster than usage and labs reduce frontier training |
	  | Long-running coding agents approach intern-level utility | Reliable multi-day tasks, checkpoints, compaction, cluster access, and low intervention rates | Agents continue looping, losing state, or requiring near-continuous supervision |
	  | Applications retain value above foundation models | Durable gross retention for products owning data, workflow, trust, security, and verification | General models absorb domain context and execute reliably with minimal integration |
	  | Human review persists in high-exposure workflows | Review spending remains despite strong automation; accountability standards tighten | Organizations publish or execute consequential outputs without meaningful verification |
	  | Multimodal reasoning is a major next capability jump | Visual transfer improves, models learn from demonstrations, and robotics benchmarks accelerate | Simple perceptual/generalization failures persist after large multimodal training runs |
	  | Household robotics follows model capability with a lag | Reliable hardware exists when multimodal reasoning crosses the threshold, followed by controlled deployment | Safety incidents, cost, maintenance, or regulation prevent scalable commercial use |
