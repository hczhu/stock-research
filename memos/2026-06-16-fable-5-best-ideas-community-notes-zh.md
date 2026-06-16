- tags:: [[Fable]], [[Anthropic]], [[Mythos]], [[agents]], [[multi-agent]], [[token economics]], [[model routing]], [[benchmark]], [[inference]], [[HBM]], [[CXL]], [[$NVDA]], [[OpenAI]], [[Cursor]], [[China]]

- ## Fable 5 讨论 Notes — Best Ideas 社群(2026 年 6 月)
	- **来源(Source)**:海外独角兽转载 Best Ideas 社群《Fable 5 讨论 Notes | Best Ideas》,2026-06。共 76 条一线/投研观点,分 7 个部分。Fable 5 为 Anthropic 前沿模型(Mythos 为其更强的内部/同代上限模型)。
	- **一句话**:一线体感取决于任务选择——**普通任务无感、宽任务(大规模并行)强、创意/前端任务更好、工程可靠性仍有争议**,这几类反馈可同时成立。模型市场正按**任务价值 × 成本效率**分层。

- ## I. 一线实测:Fable 5 的上限来自任务难度
	- **开发者任务**:
		- **Long-horizon task 是最稳定的正向反馈**——任务越难、越长、越需持续推进(拆解目标→执行→检查→汇总交付),越能体现 Fable 5 的能力差异;**项目 owner 型、每小时约 $300 的高复杂度任务**最能拉开与其他模型的差距。
		- **普通任务体现不出溢价**:一般 coding、前端小需求、材料整理用 Sonnet / Codex / GPT-5.5 也能完成,Fable 5 的额外成本未必转化为独立价值。评判上限应看它能否**越过用户的能力边界**(提出用户想不到的方案、完成用户拆不出的端到端任务)。
		- **宽任务 / 大规模 fanout**:Fable 5 第一个任务就拉起约 **100 个 agent**(其他模型通常 ~10 个);但 fanout 规模 ≠ 智能提升——有重度工程用户在 **Opus 4.8** 上也见过一次性并行 **103 个 agent**,成败仍取决于模型逻辑与任务组织。适合并行搜索、代码库遍历、舆情收集、数据处理。
		- **前端 / 3D / design taste 更明显**:Three.js、3D 世界构建上更强,一次生成的网站更少粗糙 AI 配色;但**视觉/交互细节仍需人工验收**(截图驱动的细节修正、元素大小、叠加关系仍会失手)。
		- **逆向工程 / 安全研究**:可通过网页、混淆 JS、安卓应用或游戏 ROM 主动获取上下文,反编译还原产品逻辑或游戏关卡(视觉细节仍需人工检查)。
		- **TypeScript / Excel 类任务**:Fable 5 约 **3 小时、约 $200** 完成的任务,Codex 5.5 约 **10 小时**也能做到接近 **90%**——差距主要来自"模型决定怎么做"的能力。
		- **GPT-5.5 在边界清晰的工程任务里可长时间稳定执行**:有开发者让其**连续运行 70+ 小时**、三天后结果仍满意(前提:任务拆清、规范写清、持续维护 Agents.md);能把约 **3000 个 mock 测试**迁移成真实测试,并在"大文件须降到 1000–2000 行以下"约束后把 8–9 个大文件拆好。
	- **研究任务**:auto research 价值取决于能否**形成闭环**(把 agent 工作连到实际业务结果,减少只看 token usage 的粗糙做法);开放式研究(更长、更开放、无标准答案)更易感知 Mythos / Fable 的差异。
	- **实际生产任务**:
		- 一位**日均 AI 编程成本 >$1000** 的 CTO 级用户认为:Fable 5 的**底层智能没有质变**,只是工具调用和部分 workflow 更熟练。**两天 >$1 万**的成本没换来足够确定的生产价值 → 即便模型没下架,企业领导层也不会马上全公司推广。
		- 企业 workflow 拆成四步:抽象工作流 → 工具链自动化约 **80%** → AI 替代原需人脑的约 **20%** → AI 加速工具链本身开发。
		- **OpenClaw / Hermes 自动升级** use case 暴露 Fable 难以泛化 workflow(把"每天自动升级插件 + 上游版本变化后自动修 patch"反复误解成修某个版本的 patch);**长时任务失败更像任务状态管理问题**(推进久了丢掉最初目标/约束/验收标准)。需求对齐需工程方法(如 **OPP:Objective-Problem-Proposal**)。

