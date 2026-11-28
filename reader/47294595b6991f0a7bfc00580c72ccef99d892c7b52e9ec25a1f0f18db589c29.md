---
author: AI Engineer
date: '2026-09-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=wCIYViPd4SU
speaker: AI Engineer
tags:
  - ai-agent
  - enterprise-architecture
  - identity-management
  - security-compliance
  - web-grounding
title: Tethered：以用户身份在云端安全运行 AI Agent 的企业实践
summary: 量化基金 Two Sigma 工程师 Shu Fang 分享了企业级 AI Agent 架构实践。面对本地 CLI 局限与多身份权限冲突，Two Sigma 基于 Kubernetes 基础设施让云端 Agent 以用户自身身份运行，并通过自定义追踪请求头（Trace ID）实现审计与溯源，结合 Google 企业网络检索索引在隔离 VPC 内防范数据泄露与提示注入，实现风险与收益的平衡。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Two Sigma
  - Google
products_models:
  - Claude Code
  - Kubernetes
media_books: []
status: evergreen
---
### 量化基金背景与 Agent 身份绑定的现实困境

**Two Sigma** 是一家拥有 25 年历史的量化对冲基金，长期处于高度监管的金融环境中。公司的名字来源于统计学中的“双西格玛”概念：将低波动性（Low Sigma）的各项策略汇聚，以分散风险并获取超额阿尔法收益（Differential Alpha）。在这样的强监管背景下，Two Sigma 成功构建了一个为每位员工提供专属**云端智能体**（Cloud Agent: 运行在云端集群、具备自主执行能力的 AI 实例）的生态系统，并且这些智能体均以员工自身的身份运行。

2025 年 6 月随着 **Claude Code** 等工具的面世，开发者开始广泛在本地终端中使用 Agent。然而，本地运行面临两大瓶颈：一是仅限于命令行界面（CLI），非技术人员上手门槛高；二是无法脱离本地环境全天候远程运作。团队希望员工能通过手机、Slack 或浏览器随时随地调用 Agent。最初的技术直觉是为每个智能体分配独立的“机器身份”（Machine Identity），并将其与用户账号做映射绑定。但这种做法在实践中迅速失效：双重身份导致权限同步极度困难、软件许可（Software Licensing）成本翻倍、部分企业协作系统（如 Google Workspace、邮箱等）天然不支持多身份并发操作相同数据，且公私数据权限边界模糊。

<details>
<summary>Original English Source</summary>

Perfectly. Thank you to everyone who came. This report is called "Tethered" or "Agents Everywhere". I'm Shu Fang from Two Sigma. Let's start. So, a brief explanation. Two Sigma is a small quant fund. Let me take this opportunity to explain that the name comes not from the fact that we have two co-founders who are constantly online, but from two sigmas: low sigma volatility and high sigma sum. By summing these individual volatilities, we can hedge risks and obtain differential alpha. Because we are a hedge fund, I must provide you with this important legal disclaimer. You don't have to read it. It just has to be here. In short, I'm not selling you anything. These are my personal views, not necessarily the opinion of the company. Mention of any logos or companies does not mean that I endorse them or recommend buying their shares. These are purely coincidental coincidences. It's also a smooth transition to the fact that we're an old company. We are 25 years old and operate in a highly regulated industry. But we managed to create an ecosystem where every employee has a cloud agent. Moreover, these agents operate under their own identities. So we'll explain how we came to this and why we're happy with it.

First, let's do a little review of the horror movie. If you've seen it, you can ignore it. If not, then in short: everyone has doubles, which are called "attached". When they break free, wreak havoc, and run around with golden scissors, they are called "untethered." And this applies to my report in a certain way. So, in June 2025, with the advent of Claude Code and other things, people started using agents locally on their computers. It's powerful, but, firstly, it's limited to a command line interface, and secondly, it's localized. We wanted to create a world where people could use these agents anywhere: via mobile phone, Slack, or browser, but at the same time run them remotely. This is important not only because of the functionality, but also because many people, technical or not, do not feel comfortable working only through the CLI. So the question arose: how do we launch them and under what identity should they operate?

