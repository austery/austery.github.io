---
author: AI Engineer
date: '2026-07-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=sum9DgexFRQ
speaker: AI Engineer
tags:
  - agentic-web
  - decentralized-infrastructure
  - agent-discovery
  - discrete-event-simulation
title: “Web of Agents”的开放基础设施：探索 Project Nanda 与 AI 智能体的未来
summary: 本文基于 MIT Media Lab 的 Ramesh Raskar 教授和核心贡献者 Maria 的访谈，探讨了为万亿级自主 AI 智能体构建的去中心化开放基础设施——Project Nanda。重点介绍了其核心组件 Nanda Index（发现层）、基于 host39.org 和 Maritime 的托管与入驻机制，以及用于大规模协议与协同测试的开源离散事件模拟沙盒 Nanda Town。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - MIT Media Lab
products_models:
  - Open Claw
  - Nanda Town
  - Maritime
media_books: []
status: evergreen
---
### 智能体网络与Project Nanda

**Ramesh Raskar**: 欢迎大家。在接下来的几分钟里，我们将探讨为**智能体网络**（Web of Agents）构建的**开放基础设施**。我们将讨论为什么需要它、目前已经发布了什么，以及你自己在其中扮演了怎样的角色。这项工作源自 **Project Nanda**，这是一个始于**麻省理工学院（MIT）**的开放研究项目。在本次演讲结束时，你将了解如何完全独立地将你自己构建的智能体部署到开放网络上。那么，让我们开始吧。我是 **Ramesh Raskar**，麻省理工学院的教授，也是 Project Nanda 的负责人。而 **Maria** 是 Project Nanda 的核心贡献者。

<details>
<summary>Original English</summary>

**Ramesh Raskar**: Welcome everyone. Over the next few minutes, we're going to talk about the open infrastructure being built for a web of agents. Why it's needed, what's already shipped, and exactly where your own agent fits into it. It comes out of Project Nanda, an open research effort that started at MIT. And by the end of this presentation, you will know how to put an agent that you build yourself on the open web all by yourself. So, let's get into it. I'm Ramesh Raskar, professor at MIT and director of Project Nanda. And Maria is a core contributor to Project Nanda.

</details>

**Ramesh Raskar**: 首先，什么是 Nanda？为什么它需要存在？Nanda，代表“**去中心化架构中的网络 AI 智能体**”（network AI agents in a decentralized architecture），是一项开放研究，旨在为 AI 智能体互联网构建基础设施，就像当初为文档构建开放万维网一样。它填补的空白是具体而切实的。智能体在不同厂商之间没有共享的方式来寻找彼此，没有不被单一平台拥有的便携式**身份（Identity）**或**信任（Trust）**机制，也没有开放的方式跨组织进行交易和协同。Nanda 构建了这层缺失的层级，并以开源形式发布：包括索引、注册表、协议，以及你们稍后将看到的 **Nanda Town** 模拟器。

这是推动这一切的核心前提：互联网即将托管的不仅是数百万或数以十亿计，而是最终将达到数万亿个**自主智能体**（autonomous agents）。它们进行谈判、委托任务，并在几毫秒内于不同主机之间进行迁移。与人类使用的万维网相比，这是一种根本不同的负载，它使我们为文档构建的身份和发现系统（包括域名系统 DNS）承受了极大的压力。即将到来的智能体网络需要拥有自己专属的基础设施。

而且，我们以前经历过类似的阶段。如果你今天正在构建智能体，你大多时候是在**围墙花园**（walled gardens）、封闭平台、专有智能体商店以及只能与自身对话的编排系统中构建它们，或者被迫在其中进行构建。这在某种程度上确实可行。但是，你知道，这也让人感觉似曾相识，因为我们经历过这个阶段。这非常像 20 世纪 90 年代末的 **AOL（美国在线）**时代，当时那是一个封闭的网络。你知道，在 AOL 时代，你拿到光盘，并把它们安装在你的个人电脑（PC）上。那是一个封闭的网络，一个被大门把守的目录。你生活在 AOL 这家单一公司所创建的花园中。

