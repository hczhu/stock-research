file-created-at:: 2026-04-13

- **Source**: `/Users/hc/Downloads/CLSA tour AI expert Apr 2026.pdf`
- **Document context**:
	- PDF creation date: `2026-04-13`
	- Language of source: Chinese
	- This memo is an English summary of notes labeled **AI Expert 1** and **AI Expert 2**
	- The views are expert opinions from industry practitioners, not audited company disclosures

- **Expert profiles**
	- **AI Expert 1**:
		- Background: former/ current data technology director at [[ByteDance]]
		- Experience: nearly `10 years` in large-model / algorithm work
		- Scope: model platform capability, AI education, AI commercialization, education ToB, and data-product monetization
	- **AI Expert 2**:
		- Background: product expert at Beijing Douyin Information Service / [[Volcano Engine]]
		- Experience: `5 years`
		- Joined ByteDance in `2023`
		- Prior roles included Baidu Cloud and NVIDIA internet presales engineering

- **Main arguments**
	- **Argument 1: China AI will bifurcate into two camps**
		- Expert 1 argues China will have two parallel tracks in `2026`:
			- large internet/platform companies that also operate cloud platforms and will push applications plus model services
			- model-first companies that win distribution directly through model capability, similar to North America about `3 years` ago
		- The view is that both groups will co-exist for the next `1-2 years` and shape the market together.
	- **Argument 2: Frontier model capability in China is converging, but still uneven by modality**
		- Expert 1 ranks **DeepSeek** and **Alibaba** as first tier among Chinese large-language-model providers.
		- **ByteDance** and **Zhipu** are second tier, with **Kimi** in a "tier `1.5`" position.
		- On the evaluation framework of native multimodality, end-to-end design, reasoning, and multimodal quality, **Gemini 3.0** is described as the strongest overall benchmark.
		- ByteDance is not viewed as first tier because **Seed 2.0** is said to be neither native nor end-to-end, and is weaker on MOE design efficiency, coding, math logic, and agentic capability versus top peers.
	- **Argument 3: Tencent is far behind where investor narratives often assume**
		- Expert 1 says Tencent has two near-term model milestones:
			- a roughly `10B`-parameter small model for QQ / WeChat use in April
			- a roughly `20B`-parameter model in `1H` for Tencent’s own social applications
		- Expert 2 argues Tencent’s constraint is not just model quality, but economics and infrastructure:
			- Tencent’s model investment has been too cautious
			- even if Tencent had `5x` or `10x` more current compute, it still would not be enough to support mass adoption across WeChat’s user base
			- a reference point given is that Alibaba’s compute prepared for Qwen was exhausted when usage reached roughly `30 million` DAU during Spring Festival
			- this is contrasted with WeChat’s everyday user base of `900 million` to `1 billion`
	- **Argument 4: 2026 is likely a bigger year for ToB agents than for consumer agents in China**
		- Expert 1 says China’s consumer-agent market is still small.
		- Before OpenClaw reached China, no consumer-agent app had DAU above `100,000`.
		- Even when OpenClaw was hottest in early March, domestic DAU was only about `7-8 million`, and at most about `10 million`.
		- ByteDance’s Doubao app has DAU above `100 million`, but only about `10%` of DAU call agents on ByteDance’s platform each day.
		- Most called agents are officially developed rather than third-party developed, which means the market has not yet become a mini-program-like ecosystem.
		- By contrast, Expert 1 argues ToB agent opportunity in `2026` is bigger, especially PaaS-like agents exposed through cloud services.
		- Expert 2 similarly says enterprise use cases such as coding, testing, data analysis, customer service, and business-quality control are the main near-term landing zones.
	- **Argument 5: China consumer AI monetization will lag North America**
		- Expert 1 expects all chatbots in China to remain free in `2025`, with monetization only starting from `2027`.
		- Expected chatbot paid conversion in China is below `3%`, lower than North America.
		- The model is:
			- North America: sell subscriptions first, then layer ads and e-commerce
			- China: maximize DAU first, monetize through ads and e-commerce, then sell a small amount of subscriptions later
	- **Argument 6: Inference, not training, is becoming the dominant bottleneck**
		- Expert 1 says more than `90%` of inference in `2025` still runs on NVIDIA.
		- Domestic relief from Huawei Ascend and Cambricon inference hardware may not materially help until `4Q25`, with broader market impact more likely in `1H26`.
		- Expert 2 says the domestic compute mix is shifting from North America’s **R&D:training:inference = `5:3:2`** toward China’s **`4:2:4`** in `2026`, meaning inference load is rising sharply.
		- The implication from both experts is that inference-chip demand remains tight even if model-training efficiency improves.
	- **Argument 7: ByteDance is the clearest hyperscaler-scale spender in China**
		- Expert 2 says ByteDance spent `RMB 87bn` on GPU servers in `2025`.
		- For `2026`, the estimate rises to `RMB 180bn-230bn`.
		- The expert argues training VRAM requirements are shrinking and the center of gravity is shifting toward inference for image, voice, and video generation.
		- Prior chips such as **A100**, **H200**, and **B200** can be repurposed into these inference-heavy workloads.
	- **Argument 8: Token growth in China is still exploding, but monetization is weak**
		- Expert 2 says ByteDance token consumption was roughly:
			- `5 trillion` at the start of `2025`
			- `50 trillion` by around October `2025` (the source text says “15 year 10 month,” which appears to be a typo; context suggests `2025-10`)
			- at least `500 trillion` by September-October `2026`
			- potentially `1,000 trillion` by end-`2026`
		- ByteDance external model revenue is estimated at:
			- `RMB 1bn` in `2025`
			- `RMB 10bn-15bn` in `2026`
		- The expert says a prior internal estimate of `10x` inference-token growth now looks conservative.
		- Even if inference becomes unit-economics positive first, full model-level UE breakeven may only arrive in `2H27` or `2028`.
		- The expert’s broader conclusion is that China MaaS remains a structurally weak business versus downstream applications.
	- **Argument 9: Token prices in China should keep falling unless inference scarcity dominates**
		- Expert 1 says there are two main price-decline forces and only one price-increase force.
		- Price decline:
			- DeepSeek’s next release is treated as a certainty event
			- DeepSeek `V3.2` pricing is currently `RMB 3` per `1 million` tokens
			- `V4` is expected to reach something like Opus `4.5` quality, at only `1/2` or `1/3` of that level’s price
			- Kimi / Zhipu-style companies run low-cost architectures based on DeepSeek and therefore also pressure pricing lower
		- Price increase:
			- only domestic inference compute tightness
		- Expert 2 adds that domestic model prices are only about `1/8` to `1/10` of overseas prices, and in some cases as low as `1/7`, which can pull overseas enterprise demand into Chinese models for latency-tolerant use cases.
	- **Argument 10: Domestic chips are improving, but are still meaningfully behind NVIDIA**
		- Expert 1 says Huawei Ascend needs about `30%-40%` higher all-in cost than an NV7200-equivalent setup and consumes more than `40%` extra power.
		- Switching large existing software stacks is slow:
			- ByteDance may have more than `3,000` kernel units to migrate in a chip switch
			- migration could take more than `1 year`
			- learning and debugging Huawei’s CANN ecosystem can take roughly `6-12 months`
		- Expert 2 says domestic chips lag NVIDIA by roughly `3 generations` in aggregate capability, though Huawei, Cambricon, and Kunlunxin can match parts of entry high-end performance.
		- The expert expects some Chinese vendor could ship an **H200-comparable** product in `2H26`.
		- Procurement policy matters:
			- the notes say buyers may need to pair NV `H200` purchases with domestic-chip purchases at about a `1:4` ratio
			- this is one reason Tencent is now buying Cambricon and Kunlunxin
	- **Argument 11: Custom ASICs are increasingly rational for large Chinese model players**
		- Expert 2 says top model players such as ByteDance, Zhipu, and MiniMax may lower costs through custom ASICs.
		- ByteDance has already been doing this for about `3 years`; JD is also working on it.
		- If the end-demand scenario is clear enough, self-developed chips can cost only about **half** of third-party procurement.
	- **Argument 12: Small labs can still win locally because organization quality matters as much as capex**
		- Expert 2 argues that compute, data, and team quality are intertwined.
		- Small labs like DeepSeek, Kimi, MiniMax, and Zhipu can sustain `3-6 months` of edge in vertical domains such as coding or information extraction because:
			- they decide faster
			- they focus resources narrowly
			- they avoid the internal politics of large firms
		- Data spending examples given:
			- ByteDance spent about `RMB 0.7bn` / `RMB 5bn` on data in `2024/2025`
			- expected to spend `RMB 20bn-30bn` in `2026`

