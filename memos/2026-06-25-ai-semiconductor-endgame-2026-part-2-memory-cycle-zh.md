- tags:: [[AI]], [[semiconductor]], [[HBM]], [[DRAM]], [[NAND]], [[SSD]], [[inference]], [[agents]], [[AI infrastructure]], [[CXMT]], [[YMTC]], [[super-cycle]]

- ## AI 半导体终局推演 2026 (II): HBM / DRAM / SSD 能否摆脱传统周期
	- **Source**: 用户提供的中文文章文本《AI半导体终局推演2026(II)》
	- **核心问题**:
		- `HBM / DRAM / SSD` 会不会摆脱传统内存周期性？
		- 依赖 `HBM size x HBM bandwidth` 指数增长的 GPU 推理架构路线会不会停止？
		- 长鑫扩产会不会把 DRAM 重新带回传统周期泥潭？
	- **核心结论**:
		- HBM 已经满足“去传统周期化”的大部分条件，可能从传统周期变成“成长周期性”。
		- DRAM 的去周期化市场共识更低，但 `agentic CPU` 正在把 server DRAM 变成新的结构性指数需求来源。
		- NAND SSD 的结构性需求不如 HBM / DRAM 刚性，但受益于 KV cache offloading、AI 视频、agent sandbox、未来 HBF，至少本轮也更像超级周期。
		- 这不是 HBM、DRAM、NAND 三个独立故事，而是同一个 AI memory hierarchy 在不同温度层的结构性增长。

- ## 判断内存能否摆脱传统周期的框架
	- 文章把传统内存周期的主要来源定义为: 扩产周期太长，供给无法快速调整，容易和需求周期错位。
	- `commodity` 属性本身不是周期的根源，而是振幅放大器: 标准化、可囤积、无差异化会放大价格战和囚徒困境。
	- 摆脱传统周期有三种路径，满足一条可部分摆脱，满足两到三条可摆脱大部分传统周期。

	| 条件 | 机制 | 对周期性的影响 |
	|---|---|---|
	| 定制化 | 产品不可完全互换，产能不能随便转移，客户需要签长约 | 降低库存和价格战风险 |
	| 结构性指数需求增长 | 需求曲线足够陡，供给长期追不上 | 把下行周期变浅、变短 |
	| 技术快速迭代 | 新一代快速淘汰上一代，旧货囤积价值下降 | 从数量竞争转向质量竞争 |

	- 按这个框架，文章认为 HBM 大概满足“两条半”: 定制化半条、结构性指数需求一条、技术快速迭代一条。

- ## HBM: 为什么更像成长周期性
	- **定制化只算半条**: HBM 有 NVIDIA co-design 和封装 / base die 定制成分，但 DRAM die 本身仍然高度 JEDEC 标准化。
	- Samsung HBM3E 没通过 NVIDIA qualification 后，份额从约 `60%` 跌到 `20%`，但产能没有报废，而是转供 Google TPU、AMD 等客户。这说明 HBM 仍有一定可转移性。
	- HBM4 之后定制化增强，base die 上可集成定制逻辑 / 缓存，甚至把 HBM4E 内存控制器和定制 die-to-die 接口放进 logic base die。
	- 文章提到 OpenAI、NVIDIA、AMD 都在做定制 HBM，但主要是 base die 定制，上面的 DRAM 层仍然标准化。

	| HBM 去周期化条件 | 是否满足 | 文章判断 |
	|---|---:|---|
	| 定制化 / 长约 | 半满足 | 封装和 base die 需要合作，推动长约；但 DRAM die 标准化，产能仍可转移 |
	| 结构性指数需求 | 满足 | token throughput 需要 HBM size 和 bandwidth 每代翻倍 |
	| 快速技术迭代 | 满足 | HBM 约两年一代，远快于传统 DDR |

	- **结构性需求来自 token factory**: 文章延续 Part I 的公式:
		- `token throughput = HBM size x HBM bandwidth`
	- HBM size per GPU 大约每年增长 `40%+`，这条需求曲线比 DRAM 供给端增长更陡。
	- 供给端粗略能力为 `14%` wafer 增长乘以 `9%` density 提升，很难追上 HBM / AI 推理需求。
	- 即使 HBM 涨价 `3-5x`，把钱花在 HBM 上带来的边际 token throughput 提升仍然比其他环节更划算。
	- SRAM、HBF、CXL、PIM 当前都无法在 HBM 的主战场 `KV cache / attention` 上正面替代，文章判断未来 `5 年甚至更长时间` 不太可能出现主替代路线。

