- tags:: [[Amazon]], [[$AMZN]], [[advertising]], [[retail media]], [[CTV]], [[DSP]], [[The Trade Desk]], [[$TTD]], [[programmatic]], [[identity graph]], [[agentic commerce]], [[OpenAI]], [[$GOOGL]], [[Meta]], [[agencies]], [[Publicis]], [[Roku]]
  file-created-at:: 2026-06-04

- ## Amazon's Advertising Advantages — Identity Spine, DSP & CTV (Adam Epstein / Gigi)
	- **Source**: Mobile Dev Memo podcast, "Understanding Amazon's advertising advantages," Eric Seufert w/ **Adam Epstein** (co-founder/CEO **Gigi/GG**, agentic OS for programmatic media; ex co-president of Perpetua, now owned by Omnicom; ~8 yrs in Amazon ads). June 4, 2026.
	- **Disclosure**: Seufert is an investor in GG. GG = AI agents for the Amazon DSP; launched summer 2025; powers **hundreds of millions** in Amazon DSP spend; won Amazon's **Global Technology Innovation Partner Award (Nov 2025)**. Epstein career: billions in ad spend, **$15–20B GMV**.
	- **Core thesis**: Amazon is winning ad share not by hoarding data (walled-garden model) but by **broadcasting its proprietary first-party data + deterministic identity graph** onto third-party CTV inventory, centralizing media buyers' entire TV budgets into the **Amazon DSP**. The DSP — not on-site sponsored ads — is the growth engine.

