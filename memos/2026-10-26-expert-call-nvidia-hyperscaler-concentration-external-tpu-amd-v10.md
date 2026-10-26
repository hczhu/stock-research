tags:: [[$NVDA]], [[$GOOGL]], [[$AVGO]], [[$AMD]], [[$MSFT]], [[$META]], [[$AMZN]], [[$ORCL]], [[TPU]], [[ASIC]], [[custom-silicon]], [[chiplets]], [[advanced-packaging]], [[MediaTek]], [[Trainium]]
file-created-at:: 2026-10-26

- ## Expert Call: External TPU Revenue Ramps to ~\$100B by 2028, and Nvidia's Real Risk Is the Precedent
	- **Source**: Expert-network call transcript (Client/Expert format with timestamps), anonymous expert on hyperscaler AI silicon. **Four highlighted excerpts supplied, not the full call**, spanning 00:13:12–00:37:00 and supplied out of order. No call date is shown; references to "this year" read as 2026. The expert cites "one of my colleagues from MediaTek" and figures "we are aware of internally in the industry," which suggests a supply-chain vantage point, but the affiliation is not stated. Treat as paid practitioner opinion, not reported fact. Related: [[2026-09-07-semianalysis-tpuv7-inference-externalization]], [[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]], [[2026-07-01-mediatek-meta-asic-second-customer-after-google-tpu]].
	- **Thesis**: The expert's base case is that AI demand grows fast enough for Nvidia revenue to keep rising even as Google's TPU takes share. Nvidia's exposure is that **Google proves custom-silicon economics publicly**, through an external TPU business the expert sizes at ~\$8B in 2026 rising to ~\$104B in 2028. If that works, Microsoft and AWS gain confidence in their own ASIC programs, and the pressure shows up in Nvidia's pricing and gross margin before it shows up in revenue.
	- **Calibration**: several of the expert's numbers are internally inconsistent or garbled in transcription (see the reconciliation section). The direction of each claim is more reliable than its precision.

- ## Nvidia's Hyperscaler Concentration (2025)
	- The expert estimates that **more than half of Nvidia's data-center revenue comes from four hyperscalers**, on a base of "around \$106 billion" for 2025:
	- | Customer | Estimated share of Nvidia data-center revenue | Expert's characterization |
	  |---------------------|----------------------------------|-------------------------------------------------------------|
	  | **Microsoft** | `~18%` | Largest buyer; Azure AI demand drives GPU purchases |
	  | **Meta** | `~13%` | "Highly exposed"; relies on GPUs for training and inference despite MTIA, which "is not that great. They could have done better" |
	  | **Amazon (AWS)** | `~9%` | Runs both strategies: large Nvidia deployment alongside Trainium and Inferentia |
	  | **Google** | `~9%` | "Clearly the custom ASIC counterexample"; TPU v8, v9, v10 will "dominate its own AI server deployment" but it remains a meaningful Nvidia customer |
	  | **Oracle** | `~4.5–5%` | Important AI cloud, but not on the scale of the four above |
	  | **Top five combined** | `~54%` | Consistent with "more than half" |
	- The expert expects this split to change: "The Google dependency is certainly, in my opinion, going to be less, even if Microsoft still relies heavily on NVIDIA and Meta and AWS, too."
	- The **\$106B** base should not be read as Nvidia's reported data-center revenue for any fiscal period. The expert offers it loosely ("approximate number of the GPU revenue that I am talking, data center revenue"), so the **percentages are the usable part**, not the dollar base.
	- The client's framing question, worth keeping as the open issue: "How long can CapEx grow 100% a year?"

- ## Google's Spend Split and Nvidia Purchases
	- The expert's breakdown of Alphabet's current spending:
	- | Layer | Expert figure |
	  |---------------------------------------|----------------------------------------------------------|
	  | Total capex | **~\$200B** |
	  | Server infrastructure | **~\$120B** |
	  | Nvidia hardware purchases | **~\$25B** ("the number we are aware of internally in the industry") |
	  | Split within server and compute spend | **60%** compute infrastructure; **40%** data center and networking, with Nvidia purchases ~15% inside it |
	  | Annual Nvidia purchases, midpoint | **~\$22B** |
	- Two readings point the same way: Nvidia is roughly **11–12% of Google's total capex**, and roughly a fifth of its server infrastructure. Google is a large Nvidia customer in absolute dollars while being the hyperscaler least dependent on it.
	- The expert also says "around \$55 on server and compute spending" with no unit or scale, so that line cannot be reconstructed.

