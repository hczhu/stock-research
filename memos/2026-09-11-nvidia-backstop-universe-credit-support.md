tags:: [[$NVDA]], [[semiconductor]], [[GPU]], [[data-center]], [[capex]], [[Neocloud]], [[debt]], [[OpenAI]], [[AI infrastructure]], [[Anthropic]], [[Lambda]], [[Nscale]], [[backstop]], [[residual value]], [[vendor-financing]], [[leases]], [[private-credit]], [[GPU-pricing]], [[Stratechery]], [[Ben-Thompson]], [[$GOOGL]], [[TPU]], [[CUDA]], [[bonds]], [[bubble]], [[Berkshire-Hathaway]]
file-created-at:: 2026-09-11
file-updated-at:: 2026-11-14

- ## Nvidia's Backstop Universe - Credit Support as a Distribution Strategy
	- **Source**: Daniel Nishball, Oliver Kennon, and Terence Ong, SemiAnalysis, "Nvidia's Backstop Universe - Heads I Win, Tails Who Loses?", September 11, 2026; user-provided PDF. Chart and table figures added Nov 14, 2026 from a second copy of the same PDF.
	- **Second source**: Ben Thompson, Stratechery, "Nvidia's Risky Business," August 11, 2026 (user-provided PDF), written the day after Jensen Huang announced the \$500B capital partnership. See the "Stratechery: why this is a risky business" section.
	- **Thesis**: Nvidia is turning its balance sheet and AA credit into a distribution tool: guarantees, lease commitments, and rental floors let non-investment-grade operators finance Nvidia clusters at lower rates. The structure can expand the buyer base and lock scarce powered sites to Nvidia while demand is strong, but it creates a correlated contingent liability if Nvidia loses accelerator leadership and supported projects become uncompetitive at the same time its own earnings weaken.
	- Related: [[2026-09-03-economist-nvidia-central-bank-of-ai-vendor-financing]], [[2026-06-11-nvidia-coreweave-nebius-circular-financing]], [[2026-11-13-spheron-inference-chips-asic-vs-gpu-design-tradeoffs]].

- ## Why Nvidia Is Doing This
	- SemiAnalysis's explanation: the Gigascalers (Amazon, Microsoft, Google, Meta, Oracle) have controlled access to the investment-grade capital the buildout runs on. They profit from the spread between the long-term offtake price they pay and the spot or short-term price they resell at, plus services on top.
	- Nvidia is creating alternative credit anchors so Neoclouds and Neolabs can raise money without the Gigascalers. SemiAnalysis's datacenter team reads the goal as **twenty buyers at scale rather than four**.
	- Others run the same playbook: the report cites **Google at \$75.5B of guarantees** and **Meta at \$59.0B of obligations**.
	- The report says investors focus on Nvidia's program because it is new and because of "Cisco PTSD," even though the Gigascalers' implicit backstops are much larger.

