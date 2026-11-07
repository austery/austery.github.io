---
layout: post.njk
source: https://yage.ai/share/ai-model-companies-consolidation-20260518.html
speaker: yage.ai
title: AI 模型公司的两条死路与一条活路
date: '2026-05-18'
summary: 文章分析了独立AI模型公司面临的普遍生存困境：随着模型能力收敛和价格剧烈下降，纯粹销售模型访问权限的商业模式已不可持续。大型科技公司通过强制内部调动人才和资本支出构建AI原生架构，进一步挤压了中间地带。文章指出，未来AI公司需通过地缘背书、分销渠道掌控、垂直专业化或深度构建编排层（应用层逻辑）来寻找生存空间，模型层商品化已是不可逆的趋势。
area: tech-engineering
category: ai-application
tags:
  - ai-commoditization
  - business-model
  - orchestration-layer
  - ai-strategy
  - artificial-intelligence
people:
  - Emad Mostaque
  - Lee Kai-Fu
  - Mustafa Suleyman
  - Noam Shazeer
  - Mark Zuckerberg
companies_orgs:
  - AI21 Labs
  - Meta
  - Anthropic
  - Mistral AI
  - Cohere
  - DeepSeek
  - OpenAI
products_models:
  - Jurassic
  - Jamba
  - GPT-4
  - Claude
  - Gemini
media_books: []
draft: true
status: evergreen
---

2026-05-18

5 月 18 日，两件事同时落地。

以色列 AI 公司 AI21 Labs 宣布裁员 60%，员工从 180 人降至约 70
人，停止独立销售 AI 模型，将全部资源转向 Maestro agent
优化平台。同日，Meta 内部备忘录流出：公司已将 7000 名员工重新分配到 AI
相关岗位，5 月 20 日起裁员约 8000 人（10%），此前在 4 月初已经有至少
1000 名顶级工程师被强制调入 AI 部门，拒绝者面临解雇。Meta 2026
年资本支出预计达到 1250-1450 亿美元。

两条新闻不会出现在同一篇报道里，但放在一起才构成完整的图景。一边是模型公司在收缩和转型，一边是平台公司在用组织手段强制转向
AI。两个方向指向同一个判断：中间地带正在消失。既不是超大规模平台、又没有独特护城河的
AI 模型公司，正在一个接一个地退出独立模型销售。

## 模型公司的批量死亡

AI21 不是第一个，也不会是最后一个。

2024 年 3 月到 2025 年 7 月的 16 个月内，五家知名独立 AI
模型/产品公司以几乎完全相同的交易结构被大型科技公司吸收：Inflection AI
的 Mustafa Suleyman 和核心团队加入 Microsoft（2024 年 3 月），Adept AI
的创始人和约 80% 团队加入 Amazon（2024 年 6 月），Character.AI 的 Noam
Shazeer 回归 Google（2024 年 8 月），Covariant 的联合创始人加入
Amazon（2024 年 8 月），Codeium/Windsurf 的团队和知识产权被 Google 和
Cognition 拆分收购（2025 年 7 月）。

这些交易全部使用了同一个”反向
acqui-hire”结构——大公司雇佣团队并许可技术，但不直接收购公司，以此规避反垄断审查。这种结构本身就是一个信号：买方不认为这些公司的独立业务值得购买，他们只想要人才和知识产权。

其他案例同样指向同一个方向。Stability AI 的 CEO Emad Mostaque 在 2024
年 3 月辞职，公司在裁员后由新 CEO
接手，从开源模型转向商业授权模式，收入数据仍存疑。中国的
01.AI（李开复创立）在 2025 年 3
月完全停止了大型语言模型的预训练，转而销售基于 DeepSeek
模型的定制化解决方案。Humane 的 AI Pin 以 1.16
亿美元出售资产后永久关闭，远低于其约 2.4 亿美元的融资总额。

AI21 的具体情况与这批公司共享了同一组病因。根据以色列财经媒体 Globes
的系列报道，AI21 从 2017 年成立以来累计实际到位融资约 3.36
亿美元（OpenAI 的 630 亿和 Anthropic 的 460 亿的一个零头），估值峰值 14
亿美元，2025
年底就已开始寻求出售。公司先后推出 Jurassic-1、Jurassic-2、Jamba
等语言模型，在 2021 年时 Jurassic 还是 GPT-3 的有意义竞争者。但到了
2024-2025 年，当 GPT-4、Claude 和 Gemini
在多模态、推理、长上下文等维度上形成了体系化优势后，追赶的资本成本呈指数增长。

