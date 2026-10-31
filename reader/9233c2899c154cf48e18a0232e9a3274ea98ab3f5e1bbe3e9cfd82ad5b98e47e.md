---
author: AI Engineer
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=58ulJViGFgU
speaker: AI Engineer
tags:
  - agent-security
  - authentication
  - authorization
  - api-gateway
  - mcp
title: 谁在发起请求？AI Agent 身份认证与授权基础
summary: Keycard 的 Kamil 剖析了 AI Agent 与 MCP 服务通信中的认证与授权挑战。由于 Agent 具备非确定性推理能力且易遭利用，传统静态 Token 和过度授权的 Service Account 存在失控与归因难题。演讲探讨了动态凭证、OAuth、SDK 的局限性以及基于网关隔离凭证的架构方案与权衡。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Keycard
products_models: []
media_books: []
status: evergreen
---
### Agent 认证与授权背景介绍

>> 大家好。我叫 Kamil，在 Key Card 的产品团队工作。今天我将和大家聊聊关于 Agent 的认证与授权需求。我们大概只有 18 分钟左右的时间，这根本不足以全面覆盖这个话题。所以，我今天的目标是给大家提供一个高维度的概览，说明做好这件事需要什么、如何解决这些问题，并为大家提供背景信息，欢迎大家到我们位于楼下的展位进一步交流。所以，无论大家有什么问题，都可以在结束后叫住我，或者去找 Peter，他掌握了所有的答案。
<details>
<summary>Original English</summary>
>> Uh hi everybody. My name is Kamil. I work at Key Card in a product team. I'll be talking to you today about agent authentication authorization requirements. We have around 18 minutes ish. That's nowhere close to be able to cover this topic. So, my goal today is to give you kind of high-level overview of what's required to do this, how to kind of solve these problems, and give you context to come and ask us questions at the booth. We downstairs. So, just whatever questions you have, feel free to grab me at the end or go find Peter. He has all the answers.
</details>

我们先从这张相当简单的图表开始。在关于 Agent 以及它们如何与 MCP Server 及其他 Agent 通信的各种演讲中，大家可能对这类图都很熟悉了。但是，人们通常很少讨论的是：这些 Agent 和用户之间究竟是如何相互通信的？它们又是如何进行授权并发起请求的？
<details>
<summary>Original English</summary>
We're going to start with this fairly simple diagram. You're probably familiar with this in any of the talks you have about agents and how they communicate with MCP servers and other agents around. But, what usually people don't talk about is how are these agents and users communicate with each other, how do they authorize and make requests.
</details>

### 当前凭证传递机制与潜在风险

我们经常碰到且常见的情况是，用户会获取某种访问凭证。它们可能被称为个人访问令牌（PAT）或者仅仅是普通令牌。它们代表了一种不透明的凭证，用于标识这些用户，并让 Agent 决定是否执行某项操作。如果你的 Agent 是在本地运行的，有时这个步骤就被直接略过了，之后也没有其他处理。
<details>
<summary>Original English</summary>
So, what we come across and what we see often is that users obtain some sort of access credential. They they might be called personal access tokens or just tokens. And they kind of represent opaque credential identifying these users and letting the agent decide if they're going to perform this action or not. If your agent is running locally, sometimes this step is skipped and nothing else happens.
</details>

当请求到达 Agent 时，它们自身甚至也需要凭证来执行操作，对吧？比如它们普遍需要一个 API Key 来与模型提供商通信，从而让它们具备推理能力。因此，每当大语言模型决定执行某些操作时，它们通常会调用工具。而当我们需要进行这些工具调用时，通常会使用远端的 MCP Server 来执行。为了与这些服务通信，我们理论上也需要另一套凭证。
<details>
<summary>Original English</summary>
When a request comes to the agents, they need to credentials of their own to even perform the actions, right? Like the common thing that they need is an API key to talk to the model provider that allows them to kind of do the reasoning. So, whenever the kind of LLM model decides to do some actions, they often call tools. When we need to do those tool calls, often we use remote MCP servers to perform them. And in order to communicate with them, hopefully, we need another credentials to do that.
</details>

