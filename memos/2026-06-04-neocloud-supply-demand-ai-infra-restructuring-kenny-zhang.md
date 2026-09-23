- tags:: [[Neocloud]], [[$CRWV]], [[$NBIS]], [[FluidStack]], [[$NVDA]], [[TPU]], [[AI infrastructure]], [[Anthropic]], [[OpenAI]], [[xAI]], [[data-center]], [[GPU]], [[KV-cache]], [[storage]], [[$ORCL]]
  file-created-at:: 2026-06-04

- ## Neocloud — Supply/Demand Dynamics and AI Infrastructure Restructuring
	- **Source**: 硅谷坐标 (SV-Vector) interview with Kenny Zhang, CIO of Valliance (璞林资本); June 2026
	- **Thesis**: A new industry species — **Neocloud (the "fourth cloud")** — is emerging as AI shifts from training to inference/Agent workloads. Compute infrastructure is being rebuilt away from the traditional cloud paradigm. The market misreads Neocloud margins and backlog; the real long-term moat is migrating from IaaS compute rental up to the PaaS storage/data layer.
	- **Triggering events (past month)**: Anthropic buying compute from direct rival xAI; CoreWeave backlog surpassing **$99B**; Google partnering with Blackstone to form an independent TPU cloud company.

- ## 1. Paradigm Evolution — From "Bandwidth Distribution" to "Compute Density"

	| Era | Period | Core technical moat |
	|---|---|---|
	| Mainframe | 1950s–1990s | Single-point peak compute; enterprises self-purchase, local deployment |
	| Virtualization / traditional cloud | 2000–2022 | **Distributed distribution + bandwidth management** — virtualize spare CPU, sell elastically via CDN (AWS/Azure/GCP) |
	| AI cloud | 2023–present | **Ultra-high compute density + cluster interconnect** — thousands of GPUs doing microsecond-latency All-Reduce |

	- Traditional cloud's virtualization layer (built for general-purpose workloads) causes significant performance loss in high-density parallel tasks → births "AI Native Cloud" and the **"fourth cloud"** market outside the big-3 traditional clouds

- ## 2. Demand Side — Three AI Lab Compute Strategies

	| AI Lab | Strategy | Detail |
	|---|---|---|
	| OpenAI | **Pre-stocking** | Judged early that inference compute >> training compute; locked large capacity in 2022–2023 → ample supply today |
	| Anthropic | **Rigid gap-filling** | ARR ~$9B (end of last year) → **$50B this year** (expected >$100B by year-end); compute shortage now a real bottleneck on delivery & revenue. Procurement is no longer elastic, it's mandatory |
	| xAI | **Supply regulator** | After shifting model-competition strategy, resells idle H100/H200 to Anthropic → effectively became a passive Neocloud |

	- **Steady-state architecture = "core self-build + third-party elastic procurement"** (vs. the "AI Labs will fully self-build" expectation), for three reasons:
		1. **Establish a benchmark** — Labs' moat is algorithms/model architecture, not large-cluster ops; external vendors (CoreWeave) reverse-validate internal clusters' token-output efficiency and cost
		2. **Hedge ecosystem-binding risk** — all 3 traditional clouds have their own models/AI businesses; Labs must support independent, neutral compute suppliers
		3. **Absorb elastic concurrency** — Agent-era inference requests are tidal/peaky; covering peaks entirely via self-build is not financially efficient → need Neocloud's elastic pool

- ## 3. Supply Side — Four Neocloud Factions

	| Faction | Players | Model |
	|---|---|---|
	| 1. Fourth cloud — NVIDIA camp | CoreWeave, Nebius | PaaS value-add on hardware; directly contest the future cloud market |
	| 2. Fourth cloud — TPU camp | FluidStack | "TPU version of Nebius" (low leverage + prepayment), resources switched from NVIDIA to TPU |
	| 3. Vertical / specialized | Lambda | Programming-focused; vertical, regional, highly specialized |
	| 4. Bare-metal rental | IREN/Iris Energy, Crusoe, Softbank Energy | Mostly ex-crypto miners; pure hardware rental, billed by time |

	- **Faction 1 (NVIDIA camp) economics**: AWS operating margin ~40%; pure hardware only 25–30%; the extra 10–15 pts come from PaaS (storage, distribution, DB, management software) at 80–90% gross margin, ~30–35% of AWS revenue
		- Neocloud PaaS focus areas: compute optimization, KV Cache deployment/retrieval, Serverless RL
		- CoreWeave storage + KV Cache alone: **~$300M annualized revenue by year-end**, potential **$1–2B** future
		- Kenny: if PaaS reaches 15–20% of revenue → overall margin ~30%+ (vs GPU pure hardware ~25%) = the real "fourth cloud" economic model
	- **Faction 2 (TPU camp) basis — TPU supply leap**:

		| Year | TPU supply |
		|---|---|
		| 2025 | ~1.3M units |
		| 2026 | ~4M units |
		| 2027E | ~10–12M units (approaching NVIDIA scale) |

	- **Predicted Neocloud big-3**: CoreWeave (NVIDIA long-contract leverage), Nebius (NVIDIA low-leverage prepayment), FluidStack (TPU prepayment); Amazon (Trainium-based) also holds a spot but is itself a hyperscaler
	- **Faction 4 view**: Kenny neutral — easily squeezed on both price/return and capital supply
	- **Oracle — special dual-line**: wants both bare-metal rental and hyperscaler contention; a player straddling two paths

