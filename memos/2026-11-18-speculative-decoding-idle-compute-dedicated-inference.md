tags:: [[inference]], [[speculative-decoding]], [[GPU]], [[memory-bandwidth]], [[KV-cache]], [[Fireworks]], [[Baseten]], [[Modal]], [[coding-agents]], [[tokenomics]], [[$NVDA]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Speculative decoding: turning idle GPU compute into faster tokens
	- **Source**: user-provided newsletter excerpt on inference engineering, November 2026. It cites Fireworks' Dmytro Dzhulgakov, Baseten's book *Inference Engineering*, Modal, and Joe Barrow's "Why is Speculative Decoding Fast?". The newsletter's name was not given.
	- **Thesis**: Decoding leaves GPU compute idle because it is limited by memory bandwidth. Speculative decoding uses that idle compute to draft several tokens and verify them in one pass, which vendors say raises throughput **20–50%**. It only helps when compute is spare, so providers offer it on **dedicated deployments**, not shared inference. It works best on **code**, which the author calls one more reason coding is such a profitable and efficient use of inference.

- ## How it works
	- **The inefficiency**: generating one token means reading all the model's weights plus the KV cache (the stored attention state), yet each weight is used in only one small calculation. Memory bandwidth is the bottleneck and compute sits mostly idle.
	- **Draft, then verify**: a small, fast **speculator** proposes several draft tokens. The main model checks them all in one forward pass, the way it processes a prompt during prefill. It accepts the correct drafts and replaces the first wrong one with its own token.
		- In the source's example, the model accepts 2 of 3 drafts and corrects the third, so one pass yields three tokens instead of one.
	- **The economics of verification**: Dzhulgakov says verifying **15 tokens in one pass is only about 50% slower than generating one**. Speculation therefore pays when the speculator gets more than one token right per pass on average, and the author says that at **two or more** correct guesses, drafting more tokens is worth it.
	- **Key metric**: token acceptance, meaning how many drafts the main model keeps per pass. Vendors report it reaching **10+** in specialized cases.
	- **No effect on TTFT**: time to first token depends on prefill, so speculation speeds up the stream of tokens after the first one.

- ## Types of speculators
	- | Approach | How it works | Trade-offs |
	  |---|---|---|
	  | Smaller model from the same family | A small LLM drafts tokens one at a time | Must share the main model's vocabulary. Baseten's *Inference Engineering* says it must be at least **10× faster** than the main model to pay off. Most state-of-the-art systems no longer use it because other methods are faster |
	  | **DFlash**-style draft heads | A separately trained model reads the main model's hidden layers and guesses a fixed number of tokens ahead, **independently and in parallel** | Drafts much faster than a small model, which still decodes token by token. **DSpark** builds on DFlash to raise accuracy. The author calls speculator design "a very active area of research" |
	  | N-gram and prompt-lookup heuristics | Search the prompt for matching subsequences and predict what usually follows | Very cheap to run. Work well on predictable content such as code |

- ## How providers sell it
	- **Dedicated deployments only**: in shared inference, where many customers' requests are batched together, compute is already busy and speculation "strictly adds latency." Dedicated capacity belongs to one customer and is often underutilized, so spare compute is available.
	- **Provider approaches**:
		- Most providers let customers customize the speculator.
		- **Fireworks** tunes speculators for every dedicated deployment behind the scenes, without customers knowing.
		- **Modal** offers it as a per-request service.
		- Customers typically start with a strong custom speculator that can be tuned further.
	- **Coding is the best fit**: code is far more predictable than human language. Even simple speculators based on token co-occurrence statistics can predict long sequences accurately, and they are cheap enough that the speculation penalty is minimal.

- ## Related in the repo
	- **Why spare compute exists, and when it disappears**: below the batching "knee," decode leaves compute idle. Past it, compute is saturated ([[2026-11-18-gpu-inference-interactivity-vs-throughput-tradeoff]]). This matches the source's point that speculation helps dedicated deployments but adds latency in shared, heavily batched serving.
	- **The same idea built into the model**: Nvidia's Bryan Catanzaro describes multi-token prediction that predicts about five tokens at once for a roughly 4× speedup. He argues such efficiency gains expand token demand rather than cutting GPU spend ([[2026-07-02-mad-podcast-bryan-catanzaro-nvidia-nemotron-open-models]]).
	- **Earlier estimates**: Dan Fu cited about **2–3×** speedups from a small draft model when predictions are accepted, against inference utilization below 5% ([[2026-01-22-mad-podcast-dettmers-fu-gpu-scaling-agent-era]]). A GPU programming textbook describes speculative decoding as a special form of batching ([[2026-09-12-pmpp-cpu-vs-gpu-design-kv-cache-memory-bandwidth]]).
