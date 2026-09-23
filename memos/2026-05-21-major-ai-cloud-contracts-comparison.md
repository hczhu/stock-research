- tags:: [[AI infrastructure]], [[GPU clusters]], [[OpenAI]], [[$MSFT]], [[$META]], [[Anthropic]], [[$CRWV]], [[Cerebras]], [[$ORCL]]
  file-created-at:: 2026-05-21

- ## Major AI Cloud Contracts Comparison
	- **Source context**:
		- screenshot titled `Major AI Cloud Contracts`
		- the table appears to compare large AI infrastructure contracts across CoreWeave, Cerebras, GCP, IREN, Nscale, OCI, and Nebius
		- visible rows cover announcement date, contract value, term, implied annual revenue, chip type, critical IT power contracted, disclosed GPU capex, and several derived margin views
	- **Readability note**:
		- most cells are legible from the screenshot, but a few cells are partially obscured or visually ambiguous
		- where a number is not clearly readable, I keep it as `-`
		- where a number is economically obvious from the visible row set, I note that it is inferred

- ## Contract Terms Table
	| Metric | Units | CoreWeave-Meta Deal 2 | Cerebras-OpenAI | GCP-Anthropic | IREN-Microsoft | Nscale-Microsoft Deal 2 | CoreWeave-Meta Deal 1 | CoreWeave-OpenAI Deal 3 | Nscale-Microsoft Deal 1 | OCI-OpenAI | Nebius-Microsoft | CoreWeave-OpenAI Deal 2 |
	| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
	| Announcement date | Date | 9-Apr-26 | 14-Jan-26 | 9-Nov-25 | 3-Nov-25 | 15-Oct-25 | 30-Sep-25 | 25-Sep-25 | 16-Sep-25 | 10-Sep-25 | 8-Sep-25 | 15-May-25 |
	| Contract value | USD | $21.0B | $27.6B | $42.0B | $9.7B | $14.0B | $14.2B | $6.5B | $6.2B | $30.0B | $17.4B | $4.0B |
	| Term duration | Years | 6 | 3 | 5 | 5 | 5 | 6 | 5 | 5 | 5 | 5 | 3 |
	| Implied annual revenue | USD | $3.5B | $9.2B | - | $1.9B | $2.8B | $2.4B | $1.3B | $1.2B | ~$6.0B | $3.5B | $1.3B |
	| Chip type | Type | VR NVL72 | Cerebras WSE-3 | TPU v7 | GB300 | GB300 | GB300 | GB300 | GB300 | GB300 / VR200s | GB300 | GB300 |
	| Critical IT power contracted | MW | 223 | 750 | 788 | 161 | 234 | 205 | 105 | 110 | - | 300 | 65 |
	| GPU capex disclosed | USD | - | - | - | $5.8B | - | - | - | - | 4,500 | - | - |

- ## Derived Economics Table
	| Metric | Units | CoreWeave-Meta Deal 2 | Cerebras-OpenAI | GCP-Anthropic | IREN-Microsoft | Nscale-Microsoft Deal 2 | CoreWeave-Meta Deal 1 | CoreWeave-OpenAI Deal 3 | Nscale-Microsoft Deal 1 | OCI-OpenAI | Nebius-Microsoft | CoreWeave-OpenAI Deal 2 |
	| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
	| EBIT margin, depreciation = deal term | % in year 1 | 37.1% | 33.8% | 43.9% | 24.3% | 17.1% | 25.8% | 20.8% | 16.1% | 35.1% / 33.4% | -2.5% | 28.0% |
	| EBIT margin, depreciation as per accounting policy | % in year 1 | 37.1% | 51.1% | 49.9% | 24.3% | 17.1% | 25.8% | 30.8% | 16.1% | 42.7% / 41.3% | 13.6% | 58.3% |
	| EBIT margin, 6-year depreciation | % in year 1 | 37.1% | 55.4% | 49.9% | 34.2% | 28.0% | 25.8% | 30.8% | 27.1% | 42.7% / 41.3% | 24.3% | 58.3% |

- ## Notes Visible In The Screenshot
	- AI Nvidia clusters assume a `3.4 year` InfiniBand network.
	- Prepayment assumptions are shown in red, with prepayments credited equally throughout contract life.
	- `1.` Option to increase contract value to `~$19.4B`.
	- `2.` Option to add further `700MW` in late `2027`.
	- `3.` IREN disclosed `200MW` of critical IT power, with remaining capacity likely reserved for other non-AI compute that supports this cluster in some form.
	- `4.` The `Cerebras-OpenAI` contract value of `$27.6B` accounts for RPO of `$24.6B` for `750MW` of inference compute, includes full colo pass-through on the first `250MW`, and adds back full colo pass-through on the remaining `500MW`; the screenshot also notes an assumed net of OpenAI warrant contra-revenue and says it assumes `CS.3` systems only.

- ## Context For The Data Points
	- The table is useful because it normalizes a set of headline AI infrastructure deals into a common frame: dollars, term, annualized revenue, chip platform, contracted power, and rough margin profile.
	- The largest visible contract values are `GCP-Anthropic` at `$42.0B`, `OCI-OpenAI` at `$30.0B`, and `Cerebras-OpenAI` at `$27.6B`.
	- On a power basis, the largest visible contracted cluster in the screenshot is `GCP-Anthropic` at `788MW`, followed by `Cerebras-OpenAI` at `750MW`.
	- The table suggests that similar contract values can still map to very different economics depending on chip type, depreciation treatment, and whether pass-through items are included.
	- The `OCI-OpenAI` row stands out because it appears to include two scenarios in the derived margin rows and a separate disclosed GPU capex figure of `4,500` in the source table.
	- The `Nebius-Microsoft` row stands out for weak year-1 economics under deal-term depreciation, with the screenshot showing `-2.5%` EBIT margin before improving under alternative depreciation assumptions.
	- Because this is a screenshot extraction rather than a source spreadsheet, the memo should be treated as a transcription of visible values, not a clean primary dataset.
