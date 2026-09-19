- tags:: [[SemiAnalysis]], [[data-center]], [[AI infrastructure]], [[capex]], [[power]], [[ERCOT]], [[BtM]], [[NIMBY]], [[permitting]], [[hyperscalers]], [[$VRT]], [[$ETN]], [[$GEV]], [[$BE]], [[$CVX]], [[$MSFT]], [[$AMZN]], [[$META]], [[$GOOGL]]

- ## SemiAnalysis — 300+ Data-Center Moratoriums, but Only 2.3 GW Actually Delayed
	- **Source**: SemiAnalysis, “Everyone Says Datacenter Moratoriums Are Killing the US Buildout. We Mapped All 300 of Them,” Maya Barkin, Reyk Knuhtsen, Jeremie Eliahou Ontiveros and Dylan Patel, Sep 15 2026. Paid report supplied as PDF.
	- **Thesis**: Counting ordinances dramatically overstates construction risk. SemiAnalysis maps 20.1 GW inside live local-moratorium boundaries but finds only 1.525 GW actually delayed; including New York raises the national total to roughly 2.3 GW. Restrictions currently change **where projects locate, which sites win and how power is supplied** more than they reduce aggregate U.S. capacity. The strongest read-through is continued AI-infrastructure equipment demand plus a larger premium for behind-the-meter power and already-entitled land.
	- This is the project-level update to [[2026-06-18-semianalysis-datacenter-2026-not-canceled-rebuttal]], which argued that cancellation headlines mostly capture speculative capacity that was never in the near-term forecast.
- ## Decision-Useful Data
	- | Metric | Report finding | Investment context |
	  |---|---:|---|
	  | Local moratoriums and bans enacted | **300+** | Headline count; poor proxy for affected MW |
	  | Local instruments tracked across full lifecycle | **400+ across 17 states** | Includes proposed, enacted, expired, lifted, replaced and rejected actions |
	  | Capacity inside a live local boundary | **20,138 MW** | Gross exposure before parcel, permit and timing filters |
	  | Capacity actually delayed locally | **1,525 MW, or 7.6% of exposed MW** | Only three projects account for essentially all of it |
	  | Restrictions containing no modeled planned capacity | **~80%** | Most actions are pre-emptive or arrive after projects are approved |
	  | New York capacity exposed / delayed | **~1.4 GW / ~0.8 GW** | Most affected capacity is scheduled for 2028 or later |
	  | Total U.S. delay directly attributed to moratoriums | **~2.3 GW** | Local restrictions plus New York; excludes policy actions without a project-level delay |
	  | Forecast U.S. IT capacity delivered in 2027 | **38 GW** | 22 GW under vertical construction; 16 GW planned, mostly financed and in siteworks |
	  | Facilities in SemiAnalysis project model | **6,000+** | Tracked using property records, permits, power data, FOIA and satellite imagery |
	  | Statewide instruments | **21 attempts across 17 states; two in force** | 15 failed or carried over, three proposed, one passed but not in force |
	  | Firm behind-the-meter equipment orders | **75 GW** | From SemiAnalysis's prior power work; Texas is the largest destination |
- ## Why 20.1 GW Falls to 1.525 GW
	- | Local-pipeline filter | MW removed | Why it does not count as delayed |
	  |---|---:|---|
	  | Permits already in hand | **6,663 MW** | Moratoriums generally freeze new applications rather than revoke approvals |
	  | Pause expires before approval is needed | **5,945 MW** | Short restrictions end before out-year projects reach the relevant permit stage |
	  | Parcel not reached or rights already vested | **5,185 MW** | County rules stop at city boundaries, or the project has grandfathered rights |
	  | Counted under a statewide order | **320 MW** | Removed to prevent double counting |
	  | Excluded on other project-specific grounds | **501 MW** | Inactive projects, carve-outs, alternative pathways or unrelated schedule gates |
	  | **Actually delayed** | **1,525 MW** | The residual after parcel-level and approval-level review |
	- A restriction matters only if it reaches the exact parcel, is enacted when an approval is still needed, covers the proposed use, overlaps the development schedule, lacks a carve-out, and is the binding constraint rather than an unrelated equipment or litigation delay.
	- **Exposure is therefore not delay, and delay is not cancellation.** Developers can wait out short pauses, move jurisdictions, redesign configurations, litigate, use vested rights or secure an exemption.
