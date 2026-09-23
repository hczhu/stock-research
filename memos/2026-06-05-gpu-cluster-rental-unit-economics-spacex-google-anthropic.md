- tags:: [[GPU]], [[$NVDA]], [[SpaceX]], [[xAI]], [[Colossus]], [[$GOOGL]], [[Anthropic]], [[Neocloud]], [[unit economics]], [[H200]], [[data-center]], [[compute]], [[capex]]
  file-created-at:: 2026-06-05

- ## Renting Out Nvidia GPU Clusters — Unit Economics (SpaceX/xAI → Google & Anthropic)
	- **Source**: Bloomberg, "SpaceX Inks $30 Billion Computing Power Deal With Google" (Carmen Arroyo & Julia Love, Jun 5 2026), for the Google deal; Anthropic figures folded in from [[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]] and [[2026-06-03-frontier-labs-gpu-compute-capacity-share]].
	- **Setup**: post the **Feb 2026 SpaceX–xAI merger**, SpaceX is converting xAI's data-center buildout (Memphis TN, expanding into Mississippi) into a **compute-infrastructure / GPU-rental business** — a centerpiece of its IPO pitch. It has now signed near-identical multi-year **Cloud Services Agreements** renting Nvidia GPU clusters to **two AI competitors** (Google, Anthropic). This memo extracts the rental unit economics.

- ## The Two Rental Contracts
	| Deal | Monthly fee | Term | Total contract value | GPU / hardware access | Power | Stated purpose |
	| --- | --- | --- | --- | --- | --- | --- |
	| **Google ← SpaceX** | **$920M / month** | Oct 2026 → Jun 2029 (~33 months) | **~$30B** | **110,000 Nvidia GPUs** (H200-class) + CPUs, memory chips, components | "**well over 100 MW**" (≈ powers 75,000 homes) | Bridge capacity for **Gemini Enterprise** agent platform (demand higher than expected) |
	| **Anthropic ← SpaceX** | **$1.25B / month** | through May 2029 (~36 months) | **~$45B** (≈ **$15B/year**) | **Colossus 1 + part of Colossus 2** (~550K+ H100e, mixed H100/H200/GB200) | Memphis campus = 2 GW total (rented subset not disclosed) | **Inference** — raise usage limits for Claude Code & the Claude API |
	- Both contracts share a **90-day termination notice**. The Google deal adds a kill-switch: Google can terminate if SpaceX fails to deliver Nvidia-chip access by **Sept 30 2026** (one-month grace).

- ## Derived Unit Economics — Google Deal (the clean anchor)
	- Cleanest because Bloomberg gives **both** the dollar figure **and** a literal GPU count (110,000 H200-class).
	| Metric | Value | Basis |
	| --- | --- | --- |
	| Per GPU per month | **~$8,360** | $920M ÷ 110,000 GPUs |
	| Per GPU per year | **~$100,000** | ×12 |
	| Per GPU-hour | **~$11.4** | $8,360 ÷ 730 hrs |
	| Per MW per month | **~$8.4M** | $920M ÷ ~110 MW |
	| **Per GW per month** | **~$8.4B** | $920M ÷ ~0.11 GW |
	| **Per GW per year** | **~$100B** | ×12 |
	- **Power-denominator caveat**: Bloomberg says only "well over 100 MW." At an assumed **~110 MW** (≈ 1 kW/GPU all-in for H200 systems) the per-GW figures above hold; if treated as exactly **100 MW**, they rise to **~$9.2M/MW/month** and **~$9.2B/month/GW** (~$110B/yr/GW). The per-GPU figures need no power assumption and are the most robust.
	- **Sanity check**: ~$11.4/GPU-hr for a bundled H200 cluster (GPU + CPU + memory + interconnect) is a plausible premium over bare H200 on-demand rates — consistent with a turnkey, contracted, multi-year cluster.

- ## Derived Unit Economics — Anthropic Deal (rougher)
	| Metric | Value | Basis / caveat |
	| --- | --- | --- |
	| Per H100e per month | **~$2,270** | $1.25B ÷ ~550K H100e — **but** this is *H100-equivalent* (peak-FLOP-normalized), not a literal GPU count, and the fleet mixes older/cheaper H100/H200 plus some GB200 |
	| Annual run-rate | **~$15B/year** | $1.25B × 12 |
	- **Why per-unit looks ~3.7× cheaper than Google's** ($2,270 vs $8,360): not directly comparable — Anthropic's count is **H100e-normalized** (inflates the effective unit count vs literal H200s), the silicon skews **older/cheaper**, and the contracted fleet is far larger (**scale discount**), plus the exact rented capacity is undisclosed. Treat the two per-unit numbers as **different denominators**, not a like-for-like price gap.

- ## Cross-Deal Read
	- **SpaceX/xAI rental run-rate from two customers alone ≈ $2.17B/month (~$26B/year)** — Google $920M + Anthropic $1.25B. This is the revenue engine xAI is selling into its IPO, despite "falling behind on coding."
	- **xAI as the supply regulator / passive neocloud** — reselling idle H100/H200 capacity to direct model-rivals ([[2026-06-04-neocloud-supply-demand-ai-infra-restructuring-kenny-zhang]]); compute infrastructure, not model wins, is the monetization.
	- **Google is renting from a competitor it part-owns**: Google held **6.11% of SpaceX** at end-2025 → **~5%** post-merger; Alphabet "poised for a ~$100B windfall" on the stake. Google Cloud backlog **>$460B** (nearly doubled QoQ); Alphabet upsized its AI-spend offering to **$85B** — the rental is explicitly "bridge capacity."

- ## Investment Implications
	- **GPU-cluster rental is a ~$100B/year-per-GW business at H200-class pricing** (Google anchor: ~$8.4–9.2B/month/GW, ~$100–110B/yr/GW; ~$100K/GPU/yr). A useful back-of-envelope for sizing neocloud/hyperscaler rental revenue against deployed power.
	- **Demand is so acute that hyperscalers rent from rivals they compete with and part-own** — validates the inference-capacity-scarcity thesis and the neocloud "fourth cloud" economics ([[2026-06-04-neocloud-supply-demand-ai-infra-restructuring-kenny-zhang]], [[2026-06-03-frontier-labs-gpu-compute-capacity-share]]).
	- **Contracted, multi-year, 90-day-cancellable**: large headline TCV (~$30B / ~$45B) but with near-term off-ramps — backlog quality is softer than the totals imply; watch the Sept 30 chip-delivery condition on the Google deal.
	- **Read-through to $NVDA demand durability**: two fresh multi-GW, multi-year clusters (110K GPUs for Google; Colossus 1+2 for Anthropic) are incremental, contracted Nvidia silicon pull-through.
	- **Caveat**: per-GW economics hinge on the power denominator ("well over 100 MW" is imprecise) and on H100e-vs-literal-count normalization for the Anthropic figure — anchor on the per-GPU/month number, treat per-GW as an estimate.
