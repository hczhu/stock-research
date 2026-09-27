- tags:: [[$NVDA]], [[$PLD]], [[inference]], [[data-center]], [[power]], [[GPU]], [[AI infrastructure]], [[capex]]
  file-created-at:: 2026-05-12

- ## Distributed Inference: Send Queries to Available Power
	- **Source**: Emily Waltz and Dina Genkina, “Your Next AI Query May Travel Where the Power Is,” IEEE Spectrum, May 12, 2026; corrected May 13. Extracted from the supplied article. Project schedules and estimates reflect the article's publication date, not a verified September progress update.
	- **Thesis**: Routing inference across small facilities near substations could turn fragmented grid headroom into usable AI capacity. Nvidia's proposed pilot offers a complementary path to large campuses: use existing power more flexibly to accelerate deployment, with potential opportunities for modular facilities, suitable real estate, and workload-routing software.

- ## Pilot and Power Data
	- | Item | Reported figure or plan | Business significance |
	  |---|---|---|
	  | Pilot fleet | **About 25 sites, each 5–20 MW, across five U.S. utilities** | Tests whether small power allocations can support a coordinated inference fleet. Construction was targeted to begin by end-2026. |
	  | Partners | **Nvidia, InfraPartners, Prologis, and EPRI** | Combines compute technology, data-center construction, real estate, and utility research; commercial economics are not disclosed. |
	  | Substation headroom | EPRI reports **roughly 5 MW nominally available on average, up to 20 MW** in its investigation | Too small for many large-campus developers, but potentially useful when aggregated. The article does not define the sample. |
	  | Expected workload relocation | **About 0.1% of the time**, Nvidia/EPRI estimate | Flexibility could unlock access without constant relocation; this is a pilot expectation, not an operating result. |
	  | U.S. generation utilization | **About 53% on average**, per the cited 2025 Duke Nicholas Institute report | Peak provisioning leaves temporal headroom, but average national utilization does not establish deliverable capacity at any specific site. |
	  | Flexibility potential | **76 GW of additional load** if large loads curtail **0.25% of the time**, per Duke | A modeled grid opportunity, distinct from the pilot's expected relocation frequency and not 76 GW of committed projects. |
	  | Data-center electricity demand | **9–17% of U.S. generation by 2030**, EPRI estimate | A wide forecast range that motivates alternatives to continuously supplied, inflexible loads. |

- ## Why Inference Fits the Model
	- **Route work instead of pausing service**: If a substation is overloaded or unavailable, queries can go to a site with spare power. This seeks to preserve response times while reducing local demand.
	- **Training has different constraints**: Tightly coupled training needs rapid communication among many GPUs, making a geographically dispersed fleet a poor substitute for a large training cluster. Some training jobs can instead offer flexibility by pausing briefly.
	- **Use infrastructure already near power**: Substation proximity may reduce new transmission and distribution work. Nvidia also points to existing fiber at substations, although the article does not establish that every candidate site's connectivity is sufficient for commercial inference.
	- **Forecast of a second buildout wave**: EPRI's Ben Sooter expects smaller inference facilities to become more important as inference demand rises in 2027. This is a participant's outlook rather than disclosed customer orders.

- ## Company and Industry Economics — Interpretation
	- **Nvidia**: Unlocking smaller power sites could expand the addressable deployment base for inference hardware and increase the value of orchestration across facilities. The article provides no GPU orders, revenue commitments, or pilot margins.
	- **Prologis**: Participation suggests an opportunity to pair real estate with nearby usable power. Site-specific grid access and fiber could become more valuable selection criteria; no portfolio conversion plan or financial contribution is quantified.
	- **Modular builders and utilities**: Smaller facilities could be deployed where large campuses cannot fit, while flexible demand could use infrastructure that would otherwise be underutilized. Faster connection and lower total costs remain outcomes to demonstrate.
	- **Capacity can be unlocked through flexibility as well as construction**: Better routing could defer some dedicated generation or grid expansion. It does not remove local transmission limits, power-quality requirements, or the need for reliable service agreements.
	- **The unresolved tradeoff is fleet economics**: Geographic redundancy, model and cache replication, connectivity, and smaller-site operating overhead may offset savings from faster power access. The article supplies no comparison of cost per served token, utilization, or end-to-end latency against a centralized facility.
