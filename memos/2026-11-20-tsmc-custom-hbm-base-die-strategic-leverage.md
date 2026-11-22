tags:: [[$TSM]], [[TSMC]], [[HBM]], [[custom-HBM]], [[NVHBM]], [[foundry]], [[N3]], [[CoWoS]], [[advanced-packaging]], [[GUC]], [[$3443.TW]], [[$NVDA]], [[$MU]], [[$000660.KS]], [[$005930.KS]], [[$INTC]], [[$META]], [[$AMD]], [[$MRVL]], [[semiconductor]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-20
file-updated-at:: 2026-11-22

- ## TSMC's stronger position in the custom HBM transition
	- **Source**: an AI assistant's answer supplied by the user (November 2026), a follow-up to [[2026-11-20-dram-commodity-vs-cpu-gpu-custom-hbm4-switching-friction]]. Its figures and dated reports are the answer's own. Where the repo has the same point, the matching memo is linked. Points the repo doesn't confirm are marked as unverified.
	- **Thesis**: TSMC is a major strategic winner of custom HBM, and with all three memory makers, not only SK hynix. But base dies bring in **modest direct revenue**. There is one base die under 12–16 DRAM dies, so base-die wafer volume is small. Even on N3, the answer puts it at about **\$4–7B a year, or 2–4% of revenue**. The bigger payoff is leverage. Custom HBM turns a memory component that used to be bolted onto TSMC's package into another high-margin, capacity-tight **N3 workload**. That ties memory makers, GPU designers and CoWoS packaging more tightly to TSMC.
	- **Framework**: judge TSMC's upside on two levels: **direct wafer math**, a single-digit revenue boost, and **system-level leverage**, which reinforces TSMC's hold on AI hardware.

- ## 1. Wafer math: modest revenue, but genuinely new demand
	- **Volume**: each HBM stack has one logic base die beneath 12–16 DRAM core dies of about the same size (about 140 mm²). Base-die wafers are therefore a small fraction of HBM DRAM wafers.
		- | Item | Estimate |
		  |---|---|
		  | HBM DRAM wafers, industry | **400K+ per month**: SK hynix about 180K, Samsung about 180K, Micron about 60K |
		  | Base-die wafers (DRAM wafers ÷ 12–16) | **About 25K–35K per month**, or about 300K–420K a year |
		  | Good dies per 300mm wafer | About 350–400 |
		  | HBM stacks those wafers can support | **About 100M–150M a year** |
	- **The move to a newer node drives the dollars**:
		- | Generation | TSMC node | Wafer price | Base-die revenue to TSMC | Share of TSMC revenue |
		  |---|---|---|---|---|
		  | Standard HBM4 (SK hynix's first base dies) | 12nm | Mature-node pricing | **About \$1–2B a year** | A rounding error |
		  | Custom HBM4E / NVHBM | N3P | **About \$19,500–22,000 per wafer**, before 5–10% price hikes in early 2027 | **About \$4–7B a year**, assuming 60–80% of global custom HBM4E base dies | **About 2–4%** |
		- The answer compares this with TSMC's **\$180B+ annualized revenue run rate**, noting that October 2026 alone was about \$17.8B.
	- **Why the demand is new, not cannibalized**: moving the memory controller and PHY onto the base die frees up to about **25%** of the compute die. AI chipmakers don't shrink their reticle-limited GPUs to save money. They fill the freed area with more compute cores. So base-die wafers are **new N3 demand**, not GPU silicon moved elsewhere.
	- **Memo calculation, sanity checks**:
		- \$4–7B ÷ \$180B = 2.2–3.9%, consistent with "2–4%". October's \$17.8B × 12 ≈ \$214B, so "\$180B+" is a conservative run rate.
		- At about \$20K per wafer, \$4–7B means about **200K–350K N3 wafers a year (17K–29K a month)**. That is close to the 25K–35K a month the answer estimates for the **entire** base-die market. Taken together, the figures assume most HBM base dies move to custom N3. That is the end state of the transition, not what will ship in 2027, when standard HBM4 on 12nm and Samsung's in-house 4nm still make up much of the volume.
		- The ratio of 400K DRAM wafers to 25K–35K base-die wafers assumes the base die is the same size as a core die and gets the same number of dies per wafer. A larger custom base die, or lower logic yield on N3, would raise the wafer count.

- ## 2. Where TSMC actually wins: strategic leverage
	- **All three memory makers, not just SK hynix**:
		- In **September 2026**, Micron confirmed it will outsource HBM4E base dies to TSMC, consistent with [[2026-09-04-hbm-base-die-becomes-a-foundry-business]].
		- **October 2026 reports** say Nvidia is pushing **all three vendors, including Samsung**, to make NVHBM base dies on **TSMC 3nm**, so that Nvidia keeps one standard PDK across suppliers. Update (2026-11-22): now sourced. [Seoul Economic Daily, October 18](https://en.sedaily.com/business/2026/10/18/samsung-to-use-tsmc-for-base-die-in-nvidias-custom-hbm) reported that Nvidia asked Samsung, SK hynix and Micron to use TSMC 3nm for NVHBM base dies. A friend's industry comment says the aim is to make the three suppliers interchangeable ([[2026-11-20-dram-commodity-vs-cpu-gpu-custom-hbm4-switching-friction]]). The report doesn't establish that all three are qualified at equal volume.
	- **It neutralizes Samsung's one-stop moat**:
		- Samsung's pitch has long been vertical integration: DRAM, 4nm/2nm foundry and advanced packaging under one roof.
		- If TSMC becomes the default logic foundry for HBM base dies, it already makes the compute dies (N3/N2) and does the CoWoS-L packaging. It would then hold **all three active layers of an AI accelerator**, which makes it even harder for hyperscalers to leave its ecosystem.
		- This reverses the earlier repo reading that custom HBM favors Samsung's turnkey model ([[2026-09-04-hbm-base-die-becomes-a-foundry-business]]).
	- **Pricing power from scarce N3 capacity**:
		- The answer says TSMC named HBM base dies as a new N3 customer in **Q1 2026**.
		- N3 lead times exceed **50 weeks**, and cleanroom buildout, not EUV tools, is the binding constraint through 2027.
		- Adding 20K–35K wafers a month of price-insensitive demand to N3 strengthens TSMC's hand on wafer price hikes and HPC surcharges for all its leading-edge customers.
		- See also [[2026-08-30-tsmc-across-the-board-price-increases-samsung-trigger]].
	- **Pull-through to CoWoS-L and GUC**:
		- Custom HBM4E frees enough edge space on the accelerator for up to **33% more HBM stacks** per package. That pushes packages toward larger, higher-margin CoWoS-L interposers, scaling from **5.5× toward 14× reticle by 2029**.
		- It also sends design-service and IP revenue to TSMC's subsidiary **GUC (Global Unichip)**, which co-developed TSMC's 3nm **C-HBM4E** base-die IP. TSMC's 3D DRAM report also names GUC as its custom-memory design partner ([[2026-11-08-tsmc-3d-dram-report-embedded-oxide-memory-not-commodity]]).

- ## 3. Forces limiting TSMC's share
	- **Cost friction for memory vendors**:
		- TSMC's HBM4 base dies reportedly cost **3–4× as much as the core DRAM dies** SK hynix makes in-house.
		- With TSMC raising 2027 prices, memory vendors have a strong reason to keep bargaining leverage.
		- **Late-August 2026 reports** said SK hynix was exploring **Intel Foundry** as a second source. SK hynix publicly denied this for HBM4E. The September base-die memo also recorded SK hynix "evaluating Intel Foundry as second source."
		- Intel hired former SK hynix CEO **Seok-Hee Lee** to run advanced packaging, which keeps that option open longer term.
	- **Samsung still has an opening with non-Nvidia ASICs**:
		- Nvidia can mandate TSMC 3nm for NVHBM. Hyperscalers building their own silicon have a financial and capacity reason to let Samsung run a turnkey in-house flow, which avoids TSMC's N3 queue and markup.
		- Examples: **Meta**, reportedly developing custom HBM4E with Samsung on a Samsung 2nm base die, and **AMD**.

- ## Summary of the answer's view
	- | Level | Size for TSMC | Mechanism |
	  |---|---|---|
	  | Direct base-die wafers | **About \$1–2B a year** (12nm HBM4) rising to **about \$4–7B** (N3 custom HBM4E), about 2–4% of revenue | Limited by the 1-to-12+ die ratio, but new demand |
	  | N3 pricing | Applies across all leading-edge customers | Price-insensitive demand in a cleanroom-constrained node |
	  | Packaging and design services | Larger CoWoS-L interposers, GUC IP and design revenue | Up to 33% more stacks per package |
	  | Ecosystem lock-in | Not quantified | Compute die, base die and packaging all at TSMC. Weakens Samsung's turnkey pitch |
	  | Offsets | Not quantified | SK hynix's Intel second-source option. Samsung's turnkey offer to Meta and AMD custom silicon |
	- **The answer's bottom line**: TSMC won't double its revenue from HBM base dies. Custom HBM still makes TSMC more central to AI hardware.

- ## Related in the repo
	- **Base-die strategies by vendor, and who captures the value**: [[2026-09-04-hbm-base-die-becomes-a-foundry-business]].
	- **Why custom HBM is harder to switch than DDR**: [[2026-11-20-dram-commodity-vs-cpu-gpu-custom-hbm4-switching-friction]].
	- **TSMC overview**: [[TSMC-TSM-thesis]], [[TSM-2026-Q2]].
	- **SK hynix's stacking moat**: [[2026-08-21-sk-hynix-hbm-history-mr-muf-moat]].
