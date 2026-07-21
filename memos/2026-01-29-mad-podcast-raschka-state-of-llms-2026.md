- tags:: [[AI]], [[LLM]], [[transformers]], [[mixture-of-experts]], [[post-training]], [[reinforcement-learning]], [[inference]], [[agents]], [[tool-use]], [[open-source]], [[private-data]], [[model-architecture]], [[AI infrastructure]], [[GPU]], [[$NVDA]], [[$MSFT]], [[$GOOGL]], [[$AMZN]], [[$META]], [[DeepSeek]]

- ## State of LLMs 2026: RLVR, GRPO, and Inference Scaling
	- **Source**: [The MAD Podcast with Matt Turck — “State of LLMs 2026: RLVR, GRPO, Inference Scaling — Sebastian Raschka”](https://open.spotify.com/episode/4kZjotQMlbFegGRY9PJr3U), published 29 January 2026; user-supplied transcript.
	- **Guest**: Sebastian Raschka, AI researcher, educator, and author of *Build a Large Language Model (From Scratch)*.
	- **Source-quality note**: Raschka discusses public research and personal experiments rather than company guidance. Several cost and model-name passages in the automated transcript are garbled. This memo includes only figures whose intended meaning is reasonably clear and labels reported costs as estimates.
	- **Thesis**: Frontier LLM progress is moving from a single capital-intensive pre-training curve to a broader stack of post-training, inference-time compute, tool use, model routing, and proprietary data. This can sustain AI infrastructure demand even if base architectures and model sizes plateau, but it changes the mix: more spend moves toward repeated inference, verifiers, reasoning tokens, secure execution, and domain-specific training. The resulting moats are more likely to sit in distribution, private data, workflow integration, and inference systems than in a marginal architectural tweak.

- ## Executive Takeaways
	- **Transformers remain the state-of-the-art production architecture**: text diffusion, Mamba/state-space models, and recursive models offer cost or specialization advantages, but none yet matches the general quality and versatility of leading autoregressive Transformers.
	- **Architecture is being optimized rather than replaced**: mixture-of-experts, sparse or latent attention, normalization changes, and other refinements improve efficiency. Raschka expects more efficient architectures rather than simply larger dense models.
	- **“Pre-training is not dead, but pre-training is boring”**: high-quality pre-training remains necessary, but the lowest-hanging capability gains now come from post-training and inference-time systems.
	- **RLVR is the reasoning unlock**: reinforcement learning with verifiable rewards removes expensive learned reward and value models from the training loop. In Raschka's small-model experiment, approximately 50 RL steps raised MATH-500 accuracy from about 15% to 50%, suggesting post-training can activate knowledge already present in the base model.
	- **Reasoning economics shift compute toward inference**: longer answers, best-of-N sampling, judge models, self-refinement, and recursive prompting improve accuracy by spending more compute per query. Better models therefore need not imply lower aggregate serving demand.
	- **Tool use is a major capability multiplier**: web search and code execution reduce reliance on memorized facts and can improve benchmark performance without changing model weights. The associated moat includes secure execution, permissions, context management, and interface engineering.
	- **Private data becomes the enterprise edge**: general frontier models are converging in perceived quality. Raschka expects well-capitalized finance, healthcare, defense, and other enterprises to build or train internal models rather than surrender proprietary data to outside labs.
	- **Benchmarks are saturating and increasingly gameable**: leaderboard style preferences, repeated exposure, and benchmark-specific tuning can improve scores without proportional real-world gains. Agent task completion and production outcomes should increasingly replace static benchmark deltas.
	- **Continual learning is not a credible 2026 product breakthrough**: catastrophic forgetting, data quality, shared model weights, and the operational risk of continuously updating huge production models remain unresolved.

- ## Key Data Points
	- | Data point | Raschka disclosure or example | Investment relevance |
	  |---|---|---|
	  | Transformer age | Introduced in **2017**, roughly eight to nine years before the interview | Longevity shows the architecture has become a durable platform rather than a short research cycle |
	  | Diffusion generation | A text diffusion model might use roughly **16 denoising steps** versus approximately **2,000 sequential token steps** for a long autoregressive answer | Parallel generation can be cheaper and faster, but may be less compatible with sequential reasoning and tool use |
	  | DeepSeek V3 scale | Approximately **670 billion parameters** in the transcript | Illustrates how MoE expands total capacity without activating every parameter on every token |
	  | Large MoE extension | Kimi was described as scaling a similar architecture toward approximately **one trillion parameters** | Open-model competition is converging on proven efficient scaffolds rather than wholly new architectures |
	  | RLHF model count | PPO-style RLHF can require a policy, reward model, and value model—effectively **three large models** in memory | Post-training architecture has major implications for GPU memory and training cost |
	  | RLVR/GRPO simplification | Verifiable rewards and relative group comparisons eliminate the separate reward and value models | Makes reasoning post-training materially more accessible and scalable |
	  | Raschka RLVR experiment | Approximately **15% to 50% MATH-500 accuracy after only 50 RL steps** on a Qwen3-based model | Suggests post-training can unlock latent capability rather than create all knowledge from scratch |
	  | Reported DeepSeek pre-training cost | DeepSeek V3 was associated with an estimated **\$5 million** training figure based on assumed GPU-hour pricing | Useful only as a relative public estimate; it excludes broader R&D, infrastructure, and failed runs |
	  | Reported DeepSeek R1 post-training cost | Approximately **\$300,000** in the cited paper, or more than **10x cheaper** than the V3 pre-training estimate | Supports reallocating marginal research budget toward RL post-training |
	  | Best-of-five inference | Running a prompt **five times** and choosing an answer costs approximately **5x** a single sample | Capability can rise through inference spending without any weight update |
	  | Longer reasoning | Twice as many generated tokens costs roughly **2x** as much under a simple token model | Reasoning creates variable cost per task and supports value-based routing or pricing |
	  | Tool-use uplift | Raschka recalls approximately **1.2x benchmark performance** for GPT-OSS with tools enabled versus disabled | System design can add meaningful capability to an unchanged base model |
	  | Benchmark decay | Models evaluated on refreshed data were described as approximately **5–10% worse**, while relative rankings remained similar | Absolute scores overstate real-world generalization even when rankings retain some information |
	  | Model architecture survey | Raschka's comparison had grown to approximately **13,000 words** because production models use many small variants | The competitive frontier is a large collection of incremental design choices rather than one universal recipe |
	  | Continual-learning timing | Raschka sees no major breakthrough in **2026** and treats even **2027** as speculative | Personalizing weights continuously is not yet a near-term assumption for model economics |

- ## Architecture: Stable Core, Expanding Efficiency Layer
	- Raschka would still choose a Transformer for a state-of-the-art general-purpose model in 2026. Alternative architectures mostly exchange quality, flexibility, or sequential control for lower cost.
	- A modern model such as DeepSeek V3.2 remains recognizably related to GPT-1 or GPT-2. The changes are meaningful but resemble progressively tuning the same engine:
		- **Mixture-of-experts (MoE)** increases total parameter capacity while activating only a subset per token.
		- **Multi-head latent attention** compresses attention state and reduces inference cost.
		- **Sparse attention** limits which prior tokens are processed, reducing long-context expense.
		- **Normalization placement and stability tweaks** make large runs more reliable but do not independently create a capability leap.
	- DeepSeek V3 became an influential open blueprint, with other developers adapting similar structures. This implies architectural knowledge diffuses quickly and is a weak standalone moat.
	- GPT-4.5 is cited as a warning against brute-force scale: a rumored larger model was too expensive relative to its utility, and the product direction moved toward GPT-5-style efficiency and reasoning.

- ## Alternative Architectures and Their Economic Roles
	- | Approach | Advantage | Limitation | Likely role |
	  |---|---|---|---|
	  | Autoregressive Transformer | Highest general-purpose quality; natural sequential reasoning and tool use | Sequential token generation is costly and slow | Frontier assistants, agents, coding, complex workflows |
	  | Text diffusion | Parallel generation can reduce the number of sequential steps | Quality falls unless denoising steps increase; awkward for interrupted generation and tools | Fast, low-cost tiers and bounded generation tasks |
	  | State-space/Mamba | Can improve efficiency on long sequences | Has not displaced Transformers at the quality frontier | Hybrid components and modality-specific workloads |
	  | Tiny or hierarchical recursive model | Small model repeatedly refines a latent answer; strong on narrow ARC-style tasks | Each task may require a separate model and repeated computation | Specialized reasoning modules used as tools by a general LLM |
	  | World-model objective | Trains a model to predict program state or physical evolution, not only the next token | Adds training complexity and is not yet a general replacement | Code understanding, robotics, simulation, and planning |
	- Raschka predicts that at least one company could launch a large text-diffusion model in 2026, but he expects it to compete on price or speed rather than replace the best general model.
	- Specialized recursive models demonstrate that tiny systems can beat large models on narrow benchmarks, but comparisons are misleading when a different specialist is trained for every task.
	- The likely end state is compositional: a general model routes work to cheaper specialist models, tools, or verifiers.

- ## Why Post-Training Has the Highest Marginal Return
	- Pre-training teaches broad knowledge through next-token prediction. Post-training changes how the model uses that knowledge, follows instructions, reasons, and selects actions.
	- Raschka's historical framing:
		- **2022**: RLHF and PPO transformed base GPT models into useful chat systems.
		- **2023**: LoRA and supervised fine-tuning broadened affordable customization.
		- **2024**: mid-training extended context and domain adaptation.
		- **2025**: RLVR and GRPO turned base models into stronger reasoning systems.
	- RLHF relies on subjective preferences. Humans rank answers, a reward model learns those preferences, and a value model helps stabilize policy optimization.
	- RLVR substitutes rewards that can be checked automatically:
		- Math answers can be parsed and compared to known solutions.
		- Code can be compiled and tested.
		- Citations can be checked against URLs and source metadata.
	- GRPO compares outputs within a group instead of maintaining a separate value model. The combination can reduce the number of large models required during training from three to one policy model plus inexpensive verification logic.
	- The sharp MATH-500 improvement after 50 steps suggests that much reasoning structure already exists in pre-training data. RLVR teaches the model to elicit and organize it reliably.

- ## RL Scaling Is an Engineering Curve, Not a Single Breakthrough
	- Vanilla GRPO can be unstable and requires checkpointing and monitoring. Models may train normally for hundreds or thousands of steps and then degrade suddenly.
	- Stability improved through a collection of practices: removing or modifying KL penalties, changing normalization, skipping groups with identical rewards, and handling multiple rewards more carefully.
	- NVIDIA's GDPO work is cited as an example of improving training with multiple signals such as answer correctness and output format.
	- Process reward models remain promising but immature:
		- Outcome rewards score only the final answer.
		- Process rewards attempt to score intermediate reasoning steps.
		- Grader models can be hacked or simply be wrong, sometimes requiring another model to grade the grader.
	- DeepSeek Math V2's multi-model self-refinement system achieved stronger math results but at the cost of more training and inference. This exemplifies the new scaling stack: model count, sampling, and verification rise even when the base model does not.
	- **Infrastructure implication**: post-training may be cheaper than a new frontier pre-training run, but its accessibility can multiply the number of organizations and experiments consuming GPUs.

- ## Inference Scaling: Capability Purchased Per Query
	- Inference scaling spends additional compute after training rather than embedding every improvement in model weights.
	- Major mechanisms include:
		- **Longer chain-of-thought**: more generated tokens allow additional intermediate steps.
		- **Parallel sampling**: generate several answers and select by majority vote or a judge.
		- **Self-refinement**: ask the same or another model to critique and revise an answer.
		- **Recursive prompting**: divide a large prompt into smaller pieces, process them separately, and synthesize the results.
		- **Model cascades**: use specialists, draft models, verifiers, and judges around the primary model.
	- This changes the unit of analysis from cost per token to cost per successful task. A five-sample answer can be economically superior if it materially raises completion probability on valuable work.
	- Product interfaces hide much of the stack. Prompt cleanup, context selection, memory, retrieval, routing, and tool calls can make a proprietary service feel better than the same open model served locally.
	- **[[$NVDA]] read-through**: inference-time scaling can offset improvements in cost per token by raising tokens, samples, and models invoked per task. The demand risk is that routing and smaller specialists reduce compute faster than task volume expands.

- ## Tool Use and Secure Execution
	- Tools reduce the burden on model weights. An LLM can search current information, call a calculator, run Python, or query a database instead of memorizing or approximating the result.
	- A roughly 1.2x tool-enabled benchmark uplift is directionally important because it comes without a new base model.
	- Tool use introduces a new systems moat:
		- Secure sandboxes and containers for generated code.
		- Fine-grained permissions, credentials, and audit trails.
		- Reliable tool selection and schema handling.
		- Recovery when tools fail or return adversarial content.
		- Context management across multiple calls and long-running tasks.
	- Closed providers initially hold an advantage because code runs on their controlled infrastructure. Open models become more competitive as local sandboxing and agent tooling mature.
	- **Cloud read-through**: [[$MSFT]], [[$AMZN]], and [[$GOOGL]] can monetize not only model tokens but also search, databases, code execution, storage, observability, and security surrounding every agent task.

- ## Benchmark Saturation and the Move to Agent Evals
	- Static benchmarks are increasingly exposed to repeated tuning, contamination, and leaderboard incentives.
	- Human preference leaderboards can reward fluent style over correctness when evaluators do not know the answer.
	- Refreshed benchmark data can lower every model's absolute score while preserving rank order. This means leaderboards may still show relative strength while overstating real capability.
	- Raschka increasingly evaluates models through personal use because small quality differences are difficult to summarize numerically.
	- The next evaluation frontier is long-horizon work: whether an agent can design or build something, how long it operates before failure, how often humans intervene, and whether the final artifact is correct.
	- **Investor implication**: model launches should be judged using production retention, task completion, error cost, inference spend, and workflow adoption—not a few saturated benchmark points.

- ## Private Data and the Return of In-House Models
	- General-purpose models from OpenAI, Google, Anthropic, xAI, and leading open developers are converging for many common tasks. Private data offers a way to create economically meaningful differentiation.
	- Finance companies may have decades of proprietary records; healthcare organizations hold sensitive longitudinal patient data; defense companies have classified or restricted corpora. These organizations cannot casually transfer the data to a third-party model provider.
	- Raschka says large enterprises with sufficient capital are hiring teams to train substantial models internally, in some cases contemplating data-center-scale development rather than only fine-tuning an open checkpoint.
	- **Bull case for hyperscalers**: internal models still need accelerators, storage, networking, orchestration, and managed training infrastructure. The customer shifts from buying only an API to operating a broader cloud stack.
	- **Pressure on model labs**: proprietary data stays outside the general model, limiting data flywheels and creating bargaining power for large customers.
	- **Application-software implication**: systems of record retain leverage if they control clean domain data, permissions, and workflow feedback. Thin interfaces without proprietary context are more exposed.

- ## Continual Learning: Important but Not Investable Yet
	- The attractive vision is an agent that fails, updates its weights, and performs better next time without waiting for a centrally managed model release.
	- Major barriers remain:
		- **Catastrophic forgetting**: learning a new behavior can damage old capabilities.
		- **Garbage feedback**: autonomous systems can train on incorrect or adversarial outcomes.
		- **Shared weights**: most users access the same base model; personalization currently lives in prompts and memory rather than model parameters.
		- **Operational risk**: updating a massive production model continuously is expensive, hard to monitor, and difficult to roll back safely.
	- Current practice is controlled iteration: collect failures, curate a dataset, retrain or post-train, evaluate, and release a numbered model revision.
	- APIs that make customer-specific fine-tuning easier are a step toward personalization but are not continual learning.

- ## 2026 Predictions
	- | Prediction | Raschka view | Stock or industry implication |
	  |---|---|---|
	  | Transformers remain the frontier default | High confidence | Preserves value of mature GPU software and optimized attention stacks |
	  | MoE and efficiency refinements spread | High confidence | More total parameters but lower active compute per token; increases routing and memory-system importance |
	  | Post-training attracts better marginal returns than brute-force pre-training | High confidence | Broadens GPU demand across more training runs and organizations |
	  | Inference scaling remains a major capability driver | High confidence | Supports token growth, judge models, verifiers, and premium task pricing |
	  | Tool use expands rapidly | High confidence | Benefits cloud execution, search, databases, observability, and security |
	  | A large text-diffusion model launches | Medium confidence | Could pressure low-cost inference pricing without displacing frontier autoregressive models |
	  | Companies train on private data internally | Medium-high confidence | Benefits infrastructure providers; weakens exclusive data advantage of model labs |
	  | Benchmarking moves toward agentic, long-horizon tasks | High confidence | Product telemetry and domain evals become more valuable than public leaderboards |
	  | Continual learning does not break through in 2026 | High confidence | Prompt memory, retrieval, and periodic fine-tuning remain the practical solutions |
	  | Meaningful continual-learning progress may appear in 2027 | Low confidence | Optionality rather than a base-case revenue driver |

- ## Stock Read-Throughs
	- **[[$NVDA]] — demand mix shifts, platform value persists**
		- MoE, RLVR, judge models, best-of-N sampling, and tool-using agents create compute demand beyond base-model pre-training.
		- Transformers remaining dominant supports CUDA and established kernel ecosystems, while frequent architectural tweaks reward programmable accelerators.
		- Counterpressure comes from sparse activation, smaller specialists, diffusion, and better routing, all of which reduce compute per task.
		- The decisive variable is total successful-task growth, not the FLOPS required by one forward pass.
	- **[[$MSFT]], [[$GOOGL]], and [[$AMZN]] — the full agent stack matters more than model access alone**
		- Inference scaling monetizes repeated calls, while tool use pulls through search, databases, storage, execution, and security.
		- Enterprise in-house training can expand cloud infrastructure revenue even if customers rely less on a hyperscaler's proprietary foundation model.
		- Competition remains intense because model quality is converging and open weights constrain API pricing.
	- **[[$META]] — open-weight influence versus monetization gap**
		- Open models shape architecture, developer tooling, and cost expectations, but benchmark controversy or weak real-world quality can damage ecosystem credibility.
		- Private enterprise models validate open-weight distribution strategically, though direct value capture depends on engagement, advertising, devices, and infrastructure efficiency.
	- **Enterprise software — data gravity is the defense**
		- Systems holding proprietary, permissioned, longitudinal data can become the context and verification layer for agents.
		- Vendors whose value is mostly interface and generic workflow logic face greater replication risk as tool-using models improve.
		- Observability, identity, governance, audit, and data-quality platforms gain importance as agent actions multiply.

- ## Scenario Framework
	- | Scenario | Technical development | Economic result | Equity impact |
	  |---|---|---|---|
	  | Inference-scaling boom | Reasoning, best-of-N, tools, and agent loops materially raise task success | Spend per valuable task rises despite cheaper tokens | Bullish for accelerators, hyperscalers, and agent infrastructure |
	  | Efficient-specialist shift | MoE, small models, diffusion, and routing reduce compute faster than task volume grows | API prices and GPU intensity fall | Benefits users and application owners; pressures model and infrastructure margins |
	  | Private-model proliferation | Large enterprises train or heavily customize models on proprietary data | Infrastructure demand decentralizes; data owners retain economics | Bullish for cloud training stacks and systems of record; mixed for closed labs |
	  | Evaluation crisis | Benchmarks cease to predict production value and agents remain unreliable | Adoption slows while verification costs stay high | Benefits observability, security, and incumbents with human workflow control |

- ## Key Tests for the Thesis
	- **Compute mix**: post-training and inference growth relative to frontier pre-training spend.
	- **Reasoning elasticity**: whether users pay for higher success rates when tasks consume 2x or 5x more inference.
	- **Tool adoption**: production frequency of web, code, database, and enterprise-application calls per model interaction.
	- **Private-model evidence**: disclosed enterprise training clusters, hiring, fine-tuning volume, and workloads moving away from public APIs.
	- **Specialist routing**: share of traffic served by smaller models versus the largest frontier model.
	- **Real-world evals**: task completion, human intervention rate, defect rate, and retention after model upgrades.
	- **Continual-learning progress**: evidence that personalized weight updates avoid forgetting and can be deployed with reliable rollback.

- ## Bottom Line
	- The episode argues for an AI progression built from many compounding improvements rather than another Transformer-scale breakthrough. The absence of a new architecture does not imply stalled capability or stalled compute demand.
	- Model economics are becoming system economics: post-training recipes, inference budgets, verifiers, tools, routing, security, and private data determine the cost and value of a completed task.
	- Hardware demand remains supported if cheaper computation expands reasoning depth and agent activity faster than efficiency reduces cost. If not, the value pool shifts toward clouds, data owners, and applications that orchestrate cheaper models.
	- For stock selection, the durable assets are programmable infrastructure, distribution, proprietary data, workflow control, and the ability to measure and verify outcomes—not a temporary lead on a saturated benchmark.
