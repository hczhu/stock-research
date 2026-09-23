- tags:: [[AI infrastructure]], [[GPU]], [[H100e]], [[$NVDA]], [[OpenAI]], [[Anthropic]], [[xAI]], [[$GOOGL]], [[$META]], [[compute]], [[capex]]
  file-created-at:: 2026-06-03

- ## Frontier Labs GPU Compute Capacity Share
	- **Source**:
		- user-provided Gradient Updates / Epoch AI article excerpt titled `Frontier labs don't use most AI compute (yet)`
		- the source says these estimates are more tentative than Epoch AI's standard data work
	- **Thesis**:
		- Frontier labs kicked off the AI compute boom, but they did not use most global AI compute as of end-`2025`.
		- `OpenAI`, `Anthropic`, and `xAI` likely had fewer than `4M` H100-equivalent GPUs (`H100e`) at end-`2025`, while global operational AI compute was roughly `12M-16M H100e` depending on deployment lag assumptions.
		- The key stock question is whether `OpenAI` and `Anthropic` can keep growing compute faster than the world supply base, or whether they run out of industry headroom and force either a broader capex acceleration or a frontier compute slowdown.
	- **Definitions**:
		- `H100e` means H100-equivalent compute, normalized by peak FLOP/s rather than literal H100 GPU count.
		- `Operational AI compute` means AI chips installed and available in data centers, not merely sold by chip vendors.

- ## End-2025 GPU Compute Capacity Estimates
	| Entity / group | End-2025 compute estimate | Power / capacity datapoint | Share context | Notes |
	| --- | ---: | ---: | --- | --- |
	| `OpenAI` | `~1.7M H100e` | `1.9 GW` | `~10-15%` of world operational AI compute by itself | Based on disclosed rented data-center power capacity converted to H100e. |
	| `Anthropic` | `>1.0M H100e` | `~1.4 GW` internal OpenAI memo estimate | Less than OpenAI but catching up | Includes Amazon Project Rainier and other AWS / Google capacity. |
	| `Anthropic Project Rainier` | `~500K H100e` | not separately stated | Subset of Anthropic compute | Trainium2 chips at Amazon's Indiana campus. |
	| `xAI` | `~600K-700K H100e` | Colossus 1 + 2 around `550K H100e` | Less than Anthropic and less than half of OpenAI | Includes Memphis Colossus sites plus possible smaller sites / prior Oracle use. |
	| `OpenAI + Anthropic + xAI` | `<4.0M H100e` | n/a | `~20-30%` of world operational AI compute under `12M-16M H100e` deployment assumptions | Dedicated frontier labs still do not dominate global compute. |
	| `Hyperscaler-hosted inference for OpenAI / Anthropic models` | up to `+5%` of world compute | n/a | Incremental to direct lab compute | Includes compute run by hyperscalers for APIs / hosted products. |
	| `Google total AI compute owned` | `~5.0M H100e` sold basis; `~4.0M H100e` with one-quarter deployment lag | n/a | Around one-quarter of world total by ownership estimate | Much of this goes to Google Cloud and non-frontier internal uses. |
	| `Google DeepMind` | likely `<50%` of Google's total AI compute | n/a | Unclear whether more than OpenAI | Source guesses non-DeepMind internal + Cloud uses keep DeepMind below half. |
	| `Meta total AI compute owned` | `~2.3M H100e` before deployment lag | n/a | Roughly `10%` of world AI compute | Split between frontier AI and recommender systems / core product workloads. |
	| `Meta Superintelligence Labs` | likely less than OpenAI at end-`2025` | n/a | Less than Meta's total owned compute | Meta began large external cloud deals in late `2025`, but those were still ramping. |
	| `Google + Meta total AI compute owned` | around one-third of world total | n/a | Frontier allocation likely only `~15%` of world compute | Parent-company compute is much larger than frontier-lab compute. |
	| `Five most resource-rich frontier developers` | `<50%` of global AI compute | n/a | Includes OpenAI, Anthropic, xAI, Google DeepMind, Meta Superintelligence Labs | Main conclusion: frontier labs do not yet use most AI compute. |

- ## Global AI Compute Supply Estimates
	| Metric | Estimate | Context |
	| --- | ---: | --- |
	| Cumulative sold AI compute by end-`2025` | `~20M H100e` | Based on cumulative AI chip sales. |
	| Operational AI compute with one-quarter deployment lag | `~16M H100e` | Uses Q3 `2025` sold compute as proxy for end-`2025` operational fleet. |
	| Operational AI compute with two-quarter deployment lag | `~12M H100e` | Longer installation lag means lower operational base and higher frontier-lab share. |
	| Estimated world total mentioned near article opening | `~20M H100e` | Broader reference to global AI computing power, before deployment-lag adjustment. |
	| New installed compute growth in `2025` vs `2024` | `2.7x` | Global new installed compute grew slower than OpenAI / Anthropic compute. |
	| Global AI compute stock growth in `2025` | `~3x` | Industry-wide installed base growth in H100e terms. |

