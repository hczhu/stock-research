- tags:: [[DRAM]], [[HBM]], [[bear-case]], [[cycle]], [[AI]], [[$000660.KS]], [[$005930.KS]], [[$MU]], [[CXMT]], [[efficiency]], [[X-post]]
  file-created-at:: 2026-06-02

- ## X Post (paste directly — single post, X Premium)

	- ---
	  Unpopular take: this memory cycle ends like every other one. Ten reasons the "super cycle" thesis is more fragile than it looks.

	  ——

	  1/ "This time is different" appears at the peak of every major memory cycle — and has always been wrong.

	  The 1990s PC-driven DRAM boom produced claims of structural new demand so strong that 15+ global suppliers were justified. The 2000s enterprise server cycle came with identical arguments about permanent demand and supply being structurally unable to keep pace. The 2010s smartphone supercycle generated the same "this cycle is categorically different" consensus. All three ended in significant crashes.

	  The current cycle has produced the strongest version of this narrative in memory's history. Goldman Sachs is revising SK Hynix operating profit up 21–24%. Michael Dell is citing a 625× demand expansion. Industry analysts are describing HBM demand as "endogenous to the GPU roadmap" — effectively arguing it is a law of physics rather than a market condition. When the consensus reaches this level of conviction, it historically marks proximity to the peak, not confirmation of the thesis. Strong consensus is a contrary indicator, not a validation.

	  ——

	  2/ AI model efficiency is improving faster than memory demand — and the trend is accelerating.

	  DeepSeek-V3 was trained for approximately $1.1M. Models at GPT-4 class performance levels that cost hundreds of millions to train in 2023 are now reproducible at a tiny fraction of that cost. This is not a one-time data point; it is a compounding trend of algorithmic improvements — better architectures, better training recipes, better quantization, better sparsity — that systematically reduces the compute and memory required per unit of AI output.

	  The bull case formula is `token throughput = HBM size × HBM bandwidth`. This is correct as a hardware identity at a fixed point in time. But it ignores the efficiency of the model doing the inference. If models achieve the same capability with fewer layers, fewer parameters, lower precision, and more aggressive KV cache management, the memory requirement per user-facing AI task shrinks independently of the hardware. GPT-4-class capability is now demonstrably achievable in models a fraction of the original size. Every major hardware demand cycle in history has been disrupted by efficiency gains that made the underlying resource cheaper to use. Semiconductor logic, storage, networking, and RAM all followed this pattern. There is no structural reason AI inference is exempt.

	  ——

	  3/ The HBM performance ratio is rising to levels that create their own architectural corrective pressure.

	  The HBM performance ratio — compute throughput divided by HBM bandwidth — measures how much compute a chip is trying to drive relative to its memory bandwidth. When this ratio is high, workloads become memory-bandwidth-bound, and much of the theoretical compute sits idle waiting for data. The ratio has escalated sharply: H100 at 591, H200 at 412 (temporarily better), B200 at 1,125, B300 at 1,688, R200 at 2,692.

	  GPU vendors are adding compute much faster than they are adding HBM bandwidth. This is not sustainable from a system utilization standpoint. The higher this ratio climbs, the stronger the economic incentive for software engineers, model architects, and hardware designers to route around the bottleneck rather than pay for more of it. The responses are already underway: larger on-chip SRAM caches to reduce HBM fetches, KV cache compression to shrink the per-request HBM footprint, quantization to reduce weight and activation memory, mixture-of-experts routing to skip inactive layers, speculative decoding to reduce sequential decode steps. Each technique directly compresses HBM demand per workload. The bull case assumes this architectural pressure is absent. It is intensifying with every GPU generation.

	  ——

	  4/ Supply is ramping hard — and the timing pattern is identical to every prior oversupply cycle.

	  Memory capex is rising +26% in 2025 and +31% in 2026. SK Hynix, Samsung, and Micron are all aggressively investing in HBM capacity. TSMC is expanding CoWoS packaging. And China's CXMT is entering HBM production backed by government subsidies that make unit-level profitability entirely irrelevant — the government absorbs the cost of poor yields, allowing CXMT to flood domestic markets regardless of economics.

	  The critical point is timing. Memory production has a 12–18 month lag between investment decisions and supply additions. This means the capex being committed today translates to incremental supply arriving in 2027–2028 — precisely the window the bull case describes as peak demand. In every prior cycle without exception, supply additions arrived at scale just as demand growth began to moderate, and the combination produced oversupply rapidly and sharply. The argument that Big 3 discipline prevents this ignores a fundamental asymmetry: CXMT's capex is a geopolitical and industrial policy decision, completely decoupled from market economics. It does not respond to price signals the way a commercial enterprise would. When price eventually falls, CXMT does not cut back. That is the supply-side variable the bull case has no answer for.

	  ——

	  5/ Hyperscaler capex is guidance, not a contract — and guidance can be revised overnight.

	  The $695–725B in 2026 combined hyperscaler capex from Microsoft, Amazon, Google, and Meta is a forward-looking estimate based on management guidance issued under favorable conditions. It is not legally committed spending. Microsoft paused its datacenter buildout for over a year before resuming. Corporate boards and CFOs revise capital allocation decisions based on ROI realization, shareholder pressure, and macroeconomic conditions.

	  The scale of the current buildout is historically extreme. At approximately 5% of US annual GDP, it exceeds the telecom buildout of the early 2000s (~1.2%) by a factor of four. The railroad buildout of the 1880s — the closest historical analog — ran at ~6% of GDP and produced catastrophic overcapacity. Extreme capital allocations of this magnitude have without exception produced eventual reversion when returns proved insufficient. The question is not whether the ROI math closes; it is when. A single major hyperscaler cutting guidance by $20–30B on an earnings call — entirely plausible if enterprise AI adoption proves slower than projected — would immediately and dramatically reprice the memory supply chain. The bull case requires all four major hyperscalers to maintain their guidance levels simultaneously for years. That is a fragile dependency.

	  ——

	  6/ The demand projections are built on economics that have not yet been demonstrated at scale.

	  The bull case for memory demand ultimately rests on the assumption that AI inference will grow roughly 10× annually for several consecutive years — from 5 trillion tokens per month in early 2025 to 500+ trillion by late 2026. That growth rate is real. The question is whether it is monetized at prices that justify the underlying infrastructure cost.

	  The current state of AI inference economics is characterized by heavy subsidization. Providers are pricing tokens below cost to drive adoption, absorbing large losses on the expectation of future monetization. Groq — operating on the premise that SRAM-based inference could be commercially viable — ran at approximately −50% gross margins in 2025. The broader market is not dramatically better. If AI companies cannot charge prices that justify the infrastructure cost at scale, the buildout self-limits. Capital does not continuously flow into negative-return infrastructure. The demand growth being used to justify HBM supply investment has not yet been demonstrated to be economically self-sustaining. Assuming it will be is an assumption about the future, not an observed fact.

	  ——

	  7/ CXL memory pooling and in-memory computing are architectural substitutes gaining real traction.

	  The bull case treats each GPU as requiring a fixed, dedicated pool of HBM that scales with the model size and batch requirements. CXL (Compute Express Link) 3.0 breaks this assumption by enabling memory disaggregation: multiple processors can share a large pool of DRAM over a high-speed interconnect, rather than each carrying its own dedicated HBM. A 72-GPU cluster under CXL memory pooling can share memory capacity across nodes, reducing the per-GPU HBM requirement substantially while maintaining most of the bandwidth advantages.

	  Processing-In-Memory (PIM) architectures go further, moving compute to where the data lives rather than moving data to where the compute lives. Samsung and SK Hynix have both demonstrated PIM prototypes specifically targeting the inference workload. The economic incentive to pursue these technologies is directly proportional to the price of HBM. At current pricing — with HBM representing 9–26% of total system BOM — that incentive is very large. Expensive inputs always attract architectural substitutes. Historically, every major semiconductor bottleneck has eventually been architectured around rather than simply scaled through.

	  ——

	  8/ The Samsung variable is systematically underweighted in the bull case.

	  The oligopoly pricing discipline argument requires all three major suppliers — SK Hynix, Samsung, and Micron — to simultaneously choose margin preservation over market share. Samsung's documented historical behavior is inconsistent with this assumption. Their countercyclical production strategy is well established: in the 2022–2023 downturn, Samsung explicitly maintained output at full capacity when Hynix and Micron were cutting, accepting near-term losses to defend and expand market position.

	  Samsung is simultaneously competing for foundry business against TSMC, defending HBM market share against Hynix, recovering Samsung Mobile's collapsed margins, and protecting its memory leadership in conventional DRAM. These cross-segment pressures do not uniformly point toward margin preservation. HBM market share has strategic value to Samsung that may substantially outweigh near-term pricing discipline — particularly if Hynix's current HBM leadership begins translating into durable customer lock-in. Three suppliers constitutes a highly concentrated market, but it is not a cartel, and cartels break even when they are formal and legally enforced. An informal oligopoly that requires all participants to resist short-term gain simultaneously is fragile by construction. It only takes one actor to break the pricing structure, and Samsung has the strongest historical pattern of being that actor.

	  ——

	  9/ The contract structure is evidence of buyer uncertainty, not supplier invincibility.

	  The "Lock Volume, Don't Lock Price" (鎖量不鎖價) contract structure is presented as proof of supplier pricing power — buyers are so desperate for supply that they will commit to volume at whatever the market rate turns out to be. But read from the buyer's perspective, it reveals something different: buyers are not confident enough in their own demand trajectory to commit to a fixed price. They are hedging. They want optionality on price. That is not the behavior of a buyer who believes supply will remain structurally tight indefinitely.

	  Moreover, volume commitments in commodity markets have been walked away from, renegotiated, or contested in virtually every major downturn across industries. Energy take-or-pay contracts, LNG long-term agreements, and shipping charter commitments have all been litigated or restructured when market conditions shifted. The legal obligation exists; the commercial enforcement under adverse conditions is a different question. A hyperscaler facing a $20B inventory write-down has powerful incentives to renegotiate regardless of the original contract terms. Contracts are not demand. They are an approximation of expected demand at the time they were signed, subject to revision when reality diverges from expectation.

	  ——

	  10/ Consumer electronics is approaching a natural replacement cycle that will return conventional DRAM demand at the worst possible moment for supply.

	  Mobile shipments fell 13% in 2025. PC shipments fell 10%. Both are near or past the point of maximum replacement pressure — smartphones run approximately 3-year replacement cycles, PCs approximately 5 years. The installed base of devices past their natural replacement threshold is building. This demand has not disappeared; it has been deferred by the affordability pressure created by elevated DRAM prices.

	  When consumer demand recovers — potentially accelerated by AI-enabled device features that require meaningfully more on-device memory — conventional DRAM demand will return to the market at a time when HBM capex expansions are producing supply and CoWoS packaging capacity is coming online. The concurrent arrival of recovering consumer DRAM demand and expanding HBM supply creates conditions for a conventional DRAM price correction. A sharp drop in conventional DRAM pricing reprices the broader memory narrative even if HBM pricing holds, because it compresses the blended ASP benchmarks that underpin the super cycle story. The street will not distinguish cleanly between HBM and DRAM pricing when headlines read "memory prices falling."

	  ——

	  The bear case does not require AI to disappear. It requires only one of three things: supply growth catches demand growth — already underway; algorithmic efficiency reduces memory intensity per workload — already demonstrably occurring; or hyperscaler capex moderates from historically extreme levels — already has precedent with Microsoft's pause. Any single one of these is sufficient to end the cycle. All three are simultaneously plausible. The bull case requires all three to fail indefinitely. That is a much harder bar to clear.
	- ---

