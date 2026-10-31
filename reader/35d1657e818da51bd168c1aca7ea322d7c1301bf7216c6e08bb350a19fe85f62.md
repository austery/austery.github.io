---
author: Latent Space
date: '2026-05-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=LzCUYNP5UTI
speaker: Latent Space
tags:
  - cloud-infrastructure
  - ai-agents
  - software-development-lifecycle
  - bare-metal
  - version-control
title: Railway 创始人 Jake Cooper 访谈：AI Agent 时代的“克隆机”云平台与开发范式革命
summary: Railway 创始人 Jake Cooper 深入探讨了在 AI Agent 时代，软件开发如何从“手动编写”转向“审查代码”。他提出 PR 模式正在消亡，未来的核心在于能支持大规模并行 Agent 的基础设施。通过自建裸金属数据中心、深耕内核级优化以及“克隆式”环境管理，Railway 致力于构建一个低摩擦、高确定性的 Agent 原生云环境。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Railway
  - Uber
  - Heroku
  - OpenAI
  - Salesforce
  - Bloomberg
  - Equinix
products_models:
  - Claude
  - PostgreSQL
  - Kubernetes
  - Temporal
  - Docker
  - Nyxpacks
media_books:
  - The Martian
status: evergreen
---
### 核心观点：停止手写代码，转向代码审查

**Jake Cooper**: 如果你现在还在手写代码，那你就做错了。现在的工具已经足够成熟，可以让你行动得极其迅速。虽然还存在一些痛点和问题，但你应该是在**审查**你写的代码，而不是尝试去亲手编写。

<details>
<summary>Original English</summary>

**Jake Cooper**: If you are writing code by hand, you are doing this wrong, right? Like your code, the tools are good enough at this point like that you can move extremely extremely quickly and like yes, there are issues and pain points and all these other things. Um, but you should be reviewing the code that you are writing instead of trying to go and write it by hand.

</details>

**Jake Cooper**: 那些架构模式之类的东西，现在比以往任何时候都更重要。但你不应该把时间花在生成那些你自己本来就会写的代码上。如果你知道怎么写，直接让 **Agent** 去写，然后不断调整，直到它看起来像你亲手写的一样。

<details>
<summary>Original English</summary>

**Jake Cooper**: Like all of those architectural patterns, all of those other things like you're not just don't like you're not going to throw them in the garbage or whatever. Actually, they matter more now than than than any other time. But you just shouldn't spend your time generating code that you would write. Like if you know how to go in and write it, just like ask the agent to go in and write it and then reconcile it until it looks like you would have written it.

</details>

### Railway 的定义与愿景

**Allesio**: 欢迎来到最新的 Space 播客。我是 Allesio，**Kernel Labs** 的创始人。和我在一起的是 **Latent Space** 的编辑 Swix。今天我们邀请到了 **Railway** 的 Jay Cooper。

<details>
<summary>Original English</summary>

**Allesio**: Hey everyone, welcome to the latest space podcast. This is Allesio, founder of Colonel Labs, and I'm joined by Swixs, editor of Len Space. And today we're in the studio with Jay Cooper of Railway,

</details>

**Swix**: 嘿！嘿！

<details>
<summary>Original English</summary>

**Swix**: Hey. Hey.

</details>

**Jake Cooper**: 我是 Railway 的**列车长** (Conductor)。

<details>
<summary>Original English</summary>

**Jake Cooper**: conductor of railway.

</details>

**Allesio**: 对于那些还不知道的人，Railway 到底是什么？先给个清晰的定义吧。

<details>
<summary>Original English</summary>

**Allesio**: Um okay so well for those who don't know what is railway let's give people a crisp definition up front.

</details>

**Jake Cooper**: Railway 是部署任何东西最简单的方式。你只需要打开画布 (Canvas) 或与 **Claude** 对话，告诉它“部署一个 **PostgreSQL** 实例”或“部署我的 GitHub 仓库”，然后你就可以直接起跑了。

<details>
<summary>Original English</summary>

**Jake Cooper**: Yeah, railway is the easiest way to ship anything. You just go to the canvas or you talk with claude um and you say deploy Postgress instance, deploy my GitHub repository, run this code, etc., right? Um and you'll just be up and away to the races, right?

</details>

**Jake Cooper**: 我们想让应用随着时间不断演进。目前的许多工具就像是在不断堆积熵——先是 **Docker** 和 **Kubernetes**，然后是 **Ansible** 脚本。如果我们能为你管理所有软件的版本并跟踪变更，那么克隆环境、甚至在并行宇宙中进行分叉 (Fork) 都会变得微不足道。你可以获取生产数据的副本，验证更改，然后合并，而不需要费力重建测试环境。

<details>
<summary>Original English</summary>

