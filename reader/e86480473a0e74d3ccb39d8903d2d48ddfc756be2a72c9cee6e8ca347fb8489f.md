---
author: AI Engineer
date: '2026-05-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=VMemhtlsoNk
speaker: AI Engineer
tags:
  - agentic-workflow
  - software-engineering
  - automation
  - engineering-management
title: 告别敏捷仪式：构建AI驱动的“后工程师”工程组织
summary: 本文通过PFF工程团队的实战案例，探讨了如何将传统的工程组织转型为由AI代理驱动的自动化组织。通过弃用Scrum、缩短开发流程、引入自动生成文档和代码审核，团队实现了开发效率的10倍提升和部署频率的25倍增长，同时提升了产品质量与客户满意度。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Mike Spitz
companies_orgs:
  - PFF
products_models: []
media_books: []
status: evergreen
---
### 组织转型的逻辑背景与瓶颈突破

PFF 是一家专注于体育数据的公司，主要为 NFL 和 NCAA 球队提供数据决策支持，同时也运营 fantasy football 和体育博彩业务。该工程组织由 20 名工程师组成，采用完全分布式的协作模式。

过去，工程团队面临严重的瓶颈：即便拥有各类传统的工程师福利和待遇，但交付节奏依然无法追赶竞争对手。我们意识到，工程团队本身已成为制约交付的瓶颈。随着 **Cloud Ops**（云运营）工具的兴起，我开始尝试通过两个工程师（一名资深前端，一名资深全栈）进行实验，将传统的“提升工程师产出”转变为“加速代理效率”。

结果是显著的：相比原先 10 人的团队每 5 天部署一次，这组由代理驱动的工程师实现了每天部署 5 次的频率，部署频率提升了 25 倍，且经过综合代码复杂度和票据数量评估，产出效率提升了 10 倍。更重要的是，产品质量从过去的 7.5 分（满分 10 分）提升至 8.6 分，真正交付了用户所需的功能。

<details>
<summary>Original English Source</summary>
PFF is a sports data company. We help NFL and NCAA teams figure out what they should be doing and we also have a consumer arm which does fantasy football, sport betting... We're fully distributed engineering team... The issue that we had was we were 200 employees around 20 engineers and we were falling behind our competitors. 

So, really the question is asking was instead of figuring out how we can help engineers go and output more, how do we help make the agents quicker? ... So, I just want to go straight into how the case study ended up. So, we had a 25 times more of deploys. So, the two engineers were deploying five times every day and the other team was a team of around 10 engineers. They're doing it pretty much one deploy every five days... We basically blended the number of tickets with the code complexity and we found that their output was 10x.
</details>

### Scrum 的终结：构建极致敏捷流程

为了实现这一效率跨越，Scrum 在我们的组织中未能延续。我们不仅关注工程层面的交付增益，还从流程立场进行了彻底的重新评估。为了尽可能追求极致的交付速度，我们消除了冗余的沟通环节：无需项目经理，无需多次“传声筒”式的游戏。

我们现在的流程极其基础：
* **每日短会（Huddles）**：每隔一天进行一次半小时到一小时的沟通，仅限工程师、产品经理和设计师。目标是分享进展、获取即时反馈。
* **MVP 交付**：尽可能快地部署到生产环境，以 MVP（最小可行性产品）状态获取最大反馈。
* **Agentic 研发流程**：
    1. **Spec & Interview**：由代理对我们进行访谈以生成需求规格。
    2. **LDD (Lightweight Design Document)**：轻量级设计文档由代理编写，并分析以往所有 LDD 的风格，确保产出符合团队既有规范。
    3. **自动执行**：文档分发并获得工程反馈后，自动创建票据和 PR。

这意味着我们不再需要进行耗时的 Sprint Planning（冲刺计划），因为预估票据耗时不再具有实质意义。同时，Daily Standups（每日站会）也被自动化取代——票据状态根据 PR 的状态（In Progress, Review, Merged, Closed）自动更新。

