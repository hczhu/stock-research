tags:: [[$MU]], [[Micron]], [[$000660.KS]], [[SK-hynix]], [[DRAM]], [[HBM]], [[HBM4]], [[DDR5]], [[LPDDR]], [[SOCAMM]], [[memory]], [[pricing]], [[gross-margin]], [[$NVDA]], [[Counterpoint]], [[TrendForce]], [[semiconductor]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-21
file-updated-at:: 2026-11-21

- ## HBM vs. conventional DRAM revenue at Micron and SK hynix (2026)
	- **Source**: an AI assistant's answer supplied by the user (November 2026), with two table screenshots. It draws on Micron's filings and earnings decks, SK hynix's Q3 2026 release, slides, call and quarterly report (filed November 16, 2026), Counterpoint, TrendForce, Kiwoom and IBK Securities.
	- **Neither company reports a standalone HBM revenue line**, so every HBM figure below is an estimate. Points that are checked against the repo or recomputed are labeled.
	- **Thesis**: in mid-2026, **conventional DRAM (DDR, LPDDR, GDDR) is about 84–90% of Micron's DRAM revenue, and HBM only about 10–16%**. SK hynix's HBM is also well below half of its DRAM revenue. HBM's share of DRAM revenue **fell** even though HBM revenue roughly doubled year over year. Conventional DRAM reprices every quarter and its prices went vertical, while HBM prices were locked in annual contracts. This also produced a **margin inversion**: conventional DRAM became more profitable than HBM. Both companies expect HBM's share to recover from Q4 2026, with HBM4 ramping and 2027 HBM4 contracts repriced higher.

- ## Micron: reported revenue and the derived HBM split
	- **Calendar mapping**: FQ3-26 ended May 28, 2026, roughly calendar Q2. FQ4-26 ended September 3, 2026, roughly calendar Q3. Both quarters show the same mix.
	- | Revenue line | FQ3-26 | FQ4-26 | Notes |
	  |---|---|---|---|
	  | **Total revenue** | **\$41.46B** | **\$54.23B** | Non-GAAP gross margin 84.9% in FQ3 and 87.0% in FQ4 |
	  | Total DRAM | \$31.3B (76% of total) | \$39.8B (73%) | Includes both conventional DRAM and HBM |
	  | Total NAND | \$9.9B (24%) | \$14.1B (26%) | Data-center SSDs above \$5B in FQ3, about \$10B in FQ4 |
	  | Cloud Memory BU (CMBU) | \$13.77B (33% of total; 83% gross margin) | \$16.3B (30%; 83% gross margin) | Holds **100% of HBM**, plus hyperscale DDR5 and LPDDR5 |
	  | **Estimated HBM** (derived) | **About \$3.5–5.0B** (about 11–16% of DRAM) | **About \$4.5–6.5B** (about 11–16% of DRAM) | HBM4 alone passed \$1B in FQ3. Total HBM grew more than 31% QoQ in FQ4 |
	  | **Estimated conventional DRAM** (derived) | **About \$26.3–27.8B** (about 84–89% of DRAM) | **About \$33.3–35.3B** (about 84–89%) | Server DDR5 and LPDDR5, PC and mobile DRAM, automotive and embedded |
	- **Repo cross-check**: FQ3 revenue of \$41.46B and HBM4 passing \$1B match [[2026-07-03-dram-hbm-supercycle-news-roundup-jun-jul-2026]] and [[MU-2026-Q2]], the FQ3 file.
		- **The gross-margin figures are both correct**: FQ3 gross margin was 84.6% GAAP and 84.9% non-GAAP. The roughly 85% and 84.6% in [[2026-07-01-circuit-podcast-semis-stock-memo]] both fit.
		- **Update (2026-11-21), confirmed by Micron's FQ4 release and deck** ([[MU-2026-Q3]]):
			- Revenue, DRAM, NAND and business-unit figures match the table above.
			- In FQ4, DRAM bits rose mid-single digits and prices rose high-teens %.
			- Micron said CY27 HBM contracts carry significant price increases, "**narrowing the gross margin gap with conventional DRAM**." That directly confirms the margin inversion.
	- ### How the HBM range is triangulated
		- **1. CMBU sets a hard ceiling.** Per Micron's FY2026 10-K, all data-center HBM sits in CMBU. HBM is therefore below \$13.77B (44% of DRAM) in FQ3 and \$16.3B (41%) in FQ4. It is well below those once hyperscale DDR5 and LPDDR5 are removed.
		- **2. CMBU's growth limits how big HBM can be.**
			- In FQ4, CMBU revenue rose **\$2.53B (+18.4% QoQ)**.
			- Management said HBM grew faster than total company revenue (**more than 31% QoQ**), and server LPDDR (SOCAMM) more than doubled.
			- If FQ3 HBM had been \$8–10B, 31% growth alone would have exceeded CMBU's entire dollar gain. So FQ3 HBM was about \$3–5B.
			- *Memo calculation*: total company revenue grew 30.8% QoQ, consistent with "more than 31%" for HBM. Solving HBM × 31% + (CMBU − HBM) × g = \$2.53B, where g is the growth of non-HBM CMBU revenue:
				- If non-HBM CMBU grew **10%**, FQ3 HBM was about **\$5.5B**.
				- If it grew **15%**, FQ3 HBM was about **\$2.9B**.
				- HBM growth above 31% would push both figures lower.
				- So the constraint is about **\$2.9–5.5B**, consistent with the table's \$3.5–5.0B.
		- **3. Industry data points to the lower end.**
			- Counterpoint puts Micron's HBM revenue share at **18% in calendar Q2 2026**, down from 21% in Q1 as Samsung ramped HBM4.
			- The 2026 global HBM market is about **\$50–60B**, or about \$13–15B a quarter in mid-2026.
			- The answer derives about **\$2.5–3.5B** a quarter for Micron in Q2, and \$4–6B in Q3 as HBM4 scaled.
			- Micron's last explicit HBM disclosure was an **\$8B annualized run rate** (about \$2B a quarter) in FQ4-25. HBM roughly doubled year over year since.
			- *Memo's reading*: 18% × \$13–15B is about \$2.3–2.7B, and a doubled \$2B is about \$4B. Both sit at or below the bottom of the table's ranges (\$3.5B for FQ3, \$4.5B for FQ4). So HBM's share of Micron's DRAM revenue is more likely near **10–12%** than 16%.
	- ### Why conventional DRAM outgrew HBM at Micron
		- **Supply squeeze plus agentic-AI CPU demand**:
			- HBM uses about **3× the wafer area per bit**, which starved conventional DRAM supply just as agentic workloads lifted server CPU memory demand.
			- Counterpoint notes GPU-to-CPU ratios tightening toward 2:1, and Vera Rubin's CPU DRAM rising to **1.5 TB per socket**.
			- Micron's blended DRAM prices rose by a **low-60s percentage QoQ in FQ3**, on only low-single-digit bit growth.
		- **Margin inversion**: HBM prices were mostly locked under annual agreements, while DDR5 and LPDDR repriced every quarter.
			- | FQ4-26 segment | Gross margin |
			  |---|---|
			  | Core Data Center | **90%** |
			  | Mobile and Client | **90%** |
			  | CMBU (HBM-heavy) | **83%**, flat QoQ |
			  | Company, non-GAAP | 87.0% |
			- Management said CMBU's margin was flat because of "higher pricing, offset by higher HBM mix."

- ## SK hynix: Q3 2026 (quarter ended September 30)
	- **SK hynix does not disclose an HBM vs. conventional DRAM split** in its release, slides or quarterly filing.
	- **Update (2026-11-21)**: the closest proxy is the Q3 deck's DRAM revenue-by-application chart ([[SKHY-2026-Q3]]).
		- **The chart**: "Graphics (incl. HBM)" fell from about 42% of DRAM revenue in Q3 2025 to about 18% in Q2 2026 and about **16% in Q3 2026**. Server rose from about 33% to about 55%. These values are read from the chart.
		- *Memo calculation*: about KRW 12.5T for graphics including HBM, vs. about KRW 43T for server DRAM, in Q3 2026.
		- **What it supports**: the "well below half" conclusion, with HBM's share likely closer to one-sixth of DRAM revenue. SK hynix's categories may not map exactly to HBM.
	- | Metric | Q3 2026 | Source |
	  |---|---|---|
	  | **Total revenue** | **KRW 104.62T** (+32% QoQ, +328% YoY) | Q3 release |
	  | DRAM share (conventional + HBM) | **75%** (about KRW 79.0T) | Q3 slides, Kiwoom estimate |
	  | NAND / other | 24% NAND, about 1% other | Q3 slides |
	  | DRAM bits and prices | Bits up about **10% QoQ**; average selling price up **high-20s% QoQ** | Q3 call |
	  | Server DDR5 shipments | **Up more than 40% QoQ**, well above blended DRAM | Q3 call |
	  | Largest customer (estimated to be Nvidia) | **14.8%** of 9M26 revenue (KRW 34.98T) | Q3 quarterly report |
	  | Second-largest customer (big tech) | **10.1%** of 9M26 revenue (KRW 23.85T) | Q3 quarterly report |
	  | HBM share of the big three's DRAM wafers | **About 23% in 2026**, rising to about 30% in 2027 | TrendForce |
	- *Memo calculations*:
		- +328% YoY implies Q3 2025 revenue of about KRW 24.4T, and +32% QoQ implies Q2 2026 of about KRW 79.3T.
		- 9M26 revenue of KRW 236.5T implies Q1 2026 of about KRW 52.6T.
		- Bits +10% with prices up high-20s% implies DRAM revenue up about **40% QoQ**, faster than total revenue (+32%).
		- 75% of KRW 104.62T is KRW 78.5T. The "about 79.0T" implies a share closer to 75.5%.
	- **Why conventional DRAM outpaced HBM in Q3**:
		- **Conventional prices overtook fixed HBM contracts**:
			- Counterpoint's Q3 tracker shows HBM's share of DRAM revenue falling across the market, even as HBM revenue nearly doubled.
			- Conventional **DDR revenue rose about 500% YoY and LPDDR about 400%**.
			- **16Gb DDR5 contract prices rose more than 450%** from October 2025 to September 2026.
			- IBK Securities said HBM contributed only a limited part of SK hynix's Q3 jump in DRAM prices.
		- **Agentic AI lifted server DDR5**: Counterpoint ties the squeeze to GPU-to-CPU ratios narrowing from 4:1 toward 2:1 and 1:1, and to larger host memory. Vera Rubin racks nearly triple CPU DRAM per socket, to 1.5 TB. SK hynix highlighted server DDR5 shipments up more than 40% QoQ.
		- **Customer figures cap HBM's likely share**: the largest customer (14.8%) and the second-largest (10.1%) together were about 25% of 9M26 revenue. The answer concludes that, even counting HBM sold to ASIC and hyperscaler customers through both, HBM stays **well below half** of DRAM revenue at current conventional prices.
			- *Memo calculation*: with DRAM at about 75% of revenue, the top two customers equal about **33% of 9M DRAM revenue**, even if they bought only HBM. This is suggestive rather than a strict cap, because other HBM buyers (AMD, hyperscaler ASICs) are not broken out. The 9M average also includes earlier quarters, when HBM's share was higher.
		- **Margin inversion**: on the Q3 call, CFO Woo-hyun Kim said finalized 2027 HBM4 volume and pricing deals will let "the profitability gap between HBM and conventional DRAM … narrow meaningfully." That implicitly confirms conventional DRAM currently earns more than HBM.

- ## Side by side
	- | Item | Micron | SK hynix |
	  |---|---|---|
	  | Calendar Q3 2026 revenue | \$54.23B (FQ4-26) | KRW 104.62T |
	  | DRAM share of revenue | 73% | 75% |
	  | HBM disclosed? | No. Bounded by CMBU | No |
	  | Estimated HBM share of DRAM | About 11–16% (memo's reading: likely near the low end) | Well below half (no point estimate) |
	  | Evidence of margin inversion | CMBU at 83% vs. 90% for the conventional-heavy segments | CFO expects the HBM-vs-conventional profitability gap to narrow in 2027 |
	  | Conventional DRAM driver | Prices up low-60s% QoQ (FQ3) | DRAM prices up high-20s% QoQ, server DDR5 shipments up more than 40% QoQ |

- ## The mix outlook for Q4 2026 and 2027
	- **HBM4 crossover in Q4 2026**: full-scale HBM4 mass production began in Q3. SK hynix expects HBM4 to overtake HBM3E in both bit shipments and revenue in Q4 2026, as the M15X fab ramps to full capacity.
	- **HBM4 repriced in 2027**:
		- TrendForce projects HBM4 prices rising from about **\$2.05 per Gb in 2026 to \$3.00–5.50 per Gb in 2027**, which is +46% to +168% (memo calculation).
		- The big three's DRAM wafer allocation to HBM rises from about 23% to about 30%.
		- HBM uses 3–4× as many wafers per bit, so this keeps crowding out conventional DRAM capacity.
	- **The answer's view**: HBM's share of revenue should rebound relative to conventional DRAM over the next several quarters, while conventional DRAM stays tight.

- ## Related in the repo
	- **HBM crowding out conventional DRAM**: [[2026-06-03-hbm-demand-scaling-crowding-out-conventional-dram]], [[2026-06-08-ddr-vs-hbm-price-trend-divergence]].
	- **Financials of the big three memory makers**: [[2026-06-04-memory-market-and-big3-financials]].
	- **Samsung's HBM share recovery and Counterpoint's Q3 DRAM shares**: [[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]].
	- **Custom HBM and base dies**: [[2026-11-20-dram-commodity-vs-cpu-gpu-custom-hbm4-switching-friction]], [[2026-11-20-tsmc-custom-hbm-base-die-strategic-leverage]].
	- **Index-level view**: [[DRAM-memory-ssd-index-thesis]].