- ## II. Benchmark 表现(需把分数、成本、token、步骤、拒答比例一起看)
	- **关键扰动**:Fable 5 在模型前面加了 **safety classifier(安全分类器)**,遇到 cyber / biology / chemistry / distillation 相关问题可能触发**拒答、降质或 fallback**(回退到 Opus 4.8),单一总分无法解释真实表现。
	- **Xbench / ScienceQA 拒答**:约 100 道科学+长推理题中 **21 道返回空结果**,明显高于官方披露的约 **0.3%**;拒答样本集中在生命科学(基因、遗传、蛋白、细胞)。
	- **ScienceQA 得分(仍在第一梯队)**:
		| 模型 | ScienceQA 得分 |
		|---|---:|
		| Opus 4.8 | 76.4 |
		| **Fable 5** | **73.4** |
		| GPT-5.5 Pro High | 73 |
	- **推理路径(Output token / CoT 长度)** —— Fable 5 的 CoT 显著更短:
		| 模型 | 平均每题 output token | CoT 相对长度 |
		|---|---:|---|
		| GPT-5.5 | ~5,200 | 基准 |
		| Opus 4.8 | ~1,700–1,900 | — |
		| **Fable 5** | **~1,100** | 约为 Opus 4.8 的 **60%**、GPT-5.5 的 **25%** |
	- **BabyVision(多模态理解,在爬升但未到头部)**:
		| 模型 | BabyVision 得分 |
		|---|---:|
		| Gemini 3.5 Flash | 61.8 |
		| **Fable 5** | **36.6** |
		| Opus 4.8 | 23 |
		| Opus 4.5 | 14 |
	- 在约 **$100/小时**价值的复杂任务上,Fable 5 的 pass rate 与平均分**低于前代**(可能受安全路由/拒答/降质影响);但 API token 虽更贵,CoT 输出减少后,**真实任务成本未必按 API 单价差距等比例扩大**。
	- **CursorBench 3.1(开发者任务成本对照)** —— 更高分但更贵、更慢:
		| CursorBench 3.1 模式 | 得分 | 每任务成本 | Token 数 | 步骤数 |
		|---|---:|---:|---:|---:|
		| **Fable 5 Max** | **72.9%** | $18.02 | 63,842 | 76 |
		| GPT-5.5 Extra High | 64.3% | $4.37 | 17,905 | 46 |
		- 即:Fable 5 Max 比 GPT-5.5 Extra High 高约 8.6 个百分点,但**每任务成本约 4.1×、token 约 3.6×、步骤约 1.65×**。

- ## III. Multi-agent、model routing 与 harness
	- **Multi-agent 价值首先取决于任务组织**(拆清任务、验证子任务、汇总成可交付成果);宽任务天然需要并行 agent 做信息覆盖。
	- **子任务分担主 agent 的 context 压力**:子 agent 用自己的上下文,只把压缩后的结果交回主 agent —— 相当于一种**记忆 scaling**。但**目标不清会让并行系统放大浪费**(多 agent 朝错误方向推进,token 快速放大,结果未必可靠)。
	- **Workflow 能力已跨过单一模型边界**:Claude Code 本身已有 dynamic workflow,Opus 4.8 也能触发大规模并行 agent → 评价 Fable 5 体感须**拆开看模型能力、产品 harness、路由策略**三层。
	- **Model routing 已成真实产品问题**:Fable 有时把简单任务换给 Haiku / DeepSeek / Gemini 或本地小模型,但路由逻辑不稳定、也不总让用户知情。Cursor、Harvey 等 vertical agent 需把路由层当**成本系统**(哪些步骤给前沿模型、哪些给便宜模型)。
	- **外部 harness 会持续承受模型升级冲击**:若 harness 只是弥补上一代模型缺陷,下一代把相关能力训进去后,它可能变成 **technical debt**。
	- 创业团队组织形态开始像 **file system**,人更像独立 IC(负责定义目标、验收结果、处理异常);**Agent workflow 提升可能需端到端训练**(主 agent planning + 小模型执行同环境共优化)。