- ## HBM 技术迭代: 从数量竞争到质量竞争
	- DDR3 到 DDR5 跨越约 `15 年`，而 HBM 基本约 `2 年一代`，且近期有加速趋势。
	- 文章给出的 NVIDIA GPU / HBM 带宽演进显示，HBM 速度和推理 token throughput 线性相关，旧 HBM 的边际使用成本会快速变差。

	| 维度 | DDR / 传统 DRAM | HBM |
	|---|---|---|
	| 代际节奏 | DDR3 到 DDR5 约 `15 年` | 约 `2 年一代` |
	| 性能价值 | 过去对 CPU performance 边际效用低 | 对 token throughput 近似线性重要 |
	| 旧产品价值 | 可较长时间消化 | HBM3 等旧代快速贬值 |
	| 厂商竞争方式 | 产能 / 份额竞争 | NVIDIA qualification、稳定性、带宽速度竞争 |

	| NVIDIA GPU / HBM 带宽路径 | 带宽 |
	|---|---:|
	| 早期节点 | `2TB/s` |
	| 后续节点 | `3.5TB/s` |
	| 后续节点 | `4.8TB/s` |
	| 后续节点 | `8TB/s` |
	| 未来节点 | `22TB/s` |

	- 文章认为技术升级越快，token factory 赚得越多，因此客户有动力尽量采用最新 HBM。
	- 旧产品快速贬值降低囤货价值，使 HBM 厂商理性选择从拼当前产能转向拼下一代 qualification 份额，减弱传统下行周期里“谁先减产谁吃亏”的囚徒困境。

- ## HBM 仍有周期，但更像“成长周期性”
	- 文章区分两种周期:
		- **传统周期性**: 上行周期赚得多，下行周期亏得多。
		- **成长周期性**: 上行周期赚得多，下行周期赚得少。
	- HBM 不能完全避免周期，因为供给周期、需求波动仍然存在。
	- 但只要 token 需求仍然指数增长，HBM 的需求可预测性更好；一旦降价，客户会增大 HBM size 来提高 token throughput。
	- HBM 长约和部分定制化也会把周期性转化为更长、更浅的成长周期。

- ## 供给端: DRAM density scaling 放慢，HBM 还会抽走更多 wafer
	- 文章认为 HBM / DRAM 还有第四个去周期化因素: 供给端扩产难度持续增加。
	- DRAM bit density 增长大幅放慢，导致过去“靠制程升级自然增加 bit supply”的时代结束。

	| 时间 | DRAM 每片 wafer bit density 年增长 | 含义 |
	|---|---:|---|
	| 2000 年附近 | `~45% / 年` | 不扩 wafer 也能大幅增加 bit supply |
	| 十年前 | `~20% / 年` | 仍可靠制程带来较高 bit growth |
	| 现在 | `~9% / 年` | 扩产更多依赖新厂房和 clean room |

	- HBM 堆叠倍数上升会进一步消耗 DRAM wafer。

	| 产品 | 等量 bit 所需 DRAM wafer | 供给含义 |
	|---|---:|---|
	| HBM3E | `~3x` DDR wafer | HBM bit 相对更难制造 |
	| HBM4 | `~4x` DDR wafer | HBM 扩产继续挤占 commodity DDR |

	- 文章把这称作 HBM 对 DDR 的 “bit tax”: 每年约 `3-5%` 的 DDR bit 增长会被 HBM 转换吃掉。

