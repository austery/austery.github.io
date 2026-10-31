---
author: AI Engineer
date: '2026-10-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=s-glGHAa1a4
speaker: AI Engineer
tags:
  - ai-gateway
  - vendor-lock-in
  - roi-maximization
  - identity-based-security
title: 告别厂商绑定：Tailscale 如何通过 AI 网关实现架构解耦与 ROI 最大化
summary: Tailscale 战略项目团队的 Remy 剖析了从“Token 极大主义”向“ROI 极大主义”转变的行业趋势。他将企业内部 AI 部署解构为 LLM、数据连接、交互界面与沙箱环境四大核心组件，并详解了基于 Tailscale 身份网络构建的开源网关 Aperture 如何实现无缝鉴权、细粒度管控与自由选型，彻底摆脱单一供应商绑定。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Tailscale
products_models:
  - Aperture
media_books: []
status: evergreen
---
### 从“Token 极大主义”转向“ROI 极大主义”的现实困境

在过去的一年里，整个 AI 领域被**“Token 极大主义”**（Token Maximism: 盲目追求并挥霍百万级别上下文窗口及海量 Token 吞吐的开发模式）主导。借助百万级上下文窗口（Million-token context window）、MCP（Model Context Protocol）以及各种强大的 CLI 编程工具，开发者能够轻松将全量上下文喂给大语言模型，从而推动了真正意义上的**智能体编程**（Agentic Coding）及各类 Agent 场景落地。然而，这种繁荣背后伴随着极高的财务成本和严重的资源浪费。在实际的网关监控中，经常能看到长达数百甚至数千条对话的长会话，用户从不清空上下文，导致单会话消耗数千万 Token，进而引发企业内部对 AI 预算失控的恐慌。

面对飙升的成本与财务、IT 部门的施压，许多企业的直觉反应是“合并供应商”——强制全员统一绑定至单个或两个顶尖闭源模型厂商的全家桶生态。但这种慌乱中的垂直整合往往适得其反，不仅加剧了**供应商锁定**（Vendor Lock-in: 用户高度依赖特定厂商导致切换成本极高的状态），更限制了技术创新的灵活性。因此，未来十二个月的核心任务必然是从单纯追求用量的 Token 极大主义转向**“ROI 极大主义”**（ROI Maximism: 通过提升实际业务产出价值、降低单位成本来最大化投资回报率）。ROI 极大化绝非简单的盲目砍预算，而是通过解耦核心架构，让企业能够根据任务需求自由选择最优成本的模型与工具组合。

<details>
<summary>Original English Source</summary>

[Speaker 1]: well, hi folks, um thanks for joining me here for the last talk on this stage of of the AI engineer world fair this year. um yeah, thank you for joining me. My name is Remy. I'm on the strategic projects team at Tailscale. And more specifically, I actually work on our AI gateway Aperture. And today, I want to talk a little bit about, you know what it means, you know what it's going to take to have an AI future without the lock-in, a lot of what we've seen over the last twelve months.

And yeah, so if we take a look real quick, you know, the last twelve months, you know, I think can really be described quite a bit by the phrase token maximism. And I don't mean that in the kind of negative sense that you might kind of hear outside of the AI enthusiast circles. I mean, that in the sort of it's been a year of trying to figure out you know what we can do with million token context windows um with the ability to get context from anywhere, right? Not just, you know, MCP being everywhere, but you know also having coding tools that are that great at finding context using the CLI, bring that context into the model, bringing it, you know, bring it into the thing that you need and going from there, right? It's been pretty cool, right? I mean, we've gotten. It's really made truly agentic coding possible having all of this, right? So yeah, it's quite cool and you're going to see not just agentic coding, but you know, other agent use cases continue to take off as we do so.

So you know token maximism is cool, but right it has problems, obvious problems, and it's very expensive. Right? It's an extremely expensive endeavor. You know, I think the last months have maybe been marked by: "Hey, we have, you know, an unlimited AI budget," and that's changed here in the last few months. In terms of just incentivizing what it means to use AI. And also, I mean, you know it's expensive, like just generally, if you're doing it, you're right, but it also does incentivize what I would call like wasted tokens by default. I mean, I work on an AI gateway. We use our AI gateway. I get to see all of the usage through the AI gateway. You would not believe the number of sessions that are hundreds or thousands of messages long, where nobody clears the context, they just kind of keep going. I mean, it's helpful sometimes, but you know it's pretty surprising—you will have, you know, tens of millions of tokens a session where the cache basically times out the entire time. It's really expensive.

