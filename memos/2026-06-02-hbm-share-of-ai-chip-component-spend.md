- tags:: [[HBM]], [[DRAM]], [[AI infrastructure]], [[$NVDA]], [[$AMD]], [[$GOOGL]], [[$AMZN]], [[$MSFT]], [[$META]], [[semiconductor]]
  file-created-at:: 2026-06-02

- ## HBM Share Of AI Chip Component Spend
	- **Source**:
		- user-provided screenshot from `Epoch AI | CC-BY`
		- accurate source data added in `data/ai-chip-component-cost-shares-by-quarter.csv`
		- chart title: `Average share of total component cost`
		- screenshot text says the estimates are averages across AI chips designed by `Nvidia`, `AMD`, `Google`, and `Amazon`, weighted by production volume
	- **Context**:
		- the chart splits AI chip component spending into `Memory`, `Logic`, `Packaging`, and `Auxiliary`
		- the key message is that HBM is taking more of the AI chip bill of materials while packaging and auxiliary shares fall
		- the screenshot states HBM grew from `52%` to `63%` of total AI chip component spending between `Q1 2024` and `Q4 2025`
	- **Caveat**:
		- quarterly component shares and dollar costs come from the CSV source data
		- screenshot text is used for qualitative context and hyperscaler capex comments

- ## Extracted Component Cost Share Table
	| Quarter | Memory / HBM share | Logic share | Advanced packaging share | Auxiliary share | HBM cost | Total component cost |
	| --- | ---: | ---: | ---: | ---: | ---: | ---: |
	| `Q1 2024` | `51.87%` | `14.16%` | `18.89%` | `15.08%` | `$1.68B` | `$3.23B` |
	| `Q2 2024` | `54.04%` | `13.61%` | `18.15%` | `14.20%` | `$2.31B` | `$4.27B` |
	| `Q3 2024` | `55.90%` | `13.77%` | `17.96%` | `12.37%` | `$3.34B` | `$5.97B` |
	| `Q4 2024` | `56.52%` | `14.45%` | `17.82%` | `11.20%` | `$4.81B` | `$8.50B` |
	| `Q1 2025` | `56.16%` | `14.29%` | `17.20%` | `12.35%` | `$5.53B` | `$9.85B` |
	| `Q2 2025` | `58.52%` | `14.03%` | `16.74%` | `10.71%` | `$6.28B` | `$10.74B` |
	| `Q3 2025` | `61.29%` | `13.26%` | `15.75%` | `9.71%` | `$8.72B` | `$14.23B` |
	| `Q4 2025` | `63.42%` | `12.93%` | `14.82%` | `8.83%` | `$11.00B` | `$17.35B` |

- ## Key Data Points
	| Data point | Value | Context |
	| --- | ---: | --- |
	| HBM share of AI chip component spend, `Q1 2024` | `51.87%` | Starting share from the CSV. |
	| HBM share of AI chip component spend, `Q4 2025` | `63.42%` | Ending share from the CSV. |
	| HBM share increase | `+11.55 pp` | `63.42% - 51.87%`. |
	| Logic die share change | `14.16%` to `12.93%` | Logic stays roughly flat, down only `1.23 pp` across the period. |
	| Advanced packaging share change | `18.89%` to `14.82%` | Packaging declined by `4.07 pp`. |
	| Auxiliary component share change | `15.08%` to `8.83%` | Auxiliary declined by `6.25 pp`. |
	| HBM spend across Nvidia, AMD, Google, and Amazon chips in `2024` | `$12.13B` | Sum of quarterly memory cost in the CSV. |
	| HBM spend across Nvidia, AMD, Google, and Amazon chips in `2025` | `$31.54B` | Sum of quarterly memory cost in the CSV. |
	| HBM spend growth, `2024` to `2025` | `+$19.41B`, `2.60x`, `160%` | Faster year-over-year increase than any other component per screenshot text. |
	| Total component cost, `2024` | `$21.98B` | Sum of quarterly total component cost in the CSV. |
	| Total component cost, `2025` | `$52.17B` | Sum of quarterly total component cost in the CSV. |
	| Microsoft FY2026 capex outlook | `$190B` | Screenshot says about `$25B` of this reflects higher component prices. |
	| Microsoft capex impact from higher component prices | `~$25B` | Hyperscaler capex sensitivity to component inflation. |
	| Meta 2026 capex range increase | `+$10B` | Screenshot says Meta raised its 2026 capex range by `$10B`, citing higher component prices. |

- ## NVL72 Rack-Level BOM: Memory Share by GPU Generation (Exhibit 46)
	- **Source**: Morgan Stanley Research estimates
	- **Headline**: Memory will exceed 25% of the NVL72 rack BOM for Rubin (VR200) — up from 7% on GB200 — as HBM price inflation combines with higher per-GPU HBM content

	| Component | GB200 NVL72 | GB300 NVL72 | VR200 NVL72 |
	|---|---:|---:|---:|
	| GPU | 65% | 63% | 51% |
	| Memory | 7% | 9% | **26%** |
	| Other networking chips | 5% | 7% | 7% |
	| CPU | 5% | 5% | 3% |
	| NVLink Switch chip | 2% | 2% | 2% |
	| Cooling | 2% | 2% | 1% |
	| Power supply | 1% | 1% | 1% |
	| PCB | 1% | 1% | 1% |
	| Others | 11% | 10% | 8% |
	| Rack assembly value add | 1% | 1% | 0% |
	| ABF Substrate | 0% | 0% | 0% |
	| MLCC | 0% | 0% | 0% |

	- Memory's rack BOM share: **7% (GB200) → 9% (GB300) → 26% (VR200)** — a 3.7× increase across two GPU generations
	- GPU's rack BOM share compresses from 65% → 51% as memory inflation dilutes compute's dominance in total system cost
	- The VR200 data point (26%) aligns with the Exhibit 30 figure cited elsewhere: memory jumped from 9.4% (GB300) to 25.7% (VR200) per Morgan Stanley estimates
	- This is a rack-level complement to the chip-level data above: at the chip level HBM is 63% of component cost; at the rack level it is 26% of total system BOM — both moving in the same direction

- ## Stock Implications
	- The component mix shift is directly bullish for `HBM` suppliers because memory is becoming a larger share of AI accelerator cost, not just growing with unit volumes.
	- The jump from roughly `$12B` of HBM spend in `2024` to `$32B` in `2025` suggests both volume growth and pricing / mix uplift.
	- Logic share staying roughly flat near `13%` means the marginal cost pressure in AI accelerators is not only about compute dies.
	- Packaging remains strategically important, but its share falling from `19%` to `15%` implies HBM is absorbing more of the bill-of-materials expansion.
	- The capex comments from `Microsoft` and `Meta` tie component inflation directly into hyperscaler budget revisions, which matters for cloud gross margins and AI infrastructure supply-chain pricing power.

- ## Memo Takeaway
	- The chart's core point is that HBM is becoming the dominant and still-growing cost bucket inside leading AI chips.
	- For stock work, this supports a memory-cycle thesis where HBM demand is driven by three forces at once:
		- AI chip unit growth
		- higher HBM content per chip
		- tight memory supply and rising component prices