- ## IV. 存储、算力与芯片
	- Sub-agent 推理优化同时影响 **GPU、内存与 KV cache**:多个 sub-agent 在共享 prefix 下运行时,batch inference 提高 GPU 利用率,KV cache / 内存转移开销更易被摊薄。
	- **多 agent fanout 把存储/内存问题拉到 infra 层**:几十个 subagent 或多 thread 共享上下文时,**CXL 内存池与共享内存价值变高**(多个执行分支需读取相近的项目状态与中间结果)。
	- **HBM 与内存墙仍限制高价值任务扩展**:更长任务、更大上下文、更多 KV cache 持续抬高存储需求;workflow 可提高调用效率,但**消不掉物理供给增速 < 智能需求增速**的压力。
	- **OpenAI 降价**同时反映商业竞争与推理效率变化(B 系列卡推理效率提升 → 同一模型有继续降价空间);若模型能力没明显超过 Claude,OpenAI 用降价抢份额是合理选择。
	- **AI labs 盈利更像单代模型账本**:单季盈亏很大程度取决于算力多买还是买少;训练成本被未来收入摊薄,**推理毛利才是长期利润率的关键变量**。
	- **Anthropic 短期 ARR 分歧集中在算力供给**:乐观=高价值任务带来绝对 ARR 增量;谨慎=新增算力有限 + CFO 控 token budget + OpenAI 可能打价格战。会上估算 Anthropic 可能有约 **2–3 GW 算力**(约一半或用于训练)——此类数字仅作会上观点,不确定性很大。

- ## V. Token maxxing 进入企业 ROI 账本
	- **Token maxxing 已从 adoption 指标变成成本压力**:企业开始追问"token 消耗到底带来多少业务结果"。硅谷企业探索 **quota 机制**(Google 内部对最强模型也有 quota 限制),但怎么限才不伤 AI-native 转型仍无统一答案。
	- **Vertical agent 毛利压力直接**:单用户 token 消耗每月上涨 **50%–100%**,但很多老产品仍按 **seat 收费**,收入无法同步增长。**Function tool agent → coding agent 显著放大成本**(同一 task 放进 sandbox 持续运行,token 量可能高出数倍,甚至把 gross margin 打成负数)。Subscription 计价被重度用户冲击 → agent 公司需考虑涨价、model routing、自训小模型或接开源模型。
	- **下一阶段指标从 value mapping 开始**:谁用了 token、在哪个 workflow、服务哪个 title / practice group、最后交付了什么结果;**token dashboard 成为客户侧控费基础设施**。把 token usage 当 adoption 指标会出现 **reward hacking**(只把用量冲高)。
	- **国内市场尚未明显踩刹车**:国内 token 成本更低,电商/招聘/广告等场景有明确价值反馈,但真正有钱的客户还没全面铺开 token 消耗;后续也会进入 ROI 账本。有用户激进认为 token usage 仍会大幅增长(甚至到现在的 **100×**),但单 token 价格继续下降。

