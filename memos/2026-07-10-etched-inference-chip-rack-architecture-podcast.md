- tags:: [[Etched]], [[AI-accelerators]], [[inference]], [[ASIC]], [[GPU]], [[HBM]], [[SRAM]], [[KV-cache]], [[interconnect]], [[tokens-per-watt]], [[data-center]], [[power]], [[semiconductor]], [[$NVDA]], [[$TSM]], [[OpenAI]], [[agents]]

- ## Etched: Rack-Scale Inference Architecture, Production Strategy, and AI-Chip Outlook
	- **Source**: *Invest Like the Best* interview with Etched co-founders Gavin Uberti and Rob Lockett, hosted by Patrick O'Shaughnessy; transcript supplied by the user, July 2026.
	- **Disclosure in source**: O'Shaughnessy said he is a large, repeat Etched investor. The interview is therefore useful as primary-source founder commentary, but it is not independent diligence.
	- **Thesis**: Etched argues that inference will reward purpose-built rack-scale systems rather than chips evaluated in isolation. Its proposed advantage combines low-voltage compute for prefill, low-latency cluster-scale memory for decode, aggressive vertical integration, and supply-chain-aware production. If the claims hold in production, Etched could materially improve concurrency and token economics versus general-purpose GPUs. The main risks are that its benchmarks remain founder claims, its software/model scope is deliberately narrow, its system depends on scarce foundry and memory partners, and NVIDIA can respond with faster interconnect, better utilization, and a much broader software ecosystem.

- ## Company and Product Snapshot
	| Item | Transcript claim | Investment interpretation |
	|---|---|---|
	| Company founded | `2023` | Etched was designed after the transformer/ChatGPT workload became clear, unlike incumbent architectures that founders characterize as pre-ChatGPT retrofits. |
	| Founders | Gavin Uberti and Rob Lockett | Young founders paired with veteran semiconductor and rack-system engineers. |
	| Capital raised | `~$800M` | Enough to reach first silicon and build a vertically integrated rack program, but also evidence of extreme capital intensity. |
	| Reported customer demand | `>$1B` for the first product | Strong stated interest, but the transcript does not distinguish binding orders, deposits, reservations, or non-binding demand. |
	| First-silicon status | Working chip on first tape-out attempt | Material execution milestone if independently confirmed; lowers, but does not remove, production and yield risk. |
	| Product form factor | Complete inference rack | Includes chip, boards, power delivery, cooling, interconnect, rack integration, software, and manufacturing. |
	| First product name | `Sohu` | The interview discusses the broader rack solution and next generations more than a detailed SKU sheet. |
	| Manufacturing footprint | Factory/team in Taiwan; a few dozen people there | Indicates Etched is building direct manufacturing and test capability around its foundry ecosystem. |
	| Internal validation infrastructure | `2 MW` data center in its office/facility | Supports full-rack bring-up and rapid hardware/software iteration. |
	| Time from silicon return to rack inference | `40 days` | Compared by founders with `~10 months` for another unnamed AI-chip company; shows the benefit of pre-building software, boards, cooling, and production. |
	| Supply positioning | First generation on `4nm`, different node and HBM supply from NVIDIA Rubin | Explicit attempt to avoid a zero-sum fight for the exact same leading-edge capacity. |

