tags:: [[$META]], [[Meta]], [[MSL]], [[Muse]], [[Muse-Wonder]], [[Muse-Spark]], [[AI]], [[agents]], [[pre-training]], [[reinforcement-learning]], [[benchmarks]], [[distillation]], [[agentic-commerce]], [[OpenRouter]], [[Stripe]], [[$CART]], [[talent]], [[org-design]], [[podcast]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-10
file-updated-at:: 2026-11-10

- ## Cheeky Pint with Zuckerberg and Wang: data points and anecdotes from the Muse Wonder launch
	- **Source**: *Cheeky Pint* podcast, John Collison (Stripe) with Mark Zuckerberg and Alexandr Wang, recorded around the Muse Wonder launch. User-provided auto-generated transcript, undated.
		- Speakers are often not labeled, so attribution below follows context. Garbled names are corrected where obvious: Nat Friedman, Daniel Gross, Susan Li (CFO), CJ Desai, Adam Mosseri, Kunal Shah.
		- This is a launch conversation by management. Model-quality claims rest on Meta's own evaluations.
		- **Companion memo**: [[2026-10-15-cheeky-pint-zuckerberg-meta-ai-vision-and-execution]] covers the same conversation's strategy, capex figures (\$15B a year to run 1 GW, \$50–60B to build it), monetization paths and capital-risk argument. This memo adds what that one leaves out: how the model was trained, team size, internal anecdotes, usage stories and industry trends.
		- Related: [[2026-11-05-meta-msl-flat-lab-open-weight-crown-commentary]], [[2026-09-21-apptopia-muse-launch-metrics-vs-chatgpt]], [[2026-11-06-semianalysis-gdpx-frontier-agent-performance]], [[2026-10-28-ai-demand-openrouter-app-bottleneck]], [[2026-07-09-mad-podcast-emily-sands-stripe-agentic-commerce-token-fraud]], [[META-2026-Q2]].
	- **What's new here**:
		- **MSL is small.** The research team is under 200 people, "closer to a hundred" plus infrastructure staff. Each training stage has tens of people, not hundreds as at other labs. Meta concentrates compute on these researchers instead of spreading it across competing efforts.
		- **Post-training does a lot of the work.** Muse Spark 1.0 to 1.3 used the same pre-trained model, with only more RL, and Wang says the difference feels "night and day." The new, bigger pre-train (Wonder) beat Spark almost immediately after RL started.
		- **The industry stays competitive.** Wang gives three reasons no lab has run away: execution swings at every lab, distillation (an "anti-hegemonic force"), and researchers and companies choosing not to back a single winner.
- ## Muse Wonder: launch facts
	- | Item | Detail |
	  |---|---|
	  | Models | **Muse Wonder** and **Muse Wonder Full** (a much higher-end version) |
	  | Internal codenames | Avocado = Muse Spark line; **Watermelon** = Muse Wonder line. The next fruit up would be durian, so the naming scheme is changing |
	  | Lineage | Spark came from a pre-train finished at the end of 2025. Wonder is the next, "significantly bigger" pre-train, planned since about August 2025. Each rung on the ladder is about 4–5× bigger |
	  | Version naming | Wonder has no number yet. At Meta the version number marks the pre-train and point releases are more RL |
	  | Availability | Paid Muse subscriptions (Spark stays free, with a large pool of free tokens), Meta model API, OpenRouter, Muse Code. Wonder Full is for Muse Code subscribers |
	  | Selectors | No model or effort picker in Muse. Paying users "just get better" results |
	  | Claimed strengths | Active memory, "active focus" (persistence on long tasks), domain expertise (state of the art on several finance and legal evals), coding (state of the art on two SWE-style benchmarks, strong on Terminal-Bench; names garbled in transcript) |
	  | Serving | Much more expensive to serve, so paid first. The aim is a future Spark-sized model as good as Wonder for "hundreds of millions" of users |
	- **Active memory**: both the model and a system around it are trained to remember things over days, weeks or months and to manage their own context compaction. Collison called memory in OpenClaw "pretty bad" after long use. Meta has an internal "memory bench" and admits "there's still plenty of room to improve."
	- **Where Wonder is meant to be good**: shopping, personal advice, and personal legal, health and tax questions. The goal is "a team of experts in your corner." Domain data goes in at pre-training, not only through RL at the end.
	- **Coding is a minority use**: users who code "will be a minority of all of our users," but they get a big step up.
	- **Positioning against rivals**: by benchmarks, Wonder sits at the frontier with competing models Fable and Astra (garbled in the transcript). Wang says the labs are now "focus[ing] in quite different directions."
- ## How the model was built: training insights
	- **Pre-training**:
		- Data is roughly the public internet, every book they can get, Meta's proprietary data, and images, audio and video for perception.
		- **Data is the scaling problem**: "if the internet isn't growing that quickly … where's the data coming from?" Bigger models need more data or they overfit. Some data types help each other and some hurt, which Meta keeps as a trade secret ("we have secrets").
		- **The stakes**: Meta put "a huge percentage of our compute" into the Wonder pre-train. With few samples to learn from, researchers go through "all the seven stages of grief." Perplexity-based evals guide pre-training; benchmarks guide RL.
		- Each change has to be re-tested up the ladder of model sizes, so research compute is "probably an equal amount" to the main run.
		- **The vibes are literal**: researchers hold real protractors to their monitors to measure the angle of loss curves.
	- **Post-training**:
		- Supervised fine-tuning (SFT) sets up behaviors and personality. After SFT a behavior may appear only about 10% of the time; RL raises that a lot.
		- **Scaling RL** with more compute and data is a main source of gains, and it has to scale along with pre-training. "Scale everything … scaling one thing in isolation does not work."
		- **"Less is more" with RL data**, which is the opposite of pre-training. The quality of the environments matters more than how many there are.
		- The agent harness is another scaling axis, optimized together with the model.
	- **Benchmarks**:
		- Early on, external benchmarks were "signs of life." With each release a larger share of the evals Meta steers by are internal.
		- Wang's critique: relying on a viral public benchmark is "outsourcing all of your product thinking to that PhD student" who built it.
		- MSL keeps "a spreadsheet of all the little capabilities," each worth perhaps 2% to the user, that add up to a model that feels "magical."
		- **"Big model smell" as a metric**: Meta measures the gap between performance on tasks inside its RL training distribution and tasks outside it. The gap narrows sharply from Spark to Wonder, which they credit to the better base model.
	- **Alignment**:
		- Alignment runs through the whole RL process, not separate safety steps. Environments are curated so the model never succeeds only by doing something misaligned, because high-compute RL amplifies whatever it rewards.
		- Meta defines alignment as following the user's instructions and values: "You don't want a moralizing lecture," but the model should "gracefully" refuse catastrophic requests. Zuckerberg contrasts this with other labs.
		- **Discretion**: the model should act for you while revealing as little about you as possible, for example booking a restaurant around an allergy or pregnancy without disclosing it. Coding agents don't need this, so it gets more weight at Meta.
	- **Product = model**: "the model is the product." Product work on Muse is mostly the privacy and security model (a dedicated VM per agent) plus post-training. When Nat Friedman (the product lead) thinks about making Muse feel good, "he's talking about post-training the model."
- ## MSL team and decision anecdotes
	- **The recruiting timeline**:
		- Llama 4 launched April 4, 2025. Around April 20–21 Zuckerberg sent Wang a WhatsApp message asking if he had time for a call. They talked for about 44 minutes.
		- Two days later Wang sent a long plan whose first point was that **talent density, not headcount, is what matters**.
		- Nat Friedman and Daniel Gross joined next. Zuckerberg cleared his calendar for one to two months to meet researchers.
	- **The full reboot was decided while recruiting**: they weren't sure at first that a full restart was needed. Talking to top researchers showed that "starting this thing again from scratch" would make it most attractive, while still pulling in people from Llama and FAIR.
	- **The reasoning-model meeting**: in one of Wang's first meetings, he said the top milestone was a strong reasoning model. A lead of the existing effort (no longer at Meta) replied that consumers don't need one. Wang called it a "heart sinking moment … I've joined the wrong place," and phoned Friedman afterward. It signaled that Meta's leadership needed to become "much more AI-pilled."
	- **The Hawaii offsite (end of 2025)**: before Wonder existed, the exec team weighed a check of about \$100–200B. CFO Susan Li pulled Zuckerberg aside "many times": if this doesn't work, "it's going to be very, very bad in financial terms." Some executives wanted to be more conservative; Zuckerberg said "we're doing this." Wang: "this is a fuck ton of risk."
	- **Muse surprised them**: the median internal expectation was a few iterations before product-market fit, so "we didn't have all the growth stuff really ready to go." Zuckerberg thinks it could have grown faster. Collison says third-party reports suggest it may be the fastest-growing agentic AI app yet.
	- **Culture**:
		- The lab is deliberately flat. Wang has close to 200 direct reports ("not quite that extreme in practice"), and "my Muse helps me manage them."
		- Zuckerberg says the point is "the absence of non-technical managers." People who stop coding lose touch with the field "much faster than you probably realize."
		- MSL was told "there's no deadlines." Wang describes the team as "insecure overachievers." He records their three-month forecasts and shows them later how pessimistic they were.
	- **Leadership spreading AI**: Wang says Instagram head Adam Mosseri has one of the most effective personal vibe-coding and mini-app setups he has seen. Long-tenured Meta leaders went from not AI-pilled to "super AI-pilled" quickly.
	- **The model is repeating elsewhere**: Kunal Shah, founder of CRED and "one of the top entrepreneurs in India," now runs WhatsApp, to bring entrepreneurial energy to WhatsApp commerce in Meta's largest country. Zuckerberg says this is lighter than MSL, which needed the whole company to pivot.
	- **Scale AI**: Collison refers to Meta buying 49% of Scale AI as part of the price of hiring Wang.
- ## Economics and compute: new data points
	- **GPUs are gaining value**: "the value of even an H100 at this point is higher than it was last year," because compute is still constrained. Meta expects to keep using GPUs after they are fully depreciated.
	- **The accounting edge of owning capacity**: data center capex is depreciated over many years. Researcher pay that produces a long-lived model is expensed right away. Labs renting from clouds pay the annual rate instead of building assets.
	- **R&D overlaps across generations**: each period's spend covers several model generations at once, so costs come well before payoff (Wang, citing a similar point from Anthropic's CEO).
	- **The core business funds the bet**: Zuckerberg calls Meta's core business "hundreds of billions of dollars and still growing extremely quickly." Using the models to grow it "a few percent faster" pays for much of the AI spend.
	- **Clusters were planned before MSL**: Prometheus (Ohio, scaling past 1 GW) and Hyperion (Louisiana, scaling to 5 GW over a couple of years) were planned in 2023–24 under the Llama program. "You can measure the compute strength of a lab by how big its largest single supercomputer is."
