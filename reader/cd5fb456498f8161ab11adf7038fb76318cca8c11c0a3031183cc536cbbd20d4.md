---
author: AI Engineer
date: '2026-04-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CD6R4Wf3jnY
speaker: AI Engineer
tags:
  - model-context-protocol
  - enterprise-architecture
  - api-gateway
  - agent-infrastructure
  - access-control
title: 企业级 MCP 架构之道：为什么“网关”是解锁 AI Agent 规模化部署的核心
summary: 本文探讨了企业在应用模型上下文协议（MCP）时面临的可观测性、访问控制和安全性三大挑战。Anthropic 专家指出，传统的 MCP 注册表难以满足企业级需求，提倡引入“MCP 网关”作为中继层，通过统一的认证、路由和安全隧道机制，实现 Agent 框架与数据层的深度解耦，从而降低安全团队负担并加速业务部门的 AI 创新迭代。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
products_models:
  - Model Context Protocol (MCP)
  - Claude
media_books: []
status: evergreen
---
### 企业级 MCP 的现实挑战：可观测性、权限与安全

大家好，我是 Karan Sampath，Anthropic 的前线部署工程师。今天我将分享 Anthropic 关于**模型上下文协议**（Model Context Protocol: 用于连接 AI 模型与数据源的开放标准）在企业环境中应用的思考。我给这场演讲起了一个更吸引人的标题：为什么我们认为**网关**（Gateway: 充当中介层的系统架构）是企业唯一的选择。

目前 MCP 发展迅猛，官方注册表已拥有数千个服务器，且规模在过去一年呈指数级增长。然而，企业在尝试使用它时遇到了三个“拦路虎”，我将其称为“三头犬”挑战：
1. **可观测性**（Observability: 监控系统内部状态的能力）：企业需要明确谁在调用 MCP 工具、哪些部分运行异常，而目前的协议对企业来说几乎是不透明的。
2. **访问控制**（Access Control: 限制用户访问资源的技术）：如何确保只有特定组能访问敏感服务器？例如，全公司可以查看故障仪表盘，但只有运维团队能修改它。
3. **安全性**（Security）: 这包括如何验证服务器的安全性、防止**数据泄露**（Data Exfiltration: 敏感信息被非法转移出企业网络），以及如何允许外部不受信任的客户端安全地访问内部私有数据。

<details>
<summary>Original English Source</summary>

All right. Um so everyone, I'm Karan Sampath. I'll be talking to you about how we Anthropic think about MCPs in the enterprise. I've alternatively titled it, I think more catchily, is why we think gateways are all you need. Um so before I go into the talk, I'm going to quickly tell you a bit about me. I'm a forward deployed engineer at Anthropic, first one outside the US. A lot of my work includes working with enterprises on things like MCPs, and I also work on our internal use cases.

In this talk, I'm going to be positing to you what we think the problems with enterprises, what enterprises face with MCPs today, why we think gateways and the necessary implications that come out of it are the best way to fix a lot of these problems, and how does that align with our future vision for agent tech deployments.

MCPs is an open standard that was created at Anthropic. There is an official registry today which contains over thousands of servers, and this is growing rapidly over the last year. Individual companies all the time are building new servers very quickly, and are trying to ensure that they stay ahead and trying to adhere to this protocol nowadays. But still, even if this happens, we see a major problem when enterprises try to use it.

Enterprises struggle to deal with what they believe to be table stakes. Things like observability. When they want to know who's using my MCP, who's using these tools, how do I ensure that the correct people are using it, and how do I know how to develop on certain parts of the MCP protocol, which parts of my tools aren't working properly. These are something that's simply completely opaque to enterprises today.

Second is access control. How do I ensure the correct users have access to these servers? Things like ensuring that certain servers are scoped correctly. Tools are only allowed for certain groups of servers. If you're working in observability MCP, you might want the entire company to have view into which things are failing, but only certain people to have the ability to actually change things and update new dashboards. These are the kind of things that currently are quite hard to do with MCP servers. And honestly, not something that we as a community have worked on enough.

And finally, security. And I like to think of the three of these is almost like a three-headed hydra. Security is a wide range of things. Enterprises want to know how do you verify whether a server is safe, it has the correct protocols and the correct ways of ensuring data exfiltration doesn't occur, things like the tools can't be used in a harmful way both for infrastructure externally and your internal infrastructure as well. But secondly, how do you ensure remote clients that are perhaps untrusted in nature can access your private data as an enterprise? These are all really hard problems that you've kind of solved in previous paradigms with APIs, but we really don't have a good way of solving it at the moment.

</details>

### 注册表的局限与企业创新瓶颈

