tags:: [[$SPCX]], [[SpaceX]], [[Anthropic]], [[$GOOGL]], [[$NVDA]], [[GPU-pricing]], [[GPU-rental]], [[H200]], [[Blackwell]], [[GB300]], [[Vera-Rubin]], [[neoclouds]], [[BIS]], [[export-controls]], [[China]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-25
file-updated-at:: 2026-11-25

- ## SpaceX cuts Blackwell spot pricing; early signs of a GPU-rental cooldown
	- **Source**: an industry research note (user-provided screenshot, late November 2026). It refers to "our AI Cloud and TCO Model," which is SemiAnalysis's product name. The non-renewal is described as "industry chatter," and the ~\$5/hr H200 pitch is the author's belief.
	- **Thesis**: GPU rental prices are showing **early signs of a broad cooldown**.
		- **Blackwell spot**: SpaceX has cut spot pricing to **\$10–12 per GPU-hour**, down from about **\$15–15.5**, only weeks after rentals were "still climbing across the curve."
		- **An H200 roll-off**: Anthropic is reportedly **not renewing a ~50K-H200 cluster** at SpaceX, which SpaceX is re-marketing at about **\$5/GPU-hr** for early 2027.
		- **More short-term supply**: H200 roll-offs, SpaceX's own fleet growth (mostly Vera Rubin next year), SpaceX's preference for spot over long-term deals, and **new BIS rules** that displace compute rented to Chinese customers.
		- **Not a capex signal yet**: the author's model already assumed about \$12/GPU-hr for GB300, and Blackwell paybacks stay attractive at \$10–12. The author does **not** expect SpaceX's 2027 buildout to slow.

- ## The data points
	- | Item | Before | Now | Memo calculation |
	  |---|---|---|---|
	  | SpaceX Blackwell spot price, smaller clusters | About \$15–15.5 / GPU-hr (its previous time in the market) | **\$10–12 / GPU-hr** | Down about **20–35%** |
	  | Larger clusters offered to Anthropic and Google | — | \$10–12 / GPU-hr | Smaller clusters now priced the same as large ones |
	  | Anthropic's ~50K-H200 cluster at SpaceX | Reportedly not being renewed | Re-marketed at about **\$5 / GPU-hr** for early 2027 availability | Against about \$11.4/hr for H200-class GPUs in the June Google deal, down about **56%** |
	  | The author's GB300 assumption | About **\$50M per IT MW per year**, roughly **\$12 / GPU-hr** | Unchanged | Implies about 475 GPUs per IT MW, about 2.1 kW per GPU all-in |
	  | Vera Rubin pricing | — | "Remains well above" Blackwell's | Not quantified |
	- **What is adding short-term supply**:
		- **H200 roll-offs**, such as Anthropic's.
		- **SpaceX's own fleet growth**, mostly Vera Rubin in 2027.
		- **SpaceX rents at spot** rather than signing long-term deals.
		- **New BIS rules**: compute that had been rented to **Chinese customers** now needs a new home.
		- The author calls this "a headwind for spot rates into 2027."

- ## How this compares with earlier repo data
	- **SpaceX's own Q3 message pointed the other way**: on its Q3 2026 call, SpaceX said short-term contracts were **renewing at higher \$/W**, pricing was tracking slightly above **\$50 per watt**, and it rents at spot-like rates on purpose to capture rising value ([[SPCX-2026-Q3]]). A spot cut a few weeks later is the first data point that this strategy also carries the downside.
		- *Memo calculation*: \$50M per MW per year is \$50 per watt per year, so \$10–12/hr sits at or just below that.
	- **The June contracts**: the Google deal implied about **\$11.4 per H200-class GPU-hour**. The Anthropic deal (about \$1.25B a month through May 2029, with **90-day termination notice**) was priced on a mixed H100/H200/GB200 fleet ([[2026-06-05-gpu-cluster-rental-unit-economics-spacex-google-anthropic]]). The note doesn't say whether the 50K-H200 cluster is part of that contract or a separate one.
	- **Nvidia's Q3 view**: Nvidia said multi-year Hopper renewals reached up to 2× the original price and B300 rentals rose 60%+ ([[NVDA-2026-Q3]]). A \$5/hr H200 re-pitch would be the first sign of Hopper pricing turning down.
	- **Modal's view**: Erik Bernhardsson's account of GPU prices and capacity ([[2026-11-19-modal-bernhardsson-gpu-prices-capacity-sandboxes]]) adds context on how fast spot markets can swing.

- ## Memo's reading
	- **Spot vs. contracts**: this is a **spot and short-term** signal. Labs on long-term contracts, and Nvidia's backlog, aren't directly affected. Spot prices usually move first, though, and SpaceX chose spot exposure deliberately.
	- **Hopper cools first**: older H200 capacity rolling off at about \$5/hr, while Blackwell holds at \$10–12, fits a market where demand concentrates on the newest chips. That pressures neoclouds holding Hopper fleets financed on assumptions of higher renewal rates.
	- **Anthropic's move**: dropping an H200 cluster is consistent with its fleet shifting to TPUs, Trainium and newer Nvidia generations. It isn't evidence of weaker demand on its own.
	- **Export controls**: the BIS rules turn Chinese demand served through rented capacity into supply on the open market, a one-time addition to rentable capacity.
