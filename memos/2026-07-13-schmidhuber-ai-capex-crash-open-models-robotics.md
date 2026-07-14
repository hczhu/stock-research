- tags:: [[AI]], [[AI infrastructure]], [[capex]], [[open-weight-models]], [[robotics]], [[AGI]], [[recursive-self-improvement]], [[artificial-scientists]], [[model-labs]], [[inference]], [[GPU]], [[$NVDA]], [[$MSFT]], [[$GOOGL]], [[$META]], [[$AMZN]], [[hyperscalers]], [[transformers]], [[AI-safety]], [[podcast]]

- ## Juergen Schmidhuber: AI Capex, Open Models, and Physical Intelligence
	- **Source**: User-provided transcript of the `Unsupervised Learning` podcast hosted by Jacob Efron, featuring AI researcher Juergen Schmidhuber; source date not included, accessed July 13, 2026. The transcript contains speech-recognition errors, so figures below are presented as the guest's approximate claims rather than independently verified facts.
	- **Core view**: Schmidhuber is highly optimistic about AI's long-run technological impact but deeply skeptical of current AI investment economics. He expects rapid efficiency gains and open-model diffusion to erode pricing, impair today's expensive infrastructure, and trigger a stock-market normalization. At the same time, he thinks true general intelligence requires physical robots and self-directed scientific experimentation, both of which may take decades rather than years.

- ## Executive Summary
	- **Technology bull, current-equity bear**: AI will become dramatically more capable and ubiquitous, but the companies financing today's buildout may not capture the resulting value.
	- **Efficiency is endogenous to intelligence**: Intelligent systems optimize for less computation, energy, and effort, so successful AI research should continuously reduce the resources needed for a fixed task.
	- **Frontier-model pricing is structurally vulnerable**: Open models can catch benchmark leaders within months, limiting the prices closed providers can charge and weakening returns on proprietary training infrastructure.
	- **Recursive self-improvement is unlikely to be a durable corporate moat**: Core ideas diffuse through researchers, universities, open-source communities, and small laboratories.
	- **Today's AI is incomplete**: Passing conversational tests or mastering screen-based tasks does not constitute full AGI if systems cannot operate robustly in the physical world.
	- **Artificial scientists are the next major paradigm**: Future systems will choose experiments, collect their own data, build world models, and invent useful questions rather than relying primarily on human-generated web data.
	- **Near-term market prediction**: Current capital misallocation should eventually produce an AI-related stock-market crash or valuation reset, not a collapse of AI progress or civilization.

- ## Key Quantitative Claims and Predictions

	| Topic | Schmidhuber's Claim | Investment Read-Through |
	|---|---|---|
	| Compute improvement | Compute per dollar has historically improved by roughly **10x every five years** and may continue near that rate | A fixed workload could become much cheaper before today's infrastructure is fully depreciated. |
	| Five-year cost comparison | The same computation may cost about **one-tenth** as much after five years | New hardware can undercut the operating economics of current clusters. |
	| Ten-year cost comparison | The same computation may cost about **1%** as much after ten years | Long-duration return models are highly sensitive to utilization and residual-value assumptions. |
	| Thirty-year comparison | AI may perform roughly **one million times** as much work for the same price | Long-run AI abundance does not guarantee high margins for today's suppliers or model labs. |
	| Hypothetical infrastructure impairment | Of **\$1 trillion** invested in GPUs and data centers today, he suggests roughly **\$900 billion** could be economically lost within five years | This is his most bearish and least substantiated forecast; it assumes efficiency gains overwhelm demand growth and reuse value. |
	| Current annual buildout | A few companies are spending **hundreds of billions of dollars each**, perhaps around **\$1 trillion per year** in aggregate | Concentrated hyperscaler spending creates correlated capital-cycle risk. |
	| Free-cash-flow compression | A company generating about **\$100 billion** could fall toward **\$10 billion** or even **negative \$10 billion** as infrastructure spending rises | Earnings multiples can obscure cash deterioration when capex is capitalized and depreciation lags spending. |
	| Open-model catch-up | An open model may catch a commercial benchmark leader within **a few months** | Frontier capability leads may not last long enough to support premium pricing. |
	| Physical AGI timing | Human-competitive robot hardware may take **a few decades**, not merely a few years | Robotics revenue expectations may be much earlier than robust general-purpose hardware capability. |
	| Transformer horizon | Some form of transformer may remain important for the next **five to ten years** | Architecture persists, but efficiency-focused variants may change compute demand per workload. |
	| Sequence scaling | With **1,000x** more text, a linear architecture needs about **1,000x** more compute, while quadratic attention can require **one million times** more | Linear or log-linear architectures could sharply reduce long-context infrastructure requirements. |

