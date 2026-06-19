- tags:: [[GPU]], [[$NVDA]], [[neocloud]], [[AI-compute]], [[data-center]], [[TCO]], [[H200]], [[capex]], [[SemiAnalysis]], [[AI]], [[inference]]

- **Source**: SemiAnalysis AI TCO Model — H200 SXM (InfiniBand), "Neocloud Giant" customer profile.

- **Thesis**: All-in cost to own and operate an H200 GPU is **\$1.59/hr/GPU**, of which **72.5% is capital cost** and only 27.5% is operating cost. The economics are dominated by the upfront server purchase (71% of cluster capex), so GPU rental pricing and depreciation assumptions — not electricity — drive neocloud unit economics.

- ## Headline: Total Cost of Ownership per GPU-Hour

	- | Component | Value | Share of TCO |
	  |---|---|---|
	  | Capital cost per GPU-hour | \$1.15 | 72.5% |
	  | Operating cost per GPU-hour | \$0.44 | 27.5% |
	  | **Total cost per GPU-hour** | **\$1.59** | 100% |
	- Implication: at a typical neocloud rental rate, the spread over \$1.59/hr is the gross margin. Capital cost dominance means **utilization and the entry price of the server** are the two biggest levers on profitability, far more than power cost.

- ## Capital Cost Breakdown (per 8-GPU server)

	- | Line item | USD per server | Notes |
	  |---|---|---|
	  | Server cost | \$258,001 | ~71% of total upfront capex — the GPU server itself |
	  | Networking cost | \$76,155 | InfiniBand fabric |
	  | Storage cost | \$11,732 | |
	  | Server service | \$8,000 | |
	  | Other installation | \$4,500 | |
	  | Software licenses & other | \$2,867 | |
	  | Service + networking + storage + software + others (subtotal) | \$103,253 | "everything but the server" |
	  | **Total upfront cluster capex, per server** | **\$361,255** | |
	  | **Total upfront cluster capex, per logical GPU** | **\$45,157** | \$361,255 / 8 |
	- **Amortization assumptions**: WACC **10.25%**, useful life **6 years**.
		- Total cluster capital cost per month per server: **\$6,738.18**
		- → Capital cost per GPU-hour: **\$1.15**

- ## Operating Cost Breakdown (per 8-GPU server)

	- **Power assumptions**: all-in power consumption **10.93 kW per 8-GPU server** (~**1.37 kW per GPU**); electricity **\$0.087/kWh**; utilization **80%**; PUE **1.35**.
	- | Line item | Value |
	  |---|---|
	  | Electricity cost per kW critical IT per month | \$68.59 |
	  | Colocation cost per kW/month | \$150.00 (typical US neocloud) |
	  | Total cost per kW critical IT power per month | \$218.59 |
	  | Total server power+colo cost per month | \$2,388.27 |
	  | Remote hands + support engineer (per month) | \$131.00 |
	  | Internet connection (per month) | \$39.00 |
	  | **Total cluster operating cost per month, per server** | **\$2,558.27** |
	  | **Total cluster operating cost per month, per GPU** | **\$319.78** |
	  | **Operating cost per GPU-hour** | **\$0.44** |
	- Note: colocation (\$150/kW/mo) is more than 2× the raw electricity cost (\$68.59/kW/mo) — facility/colo overhead, not the power itself, is the larger half of the per-kW operating cost.

- ## Investment Implications

	- **Capital cost is the whole game (72.5%)**: neocloud profitability is set at procurement. A change in NVIDIA server pricing, financing cost (WACC), or assumed useful life moves unit economics far more than electricity. The 6-year useful-life assumption is aggressive given accelerating GPU generational cadence — if real economic life is shorter (e.g., 3–4 years as newer GPUs compress resale/rental value), the \$1.15 capital cost per GPU-hour is understated and breakeven rental rates rise materially.
	- **Server = 71% of upfront capex** → NVIDIA captures the dominant share of the AI cloud capital stack; networking (InfiniBand, ~21% of the non-server bucket / \$76k per server) is the second-largest line, supportive of the networking-silicon and optics TAM.
	- **Power is not the cost driver people assume**: at \$0.44/hr/GPU all-in opex (electricity + colo + support + network), even large swings in electricity price barely move the \$1.59 total. The "AI is bottlenecked by power cost" narrative is more about power *availability/interconnection* than power *price* in the unit economics.
	- **Breakeven rental rate ≈ \$1.59/hr/GPU at 80% utilization** for an H200 Neocloud Giant. Spot/contract H200 pricing below this implies the operator is either under-recovering capital or assuming higher utilization. Utilization sensitivity is high because capital cost is fixed regardless of usage.
	- **"Neocloud Giant" = best-case cost profile** (largest scale, lowest cost of capital and best procurement terms). Smaller neoclouds with higher WACC and worse server pricing have structurally higher TCO — consistent with the thesis that the neocloud market consolidates toward the largest, best-capitalized players.

