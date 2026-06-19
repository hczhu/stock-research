- tags:: [[$TSM]], [[$INTC]], [[$NVDA]], [[packaging]], [[CoWoS]], [[CoPoS]], [[EMIB]], [[AI-compute]], [[semiconductor]]

- ## TSMC Accelerating CoPoS Packaging to Counter Intel EMIB-T
	- **Source**: UBS research note, via user (2026-04-09)
	- **Headline**: TSMC is accelerating CoPoS (chip on panel on substrate) development targeting mass production by 2028E to compete with Intel's EMIB-T for ultra-large AI packages

- ## Key Data Points

	| Item | Detail |
	|---|---|
	| TSMC technology | CoPoS (Chip on Panel on Substrate) |
	| TSMC CoPoS mass production target | 2028E |
	| Intel technology | EMIB-T (Embedded Multi-die Interconnect Bridge — T variant) |
	| Intel EMIB-T mass production target | H2 2027 or 2028 |
	| Target application | Ultra-large AI packages |
	| Potential TSMC customer | Nvidia Feynman platform |
	| Nvidia Feynman release | H2 2028 |
	| Feynman package configuration | 4-die package |

- ## Context
	- Current TSMC advanced packaging for AI accelerators is CoWoS (Chip on Wafer on Substrate) — CoPoS is the next-generation successor using panel-level substrates instead of wafers, enabling significantly larger package sizes
	- Panel-level packaging allows more dies per substrate run vs wafer-level, improving yield economics and enabling larger multi-die configurations
	- Intel's EMIB-T is the competitive pressure: a bridge-based interconnect that can stitch together very large multi-chiplet packages — Intel's main credible remaining advantage in advanced packaging
	- TSMC accelerating CoPoS is a defensive and offensive move: defend Nvidia (and other hyperscaler ASIC) business from Intel poaching on packaging differentiation
	- Nvidia Feynman (H2 2028) would be the first GPU generation to potentially use CoPoS — moving from 2-die (Rubin Ultra) toward a 4-die package would roughly double the compute and memory per logical GPU unit again
	- Timeline is tight: Intel targets H2 2027, TSMC targets 2028 — TSMC is currently trailing on this specific packaging vector, which is unusual

- ## Investment Implications
	- Confirms TSMC's advanced packaging roadmap extends well beyond CoWoS-L — CoPoS is a meaningful new capex and R&D cycle
	- Intel has a narrow window (2027–2028) where EMIB-T could be the preferred packaging for customers who cannot wait for CoPoS
	- Nvidia Feynman on CoPoS would sustain the memory and compute scaling trajectory — supportive of continued HBM demand growth into 2028+
	- TSMC's panel-level packaging investment requires new cleanroom infrastructure — consistent with reports of Taiwan companies investing in next-gen fab facilities

- ## TSMC Foundry & Advanced-Packaging Moat — Research Note (2026-06-18)
	- **Source**: Research note (Chinese-language; translated); argues TSMC's lead is structural and Intel's packaging entry is not a major threat
	- **Process technology lead**: TSMC leads competitors by ~2 years on key process technology metrics — a lead the note characterizes as structural, not cyclical.
	- **DTCO lock-in**: DTCO (Design-Technology Co-Optimization) and co-design practices bind large fabless customers to TSMC's process at the design stage, making it progressively harder to migrate high-volume products to competing foundries. The earlier in the design cycle a customer co-optimizes with TSMC, the more deeply embedded the dependency.
	- **Advanced packaging as a wafer-pull lever, not a standalone P&L**: TSMC views advanced packaging (CoWoS, CoPoS, etc.) primarily as a complementary capability that drives wafer sales — not as an independent revenue or profit center. This framing implies TSMC can price packaging aggressively to defend foundry share without needing the packaging segment to justify its own margin.
	- **EMIB market share**: TSMC expected to capture ~10% of the EMIB market in 2028/2029 — framed as a modest but deliberate incursion into Intel's packaging differentiation, consistent with CoPoS mass-production targeting 2028.
	- **Intel packaging threat assessment**: Intel's entry into advanced packaging is **not considered a major threat** to TSMC. Rationale: TSMC's packaging is a defensive moat around wafer revenue, so it can cross-subsidize; Intel needs packaging to be independently profitable to justify the investment, putting it at a structural pricing disadvantage.