- ## Core Technical Architecture
	- ### 1. Prefill and Decode Are Different Workloads
		- **Prefill** reads the prompt/context and constructs the model's `KV cache`; the primary optimization target is useful FLOPs and FLOP density.
		- **Decode** consumes model weights and the KV cache to generate subsequent tokens; the primary optimization target is memory movement, memory bandwidth, and chip-to-chip latency.
		- Etched expects **prefill/decode disaggregation**: one cluster performs prefill, then transfers KV caches to a decode cluster optimized for token generation.
		- Investment read-through: inference systems increasingly need heterogeneous scheduling and a memory hierarchy optimized around KV-cache transfer, supporting demand for high-bandwidth memory, networking, and memory-adjacent storage rather than compute alone.

	- ### 2. Low-Voltage Inference for Prefill
		- Founder claim: GPUs often achieve only `20%–50%` model FLOPs utilization (`MFU`) on real workloads.
		- Increasing utilization toggles more transistors, raises power draw, and can force thermal throttling; adding more nominal FLOPs does not necessarily increase useful performance.
		- Etched's proposed solution is **low-voltage inference**:
			- Voltage has a nonlinear relationship with power; lowering voltage can sharply reduce power.
			- The founders cite Bitcoin-mining ASICs as proof that much lower-voltage operation is physically possible, although a mining workload is much narrower than LLM inference.
			- Etched says its first generation runs at **less than half the voltage of any other AI chip**.
		- The company believes future inference accelerators will need to put more FLOPs in a fixed silicon area while operating at lower voltage to avoid thermal throttling.
		- **What must be proven**: useful throughput at production voltage across process variation, reliability, yield, model mix, clock rate, and rack power—not only nominal voltage or peak FLOPs.

	- ### 3. Cluster-Scale Memory for Decode
		- Etched argues that the wrong question is “How much memory bandwidth is on one chip?” The relevant metric is usable memory bandwidth across the entire scale-up cluster.
		- The system is designed to make the SRAM and HBM attached to multiple chips behave more like a shared pool through a custom interconnect stack.
		- Founder comparison:
			- Point-to-point latency on NVIDIA Blackwell can be around `4,000 ns`.
			- Etched claims its custom interconnect reduces this by **more than 5x**.
			- The physical floor is a few nanoseconds, implying substantial theoretical room below today's rack-scale latency.
		- Etched custom-built everything above Layer 2 Ethernet in its interconnect stack.
		- The goal is for token latency not to degrade materially as the model spans more chips, enabling scale-up domains of thousands or eventually tens of thousands of accelerators.
		- **Investment read-through**: AI-accelerator competition is shifting from standalone chip specifications to the whole rack's memory topology, scale-up fabric, collective operations, and latency. This supports the broader [[2026-07-07-interconnect-first-inference-latency-over-bandwidth-lpddr]] argument.

	- ### 4. Kernels-First Software, Not Full Compatibility
		- Etched deliberately chose not to support arbitrary CUDA, PyTorch graphs, ONNX graphs, or a broad general-purpose compiler.
		- Its assumption is that fewer than `100` economically important models will dominate token volume and share similar mathematical primitives.
		- Sophisticated customers receive direct hardware access and can optimize kernels close to the metal.
		- The company says high-frequency-trading engineers understood this approach early because they also distrust compiler overhead and write specialized kernels.
		- Coding models should reduce the labor penalty of this strategy:
			- Etched expects AI to generate and optimize a growing share of kernels.
			- It designs profiling and debugging tools partly for model use, not only human use.
			- Internal claim: Codex used the documentation to get `GPT-OSS` running from scratch overnight without human intervention.
		- **Trade-off**: specialization can improve performance and shorten development time, but creates model-porting, ecosystem, and customer-support risk if important architectures diverge from Etched's supported primitives.

- ## System-Level Performance Claims
	| Metric or concept | Etched claim | Caveat / diligence question |
	|---|---|---|
	| GPU real-workload MFU | Often `20%–50%` | Highly workload-, batch-, precision-, and software-dependent. |
	| First-generation voltage | Less than half that of other AI chips | Needs apples-to-apples power, frequency, reliability, and throughput data. |
	| Blackwell chip-to-chip latency | About `4,000 ns` point to point | Confirm topology, measurement boundary, payload size, and protocol overhead. |
	| Etched interconnect improvement | `>5x` lower latency | Founder claim; needs third-party benchmark at rack scale. |
	| Concurrency at fixed interactivity | Roughly `10x` more users | The central commercial claim; must be tested on named models, context lengths, output lengths, and service-level targets. |
	| Silicon-to-rack inference bring-up | `40 days` | Strong execution evidence, but not equivalent to volume qualification or customer deployment. |
	| Full-chip pre-silicon emulation | `>700` FPGAs, about a dozen models | Reduced first-silicon risk and let software development start before silicon arrived. |
	| Future production target | Product should ultimately be producible at gigawatts per month | Long-range ambition, not current capacity. |

