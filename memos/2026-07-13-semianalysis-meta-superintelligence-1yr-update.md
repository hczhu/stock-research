- tags:: [[$META]], [[Meta]], [[MSL]], [[AI-capex]], [[data-center]], [[RL-environments]], [[Anthropic]], [[OpenAI]], [[$GOOG]], [[xAI]], [[$MSFT]], [[frontier-labs]], [[talent]], [[Mercor]], [[Surge]], [[compute]]

- **Source**: SemiAnalysis (Max Kan, Julien Martin-Prin, Jeremie Eliahou Ontiveros, Dylan Patel), "The Future of Meta Superintelligence: A 1 Year Progress Update," July 9, 2026 (paid). One year after the Llama 4 flop triggered Zuck's AI-org rebuild (\$14.3B Scale AI deal to poach Alexandr Wang + SEAL team, \$100M–\$1B+ pay packages, "Tent" DC design). Companion to [[2026-07-07-mark-zuckerberg-meta-ai-ads-compute-strategy]], [[2026-07-10-sharp-tech-meta-ai-ads-zuckerberg-strategy]], [[2026-06-03-frontier-labs-gpu-compute-capacity-share]], [[2026-07-07-hyperscaler-capex-goldman-bofa-cy27-28e]].

- **Thesis frame (SemiAnalysis' call)**: Frontier AI is now a **two-horse race (OpenAI vs Anthropic)**, but of everyone chasing, **Meta is the only hyperscaler/neolab on track to be world-class at all three frontier inputs — data, talent, compute — and therefore "has the best chance at catching up."** Judge MSL on **slope, not intercept**: Muse Spark is mediocre, but the rebuild debt is paid. Meanwhile the piece delivers a scathing **"loser mentality" verdict on Google** — "the race for 3rd is currently between Meta and SpaceX, not Google."

- ## State of the Race (opinions on every player)
	- **OpenAI + Anthropic**: the two-horse frontier race.
	- **Google**: brief spotlight with Gemini 3 Pro/Nano Banana, "faded dramatically." Despite the **Windsurf acquisition**, far from a compelling agentic coding product; **3.5 Flash is "a benchmaxxed prop"** that performs far worse than GPT-5.5 and Opus 4.8 in the real world (much less Fable/5.6); **3.5 Pro is not even Opus-level on coding**.
	- **Microsoft**: "completely blown their early lead with GitHub Copilot and failed to effectively leverage their access to OpenAI IP."
	- **SpaceXAI (xAI)**: **selling \$26B/year worth of GPUs to Anthropic/Google** — monetizing compute rather than racing the frontier directly, yet still ranked ahead of Google for 3rd.
	- **Chinese labs**: "simply too compute poor to truly reach the frontier."
	- **Meta/MSL**: public debut April 2026 with **Muse Spark** — arguably a *regression* (Llama 3 70B/405B were SOTA open-source at release; Muse Spark, despite being closed-source, **lagged open-source DeepSeek V4 Pro and Kimi K2.6** on most benchmarks).

- ## Muse Spark Benchmark Reality (SemiAnalysis Tokenomics data)
	- | Benchmark | Muse Spark (Meta) | Kimi K2.6 | DeepSeek V4 Pro |
	  |---|--:|--:|--:|
	  | GDPval-AA | 1417 | 1482 | **1558** |
	  | Terminal-Bench 2.0 | 59.8% | 66.7% | **67.9%** |
	  | SWE-Bench Pro | 52.4% | **58.6%** | 55.4% |
	  | SWE-Bench Verified | 77.4% | 80.2% | **80.6%** |
	  | Chatbot Arena (Text) | **1489** | 1462 | 1459 |
	  | Humanity's Last Exam | 50.4% | **54.0%** | 48.2% |
	  | GPQA Diamond | 89.5% | **90.5%** | 90.1% |
	- **Muse Spark 1.1** (tested pre-release): "roughly on par with **Opus 4.6 or GLM 5.2** for general agentic use cases"; priced **just under GLM 5.2** (intentional); bad habits — ignores warnings instead of fixing them, poor edit-tool use. "None of our internal token volume will be moving." **Even in the bull case, not on par with Anthropic/OpenAI until end of 2026.**

- ## Leg 1 — Data: "Meta just created a top-tier RL environment startup"
	- **RL is the most important scaling law today** (tasks + environments + tools + verifiers). Sholto Douglas (Anthropic): even if algorithmic progress stalls, "**the current suite of algorithms are sufficient to automate white-collar work provided you have enough of the right kinds of data**… compared to the TAM of salaries, it is so trivially worthwhile."
	- **The human-data/RL-environment supply chain has exploded** — the invisible hand refutes "data is the fossil fuel of AI":
	  
	  | Company | Latest ARR | Valuation | Notes |
	  |---|--:|--:|---|
	  | Surge AI | ~\$3B (Jul 26, rumored) | ~\$30B | Bootstrapped, <110 employees, \$0 outside capital |
	  | Mercor | \$2B+ (Jun 26) | \$10B | \$1B→\$2B+ gross ARR in 4 months; expert hours 2K→2.5M/quarter in 2 yrs (+69% QoQ) |
	  | Handshake AI | ~\$1.0B (May 26) | \$3.5B | \$0→\$1B gross ARR in 16 months atop its job-board network |
	  | Micro1 | \$250M+ (May 26) | ~\$2.5B | \$8M→\$250M+ RR in 14 months (~30×); 7-figure profits at 20%+ MoM |
	  | Fleet | \$63M (Apr 26) | \$725M | \$1M→\$63M RR in 6 months (~60×); 30-person team |
	  | Mechanize | undisclosed | \$500M | Raised \$9.1M (~1.8% dilution); pays SWEs \$400K+ expecting **1 good task/week** |
	  | Afterquery | \$100M+ (Apr 26) | \$300M | \$0→\$100M run-rate in 14 months (YC W25) |
	  | Deeptune | undisclosed | — | Pivoted AI-dubbing→RL gyms; \$43M Series A (a16z) |
	- **Screen recordings are the scarce input**: they guarantee realism (representative of real knowledge work, right difficulty), enable rubric verifiers (thousands of traces → an LLM can nearly one-shot the grading rubric), and expose end-state for deterministic verifiers. Contrived expert-written tasks are the flaw in OpenAI's GDPval / Mercor's Apex (1,064-word itinerary prompts "a human would never write").
	- **Meta's move**: tracking employees' **screens, keyboards, and mouse movements** — "quite literally some of the most valuable data in the world today" (poetically, the Scale AI man spearheads it; minor walk-backs: privacy strengthening, 30-min pause option). Unlike data startups begging banks/law firms/ad agencies for recordings, **Meta has a large in-house workforce in each of these functions**.
	- **The ~3,000-engineer "applied AI engineering org"** (late May, part of layoffs/restructuring): **70% of new grads + many seniors now make RL tasks/environments full-time**. Scale check: Mercor logged **2,517,000 expert hours in 2Q26 (~4,800 FTEs)** — Meta is already in the same ballpark, with likely higher quality and **~70K more employees** to draw from. Frontier labs pay **\$5,000+ per decent coding task**; Mercor's average rate passed **\$100/hr**; top contractors earn 7 figures. Not low-level labeling — "creating a good piece of training data is a real intellectual challenge."
	- **Read-through**: Anthropic has been **the most aggressive buyer of coding data from RL-env startups** — cited as one reason Claude models lead coding. Meta just internalized that supply chain at hyperscaler scale.

- ## Leg 2 — Compute: "Instagram ads can fund a lot of compute"
	- Meta has a hyperscaler balance sheet, **no cloud business competing to rent the compute out** (unlike Google), and **Zuck is willing to go FCF-negative** → "Meta should be able to bring up more internal AI compute than anyone else in the world."
	- **SemiAnalysis Tokenomics projection: Meta will have more AI compute than both OpenAI and Anthropic by end of 2026.** Caveat: a meaningful share goes to RecSys and generative ads — but even conservatively counting only flagged MSL sites, **training compute is comparable to OpenAI/Anthropic through 2026–27**.
	- **Five 1GW+ "Titan" clusters being built simultaneously**: Prometheus (Ohio), Hyperion (Louisiana), + three unnamed (El Paso, Iowa, Indiana).
		- "**Never in the history of humanity** have we seen a full 1GW campus under construction simultaneously" (closest: AWS 800MW Project Rainier, Indiana) — **Meta has two right now** (Hyperion and Iowa).
		- **Hyperion**: world's largest single DC buildings at **400MW each**; **1.5GW under construction** (3×400MW + 3×100MW).
		- **Iowa**: 1GW lease with a leading DC operator; **nothing → full 1GW under construction in one year**.
		- **Prometheus**: partially operational; **~1GW → >3GW within two years**; "tent" design; a **constellation of 27 datacenters across 6 campuses** (5 within 6km, the 6th 75–80km away).
	- **Scale-across networking (AI-Backbone / AIBB)**: L3 Superspines (BAG) interconnect up to 5 DSF / 7 NSF scale-out regions; single L4 Inter-BAG hub gives **~22 Pbit/s bidirectional** across Prometheus; LR optics + DWDM/ZR between campuses. Physics constraint: 1–10µs within a region, but **≥500µs at 100km** (light propagation) → **pretraining synchronous in one region, RL spread globally asynchronously**. Other Titans will scale-across campuses **up to 2,000km apart**. (Networking/optics content demand read-through: DWDM/ZR optics and switch silicon are structural winners of the scale-across paradigm.)

- ## Leg 3 — Talent: the superteam
	- \$14B for Alexandr Wang; **\$1B+ to buy out Nat Friedman + Daniel Gross's venture fund**; 14+ researchers poached by end-June 2025 (mostly ex-OpenAI: Shengjia Zhao, Trapit Bansal, Joel Pobar, Jack Rae).
	- Newer: **Andrew Tulloch (ex-Thinking Machines cofounder)**; Joshua Gross, Mark Jen, Yinghai Lu (Thinking Machines founding team); **Jason Wei, Hyung Won Chung, Zhiqing Sun (ex-OpenAI)**.
	- **Dina Powell McCormick** (ex-Trump/W-Bush advisor) as President & Vice Chairman to build the compute fleet — political muscle for power/permitting. Also poached OpenAI's compute trio (Pete Hoeschele, Anuj Saharan, Shamez Hemani) in April — **one already quit over Meta culture issues in the infra org** (execution risk is real).

- ## The Bear Checklist (what would flip SemiAnalysis negative)
	- "Success is far from guaranteed… they are still basically at step 1." Watch for **any true weakening of resolve**:
		- Signing a **long-term compute-sale deal with no clawback** (i.e., becoming a GPU landlord instead of a lab);
		- **Disbanding the RL task-creation org**;
		- **Top researchers walking away**.
	- "Any one of these would be tantamount to a **death sentence for MSL**."

- ## "What This Means for Google" (the harshest section)
	- Meta is truly **"AGI-pilled"** (3,000 engineers on RL tasks, multi-GW ramp, \$1B equity grants) despite PR/internal backlash and stock hits. Alexandr Wang's frame: every true frontier lab starts from the conviction that superintelligence is imminent and **all business decisions are downstream of that belief** — historically only startup-labs (OpenAI, Anthropic) had this "religious zeal."
	- **Google pays lip service**: key executives don't actually believe a "country of geniuses in a datacenter" arrives within 3 years — "If they did, they'd be funneling all their compute to DeepMind instead of actively enabling its fiercest competitors."
	- SemiAnalysis projection: the **majority of Google's incremental DC capacity goes to IaaS and 3P-API businesses; DeepMind will have LESS training compute than OpenAI, Anthropic, and MSL**. The **\$85B equity raise** for AI infrastructure will mostly be **rented out to customers like Anthropic**. Verdict, verbatim: "**This is loser mentality from Google.**"
	- Google also "recently lost even more great RL people to Anthropic"; RL efforts "too decentralized." Advice: put SWEs on RL-task creation and redistribute compute to DeepMind immediately — "we give the same advice to Microsoft AI and Amazon AGI too, **but they are already beyond saving**."

- ## Investment Read-Throughs
	- **$META**: the bull case upgrades from "AI optionality" to **structural #3-or-better frontier contender** — unique data (in-house screen recordings + 3K-engineer task org), compute leadership by end-2026, and no cloud-rental conflict. The bear ledger: FCF-negative tolerance, Muse Spark's weak intercept, infra-org culture attrition, and the explicit death-sentence triggers to monitor. Pairs with the ads-monetization angle in [[2026-07-07-mark-zuckerberg-meta-ai-ads-compute-strategy]] — RecSys/gen-ads share of the same compute is the self-funding mechanism.
	- **$GOOG**: this is the strongest sell-side-adjacent articulation of the **"Google enables its competitors" bear case** — DeepMind compute-starved relative to rivals while TPU capacity is rented to Anthropic. Counterpoint to hold: renting compute is *profitable* (the Benedict Evans commodity-infrastructure lens says the picks-and-shovels position may be the *right* one — [[2026-07-13-benedict-evans-token-pricing-commodity-infrastructure]]). The two pieces are the same fact with opposite value judgments.
	- **Anthropic/OpenAI**: the two-horse framing + Anthropic's coding-data aggression corroborate the coding-moat thesis; but MSL's compute crossover by end-2026 is the first credible threat vector to watch.
	- **RL-data supply chain**: Surge/Mercor/Handshake at \$1B–3B ARR with absurd growth (60× in 6 months at Fleet) — a genuinely new spend category flowing out of lab budgets; also validates Mercor's >\$100/hr expert rates as the "agentic labor market" in reverse. Private names, but the spend shows up in lab opex and is a leading indicator of RL-scaling conviction.
	- **Infra supply chain**: five simultaneous 1GW+ Titans + 2,000km scale-across = incremental demand for **DWDM/ZR optics, switch silicon, and behind-the-meter power** on top of the [[2026-07-07-hyperscaler-capex-goldman-bofa-cy27-28e]] capex track (BofA's Meta 2028E +23% revision now has a physical explanation).
	- **xAI datapoint**: \$26B/yr of GPU sales to Anthropic/Google is a remarkable revenue disclosure — xAI as a *merchant compute provider* is itself a mini-Google-critique (selling shovels to rivals).
