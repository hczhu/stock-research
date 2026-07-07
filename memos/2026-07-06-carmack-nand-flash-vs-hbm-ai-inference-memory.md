- tags:: [[NAND]], [[HBM]], [[DRAM]], [[AI]], [[inference]], [[AI-accelerators]], [[memory]], [[$MU]], [[SanDisk]], [[SK-Hynix]], [[Samsung]], [[semiconductors]]

- **Source**: John Carmack (@ID_AA_Carmack) X post, Jul 6 2026 (438.4K views). Technical argument that NAND flash can displace HBM for AI-accelerator memory in inference. Companion to [[DRAM-memory-ssd-index-thesis]] and [[2026-07-03-dram-hbm-supercycle-news-roundup-jun-jul-2026]] (see the SanDisk HBF / High-Bandwidth Flash note there).

- **Thesis frame**: A credible first-principles case from a respected systems engineer that the **most expensive layer of the AI memory stack (HBM) is architecturally over-provisioned for inference**, and that **NAND flash — ~100× cheaper per GB — can serve model-weight reads** if the access pattern is treated as deterministic/sequential. Directly relevant to the HBF (High-Bandwidth Flash) angle from SanDisk/SK Hynix and to the long-run demand mix between HBM, DRAM, and NAND. Bull for NAND volume/value-add; a potential long-run *cap* on the HBM-only bull case; largely bullish for the memory complex overall (larger models become deployable cheaply).

- ## The Core Argument
	- **Memory cost and capacity are the binding constraints** for AI accelerators.
	- Unlike game rendering, **model inference has a deterministic memory access pattern**. Model weights do not require true "random access memory" — you can tolerate **cold-start latencies of multiple milliseconds** as long as **continuous reads are delivered at the necessary bandwidth**.
	- **NAND flash is >100× cheaper per GB than HBM.** So there is opportunity even after giving a flash controller a **1024-bit interface with HBM-class bandwidth**.

- ## Two Possible Interfaces
	- **(1) Specialized pin protocol / stream-to-scratch**: a purpose-built pin protocol supporting **pipelined transfer of full 16KB+ pages** from flash directly into **program-managed accelerator scratchpad memory**. This could **improve per-pin performance over HBM**. Downside: **code must be completely rewritten** before it works at all.
	- **(2) RAM-emulation interface** (Carmack's likely preference for convenience): make flash **look like true random-access memory with very fragile performance characteristics** — anything but sequential reads **falls off a 1000×+ performance cliff**.
		- Advantages: **automatically reuses existing cache hierarchies**; provides a **natural path to update flash with new model weights**; and it **starts working immediately (just extremely slow)**, letting you **incrementally optimize** toward full performance — versus stream-to-scratch, which is all-or-nothing.

- ## Engineering Details / Caveats
	- **Scratchpad SRAM may be too small** to hold a full layer's weights. Mitigation: revive the **old optical-drive trick of duplicating data in multiple physical locations on a sequential read to avoid seeking** — wasteful, but "**there would be capacity to burn**" given flash's cost advantage.
	- **Access-trace linearization**: possibly use something like **CUDA graph capture** to record a memory-access trace and **automatically remap everything into a linear sequence**. But Carmack judges **manual programmer/agent "elbow grease" to manage transfers and a scratch-RAM ring buffer as lower risk**.
	- **Split vs. uniform memory**: a hybrid of **some flash channels + some HBM channels** will likely be **suboptimal vs. uniform memory**, but **much cheaper**, and would **allow much larger models to be run**.

- ## Inference vs. Training
	- **Inference: strong case.** Reads are linearizable; flash's read economics dominate.
	- **Training: must stretch.** You can still linearize all weight accesses (reads *and* writes), **but flash would wear out quickly from the writes** — even if perfectly page-aligned.
		- Training alternative floated: **replace low-latency HBM with massively parallel, cheaper DRAM at higher latency** — potentially still a worthwhile cost saving (bullish for commodity DRAM as an AI-training memory tier, not just HBM).

- ## Investment Read-Through
	- **Bullish for NAND value-add / HBF**: validates the [[2026-07-03-dram-hbm-supercycle-news-roundup-jun-jul-2026]] SanDisk **High-Bandwidth Flash** concept — a smart controller + wide interface turning cheap NAND into an AI-memory tier. Winners would be **NAND makers with controller/packaging IP** (SanDisk, [[$MU]], [[SK-Hynix]] after Solidigm, [[Samsung]], Kioxia) and whoever builds the **flash-controller/pin-protocol layer**.
	- **Nuance for the HBM bull case**: if inference weight-serving can migrate to flash + scratchpad, part of the HBM TAM narrative (HBM as the *only* answer to the memory wall) has an architectural ceiling. Near term HBM demand is undisturbed (training + latency-critical inference), but this is a **long-run substitution risk to the "HBM captures all AI memory value" thesis**.
	- **Bullish for the memory complex overall**: cheaper memory → **larger models economically deployable** → more total memory content per accelerator across the HBM/DRAM/NAND stack. The tiering (SRAM scratchpad → HBM → DRAM → NAND) deepens rather than shrinks memory's share of accelerator BOM.
	- **Training tier**: the "**cheaper high-latency DRAM instead of HBM**" idea is a modest tailwind for **commodity DDR5/LPDDR** demand in AI systems, reinforcing the broad-DRAM (not just HBM) leg of [[DRAM-memory-ssd-index-thesis]].

- ## Bottom Line
	- Carmack is describing, at an architectural level, **why the AI memory hierarchy should get deeper and cheaper, not just taller and more expensive**. For the memory names this is **net bullish on volume/content** but a **caution flag on the assumption that HBM alone captures the AI-memory value pool**. Watch for: **flash-controller / HBF product announcements**, accelerator vendors adding **program-managed scratchpad + sequential-flash tiers**, and any silicon that exposes a **wide (1024-bit) flash interface** with page-pipelined transfer.