- ## Full Memo: The Memory Cycle Bear Case — Ten Arguments

- ### Thesis
	- The prevailing "super cycle" narrative rests on several assumptions that have each been falsified in prior cycles. This memo presents the strongest version of the bear case: that demand and prices will eventually correct, and that the mechanisms causing this cycle to end are already in motion.

- ### Argument 1: "This Time Is Different" Is the Peak Thesis
	- The strongest argument against the super cycle is historical: every major memory cycle has generated an identical narrative at its peak. The 1990s PC-driven DRAM boom produced claims of structural new demand that justified 15+ global suppliers. The 2000s server cycle, the 2010s smartphone cycle — each came with arguments about permanence, oligopoly pricing power, and supply being structurally unable to keep pace. Every one ended in a significant correction.
	- The current cycle has produced the strongest consensus version of the "this time is different" argument in memory's history: Michael Dell citing a 625× demand expansion, Goldman Sachs revising Hynix operating profit up 21–24%, and a widely-shared formula that HBM is now endogenous to the GPU roadmap. Strong consensus at cycle peaks is a contrary indicator, not a confirmation.

- ### Argument 2: AI Model Efficiency Is Improving Faster Than Memory Demand
	- DeepSeek-V3 was trained for approximately $1.1M — a fraction of the cost of comparable models a year prior. This is not an isolated data point; it represents a durable trend of algorithmic efficiency gains compressing the compute and memory required per unit of AI output.
	- The bull case formula `token throughput = HBM size × HBM bandwidth` is correct as a hardware identity but ignores the denominator: the number of tokens required per unit of useful work. If models achieve the same capability with fewer parameters, fewer layers, and better quantization, the memory requirement per user-facing AI task shrinks. GPT-4-class capability is now demonstrably achievable in models a fraction of the original size.
	- Algorithmic efficiency improvements have disrupted every hardware cycle they have touched. There is no structural reason AI inference is exempt.

