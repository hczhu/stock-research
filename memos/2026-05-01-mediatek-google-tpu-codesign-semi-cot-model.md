tags:: [[$2454.TW]], [[$GOOGL]], [[$TSM]], [[ASIC]], [[TPU]], [[AI infrastructure]], [[semiconductor]], [[advanced-node]], [[foundry]]

- ## MediaTek–Google TPU Co-Design and the Semi-COT Wafer Model
	- **Source**: Channel/industry notes, May 2026
	- **Thesis**: MediaTek's earnings exposure to the Google TPU program is structured around the parts it designs, not around who places the main-compute-die wafer orders. Its scale at TSMC makes it a natural shock absorber for wafer allocation regardless of how TPU orders move.
- ## Co-Design Structure
	- Google and MediaTek have run a **semi-COT** (semi customer-owned-tooling) model since **day one — the 8th-gen TPU (8t)**
	- **Where MediaTek's mark-up sits**: mostly on the **parts MediaTek designs itself** (its own IP/blocks), not on the main compute die pass-through
	- **Implication for earnings**: whether **Google places the wafer orders for the main compute die directly** is **not a key swing factor** for MediaTek's earnings trajectory — the value MediaTek captures is in its design content, not in being the wafer-order intermediary
- ## The "Humufish" Semi-COT Variant — TSMC's Preference
	- On the **Humufish** semi-COT model, **TSMC prefers MediaTek to place the wafer orders for the main compute die**
	- Two reasons:
		- **Close working relationship** between MediaTek and TSMC
		- **Scale**: MediaTek is **TSMC's third-largest advanced-node customer in 2025**
	- **Buffer role**: if TPU orders shift, MediaTek's scale makes it a **natural buffer for TSMC to rebalance its wafer allocation mix** — MediaTek can absorb or release advanced-node capacity to smooth TSMC's allocation
- ## Investment Implications
	- **Earnings quality**: MediaTek's TPU economics are insulated from the question of who owns the main-compute-die wafer orders — the design-content mark-up is the durable margin driver, reducing a perceived risk to the thesis
	- **Strategic position at TSMC**: Being the #3 advanced-node customer gives MediaTek allocation leverage and makes it structurally useful to TSMC as a capacity buffer — a moat-adjacent advantage beyond any single ASIC program
	- **Order-shift resilience**: Even if Google reroutes wafer orders, MediaTek's role and margin capture are not mechanically tied to that flow — and its buffer status means TSMC has incentive to keep MediaTek's volumes full
	- See [[MediaTek-MTK-thesis]] thesis and [[2026-03-28-mediatek-google-orders-and-broadcom-share-shift-2026-02]] for the broader Google-orders and ASIC-share context; [[2026-05-31-mediatek-terafab-strategic-asic-partner]] for the TeraFab angle
- ## FundaAI Update — June 2026
	- **Source**: FundaAI-T channel checks, June 2026. Also incorporates screenshot commentary on AVGO v9 status and 2027 shipment forecast.
	- ### Humufish + Triggerfish: Volume, ASP, and Timeline
		- | Metric | Humufish | Triggerfish | Combined |
		  |---|---|---|---|
		  | ASP (est.) | \$15k | \$20k | — |
		  | Lifecycle volume share | ~half | ~half | 6–7M units total |
		  | Mass production start | Q3 2027 | Q4 2027 | — |
		  | Ramp | 2028 | 2028 | — |
		- Lifecycle volume for Humufish + Triggerfish raised to **6–7M units** (up from prior 5M estimate). Triggerfish's share could approach **nearly half** of total lifecycle volume.
		- **Substrate is the primary bottleneck**: Google is actively pushing substrate manufacturers to expand capacity to support the ramp.
		- Implied revenue at midpoint (6.5M units, blended \$17.5k ASP): **~\$114B total lifecycle TAM** for this program across both chips.
	- ### Triggerfish Architecture: New MediaTek CPU Die
		- Beyond packing more **SRAM into the compute die**, Triggerfish adds a **new CPU developed by MediaTek** to handle workload switching between training and inference.
		- This CPU is not a standalone chip — it is a CPU die/compute die integrated within the TPU package.
		- Architecturally, this positions Triggerfish as a more versatile accelerator capable of flexibly switching between training and inference workloads, versus prior-generation TPUs that were more single-mode.
		- This increases MediaTek's design content per unit on Triggerfish relative to Humufish — the new CPU die is MediaTek IP, which should carry higher margin than pass-through wafer volume.
	- ### Pumafish: Cancellation Stands
		- No supply chain evidence of a Pumafish restart. FundaAI maintains the cancellation view. This volume is not in the 6–7M forecast above.
	- ### AVGO v9 Training Chip Status
		- Broadcom's status on the TPU v9 **training chip** contract remains **pending** as of this update — distinct from the inference/SerDes displacement by MediaTek covered in [[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]].
	- ### 2027 Total TPU Shipment Forecast
		- Prior estimate (end of April): 10M+ units.
		- Revised estimate (June 2026): **10–11M units** — modestly higher, described as "more reasonable."