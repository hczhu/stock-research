- tags:: [[$2454.TW]], [[Terafab]], [[Intel 14A]], [[AI ASIC]], [[Advanced Packaging]], [[SpaceX]], [[$TSLA]], [[semiconductor]]
  file-created-at:: 2026-05-31

- ## MediaTek 可能成为 Terafab 战略 ASIC 伙伴
	- **来源上下文**:
		- 本 memo 基于用户提供的一篇英文行业观点整理为中文。
		- 原文核心依据是“latest industry checks”，不是公司正式披露。
		- 文中关于 `Terafab`、`Musk in-house IC design team`、`Intel 14A`、`MediaTek + Google TPU` 的判断，应视为产业链观点和情景分析。

- ## 核心结论
	- 原文认为，`MediaTek` 相比其他 custom ASIC vendor，更有机会成为 `Terafab` 的战略合作伙伴。
	- 合作范围可能覆盖 `Intel 14A` 导入、先进封装整合、后续生产 ramp，以及为 Musk 内部 IC 设计团队所需芯片提供小批量制造支持。
	- 小批量制造目标时间是 `2028`，这与 Intel 14A 的早期量产窗口高度相关。
	- `Terafab` 的关键问题不是长期叙事，而是多重压力叠加下的执行确定性：范围太大、时间太紧、团队规模相对不足。
	- `MediaTek` 的优势在于：已有 Intel 生态经验、Google TPU 合作执行超预期、与 SpaceX / Starlink 有既有商业关系，并且可以把台湾半导体快速 R&D 生态带入项目。

- ## 关键数据点表
	| 主题 | 数据点 | 数值 / 时间 | 含义 |
	| --- | --- | --- | --- |
	| 合作目标 | Terafab 所需芯片小批量制造 | `2028` 开始 | MediaTek 若参与，需要帮助 Terafab 赶上 Intel 14A 早期生产窗口。 |
	| Intel 14A 时间点 | Intel 14A `PDK 0.9` 外部客户发布时间 | `2026 年 10 月` | 这是外部客户第一次真正开始 14A 设计工作的关键窗口。 |
	| Intel 14A 生产窗口 | Intel 14A 小批量生产 | `2028` | 如果错过 2026 年 10 月后的几个月窗口，Terafab 可能错过 2028 pilot production。 |
	| 设计周期压力 | Terafab 目标设计周期 | `9 个月` | 明显短于行业常规。 |
	| 行业常规设计周期 | 普通设计周期 | `18-24 个月` | Terafab 芯片迭代节奏约为行业常规的一半。 |
	| 复杂设计周期 | 复杂 IC 设计周期 | `2-3 年` | 对比 Terafab 的 9 个月目标，时间压力非常高。 |
	| 先进节点合作范围 | 并行先进节点合作对象 | `TSMC + Samsung + Intel` 三条线 | 原文认为这种组合在 IC design industry 没有先例。 |
	| 产品线范围 | 计算芯片产品线 | `2 条` | 地面芯片，面向 edge / inference；以及面向太空环境优化的芯片。 |
	| 项目数量 | 芯片项目数 | `6+` | 包括 AI series、Dojo series、SpaceX-specific chips。 |
	| 垂直整合范围 | 关键流程 | `4 个` | Photomask design、logic、memory、advanced packaging 在单一 site 内整合。 |
	| 团队规模对比 | Apple SEG vs SpaceX + Tesla chip teams | Apple SEG 大 `数倍到数十倍` | Terafab 团队更小，却要覆盖更宽范围、更紧时间表。 |
	| MediaTek Intel 经验 | Intel front-end 经验 | `Intel 16` | 证明 MediaTek 已有 Intel 制程生态接触经验。 |
	| MediaTek 封装经验 | Intel advanced packaging | `EMIB-T` | 与 Terafab 未来需要的 Intel advanced packaging ecosystem 相关。 |
	| Google TPU 合作 | TPU `8t` | `4Q26` 量产 | 原文称 MediaTek 与 Google 第一代 TPU 合作包含 8t。 |
	| Google TPU 合作 | `Humufish` | `2H27`，进度超预期 | 证明 MediaTek 有持续承接 Google TPU 后续项目的能力。 |
	| 合作模式能力 | Semi-COT collaboration | 已验证 | 对 Terafab 这种自研团队 + 外部 ASIC vendor 的模式有直接借鉴意义。 |
	| 生产协调能力 | EMIB-T production coordination | 已验证 | 直接映射到 Terafab 的先进封装整合需求。 |
	| 量产能力 | Tier-1 high-volume manufacturing | 已验证 | 对后续 production ramp 有价值。 |
	| SpaceX 关系 | Starlink user terminal 供应 | `MT7629`、`MT7762 / 61` Wi-Fi / router SoCs | MediaTek 已是 SpaceX / Starlink 合格供应商，有助于缩短合作 ramp。 |
	| 台湾 R&D 生态 | TSMC Night Hawk model | `24/7` shift-based R&D | 原文认为 MediaTek 可以作为 Terafab 接入台湾加速研发生态的通道。 |

