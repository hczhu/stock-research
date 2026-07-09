- tags:: [[AI infrastructure]], [[data-center]], [[capex]], [[opex]], [[power]], [[networking]], [[hyperscalers]]

- ## One-Gigawatt AI Data Center Annual Costs
	- **Source**:
		- user-provided screenshot from `Epoch AI | CC-BY`
		- chart title: `One-gigawatt AI data center annual costs`
	- **Context**:
		- the chart is based on a stylized model of a U.S. hyperscaler AI data center with `1 GW` of nameplate capacity for IT equipment
		- `CapEx` is converted to annual costs over each asset's lifespan, using cost of capital as the discount rate
		- `Facility` includes building shell, mechanical systems, and electrical equipment
		- values below are annualized cost categories, not upfront construction costs
	- **Caveat**:
		- the screenshot provides labeled values but does not include the full underlying model assumptions
		- totals below are derived from the labeled chart values

- ## Extracted Annual Cost Table
	| Cost category | Cost type | Annual cost | Share of total annual cost | Context |
	| --- | --- | ---: | ---: | --- |
	| `Servers` | `CapEx` | `$5.00B` | `58.6%` | Largest cost bucket; represents AI compute servers as annualized capital cost. |
	| `Facility` | `CapEx` | `$1.40B` | `16.4%` | Building shell, mechanical systems, and electrical equipment. |
	| `Network infrastructure` | `CapEx` | `$1.20B` | `14.1%` | Networking is the third-largest bucket and a major part of scaled AI cluster cost. |
	| `Energy` | `OpEx` | `$590M` | `6.9%` | Largest operating-cost item; direct power consumption cost. |
	| `Taxes` | `OpEx` | `$140M` | `1.6%` | Recurring tax burden in the stylized model. |
	| `Maintenance` | `OpEx` | `$120M` | `1.4%` | Recurring maintenance cost for facility and infrastructure. |
	| `Labor` | `OpEx` | `$40M` | `0.5%` | Small relative to power and capitalized infrastructure. |
	| `Utility works` | `CapEx` | `$20M` | `0.2%` | Grid / utility-related works shown as annualized CapEx. |
	| `Land` | `CapEx` | `$13M` | `0.2%` | Very small annualized cost versus servers, facility, and networking. |
	| `Water` | `OpEx` | `$6M` | `0.1%` | Smallest labeled operating-cost bucket. |

- ## Cost Split Summary
	| Metric | Value | Context |
	| --- | ---: | --- |
	| Total annual cost | `$8.53B` | Sum of all labeled annualized cost categories. |
	| Annualized CapEx cost | `$7.63B` | Servers, facility, network infrastructure, utility works, and land. |
	| Annual OpEx cost | `$896M` | Energy, taxes, maintenance, labor, and water. |
	| CapEx share of annual cost | `89.5%` | The model is overwhelmingly capital-cost driven. |
	| OpEx share of annual cost | `10.5%` | Operating costs are meaningful but much smaller than annualized infrastructure cost. |
	| Servers + network infrastructure | `$6.20B` | Compute and networking together account for about `72.7%` of total annual cost. |
	| Servers + facility + network infrastructure | `$7.60B` | The top three buckets account for about `89.1%` of total annual cost. |
	| Energy as share of OpEx | `65.8%` | Power dominates recurring operating cost. |

- ## Electricity Cost Back-Of-Envelope
	- Formula: `annual electricity cost = load in kW * 8,760 hours/year * $/kWh * utilization * PUE adjustment if 1GW is IT load`.
	- If `1 GW` means **grid draw at the meter**, annual energy use is `1,000,000 kW * 8,760h = 8.76B kWh`.
	- The claim that a `1 GW` site costs `~$613M/year` in electricity implies an electricity price of about `$0.07/kWh`:
		- `8.76B kWh * $0.07/kWh = $613.2M/year`.
	- The chart's `$590M` energy line implies an effective rate of about `$0.067/kWh` if it also assumes `1 GW` of all-year grid draw:
		- `$590M / 8.76B kWh = ~$0.067/kWh`.
	- Sensitivity table:
		| Assumption | Calculation | Annual electricity cost |
		| --- | ---: | ---: |
		| `1 GW` grid draw at `$0.05/kWh` | `8.76B kWh * $0.05` | `$438M` |
		| `1 GW` grid draw at `$0.067/kWh` | `8.76B kWh * $0.067` | `~$590M` |
		| `1 GW` grid draw at `$0.07/kWh` | `8.76B kWh * $0.07` | `$613M` |
		| `1 GW` grid draw at `$0.087/kWh` | `8.76B kWh * $0.087` | `$762M` |
		| `1 GW` IT load, `PUE 1.2`, `$0.07/kWh` | `8.76B kWh * 1.2 * $0.07` | `$736M` |
		| `1 GW` IT load, `PUE 1.35`, `80% utilization`, `$0.087/kWh` | `8.76B kWh * 1.35 * 80% * $0.087` | `~$823M` |
	- Read: `~$590M-$613M/year` is a reasonable electricity-cost estimate for a continuously loaded `1 GW` site at roughly `6.7-7.0c/kWh`. If the `1 GW` figure is **IT load** rather than **meter/grid draw**, the electricity bill should be grossed up by `PUE` unless the quoted power already includes facility overhead.
	- Important distinction: electricity is not the biggest dollar line versus annualized compute capex. If GPUs alone cost `~$25B` per `1 GW`, cutting GPU cost in half saves `~$12.5B` upfront, or `~$2B+/year` on a six-year straight-line life before financing cost. The stronger argument for `perf/watt` is not that the electricity bill dominates hardware dollars, but that scarce power capacity caps tokens, revenue, and deployment scale.

- ## Stock Implications
	- The cost stack is primarily a compute and capital-equipment story: servers alone are nearly `59%` of annualized cost.
	- Networking is large enough at `$1.2B` annually to matter as a separate AI infrastructure investment theme, not just an attachment to server spend.
	- Facility cost at `$1.4B` shows that power delivery, cooling, building shell, and electrical systems are major beneficiaries of AI data-center expansion.
	- Energy is much smaller than servers on an annualized basis, but it dominates OpEx and becomes strategically important as clusters scale to multi-gigawatt footprints.
	- Labor, land, water, and utility works are visible constraints but not the major dollar pools in this stylized annual-cost model.

- ## Memo Takeaway
	- A `1 GW` AI data center is modeled as roughly an `$8.5B` annual-cost machine, with nearly `90%` of annualized cost tied to CapEx categories.
	- For stock work, this supports prioritizing the infrastructure value chain around AI servers, networking, facility electrical / cooling systems, and power availability.
