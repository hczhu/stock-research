- tags:: [[$MSFT]], [[Anthropic]], [[Claude]], [[AI training]], [[model scaling]], [[AI infrastructure]]
  file-created-at:: 2026-06-02

- ## Microsoft Slide: Claude Mythos Training Compute
	- **Source**:
		- user-provided screenshots
		- user-provided text context says Microsoft's slide implies `Claude Mythos` used `6.1 x 10^27 FLOPs` in training
		- the user also provided a `95% confidence interval` of `5.3 x 10^27` to `7.1 x 10^27 FLOPs`, assuming `1 px` measurement error
	- **Why this matters**:
		- if the estimate is directionally right, `Claude Mythos` sits materially above prior named frontier models on training compute
		- that supports the view that frontier scaling is still pushing demand into accelerators, networking, memory, and power infrastructure
	- **Caveat**:
		- only the `Claude Mythos` FLOPs estimate is explicitly supplied in text
		- most other values below are visual read-offs from the chart, so they should be treated as approximate rather than exact disclosures

- ## Chart 1 Table: Training Compute Frontier
	- The first chart plots notable models across time against training compute on a log scale.

| Model | Approx. year in chart | Approx. training FLOPs | Context |
| --- | --- | --- | --- |
| `AlexNet` | `2012` | `~5 x 10^17` | Early deep-learning landmark near the `10^17-10^18` range. |
| `AlphaGo Master` | `2018` | `~4 x 10^20` | Sits below `AlphaGo Zero` in the same time cluster. |
| `AlphaGo Zero` | `2018` | `~8 x 10^20` | Higher-compute AlphaGo point, close to the `10^21` line. |
| `GPT-3` | `2020` | `~5 x 10^23` | First large jump into the `10^23-10^24` regime among named LLMs. |
| `PaLM` | `2022` | `~1 x 10^25` | Roughly around the `10^25` line. |
| `GPT-4` | `2023` | `~4 x 10^25` | Above `PaLM`, still below the highest 2024-2026 cluster. |
| `Gemini Ultra` | `2024` | `~1.5 x 10^26` | One of the larger pre-2025 frontier points in the chart. |
| `Opus 4.6` | `2025` | `~7 x 10^26` | Plotted close to the top of the visible frontier before `Mythos`. |
| `Gemini 3.1 Pro` | `2025` | `~1.6 x 10^27` | Appears slightly above `Opus 4.6` in the top-right cluster. |
| `Claude Mythos` | `2026` | `6.1 x 10^27` | User-supplied estimate from the slide. `95% CI: 5.3 x 10^27 to 7.1 x 10^27`. |

- ## Chart 2 Table: Parameter Estimate vs Accuracy
	- The second chart plots `Penalized Accuracy (IKP Score)` against `log10(Total Parameters, Billions)`.
	- The right-hand labels provide parameter estimates for several closed models.
	- Accuracy values below are read from the dashed horizontal guides and point positions, so they are approximate.

| Model | Estimated total parameters | Approx. penalized accuracy (IKP) | Context |
| --- | --- | --- | --- |
| `Gemini 3.1 Pro` | `not shown` | `~0.81` | Marked as `landmark, excluded` from the regression line. |
| `GPT-5.5` | `9.7T` | `~0.72` | Highest explicit closed-model parameter estimate listed on the chart. |
| `Claude Opus 4.6` | `5.3T` | `~0.66` | Sits just below `GPT-5.5` on the closed-model score ladder. |
| `Claude Sonnet 4.6` | `1.7T` | `~0.61` | Mid-tier frontier closed-model estimate in the chart. |
| `Gemini 2.5 Pro` | `1.2T` | `~0.58` | Close to `Claude Sonnet 4.6` but slightly lower on the score axis. |
| `GPT-5 Mini` | `410B` | `~0.52` | Smallest listed `GPT-5` family point on the right-hand annotation set. |
| `Gemini 2.5 Flash` | `207B` | `~0.47` | Lower-parameter fast model entry in the same annotation group. |
| `Claude Haiku 4.5` | `65B` | `~0.40` | Smallest listed Claude model in the chart's right-hand estimates. |

- ## Read-Through
	- The two charts together suggest that frontier competition is still being fought on both axes:
		- more training compute
		- more total parameters
	- If `Claude Mythos` really trained at `~6.1 x 10^27 FLOPs`, that would place it well above the prior named points on the training-compute curve.
	- For stocks, the most direct beneficiaries of that trend remain the AI infrastructure stack:
		- accelerators
		- HBM and other memory
		- high-speed networking
		- data-center power and supporting system infrastructure

- ## Caveats
	- The screenshots do not provide a full methodology for how each plotted point was measured.
	- The parameter estimates in the second chart are presented as `est.` values rather than company disclosures.
	- The first chart's non-Mythos FLOPs values were visually approximated from the image and should be treated as rough order-of-magnitude anchors.
