tags:: [[observability]], [[open-source]], [[Kubernetes]], [[VictoriaMetrics]], [[Grafana]], [[ClickHouse]], [[$DDOG]], [[self-hosting]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Choosing a lightweight observability stack for a 3-node cluster: why VictoriaMetrics won
	- **Source**: user-provided write-up comparing observability stacks for a tiny personal Kubernetes cluster. The author and date were not given. Resource savings are the vendors' own benchmark claims, as quoted by the author.
	- **Thesis**: When memory is the binding constraint, efficiency decides the choice. The **VictoriaMetrics + VictoriaLogs** stack keeps compatibility with Prometheus and Grafana tooling while using about 2–3× less RAM and disk. Stacks built on ClickHouse or many backends are ruled out, and the free SaaS tier is ruled out by its caps and because data leaves the house.

- ## The constraint
	- Three nodes with **8 GB of RAM each**. Every node is also a control plane and already runs **Longhorn**, Kubernetes distributed block storage. Whatever monitors the cluster has to stay small.

- ## Options compared
	- | Option | What it is | Verdict for this cluster |
	  |---|---|---|
	  | **VictoriaMetrics** (chosen, for metrics) | Prometheus-compatible time-series database | Serves the same PromQL, dashboards and alerting rules as Prometheus with **about 1.7–3× less RAM** and less disk, by its own benchmarks |
	  | **VictoriaLogs** (chosen, for logs) | Log store from the same vendor | Needs **about 2–3× less RAM and disk** than Loki at homelab volumes, and **no object storage** |
	  | kube-prometheus-stack | The default Prometheus-operator bundle that most guides use | Same functionality as VictoriaMetrics, at a higher resource cost |
	  | Loki | Grafana's log store | Heavier than VictoriaLogs at this scale, and depends on object storage |
	  | Grafana Cloud free tier | Hosted SaaS, so nothing runs on the cluster | Capped at **10K active series and 14 days of retention**, and the data leaves the house |
	  | SigNoz, Coroot, full Grafana LGTM stack | Full-featured platforms built on ClickHouse or several backends | **Too heavy** for 8 GB nodes |
	  | OpenObserve | Light, all-in-one binary | Viable, but brings its own collector and has a much smaller community |

- ## Related in the repo
	- **Observability pricing**: Grafana Labs is the main challenger to Datadog's list pricing, competing on the bill rather than the product ([[2026-09-16-repvue-observability-pricing-power]]). The memo's reading: this write-up shows the same cost-first logic at the smallest scale, where an efficient backend compatible with Prometheus beats the default stack.
	- **More software to watch**: AI coding increases the volume of software that has to be operated and monitored ([[2026-11-09-ben-congdon-agentic-monitoring-observability]]).