虽然 **MCP 注册表**（Registry: 存放可用服务器定义的目录）非常有用，但它对企业来说并不完整。MCP 协议的设计初衷是让企业级应用更强大，但在身份验证、权限控制和凭据管理方面，目前还存在巨大的空白。

在这种背景下，企业内部会出现一种尴尬的局面：各个团队都在利用 AI 快速开发 MCP 服务器，却发现根本无法部署。或者部署后，安全团队因为无法穿透黑盒进行审查而感到焦虑，从而导致审批积压。对 CEO 和管理层来说，他们会疑惑：“为什么我们的 Agent 效率这么低？为什么它们无法完成预期的工作？” 这种由于安全边界与开发自由度之间的矛盾产生的**瓶颈**，极大地限制了协议的发挥。如果企业仅停留在使用少数几个现成工具的阶段，Agent 的潜力将被扼杀。

为了打破这种僵局，具体的架构转型思路如下：

<details>
<summary>Original English Source</summary>

Registries are really useful, and I don't think there's any discussion here where we think they're not useful. We're really proud of it and we're really happy we helped develop this. But it's really important to realize that registry simply aren't complete for an enterprise. MCPs were specifically designed because they allow themselves to be so much more useful for enterprises. And there's this kind of gap which the protocol allows for that we have yet to build into well, and these include things like authentication, but also access control, observability, and credential management. These are all things that enterprises need and are critical part, but are simply not working.

So now that we have this happening, what do enterprises do nowadays? What they do is something like this, where every single team now with Claude, you know, and explosion of coding across various surfaces, can now start developing MCPs. But suddenly find out that they can't actually get them deployed. Or even if they want to get them deployed, the MCPs often can't use the tools they want to, those tools can't give them the correct access, and security teams on the other end are also pretty justified how they're going about it, because they're often overloaded, and they're often unable to see which MCPs they want to go through, and which they want to allow.

And finally, at the company level, CEOs and C-suites are like, "Why are my MCPs not working correctly? Why are my agents ineffective? Why can't your agents actually be the thing that we all thought it was going to be?" And so this bottleneck, which we're seeing right here, is something we need to solve. We need to ensure that security teams aren't overloaded, that users are given the freedom to actually develop their own MCPs, and organizations have visibility into all of them. This problem where enterprises stay with a handful of MCP tools is going to fundamentally restrict the protocol and hurt agents until we really go and solve this. It's really valuable to think how important these paper cuts are, and how valuable it is to try and invest the time to try and solve it super well.

</details>

### 核心解药：建立以“网关”为中心的信任根

解决企业级安全部署的直觉在于：当所有团队都能利用 AI Agent 轻松构建 MCP 服务器时，安全团队不能再逐一审批，而必须建立一个**信任根**（Root of Trust: 安全系统中不可置信的起始点）。

我们建议企业“加冕”一个统一的平台——即 **MCP 网关**。它作为一个中间层，介于数百个 MCP 服务器与任何 MCP 客户端（如 Claude.ai 或 IDE）之间。有了这个中介层，新的 MCP 服务器就不再需要独立处理认证、权限、可观测性、安全连接和部署这五件事。业务团队（如法律团队）只需要关注**业务逻辑**：例如，合同进来后如何红线标注、如何上报。他们不需要操心谁有权访问、系统如何扩容或如何保证安全，因为这些“基础设施负担”已由网关接管。

<details>
<summary>Original English Source</summary>

The core intuition here is at a point in which almost all of your teams can build MCP servers really well, or have the ability to theoretically be able to do so because they're simply using coding agents that can understand the structure of the servers very well. The really important thing for security teams and enterprises that want to allow this to be decentralized is they need to establish a root of trust. And so we think that the goal for any security team is to bless one platform.

Enterprises that are able to do this, in our experience, are able to explore the usage of MCPs, and thereby explore the usage of how powerful the agents are. MCPs usage is exponential; every good MCP you have helps all of the agents in your company.

A gateway, as a black box definition of it, is simply a middleman or sort of middle layer in between your MCP servers, and they can be numerous into the hundreds, and any MCP client. What we want to get out of the gateway are things like authorization, authentication, observability, ensuring that you have clear secure connections between your MCP client, which might be untrusted, and internally. And also finally, an easy way to host and deploy any new MCP server.

What this allows for is that any new MCP server now does not have to deal with any of these five things. And a team that wants to add a new server only needs to care about what is the business logic. So your legal team which wants to review contracts only needs to care about, okay, if a contract comes in, this is what I want to be seen, this is how a redline should happen, this is how you should escalate to different people. They don't need to ensure who accesses this, how often can it be accessed, how do I know it's being accessed correctly, how do I know it's scalable. A gateway is a fundamental piece of that infrastructure.

</details>

### 网关的组成要素与六大技术优势

