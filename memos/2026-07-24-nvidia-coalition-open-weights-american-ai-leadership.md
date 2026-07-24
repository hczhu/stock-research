- tags:: [[$NVDA]], [[$META]], [[$MSFT]], [[$IBM]], [[open-weights]], [[open-source]], [[AI-policy]], [[inference]], [[AI]]

- ## Open Weights and American AI Leadership — industry coalition letter
	- **Source**: NVIDIA-hosted PDF, "Open Weights and American AI Leadership," July 24, 2026. A ~3-page policy statement co-signed by 24 organizations. [images.nvidia.com](https://images.nvidia.com/pdf/Open-Weights-and-American-AI-Leadership.pdf)
	- **Thesis**: A broad industry coalition led by NVIDIA is lobbying U.S. policymakers to keep open-weight models unrestricted — framing open weights as the path to AI diffusion, competition, and security. The investable signal is in who signed (compute + open-model + application-layer players) and who did not (the closed frontier labs), and in the explicit defense of distillation.

- ## Core argument
	- Analogy to 1980s open-source software: openness, not corporate control, produced the shared foundation now underlying most of the internet, big tech, the U.S. military, and federal agencies. The U.S. faces the same choice with AI.
	- AI leadership will be "judged not by one frontier AI model, but by whether the United States builds a strong, open ecosystem that diffuses into every sector." Open weights = models anyone can download, inspect, modify, and run on their own infrastructure.
	- Four claimed benefits of open weights:
		- **Access / cost discipline**: match the right model to the right job at the right cost — reserve frontier-scale capability for genuine frontier problems, run efficient specialized models everywhere else. This "discipline" is what makes AI economically sustainable as usage scales into "billions of everyday tasks."
		- **Competition**: rivalry not just among model developers but across cloud, chips, applications, and services — driving down cost and spreading gains.
		- **Customer control**: avoid single-provider lock-in; own your data, adaptations, and accumulated value ("self-improving models, specialized capabilities, accumulated knowledge").
		- **Safety / security**: openness may be a *path to* safety, not a threat to it. Closed models are single points of failure that can be breached or fail undetected; open weights let a broad community red-team, benchmark, and remediate. Cyber defenders need models with capabilities comparable to AI-armed attackers.
	- Acknowledges the distinct risk — once released, weights are beyond the developer's control and modified versions are hard to trace or reverse — but argues the answer is not prohibition.

- ## Policy asks (what the coalition wants from Washington)
	- Expand compute access for startups and researchers.
	- Invest in shared training assets: datasets, tools, evaluation frameworks.
	- "Keep the frontier plural" — avoid premature restrictions on open models that stifle competition or push innovation overseas.
	- Strengthen application layers to expand "sovereign" use of AI across the economy.
	- **Distillation defense**: distillation (training on another model's outputs) is a legitimate, widely used technique, not misappropriation. Unlawful extraction from closed models should be handled via targeted legal/commercial frameworks, not "sweeping restrictions" on the technique. (Directly relevant to the DeepSeek-style extraction debate and to any policy that would advantage closed labs.)

- ## Signatories — read the coalition
	- **Signed (24 orgs)**: NVIDIA, Meta, Microsoft, IBM, Andreessen Horowitz, Hugging Face, Mistral, Mozilla, The Linux Foundation, Palantir, Perplexity, ServiceNow, Box, CrowdStrike, Dell Technologies, Replit, Y Combinator, Arcee AI, Arena, Black Forest Labs, Emergence Capital, Reflection, Telnyx, American Innovators Network, Mariana Minerals.
	- **Investment read**: the coalition is the compute/chip layer (NVIDIA, Dell), the open-weight model layer (Meta/Llama, Mistral, Hugging Face distribution), and the application/enterprise layer (Palantir, ServiceNow, Box, CrowdStrike, Replit). Their shared economic interest is maximizing AI *diffusion* — more models, more inference, more deployment surface — which is the volume-driven demand thesis for merchant compute.
	- **Notably absent**: OpenAI, Anthropic, Google, and Amazon — the leading *closed* frontier labs, whose economics favor concentration and API gatekeeping. The split maps cleanly onto the open-vs-closed business-model divide.
