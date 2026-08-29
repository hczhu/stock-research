tags:: [[$AMZN]], [[AWS]], [[$MSFT]], [[$NVDA]], [[$AMD]], [[$AVGO]], [[OpenAI]], [[Anthropic]], [[data-center]], [[power]], [[AI-capex]], [[capex]], [[hyperscalers]], [[circular-financing]]

- ## AWS at ~15 GW in 2025 — putting a base under the "double by 2027" claim
	- **Source**: Two data points supplied together — an **estimated ~15 GW of AWS capacity in 2025**, described as the largest hyperscaler footprint, alongside Amazon's own statement that it expects to **double capacity from 2025 to 2027**.
	- **Note the difference in status**: the doubling is a **company statement**, already recorded in [[AMZN-2026-Q2]] as "on track to double power capacity by end-2027 vs 2025." The **~15 GW is a third-party estimate**, not disclosed by Amazon. Its value is that it converts a relative claim into an absolute one.
- ## What the base implies
	- | Quantity | Value |
	  |----------------------------------|--------------------------|
	  | AWS capacity, 2025 (estimated) | **~15 GW** |
	  | Implied capacity, end-2027 | **~30 GW** |
	  | Incremental build | **~15 GW over two years** |
	  | Average annual add | **~7.5 GW/year** |
	- **For scale**: a large nuclear reactor is roughly 1 GW, so AWS is adding the equivalent of about **fifteen reactors' worth of load in two years** — and the 2027 exit rate of ~30 GW is on the order of **2% of total US installed generating capacity** (~1,200 GW), for one company, globally deployed.
- ## The cross-check against Microsoft
	- Microsoft has made **the same two-year doubling claim** and disclosed the run rate behind it: **~1 GW added per quarter** in both [[MSFT-2025-Q4]] and [[MSFT-2026-Q2]], where management said it is "on track to roughly double our overall capacity in just two years."
	- **Working backwards**: ~1 GW/quarter is ~4 GW/year, so ~8 GW added over two years — and if that doubles Microsoft's base, its **2025 base is roughly 8 GW**.
	- **That makes AWS at ~15 GW roughly 1.9× Microsoft**, which is consistent with the "largest hyperscaler" framing and gives the estimate independent plausibility. **Both are doubling; AWS is doubling off a base nearly twice as large**, so in absolute terms AWS is adding roughly the same amount again as Microsoft's entire estimated fleet.
- ## Two things to hold alongside it
	- **Capacity is not the constraint being relieved.** Even with this build, Jassy's position in [[AMZN-2026-Q2]] is that at ~\$220B of capex *"we will still not have enough capacity to meet all the demand we have in 2026"* — with the lion's share of 2027 capacity already reserved and 2028 demand described as striking. **A doubling that still leaves demand unmet is the operative fact**, not the doubling itself.
	- **A very rough capital anchor**: ~\$220B of annual capex against ~7.5 GW/year implies on the order of **\$29B per GW**. Treat this loosely — Amazon's capex includes non-AWS spending and the timing of capex versus energization does not line up — but it sits inside the commonly cited \$30–50B/GW all-in range, which is a mild sanity check on both numbers rather than a derived cost. The capital-cycle mechanics behind that spend are in [[2026-07-30-jassy-aws-data-center-server-capital-cycle]].
- ## The demand side in the same units — two labs have committed to more GW than AWS will have
	- **Source note**: added from separate commentary on compute-demand concentration. The **12 GW Nvidia figure for OpenAI is a Nvidia statement**; the other vendor numbers are announced commitments; the **~3 GW Nvidia figure for Anthropic is an estimate** ("likely"), and is the least firm number in the set.
	- **OpenAI's commitments total 30 GW**:
	  | Vendor | Committed |
	  |-----------------|-----------|
	  | **Nvidia** | **12 GW** (existing and planned) |
	  | **Broadcom** | 10 GW |
	  | **AMD** | 6 GW |
	  | **Amazon** | 2 GW |
	  | **Total** | **30 GW — Nvidia share ~40%** |
	- **Anthropic's total ~14.5 GW**, roughly half of OpenAI's:
	  | Vendor | Committed |
	  |------------------------|-----------|
	  | **Amazon** | 5 GW |
	  | **Broadcom + Google** | ~3.5 GW |
	  | **Nvidia** (estimated) | ~3 GW |
	  | **AMD** | 2 GW |
	  | **Google Cloud** | ~1 GW |
	  | **Total** | **~14.5 GW — Nvidia share ~21%** |
	- **The juxtaposition is why these belong in the same memo as the supply figures.** Combined, the two labs have committed to **~44.5 GW** — roughly **1.5× the ~30 GW AWS expects to have in total by end-2027**, and about **3× AWS's estimated 2025 base**. **Two customers have contracted for more capacity than the largest hyperscaler will own.** That is the concrete form of the concentration concern: incremental compute demand is dominated by a very small number of buyers, which is a materially different risk profile from a broad enterprise base.
	- **Nvidia's committed share across both is ~34%** — 15 GW of 44.5 — leaving **~66% committed to non-Nvidia silicon**. Both labs have been explicit that they want **heterogeneous fleets** rather than exclusive Nvidia dependence.
	- **The timing caveat matters more than the share itself.** These commitments are expected to be **frontloaded in Nvidia chips and to shift toward non-Nvidia silicon over the medium to long term**. So **committed GW share understates Nvidia's near-term revenue share and overstates its terminal share** — converting these figures into a revenue split requires a ramp assumption, not a ratio.
	- **The negotiating-leverage point is the sharpest idea here.** Nvidia would like to grow its ~21% position at Anthropic precisely as it expects to lose share at OpenAI — but **Amazon and Alphabet are equally motivated to sweeten terms** to place their own silicon. With **four vendors competing to sell into one buyer, the leverage sits with the buyer.** The wry corollary is that a lab's stated commitment to heterogeneity is negotiable **if the vendor funds the purchase** — the same instrument analysed as an off-margin price cut in [[2026-08-21-ben-thompson-ilb-risk-relocation-commodity-logic]] and catalogued in [[2026-06-11-nvidia-coreweave-nebius-circular-financing]]. **Vendor financing is how share gets bought in a market with this structure**, and it should be expected to intensify rather than fade.
	- Puts numbers on a line already on file: [[AMZN-2026-Q2]] recorded "multi-year, multi-gigawatt commitments from both Anthropic and OpenAI" for Trainium without figures. These are **5 GW and 2 GW** respectively.
