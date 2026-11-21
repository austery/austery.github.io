---
author: Latent Space
date: '2026-11-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rSWiNE92xqM
speaker: Latent Space
tags:
  - coding-assistant
  - developer-tools
  - software-engineering
  - open-source
title: 微软 CoreAI 执行副总裁 Jay Parikh 谈 GitHub 规模化与 AI 智能体演进
summary: 微软 CoreAI 执行副总裁 Jay Parikh 在 GitHub Universe 期间接受采访，探讨了平台拥有 2.25 亿开发者与海量提交的扩展规模、Copilot Harness 与多模型路由技术 Fusion、全端上下文协同、AI 安全审查以及开源生态的未来演进与上云规划。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Jay Parikh
companies_orgs:
  - GitHub
  - Microsoft
products_models:
  - GitHub Copilot
media_books: []
status: evergreen
---
### 开篇：GitHub 的规模演进与智能体时代

**>>**: GitHub 是我们所有开发的核心，并且越来越成为智能体与人类协作的核心方式。我认为很多人常常因为停机时间而对其抱怨颇多——尽管它是今年首个在可靠性上达到 0 个 9 的服务。但人们往往也不了解它为了适应人类需求以及智能体需求而试图进行演进所面临的极端规模。

今天采访的对象是微软 Core AI 执行副总裁 Jay Parikh。我认为他实际上差不多就是包括 GitHub 在内的诸多核心 AI 服务的领导者。我们之前采访过 GitHub 首席运营官 Kyle Daigle，我认为在 GitHub Universe 上，他们发布了大量的最新更新，涉及他们如何处理基础设施层、模型层以及应用层的内容。

关于 Copilot，它显然是大约五六年前推出的初代代码助手，其中一些统计数据非常令人难以置信：GitHub 上大约 40% 的拉取请求（PR）是由智能体驱动、智能体创建的；智能体总量的增长在 6 个月内达到了 6 倍。因此，GitHub 的构成发生了巨大变化。即便发生了这些转变，人类对 GitHub 的采用也在增长。现在已经达到了 2.25 亿开发者。我还记得当时达到 8000 万开发者对他们来说是一件大事。现在基本以全年每秒增加一名开发者的速度增长。这极其庞大且令人惊叹。而且他们在此过程中还在尝试迁移到 Azure。如此巨大的演进，我认为需要极强的领导力。

幸运的是，Jay 在这个领域资历深厚：他不仅曾任 Facebook 工程主管，还曾任 Lacework 首席执行官，以及 Ning 和 Akamai 的工程副总裁，这几乎就像是基础设施安全甚至社交媒体领域的“复仇者联盟”级别履历——别忘了 GitHub 本质上是一个开发者的社交网络，大家汇聚于此共同维护我们所有人都依赖的这项服务。这非常有趣。虽然这不是一条一帆风顺的道路，但面对故障和停机，我们当中又有谁能站在道德制高点去指责呢？当然，总有人试图去寻找替代 GitHub 的方案，但 GitHub 始终会是 GitHub。我认为确保我们能够帮助并理解这个我们共同协作、发布开源项目以及发现安全问题的核心平台的演进，符合我们所有人的利益。

我们目前正在筹划 AIE Code，这是今年最后一场 AI 工程师大会，也是旧金山这里唯一完全专注于编码智能体的大会。为了做准备，我认为发布这篇采访会很有帮助，能让大家在心理上对这一年间编程领域发生的巨大规模、雄心和变革做好准备，并预览下一年的发展。所以，我自然也向 Jay 询问了 2027 年的 GitHub 会是什么样。希望大家能坚持看到最后去听听他的预测。现在，让我们进入采访。

我们在你的主题演讲结束后紧接着录制。感觉如何？祝贺又一届成功的 Universe 大会。
<details><summary>Original English</summary>
**>>**: GitHub is at the heart of all of our developments and increasingly how agents and humans collaborate as well. And I think a lot of people give GitHub a lot of for it downtime uh being the first service in this year to reach 09s in reliability. But also people don't know the extreme scale at which it is trying to evolve itself uh to fit GitHub human needs as well as agent needs.

Today's interview is with Jay Parrick who is EVP of core AI at Microsoft. Uh de facto I think more or less the leader of a lot of the core AI services including GitHub. Uh we previously interviewed Kyle Dagel who's COO of GitHub and I think at GitHub Universe they release a lot of new updates as to how they're handling infrastructure layer stuff, model layer stuff, application layer uh stuff uh with copilot the obviously the original coding assistant that was launched uh almost like five six years ago now and some of the stats are really mindboggling uh about 40% of pull requests on GitHub are agentbased agent created and that uh the total agent growth has six times in 6 months. So, uh the composition of GitHub has been changing a lot. Even with all that shift, um the human adoption of GitHub has been growing as well. They're now up to 225 million developers. I remember when 80 million developers was was a big deal for them. And adding basically one developer every second of every of the year. And that's enormous and mindboggling. And uh they're also trying to migrate to Azure while doing this. And it's just so much u evolution that I think it requires a lot of leadership.

