tags:: [[DRAM]], [[HBM]], [[memory]], [[commoditization]], [[JEDEC]], [[switching-costs]], [[$MU]], [[$000660.KS]], [[$005930.KS]], [[$NVDA]], [[$AMD]], [[$TSM]], [[$MRVL]], [[advanced-packaging]], [[CoWoS]], [[custom-silicon]], [[3D-DRAM]], [[HBF]], [[semiconductor]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-20
file-updated-at:: 2026-11-22

- ## Why DRAM is more of a commodity than CPUs and GPUs, and how custom HBM4 erodes the rule
	- **Source**: a discussion between the owner and a friend about memory vendors' long-term moats, fact-checked by an AI assistant (user-provided text and two table screenshots, November 2026). The figures and dated events come from that AI answer. Where the repo has the same point, the matching memo is linked. Points the repo doesn't confirm are marked as unverified.
	- **Thesis**: standard interfaces and no software lock-in make DRAM more of a commodity than CPUs or GPUs. Customers buy it on price, yield and availability. Top-end AI memory is splitting off from that. **Standard HBM4** (2026) still follows the JEDEC interface, but its base die is now a foundry logic chip, and it is permanently bonded into the package. **Custom HBM4E / NVHBM** (2027+) moves the customer's memory controller and a proprietary die-to-die link onto that base die. Swapping DDR5 vendors is a procurement exercise. Swapping custom-HBM vendors means requalifying the chip's architecture and packaging, which locks suppliers in or out for an 18–24-month platform cycle.
	- **The structural reason, per the answer**: abstraction. Computing stacks deliberately hide memory behind a flat, byte-addressable contract so software stays portable. A part whose whole job is to obey a rigid external standard invisibly gets bought on price.

- ## The debate and the fact-check
	- | Claim | Who | Fact-check verdict | Key points |
	  |---|---|---|---|
	  | All three vendors profit together for 2–3 years | Friend | **Mostly true, but gains are uneven** | Samsung, SK hynix and Micron have about 88% of DRAM revenue in an AI super-cycle approaching \$200B. Much of 2026–27 HBM supply is locked into long-term contracts. Profits diverge: SK hynix has nearly 60% of HBM, Samsung leads total DRAM (38% in Q3 2026), and Micron has gained share more slowly |
	  | Long-term winners need a new memory architecture beyond HBM5, and all three could fail | Friend | **Right on the physics, overstated on a radical replacement** | Planar DRAM scaling is hitting capacitor-aspect-ratio and leakage limits. Vendors are moving to 3D DRAM and stacking rather than to new materials (next section) |
	  | CPU and GPU vendors face less disruption because memory's hardware and software interfaces are simpler and easier to swap | **Owner** | **Right on switching costs, incomplete in two ways** | CPUs and GPUs still face paradigm-level disruption. Top-end HBM is no longer a simple drop-in part |
	- **The two gaps in the owner's claim**:
		- **Software moats slow drop-in replacement, not architectural shifts.** Examples: Intel lost server share to AMD and Arm, CPUs lost data-center wallet share to GPUs, and GPUs now compete with custom AI ASICs such as TPUs.
		- **Top-end HBM is no longer drop-in.** Starting with HBM4 for Nvidia Rubin and AMD MI400, the stack has a logic base die made on a foundry node and co-designed with the package. Changing HBM4 suppliers is far harder than changing DDR modules.
	- **Risks shared by all three vendors**: the cycle, and regulation. A US DRAM price-fixing class action was allowed to proceed in November 2026 ([[2026-11-14-dram-antitrust-class-action-motion-to-dismiss-denied]]).
	- **Cross-checks against the repo**:
		- **Samsung's 38% Q3 2026 DRAM share** matches Counterpoint in [[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]].
		- **The "about 88%" combined share** compares with 91.5% (Q3 2025) in the court record.

- ## What comes after planar DRAM (the friend's claim 2)
	- | Path | Who and when (per the answer) | Role |
	  |---|---|---|
	  | Monolithic **3D DRAM** | Micron skipped 4F² to target 3D DRAM around 2030–31. Samsung targets stacked 3D DRAM by 2030 | Main-memory successor to planar scaling |
	  | Compute stacked vertically on memory | Samsung **zHBM**, Micron **vHBM** | Puts logic and DRAM in one stack |
	  | **High Bandwidth Flash (HBF)** | SK hynix and SanDisk; the answer says it was standardized in August 2026 | Capacity tier for AI inference |
	  | MRAM, ReRAM, PCM | Not competitive as main memory | Niche edge caches or complementary tiles, because none matches DRAM's mix of density, bandwidth and cost per bit |
	- **The answer's conclusion**: even if no exotic material succeeds, vendors will still be told apart by packaging, thermal engineering and yield, not by one make-or-break invention.
	- **HBF dating is unverified.** The repo has the SanDisk–SK hynix HBF alliance starting in February 2026, with samples in 2H26 ([[2026-07-04-dram-crisis-memory-tiering-semi-industry-observation]]). The August 2026 standardization date is not confirmed there.

- ## Table 1: Why DRAM behaves more like a commodity than CPUs and GPUs
	- | Dimension | DRAM (DDR, LPDDR, standard HBM) | CPUs and GPUs |
	  |---|---|---|
	  | Interface and standards | Strictly governed by JEDEC specs (pinouts, voltages, timings). Drop-in interchangeable across vendors | Proprietary microarchitectures, interconnects (e.g., NVLink) and specialized accelerators (e.g., Tensor Cores) |
	  | Software lock-in | **None.** Sits behind the OS virtual-memory layer and the hardware memory controller. Software never targets a memory vendor | **Massive.** Locked in through ISAs (x86, Arm), compilers, drivers and frameworks (CUDA, cuDNN) |
	  | Value metrics | Narrow and transparent: cost per GB, bandwidth, latency and power | Many dimensions: single-thread vs. parallel throughput, precision support, ecosystem tooling and developer velocity |
	  | Cost structure | Vertically integrated fabs (IDMs) with huge fixed costs that must run near full utilization, which amplifies boom-and-bust price swings | Mostly fabless (Nvidia, AMD, Apple). They outsource wafer capex to TSMC and price on scarce proprietary IP |

- ## Table 2: How switching friction rises across memory tiers
	- | Technical dimension | Commodity DDR5 (RDIMM) | Standard HBM4 (2026 wave) | Custom HBM4E / NVHBM (2027+) |
	  |---|---|---|---|
	  | Interface contract | Rigid JEDEC PCB bus (2×32-bit per DIMM) | JEDEC JESD270-4 (2,048-bit), often overclocked above spec | Customer-proprietary die-to-die PHY, plus the memory controller moved onto the base die |
	  | Base die process | None (pure DRAM dies on a PCB) | Foundry logic (TSMC N12, Samsung SF4X) or advanced CMOS | Leading-edge foundry logic (TSMC N5/N3P, Samsung 2nm/4nm) |
	  | IP ownership | 100% memory vendor | Memory vendor, plus heavy electrical tuning by the customer | Split: customer RTL and PHY, vendor's vertical TSV interface |
	  | Physical integration | Socketed, field-replaceable | Permanently bonded on CoWoS-L, with a vendor-specific warpage and thermal profile | Deeply co-designed TIM, thermal paths, interposer routing and PDK |
	  | Qualification cycle | Weeks to about 1–2 months | **6–12+ months** (interposer signal and power integrity, thermal, known-good-die yield) | **12–24 months** (co-tapeout from the early architecture phase) |

- ## Why HBM4 breaks the commodity abstraction: four bottlenecks
	- ### 1. The 2,048-bit bus forced the base die onto logic foundry nodes
		- **Stack anatomy**: 8, 12 or 16 thinned DRAM core dies are stacked with through-silicon vias (TSVs) on a base (buffer) die, which talks to the GPU or ASIC through a silicon interposer.
		- **Why DRAM processes no longer work**: through HBM3E, memory makers built the base die on their own DRAM peripheral process. That process is tuned for low-leakage capacitor cells, not fast logic. It has weak transistor drive, poor logic density and only about **3–5 coarse metal layers**, vs. **12–15+ fine-pitch layers** at a logic foundry.
		- **The HBM4 jump**:
			- | Item | HBM3E | HBM4 (JESD270-4) |
			  |---|---|---|
			  | Bus width per stack | 1,024 bits (16 channels) | **2,048 bits** (32 channels, 64 pseudo-channels) |
			  | Footprint | about 11 × 12.8 mm | About the same |
			  | Pin speed and bandwidth | — | 8–12+ Gbps per pin, more than 2.0–3.3 TB/s per stack |
			  | SK hynix stack density | — | More than 20,000 TSVs and 16,148 base microbumps |
			- Routing that density on a DRAM process causes severe RC delay, IR voltage drop and runaway switching power.
		- **Where each vendor builds the base die**:
			- | Vendor | HBM4 base die | Custom HBM4E base die |
			  |---|---|---|
			  | SK hynix | TSMC 12nm-class (N12) | TSMC N5 / N3P |
			  | Samsung | In-house **4nm FinFET (SF4X)**, which gives more pin-speed headroom | Samsung 2nm/4nm or TSMC 3nm, e.g., reported custom stacks for Meta and Nvidia's NVHBM |
			  | Micron | In-house advanced CMOS | **TSMC**, confirmed September 2026 |
			- Micron's switch to TSMC matches [[2026-09-04-hbm-base-die-becomes-a-foundry-business]].
		- **What follows**: even before any customer logic arrives, the base die's process node sets the achievable clock speed, leakage and voltage margins.
	- ### 2. "Beachfront" crowding moves accelerator logic onto the memory stack
		- **Crowding on the compute die**: on a reticle-limited AI chip (about 858 mm²), HBM PHYs and memory controllers take roughly **25–30% of die area**. They also dominate the die edge (the "shoreline" or "beachfront") where wires exit to the interposer. Doubling the interface to 2,048 bits makes shoreline wiring the main limit on how many stacks one chip can attach.
		- **Moving the controller**: in custom HBM (Nvidia NVHBM, Meta's custom HBM4E, Marvell's custom HBM platform), the chip designer moves several functions off the GPU or ASIC and onto the HBM base die:
			- The memory controller
			- ECC and RAS telemetry
			- Adaptive power management
			- Channel scheduling
		- **A custom die-to-die link replaces JEDEC**: the compute die connects to the base die through a compact, high-speed custom or UCIe-derived PHY instead of 2,048 wide, slow traces.
			- | Marvell's modeled gain from a custom base die | Up to |
			  |---|---|
			  | Compute-die area reclaimed | **25%** |
			  | Extra HBM stacks the freed shoreline allows | **33%** |
			  | Interface power saved under bursty inference traffic | **70%** |
		- **Why vendors stop being interchangeable**: once the customer's RTL lives in the base die, there are two incompatible interfaces.
			- **Horizontal (GPU to base die)**: owned by the customer and hardened to one foundry's PDK, e.g., TSMC N3P vs. Samsung SF2.
			- **Vertical (base die to DRAM core stack)**: proprietary to each memory vendor. SK hynix, Samsung and Micron each have their own TSV pin maps, bank repair and redundancy schemes, test modes and timing calibration.
			- A common GPU-facing NVHBM implementation can reduce integration work. A replacement stack still has to be qualified for the platform; whether changing vendors also requires a new tapeout depends on the implementation.
	- ### 3. 2.5D packaging, thermals and mechanical co-design
		- **Permanent bonding**: DDR5 plugs into a standard DIMM slot. HBM4 is permanently fused onto a large multi-reticle 2.5D interposer, such as TSMC CoWoS-L, where packaging alone costs more than \$1,000 per module. The memory vendor's manufacturing process therefore directly affects the accelerator's yield and reliability.
		- **Stacking inside a 775 µm height cap**: JEDEC caps HBM4 stack height at 775 µm, up from 720 µm for HBM3E. Fitting 12–16 DRAM layers plus a base die requires:
			- Wafers thinned to about **30 µm**
			- Microbumps shrunk from about 15–25 µm (HBM3E) to about **10 µm**
			- TSMC already pushing suppliers toward **5 µm** microbumps, ahead of full copper-to-copper hybrid bonding
		- **Two different bonding methods**:
			- | Vendor | Bonding method |
			  |---|---|
			  | SK hynix | **Advanced MR-MUF** (mass reflow molded underfill): liquid epoxy molding compound injected between dies |
			  | Samsung, Micron | **TC-NCF** (thermo-compression non-conductive film): solid adhesive films between dies, under heat and pressure |
			- The two methods differ in thermal expansion, warpage across reflow cycles and vertical heat conduction. Switching vendors changes the mechanical stress on the CoWoS-L interposer and its local silicon interconnect bridges, which risks solder-joint fatigue or cracked microbumps. See also [[2026-08-21-sk-hynix-hbm-history-mr-muf-moat]].
		- **Heat becomes a first-order problem**:
			- A 3–4nm logic controller and a high-speed die-to-die PHY (more than **2.0 W/mm²** at more than 28 Gbps per lane) sit directly under 12–16 DRAM layers.
			- In 2.5D packages, the HBM stack's internal vertical thermal resistance is about **57%** of its total thermal resistance, vs. about **13%** for the adjacent ASIC.
			- DRAM leakage rises exponentially with temperature. That forces more frequent refresh, which directly takes away usable bandwidth.
			- The thermal interface material, lid flatness, dummy silicon heat paths and firmware throttling curves all have to be simulated and tuned for each supplier's stack.
		- **Yield coupling**: eight HBM4 stacks sit permanently beside two reticle-sized compute dies in one package. One latent defect in a single stack scraps tens of thousands of dollars of silicon, and rework is effectively impossible.
		- **Thin signal and power margins**: running 2,048 channels above JEDEC's 8 Gbps baseline exposes small differences between suppliers in power delivery impedance, switching noise and eye closure.
			- **The answer's example**: in October 2026, Nvidia cut Vera Rubin's HBM4 speed target from **11.7 to 9.6 Gbps per pin**, which shows how hard it is to keep several suppliers aligned at extreme speeds without losing yield.
			- **Unverified**: the repo does not have this revision. The September 2026 base-die memo cites Rubin pushing past 11 Gbps per pin.
	- ### 4. What it means for market structure
		- **The answer's conclusion**: HBM4 turns memory procurement into something close to custom-ASIC or foundry co-development. DDR5 stays a pure commodity traded on spot prices. Custom HBM creates deep two-way lock-in:
			- Hyperscalers and GPU vendors can't casually change suppliers mid-generation.
			- Memory vendors that lack tight TSMC co-packaging integration or competitive logic yields get shut out of flagship platforms for a whole 18–24-month architecture cycle.
		- **The split**: conventional DDR stays a classic commodity. Top-end HBM4 becomes a semi-custom, foundry-integrated product, where packaging yield (SK hynix's MR-MUF, Samsung's hybrid bonding) and co-design with TSMC and the customer create real moats and pricing power.

- ## How this relates to the owner's claim (memo's reading)
	- The owner's claim holds for **DDR, LPDDR and standard HBM bits**, which make up most DRAM by volume.
	- At the **custom-HBM tier**, the comparison flips. A custom HBM4E supplier becomes as hard to replace mid-generation as a foundry, though the lock-in lasts only one platform cycle. Unlike a CUDA-style software moat, it does not carry over automatically to the next generation.
	- This is the same split as in [[2026-07-04-dram-commodity-vs-decommoditization-synthesis]]: commodity-like at the standard die and spec layer, de-commoditizing at the package, customer and qualification layer.

- ## Counter-argument: custom base dies commoditize memory makers further (added 2026-11-22)
	- **Source**: [Gemini Advanced, “Fact-Checking HBM4 Pricing Arguments,” November 22, 2026](https://share.gemini.google/afn2XlcNJyHA), including the original X exchange with Dawson Lee (@LiDaosen). Gemini’s answer is an interpretation; the table distinguishes company disclosures from reporting and inference.
	- **Lee’s argument**: When the accelerator designer controls the custom controller and a foundry makes the base die, the memory maker no longer controls the incremental logic IP. Lee argues this weakens the memory vendor’s pricing power and leaves it mainly supplying the DRAM stack.
	- **Counterargument in the exchange**: A GPU or custom accelerator cannot treat an HBM stack like a socketed DDR5 DIMM. The memory vendor still co-designs and qualifies the stack with the accelerator designer and its manufacturing partners.
	- | Layer or issue | What the evidence supports |
	  |---|---|
	  | **Standard HBM4 is not NVHBM** | HBM4 doubles external I/O width from **1,024 to 2,048** versus HBM3E. Standard HBM4 can use an advanced logic base die without adopting NVIDIA’s custom controller: SK hynix uses TSMC logic starting at HBM4, while Samsung ships standard HBM4 on its own **4nm** logic process. Outsourcing fabrication does not transfer ownership of the design. [SK hynix on I/O](https://news.skhynix.com/en/computex-2026-review/) · [SK hynix–TSMC collaboration](https://news.skhynix.com/en/tsmc-technology-symposium-2026/) · [Samsung HBM4](https://news.samsung.com/global/samsung-ships-industry-first-commercial-hbm4-with-ultimate-performance-for-ai-computing) |
	  | **NVHBM shifts control of the interface** | NVIDIA says its proprietary controller and PHY move into the custom base die. It claims **up to 30% more bandwidth per stack** and **15% lower HBM power** versus standard HBM4E. Those are NVIDIA’s design comparisons, not stack-level price or margin figures. NVIDIA also says a common implementation is intended to reduce integration and qualification work across suppliers. [NVIDIA launch](https://blogs.nvidia.com/blog/nvlink-fusion-nvhbm-custom-high-bandwidth-memory/) · [Technical disclosure](https://developer.nvidia.com/blog?p=120848) |
	  | **TSMC 3nm across vendors is reported, not a blanket HBM4E rule** | Seoul Economic Daily reported that NVIDIA asked **Samsung, SK hynix, and Micron** to use TSMC **3nm** for NVHBM base dies and **1c DRAM** for core dies. Samsung’s reported participation in this program does not imply it outsourced its standard HBM line, and the report does not establish identical stacks or all-three volume qualification. [Seoul Economic Daily, October 18](https://en.sedaily.com/business/2026/10/18/samsung-to-use-tsmc-for-base-die-in-nvidias-custom-hbm) |
	  | **DRAM stack engineering still differs by supplier** | The common interface reduces some work on the accelerator side, but bonding, warpage, heat dissipation, and stack yields still matter. SK hynix’s **12-layer, 48GB** HBM4E samples reached **16 Gb/s per pin** using its Advanced MR-MUF stacking process. Micron said it had worked with NVIDIA on NVHBM for **over a year** by its September 2026 call. Those are concrete examples of engineering and co-development beyond the controller. [SK hynix HBM4E samples](https://news.skhynix.com/en/sk-hynix-ships-samples-of-12-layer-next-gen-hbm4e-2/) · [Micron earnings-call transcript](https://www.roic.ai/quote/MU/transcripts/2026-year/4-quarter) |
	- **Gemini’s pricing distinction**: NVIDIA can reduce the cost of qualifying a second source without making an unqualified stack drop-in. Gemini argues that once multiple stacks are qualified, NVIDIA has more room to negotiate price and allocation; before then, usable DRAM dies, stacking yield, and available capacity still give vendors leverage. The chat and cited disclosures do not quantify how logic or stack profits are split.
	- **Demand and cyclicality are separate.** Micron said it raised calendar 2027 HBM prices significantly to narrow the profitability gap with conventional DRAM. SK hynix said long-term agreements covered **over 50% of its total 2027–28 production capacity**, with prices responsive to the market within agreed ranges. These disclosures speak to current pricing and visibility, not a permanent floor for HBM margins or a permanent increase in total DRAM demand. [Micron earnings-call transcript](https://www.roic.ai/quote/MU/transcripts/2026-year/4-quarter) · [SK hynix Q3 2026 results](https://news.skhynix.com/en/q3-2026-business-results/)
	- **Not verified:** The chat’s package-wide thermal-resistance share and broad 2027 HBM4 contract-price claim are not used. Micron’s pricing comment is company-specific and does not isolate the NVHBM contract.

- ## Pricing power through the cycle: a higher floor, a more contested ceiling
	- **Source**: Latest round of the Gemini discussion, supplied by the user on November 22, 2026. It considers a future in which HBM becomes the majority of a memory vendor’s revenue, not a claim about the current revenue mix.
	- **The chat’s argument**: HBM could raise trough margins through a narrower supplier base, longer commitments, and higher switching costs. But it trades a broad customer base for a **bilateral oligopoly**: a few qualified sellers negotiating with a few very large buyers. Once buyers have spare qualified capacity to choose from, their bargaining power over price and allocation rises.
	- | Pricing mechanism | What favors memory vendors | What limits their leverage |
	  |---|---|---|
	  | **Supplier and buyer concentration** | Leading-edge HBM is concentrated among SK hynix, Samsung, and Micron. The chat contrasts this with conventional DRAM: TrendForce estimates CXMT’s global DRAM revenue share rose from **7.6% in Q1 to 9.5% in Q2 2026**. That is total DRAM share, not HBM share. [TrendForce](https://www.trendforce.com/news/2026/10/14/news-musk-says-china-is-rapidly-advancing-in-lpddr5lpddr6-highlights-its-mass-production-capabilities/) | A handful of accelerator and custom-silicon programs can move a large share of demand. The chat’s **five to six buyers** is illustrative, not a verified count of direct purchasers or any vendor’s customer concentration. |
	  | **Contracts and inventory** | Building stacks to contracted orders can improve volume visibility and reduce the need to clear finished inventory on spot markets. Volume commitments and prepayments can strengthen that protection where the contract includes them. | Annual price resets can lag a fast-moving DDR5 market, and pricing risk can cluster at renewal. HBM is not uniformly fixed-price or prepaid; conventional DRAM is not uniformly sold on spot or built to stock. Contract protection depends on the terms. |
	  | **Wafer opportunity cost** | Micron cited a **3:1 trade ratio**: roughly **three DDR5 bits foregone for each HBM bit** made with comparable wafer capacity. That ratio rises with later HBM generations. If agentic AI sustains CPU-side DDR5 or LPDDR demand and margins, profitable server DRAM gives vendors an alternative use for future wafer starts. [Micron FQ1 2026 remarks](https://investors.micron.com/static-files/088991c5-a249-4f66-a0a6-258d9b66f3f9) | Wafer starts are a planning lever, not an immediate switch: front-end process choices, stacking capacity, qualification, and existing commitments limit how quickly mix can change. Micron’s 2027 repricing is evidence of a reset, not proof of what caused it across the market. |
	  | **Platform qualification** | Co-design, thermal validation, and package integration make replacing an unqualified stack costly mid-generation. A supplier with usable output can retain leverage even if it does not own the controller. | A common NVHBM implementation can lower the cost of qualifying alternatives, particularly for the next design cycle. Buyers can redirect meaningful volumes only if alternatives have passed qualification **and** can deliver. Reports of three vendor engagements do not establish equal-volume interchangeability on Rubin. [NVIDIA NVHBM](https://blogs.nvidia.com/blog/nvlink-fusion-nvhbm-custom-high-bandwidth-memory/) |
	  | **HBM’s share of accelerator cost** | High HBM content makes a missing stack costly when it prevents shipment of an otherwise complete accelerator. | The same cost creates an incentive to use shorter stacks where capacity is not binding, offload colder KV cache to host memory (including LPDDR/SOCAMM where supported), or explore CXL pooling. Savings depend on workload and latency. The chat’s **30–40%** is not a universal manufacturing-cost share: Epoch AI’s specific **B200 module** model puts HBM at **about 46%** of variable cost; module, server, and rack denominators differ. [Epoch AI cost model](https://epoch.ai/data-insights/b200-cost-breakdown) · [NVIDIA KV-cache offloading](https://docs.nvidia.com/dynamo/latest/kubernetes/kv-cache-offloading/overview) |
	- **Capacity-constrained regime**: The chat sees the supplier advantage as strongest when accelerator shipments are constrained by HBM availability and vendors can allocate scarce wafer starts elsewhere. Commitments and delayed repricing mean that bargaining power does not necessarily become margin immediately.
	- **Balanced or oversupplied regime**: If enough qualified capacity comes online or AI capex slows, large buyers can steer allocations and push back on price. The chat’s **late 2027–2028** is a scenario, not a confirmed crossover: Micron expected **2027–28 to be tighter than 2026** and said it did not know when supply and demand would balance. [Micron FQ4 2026 call](https://www.roic.ai/quote/MU/transcripts/2026-year/4-quarter)
	- **Margin implication, per the chat**: A higher trough than legacy commodity DRAM is plausible if contract floors, committed volumes, and unit costs support it. It is not a demonstrated margin floor or the end of cyclicality. The long-run ceiling remains contested because the largest buyers control system design, sourcing, and how much HBM they put into each product.

- ## A friend's industry view: Nvidia standardizes, the rest of the market stays vendor-designed (added 2026-11-22)
	- **Source**: a group chat with a friend who follows Taiwan's hardware supply chain, plus a question from another participant (user-provided screenshot, Chinese, translated). These are personal views and secondhand industry comments, not company disclosures.
	- **On Lee's argument: right direction, but oversimplified**:
		- "The general direction is right. The custom base die for HBM4 is increasingly **designed under Nvidia's lead and manufactured by TSMC**."
		- **Samsung vs. the others**: Samsung could have developed its own version. SK hynix and Micron are "relatively lacking in this capability."
		- **Why Nvidia wants a common design**: Nvidia wants Samsung to adopt the Nvidia/TSMC scheme too, "so the three suppliers' products are **easier to swap for one another**, to handle changes in supply and demand."
		- **The friend's objection**: "saying DRAM makers will therefore become completely commoditized is an oversimplification. HBM **manufacturing technology, yield and capacity remain important barriers**. And Nvidia is not HBM's only customer. Google and other large AI chip makers have their own requirements."
	- **Only Nvidia can impose a common base die**:
		- "Only Nvidia is strong enough to control the base-die versions of all three memory companies. AMD's scheme can't do that."
		- "**Nvidia's share of the memory companies' business will decline over the long term**. HBM is hard to commoditize."
	- **How non-Nvidia customers get HBM**:
		- **The question** (another participant): are the specs of Nvidia's base die public? Does AMD design its own base die, or leave it to Micron and the other memory makers?
		- **The friend's answer**: "Companies other than Nvidia basically use HBM versions whose **base die is designed by the memory company itself**. Customers like AMD and Google state their requirements, and the memory company develops to match."
	- **What Nvidia's integration means for the rest of the market**:
		- The friend worries that Nvidia's integration rises every generation. Second-tier Taiwanese server makers rely on more customization, so that leaves them less room.
		- The CTO of one such company told the friend that "**only Nvidia can integrate so many different component companies to this degree**. Others can't." Outside Nvidia, the market is "a hundred flowers blooming" (many competing approaches), with "very large room for development."
	- **How this fits the rest of the memo** (memo's reading):
		- **Corroborates Nvidia's intent**: the friend's account matches NVIDIA's stated aim of cutting qualification work across suppliers, and Seoul Economic Daily's October 18 report that Nvidia asked all three vendors to use TSMC 3nm for NVHBM base dies.
		- **Interchangeability is part of the point**: making suppliers swappable is a goal of the Nvidia/TSMC base die, not a side effect. That supports Lee's direction, but **only for Nvidia's volume**.
		- **The friend's main addition is market structure**:
			- If Nvidia's share of HBM demand falls over time as Google, AMD and other ASIC programs grow, more volume moves onto **vendor-designed base dies**. There the memory maker keeps the logic design and the customer relationship.
			- That limits commoditization to the Nvidia slice. It fits SK hynix's comment on the "growing importance of custom HBM" for individual customers ([[SKHY-2026-Q3]]).
		- **One nuance on "lacking capability"**: SK hynix and Micron do **design** their own standard HBM4 base dies; SK hynix has them made at TSMC. The gap is better read as a lack of in-house leading-edge logic fabs, not of design ability. Samsung has both.
		- **Some non-Nvidia programs are custom too**, such as Meta's reported custom HBM4E with Samsung and Marvell's custom HBM platform. "Basically" vendor-designed holds for now, but not universally.

- ## Related in the repo
	- **Base die economics and vendor foundry choices**: [[2026-09-04-hbm-base-die-becomes-a-foundry-business]].
	- **The commodity debate**: [[2026-06-28-joe-lion-apple-memory-commodity-argument]], [[2026-06-05-memory-de-commoditization-permanent-plateau-geninnov]], and TSMC's view that 3D DRAM is not a commodity ([[2026-11-08-tsmc-3d-dram-report-embedded-oxide-memory-not-commodity]]).
	- **HBM thermals**: [[2026-06-08-hbm-thermal-management-competition-china-memo]].
	- **Index-level view**: [[DRAM-memory-ssd-index-thesis]].