- ## The Obligation Stack Has Expanded Rapidly
	- The report says Nvidia disclosed **\$530B of gross off-balance-sheet commitments in 2Q F1/27**, up from **\$184B one quarter earlier**. Its detailed stress table, however, totals the six disclosed categories at **\$497.5B**; the definitional difference is not reconciled in the report.
		- The quarter's jump came from three items: supply and capacity commitments rose from **\$119B to \$279B** (mainly memory), guarantees and LPS guarantees rose from **\$3.5B to \$108.5B** (PORTS-Pike), and two new lines appeared (\$36B AI cloud agreements and \$20B leases for reassignment).
	- | Commitment category | Current amount | Purpose / economic exposure |
	  |---|---:|---|
	  | Supply and capacity commitments | \$279B | Primarily memory and upstream capacity; 96% is due by F1/29 |
	  | Guarantees and land, power, shell guarantees | \$108.5B | Uses Nvidia credit to make data-center leases financeable |
	  | AI Cloud Partner agreements | \$36B | Six-year take-or-pay rental floors for Neocloud GPU capacity |
	  | Third-party reassignment leases | \$20B | Nvidia signs as tenant, then assigns operating use to a Neocloud |
	  | Cloud service agreements | \$29B | Mostly Nvidia's own model-development and CI/CD compute, including a \$6.3B CoreWeave agreement through 2032 |
	  | Own-use data-center leases not commenced | \$25B | Future sites Nvidia expects to occupy itself |
	  | **Detailed-table total** | **\$497.5B** | More than 5x on-balance-sheet liabilities of \$91B |
	- Nvidia also had **\$33.4B of debt** (including \$25B of senior notes issued in the latest quarter), **\$22B of cash** (up from \$12B a few quarters earlier), and a **\$128B investment book** at 2Q F1/27. The investment book rose from \$45B a year earlier, generated \$23.7B of first-half gains, and has another \$25B committed.
	- **SemiAnalysis's forecast of each line (\$B, fiscal year-end)**. This is the authors' "how far could Nvidia go" case, not a base case. It starts F1/27 at \$589B, above the \$497.5B filed, because it adds a new residual-value line and assumes more deals close before year-end.
	- | Line | F1/27 | F1/28 | F1/29 | F1/30 | F1/31 |
	  |---|---:|---:|---:|---:|---:|
	  | AI Cloud Agreements (AICP) | 51.0 | 95.7 | 143.0 | 193.6 | 248.4 |
	  | Leases for third-party reassignment | 19.6 | 89.3 | 92.9 | 121.2 | 133.3 |
	  | Datacenter and LPS guarantees | 108.2 | 110.9 | 172.3 | 261.5 | 338.2 |
	  | Capital partnership residual value guarantees | 55.2 | 137.9 | 223.9 | 303.3 | 372.8 |
	  | Cloud service agreements | 38.0 | 48.0 | 62.0 | 77.4 | 95.7 |
	  | Own-use leases not commenced | 25.0 | 30.0 | 36.0 | 43.2 | 51.8 |
	  | Supply and capacity commitments | 292.6 | 404.0 | 517.4 | 656.7 | 827.2 |
	  | **Total** | **589.5** | **915.7** | **1,247.4** | **1,657.0** | **2,067** |
	- **Cloud service agreements history**: \$1.6B when first disclosed in 3Q F1/23, about \$11B by 1Q F1/26, \$26B in 3Q F1/26, then \$29B. Beyond the \$6.3B CoreWeave deal, SemiAnalysis attributes part of the balance to about 360 MW in Batam (Indonesia) via Oracle, about 20 MW at YTL in Malaysia, 10-20k GPUs rented from CoreWeave, and some US Oracle sites. Nvidia sometimes rents this capacity out.