- ## 4. Two Capital Structures — CoreWeave (high leverage) vs Nebius (low leverage)
	- Financial markets value Neocloud assets on **long-term customer contract value, not hardware residual value**

	| | CoreWeave | Nebius |
	|---|---|---|
	| Model | 5–6 yr irrevocable contracts + bond-market leverage | Low leverage + high customer prepayment |
	| Economics | Spend $1 → earn ~$3 over 6 yrs | Microsoft/Meta deals: **40–50% prepayment**, only convertible bonds |
	| Cost of capital | Loan rate **14.5% (2023, high-yield) → 6.2% (now, Investment Grade)** | Bears compute-price volatility, not financial leverage |
	| Returns | Levered IRR **30–35% → 50%+** | Price concession 20–25%, but unlevered IRR **35–40%** |
	| Lineage | "100-year-proven infra playbook" (Brookfield: $2T AUM, 100-yr history) | Founders ex-Yandex, relocated to Amsterdam post Russia-Ukraine war |

	- vs traditional infra (rail, ports, highways) levered return 10–12% → Neocloud is a "modern century-long business"
	- **Key clarification**: Kenny measures all returns on **net cash flow, NOT EBITDA** — EBITDA excludes depreciation, which is a real financial reality for this heavy-asset business

- ## 5. Two Core Market Misreads (why Neocloud trades ~10× vs traditional cloud 20–25×)
	- **Misread 1 — Why did margin crash from 14% to 1–2%?**
		- Trajectory: 2025 Q2–Q3 **12–14%** → Q4 **8%** → 2026 H1 **1–2%** (even as Q1 GPU spot price rose +40%)
		- Answer: classic infra **J-curve**, not a broken model. CoreWeave has 1 GW powered (only **800 MW** revenue-generating), 3.5 GW total layout, building 1 GW this year — under-construction > revenue-generating scale compresses margin

		| Timeframe | Revenue-gen scale | Under-construction | Margin |
		|---|---|---|---|
		| Now (2026 H1) | 0.8 GW | 1 GW (>100% of rev scale) | 1–2% |
		| End-2026 | 1.8–2 GW | 1 GW (~50%) | 12–14% |
		| End-2027 | 3 GW | ~30% | 20%+ |
		| End-2028 | + KV Cache/RL PaaS | — | 25% |
		| Long-term | steady state | — | ~30% |

		- Analog: GDS (万国数据) 2016 IPO had ugly statements for the same reason (build > rent)
	- **Misread 2 — Is the $99B Backlog a bubble?**
		- Current revenue ~$5B; guidance $12–13B; Capex $30B+; **Backlog $99B**
		- Waterfall structure: today's revenue and today's Capex are unrelated. "Spend $1 today → recover $3 over 6 yrs"
			- 2026 guided $12–13B revenue = result of 2023–2024 deployment
			- This year's $30–35B Capex = $90–100B revenue realized over next 6 yrs; **crossover ~2029**
		- **Backlog customer concentration is also misread**: 2025 70% revenue from Microsoft (as OpenAI intermediary) reflects 23–24 deployment. Forward backlog is diversified:

		| Customer | Share of Backlog |
		|---|---|
		| Meta (now largest, surpassed Microsoft) | 35% |
		| Microsoft | 20% |
		| OpenAI | 20% |
		| Anthropic | 8–10% |
		| Jane Street | 8–10% |

		- Overlooked clause: **NVIDIA commits to buyback/backstop** chips CoreWeave purchases but can't deploy → structurally reduces downside risk

- ## 6. Why the Valuation Gap Won't Fully Converge
	- **Capex intensity**: traditional cloud ~$15–20M/MW (self-chip $10–12M); CoreWeave/Nebius **$45–50M/MW** — 2–3× higher
	- **PaaS ceiling**: Neocloud customers (AI Labs, hyperscalers) have strong PaaS themselves → Neocloud PaaS ceiling ~15–20% vs traditional 30–35%
	- **Convergence call**: traditional cloud margin 40% → 30–35%; Neocloud 25% → 25–30%. Current 10× vs 25× gap is too wide and will converge — but not disappear