Fortunately, Jay has a lot of uh credentials in this area like he not only was head of engineering for Facebook but also CEO of Lace Work um and vice president of engineering for Ning and Akami where it's a lot of this like the avengers of like infrastructure security and uh social media even because don't forget GitHub is a social network of developers all coming together to maintain this service that all of us rely on. It's very interesting, you know, it's it's a it's not been a smooth path and but like which among us, you know, can throw a stone when it comes to outages and and downtime. Um, definitely I think there's there's a hunt for people trying to replace GitHub, but GitHub will always be GitHub. And I think it is in all of our interest to make sure that we can help and understand the evolution of the core platform that all of us collaborate on and publish open source work and also spot security issue. We're currently in the middle of preparing for AIE code which is the last AI engineer conference of the year and the only one focused entirely on coding agents here in San Francisco. So in preparation, I thought it would be nice to release this interview to help people prepare mentally for the sheer scale and ambition and change that has happened in this one year in coding and to preview the next year as well. So of course I had to ask Jay what GitHub will look like in 2027. And so I hope you stay through to the end to see his predictions. And let's go on to the interview. We're recording just after your keynote. How did it feel that uh congrats on another successful universe?
</details>

**>>**: 是的，今天涵盖了非常多的内容。很多很棒的内容。
<details><summary>Original English</summary>
**>>**: Yeah, it was a lot of stuff to cover today. A lot of good stuff.
</details>

**>>**: 很多很棒的内容。实际上，有很多内容因为时间不够，你甚至都没能在台上讲完。
<details><summary>Original English</summary>
**>>**: A lot of good stuff. Actually, a lot of stuff that you couldn't even cover on stage cuz you didn't have time.
</details>

**>>**: 没错。确实是这样。
<details><summary>Original English</summary>
**>>**: That's right. That's right.
</details>

**>>**: 比如像那些安全方面的内容。
<details><summary>Original English</summary>
**>>**: Uh like even like the security stuff and
</details>

**>>**: 那些都安排在今天和明天的各种不同工作坊里，以便深入探讨并亲自动手实践。
<details><summary>Original English</summary>
**>>**: those are all the different workshops going on today, tomorrow to dig in and then get hands-on keyboard.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 去看看这些东西是如何运作的。
<details><summary>Original English</summary>
**>>**: To see how these things work.
</details>

### 平台规模：2.25 亿开发者与每秒新增一人

**>>**: 不过让我们为播客听众重申一下核心数据。我其实还专门查了一年有多少秒，因为你说今年每一秒都有一位开发者加入。那是 3150 万人。
<details><summary>Original English</summary>
**>>**: Uh but let's reiterate for the podcast listeners topline numbers. Uh I actually had to look up how many seconds in a year because you said there's a developer that joined every second of this year. That's 31.5 million.
</details>

**>>**: 是的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 这非常令人印象深刻。GitHub 上的总用户数达到了 2.2 亿。
<details><summary>Original English</summary>
**>>**: Um which is very impressive. And the total number 220 million on on GitHub.
</details>

**>>**: 是 2.25 亿。
<details><summary>Original English</summary>
**>>**: 225.
</details>

**>>**: 那么都是谁加入了呢？
<details><summary>Original English</summary>
**>>**: But who's coming?
</details>

**>>**: 好吧，谁加入了呢？每一秒都有新的人加入。而且，我的意思是你展示的整体图表真的很令人震撼，我认为这就是大家平时看不到的。他们总是理所当然地认为 GitHub 永远都能正常运行。
<details><summary>Original English</summary>
**>>**: Okay. Well, who's coming? Well, every second there's another one. Um and like I mean just the general charts that you showed are really impressive and I think that's what people don't don't see. They they expect GitHub to just always work.
</details>

**>>**: 是的，完全没错。你刚才已经提到并说出来了。平台上拥有 2.25 亿开发者，涵盖了世界上每一个国家。在去年的 Octoverse 报告中，平台上每秒钟就有一位新开发者加入。这已经是连续第二年出现这种情况了，对吧？然后同样在 Octoverse 报告中，我们提到了一些核心统计数据。这里面有——
<details><summary>Original English</summary>
**>>**: Yeah, absolutely. So you already alluded to it or said it. 225 million developers on the platform and that spans every country in the world. And last year in our octiverse reports, a new developer joined the platform every second. And that's the second straight year that that's happened, right? And then in the Octiverse report also, we talked about a couple of like main stats. And there's
</details>

**>>**: 179 亿次代码推送（push）。有 343 亿次提交（commit）。有 13 亿个拉取请求（PR）。而且开源社区持续在以甚至超过以往的规模进行构建和分享，相比去年增长了两倍半。所以我们看到平台上在开源社区或项目中产生了 21.5 亿次贡献。
<details><summary>Original English</summary>
**>>**: 17.9 billion code pushes. There's 34.3 billion commits. There is um 1.3 billion PRs. And then the open source community continues to build and share even more than it did last year. It's up two and a half times. So we saw 2 1.5 billion contributions on the platform in open-source community or projects.
</details>

### 代码社交网络与智能体参与

**>>**: 对于正在收听的开发者和工程师来说，这每一次都意味着数据库写入、文件写入和元数据计算，完全——
<details><summary>Original English</summary>
**>>**: And for people for developers and engineers listening every that's like database rights and that's file rights and metadata comping and absolutely
</details>

**>>**: 这就是一个代码社交网络。你曾在社交网络公司工作过。运营这样一个社交网络感觉如何？[笑声]
<details><summary>Original English</summary>
**>>**: uh it's it's it's it's a it's a code social network. You've worked on social networks. um how is it running this this social network [laughter]
</details>

**>>**: 你知道，这——
<details><summary>Original English</summary>
**>>**: you know it's
</details>

**>>**: 顺便说一句，还有 Ning。
<details><summary>Original English</summary>
**>>**: and by the way Ning
</details>