在业界我们看到过几种方案。有时 Agent 会直接使用 Alice 的或用户的 PAT 令牌并原样透传；有时它们会拥有自己的静态密钥；幸运的是，我们看到越来越多的地方在采用各种动态凭证机制。但无论何时，当 MCP Server 收到该令牌时，它们通常只会将用户视作与其交互的主体身份。因此 MCP Server 并不知道到底是一个 Agent 在运行它，还是 Alice 的命令行工具（CLI），抑或是其他工具在调用它。
<details>
<summary>Original English</summary>
And we have couple of options that we've seen in the industry. Sometimes the agents will just use Alice's or like users PAT tokens and pass them through. Sometimes they will have their own static keys and luckily enough uh uh we see more and more use of all of kind of dynamic credentialing that happens there. But whenever MCP server receives that token they usually just kind of see the user as the identity that acts with it. So MCP server doesn't really know if it's like an agent running it, is it like Alice's CLI or is it like any other tool that does it?
</details>

MCP Server 通常被用来封装现有基础设施。如果你有内部 API、数据库，甚至是外部那些对 Agent 并不友好的系统，我们都可以使用 MCP Server 来承接这种通信并优化交互。但为了做到这一点，这些 MCP Server 通常需要访问这些后端服务，并且往往需要代表多个用户操作。因此它们不能只使用单个用户的 Bot 令牌，因为那会受限于该用户的权限范围。它们通常会使用服务账号（Service Accounts），而这些服务账号往往会成为权限的汇聚池，以便这些服务能够进行通信。
<details>
<summary>Original English</summary>
MCP servers are often used to kind of enclose existing infrastructure. So if you have like internal APIs, databases, even external systems that are not kind of agent friendly, we can use MCP servers to represent that communication and optimize that interaction. But in order to do that these MCP servers often need to have access to these back-end services and act kind of act for multiple users. So they cannot just use one user's bot token because that will be limited to that scope. They they often use service accounts and those service accounts kind of become aggregator of permissions so that these servers can communicate.
</details>

### 非确定性与归因困境

这并不是什么新鲜事。我们在过去的传统 SaaS 软件的服务间通信中早就见过这种模式。然而，Agent 有何不同之处？它们不是确定性的软件，对吧？所以每当请求返回给 Agent 并且它看到一些数据时，它会把数据送回给模型，由模型来决定下一步到底要做什么。
<details>
<summary>Original English</summary>
Um And this is nothing new. We've seen this pattern in the past in kind of service-to-service communication in your traditional SaaS software. However, what's what's different about agents? They're not deterministic software, right? So whenever the request comes back to the agent and it sees them some data, it will send it back to the model and it will decide to to do what it wants to do to do with it next.
</details>

在这里我们使用一个抽象的发票服务作为示例。假设 Agent 收到一个去查看近期发票的请求。它收到一张发票，上面写着“待处理，应发送给用户”。此时 Agent 无论是出于恶意，还是仅仅因为太想提供帮助，决定直接把这张发票发送给用户。那么现在问题来了：到底是谁发起的这个请求？是 Alice，还是 Agent？我们不知道。在现实中根本没有任何手段来确定这一点。
<details>
<summary>Original English</summary>
In this case we're using an abstract example of invoicing service. So imagine the agent receives a request to go and look at the recent invoice. It gets it back an invoice says I'm pending, it should be sent to the user. An agent either maliciously or is just too helpful decides to go and send this invoice to a user. Now the question becomes who is making this request? Was this Alice or was this the agent? We don't know. There's nothing to determine that in reality.
</details>

那么这张架构图还有什么问题呢？到处散落着这些凭证会带来大量隐患。每当用户使用这些访问令牌时，它们实际上并没有与任何实体做明确绑定。Alice 可以轻而易举地拿走这个令牌并放到她自己的个人电脑上，这样你就会失去所有原本可以防止滥用的企业级基础设施防护。而且也没有简便的方法来吊销这些凭证，因此它们就散落在那里，随时可能被滥用。随着 Agent 想要执行更多操作，我们会给它们更多凭证，它们开始汇聚越来越多的凭证。再次强调，由于它们是非确定性的，我们根本不知道它们会拿这些访问密钥去做什么。最后，我们又回到了服务账号的老问题上：它们同样只是过度授权的权限集合体。而在 Agent 出现之前，业界对于这种现状是默许接受的，因为我们某种程度上依赖于软件能以安全的方式发布，认为这是由开发者把关的事，所以我们承担了这种风险。
<details>
<summary>Original English</summary>
Um So what else is wrong with this picture? Um there's a lot of issues with having all of these credentials laying around. So whenever users use these access tokens, they're not really attributed to anything. So Alice can quite easily take this uh token and put it on her own personal machine uh and then you kind of lose all of that uh corporate infrastructure that might protect it from abuse. Um there is no easy way to revoke these credentials, so they kind of lay there and can be abused. Um agents as uh they want to do more things, we give them more credentials and they start aggregating them. And again, because they kind of non-deterministic, we don't really know what they're going to do with those access keys. And finally, we arrive at the old problem of service accounts. Again, they're just over-privileged bucket of permissions um and uh re- reality is like we've been okay with the status quo uh in the industry before agents because we kind of relied on the software being released in a secure way. We thought about it as something that developers take care of. So, we kind of accepted the risk.
</details>

