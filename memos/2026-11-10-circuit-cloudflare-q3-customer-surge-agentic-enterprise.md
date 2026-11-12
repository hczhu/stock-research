tags:: [[Cloudflare]], [[$NET]], [[agents]], [[enterprise-AI]], [[edge-computing]], [[networking]], [[cybersecurity]], [[Zero-Trust]], [[The Circuit]], [[Jay-Goldberg]], [[Ben-Bajarin]], [[podcast]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-10
file-updated-at:: 2026-11-10

- ## The Circuit on Cloudflare Q3 2026: a jump in customer additions as a sign of enterprise agent adoption
	- **Source**: *The Circuit* podcast, Jay Goldberg and Ben Bajarin, recorded Nov 6, 2026, the week Cloudflare reported Q3 2026. User-provided auto-generated transcript.
		- Goldberg makes the Cloudflare case. Bajarin adds the security and governance view.
		- The figures are Goldberg's recollection on air, not checked against Cloudflare's release.
		- Related: [[NET-2026-Q1]], [[2026-06-25-mad-podcast-matthew-prince-cloudflare-agentic-internet]], [[2026-06-29-hhh-hypergrowth-cloudflare-agentic-leverage]], [[2026-07-01-hhh-hypergrowth-cloudflare-agentic-waves]], [[2026-11-10-circuit-anthropic-s1-q3-slowdown-compute-constraint]], [[2026-11-10-circuit-nov-6-semi-selloff-2028-capacity-amd-arm-qcom-sitime]].
	- **Thesis (Goldberg)**: Cloudflare is a networking and security layer for distributed computing, which "turns out [is] very important for running agent workloads."
		- Its Q3 paying-customer additions went "parabolic," to about **158,000 in one quarter versus 20–30,000 a quarter before**.
		- Most Cloudflare users "are doing it for work." Goldberg reads the jump as the clearest sign yet that **enterprises are ramping hard on agentic AI**.
		- He uses it against the Nov 5 selloff: "there's real momentum in the enterprise side for adopting AI."
- ## What Goldberg said about the quarter
	- | Item | As cited | Note |
	  |---|---|---|
	  | Paying customers added in Q3 2026 | **About 158,000** | "Parabolic, straight up exponential curve" |
	  | Prior run rate | **About 20–30,000 a quarter** (about 30,000 average last year) | Suggests about 5–8× the usual pace |
	  | Stock reaction | "The stock is up a lot" | In the week the rest of tech sold off |
	  | Management tone | "Very, very bullish … very excited on their call" | |
	- **Why it matters to him**: he has long asked "when is this going to be in the enterprise?" and says this is the first time "it really feels like there's something happening." It also lines up with Bajarin's enterprise survey data from the prior week.
- ## How Goldberg describes Cloudflare
	- "I don't think people really understand what Cloudflare does. It's a little bit nebulous."
	- His version: a connecting layer that brings an enterprise's scattered container and Kubernetes workloads "under sort of one networked umbrella." Servers in offices around the world can then interconnect efficiently, like the networking AWS provides but beyond a CDN, with a lot of security built in.
	- *My note*: that is loose. Cloudflare is a global edge network that sells CDN and performance, application security (WAF, DDoS, bot management), Zero Trust/SASE networking for enterprises, and a developer platform (Workers, storage, AI inference). The agent case runs mainly through Workers, which hosts agents, and through Zero Trust and security, which govern agent traffic. See [[2026-06-25-mad-podcast-matthew-prince-cloudflare-agentic-internet]].
- ## The enterprise context (Bajarin)
	- **Cloudflare solves only part of the problem**: enterprises need "AI ops" much as they built FinOps. That means permissions, observability, data and governance for agents, and "a lot of these solutions don't exist" yet to scale governed agent production.
	- **Security comes first**: his CIO/CTO and CSO surveys find security is the first gate to scaling agents. That is the part Cloudflare addresses.
	- **The data problem**: about 80% of enterprise data created at the edge is unstructured. Leading companies use agents to structure and index it, which gives them views of the business they never had.
	- **Adoption is split**: the top ~20% of early adopters are rebuilding their processes now and the other 80% will lag. Goldberg thinks adoption is further along than Bajarin does.
- ## My notes
	- **Ask what's driving the 158K**: a 5–8× jump in paying customers in one quarter usually has a specific cause, such as a new low-price or self-serve plan, agent-related products (Workers, AI crawl controls, pay-per-crawl), a pricing change or a change in how customers are counted. Most of the new customers are probably small or self-serve accounts. That fits "agents are driving developer signups" but is weaker evidence of *large enterprise* adoption than Goldberg suggests.
	- **Check these in the Q3 release**: the number of large customers (\$100K+ and \$1M+), dollar-based net retention, Workers and developer-platform growth, and whether management explained the jump.
	- **Compare with Q1**: in [[NET-2026-Q1]] Cloudflare added as many \$5M+ customers as in all of the prior year, and more than three-quarters of Workers growth came from new customers. A Q3 surge in paying customers continues that pattern of developer and agent signups.
	- **Contrast with the semis**: Cloudflare rising while the semis fell fits Goldberg's view that the selloff was sentiment, not a demand signal.