- ## 7. DeepSeek and the "Abnormal" 2026 Spot Market
	- Kenny: this year's GPU spot price is **abnormal**; three overlapping causes:
		- **Semiconductor cycle mismatch**: Covid-era overbuild + faster-than-expected end nearly bankrupted SK Hynix, SanDisk, Kioxia in 2022–2023 → worst downcycle preceded biggest upcycle → upstream afraid to expand aggressively
		- **Silicon Content vs Capex mismatch**: 2027 cloud + AI + Neocloud Capex may grow **+50–60%**, but Silicon Content (actual chip volume) grows little — most growth is component/chip (esp. memory) **price increases**. Healthy market = Capex +50%, Silicon Content +30–40%, Token Cost drops sharply, demand truly explodes (3 variables matched)
	- **DeepSeek is not bearish — it's a necessary condition**: its efficiency optimization + token-price decline are required for healthy industry development
		- **Jevons paradox**: like mobile internet — iPhone launched 2008 but the real explosion came 2013–14 with cheap Android phones. If delivery drivers needed a $10k phone for O2O, it never scales. Hardware cost falling to mass-affordable → downstream apps explode
		- Neoclouds/AI compute firms should keep some efficiency gains and pass some to downstream B/C users = healthy ecosystem

- ## 8. Tech Evolution — Inference & Agent Era: Biggest Variable and Bottleneck
	- As AI shifts training → inference/Agent, IaaS compute rental commoditizes; Neocloud's moat/premium moves up to **PaaS**, with the deepest reconstruction in the **storage and data layers**
	- **"AI Native Cloud" is defined differently by each player**:

		| Player | Definition |
		|---|---|
		| DigitalOcean | Developer-facing product matrix (recently launched 15–20 lightweight AI products); SaaS-leaning |
		| NVIDIA + CoreWeave | Large-cluster management/optimization at the core; infra-heavy, physical layer |
		| Hyperscalers | Barely use the term — "same as before, just B-end workflow users shift from humans to machines" |

	- **Biggest variable — death of the UI, machine-native data direct connection**: in the Agent era the dominant caller becomes autonomous machines, not humans. Agents issue high-frequency API read/write directly to hardware/data — no GUI needed. Traditional clouds' front-end/middleware soft power gets diluted; PaaS competition mutates into "storage-data fusion + retrieval efficiency"
	- **Biggest bottleneck — from "compute generation" to "high-frequency retrieval"**: as models saturate verticals, Agents' high-frequency questions have largely been computed before → KV Cache and similar caching spread. The bottleneck shifts **from GPU FLOPS (compute) to storage I/O (high-concurrency, low-latency retrieval of cached answers)**. Models answer faster not because inference got faster (no new cards) but because answers are stored
	- **Why traditional storage fails, HFT crossover wins**:
		- Traditional enterprise storage (Dell EMC, NetApp, Pure Storage) built for low-frequency access + hot/cold tiering ("store it and never look again") — can't handle TB-level high-concurrency I/O from thousands of nodes simultaneously
		- AI-native storage (e.g., **WekaData**) built for high-frequency retrieval + ultra-low latency; came from Wall Street quant/HFT millisecond-critical scenarios — exactly what AI clusters need. Backlog "very strong" — hyperscalers, AI compute firms, Neoclouds all customers
		- Kenny: incumbents likely can't build this generation (their customer gene is "store and forget"). Native AI-cluster storage/retrieval scheduling will determine Neocloud's "fourth cloud" moat depth

- ## 9. Macro Lens — Digital Labor Migration

	| Wave | Period | Mechanism |
	|---|---|---|
	| 1st | 1985–2010 | Manufacturing outsourced to Asia: US lost 7M jobs, Asia +120–150M jobs, cost −60% |
	| 2nd | 2010–2025 | Cloud + SaaS capped white-collar expansion: 50M core white-collar tech-capped |
	| 3rd | 2026 onward | AI replaces white-collar labor expansion — chips replace the workers |

	- **Chips = new digital labor; data centers = production sites; Neocloud (AI native cloud) = the underlying infrastructure carrying these digital laborers**
	- This is why NVIDIA calls the data center an **"AI Factory"** — not rhetoric, but the 1990s China-manufacturing industrial logic replaying in the 2026 AI era. Neocloud's shift from "bandwidth distribution" to "compute density + high-frequency data throughput" is the inevitable result of this computing-paradigm shift

- ## Investment Implications
	- **Neocloud is mispriced on two recurring errors** (J-curve margin, waterfall backlog) — the 10× vs 25× gap should partially converge; CoreWeave's falling cost of capital (14.5% → 6.2%, now IG) is the strongest market validation
	- **Three-winner structure**: CoreWeave (NVIDIA long-contract leverage), Nebius (NVIDIA low-leverage prepayment), FluidStack (TPU prepayment); watch the TPU supply leap (1.3M → 4M → 10–12M) enabling the TPU camp
	- **NVIDIA buyback backstop** for undeployable chips is an underappreciated downside protection for CoreWeave
	- **Storage is the next moat layer**: AI-native storage (WekaData) over incumbents (Dell EMC/NetApp/Pure Storage) as KV Cache shifts the bottleneck from compute to storage I/O — a key PaaS battleground
	- **Memory cross-read**: the "Silicon Content vs Capex" mismatch (Capex +50–60% but volume up little, growth mostly memory price) corroborates the memory super-cycle thesis (see [[2026-06-01-memory-super-cycle-five-arguments]] and [[2026-06-04-memory-market-and-big3-financials]])
	- **Return discipline**: evaluate Neoclouds on net cash flow, not EBITDA — depreciation is real for this heavy-asset model
