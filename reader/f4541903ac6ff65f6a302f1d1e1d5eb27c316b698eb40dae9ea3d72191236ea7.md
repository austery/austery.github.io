---
author: AI Engineer
date: '2026-05-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=vi-2nasppAg
speaker: AI Engineer
tags:
  - event-sourcing
  - agentic-workflow
  - stream-processing
  - distributed-systems
  - ai-infrastructure
title: 事件溯源下的 AI 智能体框架：构建可调试与高度可扩展的分布式系统
summary: Iterate 联合创始人 Jonas Templestein 探讨了基于事件溯源（Event Sourcing）构建 AI 智能体（Agent Harness）的新范式。通过将所有交互抽象为层级化的流式事件，实现了极高的调试效率、分布式扩展能力及智能体自演化。演示展示了如何利用流处理器（Stream Processor）从事件中推导状态，并实现“代码即事件”的动态部署。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Jonas Templestein
companies_orgs:
  - Iterate
  - OpenAI
products_models:
  - GPT-4
  - Cloudflare Workers
media_books: []
status: evergreen
---
### 混乱中的愿景：为何选择事件溯源构建智能体？

Jonas 提到这原本是一个即兴的黑客松，由于突发情况（如孩子生病、火警导致观众一度离场等）显得有些混乱。他分享了过去一年关于智能体框架（Agent Harnesses）的思考：核心在于**事件溯源**（Event Sourcing: 一种通过保存所有状态变更事件来构建系统的方法）。大多数现有的智能体系统在调试上都很困难，因为总有某些副作用（Side Effects）无法回溯，只能在日志中寻找。如果我们将一切可能发生的事情都记录在事件流中，智能体将变得极易调试。更重要的是，这种架构不仅允许人类扩展智能体，还支持智能体**自我演化**（Self-extensible）和**组件化**（Composable）。

<details>
<summary>Original English Source</summary>

Welcome to the workshop. I am Jonas. Um and this is Misha. We both work at Iterate. And the um this is going to be uh chaos. I think pure chaos first of all because we only decided uh last Monday to do this... these have been ideas that have been kind of noodling around over the last year but we haven't really actually done anything with... it's basically how I would like to build agent harnesses.

The way I would like to do it is I would like to do it purely event sourced. Um and I say here aka debugable and that is because everything kind of skirts around of being event source... there's always something that has a side effect that you later can't tell and then you can only see it in the hotel traces or something... if you just say everything that could possibly happen is in there. It'll be really easy to debug.

And then the second thing is I want this to be extensible... valuable it is to make an agent extensible not just by humans but also extensible by itself. Um and one thing that I want in the extensibility is I want it to be composable.
</details>

### 核心原语：路径、事件与 Curl 的简洁哲学

Iterate 构建了一个名为 `events.iterate.com` 的服务，其核心原语非常简单：**智能体路径**（Agent Paths: 类似文件系统的层级结构）。每个路径下都是原始的 YAML 格式事件。这些事件由**类型**（Type）、**载荷**（Payload）和**自增偏移量**（Offset: 服务器端生成的唯一递增序列）组成。通过简单的 `curl` 命令和 **SSE**（Server-Sent Events: 服务器发送事件）流，开发者可以实时订阅事件。这种设计追求“URL 即智能体”的理念——智能体一旦存在，就应该有一个可以直接访问的 URL，支持 HTTP 通信，从而能够无缝集成 Slack Webhooks 或各种网页表单。

<details>
<summary>Original English Source</summary>

In the events app we have this concept of agent paths. So just like a file in a file system every agent has a path as a hierarchy and you just have raw events. This is YAML formatted raw events in each of these paths. And that is basically the entire primitive that we're going to be building our agent on.

There's a basic event envelope shape. We have a type that I've just invented here. Events don't need to have anything but a type, but most of them also have a payload. Uh then there is the stream path which came from the URL that we posted this to. And there's an offset. This is just an auto incrementing integer that starts at one.