- ## Recursive Self-Improvement
	- Schmidhuber traces self-improvement research across several decades:
		- **1984**: self-referential machines using reinforcement-learning concepts and universal programming languages to generate code modifications.
		- **1987**: meta-evolution, where evolutionary programs improve the procedures used to evolve subsequent programs.
		- **1992**: neural networks that alter their own weight matrices by running learned update procedures on themselves.
		- **2003**: the Goedel Machine, which searches for a formal proof that a self-modification will increase expected lifetime reward before executing it.
	- The Goedel Machine is mathematically general but less practical because proof search is computationally expensive.
	- Current systems are simplified forms of self-improvement: gradient descent trains networks to generate better weight changes or code revisions.
	- These systems can learn new tasks faster through meta-learning, but remain constrained by differentiability and the limitations of gradient descent.
	- Schmidhuber expects progress to look abrupt from a historical perspective but potentially gradual to people living through it; he is uncertain whether human-surpassing AI is a few years or a few decades away.

- ## Why Recursive Self-Improvement May Not Be a Moat
	- Most foundational AI algorithms originated in small academic groups rather than in capital-rich corporations.
	- PhD students and open-source researchers work on the same self-improvement ideas as frontier laboratories.
	- Research knowledge diffuses through papers, personnel movement, replication, and open implementations.
	- A leading lab might briefly discover a superior self-improvement loop, but Schmidhuber assigns only a remote probability to one company sustaining enough advantage to monopolize AGI economics.
	- His base case is continued democratization: AI becomes cheaper, more researchers participate, and today's impressive capabilities become commodities.
	- **Stock implication**: Model companies need moats beyond recursive improvement itself, such as distribution, proprietary workflow data, customer integration, brand, regulated access, or lowest-cost infrastructure.

- ## Artificial Scientists and Self-Generated Data
	- Web-trained models are deeply biased toward human language, human interests, and content that at least one person considered worth publishing.
	- The web is only a tiny fraction of all possible observations and experiments in the physical world.
	- A more general artificial scientist would:
		- Select its own actions and experiments.
		- Observe the consequences.
		- Train a world model on the resulting data.
		- Use that model to plan additional experiments.
		- Invent new questions rather than only answer human prompts.
	- Schmidhuber links this to his **1990** work on artificial curiosity and later work on a formal theory of creativity and fun.
	- The intrinsic reward is learning compression progress: the system seeks data containing patterns it could not previously represent efficiently but can now learn.
	- Once a pattern is understood, it becomes boring, pushing the agent toward harder experiments at the boundary between known and unknown.
	- This is analogous to infant learning: babies manipulate the world and predict sensory consequences rather than downloading a static corpus.

- ## Scientific and Industrial Applications
	- Specialized artificial scientists already exist, but have not yet had a ChatGPT-scale public breakthrough.
	- In chemistry, neural networks can train on **millions of input-output experiment pairs** and develop an intuitive ability to predict substances or reactions without deriving every result from first principles.
	- Desired properties can be specified at the output, then the model can work backward toward experimental inputs likely to produce them.
	- Schmidhuber cites a project involving metal-organic frameworks intended to extract carbon dioxide from ambient air at much lower cost.
	- The larger opportunity spans chemistry, materials, biology, and automated laboratories where AI chooses experiments and closes the discovery loop.
	- **Prediction**: The decisive breakthrough will be autonomous question generation and experimentation, not simply better retrieval from scientific literature.

