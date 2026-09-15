- tags:: [[DRAM]], [[HBM]], [[NAND]], [[memory]], [[server]], [[data-center]], [[AI infrastructure]], [[supply]], [[pricing]], [[capex]], [[CXMT]], [[$005930.KS]], [[$000660.KS]], [[$MU]], [[$SNDK]], [[$285A.T]], [[$NVDA]], [[semiconductor]]

- ## Memory Feed, Sep 7–14 2026 — Demand Is Broadening Faster Than Usable Supply
	- **Source**: User-provided TickerTick `$DRAM` AI feed, covering articles visible through Sep 14 2026. The feed aggregates TrendForce, company statements, Korean and Japanese trade press, general news, and automated summaries; figures below retain source attribution and confidence labels.
	- **Thesis**: The strongest evidence is not simply that AI needs more HBM. AI training and inference are simultaneously pulling HBM, high-capacity RDIMM, LPDDR5X and enterprise SSD demand, while suppliers are shifting wafers and leading-edge processes toward those products. Because new cleanrooms arrive slowly and HBM consumes more wafer capacity than conventional DRAM, the mix shift is constraining PC, mobile and consumer DRAM even as those end markets weaken. The near-term setup remains favorable for memory suppliers, but the feed also shows the cycle's limiting mechanism: price-induced demand destruction is already visible in consumer electronics.
	- **Incremental read versus [[2026-09-04-dram-feed-cxmt-share-break-and-lta-floor-arithmetic]]**: the prior memo established the commodity vacancy and LTA discount. This update adds hard Q2 revenue/share data, sub-10-day supplier inventory, a >10-point 2027 demand-gap forecast, and specific timing for the supply response.
- ## Supply-Demand Dashboard
	- | Signal | Data point | Context | Confidence |
	  |---|---:|---|---|
	  | Global DRAM revenue, Q2 2026 | **\$154.73B, +59.5% QoQ** | TrendForce attributes the jump mainly to traditional DRAM contract pricing; bit shipments grew only modestly | High |
	  | Samsung / SK hynix finished-memory inventory | **<10 days** | KB Securities estimate dated Sep 7; consistent with historic-low supplier inventory reported by TrendForce | Medium |
	  | 2027 DRAM + NAND demand versus supply growth | **>10 percentage-point gap** | KB Securities forecast; useful directionally, but methodology is not in the feed | Medium-low |
	  | Conventional DRAM contract prices, Q3 2026 | **+13–18% QoQ forecast** | TrendForce; price growth moderates as PC and smartphone affordability binds | High |
	  | Mobile DRAM contract prices, Q3 2026 | **+8–13% QoQ forecast** | TrendForce verification; restocking is largely complete and buyer inventories are comfortable | High |
	  | HBM4 wafer intensity | **~3× conventional DRAM** | Repeated secondary-industry estimate; explains crowding-out, but product and die-density assumptions matter | Medium |
	  | Samsung 4nm capacity allocated to HBM4 base dies | **50–60%; >15k wafers/month** | ZDNet Korea-derived estimate for Aug 2026; logic-base-die capacity, not DRAM-stack wafers | Medium |
	  | SK hynix 1c share of DRAM production | **10% Q1 → 13% Q2 → 24% Q3E → 34% Q4E → 35% Q1 2027E** | TrendForce citing ChosunBiz; node migration raises bits per wafer but is being aimed at HBM4E/server products | Medium-high |
	  | Micron acquired Taiwan fab | **\$1.8B; >10% capacity uplift by late 2027** | Feed summary; a meaningful addition, but too late to solve 2026 tightness | Medium |
	  | Samsung P5 Phase 1 | **late-2028 mass-production target** | Sep 7 piping contract starts an 8–10 month cleanroom-infrastructure milestone before tool install and yield ramp | Medium-high |
- ## Demand: Four AI Workloads Are Pulling at Once
	- **HBM**: HBM3E shipments remain strong and HBM4 is entering meaningful revenue. The demand base now includes Nvidia accelerators plus custom silicon from hyperscalers and AI labs.
	- **Server DRAM**: TrendForce explicitly attributes Q2 growth to high-capacity RDIMMs and says agentic AI is lifting RDIMM demand across capacities. General-purpose x86 servers remain important because agents generate tool calls and multitasking workloads outside the accelerator.
	- **LPDDR5X**: AI servers and specialized systems increasingly use low-power memory, while AI-phone adoption adds a smaller second demand vector. The feed reports both Samsung and CXMT supplying LPDDR5X into ZTE/ByteDance's Nubia flagship, showing that Chinese supply is now credible in premium mobile designs even if performance still trails the Korean leaders.
	- **Enterprise SSD / NAND**: KB Securities expects enterprise SSD demand to rise sharply in 2027, while SanDisk's Korea hiring and Kioxia's comments frame AI infrastructure as the reason NAND makers must sustain investment. This is directionally important but less quantitatively supported in this particular feed than the DRAM case.
	- **The US-China AI race expands both ends of the curve**: KB's framing is that frontier models raise the performance ceiling while lower-cost Chinese models lower the adoption floor. Both increase aggregate inference and token volume, which supports memory demand even if compute efficiency improves.
	- **The demand mix matters more than unit demand**: an AI server needs far more memory content and higher-value memory than a consumer device. A weak phone or notebook cycle therefore does not automatically loosen server/HBM supply.
