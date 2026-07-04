- tags:: [[DRAM]], [[HBM]], [[NAND]], [[memory]], [[$MU]], [[Samsung]], [[SK-hynix]], [[$SNDK]], [[semiconductor]], [[AI]], [[data-center]], [[capex]], [[$AAPL]], [[CXMT]], [[pricing]], [[supply-shortage]]

- **Source**: Aggregated memory-sector news feed, June 15 – July 3 2026 (TrendForce, DIGITIMES, CLSA, Yonhap, WSJ/Korea press, Micron earnings, Ming-Chi Kuo, Bernstein/Citi/Goldman). Companion to [[DRAM-memory-ssd-index-thesis]].

- **Thesis reinforcement**: The memory super-cycle intensified into mid-2026. Pricing power is broadening (Samsung seeking another +20% QoQ in Q3), demand forecasts were revised sharply upward, Korea announced trillion-dollar capacity commitments that suppliers themselves say are insufficient, and the shortage is now visibly rationing supply away from consumer electronics into AI/data-center — forcing price hikes and spec downgrades across phones, PCs, and gaming.

- ## Pricing — Another Leg Up in Q3 2026

	- | Signal | Data | Source |
	  |---|---|---|
	  | Samsung Q3 DRAM price hike | Seeking **up to +20% QoQ**; verbal notices already sent to customers | TrendForce / ZDNet, Jul 3 |
	  | Samsung LPDDR Q3 hike | **>20% QoQ** | TrendForce, Jul 3 |
	  | SK Hynix Q3 | DRAM & NAND prices likely **+20%+ QoQ** as general-purpose shortage deepens | Businesskorea |
	  | NAND ASP (Micron FQ3) | Surged **mid-80% range** QoQ; bit shipments +mid-single-digit | Citi (Merchant) |
	  | 4-year DRAM price move | **~700%** increase over four years (cited in price-fixing suit) | Class action, N.D. Cal |
	  | SanDisk LTA floor | **~\$0.29/GB** floor in recently signed long-term agreements | Bernstein (Newman) |

	- **Micron contract ceiling caveat (bearish nuance)**: Micron's largest contracts now carry a **ceiling price set at the 2026Q2 market price**, capping upside on those volumes for the next few years — a signal that the spot-vs-contract spread may compress even as reported ASPs stay high.

- ## Demand Forecast — Revised Sharply Higher

	- | Forecast | Figure | Source |
	  |---|---|---|
	  | 2026 global memory market | Raised from **\$551.6B → \$889.3B** | TrendForce (post-Micron) |
	  | 2030 semiconductor industry rev | **\$2.5T** (+80% vs 2026), of which **~\$1.4T is memory** | CLSA (Sanjeev Rana) |
	  | Memory share of semi revenue | **28% → 52%** over past 10 years | CLSA |
	  | Consumer→datacenter reallocation | **15–20%** of 2026 consumer-electronics memory allocation shifts to datacenter/AI in 2027 | Ming-Chi Kuo |

	- **Structural driver**: The shift from training toward **inference-centric Agentic AI** is expanding memory demand per workload — the same mechanism behind the KV-cache / high-capacity-SSD pull. CLSA argues AI has **broken Korea memory's traditional boom-bust cycle** because customers are signing multi-year deals at record prices specifically because they fear unavailability.

- ## Capacity Expansion — Trillion-Dollar Commitments (That Suppliers Call Insufficient)

	- Korea's government-driven megaproject: combined **KRW ~896T (\$578B)** pledged by Samsung + SK for the southwest (Honam) region; broader packages total into the trillions of USD.

	- | Company | Commitment | Detail |
	  |---|---|---|
	  | Samsung (domestic total) | **KRW 2,655T (~\$1.72T)** | Pyeongtaek/Yongin buildout + new Gwangju (Honam) memory fab; HBM packaging concentrated in Cheonan/Onyang/Chungcheong |
	  | SK Hynix (total) | **KRW 1,100T (~\$710B)** | Yongin \$600T, Cheongju \$100T, Southwest \$400T; **Yongin timeline accelerated by 12 years**; plans to **~double DRAM wafer capacity by 2030–2031** |
	  | SK Hynix (Cheongju) | **KRW 100T (~\$64B)** | \$80T NAND fab by 2029 + \$20T packaging plant by late 2027 |
	  | Samsung + SK (Chungcheong) | **KRW 392T (\$252.5B)** | HBM fabs + packaging cluster |

	- **Key caveat**: SK Hynix explicitly **warned even faster construction will not be enough** to meet projected AI memory demand. Samsung/SK also declined to give firm timelines for the southwest fabs — "leaving room to adjust until the long-term memory cycle becomes clearer" (i.e., disciplined, demand-gated capacity, not a blind glut).

