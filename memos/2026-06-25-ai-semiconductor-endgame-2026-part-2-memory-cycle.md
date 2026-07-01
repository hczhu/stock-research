tags:: [[AI]], [[semiconductor]], [[HBM]], [[DRAM]], [[NAND]], [[SSD]], [[inference]], [[agents]], [[AI infrastructure]], [[CXMT]], [[YMTC]], [[super-cycle]]

- ## AI Semiconductor Endgame 2026 (Part 2): Can HBM / DRAM / SSD Escape Traditional Cycles?
	- **Source**: user-provided Chinese article text, "AI半导体终局推演2026(II)"
	- **Core questions**:
		- Can `HBM / DRAM / SSD` escape traditional memory cyclicality?
		- Will the GPU inference roadmap that depends on exponential `HBM size x HBM bandwidth` growth stop, and if so when?
		- How large is CXMT's capacity impact, and can it pull DRAM back into the traditional cycle trap?
	- **Core conclusion**:
		- HBM already satisfies most of the conditions for de-commoditization and may shift from traditional cyclicality to "growth cyclicality."
		- DRAM de-cyclicality has much less market consensus, but `agentic CPU` demand is turning server DRAM into a new structural exponential demand source.
		- NAND SSD demand is less rigid than HBM / DRAM, but it benefits from KV-cache offloading, AI video, agent sandboxes, and future HBF; this cycle also looks more like a super-cycle.
		- HBM, DRAM, and NAND are not three independent stories. They are different temperature layers of the same AI memory hierarchy.
- ## Framework: When Memory Can Escape Traditional Cycles
	- The article defines the main source of traditional memory cyclicality as long capacity-expansion cycles: supply cannot adjust quickly, so it easily mismatches demand cycles.
	- `Commodity` characteristics are not the root cause of cycles; they are an amplitude amplifier. Standardization, storability, and weak differentiation magnify price wars and prisoner-dilemma behavior.
	- There are three ways to partially escape traditional cyclicality. Satisfying one condition helps; satisfying two to three conditions can eliminate most of the traditional cycle pattern.
	  
	  | Condition | Mechanism | Effect on cyclicality |
	  |---|---|---|
	  | Customization | Products are not fully interchangeable, capacity cannot move freely, and customers need long-term agreements | Reduces inventory and price-war risk |
	  | Structural exponential demand | Demand curve is steep enough that supply persistently lags | Makes downturns shallower and shorter |
	  | Fast technology iteration | New generations rapidly obsolete older generations, reducing inventory value | Shifts competition from quantity to quality |
	- Under this framework, the article argues that HBM satisfies roughly two and a half conditions: half for customization, one for structural exponential demand, and one for rapid technology iteration.
- ## HBM: Why It Looks More Like Growth Cyclicality
	- **Customization counts as only half a condition**: HBM has NVIDIA co-design and package / base-die customization, but the DRAM dies remain highly JEDEC-standardized.
	- After Samsung's HBM3E failed NVIDIA qualification and its share reportedly fell from roughly `60%` to `20%`, that capacity was not stranded; it could be redirected to Google TPU, AMD, and other customers. This shows HBM capacity is still partly transferable.
	- HBM4 increases customization because the base die can integrate custom logic / cache, and a more complex design can place the HBM4E memory controller and custom die-to-die interface directly into the logic base die.
	- The article notes that OpenAI, NVIDIA, and AMD are all working on customized HBM, but the customization mainly refers to the base die. The DRAM layers above it remain standardized.
	  
	  | HBM de-cyclicality condition | Satisfied? | Article's assessment |
	  |---|---:|---|
	  | Customization / LTAs | Half | Package and base-die collaboration pushes customers toward long-term agreements, but standardized DRAM dies keep capacity partly transferable |
	  | Structural exponential demand | Yes | Token throughput requires HBM size and bandwidth to double by generation |
	  | Fast technology iteration | Yes | HBM is roughly a two-year generation cycle, much faster than traditional DDR |
	- **Structural demand comes from the token factory**. The article extends the Part I formula:
		- `token throughput = HBM size x HBM bandwidth`
	- HBM size per GPU is growing roughly `40%+` per year, a much steeper demand curve than DRAM supply can match.
	- The rough supply-side capability is `14%` wafer growth multiplied by `9%` density improvement, which struggles to catch up with HBM / AI inference demand.
	- Even if HBM prices rise `3-5x`, spending more on HBM can still produce better marginal token-throughput returns than spending elsewhere.
	- SRAM, HBF, CXL, and PIM currently cannot directly replace HBM in its main battlefield: `KV cache / attention`. The article argues that no major replacement path is likely for at least `5 years`, and possibly longer.
