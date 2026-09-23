- tags:: [[HBM]], [[GPU]], [[AI infrastructure]], [[$NVDA]], [[$AMD]], [[Cerebras]], [[Groq]]
  file-created-at:: 2026-05-21

- ## HBM Perf Ratio: Cerebras vs Others (Chips)
	- **Source context**:
		- screenshot titled `Cerebras vs Others (chips)`
		- the table compares low-precision compute throughput, HBM capacity / bandwidth, SRAM capacity / bandwidth, and derived performance ratios across several AI chips
		- the screenshot footnote says `perf ratio` is also known as `Arithmetic Intensity`, defined as `FLOPs / bw`
	- **What `HBM perf ratio` means**:
		- `HBM perf ratio = compute throughput / HBM bandwidth`
		- in practice, it measures how much compute a chip is trying to drive per unit of HBM bandwidth
		- a higher ratio means the chip has more compute relative to external memory bandwidth, so it is easier for real workloads to become HBM-bandwidth-bound unless they have high data reuse, strong batching, or effective SRAM usage
		- a lower ratio means the chip has more HBM bandwidth relative to compute, which makes it easier to keep the compute units fed

- ## Table
	| Chip | FP16 or BF16 perf | FP8 or INT8 perf | FP4 perf | HBM capacity | HBM bandwidth | HBM perf ratio | SRAM capacity | SRAM bandwidth | SRAM perf ratio |
	| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
	| H100 | 0.989 PFLOPS | 1.979 PFLOPS | - | 80 GB | 3.35 TB/s | 591 | 50 MB | 12.8 TB/s | 155 |
	| H200 | 0.989 PFLOPS | 1.979 PFLOPS | - | 141 GB | 4.80 TB/s | 412 | 50 MB | 12.8 TB/s | 155 |
	| B200 | 2.25 PFLOPS | 4.5 PFLOPS | 9 PFLOPS | 192 GB | 8 TB/s | 1125 | 126 MB | 20 TB/s | 450 |
	| B300 | 2.25 PFLOPS | 4.5 PFLOPS | 13.5 PFLOPS | 288 GB | 8 TB/s | 1688 | 126 MB | 20 TB/s | 675 |
	| Cerebras WSE-3 | 15.625 PFLOPS | 15.625 PFLOPS | - | - | - | - | 44 GB | 21000 TB/s | 0.74 |
	| Groq LP30 | 0.6 PFLOPS | 1.2 PFLOPS | - | - | - | - | 500 MB | 150 TB/s | 8 |
	| R200 | 4 PFLOPS | 17.5 PFLOPS | 35 PFLOPS | 288 GB | 13 TB/s | 2692 | ? | ? | ? |

- ## Interpreting The Data Points
	- The visible ratios imply the table is using the highest relevant low-precision compute mode available for each chip when calculating `HBM perf ratio`.
	- Example calculations from the screenshot:
		- `H100`: `1.979 PFLOPS / 3.35 TB/s = 591`
		- `H200`: `1.979 / 4.80 = 412`
		- `B200`: `9 / 8 = 1125`
		- `B300`: `13.5 / 8 = 1688`
		- `R200`: `35 / 13 = 2692`
	- `H200` lowers the HBM perf ratio versus `H100` because compute is similar but HBM bandwidth rises from `3.35 TB/s` to `4.80 TB/s`. That means H200 is less memory-starved at the same low-precision throughput.
	- `B200`, `B300`, and especially `R200` show much higher HBM perf ratios. That suggests their delivered performance depends more heavily on:
		- keeping data resident in SRAM or cache
		- increasing batching
		- raising arithmetic intensity
		- minimizing repeated HBM fetches
	- `B300` raises the ratio further than `B200` because FP4 compute rises from `9 PFLOPS` to `13.5 PFLOPS` while HBM bandwidth remains `8 TB/s`.
	- `R200` is the most compute-dense relative to HBM in the table, at `2692`, which means it likely requires the most favorable software and workload characteristics to avoid HBM bottlenecks.

- ## Stock Memo Context
	- For HBM suppliers, the key takeaway is that newer AI accelerators are not simply adding compute. They are often adding compute faster than HBM bandwidth, which increases the pressure on memory hierarchy design and keeps HBM strategically important.
	- For GPU vendors, a rising HBM perf ratio can be positive if software, batching, and cache hierarchy improvements are strong enough to unlock the added compute. If not, some of the theoretical compute uplift will be stranded behind memory constraints.
	- For alternative architectures such as Cerebras and Groq, the table is implicitly arguing that very large on-chip SRAM pools and extremely high SRAM bandwidth are a different way to attack the same bottleneck.
	- Missing entries in the screenshot should be treated as unavailable source data, not zeros.