**Jake Cooper**: But yeah, we want to make it really easy for not just to like deploy things, but for you to almost like evolve applications over time. Like we believe that most of the tooling right now is kind of like stacked up like you're stacking entropy on top of entropy on top of entropy, right? So you have like Docker and Cube and then like Ansible scripts and all of these other things, right? Um, and if we can kind of like version all of your software for you and keep track of all of the changes, then we can make it actually trivial for you to clone environments, you know, fork into a parallel universe, get copies of like production data, get copies of like any of your services, make those changes, validate those changes, collapse it in, uh, without kind of having to just like reproduce everything across a, you know, a staging environment or all of those other things, right?

</details>

### 从 Uber 到 Railway：追求极致体验

**Allesio**: 我看你的背景，**Bloomberg**、**Uber**，似乎没有哪一点能预示你会创办下一个伟大的 **PaaS** (平台即服务)。是什么让你为此做好了准备？

<details>
<summary>Original English</summary>

**Allesio**: Amazing. Uh, one thing I I was looking at your background, right? like um Bloomberg, Uber, there's nothing immediately that stands out to me as like okay this guy's going to found like the next great platform as a service. Uh what prepared you for real?

</details>

**Jake Cooper**: 这几乎是一种不断深入的好奇心。我从前端开始，后来在 Uber 接触分布式系统，将 Jump 单车系统迁移到基于 **Cadence**（**Temporal** 的前身）的分布式系统上。我一直想要那种“走近单车、解锁、然后顺畅骑行”的**无摩擦体验**。

<details>
<summary>Original English</summary>

**Jake Cooper**: It's almost like a curiosity just like ever go deeper, right? Um and so like you know started out on like front end stuff you know like working on the like wolf from like web mathematic and like porting it over there and then you know briefly moving to Bloomberg um and then moving towards Uber and like distributed systems and kind of like taking all the jump bikes uh kind of systems and and moving them over to a distributed uh system built on top of uh Cadence like uh the yeah the pre-temporal temporal. And so like it's just been a a a continual step of like I I want this experience whether it is like walking up to like a bike and just unlocking it and like having it be like frictionless to like work or whatever and then like necessitating the like depth required to go in and make that happen, right?

</details>

**Jake Cooper**: 我们团队的核心理念是：为了把体验做对，我们不介意潜到游泳池的最深处。我没有物理学博士学位，只是学了电子工程和计算机科学 (EECS)，但我始终在思考如何达到下一步。这就是为什么我们现在甚至开始涉足**裸金属** (Bare Metal) 数据中心。这周我还在给内核打补丁，只是为了让体验更完美。

<details>
<summary>Original English</summary>

**Jake Cooper**: Like it it a lot of the work that that I do and a lot of the team does is like it's all in service of that experience, right? and like we fundamentally don't care like how deep we have to go whatever like we will swim to the bottom of the swimming pool to go and get the experience right um and I think that's what a lot of of you know kind of the trajectory was right and so it's not like I have a physics PhD or whatever I did like an EECS degree you know it it's just it's always been about just trying to figure out that next step of like how do we get there right um and that's like what's led to you know starting railway for that experience and then like moving all the way to bare metal data centers right like you know I was adding patches to the kernel this week Right. Just to like get the experience there cuz I'm like I see it and like how much better it can be. Right.

</details>

### 数据中心的经济学：3 个月回本

**Allesio**: 你提到了新加坡的数据中心，在其他地区也有。建立数据中心是什么感觉？

<details>
<summary>Original English</summary>

**Allesio**: Yeah. You have a data center in Singapore. Singapore, we're adding a second one in Q3. So, Yep. So, so like what's it like? I mean I I' I've never built a data center.

</details>

**Jake Cooper**: 基本上就是去跟 **Equinix** 这样的人说：“我需要电力和一个机柜。”他们会租给你一个机柜，然后你需要往里填满机架、服务器并接入互联网。

<details>
<summary>Original English</summary>

**Jake Cooper**: You basically just go and you say, "Hey, listen. I want uh power and I want a cage." Uh and they're like, "Great. Here this is what it's going to be." Um and then you rent the cage for a period of time and then you have to fill the cage uh with racks servers and then hook up internet to it, right? Um that's realistically.

</details>

**Allesio**: 相比于直接用公有云，这里的数学账是怎么算的？

<details>
<summary>Original English</summary>

**Allesio**: and like what's the math versus obviously the clouds?

</details>

**Jake Cooper**: 如果我们在云端租用资源，相比之下，我们转向裸金属服务器的**投资回收期** (Payback Period) 大约只有 3 个月。这太疯狂了。而且硬件还在升值，因为内存价格涨了。

<details>
<summary>Original English</summary>

