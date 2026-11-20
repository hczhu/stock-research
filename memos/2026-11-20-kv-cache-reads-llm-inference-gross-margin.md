tags:: [[Anthropic]], [[OpenAI]], [[inference]], [[KV-cache]], [[tokenomics]], [[gross-margin]], [[pricing]], [[coding-agents]], [[agents]], [[open-weights]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-20
file-updated-at:: 2026-11-20

- ## Why LLM inference is so profitable: agents pay full price for cache reads that cost labs almost nothing
	- **Source**: Diogo, "(KV) Cache Rules Everything Around Me," *Complete Skeptic* (Substack), September 9, 2026 (user-provided PDF). The author simulated costs by replaying **Nvidia's Open-SWE-Traces** coding-agent trajectories at list prices, with cache writes at 1.25× the input price. Some chart values are cut off at the page edge and are marked where reconstructed.
	- **Thesis**: an agent re-reads its whole context on every tool call, so **cache reads are the largest part of an agent's bill**: about **67% with perfect caching**, while output tokens are only 9–18%. The author argues cache reads cost the provider **close to nothing** to serve, because the KV cache already sits in memory and its cost is mostly covered by output-token pricing. As workloads shift to agents, more of every bill is near-pure margin. The author says this is how labs' inference margins keep climbing while models commoditize.

- ## Where an agent's bill actually goes
	- | Cost line | What developers assume | What a coding agent actually costs (Fable 5, 100% cache hit rate) |
	  |---|---|---|
	  | Output tokens | **75%** | About 18% |
	  | Input tokens | 18.8% | 12% |
	  | Cache write premium | 4.7% | 3% |
	  | **Cache reads** | 1.5% | **67%** |
	- **Why cost grows faster than the session**: an agent is a loop. With a context of N tokens and T tool calls, it processes about **N × T input tokens** to produce comparatively few output tokens. N grows every turn, so a session's cost grows **quadratically** with its length, and faster still with more tool calls.
	- **A second estimate**: Martin Alderson's model of a 100-turn session starting from 60K tokens of context had cache reads at **about 76%** of an Opus 5 bill.

- ## The cache hit rate drives the bill
	- **Simulated workload at Fable 5 prices**:
		- | Cache hit rate | Total cost | Cache writes | Cache reads | Output |
		  |---|---|---|---|---|
		  | 89% (Claude Code's reported rate) | **\$1.97M** | 58% (about \$1.1M) | 32% (about \$0.6M) | 9% (about \$0.2M) |
		  | 100% (perfect) | **\$1.07M** | 15% (about \$0.2M) | 67% (about \$0.7M) | 18% (about \$0.2M) |
		- The 89% case costs **84% more** than perfect caching. Even moving from 95% to 98% saves about 17% of the bill.
	- **Cache hit rates by coding client**, measured by the OpenCode team on DeepSeek traffic:
		- | Client | Cache hit rate |
		  |---|---|
		  | ZCode | 98.60% |
		  | OpenCode V2 | 97.86% |
		  | Cursor | 97.84% |
		  | Kimi Code CLI | 97.64% |
		  | Pi | 96.98% |
		  | Codex | 96.66% |
		  | Kilo Code | 95.73% |
		  | OpenCode V1 | 95.69% |
		  | Claude Code / CLI | 89.31%; others have measured about 95% |
	- **Same workload priced by model** (100% cache hit rate; cache reads are the largest part of each bar):
		- | Model | Cost |
		  |---|---|
		  | Fable 5 | About \$1.07M (cut off on the chart; matches the table above) |
		  | GPT-5.6 Sol | \$552K |
		  | Opus 4.8 | \$533K |
		  | GPT-5.6 Terra | \$276K |
		  | GLM 5.2 | \$221K |
		  | Sonnet 5 | \$213K |
		  | GPT-5.6 Luna | \$110K |
		  | Haiku 4.5 | \$107K |

- ## Why cache reads are nearly free to serve
	- | Step | What it costs the provider | How it is priced |
	  |---|---|---|
	  | **Prefill** (input tokens) | **Compute**, in proportion to the number of tokens. A cache write is a prefill whose KV cache (preprocessed activations) is kept | Input price, plus a 1.25× premium for cache writes |
	  | **Decode** (output tokens) | **Memory bandwidth**: every output token reads the whole KV cache from HBM. This is the real bottleneck of inference | Output costs about **5× input** |
	  | **Tool-call pause** | Only holding the KV cache in memory. It uses neither compute nor HBM bandwidth, the two resources inference is actually short of | Charged again as **cache reads** when the agent resumes |
	- **The author's claim**: the cost of re-reading the context is "primarily already included in the price of output tokens," so cache-read revenue is close to pure margin.
	- **Evidence from provider behavior**:
		- On the Claude API, **cache reads don't count toward input-token rate limits**. Rate limits protect capacity, so this signals how little a cache read costs Anthropic.
		- OpenAI ran automatic prefix caching **for over a year without charging for cache writes**. Its 1.25× cache-write premium arrived only with GPT-5.6, to match Anthropic.
		- Fable 5.1 cut the cache-read price from **\$1.00 to \$0.25 per million tokens**, which the author reads as a sign of room for further cuts.

- ## What it explains
	- **Rising margins despite commoditization**: open-weight models' share of tokens on Vercel's AI Gateway rose from about **11% in April 2026 to about 36% in July**, but their share of spend only from about **3% to 9%** (values read from the chart). The author says labs' inference margins kept climbing anyway because agentic workloads mean more tool calls, more cache reads and more profit.
	- **"Subsidized" subscriptions**: SemiAnalysis found the \$200/month Claude plan can yield up to **\$8,000/month** of API-equivalent tokens, and OpenAI's up to **\$14,000/month**. That is a 40–70× subsidy at list price. The author says it looks insane until you remember that **90%+ of a coding agent's tokens are cache reads** whose true cost is a small fraction of the sticker price.
	- **Self-hosting agents**: running an open-weight model yourself is the only way to keep the cheapness of the KV cache rather than handing it to the lab, at least until cache-read prices fall further.
	- **Model routing backfires for agents**: KV caches are not shared between models, so handing a long context to a cheaper model means paying to write the whole context again.
		- **The author's example**: a 100K-token Opus 5 session generates 1K tokens and gets 3K back from a tool.
		- **Staying on Opus costs \$0.100**: a \$0.050 cache read, \$0.025 of output and a \$0.025 cache write.
		- **Routing to Sonnet costs about \$0.285** (memo calculation from the visible rows): a \$0.250 cache write to load the context into Sonnet, \$0.010 of output and \$0.025 to re-cache on Opus.
		- The "easy" step costs **almost 3× more**, and a weaker model did it.
		- Subagents help only when they don't need the parent's context. A subagent told to "search for X and report back in 200 tokens" keeps the search output out of the parent's context.
	- **Advice to agent builders**: measure the cache hit rate and the number of tool calls. Tool-call count matters more than tokens per call.

- ## Related in the repo
	- **Anthropic's margins**: Anthropic reports **85% gross margin** on serving models, while commentary notes R&D makes fixed costs behave like marginal costs ([[2026-10-26-anthropic-s1-financials-compute-economics]]). This memo explains one mechanism behind the high serving margin.
	- **Decode is limited by memory bandwidth**: [[2026-11-18-gpu-inference-interactivity-vs-throughput-tradeoff]] and [[2026-11-18-speculative-decoding-idle-compute-dedicated-inference]].
	- **KV cache as a memory market**: [[2026-07-16-weka-kv-cache-nand-inference-memory-podcast]].
