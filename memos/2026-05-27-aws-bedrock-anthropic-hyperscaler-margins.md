- tags:: [[AWS]], [[$AMZN]], [[Anthropic]], [[Bedrock]], [[$MSFT]], [[Azure]], [[$GOOGL]], [[GCP]], [[hyperscalers]], [[TaaS]], [[AI]], [[margins]], [[Trainium]], [[Graviton]], [[SemiAnalysis]]
  file-created-at:: 2026-05-27

- ## AWS Bedrock / Anthropic Deal Drives Margin Divergence Across Hyperscalers
	- **Source**: SemiAnalysis — "Anthropic Growth and Bedrock Mix Drive AWS Margins Higher While Peers Lag", Jeremie Eliahou Ontiveros, Joey Brookhart, Crystal Huang, Dylan Patel. May 27, 2026.
	- **Thesis**: AWS is the only hyperscaler showing a true rising margin trend in 1Q26. The driver is Bedrock's Token-as-a-Service (TaaS) model combined with Anthropic's explosive ARR growth, Trainium vertical integration, and superior capacity execution. The margin story at Azure and GCP is either declining or distorted. Oracle and neoclouds are far behind with practically zero TaaS revenue.

- ## The Core Framework: TaaS vs. IaaS Economics

	- **IaaS (Infrastructure-as-a-Service)**: Cloud provider rents GPUs to customers on multi-year take-or-pay contracts. Revenue is predictable but margins are structurally capped — effectively a hardware rental business.
	- **TaaS (Token-as-a-Service)**: Cloud provider sells tokens on behalf of an AI Lab (e.g. Claude via Bedrock). The AI Lab is the seller of record; the CSP earns an infrastructure fee plus a **revenue share / distribution fee**. Revenue is variable but margins are significantly higher than IaaS.
	- **Why TaaS margins are higher**: The distribution fee layer on top of the infrastructure fee creates margin well above the underlying compute cost. The CSP is not just renting hardware — it is a distribution channel for frontier model IP. This is not available to neoclouds or Oracle.
	- **Access to frontier models is the moat**: Only three CSPs can currently sell OpenAI, Claude, and Gemini tokens. AWS recently gained OpenAI access (in addition to existing Claude). Microsoft recently gained Claude access (in addition to existing OpenAI). No other CSP has access to all three frontier models simultaneously.

- ## AWS / Amazon: The Margin Outperformer

	- ### Bedrock Business Metrics
		- AWS EBIT margins inflected in 1Q26: **+213bp Q/Q** while all other CSPs lagged
		- AI as % of total AWS revenue: `2%` (1Q24) → `10%` (1Q26)
		- Bedrock as % of AWS AI revenue: `9%` (1Q25) → `37%` (1Q26) → est. `53%` (2Q26E)
		- Bedrock revenue growth: `+60% Q/Q` (4Q25), `+170% Q/Q` (1Q26)
		- Bedrock estimated run rate: **`$5.5B`** with `80–90%+` of volume on Anthropic models
		- Bedrock accounted for **`30%` of the step-up in Gross Profit Dollars Y/Y** despite representing only **`4%` of total AWS revenue** — the clearest illustration of TaaS margin leverage
		- Anthropic ARR per MW on Bedrock compute: ~`$26M` (1Q26E) → ~`$42M` (2Q26E)
		- Implied Bedrock EBIT margins: **~`55%`** at $26M/MW Anthropic ARR/MW in 1Q26

	- ### Deal Structure (Bedrock / Anthropic)
		- Flat IaaS fee + **revenue share** + performance hurdles for outperformance above certain token/spend throughput thresholds
		- Anthropic is the seller of record; AWS invoices customers and earns both an infrastructure fee and a distribution/revenue share fee
		- Anthropic's revenue is recognized on a gross basis; margins on Bedrock are slightly negative mix vs Anthropic's blended ~low-60% inference gross margins — but still highly accretive to AWS EBIT vs standard IaaS

	- ### Vertical Integration: Trainium + Graviton
		- **Trainium**: In Bedrock, the underlying hardware is abstracted from customers (they only see tokens). This makes Bedrock a natural offtake for Trainium inference. Per AWS CEO Matt Garman (Nov 2025): **"Trainium chips now power more than 50% of Amazon Bedrock token usage."** Trainium2/3 offer leading perf/TCO for high-batch inference and RL workloads where memory bandwidth is the bottleneck.
		- **Graviton**: Amazon's fifth-generation custom CPU. Graviton4 and 5 provide a **perf/TCO advantage** over merchant (Intel/AMD) solutions. Graviton4 is integrated into Trn3 as head node and handles RL and agentic workloads. Amazon has large Graviton deals with **Anthropic, OpenAI, and Meta** — indicating CPU vertical integration is becoming a revenue stream in its own right.
		- Upselling Graviton to existing Bedrock customers is a natural, low-friction incremental revenue path.

	- ### Capacity: AWS Is Building More Than Anyone
		- Amazon has secured more power than any other CSP besides Google, signing multi-billion dollar PPAs with IPPs including **Talen, Vistra, and NiSource**
		- Net new MW additions: AWS will add more capacity than any other CSP in `2025`, `2026`, and `2027` per SemiAnalysis Datacenter Industry Model
		- Speed advantage: AWS built close to **`2 GW` in Indiana and Mississippi** — described as "lightning speed" vs rivals
		- New datacenter design rolling out at large scale: increased modularity and prefabrication will further widen the speed advantage