Globes 的报道原话是 AI21 “has struggled to sell its language
models”，“has not garnered great commercial
success”。公司从未公开披露收入，据估计在几千万美元量级。到 2025
年底，公司开始寻求出售，先后与 Nvidia 和 Nebius
谈判，两轮都没有达成。Nvidia 的谈判在 2026 年 1 月破裂后，AI21
专门发声明否认”收购谈判”，但措辞聚焦于”收购”一词本身，暗示
Nvidia 实际上提出了类似 acqui-hire 的方案但被拒绝。Nebius 的谈判在
2026 年 4 月启动，到 5 月也破裂，但双方签了 Maestro 的实施协议，说明
Nebius 认为买产品比买公司更划算。收购未果后，裁员和
pivot 几乎同步宣布。

公司声明中有一句话本身就是判决书：“公司将停止销售模型本身——这是其在
AI 领域专长的重要基础设施，但本身不是充分的收入来源。”

这句话概括了整件事的核心逻辑。

## 平台公司正在赌命

Meta 做的是同一逻辑下的相反选择。

根据 The Information、Reuters 和 NYT 的交叉确认，Meta 在 2026 年 4
月初强制将至少 1000 名顶级工程师调入 Reality Labs 内部新成立的 Applied
AI Engineering 部门。内部将这次调动称为”the Draft”（征兵），拒绝调动的工程师被威胁解雇。这种做法在硅谷极为罕见——在以人才流动性著称的科技行业，用解雇威胁强迫工程师转入特定团队，说明管理层将这件事的优先级放在了组织健康之上。

5 月 18 日的内部备忘录进一步披露：公司计划裁掉约 8000
人（占全球员工的 10%），同时将约 7000 名员工重新分配到四个新的 AI
组织中。6 月另有 6000 个开放岗位被关闭。HR
负责人 Janelle Gale 在备忘录中使用了”AI native design
principles”和”flatter structure with smaller teams of
pods/cohorts”的措辞——意思是公司架构本身正在被重新设计为 AI
原生的组织形态，减少管理层级，用小型的自主团队替代传统的层级结构。

员工反应可以用一份来自 SF
Standard 的采访来概括。一名在 Meta
工作了十年的员工在匿名条件下接受了详细采访，以下是部分原话：“I tend to
cry in the shower.” “This is as anxious and stressed as I have ever been
at a job.” “Even if we haven’t lost our jobs to AI yet, we’re being
commoditized in advance.” 该员工描述了一种”绞刑架幽默”文化——关于裁员的
meme
和跳舞骷髅在包括副总裁在内的聊天群中传播。大量员工请了心理健康假期，这被描述为一个”公开的秘密”。

另外两件事加剧了内部对立。第一是 Meta 在 4
月启动了员工键盘和鼠标操作的追踪计划，用于训练 AI
模型”理解人类如何使用计算机”。CTO
Andrew Bosworth
明确回复”在公司的笔记本电脑上没有选择退出的选项”，超过 1000
名员工签署了请愿书反对这一隐私侵犯。第二是部分员工开始手动关闭视频会议中的
AI 笔记转录功能，以便在会议中自由讨论裁员传闻——这意味着员工把公司自己的
AI 工具当成了监控基础设施。

Zuckerberg 在做的事情有一条清晰的历史参照线：Google 在 2022 年底
ChatGPT 发布后宣布的”Code Red”。当时 Sundar Pichai
将大量工程师从搜索、助手和其他部门重新分配到 AI 团队，数周内就推出了
Bard（后改名 Gemini）。Google 确实产出了有竞争力的 AI
产品，但代价是高端研究人员大量流失到 OpenAI 和
Anthropic——这些离开的人才后来直接成为了 Google AI 的竞争对手。Meta
目前的”征兵”机制比 Google 的”Code Red”更激进（强制 vs
自愿内部调动），人才流失的风险相应更大。

## 经济学逻辑：模型层的商品化

模型公司死亡和平台公司赌命，背后是同一个经济逻辑。

模型能力正在收敛。AI
基准评测平台 Artificial Analysis追踪了来自 51 个模型制造商的 516
个模型。它的 Intelligence Index 显示，GPT-5.5、Claude、Gemini、Grok 和
DeepSeek
在顶层形成一个紧密的集群，开源权重的模型在多个维度上已经接近甚至匹敌专有模型。差距仍然存在于特定的维度——尤其是推理和
agentic
任务——但在通用文本生成质量上的差异已经不足以支撑一个独立的商业模型。

token 定价的趋势方向更明确。2023 年 3 月 GPT-4
发布时定价约为每百万输入 token 30 美元，到 2025
年底同等级别能力的模型价格已降至约 0.30 美元，两年内下降了约 100
倍。对于同一个开源权重模型，Artificial Analysis 追踪到 21
家竞争性的推理服务商——产品完全一致，唯一的分化维度是价格和速度。

