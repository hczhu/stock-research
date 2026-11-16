tags:: [[DRAM]], [[NAND]], [[HBM]], [[semiconductor]], [[$005930.KS]], [[$000660.KS]], [[$MU]], [[$SNDK]], [[$TSM]], [[$NVDA]], [[CXMT]], [[foundry]], [[CXL]], [[KV-cache]], [[HBF]], [[capex]], [[buybacks]], [[smartphones]], [[PC]], [[consumer-electronics]], [[India]], [[Elon-Musk]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-15
file-updated-at:: 2026-11-15

- ## Memory/NAND 2026-11 updates
	- **Thesis**: Supply stays tight into 2027, but the capacity Samsung and SK Hynix are paying for in 2026 lands in 2028 together with CXMT's expansion. Meanwhile, high memory prices are already shrinking phone and PC volumes.
	- **Source**: \$DRAM news feed, Oct 15 to Nov 14, 2026. It cites DIGITIMES, Maeil Business, Omdia, Counterpoint, Macworld, SK Hynix conference talks and Elon Musk's X posts. Figures are as reported and have not been checked against company filings.
	- **Currency**: won converted at ₩1,336 per \$1 and rupees at ₹94.4 per \$1, using the [open.er-api.com](https://open.er-api.com/v6/latest/USD) rate published Nov 16, 2026.
- ## Capital Allocation: Shareholder Returns vs. Capacity
	- Samsung plans up to **\$82B** of shareholder returns and SK Hynix **\$75B**.
	- Maeil Business argues the money should go into capacity to stay ahead of China.
	- *My math*: the two companies' combined returns of about **\$157B** are roughly **1.9x** the about \$82B they are spending on equipment in 2026 (next sections). Both are choosing to return more cash than they spend adding supply, which supports pricing discipline. Maeil's point is that this also leaves room for CXMT.
- ## Base Dies Move to Foundries
	- **Nvidia's custom HBM (NVHBM)**: Nvidia wants every NVHBM base die made on TSMC's 3nm process, and Samsung agreed. That is a first for Samsung, which previously built its HBM entirely in-house.
	- **Yield gap**: one unverified source puts Samsung's 2nm yield at 50–60%, versus over 90% for TSMC's 3nm.
	- *My note*: the base die is becoming a foundry product, and TSMC captures that value even in Samsung's HBM. This continues the shift described in [[2026-09-04-hbm-base-die-becomes-a-foundry-business]].
- ## When New Supply Arrives
	- **2028 timing (DIGITIMES)**: Samsung and SK Hynix are spending a combined **\$82B** on equipment in 2026, but the extra supply doesn't arrive until 2028. That is when new Korean plants and CXMT's expansion come online together, which risks price competition in commodity DRAM.
	- **Q4 2026**: the market stays undersupplied, but contract price caps and weak consumer demand limit further price increases.
	- **Elon Musk**: "[China will be making a LOT of RAM in 2028](https://x.com/elonmusk/status/2110566143983223006)" (X, Oct 15). Musk also [called memory pricing excessive at every maker except Micron](https://x.com/elonmusk/status/2110126632572756339) (X, Oct 13), without naming Samsung or SK Hynix. That post is covered in [[2026-11-15-micron-memory-shortage-contracts-musk-pricing]].
- ## SK Hynix Architecture Claims
	- **Pooled DRAM (VP Joo Young-pyo, Intel AI Summit, Nov 12)**: several servers share remote DRAM over CXL instead of each relying only on its own HBM. Average time to first token in partner tests:
		- | Approach | Time to first token | Pooled DRAM is faster by |
		  | --- | --- | --- |
		  | Pooled CXL DRAM | 15.45s | baseline |
		  | External SSD | 33.56s | 54% |
		  | Evict KV cache and recompute | 80.76s | 81% |
		- The speedup column is *my math* from the reported times.
		- *My note*: SK Hynix's HBM is sold out, yet it is pitching cheaper pooled DRAM as part of the answer to the shortage. Even the HBM leader expects AI memory demand to spill into conventional DRAM tiers.
	- **Ahn Hyun at SEDEX** (before becoming head of SK Hynix's Americas unit):
		- AI infrastructure needs to scale about **20x by 2030**, and KV-cache overflow is the central bottleneck.
		- **Targets**: 3D-stacked DRAM bonded directly onto processor dies by **2028**, and a high-bandwidth flash (HBF) standard in **January 2027**.
- ## Demand Destruction From Memory Prices
	- | Market, Q3 2026 | Shipments | Change YoY | Source |
	  | --- | --- | --- | --- |
	  | Laptops | 46.4M | −20.6% | Omdia |
	  | All PCs | 58.1M | −21.2% | Omdia |
	  | Global smartphones | Not given | −20%, the weakest Q3 since 2012 | Counterpoint |
	  | India smartphones | 35.8M, a 10-year low | −26% | Counterpoint |
	- **Mix**: in India, phones under ₹20,000 (about \$212) fell 47%. Globally, Samsung and Apple gained share, to 23% and 22%, so the low end is shrinking fastest.
	- **Samsung Galaxy A**: Q4 production was cut by about 20%, about 10M units annualized. The A series is over 70% of Samsung's phone units, and Samsung's mobile business is heading for its first annual loss.
	- **Retail price increases**:
		- Galaxy S26 Ultra: \$1,299 → \$1,399 in October.
		- Galaxy Tab A11+ in India: up to ₹3,000 (about \$32).
		- Sandisk Extreme Pro portable SSD: 2TB at \$549.99 and 4TB at \$1,099.99. Macworld lists "Expensive (thanks to the AI apocalypse)" as a con.
	- **Product strategy**:
		- Samsung and LG are cutting memory specs to keep laptops at about \$750, a key Korean retail price point.
		- TVs are shifting toward premium models because "chip inflation" squeezes budget-TV margins.
	- *My note*: phone and PC makers are cutting units and memory per device rather than absorbing the cost. That shrinks the consumer bit demand the 2028 supply wave would otherwise go to. See [[2026-11-13-memory-shortage-pc-pricing-demand-and-inventory]] and [[2026-11-12-qualcomm-handset-softness-memory-apple-and-pricing]].
