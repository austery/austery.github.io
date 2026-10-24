---
author: AI Engineer
date: '2026-07-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=q2JrUKBMf0w
speaker: AI Engineer
tags:
  - llm-evaluation
  - agent-evaluation
  - agentic-workflow
  - observability
title: 评估的未来：从大模型裁判到智能体裁判
summary: Arize AI 联合创始人 Aparna Dhinakaran 探讨了 AI 评估（Evals）的演进趋势。随着 Frontier 模型引入工具调用和推理，评估对象从单一 Prompt 升级为复杂的长周期 Agent。针对动态且不可预测的执行轨迹，传统基于固定标准的大模型裁判已无法满足需求，而自适应的智能体裁判（Agent as a Judge）将成为未来趋势，Arize AI 对此发布了主动分析并修复代码缺陷的 Signal 智能体。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Arize AI
  - Uber
  - Snorkel
  - Anthropic
  - OpenAI
products_models:
  - Signal
media_books: []
status: evergreen
---
### 评估的演进：从辅助技能到AI团队的核心战略

大家好，我是 **Arize AI**（Arize AI: 专注于AI可观测性与评估的平台）的联合创始人 **Aparna Dhinakaran**。在过去，**大语言模型评估**（LLM Evaluation: 评估大语言模型输出质量与性能的系统性方法）可能只是每个产品经理（PM）和 AI 工程师需要学习的一项辅助性新技能，而如今，它已经变成了每个严肃的 AI 团队都在全力押注的核心战略。我们非常幸运能够与世界上最优秀的 AI 团队合作，这让我们不仅能在一线亲眼见证他们在构建和发布智能体时的整个过程，更能直接观察到这些团队是如何通过**链路追踪**（Trace: 记录AI应用执行过程中每一步输入输出及中间状态的日志链）对生产环境中的在线智能体进行实时评估的。

为了让大家更直观地感受这一领域的规模，这里有一些实际的数据统计：我们每个月运行超过 1 亿次评估；平均每个团队会运行约 12 个不同的评估任务，而顶尖团队运行的评估器数量甚至超过了 3,800 个。尽管离线评估和在线评估各司其职，但在当前阶段，我们更倾向于关注那些通过链路追踪在真实运行数据上运行评估的团队。正是这种方式帮助团队找出哪些策略有效，捕捉运行中的失败，并为持续学习闭环提供源源不断的数据支撑。整个行业对此已经达成了共识，无论是 **Anthropic** 还是 **OpenAI** 的首席产品官，还是 **Y Combinator** 的 **Garry Tan**，都在强调“评估就是你所需的一切”。

然而，在建立起这种对评估重要性的共识之后，整个技术底层却悄然发生了改变，这促使我们必须重新审视评估的定义。

<details>
<summary>Original English</summary>

Awesome. Well, hey everyone. My name is Aparna, one of the founders of Arize. We work with some amazing teams to help them build evals. And we have an incredible lineup of talks for you all today at the evals track. It's happening in room 2005 and there's going to be amazing speakers from Term Bench and Uber and Snorkel kind of all happening after this. But today I'm here to talk to you about the future of evals. Evals have gone from the new skill that every PM and every AI engineer has to learn to the thing that every serious AI team is betting on. We've been really fortunate to get to work with some of the best AI teams in the world. So, we get a front row seat into not just what's happening when they're building their actual agents and before they actually ship, but actually the evals that teams are running on their live production agent via their traces. Little bit of some stats for you guys. We run over 100 million evals every month. The average team runs about 12 different eval jobs with the top teams running over 3,800 different evaluators. And offline evals, online evals, they each have their own place, but today what I'm actually going to talk to you about is the teams that are running evals on their traces. This is actually what's helping teams figure out what's working, catch their failures, and that's the type of data you need to fuel your continual learning loops. And the industry kind of agrees. I mean, all the CPOs of Anthropic, OpenAI, all you know, GDB, you have Garry Tan saying, "Evals are everything you need." And the whole industry kind of agrees.
</details>

### 评测对象的范式转移：2023与2024的复杂性鸿沟

当我们满心欢喜地以为通过引入第一代评估系统就能捕捉到所有错误时，我们真正评估的底层对象已经发生了根本性的改变。回顾 2023 年，评估的核心还是围绕着如何回答好一个单一的 **提示词**（Prompt: 引导大语言模型生成特定响应的文本指令）。然而到了 2024 年，随着前沿模型的推出，事情变得复杂得多：

* 模型中加入了**工具调用**（Tool Call: 模型调用外部API或执行特定功能的能力）；
* 引入了更为复杂的推理机制与深度研究功能；
* 团队开始在真实世界的数据上运行复杂的控制循环，并由子智能体去执行**长周期任务**（Long-horizon Task: 需要多步推理与多智能体协作才能完成的复杂任务）。

这一系列的变化不仅仅是让评测任务变得更难，而是将我们推向了一个在本质上完全不同的新问题。系统越复杂，它们在运行中失效和崩溃的方式也变得越发多样和难以预测。

为了应对这种由于系统复杂性跃升而带来的新型失败模式，我们必须深入理解复杂智能体在实际应用中的边界与痛点。

<details>
<summary>Original English</summary>

So, we added evals, they catch all the failures, right? Here's the problem. When we were building all of these first-gen evals, the thing that we were actually evaluating has changed underneath us. In 2023, it was about just answering a prompt. In 2024, we started to see all the frontier models. They've added tool calls, they've added reasoning, they've added deep research. Now, what we have is teams running loops on real-world data with sub-agents kicked off on long-horizon tasks. Every one of these was actually a massive jump in complexity, and we didn't just make the problem harder, we actually got a fundamentally different type of problem. What that meant is that as these systems got more complex, so did the way that they actually fail.
</details>

