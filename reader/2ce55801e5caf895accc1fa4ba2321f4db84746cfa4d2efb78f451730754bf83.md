---
author: a16z
date: '2026-10-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=blkIGLlZePg
speaker: a16z
tags:
  - distributed-systems
  - observability
  - system-reliability
  - ai-agents
  - infrastructure-operations
title: 从代码自动补全到系统运维：AI能否接管分布式系统的现实世界复杂度？
summary: 本期对话中，a16z合伙人Martin Casado与Granica创始人兼CEO Jad Naous围绕AI在软件工程与系统运维中的应用边界展开深度探讨。从Stanford求学与Nicira创业经历出发，两人剖析了AI在代码生成（纯数字世界、确定性反馈）与系统运维（物理世界交互、噪声与黑盒状态）之间的本质差异，指出遥测数据在微服务时代的成本失控本质，并展望了AI赋能全自动运维（AIOps）的可行路径与核心瓶颈。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Martin Casado
  - Jad Naous
companies_orgs:
  - Granica
  - Andreessen Horowitz
  - AppDynamics
products_models: []
media_books: []
status: evergreen
---
### 现实与数字世界的割裂

**Martin Casado**: 人工智能所处的世界完全是数字化的，但现实世界是客观存在的实体，这两者并不完全相同。

<details>
<summary>Original English</summary>

**Martin Casado**: The world that the AI lives in is all digital and there's the actual world and like those things are not necessarily the same.

</details>

**Jad Naous**: 当我们最初开始做面向编程的 AI 时，它其实就是**代码补全（autocomplete）**。当时没有任何人真正知道究竟能在多大程度上用 AI 去构建复杂的软件。但随后它彻底打破了人们的预期，因为我们能够在系统中对越来越高的复杂性进行建模。

<details>
<summary>Original English</summary>

**Jad Naous**: When we started doing AI for coding, it was autocomplete. Nobody really knew to what extent you can actually build complex software using AI and then it basically broke through the expectations because we were able to model more and more complexity in the systems.

</details>

**Martin Casado**: 我只是不确定运维领域（operations）是否受到同样的约束。甚至我们去哪里找数据，来训练出一个能够理解全部运维流程的系统？我的假设是我们拥有所有的数据。我认为核心问题可能在于复杂性，以及在多大程度上你能把你所描述的那些运维层面的事物，转化为 AI 可以进行逻辑推理的形式？长期以来，依靠纯人力来管理分布式集群一直是行业里秘而不宣的事实。你觉得我们现在是否已经到了可以用 AI 来实际运行这类服务的临界点？

<details>
<summary>Original English</summary>

**Martin Casado**: I just don't know if operations is constrained in the same way. Where's even the data to learn how to like build a system that understands like all of the operations? My assumption is that we have all the data. The question I think is maybe about complexity and like to what extent can you take the things that you've described that are operational and convert them into something that an AI can reason about the dirty secret for the longest time of running like a distributed cluster with just human beings managing it. Do you think we're at a spot where you could like use AI to run one of these services?

</details>

### 斯坦福岁月与极客往事

**Martin Casado**: 好吧，Jad，非常感谢你能来参加这期播客。对于那些还不了解你的听众，Jad 是 **Granica** 的创始人兼 CEO，但同时我们当年也是在斯坦福同一个研究生课题组里的同学。我记得第一次见到你时，组里刚来了一位新学生。我走进办公室，桌上放着一个摩托车头盔和一包万宝路香烟。我当时心想：“这家伙未免也太酷了吧！”所以我的第一个问题是：你当年那种酷劲儿后来都去哪儿了？

<details>
<summary>Original English</summary>

**Martin Casado**: All right, Jad. thanks for joining me on the podcast. For those of you who don't know, Jaden is the CEO of Greer, but also we uh went to grad school in the same group. And when I first met you, I we we had a new student. I I walked into the office and there was a motorcycle helmet and a pack of Maros. [laughter] I'm like, "This guy must be unbelievably cool." So my question is is what happened to all your coolness? [laughter] Question number one,

</details>

**Martin Casado**: 哈哈，开个玩笑。为了给听众提供一些背景信息，也许你可以先简要介绍一下你的个人履历。向大家介绍一下，Jad 是我认识的最优秀的**系统思维者（systems thinker）**之一，我非常喜欢和他交流。今天我们将从系统视角深入探讨工程架构，以及 AI 正在给我们带来怎样的冲击，尤其是深入到运维等领域。不过为了让大家有个基本了解，先聊聊你的背景吧。

