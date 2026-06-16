tags:: [[DRAM]], [[HBM]], [[HBF]], [[NAND]], [[SSD]], [[storage]], [[$005930.KS]], [[$000660.KS]], [[$MU]], [[memory]], [[super-cycle]], [[AI infrastructure]], [[semiconductor]]

- **Instrument**: $DRAM — memory & storage-industry index fund (not a single company); spans DRAM, HBM, and NAND/enterprise SSD
- **Top 3 holdings**: Samsung Electronics, SK Hynix, Micron — the "Big 3" controlling ≈90% of DRAM output and the majority of total memory; all three are also leading NAND/enterprise-SSD makers, so the index captures the AI-driven storage (SSD) tailwind alongside DRAM/HBM
- **Date**: 2026-06-04
- **Market cap of holdings (combined)**: ≈$3.5T (Big 3)
- **Position**: long
- **Why an index, not a single name**: The memory super-cycle is an *industry* thesis — tight oligopoly supply meeting AI-driven demand. An index diversifies single-name execution risk (e.g., Samsung HBM4 yield, Micron valuation/volatility) while capturing the structural pricing power shared across all three. See [[2026-06-04-memory-market-and-big3-financials]] for combined financials.
  
  ---
- ## References

	| | |
	|---|---|
	| [GenInnov — "Is DRAM at a Permanently Higher Plateau?"](https://www.geninnov.ai/blog/is-dram-at-a-permanently-higher-plateau) | [Ma & Patterson (Google) — "Challenges and Research Directions for Large Language Model Inference Hardware" (arXiv)](https://arxiv.org/pdf/2601.05047) |
	| [Korea import/export data (Korea Customs Service trade statistics)](https://tradedata.go.kr/cts/index_eng.do#) | [DRAMeXchange — DRAM/NAND spot & contract price tracker](https://www.dramexchange.com) |
	| [TrendForce — memory market research & data (runs DRAMeXchange)](https://www.trendforce.com) | [OpenRouter rankings — weekly token consumption by top models (demand proxy)](https://openrouter.ai/rankings) |

  ---
- ## Main Narrative
	- > What will the industry look like in 5–10 years? Is the market big enough to support 10x growth? Can it at least 4x revenue in 10 years?
	- **The one-line story**: AI has turned memory from a commodity into a structurally scarce strategic input. Demand (HBM + server DRAM + enterprise NAND, and potentially a new on-package flash tier via HBF) is growing exponentially against a supply curve that physically cannot ramp for years, handing the Big 3 oligopoly durable pricing power and a step-change in through-cycle earnings.
	- **Market size & growth** (see [[2026-06-04-memory-market-and-big3-financials]]):
		- Total memory TAM: **$220B (2025) → $890B (2026E)** per Morgan Stanley — a 4× jump, ≈80% price-driven, ≈20% volume
		- HBM market: **$31.5B (2025) → ≈$70B (2026E) → $116B (2027E) → $168B (2028E)** (Goldman Sachs)
		- The 2026 YoY *increment* in memory revenue alone (≈$595B) rivals the entire standalone smartphone TAM
	- **HBM price divergence vs. DDR**: HBM3e is moving up the value curve while DDR4 continues to deflate. A 2023-2025 HBM3e chart shows estimated cost rising from roughly **$15/GB to $21/GB** and **$0.29/GBps to $0.42/GBps**. The paired DDR4 chart shows the opposite trend from 2022-2025: roughly **$3/GB to $1.5-1.7/GB** and **$4.5/GBps to $2/GBps**, despite cyclical spikes. This is the clearest evidence that HBM is no longer behaving like plain commodity DRAM.
	- **The TSMC analogy**: DDR is a mature, standardized commodity where scale, yield learning, and supplier competition push cost per bit lower. HBM increasingly resembles leading-edge logic at TSMC: each generation can command higher ASPs because performance gains depend on technical advances only a handful of suppliers can execute reliably. The analogy is not perfect — memory remains cyclical and buyer concentration is high — but HBM's pricing power is increasingly determined by stacking, packaging, qualification, and yield, not DRAM bit supply alone.
	- **Why this cycle is a super-cycle, not a normal upturn** (see [[2026-06-01-memory-super-cycle-five-arguments]]):
	  1. **Structural demand shift** — AI training/inference replaces PC/smartphone replacement cycles as the demand driver; memory prices >2× even as 2025 smartphone units fell 13% and PCs 10%
	  2. **Triple whammy** — DRAM, HBM, and NAND all in simultaneous shortage (KV-cache for inference lifts DRAM; agent "dump-to-disk" lifts NAND; HBF is a potential future bridge product that pulls advanced NAND into the same AI memory stack)
	  3. **Supply discipline** — oligopoly focuses on margin and tech upgrades, not share grabs and price wars
	  4. **Dual physical bottleneck** — fab capacity *and* CoWoS packaging both gate HBM
	  5. **Rewritten contracts** — "lock volume, float price" LTAs; buyers prepay or fund supplier capex
	- **Supply cannot respond for years**: Tool→qualified-output lead time is ≈2 years (order → deliver → qualify → ramp). EUV/fab/packaging constraints cap DRAM bit growth near ≈30%/yr. SK Hynix projects tight supply until **at least 2028**; TSMC's CC Wei says AI chip demand "cannot be met for years" and warns the shortage is spreading from low-end to high-end devices ([[2026-06-04-tsmc-agm-cc-wei-ai-demand-2026]]).
	- **What has to be true**: AI capex stays elevated, model efficiency gains don't outrun demand growth, and the Big 3 hold supply discipline while CXMT stays sub-scale in global server DRAM.
	- ---
- ## Napkin Math
	- > Back-of-the-envelope valuation anchored to a 5- and 10-year horizon. Size the TAM, project revenue and margins, work backward to what you are paying today.
	- **Combined Big 3 memory revenue**: ≈$178B (2025) → ≈$712B (2026E share-adjusted, ≈80% of the $890B TAM). See [[2026-06-04-memory-market-and-big3-financials]] Table 0/0b.
	- **Valuation anchor (P/S on ≈$712B Big 3 memory revenue)**:
	  
	  | P/S | Implied Combined Market Cap | vs. Current ≈$3.5T |
	  |---:|---:|---:|
	  | 4× | $2.85T | −19% |
	  | 5× | $3.56T | +2% |
	  | 6× | $4.27T | +22% |
	- **Key read**: At ≈5× the share-adjusted revenue, implied market cap (≈$3.56T) ≈ today's ≈$3.5T — the market is already pricing ≈5× *peak-cycle* memory sales. Upside requires multiple expansion or revenue above the $712B level; the cyclical risk is that peak revenue deserves a *lower* multiple.
	- **Margin context**: SK Hynix Q1 2026 operating margin 72%; Micron FQ2 2026 gross margin 74.4% (guiding ≈81%). These are peak-cycle margins — the valuation question is normalized earnings power, not the spot peak.
	- ---
- ## Key Value Drivers
	- > Metrics to monitor for the thesis to play out.
	  
	  | Driver | What to watch |
	  |---|---|
	  | DRAM contract price (rate of change) | The consistent leading indicator of cycle and stock inflections; stocks lead DRAM, concurrent with NAND at trough |
	  | HBM demand vs. supply (mn GB) | Demand > supply by 2027E in MS model; convergence = warning |
	  | HBM vs. DDR price divergence | HBM3e cost/GB and cost/GBps rising 2023-2025 while DDR4 cost/GB and cost/GBps trend down 2022-2025; widening spread supports de-commoditization |
	  | Big 3 capex discipline | +26% (2025), +31% (2026E) — too much = future oversupply |
	  | LTA coverage % | Higher commodity-LTA coverage supports a P/E re-rating (MS: 5× → ≈8.5× if 70% covered) |
	  | Hyperscaler capex guidance | $695–725B 2026E; the swing variable — a single $20–30B cut reprices the chain |
	  | HBF design wins / packaging readiness | Watch whether HBF moves from papers/prototypes into real accelerator roadmaps; the tell is co-development among the Big 3, TSMC/Intel packaging, and GPU/NPU vendors |
	  | CXMT/YMTC qualification | Watch for China entering global hyperscale server-DRAM qualification at scale |
	  | Weekly token consumption (top models) | Real-time demand proxy — inference volume drives DRAM/HBM need; sustained WoW growth supports the demand leg (see table below) |
	- **Weekly token consumption — top models on OpenRouter** (data source: [openrouter.ai/rankings](https://openrouter.ai/rankings)). Tokens in trillions (T); sorted newest first:
	  
	  | Week | Tokens (T) | WoW growth |
	  |---|---:|---:|
      | 2026-06-08 | 44.6 | +23.5% |
      | 2026-06-01 | 36.1 | +12% |
	  | 2026-05-25 | 31.821 | +10.0% |
	  | 2026-05-18 | 28.931 | +7.5% |
	  | 2026-05-11 | 26.915 | +4.6% |
	  | 2026-05-04 | 25.743 | +7.9% |
	  | 2026-04-27 | 23.869 | +8.7% |
	  | 2026-04-20 | 21.953 | +6.8% |
	  | 2026-04-13 | 20.558 | −2.3% |
	  | 2026-04-06 | 21.036 | −22.2% |
	  | 2026-03-30 | 27.039 | +19.0% |
	  | 2026-03-23 | 22.730 | +11.7% |
	  | 2026-03-16 | 20.350 | n/a |
	- **Read**: From the 2026-04-13 trough (20.558T), consumption has compounded ≈7–10% WoW for 7 straight weeks to 34.528T — a steady, accelerating demand signal underpinning the inference-driven memory thesis. The late-March spike/reversion (27.0T → 21.0T) shows the series is noisy week-to-week; watch the trend, not single prints.
	- ---
- ## Secular Trends as Tailwinds
  
	- **Agentic AI** — Longer context windows, KV-cache, agent swarms → structural rise in memory intensity per workload ([[2026-06-03-ai-memory-wall-agentic-ai-dram-demand]])
	- **AI server = memory system** — NVL72-class racks carry 20.7TB HBM + 54TB DRAM; server share of DRAM bit demand 37% (2023) → 59% (2028E)
	- **Inference shift to NAND** — Enterprise SSD share of NAND demand 18% (2023) → 65% (2028E)
	- **SSD eating the HDD market** — Flash is displacing HDD in the datacenter: SSD ≈32% of storage *bits* (2026E) yet ≈ *dollar* parity with HDD (≈$47–49B vs ≈$53B) — earning far more per bit. IDC: ≈89% of cloud-provider data still on HDD = a large conversion pool; enterprise-SSD ≈ 10–14TB-HDD cost crossover ≈2026. NAND/SSD volume tailwind for the Big 3 (see Appendix; [[2026-05-05-micron-6600-ion-245tb-ssd]])
	- **KV-cache offload to flash (NVIDIA CMX)** — Serving longer context from AI agents creates a *new* flash demand tier. NVIDIA **CMX** (Context Memory eXtension, née ICMS) inserts a disaggregated **NVMe-flash "Tier G3"** between HBM/system RAM and deep network storage, dedicated to holding & reusing **KV cache** for long-context, multi-turn, agentic inference — so GPUs save/prestage context instead of recomputing it. Part of the STX reference arch (BlueField-4 DPUs, Spectrum-X, ConnectX-9, Dynamo/NIXL/DOCA); claims **≈5× throughput and ≈5× power efficiency**. As context windows hit millions of tokens and agents multiply, KV cache becomes a *persistent, strategic* asset → structural high-performance enterprise-SSD/NAND pull for the Big 3 ([[2026-06-06-nvidia-cmx-kv-cache-flash-storage-tier]])
	- **HBF (High-Bandwidth Flash) as a new memory tier** — HBF brings dense 3D NAND into or next to the accelerator package as a bridge between scarce/expensive HBM and slower off-package NVMe SSDs. If commercialized, it matters because it pulls *more NAND content* into the AI compute bill of materials, upgrades flash from a peripheral storage device into a packaging-sensitive memory tier, and extends the Big 3's relevance beyond DRAM/HBM into on-package inference memory.
	- **HBM de-commoditization** — DDR4's cost curve still looks like classic memory: standardized, mature, oversupply-prone, and deflationary over time. HBM3e's cost curve looks like a scarce AI bottleneck: capacity and bandwidth cost rise as customers demand more performance and suppliers absorb higher stacking, packaging, and qualification complexity. That divergence is the economic core of the $DRAM thesis.
	- **Edge / physical AI** — AI agents in phones, autos, robots add a second demand wave beyond data centers
	- **Chipflation** — Memory inflation now a macro input — PPI electronics +27.6% YoY ([[2026-06-03-chipflation-macro-cpi-ppi-impact]])
	- ---
- ## Innovative Culture
	- > Does the industry compound innovation?
	- Memory is an R&D- and capex-treadmill business: progress comes from node shrinks (EUV), stacking (HBM TSV, hybrid bonding), packaging (CoWoS), and now potentially *architectural tiering* via HBF rather than from classic product-cycle disruption. The Big 3 differentiate on yield and time-to-volume of next-gen HBM (HBM4/4E), but the next innovation vector may be pulling NAND closer to compute and turning flash into a heterogeneous memory layer for inference. SK Hynix currently leads on HBM yield/UTR; Samsung is the most vertically integrated candidate to push HBF-style concepts given its NAND + foundry + packaging stack; Micron is the US strategic supplier with both high-layer NAND and high-bandwidth-memory ambition. Risk: value capture may shift toward packaging integrators and accelerator vendors if HBF becomes real, so not all innovation automatically accrues to commodity-memory shareholders.
	- The pricing evidence strengthens the innovation argument. HBM's economics increasingly resemble a scarce advanced-manufacturing bottleneck rather than a commodity bit market: higher ASPs are tied to TSV stacking, finer interconnects, thermal management, advanced packaging, known-good-die sorting, and customer qualification. In this respect HBM looks more like leading-edge foundry logic than legacy DRAM, because technological complexity determines pricing power.
	- ---
- ## Vibe Checks
	- **What do you like most?**
		- An oligopoly with genuine, AI-driven, multi-year demand visibility and contractually locked pricing — a structurally better setup than any prior memory cycle.
	- **What do you hate most?**
		- It is still memory. Every prior "this time is different" appeared at a cycle peak and was wrong. Buying peak earnings at peak margins is how memory investors get hurt.
	- **How popular is the product or service?**
		- Extreme: HBM sold out through 2026 and largely 2027; customers prepay and fund supplier capex to secure allocation.
	- ---
- ## Competition Landscape
	- > Within the index, the three holdings compete; externally, China and architectural substitutes are the threats.
	  
	  | Competitor | Advantage / threat | Assessment |
	  |---|---|---|
	  | SK Hynix (holding) | HBM leader; best yield/UTR; strong Nvidia exposure | Highest-quality earnings; ≈56% HBM share 2025 |
	  | Samsung (holding) | Largest DRAM capacity; broadest base; HBM4 recovery | Execution/yield risk; countercyclical-share-grab history is the key oligopoly-discipline risk |
	  | Micron (holding) | Only US-HQ strategic supplier; gov't-buyer edge | Strong cycle position but high valuation/volatility (MS least-preferred of the three) |
	  | CXMT / YMTC (China) | State-subsidized, price-insensitive capacity | Sub-scale in global hyperscale DRAM today; the key long-term supply-discipline wildcard |
	  | Architectural substitutes | CXL pooling, PIM, quantization, MoE, SRAM caches, HBF | Reduce HBM per workload; incentive rises with HBM price. HBF is partially substitute, partially complement: bearish for HBM content per accelerator, bullish for NAND/packaging content |
	- ---
- ## Durable and Unfair Competitive Advantages
	- > Moats are time-bound — a bridge to the next defensible position.
	  
	  | Competitive advantage | Detail |
	  |---|---|
	  | Oligopoly structure | 3 firms control ≈90% of DRAM output; rational, margin-focused behavior vs. the 15+ suppliers of the 1990s |
	  | Capital intensity barrier | New fabs cost multi-billions, take years, and need EUV tool allocation — near-impossible for new entrants to replicate at scale |
	  | HBM technical lead | TSV stacking, yield, and CoWoS co-optimization create a multi-year gap vs. would-be entrants (CXMT) |
	  | LTA lock-in | 3–5 year agreements + prepayments convert cyclical commodity sales into durable, high-margin, visible revenue ([[2026-06-03-memory-two-tier-market-and-ltas]]) |
	  | Two-tier allocation power | AI/cloud buyers locked in first; suppliers steer scarce supply to the highest-margin, most-durable contracts |
	- ---
- ## Pre-Mortem — What Can Go Wrong?
	- > Assume the thesis fails. The bear case (see [[2026-06-02-memory-cycle-bear-case-arguments]]) needs only ONE of these, not all:
	- 1. **Supply catches demand** — +30% capex YoY is exactly how prior oversupply cycles began; new capacity lands 2027–28, the supposed peak-demand window. CXMT's subsidized, price-insensitive supply has no commercial brake.
	  2. **Efficiency outruns demand** — algorithmic gains (cheaper training, KV-cache compression, quantization, MoE, speculative decoding) cut memory intensity per workload; rising HBM perf-ratio (H100 591 → R200 2,692) intensifies the incentive to route around HBM.
	  3. **HBF/value-capture mismatch** — if HBF becomes important, the Big 3 may sell more high-value NAND, but the *profit pool* could accrue disproportionately to TSMC/Intel packaging, custom accelerator vendors, or system architects rather than to memory makers themselves.
	  4. **Hyperscaler capex moderates** — it is guidance, not contract; Microsoft already paused once; ≈5% of US GDP is a historically extreme allocation that has always reverted eventually.
	  5. **Samsung breaks discipline** — documented countercyclical share-grab behavior (2022–23); an informal oligopoly breaks when one actor defects.
	  6. **Consumer DRAM snap-back** — deferred PC/smartphone replacement returns just as HBM supply ramps, correcting blended ASPs; "memory prices falling" headlines reprice the whole group even if HBM holds.
	  7. **Contracts ≠ demand** — "lock volume, float price" can be read as buyer *uncertainty*; volume commitments get renegotiated in every commodity downturn.
	- **Cycle-risk sizing**: peak-to-trough EPS revisions average ≈2× (+102% to −88%) over ≈12 months; stocks don't get rewarded for buying peak earnings as the second derivative rolls.
	- ---
- ## Anecdotes & Opinions
	- > Qualitative signals that don't fit a model but often move early.
	-
	- | Date | Source | Anecdote / Opinion | Signal direction |
	  |------|--------|--------------------|-----------------|
	  | 2026-06 | TSMC AGM (CC Wei) | Memory chip shortage spreading from low-end to high-end devices by end-2026; warns against "unsustainable" memory-style price hikes — implicitly validates how aggressive memory pricing has become | bullish |
	  | 2026-Q1 | SK Hynix earnings | HBM customer requests already exceed planned production capacity for the next three years | bullish |
	  | 2026 | Michael Burry / bear case | Micron gross margin ≈74% characterized as an all-time high — peak-margin warning | bearish |
	  | 2026 | Bear thread | "This time is different" has marked the peak of every prior memory cycle; strong consensus is a contrary indicator | bearish |
	  | 2026-06 | Ex-SK Hynix strategy director (34 yrs), via @SteadyCompound | **Supply is slower and more controllable than headline capex implies**: even after ordering equipment (≈1-yr cycle) and installing it, makers can delay wafer input to watch the market. Samsung's P5 fab (600k wpm, ≈ its entire current 650k wpm capacity) completes 2028 → shipments not until ≈2029. Meanwhile LTAs are now **binding purchase obligations** (not forecasts) — hyperscalers legally commit to buy, shifting inventory risk off suppliers — and prepay **10–30%** of a $15–20B fab's cost, de-risking vendor capex | bullish |
	- ---
- ## Appendix — SSD vs HDD Market Share (Bits vs Dollars)
	- **Source**: industry estimates compiled via web search (IDC, Gartner, market-research firms); figures vary by source/definition (total vs enterprise vs data-center), treat as approximate. See [[2026-05-05-micron-6600-ion-245tb-ssd]].
	  
	  | Metric (≈2026E) | HDD | SSD |
	  |---|---:|---:|
	  | Capacity shipped — exabytes ("bits") | ≈3,200 EB (**≈68%**) | ≈1,400 EB (**≈32%**) |
	  | Enterprise / data-center revenue ($) | ≈$53B | ≈$47–49B (**≈ parity**) |
	  | Forward revenue CAGR | **≈−1%** | **≈+8%** |
	- **The key contrast**: HDD still ships ≈2/3 of the *bits*, but SSD is roughly **at dollar parity** — flash earns far more revenue per bit, and the value is migrating to SSD even as HDD wins on raw capacity
	- **Installed base skews further to HDD**: IDC estimates ≈**89% of data stored by lead cloud providers still resides on HDD** — a large pool still available to convert to flash
	- **Cost crossover**: enterprise SSD ≈ 10–14TB-HDD cost parity around 2026 — the tipping point that widens flash's addressable market (and the backdrop for Micron's 245TB drive)
	- **Why it matters for $DRAM**: SSD displacement is incremental NAND-bit demand for the Big 3 (Samsung, SK Hynix, Micron) on top of the DRAM/HBM cycle — a structural, multi-year volume tailwind largely independent of the DRAM price cycle
	- ---
- ## Appendix — High-Bandwidth Flash (HBF)
	- **Definition**: HBF is an emerging architecture that stacks dense 3D NAND flash with a logic base die and places it directly inside or beside the accelerator package, creating a memory tier between HBM and off-package NVMe SSD.
	- **Why it exists**: AI inference is pushing against the "memory wall" from two directions at once: HBM is extremely fast but too expensive and capacity-constrained, while PCIe SSD is cheap and dense but too far away and too slow. HBF aims to bridge that gap.
	- **Economic/technical claim**: Versus HBM, HBF should offer materially higher capacity per stack and lower cost per GB, while still delivering much higher effective bandwidth than conventional SSD by exploiting massive internal NAND parallelism and much shorter package-level interconnects.
	- **What has to work technically**:
		- Massively parallelized 3D NAND subarrays so flash can serve wide, many-lane reads instead of narrow sequential storage traffic
		- HBM-like packaging techniques applied to NAND: TSVs, interposers, and eventually finer-pitch hybrid bonding (W2W / D2W)
		- Near-storage compute/search inside the base logic die so data movement is reduced and read-heavy inference tasks run "in the storage tier"
		- Read-optimized controllers because the best early use cases are AI inference, vector search, and KV-cache retrieval, not write-heavy enterprise storage
	- **Why it matters for this thesis**:
		- Bull case: it expands the AI memory bill of materials from DRAM/HBM into higher-value NAND, giving the Big 3 another way to monetize inference growth
		- Nuance: HBF is not purely additive; it may cap *some* HBM demand per workload by inserting a cheaper intermediate tier
		- The most advantaged memory vendors are the ones that combine leading 3D NAND with advanced packaging relationships and enough controller/system expertise to ship a usable tier, not just raw bits
	- **Who is best positioned**:
		- **Samsung** — strongest vertical-integration story: V-NAND + foundry + X-Cube packaging + PIM/near-memory research
		- **SK Hynix** — best current stacking/TSV credibility from HBM leadership; plausible path to translate multi-die packaging know-how into flash
		- **Micron** — strategically important US supplier with strong NAND roadmap and a clear incentive to climb the memory hierarchy
		- **TSMC / Intel** — not direct beneficiaries of the memory index, but critical enablers because HBF only becomes real if advanced packaging platforms like CoWoS / SoIC / Foveros Direct can integrate flash stacks tightly with AI logic
	- ---
- ## Appendix: The 2022–2023 Memory Downcycle (How the Last Cycle Played Out)
	- **Source**: user-provided article. Context for the current thesis — the 2022–2023 cycle is the textbook severe downturn that immediately preceded today's AI-driven upcycle; it shows how the glut formed, how the Big 3 behaved, and how AI ended it.
	- **One-line**: a violent swing from pandemic-era shortages to massive oversupply forced unprecedented losses on manufacturers before pivoting into a structural, AI-driven recovery.
	- ### How It Started — The Pandemic Hangover (bullwhip effect)
		- **Demand shock**: 2020–2021 remote-work/digital-acceleration surged demand for PCs, laptops, smartphones, and cloud data-center infra. Fearing supply-chain disruption, buyers **aggressively over-ordered** DRAM and NAND to build safety stock.
		- **Reversal**: by early 2022, high inflation, rising rates, and economic reopening **collapsed consumer electronics spending**.
		- **Glut**: PC and smartphone shipments fell double-digits; device makers and hyperscalers sat on months of excess, expensive memory inventory and **stopped ordering**, choosing to burn through existing stock.
	- ### The Manufacturer Dilemma — Price Crashes & Cash Burns
		- Fabs are capital-intensive and costly to idle, so producers initially **kept lines running** → record inventory, crashing prices. Through 2022–early 2023, **DRAM and NAND ASPs plunged >50%**.
		- **Phase 1 — Denial & market-share defiance (late 2022)**: **Micron and SK Hynix blinked first**, announcing **30–50% capex cuts** for 2023 and trimming wafer starts. **Samsung** took a contrarian stance, leveraging cash reserves to **refuse production cuts** and squeeze weaker rivals.
		- **Phase 2 — Capitulation & historic cuts (early 2023)**: by Q1 2023 the industry was losing **billions/quarter** with operating margins sharply negative. **In April 2023, Samsung reversed course** and announced a "meaningful" production cut, aligning with Micron and SK Hynix. The Big 3 (plus NAND players **Kioxia, Western Digital**) enacted **historic utilization cuts** — idling lines and delaying node transitions to starve the market of supply.
	- ### How Buyers Reacted — Opportunistic De-stocking
		- **Strikebound buying**: with prices falling week-over-week, buyers played a waiting game — refusing long-term agreements and buying only as-needed on the **spot market** to exploit falling prices.
		- **Inventory depletion**: hyperscalers (Microsoft, AWS, Meta) and PC OEMs (Dell, HP) spent **~12–18 months** drawing down stockpiles.
	- ### How It Ended — The Bottom & the AI Pivot
		- **Bottom: 2H 2023.** By **Q3 2023**, aggressive production cuts finally matched depleted buyer inventories → supply/demand equilibrium, and **DRAM spot prices ticked up for the first time in ~2 years**.
		- **The AI lifeline**: the explosion of Generative AI shifted demand from commodity DRAM toward high-margin **HBM and enterprise SSDs**. Because **HBM needs ~3–4× the wafer capacity** of conventional DRAM, manufacturers **rapidly reallocated lines to AI memory** — by late 2023 this diversion constrained standard PC/server memory supply, evaporated the glut, and set the stage for the structural upcycle this thesis is built on.