And another thing, right? This has been an exciting time, if people are doing things, building things, but this has led to, you know, in many cases, very vertically integrated toolchains. Claude Code is, obviously, you know, a big one, Codex, everybody's kind of building up there, you know, from the model all the way to the top, building their own tooling, their toolchains. So there's a lot of problems there. And so you know, my question in terms of this is: how do we address these problems? In particular, how do we address the lock-in? And how do we actually improve how we use AI such that we can use it for things that aren't just essentially frontier tasks, where we're just kind of wasting money, wasting tokens?

But first, I want to talk about how not to address the problem. And this is a super common thing. In the last six months, we've been talking to hundreds and hundreds of folks about their AI spend, their AI usage, right? That's the benefit of working on an AI gateway—folks come to you. They're like, "I don't know what's going on. I know we're using a lot of it. I get an Anthropic bill every day, I get a Codex bill every day." So you see it all the time. So what do they usually come to as a solution? It's, "Oh, everybody seems to be using Claude Code, right? So we're just going to consolidate on a single vendor, maybe two vendors, right? I need to get a handle on this. How do I get a handle on this? Oh, okay, yeah, everybody's going to use this. We're just going to use this thing."

That is not a great idea. It might seem obvious sitting here, but it's not a great idea. But you know, you're in that panic zone: we've spent a lot of money, and we don't know how exactly, and finance is talking to you, IT is saying "what are you doing?" And it's a pretty natural reaction: "Okay, I'm going to consolidate everything down, right? I'm going to have control over this." And you know, I think this is kind of pointing at what we're going to see the next twelve months in what people are actually trying to do, at least as opposed to token maximism: what I would like to call ROI maximism. We're not going to be token maximism, we're going to be ROI maximism. And it's really just necessity, right? When I say ROI maximism, I don't just mean cutting costs, right? I mean actually proving some sort of value to the thing that you're doing, and not only that, but also kind of opening things up, right? If the only thing you have is two frontier models and their entire stack ecosystem, that's a certain cost level where it just makes certain things untenable, right? You can't actually expand AI usage across the company if that's the only way you can use AI.
</details>

### 解构内部 AI 部署：四层架构与多维决策权

在建立实现投资回报最大化的技术策略之前，必须先理清企业内部 AI 部署的系统构成。一套完整的内部 Agent 体系可以清晰地拆解为四个独立组件：
* **大模型层**（LLM Layer）：包括各类开源及闭源的基础大语言模型；
* **数据连接层**（Data Connector Layer）：智能体获取外部数据与执行动作的桥梁，典型如 **MCP**（Model Context Protocol: 模型上下文协议），也包括传统的 CLI、REST API 或本地文件读取通道；
* **交互界面层**（Interface Layer）：从最初的 Web 聊天窗口、IDE 插件、移动端，到当下深度集成的 Slack 机器人或终端应用；
* **沙箱环境层**（Sandbox Environment Layer）：智能体代码执行与工具调用的安全运行时隔离环境。

**ROI 极大主义**的核心实质，是在上述每一个层级上都最大化保留自主选择权（Maximizing Choice）。不同部门与业务场景在各层级的诉求大相径庭：研发团队可能偏好在 IDE 或 CLI 中使用代码审查智能体，而市场团队则更习惯直接在 Slack 讨论流中向数据分析智能体提问。如果企业将整套工具链硬编码绑定在单一厂商的技术栈上，就会丧失架构灵活性。通过在各个层级实现标准化解耦，团队便能针对不同任务灵活搭配最契合性价比的组件，这也是引入中立 **AI 网关**（AI Gateway: 充当应用程序与 AI 模型/工具之间代理的管控与接入平台）的真正价值所在。

<details>
<summary>Original English Source</summary>

