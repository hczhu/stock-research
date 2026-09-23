file-created-at:: 2026-05-20

# Claude Opus 4.6 Provider Performance (OpenRouter)

Source: OpenRouter cross-provider performance dashboard. Metrics are averages across all locations.

## Metric Definitions

- **Throughput**: Tokens generated per second (higher = better)
- **Latency (TTFT)**: Time To First Token — how quickly the model starts responding (lower = better)
- **E2E Latency**: End-to-end latency — total time from sending a request to receiving the complete response (TTFT + time to generate all remaining tokens). For long responses E2E will be much larger than TTFT; for short responses they converge. (lower = better)
- **Tool Call Error Rate**: % of tool/function calls that fail (lower = better)
- **Structured Output Error Rate**: % of structured output (JSON schema) requests that fail (lower = better)

---

## Claude Opus 4.6 (Standard)

| Metric | Provider | Avg Value |
|--------|----------|-----------|
| Throughput | Google Vertex | 45 tok/s |
| Throughput | Google Vertex (Europe) | 39 tok/s |
| Throughput | Amazon Bedrock | 38 tok/s |
| Latency (TTFT) | Google Vertex | 1.39 s |
| Latency (TTFT) | Google Vertex (Europe) | 1.54 s |
| Latency (TTFT) | Anthropic | 2.05 s |
| E2E Latency | Anthropic | 6.60 s |
| E2E Latency | Amazon Bedrock | 8.04 s |
| E2E Latency | Google Vertex (Europe) | 8.66 s |
| Tool Call Error Rate | Amazon Bedrock | 0.56% |
| Tool Call Error Rate | Google Vertex | 0.60% |
| Tool Call Error Rate | Azure | 0.75% |
| Structured Output Error Rate | Azure | 1.40% |
| Structured Output Error Rate | Claude Platform on AWS | 6.87% |
| Structured Output Error Rate | Anthropic | 7.07% |

---

## Claude Opus 4.6 (Fast)

Fast mode uses the same Claude Opus 4.6 model with faster output. Only available via Anthropic directly.

| Metric | Provider | Avg Value |
|--------|----------|-----------|
| Throughput | Anthropic | 66 tok/s |
| Latency (TTFT) | Anthropic | 0.98 s |
| E2E Latency | Anthropic | 3.25 s |
| Tool Call Error Rate | Anthropic | 1.74% |
| Structured Output Error Rate | Anthropic | 30.80% |

---

## Key Takeaways

| Goal | Best Choice |
|------|-------------|
| Highest throughput (standard) | Google Vertex (45 tok/s) |
| Lowest TTFT (standard) | Google Vertex (1.39 s) |
| Lowest E2E latency (standard) | Anthropic (6.60 s) |
| Lowest tool call error rate | Amazon Bedrock (0.56%) |
| Lowest structured output error rate | Azure (1.40%) |
| Overall fastest (all metrics) | Opus 4.6 Fast on Anthropic — 66 tok/s, 0.98 s TTFT, 3.25 s E2E |

**Caveat**: Fast mode has a very high structured output error rate (30.80% vs ~1–7% for standard), making it unsuitable for JSON schema–constrained outputs. For tool-heavy or structured-output workloads, use standard mode on Amazon Bedrock or Azure.
