- tags:: [[xAI]], [[Colossus]], [[$NVDA]], [[GPU]], [[data-center]], [[power]], [[HBM]], [[Memphis]]

- ## xAI Colossus Memphis Expansion Timeline
	- **Source context**: user-provided chronology about xAI's Memphis data center buildout
	- **Scope**:
		- this memo only captures the figures explicitly stated in the provided text
		- where arithmetic is straightforward, derived metrics are broken out separately and labeled as derived
	- **Interpretation**:
		- the story is one of extremely rapid scaling from an already very large initial cluster
		- the disclosed roadmap shows expansion along four dimensions at once:
			- total GPU count
			- newer GPU mix
			- power draw / power capacity
			- physical and electrical self-sufficiency of the Memphis site

- ## Timeline Table

	| Date / phase | Facility scope | GPU count | GPU mix / type details | HBM / memory details | Power draw / capacity | Capex / site details | Other infrastructure notes |
	|---|---|---:|---|---|---|---|---|
	| Initial configuration | Initial Colossus configuration | 100,000 | Nvidia GPUs | Not specified | ~150 megawatts draw | Not specified | Baseline deployment |
	| Within 92 days | Facility doubled from the initial configuration | 200,000 | Included `50,000` Nvidia `H200` GPUs | H200 units had `141GB` of `HBM3e` each | ~250 megawatts draw | Not specified | Indicates very fast installation and power ramp |
	| Early 2026 | Colossus 1 alone | `>230,000` | Included `>30,000` Nvidia `GB200 Blackwell` chips | No per-chip HBM figure stated in the source text | Not specified | Not specified | Shows continued densification even before the full campus announcement |
	| January 2026 announcement | Expanded Memphis campus after acquiring a third building | 555,000 | Nvidia GPUs across the total facility | Not specified | `2 gigawatts` of power capacity | Third Memphis building acquired; GPU investment alone estimated at `$18 billion` | `2GW` described as enough to power about `1.5 million` homes |
	| March 5, 2026 filing | Planned building expansion at Memphis site | Not separately stated | Not separately stated | Not specified | Built around the full `2 gigawatt` load | `$659 million` building expansion; `79-acre` parcel at `5414 Tulane Road` | Direct liquid cooling, Tesla Megapacks, and an on-site gas-fired power plant for self-contained generation |

- ## Derived Metrics Table

	| Metric | Value | How it is derived | Relevance |
	|---|---:|---|---|
	| Initial power per GPU | `~1.5 kilowatts / GPU` | `150MW / 100,000 GPUs` | Rough indicator of the initial cluster power intensity |
	| Power per GPU after doubling | `~1.25 kilowatts / GPU` | `250MW / 200,000 GPUs` | Suggests scaling efficiency improved as the cluster expanded |
	| Incremental GPUs added in the first 92 days | `100,000` | `200,000 - 100,000` | Shows the speed of deployment |
	| H200 share of the 200,000-GPU configuration | `25%` | `50,000 / 200,000` | Indicates material mix shift toward higher-end accelerators |
	| Total HBM3e attached to the 50,000 H200s | `7,050,000 GB` | `50,000 x 141GB` | Raw memory footprint disclosed through the H200 configuration |
	| Total HBM3e attached to the 50,000 H200s | `~7.05 PB` | `7,050,000 GB / 1,000,000` | Easier way to interpret the same memory footprint at data-center scale |
	| GPU increase from initial configuration to January 2026 announced capacity | `455,000` | `555,000 - 100,000` | Highlights the magnitude of the long-range scale-up |
	| Capacity multiple from initial configuration to January 2026 announced capacity | `5.55x` | `555,000 / 100,000` | Captures how much larger the campus plan is versus the starting point |
	| Power capacity increase from initial draw to January 2026 campus capacity | `~13.3x` | `2,000MW / 150MW` | Shows power scaling required to support the broader buildout |

- ## Caveats
	- The source text mixes historical snapshots, an announcement, and a later filing, so not every row is directly comparable.
	- `Colossus 1` and the broader Memphis facility are not the same scope; the memo keeps those references separate instead of forcing them into one series.
	- No building square footage was stated in the provided text, so this memo does not add any footage estimate.
	- HBM capacity is only directly quantifiable for the `50,000` `H200` units because that is the only GPU memory figure explicitly provided.

- ## Additional Independent Data Point
	- **DRAM wafer intensity of a 1GW data center**:
		- seminar datapoint heard on `2026-04-29`: roughly `350,000` DRAM wafers are needed to build a single `1GW` data center
		- this is included as a separate reference point rather than merged into the timeline table because it is a generic infrastructure-intensity datapoint, not a dated xAI site milestone
