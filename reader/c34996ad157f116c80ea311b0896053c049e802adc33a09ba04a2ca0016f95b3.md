---
author: How I AI
date: '2026-04-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=AI1FLDY3q5s
speaker: How I AI
tags:
  - customer-support
  - code-as-documentation
  - knowledge-management
  - workflow-automation
  - prompt-engineering
title: 非工程师如何利用Claude Code和多代码库高效解答客户问题
summary: 本期节目中，Galileo现场工程团队的Al Chen分享了如何利用Claude Code查询15个代码库和Confluence文档，为企业客户提供定制化的技术问题解答。这种方法不仅显著提升了客户体验，减少了对内部工程团队的依赖，还实现了动态、实时更新的知识库构建。访谈强调了在AI驱动的工作流中，人工审核和持续学习的重要性，以及如何通过AI将客户支持转化为更高效的价值创造循环。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Galileo
  - Anthropic
  - OpenAI
  - LangChain
  - Orcus
  - Tines
products_models:
  - Claude Code
  - GPT-4o
  - Conductor
  - Cursor
  - Pylon
  - ChatGPT
  - Google Secrets Manager
  - ClickHouse
  - GitHub
media_books: []
status: evergreen
---
### 利用代码库和AI解决客户问题

**Al Chen**: 我意识到我无法真正完成我的工作，是在我尝试参考我们的公开文档并提供答案时。它仍然无法给出我的客户正在寻找的答案。

<details>
<summary>Original English</summary>

**Al Chen**: The minute I realized I couldn't really do my job was when I was trying to reference our public documentation and trying to provide an answer. It just still wasn't coming up with the answer that my customers were looking for.

</details>

**Clarvo**: 他们不想要文档的答案。他们想要的是所有这些服务如何协同工作的分步解答。

<details>
<summary>Original English</summary>

**Clarvo**: They don't want the doc's answer. They want the step-by-step answer of how all these services cascade together.

</details>

**Al Chen**: 我意识到我实际上可以将所有这些代码库拉到我的 **VS Code** 中，现在我可以使用 **Claude Code** 来向我们整个代码库提问。

<details>
<summary>Original English</summary>

**Al Chen**: What I realized is that I can actually pull all of these repos into my **VS Code** and I can now use **Cloud Code** to ask our entire codebase questions.

</details>

**Clarvo**: 你是说 **Claude Code** 给我写了一个脚本来拉取所有这些东西吗？

<details>
<summary>Original English</summary>

**Clarvo**: Did you just say **Claude Code** write me a script that pulls all these?

</details>

**Al Chen**: 是的，是的，我正在我的 **VS Code** 中打开那个脚本。它大概有16行。我不需要自己写。我只是说帮我找到一种方法，将最新的主分支拉到我的本地代码库中。

<details>
<summary>Original English</summary>

**Al Chen**: Yeah. Yeah, I'm opening up the script right now. It's like what 16 lines. Didn't have to write this. I just said help me figure out a way to pull the latest main branches into my local repos.

</details>

**Clarvo**: 现实是，我们现在都可以生活在稍微多一点的混乱中，因为 **AI** 可以为我们跨系统导航所有信息，对吧？所以你可以在你的代码中查询 **Confluence**，它会找到信息。你不需要那么在意信息的存储位置和方式。

<details>
<summary>Original English</summary>

**Clarvo**: The reality is we can now all live in a little bit more chaos because the **AI** navigates all that information for us across systems, right? So you can be in your code querying **Confluence** will find the information. You have to be less precious about where and how you store the information.

</details>

**Al Chen**: 扔到 **Confluence** 里，扔到 **Notion** 里，扔到 **Slack** 里，随便哪里。当你尝试向 **Claude** 提问关于客户或你的代码库的问题时，这些最终都会成为你可以提供给它的上下文。

<details>
<summary>Original English</summary>

**Al Chen**: Throw into **Confluence**. Throw it into **Notion**, throw it into **Slack**, wherever. That ends up being context you can provide to **Claude** when you are trying to ask it a question about a customer or about your codebase.

</details>

**Clarvo**: 每次 **Claude Code** 正确回答一个问题时，我们都给它一点奖励吧。你得和 **Claude Code** 分享你的配额。

<details>
<summary>Original English</summary>

**Clarvo**: Let's give **Claude Code** a little spiff every time it answers a question correctly. You got to split your quota with **Claude Code**.

</details>

**Al Chen**: 是的，你给它越多钱，它给出的答案就越好，之类的。

<details>
<summary>Original English</summary>

**Al Chen**: Yeah, it gives you better answers the more bucks you give it or something.

</details>

**Clarvo**: 投币式 **Claude**。那将是我的新技能。

<details>
<summary>Original English</summary>

**Clarvo**: Coin operated **Claude**. That's going to be my new skill.

</details>

**Clarvo**: 欢迎回到《我如何AI》。我是 **Clarvo**，产品负责人，也是 **AI** 的狂热爱好者，致力于帮助大家更好地利用这些新工具进行构建。今天，我们有一期节目，专门探讨如何利用你的代码来极大地改善客户体验。**Galileo** 现场工程团队的 **Al Chen** 将向我们展示他如何使用他们的15个代码库和 **Claude Code** 来回答他遇到的每一个细致入微的客户问题，并利用这些让整个客户群和他的整个团队都更加满意。让我们开始吧。本期节目由 **Orcus** 赞助，该公司是开源 **Conductor** 的幕后推手，**Conductor** 为代理工作流中的现代企业应用提供复杂的流程编排。传统的业务流程自动化工具正在失效。孤立的低代码平台、过时的流程管理系统以及断开连接的 **API** 管理工具并非为当今 **AI** 驱动的世界而生。**Orcus** 改变了这一切。通过 **Orcus Conductor**，你将获得一个现代化的编排层，它具有高可靠性并能实时将人类、**AI** 和系统整合在一起。它不仅仅是关于任务，而是关于编排一切：**API**、微服务、数据管道、人工干预操作，甚至是自主代理。因此，你可以轻松构建、测试和调试复杂的工作流，同时保持企业级的安全性、合规性和可观察性。**Orcus**，编排未来的工作。访问 orcus.io 了解更多并开始构建。**Al**，感谢你加入《我如何AI》。我对这期节目非常兴奋，因为我们已经看到了很多关于将代码用作文档的例子。你知道，我们听过工程师说，文档和代码应该放在代码库中。产品经理说，代码现在可以成为我面向内部资产的文档，或者在我起草 **PRD** 时提供帮助。但你将向我们展示如何将代码作为资产来创建面向客户的内容并解决面向客户的问题。那么，当你决定克隆代码库并启动 **Claude Code** 来解决这些问题时，你面临着什么问题？

<details>
<summary>Original English</summary>

**Clarvo**: Welcome back to How I AI. I'm **Clarvo**, product leader and **AI** obsessive here on a mission to help you build better with these new tools. Today we have an episode all about harnessing your code to make your customers experience way better. **Al Chen**, who's on the field engineering team at **Galileo**, shows us how he uses their 15 repositories and **Claude Code** to answer every nuance customer question that comes across his desk and use that to make the entire customer base and his entire team a lot happier. Let's get to it. This episode is brought to you by **Orcus**, the company behind Open-source **Conductor**, which powers complex workflows and process orchestration for modern enterprise apps in Agentic Workflows. Legacy business process automation tools are breaking down. Siloed low code platforms, outdated process management systems, and disconnected **API** management tools weren't built for today's **AI** powered world. **Orcus** changes that. With **Orcus Conductor**, you get a modern orchestration layer that scales with high reliability and brings humans, **AI**, and systems together in real time. It's not just about tasks. It's about orchestrating everything. **APIs**, microservices, data pipelines, human in the loop actions, and even autonomous agents. So build, test, and debug complex workflows with ease. All while maintaining enterprisegrade security, compliance, and observability. **Orcus**, orchestrate the future of work. Learn more and start building at orcus.io. **Al**, thanks for joining how I AI. I am really excited about this episode because we've seen a lot about using your code as documentation. You know, we've heard engineers saying, you know, docs and code should be in the repo. Product managers saying code can now be my documentation for internally facing assets or as I help draft **PRDs**. But you're going to show us how you can use code as an asset to create customerf facing things and solve customerf facing problems. So tell me what what problem were you facing when you decided I'm just going to clone the repo and fire up **Claude Code** and solve some of these problems myself?

</details>

**Al Chen**: 当然。我在 **Galileo** 的现场工程团队工作，我处于与企业客户打交道的第一线，这些客户通常本身就是开发者，他们会提出非常深入的技术问题。我意识到我无法真正完成我的工作，是在我尝试参考我们的公开文档并提供答案时，即使使用 **Claude Code** 或 **ChatGPT** 等工具，并尝试整合所有这些帮助文档来找到答案，它仍然无法给出我的客户正在寻找的答案。我个人背景不是工程师，从未担任过工程职位，但我认为我懂的足以“危险”。我意识到我们的产品 **Galileo** 是一款针对 **AI** 应用的**可观察性工具**。如果你看这里这张图片，我展示的是我们平台所有不同服务的高级架构图。这都是客户需要部署到他们的 **Kubernetes** 集群上的后端镜像。我意识到所有这些不同的服务，比如 **UI API**、认证代码库，我们不是一个单一代码库，我们有多个不同的代码库。所以我意识到我实际上可以将所有这些代码库拉到我的 **VS Code** 中。最初这只是为了我自己，我想了解我们的代码是如何工作的，以及我们的代码结构是怎样的。但当我把所有这些都放到 **VS Code** 中时，就像你在这里看到的，左侧我打开了 **VS Code**，这些目录中的大多数都对应着我们架构中的一个服务。所以一个代码库对应一个服务。通过在我的 **VS Code** 中拥有所有这些代码库，我就可以使用 **Claude Code** 来向我们整个代码库提问，这些问题是我们的公开文档无法回答的。所以有时我会收到非常深入的问题，比如“这个功能到底是如何工作的？”于是我就会问 **Claude Code**，让它查看 **API** 代码库、认证代码库，并帮助我找到答案。如果找不到答案，就参考我目录中、我根目录中的其他代码库，帮助我找出答案。所以，关键的突破点就是我发现我可以获得更深入、更技术性的信息，同时我自己也能学习我们的代码库是如何工作的。这真正帮助我的是，我不再需要不断地在我们的团队工程频道中询问：“嘿，这个问题答案是什么？客户刚刚问我这个。”你可以想象，当我尝试发布这些问题，然后客户又问我一个后续问题，我又在 **Slack** 线程中发布那个后续问题时，工程师们会感到多么沮丧。所以，我相信许多在客户一线工作的人都明白那种感受。但我通过将所有这些代码库拉到我的本地 **VS Code** 中，基本上将所有这些都减少到了几乎为零。

