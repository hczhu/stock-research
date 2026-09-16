- tags:: [[$NVDA]], [[HBM]], [[DRAM]], [[memory]], [[$MU]], [[$005930.KS]], [[$000660.KS]], [[$TSM]], [[$AMD]], [[$META]], [[SemiAnalysis]], [[AI-ASIC]], [[inference]], [[bandwidth]], [[supply]], [[advanced-packaging]], [[substrates]], [[semiconductor]], [[token-economics]]

- ## SemiAnalysis — Why 4-High HBM Wins, and Rubin Ultra Falls From 1TB to 192GB
	- **Source**: SemiAnalysis — the **article** "The Optimal Mix of Bandwidth and Capacity" (added Sep 16 2026, with its three charts), and the **Semi Weekly podcast episode** discussing it. Analyst commentary is Myron's; the host presses on the supply-chain consequences. Memory-supplier specifics were kept behind their paywall and are absent here.
	- **Thesis**: HBM is **priced per gigabyte but bought for bandwidth**, and bandwidth per stack is fixed at four dies. That mismatch was tolerable while models strained capacity; it no longer is. The result is the first capacity *regression* in an Nvidia flagship — **Rubin Ultra cut from a previewed 1TB to 192GB, an 81% reduction and a third below what ships today** — driven by supply rationing rather than design preference. The second-order effects on cube output, commodity DRAM and the next bottleneck matter more than the headline.
- ## The revision, and the arithmetic behind it
	- | | Previewed at GTC | Now expected |
	  |---|---|---|
	  | Compute dies per package | 4 | **2** |
	  | Memory | HBM4E | **HBM4** at start |
	  | Die density | 32Gb (4GB) | **24Gb (3GB)** |
	  | Stack height | 16-high | **8-high** |
	  | Stacks | 16 | **8** |
	  | **Package capacity** | **1,024GB** | **192GB** |
	- Both configurations check out exactly: 16 × 16 × 4GB = 1,024GB; 8 × 8 × 3GB = 192GB. **The cut is 81%.**
	- **The part that has no precedent**: 192GB is **33% below the 288GB** shipping today in GB300 NVL72 and in vanilla Rubin. As the host puts it, this is "the first time in the history of me keeping track of Nvidia that the next frontier GPU is going to have less capacity than the previous one."
	- **The cause is stated plainly and is a rationing decision, not an engineering one.** Customers secured more TSMC logic than their HBM allocation can dress at 12-high: "if we take the HBM supply we have and ship it into 12-high cubes, it's not enough supply to ship all that logic. So let's ration our HBM supply and ship it in 8-high cubes. So you get more cubes from the implied wafers."
	- **Timing matters and is easy to misread**: this lands at **Rubin Ultra** — the generation *after* the Rubin being installed now, "if there was an R200, it would be the R300." Current 288GB parts are unaffected. This is a 2027–2028 event.
- ## The pricing mismatch that makes 4-high close to free
	- **HBM bandwidth is fixed per stack regardless of height.** HBM4 and HBM4E run **2,048 data wires** between cube and compute die, and each die supports up to **512 signal wires** — so **four dies saturate the interface.** Dies five through twelve add capacity and **exactly zero bandwidth**.
	- **But suppliers price per gigabyte.** An 8-high cube costs roughly 2× and a 12-high roughly 3× a 4-high cube **for identical bandwidth.** The conclusion is mechanical: "the dollar per bandwidth is much better for 4-high... if you're really bandwidth-focused, paying for 4-high only when all you really need is that bandwidth is almost a free lunch."
	- **This is the structural insight and it generalizes past this product cycle.** A component sold on one axis and valued on another creates an arbitrage that rational buyers will close. Nvidia is closing it. The read-through for memory suppliers is that **per-gigabyte pricing power is strongest exactly where the gigabytes are least useful**, which is not a stable arrangement.
