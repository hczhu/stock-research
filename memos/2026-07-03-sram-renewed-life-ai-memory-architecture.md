- tags:: [[SRAM]], [[HBM]], [[DRAM]], [[AI ASIC]], [[inference]], [[semiconductor]], [[advanced packaging]], [[TSMC]], [[Samsung]], [[Intel]], [[IBM]], [[Groq]], [[Cerebras]], [[$NVDA]]
-
- ## Source
	- Source document: `SRAM，再续生机`, Semiconductor Industry Observer, 2026-07-03.
	- Source file: `/Users/hc/Downloads/SRAM，再续生机.pdf`.
	- Core topic: SRAM scaling has become a visible bottleneck at advanced nodes, but IBM's Nanostack / 3D transistor work and AI accelerator architectures are reopening the question of whether SRAM can keep gaining density and strategic importance.
-
- ## Key Takeaways
	- SRAM is becoming a first-order AI chip architecture constraint. Compute units, HBM stacks, advanced packaging, and interconnect get most of the attention, but the deeper bottleneck is whether data can stay close enough to compute with low latency, high bandwidth, and predictable access.
	- The old assumption that SRAM automatically follows logic scaling is breaking. TSMC's 3nm-era SRAM data show bitcell scaling stagnating around the N5 level, even while logic density keeps improving.
	- IBM's 0.7nm-class Nanostack announcement matters less for the headline node label and more for its reported SRAM scaling path: IBM claims roughly **40% SRAM scaling** by changing transistor layout from lateral nFET / pFET placement toward vertical stacked structures.
	- The industry response is no longer one-dimensional geometry shrink. TSMC, Samsung, Intel, IBM, and CFET researchers are all pushing a mix of GAA nanosheets, DTCO, backside power, vertically stacked devices, and 3D CMOS to recover SRAM density, stability, and power benefits.
	- SRAM-heavy AI architectures such as Groq and Cerebras are a live proof point that on-chip memory can be a differentiated product axis. The risk is capacity: SRAM gives low latency and deterministic bandwidth, but it does not replace HBM capacity for large models.
-
- ## Data Points Extracted
	- The most important datapoints are about **SRAM bitcell stagnation**, **new transistor structure claims**, and **AI chip SRAM intensity**.
	-
	| Area | Company / Technology | Data point | Implication |
	|---|---:|---:|---|
	| SRAM scaling | TSMC N5 | High-density SRAM bitcell around **0.021 um²** | Baseline showing late FinFET SRAM density level |
	| SRAM scaling | TSMC N3 | High-density SRAM bitcell around **0.0199 um²** | Only modest shrink from N5, roughly **5%** |
	| SRAM scaling | TSMC N3E | High-density SRAM bitcell around **0.021 um²** | SRAM bitcell effectively back to N5 level |
	| SRAM scaling | TSMC N2 CMOS nanosheet | **38.1 Mb/mm²** SRAM density | TSMC improves macro-level SRAM density despite bitcell size stagnation |
	| SRAM scaling | TSMC N2 bitcell | **0.021 um²** high-density bitcell | Density gain comes from GAA / array / circuit / DTCO, not a much smaller bitcell |
	| SRAM scaling | TSMC N2 macro | **580Kb** SRAM macro, about **1.1x** / **10%** density uplift vs prior generation | SRAM scaling is incremental and design-assisted |
	| Transistor roadmap | IBM Nanostack | **0.7nm-class** nanosheet-based 3D transistor architecture | IBM positions Nanostack as a post-GAA scaling path |
	| Density claim | IBM Nanostack | Nearly **100B transistors** in fingernail-sized chip area | Claimed density roughly **2x** IBM's 2021 2nm chip |
	| Performance / efficiency | IBM Nanostack vs IBM 2nm | Up to **50%** performance improvement or **70%** energy-efficiency improvement | Source-reported research target, not commercial product proof |
	| SRAM scaling claim | IBM Nanostack | Roughly **40% SRAM scaling** / cell-height reduction | Key datapoint: vertical device placement may reopen SRAM density gains |
	| Prior IBM node | IBM 2nm, 2021 | Claimed **45%** performance improvement or **75%** lower energy vs 7nm | IBM has used research-node announcements to seed partner roadmaps |
	| CFET research | IEEE TED 2023 CFET SRAM DTCO | A5 CFET SRAM can deliver up to **55%** bitcell area scaling vs A14 nanosheet SRAM | CFET supports the same vertical-stack logic as IBM Nanostack |
	| CFET research | IEEE TED 2023 CFET SRAM DTCO | A5 CFET SRAM can deliver around **40%** bitcell area scaling vs A10 forksheet SRAM | Forksheet helps, but full vertical complementary stacking can help more |
	| Intel 18A | RibbonFET + PowerVia | **0.023 um²** high-current SRAM cell | Intel uses gate-all-around + backside power in SRAM-compatible silicon |
	| Intel 18A | RibbonFET + PowerVia | **0.021 um²** high-density SRAM cell | Similar absolute bitcell scale to TSMC N2/N3E but with PowerVia |
	| Cerebras WSE-3 | Wafer-scale AI chip | TSMC 5nm, **4T transistors**, **900K AI cores**, **125 PFLOPS** peak AI performance | Extreme on-chip compute + memory integration route |
	| Cerebras WSE-3 | On-chip memory | **44GB** on-chip SRAM | Largest proof point for SRAM-heavy AI systems |
	| Groq LPU | SRAM-centric inference | "Hundreds of MB" SRAM used as primary weight storage, not just cache | Architecture attempts to control data movement explicitly |
