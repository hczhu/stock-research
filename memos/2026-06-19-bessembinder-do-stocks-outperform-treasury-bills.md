- tags:: [[skewness]], [[diversification]], [[concentration]], [[stock-returns]], [[portfolio-construction]], [[active-management]], [[academic-research]], [[investing]]

- **Source**: Bessembinder, Hendrik — "Do Stocks Outperform Treasury Bills?", *Journal of Financial Economics* (2018). Data: CRSP monthly returns, all NYSE/Amex/Nasdaq common stocks, 1926–2016 (~26,000 / ~25,300 firms).

- **Thesis**: Although the *overall* US stock market dramatically outperforms Treasury bills (the "equity premium puzzle"), the *majority of individual stocks do not*. Aggregate market gains are driven by a tiny minority of big winners. This is a direct consequence of **positive skewness** in long-horizon individual-stock returns — and it is the core mathematical case for diversification and against concentrated/active portfolios.

- ## Headline Data Points

	- | Statistic | Value |
	  |---|---|
	  | Monthly CRSP returns > 1-month T-bill (1926–2016) | only **47.8%** |
	  | Monthly CRSP returns that are positive | **less than half** |
	  | Stocks with lifetime buy-and-hold return > T-bill | only **42.6%** (≈3 of 7) |
	  | Stocks with negative lifetime return | **more than half** |
	  | Single most common lifetime outcome (rounded to 5%) | a **−100% loss** (total wipeout) |
	  | Median stock lifespan in CRSP | **7.5 years** (90 months) |
	  | 90th-percentile lifespan | ~28 years (334 months) |
	  | Stocks present all 90 years | just **36** |

- ## Aggregate Wealth Creation Is Extremely Concentrated

	- Total lifetime shareholder wealth creation (market value accumulated above what 1-month T-bill interest would have produced), as of Dec 2016: **~\$35 trillion** across ~25,300 firms.
	- | Group | Share of firms | Share of net wealth creation |
	  |---|---|---|
	  | Top 5 firms (Exxon Mobil, Apple, Microsoft, GE, IBM) | ~0.02% | **10%** |
	  | Top 90 firms | ~0.36% (1/3 of 1%) | **over 50%** |
	  | Top 1,092 firms | **4%** | **100%** of net wealth creation |
	  | Remaining 96% of firms | 96% | collectively **matched T-bills** (zero net) |

- ## Bootstrap Simulation: Single-Stock Strategy (random stock each month, 1926–2016)

	- Underperformed the **value-weighted market** in **96%** of simulations.
	- Underperformed the **1-month T-bill** in **73%** of simulations.
	- Note: this is *despite* the documented small-firm effect (Banz 1981), which would have predicted single-stock outperformance — skewness overwhelms it.

- ## The Core Argument: Mean vs Median, and Skewness

	- Standard asset-pricing models predict a positive **mean** excess return (risk premium) — they say nothing requiring a positive **median**. The data: negative *median* excess return, positive *mean*. So the findings are **not inconsistent** with risk-averse equilibrium models.
	- A few large winners pull the mean above zero while the typical (median) stock loses to T-bills. That gap *is* positive skewness.
	- Skewness has two sources: (1) skewness already present in monthly individual-stock returns, and (2) **compounding of random returns mechanically induces skewness** — so skewness *increases with horizon*. Long-horizon returns are far more skewed than monthly.
	- Normal-distribution / mean-variance / Sharpe-ratio framing is "reasonable at short horizons" but breaks down at long horizons because of this skewness.

- ## Why Recent-Era Stocks Are Worse

	- The share of stocks underperforming T-bills is **higher for cohorts that listed in recent decades**. Consistent with Fama-French (2004): post-1980 surge of new listings — riskier firms, high asset growth, low profitability, low survival rates.
	- Supports "winner-take-all" internet-economy outcomes (Noe-Parker 2005) and rising industry concentration with abnormal returns to winners (Grullon et al. 2018).
	- Public-equity long-term returns therefore resemble **venture-capital payoff distributions** (most investments lose, a few huge winners carry the whole) — not just pre-IPO, but listed equities too, especially small and recently-listed firms.

- ## Related Time-Series Findings (cited)

	- Savor-Wilson (2013): ~60% of cumulative market excess return accrues on the few days with macro announcements.
	- Lucca-Moench (2016): half of US excess return since 1980 accrues the day before FOMC meetings.
	- Parallel lesson: just as you must not be *out of the market* at key times, you must not *omit key stocks* from the portfolio.

- ## Investment Implications

	- **Diversification is not just variance reduction — it's skewness insurance.** A concentrated portfolio bears the risk of simply *missing* the handful of stocks that, ex post, produce essentially all the gains. This is the cleanest mathematical explanation for why most active (poorly-diversified) managers underperform the index *more than half the time* (Heaton et al. 2017, Ikenberry et al. 1998).
	- **Median ≠ mean is the whole game.** "Pick a random stock and hold it" loses to cash 73% of the time over the long run. Stock-picking only wins if you have a genuine comparative advantage at identifying the rare extreme winners *in advance* — the payoff to that skill is enormous, but the base rate for the median stock is brutal.
	- **The skewness justifies *both* sides**: index investors should diversify broadly to guarantee capturing the winners; long-horizon investors who explicitly value upside lottery-like skewness may rationally hold concentrated books *despite* knowing they'll most likely underperform the market.
	- **Caution on performance evaluation**: standard Sharpe-ratio / mean-variance manager evaluation may be misleading at long horizons given strong positive skewness — the paper argues for reassessing how investment performance is judged.
	- **Read-through to today's mega-cap concentration**: the empirical regularity (top handful of names = the bulk of wealth creation) is structural and long-standing, not a 2020s anomaly — relevant context for debates about market breadth and index concentration in names like the AI mega-caps.