- ## Backstops Convert Nvidia Credit Into GPU Demand
	- **AI Cloud Partner (AICP)**: Nvidia provides a six-year rental floor averaging about **\$2.35 per GB300 GPU-hour**, versus the report's **\$4.50-\$4.60** range for five-year market contracts. The Neocloud pays Nvidia 50% of revenue above the floor, so Nvidia receives upside if third-party rentals remain strong while lenders underwrite against Nvidia's downside floor.
		- Announced or estimated obligations include Firmus Batam at **360 MW / \$21.1B**, SharonAI at **\$4.2B**, and GMI at an estimated **\$2.2B**. SemiAnalysis says Nvidia paused new AICP deals shortly before publication.
		- The Neocloud sells compute to AI Natives and other tenants on short-term contracts and can rent to Nvidia whenever those contracts fall through. SemiAnalysis expects deals signed before the pause to take the line to **\$51B at F1/27** year-end.
		- The report's AICP diagram labels the floor "**~\$3.25 on avg**," which conflicts with the \$2.35 in the text. The report doesn't explain the difference; it may be a different GPU or an older version of the diagram.
	- **Capital partnership residual-value guarantees**: Nvidia has proposed guaranteeing up to **25%** of project residual value while institutional capital bears the remaining risk. SemiAnalysis estimates this can support capacity with about **\$9.4B of Nvidia obligation per GW**, versus **\$25B/GW** for PORTS-Pike and **\$59B/GW** for AICP, but it does not solve the data-center lease leg.
		- Announced in August 2026 as a program with private equity funds to mobilize **over \$500B** of third-party capital. Jensen Huang said support would be limited and decided project by project. SemiAnalysis assumes an aspirational **\$2.5T** of funding through F1/31.
		- SemiAnalysis models it on the Google-Broadcom-Anthropic-Apollo TPU structure. There, Broadcom's residual value guarantee makes the TPU SPV's noteholders whole after an equipment sale, and Google backstops rent to the datacenter operators. Nvidia's version is thinner: a 25% guarantee and nothing on the datacenter.
		- **SemiAnalysis's illustrative 1 GW Vera Rubin NVL72 cluster**:
			- | Item | Value |
			  |---|---|
			  | All-in capex | \$43.5B for about 306k GPUs |
			  | Offtake | AI lab pays **\$6.80/hr per GPU** on a 5-year lease |
			  | A-1 notes (banks) | About \$7.5B at Treasuries + 100-200 bp |
			  | A-2 notes | About \$30B at 6-7% |
			  | B notes (no guarantee) | About \$4.5B at 9%+ |
			  | Sponsor equity | About \$1B, from one of Apollo, BlackRock, Blackstone, Brookfield, GS or KKR |
			  | Nvidia | Makes whole up to 25% of any residual value shortfall |
			  | Insurer | Athene or a similar affiliate gives a 15% limited guarantee of Nvidia's make-whole |
			- The Neocloud operates the cluster for a fixed fee. Equity and mezzanine take first loss, Nvidia's 25% sits above them and below the senior lenders, and that cushion is meant to make the senior tranche safe enough for banks.
	- **Lease reassignment**: Nvidia signs as the investment-grade tenant so a developer can finance construction, then transfers operating use to a Neocloud while likely remaining the primary obligor until the project deleverages.
		- Hut 8 financed the first 352 MW Beacon Point building with **\$4.25B of 6.129% Baa2 senior secured notes**. Two 352 MW, 15-year Beacon Point leases total **\$19.6B**, while Lambda's offtake covers only the first six years; Nvidia retains years 7-15 to re-tenant or use.
		- **The Nvidia-Anthropic-Lambda-Hut 8 chain** (SemiAnalysis diagram):
			- | Link | Terms |
			  |---|---|
			  | Anthropic → Lambda | **\$5.80/hr** rental, 6-year Vera Rubin NVL72 compute deal, about 115k GPUs |
			  | Lambda → Nvidia | 10% revenue share; about \$125/kW/month in year 1 for the colocation lease reassigned from Nvidia |
			  | Hut 8 | \$10M/MW capex; datacenter debt raised at 95% loan-to-cost |
			  | Lambda's lenders | About \$13B lent at about 80% loan-to-cost |
		- SemiAnalysis's view: lenders who bought Baa2 paper on an AA tenant won't accept a B-rated one, so Nvidia likely stays primary obligor until the project deleverages or clears a debt-service-coverage test. It calls the 15-year lease against a 6-year offtake optionality, not a mismatch: at year six Nvidia can re-tenant with new GPUs or let the operator keep running old hardware at spot prices. Both paths are worth more while grid interconnection queues run four to seven years.
	- **Land, power, and shell guarantees**: Nvidia guarantees the landlord rather than the GPU renter, directly addressing the hardest-to-finance part of the stack.
		- PORTS-Pike adds a **\$105B cap** for 4.25 GW of 20-year leases to an OpenAI affiliate, with exposure phasing in as buildings become ready from fiscal 2029 and ending if OpenAI achieves an acceptable credit rating.
		- Nvidia can support another 3.8 GW; exercising the option on similar terms would add about **\$93B** and bring the campus guarantee near **\$200B**. Nvidia estimates the site could generate **\$150B-\$200B of revenue per hardware generation**.
		- **PORTS-Pike structure**:
			- SB Energy develops a roughly 8 GW campus through 17 building-level landlord subsidiaries. Each has its own 20-year triple-net lease with an OpenAI affiliate. The land is a Department of Energy ground lease. The site will host only Nvidia infrastructure.
			- The diagram dates the first 800 MW to 2028, notes more than \$6B of collateral letters of credit, and shows power from 9.2 GW of SoftBank-affiliate gas generation through PJM and AEP Ohio, with about \$5.1B of grid capex.
			- OpenAI compensates Nvidia for the guarantee and reimburses it if the guarantee is called; the fee terms aren't public. If Nvidia passes on phase two, OpenAI must find a guarantor rated A- or better.
			- Nvidia is investing \$3B in SB Energy (\$1.5B conditional on its IPO), and OpenAI receives SB Energy warrants.
			- On gross exposure, the guarantee costs about **\$24.7M per MW**, versus about **\$58.6M per MW** for AICP.
		- **Ionic Digital / Nscale**: Ionic Digital's S-1 shows Nscale on a 126-month triple-net lease for 234 MW in Ward County. Nvidia guarantees the first five years of rent up to **\$860.3M** and takes \$60M of Nscale warrants; Nscale's parent guarantees from year six. About \$2.6B of the prior quarter's \$3.5B has no named deal.
		- SemiAnalysis's backstop count: PORTS-Pike 4.25 GW, an unnamed second frontier lab (Anthropic inferred) 2.00 GW with undisclosed credit enhancement, and Nscale 0.23 GW. That totals **6.48 GW**, with \$105.86B of disclosed caps.

