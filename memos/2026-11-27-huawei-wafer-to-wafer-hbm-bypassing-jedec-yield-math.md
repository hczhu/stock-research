tags:: [[Huawei]], [[China]], [[HBM]], [[DRAM]], [[CXMT]], [[YMTC]], [[hybrid-bonding]], [[JEDEC]], [[EUV]], [[export-controls]], [[$000660.KS]], [[$005930.KS]], [[$MU]], [[$TSM]], [[ai-model:Opus5.5]], [[ai-effort:high]]
file-created-at:: 2026-11-27
file-updated-at:: 2026-11-27

- ## Huawei's wafer-to-wafer HBM: going wider to get around EUV, at a steep yield cost
	- **Source**: X post, November 26, 2026, about 37.4K views (user-provided text; author not shown). It comments on Huawei's reported non-JEDEC HBM approach, which the author calls Huawei's "Tau-style way around the EUV bottleneck."
	- **Thesis (the author's)**:
		- **The idea**: without EUV-class DRAM scaling or leading-edge foundry logic, Huawei can't push HBM **pin speeds** higher. So it is going **wider**, aiming for **HBM4-class bandwidth per stack at HBM3-class pin speeds**, using **wafer-to-wafer (W2W) hybrid bonding**, an area where China is strong.
		- **The catch**: W2W can't screen out defective dies before stacking, so **layer yields multiply**. That could multiply the DRAM wafers China needs per good stack.
		- **Strategically**: "Chinese and Western tech standards are gradually diverging, much like Soviet and Western standards did during the Cold War."

- ## Two routes to HBM bandwidth
	- | | Western HBM (SK hynix, Samsung, Micron) | Huawei's reported route |
	  |---|---|---|
	  | Standard | JEDEC HBM4 / HBM4E, plus custom base dies | **Bypasses JEDEC**, with its own interface |
	  | How bandwidth is raised | Higher **pin speeds** on a 2,048-bit interface | A **wider** interface at HBM3-class pin speeds |
	  | DRAM scaling | EUV-enabled nodes (1b, 1c) | Constrained without EUV |
	  | Logic base die | Leading-edge foundry, e.g. **TSMC 3nm** for custom HBM4E | No access to leading-edge foundry nodes |
	  | Stacking | Die-to-wafer (D2W) with known-good-die selection; MR-MUF, TC-NCF, moving toward hybrid bonding | **Wafer-to-wafer hybrid bonding**. YMTC already uses W2W in its Xtacking NAND |
	- See [[2026-11-20-dram-commodity-vs-cpu-gpu-custom-hbm4-switching-friction]] for why Western HBM4 base dies moved to foundry logic nodes to reach high pin speeds.

- ## The yield arithmetic
	- **W2W bonds whole wafers**, so a defect in any layer scraps the stack. Stack yield is the per-layer yield **y** raised to the number of layers. D2W tests dies first and stacks only known-good ones.
	- | Per-layer yield (y) | 5-layer stack yield (y⁵) | W2W wafers per good stack vs. D2W (1/y⁴) |
	  |---|---|---|
	  | 95% | **77%** | **1.23×** |
	  | 70% | **17%** | **4.16×** |
	- *Memo calculation*: both rows check. 0.95⁵ = 0.774, 0.70⁵ = 0.168, 1/0.95⁴ = 1.23 and 1/0.70⁴ = 4.16.
		- The 1/y⁴ ratio comes from D2W needing about 5/y wafers per good stack while W2W needs 5/y⁵.
		- This ignores bonding losses in D2W, assumes perfect known-good-die testing, and assumes equal die area.
	- **The author's worst case**: at 70% per layer, China would need **more than 4×** SK hynix's DRAM wafers per HBM stack. Matching US AI accelerator shipments would then take more than 4× the combined DRAM capacity of South Korea and Micron.
	- **Taller stacks** (memo calculation): the post uses five layers. Western HBM runs **12–16** layers, and losses compound with height.
		- At 95% per layer, a 12-layer W2W stack yields about **54%** and needs about **1.76×** D2W's wafers.
		- At 90% per layer, it yields about **28%** and needs about **3.2×**.
		- A wider, shorter stack helps Huawei, which may be part of the design choice.

- ## Context in the repo
	- **China's DRAM wafers are already scarce**:
		- Morgan Stanley put CXMT's bits per wafer at roughly **one-third** of Western levels. It said China's HBM contribution "should be modelled conservatively, if at all" ([[2026-06-03-china-memory-cxmt-ymtc-geopolitics]]).
		- A W2W yield penalty stacks on top of that density gap.
	- **CXMT's HBM roadmap**: CXMT targeted 12-high HBM3E by 2027, which would let Huawei source domestically ([[2026-04-09-cxmt-china-hbm-mass-production]], [[2026-06-05-cxmt-korea-china-hbm-gap-narrows-three-years]]).
	- **Huawei's accelerators**: Huawei's Ascend 950 inference economics are covered in [[2026-11-18-huawei-ascend-950dt-inference-economics-vs-h200]]. Epoch AI put Huawei at about 3% of AI compute shipped in Q2 2026 ([[2026-11-20-epoch-ai-chip-sales-nvidia-vs-google-tpu-2026q2]]).
	- **Western standards**: JEDEC relaxed HBM's height limit to avoid forcing a costly move to hybrid bonding ([[2026-06-05-memory-de-commoditization-permanent-plateau-geninnov]]). Western vendors are adopting hybrid bonding cautiously, while China appears to be using W2W first, out of necessity.

- ## Memo's reading
	- **For Western memory makers**:
		- If W2W yields are poor, China's HBM drains wafers, which limits how much Huawei can build and keeps China's memory makers busy supplying the home market.
		- If yields are good, as with YMTC's mature W2W process in NAND, China gains a credible HBM4-class path without EUV. That would narrow the export-control moat on HBM.
		- Either way, a separate Chinese standard reduces the chance that Chinese HBM competes in Western markets.
	- **For export controls**: this is the second sign this week of China engineering around chokepoints rather than through them, after YMTC's consumer SSD push ([[2026-11-22-ymtc-zhitai-ssd-korea-g-star-consumer-nand-pricing]]). Controls that slow node scaling push China toward **architectural workarounds**: wider interfaces, wafer bonding and its own standards.
	- **Caveats**:
		- The post gives no actual Huawei yield, layer count or bandwidth figures.
		- The 95% and 70% yields are the author's illustrations.
		- "Tau-style" is the author's label and isn't explained in the excerpt.