The common thought is that you run them as some machine identity that is tied to your user in some way. You have a user and you have a user agent. But that quickly becomes unviable, and we found that out for every reason you can imagine, right? It is very difficult to keep permissions synchronized. Every time you deal with software licensing, you now have to deal with two licenses. There are certain systems that don't support multiple identities interacting with the same data, such as Google Workspace, your emails, etc. And some systems block it right away, so you have to overcome that barrier. And you also need to understand how you actually manage public and private boundaries.

</details>

### 基于 Kubernetes 命名空间的同身份云端架构与安全风险

针对上述痛点，Two Sigma 决定反其道而行之：直接让远程智能体以用户自身身份运行，从而完美继承既有的权限体系与数据访问通路。由于公司此前在日常自动化流水线与数据科学研究任务中，就已经为每位员工在各区域的 **Kubernetes** 集群中配置了专属命名空间（Namespace），这套既有基础设施被直接复用为 Agent 的运行底座。当触发指令到达调度控制器时，Pod 内的 Sidecar 容器会从专门的身份服务加载用户凭证并进行挂载，使容器内运行的 Agent 能够代表该员工执行操作。

然而，“以用户身份运行”带来了巨大的安全挑战。首先是**内部威胁与归因难题**：当员工与 Agent 共享同一个系统身份时，日志审计系统无法区分某项操作是人类主动发起的还是 Agent 自动执行的，这在需要严格审计、阻断与留痕的金融合规场景下是致命的。其次是**外部网络出站风险**（External Egress Risk）：大语言模型本质上是时间切片固定的数学函数，必须通过联网搜索获取实时信息；但一旦开放公网访问，企业将直接暴露在数据泄露（Data Leakage）、知识产权外溢、不可信内容注入、**提示词注入**（Prompt Injections: 恶意输入诱导模型违背安全策略执行攻击）以及版权合规风险之下。在金融的“风险-收益”（Risk-Reward / 夏普比率）权衡中，必须在不削弱功能价值的前提下最大限度压低这些风险。

<details>
<summary>Original English Source</summary>

So of course the question arises: why don't we just run them as a user, right? How do we run them remotely under the same user identity? As a result, all possibilities, all access, all previous restrictions no longer apply. We already had the infrastructure for this, and I think many of you have it too. If not, I would advise investing in it, for example, having a Kubernetes cluster. You have all your clusters, regions, etc. And you have namespaces for individuals, right? The reason we had this is that we often needed this capability not for agent purposes, but for all automated operations that could not be limited to the local machine. We run automated tasks, code in containers usually works on this principle, research notebooks, etc. And each user already had these namespaces in each region, and everything in them runs on behalf of the user.

Very simplified principle of operation: a certain trigger comes to your controller and says: "Hey, I need to start computing resources." You have a separate identity service from which the sidecar in the pods loads data so that your containers can start, mount that identity, and operate on your behalf. Of course, there are great dangers in this, right? The first danger you can imagine is an internal threat. How can you really tell who or what performed the action, right? You and your agent now have the exact same identity. That's why I grew this mustache so you can tell us apart right now. But it's really important for you to know this distinction because there are certain actions that you want to audit, maybe block, and just have a history of them being performed, right? You need to have attribution to determine, "Hey, was this a person acting in a purely human way, or was this an agent doing these things?"

