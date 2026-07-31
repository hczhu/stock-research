- tags:: [[compute]], [[GPU]], [[inference]], [[Anthropic]], [[AI-capex]], [[unit-economics]], [[Epoch-AI]], [[SemiAnalysis]], [[Dwarkesh]], [[semiconductor]]

- ## Dwarkesh Patel: why compute might get 10x+ more expensive
	- **Source**: Dwarkesh Patel, "Why compute might get 10x+ more expensive in coming years," July 29, 2026. The author states it is a **deliberately time-boxed 2-hour post** and that he cannot nail down important sub-questions — treat the estimates as reasoned conjecture, not research output. One margin figure is self-labeled a "total vibe claim."
	- **Thesis**: Lab revenue is growing ~10x/year while compute capacity grows only ~3x/year. That gap has to be absorbed by some combination of margins, compute prices, and inference mix — and since margins cannot plausibly reach the mid-90s and labs *don't want* to shift more compute to inference, the residual lands on **price**. The provocative anchor: if a human-level software engineer ran on one H100-equivalent, that H100 should rent for **>\$250k/year — roughly 15x today's spot price**.

- ## The accounting identity behind the argument
	- Premise: Anthropic revenue has 10x'd YoY and likely exits this year at **~\$100–150B**; extending the trend implies **~\$1T by end of next year**. The author is explicit that there is "no deep reason why the trend needs to continue."
	- Meanwhile lab compute **3x's per year** (per Epoch). To 10x revenue on 3x compute, one of three things must give:
		- | Lever | Status per the author | Can it carry the gap alone? |
		  |-----------------------------|------------------------------------------------------------|------------------------------------------------|
		  | Margins increase | Anthropic ~40% (2025) → **>80%** this year on Fable inference | No — would require **mid-90s%** by end of next year |
		  | Compute price increases | Spot **+40%** off the February trough | Yes — this is the residual the argument lands on |
		  | Higher inference share of compute | OpenAI ~**25%** of 2024 compute spend → "closer to 50% if not higher" now | Labs actively resist this |
	- **Why labs resist the inference shift** — the sharpest strategic observation in the piece: "the point of inference revenue is to convince investors to give you more money to buy more compute to train bigger models." Spending most compute on inference is tantamount to **declaring AI progress has stalled**, because it says further training isn't worth it and the business is really a cloud provider. Labs believe they are serving models that "will look extremely shitty within a year" precisely to fund the next training run.
	- Margin ceiling logic: in a market, margins are set by how much better you are than the next best alternative — so margins can only carry the gap if the top one or two labs stay far ahead of everyone else.

- ## Evidence the price effect has already begun
	- **Google/SpaceX rental**: reportedly **\$900M per month for 110K GPUs** (a GB200/GB300 blend) — approximately **2x the spot price per hour** for those GPUs. And spot is already 40% above February.
	- The relevant price is not spot. Labs "obviously can't rely on spot instances" — they need weight and customer-data security, plus enough scale for good utilization and flexibility. That **tranche of compute prices well above the headline spot rate**, so published spot figures understate what labs actually pay.
	- This is the most monitorable claim in the post: the **premium of contracted/secure lab-grade compute over spot** is a trackable spread, and the SpaceX deal puts an early marker at ~2x.

- ## The headline calculation and its economic defense
	- If a true human-level software engineer runs on one H100-equivalent, then at current market rates for software engineers that H100 should rent for **>\$250k/year**, i.e. **~15x today's spot**, implying roughly **\$20 per H100-hour**.
	- Core mechanism: **as models get smarter, they monetize the same compute better.** Compute price should track the value of the labor it replaces, not the cost of the silicon.
	- **The obvious objection, and the author's rebuttal**: wouldn't 10 million extra software engineers crush the marginal value of one? He argues that applying that logic to people would be the **lump of labour fallacy** — economists generally hold that high-skilled immigration doesn't depress long-run wages because specialization and innovation raise the value of labor. If standard labor economics holds, marginal value of labor (and thus compute price) stays "astonishingly high."
	- He hedges honestly: "maybe this labor supply shock is so big and so fast that this general heuristic no longer applies."

- ## Where the 3x annual compute growth comes from — and where it breaks
	- | Component | Contribution | Constraint |
	  |----------------------------------------|--------------|--------------------------------------------------------|
	  | Moore's Law | 1.4x | Steady |
	  | New fab construction | 1.2x | **EUV tool supply bottlenecked through at least 2030** |
	  | AI taking leading-edge wafer allocation | 1.8x | **Hits a wall by end of 2027** |
	  | Compound | **~3.0x** | |
	- The wafer-allocation lever is the one with a dated expiry: AI goes from **60% of N3 to 86%** by end of 2027, after which the 1.8x factor saturates. The author sees little room to push any of the three inputs harder.
	- This is the crux of the whole argument: supply growth is mechanically capped near 3x while demand-side value per unit compounds faster.

- ## Predicted consequences
	- **Catch-up becomes structurally harder.** If software engineering is automated by 2028 and compute is 15x more expensive, a competitor with no revenue simply cannot bid against frontier labs for compute. Compute price becomes a moat, not just a cost.
	- **Premium models command far higher margins — the Alchian–Allen effect.** When a large fixed cost is added to two goods of differing quality, the premium good becomes relatively cheaper and demand shifts toward it. At **\$20 per H100-hour**, using a weaker, less efficient model is "extremely costly and stupid" because it burns more tokens on expensive compute to reach the same result. Having paid for the compute, you may as well pay extra for the model that economizes it best.
		- Investment read: this argues **against** commoditization of frontier models. Rising compute prices would widen, not compress, the price umbrella for the most token-efficient model — a direct counter to the "models are becoming a commodity" thesis.
	- **Low-value AI applications get priced out.** AI is currently cheap relative to human labor partly because it can't do what top humans can. Once it can, "using GPUs to make short-form video slop will just get priced out."
	- **Strong economies of scale in the model business.** 10x revenue on 3x compute implies large scale economies: training pays a one-time cost to learn skills that amortize across all users, unlike human labor where "each instance has to be retrained from scratch." The author adds he wishes this weren't so, citing concern about **power concentration**.
	- **The eventual reversal**: at some point robots turn "shores of silica sand and mines of copper into computers," and compute prices fall toward raw input and tooling cost. The thesis is explicitly scoped to the current regime where compute only 3x's annually.

- ## The author's own counter-argument
	- He flags that this prediction pattern-matches to historically wrong scarcity calls, naming the **Simon–Ehrlich wager** — Ehrlich lost betting a commodity basket would rise in price through 1990, underestimating how market signals and ingenuity economize scarce inputs.
	- His rebuttal: commodities are the wrong reference class, because **compute supply is far less elastic** and less able to absorb large demand shocks or be met by substitutes than metals extraction is.
	- He also concedes the analysis cuts both ways on Simon–Ehrlich: in a different decade, Ehrlich would have won the bet.
