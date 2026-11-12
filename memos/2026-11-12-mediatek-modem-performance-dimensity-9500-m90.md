tags:: [[$2454.TW]], [[$QCOM]], [[semiconductor]], [[5G]], [[smartphones]], [[ai-model:GPT-6 Astra]], [[ai-effort:high]]
file-created-at:: 2026-11-12

- ## MediaTek modems: a stronger premium-phone proposition, not blanket leadership
	- **Source**: User-supplied thesis prompt, checked against MediaTek and Qualcomm product documentation and a first-hand Beebom handset test. Sources linked below; researched November 12, 2026.
	- **Thesis**: Competitive connectivity can remove an obstacle to MediaTek winning premium handset sockets, complementing its compute and AI capabilities. The evidence supports a credible alternative to Qualcomm, not superiority across every network or automatic pricing power.

- ## Field evidence: uploads and congestion versus download speed
	- [Arjun Sha's May 4, 2026 test](https://gadgets.beebom.com/stories/i-tested-5g-modems-on-qualcomm-and-mediatek-phones-to-find-which-performs-better) compared a **Vivo X300 Pro / Dimensity 9500** with a **OnePlus 15 / Snapdragon 8 Elite Gen 5**, using one Jio SIM at two Noida locations and Ookla Speedtest.
	- | Environment / metric | Dimensity handset | Snapdragon handset |
	  |---|---|---|
	  | Quiet: download | 325 Mbps | 436 Mbps |
	  | Quiet: upload | 57.8 Mbps | 42.6 Mbps |
	  | Quiet: ping | 27 ms | 16 ms |
	  | Crowded: download | 27.5 Mbps | 44.0 Mbps |
	  | Crowded: upload | 11.7 Mbps | 0.86 Mbps |
	  | Crowded: ping | 28 ms | 159 ms |
	  | Crowded: jitter | 14 ms | 72 ms |
	- **Reading**: MediaTek's handset delivered much better congested uplink and responsiveness; Qualcomm's retained faster downloads. Quiet-site latency favored Qualcomm. This does not establish universally better gaming connectivity.
	- **Boundary**: one operator, two sites, different antennas and RF tuning; no repeat-run distribution disclosed. This is device-level evidence, not a controlled silicon comparison or longitudinal proof of gap-closing.

- ## Correct the specification mapping: Dimensity 9500 is not M90
	- | Platform | Officially documented cellular capability | Meaning |
	  |---|---|---|
	  | Dimensity 9500 | Release 17; sub-6GHz **5CC aggregation**, up to **7.4Gbps** | These are the specifications relevant to the tested MediaTek flagship. Its cited product page does not establish mmWave, 10CC, or NTN support. |
	  | MediaTek M90 | Release 17 / Release 18-aligned; up to **12Gbps** downlink; **6CC sub-6GHz**, **10CC mmWave**; IoT-NTN and NR-NTN | A separately announced modem capability set, not grounds for assigning every feature to Dimensity 9500 or every MediaTek phone. |
	  | Qualcomm X85 in Snapdragon 8 Elite Gen 5 | Up to **12.5Gbps downlink / 3.7Gbps uplink**; **6CC sub-6GHz**, **10CC mmWave**; NTN; Release 18-ready | Qualcomm also supports these advanced features. Headline rates are ceilings, not expected consumer throughput. |
	- Sources: [Dimensity 9500 specifications](https://www.mediatek.com/products/smartphones/mediatek-dimensity-9500), [M90 announcement, February 26, 2025](https://www.mediatek.com/press-room/mediatek-introduces-m90-5g-advanced-modem-with-ai-and-12gbps-peak-speed), [Snapdragon 8 Elite Gen 5 specifications](https://www.qualcomm.com/smartphones/products/8-series/snapdragon-8-elite-gen-5).
	- **Carrier aggregation** combines component carriers; **10CC here refers to mmWave**, not ten sub-6GHz carriers. NTN means non-terrestrial connectivity; standards support alone does not establish a handset's antenna implementation, service availability, or satellite subscription economics.
	- MediaTek claims **10% power savings** through AI traffic prediction and **50% latency reduction** through AI congestion prediction for Dimensity 9500. These are vendor feature claims, not measured savings versus Qualcomm in the cited field test. [MediaTek product page](https://www.mediatek.com/products/smartphones/mediatek-dimensity-9500)
	- The M90 announcement reported an **11.6Gbps FR1+FR2 test with Keysight** and a **5.5Gbps sub-6GHz 6CC trial with Verizon and Samsung**. These demonstrate interoperability under specified test configurations, not retail-phone speeds. Its engineering-sample schedule was a historical announcement; no current shipping-volume or handset-design-win claim is inferred from it. [M90 announcement](https://www.mediatek.com/press-room/mediatek-introduces-m90-5g-advanced-modem-with-ai-and-12gbps-peak-speed)

- ## How modem capability can become shareholder value
	- **Premium socket eligibility**: an OEM needs the whole platform to work—compute, camera, connectivity, power, and software. Strong connectivity can reduce a reason to reject an otherwise competitive Dimensity design. That can support flagship mix and average selling prices, but neither follows mechanically from a speed test.
	- **Procurement leverage cuts both ways**: a credible second supplier gives handset makers more negotiating power. MediaTek may gain units while part of the technology benefit accrues to OEMs through lower chip prices. Revenue share and gross profit are therefore better evidence of economic success than specification parity alone.
	- **Durable engineering versus a single benchmark**: standards expertise, RF integration, operator interoperability, firmware, and OEM support require sustained investment. The potential moat is repeatedly shipping reliable platforms across devices and networks, not one favorable congestion result.
	- **Complement to the ASIC thesis**: connectivity reinforces MediaTek's breadth of silicon and systems integration. Cellular RF competence and data-center SerDes are different disciplines; modem progress does not independently validate TPU wins, ASIC volumes, or SerDes superiority. Treat mobile premiumization and custom silicon as separate earnings paths.
	- **Evidence needed for a financial upgrade**: repeated multi-operator tests, confirmed production sockets, premium-platform revenue mix, realized pricing, and margins after R&D. The sources here provide no incremental shipment or earnings estimate, so the update strengthens the qualitative mobile thesis without changing valuation assumptions.
	- **Integrated thesis**: [[MediaTek-MTK-thesis]].