- ## HBM Technology Iteration: From Quantity Competition To Quality Competition
	- DDR3 to DDR5 took roughly `15 years`, while HBM is roughly a `2-year` generation cycle and appears to be accelerating.
	- The article's NVIDIA GPU / HBM bandwidth path shows that HBM speed is linearly related to inference token throughput, making older HBM economically unattractive quickly.
	  
	  | Dimension | DDR / traditional DRAM | HBM |
	  |---|---|---|
	  | Generation cadence | DDR3 to DDR5 took roughly `15 years` | Roughly `2 years` per generation |
	  | Performance value | Historically low marginal utility for CPU performance | Approximately linear value for token throughput |
	  | Older product value | Can be digested over a longer period | Older generations such as HBM3 depreciate quickly |
	  | Supplier competition | Capacity / share competition | NVIDIA qualification, stability, and bandwidth-speed competition |
	  
	  | NVIDIA GPU / HBM bandwidth path | Bandwidth |
	  |---|---:|
	  | Early node | `2TB/s` |
	  | Later node | `3.5TB/s` |
	  | Later node | `4.8TB/s` |
	  | Later node | `8TB/s` |
	  | Future node | `22TB/s` |
	- The article argues that in the token-factory era, more technology upgrade, especially HBM bandwidth, means more earning power. Customers therefore have strong incentives to use the newest HBM.
	- Faster depreciation of old product lowers the value of inventory hoarding. This pushes HBM suppliers away from pure quantity competition and toward next-generation qualification share, weakening the classic prisoner dilemma where no supplier wants to cut capacity first in a downturn.
- ## HBM Still Has Cycles, But They Look Like Growth Cycles
	- The article distinguishes two cycle types:
		- **Traditional cyclicality**: suppliers earn a lot in upcycles and lose a lot in downcycles.
		- **Growth cyclicality**: suppliers earn a lot in upcycles and earn less in downcycles.
	- HBM cannot fully avoid cycles because supply cycles and demand volatility still exist.
	- But as long as token demand remains exponential, HBM demand is more predictable; when price falls, customers have incentive to increase HBM size to improve token throughput.
	- Long-term agreements and partial customization can also convert traditional cyclicality into a longer, shallower growth cycle.
- ## Supply Side: Slower DRAM Density Scaling And HBM Wafer Drag
	- The article adds a fourth de-cyclicality factor for HBM / DRAM: supply-side expansion keeps getting harder.
	- DRAM bit-density growth has slowed sharply, ending the era when process migration alone could generate large bit-supply growth.
	  
	  | Period | Annual DRAM bit-density growth per wafer | Implication |
	  |---|---:|---|
	  | Around 2000 | `~45% / year` | Large bit-supply growth even without more wafers |
	  | Around ten years ago | `~20% / year` | Process scaling still drove high bit growth |
	  | Today | `~9% / year` | Expansion relies more on new fabs and clean rooms |
	- Higher HBM stack counts further consume DRAM wafers.
	  
	  | Product | DRAM wafers needed for equivalent bits | Supply implication |
	  |---|---:|---|
	  | HBM3E | `~3x` DDR wafers | HBM bits are harder to manufacture than DDR bits |
	  | HBM4 | `~4x` DDR wafers | HBM expansion keeps crowding out commodity DDR |
	- The article calls this the HBM "bit tax" on DDR: roughly `3-5%` of annual DDR bit growth is consumed by HBM conversion.
- ## Will The GPU / HBM Architecture Roadmap Stop?
	- The real question is not HBM itself, but whether Transformer attention and the KV-cache mechanism disappear.
	- The article argues that after AI architecture revolutions, the operations that survive are those with mathematical universality as primitive operations.
	- FFN / MLP layers survived from the 2012 deep-learning era into LLMs because they relate to the universal approximation theorem.
	- Attention solves another fundamental problem: dynamic routing between arbitrary positions in a sequence, allowing any two positions to connect on demand. Once this capability is proven useful, it is hard to fully discard.
	- Therefore, even if future architectures evolve from pure Transformers toward hybrid architectures or world models, attention layers likely remain, and KV cache or a latent-compressed equivalent remains necessary.
	- Conclusion: the GPU KV-cache architecture path that depends on exponential HBM growth is unlikely to stop soon. HBM remains one of the core inference resources.
