- tags:: [[SaaS]], [[software]], [[metrics]], [[valuation]], [[unit-economics]], [[ARR]], [[churn]], [[FCF]], [[Rule-of-40]], [[Barclays]]

- **Source**: Barclays Research — "The Metrics Handbook: A Guide to Analyzing Software," 7 December 2020. Analyst: Raimo Lenschow, CFA.

- ## Overview

	- Three metric categories: **Top-Line** (revenue quality/visibility), **Customer** (retention/acquisition economics), **Profitability** (efficiency/cash generation).
	- Formula cheat-sheet from the report:
		- | Metric | Formula |
		  |---|---|
		  | Billings | Revenue + ΔDeferred Revenue (q/q) |
		  | Bookings | Revenue + ΔRPO |
		  | ST Bookings | Revenue + ΔcRPO |
		  | ARR | Recurring TCV / Duration |
		  | Gross Customer Retention | (Beg. Customers − Lost) / Beg. Customers |
		  | Net Customer Retention | Ending Customers / Beg. Customers |
		  | Dollar Net Retention | (Beg. Rev + Upsells − Downsells − Churn) / Beg. Rev |
		  | LTV | (Net New Revenue × Gross Margin) / Churn Rate |
		  | CAC | Prior S&M × % on New Business |
		  | CAC Payback | CAC / (ARPC × Gross Margin) |
		  | New Business Dependency | Revenue Growth − Dollar Net Expansion |
		  | SMB Exposure | SMB Revenue / Total Revenue |
		  | Rule of 40 | Top-line Growth % + Profitability Margin % |
		  | S&M Margin | S&M Expense / Revenue |
		  | Magic Number | [(Curr Rev − Prior Rev) × 4] / Prior S&M |
		  | FCF | Operating Cash Flow − Capex |
		  | uFCF | FCF + Interest Expense |
		  | FCF Margin | FCF / Revenue |
		  | Cash Conversion | FCF / EBITDA |
		  | ROIC | [EBIT × (1 − Tax Rate)] / (Total Equity + Total Debt − Cash) |

