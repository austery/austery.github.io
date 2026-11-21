---
author: Latent Space
date: '2026-05-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=287Q-bs_pEU
speaker: Latent Space
tags:
  - ai-agents
  - serverless-computing
  - actor-model
  - open-source-culture
  - agentic-software
title: 超越增量更新：Sunil Pai 谈 AI 智能体架构、开源『乱改』与原创精神
summary: Cloudflare 的 Sunil Pai 深入探讨了 AI 智能体的新型软件架构，重点介绍了 Durable Objects 和 Dynamic Workers 如何重塑 Actor 模型。他分享了与 Vercel 的『Slop Fork』争议背后的思考，呼虑开发者停止构建平庸的框架，转而利用 AI 力量去实现更具原创性和『科幻感』的项目。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Sunil Pai
companies_orgs:
  - Cloudflare
  - Anthropic
  - Vercel
products_models:
  - Durable Objects
  - Dynamic Workers
  - Agents SDK
  - Model Context Protocol
  - Claude Code
media_books: []
status: evergreen
---
### 智能体新架构：Durable Objects 与动态代码执行的范式转移

在当前的 AI 浪潮中，我们正在经历一场**软件架构的重构**（Architecture of the New Software）。Sunil Pai 指出，Cloudflare 在这一演进中提供了两个至关重要的底层原语：**持久化对象**（Durable Objects: 有状态的 Serverless 编程模型）和**动态 Worker**（Dynamic Workers: 允许安全、即时执行用户或 AI 生成的代码）。

**持久化对象**是业界首个在基础设施层实现的 **Actor 模型**（Actor Model: 一种并发计算的数学模型），它允许在后台运行数百万个有状态的单元，而无需像传统方式那样启动庞大的虚拟机。与此同时，**动态 Worker** 解决了长期以来 `eval` 被视为危险操作的问题。通过构建安全的沙箱环境，开发者可以精确控制 API 暴露和网络流量。这种架构不仅让 Cloudflare 能够高效构建 AI 智能体，还通过 **MCP 服务**（Model Context Protocol: 模型上下文协议）简化了海量 API 的调用——AI 不再需要针对 2600 个端点逐一学习工具，而是通过“搜索并执行”的模式，直接生成代码并在隔离环境中运行，极大地减少了与 LLM 的往返交互。

<details>
<summary>Original English Source</summary>

I think that you see like anything else I think we are like discovering the architecture of the new architecture of building software. Interestingly our primitive the two primitives that I think are critical that I suspect every platform will eventually get one is durable objects which are stateful serverless programming uh I think that's a true innovation it's the world's first implementation of the actor model in on an in an infrastructure layer not in userland it means you can spin up millions of these stateful things that run in the background etc and it runs with serverless uh characteristics instead of spinning up a whole VM. 

The Second, which we announced just a few weeks ago is what we call dynamic workers. Famously, eval has been considered a bad idea evaluating code, user generated code or now LLM generated code. But we built this thing that lets you run it in a safe environment with zero startup time. Given these things, we feel we can build a much more efficient and much um a new kind of architecture for building AI agents. 

One of applications of dynamic workers... our MCP server. The Cloudflare API is 2600 API endpoints. So if you exposed a tool for each one of them, you're screwed. No, we said you can have two tool calls. One is search and execute. And to each one of these, you actually submit code that we run in and isolate. well, turns out LLMs are great at running code. So, this is fundamental capabilities. It's not something you can patch on and use.

</details>

### 『Slop Fork』争议：AI 时代的开源文化冲突

Sunil 分享了近期引发热议的 **Slop Fork**（AI 辅助的快速分叉与适配）事件，这起源于他与 Vercel 之间的一场 Twitter 摩擦。他在参加 JSConf 期间，尝试将 Vercel Labs 的项目 **Just Bash**（基于 JavaScript 的 Bash 纯实现）适配到 Cloudflare。在 AI 模型 **Opus** 的帮助下，他在午餐时间就生成了 5000 行代码。

这场争议暴露了现代开源环境的紧张局势。尽管 Sunil 认为**分叉**（Forking）在程序员文化中象征着尊重和社区繁荣，但在商业化和社交媒体的放大下，这种行为有时会被误解为竞争性的“窃取”。Sunil 强调，开源的内核应当是“为了热爱而战”，他鼓励开发者自由地移植和改进代码。然而，现实中的开源维护者正面临前所未有的压力，包括**对抗性环境**（Adversarial Grounds）和虚假的安全报告攻击。他认为，AI 时代的开源协作正在发生变化，有时甚至需要暂时关闭贡献通道，转而通过 AI 快速处理 Issue 并生成解决方案。

<details>
<summary>Original English Source</summary>

Let's talk about slop forks. What happened with you and Vercel? I've been in this industry long enough that I have friends everywhere. Uh we describe the industry as a forest of revolving doors. The event is I was playing with this project that uh Vercel Labs had just come out with called Just Bash. I loved it. And I was like, "Oh, of course I want to make some of this stuff work with uh Cloudflare." And the way I did it in 2026 is I just point Opus at it and I go out like for lunch, etc., right? And I come back and it spat out 5,000 lines of code.

I go on Twitter and the Vercel CTO is uh trashing my work saying well suddenly it's Cloudflare did this. I was just like, "Oh, this is not it at all." Forking is a great sign of uh prestige, respect in my culture. It's how the React community grew. Core to what open source is right you want to build on it you should take our work fork it and do whatever. If you're in it for the love of the game, then do it for the love of the game.

I think there's also this tendency now which is open-source repos have become adversarial grounds. So on the agents SDK for example, we had to shut down contributions. We only allow issues right now. And like the end result is I'm going to take a resolution and paste it into Opus. I think open source repos have become adversarial to the point that people are almost afraid of gaining um popularity in that space.

</details>

### 寻找 AI 领域的 React：技能抽象与原创勇气

尽管目前智能体框架层出不穷，但 Sunil 认为，我们尚未迎来 AI 时代的 **React 时刻**——即一个能够跨语言、跨公司、跨基础设施复用的原创性思维框架。他预测，这种标准化的层级可能隐藏在**技能**（Skills）之中。

**技能**（Skills）作为一种通过英语（Markdown 文件）描述的抽象，具有极强的扩展性和可访问性，它能作为多语言世界之间的桥梁。Sunil 对未来软件可能由 Markdown 文件驱动的前景感到兴奋。在访谈的最后，他发出了一个极具感染力的呼吁：在这个 AI 可以轻易实现任何平庸想法的时代，不要再去构建那些**增量式改进**（Incrementally Better）的工具或框架，而是要去构建那些**具有科幻感**（Sci-fi Stuff）、真正能改变家庭生活或解决独特问题的原创作品。他乞求开发者展现出原创的勇气，因为世界并不需要另一个平庸的智能体框架。

<details>
<summary>Original English Source</summary>

It's so hard but the way I'm framing it in my head is no one has built the react yet. The moment React came in... that established every framework in the future. I suspect we haven't done that yet. It might just be skills. I feel like skills are the ultimate translation thing. They scale well. It's English. Uh, you know, you can abstract it down. 

Is that it? Like, by the way, I'd be so happy if you say the future of software is Markdown files. Beautiful. Instantly accessible. A multi-language bridges the world. 

The real thing I encourage people to do is to be original. In such a crazy world where any idea seems to work now like the clanker like will make it work for you. Don't even try to do something incrementally better. Build sci-fi stuff. Build stuff like for your family. Use agents SDK for doing it. I'm begging you to be original and to have courage to try a new idea. I don't need another agent framework. Nobody needs it.

</details>