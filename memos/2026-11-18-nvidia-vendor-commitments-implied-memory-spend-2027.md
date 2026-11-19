tags:: [[$NVDA]], [[$000660.KS]], [[$005930.KS]], [[$MU]], [[HBM]], [[DRAM]], [[purchase-commitments]], [[supply-chain]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-19

- ## Nvidia's vendor commitments and the implied memory spend for 2027
	- **Sources**:
		- A user-provided news excerpt on Nvidia's Q3 FY2027 commitments (publication not given).
		- The owner's memory-share estimate.
		- Supporting figures from [[NVDA-2026-Q3]], [[2026-09-11-nvidia-backstop-universe-credit-support]], [[2026-06-02-hbm-share-of-ai-chip-component-spend]] and [[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]].
	- **Fiscal calendar**: Nvidia's FY2028 runs from February 2027 to January 2028, so it is roughly calendar 2027.
	- **Thesis**: Nvidia's spending commitments jumped by \$152B in a quarter, to \$518B, partly because memory chips cost more. Most of the increase goes to component suppliers, with **\$203B of component spending planned for FY2028**. At the rack-level memory share of 25%, that is about **\$50B paid to the three memory makers in 2027**. That 25% is likely a floor for Nvidia's own purchases.

- ## The commitment numbers
	- | Item | Prior quarter (Q2 FY27) | Latest (Q3 FY27) | Source |
	  |---|---|---|---|
	  | Total spending commitments (excludes guarantees) | \$366B | **\$518B** (+\$152B, +42%) | News excerpt |
	  | Of which supply and capacity (purchase) commitments | \$279B, up from \$119B in Q1. Primarily memory and upstream capacity, 96% due by FY2029 | **\$390B** (+\$111B) | Q2: SemiAnalysis, "Nvidia's Backstop Universe," Sep 11, 2026, from Nvidia's Q2 FY27 disclosures ([[2026-09-11-nvidia-backstop-universe-credit-support]]). Q3: Nvidia ([[NVDA-2026-Q3]]) |
	  | Data-center lease and cloud-service commitments | — | \$102B, including the \$32B below | Nvidia, Q3 call (Kress: "a little over \$100B"); \$102B per a user-provided source |
	  | Of which neocloud agreements | — | \$32B | Nvidia, Q3 call |
	  | **Component suppliers, FY2028 only** | — | **\$203B** | News excerpt |
	  | Guarantees (separate from spending commitments) | — | \$118B, including \$105B for PORTS-Pike | Nvidia, Q3 call |
	- The excerpt says the majority of the \$152B increase goes to component suppliers, especially for next year, and attributes part of the rise to more expensive memory chips.
	- **Definitions vary by source**: the Q2 breakdown comes from SemiAnalysis and the totals come from the news excerpt. The rows may not add up exactly to each total.

- ## The owner's estimate: memory at 25% of commitments
	- The 25% rounds memory's roughly **26%** share of the NVL72 rack bill of materials for Vera Rubin (VR200; 25.7% per Morgan Stanley), up from 9% on GB300 ([[2026-06-02-hbm-share-of-ai-chip-component-spend]], [[2026-06-01-memory-super-cycle-x-thread-and-memo]]).
	- | Period | Commitment base | Memory at 25% | Owner's figure |
	  |---|---|---|---|
	  | FY2028 (about calendar 2027) | \$203B of component spending | **\$51B** | **\$50B** |
	  | After FY2028, owner's method | \$518B − \$203B = \$315B of all remaining commitments | \$79B | **\$80B** |
	  | After FY2028, purchase commitments only | \$390B − \$203B = \$187B | **\$47B** | — |
	- **Which base to use after FY2028**: the owner's \$80B applies 25% to all remaining commitments. That base includes about \$102B of data-center leases and cloud services, \$32B of it with neoclouds, which contain no memory. Applied to purchase commitments alone, 25% gives about **\$47B** (memo calculation). That amount also covers the rest of FY2027 (Q4) as well as FY2029 and later.

- ## Why 25% is probably a floor
	- | Memory share | FY2028 memory spend (on \$203B) | Basis |
	  |---|---|---|
	  | 25% | \$51B | Memory's share of the Vera Rubin rack BOM, which includes rack, cooling and power parts that Nvidia may not buy itself |
	  | 40% | \$81B | Midpoint between the rack and chip views |
	  | 50% | \$102B | HBM is at least 50% of packaged-GPU cost, by a SemiAnalysis estimate ([[2026-10-08-ieee-hbm-dram-shortage-supply-response]]) |
	- **Memory dominates Nvidia's own purchasing**: SemiAnalysis's commitment table describes Q2's \$279B of supply and capacity commitments as primarily memory and upstream capacity, and attributes most of the quarter's \$160B jump (from \$119B) to memory ([[2026-09-11-nvidia-backstop-universe-credit-support]]). It gives no exact memory share. Nvidia's purchases are weighted toward GPU packages and memory, not the full rack, so the share in its own commitments is likely above the rack-level 25%.
	- **Nvidia buys more than HBM**: it also buys LPDDR for Vera CPUs and SOCAMM modules, and GDDR for other products. This adds to the memory total.

- ## Split across the three memory vendors
	- Applying Daishin's estimated 2026 shares of Nvidia HBM4 ([[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]]) to the owner's \$50B for 2027 (memo calculation):
		- | Vendor | Share of Nvidia HBM4, 2026 (Daishin) | Implied 2027 Nvidia memory revenue at \$50B |
		  |---|---|---|
		  | SK hynix | 55% | About \$27.5B |
		  | Samsung | 28% | About \$14B |
		  | Micron | 17% | About \$8.5B |
	- **Caveats**: shares will shift in 2027. Counterpoint expects Samsung to retake the No. 1 HBM revenue position in 2027, and the split covers HBM only. Prepayments and long-term agreements make these flows stickier than ordinary purchase orders ([[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]]).