<details>
<summary>Original English</summary>

**Al Chen**: Sure. Uh so working at **Galileo** on the field engineering team I'm on the front lines in terms of working with our enterprise customers who are typically developers themselves and asking very indepth technical questions and the minute I realized I couldn't really do my job was when I was trying to reference our public documentation and trying to provide an answer to my customers even by you even using **Claude Code** or **ChatGPT** or whatever and trying to take all these different help docs and trying to come up with the answer. It just still wasn't coming up with the answer that the my customers were looking for and I just background I'm not an engineer. I've never held an engineering role but I think I know enough to just be dangerous and I realized that our product **Galileo**'s product we're an **observability tool** for **AI** **AI applications**. If you look at this image here, I'm showing an architecture diagram high level of all the different services that make up our platform. This is all like backend images that you have to that customers have to deploy onto their **Kubernetes** cluster. And I realized that all these different um services like **UI API**, autho repo. We're not a mono repo. they have like multiple different repos. And so what I realized is that I can actually pull all of these repos into my **VS Code**. Initially was just more for me to like I wanted to understand like how our code works and how our code is structured. But then when I threw it all into **VS Code** which looks like here you notice along the left hand side I'm open **VS Code** now and most of these directories correspond to one of those services within our architecture. So one repo corresponds to one service. And by having all of these repos in my **VS Code**, I can now use **Claude Code** to ask my our entire codebase questions that are not answerable by our public documentation. And so sometimes I'll get really inep questions about, well, how does this feature actually work? And so I'll ask **Claude Code** look into the **API** repo, look into the auth repo and help me come up with an answer. If you can't find the answer, reference other repos within my directory, my my root directory and help me figure out the answer. And so that's the key unlock was when I figured out I could get way more in-depth, way more technical and at the same time myself I can learn qu learn how our codebase works. And how this has really helped me is I don't have to constantly ping our, you know, team engineering channel with, hey, what's the answer to this question? The customer just ping me about this. And you can imagine engineers being really frustrated when I'm trying to, you know, post these questions and then the customer asks me a follow-up and then I'm I'm posting that follow-up in the **Slack** thread. So, I'm sure many of you who are working on the front lines of customers understand how that feels. But I've basically reduced all that almost down to zero by pulling all these repos into my local **VS Code**.

</details>

**Clarvo**: 我非常理解这个问题，因为我以前在 **LaunchDarkly** 工作，负责产品和工程，那是一个非常技术性的产品。我们也有一个非常相似的架构图。而且，人们可能认为首席产品官（**CPO**）或首席技术官（**CTO**）是面向内部的。不不不，我们是销售人员。我们永远是销售人员。你把我们推出去，让我们面对客户或潜在客户，回答技术问题。我们也有那样的图表，我总是会收到那些需要非常详细答案的细致问题，比如你的缓存是如何工作的？你知道，当你的应用程序有七层缓存时，你可以给出高级文档的答案，但当你和一个架构师或一个技术专家坐在同一个房间里时，他们不想要文档的答案。他们想要的是所有这些服务如何协同工作以构建一个弹性缓存机制的分步解答，举个例子。我只是觉得，在会议中或在邮件往来中，能够不只是给出这种高级别的答案，而是能够查询当前的**代码库**并真正详细地了解它是如何工作的，这有多么强大。我认为“当前”非常重要，因为你知道，代码库总是随着时间演进的。所以即使你一个月前得到了正确的答案，也许你的团队发布了更新，或者那个方法实际上已经过时了，或者文档有点过时了。所以我确实认为，因为代码库，至少你的主分支，永远是**事实的单一来源**，它成为了一个非常可靠的上下文集，供你回答关于产品如何运作的问题。

<details>
<summary>Original English</summary>

**Clarvo**: I'm really empathetic to this this problem because I you know I used to work at **LaunchDarkly** leading product and engineering very technical product. We too had an architecture diagram that looked very similar to that and again as a more of a you know people think that **CPOs** chief product officers or **CTOs** are internal facing. No no no we're sales people. We're always sales people. you trot us out and you put us in front of the customer or you put us in front of the prospect to answer the technical questions and we had a diagram like that and I would constantly get these very detailed questions that required very detailed answers like how does your caching work and you know when you have seven layers of caching in your app you can give the highlevel docs answer but when you're sitting with you know an architect in the room or somebody highly technical they don't want the docs answer. They want the step-by-step answer of how all these services cascade together to build a resilient caching mechanism, for example. And I just think how powerful is it to be in a meeting or in an email back and forth and not just sort of give this high level, but be able to query the current codebase and really understand at a detailed level how it works. And I think current is very important because you know and I know this is always evolving over time. So even if you got the answer right you know a month ago maybe your team shipped an update or maybe you know that method is actually out of date or the docs are a little bit out of date. So I do think because the codebase is you know at least your main branch is always the **source of truth** it becomes a really reliable you know uh context set for you to answer questions about how the product operates.

</details>

### 保持代码库最新

**Al Chen**: 是的。关于你说的代码显然总是在不断演进的评论，我想快速回应一下。我们每天都会推出多个功能，多个版本。我用 **Claude Code** 写了一个脚本，放在我的根目录里，它叫做“pull all”，我不确定其他人是否也这样做，但它会把我的根目录中所有代码库的主分支拉到我的本地。所以如果我每天都运行这个脚本，我就能在我 **VS Code** 左侧的所有这些目录中获得最新的代码。我之前有几周是手动操作的，我意识到那是在每个目录上都执行 `git pull origin main`，这根本无法扩展，因为现在有大约15个不同的代码库我需要拉取最新代码。所以这就是我如何解决代码库不断演进的问题，以确保我总是能为客户提供最新的信息。我必须问，你刚才是不是说 **Claude Code** 给我写了一个脚本来拉取所有这些？

<details>
<summary>Original English</summary>

**Al Chen**: Yeah. And to quickly address your comment about how your code is obviously always evolving. I mean we're pushing out you know multiple features per day, multiple releases. And one thing I've done wrote this with **Claude Code** is I have this script at my root directory that says like I just do something called pull all and this I'm not sure if this is how other people do it but it just pulls the main branch into my repo for all the repos in my root directory. So if I do this every day I kind of get the latest code across like all these directories on the lefth hand side of my **VS Code**. So it the alternative which I was doing before for like a few weeks and I realized this is just as I'm doing this is doing `git pull origin main` on every single directory and it was just like not scalable because there's now like 15 different repos I have to pull the latest from. So that's kind of how I solved the codebase is always evolving problem to make sure that I'm always getting the most up-to-date information for my customers. And I have to ask, did you just say **Claude Code** write me a script that get pulls all these?

</details>

**Clarvo**: 哦，是的，是的，是的。我完全不知道。我正在我的 **VS Code** 中打开那个脚本。它大概有16行。我根本不需要写这个。我只是说“帮我找到一种方法，将最新的主分支拉到我的本地代码库中”，它就一次性完成了。

<details>
<summary>Original English</summary>

**Clarvo**: Oh yeah, yeah, yeah. I I have no idea. This is the I'm I'm opening up the script right now in my **VS Code**. And it's like what 16 lines. I have didn't have to write this. I just said help me figure out a way to pull the latest main branches into my local repos. And it just did it in like one shot.

</details>

**Clarvo**: 是的。当我看着你的屏幕时，我想向大家指出另一件事，我认为人们没有充分利用这个技巧，那就是在 **VS Code**、**Cursor** 以及你使用的任何 **IDE** 中。如果你想回答跨产品的问题，以多代码库级别而不是单个代码库级别加载项目非常重要。所以，你知道，在查询所有这些代码库和文件时，可能会出现一些上下文膨胀的问题，但如果你必须一个接一个地进入每个代码库进行查询，然后再进入另一个进行查询，那会非常痛苦。所以我喜欢这种在 **IDE** 中同时打开所有代码库的想法，这样当你使用 **Claude Code** 或 **Cursor** 等工具进行查询时，它就可以跨代码库进行遍历，并真正为你提供高度情境化的答案。是的，我们的代码库恰好是多个代码库，但我只是把它们都拉到这个巨大的 **Galileo** 目录中。所以所有东西都在同一个父级下，但如果你在一个单一代码库（**monorepo**）中，呃，是的，实际上我不知道这在单一代码库中如何与 **Claude Code** 配合使用，因为我从未在单一代码库中使用过 **Claude Code**，但至少对于我们 **Galileo** 来说，它是这样运作的。

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. The other thing I want to call out for folks as I'm looking at your screen is I don't think people use this trick enough which is in **VS Code** in **Cursor** and whatever your **IDE** is. Um loading a project at the multi-reo level as opposed to at the individual repo level if you're trying to answer questions across the product is really important. So, you know, there's some like context bloat stuff that can come into sort of querying across all those repos and all those files, but it would be very painful if you had to go into each of these repos one by one and like query and then go into the other one and query. And so I like this idea of opening them all jointly in in in your **IDE** so that when you're querying it with **Claude Code** or you're clearing it you know with something like **Cursor** um it can have it can it can go across traverse across repos and really give you highly contextualized answers. Yeah, our code bases happens to be in multiple repos, but I just pull them all into this like giant **Galileo** directory here. And so everything is like at the same parent, but yeah, if you're in a monor repo, uh could be yeah, actually I don't know how this would work with monor repo because I've never done it with monor repo with **Claude Code**, but um at least for us at **Galileo**, this is how how it works.

