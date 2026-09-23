- tags:: [[data-center]], [[capex]], [[infrastructure]], [[$NVDA]], [[$GOOGL]], [[networking]], [[power]]
  file-created-at:: 2026-05-02

- ## 1GW Data Center Cost Breakdown
	- **Primary source context**:
		- extracted from [2026-03-28-GTC 2026.md](/Users/hc/Logseq-github-Codex/pages/stock-memos/2026-03-28-GTC%202026.md)
		- attributed there to Jensen Huang commentary
	- **Core datapoint**:
		- a `1 gigawatt` AI factory / data center is estimated to cost roughly `$50B-$60B`
		- of that, roughly `$15B-$17B` is infrastructure:
			- land
			- power
			- shell
		- the remainder goes to technical equipment and systems

- ## Extracted Cost Breakdown

	| Component bucket | Low estimate | High estimate | Notes |
	|---|---:|---:|---|
	| Total 1GW factory cost | 50 | 60 | Stated estimate for a `1GW` AI factory / data center |
	| Infrastructure: land, power, shell | 15 | 17 | Explicitly identified in the source quote |
	| Implied remainder: compute, networking, storage, and related systems | 33 | 45 | Derived as total minus infrastructure |

- ## Derived Mix

	| Metric | Low-end case | High-end case | Notes |
	|---|---:|---:|---|
	| Infrastructure share of total cost | 30.0% | 28.3% | `15/50` on the low-end cost case and `17/60` on the high-end cost case |
	| Technical systems share of total cost | 70.0% | 75.0% | Complements the infrastructure share |

- ## Additional Independent Data Point
	- **Google SEC filing asset mix**:
		- approximately `60%` of technical infrastructure assets were comprised of servers and network equipment
		- the remaining balance, approximately `40%`, was comprised of data center land and buildings and related assets
	- **Why it matters**:
		- this provides a second lens on data center cost structure from an accounting / asset-mix perspective
		- it is directionally consistent with the idea that technical equipment is the majority of spend, while physical site and building assets are still a large but smaller share

- ## Interpretation
	- The Jensen-style estimate implies that for a `1GW` AI factory, the majority of total capital goes into technical systems rather than only into land and buildings.
	- On the extracted numbers, the non-infrastructure bucket is roughly `$33B-$45B`, which includes:
		- compute
		- networking
		- storage
		- other related systems
	- The Google filing datapoint is not a perfect apples-to-apples comparison because it describes asset composition rather than a greenfield `1GW` factory build quote, but it points in the same general direction: servers and networking dominate the technical asset base.

- ## Caveats
	- The source quote does **not** separately break out GPUs, CPUs, networking, and storage inside the `$33B-$45B` remainder.
	- The Google filing datapoint refers to the composition of technical infrastructure assets, not explicitly to total `1GW` greenfield project cost.
	- The two datapoints are best used together as directional framing, not as a fully normalized cost model.
