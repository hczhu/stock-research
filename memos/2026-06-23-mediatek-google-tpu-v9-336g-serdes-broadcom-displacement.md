- tags:: [[$2454.TW]], [[$MTK]], [[Google]], [[TPU]], [[SerDes]], [[AI-ASIC]], [[semiconductor]], [[optical-interconnect]], [[Broadcom]], [[$AVGO]], [[TSMC]]

- **Source**: 工商時報 (Commercial Times), June 23 2026. Reporter: 張珈睜.

- ## MediaTek Wins Google TPU v9 via 336G SerDes; Broadcom Displaced

	- MediaTek secured the primary Google TPU v9 ASIC contract by implementing a **336G SerDes** solution, directly displacing Broadcom which had been the incumbent vendor targeting a **448G SerDes** architecture.

- ## Why Broadcom Lost

	- Broadcom's 448G SerDes approach stalled on three interlocking problems: signal integrity degradation at 448G speeds, elevated power consumption, and thermal dissipation constraints that could not be resolved within Google's timeline.
	- The 448G optical module design appears to require a **2nm process node**, pushing potential volume production out to **2028–2029** — too late for Google's TPU v9 ramp.
	- Google pivoted to the 336G standard as a technically achievable bridge solution, and MediaTek was positioned to execute it.

- ## MediaTek's Winning Edge

	- MediaTek leveraged multi-year accumulated **high-speed interface IP** combined with deep **TSMC advanced-process collaboration experience** to complete the custom design and win primary development status.
	- This is consistent with the pattern established in earlier TPU generations: MediaTek's proximity to TSMC and its Semi-COT model give it execution advantages that pure fabless vendors with less TSMC integration cannot easily replicate.

- ## Revenue Projections

	- | Metric | 2026E | 2027E |
	  |---|---|---|
	  | AI accelerator ASIC revenue | \$2B (revised up) | Tens of billions USD |
	  | Primary customer | Google (TPU v9) | Google + multiple CSPs |

	- The 2027 projection of "several tens of billions" implies a step-change, likely contingent on multiple hyperscaler / CSP programs beyond Google beginning volume production.

- ## Pipeline Beyond Google

	- Multiple cloud service providers have AI ASIC programs in development with MediaTek that are expected to "progressively materialize" — names not disclosed in this article.
	- This confirms the market view that MediaTek is building an ASIC platform business across the hyperscaler tier, not a single-customer relationship.

- ## Competitive Landscape: The Emerging Differentiation Axis

	- The article signals a structural shift in how AI ASIC vendors will compete: the battle is moving from raw compute chip design toward **integrated system capability** — combining high-speed SerDes transmission, optical interconnect co-design, and system-level architecture.
	- Technologies in active development that define the next competitive frontier:
		- **Thin-film lithium niobate (TFLN)** laser technology — high-bandwidth, low-power optical modulation
		- **Micro LED** solutions — optical interconnect for rack-scale communication
		- **VCSEL arrays** — short-distance optical applications
	- Broadcom's difficulty with 448G illustrates that the transition to next-generation optical interconnect is not trivial. Vendors who can co-design SerDes and optical layers with the compute chip will have structural advantages.

- ## Connection to Prior MediaTek Memos

	- This is the latest in a progression: [[2026-03-28-mediatek-google-orders-and-broadcom-share-shift-2026-02]] established that MediaTek was taking Google share from Broadcom. [[2026-05-01-mediatek-google-tpu-codesign-semi-cot-model]] documented the Semi-COT codesign model. This memo confirms the displacement is now concrete on a named generation (TPU v9) with specific technical rationale.
	- The 336G SerDes win validates the thesis that MediaTek's high-speed interface IP and TSMC integration are durable, compounding moats — not one-off wins.

- ## Key Risks

	- 336G is a transitional specification. If the 448G or next-generation optical interconnect paradigm resolves faster than expected, Broadcom or another vendor could reclaim ground in later TPU generations.
	- The 2027 "tens of billions" revenue projection requires multiple CSP programs to ramp — execution risk across several design wins simultaneously.
	- Optical interconnect technology (TFLN, Micro LED) remains at early commercialization stages; the eventual winning architecture is not settled.
