- tags:: [[$GOOGL]], [[Google]], [[Gemini]], [[DeepMind]], [[GCP]], [[TPU]], [[Anthropic]], [[SemiAnalysis]], [[AI-capex]], [[compute]], [[inference]]

- ## SemiAnalysis: "Gemini is Cooked but GCP is Cooking"
	- **Source**: SemiAnalysis, August 6, 2026 — Max Kan, Joey Brookhart, Doug O'Laughlin, Dylan Patel. Paid post. Revenue and compute-share figures are **SemiAnalysis Tokenomics/Accelerator Model estimates, not disclosed Google figures**; the model-quality judgments are opinion, stated bluntly.
	- **Companion**: [[GOOG-2026-Q2]] — Google's own Q2 call. **Two of that file's disclosures directly contradict this piece** (allocation priority and token-growth framing); see the tension section below.
	- **Thesis**: The August 5 DeepMind leadership overhaul is read as Google conceding the frontier race, with Thomas Kurian winning the internal compute-allocation fight. The investable consequence is a **transfer of value from first-party model economics (~\$12B Gemini ARR) to third-party compute and TPU system sales (~\$200B external by end-2027)** — near-term EPS accretive, but converting Google into what the authors call "a glorified neocloud."

- ## The trigger: DeepMind leadership overhaul (Aug 5, 2026)
	- | Person | Prior role | Change |
	  |----------------------|--------------------------------------|------------------------------------------|
	  | Demis Hassabis | DeepMind co-founder, CEO | **No longer in day-to-day operations** |
	  | Jeff Dean | Google Chief Scientist, Gemini co-lead | Leaving to found neolab **Discovery Loop** |
	  | Sanjay Ghemawat | Senior Google Fellow | Joining Discovery Loop |
	  | Quoc Le | Google Fellow | Joining Discovery Loop |
	  | Oriol Vinyals | **Gemini co-lead** | Joining Discovery Loop |
	  | Koray Kavukcuoglu | DeepMind CTO, remaining Gemini co-lead | **Replaces Demis** leading DeepMind/Gemini |
	- Jeff Dean co-founded Google Brain and **started the TPU program** — the piece's framing is that the person who built Google's silicon advantage is leaving as Google monetizes it.
	- The neolab playbook is now templated: leave Google, raise billions from outside investors **and Google Ventures**, then **spend it on NVIDIA GPUs in GCP**. Google funds and hosts the talent it loses.
	- SemiAnalysis's call: **"DeepMind is no longer a frontier lab"** — told to Tokenomics clients months earlier on RL-team departures and poor compute allocation. Odds of reaching SOTA again "have dropped to zero."

- ## Model position: the claimed decline
	- Sequence per the July 9 institutional note plus updates: Gemini 3 Pro (Nov 2025) was arguably the world's best model and forced Sam Altman's "code red" → **Gemini 3.5 Flash "a total flop"** → **Gemini 3.5 Pro silently cancelled**, with Google now hyping Gemini 4 → **Gemini 3.6 Flash** shipped as a bridge model.
	- **Artificial Analysis Intelligence Index (v4.1, 9 evals)** — the ranking that anchors the "8th or 9th place" claim:
		- | Model | Score |
		  |--------------------------|-------|
		  | Claude Opus 5 (high) | **61** |
		  | Claude Fable 5 (reasoning) | 60 |
		  | GPT-5.6 Sol (high) | 59 |
		  | Kimi K3 (max) | 57 |
		  | **Gemini 3 Max** | **56** |
		  | GPT-5.6 Fermi (high) | 55 |
		  | Muse Spark 1.2 (high) | 54 |
		  | Grok 4.5 (high) | 54 |
		  | Claude Sonnet 5 (high) | 53 |
		  | GPT-5.6 Lino (high) | 51 |
		  | GLM-5.2 (max) | 51 |
		  | **Gemini 3.6 Flash** | **50** |
		- Note the composition: Google's best entry sits **below two Anthropic models, one OpenAI model, and a Chinese open-weight model (Kimi K3)**. The bridge model ranks last of the twelve shown.
	- Talent: **Noam Shazeer and John Jumper** among departures; "most of the best RL people at Gemini recently left."
	- Competitive forecast: **both MSL and SpaceXAI expected to surpass Gemini on model quality by end of 2026**. OpenAI has "overcome their pre-training issues," with a much larger model codenamed **"Doug"** in the works.

- ## The Gemini API deceleration — same numbers, opposite framing
	- | Quarter | Tokens/min | QoQ growth |
	  |---------|------------|------------|
	  | 4Q25 | 10B | — |
	  | 1Q26 | 16B | **+60%** |
	  | 2Q26 | 22B | **+38%** |
	- **This is the single most useful cross-check in the piece.** [[GOOG-2026-Q2]] presents the *same* 10B→16B→22B series as momentum ("a ~2.2× jump in ~6 months," explicitly supply-constrained). SemiAnalysis presents it as deceleration (60% → 38% QoQ) with a corresponding decline in Gemini 1P API revenue growth. **Both readings are arithmetically correct** — which is precisely why the metric needs to be tracked as a growth *rate*, not a level.
	- Gemini 1P API revenue (chart read, approximate): rising to **~\$2.2B in 2Q26**, but QoQ growth decelerating from a ~175% peak around 2Q25 to roughly **45%** by 2Q26.
	- Offsetting: **Gemini Enterprise Agent Platform (formerly Vertex) is meaningfully stronger overall — thanks to third-party models like Claude.** Google's enterprise AI platform is being carried by a competitor's model, which is the whole thesis in miniature.

