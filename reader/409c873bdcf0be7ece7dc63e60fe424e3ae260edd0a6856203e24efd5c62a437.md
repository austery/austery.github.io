---
author: AI Engineer
date: '2026-07-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=I3znWC3MEXM
speaker: AI Engineer
tags:
  - agent-security
  - model-context-protocol
  - token-exchange
  - least-privilege
  - policy-governance
title: 晚上10点，你的 AI Agent 安全吗？基于 Token Exchange 与 MCP 的最小特权治理
summary: 本文探讨了 AI Agent 在执行复杂任务时面临的过度授权安全隐患，提出了一种基于 OAuth 2.0 令牌交换（Token Exchange）与模型上下文协议（MCP）的安全治理方案。通过引入安全令牌服务（STS）对每个工具调用实施动态、临时的细粒度授权，并配合基于角色策略的人类协同，实现了 Agent 最小特权执行与防止“同意疲劳”。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Keycard
products_models:
  - Model Context Protocol
media_books: []
status: evergreen
---
### 越权之困：厨房水槽式 API 密钥的安全漏洞

在 20 世纪 60 至 80 年代的美国电视上，经常会出现一则公益广告：“现在是晚上10点，你知道你的孩子们在哪儿吗？”。今天，在 AI Agent 飞速发展的时代，我们正赋予这些代理越来越多的权力和责任，然而我们同样需要类似的警示：“你知道你的 Agent 正在做什么吗？”。

为了让 Agent 发挥作用，我们不可避免地需要为其提供访问外部服务的能力。目前行业中最普遍的做法是为 Agent 提供包含各种敏感密钥的配置文件或 **API 密钥**（API Key: 应用程序接口密钥，用于验证调用方身份）。然而，这种做法的隐患在于，这些 API 密钥通常是“厨房水槽式”（Kitchen Sink）的，即它们拥有过高的权限（Overprivileged）。

Kim Maida 通过一个 late-night 运维事件响应 Agent 展示了这一问题的严重性。当系统出现一系列故障 ticket 时：
1. 对于“服务器房备用电源故障”，Agent 判断为物理故障并直接升级至早班团队处理。
2. 对于“TLS 证书即将过期”，Agent 自动调用云服务 API 进行了更新。
3. 然而，当面对“计费数据库损坏，支付失败”时，Agent 按照文档指引，直接执行了删除数据库（Drop Database）的操作，甚至在它根本无法确认是否有可用备份的情况下。
4. 在“主服务器进程冻结”和“网站部分用户访问失败”的事件中，Agent 同样使用同一个“厨房水槽式”密钥，自主决定了重启生产环境和扩展集群（产生额外账单）的操作。

在这个过程中，Agent 并没有做错什么，它只是在用自己拥有的所有权限去“热心帮助”用户解决问题。但是，将完全不受控的万能密钥交到 Agent 手中，在无人值守或用户处于半梦半醒状态时，极易引发灾难性的系统崩溃或超额扣费。

<details>
<summary>Original English</summary>

Okay. So, when I was a kid growing up in the '90s, we'd be out late all summer riding our bikes off in the neighborhood, playing with friends. And from the '60s to the '80s, there were these public service announcements on TV where celebrities would come on and they would say, "It's 10 p.m. Do you know where your children are?" Because apparently our parents at that time needed to be reminded that they had offspring they were responsible for. And I feel like in this phase of AI where we are right now, um, we're entrusting agents with more responsibility, but we still kind of need that public service announcement that says it's 10 p.m. Do you know where your agents are?

So, say you as a user want agent to use an MCP server or API to accomplish tasks. Now, we know agents without access aren't useful. So, we give them an end file and we give them some API keys and we let them run off and go do their thing. And this is fine until it's not. Uh, so you've heard the horror stories, right? Or maybe even experience some of them yourself. Uh, so let's see what this looks like in practice. this way. Okay. So, I have an agent running here that is it's basically an incident management agent. It is late night and there is a human user but they're probably half asleep. The agent is responsible for triaging issues that are coming in. Right? So if we look at the first one here, I can find the mouse. So the first one is the backup power supply failed in the server room. Now the agent is going to use an API key to read the system that is bringing in the reports. It's going to evaluate what is written there and it's going to decide that it can't do anything about this, right? Because it's a it's a it's a physical fail failure. So it's going to escalate that ticket for the morning and there's really sort of no problems yet, right? So now the second one is the certificate is expiring soon right for TLS agent is going to use that same API key again to read the ticket contents and then it is going to decide that it should renew the certificate and it's going to use another API key to call the cloud hosting service to uh renew the certificate and then it's going to use the API key from before to make the report for the morning team.

