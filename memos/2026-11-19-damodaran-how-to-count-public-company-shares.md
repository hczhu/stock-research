tags:: [[valuation]], [[Aswath-Damodaran]], [[share-count]], [[stock-based-compensation]], [[ai-model:GPT-6.2 Sol]], [[ai-effort:medium]]
file-created-at:: 2026-11-19
file-updated-at:: 2026-11-19

- ## How to count a public company’s shares
	- **Source**: Aswath Damodaran, *Musings on Markets*, November 18, 2026. [The Rocky Road from Aggregate to Per Share Value](https://aswathdamodaran.blogspot.com/2026/11/the-rocky-road-from-aggregate-to-per.html)
	- **Thesis**: Start with actual common shares outstanding across every class, then account for outstanding equity claims once. This distinction matters most at companies with substantial stock-based compensation or convertibles, where a single denominator can hide a material claim on common equity.

- ## Which numbers to pull from the filing
	- | Item | Where to look | Treatment |
	  | --- | --- | --- |
	  | Authorized shares | Equity footnote or charter | Legal issuance capacity. Leave it out of the share count. |
	  | Issued and treasury shares | Balance sheet and equity footnote | Issued shares can include shares the company bought back and holds in treasury. If the filing supplies issued and treasury shares on the same basis and date, subtract treasury shares to get outstanding shares. |
	  | Common shares outstanding | Filing cover page, balance sheet and equity footnote | Sum all outstanding common classes, including unlisted founder shares. If classes have different economic rights, allocate value according to those rights before computing a class-specific price. |
	  | Restricted stock and restricted stock units | Share-based compensation footnote and award rollforwards | Issued restricted shares can already be in outstanding shares. An unsettled RSU is a promise to deliver shares under the award terms. Check vesting, settlement, performance conditions and forfeitures before adding incremental shares. |
	  | Employee options | Option rollforward and strike or maturity disclosures | Use outstanding grants and their exercise prices, remaining lives and vesting terms. An option can have time value when the stock trades below its strike. Above the strike, waiting can be worth more than immediate exercise. |
	  | Convertible bonds or preferred shares | Debt and preferred equity footnotes | Check conversion ratio, triggers and whether settlement is in cash or shares. In a conversion scenario, update both the share count and the debt or preferred claim in the equity bridge. |
	- Restricted awards can have service or performance conditions. Some issued shares also have trading restrictions after vesting. A trading restriction affects liquidity. Check legal issuance and the filing’s definition of outstanding shares separately.
	- Record the count date and reconcile subsequent buybacks, issuances, stock splits or offering shares through the valuation date when disclosed. Cover-page counts often have a later measurement date than the balance sheet. Reconcile changes from a consistent starting date so a settled award or completed buyback enters the count once.
	- Basic EPS generally uses weighted-average shares for the reporting period. Diluted EPS adjusts that period average for securities that are dilutive under the applicable accounting rules. A loss quarter can exclude potential shares as antidilutive even when the awards still matter for valuation. [Example of EPS and award disclosures in a public filing](https://www.sec.gov/Archives/edgar/data/1650729/000110465926038881/tm268959d3_ars.pdf)

- ## Share counts for valuation
	- | Method | Construction | How to interpret it |
	  | --- | --- | --- |
	  | Primary | Actual outstanding common shares across classes | Clean starting point for a dated cap table. Dividing total equity value by this count alone can overstate common value per share when other claims are material. |
	  | Partially diluted | Add a defined subset, such as vested unsettled awards and in-the-money options | Makes near-term dilution visible. The count depends on the share price and eligibility rules. A gross option count ignores exercise proceeds. |
	  | Fully diluted, gross | Add all incremental share-settled awards, option shares and assumed conversion shares covered by the scenario | Shows potential share issuance under stated assumptions. A simple fixed-equity calculation ignores option proceeds and changes to senior claims on conversion. |
	  | Option-adjusted valuation | Subtract fair value of existing options from aggregate equity value and divide by primary shares plus incremental restricted share equivalents included in the model | Preserves the distinction between a share and a contingent claim. Model the relevant exercise price, expected life and volatility. Keep option shares out of this denominator because their value is already deducted. |
	- A treasury stock calculation is a useful shortcut for plain options. At a chosen share price, estimate net incremental shares as in-the-money option shares minus shares that their exercise proceeds could repurchase at that price. Reported diluted EPS applies its own period-average pricing and accounting rules. Fair-value treatment also captures option time value.
	- Treat a convertible consistently. If its full fair value is already deducted in the enterprise-to-equity bridge, its conversion option is already reflected in that claim. Under an assumed share conversion, remove the relevant senior claim and add the corresponding shares. Value existing awards as outstanding claims and reflect compensation from future grants in projected economics.

- ## Worked example with the same starting equity value
	- Assume USD 2 billion of equity value before allocating it to existing options, 100 million outstanding shares, 4 million additional RSUs (2 million vested but unsettled), and 6 million options. Assume 4 million options have a USD 10 strike and 2 million have a USD 30 strike, with a USD 20 reference stock price. The example assumes full settlement of the RSUs in the gross and option-adjusted cases.
	- | Valuation treatment | Denominator | Implied value per share |
	  | --- | ---: | ---: |
	  | Primary only | 100 million | USD 20.00 |
	  | Partially diluted, gross | 106 million, including vested unsettled RSUs and in-the-money options | USD 18.87 |
	  | Fully diluted, gross | 110 million, including all RSUs and all options | USD 18.18 |
	  | Option-adjusted, assuming USD 60 million of aggregate option fair value | 104 million, including RSUs | USD 18.65 |
	- The first three rows hold the numerator fixed to show what a change in the share count alone does. The last row allocates USD 60 million of value to option holders before dividing the remaining USD 1.94 billion by 104 million shares. For comparison, exercising 4 million options at USD 10 would bring in USD 40 million. The simple gross calculation gives no credit for that cash.
	- When comparing price targets or multiples, record the exact share-count date, the treatment of each material award and convertible, and any corresponding adjustment to equity value. This makes a difference in valuation assumptions distinguishable from a difference in dilution assumptions.
