tags:: [[inference]], [[GPU]], [[HBM]], [[memory-bandwidth]], [[KV-cache]], [[throughput]], [[interactivity]], [[tokenomics]], [[$NVDA]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## The GPU inference trade-off between interactivity and throughput
	- **Source**: the owner's Q&A with an AI assistant, November 2026. The numbers are illustrative, not benchmarks.
	- **Thesis**: Generating tokens is limited by memory bandwidth, so batching users together is almost free up to the point where compute and memory bandwidth are both saturated (the "knee"). Below the knee, batching improves throughput and interactivity together. Past the knee, bigger batches raise tokens per second per GPU but slow every user. The industry's interactivity-vs-throughput curve is therefore a **speed-vs-cost frontier, normalized per GPU**.

- ## Why the trade-off exists
	- **Memory bandwidth is the bottleneck**: producing each token requires moving billions of model weights from HBM to the compute cores. At batch size 1 the GPU spends almost all its time moving weights while the cores sit idle. That one user gets peak speed, but the hardware's total output is tiny.
	- **Batching unlocks throughput**: with many users in a batch, the GPU loads the weights once and reuses them for every request. This amortizes the memory transfer, puts idle compute to work, and makes total tokens per second rise sharply.
	- **Batching eventually hurts interactivity**: as the batch grows, each decoding step gets heavier. The GPU must read a larger combined KV cache (each user's stored context) and do more matrix math. Once the workload becomes compute-bound or hits KV-cache bandwidth limits, every added user lengthens the time between tokens for everyone in the batch.

- ## Worked example: 10 concurrent requests on one GPU
	- | Approach | Assumption | What each user experiences | Time to finish all 10 |
	  |---|---|---|---|
	  | **1. Batch all 10 together** | Compute and memory bandwidth are balanced and both saturated | All 10 users wait about 10 seconds. A larger KV cache to read makes it closer to 12 seconds | About 10–12 seconds |
	  | **2. Serve one at a time** | Memory-bound. The same weights are moved 10 times instead of once, so 10× the data moves | 10, 20, 30, … 100 seconds | 100 seconds |
	- **Batching wins on both metrics here**, because it removes the queuing delay. The example stops exactly at the knee, where batching is nearly free.

- ## Where the trade-off actually shows up
	- | Regime | What happens | Effect on per-user speed | Effect on tokens/sec per GPU |
	  |---|---|---|---|
	  | Up to the knee (batch 1 → 10 in the example) | Weight reads get amortized, and only the KV cache adds work | Small loss | **Large gain** |
	  | Past the knee, same GPU (batch 10 → 50 or 100) | Each step takes longer because of heavier compute and KV-cache reads | **Every user slows down** | Keeps rising toward the hardware's peak |
	  | Splitting one request across 8 GPUs (tensor parallelism) | The user gets about 8× the memory bandwidth, but inter-GPU communication and smaller per-GPU workloads add overhead | **Much faster** | **Drops** |
	- **The comparison is apples-to-apples**: benchmarks report throughput per GPU (tokens/sec/GPU) and divide multi-GPU output by the number of GPUs. The curve is then a pure speed-vs-cost frontier: how much hardware efficiency you give up to make each user's experience faster. Faster responses can always be bought with smaller batches across more GPUs, but throughput per dollar falls.

- ## Related in the repo
	- **The measured curve**: SemiAnalysis InferenceMAX plots tokens/sec/GPU against tokens/sec/user for DeepSeek R1 on GB200/GB300 NVL72 vs. H100 ([[2026-05-20-deepseek-r1-token-throughput-per-gpu-vs-interactivity]]). Google claims "full pareto frontier leadership" on this kind of curve for TPU v7 in agentic workloads ([[2026-11-18-trainium-tpu-native-pytorch-backends-privateuse1]]).
	- **Which end of the curve matters more**: one forecast has inference shifting from about 50/50 background vs. real-time to 90/10 background, which would move the optimization target toward throughput ([[2026-07-18-napkin-llm-inference-cost-serving-economics]]).
	- **KV cache and memory bandwidth in depth**: [[2026-09-12-pmpp-cpu-vs-gpu-design-kv-cache-memory-bandwidth]] and [[2026-07-07-interconnect-first-inference-latency-over-bandwidth-lpddr]].