<details>
<summary>Original English</summary>

**Martin Casado**: maybe maybe maybe just for a context, maybe give give um a quick um uh overview of your background. So just just for those that are listening, you know, dad is one of the best systems thinkers I know. I love talking to him. We're going to go kind of to a deep dive of like engineering from a systems perspective and how AI is impacting us. We're going to kind of especially when it comes to things like operations, but just to ground it maybe a bit about your background.

</details>

**Jad Naous**: 没问题。你当时遇到我的时候，正好是我人生中耍酷的巅峰期之一。

<details>
<summary>Original English</summary>

**Jad Naous**: Sure. So, uh, you met me at, uh, one of the peaks in my coolness.

</details>

**Martin Casado**: 是啊，你那时候特别酷。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah, you're very cool.

</details>

**Jad Naous**: 摩托车配万宝路香烟。

<details>
<summary>Original English</summary>

**Jad Naous**: Motorcycle and Marorrow cigarettes.

</details>

**Martin Casado**: 我记得我当时在想：“哇，现在抽烟难道还合法吗？”在那个环境下看起来实在太违和了。

<details>
<summary>Original English</summary>

**Martin Casado**: I remember thinking I'm like, "Wow, are cigarettes even legal?" It was like so discordant.

</details>

**Jad Naous**: 我记得有一天我们的导师 **Nick McKeown** 看到我在盖茨计算机大楼（Gates Building）外面抽烟，他看着我说：“天哪，Jad！”

<details>
<summary>Original English</summary>

**Jad Naous**: I remember Nick seeing me one day smoking outside of uh outside of Gates and looking at me and going like, "G Nick Bun is our adviser. Gates

</details>

**Martin Casado**: 对，Nick McKeown 是我们的导师，盖茨楼就是斯坦福计算机系大楼。

<details>
<summary>Original English</summary>

**Martin Casado**: is computer science department.

</details>

**Jad Naous**: 其实我最喜欢的一件事——你还记得 Balaji Prabhakar 教授吗？

<details>
<summary>Original English</summary>

**Jad Naous**: actually one of my favorite thing I don't do you remember Balaji Prabakar the professor

</details>

**Martin Casado**: 当然记得。

<details>
<summary>Original English</summary>

**Martin Casado**: of course

</details>

**Jad Naous**: 我最喜欢他的一点就是他也抽烟。他是系里唯一抽烟的教授，我觉得这太酷了。

<details>
<summary>Original English</summary>

**Jad Naous**: my favorite thing about him is that he smoked I was like the [laughter] only professor I just thought it was like great

</details>

**Martin Casado**: 先澄清一下，我现在已经不抽烟了。

<details>
<summary>Original English</summary>

**Martin Casado**: just to be clear I don't smoke anymore

</details>

**Jad Naous**: 我也不抽了，人到中年，折腾不起了。不过说回正题，你看，我和你一起在斯坦福读书，你当时一直是我仰望的前辈，我心想：“这就是我长大后想要成为的人。”

<details>
<summary>Original English</summary>

**Jad Naous**: no too old too middle-aged for that now um but let's see so you know I went to Stanford with uh with you you were always the guy I had to look into to look to look up to and be like hey this is the guy I want to be when I grow up

</details>

**Martin Casado**: 我比你早入学四年，所以确实比你早一些。

<details>
<summary>Original English</summary>

**Martin Casado**: I was I think it was I it was a I started started four years before you did. So I was ahead

</details>

**Jad Naous**: 你比我高四届，比我早毕业好一阵子。你毕业后去创立了 **Nicira**。我当时选择继续留下来，在 **OpenFlow** 项目上做了更多研究，从安全角度协助在硬件层面构建了许多基础设施。实际上，我在那里做过的最有趣的项目之一，是我构建了人们当时正在评估的第一批 **SHA-3** 硬件实现，为了我的博士论文，我在硬件上验证它们到底能否正常工作。那段经历非常有意思。

<details>
<summary>Original English</summary>

**Jad Naous**: and so you were four years ahead of me. You graduated a while ahead of me. You went and started Nicer. I stayed and stuck around worked more on OpenFlow. Helped uh build a bunch of stuff on the hardware side from a security perspective. Actually, one of the one of the, you know, most fun projects that I worked on there was uh I built the first set of uh Shaw 3 implementations that people were considering using and um I built them in hardware to kind of show whether they work or not and whatever for one of my for uh one of my projects for my thesis. That was fun.

</details>

**Martin Casado**: 确实很酷。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah. Yeah. Cool.