- ## Robotics and Physical AGI
	- Schmidhuber rejects the idea that a conversational system behind a screen is sufficient for AGI.
	- Human bodies remain far ahead of engineered robots:
		- A hand contains millions of sensors and control connections.
		- It combines high-force grips with precise manipulation.
		- Biological tissue can heal after damage.
	- Better models can improve current robots, but hardware reliability, sensing, actuation, dexterity, energy efficiency, and self-repair remain fundamental bottlenecks.
	- This makes physical-AI timing harder to forecast than compute scaling; general-purpose home robots may require decades.
	- A nearer threshold may be robots capable of operating the machines humans already use. A coordinated set of such robots could manufacture additional robots, creating self-replicating and eventually self-improving machine societies.
	- Schmidhuber's very long-run vision extends self-replicating robotics beyond Earth, where machines could use extraterrestrial materials to build infrastructure and expand through the solar system.

- ## AI Capex Bear Case
	- The largest technology companies are changing from asset-light software businesses into capital-intensive utilities that must finance data centers, power plants, gas turbines, and nuclear capacity.
	- Accounting earnings may not reveal the deterioration immediately because capex reduces free cash flow before it fully reaches the income statement through depreciation.
	- Debt-financed expansion can prolong the buildout but also raises fixed obligations and financial risk.
	- Falling unit costs create a treadmill: companies buy more hardware to compensate for the fact that existing hardware is not yet cheap or capable enough, while each generation threatens the economics of the prior one.
	- Closed model providers cannot simply raise prices because open alternatives remain close enough to constrain customers' willingness to pay.
	- Schmidhuber expects supply and demand eventually to force uneconomic services and projects out of the market.
	- His forecast is a re-normalization of highly valued AI companies through a stock-market decline, followed by capital reallocation toward more efficient approaches.

- ## Counterarguments to the Crash Thesis
	- **Demand elasticity**: A 10x reduction in compute cost can create more than 10x growth in tokens, agents, video, simulation, scientific workloads, and always-on inference.
	- **Old hardware can migrate down-market**: Prior-generation GPUs may remain useful for inference, fine-tuning, batch jobs, sovereign workloads, and customers with lower performance requirements.
	- **Efficiency can increase total compute consumption**: Jevons paradox may apply if lower prices unlock applications and raise utilization faster than cost per task falls.
	- **Infrastructure owners have distribution**: Hyperscalers can bundle compute with storage, data, identity, security, databases, and enterprise contracts, creating value beyond raw model performance.
	- **Frontier economics may be winner-skewed**: Even if average labs lose money, a provider with a capability, distribution, or data advantage could capture outsized returns.
	- **Depreciation schedules already assume obsolescence**: Economic loss depends on utilization and cash generation relative to purchase cost, not merely on newer chips becoming more efficient.
	- **Power and physical capacity remain scarce**: Faster chips do not eliminate constraints in electricity, transmission, networking, memory, cooling, permitting, and construction.
	- **The \$900 billion impairment estimate is a scenario, not a model**: The transcript does not provide utilization, pricing, depreciation, demand, or residual-value assumptions sufficient to substantiate it.

- ## Model-Company Economics
	- **Bearish factors**:
		- Short benchmark leads.
		- Open-weight catch-up.
		- High training and inference costs.
		- Pricing pressure from close substitutes.
		- Dependence on debt or external capital.
		- Weak ownership of foundational research ideas.
	- **Potential durable advantages omitted or discounted by the guest**:
		- Proprietary user interactions and reinforcement signals.
		- Enterprise distribution and switching costs.
		- Workflow-specific integrations and permissions.
		- Consumer brand and default status.
		- Inference optimization, hardware access, and scale purchasing.
		- Safety, compliance, and regulated-industry credibility.
	- **Prediction**: Standalone model pricing should commoditize faster than application, distribution, or proprietary-data economics.

