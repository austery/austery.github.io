---
author: The MAD Podcast with Matt Turck
date: '2026-05-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Gs2styCcwro
speaker: The MAD Podcast with Matt Turck
tags:
  - enterprise-ai
  - token-economics
  - agentic-workflow
  - headless-software
  - future-of-work
title: 2026 企业级 AI 现状：Aaron Levie 谈 Token 成本、无头软件与职业转型
summary: Box 首席执行官 Aaron Levie 深度解析企业级 AI 部署的残酷现状。他指出，AI 技术的爆发式进步反而由于导致架构过时而减缓了企业落地。文章探讨了 Token 成本从补贴转向真实支出后的预算模型变革，提出了‘无头软件’与‘内部 FDE’（全职部署工程师）的崛起，并利用杰文斯悖论论证了 AI 如何在提升效率的同时驱动更多就业需求。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Aaron Levie
companies_orgs:
  - Box
  - OpenAI
  - Anthropic
  - Microsoft
products_models:
  - GPT-4o
  - Claude
  - Cursor
media_books: []
status: evergreen
---
### 创新悖论：快速迭代如何反向阻碍企业落地

在硅谷工程圈与全球 2000 强企业（Global 2000）之间存在着显著的**认知鸿沟**。Aaron Levie 认为，Box 的核心使命是作为“技术桥梁”，将尖端的突破转化为现实世界的应用。目前的痛点在于，AI 领域的突破速度已经超过了客户实施任何标准架构的能力。

这种**甜蜜的烦恼**（Bittersweet Paradox）表现为：当你还在部署 GPT-5 时，GPT-5.5 已经让上周建立的架构显得陈旧。这种缺乏“稳定环境”的现状，使得企业的变更管理（Change Management）变得异常漫长。尽管“聊天机器人”模式已在企业内初步铺开，但真正的**智能体化工作**（Agentic Work）才刚刚进入“第一天”。

<details>
<summary>Original English Source</summary>

Let's just say you took GBT55 or Opus and you just snapped the line right now. You could probably do this diffusion in like two years or three years and we could probably all do the change management like collectively as an ecosystem. The problem is is the breakthroughs keep happening faster than the customer can implement any kind of standard architecture and those breakthroughs often times make obsolete the last thing you implemented. It's this really bittersweet thing which is like the technology is getting so advanced that it makes obsolete the prior thing that you implemented which actually means that the roll out takes longer. ... It's not just Silicon Valley versus everybody else. It's it's sort of Silicon Valley engineering versus everybody else. ... The bigger question is like Silicon Valley versus versus sort of non-engineering knowledge work. And that's like the big question right now which is which is what is this sort of path from AI coding agents that we know have totally you know reached escape velocity to now agentic work in the in the rest of the organization.

</details>

### Token 经济学：从资本补贴转向企业真实预算

企业级 AI 部署面临的最直接瓶颈是 **Token 成本**。过去几年，行业处于一种“隐性补贴”状态，许多工具将昂贵的推理成本包含在固定的订阅费中。然而，随着智能体具备处理更复杂任务、使用更大上下文窗口的能力，单次任务的算力成本可能飙升至 1000 美元，这彻底打破了传统的**人头计费模型**（Per-user-per-month pricing）。

这种转变迫使 AI 成本从 IT 预算（通常占营收的 3-7%）溢出到业务部门（Line of Business）的 **运营支出**（Opex）中。这意味着未来的首席营销官（CMO）需要像管理广告投放一样管理算力预算。目前市场极度缺乏测量 **Token 投资回报率**（ROI on Tokens）的工具。Aaron 预测，这催生了一个价值 50 亿美元的 **AI 算力 ERP** 创业机会。

<details>
<summary>Original English Source</summary>

The cost of tokens and budgeting and budget planning ... probably is at least one-third of the hottest button issues that relate to AI. ... We've just gone from a pricing model of a chatbot ... to that pricing model no longer working when one coding agent could be consuming $1,000 of compute on a single task. ... IT spend is basically somewhere between like 3 to 7% of corporate revenue. ... It's going to escape that and it's going to move to the line of business budgets. ... One of the things that we don't have tooling for is like how do you measure the ROI on the tokens? ... You probably need new pieces of software. Probably a $5 billion startup waiting to happen just in like ERP for your AI compute.

</details>

### 无头软件的兴起：从图形界面到 AI 消费驱动

**无头软件**（Headless Software: 仅通过 API 与外界交互，不强制要求人工界面的软件架构）正成为企业级软件的必然趋势。Aaron 认为，未来的软件将遵循**双重模型**：
1. **座席计费模式**：针对人类用户，保留传统的图形用户界面（GUI）。
2. **消耗计费模式**：针对 AI 智能体，通过 API 进行大规模调用。

