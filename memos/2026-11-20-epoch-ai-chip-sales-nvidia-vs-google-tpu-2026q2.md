tags:: [[$NVDA]], [[$GOOGL]], [[$AMZN]], [[$AMD]], [[Huawei]], [[Cambricon]], [[GPU]], [[TPU]], [[Trainium]], [[custom-silicon]], [[Epoch-AI]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-20
file-updated-at:: 2026-11-20

- ## AI chip sales in 2026 Q2: Nvidia vs. Google TPUs (Epoch AI)
	- **Source**: [Epoch AI, "AI chip sales" data hub](https://epoch.ai/data/ai-chip-sales?view=graph&tab=power&cumulative=false&utm_source=substack&utm_medium=email&viewType=designer). Three user-provided screenshots show quarterly sales by designer and by chip, in **compute capacity (H100 equivalents)** and **chip power (GW)**. Q2 2026 figures come from the charts' tooltips and include Epoch's 90% confidence intervals. Earlier quarters are read off the charts and are approximate (≈). These are Epoch estimates, not company disclosures.
	- **Thesis**: Nvidia sold about **62% of AI compute** shipped in Q2 2026, and Google's TPUs about **25%**. Measured in power instead, Nvidia's share rises to about **67%** and Google's falls to about **19%**. By Epoch's numbers, TPUs deliver about **43% more H100-equivalent compute per watt** than Nvidia's mix (memo calculation). Total quarterly compute shipped grew roughly **8× in nine quarters**, from about 0.8M H100e in Q1 2024 to **6.33M** in Q2 2026.

- ## 2026 Q2 by chip designer
	- | Designer | Compute (H100e) | 90% CI | Share of compute | Chip power (GW) | 90% CI | Share of power | H100e per GW (memo calculation) |
	  |---|---|---|---|---|---|---|---|
	  | **Nvidia** | **3.95M** | 3.35–4.64M | **62.4%** | **2.15** | 1.82–2.52 | **66.8%** | 1.84M |
	  | **Google** | **1.61M** | 1.12–2.12M | **25.4%** | **0.61** | 0.45–0.78 | **18.9%** | **2.64M** |
	  | Amazon | 288K | 143–634K | 4.5% | 0.19 | 0.10–0.40 | 5.9% | 1.52M |
	  | AMD | 261K | 190–342K | 4.1% | 0.14 | 0.10–0.19 | 4.3% | 1.86M |
	  | Huawei | 205K | 99–330K | 3.2% | 0.12 | 0.039–0.22 | 3.7% | 1.71M |
	  | Cambricon | 12.4K | 11.1–13.8K | 0.2% | 0.0096 | 0.0085–0.011 | 0.3% | 1.29M |
	  | **Total** | **6.33M** | | 100% | **3.22** | | 100% | **1.97M** |
	- **Combined custom silicon**: Google, Amazon, Huawei and Cambricon together sold about **2.12M H100e (33%)** of compute. AMD is the only merchant GPU vendor besides Nvidia, at about 4%.
	- **Confidence**: Google's estimate is less certain than Nvidia's. Its 90% range spans about ±31%, vs. about ±16% for Nvidia. Amazon's range is the widest, at 143–634K.

- ## 2026 Q2 by chip
	- | Designer | Chip | Compute (H100e) | 90% CI |
	  |---|---|---|---|
	  | Nvidia | **B300** | **3.37M** | 2.86–3.96M |
	  | Nvidia | B200 | 564K | 481–661K |
	  | Nvidia | H100/H200 | 19.4K | 16.2–22.8K |
	  | Google | **TPU v7** | **1.44M** | 1.08–1.81M |
	  | Google | TPU v8i | 131K | 37.5–235K |
	  | Google | TPU v6e | 38.8K | — |
	  | Amazon | Trainium2 | 167K | 105–259K |
	  | Amazon | Trainium3 | 121K | 38.2–375K |
	  | AMD | MI355X | 165K | 136–199K |
	  | AMD | MI350X | 54.4K | 29.5–78.8K |
	  | AMD | MI300X | 22.3K | 14–33.1K |
	  | AMD | Other AMD | 18.7K | 11.2–31.1K |
	  | Huawei | Ascend 910C | 135K | 44–245K |
	  | Huawei | Ascend 950PR | 69.7K | 55–85K |
	  | Cambricon | Siyuan 590 | 12.4K | 11.1–13.8K |
	- **Two chips dominate**: **B300** (53% of all compute) and **TPU v7** (23%) together make up about **76%** of Q2 2026 AI compute sold (memo calculation).
	- **Product transitions**: Nvidia's mix is almost entirely Blackwell (B300 85% of Nvidia compute). Hopper is down to 19.4K H100e. Google's next-generation TPU v8i has started shipping, at about 8% of Google's compute.

- ## Nvidia GPUs vs. Google TPUs
	- | Metric (2026 Q2) | Nvidia | Google TPU | Ratio, Nvidia ÷ Google |
	  |---|---|---|---|
	  | Compute sold (H100e) | 3.95M | 1.61M | 2.5× |
	  | Chip power sold (GW) | 2.15 | 0.61 | 3.5× |
	  | Share of compute | 62.4% | 25.4% | |
	  | Share of power | 66.8% | 18.9% | |
	  | H100e per GW (memo calculation) | 1.84M | 2.64M | Google about 43% higher |
	  | Lead chip | B300, 3.37M H100e | TPU v7, 1.44M H100e | 2.3× |
	- **More compute per watt for TPUs**: Google's share of compute (25%) is well above its share of power (19%), so each gigawatt of TPUs carries more H100-equivalent compute than a gigawatt of Nvidia chips. **Caveat**: H100e is Epoch's performance-normalized unit and chip power is chip-level, so this is not a system-level or real-workload efficiency comparison.
	- **Over time**: Google's TPU slice has grown from roughly 0.15M H100e per quarter in early 2024 to 1.61M in Q2 2026. It has roughly 25% of quarterly compute, while Nvidia remains the large majority throughout. Mid-period quarters are partly hidden by the tooltips, so the memo gives no exact series.

- ## Total AI chip sales by quarter (approximate, read from the charts)
	- | Quarter | Compute sold (H100e) | Chip power sold (GW) |
	  |---|---|---|
	  | 2024 Q1 | ≈0.8M | ≈0.7 |
	  | 2024 Q2 | ≈1.0M | ≈0.87 |
	  | 2024 Q3 | ≈1.3M | ≈1.07 |
	  | 2024 Q4 | ≈1.9M | ≈1.35 |
	  | 2025 Q1 | ≈2.55M | ≈1.55 |
	  | 2025 Q2 | ≈2.9M | ≈1.62 |
	  | 2026 Q2 | **6.33M** | **3.22** |
	- 2025 Q3 through 2026 Q1 are partly hidden behind the tooltips.
	- **Compute is growing faster than power**: from Q1 2024 to Q2 2026, compute grew about 8× and power about 4.6× (memo calculation). Compute per watt shipped therefore improved about 1.7× as Blackwell and newer TPUs replaced older chips.

- ## Related in the repo
	- **Installed base**: Epoch's earlier cumulative chip-ownership chart put Google at about 5.0M H100e at the end of 2025, about 3.8M of it TPUs, the largest of any company ([[Google-GOOGL-thesis]] appendix).
	- **TPU economics**: MBI estimates a self-built TPU gigawatt costs Google about \$33B vs. about \$50–60B for an Nvidia build ([[2026-11-18-mbi-google-tpu-gigawatt-cost-vs-nvidia]]). TPU orders from OpenAI and Anthropic run through 2029 ([[2026-11-15-google-tpu-openai-anthropic-orders-2029-mediatek-quillfish]]).
	- **Nvidia's quarter**: Vera Rubin shipments began in August 2026, after this Q2 snapshot ([[NVDA-2026-Q3]]). Huawei's Ascend 950 inference economics are in [[2026-11-18-huawei-ascend-950dt-inference-economics-vs-h200]].