- ## GPU / HBM 架构路线会不会停止
	- 问题本质不是 HBM 本身，而是 Transformer attention 和 KV cache 机制会不会消失。
	- 文章认为，AI 模型架构革命后真正被保留下来的，是数学上具有普适性的 primitive 操作。
	- FFN / MLP 从 2012 年深度学习时代一路保留到 LLM，因为它对应 universal approximation theorem。
	- Attention 解决的是 sequence 中任意两个位置之间的 dynamic routing，让任意位置能按需建立联系。这种能力一旦验证有效，很难被完全丢弃。
	- 因此即便未来从纯 Transformer 走向混合架构或世界模型，attention 层大概率仍会存在，KV cache 或 latent-compressed equivalent 仍会需要。
	- 结论: 依赖 HBM 指数增长的 GPU KV cache 架构路线不会很快停止，HBM 仍是推理核心之一。

- ## DRAM: 市场低共识的去周期化可能
	- HBM 去周期化市场已有一定共识，但 DRAM 去周期化共识很低。
	- DRAM 没有明显定制化，因此关键要看结构性指数需求和技术迭代边际效用。
	- 文章认为 `2025 年底之后` 发生变化: agentic CPU 开始释放潜力，CPU 附带的 DRAM 需求成为新的结构性指数增长来源。
	- DRAM 需求增长分两层:
		- CPU server TAM 快速增长。
		- 每个 CPU core 需要的 DRAM 因 agentic flow 快速上升。

- ## Agentic CPU 带来的 server DRAM 需求
	- CPU server TAM 增长的四个逻辑:
		- AI 加速器集群中 CPU:GPU 配比从传统 `1:4` 走向 `1:2`，甚至可能走向 `1:1`。
		- Agentic flow 中 CPU 处理延迟占比高，`50-90%` 成为重要瓶颈，需要同步扩容。
		- AI coding 提升 SDE 效率，代码量和软件 API 调用指数增长，转化为 CPU hours 上升。
		- Sandbox 为数据安全和隔离复制数据库 / 用户上下文，造成 DRAM 和 CPU core 浪费，且五年甚至更久难以优化。

	| 时间 / 来源 | 2030 CPU TAM 预测 | 文章解读 |
	|---|---:|---|
	| AMD 上上季度财报 | `\$60B` | 旧基准 |
	| AMD / ARM 两个月前 | `\$120B` | 预测翻倍 |
	| NVIDIA 一个月前 | `\$200B` | 再次上修 |
	| Bernstein 上周 | `\$223B` | 继续上修 |
	| 作者判断 | `2031E \$400B` | 未来大概率继续上修 |

	- 每个 CPU core 的 DRAM 配比上升来自两个机制:
		- Agent 是带状态的长驻进程，不是 stateless request-response；任务可运行一分钟到一小时，message history、system prompt、工作记忆、长期记忆、tool result buffer 都常驻 DRAM。
		- Context window 从 `32K -> 256K -> 1M`，reasoning / test-time compute 序列长度增长，每个活跃会话常驻 messages 随 context 长度线性增长。

	| 变量 | 旧世界 / 当前 | Agentic 时代 |
	|---|---:|---:|
	| CPU server TAM | `\$60B` 旧预测 | `\$120B -> \$200B -> \$223B`，作者认为可到 `\$400B` |
	| 每 core DRAM 配比 | `4-8GB/core` | `16-32GB/core` |
	| 增长性质 | 传统 server growth | CPU TAM 扩张 x DRAM/core 一次性重估 |

	- 文章测算: 2030 年即便按保守 `\$300B` CPU TAM、`\$50/core`、`16GB/core`，新增 DRAM 需求至少 `96EB`。
	- 对比供给: 今年 DRAM 总产量约 `47EB`，明年勉强 `60EB`。