**>>**: 还有 Facebook。是的，这里面确实有一些相似的模式。我想说，显而易见的是，这里的最终用户或使用平台的人群是非常不同的，对吧？但实际上我认为，考虑到如今 AI 领域发生的一切，存在一个巨大的机遇，那就是这个社区现在能够吸纳更多的人群，对吧？从历史上看，GitHub 可能是：“嘿，我是软件工程师，或者我是产品经理，或者是设计师，我可以使用 GitHub。”但现在，你不再需要成为一名技术娴熟的软件工程师才能使用 GitHub 了，对吧？现在借助编码智能体，它们可以为你完成很多事情，然后你就可以去分享想法。

前几天我其实还在跟另一位记者交流，他当时在尝试做一些实验，然后决定：“嘿，我想建一个仓库，然后把这个仓库分享给其他人并获取反馈。”所以我觉得这是全世界采纳并学习 AI、共同构建事物的一种全新方式。今天我在主题演讲中也谈到了这一点，对吧？那就是这个社区最让人惊叹的地方之一就在于：你不需要独自构建，我们都在这里共同构建。
<details><summary>Original English</summary>
**>>**: and and Facebook yeah there's there's some pattern in here I would say it's obviously a very different set of end users or people using the the platform right but I actually think just given what's happening with with AI these days what I I think there's just a really big opportunity which is that community now can encompass so many more people, right? And historically, maybe GitHub was, hey, I'm a software engineer or I'm a product manager or maybe a designer and I can use GitHub. But now, you know, you don't have to be a, you know, a skilled software engineer to use GitHub, right? So now with coding agents can do a lot of things for you and then you can share an idea. Uh I was actually talking to another reporter the other day who you know was experimenting with something and like decided hey I want to create a repo and then I want to share that repo with people and get feedback on it. So I think it's like another way of the world adopting and learning AI to build things together. And that's I said it today in the keynote, right, which is that is um one of the most like amazing things about this community is like you don't have to build alone like we're all here building together.
</details>

**>>**: 是的。我觉得有一点非常重要，你们获得的支持背书之一来自 OpenClaw 的 Pete Steinberger，他可能是你们最顶尖的 0.001% 的核心用户之一，真正把 GitHub 推到了极限。我认为他提出的一个有趣的推进点可能是拉取请求（PR）的终结。我不知道你们是否考虑过这一点，以及随着智能体的出现这会发生怎样的变化。
<details><summary>Original English</summary>
**>>**: Yeah. One thing that uh is very important I feel like one of the endorsements you guys got was Pete Steinberger openclaw probably one of your top 0.001% 001 percentile users um like really pushing GitHub to its limits. I think one of his interesting pushes is the end of the pull request maybe. I don't know if you guys have considered that and how that changes with agents.
</details>

**>>**: 是的，确实如此。我认为，Peter 和他的团队共事起来非常棒，他们不断督促我们变得越来越好，这正是我们所欢迎的，对吧？因为技术在飞速发展，我们希望不断迭代、不断构建，所以当新的范式出现、新的工作方式诞生时，我们将继续演进、适应并改变这个平台，对吧？因此，如果这些概念中的某一个不再有用，或者大家不希望它是强制要求的，那完全可以做成可配置的，对吧？

但请记住，面对 2.25 亿开发者，有大型企业、小型团队、学生等等，我们必须提供一个包含多种概念的平台，然后你可以将这些概念组合在一起，以任何你喜欢的方式去开展工作，对吧？我自己也有一些用来折腾和摆弄的仓库，我就不用 PR，对吧？对我来说，我就是不断地把想法倒进去，就是不停地构建、构建、构建、构建，我不想去处理 Issue 或者 PR 之类的东西，对吧？所以同样地，平台应该允许并为这些方式提供支持，我们会持续去适应。
<details><summary>Original English</summary>
**>>**: Yeah, absolutely. So I think you um Peter and team are just wonderful to to work with and it's great they keep pushing us to get better and better and better and that's what we we welcome right because the technology is advancing rapidly and we want to keep iterating we want to keep building so as like new paradigms come up and new ways of working arise we will keep evolving and adapting and changing the platform right so if one of these concepts is not useful or people don't want it to be required like that can be configurable right but remember across 225 million developers big enterprises small you know students etc we do have to provide a platform with many concepts and then you should be able to assemble these concepts together and however you want to do work right there's repos I have that I tinker with and play with you know and I don't do PRs right and to me I just like I'm just constantly just firing in ideas and I'm just like building building building building and I don't want to deal with issues or PRs anything right so again the platform should allow and have the affordances for these things so we'll keep adapting
</details>

### 代码定义的演化与企业遗留资产

**>>**: 是的，是的。这很有意思。还有一种观点是，代码或许是一种凌驾于最终运行的可执行软件之上的抽象。在你的主题演讲中重点展示的仓库之一，是我的一位演讲嘉宾 Matt Pocock 的项目。
<details><summary>Original English</summary>
**>>**: yeah yeah so it's interesting I also there's an concept of maybe code is an abstraction above just the executable software that gets run um one of your repos that you featured on your keynote very prominent was one of my my speakers, uh, Matt PCO.
</details>

**>>**: 嗯哼，是的。
<details><summary>Original English</summary>
**>>**: Uhhuh. Yes.
</details>

**>>**: 里面就是一个 markdown 文件夹。全是 markdown。
<details><summary>Original English</summary>
**>>**: Who it's a it's a markdown folder. It's just markdown.
</details>

