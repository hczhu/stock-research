- tags:: [[HBM]], [[DRAM]], [[$005930.KS]], [[$000660.KS]], [[$MU]], [[$NVDA]], [[$AMD]], [[$GOOGL]], [[AWS]], [[$MSFT]], [[CoWoS]], [[semiconductor]], [[supply]], [[AI infrastructure]]
  file-created-at:: 2026-06-03

- ## HBM Supply and Demand Model — Morgan Stanley Exhibit 30
	- **Source**: Morgan Stanley Research estimates, Company data (Exhibit 30)
	- **Thesis**: HBM supply is growing rapidly but demand is outpacing it — total DRAM sufficiency deteriorates from −4% (2023–2025) to −17% (2026e) and −15% (2027e), with SK Hynix leading on both yield and utilization

- ## HBM TSV Capacity (K wpm)

	| Vendor | 2023 | 2024 | 2025 | 2026e | 2027e |
	|---|---:|---:|---:|---:|---:|
	| Samsung | 45 | 130 | 150 | 180 | 250 |
	| SK Hynix | 45 | 120 | 150 | 200 | 250 |
	| Micron | 3 | 20 | 60 | 100 | 110 |
	| **Total** | **93** | **270** | **360** | **480** | **610** |

- ## Yield Rate Assumptions

	| Vendor | 2024 | 2025 | 2026e | 2027e |
	|---|---:|---:|---:|---:|
	| Samsung | 50% | 60% | 55% | 70% |
	| SK Hynix | 60% | 75% | 65% | 70% |
	| Micron | 50% | 70% | 65% | 70% |

- ## UTR (Utilization Rate) Assumptions

	| Vendor | 2024 | 2025 | 2026e | 2027e |
	|---|---:|---:|---:|---:|
	| Samsung | 80% | 60% | 70% | 100% |
	| SK Hynix | 100% | 100% | 100% | 100% |
	| Micron | 100% | 100% | 100% | 100% |

- ## Implied HBM Production (mn Gb)

	| Vendor | 2023 | 2024 | 2025 | 2026e | 2027e |
	|---|---:|---:|---:|---:|---:|
	| Samsung | 1,500 | 4,435 | 6,387 | 9,696 | 21,239 |
	| SK Hynix | 1,500 | 6,273 | 12,830 | 17,363 | 22,226 |
	| Micron | 150 | 729 | 3,548 | 7,937 | 10,372 |
	| **Total** | **3,150** | **11,436** | **22,765** | **34,997** | **53,837** |

- ## Sufficiency Ratio (mn Gb)

	| Metric | 2023 | 2024 | 2025 | 2026e | 2027e |
	|---|---:|---:|---:|---:|---:|
	| HBM demand | 1,866 | 9,059 | 19,516 | 34,205 | 56,085 |
	| Commodity DRAM market demand | 209,527 | 243,423 | 316,640 | 469,675 | 619,970 |
	| Total HBM+DRAM demand | 211,393 | 252,481 | 336,156 | 503,879 | 676,055 |
	| Commodity DRAM market supply | 200,214 | 228,086 | 301,257 | 382,107 | 519,666 |
	| Total HBM+DRAM supply | 203,364 | 239,523 | 324,022 | 417,104 | 573,503 |
	| **Total DRAM sufficiency** | **−4%** | **−5%** | **−4%** | **−17%** | **−15%** |

	- 2026e and 2027e sufficiency ratios highlighted in red in source — deepening structural shortage

- ## Key Observations
	- **Capacity**: Total HBM TSV capacity grows 6.6× from 93K wpm (2023) to 610K wpm (2027e); SK Hynix and Samsung converge at 250K wpm by 2027e while Micron remains ~44% smaller
	- **SK Hynix execution lead**: Highest yield rates (75% in 2025 vs Samsung 60%) and 100% UTR every year — explains SK Hynix's dominant HBM market share and margin premium
	- **Samsung execution risk**: UTR drops to 60% in 2025 (vs 100% for peers) and yield dips to 55% in 2026e — HBM4 qualification delays are visible in the model assumptions
	- **Micron ramp**: Smallest base (3K wpm, 2023) but fastest percentage growth; 100% UTR from the start suggests disciplined, demand-pull ramp rather than speculative build
	- **Demand outpacing supply**: HBM demand grows from 1,866 mn Gb (2023) to 56,085 mn Gb (2027e) — 30× in four years. Total HBM production reaches only 53,837 mn Gb by 2027e, meaning HBM itself is still short in 2027e
	- **DRAM sufficiency worsening**: The −17% in 2026e is the worst in the model period — HBM capacity conversion is crowding out commodity DRAM supply faster than commodity demand is growing

- ## Investment Implications
	- **SK Hynix**: Best-positioned across all three dimensions — capacity, yield, and utilization. The yield and UTR gap vs Samsung is the structural source of SK Hynix's ASP and margin premium
	- **Samsung**: Recovery depends on closing the yield and UTR gap in 2026–2027; the model assumes full UTR recovery by 2027e — that assumption is the key risk to watch in Samsung earnings calls
	- **Micron**: Clean ramp profile with 100% UTR; the capacity gap vs Korean peers is the binding constraint, not execution. US-headquartered strategic value adds a policy premium
	- **Commodity DRAM**: Sufficiency ratio of −17% in 2026e reflects HBM wafer diversion crowding out conventional DRAM — supports the bull case for DDR5 and LPDDR5X pricing even independent of AI demand
	- **HBM demand model**: 56,085 mn Gb demand vs 53,837 mn Gb supply in 2027e means HBM remains sold out even at the end of the forecast horizon — no oversupply in sight through 2027

