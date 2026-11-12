tags:: [[The Circuit]], [[Ben-Bajarin]], [[Jay-Goldberg]], [[semiconductors]], [[SOX]], [[market-sentiment]], [[AI-capex]], [[supply-chain]], [[enterprise-AI]], [[agents]], [[$AMD]], [[$INTC]], [[$ARM]], [[$QCOM]], [[$SITM]], [[$AAPL]], [[$TSM]], [[$NVDA]], [[Renesas]], [[MEMS-timing]], [[iPhone-Duo]], [[podcast]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-10

- ## The Circuit, Nov 6, 2026: the semis selloff, 2028 capacity, "capacity wins" earnings, and SiTime
	- **Source**: *The Circuit*, Ben Bajarin and Jay Goldberg, recorded November 6 and published November 9, 2026. User-provided transcript, with company disclosures linked where checked. [Episode](https://podcasts.apple.com/br/podcast/the-semi-apocalypse-market-panic-enterprise-ai-and/id1661329711?i=1000800837887&l=en-GB)
		- **Transcript review, November 12**: the newly supplied transcript covers this same episode. This memo is extended rather than duplicated; the Anthropic and Cloudflare links below preserve the more detailed company-specific extractions. Spoken estimates, forecasts, and first-hand observations are distinct from the linked company disclosures.
		- The Anthropic and Cloudflare parts of the episode have their own memos: [[2026-11-10-circuit-anthropic-s1-q3-slowdown-compute-constraint]] and [[2026-11-10-circuit-cloudflare-q3-customer-surge-agentic-enterprise]].
		- Related: [[2026-09-05-circuit-broadcom-custom-asic-unmodelable-2027-peak-constraint]] (Bajarin's "2027 is peak constraint" report), [[2026-10-05-the-circuit-memory-cycle-balance-sheet-tokenomics]], [[2026-11-03-stratechery-apple-memory-purchase-commitments-consumer-memory-market]], [[2026-11-02-trendforce-ai-infrastructure-component-lead-times]].
	- **Thesis**: The hosts saw little evidence in that week's earnings of an immediate demand break. Securing components helps chipmakers ship in 2027, while a step-up in capacity could shift the constraint to paid demand and utilization in 2028. Both conditions can occur in the same investment cycle.
- ## The Nov 5 selloff
	- **What happened**: the hosts described a broad November 5 selloff in semiconductors and tech, two days after the US election, with several names down double digits.
	- **Explanations the hosts discussed**:
		- **Data center moratorium fears after the election**: Goldberg says "I really, really, really don't think we're going to ban data centers in the US." Compare [[2026-11-07-stratechery-ai-on-the-ballot-political-compute-constraint]].
		- **Anthropic's amended S-1**, released Monday, showing slower growth.
		- **Animal spirits**: "the market gets spooked and it became self-reinforcing."
		- **AI-designed levered trades (Goldberg)**: he speculates that some funds use AI to design leveraged strategies that can amplify moves in both directions. The episode gives no positioning or flow data to quantify this.
		- **Bot-speed reactions (Bajarin)**: AMD stock was up about 7% "literally the second earnings dropped. … humans can't do that."
		- **Adding 2028 to models (Goldberg)**: "this is the time of year when we start adding years to our models." Analysts putting real 2028 assumptions in for the first time are getting nervous.
	- **Evidence against the selloff**: hyperscalers "all either affirmed or raised their capex numbers for next year." Goldberg says the companies he talks to "all have very healthy order books."
- ## 2028: when capacity arrives
	- **Everything lands at once**: "a whole bunch of fabs come online, memory fabs … a whole bunch of data centers coming online. … It's also the year when it looks like a lot of the energy bottlenecks will get resolved."
	- **GPU-glut talk has started**: "for the first time … the last 30 days, I've had a lot of people come to me talking about gluts of GPUs." Goldberg says "I don't think we're there yet."
	- **Bajarin's framework**: 2027 is "peak constraint." In 2028 the supply of memory, accelerators and CPUs rises in a step, so the question becomes whether demand is enough to fill it.
	- **A "digestion year"** was built into some sell-side models and then went back and forth.
	- **Enterprise demand is what decides 2028**:
		- Bajarin: enterprise "either funds this cycle or it doesn't."
		- At a big OEM event this week, every enterprise decision-maker said "we're early." Security, data, storage, governance and processes all need rebuilding for agents.
		- Bajarin characterizes the leading ~20% as rebuilding now and the remaining ~80% as slower followers. The transcript provides no sample, definition, or method for this split; treat it as his adoption framework, not a measured market penetration statistic.
		- Goldberg is more bullish on the pace of adoption, citing conversations with companies rushing to adopt AI for productivity. Bajarin's survey and conversations suggest security, permissions, observability, and getting unstructured data into usable form are prerequisites for broader production deployment.
	- | Evidence cited in the episode | What it supports | What remains open |
	  |---|---|---|
	  | Anthropic's slower sequential growth and Goldberg's estimate of **\$4.5B** of Q3 spot compute | A plausible supply constraint at a fast-growing lab. Goldberg infers that throttling and delayed sign-ups could have held revenue back | The spot split is the host's estimate. Revenue could slow for multiple reasons. See [[2026-11-10-circuit-anthropic-s1-q3-slowdown-compute-constraint]] |
	  | Cloudflare added **over 158K paying customers** in Q3, after **over 80K** in Q2 | A larger developer funnel. Management also reported **308 additions above \$100K annualized revenue** and **122% dollar-based net retention**, stronger measures of large-account traction | The paying-customer count includes small developer accounts. Cloudflare gave no AI or agent share of Workers growth. See [[NET-2026-Q3]] and the [company release](https://www.cloudflare.net/news/news-details/2026/Cloudflare-Announces-Third-Quarter-2026-Financial-Results/default.aspx) |
	- **The timing question for 2028**. If supply comes online faster than paid workloads, rental rates and utilization can fall even as AI use grows. If enterprise agents move from pilots to recurring production workloads as new capacity arrives, stronger utilization can absorb the supply increase. If power or buildouts slip, tight supply can persist even with plenty of chips on order.
- ## Enterprise conversations: urgency is clearer than deployment readiness
	- | First-hand evidence or host claim | What the transcript actually establishes |
	  |---|---|
	  | Bajarin attended an event hosted by a large infrastructure/services OEM | Decision-makers described unresolved security, storage, governance, and business-process work. The host does not identify a representative sample or quantify deployment budgets. |
	  | Goldberg heard the productivity-driven adoption argument about a dozen times that week | Companies he spoke with expressed urgency; this is qualitative demand evidence, not a count of signed contracts or production deployments. |
	  | Bajarin cites CIO/CTO and security-officer surveys | He says security must be cleared before agents scale; the transcript does not supply questionnaire design, sample size, or numerical survey results. |
	  | Roughly 80% of enterprise data created at the edge is unstructured, according to Bajarin | No underlying study or denominator is supplied. He reports some leading companies using agents to structure and index data; that workflow example is more useful than treating the percentage as verified. |
	- **The hosts disagree on timing, not the need for preparation**: Goldberg believes substantial work has already happened and adoption may accelerate sooner; Bajarin worries the longer tail moves slowly even when competitive pressure is strong. Neither supplies a dated enterprise-spending forecast.
	- **Interpretation**: data preparation, identity, permission enforcement, and observability can receive spending before broad autonomous production. Converting previously unused data into governed context can also create incremental storage, processing, and inference workloads, not merely substitute AI for existing employee tasks.
	- **Do not equate urgency with utilization**: pilots and remediation projects can coexist with delayed deployment. The hosts' enterprise-demand argument is a plausible way to absorb future infrastructure, not evidence that 2028 capacity is already economically covered.
- ## Earnings: capacity decides who wins
	- **AMD**:
		- **Results**: AMD reported **\$13.38B in Q3 revenue (+45% YoY)**, including **\$8.55B from Data Center (+97%)**, driven by EPYC and the MI450 Series launch. Data Center was about **64% of company revenue**. [AMD Q3 results](https://ir.amd.com/financial-information/sec-filings/content/0000002488-26-000188/q32026991.htm)
		- **Growth outlook**: Bajarin read the call as moving the 2027 Data Center growth outlook from about 70% to **about 80%** and saw a scenario where **total 2027 revenue reaches about \$100B**. The revenue scenario is his estimate.
		- **GPUs**: AMD named Anthropic, Meta, Microsoft, OpenAI, and OCI as running workloads on early Helios racks using MI450 Series GPUs. Goldberg sees the MI455 as competitive with NVIDIA Rubin on paper. The investment comparison depends on realized throughput, software, and deployments at scale. [AMD Q3 results](https://ir.amd.com/financial-information/sec-filings/content/0000002488-26-000188/q32026991.htm)
		- **Supply**: Lisa Su went out of her way to say AMD has secured the capacity, substrates and memory to hit its numbers. Bajarin suspects TSMC moved wafers from an unnamed competitor to AMD, a possible source of upside.
		- **Servers vs Intel**: Bajarin thinks AMD could ship more server CPUs than Intel in 2027. AMD's disclosed Data Center segment includes CPUs and GPUs, so a comparison of segment sales cannot establish CPU unit share.
		- **Positioning**: AMD now calls itself "a data center company," not a client computing company.
	- **Intel**: the counterexample. It didn't lock in supply, "and that became a problem to their upside."
	- **Apple**: made **about \$33B of purchase commitments in the quarter**. "Even they finally signed."
	- **Arm**:
		- Arm is entering the chip business. All year the CEO and CFO said securing supply took most of their time.
		- Goldberg heard greater confidence on securing supply. Arm disclosed orders from multiple AGI CPU customers extending through calendar 2027, with first commercial deliveries planned for fiscal Q4 2027. Chip shipments would add a revenue stream alongside licenses and royalties. [Arm shareholder letter](https://investors.arm.com/static-files/0b5baa2e-fc47-4d05-b724-e49de7bd4356)
	- **Qualcomm**: "a little bit more tepid."
		- Fiscal Q4 QCT handset revenue was **\$5.14B (−26% YoY)** and automotive revenue was **\$1.99B (+89%)**. Handsets still made up about 57% of quarterly QCT revenue. The hosts heard increasing interest in Qualcomm's data center products. [Qualcomm FY2026 Q4 results](https://investor.qualcomm.com/files/content_files/FY2026-4th-Quarter-Earnings-Release.pdf)
		- It published technical data on its **high bandwidth compute (HBC)** product, which Goldberg finds promising and Bajarin calls a possible "real advantage."
		- Bajarin discusses a possible shift toward non-handset revenue. The transcript is ambiguous about the denominator and period of the 60% figure.
	- **Arm's mix will flip**: Bajarin says once Arm recognizes revenue from its own data center CPUs, data center becomes most of its revenue "almost immediately," because chip sales bring in far more than licensing.
	- **Next topic, operations**: who could have planned supply better, and who has the best operations, will be argued over the next quarter or two. Substrates in particular "you either got … in advance or you didn't."
- ## SiTime: timing chips going from analog to digital
	- **Bajarin's framing**: every analog-to-digital shift (TV, autos, phones) made the market much bigger. In timing, the shift is from quartz crystals to programmable **MEMS** (silicon micro-machined) oscillators.
	- **Acquisition and underlying growth**. SiTime closed the Renesas timing acquisition on July 1. In Q3, it reported **\$298.7M in revenue (+257% YoY)**, of which the acquired business contributed **\$86.3M**. Subtracting that contribution leaves about **\$212.4M**, up about **154% YoY** on a simple comparison with the prior-year quarter. Management separately said its core communications, enterprise, and data center business grew **202% YoY**. The acquisition adds quartz-based products and clocking IP. The hosts argue SiTime has a strong market position, but the episode gives no market-share denominator. [SiTime Q3 release](https://investor.sitime.com/news/news-details/2026/SiTime-Reports-Third-Quarter-2026-Financial-Results-11-4-2026/default.aspx), [10-Q, Note 2](https://investor.sitime.com/static-files/2038d70b-1ae9-4f67-9b82-9e585199c2fd)
	- **Why AI raises timing content**:
		- Denser compute means racks, scale-up pods and networking have to stay synchronized so no part becomes a bottleneck.
		- Higher-frequency parts on SiTime's roadmap carry higher prices and more timing per system.
		- Retimers sit next to Broadcom switches for the same reason: rack-to-rack and in-rack (north-south, east-west) synchronization depends on good timing.
	- **Units and prices (Goldberg)**:
		- About 10–20 timing devices per server board, maybe about 100 per server, and about 10–20 per phone.
		- Most cost cents ("10 cents, 50 cents") up to a dollar or two, but SiTime's pricing on the call was "more than you think." Quartz stays at the very high end (satellites, about \$1,000 parts).
		- **Estimation limit**: Goldberg revises his counts and pricing while speaking. These are illustrative recollections, not a validated bill of materials, SiTime blended ASP, or proof that quartz is confined to expensive applications. Do not build a timing TAM by multiplying these guesses together.
	- **The design trade-off**: the hosts emphasize programmability and flexibility. Clock accuracy and stability depend on the specific part and application. More clock domains, links, and higher-spec parts can raise timing content per rack even if rack shipments grow more slowly.
	- **Valuation**: Bajarin acknowledges investor pushback on price but says it is growing fast into a large, critical market. Goldberg declines to comment on valuation. Bajarin's new report sizes the market from his accelerator and networking models.
- ## Opening anecdote: Apple polishing cloths
	- **A shortage of Apple's polishing cloth** (Bajarin jokes it's Apple's "newest billion dollar business"). His team member Max ordered extras because of it, and he heard prices went up.
	- **Why**: Bajarin is now a full-time **iPhone Duo** user. He was skeptical of the passport-style foldable but says "there's no going back." The mixed reviews undersell it.
		- He also has the new **touchscreen MacBook Pro**.
		- Only Apple's dense microfiber cloth cleans the nano-texture screens. Other microfiber cloths, water and a T-shirt all failed.
		- His tongue-in-cheek theory: Apple gives you big screens to touch that only its cloths can clean.
	- **The supplier**: Goldberg's quick Claude search suggests Toray's Ultrasuede-type microfiber, which he says is milled in China. *My note: Alcantara is a separate Italian brand partly owned by Toray. The supplier is unconfirmed.*
	- **Firsthand product signal**: Bajarin became a regular foldable user after initial skepticism about the form factor. His experience is evidence about product appeal for one user.
- ## My notes
	- **Capacity is the theme to track in Q4 reports**: companies that say they have secured substrates, memory and wafers for 2027 (AMD, Arm, Apple's \$33B in commitments) against those that hedge. TrendForce lead times ([[2026-11-02-trendforce-ai-infrastructure-component-lead-times]]) are the external check.
	- **Compare available capacity with paid utilization**. Near-term lab shortages say little about the amount of demand in 2028. Energized capacity, utilization by accelerator generation, rental rates, and paid inference growth offer different evidence about whether additional supply is being absorbed.