Another danger, and perhaps a bigger one, is that we all know: for all these opportunities and for LLM in general, it is essential to have access to the external network. These are mathematical functions fixed in time that cannot be updated based on current data. So, it's like open access to the internet. That's why this is the main function—web search, tools for getting data from the web, right? The problem is that once you gain this capability, you become vulnerable to huge threat vectors. One of them is the risk of data leakage. This is something that we are very concerned about in terms of potential loss of intellectual property, you know, just exposing our confidential information, and also the possibility of untrusted content getting back out there. And, you know, prompt injections, just malware and vulnerabilities—those are all big risks. And another thing that we're working on separately is being able to make sure that we're not using licensed content without proper copyright or appropriate license, right? You can draw a parallel with the "golden scissors" they use in the US. So, honestly, that's our biggest fear.

We are a financial firm, and in finance there is the concept of risk and return. So when we think about positioning on the risk-reward graph, allowing agents to operate in this mode provides tremendous value, but also carries very high risk. We usually want to make sure we get the most benefit but minimize the risk. We optimize this risk-reward ratio. Some of you may know about the Sharpe ratio. We look at this from the perspective of how to enable agents to operate as users and optimize that profitability. And the ways we have to do that is by addressing these two critical issues. The first is the distinction between access attributed to a person versus an agent. The second is ensuring secure access to the network.

</details>

### 请求头追踪与企业网络检索隔离机制

为了解决归因与网络安全两大核心挑战，Two Sigma 实施了针对性的工程防护方案：

* **自传播追踪头（Trace ID 注入与溯源）**：借鉴分布式观测系统的 **链路追踪 ID**（Trace ID: 贯穿多个微服务调用的唯一请求标识）机制，在所有由 Agent 发起的 HTTP 请求中注入特定请求头（如 `XSL-Agent`）。借助定制 HTTP 客户端、**模型上下文协议**（MCP / Model Context Protocol: 连接大模型与外部工具的统一标准接口）以及 Agent 技能框架，将该标识在跨系统 RPC 调用链条中逐级透传。这样既保留了用户的身份执行权限，又能完整重建操作来源与调用链路，实现精准的审计与权限管控。
* **企业网络检索隔离（Web Grounding for Enterprise）**：针对公网数据泄露风险，团队禁用了原生 Agent 框架自带的外部抓取与搜索工具（例如 Claude Code 默认的 Brave Search 接口），转而接入 Google 面向强监管行业提供的企业级 **网络检索对齐**（Web Grounding: 让大模型基于受控检索索引生成事实依据的机制）服务。所有查询与数据抓取全部收敛在企业私有虚拟云（VPC）内部完成。虽然检索索引存在 6 至 24 小时的数据时效延迟，但它彻底切断了数据外流通道，大幅降低了提示注入风险。

<details>
<summary>Original English Source</summary>

So the first thing we did was this attribution step, right? And we did it with a headline. We make sure that each individual agent continues to add data to this header. And that's something we've all, I hope, done to some extent, right? Trace IDs. You all did this in deterministic code. Make sure your observability stack propagates the trace ID across all disparate systems. We did it almost exactly the same way as we do for the trace ID, except for a slight difference in the control vector, namely the agent itself, right? You can force, using certain HTTP clients, MCPs, or skills, to ensure that this header is initially populated and then propagated everywhere, right? You have much more deterministic control over agents, bindings, and frameworks than you might think, and you can do this using existing primitives.

This gets really interesting because we get more than just proper identification of who did something, right? This goes far beyond these limits. We are no longer limited to just knowing the identity of the performer, we also get the full origin story through the entire system, right? By working with many steps in the system, we can recreate the entire chain of actions that led to a certain end result. The comparison is this: if we used the agent identity, we would not have this, but only knew that at some point the agent initiated a flow into the range, but would not be able to trace the subsequent actions back to the point of origin. With this header, this trace ID, we get full distribution, and I'm still the executor, right? This is still my personality.