</details>

**Jad Naous**: 但过了一段时间后，我觉得自己其实并不喜欢网络底层，因为网络本质上无非就是把比特从一个地方搬运到另一个地方。

<details>
<summary>Original English</summary>

**Jad Naous**: And then I decided after a while that I actually don't like networking because it's just about moving bits from one place and putting them in another place.

</details>

**Martin Casado**: 移动比特能有多难呢？

<details>
<summary>Original English</summary>

**Martin Casado**: How hard can that be?

</details>

**Jad Naous**: 这取决于你哲学上是认同它高深莫测，还是觉得它很浅显。大多数人都以为它很简单，但我认为它其实极其深奥。

<details>
<summary>Original English</summary>

**Jad Naous**: I think that would have to either be philosophically aligned that it's deep or not. Most people assume it's not. I think it's very deep.

</details>

**Martin Casado**: 它确实有其迷人之处，但对我来说，它最终并不能激发我的热情。

<details>
<summary>Original English</summary>

**Martin Casado**: I mean there's something interesting about it, but ultimately to me that's like it's not

</details>

**Jad Naous**: 是的，它点燃不了你。后来我去 MIT 跟随 **Nickolai Zeldovich** 做博士后，他也是极其渊博、智商极高的学者。

<details>
<summary>Original English</summary>

**Jad Naous**: Yeah. It doesn't do it for you. Yeah. Um and then uh I actually went and did a posttock at MIT with Nikolai Zelda who's also amazingly deep and super smart.

</details>

**Martin Casado**: 他确实非同凡响。

<details>
<summary>Original English</summary>

**Martin Casado**: he's phenomenal.

</details>

**Jad Naous**: 我当时从事了一些应用安全方面的研究。后来基于我和 Ramesh Chandra 合作的研究成果创办了一家公司。核心逻辑主要是 Ramesh 的博士课题：如果系统遭受攻击，能否自动隔离故障并修复系统？

<details>
<summary>Original English</summary>

**Jad Naous**: I did some application security work at the time. Started a company um based off some of the research I had worked on with Ramsh Chandra over there who What was it? So what we did was um well you know ultimately a lot of the work was actually really Romeshes and his PhD was on well hey if you get attacked, can you

</details>

**Martin Casado**: 明白。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah.

</details>

**Jad Naous**: 我们试着在真实商业世界中去落地这个方案，结果发现这太困难了。不过这恰好与我们今天要聊的主题高度相关。

<details>
<summary>Original English</summary>

**Jad Naous**: And so we started doing that in the real world and we're like ah that sounds really hard. It's actually kind of relevant to what we're going to talk about today.

</details>

**Martin Casado**: 我们当年也差点就做成了。对于所有长尾学科（longtail disciplines）来说，这正是为什么聪明人往往会陷入其中——你看到了一点进展，就以为能搞定一切。

<details>
<summary>Original English</summary>

**Martin Casado**: yeah I we almost got it working almost I feel like for all longtail disciplines this is why people get in like the fly track for smart people is like you see a bit of progress but you

</details>

### 从实战运维到风险投资

**Jad Naous**: 后来我加入了 **AppDynamics**，在那里待了大约三年半。公司规模从大约 200 人扩张到了 2000 人，最终被思科（Cisco）收购。我只当了一天的思科员工就离开了。当时你对我说：“Jad，我太喜欢你了，过来跟我一起干吧！来跟我一起做 VC 投资！”我当时的反应是：“什么？什么是风险投资？我是一个系统架构师，我做的是硬核工程，你在说什么啊？”你说：“太好了，你懂的越少越好。”

<details>
<summary>Original English</summary>

**Jad Naous**: So then I joined App Dynamics. I was there for about three and a half years. They went from about 200 people to 2,000 people. Got acquired by Cisco. I was a Cisco employee for one day. And I said, and then you're like, Jad, I know. I love you. Come work with me. Come do this VC thing with me. I'm like, what the What What is VC? What? Like I'm an architect. I do like engineering stuff. What do you He's like, great. The less you know, the better.

</details>

**Martin Casado**: 哈哈，这确实是我当时的原话。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah. Literally what you said.

</details>

**Jad Naous**: 确实如此。我入职第一天，你对我说：“把节奏慢下来。”从实际一线运维和工程世界跨界进入风险投资领域，需要对大脑认知进行彻底重构。

<details>
<summary>Original English</summary>

**Jad Naous**: It's true. And then the first day I started here, you said slow down. It's actually people that move from operate like from like actually an operating world to VC. It requires a lot of reworking the brain.