Agent 改变了这一切，因为现在我们生活在一个有另一个独立主体可以代表你采取行动的世界里。我经常用这个类比——几乎在我工作过的每家公司，我们都会做这样一件事：在办公室走动时，如果看到有同事没锁电脑屏幕，我们就会跑到 Slack 上以他的名义发一条：“我今天请大家吃甜甜圈”。在当时我们就知道这样做是不对的，所以大家玩这个游戏，把电脑锁上，以后就不会再犯了。但是 Agent 基本上一直在做这种事。我们任由它们拿着我们的凭据横冲直撞，而且一直都在这么干。
<details>
<summary>Original English</summary>
Agent changed all of that because now we live in a world where there is this other actor that can behave on behalf of you. I always use this analogy uh like in almost every company I worked at, uh we have this thing when we would walk around and see if one of your colleagues left the laptop unlocked and we would go to the Slack and be like, "I'm buying donuts for everybody today." And back then we knew that that is not a good thing. So, that we we played this game. We would lock the machine down uh and then we would never do it again. But agents are basically doing this all the time. We just let them run rampant with our credentials and do this all the time.
</details>

### 理想的认证与授权架构要求

因此，我们需要一个更好的解决方案来处理这个问题。有趣的是，解决其中某些问题的技术已经存在很多很多年了，我们之前只是没有动力去花时间好好实现它。所以，与其让 Alice 到处去琢磨该从哪里获取访问令牌——这种用户体验也很糟糕，你可能会想：“为什么我非得自己去拉取这些凭证？”——我们为什么不能让 Agent 能够声明如何获取对其的访问权限，并在客户端中集成向外部系统请求授权的能力？然后，我们就可以签发这种动态凭据：它的范围严格限定在该次具体交互中，仅限于使用它的那个工具，并且一旦交互结束就立即失效。OAuth 这项技术恰好允许我们做到这一点。
<details>
<summary>Original English</summary>
So, um we need a better solution to do this. And uh funnily enough, technology to solve some of these problems existed for many, many years. We just didn't have incentive to kind of um spend time how to implement this properly. Um so, instead of Alice uh going trying to figure out where to get access tokens, uh which is also terrible user experience. You can kind of think like, "Why why do I need to go and fetch these credentials?" Um why wouldn't we have agents um that basically can advertise how to get access to them and then embed into the client's ability to go and request that authorization from some external system. And then we can issue this kind of dynamic uh credentials that are scoped to that specific interactions, that limited to the tool that was using it. Uh and whenever it's done, it's finished. And OAuth as a technology allows us to do this.
</details>

仔细想想，我们在很久以前就已经解决了针对用户的认证问题，但对于软件，我们此前却认为这并非强制要求。但我们必须改变这种现状，并且必须利用手头现有的技术，强制 Agent 在我们为其签发任何凭证之前先完成自身身份认证。因此，我们可以使用类似工作负载身份联合（Workload Identity Federation）的技术。还有其他机制，比如可以使用私钥认证、证书，或者基于 URL 的授权。具体采用哪种机制并不重要，只要你使用了它，并强制 Agent 向系统进行认证即可。有趣的是，一旦你做到了这一点，就可以不断复用相同的模式。与其给这些 Agent 分配服务账号并在其中追加持久的权限，为什么不让它们在每次需要与远程服务器通信时，动态确定需要什么授权，再去远程服务获取令牌并继续执行呢？
<details>
<summary>Original English</summary>
Um and when you think about this, um we kind of solved authentication for users um a long time ago, but then for software, we decided that that's not really a requirement. Um but we need to change this and we need to also use technologies that we have available to us to make agents authenticate before we issue them any credentials. So, we can use things like workload identity federation. There's other mechanism, you can use private key authentication, you can use certificates, you can you can use URL based authorization. The mechanism doesn't really matter as long as you use it and make agents authenticate to the systems. And funnily enough, once you do that, then you can just kind of repeat the same pattern. Instead of giving these agents kind of service accounts and adding like persistent permissions to the service accounts, why don't they just every single time they want to talk to some remote server kind of determine what authorization is required, go to this remote service, obtain the token, and go forth. And [snorts]
</details>