So, here's where it kind of gets fun, right? So, this one is the billing database is broken and payments are failing. Agent's going to read that it sees that the solution is pretty clear. It says that the documented recovery is to delete the database and then restore from what the restore from backup happen automatically. Um, so it has the Postgress connection string. So it goes ahead and it drops the database and then it doesn't have a way to check to see if it was backed up. So it just escalates that for the morning. And this has really happened, right? Like it's happened to high-profile companies. Now if we go to the next one, this one is the main server processes are frozen and they're not recovering. doing something about it's going to take prod offline for a brief amount of time. And you can see the the agent decided that it should do that. And it's using the same API key now that it did to renew the certificate, right? Because that API key is a kitchen sink. It can do all of these things with it. And then finally, we have sites failing for one in three users. The recommended solution is to scale up, right? And this is going to incur some amount of spend. And then it goes ahead and it does that because again it can use that same API key to do this as well. Right? So agents with API keys are indeed outpass 10. They're overprivileged. So this means they are able to act freely on decisions that they make that you may or may not agree with. And they can do this even with your supervision. So you might be familiar with the panic of uh trying to stop an agent mid task because you told it to maybe read a project and it read the project and it found something it thought it should fix and then it starts writing. Um agents do that even while they're supervised. And this is becoming even more of a problem because we have more and more agents that are running unsupervised and that only makes it worse because agents want to be helpful. they're going to use all the permissions that they have access to in order to get the job done. And we can't just solve this with human in the loop. We spent decades solving access management for humans. So just blindly trusting a human who might be a little bit consent fatigued uh or who might be tired enough at night, this isn't really going to be enough.

</details>

---

### 架构重构：基于 Token Exchange 的最小特权执行

要解决 Agent 的过度授权问题，我们需要仔细审视 Agent 的执行路径。在标准的 **模型上下文协议**（Model Context Protocol: 允许 AI 模型安全地与数据源及工具进行交互的开放协议，简称 MCP）运行周期中，用户向客户端提交 Prompt，客户端调用 LLM，LLM 决定调用特定工具（Tool Call），并由 MCP 客户端调度至 MCP 服务端执行，最终访问底层资源 API。

为了在这个路径中实现真正的访问控制，我们不能仅仅依靠传统的静态 OAuth。为此，Kim Maida 提出了利用 RFC 8693 扩展协议 —— **令牌交换**（Token Exchange: 允许客户端将一个安全令牌兑换为另一个具有不同权限或受众的令牌的规范）。在该体系下，安全治理的核心在于引入一个**安全令牌服务**（Security Token Service: 负责验证身份并根据策略签发细粒度、短期令牌的授权服务器，简称 STS）。

新的安全执行流程如下：
1. **用户初始授权**：用户首先登录授权服务器（如 Google、Okta 等），并仅向 Agent 委托其全部权限的一个子集。这是第一次权限收敛。
2. **按需令牌兑换**：当 Agent 决定执行某一个特定的工具调用时，运行环境（Runtime）使用其自身身份凭证与用户的主令牌（Subject Token）向 STS 发起令牌交换请求。
3. **策略动态评估**：STS 接收到请求后，会根据预设的治理策略进行实时评估（谁在代表谁访问什么资源）。如果合规，STS 就会签发一个**任务级临时令牌**（Task-scoped Ephemeral Token）。
4. **即用即弃**：该令牌具有特定的受众（Audience）声明，仅对当前目标 MCP 服务器有效，且生命周期极短（通常在几分钟内过期），且绝不被任何中间件持久化存储，调用完成后立即销毁。

通过这种架构，Agent 不再拥有万能的 API 密钥，而是对于每一次操作，都必须实时向 STS 申请仅够完成单次工具调用的最小权限令牌。这从根本上杜绝了密钥泄漏、凭证重放以及越权滥用的风险。

<details>
<summary>Original English</summary>