</details>

**Al Chen**: 嗯，我有很多单一代码库，是的，你只需在正确的级别打开它。我想说，我对大家的建议是，在正确的级别打开 **Claude Code** 或你的 **IDE**，有时它很窄，有时你需要向上一个目录。我认为真正思考这一点，你甚至可以根据你正在尝试解决的问题来情境化地进行操作，对吧？嗯，我认为这样做真的很有帮助。你能否向我们展示一下，仅仅使用 **Claude Code**，你可以用这个代码上下文回答什么类型的问题？

<details>
<summary>Original English</summary>

**Al Chen**: Well, I have a many monor repos and yeah, you just open it at the right. I would I would say my advice to folks is open **Claude Code** or open you know your **IDE** at the right level and sometimes it's narrow and sometimes you need to go up a directory and I think really thinking about that and you can even do that contextualized to the problem you're trying to solve right um and and doing that I think is really helpful could you show us just using **Claude Code** what kind of question you could answer with this code context

</details>

### 定制化部署方案

**Al Chen**: 我会给你一个例子，嗯，我是一个非常相信使用快捷方式的人。所以我使用了一堆自定义的 **Claude Code** 命令来帮助我完成工作。我经常做的一件事是帮助客户将 **Galileo** 部署到他们的 **VPC** 上。所以我有一个叫做 **DPL** 的自定义命令，它实际上会引用我们的，它做的第一件事是查看我们的 **Confluence**，因为我们有很多关于如何使用不同的镜像等部署到 **Kubernetes** 的 **Confluence** 页面。所以我会说“**DPL** 我的客户不能使用 **CRD**，他们正在使用 **Google Secrets Manager**，并且想要部署 **wizard** 镜像，给我一个分步的部署过程。”这实际上不是一个非常有代表性的查询，因为实际的查询比这详细得多，我也会提供更多的上下文，但我希望 **Claude Code** 首先关注 **Confluence**，因为我知道那里有很多部署相关的内容，然后如果找不到答案，它就会去我的 **Claude Code VS Code** 左侧的所有不同代码库中寻找答案。所以现在它正在使用 **Lassie** 和 **MCP** 从 **Confluence** 中提取信息，然后将其与我们的代码库结合起来，回答一个非常深入的部署问题。

<details>
<summary>Original English</summary>

**Al Chen**: I will um give give you an example of um I guess um I'm a big believer in using shortcuts too. So I use a bunch of custom uh **Claude Code** custom commands to help me do stuff. So one thing I do a lot is helping my customers deploy **Galileo** onto their **VPC**. So I have a a a custom command called **DPL** which is it actually references our the first thing it does is it looks at our **Confluence** because we have a whole bunch of **Confluence** pages about how to deploy into **Kubernetes** using our different images and stuff like that. So I'll say **DPL** my customer um cannot use **CRDs** and they are using **Google Secrets Manager** and want to deploy the **wizard** image give me a stepbystep process on how to do it. This is actually not a super representative um query because they're way more detailed than this and I provide a lot more context but I want **Claude Code** to to focus on um looking at **Confluence** first because I know that we have a whole bunch of deployment stuff there and then from there if they can't find the answer it will go off into all the different repos along the lefth hand side of my **Claude Code VS Code** to find the answer. So right now it's just using the **Lassie** and **MCP** to pull information from **Confluence** and then marries that with like our codebase to answer a very kind of in-depth um deployment question.

</details>

**Al Chen**: 有一件事，嗯，我确定我们现在是否应该谈论这个，但我开始在 **Confluence** 中做这件事，我们有一个我们称之为“客户怪癖”的页面。这些是我们所有企业客户的各种情况，他们通常有**气隙环境**。所以他们有所有这些安全措施，我们在将产品部署到他们的环境中时必须遵守。所以我确实有一个看起来完全像这样的页面，我在顶层列出客户的名称，然后是一堆项目符号，比如他们如何存储他们的**秘密**。他们如何处理**命名空间**。你知道，他们如何处理**边车**和**服务到服务加密**。这些我一无所知的事情，但是当我与客户会面时，我把所有这些都放到了这个 **Confluence** 页面中，这个不断增长的 **Confluence** 页面，然后这实际上是进入 **DPL** 自定义命令的核心页面之一，它会查看“客户怪癖”页面，如果我提到一个在该页面上的客户，它就会查看他们的所有怪癖，然后 **Claude** 的回复就会高度定制化，高度适应他们的环境，因为我从与我们的 **DevOps** 团队合作中看到，我们可以为客户提供关于 **Kubernetes** 或 **ClickHouse** 或其他任何东西的通用答案，但这就像你通过 **Google** 或使用 **AI** 就能在线找到的东西。但当它根据特定的安全要求和部署要求进行定制时，它会更有效，并且能让客户更信任我们知道自己在做什么。本质上。

<details>
<summary>Original English</summary>

**Al Chen**: The one thing um I'm not sure if we should talk about this now but I started doing um this in **Confluence** where we have a we call it a customer quirks page. These are all kinds of all of our enterprise customers you typically have **airgapped environments**. So they have all these security measures and we have to abide by them when we deploy the pro the product into their their environment. And so I literally have a page that looks exactly like this where I have the customer's name at the top level and then a bunch of bullet points with like you know here are some things about how they store their **secrets**. Here's how they do **name spaces**. You know here's how they handle **side cars** and **service service to service encryption**. the things I have no I know nothing about but um as I'm meeting with my customers I'm putting this all into this this one **Confluence** page this ever growing **Confluence** page and then this is actually one of the core pages that goes into this uh **DPL** custom command which is look at the customer quirks page if I'm mentioning a customer that's on that page look at all their quirks and then in the response from **Claude** it's highly customized highly tailored to their environment because I've seen from working with our **DevOps** team that we can provide a generic answer about **Kubernetes** or about **ClickHouse** or about whatever for the customer, but it's like something you can just find online by googling or using **AI**. But when it's tailored to specific security requirements and deployment requirements, it it's way more effective and just gives the customer more trust that we we know what we're doing. Essentially

</details>

### AI驱动下的知识管理

**Clarvo**: 我喜欢你在这里展示的，它结合了代码库和 **Confluence MCP**，既有团队生成的一般文档，也有你在客户层面生成的微文档。在我20年的企业 **SaaS** 经验中，我经常听到“这个信息的**事实的单一来源**是什么？”我相信你也听过，比如“**XYZ** 是如何工作的**事实的单一来源**是什么？”或者“这个客户的**事实的单一来源**是什么？”人们花费了大量时间来修剪这些 **Confluence** 花园，组织他们的 **Slack** 频道，并试图让人们正确使用命名约定。而现实是，我们现在都可以生活在稍微多一点的混乱中，因为 **AI** 可以为我们跨系统导航所有信息，对吧？所以你可以在你的代码中查询 **Confluence**，它会找到信息，你可以把它指向正确的方向，它就能找到信息。你不需要那么在意信息的存储位置和方式。无论是怪癖的要点列表，还是非常正式的文档，都无所谓。因为 **AI** 在遍历所有这些信息、提取信息并使其对你可操作方面，效率要高得多。我不认为有哪个人类会为此感到骄傲，说自己擅长找到正确的 **Confluence** 文档。那从来都不是附加价值。

<details>
<summary>Original English</summary>

**Clarvo**: what I love about what you showed here which is you know kind of combining the repository with the **Confluence MCP** and then both like team generated general documentation as well as you generated like micro documentation at the customer level is I've heard so often in my 20 years in enterprise **SaaS** like what is the **source of truth** for this information like I'm sure you've heard this too like what's the **source of truth** for how **XYZ** works or what's the **source of truth** for this customer and people have spent so much time like you know pruning these **Confluence** gardens and organizing their **Slack** channels and trying to get people to you know get naming conventions right and like the reality is we can now all live in a little bit more chaos because the **AI** navigates all that information for us across systems right so you can be in your code querying **Confluence** it will find you can kind of point it in the right direction it find the information. You have to be less precious about where and how you store the information. Bullet point list of quirks, you know, like really official docs, whatever. It doesn't matter because **AI** is just so much um more effective at traversing all that information and pulling it in and making it actionable for you. And I don't think that's anything like any human was really proud that they were good at. They're like, I'm really good at finding like the right **Confluence** doc. Uh that was never never the value ad.

</details>