正如我所提到的，Agent 与传统软件唯一的区别就在于那个推理循环。如果你把推理循环拿掉，无论是遗留软件还是 Agent，本质上都只是软件而已。因此，你完全可以在当前编写的应用程序中复用相同的模式，一切都没有改变，你可以通过这种方式去重构整个技术栈。这听起来很简单，那为什么我们之前没有这么做呢？
<details>
<summary>Original English</summary>
um the only difference between agents and traditional software that we have that I mentioned is that reasoning loop. If you take that out of equation, both the legacy software and agent is just software. So, again, you can just reuse the same pattern for the application that you're writing now, and nothing changes, and you can kind of go and re-implement the entire stack this way. So, that sounds easy. So, why we didn't do this before?
</details>

### 大规模落地面临的复杂性与核心需求

当我们在大规模场景下思考这个问题时，所有这些事情都会变得极其棘手。我们面对的不是单个 API，而是成百上千个 API，而且它们认证用户的方式各不相同。在这些 API 背后，总是有某种授权服务器需要对用户进行认证。在之前的简图中，我们只需要针对一个模块进行授权；而现在，客户端必须跨越数百个这类服务来完成这套流程。而且 Agent 的类型也并非单一，我们会有采购的 Agent（例如你的 Cloud Code），也会有自己构建的 Agent。有时候你无法修改那些软件，所以我们必须找到在这种情况下该如何落地的途径。此外，调用链条也不是单跳的，现在我们需要处理这种委托流（delegation flow），验证所有这些 Agent 如何与其他 Agent 相互通信，以及该循环中可能存在多少层跳转。最后，我们面临的最大问题在于归因：到底是谁决定采取了这项操作？现在我们有成千上万的用户需要对 Agent 所执行的这些任意操作进行授权同意。因此在规模化场景下，我们必须把所有这些问题合并在一起解决，才能为我们打造出真正有用的系统。
<details>
<summary>Original English</summary>
Well, all of this kind of becomes way way way tricky to do when we think about this problem at scale. There isn't like one API that we have, there's like hundreds of APIs that we have, and they use different ways to authenticate users. Behind those APIs, there's always some sort of authorization server that needs to authenticate the user. So, in a previous picture we had we had like one block that we would have to authorize against. Now you have clients who need to do this across like hundreds of these services. And there isn't like one agent type. We're going to have like uh agents that you buy, so your cloud code, agent that you build. Sometimes you won't be able to like change that software, so we need to find a way to how we're going to do this. And and there isn't like one hop. So, now we need to process this kind of delegation flow and verify how all these agents going to talk to other agents and how many hops there can be in that loop. And finally, like the biggest problem that we have is the attribution of like who decided to make this action. So, we now have like thousands of users who need to consent to these arbitrary actions that agents are doing. So, at scale, now we have to solve all of these problems all together in order to make something useful um for us.
</details>