- ## VI. 安全边界与发布节奏决定 adoption 速度
	- **安全分类器已进入模型体验层**:cyber / biology / chemistry / distillation 被当作发布里最需关注的风险方向(Xbench 拒答样本集中在生命科学)。
	- **反编译能力增强**对网络安全、工具权限、边界控制提出更高要求;**自主 agent 越强、权限边界越重要**(prompt injection、工具权限、proactive agent 行动边界、模型自约束)将成下一阶段核心问题。
	- **Fable 访问暂停**首先影响短期市场情绪:二级市场投资人会重评 ARR、监管风险、IPO 时间表、模型发布节奏(也有人认为是外因短期扰动,不应简单外推到所有 AI labs)。访问暂停还可能改变企业备选方案(自研模型、开源微调、前沿模型备份)→ **反而带来新的算力需求**。国内"模型自主可控"被重新强调,**智谱 GLM 5.2** 的发布值得关注。

- ## VII. 模型市场会按任务价值与成本效率分层
	- **前沿模型锁定高价值任务**:超级工程、科研、安全、底层系统重构、投资研究、国土安全等可承受更高模型成本。To C 与 To B 可能走向两套优化体系(To C 更强调快/好/省+产品体验;To B 继续追顶尖智能解决大型工程/高价值任务)。
	- **AI 时代 toB 生产力场景可能大于传统互联网时期**:企业内部系统/workflow/agent/机器人持续消耗模型能力,平台公司内部 token 消耗可能显著高于 consumer 直接用量。**To-agent / to-human 比 to-consumer 更能解释未来 token 用量**(大量调用由 agent 网络发起);**机器人**可能成为 to-agent 之外又一类巨大智能消耗(模型触达物理世界)。
	- **低价模型承接普通步骤**:很多企业任务只需 GPT-4 级或 Opus 4.6 级智能,即便 long-horizon task 里也有很多 step 不需前沿模型。**国产/开源模型的机会在成本效率**——若能以 **1/10–1/20** 价格达到 Opus 4.6 级智能,大量白领流程/普通企业任务会被重新打开。
	- **可能的分层情景**:"**前沿模型拿 80% revenue,开源模型处理 80% token**"。但国产成本优势仍要继续验证:前沿 lab 可用自家强模型生成更高质量蒸馏数据、并优化同档智能下的推理成本;且头部 lab 短期缺少卷低价小模型市场的动力(高价值客户+推理算力仍供不应求)。

- ## 投资含义 / Cross-links
	- **任务分层是核心交易逻辑**:前沿模型(Fable/Mythos/Opus/GPT-5.5)守高价值长任务,低价/国产/开源吃普通 step —— 对应 [[2026-06-03-foundation-model-pricing-power-bear-case]] 的"模型访问层 + 五层 access tiers"框架。
	- **Token 经济从 adoption 转向 ROI**:vertical agent 单用户 token +50–100%/月 vs seat 计价 → 涨价/路由/自训小模型,呼应订阅利润率与按量定价 ([[2026-06-11-ai-subscription-margin-by-utilization]]、[[2026-06-05-coding-agents-token-demand-and-enterprise-pmf-willison]]);宏观上仍支撑 token 需求长期增长 ([[2026-06-05-goldman-agentic-ai-token-demand-24x-by-2030]])。
	- **Multi-agent fanout = 存储/内存 infra 需求**:CXL 内存池、KV cache、HBM/内存墙是高价值任务扩展的物理瓶颈 ([[2026-06-04-neocloud-supply-demand-ai-infra-restructuring-kenny-zhang]]、[[2026-06-09-deepseek-v4-inference-performance-gpus-engines-semianalysis]])。
	- **算力供给决定 lab ARR**:Anthropic ~2–3 GW(约半数训练)、推理毛利是长期利润率关键变量 ([[2026-06-03-frontier-labs-gpu-compute-capacity-share]]、[[2026-06-05-gpu-cluster-rental-unit-economics-spacex-google-anthropic]])。
	- **安全/发布节奏 = adoption 与备选方案变量**:访问暂停推动自研/开源/国产(智谱 GLM 5.2)→ 反而可能新增算力需求。
	- **注意(Caveat)**:以上为社群一线体感与会上观点(含 Anthropic 算力 GW、ARR 等强不确定估算),benchmark 分数受安全分类器拒答/fallback 干扰,需拆开 fallback 单独看;数据点多为单点案例,非严格统计。
