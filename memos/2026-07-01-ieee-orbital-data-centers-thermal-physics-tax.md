tags:: [[space-datacenter]], [[orbital-compute]], [[SpaceX]], [[Starlink]], [[Starcloud]], [[Elon-Musk]], [[data-center]], [[TCO]], [[power]], [[cooling]], [[Starship]], [[satellite]], [[germanium]], [[supply-chain]], [[China]], [[$NVDA]], [[$GOOGL]], [[$TSLA]], [[defense]], [[AI-compute]]
file-created-at:: 2026-07-01

- **Source**: Two linked *IEEE Spectrum* pieces — Andrew Cavalier (aerospace analyst, ABI Research), "Why Orbital Data Centers Are Harder Than Silicon Valley Thinks," June 11 2026, and Harry Goldstein's editorial "The Space-based Data Center Hype Machine Is Already in Orbit," July 1 2026, with comments from Spectrum editors Dina Genkina and Goldstein. **Cavalier's TCO model is explicitly back-of-envelope** and his employer sells aerospace research; the editorial is opinion. Every derived figure below was recomputed.

- **Thesis**: Three published TCO models of the same question now span roughly **200×** — Starcloud's own filing implies orbital is ~21× *cheaper*, SemiAnalysis says ~4.4× more expensive, ABI says at least 10× more expensive. That spread is the finding: **the question is not yet modelable, so any capital allocated to it today is allocated on narrative.** What *is* firm is the physics — radiator area scales with power and nothing else, and thermal plus power hardware consumes 65–70% of satellite mass — which means cheaper launch cannot fix the economics, a conclusion two independent models now reach by different routes.

- ## The three models, and how far apart they are

	- | Model | Source interest | Claim |
	  |---|---|---|
	  | **Starcloud** | Applicant; raising against the thesis | ~\$8M per 40-MW cluster over 10 years vs. ~\$167M terrestrial — implies **~21× cheaper in orbit** |
	  | **SemiAnalysis** | Paid research, no launch exposure | **4.4× more expensive** on LCOC in 2026; parity ~2040 base case, ~2034 in an "Elon Musk" case |
	  | **ABI Research** | Paid research, no launch exposure | **At least 10× more expensive** per GPU-year, at an optimistic \$44/kg Starship launch and \$0.20/kWh terrestrial power |

	- The two disinterested models agree on sign and disagree on magnitude by ~2.3×. **The one model claiming orbital is cheaper belongs to the party filing for an 88,000-satellite constellation.** Treat the 21× as a fundraising artifact until an independent party reproduces it.

	- **Forecast optimism tracks vertical integration into launch almost perfectly.** Musk says parity in 2–3 years and owns the compute (xAI, now inside SpaceX), the launch (Starship) and the solar (Tesla) — Genkina's summary is *"it's almost like he's paying himself."* Starcloud owns none of the launch and depends on Starship, and forecasts near-term parity anyway. **Google, which simply buys launch, is the only one with a mid-2030s date** — and conditions it on launch falling below \$200/kg, in its own published paper. See [[2026-06-19-semianalysis-space-datacenters-tco-orbital-compute]].

