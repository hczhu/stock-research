- tags:: [[$NVDA]], [[Nvidia]], [[AI infrastructure]], [[capex]], [[TAM]], [[data-center]], [[accelerated-computing]], [[agents]], [[robotics]], [[semiconductors]]

- **Source**: NVIDIA investor/IR slide, dated **October 2025** — "\$3–4 Trillion AI Infrastructure Spend by 2030: Key TAM Growth Drivers," with a chart of global data-center capex (public cloud, private cloud, enterprise on-prem, edge) vs NVIDIA AI revenue, 2022–2030. This is NVIDIA's own TAM framing — treat as a company-interested source. Companion to [[2026-07-07-hyperscaler-capex-goldman-bofa-cy27-28e]], [[2026-06-03-gavin-baker-semiconductor-ai-infrastructure-thesis]], and [[DRAM-memory-ssd-index-thesis]].

- **Headline claim**: **\$3–4T cumulative-scale AI infrastructure (data-center capex) by 2030**, growing at **~40% 5-year CAGR (2025–2030)**. Chart shows DC capex rising from a few hundred \$B (2022–24) through ~\$700B (2025) → ~\$950B (2026) → ~\$1.3T (2027) → ~\$1.8T (2028) → ~\$2.4T (2029) → **~\$3.5T (2030)** (bars approximate). NVIDIA AI revenue shown as a small green sliver in 2022–24 — visually implying most of the TAM is still ahead.

- ## The Five TAM Growth Drivers (NVIDIA's argument, with their data points)
	- **1. End of Moore's Law → shift from general-purpose to accelerated computing.** Every CPU workload is a conversion candidate:
		- Data processing: cuDF/cuML/cuVS accelerate structured + unstructured processing **10–100×** over CPU.
		- Computational lithography: cuLitho **40–60×** over CPU for photomask generation (note: sold *into* TSMC/ASML workflows — the fab ecosystem itself becomes an accelerated-computing customer).
		- Genomics: deciphEHR via Parabricks — **>5× faster alignment, >10× faster variant calling**.
	- **2. Hyperscale shift to Generative AI.** Existing internet workloads re-platform onto GenAI:
		- Ad generation: Google AI-powered YouTube video campaigns deliver **17% higher ROAS** than manual.
		- Recommenders: Pinterest moved to **100× larger recommender models** on NVIDIA GPUs → **+16% engagement**.
		- Search and UGC moving to LLM-powered generative AI.
	- **3. Model makers — "a new industry."** OpenAI, Google, Anthropic, xAI, Meta building the foundations of AI — i.e., frontier-lab training demand is a *structurally new* customer class, not a reallocation of existing IT budgets. (Matches the NBER finding that the closed frontier is a capital-gated 10-firm club — [[2026-07-13-emerging-market-for-intelligence-nber-llm-pricing]].)
	- **4. Enterprise — agentic AI enters the labor market.** The TAM argument shifts from IT budgets to **labor budgets**:
		- Coding: developers with AI assistants complete tasks **up to 55% faster** (MIT study).
		- Vibe coding: Lovable opens coding to designers, creatives, marketing, IT, teachers.
		- Legal: **STARA** did a statutory-research task that takes two humans **8–13.5 hours / ~\$3,000** in **20 minutes for ~\$0.86** — a ~3,500× cost reduction; the flagship agentic-economics data point on the slide.
	- **5. Robotics, AV, factories, edge — Physical AI.** "Labor shortages drive everything that moves in **\$50T industrials** to be autonomous" — the option-value layer of the TAM (echoes Micron's humanoid-robot memory thesis in [[MU-2026-Q2]]).

- ## Read-Through
	- **The TAM ladder**: each driver is bigger and later — (1) converts the existing ~\$1T compute installed base, (2) converts internet opex, (3) adds frontier-lab capex, (4) attacks labor budgets (orders of magnitude larger than IT), (5) attacks the \$50T physical economy. The structure is designed to argue the spend is *early*, not peaking — NVIDIA's answer to the AI-bubble/capital-cycle debate ([[2026-06-18-ai-bubble-debate-capital-cycle-cyclicality-podcast]]).
	- **Cross-check vs third parties**: the slide's ~\$950B (2026) → ~\$1.3T (2027) DC-capex path is *above* the Goldman/BofA hyperscaler-capex trajectories ([[2026-07-07-hyperscaler-capex-goldman-bofa-cy27-28e]]) because it includes private cloud, enterprise on-prem, and edge — the broadest possible definition. BofA's separate "US chip demand to \$2.7T by 2030, 28% CAGR" ([[DRAM-memory-ssd-index-thesis]]) is directionally consistent.
	- **For the supply chain**: if even the low end (\$3T) materializes, the binding constraints stay the usual suspects — TSMC leading-edge + CoWoS ([[TSMC-TSM-thesis]]), HBM/DRAM ([[DRAM-memory-ssd-index-thesis]]), and power. A 40% capex CAGR against ~30%/yr DRAM bit-growth ceilings implies the memory-scarcity regime persists through the window.
	- **Skeptic's flags**: (a) NVIDIA is talking its book — the chart conflates *all* DC capex with its TAM while its own revenue is the green sliver; (b) the agentic examples (STARA \$0.86, 55% coding speedup) are best-case anecdotes, and the NBER paper shows enterprises actually buy *below-frontier* intelligence at falling prices — revenue per task deflates fast even as tasks grow; (c) ASIC share of that capex (Google/Amazon/Meta/OpenAI custom silicon, [[2026-07-06-openai-broadcom-jalapeno-hn-cerebras-hbm-readthrough]]) grows faster than GPU share, so DC-capex TAM ≠ NVIDIA revenue at historical capture rates.