- ## Stack reads per token — the unit that makes the mismatch measurable
	- The article supplies the metric the podcast only gestured at. **Bandwidth budget per token** = stack bandwidth ÷ tokens per second. **Stack reads per token** = that budget ÷ stack capacity. Illustrative table, HBM4 at 2.56 TB/s per stack:
	- | Interactivity | Bandwidth budget per token | 4-Hi (12GB) | 8-Hi (24GB) | 12-Hi (36GB) |
	  |---|---|---|---|---|
	  | 100 tok/s | 25.6 GB/token | **2.13** | 1.07 | 0.71 |
	  | 200 tok/s | 12.8 GB/token | 1.07 | 0.53 | 0.36 |
	  | 400 tok/s | 6.4 GB/token | 0.53 | 0.27 | 0.18 |
	- **How to read the ratio**, and it is the cleanest framing of the whole argument:
		- **= 1** — capacity and bandwidth are matched exactly. One token has precisely enough bandwidth to read the entire working set once, no more and no less.
		- **> 1** — bandwidth is nominally over-provisioned, but it is **rarely wasted**, because the surplus budget converts directly into more tokens per second.
		- **< 1** — the token cannot read all the installed capacity. The working set must then be smaller than physical memory, and **the difference is stranded.**
	- **The asymmetry is the investable conclusion**: *"bandwidth can normally be used up in its entirety, while spare capacity can not always be used up, whilst also carrying a cost that is only getting higher."* Over-provisioned bandwidth is latent throughput; over-provisioned capacity is dead weight on the BOM.
	- **And it worsens with speed.** Raising tokens per second lowers the budget per token, which lowers stack reads per token, which strands more capacity. Every increase in interactivity makes tall stacks less defensible — note the 12-Hi column never reaches 1.0 at any speed in the table.
	- Separate worked example in the text uses HBM4E: 2,048 pins × 13 Gbps = **3,328 GB/s** per stack, and 32Gb core dies give **16 / 32 / 48GB** at 4-, 8- and 12-hi. **Do not mix the two illustrations** — the table is HBM4 with 24Gb dies, the case study below is HBM4E with 32Gb dies.
- ## Batching, and the only condition under which capacity pays
	- The single-sequence analysis ignores batching, which is where inference economics actually live. **The saving from batching is amortizing one read of the weights across many users' requests** — every step reads the weights once regardless of batch size.
	- But concurrency consumes capacity, because **each user's KV cache must be resident**. So "increasing batch size is often how inference workloads become memory capacity bounded rather than bandwidth bounded."
	- **Concurrency is the lower of two ceilings**: capacity-bound (how many KV-cache sets fit in memory) and bandwidth-bound (how many users can be served at the minimum interactivity). Throughput = users × tokens/s/user.
	- **The condition for capacity to be worth buying is therefore specific**: once HBM comfortably holds the weights, extra capacity buys throughput **only through more batching** — and **the larger the weight footprint, the more each additional concurrent user unlocks.** Bigger models shift every breakeven to the right; this is the same batching mechanism behind the counter-argument recorded further down.
	- **One subtlety that flatters 4-hi and is easy to miss**: the per-user SLA is a **minimum**, not the delivered rate. When concurrency is capped by capacity, spare bandwidth remains, and it is spent on faster tokens per user. So 4-hi's lower batch size is "wholly or partially offset" by higher interactivity.
- ## The Kimi K3 roofline: where taller stacks stop adding tokens
	- Setup: **Rubin Ultra NVL576**, HBM4E at 13 Gbps, **8 stacks per GPU** — so 4-hi = **128GB**, 8-hi = **256GB**, 12-hi = **384GB** per GPU. Kimi K3 at **2.78T parameters**, **W = 16.8GB of weights per GPU** (2.1GB per stack), **K = 4.01GB of KV cache per user at 274k tokens**.
	- | Stack | Capacity/GPU | Users at capacity | SLA where capacity fills | Throughput |
	  |---|---|---|---|---|
	  | 4-hi | 128GB | **27** | **213 tok/s/user** | 5,749 tok/s per GPU |
	  | 8-hi | 256GB | **59** | **105 tok/s/user** | 6,202 tok/s per GPU |
	  | 12-hi | 384GB | **91** | **70 tok/s/user** | 6,350 tok/s per GPU |
	- **The user counts are reproducible from first principles**: (capacity − 16.8GB of weights) ÷ 4.01GB per user gives 27.7, 59.7 and 91.6 — matching the chart exactly. The model is internally consistent and can be re-run against other models.
	- **The breakevens are the headline.** At **105 tok/s/user**, 12-hi stops beating 8-hi. At **213 tok/s/user**, nothing beats 4-hi — *"right of the 4-hi point every stack height serves the same users at the same speed: the extra capacity of 8-hi and 12-hi sits idle."*
	- **Peak throughput gains are small**: 8-hi **+7.9%** and 12-hi **+10.5%** over 4-hi, at their best. Against that, accepting 4-hi's ceiling buys **more than double the interactivity** — 213 tok/s versus 105, or **3.0×** versus 12-hi's 70.