- ## Usage anecdotes
	- **MMA coaching (Zuckerberg)**:
		- Cameras in his gym feed Muse, which gives feedback in the one-minute break between rounds: balance, hip position, a missed underhook, risk of being rolled.
		- Muse built its own video pipeline, pulling stills without being told how. When feedback took 30 seconds he told it to "optimize yourself."
		- It started as an OpenClaw experiment before Muse existed and is now an informal eval for the product. Zuckerberg's takeaway: "everyone is actually going to be writing tons of code. They're just not going to know that they're writing code."
	- **Tea sourcing (Wang)**: his Muse, named Euler, buys increasingly obscure teas weekly from small farms in Taiwan and Japan.
	- **Baking with his daughter (Zuckerberg)**:
		- In the unreleased voice mode, Muse tells his voice apart from his three-year-old daughter's.
		- They plan the weekend bake during the week, and Muse orders ingredients on Instacart in time for Saturday.
		- When the order was below the delivery minimum, Muse suggested adding a watermelon on the day Watermelon (Wonder) launched.
		- He went from using Instacart about twice a year on his wife's account to his own account once or twice a week. "Is that Instacart account really for me or is it for the Muse?" Agents with accounts could enlarge the market for commerce.
	- **Home devices**:
		- A nickel-sized USB "home" gadget links Muse to Sonos speakers and lights. Zuckerberg has it dim the house in the evening.
		- Several phone makers have approached Meta about building the Muse gadgets platform into their phones.
	- **Subscription clean-up**: users ask Muse to search email for unused subscriptions and cancel them. Zuckerberg doubts Meta would monetize this.