**Jake Cooper**: Yeah. Uh it our payback period when we go to to metal um if we rent it in the cloud, our payback period is about 3 months. It goes crazy. It's nuts. Yeah. and and that's like four years worth of like depreciated hardware, right? Um and so I think it's like you're going to see a lot of this almost like compute crunch so to speak because a lot of the hyperscalers are buying up a lot of stuff.

</details>

### AI Agent 对基础设施的渴求

**Jake Cooper**: 很多人看到大型厂商投入数百亿美元进行资本支出，觉得不可思议。但如果你意识到未来每个人都会同时运行几十个甚至几百个 Agent，你就会发现目前的算力缺口有多大。即使效率再高，算力需求也会爆炸。

<details>
<summary>Original English</summary>

**Jake Cooper**: if you go back to every person is going to run you know dozens hundreds whatever of agents in parallel like you should spend more than you have you have like you have no conceptual idea of like how much compute is required to go in and make that experience happen. Even if you're deeply efficient, even if you're sharing resources, even if you're doing all of these other things correctly, and that doesn't even count inference.

</details>

**Allesio**: 你们什么时候开始优先考虑 AI 或 Agent 的开发？

<details>
<summary>Original English</summary>

**Allesio**: Is there any point at which you started prioritizing um AI developments or agent development?

</details>

**Jake Cooper**: 过去六个月里，我们深度优先考虑将 **Agentic**（代理化）作为构建和部署软件的核心机制。我们相信这是一种不可逆转的趋势。人类经历了从汇编到 C，再到 C++、JavaScript，现在正进入“文字”阶段。你必须能够闭合这个环路。

<details>
<summary>Original English</summary>

**Jake Cooper**: Um and probably over the last like six months we've probably deep deeply prioritized like Agentic as a as a mechanism to go and build and and deploy things. uh just because we we believe fundamentally like the the curve is so sheer and like that is the way that people are going to go and build and deploy software. we've moved from assembly to C to C++ to JavaScript to now like words, right? And you're going to need to be able to close that loop, right?

</details>

### PR 的消亡与提示请求的兴起

**Allesio**: 除了开发工具的改变，软件开发生命周期 (SDLC) 还有什么变化？

<details>
<summary>Original English</summary>

**Allesio**: Yeah, the SDLC is changing and it's something that both of us are like super interested in exploring as well. Um, my one of my thesis or it's not my thesis, it's the pull request is dying, right? It's it's going to be the prompt request.

</details>

**Jake Cooper**: 没错，**PR** 正在死去，代码审查也在死去。如果你有完善的系统，你还需要像现在这样审查吗？我们想消除“推送-拉取-重新构建”这种带有摩擦的循环。理想的状态是，你在生产环境中做一个小改动，这个改动会在你的整个基础设施中自动版本化，与数据库的写时复制 (Copy-on-write) 版本协同工作，然后瞬间上线。这就是闭环的“圣杯”。

<details>
<summary>Original English</summary>

**Jake Cooper**: and then beyond that code review is also kind of dying because do you really need to uh if you have all the other systems in place? But that like pushpull rebuild thing, right, is a point of friction that we are like removing entirely from from our loops.

</details>

### 宠物还是牲畜？我们要能克隆的“宠物”

**Allesio**: 关于服务器管理，有个经典的说法是“**牲畜而非宠物**” (Cattle not Pets)。

<details>
<summary>Original English</summary>

**Allesio**: cattle not pets. Right. Because like your prod like it has a name like a baby, you know, I have to keep it alive. But when it's cattle, you can just mass farm and you can like roll out and you can like, you know, uh portion out parts of them and kill them or whatever.

</details>

**Jake Cooper**: 我有个不同的观点：你可以把它们当成“宠物”，只要你有一台**克隆机**。如果你能快照每一帧的状态，那么它是否被毁灭就不再重要，因为你可以随时恢复。我们之前的整个 DevOps 体系都是为了“防爆”，限制任何变更。但如果我们能秒级快照整个文件系统并延迟加载，我们就不再需要那么多复杂的仪式（如 Dockerfile 或 Ansible）。你直接在生产环境的副本上迭代，觉得对了，直接合并文件系统。

<details>
<summary>Original English</summary>

**Jake Cooper**: I actually think that maybe that's the the hot take, but I think that that's actually going to change. And I think you can move towards having pets so long as uh you have a and this is going to be a jump. So long as you have a cloning machine for your pets. If you can snapshot every single thing at every frame, then like it actually doesn't matter if you know that obliterated because you have some sort of like snapshot of it, right? What if you just had the whole file system? what if you just snapshot it and what if you lazily load the entirety of the file system? right then you can get around this problem entirely.

</details>

**Allesio**: 听起来很有趣。非常感谢你的分享。

<details>
<summary>Original English</summary>

**Allesio**: Sounds fun. Amazing. All right, that's the future of cloud. Thank you. Thank you for having me. It's been wonderful.

</details>