而 AOL 之后迎来的是**开放万维网**。你知道，每个人都以无须许可（permissionless）的方式创建网站、开发浏览器，任何网站都可以与任何浏览器进行对话。这就是智能体即将发生的转变。因此，下一个时代需要万维网曾经需要的东西：一个开放的基础设施，使来自一个公司或一个实体的智能体能够发现来自另一个实体的智能体。该智能体可以向其移交工作、向其付款，并跨越组织边界向其学习，不需要任何许可。这里有三个层级：**发现（discovery）**、**商业（commerce）**，以及我称之为“**集市（bazaar）**”的层级。因此，请记住这三个概念。我们稍后会回到它们并进行讨论。

<details>
<summary>Original English</summary>

**Ramesh Raskar**: So, first, what is Nanda and why does it need to exist? Nanda, which stands for network AI agents in a decentralized architecture, is an open research building the infrastructure for an internet of AI agents, the way open web was built for documents. The gap it fills is concrete. Agents have no shared way to find each other across vendors, no portable identity or trust that isn't owned by a single platform, and no open way to transact and coordinate across organizations. Nanda builds that missing layer and ships it in open. The index, the registries, the protocol, and the Nanda Town Simulator you will see later. Here's the premise that drives it all of it. The internet is about to host not millions or billions, but eventually trillions of autonomous agents. They negotiate, they delegate, they migrate between hosts in milliseconds. That's a fundamental different load than the human web, and it strains the identity and discovery system we built for documents, DNS among them. The web that's coming needs infrastructure of its own. And we have been here before. If you're building agents today, you're mostly building them or you're forced to build them inside walled gardens, closed platforms, proprietary agent stores, and orchestrations that only talk to itself. And it kind of works. But, you know, it also feels similar because we have been this we have been here before. This is like the AOL era from the late '90s where it was a closed network. You know, AOL, you got the CDs and you installed it on your PC. It was a closed network. It was a gated directory. You live inside the garden created by this one company called AOL. And what came after AOL was this open web. You know, everybody's in a permissionless manner creating websites, creating browsers, and any website can talk to any browser. And that's the transition that's about to happen to agents as well. So, the next era needs what the web needed, an open infrastructure where an agent from one company or one entity can discover agent from another. That agent can hand off work to it, pay it, learn from it across organizational boundaries, no permissions required. There are three layers here, discovery, commerce, and what I will call the bazaar. So, hold on to those three concepts. We'll come back to them and discuss.

</details>

### 智能体定义与自托管

**Maria**: 大家好，我是 **Maria**，是 Project Nanda 的核心贡献者。那么，让我们从智能体（Agent）的一个简单定义开始。在我看来，智能体就是**在循环中调用工具的模型**。对，你给它一个目标，它决定下一步做什么，它调用一个工具，它观察结果，然后它继续运行，直到任务完成。所以，这个**循环（Loop）**是核心理念。其他一切，比如记忆、编排和多智能体系统，都是构建在其之上的。

因此，你可以用许多不同的方式来构建这个智能体循环。其中一个例子就是 **Open Claw**。Open Claw 是一个**自托管的智能体网关**。这意味着你可以自己运行它，并将它连接到你已经使用的应用程序和工具中。这非常重要，因为智能体不仅仅是聊天机器人（Chatbots）。如果一个智能体要完成真正的工作，它就需要访问你的真实工具和应用程序。而且，如果它能够访问真实工具，我们就应该关心谁来控制它、它在哪里运行，以及我们能看到多少。这就是为什么**开源自托管智能体**超级重要的原因。它们让人们对自己的智能体拥有更多的控制权。但接着，我们遇到了一个新的问题。如果智能体在许多不同的地方运行——无论是在本地还是在云端，在许多不同的服务器上，由许多不同的人所拥有——它们如何找到彼此？而这正是索引（Index）的工作。

<details>
<summary>Original English</summary>

