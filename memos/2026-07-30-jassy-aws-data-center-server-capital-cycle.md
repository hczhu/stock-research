- tags:: [[$AMZN]], [[AWS]], [[AI-capex]], [[capex]], [[data-center]], [[unit-economics]], [[ROIC]], [[depreciation]], [[memory]]

- ## Jassy's two-cycle capital framework for AI infrastructure
	- **Source**: Andy Jassy, Amazon Q2 2026 earnings call, July 30, 2026 — prepared remarks defending ~\$220B of 2026 cash capex. Full quarter context in [[AMZN-2026-Q2]].
	- **Thesis**: Jassy's answer to the AI-capex ROIC bear case is to split the spend into two assets with opposite risk profiles — **long-lived, committed data center shells** and **short-lived, demand-gated servers**. The framework is internally coherent and the arithmetic checks out, but the demand gate he emphasizes protects only the server half; the data center half is committed two years ahead of any revenue and is where the actual risk sits.

- ## The two capital cycles
	- | Dimension | Data centers | Servers & networking |
	  |------------------------------|--------------------------------------|---------------------------------------|
	  | Spend timing vs. revenue | **~2 years before** monetization | **A few months before** in service |
	  | Demand visibility at spend | Low — built ahead of contracts | **High — "if the demand isn't there, we won't spend the capital"** |
	  | Time to break even | n/a (recovered via server generations) | **A little less than 3 years** |
	  | Useful life | **30+ years** | **At least 5–6 years** |
	  | Contract coverage | — | Most AI capacity **contracted ≥5 years** |
	  | Repeat capital required | **None** after initial build | Every generation |
	  | Risk character | Committed, long-lead, un-gated | Optional, short-lead, gated |

- ## Cash-flow timeline of a single server generation
	- | Phase | Timing | Cash characteristic |
	  |-------------------------|----------------|--------------------------------------------------|
	  | Data center construction | **T−2 to T−0** | Pure outflow, no revenue |
	  | Servers installed, revenue begins | **T−0** | "Significant revenue right away" |
	  | Server payback period | **T−0 to ~T+3** | Revenue covers but does not yet exceed the server investment |
	  | **Harvest window** | **~T+3 to T+5/6** | **"Significant free cash flow"** |
	- **Derived — the full cash cycle is ~5 years**: roughly 2 years of data center build plus a little under 3 years of server payback before the first generation turns cash-positive. That is the honest lag behind the current FCF headwind, and it is why Jassy pre-committed to "free cash flow headwinds until these data centers come online."
	- **Derived — the harvest window is ~40–50% of asset life**: a 5–6 year useful life minus a sub-3-year breakeven leaves 2–3 years of FCF generation per generation.
	- **The detail that makes the payback credible**: AI capacity is **contracted for at least five years** against a **5–6 year useful life**. Contracted revenue therefore covers essentially the *entire* asset life, not just the payback period — this is what distinguishes the claim from a speculative utilization assumption. It is the single most load-bearing fact in the framework.

- ## Multi-generation economics — where the returns actually come from
	- | Generation | Data center capital borne | Server capital borne | Relative economics |
	  |-----------------|---------------------------|----------------------|----------------------------|
	  | 1st | **Full** | Full | Lowest ROIC of the series |
	  | 2nd–5th/6th | **None** | Full | Structurally better |
	- **Arithmetic check**: a 30+ year shell divided by a 5–6 year server life gives **5–6 generations**, exactly as Jassy claims. The claim is internally consistent.
	- The strategic consequence: **Gen-1 ROIC materially understates the blended ROIC of the shell over its life.** Any analysis that judges the current build on first-generation returns is measuring the worst point in the series. That is a legitimate framing — and also, conveniently, unfalsifiable for another ~5 years.
	- Stated inflection condition, worth holding as the testable claim: FCF turns when **"revenue growth outpaces the incremental CapEx growth, which will happen at some point."** No date offered.

- ## What the framework does not address
	- **The demand gate covers the smaller-risk half.** Servers are bought months ahead with contracts in hand. Data center shells are committed **two years early, without contracts**, and Jassy explicitly noted demand is "necessitating so many data centers being built simultaneously in advance of when we can start monetizing them." If the middle of his own [[AMZN-2026-Q2]] demand barbell — existing enterprise workloads not yet using inference pervasively — arrives slower than hoped, the exposure is in shells already built, not in servers that were never bought.
	- **Memory inflation cuts directly against the sub-3-year breakeven.** In the same remarks Jassy raised 2026 capex from ~\$200B to ~\$220B specifically because of memory cost. Higher server cost per unit lengthens payback unless prices reset — and he separately confirmed **existing contracts hold price for their duration**, so cost inflation only reprices on renewal. The breakeven figure and the capex raise are in tension for the currently-contracted book.
	- **A 30-year shell life assumes retrofittability across escalating power density.** Five to six server generations spanning three decades implies the physical facility remains fit for purpose as racks move from air to liquid cooling and power density climbs. Retrofit capex is not the same as repeating the original build, but it is not zero either — and "we don't have to spend that startup capital again" quietly assumes it is.
	- **"Extending useful life" is simultaneously an operational achievement and an accounting lever.** Jassy cites AWS's track record of pulling breakevens forward *and* extending equipment life. Extending depreciable life flatters reported operating income; it is worth watching whether the disclosed depreciation schedule moves alongside these claims, particularly given peers have recently moved the other way on AI-specific hardware.

- ## What would confirm or falsify this
	- **Timing of the FCF inflection** relative to the ~5-year full-cycle math — the first generation of AI data centers should begin harvesting on this schedule.
	- **The capex-vs-revenue-growth crossover** Jassy named as the trigger, and whether it arrives before or after 2028 capacity (already described as substantially reserved) is monetized.
	- **Any change to server depreciable life** in the 10-K, in either direction.
	- **Whether contract terms stay at ≥5 years** as memory-driven cost inflation persists — shorter terms would break the contracted-life-equals-useful-life symmetry that makes the payback claim work.