- ## Why Etched Thinks Inference Becomes the Dominant Compute Market
	- Software gross margins are structurally changing: AI products incur meaningful marginal inference cost rather than near-zero marginal cost per user.
	- Better hardware expands demand in two dimensions:
		- **Concurrency**: more users or agents can be served at a guaranteed speed within a fixed power envelope.
		- **Wall-clock compression**: a long-running agentic or scientific task can finish sooner, increasing iteration speed and making previously impractical workflows useful.
	- The founders expect paid AI adoption to expand from a small fraction of the global population toward billions of concurrent users.
	- They view power as the binding resource: the relevant output metric becomes **tokens or agents per megawatt**, not just tokens per chip.
	- Long-horizon forecasts stated in the interview—not established facts:
		- Inference could become a majority of global GDP over time.
		- More knowledge-work agents than humans could exist by `2027`.
		- Individual AI data centers could eventually cost `>$1T`.
		- Nations could devote a majority of their energy to inference.
	- Investment interpretation: these predictions are intentionally extreme, but the nearer-term logic is sound—lower latency and higher tokens per watt can both unlock new use cases and protect gross margins for AI applications.

- ## Production and Company-Building as Competitive Advantages
	- Etched's operating maxim is **“production is the product.”** A superior accelerator without supply is economically irrelevant.
	- The company uses “prefetching” to parallelize all work that can occur before silicon returns:
		- Built the software stack against FPGA emulation.
		- Shipped chipless racks with networking, CPUs, and storage to customer data centers for software bring-up.
		- Built thermal dummy chips with expected hot spots to design and pressure-test cold plates.
		- Completed multiple circuit-board revisions and prepared the production line before first silicon.
	- It combines experienced “legends” with young engineers willing to challenge inherited constraints:
		- Recruited Brian—described as the founder of NVIDIA's HGX/DGX systems team—to lead rack expertise.
		- Recruited semiconductor veterans by repeatedly returning after milestones rather than expecting a first-call yes.
	- Vertical integration includes chip, boards, cold plates, interconnect, rack, test, and manufacturing, while fabrication and memory remain partner-dependent.
	- The founders favor immediate decisions with a reasonable error rate over waiting for perfect information, particularly when vendors or factories are blocked.

- ## Execution Timeline and Anecdotes
	| Period / stage | Event | Significance |
	|---|---|---|
	| `2023` | Company founded; founders concluded pre-ChatGPT accelerators were not optimized for modern inference | Architecture started with inference rather than adapting a training/general-purpose GPU. |
	| Late `2023` | Wrote a roughly `30-page` technical/fundraising memo | Needed to explain why a first product required far more capital than prior semiconductor Series A rounds. |
	| Early `2024` | Needed at least `~\$40M` for physical-design work while holding only `~\$15M` cash | Forced an unusually large financing before tape-out. |
	| Series A process | Raised about `~$103M` in soft commitments after most major investors initially passed | Allowed the company to build the full system rather than a small test chip. |
	| Vendor delay | Sent about a dozen engineers to Bangalore for months and ran 24-hour US/India handoffs | Avoided what founders estimated could have been a roughly one-year schedule slip. |
	| Pre-silicon | Built a `>700`-FPGA full-chip emulation cluster and pre-built rack, software, cooling, and production | Enabled rapid post-silicon bring-up. |
	| First silicon | Initial wafer-sort display showed all dies red; team found the issue and saw green dies within about a day | Illustrates bring-up volatility and the importance of experienced validation leadership. |
	| Bring-up | Found a clock-domain/backpressure issue requiring two clocks to align within `50 ps`, about `2B` times per second | Team developed a phase-drift/locking workaround in roughly `2–3 weeks`; shows both technical ingenuity and first-silicon fragility. |
	| Post-silicon | Reached inference in a rack in `40 days` | Claimed schedule advantage from parallel development. |

