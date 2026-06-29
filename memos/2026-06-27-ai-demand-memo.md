- tags:: [[AI infrastructure]], [[hyperscalers]], [[capex]], [[data-center]], [[inference]], [[DRAM]], [[HBM]], [[$AMZN]], [[$MSFT]], [[$GOOGL]], [[$ORCL]]

- **Source**: User-provided Exponential View / Ramp / Reddit screenshots and charts, extracted into memo form on 2026-06-27.

- ## Latest backlog by company
	- Data points below use the explicit labels from the chart. Shares use the labeled company values, which sum to **\$2.018T**, close to the chart headline of **\$2.0T**.
	  
	  | Company | Backlog ($B) | Share of labeled total | Chart definition / caveat | AI demand read-through |
	  |---|---:|---:|---|---|
	  | Microsoft | 633 | 31.4% | Total RPO, includes M365 / Dynamics | Largest backlog base; Azure AI demand is mixed with broader enterprise software obligations |
	  | Oracle | 553 | 27.4% | Quarter ends one month earlier | Most visibly AI-cloud-driven backlog acceleration; OCI capacity commitments are a major signal |
	  | Google | 468 | 23.2% | Revenue backlog, mostly Cloud | Cloud backlog confirms Google is now participating more directly in AI infrastructure demand |
	  | Amazon | 364 | 18.0% | Total company RPO, mostly AWS | AWS backlog remains large, but labeled backlog is below Microsoft / Oracle / Google in this chart |
	  | **Total** | **2,018** | **100.0%** | Chart headline rounds to **$2.0T** | Contracted demand supports multi-year AI infrastructure buildout |
- ## Combined backlog trend
	- The chart is a stacked area chart, so historical totals below are **visual estimates** rather than labeled datapoints. They are useful for direction and scale, not precise modeling.
	  
	  | Point in time | Combined backlog ($B, approx.) | Increment vs. prior point | Read |
	  |---|---:|---:|---|
	  | 2020 | ~180 | n/a | Pre-GenAI cloud backlog base |
	  | 2021 | ~230 | +~50 | Normal cloud growth before the AI acceleration |
	  | 2022 | ~320 | +~90 | Backlog grows steadily before ChatGPT launch |
	  | ChatGPT launch / late 2022 | ~400 | +~80 | Inflection marker before the visible acceleration |
	  | 2023 | ~470 | +~70 | Early post-ChatGPT backlog growth, still gradual |
	  | 2024 | ~600 | +~130 | AI demand begins to show more clearly in contracted obligations |
	  | 2025 | ~750 | +~150 | Backlog growth continues before the sharp 2025-2026 ramp |
	  | 2026 latest | ~2,000 | +~1,250 | Step-function backlog expansion; AI infrastructure commitments become the dominant story |
- ## Stock implications
	- **AI infrastructure demand is contract-backed**: A $2T backlog makes the AI buildout look less like speculative spot demand and more like a multi-year contracted capacity cycle.
	- **Positive for the picks-and-shovels chain**: Sustained backlog supports demand for GPUs, networking, optical components, power equipment, memory, storage, and data-center construction.
	- **Oracle is the surprise signal**: Oracle's $553B backlog is unusually large relative to its historical cloud share, suggesting OCI AI contracts are changing its growth profile.
	- **Microsoft remains the broadest platform beneficiary**: Microsoft has the largest labeled backlog, but interpretation is harder because total RPO includes non-Azure software obligations.
	- **Memory read-through is constructive**: If hyperscaler backlog converts into deployed AI capacity, it reinforces demand for HBM, server DRAM, enterprise SSDs, and potentially new memory tiers such as HBF.
- ## Data center power scaling
	- Source: Exponential View analysis; TOP500 / Green500; Epoch AI; OpenAI; Oracle.
	- The chart tracks the power of the most powerful computers over time. Values below use explicit chart labels where available; target projects are not completed capacity.
	  
	  | System / project | Category | Approx. date | Power | Multiple vs. prior labeled point | Chart note |
	  |---|---|---:|---:|---:|---|
	  | Cray-1 | Leading supercomputer | 1980 | 0.12 MW | n/a | 160 MFLOP/s |
	  | Cray Y-MP | Leading supercomputer | 1990 | 0.15 MW | 1.3x | ~2.6 GFLOP/s |
	  | ASCI Red | Leading supercomputer | 1997 | 0.85 MW | 5.7x | First teraflop |
	  | Earth Simulator | Leading supercomputer | 2002 | 6.4 MW | 7.5x | Fastest 2002-04 |
	  | Summit | Leading supercomputer | 2018 | 13 MW | 2.0x | TOP500 #1 |
	  | Frontier | Leading supercomputer | 2022 | 21 MW | 1.6x | First exaflop |
	  | xAI Colossus | AI data center | Early 2025 | ~300 MW | 14.3x | 200k+ GPUs |
	  | Rainier, New Carlisle | AI data center | Mar 2026 | ~1.1 GW | 3.7x | 500k+ Trainium2 |
	  | Rainier full build | Target under construction | Target | ~2.3 GW | 2.1x | ~30 buildings |
	- **Read**: The shift from supercomputer to AI data center changes the unit of competition from single-machine power to campus-scale power. Frontier's 21 MW exaflop system in 2022 compares with Rainier's ~1.1 GW 2026 AI data center, a **~52x increase in four years**. The Rainier full-build target of ~2.3 GW would be **~110x Frontier**.
	- **Stock implication**: AI demand is no longer just a semiconductor content story; it is also a power, land, grid interconnect, cooling, networking, memory, and construction bottleneck story. The capex beneficiaries broaden as AI clusters move from tens of MW to gigawatt-scale campuses.
