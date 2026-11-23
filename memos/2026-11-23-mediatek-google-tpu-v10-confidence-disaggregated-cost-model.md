tags:: [[$2454.TW]], [[MediaTek]], [[$GOOGL]], [[TPU]], [[ASIC]], [[custom-silicon]], [[$AVGO]], [[HBM]], [[supply-chain]], [[Morgan-Stanley]], [[Bernstein]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-23
file-updated-at:: 2026-11-23

- ## MediaTek and Google TPU v10: deeper role, and a cheaper disaggregated model for Google
	- **Source**: user-provided text summarizing **Morgan Stanley** and **Bernstein** views on MediaTek (November 2026). The underlying reports weren't supplied.
	- **Thesis**: MediaTek has become a durable custom-silicon partner for Google.
		- **More generations**: after v8 and v9, it is "highly confident" of winning **TPU v10** (Morgan Stanley), and its revenue per chip should rise as its role in Google's AI data centers expands.
		- **Lower cost for Google**: Google is moving to a **disaggregated** TPU model in which it reportedly buys HBM directly. Bernstein estimates that cuts per-chip cost by **roughly half** compared with Broadcom's turnkey model.
		- **Fit**: MediaTek's cost-efficiency DNA suits Google's push to control design, supply chain and economics.
		- **Platform for more customers**: the Google franchise is a base for other accounts. MediaTek has already confirmed a **second AI ASIC customer outside China**.

- ## The data points
	- | Item | View | Source |
	  |---|---|---|
	  | TPU v10 | MediaTek is "highly confident" of winning the v10 project, after its work on v8 and v9 | Morgan Stanley |
	  | Revenue per chip | Expected to **rise** as MediaTek's role in Google's AI data centers expands | Morgan Stanley |
	  | Second customer | A second AI ASIC customer outside China is **confirmed** | MediaTek |
	  | Cost of the disaggregated model | Google's more disaggregated TPU model, reportedly including **direct HBM procurement**, could cut per-chip cost by **roughly half** vs. Broadcom's turnkey model | Bernstein |
	  | Strategy | Google is taking more control of its custom silicon design, supply chain and economics; MediaTek's cost efficiency fits that | Source text |

- ## How it fits earlier repo data
	- **v10 is consistent with Kuo**: Ming-Chi Kuo's November 15 note already put MediaTek as the design-service winner for **v10 (Quillfish, 2029)** and **v11 (Icefish, 2030)**, and as **sole designer from v9 onward** ([[2026-11-15-google-tpu-openai-anthropic-orders-2029-mediatek-quillfish]]). Morgan Stanley's "highly confident" is a softer version of the same claim.
	- **The expert call is more cautious**: an expert said "diversification is always Google's strategy," that Broadcom isn't being displaced, and that AMD may contribute CPU IP and packaging to v10 ([[2026-10-26-expert-call-nvidia-hyperscaler-concentration-external-tpu-amd-v10]]).
	- **Second customer**: MediaTek confirmed on its Q3 2026 call (October 30) that a non-China second ASIC customer contributes revenue from 2028. Reports had pointed to **Meta** ([[2026-07-01-mediatek-meta-asic-second-customer-after-google-tpu]], [[2026-11-02-mediatek-emib-yield-tsmc-backstop-second-asic-customer]], [[MediaTek-2026-Q3]]).
	- **How MediaTek works with Google**: under the **semi-customer-owned-tooling ("semi-COT")** model, Google owns more of the design and supply relationships and MediaTek designs specific blocks ([[2026-05-01-mediatek-google-tpu-codesign-semi-cot-model]]). Bernstein's "disaggregated" model is the same direction taken further.
	- **Google's cost edge in TPUs**: MBI puts Google's chip and networking cost at about **\$21B per GW**, vs. about **\$40B of Nvidia content** per Vera Rubin GW ([[2026-11-18-mbi-google-tpu-gigawatt-cost-vs-nvidia]]). Halving per-chip cost vs. Broadcom's turnkey model would widen that edge further.

- ## What it means for MediaTek's economics (memo's reading)
	- **A tension in "revenue per chip rises"**:
		- If Google buys HBM directly, the HBM pass-through, often the largest bill-of-materials item, drops out of the chip vendor's revenue. That lowers reported revenue per chip but raises margin percentage.
		- Morgan Stanley's rising revenue per chip must therefore come from MediaTek's **broader design scope**, such as more IP blocks, SerDes and I/O, packaging work, and more of the TPU family, not from pass-through content.
		- Kuo's note said MediaTek and Broadcom both procure key components. Who buys what in each generation remains an open question.
	- **The trade-off with Broadcom**: Bernstein's halving of cost is a cost for Google, not a revenue figure for MediaTek. The savings come partly from removing the turnkey vendor's margin on procured parts and integration. So the disaggregated model makes **Google's** TPU cheaper and gives MediaTek a smaller-ticket but sticky role, while Broadcom's turnkey economics come under pressure. That is consistent with [[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]].
	- **Execution risks**: from v9, the second-generation ASIC depends on Intel EMIB-T packaging yields, with TSMC CoWoS as a backstop. Reliance on Google is high until the second customer ramps in 2028 ([[MediaTek-MTK-thesis]]).