- ## Supply Chain Insights
	- ### TSMC's Moat Is Service, Not Only Process Technology
		- The founders call TSMC's customer service the best they have seen in any industry.
		- Anecdote: Etched proposed a process change to improve yield; TSMC reportedly ran an experiment at its own expense and moved the rest of the line after the result worked.
		- Etched gained early TSMC support after a founder discussed modern model tensors and low-voltage design in detail with a senior TSMC executive.
		- Read-through for [[$TSM]]: leading-edge foundry advantage includes collaborative process optimization, execution speed, financing flexibility, and customer trust—not just transistor density.

	- ### Supply Must Be Designed In, Not Procured Later
		- Foundry wafers, HBM, power, and large data-center blocks are all scarce; the more capacity required in one location, the more severe the shortage.
		- Etched intentionally selected a `4nm` and HBM supply chain different from NVIDIA Rubin's `3nm` path to make incremental deployments additive rather than purely substitutive.
		- The founders' rule: if the best-performing chip cannot be manufactured, “it is just a podcast.”
		- Read-through for memory: Etched does not argue that HBM disappears. Its cluster-memory architecture tries to use pooled HBM and SRAM more efficiently, but volume scaling still requires large memory supply.

	- ### Power and Space Are Now Compute Inputs
		- Founder statement: xAI Colossus can charge a premium for Blackwell access because it offers a large cluster in one place, not merely individual chips.
		- A `500 MW` contiguous data-center site is harder to source than the same power fragmented across smaller sites.
		- Etched frames its product around guaranteed interactivity and the number of concurrent users per power envelope, making **tokens per megawatt** more useful than peak chip FLOPs.

- ## Competitive Read-Through
	- ### NVIDIA
		- [[$NVDA]] remains the benchmark because it combines chips, systems, networking, software, supply, and customer trust.
		- Etched's bear case on NVIDIA is that a general-purpose GPU carries architectural buffer and compatibility overhead that a narrow inference system can remove.
		- Etched's own risk is the reverse: NVIDIA's generality, CUDA ecosystem, annual rack roadmap, and supply scale may outweigh a specialized chip's benchmark advantage.
		- The relevant comparison is not peak chip FLOPs; it is **throughput at a fixed user latency, power, model, context, reliability target, and delivered availability**.

	- ### Hyperscaler ASICs
		- Founder opinion: Google TPU, Meta MTIA, Microsoft Maia, and OpenAI Jalapeño are not existential to their parent companies, so those teams may optimize for avoiding the “NVIDIA tax” rather than taking maximum architectural risk.
		- They argue hyperscaler chips can be “similar enough” to GPUs and still create value through lower internal cost.
		- Etched claims its existential focus attracts more intense talent and supplier/customer support.
		- Counterpoint: hyperscalers own the workloads, data centers, software, and demand. Their lower need for merchant margins may let a merely adequate internal ASIC beat a technically superior startup on total economics.

	- ### Other Inference Startups
		- SRAM-heavy, 3D-DRAM, DDR-pooling, optical-interconnect, and advanced-packaging architectures each trade off bandwidth, capacity, thermals, latency, supply, and programmability.
		- Etched says it evaluated these paths and rejected the idea that one memory technology is a free lunch.
		- Its claimed distinction is jointly optimizing prefill compute and decode memory at rack scale rather than branding itself only as an SRAM, HBM, prefill, or decode chip.
		- Cross-reference: [[2026-07-06-gpt56-sol-hn-cerebras-inference-economics]], [[2026-07-03-sram-renewed-life-ai-memory-architecture]], and [[2026-06-07-ai-inference-hardware-semi-investment-memo]].

- ## Model-Architecture Opinions
	- Chips make arithmetic cheaper faster than they make DRAM movement cheaper; therefore future models should use more computation to economize on memory movement.
	- Possible directions include:
		- More and larger mixture-of-experts (`MoE`) experts.
		- Multiple model copies or parallel agent populations.
		- Very long context, potentially up to extremely large corpora in active memory.
		- Dynamic compute and memory allocation by token: important tokens receive more context or compute, while less important tokens receive less.
		- Dynamic routing across chips for MoE and other sparse workloads.
	- Hardware designed before dynamic routing can waste capacity through blocky, uniform execution.
	- This creates a feedback loop: lower-latency scale-up fabrics make more dynamic model architectures practical; those architectures then increase the value of low-latency fabrics.