- ## Nvidia's Direct Datacenter Leases
	- About 1.2 GW signed in 2026 so far. With older leases, Nvidia is a tenant on about 1.5 GW. Only the Hut 8 leases are for reassignment; the rest are for Nvidia's own use.
	- | Landlord | Site | MW | Ready | Term | Commitment | Use |
	  |---|---|---:|---|---|---:|---|
	  | Hut 8 | Beacon Point Bldg 1, Calallen TX | 352 | 3Q27 | 15 yr, 3% escalator | \$9.80B | Reassignment |
	  | Hut 8 | Beacon Point Bldg 2, Calallen TX | 352 | 2Q28 | 15 yr, 3% escalator | \$9.80B | Reassignment |
	  | Tract (Fleet Datacenters) | McCarran NV | 400 | 4Q27-2Q28 | 197 months | \$12.00B | Own use |
	  | Vantage | McCarran NV | 224 | 2027-2030 | n.a. | \$6.72B | Own use |
	  | Digital Realty | Manassas VA | 96 | Live, full 2027 | n.a. | \$2.88B | Own use |
	  | Mega Data Centres | Ein HaEmek, Israel | 64 | 2Q27 | n.a. | \$1.92B | Own use |
	  | Aligned | Hillsboro OR | 36 | 2026 | n.a. | \$1.08B | Own use |
	  | **Total** | | **1,524** | | | **\$44.20B** | |
	- The \$44.2B total roughly matches the \$45B filed (\$20B reassignment plus \$25B own use). SemiAnalysis values the own-use leases at about \$30M per MW.

