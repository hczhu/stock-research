tags:: [[$TSM]], [[TSMC]], [[Samsung]], [[$INTC]], [[SMIC]], [[foundry]], [[semiconductor]], [[pricing]], [[capex]], [[advanced-packaging]], [[$NVDA]], [[$AAPL]]

- ## TSMC reportedly raising prices across every node — and Samsung fired first
	- **Source**: 工商時報 / 理財周刊投研部, reposted by 半導體行業觀察 (issue 4514), August 30, 2026, citing TrendForce, Nomura, Citi and CLSA research plus supply-chain checks. **Two strong bias flags.** Much of the TSMC pricing detail is explicitly framed as rumour circulating among foreign institutions (「外資圈更盛傳」), not confirmed. And the piece closes with an outright buy recommendation — that the current dip is a good entry point — so **treat it as promotional commentary, not neutral reporting.**
	- **Thesis**: The investable content is not the size of any single increase but **the sequence and the breadth**. Samsung — the distant number two, loss-making in foundry since 2022 — raised prices first, which is the strongest possible evidence that the leader can. And the increases reportedly extend to **mature nodes untouched for three years**, which means this is genuine capacity tightness rather than an AI-only leading-edge story.
- ## The reported price moves
	- | Supplier / node | Change | Timing |
	  |----------------------------|-------------------|--------------------|
	  | **Samsung** N4 and N5 | **+10–15%** | from July |
	  | **Samsung** N8 (mature) | **+~10%** | from July |
	  | **TSMC** N3E / N3P | **up to +15%** | H2 2026, already negotiated mid-year |
	  | **TSMC** N2, N3, N5 | **+5–10%** on top | early 2027 |
	  | **TSMC** N12, N16, N28 | **up to +10%** | unchanged for three years prior |
	- **Foundry share as of Q1**: TSMC **~73%**, Samsung **~7%**, SMIC **~5%**. The article's argument is simply that at a 73:7 split, if the 7% player can raise prices, the 73% player has no reason not to follow.
	- **The mature-node increase is the more informative half.** N12/N16/N28 are where Chinese competition is most intense and where pricing has been flat for three years. Raising there implies **broad capacity tightness**, not merely AI-driven scarcity at the leading edge — and it is the part least likely to have been leaked as wishful thinking, since it is the least glamorous.
	- **Samsung's position is the cleanest cycle signal in the piece**: its foundry division has been **loss-making since 2022**, is now absorbing transfer orders because TSMC's N5-through-N2 capacity is full, and is raising prices into that. **When the marginal, less-preferred supplier gains pricing power, the market is genuinely short** — that is a more reliable indicator than anything the leader says.
- ## Why TSMC faces almost no demand resistance — the derivation worth keeping
	- **The disclosed anchor**: N2 starts at **\$30,000 per wafer**, a **10–20% technology premium** over N3, which implies **N3 at roughly \$25,000–27,300**.
	- **Combine that with the wafer intensity in [[2026-08-29-dylan-patel-dwarkesh-revenue-per-megawatt-compute-centralization]]** — 1 GW of Vera Rubin requires roughly **55,000 N3 wafers**:
	  | Item | Value |
	  |-------------------------------------|--------------------|
	  | N3 wafer cost per GW at ~\$26,000 | **~\$1.43B** |
	  | After the H2 +15% | ~\$1.64B (**+\$214M**) |
	  | After a further early-2027 +10% | ~\$1.81B (**+\$379M**) |
	  | **As a share of ~\$100B annual revenue per GW** | **~1.4%**, rising to ~1.8% |
	  | **Cost of the full ~26.5% cumulative hike** | **~0.38% of end revenue** |
	- **This is the whole pricing-power argument in one number.** A cumulative 26.5% wafer price increase costs the buyer **less than half a percent** of the revenue that gigawatt generates. **There is essentially no elasticity at this point in the chain**, which is the concrete form of the ~100× fab-capex-to-revenue arbitrage in that memo. **The constraint on TSMC's pricing is customer-relationship management and long-term strategy, not customer willingness to pay.**
	- **Corollary for modelling**: do not treat these increases as a demand risk. Model them as **near-pure gross-margin expansion**, and expect the same logic to keep working until the arbitrage closes — which requires far more supply, not higher prices.
