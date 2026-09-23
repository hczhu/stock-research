- tags:: [[$NVDA]], [[$TSM]], [[semiconductor]], [[AI]], [[inference]], [[HBM]], [[DRAM]], [[Cerebras]], [[Groq]], [[hyperscalers]], [[private-credit]], [[$CRWV]], [[capex]], [[orbital-compute]]
  file-created-at:: 2026-06-03

- ## Gavin Baker on Semiconductor & AI Infrastructure: Watts, Wafers, and the Next Phase
	- **Source**: Patrick O'Shaughnessy × Gavin Baker conversation, June 2026

- ## 1. The Core Constraints: Watts and Wafers
	- Gavin structures the next phase of AI computing around two distinct physical bottlenecks:
	- **Watts (Power Supply):**
		- **The Near-Term Outlook**: Gavin argues that capitalism will solve the near-term power shortage. He expects the bottleneck to begin alleviating in 2027 and 2028 as massive new turbine capacity and energy sources come online.
		- **The Gating Shift**: According to data center infrastructure private equity sources (Blackstone, Apollo, KKR), the primary gating factors have shifted from pure energy and chips to local zoning laws and regulatory approvals.
		- **Orbital Compute (The Long-Term Solution)**: Terrestrial power regulations will eventually push inference into space. Gavin redefines "orbital compute" not as floating buildings, but as individual Blackwell-sized racks in space (3,000 lbs, 8ft high, 4ft deep, 3ft wide) operating in sun-synchronous orbits with 500-foot solar wings.
	- **Wafers (Supply & Bubble Prevention):**
		- **TSMC as the Ultimate Governor**: Gavin believes that the fundamental wafer shortage—tightly managed by Taiwan Semiconductor Manufacturing Company (TSMC)—is the single variable preventing a massive macroeconomic AI bubble.
		- **Latent Demand Data Point**: If TSMC expanded capacity to meet unconstrained demand, Gavin estimates Nvidia could sell $2 trillion to $3 trillion worth of GPUs in 2026 or 2027.
		- **The Discipline Risk**: Historically, semiconductor cycles break because trailing players fail to maintain discipline. The key metric to watch for a potential market crash is whether Intel or Samsung breaks discipline and expands capacity too aggressively to secure a 30%+ market share.

- ## 2. Chip Architectural Shifts and Startup Dynamics
	- The physical limitations of current manufacturing lines are forcing a richer canvas for chip design:
	- **The Iron Triangle of Chip Design**: Designers must constantly trade off between attack (compute), defense (memory capacity), and mobility (memory bandwidth). Because they must live within TSMC's strict design rules, startups cannot win by simply trying to build a "better GPU." Nvidia will always receive better pricing and possesses deep design partnerships with every major model builder.
	- **The Disaggregation of Pre-fill and Inference**: This architectural shift opens up the canvas for new chip designs by separating the two core parts of processing:
		- **Pre-fill (Loading the Cannon)**: The model processes the prompt and context. This is fundamentally a memory capacity-bound problem.
		- **Decode (Firing the Cannon)**: The process of generating new tokens. This is a memory bandwidth-constrained problem.
	- **Startup Evaluation ("Different and Hard")**: For a semiconductor startup to succeed, its architecture must make aggressive, non-obvious trade-offs in the pre-fill or decode canvas that are physically hard to duplicate. Gavin notes that Cerebras succeeded by choosing wafer-scale computing, though it requires solving extreme I/O constraints along the chip's "shoreline" (potentially via optical wafer bonding).
	- **Venture Return Benchmark**: Gavin uses a rule of thumb that capturing just 1% of market share in this environment yields a $100 billion venture outcome.

- ## 3. Financial Implications: Useful Life and Private Credit
	- A major debate among AI skeptics centers on the rapid depreciation of hardware assets. Gavin strongly pushes back on this using recent technical shifts:
	- **10 to 15-Year GPU Lifespans**: Skeptics argue GPUs have a useful life of only 1 to 2 years due to rapid obsolescence. Gavin counters that the disaggregation of pre-fill and inference completely alters hardware economics.
	- **Repurposing Legacy Hardware**: Operators can now place ultra-fast specialized chips (like Cerebras systems or Groq LPUs) in front of legacy units like an Nvidia Hopper or Ampere. The older, slower GPUs are repurposed strictly to handle the memory-heavy pre-fill stage, extending their useful operational lives "until they melt" (10 to 15 years).
	- **Impact on Private Credit**: This extended lifespan mathematically alters the risk profile for the private credit firms financing the AI buildout. Instead of underwriting equipment loans on aggressive 3-to-4-year timelines, extended lifespans allow for lower financing costs. Gavin notes CoreWeave's lowest financing was previously in the low 7% range, but extended asset lives make financing at 5% to 6% possible.

- ## 4. The Geopolitical and Competitive Landscape
	- **Elon Musk's "TerraFab"**: A joint project involving SpaceX and Tesla to build the world's largest semiconductor fabrication plant in the United States.
		- **The Strategy**: It leverages Intel's 50 years of institutional knowledge, putting it roughly 3 to 5 quarters behind the absolute leading edge.
		- **Talent Acquisition**: It relies on Elon's reputation in hardware engineering to recruit top-tier talent from Asia by building localized "Taiwan Towns," "Japan Towns," and "Korea Towns" directly next to the Texas fab to transplant entire restaurant and support staffs for the engineers.
	- **The Asymmetry of Valuations**: Gavin points out a glaring cross-sectional inefficiency in the semiconductor market driven by temporary commodity shortages:
		- Semi-Cap Equipment Companies have been trading at 40x next quarter's annualized earnings.
		- DRAM (Memory) Companies have traded at mid-single-digit multiples.
		- During previous cyclical peaks, this gap was only 5x versus 12x. Gavin argues that while Semi-Cap models have improved via recurring maintenance revenue, it does not justify a 1,000% multiple disparity, rendering memory structurally undervalued relative to its importance in HBM (High Bandwidth Memory).
	- **Hyperscaler Dynamics (The "Sellers" vs. "Buyers" of Shortage)**: While the market heavily favors the sellers of hardware (Nvidia), the "buyers" (hyperscalers like Google, Amazon, and Microsoft) possess a hidden advantage in an agentic AI world. Agents require immense orchestration and tool calls, which are heavily reliant on traditional CPUs. The hyperscalers own the largest installed legacy CPU fleets in the world, positioning them to capture a massive wave of downstream monetization.
