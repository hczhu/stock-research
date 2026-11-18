tags:: [[Huawei]], [[Ascend]], [[China]], [[GPU]], [[H200]], [[$NVDA]], [[inference]], [[tokenomics]], [[DeepSeek]], [[GLM]], [[Kimi]], [[export-controls]], [[semiconductor]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-18
file-updated-at:: 2026-11-18

- ## Huawei Ascend 950DT — inference throughput, cost and token economics vs. H200
	- **Source**: X thread by @MaxForAI (Max For AI), November 2026, in Chinese. It summarizes an unnamed report (PPT) benchmarking three generations of Ascend chips, and adds the author's own corrections and a Kimi K3 sensitivity analysis. The report's figures are not independently verified.
	- **Thesis**: According to the report, Huawei's Ascend 950DT reaches **86% of H200 inference throughput** and about **30% better inference cost-performance** on rental pricing. Its FP16 compute is only **43% of H200's**, so the gap in training remains large. Whether serving tokens on it pays off depends mostly on the model's API price.
	- Architecture background (950PR vs. 950DT, CANN, Day-0 DeepSeek V4 support): [[2026-06-09-deepseek-v4-inference-performance-gpus-engines-semianalysis]].

- ## Inference throughput and hardware cost by chip
	- Benchmark: GLM 5.2, 16K input / 2K output, total throughput per card. Costs are for an 8-card server at centralized-procurement prices. The all-in monthly cost spreads equipment, maintenance, supporting facilities and IDC (data center hosting) over five years.
	- | Chip | Throughput per card | Share of H200 throughput | 8-card server price | All-in monthly cost per server | Bare-metal rent per server per month |
	  |---|---|---|---|---|---|
	  | Ascend 910B4 | 169 tokens/s | 8% | RMB 0.65M | RMB 16.1K | — |
	  | Ascend 910C | 483 tokens/s | 22% | RMB 2.15M | RMB 48.7K | — |
	  | **Ascend 950DT** | **1,951 tokens/s** | **89%** (82% at 7K/2K; report's conclusion **86%**) | RMB 2.97M | RMB 63.6K | **RMB 84.3K** |
	  | NVIDIA H200 | About 2,200 tokens/s (report's estimate from vLLM data) | 100% | — | — | **RMB 130K** |
	- **Generational step**: the 950DT has **4× the throughput of the 910C** and **11.5× the 910B4**. Per unit of all-in cost it delivers **3.1× the 910C and 2.9× the 910B4**, because its server costs only 38% more than a 910C server.
	- **Against H200**: the 950DT rents for 35% less than an H200 server (RMB 84.3K vs. RMB 130K a month). The report puts the 950DT's inference cost-performance about **30% above H200**.

- ## Does buying 950DTs to serve tokens make money?
	- The report assumes tokens are sold at **50% of each model's official API price**:
	- | Model | Tokens per server per month | Monthly revenue per server | Implied revenue per million tokens | Vs. RMB 63.6K all-in monthly cost | Cash payback (author's estimate) |
	  |---|---|---|---|---|---|
	  | GLM 5.2 | 32.57B | RMB 100.7K | RMB 3.09 | Profitable | **About 43 months** |
	  | DeepSeek V4 Pro | 35.65B | RMB 56.1K | RMB 1.57 | **Does not cover cost** | **About 86 months**, beyond the report's 5-year (60-month) amortization period |
	- **Price, not throughput, decides it**: DeepSeek V4 Pro produces about the same token volume per server as GLM 5.2 but earns about half the revenue, because its API price is roughly half GLM's.
	- **The author's correction**: the report states a month has 26 working days but computes capacity on 30 days, which overstates monthly output. The payback estimates are the author's rough cash numbers covering 5-year maintenance-inclusive equipment cost, supporting investment, and monthly IDC and staff costs. They exclude financing costs, tax differences and operating risk.

- ## Author's sensitivity: serving Kimi K3 on a 64-card supernode
	- **Pricing**: Kimi K3's official China API price is RMB 20 per million input tokens and RMB 100 per million output tokens. At 50% of list, with a 7K input / 2K output mix and no cache hits, blended revenue is about **RMB 18.9 per million tokens**.
	- **Break-even throughput**: matching the bare-metal rent of a 64-card supernode (8 servers, RMB 674K a month) requires selling about **35.7B tokens a month**. Under the report's usage and utilization assumptions that is about **462 tokens/s per card**.
	- **Why GLM numbers don't carry over**: K3 has **2.8T parameters** and its full low-bit quantized weights do not fit on one 8-card server, so the GLM 5.2 throughput cannot be applied directly.
	- **Payback sensitivity**:
		- | K3 throughput per card, relative to GLM 5.2 | Cash payback on hardware |
		  |---|---|
		  | 20% | About 34 months |
		  | 10% | About 77 months |

- ## Training is a different story
	- **Raw compute**: the 96GB 950DT in the report has **425 TFLOPS of FP16** per card. H200 SXM has about 990 TFLOPS of dense FP16, so the 950DT reaches only **about 43% of H200**.
	- **Other training hurdles**: large-scale training also depends on communication efficiency, numerical precision, memory capacity, the software ecosystem and long-run stability. The author hints that Ascend's software ecosystem is a known weak spot.
	- **Why it matters**: DeepSeek and Huawei are working together on pretraining models on Ascend. The author says the open question is whether Ascend can support DeepSeek's next-generation large-scale pretraining. On inference, the author calls the 950DT's results "a report card well worth watching" if the data is validated.