- ## Terafab 的三类执行压力
	- **压力一：Scope 太大**
		- Terafab 需要同时处理 `TSMC`、`Samsung`、`Intel` 三条先进节点合作线，原文认为这种组合在 IC 设计行业没有先例。
		- 产品线至少包含两类：地面芯片，面向 edge / inference；以及为太空环境优化的芯片。
		- 项目范围超过 `6+` 个芯片项目，包括 AI series、Dojo series 和 SpaceX-specific chips，横跨多个应用领域。
		- Terafab 还试图在单一 site 内垂直整合 `photomask design`、`logic`、`memory`、`advanced packaging` 四个关键流程，规模和复杂度都没有先例。
		- 目标设计周期只有 `9 个月`，而行业常规是 `18-24 个月`，复杂设计通常需要 `2-3 年`。
	- **压力二：Time 太紧**
		- Terafab 将运行在 `Intel 14A` 上，而外部客户要到 `2026 年 10 月` 的 `PDK 0.9` 发布后，才有第一次真正参与 14A 设计工作的窗口。
		- 如果 Terafab 没抓住这个窗口，就可能错过 Intel 14A 在 `2028` 的小批量生产，进而影响自身 `2028 pilot production` 目标。
		- 原文行业检查还显示，Terafab 正在向设备供应商给出明显高于市场价的价格以锁定关键设备，这进一步说明时间压力很大。
	- **压力三：Headcount 不足**
		- 原文将 Terafab 团队与 Apple Silicon Engineering Group 对比，指出 Apple SEG 作为顶级 IC design team，规模是 SpaceX 与 Tesla chip teams 合计的数倍到数十倍。
		- Terafab 团队更小，却要覆盖更大 scope，并承受更紧时间表，外部合作伙伴的重要性因此上升。

- ## 为什么 MediaTek 是最匹配的合作方
	- **Intel 生态实战经验**
		- MediaTek 已有 `Intel 16` front-end 经验，也直接参与过 `EMIB-T` 先进封装。
		- 这种经验有助于 Terafab 抓住 `Intel 14A PDK 0.9` 发布后的关键几个月窗口，并支持后续制造 ramp。
	- **Google TPU 合作验证了执行能力**
		- MediaTek 与 Google 的 TPU 合作包含 `8t`，计划在 `4Q26` 量产。
		- 后续项目 `Humufish` 目标时间是 `2H27`，且原文称开发进度超预期。
		- 这些项目证明了三类能力：`Semi-COT` 合作模式经验、`EMIB-T` 生产协调能力、Tier-1 高量产制造能力。
		- 这三类能力都直接对应 Terafab 的需求。
	- **与 SpaceX 已有信任和商业关系**
		- MediaTek 已经为 Starlink user terminals 供应 `MT7629` 和 `MT7762 / 61` 系列 Wi-Fi / router SoCs。
		- 在 Terafab 时间表紧张的情况下，选择已经合格的供应商，可以降低导入摩擦并加速合作 ramp。

