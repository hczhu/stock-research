- tags:: [[$NVDA]], [[Groq]], [[SRAM]], [[HBM]], [[inference]], [[Heterogeneous Inference]], [[GTC 2026]]
  file-created-at:: 2026-05-31

- ## GTC 2026 预览：从 Groq 生态位看 AI 异构推理新时代
	- **来源上下文**:
		- 本 memo 基于用户提供的一篇中文观点整理。
		- 原文包含大量技术推演和商业判断，尤其是关于 `Nvidia 收购 Groq`、`GTC 2026`、`CPX / LPU / ICMS / CMX` 的部分，应视为情景分析和投资框架，不是公司正式披露。
		- 核心问题是：`Groq` 的 SRAM / LPU 路线在 AI 推理体系中的真实生态位是什么，是否会替代 HBM GPU，以及如果并入 Nvidia 系统后会怎样改变推理架构。

- ## 核心结论
	- `Groq` 本质不是 `SRAM first`，而是 `compiler first`：它的核心是完全确定性编译器，将 AI 推理中可预测的计算、访存和通信尽量全部前移到编译期。
	- `SRAM-only` 是确定性编译路线的结果，而不是起点；因为 cache / DRAM / HBM 的运行时不确定性会破坏 cycle-accurate 调度。
	- Groq 的确定性编译器路线很难直接套进 Nvidia 现有 `GPU + HBM + SIMT` 体系，因为 HBM/DRAM 延迟天然不确定，而 Nvidia GPU 的核心设计是用 warp switching 隐藏这种不确定性。
	- 因此，Groq 在 Nvidia 体系内更可能成为独立的低延迟 decode 专用产品，而不是被融合进现有 GPU 架构。
	- Nvidia 能给 Groq 带来的主要提升，可能不是简单的软件整合，而是通过先进工艺、hybrid bonding、3D SRAM 等方式扩大 LPU SRAM 容量，减少 scale-out 卡数和 pipeline stage，从而降低 interconnect latency。
	- SRAM 不会颠覆 HBM。SRAM 路线本质是用显著更高成本换更低延迟，只适用于低 batch、低延迟、实时交互式推理市场；大规模 batch inference、offline processing、ranking / recommendation 仍以 HBM GPU 的 TCO 为核心。
	- 更大的投资含义是：推理 workload 正在分化，Nvidia 可能从“GPU 单点性能竞争”走向“数据中心即一台异构计算系统”的系统级编排，竞争门槛从“做出一颗好芯片”抬升到“定义并整合一整套异构推理系统”。