- ## Amazon Ad Business — Size & Growth
	| Metric | Value |
	|---|---|
	| 2024 ad revenue (per guest) | **"just shy of $50B"**, +**20% YoY** (reported FY2024 actually **$56.2B**) |
	| **LTM ad revenue (Q2'25–Q1'26)** | **~$72B** (Q2'25 $15.7B + Q3'25 ~$17.7B + Q4'25 $21.3B + Q1'26 $17.24B) |
	| FY2025 ad revenue | **$68.6B**, +**22%** vs $56.2B FY2024 |
	| Latest quarter (Q1 2026) | **$17.24B**, +**24% YoY** |
	| Target | **~$100B** (incremental ~$30B mostly from **DSP**) |
	| Revenue growth | decelerated from **27% peak (Q4 2023)** → back to **mid-20s** last 4 qtrs |
	| Amazon Ads headcount | tens of thousands; **~60–70% work on DSP**, not sponsored ads |
	| Retail media share | Amazon = **70–80%** of all retail media |
	| US e-commerce share | Amazon = **~50%** of total US e-commerce |
	- **Two halves of the business**:
		- **On-site sponsored ads** — PPC on search / product detail pages. **Capped by inventory & price**; "everything on Amazon is already an ad"; **CPCs flatlined** (sellers can't pay more past profitability thresholds). Low growth.
		- **Amazon DSP** — display, video, **CTV** (primary), audio across O&O (Prime Video) + 3P (Disney, Netflix). **All incremental growth comes here**, specifically **CTV buying**.

- ## The Identity Spine (the central moat)
	- Authenticated graph **deterministically reaches 90% of US households** — verified, logged-in, **non-modeled** data.
	- Built on the **Roku partnership** (announced Cannes, summer 2025): unified identity service combining Amazon + Roku identities. **Roku = largest CTV hardware OEM**, closing the deterministic-household gaps Amazon couldn't see alone.
	- **Disney deal** (and Roku) = **identity deals, NOT inventory-expansion deals** — the strategic tell.
	- **Why it matters for TV**: large TV buyers manage to **reach & frequency**; a **deduplicated identity spine** across all TV buys is the critical primitive. Amazon's pitch: centralize *all* TV buying (linear, DV360, Trade Desk) into Amazon DSP for the **highest-signal unified R&F layer** available.

- ## Endemic → Non-Endemic Expansion ("unfair data advantages")
	- **Endemic** advertisers = e-commerce/CPG brands where Amazon owns proprietary purchase data. Already largely centralized to DSP.
	- **Next leg = non-endemic categories** — largest are **financial services, pharma, auto**:
	| Category | Amazon's proprietary edge |
	|---|---|
	| **Auto** | One of largest CTV categories. **Amazon Autos** = digital showrooms; some OEMs allow purchase on Amazon; creates a **new path-to-purchase touchpoint** no other DSP has. Shopping data on household/family car decisions. |
	| **Pharma** | Health purchase history + **One Medical** (prescriptions) + **PillPack** (acquired >$1B). Data **not yet exposed** to advertisers — but *if* exposed, turns pharma into a pseudo-endemic category with an unfair edge. |
	| **Financial services** | Purchase/decision signals; same playbook. |
	- Strategy = turn non-endemic categories **pseudo-endemic**, then use the data edge to centralize budget into the DSP.

- ## Competitive Dynamics — Trade Desk under existential pressure
	- Amazon's stated DSP competitors: **The Trade Desk (TTD)** and **DV360 (Google)**.
	- **TTD red flags**:
		- **4 CFOs in one year** (one interim) — per Adweek; described as **unprecedented** outside financial distress/regulatory intervention.
		- Owns **no proprietary inventory and no proprietary data** — Amazon + Google have created "existential doubt."
		- Growth decelerating; unclear if it regains prior rate/scale. "How did I go bankrupt? Slowly, then all at once."
	- **TTD's remaining edge**: **log-level impression data** matched back to outcomes — **open data**. Critical for **pharma** (two-sided: market to consumers *and* HCPs; need the specific impression → HCP purchase link), which you **can't** do on Amazon or Google today.
	- **Epstein vs Jeff Green (TTD CEO)** — calls Green's claims "categorically false":
		- Claim "Amazon DSP isn't a priority" → false (60–70% of Amazon Ads headcount; ~$30B incremental rides on it).
		- Claim "Amazon favors own inventory / pushes Prime Video" → false; **Amazon sales are incentivized to sell non-Amazon inventory** (Disney/Netflix/NBC/Paramount) to centralize *all* TV buys. Leading with only Prime Video would defeat the centralization strategy.
	- **Lynchpin framing**: Google brings buyers into DV360 via **YouTube**; Amazon brings them into DSP via **Prime Video ads** (only buyable on Amazon DSP; **on by default** → most at-scale ad-supported premium CTV service). Positioning: Amazon = **premium CTV**; Google/YouTube = "cat videos / creators / junk."

- ## Blind Spots & Ceiling
	- Cannot bring its data to **social ads** or **Google Search** — the two closed surfaces.
	- **Constrained inventory**: unlike **Meta/TikTok/YouTube**, Amazon **can't create net-new organic-content ad inventory**; DSP is bounded by broader CTV supply (growing, but slower than Meta).
	- **Social commerce** = blind spot (Meta partnership exists, little scale).
	- Global digital-ad share: **Meta just passed Google**; Amazon (2nd–3rd) faces structural challenges pushing **past $100B** in current form.

- ## Chatbots / Agentic Commerce (the big swing)
	- **Disruption dilemma** (shared with Google): most ad revenue is **search-based** (keywords / SKUs). If discovery shifts to chatbots, Amazon **erodes its own base** (fewer keyword clicks / SKU views).
	- **Amazon's answer = Rufus** (its AI chatbot) with **sponsored prompts**, already monetizing — mirrors Google monetizing AI answers in Gemini. (Google data point: **1B MAU for AI mode at I/O; Search still +19% YoY** — Seufert argues that's *winning*, not losing.)
	- **The OpenAI hypothesis** (Seufert): Amazon invested in **Anthropic**, did a **Meta** deal — next is **account-linking with ChatGPT**, broadcasting the identity spine + ad infra onto chatbots as **"the next social"** (Amazon missed social; lost it; Twitch too small).
		- **ChatGPT needs Amazon**: e-commerce ads don't scale without reliable catalog/inventory/pricing/delivery data; **Amazon = ~50% of US e-commerce**. A **Shopify-only** ChatGPT commerce product stays **niche**. To reach **$100B ad revenue you need CPG + e-commerce** — fastest path is partnering with Amazon.
		- Amazon also gets an OpenAI **Trainium** customer; would demand a large cut of ChatGPT ad revenue. PLAs / DSP display easily extendable to ChatGPT. Timing/structure TBD.
	- **Seufert's "agentic commerce is over" call**: **Rufus / Walmart's Sparky = agentic commerce** = **on-platform discovery**, and it already happened. **Independent agentic commerce was DOA**: instant checkout suboptimal, affiliate model misaligned; **OpenAI shut down instant checkout after ~6 months**. The playbook isn't being written — **it's advertising**, and it requires cooperation from the largest retail/ad entity (Amazon). The moment ChatGPT accepts Amazon ads + identity spine, every chatbot follows → death of independent agentic commerce.

