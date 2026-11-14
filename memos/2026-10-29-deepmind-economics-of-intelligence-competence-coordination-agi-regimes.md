tags:: [[AGI]], [[AI-economics]], [[labor]], [[wages]], [[agents]], [[multi-agent]], [[coordination]], [[market-concentration]], [[benchmarks]], [[compute]], [[Google-DeepMind]], [[$GOOGL]], [[Shane-Legg]], [[Alex-Imas]], [[OpenAI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-10-29
file-updated-at:: 2026-10-29

- ## DeepMind essay: competence changes the economy gradually, coordination changes it abruptly
	- **Source**: Alex Imas, Andrew Koh and Shane Legg, "The Economics of Intelligence: How and when does AGI lead to economic transformation?", Google DeepMind's DMI essay platform, Oct 29, 2026 (user-provided text). The formal model is in the companion paper "Organizing Intelligence" (arXiv 2611.05417). DMI says its pieces are "conversation starters" and not Google's official view.
	- **Thesis**: benchmarks measure the wrong thing. The economy is made of organizations, not individuals, so AI transforms it only when *organizations of agents* beat organizations of humans.
		- That depends on two separate thresholds: **competence** (individual skill) and **coordination** (how well agents work together).
		- Gains in competence move wages and prices smoothly and leave industry structure intact.
		- Coordination past a **"supercooperative threshold"** flips returns to scale from concave to convex. That causes sudden concentration, job losses and wage drops in large, standardized markets.
		- Today AI is strong on competence and weak on coordination. That is why the economy looks unchanged while wages and roles are already shifting.
	- Related: [[2025-07-23-lex-fridman-demis-hassabis-agi-predictions]], [[2026-11-12-steve-yegge-agent-factories-human-bottlenecks]], [[2026-11-06-steinsson-ai-commoditization-not-automation-labor]], [[2026-08-03-sf-controller-q2-economy-ai-boom-without-jobs]].
- ## The reasoning path
	- **Step 1. The individual agent is the wrong economic unit.**
		- Benchmarks test one agent in isolation, but economic outcomes come from organizations competing under supply and demand.
		- A model can beat every person one-on-one and still lose to a well-structured team. That is why organizations have been called "a form of superintelligence."
	- **Step 2. Humans are jagged in different directions, and firms combine them into "mosaic intelligence."**
		- In a quiz of 100 people across six domains (math, verbal, science, patterns, culture, economics), scores in one domain were not very predictive of scores in another.
		- Firms apply Ricardian comparative advantage internally: they assign specialists so the team covers gaps no member covers alone.
		- **Data point**: pairs of participants matched to complement each other beat random pairs by **32%**.
		- **Coordinators** look like the weakest workers on any solo benchmark (average at everything), yet earn some of the highest wages. They "maximize the output of the mosaic."
	- **Step 3. AI models are jagged in the *same* direction.**
		- Another copy of a model adds capacity but not breadth.
		- So an AI that beats the average human everywhere can still lose to a team of complementary humans. The question that matters is whether "an organization of AI agents can surpass an organization of humans."
	- **Step 4. AI differs from humans in two ways that matter economically.**
		- **Duplicability**:
			- Human expertise is in fixed supply. Scaling an industry means hiring further up the talent curve, which pushes up wages, and Ricardo's rents go to skills that can't be reproduced.
			- A model at a given capability can be rented in any quantity at the cost of compute. Once a model matches a human skill, ^^**"human wages become tied to the cost of compute."**^^
		- **Coordination**:
			- Coase asked why all production doesn't happen inside one big firm. The answer has been human limits: span of control, lossy handoffs (Polanyi: "we can know more than we can tell"), information loss in communication (Marschak and Radner's theory of teams) and misaligned career incentives.
			- Agents need not face these limits. Copies share weights and can pass full working state (codebases, derivations, entire context windows) with no career conflicts.
			- Historical precedent: the telegraph and railroad didn't make individual workers better. They improved handoffs, and that produced the modern firm.
	- **Step 5. Competence sets the level, coordination sets the scale: organizational scaling laws.**
		- Output per worker plotted against firm size has three phases:
		- | Phase | Coordination level | What happens |
		  |---|---|---|
		  | 1. Solo work | Below a basic floor | Agents cooperate so poorly that working alone wins |
		  | 2. Bounded scale | Between the floor and the tipping point | Today's world. Dividing work raises output at small firm sizes, then levels off and falls. More competence raises the curve without changing firm size. Better coordination (the coordinator) lets firms grow |
		  | 3. Unbounded scale | Above the **supercooperative threshold** | Each new member makes the team *more* productive. This breaks the "Coasean ceiling": firm size is limited only by market size |
	- **Step 6. Conclusion**: competence reshapes the economy gradually. Coordination transforms it abruptly, through jumps in firm concentration, employment and wages.
- ## The four regimes and three sectors
	- **The three sectors**:
		- **Deep scalable markets**: large, standardized industries such as software, logistics and finance, where demand can absorb massive volume.
		- **Niche markets**: specialized or custom work where bounded demand limits the payoff from scale.
		- **The relational sector**: goods and services where human involvement is part of the value, such as healthcare, teaching, services and craft.
	- | Regime | Competence | Coordination | Market structure | Employment and wages |
	  |---|---|---|---|---|
	  | **Minimal AGI** | Matches or beats the *average* human across tasks | Below threshold | Barely changes. Human mosaic teams still win deep markets. Industries stay fragmented. Small AI firms enter price-sensitive niches and push prices down | Headcounts intact. Wages for skills AI matches fall toward compute cost. Specialists and coordinators earn *more* |
	  | **Supercompetent AI** | Beats *every* human expert on every task except coordination | Below threshold | "Abundance without concentration": many lean, very productive firms, and cheap goods | Firms shrink. Routine specialist pay falls. Human coordinators who set direction and keep work aligned multiply output |
	  | **Supercooperative AI** | At minimal-AGI level | **Above threshold** | Sudden phase transition. Deep markets reorganize into a few large AI-only firms. Niche markets stay sheltered because bounded demand limits payoffs from scale | Wages drop abruptly in deep markets. Displaced workers move into niche and relational work, pushing wages down there |
	  | **ASI** | Above the supercompetent threshold | Above threshold | Deep markets stay concentrated. Lean AI firms now serve niches too | Pay in commoditized production is anchored to compute cost. The relational sector and new kinds of jobs may employ much of the workforce "at high real wages" |
	- **Two economies with nearly identical model competence** can look completely different if they sit on opposite sides of the supercooperative threshold: one fragmented and familiar, the other reorganized into a few AI-only firms.
	- **Where workers go under ASI**: agriculture and manufacturing automation made society richer, and spending moved to services, which grew in value and jobs.
		- The difference this time is that AI automates far more broadly.
		- The essay's answer is the relational sector, where human delivery adds value even when the tasks can be automated (healthcare, education), plus jobs not yet imaginable ("in 1950, who would have thought… 'software engineering'?").
		- This cites Pascual Restrepo's analysis that pay in fully automated industries is anchored to compute.
- ## The predictions
	- | Prediction | Reasoning behind it |
	  |---|---|
	  | **Today the economy sits at high competence and low coordination**, so it looks modest from the outside | Models match experienced specialists on self-contained work, but agent swarms hit diminishing returns quickly |
	  | **Today's labor-market signature**: leaner startups, flatter org charts, softer entry-level hiring "closest to benchmark tasks," and steady or rising demand for experienced people who direct work across teams | Competence gains lower the value of standalone specialist work and raise the value of coordination |
	  | **Wages and job roles move first**, well before GDP or industry concentration | Wage effects arrive before firms restructure. "Macro statistics of employment rates provide poor evidence that AI is not having an effect" |
	  | **More competence alone won't concentrate industries.** It gives cheaper goods across many lean firms | Coordination, not skill, caps firm size in phase 2 |
	  | **Crossing the supercooperative threshold triggers sudden concentration and wage drops** in software, logistics, finance and other deep markets, even with unremarkable individual agents | Returns to scale turn convex, so the largest AI organization wins |
	  | **Niche markets protect human teams until ASI** | Bounded demand can't reward scale, so only supercompetent lean AI firms can take them |
	  | **The relational sector and new job categories absorb workers** | The historical pattern of structural change: spending moves to what is still scarce |
	  | **Benchmarks and statistics will need to change**: multi-agent benchmarks for splitting work without duplication, clean handoffs, and catching rather than compounding errors over long horizons. National statistics that track payroll alongside compute spend | Solo leaderboards overstate how AI fares against complementary human teams and give no warning of how close the coordination tipping point is |
	- **Evidence that coordination still lags**: OpenAI's Noam Brown, on running thousands of agents in parallel on open math problems, said "it's actually very difficult to get these agents to coordinate in a productive way."
		- The swarms collapsed into agents working the problem independently.
		- Brown "wouldn't even attribute 10% of the credit to multi-agent" capabilities over single-agent performance.
	- **No timeline**: the essay never says when either threshold will be crossed. It argues only that coordination is the threshold to watch, and that current benchmarks don't measure it.
- ## My notes
	- **Compute becomes the wage anchor.** In every regime, pay for any skill AI matches converges to the rental cost of compute.
		- That makes compute the price-setting input across a growing share of labor, which supports long-run demand for compute and ties it to labor substitution, not just to model training.
		- Past the supercooperative threshold, demand in deep markets would jump: the winning firm adds agents indefinitely because each one raises productivity.
	- **The leading indicator to track is multi-agent coordination, not solo benchmarks.** The Brown quote puts frontier labs in phase 2.
		- Yegge's agent factories show the same thing from practice: human attention and quality control remain the bottleneck in running many agents ([[2026-11-12-steve-yegge-agent-factories-human-bottlenecks]]).
		- A credible multi-agent benchmark showing returns to adding agents would be the regime-change signal for this framework.
	- **Software is a deep scalable market, so it is the first candidate for concentration.**
		- Before the threshold, the model predicts many lean AI-assisted software firms and falling prices. That fits the vibe-coding pressure on low-end SaaS.
		- After it, the model predicts a few AI-only firms. That is a winner-take-most outcome whose winners could be the model owners or whoever runs the largest coordinated agent organization, rather than today's fragmented SaaS vendors.
		- *My note*: this is my extrapolation. The essay names software as a deep market but doesn't discuss vendors.
	- **The current data fit the minimal-AGI to supercompetent path**: AI investment rising without jobs ([[2026-08-03-sf-controller-q2-economy-ai-boom-without-jobs]]), and Steinsson's view that jobs get commoditized at lower wages rather than eliminated ([[2026-11-06-steinsson-ai-commoditization-not-automation-labor]]).
		- Both match "wages before structure."
		- The rising premium for coordinators also fits Goldman restricting coding agents to engineers while keeping its human hierarchy ([[2026-11-02-goldman-restricts-claude-code-github-to-engineers]]).
	- **A tension with Hassabis**: Hassabis predicts 10× the Industrial Revolution in about a decade ([[2025-07-23-lex-fridman-demis-hassabis-agi-predictions]]). This essay, co-written by DeepMind co-founder Shane Legg, implies the visible change waits on a capability neither benchmarks nor labs yet show.
		- On this framework, a fast transformation requires a coordination breakthrough, not just more scaling of individual models.
	- **Limits of the evidence**:
		- The regimes come from a theoretical model.
		- The empirical support is one 100-person quiz and the 32% pairing result.
		- The "relational sector at high real wages" outcome is stated as a possibility ("may expand"), not a derived result.
