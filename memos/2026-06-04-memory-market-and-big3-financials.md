- tags:: [[DRAM]], [[HBM]], [[NAND]], [[$005930.KS]], [[$000660.KS]], [[$MU]], [[semiconductor]], [[AI infrastructure]], [[supply]]
  file-created-at:: 2026-06-04

- ## Memory Market Size and Big 3 Financials — Data Compilation
	- **Source**: Synthesized from memos in this repo; primary sources include Morgan Stanley, Epoch AI, UBS, Goldman Sachs, Gartner; Big 3 annual and quarterly earnings reports (2025–Q1 2026)
	- **Unit note**: HBM volume rows below are in mn GB (gigabytes). Raw source data is in Gb (gigabits); divided by 8 to convert. ASP derived from HBM market size ÷ HBM demand volume in GB.

- ## Table 0: Memory Market and Big 3 Revenue Overview

	| Metric | 2025 | 2026E | 2027E | 2028E |
	|---|---:|---:|---:|---:|
	| **Big 3 combined memory revenue ($B)** | **$178** | **$439¹** | n/a | n/a |
	| Big 3 revenue growth YoY | +35% | +147%¹ | n/a | n/a |
	| Total memory market size ($B) | $220 | $890 | n/a | n/a |
	| **HBM market size ($B)** | **$31.5** | **~$70²** | **$116** | **$168** |
	| HBM volume demand — MS (mn GB) | 2,440 | 4,276 | 7,011 | n/a |
	| HBM volume demand — UBS (mn GB) | 2,188 | 4,113 | 7,250 | n/a |
	| HBM volume supply — MS (mn GB) | 2,846 | 4,375 | 6,730 | n/a |
	| HBM volume supply — UBS (mn GB) | n/a | n/a | n/a | n/a |
	| HBM ASP ($/GB) | $14.4 | ~$17.0 | ~$16.0 | n/a |

	- **¹ 2026E Big 3 revenue**: Annualized from Q1 2026 × 4 (SK Hynix $35.5B + Samsung $50.5B + Micron $23.9B = $109.9B/quarter). Likely understates full year if prices continue rising through H2 2026
	- **Big 3 2025 breakdown**: SK Hynix FY2025 $68B (KRW 97.15T, +50% YoY); Samsung memory FY2025 $73B (KRW 104.1T, +23% YoY); Micron FY2025 (FYE Sep) $37B (+49% YoY)
	- **Big 3 2024 base** (for growth calc): SK Hynix ~$45B, Samsung memory ~$62B, Micron $25B → total ~$132B
	- **² HBM 2026E market size**: ~$70B is a midpoint estimate; Goldman Sachs revised 2027E to $116B (from $75B prior) in June 2026, implying ~$65–75B for 2026E by interpolation
	- **HBM 2027E/2028E**: Goldman Sachs June 2026 forecast (revised up from $75B/$100B prior estimates)
	- **Total memory 2025/2026E**: Morgan Stanley Chipflation report June 2, 2026; $890B is full-year 2026E forecast (not annualized Q1), +71% upward revision from prior $520B estimate
	- **HBM ASP**: Derived as HBM market size ÷ UBS demand (converted from Gb to GB ÷ 8); 2025: $31.5B / 2,188 mn GB = $14.4/GB; 2027E: $116B / 7,250 mn GB = $16.0/GB
	- **UBS supply**: UBS did not publish HBM supply-side forecasts in available memos

