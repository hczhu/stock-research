- tags:: [[DRAM]], [[HBM]], [[SSD]], [[NAND]], [[packaging]], [[semiconductor]], [[AI infrastructure]], [[$NVDA]], [[$TSM]], [[$000660.KS]], [[$005930.KS]], [[$MU]]
  file-created-at:: 2026-06-07

- **Source**: user-provided PDF, "DRAM Deep Dive - Interactive Tutorial" (Module 10: HBM & 3D DRAM), Chrome/Skia PDF created 2026-06-07
- **Source coverage note**: The second requested file, "DRAM Deep Dive - Interactive Tutorial-future-directions.pdf", was not present at `/Users/hc/Downloads/` when accessed from the shell, so this memo extracts from the available DRAM Deep Dive tutorial text. SSD-specific conclusions below are limited to read-through from HBM/DRAM architecture and existing NAND/flash investment context, not direct extraction from the missing second PDF.

- ## Bottom line
	- The tutorial explains why HBM exists: conventional PCB-attached memory hits a **pin-count and signal-integrity wall**, while HBM solves it by moving DRAM dies close to the accelerator and using a very wide, short, low-energy interface.
	- The investment read-through is that AI memory value is increasingly captured by **stacking, TSVs, interposers, hybrid bonding, and logic-base-die sophistication**, not just commodity DRAM bit output.
	- For SSD/NAND work, the key contrast is that SSDs solve cheap capacity, while HBM solves local bandwidth. AI systems likely need both: HBM for active accelerator memory and SSD/NAND for larger context, model, and storage tiers.

- ## Core technical argument
	- **Why HBM exists**:
		- GDDR6 can reach high bandwidth, but it needs many chips, many pins, and very fast PCB traces.
		- The tutorial's example: GDDR6 at up to **512 GB/s** uses **8 chips**, each with a **32-bit bus**, for **256 data pins** total at **16 Gbps**.
		- Doubling bandwidth through more pins or faster PCB signaling quickly runs into routing space, equalization, and impedance-control limits.
	- **HBM's answer**:
		- Put DRAM dies above or beside the logic die.
		- Use a **1024-bit internal bus** through TSVs instead of long PCB traces.
		- At **1024-bit width** and **6.4 Gbps/pin**, HBM3 reaches **819 GB/s per stack**.
	- **Why it matters for AI**:
		- AI accelerators are not just compute chips; they are memory-package systems.
		- The bottleneck moves from "can the GPU calculate?" to "can the package feed the GPU enough data at acceptable power and cost?"

- ## Key data points
	- **HBM generation progression**
	
	  | Generation | Year | Bandwidth / stack | Capacity | Dies |
	  |---|---:|---:|---:|---:|
	  | HBM1 | 2013 standard / 2015 product | 128 GB/s | 1 GB | 4 |
	  | HBM2 | 2016 | 256 GB/s | 4-8 GB | 4-8 |
	  | HBM2E | 2020 | 460 GB/s | 8-16 GB | 8 |
	  | HBM3 | 2022 | 819 GB/s | 24 GB | 12 |
	  | HBM3E | 2024 | 1.2 TB/s | 36-64 GB | 16 |
	  | HBM4 planned | 2025+ | 2+ TB/s | 64-128 GB | 16+ |
	- **TSV and packaging dimensions**
	
	  | Item | Data point | Investment relevance |
	  |---|---:|---|
	  | TSV diameter | 5-10 microns | Requires specialized process capability and yield control |
	  | TSV depth | 30-50 microns | HBM die thinning and via formation are non-trivial manufacturing steps |
	  | TSV pitch | 40-60 microns | Enables dense vertical wiring not possible on PCB |
	  | TSV count per HBM3 stack | ~40,000 | Raises process complexity and yield sensitivity |
	  | Standard DRAM die thickness | ~700 microns | Baseline before thinning |
	  | HBM die thickness | 30-50 microns | Mechanical handling and yield become key differentiators |
	  | TSV capacitance vs PCB trace | ~100x lower | Lower power per bit transferred; major reason HBM is viable |
	- **Interposer and bonding data**
	
	  | Layer / interface | Data point | Read-through |
	  |---|---:|---|
	  | Silicon interposer line/space | 2-5 microns | Much denser routing than organic PCB |
	  | PCB line/space | 50-100 microns | Limits high-bandwidth external memory routing |
	  | Interposer routing layers | 4-8 metal layers | Advanced packaging becomes a core value layer |
	  | Microbump pitch | ~55 microns | Proven through HBM3E, but limits bandwidth density |
	  | Hybrid bonding pitch | ~1-10 microns | 10-50x denser than microbumps; key for HBM4+ |
	  | 1024-bit bus bump area at 55 micron pitch | ~1 mm2 | Shows why microbump pitch becomes a scaling constraint |
	- **Cost contrast**
	
	  | Product / package | Approx. cost | Point |
	  |---|---:|---|
	  | H100 GPU module with 5 HBM3 stacks | ~$30,000 at launch | HBM packaging pushes AI modules into premium system economics |
	  | GDDR6 GPU cards with similar memory bandwidth | ~$500-$1,500 | Illustrates how expensive advanced HBM packaging is vs conventional memory cards |

