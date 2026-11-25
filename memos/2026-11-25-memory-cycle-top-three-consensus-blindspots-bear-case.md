tags:: [[$MU]], [[$000660.KS]], [[$SKHY]], [[$005930.KS]], [[DRAM]], [[HBM]], [[DDR5]], [[memory]], [[memory-cycle]], [[bear-case]], [[LTA]], [[strategic-customer-agreements]], [[inventory]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-25
file-updated-at:: 2026-11-25

- ## Memory-cycle bear case: three "consensus blindspots" at a semiconductor top
	- **Source**: an unattributed post supplied by the user (November 2026), tagged \$MU and \$SKHY.
	- **Thesis (the author's)**: today's pushback on the memory-cycle-top thesis repeats three classic blindspots.
		- **Guidance lags**: management guidance and the absence of oversupply forecasts from the sell side mean nothing at a cyclical top.
		- **HBM isn't isolated**: HBM capacity is not insulated from commodity DRAM.
		- **Contract floors don't hold**: contract price floors don't survive a spot collapse.
		- "Contractual bands do not suspend microeconomic gravity. When cleanroom yields climb and defensive ordering stops, price floors dissolve into balance sheet inventory write-downs."

- ## The three arguments
	- | Blindspot | The author's claim | Mechanism |
	  |---|---|---|
	  | **1. The "management guidance" myth** | Hyperscalers and 100+ sell-side analysts not guiding to oversupply doesn't mean it can't happen. Corporate guidance in cyclical commodities lags | During allocation crunches, hyperscalers **double-order** defensively. When supply normalizes, "phantom backlogs disappear overnight." In **2018 and 2021**, sell-side models projected a permanent supercycle **two quarters** before margins turned negative |
	  | **2. The "HBM isolation" fallacy** | HBM capacity can affect standard DDR5 | HBM needs **2.5–3× the wafer area** of standard DRAM, and front-end lithography and etch tools are fungible. As **TSV yields climb from 65% to 85%**, fewer raw wafers are needed per stack. Fabs carry huge fixed depreciation and can't leave tools idle, so released wafers flow back into commodity **DDR5 and LPDDR5** |
	  | **3. The "LTA price floor" fiction** | Strategic Customer Agreements (SCAs) are "commercial volume frameworks, not escrow-backed debt covenants" | When spot falls **40% below** a contract floor, no tier-1 hyperscaler accepts above-market deliveries. Customers push out deliveries, freeze acceptance, and demand renegotiation, under threat of excluding the vendor from next-generation platform qualification |
	- **The author's precedent**: Micron had multi-year customer commitments going into FY23, yet delayed takes pushed **inventory days past 160**. That triggered **over \$1.8B of lower-of-cost-or-market (LCM) inventory write-downs**, which pushed GAAP gross margin negative.
		- *Memo's check*: the order of magnitude matches Micron's FY23 write-downs, about \$1.4B in fiscal Q2 2023 and about \$0.4B in fiscal Q3, which drove GAAP gross margin negative. This is from memory, not from a filing in the repo. The 160-day DIO figure isn't checked here.

- ## Testing each claim against repo data (memo's reading)
	- ### 1. Guidance and double-ordering
		- **For the author**: Micron and SK hynix both say demand far exceeds supply. SK hynix says customers want **more than twice** what it can supply ([[SKHY-2026-Q3]]). Unmet requests that large are where double-ordering would hide.
			- SK hynix now screens customers' **"financial health and funding capability"** before building capacity, an implicit acknowledgment that some orders may not be real.
			- Michael Burry's bear case named "customers push out or renegotiate 2027 bookings" as the sign that hoarding is unwinding ([[2026-06-03-michael-burry-memory-companies-bear-case]]).
		- **Against the author**: this cycle's commitments come with **cash**.
			- Micron holds **\$12.7B of customer deposits** against **\$32B of commitments** ([[MU-2026-Q3]]).
			- SK hynix's agreements include deposits ([[SKHY-2026-Q3]]).
			- Double-ordering is costlier when each order ties up cash.
	- ### 2. HBM and commodity DRAM
		- **The trade ratio is real**: Micron cites about **3:1**, rising to about **4:1 for HBM4E**. SK hynix says **3–4×** ([[2026-11-15-micron-memory-shortage-contracts-musk-pricing]], [[2026-11-21-micron-sk-hynix-hbm-vs-conventional-dram-revenue-mix]]). The author's 2.5–3× is at the low end.
		- **Front-end tools are fungible**: that is correct, and it cuts both ways. HBM's pull on wafers is what made commodity DRAM scarce in 2026, so any HBM slowdown would release capacity into DDR5. Burry makes the same point ([[2026-06-03-michael-burry-memory-companies-bear-case]]).
		- **Pressures that work against freed capacity**:
			- **Rising trade ratios**: HBM3E to HBM4 to HBM4E absorb more wafers per bit with each generation.
			- **Shorter stacks**: customers moving to fewer layers per stack need **more stacks and base dies** for the same bits ([[SKHY-2026-Q3]]).
			- **Shrinking node gains**: smaller bit gains from node transitions ([[MU-2026-Q3]]).
			- These work against the yield-driven release the author describes. The **65% → 85%** TSV-yield path isn't sourced in the post.
		- **Margin inversion**: conventional DRAM is currently **more profitable than HBM** ([[2026-11-21-micron-sk-hynix-hbm-vs-conventional-dram-revenue-mix]]). Memory makers already have an incentive to shift wafers toward DDR5, which would raise commodity supply even before HBM yields improve.
	- ### 3. Contract floors
		- **What changed since FY23**:
			- Micron describes moving from **ordinary LTAs** to **non-cancelable SCAs** with take-or-pay terms, price bands and **cash deposits** that are returned only if minimum purchases are met ([[MU-2026-Q2]]).
			- That is closer to a covenant than the FY23 framework was, though still not escrow.
		- **The author's renegotiation dynamic**:
			- A veteran investor makes the same argument: buyers will "gladly forfeit their deposits" when the spot discount exceeds the deposit ([[2026-11-05-veteran-investor-memory-pe3-not-cheap-lta-skepticism]]).
			- *Memo calculation*: Micron's \$12.7B of deposits held is about **9%** of its roughly \$150B of remaining performance obligations. A 40% spot discount on the remaining volume would exceed that.
		- **How far below spot the floors sit**: SanDisk's floor price is about **26–28% below** realized 4Q26 ASP, a gross-margin floor of about 78–80% ([[2026-09-04-dram-feed-cxmt-share-break-and-lta-floor-arithmetic]]). The author's 40%-below-floor scenario would therefore mean spot falling about **55–57%** from current ASP before the stress applies.
		- **The vendor's leverage**: the author assumes buyers can threaten to exclude a vendor from next-generation qualification. In HBM, where suppliers are qualified separately for each platform and capacity is short, the vendor has leverage too ([[2026-11-20-dram-commodity-vs-cpu-gpu-custom-hbm4-switching-friction]]).
	- ### Net
		- **What holds**: the author's mechanisms are real. Fungible front-end tools, double-ordering risk, and floors that can be renegotiated are the standard cycle risks.
		- **What this cycle adds**: cash deposits, take-or-pay terms, rising HBM trade ratios and a 2027–28 supply outlook that both Micron and SK hynix call tighter than 2026.
		- **What the post doesn't show**: it gives no evidence that oversupply is starting now. Its precedents (2018, 2021, FY23) describe how a downturn unfolds, not when.

- ## Related in the repo
	- **Earlier bear cases**: [[2026-06-02-memory-cycle-bear-case-arguments]], [[2026-07-21-memory-positioning-bull-bear-debate]], [[2026-10-05-the-circuit-memory-cycle-balance-sheet-tokenomics]].
	- **Index-level view**: [[DRAM-memory-ssd-index-thesis]].