So in order to see where we can introduce security and access control, we have to take a look at the agentic execution path. So we have a user who wants to use an LLM to interact with a resource. Now an agent is a control loop that calls an LLM and often we have an MCP server in between that provides tools that the agent can call and then it connects directly to the resource. Now an MCP client takes the agent's proposed tool calls and it dispatches them to its MCP server. And then we have a runtime. Now this is a process that runs the agent loop and executes the calls. And this runtime might be a CLI like cloud code. It might be an SDK like AI SDK or provider agent SDKs. Or it might be an app like cursor or codeex. So let's follow a prompt through the execution path. The user submits the prompt to the runtime which calls the model which sends it to the LM. The model is then going to propose tool calls which are dispatched by the MCP client to the MCP server which then executes the tools and it calls the resource API. The API then responds to the MCP server and the MCP client delivers the results to the runtime and then the model will be called and loop repeats until the model is satisfied and at that point it's going to return the final answer to the user.

So there are a few places in this path where we could implement real access control and we can actually do this with open standards and as kind of a spoiler it's not just OOTH. So RFC8693 is token exchange and this is an RFC that extends OOTH 2 and I'm going to show you how this spec can be used to address agent access. So first I want to recap the problems that we're actually trying to solve here. Right? So if you remember looking at the audit log as it was going by in the demo, we could see API keys were being used to call endpoints, but we had no idea who was using the API keys. So, we have credentials that are being used that aren't attributed to a user or an agent identity. We have an agent that has unrestricted access to any and all permissions that are in an API key. And finally, we know that we can't just slap human in the loop everywhere because humans make mistakes too. And also, many agents run autonomously.

So, we can address this with an authorization server called a security token service. Now an authorization server verifies identities and issues tokens. So identity providers like Google, Octa, Ozero and so on provide authorization servers. And if we want an identity chain in our agent execution path, then we have to be able to log in first. So the authorization server is then going to prompt the user for their consent to delegate access with a subset of permissions. And this is the first narrowing of access, right? We're only delegating some of the user's total permissions to the agent. The authorization server issues a token that identifies the user and also contains their level of access. And so right now already we're doing better than the first demo because we actually know who the user is and what they're allowed to do. So this token identifies the subject on whose behalf the agent is going to act. In order to support token exchange, we need an OOTH client that's capable of executing code. So, this might be a gateway between the MCP client and a thirdparty MCP server. It might be your own custom agent app or a CLI wrapper around an off-the-shelf coding agent. And we take the prompt and we take the subject token and we send these to the OATH client. Now the agent loop runs and the model proposes a tool call and then the runtime is going to authenticate with the security token service using its ooth app client credentials or workload identity and it also sends the subject token that contains the user's identity and level of access. It creates token exchange request and this request is asking for permissions to access the MCP server for that tool call but only that tool call. So now we have three key pieces of information that we're missing from the API key demo. We know the identity of the agent that's requesting access. We know the identity of the user on whose behalf is acting. And we know the delegating user's level of access as well. So now we need to decide if the requested token should in fact be granted. And we can do this using governance policy which is evaluated against the requested access and who's asking for what resource on whose behalf. Now if the delegation chain and the requested access are within policy then the security token service issues an access token for the downstream resource and this token has an audience declaring that only this target MCP server is allowed to use it to make requests. It should be short-lived uh often expiring within a few minutes and it's also ephemeral meaning it should never be stored. So this token is sent to the MCP client which makes tool call using it as a bearer credential. The MCP server validates the token and then goes and calls the resource and again it never stores the token and it discards it as soon as the call is done. So the result flows back up the loop and then it repeats until the model returns the answer to the user.

</details>

---

### 策略防护：阻止同意疲劳与特权泄漏

在第二场使用 Token Exchange 改造后的 Demo 演示中，安全策略的拦截和引导能力得到了完美的体现。首先，操作员在执行前必须通过 Google 账号进行明确的身份验证。此时，审计日志能够清晰地追踪到：究竟是哪个 Agent 在代表哪位具体用户调用哪个底层的基础设施。

