- tags:: [[DRAM]], [[HBM]], [[NAND]], [[super-cycle]], [[AI]], [[$000660.KS]], [[$005930.KS]], [[$MU]], [[$NVDA]], [[CoWoS]], [[$TSM]]
  file-created-at:: 2026-06-01

- ## Why This Memory Cycle Is a Super Cycle — Five Core Arguments
	- **Source**: Interview transcript (user-provided), summarized `2026-06-01`
	- **Thesis**: This memory cycle differs fundamentally from all prior historical cycles and should be classified as a Super Cycle (or Mega Cycle), not a normal inventory correction

- ## Argument 1: Structural Shift in Demand (AI-Driven vs. Consumer Electronics)
	- **Context**: Past cycles were traditional inventory correction periods driven by the replacement cycles of PCs and smartphones. This cycle is driven by structural, exponential demand from AI training and inference.
	- **Key data points**:
		- HBM per Nvidia GPU generation:

			| GPU | HBM Capacity |
			|---|---:|
			| H20 | 96 GB |
			| H200 | 141 GB |
			| B200 | 192 GB |
			| B300 | 288 GB |
		- In `2025` alone, Nvidia shipped **millions of GPUs**; Nvidia's memory consumption now rivals the historical aggregate demand of the entire PC or smartphone industries
		- Global smartphone shipments dropped `13%` in `2025`; PC shipments fell `10%` in `2025`
		- Despite the consumer collapse, memory prices **more than doubled** — AI servers successfully outbid and hollowed out consumer electronics supply
	- **Implication**: This is not a cyclical rebound from consumer demand. The demand curve has been reset by a structurally different and exponentially growing buyer class.

- ## Argument 2: A Triple Whammy of Coinciding Product Demand
	- **Context**: Prior upturns usually featured a single product bottleneck. This cycle features a concurrent demand explosion across three separate premium memory categories simultaneously: **DRAM**, **HBM**, and **NAND Flash**.
	- **Key data points**:
		- **HBM**: Entirely sold out through `2026` and mostly through `2027` for top manufacturers including [[$000660.KS]] and [[$005930.KS]]
		- **DRAM**: The shift from AI training (dominant in `2023–2024`) to AI inference (surging from `2025` onward) requires heavy **KV Cache retention**, vastly amplifying the necessity for large DRAM capacity
		- **NAND Flash**: Evolved from simple passive data storage to an active participant in the AI inference loop — AI Agents running long chain-of-thought workflows must constantly "dump data to disk" (落盤) to allow state restoration; this turns NAND into an inference-critical component
	- **Implication**: All three memory categories are under simultaneous pressure from the same underlying driver (AI inference at scale), making demand breadth unprecedented versus any prior cycle.

- ## Argument 3: Supply-Side Capital Discipline Over Market Share Wars
	- **Context**: In previous downturns, memory manufacturers engaged in aggressive price wars and overexpanded production to steal market share, causing catastrophic price crashes. Today, consolidation has created a disciplined oligopoly focused on profitability and technology upgrades over raw volume expansion.
	- **Key data points**:
		- In `1998`: roughly `15` global DRAM suppliers
		- Today: only `3` major suppliers ([[$000660.KS]], [[$005930.KS]], [[$MU]])
		- Rather than building new fabs for volume, manufacturers are prioritizing **technology upgrades** (HBM3 → HBM3E → HBM4 → HBM4E)
		- [[$000660.KS]] reported a **`72%` profit margin in Q1** of the current cycle — more money in three months than in the entire prior year
	- **Implication**: The oligopoly structure removes the competitive incentive to flood the market. Margin maximization has replaced market-share warfare as the dominant strategy.