</details>

**Martin Casado**: 没错，顺便说一句，就像从读博士转向实际一线运营一样，你必须清除过去留下的某些思维定势。

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah. Just like going from a PhD to operating by the way. Like you have to like undo the brain damage.

</details>

**Jad Naous**: 这正是我切身经历的真实世界。之后我在 **a16z** 待了几年，和你一起做了大量投资工作，那是一段非常愉快的时光，与 Jennifer、Mark、Ben、Satish 等诸多优秀伙伴并肩作战。

<details>
<summary>Original English</summary>

**Jad Naous**: This is my experience. This is what real world is like. I know. And then um I stayed here for a couple of years. Did a bunch of work with you. It was a really fun time. Worked with a lot of great people like Jennifer, Mark, and Ben. Satish.

</details>

**Martin Casado**: 还有 Satish，Matt 在你快离开时也加入了。

<details>
<summary>Original English</summary>

**Martin Casado**: Satish. Um Matt was uh here when I first uh what almost towards the end when I was leaving. Yeah.

</details>

### 可观测性的成本危机与 Granica 的诞生

**Jad Naous**: 离开机构后，我加入了一家初创公司担任首席产品官（CPO），负责组建工程与产品团队，将团队从 15 人扩充到涵盖产品、工程、信息安全和设计的 90 多人规模。大约三年后，团队各个方向都有了成熟的负责人，我发现自己整天都在开会和协调，于是想跳出来做点新东西。离职后，我开始密集地与大量工程研发负责人交谈，调研他们面临的核心痛点。那是在 2023 年左右，大家都在谈“降本增效”。我问他们：“你们的钱主要花在哪里了？”几乎所有人的第一反应都是基础设施，紧接着就是**可观测性（Observability）**。我便开始深入研究这个问题：为什么大家普遍觉得可观测性太贵了？

<details>
<summary>Original English</summary>

**Jad Naous**: And then um and then joined Apply as their chief product officer. Um helped them build uh their engineering product teams. Kind of scaled from about engineer like 15 people to over 90 across product engineering infosac and design. And after about 3 years, um, I kind of had a head for each one of these pieces that I owned and I kind of was sitting around just coordinating and doing meetings all day and wanted to go do something else. So left and then um started talking to a lot of engineering leaders about the problems that they're facing and what they're trying to do. Everybody at the time, this was in 23, everybody was saying, "Hey, we're trying to reduce spend." And ask them, "What are you spending money on?" Everybody would say observability. And you know well first actually it was infrastructure and then observability. And so I started looking at that problem trying to understand like what is why do people think it's too expensive?

</details>

**Martin Casado**: 他们希望获得支出的可预测性。

<details>
<summary>Original English</summary>

**Martin Casado**: of spend like predictability of spend

</details>

**Jad Naous**: 深入分析后发现了几点核心原因：首先，企业在可观测性上的花费，通常占到了基础设施总成本的 5% 到 20%。但大家购买可观测性，其底层本质是在**购买系统的可靠性（Reliability）**。大家把资金砸向可观测性，是将其视作可靠性的代名词。在过去很长一段时间里，你投入的资金越多，获得的系统可靠性就越高。

<details>
<summary>Original English</summary>

**Jad Naous**: reliability of their infrastructure and applications. Right. And so they were putting money into observability as a proxy for reliability. And for the longest time, the more money you spend,

</details>

**Martin Casado**: 确实是这样。

<details>
<summary>Original English</summary>

**Martin Casado**: I see. I see. I see.

</details>

**Jad Naous**: 但是，随着系统架构演化为粒度更小、垂直集成度更高的**微服务（Microservices）**架构，系统每一层产生的数据呈爆炸式激增。数据收集量与可观测性成本的增速，已经远远超过了业务功能的产出增长。更致命的是，每在可观测性上多花一块钱所带来的边际可靠性提升，曲线已经彻底拉平了。所以大家都觉得它贵，但为了可靠性又不得不支付这 5% 到 20% 的账单。于是核心命题就变成了：我们能否不靠一味增加可观测性投入，而是换一种方式重新找回可靠性的边际收益？

<details>
<summary>Original English</summary>