And the second step that we needed to fix was access to web resources, right? Many web access tools today use indexes for search, right? I think Cloud Code uses the Brave web browser and its index. We thought, "Hey, why not see what Google has to offer, right? Google is still, hopefully, a search engine company at its core, and they're already doing indexing." It turns out they offer a solution specifically for regulated industries like ours that allows you to use their web index in your existing VPC and with your network controls, right? It's called Web Grounding for Enterprise. It works something like this: everything stays within the same network, where you probably run your cloud agents and stuff. It offers two main capabilities: searching and retrieving data, right? That is, exactly the possibilities that we wanted to recreate. We use it and get all these guarantees. There is one small downside: the data will obviously not be completely fresh, right? And the limits on this, last time I checked, are 24 hours for fresh data, and 6 hours for sites that are updated more frequently. But for most agent use cases, this is probably quite sufficient, and it completely eliminates the external egress vulnerability vector.

Now the second question: how do we actually ensure that agents use web grounding? And again, it's very simple with the available primitives, right? You just need to make sure they don't get mixed up. And you're certainly blocking the access itself, but for user experience and things like that, you need to make sure that these tools themselves, which already exist and are primitive and native to these agent systems and frameworks, are actually blocked, right? Again, here is an example of Claude's code. I think every other system has the same thing. Web search, web data retrieval. We simply prohibit these tools. It's like, "Hey, you can't even use them." They are not even in your toolbox of useful tools. Instead, we use redirects via MCPCLI and actual client code, using supported paths and skills, to ensure that when someone needs to access the internet, they go through this cached web grounding index.

</details>

### 安全受控下的企业全员 Agent 规模化落地与演进

通过为智能体“栓上缰绳”（Tethered）——即在同一用户身份下实施请求头归因与网络沙箱隔离，Two Sigma 在未牺牲业务价值的前提下大幅消除了安全合规风险。这套架构使得全公司员工都能轻松在云端部署属于自己的专属 Agent，并通过多种非 CLI 交互渠道进行协作。

在现场问答环节中，演讲者进一步阐述了系统的技术细节与未来演进：
1. **本地私有化大模型的前景**：从长期来看，出于成本控制与版本稳定性考虑，自托管的开源大模型是企业最终的演进方向。公有云前沿大模型频繁迭代常伴随不可预测的性能退化，自建私有模型能提供更确定性的推理表现。
2. **身份鉴权与防伪机制**：追踪头本身虽可被注入，但底层 RPC 入口与服务网格具备严格的调用者身份验证体系，二者结合确保了调用链路既真实不可伪造，又能完整溯源。
3. **基于会话行为数据的持续调优**：员工的 Agent 会话与行为数据在严格保障数据隐私与隔离的前提下被系统收集，用于分析真实使用习惯，并动态下发更符合实际工作流的配置与技能扩展。
4. **全员 Agent 孵化与企业级推广标准**：借助成熟的 Agent 开发框架与 Kubernetes 租户基建，全员均可敏捷构建原型；而当某个团队的 Agent 需要提升为全公司通用的企业级工具时，则遵循标准软件生命周期的治理流程，涵盖长期运维支持与合规安全审查。

<details>
<summary>Original English Source</summary>

So, the conclusions from this conversation. Basically, make sure you keep your agents on a leash, okay? After all, letting them run around unsupervised is very dangerous. We want to keep them on a leash. It's much safer that way. And actually, if we go back to that opening slide about how we evaluate this in terms of risk and expected return, because of some of the things we discovered as we worked, we believe we haven't lost any expected value by significantly reducing the risk. True? So the index is definitely lagging behind, but we get a lot more observational power just by using this tagging primitive instead of just checking for identity. And I think that's something that people should really think about, especially those who work in companies and enterprises, because there are a lot of things happening in the generative AI environment that probably scare us, make your security teams afraid, and seem like they're going too far, right? You say, "I wouldn't run this locally." "I wouldn't run an open cloud agent on my local computer with full permissions, right?" "There are so many horror stories and various anecdotes about why that's bad." But within the enterprise, you can again figure out how to leverage corporate resources to really mitigate these risk factors and get real value from these opportunities, and that's where you should invest your time.