a16z 是这种判断最明确的表达者。在 2025 年底的 Big
Ideas 2026 中，a16z 的四个合伙人将”企业编排层”（Enterprise
Orchestration Layer）列为年度核心论点。2026 年 5 月的后续文章 From
System of Record to System of Intelligence
将论证表达得更直接：企业软件的价值位置正在从数据库层（CRM、ERP）向上迁移到能够读取这些数据、推理和采取行动的编排层。“基础模型本身不是一个进入市场的应用，就像
Oracle 的数据库引擎不是 CRM
一样。在模型和客户之间，存在着大量的、不光彩的和领域特定的工作——这些工作才是新的进入市场的应用层。”

SaaStr 的 Jason Lemkin 提供了一个具体的微观案例：他的公司将
Salesforce 的席位数从 10+ 个减少到 2 个人工席位加 1 个 API
席位，但总支出从每年 1.2 万美元上升到 2.2
万美元。模型层变便宜了；编排层捕获了更多的价值。

## 什么能活下来

如果模型层在商品化，那么什么样的独立模型公司还能活？

从反例中可以提取出一组护城河类型，每个存活的公司在其中至少占据一条，通常占据多条。

第一，主权/地缘背书。Mistral AI 的估值达到了 140
亿美元，很大程度上不是因为它的模型比别人的好，而是因为它把自己定位为欧洲
AI 主权的代表。ASML（荷兰半导体设备巨头）投资了 15 亿欧元并持有 11%
的股份。Mistral 从法国和瑞典政府获得了建立自有数据中心的支持。Cohere
从加拿大政府获得了 2.4 亿美元公共资金用于国内 AI 计算基础设施，并在 2026
年 4 月宣布与德国的 Aleph Alpha 合并，构建了一条跨大西洋的 AI
主权叙事。DeepSeek 的隐含中国政府和 PLA
关联提供了类似的背书和国内市场访问权限。AI21
是以色列公司，但没有相应的主权叙事。

第二，分销渠道的所有权而不是模型质量。Anthropic 的估值达到 3800
亿美元，不是因为 Claude 的模型能力独步天下，而是因为它同时嵌入了
AWS（Amazon 累计投资 80 亿美元）、Google Cloud（25 亿美元以上）和
Microsoft Azure（150 亿美元交易），并获得了美国政府 2
亿美元国防合同。它的 Model Context Protocol 正在成为连接 AI
模型和外部数据的行业标准。AI21 的模型在 AWS Bedrock
上可用，但这只是一条渠道，不是渠道所有权的任何一种形态。

第三，耐心资本与非 VC 激励结构。DeepSeek 的母公司 High-Flyer
是一家中国量化对冲基金，它不需要从模型中产生商业收入。DeepSeek
明确表示”没有立即商业化的计划”。Anthropic 的融资规模（300 亿美元系列
G）创造了数年的发展空间。Mistral
的战略投资者（ASML、Microsoft）的利益与长期定位一致，而非短期退出。相比之下，AI21
的 3.36 亿美元 VC
融资规模不足以成为耐心资本——一旦模型销售被证明不可行，VC
回报的逻辑就需要一个 pivot 或一个退出，两者最终都发生了。

第四，垂直专业化而非通才竞争。Cohere 的 ARR 达到了 2.4 亿美元（从
2025 年 5 月的 1
亿美元在不到一年内翻倍），通过放弃前沿模型的基准竞赛，聚焦于受监管行业（金融、医疗、国防）的企业部署。其
North 平台为无法使用公有云 AI 服务的企业提供安全的 AI 工作空间。Cohere
的定位使它在切换成本高、合规要求构成天然进入壁垒的领域获得了优势。AI21
从未专业化过——它一直试图以通才模型提供商的身份竞争。

第五，开源作为生态系统策略而非营销。Mistral 和 DeepSeek
发布开源权重模型（分别使用 Apache-2.0 和 MIT
许可），从而建立了开发者社区的锁定效应。但开源本身不够——01.AI
也是开源的，仍然不得不放弃模型建设。开源仅在与其他优势叠加时才构成护城河（Mistral
的主权背书，DeepSeek 的成本优势）。

即使拥有这些护城河的公司，也需要作出同一个选择——它们无一例外地在主动向上（进入应用层）或向下（进入基础设施层）移动。Anthropic
的 Claude Code 是开发者工具而非模型 API。Mistral 的 Le Chat
是消费者产品。Cohere 的销售对象是解决方案而非
API。纯粹销售模型访问权限的公司，无论规模大小，都正在被证明是一个在结构上不可持续的商业模式。

## 尾声

兜了一圈，结论是简单的。

模型层在商品化。这件事已经在价格、能力和资本流向三个维度上同时发生，不是预测，是进行时。独立卖模型的路已经走不通了——AI21
的裁员声明本身就是在替整个行业做总结：“模型本身不是充分的收入来源。”

对 builder
来说只剩两条。第一，模型选择做成运行时优化参数，不要做成架构决策，编排层永远保持多供应商。第二，值钱的东西在你的编排层里——领域逻辑、用户上下文、多步骤工作流自动化——这些东西模型再强也替不了你。