- ## 关键数据点表
	| 主题 | 数据点 | 数值 / 表述 | 投资含义 |
	| --- | --- | --- | --- |
	| Groq 架构哲学 | Instruction dispatch 面积占比 | `<3%` | Groq 将复杂度从硬件调度转移到静态 compiler，硬件本身极度简化。 |
	| SRAM 容量瓶颈 | 单张 Groq TSP 计算卡 SRAM | `230MB` | 在 CNN / LSTM 时代足够，但 LLM 参数和 KV cache 让 SRAM 容量成为核心限制。 |
	| LLM 模型规模对比 | LLaMA 70B 参数内存规模 | 约等于 `3000 个 ResNet50` | 说明 Groq 早期架构从 CNN 时代进入 LLM 时代后被迫大规模 scale out。 |
	| 70B 推理配置 | Groq 70B 推理集群 | `576 张卡` | SRAM 容量不足导致必须通过大量卡并行承载模型参数和 KV cache。 |
	| 70B 并行方式 | Pipeline parallelism / tensor parallelism | `16 个 PP x 36 个 TP` | 80 层模型切成 16 级流水，每级横向并行，通信复杂度很高。 |
	| Groq 延迟瓶颈 | PP / TP 通信延迟占比 | `>80%` 总延迟 | Decode 不再主要受 SRAM 带宽限制，而是受 interconnect latency 限制。 |
	| Pipeline 延迟占比 | PP 延迟占比 | `>50%` 总延迟 | 减少 pipeline stage 是提升 token speed 的关键路径之一。 |
	| 工艺升级潜力 | 14nm 到 3nm SRAM 容量提升 | `230MB -> 500MB` | 若由 Nvidia 推动先进工艺迁移，单 LPU SRAM 容量可显著提升。 |
	| 3D SRAM 潜力 | Hybrid bonding / 3D SRAM | 容量“还能翻倍” | 类似 AMD 3D V-Cache 的堆叠方式可能进一步缓解 SRAM 容量瓶颈。 |
	| 升级后集群规模 | 70B 推理所需 LPU 数量 | `576 -> 256` | SRAM 容量扩大后，scale-out 卡数下降，通信延迟可下降。 |
	| 升级后并行猜测 | 新并行结构 | `32 个 TP x 8 个 PP` | Pipeline stage 从 16 降到 8，原文推测 pipeline interconnect latency 可直接减半。 |
	| Groq 硬件成本 | Groq 计算卡零售价 | 约 `$20,000 / 颗` | 如果按 retail 算，SRAM 路线硬件成本远高于 HBM GPU 路线。 |
	| Groq 实际售价假设 | 原文保守假设 | `$2,000 / 颗` | 即使用低很多的实际售价估算，成本仍显著高。 |
	| 70B Groq 成本 | `576` 张卡硬件成本 | `>$1.1M` | 远高于 H100 路线，体现 SRAM 路线结构性成本劣势。 |
	| 70B H100 对比 | 运行同模型所需 H100 | `2 张 H100`，成本 `<$100K` | 同样模型下，H100 硬件成本低一个数量级。 |
	| Groq API 经济性 | 2025 年 LPU API 收入 | 约 `$40M` | 原文认为 Groq 低价 token 服务不是因为经济性更强，而是靠补贴。 |
	| Groq API 成本 | 2025 年业务成本 | 约 `$60M` | 对应毛利为负。 |
	| Groq API 毛利 | 毛利率 | `-50%` | 支持“SRAM token 便宜来自 VC 补贴，不是结构性成本优势”的论点。 |
	| 速度溢价案例 | Claude Opus 4.6 Fast 输出速度 | `2.5x` | 市场愿意为低延迟推理付费。 |
	| 速度溢价价格 | Claude Opus 4.6 Fast 定价变化 | 从 `$5 / $25` 提至 `$30 / $150` per million tokens | 价格约 `6x`，说明低延迟有真实 premium market。 |
	| 低延迟市场占比 | 某 hyperscaler 说法 | 约 `10%` | 原文认为这是 SRAM 路线可服务市场的一个粗略锚点。 |
	| Agentic workload 瓶颈 | CPU 在 E2E 延迟中的占比 | 最高可达 `90%` | 在 agentic flow 中，单次 decode 加速可能被 CPU / 工具调用 / orchestration 延迟稀释。 |
	| SRAM 物理成本 | SRAM cell vs DRAM cell | `6T SRAM` vs `1T1C DRAM` | SRAM 成本劣势由物理结构决定，长期不容易收敛。 |
	| SRAM scaling | N5 到 N3E | SRAM 单元面积“几乎没有缩小” | 工艺推进对 SRAM 成本和容量的改善慢于理想情况。 |
	| SRAM 带宽优势 | Groq SRAM 速度 | `80T/s` | 原文认为 SRAM 速度优势已不如早期显著。 |
	| HBM 对比 | Rubin HBM4 带宽 | `22TB/s` | SRAM 与 HBM 的速度差距已不到一个数量级，未来可能继续收窄。 |

- ## 论点一：Groq 是 compiler-first，不是 SRAM-first
	- **术语说明：什么是 `VLIW`**
		- `VLIW` 是 `Very Long Instruction Word` 的缩写。
		- 它是一种处理器设计思路：由编译器提前把多个可并行执行的操作打包进一条很宽的指令中，由硬件按这个静态计划并行执行。
		- 与 out-of-order 或 `SIMT` 这类更多依赖硬件在运行时做调度的架构不同，`VLIW` 将大量调度复杂度前移给编译器。
		- 这种设计的优点是硬件可以更简单、更高效；缺点是它更依赖 workload 的可预测性，如果运行时行为不规则，静态调度就更难做到高效。
		- 这也是为什么 `VLIW` 会反复出现在 `Groq` 讨论里：Groq 试图利用 AI 推理 workload 的高确定性，把并行执行计划尽量在编译期完成。
	- Groq 的基本设计前提是：AI 推理 workload 比传统 CPU workload 更 deterministic。
	- AI 推理通常具有更少的 data-dependent branching、更固定的 tensor shape、更确定的 memory access pattern。
	- 因此 Groq 重新回答了 hardware-software interface 的问题：哪些事情应该在编译时完成，哪些事情应该在运行时完成。
	- 对 AI 推理来说，Groq 的答案是“几乎一切都可以在编译时完成”。
	- 这导向了 fully deterministic compiler：编译器需要精确安排每个 clock cycle 里每个计算、访存、通信动作。
	- 为了实现这种 cycle-accurate 调度，硬件中所有运行时不确定性都需要被移除：
		- 不做乱序执行和 speculation。
		- 避免 runtime arbiter、crossbar、replay 等动态决策结构。
		- cache 替换成 software-controlled scratchpad SRAM。
		- 通信按编译器预先决定的时间表同步执行，而不是依赖传统 packet routing / buffer queuing。
	- 这也是 Groq 芯片间通信 overhead 低的原因之一：传统互联里的 packet routing、arbiter contention、buffer queuing 都是 latency jitter 的来源，而 Groq 用确定性时间表规避它们。
	- 所以 SRAM-only 不是 Groq 的第一性原理，而是 deterministic compiler 路线自然推出的硬件要求。