**Al Chen**: 是的，是的。我的意思是，我认为，即使只是简单地，嘿，你在 **Slack** 中，比如在一个非常活跃的 **Slack** 线程中，找到了一个非常棒的答案，把它扔到 **Confluence** 页面或者保存那个 **Slack** 线程，因为我也使用 **Slack MCP** 来总结线程。所以，如果你有一些随机的、持续的意识流文档，你希望 **Claude Code** 扫描，我只会说把它扔到 **Confluence**，扔到 **Notion**，扔到 **Slack**，随便哪里。然后当你试图向 **Claude** 提问关于客户或你的代码库的问题时，这些最终都会成为你可以提供给它的上下文。

<details>
<summary>Original English</summary>

**Al Chen**: Yeah. Yeah. I mean, I think um even if it's as simple as, hey, you you've came come across a really great answer in **Slack**, like in a really engaging **Slack** thread, throw that into a **Confluence** page or save that **Slack** thread because I also use the **Slack MCP** to be able to summarize threads. So, if you have like just some random like just ongoing stream of consciousness of documents you want to have **Claude Code** scan, I would just say throw into **Confluence**, throw into **Notion**, throw it into **Slack**, wherever. And then that ends up being context you can provide to **Claude** when you are trying to ask it a question about a customer or about your codebase.

</details>

### 提升客户体验的竞争优势

**Clarvo**: 还有一件事，这可能要回到我介绍本期节目时所说的，那就是人们大量使用 **AI** 在产品和工程速度领域进行竞争。我的意思是，我们都在使用 **Claude Code** 来交付更多的产品。我们都在使用 **AI** 和编解码器来构建更好的用户体验，或更具弹性的后端，或诸如此类的东西。但还有一个完全不同的竞争领域，那就是你如何与客户建立关系。我认为你所展示的是，你实际上可以使用 **AI** 来投资并竞争客户体验。我的假设是，当你的非常复杂的企业客户看到你出现时，你不仅仅是说“这是我们部署这个产品的通用文档”，而是说“我听到了你的需求，我理解你的需求，这是你具体如何部署这个产品的定制文档，而且我已经预先考虑了你告诉我的所有问题。”你知道，从竞争的角度来看，这一定会给接收方带来更愉快的客户体验，并让你将自己定位为不仅拥有优秀产品，而且拥有一个能够很好地服务客户的优秀团队。

<details>
<summary>Original English</summary>

**Clarvo**: Well, and the other thing and this is maybe going back to how I introduced this episode which is people use **AI** so much to compete on the field of the product and engineering velocity. And what I mean by that is like we're all using **Claude Code** to ship more product. we're all using **AI** and codecs to build, you know, better user experiences or more resilient backends or any of that stuff. But there's also a completely different competitive field which is how you show up in your relationships with your customers. And I think you know what you're showing is you can actually use **AI** to invest and compete on customer experience. And you know, my hypothesis is when your very complex enterprise customers have you show up and you don't just say like here are our general docs to deploy this and instead you say I heard you. I understand what your needs are and here are your custom docs on how you specifically need to deploy this and I've already pre-thought about all the problems you've already told me about. you know, just looking like in a competitive sense, that's got to come across as a much more um enjoyable customer experience on the receiving end and allows you to position yourself not just as great product, but as a great team that's going to service your customers well.

</details>

**Al Chen**: 是的，我希望如此。我的意思是，我认为我们的客户，我的客户，希望能够享受我提供的答案以及我提供的深度。我想过把这推向极端，那就是我们有一些客户，他们非常深入细节，他们想立即知道一些事情。我实际上会把他们的问题拿过来，然后就说“我的客户问了我这个问题，因为他们看不到你的代码，但我 **Al** 能看到代码，帮我找到答案。”所以如果我把它推到逻辑的极致，那就像是“为什么我们不能直接和客户分享我们的代码库呢？”因为那样他们就可以直接查询我们的代码库来获得他们需要的答案，而不是我作为所谓的“中间人”。你知道，问题是我们的代码是专有的，诸如此类。但我看到过，**LangChain** 有一个案例研究，由于 **LangChain** 的许多代码库都是开源的，他们的支持代理机器人实际上做了很多我做的事情，但它能够查询所有公开的开源代码库。在座的任何尝试使用 **LangChain** 或 **LangGraph** 的人，你们都可以将所有这些代码库拉到你们的本地机器上，然后当然可以使用 **Claude Code** 或 **Cursor** 等工具提问。嗯，但我经历过那种思想实验，就像我仍然是回答客户问题的瓶颈，因为我掌握着我们代码的钥匙。但如果他们 somehow 拥有一个经过清理的版本，那么也许他们也可以自己回答他们的问题，因为他们也都在使用 **VS Code**、**Cursor** 和 **Claude**，只是他们没有我们的专有代码库。

<details>
<summary>Original English</summary>

**Al Chen**: Yeah, I I hope so. I mean, I think our customers I think my customers are hopefully enjoying the answers I provide and the in-depthness that I provide. I think I've thought about taking this to the extreme which is there we have certain I have certain customers who are like you know very in the weeds they want to know things like right at this very second and I'm literally taking their question and then just like saying my customer then asked me this because they can't see your code but me **Al** I can see the code help me get the answer and so if I take that to the logical logical conclusion it's like why can't we just share our repos with the customer because then they can just start querying our repos directly to get the answers they need instead of me as kind of like the quoteunquote middleman and you know the issue is that like our code is proprietary and all that kind of stuff but I have seen um there's actually a case study from **LangChain** and since a lot of **LangChain**'s um repos are you know it's open source like their support agent bot actually does a lot of things I do but it is able to query you know all the public open source repos And any of you out there who are trying to use **LangChain** or **LangGraph**, you can just pull all those repos down to your local machine and then ask questions of course using **Claude Code** or **Cursor** or whatever. Um, but I've got went through that kind of thought experiment of like I'm still kind of a bottleneck in terms of answering my customers questions cuz I kind of like hold the keys to our code. But if they somehow had had a sanitized version of it, then maybe they could just self-answer their questions too because they're also all using **VS Code** and **Cursor** and **Claude** too, but they just don't happen to have our, you know, proprietary codebase.

</details>

### AI时代的人工价值

**Clarvo**: 是的。我本来想问你，你担心 **AI** 机器人会取代你，让你出局吗？我只是好奇，你如何看待在 **AI** 驱动的关系中，人类的最高价值不是充当一个传声筒，而且我认为你也不认为自己是那样。那么，在这种由 **AI** 赋能的关系中，人类在哪里增加价值呢？

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. I was I was going to ask you, are you worried that like the **AI**bot is coming and you're you're cut you're cut out of it? And I I'm I'm just curious how you think about then when like you you again like the highest order of you is not to be a pass through and I don't think you think of that yourself as that. And so where does the human in these relationships powered by **AI** you know add add the value

</details>

**Al Chen**: 嗯，我不会盲目地将从 **Claude Code** 获得的答案复制粘贴给我的客户，无论是在 **Slack** 还是电子邮件中。我仍然会尝试校对所有内容，并且我确实会努力让它听起来更像人类。你可能会争辩说“为什么不让 **Claude Code** 让你的答案听起来更像人类呢？”但我认为我们所有人都知道，当我们收到一个来自 **AI** 的答案时，它会是什么样子，比如你会看到一个项目符号，上面写着“总结一下，你需要做这些事情来确保你的 **ClickHouse** 在...中工作”，所以去除那些让它看起来像机器人发出的东西，会使它看起来更像人类。我们实际上，我的意思是，这有点深入到我们工作方式的幕后，但我们有时会因为客户说“你能不能不要给我一个错误响应，而是给我一个人工校对过的，告诉我它如何适用于我？”而受到批评，因为通常的响应太冗长了。它包含的信息太多了，而客户只想知道最关键的要点。我需要知道什么才能将这个镜像部署到我的集群上？所以，这就是人类的价值所在，我仍然认为自己是提供价值的人，将信息提炼成他们实际需要的东西。我想说，即使对于一些更深入的技术问题，我仍然会尝试获得工程师的视角，以确保 **Claude Code** 没有产生幻觉或说出任何不寻常的事情。在我的系统提示中，我总是，你知道，在我的 **Claude Code** 中，我会说“不要编造任何东西。始终引用你的来源，指出你获取这些信息的代码行。”但即便如此，如果我没有完全理解这个函数是如何工作的，或者其他什么，我仍然会向工程频道询问：“嘿，这是 **Claude Code** 告诉我的。这和你的想法一致吗？”有时我错了，或者 **Claude Code** 错了，因为我们的工程师一直在考虑重构到这个新模型中，而这个新模型并没有在我们的代码库中捕获。它只可能记录在某个会议记录中，或者只是在走廊里的对话中。所以这些是我永远无法在 **Claude** 中查询到的东西。

<details>
<summary>Original English</summary>

**Al Chen**: well to I don't just blindly copy and paste the answers I get from **Claude Code** to my customers in **Slack** or email or wherever. I still try to proofread everything and I actually do like try to make it sound more human and you can then say the argument oh why don't you use **Claude Code** to make your answer sound more human and I think all of us know when we get an answer that's from an **AI** and it's you know things like you know you'll see like a bullet point saying like in summary here are the things you need to do to make sure your **ClickHouse** works within so it's like removing things like that that just make it seem like it's from a bot just makes it seem more human and we've actually I mean this is kind of going into going behind the scenes of how we work but we've been dinged sometimes where the customer will say can you just not give me an error response and just give me like a human proof read of it and tell me how it applies to me because typically the response is way too verbose. It has way too much information and the customer just wants to know give me like the bottom line up front. what do I need to know to like deploy this image onto my cluster? And so that's where the human I I still come see myself as a human providing value and callulling that down to what they actually need. And I would say even for some of the more in-depth technical questions, I still try to get an engineer's perspective on it to make sure like **Claude Code** is not hallucinating or not saying anything out of the out of the ordinary. In my system prompt, I always, you know, in my **Claude Code**, I say things like, "Don't make anything up. Always site your sources, point me to the line of code where you're getting this information from." But even with that, if I don't fully understand how this function works or whatever, I'm still paying like the engineering channel to say, "Hey, this is what **Claude Code** told me. Does that jive with what you're thinking?" And there are times when I'm wrong or **Claude Code** is wrong because our engineers have been thinking about refactoring into this new model which is not captured in our codebase anywhere. It's just captured in like a meeting note somewhere or just like you know hallway conversations. And so those are the things that I'll never be able to query let's say in in **Claude**.