- ## Top-Line Metrics

	- ### Revenue
		- **Definition**: Income recognized from normal business activities per ASC 606.
		- **Pros**: Universally reported, easiest to compare across companies.
		- **Cons**:
			- ASC 606 creates timing distortions — term licenses front-load recognition; subscription revenue spreads it out, causing the same contract to produce very different reported revenue profiles.
			- Lags cash: revenue is drawn from the deferred revenue balance built up by prior billings.
			- Not a proxy for future performance on its own.

	- ### Billings
		- **Definition**: Revenue + ΔDeferred Revenue (quarter-over-quarter). Captures what was invoiced in the period.
		- **Pros**: Leading indicator of future revenue; closer to cash received; reflects current business momentum better than GAAP revenue.
		- **Cons**:
			- Only captures invoiced amounts, not total contracted (misses multi-year TCV not yet invoiced).
			- Highly volatile based on invoicing terms — annual vs. multi-year prepayments distort comparisons.

	- ### Bookings
		- **Definition**: Revenue + ΔRPO (change in remaining performance obligations). Captures total new contract value committed regardless of invoicing.
		- **Pros**: Best leading indicator; unaffected by invoicing terms; shows full TCV of new contracts signed.
		- **Cons**:
			- No duration adjustment — a \$10M 5-year contract looks the same as a \$10M 1-year contract.
			- Newer disclosure with short history (harder to build long time-series).

	- ### Short-Term Bookings (ST Bookings)
		- **Definition**: Revenue + ΔcRPO (current RPO, typically the next 12 months of remaining obligations).
		- **Pros**: Leading indicator that also normalizes for contract duration by focusing on the next 12 months.
		- **Cons**:
			- cRPO definition varies by company (some use 12 months, others 24+ months).
			- Distorted during cloud/subscription transitions where large multi-year contracts shift in and out.

	- ### Annual Recurring Revenue (ARR)
		- **Definition**: Recurring TCV / Duration. Company-reported non-GAAP figure annualizing the recurring revenue run-rate.
		- **Pros**: Normalizes both ASC 606 timing distortions and contract duration differences; gold standard for pure subscription businesses; most directly tracks underlying recurring business growth.
		- **Cons**:
			- Ignores non-recurring revenue (professional services, one-time fees).
			- Non-GAAP "black box" — each company defines and calculates it differently; not audited.

	- ### Professional Services Mix
		- **Definition**: Professional Services Revenue / Total Revenue.
		- **Pros**: Quality signal — lower mix = more recurring, higher-margin revenue; resiliency signal for downturns (recurring revenue is stickier than project-based).
		- **Cons**:
			- Only ~70% of software companies report it separately.
			- Company-specific nuances: some high services mix is justified (e.g., Appian's low-code platform requires significant implementation work as a feature, not a flaw).

- ## Customer Metrics

	- ### Gross Customer Retention
		- **Definition**: (Beginning Customers − Customers Lost) / Beginning Customers. Measures how many customers stayed.
		- **Pros**: Leading indicator of product-market fit; direct satisfaction proxy.
		- **Cons**:
			- Treats all customers equally regardless of ARR size — a \$1M customer churning has the same impact as a \$10K customer.
			- Ignores natural SMB churn dynamics (SMB inherently has higher churn than enterprise).

	- ### Net Customer Retention
		- **Definition**: Total Ending Customers / Beginning Customers. Includes both retained and newly added customers.
		- **Pros**: Captures high-growth phases where gross retention is misleading (gross retention can be falling while net customer count keeps growing at 120%+).
		- **Cons**: Still treats all customers as equal; doesn't surface revenue quality.

	- ### Dollar Net Retention Rate
		- **Definition**: (Beginning Revenue + Upsells − Downsells − Churn) / Beginning Revenue.
		- **Pros**:
			- Considers all existing customer actions (upgrade, renew, downgrade, churn).
			- Focuses on hard dollars, not customer count — more relevant at scale.
			- Industry benchmark: ~115% is strong; >130% is exceptional (e.g., Workday, Elastic at time of report).
		- **Cons**:
			- Can downplay customer churn: a company losing customers rapidly can still show >100% DNR if average ACV per remaining customer grows fast enough (see illustrative example: customer count falls from 1,000 → 765 over 4 years while DNR stays 105–112%).
			- No accounting for new customer activity — companies with high new customer dependency (e.g., Five9 at ~82% of growth from new logos) are poorly analyzed by DNR alone.

	- ### LTV to CAC
		- **Definition**: LTV = (Net New Revenue × Gross Margin) / Churn Rate. CAC = Prior S&M × % Spent on New Business. Industry benchmark: **>3.0x**.
		- **Pros**:
			- Proxy for sales efficiency: a ratio >3.0x means S&M is tripling its investment.
			- LTV:CAC <1.0x means salesforce is destroying value.
			- Focuses specifically on new customer economics (unlike retention metrics which focus on existing).
		- **Cons**:
			- CAC only includes S&M — ignores R&D (which builds the features that close deals) and G&A.
			- LTV assumes constant churn and gross margin over time; in practice both change materially as a business scales.

	- ### CAC Payback Period
		- **Definition**: CAC / (ARPC × Gross Margin). Result is in years; multiply by 12 for months.
		- **Pros**:
			- Adds time dimension to unit economics — "how many months until the customer pays back what it cost to acquire them?"
			- Shorter payback = less working capital needed to fund growth.
			- Industry segment benchmarks: Freemium = short, SMB = medium, Enterprise = long.
		- **Cons**:
			- Assumes 0% churn (overstates ability to recoup CAC).
			- Ignores time value of money (no discount rate).
			- Varies enormously by customer segment — blended company-level CAC payback is hard to compare without segment-level disclosure.

	- ### Customer Concentration
		- **Definition**: Qualitative/quantitative measure of what % of ARR comes from the largest customers, typically disclosed as "no customer > X% of revenue."
		- **Pros**:
			- Barometer for revenue risk and resiliency.
			- High concentration = fragile in downturns; diverse customer base = more resilient.
		- **Cons**:
			- Artificially rewards consumer and SMB models (many small contracts naturally look diverse; their actual resilience may be lower due to higher individual churn rates).
			- Relies entirely on management disclosure; cannot be independently calculated.

	- ### New Business Dependency
		- **Definition**: Revenue Growth − Dollar Net Expansion (from existing customers). The residual is the portion of growth coming from new logos.
		- **Average across Barclays coverage**: ~50% of revenue growth comes from new customers.
		- **Pros**:
			- Reveals the underlying sales motion (new logo hunting vs. land-and-expand).
			- Complements DNR: high DNR + low new business dependency = strong expansion business; high new business dependency + weak DNR = land-heavy model with upsell challenges.
		- **Cons**:
			- Business model context is essential — horizontal/best-of-suite platforms (Workday, Salesforce) legitimately have higher new business dependency because upsell potential is capped by product breadth.
			- Seldom directly disclosed; must be derived.

	- ### SMB Exposure
		- **Definition**: SMB Revenue / Total Revenue. SMB defined differently by each company (e.g., Five9 uses <50 users).
		- **Enterprise vs. SMB comparison**:
			- | Dimension | Enterprise | SMB |
			  |---|---|---|
			  | Contract value | Higher | Lower (volume) |
			  | Retention | Higher | Lower (natural churn) |
			  | Sales cycle | Longer, complex | Quicker, direct |
			  | CAC | Higher | Lower |
		- **Pros**: Contextualizes other metrics — high SMB exposure explains lower DNR, higher gross churn, and lower ACV; essential for like-for-like comparisons.
		- **Cons**:
			- SMB definitions vary wildly; hard to compare across companies.
			- High SMB exposure can be strategic and intentional (e.g., Slack's prosumer motion).

- ## Profitability Metrics

	- ### Rule of 40
		- **Definition**: Top-line Growth % + Profitability Margin %. Passes when sum ≥ 40.
		- **Formula flexibility**: Growth can be revenue, ARR, or billings growth; margin can be operating, FCF, EBITDA, or uFCF margin. Use whichever best represents the business.
		- **Illustrative equivalence**: A startup with 60% revenue growth and −20% FCF margin = Rule of 40; a mature company with 20% growth and 20% FCF margin = same Rule of 40.
		- **Pros**:
			- Near-universal metric that normalizes across business lifecycle stages.
			- Directly maps to how software companies are valued (EV/Sales for growth, EV/FCF for maturity).
			- Flexible metric inputs allow adjusting for business model nuances.
		- **Cons**:
			- Outliers exist: ZoomInfo had Rule of 92 pre-IPO; Zoom Video was guiding 314% growth with −273% profitability margin (still "passes" mathematically, making the benchmark less useful at extremes).
			- Not applicable at the very early stage (VCs use unit economics) or very mature stage (dividends/buybacks dominate).

	- ### S&M Margin
		- **Definition**: Sales and Marketing Expense / Revenue.
		- **Context**: S&M is typically the largest opex item for software companies (~65% of total opex at median, vs R&D ~35%, G&A ~10%).
		- **Pros**:
			- Universally reported and in every financial model — easiest cross-company comparison.
			- Quick proxy for sales efficiency and go-to-market productivity.
		- **Cons**:
			- Does not tell the whole story — companies with heavy R&D spend (product-led growth) or G&A could look efficient on S&M but aren't.
			- Lags S&M to revenue: S&M investments in Q1 drive Q2/Q3 revenue (6–9 month average sales cycle in software), so the ratio in any given period is inherently distorted.

	- ### Magic Number
		- **Definition**: [(Current Quarter Revenue − Prior Quarter Revenue) × 4] / Prior Quarter S&M.
		- **Decision rules**:
			- | Magic Number | Interpretation |
			  |---|---|
			  | <0.5 | Not ready for S&M investment — returns too low |
			  | 0.5–0.75 | Evaluate situation |
			  | >0.75 | Ideal time to invest aggressively in S&M |
		- **Pros**:
			- Annualizes the revenue added per dollar of S&M spend (×4 factor).
			- Correctly lags S&M to revenue by one quarter (Q1 S&M drives Q2 revenue).
			- Better than raw S&M margin for go-to-market efficiency assessment.
		- **Cons**:
			- Highly sensitive to one-off quarterly fluctuations (COVID quarter example: a temporary revenue dip gets multiplied by 4, which can push a healthy business below the 0.5 threshold).
			- Treats all revenue growth as equal — can't tell if the growth came from new customers (S&M's job) or existing expansion (customer success's job); must be paired with DNR to interpret properly.

	- ### Free Cash Flow (FCF) Margin
		- **Definition**: FCF / Revenue. FCF = Operating Cash Flow − Capex. uFCF = FCF + Interest Expense (for companies with significant debt).
		- **Derivation**: Net Income → add back non-cash charges, working capital changes → Operating Cash Flow → subtract Capex → FCF.
		- **Pros**:
			- Closest metric to cash actually left over for shareholders after operating expenses and capital investment.
			- Normalizes for size via revenue denominator; valid across company lifecycle once FCF turns positive.
			- Preferred profitability input for Rule of 40 in mature software companies.
		- **Cons**:
			- Less relevant for high-growth unprofitable companies (negative FCF is common; operating margin and EV/Sales multiples are used instead).
			- Companies with debt need uFCF adjustment — standard FCF overstates shareholder cash if interest payments are material.

	- ### Cash Conversion
		- **Definition**: FCF / Adjusted EBITDA. Measures how much of EBITDA ultimately becomes free cash flow.
		- **Benchmark**: Close to 100% = almost all operating profit becomes shareholder cash; well above 100% is unusual and warrants investigation.
		- **FCF vs. EBITDA gap explained**: FCF = (EBITDA + Interest Expense) × (1 − Tax Rate) − ΔWorking Capital − Capex.
		- **Pros**:
			- Normalized as a % of EBITDA (adjusts for depreciation and accounting differences across companies).
			- Measures working capital management and capex efficiency simultaneously.
			- EBITDA acts as a common denominator that adjusts for capital structure differences.
		- **Cons**:
			- Requires positive FCF and EBITDA to be meaningful; useless for unprofitable growth companies.
			- Doesn't split capex intensity from working capital efficiency — strong cash conversion could mask under-investment in capex (deferred maintenance/growth) rather than genuinely lean working capital management. Should be viewed alongside capex as % of revenue.

	- ### Return on Invested Capital (ROIC)
		- **Definition**: NOPAT / Invested Capital = [EBIT × (1 − Tax Rate)] / (Total Equity + Total Debt − Cash).
		- **WACC context**: Commonly compared vs. WACC. ROIC − WACC > 2% = value creator; < 2% = value destroyer.
		- **Pros**:
			- Proxy for true value creation — how much return does the business generate on capital deployed by all providers (debt + equity).
			- Normalizes across capital structures by including both debt and equity in the denominator (cash subtracted as it's not "deployed" in operations).
		- **Cons**:
			- Uses EBIT, which is subject to depreciation assumptions, SBC treatment, and tax rate estimates (tax rates can be near-zero for software companies with NOLs, inflating ROIC optically).
			- Denominator is a point-in-time snapshot — timing of M&A or large cash events can cause wild swings (e.g., VMware showed artificially high ROIC due to large cash balance at measurement date).
			- EBIT is negative for a significant portion of software coverage, making the metric inapplicable.

