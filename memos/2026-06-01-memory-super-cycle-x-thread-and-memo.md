- tags:: [[DRAM]], [[HBM]], [[NAND]], [[super-cycle]], [[AI]], [[$000660.KS]], [[$005930.KS]], [[$MU]], [[$NVDA]], [[CoWoS]], [[$TSM]], [[X-thread]]
  file-created-at:: 2026-06-01

- ## X Post (paste directly — single post, X Premium)

	- ---
	  Memory is in a Super Cycle — not a normal inventory correction. Here's why this time is structurally different.

	  ——

	  The demand driver has changed permanently. Past cycles tracked PC/smartphone replacement. Now the governing equation is:

	  token throughput = HBM size × HBM bandwidth

	  Memory directly sets the AI output ceiling — not compute. If NVIDIA wants 2× token throughput per GPU generation, HBM must double. This is a physical constraint baked into the roadmap, not a preference.

	  ——

	  Per-GPU HBM per generation:
	  • H100 (2022): 80 GB
	  • H200 (2023): 141 GB
	  • B200 (2024): 192 GB
	  • Rubin Ultra (2027): 1 TB

	  12.5× more HBM per GPU in 5 years. In the NVL72 system BOM, memory's share of total cost jumped from 9.4% (GB300) to 25.7% (VR200) in a single generation — a 4.35× increase in just one transition.

	  ——

	  The multiplier effect makes the demand math extreme.

	  HBM per accelerator is growing ~25× from 2022 to 2028 (80 GB → ~2 TB). Data center system scale is also growing ~25× in accelerator count. That's 25 × 25 = 625× total memory demand expansion. (Michael Dell, BofA conference, Apr 2026)

	  ——

	  The clearest proof this isn't cyclical: in 2025, smartphone shipments fell 13% and PC shipments fell 10%. In any prior memory cycle, that demand destruction would have caused price collapses.

	  Instead, memory prices more than doubled. DRAM contract prices: +100% QoQ in Q1 2026, then +30% more in Q2. AI servers simply outbid consumer electronics for every available wafer.

	  ——

	  It's not just HBM. All three premium memory categories are simultaneously maxed out — something no prior cycle produced:

	  • HBM: sold out through 2026–2027 for SK Hynix and Samsung
	  • DRAM: AI inference KV cache must stay resident in DRAM throughout each session, creating a structural new demand class
	  • NAND: AI agents running long chain-of-thought workflows must dump state to disk (落盤) — NAND is now an active inference participant, not passive storage

	  ——

	  Supply has two independent ceilings, not one.

	  HBM must be physically bonded to the GPU die via TSMC's CoWoS packaging before it can ship. Even if every memory fab added wafers today, CoWoS throughput caps delivery — 6–9 month lead time minimum. TSMC is spending billions developing CoPoS (next-gen panel-level packaging) specifically to relieve this constraint for the 2028 GPU generation.

	  ——

	  The oligopoly has killed the price war mechanism.

	  1998: ~15 DRAM suppliers. Today: 3. SK Hynix reported 72% operating margin in Q1 — more profit in one quarter than in the full prior year. Manufacturers are prioritizing HBM technology upgrades (HBM3 → HBM3E → HBM4 → HBM4E), not flooding the market with commodity capacity. Technology-upgrade capex takes 18–24 months to translate into supply, and it arrives at structurally higher ASPs.

	  ——

	  Contracts have been rewritten entirely in suppliers' favor.

	  Domestically: buyers can only lock VOLUME in long-term agreements — prices float upward with the market (鎖量不鎖價). Overseas: buyers must either pay large upfront deposits or directly finance the supplier's capital equipment purchases. SK Hynix has publicly projected the imbalance won't ease until at least 2028.

	  ——

	  The data is corroborating in real time.

	  South Korea memory exports are annualizing ~$209B in 2026 vs $94.6B for full-year 2025 — both price and volume rising simultaneously. Big 4 hyperscaler capex for 2026 alone: $695–725B (Microsoft $190B, Amazon ~$200B, Google $180–190B, Meta $125–145B), with Google already signaling another step-up in 2027. Goldman Sachs revised SK Hynix FY27 operating profit up +21% — projecting 82.8% DRAM operating margins.

	  Not cyclical. Structural.
	- ---

- ## Full Memo: The Memory Super Cycle — Nine Structural Arguments

- ### Thesis
	- This memory cycle is not a normal inventory correction. It is a structural Super Cycle driven by a permanent shift in the identity of the largest memory buyer — from consumer electronics OEMs to AI infrastructure operators. The arguments below are independent but mutually reinforcing.

- ### Argument 1: HBM Is Now Endogenous to the GPU Roadmap
	- In the CPU era, DRAM was peripheral. CPUs hid memory latency through superscalar execution, caches, and warp switching. Doubling DDR speed improved system performance by less than 20%. DDR3 to DDR5 took 15 years. Average PC DRAM capacity grew only 3× over a decade.
	- In the AI inference era, the system-level KPI is token throughput — how many tokens can be produced cheaply and at speed. The binding equation is:
		- `token throughput = HBM size × HBM bandwidth`
	- Each concurrent inference request holds a live KV cache in HBM. For an 80-layer model, generating one token requires reading the KV cache 80 times from HBM. HBM is no longer auxiliary. It directly sets the ceiling on what a data center can produce. If NVIDIA wants 2× token throughput per GPU generation, HBM size × bandwidth must also double. This is not a preference — it is a physical constraint embedded in the GPU roadmap.

