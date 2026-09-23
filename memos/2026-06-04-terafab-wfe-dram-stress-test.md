- tags:: [[semiconductor]], [[WFE]], [[DRAM]], [[HBM]], [[AI infrastructure]], [[data-center]], [[capex]], [[$AMAT]], [[$ASML]], [[$KLA]], [[Morgan Stanley]]
  file-created-at:: 2026-06-04

- ## TeraFab WFE Stress Test — DRAM Equipment Demand from Large-Scale AI Compute Build-Outs
	- **Source**: Morgan Stanley SPE (semiconductor equipment) team, TeraFab illustrative analysis
	- **WFE**: Wafer Fab Equipment — the capital equipment (lithography, etch, deposition, inspection tools) required to manufacture semiconductors
	- **Thesis**: A single large AI compute facility ramping to 12 GW of annual output would require $33B of WFE in year one, with DRAM alone accounting for $14B — confirming AI data center deployment is a full-stack memory capacity buildout, not just a chip procurement story

- ## WFE Demand by Ramp Scenario

	| Ramp Scenario | Annual Compute Output | Total WFE (Year 1) | DRAM WFE (Year 1) | DRAM Share of Total WFE |
	|---|---:|---:|---:|---:|
	| Aggressive | 12 GW | ~$33B | ~$14B | ~42% |
	| Conservative | 3 GW | ~$8.25B (implied) | ~$3.5B | ~42% |

	- DRAM WFE share is consistent across scenarios (~42%), suggesting it is a structural proportion of total memory fab investment rather than a variable mix
	- At 3 GW, $3.5B of DRAM WFE from a **single facility** — multiple simultaneous AI data center buildouts would stack these numbers additively

- ## Key Observations
	- **Scale of a single facility**: $14B of DRAM WFE at 12 GW ramp is roughly equivalent to one full-scale DRAM fab expansion — implying AI data center buildout is creating demand for effectively one new DRAM fab's worth of equipment per large facility per year
	- **HBM is the critical path**: Within the DRAM WFE envelope, HBM remains the most constrained and strategically differentiated product — HBM requires additional TSV (through-silicon via) process steps vs. conventional DRAM, demanding incremental WFE beyond standard DRAM equipment
	- **AI DC = full-stack memory story**: The analysis explicitly frames AI data center deployment not as a chip demand story but as a memory capacity story — the GPU/ASIC is the headline, but DRAM WFE is the long-cycle enabling investment
	- **Linear scalability**: The 3 GW → 12 GW WFE relationship scales ~4× in line with compute output, suggesting WFE demand is roughly linear with deployed compute — no significant economies of scale in equipment intensity

- ## Investment Implications
	- **Semiconductor equipment (SPE)**: AMAT, ASML, KLA, Tokyo Electron, and Ulvac are the primary WFE beneficiaries; $14B of DRAM WFE per 12 GW facility is a meaningful incremental TAM on top of baseline memory capex cycles
	- **WFE demand is a leading indicator**: Equipment orders lead wafer output by 12–18 months (tool delivery + qualification); rising AI data center announcements today translate into WFE order books now
	- **TeraFab as a stress test, not a base case**: Morgan Stanley frames this as illustrative — but multiple hyperscalers simultaneously building large AI campuses makes the additive WFE demand plausible at scale
	- **DRAM capex cycle inflects upward**: The memory capex table in the MS semiconductor report (Samsung +20%, SK Hynix +42%, Micron +45% in 2026) aligns with this WFE demand framework — suppliers are already responding to the pull signal
	- **HBM TSV equipment is a sub-TAM**: HBM-specific bonding and TSV equipment (Besi, BE Semiconductor) captures incremental WFE above standard DRAM tools — not captured in simple DRAM WFE line items