- ## The financialization math
	- | Line | Figure | Basis |
	  |-------------------------------|-----------------|--------------------------------|
	  | Gemini ARR, 2Q26 | **~\$12B** | First-party model business today |
	  | GCP third-party AI ARR (IaaS/TaaS), end-2027 | **>\$73B** | Estimate |
	  | TPU system sales, end-2027 | **~\$120B** | Estimate |
	  | **Total external, end-2027** | **~\$200B** | At **high-30s EBIT margins** |
	- Their conclusion: "**\$200B of external sales… vs a first party business generating just \$12B today shows where the focus is.**"
	- **DeepMind's share of total GCP AI megawatts** (chart read) — the compute-allocation evidence: peaks ~**44%** in 1H25, ~38% in 1Q26, then falls to ~30% (2Q26), ~21% (4Q26), and **~15% by 4Q27**. If accurate, DeepMind's compute share roughly **thirds** in two years.
	- **TPU sales to Anthropic**: **>20% of total TPU shipments from 3Q26 to 4Q27 sold directly to Anthropic** — and this *excludes* the hundreds of thousands GCP already rents to Anthropic, plus hundreds of thousands more committed to Anthropic and Meta over the next six quarters. Chart shows direct-sale share rising from **~15% (2026) to ~22% (2027)**. Footnote: "shipment" means supplier revenue recognition, not chips operational.
	- **GCP growth decomposition** — the most decision-useful disclosure: reported GCP growth was **82%**, but TPU system sales (accounted **gross at ~\$35B/GW**) contributed **~\$1.2B in 2Q26**, so **core GCP grew in the low 70s**. Backlog **>\$150B of TPU systems**, with an estimated **>\$250B of additional TPU bookings** potentially entering RPO in coming quarters.
	- Their 2027 call: TPU system sales drive **GCP growth into the mid-100s vs sellside consensus at 64%**, adding **~\$3 to Google EPS in 2027**. Caveat they raise themselves: system-sale EBIT margins are lower (low 30s) than core cloud, and **how investors capitalize the TPU backlog is an open question**.

- ## Where this contradicts Google's own disclosure
	- **Compute allocation.** [[GOOG-2026-Q2]] records management stating *repeatedly* a priority stack of **(1) frontier/AGI model development first**, then core products, then cloud serving, with external TPU demand balanced **last**. SemiAnalysis asserts the inverse — that Kurian won, and DeepMind's MW share collapses to ~15%. **These cannot both be true.** The DeepMind-share chart is the falsifiable version of the claim; Google's stated priority is the rebuttal. Worth resolving before acting on either.
	- **Token growth.** Momentum vs deceleration on identical figures, as above.
	- A third, softer tension: Google is simultaneously **selling TPUs externally and renting third-party capacity** (SpaceX deal) to bridge its own shortage — which fits SemiAnalysis's "selling compute to competitors" thesis but complicates the claim that this is purely opportunistic financialization rather than capacity arbitrage.

- ## The structural bear case, and the counter
	- **"No substitute for conviction."** The argued failure mode: AGI-pilled labs pre-pay for multiple GWs and find creative ways to monetize excess capacity **while retaining optionality to claw it back for research** — explicitly what Meta and SpaceX do. Google instead sold compute to Gemini's fiercest competitors **on long-term contracts with no path to returning it to DeepMind**.
	- **The IBM/Intel analogy**: Google "will join the ranks of other legendary tech giants like IBM and Intel to give up on the harder thing and do the thing that will make you more money" — IBM retreating to mainframes and consulting, Intel quitting mobile then stumbling on EUV. Also the cable analogy: owning the vertical stack → becoming "the dumb pipes" à la Charter.
	- **The ratchet argument** is the sharpest formulation: "once they start to post those impressive numbers, it will be **literally impossible to stop giving shareholders what they want or shares will tank**." Financialization is self-reinforcing regardless of strategic cost.
	- **Culture, not people, is the diagnosis**: "The issue with Google was not Jeff Dean nor Noam Shazeer, but rather their extremely bureaucratic, painfully slow, and strategically timid culture." Evidence cited: **DeepMind had a ChatGPT-equivalent chatbot a year before ChatGPT** (internally "LMChat") and was blocked from shipping it for fear of disrupting search — confirmed publicly by Tibo (@thsottiaux), a 9-year Google/DeepMind veteran who left in July 2024, co-led OpenAI's original coding-agent team, and now heads Codex.
	- **TPU durability is not assumed**: of the **76 credited authors on the TPU v1 ISCA-2017 paper**, only **28 remain at Google** — 9 went to OpenAI, 3 each to NVIDIA (via Groq), Etched, and Meta, with 17 leaving no public trail. The authors flag that TPU's TCO advantage "may crumble" against NVIDIA and ask openly whether Google can maintain the edge.
	- **The strongest counter-argument appears in the comments, not the piece.** One reader: model weights and algorithms are **soft moats that walk out the door with talent**, whereas **physical infrastructure and power are hard moats**; Google is maximizing near-term revenue from rivals to subsidize its own capex in a market hitting the "Power Wall." Another notes **Amazon abandoned first-party frontier models long ago and is doing fine** — which is precisely Jassy's position in [[AMZN-2026-Q2]] ("AWS and Amazon can have a wildly successful business without its own frontier model"). If Amazon's stance is respectable, the same stance at Google is a strategy, not a surrender.