一个完整的 MCP 网关通常包含以下核心组件：
*   **身份认证与角色访问控制**（RBAC: 基于用户角色的权限管理）
*   **路由代理**（Proxy: 隐藏后端服务器拓扑，实现负载分发）
*   **安全隧道**（Tunnel: 建立加密的端到端连接）
*   **子注册表**（Sub-registry: 存储企业内部私有的 MCP 定义）
*   **开发者工具集**（CLI: 让 Agent 也能轻松集成的命令行工具）

这种架构投资会带来一系列“免费的午餐”：
1. **多端一致性**：只需配置一次，即可让 MCP 服务器同时支持 Claude.ai、Claude Core 或其他新终端。
2. **深度安全连接**：支持完全加密，防止企业核心资产在传输中丢失，建立真正的根信任。
3. **极速迭代**：法律或财务团队可以自主修改 Workflow，无需重复进行耗时的安全评审。
4. **标准化原语**：网关可以强制要求所有 Agent 遵循企业的**标准作业程序**（SOP: 指导员工完成复杂日常工作的详细说明）。
5. **可插拔凭据**：支持在公司账户、团队账户和服务账户之间智能切换凭据。
6. **规模化扩展**：将处理成千上万个 Agent 请求的压力从零散的服务器转移到成熟的网关层。

<details>
<summary>Original English Source</summary>

What does a gateway contain? There are normally these components: a way to do auth, a way to do access control using roles, a way to route using a proxy such that any MCP client can only see your gateway, and the gateway then can route to the individual MCP servers. You want a way to ensure you have a tunnel which is a secured connection. You want to have a sub registry, which is your MCP servers internally. And finally, you would want to have any additional tooling like a CLI for your gateway.

Someone who just wants to create a new MCP server can use the gateway CLI and just easily integrate into these five components, and then completely focus on their MCP server.

Looking at what this gives you: you have a vision of a gateway which can give you access authentication very easily. You might have your own IDP which you can plug in. You can have delegated identity in terms of users and agents. This is something we think is going to be really important where agents are going to require newer and novel definitions of identity. Observability here is nuanced; you not only want usage metrics, but you also kind of want to know how are your tools being defined. How do you better adapt them to meet the needs of your various agents?

There's a lot of exciting follow-ons or almost free lunches you kind of get from there. The first is it's very easy for you to add any new surface. You only need to do it one time. Compare that to the world where you have 40 different MCP servers. The second is you have far more secured connections. You can now invest in much more secured connections between your MCP server and your client that is completely encrypted. The third is faster iteration. If the legal team is able to iterate on their legal MCP rapidly without repeated security reviews, that has a massive effect. The fourth is that you get more standard primitives. A gateway is a way of encoding your standard operating procedures. The fifth is pluggable credentials, allowing any new MCP server to easily support new credentials and swap it in and out in an intelligent manner. And then finally, it's scalable. A gateway is a far better place for your teams to focus on.

</details>

### 未来愿景：解耦 Agent 框架与底层数据

展望未来，我们的目标是实现**Agent 框架**（Agent Harness: 承载 AI 逻辑的运行环境）与**数据层**（Data Layer）的完全分离。

目前 Agent 数量呈爆炸式增长，但它们不应该与你的数据结构或 MCP 结构紧密耦合。通过 MCP 网关，作为企业，你可以灵活决定哪些 Agent 留在内部，哪些部署在外部（例如使用 Claude Managed Agents 或内部 SDK），而网关始终作为不变的基础设施存在。这为你提供了应对未来多样化 Agent 需求的灵活性。

总结来说，企业应关注三点：
1. **投资通用基础设施**，不要重复造轮子，让业务团队专注于构建自己的 MCP 业务逻辑。
2. 利用**网关建立安全连接**，从而在企业内部构建根信任。
3. 推动 Agent 运行框架与底层数据层的解耦，迎接未来的大规模部署。

<details>
<summary>Original English Source</summary>

I want to take these last few minutes to think about where we're going with this. We want to ensure the larger picture: we want to separate the agent harness from where your data lives. We see an explosion of agents, but those agents shouldn't be tightly coupled to how your data is structured and how your MCPs are structured.

If you have an MCP gateway, you can easily connect it to Claude managed agents which was released recently, but you can also build it into use it internally with your own Claude agent SDK as well. As an enterprise, you now have the ability to quickly decide which agents you want to keep in-house, which agents you want to have outside, but that becomes an invariant decision. The gateway remains regardless. The gateway is an investment which will allow you the flexibility to meet the wide-ranging agent needs of the future.

In summary, three main things: The first and the most important takeaway is to invest in common infra, to not try and roll your own MCPs, and to ensure your teams can build their own MCPs. Second, gateways for secured connections allow you to build that root of trust. And third, that moves towards a world where we think the agent harness is better separated from your data layer. Thank you so much.

</details>