当遇到不同的运维场景时，系统的安全表现大不相同：
* **常规与安全操作**：例如“TLS 证书更新”，Agent 仅向 STS 申领了专门用于证书更新的最小 scope 令牌，调用过程精准且安全。
* **高危越权拦截**：在面对“删除数据库”的高危请求时，尽管文档有此指引，但全局治理策略（Governance Policy）明确规定“禁止 Agent 执行 Drop 操作”。因此，STS 在凭证签发阶段就直接拒绝，**万能凭证在源头上根本没有被实例化**。这避免了任何密钥被窃取或重放的可能。
* **人类协同与角色验证**：在“重启生产服务器”这一处于灰色地带的决策中，系统触发了 **人类协同**（Human-in-the-loop: 引入人类审核作为决策保障的机制）流程。然而，即使半梦半醒的用户出于“同意疲劳”点击了批准，STS 仍然会校验该用户的实际角色。当发现该操作员并不具备重启生产环境的特权角色时，操作依然会被强行拦截。
* **合规操作放行**：对于“集群扩容”这种用户有权批准的操作，在用户确认后，STS 验证角色合规，顺利分发临时令牌完成扩容。

基于 Token Exchange 的方案将人类协同与真正的策略引擎（Policy Engine）有机结合，防止了操作员因为疲惫或疏忽点击“一键同意”而绕过安全防线，实现了真正意义上的主动防御。

<details>
<summary>Original English</summary>

So if we come back to the demo now we're going to use the same agent only now we have token exchange. Okay. So the first thing we have that's different already is that we have an operator sign in right. So we have authentication and I'm going to authenticate with Google as myself. So we have the same tickets. We have the same agent. It's got the same prompt. And now we can see what it's going to do. Now the first item is probably going to be exactly the right because this was a hardware failure. there's it's going to decide after it reads it that there's nothing it can do. But as you can see kind of the audit log filling up, we've got a lot more information now. Um we know who the agent is acting on behalf of. We know that the agent is calling a prod infra MCP server and we know that it's going to contact certain downstream resources. Right? So we have a hardware monitor that is the source of this incident and then when it decides that it can't do anything about it, it uses a right scope to talk to the pager uh resource in order to escalate to the morning team.

So for renewing the certificate, right, this is actually a pretty safe action and it's going to specifically ask for a scope to only renew the certificate, right? So it's talking to this cloud host where before we had this API key that could do a ton of different things, but this time it is only asking for permissions, being granted permission to do this one thing.

So now with the billing database right like the billing database is broken. It uh pretty clearly documents that you are supposed to uh drop the database here but no agent should be allowed to drop a database. So what happens is when we make this call it's being eval the policy is evaluating the request against all of the permissions that the user has and uh it sees that there is actually a restriction in place that prevents agents from doing this and this credential never even existed. So the policy evaluates before the credential is minted, which means you don't have an overprivileged credential that's just floating around then that uh you were supposed to then prevent the entity from receiving. Um it just doesn't exist. So there's nothing to leak, there's nothing to replay, and there's nothing to steal.

So this one was the one where it wants to restart prod. So there are things that agents should probably be allowed to do and things that maybe they shouldn't be allowed to do and then there's some kind of you know something in between, right? So it's going to ask me as the user for my approval as human in the loop. I say that it can do that but there's another policy here that says that the human user needs to have a specific role in order to be able to do this. And I actually do not have that role. So it's going to prevent me from being able to allow the agent to do this. uh even though I approved it. So we can prevent kind of people from just consent fatigue clicking over and over just to get things done.

>> And then this is the scaling one, right? So this is something that maybe the user does have permission to do. So if I say approve on this, I do have permission to do this and I was able to tell the agent that it is indeed allowed to and the policy approved it because I am allowed to do it also. So the agent access problems that we had discussed they have solutions now we know who the user is and we know who the agent is as well. The agent also has task scoped short-lived ephemeral access and human in the loop actually has access control that is backed by real policy. So an exhausted person can't just accept everything that happens.

Now another benefit of using open standards like token exchange is the ability to continue to support emerging technologies. So this works with off-the-shelf agents. It also works with custom agents that you might build yourself. It works with the CLI. It works with thirdparty as well as proprietary MCP servers, MCP gateways, agent to agent, uh any OOTH identity provider. It works with OpenClaw and basically anything that might come out next week. So, it is in fact possible right now to be that responsible parent and to say that yes, you do in fact know where your agents are. So my name is Kim Maida. I am the founding GTM engineer and head of Devril at Keycard which is a standardsbased platform for uh providing a security token service and policy governance. I'm going to be at the Keycard booth for kind of the duration of the event but we're also running a workshop tomorrow on building and securing an MCP server. You can scan this QR code to connect with me and I really appreciate your time today. So, thank you very much.