The moment an agent exists, it should have a URL. That's just my opinion because otherwise like you end up making all these things and then you tie yourself backwards inventing a connector concept just so you can get Slack messages in.
</details>

### 流处理器：将事件流转化为逻辑实体

智能体的业务逻辑被抽象为**流处理器**（Stream Processor）。这借鉴了函数式编程中的 `reduce` 思想：通过一个同步的 **Reduce 函数**（Reducer: 根据新事件更新当前状态的纯函数）从事件中推导世界状态（World State）。这种方式解决了分布式环境下的状态同步难题。例如，当程序重启或网络重连时，处理器可以快速回溯过去的所有事件以恢复状态，然后再决定是否触发副作用（如发起 LLM 请求）。将逻辑分为“状态约简”和“副作用触发”两个阶段，可以有效防止因系统波动导致的重复动作。

<details>
<summary>Original English Source</summary>

I think the way I think about what we're really doing is we're writing a stream processor. And if you've never done stream processing... really um what we're saying is um there exists uh some kind of world state that we're interesting in that can be derived from the events.

And then you can write the entire logic of your program as uh effectively a reduce function. This is synchronous and it just um it just uh looks at all the new events as they come in and then it updates the state. That's all it does.

And the reason I've split the reduce function from after append where you should do your side effects is because uh if you think about what happens if if your program uh goes to sleep... you bring you open your computer again, you start your program again and you don't want your program to go and um make a ton of LLM requests for all of those 100 events in the past.
</details>

### 代码即事件：动态 Worker 与分布式扩展

这种架构支持**分布式**（Distributed）和**多语言**（Polyglot）扩展：一个插件可以用 Rust 编写运行在 A 服务器，另一个用 TypeScript 运行在 B 服务器。最先进的概念是**动态 Worker**（Dynamic Worker）：开发者可以直接向事件流中追加一个包含 JavaScript 源代码的事件，系统检测到该事件后，会自动在边缘端（如 Cloudflare Workers）部署并运行该处理器。这意味着“部署智能体”这一动作本身就被简化为了“向流中发送一个事件”。这种“可编程流”的概念允许智能体根据环境动态修改自己的行为。

<details>
<summary>Original English Source</summary>

By distributed I mean you should be able to have uh an agent um running uh sort of on one computer here on a server and my plug-in running over over here... yours is written in Rust and mine is written in Typescript and it all just doesn't really matter.

Actually one thing that you can also do... you can also make an event that contains the source code of your stream processor and then it'll just run on every event. And so like it's basically it is like it is like a programmable stream.

You can append an event of type dynamic worker configured... and the script is a string. And inside the string is a reducer uh and an after append hook. I have here a stream that knows nothing about the world and then I have appended this event here that just has a little bit of JavaScript in it. And this little bit of JavaScript uh just makes it respond with pong whenever it encounters something with ping.
</details>

### 最终一致性与智能体基础设施的未来

Jonas 认为未来的数字智能体不应是封闭的“机器人”，而应该是互联网连接的、基于标准协议的实体。虽然演示中为了方便没有包含身份验证（Authentication），但在实际生产中，权限可以通过事件的**来源信息**（Provenance）来严格管理。这种架构天然支持**最终一致性**（Eventual Consistency）：系统可以为安全检查或 RAG（检索增强生成）管道预留 200 毫秒的窗口期，如果这些组件能及时返回额外上下文则合入，否则主流程继续运行。这种松耦合设计使得构建复杂的 AI 协作生态系统变得可能。

<details>
<summary>Original English Source</summary>

The way I think of it is basically an intelligent entity like a digital one that's not a robot in the future. It's just internet connected uh basically server program, right? It just speaks HTTP.

I'm very against before hooks... I think there were some instances in Open Claw, for example, some massive performance regressions... it's just way better to think of the whole system as as being eventually consistent.

You can easily have a little processor that says I have like a indexed version of the notion knowledge base or something and I'm just going to sit here and try to squeeze in a little bit of extra context if I think it's relevant, but if I don't get there in time, it's like totally chill. The whole thing still works.
</details>