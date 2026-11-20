tags:: [[$GOOGL]], [[TPU]], [[ASIC]], [[$AVGO]], [[$2454.TW]], [[MediaTek]], [[custom-silicon]], [[supply-chain]], [[power]], [[Ming-Chi-Kuo]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-20
file-updated-at:: 2026-11-20

- ## Google cuts 2027 TPU 8i (Broadcom) by about 1M units and shifts toward 8t (MediaTek)
	- **Source**: Ming-Chi Kuo (@mingchikuo), X post, November 20, 2026, citing his latest industry survey (user-provided screenshot).
	- **Thesis**: Google is cutting 2027 shipments of the **Broadcom-designed, inference-focused TPU 8i** by about **1M units**, roughly 20% of the series and mostly the higher-priced **8i Max ("Whalefish")**. It plans to raise 2027 shipments of the **MediaTek-designed, training-focused TPU 8t**, though details aren't final. Kuo ties the shift to Google's stated priority that **frontier model development gets first call on compute**, amid a tight supply chain and data-center power constraints.
	- Prior plan from Kuo: [[2026-11-15-google-tpu-openai-anthropic-orders-2029-mediatek-quillfish]]. 8t is Zebrafish (MediaTek) and 8i is Sunfish (Broadcom) ([[2026-06-03-hbm-supply-demand-model-morgan-stanley]]). Google split TPUv8 into a training-focused 8t and an inference-focused 8i ([[2026-09-07-semianalysis-tpuv7-inference-externalization]]).

- ## The change
	- | Item | Detail |
	  |---|---|
	  | TPU 8i (Broadcom) | 2027 shipments **cut by about 1M units**, mostly the higher-priced **8i Max / Whalefish** |
	  | Size of the cut | About **20%** of 2027 8i-series shipments, implying a 2027 8i plan of about **5M units before** the cut and about **4M after** (memo calculation) |
	  | TPU 8t (MediaTek) | 2027 shipments planned to **increase**. Details not final |
	  | Kuo's explanation | Frontier model development gets first call on compute. With a tight supply chain and limited data-center power, Google is shifting the mix toward the training chip |

- ## Reconciling with Kuo's November 15 plan (memo calculation)
	- **Before this cut**: Kuo's November 15 note put total 2027 TPU shipments at **8–9M**, with MediaTek supplying **45–50%** (about 3.6–4.5M units, if share is measured in units). An 8i plan of about 5M leaves about 3–4M for 8t and other parts, roughly in line with MediaTek's share given rounding.
	- **After this cut**: 8i falls to about 4M.
		- **If 8t is not raised**: total 2027 shipments fall to about **7–8M**.
		- **If 8t is raised by a similar amount**: total stays near 8–9M.
		- **Either way**: MediaTek's share of 2027 TPU units rises, either because Broadcom's volume shrinks or because MediaTek's grows. Kuo does not give the size of the 8t increase.
	- **Revenue impact on Broadcom**: the cut is concentrated in the higher-priced 8i Max, so Broadcom loses more than 20% of 2027 8i revenue. Kuo's earlier note said Broadcom earns a higher margin on 8i.

- ## Context
	- **Who buys 8t and 8i later on**: Kuo attributes 2028–29 v8 demand mainly to outside customers, with OpenAI buying about 12M 8t and Anthropic about 14M 8i. This post concerns **2027**, when Google's own compute priorities still decide the mix.
	- **8i is already shipping**: Epoch AI estimates TPU v8i was about 131K H100e of Google's 1.61M H100e shipped in Q2 2026 ([[2026-11-20-epoch-ai-chip-sales-nvidia-vs-google-tpu-2026q2]]).
	- **MediaTek's packaging risk**: MediaTek is exposed to Intel EMIB-T packaging capacity for later TPU generations ([[2026-11-02-mediatek-emib-yield-tsmc-backstop-second-asic-customer]], [[MediaTek-MTK-thesis]]).