**Jad Naous**: the more reliability you got out. But as architectures changed and turn into microservices that are much smaller, that are much more vertically integrated. The volume of data that's being collected at every layer expanded. there was much deeper market penetration for observability and kind of the uh volume of data that you're collecting and the cost of observability was actually starting to grow faster than the units of function that you're outputting. And um and the marginal rate of or like the marginal increase in reliability for every additional dollar you were spending on observability was just flattening out. Um, and so that's why people thought it was expensive, but people were still willing to pay 5 to 20% on reliability. And so the question was like, can we actually solve that problem and bring back the um that increase in reliability, that marginal increase in reliability,

</details>

**Martin Casado**: 通过某种全新的途径来解决。

<details>
<summary>Original English</summary>

**Martin Casado**: not necessarily by spending more money on observability, but some other way.

</details>

**Jad Naous**: 没错。我们的构想是：如果能在海量数据中精准辨别出真正的**信号（Signal）**与**噪声（Noise）**，将当前绝大部分形同虚设、沦为安慰剂保险的冗余遥测数据在数据流的上游完成特征提取与精简，下游的可观测性存储与分析成本就会大幅下降。而在上游实时提炼出高质量信号后，我们就可以将其注入其他系统，驱动真正的自动化运维。当时生成式 AI 正在崭露头角，我们意识到：如果我们卡位在数据流的核心路径上并提炼信号，就占据了为未来 AI 系统输送养料的战略要塞。这就是 **Granica** 的业务初心。

<details>
<summary>Original English</summary>

**Jad Naous**: And so the thinking was like, okay, great. If we can figure out what is the signal, what is the noise, can we actually turn the observability data that you're collecting that it's mostly fluff and mostly insurance at this point and do that kind of extraction of information upstream, do whatever you need upstream and be able to ultimately massively reduce the cost of observability downstream. And if you can extract that signal in real time upstream then you can one reduce the cost but two you can now feed it into other systems and use it for driving reliability operations afterwards and the distance at the time there was something that was called AI coming coming into the picture and we're like well great if we are in the data stream and we're extracting the signal then we are in a strategic position to feed that to whatever is going to come in the future because that's going to be necessary.

</details>

**Martin Casado**: 顺便问一句，你日常使用大模型来辅助编程或系统构建吗？你觉得这种使用效率是针对特定模型训练出来的直觉，还是对广泛意义上的 AI 形成的使用方法论？

<details>
<summary>Original English</summary>

**Martin Casado**: Yeah. And what I do, as an aside, do you think that's model specific? Like is it do you learn how to use AI, you know, writ large or do you get efficient at a given model?

</details>

### 从代码生成到复杂运维的鸿沟

**Jad Naous**: 我认为目前很大程度上依然是模型特定的。不同的模型有各自独特的“脾气”，比如语法风格、提示词触发词等。你熟悉了某一个模型后，换到另一个模型往往需要重新适应其响应特征。

<details>
<summary>Original English</summary>

**Jad Naous**: yeah And the syntax is the fact that it's just three a threeletter word

</details>

**Martin Casado**: 那么回到代码与运维的对比上来。代码之所以能够被 AI 极好地解决，核心在于代码的世界是一个封闭的纯数字系统，有编译器提供即时反馈，有单元测试进行确定性验证。但对于**系统运维（Operations / SRE）**而言，环境完全是开放且不可预测的。你如何看待这种差别？

<details>
<summary>Original English</summary>

**Martin Casado**: Well, what do you want to call them? When you think about code versus operations, code is constrained. There is a compiler, there are deterministic test cases. In operations, you are dealing with real-world messiness.

</details>

**Jad Naous**: 这一点极其关键。在软件工程中，从需求到代码实现，中间的逻辑链条虽然复杂，但在计算机内部是被严格定义的；如果编译失败或测试报错，模型可以立即获取反馈并自我纠错。但在分布式系统运维中，你面对的是生产环境中成千上万个动态交织的变量。网络抖动、磁盘坏道、依赖服务超时、突发流量洪峰——很多故障根本无法在沙盒中精准重现。更重要的是，遥测监控数据本身存在滞后与失真，你看到的指标异动往往只是表象，背后的根因（Root Cause）隐藏在错综复杂的微服务调用链深处。

<details>
<summary>Original English</summary>

**Jad Naous**: That's exactly right. In coding, you have a closed loop. The compiler tells you if you have a syntax error, your test suite tells you if your logic holds. In operations, you are dealing with real-world physics, network partitions, cascading failures, noisy telemetry. You cannot simply roll back the universe to test a hypothesis safely in production.

</details>

**Martin Casado**: 这让我想起过去这么多年，大规模分布式集群的实际管理方式几乎是行业里的“肮脏小秘密”。外面看起来一切都是自动化的 Kubernetes、弹性伸缩，但底层真正在救火的永远是一群疲惫不堪的 SRE 工程师，在深夜靠着 Slack 报警排查各种莫名其妙的系统偶发异常。