总的来说，如果我们想要一套完备的 Agent 认证系统，需要提供什么？
- 首先，我们需要 **Agent 身份标识**。我们需要一个能够为每个 Agent 颁发这些身份的系统，甚至可能是按每个会话（Session）颁发，但它必须与启动该 Agent 的人分离开来。
- 其次，我们需要能够表达这种**委托语义**。也就是说，我们必须能够说明哪些用户有权使用这些 Agent 执行操作，哪些 Agent 可以代表其他用户行动。我们需要一个能够为我们所做的每一步操作签发限定范围（scoped）且生命周期短暂（short-lived）的凭据的系统，并且绝对不能存在允许通杀的主密钥（master key）。
- 第二，正如我提到的，我们已经有上百种不同的系统，无法指望凭空魔法般地把它们全重写一遍。大模型速度虽快，但还没那么快。因此，我们必须能够在它们之间建立联合身份信任，并在系统交互时相互信任。而且，我们将永远面对遗留软件，不能指望它们在短期内都能支持 OAuth。因此，我们需要一个自适应层或 Broker，让我们能够安全且即时（just-in-time）地置换那些遗留凭据。
- 最后，你需要能够通过**策略**来表达这一切。必须有人能够编写规则，规定哪些操作需要人工审批，哪些 Agent 可以自动运行。而且系统总会出错，为了让我们能够吸取教训并加以改进，我们必须具备**审计能力**。我们需要能够明确指出是谁批准了该请求，是谁让这一切成为可能的。
<details>
<summary>Original English</summary>
So, in summary, um if we want to have a proper agent authentication system, what do we need to deliver? So, first of all, we need agent identities. We need a system that's going to issue these identities per agent. Uh then that might be even be per session. Um but that must be separate from whoever launched it. Then we need to be able to express this delegation uh semantics. So, we need to be able to say which users are authorized to perform actions with these agents, which agents can act on behalf of other users. We need to have a system that can uh issue scoped and short-lived credentials for everything that we do. Um and there cannot be like any master key that allows us to do this. Um Second, as I mentioned, there's like 100 different systems that we already have. We cannot magically hope we can rewrite them all. LM are fast, but not that fast. Uh so, we need to be able to build a federated trust of identities across them and allow to trust each other when they exchange these systems. And again, we're going to have legacy software forever. Um you won't be able to kind of go and hope that they will be supporting OAuth anytime soon. So, we need to be able to kind of have an adaptive layer, a broker, that allows us to securely exchange those legacy credentials just in time. Um and finally, you need to be able to express this with policies. Um someone needs to be able to write which uh actions need human approval, which agents can run automatically. Um and things will go wrong. So, um in order for us to learn uh how to improve things, we need audit. Um we need to be able to say who authorized this request and who made this possible.
</details>

要真正把这些事情做对，需要经历很多步骤。我在这里想向大家展示的是：哪怕仅仅为了跑通 Agent 和 MCP Server 之间的一次交互，你都会涉及客户端和服务器端。服务器端需要能够发布这些信息，客户端需要能够发现它；随后 Agent 需要能够获取这些凭据，并向该远程服务器证明自身身份；接着当请求发生时，MCP Server 必须能够验证这些凭据是否经过正确签名，需要检查签发方是否可信，并且必须校验这些令牌；随后必须有某种策略生效，强制检查最新的规则是否起作用；一旦通过并需要与外部系统通信时，它们可能还需要获取额外的凭据来进行交互；最后，我们必须确保这些操作中的每一步都被记录在审计日志中。大家举手示意一下，谁认为大语言模型每次都能完美无瑕地搞定这些？好的，看来大家的意见是一致的。
<details>
<summary>Original English</summary>
Um So, um there's a lot of steps to actually get this right. So, um what I want to show you here is just like if you take one interaction between agent and MCP server just to get this working, um you will have a client and a server. Um server needs to be be to publish this information. Cli- clients need to be able to discover it. Then the agents need to be able to obtain these credentials. They need to be able to authenticate themselves to this remote server. Um then when that happens, uh the MCP server has to be able to validate if those credentials been been correctly signed. They need to check if the issue is trusted. They need to verify those tokens. Um then there is some policy that needs to come into action. They need to enforce if the latest rules uh are in play. Um once that happens, and they communicate to external system, uh they might need to obtain additional credentials to talk to it. Uh and finally, we need to make sure that every single one of these actions is captured in the audit log. Um Raise of hands, who thinks LLMs can do this uh every single time perfectly? All right. Uh I think we're all in agreement.
</details>

### SDK 方案的弊端与凭据外置架构

这确实不简单，但我们以前解决过类似的问题，对吧？比如我们编写通用共享库、中间件、SDK，以便一次性写好这些逻辑，在更大范围内验证它们是否按预期工作，并在各处复用。这听起来像是我们这里需要的一种解决方案。
<details>
<summary>Original English</summary>
Um so, this is not simple, but we have solved similar problems before, right? Like we've written shared libraries, we've written middleware, we've written SDKs in order to kind of write these things once, verify with a larger group of people if those performing um appropriately, and kind of reuse them all the time. Um which sounds like a solution to what we want to do here.
</details>

