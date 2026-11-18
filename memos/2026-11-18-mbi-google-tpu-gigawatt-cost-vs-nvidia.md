tags:: [[$GOOGL]], [[$NVDA]], [[TPU]], [[Anthropic]], [[data-center]], [[capex]], [[depreciation]], [[unit-economics]], [[custom-silicon]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## What a gigawatt of AI compute costs Google with TPUs, vs. an Nvidia build
	- **Source**: MBI Deep Dives (Mostly Borrowed Ideas), November 2026, user-provided excerpt. Google's figures are **MBI's estimates**, not Google disclosures. Anthropic's \$11.6B comes from MBI's own Anthropic model. The Nvidia comparison uses figures already in the repo, with derived numbers marked as memo calculations.
	- **Thesis**: By MBI's estimate, Google builds a gigawatt for itself for about **\$33B of capex** and runs it for about **\$5.2B a year**. That is **less than half of Anthropic's ~\$11.6B blended compute cost per GW**, because Google designs its own chips and builds its own data centers. Against an Nvidia-based build of about \$50–60B per GW, Google's capex is roughly 55–66% as much, and the gap is almost entirely in the chips.

- ## MBI's estimate for a Google self-built gigawatt
	- | Item | Capex per GW | Depreciation life | Annual cost per GW |
	  |---|---|---|---|
	  | TPUs and networking | **\$21B** | 6 years | \$3.5B (memo calculation) |
	  | Data center | **\$12B** | 25 years | \$0.5B (memo calculation) |
	  | Power and operations | — | — | About \$1.2B (memo calculation, as MBI's total minus depreciation) |
	  | **Total** | **About \$33B** | | **About \$5.2B** (MBI) |
	- **Comparison with a frontier lab**: Anthropic's blended compute cost is about **\$11.6B per GW this year** in MBI's model, more than 2× Google's. Anthropic rents most of its compute, so its cost includes the margins of the clouds and chip vendors it buys from.
	- **Chips dominate the annual bill**: on MBI's numbers, chip depreciation is about two-thirds of Google's annual cost per GW (memo calculation), so chip cost and chip lifespan matter far more than the building.

- ## Contrast: Nvidia-based AI data center cost per GW
	- | Source | Total per GW | Chips, systems and networking | Facility (land, power, shell) |
	  |---|---|---|---|
	  | **Google TPU self-build** (MBI estimate) | **About \$33B** | **About \$21B** (TPUs and networking) | About \$12B |
	  | Jensen Huang, GTC 2026 ([[2026-05-02-1gw-data-center-cost-breakdown]]) | \$50–60B | \$33–45B (remainder after infrastructure) | \$15–17B |
	  | Stephen Balaban, Lambda ([[2026-06-18-mad-podcast-stephen-balaban-lambda-ai-compute-neoclouds]]) | \$47–63B | \$35–45B (compute servers) | \$10–15B shell plus \$2–3B generation |
	  | Nvidia CFO, Vera Rubin ([[2026-09-01-stratechery-nvidia-earnings-dollars-per-gigawatt-hugging-face]]) | About \$60B, implied by "two-thirds" | **About \$40B of Nvidia revenue** | About \$20B for everything else, implied |
	- **Where the gap is** (memo calculation):
		- Google's chips and networking cost about **\$21B per GW versus about \$40B of Nvidia content** per Vera Rubin gigawatt, roughly half. This is the margin Google avoids by designing its own chips.
		- Facility costs are similar: Google's \$12B is close to the \$10–17B range for an Nvidia build, so building its own data centers adds a smaller saving.
		- In total, Google's capex is about **55–66%** of an Nvidia-based gigawatt (\$33B vs. \$50–60B).
	- **Annual cost under MBI's method** (memo calculation): applying MBI's lives (6 years for technical systems, 25 years for the facility) and Google's implied \$1.2B of power and operations to an Nvidia-based build:
		- \$50B case (\$35B systems, \$15B facility): about \$7.7B a year.
		- \$60B case (\$43B systems, \$17B facility): about \$9.1B a year.
		- Google's \$5.2B is therefore about **57–68%** of an Nvidia-based self-build. Anthropic's \$11.6B sits above both because renting adds the cloud provider's margin on top of Nvidia's.

- ## Related in the repo
	- **Google sells this cost advantage**: Google is renting TPUs to outside customers and securing TPU orders from OpenAI and Anthropic through 2029 ([[2026-09-07-semianalysis-tpuv7-inference-externalization]], [[2026-11-15-google-tpu-openai-anthropic-orders-2029-mediatek-quillfish]]). This is the "AI compute provider" narrative in [[Google-GOOGL-thesis]].
	- **A cross-check**: on Google's Q3 call, analyst Ross Sandler used an illustrative **~\$35B per GW** full-system cost for TPU systems Google sells to outside customers ([[2026-10-29-google-tpu-repurchase-guarantees]]). That assumption is close to MBI's \$33B internal build cost. Neither is a Google disclosure.