- ## DRAM 供需缺口和 bit growth
	- 文章认为非 HBM 的传统 DRAM 供给端大约每年增长 `20%`。
	- 需求端仅 agentic CPU 相关 DRAM，按文章参数可从 `16EB` 增至 `80EB`，CAGR 约 `50%`，显著高于供给增长。

	| 项目 | 2026E / 当前 | 2030E / 未来 | 隐含变化 |
	|---|---:|---:|---:|
	| CPU TAM 假设 | `\$60B` | `\$400B` | `~6.7x` |
	| DRAM/core 假设 | `8GB/core` | `16GB/core` | `2x` |
	| CPU 单 core 价格假设 | `\$30-35/core` | `\$80/core` | `>2x` |
	| Agentic CPU DRAM 需求 | `16EB` | `80EB` | `~50% CAGR` |
	| 传统非 HBM DRAM supply growth | — | — | `~20% / 年` |

	- 文章强调: DRAM 不像 HBM 直接绑定 GPU 赚钱效率，因此需求刚性弱一些；DRAM 不够主要影响 agent flow 速度，某些低价值任务可以等待。
	- 但结构性指数需求依然很强。Semianalysis 口径下今年 DRAM 缺口为个位数百分比，明年超过 `10%`；文章认为到 2030 年前缺口看不到缓解。

- ## DDR / LPDDR 技术迭代边际效用上升
	- 过去 DDR 技术迭代依赖消费电子，性能边际效用低，新一代出来后客户经常等降价再用。
	- 未来碳基消费电子 DRAM 用量会远小于硅基消费，即 CPU server DRAM。
	- CPU server 对 memory 的需求上升、端侧 AI 对 DDR / LPDDR 速度要求上升，使 DDR6 / LPDDR6 的边际效用显著提高。
	- 苹果为了跑本地大模型，LPDDR 速度和容量要求都在提高；最新端侧 AI 满血版内存要求从 `8GB` 升到 `12GB`。
	- 文章认为 LPDDR6 / DDR6 的迭代时间缩短、速度斜率重新抬头，客户对新一代内存的态度从“等降价”变为“尽量早上”。

- ## 长鑫扩产: 影响有，但不足以打破本轮 DRAM 结构性短缺
	- 长鑫扩产速度很快，但文章认为其 bit density 约只有御三家一半，因此需要按等效产能折半看。

	| 厂商 / 区域 | 2025E 月产能 | 2028E 月产能 | CAGR |
	|---|---:|---:|---:|
	| Samsung | `685K wspm` | `920K wspm` | `10.3%` |
	| SK Hynix | `519K wspm` | `725K wspm` | `11.8%` |
	| Micron | `340K wspm` | `560K wspm` | `18.1%` |
	| 非中国其他 | `150K wspm` | `218K wspm` | `13.3%` |
	| 中国（密度折半） | `117K wspm` | `274K wspm` | `32.8%` |
	| 含中国总计 | `1,811K wspm` | `2,697K wspm` | `14.2%` |
	| 无中国总计 | `1,694K wspm` | `2,423K wspm` | `12.7%` |

	| 长鑫节点 | 月产能 / 新增 | 时间 |
	|---|---:|---|
	| 现有 / 2025 | `~20 万片 / 月` | `2025` |
	| 北京厂及新增线 | `32-35 万片 / 月` | `2026` |
	| 上海一期 | `+10 万片 / 月` | `2027` |
	| 上海二期 | `+10 万片 / 月` | `2028` |
	| 名义目标 | `~50 万片 / 月` | `2028` |
	| 按 density 折半等效 | `~25 万片 / 月` | `2028` |

	- 折半后，长鑫从 2025 年底到 2028 年底对全行业 DRAM bit 产能 CAGR 的影响约 `+1.5pct`，把全行业 CAGR 从 `12.7%` 拉到 `14.2%`。
	- 即便长鑫继续增产，到 2030 年对全行业等效 bit volume CAGR 的影响也不到 `3pct`，例如从 `20%` CAGR 变成 `23%` CAGR。
	- 光刻机限制也是长期约束。DDR6 需要 `14400 MT/s` 起步、更高密度，御三家大概率用 `1c` 或更先进节点（约 `12nm` 以下）并全面用 EUV；长鑫在 DDR6 上可能速率受限且密度只有一半。

