tags:: [[MediaTek]], [[$2454.TW]], [[ASIC]], [[XPU]], [[custom-silicon]], [[advanced-packaging]], [[HBM]], [[SerDes]], [[CPO]], [[UCIe]], [[NVLink-Fusion]], [[data-center]], [[TSMC]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-17
file-updated-at:: 2026-11-17

- ## MediaTek's AI Data Center Pitch: From Custom ASIC to the Rack
	- **Source**: MediaTek's own five-step description of its AI data center solution, apparently narration for a product animation. Text supplied by the user on Nov 17, 2026, without a URL. These are the company's marketing claims, not independent findings.
	- **Thesis (MediaTek's view)**: MediaTek pitches itself as one of the few companies that delivers the whole custom-AI stack: ASIC design, advanced packaging, the multi-die XPU, interconnect at every reach, and rack integration. It claims an efficiency edge from **low-voltage design inherited from mobile**, which it says data-center-only competitors can't replicate.
	- Related: [[MediaTek-MTK-thesis]], [[2026-06-23-mediatek-google-tpu-v9-336g-serdes-broadcom-displacement]], [[2026-11-02-mediatek-emib-yield-tsmc-backstop-second-asic-customer]] and [[2026-08-31-nvidia-mediatek-convertible-nvlink-fusion]].
- ## The Five Steps
	- | Step | What MediaTek says it provides | Specifics claimed |
	  | --- | --- | --- |
	  | **1. Custom ASIC design** | Co-architects a customer's proprietary IP into a full ASIC, or designs accelerators from scratch around the customer's workloads | Design-technology co-optimization (DTCO) with leading fabs to tune the process itself. **10+ tape-outs on TSMC N3, 2+ on N2, first A14 test chip taping out later this year.** Low-voltage operation |
	  | **2. Advanced packaging** | The package as the "system canvas," combining heterogeneous dies into one engine | **2.5D**: compute dies and HBM side by side on a silicon interposer, packages under 10,000 mm². **3.5D**: vertical die stacking for systems of 10,000–20,000 mm² integrating CPUs, XPUs, HBM and I/O chiplets |
	  | **3. The XPU** | A system of four co-designed elements, not a single die | Compute die; memory interface die tuned to HBM per model and deployment phase; ultra-high-speed I/O, with co-packaged copper (CPC) for short reach and co-packaged optics (CPO) for long reach; system-technology co-optimization (STCO) across the package |
	  | **4. Interconnect** | Proprietary technology at every tier | **On package**: die-to-die via UCIe or MediaTek's custom **M-Link**. **On board**: high-speed SerDes and uLED. **Off board/rack**: Ethernet SerDes, **NVLink Fusion** and CPO. **Longest reach**: optical links up to **500 m** |
	  | **5. The rack** | "The rack is the new unit of compute" | A fully integrated AI system optimized for performance per watt and per TCO under real power and thermal limits. "We don't stop at the chip boundary. We architect the rack." |
- ## The Efficiency Argument
	- **Power scales cubically with voltage**, per MediaTek, so running at lower voltage has an outsized effect on efficiency. MediaTek says its mobile heritage, where low-voltage design is foundational, gives it "a head start no data center-only competitor can replicate."
	- **DTCO and early node adoption** are the other levers for "process entitlement," that is, extracting the most performance per watt a node can deliver.
- ## Not Stated
	- No customers, programs, revenue figures or ship dates are named. The text doesn't say which packaging technology (e.g., TSMC CoWoS or Intel EMIB) backs the 2.5D and 3.5D claims, or whether MediaTek has shipped a rack-level system yet.
