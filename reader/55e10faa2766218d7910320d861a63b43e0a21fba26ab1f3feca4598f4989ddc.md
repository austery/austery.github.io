---
layout: post.njk
source: https://yage.ai/share/saas-ai-data-pricing-20260519.html
speaker: yage.ai
title: |-
  当数据保护变成定价功能：SaaS 行业 AI
  数据策略的三代演化
date: '2026-05-19'
summary: 随着大模型普及，SaaS行业AI数据策略演变为三代：从早期的“土地掠夺”式全量训练，到“默认收集+隐藏退出”的正常化，演进至当前的“分层定价（tier-gating）”。企业开始将“数据不用于AI训练”从基础合规义务转化为企业级产品的溢价功能。这一趋势不仅造成了数据政策碎片化，更增加了中小企业的合规成本与数据主权风险，迫使采购者在企业级服务评估时，必须将AI数据政策视为核心定价维度。
area: tech-engineering
category: ai-application
tags:
  - ai-data-policy
  - saas-strategy
  - tier-based-pricing
  - data-sovereignty
  - ai-training
people:
  - Martin Woodward
  - Bill Staples
  - Simon Willison
companies_orgs:
  - Atlassian
  - GitHub
  - Slack
  - Figma
  - Salesforce
  - Google
  - Microsoft
  - GitLab
  - Notion
  - Dropbox
  - ServiceNow
  - OpenAI
  - Zoom
products_models:
  - Jira
  - Confluence
  - Copilot
  - Einstein AI
  - Rovo
  - Google Workspace
  - Microsoft 365 Copilot
  - Gemini
media_books: []
draft: true
status: evergreen
---

到 2026 年 8 月 17 日，如果你在 Jira 里记录过一个 sprint 计划，或在
Confluence 里写过一页内部文档，Atlassian 会默认把这些数据用于训练它的 AI
产品。根据 Atlassian
官方 FAQ，metadata 的收集对 Free、Standard、Premium
层级的客户是强制的——没有关闭开关。只有升级到 Enterprise（最低 801
用户，定制报价）才能退出。

同一周，GitHub
Copilot 的 Free、Pro、Pro+ 用户也被默认纳入 AI 训练数据管道。Slack
在 2024 年已经做过一轮类似操作，被
Ars Technica 曝光后修改了措辞。Figma
的非 Enterprise 用户从 2024 年 8 月起就被默认训练。Salesforce
的数据也一直在被用于训练 Einstein AI 模型。

另一边，Google
Workspace 在合同里写明不用客户数据训练底层模型。Microsoft
365 Copilot 的企业数据保护承诺同样写在 Data Protection Addendum
里。GitLab
把这个”不训练”做成了核心差异化策略，连续发 blog 直接对比 Atlassian
和 GitHub。

表面上看，这是一个隐私危机。但把这一组事件放在一起看，它们在讲一个更具体的产业变化：企业
SaaS 正在把数据保护从合规义务转化为定价维度。 你的数据不被用于
AI 训练，正变得和 SSO、审计日志、SLA
一样，是一个需要花钱购买的功能。

## 三代演化：从 land grab 到
tier-gating

这个转变不是一次性的，而是经过了三代政策试错。

第一代是 Zoom 的 land grab（2023 年 7 月）。 Zoom
更新了服务条款，赋予自己使用”service-generated data”训练 AI
的广泛权利，且不提供任何客户级的 opt-out。Mozilla
基金会发文质问，社区猛烈反弹。Zoom 在一个月内退让，在条款里加粗声明不用音频、视频、聊天内容训练
AI。

Zoom
这一轮的教训很清楚：完全不给退出机制，在舆论上不可行。但它证明了一个关键点——即使用户反对，也不会大规模迁移。Zoom
的用户量在事件后没有明显下降。这给了后来者一个重要的信号：舆论反弹是暂时的，锁定效应是持久的。

第二代是 Slack 的悄悄正常化（2024 年 5 月）。 Slack
的隐私原则页面里有一句话：“To develop AI/ML models, our systems analyze
Customer Data (e.g. messages, content, and files) submitted to Slack.”
被一个 Hacker
News 用户在深夜发帖爆出来后，社区炸了。Ars Technica
报道的标题是”Slack users horrified to discover messages used for AI
training”。

Slack 的回应策略和 Zoom
不同。它没有删掉政策，而是修改了措辞——把”AI/ML
models”改成了”non-generative AI/ML models for features such as emoji and
channel recommendations”。官方发了 blog 强调”不用客户数据训练 LLM”。但
opt-out 机制仍然极其笨重：需要 workspace owner 发邮件到
[email protected]，写特定的 subject
line，然后等人工处理。没有自助按钮。

这一轮比 Zoom 进了一步：它证明了”默认收集 + 提供理论上的退出 +
把退出路径藏深”是一个可操作的模板。Slack 没有遭受 Zoom
级别的舆论危机，也没有在用户量上受损。HN 和 Reddit
上的怒气很大，但实际迁移的案例极少——r/Slack 上一个帖子专门问”Are people
leaving Slack?“，多数回复的结论是”不会，因为迁移到 Matrix/Element
太麻烦”。