在 Box 的实践中，这意味着 AI 可以“无头”地处理法律合同、审计数据房，而无需像人类那样点击界面。虽然人类依然需要图形界面进行复杂的决策和交互，但从**调用容量**来看，智能体对系统的访问量将是人类的数百倍。

<details>
<summary>Original English Source</summary>

I actually totally believe in headless software. ... If I'm going to go and do a complex query that involves Box data, Salesforce data, Workday... I'm going to do that fully headlessly. ... By volume agents are going to be banging on these systems far more than humans ever did. ... Any enterprise software in three years from now... will have a seat business model ... and it'll have a consumption business model. ... Everything you would ever want to do with your enterprise content, you should be able to do via an external agentic interface. ... Headless users might use our search tool very aggressively. So we have to inform them as they're doing their searches how to think about this certain context inside these files.

</details>

### 杰文斯悖论与就业：为什么 AI 不会导致大裁员

针对“AI 夺走工作”的恐惧，Aaron 引用了**杰文斯悖论**（Jevons Paradox: 随着技术进步提高资源利用效率，该资源的总体消耗量反而会因为需求增加而上升）。虽然 AI 大幅降低了工程、设计和法律工作的单次成本，但这反而会释放出那些原本因为昂贵而从未被启动的**潜在项目**。

例如，原本雇不起设计师的小企业，现在会因为 AI 效率提升而开始雇佣一名设计师来操纵十个 AI 智能体，从而开启全新的营销业务。企业不再面临“裁员”，而是面临**职责重构**。新的角色正在崛起，例如**内部 FDE**（Forward Deployed Engineer: 驻场开发/部署工程师，负责在业务部门内部调优 AI 智能体），这种高度技术化的角色将成为未来企业的核心基石。

<details>
<summary>Original English Source</summary>

I'm like a complete Jevons Paradox pill person. ... What's going to happen now with agents is all of a sudden all of those other companies are going to light up far more technical projects and technical work ... because for the first time ever one of their engineers now has the capacity of three or five or 10. And so that's going to get them to sign up for way bigger projects. ... One of the hottest topics also is like what is this new internal FDE role or external FTE role like what is the technical talent I need to go and actually help me deploy these types of systems. ... This is why the job argument ends up falling on its face once you start to see actually how AI is rolling out in a lot of organizations.

</details>

### 职业未来证明：利用 VC 补贴进行自我进化

对于大型企业的普通员工，如何在这个 Agentic 时代生存？Aaron 的建议非常务实：**利用风险投资的补贴**。目前的 AI 工具（如 Cursor, Claude Co-worker, Perplexity）大多仍处于高额补贴阶段，员工应该花费 5-10% 的时间成为这些工具的“高级用户”。

更深层的转型在于思维方式的改变。员工应当思考：如果我有一个**首席幕僚**（Chief of Staff）可以处理无限量的任务，我会如何重构我的工作流？这不再是简单的“提示词工程”，而是如何通过 AI 产生真正的价值。Aaron 透露，即使是他自己，在深度使用 AI 后发现，AI 创造的巨大价值反而让他产生了雇佣更多人类来处理这些产出物的冲动。

<details>
<summary>Original English Source</summary>

As an employee, I would be spending 5% of my time, 10% of my time... just getting really good at this stuff. ... You have to use the tools. ... Stop one of your cable subscriptions to do this and just start to use agents a lot. ... Please use the VC subsidies to your advantage as much as possible. ... What if I just did have a chief of staff that I could throw any task to? ... You'll see lots of areas actually where you should hire more people because you'll like 'oh my god this thing is spitting out incredible gold mine of value but who's going to go and run with that?' That's the next set of jobs.

</details>

### 市场格局：垂直初创企业的“桥梁”红利

尽管大模型厂商（Labs）正在不断向上层应用渗透，但 Aaron 对**垂直领域初创企业**保持乐观。他认为，AI 的能力与最终用户的业务工作流之间始终需要一个“桥梁层”。

除非 OpenAI 或 Anthropic 愿意为每一个细分垂直行业雇佣成千上万的专家，否则这种针对具体业务背景、数据集成和变更管理的**深度定制化工作**（Bespoke Workflows）依然是初创企业的蓝海。在这个过程中，资本主义会自动平衡生态：如果某个模型实验室过于排外，其他竞争者就会通过更开放的生态策略取而代之。

<details>
<summary>Original English Source</summary>

I remain pretty confident and optimistic on the need for a kind of a bridge layer from the AI capability to the end user workflow. ... Unless the labs build out literally the equivalent of hundreds or thousands of people for every single vertical... there's actually a lot of opportunity in that bridge area. ... The hyperscalers actually had to figure this out... where are they going to compete in the applied layer versus where are they going to partner. ... The compression of all of that into applied use cases is where the vertical players are going to have their opportunity to compete.

</details>