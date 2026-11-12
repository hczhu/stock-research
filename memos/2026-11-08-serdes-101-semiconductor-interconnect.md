tags:: [[SerDes]], [[semiconductor]], [[interconnect]], [[AI-ASIC]], [[data-center]], [[$AVGO]], [[$MRVL]], [[ai-model:GPT-6 Astra]], [[ai-effort:medium]]
file-created-at:: 2026-11-08
file-updated-at:: 2026-11-10

- ## SerDes 101 — Moving Data Between Chips
	- **Source** — User-supplied excerpt titled “[1.a] What is a SerDes?” and Lattice Semiconductor’s January 2003 SerDes Introduction training graphic, page 8. The excerpt’s author, publication, and date were not supplied. Technical clarifications below use primary industry sources.
	- **Thesis** — SerDes converts scarce chip pins and board routing into more bandwidth per connection. For AI hardware suppliers, the economically valuable capability is delivering that bandwidth within the system’s power, reach, reliability, and packaging constraints.

- ## How Serialization Works
	- **SerDes means serializer/deserializer.** The transmitter combines multiple parallel bits into a serial stream, and the receiver reconstructs parallel data. The conversion permits a wide internal bus to communicate through fewer external signal paths. A serial electrical lane commonly uses a differential pair of conductors. [TI design guide](https://www.ti.com/lit/ug/snla200/snla200.pdf)
	- **The source’s clock examples are illustrative.** It places high-end chips around 1–5 GHz, throughput-oriented GPUs and AI ASICs around 1–2 GHz, and general-purpose CPUs around 4–5 GHz. It then assumes a fixed 2 GHz host to explain serialization. Actual clocks depend on the device and operating conditions.
	- **Core clock speed does not define SerDes.** The relevant feature is parallel-to-serial conversion. A link’s bit rate exceeding the host’s core clock is insufficient to classify its architecture, especially when modulation carries multiple bits per symbol.
	- **Three different units matter.** GHz measures clock cycles per second, Gbaud measures transmitted symbols per second, and Gbps measures bits per second. The serial link has its own timing requirements.
	- **PHY means physical layer.** A SerDes-based PHY includes the circuits that transmit and receive the signal. Depending on the design, clock recovery and equalization help recover timing and compensate for channel distortion. [Broadcom SerDes overview](https://www.broadcom.com/topics/what-is-serdes-for-ai-infrastructure)

- ## What the Lattice Graphic Shows
	- The graphic compares a wide parallel bus crossing a backplane with a serialized connection carrying equivalent aggregate bandwidth. Its visual message is that serialization consolidates many slower signal paths into fewer faster paths.
	- | Graphic point | Parallel transfer | Serial transfer and practical qualification |
	  |---|---|---|
	  | Board space | Many traces and pins consume routing area. | Fewer signal paths reduce routing and connector requirements. |
	  | Interference | Adjacent lines can couple noise into one another. | Fewer paths can ease crosstalk management, although faster signaling still requires careful layout. |
	  | Termination circuitry | Each signal line needs suitable termination. | Fewer lines can reduce the number of terminations. Serializer, receiver, and timing circuits add their own area and power. |
	  | Timing skew | Different arrival times across bus lines constrain timing. | Serialization removes the requirement to align all bits of a wide word across separate wires. Jitter and alignment across multiple serial lanes still matter. |
	  | “Single wire” illustration | Many blue lines depict a wide bus. | One green line represents a serial channel schematically. Physical implementations often use a differential pair. |
	- The slide’s “No Skew issues” wording applies to the parallel-bus timing problem it illustrates. Multiple SerDes channels can still have skew between their paths. [TI wide-bus SerDes application report](https://www.ti.com/lit/pdf/snla054)

- ## NRZ, PAM4, and Bandwidth per Lane
	- NRZ uses two signal levels to carry one bit per symbol. PAM4 uses four levels to carry two bits per symbol, doubling raw bit rate at the same symbol rate. Closer level spacing reduces noise margin and increases the importance of signal quality and error handling. PCIe 6.0 uses error correction and CRC to address the higher bit error rate. [PCI-SIG PAM4 explainer](https://pcisig.com/blog/why-did-pcie%C2%AE-60-specification-adopt-pam4-there-are-many-reasons)
	- | Signaling example from the excerpt | Raw lane bit rate | Symbol rate implied by modulation |
	  |---|---|---|
	  | 2G NRZ | 2 Gbps | 2 Gbaud |
	  | 4G PAM4 | 4 Gbps | 2 Gbaud |
	  | 4G NRZ | 4 Gbps | 4 Gbaud |
	  | 32G NRZ | 32 Gbps | 32 Gbaud |
	  | 112G PAM4 | 112 Gbps | 56 Gbaud |
	  | 224G PAM4 | 224 Gbps | 112 Gbaud |
	- These are nominal raw-rate examples. Usable payload bandwidth also depends on encoding, error correction, and protocol overhead. Aggregate raw bandwidth in one direction equals lane count multiplied by raw bit rate per lane.
	- The 4G PAM4 example shows why bit rate and signaling speed must be distinguished. It carries twice the bits of 2G NRZ at the same symbol rate.

- ## Why AI Systems Use Many Serial Lanes
	- The source argues that AI chips need so much I/O that designers combine many SerDes lanes into very wide links. Each lane remains serial, while the system gains aggregate bandwidth by operating lanes concurrently.
	- | Source observation | How to interpret it |
	  |---|---|
	  | More than roughly 18–24 adjacent lanes at 112G PAM4 or faster can create serious problems. | An author’s layout rule of thumb. The excerpt supplies no channel geometry, measurements, or universal lane limit. |
	  | 32–64G NRZ is the author’s preferred electrical/optical operating range. | A design opinion balancing speed and complexity. The best operating point depends on reach, lane count, energy, and packaging. |
	  | A 2 GHz chip might use a 500 MHz internal network. | Illustrates separate clock domains and wide internal buses. On-chip network frequency and external lane rate serve different purposes. |
	- **Parallel interfaces remain relevant.** Memory is a major exception to the excerpt’s claim that off-chip parallel I/O has disappeared. Micron’s HBM2E uses a 1,024-bit-wide interface. UCIe also supports a wide die-to-die architecture within a package, with implementations described as parallel interfaces even though individual lanes serialize data. [Micron HBM2E](https://www.micron.com/about/blog/applications/data-center/hbm2e-fastest-memory-modern-data-center), [Synopsys UCIe IP listing](https://ocpstagingweb2.opencompute.org/chiplets/7/synopsys-ucie-ip)
	- Ethernet and PCIe are examples of interfaces implemented with high-speed serial PHYs. Interface names alone do not specify the modulation, number of lanes, or physical channel.

- ## Where SerDes Matters for Semiconductor Businesses
	- **Analytical inference** — A vendor that combines reliable SerDes with compute, switching, and packaging can address a system bottleneck that additional compute alone cannot solve. Commercial comparisons should include energy per bit, supported reach, error rate, bandwidth per package edge, and deployment maturity alongside headline Gbps.
	- | Company exposure | Verified connection to SerDes | Business question |
	  |---|---|---|
	  | Broadcom [[$AVGO]] | Its NIC and switch products reuse Ethernet and PCIe SerDes technology. | Does reusable connectivity IP improve integration and customer adoption across product families? |
	  | Marvell [[$MRVL]] | Its custom accelerator platform includes SerDes for scale-up fabrics, copper, and optical connectivity. | Does the combination of SerDes and custom compute translate into awarded designs and production revenue? |
	- Company context comes from vendor product descriptions. [Broadcom NIC product brief](https://docs.broadcom.com/doc/PCIe-NIC-Ethernet-Adapters-Specification-Sheet), [Marvell custom AI accelerators](https://www.marvell.com/products/custom-ai-accelerators.html)
	- **Analytical inference** — Fewer physical connections can lower routing and connector costs, while faster lanes can require more complex circuitry and channel engineering. The investment case depends on the resulting system cost and performance, together with the supplier’s ability to capture that value.