第三代是 Atlassian 和 GitHub 的系统性 tier-gating（2026
年）。
这一轮更精细，也更激进。不是一刀切的默认收集，而是按付费层级分层开放数据保护。

Atlassian 把数据分成两类：metadata（story points、sprint 日期、SLA
值、页面复杂度评分、跨客户的高频搜索词）和 in-app content（Confluence
页面内容、Jira issue 描述和评论）。前者对 Free、Standard、Premium
层级强制且不可关闭；后者默认开启但可关闭。只有 Enterprise
才能完全退出。数据保留最长七年。更关键的是，Atlassian
的 Teamwork Graph 连接器会把 Slack、Figma、Google Drive、Salesforce 等
50+ 第三方工具的关系和活动信号也卷进元数据收集范围——这意味着暴露面不限于
Atlassian 产品本身。

Atlassian 做了一件之前的厂商没有做的事：逆转了此前的明确承诺。在 2025
年 11 月之前，Atlassian 的官方帮助页面标题就是”Rovo
and Atlassian Intelligence customer data is not used for AI model
training”，正文写的是”Customer data…is never used to train, fine-tune,
or improve AI models or services.” 从”never”到”by default, unless you
pay more”，是一个硬翻转。

GitHub Copilot 同期的政策变化结构类似：Free、Pro、Pro+
用户的交互数据默认用于训练，Business 和 Enterprise
客户受合同保护。Martin Woodward 在 HN
评论里确认了这条边界。

## 谁在训练，谁不在训练，以及为什么

行业在 AI 数据策略上出现了明显分裂。

默认收集（或默认训练）：Atlassian、GitHub
Copilot（非 Enterprise）、Slack（非生成式 ML）、Figma（非
Enterprise）、Salesforce、LinkedIn。

明确不训练（合同级别承诺）：Google
Workspace、Microsoft
365 Copilot、GitLab、Notion、Dropbox、ServiceNow、OpenAI
Enterprise。

这个分裂不是道德立场差异。选择”不训练”的公司，各自有不同的理由。

Google 和 Microsoft 同时是 AI
基础设施提供商。它们的底层大模型（Gemini、与 OpenAI
的深度绑定）已经有足够多的训练数据来源：公开互联网索引、消费者产品数据、合成数据、许可协议。企业客户数据对它们模型质量的边际贡献极小，但信任风险极大——一旦爆出企业数据被用于训练，Fortune
500 CIO 的集体出走是它们承担不起的。它们选择把承诺写进合同（CDPA 的
Training Restriction 条款、DPA），不是道德选择，是商业计算。

GitLab 的处境不同。它不开发底层模型，AI 功能全部通过
Anthropic、OpenAI、Mistral
等第三方模型提供，角色是中间层。它收集客户数据训练自己的模型本身就不在其业务范围内——但这恰好让它可以把”不能”包装成”不愿”，并直接对比
GitHub 和 Atlassian 做差异化叙事。

另一边，Atlassian 和 GitHub 的处境迫使它们更激进。它们的 AI
产品（Rovo、Copilot）需要在功能上跟上 Google/Microsoft
的步伐，但没有独立的训练数据管道。专有工作流数据是它们唯一的差异化来源。对小客户默认收集、对大客户提供合同级保护，是它们在”需要训练数据”和”不能失去大客户信任”之间的折中。

## 更深一层：隐私变成定价功能

到这里，故事还停留在隐私政策的层面。但从商业逻辑看，真正发生的事情更根本。

SaaS
行业一直以来把数据保护当作基础设施承诺：你的数据在云上加密存储，符合 SOC
2、ISO 27001，这是 everyone gets it 的基础条款。但现在 Atlassian
做了一个概念上的重新分类：数据不被用于 AI
训练，不是一个基础设施承诺，而是一个功能特性。和 SSO、审计日志、SLA
一样，你需要在某个 tier 以上才能获得。

这个转变之所以重要，不是因为它侵犯了隐私，而是因为它创造了一个新的定价维度，而这个维度完全没有市场定价机制。Atlassian
单方面决定了”你的 metadata 值多少钱”，隐含在 tier
价格差里，但买家没有任何方式独立评估自己数据的价值，也无法谈判。如果你是
Premium 客户，Atlassian 强制收你的
metadata，你不满意但没有议价能力——价格表上没有”数据贡献折扣”这个行项。

这不是 Atlassian 一家的问题。从 Zoom 到 Slack 到 GitHub 到
Figma，整个行业正在形成同一种默认模式：中小客户用数据支付隐性价格，大客户用金钱购买数据主权。这和
2010 年代开源许可证分裂（MongoDB、Elastic、Redis 转向 BSL/SSPL
限制云厂商免费使用，而 Linux 基金会、Apache
项目坚持传统开源）的结构一模一样。市场不会出现某一方赢家通吃，而是会分层共存——数据保护成为企业级产品的溢价特性，中小客户的数据贡献成为平台的隐性支付方式。