So, we finally released this whole system, right? We have the ability to run cloud agents as user identities because of all those safeguards and vectors that we've implemented, and we also use different interface vectors to work with them so that people who aren't used to the command line interface can use them. As part of this, we deployed a managed fleet of cloud agents to each user remotely so they could interact with them, and we continued to roll out and improve what was available to everyone, including the ability for anyone in the company to deploy an agent in the cloud under their own account. So, in conclusion, everything I talked about happened last year. So if you're curious to know what we're working on now, or better yet, if you're thinking, "That was awful. We could do much better." We are hiring and encourage you to apply if you have experience in any of these areas. You can scan the QR code or follow this link. Yes. That's all. Are there any questions?

What do you think about local LLMs connected to agents for enterprises?
Well, not if you use them in my company, but personally I think it is. Yes, sorry. His question was about how I feel about local LLMs for corporate use? I think local models that we run ourselves are probably where we want to get to eventually for most of our token and withdrawal needs. Because of the cost, because of obsolescence, because every time Frontier Lab releases a new model, you notice some degradation. There's just too much instability that we don't want to risk as open-scale models become more and more sophisticated.

Yes, so you see that the headline itself is not a purely differentiating factor. Someone could fill it in, of course, but the identity of the subject wouldn't be mine, right? So someone could, I suppose, write that they're using some kind of agent, but the underlying prior identity isn't fake or interceptable, right? So we still have both the initial identity and, you know, all your ecosystems and chains of identity that guarantee that, but also the header. Yes, this is a separate thing. The header is just an XSL agent, and you still need some way to actually determine the identity of the caller.
I have a problem with this.
Yeah, I, you know, generally all of our RPCs to some extent have an initial entry point that can be filled with this header, and then once it goes off the chain, it makes sure that the same thing with the trace IDs is part of the range within the system.

Can you clarify how using Google's cached index solves the query injection problem?
Yes, the key feature of this index is that it is not just a cached index, it has many other controls and security safeguards around it. It is specifically designed for such curated financial and highly regulated industries. So they do some of their own curation on top of it. Of course, I believe that this curation could backfire. This is probably done using generative AI. But the risk of query injection is significantly reduced because everything remains internal. Yes.

How do you get this behavioral data for these agents, and what sources are you considering for collecting it? Do you mean how they are used?
It's behavioral data.
Yes, I think it's critically important, in the sense that this behavioral data is what we can further tune the system based on, right? We try to ensure that not everyone in the firm can see what your agents are doing, right? There are work moments there, but also more confidential information that may be privileged for you. So your session data is kind of localized. Now, this behavioral data in session data is very powerful because it can identify additional configurations that can be applied to these agents to improve the user experience. We try to use this to determine what to tweak next, not just based on someone's hierarchical role, but actually based on their usage, to ensure that their experience continues to improve based on what they do. Oh, I'm almost out of time. Me and my...Excuse me. I will answer the last question.

Yes. I just wanted to ask, you say you have a process that allows individuals to create their own agents.
Yes.
Um, what I mean is, how do you implement this so that anyone can create their own agents? Is there, is there a process for granting access to certain individuals? And is there any process for leveling up agents for use across the entire company, not just by individual teams?
Yes. To create our own AI agents, we use certain existing frameworks for agent development. Of course, all of our generative AI tools work great with these agent frameworks. So thanks to this, the number of agents is constantly growing. As for the provision, everything is ready. Each user in the company has all the necessary infrastructure. So it's not a big problem. They can create an agent and deploy it in their namespace under their own account. And the question of how agents become universal—for the entire company, not just for individual users—is solved by standard mechanisms, right? That is, will the product be properly supported? Are there appropriate safety measures? It's just like with any other application you develop. Well, my colleagues and I will stay here in case anyone wants to talk in more detail. I guess if you stay, I can answer additional questions, but thank you for coming to the presentation.

</details>