- ## The cost test, which is where the argument closes
	- Modelled as the BOM increase an end owner pays against a 4-hi HBM4E Rubin Ultra NVL576 baseline, using all-in system cost as a TCO proxy:
	- | Stack | System cost per GPU | Premium vs 4-hi | Best throughput gain | Verdict |
	  |---|---|---|---|---|
	  | 4-hi | \$120,350 | — | — | baseline |
	  | 8-hi | \$134,869 | **+12.1%** | +7.9% (SLA ≤105) | **short by 4.2 points at every SLA** |
	  | 12-hi | \$151,965 | **+26.3%** | +10.5% (SLA ≤70) | **short by 15.8 points at every SLA** |
	- **Neither taller stack ever pays.** The throughput gain comes in below the cost increase at *every* interactivity point, so at current memory prices — "along with Nvidia's margin stack" — **8-hi and 12-hi deliver a higher cost per token than 4-hi.** This is the quantitative form of the podcast's qualitative claim, and it is a stronger result than "4-high is cheaper per unit bandwidth": it says tall stacks lose on the metric buyers actually optimize.
	- **And the comparison is generous to tall stacks**, because it comes *before* KV-cache offloading to lower memory tiers, which reduces the resident capacity requirement further and pushes the breakevens left again. See [[2026-07-16-weka-kv-cache-nand-inference-memory-podcast]].
	- **Their own caveats, which mostly reinforce the conclusion.** This is a **roofline** analysis on peak bandwidth; achieved bandwidth is "significantly lower," which shifts the breakeven interactivity thresholds **left** — so tall stacks fare *worse* in reality, not better. It also covers **only the decode pool in a disaggregated prefill/decode setup.** The one caveat that cuts the other way is theirs too: shifted far enough left, the breakevens "could push into the speeds that users find unacceptably low," i.e. the regime where 4-hi wins may sit below a usable SLA.
- ## Why capacity stopped binding — and the arithmetic reconciles
	- The comparison is the cleanest quantitative argument in the episode:
		- **Hopper era**: an HGX node held 8 × 80GB = **640GB**. Llama 3.1 405B quantized at FP8 needed **405GB — about 63% of the node.** Capacity was the binding constraint, which is why HBM3E's density uplift on H200 mattered so much.
		- **Today**: NVL72 GB200 holds 72 × 288GB = **20,736GB**. Kimi K3 at 2.8 trillion parameters quantized at MXFP4 needs roughly **1,400GB — about 7% of the domain.**
	- **The decomposition**: parameters grew **6.9×**, bits per parameter halved, and the scale-up domain grew **32.4×**. Net utilization falls from 63% to ~7%, which reproduces the stated figure. Capacity headroom expanded by roughly an order of magnitude while everyone assumed it was tightening.
	- **And Rubin Ultra widens it again**: the scale-up domain goes to **NVL576**, another ~8× increase. Even at 8-high, aggregate HBM inside the domain rises.
	- **Why parameters stopped scaling**: reasoning, post-training and RL substitute for raw size. **Looped transformers** are called out specifically — "confirmed that GPT-6 Astra uses looped transformers... instead of adding parameter count, input goes through the layers more than once. You add compute depth, but you don't increase model size." Post-training is "very inference-like, so it also tilts to more bandwidth."
	- **Independent confirmation from data-center design**, which is a nice falsifiable tell: pre-training sites are identifiable by network topology and building size — **>100,000 GPUs in one building or an interconnected campus**, versus 2,000–8,000 GPUs spread across four data halls worldwide. Their read of the fleet data: **"the marginal data center that they bring into their fleet is not going towards pre-training."** Supports the compute-mix argument in [[2026-08-29-dylan-patel-dwarkesh-revenue-per-megawatt-compute-centralization]].
- ## Supply: more than double the cubes, and where the bottleneck moves next
	- Going 8-high → 4-high yields **more than double** the harvestable cubes, because die count and yield compound in the same direction. At an illustrative 99% per-layer stacking yield:
	- | Stack height | Compounded stack yield | Cubes per wafer vs 4-high |
	  |---|---|---|
	  | 4-high | **96.1%** | — |
	  | 8-high | 92.3% | 4-high yields **2.08×** |
	  | 12-high | 88.6% | 4-high yields **3.25×** |
	- Secondary manufacturing advantages: delivering power up a 4-die stack is materially easier than 8 or 12, and 4-high "has a longer manufacturing history and is simpler to manufacture — there's less steps to make a mistake."
	- **Relieving HBM does not relieve the system; it promotes the next constraint.** If cube output roughly doubles, the binding constraint moves to **leading-edge logic at TSMC** — can they double co-packaged logic wafers? "probably not quite" — then to **substrates**, where doubling is "going to be a big ask," then to **power.** Exactly the deepest-bottleneck dynamic argued in [[2026-09-05-circuit-broadcom-custom-asic-unmodelable-2027-peak-constraint]].