</details>

**Clarvo**: 是的。我想说，人类增加价值的另一个方面，我总是说，就是**关系**是唯一的护城河。在某个时候，人们只是想有一个面孔，与那些向他们销售软件的人建立信任的个人关系。这就像我的企业展示一样。你想知道你有一个可以打电话的人。你想知道你有一个可以召集合适的人围绕你的团队和你的部署的人。而且，你知道，你想享受与那个人一起工作的乐趣。我只想说，我用这些 **AI** 工具进行构建非常有趣，但我不会说我的 **AI** 同事是最有趣的相处对象，就像我不会总是期待我的 **Claude Code** 会话。我不会真的和老朋友 **Claude** 闲聊。嗯，我确实认为你仍然需要与你的人类伙伴、人类同事等建立关系。所以我认为这其中有一部分是不会被淘汰的。老实说，我两年前做过一次演讲，我说产品经理（**PM**）已死，人们就问“那我们该做什么？”我说“去做销售吧”，因为销售不会消失。面向客户的工作不会消失。嗯，所以对于任何想要在即将到来的“末日”中生存下来的人，我确实认为面向客户的角色以及花更多时间与客户打交道是每个人工作中非常重要的一部分。

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. I would I would say the other thing that you know where I see humans adding value and I say this all the time which is like **RZ** is the only moat which is at some point you know people just want to have a face and a trusted personal relationship you know with the folks and this is like my enterprise showing but like with the folks that are selling them software. You want to know that you have somebody to call. You want to know that you have somebody that can gather the right the right folks around your team and your deployment. And you know, you want to enjoy working with that person. And I will just say I get a lot of um it is very fun for me to build with these tools with **AI** tools, but I wouldn't say my **AI** colleagues are like the most fun to hang out with, which is like I'm not like always looking forward to like my my **Claude Code** session. Like I'm going to really chitchat with with good old **Claude**. Um and I do think you still have that relationship with, you know, your human partners, your human colleagues, all that sort of stuff. And so I think there is a piece of that that's just not going to get cut out. And honestly I gave this talk uh I don't know two years ago I said **PM** is dead and people are like well what else should we do? And I was like get into sales like that's not going away. Customerf facing stuff is not is not going away. Um so for anybody that wants to survive you know the the incoming apocalypse I do think customerf facing roles and spending more time customerf facing is a really important part of everyone's job.

</details>

**Al Chen**: 绝对如此。如果你从事企业销售，那完全是人际交往、握手、午餐、晚餐，所以我想这在短期内永远不会被 **AI** 取代。

<details>
<summary>Original English</summary>

**Al Chen**: Absolutely. if you're working enterprise sales like that is all people handshakes um lunches dinners so that will never be replaced I think by **AI** anytime soon

</details>

**Clarvo**: 嗯，你知道，这里可能存在一个代际转变，我认为随着我们不断销售，我们会看到。我以前常说我在企业销售中的笑话，企业销售最大的阻力是我开始向千禧一代销售，他们希望你到他们门口时发短信，而不是敲门，就像他们被颠覆了一样。嗯，我们拭目以待。我们将看看企业销售会如何随着代际变化。本期节目由 **Tines** 赞助，这是一个智能工作流平台，为世界上最重要的工作提供动力。业务发展速度快于支持它的系统。团队被重复性任务、分散的工具和难以获取的数据所困扰。**AI** 潜力巨大，但当底层一切都碎片化时，它就会举步维艰。**Tines** 解决了这个问题。它在一个安全、灵活的平台中统一了你的工具、数据和流程，融合了代理 **AI**、自动化和人工干预。团队可以节省时间，工作流运行更智能，**AI** 真正提供实际价值。客户现在每周自动化超过15亿次操作。**Tines** 受到 **Canva**、**Coinbase**、**Databricks**、**GitLab**、**Mars** 和 **Reddit** 等公司的信任。请访问 times.com/howiAI 试用 **Tines**。好的，所以我们来回顾一下，我们展示了你如何在你非常复杂的代码库中使用所有这些代码库。将其与 **Claude Code** 结合起来，通过一些快捷方式和脚本使其更高效，从而能够回答客户查询，然后还能够为你的客户构建定制的部署计划，这些计划精确地基于你的代码如何工作以及他们的基础设施如何工作，让每个人都更满意，并让客户更快地启动。但是。

<details>
<summary>Original English</summary>

**Clarvo**: well you know and there might be a generational shift though here I think as as we sell as we sell we'll see you know I used to say my my joke in enterprise sales and the biggest um the the biggest headwind to enterprise sales was I was starting to sell to millennials who like wanted you to text when you showed up at their door. They didn't want you to knock on their door like they're subverted. Um, we'll see. We'll see how enterprise sales changes generationally. This episode is brought to you by **Tines**, the intelligent workflow platform powering the world's most important work. Business moves faster than the systems meant to support it. Teams are stuck with repetitive tasks, scattered tools, and hardto-reach data. **AI** has huge promise, but struggles when everything underneath is fragmented. **Tines** fixes that. It unifies your tools, data, and processes in one secure, flexible platform, blending **Agette AI**, automation, and human-led intervention. Teams get their time back, workflows run smarter, and **AI** actually delivers real value. Customers now automate over 1.5 billion actions every week. **Tines** is trusted by companies like **Canva**, **Coinbase**, **Databricks**, **GitLab**, **Mars**, and **Reddit**. Try **Tines** at times.com/howiAI. All right, so we have just to recap, we've shown how you use all these repositories in your very complex codebase. Pair that with **Claude Code**, um, which is made more efficient through a couple like shortcuts and scripts to be able for you to answer customer queries and then also build custom deployment plans for your customers anchored in exactly how your code works and exactly how their infrastructure works, making everybody happier and getting customers off the ground quicker. But

</details>

### 利用AI自动化客户支持工作流

**Clarvo**: 也有一些情况，你需要在不同的渠道进行更具响应性的支持，我知道你正在为此使用 **AI**。那么，你愿意向我们介绍一下你如何使用 **AI** 和 **Slack** 来支持客户吗？

<details>
<summary>Original English</summary>

**Clarvo**: there are also instances where you need to be doing more reactive um support in in different channels and I know you're using **AI** for that. So you want to walk us through how you're using **AI** and **Slack** and supporting customers there.

</details>

**Al Chen**: 是的。就像许多我所说的数字 **AI** 原生公司一样，我们大部分的客户支持都是通过 **Slack** 进行的。你知道，我们与客户有外部渠道，我来自一个所有事情都通过中央 **Zendesk** 或 **Intercom** 等工具处理的世界，但对于企业客户来说，这有点像一种随时随地的模式。因此，我们在内部使用一个名为 **Pylon** 的工具来监控所有不同的外部 **Slack** 渠道。我将在这个标签页中向你展示它的样子。这是一个我与客户进行对话的例子，客户提出了关于我们 **Galileo** 回调函数以及它如何发出不同事件的深入问题。正如你所想象的，我除了使用我们的文档外，还使用 **Claude Code** 来帮助回答这些问题。但是当你在 **Pylon** 或 **Slack** 中看到这样的对话时，你首先要考虑的是，我是否可以把它变成一篇帮助文章，或者我是否应该更新我们的文档，或者其他客户是否会从这个小 **Slack** 线程中捕获的知识中受益。**Pylon** 允许我们做的是，查看一个非常长的 **Slack** 线程，它可以帮助你生成一篇帮助文章。在这里，我有一个已经与这个特定对话关联的文章。它实际上就是点击“添加文章”、“生成文章草稿”，然后选择不同的模板，它就会即时为你创建这样一篇文章。这并不是什么高深的技术。你可以复制粘贴整个 **Slack** 线程，把它放到任何你想要生成帮助文章的 **AI** 工具中。**Pylon** 的主要优点是所有东西都集中在一个界面中。所以你不需要担心复制粘贴和整理链接。所以这就像它生成的草稿。然后我们有一个基于真实客户对话的持续文章列表。这些文章经过抽象，不显示任何特定的客户信息。但当我们发布这些文章时，它们就会进入这个知识库，这也是一个公共知识库。这有点像关于 **Galileo** 如何工作的部署问题的深入、细节的“活生生的真相”。与我们的文档相比，它总是更深入、更及时，因为我们的官方文档需要拉取文档代码库，提交 **PR**，获得批准等等。所以这是一个更完善的流程。而这些基于知识库的文章，则有点像即时性的，你有一个 **Slack** 线程想要总结，就用 **Pylon** 创建它，然后它就会自动发布到这个知识库网站。所以，我喜欢这一点的原因之一是，它代表了我所说的 **AI** 中的“然后”工作流发现，我的意思是，想象你有一个无限人力的团队，你面临一项任务，每次他们完成任务的一个步骤，你都会问“然后呢？”，他们都能做到。所以，这就像我从客户那里收到了一个 **Slack** 查询，我回答了它，然后就像如果你有一个完美配置的团队，接下来你会做什么？你会说“然后我会把它变成一篇文章”，然后你会说“好的，你把它变成文章了，然后呢？”你会说“然后我会把它分享给我们的客户成功团队，并就这个答案对他们进行培训，因为每个人都需要知道这些信息。”然后你会说“然后我们可以利用所有这些问题进行长尾 **SEO**。”我认为你可以像这样将这些“然后”工作流串联起来，实际构建出一个非常酷的良性循环系统，基于一个单一行动。而且，因为做其中任何一个的成本都趋近于零，你可以真正地深入挖掘这些任务，而这些任务是任何人类团队都没有能力真正完成的。但如果你把它看作一个系统，它会帮助你的人类队友，帮助你的客户，你可以完成很多事情。我们有几集节目。嗯，**Suzie** 的 **Matt** 展示了一个类似的版本，他会记录客户电话，然后根据客户说的短语在 **AdWords** 上竞价，并撰写博客文章，并进行销售辅导。所以我认为这是一个非常相似的例子，那就是你在 **Slack** 中有一个原子单位的问题，然后你把它变成了一个让整个团队受益的东西。