- ## Supply: More Bits, but Not Enough Fungible Capacity
	- TrendForce says the big three will rely mainly on **process migration** in 2026–27. Wafer starts rise only modestly through process optimization, cleanroom acquisitions and reallocation from other products.
	- Process migration is not immediately fungible supply. New nodes need yield learning and qualification; HBM additionally needs known-good dies, base dies, TSV stacking and advanced packaging.
	- Samsung is using **more than half of 4nm foundry output** for HBM4 base dies. This validates demand but also reveals a second bottleneck: HBM4 competes for leading-edge logic capacity before the DRAM stack is even assembled.
	- SK hynix's 1c ramp should improve cost per bit, but the planned mix is aimed at HBM4E and high-value server DRAM. It is supply growth for the tightest segments, not a broad commodity flood.
	- Samsung P5 is under active construction, but a late-2028 target means cleanroom supply cannot close the 2026–27 gap. The feed's 8–10 month piping window precedes equipment installation, qualification and production ramp.
	- Micron's Taiwan fab acquisition is the clearest nearer-term wafer addition, but **late 2027** timing still leaves several quarters of scarcity. A >10% Micron capacity increase is material to the cycle once qualified.
	- SK hynix's Indiana project is a **packaging and test** facility using wafers made in Korea, not new front-end DRAM wafer capacity. Its official schedule—cleanroom Oct 2028, mass production in H2 2029—improves geographic resilience rather than near-term bit supply.
	- Kioxia rejected the idea of joint NAND production with SK hynix, citing the structure of its SanDisk manufacturing venture and antitrust obstacles. That removes one theoretical fast path to coordinated NAND supply expansion.
- ## Pricing: Scarcity Rent Is High, but Elasticity Has Arrived
	- Traditional DRAM pricing, not volume, drove most of the Q2 industry revenue surge. TrendForce says bit shipments increased only modestly while total revenue rose 59.5% sequentially.
	- Conventional DRAM contract pricing is still forecast up 13–18% in Q3, but the rate is moderating. High-capacity RDIMM buyers are shifting toward smaller modules, and PC/phone customers have less ability to absorb increases.
	- Mobile DRAM is already in a negotiation stalemate: restocking is largely complete, brands hold roughly **12–14 weeks** of inventory, and Q3 price growth is projected at 8–13%, below broader conventional DRAM.
	- PC makers are still replenishing inventory and server shipments should remain robust into 2027, but higher notebook prices are expected to reduce full-year unit volumes.
	- The clearest end-market warning comes from Samsung India reports: memory-chip prices have more than doubled while smartphone volumes weakened, squeezing margins and contributing to planned layoffs of roughly 80–100 executives. This is anecdotal, but it shows component inflation has crossed into OEM operating decisions.
	- Consumer DRAM can remain tight despite weak sell-through because suppliers are withdrawing capacity faster than demand falls. That is supportive for ASP, but not evidence of healthy end demand.
- ## How the Shortage Propagates
	- **Step 1 — AI raises premium-memory content**: accelerators take HBM, agentic CPU servers take RDIMM, and inference storage takes enterprise SSDs.
	- **Step 2 — producers optimize mix**: Samsung, SK hynix and Micron assign leading-edge wafers, engineering effort and packaging to HBM/server products where customer commitments and margins are highest.
	- **Step 3 — effective commodity supply contracts**: fewer wafers remain for PC, mobile, graphics and consumer DRAM even without an outright cut in total wafer starts.
	- **Step 4 — mature suppliers inherit the vacancy**: CXMT, Nanya, Winbond and PSMC gain pricing and volume in products the big three no longer fully serve.
	- **Step 5 — prices ration demand**: OEMs raise device prices, reduce memory configurations, build inventory selectively and cut low-end production.
	- **Step 6 — the shortage eventually creates its own ceiling**: lower device volumes and de-speccing weaken bit demand before greenfield fabs contribute meaningful supply.
	- This is why **tight supply and weak consumer demand can coexist**. The apparent contradiction disappears once wafer allocation is modeled by product rather than at the total-industry level.
