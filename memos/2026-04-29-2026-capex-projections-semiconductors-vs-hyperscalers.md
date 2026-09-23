- tags:: [[capex]], [[hyperscalers]], [[semiconductor]], [[$MSFT]], [[$META]], [[$GOOGL]], [[$AMZN]], [[$TSM]], [[$005930.KS]], [[$MU]], [[$000660.KS]]
  file-created-at:: 2026-04-29

- ## 2026 Capex Projections: Semiconductor Companies vs Hyperscalers
	- **Source memos**:
		- [2026-04-16-semiconductor-capital-expenditures-2024-2026.md](/Users/hc/Logseq-github-Codex/pages/stock-memos/2026-04-16-semiconductor-capital-expenditures-2024-2026.md)
		- [2026-04-29-us-big-4-tech-capex-projections-2026.md](/Users/hc/Logseq-github-Codex/pages/stock-memos/2026-04-29-us-big-4-tech-capex-projections-2026.md)
	- **Scope**:
		- this memo charts `2026` capex projections for named semiconductor companies and the US Big 4 hyperscalers
		- all figures are in **US$ billions**
	- **Method**:
		- semiconductor figures are direct `2026` company values from the semiconductor capex memo
		- hyperscaler figures use low/high ranges where ranges were provided
		- single-point hyperscaler figures are shown as the same value on both the low and high series
		- segment totals and `Others` rows are excluded so the chart focuses on named companies

- ## Semiconductor Companies Chart

```mermaid
xychart-beta
    title "2026 Capex Projections: Named Semiconductor Companies"
    x-axis ["TSMC","Samsung","SK Hynix","Micron","Intel","SMIC","Infineon","Terrafab","Texas Instruments","STMicroelectronics","UMC","GlobalFoundries"]
    y-axis "US$ bn" 0 --> 60
    bar [54.0,40.0,27.4,20.0,17.7,8.1,3.1,3.0,2.5,2.1,1.5,1.2]
```

- ## Hyperscalers Chart

```mermaid
xychart-beta
    title "2026 Capex Projections: Big 4 US Hyperscalers"
    x-axis ["Amazon","Microsoft","Google","Meta"]
    y-axis "US$ bn" 0 --> 220
    bar "Low" [200,190,180,125]
    bar "High" [200,190,190,145]
```

- ## Combined 2026 Table

	| Category | Company | 2026 capex low | 2026 capex high | Notes |
	|---|---|---:|---:|---|
	| Hyperscaler | Amazon | 200 | 200 | Reaffirmed record plan at roughly `US$200B`. |
	| Hyperscaler | Microsoft | 190 | 190 | Guidance above prior `US$150B` estimate. |
	| Hyperscaler | Google | 180 | 190 | Raised range and flagged significant `2027` increase. |
	| Hyperscaler | Meta | 125 | 145 | Raised range on component costs and data center buildouts. |
	| Semiconductor | TSMC | 54.0 | 54.0 | Largest named semiconductor-company capex in the source memo. |
	| Semiconductor | Samsung | 40.0 | 40.0 | Largest memory-company capex in the source memo. |
	| Semiconductor | SK Hynix | 27.4 | 27.4 | Strong memory upcycle / AI-linked capex expansion. |
	| Semiconductor | Micron (FYE Sep.) | 20.0 | 20.0 | Large step-up versus `2025`. |
	| Semiconductor | Intel | 17.7 | 17.7 | Flat versus `2025` in the source memo. |
	| Semiconductor | SMIC | 8.1 | 8.1 | Flat in `2026` versus `2025`. |
	| Semiconductor | Infineon (FYE Sep.) | 3.1 | 3.1 | Rebounds from `2025`. |
	| Semiconductor | Terrafab | 3.0 | 3.0 | Only `2026` value was shown in the original screenshot-based memo. |
	| Semiconductor | Texas Instruments | 2.5 | 2.5 | Meaningful cut versus prior years. |
	| Semiconductor | STMicroelectronics | 2.1 | 2.1 | Small rebound from `2025`. |
	| Semiconductor | UMC | 1.5 | 1.5 | Down slightly versus `2025`. |
	| Semiconductor | GlobalFoundries | 1.2 | 1.2 | Small in absolute dollars despite high growth rate. |

- ## Quick Comparisons
	- The hyperscaler spending scale is an order of magnitude larger than individual semiconductor-company capex.
	- Even the lowest Big 4 hyperscaler in the range, [[$META]] at `US$125B`, is still more than `2x` [[$TSM]]'s `US$54B` projected capex.
	- [[$AMZN]] plus [[$MSFT]] alone imply roughly `US$390B` of `2026` capex, which exceeds the full `US$200B` `2026` semiconductor-industry total shown in the semiconductor memo.
	- Within semiconductors, [[$TSM]], [[$005930.KS]], [[$000660.KS]], and [[$MU]] are the dominant named capex spenders in the source dataset.

- ## 2027 Hyperscaler Capex Outlook — Consensus vs Bull Case
	- **Source**: user-provided estimate; argues consensus 2027 hyperscaler capex is **too conservative**.
	- All figures aggregate **total hyperscaler** capex (broader than the Big-4-only ~`US$695-725B` 2026 base in [[2026-04-29-us-big-4-tech-capex-projections-2026]]).

	| Scenario | 2027 hyperscaler capex | YoY growth | Basis |
	|---|---:|---:|---|
	| Consensus (analyst estimates) | **~$920B** | **+22%** | Implies a sharp deceleration from **+84% in 2026** |
	| Bull case (this estimate) | **~$1.1T** | **+45%** | Incremental investment reaching **2-3% of GDP**, similar to the railroad and auto build-outs |

	- **Implied 2026 base ≈ $754-759B** (consistent across both scenarios: $920B ÷ 1.22 ≈ $754B; $1.1T ÷ 1.45 ≈ $759B), itself up ~84% on 2025 (~$410B).
	- **The debate is the growth rate, not the level**: consensus has 2027 growth collapsing to +22% right after a +84% 2026; the bull case says a GDP-anchored build-out keeps growth near +45%, a **~$180B gap** ($1.1T vs $920B) in a single year.
	- **Read-through**: a +45% vs +22% 2027 outcome is the swing factor under the AI-infra/memory demand theses — the difference between a decelerating and a still-accelerating capex cycle ([[2026-05-24-ai-data-center-buildout-capacity-and-spend-scenario]], [[2026-06-10-morgan-stanley-hyperscaler-capex-accounting-risk]]).

- ## Caveats
	- The two source memos do not represent the same economic layer: one tracks semiconductor manufacturers, the other tracks cloud / platform operators.
	- Hyperscaler figures include broader data center and infrastructure spending, not just chip-related capex.
	- [[$META]] and [[$GOOGL]] are ranges; the chart shows both low and high values rather than forcing a midpoint.
