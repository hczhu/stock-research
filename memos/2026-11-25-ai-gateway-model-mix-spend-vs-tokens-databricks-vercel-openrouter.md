tags:: [[Anthropic]], [[OpenAI]], [[$GOOGL]], [[Gemini]], [[xAI]], [[open-weights]], [[Databricks]], [[Vercel]], [[OpenRouter]], [[tokenomics]], [[pricing]], [[market-share]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-25
file-updated-at:: 2026-11-25

- ## Frontier models still take most of the spend, while open-weight models take most of the tokens
	- **Source**: chart "AI gateway model mix: Databricks vs Vercel vs OpenRouter" (user-provided image; author not shown). Weekly data (Monday to Sunday), through **November 15, 2026** for Databricks and Vercel and **November 22** for OpenRouter.
		- **Databricks**: AI Index. Spend is at **list price including the cache-read rate**, not Databricks billing.
		- **Vercel**: AI Gateway leaderboard, text models, weekly average of daily share.
		- **OpenRouter**: tokens and list-price-equivalent spend, read from its charts.
		- **Reading the chart**: the latest values are printed on it. Intermediate peaks and troughs are read off the chart and marked ≈.
	- **Thesis**: at all three gateways, **open-weight and other models carry most of the tokens** (73% on Vercel, 89% on OpenRouter), but **proprietary frontier models still collect most or about half of the spend**. Among proprietary models, **Anthropic leads spend** at all three gateways (65–74%) and holds a larger share of spend than of tokens, so it earns more per token than OpenAI. OpenAI's spend share rose from August, peaked in September and October, and has since eased back toward Anthropic's advantage.

- ## Anthropic and OpenAI shares of proprietary spend and tokens
	- **Denominator**: Anthropic + OpenAI + Gemini/Grok. "Proprietary" means Claude, GPT, Gemini and Grok at Databricks; Anthropic, OpenAI, Google and xAI at Vercel; and OpenAI, Anthropic and Google at OpenRouter.
	- | Metric | Gateway | Start (late Jul to Aug) | Latest | Path in between |
	  |---|---|---|---|---|
	  | **Anthropic, share of proprietary spend** | Databricks | 85.5% | **73.9%** | Steady decline, flat at about 70% since October |
	  | | Vercel | 72.3% | **65.4%** | Fell to ≈50–52% (late September and early November), then rebounded |
	  | | OpenRouter | 61.9% | **67.4%** | Trough ≈38% in mid-September, back above 65% since mid-October |
	  | **OpenAI, share of proprietary spend** | Databricks | 10.1% | **21.9%** | Peak ≈30% in late October |
	  | | Vercel | 16.3% | **19.7%** | Peak ≈33% in late September |
	  | | OpenRouter | 26.7% | **16.1%** | Spike to ≈55% in mid-September |
	  | **Gemini (+Grok), latest week, spend** | Databricks / Vercel / OpenRouter | | **4.3% / 14.9% / 16.5%** (OpenRouter is Gemini only) | |
	  | **Anthropic, share of proprietary tokens** | Databricks | 80.0% | **65.6%** | Range ≈57–69% |
	  | | Vercel | 50.7% | **48.1%** | Trough ≈31% in early October |
	  | | OpenRouter | 24.8% | **38.8%** | Trough ≈13% in mid-September |
	  | **OpenAI, share of proprietary tokens** | Databricks | 16.4% | **30.5%** | Peak ≈38% in late September |
	  | | Vercel | 33.7% | **39.2%** | |
	  | | OpenRouter | 45.0% | **42.9%** | Peak ≈68% in mid-September |
	  | **Gemini (+Grok), latest week, tokens** | Databricks / Vercel / OpenRouter | | **3.9% / 12.7% / 18.3%** (OpenRouter is Gemini only) | |

- ## Open-weight and other models, share of all traffic
	- | Metric | Gateway | Start | Latest | Notes |
	  |---|---|---|---|---|
	  | **Share of all spend** | Vercel | 12.4% | **31.0%** | Peak ≈37% in mid-October. More than doubled since late July |
	  | | OpenRouter (incl. Grok) | 46.0% | **49.4%** | Range ≈45–55% |
	  | | Databricks | — | — | Databricks doesn't publish this split |
	  | **Share of all tokens** | Vercel | 47.0% | **73.4%** | Peak ≈80% in late September, dip ≈61% in early October |
	  | | OpenRouter (incl. Grok) | 80.2% | **89.1%** | Highest of the three |
	  | | Databricks (Databricks-hosted models only; not comparable) | 7.3% | **32.9%** | More than 4× since late July |

- ## What the gaps between spend and tokens imply (memo calculations, latest week)
	- **Spend share ÷ token share among proprietary models**: above 1 means more spend per token than the proprietary average.
		- | Gateway | Anthropic | OpenAI |
		  |---|---|---|
		  | Databricks | 73.9 ÷ 65.6 = **1.13** | 21.9 ÷ 30.5 = **0.72** |
		  | Vercel | 65.4 ÷ 48.1 = **1.36** | 19.7 ÷ 39.2 = **0.50** |
		  | OpenRouter | 67.4 ÷ 38.8 = **1.74** | 16.1 ÷ 42.9 = **0.38** |
		- Anthropic earns more per token than OpenAI at every gateway, from about 1.6× to about 4.6×. That reflects higher list prices, more use of premium models such as Opus, or both.
	- **Proprietary vs. open-weight price per token**:
		- On Vercel, proprietary models take 69.0% of spend with 26.6% of tokens, and open-weight models take 31.0% with 73.4%. Proprietary spend per token is about **6.1×** open-weight's.
		- On OpenRouter (50.6% / 10.9% vs. 49.4% / 89.1%) it is about **8.4×**.

- ## How it fits earlier repo data
	- **Vercel's open-weight share**: the KV-cache memo cited Vercel AI Gateway data with open-weight models rising from about **11% of tokens in April 2026 to about 36% in July**, and from about **3% to 9% of spend** ([[2026-11-20-kv-cache-reads-llm-inference-gross-margin]]). This chart has Vercel's "open-weight & other" at **47% of tokens and 12.4% of spend** in late July. The gap is probably definitional: "other" here also includes non-frontier proprietary models outside Anthropic, OpenAI, Google and xAI. On both measures the trend is sharply upward.
	- **Commoditization at the token level**: consistent with [[2026-07-16-kimi-k3-open-weight-frontier-commoditization]] and [[2026-07-13-benedict-evans-token-pricing-commodity-infrastructure]].
	- **Anthropic's revenue concentration in coding and premium use**: [[2026-10-26-anthropic-s1-financials-compute-economics]].

- ## Memo's reading
	- **Tokens commoditize while spend stays concentrated**: high-volume, low-value tokens (background tasks, classification, cheap agents) move to open-weight models. The work customers pay most for stays with frontier models. That supports frontier labs' revenue and gross margins even as token share erodes.
	- **Anthropic holds the premium position**: Anthropic has the largest share of proprietary spend at all three gateways, and the most spend per token. The September–October dip shows that share can move quickly when competitors launch, but it recovered at OpenRouter and Vercel within weeks.
	- **Gemini is small at the gateways**: Gemini's 4–17% here understates Google's position, because most Gemini usage runs through Google's own channels (Vertex, AI Studio, consumer apps). It also predates the late-November Gemini 4 Neon reception ([[2026-11-23-google-gemini-neon-vs-opus-rauch-personal-eval]]).
	- **Biases in the gateways**: OpenRouter skews toward hobbyist, price-sensitive and Chinese-model users. Databricks skews enterprise. Vercel sits between them. None is representative of direct API spend at the labs.
