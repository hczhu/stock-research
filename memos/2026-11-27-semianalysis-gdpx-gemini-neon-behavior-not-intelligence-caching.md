tags:: [[$GOOGL]], [[Gemini]], [[Anthropic]], [[OpenAI]], [[$META]], [[SpaceX]], [[benchmarks]], [[GDPx]], [[KV-cache]], [[prompt-caching]], [[tokenomics]], [[SemiAnalysis]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-27
file-updated-at:: 2026-11-27

- ## SemiAnalysis on Gemini 4 Neon: liked for its behavior more than its intelligence, and costlier to run because of weak caching
	- **Source**: user-provided excerpt, late November 2026. It refers to **GDPx** and the **Tokenomics Model**, both SemiAnalysis products, so it appears to be a SemiAnalysis follow-up to its GDPx benchmark ([[2026-11-06-semianalysis-gdpx-frontier-agent-performance]]).
	- **Thesis (the author's)**:
		- **Not the leader on hard work**: Gemini 4 Neon doesn't lead on GDPx's hardest domains. OpenAI's **6.2 Astra** and Anthropic's **Fable 5.2** beat it on most of them.
		- **Why it's popular**: its "overwhelmingly positive reception" is largely about **model behavior, not intelligence**. It is cheerful and pleasant to talk to, like GPT-4o was.
		- **The race**: Anthropic and OpenAI remain **in a tier of their own**. Google is a **distant third** in its own tier. Meta, SpaceX, Moonshot, Alibaba and others are fighting for fourth.
		- **Cost**: Neon is **unnecessarily expensive to run** because Google's prompt caching lags its rivals'.

- ## Who leads which GDPx domain
	- | Domain | Leader | Note |
	  |---|---|---|
	  | Recursive self-improvement (RSI) | **6.2 Astra** (OpenAI) | "Significantly outperforms" Neon |
	  | Materials science | **6.2 Astra** | Same |
	  | Hardware design | **6.2 Astra** | Same. In the November 1 GDPx, Opus 5.5 led this |
	  | Chip design | **Fable 5.2** (Anthropic) | "Dominates" |
	  | Software engineering | **Fable 5.2** | In the November 1 GDPx, Gemini 4 Carbon narrowly led this |
	  | Quant trading | **Fable 5.2** | |
	  | Biology | **Gemini 4 Neon** | Top score, but "likely due to more lenient safety classifiers." Neon's cyber classifiers are *stricter* than other Google models' |
	- **Changes since the November 1 GDPx** (memo's reading):
		- OpenAI's Astra kept its RSI and materials lead and added hardware design.
		- Anthropic's newer Fable 5.2 took software engineering from Google and kept chip design and quant trading.
		- Google again leads only biology, and the authors attribute that to safety filters rather than capability, as they did with Carbon.

- ## Prompt caching makes Neon more expensive
	- **What was measured**: the authors compare **theoretical cache hit rates**, meaning the share of cacheable input tokens actually served from cache. That isolates the quality of each provider's caching stack from how a particular workload is structured.
	- | Scenario | Cost of running Neon on GDPx | vs. actual |
	  |---|---|---|
	  | Neon's actual cache hit rate | **\$15,286** | — |
	  | At Opus 5.5's cache hit rate | **\$12,536** | **about −18%** |
	  | At 6.2 Astra's cache hit rate | **\$10,403** | **about −32%** |
	- *Memo calculation*: \$12,536 ÷ \$15,286 = 0.82 and \$10,403 ÷ \$15,286 = 0.68, consistent with the stated savings.
	- **Google is catching up**: it shipped a caching update the same day. Neon's cache hit rate rose another **4.5%**, which the authors say would cut this bill by about **17–18%**, roughly closing the gap to Opus 5.5. The authors expect the gap to keep closing, because "improving an inference serving stack is also something models are rapidly becoming superhuman at."

- ## How it fits the developer reports
	- **DHH and Rauch**: earlier this week both praised Neon ([[2026-11-23-dhh-gemini-4-neon-coding-agent-harness]], [[2026-11-23-google-gemini-neon-vs-opus-rauch-personal-eval]]).
		- DHH called Neon a "quiet cat" whose results were "perfect."
		- In Rauch's personal eval, Neon won mainly on **fewer user-dissatisfaction follow-ups**, while Opus led on **tool reliability and speed**. Restricted to interactive work, the two **tied**.
	- **SemiAnalysis's reading fits that evidence**: Neon wins on how working with it **feels**, not on hard capability. Note that SemiAnalysis describes Neon as cheerful, with liberal exclamation marks, while DHH describes it as quiet while it works. Both are about style, but they point in different directions.
	- **Caching economics**: cache reads dominate agent bills, and cache hit rate is the main cost driver ([[2026-11-20-kv-cache-reads-llm-inference-gross-margin]]). An 18–32% cost penalty from weaker caching matters directly to agent builders choosing a model.

- ## Memo's reading
	- **For Google**: a distant-third ranking from SemiAnalysis is far more cautious than the developer enthusiasm of the past week and Google's Q3 claim that it closed the coding gap ([[GOOG-2026-Q3]]). But being popular to use still has commercial value, as GPT-4o showed for consumer engagement. Google's caching fix shows its serving costs are improvable.
	- **For Anthropic and OpenAI**: the two-leader view supports their pricing power in high-value work such as chip design, software engineering, quant and RSI. That matches the gateway data showing Anthropic holding the most proprietary spend ([[2026-11-25-ai-gateway-model-mix-spend-vs-tokens-databricks-vercel-openrouter]]).
	- **Caveats**:
		- GDPx weights 11 domains chosen by SemiAnalysis.
		- Safety classifiers move domain rankings.
		- Per-domain scores and the full leaderboard weren't in the excerpt.
