tags:: [[Anthropic]], [[OpenAI]], [[ARR]], [[revenue]], [[enterprise]], [[model-adoption]], [[Ramp]], [[tokenomics]], [[AI]], [[pricing]]

- ## FT revenue figures for Anthropic and OpenAI, plus the Ramp AI Index model mix
	- **Source**: Simon Willison's notes on a *Financial Times* story, with figures the FT attributes to **"people with knowledge of the matter"** — unaudited, company-supplied, and not defined in the article. Includes the July 2026 **Ramp AI Index** model-spend breakdown for Anthropic.
	- **Thesis**: Two things worth extracting. First, **Anthropic's reported run rate has moved above OpenAI's**, which inverts the default narrative — but the supporting customer disclosure does not reconcile with the headline, so the definitional question matters more than the number. Second, the Ramp data shows **enterprise spend concentrated in the most expensive tier and migrating between model versions very slowly**, which cuts against the fastest versions of the commoditization thesis.
- ## The revenue figures, with the arithmetic they imply
	- | Company | Reported annualized revenue | Growth | Context |
	  |----------------|-----------------------------|--------------------------|-----------------------------------------|
	  | **Anthropic** | **\$65bn** (July) | from **\$47bn** in May — **+38.3% in ~2 months** | Expects Q3 to be profitable |
	  | **OpenAI** | **>\$40bn** | **+35% quarter-to-date** | GPT-5.6 launched in July, "jolting" performance after a sluggish start to the year |
	- **The headline comparison**: Anthropic is now reported at roughly **1.6× OpenAI's annualized revenue**. Given how the relative positioning is usually described, that is the single most narrative-relevant figure here — and it is consistent with Ben Thompson's aside in [[2026-08-21-ben-thompson-ilb-risk-relocation-commodity-logic]] that OpenAI is pivoting to enterprise "because Anthropic is kicking [them] over" there.
	- **Both numbers should be handled as run rates, not revenue.** "Annualized revenue" is typically the latest month or week multiplied out; it is not a forward guarantee, not audited, and the two companies need not be computing it the same way. Neither figure is comparable to a reported GAAP revenue line. Prior figures in the series are tracked in [[2026-06-02-anthropic-arr-growth-milestones]] and [[2026-07-13-semianalysis-anthropic-ipo-financials-tokenomics]].
	- **The profitability claim carries a load-bearing qualifier** that Willison preserves deliberately: Anthropic expects Q3 to be profitable *"according to the same model they used to declare Q2 profitable."* That is a company-defined model, not a standard. For a frontier lab the classification of **training compute** — expensed, capitalized, or excluded as R&D — decides the answer, so "profitable" here says less than it appears to.
- ## The disclosure that does not reconcile
	- Anthropic also told investors it has **6,000 customers spending \$100,000 or more annually**. Taken at the threshold, that cohort is worth **\$600M — about 0.9% of a \$65bn run rate.**
	- **Working the implication**: in enterprise software the ≥\$100k cohort typically carries most of revenue. If it carried **60%** of Anthropic's run rate, the average customer in it would have to be spending **~\$6.5M per year**. For scale, Datadog's ≥\$100k cohort in [[DDOG-2026-Q2]] is ~4,720 customers producing ~91% of roughly \$4.5bn of ARR — an average near **\$870k**. Anthropic would need roughly **7.5× that average across a larger cohort**.
	- **Three readings, and the memo does not pick one**: (1) revenue is extraordinarily concentrated in a handful of very large accounts (resale partners, coding-tool platforms, hyperscaler channels) that dwarf the 6,000; (2) a large share sits outside the enterprise-contract base entirely, in consumer and prosumer subscriptions; or (3) **the \$65bn and the 6,000-customer figure are computed on different bases** and should not be placed in the same sentence.
	- **The usable conclusion**: the customer-count disclosure is a **floor statistic offered without a denominator**, and it is the kind of number that reads as substantiation while providing none. Do not treat "6,000 customers at \$100k+" as evidence for the \$65bn figure — arithmetically it is closer to evidence against it.
