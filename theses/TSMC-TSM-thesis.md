tags:: [[$TSM]], [[TSMC]], [[semiconductors]], [[foundry]], [[CoWoS]], [[advanced-packaging]], [[AI infrastructure]], [[$NVDA]], [[$AAPL]], [[Taiwan]]

- **Company**: Taiwan Semiconductor Manufacturing Company (TSM / 2330.TW)
- **Date**: 2026-07-12
- **Market cap at writing**: ~\$1.9T (JPMorgan, Jun 2026; \$1.14T as of Nov 2025)
  
  ---
- ## References
	- | | |
	  |---|---|
	  | TSMS numbers - \$TSM (spreadsheet) | Monthly revenue |
	  | r/semiconductors | SemiAnalysis Foundry Industry Model |
	  | [[2026-06-04-tsmc-agm-cc-wei-ai-demand-2026]] | [[2026-06-02-tsmc-supply-chain-podcast-node-economics-capacity-and-dram-constraints]] |
	  | [[2026-04-09-tsmc-copos-vs-intel-emib-packaging]] | [[2026-06-21-semidoped-advanced-packaging-cowos-emib]] |
	  | [[2026-06-03-gavin-baker-semiconductor-ai-infrastructure-thesis]] | [[2026-07-10-etched-inference-chip-rack-architecture-podcast]] |
	  | [[2026-07-03-samsung-foundry-wins-skhynix-capacity-roadmap]] | [[2026-07-03-sram-renewed-life-ai-memory-architecture]] |
	  | [[MediaTek-MTK-thesis]] | [[DRAM-memory-ssd-index-thesis]] |
	  
	  ---
- ## Main Narrative
	- **TSMC will be a winner of AI Semis long term no matter where the growth is coming from — GPU or ASIC, Cloud or Edge AI chips — most if not all manufactured by TSMC foundry services.**
	- AI is transforming TSMC completely: make more profit from **leading-edge nodes by charging a high price**, rather than from trailing nodes after full depreciation. Reworking 5nm fabs for 3nm; expanding 3nm capacity globally — "historically, we do not add additional capacity to a node once it reaches its targeted capacity" (2026 Q1).
	- The power dynamic shifted from a **unipolar world (Apple) to a bipolar world (Apple + AI)**: Apple is the predictable baseline that justifies massive fixed costs of new fabs; Nvidia/AI provides the high-margin upside. TSMC can arbitrage demand between the two to maintain pricing power (2026/01).
	- From the memos: TSMC is the **disciplined governor of the entire AI cycle** — the single wafer bottleneck preventing an AI macro-bubble. If TSMC expanded to meet unconstrained demand, Nvidia could sell **\$2–3T of GPUs in 2026/27** (Gavin Baker). CC Wei (AGM Jun 2026): global AI chip demand **"cannot be met for years"**; shortage spreading from low-end to high-end devices by end-2026.
	- The "shovel-seller" framing: TSMC makes **~95% of AI chips but AI is still <30% of its exposure** — lower-volatility AI exposure vs boom-bust product-cycle names (JPM primer).
	- ---
