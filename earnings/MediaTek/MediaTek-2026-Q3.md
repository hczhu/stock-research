tags:: [[MediaTek]], [[$2454.TW]], [[earnings]], [[AI-accelerators]], [[ASIC]], [[custom-silicon]], [[data-center]], [[TPU]], [[$GOOGL]], [[$NVDA]], [[NVLink-Fusion]], [[UALink]], [[EMIB-T]], [[$INTC]], [[$TSM]], [[advanced-packaging]], [[SerDes]], [[CPO]], [[HBM]], [[$AVGO]], [[edge-AI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-12

- ## MediaTek 3Q26 Earnings — AI ASIC Ramp Begins, 2027 Aimed at ~\$16B
	- **Source** — MediaTek 3Q26 press release and earnings-call transcript (Oct 30, 2026). All NT$ figures converted to US$ at MediaTek's stated average rates: **31.99** (3Q26), **31.60** (2Q26), **29.95** (3Q25); 4Q26 guidance at the company's **31.7** forecast rate. Balance-sheet items use the 3Q26 average rate as an approximation.
	- **Thesis** — The first AI accelerator (customer unnamed; prior memos identify it as Google TPU) began shipping in September and is guided to ~\$2.5B in 2026, almost all in 4Q26 — ~37% of 4Q revenue. 2027 is guided to the high end of the ~\$16B target (~20% of the AI ASIC market), with a second-generation chip in HVM 1Q28 and a newly confirmed second, non-China ASIC customer from 2028. Management's business-model pitch: gross-margin dilutive, operating-margin accretive — 2027 operating margin guided above 20% vs 16.1% in 3Q26.
	- Related: [[2026-11-02-mediatek-emib-yield-tsmc-backstop-second-asic-customer]], [[2026-08-31-nvidia-mediatek-convertible-nvlink-fusion]], [[2026-07-01-mediatek-meta-asic-second-customer-after-google-tpu]], [[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]]

- ## ★ Highlight — \$3.9B Convertible Bond with NVIDIA and Alphabet Participating
	- **What management said** (CEO prepared remarks): *"During the quarter, we successfully completed an Overseas Convertible Bond offering of 3.9 billion US dollars, with participation from NVIDIA and Alphabet. This not only strengthened our partnership with key AI infrastructure partners but also enhanced our ability to secure capacity for critical components for business expansion."*
	- **Who is in it**
		- **NVIDIA** — the anchor. Per [[2026-08-31-nvidia-mediatek-convertible-nvlink-fusion]], NVIDIA's commitment was \$3.5B, tied to MediaTek adopting **NVLink Fusion** and co-developing **RTX/DGX Spark** PC chips.
		- **Alphabet** — the newly disclosed participant, and very likely **MediaTek's lead AI ASIC customer** (the Google TPU program in prior memos). If NVIDIA took \$3.5B, Alphabet's piece is at most ~\$0.4B (my arithmetic; the split was not disclosed).
	- **Why it matters**
		- **Both sides of the AI compute fight are now financing the same supplier.** NVIDIA funds MediaTek to pull custom XPUs onto NVLink; Alphabet funds the house that builds its TPUs. MediaTek sits between the GPU incumbent and the largest custom-silicon buyer, and is getting paid by both.
		- **The customer is funding its own supply.** The stated use is "to secure capacity for critical components" — in practice, substrates, HBM and advanced-packaging slots, which management repeatedly called the binding constraint. Alphabet's money effectively pre-funds the 2027 ~\$16B ASIC ramp.
		- **It answers a lock-up question from the August memo.** On this call MediaTek said it **supports UALink for Ethernet-based racks** alongside NVLink Fusion, so the NVIDIA deal does not appear to make it NVLink-exclusive.
		- **Convertible, not equity**: no immediate dilution for MediaTek; investors get equity upside with downside protection.
	- **Where it shows up in the numbers**
		- Financing cash inflow of **+\$3.37B** in 3Q26 (NT\$107.7B, net of other financing flows).
		- Non-current liabilities rose to **~\$4.72B** from ~\$1.09B.
		- Cash and current financial assets rose to **~\$8.70B** from ~\$6.28B.
		- The cash landed in the same quarter as a **~\$1.7B inventory build** and **negative operating cash flow**, i.e. it is funding the ramp.
	- **Not disclosed** — coupon, maturity, conversion price and the per-investor split. Without the conversion price, NVIDIA's and Alphabet's potential equity stakes can't be sized.

- ## ★ Highlight — Data Center / AI ASIC
	- **What management said** (CEO prepared remarks, verbatim):
		- *"For data center, demand for our first AI accelerator remains very strong. We have already commenced initial shipments in September and are confident of delivering 2.5 billion US dollars revenue in the fourth quarter. For 2027, we expect this program to achieve the high end of our revenue target range of approximately US\$16 billion, representing around 20% of the total AI accelerator ASIC market. This confidence is underpinned by our solid supply outlook. We are working closely with our supply chain partners for additional capacity to meet the strong customer demand. The successful ramp of our first AI accelerator marks an important milestone, demonstrating our ability to integrate industry-leading interconnect IPs, advanced process and advanced packaging technologies, together with our capabilities to orchestrate global supply chain, we are now able to deliver a highly competitive custom silicon for data centers."*
		- *"For our second AI accelerator project, the development is progressing well, and we are on track for high-volume production in the first quarter of 2028. This chip is purpose-built to power our customer's next-generation AI infrastructure. MediaTek incorporates cutting-edge technologies across every critical aspect of the design to deliver multiple times higher performance per watt with significantly lower TCO. We expect this project to further strengthen our market position and contribute substantially to our revenue growth."*
	- **The key numbers in that quote**
		- | Item | Guidance | Context |
		  |---|---|---|
		  | Gen 1 AI accelerator, 4Q26 | **~\$2.5B** | Raised from "slightly above \$2B." About 37% of the 4Q26 revenue midpoint (\$6.81B). Shipments only began in September. |
		  | Gen 1 AI accelerator, 2027 | **High end of ~\$16B** | ~20% of the AI accelerator ASIC market, implying ~\$80B (Q1 call: \$70–80B, 15% share target). That's ~1.6× the 4Q26 annualized run-rate (~\$10B) and ~80% of MediaTek's trailing revenue (~\$20B). |
		  | Gen 2 AI accelerator | **HVM 1Q28** | "Multiple times higher performance per watt," "significantly lower TCO." |
	- **Reading it**
		- **The guidance moved up again.** The Q4 ASIC number went from \$1B to \$2B on the Q1 call, to "slightly above \$2B," and now to \$2.5B. The 2027 market-share framing rose from 15% to ~20%.
		- **2027 is supply-gated, not demand-gated.** Confidence is "underpinned by our solid supply outlook," and MediaTek is still chasing "additional capacity." Upside beyond ~\$16B depends on substrates, HBM and packaging, which is what the convertible bond is meant to secure.
		- **The pitch is integration capability.** Interconnect IP (SerDes), advanced process, advanced packaging and supply-chain orchestration are exactly where Broadcom has been the default. A successful Gen 1 ramp is MediaTek's proof point for winning Gen 2 share and new customers.
		- **Gen 2 is the bigger prize and the bigger risk.** It's a higher-performance, higher-ASP part on an EMIB-T packaging flow whose yield is still being worked on, which is why management spent so much of the Q&A on tape-out timing and yield.
	- **Wording nuance** — The CEO said \$2.5B "in the fourth quarter." The CFO later framed it as "'26, we deliver ... \$2.5 billion for just — mainly for fourth quarter," and an analyst called it 2026 guidance. September shipments were "initial," so 2026 ASIC revenue is roughly \$2.5B, essentially all of it in Q4.

- ## Data Center / AI ASIC — Details from the Call and Q&A
	- **First AI accelerator (Gen 1)**
		- Initial shipments started **September 2026**.
		- **~\$2.5B revenue in 4Q26** — raised from the prior "slightly above \$2B." The CEO attributed the upside to robust customer demand plus success "rounding up" scarce supply, especially **substrates**.
		- **2027: high end of the ~\$16B revenue target range**, ~**20% of the total AI accelerator ASIC market**, which implies a TAM of roughly **\$80B** (my arithmetic). Still working with suppliers for more capacity above that.
		- For scale, the 2027 ASIC target alone (~\$16B) is ~80% of MediaTek's entire trailing-twelve-month revenue (~\$20B).
	- **Second AI accelerator (Gen 2, same lead customer)**
		- **On track for high-volume production in 1Q28.** "Multiple times higher performance per watt" with "significantly lower TCO."
		- Tape-out status (addressing market "noise" about delays): "a couple dies have been taped out already"; the big, most complex die will tape out on schedule, taking "a couple three weeks longer" than the others.
		- **Packaging: US IDM process (EMIB-T) is the "absolute priority."** MediaTek has built an in-house manufacturing team led by retired fab executives, working with the IDM plus Japanese and Taiwanese substrate suppliers on yield. CEO claims "very high confidence that the yield will go up very quickly" once two or three key defect sources are fixed.
		- Customer is asking for **upside** beyond plan; MediaTek is working the supply chain for it.
		- CFO on competition within the customer: rival "competing projects" are "not even close" on overall performance.
		- 2028 revenue not quantified — "another year of strong growth" vs 2027; supply for 2028 still being finalized.
	- **Third generation** — Working closely with the customer; definition not finalized. No timing (analysts assume late 2029).
	- **Second ASIC customer — confirmed**
		- A **different customer**, **not from China**. Project already kicked off; **first revenue in 2028**.
		- No size or margin given. CFO: customer demand "is pretty strong," but 2028 supply is still being finalized.
	- **Supplier dependence** — Asked about EMIB-T/Intel lock-in risk, the CEO said MediaTek is "not dependent on one supplier" and called **TSMC "our most important partner, period."**
	- **Enabling technology**
		- **448G SerDes (PAM6)** taped out; "will not be on the critical path." Will be made interoperable for a broader customer base.
		- **3.5D advanced packaging**, **co-packaged optics**, **HBM5** capability.
		- Moving beyond silicon into **system and rack solutions**.
	- **NVLink Fusion + UALink**
		- Connects custom XPUs to NVIDIA's NVLink ecosystem; also supports UALink for Ethernet-based racks. Pitch: faster customer "time-to-computation-power."
		- In discussion with **several potential customers together with NVIDIA**; positive feedback; hopes to "officially announce some case" in the near term.
	- **Financing** — See the convertible-bond highlight above. Separately, MediaTek is open to vendor financing for frontier-model customers "if we have the right customer."

- ## ASIC Economics — Gross-Margin Dilutive, Operating-Margin Accretive
	- Data center gross margin is **still below the corporate average** — why 4Q gross-margin guidance steps down ~1 point (45% ±1.5%).
	- **From 4Q26 the ASIC business's operating margin is accretive** to the company average (not quantified).
	- **2027 operating margin: "20% plus, if not slightly higher"** for the full year, vs 16.1% in 3Q26 and ~19% implied by 4Q26 guidance.
	- **Price increases** on non-data-center products starting 3Q26 to pass through supply-chain cost inflation.

- ## 3Q26 Financials (US$)
	- | Metric | 3Q26 | 2Q26 | 3Q25 | QoQ | YoY |
	  |---|---|---|---|---|---|
	  | Revenue | \$5.25B | \$4.82B | \$4.74B | +9.1% | +10.7% |
	  | Gross profit | \$2.43B | \$2.23B | \$2.21B | | |
	  | Gross margin | 46.3% | 46.2% | 46.5% | +0.1pt | −0.2pt |
	  | R&D | \$1.32B (25.1%) | \$1.25B (25.9%) | \$1.21B (25.6%) | | |
	  | Selling + admin | \$0.27B (5.1%) | \$0.26B (5.3%) | \$0.25B (5.3%) | | |
	  | Operating income | \$0.85B | \$0.72B | \$0.74B | +17.1% | +14.4% |
	  | Operating margin | 16.1% | 15.0% | 15.6% | +1.1pt | +0.5pt |
	  | Non-TIFRS operating income | \$0.87B (16.6%) | \$0.75B (15.6%) | \$0.76B (16.1%) | | |
	  | Net income to parent | \$0.87B | \$0.77B | \$0.84B | | |
	  | EPS (NT$ → US$) | NT\$17.50 ≈ \$0.55 | NT\$15.28 ≈ \$0.48 | NT\$15.84 ≈ \$0.53 | | |
	- **Currency matters** — In NT$, revenue grew 10.4% QoQ and 18.3% YoY; in US$ it was +9.1% and +10.7%. The New Taiwan dollar weakened from 29.95 to 31.99 per US$ over the year, so YoY growth looks smaller in dollars.
	- Revenue beat the guidance range on better-than-expected demand and improving supply. Share-based compensation was only \$24M (NT\$783M) — small next to US peers.

- ## Segment Revenue (3Q26)
	- | Group | Share | ≈ US$ | QoQ | YoY | Drivers |
	  |---|---|---|---|---|---|
	  | Mobile Phone | 37% | ~\$1.94B | −1% | −17% | Flagship outperformed; first 2nm **Dimensity 9600 Pro** phones launching. |
	  | Smart Edge Platforms | 58% | ~\$3.05B | +20% | +63% | New projects: **5G thin modem for a new smartphone customer**, AI tablets, AI PCs, auto cockpits; TV SoC up on higher DRAM content. Includes early AI ASIC shipments. |
	  | Power IC | 5% | ~\$0.26B | +1% | +18% | **Share gains in data center-related business.** |
	- Segment dollar amounts are share × total revenue (approximate). Growth rates are as stated by the company.

- ## Balance Sheet and Cash Flow — Building for the Ramp
	- **Inventory jumped to ~\$4.80B** (NT\$153.5B), from ~\$3.11B in 2Q26 and ~\$1.90B a year ago. Inventory days rose to **127** (from 102 and 68). This is consistent with pre-building for the 4Q ASIC ramp (my inference; the company didn't explain it).
	- **Operating cash flow turned negative: −\$0.13B** (vs +\$0.77B in 2Q26, +\$1.31B in 3Q25), driven by the inventory build. Investing −\$0.73B.
	- **Financing +\$3.37B**, mainly the \$3.9B convertible bond (see highlight above). Non-current liabilities rose to ~\$4.72B from ~\$1.09B; short-term loans ~\$1.31B (from ~\$0.54B).
	- Cash and current financial assets **~\$8.70B** (from ~\$6.28B); accounts receivable ~\$2.51B (43 days).

- ## 4Q26 Guidance
	- | Item | Guidance | US$ (at 31.7) |
	  |---|---|---|
	  | Revenue | NT\$210.1–221.8B | **\$6.63–7.00B** (midpoint \$6.81B) |
	  | QoQ | +25% to +32% | |
	  | YoY | +40% to +48% | |
	  | Gross margin | 45% ±1.5pt | |
	  | Opex ratio | 26% ±2pt | |
	  | Implied operating margin | ~19% | ~\$1.3B operating income at midpoint (my arithmetic) |
	- **AI ASIC is ~37% of 4Q revenue.** With ~\$2.5B of ASIC revenue in 4Q, non-ASIC revenue is ~\$4.3B, *down* ~15–17% QoQ from ~\$5.2B. Management flagged "seasonal softness in consumer electronics." This split is my estimate, not company guidance.
	- **FY2026 US$ revenue growth now expected to exceed the prior "high-single-digit" target.**

- ## Edge AI Highlights
	- **N1X (NVIDIA GPU + MediaTek SoC) in RTX Spark AI PCs** went on sale mid-October through major OEMs; second-generation SoC already in development.
	- **Dimensity 9500** in Samsung Galaxy Tab S12 — third straight generation of Samsung AI tablets on MediaTek flagship SoCs.
	- **5G thin modem** volume production for a new smartphone customer (unnamed).

- ## Takeaways and Watch Items
	- **The ASIC story is now in the numbers.** Roughly \$2.5B in one quarter going to ~\$16B in 2027 makes MediaTek a second-source-scale custom-silicon vendor against Broadcom. 2027 ASIC revenue would be ~80% of today's trailing company revenue.
	- **The real 2028 risk is Gen 2 execution on EMIB-T packaging yield and substrate supply.** Management is unusually emphatic about yield progress — worth tracking at each update, along with whether TSMC CoWoS ends up as a backstop.
	- **Second customer (non-China, 2028)** reduces single-customer concentration. Watch for its identity (US CSP or AI lab) and size. A NVLink Fusion customer announcement may also come soon.
	- **Margin mix:** expect gross margin to drift toward ~45% while operating margin expands past 20% in 2027 — the opposite of how a classic handset-SoC model scales.
	- **Working capital:** the inventory build and negative operating cash flow are tolerable during a ramp but should reverse in 4Q–1Q as ASIC shipments convert to cash.
	- **Core business:** Mobile is shrinking YoY (−17%); growth is coming from Smart Edge new projects and data center.
