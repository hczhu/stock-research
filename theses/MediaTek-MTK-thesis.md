tags:: [[$2454.TW]], [[ASIC]], [[semiconductor]], [[AI infrastructure]]

- **Company**: MediaTek (2454.TW)
- **Date**: 2026-06-04
- **Market cap at writing**: TBD
  
  ---
- ## References

	| [Earnings call notes](https://github.com/hczhu/stock-research/tree/main/earnings/MediaTek) | |
	|---|---|
	| | |

  ---
- ## Main Narrative
	- > What will the business look like in 5–10 years, qualitatively and quantitatively? Is the market large enough to support 10x its current revenue? Can the business at least 4x revenue in 10 years?
	- ### Data Center & ASIC Breakthroughs
		- MediaTek's most critical technical leap involves **moving data within AI clusters**.
		- **224G SerDes Silicon**: MediaTek has demonstrated silicon-proven **224G SerDes** (Serializer/Deserializer) — the "nervous system" of modern AI data centers, enabling ultra-high-speed data transfer between GPUs and TPUs. Features the industry's smallest "beachfront density" (**350 microns**), pushing **670 Gbps per millimeter** of chip edge.
		- **2nm UCIe-Advanced IP**: At MWC 2026, MediaTek unveiled the world's first **silicon-validated die-to-die connectivity** on TSMC's **2nm and 3nm** processes. Lets different chips (e.g., a CPU and an AI accelerator) be "glued" together with bandwidth up to **10 Terabits per second**.
		- ### Hyperscaler ASIC Diversification — Google (and likely Anthropic next)
			- **MediaTek is Google's second TPU design partner** — the diversification away from sole-source **Broadcom**. On the **June 2026 Broadcom earnings call**, CEO **Hock Tan** conceded Broadcom would not stay Google's only partner:
				- > "while we like to win every design in that program, we also accept the fact that given the growth of … development and consumption of AI compute even by our partner, Google, … we fully expect that there will be some diversity of sources for them."
			- Google is already partnering with MediaTek on TPU design and is also pulling more design capability in-house. **Structural driver**: as a hyperscaler's AI-compute consumption scales, single-vendor design risk (capacity, pricing, roadmap leverage) becomes unacceptable, so it adds a second ASIC design partner — and MediaTek is the one filling Google's second-source slot ([[2026-05-01-mediatek-google-tpu-codesign-semi-cot-model]], [[2026-03-28-mediatek-google-orders-and-broadcom-share-shift-2026-02]]).
			- #### TPU v9 / Triggerfish — Incremental Google Order (2026 industry check)
				- Google is developing a codename **Triggerfish** upgrade chip on top of TPU v9 / Humufish, with MediaTek exclusively receiving this incremental order at a **~30% higher unit price** than Humufish.
				- Triggerfish vs. Humufish — key architecture differences:
					- | Dimension | Humufish (TPU v9) | Triggerfish (v9 upgrade) |
					  |---|---|---|
					  | SRAM capacity | baseline | **2–3× Humufish** |
					  | Simulation die | none | **new die** (RL + AI agent; local TPU mgmt; train/infer mode switching) |
					  | HBM generation | HBM4 | **HBM4E** |
				- **Why larger SRAM**: keeps more of the active working set for RL workloads and AI-agent collaboration local to the TPU → reduces data-movement cost → improves ultra-low-latency decode efficiency. Designed to address **both CPU wall and memory wall** simultaneously.
				- **Simulation die functions**: local TPU resource management, training/inference mode switching, and — most importantly — enabling **reinforcement learning (RL)** and **multi-agent AI** workloads natively on the TPU cluster.
				- Volume and revenue bridge (updated FundaAI, Jun 2026):
					- | Metric | Humufish (TPU v9) | Triggerfish | Combined |
					  |---|---|---|---|
					  | Lifecycle units | ~3–3.5M (~half) | ~3–3.5M (~half) | **6–7M** (raised from prior 5M) |
					  | Mass production start | **Q3 2027** | **Q4 2027** | — |
					  | Volume ramp | 2028 | 2028 | — |
					  | ASP (FundaAI est.) | **\$15k** | **\$20k** | blended ~\$17.5k |
					  | Unit price delta | baseline | **~+30%** | — |
				- **Lifecycle revenue implied**: 6.5M units × \$17.5k blended ASP = **~\$114B total program TAM** across both chips.
				- **Substrate is the primary bottleneck**: Google is actively pushing substrate manufacturers to expand capacity to support the 2028 ramp.
				- **Triggerfish CPU die**: beyond the SRAM expansion, Triggerfish integrates a **new MediaTek-developed CPU die** for workload switching between training and inference — MediaTek IP embedded in the package, carrying higher margin than pass-through wafer volume and deepening design content per unit.
				- **Pumafish**: confirmed cancelled; no supply-chain evidence of restart. Volume excluded from the 6–7M figure.
				- Triggerfish is incremental to the Humufish base — a new 2028 revenue driver for MediaTek at higher ASP, further cementing its position as Google's preferred TPU v9-generation design partner.
			- **Anthropic is most likely to do the same in the long run**: as its own custom-silicon ambitions mature, Anthropic is strongly motivated to diversify accelerator design away from a single partner — a second leg of MediaTek's ASIC-design TAM. This generalizes the thesis from "Google's second source" to **MediaTek as the default second-source ASIC design house for any scaling AI compute buyer**.
		- #### SerDes Win: MediaTek 336G Displaces Broadcom 448G on TPU v9 (Jun 2026)
			- MediaTek secured the **primary TPU v9 ASIC contract via 336G SerDes**, directly displacing Broadcom which had targeted 448G SerDes.
			- **Why Broadcom lost**: 448G SerDes stalled on signal integrity, power, and thermal dissipation — unresolvable within Google's timeline. The 448G optical module design requires a **2nm process node**, pushing volume production to **2028–2029** — too late for the TPU v9 ramp.
			- **Why MediaTek won**: multi-year accumulated high-speed interface IP + deep TSMC advanced-process collaboration. Same structural advantages as the Semi-COT model — execution capabilities that pure fabless vendors without equivalent TSMC integration cannot replicate on the same timeline.
			- **Structural shift**: AI ASIC vendor differentiation is moving from compute chip design to **integrated system capability** — SerDes, optical interconnect co-design, and system-level architecture. MediaTek's IP depth here is a compounding moat.
			- **AVGO v9 training chip**: Broadcom's status on the TPU v9 *training* chip contract remains pending (FundaAI, Jun 2026) — a separate contract from the inference/SerDes work MediaTek won.
			- Source: Commercial Times (工商時報) Jun 23 2026 ([[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]])
	- ### AI ASIC Revenue Trajectory
		- | Year | AI Accelerator ASIC Revenue | Primary drivers |
		  |---|---|---|
		  | 2026E | **\$2B** (revised up) | Google TPU v9 ramp |
		  | 2027E | **Tens of billions** | TPU v9 volume + multiple CSP programs |
		- 2027 projection requires multiple CSP programs (beyond Google) to begin volume production — execution risk is real but pipeline is confirmed to exist.
		- **2027 total Google TPU shipment forecast** (all vendors): **10–11M units** (FundaAI Jun 2026; raised from 10M+ in April). MediaTek's share of this via Humufish + Triggerfish: 6–7M lifecycle units across 2027–2028 ramp.
	- ### Consumer Chips — Nvidia RTX Spark Partnership
		- MediaTek is the **design partner with Nvidia on the RTX Spark chip**.
		- **Nvidia is redefining endpoint devices**: For the past 40 years the PC industry revolved around the operating system and applications; the future shifts toward a new computing architecture centered on **LLMs and AI agents**. RTX Spark is not aiming for pure PC market share but for **the user entry point of the AI era**.
		- **Why Nvidia needs MediaTek**: MediaTek has cultivated the smartphone and mobile-computing markets for 20+ years, shipping billions of SoCs annually and accumulating deep technology and IP across **CPU, GPU, NPU, 5G comms, ISP, and power management**. By contrast, Nvidia once tried to enter mobile via Tegra but never built economies of scale. Even if Nvidia keeps strengthening its CPU layout, it is unlikely to fully abandon MediaTek — the partnership is the **lowest-cost, highest-efficiency** choice, and it means Nvidia does not need to assemble a huge in-house CPU R&D team.
	- ---
- ## Napkin Math
	- > Back-of-the-envelope valuation anchored to a 5- and 10-year horizon. Size the TAM, project revenue and margins, and work backward to what you are paying today.
	-
	- | FY | 2031E | 2026YTD | 2025 | 2024 | 2023 |
	  |---|---:|---:|---:|---:|---:|
	  | Revenue $M |  |  |  |  |  |
	  | YoY |  |  |  |  |  |
	  | Gross margin % |  |  |  |  |  |
	  | R&D % |  |  |  |  |  |
	  | S&M % |  |  |  |  |  |
	  | Capex % |  |  |  |  |  |
	  | Other expenses % |  |  |  |  |  |
	  | SBC dilution YoY |  |  |  |  |  |
	  
	  ---
- ## Durable and Unfair Competitive Advantages
	- > What does the company do that is genuinely hard to replicate — not tied to a single product but woven into its identity? Moats are time-bound, not permanent. At best they are a bridge. The question is whether the company is using that bridge to reach the next defensible position, or standing still while competitors close the gap.
	- ---
- ## Key Value Drivers
	- > The critical metrics to monitor for the narrative to play out — e.g., revenue growth, gross margin expansion, share repurchases, cost structure improvements, new product attach rates. If these move in the right direction, the thesis is on track; if they stall, revisit.
	- ---
- ## Secular Trends as Tailwinds
	- > Which macro or structural forces are at the company's back, independent of execution? The best businesses ride a wave — name the waves and explain why the company is well-positioned to capture them.
	- ---
- ## Innovative Culture
	- > Does the company's culture enable compounding innovation? Signs of yes: fast product cycles, willingness to cannibalize existing revenue, strong engineering or R&D culture, founder involvement, low bureaucracy. Signs of no: consensus-driven decisions, feature bloat, talent attrition, reliance on acquisitions to stay relevant.
	- ---
- ## Vibe Checks
	- **What do you like most?**
		-
	- **What do you hate most?**
		-
	- **How popular is the product or service?**
		- ---
- ## Competition Landscape
	- > Who are the real competitors — incumbents, new entrants, and platform substitutes? For each, assess: how much of the TAM can they realistically take, and on what timeline? Is the competitive intensity increasing or decreasing?
	-
	- | Competitor | Threat level | Key advantage | Assessment |
	  |------------|-------------|---------------|------------|
	  |            |             |               |            |
	  
	  ---
- ## Pre-Mortem — What Can Go Wrong?
	- > Assume the thesis fails. Work backward: what caused it? List the top risks in order of likelihood × impact. Distinguish between risks that invalidate the thesis entirely versus ones that merely delay it.
	- 1.
	  2.
	  3.
	  
	  ---
- ## Friendly to Shareholders?
	- > How does management treat outside shareholders? Examine: share dilution rate, executive compensation structure and alignment, history of buybacks (price-disciplined or reflexive?), dividend policy, related-party transactions, and candor in shareholder communications.
	-
	- | Factor | Signal | Assessment |
	  |--------|--------|------------|
	  | Share dilution (annual %) |  |  |
	  | Executive comp structure |  |  |
	  | Buyback history |  |  |
	  | Dividend |  |  |
	  | Insider ownership |  |  |
	  
	  ---
- ## Anecdotes & Opinions
	- > First-hand observations, user stories, expert opinions, or social proof that supports or challenges the thesis. These are qualitative data points that don't fit neatly into a model but are often early signals — a product someone can't live without, a salesperson who says the pipeline is dry, a developer who switched away. Capture the source and date so you can revisit whether the signal aged well.
	-
	- | Date | Source | Anecdote / Opinion | Signal direction |
	  |------|--------|--------------------|-----------------|
	  | 2026-06 | Industry check (private) | **Google Triggerfish**: Google developing a v9 upgrade (Triggerfish) exclusively with MediaTek; SRAM 2–3× Humufish, new simulation die (RL/AI-agent), HBM4→HBM4E. Triggerfish adds 1–2M incremental units to the 4–5M Humufish base; production late 2027, volume 2028; unit price ~30% above Humufish → new 2028 earnings driver. | bullish |
  | 2026-06 | Industry chatter / personal view | The current rumor is that MediaTek's order volume for Google's next-generation TPU will be even larger — and I agree. The 8th-gen TPU shipping now had its capacity booked two years ago, when Google had not yet reserved nearly as much capacity. TSMC currently cannot let MediaTek add much capacity, so as more capacity is allocated, the next-gen Google order should ramp materially larger. | bullish |
  | 2026-06-23 | Commercial Times (工商時報) | **SerDes win confirmed**: MediaTek wins Google TPU v9 primary contract via **336G SerDes**, displacing Broadcom (whose 448G approach failed on signal integrity / power / thermal; 448G optical module needs 2nm, volume not until 2028–2029). AI ASIC revenue: **\$2B 2026E**, "tens of billions" 2027E. Multiple CSP programs expected to materialize beyond Google. | bullish |
  | 2026-06 | FundaAI-T channel check | **H+T volume raised to 6–7M lifecycle units** (up from prior 5M). Humufish ASP \$15k, Triggerfish ASP \$20k, ~half each. Substrate is primary bottleneck; Google pushing substrate makers to expand. Triggerfish adds MediaTek-developed CPU die (training/inference workload switching). Pumafish cancellation maintained — no restart signal. AVGO v9 training chip: still pending. 2027 total TPU forecast: **10–11M units** (vs. 10M+ at end-April). | bullish |