- ## Data center build-cost mix shift
	- Source: Exponential View analysis; Goldman Sachs; Epoch AI; SemiAnalysis.
	- The chart compares share of total data-center build cost by component in 2021 vs. 2026E. Figures may not sum perfectly because of rounding.
	  
	  | Component | 2021 share | 2026E share | Change | Relative change | Stock read-through |
	  |---|---:|---:|---:|---:|---|
	  | Memory | 2% | 18% | +16 pp | 9.0x | Biggest mix shift; directly supports HBM, DRAM, and high-value memory suppliers |
	  | Logic | 38% | 42% | +4 pp | +11% | Compute share still grows, but much less dramatically than memory |
	  | **Chips total** | **40%** | **60%** | **+20 pp** | **+50%** | Each incremental data-center dollar buys more silicon and less concrete |
	  | Cooling | 15% | 10% | -5 pp | -33% | Still important, but share is diluted by the rising chip bill of materials |
	  | Power | 25% | 15% | -10 pp | -40% | Absolute power spend can rise even as mix share falls |
	  | Building | 20% | 15% | -5 pp | -25% | Physical shell becomes a smaller share of the total build |
	- **Read**: AI data centers are becoming more silicon-intensive. Chips rise from **40% to 60%** of build cost, while memory alone rises from **2% to 18%**. This is the cleanest version of the memory thesis: AI buildout does not just increase total data-center capex; it increases the memory share of each capex dollar.
	- **Stock implication**: The mix shift is most bullish for memory and compute suppliers because they capture a larger share of a rapidly growing spend pool. It is still positive for power/cooling/building suppliers in absolute dollars if total data-center capex grows fast enough, but their share of the buildout wallet is falling.
- ## AI revenue penetration vs. macro yardsticks
	- Source: Exponential View analysis; St. Louis Fed.
	- The chart compares global AI revenues excluding China against U.S. GDP, U.S. labor costs, and U.S. corporate profits. Endpoint labels are explicit chart values; intermediate values below are visual estimates from the line chart.
	  
	  | Metric | Q1 2024 | Q1 2025 | Latest / 2026 | Growth vs. Q1 2024 | Growth vs. Q1 2025 | Read |
	  |---|---:|---:|---:|---:|---:|---|
	  | AI revenue as % of GDP | 0.04% | 0.13% | 0.42% | 10.5x | 3.2x | Still tiny relative to the economy, but compounding quickly |
	  | AI revenue as % of labor costs | ~0.08% | ~0.22% | 0.8% | ~10.0x | ~3.6x | Labor substitution / augmentation TAM remains much larger than current revenue |
	  | AI revenue as % of corporate profits | ~0.32% | ~0.9% | 3.0% | ~9.4x | ~3.3x | Even the generous profits yardstick is still ~32x larger than GenAI revenue |
	- **Latest macro comparison**:
	  
	  | Yardstick | AI revenue penetration | Implied remaining headroom |
	  |---|---:|---|
	  | U.S. GDP | 0.42% | AI revenue is still a rounding error versus total economic output |
	  | U.S. labor costs | 0.8% | AI revenue remains small relative to the labor-cost pool it could augment or automate |
	  | U.S. corporate profits | 3.0% | Corporate profits are still roughly **32x** larger than all GenAI revenues |
	  | IT sector share of GDP | 9.4% | AI revenue is far below the existing IT sector's economic footprint |
	- **Read**: The demand debate should separate growth rate from penetration. AI revenue has already risen about **10x vs. Q1 2024** and **3x vs. Q1 2025** relative to GDP, but the endpoint is still only **0.42% of U.S. GDP**. That supports the "still early" part of the AI demand thesis: rapid revenue growth can continue for a long time before AI becomes a macro-sized revenue pool.
	- **Stock implication**: The chart is bullish for long-duration AI demand because current AI revenue is small relative to the economic pools it targets. It is especially relevant for software, cloud, model providers, AI infrastructure, and memory suppliers: infrastructure spend can look large today while end-market AI revenue is still early in penetration terms.
