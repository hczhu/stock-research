- tags:: [[advanced-packaging]], [[CoWoS]], [[EMIB]], [[TSMC]], [[Intel]], [[semiconductor]], [[AI-compute]], [[HBM]], [[TPU]], [[packaging]], [[chiplets]]

- **Source**: Semi-Doped podcast — Austin Lines & Vick Shaker (Vick's Newsletter). Episode recorded Friday June 13, 2025 (pre-published). Topic: Advanced Packaging — CoWoS vs EMIB.

- ## Core Thesis: Packaging IS the Chip Now

	- For most of semiconductor history, packaging was a "necessary evil" — mechanical protection and electrical connection, outsourced to low-margin OSATs with no design input. It was unglamorous, boring, capex-light.
	- The transition: packaging → performance limiter (RF parasitics with wire bonds) → design input (flip chip relieved parasitic constraints) → **part of the chip** → **the chip itself**.
	- Today, for AI accelerators: **there is no chip without the packaging**. CoWoS and EMIB are not afterthoughts — they determine whether you can stitch together the compute needed to train and run frontier models.

- ## Packaging Basics — The Foundation

	- ### Why Packaging Exists
		- Silicon dies must be: (1) electrically connected to the outside world (PCB, power, signals), (2) thermally managed, (3) mechanically protected from the physical environment (ESD, moisture, shock).
		- The die is never exposed in a finished product — you would have to cut off the packaging to see bare silicon.

	- ### Wire Bonding (Simple Packaging)
		- Oldest method: literal metal wires from PCB leads to the die's edge pads.
		- Still used today for **power chips** (need to carry high current; big thick wires work well).
		- Downsides: labor-intensive, error-prone, long wire = high resistance + high parasitic inductance and capacitance. Terrible for RF/high-speed work.

	- ### Flip Chip (Simple → Intermediate)
		- Revolution of the 1990s: flip the die upside down, attach solder micro-bumps directly to the PCB.
		- Shorter connection distance → dramatically lower parasitics (R × C = τ) → chips work better without redesigning for package.
		- Key design insight (Vick): with flip chip, you design the chip and it works as-is. Wire bonds force you to account for package parasitics in the design.
		- Over time: solder ball pitch shrank → more connections per unit area → enabled thousand-pin I/O counts.

	- ### Industry Structure: Foundry → OSAT → Advanced Packaging Blurring
		- Traditional supply chain: **Fabless** (design) → **Foundry** (TSMC: front-end wafer fab) → **OSAT** (back-end packaging + test).
		- OSAT = Outsourced Semiconductor Assembly and Test. Key players: **Amkor, ASE, SPIL, PowerTech**.
		- OSATs handled simple packaging cheaply; foundries delivered finished wafers and stepped away.
		- **Advanced packaging changed the economics**: it requires the same fab tooling, lithography, and process know-how as front-end logic. This brought TSMC into packaging and is now pulling OSATs up into advanced packaging — both directions converging.
		- OSATs (e.g., Amkor) are actively moving toward advanced packaging to capture the higher-margin work.

- ## Why Advanced Packaging? The Reticle Limit

	- ### The Physical Constraint
		- Maximum die size = **858 mm² (26mm × 33mm reticle)**. This is set by the exposure area of the lithography system — you cannot pattern a larger die in a single shot.
		- The H100 was already at this limit.
		- To add more compute, you must stitch multiple reticle-sized dies together and make them behave as one piece of silicon.

	- ### 2D / 2.5D / 3D Taxonomy
		- | Dimension | What it means | Example |
		  |---|---|---|
		  | 2D | Single die on substrate (flip chip) | Traditional SoC |
		  | 2.5D | Multiple dies side-by-side on a shared passive interposer | GPU + HBM on silicon interposer |
		  | 3D | Active dies stacked vertically | HBM internally (8–12 DRAM dies stacked) |
		- HBM is **3D internally** (DRAM dies stacked via TSVs) but the HBM + GPU assembly is **2.5D** (side by side on an interposer). The 2.5D terminology is confusing precisely because of this nesting.
		- This memo focuses on 2.5D advanced packaging.

	- ### HBM Interconnect Density Escalation
		- HBM3: **1,024 parallel signal lanes** per stack to the GPU.
		- HBM4: **2,048 parallel signal lanes** per stack.
		- At these pin counts, routing on organic PCB-like substrates is physically impossible. You need semiconductor-grade metal patterning at micron-scale pitch — which is the fundamental reason advanced packaging requires a wafer fab process.

	- ### The Organic Substrate Problem
		- Organic substrates (PCB-like materials): cheap, large, but **cannot pattern fine-pitch metal lines**. Organic materials also suffer from dimensional instability — they warp, shrink when heated, absorb moisture — so patterned wires move, short, or disconnect.
		- Foundry-class silicon: expensive, reticle-limited, but enables micron-scale routing with excellent stability.
		- This trade-off is the engineering problem that drove all three CoWoS variants and EMIB.

- ## CoWoS (Chip on Wafer on Substrate) — TSMC's Approach

	- TSMC entered advanced packaging in the late 2000s / early 2010s; first production with FPGAs. Now the dominant advanced packaging provider for all AI accelerators.
	- Three-layer sandwich: **Die (GPU/accelerator)** → **Interposer layer** (where fine routing happens) → **Organic substrate** (connects to PCB / power delivery).
	- The interposer is the key differentiator across the three CoWoS variants.

	- ### CoWoS-S: Silicon Interposer
		- Middle layer = large silicon wafer with no transistors, only metal routing layers.
		- **Pros**: finest routing pitch possible (silicon is ideal for this); fully proven at AI accelerator scale.
		- **Cons**: (1) Expensive — silicon wafers used purely for routing, not compute. (2) **Reticle-limited** — the interposer itself must be patterned in a fab, so the package cannot exceed ~**3.3× reticle size** (~2,800 mm²). This was the first-generation ceiling.
		- Waste: cutting large square/rectangular packages out of circular 300mm wafers leaves huge unusable wafer area (Vick's pancake/cookie-cutter analogy).

	- ### CoWoS-R: Organic RDL Interposer
		- Middle layer = organic RDL (Redistribution Layer) — polyimide dielectric with 2–3 patterned metal levels.
		- **Pros**: cheaper than silicon; not restricted by reticle size (RDL is a different, non-fab process).
		- **Cons**: routing pitch is too coarse for GPU-class AI accelerators; organic instability limits achievable pitch.
		- Application: lower-cost chips (automotive, mid-range mobile) where AI-grade bandwidth is not required.

	- ### CoWoS-L: Local Silicon Bridges (Hybrid)
		- Middle layer = organic substrate (like CoWoS-R) + small embedded silicon bridges only **where fine routing is needed** between adjacent dies.
		- Power/bulk signals: routed through cheap organic material.
		- Die-to-die high-density signals: routed through tiny embedded silicon bridges.
		- **Pros**: (1) Silicon-class routing density at die interfaces. (2) Breaks the reticle size limit — bridges are tiny (thousands per wafer, high yield), so the overall package can grow far beyond what a silicon interposer could cover. (3) Better cost than CoWoS-S.
		- Austin's Iowa roads analogy: gravel (organic) everywhere except paved (silicon) roads in town — use the best material only where it's needed.
		- Note: TSMC did not originate the bridge concept — **Intel's EMIB predates CoWoS-L**. TSMC adapted the approach.

	- ### CoWoS Size Roadmap
		- | Generation | Package size | Notes |
		  |---|---|---|
		  | Gen 1 (CoWoS-S) | ~3.3× reticle (~2,800 mm²) | First AI accelerators |
		  | Current (CoWoS-L, Blackwell Ultra / Rubin-class) | ~5.5× reticle | 2 GPU dies stitched |
		  | Next gen | ~9.5× reticle | Planned |
		  | System on Wafer (SoW) | ~40× reticle | Future; no firm timeline |
		  | Chip on Panel on Substrate (CoPoS) | Panel-scale | TSMC targets **2028–2029** |
		- Rubin: expected **4 GPU dies** stitched together (up from 2 in Blackwell).

- ## EMIB (Embedded Multi-die Interconnect Bridge) — Intel's Approach

	- ### Core Concept
		- Intel invented the bridge concept and has used EMIB for **~10 years** — shipping in Sapphire Rapids, Granite Rapids, and early FPGAs (millions of chips shipped).
		- Two-layer structure: **Dies** directly on **organic substrate** with **tiny silicon bridge chips embedded into the substrate**.
		- No separate interposer layer at all — bridges are pushed (embedded) into the substrate only where die-to-die fine routing is needed.
		- Vick's analogy: pushing crackers into Jell-O. The bridge chip sinks into the organic substrate, and dies are connected to it from above.

	- ### EMIB Variants
		- **EMIB-T** (TSV): through-silicon vias run vertically through the bridge → enables power and high-speed signals to pass through the bridge to the die. Required for AI accelerator integration.
		- **EMIB-M** (MIM capacitors): Metal-Insulator-Metal bypass capacitors embedded in the bridge → clean power delivery by filtering power supply noise at the point of use.

	- ### Structural Advantages vs. CoWoS
		- | Advantage | Mechanism |
		  |---|---|
		  | **2 layers vs. 3** | No separate interposer → lower material cost, fewer process steps, less waste from interposer dicing |
		  | **Panel format** | Substrates built on ~500×500mm square panels vs. circular 300mm wafers → ~5–6× area per panel, near-zero rectangular waste (no pancake-cookie-cutter problem) |
		  | **Scalability** | Bridges are tiny rectangles; you can conceptually tile any number of dies (3×3, 4×4 grid) with bridges at every interface — not limited by interposer size |
		  | **Yield** | Small bridge = small defect probability per bridge; bridges independently yield-tested |
		  | **External customer flexibility** | Intel Foundry offers EMIB as a pure packaging service — customers can bring dies fabbed at TSMC and have Intel package them with EMIB (no need to commit to Intel Foundry logic) |

	- ### EMIB Size Roadmap
		- Current EMIB-T: **~8× reticle**
		- 2028 target: **>12× reticle** (~120mm × 180mm form factor)
		- Comparison: TSMC's next CoWoS generation is targeting ~9.5× reticle; EMIB's 2028 target of >12× would be ahead.

	- ### Yield Debate
		- Reported EMIB yield: 90–95%. Critics argue packaging yield must be effectively 100% because packaging failures destroy fully-fabricated dies (reticle-sized, 2–3nm process).
		- Counter-argument: Intel has shipped EMIB internally for a decade across millions of chips. Original EMIB yield is certainly production-grade. The 90% figure likely refers to newer EMIB-T/M variants still ramping. TSMC's CoWoS yield is not publicly reported but must be extremely high given universal industry adoption.

- ## Google TPU + MediaTek + Intel EMIB

	- **The news**: Google is booking ~**3 million TPUs** to be packaged using Intel EMIB, targeting **2028** delivery. The arrangement runs through **MediaTek** — Google's custom ASIC partner — who then uses Intel's advanced packaging for the final assembly.
	- **Strategic implication**: this is the first major AI customer publicly committing to EMIB at scale for inference/training chips. Validates EMIB as a production path for AI accelerators beyond Intel's own chips.
	- **MediaTek vs. Broadcom**: MediaTek's rise as a custom ASIC + packaging integrator for Google is a direct competitive threat to Broadcom's custom ASIC model (e.g., Google's prior TPUs used Broadcom packaging). Cited as a partial explanation for Broadcom stock weakness.
	- **SK Hynix**: also reportedly testing EMIB for HBM integration.
	- **Intel Foundry CFO David Zinsner**: advanced packaging alone is generating "**billions of dollars worth of commitments**." Advanced packaging capacity is in New Mexico.

- ## Intel Foundry's Packaging-Only Business Model

	- Intel Foundry is explicitly offering EMIB as a **standalone packaging service** — customers bring dies from any foundry (TSMC, Samsung, etc.) and Intel provides EMIB packaging. This decouples the packaging decision from the logic fab decision.
	- This lowers the barrier to EMIB adoption: customers can test EMIB on TSMC-fabbed dies without committing their entire chip supply chain to Intel Foundry.
	- Potential future opportunity: Intel has a strong photonics/optics capability that could combine with EMIB to enable **co-packaged optics (CPO)** — packaging optical engines directly alongside compute dies. Not yet the focus (lip-bü era priorities are 18A → 14A logic wins), but the technical foundations exist.

- ## Key Investment Takeaways

	- **CoWoS is the incumbent** — dominant for all AI accelerators today, massive volume, proven yield, deep integration with Nvidia/AMD chip designs. The bottleneck is **TSMC capacity** (fully fab-based process, cannot be outsourced to OSATs).
	- **EMIB is the credible challenger** — Intel has a decade of internal EMIB history; the structural advantages (panel format, no interposer, scalability) are real. The missing ingredient is external customer volume, and Google/MediaTek is the beachhead.
	- **Capacity is the binding constraint, not technology** — the recent interest in EMIB is not primarily because CoWoS is inadequate; it's because CoWoS capacity is limited and controlled by a single supplier. EMIB offers an alternative supply chain.
	- **OSATs are trying to move up** — companies like Amkor are investing to enter advanced packaging. Watch their earnings calls for update on progress. The margin pool is at the advanced packaging layer, not simple wire-bond assembly.
	- **Panel-level packaging (CoPoS, EMIB panels) is the next scalability unlock** — moving from 300mm circular wafers to 500×500mm panels eliminates the geometric waste problem and roughly 5–6× the substrate area per batch. TSMC targets 2028–2029. Intel is already on panels for EMIB substrates.
	- **Reticle-limit progression** drives the next several GPU generations: Blackwell (2×), Rubin (4×), and beyond will require ever-larger packaging substrates — a structural demand driver for advanced packaging capacity regardless of which technology wins.