- ## The commodity DRAM dividend, which is the under-discussed part
	- Conventional DRAM is tight and **servers are being de-specced — per-socket DRAM taken down** — because **DRAM wafers are being cannibalized by HBM production.** Relaxing HBM wafer intensity returns wafers to server DRAM.
	- **Why that is not a side note**: agentic AI needs CPUs for tool calls, and "a lot of times we're bottlenecked by waiting for a CPU task." CPU demand is high, but those CPUs will be "poorly utilized because they don't have enough DRAM to support them." A 4-high shift is therefore a **throughput unlock on the CPU side of agentic workloads**, not merely an accelerator cost saving.
	- The framing worth borrowing: **tokens per HBM wafer**, by analogy to tokens per dollar. "HBM wafers are valuable and scarce resources... if you want to deliver the most tokens on aggregate, going 4-high is how you do that." Connects to the crowding-out thesis in [[2026-06-03-hbm-demand-scaling-crowding-out-conventional-dram]].
- ## When does the crunch ease — and a direct conflict with another memo
	- On why record-profit memory makers cannot simply add supply: cleanrooms are "the number one reason" — they must be built before equipment can be installed, and equipment is itself rationed. ASML can only produce so many EUV tools a year because its own suppliers, making things like ultra-smooth mirrors, have long lead times of their own.
	- **Their answer on timing is blunt: "The TLDR is not within this decade."** Not before 2030.
	- **This conflicts with [[2026-09-05-circuit-broadcom-custom-asic-unmodelable-2027-peak-constraint]]**, where Bajarin argues 2027 is peak constraint with meaningful relief arriving in 2028. The two are less far apart than they sound — Bajarin also expects the imbalance to remain above parity, improving only from 120–150% to 105–110% — but the difference in tone is material to positioning. **SemiAnalysis is saying the shortage does not clear; Bajarin is saying it eases.** Both cannot be the base case, and the distinction decides whether 2028 is a pricing-relief year or merely a less-bad one.
- ## The counter-argument, which they raise against themselves
	- **"At what point is 4-high not enough?"** If model sizes explode, the extra capacity of 8-high becomes worth paying for — and the mechanism is **batching economics**: with batching you read the weights once per batch, so the larger the weights, the more efficiency additional capacity buys.
	- They modelled **3× Kimi K3**: at that size, 8-high or 12-high "is much better, and it's probably worth the cost." So the thesis is explicitly conditional on parameter counts staying flat.
	- **Two arguments they offer against that risk, one weak and one strong.** The weak one is that techniques keep the footprint small. **The strong one is revealed preference: "the loudest cries for 4-high are coming from the labs"** — the parties best positioned to know how their own models will scale. Buyers asking for less capacity is more informative than vendors claiming it is sufficient.
	- A clever inference worth keeping: it "would be very embarrassing for OpenAI and Anthropic if Kimi K3 was this close to performance with them" at 2.8 trillion parameters — **"it's kind of implied that the models are of similar size to Kimi."** An open-weight model's competitiveness is being used to bound the size of closed frontier models.
- ## SKU proliferation is already here
	- Same base logic die, different memory configurations per customer. **Meta already takes custom and semi-custom SKUs with non-standard memory**, and for **AMD's MI450 there is a custom Meta version with 8-high HBM instead of 12-high.**
	- The historical pattern supports more of it: V100 16GB → 32GB, A100 40 → 80, H100 80 → H200. The expectation is "the Meta flavor of the Rubin Ultra, and the OpenAI flavor."
	- **Why this matters for modelling**: in a capacity-constrained world, over-provisioning a resource a customer does not need becomes expensive, so **per-customer memory SKUs proliferate — and blended HBM content per accelerator becomes a distribution rather than a number.** Another input that makes accelerator revenue harder to model from unit counts, compounding the unbundling problem already flagged for custom ASIC.
- ## Three memos in this repo carry the superseded figure
	- The 1TB Rubin Ultra number is load-bearing in DRAM demand models and appears in at least three places that now need correcting:
		- [[2026-05-24-ai-data-center-buildout-capacity-and-spend-scenario]] — "Rubin Ultra: 1 TB HBM," and again in the roadmap table as "1 TB HBM4e"
		- [[2026-06-01-memory-super-cycle-x-thread-and-memo]] — "Rubin Ultra (2027): 1 TB," and again in its table
		- [[2026-06-03-hbm-demand-scaling-crowding-out-conventional-dram]] — "Rubin Ultra roadmap increases per-GPU capacity to 1TB"
	- **The error is 5.3× on a per-package capacity input**, and it runs the wrong way for HBM bit demand while running the *right* way for cube counts. Any model built on those memos overstates HBM gigabyte demand per Rubin Ultra package and understates the number of packages a given HBM supply can dress.