- ## The thermal arithmetic, recomputed

	- Radiative cooling is the only mechanism available — vacuum removes conduction and convection — so the Stefan-Boltzmann law governs. Radiated power scales with area and with the **fourth power** of absolute temperature:

		- $$P = \varepsilon \sigma A \left(T^{4} - T_{\text{bg}}^{4}\right)$$

		- where $P$ is heat rejected (W), $\varepsilon$ the surface emissivity, $\sigma$ the Stefan-Boltzmann constant $5.67 \times 10^{-8}\ \mathrm{W\,m^{-2}K^{-4}}$, $A$ the radiator area (m²), $T$ the radiator temperature (K) and $T_{\text{bg}}$ the 3 K background of deep space.

		- The background term is negligible — $3^{4}/333^{4} \approx 7 \times 10^{-9}$ — so it drops out, and the form that matters is the one solved for the **only variable an orbital architect controls**:

		- $$A = \frac{P}{\varepsilon \sigma T^{4}}$$

	- **Area is therefore linear in power and inverse-quartic in temperature.** Doubling the heat load doubles the radiator; running the chip hotter is the only way to shrink it, which is why every proposal fights for the highest tolerable junction temperature. Cavalier calls the consequence a **"physics tax."**

	- Working the formula at Cavalier's stated 60 °C: $\sigma T^{4} = 698.5\ \mathrm{W/m^{2}}$, so a perfect blackbody radiator would need **1.00 m²** for a 700 W chip. His **1.4 m²** therefore implies an emissivity of about **0.72** — an assumption the article never states, and a generous one for a coating that the same article says degrades under UV and atomic oxygen.

	- **The model's stated assumptions**, each of which pushes the answer favourably:

	- | Assumption | Value | Effect |
	  |---|---|---|
	  | Reference chip | Nvidia H100 at **700 W** | Blackwell-class parts draw more, so the per-chip area understates current silicon |
	  | Operating temperature | constant **60 °C** | Called the sweet spot for GPU longevity; hotter would shrink the radiator, cooler would enlarge it quartically |
	  | Radiator orientation | **perfectly facing deep space** | Assumes away the attitude-control cost of maintaining it |
	  | Background temperature | **3 K** | Contributes ~7 parts per billion; harmless |
	  | Emissivity | not stated — **~0.72 implied** | See below; a fresh-coating value |

	- **The scaling ladder, fresh against end-of-life.** Degradation from UV and atomic oxygen over a LEO satellite's typical **5-year** life raises the per-chip requirement from 1.4 m² to nearly 2.0 m² — a **+40% physics tax** that must be launched as mass on day one:

	- | Unit | Power | Radiator, fresh | Radiator, end-of-life | Implied flux |
	  |---|---|---|---|---|
	  | One H100 | 700 W | **1.4 m²** | **~2.0 m²** | 500 → 350 W/m² |
	  | One GPU slot, all-in | 1,250 W | 2.5 m² | 3.6 m² | rack power ÷ 32 |
	  | One rack, 32 GPUs | 40 kW | **80 m²** — "a pickleball court" | 112 m² | 40 kW ÷ 700 W × 1.4 = 80.0 exactly |
	  | 100-MW data center | 100 MW | **2,500 radiators** = 200,000 m² (**0.2 km²**) | 280,000 m² (**0.28 km²**) | 2,500 racks = 80,000 GPUs |

	- **The GPUs are only 56% of the thermal load.** Thirty-two H100s draw 22.4 kW of the rack's 40 kW; CPUs, memory and networking add **+79% on top of GPU power**. Every GPU slot therefore carries **1,250 W** of heat, not 700 W, and **44% of the radiator exists to cool things that are not the accelerator** — so a more efficient GPU shrinks the radiator far less than proportionally.

	- **Radiator area per unit of delivered service**, using the rack capability figures Cavalier cites (2.5 TB of memory, "over 20,000 concurrent users," or 16 simultaneous Llama 3 instances):

	- | Service unit | Fresh | End-of-life |
	  |---|---|---|
	  | Per 1,000 concurrent users | **4.0 m²** | 5.6 m² |
	  | Per Llama 3 instance | **5.0 m²** | 7.0 m² |

	- These are the figures to carry forward: serving twenty thousand users requires a pickleball court of radiator that must be folded into a fairing, launched, unfurled, and kept pointed at the void for five years while it degrades 40%.

	- **The cross-check that matters is against flight hardware.** The ISS radiator rejects 70 kW across 325 m² — **215 W/m²**. Cavalier's fresh-radiator assumption is **500 W/m², about 2.3× better than the best thing actually flying**, and even his degraded end-of-life figure at 350 W/m² is **1.6× better than ISS**. His model is therefore optimistic in the same direction as its conclusion is damning: the real areas are likely larger than tabulated.

	- **One internal inconsistency, visible once the formula is applied.** The figure caption gives "just under 3 m²" at 20 °C against 1.4 m² at 60 °C, a ratio of ~2.1×, where $\left(333/293\right)^{4} = 1.67$. Backing out emissivity from each stated pair gives $\varepsilon \approx 0.72$ at 60 °C and $\approx 0.75$ at 85 °C — mutually consistent — but $\approx 0.56\!-\!0.58$ at 20 °C (the caption says "just under 3 m²"). **No single radiator satisfies all three figures**, so at least one is wrong or assumes a different surface.

- ## Mass, not launch cost, is the binding constraint

	- **Radiators and solar arrays consume 65–70% of total satellite mass.** Compute is a minority of what you launch. Cavalier: *"the critical factor isn't just launch cost; it's the computing power per unit mass and electric-power economics."*

	- The power and cooling areas are near-equal by construction: solar collects ~**400 W/m²** (29% of the 1,361 W/m² solar constant) while radiators reject ~**450 W/m²**, so **every square metre of generation demands roughly another square metre of cooling**, and the radiator must be a structural element rather than a coating on something else.

	- **Two independent models now converge on "launch cost is not the lever," by different mechanisms.** SemiAnalysis gets there from the cost side — IT capital is 75–80% of TCO, and cutting launch 85% moves total program capex only 8%. ABI gets there from the mass side — the majority of launched mass is thermal and power hardware that stays expensive at any launch price, and space-grade photovoltaics run orders of magnitude above terrestrial. **That convergence is the strongest claim in this memo**, and it directly contradicts Google's own framing, which makes a sub-\$200/kg launch price the trigger for parity.

	- Perfect three-way alignment — panels to sun, radiator to the void, antennas to Earth — is what makes the numbers above achievable at all, and it requires high-torque attitude control with many failure modes, on hardware that cannot be serviced.