- ## Anthropic: The Engine Behind Bedrock's Outperformance

	- ### Revenue and ARR
		- Anthropic added **`$21B` in net new ARR in 1Q26** to reach **`$30B` of ARR**
		- API revenue grew **~`13x` Y/Y**
		- Revenue is primarily API and Enterprise (vs OpenAI which skews consumer with heavy inference cost load from free users)
		- Demand driven by **Claude Code**, which has taken enterprises by storm
		- Anthropic gaining majority share of **net new customers vs OpenAI** in card panels; higher average transaction values
		- SemiAnalysis estimates potential for **well over `$100B` in ARR by year-end**

	- ### Margin Progression
		- Inference gross margins: **`-94%`** (2024) → **`38%`** (2025) → **mid-60s** (1Q26)
		- Expected to be **Operating Income profitable in 2Q26** (adjusted for SBC), per WSJ May 20, 2026
		- SemiAnalysis cost model (allocating Free/Paid Inference, Training, OpEx) was highly aligned with Anthropic's actual revenue, cost mix, and GAAP EBIT trajectory

- ## Microsoft / Azure: IaaS-Heavy, Margin Pressure, Capacity Constrained

	- ### Margin and Mix
		- Azure margins on a **downward trend** — the opposite of AWS
		- AI as % of total Azure revenue: `27%` in 1Q26 (vs `10%` AWS, `36%` GCP)
		- AI IaaS still `80%+` of Azure AI business mix — heavily IaaS-oriented relative to AWS's `37%` Bedrock TaaS mix
		- Microsoft Copilot (365) and GitHub Copilot have **"failed to create traction"** — have not become meaningful margin contributors comparable to Bedrock

	- ### OpenAI Dependency and Capacity Lock-in
		- The vast majority of Microsoft's AI compute is committed to **OpenAI via long-term compute contracts**
		- **OpenAI's backlog alone is `2.5x` total Azure annual revenue** — an extraordinary share of Microsoft's backlog locked to a single customer
		- This reduces compute available to the broader Azure customer base and limits TaaS optionality for Azure

	- ### Datacenter Execution
		- Microsoft experienced a **year-long datacenter pause** (SemiAnalysis "Datacenter Freeze" coverage), significantly reducing its 2027 capacity forecast
		- Slow execution on large-scale AI clusters — Wisconsin project cited as the opposite of AWS's Indiana/Mississippi build
		- To close the capacity gap, Microsoft is contracting significant amounts of capacity from **neoclouds** — more expensive and margin dilutive

- ## Google Cloud (GCP): Margins Are an Illusion

	- ### Revenue and Reported Margins
		- GCP revenue growth: **`>60% YoY`** in latest quarter — strong
		- GCP margins at a record high — but SemiAnalysis argues this is **"EBTIT" (Earnings Before Training, Interest and Taxes)**
		- AI as % of total GCP revenue: `36%` in 1Q26

	- ### The DeepMind Training Cost Distortion
		- Alphabet classifies Gemini/DeepMind training expenses under **"Alphabet-Level Activities"**, not GCP
		- Alphabet-Level Activities: **`$5.4B` in 1Q26**, up from **`$3.0B` in 1Q25** — a `+$2.4B` YoY increase (`+80%`)
		- All Gemini API revenue flows into GCP at above-average margins while `$10B+` run-rate costs are bucketed elsewhere — making GCP margins structurally overstated
		- Potential additional distortion: one-off royalty payments from TPU sales to Anthropic (via Broadcom, with Google acting as IP vendor) may have boosted margins temporarily

	- ### Supply Constraints and Strategic Overextension
		- Google is attempting to compete simultaneously against: **AWS (Cloud), Nvidia (hardware), Anthropic/OpenAI (models), Meta (ads), Tesla (autonomy)**
		- Internal AI use takes priority over cloud customers — Gemini Enterprise Agent Platform (previously Vertex) is seeing **significantly lower capacity additions than Bedrock**
		- Capacity is insufficient to serve all demand; limited room for the Cloud business to grow at the same pace as AWS
		- GCP strategy appears to be a **platform to upsell additional services** rather than a pure token distribution play — Meta example: large GPU deal → Gemini adoption → massive TPU hardware deal