- ## Glossary
	- **Stack construction**
		- **x-high** (4-high, 8-high, 12-high, 16-high) — **the number of DRAM dies stacked vertically inside one HBM cube.** An HBM part is a tower, not a flat chip. Capacity scales linearly with height; **bandwidth does not scale at all.** This asymmetry is the entire argument of the memo.
		- **Cube / stack** — one complete HBM unit: a base die with DRAM dies stacked on top. Several cubes sit beside the compute die on the same package. Used interchangeably in the source.
		- **Base die** — the logic die at the bottom of the stack that interfaces to the compute chip. From HBM4 it is fabricated on a logic node rather than a DRAM node — see [[2026-09-04-hbm-base-die-becomes-a-foundry-business]].
		- **TSV** — through-silicon via. The vertical wiring that connects stacked dies to each other and to the base die.
		- **Die density** — capacity of a single DRAM die, quoted in **gigabits**. 24Gb = 3GB (HBM4); 32Gb = 4GB (HBM4E). The source says "GB" where it means Gb; the memo converts.
		- **Package capacity** — stacks × height × die capacity. Rubin Ultra revised: 8 × 8 × 3GB = 192GB.
	- **Why height does not buy bandwidth**
		- **Data wires / signal wires** — the parallel interface between a cube and the compute die. HBM4 and HBM4E use **2,048 data wires**, and each DRAM die can carry up to **512** of them.
		- **Four-die saturation** — 2,048 ÷ 512 = **4**, so four dies already use every wire. Dies five through twelve add storage behind an interface that is already full: capacity up, **bandwidth unchanged**.
		- **Dollar per gigabyte vs dollar per bandwidth** — suppliers price HBM on **capacity**; inference buyers value **bandwidth**. A 12-high cube costs roughly 3× a 4-high one and moves data no faster, so dollar-per-bandwidth is best at 4-high. The mismatch is the arbitrage Nvidia is closing.
		- **Stack yield compounding** — every bonding layer multiplies its own yield loss, so tall stacks lose more. At 99% per layer: 96.1% at 4-high, 92.3% at 8-high, 88.6% at 12-high. This is why 4-high yields **more** than double the cubes of 8-high (2.08×), not exactly double.
		- **Harvestable cubes** — finished good cubes obtainable from a given DRAM wafer supply. The metric that matters when wafers, not designs, are the constraint.
	- **System and product terms**
		- **HBM4 / HBM4E** — sixth- and seventh-generation High Bandwidth Memory. HBM4E carries denser dies (32Gb vs 24Gb) and arrives later.
		- **Rubin / Rubin Ultra** — Nvidia generations. Rubin is shipping and installing now at 288GB; **Rubin Ultra is the generation after it** — "if there was an R200, it would be the R300." The capacity cut applies only to Rubin Ultra.
		- **Scale-up domain** — the set of accelerators connected coherently enough to be treated as one pooled memory system. **Aggregate capacity across the domain, not per-package capacity, is what a model must fit into.**
		- **NVL72 / NVL576** — scale-up domains of 72 and 576 GPUs. NVL72 at 288GB each is 20.7TB of pooled HBM; Rubin Ultra moves to NVL576, another ~8× step.
		- **HGX** — Nvidia's 8-GPU baseboard, the pre-rack unit. A Hopper HGX node held 8 × 80GB = 640GB, the baseline for the capacity-pressure comparison.
		- **De-specced** — reducing per-socket server DRAM because supply is short. Currently happening because DRAM wafers are being cannibalized for HBM.
	- **Workload terms that decide the trade-off**
		- **KV cache** — per-user conversational state held in HBM alongside the weights. The main consumer of capacity beyond the model itself, and what sets the batching ceiling.
		- **Batching economics** — with batching the weights are read **once per batch**, so the larger the weights, the more throughput each extra gigabyte of capacity buys. This is the mechanism behind the counter-argument: if models get much bigger, 8-high wins again.
		- **Quantization (FP8, MXFP4)** — bits used per parameter. Moving FP8 → MXFP4 **halves** the capacity a given model needs, and is half the reason capacity stopped binding.
		- **Looped transformer** — adds capability by passing input through the same layers repeatedly, buying **compute depth instead of parameter count**. Reportedly used by GPT-6 Astra, and a direct reason parameter counts have stopped scaling.
		- **Tokens per HBM wafer** — the source's framing, by analogy to tokens per dollar. If HBM wafers are the scarce input, the right objective is aggregate tokens per wafer, which favours shorter stacks.