- ### Argument 2: Per-GPU HBM Content Is Escalating 12.5× in Five Years

	| GPU | Year | HBM Capacity | Normalized HBM Cost |
	|---|---|---|---|
	| H100 | 2022 | 80 GB | ~$800–1,200 |
	| H200 | 2023 | 141 GB | ~$1,410–2,115 |
	| B200 | 2024 | 192 GB | ~$1,920–2,880 |
	| R100 (Rubin) | 2026 | 288 GB | ~$2,880–4,320 |
	| Rubin Ultra | 2027 | 1 TB HBM4e | ~$10,000–15,000 |
	| Feynman | 2028 | >1 TB HBM5 | TBA |

	- Additionally, the HBM performance ratio (compute / HBM bandwidth) is escalating with each generation: H100=591, B200=1,125, R200=2,692. Compute is being added faster than HBM bandwidth, which means each new GPU generation is increasingly memory-bandwidth-bound — keeping HBM perpetually in the critical path regardless of whether compute improves.
	- In the NVL72 system BOM, memory's share of total cost jumped from **9.4% (GB300) to 25.7% (VR200)** in a single generation — a 4.35× increase in memory cost share. (Source: Morgan Stanley estimates)

- ### Argument 3: The 625× Total Demand Framework
	- HBM per accelerator is growing ~25× from 2022 to 2028 (80 GB → ~2 TB). Simultaneously, data center system scale in terms of accelerator deployment is expanding ~25×. The multiplicative framework: **25 × 25 = 625×** total memory demand expansion.
	- OpenAI's available compute trajectory independently corroborates the system-scale claim: 0.2 GW (2023) → 0.6 GW (2024) → ~1.9 GW (2025) → 30 GW (2030 target). That is a 150× increase in 7 years. Supply cannot react at this velocity — memory fab expansions take years, and the 2023 industry downturn created an underinvestment hole that is still being worked through.

- ### Argument 4: AI Demand Outbid and Replaced Consumer Electronics
	- In 2025: global smartphone shipments fell **13%**. PC shipments fell **10%**. Both core consumer electronics categories contracted sharply. In any prior memory cycle, this demand destruction would have caused price collapses.
	- Instead, DRAM prices more than doubled. Samsung raised Q2 2026 contract prices ~30% QoQ following a ~100% QoQ increase in Q1. Price path: KRW 10,000 (start 2025) → KRW 20,000 (Q1 2026) → KRW 26,000 (Q2 2026).
	- The mechanism: the Big 3 memory makers concentrated their wafer capacity on HBM production, tightening conventional DRAM supply as a direct byproduct. AI servers occupy the highest tier of memory procurement and have been able to outbid consumer device OEMs at every price point. The consumer electronics demand signal has been effectively severed from the memory pricing mechanism.

- ### Argument 5: Triple Product Demand — DRAM, HBM, and NAND Simultaneously
	- Prior memory upturns typically had a single product category driving the cycle. This one has three concurrent ceilings:
	- **HBM**: Entirely sold out through 2026 and mostly through 2027 for SK Hynix and Samsung. UBS demand model: 17.5 bn GB (2025) → 32.9 bn GB (2026E, +88% YoY) → 58.0 bn GB (2027E, +76% YoY). Google alone: 1.8 bn → 6.1 bn → 15.7 bn GB over two years, driven by custom TPU infrastructure buildout.
	- **DRAM**: The shift from AI training (2023–2024) to AI inference (surging 2025 onward) requires heavy KV cache retention during inference. KV caches must remain resident in DRAM throughout an inference session, creating a structural new demand class for server DRAM that scales with inference volume.
	- **NAND Flash**: AI agents running extended chain-of-thought workflows must periodically dump state to disk (落盤) to enable recovery and restoration. This is a new and growing use case that turns NAND from passive storage into an active participant in the AI inference loop.

- ### Argument 6: Oligopoly Structure Eliminates Price Wars
	- 1998: approximately 15 global DRAM suppliers. Today: **3** (SK Hynix, Samsung, Micron). The consolidation has permanently altered the competitive incentive structure. In prior cycles, manufacturers engaged in price wars and capacity overexpansion to steal market share, causing catastrophic price crashes. With 3 players, each rational actor gains more from margin maximization than from share warfare.
	- The result is visible in the financials. SK Hynix reported a **72% operating margin in Q1** — more profit in one quarter than in the full prior year. Rather than building commodity fabs, all three manufacturers are investing in HBM technology progression (HBM3 → HBM3E → HBM4 → HBM4E). Technology upgrade capex does not translate to near-term commodity supply — it takes 18–24+ months and produces new products at structurally higher ASPs.
	- Memory capex is growing (+26% in 2025, +31% in 2026 for memory companies) while IDM capex is shrinking (-25% in 2025). This divergence confirms that memory investment is technology-driven and AI-linked, not a capacity race.