- ## DRAM: A Low-Consensus Path To De-Cyclicality
	- The market has some consensus that HBM is de-cycling, but very little consensus that DRAM can do the same.
	- DRAM has little meaningful customization, so the key questions are structural exponential demand and higher marginal utility from technology iteration.
	- The article argues that something changed after late `2025`: agentic CPUs began to unlock demand, and CPU-attached DRAM became a new source of structural exponential demand.
	- DRAM demand growth has two layers:
		- CPU server TAM grows quickly.
		- DRAM per CPU core rises quickly because of agentic flow.
- ## Agentic CPU And Server DRAM Demand
	- The article gives four drivers for CPU server TAM growth:
		- In AI accelerator clusters, the CPU:GPU ratio is moving from the traditional `1:4` toward `1:2`, and possibly toward `1:1`.
		- CPU processing can account for `50-90%` of latency in agentic flow, making CPU a major bottleneck that must scale with accelerators.
		- AI coding increases SDE productivity, code volume, and software API calls, which converts directly into more CPU hours.
		- Sandboxes replicate databases and user context for data security and isolation. This wastes DRAM and CPU cores, and the waste may be difficult to optimize away for five years or longer.
		  
		  | Time / source | 2030 CPU TAM forecast | Article's read |
		  |---|---:|---|
		  | AMD earnings two quarters ago | `\$60B` | Old baseline |
		  | AMD / ARM two months ago | `\$120B` | Forecast doubled |
		  | NVIDIA one month ago | `\$200B` | Forecast revised higher again |
		  | Bernstein last week | `\$223B` | Continued upward revision |
		  | Author's view | `2031E \$400B` | Likely to be revised higher again |
	- DRAM per CPU core rises for two reasons:
		- Agents are stateful long-running processes, not stateless request-response jobs. A task can run from one minute to one hour, during which message history, system prompt, working memory, long-term memory, and tool-result buffers stay resident in DRAM.
		- Context windows are moving from `32K -> 256K -> 1M`, while reasoning / test-time compute expands sequence length. Resident messages per active session scale roughly with context length.
		  
		  | Variable | Old world / current | Agentic era |
		  |---|---:|---:|
		  | CPU server TAM | `\$60B` old forecast | `\$120B -> \$200B -> \$223B`; author thinks `\$400B` is possible |
		  | DRAM per core | `4-8GB/core` | `16-32GB/core` |
		  | Growth character | Traditional server growth | CPU TAM expansion x one-time DRAM/core reset |
	- The article estimates that even under a conservative 2030 case of `\$300B` CPU TAM, `\$50/core`, and `16GB/core`, incremental DRAM demand is at least `96EB`.
	- Supply comparison: total DRAM output is roughly `47EB` this year and barely `60EB` next year.
- ## DRAM Supply-Demand Gap And Bit Growth
	- The article estimates non-HBM traditional DRAM supply growth at roughly `20%` per year.
	- Demand from agentic CPU DRAM alone could rise from `16EB` to `80EB`, a roughly `50%` CAGR, far above estimated supply growth.
	  
	  | Item | 2026E / current | 2030E / future | Implied change |
	  |---|---:|---:|---:|
	  | CPU TAM assumption | `\$60B` | `\$400B` | `~6.7x` |
	  | DRAM/core assumption | `8GB/core` | `16GB/core` | `2x` |
	  | CPU price per core assumption | `\$30-35/core` | `\$80/core` | `>2x` |
	  | Agentic CPU DRAM demand | `16EB` | `80EB` | `~50% CAGR` |
	  | Traditional non-HBM DRAM supply growth | — | — | `~20% / year` |
	- DRAM is less rigid than HBM because it is not directly tied to GPU monetization efficiency. DRAM shortages mainly slow agent flow, and some low-value tasks can wait.
	- Still, the structural exponential demand is strong. On the SemiAnalysis framing, this year's DRAM shortage is single-digit percent, next year exceeds `10%`, and the article argues the shortage is unlikely to ease before 2030.
- ## DDR / LPDDR Technology Iteration Becomes More Useful
	- Historically, DDR technology iteration depended heavily on consumer electronics, and its performance utility was low. Customers often waited for price declines before adopting new generations.
	- In the future, carbon-based consumer-electronics DRAM demand may be far smaller than silicon-based CPU-server DRAM demand.
	- Rising memory needs in CPU servers and edge AI raise the marginal utility of DDR / LPDDR speed. This makes DDR6 / LPDDR6 more valuable than prior DDR transitions.
	- Apple is increasing LPDDR speed and capacity requirements to run local models. The latest full edge-AI feature set reportedly requires memory to rise from `8GB` to `12GB`.
	- The article argues that LPDDR6 / DDR6 iteration intervals are shortening and the speed slope is rising again. Customer behavior shifts from "wait for price declines" to "adopt as early as possible."