- ## HBM4 and hybrid bonding
	- HBM4 is presented as the next major packaging step:
		- **2048-bit bus** per stack, doubling the prior HBM bus width
		- **1-10 micron hybrid bonding pitch**, replacing ~55 micron microbumps
		- **~9.6 Gbps/pin**
		- **2+ TB/s** bandwidth per stack
		- **64-128 GB** capacity target
		- **16-die + logic-base assembly**
	- The important investment point is that HBM4 is not a simple DRAM bit-density upgrade. It depends on advanced bonding, stack yield, thermal management, and base-die logic capability.
	- SK Hynix's option to fabricate the HBM4 logic base die on a **TSMC 3nm-class node** is strategically important because it moves HBM closer to a logic-memory co-design product, not a standalone memory commodity.

- ## Processing-in-memory read-through
	- The tutorial frames PIM as a response to expensive data movement: process data where it lives rather than constantly moving it across the memory bus.
	- **Examples cited**
	
	  | Approach | Detail | Investment read-through |
	  |---|---|---|
	  | SK Hynix AiM | SIMD multiply-accumulate units in the HBM logic base die; ~1 TOPS MAC throughput inside the stack | Supports SK Hynix as a memory architecture leader, not just bit supplier |
	  | Samsung HBM-PIM | Programmable FP16 compute in the sense-amp region of each bank; accessed via new JEDEC-defined commands | Supports Samsung's push toward memory-plus-compute differentiation |
	  | UPMEM | DIMM-based design with a 24-core RISC processor per DRAM chip | PIM can also matter outside HBM for database/genomics-style workloads |
	- **Caveat**: PIM requires a new programming model and works best when kernels are simple, parallel, and memory-bound. This limits near-term generality but keeps optionality alive for inference, search, scans, and other memory-heavy workloads.

- ## DRAM investment implications
	- **HBM is structurally more defensible than commodity DRAM**:
		- Value comes from packaging, TSV yield, thermal management, and system integration.
		- This is why SK Hynix, Samsung, and Micron can have different economics in HBM despite all being DRAM suppliers.
	- **Advanced packaging is a bottleneck and profit-pool gatekeeper**:
		- Silicon interposers, microbumps, hybrid bonding, and high-density routing are not side details; they are the product.
		- This reinforces the importance of TSMC-style packaging capacity and the broader CoWoS / interposer / hybrid-bonding supply chain.
	- **HBM4 increases logic-foundry relevance to memory**:
		- If the HBM base die moves to advanced logic nodes, memory vendors become more dependent on foundry partners.
		- This may shift some value capture from pure memory manufacturing toward co-design and packaging integration.
	- **The HBM moat is time-bound**:
		- Hybrid bonding can expand bandwidth density, but it also raises yield difficulty.
		- Leadership can change by generation if a supplier misses bonding, base-die, thermals, or customer qualification.

- ## SSD / NAND implications
	- The extracted tutorial is HBM/3D-DRAM focused rather than SSD focused, but it clarifies why SSDs do not substitute for HBM in active accelerator memory:
		- HBM solves local bandwidth and power-per-bit through short, dense links.
		- SSD/NAND solves cheap capacity and persistence, but not immediate accelerator bandwidth.
	- The investment implication is complementary, not either/or:
		- **HBM** captures the premium tier close to GPU/ASIC compute.
		- **SSD/NAND** captures larger, cheaper tiers for datasets, checkpoints, retrieval corpora, KV-cache offload, and future flash-based memory tiers.
	- This supports a memory-stack model for AI infrastructure:
	
	  | Tier | Best fit | Semi beneficiaries |
	  |---|---|---|
	  | HBM | Active model weights, decode bandwidth, accelerator-local working set | SK Hynix, Samsung, Micron, packaging/foundry partners |
	  | Server DRAM / LPDDR | CPU-side memory, orchestration, system memory | Big 3 memory suppliers |
	  | SSD / NAND | Large persistent capacity, RAG corpora, checkpoint storage, KV-cache offload | Samsung, Micron, SK Hynix/Solidigm, SSD controller ecosystem |
	  | Future HBF / near-flash memory | Potential bridge between HBM and SSD | NAND suppliers plus advanced packaging integrators |

- ## What to monitor
	- HBM4 customer qualifications and which vendor wins the first high-volume AI accelerator sockets.
	- Evidence that hybrid bonding reaches volume yield at acceptable cost.
	- TSMC involvement in HBM base dies or memory-adjacent logic integration.
	- CoWoS/interposer bottlenecks and whether packaging capacity remains the limiting factor for AI accelerators.
	- PIM/PNM announcements that move from demos into production inference or database workloads.
	- SSD/NAND demand tied to AI retrieval, KV-cache offload, and context-memory architectures, since those are the places where NAND can move up from storage into active inference infrastructure.
