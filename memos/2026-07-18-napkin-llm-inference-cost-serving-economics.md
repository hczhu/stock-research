- tags:: [[inference]], [[LLM-serving]], [[AI-economics]], [[unit-economics]], [[$NVDA]], [[HBM]], [[DRAM]], [[gross-margin]], [[AI-capex]], [[Anthropic]], [[OpenAI]], [[semiconductors]]

- **Source**: injuly.in, "Napkin math for LLM inference cost" ([link](https://injuly.in/blog/napkin-inference-cost/index.html)). A roofline/first-principles walkthrough estimating what it costs to serve one user of a 32B FP8 model on a single Nvidia B200, working backward from GPU compute/bandwidth to concurrent users to per-user cost. Investment framing is mine; these are the author's illustrative assumptions, not a vendor P&L. Companion to [[2026-07-16-dylan-patel-podcast-ai-infra-memory-cpu-optics-power]] (token-efficiency), [[2026-07-07-interconnect-first-inference-latency-over-bandwidth-lpddr]] (memory-bound decode), [[2026-07-13-benedict-evans-token-pricing-commodity-infrastructure]], and [[DRAM-memory-ssd-index-thesis]].

- **Thesis frame**: The napkin math lands on a striking result — **serving a good open model can cost on the order of ~\$0.01/user-hour (~\$9/user-month) at scale**, because decode is **memory-bandwidth-bound** and one B200 can serve **hundreds of concurrent chat users** once idle time and PagedAttention are accounted for. Two investable read-throughs: (1) **API token prices carry very high gross margins** vs raw serving cost (corroborates the "Anthropic prints" and "inference is cheaper than people assume" claims), and (2) **the binding constraint is memory bandwidth / KV-cache, not FLOPs** — structurally bullish HBM and the interconnect/memory theses.

- ## Extracted Data Points
	- | Category | Item | Value |
	  |---|---|---|
	  | **B200 hardware** | Dense compute | 4,500 TFLOP/s |
	  | | Sparse compute | 9,000 TFLOP/s |
	  | | Memory bandwidth | 8 TB/s (8×10¹² B/s) |
	  | | Compute:bandwidth (arithmetic-intensity break-even) | **562 FLOPs/byte** |
	  | | Purchase cost | \$40,000 |
	  | | Rental cost (bulk/committed) | \$4/hour |
	  | **32B ref model (FP8)** | Parameters → VRAM | 32B → 32 GB |
	  | | Hidden dim (d) | 8,192 |
	  | | Layers (L) | 64 |
	  | | Context window | 200,000 tokens |
	  | | Query heads / KV heads (GQA) | 64 / 8 (8× reduction) |
	  | **KV cache** | Per sequence, no GQA | 210 GB |
	  | | Per sequence, 8× GQA | ~26 GB |
	  | **Concurrency** | Max users @ 100% duty cycle | 6 |
	  | | Realistic (PagedAttention + variable ctx) | 40–60 /GPU |
	  | | Practical (incl. idle time) | **300–800 /GPU** |
	  | **Batching** | Optimal batch for full GPU util (2B = 562) | B ≈ 331 users |
	  | **Latency/throughput** | Data-movement time / forward pass | 23.75 ms |
	  | | Compute time / forward pass | 0.5 ms |
	  | | Total / forward pass | ~24 ms |
	  | | System tokens/sec (6 users) | ~250 |
	  | | Per-user tokens/sec | ~40 |
	  | **Cost — purchase (per-user lifetime)** | @ 6 users | \$6,667 |
	  | | @ 300 users | **\$133** |
	  | **Cost — rental (per-user)** | @ 300 users | **\$0.013/hr** |
	  | | monthly equivalent (30 days) | **~\$9.36/user-mo** |
	  | **Assumptions** | Duty cycle (typical chat) | ~20% |
	  | | Median conversation length | 4–40k tokens (vs 200k max) |

- ## The Core Insight — Decode Is Memory-Bound
	- The **562 FLOPs/byte** break-even (4,500 TFLOP/s ÷ 8 TB/s) is the crux: to saturate a B200's compute you must do 562 ops per byte moved. A single-user decode step does far less (~2 ops/byte), so the GPU sits **compute-idle while waiting on memory** — decode is bandwidth-bound, exactly the roofline point in [[2026-07-07-interconnect-first-inference-latency-over-bandwidth-lpddr]].
	- **Batching is the escape**: you need batch **2B ≈ 562** (B ≈ 331 concurrent users) to make compute the bottleneck. Only at high batch does the expensive silicon get used — which is why **serving is cheap per user only at scale**, and why single-user/self-hosted economics are far worse (the [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]] "bursty usage kills self-hosting" point).
	- **KV cache is the real capacity limit**: GQA cuts it 8× (210 GB → 26 GB/sequence), and PagedAttention plus the fact that real chats use **4–40k of a 200k window at ~20% duty cycle** is what turns a naive **6-user** ceiling into a practical **300–800 users/GPU**. Capacity is gated by **memory (KV cache), not FLOPs**.

- ## Cost Ladder (the punchline)
	- **Rental at scale**: \$4/hr ÷ ~300 users = **\$0.013/user-hr ≈ \$9.36/user-month** of *raw compute cost*. Compare to \$20/mo consumer subscriptions — even after harness, networking, prefill, and overhead, there is **large headroom**, consistent with API gross margins being high (Dylan Patel: "inference is cheaper than people assume; API margins are very high," [[2026-07-16-dylan-patel-podcast-ai-infra-memory-cpu-optics-power]]).
	- **Purchase amortization**: \$40k GPU ÷ 300 users = **\$133/user lifetime** vs \$6,667 at 6 users — a **~50× swing** purely from batching/utilization. Utilization, not chip price, dominates unit economics.
	- **Sensitivity**: these are for a **32B FP8** model. Frontier models are ~100× larger (multi-GPU, more HBM, lower batch per GPU per the [[2026-07-07-interconnect-first-inference-latency-over-bandwidth-lpddr]] sharding math), so per-user cost scales up — but the *shape* (bandwidth-bound, batching-driven, KV-cache-gated) holds.

- ## Investment Read-Throughs
	- **Frontier-lab margins (Anthropic/OpenAI)**: raw serving cost of a good model at ~\$0.01/user-hr underpins the claim that **token APIs run high gross margins** and that "subsidized subscription" narratives are overstated — the caveat being that *frontier* models cost more to serve than the 32B example, and that R&D/training (not inference) is the cash drain. Supports the [[2026-07-16-dylan-patel-podcast-ai-infra-memory-cpu-optics-power]] view over the pure commoditization bear.
	- **Bullish HBM/DRAM ([[DRAM-memory-ssd-index-thesis]])**: the whole cost model is **memory-bandwidth- and KV-cache-bound**, not compute-bound. More context, more concurrency, and bigger models all scale **memory** demand faster than FLOPs — the mechanistic case for HBM content growth per accelerator (same conclusion as [[2026-07-06-carmack-nand-flash-vs-hbm-ai-inference-memory]] and the reasoning/KV-cache explosion in the Patel memo).
	- **Utilization is the moat for inference providers ([[$NVDA]] customers, neoclouds)**: the 50× per-user cost swing from batching means **whoever fills the batch wins** — favors high-utilization at-scale servers (hyperscalers, CoreWeave-style neoclouds, frontier labs) over fragmented self-hosting. Reinforces the [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]] point that open weights don't trivially undercut hosted APIs on cost unless you can keep GPUs saturated.
	- **The interconnect-first / LPDDR challenge gains force**: since decode wastes B200 compute waiting on memory, designs that **balance compute to memory bandwidth** (LPDDR + low-latency mesh) attack exactly the inefficiency this napkin math exposes — see [[2026-07-07-interconnect-first-inference-latency-over-bandwidth-lpddr]].
	- **Caveats**: illustrative single-model, single-GPU math; excludes prefill cost, networking, redundancy, load-balancing, and the reality that frontier models shard across many GPUs at lower per-GPU batch. Directional, not a P&L — but the **memory-bound, batching-driven** structure is the durable takeaway.