### 智能体裁判：重构动态轨迹的评估范式

我们非常幸运能在自己的产品界面中构建并运行自己的智能体 **Alex**，因此我们得以上演“肉身试毒”，切身感受这些开发中的痛点。每当前沿实验室发布新的功能，我们就会将其整合进 Alex。虽然如今的 Alex 拥有了更长的记忆力、生成动态界面的能力以及跨海量追踪数据进行检索的本领，但我们也发现它开始出现遗忘上下文、无法判断任务何时真正结束，甚至偶尔会陷入无尽死循环的问题。

此时，许多人在这个房间里写过的传统**大模型裁判**（LLM as a Judge: 利用大语言模型作为裁判对生成内容进行评估打分的机制）就显得捉襟见肘，根本无法捕获我们正在经历的那些复杂失败模式。以往的确定性工作流中，输出轨迹是固定的；而现在，用户每次与 Alex 互动都会产生一个全新的动态界面，这代表着一条完全不同的**执行轨迹**（Trajectory: 智能体在完成任务过程中所经历的所有状态与决策序列）。

这一痛点引发了我们的重大启示：如果评估智能体的最佳方式，其实是使用另一个智能体呢？这并不意味着过去那些基于确定性规则或大模型裁判的经典评估方式不再重要，而是意味着我们需要一种全新的工具来解决这种全新的问题。传统大模型裁判通常只提供基于固定标准的打分表，而**智能体裁判**（Agent as a Judge: 采用动态、自适应的智能体对复杂的智能体执行轨迹进行评估分析的方法）则专注于自适应的动态轨迹分析。当智能体在用户输入数据后每次都表现出截然不同的执行路径时，你就必须拥有一种在本质上完全不同的评估手段。虽然目前大多数团队只停留在前两种评估阶段，但我们坚信，评估的未来必定是将这三者融为一体。

在明确了智能体裁判的必要性之后，我们开始致力于将这种先进的动态分析方法落地为具体的生产力工具。

<details>
<summary>Original English</summary>

We're really lucky cuz we have our own agent that we've built, Alex, that lives in our UI, and we get our kind of get to feel this pain ourselves. Every time the frontier labs added new functionality, we added it to our agent. And now Alex has much longer memory. It has the ability to create dynamic UIs. It can go search across an enormous volume of traces. But, we also realized that it would forget context. It wouldn't know when something was done. Sometimes it would just get stuck in these loops. And the key thing here is that the classical LLM as a judge evals, that probably many of you have written in this room, just weren't for us to be able to catch all the types of failures that we were experiencing. It's just fundamentally different, right? You have a deterministic flow, and now what we have is literally every time a user interacted with Alex, it would create a new UI. That's a fundamentally different trajectory. So, this led to our really big revelation. What if the best way to evaluate an agent was actually with an agent? Doesn't mean that all of the ways that we did evals, with deterministic evals, with LLM as a judge, classic evals, doesn't matter anymore, but it just means that we have a different type of tool to solve a different type of problem. Agent as a judge is about adaptive dynamic analysis. LLM as a judge just gives you a fixed rubric with these fixed scores. It's what everyone's doing, but when your agent's doing completely different trajectories every time a user puts in data, it just means that you need a fundamentally different type of eval. My take is that most teams today are doing the first two, but the future of evals is actually having all three.
</details>

### 主动式反馈闭环：利用 Signal 智能体自动发现与修复缺陷

今天，我非常激动地向大家宣布，我们正式推出了智能体裁判功能，以助力开发团队的评估旅程。我们发布了名为 **Signal** 的长周期运行智能体，它能够读取传入的链路追踪数据并自动发现潜在的问题模式。对于那些传统的、基于固定规则的大模型裁判根本无法捕获的轨迹失败，Signal 能够凭借其自适应特性轻松识别。

在实际使用中，Signal 帮助我们揪出了许多极其隐蔽的异常，比如：

* 智能体在多步执行中陷入了重复循环；
* 智能体在极长的时间内频繁调用同一个工具；
* 整体执行轨迹极其低效。

更强大的是，因为 Signal 拥有完整的轨迹分析上下文，它不仅能发现问题，甚至还能直接提交拉取请求（Pull Request: 托管平台中用于代码合并的请求）并部署修复方案。

如果您想了解更多关于 Signal 的细节，欢迎来到我们靠近 OpenAI 的展位，我们将为您提供现场演示并深入探讨。同时，我们今天也将主导 2005 房间的评估专题分论坛（Evals Track），在那里我们将深度探讨评估的未来形态。最后，如果您只想和我们的团队放松一下，我们今晚还将为美国队的世界杯比赛举办一场观赛派对，欢迎大家查看 Luma 并注册加入我们。非常感谢大家！

<details>
<summary>Original English</summary>

And today I'm actually excited to share we've released agent as a judge to help our teams on their eval journey. We've released Signal. Signal's actually a long-running agent that can read traces sent in, discover patterns of issues. It can figure out types of problems that a classical LLM as a judge eval just would never be able to do with these deterministic rubrics. It's helped us figure out very subtle failures that you wouldn't even think of doing, such as something going on in a loop for multiple times, it was calling the same tool repeatedly long time, the trajectory was inefficient. And actually what this does is because it has all that analysis, it can go put up a PR and put up a fix. So, if you want to learn more, come to our booth. We're right by the OpenAI booth. We'll give you a demo, we'll show you a bit more about it. We're also, like I said, taking over the evals track, so come to room 2005. We're going to be talking a lot about the future of evals and what they look like. And if you just want to hang out with our team, we're throwing a viewing party for the USA World Cup game tonight, so check out the Luma and register to come join us. Awesome. Thank you all so much.
</details>