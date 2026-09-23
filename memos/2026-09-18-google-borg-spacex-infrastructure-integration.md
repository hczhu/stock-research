- tags:: [[$GOOGL]], [[SpaceX]], [[Borg]], [[AI]], [[data-center]], [[compute]], [[capex]]
  file-created-at:: 2026-09-18

- ## Google Borg: Rented Compute Is Only Valuable Once It Runs
	- **Source**: User-provided excerpt, “Overtime at Google to get Borg working on SpaceX’s data centers,” citing conversations with current Google engineers. The operational claims are reported anecdotes, not company disclosures.
	- **Thesis**: Compute scarcity is pushing Google onto external infrastructure, exposing the portability cost of a system optimized for its own data centers. Securing hardware does not immediately translate into usable capacity or revenue.

- ## Reported Bottleneck
	- Google has reportedly committed **$920M per month** to rent SpaceX compute. Borg, Google's infrastructure-management system, assumes networking and physical layouts that hold inside Google but do not hold at SpaceX, obstructing deployment.
	- The excerpt says the Borg team is working **996—9 a.m. to 9 p.m., six days a week**—to resolve compatibility. Fewer remaining long-tenured engineers deeply familiar with Borg reportedly make the work harder.
	- **Roughly $30M per day** is the monthly fee divided by about 30 days. It represents potential rental-cost exposure if the entire paid allocation is unusable, rather than a verified daily loss; actual exposure depends on billing commencement and the fraction of capacity affected.
	- **Timing remains unresolved**: [[2026-06-05-gpu-cluster-rental-unit-economics-spacex-google-anthropic]] records an October 2026 contract start, whereas this excerpt describes current payments. The excerpt does not establish that the full charge is already accruing.

- ## Business Significance
	- **Alphabet**: Integration delays can separate infrastructure expense from productive workload growth. Borg's tight fit with Google's own facilities becomes a deployment constraint when compute must come from another operator.
	- **SpaceX**: Fixed rental commitments could protect near-term receipts despite a customer's software problems, subject to the actual contract terms. The excerpt's claim that Google must pay regardless should not be read as proof that no termination or delivery protections exist.
	- **Broader lesson**: As hyperscalers rent external capacity, software portability and retained infrastructure expertise become economically important. The source's expectation that non-Google infrastructure becomes a new baseline is a strategic forecast, not a disclosed Google roadmap.