- ## Argument 4: Advanced Packaging Bottlenecks (The CoWoS Constraint)
	- **Context**: Even if memory fabricators wanted to flood the market with HBM, they physically cannot due to downstream manufacturing bottlenecks — specifically, [[$TSM]]'s advanced packaging.
	- **Key data points**:
		- HBM must be physically bound to the processor using [[$TSM]]'s **CoWoS** (Chip-on-Wafer-on-Substrate) technology
		- Historical CoWoS capacity expansion lead time: **`12–15` months**
		- Recently optimized lead time: **`6–9` months** — still a multi-quarter ceiling
		- This physical supply-chain constraint prevents sudden market oversupply regardless of memory fab capacity decisions
	- **Implication**: HBM supply is not just gated by wafer capacity at memory fabs — it is doubly gated by CoWoS packaging throughput at TSMC. Two independent bottlenecks must both expand before supply can overshoot.

- ## Argument 5: Rewritten Pricing Power and Long-Term Agreements (長協)
	- **Context**: In older cycles, buyers held the leverage, forcing manufacturers to cut prices during gluts. In this cycle, pricing power has shifted entirely to memory suppliers, who are rewriting contract terms to eliminate their own downside risk.
	- **Key data points**:
		- **"Lock Volume, Don't Lock Price" (鎖量不鎖價)**: Tier-1 buyers signing long-term agreements (LTAs) in domestic markets can only secure guaranteed **allocation volume** — the actual purchase price floats with future market rates; suppliers retain full price upside
		- **Capital / interest binding**: In overseas markets, buyers must either pay **massive upfront deposits** to secure supply or directly **finance / subsidize the memory manufacturer's capital expenditures** (equipment purchases), aligning the buyer's capital with the supplier's risk
		- [[$000660.KS]] projects the tight supply-demand imbalance will **not ease until at least `2028`**
	- **Implication**: The contractual structure itself has been redesigned to ensure suppliers cannot lose on the downside. This is not a normal buyer's market dressed up as a seller's market — the legal and financial architecture of procurement has been rewritten.

- ## Summary Table

	| Argument | Old Cycle Dynamic | New Cycle Dynamic |
	|---|---|---|
	| Demand driver | PC / smartphone replacement cycles | AI training + inference, exponential and structural |
	| Demand breadth | Single product bottleneck | Simultaneous DRAM + HBM + NAND explosion |
	| Supply behavior | Price wars, share grabs, oversupply | Oligopoly discipline, margin focus, tech upgrades |
	| Physical supply ceiling | Fab capacity only | Fab capacity + CoWoS packaging (dual bottleneck) |
	| Contract structure | Buyers set price in downturns | Suppliers lock volume, float price; buyers fund capex |

- ## External Validation — TSMC Chairman CC Wei (June 4, 2026 AGM)
	- CC Wei warned that memory chip supply constraints will hit **higher-end devices by end of 2026** — lower-cost devices were already affected; the shortage is now **spreading across the entire market**
	- This is a foundry-side confirmation of the broadening thesis: the shortage is not contained to AI servers and low-cost consumer segments; it is moving up market
	- Wei also said he "would like to" raise TSMC prices but wants to avoid memory-style aggressive price increases — framing memory chip pricing as the benchmark for unsustainable inflation; implicitly validates that memory price increases are real and significant
	- Source: [[2026-06-04-tsmc-agm-cc-wei-ai-demand-2026]]

- ## Cross-References
	- [[2026-04-07-michael-dell-memory-demand-arguments]] — Dell's `625x` demand expansion framework (`25x` per-GPU × `25x` system scale)
	- [[2026-04-29-ai-semiconductor-endgame-2026-part-1-hbm-token-economics]] — token throughput = HBM size × HBM bandwidth; HBM demand is endogenous to GPU roadmap
	- [[2026-04-04-memory-dram-pricing-mobile-market-collapse]] — Samsung Q1 +100% / Q2 +30% QoQ price increases; mobile unit collapse
	- [[2026-04-09-cxmt-china-hbm-mass-production]] — CXMT supply risk and why patent/equipment constraints limit the threat
	- [[2026-05-24-ai-data-center-buildout-capacity-and-spend-scenario]] — UBS HBM demand: 17.5 bn GB (2025) → 32.9 bn (2026E) → 58 bn (2027E)
	- [[2026-06-04-tsmc-agm-cc-wei-ai-demand-2026]] — CC Wei: shortage spreading from low-end to high-end devices by end of 2026