但 SDK 存在哪些问题呢？
1. 如今编写 SDK 很容易，但你需要让所有人都在实践中采纳它们。如果采纳落地存在缺口，那么你的 SDK 又有什么用呢？
2. 你需要针对系统中所使用的每一种语言分别编写 SDK。虽然大模型或许擅长编写其中某些语言，但可能并不擅长系统中的那些老旧语言。
3. 对于那些你无法修改的商业化或闭源工具（比如你的 Cloud Code、Codex），你该怎么办？SDK 在这种场景下帮不上什么忙。
4. 如果出现 Bug——大模型会写出 Bug，人类也会写出 Bug——为了修复它，你不仅要修复 SDK 本身，还要去追踪该 SDK 在哪里被使用过，以及哪些系统引入了它。
5. 上述四个问题是过去一直存在的，并不新鲜。但 Agent 还带来了额外的问题：正如我所说，它们在行动时往往过于乐观，或者可能被诱导去执行某些操作，而且事实证明它们在试图绕过我们的控制措施时非常执着。那么，我们真的能信任仅仅依靠客户端代码来安全管理这些凭据吗？当然，它们可以缓存凭据，也可以正确存储它们，但只要它们意识到存在可用的凭据，并且该凭据就在它们自己的执行环境中，我们就面临着风险。
<details>
<summary>Original English</summary>
Um but what are the problems with SDKs? So, um it's easy to write them these days, but you need to get them adopted by everybody, right? Like if you have gaps in your uh adoption, then well, what's good are your SDKs? Um then you need to write them for every single language that you have. And LLMs are probably good at writing some of these languages, but probably not the older ones that you have in your system. Uh and then what do you do about your cloud codes, your code X that you cannot go and modify, right? Like SDKs won't help you there too much. Um then if you're going to have bugs because a LLMs make bugs, we write bugs. Um in order to fix that, you not only have to fix the SDK, but then you need to track where is this SDK used, and which one of the systems consumed it. Um And then finally, so all of these previous four problems existed before, so that's nothing new. But agents have additional problem. As I said, they kind of act um and trying to be too optimistic, or they can be kind of manipulated do things, and they proved to be very persistent in trying to bypass our controls. So, um do we really trust with using just kind of client-side code to be able to manage these credentials securely? Of course, they can cache them, they can store them properly, but if they figured out that there is credential that they can use, as long as it's within their own kind of execution environment, we have a problem.
</details>

因此，出于诸多原因，SDK 显然无法解决这个问题；更重要的是，它们并没有解决“向 Agent 隐藏凭据”的核心问题。
<details>
<summary>Original English</summary>
So, SDKs clearly are not going to solve this problem for many reasons, and additionally, they don't solve the problem of hiding credentials from agents.
</details>

### 基于网关与运行时授权服务的解决方案及权衡

以这幅架构图为例，我们希望达成的挑战是将所有这些令牌移出 Agent 的触及范围。那么我们可以怎么做？我们可以尝试把所有这些凭据从当前执行环境中剥离出来，放置在某种安全隔离区（secure enclave）内。我们可以建立运行时授权系统和金库服务（vaulting service），用来存储并代理所有这些凭据。
<details>
<summary>Original English</summary>
So, if we take this picture, um the challenge that we want to do is to get all of these tokens out of the reach of the agent. So, what can we do? Well, let's try to move all of these credentials out of this execution environment and put them in some sort of secure enclave. So, we can have our kind of runtime authorization system, vaulting service, that can store and kind of broker all these credentials.
</details>

接下来的另一个问题是：我们该如何使用它们？网关（Gateways）是我们过去使用过的组件，它们可以帮我们解决这个问题。Agent 可以与网关通信，请求访问特定的目标（例如 GitHub）。网关可以对调用者进行身份认证，与我们的运行时授权服务通信，验证相关策略是否就绪，并拉取特定的凭据。随后，网关直接将凭据注入到请求链路中，并转发给 GitHub。
<details>
<summary>Original English</summary>
And then the other problem is now how are we going to make use of them? So, gateways are something we've used in the past, and they can solve this problem for us. So, agents can communicate to the gateway, can request specific target to talk to GitHub, for example, and a gateway can authenticate who's calling it, talk to our runtime authorization service, validate that policies are in place, and fetch the specific credential. And then they can simply inject them into the request path and send it forward to GitHub.
</details>