<details>
<summary>Original English Source</summary>
So, Scrum did not survive. We were basically having a look not just on an engineering front and all of the delivery gains from that, but also from a process standpoint. And so, no need for a project manager. We don't need to play multiple games of telephone and everything we're doing was optimizing to be as quick as possible. 

Engineers aren't the bottleneck. So, we don't need to have all the old ceremonies that we had before. So, what did we have? It looks pretty basic. We basically had huddles... And that development flow is we have a spec. ... We get feedback on that spec and then we make a lightweight design document. That's done by the agent. ... And then at that stage we automatically create all the tickets and then the PRs after that. So, sprint planning we don't have sprint planning anymore cuz we don't need to have an hour going and basically estimating tickets cuz those estimations don't really make any difference.
</details>

### 工程自动化与人员职能的重塑

在实施过程中，我们必须诚实地面对：并非所有工程师都能适应这种全新的“跑车”驱动方式。在 AI 驱动的工程时代，好奇心强的工程师将会脱颖而出——他们倾向于花费时间去理解系统的底层构建方式，而不是仅仅被动等待指令。而那些依赖于严格、预定义 **Spec**（规格说明书）的老派工程风格，将会面临巨大挑战。

我们在自动化方面构建了清晰的边界：
* **Verifiable Tasks**：专注于可验证、确定性的任务。
* **Agentic Code Review**：利用代理处理那些工程师最讨厌反馈的琐碎事项，如变量命名、风格一致性等。通过将这部分意见从人工审核中移除，不仅避免了情绪化反馈，也让工程师能够专注于架构层面的大局观。
* **QA 代理**：每次 PR 合并后自动部署至 Staging 环境，触发 QA 代理根据票据和验收标准进行测试，并通过反馈标记问题，未来将实现自动生成修复 PR 的自愈闭环。

对于工程师的职能，重点在于 **LDD** 的质量，通过极具预见性的设计文档，在起始阶段就规避过度设计和无效代码。

<details>
<summary>Original English Source</summary>
The big big thing here though is not everyone can drive a sports car. ... And this new era is going to be hard for a few engineers. And I think the type of engineer will there really strive is one who is curious. ... Next thing is the agentic code review. ... we use agents to do the code reviews that engineers hate getting any feedback from. ... We have a QA process also. So, what happens is um whenever we merge a PR, it automatically deploys onto staging. ... I'm aiming in the next a couple months is to then have an agent have a look at those tickets, find out where the acceptance criteria hasn't happened, and then automatically create the PRs.
</details>

### 实施指南：从小范围迭代到工程文化

想要在组织中实施这一转型，我建议遵循以下原则：

1. **从非关键系统入手**：在 नवंबर（11月）开始时，我通过非关键功能进行小规模验证，即使出错也不会造成实质损失。待模式成熟后，再应用至拥有 1 亿次年浏览量的核心系统中。
2. **渐进式方法**：不要试图同时让所有工程师都切换。这需要缓慢的阶段性方法，并依赖于最好的工程师作为先锋。
3. **消除冗余流程**：询问每一个现有的会议或流程，其存在的目的是为了帮助，还是仅仅因为惯例？如果无法证明其有助于提升产出，则予以剔除。
4. **文化编码**：将团队的软件设计模式编码到代理的 **Skills** 中。例如，我们在构建 API 时强制使用服务存储库模式（Service Repository Pattern），确保代理产出的代码始终与团队 ethos（精神风貌）保持一致。

这并非一夜之间的转型。对于规模较大的企业，这确实非常困难，但对于小团队而言，这不仅是机遇，更是为了不被竞争对手甩在身后必须采取的行动。

<details>
<summary>Original English Source</summary>
So, how would I recommend attacking this? You should go see your engineering development life cycle like a factory. ... The one thing I would flag is I'm not a big fan of um a consuming other people's skills if they have strong software kind of opinions that are in contrast to the today's engineering org. ... Things you should not do is to try and onboard everyone at the exact same time. ... I think those small companies are at a huge advantage of the big enterprise companies cuz it's really easy for me to scale this out when I've got 20 engineers. It's really hard for me to scale this out if I was in charge of 100 or if I was in charge of 1,000 engineers... But you don't want to be too shy.
</details>