- ## How the $890B 2026E Memory TAM Is Built (MS Exhibit 40)

	- The $890B is **total memory — DRAM + NAND, not DRAM alone**. MS reaches it as the 2025 base plus a record one-year increment, decomposed by segment:

	| Build step | DRAM | NAND | Total |
	|---|---:|---:|---:|
	| 2025 memory market (base) | — | — | $220B |
	| + 2026 YoY incremental revenue (Exhibit 40) | ~$445B | ~$150B | **~$595B** |
	| = implied 2026E (base + increment) | — | — | ~$815B |
	| **2026E memory TAM (MS headline)** | — | — | **$890B** |

	- **Estimate revision** — the $890B is a fast-moving number; MS raised it sharply in just 3 months:

	| 2026E memory TAM estimate | Value |
	|---|---:|
	| Prior estimate (≈Mar 2026) | $520B |
	| Current estimate (Jun 2, 2026) | $890B |
	| Revision | +$370B (+71%) |

	- **Scale context** — the ~$600B YoY *increment* in memory revenue alone rivals or exceeds entire standalone 2026 hardware TAMs (Exhibit 40):

	| 2026 standalone market | TAM |
	|---|---:|
	| Smartphone | $600B |
	| **2026 incremental memory revenue** | **~$595B** |
	| Server | $424B |
	| PC | $256B |
	| External Storage | $38B |

	- **Incremental memory $ burden by end market** (who absorbs the cost): Servers **$246B**, Smartphones **$175B**, PCs **$132B**, External Storage **$13B** (~$566B total) — over half of the ~$1.3T aggregate hardware TAM
	- **Reconciliation note**: $220B base + ~$595B increment ≈ $815B, ~$75B short of the $890B headline. The gap reflects rounding ("~$600B" increment) and stitched TrendForce/IDC data vintages — MS does not present a fully tied-out bridge; the $890B is the round full-TAM figure
	- **Source**: Morgan Stanley Chipflation report, June 2, 2026, Exhibit 40 (TrendForce estimates, IDC data, MS Research)

- ## Table 0b: Big 3 Implied Combined Market Cap by P/S Multiple

	- Bull-case framing: the Big 3 capture **~80% of the $890B 2026E memory TAM** (see derivation below) → **~$712B** combined Big 3 memory revenue. Implied combined market cap at various price-to-sales (P/S) multiples:

	| P/S Ratio | 2026E Big 3 Memory Revenue ($B) | Implied Combined Market Cap ($T) | vs. Current ~$3.5T |
	|---:|---:|---:|---:|
	| 4× | $712 | $2.85T | −19% |
	| **5×** | **$712** | **$3.56T** | **+2%** |
	| 6× | $712 | $4.27T | +22% |
	| 8× | $712 | $5.70T | +63% |
	| 10× | $712 | $7.12T | +103% |

	- **Big 3 share of TAM (~80%)**: Weighted by segment — DRAM (incl. HBM) ~72% of the $890B TAM with Big 3 at ~90% share, plus NAND ~28% of TAM with Big 3 at ~58% share (Kioxia, SanDisk, YMTC hold the rest). Blended ≈ 81%, rounded to ~80% → ~$712B
	- **$890B TAM source**: Full 2026E memory TAM from Table 0 (MS Chipflation, June 2, 2026)
	- **Current combined market cap**: The three companies are together worth ~$3.5T as of June 2026
	- **5× P/S as a conservative anchor**: A conservative 5× multiple on ~$712B implies ~$3.56T combined — roughly in line with the current ~$3.5T (+2%), suggesting the market is already pricing ~5× peak-cycle memory sales; meaningful upside requires either higher multiples or revenue above the $712B share-adjusted level
	- **Caveat — Samsung is not a pure play**: Samsung's market cap includes non-memory businesses (foundry, mobile, displays, consumer electronics). Applying a memory-revenue P/S to Samsung's full market cap overstates the memory-attributable multiple; the table is a blunt aggregate, not a clean per-company valuation
	- **Caveat — cyclicality**: Memory is deeply cyclical; peak-cycle revenue should command a lower P/S than the table's flat multiples imply. The market typically de-rates memory names as the cycle approaches its top, anticipating the downturn

- ## Table 1: Server Memory Market Size ($ Billion)

	| Segment | 2024 | 2025 | 2026E | 2027E | 2028E |
	|---|---:|---:|---:|---:|---:|
	| HBM | $12.1B | $31.5B | ~$60–75B† | ~$110–130B† | n/a |
	| Server DRAM (non-HBM) | n/a | n/a | n/a | n/a | n/a |
	| **Total server memory** | n/a | n/a | n/a | n/a | n/a |
	| **Total memory (all)** | n/a | **$220B** | **$890B** | n/a | n/a |

	- **HBM 2024/2025**: Epoch AI; tracks HBM spend across NVIDIA, AMD, Google, Amazon chips (all major HBM buyers — effectively total HBM market). Q4 2025 alone = $11.0B, implying ~$44B+ annualized run rate entering 2026
	- **HBM 2026E/2027E (†)**: Derived from UBS volume model (+88% YoY in 2026E, +76% in 2027E) applied to 2025 base, with modest ASP compression assumed. Not directly sourced from a memo dollar figure
	- **Total memory $220B/$890B**: Morgan Stanley Chipflation report (June 2, 2026); $890B reflects a +71% upward revision in just 3 months from a prior $520B estimate; includes all memory types globally
	- **Server DRAM dollar market**: Not available in current memos. Volume data available: commodity DRAM demand 316,640 mn Gb (2025) → 469,675 mn Gb (2026E) → 619,970 mn Gb (2027E) per Morgan Stanley, of which server's share of DRAM bit demand rises from 37% (2023) → 59% (2028E)

