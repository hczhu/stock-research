- tags:: [[$NVDA]], [[AI infrastructure]], [[AI-factory]], [[GPU]], [[LPU]], [[CPU]], [[DPU]], [[NVLink]], [[Spectrum-X]], [[ConnectX]], [[CPO]], [[networking]], [[inference]], [[data-center]], [[rack-scale]]

- **Source**: User-provided table, "Make table for each name in Nvidia hardware ecosys...," local PDF `/Users/hc/Downloads/Make table for each name in Nvidia hardware ecosys....pdf`, accessed July 13, 2026. Roadmap names were cross-checked against Nvidia's official [Vera Rubin platform overview](https://developer.nvidia.com/blog/inside-the-nvidia-rubin-platform-six-new-chips-one-ai-supercomputer/), [Vera Rubin POD / Kyber roadmap](https://developer.nvidia.com/blog/nvidia-vera-rubin-pod-seven-chips-five-rack-scale-systems-one-ai-supercomputer/), [Groq 3 LPX technical overview](https://developer.nvidia.com/blog/inside-nvidia-groq-3-lpx-the-low-latency-inference-accelerator-for-the-nvidia-vera-rubin-platform), and GTC 2026 keynote. Future specifications remain subject to change.
- **Thesis**: Nvidia's hardware strategy is no longer centered on selling standalone GPUs. It is building every critical layer of the AI factory: throughput compute, low-latency inference, host processing, infrastructure offload, scale-up fabric, scale-out Ethernet, network endpoints, and liquid-cooled rack systems. This expands Nvidia's content per deployed accelerator, turns the rack or pod into the relevant product unit, and makes performance depend on full-system co-design rather than GPU specifications alone.

- ## Nvidia Hardware Ecosystem Overview

	| Component Family | Names in PDF | What It Is | Primary Function | Roadmap / Verification Note |
	|---|---|---|---|---|
	| GPUs | Blackwell, Blackwell Ultra; Rubin, Rubin Ultra; Feynman | Primary parallel AI compute engines using HBM3e, HBM4, and future custom HBM generations. | Training, high-throughput inference, prefill, attention, and complex model execution. | PDF groups Blackwell with 2024, Rubin with 2026, and Feynman with 2028. Broad sequence is confirmed; exact launch timing and specifications can change. |
	| LPUs | LP30, LP35, LP40 | SRAM-heavy, deterministic low-latency processing units derived from Groq technology. | Accelerate latency-sensitive token generation, especially FFN/MoE portions of decode for interactive AI. | LP30 is the Groq 3 chip used in LPX; Nvidia says LP35 is the Rubin Ultra follow-on and LP40 belongs to the Feynman generation. |
	| CPUs | Grace, Vera, Rosa | Custom, energy-efficient data-center host processors. | System orchestration, data preprocessing, tool calling, sandboxing, and single-thread-sensitive work that does not fit GPUs/LPUs efficiently. | PDF maps Grace to 2024, Vera to 2026, and Rosa to 2028. Vera is officially positioned for agentic processing and data movement; Rosa is future roadmap. |
	| DPUs | BlueField-3, BlueField-4, BlueField-5 | Programmable infrastructure processors running Nvidia DOCA. | Offload networking, storage, security, isolation, routing, and infrastructure management from host CPUs. | BlueField-3 is current; BlueField-4 is part of Vera Rubin and CMX/STX; BlueField-5 is a future roadmap component. |
	| GPU switches | NVLink 5; NVLink 6 / 7; NVLink 8 CPO | Proprietary scale-up interconnect and switch silicon. | Connect GPUs within and eventually across racks into one coherent high-bandwidth NVLink domain. | NVLink 5 maps to Blackwell and NVLink 6 to Rubin. Later-generation NVLink 7/8 and CPO details are roadmap items and should be treated as preliminary. |
	| Ethernet switches | PDF: Spectrum5 51T; Spectrum6 102T CPO; Spectrum7 204T CPO | Spectrum-X scale-out Ethernet switch silicon and systems. | Connect racks across pods and data centers with AI-optimized congestion control, routing, telemetry, and optics. | **Naming discrepancy**: Nvidia's official Rubin table calls the 51.2 Tb/s Grace Blackwell generation **Spectrum-4**, not Spectrum5. Spectrum-6 at 102.4 Tb/s is confirmed; Spectrum-7 is future roadmap. |
	| Network adapters | CX8 800G; CX9 1600G; CX10 | ConnectX SuperNIC endpoint adapters. | Connect compute nodes to Spectrum-X or InfiniBand fabrics and enforce endpoint-level traffic control, isolation, RDMA, and security. | Official table shows ConnectX-8 at 800 Gb/s per GPU and ConnectX-9 at 1.6 Tb/s per GPU; ConnectX-10 is future roadmap. |
	| Systems / racks | Oberon: NVL72, PDF label ETL256; Kyber: NVL144, NVL1152 | Liquid-cooled AI-factory chassis and rack architectures integrating compute, memory, networking, power, and cooling. | Let customers deploy validated AI factories rather than assemble individual chips and subsystems. | Oberon supports NVL72 and optical expansion; LPX uses an MGX ETL rack with 256 LP30 chips. Kyber starts at NVL144 and scales eight racks into an NVL1152 domain. |