- ## The Three Local Delays
	- | Project | MW reached by restriction | Estimated schedule slip |
	  |---|---:|---|
	  | AWS campus near Columbus, Ohio | **765 MW** | Three quarters |
	  | NorthPoint campus near Scranton, Pennsylvania | **720 MW** | Four quarters |
	  | CoreSite campus near Denver, Colorado | **40 MW** | Expansion frozen until May 21 2027 |
	- NorthPoint is the clean example of a binding moratorium: the parcel is inside the township, the June 2026 restriction covers data centers directly, the developer had not filed for the required special exception, and first-building construction had been scheduled for Q4 2026.
	- NorthPoint continues pursuing the site and proposed a **\$165M community-benefits package**. Even when a project survives, political friction can transfer part of its economics to host communities.
- ## Restriction Count Follows Growth Rather Than Predicting It
	- Michigan, Ohio, North Carolina and Georgia account for roughly half of local instruments. The clustering largely follows rapid data-center proposals rather than anticipating them.
	- **Michigan** leads with 45 enacted and seven proposed restrictions, yet carries effectively zero modeled pipeline exposure. Major campuses sit on industrial land where data processing is already permitted or obtained approvals before pauses began.
	- **Ohio** has 40 enacted moratoriums, 83% adopted in 2026. Critical IT capacity grew from 760 MW in 2022 to 1 GW in 2023, 2 GW in 2024 and 3 GW in 2025; seven moratoriums followed in 2025 and 33 through Aug 2026.
	- The Ohio backlash has an economic trigger: the report attributes a **25.7% YoY increase in average residential electricity bills** partly to data-center-driven PJM capacity costs.
	- Community opposition is self-reinforcing across nearby jurisdictions: hearing tactics, citizen groups and ordinance language travel regionally, making existing clusters more politically expensive even if aggregate MW continues growing.
- ## Public Acceptance Is the Durable Constraint
	- SemiAnalysis surveyed **1,274 U.S. registered voters** in Aug 2026, weighted to the Census population.
	- | Topic | Favorable | Unfavorable | Strongest negative response |
	  |---|---:|---:|---:|
	  | Data centers generally | **29%** | **46%** | 24% very unfavorable |
	  | A new data center in respondent's city or town | — | **46% opposed** | 30% strongly opposed |
	  | Artificial intelligence generally | **46%** | **34%** | 14% very unfavorable |
	- Voters are net-positive on AI but net-negative on its physical infrastructure. That gap implies recurring demands for ratepayer protection, full property taxes, water safeguards, local hiring and community-benefit payments.
	- The political risk is therefore more likely to appear as **higher project costs and longer pre-permit diligence** than as a nationwide construction ban.
- ## State Policy Is Narrower Than the Headlines
	- | State action | Scope | Modeled effect |
	  |---|---|---|
	  | New York EO 62 | Pauses discretionary environmental approvals for new projects of 50 MW+ through roughly Jul 2027 | 1.4 GW exposed; ~0.8 GW genuinely delayed |
	  | Texas audit | Pauses new ERCOT interconnection approvals while Batch Zero projects are verified | Base load largely preserved; studied and conditional load waits; BtM is exempt |
	  | Pennsylvania EO 2026-05 | Conditions DEP review on local approval and GRID requirements; removes fast-track treatment | Longer diligence for speculative projects, not a fixed-duration statewide moratorium |
	  | Oregon directive | Pauses unapproved use or transfer of state-owned property through Jul 1 2027 | No impact on the modeled pipeline because affected projects lack site control |
	- New York had nearly **12 GW of requests in the NYISO queue**, but its order reaches only projects still needing discretionary state permits. Stream's ~340 MW campus is delayed about six months; Urbacon's 135 MW about six months; Blockfusion's 300 MW about eight to ten months. TeraWulf's 300–400 MW and Riverview's 200 MW are not meaningfully delayed by the order itself.
	- Of 21 statewide attempts, the two in force are executive actions in New York and Texas. Broader legislative measures repeatedly died in committee, expired, were tabled, carried over or vetoed, showing how difficult permanent statewide bans are to enact.