<details>
<summary>Original English</summary>

**Al Chen**: Yeah. So like many I say digital **AI** native companies, we do a lot of our customer support through **Slack**. you know, we have external channels with our customers and not I I mean, I come from the I used to work in a world where everything was through like a central **Zendesk** or **Intercom** or whatever, but for enterprise customers, it's kind of like a onthe-go always kind of on kind of thing. And so, we use a tool internally called **Pylon** for monitoring all our different external **Slack** channels. And I'm going to show you what this looks like in this tab. And this is an example of a conversation I had with a customer asking in-depth qu uh questions about like our **Galileo** call back function and how it admits different events. And as you can imagine, I was using **Claude Code** to help answer these questions in addition to using our docs. But when you're looking at a conversation like this in **Pylon** or in **Slack**, the first thing you have to think about is like, I wonder if like I could turn this into a help article or if I should update our docs or will other customers benefit from the knowledge that's being trapped in this little **Slack** thread. And so what **Pylon** allows us to do is looking at a really long **Slack** thread, it can help you generate a help article. And right here I already have one that's associated with this specific conversation. But it's literally just clicking on add article generate article draft and then these different templates and it just creates like this article for you on the fly. Now this is not rocket science. You could copy and paste the whole **Slack** thread, put it into any **AI** tool you want to generate help article. The main thing with **Pylon** is everything is kind of just like in one interface. So you don't have to worry about like copy and pasting and putting links together. So this is kind of like that draft that this came up with. And then we have this ongoing list of articles based on real customer conversations. And those articles are abstracted to not show any specific customer information. But then when we publish these articles, they go they go into this knowledge base which is also public knowledge base. And this is kind of like the living truth of like indepth in the weeds uh com questions about deployment about how **Galileo** works. And it's always way more in depth and way more up to-date compared to our docs because our official docs require pulling down the docs repo, submitting a **PR**, getting it approved, so on and so forth. And so it's a lot more of a polished process. Whereas with these knowledgebased articles, it's kind of like just on the fly you have a **Slack** thread you want to summarize, use it uh create it in **Pylon** and then it just automatically gets autopublished to this uh knowledgebased site. So one of the things that I love about this is this represents my then like what I call the and then workflow discovery in **AI** which is I say imagine you had an infinitely staffed team and you were faced with the task and every time they did one step of the task you asked and then and they were able to do it. So it's like I got a **Slack** query from a customer so I answered it and it was like if you had a perfectly staffed team what would you do next and be like and then I would turn that into an article and it was like okay and you turn it into article and then what you do it's like and then I would share that with our customer success team and train them on this answer because you know everybody needs to know this information and be like and then you be like and then we could probably do like longtail **SEO** off all these questions and I think you can like chain chain these like and then um you know workflows to actually build out like a pretty cool you know virtuous cycle system based off a single action. And because again like the cost of doing any one of those collapses to zero, you can really pull the thread of these tasks that like no human team would have the capacity to really do. But if you think of it as a system, it helps your human teammates, it helps your customers, and you can get a lot of stuff done. We have a couple episodes. Um, **Matt** at **Suzie** showed kind of a a version of this where he takes a customer a recorded customer call and like is bidding on **AdWords** for like phrases the customer says and like spinning up blog posts and doing like sales coaching off of it. So I think this is like a very similar example which is you have this like you know atomic unit of a question in **Slack** and you've turned it into something that benefits benefits the full team.

</details>

**Clarvo**: 是的。我想如果你回到 **AI** 之前的时代，我用 **Intercom** 做过这件事，我们想看看我们的用户在提问时最常谈论什么。所以如果你开始将所有这些用户问题和见解聚类成不同的主题和类别，这些最终也可以决定你的产品路线图。所以我认为 **AI** 只是在某种程度上自动化了更多这方面的工作，而你不需要在 **Google Sheets** 或其他地方进行手动排序和分组。我知道有一些平台可以为你做这件事。我想有一个叫做 **Interpret** 的，我以前用过。

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. I think if you go back to pre-**AI** days and I'm doing this with **Intercom** was you we wanted to see what are what are our users talking about the most when they're asking us questions. And so if you start clustering all these user questions and insights into different themes and categories, those can end up determining determining your product road map too. And so I think with **AI** just kind of automates much a little bit more of that without you having to like do the manual sorting and grouping within like **Google Sheets** or whatever. I know there's like platforms you can buy that do this for you. I think there's one called um **Interpret** which I've used in the past.

</details>

**Al Chen**: 他们是《我如何AI》的赞助商，所以谢谢 **Interpret**。是的，是的。所以，嗯，你知道，我认为这再次取决于你如何看待这个良性循环。也许你不想让所有数据都像在一个地方孤立起来，你希望它更开放。所以这也是需要考虑的。但是的，**AI** 肯定有助于你所说的，为客户也为你的产品团队创造那个良性循环。所以，我有一个问题。嗯，这是 **Al** 的系统，还是 **Galileo** 的现场工程系统？我的意思是，你有了这个很棒的工作流。你发现了所有这些东西。这种流程如何才能在整个组织中推广、分享和教授，以便所有与客户互动的人都能从你发现的所有技巧中受益？

<details>
<summary>Original English</summary>

**Al Chen**: There's they've been a how I sponsor so thank you **Interpret**. Yeah. Yeah. So um but you know I think again depending on how you want to view view this whole virtuous life cycle. Maybe you don't want all of your data to be like in a silo in one place and you want to be more open. So there's that to think about too. But yeah **AI** definitely helps to your point make that virtual cycle for customers but also for your product team. So I have a question. Um, is this the the **Al** system or is this the **Galileo**, you know, field engineering system, which is, you know, you have this great workflow. You've discovered all these things. How does this sort of process get scaled out, shared, taught throughout the organization so that everybody that interacts with customers is benefiting from all the tips and tricks that you're figuring out yourself?

</details>

### 推广AI驱动的工作流

**Al Chen**: 当然。我以前的背景是在无代码/低代码领域工作，我非常相信系统、工具、流程以及帮助你创建这些东西的工具。所以当谈到这是否是做事的方式时，是的，这是我的方式，但我也可能是现场工程团队中对我们应该如何与客户交流、回答他们的问题以及引入正确内容文本方面最有主见的人之一。所以我告诉过很多人，将所有代码库拉到你的本地机器上，让 **Claude Code** 运行一个初始化命令来索引整个代码库等等。我只是不断地向我的队友分享这些技巧，以确保他们也能发挥出他们的能力。所以，这是我的方式，但我想说，我对我们应该如何做事也很有主见，因为我做过困难的、手动的方式。而这种方式对我来说，效率提高了10倍。所以，我们没有一个明确的规定，说“哦，因为 **Al** 现在这样做，整个团队都必须这样做。”更多的是人们展示“这是我遇到的问题，这是我使用 **Claude Code** 获得的结果，以及为什么我认为你应该采用我的解决方案。”我不断地在内部进行这种对话，讨论我们如何摆脱一些我认为会拖慢我们的流程，以及 **AI** 如何也能融入所有这些流程。

<details>
<summary>Original English</summary>

**Al Chen**: Sure. So I my previous background was I've worked in kind of the no code low code space and I'm a big believer in systems tools processes and the tools that help you create those things and so when it comes to is this the way of doing things yes it's my way but I'm also very probably one of the more more opinionated people on the field engineering team about like how we should be doing things in terms of talking to customers answering their questions and pulling in the right content text. And so I've told multiple people like pull all the repos into your local machine and have **Claude Code** run an init command to index the whole codebase or whatever. And I'm just like constantly sharing these tips and tricks to my teammates to make sure they're also um functioning at their capacity. So, it's my way, but I'm I would say I'm also very opinionated about how we should do things because I've done things the hard way, the manual way. And this way to me is like just 10 times way more productive. So, um we don't have like a specific like, oh, because **Al**'s doing it now, the whole team has to do it. It's more just like people show here's the problem I had, here's the results I had with **Claude Code** or whatever, and here's why I think you should adopt my um solution. And I'm constantly having that conversation internally about like how do we break out of certain processes that I think are slowing us down and um how **AI** can be infused into all those processes as well.

</details>

**Clarvo**: 嗯，现在你正在向我们所有的《我如何AI》观众分享他们如何做到这一点。所以你的影响力不仅仅局限于你的团队。好的。那么，再总结一下，你的代码是你的**事实的单一来源**。它可以帮助你回答客户问题。它可以帮助你记录客户解决方案。你还可以通过 **Slack** 等其他渠道做到这一点，然后创建这些良性循环，解决单个客户的问题，然后建立一个系统，为你自己和你的队友，在整个客户群中更可扩展地解决这个问题。嗯，这是一期非常有影响力的节目。我认为人们会从中获得很多启发。对于所有面向客户的朋友来说，这非常实用，关于他们明天就可以开始使用 **AI** 来为客户提供更好的体验。让我们进入闪电问答环节。我有一个非常关心的问题，