- ## 为什么 DRAM 超级周期可能至少持续五年
	- 第一，agentic CPU 带来的 server DRAM 需求增速远高于供给 bit growth。
	- 第二，DRAM 涨价消灭的需求不是永久消失，而是延迟，形成很厚的需求蓄水池。
	- 第三，HBM 和 DRAM 产能可互相转换，整个 DRAM complex 会一起 re-rate。
	- 第四，density scaling 放慢、扩产难度增加、厂商扩产谨慎、长鑫冲击有限。

	| 需求蓄水池 | 机制 | 内存降价后的释放方式 |
	|---|---|---|
	| 内存换算力 / 速度 | 额外内存可优化速度和算力，贵时被压制 | 降价后重新采用类似 CPX prefill 加速方案 |
	| 低价值 task | 高 token 成本下低价值任务被延后 | 降价后低价值任务恢复 |
	| 端侧 AI | AI PC / 手机本地模型需要更高内存 | AI PC 可能从 `24GB` 升到 `128GB`；苹果端侧 AI 从 `8GB` 到 `12GB` |
	| 常规消费电子 / Agent PC / 低端手机 | 涨价时减少配置或推迟换机 | 降价后补库存 / 升配置 |

	- CPX prefill 加速原本使用低成本 GDDR7 做专门 prefill accelerator，但 LPDDR / GDDR 太贵后 ROI 不划算；等普通内存降价，类似方案可能回归。
	- HBM 长约透明性使其利润率有保障；如果 DRAM 降价、毛利下滑，HBM 会间接抽走更多 DRAM 产能。
	- HBM 降价也会让 GPU 厂商更愿意升级 HBM size，进一步支撑 DRAM complex 的价格地板。
	- 文章结论: 可预见的至少五年甚至更长时间内，DRAM 很难进入传统周期低谷。

- ## NAND SSD: 结构性增长更分散，但本轮也像超级周期
	- NAND 的结构性增长动力不如 DDR 强。今年缺货主要来自主要玩家保持生产纪律，没有大规模扩产；产能增加主要来自 NAND 堆叠层数提升。
	- 文章列出四个结构性增长来源。

	| NAND / SSD 结构性需求来源 | 机制 | 时间判断 / 备注 |
	|---|---|---|
	| KV cache offloading | 把 HBM 溢出的 warm / cold KV cache 卸载到 NAND SSD | 还没大规模发生，SSD 已经比 DRAM 更缺；Rubin CMX 放量后会更明显 |
	| AI 视频 | Seedance 等视频生成体量快速增长 | 体量以每年 `10-40x` 增长，当前仍被算力不足压制 |
	| Agent sandbox | 每个任务复制数据库和用户上下文 | 同时浪费 CPU、DRAM、SSD，带来存储需求 |
	| HBF | 用 flash 存放大模型 weights，写一次、只读 | 可能 2030 年后更重要；需和 GPU / HBM 封装在一起，否则 PCIe 速度太慢 |

	- SSD 便宜是核心优势。文章称到 2027 年 SSD 价格约 `\$0.8/GB`，约为同期 DRAM 的 `1/40`。
	- 如果 DRAM / HBM 单独涨价而 SSD 不涨价，系统设计会尝试用 SSD 承载部分 warm / cold memory 功能，用低成本实现类似效果。
	- NAND 能否真正摆脱传统周期，取决于生产纪律。潜在破坏者是长存，因为 NAND 扩产难度比 DRAM 更简单，一旦有玩家激进扩产，囚徒困境会重新出现。
	- 文章判断: 即便不彻底去周期化，本轮 NAND 也属于超级周期，多个结构性需求足以把下行期推迟到 `2030` 左右。

