tags:: [[$AAPL]], [[App-Store]], [[services]], [[regulation]], [[take-rate]], [[gaming]], [[subscriptions]], [[RevenueCat]], [[Sensor-Tower]]

- ## The US App Store decline, decomposed: gaming weakness plus web-payment leakage
	- **Source**: A *Financial Times* chart of **Sensor Tower** data — US consumer spending on Apple's App Store, year-on-year change by quarter, 2016 through 2026, **net of Apple's take** — showing the **first negative print in a decade** in Q2 2026. Paired with a decomposition from **RevenueCat CEO Jacob Eiting**; RevenueCat is the leading in-app purchase SDK.
	- **Thesis**: This supplies the answer to the causality question left open in [[2026-08-19-stratechery-apple-app-store-fee-settlements-att-germany]], and the answer is **both, in identifiable proportions**. The underlying app economy is still growing; **gaming is shrinking while non-gaming grows strongly**; and **6 points of transaction share moved off-platform in a single year**. The App Store *channel* is contracting even though the app economy is not.
- ## The two datasets
	- **Sensor Tower (channel view)**: the chart shows YoY growth running roughly 30–45% through 2016–2018, spiking near 48% in 2020, decelerating through 2021–2024, falling to single digits across 2025, and turning **negative in Q2 2026**. The FT reporting already on file puts that print at **−6%, against +9% a year earlier**.
	- **RevenueCat (developer-revenue view)**, per Eiting:
	  | Segment | YoY change |
	  |----------------------------|-----------------------|
	  | **Gaming revenue** | **−4.5%** — described as the majority of the decrease |
	  | **Non-gaming (apps)** | **+14.6%** |
	  | **Web payments share** | **20% → 26%** of transactions |
	- Eiting's summary is that this is a mix of **less spending on game IAP** and **more companies bypassing Apple's in-app-purchase flow in favour of web checkout**, with the **2025 court ruling forcing Apple to permit web payment links on iOS** named as a likely factor — the same ruling whose commission structure is covered in [[2026-08-19-stratechery-apple-app-store-fee-settlements-att-germany]].
- ## Reconciling them — the derived result
	- **The two sources measure different things**, which is why they look contradictory: Sensor Tower measures spending *through the App Store channel*; RevenueCat's SDK sees developer revenue *across channels*. Working the algebra makes all three figures mutually consistent:
	  | Step | Result |
	  |-------------------------------------------------|--------------------|
	  | Channel share shift, 80% → 74% of transactions | **−7.5%** drag on App Store revenue, before any growth |
	  | Total app-economy growth implied by a −6% channel print | **~+1.6%** |
	  | Gaming share of the base implied by −4.5% / +14.6% blending to +1.6% | **~68%** |
	  | Contribution split | gaming **−3.1pp**, non-gaming **+4.7pp** |
	- **The 68% falls right on the long-standing estimate that games are roughly two-thirds of App Store consumer spend**, which is strong independent evidence the reconciliation is sound rather than a coincidence of arithmetic. The numbers are not in conflict; they describe one system from two vantage points.
	- **The resulting picture**: the app economy grew about **1.6%**, gaming dragged it down by about 3 points while non-gaming added nearly 5, and **on top of that a 6-point channel shift removed roughly 7.5% from Apple's side of the ledger.** Leakage is the larger single force; gaming weakness is what prevents underlying growth from offsetting it.
- ## What this settles, and what it doesn't
	- **It refutes the simplest bear case.** Non-gaming revenue growing **14.6%** means the ecosystem is not collapsing and consumers have not stopped paying for software. Subscription apps — the category that dominates non-gaming — are healthy.
	- **It also refutes the simplest bull case.** Apple's problem is not a one-time re-basing. **Web share moved 20% → 26%, a 30% relative increase in a single year**, and it is driven by a court ruling that is not going away. This is a **structural, recurring drag on channel share**, independent of consumer spending.
	- **On Thompson's question — leakage or attention?** The data supports leakage as the dominant channel effect, but **gaming weakness is real and unexplained**, and gaming IAP is precisely where attention reallocation to short-form video, free games, and AI would show up first. **RevenueCat does not distinguish "teens play fewer paid mobile games" from "teens play the same games and pay elsewhere,"** so the attention hypothesis survives intact within the gaming segment.
	- **Context that argues against reading this as purely regulatory**: the chart shows a **decade-long deceleration**, from 30–45% growth in 2016–2018 to mid-teens by 2023–2024 to single digits in 2025. **Q2 2026 is the endpoint of a long maturation curve, not a break in it.** Regulation and leakage pushed an already-decelerating series across zero; they did not create the deceleration.
- ## The number to extrapolate, and why it compounds with fee compression
	- **The 6-point annual channel shift is the forward-looking variable.** Naively extended, App Store channel share goes **74% → 68% → 62%** over the next two years, each step costing roughly 7–8% of Apple's App Store revenue base before any growth offset. Whether that rate holds is the key uncertainty — the 2025 ruling was a one-time unlock, so the shift may be a step function toward a new equilibrium rather than a constant annual rate. **Watch the next two prints to distinguish those.**
	- **The compounding problem for Apple is that rate and volume are falling together.** [[2026-08-19-stratechery-apple-app-store-fee-settlements-att-germany]] documents the headline commission moving from **30% toward 15%**, with payment processing valued at roughly its cost. This data adds that **the base those rates apply to is itself shifting off-platform.** Two independent compressions on the same high-margin line, and Apple has now conceded in filings that it **"may not earn a commission at all"** on alternative-payment purchases.
	- Set against the input-cost pressure in [[AAPL-2026-Q2]] and the second round of hardware price increases in [[2026-08-28-stratechery-mac-refresh-memory-pricing-and-jalapeno]], **Apple is absorbing Services take-rate compression, Services channel loss, and hardware input inflation simultaneously.**
- ## Source caveats
	- **RevenueCat has a commercial interest in the leakage narrative** — it sells the tooling developers use to run subscriptions and web checkout, so higher web-payment share is favourable to its business. The figures are plausible and specific, but they are vendor-supplied and unaudited.
	- **RevenueCat's panel skews toward subscription apps using its SDK**, which likely **under-represents large games with in-house billing** — the very category driving the −4.5%. The gaming figure is the least reliable number in the set despite carrying the most weight in the reconciliation.
	- The Sensor Tower series is an **estimate**, explicitly net of Apple's take, and covers **US only** — Apple's global mix may behave differently, particularly where the web-link ruling does not apply.