**>>**: 但这确实引发了我的思考，比如你看 GitHub 会对语言进行细分，说“噢，这个仓库有 76% 是 Rust”——
<details><summary>Original English</summary>
**>>**: And but like it does make me think like you know how GitHub has the the whole like language breakdown like oh this this repo is like 76% Rust
</details>

**>>**: 50% 都不再重要了，对吧？那么，到底什么是仓库？甚至什么是代码？我们究竟在存储什么？对吧？因为——
<details><summary>Original English</summary>
**>>**: 50% doesn't matter anymore, right? So like what is a repo? What is what is code even? What are we storing? Right? Because like
</details>

**>>**: 你需要的远不止可执行文件本身。
<details><summary>Original English</summary>
**>>**: you need much more than just the executable file.
</details>

**>>**: 是的，我认为依然存在大量的内容。我同意你的看法。但我认为目前也依然存在着海量的代码，想想所有用 Java 和 .NET 编写的代码，它们今天支撑着关键业务的庞大运转，对吧？所有这些系统都处于需要你进行安全修复、进行现代化改造、持续优化和修复 Bug 的过程中。

所以请记住，它涵盖了许多不同类型的内容和文本，其中一些东西已经存在几十年了，对吧？而有些东西在我们谈话的当下正在被验证并推向生产环境，对吧？这就是我认为工具必须具备灵活性、必须提供丰富选择的地方，对吧？我们也关心并且坚信开发者需要选择权，对吧？我自己就是开发者。我对某些事情非常挑剔，我希望拥有特定的东西，因为在某种程度上，这体现了我的个性，或者说是我通过所使用的工具表达的一种技艺。
<details><summary>Original English</summary>
**>>**: Yeah, I think there is still a lot. I agree with you. I think that there's still also a lot of code that exists and you think about all of the code that's been written in Java andnet that's running businesscritical massive businesses today right so those are all in the process of like you know you have to make security fixes you're modernizing them you're still optimizing them you're still bug fixing them so remember it's you know spanning a lot of different types of you know content text and some of these things are decades old, right? And some of these things are being viodated into production while we're talking, right? So that's the I think where the tools have to be flexible and there's lots of choice out there, right? And we also care and believe that developers need choice, right? I'm a developer. I'm finicky about certain things and you know, I want certain things because I have in some ways like my personality or there's a craft that I have that I express using with the tools that I use.
</details>

### Copilot Harness 与多模型路由技术 Fusion

**>>**: 没错，完全是这样。我还想探讨另外几个问题。关于 Fusion，这是一件大事。在我看来，它就像是 Harness（测试装配/编排工具）的某种元抽象。比如 Copilot 是第一个 Harness，至今已经三年了，或者四年？
<details><summary>Original English</summary>
**>>**: Yeah, that's right. That's right. Um, a couple other things I wanted to hit on as well. Fusion, very big deal. Uh, to me it is like uh the sort of meta abstraction of what a harness is. Like co-pilot was the first harness uh in you know uh three years now, four years, four years maybe.
</details>

**>>**: 大约四年左右。
<details><summary>Original English</summary>
**>>**: Fourish.
</details>

**>>**: 是的。但是在其最核心的层面，一个 Harness 的根本任务就是充分发挥模型的能力，而其中非常核心的一部分就是模型路由。你能不能深入探讨一下，为什么在那个领域建立领导地位对你们来说如此重要？
<details><summary>Original English</summary>
**>>**: Yeah. and and and but like the really the core job of a harness at its very very root is like making the most out of the model capabilities and at at you know very part of it is is model routing. Uh can you dive a little bit more into that uh why it's so important for you to establish like leadership in that area?
</details>

**>>**: 好的，这里有几点，我想把其中的几件事联系起来。今天我们谈到了一些，并且发布了更多关于 Copilot Harness 的信息；我们在这个 Harness 上已经投入了一段时间。我们认为这很重要，其中的 SDK 部分也是如此，因此你可以拿走那个 SDK 并用它去构建其他应用程序，对吧？我自己做过，很多人也都做过。那个 Harness 本身支持一系列不同的功能，但它背后的核心原则之一就是多模型，对吧？你也可以决定从哪个环节接入该 Harness。

首先，它支持多模型，我们一直在做工作让那个 Harness 变得越来越好，你必须根据行业现状去调整它，对吧？比如 MCP、编程所需的其他工具，或者新引入的不同模型。Harness 已经就位，接下来你需要一定的智能化能力，知道如何接纳一个任务、一段 Prompt 或一个最终将转化为完整软件工作单元的项目，将其进行拆解，并在某种程度上为你这位工程师分担认知负荷——毕竟面对这些在性价比等方面各不相同的模型，系统可以说：“嘿，我们可以直接为你进行优化。我们可以非常快速、以便宜得多的成本为你提供最佳质量。”

