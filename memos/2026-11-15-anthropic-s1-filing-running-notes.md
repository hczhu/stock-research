tags:: [[$ANT]], [[Anthropic]], [[IPO]], [[S-1]], [[accounting]], [[non-GAAP]], [[$GOOGL]], [[$AMZN]], [[$MSFT]], [[Bloomberg]], [[Matt-Levine]], [[WSJ]], [[Warren-Buffett]], [[Berkshire-Hathaway]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-15
file-updated-at:: 2026-11-15

- ## Anthropic S-1 Filing: Running Notes
	- **Scope**: a running memo on Anthropic, PBC's [Form S-1](https://www.sec.gov/Archives/edgar/data/2130357/000162828026067168/anthropicpbc-sx1.htm) (publicly filed Monday, October 26, 2026), extended as new commentary arrives. The core financial and compute analysis is in [[2026-10-26-anthropic-s1-financials-compute-economics]]. Demand and moat field notes are in [[2026-10-28-anthropic-s1-hacker-news-demand-product-moat-field-notes]], and the Q3 slowdown read is in [[2026-11-10-circuit-anthropic-s1-q3-slowdown-compute-constraint]].
	- **Sources so far**:
		- Matt Levine, *Money Stuff* (Bloomberg), early November 2026 (exact date not given in the excerpt). Levine quotes Jonathan Weil's *Wall Street Journal* column, written the week the S-1 went public.
- ## The \$80.7B H1 Loss Is a Mark-to-Market Artifact (Money Stuff)
	- | Item, H1 2026 | Amount | What it is |
	  | --- | --- | --- |
	  | GAAP net loss | **\$80.7B** (\$80.748B in the S-1) | Flows through the income statement |
	  | Excluded fair-value losses | **About \$72B** (\$72.388B in the S-1) | Marking convertible notes, derivative liabilities and SAFEs to market |
	  | Adjusted net income | **\$2.7B profit** | Anthropic's non-GAAP metric, which excludes those marks |
	  | Operating cash flow | **+\$3.929B** | From [[2026-10-26-anthropic-s1-financials-compute-economics]], for comparison |
	- **The mechanism, in Levine's framing**:
		- Anthropic previously sold stock-like instruments, largely to Google and Amazon: convertible notes, preferred stock and purchase agreements.
		- Some of their provisions make them partly **"derivative liabilities"** under US GAAP, so they must be marked to market.
		- Anthropic's value rose by about \$80B in H1, so those investors gained about \$80B, and Anthropic booked the matching loss.
		- For most practical purposes the instruments are stock. If they were plain stock, they would have created no accounting loss.
		- **The marks end at conversion.** Once the instruments convert into regular stock, they are no longer marked to market.
	- **Levine's summary of the economics**: "we basically broke even in our business, but because we issued some weird stock, we have an \$80 billion non-cash accounting loss reflecting the fact that our stock went up." In Levine's words, "the stock going up is a good thing!"
	- **Market reaction**: Levine says the general reaction to the financials has been positive, and analysts are quoting the roughly **\$2.7B adjusted net income**.
	- *My math*: going from a −\$80.7B GAAP loss to +\$2.7B adjusted income takes about **\$83.4B** of adjustments. The \$72.4B of fair-value marks covers most of it, leaving roughly **\$11B of other add-backs** that the excerpt doesn't explain. Pull the S-1's adjusted-net-income reconciliation before relying on the \$2.7B; stock-based compensation is a likely candidate, but that's unverified.
	- *My note*: as long as these instruments stay outstanding, any rise in Anthropic's value before the IPO adds more GAAP loss. An IPO priced above the June 30 mark would probably produce another large H2 fair-value charge before conversion (my inference; conversion terms not yet checked). After conversion, the line should disappear, and GAAP and adjusted results should converge.
- ## The Ledger Asymmetry: Weil vs. Levine
	- **Weil's argument (WSJ)**:
		- "On the other side of the ledger, Amazon.com and Alphabet booked large paper gains on some of the same financing deals."
		- Consistency question: "At Amazon and Alphabet, the gains count. But at Anthropic, the corresponding losses don't." Analysts include those unrealized gains in the consensus "Street earnings" for Amazon and Alphabet, even though the marks are volatile and unrelated to operations.
		- Weil grants that excluding Anthropic's \$72B of liability marks "arguably makes sense," because they don't reflect ongoing operations. If so, analysts covering Amazon and Alphabet should exclude the matching gains too.
		- Weil also reports the IPO could come "as soon as November."
	- **Levine's rebuttal: the overlap is a coincidence**:
		- Levine estimates investors' total gains on Anthropic at "\$1.5 trillion or whatever" (a rough figure). Only about **\$80B** of that shows up as a GAAP loss at Anthropic; the other roughly **\$1.42T** doesn't.
		- The \$80B is "a genuinely weird exception" to the normal rule. When a company issues stock and the stock rises, the company books no loss.
		- Holders booking a gain is normal. When a bank makes money trading stocks, everyone treats it as income for the bank, and the issuers record no offsetting loss.
		- Holder gains counting as income is a rule choice: US GAAP changed in 2016 to put most unrealized equity gains into net income. Warren Buffett objected that the change would "severely distort Berkshire's net income figures and very often mislead commentators and investors." Levine disagrees with Buffett: "I bought stocks that went up, so I have income" seems normal, while "Anthropic issued stock that went up, so it has a loss" does not.
	- **Levine's four rules**:
		- When you buy stock and it rises, you have economic and accounting income (but not taxable income).
		- When a company issues stock and it rises, the company has no economic or accounting loss.
		- So the books don't balance: the investor's gain isn't offset by the issuer's loss.
		- "Such is life!"
	- **The economic point**: if investors made \$1.5T on Anthropic, Anthropic didn't lose \$1.5T. It created \$1.5T of value, which it shares with investors. Stock investing is positive-sum.
- ## Where the Same Marks Land: Hyperscaler Earnings
	- **Microsoft**: discrete items in [[MSFT-2026-Q2]] included a **\$3.2B gain on the investment in Anthropic**, part of a **\$0.27 EPS** benefit versus guidance.
	- **Alphabet**:
		- [[GOOG-2026-Q2]]: OI&E was about **\$9.8B**, mostly unrealized equity-securities gains.
		- [[GOOG-2026-Q3]]: OI&E swung to **−\$8.2B**, mostly an unrealized loss on SpaceX.
		- My notes don't record how much of the Q2 gain came from Anthropic.
	- **Amazon**: Amazon's Q3 2025 results included a **\$9.5B pre-tax gain** on its Anthropic investment. That comes from Amazon's Q3 2025 release, not from this source.
	- *My note*: Weil's point lands on reported EPS for these companies. Once \$ANT trades publicly, a quoted price will likely replace marks based on funding rounds (my assumption about the accounting treatment). Each quarter's move in Anthropic's stock would then flow into Alphabet's and Amazon's other income, and into Microsoft's to the extent its stake is held as equity securities. Strip these out when comparing operating trends; GAAP and Street EPS will swing with \$ANT.
- ## Open Questions
	- What makes up the roughly \$11B of non-fair-value add-backs between GAAP net loss and the \$2.7B adjusted net income?
	- Which instruments convert at the IPO, on what terms, and how large is the H2 2026 fair-value charge up to conversion?
	- After the IPO, how do Alphabet and Amazon classify their stakes, and will analysts keep the marks in Street earnings?