- ## 台湾 R&D 生态是 MediaTek 的结构性加分项
	- 原文认为，MediaTek 对 Terafab 的价值不只是公司自身能力，还包括它可以作为 Terafab 接入台湾半导体加速 R&D 生态的通道。
	- TSMC 的 `Night Hawk` 模式是一种 `24/7` shift-based R&D 机制，是其执行速度的重要来源之一。
	- 韩国部分政治人物和半导体产业人士也曾引用台湾模式，呼吁修改劳动法规以提升 R&D 竞争力，这说明台湾模式在区域竞争中被视为效率标杆。
	- Apple 供应链已经利用过这种优势：一家美国上游材料供应商在台湾设立实验室，并采用 Night Hawk 模式来满足 Apple 新品开发节奏，结果得到 Apple 认可。
	- 如果 Terafab 与 MediaTek 合作，并结合美国与台湾跨时区 R&D handoff，Terafab 的执行效率可能显著改善。

- ## 投资含义
	- 对 `MediaTek`：
		- 若成为 Terafab 战略伙伴，MediaTek 的定位会从传统 mobile / connectivity / ASIC supplier 上升到 AI ASIC ecosystem enabler。
		- Intel 14A、EMIB-T、Google TPU、Starlink 关系叠加，可以提升市场对 MediaTek AI ASIC 价值量和议价能力的认知。
	- 对 `Intel`：
		- Terafab 如果采用 Intel 14A 并在 2028 推进小批量生产，会提升 14A 外部客户生态的战略意义。
		- 但这也要求 Intel 在 PDK、良率、advanced packaging 和 customer support 上按时兑现。
	- 对 `Terafab / Musk 体系`：
		- 最大风险不是愿景，而是执行。
		- 在多节点、多产品线、多流程垂直整合、超短设计周期和小团队约束下，选择合适的 custom ASIC partner 可能是项目成败关键。
	- 对 `TSMC / Samsung / 其他 ASIC vendor`：
		- 如果 MediaTek 成为 Intel 14A / Terafab 的核心桥梁，custom ASIC vendor 的竞争将不只是设计能力，也包括先进制程生态经验、封装协调能力、量产 ramp 能力和既有客户信任。

- ## 风险与待验证点
	- Terafab 与 MediaTek 的合作尚未被公司正式确认。
	- Intel 14A `PDK 0.9`、2028 小批量生产、良率和封装生态是否如期推进仍是关键变量。
	- MediaTek 与 Google TPU 的合作进度、量产质量和经济性需要后续验证。
	- Terafab 是否真的需要同时推进 `TSMC + Samsung + Intel` 三条先进节点合作线，以及是否能在 9 个月设计周期下完成复杂 ASIC，需要持续跟踪。
	- 台湾 `Night Hawk` 式 R&D 机制能否被 Terafab 有效吸收，取决于组织接口、IP 安全、跨时区协作和供应链协调能力。

- ## Memo 结论
	- 这篇文章的核心判断是：Terafab 的主要瓶颈是执行，而不是愿景。
	- MediaTek 之所以可能成为最强匹配方，是因为它同时具备 Intel 制程 / 封装经验、Google TPU Semi-COT 执行案例、Tier-1 量产经验、SpaceX 既有供应关系，以及台湾加速 R&D 生态入口。
	- 如果合作落地，MediaTek 在 AI ASIC 市场的定位和 value-add 可能被明显重估。
	- 但该 thesis 的关键验证点仍是：Intel 14A 时间表、Terafab 2028 pilot production、MediaTek 是否真正获得战略 partner 角色，以及后续量产 ramp 的执行质量。