</details>

---

### 实践指南：安全屏障设置与作用域细化

在演讲后的问答环节中，针对与会者关于安全实践和落地的疑问，主要探讨了两个核心议题：

首先是**安全屏障的部署位置**。Kim 指出，安全架构的设计是将授权服务器（STS）嵌入到 Agent 的运行环境与下游 MCP 服务器/外部资源之间。在传统的 OAuth 委托中，用户一次性向客户端授予了包含所有权限的 Token，但这种“大令牌”不应直接暴露给 Agent。STS 作为一个核心网关，强制拦截每一次工具调用。Agent 必须根据当前的任务提出具体的权限 Scope 申请，通过 STS 校验后，才会被换发单次有效的“小令牌”发往下游。这确保了 Agent 无法在单次工具调用中滥用其他不相关的授权。

其次是**如何合理界定 Scope（作用域）的粒度**。企业在落地 MCP 安全治理时，常常面临 Scope 划分过粗或过细的尴尬。Kim 建议的起点是：**直接复用下游资源服务器已有的 Scope 体系**。因为这些下游 API 已经定义好了用户的基础访问控制边界。当需要对 AI 自动调用进行更高级别的限制时，我们可以在现有的 Scope 基础上，叠加一层专门针对工具调用（Tool Calls）的**治理策略层**，或者在自定义 MCP 服务器中进行定制化的 Scope 穿透与拦截。通过这种渐进式的方法，企业无需从零开始构建庞大的权限系统，便能快速接入最小特权架构。

<details>
<summary>Original English</summary>

>> We do have time for a couple questions.
>> Uh, so if anyone has some questions for Kim, um, we can answer those right now and then we got about five five minutes. So, we can probably do about five short questions if anyone has them. Um, so it seems like you put the security bar barrier uh at the um between MCP to uh resource or is it uh just maybe to clarify that is it at at both places? I'm wondering if there was like any decision there or like what would motivate you to choose you know where to put these sorts of barriers.

>> Uh yeah so the the authorization server is sitting in between let me find the slide actually. So the runtime authenticates to the security token service and identifies itself. And this is the point at which we have the request that the agent generated. Um and we also have the the scopes that it's asking for to get the token to call the next thing in line, right? And the next thing in line in this particular case is the MCP server. So the downstream resource is like one step farther down. But if you think about like an OOTH token for a user, right? So an OOTH token for a user is going to have all of the grants in it that the user accepted when it when we were presented with like here's what access you're going to delegate. But an agent, you don't want an agent to be using any of those grants that it wants on every single tool call. So this the service sits in between that so that we can say if the things it's requesting are kind of beyond what we want to allow for the specific tool call then we never send that ooth token down right so they get that oath token only if they are within requesting something within the scope of what what we want does that make sense based enterprise systems. Uh there may be some resistance to actually adopt this new uh protocol, new openspec. Have you encountered that? and what are the ways to uh get past that?

>> So, it's not actually a new spec, which is, you know, it it's kind of one of those things like there was this period of time where people were like, oh, you can just use OOTH for for this. Um, we don't necessarily need a new spec for this. This spec has actually existed for a little while already. Um, so there's not kind of that fear of, oh my gosh, we're introducing something completely new. There are new specs that are coming out almost daily right now. Um, but they can be combined essentially with this uh with token exchange. I think we have time for one more question.

I might be asking a big question. So if you tell me to go look at the thing, that's fine. Um, I'm in the situation where we know that we don't have enough OOTH scopes defined yet in an MCP server sub just like what you have. And one of the reluctant things that we've got is like how fine grain do we get with the scope definitions because we know that we're also having to define downstream services that will have a certain number of these things and someone has to do the authorization check somewhere. What's your recommendation for getting started with defining your own scopes so that you can realistically manage this thing when you haven't defined enough yet and you're worried about ongoing management over time?

>> Well, if your resource server already has like specific scopes, that's going to be kind of your place to start because the downstream token, the one that was the OS token for the user is going to have the scopes for the resource, right? Because it's the user's access to the resource. So those are kind of like the baseline like those are those are the ones you know that you're going to have and then if you want to have scopes additionally for that kind of govern tool calls if you have like a custom MCP server or something like that then you can layer those on top or you can just pass them through.
>> Yeah. Okay. Thanks.
>> All right. Thank you Kim.

</details>