和开源分裂导致 license compatibility 噩梦一样，企业正在面临跨 vendor
的数据政策碎片化——你的 Jira 元数据进了 Atlassian 的训练池，你的 GitHub
交互数据进了 Microsoft 的模型，但你的 Google Docs 内密和 GitLab
代码受到了保护。谁能在组织层面管理这个碎片化的暴露面，目前没有现成的答案。

## 对买方的实际影响

即使从纯商业角度（搁置隐私和伦理讨论），这个趋势对买方的实际影响也值得认真对待。

最直接的影响是合规成本的分层。Atlassian
之前所有客户享受同一套数据承诺——“never used to
train”。现在数据保护被拉到了 Enterprise
层，意味着大量中小企业和团队面临一个二元选择：要么接受数据被训练，要么承担巨大的升级成本（Enterprise
最低 801 用户，定制报价）。这不是一个温和的价格梯度，而是一个断崖。

其次，这种政策变化的速度正在加快。Zoom 用了 1 个月退让，Slack 用了 1
周修改措辞，GitHub 给了 30 天 opt-out 窗口，Atlassian 给了 90
天审查期。每一次都比上一次更”规范”，但本质上都是单方面修改条款、由客户承担注意和应对的负担。企业
SaaS 合同的切换周期通常是 12-36
个月——当你意识到需要反应时，你可能已经被锁在了你不想要的条款里。

还有一层更隐蔽的风险。Atlassian 的 metadata 定义包括了 story
points、sprint 结束日期、SLA
指标、页面复杂度、语义相似度分数。这些数据去标识化后在单个维度上看起来无害，但维度足够多时，模式和结构的重建是可行的。当
Atlassian 拥有跨 300,000 个组织的聚合数据时，去标识化的承诺能否抵御维度足够多的模式重建，是一个工程问题，不是法律问题。

评估任何 SaaS 公司 AI
数据风险时，最有效的预判变量不是它的隐私政策措辞，而是它在 AI
技术栈中的位置：距离拥有底层基础大模型越远的公司，数据收集政策就越激进。这个规律之所以有用，不是因为它绝对准确，而是因为它把注意力从公关声明转移到了商业结构上——后者更难伪装。

## 什么还没发生

三个重要的事情还没有发生。

第一，没有出现大规模的企业迁移。Hacker News 上 Atlassian
政策讨论的帖子有 604 个 upvote 和
136 条评论，GitHub Copilot
的讨论有 745 个 upvote 和 316
条评论——情绪很强烈。但实际验证的迁移案例极少。Simon Willison 在 HN
评论里说过一句切中要害的话：“I don’t think there’s nearly as much value
in this stuff as AI training data as people often assume.”
如果这些数据对 AI
训练的价值本身被高估了，那围绕它的恐慌可能也是过度的。

但缺乏迁移不意味着缺乏影响。迁移成本太高——Jira、Confluence、Slack
深度嵌入企业工作流，迁移是 6-12
个月的项目级工作。大多数组织不会仅因数据政策而启动迁移，但会在合同续约时把
AI 数据政策加进谈判条款里。这个影响的滞后性意味着 2027-2028
年才是真正的压力测试期。

第二，没有出现统一的监管回应。GDPR 写于 LLM 之前。Atlassian
用客户数据训练 AI 时，从 data processor 变成了独立的 data controller——这是
Seibert Group 法律分析中识别出的最实质性的 GDPR 风险。但 EDPB
没有就此发布过具体指导意见，成员国 DPA 也没有对 SaaS 厂商 AI
训练行为发过正式执法行动。EU AI Act 要求对高风险 AI
系统有透明度义务，但一个 SaaS 厂商用聚合客户 metadata
训练推荐模型是否构成高风险，法律上远未确定。

第三，没有出现跨厂商的数据政策兼容标准。今天一家同时使用
Jira、Slack、Figma 和 GitHub 的组织，面对四个不同的 AI
数据政策，四个不同的 opt-out
机制，四个不同的数据保留期。谁是组织内部负责统一管理这个暴露面的角色？目前没有——这不是
CISO 的传统职责，不是 CPO
的传统职责，也不是采购的。市场和监管都还没有追上这个碎片化的速度。

## 结语

GitLab CEO Bill Staples 在 LinkedIn
上反复重申的立场代表了这个分歧的一端：合同级别的无条件承诺，任何
tier 都不训练，AI 供应商也被合同禁止使用客户数据。Google 和 Microsoft
在架构层面做了同样的事——把企业数据处理管道和消费者数据处理管道物理隔离。这些做法比
opt-out toggle
贵得多，但它们代表了一种选择：把信任建在不可覆盖的约束上，而不是可更改的设置上。

另一端是一个更现实的问题。如果中小企业既负担不起 Enterprise tier
的溢价，又没有能力做完整的 vendor
migration，它们唯一的选择就是接受数据被训练。这个群体恰好在法律和舆论上都缺乏议价能力。

这个张力在短期不会自行消解。监管介入的速度、企业迁移的意愿、以及中小客户是否真的在乎，决定了
2027-2028 年的产业格局。但有一条已经可以确定：在采购任何企业 SaaS
之前问一句”你的 AI 数据政策是什么”，不再是吹毛求疵——它是和问”你是否支持
SSO”一样基本的问题。