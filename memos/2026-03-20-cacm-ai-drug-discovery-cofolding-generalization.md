tags:: [[AI]], [[drug-discovery]], [[biotech]], [[healthcare]], [[life-sciences-tools]], [[$GOOGL]], [[DeepMind]], [[$RXRX]], [[open-source]], [[synthetic-data]], [[federated-learning]], [[benchmarks]], [[foundation-models]]
file-created-at:: 2026-03-20

- ## Co-Folding Models: Closing AlphaFold Commoditized It in Five Months, and More Data Did Not Fix Generalization
	- **Source**: Chris Edwards, "AI Multiplies for Drug Discovery," *Communications of the ACM*, posted 20 March 2026. Quotes MIT postdoc Gabriele Corso (Boltz), University of Basel doctoral student Peter Škrinjar (Runs N' Poses benchmark), and Aleksandra Faust, chief AI officer at Genesis Molecular AI. Related: [[2026-09-13-david-bellamy-ai-wet-lab-bottlenecks]], [[2026-10-17-ieee-ai-designed-phage-genomes-evo-biosecurity]].
	- **Thesis**: Two findings cut against the "AI foundation models will compress pharma R&D" trade. First, **DeepMind's attempt to close AlphaFold3 produced a commodity category within five months** rather than a defensible lead. Second, and more durable, **adding 25,000 experimental structures to Boltz-2 produced no significant generalization gain** — the binding constraint is architectural, not data or compute, so the scarce asset is experimental data generation and physics-aware model design rather than training capacity.

- ## The Enclosure That Backfired
	- DeepMind restricted AlphaFold3 in 2024: the public version was **forbidden for drug discovery**, and the *Nature* paper omitted source code — a break from previous releases. Days later, **1,500 scientists signed an open letter** demanding open science and inter-lab collaboration tooling. DeepMind partially relented, releasing some source under a Creative Commons license with use limits.
	- | Event | Timing | Consequence |
	  |----------------------------------|-------------------------|---------------------------------------------------------------|
	  | AlphaFold3 access restricted | 2024 | Removed the leading co-folding tool from commercial drug discovery |
	  | Open letter, 1,500 signatories | Days after launch | Public legitimacy cost; partial CC release followed |
	  | MIT releases **Boltz-1** open source | **Five months later** | Restored open access to co-folding; built because the team "would need to have control over protein-structure prediction" |
	  | Three rival launches in one week | End of October 2025 | Open-source and proprietary variants proliferate |
	  | Measured outcome | — | All show **broadly similar performance** on unfamiliar protein-ligand combinations |
	- The investable read: in AI-for-science tooling, **restricting access converts a technical lead into a commodity category rather than defending it**, because the method is published even when the weights are not. Alphabet won a Nobel for the underlying ideas and still holds no durable tooling moat here. Value accrues instead to whoever controls scarce inputs — proprietary data, experimental throughput, and clinical assets — not the model layer.
	- Corso's observation on why the category matters commercially: MIT's earlier DiffDock "was adopted in a lot of pharmaceutical companies, biotech companies, and that gave us an idea both about the importance of this task, and also about the way in which some of these models were used."

- ## The Generalization Wall Is the Real Finding
	- The **Runs N' Poses** benchmark (Škrinjar and colleagues, University of Basel) tested whether co-folding models generalize atom-level interactions or memorize shapes. Existing models showed a **steep accuracy decline on structures outside the training set** — "like the pre-AlphaFold situation for single proteins."
	- Critically, accuracy collapses **even when the target protein is well-represented in databases but the ligand molecule is not**. Small-molecule diversity is far higher than protein diversity in biology, so the ligand side is where coverage will always be thinnest.
	- | Experiment | Data added | Generalization result |
	  |-----------------------------|-------------------------------------|------------------------------------------------------|
	  | **Boltz-2** (MIT + Recursion, summer 2025) | **+25,000 PDB structures** vs predecessor | **No significant improvement** in generalization |
	  | **Pearl** (Genesis Molecular AI) | Synthetic data from physics simulations | Held-out success rate rose with more synthetic data, but **steep drop-off below 40% similarity** to training data |
	  | Boltz-1 variant with physics module | Post-prediction physics modeling | Prediction quality improved; **generalization to unseen targets did not** |
	- Škrinjar's diagnosis: "More experimental data and better balance across target classes might help with the performance. But I believe the main limitation remains architectural. Co-folding methods do not yet capture the deeper geometric and physical principles of protein-ligand binding."
	- The physics gap is specific: binding strength depends on **electron-density effects**, not shape alone — an oxygen atom pulls electrons from neighbors, creating local charge that must line up with compatible sinks and donors on the protein surface. Shape-matching models do not represent this. Bolted-on physics modules need a good initial pose and "cannot correct large mistakes made by the diffusion engine."
	- Read-through: the Boltz-2 result is the single most important datapoint for anyone underwriting AI drug discovery on a data-scaling thesis. **A 25,000-structure increment bought no generalization**, which breaks the analogy to LLM scaling and pushes the payoff horizon out to an architectural breakthrough that has not arrived.

- ## Three Races to Get Past the Data Wall
	- | Strategy | Who | Scale and status |
	  |-------------------------|----------------------------------------|------------------------------------------------------------------|
	  | **New experimental data** | OpenBind — OMSF with Diamond Light Source (UK), funded by the British government's AI for Science program launched late 2025 | **>500,000 protein-ligand structures over five years**, a dataset the group expects to be **20× larger than everything collected in the past 50 years** |
	  | **Federated access to private data** | **Apheris**, working with pharmaceutical companies | Training runs on the companies' own machines so **no proprietary data is exposed** |
	  | **Synthetic data** | **Genesis Molecular AI** (Pearl model) | Faust: "We are the first to provide clear evidence of **synthetic-data scaling laws for co-folding**" |
	- The OpenBind figure is the one to monitor: a 20× step-up in the experimental corpus is the only approach that attacks the ligand-coverage problem directly, and **automation of X-ray crystallography — some of it machine-learning assisted — is what makes it feasible** after decades of painstaking manual effort. That makes structural-biology instrumentation and automation a derivative beneficiary of AI drug discovery regardless of which model wins.
	- The federated pattern matters beyond pharma: Apheris is a template for monetizing regulated proprietary data without moving it, applicable anywhere data gravity and compliance block model training.
	- Faust's caveat on synthetic data is the generalizable lesson: results are "consistent with prior work in robotics and large language models, which suggests synthetic data must be **diverse and maintain a sufficient distributional distance** to the original training data." Synthetic data extends a distribution; it does not escape one.

- ## Where the Architecture Is Heading
	- AlphaFold3's two advances were **denoising/diffusion** (the same technique behind image and video generators, refining the Evoformer's coarse structure) and **co-folding** — predicting protein conformational change and ligand placement together, which proved more accurate than AI docking tools including MIT's DiffDock.
	- Groups working outside the AlphaFold paradigm use **graph neural networks** to incorporate physics more directly. These simulate conformational change better but regress to pre-AlphaFold weakness on large-scale protein structure — the inverse failure mode.
	- The expected convergence is **hybrid**: diffusion models to build initial structures, then physics-oriented models to resolve protein-ligand detail. The article flags integration as challenging and unresolved, which is the honest status of the field — no current architecture does both halves well.