- ## The three programs

	- | | SpaceX / xAI | Starcloud | Google Project Suncatcher |
	  |---|---|---|---|
	  | Status | FCC filing Jan 2026; AI-1 design June 2026 | One H100 flown late 2025; second satellite due Oct 2026 | Research; 2-satellite demo with Planet early 2027 |
	  | Scale | Up to **1 million satellites** | 5 GW across ~100 launches | 81-satellite clusters |
	  | Power/satellite | Up to 150 kW | 40 MW per launch container | Not specified |
	  | Silicon | Custom **D3** chip, Terafab consortium | Off-the-shelf H100 / Blackwell | **Trillium TPU v6e** |
	  | Orbit | 500–2,000 km LEO, SSO shells at 50-km intervals | Dawn-dusk SSO, >99% sunlight | Dawn-dusk SSO, ~650 km |
	  | Parity claim | 2–3 years | Near-term | Mid-2030s, at <\$200/kg |

	- **Starcloud's single flown H100 could not run at full power because its radiator was too weak.** That is the entire body of orbital AI-compute flight evidence to date, and it failed on exactly the constraint both disinterested models identify as binding.

	- **The good orbit is scarce, and all three want it.** SemiAnalysis notes most LEO gets sun only ~60% of the time; only dawn-dusk sun-synchronous orbit approaches continuous illumination, and it is a narrow subset of LEO. Starcloud and Google both target it. SpaceX's 1M-satellite filing spans 500–2,000 km on 50-km shell spacing, so **most of that constellation cannot sit in the orbit that makes the power argument work.**

	- **The deployment arithmetic is the editorial's strongest point.** Roughly 7,000 orbital launches have occurred in all of history. One million satellites at Starship's 60 per vehicle needs **16,667 dedicated launches**; against SpaceX's record 165 missions in 2025, even a **10× cadence takes 10.1 years**. At Starlink's ~4,000 satellites/year build rate, a **10× manufacturing increase still takes 25 years**. Both check exactly.

- ## Two constraints the AI-compute framing misses

	- **Germanium.** Space-grade solar depends on germanium substrates whose supply is **concentrated in China**, and Cavalier judges scaling that availability extremely difficult. Radiation-tolerant perovskite is the alternative and is **five or more years out**. A US-led orbital compute buildout therefore runs through a Chinese-controlled input at the one layer that consumes two thirds of satellite mass alongside the radiators.

	- **Silicon has to be commercial, and commercial silicon is soft.** Rad-hard processors cannot run a modern LLM, so orbital data centers must fly the same H100s and TPUs used terrestrially, exposed to bit flips and latch-ups. The mitigation is redundancy rather than shielding — a cluster of commercial nodes at **one tenth to one hundredth** the cost of rad-hard, with triple-modular voting and an orchestrator that reboots corrupted nodes. **Some fraction of the fleet's compute is permanently spent on checking itself**, which is a direct haircut to the delivered FLOPs the TCO models divide by.

- ## What is actually investable here

	- **The defensible applications are not AI compute.** Cavalier names three: preprocessing Earth-observation data, where hyperspectral and SAR sensors generate hundreds of TB/day against congested RF downlink and insufficient ground infrastructure; real-time hypersonic missile detection and tracking; and collision avoidance. These are **defense and space-infrastructure markets**, sized and sold entirely differently from AI capacity, and "space data center" as an investment theme welds them to a compute story they have little to do with.

	- The collision-avoidance case has the clearest quantitative hook: **Starlink executes an avoidance manoeuvre every 2 minutes on average**, already using onboard AI but with most processing still on the ground. At megaconstellation density the OODA loop has to move onboard — minutes to milliseconds — and standard flight computers cannot run the probability models required. **That is a real compute requirement created by the constellation itself**, and it grows with satellite count regardless of whether orbital AI training ever pencils.

	- **Regulatory and externality risk is real and under-priced.** A million satellites carrying large radiative wings draws astronomer opposition over sky brightness and raises Kessler-cascade exposure across all of LEO. The FCC filing is an application, not an approval.

	- **For [[$NVDA]], this is TAM marketing rather than demand.** Jensen Huang's GTC line — *"Space computing, the final frontier, has arrived"* — sits against a flight record of one H100 that could not run at full power. Starcloud and Google both fly merchant parts, so any real deployment is incremental silicon demand, but at a scale invisible against terrestrial. SpaceX's custom D3 through the Terafab consortium is the one design that would route around merchant GPUs entirely.

	- One housekeeping note: the two articles disagree on the installed base — the editorial says **~14,500 active satellites**, the feature says **over 17,000 in orbit**. The gap is probably active-versus-total; neither figure should be quoted without that qualifier.