- ## HBM Volume Demand (mn Gb) — Morgan Stanley / UBS

	| Source | 2023 | 2024 | 2025 | 2026E | 2027E |
	|---|---:|---:|---:|---:|---:|
	| Morgan Stanley (demand) | 1,866 | 9,059 | 19,516 | 34,205 | 56,085 |
	| Morgan Stanley (supply) | 3,150 | 11,436 | 22,765 | 34,997 | 53,837 |
	| UBS (demand, bn GB) | — | — | 17.5 | 32.9 | 58.0 |
	| UBS YoY growth | — | — | — | +88% | +76% |

	- MS and UBS figures broadly consistent; slight differences reflect model vintage and methodology
	- HBM supply and demand converge in 2026E and reverse (demand > supply) by 2027E per MS model

- ## Table 2: Big 3 Latest Quarter Revenue by Segment

	**Note**: None of the Big 3 separately disclose HBM revenue or server vs. consumer DRAM revenue. Segment breakdowns below reflect the finest granularity publicly reported. KRW figures converted at ~1,480 KRW/USD.

	### SK Hynix — Q1 2026

	| Metric | Value | Source |
	|---|---|---|
	| **Total revenue** | **KRW 52.58T (~$35.5B)** | SK Hynix Q1 2026 earnings (Apr 23) |
	| Revenue growth | +198% YoY / +60% QoQ | SK Hynix Q1 2026 earnings |
	| DRAM revenue (implied) | KRW ~41.5T (~$28.0B) | Total minus NAND |
	| HBM revenue | Not disclosed; ~56% HBM supply market share | — |
	| Server DRAM revenue | Not broken out | — |
	| Consumer DRAM revenue | Not broken out | — |
	| **NAND revenue** | **KRW 11.04T (~$7.5B), +248% YoY** | Seoul Economic Daily / earnings |
	| **Operating margin** | **72%** | SK Hynix Q1 2026 earnings |
	| Operating profit | KRW 37.61T (~$25.4B) | SK Hynix Q1 2026 earnings |
	| Net margin | 77% | SK Hynix Q1 2026 earnings |
	| Operating profit vs. prior year | Q1 2026 alone exceeded all of FY2025 | Earnings call |
	| FY27E operating margin (DRAM) | 82.8% | Goldman Sachs estimate |
	| FY27E operating profit revision | +21% vs. prior GS estimate | Goldman Sachs |
	| FY28E operating profit revision | +24% vs. prior GS estimate | Goldman Sachs |

	### Samsung — Q1 2026

	| Metric | Value | Source |
	|---|---|---|
	| **Memory revenue** | **KRW 74.8T (~$50.5B)** | Samsung Q1 2026 earnings (Apr 30) |
	| Revenue growth | +292% YoY / +101% QoQ | Samsung Q1 2026 earnings |
	| DS Division revenue (memory + foundry) | KRW 81.7T (~$55.2B) | Samsung Q1 2026 earnings |
	| DS Division operating profit | KRW 53.7T (~$36.3B), ~48× YoY | Samsung Q1 2026 earnings |
	| DRAM revenue | Not separately disclosed | — |
	| HBM revenue | Not disclosed; tripled YoY; conventional DRAM currently more profitable per chip | Samsung earnings call |
	| Server DRAM revenue | Not broken out | — |
	| Consumer DRAM revenue | Not broken out | — |
	| NAND revenue | Not separately disclosed | — |
	| DRAM contract price, Q1 2026 | ~KRW 20,000 (+100% QoQ) | pricing memo |
	| DRAM contract price, Q2 2026 | ~KRW 26,000 (+30% QoQ) | pricing memo |
	| HBM yield rate, 2025 | 60% | MS Exhibit 30 |
	| HBM yield rate, 2026E | 55% (declining — execution risk) | MS Exhibit 30 |
	| HBM UTR, 2025 | 60% (vs. 100% for peers) | MS Exhibit 30 |
	| Memory capex 2026E | $40.0B (+20% YoY) | semi capex memo |
	| Samsung MX operating profit FY2026E | KRW ~5T (>60% decline) | DRAM pricing memo |

	### Micron — FQ2 2026 (Dec 2025 – Feb 2026; FYE September)

	| Metric | Value | Source |
	|---|---|---|
	| **Total revenue** | **$23.86B** | Micron FQ2 2026 earnings (Mar 18) |
	| Revenue growth | +196% YoY / +75% QoQ | Micron FQ2 2026 earnings |
	| **DRAM revenue** | **$18.8B (79% of total), +207% YoY** | Micron FQ2 2026 earnings |
	| HBM revenue | Not disclosed; HBM sold out through 2026 | Micron FQ2 2026 earnings |
	| Server / Data Center DRAM | Not broken out; Data Center revenue +150% YoY | Micron FQ2 2026 earnings |
	| Consumer DRAM revenue | Not broken out | — |
	| **NAND revenue** | **$5.0B (21% of total), +169% YoY** | Micron FQ2 2026 earnings |
	| **Gross margin** | **74.4%** (all-time high; up from 36.8% a year prior) | Micron FQ2 2026 earnings |
	| Net income | $13.8B ($12.07/share) | Micron FQ2 2026 earnings |
	| FQ3 2026 revenue guidance | $33.5B ± $750M | Micron FQ2 2026 earnings |
	| FQ3 2026 gross margin guidance | ~81% | Micron FQ2 2026 earnings |
	| Memory capex FY2026E (FYE Sep) | $20.0B (+45% YoY) | semi capex memo |
	| HBM yield rate, 2025 | 70% | MS Exhibit 30 |
	| HBM UTR, 2025 | 100% | MS Exhibit 30 |