这带给我们的好处在于建立了一个物理控制层：Agent 根本没有任何途径获取该凭据，除非它具有强烈的确定性意图去尝试攻击我们的网关，或者去攻击我们的授权服务。
<details>
<summary>Original English</summary>
And what that gives us is now we have like a physical control layer where there's simply no way for this agent to obtain this credential unless it's going to be very deterministic and go try to hack our gateway, or even worse, our authorization service.
</details>

但更重要的是，我们从中获得了更多优良特性：
- **即时吊销（Instantaneous Revocation）**：即使你使用短生命周期的凭据，它们仍会有一定的过期时间，而在分布式系统中我们至今仍未完美解决撤销问题。但如果使用网关并强行让所有通信都经过该节点，你就可以实现即时吊销，因为网关可以在运行时动态检查每一个请求。
- **权限衰减（Attenuation）**：Agent 往往会执行过多操作。很多遗留服务无法做好精细的权限范围控制，它们提供的令牌往往只区分 Admin、读或写权限，但这还不够好。比如我们希望能够做到：“你可以读取我的电子邮件，但不能发送我的电子邮件”。有了网关，因为我们能够拦截并且更重要的是能够内省（introspect）所有的请求，我们就可以对该请求进行衰减。我们可以规定：“对于这个特定请求，是的，可以使用安全凭据；但如果你尝试发起发送请求，我们会直接拦截阻断。”
- **网络可观测性（Observability）**：由于网关位于网络路径上，我们可以精确查看所有请求发生了什么，而且不需要对下游服务做任何更改。
<details>
<summary>Original English</summary>
But what most importantly, we get couple more properties out of this. Even if you use short-lived credentials, they will have some sort of expiry time, right? And we still haven't figured out how to do revocation probably across distributed systems. But if you use gateways and you force all of your communication through that point, you can have instantaneous revocation because gateway can check every single request on the fly. Additionally, agents will do too much. A lot of these legacy services won't be able to scope access properly. They will have tokens that allow you either admin, read, or write permissions, but they're not good enough, right? Like we want to be able to say, "Hey, you can read my email, but you cannot send my email." With the gateways, because we can intercept and more importantly introspect all of the requests, we can attenuate that request. We can say, "For this specific request, yes, there is a secure credential we're going to use, but if you're trying to send request, we're just going to block it." We also get more observability because the gateway is on a network path, we can see exactly what happens for all the requests, and we don't need to change anything in our downstream services.
</details>

天下没有免费的午餐，网关方案也会带来一些挑战：
- **增加网络跳数与延迟**：你在调用链路上增加了一跳，如果对延迟非常敏感，这会带来一定开销。
- **强制流量引导**：你需要强制所有 Agent 都与网关通信。如果没有强有力的网络控制措施，一旦它们能够绕过网关，这套机制就无法生效。
- **本地工具执行不受控**：某些 Agent 倾向于在本地执行工具，网关对此无能为力。
- **未解决身份根源**：网关本身并没有解决身份标识问题。Agent 仍然需要获取某种认证凭据并提交给网关，才能发起经过正确认证的请求。
- **成为集中攻击目标**：你创造的这个组件会成为一个显眼的攻击靶点，因为现在所有凭据都要经过它，自然会有人尝试去攻击它。
- **技术与配置复杂性**：构建网关存在大量技术复杂性，有些人也称其为代理（Proxy），TLS 就是其中一个难点。如果试图拦截并与所有这些系统交互，可能会遇到问题。
- **路由与运维负担**：在分布式系统中，面对大量开发者构建的 Agent，必须有人负责配置所有这些网关中的路由、策略和连接器，必须有人定义 Agent A 是否可以通过网关与 Agent B 通信；并且必须有人去运维它。
<details>
<summary>Original English</summary>
But, there's nothing for free in life. So, gateways also come with some challenges. While you're adding another hop to your call, so if you're really careful about your latencies, that's going to add some to it. Um Well, you need to force all your agents to talk to your gateway. If they can go bypass it if you don't have strong network controls, then that's not going to help you. Additionally, some agents want to have kind of local tool execution, so you're not really guarding against that. There's nothing gateway does about your identity problem. Yes, agents still need to get some sort of authentication credentials and present it to the gateway in order to have a correct authenticated requests. You're also putting a big target on this one thing that you're creating because now what we're saying is like every single credential will go through it. So, well, some people will go try try to hack it for you. There's a lot of technical complexities with building gateways. Some people call them proxies as well. TLS is one of those things. If you try to intercept that and try to work with all of these systems, you might run into some problems. And finally, if you're running distributed system, you have all of these developers building agents, they need to figure it out how they're going to configure the the routes, the policies, the connectors in all of those gateways, right? That still someone has to say if agent A can talk to agent B via the gateway. And two, someone has to run it. Um, so these are all the problems we have with gateways.
</details>