- ## Texas: Queue Sorting, Not a Buildout Stop
	- ERCOT Batch Zero covers roughly **205 GW across 326 applicants**. The audit applies to large loads of 75 MW+; a separate community-impact review gathers data from unenergized computational loads of 25 MW+.
	- Already-energized and approved projects are unaffected. Advanced “base load” projects retain capacity and face at most about four months of administrative delay. “Studied load” lacks a final MW allocation and is genuinely delayed; excluded projects wait for a future batch.
	- **Seventeen facilities representing 6.6 GW** had cleared every other ERCOT gate and were working through verification. The report was targeted for Dec 10 with PUCT review Dec 17, although the larger system-wide study will not finish by its prior Apr 2027 target.
	- Galaxy Digital, Hut 8, IREN, Cipher and CleanSpark disclosed favorable conditional classifications for specific sites, illustrating the advantage of site control, financial security and completed studies.
	- The audit does not reach fully islanded projects. Every month of grid delay increases the option value of on-site generation and power-secured land.
- ## How Developers Route Around Restrictions
	- **Relocate** to a nearby jurisdiction, **redesign** to comply with new zoning, **litigate** exclusionary rules, or secure **jurisdictional exits and carve-outs**.
	- The Meta-linked Howell Township project withdrew its rezoning application with plans to reapply after the local ordinance is finalized—delay and redesign, not abandonment.
	- SpaceX had **444 acres de-annexed from Brownsville** before a proposed moratorium and paired the request with a **\$220M regional water-infrastructure commitment**. Scale and willingness to fund public infrastructure create negotiating leverage smaller developers lack.
	- Restrictions consequently favor well-capitalized hyperscalers and experienced developers over speculative entrants. The competitive moat is no longer just capital or compute access; it includes entitlements, municipal relationships and credible power plans.
- ## Equity Lens
	- **[[$VRT]] and [[$ETN]]**: the report leaves the 2026–27 construction forecast intact, weakening the thesis that moratorium headlines will erase ordered power and cooling equipment. Delayed projects are concentrated before procurement; active builds still need electrical distribution and thermal infrastructure.
	- **[[$GEV]] and on-site generation suppliers**: Texas policy explicitly exempts behind-the-meter projects, while 75 GW of firm BtM equipment orders already exist. Grid friction adds demand to multiyear-full turbine, genset and fuel-cell order books rather than subtracting from them.
	- **[[$BE]]**: fuel cells benefit where developers need modular power that avoids the interconnection queue and can clear local air-permitting constraints more easily than combustion turbines, although fuel availability and emissions rules remain site-specific.
	- **[[$CVX]] / [[$MSFT]]**: Chevron's 2.67 GW off-grid Project Kilby is designed to serve a roughly 2 GW Microsoft Permian campus—the clearest example in the report of policy increasing the value of an integrated, non-grid power solution.
	- **Hyperscalers**: [[$AMZN]], [[$META]], [[$GOOGL]] and [[$MSFT]] can spread projects across jurisdictions, fund infrastructure and litigate. Policy raises cost but can widen their advantage over less-capitalized developers.
	- **Entitled and powered land**: existing industrial zoning, vested rights and secured interconnections become scarcer assets. The premium should accrue to incumbent campuses and land already beyond discretionary approvals, not undifferentiated greenfield acreage.
- ## Where the Report Could Be Wrong
	- The underlying parcel and project database is proprietary, so the 1.525 GW result cannot be independently reconstructed from the PDF. SemiAnalysis also sells data-center forecasts and has an institutional incentive to emphasize pipeline resilience.
	- The forecast assumes today's mostly temporary, local rules remain the dominant form. A durable statewide construction ban, state preemption failure, or coordinated utility restrictions would invalidate the low-impact conclusion.
	- A project can be economically impaired without being counted as delayed: community payments, property taxes, litigation, redesign and more expensive BtM power reduce returns even if the opening date holds.
	- BtM is a routing mechanism, not a free bypass. Turbine lead times, gas-pipeline capacity, air permits and fuel-cell economics can replace grid interconnection as the binding constraint.
	- The voter data are the strongest warning: moratoriums have limited MW impact today, but **46% local opposition** gives politicians a durable constituency for tighter rules. The direction of policy risk is worse even if its current magnitude is small.
