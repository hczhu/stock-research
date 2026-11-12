tags:: [[$UBER]], [[$DASH]], [[Uber]], [[Uber Eats]], [[DoorDash]], [[food-delivery]], [[unit-economics]], [[sum-of-the-parts]], [[valuation]], [[SBC]], [[marketplaces]], [[ai-model:Opus5.5]], [[ai-effort:medium]]
file-created-at:: 2026-11-07
file-updated-at:: 2026-11-07

- ## Uber Delivery vs DoorDash: once costs are treated the same way, per-order margins are about equal
	- **Source**: MBI Deep Dives (Mostly Borrowed Ideas), per-order economics comparison after Q3 2026 results. Uber's Delivery order count is MBI's **estimate**, not a disclosed figure. The per-order and margin figures depend on it, and Uber's unallocated costs are spread across segments by MBI's own method. Related: [[2026-07-25-waymo-uber-trip-market-platform-thesis]], [[2025-02-13-stratechery-dara-khosrowshahi-uber-aggregation-autonomy]], [[2024-10-01-stratechery-uber-waymo-transportation-aggregator]].
	- **Thesis**: Uber's reported Delivery margin (3.7% of Gross Bookings) looks better than DoorDash's (3.1%), but the two figures leave out different costs. Uber's excludes corporate costs, and DoorDash's excludes SBC. Charging both with corporate costs and SBC, the two platforms earn **about the same margin: ~2.1% of order value for Uber Delivery vs ~2.3% for DoorDash**. Their margins, growth and scale are now similar, so **DoorDash's valuation is a reasonable benchmark for Uber Delivery**. Subtracting that from Uber's market value shows what the market is paying for Mobility.
- ## Estimating Uber's Delivery order count
	- Uber reports total Trips (**4.06B in Q3 2026**) but doesn't split them between rides and deliveries.
	- **MBI's method**: Uber's February 2024 Investor Update disclosed, for each segment, growth in consumers and in trips per consumer from Q4'21 to Q4'23. Only one Mobility/Delivery mix matches those figures and total trip growth. MBI carries it forward with the Mobility trip growth Uber has disclosed since, assuming the Q3'24 mix equals Q4'24.
	- **Result**: Delivery is **~22% of trips**, or **~900M orders** in Q3'26 (4.06B × 22% ≈ 893M).
	- **Sensitivity**: one point of mix moves the per-order figures by **~4–5%** (1/22 ≈ 4.5%). The conclusion that the margins are about equal is safer than any single per-order number.
- ## Per-order economics, Q3 2026
	- | Per order | Uber Delivery (MBI est.) | DoorDash |
	  |---|---|---|
	  | Gross Bookings per order | ~\$31 | ~\$35 (implied from \$0.80 at 2.3%) |
	  | Kept after courier pay and consumer incentives | ~\$3.51 (~11% of GB) | n/a |
	  | After other segment costs (segment operating income) | ~\$1.17, up from ~\$1.04 a year ago | n/a |
	  | Allocated corporate G&A and platform R&D | −~\$0.57 | Already included |
	  | Adjusted EBITDA less SBC | **~\$0.66** (after adding back depreciation) | **~\$0.80** |
	  | As % of order value, after SBC | ~2.1% | ~2.3% |
	  | As % of order value, before SBC | ~3.0% | ~3.1% |
	  | Headline reported margin | 3.7% (before corporate costs) | 3.1% (before SBC) |
	- **Corporate costs are the big adjustment**: Uber doesn't allocate ~\$1.1B a quarter of corporate G&A and platform R&D to its segments. MBI allocates it by share of Gross Bookings, which costs Delivery ~\$0.57 an order, almost half of its segment operating income. The \$0.57 implies Delivery is ~47% of Uber's Gross Bookings (\$0.57 × ~900M ≈ \$0.51B of \$1.1B).
	- **Matching DoorDash to Uber's basis**: MBI's DoorDash piece showed \$0.76 per order, but that figure also deducted legal, transaction and restructuring costs, which Uber excludes. On Uber's basis (adjusted EBITDA less SBC), DoorDash earns **\$0.80**.
	- **Gap in dollars, not in margin**: DoorDash's \$0.14 lead per order is mostly a larger basket (~\$35 vs ~\$31). As a share of order value the gap is only ~0.2 points, smaller than the mix uncertainty in the Uber estimate.
	- **Uber is improving**: segment profit per order rose ~12% YoY (\$1.04 → \$1.17). The source doesn't break down the drivers; ads, membership and density are the usual candidates.
- ## Valuation: using DoorDash to value Uber's parts
	- **Method**: MBI compares the two on reported adjusted EBITDA less SBC. SBC is treated as a real, recurring cost. Legal, restructuring and acquisition costs are excluded, as both companies do.
	- **Scale**: over the last twelve months, Uber Delivery earned **~92% of DoorDash's** adjusted EBITDA less SBC.
	- **Implication**: valuing Uber Delivery at DoorDash's multiple gives roughly 92% of DoorDash's enterprise value. Uber's enterprise value minus that amount is what the market implicitly pays for Mobility (plus Freight). If the result looks low compared with Mobility's earnings, the market is either discounting Mobility for robotaxi disruption ([[2026-07-25-waymo-uber-trip-market-platform-thesis]]) or valuing Uber Delivery below DoorDash.
	- **Why the comparison is reasonable**: the businesses now have similar margins, growth and scale. That is a change from a few years ago, when Uber Delivery was widely seen as the weaker, subscale player.
- ## Where the comparison is weak
	- **The allocation is a choice**: allocating corporate costs by Gross Bookings is MBI's method. Platform R&D supports both segments, but Mobility may use more of it (mapping, pricing, autonomous partnerships). Allocating by revenue or headcount would change Delivery's figure. The \$0.57 is the largest single adjustment, and it is an estimate.
	- **Not the same business mix**: Uber Delivery includes more international markets and grocery and retail; DoorDash includes Wolt, Deliveroo and its own non-restaurant push. Equal margins in total can hide different margins by market.
	- **Shared costs favor Uber**: a standalone Uber Delivery would need its own corporate functions, likely costing more than the allocated \$0.57. Shared courier networks, the Uber One membership and cross-selling with Mobility are advantages DoorDash can't copy, and they don't show up in a per-order margin comparison.
	- **Valuing it like DoorDash assumes the market would**: a sum-of-the-parts discount for a combined company is common, so implied Mobility value may be understated, not just the Delivery value overstated.