<details>
<summary>Original English</summary>

**Martin Casado**: That's the dirty secret for the longest time of running like a distributed cluster with just human beings managing it. On the surface it looks like automated orchestrators, but in reality it's humans on pager duty at 3 AM looking at dashboards trying to guess what broke.

</details>

**Jad Naous**: 完全正确。运维人员的大脑实际上在扮演着一个极度复杂的隐式推理引擎：他们结合了系统的拓扑结构、历史故障记忆、最近的代码部署变更记录，以及当下的警报，在脑海中做模糊匹配与归因推理。现在的挑战在于：AI 能否从海量杂乱的日志、指标（Metrics）与链路追踪（Traces）中抽丝剥茧，构建出这样一套世界模型？

<details>
<summary>Original English</summary>

**Jad Naous**: Exactly. An on-call engineer's brain is essentially running an intuitive reasoning loop combining mental models of topology, past incident memory, git diffs from the latest push, and current alert firehoses. The billion-dollar question is whether an AI agent can build that same contextual world model from telemetry data.

</details>

### 数据提纯与未来自动化运维图景

**Martin Casado**: 很多人会说，既然如此，为什么不把所有的日志与监控数据无脑喂给大模型上下文？

<details>
<summary>Original English</summary>

**Martin Casado**: People often ask: why not just dump all the raw logs and telemetry straight into a massive context window and let the LLM figure it out?

</details>

**Jad Naous**: 这正是最致命的误区。首先是成本与吞吐量完全不可承受——一家中大型科技公司每天产生的遥测日志往往以 PB 计算，没有任何大模型能实时处理这种量级的数据。其次是信噪比极低：99% 的遥测数据在平时都是心跳探测和无意义的健康确认，真正的异常信号被严重稀释。如果你把未经提炼的原始数据喂给模型，模型不仅会被噪声干扰产生严重幻觉，而且根本抓不住核心诱因。这就是为什么必须在数据流的上游完成特征抽取和语义升维，将底层冰冷的字节转换为带有拓扑与因果语义的高纯度事件，AI 才有可能进行严密的高阶推理。

<details>
<summary>Original English</summary>

**Jad Naous**: That is a catastrophic mistake both economically and technically. Mid-to-large enterprises generate petabytes of telemetry daily. You cannot stream that into LLMs without bankrupting the company. Furthermore, 99% of that telemetry is pure noise—routine heartbeats and healthy pings. If you dump raw noise into a model, you get hallucination and context saturation. You must distill telemetry into high-signal semantic events upstream before feeding it to reasoning agents.

</details>

**Martin Casado**: 这回到了价值衡量的根本问题。在代码生成领域，开发者生产力提升可以直接体现在功能交付速度上，ROI（投资回报率）非常直观。而在运维与可靠性领域，衡量其商业价值似乎要复杂得多。

<details>
<summary>Original English</summary>

**Martin Casado**: And it's interesting, like for code, people just get it. They see the velocity increase. On the ops side or anything beyond that, it's very hard to understand the actual value and put a dollar value to it.

</details>

**Jad Naous**: 确实如此。代码工具是“进攻型”的，能直接多写功能；而运维工具是“防御型”的。但如果你换个视角看：一次灾难性的业务宕机，带来的损失可能是数百万美元甚至品牌的毁灭。如果 AI 能够提前预判链路瓶颈并实施自愈操作，避免服务中断，那创造的隐性价值是不可估量的。只不过目前行业在系统级全自动运维上仍处于极早期探索阶段。

<details>
<summary>Original English</summary>

**Jad Naous**: Exactly. But you can also think about it in terms of business downtime saved. If an intelligent operations system prevents a Tier-0 outage, the avoided loss is massive. Code generation felt magical because autocomplete surprised everyone. For automated operations and SRE agents, we are still at the very beginning of that curve.

</details>

**Martin Casado**: 无论如何，这是一场极其深刻的范式变革。非常感谢你今天的精彩分享，Jad！

<details>
<summary>Original English</summary>

**Martin Casado**: It's still pretty early, but the potential is enormous. All right, well, listen, it was great to chat. Thanks so much, Jad!

</details>

**Jad Naous**: 谢谢你，Martin！聊得非常尽兴。

<details>
<summary>Original English</summary>

**Jad Naous**: Thanks, Martin! Really enjoyed it.

</details>