- **Data-point table**

| Topic | Data point | Value | Context |
|---|---|---:|---|
| Chinese consumer chatbot monetization | Paid conversion rate | `<3%` | Expert 1 says China chatbot paid conversion is expected to remain below North America. |
| Tencent model launch cadence | Small model size | `~10B` parameters | Expected in April for QQ / WeChat usage. |
| Tencent model launch cadence | Larger model size | `~20B` parameters | Expected in `1H` for Tencent’s social apps. |
| OpenClaw China traction | Peak domestic DAU | `~7m-8m` | Expert 1 says China DAU reached only about `7-8 million` at the peak. |
| Consumer agent threshold before OpenClaw | DAU | `<100,000` | No consumer-agent app exceeded this before OpenClaw. |
| Doubao app scale | DAU | `>100m` | Expert 1 says Doubao app DAU exceeded `100 million`. |
| Doubao agent penetration | Daily users calling agents | `~10% of DAU` | Only about one in ten Doubao DAU use ByteDance agents daily. |
| Inference chip share | NVIDIA share of inference in 2025 | `>90%` | Expert 1 says over `90%` of inference in `2025` still uses NVIDIA chips. |
| Huawei/Cambricon relief timing | Earliest visible relief | `4Q25` | Domestic inference-chip relief may begin to show then. |
| Huawei/Cambricon relief timing | Larger-scale market impact | `1H26` | More meaningful easing expected next year. |
| Training-node economics | Cost of one Huawei 384 supernode | `>RMB 100m` | Expert 1 says a single supernode may cost over `RMB 100 million`. |
| Training-node economics | Nodes needed for large training | `~100` supernodes | Implies tens of billions of RMB of cluster spend. |
| Training cadence | Full large training runs supported | `2-3` | Expert 1 says the objective is to complete `2-3` training runs. |
| North America compute mix | R&D : training : inference | `5:3:2` | Expert 1 describes this as the current rough allocation in North America. |
| China compute mix | R&D : training : inference | `4:2:4` | Expert 1 expects China to shift to this in `2026`. |
| ByteDance GPU capex | 2025 | `RMB 87bn` | Expert 2 estimate. |
| ByteDance GPU capex | 2026 | `RMB 180bn-230bn` | Expert 2 estimate. |
| ByteDance token consumption | Start of 2025 | `5tn` | Expert 2 estimate. |
| ByteDance token consumption | Around Oct 2025 | `50tn` | Expert 2 estimate; source text likely contains a year typo. |
| ByteDance token consumption | Sep-Oct 2026 | `>=500tn` | Expert 2 estimate. |
| ByteDance token consumption | End 2026 | `up to 1,000tn` | Expert 2 estimate. |
| ByteDance external model revenue | 2025 | `RMB 1bn` | Expert 2 estimate. |
| ByteDance external model revenue | 2026 | `RMB 10bn-15bn` | Expert 2 estimate. |
| Jimeng subscription revenue | Monthly | `~RMB 150m` | Expert 2 says Jimeng already generates about `RMB 150 million` per month. |
| Industry inference revenue growth | 2026 | `>=10x` | Expert 2 says the market’s inference revenue should grow at least `10x` this year. |
| Industry inference revenue growth | Next 2-3 years | `10x-15x annually` | Expert 2 says the market could keep expanding at `10-15x` per year for the next few years. |
| Token pricing | DeepSeek V3.2 price | `RMB 3 / 1mn tokens` | Expert 1 cites current pricing. |
| Token pricing | Chinese vs overseas model price | `1/8 to 1/10` | Expert 2 says domestic token cost is only about one-eighth to one-tenth of overseas levels. |
| Token pricing | Some overseas enterprise demand flow | `~1/7 price level` | Expert 2 says some foreign firms use Chinese entities because domestic model pricing is about one-seventh of overseas pricing. |
| Huawei vs NVIDIA economics | Cost premium | `+30%-40%` | Huawei Ascend system cost vs NV7200-equivalent. |
| Huawei vs NVIDIA economics | Power premium | `>40%` | Huawei Ascend also uses over `40%` more power. |
| Kernel migration complexity | ByteDance kernel units | `>3,000` | Expert 1 says chip migration may involve over `3,000` kernel units. |
| Kernel migration time | Migration duration | `>1 year` | For large codebase / inference-stack migration. |
| Huawei software learning curve | CANN learning/debug time | `6-12 months` | Expert 1 estimate. |
| Tencent compute gap reference | Qwen DAU that exhausted Alibaba prep | `30m DAU` | Expert 2 says `30 million` DAU already exhausted Alibaba’s prepared compute during Spring Festival. |
| WeChat reference scale | DAU | `900m-1bn` | Expert 2 uses this to show Tencent’s infrastructure gap. |
| MiHoYo third-party compute rental | H100 count | `8,000` | Expert 2 says MiHoYo rented `8,000` H100s from Baidu for game-realism models. |
| Domestic chip roadmap | Lag vs NVIDIA | `~3 generations` | Expert 2 aggregate capability estimate. |
| Domestic chip roadmap | Potential H200-equivalent arrival | `2H26` | Expert 2 says one or more vendors may ship an H200-comparable chip then. |
| Procurement policy | NV H200 paired domestic purchase ratio | `1:4` | Notes say buyers may need to pair imported H200 with domestic-chip procurement. |
| Custom ASIC economics | Cost vs third-party procurement | `~50%` | Expert 2 says self-developed chips can cost about half of outsourced procurement. |
| ByteDance data procurement | 2024 / 2025 / 2026E | `RMB 0.7bn / 5bn / 20bn-30bn` | Expert 2 estimate for purchased data spending. |

- **Implications**
	- The combined expert view is bullish on:
		- Chinese inference demand
		- high-density inference chips
		- cloud / PaaS agent monetization
		- domestic chip policy support
	- It is less bullish on:
		- near-term China consumer-agent monetization
		- pure MaaS gross margins in China
		- Tencent’s near-term ability to scale model usage across its full social graph
	- For listed equities, the memo tilts positive on:
		- compute infrastructure suppliers
		- inference-heavy cloud platforms
		- stronger model companies with fast iteration and lower token prices
		- domestic chip vendors that benefit from policy-driven procurement

- **Caveats**
	- The source is an expert-call style note, so several figures are estimates or informal industry checks rather than audited company disclosures.
	- Some company comparisons are subjective rankings.
	- At least one date in the source text appears to be a typo around the `50tn` ByteDance token figure.
	- The memo translates and condenses the Chinese source into English, so wording precision may differ slightly from the original Chinese phrasing.
