tags:: [[$GOOGL]], [[TPU]], [[ASIC]], [[$2454.TW]], [[MediaTek]], [[$AVGO]], [[$INTC]], [[EMIB]], [[advanced-packaging]], [[OpenAI]], [[Anthropic]], [[$NVDA]], [[semiconductor]], [[AI-capex]], [[Ming-Chi-Kuo]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-15
file-updated-at:: 2026-11-15

- ## Google TPU: OpenAI and Anthropic Orders Extend Visibility to 2029, and MediaTek Becomes the Sole Next-Gen Designer
	- **Source**: [Ming-Chi Kuo (郭明錤, @mingchikuo), X post, Nov 15, 2026](https://x.com/mingchikuo/status/2122133109630194098), titled "Google TPU update: New OpenAI and Anthropic orders extend shipment visibility to 2029; v10 lineup overhauled (now Quillfish); MediaTek and Broadcom lead as the top suppliers to watch." Kuo bases it on his latest industry survey. Unit and share figures are Kuo's estimates, not company disclosures.
	- **Thesis**: OpenAI and Anthropic orders for v8 TPUs, not Google's own buildout, drive TPU volume through 2029. MediaTek gains on two fronts: it designs the high-margin 8t that OpenAI buys, and it is the sole designer of v9, v10 and v11. Its main exposures are Intel EMIB-T packaging capacity and OpenAI's ability to fund about 12M chips.
	- **Prior codenames**, from [[2026-06-03-hbm-supply-demand-model-morgan-stanley]]: 8t is Zebrafish (MediaTek) and 8i is Sunfish (Broadcom). The v9 parts are Humufish and Triggerfish ([[2026-05-01-mediatek-google-tpu-codesign-semi-cot-model]]).
- ## Shipment Plan: Visibility Now Runs to 2029
	- **Visibility**: new OpenAI and Anthropic orders extend TPU shipment visibility to **2029**. Kuo puts visibility for Nvidia GPUs and other AI ASICs mostly at **4Q27–2Q28**.
	- **Customer split**: from 2028, v9 becomes the mainstay of Google's own compute buildout, so Kuo attributes v8-series orders (8t, 8i or their design variants) to OpenAI and Anthropic.
	- | Customer | Chip and designer | 2028–29 combined demand | How it pays |
	  | --- | --- | --- | --- |
	  | OpenAI | 8t, designed by MediaTek | **About 12M units**, growing YoY | Buys outright |
	  | Anthropic | 8i, designed by Broadcom | **About 14M units**, growing YoY | Mix of leasing and outright purchase |
	- **Supply-constrained total shipments, with MediaTek's share of TPU supply**:
		- | Year | Total TPU shipments | MediaTek share of supply | Implied MediaTek units (*my math*) |
		  | --- | --- | --- | --- |
		  | 2027 | 8–9M | 45–50% | 3.6–4.5M |
		  | 2028 | 14–15M | 50–55% | 7.0–8.3M |
		  | 2029 | 16–18M | 55–60% | 8.8–10.8M |
		- The implied-units column assumes the share is measured in units. The note doesn't say whether it means units or revenue.
	- **Against the capex-peak view**: the market broadly expects AI capex to peak in 2028. In this plan, TPU shipments still grow in 2029 because OpenAI and Anthropic order directly.
	- *My math*:
		- **Growth**: at midpoints, shipments grow about **71%** in 2028 (8.5M to 14.5M) and about **17%** in 2029 (14.5M to 17M). 2029 still grows, but the growth rate is already slowing sharply.
		- **Customer concentration**: OpenAI plus Anthropic total about 26M of the 30–33M units shipped in 2028–29, or **79–87%**. That leaves only about 4–7M units over two years for Google's own v9 and v10 buildout.
		- **The numbers reconcile**: MediaTek's implied 2028–29 total is 15.8–19.1M units. Subtracting OpenAI's 12M of 8t leaves 3.8–7.1M of v9 and v10, which matches the 4–7M left for Google. The remainder for Broadcom, 11–17M, brackets Anthropic's 14M of 8i.
	- *My note*: the expert call in [[2026-10-26-expert-call-nvidia-hyperscaler-concentration-external-tpu-amd-v10]] put external TPU volume at about 2.4M chips in 2027, a figure that may be a transcription error. That count covers external sales only, so it is not directly comparable with this note's 8–9M total. Even so, the gap is large enough that the 2027 figure deserves a cross-check.
- ## Roadmap Reshuffle: Quillfish Becomes v10
	- | Generation | Codename | Designer | Mass production |
	  | --- | --- | --- | --- |
	  | v8t | Zebrafish | MediaTek | Mass production from 4Q26; OpenAI's chip in 2028–29 |
	  | v8i | Sunfish | Broadcom | Current generation; Anthropic's chip in 2028–29 |
	  | v9 | Humufish and Triggerfish | **MediaTek, sole supplier** | Google's mainstay from 2028 |
	  | v10 | **Quillfish**, replacing Icefish and Merope / Bladerunner | **MediaTek**, design-service win | **2029** |
	  | v11 | **Icefish**, moved from v10 | **MediaTek**, design-service win | **2030** |
	  | Not assigned | Merope | No supplier chosen | Low visibility; may be canceled |
	- **What changed from earlier memos**:
		- Icefish was previously reported as the 10th-generation TPU, with a Samsung 2nm I/O die and a TSMC compute die around 2028 ([[2026-07-03-samsung-foundry-wins-skhynix-capacity-roadmap]]). It now slips to v11 in 2030.
		- The Merope / Bladerunner branch has lost its v10 slot.
	- **Packaging**: from v9 onward, every new TPU uses Intel's **EMIB-T** advanced packaging. EMIB-T's initial capacity is limited, so **v8 stays the bulk of TPU shipments through 2029**.
- ## MediaTek: The Biggest TPU Winner of the Next Few Years
	- **Why Kuo ranks MediaTek first**:
		- **Sole designer from v9 onward**: MediaTek designs v9, v10 (Quillfish) and v11 (Icefish).
		- **Rising share of a growing total**: its share of TPU supply rises from 45–50% in 2027 to 55–60% in 2029. Combined with rising shipments, TPU revenue and profit contribution should rise every year.
		- **8t is the profit engine**: the high-margin 8t has shipment visibility through 2029, with OpenAI as the 2028–29 buyer.
		- **Learning curve plus procurement**: v8 is expected to be the main source of TPU profit growth for both MediaTek and Broadcom over the next few years. Both have accumulated substantial learning-curve gains, and both procure the key components and materials.
	- *My note*: four points for the MediaTek position.
		- **Profit is concentrated on one customer**: because EMIB-T capacity keeps v9 and v10 small through 2029, MediaTek's TPU profit in 2028–29 depends heavily on 8t, which means OpenAI. OpenAI buys outright, so MediaTek's volume rides on OpenAI's ability to fund about 12M chips. Anthropic's leasing mix spreads that funding risk on Broadcom's side.
		- **EMIB-T caps the upside and adds timing risk**: MediaTek's second-generation ASIC (v9) targets mass production in 1Q28 on EMIB-T. The bottleneck is reportedly substrate yield, and TSMC has signaled CoWoS as a backstop ([[2026-11-02-mediatek-emib-yield-tsmc-backstop-second-asic-customer]]). This note implies the EMIB-T constraint limits how fast v9 and v10 can replace v8, but not who gets the orders.
		- **This conflicts with Google's diversification habit**: the earlier expert call said "Diversification is always Google's strategy." It also said Broadcom is not being displaced and AMD may contribute CPU IP and packaging to v10. Sole-supplier status from v9 to v11 is a stronger claim than that call. Broadcom keeps 8i, so Google stays dual-sourced at the fleet level, just not within each generation.
		- **Revenue may outgrow margin**: MediaTek's procurement of key components lifts revenue. If that includes HBM or other pass-through content, margin could grow more slowly than revenue as v9 ramps. The note doesn't say what is procured.
	- **Second customer**: MediaTek's non-Chinese second ASIC customer, confirmed on its Oct 30 call for 2028 revenue, is separate from all of this and adds on top.
- ## Broadcom: Higher Margin on 8i, but TPU Becomes a Smaller Share
	- Broadcom leads the 8i design, and 8i's gross margin is **even higher than 8t's**, which supports Broadcom's profit growth.
	- Broadcom's focus over the next few years is non-TPU XPU and AI networking orders. **Non-TPU revenue could pass TPU revenue as early as 2027.**
	- *My note*: for Broadcom, Google's TPU becomes a high-margin legacy line tied to Anthropic, while growth shifts to other customers' XPUs and networking. See [[2026-09-05-circuit-broadcom-custom-asic-unmodelable-2027-peak-constraint]].
- ## Why Market Attention on TPU Should Persist
	- **Nvidia's leadership uncertainty**: uncertainty over Nvidia's CEO succession helps Google when it discusses post-2028 long-term plans with customers (see [[2026-11-12-nvidia-huang-exit-hbm-vendor-agreements]]).
	- **OpenAI and Anthropic IPOs**: both are key TPU customers, so their IPOs should keep attention on the TPU. MediaTek and Broadcom are the suppliers the market most readily associates with it.
	- **Anthropic's leasing**: Google's TPU repurchase guarantees ([[2026-10-29-google-tpu-repurchase-guarantees]]) are one way Google can make leasing financeable for Anthropic. Whether Anthropic leases through Google or third parties isn't stated.
- ## Open Questions
	- Is MediaTek's 45–60% supply share measured in units or revenue?
	- What does "procurement of key components" include? If it includes HBM, revenue grows faster than profit.
	- Who supplies Merope if it survives, and does AMD still have a role in Quillfish?
	- How fast can EMIB-T capacity grow before 2029? That sets how quickly v9 and v10 replace the v8 profit base.