- ## HBM — AI Chip Consumption in 2026 (Exhibit 31)
	- **Source**: Morgan Stanley Research estimates; compiled using Asian supply chain checks
	- **Total CoWoS capacity allocated**: 1,479k wafers across all vendors
	- **Total HBM demand**: 4,034,885k GB = **32,279 mn Gb** — consistent with the 34,205 mn Gb demand figure in Exhibit 30's 2026e row (minor difference reflects model vintage)
	- Values in red in source (TPU v8i chips/wafer, TPU v8t CoWoS allocation, Trainium 3 CoWoS allocation) indicate MS estimates with higher uncertainty

- ## AI GPU Consumption (2026e)

	| Vendor | Product | CoWoS Alloc (k wafers) | Chips/wafer | Implied Shipments (k) | HBM Density (GB) | HBM Chip Units | Total HBM Size (GB) | HBM Generation | HBM Vendor | HBM Demand (k GB) |
	|---|---|---:|---:|---:|---:|---:|---:|---|---|---:|
	| NVIDIA | B300 | 390 | 14 | 5,460 | 36 | 8 | 288 | HBM3e 12hi | Hynix/Micron/Samsung | 1,572,480 |
	| NVIDIA | Vera CPU | 90 | 23 | 2,070 | — | — | — | — | — | — |
	| NVIDIA | Spectrum/CPX | 60 | — | — | — | — | — | — | — | — |
	| NVIDIA | Rubin R200 | 260 | 8 | 2,080 | 36 | 8 | 288 | HBM4 | Hynix/Micron/Samsung? | 599,040 |
	| NVIDIA | H200 | 75 | 27 | 2,025 | 24 | 6 | 141 | HBM3e 8hi | Hynix | 285,525 |
	| AMD | MI300 | 3 | 12 | 36 | 24 | 8 | 192 | HBM3 | Samsung | 6,912 |
	| AMD | MI350/375 | 7 | 12 | 84 | 36 | 8 | 288 | HBM3e 12hi | Samsung/Micron | 24,192 |
	| AMD | MI400 | 65 | 10 | 650 | 36 | 12 | 432 | HBM4 | Samsung/Micron | 280,800 |

- ## AI ASIC Consumption (2026e)

	| Vendor | Product | CoWoS Alloc (k wafers) | Chips/wafer | Implied Shipments (k) | HBM Density (GB) | HBM Chip Units | Total HBM Size (GB) | HBM Generation | HBM Vendor | HBM Demand (k GB) |
	|---|---|---:|---:|---:|---:|---:|---:|---|---|---:|
	| Google | TPU v7p (Ironwood; AVGO) | 145 | 16 | 2,320 | 24 | 8 | 192 | HBM3e 8hi | Hynix/Samsung | 445,440 |
	| Google | TPU v8i (Sunfish; AVGO) | 80 | 12* | 960 | 36 | 8 | 288 | HBM3e 12hi | Hynix/Samsung/Micron | 276,480 |
	| Google | TPU v8t (Zebrafish; MediaTek) | 40* | 20 | 800 | 36 | 6 | 216 | HBM3e 12hi | Hynix/Micron | 172,800 |
	| AWS | Trainium 3 | 100* | 17 | 1,700 | 36 | 4 | 144 | HBM3e 12hi | Hynix/Samsung/Micron | 244,800 |
	| Microsoft | Maia 200 | 4 | 29 | 116 | 16 | 4 | 64 | HBM3 | Samsung | 7,424 |
	| Microsoft | Maia 300 | 5 | 11 | 55 | 36 | 8 | 288 | HBM4 | Samsung | 15,840 |
	| **Total** | | **1,479** | | | | | | | | **4,034,885** |

	- \* Red in source — higher-uncertainty MS estimates

- ## Key Observations (Exhibit 31)
	- **NVIDIA dominates CoWoS allocation**: B300 alone consumes 390k wafers (26% of the 1,479k total); NVIDIA's three active products (B300 + Rubin R200 + H200) account for 725k wafers (49% of total)
	- **B300 is the HBM demand kingpin**: 1,572,480k GB demand — 39% of total 2026e HBM demand from a single product; HBM3e 12hi sourced across all three Korean suppliers
	- **HBM4 ramp visible**: Rubin R200 (NVIDIA) and MI400 (AMD) both on HBM4 in 2026e; Maia 300 (Microsoft) also on HBM4 — confirms HBM4 is not just a 2027 story
	- **Google's ASIC scale rivals AMD**: Google's three TPU products together demand 894,720k GB — larger than AMD's total GPU HBM demand of 311,904k GB
	- **AWS Trainium 3 is CoWoS-constrained**: 100k wafer allocation flagged in red (uncertain estimate); 4 HBM chip units per accelerator is the lowest among AI accelerators, reflecting Trainium's memory-efficient architecture
	- **Microsoft still small**: Maia 200 + Maia 300 combined = 23,264k GB — less than 0.1% of total; Samsung sole supplier for both, consistent with Microsoft's Samsung-first HBM relationship
	- **SK Hynix concentration in highest-demand products**: Hynix appears as primary vendor for B300, H200, and all Google TPUs — the highest-volume products; Samsung skews toward AMD and Microsoft (lower volume)