[Speaker 1]: And so when we think about ROI maximism, we first need to kind of think about like what are the components of an internal AI deployment. I'm not talking about like, "Hey, we built this new AI feature in our app." I mean, you know, internal to your organization. So there's four things, right:
There's the LLM layer.
There's sort of the data connector layer—this is MCP for a lot of people, but in reality, it's CLI or API or really just any way that you get data, could be reading a file right into your agentic system.
There's the interface—I think people kind of forget about this sometimes, but you know it started with chat interface, we got IDEs with chat, we got backlash from IDEs, and you know "I'm going to do my code on my phone," to "Oh, now the thing is Claude Code and how do I interface with agents via Slack, right?" So it's another core component, and it is a component that you can break out.
And then the last, when I say sandboxes slash just the environment in which the agent runs, right.

So there's your four components really. And to be ROI maximism means to be maximizing every opportunity that you have for choice to make a choice at one of those layers, right? You don't have to necessarily have made a bespoke special choice at every one of those layers, but it's really important to be able to make a choice at any given layer that you need to hit at any given time. And it might be different for different layers or different roles; it can be pretty different across the organization. I can't totally imagine an entire engineering team just coding via a Slack thread—might be fun, but I don't totally imagine that—but the entire marketing team might be working entirely in a Slack thread, asking data questions, doing other things like that. So it's really important to be able to kind of separate these things.

And right, so I work at Tailscale, and I work on our AI gateway, but you know, maybe no surprise, I'm here to talk a little bit about why an AI gateway will help you do that, can help you do that. I don't just mean using our AI gateway—I think it's nice, but just any AI gateway is important for this.
</details>

### 基于身份网络的网关实践：Tailscale Aperture 的解耦架构

Tailscale 孵化的开源 AI 网关 **Aperture** 正是基于解耦理念构建。传统 AI 网关通常要求管理员在网关注册底层大模型 API Key，再为每位用户或服务分别生成一套虚拟令牌（Synthetic Keys），在企业规模扩展时带来了巨大的密钥分发与权限维护负担。Aperture 彻底改变了这种模式，其底层依托 **Tailscale** 基于 WireGuard 构建的**基于身份的网格网络**（Identity-based Mesh Network: 节点间通过真实身份而非静态 IP/Token 进行鉴权与互联的虚拟网络）。在这一架构中，所有运行 Tailscale 客户端（Tailnet）的容器、开发机或 GPU 节点，其发起的每一条流量连接都原生携带机器标签（Tag）或真实用户身份信息，并能与 Okta 或 Microsoft Entra 等身份提供商同步用户组信息。借助底层开源网络库 **`tsnet`**，网关能对接入端发起者做到零门槛精准识别。

依托这种原生身份感知能力，Aperture 在各核心层级上实现了无缝治理：
* **大模型访问与动态配额**：网关统一托管 Anthropic、OpenAI、AWS Bedrock 等厂商凭证。客户端在接入网关时无需额外配置任何认证参数，网关根据其身份策略自动鉴权并分配配额——例如为普通开发者开放廉价模型（如 GLM-5.2）的无限预算，但对前沿尖端模型（Frontier Models）施加极其严格的限额；
* **MCP 与 API 统一数据接入**：Aperture 不仅是 LLM 网关，更是统一的 **MCP 网关**。它能够将标准 REST API 包装并注入鉴权头转换为 MCP 暴露，同时消除市场上不同 MCP 服务鉴权规范混乱、版本碎片化的问题。管理员可针对部门细分数据权限（如为市场团队开放 Google Calendar/Gmail，为研发团队开放 GitHub，甚至按组划分读写控制），且无论开发者使用 Cursor、Claude Code、Codex 还是自研 Agent 框架，只需指向网关统一端点即可自动继承 Tailnet 身份，免除了在每个工具中重复鉴权的磨损成本；
* **会话全链路洞察与根因诊断**：网关保留完整的交互审计日志。当智能体执行陷入死循环或因廉价模型推理能力不足而产生“失控螺旋”时，开发者可以直接将网关审计日志反馈给模型进行复盘反思，大幅提升排错与调试效率。

<details>
<summary>Original English Source</summary>

[Speaker 1]: So our AI gateway is called Aperture. And what it does is—it's maybe no surprise here, right—it sits in between your agents and that interface, and all of your endpoints, as well as both LLM endpoints and data MCP endpoints, API endpoints, anything that you have. It sits in the middle and lets you both control and monitor what's happening. That can be from a security perspective, that can be from a cost perspective, that can be from—which we do a lot—"I want to learn about what somebody is doing or what an agent is doing" perspective.

