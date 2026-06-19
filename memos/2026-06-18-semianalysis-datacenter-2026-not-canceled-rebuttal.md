- tags:: [[data-center]], [[AI]], [[capex]], [[hyperscalers]], [[$VRT]], [[power]], [[ERCOT]], [[$ORCL]], [[$NBIS]], [[CoreWeave]], [[$NVDA]], [[SemiAnalysis]], [[neocloud]], [[BtM]], [[transformers]]

- **Source**: SemiAnalysis — "Stop Saying Half of 2026 US Datacenter Capacity Is Canceled" (Reyk Knuhtsen, Maya Barkin, Jeremie Eliahou Ontiveros + 2 others), Jun 18, 2026. Paid post.

- **Thesis**: The viral "half of 2026 US datacenter capacity is delayed/canceled" claim is wrong. Cancellations/delays cluster in the early-stage announcement layer that was always structurally oversupplied and never going to deliver in 2026. The verifiable 2026 pipeline (site control + equipment ordered + interconnection signed + vertical construction underway) is on track. Over the last 6 months SemiAnalysis's YE2026 NA Hyperscale self-build forecast moved only ~1%, colocation <5%. Bearish read-through to equipment suppliers (Vertiv etc.) is also wrong.

- ## Where the "50% Canceled" Claim Comes From — and Why It's Flawed

	- Traces to Bloomberg's Apr 1, 2026 piece *America's AI Build-Out Hinges on Chinese Electrical Parts*. TechRadar, Tom's Hardware, The Register then ran sharper clickbait versions → "half of datacenters cancelled."
	- **Flaw 1 — flawed denominator (off by multiples)**: Bloomberg's data comes from **Sightline Climate**, which estimates of ~12 GW expected online in US in 2026, only ~5 GW is "under construction." SemiAnalysis's satellite-trained Vision Model says even the *Under Construction* figure is off by multiples — the top-two hyperscalers alone (self-build only) exceed 5 GW under construction. Sightline tracks only large, publicly-announced projects → basis skewed toward speculative megaprojects from inexperienced developers most prone to slip. "50% cancelled" describes the slice of the pipeline most prone to slipping, not the US pipeline.
	- **Flaw 2 — flagged capacity sits in pre-construction "announced" bucket**: speculative MW that were never landing on a 2026 timeline. These show up in SemiAnalysis's model as **2028+**, not 2026. Large US load queue: >0.5 TW flagged Dec 2025, now **>1 TW** — vast majority highly speculative.
	- **Vibe-coded / "Claude Coded" forecasts** are the root cause: they pull press releases, treat unfounded GW-scale announcements as ground truth, misunderstand construction timelines and grid complexity. (SemiAnalysis spent \$171,476 on Claude Code in one week — flexes familiarity to call out others' methodology errors.)

- ## The Anatomy of a Datacenter Delay — 3 Buckets

	- | Bucket | Description | Example |
	  |---|---|---|
	  | 1. Aggressive announcements by new players | Speculative early-stage projects with unrealistic timelines; should be discounted | Data City (Energy Abundance) 5GW, 300MW "2026" — website is just a "Contact Us" button, no satellite progress; APR Energy 400MW TX, no customer; Cloudburst 1.2GW San Marcos TX |
	  | 2. Advanced projects, too-optimistic construction timelines | New developers lacking experience; don't budget for supplier/weather/equipment delays | Nebius/DataOne NJ 50MW; Core Scientific Denton |
	  | 3. Well-capitalized projects hit by permitting/NIMBY | Forces change to power source or design | Oracle/STACK New Mexico (delayed to 2029) |
	- It can take **>4 years from land purchase to datacenter delivery**. A 2025 announcement claiming 2026-operational from an unknown developer is a red flag.

- ## Case Study — Nebius/DataOne New Jersey 300MW (Bucket 2)

	- DataOne (no prior US DC track record) targeted a 4-month delivery for first 50MW phase using precast/prefab. Reality:
		- | Date | Event |
		  |---|---|
		  | Mar 2025 | Targets: 25MW by Jul, 50MW by Sep, 100MW by YE2025 |
		  | Jun 2025 | First delay acknowledged → Aug |
		  | Sep 2025 | 50MW declared "imminently delivered"; 4-month build became 6; satellite shows only chillers for 25MW going on roof |
		  | ~Oct 2025 | First 25MW delivered |
		  | Mid-Dec 2025 | Second chiller batch still not installed; ~25MW energized vs 100MW promised for year-end |
		  | Jan/Feb 2026 | Full 50MW complete (much later than 4-month target; still fast — 10–11 months — by industry standard) |
	- Late supplier deliveries alone added 2 months; MEP setup took far longer than shell. Nebius YE2026 ARR guide: \$7–9B.

- ## Case Study — Oracle/STACK New Mexico "Project Jupiter" (Bucket 3, delayed to 2029)

	- Oracle Jun 10 earnings guided 1H2027 customer delivery; FERC records and construction timelines don't support it. SemiAnalysis moved base case off 2027 → **2029**.
	- Three things went wrong: (1) microgrid permitting threaded right at the major-source threshold; (2) required a brand-new gas pipeline; (3) organized local opposition.
	- Two behind-the-meter gas microgrids (East NSR 10732, West NSR 10734). NMED Dec 2025 incompletion: East could emit up to 521 tpy NOx vs requested 248.90 cap; West 388 vs 249.97 — both too close to 250 tpy major-source threshold. Mar 23 2026 NMED pushed reviews to Jul 21, ordered public hearing, cited ~7,155 comments.
	- Apr 27 2026 Oracle withdrew turbine apps, filed for **Bloom Energy fuel cells** (~37 tpy NOx) instead — but binding constraint remained: 400,000 Dth/d of gas via one unprepared pipeline (Green Chile / Transwestern, contractual Aug 15 2026 in-service). NM State Land Office denied right-of-way across state trust land (Mar 20); FERC opened formal Section 7 review (May 15); no viable alternative route. Contractual in-service became infeasible → power off 2027, out to 2029.
	- **Takeaway**: NIMBYism rarely kills a capitalized project of this scale outright, but adds months of permits/hearings/ROW — enough to blow strict deadlines.

- ## What's Fueling the Panic — All Generate Headlines, ~Zero Delivered 2026 MW

	- **Moratoriums**: As of Apr 2026, ≥12 states filed moratorium bills; Indiana has ≥4 counties enacted. But none had datacenters in them. Maine vetoed LD 307 (would have been first statewide ban) — but Maine has **<5MW planned**. Measures land in inconsequential areas or projects already too early-stage for 2026.
	- **NIMBY**: Opposition slowing a real capitalized project is rare; killing speculative paper rezoning is common. Compass withdrawal (Prince William County), rejected GA rezonings, pulled proposals across 20+ states — nearly all in the announcement layer with no equipment, no interconnection, no 2026 delivery to lose.
	- **Unfounded announcements / ERCOT**: As of Apr 2026 ERCOT assessing >410GW large-load interconnection requests, >87% (~357GW) from datacenters. TX all-time peak demand ~85GW → queue ~5× the grid. SemiAnalysis tracks only **45.4GW real** (2030Q4 buildout); **311GW is Phantom Datacenter** demand; 53GW non-DC. Tracked projects = only ~13% of ERCOT's DC queue.
	- TX Senate Bill 6 (site-control docs, \$100k minimum study fee, mandatory curtailment) slowed speculative filings — a sorting mechanism. Much of what is "canceled" is MW that never had site control / financing / interconnection.

- ## Why the 2026 Outlook Hasn't Moved — Early-Stage Is Structurally Oversupplied

	- Cancellations cluster in a layer SemiAnalysis already treats as oversupplied (surplus appears late as 2028). Volume of announced early-stage capacity far exceeds deliverable — a normal feature reflecting asymmetry between low barriers to *announce* and real constraints to *build*.
	- A project moves beyond high-risk phase once it secures ≥2 (preferably 3) of: **secured land** (acquisition / ground lease / exclusivity / shell entity); **defined power solution** (grid interconnection or onsite gen procured); **approved permits** (construction + air permits for onsite gen). Ordering long-lead equipment (requires deposits + capital) also crucial.

- ## How Leading Operators Route Around Constraints — Two Playbooks

	- **Political playbook (permits + zoning)**: land-bank multiple sites; local land-use lawyers on retainer; relationships with utility VPs & econ-dev staff; community investment (PILOT structures, e.g. \$31M Microsoft put into Quincy Water Reuse Utility then leased back for \$10/yr). Developers increasingly *withdraw proposals ahead of a vote* (avoid a citable public rejection), relocate to friendlier jurisdiction, refile modified design, or shift to brownfield/unincorporated land. Sites die quietly; project moves — hence the many land-banks.
	- **Physical playbook (energy)**: grid connection lead times stretched to **7–10 years** in multiple metros.
		- *Pay directly into the grid*: Oracle/DTE BESS deal; Meta/Entergy (Meta pays for full construction + operation of dedicated power plant).
		- *Powered land*: in constrained markets (Europe, US metros) businesses now sell/lease grid-connected land outright — Lancium, Cloverleaf performing well.
		- *Behind-the-meter (BtM) generation*: hyperscalers + AI labs going offsite (xAI Colossus 1 retrofitting a warehouse).
	- **Physical playbook (equipment) — 3 adaptations now standard practice (last 12 months)**:
		- *Long-lead procurement in scoping phase*: lock transformers, MV/LV switchgear well ahead of vertical construction. (A specific cooling SKU flagged as the next big bottleneck post-Computex.)
		- *Chinese OEMs in the supply chain*: quietly alleviating high-end bottlenecks. xAI likely uses Sieyuan transformers/breakers. Multiple US companies now broker for Chinese OEMs; sometimes hyperscalers buy directly. Trend accelerated meaningfully over last 12 months.
		- *Modular/prefab builds*: old news in China, new to US AI DCs. Condenses supply-chain complexity into one product, cuts skilled-labor intensity of onsite assembly — pressure-release on equipment AND labor simultaneously.

- ## The Equipment Supplier Bear Narrative Is Also Wrong

	- Fear priced into Vertiv etc.: delays/cancellations eat into record orders/backlog. But SemiAnalysis capacity forecast shows quarter-by-quarter delivery accelerating; delivered MWs are rising.
	- Lead times remain long: Reinhausen tap-changer bushings (single subcomponent gating the whole large-HV stack) quoted **3–5 years**; most critical SKUs still >1 year. GE Vernova, Hitachi Energy, Mitsubishi Electric booked out **3–4 years** on main lines. Hitachi's new South Boston plant (announced Sep 2025) not operational until 2028.
	- Capacity now allocated via **prepayments**: buyers wire money up front to hold queue slots (boxing out less-capitalized players). BtM prepayments now **10–15%** standard to secure a queue position. AI demand lifted pure-play electricals (Vertiv, Schneider) to margins **>20%**.
	- **Why cancellation fear doesn't hit OEM backlog**: canceled projects are early-stage ones that never placed equipment orders — a speculative announcement dying in a county hearing removes zero orders from anyone's books. Projects in OEM backlogs have prepaid, locked long-lead SKUs, often broken ground. In the rare case a real order falls away, a 3–4-year-deep queue reallocates the slot to the next buyer rather than vanishing.
	- SemiAnalysis Industrials Model: >550 DC equipment suppliers, mapped to >6,000 facilities globally, exposure project-by-project to separate locked vs at-risk backlog.

- ## 2026 Outlook & What's Being Watched into 2H26

	- When noise is filtered out, ~**24GW** expected online in 2026, already under construction and tracking. Cancellations/delays concentrated in the early-stage layer that was always going to be culled.
	- **Three inflection points into 2H26**:
		- *State-level moratorium activity*: Maine LD 307 vetoed but Pennsylvania's 3-year proposal + broader 12-state wave could shrink the buildable map; a single statewide ban would be a precedent.
		- *Q3 lead-time prints*: recent stabilization is fragile; next OEM commentary tells whether we approach an equipment cliff or prepayment-secured supply keeps clearing.
		- *Continued BtM supply signals*: generation-provider entries push BtM toward oversupply, but inflections coincide with grid-headroom decreases → possible BtM underutilization near-term, higher demand 2028+.
	- **Real delays SemiAnalysis still flags**: TeraWulf flagship (Lake Mariner + Abernathy for Fluidstack) likely delayed past YE2026 guidance — Lake Mariner second 80MW building (construction began March) a tight 2026 timeline; Abernathy maintained delay to 2027 (MEP+commissioning overlooked). CoreWeave: correctly predicted 1.7GW Active Power by end-2026 (matched company guide — "not everything is delayed").

- ## Investment Implications

	- **Bullish equipment suppliers (Vertiv, Schneider, GE Vernova, Hitachi Energy, Mitsubishi Electric)**: backlog is prepayment-locked, queues 3–4 years deep, margins >20%. The "datacenter cancellation → backlog erosion" short thesis misreads where cancellations occur (early-stage, no orders placed). Delivered MW accelerating.
	- **Discount headline "cancellation" data**: any pipeline estimate built on announcement-stage data (press releases, real-estate filings, non-binding LOIs) — including "vibe-coded" forecasts — systematically overstates both the at-risk pipeline AND the prior pipeline. The ERCOT 357GW DC queue vs 45GW real (13%) is the cleanest illustration of phantom demand.
	- **Watch the verifiable filter**, not announcements: site control + equipment ordered + interconnection signed + vertical construction. Satellite imagery (chiller install, MEP, shell progress) is the leading indicator of real delivery vs declared delivery.
	- **Chinese electrical equipment dependency is real but is a relief valve, not a fragility** in this framing — Sieyuan transformers/breakers, brokered Chinese OEMs alleviate the high-end bottleneck. Inverts the Bloomberg "fragile China-dependent supply chain" framing.
	- **Power/permitting is the true 2026+ binding constraint** (7–10yr grid interconnection; gas pipeline + air-permit threading), pushing well-capitalized players to BtM, powered land, and direct grid payments — read-through to BESS (Oracle/DTE), gas turbines, fuel cells (Bloom Energy), and powered-land plays (Lancium, Cloverleaf).