- ## 论点二：Groq 编译器路线很难直接并入 Nvidia GPU + HBM
	- 原文认为 Groq 的 deterministic compiler 很难直接用于 Nvidia 现有 GPU/HBM 体系，原因有两个。
	- 第一个原因是 HBM/DRAM 延迟天然不确定：
		- DRAM 需要周期性 refresh，refresh 会阻断 bank 访问，且频率会随温度变化。
		- Memory controller 为最大化带宽，会做实时 batch scheduling、page locality 优化、读写切换优化、bank 利用优化。
		- 系统级 bank address hashing 等机制让 compiler 很难在编译期静态定位数据并承诺 cycle-level latency。
	- 理论上可以做 deterministic DRAM，但代价是放弃大量动态优化，大幅牺牲 DRAM / HBM efficiency 和 bandwidth utilization。
	- 这相当于用 compiler 重写一个 software-defined memory controller，而且每代 memory、每家 DRAM 供应商都要重新验证，工程上不现实。
	- 第二个原因是 Nvidia SIMT 路线和 Groq VLIW / compiler-first 哲学相反：
		- Groq 试图在编译期消灭不确定性。
		- Nvidia GPU 则假设延迟不可预测，并通过 warp switching 隐藏访存 stall。
		- 如果用 deterministic compiler 接管 Nvidia GPU，就等于废弃其核心硬件调度单元和大量 register file 设计逻辑。
	- AMD 从 TeraScale VLIW 迁移到 GCN scalar SIMT 的历史说明：当 workload 不够可预测时，VLIW compiler 负担过重，调度权应还给硬件。
	- 因此 Groq 在 Nvidia 中更合理的定位，是作为低延迟 decode 的独立专用产品线，而不是改造现有 GPU。

- ## 论点三：Nvidia 能通过 SRAM 容量和互联优化提升 Groq
	- Groq 当前的核心瓶颈不是单纯 SRAM 带宽，而是 SRAM 容量不足导致 scale-out 规模过大，进而产生严重 interconnect latency。
	- 对 70B 模型，`576` 张卡、`16 PP x 36 TP` 的结构导致 PP/TP 通信延迟占总延迟 `>80%`，其中 pipeline latency 占 `>50%`。
	- 如果 Nvidia 通过工艺迁移和 hybrid bonding 把单卡 SRAM 从 `230MB` 提升到 `500MB`，再结合 3D SRAM 进一步翻倍，Groq 的 scale-out 需求会下降。
	- 原文推测，原来 `576` 张 LPU 才能完成的 70B 推理，未来可能降低到 `256` 张 LPU，并从 `16 PP` 降到 `8 PP`。
	- 这类改进的投资含义是：Nvidia 对 Groq 的价值不只是渠道和资本，而是把先进封装、制程迁移、系统互联和软件栈一起用于降低 Groq 的延迟瓶颈。
	- 同时，Groq 产品应避开 prefill 这类 compute-bound 短板，只专注于自己擅长的 decode 阶段。