**Maria**: Hey, my name is Maria and I'm a core contributor to Project Nanda. So, let's start with a simple definition of an agent. The way I think about it, an agent is a model that uses tools in a loop. Right, you give it a goal, it decides what to do next, it calls a tool, it looks at the result, then it keeps going until the task is done. So, that loop is the core idea. Everything else, like memory orchestration and multi-agent systems, is built on top of it. So, you can build this agent loop in many different ways. One example is Open Claw. So, Open Claw is a self-hosted agent gateway. That means you can run it yourself and connect it to the apps and tools you already use. This matters because agents are not just chatbots. If an agent is going to do real work, it needs to access your real tools and apps. And if it has access to real tools, we should care about who controls it, where it runs, and how much we can see. And that is why open-source self-hosted agents are super important. They give people more control over their own agents. But then, we get a new problem. If agents are running in many different places, locally and on the clouds, on many different servers, like owned by many different people, how do they find each other? And that is the job of the index.

</details>

### 发现层：Nanda Index

**Maria**: 这正是 **Nanda Index** 的构建目的。Nanda Index 是智能体网络的**发现层**。它为智能体提供了一个共享的场所，用于发布它们是谁、它们能做什么，以及其他智能体如何联系到它们。常规的互联网已经通过 **DNS** 拥有了这方面的版本。因此，DNS 将名称映射到地址，这样你的浏览器就知道该去哪里。

但智能体需要的不仅仅是一个地址。它们需要知道另一个智能体做什么、它可以使用什么工具、它遵循什么规则，以及如何与它进行对话。索引为智能体提供了一种通用的方式来发现彼此并建立连接。

那么，以下是索引的工作原理。一个智能体从一个身份开始，比如 `agent@hotmail.com`。Nanda Index 获取该身份并返回一张**智能体卡片（Agent Card）**。所以，卡片说明了智能体是什么、如何联系它，以及将消息发送到哪里。消息不会直接发送到智能体的运行时（runtime）。它们会先进入**信箱（Message Box）**。信箱检查谁在发送消息、处理访问控制、过滤垃圾邮件或不良请求，并保留消息，直到智能体准备就绪。

现在，**智能体事实记录（Agent Facts Record）**是使发现变得值得信赖的关键。它是一个经过签名的记录，告诉其他智能体这个智能体是谁、它能做什么、它被允许接触什么、是谁构建了它，以及在哪里可以联系到它。因此，在一个智能体连接到另一个智能体之前，它可以先检查这些基本事实。

现在，索引不仅仅是一个查找表。它并不指向一个名字到唯一个固定地址。它可以根据请求返回更新后的智能体事实。因此，这意味着一个智能体可以拥有许多端点（Endpoints）。流量可以被路由 to 最佳的那一个，并且隐私细节不需要被暴露。因此，解析是**自适应的（Adaptive）**。它根据智能体所处的位置、发起查询的对象以及他们被允许访问的内容而变化。那么，你如何将你的智能体放入索引中呢？

<details>
<summary>Original English</summary>

**Maria**: And this is what the Nanda index is built for. Nanda index is the discovery layer for the agentic web. It gives agents a shared place to publish who they are, what they can do, and how other agents can reach them. The regular internet already has a version of this with DNS. So, DNS maps a name to an address, so your browser knows where to go. But agents need more than an address. They need to know what another agent does, what tools it can use, what rules it follows, and how to talk to it. The index gives agents a common way to find each other and connect. So, here's how the index works. An agent starts with the an identity like agent@hotmail.com. The NANDA index takes that identity and returns an agent card. So, the card says what an agent is, how to reach it, and where to send the messages. Messages do not go straight to the agent's runtime. They go to the message box first. The message box checks who is sending the message, handles access, filters spam or bad requests, and holds the message until the agent is ready. Now, the agent facts record is what makes discovery trustworthy. It is a signed record that tells other agents who this agent is, what it can do, what it is allowed to touch, who built it, and where to reach it. So, before one agent connects to another, it can check the basic facts first. Now, the index is not just a lookup table. It does not point to one name to one fixed address. It can return updated agent facts based on the request. So, that means one agent can have many endpoints. Traffic can be routed to the best one, and private details do not have to be exposed. So, the resolution is adaptive. It changes based on where the agent is, who's asking, and what they are allowed to access. So, how do you put your agent on the index?

</details>

### 智能体入驻方式与平台

**Maria**: 你可以从 **`host39.org`** 开始。在这里，你填写智能体事实表单，获得一张智能体卡片，并将其发布到 Nanda Index。一旦它被列入列表，其他智能体就可以找到它并知道如何联系它。