- ## Oracle and Neoclouds: Not in the Race on TaaS

	- Both Oracle and CoreWeave disappointed the market with **lower-than-expected profits** from their cloud arms
	- TaaS (Token-as-a-Service) businesses: practically **`$0` ARR** for neoclouds and Oracle vs **`$10B+` ARR** for AWS, Azure, and GCP
	- Fundamental limitation: no access to frontier model IP (Claude, OpenAI, Gemini). The distribution moat requires CSP-Lab partnerships that Oracle and neoclouds have not secured.
	- Margin structure is limited to **wholesale GPU rental** — the lowest-margin layer of the AI stack

- ## Key Data Points Table

	| Metric | Value | Source / Period |
	|---|---|---|
	| AWS EBIT margin change | `+213bp` Q/Q | 1Q26 |
	| AI as % of AWS revenue | `2%` → `10%` | 1Q24 → 1Q26 |
	| Bedrock as % of AWS AI revenue | `9%` → `37%` → `53%E` | 1Q25 → 1Q26 → 2Q26E |
	| Bedrock revenue growth | `+60% Q/Q`, then `+170% Q/Q` | 4Q25, 1Q26 |
	| Bedrock run rate | `$5.5B` | 1Q26 |
	| Anthropic share of Bedrock volume | `80–90%+` | 1Q26 |
	| Bedrock gross profit contribution | `30%` of AWS GP step-up Y/Y | 1Q26 |
	| Bedrock as % of AWS total revenue | `4%` | 1Q26 |
	| Bedrock EBIT margin | `~55%` | 1Q26 at $26M Anthropic ARR/MW |
	| Anthropic ARR/MW on Bedrock | `$26M` → `$42M` | 1Q26 → 2Q26E |
	| Trainium share of Bedrock usage | `>50%` | Matt Garman, Nov 2025 |
	| Anthropic net new ARR | `$21B` in the quarter | 1Q26 |
	| Anthropic total ARR | `$30B` | 1Q26 |
	| Anthropic API revenue growth | `~13x` Y/Y | 1Q26 |
	| Anthropic inference gross margins | `-94%` → `38%` → mid-60s | 2024 → 2025 → 1Q26 |
	| Anthropic OI profitability (adj. SBC) | Expected positive | 2Q26, per WSJ 5/20/26 |
	| Anthropic ARR potential | `>$100B` by year-end | SemiAnalysis estimate |
	| AI as % of Azure revenue | `27%` | 1Q26 |
	| AI as % of GCP revenue | `36%` | 1Q26 |
	| Azure AI mix (IaaS vs TaaS) | `>80%` IaaS | 1Q26 |
	| OpenAI backlog vs Azure annual revenue | `2.5x` total Azure annual revenue | 1Q26 |
	| GCP Alphabet-Level AI R&D costs | `$5.4B` (up from `$3.0B`) | 1Q26 (vs 1Q25) |
	| AWS Indiana + Mississippi build | `~2 GW` | SemiAnalysis Datacenter Model |
	| Hyperscaler TaaS ARR (AWS/Azure/GCP) | `>$10B` each | 1Q26 |
	| Neocloud / Oracle TaaS ARR | `~$0` | 1Q26 |

- ## Investment Implications

	- **AWS (Amazon) — most differentiated**: Bedrock's TaaS model + Anthropic deal structure + Trainium vertical integration + Graviton + capacity leadership creates a compounding margin advantage. The trend is up in both revenue mix and profitability. Bedrock is 4% of AWS revenue but 30% of gross profit step-up — this leverage will widen as mix shifts to 53% TaaS.
	- **Anthropic**: Margin inflection (from -94% to mid-60s gross margins in two years) combined with $30B ARR and $21B net new ARR in a single quarter is extraordinary. Enterprise API and Claude Code are the growth engines. Potential $100B+ ARR by year-end makes the Bedrock revenue share deal increasingly valuable to AWS.
	- **Google (Alphabet)**: GCP revenue growth is real but margins are distorted. True margin performance requires adding back DeepMind training costs bucketed at Alphabet level. Supply allocation tension (cloud vs. internal AI vs. hardware) is a structural constraint.
	- **Microsoft (Azure)**: IaaS-heavy mix, OpenAI dependency consuming 2.5x Azure's annual revenue in backlog, datacenter pause, and slow cluster execution are headwinds. CoPilot has not offset the margin mix deterioration from heavy IaaS concentration.
	- **Longer-term**: AI Labs will increasingly verticalize their own inference stack, pressuring pure IaaS margins across all CSPs. The winners will be those with TaaS distribution agreements, custom silicon, and owned capacity — which points to AWS maintaining its margin lead.

- ## Open Questions
	- Will Microsoft close the TaaS gap now that it has gained Claude access on Foundry? What is the revenue ramp trajectory?
	- How much of Google Cloud's TPU hardware revenue to third parties (e.g. Anthropic via Broadcom) is one-off vs. recurring?
	- Can Azure's capacity, currently dominated by OpenAI commitments, be rebalanced toward TaaS? Or is the OpenAI backlog lock-in structural through ~2030?
	- What is Anthropic's pricing trajectory as inference gross margins approach the 70s? Does higher margin lead to price cuts (competitive) or retention of pricing power?