- ### Argument 3: The HBM Performance Ratio Creates Its Own Corrective Pressure
	- The HBM performance ratio — compute throughput divided by HBM bandwidth — is escalating sharply by generation: H100 at 591, H200 at 412 (an improvement), B200 at 1,125, B300 at 1,688, R200 at 2,692.
	- The rising ratio means each GPU generation strands more theoretical compute behind memory bandwidth constraints. GPU vendors cannot indefinitely sell systems where the additional compute is increasingly bottlenecked. The economic response is architectural: larger on-chip SRAM caches, KV cache compression, quantization to lower precision, mixture-of-experts sparsity routing, speculative decoding. Each of these techniques directly reduces the amount of HBM capacity and bandwidth required per workload.
	- The higher the HBM performance ratio rises, the more aggressively software and hardware architects are incentivized to route around HBM dependency. The bull case assumes this pressure is absent; it is in fact intensifying.

- ### Argument 4: Supply Is Ramping Exactly As It Did in Prior Cycles
	- Memory capex is rising at +26% (2025) and +31% (2026), with SK Hynix, Samsung, and Micron all aggressively investing. TSMC is expanding CoWoS packaging capacity. China's CXMT is entering HBM production backed by government subsidy that makes unit-level profitability irrelevant — the government simply absorbs the cost of poor yields.
	- The production lag of 12–18 months means today's investment decisions translate to supply additions in 2027–2028. This is precisely the window the bull case describes as peak demand. In every prior cycle, supply additions arrived at scale just as demand growth moderated, and the combination produced oversupply rapidly. The timing pattern is identical.
	- The argument that the Big 3's disciplined capex prevents oversupply ignores that CXMT is not subject to commercial discipline — its capex is a geopolitical decision, not a return-on-investment calculation.