- ## Company-level AI spend is still small
	- Source: Exponential View analysis; Ramp Economics Lab (n = 70,000 U.S. businesses); Uber filings.
	- Left chart: AI spend per employee per month across Ramp customers, compared with Uber's max per-engineer cap. The lines are log scale; values below are approximate visual reads.
	  
	  | Group | Jul 2023 spend / employee / month | Latest 2026 spend / employee / month | Approx. increase | Read |
	  |---|---:|---:|---:|---|
	  | Median Ramp customer | ~$2 | ~$11 | ~5.5x | Median AI spend is still negligible at the company level |
	  | Top 10% Ramp customer | ~$60 | ~$600 | ~10x | Heavy adopters are scaling spend, but still below Uber's cap |
	  | Top 1% Ramp customer | ~$600 | ~$7,500 | ~12.5x | The most aggressive adopters already spend several thousand dollars per employee per month |
	  | Uber cap | $1,500 | $1,500 | flat | Uber's cap puts it roughly in the top 10% of Ramp per-employee AI spend |
	- Right chart: Uber max-cap AI spend for 5,000 engineers versus FY2025 P&L line items. Percentages are explicit chart labels.
	  
	  | Uber line item | FY2025 amount | AI spend for 5k engineers | AI spend as % of line item | Read |
	  |---|---:|---:|---:|---|
	  | AI spend for 5k engineers | $90M | $90M | 100% | $1.5k / engineer / month = $18k / year; 5k engineers = $90M / year |
	  | D&A | $720M | $90M | 12% | Meaningful versus D&A, but not a major P&L burden |
	  | R&D | $3.4B | $90M | 2.6% | Small relative to engineering / product investment budget |
	  | People opex | $14B | $90M | 0.6% | Barely moves the total people-cost base |
	  | EBITDA | $8.7B | $90M | 1.0% | Small relative to profitability |
	  | Revenue | $52B | $90M | 0.2% | Almost invisible against revenue |
	- **Read**: The chart reframes enterprise AI adoption. Even an aggressive **$1.5k per engineer per month** cap is only **$90M/year** for 5,000 engineers, or **0.2% of Uber revenue** and **2.6% of R&D**. AI usage can grow substantially before it becomes a major P&L line item for large companies.
	- **Stock implication**: This supports continued AI software and inference demand growth because budget headroom remains large. The constraint is less "can enterprises afford AI?" and more whether AI tools create enough productivity to justify broader rollout. For model providers and AI infrastructure, the key is that enterprise usage can scale from small P&L percentages into much larger absolute dollars across a broad customer base.
- ## Anecdotes
	- **Large insurance company ran out of tokens**
		- Source: Reddit post on `r/csMajors` by `u/jmclondon97`, screenshot provided by user, dated roughly 14 hours before capture.
		- A large U.S. insurance company reportedly uses GitLab Duo Agent for software engineering workflows, including repo access and code review.
		- The company reportedly sent a notice that it had run out of tokens until July.
		- Follow-up guidance reportedly told employees to be more mindful of usage, imposed individual limits, and steered them away from expensive models toward cheaper ones first.
		- The bottleneck is not employee willingness to use the tools; it is cost governance and model routing.
- ## Reference links
	- | | |
	  |---|---|
	  | [GPU pricing index dashboard](https://semianalysis.com/gpu-pricing-index/) | |
- ## Caveats
	- Backlog is not the same as revenue. Timing, cancellation terms, capacity availability, and customer concentration matter.
	- Company definitions are not identical, so cross-company comparisons are directionally useful but not perfectly apples-to-apples.
	- The chart does not isolate AI-only backlog. Some Microsoft, Amazon, and Google obligations include non-AI cloud or software commitments.
	- The historical trend table is visually estimated from the chart, while the latest company values are explicit chart labels.
	- The data-center power table mixes completed systems, announced data centers, and targets under construction. It is best used to understand order-of-magnitude scaling, not as a like-for-like efficiency comparison.
	- Build-cost shares do not indicate absolute dollars. A component can lose share and still grow revenue if total AI data-center capex expands fast enough.
	- AI revenue penetration uses global AI revenue excluding China against U.S. macro denominators, so it is best read as a scale comparison rather than a strict geographic accounting ratio.
	- Ramp spend distribution is based on customer-card spend and may miss direct enterprise contracts, cloud-bundled AI spend, or internally allocated AI infrastructure costs.
	- The Reddit anecdote is a single self-reported account and should be treated as directional color, not audited enterprise data.