因此，我们将继续在此基础上进行迭代。我们还有很多想法。我们会继续让它变得更好。不过在我看来，这就好比 Harness 和 Fusion 在共同协同起伏，因为你正在解决的恰恰是开发者的那种工作需求——对所有工具以及你工作方式的编排，但你同时也需要 Fusion 来帮助你确定使用哪个模型，因为当下的选择实在太多了。
<details><summary>Original English</summary>
**>>**: Yeah, so a few things here which is one is we have and I would connect a couple things here. We've talked a little bit and released more information today about the the copilot harness and that harness as we've been working on it for a while. We believe it's important the SDK part of it is yes and so you can take that SDK and go build other applications with it right and I've done that and lots of people have as well and that harness itself supports a bunch of different things but one of the key tenants principles behind it is multi-model right and you can kind of decide where you want to plug into that harness as well so one is it does support and we constantly are doing work to make that harness better and better and better and you have to adapt it right based on what's happening MCP other tools that you need for coding or other things different models that come in as well so the harness is there then you need some intelligence around how to take a task take a prompt take some item that is going to be some eventual unit of completed software work and dissect that and take in some ways the cognitive load off of you as an engineer that has all of these models that are different price performance and stuff like that and say, "Hey, we can just like optimize that for you. We can get you the best quality really fast and much more cheaply." So, we'll keep iterating on this. We have lots more ideas. We will continue to make this better. The way I see it though is like you think about the harness and fusion kind of ebbing and flowing together because you're solving exactly that problem or that kind of job to you know job for the developer is that orchestration of all the tools the way you're doing your work but you want to have fusion which helps you figure out which model because there's so many choice today.
</details>

### 全端协同与上下文智能沉淀

**>>**: 是的。我认为模型选择非常重要，显然 Satya 也来过我们的播客，并在节目中把这作为微软日益明确的信号进行了探讨。另一件我非常喜欢的、你们正在推进的事情，是基本上把 Copilot 覆盖到了每一个界面。你们有一个很棒的移动端应用，还有桌面端应用，你们都展示了。

我在这里的问题是：你觉得有必要在这些方面进行创新吗？或者说，它基本上只是别人已有的东西的微软品牌版本？对吧？就像你们必须在 UI 上创新，还是只要在模型层做好就足够了？
<details><summary>Original English</summary>
**>>**: Yeah. Um and uh I think that model choice is very important and I think I've obviously had Satia on on the podcast actually here uh to talk about that as an increasing message of Microsoft. One other thing I really like that you guys are working on is like basically co-pilot across every surface. Um you have a great mobile app uh desktop app you guys showed it. My question there is do you feel the need to innovate there or is it basically just the Microsoft branded version of what other people also have? Right? like do you have to innovate on UI or can you just be good at the model layer and you're you're fine.
</details>

**>>**: 我认为两者都需要。在某种程度上，这正是我今天所谈到的很多内容：对每一层进行演进。这包括底层深度的低阶基础设施、存储、计算、网络、安全等一切；然后是平台层，我们讨论了 Git，还有 Actions、AI 网关，以及当今驱动 Git 的众多其他服务；再往上是工作流，以及不同的交互界面。因此，我认为把所有这些都做好非常重要，因为在很多方面，这就是所谓的“铺就之路”（paved path）。所以对我们来说，技术栈的每一层都需要创新和演化。

我还想补充另一件事：当你使用我们的交互界面时——比如 GitHub Copilot 应用程序、VS Code 或是网页端 GitHub.com——现在它们全部通过相同的 Harness 紧密连接在一起。这非常强大，因为你可以在手机上发起一个任务，然后在桌面端或在其他地方的笔记本电脑上接续处理并继续工作；或者你想到了另一个点子，直接随手输入到手机里，它就会继续执行下去。

但至关重要的是，所有的上下文都与你保持在一起，对吧？保留在你的仓库、你的 Issue、你的 PR 以及你的安全检查结果中。无论你使用哪种模型都没关系——你可以换用不同的模型，但所有的上下文、记忆、偏好以及我今天早上提到的那个智能引擎，都在一个地方为你持续复利累积。而在今天，如果你使用不同的其他工具，假设你在这里使用一个提供商的工具，然后切换到另一个，它们的智能是无法彼此复利叠加的，对吧？所以这就是我们希望解决的问题：你应该能够完成越来越多、源源不断的工作，而且对你来说会更便宜、更好、更快，因为你正在利用我们平台和工具的威力，但你依然保留了极大的自定义空间。你可以使用不同的模型，可以使用 Fusion，也可以使用其他工具。
<details><summary>Original English</summary>
**>>**: I think it's both and I think it's you know innovation at the is in some ways what I in many ways what I talked about today it's like evolving every layer and that's like the deep down low-level infrastructure and storage and compute and network and security and everything and then think kind of platform so we talked about git and there's actions and there's the AI gateway and there's lots of other services that power git today and then you have kind of workflows you have the different surfaces as well So I think it is important to have that all be great because that is a in many ways a paved path so to speak. So for us it is innovation and evolution at every layer of the stack and the the I would say a couple of maybe one other thing which is when you're using our surfaces like the GitHub copilot app or VS code or you're in.com. Yes. Now they're all connected using the same harness. So that's like really powerful because you can be firing something off on your phone and then you can pick it up on your desktop or you know your your laptop somewhere else continue work or hey I have this other idea let me just like pop it into my phone and and it will keep going but it is important that all that context stays in with you right in your repo in your issues in your PRs in your security findings and it doesn't model it doesn't matter which model you're using you can use different models, but all that context, the memory, the preferences, that intelligence engine that I talked about this morning, it's all compounding for you in one place. Today, if you're using different other tools, there is no way if you're using one tool from one other provider here and then you flip to another one, they don't compound their intelligence together, right? So that's what we want to try to solve is like you should be able to get more and more work done and it's going to be cheaper, better, faster for you because you're using the the power of our platform and our tools, but you can still customize it quite a bit. You can use different models, you can use Fusion, you can use other tools as well.
</details>

