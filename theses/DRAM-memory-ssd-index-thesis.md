tags:: [[DRAM]], [[HBM]], [[HBF]], [[NAND]], [[SSD]], [[storage]], [[$005930.KS]], [[$000660.KS]], [[$MU]], [[memory]], [[super-cycle]], [[AI infrastructure]], [[semiconductor]]

- **Instrument**: $DRAM — memory & storage-industry index fund (not a single company); spans DRAM, HBM, and NAND/enterprise SSD
- **Top 3 holdings**: Samsung Electronics, SK Hynix, Micron — the "Big 3" controlling ≈90% of DRAM output and the majority of total memory; all three are also leading NAND/enterprise-SSD makers, so the index captures the AI-driven storage (SSD) tailwind alongside DRAM/HBM
- **Date**: 2026-06-04
- **Market cap of holdings (combined)**: ≈$3.5T (Big 3)
- **Why an index, not a single name**: The memory super-cycle is an *industry* thesis — tight oligopoly supply meeting AI-driven demand. An index diversifies single-name execution risk (e.g., Samsung HBM4 yield, Micron valuation/volatility) while capturing the structural pricing power shared across all three. See [[2026-06-04-memory-market-and-big3-financials]] for combined financials.
  
  ---
- ## References
  
  | | |
  |---|---|
  | [GenInnov — "Is DRAM at a Permanently Higher Plateau?"](https://www.geninnov.ai/blog/is-dram-at-a-permanently-higher-plateau) | [Ma & Patterson (Google) — "Challenges and Research Directions for Large Language Model Inference Hardware" (arXiv)](https://arxiv.org/pdf/2601.05047) |
  | [Korea import/export data (Korea Customs Service trade statistics)](https://tradedata.go.kr/cts/index_eng.do#) | [DRAMeXchange — DRAM/NAND spot & contract price tracker](https://www.dramexchange.com) |
  | [TrendForce — memory market research & data (runs DRAMeXchange)](https://www.trendforce.com) | [OpenRouter rankings — weekly token consumption by top models (demand proxy)](https://openrouter.ai/rankings) |
  | [GPU pricing index dashboard](https://semianalysis.com/gpu-pricing-index/) | |
  
  ---
- ## Main Narrative
	- > What will the industry look like in 5–10 years? Is the market big enough to support 10x growth? Can it at least 4x revenue in 10 years?
	- **The one-line story**: AI has turned memory from a commodity into a structurally scarce strategic input. Demand (HBM + server DRAM + enterprise NAND, and potentially a new on-package flash tier via HBF) is growing exponentially against a supply curve that physically cannot ramp for years, handing the Big 3 oligopoly durable pricing power and a step-change in through-cycle earnings.
	- **Market size & growth** (see [[2026-06-04-memory-market-and-big3-financials]]):
		- Total memory TAM: **\$220B (2025) → \$890B (2026E)** per Morgan Stanley — a 4× jump, ≈80% price-driven, ≈20% volume
		- HBM market: **\$31.5B (2025) → ≈\$70B (2026E) → \$116B (2027E) → \$168B (2028E)** (Goldman Sachs)
		- The 2026 YoY *increment* in memory revenue alone (≈$595B) rivals the entire standalone smartphone TAM
	- **HBM price divergence vs. DDR**: HBM3e is moving up the value curve while DDR4 continues to deflate. A 2023-2025 HBM3e chart shows estimated cost rising from roughly **\$15/GB to \$21/GB** and **\$0.29/GBps to \$0.42/GBps**. The paired DDR4 chart shows the opposite trend from 2022-2025: roughly **\$3/GB to \$1.5-1.7/GB** and **\$4.5/GBps to \$2/GBps**, despite cyclical spikes. This is the clearest evidence that HBM is no longer behaving like plain commodity DRAM.
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
	- **Combined Big 3 memory revenue**: ≈\$178B (2025) → ≈\$712B (2026E share-adjusted, ≈80% of the \$890B TAM). See [[2026-06-04-memory-market-and-big3-financials]] Table 0/0b.
	- **Valuation anchor (P/S on ≈$712B Big 3 memory revenue)**:
	  
	  | P/S | Implied Combined Market Cap | vs. Current ≈$3.5T |
	  |---:|---:|---:|
	  | 4× | $2.85T | −19% |
	  | 5× | $3.56T | +2% |
	  | 6× | $4.27T | +22% |
	- **Key read**: At ≈5× the share-adjusted revenue, implied market cap (≈\$3.56T) ≈ today's ≈\$3.5T — the market is already pricing ≈5× *peak-cycle* memory sales. Upside requires multiple expansion or revenue above the \$712B level; the cyclical risk is that peak revenue deserves a *lower* multiple.
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
	  | Hyperscaler capex guidance | MS (Apr 2026): \$805B 2026E / \$1,116B 2027E (raised from \$765B/\$951B); AMZN+GOOGL+META+MSFT+ORCL combined; the swing variable — a single \$20–30B cut reprices the chain |
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
	- **Hyperscaler + neocloud capex from Exponential View chart** (source: Exponential View analysis; company filings. Total capex includes PP&E + leases; 2026E based on guidance. Annual totals are chart labels; company stack mix is visual and not used as precise data):

	  | Year | Total capex ($B) | YoY growth | Cumulative since 2020 ($B) | Read-through for memory |
	  |---|---:|---:|---:|---|
	  | 2020 | 97 | n/a | 97 | Pre-AI baseline for cloud infrastructure spend |
	  | 2021 | 132 | +36% | 229 | Cloud buildout still mostly conventional hyperscaler growth |
	  | 2022 | 160 | +21% | 389 | Capex continues rising before the GenAI acceleration fully hits |
	  | 2023 | 163 | +2% | 552 | Pause year; establishes the pre-boom base |
	  | 2024 | 268 | +64% | 820 | AI capex step-up begins to show in aggregate spend |
	  | 2025 | 459 | +71% | 1,279 | Buildout broadens across hyperscalers and neoclouds |
	  | 2026E | 848 | +85% | 2,127 | Memory demand anchor: AI infrastructure capex is nearly 9x the 2020 level |
	- **Read**: The chart implies roughly **$2.1T cumulative hyperscaler + neocloud capex from 2020-2026E**, with **2024-2026E alone contributing ~$1.6T**. This supports the $DRAM thesis because memory demand is being pulled by a multi-year infrastructure buildout, not just one customer's training cluster cycle. Risk: total capex is not pure AI capex; it includes pre-planned cloud/SaaS, metaverse, and logistics spend, so use it as a demand-context proxy rather than a direct HBM/DRAM revenue model.
	- ---
- ## Secular Trends as Tailwinds
	- **Agentic AI** — Longer context windows, KV-cache, agent swarms → structural rise in memory intensity per workload ([[2026-06-03-ai-memory-wall-agentic-ai-dram-demand]])
	- **AI server = memory system** — NVL72-class racks carry 20.7TB HBM + 54TB DRAM; server share of DRAM bit demand 37% (2023) → 59% (2028E)
	- **Inference shift to NAND** — Enterprise SSD share of NAND demand 18% (2023) → 65% (2028E)
	- **SSD eating the HDD market** — Flash is displacing HDD in the datacenter: SSD ≈32% of storage *bits* (2026E) yet ≈ *dollar* parity with HDD (≈\$47–49B vs ≈\$53B) — earning far more per bit. IDC: ≈89% of cloud-provider data still on HDD = a large conversion pool; enterprise-SSD ≈ 10–14TB-HDD cost crossover ≈2026. NAND/SSD volume tailwind for the Big 3 (see Appendix; [[2026-05-05-micron-6600-ion-245tb-ssd]])
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
	  | CXMT / YMTC (China) | State-subsidized, price-insensitive capacity | Sub-scale in global hyperscale DRAM today; the key long-term supply-discipline wildcard. **Update (WSJ Feb 2026)**: HP and other major PC makers in talks to use CXMT chips in Asia-bound products — first signal of CXMT entering branded OEM supply chains; not yet a global server-DRAM threat but a leading indicator of eventual volume displacement in consumer segments |
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
	- **Supply catches demand** — +30% capex YoY is exactly how prior oversupply cycles began; new capacity lands 2027–28, the supposed peak-demand window. CXMT's subsidized, price-insensitive supply has no commercial brake.
	  **Efficiency outruns demand** — algorithmic gains (cheaper training, KV-cache compression, quantization, MoE, speculative decoding) cut memory intensity per workload; rising HBM perf-ratio (H100 591 → R200 2,692) intensifies the incentive to route around HBM.
	- **HBF/value-capture mismatch** — if HBF becomes important, the Big 3 may sell more high-value NAND, but the *profit pool* could accrue disproportionately to TSMC/Intel packaging, custom accelerator vendors, or system architects rather than to memory makers themselves.
	  **Hyperscaler capex moderates** — it is guidance, not contract; Microsoft already paused once; ≈5% of US GDP is a historically extreme allocation that has always reverted eventually.
	- **Samsung breaks discipline** — documented countercyclical share-grab behavior (2022–23); an informal oligopoly breaks when one actor defects.
	  **TSMC cultivates non-Big-3 memory supply** — TSMC bringing Winbond into next-gen WoW (Wafer-on-Wafer) AI-chip stacking is not an immediate HBM/DDR replacement, but it is a strategic warning. If TSMC can qualify Taiwanese DRAM wafers and stack them directly with logic wafers, some AI-memory value capture and supply optionality shifts from Samsung/SK Hynix/Micron toward the foundry/packaging layer. The risk is not near-term oversupply; it is that TSMC reduces dependence on the Big 3 over time and weakens the scarcity premium embedded in the $DRAM thesis.
	  **Consumer DRAM snap-back** — deferred PC/smartphone replacement returns just as HBM supply ramps, correcting blended ASPs; "memory prices falling" headlines reprice the whole group even if HBM holds.
	  **Contracts ≠ demand** — "lock volume, float price" can be read as buyer *uncertainty*; volume commitments get renegotiated in every commodity downturn.
	- **Cycle-risk sizing**: peak-to-trough EPS revisions average ≈2× (+102% to −88%) over ≈12 months; stocks don't get rewarded for buying peak earnings as the second derivative rolls.
	- **DRAM price can't grow too high** -- When DRAM price hits an inflection point, it'd be more profitable for model serving to ditch KV-cache and recompute attentions.
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
	  | 2026-06-17 | Channel check (private source) | DRAM contract: Q3 2026 +30% QoQ, Q4 +20–30%; price to double from current levels by H1 2027 — "no suspense." HBM renewal prices jumped from \$15–16.6/GB to ≥\$53/GB; actual prices above \$53/GB, with NVIDIA receiving meaningful volume discounts. Key nuance: high HBM mix may not be unambiguously good — HBM price increases are structurally lagged vs. commodity DRAM, priced via long-term contracts driven by DDR (not the reverse), so commodity DRAM margins will exceed HBM margins for ≥5 years. | bullish |
	  | 2026-06-18 | WSJ + BofA (Jun 17–18) | Apple CEO Tim Cook confirmed iPhone 18 Pro price hike to offset **escalating memory costs** (WSJ exclusive, Jun 17). BofA raised Pro/Pro-Max ASP by +\$200 total (\$100 already in prior estimate + \$100 new raise; base model and Air unchanged). iPhone 18 Pro BOM: DRAM \$39→\$145 (+272%), NAND \$13→\$51 (+292%); memory+storage combined \$52→\$196 (+\$144, +277%) — the single largest per-unit BOM swing vs. prior gen. Apple total cost \$582→\$726; est. retail \$1,099→\$1,299. Source: TechInsights / iFixit / WSJ. See Appendix: iPhone 18 Pro BOM. | bullish |
  | 2026-06-23 | Industry sources (Korean press) | **SK Hynix delays HBM3E→HBM4 line conversion; pivots to commodity DRAM.** Key data points: (1) **Profitability reversal confirmed**: commodity DRAM OP margin now exceeds HBM by **>15 ppts**; Daishin Securities projects theoretical peak of **90% OP margin** for general-purpose DRAM within 2026. (2) HBM revenue already **>40% of total SK Hynix revenue** — HBM position is secure, no need to rush HBM4. (3) **Nvidia Rubin production forecasts trending down**, reducing urgency of HBM4 ramp. (4) SK Hynix Q1 DRAM ASP rose to **mid-60% range**. (5) **3-year DDR5 LTA signed with Microsoft** — locks in long-term commodity DRAM earnings visibility. (6) Goldman Sachs: maintaining >50% HBM3/HBM3E share through at least 2026 is sufficient. (7) Morgan Stanley: raised SK Hynix earnings 56–63%; projects **DRAM ASP +62% by 2026**; key driver is memory price cycle, not HBM share defense. (8) HBM share risk: SK Hynix at 57% (Q4 2025, Counterpoint); could drop to 50–60% if Samsung achieves HBM4 mass production in H2 2026. | bullish |
  | 2026-06-24 | BofA | **US chip demand raised to \$2.7T by 2030** (prior: \$2.3T); implies **28% CAGR 2025–2030**. Upgrade driven primarily by stronger demand for **memory chips** and **AI data-center hardware**. | bullish |
  | 2026-06-20 | Industry chat (private) | **Nanya / DDR4 long-tail revival.** History: in the 2008 downturn Samsung's pricing nearly wiped out the entire global memory industry — Hynix was sold to SK Group (bailed out by the Korean government) and Micron absorbed the remaining Japanese/Taiwanese makers. Taiwan's Formosa Plastics Group ran two memory companies, Nanya and Inotera; Inotera was sold to Micron, while Nanya survived but lacked the capital to develop DDR5 — effectively "waiting to die." (Aside: Formosa was an original TSMC shareholder at ~10% but sold out early.) The DDR4 market kept shrinking and the Big 3 signaled exit, yet industrial PCs and Cisco gear require long-lifecycle parts that **must** use DDR4 — leaving those OEMs scrambling, and Nanya surviving on exactly these long-tail products. **New twist (the signal):** with DRAM scarcity so acute, customers may now directly fund Nanya's DDR5 development — even a few wafers of marginal supply can pull prices down enough to recoup the investment. Nanya thus shifts from "waiting to die on D4" to a credible path forward to D5. Illustrates how tight the cycle is: pricing power is reaching even long-tail legacy nodes and the industry's weakest surviving supplier. | bullish |
  | 2026-06 | Jefferies (memory expert) | **3Q pricing +40–50% QoQ; 4Q +30–40% QoQ; 2027 +40–45% YoY; 2028 ASP risk from 15–20% supply growth + slowing demand. China not a threat in 2026/7 (tech gap) but NAND could catch up by 2028. LTAs now only with CSPs at 50% of capacity (could reach 70%) — less supply available for consumer electronics.** Bullish near-term; 2028 is the flagged inflection. | bullish |
  | 2026-06 | Citi Research | **DRAM ASP +200% YoY in 2026E; NAND ASP +186% YoY.** Front-loaded: blended DRAM QoQ peaks at +64% in 1Q26, NAND at +63% in 1Q26, then decelerates through year-end. Server DRAM leads all segments at +331% YoY. SSD leads NAND at +267% YoY. Graphic/Consumer DRAM is the laggard at +29% YoY — consumer end-market pricing power diverging sharply from AI/server. See Appendix: Citi DRAM & NAND ASP Projection. | bullish |
  | 2026-02-12 | WSJ / TrendForce | **~7× increase in DRAM and NAND flash contract prices in the past 12 months** (i.e., Feb 2025 → Feb 2026). Source: TrendForce tracking data. Consistent with Citi's +200%/+186% YoY ASP projections; confirms the pricing cycle is not a modeling assumption — it was already visible in contract data months before the Citi report. | bullish |
  | 2026-02-12 | WSJ | **CXMT entering PC OEM supply chains for Asia**: HP and other major PC makers in talks with supply-chain partners about using CXMT memory chips in products bound for Asia. First disclosed signal of CXMT qualifying into branded OEM products. Not hyperscale server DRAM — consumer/commercial PC DRAM is a different, lower-spec segment — but this is the adoption pathway: consumer PC → broader commercial → eventually data-center adjacencies. Confirms the Jefferies view that China is not a 2026/27 threat but could be meaningful by 2028+ in non-HBM segments. | bearish |
  | 2026-06 | Industry news / Korean press | **TSMC brings Winbond into AI-chip memory supply chain via next-gen WoW 3D stacking.** TSMC and Winbond will collaborate on Wafer-on-Wafer stacking, with Winbond supplying DRAM wafers and TSMC stacking them with logic wafers for AI chips. Read: this is less a normal supply deal than a TSMC supply-chain strategy — diversify away from exclusive dependence on Samsung/SK Hynix/Micron, cultivate a Taiwan-based memory ecosystem, and improve AI-chip supply stability. For Winbond, it is a possible entry point into AI server / HPC supply chains. Risk to thesis: not immediate HBM displacement, but longer-term value-capture and sourcing risk if TSMC can make on-package DRAM supply more foundry-controlled. | bearish |
  | 2026-02-12 | WSJ | **Micron US fab timeline and geopolitical context**: (1) New Idaho facilities: first opens **mid-2027**. (2) New York (Clay, near Syracuse) plant: production starts **2030**. (3) Manassas, VA expansion: new supply line already in production. (4) Total US investment pledge: **\$200B**. (5) Micron lobbying for stronger restrictions on US-China semiconductor partnerships; bipartisan legislation introduced. (6) Historical precedent: Apple was working with YMTC in 2022 to qualify it as a NAND supplier — abandoned after lawmaker opposition. The YMTC episode illustrates how quickly a qualified supply relationship can be severed by policy action, raising the ceiling on how aggressively the US can intervene in Chinese memory supply chains. | bullish |
	- ---
- ## Appendix — SSD vs HDD Market Share (Bits vs Dollars)
	- **Source**: industry estimates compiled via web search (IDC, Gartner, market-research firms); figures vary by source/definition (total vs enterprise vs data-center), treat as approximate. See [[2026-05-05-micron-6600-ion-245tb-ssd]].
	  
	  | Metric (≈2026E) | HDD | SSD |
	  |---|---:|---:|
	  | Capacity shipped — exabytes ("bits") | ≈3,200 EB (**≈68%**) | ≈1,400 EB (**≈32%**) |
	  | Enterprise / data-center revenue (\$) | ≈\$53B | ≈\$47–49B (**≈ parity**) |
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
	- ---
- ## Appendix: Peer Capex Comparison (2016–2026 Guidance)
	- Big 3 memory capex history; tracks the supply-discipline / capacity-add signal central to the cycle (see Key Value Drivers). Note the synchronized **2023 trough** (all three cut) and the **2024–2026 AI-driven re-acceleration**.
	  
	  | Year | Micron Capex (USD) | Micron YoY | SK Hynix Capex (KRW) | SK Hynix YoY | Samsung DS Capex (KRW)* | Samsung DS YoY |
	  |---|---:|---:|---:|---:|---:|---:|
	  | 2026 (Guid.) | >$25.00B | +57.6% | ~₩35.00T | +27.2% | ~₩54.00T | +4.9% |
	  | 2025 | $15.86B | +89.0% | ₩27.52T | +72.5% | ₩51.46T | +7.4% |
	  | 2024 | $8.39B | +9.2% | ₩15.95T | +91.5% | ₩47.92T | +7.9% |
	  | 2023 | $7.68B | −36.4% | ₩8.33T | −56.2% | ₩44.40T | −7.3% |
	  | 2022 | $12.07B | +20.3% | ₩19.01T | +52.2% | ₩47.90T | +10.0% |
	  | 2021 | $10.03B | +26.2% | ₩12.49T | +26.3% | ₩43.56T | +32.4% |
	  | 2020 | $7.95B | −12.7% | ₩9.89T | −23.3% | ₩32.89T | +45.5% |
	  | 2019 | $9.11B | +12.2% | ₩12.89T | −24.4% | ₩22.60T | −23.7% |
	  | 2018 | $8.12B | +59.8% | ₩17.04T | +65.4% | ₩29.60T | −13.9% |
	  | 2017 | $5.08B | −3.8% | ₩10.30T | +63.8% | ₩34.40T | +160.6% |
	  | 2016 | $5.28B | — | ₩6.29T | — | ₩13.20T | — |
	- **\*Note**: Historically, ~**80–85%** of Samsung's DS-division capex line is directed exclusively toward **Memory (DRAM/NAND)** infrastructure and technology transitions.
	- ---
- ## Appendix: Micron Segment Breakdown (technology & business unit)
	- **Source**: Micron FQ2-26 earnings deck (reported Mar 18, 2026) and FQ1-26 earnings deck (reported Dec 17, 2025). Total revenue: **FQ2-26 \$23.86B** (+75% Q/Q, +196% Y/Y), FQ1-26 \$13.64B, FQ4-25 \$11.31B, FQ2-25 \$8.05B.
	- **Business-unit context** (Micron reorganized in **2025 around customer types rather than product types**):
		- **CMBU — Cloud Memory BU**: customers = large hyperscalers (Microsoft, Amazon, Google) + AI-infra providers; products = **HBM, AI-accelerator memory, high-capacity server DRAM, LPDRAM for AI servers**. Split out because AI memory is Micron's fastest-growing, highest-margin business. **⚑ HBM revenue is reported inside CMBU.**
		- **CDBU — Core Data Center BU**: customers = enterprise data centers, OEM server vendors, smaller cloud providers; products = server DRAM, enterprise SSDs, storage, traditional DC memory. Split out for its different buying patterns, product requirements, and sales cycles vs hyperscalers.
		- **MCBU — Mobile and Client BU**; **AEBU — Automotive and Embedded BU** (record AEBU revenue, auto + industrial > $2B in the quarter).
	- ### DRAM
	  | Quarter | Revenue | % of total rev | Rev Q/Q | Rev Y/Y | Bit shipments Q/Q | ASP Q/Q |
	  |---|---:|---:|---:|---:|---|---|
	  | FQ2-26 | $18.8B | 79% | +74% | +207% | +5% | **+65%** |
	  | FQ1-26 | $10.8B | 79% | +20% | +69% | ~+1% | **~+20%** |
	  | FQ4-25 | $9.0B | 79% | +20% | +69% | — | — |
	- ### NAND
	  | Quarter | Revenue | % of total rev | Rev Q/Q | Rev Y/Y | Bit shipments Q/Q | ASP Q/Q |
	  |---|---:|---:|---:|---:|---|---|
	  | FQ2-26 | $5.0B | 21% | +82% | +169% | +2.5% | **+77.5%** |
	  | FQ1-26 | $2.7B | 20% | +22% | +22% | +5–7.5% | **+15%** |
	  | FQ4-25 | $2.3B | 20% | +22% | +22% | — | — |
		- The up-cycle is overwhelmingly **price-driven**: bit shipments up only ~2.5–5% Q/Q while ASPs jump +65% (DRAM) / +77.5% (NAND). (Qualitative ASP/bit bands from the deck mapped to midpoints: low-≈X2.5%, mid-≈X5%, high-≈X7.5%.)
	- ### Business-unit % of total revenue
	  | Quarter | CMBU | CDBU | MCBU | AEBU |
	  |---|---:|---:|---:|---:|
	  | FQ2-26 | 32.5% | 23.8% | 32.3% | 11.4% |
	  | FQ1-26 | 38.7% | 17.4% | 31.2% | 12.6% |
	  | FQ4-25 | 40.1% | 13.9% | 33.2% | 12.7% |
	  | FQ2-25 | 36.6% | 22.7% | 27.8% | 12.8% |
	- ### Business-unit gross margin
	  | Quarter | CMBU | CDBU | MCBU | AEBU |
	  |---|---:|---:|---:|---:|
	  | FQ2-26 | 74% | 74% | 79% | 68% |
	  | FQ1-26 | 66% | 51% | 54% | 45% |
	  | FQ4-25 | 59% | 41% | 36% | 31% |
	  | FQ2-25 | 55% | 47% | 15% | 21% |
	- ### Business-unit revenue Q/Q growth
	  | Quarter | CMBU | CDBU | MCBU | AEBU |
	  |---|---:|---:|---:|---:|
	  | FQ2-26 | +47% | +139% | +81% | +57% |
	  | FQ1-26 | +16% | +51% | +13% | +20% |
	  | FQ4-25 | — | — | — | — |
		- **Read**: every BU's gross margin re-rated hard in two quarters (e.g. MCBU 15% → 79%, AEBU 21% → 68%) — the pricing-driven super-cycle lifting all segments, not just the AI-centric CMBU/CDBU. CMBU + CDBU (the data-center-facing units, incl. all HBM) = **~56% of FQ2-26 revenue**.
		- **Note on labels**: FQ2-26 is Micron's fiscal Q2 2026 (reported Mar 18, 2026). Technology-level Q/Q bit/ASP detail and per-BU Q/Q are only available for the latest quarter pair in the deck; earlier-quarter Q/Q would require quarters not shown. FQ4-25 Q/Q data not available (requires FQ3-25 figures from the FQ4 2025 earnings deck).
	- ---
- ## Appendix: Analyst Estimates — Micron ($MU)
	- **Source**: Stifel (via @firstadopter / Tae Kim, X post 2026-06-18)
	- **Headline**: MU trading at **6.6× Stifel's 2027E EPS** of \$159 as of 2026-06-18. Street consensus for FQ3-26 EPS is ~\$19; Stifel at \$26 — **37% above consensus**.
	- ### Stifel EPS (net) estimates — Micron calendar year
	  | Quarter | 2025A | 2026E | 2027E |
	  |---|---:|---:|---:|
	  | Q1 | \$1.79 | \$4.78A | \$35.50 |
	  | Q2 | \$1.56 | \$12.20A | \$39.00 |
	  | Q3 | \$1.94 | \$26.00 | \$41.05 |
	  | Q4 | \$3.03 | \$32.02 | \$43.45 |
	  | **Full Year** | **\$8.32A** | **\$75.00** | **\$159.00** |
	  | **P/E** | NM | 13.9× | **6.6×** |
	- **Read**: EPS ramps from \$8.32 in 2025 to \$75 in 2026E (+802% YoY) and \$159 in 2027E (+112% YoY). At 6.6× 2027E, MU is priced as a deep-value cyclical, not a structural compounder — the market is heavily discounting whether peak earnings are durable.
	- ---
- ## Appendix: iPhone 18 Pro BOM — Memory Price Pass-Through
	- **Source**: TechInsights (component cost estimates), iFixit (hardware teardown), WSJ (Andrew Mollica, Jun 2026); BofA analyst note (Jun 17–18, 2026)
	- **Headline**: Memory and storage are the sole drivers of the iPhone 17→18 Pro BOM increase, rising a combined +\$144 per unit (+277%). Apple CEO Tim Cook confirmed the pricing lever in a WSJ exclusive (Jun 17), and BofA raised its iPhone 18 Pro/Pro-Max ASP estimate by an incremental +\$100 (on top of +\$100 already embedded), implying a ~+\$200 total retail price increase vs. iPhone 17 Pro.
	- ### Bill of Materials — iPhone 17 Pro vs. iPhone 18 Pro (base model)
	  | Component | iPhone 17 Pro cost | iPhone 18 Pro est. cost | Change |
	  |---|---:|---:|---:|
	  | Rear camera array | \$125 | ~\$125 | — |
	  | Processor (A19 Pro) | \$93 | ~\$93 | — |
	  | Display | \$42 | ~\$42 | — |
	  | Other components* | \$229 | ~\$229 | — |
	  | **Memory (12 GB DRAM)** | **\$39** | **\$145** | **+\$106 (+272%)** |
	  | **Storage (256 GB NAND)** | **\$13** | **\$51** | **+\$38 (+292%)** |
	  | **Apple's total cost** | **\$582** | **\$726** | **+\$144 (+25%)** |
	  | **Retail price** | **\$1,099** | **\$1,299 (est.)** | **+\$200 (+18%)** |
	- *Other components includes main enclosure, 5G modem, battery, and conversion cost.
	- **Gross margin read**: Apple's cost rises +25% but retail rises only +18% → Apple absorbs ~\$56 of the \$144 BOM increase; gross margin compresses modestly. Memory suppliers capture the remainder via ASP, confirming pricing power flows through the supply chain to OEMs.
	- **BofA pricing revision summary**:
		- Pro / Pro-Max: prior estimate +\$100 → revised to +\$200 total
		- Base model: no change
		- Air: already reflected +\$100; no further change
		- Rationale: Cook's public confirmation of the pricing lever + continued memory price escalation
- ---
- ## Appendix: Citi DRAM & NAND ASP Projection by Application
	- **Source**: Citi Research, © 2026 Citigroup Inc. (Figures 3 & 4). All figures are QoQ % change in ASP by quarter; YoY column reflects full-year 2025A or 2026E change.

	- ### DRAM ASP QoQ % by Application
	  | Application | 2025 1Q | 2025 2Q | 2025 3Q | 2025 4Q | 2025 YoY | 2026 1Q | 2026 2Q | 2026 3Q | 2026 4Q | 2026 YoY |
	  |---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
	  | Server | −8% | +8% | +15% | +71% | +43% | +88% | +43% | +16% | +7% | +331% |
	  | Mobile | −10% | −2% | +2% | +50% | 0% | +67% | +45% | +12% | +7% | +225% |
	  | PC | −15% | +3% | +4% | +45% | +1% | +63% | +35% | +10% | +6% | +194% |
	  | Graphic/Consumer | +5% | +4% | +2% | 0% | +50% | +5% | +8% | +10% | +30% | +29% |
	  | **DRAM ASP blended** | **−7%** | **+3%** | **+7%** | **+47%** | **+28%** | **+64%** | **+37%** | **+13%** | **+11%** | **+200%** |

	- ### NAND ASP QoQ % by Application
	  | Application | 2025 1Q | 2025 2Q | 2025 3Q | 2025 4Q | 2025 YoY | 2026 1Q | 2026 2Q | 2026 3Q | 2026 4Q | 2026 YoY |
	  |---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
	  | SSD | −7% | +2% | +5% | +31% | +21% | +70% | +63% | +25% | +10% | +267% |
	  | Mobile | −13% | +3% | 0% | +11% | −16% | +55% | +25% | +10% | +3% | +113% |
	  | USB & Others | −14% | +8% | +2% | +20% | −6% | +63% | +40% | +12% | +5% | +169% |
	  | **NAND ASP blended** | **−11%** | **+3%** | **+3%** | **+21%** | **+3%** | **+63%** | **+45%** | **+17%** | **+6%** | **+186%** |

	- ### Key Reads
		- **2026 DRAM YoY by segment**: Server (+331%) >> Mobile (+225%) >> PC (+194%) >> Graphic/Consumer (+29%) — the AI/server premium vs. consumer is enormous; Graphic/Consumer barely moved while server nearly quadruples.
		- **Front-loaded cycle**: sharpest QoQ gains are in 1Q–2Q 2026 (DRAM blended +64%/+37%; NAND blended +63%/+45%), decelerating to mid-single-digit QoQ by 4Q 2026 — consistent with the channel-check view that pricing peaks H1 2026 and moderates into H2.
		- **NAND 2025 YoY was near-flat** (blended +3%) despite strong 4Q; SSD led at +21% while Mobile and USB/Others declined — the AI/datacenter SSD bid arrived later than DRAM and is now accelerating sharply into 2026 (+267% SSD YoY).
		- **Cross-check with channel checks** (2026-06-17 anecdote): "DRAM contract Q3 +30% QoQ, Q4 +20–30%." Citi models 2026 3Q at +13% and 4Q at +11% — more conservative on the back half; both agree the cycle continues decelerating into year-end from a very high H1 base.

- ## Appendix: Morgan Stanley Hyperscaler CapEx Estimates (2024–2027)

	- **Source**: Morgan Stanley Research (Company data + MS estimates). Via Altimeter. Reference: *GOOGL, AMZN, and META Surprises and Learnings*, 30 Apr 2026. Headline: MS now sees hyperscaler capex approaching \$800B/\$1.1T in '26/'27 vs \$765B/\$950B previously.

	- ### Per-Company CapEx (\$B)

	  | Company | 2024A | 2025A | 2026 Prior | 2026 Current | 2027 Prior | 2027 Current | '24–'27 CAGR |
	  |---|---:|---:|---:|---:|---:|---:|---:|
	  | AMZN | \$83 | \$132 | \$211 | \$212 | \$249 | \$268 | 48% |
	  | GOOGL | \$53 | \$91 | \$185 | \$190 | \$250 | \$299 | 69% |
	  | META | \$39 | \$72 | \$135 | \$135 | \$165 | \$165 | 59% |
	  | MSFT | \$76 | \$118 | \$156 | \$190 | \$178 | \$276 | 54% |
	  | ORCL | ~\$10 | \$35 | \$78 | \$78 | \$108 | \$108 | 116% |
	  | **Total** | **\$261** | **\$449** | **\$765** | **\$805** | **\$951** | **\$1,116** | **62%** |

	- ### Revision Delta (Current vs. Prior)

	  | Year | Prior | Current | Delta | Delta % |
	  |---|---:|---:|---:|---:|
	  | 2026 | \$765B | \$805B | +\$40B | +5% |
	  | 2027 | \$951B | \$1,116B | +\$165B | +17% |

	- ### Key Reads
		- **2027 revision is the signal**: the +\$165B upward revision to 2027 is 4× larger than the 2026 revision — MS is increasing its conviction in a sustained, not just front-loaded, capex cycle.
		- **MSFT was the key 2027 mover**: revised from \$178B to \$276B (+\$98B), the largest single-company upward revision — notable given Microsoft paused some datacenter leases in early 2025, suggesting that pause was temporary and capacity commitment has returned with force.
		- **GOOGL is the fastest-growing of the large hyperscalers** on a dollar basis (2024→2027: \$53B→\$299B, +\$246B); the 69% CAGR implies Google is structurally closing the infrastructure gap with AWS.
		- **ORCL CAGR of 116%** reflects a low 2024 base (\~\$10B) ramping aggressively into AI cloud; Oracle's announced datacenter build commitments have been the most surprising upside datapoint of 2025–26.
		- **META is the only company with unchanged estimates**: both 2026 and 2027 held at \$135B/\$165B — either MS has high confidence in META's guidance or META management has given unusually precise forward visibility.
		- **\$1.1T in 2027 is a new order of magnitude**: for context, total S&P 500 capex in 2019 was \~\$800B; five hyperscalers alone are projected to exceed that by 2027. This is the macro demand anchor for AI infrastructure supply chains including memory, networking, power, and cooling.

- ## Appendix: TechInsights DRAM & NAND Price Change vs. Q1 2023

	- **Source**: TechInsights (via WSJ, Feb 2026). Average price per gigabyte, indexed to Q1 2023 = 0%. Data from 3Q 2026 onwards are estimates.

	- | Period | DRAM (% chg from Q1 2023) | NAND (% chg from Q1 2023) | Status |
	  |---|---:|---:|---|
	  | Q1 2023 | 0% | 0% | Actual (baseline) |
	  | Q4 2023 | ~0% | ~0% | Actual |
	  | Q2 2024 | ~15% | ~10% | Actual |
	  | Q4 2024 | ~50% | ~25% | Actual |
	  | Q2 2025 | ~55% | ~45% | Actual |
	  | Q4 2025 | ~65% | ~55% | Actual |
	  | Q1 2026 | ~150% | ~75% | Actual |
	  | Q2 2026 | ~575% | ~375% | Actual |
	  | Q3 2026 | ~640% | ~440% | **Estimate** |
	  | Q4 2026 | ~700% | ~490% | **Estimate** |
	  | Q1 2027 | ~750% | ~510% | **Estimate** |
	  | Q2 2027 | ~790% | ~500% | **Estimate** |
	  | Q4 2027 | ~850% | ~415% | **Estimate** |

	- ### Key Reads
		- **The Q1–Q2 2026 inflection is the visual story**: both DRAM and NAND prices were essentially flat from Q1 2023 through end of 2025 (+50–65% over nearly 3 years), then exploded in a single two-quarter window. The chart makes clear this is not a gradual cycle — it is a step-change.
		- **DRAM dramatically outpaces NAND**: by Q2 2026 DRAM is +575% vs. NAND +375% from the same baseline. The divergence reflects AI/server DRAM demand being structurally tighter than NAND demand, consistent with HBM sold-out status and LTA lock-in dynamics.
		- **NAND peaks and rolls in 2027E**: TechInsights estimates NAND prices peak around Q1 2027 (~+510%) then decline toward ~+415% by end of 2027 — a meaningful reversal. This is consistent with NAND supply responding faster than DRAM (more fab-convertible capacity; China NAND ramp) and with the Jefferies expert flagging 2028 as the NAND risk inflection.
		- **DRAM keeps rising through all of 2027E**: no peak visible in the DRAM estimate curve — it continues climbing to ~+850% by end of 2027. This implies TechInsights does not see a DRAM supply response materializing within the 2027 window, consistent with Micron's US fab timelines (Idaho mid-2027, NY 2030) and Samsung P5 (2028 completion, shipments ~2029).
		- **Cross-check with WSJ/TrendForce**: the "~7× increase in 12 months" cited in the Feb 2026 WSJ article corresponds to the near-vertical DRAM line between ~Q1 2025 (~+50%) and ~Q1 2026 (~+580%) — a ~530-percentage-point rise or roughly 7× the Q1 2023 absolute price level. The two data sources align.