- ## Napkin Math
	- **Foundry 2.0** (includes packaging, testing, mask-making, and all IDM excluding memory manufacturing): TAM ~**\$250B in 2023**, forecast ~10% y/y growth in 2024. **TSMC share 28% in 2023**, expected to increase.
	- Wafer ASP trajectory: **\$5.38K (2Q23) → \$8.60K (1Q26)**, +60% in under 3 years; annual ASP \$2,346 (2011) → \$4,334 (2022F) — the AI era roughly doubled the historical ASP slope. Gross margin now **mid-to-high 60s** ("extraordinary for a manufacturer").
	- AI revenue (Morgan Stanley): server AI ~**\$55B and ~34% of revenue by 2027e** (from ~5% in 2021), split general-purpose AI + ASICs + CoWoS/wafer test.
	- Breakeven check (Nov 2025, ROE table): TSMC LTM revenue \$119.1B, net margin 39.5%, ROE 28.1%; **revenue growth needed next 5 yrs: 11.75%** — the *lowest* hurdle among Mag7/NVDA/AVGO peers, i.e. the least demanding valuation on that screen.
	- | Scenario | Revenue (5Y) | Revenue (10Y) | Margin | Net Income (10Y) | Fair PE | Implied Price |
	  |----------|-------------|--------------|--------|-----------------|---------|---------------|
	  | Bear     |             |              |        |                 |         |               |
	  | Base     |             |              |        |                 |         |               |
	  | Bull     |             |              |        |                 |         |               |
	- See Appendix for quarterly wafer shipments/ASP table and per-GW revenue math.
	  
	  ---
- ## Key Value Drivers
	- **Pricing power from leading-edge tech** requiring decades of know-how accumulation: "the leading edge costs a lot of money to ramp up but those costs are made up for by the ability to charge much higher prices." N2 wafer prices reportedly **+10–20% vs prior generation** (partly to recoup US expansion costs); 3nm prices **+5%** and advanced packaging **+10–20%** (2024/09).
	- **Competitive business model from mature nodes**: low-cost high-margin chips in fully-depreciated fabs; undercut competitors on price; specialized technologies (JASM Fab 1 CMOS sensors, ESMC automotive) rather than raw capacity. Winding down Fab 2 (6-inch) and Fab 5 (8-inch) to optimize support for leading edge.
	- **AI drives larger chip sizes** on the edge (smartphones, PCs) and eventually an upgrade cycle; AI chips are growing into "super chips" with very large die — posts challenges (and pricing power) to packaging.
	- **Advanced packaging margins approaching fab margins** — used to be a lower-margin business. CoWoS capacity 17K → 33K wpm in one quarter (2024/09); Nvidia (with ~80% gross margins) *agrees to price increases* to secure packaging capacity. TSMC allocated **27% of CoWoS capacity to ASICs in 2025 at better margin**; total AI semis ~30% of revenue in 2026 (2024/12).
	- **ASIC wave is accretive, not dilutive**: UBS per-GW math — Nvidia Rubin gives TSMC **~\$1,102M revenue per GW** vs Google TPU v7p **~\$1,895M per GW** (10.9% of customer sales vs 5.0%). Hyperscaler ASICs give TSMC a *larger* share of the value per GW than Nvidia GPUs do.
	- **Capacity allocation discipline**: only **20–30% of capacity to Nvidia** despite demand — preserving customer diversification; behaves like a long-horizon allocator of scarce industrial capacity.
	- ---
- ## Secular Trends as Tailwinds
	- **Agents driving compute demand**: Wei and team convinced (2026 Q1, per Stratechery) that (1) agents are real and (2) agents drive a massive expansion of compute demand.
	- **AI consumes ~60% of TSMC N3 in 2026 → ~86% in 2027** (SemiAnalysis); real capacity relief only ~2032–2034 (Arizona/Japan ramps). N2 allocation being urged as far out as 2Q27; capacity "close to sold out for the next two years" (2026/03).
	- **Huang's Law where Moore's Law left off**: 1,000× single-chip inference performance in 10 years (number representation ~16×, complex instructions ~12.5×, process ~2.5×, sparsity ~2×) — process is a *minority* of the gain, but every vector runs through TSMC silicon + packaging.
	- **Hyperscaler capex supercycle**: Google to ~\$185B (2026 plan), Amazon ~\$155B, Microsoft ~\$125B+ — the "AI Industrial Revolution" capex all terminates in TSMC wafers, CoWoS, and HBM base dies.
	- **Every inference-ASIC challenger still needs TSMC**: OpenAI/Broadcom Jalapeño (3nm, TSMC-fabbed), Cerebras (N5 wafer-scale), Taalas (N6), Etched — "specialized silicon" diversifies *architectures*, not *foundries* ([[2026-07-06-openai-broadcom-jalapeno-hn-cerebras-hbm-readthrough]], [[2026-07-06-gpt56-sol-hn-cerebras-inference-economics]]).
	- ---