- ## 投资含义
	- **HBM**: 最强。它满足两条半去周期化条件，并直接绑定 GPU token throughput，价格上涨仍可能被客户接受。
	- **DRAM**: 市场低共识，但变化最大。Agentic CPU 把 server DRAM 从传统 commodity demand 推向结构性增长，DRAM 可能从传统周期变成较弱版本的成长周期。
	- **NAND / SSD**: 需求刚性弱于 HBM / DRAM，但应用面最宽、成本最低，是 AI memory hierarchy 的低温层万金油。
	- **中国供给冲击**: 长鑫对 DRAM 的新增影响需要按 bit density 折半看，短中期不足以抵消 agentic CPU + HBM bit tax 的结构性紧缺；长存对 NAND 的生产纪律更值得跟踪。
	- **最重要的跟踪变量**:
		- `HBM size x HBM bandwidth` 是否继续每代翻倍。
		- Agentic CPU TAM 是否继续被 AMD / ARM / NVIDIA / sell-side 上修。
		- `GB/core` 是否从 `4-8GB` 迁移到 `16-32GB`。
		- HBM bit tax 是否持续吃掉 `3-5%` 的 commodity DDR bit growth。
		- 长鑫 / 长存是否突破设备限制并改变行业生产纪律。

- ## 需要保留的核心数据点
	| 类别 | 数据点 |
	|---|---|
	| HBM 定制化 | Samsung HBM3E NVIDIA 份额从约 `60%` 跌到 `20%` 后可转供 Google TPU / AMD |
	| HBM demand | HBM size per GPU 每年增长 `40%+` |
	| DRAM supply | wafer 增长约 `14%`，density 提升约 `9%` |
	| DRAM density | 2000 年附近 `45% / 年`，十年前 `20% / 年`，现在 `9% / 年` |
	| HBM wafer tax | HBM3E 约 `3x` DDR wafer，HBM4 约 `4x` DDR wafer |
	| DDR bit tax | 每年约 `3-5%` DDR bit growth 被 HBM 吃掉 |
	| 非 HBM DRAM growth | 传统 commodity DDR bit growth 约 `20% / 年` |
	| CPU latency bottleneck | Agentic flow 中 CPU 延迟占比 `50-90%` |
	| CPU TAM | `\$60B -> \$120B -> \$200B -> \$223B`，作者认为 2031 可到 `\$400B` |
	| DRAM/core | `4-8GB/core -> 16-32GB/core` |
	| DRAM total production | 今年约 `47EB`，明年约 `60EB` |
	| Conservative agent CPU DRAM addition | 2030 年按 `\$300B` CPU TAM、`\$50/core`、`16GB/core`，新增至少 `96EB` |
	| Agentic CPU DRAM demand | `16EB` 到 `80EB`，约 `50% CAGR` |
	| CXMT impact | 等效后把行业产能 CAGR 从 `12.7%` 提高到 `14.2%` |
	| DDR6 hurdle | `14400 MT/s` 起步，御三家大概率 1c 或更先进节点 / EUV |
	| AI PC memory | 可能从 `24GB` 到 `128GB` |
	| Apple edge AI | 满血版端侧 AI 内存要求从 `8GB` 到 `12GB` |
	| Seedance growth | AI 视频体量每年 `10-40x` 增长 |
	| SSD cost | 2027 年约 `\$0.8/GB`，约为同期 DRAM 的 `1/40` |

- ## Caveats
	- 这是一篇 thesis-driven 文章，不是审计过的行业报告；多个数据点来自作者框架和行业判断。
	- 部分测算依赖 CPU TAM、core 单价、GB/core、agentic workload 形态等假设，敏感性很高。
	- HBM / DRAM 去周期化不等于没有周期，而是周期形态可能从“亏损周期”变成“盈利波动周期”。
	- NAND 的结论最依赖厂商生产纪律，尤其需要持续观察长存是否激进扩产。
