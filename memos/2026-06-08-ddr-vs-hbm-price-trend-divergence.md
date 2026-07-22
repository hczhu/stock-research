- tags:: [[HBM]], [[DRAM]], [[semiconductor]], [[GPU]], [[AI-infrastructure]], [[capex]]

- **Source**: User-provided chart, 2026-06-08, comparing HBM3e and DDR4 cost per capacity and bandwidth over time.

- ## Extracted Chart Data
	- Exact point values are estimated visually from the provided chart, so treat them as directional rather than source-grade measurements.

	| Product | Period | $/GB capacity trend | $/GBps bandwidth trend | Directional read |
	|---|---|---:|---:|---|
	| HBM3e | Q4-23 → Q4-25 | roughly **$15/GB → $21/GB** | roughly **$0.29/GBps → $0.42/GBps** | Both capacity and bandwidth costs rise steadily |
	| DDR4 | 2022 → 2025 | roughly **$3/GB → $1.5-1.7/GB** | roughly **$4.5/GBps → $2/GBps** | Both trend down, with cyclical volatility |

- ## Why HBM Prices Rise While DDR Prices Fall
	- **DDR is a mature commodity market**. DDR4 is standardized, produced at scale, and sold into broad PC/server channels where vendors compete mostly on cost per bit. As nodes mature, yields improve, depreciation rolls through, and inventory cycles force price declines. Even when DDR prices spike, the long-term trend is deflationary because supply is more fungible and customers can switch suppliers more easily.
	- **HBM is not just DRAM bits**. HBM is a vertically stacked memory subsystem that requires TSVs, microbumps or hybrid bonding, base dies, thermal engineering, known-good-die sorting, and tight integration with advanced packaging. Each added die in the stack creates yield loss and assembly complexity. Cost does not fall simply because DRAM bit density improves.
	- **HBM bandwidth is physically scarce**. AI accelerators are memory-bandwidth constrained, and the only practical way to feed large GPUs is to place high-bandwidth memory very close to compute. That makes HBM a system bottleneck, not a commodity component. Customers pay for GPU utilization, training throughput, and inference economics, so the willingness to pay is tied to accelerator ROI rather than standalone memory cost.
	- **Qualification limits substitutability**. DDR modules are broadly interchangeable. HBM stacks are qualified by accelerator generation, packaging flow, capacity, thermals, and supplier-specific yield. SK Hynix, Samsung, and Micron are not perfectly substitutable at a given NVIDIA/AMD/ASIC socket, especially around HBM3E/HBM4 ramps.
	- **Supply additions are slow and expensive**. HBM capacity requires not only wafer starts but also advanced packaging capacity, stack assembly, test, and customer qualification. Even if DRAM wafer supply exists, it cannot instantly become qualified HBM output. That makes HBM supply response slower than DDR supply response.
	- **DDR demand is broad but cyclical; HBM demand is narrow but urgent**. DDR demand depends on PCs, servers, and general cloud capex. HBM demand is pulled by frontier AI accelerators where memory shortage can bottleneck multi-billion-dollar compute deployments. Narrow, urgent demand can support premium pricing if supply is constrained.

- ## Investment Implications
	- **Bullish for memory de-commoditization**: HBM price inflation supports the view that the AI memory cycle can produce structurally better margins than prior DRAM cycles.
	- **Bullish for SK Hynix leadership**: if HBM remains qualification- and yield-constrained, the leader with the best HBM3E/HBM4 execution captures outsized value.
	- **Samsung and Micron are recovery/qualification stories**: their upside depends less on generic DRAM bit supply and more on earning qualified high-volume sockets for HBM3E/HBM4.
	- **Packaging bottlenecks matter**: HBM economics will increasingly depend on advanced packaging ecosystems, not only memory wafer capacity.
	- **Commodity DRAM bear case remains separate**: DDR price deflation can coexist with HBM price inflation. A memory thesis should separate premium AI HBM from commodity DDR/PC/server DRAM rather than treating all DRAM as one cycle.

- ## What Would Break This View
	- HBM suppliers overbuild stack and packaging capacity faster than AI accelerator demand grows.
	- HBM4 standardization makes suppliers much more interchangeable and compresses qualification premiums.
	- Inference architectures reduce HBM intensity through KV-cache offload, flash tiers, SRAM-heavy designs, compression, or model-architecture changes.
	- GPU supply becomes less constrained than HBM supply, reducing the urgency premium customers pay for memory bandwidth.