- ## AI Safety View
	- Schmidhuber has been less concerned than many alignment researchers since the safety debates of the 2010s.
	- He argues there is no universal human objective: individuals, governments, militaries, and intelligence services have conflicting goals.
	- Systems capable of inventing scientific questions will also need to modify or create their own objectives, making permanent alignment to one fixed reward function unrealistic.
	- Autonomous goal formation increases unpredictability, but he compares machine socialization to raising children through feedback, rewards, and punishment.
	- He expects advanced artificial scientists to value life, civilization, and their own origins as rich sources of interesting patterns, giving them reasons to preserve rather than destroy humanity.
	- **Risk caveat**: This is a philosophical expectation, not a demonstrated safety mechanism; autonomous systems, military deployment, and conflicting actors still create substantial tail risk.

- ## Architecture Outlook
	- Schmidhuber expects transformer-like systems to persist over the next five to ten years, but with more efficient attention and memory mechanisms.
	- He favors linear or near-linear scaling over the quadratic attention complexity associated with the 2017 transformer.
	- He points to earlier fast-weight or unnormalized linear-transformer concepts and newer hybrids such as xLSTM.
	- The economic direction is consistent with his broader thesis: intelligence means performing the same task with less compute and energy.
	- **Semiconductor implication**: Architectural efficiency is a demand risk per workload, but can also broaden feasible context lengths and applications enough to expand aggregate compute.

- ## Investment Implications
	- **Model labs**: Treat current revenue growth separately from long-run gross-margin durability. Open-model parity and efficiency gains may compress pricing before infrastructure costs fall.
	- **Hyperscalers**: Track free cash flow, debt, depreciation, and power commitments rather than relying only on earnings or cloud revenue growth.
	- **Nvidia and accelerators**: The central debate is whether workload growth and system complexity exceed efficiency gains and generational obsolescence. Unit demand can stay strong even if customer returns deteriorate temporarily.
	- **Robotics**: Near-term value is more credible in constrained industrial tasks than in general-purpose humanoids or home robots; hardware remains the limiting layer.
	- **Scientific AI**: Automated experimentation in chemistry, materials, and biology may create more defensible data loops than web-trained general models because the systems generate proprietary physical results.
	- **Applications and distribution**: Falling model costs transfer value toward companies that own customers, workflows, proprietary feedback, and transactions.
	- **Market timing**: Schmidhuber gives no timing for the predicted stock-market reset. Rapid technological progress can coexist with an extended period of poor infrastructure returns.

- ## What to Monitor
	- Compute cost per standardized training and inference workload across hardware generations.
	- Token and agent demand elasticity as inference prices decline.
	- Utilization, pricing, depreciation, and residual value of prior-generation GPU fleets.
	- Hyperscaler free cash flow after capex, debt issuance, lease commitments, and power-project financing.
	- Closed-versus-open model capability gaps and the time required for open models to reach parity.
	- Frontier-lab gross margins after inference subsidies and enterprise discounts.
	- Evidence that recursive self-improvement creates a sustained lead rather than rapidly diffusing.
	- Autonomous-lab adoption and the volume of proprietary experimental data generated without human selection.
	- Robotics progress in dexterity, sensing, actuation, battery life, reliability, and self-repair.
	- Adoption of linear-attention, state-space, xLSTM, and other architectures that reduce quadratic scaling.
	- AI infrastructure write-downs, project cancellations, distressed financing, or materially extended depreciation schedules.
	- Whether AI-related equity corrections originate in demand shortfalls, financing costs, technological obsolescence, or margin compression.