- ## Scale: Material to Nvidia's Channel, Still Minor to the Industry
	- SemiAnalysis counts **about 6.5 GW** under current Nvidia backstops, most not yet built. This is just under **3%** of the report's projected **240 GW** increase in global AI IT capacity from year-end 2025 through 2030.
		- Net additions by year in the SemiAnalysis model: CY2026 **19.3 GW**, CY2027 **35.8 GW**, CY2028 **40.7 GW**, CY2029 **63.3 GW**, CY2030 **79.2 GW**, for **238.3 GW** in total.
		- The report puts cumulative global AI IT and datacenter capex at about **\$11T** from CY24 through CY29; its chart is titled 2024-2030 and labeled "~\$10.7T." The year labels are cut off in the PDF, and the visible bars add up to more than the label, so treat the total as approximate.
	- That 6.5 GW equates to roughly **2.5M-3.0M GB300-equivalent GPUs**, or 25-35% of forecast CY2027 Nvidia shipments. Spread evenly over five years, it becomes about **0.6M GPUs annually**, less than 10% of the CY2027 shipment forecast.
	- The Gigascalers remain the larger credit anchors: the report expects Microsoft, Meta, Amazon, Oracle, and Google to lease about **39 GW of third-party capacity by 2028**, versus Nvidia's roughly **1.5 GW** of third-party and own-use leases signed to date.
	- SemiAnalysis's expansion case reaches **46.6 GW** of Nvidia-supported capacity, still below 20% of planned AI capacity additions through 2030. Of that, 28.2 GW uses only a 25% residual-value guarantee rather than a full revenue or lease backstop.
		- | Program (commitments through F1/29) | Obligation (\$B) | \$B per GW | GW |
		  |---|---:|---:|---:|
		  | Capital partnership residual value guarantees | 264.7 | 9.4 | 28.2 |
		  | AI Cloud Agreements | 170.6 | 58.6 | 2.9 |
		  | Beacon Point leases | 19.6 | 27.8 | 0.7 |
		  | New third-party lease program | 172.4 | 30.0 | 5.8 |
		  | PORTS-Pike initial commitment | 105.0 | 24.7 | 4.3 |
		  | New direct LPS guarantees (includes a 2 GW lab campus) | 94.7 | 24.7 | 3.8 |
		  | Existing partner lease guarantees | 3.5 | 3.7 | 1.0 |
		  | **Total** | | | **46.6** |
		- Several instruments can support the same project, so the GW figures may double-count. The report treats them as an upper bound.
	- SemiAnalysis sees the programs as temporary: backstopped projects give operators a track record so customer revenue and independent capital can fund later expansion.

- ## Economics Are Asymmetric Until Leadership Breaks
	- In the favorable case, Nvidia books the GPU sale at full margin, receives revenue share above AICP floors, and locks scarce power and campuses to its architecture. Its credit support also creates more scaled buyers, reducing strategic dependence on four Gigascalers that are developing custom accelerators.
	- The support can preserve Neocloud solvency in a demand slowdown because rental floors are set to cover amortizing debt. It protects lenders and can prevent forced asset sales, but shifts some utilization and lease risk back to Nvidia.
	- The report argues a normal demand air pocket is absorbable because Nvidia retains the GPU margin and cash generation while the obligation is long-dated. Its modeled F1/27 funded debt of **\$36B** sits against **\$204B of EBITDA**, producing net debt / EBITDA of **negative 0.2x** before contingent obligations.
		- Net debt / EBITDA falls to **-1.7x by F1/31** because cash builds faster than debt. Credit analysts the authors spoke with put downgrade territory at about **1.5x**, and off-balance-sheet obligations currently don't count as leverage.
	- SemiAnalysis's severe but highly assumption-dependent test treats all forecast obligations as immediately due. The ratio of net debt plus obligations to EBITDA is **2.68x in F1/27**, falling to **1.41x by F1/31** as earnings and cash compound.
		- The path in between is 1.96x (F1/28), 1.79x (F1/29) and 1.67x (F1/30).
	- The model assumes roughly **\$441B of EBIT in F1/28**, cash reaching **\$1.4T by F1/31**, and off-balance-sheet obligations growing to about **\$2.1T**. Under a stable-asset test that haircuts receivables by 30% and securities by 80%, coverage of the growing obligation stack rises from **0.09x to 0.57x**, or **0.70x** if shareholder payouts are suspended for a year.
		- If obligations stay at today's level instead of growing, stable net worth covers **0.11x in F1/27**, passes **1.0x in F1/29**, and reaches **2.35x in F1/31**.
		- With a year of payouts suspended, coverage runs 0.23x, 0.42x, 0.54x, 0.61x and 0.70x from F1/27 to F1/31.
		- Payouts are a cushion: Nvidia returned nearly **\$26B** to shareholders in one quarter, which SemiAnalysis calls a **\$300B lever over three years**.
	- Those outputs demonstrate capacity under the authors' earnings path, not contractual maximum loss or a downturn forecast; the conclusion is most sensitive to Nvidia's future cash generation and how much of each gross commitment is actually called.
	- SemiAnalysis says the direct marginal cost of a guarantee in the base case is zero because the tenant pays (and at PORTS-Pike, OpenAI also indemnifies Nvidia), and it argues Nvidia should offer more support.

