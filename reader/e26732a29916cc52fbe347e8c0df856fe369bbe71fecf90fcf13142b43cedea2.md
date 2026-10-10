---
author: AI Engineer
date: '2026-05-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5Sui_OnSRlY
speaker: AI Engineer
tags:
  - agent-swarms
  - software-factory
  - sdlc-automation
  - agent-coordination
  - context-management
title: 软件工厂的缺失基元：构建自主代理群落
summary: 软件工程师 Lou Bichard 探讨了如何通过“软件工厂”模式实现 SDLC 的自动化。他指出，尽管运行时和编排问题基本已解决，但代理协调（agent coordination）与上下文管理仍是核心痛点。他提出了以虚拟机（VM）为基础的开发环境隔离方案，并探讨了通过状态机和命令行工具（CLI）实现代理间协作的未来方向。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Owner
  - Stripe
  - Ramp
  - OpenAI
products_models:
  - Symphony
media_books: []
status: evergreen
---
### 软件工厂与代理群落的自动化模式

在软件工程领域，目前大家都在致力于构建一种“软件工厂”模式。所谓**软件工厂**（Software Factory: 致力于将人类逐步从软件开发生命周期 SDLC 中解放出来的承诺），其核心定义在于让工作在开发与生产环境间以自动化的方式流动，从而减少人工的直接参与。

为了实现这一目标，代理（Agent）的运行模式至关重要。目前主要存在几种可扩展的运行模式：**群落模式**（Swarm Pattern: 从单一意图触发，分发至多个代理，最后汇聚成 PR 或任务）、**舰队模式**（Fleets: 将代理扇出到组织内部的多个代码仓库中）、以及**事件驱动模式**（Events: 通过 webhook 等基础设施触发代理）。像 Stripe 的 Minions 和 Ramp 的 Inspect 都是这种基础设施的典型应用，能够支持大规模的自动化 pull request 处理。

<details>
<summary>Original English Source</summary>
In my world at least, everyone is trying to build a form of a software factory. I've seen a few different talks at this conference of similar sort of ideas trying to take coding agents and then apply them across the software development life cycle. I added a definition in this slide as well just to quickly define what I believe to be as a software factory which is sort of the commitment to incrementally moving the human out of the loop within the SDLC. Such that the human is not proactively interacting with a computer. My personal definition is that you're slowly bringing the human out of it and then work is flowing from sort of development into production theoretically in an automated fashion.

We have different patterns really for running these agents at scale. So, one of them really is sort of the swarm pattern which for my definition is starting off with an individual intent firing that out to a number of different agents and then funneling that back in let's say to an individual PR or task. Fleets is where you're fanning out agents across let's say number of different repositories inside of an organization which is a capability we've had in Owner for quite some time now. And then the bottom you've kind of got events. If you think about how do we take the human out of the loop and build this sort of software factory, you need to know how and when are you going to trigger those agents, when do they come online? A lot of this already exists with existing sort of web hook infrastructure. Stripe has one. There's what they call minions which is built on top of their existing infrastructure where they've then plugged in these coding agents. Another very noteworthy one and Ramp has been so loud on social media these last couple of weeks. But, they also built one that they internally call inspect which again is their sort of infrastructure for for running these background agents.
</details>

### 构建软件工厂的核心基础设施

要从基础设施层面构建软件工厂，首先需要解决三个关键点：运行时、编排与协调。**运行时**（Runtime: 为代理提供执行环境）目前已基本解决，可以通过隔离的开发环境（Development Environments）来实现。在安全边界和性能抖动（Noisy Neighbor 问题）方面，我们认为基于**虚拟机**（Virtual Machine: 具备物理隔离能力的开发环境）的方案要优于容器方案。

在软件工厂的构建中，**哈尼斯工程**（Harness Engineering: 将过程知识编码到仓库、上下文文件和代理中的一种工程实践）发挥着重要作用。这本质上是上下文工程的延伸，旨在通过不断实验、发现代理失效点并将其编码回上下文，来优化代理在软件工厂中的自动化流转。然而，目前的 SDLC 模型在实际应用中过于粗糙，代理无法理解其中的复杂性，因此需要将 SDLC 细分为更可控的**微步骤**（Micro-steps）。

<details>
<summary>Original English Source</summary>
If we take a step back and then think about from an infrastructure level what you need effectively to build this form of sort of software factory, the first piece of that puzzle is a runtime or you need somewhere for the agent to run. And I believe this is mostly is is pretty much a solved problem now. You then need a way to orchestrate these. You need to run them at scale. You need some way to trigger them. But, for me one of the biggest difficulties if you try and build this today is effectively agent coordination.

We at least believe that for running sort of proper development tasks, it has to be inside of a virtual machine. The reason for that is for the isolation from a security standpoint, a container is not bulletproof isolation boundary. They're also bursty. If you run them on Kubernetes or in pods, you have noisy neighbor problems. And only with having sort of the full isolation of a VM will you be able to effectively do this properly.

Over the last couple of days I had a few questions with people talk about harness engineering and what is it? For me, it's really another extension on context engineering whereby everything in your repository from skills to agents.md to unit tests, everything that you could possibly use to give feedback to your agent is for me harness engineering. The conceptual SDLC that we present and talk about with each other is very coarse-grained five steps. Agents don't respect this and they don't understand I mean, these boxes contain a ton of complexity. So, if we take something like plan or plan stage, actually within that our SDLC has a ton of different sort of micro steps almost to it. And if we're wanting them to train agents to then step through the SDLC, we need to find ways to actually break down the SDLC into these some of these micro steps.
</details>

### 协调层：代理群落的终极挑战

在基础设施之上，目前最缺失的拼图是**代理协调**（Agent Coordination: 代理之间如何相互作用、任务分发与协作）。现有的人类协作工具（如 GitHub、Linear）在用作代理协调层时显得异常嘈杂且效率低下，无法让用户清晰地介入和干预代理行为。

未来解决这一问题的方向可能在于**状态机**（State Machine: 通过定义确定性的工作流来管理代理执行逻辑）和**持久化执行**（Durable Execution: 实现过程的持久化运行）。同时，还需要一个能够集成到本地开发环境（如代理、CLI）中并能远程在 CI 环境运行的标准化**命令行接口构造**（CLI Construct）。这不仅能解决代理的协调，还能解决复杂 SDLC 过程中的合规性与门控检查问题。

<details>
<summary>Original English Source</summary>
Once you got this infrastructure, you have the runtimes, you have the orchestration, the missing piece that you also need is coordination. So, if you use something like GitHub, GitHub is not a coordination layer for agents. It gets incredibly overwhelming. You know, you can have your agents raise a pull request, you can review it, you can then solve the merge conflicts, you can fix the CI build, etc. But this gets incredibly noisy for you as a human to make sense of where you should step in to intervene with that agent itself.

But I think we are now at the cusp of now effectively solving this. And I think it might be solved in a few different ways. One is through sort of state machines, you know, by building out workflows and effectively state machines that we've had for a very long time and then building these as our versions of our SDLC. I do believe to a degree some of the ideas from durable executions comes into this as well. You know, lots of companies have pioneered this over time to be able to run a process in a in a durable fashion. But we do need to solve also the gates and compliance section of this. And I do believe actually there is definitely a a gap right now also for packaging this in some form of like CLI construct whereby you can run this locally in a sort of development environment, but also then remotely in, you know, in a CI or some other fashion like this.
</details>