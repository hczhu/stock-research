tags:: [[$ASML]], [[EUV]], [[lithography]], [[semiconductor]], [[moat]], [[platform]], [[monopoly]], [[export-controls]], [[China]], [[SMIC]], [[Huawei]], [[$TSM]], [[$INTC]], [[$005930]], [[Zeiss]], [[Nikon]], [[Canon]], [[EDA]], [[Moore's Law]], [[capex]]
file-created-at:: 2026-10-15

- ## ASML's EUV Monopoly: An Integration Moat, Not an Invention Moat
	- **Source**: Michael A. Cusumano, "The ASML Monopoly: Platform and Ecosystem Leadership in EUV Lithography," *Communications of the ACM*, October 2026 (Vol. 69, No. 10, pp. 26-28), DOI 10.1145/3838602, Technology Strategy and Management column. Cusumano is MIT Sloan SMR Distinguished Professor and co-author of *The Business of Platforms*. Extracted from user-provided photos of the printed pages. Same issue as [[2026-10-15-text-to-sql-benchmarks-spider-bird-enterprise-gap]]; companion columns to [[2026-07-12-tsmc-manufacturing-innovation-platform-cusumano]] and [[2025-01-01-intel-fall-from-grace-cusumano]].
	- **Thesis**: ASML's de facto monopoly "is **not based on a single breakthrough innovation**" but on decades of foresighted investment plus platform-leadership and ecosystem-management skill — it **outsources 90% of modules** and keeps the system-integration role. Two investable consequences follow. First, the moat is replication-proof on a decade horizon: no competitor has reproduced "the core technology or the full stack of system capabilities," China's prototype is not expected to reach commercial production before **2030**, and Russia is ~**two decades** behind. Second, the same outsourcing strategy **caps unit output** — ASML shipped just **48 EUV systems in 2025**, planning 60 in 2026 and 80/yr thereafter — so ASML is a volume-constrained toll on every leading-edge wafer, with growth coming from **ASP mix (\$200M → \$400M)** more than from unit scale.

- ## The Monopoly by the Numbers
	- | Metric | Value |
	  |---|---|
	  | Share of all lithography tools | **~90%** |
	  | Share of EUV systems | **100% — the only supplier** |
	  | Advanced DUV market share | **60-85%** |
	  | Market value | **~\$677 billion** (Europe's most valuable technology company) |
	  | FY2025 revenues | **>\$37 billion** |
	  | FY2025 profits | **\$11 billion** |
	  | Employees | **44,000** |
	- Context for why this layer matters: the generative-AI semiconductor stack is "constrained at multiple levels" — Nvidia in GPU designs, TSMC in advanced manufacturing, SK Hynix/Micron/Samsung in HBM — and ASML sits **one layer deeper**, in the equipment used to fabricate the most advanced chips.

- ## Origins: A Failed First Product, Then a Modular Platform
	- Photolithography "prints" circuit patterns onto photosensitive-coated silicon wafers; the technique resembles photography and dates to the **1950s**, invented for the U.S. military and Fairchild Semiconductor.
	- **Early 1980s**: U.S. firms (notably GCA) held as much as an **85% share** of lithography machines. By the later 1980s **Nikon and Canon overtook GCA** — which shut down in **1993** — and came to dominate.
	- **1984**: ASML founded as a joint venture between **Philips** (founded 1891; also an early TSMC investor) and **ASM International** (founded 1964), to commercialize Philips' in-house photolithography technology.
	- First product, the **PAS 2000** ("Philips Automatic Stepper"), was unreliable and **failed**. ASML became independent in **1988**.
	- **1991 — PAS 5500**: highly successful, built on a **modularized architecture**, precision optics from **Carl Zeiss AG** (partnership started 1983), and "near" ultraviolet light. Added **DUV** in the mid-1990s. The modular architecture is the origin of the later ecosystem strategy.
	- The 1990s strategic problem for European/U.S. players was how to **leapfrog Nikon and Canon** — by establishing an early lead in the *next* generation. DUV had physical limits; rivals to EUV (X-rays, electron beams, ion beams, charged particles) "none offered the potential speed and cost advantages of EUV."

- ## The EUV Program: Two Decades and \$11 Billion
	- Cusumano calls EUV commercialization "one of the greatest stories in the history of science, engineering, and business" — it took roughly **two decades**, **\$11 billion in R&D**, and a global effort **coordinated by one firm**.
	- | Year | Milestone |
	  |---|---|
	  | 1985-86 | **Hiroo Kinoshita** (NTT labs, Japan) adapts **Soviet** multilayer-mirror research to project the first EUV images using 365nm mercury-vapor lamps; his 1986 conference presentation is met with skepticism but prompts global research |
	  | 1994-95 | ASML executives conclude EUV is the future. **Martin van den Brink** (later president/CTO), who led PAS 5500, champions it and puts **Jos Benschop** in charge |
	  | 1998 | ASML and Zeiss form the **EUCLIDES** consortium. Similar consortia appear in the U.S. and Japan — **only EUCLIDES succeeded** |
	  | 2000 | Small team formed to build a prototype EUV stepper; ASML buys **Silicon Valley Group (SVG)**, the last surviving U.S. lithography company, gaining **U.S. military R&D** access |
	  | 2006 | Prototype completed — it **took six years**. Close work with suppliers, universities, and **IMEC** (Belgium) as test ground |
	  | 2009 | New EUV R&D facility at Veldhoven headquarters |
	  | 2012 | **Intel, Samsung, and TSMC become investors** to share R&D cost. Intel's **\$4 billion for a 15% stake** was several times larger than TSMC's or Samsung's |
	  | 2010 → 2013 → 2017 | EUV prototypes ship (2010) → commercially viable system (2013) → **machines perfected for mass production (2017), priced at \$100 million** |
	  | Aug / Oct 2019 | **Samsung** ships the first EUV-enabled product ("7nm" node) in the **Galaxy Note 10**; **TSMC** follows in October with 7nm EUV products for multiple customers **including Huawei** |
	- **Intel's self-inflicted wound**: despite backing EUV early and buying the largest stake, Intel **delayed commercial introduction because of the high cost**. That delay caused it to fall behind TSMC and Samsung in advanced manufacturing and led to "severe financial and reputational difficulties, from which Intel is only now starting to recover."

- ## Why the Machines Cannot Be Copied
	- **The physics**: feature size depends on wavelength. The industry ran on **DUV at 193nm** for decades (still widely used); EUV cuts this to **13.5nm**.
	- EUV light **cannot pass through air or conventional glass**, which eliminates lens-based optics entirely. Instead the machines use **multilayer mirrors fabricated to sub-nanometer precision by Zeiss**.
	- **Light generation**: a high-powered laser from **TRUMPF GmbH** (Germany) strikes microscopic **tin droplets 50,000 times per second**, creating a plasma at about **200,000°C — 40× hotter than the surface of the sun**. The **laser module alone is said to contain 457,329 parts**.
	- **Masks**: foundries build them with EDA vendors (**Cadence, Synopsys**), generating data for the **~50 alternating layers of silicon and molybdenum** per mask, which must be perfectly compatible with the optics, light system, and the stepper's numerical aperture. Validation needs special test engines and many simulation rounds.
	- **The actual moat** (pull quote): *"The challenge for potential competitors is that no one component defines performance of the whole system."* Light source, optics, wafer, mask, and control software come from **different specialist firms**, and all modules must work as a **tightly coupled system in a vacuum** under extreme thermal, mechanical, and computational constraints — requiring advances across plasma physics, precision optics, mechanical engineering, materials science, and software. ASML also holds rights to **thousands of patents**.

- ## Machine Economics and the Capacity Ceiling
	- | Attribute | Detail |
	  |---|---|
	  | Price range | **~\$200M** for less sophisticated versions; **~\$400M** for the most advanced ("2nm" and denser nodes) |
	  | Physical scale | **~400,000 lbs**, size of a double-decker bus, **three Boeing 747s** to transport |
	  | Bill of materials | **>100,000 modules** from some **800 suppliers**, who have thousands of sub-suppliers |
	  | ASML's role | **Outsources 90% of modules**; acts as R&D leader and **system integrator** |
	  | 2025 shipments | **48 EUV systems** out of **327 lithography machines of all types** |
	  | Plan | **60 EUV in 2026**, then **80 annually** |
	- The outsourcing strategy "leveraged the R&D and capabilities of many outside firms, but **has limited ASML's control over manufacturing capacity**" — the explicit trade-off behind the low unit count.
	- **Why EUV wins on cost despite the price tag**: as Intel discovered, the power, precision, and speed of EUV make it **cheaper** to produce the densest chips than DUV workarounds with creative 3D chip designs.
	- **Why rivals exited**: cost and complexity explain both why Intel, TSMC, and Samsung **chose to invest in ASML rather than build EUV themselves**, and why Nikon and Canon — DUV masters — **gave up on EUV** and then fell behind in advanced DUV too. Cusumano adds that the Japanese lacked the **U.S. military and national-lab access** ASML obtained via SVG.
	- ASML keeps tight control of critical subsystems through subsidiaries: **HMI** (mask pattern verification), **Cymer** (light sources), **Berliner Glas** (optics).

- ## China's Response
	- Since **2019**, following U.S. policy, the Netherlands has blocked export of the most advanced ASML machines to China — provoking "a **Manhattan Project-type of response**." China is investing an estimated **\$50 billion per year** in semiconductor manufacturing technology. Russia has pursued EUV for years but "appear[s] to be as much as **two decades behind**."
	- **SMIC** (founded 2000 as a TSMC-like national foundry, formerly a large ASML customer) has since 2019 been barred from importing **both EUV and the latest DUV** machines from ASML, Canon, and Nikon.
	- **The DUV workaround**: SMIC and others extend DUV via **multi-patterning** — extra mask lines across multiple passes. "Though costly and slow," it has enabled **7nm and 5nm** devices, mainly **for Huawei**.
	- **The domestic EUV program** (reported by Reuters; treated as a state secret): in **early 2025, former Chinese ASML engineers completed a prototype at a Shenzhen laboratory**, built with components sourced from **older ASML machines on secondary markets**. It is operational and undergoing testing; observers expect **at least 2030** before commercial production.
	- Structure — not simple reverse engineering: the **Central Science and Technology Commission** oversees the project, **Huawei is the system integrator**, and the **Shanghai Institute of Optics and Fine Mechanics (SIOM)** plus several private firms participate. Technically they are using **solid-state lasers** for EUV generation — an approach **ASML had determined inadequate for mass production** — and still need **Zeiss mirrors (also export-banned) or a substitute**. Huawei is separately developing **Laser-Induced Discharge Plasma (LDP)**, using high voltages to generate EUV; LDP should consume **less energy than ASML's tin-droplet approach** while still producing 13.5nm light.
	- **The real obstacle is mass production, not a working prototype.** Precedent from the DUV workaround: for 7nm, SMIC reportedly ran **yields below 50%** and **wafer costs 40-50% above TSMC** — yet still shipped advanced devices. Initial machine cost is "probably a secondary concern" for a state program.
	- **The target keeps moving**: ASML and its customers are **already introducing sub-2nm fabrication technology**. Cusumano's closing caveat: "At some point, the laws of physics will limit ASML's approach and a better technology will emerge, **but we are not there yet**."

- ## Related Memos
	- [[2026-07-12-tsmc-manufacturing-innovation-platform-cusumano]] — same author on TSMC as innovation platform
	- [[2025-01-01-intel-fall-from-grace-cusumano]] — same author on Intel's decline, incl. the EUV delay
	- [[2026-05-19-imec-roadmap-cfet-2033-2d-2041]] — IMEC long-range node roadmap
	- [[2026-06-07-semi-equipment-market-revenue-by-region-1Q2026]] — WFE spending by region
	- [[2026-02-05-mad-podcast-dylan-patel-nvidia-moat-china-ai-capex]] — China semi capability and export controls