- ## How the Layers Fit Together
	- **CPU orchestration layer**: Grace, Vera, and Rosa execute serial control work, data processing, agent tools, and host services.
	- **Throughput compute layer**: Blackwell, Rubin, and Feynman GPUs handle massively parallel training and inference.
	- **Latency compute layer**: LP30/LP35/LP40 LPUs specialize in predictable, interactive token generation where low tail latency matters more than maximum aggregate FLOPS.
	- **Infrastructure layer**: BlueField DPUs isolate and offload networking, storage, security, and management tasks so CPU/GPU cycles remain focused on AI work.
	- **Scale-up layer**: NVLink joins accelerators into a shared high-bandwidth domain inside a rack and, with optical links, across racks.
	- **Endpoint layer**: ConnectX SuperNICs control how each compute node injects traffic into the broader network.
	- **Scale-out layer**: Spectrum-X switches connect NVLink domains across pods and data centers.
	- **System layer**: Oberon, ETL, and Kyber package the silicon, memory, optics, cooling, power delivery, and serviceability into deployable rack-scale products.

- ## Product Family Details

- ### GPUs: The Flexible Throughput Engine
	- The PDF lists a three-generation progression:
		- **Blackwell / Blackwell Ultra**: current generation, paired with HBM3e and NVLink 5.
		- **Rubin / Rubin Ultra**: 2026-era platform, moving to HBM4-class memory and NVLink 6, with larger optical scale-up domains.
		- **Feynman**: 2028 roadmap generation, expected to use further customized HBM and next-generation networking.
	- GPUs remain the general-purpose workhorse because they can handle training, prefill, attention, throughput-oriented decode, simulation, and non-LLM accelerated workloads.
	- Strategic role: the GPU anchors demand for every attached Nvidia layer, including CPU, NVLink, ConnectX, BlueField, Spectrum-X, and rack systems.

- ### LPUs: A New Low-Latency Inference Tier
	- Nvidia's LPU roadmap introduces specialization inside the AI factory rather than replacing GPUs:
		- **LP30**: Groq 3 chip in the current LPX system.
		- **LP35**: Rubin Ultra follow-on incorporating Nvidia NVFP4, according to the GTC 2026 keynote.
		- **LP40**: Feynman-generation LPU.
	- The LPX rack contains **256 LP30 chips**, **128 GB total SRAM**, **40 PB/s on-chip SRAM bandwidth**, **640 TB/s scale-up bandwidth**, and **315 PFLOPS FP8**, according to Nvidia.
	- Nvidia splits inference by workload characteristics:
		- Rubin GPUs handle prefill, decode attention, long context, and flexible high-throughput work.
		- LPUs handle latency-sensitive FFN/MoE expert execution and deterministic token generation.
	- Investment implication: Nvidia is protecting inference share by embracing heterogeneous compute before a specialized low-latency competitor can establish an independent platform.

- ### CPUs: Agentic Orchestration and Data Movement
	- **Grace** established Nvidia's Arm-based data-center CPU strategy.
	- **Vera** is designed around high single-thread performance, data movement, energy efficiency, agent tools, and large-scale sandboxing.
	- **Rosa** is the Feynman-era successor and remains a roadmap product.
	- CPUs matter more in agentic systems because AI workloads increasingly call tools, execute code, manipulate data, and coordinate long-running workflows rather than only run dense matrix operations.
	- Strategic role: Nvidia CPUs reduce dependence on x86 host vendors and allow tighter optimization of the full AI rack.

- ### DPUs: The AI Factory Control Plane
	- **BlueField-3** provides current networking, security, and storage offload.
	- **BlueField-4** extends infrastructure offload into agentic-AI storage through STX/CMX context-memory systems.
	- **BlueField-5** is the future roadmap step paired with Feynman/Rosa-era infrastructure.
	- DPUs make the AI factory programmable and isolated without spending expensive CPU or GPU resources on infrastructure work.
	- Strategic role: BlueField plus DOCA creates a software-defined infrastructure moat around networking, storage, security, and multi-tenant operations.

- ### NVLink: Scale-Up as a Proprietary Moat
	- NVLink is the fabric that lets many GPUs behave like one rack-scale accelerator.
	- Confirmed generational progression:

	| Architecture | NVLink Generation | Bandwidth per GPU | Aggregate NVL72 Bandwidth |
	|---|---|---|---|
	| Hopper | NVLink 4 | **900 GB/s** | Not applicable in the same rack-scale form |
	| Blackwell | NVLink 5 | **1.8 TB/s** | **130 TB/s** |
	| Rubin | NVLink 6 | **3.6 TB/s** | **260 TB/s** |

	- Nvidia is adding optical scale-up alongside copper so NVLink domains can expand beyond a single rack.
	- Strategic role: NVLink makes the system-level performance advantage harder to replicate with a competing accelerator connected by commodity networking.

