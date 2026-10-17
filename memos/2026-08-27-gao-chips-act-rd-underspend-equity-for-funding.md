tags:: [[semiconductor]], [[CHIPS-Act]], [[industrial-policy]], [[policy]], [[US]], [[R&D]], [[lithography]], [[quantum]], [[imec]], [[$INTC]], [[$AMAT]], [[$LRCX]], [[$KLAC]]
file-created-at:: 2026-08-27

- ## GAO: CHIPS Act Fabs Are on Schedule, the \$11B R&D Arm Is 95% Unspent
	- **Source**: IEEE Spectrum, "The U.S. Is Building CHIPS Act Fabs but Neglecting R&D," Alex Music and Lucas Laursen, 27 August 2026 (October 2026 print issue). Reports on the US Government Accountability Office report released 6 August 2026. Quotes Donna Dubinsky (former Commerce official, Natcast trustee until August 2025), Brent Omdahl (SVP government affairs, GlobalWafers), and VJ Sahi (Clark Street Associates).
	- **Thesis**: The CHIPS Act has split into two programs running at opposite speeds — **milestone-based manufacturing incentives are disbursing on schedule**, while the **R&D arm has spent ~4.6% of its \$11B** after Commerce canceled the \$7.4B Natcast contract. The investable change is not the underspend itself but the **replacement funding model: equity-for-grants**, which converts federal support from non-dilutive leverage into a cap-table event for recipients.

- ## The R&D Funding Split
	- | Bucket | Amount | Status |
	  |--------------------------------------|--------------:|--------------------------------------------------------------|
	  | Total CHIPS Act R&D appropriation | `\$11B` | Baseline |
	  | Canceled (mostly Natcast/NSTC) | `\$7.8B` | Commerce canceled the \$7.4B Natcast contract in August 2025, electing to run the NSTC itself |
	  | Disbursed to date | `\$506.8M` | **~4.6% of the appropriation** |
	  | Remaining | `\$2.69B` | Unallocated |
	  | *of which* NIST metrology research | `~\$347M` | The largest actually-funded R&D component |
	  | *of which* SBIR component | `<\$5M` | Effectively untouched |
	- New awards made **outside** the original NSTC framework total `\$900M` — to **xLight**, **SandboxAQ**, and **I-Pulse** — plus a promised `\$2B` in preliminary awards for **quantum computing**, also to be drawn from CHIPS R&D funds.
	- GAO's procedural findings: Commerce's April 2026 NSTC charter "does not mention the strategy or contain sufficient detail to demonstrate plans for the NSTC to align with" the National Strategy on Microelectronics Research — a statutory requirement — and Commerce has not involved the private sector in establishing its investment fund, another requirement.

- ## Equity-for-Grants Is the Policy Regime Change
	- The \$900M of post-NSTC awards **required equity from the companies** in exchange for government funds. The original NSTC-framework awards did not.
	- Dubinsky's objection is the one that matters for modeling: "They're using these funds for investment in equity, when these are companies that have access to the capital markets.... If private capital is serving a sector well, then there's no need for the government to play a role. The whole idea of this program was to provide leverage that would enable substantially more private-sector investment."
	- Read-through: federal semiconductor support should no longer be modeled as **non-dilutive**. Any company accepting new CHIPS R&D money should be assumed to be issuing equity to the government, and the leverage ratio the Act was designed around (public dollars crowding in private dollars) no longer applies to this tranche.
	- Countervailing datapoint for existing direct-grant awardees: Omdahl says he has **not heard of the government going back to awardees to ask for equity positions**, and that the administration's changes have made GlobalWafers' work run *more* smoothly. The equity model appears to apply to new awards, not retroactively to signed milestone grants.

- ## Manufacturing Is the Half That Works
	- | Metric | Value | Note |
	  |-----------------------------------------|----------------|----------------------------------------------------------|
	  | Milestones completed (as of April 2026) | `24 of 144` | Across 49 projects; associated funding disbursed |
	  | Projects added since April 2026 | `7` | Five for USA Rare Earth, one each for Bosch and Powerex |
	  | Majority of projects complete by | `2028` | GAO expectation |
	  | All projects complete by | `2033` | Long tail |
	- **GlobalWafers** completed phase one of its Texas wafer facility last year and received the promised `\$200M` shortly afterward — a working example of the milestone-disbursement mechanism. The company is also building in Missouri.
	- Omdahl on the early-administration scare: "Obviously everybody in industry got perhaps a little anxious when President Trump, at the beginning of the administration, said he didn't like the direct-grant program." That risk has not materialized for signed awards.
	- The 2028 completion cluster is the monitorable supply signal — US capacity additions from this program land as a wave rather than a ramp, with semicap revenue recognition front-running it.

- ## Where Leading-Edge Process R&D Goes Instead
	- Dubinsky: "We are choosing to not invest in future semiconductor technology leadership in the U.S., and I don't understand that choice.... Now it's going to be in Belgium. It's going to be in Tokyo. It's going to be in Korea. It's not going to be in the U.S."
	- The named destinations are the existing consortium centers of gravity — **imec** in Belgium above all. A US R&D vacuum strengthens the pull of non-US pre-competitive research hubs, where tool vendors co-develop next-node process capability and where early tool placements are decided.
	- Sahi's counterpoint caps the damage: "There were no significant developmental awards in flight" within the NSTC, so cancellation "may not have harmed valuable research or development so much as delayed it. The trade-off has been a delay...but it has also provided more available capital [which is positive] if they can now move to deploy those R&D dollars on a reasonable schedule."
	- The \$2.69B unallocated plus the \$2B quantum earmark means the capital still exists. The open question is deployment schedule and whether it goes to semiconductor process research at all — the quantum earmark suggests the R&D pot is being repurposed toward adjacent priorities.