- ## CXMT Expansion: Meaningful, But Not Enough To Break This DRAM Shortage
	- CXMT is expanding quickly, but the article estimates its bit density is only about half of the Big 3, so effective capacity should be discounted by half.
	  
	  | Vendor / region | 2025E monthly capacity | 2028E monthly capacity | CAGR |
	  |---|---:|---:|---:|
	  | Samsung | `685K wspm` | `920K wspm` | `10.3%` |
	  | SK Hynix | `519K wspm` | `725K wspm` | `11.8%` |
	  | Micron | `340K wspm` | `560K wspm` | `18.1%` |
	  | Other non-China | `150K wspm` | `218K wspm` | `13.3%` |
	  | China, density-adjusted half | `117K wspm` | `274K wspm` | `32.8%` |
	  | Total including China | `1,811K wspm` | `2,697K wspm` | `14.2%` |
	  | Total excluding China | `1,694K wspm` | `2,423K wspm` | `12.7%` |
	  
	  | CXMT node | Monthly capacity / addition | Timing |
	  |---|---:|---|
	  | Existing / 2025 | `~200K wafers / month` | `2025` |
	  | Beijing fab and added lines | `320-350K wafers / month` | `2026` |
	  | Shanghai Phase 1 | `+100K wafers / month` | `2027` |
	  | Shanghai Phase 2 | `+100K wafers / month` | `2028` |
	  | Nominal target | `~500K wafers / month` | `2028` |
	  | Density-adjusted equivalent | `~250K wafers / month` | `2028` |
	- After density adjustment, CXMT increases industry DRAM bit capacity CAGR by roughly `+1.5pct` from end-2025 to end-2028, from `12.7%` to `14.2%`.
	- Even if CXMT keeps expanding, its 2030 impact on industry equivalent bit-volume CAGR may be less than `3pct`, for example moving `20%` CAGR to `23%` CAGR.
	- Lithography is also a constraint. DDR6 starts at `14400 MT/s` and requires higher density. The Big 3 are likely to use 1c or more advanced nodes, roughly below `12nm`, with broad EUV use. CXMT may be rate-limited and still only half as dense in DDR6.
- ## Why The DRAM Super-Cycle Could Last At Least Five Years
	- First, agentic CPU server DRAM demand grows much faster than supply bit growth.
	- Second, demand destroyed by DRAM price increases is not permanently destroyed; much of it is delayed, creating a large demand reservoir.
	- Third, HBM and DRAM capacity can convert between each other, so the whole DRAM complex can re-rate together.
	- Fourth, density scaling has slowed, expansion difficulty is rising, supplier capex plans remain cautious, and CXMT's impact is limited.
	  
	  | Demand reservoir | Mechanism | Release when memory prices fall |
	  |---|---|---|
	  | Memory-for-compute / speed | Extra memory can optimize speed and compute, but high prices suppress use | Designs similar to CPX prefill acceleration can return |
	  | Low-value tasks | High token costs push low-value tasks into delay queues | Lower memory prices bring delayed tasks back |
	  | Edge AI | AI PCs / phones need more memory for local models | AI PCs could move from `24GB` to `128GB`; Apple edge AI from `8GB` to `12GB` |
	  | Consumer electronics / Agent PCs / low-end phones | High prices reduce configurations or delay replacement | Lower prices trigger restocking / higher configurations |
	- CPX prefill acceleration was originally designed to use low-cost GDDR7 for a dedicated prefill accelerator, but LPDDR / GDDR became too expensive and weakened ROI. If ordinary memory prices fall, similar designs may return.
	- HBM long-term contract transparency protects profitability. If DRAM prices fall and margins decline, HBM can indirectly pull away more DRAM capacity.
	- HBM price declines also make GPU vendors more willing to upgrade HBM size, which indirectly supports the DRAM complex price floor.
	- The article's conclusion: for at least the next five years, and possibly longer, DRAM is unlikely to enter a traditional cyclical trough.
