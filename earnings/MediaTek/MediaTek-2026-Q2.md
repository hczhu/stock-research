tags:: [[MediaTek]], [[$2454.TW]], [[earnings]], [[ASIC]], [[AI-accelerators]], [[custom-silicon]], [[data-center]], [[SerDes]], [[CPC]], [[CPO]], [[D2D]], [[3.5D-packaging]], [[EMIB-T]], [[$INTC]], [[$TSM]], [[advanced-packaging]], [[NVLink-Fusion]], [[HBM]], [[$AVGO]], [[$GOOGL]], [[edge-AI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-12
file-updated-at:: 2026-11-12

- ## MediaTek 2Q26 Earnings — AI ASIC Share Target Raised; 448G SerDes Taping Out
- **Source**: MediaTek 2Q26 earnings call transcript (July 31, 2026; CEO Rick Tsai, CFO David Ku), 2Q26 press release, and investor-conference slides. Dollar figures are converted from NT\$ at the quarter's average rate of **NT\$31.60/US\$** (1Q26: 31.62; 2Q25: 30.88).
- **Related**: [[MediaTek-2026-Q1]] · [[MediaTek-2026-Q3]] · [[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]] · [[2026-08-31-nvidia-mediatek-convertible-nvlink-fusion]] · [[2026-11-02-mediatek-emib-yield-tsmc-backstop-second-asic-customer]]
- **Thesis**: The quarter itself was flat: revenue was \$4.82B (+2% QoQ, −1% YoY in US\$) and operating margin was 15.0%. All of the news was in data center. MediaTek raised its 2027 AI-accelerator share target to **15–20% of an \$80B market (\$12–16B)**. It now expects data-center revenue **above \$2B in 2026** and called the second ASIC (EMIB-T) on track for early 2028. It also added two pieces aimed at systems rather than chips: **448G SerDes is taping out** and a **pre-validated subsystem / rack design** that includes NVLink Fusion. The Board approved a **\$5B discretionary financing budget** to secure supply.

- ## ★ Highlight — Data Center / AI ASIC
	- > "Through close partnership with a major US CSP customer, we have successfully built our first AI accelerator ASIC with leading performance. Production of this product is scheduled to begin in the fourth quarter of this year. We expect our data center revenue to exceed 2 billion US dollars in 2026 and will continue to scale substantially in 2027 … we now believe the 2027 SAM will be 80 billion US dollars, and we are raising our share target to 15% to 20% from 10% to 15% that we guided last quarter." — Rick Tsai
	- | Item | 2Q26 call | Implied / context |
	  |---|---|---|
	  | First AI ASIC (major US CSP; Google TPU) | Production starts **4Q26** | Shipments are almost all in 4Q |
	  | 2026 data-center revenue | **> \$2B** | 1Q call: ~\$2B in 4Q26 (raised from \$1B) |
	  | 2027 AI-accelerator SAM | **\$80B** | Accelerator only; **excludes HBM**, CPUs and switches |
	  | 2027 share target | **15–20%** (was 10–15%) | **\$12–16B**, or 62–83% of 2Q26 annualized revenue (~\$19.3B) |
	  | Second AI ASIC | Early-2028 high-volume production; tape-out on track | Uses Intel EMIB-T packaging |
	  | 2028 | SAM "quite a bit higher" than 2027 | Both ASICs in production; share to rise "in a very significant manner" |
	- **First ASIC.** The CFO said supply is lined up for the 2026 and 2027 targets across foundry, substrate and memory. He said he is "very comfortable". Rick Tsai said there is strong demand for both 2027 and 2028 and that MediaTek will try to "fulfill any and all the demand".
	- **Second ASIC.** This is "a much more powerful chip" in performance per TCO and per watt. MediaTek is co-designing it with the customer, drawing on what both sides learned from the first chip. On packaging, MediaTek is "working on all those down to the operation details" with the supplier: yield, capacity and cycle time.
		- **EMIB-T.** A UBS analyst asked whether MediaTek's upbeat tone and Unimicron's comments that week meant EMIB-T yield and maturity were on track for 2028. Rick Tsai answered, *"In short, yes you can."*
		- **TSMC CoWoS as a backup.** The CFO noted that switching packaging technology "will take time". Given the positive results so far, the plan is still to ship on EMIB-T and start volume in 2028.
	- **More customers.** For the first time, MediaTek said it is "deepen[ing] our engagements with **several customers** for data center ASIC opportunities". It gave no names or tiers.
		- An analyst said the third-generation chip in the same family is in the RFQ stage. The CFO would not comment and said "let's focus on 2027 and 2028".
	- **Majority supplier?** Asked whether MediaTek could become this customer's main supplier, Rick Tsai declined to comment on the "reports in the market" and said only "hopefully better-than-fair share".
	- **Economics.**
		- Gross margin should be similar across ASIC generations and **slightly below** the corporate average.
		- Operating margin will be accretive "**meaningfully and sizably**" once volume scales.
		- Operating expense in dollars will rise slightly, while the opex ratio falls "substantially".
		- MediaTek will quantify the operating-margin accretion around the 3Q call.

- ## ★ Highlight — SerDes, Interconnect and System IP
	- > "Our development of 448G SerDes is progressing well, delivering best-in-class performance and power with our Co-Package Copper (CPC) system solution. Looking beyond 448G, we continue to develop CPO system solutions on TSMC's COUPE platform to enable next-generation system connectivity." — Rick Tsai
	- | Item | Status | Who said it |
	  |---|---|---|
	  | **448G SerDes** (analysts describe it as 2nm-based) | **Taping out on schedule** | CFO David Ku |
	  | 400G/448G SerDes IP ready for customers | "Sometime next year, maybe **second half of next year**" (2H27) | CEO Rick Tsai |
	  | Current-generation SerDes | "Middle-of-the-road SerDes now already well proven" | CEO |
	  | Die-to-die (D2D) IP | "At least equivalent industry-leading" in performance and power | CEO |
	  | Co-Packaged Copper (CPC) | System solution paired with 448G | Prepared remarks |
	  | Beyond 448G | "Most likely we need to go on the optical": **CPO on TSMC COUPE** | CFO and prepared remarks |
	  | 3.5D platform | End-to-end 3.5D IP, packaging and design flow for very large chips | Prepared remarks |
	- **Why the timing matters.** Tape-out now and customer-ready IP in 2H27 points to the next design cycle, the third-generation RFQ, rather than the second ASIC. A June report said MediaTek won the TPU v9 with a 336G SerDes after Broadcom's 448G effort stalled ([[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]]). If that is right, MediaTek's own 448G taping out on schedule lets it compete at 448G for the next socket.
	- **Beyond copper.** A Deutsche Bank analyst noted that MediaTek's "main competitor" (Broadcom) has not shown a copper roadmap past 448G. MediaTek's answer is the same: optics come next. So the competition beyond 448G will be decided in CPO, where MediaTek works with TSMC on COUPE.
	- **Moving from IP to subsystems.** The prepared remarks describe "pre-validated subsystems solutions for memory, I/O, and connectivity". In Q&A, Rick Tsai called it "similarly a rack design".
		- It combines MediaTek's SerDes, D2D and 3.5D packaging with **NVLink Fusion** connectivity.
		- It targets CSPs and enterprise customers. There is no revenue timeline yet.
		- In his words, MediaTek is moving from "very competitive IPs" to "integration of those IPs into a chassis format" for faster time to market.
	- **Other technologies.**
		- **HBM vs. LPDDR.** The CFO said HBM "is still a must" for top hyperscalers, rejecting a competitor's LPDDR-based alternative (HMC) for this segment.
		- **Investment areas.** Rick Tsai named memory-on-silicon, CPC and CPO as technologies "the whole industry needs" for next-generation accelerators, and MediaTek is hiring key talent for them.
	- **Supply chain.** MediaTek pitches itself as an orchestrator. It does design-technology co-optimization (DTCO) with TSMC on 2nm, builds very large dies on both CoWoS and EMIB-T, and secures memory and substrates for customers. It calls this "significant value beyond semiconductor".

- ## \$5B Financing Budget
	- The Board approved a **discretionary US\$5B financing budget** "to secure supply chain capacity and fuel our strategic expansion from AI ASIC chips to full-scale systems and platforms."
	- The CFO called it an option to be used "when we need it". MediaTek already holds "**\$7B plus**" of cash, and the budget sits on top of that.
		- He cited two reasons: supply-chain constraints and "the possibility for different AI ASIC business models".
		- Asked whether it could fund **suppliers' capacity expansion**, he answered "Yes, yes."
	- **What happened next.** In 3Q this became the **\$3.9B overseas convertible bond, with NVIDIA and Alphabet participating** (see [[MediaTek-2026-Q3]] and [[2026-08-31-nvidia-mediatek-convertible-nvlink-fusion]]).

- ## 2Q26 Financials (US\$)
	- | Metric | 2Q26 | 1Q26 | 2Q25 | QoQ | YoY |
	  |---|---|---|---|---|---|
	  | Revenue | \$4.82B | \$4.72B | \$4.87B | +2.1% | −1.1% |
	  | Gross profit | \$2.22B | \$2.18B | \$2.39B | | |
	  | Gross margin | 46.2% | 46.3% | 49.1% | −0.1pt | −2.9pt |
	  | R&D | \$1.25B (25.9%) | \$1.21B (25.7%) | \$1.20B (24.6%) | | |
	  | Selling + admin | \$0.26B (5.3%) | \$0.25B (5.2%) | \$0.25B (5.0%) | | |
	  | Operating income | \$0.72B | \$0.72B | \$0.95B | 0.0% | −23.9% |
	  | Operating margin | 15.0% | 15.3% | 19.5% | −0.3pt | −4.5pt |
	  | Non-TIFRS operating income | \$0.75B (15.6%) | \$0.75B (15.8%) | \$0.97B (19.9%) | | |
	  | Net income to parent | \$0.77B | \$0.76B | \$0.90B | | |
	  | EPS (NT\$ → US\$) | NT\$15.28 ≈ \$0.48 | NT\$15.17 ≈ \$0.48 | NT\$17.50 ≈ \$0.57 | | |
	- **Results vs. guidance.** Revenue was NT\$152.2B, above the top of the guidance range, driven by Smart Edge Platforms. Gross margin landed near the middle of the range.
	- **Margins.** The 2.9pt year-over-year drop in gross margin is mostly a **one-time benefit in 2Q25**. The 4.5pt drop in operating margin reflects that, plus R&D rising 6.6% YoY in NT\$.
	- **Below the operating line.** Non-operating income was \$0.16B (3.3% of revenue), mostly interest and dividends.
	- **SBC.** Share-based compensation was only **\$25M** (NT\$781M), compared with NT\$637M in 1Q.
	- **Currency.** Revenue rose 1.2% YoY in NT\$ but fell 1.1% in US\$ because the NT\$ strengthened to 31.60 from 30.88.

- ## Segment Revenue (2Q26)
	- | Segment | Share | ≈ US\$ | QoQ | YoY | 3Q26 guide (QoQ) |
	  |---|---|---|---|---|---|
	  | Mobile Phone | 41% | ~\$1.97B | −14% | −20% | Flat to down mid-single digits |
	  | Smart Edge Platforms | 53% | ~\$2.55B | +19% | +26% | Up mid-to-high single digits |
	  | Power IC | 6% | ~\$0.29B | +11% | +6% | Flattish |
	- **Mobile.**
		- Demand is weak because smartphone bill-of-materials costs are rising (memory).
		- MediaTek still expects global smartphone units to fall about **15%** in 2026.
		- The 2nm flagship SoC launches in 3Q, and flagship share should rise in 2027.
		- MediaTek is raising prices to pass costs through, not to expand margin. The CFO said the goal is to *maintain* gross margin, and price increases apply to all segments.
	- **Smart Edge Platforms.**
		- Gains came from share wins in connectivity, computing and automotive, plus DRAM content passed through in TV SoCs.
		- **RTX Spark**, built with NVIDIA, is a Windows PC for agentic AI that goes on sale for the 2026 holiday season. Rick Tsai called it validation of MediaTek's high-performance CPU system integration.
	- **Power IC.** Revenue grew on share gains in **computing and data center**.

- ## Balance Sheet and Cash Flow
	- **Cash and current financial assets** were NT\$198.4B (~\$6.3B at 31.6). The CFO cited "\$7B plus".
	- **Inventory** was NT\$98.4B (~\$3.1B), up **15% QoQ and 77% YoY**. Inventory days rose to **102**, from 87 last quarter and 66 a year ago.
	- **Receivables** were NT\$77.0B (~\$2.4B); receivable days rose to 47, from 43.
	- **Operating cash flow** was **+\$0.77B**, compared with −\$0.56B in 1Q26 and +\$1.48B in 2Q25. Investing cash flow was −\$0.62B.
	- **Intangible assets** rose NT\$9.9B (~\$0.31B) QoQ to NT\$97.5B, and other non-current assets rose NT\$11.1B. These look like IP and licensing spending for the data-center push; it wasn't explained on the call.
	- **Short-term loans** were NT\$17.1B (~\$0.54B).

- ## 3Q26 Guidance
	- | Item | Guide | ≈ US\$ (at 32.0) |
	  |---|---|---|
	  | Revenue | NT\$152.2–159.8B (flat to +5% QoQ; +7–12% YoY) | **\$4.76–4.99B** (midpoint \$4.88B) |
	  | Gross margin | 46% ± 1.5pt | |
	  | Opex ratio | 31% ± 2pt | Implies ~15% operating margin (~\$0.73B) |
	- **Full year.** MediaTek now expects the **high end** of its 2026 target of high-single-digit US\$ revenue growth. Full-year gross margin should stay inside the 3Q range.

- ## Hindsight (from the 3Q26 report)
	- 3Q26 revenue came in at **\$5.25B**, about 5% above the top of this guidance, with a 16.1% operating margin.
	- The 2026 data-center number rose from ">\$2B" to **~\$2.5B** (mostly 4Q).
	- The 2027 share target narrowed to the high end, **~20%** (about \$16B).
	- The \$5B budget was partly used for the **\$3.9B convertible** with NVIDIA and Alphabet.

- ## Takeaways
	- **Data center is the whole story.** The 2027 share target rose 5pt in one quarter, and the second ASIC and EMIB-T were described as on track. Each quarter has raised the numbers: 4Q26 went from \$1B to \$2B to >\$2B in 2026, and the share target went from 10–15% to 15–20%.
	- **MediaTek now has a SerDes roadmap of its own.** 448G is taping out, customer-ready IP is due in 2H27, and CPO on COUPE comes after that. This weakens the argument that MediaTek only wins on cost while Broadcom owns the I/O. The third-generation RFQ is where this will be tested.
	- **MediaTek wants to sell systems, not just ASIC services.** The subsystem/rack design with NVLink Fusion, the \$5B financing for supplier capacity, and the "different AI ASIC business models" remark all point to a bigger revenue share per socket, with more balance-sheet risk.
	- **The base business is weak.** Mobile is down 20% YoY, gross margin is pinned around 46%, and operating margin has fallen from 19.5% to 15.0%. Until the ASIC ramp shows up in 4Q26, results depend on Smart Edge share gains.

- ## Watch Items
	- **EMIB-T yields** for the second ASIC, and any sign MediaTek moves to TSMC CoWoS as a backstop.
	- **448G SerDes** silicon validation in 2H27, and whether it is designed into the third-generation socket.
	- **The "several customers"**: who they are, whether tier-1 or tier-2, and when they produce NRE or production revenue.
	- **Inventory** at 102 days: is it a deliberate pre-build or a buildup the business doesn't need?
	- **The operating-margin accretion** figure promised around the 3Q call.
