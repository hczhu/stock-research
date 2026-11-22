tags:: [[YMTC]], [[ZhiTai]], [[Xtacking]], [[NAND]], [[SSD]], [[consumer]], [[China]], [[Korea]], [[pricing]], [[$MU]], [[$SNDK]], [[$005930.KS]], [[$000660.KS]], [[$285A.T]], [[memory]], [[semiconductor]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-22
file-updated-at:: 2026-11-22

- ## YMTC markets ZhiTai SSDs in Korea: a threat to consumer NAND pricing?
	- **Source**: X post by Dawson Lee (@LiDaosen, "Silicon & Infra Alpha"), quoting Jukan (@jukan05), November 2026 (user-provided screenshot).
	- **What happened** (Jukan):
		- YMTC, China's NAND maker, has a booth at **G-Star**, Korea's biggest gaming show, promoting its **ZhiTai** consumer SSDs. Jukan says YMTC is "getting pretty aggressive with its marketing in Korea."
		- The booth banner reads "ZHITAI SSD 라인업: 더 나은 스토리지 경험을 위해" ("ZhiTai SSD lineup: for a better storage experience").
		- It shows the **TiPlus9100**, **TiPro9000** (with a detachable heatsink), **TiPlus7100s** and **Ti600s**. The last two are labeled PCIe 4.0 NVMe.
	- **Dawson Lee's thesis** (tagged \$MU and \$SNDK):
		- "the memory cartel cannot defend pricing power."
		- **Xtacking**, YMTC's process that bonds the logic wafer to the memory-array wafer, delivers "massive \$/TB cost advantages." Chinese capacity "is eviscerating incumbent consumer margins on Samsung's home turf, collapsing peak gross margin models."
		- "Gamers don't care about geopolitics; they buy the lowest \$/TB." As YMTC's supply "pushes into Korea and Asia, consumer NAND cash cows evaporate."
		- Fabs "relying on peak gross margins to justify 2x multiples will see their pricing power crack from the bottom up."

- ## What the repo already shows about YMTC
	- | Item | Data point | Source in the repo |
	  |---|---|---|
	  | Capacity | About **200K wafers per month**, about 15% of industry NAND capacity | [[2026-09-04-dram-feed-cxmt-share-break-and-lta-floor-arithmetic]] |
	  | Rank | Passed Kioxia to **No. 3 by shipment volume** in Q2 2026 | Same |
	  | Ambition | Told IPO investors it aims to be the **world's largest NAND supplier by end-2027** | Same |
	  | IPO | Parent CCSH filed a **¥33.3B (about \$4.9B)** STAR Market listing | Same |
	  | Expansion | Three new 100K-wafer-per-month fabs, the first 50K live in 2027. That is a 20% addition to industry capacity, but only **about 4% a year** over five years | Same |
	  | Cost per bit | Morgan Stanley: YMTC is competitive on headline layer counts, but **bits per wafer run about 20% below Western peers** | [[2026-06-03-china-memory-cxmt-ymtc-geopolitics]] |
	  | 2028 share | Morgan Stanley base case about **14%** of global NAND supply. An upside case of 24% would require looser US export controls | Same |
	  | Trade status | On the US **Entity List since late 2022** and the Pentagon's 1260H list. Neither bars selling memory into Western markets | Same |
	  | Consumer channel | A YMTC SSD has already appeared in a branded **Lenovo ThinkBook**, with weak random-read (4K) performance | [[2026-07-03-notebookcheck-ymtc-ssd-lenovo-thinkbook]] |
	- **The cost claim is unproven**: the repo has no evidence that Xtacking gives YMTC a "massive" cost-per-TB lead. Morgan Stanley's bits-per-wafer estimate points the other way. A lower retail price could instead come from pricing strategy, state support or lower margin targets.

- ## How exposed the incumbents are to consumer NAND
	- | Company | Consumer exposure (latest repo data) | Memo's reading |
	  |---|---|---|
	  | **Micron** | Data-center SSDs are nearly \$10B, **over two-thirds** of FQ4-26 NAND revenue of \$14.1B. All NAND is 26% of revenue ([[MU-2026-Q3]]) | Memo calculation: non-data-center NAND (client SSD, mobile, auto and so on) is at most about **\$4.1B, about 8% of revenue**. Retail gaming SSDs are a fraction of that |
	  | **SK hynix** | SSDs about **78%** of NAND revenue in Q3 2026 (read from the chart), mostly enterprise including Solidigm. Mobile about 15%, USB, card and other about 7% ([[SKHY-2026-Q3]]) | It is moving NAND bits toward 321-layer **enterprise** SSDs and even let NAND shipments fall in Q3 to do so |
	  | **Samsung** | Large retail SSD brand, and Korea is its home market | **Most exposed to the "home turf" point**, but NAND is a small part of a conglomerate |
	  | **SanDisk** | Consumer and retail brands (cards, USB, client SSDs) are a larger part of the mix than at Micron or SK hynix | **Most exposed among pure plays** to price-driven competition in consumer channels |
	  | **Kioxia** | Partner of SanDisk on NAND manufacturing | Exposed through shared wafer economics |

- ## The case against the thesis (memo's reading)
	- **The shortage pulls YMTC in rather than pushing incumbents out**:
		- Incumbents are steering scarce NAND bits to enterprise SSDs for AI. SK hynix cut Q3 NAND bits to focus on high-value eSSD. Micron expects its 2026 NAND supply to grow less than the industry's. Both say NAND stays supply-constrained in 2027.
		- That leaves the consumer channel underserved, and YMTC fills it, the same pattern as the Lenovo ThinkBook case.
		- A booth at a gaming show is marketing, not evidence of falling prices. The post cites no price data.
	- **Retail gaming SSDs are the least important slice**: they are the most price-sensitive and lowest-margin part of NAND. The incumbents' NAND margins now come mainly from **AI data-center SSDs** used for KV-cache offload and replacing hard drives. Western hyperscalers are unlikely to qualify Entity-List NAND for those.
	- **YMTC's expansion is gradual**: about 4% of industry capacity a year, and limited by equipment controls.
	- **Where the thesis has force**:
		- NAND is more prone to oversupply than DRAM. Bits per wafer still rise about 56% every 18 months without new lines ([[2026-08-24-dram-feed-nand-price-vs-volume-hbm4-yield-convergence]]).
		- YMTC is the player most likely to break industry production discipline ([[2026-06-25-ai-semiconductor-endgame-2026-part-2-memory-cycle]]).
		- **When the shortage eases**, a YMTC already established in Korean and Asian retail would cap consumer prices first. The pressure would hit SanDisk and Samsung before Micron and SK hynix.
	- **Unverified**: the post's "2x multiples" and "collapsing peak gross margin models" are assertions without supporting figures.

- ## Related in the repo
	- **China's memory capacity and export controls**: [[2026-06-03-china-memory-cxmt-ymtc-geopolitics]], [[2026-06-05-cxmt-korea-china-hbm-gap-narrows-three-years]].
	- **Earlier memory-pricing debates**: [[2026-07-21-memory-positioning-bull-bear-debate]], [[2026-11-20-dram-commodity-vs-cpu-gpu-custom-hbm4-switching-friction]].
	- **Index-level view**: [[DRAM-memory-ssd-index-thesis]].