- ## 论点四：SRAM 不会替代 HBM，但有高价值细分生态位
	- SRAM 路线的核心 tradeoff 是用更高成本换更低延迟。
	- 在 LLaMA 70B 案例中，即使用 `$2,000 / 卡` 的低价假设，`576` 张 Groq 卡也要 `>$1.1M`，而 `2` 张 H100 就能跑同类模型，成本 `<$100K`。
	- Groq API 低价并不能证明 SRAM 经济性更好，因为原文给出的 2025 年估算是收入 `$40M`、成本 `$60M`、毛利 `-50%`。
	- 但低延迟 premium market 确实存在。Claude Opus 4.6 Fast 模式输出速度提升 `2.5x`，价格从 `$5 / $25` 提到 `$30 / $150` per million tokens，约 `6x`。
	- 适合 SRAM 的 workload 主要是：
		- low batch decode。
		- real-time / interactive LLM。
		- chat、copilot、agent 中对单次响应速度极敏感的部分。
		- reasoning model 中极端看重 token speed 的场景。
	- 不适合 SRAM 的 workload 主要是：
		- batch inference。
		- offline processing。
		- ranking / recommendation。
		- 高吞吐、低成本 per token 优先的任务。
	- Agentic flow 对 SRAM 的利好也有限，因为 SWE-Agent、LangChain、Toolformer 等框架中，CPU / orchestration 延迟最高可占 `90%` E2E latency，单次 decode 加速未必能充分转化为端到端体验提升。
	- 长期看，SRAM 的成本劣势是结构性的：`6T SRAM` 天然比 `1T1C DRAM` 贵，而且 SRAM scaling 已明显放慢。
	- 同时 HBM 带宽仍在快速上升，原文对比 `Groq SRAM 80T/s` 与 `Rubin HBM4 22TB/s`，认为 SRAM 对 HBM 的速度优势已经不到一个数量级，未来可能继续收窄。

- ## 论点五：GTC 2026 的主线可能是系统化异构推理
	- 原文将 Nvidia 下一阶段的推理系统拆成多个异构层：
		- `Vera CPU`：控制、调度、agent runtime。
		- `CPX`：面向 long context prefill 的 compute-bound 模块。
		- `Groq LPU`：小模型、低延迟、low batch decode。
		- `HBM GPU`：高吞吐、高并发、batch decode 主力。
		- `ICMS / CMX`：inference context memory storage，用于管理 KV cache 和 memory hierarchy heterogeneity。
	- 这意味着未来推理不会由单一硬件统一完成，而是根据 workload 阶段和经济性要求拆分。
	- 一个可能流程是：
		- CPU 做控制和调度。
		- CPX 完成 prefill，产生几十 GB KV cache。
		- KV cache 被分配到 Groq LPU SRAM 或 HBM GPU。
		- 后续 decode 根据 latency / batch / cost 要求在 LPU 或 GPU 上执行。
	- 另一个更大胆的方向是 speculative decoding：
		- LPU 跑小型 draft model。
		- HBM GPU 跑主模型做 verification。
		- 对代码等模式固定、draft model 容易猜对语法的任务，token rate 可能显著提升。
	- 这套系统如果成立，Nvidia 的竞争维度会从 GPU 单点性能变成 agentic flow 的底层异构编排能力。

- ## 投资含义
	- 对 `Nvidia`：
		- 如果 Nvidia 将 CPX、LPU、GPU、Vera CPU、ICMS / CMX、Dynamo 等组件整合成完整 inference stack，护城河会从芯片参数扩展到系统架构和软件栈。
		- 竞争对手不再只是“做出更快的 AI chip”，还要能定义一整套异构系统，并优化端到端 agentic workflow。
	- 对 `HBM / DRAM`：
		- SRAM 不会替代 HBM。HBM 仍是高吞吐、高 batch、TCO 优先推理的主力。
		- 但 KV cache 和 context memory storage 的重要性提升，说明 memory hierarchy 会成为 AI 推理基础设施的核心环节。
	- 对 `Groq / SRAM 路线公司`：
		- 独立运行时，SRAM 路线可能受限于成本和市场规模。
		- 如果被并入大厂异构推理系统，专注低延迟 decode 或 draft model，生态位会更清晰，商业价值也可能显著提升。
	- 对 `AI ASIC startup`：
		- 原文类比移动 SoC 时代：早期各类 AP、baseband、ISP、GPU startup 群雄并起，最终赢家通常是能做系统级整合的大厂。
		- AI 推理进入异构系统阶段后，startup 独立生存空间可能被压缩，收购和生态整合会成为重要路径。

- ## Memo 结论
	- 这篇文章的核心不是简单判断 Groq 好坏，而是把 Groq 放进 Nvidia 可能形成的异构推理系统里重新定价。
	- Groq 的真实价值不在于“SRAM 替代 HBM”，而在于“compiler-first + SRAM-only”的低延迟 decode 能否成为 Nvidia inference stack 的一个专用 tier。
	- SRAM 路线有真实市场，但更像低延迟 premium segment，而不是吞噬整个推理市场的通用路线。
	- Nvidia 如果能把 CPU、CPX、LPU、HBM GPU、KV cache storage 和软件调度层整合起来，AI 推理竞争会进入系统级异构计算时代，护城河也会从单颗 GPU 扩展到整套数据中心计算系统。