因此，有几种方法可以进入索引，具体取决于你是谁。**企业**可以运行自己的目录，并从自己的域名注册它们的网关。**现有的网站**可以字面上使用 DNS AID 来将智能体连接到它们已经拥有的域名。**小企业和个人**可以使用 `host39`，填写智能体事实表单，并获得托管的智能体 URL，而不需要拥有自己的域名。我们的目标是使入驻（Onboarding）工作适用于每个人，从大型公司到拥有个人智能体的普通人。

<details>
<summary>Original English</summary>

**Maria**: You start at host39.org. So, you fill out the agent facts form, get an agent card, and publish it to the NANDA index. Once it's listed, other agents can find it and know how to reach it. So, there are a few ways to get onto the index, depending on who you are. Enterprises can run their own catalog and register their gateway from their own domain. Existing websites can literally use DNS AID to connect agents to domains they already own. Small businesses and individuals can use host39, fill out the agent facts form, and get a hosted agent URL without needing their own domain. Goal is to make the onboarding work for everyone, from a large company to one person with a personal agent.

</details>

### 智能体托管与成本优化

**Maria**: 既然我们知道了智能体是如何在索引上列出的，下一个问题是，智能体实际上在哪里运行？为了有用，智能体需要保持在线并可被触达。你可以在**本地运行**它，这能给你完全的控制权，但这样你就需要负责维持它的运行。对于大多数用例来说，将其**托管在云端**更有意义。这可以在像 AWS 这样的通用云上，这更适合企业，或者在一个专门的智能体托管平台上，比如 **Maritime**，它旨在使托管 AI 智能体变得更便宜、更简单。

这里介绍一下 Maritime。托管一个智能体可能是负担得起的，但当你想要同时运行许多智能体时，成本问题就会出现，无论是为了一个团队、一个产品还是一个模拟系统。这就是**单智能体成本**真正起作用的地方。而 Maritime 是解决这一问题的方法之一。它为你运行 Open Claw 或其他智能体提供了一个简单的云端默认设置，采用**休眠与唤醒架构（Sleep and Wake Architecture）**，这样空闲的智能体就不会持续消耗算力。其核心目的在于使运行许多智能体变得实用、便宜且简单。

因此，你可以托管一个智能体并将其列在索引上，但让单个智能体上线总是容易的部分。智能体网络的难题在于**大规模智能体之间的协同**。因此，数以千计的智能体如何发现彼此、证明它们是谁、决定信任谁，以及在没有中央权威的情况下进行协调。

<details>
<summary>Original English</summary>

**Maria**: Now that we know how agents get listed on the index, the next question is, where does the agent actually run? To be useful, an agent needs to stay online and be reachable. You can run it locally, which gives you full control, but then you're responsible for keeping it up. For most use cases, it makes more sense to host it on the cloud. That could be on a general cloud like AWS, which is more enterprise ready, or on an agent hosting platform like Maritime, which is built to make hosting AI agents cheaper and simpler. So, a little bit about Maritime. Hosting one agent can be affordable, but the cost problem starts when you want to run many agents at once, for a team, a product, or a simulation. That is where per agent cost really matters. And Maritime is one way to solve this. It gives you a simple cloud default for running Open Claw or other agents with sleep and wake architecture, so idle agents do not keep burning compute. And the point is to make running many agents practical, cheap, and simple. So, you can host an agent and list it on the index, but getting one agent online was always the easy part. The hard problems of the agent web live between agents at scale. So, how thousands of them discover each other, prove who they are, decide whom to trust, and coordinate with no central authority.

</details>

### 模拟沙盒：Nanda Town

**Ramesh Raskar**: 因此，你不能只是假设协议在大负载下能够支撑得住，你必须测试和运行它们，并观察它们在什么时候会崩溃。这就是 Nanda Town 发挥作用的地方。那么，在开放的智能体网络承载真实互联网的负荷之前，你如何证明它确实有效呢？你对其进行**模拟（Simulation）**。

这就是 **Nanda Town**，Project Nanda 的一个开源项目。最简单的描述是，它是**智能体平台（Agoric platform）**基础设施的模拟剧本（Simulation Playbook）。所以，可以把它想象成一个沙箱城镇，其中建模了整个智能体经济（Agoric economy），比如发现、身份、注册表、消息传递、协调等等，全部包含在内。因此，你可以大规模运行并测试它。