- ## Ramp AI Index — what it measures, and what it cannot
	- **Methodology**: billing data from **70,000 companies** using Ramp corporate cards, used to estimate model adoption. Three structural limits that determine how far the data travels:
		- It captures **card-billed spend**. Large enterprise contracts paid by invoice, wire, or through a hyperscaler marketplace are invisible — which means it systematically **under-represents exactly the ≥\$100k cohort** discussed above.
		- Ramp's customer base skews **startup, SMB, and tech**. Read it as a proxy for that segment, not for the market.
		- It measures **dollars, not tokens or seats**. Cheap models are structurally under-weighted: a model can carry enormous token volume and a trivial spend share.
	- **Anthropic model spend share, July 2026**:
	  | Rank | Model | Share |
	  |------|--------------|--------|
	  | 1 | Opus 4.8 | **28.0%** |
	  | 2 | Sonnet 4.6 | 8.3% |
	  | 3 | Fable 5 | 8.0% |
	  | 4 | Opus 4.6 | 6.9% |
	  | 5 | Sonnet 5 | 3.6% |
	  | 6 | Opus 5 | 3.5% |
	  | 7 | Opus 4.7 | 1.7% |
	  | 8 | Sonnet 4.5 | 1.3% |
	  | 9 | Haiku 4.5 | 1.0% |
	  | 10 | Opus 4.5 | 0.7% |
	  - **Derived**: the top ten sum to **63.0%**, leaving **37% unlisted** — so this is a partial picture even within Ramp's own panel. By family: **Opus 40.8%, Sonnet 13.2%, Fable 8.0%, Haiku 1.0%**. Opus is therefore **~65% of all identified spend.**
- ## What the model mix actually shows
	- **Enterprises are paying for the top tier.** Opus taking roughly two-thirds of identified spend is the clearest signal in the table, and it argues against the fastest version of the intelligence-commoditizes thesis — at least in dollar terms, buyers are not trading down. The caveat is the methodology one: this is spend share, so an expensive model wins share by being expensive.
	- **Version migration is slow, and this is the most useful operational finding.** Legacy Opus releases (4.5 through 4.8) total **37.3%** against **3.5%** for Opus 5. Willison's own read is that this looks reasonable because **Opus 5 only shipped on July 24**, giving it about a week of the month — so the 3.5% is not a demand signal. But the same pattern appears where recency is not an excuse: **Sonnet 4.6 at 8.3% versus Sonnet 5 at 3.6%.** Buyers stay on known versions.
		- **Read-through**: a long tail of production traffic sitting on older model versions makes life easier for inference stacks that compile ahead of time for a narrow model catalog — the central weakness flagged for TileRT in [[2026-08-09-semianalysis-tilert-inferencex-gpu-vs-dataflow-asic]]. If enterprises take months to move versions, a small supported catalog is less disqualifying than it appears.
	- **Fable 5 at 8.0%** — Willison reads the placement as supporting the idea that **Fable's cost has made it a less popular model**. Worth holding loosely: in a spend-denominated index, a *high-priced* model showing modest share is a stronger negative signal than it would be in a usage-denominated one, since price inflates the numerator.
	- **Haiku 4.5 at 1.0%** should not be read as low adoption. In a dollar-weighted index the cheapest model is guaranteed to look small; its token share could be many multiples of its spend share. **This is the clearest illustration of why the index answers "where do the dollars go," not "which models get used."**
- ## What would make these numbers trustworthy
	- A definition of "annualized revenue" from either company — latest month annualized, contracted, or recognized.
	- The **share of revenue** from the ≥\$100k cohort, not just the count, which is the disclosure that would resolve the reconciliation above.
	- Treatment of **training compute** in the profitability model.
	- A **usage-weighted** companion to the Ramp index, which would separate the price effect from the adoption effect in the Fable and Haiku readings.