- ## Innovative Culture
	- **"Night Hawk" model**: 24/7 shift-based R&D — a key source of execution speed.
	- **Customer-success-as-religion**: "TSMC 說客戶成功就是他成功, 他是真心這樣想的" (TSMC genuinely believes customer success is its success — "for years I didn't believe it, thought it was a slogan"). "缺貨不會漲客人價" — it doesn't jack up prices on customers even in shortage.
	- **Taiwan manufacturing culture**: highly capable people willing to work long hours for relatively modest pay; mass-production excellence is where Taiwan excels. Counterpoint (talent risk): after 2001 Taiwan's best engineering talent went to IC design (MediaTek paid ~\$300K/yr vs TSMC \$100K) — a **20–25 year talent-layer gap**; "under 50 there is no top Taiwan talent at TSMC."
	- High-NA EUV purchased from ASML but held until profitable mass production — disciplined, not first-mover-flashy.
	- ---
- ## Vibe Checks
	- **What do you like most?**
		- The only company in the world where *every* AI roadmap (Nvidia, AMD, Google, Amazon, Microsoft, Meta, OpenAI, Apple) converges — with pricing power finally being exercised, and packaging becoming a second margin engine.
	- **What do you hate most?**
		- Geographic concentration in Taiwan (25% of Taiwan's tax revenue, ~10% of its electricity) and a US buildout with structurally terrible economics (8% GM wafers at Fab 21 vs 62% in Taiwan).
	- **How popular is the product or service?**
		- Customers pay upfront, beg for allocation (N2 sold out ~2 years ahead), and Apple literally runs out of chips (A19 Pro shortage; MacBook Neo blew through the A18 Pro stockpile, May 2026). Etched founders: "best customer service seen in any industry."
	- ---
- ## Competition Landscape
	- | Competitor | Threat level | Key advantage | Assessment |
	  |------------|-------------|---------------|------------|
	  | Samsung Foundry | Low→Medium (rising) | Price flexibility; GAA experience since 3nm (one generation ahead of TSMC on GAA); memory+foundry bundle | ~3 yrs behind TSMC in PPA (~1 yr behind Intel); Nvidia/Qualcomm test nodes there but keep highest-volume at TSMC. 2nm inroads real: Tesla AI6 (entire volume, ~\$16.5B), Exynos 2600 proving ground, Grok LPU, Anthropic 2nm, Google Icefish TPU I/O die (split-mfg w/ TSMC 1.4nm compute). Yield 50–60% vs TSMC ~80% at 2nm. 7.3% share vs TSMC 70.2% (2Q25) |
	  | Intel Foundry | Low→Medium | EMIB-T advanced packaging (predates CoWoS-L); 18A RibbonFET+PowerVia; US-soil politics; packaging offered as standalone service (bring TSMC dies) | Packaging customers: Amazon, Cisco, new commitment from SpaceX & Tesla; Nvidia testing. External foundry business expected to stay relatively small; more Intel products in-house. 18A vs N2: Intel wins backside power, TSMC wins density/yield-maturity/track record/Apple qualification/proven packaging |
	  | Terafab (Tesla/SpaceX/xAI) | Low (long-dated) | Capital, vertical integration hunger | "It takes 2–3 years to build a new fab. No shortcuts. Another 1–2 years to ramp." Foundry fundamentals never change: technology leadership, manufacturing excellence, customer trust, and most of all *service*. No process IP (SemiAnalysis) |
	  | SMIC | Low (ex-China) | State backing | Distant fourth; likely remains so |
	  | GlobalFoundries / UMC | Low | Mature nodes | 5th/6th; Groq's LPU was GF 14nm — proof ASICs *can* skip TSMC, but the exception |
	  | China domestic (Naura, ACMR, AMEC toolchains) | Medium at low end | Subsidy; good-enough tools | "The lower end of the stack will 100% get disrupted" — next decade about Chinese *competition*, not revenue exposure. EUV-class capability still 10+ years away |
	  
	  ---
- ## Durable and Unfair Competitive Advantages
	- **~2-year structural process lead** (characterized as structural, not cyclical). The TSMC/UMC precedent: staying "one generation behind" compounded into an **~80× market-cap divergence over 25 years** — being behind at the leading edge means small profits, then surrender ([[2026-03-20-asic-vs-gpu-trainium]]).
	- **DTCO lock-in**: Design-Technology Co-Optimization binds large fabless customers at the design stage; the earlier a customer co-optimizes, the harder migration becomes. The "Iron Triangle": startups can't win with a "better GPU" because everyone lives inside TSMC's design rules (Gavin Baker).
	- **Service moat, not only process** (Etched, 2026/06): proposed a yield-improving process change → TSMC ran the experiment *at its own expense* and moved the line when it worked. Leading-edge advantage = collaborative process optimization + execution speed + financing flexibility + trust, not just transistor density.
	- **Advanced packaging as a wafer-pull lever, not a standalone P&L**: TSMC can price packaging aggressively to defend foundry share (cross-subsidize); Intel needs packaging to be independently profitable — a structural pricing disadvantage for Intel. TSMC expected to take ~10% of the EMIB market itself by 2028/29.
	- **The Taiwan ecosystem cannot be moved**: ~1,000 niche supplier companies built up over decades; "TSMC without those other smaller companies is nothing." US fabs get "cheap labor for the low-level stuff; the majority will be held by Taiwanese."
	- **Scale + yield execution**: N3 reached **100% utilization within five quarters** of mass production; N2 at **~80% yield** entering stable mass production (vs Samsung 50–60%).
	- **Standard-setting power**: Samsung's HBM3E reportedly *failed NVDA verification due to TSMC's standard* (2024/05) — TSMC's specs discipline even the memory suppliers ([[DRAM-memory-ssd-index-thesis]]).
	- **Ecosystem leverage**: MediaTek as TSMC's #3 advanced-node customer acts as a capacity buffer TSMC can rebalance around ([[2026-05-01-mediatek-google-tpu-codesign-semi-cot-model]]); Winbond pulled into WoW 3D stacking shows TSMC can cultivate its own memory supply options.
	- ---
- ## Pre-Mortem — What Can Go Wrong?
	- 1. **Taiwan geopolitical event** — the unhedgeable tail. Japan buildout is the explicit diversification strategy ("if Taiwan goes under or gets attacked") and went phenomenally well — the exact opposite of Arizona; Japanese government eager, huge new fund. But US economics are brutal: **fab construction ~3× the Taiwan cost; Fab 21 gross margin per wafer ~8% vs 62% at Fab 18** (same \$17,500 ASP; depreciation 4.9×, labor/materials 2×).
	  2. **The monopoly under-investment trap** — "TSMC's customers realize their biggest risk isn't that TSMC gets blown up by China, but that TSMC's monopoly and reasonable reluctance to invest at the industry's pace means the industry fails to fully capture the value of AI." Conservative pricing/capex leaves value on the table (and hands the ASP windfall to memory makers — the de-commoditization memos argue two or three memory names may out-earn TSMC within a year or two).
	  3. **Customer concentration** — Apple 26% of revenue (~\$20B; only ~9% of Apple's COGS — value asymmetry favors TSMC), and top-10 customers now ~78% of revenue (2025) vs ~55% mid-2010s. HPC/AI (Nvidia + hyperscaler ASICs) now surpassing Apple; non-Apple revenue grows faster.
	  4. **Competitor break-through**: Intel coming online makes TSMC "hesitant to take too much price, because they, above all, are terrified about ever losing volume" (2024/02); Samsung 2nm GAA experience edge is the first time TSMC adopts GAA while Samsung has a generation of learning.
	  5. **AI overbuild / capital cycle** — wherever the overbuild lands (DCs, memory, or TSMC overcapacity) is where pricing breaks ([[2026-06-18-ai-bubble-debate-capital-cycle-cyclicality-podcast]]); capex keeps outgrowing depreciation (claim: capex declines after 3nm — hasn't happened; \$54B in 2026).
	  6. **Architecture risk (largely debunked but tracked)**: "AI chips settle on 12nm" — scaling 12nm→3nm delivered 2.9× vs 8× Moore's-Law expectation, so mature nodes + architectural specialization could suffice (Groq ran on GF 14nm). Counter-evidence: every major 2025–26 accelerator is on N3/N2. Related: SRAM stopped scaling (N2 bitcell = N5 bitcell) → differentiation shifts to the system stack where TSMC still leads, but the pure-shrink story is over.
	  7. **China disrupts the low end** — domestic WFE (Naura/ACMR/AMEC) is "not as good but good enough"; mature-node pricing pressure is structural.
	  8. **Talent hollowing** — the 20–25-year Taiwanese top-talent gap (lost to IC design comp) is TSMC's long-term hidden worry.
	- ---
- ## Friendly to Shareholders?
	- | Factor | Signal | Assessment |
	  |--------|--------|------------|
	  | Share dilution (annual %) | Minimal; no stock-comp culture (salary-based, unlike US peers) | Positive |
	  | Executive comp structure | Modest by US standards | Positive |
	  | Buyback history | Rare; dividend-first | Neutral |
	  | Dividend | Steadily growing NT\$ dividend | Positive |
	  | Insider ownership | Low founder-family ownership; national-champion governance | Neutral |
	- Pricing philosophy is customer-first over shareholder-first: "we don't change our pricing dramatically… number one, our customer has to be successful" — long-term compounding over short-term margin capture.
	- ---
- ## Anecdotes & Opinions
	- | Date | Source | Anecdote / Opinion | Signal direction |
	  |------|--------|--------------------|-----------------|
	  | 2026-06 | Etched founders (podcast) | TSMC customer service "best seen in any industry"; ran a yield experiment at its own expense, moved the line when it worked; early support won via deep technical discussion with a senior exec | bullish |
	  | 2026-06 | TSMC AGM (CC Wei) | AI demand "cannot be met for years"; even full US production can't meet US customer needs near-term; stock NTD 950 → 2,425 in a year; refuses memory-style price hikes ("long-term sustainable growth" pricing) | bullish |
	  | 2026-05 | Stratechery/Culpan | Apple can't get enough A19 Pro chips AND blew through its A18 Pro stockpile (MacBook Neo demand) — TSMC has no spare capacity for its largest customer | bullish |
	  | 2026-03 | Industry | TSMC urging clients to apply for N2 allocation out to 2Q27; large allotments "close to sold out for the next two years" | bullish |
	  | 2026-03 | Analyst opinion | TSMC remains dominant; Intel external foundry stays small; Samsung similar; SMIC distant 4th; GF/UMC mature nodes | bullish |
	  | 2026-01 | Analyst opinion | Capex now split between Moore's Law (2nm for Apple) and packaging density (CoWoS-L for Nvidia); bipolar demand (Apple + AI) lets TSMC arbitrage to maintain pricing power | bullish |
	  | 2025-11 | Korean press | Samsung discloses first 2nm results (GAA: +5% perf, +8% power eff., −5% area vs its 3nm gen-2); TSMC ~80% 2nm yield vs Samsung 50–60%; Samsung wins entire Tesla AI6 (~\$16.5B); Exynos 2600 is the proving ground | mixed |
	  | 2024-12 | Industry | TSMC produces ALL the above ASICs; allocating 27% of CoWoS to ASIC in 2025 at better margin; AI semis ~30% of revenue in 2026 | bullish |
	  | 2024-09 | Industry | Google eyeing long-term TSMC partnership for Tensor G5/G6 on 2nm — driven by Samsung's low 3nm GAA yields | bullish |
	  | 2024-09 | Industry | 3nm prices +5%, advanced packaging +10–20% next year; CoWoS 17K→33K wpm in a quarter; Nvidia (≈80% GM) agrees to price increases to lock packaging capacity | bullish |
	  | 2024-05 | Market chatter | Samsung HBM3E unable to pass NVDA verification due to TSMC's standard (SK Hynix +2% vs Samsung −1% overnight) | bullish |
	  | 2024-02 | Podcast (Daniel et al.) | Why aren't margins higher? Survivor culture: "been through so many rounds of boom and bust"; Morris Chang-era cost-plus mentality; not used to being the leader; finally raising prices but "worried about keeping everyone in the tent" as Intel comes online | mixed |
	  | — | Taiwan industry veteran (Chinese) | Post-2001 top Taiwan talent all went to IC design (MediaTek ~\$300K/yr vs TSMC ~\$100K, no stock) → 20–25-year talent-layer gap; but the culture is real: "customer success is TSMC's success"; shortage ≠ price hikes on customers | mixed |
	  | — | Supply-chain commentary | The Taiwan ecosystem (~1,000 niche suppliers) can't be moved to the US; "TSMC without those other smaller companies is nothing"; US gets the low-level work | neutral |
	  | — | Stratechery (Japan) | Japan buildout went phenomenally well — exact opposite of Arizona; 28nm auto-focused; TSMC's diversification strategy if "Taiwan goes under"; government eager with a huge new fund | bullish |
	  
	  ---
- ## Appendix
	- ### Quarterly wafer shipments, revenue, ASP (Napkin-Math backing table)
		- **Source**: TSMS numbers spreadsheet / company reports.
		-
		- | Quarter | Wafer shipments (K) | Revenue \$B | Wafer price (\$K) | QoQ |
		  |---|---:|---:|---:|---:|
		  | 1Q26 | 4,174 | 35.90 | 8.60 | +1.0% |
		  | 4Q25 | 3,961 | 33.73 | 8.52 | +5.1% |
		  | 3Q25 | 4,085 | 33.10 | 8.10 | +0.2% |
		  | 2Q25 | 3,718 | 30.07 | 8.09 | +3.2% |
		  | 1Q25 | 3,259 | 25.53 | 7.83 | −0.4% |
		  | 4Q24 | 3,418 | 26.88 | 7.86 | +11.7% |
		  | 3Q24 | 3,338 | 23.50 | 7.04 | +5.7% |
		  | 2Q24 | 3,125 | 20.82 | 6.66 | +7.0% |
		  | 1Q24 | 3,030 | 18.87 | 6.23 | −6.1% |
		  | 4Q23 | 2,957 | 19.62 | 6.64 | +11.4% |
		  | 3Q23 | 2,902 | 17.28 | 5.95 | +10.7% |
		  | 2Q23 | 2,916 | 15.68 | 5.38 | — |
	- ### TSMC 5nm wafer economics — Taiwan vs Arizona (as of 2025)
		- **Source**: SemiAnalysis. The quantified case that US reshoring is strategically necessary but economically dilutive.
		-
		- | Cost item | Fab 18 P1–3 Taiwan (depreciating) | Fab 21 multiple | Fab 21 P1 USA |
		  |---|---:|---:|---:|
		  | Fab capex | \$27.0B | 1.6x* | \$14.38B |
		  | Installed WSPM | 90K | — | 24K |
		  | Raw materials /wafer | \$1,520 | 2x | \$3,040 |
		  | Labor /wafer | \$1,800 | 2x | \$3,600 |
		  | Depreciation /wafer | \$1,500 | 4.9x | \$7,289 |
		  | Total cost /wafer | \$6,681 | 2.4x | \$16,123 |
		  | ASP /wafer | \$17,500 | 1x | \$17,500 |
		  | **Gross margin /wafer** | **62%** | — | **8%** |
		- Fab construction costs ~3× more in the US than Taiwan. Fab 21 total ~\$15.69B: equipment \$8.6B, cleanroom \$1.71B, concrete/steel ~\$2.76B, labor/installation \$604M, permits+fees ~\$1.31B non-capex.
	- ### TSMC revenue per GW of AI hardware (UBS)
		- **Source**: UBS estimates. Key insight: **ASICs pay TSMC more per GW than Nvidia does.**
		-
		- | Platform | Node | TSMC rev/GW (US\$M) | % of customer sales |
		  |---|---|---:|---:|
		  | Nvidia Blackwell Ultra (2025) | N4 | 1,099 | 4.5% |
		  | Nvidia Rubin (2026) | N3 | 1,102 | 5.0% |
		  | Nvidia Rubin Ultra (2027) | N3P | 1,948 | 5.6% |
		  | Nvidia Feynman (2028) | A16 | 1,400 | 5.2% |
		  | AMD MI450 (2026) | N2 | 746 | 4.3% |
		  | **Broadcom Google TPU v7p (2026)** | N3 | **1,895** | **10.9%** |
	- ### CoWoS demand by customer (K wafers)
		- **Source**: Morgan Stanley. Total demand 60K (2022) → 730K (2025e), 12x in 3 years.
		-
		- | Customer | 2022 | 2023 | 2024e | 2025e | 2025e share |
		  |---|---:|---:|---:|---:|---:|
		  | NVIDIA | 24 | 53 | 200 | 450 | 62% |
		  | Broadcom | 15 | 23 | 68 | 90 | 12% |
		  | Marvell | 2 | 1 | 18 | 70 | 10% |
		  | AMD | 1 | 7 | 40 | 60 | 8% |
		  | AWS+Alchip | 0 | 9 | 16 | 18 | 2% |
	- ### Packaging technology roadmap (vs CoWoS)
		- | Technology | Type | Key concept | Perf vs CoWoS | Cost |
		  |---|---|---|---|---|
		  | SoIC | 3D IC | Die-to-die hybrid bonding (Cu-Cu) | Highest (shortest interconnect, best power) | High |
		  | CoPoS | 2.5D panel | Panel-level CoWoS, larger area + throughput | Similar | Lower (economies of scale) |
		  | SoW-X | System-level | Full wafer-scale integration | Extreme | Very high, niche |
		  | InFO | 2D fan-out | No interposer, RDL | Lower | Lowest |
		- CoPoS mass production target 2028 (Nvidia Feynman) vs Intel EMIB-T H2 2027 — TSMC unusually *trailing* on this vector; but packaging is a wafer-pull lever it can cross-subsidize ([[2026-04-09-tsmc-copos-vs-intel-emib-packaging]]).
	- ### Customer concentration
		- Top-10 customers ≈ **78% of revenue (2025)**, up from ~55% mid-2010s (SemiAnalysis). Apple 26% of revenue but chips ≈ 9% of Apple's input costs — the value asymmetry runs in TSMC's favor. Non-Apple revenue growth has exceeded Apple's every year since 2019 except 2021.
	- ### Intel 18A vs TSMC N2 (SemiAnalysis comparison)
		- Intel advantages: backside power (PowerVia) now, gate-all-around parity. TSMC advantages: density (N2 more direct N3P successor), HVM timeline (4Q25 tie), yield maturity/track record, 15 years of Apple design qualification, proven advanced packaging at scale (CoWoS/InFO/SoIC vs EMIB/Foveros).
