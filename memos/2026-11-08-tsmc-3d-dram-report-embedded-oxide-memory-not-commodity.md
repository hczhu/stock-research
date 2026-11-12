tags:: [[$TSM]], [[TSMC]], [[$NVDA]], [[$MU]], [[$000660.KS]], [[$005930.KS]], [[DRAM]], [[3D-DRAM]], [[HBM]], [[SRAM]], [[embedded-memory]], [[oxide-semiconductor]], [[BEOL]], [[SoIC]], [[hybrid-bonding]], [[GUC]], [[foundry]], [[ai-model:Opus5.5]], [[ai-effort:medium]]
file-created-at:: 2026-11-08
file-updated-at:: 2026-11-08

- ## TSMC "entering DRAM": most likely embedded cache memory, not a fourth commodity DRAM maker
	- **Source**: User-provided bundle: (1) an industry commentator's rebuttal (unnamed, citing conversations with industry experts) of the claim that TSMC will disrupt the big three; (2) Tom's Hardware, Anton Shilov, "TSMC denies exploring 3D DRAM at Nvidia's request" (Nov 7, 2026); (3) Reuters summary (Nov 6, 2026) of The Information's original report. The Information's claims rest on two unnamed people; TSMC's statement is on the record. Related: [[2026-09-04-hbm-base-die-becomes-a-foundry-business]], [[2026-07-03-sram-renewed-life-ai-memory-architecture]], [[2026-06-07-dram-deep-dive-hbm-3d-dram-memo]], [[2026-11-08-memory-cycle-3d-dram-tsmc-wechat-discussion]], [[2026-11-05-veteran-investor-memory-pe3-not-cheap-lta-skepticism]].
	- **Thesis**: The headline "TSMC to make 3D DRAM for Nvidia" has been read as a new supplier coming to break the memory shortage. The evidence points elsewhere. TSMC has no DRAM IP, patents or process, and denies it is leaving logic. What it has published is a **1T1C oxide-semiconductor memory built into the wiring layers of a logic chip**, aimed at **replacing SRAM as on-chip cache**, in small volumes. "3D DRAM" means two different things here, and that ambiguity drives the confusion. For memory stocks this isn't a supply threat within the current cycle. For TSMC, the realistic way to capture memory value is base dies, hybrid bonding and embedded memory, not DDR or LPDDR fabs.
- ## What was reported
	- **The Information (via Reuters)**: TSMC recently started planning **3D DRAM** production at the request of **Nvidia**, its largest customer. Options include new fabs or **buying and converting an existing fab**, as Micron did this year. Timing is unclear. The effort is reportedly led by **Hsu Kuo-chin**, the VP for advanced packaging and former head of Micron's Taiwan operations.
	- **TSMC's response**: "TSMC focuses on our core business at all times, which is dedicated IC foundry ... Our mission is to be the trusted technology and capacity provider of the global logic IC industry." It calls itself a pure-play logic foundry, which is effectively a denial.
	- **Context**: the AI-driven shortage has turned memory from a commodity into a strategic input that decides whether a company can ship. That gives Nvidia a clear reason to want another supplier, or at least the appearance of one.
- ## Two meanings of "3D DRAM"
	- | | Commodity 3D DRAM | TSMC's embedded oxide memory |
	  |---|---|---|
	  | What it is | Memory cells stacked vertically on a standalone DRAM die to raise capacity per wafer | 1T1C memory array built in the back-end-of-line (BEOL) interconnect layers above a logic chip; "3D" because it sits on top of the logic |
	  | Who is working on it | Micron, Samsung, SK hynix | TSMC (2025 VLSI Symposium paper; more than five years of work per the commentator) |
	  | Replaces | Planar DRAM (DDR, LPDDR, HBM core dies) | **On-chip SRAM cache** |
	  | Volume | Huge, commodity bit volumes | Small; sold as part of the logic chip |
	  | Timing | Years away even for the big three; Micron plans **at least four more planar nodes** first | Test chip demonstrated; product timing not disclosed |
	- **TSMC's test chip (VLSI 2025)**: oxide-semiconductor select transistors and capacitors made at low temperature so they can be built over finished logic. Logic and memory on one die, running at **0.75V**, with **retention over 128ms**, **random read/write cycle under 8ns** and **endurance above 10¹⁴ cycles**. TSMC positions it as cache with **higher density than SRAM** at low power and latency.
	- **Why that matters**: SRAM is taking a growing share of die area on leading-edge AI chips and barely shrinks with each new node. A denser on-die memory that TSMC can add to its own logic process is valuable to Nvidia and every other customer. It is a feature of the logic chip TSMC already sells, not a separate memory business.
	- The commentator's conclusion: "Anyone saying TSMC will make DDR or LPDDR has no idea what they're talking about."
- ## Why TSMC is unlikely to make commodity DRAM
	- **No technology base**: DRAM uses a completely different process from logic, and 3D DRAM adds the difficulty of stacking cell layers while controlling defects and yield. Tom's Hardware's view: it is "hardly possible" to develop a 3D DRAM process without a competitive planar DRAM process, which TSMC doesn't have.
	- **Too late for the shortage**: even if it started now, 3D DRAM couldn't relieve the shortage for **at least five years**.
	- **The acquisition route is only partial**: buying a small specialty DRAM maker would bring fabs and some IP, but not leading-edge nodes. TSMC would still need billions of dollars and years of R&D.
	- **Cycle risk**: shortages invite capacity expansion that ends in oversupply. That would add commodity price swings to a business valued for steady pricing (see the TSMC vs memory comparison in [[2026-11-05-veteran-investor-memory-pe3-not-cheap-lta-skepticism]]).
	- **Customer conflict**: SK hynix uses TSMC for HBM4 logic base dies. Competing with memory makers would put that relationship, and TSMC's packaging work with all three, at risk.
	- **Antitrust**: combining leading-edge logic, advanced packaging and memory could draw scrutiny over self-preferencing, although another supplier would also add competition to a three-company market.
- ## How TSMC can capture memory value without making DRAM
	- **HBM base dies**: from HBM4 the bottom die is logic on a foundry node, which already shifts part of each HBM stack's value to TSMC ([[2026-09-04-hbm-base-die-becomes-a-foundry-business]]).
	- **SoIC hybrid bonding**: stacking memory directly on processors, the direction also taken by d-Matrix's accelerator on custom DRAM.
	- **Custom memory with partners**: designs with GUC and the established DRAM makers, where TSMC supplies logic and integration and the memory makers supply cells.
	- **Embedded oxide memory**: the SRAM replacement above, which raises the value of each TSMC wafer instead of adding bit supply.
- ## What it means for the stocks
	- **Memory makers (Micron, SK hynix, Samsung)**: if the headline caused selling, it was misread as new supply. No credible TSMC DRAM bits exist within this cycle. The longer-term risk from 3D DRAM is that whichever of the big three, or a startup, gets there first reshapes shares among them, which is the point in [[2026-11-08-memory-cycle-3d-dram-tsmc-wechat-discussion]].
	- **TSMC**: the upside is more value per logic wafer (embedded memory, base dies, bonding), not a memory segment. A real move into commodity DRAM would hurt the stock's valuation, since it would bring memory-style cyclicality into the business.
	- **Nvidia**: the report fits Nvidia's interest in putting pressure on memory pricing and getting more memory closer to compute. A denser on-die cache would also reduce how much each chip depends on external memory bandwidth for some workloads.
	- **What would change the reading**: TSMC buying a DRAM fab or company, hiring DRAM process teams at scale, or Nvidia disclosing a memory supply deal with TSMC. TSMC's denial and the VLSI paper both point the other way for now.