### 安全防线与开源供应链

**>>**: 是的，太棒了。我想留到最后探讨的一个板块是我们刚才提到的安全方面的内容。你们承担着巨大的责任，尤其最近随着 PHP 相关事件的发生，安全显然是大家最关注的焦点。
<details><summary>Original English</summary>
**>>**: Yeah. Amazing. Um, one part I wanted to leave towards the end was the security stuff that we alluded to. you have you have uh enormous uh responsibility and I think it's very top of mind obviously recently with the PHP stuff as well.
</details>

**>>**: 你们希望大家了解 GitHub 正在为大家做些什么？
<details><summary>Original English</summary>
**>>**: Um what's going like what do you want people to know just in the general like what GitHub is doing for people.
</details>

**>>**: 是的。我们在这方面做了大量工作，但依然任重道远。这里有几点。首先从产品或功能的角度来看：我们谈到了正在推进的一系列措施，比如现在我们推出了 Code Review Max，它应该能帮助发现代码中严重程度更高、更隐蔽的 Bug 等等。这一点非常关键，因为我们正在生成多得多的代码，我们必须确保代码质量标准不会滑坡。像代码审查、Copilot Code Review 这样的功能可以帮助你维持这一质量标准。

第二点是我们在安全方面所做的一切以及 GitHub 高级安全（Advanced Security），现在那里引入了 AI 扫描技术；就像我们在主题演讲演示中展示的那样——
<details><summary>Original English</summary>
**>>**: Yeah. So, lots of work going on here. We still have lots of work to do. A few things here. One from a product or a feature perspective. We talked about a number of things that we're doing around like now we have code review max and that should, you know, even help find higher severity, more obscure bugs in the code, etc. So, really important to make sure we're generating so much more code. We want to make sure the quality bar doesn't slip. things like code review, copilot code review help you maintain that quality bar. Second would be everything that we're doing in security and GitHub advanced security and now having AI scan scanning technology there and like we showed in the keynote demo where
</details>

**>>**: Damien 不小心推送了一个 Secret 密钥，对吧？但系统直接阻止了它被提交进仓库。所以我们在这里做了更多的工作，通过深度扫描不仅可以查找表面层次的漏洞，我们还将持续推出更多能力。今天有许多深入的研讨会，让你能够将更复杂的 AI 扫描引入到工作流以及软件交付方式中。

然后正如我们谈到的，微软安全团队与 GitHub 安全团队之间展开了大量的协作，既包括对平台进行加固，也包括与外部的开源维护者合作，开展大量工作来限制 npm 等包管理器的风险暴露，引入时间延迟，并下架已被攻陷的仓库。我们正在那里进行大量的持续性工作，每天都在与社区、开源项目和维护者合作进行改进；整个微软也在投入资金进行安全加固，这毫无疑问是每个人最关心的头等大事。
<details><summary>Original English</summary>
**>>**: Damian pushed a secret you know by accident right but it blocked it from even getting entered into the repo. So we have a lot more happening here deep scanning that can look for you know not just sort of the surface level vulnerabilities but we'll keep we have a lot of stuff coming here there was a number of deep dives today that workshops so you can plum in more of the more sophisticated AI scanning into your workflow into the way you need to deliver software and then there is a lot of collaboration going on as we talked about between Microsoft security team and the GitHub security team both on like hardening the platform but also working with maintainers open source out there doing a bunch of work on like limiting the exposures of package managers like npm right now and you know having time delays and taking down uh you know repos that have been compromised and so a lot of ongoing work there kind of daily improvements that we're doing working with the community working with the open source projects the maintainers and then all of Microsoft is investing in hardening this is much you know like it's top of mind for everybody.
</details>

**>>**: 是的，太棒了。考虑到安全与开源之间的关系，我脑海中一直在想一件事。我认为 GitHub 以及我们的开源供应链都是建立在“代码昂贵”这一前设之上的，而现在代码可能变得很廉价了。或许安全审查实际上也很廉价，可能保护我们系统最好的方式是把所有依赖全部内部化（vendor）或者重写一遍，因为重写很廉价，无所谓了，从而不再依赖开源。我不知道是否存在这种感觉，或者——
<details><summary>Original English</summary>
**>>**: Yeah. Amazing. I I think one thing that is on my mind in terms of the relationship between security and open source. I think GitHub and our supply chain of open source is predicated on the idea that code is expensive and maybe code is cheap now. Maybe security review is actually cheap and actually the best way to secure our systems is to vendor everything or rewrite everything because it's cheap like whatever. Uh and not rely on open source. I I don't know if there's like a like there's that field and then or there's like
</details>

**>>**: 存在那种观点。
<details><summary>Original English</summary>
**>>**: there's that opinion.
</details>

**>>**: 存在那种观点，即：“看，我的依赖项包括了每个人都在使用的 2000 个核心软件组件，它们全是暴露的脆弱攻击面，对吧？也许我直接把它们减少到 20 个。”我不知道你对此是否有看法，还是说这个想法太疯狂了。
<details><summary>Original English</summary>
**>>**: There's that opinion which is like well let's like my my dependencies are like 2,00 core pieces of software that every that everyone uses. they they're all vulnerably surface areas, right? Maybe I just reduce them to 20. Uh there's I don't know if you have a point of view on that or if that's too wild.
</details>

