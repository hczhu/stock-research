tags:: [[$INTC]], [[$TSM]], [[EMIB]], [[CoWoS]], [[advanced-packaging]], [[semiconductor]], [[AI-compute]], [[HBM]], [[capex]]
file-created-at:: 2026-11-03
file-updated-at:: 2026-11-09

- ## Intel EMIB vs. TSMC Advanced Packaging: Yield and Scale Are the Test
	- **Source**: User-provided X screenshot quoting an unnamed “Intel expert”; claims are not independently verified and should be treated as channel checks, not company guidance.
	- **Thesis**: Intel’s EMIB may offer cost and form-factor advantages for large chiplet/HBM packages, but low reported yields and very small external foundry revenue make execution—not the architecture—the key question. TSMC’s broader CoWoS/SoIC platform remains the established alternative.

- ## What the Source Claims
	- **EMIB investment and ramp**: About **$3.5B** of next-year capex would go to EMIB. Substrate yield reportedly improved from **~30% in Q2** to **45% in September**, with targets of **50% in Q4** and **60% in Q1 next year**; assembly yield was said to be **40.5%**.
	- **Capacity targets**: Reported EMIB capacity targets are **20K baseline / 50K stretch by end-2027**, rising to **80K baseline / 120K stretch by end-2028**. The post does not define the unit or clarify whether the figures refer to monthly throughput, so they should not be compared directly with other capacity estimates.
	- **Foundry economics**: Intel’s total next-year capex is estimated at **\$27–33B**, with a **\$30B midpoint**, mostly for 18A and 14A. The post says external-customer revenue is still **under 2%** of foundry revenue.
	- **Customer pipeline**: Tesla was described as negotiating a contract, with no deposit yet; Google, Microsoft, and Amazon were named as prospective customers. These are prospects, not confirmed awards.
	- **Relative cost positioning**: The source sees Intel as more cost-competitive for large-format, multi-chiplet, multi-HBM packages, while TSMC is stronger in low-power and mature-process products. It argues that labor and union costs at TSMC’s U.S. fabs could narrow the U.S.-manufacturing cost gap.

- ## Technology Context and Read-Through
	- Intel EMIB embeds small silicon bridges in the package substrate where dense die-to-die connections are needed, rather than using one large silicon interposer. This can suit large heterogeneous packages; Intel’s public brief describes EMIB as a production 2.5D interconnect technology. [Intel EMIB brief](https://www.intel.com/content/dam/www/central-libraries/us/en/documents/2025-07/emib-product-brief.pdf)
	- TSMC’s CoWoS uses an interposer-based 2.5D approach to integrate logic chiplets and HBM; its 3DFabric portfolio also includes SoIC for 3D die stacking. These are related but not identical architectures, and customer/package design determines the best fit. [TSMC CoWoS](https://3dfabric.tsmc.com/english/dedicatedFoundry/technology/cowos.htm) · [TSMC 3DFabric](https://3dfabric.tsmc.com/english/dedicatedFoundry/technology/3DFabric.htm)
	- The reported gap between substrate and assembly yields points to the substrate process as a potential ramp bottleneck. If accurate, low package yield would raise effective cost per good unit and constrain customer shipments even if nominal capacity expands.
	- **Commercial proof remains limited**: A prospect list and planned capacity are not revenue. The key validation is sustained yield improvement alongside customer qualification, deposits/contracts, and material external-customer sales.
	- The claimed cost advantage is application- and location-specific, not a blanket Intel-versus-TSMC cost conclusion. Comparing U.S. manufacturing economics should include yield, utilization, packaging scope, labor, and customer-specific design costs.