- ### Spectrum-X and ConnectX: Scale-Out as a System
	- **Spectrum-X switches** control traffic across racks using adaptive routing, congestion control, telemetry, and increasingly co-packaged optics.
	- **ConnectX SuperNICs** implement traffic shaping, isolation, encryption, and RDMA at each server endpoint.
	- Official Vera Rubin comparison:

	| Platform | Switch | Switch Bandwidth | Adapter | Adapter Bandwidth per GPU |
	|---|---|---|---|---|
	| Grace Blackwell | Spectrum-4 | **51.2 Tb/s** | ConnectX-8 | **800 Gb/s** |
	| Vera Rubin | Spectrum-6 | **102.4 Tb/s** | ConnectX-9 | **1.6 Tb/s** |

	- The switch and endpoint are co-designed: Spectrum controls the fabric while ConnectX controls traffic injection before congestion forms.
	- CPO becomes increasingly important as electrical links struggle with the bandwidth, reach, power, and reliability requirements of million-GPU-scale networks.

- ### Racks: Oberon, ETL, and Kyber
	- **Oberon NVL72**: current third-generation MGX rack design for Vera Rubin, integrating 72 GPUs with NVLink 6.
	- **ETL / LPX**: specialized low-latency inference rack with 256 LP30 LPUs; the PDF's “ETL256” label is best understood as this 256-chip LPX configuration.
	- **Kyber NVL144**: next-generation rack doubling density to 144 GPUs per rack.
	- **Kyber NVL1152**: eight Kyber racks connected into one all-to-all 1,152-GPU NVLink domain for Feynman-era scale-up.
	- Nvidia also describes Rubin Ultra options at NVL72, NVL144, and NVL576 before the Feynman/Kyber NVL1152 generation.
	- Strategic role: the rack architecture standardizes power, liquid cooling, cabling, serviceability, and system validation, increasing Nvidia's influence over data-center design.

- ## Investment Implications
	- **Nvidia's addressable content expands faster than GPU units**: Each accelerator deployment can pull Nvidia CPU, DPU, NVLink switch, SuperNIC, Ethernet switch, rack, optics, and software content.
	- **The unit of competition is now the AI factory**: Competitors must match rack-level token economics, networking, memory movement, reliability, and deployment speed, not merely GPU FLOPS.
	- **Heterogeneous inference protects the franchise**: Adding LPUs lets Nvidia cover premium low-latency decode without abandoning the flexible GPU platform.
	- **Networking becomes a larger share of value**: NVLink, ConnectX, Spectrum-X, and optics scale with cluster size and model communication intensity.
	- **CPO is both opportunity and execution risk**: Optical integration can reduce power and improve reach, but introduces packaging, yield, thermal, laser, connector, and field-service complexity.
	- **Vertical integration strengthens lock-in**: Customers receive validated performance and faster deployment, but become more dependent on Nvidia's proprietary interfaces, software, and roadmap cadence.
	- **Racks increase revenue visibility but raise working-capital complexity**: Selling integrated systems captures more wallet share while exposing Nvidia and partners to cooling, power, mechanical, component, and deployment bottlenecks.
	- **Roadmap breadth raises execution risk**: Nvidia must deliver synchronized generations across GPUs, LPUs, CPUs, DPUs, switches, NICs, optics, and racks; one delayed layer can constrain the entire platform.
	- **Open and custom alternatives remain the strategic counterforce**: Hyperscalers and merchant silicon vendors can resist Nvidia's full-stack economics through custom accelerators, open Ethernet, UALink, and disaggregated rack designs.

- ## What to Monitor
	- LP30/LPX shipment timing and customer adoption alongside Vera Rubin NVL72.
	- LP35 tape-out and whether NVFP4 materially improves low-latency decode economics.
	- Nvidia's disclosed mapping for NVLink 7/8, Spectrum-7, ConnectX-10, and BlueField-5.
	- Spectrum-6 CPO production yields, power savings, reliability, and field serviceability.
	- Customer adoption of Nvidia CPUs versus x86 hosts in Rubin and Feynman systems.
	- BlueField-4 CMX/STX adoption and whether context-memory storage becomes a standard inference tier.
	- Mix shift from component sales toward NVL72, LPX, NVL144, NVL576, and eventually NVL1152 systems.
	- Competitive progress from AMD rack systems, hyperscaler ASICs, UALink, Broadcom/Marvell custom silicon, and open Ethernet fabrics.
	- Whether customers accept increasing Nvidia content per rack or push back against full-stack pricing and lock-in.