-
- ## Timeline
	| Year / date | Event | Read-through |
	|---|---|---|
	| 2021 | IBM announced 2nm nanosheet technology, claiming up to **45%** performance improvement or **75%** lower energy vs 7nm | IBM established itself as a research-node contributor to GAA scaling |
	| 2022 | IBM and Rapidus announced strategic cooperation to develop IBM's 2nm node technology for Rapidus' Japan fab | IBM's research roadmap depends on manufacturing partners for commercialization |
	| 2022 | Samsung announced initial 3nm GAA / MBCFET production | First major foundry push toward GAA, with SRAM design flexibility via nanosheet width tuning |
	| 2023 | CFET SRAM DTCO paper showed up to **55%** area scaling vs A14 nanosheet SRAM and around **40%** vs A10 forksheet SRAM | Industry research direction increasingly shifts from planar scaling to vertical device stacking |
	| 2024 | IBM and Rapidus expanded cooperation to 2nm-generation chiplet packaging | Advanced logic and advanced packaging are increasingly linked |
	| 2024 | SemiEngineering highlighted SRAM scaling difficulty as a power/performance challenge, while also noting SRAM's centrality for AI workloads | SRAM stagnation becomes a visible AI architecture problem |
	| 2025-12 | Source says Groq and NVIDIA announced a non-exclusive inference technology licensing agreement, with some Groq executives/team members joining NVIDIA | SRAM-centric inference IP can become valuable to mainstream accelerator vendors |
	| 2026 VLSI | IBM Nanostack SRAM bitcell paper: `Area and Performance of Staggered-Channel Nanostack SRAM Bitcells` | IBM claims the architecture can drive about **40%** SRAM scaling |
	| 2026-06-25 | IBM announced 0.7nm-class Nanostack transistor architecture | Source frames this as a possible new answer to SRAM scaling stagnation |
	| Potential next 5 years | Reuters-cited comment in source: IBM believes the Nanostack technology may enter a production path within about five years | Commercialization remains a medium-term question, not a near-term revenue event |