- ## Big 3 Capital Expenditure ($ Billion)

	| Vendor | 2024 | 2025 | 2026E | 2025 Growth | 2026E Growth |
	|---|---:|---:|---:|---:|---:|
	| Samsung | $33.0B | $33.4B | $40.0B | +1% | +20% |
	| SK Hynix | $11.7B | $19.4B | $27.4B | +66% | +42% |
	| Micron (FYE Sep) | $8.1B | $13.8B | $20.0B | +70% | +45% |
	| **Total** | **$54.9B** | **$69.1B** | **$90.3B** | **+26%** | **+31%** |

	- **Source**: SC-IQ estimates via Morgan Stanley semiconductor capex memo

- ## HBM Production Share by Vendor (Implied from MS Exhibit 30)

	| Vendor | 2025 Production (mn Gb) | Share | 2027E Production (mn Gb) | Share |
	|---|---:|---:|---:|---:|
	| SK Hynix | 12,830 | 56% | 22,226 | 41% |
	| Samsung | 6,387 | 28% | 21,239 | 40% |
	| Micron | 3,548 | 16% | 10,372 | 19% |
	| **Total** | **22,765** | 100% | **53,837** | 100% |

	- SK Hynix leads in 2025 on volume share, driven by superior yield (75%) and UTR (100%)
	- Samsung and SK Hynix converge by 2027E as Samsung recovers UTR to 100% and yield to 70%
	- Micron grows fastest proportionally but remains smallest in absolute volume

- ## Remaining Data Gaps
	- **HBM revenue by vendor**: None of the Big 3 disclose HBM revenue separately; it is embedded in DRAM; approximate shares can be inferred from production volume data (Table 4 above)
	- **Server vs. consumer DRAM split**: Not broken out by any vendor in public filings; must be estimated using DRAM share of shipments from industry reports (e.g., Morgan Stanley, IDC)
	- **Samsung DRAM vs. NAND revenue**: Samsung reports memory as a single line; DRAM/NAND split not separately disclosed (unlike SK Hynix, where NAND is attributed to a separate business unit)
	- **Server DRAM dollar TAM**: Requires a Gartner / IDC / IHS Markit market sizing report — not currently in memos
	- **2028 HBM forecast**: MS and UBS models end at 2027E