- ## External TPU: Sized at ~\$100B by 2028
	- Google **began recognizing external TPU sales in Q2 2026**. Management has said most revenue from existing agreements will be recognized in 2027.
	- | Year | External TPU hardware revenue (expert) | Note |
	  |----------|-------------------------------------|-----------------------------------------------------------|
	  | **2026** | **~\$8B** | "That's how we are closing the year" |
	  | **2027** | **~\$51B** | The expert explicitly rejects a **\$75B** figure in circulation: "That estimate is not \$75 billion" |
	  | **2028** | **~\$104B** | Roughly doubling again |
	- Volume: the expert says Google shipped "around **240,000** chips" in 2026 and that 2027 is "going to be exactly \$2.4 million." The second figure is almost certainly a transcription error. A unit reading of **~2.4 million chips** would be a ~10× step-up, roughly in line with the ~6× revenue step from 2026 to 2027 if per-unit pricing falls with volume, but the transcript does not establish which was meant.
	- The external TPU sales are included in Google Cloud's **\$514B** backlog, which "could plausibly scale from a single-digit billions in 2026 to tens of billions of dollars."
	- The expert's correction from \$75B to \$51B for 2027 is the most actionable number in the call. His **\$51B is ~32% below the \$75B figure in circulation**, so whoever holds the \$75B number (the transcript does not say whether it is consensus, sell-side, or the client's own) may be too high for 2027, even though the absolute ramp remains extraordinary.

- ## Why Nvidia Can Keep Growing, and What to Watch Instead
	- The base case is explicit: "The total AI demand is growing so rapidly that NVIDIA can continue increasing revenue," even as custom silicon takes share. Nvidia "can also continue growing laterally on a different foot."
	- The expert's recommended metric is **not** whether Google uses TPUs: "It is whether NVIDIA's sales growth and pricing gross margin can weaken as custom deployments are scaling."
	- The core argument: "**NVIDIA's risk is not just towards losing one customer here. It's the precedent.** If Google demonstrates compelling economics with custom accelerators, then other hyperscalers like Microsoft and AWS, they can gain confidence in their own ASIC programs too, and that can pressure NVIDIA long-term share and pricing power."
	- Google's integration now extends past the chip: it "owns the architecture, going forward, it's going to own the compiler and the serving stack." The expert calls it "the strongest example of vertical integration" in AI silicon. That is why the external TPU business matters beyond its revenue: **external customers who run on TPUs at scale are the public proof of the economics** that the precedent argument depends on.

- ## AMD's Role in TPU v10: Integration, Not Broadcom Replacement
	- AMD's involvement with the Google TPU is "an early discussion phase." Its role is in **v10, not v11**. Per the expert's MediaTek colleague (August 2026), **AMD is possibly contributing CPU IP and packaging expertise**.
	- **Broadcom is not being displaced**: "This is different from AMD replacing Broadcom. All that stuff is not happening... They are not replacing Broadcom." Broadcom is not losing significant share in the Google TPU. v11 participation for AMD is "still getting evaluated. If they do well in v10, they get a chance in v11."
	- **Why integration matters**: a TPU combines an HBM die, IP, large SRAM blocks, core logic, PHY, interposer, and packaging. "If you don't know the heterogeneous integration technology for a TPU variant, then you are going to suffer big time in the reliability, in their yield."
	- **Why CPU cores belong in the TPU package**: agentic AI and reinforcement learning involve "repeated inference and scheduling and control-heavy operations, not just matrix multipliers." A **tightly coupled CPU and tensor compute** "could reduce a lot of communication overhead and improve the latency" for CPU-sensitive phases. This is a workload-driven architecture shift: as RL and agent loops grow, the accelerator needs general-purpose compute close at hand.
	- **Chiplets are the reference design**: "Chiplets are literally the future for the next generation AI ASIC." The expert points to AMD's **MI300A** (CPU and GPU chiplets in one package) as "an industry benchmark today" whose packaging approach Google wants to bring to v10.
	- "**Diversification is always Google's strategy.**" Read with the earlier MediaTek role, Google now sources TPU design and integration from Broadcom, MediaTek, and potentially AMD, which limits any single partner's pricing power over the program.

- ## Reconciling the Expert's Numbers
	- **Google's share of Nvidia does not match the Google spend figures.** At ~9% of a ~\$106B base, Google bought ~\$9.5B of Nvidia hardware in 2025. The same expert puts current Google Nvidia purchases at **~\$22–25B**. The gap could reflect 2025 versus a 2026 run-rate, a different revenue base, or both, but the transcript does not reconcile it. Either the share table understates Google, or the spend figures overstate current purchases.
	- **The \$22B midpoint does not follow from the stated arithmetic.** 15% of \$120B is \$18B; 15% of \$200B is \$30B. \$22B is roughly the midpoint between \$18B and \$25B, which appears to be what the expert means by "midpoint."
	- **The 2027 volume figure** ("\$2.4 million") is garbled, as noted above.
	- None of these change the direction of the argument: Nvidia's top-four concentration is high, Google is the least dependent, and external TPU revenue is ramping steeply. They do mean no single dollar figure from this call should be carried into a model without a second source.
