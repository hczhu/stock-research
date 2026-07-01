tags:: [[$DDOG]], [[Datadog]], [[AI]], [[LLM]], [[agents]], [[inference]], [[enterprise-AI]], [[observability]], [[AI infrastructure]], [[OpenAI]], [[Anthropic]], [[$GOOGL]]

- **Source**: Datadog, [State of AI Engineering](https://www.datadoghq.com/state-of-ai-engineering/), 2026
- **Dataset**: LLM telemetry from more than a thousand Datadog customers using Datadog LLM Observability; results are biased toward Datadog's customer base, which skews cloud-native and infrastructure-mature.
- ## Bottom line
	- Datadog's report says production AI is becoming a **distributed-systems operations problem**: multi-model routing, prompt and context management, rate limits, retries, tool calls, service boundaries, evaluations, and cost control.
	- This is directly bullish for **LLM observability and AI platform engineering**. As agents move from demos to production, the pain shifts from "can the model answer?" to "can the whole AI system stay reliable, cheap, debuggable, and governed?"
	- For $DDOG, the most important read is that LLM Observability is not a side feature. The report frames agentic AI as a new observability surface with growing complexity, invisible drift, and production failure modes that map naturally to Datadog's core product DNA.
- ## Key data points
	- **Provider and model adoption**
	  
	  | Metric | Datadog finding | Investment read |
	  |---|---:|---|
	  | OpenAI provider share | 63% | Still the default provider, but no longer the only serious production option |
	  | OpenAI share one year prior | 75% | Share down, but absolute Datadog customer usage more than doubled |
	  | Google Gemini share gain | +20 percentage points YoY | Google is gaining production relevance in enterprise LLM fleets |
	  | Anthropic Claude share gain | +23 percentage points YoY | Anthropic is gaining quickly in production workloads |
	  | Organizations using 3+ models | >70% | Multi-model operations are now mainstream |
	  | Organizations using 6+ models | Nearly doubled | Model sprawl creates evaluation, governance, routing, and observability demand |
	  | Claude Sonnet 4.6 first-month adoption | 17% | Teams rapidly test new frontier models |
	  | Sonnet 4.5 adoption in March 2026 | 19% | Old models persist after successors launch |
	  | GPT-4o adoption in March 2026 | 22% | Deprecation and model retirement risk becomes operational tech debt |
	- **Frameworks, context, caching, and reliability**
	  
	  | Metric | Datadog finding | Investment read |
	  |---|---:|---|
	  | Agent framework adoption | >9% of organizations in early 2025 to almost 18% by early 2026 | Framework adoption nearly doubled; agent telemetry need rises with abstraction |
	  | Services using agentic frameworks | More than doubled YoY | AI logic is entering more production services |
	  | System prompts as share of input tokens | 69% | Scaffolding, policies, tool instructions, and guardrails dominate token cost |
	  | LLM call spans with cached-read input tokens | 28% among cache-supporting models | Prompt caching is materially underused |
	  | Context window growth | 128K tokens to as high as 2M tokens in some tiers | Context capacity is less scarce; context quality becomes the bottleneck |
	  | Average tokens per request | More than doubled YoY for median customers | Production agents are consuming more context |
	  | 90th-percentile token usage | Quadrupled YoY | Power users are driving much larger prompt/context loads |
	  | February 2026 LLM spans with errors | 5% | Reliability remains a production problem |
	  | February 2026 errors from rate limits | 60% | Provider capacity is a dominant failure mode |
	  | March 2026 LLM spans with errors | 2% | Error rate improved month to month |
	  | March 2026 errors from rate limits | Almost one-third; nearly 8.4M rate-limit errors | Rate limits remain a material production bottleneck |
	  | Agentic requests with one service call | 59% | Most production agents are still monolithic |
	  | Agentic requests with 3+ service calls | 18% | Multi-agent / distributed-agent architectures are still early |
- ## Main arguments
	- **Fact 1: Production teams are going multi-model**
		- The report shows that most production AI teams no longer standardize on one model.
		- The operational consequence is model routing, benchmarking, fallback, safety enforcement, and cost/latency optimization across providers.
		- Read-through: multi-model adoption favors **gateways, observability, and evaluation tooling**, and weakens the idea that one model provider captures all enterprise AI value.
	- **Fact 2: Model tech debt is compounding**
		- Teams adopt new releases quickly but retire old defaults slowly.
		- This creates fleets where multiple model versions remain active, each with its own quality, latency, cost, and regression profile.
		- Read-through: model deprecation and regression management become recurring platform work, not one-time migration events.
	- **Fact 3: Agent frameworks double adoption, but add opacity**
		- LangChain, LangGraph, Pydantic AI, Vercel AI SDK, and similar frameworks make agents easier to build.
		- They also hide execution paths, retries, tool fan-out, branching, and framework boilerplate under imports.
		- Read-through: framework growth is bullish for deep tracing, span-level telemetry, and workflow observability.
	- **Fact 4: System prompts dominate input tokens, while caching is underused**
		- With **69%** of input tokens coming from system prompts, agent scaffolding is a major cost center.
		- Only **28%** of eligible call spans show cached-read input tokens, meaning many calls still reprocess stable instructions.
		- Read-through: prompt engineering is becoming cost engineering; observability can identify reusable prefixes, cache misses, and prompt-layout waste.
	- **Fact 5: Bigger context windows do not remove the need for context engineering**
		- Context windows have expanded to as high as **2M tokens**, but Datadog says most teams do not approach model limits.
		- The bottleneck shifts from available context length to choosing, compressing, deduplicating, and ordering the right information.
		- Read-through: retrieval quality, summarization, context hygiene, and online evaluation matter more than simply buying longer-context models.
	- **Fact 6: Rate limits are the dominant production failure mode**
		- Rate limits caused **60%** of LLM errors in February 2026 and nearly one-third in March 2026.
		- In March, Datadog observed nearly **8.4M** rate-limit errors.
		- Read-through: production agent reliability is constrained by provider capacity, concurrency, retries, and runaway loops, not just model quality.
	- **Fact 7: Most agents are still monolithic**
		- **59%** of agentic requests made only one service call.
		- Only **18%** made three or more service calls.
		- Read-through: the market is early. As agents become more distributed, demand for service maps, trace propagation, tool-aware observability, and cross-service debugging should rise.
- ## Investment implications
	- **Datadog / observability**
		- This report is strategically favorable for $DDOG because AI production work creates new observability objects: prompts, model calls, tool calls, context windows, cached tokens, retries, rate-limit failures, and eval traces.
		- Datadog's advantage is that AI apps are becoming normal distributed systems with abnormal failure modes. Existing APM, logs, traces, service maps, and cost monitoring can be extended into LLM Observability.
		- The report also supports an attach-rate thesis: customers already instrumented with Datadog are natural buyers of AI observability as their services start making LLM calls.
	- **OpenAI / Anthropic / Google**
		- OpenAI remains the production share leader at **63%**, but the share decline from **75%** plus Gemini/Claude gains suggests enterprise customers are diversifying.
		- Anthropic and Google are both gaining production adoption, but multi-model behavior means share gains may not translate into winner-take-all economics.
		- Model providers still face operational trust issues: rate limits, deprecations, model churn, and latency/cost variability can push enterprises toward gateways and fallback systems.
	- **AI infrastructure**
		- More tokens per request, higher context usage, and more agent loops support the inference-demand thesis.
		- Prompt caching underuse is a counterweight: better caching and context engineering can lower token demand per task.
		- Rate-limit errors show that capacity remains tight enough to affect production reliability, which supports continued investment in inference capacity and routing/fallback infrastructure.
	- **Developer tools / agent platforms**
		- Framework adoption almost doubling suggests developers are standardizing around agent abstractions.
		- But if frameworks create hidden cost and latency, customers will demand tools that make framework behavior inspectable.
		- The tooling opportunity is less "build agents" and more "operate, evaluate, route, debug, and govern agents."
- ## Product and market read-through
  | Theme | What the data says | Who benefits |
  |---|---|---|
  | Multi-model production | >70% of orgs use 3+ models | LLM gateways, eval platforms, observability vendors |
  | Model sprawl | 6+ model usage nearly doubled | Governance, model inventory, deprecation tooling |
  | Agent framework growth | Adoption nearly doubled YoY | Framework ecosystems, but also telemetry vendors |
  | Prompt cost center | 69% of input tokens are system prompts | Prompt optimization, caching, context engineering |
  | Caching gap | Only 28% of eligible spans use cached-read tokens | Observability and cost tooling that surfaces cache misses |
  | Context explosion | Median request tokens more than doubled; 90th percentile quadrupled | Inference infra, context tools, retrieval quality systems |
  | Capacity failure mode | Rate limits dominate errors | Capacity planning, fallback routing, model gateways |
  | Early agent architecture | 59% single-service calls; 18% 3+ calls | Future growth in distributed agent observability |
- ## Risks and caveats
	- Datadog's dataset is not the whole market. It skews toward cloud-native, infrastructure-mature organizations already instrumenting production systems.
	- The report measures Datadog customer telemetry, so it may overstate the importance of observability practices relative to the broader market.
	- Better prompt caching and context engineering could reduce token waste, which is good for enterprise AI margins but can modestly temper the most aggressive inference-demand assumptions.
	- Multi-model adoption weakens model-provider monopoly power, but it does not automatically mean buyers have pricing power if capacity remains constrained.
- ## Links to related notes
	- [[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]]
	- [[2026-06-03-ai-memory-wall-agentic-ai-dram-demand]]
	- [[2026-05-26-compute-crunch-token-demand-vs-supply]]
	- [[Datadog-DDOG-thesis]]