- ## Public-Market Investment Implications
	| Company / segment | Read-through | Direction |
	|---|---|---|
	| [[$TSM]] | Etched's first-hand praise reinforces TSMC's service and co-optimization moat. More AI-ASIC startups increase leading-edge wafer demand even when they diversify away from NVIDIA's exact node. | Positive, subject to Taiwan concentration and capacity allocation. |
	| [[$NVDA]] | Specialized inference racks attack NVIDIA on tokens per watt and concurrency, but the interview also validates the importance of NVIDIA's full-stack rack model and availability. | Competitive risk at inference margin; strategic model validated. |
	| HBM / [[DRAM]] suppliers | Cluster-scale pooling may improve utilization, but Etched still requires HBM and explicitly designed around HBM availability. More accelerator architectures broaden memory demand. | Positive for volume; efficiency gains temper per-token memory intensity. |
	| Networking / interconnect | Chip-to-chip latency becomes a first-order inference metric as scale-up domains grow from tens to thousands of chips. | Positive for high-speed SerDes, switches, optical/copper interconnect, and scale-up fabrics. |
	| Hyperscaler ASIC partners | Internal ASICs do not need frontier merchant performance to save money; this supports [[$AVGO]], [[$MRVL]], and MediaTek-style design-service demand. | Positive, though Etched argues internal teams may be less aggressive technically. |
	| AI application software | Cheaper, faster inference can expand usage and improve gross margin, but continued model sophistication may absorb savings through more tokens and longer tasks. | Positive for demand; uncertain for near-term margins. |

- ## Variant Perception
	- **Consensus framing**: AI chips compete on peak FLOPs, on-chip HBM bandwidth, node, or benchmark speed.
	- **Etched framing**: the winning unit is a producible rack delivering the most concurrent users at a guaranteed latency within fixed power. Voltage, thermal behavior, interconnect latency, memory pooling, software specialization, manufacturing, and supply allocation compound into the result.
	- **Potentially important insight**: efficiency does not necessarily shrink total hardware demand. If lower token cost unlocks longer-running agents and more concurrent users, demand elasticity can consume the savings and increase total inference infrastructure.
	- **Hardest claim to underwrite**: an order-of-magnitude concurrency advantage can survive production variation, real model diversity, system overhead, and NVIDIA's roadmap while Etched simultaneously reaches volume availability.

- ## Risks and Open Questions
	- **Benchmark risk**: no independent model-level results, price, rack power, yield, or production-volume data were provided in the transcript.
	- **Demand-quality risk**: `>$1B` of “customer demand” may not equal contracted backlog or recognized revenue.
	- **Single-purpose risk**: deliberately narrow model support can become a liability if model architectures change faster than kernels and software can be ported.
	- **Incumbent response**: NVIDIA can improve voltage, utilization, interconnect, scale-up domains, inference software, and pricing while preserving ecosystem compatibility.
	- **Supply risk**: Etched still depends on TSMC, HBM suppliers, packaging, and power. Choosing a different supply lane reduces direct conflict but does not eliminate scarcity.
	- **Capital intensity**: the company raised `~$800M` before broad commercial scale; future generations, inventory, capacity reservations, and customer support may require substantially more capital.
	- **Reliability risk**: first-silicon bring-up anecdotes show the team can solve difficult problems, but also reveal how small analog/timing issues can threaten correctness.
	- **Key-person and culture risk**: 24/7 shifts, relocation, and extreme intensity can accelerate execution but may create burnout and retention problems.
	- **Customer concentration**: a small number of frontier labs and hyperscalers buy most AI accelerators and have leverage, internal silicon programs, and the ability to multi-source.
	- **Economies-of-scale assumption**: Etched expects cluster-scale memory to make marginal tokens cheaper as systems grow; congestion, synchronization, failures, and communication overhead could weaken that curve.

- ## What to Monitor
	- Named customers, binding order value, deposits, delivery dates, and revenue recognition.
	- Independent throughput-versus-interactivity curves on named frontier and open models.
	- Rack power, tokens per watt, tokens per dollar, and concurrency versus Blackwell/Rubin at equal service-level objectives.
	- Production yield, packaged-good-die output, HBM qualification, field reliability, and serviceability.
	- Whether the `>5x` interconnect-latency claim holds across a full rack and larger multi-rack domains.
	- Time required to support new model architectures and whether AI-generated kernels materially reduce porting cost.
	- TSMC node allocation, HBM supplier mix, advanced-packaging path, and ability to scale without competing directly with NVIDIA capacity.
	- Second-generation simplification: part count, assembly cycle time, repairability, and actual monthly rack output.
	- NVIDIA's response in low-voltage operation, NVLink latency, scale-up size, inference scheduling, and price/performance.