- ## HBM Competitive Dynamics

	- **Samsung closing the gap**:
		- HBM4E reliability yield **>70%** (80%+ = "mature"); 1c DRAM and 1d (D1d) process advantage claimed
		- HBM4 revenue **crossed \$1B in ~4 months**, projected **\$10B in 2026** (first year)
		- HBM share projected **27% (2025) → 37% (2026)**; SK Hynix **56% → 43%**; Samsung could **overtake in 2027**
		- Allocated **~75,000 of 150,000** monthly HBM wafers to HBM4; suspended low-demand HBM3E 8-layer
	- **SK Hynix**: shipped **12-layer HBM4E samples early** (48GB/stack, 16Gbps/pin, ~4TB/s, 20%+ efficiency); still holds **~57–62% HBM share** and ~2/3 of Nvidia Rubin orders (Goldman). But is **deliberately slowing HBM4 ramp** to harvest higher-margin DDR5 (see [[DRAM-memory-ssd-index-thesis]] anecdote 2026-06-23).
	- **Demand caveat**: **Nvidia Rubin (HBM4) production forecasts trending down** — a watch-item for HBM4 volume timing. Only Nvidia currently requesting HBM4E.

- ## Shortage Spillover — Rationing Hits Consumer Electronics

	- The clearest confirmation the shortage is **real and binding**: memory is being pulled from consumer devices into AI/datacenter, forcing price hikes and downgrades.

	- | Sector / Product | Impact |
	  |---|---|
	  | Apple | Raised prices on **Macs, iPads, Vision Pro, home devices**; **A20 chip orders 10–20% below plan** for late-2026/early-2027 (LPDDR squeeze, per Kuo) |
	  | Apple sourcing | Lobbying US govt to buy DRAM from **CXMT** (on Pentagon 1260H list) — needs a second mainstream-memory source |
	  | Samsung phones | **Dropped Exynos from Galaxy A18** (using MediaTek 4G / Qualcomm 5G) as cost move; Galaxy A27 **+\$50**; A37 pricier; **Z Fold 8 price hike** |
	  | Lenovo | Warns higher memory prices are the **"new normal"** |
	  | Gaming | SanDisk officially-licensed **PS5 SSDs up to ~\$2,960** (5× a PS5 console) |
	  | MLCC (adjacent) | LTA trend spreading beyond memory — Samsung Electro-Mechanics signed **KRW 454B** 1-yr AI-server MLCC contract |
	  | Macro | Asia Times: 25-yr consumer-tech disinflation era is over — **memory inflation now an upward CPI/PPI force** |

	- **Ming-Chi Kuo framing**: supply crunch could **last through 2027**; not just higher prices but genuine availability constraint.

- ## Corporate / Financial Scorecard

	- **Micron FQ3-2026 (record)**: revenue **\$41.46B (+346% y/y)**, GAAP net income **\$28.24B (+1,398% y/y)**, gross margin **~85%** (all-time high), HBM4 revenue **>\$1B**; guided ~\$50B next quarter. "AI megacycle" confirmed.
	- **Q2 consensus**: Samsung operating profit **~\$56–70B (86–100T won)**; SK Hynix **~63T won (+589% y/y)**.
	- **SK Hynix Nasdaq ADR**: raising **~\$29.4B**, trading ~**July 10**, proceeds for **capacity expansion** — among the largest offerings on record. Market cap crossed **\$1T+**, briefly overtook Samsung as Korea's most valuable company (first time in 25+ years).
	- **Mohnish Pabrai**: called selling Samsung/SK Hynix a "deeply painful mistake"; memory now a durable **Big 3 oligopoly** (patent/talent/fab barriers block a 4th entrant); "don't sell."

- ## Bear / Risk Signals (for balance)

	- **Supply-glut selloff (Jul 1–2)**: SanDisk **−14%**, Seagate **−10%**, Micron **−5.5%** on fears of new Samsung/SK supply + potential AI-capex plateau. Morningstar warned of a **20–30% drop** (vs BofA's \$2,500 SanDisk target).
	- **Capex-vs-demand math (from earlier trade log)**: research-firm memory-market forecasts (\$1T 2026 / \$1.5T 2027) imply server-memory TAM approaching the **\$700–800B Big-4 hyperscaler capex** envelope — euphoria risk if capex plateaus. See [[2026-06-24-soxx-dram-401k-trim-pre-micron-earnings]].
	- **Meme-stock warning**: Bloomberg (Shuli Ren) flags Samsung/SK Hynix/SpaceX trading on gamma squeezes and Korean leveraged ETFs, not fundamentals. Korean regulator issued a leveraged-product investor warning.
	- **Price-fixing class action** (N.D. Cal, filed Jun 25): Samsung/SK Hynix/Micron accused of using the HBM shift as pretext to wind down DDR3/DDR4 and inflate commodity DRAM (~700% over 4 yrs). The three control ~90% of DRAM.
	- **China (CXMT)**: DRAM ASP reportedly only **5–10% below** the Big 3 — signals China is **not dumping** (wants profit), but is catching up; SemiAnalysis flags CXMT IPO + wafer adds as a 2027–2028 supply watch-item.
	- **SEMI (incl. Micron, Samsung) letter to Treasury (Bessent)**: warns US intervention in chip pricing/capacity would **worsen** the shortage.