- ## Supply Timeline
	- **Now through early 2027**: allocation and pricing do most of the balancing; supplier inventories remain exceptionally low and advanced-node transitions mainly feed premium products.
	- **Late 2027**: Micron's acquired Taiwan fab can add more than 10% to its capacity, the earliest discrete supply addition identified in the feed.
	- **Late 2028**: Samsung P5 targets mass production after cleanroom construction, tool installation and qualification.
	- **H2 2029**: SK hynix Indiana begins HBM packaging and test; because front-end wafers still come from Korea, it expands back-end resilience more than global DRAM bit capacity.
	- The practical conclusion is that **2026 scarcity is already baked in**, while 2027 is the key debate and 2028–29 capacity is too remote to anchor near-term pricing forecasts.
- ## Company Read-Through
	- | Company | Q2 2026 DRAM position | Supply-demand interpretation |
	  |---|---|---|
	  | Samsung | **\$60.98B revenue, +63.4% QoQ; 39.4% share** | Early HBM4 shipments plus the largest commodity exposure create the strongest upside to both bit growth and ASP; P5 is a late-2028 answer |
	  | SK hynix | **\$38.59B, +37.9%; 24.9% share** | HBM leadership supports mix and contracts, but its high HBM share limited Q2 ASP growth relative to commodity-heavy peers; 1c ramp is the key supply lever |
	  | Micron | **\$36.0B, +65.5%; 23.3% share** | Prioritizing high-priced server DRAM produced the fastest big-three revenue growth; acquired Taiwan capacity creates the most visible late-2027 share opportunity |
	  | CXMT | **10% global DRAM revenue share; 82% reported Q2 EBIT margin** | Benefits from DDR5 scarcity created by incumbent HBM pivots; 7,500-person R&D force, +60% YoY, raises long-run supply risk |
	  | SanDisk / Kioxia | Feed is qualitative in this window | AI expands NAND opportunity, but management emphasis on price stability and disciplined investment suggests supply response will be controlled |
	- Samsung and SK hynix held **83% of HBM revenue** in Q2—50% and 33%, respectively—so the HBM profit pool remains highly concentrated even as commodity DRAM share fragments.
	- CXMT's reported 82% margin—versus 76% for SK hynix and 70% for Samsung in the same secondary comparison—should not be treated as normalized economics. It is the output of an extreme spot-price window and may use non-comparable EBIT definitions.
	- CXMT is still the central medium-term bearish supply variable. Its share and R&D scale are real; its cost disadvantage becomes visible only when prices normalize.
- ## Stock View
	- **Near-term preference: Micron and Samsung for incremental upside.** Both retain more exposure than SK hynix to conventional/server DRAM price spikes, and both posted faster Q2 revenue growth. Micron adds the clearest 2027 capacity option; Samsung adds HBM4 catch-up and foundry integration.
	- **Highest-quality franchise: SK hynix, but more of the strength is contracted and recognized.** It remains the HBM leader and is moving aggressively to 1c, yet the feed shows why HBM leadership can lag in a quarter when commodity ASP moves faster.
	- **NAND is a selective, not blanket, long.** Enterprise SSD demand is AI-supported, but consumer NAND is softer and NAND bit supply scales more easily through layer transitions. The feed does not justify applying the DRAM shortage multiple to every NAND exposure.
	- **The most important bearish signal is demand destruction, not announced capacity.** Consumer affordability is already limiting DRAM price increases; if server buyers begin de-speccing or delaying deployment, pricing can turn before new fabs arrive.
	- **The second bearish signal is 2027 supply elasticity** from Micron's acquired fab, SK hynix's 1c migration and CXMT's expansion. None resolves 2026, but together they narrow the window in which a >10-point supply deficit can persist.
- ## Evidence Discipline
	- **High confidence**: TrendForce's Q2 revenue/share figures, modest bit-shipment growth, Q3 pricing ranges and supply-via-node-migration framework; SK hynix's official Indiana schedule.
	- **Medium confidence**: sub-10-day inventories, Samsung's 4nm allocation, HBM4's ~3× wafer intensity, SK hynix's 1c mix and Micron's capacity timing. These are credible trade-press or brokerage estimates rather than audited disclosures.
	- **Low confidence / do not put directly into a model**: the feed's claim that a 2025 OpenAI letter of intent represents **900,000 DRAM wafers per month** of committed demand. It is better read as a long-range ecosystem aspiration than a current purchase order; at face value it is too large to use without scope and timing definitions.
	- **Key falsifiers**: supplier inventory recovering above normal levels; server DRAM contract-price growth turning negative; CSP LTAs being reduced rather than extended; Micron/CXMT capacity qualifying earlier than expected; or consumer weakness spreading into server deployment delays.
