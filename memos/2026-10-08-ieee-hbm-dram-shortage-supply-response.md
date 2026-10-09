tags:: [[$MU]], [[$000660.KS]], [[$005930.KS]], [[$NVDA]], [[$AMD]], [[HBM]], [[DRAM]], [[semiconductor]], [[advanced-packaging]], [[supply]], [[pricing]], [[capex]]
file-created-at:: 2026-10-08

- ## HBM Demand Tightens the Whole DRAM Market
	- **Sources**: Samuel K. Moore, “How and When the Memory Chip Shortage Will End,” IEEE Spectrum, February 10, 2026, corrected March 9; and Harry Goldstein, “AI Is Insatiable,” April 6, 2026. Supplied PDFs are titled “AI Boom Fuels DRAM Shortage and Price Surge” and “AI and the High Bandwidth Memory Shortage.” Goldstein's editorial builds on Moore's reporting, so the two are not independent confirmations.
	- **Thesis**: AI buyers are pulling DRAM capacity toward HBM just as suppliers remain cautious after the previous downturn. This supports memory pricing beyond AI products, while exposing PC and consumer-electronics makers to scarcity. Packaging improvements can relieve bottlenecks sooner than new fabs, but taller stacks also increase silicon consumption; eventual capacity additions still carry cyclical downside.
	- **Date boundary**: This memo was created October 8. Prices, forecasts, and project dates below are those reported in the February/April articles, not an October market update. Several charts are incomplete in the saved PDF; figures are taken from the readable prose.

- ## Key Data Points
	- | Signal | Reported figure | Interpretation |
	  |---|---|---|
	  | DRAM prices | **Up 80–90% quarter-to-date**, Counterpoint cited in Moore's article | Evidence of an early-2026 price shock; product mix and spot/contract basis are not specified. |
	  | HBM price and GPU cost share | **About 3× other memory; at least 50% of packaged-GPU cost**, SemiAnalysis estimate | Memory is a major accelerator cost driver. Packaged-GPU cost is not the same as system selling price or total data-center cost. |
	  | Micron revenue mix | HBM **plus other cloud memory** rose from **17% of DRAM revenue in 2023 to nearly 50% in 2025** | A substantial mix shift toward cloud buyers; this is not HBM-only revenue. |
	  | HBM market forecast | Micron projected **\$35B in 2025 → \$100B in 2028**, reaching the latter milestone **two years earlier** than previously expected | A roughly **2.9×** expansion, or **42% annualized growth** (derived); a company forecast rather than realized demand. |
	  | Accelerator memory content | Nvidia B300 and AMD MI350 each use **eight HBM stacks with 12 DRAM dies per stack** | **96 memory dies per accelerator** before base dies (derived); GPU shipments alone understate the memory manufacturing requirement. |
	  | New-fab economics | **$15B or more**, with construction and ramp taking **18 months or more**, per Thomas Coughlin | Supply responds with a substantial capital commitment and lag, creating the conditions for overshoot. |

- ## Why Supply Is Slow to Respond
	- **The previous bust still shapes investment**: Coughlin describes pandemic inventory accumulation followed by a 2022–23 downturn and aggressive production cuts. In his account, suppliers remained reluctant to add capacity through 2024 and much of 2025, leaving the industry poorly positioned for the AI surge.
	- **Product allocation spreads the shortage**: HBM's demand and profitability attract production resources away from conventional memory. Large AI hardware buyers receive priority, while other electronics manufacturers compete for the remaining supply.
	- **Yield and packaging matter before greenfield fabs**: Economist Shawn DuBravac expects nearer-term relief from incremental expansion, process learning, stacking efficiency, and coordination between memory suppliers and chip designers. A fab announcement does not by itself establish qualified, saleable HBM output.

- ## Capacity Timeline as Reported in the Article
	- | Supplier | Projects and stated milestones | How to read the dates |
	  |---|---|---|
	  | **Micron** | Singapore HBM facility: **2027** production; acquired PSMC Taiwan fab: **2H27** production; New York DRAM complex: **2030** full production | These are the article's historical expectations, with different ramp stages and facility functions. |
	  | **Samsung** | New Pyeongtaek plant: **2028** production | No incremental wafer volume or product mix is supplied. |
	  | **SK Hynix** | Cheongju HBM fab: **2027** completion; West Lafayette HBM/packaging facilities: production by **end-2028** | Construction completion and production start are different milestones. |
	- Intel CEO Lip-Bu Tan is quoted expecting no DRAM relief until **2028**. That is an executive outlook, not a guaranteed shortage duration; the articles provide no common capacity model reconciling these projects with demand.

- ## Technology Can Ease Supply and Increase Memory Intensity
	- **Taller stacks consume more DRAM per package**: Moore reports 12-high commercial stacks against standards permitting 16. Moving from 12 to 16 dies would increase die count by **one-third**, holding die capacity and stack count constant; it does not necessarily improve bits per wafer or manufacturing yield.
	- **Heat removal constrains the roadmap**: SK Hynix claims an advantage from advanced MR-MUF. Hybrid bonding can shorten die-to-die distance and improve thermal conduction; the article cites Samsung's **2024 demonstration of a 16-high stack**, with 20-high suggested as feasible. Demonstration is not evidence of high-volume yield or customer qualification.
	- **Demand can adapt before fabs arrive**: Goldstein highlights hardware choices and product redesigns that use less memory at some performance cost. This creates a demand-side adjustment that a fixed memory-per-device forecast can miss.

- ## Company Economics and the Cycle
	- **Micron, SK Hynix, Samsung**: The combination of cloud mix growth, scarce conventional DRAM, and difficult packaging can support pricing and margins. Their relative benefit depends on qualified HBM output and yields, not simply installed wafer capacity.
	- **Nvidia and AMD**: More memory content raises the importance of supplier access and packaging execution. HBM cost pressure can absorb some of the value created by faster accelerators; the sources do not quantify how much is passed through to customers.
	- **Consumer-electronics manufacturers**: AI buyers' willingness to pay can raise component costs even without strong consumer demand. Tariffs and broader inflation make the memory contribution harder to isolate in final retail prices, as Goldstein notes.
	- **A tight market is not proof of permanent de-cyclicality**: Moore's article argues prices could remain high after capacity expands, but Coughlin warns that weakening AI investment could coincide with new supply. Scarcity, customer redesigns, and delayed capacity must be considered together rather than extrapolating peak pricing.
