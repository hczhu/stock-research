tags:: [[Anthropic]], [[Claude]], [[IPO]], [[S-1]], [[compute]], [[spot-compute]], [[GPU-pricing]], [[enterprise-AI]], [[agents]], [[cybersecurity]], [[OpenAI]], [[The Circuit]], [[Ben-Bajarin]], [[Jay-Goldberg]], [[podcast]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-10
file-updated-at:: 2026-11-10

- ## The Circuit on Anthropic's amended S-1: was the Q3 slowdown a lack of compute rather than of demand?
	- **Source**: *The Circuit* podcast, Ben Bajarin (Creative Strategies) and Jay Goldberg, recorded Friday Nov 6, 2026. User-provided auto-generated transcript.
		- Most of the Anthropic argument is Goldberg's. Bajarin adds the enterprise-security angle.
		- S-1 figures below are as the hosts recalled them on air. The disclosed figures are in the linked memos.
		- Related: [[2026-10-26-anthropic-s1-financials-compute-economics]], [[2026-10-17-anthropic-q3-revenue-ipo-valuation-compute-commitments]], [[2026-10-28-anthropic-s1-hacker-news-demand-product-moat-field-notes]], [[2026-11-04-expert-call-aws-bedrock-sales-motion-anthropic-economics]], [[2026-11-10-circuit-nov-6-semi-selloff-2028-capacity-amd-arm-qcom-sitime]] (the selloff and other topics from the same episode), [[2026-11-10-circuit-cloudflare-q3-customer-surge-agentic-enterprise]].
	- **Thesis (Goldberg)**: the market read Anthropic's Q3 slowdown as demand running out ("everybody has coded all the things they're going to code"). The S-1 points instead to Anthropic being **short of compute**. It throttled users and delayed signups, which held back growth. Goldberg ties the slowdown to a broader view that AI demand is fine: it is one data point in his case against the Nov 5 selloff.
		- Goldberg hedges: "I don't know that that's true, but … there are a lot of things in the S-1 that point in that direction."
- ## The numbers the hosts cited
	- | Item | As cited on the podcast | Note |
	  |---|---|---|
	  | Sequential revenue growth | From about **150%** (Q2) to about **40%** (Q3) | S-1 figures in the linked memos: about 144% in Q2 and about 45% in Q3 (\$16.8B Q3 revenue) |
	  | Outage | About a day in March–April 2026 when the service "just didn't work" | Goldberg says the S-1 attributes it to **running out of compute** |
	  | Q3 compute spend | **About \$10B** | |
	  | Contracted portion | **About \$5.5B** | |
	  | Spot purchases | **About \$4.5B** | Bought at short notice. Goldberg: "I can probably even pick out the day that that started if you look at the pricing data" |
	- **Market reaction**: the amended S-1 came out Monday, Nov 2. Goldberg thinks its "concerning numbers" may have helped set off the Nov 5 tech selloff, though he calls the selloff mostly sentiment.
	- **IPO price range** (user-provided, not from the podcast): \$70 to \$78 per share, which corresponds to a fully diluted valuation of about **\$1.26 trillion to \$1.41 trillion**.
		- *My note*: both ends imply about 18B fully diluted shares. Against Q3 revenue of \$16.8B annualized (about \$67B), the range is about 19–21× run-rate revenue.
- ## Goldberg's reading of the compute constraint
	- **Avoiding an outage before the IPO**: with strong usage, Anthropic "really, really, really [didn't] want to have an outage." Another failure months before listing would look terrible, so it paid up for spot compute.
	- **Spending nearly half on spot shows how tight compute is**: putting about 45% of a quarter's compute on expensive spot capacity is what a company does when it can't get enough contracted capacity. It isn't a sign of falling demand.
	- **Rationing slowed growth**: "they just couldn't serve everybody that they wanted to serve, and they had to throttle people and delay signups … that hurts their growth."
	- **Why this matters beyond Anthropic**: if the largest fast-growing lab is limited by supply rather than demand, AI compute demand is still outrunning capacity in late 2026. That runs against the "GPU glut" talk the hosts say they've started hearing about 2028.
- ## Enterprise security as the next bottleneck (Bajarin)
	- **Security has to come first**: Bajarin's CIO/CTO and CSO surveys (the CSO results publish this week) show that security is "the gate that has to be cleared first to agentic scale."
	- **Dedicated cyber models**: in June he wrote that Anthropic and OpenAI had an opening to build cybersecurity models. He says OpenAI launched a GPT-6 cyber model "yesterday" (around Nov 5). That pressures Anthropic to answer for enterprise security buyers.
	- **Enterprises are early**: the top ~20% of adopters are rebuilding processes, permissions, observability, data and governance for agents. The other ~80% will lag. Bajarin says enterprise spending "funds this cycle or it doesn't," so how fast these companies move sets how fast labs like Anthropic grow.
	- **Goldberg is more bullish**: "a surprising number of people have done a surprising amount of work." In company meetings this week he heard "a dozen times" about firms rushing to adopt AI for employee productivity.
- ## My notes
	- **Another explanation the podcast didn't mention**: [[2026-10-17-anthropic-q3-revenue-ipo-valuation-compute-commitments]] reports that distillation usage by rival labs was **5–7% of revenue** and that Anthropic cut it back "materially" in Q3. That would slow reported growth on its own, apart from compute or demand.
	- **The margin cost**: if about \$4.5B of Q3 compute was spot at premium prices, Q3 gross margin took a hit that should ease as contracted capacity arrives. Check the S-1's gross margin by quarter against this split.
	- **Testing the claim**: if Goldberg is right, growth should pick up again as contracted capacity comes online. Watch Q4 sequential growth against new compute coming online (Google TPU, AWS Trainium, Azure). If growth stays near 40% after supply loosens, the demand reading gains weight.
	- **Spot GPU prices**: \$4.5B of spot buying in one quarter is large enough to move spot prices. That fits Zuckerberg's remark that an H100 is worth more now than a year ago ([[2026-11-10-cheeky-pint-meta-muse-wonder-training-msl-anecdotes]]).