It's actually really cool when you have logs, and you can tell your agent, "Hey, it didn't reach an answer, it just kind of spiraled out of control." That definitely used to happen quite a bit; it happens with cheaper models more often too. They're usually not great at stopping themselves, but they are great at analyzing where they went wrong after the fact. And so when you have something like an AI gateway, it's really easy to point it back at what you were doing and say, "What happened? Why did this not work the way I was expecting it to?"

And so, you know, if you've used an AI gateway before—how many people have deployed an AI gateway, using an AI gateway? Yeah. So if you've used one before, you're probably used to: "Okay, so I put all my keys on the gateway, now I need to go create synthetic keys for everything that I have, right?" So it's turning some keys into a bunch more keys. We get to do something a little special: Aperture is built on Tailscale. And if you're not familiar with Tailscale, Tailscale is an identity-based mesh network. It's based on WireGuard. And what you get to do with Tailscale is every connection that is made over a Tailscale network—you install the Tailnet agent everywhere that you need, can be containers, laptops, GPU servers, doesn't matter, install it everywhere—every connection that's now made over that Tailnet comes with the identity of the machine or the user on the other side. So that can be a tag, right? It can be like, "Hey, this is the machine that is doing PR review bot," and then it would get a separate node ID underneath: "This is the instantiation of that PR review bot, right?" Or it can be the user: it's just me using Claude Code on my laptop, that can come with it as well. In addition to, if you're using something like Microsoft Entra or Okta, we can actually sync all the groups so you can see the group that that person is associated with.

We have this really cool library called `tsnet`, an open-source library you can use to build these sorts of apps. That is what we used to build Aperture. That is what is actually happening here. So it is able to see the identity of that user or that agent on the other side of the connection.

And so, again, just my components of an internal AI deployment: there's the LLM side of things, the data side of things, the interface side of things, and the actual sandboxes/sandboxing environment side of things. When it comes to using Aperture, as far as LLMs go, this is pretty similar to what you might expect from other AI gateways, except here I configure the gateway—it's got Anthropic, OpenAI, AWS Bedrock, everything you can imagine. I put all those keys on that gateway. And then now when I want to actually connect to that LLM provider as an agent or a user, there's no extra screen to create these API keys, create these identities. Once I connect to the gateway, it knows who I am, and it's like, "Oh, you have access to this provider. You can use GLM-5.2. You get this budget with GLM-5.2. You get an unlimited budget with a cheap model, and you get an extremely narrow budget with a frontier model," right? Those sorts of things. There's no extra setting here—it's just configure the API and go. So again, we've taken all the LLM layer, and we've put it into one place that you can expand out within your organization. Doesn't matter if you try to switch models or providers, you can do that.

The next thing is the data side of things. In addition to being an LLM gateway—and this is actually why I said "AI gateway" at the beginning, I specifically chose that term because we're both an LLM gateway and an MCP gateway, and we even do auth injection for just standard APIs and re-expose those as MCPs too, intentionally choosing the broad term here. In Aperture, as an admin, you can go in and configure whatever MCP servers you want. We have built-in ones where we've checked them out, made sure they're easy to work with. If you've ever deployed an MCP or used MCP within your organization, you know that there's a standard, but everybody follows a different version of that standard. You can tell exactly when an MCP server was built by exactly how they decided to do auth—it's an archaeology lesson when you go through setting up MCP servers. But we try to make that a very simple process here. So you as an admin can say, "Hey, these are the ones that are allowed." You can use that same identity information to say the marketing team gets access to Google Calendar and Gmail, but the engineering team also gets access to GitHub. You can even say this side of the engineering team gets write access to GitHub, or read-only access to GitHub. You can do all sorts of things here.

And what's really nice, again talking about decoupling, is all of the authentication happens here. So if you have folks that want to use Cursor, or Claude Code, or Codex, or some special agent framework, all they have to do is hit that endpoint. And if they're on the Tailnet, everything is authenticated as them or as whatever the agent/tagged device is. There's no "I have to go re-auth everything and then re-auth in this new tool." We make the switching cost of actually trying out tools and trying different workloads and different experiences a lot easier. It's all those little points of friction that lead to use cases where people just don't try new use cases—they don't experiment to make things cheaper or faster.
</details>

### 通用翻译层演进：界面透传与沙箱编排的未来