- ### Argument 5: Hyperscaler Capex Is Guidance, Not a Contract
	- The $695–725B in 2026 combined hyperscaler capex is a forward-looking estimate based on current guidance. It is not a legal obligation. Microsoft paused its datacenter buildout for over a year. The buildout, at approximately 5% of US GDP annually, is historically extreme — comparable to the 1880s railroad buildout that was followed by significant overcapacity.
	- If AI consumer and enterprise ROI does not materialize at the rate assumed, hyperscalers will moderate capex. They have strong financial discipline mechanisms: shareholder pressure, earnings guidance revisions, and board oversight. A $20B guidance cut from a single hyperscaler would immediately reprice the entire memory supply chain. The gap between guidance and committed spending can close quickly.

- ### Argument 6: Demand Projections Rest on Unproven Unit Economics
	- Token consumption projections of 10× annual growth require monetization at prices that justify the infrastructure. The current state of AI inference economics is characterized by heavy subsidization: providers are pricing tokens below cost to drive adoption, absorbing losses on the expectation of future monetization.
	- If this monetization does not materialize at scale — if consumers and enterprises prove unwilling to pay prices that justify the compute cost — the buildout self-limits. The assumption that demand will absorb all supply at current pricing is the assumption that price elasticity is zero. It never is.

- ### Argument 7: CXL Memory Pooling and In-Memory Computing Reduce Per-GPU HBM Requirements
	- CXL (Compute Express Link) 3.0 enables memory disaggregation: multiple processors sharing a large pool of DRAM over a high-speed interconnect rather than each GPU requiring dedicated HBM. If CXL adoption accelerates, effective HBM content per workload drops significantly because memory capacity can be shared across compute nodes.
	- Processing-In-Memory (PIM) architectures — where compute is moved to data rather than data to compute — go further, potentially eliminating some classes of HBM bandwidth demand entirely.
	- Both technologies have been commercially slow but have strong economic incentives now precisely because HBM is expensive. The history of semiconductor design is a history of expensive bottlenecks attracting architectural solutions. HBM is currently the most expensive bottleneck in AI infrastructure. It will attract substitutes.

