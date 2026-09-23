- tags:: [[AI]], [[inference]], [[$NVDA]], [[GB200]], [[GB300]], [[H100]], [[throughput]], [[interactivity]], [[SemiAnalysis]]
  file-created-at:: 2026-05-20

- ## Token Throughput per GPU vs. Interactivity
	- **Source context**:
		- chart title: `Token Throughput per GPU vs. Interactivity`
		- model / test setup shown: `DeepSeek R1 0528 · FP4, FP8 · 8K / 1K`
		- source shown in chart: `SemiAnalysis InferenceMAX™`
		- update date shown in chart: `02/14/2026`
	- **What the chart is showing**:
		- `y-axis`: token throughput per GPU (`tok/s/GPU`)
		- `x-axis`: interactivity (`toks/user`)
		- the chart compares newer `GB200/GB300 NVL72` inference systems against an `H100 Disagg+WideEP FP8` baseline
	- **Important caveat**:
		- the screenshot does not expose hover tooltips or raw exported data
		- the tables below therefore separate:
			- exact values explicitly printed on the chart
			- approximate curve points visually read from the screenshot
		- the small numeric labels next to points are preserved as shown where possible, but the screenshot does not define what those labels represent

- ## Exact Chart Annotations

	| Field | Value | Context |
	|---|---:|---|
	| Model | DeepSeek R1 0528 | Printed directly under the chart title |
	| Precision modes shown | FP4, FP8 | Printed in the subtitle |
	| Context / request setting shown | 8K / 1K | Printed in the subtitle |
	| Source | SemiAnalysis InferenceMAX™ | Printed in the subtitle |
	| Update date | 02/14/2026 | Printed in the subtitle |
	| Annotated comparison multiple | 20.2x | Orange callout between the top NVL72 FP4 curve and the H100 baseline at low interactivity |
	| Annotated comparison multiple | 79.3x | Orange callout at a mid-interactivity operating point |
	| Annotated comparison multiple | 100.5x | Orange callout at another mid-interactivity operating point |

- ## Approximate Representative Curve Points

	| System / curve | Interactivity (toks/user) | Throughput (tok/s/GPU) | Visible point label | Confidence / note |
	|---|---:|---:|---:|---|
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~28 | ~18,000 | 28 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~42 | ~14,500 | 42 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~56 | ~13,100 | 44 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~95-100 | ~12,000 | 36 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~120 | ~9,000 | 64 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~150 | ~7,000 | 48 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~160 | ~5,000 | 40 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~195-200 | ~1,500 | 26-28 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~220 | ~1,100 | 36 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~245 | ~900 | 34 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~280-290 | ~600-700 | 36 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP4 (upper dark-circle curve) | ~310 | ~450-500 | 34 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~36 | ~8,600 | 36 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~56 | ~8,400 | 56 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~90 | ~7,600 | 48 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~120 | ~6,300 | 64 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~145 | ~4,800 | 56 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~165 | ~700-900 | 40 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~195-200 | ~500-600 | 26 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~220 | ~350-400 | 32 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~245 | ~200-300 | 36 | Approximate from chart grid |
	| GB200/GB300 NVL72 FP8 (upper dark-square curve) | ~290-300 | ~80-120 | 36 | Approximate from chart grid |
	| H100 Disagg+WideEP FP8 (baseline lower curve) | ~48 | ~900 | 48 | Approximate from chart grid |
	| H100 Disagg+WideEP FP8 (baseline lower curve) | ~64 | ~150-200 | 64 | Approximate from chart grid |
	| H100 Disagg+WideEP FP8 (baseline lower curve) | ~114-120 | ~90-120 | 64 | Approximate from chart grid |

- ## Context For The Data Points
	- The chart’s basic message is that `GB200/GB300 NVL72` systems deliver materially higher token throughput per GPU than the `H100 Disagg+WideEP FP8` baseline, especially at low-to-mid interactivity.
	- The orange callouts (`20.2x`, `79.3x`, `100.5x`) are the cleanest explicit comparison datapoints in the screenshot and indicate very large throughput advantages at selected operating points.
	- All visible curves slope downward as interactivity rises, which implies that throughput per GPU falls as workloads become more interactive and less batch-friendly.
	- The `FP4` NVL72 curve is the highest visible family, the `FP8` NVL72 curve sits below it, and the `H100` baseline is much lower still.
	- At the far right of the chart, the gap narrows in absolute throughput terms because all systems are operating in a much more interactive regime where batching efficiency is weaker.

- ## Interpretation
	- The chart is supportive of the view that `GB200/GB300 NVL72` systems materially improve inference economics and utilization relative to older `H100`-class disaggregated setups.
	- The largest gains appear in workloads where the system can still preserve some batching / throughput efficiency rather than operating in the most latency-sensitive regime.
	- For the memory and networking stack, this type of chart is indirectly bullish because the advantage is being expressed at the system level, not just at raw chip spec level.