- ## Demand and competitive datapoints
	- **N2 and N3 are described as nearly fully booked by Apple and NVIDIA.** Citi's view is that advanced-node utilization stays high with N2/N3 rigid demand supporting prices **through 2027**.
	- **The most interesting competitive item is Intel.** For its **Nova Lake** desktop processors launching early 2027, Intel will use its own **18A** *and* expand purchases of TSMC's **N2X** — the high-performance extension of N2. **A vendor buying its competitor's leading node for its flagship consumer part is a strong statement about relative process confidence**, and it adds an unexpected demand source to TSMC's most expensive tier.
	- Revenue backdrop: **May, July and the month between each set records**, with three consecutive months of both YoY and MoM growth and three months of double-digit cumulative growth.
- ## Capex — and an update to what I wrote about overseas fabs
	- | Year | Capex |
	  |------|------------------|
	  | 2026 | **\$52–56B** (raised, record) |
	  | 2027 | **~\$80B** (CLSA estimate, **+~48%**) |
	  | 2028 | **~\$90B** (**+~12%**) |
	  - CLSA's stated rationale is widening the technology and scale gap against Samsung and Intel — i.e. **spending as a competitive moat rather than purely demand-following**.
	- **The US commitment was raised in July to \$265 billion**: **10 fabs, 2 advanced packaging plants, and 1 R&D center** in Arizona.
	- **This materially qualifies the argument in [[2026-08-21-tsmc-cross-node-utilization-truck-fleet]].** I wrote there that cross-node utilization — trucking partially processed wafers between fabs at different nodes — requires dense multi-node clustering under one operator, and that overseas fabs are therefore *geographically isolated islands* that cannot access the mechanism. **A ten-fab Arizona cluster with its own packaging is not an island.** If TSMC builds out that footprint, it can eventually replicate the domestic cross-utilization play in the US, which removes one of the structural cost penalties on overseas expansion. **The isolation argument was correct for one or two fabs and gets weaker with every additional one on the same site.**
- ## Supply-chain read-through
	- The piece identifies four categories tied to the buildout — **facility and cleanroom engineering, semiconductor equipment, materials, and chemicals/specialty chemicals** — noting many constituents set record January–July cumulative revenue with double-digit YoY growth.
	- **The useful framing**: capex guidance of \$80B in 2027 and \$90B in 2028 is *already* the forward order book for these suppliers, and the article notes visibility extending beyond 2027. **Equipment and materials order books lead TSMC revenue, so they are the earlier read on whether the capex plan is real.**
- ## Market view, and what to discount
	- Target prices were raised into a **NT\$3,100–4,200** range against a close of **NT\$2,375** (down NT\$35, below the quarterly moving average). **The article's explicit conclusion that this is a good moment to buy the dip is the clearest signal of its promotional intent** and should be set aside.
	- **What to hold lightly**: the TSMC increases are unconfirmed and sourced to institutional rumour and supply-chain checks; the 2027/2028 capex figures are a **CLSA estimate**, not guidance; and price increases negotiated with customers do not translate one-for-one into realized ASPs given mix, long-term agreements, and volume commitments.
	- **What to hold firmly**: **Samsung's disclosed July increases**, its loss-making history and receipt of transfer orders, the **73/7/5 share split**, the **\$30,000 N2 wafer price**, the **\$265B / 10-fab Arizona plan**, and Intel's N2X purchase. Those are specific enough to verify and are the load-bearing facts under the pricing thesis.
	- **The single question that decides the thesis**: whether the mature-node increases (N12/N16/N28) actually land. Leading-edge increases are consistent with AI scarcity alone; **mature-node increases after three flat years would confirm system-wide tightness** and are the more meaningful confirmation to watch for.