在解决模型与数据接口层之后，AI 网关进一步向**交互界面层**与**执行沙箱层**延伸。Aperture 虽配备了开箱即用的 Web 聊天界面，但其核心逻辑完全暴露为可扩展 API，支持团队构建 Slack 机器人、专用移动端乃至语音交互应用。在以往部署 Open WebUI 或 LibreChat 等开源前端工具时，团队常面临一个致命缺陷：所有请求均以系统级凭据发起，导致后端完全丢失终端用户或机器的真实身份。为此，Aperture 正式引入全链路身份透传（Pass-through Auth）机制，使团队在自建多样化前端界面的同时，依然能在网关层保有端到端的安全审计能力。

针对第四个核心维度——沙箱运行时，业界目前处于百花齐放但碎片化严重的阶段，各团队对沙箱隔离与环境能力的需求各异。针对这一痛点，Aperture 正在扩展构建专属的**沙箱编排层**（Sandbox Orchestration Layer），使 AI 网关进化为连接前端界面、沙箱容器、数据连接器与大语言模型的**通用翻译层**（Universal Translation Layer）。

引入 AI 网关的战略意义远不止于防范供应商锁定与降低调用成本，更关键的是消除技术栈摩擦，激发团队的实验创新活力。无论是企业管理全局成本与安全边界，还是个人开发者监控本地智能体在后台的意外行为，一个兼具身份感知与协议适配的网关都是构建健壮 Agent 系统不可或缺的基石。

<details>
<summary>Original English Source</summary>

[Speaker 1]: Next thing, talking about the interface. With Aperture, we actually have a built-in chat UI—surprise, everybody seems to have a chat UI. However, it is built on top of an API that you can also leverage yourself. Our whole goal with Aperture is to actually provide you with the tools to build the interfaces that you can, whether you want to build a Slack bot, tools that nobody thought of, some mobile thing, voice-only interface, right? You can do that. We want to support all of those different individual use cases. But again, you can see it has connectors; those are all set up through Aperture itself and not set up in the chat UI.

Talking about interfaces, the one other thing that's coming very soon here: if anyone ever tried to set up Open WebUI, or LibreChat, any of those interfaces, one big thing is you always lose identity information. And then suddenly everything is coming from the UI, everything is coming from the system. We're actually going to be adding full pass-through auth, so you will be able to actually see all of the user identities and machine identities for reasons they're using whatever interface you have set up, such that you can pass through the auth and still get all of the same visibility that you're expecting from an AI gateway.

And the last thing is sandboxes. This is actually the area in which folks are doing pretty good; there's actually a lot of choice already, people are trying to do this. I think that's because the definition of a sandbox—I'm sure I could poll everybody here and everybody would have a different definition of exactly what a sandbox is or what they need from a sandbox. So we're kind of in that "let a thousand flowers bloom" phase, where there's a sandbox provider for every sort of need and want out there. Folks are doing a pretty good job integrating them, but again, it's a really important thing. We are actually going to be adding an orchestration layer as well for sandboxes to our gateway.

Again, choosing that term "AI gateway" very loosely, intentionally very loosely, because in order to make the best choices for all of the different endpoints that you have—your environments, LLMs, data connectors, all these things—you really do need to have a place to see them all, and then a place that brings them all together, such that you can use them with each other. Kind of a universal translation layer, in a way.

So that's mostly that. And as a reminder here: ROI maximism really is all about maximizing choice to prevent lock-in, right? Even if you don't use Aperture, I do highly recommend you start considering an AI gateway. Look at an AI gateway beyond just, "Oh, I don't have to configure three different providers and switch between them." It's great for just understanding what agents are doing. Even if it's just you as an individual—we have so many people who as an individual have their usage behind an AI gateway just to have an idea of what their agents are doing. Because very commonly, people run something like open Claude Code on Tailscale, and it's on their Tailnet running in the background, and they're like: "Oh my god, it did something, I'm not sure what it did, it did something it was not supposed to do." With something like an AI gateway, you can actually go back and look, and you can actually diagnose what went wrong, what happened.

So it's not just lock-in; it's actually just experimentation and understanding. It's very important to use an AI gateway. So that's it. Thank you very much for attending. This is the last talk here of the day, so I hope everybody's had a really great conference. I love the AI Engineer World's Fair, and I hope you do too. Thank you.
</details>