- ## Agencies — disruption strengthens them (near term)
	- Historically, big tech disruptions **push advertisers toward agencies** ("agencies are like cockroaches"). Complexity (programmatic, retail media, agentic AI) → brands hire experts.
	- **In-housing**: ~**1/3 of total US media spend**, growing **low-single-digit %**; even reaching **~40% by 2028** wouldn't be the majority. Holdcos losing share; **independent agencies + in-housing** both growing.
	- **AI-enabled services tailwind**: agencies can scale revenue **without linear headcount** → software-like margins → **higher valuation multiples** → more agency proliferation.
	- **GG's wedge**: agencies control most Amazon DSP buying; GG **rewrites media-buying playbooks "unconstrained by human labor"** — AI agents always-on, using a proprietary ML model for bids/budgets/adjustments at precision/scale humans can't match → **immediate performance gains**. Next: expand to **DV360 + Trade Desk** = **orchestration layer across all 3 enterprise DSPs**.
	- Long-term ambiguity: in-housing could reclaim once AI tooling matures; Epstein sees agentic AI as an **agency tailwind for the next 2–3 yrs** ("three years out, maybe Neuralinks in CMOs").

- ## Shoppable TV — stays niche
	- **Low single-digit % conversion**; not becoming ubiquitous even on Amazon (its best possible channel).
	- **"TV is the second device"** (James Borrow, Universal Ads) — the phone is the engaged first device; people don't want to shop on the remote.
	- **Attribution doesn't need it**: timestamps + IP address (TV + phone on same home WiFi) ≈ **near-deterministic attribution** anyway; people buy on the phone they already use. GG recommends a shoppable creative per TV ad and lets the agent pick the winner, but treats it as niche.

- ## LiveRamp / Publicis (data-layer M&A)
	- Publicis's **LiveRamp** acquisition read as **defensive** vs platforms (like Amazon) extending reach to non-platform inventory.
	- Holdco profit shift = **non-services revenue**: **principal-based media buying + proprietary audiences**. Publicis already marks up CPMs via **Epsilon** (audience graph).
	- **LiveRamp** lets Publicis **collaborate first-party signals** across brands/retailers (multi-tenant data clean-room style) and **mark up fees** on resulting proprietary audiences — strengthening its data layer across publishers/buyers/brands.

- ## Investment Implications
	- **$AMZN ads**: deterministic 90%-household identity spine + Prime Video lock-in + DSP centralization = durable, compounding CTV share-taker; clearest path to ~$100B ad revenue, though structurally **capped vs Meta** on net-new inventory and blocked from social/Search.
	- **$TTD bear signal**: no owned data/inventory + 4 CFOs/yr + Amazon/Google centralization pitch = structural share erosion; **log-level data + pharma HCP attribution** is the defensible niche to watch.
	- **$GOOGL**: same search-disruption dilemma as Amazon, but monetizing AI mode (1B MAU, Search +19%) — "winning" doesn't require the top benchmark model.
	- **OpenAI × Amazon ad partnership** is the key unrealized catalyst — would validate the "advertising, not independent agentic commerce" thesis and broadcast Amazon's identity spine onto chatbots ([[2026-06-05-goldman-agentic-ai-token-demand-24x-by-2030]]).
	- **Agencies / agentic-media tooling** (GG-type) = near-term winners of complexity; in-housing a slow secular drag, not a near-term threat.
