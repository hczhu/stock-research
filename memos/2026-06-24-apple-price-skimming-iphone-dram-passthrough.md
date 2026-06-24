- tags:: [[$AAPL]], [[Apple]], [[iPhone]], [[pricing]], [[price-skimming]], [[DRAM]], [[services]], [[market-share]], [[consumer-electronics]], [[AI]], [[Siri]], [[EU-regulation]], [[$NVDA]]

- **Source**: Stratechery (Ben Thompson), June 2026. Covers Apple price increases (WSJ Tim Cook interview), memory cost chronology, and Siri AI EU exclusion.

- ## Apple Has Already Skimmed the Richest Buyers — Memory Price Increases Pass Through

	- The argument that Apple should absorb DRAM/memory cost increases to make a play for market share misunderstands who Apple's remaining addressable customers are.

- ## The Price Skimming Insight

	- Apple has already captured the most price-insensitive smartphone buyers. By definition, the customers Apple has **not yet captured** are more price-sensitive — and price-sensitive customers are less profitable across **every revenue vector simultaneously**:
		- Lower ASP on hardware (the whole premise of the "eat the cost" argument)
		- Lower likelihood to pay for App Store subscriptions
		- Lower Services ARPU broadly
	- The implication: the marginal customer Apple would gain by cutting effective iPhone prices is worth **less** than Apple's current customer base on both hardware margin and Services margin. The trade is doubly bad, not neutral on one axis.

- ## "Not Raising Prices" ≠ Market Share Gains

	- The assumed mechanism — Apple holds prices flat as memory costs rise → iPhones become relatively cheaper → price-sensitive buyers switch from Android — does not hold:
		- Price-sensitive buyers considering a \$400 Android phone are not going to buy a \$1,000 iPhone because it's \$50 cheaper than it otherwise would have been. The gap remains enormous.
		- What actually happens when cost increases are not passed through: **existing marginal customers simply delay upgrades**. They do not represent new market share.
	- Not raising prices does not win customers; it bleeds margin from existing customers without a compensating volume gain.

- ## Correct Apple Strategy: Protect Margin, Grow via Differentiation

	- Apple's actual path to market share expansion is differentiation — features, ecosystem lock-in, brand — not price competition. This is consistent with Apple's 20-year track record: they have never competed on price and have grown share anyway.
	- Protecting margin also protects the Services flywheel: a wealthier, more engaged installed base pays more for App Store, Apple One, iCloud, and future AI services. Diluting that base with price-sensitive switchers would degrade the Services revenue quality simultaneously.

- ## The Services Narrative Enabled Years of Real-Term Price Decreases

	- Apple held nominal iPhone prices flat for years, which in inflation-adjusted terms meant **declining real prices**. The iPhone 17 Pro's 2025 starting price of \$1,099 equals \$892 in 2020 dollars — meaningfully below the actual \$999 starting price in 2020. Real prices across the lineup declined every year from 2020 to 2024:

	- | Price in 2020 \$ | 2020 | 2021 | 2022 | 2023 | 2024 | 2025 |
	  |---|---|---|---|---|---|---|
	  | 2-year-old iPhone | \$499 | \$477 | \$441 | \$422 | \$411 | N/A |
	  | 1-year-old iPhone | \$599 | \$572 | \$530 | \$507 | \$493 | \$568 |
	  | New iPhone | \$799 | \$763 | \$707 | \$676 | \$657 | \$649 |
	  | iPhone Pro | \$999 | \$954 | \$883 | \$846 | \$822 | \$892 |
	  | iPhone Pro Max | \$1,099 | \$1,050 | \$972 | \$1,015 | \$904 | \$973 |

	- The Services Narrative allowed Apple to sustain hardware margins while offering lower real prices — services revenue cross-subsidized the hardware pricing restraint. The AI-driven DRAM cost surge ends this era: **it's the AI narrative now, and this time it's outside Apple's control**.

- ## How Apple Got Caught: The Memory Cost Chronology

	- Tim Cook's Q earnings call laid out the progression explicitly:
		- **December quarter**: minimal memory impact
		- **March quarter**: higher memory costs, **partially offset by carry-in inventory**
		- **June quarter guidance**: "significantly higher" memory costs, also **partly offset by carry-in inventory**
		- **Beyond June**: "memory costs will drive an increasing impact on our business"
	- Apple's strategy was to absorb via carry-in inventory buffer and hope the situation resolved. It didn't. By June, Cook was giving emergency WSJ interviews. The implication: **Apple did not fully anticipate this memory cycle** and delayed the price increase decision until the buffer inventory ran out.
	- **TechInsights estimate**: passing through full memory cost increases to maintain margins would add approximately **\$270** to the next iPhone Pro model price.
	- One possible reason for Cook announcing imminently rather than waiting for September iPhone 18: taking the political blame himself so incoming CEO John Ternus doesn't have to open his first iPhone launch with a price increase.

- ## Memory Hits Apple Twice

	- Higher DRAM/NAND costs are a double hit for Apple specifically:
		- (1) **Direct cost**: every device shipped costs more to build
		- (2) **AI feature requirements**: Apple Intelligence requires more RAM. Devices with ≥12GB run all on-device models (including expressive voices, advanced dictation); devices with 8GB run only basic models. Apple needs to ship more memory per device to stay competitive on AI features — exactly when memory is most expensive.
	- This makes Apple uniquely exposed in the current cycle compared to non-AI-feature-dependent consumer electronics.

- ## Siri AI, EU Exclusion, and the Nvidia Privacy Connection

	- Apple is not launching **Siri AI** in the EU on iOS/iPadOS initially. The reason: the EU's DMA interpretation would require Apple to give any virtual assistant "nearly unlimited access" to user data and autonomous control across apps — including reading messages, making purchases, executing actions — without Apple's privacy safeguards. Apple views this as a security risk and refused.
	- Apple's Trusted System Agent proposal (an intermediary to allow third-party AIs safe access) and a phased 18-month rollout plan were both rejected by the European Commission.
	- **The Siri AI differentiator is precisely what the EU wants to ban**: Siri AI's value proposition is that it is the only AI with access to your personal on-device data. That integration is Apple's product promise — and the EU DMA, in Apple's reading, would force exposure of that data to every third-party AI simultaneously.
	- **Why Apple uses Nvidia for Siri AI's server-side models** (not Google TPUs):
		- Optionality: keeps the option to move workloads away from Google
		- More importantly: **Nvidia Grace Blackwell supports Confidential Computing at multi-node rack-scale**, extending trusted execution environments across an entire rack domain. Grace Hopper supported it only on a single-GPU-per-VM basis, which doesn't scale. Privacy requirements drove Apple back to Nvidia.

- ## Investment Implications (DRAM / Memory Passthrough)

	- This analysis supports the thesis that **Apple will pass through memory cost increases to end consumers** rather than absorb them. Apple has the brand and installed-base loyalty to do so without meaningful volume loss among its target customers.
	- For the DRAM super-cycle thesis: Apple's pricing discipline means memory price inflation flows through the supply chain to ASPs, sustaining DRAM maker revenue and margin through the upcycle. See [[DRAM-memory-ssd-index-thesis]].
	- The AI feature race (requiring more on-device RAM) structurally increases Apple's memory content per device independent of price — a secular unit volume tailwind for DRAM makers even before price increases.