- ## OpenAI Compute Trajectory
	| Year | OpenAI data-center power capacity | Estimated H100e compute | Growth context |
	| --- | ---: | ---: | --- |
	| `2023` | `0.2 GW` | `~100K H100e` | Early ChatGPT-scale infrastructure. |
	| `2024` | `0.6 GW` | `~400K H100e` | Power capacity roughly triples. |
	| `2025` | `1.9 GW` | `~1.7M H100e` | Another roughly `3x` power increase; H100e grows around `4x` due to hardware efficiency. |
	| `2026E` | n/a | n/a | Greg Brockman testified OpenAI would spend `$50B` on compute, roughly triple `2025` spend. |
	| `2027E` | `low double-digit GW`; example `~12 GW` | n/a | If `12 GW`, this implies roughly `2.5x` annual power-capacity growth from `2025`. |

- ## Anthropic And xAI Forward-Looking Compute Datapoints
	| Entity | Datapoint | Context |
	| --- | ---: | --- |
	| `Anthropic` | `~1.4 GW` at end-`2025` | Internal OpenAI memo estimate cited by the source. |
	| `Anthropic` | `>1M H100e` at end-`2025` | Source's bottom-line estimate. |
	| `Anthropic + OpenAI` | `5-6 GW each` by end-`2026` | Third-party forecast cited in the source. |
	| `Anthropic` | `1 GW` Trainium capacity targeted online in `2026` with Amazon | Part of April multi-GW expansion activity. |
	| `Anthropic` | up to `$15B/year` to rent xAI Colossus capacity | Includes Colossus 1 and part of Colossus 2. |
	| `Anthropic` | compute spending from `~$3B/quarter` in Q1 to `~$6B/quarter` in Q2 | Source frames this as a rapid spending ramp. |
	| `xAI Colossus 1 + 2` | `~550K H100e` at end-`2025` | Memphis sites. |
	| `xAI total` | `~600K-700K H100e` at end-`2025` | Includes smaller sites / cloud partner usage. |
	| `xAI Colossus 2 target` | `~1.4M H100e` | xAI target after renting Colossus 1 to Anthropic. |

- ## Headroom Scenario
	| Assumption | Result | Implication |
	| --- | --- | --- |
	| Top two labs have `20%` global compute share today | Starting point for illustration | Roughly aligns with OpenAI + Anthropic share estimates. |
	| Top two labs grow compute `33%` faster than world supply | Example: labs grow `4x/year`, world grows `3x/year` | Lab share doubles in about `2.5` years. |
	| Same relative-growth gap continues for `5` years | Top two labs reach `~80%` of world compute | Frontier labs would consume most industry headroom. |
	| More labs share the same growth race | Headroom runs out faster | If top `4-5` labs all scale aggressively, global supply becomes the binding constraint sooner. |
	| AI capex reaches `~$1T/year` in `2026-2027` | Around `1%` of gross world product and `3%` of U.S. GDP | Further acceleration would require dramatic economic changes or much stronger AI monetization. |

- ## Stock Implications
	- The article is bullish near term for `Nvidia`, accelerators, HBM, networking, and AI data-center suppliers because OpenAI and Anthropic are trying to grow compute faster than the global supply base.
	- The same analysis creates a medium-term constraint: once frontier labs absorb available headroom, their compute growth converges toward global compute production unless capex accelerates again.
	- This makes the sector sensitive to whether AI capex can move from nearly `$1T/year` toward a much larger run rate without breaking hyperscaler economics.
	- The compute distribution also matters for neoclouds and hyperscalers: large pools of compute not currently used by top labs may be bought, rented, repriced, or redirected as Anthropic and OpenAI consolidate demand.
	- For model labs, compute share becomes a strategic variable: revenue and funding growth translate directly into bargaining power for scarce GPU capacity.

- ## Memo Takeaway
	- Frontier labs do not yet use most AI compute, but OpenAI and Anthropic are growing fast enough that this could change within a few years.
	- The key data point is that OpenAI, Anthropic, and xAI likely had `<4M H100e` at end-`2025`, compared with roughly `12M-16M` operational H100e globally under deployment-lag assumptions.
	- The investment question is what happens when that slack disappears: either global AI compute production accelerates, frontier model scaling slows, or both.