- ### Argument 8: The Samsung Variable Is Underweighted
	- The oligopoly discipline argument requires all three major suppliers to behave rationally in the same direction simultaneously. Samsung's documented historical behavior is inconsistent with this assumption. Their countercyclical production strategy — maintaining or increasing output through downturns to gain market share at the expense of near-term margins — played out visibly in 2022–2023.
	- Samsung is simultaneously competing in cloud foundry (TSMC competition), HBM supply, conventional DRAM, and mobile. Their cross-segment incentives do not uniformly point toward margin preservation. HBM market share leadership has strategic value to Samsung that may outweigh near-term pricing discipline.
	- Three suppliers constitutes a highly concentrated market, but it does not constitute a cartel. The history of commodity markets shows that it only takes one major supplier to price aggressively to break an oligopoly pricing structure.

- ### Argument 9: Contract Structures Are Not Demand
	- The "Lock Volume, Don't Lock Price" (鎖量不鎖價) contract structure is presented as evidence of supplier pricing power. It can equally be read as evidence of buyer uncertainty: customers are willing to commit volume but not price, which means they do not have sufficient confidence in demand to accept price risk.
	- Take-or-pay and similar volume-commitment structures have been contested, renegotiated, or defaulted on in every major commodity downturn — energy, LNG, shipping, industrial metals. The legal commitment exists; the enforcement of it under adverse conditions is a different question. Distressed buyers in a falling market find ways to renegotiate.

- ### Argument 10: Consumer Electronics Replacement Cycle Is Building
	- Mobile shipments fell 13% and PC shipments fell 10% in 2025. Both product categories are approaching natural replacement thresholds — smartphones run approximately 3-year replacement cycles, PCs approximately 5 years. The installed base of sub-threshold devices is growing.
	- When consumer demand recovers — potentially accelerated by AI-enabled device features requiring on-device memory — conventional DRAM demand will return at precisely the time HBM supply is ramping and CoWoS packaging capacity is expanding. The resulting combination of legacy DRAM demand recovery plus HBM supply additions may create a conventional DRAM price correction that pressures the broader memory narrative, even if HBM pricing holds.

- ### Summary: What the Bear Case Requires
	- The bear case does not require AI demand to disappear. It requires only one of the following:
		- Supply growth catches demand growth (capex is already running hard)
		- Algorithmic efficiency reduces memory intensity per workload (already occurring)
		- Hyperscaler capex moderates from historically extreme levels (precedent: Microsoft pause)
	- All three are plausible simultaneously. The bull case requires all three to fail simultaneously and indefinitely.

	| Bull Assumption | Bear Rebuttal |
	|---|---|
	| token throughput = HBM × bandwidth is a permanent ceiling | Model efficiency and architectural innovation attack the denominator |
	| Supply can't respond fast enough | +30% capex YoY is exactly how prior oversupply cycles started |
	| Oligopoly means no price war | Samsung's historical behavior and CXMT's subsidized entry both undermine this |
	| Hyperscaler capex is committed demand | It is guidance; Microsoft already paused; extreme allocations historically revert |
	| Rising HBM perf ratio justifies more HBM | Rising ratio creates architectural incentive to reduce HBM dependency |
	| "This time is different" | This claim has appeared at the peak of every major memory cycle |