- ## NAND SSD: More Diffuse Structural Growth, But Still A Super-Cycle
	- NAND's structural growth drivers are weaker than DDR's. This year's shortage is mainly because major producers kept production discipline and did not expand aggressively; capacity additions mostly come from higher NAND layer counts.
	- The article identifies four structural demand sources.
	  
	  | NAND / SSD structural demand source | Mechanism | Timing / note |
	  |---|---|---|
	  | KV-cache offloading | Move warm / cold KV cache that spills out of HBM onto NAND SSD | It has not yet scaled materially, but SSD is already tighter than DRAM; Rubin CMX ramp should make this more visible |
	  | AI video | Seedance-like video-generation workloads grow quickly | Volume is growing `10-40x` per year, currently still constrained by compute shortages |
	  | Agent sandbox | Each task replicates databases and user context | Wastes CPU, DRAM, and SSD simultaneously, creating storage demand |
	  | HBF | Use flash to store model weights, write once, read mostly | Could matter more after 2030; must be packaged with GPU / HBM because PCIe is too slow |
	- SSD's key advantage is cost. The article says SSD could be around `\$0.8/GB` in 2027, roughly `1/40` the price of DRAM at the same time.
	- If DRAM / HBM rise alone while SSD does not, system architects will try to use SSD to carry some warm / cold memory functions at much lower cost.
	- Whether NAND truly escapes traditional cycles depends on production discipline. YMTC is the potential spoiler because NAND is easier to expand than DRAM; if one supplier expands aggressively, the prisoner dilemma can return.
	- The article argues that even if NAND does not fully de-cycle, this is still a super-cycle. Multiple structural demand drivers could delay the downturn to around `2030`.
- ## Investment Implications
	- **HBM**: strongest case. It satisfies two and a half de-cyclical conditions and directly ties to GPU token throughput, so customers may tolerate large price increases.
	- **DRAM**: lower consensus but potentially the biggest change. Agentic CPU moves server DRAM from traditional commodity demand toward structural growth, turning DRAM into a weaker version of growth cyclicality.
	- **NAND / SSD**: less rigid demand than HBM / DRAM, but it has the broadest application surface and the lowest cost, making it the low-temperature utility layer of the AI memory hierarchy.
	- **China supply shock**: CXMT's DRAM impact should be adjusted for bit density, and near-term additions do not offset agentic CPU demand plus HBM bit tax. YMTC's NAND production discipline matters more for NAND.
	- **Most important variables to track**:
		- Whether `HBM size x HBM bandwidth` continues doubling by generation.
		- Whether AMD / ARM / NVIDIA / sell-side forecasts keep raising agentic CPU TAM.
		- Whether `GB/core` migrates from `4-8GB` to `16-32GB`.
		- Whether HBM bit tax keeps consuming `3-5%` of commodity DDR bit growth.
		- Whether CXMT / YMTC break through equipment limits and change industry production discipline.
- ## Key Data Points To Retain
  | Category | Data point |
  |---|---|
  | HBM customization | Samsung HBM3E NVIDIA share reportedly fell from roughly `60%` to `20%`, but capacity could redirect to Google TPU / AMD |
  | HBM demand | HBM size per GPU grows `40%+` per year |
  | DRAM supply | Wafer growth roughly `14%`; density uplift roughly `9%` |
  | DRAM density | Around 2000: `45% / year`; around ten years ago: `20% / year`; today: `9% / year` |
  | HBM wafer tax | HBM3E needs roughly `3x` DDR wafers; HBM4 roughly `4x` |
  | DDR bit tax | HBM consumes roughly `3-5%` of annual DDR bit growth |
  | Non-HBM DRAM growth | Traditional commodity DDR bit growth roughly `20% / year` |
  | CPU latency bottleneck | CPU accounts for `50-90%` of latency in agentic flow |
  | CPU TAM | `\$60B -> \$120B -> \$200B -> \$223B`; author thinks 2031 can reach `\$400B` |
  | DRAM/core | `4-8GB/core -> 16-32GB/core` |
  | DRAM total production | Roughly `47EB` this year; roughly `60EB` next year |
  | Conservative agent CPU DRAM addition | At `\$300B` CPU TAM, `\$50/core`, `16GB/core`, incremental demand is at least `96EB` |
  | Agentic CPU DRAM demand | `16EB` to `80EB`, roughly `50% CAGR` |
  | CXMT impact | Density-adjusted China capacity raises industry capacity CAGR from `12.7%` to `14.2%` |
  | DDR6 hurdle | Starts at `14400 MT/s`; Big 3 likely use 1c or more advanced EUV nodes |
  | AI PC memory | Could move from `24GB` to `128GB` |
  | Apple edge AI | Full edge-AI features require memory moving from `8GB` to `12GB` |
  | Seedance growth | AI video volume growing `10-40x` per year |
  | SSD cost | Around `\$0.8/GB` in 2027, roughly `1/40` of DRAM |
- ## Caveats
	- This is a thesis-driven article, not an audited industry report; many data points come from the author's framework and industry judgment.
	- Several calculations depend heavily on CPU TAM, price per core, GB/core, and the eventual shape of agentic workloads.
	- HBM / DRAM de-cyclicality does not mean no cycles; it means the cycle may shift from loss-making troughs to earnings volatility.
	- NAND is the most dependent on production discipline, especially whether YMTC expands aggressively.