<details>
<summary>Original English</summary>

**Clarvo**: Well, and now you're sharing to all of our how I **AI** audience on how they can do that. So you're having more impact than just on your team. All right. Well, so to just recap again, your code is your **source of truth**. It can help you answer customer questions. It can help you document um customer solutions. You can also do that with other channels like **Slack** and then like create these virtuous loops of solving a single customer's problem and then a system to solve that problem more scalably across your entire customer base for yourself and for your teammates. Um very very high impact episode. I think people are going to have a lot of takeaways from this one. super practical for all my friends that are customerf facing out there on things they can do starting tomorrow to use **AI** um to to give their customers a better experience. Let's jump into lightning round questions. And I have one that's really top of mind,

</details>

### 工程师对代码库开放的顾虑

**Clarvo**: 看起来 **Galileo** 有一个非常健康的文化，但我可以想象有些团队，特别是工程团队，会说：“哦，不不不不。我真的不希望面向客户的人员进入我们的代码库，查询它，然后随意地向我们的客户群提供答案，尤其是在一个真正需要深入技术理解的更技术性的产品中。”我认为你已经证明这样做有很多价值。但对于那些对向非技术角色开放代码库访问权限有点犹豫的团队，你会说什么？

<details>
<summary>Original English</summary>

**Clarvo**: which is it seems like you have a very healthy culture at **Galileo**, but I can imagine teams, especially engineering teams that are like, "Oh, no, no, no, no. I I don't really want the customerf facing folks like going into our repo, querying it, and then just yoloing answers over to our customer base, especially in a more technical product that really requires deep technical understanding. I think you've proven that there's a lot of value in doing that. But what would you say to those teams that are a little bit more hesitant about ungating access to the repo to non-technical roles?"

</details>

**Al Chen**: 嗯，我认为从工程工程师的角度来看，我会这样看：你在一周内、在一天内，有多少次在 **Slack** 上被问到紧急问题，有多少次被私信，有多少次在线程中被提及“这个东西怎么运作的？它在哪里？我们怎么确保它按预期运行？”而你总是回答这些问题的来源，你就是瓶颈。如果你为你的面向客户的团队提供一个类似于我所拥有的系统，那么你就可以消除那种苦差事，以及不断地随叫随到回答那些随机的产品和工程问题，这些问题可能已经在你的代码库中，或者可能已经在你的 **Confluence** 中。所以我认为对我来说最大的收获是，你的客户团队有多少时间被浪费了，因为他们无法访问代码。我的意思是，我认为有一些无代码，我的意思是，我认为你也许可以将你的代码拉入 **Claude Co-Work**，它更偏向无代码，还有其他一些更偏向无代码的做事方式，但我认为我所展示的是，我认为是能够拉取你的代码并获得答案的最有效方式。嗯，所以我认为从工程师的角度来看，这可以节省多少时间，以及你的客户团队能变得多么有效。我认为与之相关的是，我们的现场工程团队非常技术化，所以也许你可以提高你的客户成功或客户工程团队的招聘门槛，让他们能够熟练使用 **GitHub** 并将代码库拉到本地。所以，如果他们今天不那么技术化，可以只是进行一个简单的教程或赋能会议，教他们如何使用 **GitHub**，如何使用 **Git** 命令，诸如此类。可能还需要一些自学。但我认为一旦你设置好环境，这整个过程中最困难的部分就是设置环境。一旦设置好，那么使用 **Claude Code** 就像使用任何其他 **AI** 聊天机器人一样。嗯，所以我认为有几种不同的方法可以实现代码库的民主化访问。

<details>
<summary>Original English</summary>

**Al Chen**: Um I think from the engineering engineers perspective I would look at it as how many I would try to think about how many times in the last week in the last day have you been asked a last minute question on **Slack** a last minute **DM** ping mentioned in a thread where how does this thing work where is this how do we make sure that this is functioning the way it should be and you're constantly the source of you're the bottleneck for answering that question And if you provide a system kind of similar to what I have to your uh your customerf facing team then you kind of just take away that toil and the constant like on callness of like answering these random product and engineering questions that is already in your codebase or maybe it's already living in your **Confluence** or something like that. So I think that's really the biggest takeaway for me is how much of your time is being sucked away from your customers team because they don't have access to the code. And I mean I think there's some no code I mean I think you can maybe pull in your code into **Claude Co-Work** which is a little more noodey and other kind of like more no cody ways of doing things but I think what I've shown is I think the most performant way of being able to pull your code and get answers out. Um so I think that's kind of um from an engineer's perspective how much time can you save and then also how more effective your your customer um facing or can be and I think the correlary correlary to that is that our field engineering team is very technical and so maybe you increase the hiring bar for your customer success or customer engineering team to feel comfortable using **GitHub** and pulling repos into your local And so that could be today if it's if they're not technical is just doing like a simple tutorial or enablement session on how do you use **GitHub**, how do you use **Git** commands, um things like that. And there might be some self-learning you have to do on the side too. But I think once you're once you have your environment set up, that's always like the hardest part about this whole exercise is getting your environment set up. Once that thing is set up, then using **Claude Code** is just like using any other **AI** chatbot. Um, so I think there's like a few different ways I'd approach it from to democratize access to your repos.

</details>

### 硬技能与终身学习

**Clarvo**: 我想说的一件事是，我经常告诉人们，这是**硬技能**的时代，也就是说，无论你担任什么角色，抱歉，你都得学一点如何编码。你必须学一点 **Git** 是如何工作的。你必须能够接受在 **IDE** 中打开一些你不懂的代码，因为在接下来的3年里，这将是我们沟通的基础。它将越来越接近代码，因为这些**大型语言模型（LLMs）**非常擅长理解代码。所以我认为，总的来说，人们需要变得更技术化，并围绕代码发展硬技能，即使你的工作不是编码。我认为我告诉人们的第二件事是，现在是学习如何编码的最佳时机。真正没有比现在更好的学习如何实际编码的时机了。我认为那些使用 **Claude Code** 进行开发，但没有将其作为学习一些基本软件工程概念的借口或支持的人，错失了50%的价值。就像我必须通过一本书自学编程。字面意义上的一本书。我打开一本书，然后看着我的单屏幕，因为我们那时都没有双屏幕。那会很疯狂。我会读那本书，然后把书中的文字作为代码输入，按下回车，它就会显示“Hello World”。那就是我的生活。而现在，你的电脑里有这样一个神奇的、超级有耐心、无限智慧的老师，你可以用它来学习编程。而且我认为，你知道，你谈到了一些关于 **Kubernetes** 以及你如何在这方面提升技能。所以我很好奇你对使用这些工具提升技术技能的看法。

<details>
<summary>Original English</summary>

**Clarvo**: One of the things I was going to say is I often tell people this is the era of the **hard skill**, which is no matter what role you're in, sorry babe, you got to like learn a little bit how to code. You have to learn a little bit what **Git** works like. you have to be okay opening up some code you don't understand in an **IDE** because that's just going to be the substrate by which we communicate for the next 3 years. It's going to go like closer and closer to the code because these **LLMs** are extremely good at understanding code. And so I think across the board people just need to become more technical and develop hard skills around code even if your job is not code. I think the second thing that I tell people is um there's no better time to learn how to code. Truly no better time to learn how to actually code. And I think people that are shipping with **Claude Code** but not using that as an excuse or a support to learn some fundamental software engineering concepts are missing 50% of the value. Like I had to teach myself how to code out of a book. Like literally out of a book. It was I had a book open and then I would look at my single screen because none of us had two screens. That would be crazy. And I would like read the book and I would type the book in the like the words in the book in code and press enter and it would say hello world. And that was my life. And now you have this like magic, super patient, infinitely wise, you know, like teacher in your computer that you can use to learn to code. And I think you know, you talked a little bit about **Kubernetes** and how you you scaled up on that. So I'm curious your thoughts on just upleveling technical skills using some of these these tools.

</details>

**Al Chen**: 我认为最重要的启示是，你只需要对事物如何运作保持好奇心。除此之外，我真的说不出什么了。这有点像我也来自那个世界，就是看书学习，然后我会说比那更高一级的进步是知道如何写一个好的 **Google** 查询，然后是 **Stack Overflow**，去 **Stack Overflow**。然后你们有多少人对此有共鸣：你去某个 **Stack Overflow** 问答，复制粘贴代码，当然它不会完美运行，所以你就会去 **Google** 搜索你复制粘贴后得到的错误。当然，**Stack Overflow** 上的每个人都超级刻薄，那不是一种健康的对话。然后就像你说的，你现在有一个无限耐心、无限友善的助手，它永远不会给你 **Stack Overflow** 上错误的**代码片段**。它总是根据你的需求、你想要的东西量身定制。然后如果你再进一步，就像你说的“然后呢？”，如果你再进一步说：“好的，谢谢 **Claude**。你告诉我这是答案。告诉我为什么它会这样工作。”然后你就会开始深入了解 **Kubernetes** 和更深层次的细节。但当然，你不可能一下子就知道所有事情。所以你可以说：“哦，用简单的术语向我解释，像我五岁一样向我解释。”所以你只是在不断地深入探究。我有时确实会在这个“兔子洞”里迷失方向。嗯，但我从未发现过不深入探究这个“兔子洞”对我的日常工作没有帮助的情况，尤其是在 **AI** 领域，一切都发展得如此之快。

