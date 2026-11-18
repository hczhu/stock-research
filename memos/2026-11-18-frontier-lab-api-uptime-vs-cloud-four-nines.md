tags:: [[Anthropic]], [[OpenAI]], [[$AMZN]], [[AWS]], [[reliability]], [[SRE]], [[inference]], [[enterprise-AI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Frontier labs' API uptime falls well short of cloud-provider standards
	- **Source**: user-provided newsletter excerpt, November 2026, citing each company's self-declared uptime. The newsletter's name was not given.
	- **Thesis**: Frontier labs promise much less uptime than enterprises expect from cloud infrastructure. Anthropic's self-declared **99.5%** allows about **50× the downtime** of the 99.99% ("four nines") standard that AWS is known for upholding.

- ## Self-declared uptime vs. the cloud standard
	- | Service | Self-declared uptime | Allowed downtime per month | Allowed downtime per year | Multiple of four-nines downtime |
	  |---|---|---|---|---|
	  | Anthropic API | **99.5%** | About 3.7 hours | About 44 hours | **About 50×** |
	  | OpenAI API | **99.97%** | About 13 minutes | About 2.6 hours | About 3× |
	  | ChatGPT | **99.2%** | About 5.8 hours | About 70 hours | **About 80×** |
	  | Cloud-provider standard (e.g. AWS) | **99.99%+** | About 4.4 minutes | About 53 minutes | 1× |
	- Downtime columns are memo calculations from the uptime percentages, using a 730-hour month and an 8,760-hour year.
	- **OpenAI splits by product**: its API is self-declared about 27× more available than ChatGPT, its consumer app (memo calculation, 0.03% vs. 0.8% downtime). Anthropic's API figure is below both of OpenAI's.

- ## Related in the repo
	- **Compute shortage as a cause**: a roughly day-long Anthropic outage in March–April 2026 is attributed in the S-1 to running out of compute, according to Goldberg. Anthropic paid up for spot compute to avoid another outage before its IPO ([[2026-11-10-circuit-anthropic-s1-q3-slowdown-compute-constraint]]).
	- **Hyperscalers sell reliability**: once Anthropic joined Bedrock, AWS reached "basically parity" on models and competed on compliance, reliability, scalability and GPU availability ([[2026-11-04-expert-call-aws-bedrock-sales-motion-anthropic-economics]]). The memo's reading: the uptime gap gives enterprises a reason to buy frontier models through a hyperscaler rather than directly from the lab.
	- **Running the service is the product**: customers pay for software that keeps working (uptime, recovery, accountability), not for the code itself ([[2026-01-24-swizec-future-of-software-engineering-is-sre]]).