- ## Concentration and the True Failure Mode
	- OpenAI represents **97% of Nvidia's current guarantee cap**, while the report says two frontier labs are the ultimate payers behind almost every rental floor, lease, and guarantee. Diversifying across Neocloud borrowers therefore does not diversify end-demand risk.
	- A cyclical slowdown alone need not impair Nvidia: obligations mature over as long as 20 years, replacement tenants and asset sales reduce claims, and Nvidia can suspend buybacks and dividends.
	- The damaging case is a **competitive accelerator transition**, not simply lower AI demand. If a rival chip becomes more productive, Nvidia may need to cut price to defend share just as Nvidia-backed clusters lose competitiveness and guarantees are called. EBITDA, collateral values, and obligation performance would then deteriorate together.
	- Backstops amplify that competitive loss rather than cause it. Their strategic logic is strongest while Nvidia leads and power is scarce: securing the powered site can bind the campus to Nvidia for multiple hardware generations, but the benefit erodes quickly if the architecture no longer sets the performance-per-dollar frontier.

- ## Stratechery: why this is a risky business
	- **Thompson's thesis**: the AI buildout has moved past funding from free cash flow, into debt, and now into equity and safety-seeking institutional capital. Nvidia's \$500B partnership protects its margins by finding new capital willing to take risk, but its guarantee works as a price cut forced by cheaper TPUs and Trainium, and the risk now sits in places that aren't marked to market. ^^**"AI better deliver before it's too late."**^^
	- **The 1873 analogy**
		- In 1870 Jay Cooke agreed to sell Northern Pacific's bonds. Northern Pacific lacked the federal guarantees behind the Union Pacific and Central Pacific, and banks wouldn't buy its bonds. Cooke got a 12% commission plus \$200 of stock per \$1,000 of bonds sold, and turned retail investors into the main funding source using 1,500 salespeople and 1,300 newspapers that Cooke paid.
		- Northern Pacific's capital needs never ended. Cooke covered the gaps between bond sales with deposits at Cooke's own bank. When credit tightened in September 1873 (the Vienna crash and the demonetization of silver), there were no more buyers. The failure of Jay Cooke & Company set off the Panic of 1873, a wave of railroad bankruptcies, a multi-year depression and decades of deflation.
		- Liaquat Ahamed's book *1873* scales 1870s sums by about 1,200x: the \$500M a year that went into US railway bonds then equals about **\$600B** today, roughly Big Tech's projected 2026 capex. Satya Nadella called it "the book to be read" on Microsoft's earnings call.
		- Thompson's lesson: the upside Cooke got was huge because the deal was very risky, and new funding mechanisms only spread the losses more widely when it failed.
	- **Stage 1 to 2: from cash flow to debt**
		- A year earlier, nearly all of Big Tech could say its capex wasn't funded by debt, the usual argument against a bubble. Microsoft is now the only hyperscaler that still can, with **\$19.6B** of free cash flow last quarter.
		- | Measure | Value |
		  |---|---|
		  | Debt raised by Oracle, Meta, Alphabet and Amazon, Sep-Nov 2025 | \$80B |
		  | Same four, all of 2025 | \$108B |
		  | Same four, 2026 through July 7 | **\$194B** |
		  | 2026 bonds trading at higher yields than at issuance | 86% |
		  | Order book cover on recent deals | Below 2x, down from 5x in February |
	- **Stage 3: equity**. In early June Google announced an **\$85B** equity raise, including \$10B from Berkshire Hathaway.
		- Thompson's reading: if compute is scarce, whoever brings the most cash gets the most compute, and that advantage compounds. Google can earn from all of it: Services, Gemini, and selling capacity to the frontier labs. TPUs give that capacity a lasting cost advantage, so if compute becomes a commodity, Google is the hyperscaler set to make the most absolute profit, even at lower margins.
		- Berkshire is replaying the See's Candies → BNSF model, with Berkshire's \$373B of cash as See's and Google as the capital-hungry railroad.
		- DeepMind's leadership turmoil ([[2026-08-06-semianalysis-gemini-cooked-gcp-cooking]]) arguably helps that bet, because compute shifts from Gemini to Google Cloud. Cloud grew **82%** year over year at a **36%** margin, and Pichai described a short-term "bridge deal" renting third-party capacity for a very large customer, almost certainly Anthropic.
		- SemiAnalysis: more than **20% of TPU shipments from 3Q26 to 4Q27** go directly to Anthropic, on top of the hundreds of thousands of TPUs GCP already rents to it and many more committed to Anthropic and Meta.
	- **Why the backstop is a price cut**
		- Thompson: TPUs are likely cheaper than Nvidia GPUs. By buying TPUs for its own data centers, Anthropic turns compute from a marginal cost into a capital cost, which suggests TPUs are cheaper over their life.
		- If capital is the constraint on new data centers, a lower upfront price can matter more than token efficiency, even if Nvidia's chips are better.
		- Nvidia's up-to-25% residual-value guarantee lowers the cost of capital for anyone building with Nvidia chips by putting Nvidia's profits at risk. Thompson calls it "in a certain sense, a price cut," a response to Google's (and soon Amazon's) aggressiveness.
		- The guarantee also suggests Huang believes the "investable asset class" pitch much more than the market does.
	- **Huang's pitch, from an X article**
		- Partners are Apollo, BlackRock, Blackstone, Brookfield, Goldman Sachs and KKR, with "over \$500 billion" to mobilize. "In AI, compute is revenue."
		- Huang argues Nvidia-based AI factories make an investable asset because they "produce revenue, serve a broad market, improve in performance over time and can be redeployed." Fungibility protects residual value, and CUDA keeps improving the installed base.
		- Thompson's contrast with Google: Google's equity raise dilutes shareholders' upside without adding risk to the company. Nvidia's structure keeps its margins by finding outside capital to carry the risk, while keeping part of that risk through the guarantee.
	- **The CUDA moat is weakening where it matters most**
		- Thompson in 2024: AI use cases now sit above CUDA, on top of models. Combined with strong incentives to find cheaper chips, that makes escaping CUDA more feasible than ever, though still far off for low-level work and training.
		- Now Anthropic and OpenAI seem to be pulling away. Anthropic hasn't depended on CUDA for years, and OpenAI is moving off it, at least for inference. If they win, Nvidia's profits get squeezed, and Thompson argues the backstop shows they already are. That is also why Huang's first X post was an open letter defending open models.
	- **The danger zone**
		- If AI revenue takes off, debt markets reopen and companies go back to funding capex from free cash flow, and the backstop may cost Nvidia nothing.
		- But right now hyperscalers are exhausting the debt markets and Google has started issuing equity. Nvidia's partners draw on insurance floats, pension funds and other long-term liabilities. Thompson calls that risk "unmarked, unlike equity" and "considerably higher."
		- "It's one thing to spend all of your free cash flow; it's another thing to tap the debt markets. And, beyond that, it's a completely new nerve-racking thing to bring safety-seeking assets to bear."