<details>
<summary>Original English</summary>

**Al Chen**: I I think the meta takeaway is like you just have to be curious about like how things work. I can't really say anything else besides that. It's kind of like I come from that same world too of like looking at a book and then I would say the graduation above that was knowing how to write a good **Google** query and then **Stack Overflow** going to **Stack Overflow** and then how many of you resonate with this where you go to some **Stack Overflow Q&A** you copy and paste the code it doesn't work perfectly of course so you're googling the error you get from that thing you copied and pasted and of course everyone in **Stack Overflow** is super snarky and it's like not a kind of healthy conversation and then to your point you have this like infinitely patient, infinitely kind assistant who never gives you the wrong **code snippet** from **Stack Overflow**. It's always like tailored to back to everything I'm saying is tailored to your needs to what you want. And then if you go the extra step and like what you said and then what if you go the extra step and say, "Okay, thanks **Claude**. You told me this is the answer. tell me why this works. And then it's you start getting into **Kubernetes** and into the deeper in the in the weeds things. But of course, you're not going to know everything right off the bat. So you can say things like, "Oh, explain to me in simple terms, explain to me like I'm five." And so you're just kind of pulling on that thread. And I sometimes do get lost going down the rabbit hole. Um, but I've never found a situation where not going down that rabbit hole does not help me in my day-to-day job, especially in **AI** where everything's is is moving so fast.

</details>

**Clarvo**: 是的。这只是为了让大家感到安心。这不仅仅是初学者的事情。我发现我自己也在用 **GPT-4o** 做这件事，它是一个强大的模型，就像在和一位你遇到过的最深奥的资深软件工程师交谈，他用非常技术性的术语解释他的计划，我就会说“老兄，你能不能用最简单的方式解释你在做什么？用通俗的语言告诉我。我不需要技术细节。就用通俗的语言告诉我。”这再次源于好奇心，我想确保我理解你所谈论的基本概念。我想确保我在学习我们的代码库和通用原则的同时不断进步。所以我确实认为，无论你的资历水平如何，你对技术的经验如何，这种好奇心心态都能让你不断学习，学得更好。好的，在我们结束之前，我的最后一个问题。嗯，当 **AI** 没有给你正确的答案，它给你的是它想发给客户的 **AI** 废话时，你的提示技巧是什么？

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. And this is just to to make everybody feel comfortable. This is not just a beginner thing. And I find myself doing this with um **GPT-4o** which is like a powerhouse model and also like talking to the most esoteric senior software engineer you've ever met where it like explains his plans in these very technical terms and I'm like dude just like explain to me what you're doing in number one. Tell me in plain language. I do not need the technical details. Like just tell me in plain language. And again, it comes from this curiosity of I want to make sure I understand the fundamental concepts of what you're talking about. And I want to make sure I'm learning both my codebase and general principles as we go. And so I do think that curiosity mindset, no matter what your seniority level is, your experience with technology, you can always learn learn something better. Okay, my last question before we get you out of here. Um, when **AI** is not giving you the right answer, it's giving you **AI** slop that it wants to email to your customer, what is your prompting technique?

</details>

### 高效提示技巧

**Al Chen**: 我首先要说一件事，那就是我在从 **Claude** 或 **AI** 获取正确答案方面非常执着。我把它当作我的初级分析师，你知道，我可以向它抛出无数个问题。因为我以前是分析师，我来自一个你被期望不断努力工作的世界，所以我在要求 **AI** 为我做事方面非常执着，尤其是在回答客户问题时。我认为我使用的一个提示策略是，我的意思是，你可能以前听过类似的版本，比如“我的客户会，你知道，如果我做不好，就会...”，或者“我的配额取决于完成这件事。”嗯，这些是我处理问题的一些方式，但这些都只是半个答案。我认为真正的答案，这又回到了好奇心的问题，就是“**深入思考**”。更深入地思考你为什么给我这个答案。深入思考为什么这是正确的。所以在 **Claude Code** 中，实际上有这种“**深入思考**”、“**更深入思考**”的范式，关于它为了得出答案做了多少推理。所以它只是更深入一步，说“你给了我答案，告诉我你为什么认为这是正确的答案，并给我提供你得出这个推理的来源。”嗯，所以我认为多走那一步，特别是对于那些你不确定答案是否正确，或者你读代码觉得有点道理但又不太确定的问题，多进行一次查询以确保你得到正确的响应，有时会给你关于你的代码库、你的产品以前从未想过的新见解。

<details>
<summary>Original English</summary>

**Al Chen**: I I'll I'll say one thing first off the bat is like I'm very relentless when it comes to getting the right answer from **Claude** or from **AI**. Like I treat it like my entry level analyst, you know, to that I can just like throw a billion questions. I cuz I used to be an analyst and u I come from the world where like you were just expected to crank and so I'm relentless when it comes to asking **AI** to do things for me especially when it comes to answering customer questions. I think the one prompt strategy I use is like I mean you've probably heard versions of this before which is like you know my customer will you know turn if I don't get this right or you know like um my my quota is dependent on getting this this thing done. Um, so those are kind of ways I've approached it, but that those are like half answers. I think the the real answer, and this goes back to curiosity thing, is like, and "**think hard**". "**Think harder**" about why you're giving me this answer. "**Think hard**" about why this is right. And so in **Claude Code**, there's actually like this "**think hard**", "**think harder**" paradigm of like how much reasoning it does to come to the answer. And so it's just going going one step deeper and saying like you gave me the answer, tell me why you think this is the why this is the right answer and give me the sources for what provided you with this reasoning. Um, so I think going that one extra step, especially for those questions where you're like not quite sure if it's the right answer and like you're reading the code and it kind of makes sense, but just going that one extra query to make sure you're getting the right response will u sometimes, you know, give you new insights about your codebase that your product that you haven't thought about before.

</details>

**Clarvo**: 好的。我喜欢这种实用的方法，比如强制增强推理，“**深入思考**”，“**更深入思考**”。我不想让人们错过你说的，你会引用错误。我的意思是，每次 **Claude Code** 正确回答一个问题时，我们都给它一点奖励吧。你得和 **Claude Code** 分享你的配额。这才是我们真正需要做的。嗯，然后说“看，如果能回答这个问题，我会在这个交易中给你加一分。”

<details>
<summary>Original English</summary>

**Clarvo**: Okay. I like the practical like force the enhanced reasoning, "**think hard**", "**think harder**". I don't want people to miss you tell people you're going to miss quote. I mean like let's give **Claude Code** a little spiff every time it answers a question correctly. You got to split your quota with **Claude Code**. That's really what we need to do. Um and say look I'll give you a point on this deal if we can answer this this question.

</details>

**Al Chen**: 非常非常有趣。我认为今天，嗯，到这集节目上线的时候，它就会上线了。**Stripe** 刚刚发布了这个支付协议，所以你可以支付你的代理。所以你可以，你知道，每次都给它一些代理费之类的。

<details>
<summary>Original English</summary>

**Al Chen**: Very very funny. And I think today um it'll be live by the time this episode goes live. **Stripe** just released this like payments protocol so you can pay your agents. So you can, you know, toss it a couple agent bucks or whatever. Uh, every time.

</details>

**Clarvo**: 是的。你给它越多钱，它给出的答案就越好，之类的。没错，就是投币式 **Claude**。那将是我的新技能。好的，**Al**，这次谈话很棒。我们可以在哪里找到你，我们如何能提供帮助？

<details>
<summary>Original English</summary>

**Clarvo**: Yeah. Gives you better answers the more bucks you give it or something. That's exactly coin. **Claude** coin coin operated **Claude**. That's going to be my new my new skill. Well, **Al**, this was great. Where can we find you and how can we be helpful?

</details>

**Al Chen**: 嗯，我在 **LinkedIn** 上，**Al Chen** 在 **Galileo** 的 **LinkedIn**。如果你正在构建 **AI** 应用程序，请查看 **Galileo**。另外，我认为对我来说最重要的一点是，我的团队正在积极招聘现场工程师。所以如果你想从事售后、售前、部署工程方面的工作，我们有很多空缺职位。如果这让你感兴趣，我们非常欢迎你加入团队。

<details>
<summary>Original English</summary>

**Al Chen**: Um, I'm on **LinkedIn** um **Alchen** on **LinkedIn** at **Galileo** and um check out **Galileo** if you're building a **AI** applications. Also, I think number one thing for me is my team is actively hiring field engineers. So if you want to work in post sales, pre-sales, for deployed engineering, um we have a bunch of open roles. So would love to have you join the team if um this is of interest.

</details>

**Clarvo**: 太棒了。感谢你加入《我如何AI》。

<details>
<summary>Original English</summary>

**Clarvo**: Amazing. Thanks for joining How **AI**.

</details>

**Al Chen**: 非常感谢。

<details>
<summary>Original English</summary>

**Al Chen**: Thank you so much.

</details>

**Clarvo**: 非常感谢大家的收看。如果你喜欢这个节目，请在 **YouTube** 上点赞并订阅，或者更好的是，留下你的评论和想法。你也可以在 **Apple Podcasts**、**Spotify** 或你最喜欢的播客应用上找到这个播客。请考虑给我们留下评分和评论，这将帮助其他人找到这个节目。你可以在 howiaipod.com 查看我们所有的节目并了解更多信息。下次再见。

<details>
<summary>Original English</summary>

**Clarvo**: Thanks so much for watching. If you enjoyed this show, please like and subscribe here on **YouTube** or even better, leave us a comment with your thoughts. You can also find this podcast on **Apple Podcasts**, **Spotify**, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>