- ## Agentic commerce: trends and first-hand data
	- **Browser use is the backstop**: Muse is trained to use websites so "no one has to do anything to integrate." Important partners get direct APIs, which are faster and cheaper than an agent browsing.
	- **More businesses want in than want out**: "We have way more businesses that are calling us asking to integrate deeply … very few … have tried to block it."
		- Collison's framework for who should rationally block: businesses with thin moats, or that rely on consumers spending time on site or on overcharging them.
	- **People are handing over purchases**: Wang says Muse is one of the first products where people fully delegate purchases. Value comes from less research friction, constraints like "deliver by Wednesday" applied automatically ("it was insane that we ever relied on" keyword search), and personalization across all of a user's context. Today's recommendation systems are "quite siloed."
	- **Stripe's timeline**:
		- One of the guests, likely Wang from context, told Patrick Collison at a 2023 dinner that Stripe was "way behind the eight ball" on agents buying things. He was "directionally correct but like three years early."
		- Stripe announced its agentic commerce products at Sessions in May 2026. John Collison says Stripe's agentic commerce stats only turned sharply upward starting in September.
	- **Stripe has agreed to acquire OpenRouter** (in the episode's ad and discussion; not yet closed). OpenRouter routes **more than 10 trillion tokens a day**. Wang's advice: help developers understand the subtle differences between models, which benchmarks flatten.
- ## Industry trends from the conversation
	- **Why no lab ran away (Wang)**:
		- Execution swings at every lab: "if all players when they were in the lead executed perfectly they would probably be able to stay in the lead."
		- Distillation lets open-source and small models catch up. "Really small models today are much more powerful than the biggest models a year or two years ago."
		- Researchers and companies choose employers and deals that push toward a more balanced outcome.
	- **Models are specializing**: Meta optimizes for personal and professional agents, while others favor coding and knowledge work. Zuckerberg: everyone else is "obsessed … with just automating knowledge work," while he thinks invention and creation are the higher use. He welcomed Nvidia's recent open-source moves.
	- **The coding-only view was a point of tension**: Zuckerberg says much of the industry earlier this year thought "coding was all that mattered." Consumer use depends on strong multimodal models, and Meta's visual data helps.
	- **Voice input is exploding, voice output less so**: most MSL researchers "whisper into their keyboard." College students "word vomit" for 10–15 minutes and let AI organize it. Zuckerberg says listening to information is much less efficient than reading, so the best interface is voice in and visual out, which favors display glasses.
	- **Turn-taking is the hard part of voice**: pauses get read as the end of a turn, and interruptions get read as a new question.
	- **Glasses before the app store**: camera-and-audio glasses with no display are already useful. Meta has started shipping small-display glasses. Zuckerberg isn't sure the glasses will need an app store once models generate interfaces on demand.
	- **Consumer AI products are built by engineers**: model naming where "the numbers go backwards" confuses mainstream users. That's the case for Muse having no model picker.
- ## What it means for the stock
	- *My reading; the episode doesn't discuss the stock.*
	- **Lean R&D headcount, heavy compute**: a research team of about 100–200 means the AI cost is almost all compute and capex, not people. That supports the depreciation-vs-expense argument, but makes returns depend on keeping the clusters busy.
	- **The Hawaii story puts the bet in the CFO's own terms**: Susan Li warned that failure would be "very, very bad in financial terms." Muse adoption, Wonder subscriptions and any lift to the core ad business are what will justify the \$100–200B decision ([[2026-10-15-cheeky-pint-zuckerberg-meta-ai-vision-and-execution]] covers the backstops).
	- **Rising H100 value is a near-term support**: if old GPUs are worth more than a year ago, depreciation schedules look conservative and resale is a real fallback. That reverses if compute becomes plentiful.
	- **Agentic commerce cuts both ways**: delegated purchases and agent accounts could grow Meta's role in commerce. The same trend threatens businesses that monetize time on site, which includes parts of the ad market. Instacart ($CART) is the named beneficiary in the anecdote.
	- **Stripe–OpenRouter** gives the largest model router (10T+ tokens a day) a payments owner. That makes it easier to sell Meta's API next to closed models, but also makes models easier to swap.