以下是它在实践中的样子。Nanda Town 是一个用于测试智能体网络的实时沙箱。你可以在地图上看到智能体，实时观察消息的移动，比较协议结果，并逐步重放运行过程。它是完全开源的，体积足够小，可以在你自己的笔记本电脑上运行，旨在使智能体网络更容易被测试和理解。

Nanda Town 已经开始运行真实的实验了。例如，有一个买家和卖家商定价格的**市场**，一个智能体对商品进行竞价的**拍卖**，以及一个智能体提交和计票的**投票测试**。还有针对共识和**供应链**（Supply Chains）的测试。关键在于研究真实的协同问题：智能体如何达成交易、如何对决策达成一致、如何传递消息，以及在出现问题时如何恢复。

在底层，Nanda Town 将智能体网络分成了 **12 个部分**：传输、通信、身份、注册表、授权、信任、支付、协调、谈判、记忆、隐私、数据效应。每一部分都是真实智能体平台所需要的。所以，注册表层就是我们刚刚介绍的 Nanda Index，但在这里它只是一个更大系统中的一部分。并且你不需要构建所有的东西来尝试它。你可以获取其中一层，添加你自己的版本，在 Nanda Town 中运行它，并观察它如何与网络的其余部分协同工作。

Nanda Town 采用**离散事件模拟（Discrete Event Simulation）**运行。你在一个简短的 YAML 文件中定义一个场景，注入智能体和流量，测试床就会将其播放出来，以便你可以端到端地测量实际发生的情况。第一阶段（Tier 1）使用简单的脚本智能体，第二阶段（Tier 2）则换入真实的 AI 模型。

总之，Project Nanda 为 AI 智能体互联网构建了开放的基础设施：通过**索引**实现发现，通过**便携式身份与信任**实现商业，通过**开放协议**实现协调，并全部在 Nanda Town 中进行测试。如果你想了解更多信息，可以访问 `projectnanda.org`，阅读我们的论文，并查看我们最新的项目。

<details>
<summary>Original English</summary>

**Raskar**: So, you can't just assume that protocols will hold up under the load, and you have to test and run them and watch when they break. So, that's exactly where Nanda town comes in. So, how do you prove an open agent web actually works before it's load bearing on the real internet. You simulate it. This is Nanda Town, an open-source project from Project Nanda. The easiest way to describe it is it's a simulation playbook for the infrastructure of the Agoric platform. So, think of it as a sandbox town where the whole Agoric economy is modeled, like discovery, identity, registries, messaging, coordination, all of it. So, you can run and test it on scale. Here's what it looks like in practice. Nanda Town is a live sandbox for testing Agoric networks. You can see agents on a map, watch messages move in real time, compare protocol results, and replay a run step by step. It's fully open source, it's small enough to run on your own laptop, and built to make Agoric networks easier to test and understand. Nanda Town is already running real experiments. For example, there is a marketplace where buyers and sellers negotiate prices, an auction where agents bid on items, and a voting test where agents submit and count ballots. There are also tests for consensus and supply chains. The point is to study real coordination problems, how agents make deals, agree on decisions, pass messages, and recover when something breaks. Under the hood, Nanda Town breaks the Agoric web into 12 parts. Transport, communication, identity, registry, auth, trust, payments, coordination, negotiation, memory, privacy, data effects. Each part is something a real Agoric platform needs. So, the registry layer is the Nanda index we just walked through, but here it is just one piece of a bigger system. And you do not need to build everything to try it. You can take one layer, add your own version, run it inside Nanda Town, and see how it works with the rest of the network. So, Nanda Town runs as a discrete event simulation. You define a scenario in a short YAML file, inject agents and traffic, and the test bed plays it out so you can measure what actually happens end-to-end. Tier one uses simple scripted agents, and tier two swaps in real AI models. So, to summarize, Project Nanda builds the open infrastructure for an internet of AI agents. Discovery through the index, commerce through portable identity and trust, and coordination through open protocols, all tested in Nanda Town. And if you want to learn more, you can go to projectnanda.org, read our papers, and check out our latest projects.

</details>