### Keycard 的实践与建议

我们在 Keycard 一直都在思考所有这些问题。我们认为让每个人都去重复构建这些功能是不切实际的。因此，我们构建了统一的控制平面：既能为你的 Agent 提供身份标识，能够签发令牌并与你现有的所有系统进行联合信任；我们为你的所有请求提供策略控制和审计能力；你可以从我们这里获取用于凭证注入与发现的客户端 SDK；我们也提供服务端 SDK，让你无需操心服务端如何进行认证；如果你确实需要强管控，我们也可以提供网关。
<details>
<summary>Original English</summary>
Um, so what we do at Keycard, we think about all of these problems all the time. Um, so we don't think uh it's it's sensible for everybody to replicate all of these functionalities. So, we've built a single control plane um that allows you to both give your agents identities. We issue tokens uh in and federate with everything that you have going on. Um, we provide you policies and audit um to all of your requests. Um, you can get from us all of the client SDKs that allow you to do uh injection and discovery. We provide you with service SDKs that you don't have to worry about how they're being authenticated. Um, we also give you gateway uh if you really want to have those controls, but fundamentally um you can bring all of these components to us um and kind of pick and choose which one of these capabilities you need to build your system because you might be building a chat application. You might be building a complete uh orchestration platform. Um, we are fairly unopinionated on the problem you're trying to solve with agents. We're just trying to help you solve these in a secure fashion.
</details>

从根本上说，你可以把这些组件带到我们这里，根据构建系统所需的具体能力按需挑选，因为你可能只是在构建一个聊天应用，也可能在构建一个完整的编排平台。对于大家用 Agent 解决什么业务问题，我们保持中立，我们只是致力于帮助大家以安全的方式解决这些安全问题。
<details>
<summary>Original English</summary>
Um, so if you take anything out of this talk uh and want to come talk to us, um agent off isn't an option optional anymore. Uh yes, we kind of managed to survive without this for decades, but uh agents proved themselves recently that uh they cannot be trusted. Uh reality is messy. So, even if you go on a mission of trying to build some of these components, uh make sure that you use open standards uh and to be interoperable with other systems because um we're not going to win this game uh by playing uh alone. Uh and then really really don't yellow it uh because LLMs won't be able to implement this for you. Um, and make sure that whatever you do, check if the code written to implement these uh capabilities is secure.
</details>

如果大家能从这次演讲中带走一些思考并想来找我们聊聊：Agent 认证已经不再是一个可选项了。是的，过去几十年我们在没有它的情况下也过来了，但 Agent 最近的表现证明了它们是不可信的。现实是复杂的，所以即使大家打算自行构建其中的部分组件，请务必使用开放标准，确保与其他系统的互操作性，因为单打独斗是无法在这场博弈中获胜的。另外，千万不要草率行事（don't YOLO it），因为大模型无法替你搞定这些实现。无论大家怎么做，请务必检查用于实现这些功能的代码是否安全。
<details>
<summary>Original English</summary>
Um, thank you. Um, if you want to find out about us, come to the booth. We're Keycard AI. Uh also check out agent baseline.org. We have recently uh kind of released uh a software uh factory reference implementation of all of the capabilities that you've seen here. So, you can kind of learn and come and work with us on the how to solve this problems. That's it.
</details>

非常感谢大家。如果想了解我们，欢迎来展位找我们，我们是 Keycard AI。大家也可以去看看 agentbaseline.org，我们最近发布了涵盖此处介绍的所有能力的软件工厂参考实现，大家可以在上面学习，并欢迎来与我们共同探讨如何解决这些问题。就到这里，谢谢大家。

>> [掌声]
<details>
<summary>Original English</summary>
>> [applause]
</details>