tags:: [[Modal]], [[GPU]], [[GPU-pricing]], [[neoclouds]], [[$NVDA]], [[$CRWV]], [[inference]], [[sandboxes]], [[compute]], [[capex]], [[open-weights]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-19
file-updated-at:: 2026-11-19

- ## Modal's Erik Bernhardsson on GPU prices, capacity deals and sandboxes
	- **Source**: podcast interview with Erik Bernhardsson, co-founder and CEO of Modal, November 2026 (user-provided auto-generated transcript; the show is not named, and the transcript renders his name as "Eric Fern-Hartson"). Modal is a serverless AI compute platform whose customers include Decagon, Suno, Runway and Cognition. It **rents all its GPUs** and owns none.
	- **Thesis**: GPU prices are rising in a market where hardware prices normally fall. Getting capacity now means **three-year, prepaid deals** with dozens of clouds. Bernhardsson sees the scarcity as real but not cornered, and worries more about a **price collapse hitting anyone locked into supply** than about prices going up. Most of the scarcity rent currently goes to Nvidia and to capacity owners.

- ## How GPU procurement has changed
	- | | Until end of 2025 | Now (late 2026) |
	  |---|---|---|
	  | Sources | Mostly hyperscalers (AWS, then GCP and Azure), plus Oracle early on for cheap A10s and A100s | **Almost 25 clouds**, including many neoclouds |
	  | Contract type | Mostly spot (preemptible) and one-year reservations | Often **3+ year deals with a meaningful upfront payment**, locking in prices for the term |
	  | Team needed | Little | A **four-person procurement desk** working full time on deals with neoclouds, plus a **10-engineer team** managing bare-metal capacity (network issues, bad drives, GPUs dropping offline) |
	- **Vetting vendors**: Modal sends a spec sheet (IOPS, CPU benchmark scores, network bandwidth), tests one node first, and keeps an internal "Modal Max" vendor score modeled on SemiAnalysis's ClusterMAX. Some commitments run to **tens or hundreds of millions of dollars** with vendors Modal does not yet know well.
	- **Where spare capacity is**: frontier labs prefer tier-one clouds and the large contiguous blocks they need for training. Smaller blocks are available worldwide, for example **32 nodes in Armenia** or **128 nodes in Indonesia**, at good prices.
	- **Nvidia spreads its allocation**: Bernhardsson thinks Nvidia prefers many buyers over a few large ones. Even hyperscalers get constrained allocations, while neoclouds and alternative clouds get more.

- ## GPU price trend and risks
	- **Prices are rising, against the normal direction for hardware**: this phase "could be another six months, could be another 36 months."
	- **The market is tight but not cornered**: Nvidia is shipping "several hundred thousand" Blackwells a month, and anyone willing to outbid others can get capacity. He compares buying everything available to "the great toilet paper shortage" and a run on the bank.
	- **Modal is effectively long GPU prices**: its locked-in reservations rise in value with scarcity, and scarcity also lets it charge customers more.
	- **The real risk is a collapse**: "I do worry more about actually prices collapsing." He doesn't expect it soon, but it would hurt anyone who locked in a lot of supply and "paid too much." In a downturn, falling prices, falling utilization and a vanishing resale market would arrive together. He cites the Hunt Brothers' failed attempt to corner silver.
	- **Who captures the scarcity rent**: mostly **Nvidia**, and to some extent **neoclouds** and anyone owning capacity. In the long run, he is unsure the premium from owning GPUs is worth the balance-sheet risk.
	- **Macro backdrop**: AI investment is "starting to become like several percentage points" of US GDP, and US interest rates have been "shooting up in the last few weeks."

- ## The "rectangle" problem and duration transformation
	- **How capacity is sold**: "almost all capacity is sold as a three year rectangle starting three to six months in the future." Real demand is bursty, scales up and down through the day, and grows over time.
	- **Modal's role**: Modal buys the rectangles and rents capacity out on demand. A customer can get 100 GPUs immediately without talking to sales. Pooling thousands of customers makes aggregate demand smooth. Bernhardsson calls this a "massive differentiator."
	- **Why separate inference providers exist**: demand swings between open models whenever a lab releases a better one. A provider can shift, say, 50% of a model's GPUs to another model overnight, whereas each lab holding its own capacity would see utilization swing with every release.

- ## How neoclouds grow, and GPUs as an asset class
	- **The neocloud playbook**:
		- 1. Pre-sell a multi-year contract to a lab such as Anthropic or OpenAI.
		  2. Take the contract to Wall Street to raise money, often using GPUs as loan collateral.
		  3. Buy the hardware from Supermicro or Dell and install it.
		- This lets neoclouds scale extremely fast. Nscale went from little capacity to "hundreds of billions" in its pipeline. Bernhardsson calls neoclouds, especially CoreWeave, "very, very sophisticated financial engineering companies." Modal's product-led, self-serve model makes this kind of financing harder for it.
	- **Rent or own**: renting is capital-efficient. Buying brings operational complexity and a funding problem: equity is dilutive, and debt needs locked-in long-term revenue. "Everything is on the table," including joint ventures and special-purpose vehicles. Capacity prepayments are "the best use of cash" today, and salaries are "basically a rounding error."
	- **GPU indices and derivatives**: startups such as Silicon Data, Compute Exchange and Ornn are building price indices and derivatives. Compute is less uniform than oil, varying by network, location, disks, CPUs and reliability. He doubts GPUs become a Brent-crude-style traded commodity, but welcomes more hedging and insurance.

- ## Alternative accelerators and open models
	- **Non-Nvidia chips**: "2027 might be the year of non-Nvidia accelerators." He has said this every year for 5–10 years and been wrong. TPUs work well inside Google, and the remaining gap is mostly software. TSMC and ASML may be deeper bottlenecks than Nvidia.
	- **Mixed hardware setups**: disaggregated inference that runs prefill on Nvidia and decode on Cerebras or Groq, matching compute-bound and memory-bound work to different chips.
	- **Open models**: Kimi K3, DeepSeek 4.1 and GLM 5.3 are "basically almost as good as the frontier model at a much lower cost." Fine-tuning has become optional, though demand for post-training (supervised fine-tuning and reinforcement learning) remains.

- ## Modal's own data points
	- | Metric | Figure |
	  |---|---|
	  | Growth since about two years ago | "At least **50×**" in revenue and users |
	  | Early revenue | \$100 a month in November 2022, then \$2K in December and \$30K in January 2023 on Stable Diffusion demand. One customer, Mage, was 80–90% of Q1 2023 revenue, and Suno was large from late 2023. Revenue is now well diversified |
	  | Revenue mix | **Functions about two-thirds** (mostly inference), **sandboxes about one-third** |
	  | Sandbox growth | Sandbox revenue "keeps going up **30% every month**." Drivers include vibe-coding apps (Lovable), background agents (Ramp) and neolabs running reinforcement learning. Anthropic's Managed Agents integrates Modal as a bring-your-own sandbox. The median sandbox lasts about **8 seconds** |
	  | Uptime | Recently "four or five nines" |
	  | People | About 200 employees (150 engineers), heading to about 250 by year-end and possibly about 700 next year. Headcount grew about 4× in the last 12 months. Forward-deployed engineers went from 4 to about 24 this year |
	- **Product direction**: training for small and mid-sized models (computational biology, speech, recommendation systems), batch jobs, low-latency voice, and post-training. Sandboxes are moving toward very short-lived environments: one sandbox per command, with snapshotting, forking and massively parallel CI.
	- **Cloud over on-prem**: Bernhardsson calls himself a "cloud maximalist." He sees on-prem and bring-your-own-cloud deployments as legacy, but bring-your-own-cloud could pool neolabs' reserved capacity under Modal's control plane.

- ## Related in the repo
	- **Rental prices confirm the trend**: Nvidia says multi-year Hopper renewals reached up to 2× the original price and B300 rentals rose 60%+ ([[NVDA-2026-Q3]]). SpaceX reports compute renewing at higher \$/W ([[SPCX-2026-Q3]]).
	- **Neocloud financing**: [[2026-06-11-nvidia-coreweave-nebius-circular-financing]] and [[2026-09-11-nvidia-backstop-universe-credit-support]].
	- **Upfront payments spreading**: the same upfront-payment demands now apply to bulk CPU orders ([[2026-11-16-daytona-burazin-cpu-shortage-upfront-payments]]).
	- **Modal's inference products**: Modal offers speculative decoding as a per-request service ([[2026-11-18-speculative-decoding-idle-compute-dedicated-inference]]).
