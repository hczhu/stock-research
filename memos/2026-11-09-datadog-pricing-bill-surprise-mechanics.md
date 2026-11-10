tags:: [[$DDOG]], [[Datadog]], [[observability]], [[SaaS]], [[pricing]], [[OpenTelemetry]], [[customer-experience]]
file-created-at:: 2026-11-09

- ## Datadog Pricing — How Telemetry Growth Becomes a Budget Surprise
	- **Source** — User-supplied pricing observations, checked against Datadog billing documentation and AWS networking documentation on November 9, 2026. Public documentation describes multiple billing models; the customer's contract determines the applicable model and allowances.
	- **Thesis — analytical inference.** Datadog monetizes several dimensions of the same application environment. Hosts, telemetry volume, retention, metric cardinality, and product attachment can grow independently, making a simple host-count budget unreliable. This supports expansion revenue but can also trigger optimization, renegotiation, and migration.

- ## Four Mechanisms That Catch Buyers Off Guard
	- | Mechanism | What the buyer may miss | Verified qualification |
	  |---|---|---|
	  | Ingestion plus indexing | Sending telemetry and retaining selected data for historical search can create separate charges. | Logs and spans have different units and allowances. APM includes allocations, and not all ingested data must be indexed. |
	  | Custom metrics and cardinality | Adding a high-cardinality tag can create many separately counted metric series without adding hosts. | Applies to the cardinality-based model. Metric Name Pricing uses different dimensions; supported OTel integration metrics can be included at no extra cost. |
	  | APM plus infrastructure | The same machine can appear under both product charges. | This applies to APM purchased with Infrastructure Monitoring attached. Standalone APM is also available. |
	  | External network charges | Transporting telemetry can add cloud-provider charges beyond the Datadog invoice. | Amounts depend on provider, route, region, networking services, and allowances. Egress is not automatically charged on every route. |
	- The sections below provide the sources and contract distinctions behind each row.

- ## Ingestion and Indexing — Separate Meters on One Data Pipeline
	- Datadog bills ingested logs by gigabytes and indexed logs by event count at the selected retention rate. Reducing the indexed subset can lower retention/search charges while ingestion charges remain. Describing this as “paying twice” captures the customer's budgeting frustration, but the two charges meter different processing stages and units. [Datadog billing definitions](https://docs.datadoghq.com/account_management/billing/pricing/)
	- Standard log indexes have no exclusion filter by default, so every matching log is indexed unless configured otherwise. Debug verbosity or a newly connected service can therefore increase both ingestion and indexed-event usage. [Datadog index configuration](https://docs.datadoghq.com/logs/log_configuration/indexes/)
	- APM separately meters ingested spans and indexed spans, with included per-host allocations pooled across APM hosts. Overage depends on those allowances and the contract. Sampling and retention choices determine which spans proceed through each stage. [Datadog APM pricing and allowances](https://www.datadoghq.com/pricing/)
	- **Analytical inference.** A buyer budgeting only on incoming GB can miss the cost of event count and retention. A growth-driven bill can later reverse when customers prune indexing or shorten retention, even if application demand stays strong.

- ## OTel and Custom Metrics — Tag Design Can Become a Financial Decision
	- Under cardinality-based billing, a custom metric is a unique combination of metric name and tag values, including the host tag. Usage is averaged across hourly distinct-series counts over the month. Pro includes 100 ingested and 100 indexed custom metrics per host; Enterprise includes 200 of each, pooled across the infrastructure. The “100 free metrics” shorthand therefore describes a plan allowance rather than a universal entitlement. [Datadog custom-metrics billing](https://docs.datadoghq.com/account_management/billing/custom_metrics/)
	- User IDs, request IDs, and session IDs used as metric dimensions can proliferate distinct series. A single business measurement can produce many billable combinations. Datadog explicitly warns against unbounded grouping for log-derived custom metrics. [Datadog log-based metrics guidance](https://docs.datadoghq.com/logs/log_configuration/logs_to_metrics/)
	- OTel attributes do not all become separately billable custom metrics merely because they exist. Supported receiver metrics can be collected at no extra cost; incorrect integration configuration can cause classification as custom metrics. The key questions are the metric's classification and which attributes become its dimensions. [Datadog OTel integrations](https://docs.datadoghq.com/opentelemetry/integrations/)
	- **Contract evolution matters.** Datadog also documents Metric Name Pricing, where usage views show unique metric names, indexed point volume, and ingested-to-indexed point ratios. Organizations on that model must use its matching usage monitors rather than the older cardinality counters. [Datadog Metric Name Pricing guide](https://docs.datadoghq.com/metrics/guide/metric_name_pricing_experience/)
	- **Analytical inference.** Pricing changes can improve predictability while changing what customers must optimize. Legacy cardinality complaints cannot automatically be extrapolated to every current contract.

- ## APM and Infrastructure — Product Attachment Changes the Host Budget
	- For APM purchased using the Infrastructure Monitoring pricing model, each APM host must also have Pro or Enterprise infrastructure coverage. The user's 20-host example therefore means budgeting for 20 APM subscriptions plus 20 infrastructure subscriptions under that model. The same physical machines participate in two product meters. [Datadog APM pricing FAQ](https://www.datadoghq.com/pricing/?LanguageId=1)
	- Datadog also offers standalone APM without mandatory Infrastructure Monitoring. A buyer must compare the actual package and included capabilities. Counting every host twice as a universal rule would overstate the requirement. [Datadog APM pricing FAQ](https://www.datadoghq.com/pricing/?LanguageId=1)
	- **Analytical inference.** Cross-sell can increase wallet share without expanding the customer's server fleet. Budget planning based on an advertised starting rate can understate the cost of the chosen combination of products.

- ## Cloud Networking — Part of Customer Cost, Outside Datadog Revenue
	- Telemetry transport can incur provider-side transfer, NAT, or endpoint charges. AWS documents separate networking-service charges, including PrivateLink endpoint hours and data processing. These costs depend on architecture and are not captured by Datadog subscription units. [AWS networking billing](https://docs.aws.amazon.com/vpc/latest/userguide/vpc-share-billing.html), [AWS PrivateLink pricing](https://aws.amazon.com/privatelink/pricing/)
	- **Analytical inference.** Higher external networking costs worsen the buyer's total economics without directly increasing Datadog revenue. Customer-side filtering can reduce both network traffic and downstream ingestion; filtering after receipt cannot undo already incurred transport.

- ## How These Mechanics Feed the Stock Thesis
	- **Expansion mechanism.** More instrumentation, products, logs, or metric dimensions can lift spending faster than host count. This makes telemetry behavior and platform attachment important drivers alongside compute growth.
	- **Optimization mechanism.** Bill discovery can lead to tighter sampling, lower retention, tag pruning, package changes, and commercial negotiations. Those actions can slow revenue growth even when production workloads expand.
	- **AI-agent connection.** Agents can drive more application activity and automated investigation, while also helping customers identify waste. The net effect depends on how much additional usage converts into paid value after optimization.
	- These are analytical implications of the billing structure, not estimates of overcharging, churn, or future revenue. Related evidence appears in [[2026-11-09-datadog-reddit-practitioner-product-service-feedback]] and the renewal discussion in [[DDOG-2026-Q3]].