**>>**: 我不认为这太疯狂，因为我认为这确实是大家在考虑自身做法时常常会问我们的一个问题，对吧？我认为——
<details><summary>Original English</summary>
**>>**: I I think I don't think it's too wild because I think it is a question we get asked, right? In terms of what people are doing. Uh I think there are
</details>

**>>**: 我也不认为那是万灵药，对吧？因为，“嘿，我在系统里使用了 2000 个开源项目。我打算砍掉——
<details><summary>Original English</summary>
**>>**: I don't think that that's a panacea either, right? Because hey, I have 2,000 open source projects I use in my thing. I'm going to get rid of,
</details>

**>>**: 砍掉其中的 1980 个，保留 20 个使用；但另外那 1980 个现在必须由我自己来维护了，对吧？”
<details><summary>Original English</summary>
**>>**: you know, 1980 of them and then 20 of them I'll use, but the other 1980 I've got to maintain now, right?
</details>

**>>**: 所以，这属于你必须选择将资金、人员和时间投入到哪里的情况之一。此外我也认为，开源领域正在发生的事情极其重要且极具价值，我不认为这会停止。如果有任何变化的话，我认为开源对企业、构建者和创作者的价值从现在起只增不减。同样，我认为让我们去解决问题本身，即让开源中的内容变得安全，而不是让所有人都走向某种“围墙花园”的方式。
<details><summary>Original English</summary>
**>>**: So, it is one of those where you have to choose where you're going to like put your dollars, your people, your time. And I also think that there's just so much happening that's important and valuable in open source. And I don't think that's going to stop. If anything, I think the value of open source to businesses, to builders, to creators out there only increases from here. And again, I think let's solve the problem, which is like let's make the stuff in open source secure versus everybody going into like some walled garden approach.
</details>

### 未来展望：Azure 迁移、成本治理与硬件联动

**>>**: 好的。收尾的问题：我现在处于一个向大家征集预测的模式。到明年的这个时候，我们将从 GitHub 看到什么？
<details><summary>Original English</summary>
**>>**: Yeah. Um, so closing question. I'm in a business I'm in a mode of asking people for predictions. What are we going to see from GitHub by this time next year?
</details>

**>>**: 你会看到几件事：第一，我们将继续沿着今天讨论的道路走下去，那就是我们如何不断演进技术栈的每一层。这是一个伴随我们已久的主题，但我认为我们终于以某种方式将其整合在一起，讲述了从底层基础设施层一直向上的完整演进故事。
<details><summary>Original English</summary>
**>>**: You're going to see a few things which is one is we'll continue down this path that we talked about today which is how do we keep evolving every layer of the stack that's a theme that has been with us for a while but I think we finally put it together in some way to tell the story from the bottom kind of infrastructury layers all the way up to this
</details>

**>>**: 迁移到 Azure 会完成吗？
<details><summary>Original English</summary>
**>>**: will the move be to to Azure be done
</details>

**>>**: 计划是明年完成。明年——这是我们正在努力实现的目标，对吧？
<details><summary>Original English</summary>
**>>**: that's the plan next year next year that's a pretty what we're what we're aiming for right
</details>

**>>**: 听着，你今天看到了扩容图表，那真的非常狂野。
<details><summary>Original English</summary>
**>>**: and Listen, you saw the you saw the scaling graphs today. They're pretty pretty wild.
</details>

**>>**: 所以我们必须保持演进，我们必须保持快速推进，必须在技术栈的每一层都实现阶跃式的改进。我们会继续分享这些进展，因为我认为与社区分享这些非常硬核、有趣的工程挑战是极具意义的。

第二点是人们正在改变他们的工作方式，对吧？包括我们如何思考软件的构建、部署和优化。今天，我推测一年后的面貌会大不相同。它会是什么样子？我们届时是在管理成千上万个智能体，还是管理几十个、上百个？我不知道。因此，我们必须继续为平台构建正确的原语，以便你可以组合这些原语来适应你想要的任何工作方式，对吧？所以我们拭目以待，但我们会持续演进。你会看到基础设施规模方面的内容将是我们不变的主题。这些平台服务将如何演进，从而让你能够利用这些积木，按需搭建起符合你工作要求的一切。

我想说的另一件将更加受到关注的事：第一是安全，这我们已经讨论过了；第二就是 FinOps 之类的管理，或者说“嘿，我该如何管理我在 Token 上的全部花销？”因为这是当下非常热门的一个话题。
<details><summary>Original English</summary>
**>>**: And so we got to keep evolving. We got to keep moving fast. We've got to make step function improvements in every layer of the stack. So we'll keep sharing that because I think it's like really interesting hard engineering challenges to share with the community. Number two is people are changing the way they work, right? In terms of how we think about building software and deploying it and optimizing it. today. I'm guessing that it's going to look, you know, quite a bit different a year from now. And what does it look like? Are we managing thousands of agents versus, you know, dozens or hundreds? I don't know. So, we've got to continue to build the platform with the right primitives and so that you can compose those primitives for however you want to work, right? So, we'll see, but we're going to keep evolving. You'll see us infrastructure scale stuff will be a constant theme from us. what are these platform services that are evolving so that you can take these building blocks put them together for however you need to work. I would say another thing that is going to be more top of- mind is one security which we talked about two is just like POPS or like hey how do I manage all of my spend in tokens and you know because it is a it's a a very popular topic these days
</details>

**>>**: 而且你们展示了成本控制功能，这实际上是各家模型实验室不愿意做的事，因为他们希望你花得越多越好。
<details><summary>Original English</summary>
**>>**: and you guys showed off the cost control stuff that and that that is actually something the labs don't do because they want you to spend as much as you want.
</details>

