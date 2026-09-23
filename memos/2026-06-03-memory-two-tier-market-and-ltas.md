- tags:: [[DRAM]], [[HBM]], [[NAND]], [[hyperscalers]], [[$005930.KS]], [[$000660.KS]], [[$MU]], [[$285A.T]], [[AI infrastructure]], [[semiconductor]], [[supply chain]]
  file-created-at:: 2026-06-03
- **Source**: Morgan Stanley "Chipflation" report, June 2, 2026 — Sections: LTAs, Two-Tier Market
- **Core argument**: The memory market is shifting from price-driven commodity cycles to supply-security-focused allocation, creating a structural two-tier market where AI/cloud buyers lock in supply first and non-LTA buyers face a smaller, more volatile, more expensive residual pool
- **The allocation stack (who gets memory supply first)**

	| Tier | Buyer Type | Memory Products | Procurement Method |
	|---|---|---|---|
	| 1 | Hyperscalers / AI accelerator ecosystem | HBM, server DRAM, eSSD | LTAs / prepay |
	| 2 | Server OEMs / cloud infrastructure | Server DRAM, eSSD | Strategic contracts |
	| 3 | Premium PC / smartphone OEMs | DDR, LPDDR, NAND | Annual contracts |
	| 4 | Autos / networking / industrial / medical | DDR, NAND, specialty | Qualified supply |
	| 5 | Small OEMs / startups / low-end devices | Commodity DRAM/NAND | Spot / distribution |

	- Higher allocation priority = lower spot-price exposure; lower tier = higher volatility
- **Why LTAs are now absolute necessities (not just upcycle tools)**
	- Historically memory customers procured opportunistically; LTAs during upcycles had limited enforceability and were renegotiated when market softened
	- Now: CSPs are managing supply risk, not just price risk — AI deployment roadmaps depend on memory availability
	- Leading memory producers establishing strategic supply chain partnerships via LTAs, allowing them to lock in long-term orders and prices, establish stable high-margin models, and mitigate cyclical volatility

	| Vendor | LTA Terms |
	|---|---|
	| Samsung | Moving quarterly/annual contracts to 3–5 year agreements |
	| SK hynix | Increasing customer requests for medium- to long-term supply commitments |
	| Micron | Announced 5-year Strategic Customer Agreement |
	| SanDisk | Multi-year partnerships backed by firm financial guarantees |
	| KIOXIA | Long-term supply agreements with hyperscale customers extending to FY28–29 |
- **The two-tier dynamic in practice**
	- As top-tier CSPs secure multi-year supply through LTAs, residual memory market becomes structurally tighter
	- Customers without LTAs procure from a smaller pool of uncommitted supply at higher, more volatile prices
	- Historically, weak PC/smartphone demand would loosen DRAM markets for everyone; this cycle AI demand keeps allocation tight even if consumer demand softens — HBM and server applications set the priority order
	- Suppliers have limited incentive to flood the market with commodity supply when AI customers offer stronger pricing, better margins, and more durable contracts
- **Demand shift from consumer to AI/server**

	| Category | 2023 Share | 2028E Share |
	|---|---:|---:|
	| DRAM server share of bit demand | 37% | 59% |
	| Enterprise SSD share of NAND bit demand | 18% | 65% |

	- Server/AI buyers have stronger purchasing power, longer-duration demand visibility, and greater willingness to sign LTAs → pricing and allocation gravitate toward AI/server at expense of consumer end markets
- **Implication for supplier pricing power**
	- The more supply committed to strategic AI customers, the less flexible supply for opportunistic buyers → supports ASP resilience even if parts of consumer demand weaken
	- LTAs instill price stability, improve earnings predictability, reduce risk of overbuilding, and lock in elevated pricing with prepayments
	- MS: market pricing for Samsung/SK hynix is not yet assigning meaningful P/E premium for LTA-backed earnings; if 10x P/E applied to LTA-backed earnings (70% commodity LTA coverage), 2027 P/E for Samsung/hynix could expand to ~8.5x (from 5x currently)
- **NAND: two-tier forming later but same trajectory**
	- NAND remains under-supplied through 2028E; sufficiency ratio deteriorates to ~14% undersupply in 2028E
	- NAND capacity additions recover only after net cuts in 2024–25, rising to ~170kwpm in 2028E (Samsung, KIOXIA/SanDisk, SK hynix/Solidigm, Micron, YMTC)
