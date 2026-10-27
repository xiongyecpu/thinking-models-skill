# 用思维模型拆问题

给 **各类 AI agent** 用的通用 Skill：把含糊的工作/业务问题，拆成可核对、可拍板的分析。

## 这个 Skill 解决什么

和 agent「随便聊两句给建议」不同，本 Skill 强制走固定流程，避免空泛视角：

1. **先澄清**：决定是什么、约束是什么、证据缺口在哪  
2. **固定选 3 个模型**：从 156 条库 + 61 个场景表里选型，不编库外名字  
3. **按细文步骤填问题**：不是贴定义，而是逐步作答  
4. **结果表格化**：矩阵、对照、漏斗等扫表就能下结论  

适合：产品/运营/战略里「方案怎么比」「问题怎么拆」「要不要做」「先做哪件」这类需要结构、又怕 agent 空话的场景。细文托管在 [51as.com/toolbox](https://51as.com/toolbox)；本仓库只放配方与轻量索引，不绑死某一家产品。

## 怎么用

**装到 agent 上**

1. 把 `SKILL.md`、`models-index.yaml`、`scene-lookup.yaml` 放进**同一目录**（该平台的 skills / workflows / prompts 目录）。  
2. 按平台规则启用（Cursor、Claude Code、Codex、DeepSeek Harness 等凡能加载 Skill 目录的都行）。  
3. 本仓库是 **Skill 配方包**，不是 npm 包；`npm install` 不会自动变成可调用 skill。

**对 agent 说什么**

- 「用思维模型拆一下：……」  
- 「帮我选型思维模型分析：……」  
- 或直接描述业务问题，让 agent 按本 Skill 的 description 自动匹配  

Agent 应输出：澄清后的问题 → 3 个模型及理由 → 每个模型按 steps 逐步分析（含表格）→ 综合与下一步。分析时打开 `https://51as.com/toolbox/<slug>` 读细文步骤。

## 规模一览

| 项目 | 数量 |
| --- | ---: |
| 思维模型 | **156** |
| 分类 | **15** |
| 工作场景速查（选型入口） | **61** |

每次分析固定使用 **3 个**模型（主模型 + 辅助），禁止少于或多于 3 个，也禁止用库外模型名顶替。

## 分类与条目数

| 分类 | 条目数 | 编号范围 |
| --- | ---: | --- |
| 问题定义与诊断 | 11 | A01–A11 |
| 判断与决策 | 11 | A12–A22 |
| 战略与竞争 | 11 | B01–B11 |
| 商业模式与市场 | 11 | B12–B22 |
| 用户洞察与问题探索 | 11 | C01–C11 |
| 产品方案与体验验证 | 11 | C12–C22 |
| 增长与行为 | 11 | D01–D11 |
| 品牌定价与客户经营 | 11 | D12–D22 |
| 经营与流程 | 11 | E01–E11 |
| 改进质量与数据验证 | 11 | E12–E22 |
| 目标与项目执行 | 11 | F01–F11 |
| 组织协作与学习 | 11 | F12–F22 |
| 创新发散与技术演进 | 6 | G01–G06 |
| 投入取舍与成果推导 | 6 | G07–G12 |
| 心智模型 | 12 | H01–H12 |
| **合计** | **156** | |

## 全部模型清单

链接指向细文页。机器可读索引见 [`models-index.yaml`](./models-index.yaml)；场景 → 模型见 [`scene-lookup.yaml`](./scene-lookup.yaml)。

### 问题定义与诊断（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [A01](https://51as.com/toolbox/5w2h) | [5W2H 问题描述法](https://51as.com/toolbox/5w2h) | 5W2H | 用七个角度把含糊任务写成可分工问题 |
| [A02](https://51as.com/toolbox/mece) | [相互独立、完全穷尽](https://51as.com/toolbox/mece) | MECE | 同层分类互不重叠、合起来盖住总体 |
| [A03](https://51as.com/toolbox/issue-tree-logic-tree) | [问题树与逻辑树](https://51as.com/toolbox/issue-tree-logic-tree) | Issue Tree / Logic Tree | 把大问题拆到末端可验证的子问题 |
| [A04](https://51as.com/toolbox/hypothesis-driven-analysis) | [假设驱动分析](https://51as.com/toolbox/hypothesis-driven-analysis) | Hypothesis-Driven Analysis | 先提可推翻的判断，再选最有区分度的验证 |
| [A05](https://51as.com/toolbox/first-principles) | [第一性原理](https://51as.com/toolbox/first-principles) | First Principles | 把问题拆到不可再拆的基本事实再往上推 |
| [A06](https://51as.com/toolbox/systems-thinking-causal-loop-diagram) | [系统思考与因果回路](https://51as.com/toolbox/systems-thinking-causal-loop-diagram) | Systems Thinking / Causal Loop Diagram | 用反馈、延迟与累积解释反复出现的问题 |
| [A07](https://51as.com/toolbox/systems-thinking-iceberg-model) | [系统思考冰山模型](https://51as.com/toolbox/systems-thinking-iceberg-model) | Systems Thinking Iceberg Model | 从事件往下挖模式、结构与心智假设 |
| [A08](https://51as.com/toolbox/cynefin-framework) | [情境判断框架](https://51as.com/toolbox/cynefin-framework) | Cynefin Framework | 按因果可知性选流程、专家、试探或止损 |
| [A09](https://51as.com/toolbox/5-whys) | [连续追问原因](https://51as.com/toolbox/5-whys) | 5 Whys | 对有证据的原因连问「为什么」直到可干预 |
| [A10](https://51as.com/toolbox/fishbone-ishikawa-diagram) | [鱼骨图／因果图](https://51as.com/toolbox/fishbone-ishikawa-diagram) | Fishbone / Ishikawa Diagram | 按类别展开结果的候选原因再验证 |
| [A11](https://51as.com/toolbox/pareto-analysis) | [帕累托分析](https://51as.com/toolbox/pareto-analysis) | Pareto Analysis | 按统一口径排序找贡献最大的少数类 |

### 判断与决策（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [A12](https://51as.com/toolbox/weighted-decision-matrix) | [加权决策矩阵](https://51as.com/toolbox/weighted-decision-matrix) | Weighted Decision Matrix | 用权重×一致量表给多方案算可比总分 |
| [A13](https://51as.com/toolbox/decision-tree-expected-value) | [决策树与期望值](https://51as.com/toolbox/decision-tree-expected-value) | Decision Tree / Expected Value | 画选择与不确定结果，用概率加权倒推 |
| [A14](https://51as.com/toolbox/bayesian-updating) | [贝叶斯更新](https://51as.com/toolbox/bayesian-updating) | Bayesian Updating | 用新证据按可能性调整假设可信度 |
| [A15](https://51as.com/toolbox/sensitivity-analysis) | [敏感性分析](https://51as.com/toolbox/sensitivity-analysis) | Sensitivity Analysis | 改关键输入看结论何时翻转 |
| [A16](https://51as.com/toolbox/scenario-planning) | [情景规划](https://51as.com/toolbox/scenario-planning) | Scenario Planning | 用多套自洽未来压力测试战略而非单点预测 |
| [A17](https://51as.com/toolbox/pre-mortem) | [事前验尸](https://51as.com/toolbox/pre-mortem) | Pre-Mortem | 先假设方案已失败，再倒推可能原因 |
| [A18](https://51as.com/toolbox/inversion) | [逆向思考](https://51as.com/toolbox/inversion) | Inversion | 先问怎样会失败，再避开那些路径 |
| [A19](https://51as.com/toolbox/opportunity-cost) | [机会成本、边际分析与沉没成本](https://51as.com/toolbox/opportunity-cost) | Opportunity Cost, Marginal Analysis & Sunk Cost | 用下一单位收益与所放弃选项比，别被已花成本绑住 |
| [A20](https://51as.com/toolbox/ooda-loop) | [观察—判断—决策—行动循环](https://51as.com/toolbox/ooda-loop) | OODA Loop | 在变化环境中缩短有效学习与适应周期 |
| [A21](https://51as.com/toolbox/second-order-effects) | [二阶效应与后果链](https://51as.com/toolbox/second-order-effects) | Second-Order Effects | 问完「然后呢」，顺着后果链往下想 |
| [A22](https://51as.com/toolbox/game-theory-strategic-interaction) | [博弈论与激励互动](https://51as.com/toolbox/game-theory-strategic-interaction) | Game Theory / Strategic Interaction | 分析各方激励与最佳回应，再改规则减少冲突 |

### 战略与竞争（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [B01](https://51as.com/toolbox/pestel-pestle) | [宏观环境分析](https://51as.com/toolbox/pestel-pestle) | PESTEL / PESTLE | 按政经社技环法六类扫外部变量及业务传导 |
| [B02](https://51as.com/toolbox/porters-five-forces) | [波特五力](https://51as.com/toolbox/porters-five-forces) | Porter’s Five Forces | 从五类力量看行业利润如何被瓜分 |
| [B03](https://51as.com/toolbox/swot-tows) | [优势劣势机会威胁与战略匹配](https://51as.com/toolbox/swot-tows) | SWOT / TOWS | 整理内外部因素并配对成可行动的战略选项 |
| [B04](https://51as.com/toolbox/vrio) | [资源与能力竞争优势分析](https://51as.com/toolbox/vrio) | VRIO | 用价值稀缺难仿组织四问检验能力能否变优势 |
| [B05](https://51as.com/toolbox/value-chain-analysis) | [价值链分析](https://51as.com/toolbox/value-chain-analysis) | Value Chain Analysis | 按创造客户价值的活动找成本与差异化来源 |
| [B06](https://51as.com/toolbox/bcg-growth-share-matrix) | [增长—份额矩阵](https://51as.com/toolbox/bcg-growth-share-matrix) | BCG Growth–Share Matrix | 用市场增长与相对份额给业务组合分类讨论资金 |
| [B07](https://51as.com/toolbox/ge-mckinsey-nine-box-matrix) | [行业吸引力—竞争实力九宫格](https://51as.com/toolbox/ge-mckinsey-nine-box-matrix) | GE–McKinsey Nine-Box Matrix | 用多指标吸引力与实力九格讨论多业务投入 |
| [B08](https://51as.com/toolbox/ansoff-matrix) | [产品—市场增长矩阵](https://51as.com/toolbox/ansoff-matrix) | Ansoff Matrix | 用四象限区分渗透、新市场、新产品与多元化增长 |
| [B09](https://51as.com/toolbox/three-horizons-of-growth) | [三个增长地平线](https://51as.com/toolbox/three-horizons-of-growth) | Three Horizons of Growth | 同时管理核心兑现、成型增长与探索机会三条线 |
| [B10](https://51as.com/toolbox/strategy-canvas-errc) | [蓝海战略画布与四步动作](https://51as.com/toolbox/strategy-canvas-errc) | Strategy Canvas / ERRC | 比较价值曲线并用剔除减少增加创造重画组合 |
| [B11](https://51as.com/toolbox/playing-to-win-strategy-choice-cascade) | [战略选择级联](https://51as.com/toolbox/playing-to-win-strategy-choice-cascade) | Playing to Win / Strategy Choice Cascade | 用五层相互支持的选择把战略落到可检验承诺 |

### 商业模式与市场（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [B12](https://51as.com/toolbox/business-model-canvas) | [商业模式画布](https://51as.com/toolbox/business-model-canvas) | Business Model Canvas | 用九块模块描述创造交付与获取价值的方式 |
| [B13](https://51as.com/toolbox/lean-canvas) | [精益画布](https://51as.com/toolbox/lean-canvas) | Lean Canvas | 用问题方案指标与优势快速整理创业假设 |
| [B14](https://51as.com/toolbox/value-proposition-canvas) | [价值主张画布](https://51as.com/toolbox/value-proposition-canvas) | Value Proposition Canvas | 对照客户任务痛点收益与产品缓解创造是否匹配 |
| [B15](https://51as.com/toolbox/tam-sam-som) | [市场规模分层估算](https://51as.com/toolbox/tam-sam-som) | TAM / SAM / SOM | 分层估算总需求、可服务与可争取市场规模 |
| [B16](https://51as.com/toolbox/stp) | [市场细分、目标市场与定位](https://51as.com/toolbox/stp) | STP | 细分有意义群体、选择目标并明确心智位置 |
| [B17](https://51as.com/toolbox/3c-strategic-triangle) | [战略三角](https://51as.com/toolbox/3c-strategic-triangle) | 3C / Strategic Triangle | 把客户竞争与自身放在同一判断中找机会 |
| [B18](https://51as.com/toolbox/4p-7p-marketing-mix) | [营销组合](https://51as.com/toolbox/4p-7p-marketing-mix) | 4P / 7P Marketing Mix | 检查产品价格渠道推广及服务要素是否共撑承诺 |
| [B19](https://51as.com/toolbox/product-life-cycle) | [产品生命周期](https://51as.com/toolbox/product-life-cycle) | Product Life Cycle | 按导入成长成熟衰退观察并调整经营动作 |
| [B20](https://51as.com/toolbox/diffusion-of-innovations) | [创新扩散](https://51as.com/toolbox/diffusion-of-innovations) | Diffusion of Innovations | 分析创新如何被不同群体采用及障碍何在 |
| [B21](https://51as.com/toolbox/network-effects) | [网络效应分析](https://51as.com/toolbox/network-effects) | Network Effects | 检验参与者增加是否真正提升他人所得价值 |
| [B22](https://51as.com/toolbox/business-ecosystem-mapping) | [商业生态系统地图](https://51as.com/toolbox/business-ecosystem-mapping) | Business Ecosystem Mapping | 以用户价值为中心画出多方活动依赖与瓶颈 |

### 用户洞察与问题探索（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [C01](https://51as.com/toolbox/jobs-to-be-done-jtbd) | [待完成任务](https://51as.com/toolbox/jobs-to-be-done-jtbd) | Jobs to Be Done, JTBD | 从用户处境与想取得的进展理解需求，而非功能清单 |
| [C02](https://51as.com/toolbox/empathy-map) | [同理心地图](https://51as.com/toolbox/empathy-map) | Empathy Map | 用说、想、做、感受四区整理特定情境中的用户证据 |
| [C03](https://51as.com/toolbox/persona) | [用户画像](https://51as.com/toolbox/persona) | Persona | 把反复出现的目标、行为与限制合成可记忆的典型角色 |
| [C04](https://51as.com/toolbox/user-journey-map) | [用户旅程地图](https://51as.com/toolbox/user-journey-map) | User Journey Map | 沿时间顺序串联行动、想法、感受与触点，定位体验断点 |
| [C05](https://51as.com/toolbox/service-blueprint) | [服务蓝图](https://51as.com/toolbox/service-blueprint) | Service Blueprint | 在用户旅程下展开前台、后台与支持流程，定位交接断点 |
| [C06](https://51as.com/toolbox/contextual-inquiry) | [情境调查](https://51as.com/toolbox/contextual-inquiry) | Contextual Inquiry | 在真实环境中观察工作并适时核对解释，挖出习以为常的步骤 |
| [C07](https://51as.com/toolbox/critical-incident-technique-cit) | [关键事件访谈法](https://51as.com/toolbox/critical-incident-technique-cit) | Critical Incident Technique, CIT | 系统收集导致明显成功或失败的具体事件与条件 |
| [C08](https://51as.com/toolbox/affinity-diagram) | [亲和图／KJ 法](https://51as.com/toolbox/affinity-diagram) | Affinity Diagram | 把碎片事实按自然关联归组，发现主题而非套旧分类 |
| [C09](https://51as.com/toolbox/opportunity-solution-tree-ost) | [机会解决方案树](https://51as.com/toolbox/opportunity-solution-tree-ost) | Opportunity Solution Tree, OST | 把期望结果、用户机会、候选方案与假设测试连成可追溯结构 |
| [C10](https://51as.com/toolbox/double-diamond) | [双钻模型](https://51as.com/toolbox/double-diamond) | Double Diamond | 用两轮发散—收敛安排问题探索与方案落地 |
| [C11](https://51as.com/toolbox/design-thinking) | [设计思维](https://51as.com/toolbox/design-thinking) | Design Thinking | 以人的真实需要为起点，通过框问题、原型与测试迭代学习 |

### 产品方案与体验验证（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [C12](https://51as.com/toolbox/kano-model) | [Kano 需求分类模型](https://51as.com/toolbox/kano-model) | Kano Model | 按实现程度与满意度的非线性关系给属性分类 |
| [C13](https://51as.com/toolbox/quality-function-deployment-qfd) | [质量功能展开／质量屋](https://51as.com/toolbox/quality-function-deployment-qfd) | Quality Function Deployment, QFD | 把用户需要映射到技术特性与可验收目标，暴露冲突 |
| [C14](https://51as.com/toolbox/reach-impact-confidence-effort) | [RICE 优先级评分](https://51as.com/toolbox/reach-impact-confidence-effort) | Reach–Impact–Confidence–Effort | 用覆盖、影响、信心与工作量给候选项相对排序 |
| [C15](https://51as.com/toolbox/impact-confidence-ease) | [ICE 实验优先级评分](https://51as.com/toolbox/impact-confidence-ease) | Impact–Confidence–Ease | 用影响、信心、容易度平均分快速筛下一轮实验 |
| [C16](https://51as.com/toolbox/must-should-could-wont) | [MoSCoW 范围优先级](https://51as.com/toolbox/must-should-could-wont) | Must / Should / Could / Won’t | 在固定期限与容量内把需求分成必须、应该、可以与本轮不做 |
| [C17](https://51as.com/toolbox/user-story-mapping) | [用户故事地图](https://51as.com/toolbox/user-story-mapping) | User Story Mapping | 按用户活动展开任务与故事，用横向切片规划可走通版本 |
| [C18](https://51as.com/toolbox/lean-startup-build-measure-learn) | [精益创业与 MVP 验证循环](https://51as.com/toolbox/lean-startup-build-measure-learn) | Lean Startup / Build–Measure–Learn | 用构建—测量—学习循环尽早检验会改变方向的假设 |
| [C19](https://51as.com/toolbox/assumptions-mapping) | [假设映射](https://51as.com/toolbox/assumptions-mapping) | Assumptions Mapping | 显式写出方案成立前提，按重要性与证据弱强排序先测风险 |
| [C20](https://51as.com/toolbox/usability-testing) | [可用性测试](https://51as.com/toolbox/usability-testing) | Usability Testing | 让目标用户在接近真实条件下执行任务，用行为发现可用性问题 |
| [C21](https://51as.com/toolbox/nielsens-10-usability-heuristics) | [尼尔森十大可用性启发式](https://51as.com/toolbox/nielsens-10-usability-heuristics) | Nielsen’s 10 Usability Heuristics | 用分组检查视角走查界面，尽早标出可用性风险 |
| [C22](https://51as.com/toolbox/happiness-engagement-adoption-retention-task-success) | [HEART 用户体验度量框架](https://51as.com/toolbox/happiness-engagement-adoption-retention-task-success) | Happiness–Engagement–Adoption–Retention–Task Success | 用满意、参与、采用、留存与任务成功视角把体验目标落成指标 |

### 增长与行为（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [D01](https://51as.com/toolbox/aarrr-pirate-metrics) | [海盗指标](https://51as.com/toolbox/aarrr-pirate-metrics) | AARRR / Pirate Metrics | 用获取、激活、留存、推荐、收入五类视角拆增长 |
| [D02](https://51as.com/toolbox/north-star-metric) | [北极星指标](https://51as.com/toolbox/north-star-metric) | North Star Metric | 选一个代表用户持续获得核心价值的关键量 |
| [D03](https://51as.com/toolbox/funnel-analysis) | [漏斗分析](https://51as.com/toolbox/funnel-analysis) | Funnel Analysis | 在同一批人与时间窗内看规定步骤的转化损失 |
| [D04](https://51as.com/toolbox/cohort-analysis) | [同期群分析](https://51as.com/toolbox/cohort-analysis) | Cohort Analysis | 按共同起点分群，沿相同用户年龄比长期表现 |
| [D05](https://51as.com/toolbox/growth-loops) | [增长循环](https://51as.com/toolbox/growth-loops) | Growth Loops | 把增长写成输入—过程—产出—回流的可重复机制 |
| [D06](https://51as.com/toolbox/aida) | [注意—兴趣—欲望—行动](https://51as.com/toolbox/aida) | AIDA | 用注意、兴趣、欲望、行动四段检查沟通是否成链 |
| [D07](https://51as.com/toolbox/fogg-behavior-model) | [福格行为模型](https://51as.com/toolbox/fogg-behavior-model) | Fogg Behavior Model | 目标行为需动机、能力与提示在同一时刻汇合 |
| [D08](https://51as.com/toolbox/hook-model) | [上瘾模型／习惯循环](https://51as.com/toolbox/hook-model) | Hook Model | 用触发、行动、酬赏、投入设计自然回访机制 |
| [D09](https://51as.com/toolbox/com-b) | [能力—机会—动机行为系统](https://51as.com/toolbox/com-b) | COM-B | 从能力、机会、动机三系统诊断复杂行为障碍 |
| [D10](https://51as.com/toolbox/east) | [简便—吸引—社会—及时](https://51as.com/toolbox/east) | EAST | 用简便、吸引、社会、及时四原则生成行为干预 |
| [D11](https://51as.com/toolbox/rfm) | [近期—频次—金额分层](https://51as.com/toolbox/rfm) | RFM | 用近期、频次、金额描述交易行为并分层经营 |

### 品牌定价与客户经营（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [D12](https://51as.com/toolbox/aaker-brand-equity-model) | [阿克品牌资产模型](https://51as.com/toolbox/aaker-brand-equity-model) | Aaker Brand Equity Model | 从忠诚、知名、感知质量、联想与专有资产盘点品牌 |
| [D13](https://51as.com/toolbox/net-promoter-score-nps) | [净推荐值](https://51as.com/toolbox/net-promoter-score-nps) | Net Promoter Score，NPS | 用推荐倾向分推荐者与贬损者，追踪关系温度 |
| [D14](https://51as.com/toolbox/keller-customer-based-brand-equity-cbbe) | [凯勒顾客品牌资产金字塔](https://51as.com/toolbox/keller-customer-based-brand-equity-cbbe) | Keller Customer-Based Brand Equity，CBBE | 按识别、意义、反应、关系四层安排品牌建设 |
| [D15](https://51as.com/toolbox/peak-end-rule) | [峰终定律](https://51as.com/toolbox/peak-end-rule) | Peak-End Rule | 回顾评价常受最强时刻与结尾影响，需验证后用 |
| [D16](https://51as.com/toolbox/value-based-pricing) | [价值定价](https://51as.com/toolbox/value-based-pricing) | Value-Based Pricing | 从客户可实现价值与替代选择出发定价格 |
| [D17](https://51as.com/toolbox/van-westendorp-price-sensitivity-meter-psm) | [范韦斯滕多普价格敏感度](https://51as.com/toolbox/van-westendorp-price-sensitivity-meter-psm) | Van Westendorp Price Sensitivity Meter，PSM | 用四问探「过低、便宜、偏贵、过高」的价格认知边界 |
| [D18](https://51as.com/toolbox/gabor-granger) | [加博—格兰杰价格研究](https://51as.com/toolbox/gabor-granger) | Gabor-Granger | 对固定配置逐级问价，形成陈述需求与收入指数 |
| [D19](https://51as.com/toolbox/conjoint-analysis) | [联合分析](https://51as.com/toolbox/conjoint-analysis) | Conjoint Analysis | 用整方案选择估计属性水平对偏好的相对贡献 |
| [D20](https://51as.com/toolbox/spin-selling) | [顾问式销售提问](https://51as.com/toolbox/spin-selling) | SPIN Selling | 用现状、问题、影响、收益四类提问发展客户需求 |
| [D21](https://51as.com/toolbox/meddicc-meddpicc) | [复杂销售资格评估](https://51as.com/toolbox/meddicc-meddpicc) | MEDDICC / MEDDPICC | 用指标、决策者、标准、流程等证据检查商机资格 |
| [D22](https://51as.com/toolbox/servqual) | [服务质量量表](https://51as.com/toolbox/servqual) | SERVQUAL | 用期望与感知差距诊断有形、可靠、响应、保证、移情 |

### 经营与流程（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [E01](https://51as.com/toolbox/cost-volume-profit-break-even-analysis) | [本量利与盈亏平衡](https://51as.com/toolbox/cost-volume-profit-break-even-analysis) | Cost–Volume–Profit / Break-even Analysis | 用销量、价格与成本结构算出何时不亏 |
| [E02](https://51as.com/toolbox/unit-economics-ltv-cac) | [单位经济模型](https://51as.com/toolbox/unit-economics-ltv-cac) | Unit Economics：LTV、CAC 与回收期 | 按客户或订单对照获客成本与后续贡献 |
| [E03](https://51as.com/toolbox/cash-conversion-cycle-working-capital) | [现金转换周期与营运资金](https://51as.com/toolbox/cash-conversion-cycle-working-capital) | Cash Conversion Cycle / Working Capital | 量清存货与赊销占资、账期抵减后的现金周转天数 |
| [E04](https://51as.com/toolbox/npv-irr-dcf) | [净现值、内部收益率与折现现金流](https://51as.com/toolbox/npv-irr-dcf) | NPV / IRR / DCF | 把不同时点的现金折到同一时点再比方案 |
| [E05](https://51as.com/toolbox/dupont-analysis) | [杜邦分析](https://51as.com/toolbox/dupont-analysis) | DuPont Analysis | 把净资产收益率拆成利润率、周转与杠杆 |
| [E06](https://51as.com/toolbox/activity-based-costing-abc) | [作业成本法](https://51as.com/toolbox/activity-based-costing-abc) | Activity-based Costing，ABC | 按作业动因把间接费用分到产品或客户 |
| [E07](https://51as.com/toolbox/driver-tree-variance-analysis) | [指标驱动树与经营差异分解](https://51as.com/toolbox/driver-tree-variance-analysis) | Driver Tree / Variance Analysis | 用可复算关系拆指标，再分解预算与实际差额 |
| [E08](https://51as.com/toolbox/theory-of-constraints-toc) | [约束理论](https://51as.com/toolbox/theory-of-constraints-toc) | Theory of Constraints，TOC | 先找限制整体产出的瓶颈再集中改善 |
| [E09](https://51as.com/toolbox/suppliers-inputs-process-outputs-customers) | [SIPOC 流程边界图](https://51as.com/toolbox/suppliers-inputs-process-outputs-customers) | Suppliers–Inputs–Process–Outputs–Customers | 用供应—输入—过程—输出—客户框定流程边界 |
| [E10](https://51as.com/toolbox/value-stream-mapping-vsm) | [价值流图](https://51as.com/toolbox/value-stream-mapping-vsm) | Value Stream Mapping，VSM | 画出工作与信息如何流动并标出等待浪费 |
| [E11](https://51as.com/toolbox/littles-law-queueing) | [Little 定律与排队分析](https://51as.com/toolbox/littles-law-queueing) | Little’s Law / Queueing | 用在制量与吞吐估算平均停留时间 |

### 改进质量与数据验证（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [E12](https://51as.com/toolbox/plan-do-check-act) | [PDCA 持续改进循环](https://51as.com/toolbox/plan-do-check-act) | Plan–Do–Check–Act | 计划—试行—核对—固化，小步闭环改进 |
| [E13](https://51as.com/toolbox/define-measure-analyze-improve-control) | [DMAIC 数据驱动改进](https://51as.com/toolbox/define-measure-analyze-improve-control) | Define–Measure–Analyze–Improve–Control | 定义—测量—分析—改进—控制的严谨改进流程 |
| [E14](https://51as.com/toolbox/statistical-process-control-spc) | [统计过程控制与控制图](https://51as.com/toolbox/statistical-process-control-spc) | Statistical Process Control，SPC | 用控制图区分普通波动与异常信号 |
| [E15](https://51as.com/toolbox/failure-mode-and-effects-analysis-fmea) | [失效模式与影响分析](https://51as.com/toolbox/failure-mode-and-effects-analysis-fmea) | Failure Mode and Effects Analysis，FMEA | 上线前系统梳理会怎么坏、影响谁、如何防 |
| [E16](https://51as.com/toolbox/eoq-reorder-point-safety-stock) | [经济订货量、补货点与安全库存](https://51as.com/toolbox/eoq-reorder-point-safety-stock) | EOQ / Reorder Point / Safety Stock | 决定每次买多少、何时补货、备多少缓冲 |
| [E17](https://51as.com/toolbox/abc-inventory-analysis) | [ABC 库存分类](https://51as.com/toolbox/abc-inventory-analysis) | ABC Inventory Analysis | 按经济重要性给 SKU 分层管理精力 |
| [E18](https://51as.com/toolbox/time-series-forecasting) | [时间序列预测](https://51as.com/toolbox/time-series-forecasting) | Time-series Forecasting | 从历史时间规律外推未来并给出区间 |
| [E19](https://51as.com/toolbox/a-b-testing-randomized-controlled-experiment) | [A/B 随机对照测试](https://51as.com/toolbox/a-b-testing-randomized-controlled-experiment) | A/B Testing / Randomized Controlled Experiment | 随机分组比较处理与对照的平均因果效应 |
| [E20](https://51as.com/toolbox/causal-dag-confounding-control) | [因果图与混杂控制](https://51as.com/toolbox/causal-dag-confounding-control) | Causal DAG / Confounding Control | 用有向无环图理清混杂并选择调整变量 |
| [E21](https://51as.com/toolbox/regression-analysis) | [回归分析](https://51as.com/toolbox/regression-analysis) | Regression Analysis | 用模型描述解释变量与结果的条件关系 |
| [E22](https://51as.com/toolbox/monte-carlo-simulation) | [蒙特卡洛模拟](https://51as.com/toolbox/monte-carlo-simulation) | Monte Carlo Simulation | 对不确定输入反复抽样，得到结果分布 |

### 目标与项目执行（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [F01](https://51as.com/toolbox/smart-objectives) | [SMART 目标检验](https://51as.com/toolbox/smart-objectives) | SMART Objectives | 用具体可验的五项约束把模糊愿望写成可验收目标 |
| [F02](https://51as.com/toolbox/objectives-and-key-results-okr) | [目标与关键结果](https://51as.com/toolbox/objectives-and-key-results-okr) | Objectives and Key Results，OKR | 用少数有意义目标加可验证关键结果对齐行动 |
| [F03](https://51as.com/toolbox/balanced-scorecard-bsc) | [平衡计分卡](https://51as.com/toolbox/balanced-scorecard-bsc) | Balanced Scorecard，BSC | 用财务客户流程能力多视角连接战略与日常指标 |
| [F04](https://51as.com/toolbox/work-breakdown-structure-wbs) | [工作分解结构](https://51as.com/toolbox/work-breakdown-structure-wbs) | Work Breakdown Structure，WBS | 按交付成果把项目逐层拆成可估算可验收的工作包 |
| [F05](https://51as.com/toolbox/critical-path-method-cpm-pert) | [关键路径与三点估算](https://51as.com/toolbox/critical-path-method-cpm-pert) | Critical Path Method，CPM；PERT | 用依赖网络找决定工期的最长路径，并用三点估时长不确定性 |
| [F06](https://51as.com/toolbox/kanban-and-wip-limits) | [看板与在制品限制](https://51as.com/toolbox/kanban-and-wip-limits) | Kanban and WIP Limits | 显式工作流并限制同时进行的工作以改善流动 |
| [F07](https://51as.com/toolbox/scrum) | [Scrum 敏捷协作框架](https://51as.com/toolbox/scrum) | Scrum | 用短周期增量、固定事件与角色实现透明检视适应 |
| [F08](https://51as.com/toolbox/responsible-accountable-consulted-informed-raci) | [责任分配矩阵](https://51as.com/toolbox/responsible-accountable-consulted-informed-raci) | Responsible, Accountable, Consulted, Informed，RACI | 按任务区分执行、最终负责、征询与知会四类义务 |
| [F09](https://51as.com/toolbox/rapid-decision-making) | [RAPID 决策权分配](https://51as.com/toolbox/rapid-decision-making) | RAPID Decision Making | 把建议、同意、执行、输入与拍板权拆开落到具体人 |
| [F10](https://51as.com/toolbox/power-interest-grid) | [干系人权力—关注度矩阵](https://51as.com/toolbox/power-interest-grid) | Power–Interest Grid | 按权力与关注度把相关方分组以匹配沟通投入 |
| [F11](https://51as.com/toolbox/likelihood-impact-risk-matrix) | [概率—影响风险矩阵](https://51as.com/toolbox/likelihood-impact-risk-matrix) | Likelihood–Impact Risk Matrix | 用发生可能与后果严重度粗分风险以排应对优先级 |

### 组织协作与学习（11）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [F12](https://51as.com/toolbox/mckinsey-7-s-framework) | [麦肯锡 7S 组织诊断](https://51as.com/toolbox/mckinsey-7-s-framework) | McKinsey 7-S Framework | 从战略结构系统价值观技能人员风格七要素查组织错位 |
| [F13](https://51as.com/toolbox/galbraith-star-model) | [加尔布雷思星型组织模型](https://51as.com/toolbox/galbraith-star-model) | Galbraith Star Model | 用战略结构流程奖励人员五政策成套设计组织 |
| [F14](https://51as.com/toolbox/tuckmans-stages-of-team-development) | [塔克曼团队发展模型](https://51as.com/toolbox/tuckmans-stages-of-team-development) | Tuckman’s Stages of Team Development | 用形成震荡规范表现等状态语言讨论团队协作阶段 |
| [F15](https://51as.com/toolbox/nine-box-talent-grid-and-skills-matrix) | [人才九宫格与能力矩阵](https://51as.com/toolbox/nine-box-talent-grid-and-skills-matrix) | Nine-Box Talent Grid and Skills Matrix | 用绩效潜力九宫格与技能覆盖表支撑盘点与培养 |
| [F16](https://51as.com/toolbox/kotters-eight-steps-for-leading-change) | [科特八步变革](https://51as.com/toolbox/kotters-eight-steps-for-leading-change) | Kotter’s Eight Steps for Leading Change | 用紧迫感联盟愿景动员试点成果与制度嵌入推动变革 |
| [F17](https://51as.com/toolbox/awareness-desire-knowledge-ability-reinforcement) | [ADKAR 个人变革模型](https://51as.com/toolbox/awareness-desire-knowledge-ability-reinforcement) | Awareness, Desire, Knowledge, Ability, Reinforcement | 按认知意愿知识能力强化定位个人采纳卡点 |
| [F18](https://51as.com/toolbox/lewins-unfreeze-change-refreeze-model) | [勒温变革三阶段](https://51as.com/toolbox/lewins-unfreeze-change-refreeze-model) | Lewin’s Unfreeze–Change–Refreeze Model | 用解冻改变再冻结检查习惯变革前后支持条件 |
| [F19](https://51as.com/toolbox/after-action-review-aar) | [行动后复盘](https://51as.com/toolbox/after-action-review-aar) | After Action Review，AAR | 对照预期与实际提炼可验证改进行动的事后学习 |
| [F20](https://51as.com/toolbox/double-loop-learning) | [双环学习](https://51as.com/toolbox/double-loop-learning) | Double-Loop Learning | 在改行动之外进一步检验目标规则与默认假设 |
| [F21](https://51as.com/toolbox/scqa-and-the-minto-pyramid-principle) | [SCQA 与金字塔表达](https://51as.com/toolbox/scqa-and-the-minto-pyramid-principle) | SCQA and the Minto Pyramid Principle | 用背景冲突问题答案开场，再金字塔分组支撑中心结论 |
| [F22](https://51as.com/toolbox/batna-and-zopa) | [谈判替代方案与可协议区间](https://51as.com/toolbox/batna-and-zopa) | BATNA and ZOPA | 用最佳替代方案与双方可接受重叠区间准备谈判 |

### 创新发散与技术演进（6）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [G01](https://51as.com/toolbox/six-thinking-hats) | [六顶思考帽](https://51as.com/toolbox/six-thinking-hats) | Six Thinking Hats | 同一时段全员用同一视角讨论，再切换视角 |
| [G02](https://51as.com/toolbox/scamper) | [SCAMPER 创意检查表](https://51as.com/toolbox/scamper) | SCAMPER | 用七种变换提问，系统挤出不同方向的候选 |
| [G03](https://51as.com/toolbox/theory-of-inventive-problem-solving) | [TRIZ 发明问题解决理论](https://51as.com/toolbox/theory-of-inventive-problem-solving) | Theory of Inventive Problem Solving | 把冲突抽象成矛盾，再找跨领域解决原理 |
| [G04](https://51as.com/toolbox/general-morphological-analysis) | [形态分析](https://51as.com/toolbox/general-morphological-analysis) | General Morphological Analysis | 拆维度与状态，检查组合相容后挑代表概念 |
| [G05](https://51as.com/toolbox/analogical-reasoning-structure-mapping) | [类比推理与结构映射](https://51as.com/toolbox/analogical-reasoning-structure-mapping) | Analogical Reasoning / Structure Mapping | 映射关系结构，而不是表面相像 |
| [G06](https://51as.com/toolbox/wardley-mapping) | [Wardley 地图](https://51as.com/toolbox/wardley-mapping) | Wardley Mapping | 按用户需求画价值链，标能力演进位置再定自研或采购 |

### 投入取舍与成果推导（6）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [G07](https://51as.com/toolbox/impact-mapping) | [影响地图](https://51as.com/toolbox/impact-mapping) | Impact Mapping | 用目标—角色—行为变化—交付物四层连起范围 |
| [G08](https://51as.com/toolbox/weighted-shortest-job-first) | [WSJF 与延迟成本](https://51as.com/toolbox/weighted-shortest-job-first) | Weighted Shortest Job First | 用延迟成本相对工期，给稀缺产能排先后 |
| [G09](https://51as.com/toolbox/value-of-information) | [信息价值分析](https://51as.com/toolbox/value-of-information) | Value of Information | 信息有价值，当且仅当它能改变决策并改善结果 |
| [G10](https://51as.com/toolbox/real-options) | [实物期权思维](https://51as.com/toolbox/real-options) | Real Options | 把分阶段投入当成可执行的扩大、等待或退出权利 |
| [G11](https://51as.com/toolbox/reference-class-forecasting) | [参考类预测](https://51as.com/toolbox/reference-class-forecasting) | Reference Class Forecasting | 先看可比项目真实结果分布，再估本次落点 |
| [G12](https://51as.com/toolbox/theory-of-change-logic-model) | [变革理论与逻辑模型](https://51as.com/toolbox/theory-of-change-logic-model) | Theory of Change / Logic Model | 把投入到长期影响的因果链与假设写清楚再验收 |

### 心智模型（12）

| ID | 中文名 | 英文名 | 一句定义 |
| --- | --- | --- | --- |
| [H01](https://51as.com/toolbox/reversible-decisions) | [可逆与不可逆决策](https://51as.com/toolbox/reversible-decisions) | Reversible and Irreversible Decisions | 先分清能不能回头，再决定快慢与严谨度 |
| [H02](https://51as.com/toolbox/regret-minimization) | [后悔最小化](https://51as.com/toolbox/regret-minimization) | Regret Minimization | 用长期回望选更少悔恨的路径 |
| [H03](https://51as.com/toolbox/leverage-points) | [杠杆点](https://51as.com/toolbox/leverage-points) | Leverage Points | 找小改动能撬动系统大变化的位置 |
| [H04](https://51as.com/toolbox/compounding) | [复利](https://51as.com/toolbox/compounding) | Compounding | 小改进持续叠加，后期收益非线性放大 |
| [H05](https://51as.com/toolbox/emergence) | [涌现](https://51as.com/toolbox/emergence) | Emergence | 整体行为无法仅由拆开零件相加解释 |
| [H06](https://51as.com/toolbox/moat) | [护城河](https://51as.com/toolbox/moat) | Moat | 判断优势能挡住竞争多久、靠什么维持 |
| [H07](https://51as.com/toolbox/base-rate) | [基础比率](https://51as.com/toolbox/base-rate) | Base Rate | 先看同类事件本来有多常见，再看个案线索 |
| [H08](https://51as.com/toolbox/margin-of-safety) | [安全边际](https://51as.com/toolbox/margin-of-safety) | Margin of Safety | 估计不准时主动留余量，避免贴边运行 |
| [H09](https://51as.com/toolbox/map-is-not-territory) | [地图不是疆域](https://51as.com/toolbox/map-is-not-territory) | The Map Is Not the Territory | 模型只是简化图，别把它当成现实本身 |
| [H10](https://51as.com/toolbox/confirmation-bias) | [确认偏误](https://51as.com/toolbox/confirmation-bias) | Confirmation Bias | 人会偏爱印证已有看法的证据，须主动找反例 |
| [H11](https://51as.com/toolbox/circle-of-competence) | [能力圈](https://51as.com/toolbox/circle-of-competence) | Circle of Competence | 先认清自己懂什么，再决定能不能下结论 |
| [H12](https://51as.com/toolbox/occams-razor) | [奥卡姆剃刀](https://51as.com/toolbox/occams-razor) | Occam's Razor | 同样能解释时，优先更少额外假设的说法 |

## 仓库文件

| 文件 | 作用 |
| --- | --- |
| `SKILL.md` | Skill 正文（YAML frontmatter + 步骤与输出版式） |
| `models-index.yaml` | 156 条模型轻量索引 |
| `scene-lookup.yaml` | 61 个工作场景 → 主/辅模型 |
| `LICENSE` | MIT |

## 接入说明

见文首「怎么用」。


## 硬规矩（摘要）

1. 选出模型只是半截；交付主体是「用该模型的 steps 拆用户问题」。
2. 恰好 3 个模型；必须从本库索引选型。
3. 矩阵 / 对照 / 漏斗等结果用表格（或列表 / mermaid）摊开，扫表能下结论。

## 许可

- 本仓库配方与索引：**MIT**（见 [`LICENSE`](./LICENSE)）
- 站上细文：[51as.com/toolbox](https://51as.com/toolbox) 页面版权以站点标注为准；本仓库不二次分发全文

## 相关

- 工具箱站点：https://51as.com/toolbox
- 本仓库：https://github.com/xiongyecpu/thinking-models-skill