**>>**: 我们还有很多别的内容[笑声]——我们会将其细化拆解：对于一个组织，这里展示了我们用来告知你花费情况的所有举措，这里展示了我们可以指导你优化支出的功能，比如提示：“嘿，你在这类使用场景中使用了这款模型，也许你应该换用另一款模型。”因此我们会在产品中持续提供优化建议；此外，特别是对于财富 500 强企业，他们需要治理，需要能够设定限额等等，所以我们必须在那方面提供相应的控制和治理能力。
<details><summary>Original English</summary>
**>>**: We have a lot of [laughter] other things where we break it down into here's you know for for an organization here's all the things that we do to inform you about your spend here's the things where we can guide you to like optimize your spend saying hey you're using this model for these types of use cases maybe you should use this other model so we will continue to make recommendations in the product and then for the especially the fortune 500 they want governance they want to be able to put in limits you know whatever so we have to provide the controls the governance there as
</details>

**>>**: 是的，作为公司领导者，我不介意你把我的钱花在 Token 上，只要向我证明这笔钱花得值就行。
<details><summary>Original English</summary>
**>>**: Yeah, as a company leader, I don't mind that you're spending my money on tokens. Just show me that it's spent well.
</details>

**>>**: 所以，关键在于我们如何帮助你以及其他许多人完成闭环：比如，“嘿，我这周在 Token 上花掉了 1000 美元，”
<details><summary>Original English</summary>
**>>**: So, that's how can we help you and lots of other people close the loop that, hey, I spent, you know, a,000 bucks on tokens this week.
</details>

**>>**: “然后如果你能说，‘嘿，我带来了 25000 美元的收入’，那你可能会觉得‘嘿，这挺不错。’”
<details><summary>Original English</summary>
**>>**: And then if you can say, hey, I generated $25,000 in revenue, then you may like, hey, that's pretty good.
</details>

**>>**: 我觉得谈收入有点太远了，作为程序员我并不直接对收入负责，对吧？但至少我交付了功能。我认为能够讲清楚这如何转化为某种投资回报率（ROI）——即便不是直接收入——
<details><summary>Original English</summary>
**>>**: I think revenue is a bit too like I'm not responsible for revenue as a coder, right? But at least I ship features. I think being able to talk about how that turns into some ROI, maybe not revenue,
</details>

**>>**: 成本节约，我们都知道成本——
<details><summary>Original English</summary>
**>>**: cost savings, we know cost,
</details>

**>>**: 成本节约，或者“嘿，这提高了用户参与度或留存率，或者提升了客户满意度（CSAT）”。这些都是可衡量的指标，作为产品团队和工程团队，你应该与这些结果指标挂钩。
<details><summary>Original English</summary>
**>>**: cost savings or hey, this increased engagement or retention or it improved seesat. These are all things that are measurable and as a product team and engineer team, you should be attached to these outcome metrics.
</details>

**>>**: 是的，太棒了。非常期待与你们保持长期的合作关系。祝贺又一届成功的 Universe 大会。
<details><summary>Original English</summary>
**>>**: Yeah. Awesome. Well, uh, looking forward to having a continuing relationship. Congrats on another successful universe.
</details>

**>>**: 非常感谢。我非常想夸奖一下设计 GitHub Universe 胸牌的人。就冲这个胸牌我也愿意来参加大会，因为——[笑声]——通常这些东西我转头就扔了。但我会把这个摆出来展示，通常这种东西会产生很多电子垃圾。但这其实是一个 Game Boy。
<details><summary>Original English</summary>
**>>**: Thank you so much. Something I really want to shout out is whoever did the GitHub universe badge. Like I would come to this conference just for this because [laughter] you these things I usually throw away. I display so there's a lot of like e-waste I guess from these. But this is a game boy.
</details>

**>>**: 它里面有一个小程序，实际上可以直接连到 GitHub Copilot。
<details><summary>Original English</summary>
**>>**: It has a little program it actually just hook it up to GitHub Copilot.
</details>

**>>**: 它是用 Copilot 做出来的。
<details><summary>Original English</summary>
**>>**: It was made with Copilot.
</details>

**>>**: 是的，它就是做出来的。
<details><summary>Original English</summary>
**>>**: Yes, it was made.
</details>

**>>**: 我告诉他们……好吧，快给我们讲讲把这一切整合起来背后的故事，因为很多开发者都想捣鼓硬件。而软硬件交互的接口，现在正是模型能够处理的事情，不需要我掌握其中的每一个微小细节。
<details><summary>Original English</summary>
**>>**: I told them to like Okay, well tell tell us the story about like putting putting all this together because a lot of developers want to tinker with hardware. Um and and the hardware software interface like that's something that models can do now that I don't have to know every little bit of.
</details>

**>>**: 应该亲自去试试看。
<details><summary>Original English</summary>
**>>**: Should try it out.
</details>

**>>**: 好的。
<details><summary>Original English</summary>
**>>**: Yeah.
</details>

**>>**: 好的，非常感谢你。
<details><summary>Original English</summary>
**>>**: Well, thank you so much.
</details>

**>>**: 谢谢，很高兴见到你。
<details><summary>Original English</summary>
**>>**: Thank you. Good to see you.
</details>

**>>**: 好的，谢谢。
<details><summary>Original English</summary>
**>>**: Yeah. Thank you.
</details>