tags:: [[GPU]], [[inference]], [[HBM]], [[KV-cache]], [[memory-bandwidth]], [[throughput]], [[interactivity]], [[$NVDA]], [[semiconductor]], [[ai-model:Gemini Neon]], [[ai-effort:medium]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## GPU interactivity vs. throughput trade-off in LLM inference
	- **Source**: User-provided technical Q&A notes on LLM decode batching, memory bandwidth, and per-GPU normalization.
	- **Thesis**: LLM token generation is bottlenecked by HBM bandwidth, creating a speed-versus-cost frontier where batching lifts per-GPU throughput almost for free up to the compute-memory saturation knee, after which higher per-user interactivity requires smaller batches or multi-GPU tensor parallelism that reduces tokens/sec/GPU.

- ## Why the trade-off exists
	- **Memory bandwidth bottleneck**: generating one token requires loading billions of model weights from HBM to compute cores. At batch size 1, the GPU spends most of its time moving weights while compute cores sit idle—yielding peak interactivity for one user but minimal total output.
	- **Batching unlocks throughput**: grouping multiple users into a batch loads model weights once and reuses them across requests, amortizing memory transfers and engaging idle compute cores so total tokens/sec rises sharply.
	- **Why batching hurts interactivity**: larger batches increase both combined KV-cache reads from memory and matrix math per decoding step. Once the workload shifts from memory-bound to compute-bound (or hits KV-cache bandwidth limits), each added user directly lengthens time between tokens for every user in the batch.

- ## Concrete example: serving 10 concurrent requests on one GPU
	- | Serving strategy | Weight transfers from HBM | Perceived user latency | Total completion time | Trade-off behavior |
	  |---|---|---|---|---|
	  | **Case 1: Batched (Batch 10)** | Loaded once, reused across 10 users | ~10s for all 10 users (~12s with larger KV-cache reads) | ~10s–12s | Compute and memory bandwidth balanced; eliminates queuing delay |
	  | **Case 2: Sequential (Batch 1)** | Loaded 10× (10× data moved) | 10s, 20s, 30s, …, 100s | 100s | Memory-bandwidth bottlenecked; queuing degrades both metrics |
	- **Why the trade-off does not appear here**:
		- **Stops at the "free lunch" knee**: up to the balance point where compute and memory bandwidth saturate together (Batch 10), batching beats sequential serving on both throughput and interactivity by removing queuing delay, with only minor KV-cache overhead.
		- **Trade-off begins past saturation**: pushing beyond Batch 10 to Batch 50 or 100 to maximize hardware utilization directly slows per-user token generation.

- ## Why the curve is apples-to-apples (per-GPU normalization)
	- **Same-GPU trade-off**: on a single GPU past the saturation knee (e.g., Batch 10 → Batch 50), individual user speed drops from heavier compute and KV-cache reads while total tokens/sec climbs toward theoretical peak.
	- **Multi-GPU normalization (Tensor Parallelism)**: splitting one request across 8 GPUs gives that user ~8× the memory bandwidth for higher interactivity, while dividing total output by 8 (`tokens/sec/GPU`) reflects inter-GPU communication overhead and smaller per-GPU workloads.
	- **Economic frontier**: normalizing throughput per GPU compares one GPU running large batches against multiple GPUs running small batches (or tensor-parallel requests), turning the curve into a pure speed-versus-cost frontier showing how much hardware efficiency is traded for faster per-user speed.

- ## Related notes in the repo
	- DeepSeek R1 throughput-vs.-interactivity chart: [[2026-05-20-deepseek-r1-token-throughput-per-gpu-vs-interactivity]].
	- Ultra-high interactivity and Pareto-frontier trade-off on GPUs: [[2026-08-09-semianalysis-tilert-inferencex-gpu-vs-dataflow-asic]].
	- GPU memory bandwidth and KV-cache mechanics: [[2026-09-12-pmpp-cpu-vs-gpu-design-kv-cache-memory-bandwidth]].
	- Concurrency, bandwidth ceilings, and HBM stack trade-offs: [[2026-09-14-semianalysis-four-high-hbm-rubin-ultra-capacity-cut]].