- ### Argument 7: CoWoS Creates a Dual Supply Bottleneck
	- HBM cannot reach the end customer without being physically bonded to a GPU die using TSMC's CoWoS (Chip-on-Wafer-on-Substrate) advanced packaging. This creates a **second independent supply ceiling** on top of memory fab capacity. Both bottlenecks must expand before HBM supply can grow.
	- Historical CoWoS capacity expansion lead time: **12–15 months** (recently optimized to 6–9 months, but still multiple quarters). Even if memory fabs added wafers today, CoWoS limits how fast finished HBM can ship.
	- The constraint is so significant that TSMC is developing a next-generation successor — CoPoS (panel-level) targeting mass production in 2028 for the Feynman GPU platform — while Intel is independently investing in EMIB-T as a competing solution. The fact that two major infrastructure companies are spending billions to resolve a packaging bottleneck is itself evidence of how binding it is.

- ### Argument 8: Contracts Have Been Rewritten in Suppliers' Favor
	- In prior cycles, buyers could extract price concessions during inventory gluts. That leverage has been eliminated. The contractual architecture of memory procurement has been redesigned:
	- **Domestic LTAs (鎖量不鎖價)**: Buyers signing long-term agreements can secure guaranteed allocation volume only. The actual purchase price floats with market rates. Suppliers retain full price upside with no ceiling.
	- **Overseas capital binding**: Buyers must either pay substantial upfront deposits to secure supply or directly finance the memory manufacturer's capital expenditures — purchasing equipment on the manufacturer's behalf. Buyer capital is subordinated to supplier risk.
	- SK Hynix has publicly projected that the supply-demand imbalance will not ease until **at least 2028**. This is not a cyclical statement. It is a structural forecast about the duration of pricing power.

- ### Argument 9: The Data Is Corroborating, Not Just Projecting
	- **South Korea memory exports**: Jan–Apr 2026 = $69.5B, annualizing to ~$209B vs $94.6B full-year 2025. Both volume and value growing simultaneously — the strongest possible revenue environment. Taiwan's value-per-ton: $108K in 2026 vs $80K in 2025, reflecting HBM's premium as it flows through CoWoS packaging before entering hyperscaler servers.
	- **Distributor data**: Supreme Electronics, Samsung's Taiwan memory distributor serving major AI server ODMs (Foxconn, Quanta, Wistron), reported +191% YoY in March 2026 and +137% for Q1 2026 — not a price-only effect, volume is also surging. This closes the loop from hyperscaler capex commitments to actual chip pull-through.
	- **Hyperscaler capex**: Big 4 US tech 2026 combined guidance: **$695–725B** (Microsoft $190B, Amazon ~$200B, Google $180–190B, Meta $125–145B). Google has already flagged another significant step-up in 2027.
	- **Sell-side confirmation**: Goldman Sachs revised SK Hynix FY27 operating profit up **+21%** and FY28 up **+24%** above prior estimates. FY27 DRAM operating margin forecast: **82.8%** — historically extreme. This is not a one-quarter beat. It is a structural multi-year upgrade.

- ### What Doesn't Change This View
	- **CXMT**: China's CXMT is progressing faster than expected — HBM3E 12-high targeted for 2027, compressing the Korea–China gap to ≤3 years. But two hard constraints cap the threat: (1) HBM patents are owned by Korean companies, limiting CXMT to domestic Chinese customers only; (2) US equipment export controls (AMAT, KLA banned) prevent 10× scale-up. CXMT is a medium-term pricing risk on the commodity tier only; leading-edge HBM4/HBM4E remains a Korean moat.
	- **SRAM alternatives (Cerebras, Groq)**: SRAM has a structural and permanent cost disadvantage (6-transistor cell vs. 1T1C DRAM). Running a 70B model: Groq requires ~576 cards at >$1.1M; H100 requires 2 cards at <$100K. SRAM is a viable premium niche (~10% of inference workload) for real-time low-batch decode — it is not a HBM substitute for bulk inference.

- ### Summary

	| Dimension | Old cycle | This cycle |
	|---|---|---|
	| Demand driver | PC / smartphone replacement cycles | AI inference — structural and exponential |
	| Memory's role | Peripheral, <20% system leverage | Central — directly sets token throughput ceiling |
	| Per-unit memory intensity | Slow / stable | 12.5× per GPU in 5 years; BOM share 9.4% → 25.7% |
	| Demand breadth | Single product bottleneck | HBM + DRAM + NAND simultaneously |
	| Consumer demand crossover | Prices correlated with consumer | Consumer -13% smartphones, prices still doubled |
	| Supply structure | 15 competitors, price wars | 3 oligopolists, margin focus, technology upgrades |
	| Physical supply ceiling | Fab capacity only | Fab + CoWoS packaging: two independent bottlenecks |
	| Contract structure | Buyers reprice in gluts | Suppliers lock volume / float price; buyers fund capex |
	| Duration guidance | 1–2 year inventory corrections | SK Hynix: imbalance through at least 2028 |