-
- ## Why SRAM Matters More in AI
	- AI chips are constrained by data movement, not only arithmetic throughput.
	- Transformer workloads repeatedly move weights, activations, intermediate results, attention data, and KV cache across memory tiers.
	- If more of this working set can stay near compute, the chip can reduce HBM accesses, cross-chip movement, scheduling complexity, and tail-latency variance.
	- The source identifies five direct consequences if SRAM scaling stalls:
		- **Die area pressure**: on-chip storage consumes more of large GPU / AI ASIC / CPU die area, reducing the area benefit of advanced nodes.
		- **Yield pressure**: larger dies and larger SRAM arrays raise defect sensitivity, redundancy needs, repair complexity, test cost, and yield-management burden.
		- **Power pressure**: moving data off-chip costs more energy than on-chip access.
		- **Latency pressure**: LLM inference, especially decode, long context, multi-turn dialogue, and real-time response, becomes more exposed to HBM and inter-chip access delays.
		- **Architecture pressure**: chip designers must choose between more HBM, larger on-chip SRAM, chiplet cache, 3D cache, near-memory compute, compute-in-memory, and CXL-based memory pools.
-
- ## Technology Routes
	- **TSMC route: DTCO around a flat bitcell**
		- TSMC's N2 SRAM story is not a large bitcell shrink.
		- The source's framing is that TSMC uses GAA nanosheets, array architecture, circuit techniques, and DTCO to raise macro-level SRAM density.
		- This implies future TSMC AI/HPC node differentiation is increasingly a system stack: logic + SRAM + power network + BEOL interconnect + advanced packaging.
	- **Samsung route: GAA / MBCFET device flexibility**
		- Samsung emphasizes tunable nanosheet channel width.
		- The source highlights SRAM-specific flexibility: PMOS, NMOS, pull-down, and pass-gate transistor widths can be adjusted to improve SRAM margin and the PPA / stability tradeoff.
		- Samsung SF2 continues the MBCFET / GAA direction with multiple nanosheet-width configurations and lower cell height.
	- **Intel route: RibbonFET + PowerVia**
		- Intel 18A combines GAA-style RibbonFET with backside power.
		- Backside power is important for SRAM because SRAM arrays are voltage-sensitive: read/write stability, minimum operating voltage, dynamic IR drop, and frequency all depend on power integrity.
		- The source positions PowerVia not just as logic-routing relief but also as an enabler for high-density SRAM-adjacent power delivery.
	- **IBM / CFET route: vertical transistor stacking**
		- IBM Nanostack and CFET-style work address a core SRAM layout bottleneck: lateral nFET-to-pFET spacing.
		- By stacking n-type and p-type devices vertically, part of the horizontal isolation area can be converted into vertical bonding / dielectric spacing.
		- This is why the reported **40%** SRAM scaling claim is important: it attacks a layout bottleneck that pure transistor miniaturization no longer solves well.
-
- ## Company And Ecosystem Read-Through
	- **Foundries**
		- TSMC, Samsung, and Intel are competing on SRAM-adjacent system metrics, not only headline logic density.
		- For AI/HPC customers, the key question becomes effective SRAM macro density, voltage stability, power delivery, and packaging integration.
		- SRAM stagnation may make advanced-node differentiation more complex and more customer-specific.
	- **IBM / Rapidus**
		- IBM's Nanostack work is strategically relevant as research IP, but commercialization depends on partners such as Rapidus or Samsung.
		- The source's "future five-year production path" framing means this is not a near-term foundry share event.
		- Rapidus' ability to translate IBM research into manufacturable 2nm-and-beyond flows remains a watch item.
	- **NVIDIA**
		- The source-reported Groq licensing agreement suggests NVIDIA is willing to absorb SRAM-centric inference IP if it improves low-latency inference economics.
		- NVIDIA's mainstream GPU roadmap still relies heavily on HBM, but SRAM-centric ideas can matter at the inference-system layer.
	- **Groq**
		- Groq demonstrates the value of deterministic, compiler-controlled data movement with SRAM as primary local storage.
		- The limitation is capacity: SRAM can improve latency and predictability, but does not remove the need for external memory in large-model regimes.
	- **Cerebras**
		- Cerebras is the most extreme SRAM-heavy architecture in the source: **44GB** on-chip SRAM and wafer-scale compute.
		- The architectural bet is that moving compute, memory, and interconnect onto one wafer changes the scaling constraints for certain AI workloads.
		- The risk is that cost, yield, software mapping, and model-memory requirements still need to justify the system-level premium.
	- **Memory suppliers**
		- SRAM's renewed importance does not directly displace HBM; it changes the optimal balance between on-chip SRAM and off-chip HBM.
		- If SRAM scaling improves, some AI architectures may reduce pressure on HBM bandwidth/latency for specific working sets, but HBM remains necessary for large-capacity model storage.