- ## My notes
	- **The deal terms give a ladder of GPU rental prices.** The GB300 floor is \$2.35/hr, five-year GB300 market contracts are \$4.50-\$4.60, Anthropic pays Lambda \$5.80/hr for Vera Rubin NVL72, and the illustrative capital-partnership cluster assumes an AI lab pays \$6.80/hr for Vera Rubin. That fits Spheron's November data showing Blackwell on-demand prices rising while H100 fell ([[2026-11-13-spheron-inference-chips-asic-vs-gpu-design-tradeoffs]]). The newest generation earns roughly 2.5-3x the floor Nvidia is willing to guarantee.
	- **The Lambda numbers match the Economist's \$35bn.** \$5.80/hr × 115k GPUs × 8,760 hours × 6 years ≈ \$35B (my math), the size the Economist reported for Anthropic's Lambda deal ([[2026-09-03-economist-nvidia-central-bank-of-ai-vendor-financing]]).
	- **The illustrative cluster pays back about twice.** \$6.80/hr × 306k GPUs × 8,760 hours ≈ \$18B a year, or about \$91B over the 5-year lease, against \$43.5B of capex and \$42.5B of notes (my math). That margin is why a 25% residual guarantee is enough. It is also why a lab paying below \$4/hr would make the structure much thinner.
	- **The model's earnings figures don't reconcile.** The stress table shows net income above EBITDA (\$238B vs \$204B in F1/27, \$409B vs \$351B in F1/28), and the text cites \$441B of consensus EBIT for F1/28, which is above the table's EBITDA. A reader comment raised the net-income point and got no answer in the PDF. If EBITDA is understated, the leverage ratios are conservative; if net income is overstated, the cash build and coverage ratios are too generous.
	- **The \$530B headline overstates the backstop risk.** More than half (\$279B) is supply commitments, mostly memory purchases Nvidia would make anyway. The truly contingent lines (guarantees, AICP, reassignment leases) total about \$165B today, and PORTS-Pike alone is \$105B of that.
	- **SemiAnalysis and Thompson define the risk differently.** SemiAnalysis asks whether Nvidia can pay, and finds it can under its earnings path. Thompson asks who gets hurt when the cycle turns, and points to pension and insurance money whose losses aren't marked until late. Both can be right: Nvidia's balance sheet can survive while the losses spread through private credit, just as Cooke's buyers carried Northern Pacific's.
	- **Thompson argues the SemiAnalysis failure mode has already begun.** SemiAnalysis says the damaging case is a rival chip taking the lead, which it treats as a future scenario. Thompson's evidence that it's underway: Anthropic is off CUDA, OpenAI is moving off it for inference, Anthropic is buying TPUs outright, and over 20% of 3Q26-4Q27 TPU shipments go to Anthropic. On that reading, the guarantee is margin given up today, not a free option.
	- **Concentration links the two pieces.** The labs Thompson says are leaving CUDA, Anthropic and OpenAI, are the same two SemiAnalysis names as the end payers behind almost every Nvidia floor, lease and guarantee. OpenAI is 97% of the guarantee cap, and Anthropic sits at the end of the Lambda/Hut 8 chain. Nvidia is backstopping demand from the customers best placed to leave it.
	- **The rental price is the shared signal.** Thompson's "danger zone" ends if AI revenue proves out and debt markets reopen. Until then, the cleanest live gauge is GPU rental prices against the floors: \$2.35 for GB300 under AICP and about \$2.80/hr for H100 one-year contracts ([[2026-09-03-economist-nvidia-central-bank-of-ai-vendor-financing]]). Blackwell prices rising into November ([[2026-11-13-spheron-inference-chips-asic-vs-gpu-design-tradeoffs]]) argues the floors aren't close to being tested yet.
	- **Possible leadership change**: the Stratechery page's sidebar, printed in November, lists episodes titled "Jensen Huang Likely Out at Nvidia" (Nov 11) and "Nvidia After Jensen Huang" (Nov 12-13). Both came after this post, and the repo has no memo on them. The capital partnership and the "investable asset class" pitch are Huang's, so a CEO change would raise questions about whether the program continues. Unverified here.