-
- ## Investment Lens
	- The central stock-research insight is that **AI memory is becoming a hierarchy problem**, not only an HBM supply problem.
	- HBM remains the capacity and high-bandwidth workhorse, but SRAM determines latency, scheduling simplicity, on-chip buffering, compiler control, and power efficiency.
	- A durable SRAM scaling path would increase design space for AI ASICs, edge inference chips, and latency-sensitive workloads.
	- The companies with leverage are not only DRAM/HBM makers. Leverage also sits with:
		- Foundries that can deliver SRAM macro density and power integrity at advanced nodes.
		- EDA/IP vendors that help customers manage SRAM stability, redundancy, compiler scheduling, and memory hierarchy optimization.
		- Advanced packaging players that enable chiplet cache, 3D cache, and SRAM-adjacent logic integration.
		- AI ASIC companies that can turn SRAM into system-level latency/cost advantages rather than a small cache feature.
-
- ## What This Changes Versus The Simple HBM Shortage Thesis
	- The simple thesis says AI chips need more HBM, therefore memory value accrues mostly to HBM suppliers.
	- This source adds a second layer: even with abundant HBM, AI chips need enough fast on-chip working memory to avoid wasting compute and power on data movement.
	- If SRAM cannot scale, systems compensate with more HBM, larger packages, chiplets, CXL, near-memory compute, and more complex scheduling.
	- If SRAM can scale through Nanostack / CFET / 3D CMOS, some AI workloads gain a new architecture lever: put more working state close to compute and reduce off-chip traffic.
	- The likely outcome is not "SRAM replaces HBM"; it is a richer memory hierarchy where HBM capacity and SRAM locality both become strategic bottlenecks.
-
- ## Open Questions
	- Can IBM Nanostack or CFET SRAM move from research claims into manufacturable, high-yield, foundry-scale processes?
	- Does TSMC N2's macro-level **1.1x** SRAM density uplift prove enough for near-term AI/HPC customers, or will SRAM area pressure keep worsening at A16 and later nodes?
	- Can Samsung's GAA channel-width tuning become a real SRAM stability / density advantage, or is it primarily a process-flexibility message?
	- Does Intel PowerVia create measurable SRAM voltage / frequency / density advantages for AI/HPC customers versus frontside-power competitors?
	- Which workloads benefit most from SRAM-heavy designs: low-latency inference, edge AI, long-context KV-cache optimization, sparse models, or deterministic serving?
	- Can SRAM-centric inference companies sustain differentiation once NVIDIA and other major accelerator vendors internalize similar compiler and memory-hierarchy ideas?
-
- ## Bottom Line
	- The memo's core conclusion is that SRAM is regaining strategic importance because AI chips are increasingly memory-movement constrained.
	- SRAM bitcell scaling has clearly slowed at leading nodes, but the industry is now attacking the problem through architecture: GAA nanosheets, backside power, DTCO, CFET, Nanostack, chiplet cache, and wafer-scale / SRAM-heavy accelerator designs.
	- For stock research, SRAM should be tracked as a separate AI infrastructure bottleneck alongside HBM and advanced packaging.
