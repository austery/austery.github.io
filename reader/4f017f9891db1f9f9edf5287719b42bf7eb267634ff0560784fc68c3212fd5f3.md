---
author: Latent Space
date: '2026-03-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Io0mAsHkiRY
speaker: Latent Space
tags:
  - context-engineering
  - knowledge-graph
  - rag
  - ai-infrastructure
  - personalization
title: 超越 RAG：Super Memory 创始人谈现代 AI 记忆架构与 OpenClaude 的局限
summary: Super Memory 创始人 Dhravya Shah 深入解析了 AI 记忆系统的演进。他指出 OpenClaude 等工具依赖静态 Markdown 文件和工具调用的局限性，并介绍了如何通过知识图谱、时间推理和用户画像构建“挂钩式”上下文基础设施，同时分享了在 Cloudflare 上以极低成本运行大规模系统的工程实践。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Dhravya Shah
companies_orgs:
  - Super Memory
  - Cloudflare
  - Anthropic
  - Bspace
products_models:
  - OpenClaude
  - Claude Code
  - Cursor
  - MemoryBench
media_books: []
status: evergreen
---
### Super Memory 的起源：从书签工具到上下文基础设施

**[主持人]**: 好的，我们现在在一个远程演播室，和 **Super Memory** 的 **Dhravya Shah** 在一起。欢迎来到 Lane Space。

<details>
<summary>Original English</summary>

**[Host]**: Okay, here we're here in a remote studio with Dravia Sha of Super Memory. Welcome to Lane Space.

</details>

**[Dhravya Shah]**: 谢谢邀请。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Thanks for inviting me.

</details>

**[主持人]**: 显然，你已经在时间线上火了好几年了。我刚发现你是在 2023 年推出 Super Memory 的。感觉时间没那么久，但你也确实做了很长时间了。

<details>
<summary>Original English</summary>

**[Host]**: Yeah. Uh, obviously you've been blowing up on on the timeline for multiple years now. I just found out you launched Super Memory in 2023. It feels shorter than that, but also you've been doing this for a while.

</details>

**[Dhravya Shah]**: 是的，我进入这个领域太久了。Super Memory 曾经是很多不同的产品，但现在它成了一个全能的工具。我会再回到这个问题上。但是，是的，经历了很多事情。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah, I've been in the space for way too long. Super Memory has been many different products, but now it's everything at once. I I'll get back into that. But yeah, lots of things.

</details>

**[主持人]**: 那么，这个项目最初是什么？我们回顾了你第一次在 **Product Hunt** 上的发布。你能给我们展示一下它最初是什么样子的吗？

<details>
<summary>Original English</summary>

**[Host]**: Okay. So, so what is this Laura? Can can uh we looked back at your first product hunt launch. You can show us what was it originally.

</details>

**[Dhravya Shah]**: 让我们从那里往回追溯。Super Memory 最初是作为一个消费者应用推出的，原本应该是一个更好的**书签和笔记工具**，并带有一些其他功能。例如，你可以跨 LLM 携带你的记忆。那是很久以前的事了。所以我们有一个 **MCP**（Model Context Protocol）发布，然后是应用本身的另一个发布。

最初显然只是应用，就像一个保存功能，你可以把东西存到应用里，再从应用里取出来，非常简单。然后我们觉得，既然 MCP 现在很流行，我们也应该做一个 MCP 版本。那段时间我个人正在做实习，当时在 **Cloudflare** 工作。这是我在一个叫 **Bspace** 的项目中做的副作用项目。你可能知道 Bspace，那是一个很多开发者在夜晚和周末构建东西的地方。他们真的会推动你去构建一些东西，并去和用户交流之类的。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Let's let's walk back from there. So, Super Memory launched as this consumer app that was supposed to be your kind of uh better bookmarking and note-taking tool with a few other features. So like for example you can take your memories across LLMs and this is from very long ago. So we had a uh an MCP launch and then we had another launch for the app itself. So earlier obviously it was just the app which was like a save you can save things to the app you can get things from the app very simple as that. And then we were like okay MCP is a thing now so we should probably make an MCP out of it. And this was a time when I personally was doing internships. I was working at Cloudflare at the time. And this was a side project that I did as a part of this thing called Bispace. And Bspace uh you might know about Bispace is it was like this place where a lot of builders used to build things nights and weekends. And they really pushed you to building something and like talking to users and stuff like that.

</details>

**[主持人]**: 是的，那就像一个 Z 世代的加速器，创始人后来放弃了，直接转向了别的事情。

<details>
<summary>Original English</summary>

**[Host]**: Yeah. That's like a Gen Z accelerator that like they the founder just gave up and just like moved on.

</details>

### $5 预算与 10 万用户的架构奇迹

**[Dhravya Shah]**: 没错。我参加了 Bspace 的第 3 季和第 5 季。我在 Bspace 期间**开源**了 Super Memory，结果这个项目彻底爆火了。它成了 2024 年增长最快的项目之一。我一直在推特上发，说我是如何以每月 **$5** 的预算在 Cloudflare 上运行这个项目的，而且它当时还是个消费者应用。

但随后我不断添加功能。早期，全世界对“记忆”的理解以及我们对“记忆”的理解仅仅是 **RAG**。你只需进行嵌入（embed），放入向量数据库，这就是你需要的全部。后来我深入钻研，发现向量数据库——当时甚至是现在，除了像 **Turso** 和 **Chroma** 少数几个——对于我当时达到的规模来说，其实并不具备扩展性。它们要么变得太慢，要么运行成本太高。所以我必须寻找其他创意方法来降低运行成本。我一直在发相关的推文，比如“我用每月 $5 运行 Super Memory，拥有 10 万用户，这是我的架构”，并配上一张完整的架构图。那次彻底火了，那是 Super Memory 的第一次成名事件。这导致人们感兴趣的不再是应用本身，而是我正在构建的**基础设施**。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Exactly. So I was in both season 3 and season 5 of Bspace and I open sourced Soup Memory during Bspace and it like the project absolutely blew up. it got like you know it was one of the biggest projects like fastest growing projects of 2024 and I I kept tweeting about how I'm running this on Cloudflare on $5 a month budget and it was still a consumer app but then I kept adding features to it so earlier the way we the world used to think of memory and how we used to think of memory was just rag so you just embed it put it in a vector database and that's all you need to do and now then I like dug down the rabbit hole and so so vector databases like at that time and even now except a few like like Turppuffer and Chroma were not really scalable for the scale I was getting to where they were either getting too slow or too expensive to run and so I had to you know find other creative ways of making it really cheap for me to run and I kept tweeting about all this so my tweet was like I run soup memory on $5 a month and I have 100,000 users and this is my architecture so it was like an entire diagram and that blew up that was the first kind of you know uh famous super memory event and that led to not people being interested in the app itself, people being interested in the infrastructure that I was building.

</details>

**[主持人]**: 是的。我记得你开源了它，然后我想，“噢是的，我得给它点个星并 fork 一下，因为如果我哪天需要这种配置，我绝对需要这个。”

<details>
<summary>Original English</summary>

**[Host]**: Yeah. I remember you open sourced it and then I was like, "Oh yeah, I need to star and fork this cuz I'm like if I ever need this, I need I need this uh setup."

</details>

### 现代 AI 记忆的四个维度

**[Dhravya Shah]**: 没错。在开源之后，几周内星标就涨到了 1 万。但我意识到，很多公司都在联系我，他们会问，“嘿，你能帮我们搭建我们的记忆系统吗？”我也去其他记忆公司工作过。这变成了整件事情，我基本上做了很多关于**上下文工程**（Context Engineering）的咨询工作。

我意识到，所有这些都有非常相似的用例，但风格略有不同。他们不仅需要检索，还需要真正的**用户理解**。我们稍后也会谈到什么是现代记忆，AI 应该如何记忆。我当时觉得，要让 LLM 真正擅长理解用户，你必须处理四件事：

1.  **知识更新**: 你必须使陈旧的知识失效并在其基础上构建，这与仅仅存储向量不同。
2.  **时间推理**: 给 Agent 一种对时间的理解，理解事情是如何随着时间流逝而变化的。
3.  **遗忘机制**: 为了个性化，需要忘掉那些不再相关的事情。
4.  **用户画像**: 记忆不仅仅是一个检索调用。LLM 有一个非常小的用户个人资料，它会在每一轮对话中使用。

我当时正在把所有这些组件构建到 Super Memory 中。我意识到这里有一些非常困难的基础设施挑战需要解决，既包括**提取层**（如何训练一个小模型来提取关于用户的信息），也包括维护第二层——**知识图谱**。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Exactly. Exactly. So after starting it and like after that open source, you know, it it blew up to like 10,000 stars in a few weeks. But then I realized like, you know, a lot of companies were reaching out to me. and they were like, "Hey, can you help us set up our memory thing?" And I also went and worked at other memory companies. And it became like this entire thing that like I was doing pretty much a lot of consultation work around context engineering. Um, and I realized like all of these have very similar use cases but with slightly different flavors where they they not only need retrieval, they need like true user understanding. And we'll get get to that as well like what is modern memory you know like how how should AI remember and then I was like okay so to make an LLM truly good at understanding a user you have to handle four things one is knowledge updates so you have to invalidate stale knowledge and build on top of it which is different from the storing vectors you have to have some sort of temporal reasoning so you have to have like give the agent an understanding of time and how things have passed for personalization And you need some sort of forgetfulness to forget things that are not relevant anymore at all. But you also need this concept we call user profiles to always like memory is not just a retrieval call. The LLM has this very small profile of the user that it will utilize on every single turn. So I I was building all of these components into supermember and and all of these apps and I realized that okay there's some really difficult infrastructure challenges to be solved here which is both on the extraction layer which is how do you truly like you know how do you train a small model that can extract things about the user and maintain the second layer which is the knowledge graph and the way we we build a knowledge graph is different from how people usually build knowledge graphs.

</details>

### 为什么传统三元组知识图谱是错误的

**[Dhravya Shah]**: 我们构建知识图谱的方式与人们通常的方式不同。人们通常有“**三元组**”（Triplets）的概念。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: So people usually have this concept of triplets.

</details>

**[主持人]**: 三元组。

<details>
<summary>Original English</summary>

**[Host]**: Triplets

</details>

**[Dhravya Shah]**: 他们有“主语-谓语-宾语”。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: where they have

</details>

**[主持人]**: 宾语-谓语-主语。

<details>
<summary>Original English</summary>

**[Host]**: object predicate object.

</details>

**[Dhravya Shah]**: 没错。或者实体-关系-实体。我们认为三元组实际上会导致性能变差，因为你必须遍历它们很多次才能获得任何信息。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Exactly. Object predicate object or entity relation entity and we think that triplets actually lead to worse performance because you have to traverse them a lot to get to any information and

</details>

**[主持人]**: 这是每个做图谱的人最终都会学到的教训。

<details>
<summary>Original English</summary>

**[Host]**: this is the learning of every graph guy ever.

</details>

**[Dhravya Shah]**: 没错。所以为了发现“Dhravya 喜欢什么食物”，你必须首先找到实体 Dhravya，然后你必须遍历一两层深度才能发现“Dhravya 喜欢食物，喜欢这个东西”等等。这导致了极其缓慢且不必要的开销。所以我们构建了自己的知识图谱，构建了自己的提取流水线。我觉得消费者应用可能不再是重点，核心基础设施现在更有用，那是我们现在的核心业务，也是我们提供的服务。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Exactly. Exactly. Okay. So you have to like to so to find out like okay what what food does dra like you have to first get to the entity DA and you have to traverse one or two layers deep to find out like okay D likes food enjoys this thing etc etc and that leads to extremely slow and like this is just unnecessary. So we built our own knowledge graphs we built our own extraction pipeline and I was like this consumer app is probably not useful anymore. this core infrastructure is more useful now and that is our core business now and that's what we offer.

</details>

**[主持人]**: 惊人的更新。我觉得我们可以更深入地探讨一下。现在的 Super Memory 是什么样的？它是一家云业务公司吗？是一家 VC 支持的公司吗？你是一个年轻的创始人，给人们多介绍一下公司本身和现状，因为显然我们刚才花了很多时间讲背景。

<details>
<summary>Original English</summary>

**[Host]**: Amazing update. Um I think one of those things where like I think we can get more into it. Uh what what is super memory today? Like is it a cloud business? Is it a VCbacked company? You know you're you're a young founder like tell people more just about the company itself and and what it is today because obviously we spend a bunch on the background. Yeah.

</details>

**[Dhravya Shah]**: 好的。我本该早点做自我介绍的，我叫 Dhravya，今年 20 岁。在此之前，我在几家公司（包括 Cloudflare、High Fury 等）从事 Agent 和数据库等工作。我有两家公司被收购，然后来到了美国。我再次构建了 Super Memory，去年融资了 **$300 万**。从那以后，我们成了一家 VC 支持的云业务公司，实际上大部分是开源的。我们试图为 AI 时代构建**上下文基础设施**。

我所说的上下文基础设施是指 Agent 所需的任何外部上下文，包括从检索到用户理解、记忆、自我提升、自我学习以及个性化。我们在 Super Memory 这一个工具中提供所有这些功能。因为我们组织数据的方式，我们可以自动提供所有这些维度，因为每个记忆用例都需要不同的实现方式。我们为开发者提供 API，但也保留了一个面向消费者的应用。其理念是你可以拥有自己的记忆，并将其应用到你使用的所有东西中，或者你可以将 Super Memory 添加到你的 Agent 中，让它更擅长记住事情。

例如，**OpenClaude** 最近很火，**Claude Code** 也火了，获得了 200 万次曝光。这两者都是我们提供的面向消费者的插件。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah. Uh well I I should have done this before but uh All right. I'll give a little bit of an intro about myself first. So I'm Draville. I'm currently 20 years old. Before this I was working on agents and databases and a bunch of other things at a few companies including Cloudflare, High Fury and others. I had two companies acquired and came to the US. So I built super memory again as this thing raised $3 million um last year and since then we have been a VC backed cloud business that's mostly open source actually and we are trying to build a context infrastructure for the AI era and so what do I mean by context infrastructure whatever external context or like that the agent would need including just retrieval to like user understanding memory etc like self-improvement self- learning personalization We provide all of these in this one single tool which is super memory because the way we structure the data we can automatically provide all of these facets because again every single memory use case would require a different way of implementing it. Um and so we do that for developers. We provide an API for people to use, but we also still have a consumerf facing app which the the idea is that you have your own memory that you can utilize across everything you use or you can add soap memory to your agent to make it much better at remembering things. So for example, the open clothing was blowing up or claw code blew up as well. It got like 2 million impressions. Um both of them were kind of this consumerf facing like plugins that we offer.

</details>

### OpenClaude 的记忆系统为什么“掉链子”？

**[主持人]**: 看着这一切真的很令人印象深刻。我想很多人，我会把 OpenClaude 放在这个视频的标题里。让我们直接谈谈 OpenClaude 的事情。Super Memory 还有很多可以聊的，人们可以去查看你发布的很多资料。但当下的热门话题是，好像是 Peter Levels 还是谁，有人在使用 OpenClaude 的记忆功能时遇到了问题。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, it's uh it's really impressive to watch. I think a lot of people I'm gonna put open call in the in the title of this thing. Let's let's go right into the open call thing. You know, there there's there's more to go into super memory. I think more people can check it out. You've published a lot of stuff. But the topic of the moment is I think was it Peter levels or something? Somebody was having problems with open call memory.

</details>

**[Dhravya Shah]**: 每个人，每个人都在抱怨。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Everyone everyone has been

</details>

**[主持人]**: 然后他们会说，好吧，那该怎么做呢？然后会有各种不同的答案，我就觉得，哇，这真的还没被解决。

<details>
<summary>Original English</summary>

**[Host]**: and then they're like, well, okay, how do you do it? And then and then there's like all these different answers and I'm like, wow, this is really not solved.

</details>

**[Dhravya Shah]**: 是的，没错。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah, exactly.

</details>

**[主持人]**: 好的。告诉大家发生了什么。

<details>
<summary>Original English</summary>

**[Host]**: Okay. Okay. So, so tell everybody what what's going on.

</details>

**[Dhravya Shah]**: 好的。我们先来谈谈 OpenClaude 目前是如何处理记忆的。我为我的文章准备了一个小的 Claude Artifact。OpenClaude 无论是通过 QMD 还是你使用的任何记忆插件，本质上都依赖于**工具（Tools）**来搜索它准备的这些 `memory.md` 文件。比如，Agent 会决定去搜索“我当时对 API 做出了什么决定”，有时它会决定不去搜索，这可能是这里最大的问题。然后它会得到一些结果，进行评分，最后返回。

目前的这种搜索是针对 `memory.md` 文件或记忆文件夹。如果 Agent 决定不显式地记住某些事情，它就永远不会出现在结果中，因为你不知道在注入时该记住什么。

所以这里有一系列问题。因为这些文件是**静态**的，它们不处理更新。它们不处理我提到的遗忘机制，也没有时间推理。你无法查看文件的特定部分，因为你不知道什么东西在哪里。这就是为什么每个人都在抱怨 OpenClaude 的记忆功能。

这让我感到惊讶，因为当人们抱怨或当 OpenClaude 推出记忆功能时，人们并没有深入研究它究竟是如何运作的以及为什么不好。所以我们做了所有的挖掘工作，我们在想什么是做记忆的正确方式。我们已经有了针对 Claude Code 和 OpenClaude 的插件，所以我们对于 Agent 应该如何保持**有状态**（stateful）有很多心得。

我们基本上把基于工具的方法转变为基于**挂钩（Hooks）**的方法，它实际上是从 Super Memory 的图谱中读取数据，从而保持内容的**新鲜度**。所以它能处理更新等等。现在，对于每一个工具调用或每一条用户消息，挂钩会自动动态注入价值不到 2000 个 token 的信息。所以整个上下文不会包含超过 2000 个 Super Memory token，如果需要更多信息，它还可以选择进行工具调用。我们还内置了冲突解决、时间推理等功能。无论如何，信息永远是真正新鲜的。这就是要点。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: All right. So, let's first talk about how OpenCL claw currently handles memory. And I have like this little claw artifact that I prepared for my article. But so the way OpenClaw has with QMD or with whatever memory plug-in you use, it it inherently relies on tools to search through these memory. MD files that it prepares. So you know like what did I decide about the API then agent will decide to search and sometimes it won't decide to search which is probably the biggest problem here and then it will get some results it will do some scoring and then it will return it back. So and this search right now is through the memory MD files or the memory folder. So if you if the agent decides to not remember things explicitly, it will never show up in the results because you don't know what to remember at injection time. So there's a bunch of issues here. And because these files are static, they don't handle updates. They don't handle uh like the forgetfulness I was talking about. There's no temporal reasoning. You cannot look at particular parts of the file because you don't know what is where and other problems like that. This like you know this is the reason why everyone is complaining about open clause memory. This to me is surprising because when people complain about open clause memory or when openclaw even did the memory people didn't like look into how exactly and why it's bad. So we did all of this digging in and we were like okay what is the right way to do memory and we already had these plugins for cloud code for open code. So we had a lot of learnings about how agents should be stateful. So we basically turned the tools based approach to hooks based approach that actually is reading from the soup memory graph which keeps the content fresh. So it handles updates etc etc. So now you know for every tool call or for every user message a hook automatically will put less than 2,000 tokens worth of information dynamically. Um so the entire context will not have more than 2,000 super memory tokens and optionally it could also do a tool call if it needs more information and we have like contradictions resolution we have temporal reasoning and all of that built in. So the information is always truly fresh no matter what. That's the gist of it.

</details>

### 基于挂钩 vs 基于工具

**[主持人]**: QMD 是 Toby Luca 开发的，非常令人印象深刻。Toby 基本上想让所有东西都在本地运行。而你显然是 Cloudflare 的狂热信徒，你都要在 Cloudflare 上做吗？（笑）

<details>
<summary>Original English</summary>

**[Host]**: QMD is is from Toby Luca which is like really super impressive. I think it's a very interesting basically Toby wants to do everything locally. You you obviously are Cloudflare Maxis. are you going to do on Cloudflare? [laughter]

</details>

**[Dhravya Shah]**: 是的。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah.

</details>

**[主持人]**: 所以显然这是根本不同的东西。我认为**基于挂钩**（hook-based）可能是对的，因为模型显然会犯错。当我使用 xAI 的 Grok 而它不去搜索推文时，我会感到非常非常沮丧。伙计，我用 Grok 的唯一原因就是它能搜索推文。

<details>
<summary>Original English</summary>

**[Host]**: So obviously that's like a fundamentally different thing. I think hookbased is probably right because obviously models make mistakes and I get very very frustrated when like I use Grock in XAI and it doesn't search tweets. Like I'm dude there's only one reason I use Grock is it search tweets.

</details>

**[Dhravya Shah]**: 是的，你必须像求它一样说“请使用这些工具”，而大多数 OpenClaude 用户甚至不知道工具是什么。所以他们不想考虑工具的问题。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah, you have to like ask it like please use these tools and most of the open claw users don't even know that tools are a thing. So they don't want to think about the tools. So yeah.

</details>

**[主持人]**: 你认为他们不够专业吗？我是说……

<details>
<summary>Original English</summary>

**[Host]**: Do you think do you perceive that they're not technical? I mean is

</details>

**[Dhravya Shah]**: 你知道的……

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: so you know

</details>

**[主持人]**: 尤其是很多人在工程意义上很专业，但在 Agent 领域并不专业。我认为我们现在处于一个巨大的泡沫中。

<details>
<summary>Original English</summary>

**[Host]**: especially you know a lot of people have been seeing they're technical in the engineering sense but they're not technical in the agents world. I think we're in a huge bubble right now

</details>

**[Dhravya Shah]**: 他们根本不知道幕后发生了什么，甚至不会去深究。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: and like they won't know that okay this is exactly what's going on behind the scenes like they would not even look into it. Um so yeah

</details>

**[主持人]**: 只是好奇，因为作为一个工程师，你应该——显然你和我都会认为这是唯一有趣的事情，但你知道，还有很多其他工程师有真实的现实生活。

好的，除了这个之外，Cursor 和 Claude 的那些家伙一直在谈论另一种记忆讨论，即**基于文件系统的记忆**，对吧？你只需把一堆东西丢进你的文件系统里。

<details>
<summary>Original English</summary>

**[Host]**: it's just curious because as an engineer you should this is obviously you and I think that this is the only thing that's interesting but uh you know there's many other engineers who have real life. Yeah. So, so okay, I think other than this there's another memory discussion that I think cursor and claude those guys have have been saying which is like sort of file system based memory right like where you just you put you dump a bunch of

</details>

**[Dhravya Shah]**: 无论是什么空文件丢到文件系统，然后封装在上面。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: whatever empty to your file system and then you wrap over it and

</details>

**[主持人]**: OpenClaude 有一些压缩机制，对吧？比如一些日志、一些心跳（heartbeat）之类的。你对这些有什么看法？

<details>
<summary>Original English</summary>

**[Host]**: open claw has some compaction right like some journal some heartbeat stuff what are your takes on all those things

</details>

**[Dhravya Shah]**: 我认为文件系统记忆在很多情况下实际上是正确的方式，比如对于大多数 Claude Code 用户，因为这可能是最合适的事情。但你仍然面临同样的问题：你必须知道该记住什么，它才能记住。你必须显式地提到“请记住这个”或者“请把这个调出来”，而且它受限于文件本身。文件会变得越来越长，这成了一个问题。所以你必须拆分成很多文件，而这些文件仍然没有任何更新逻辑等等，除非你显式地让 Agent 这么做。

它们的遍历速度也非常慢。你必须进行“Agent 式探索”才能找到任何上下文来回答任何问题。例如，如果我有类似于“实现这个工作流”的任务，它必须先查看记忆中已知的所有内容、所有工作流等等，然后才能得出答案。

现在，我觉得这是一个非常激进的观点，但我认为他们可以做两件事：一是**个性化**（我正在谈论的），二是**代码索引**。他们可以索引代码，Cursor 做了，但 Claude Code 没做。我相信这也是因为他们没有动力去通过让终端用户使用更少的 token 来省钱，因为他们只是把索引成本等转嫁给了用户运行 Agent 所花费的 token 和时间，这正是他们想要的。所以理论上你可以添加代码索引，你可以添加个性化，它会变得更好、更快。

我不只是随口说说。我们昨天刚运行了一个基准测试。我发布了这篇博客，我再分享一下屏幕。我发布了这个极其专业的技术报告，也火了。我们针对三个东西运行了 LongMemEval 基准测试。

Claude Code 的表现最差，OpenClaude 稍微好一点，而 **Super Memory** 是最高的。你可以看到有非常显著的差异，几乎达到了 50%。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: so I think file system memory is actually the right way to do things in a lot of cases like for most claw code users because that is probably the right thing to do. But you still have the same problem of you have to know what to remember in order for it to remember things. So you have to explicitly mention that okay please remember this or please bring this up and it's limited by the files themselves. So the files can get longer and longer. So that becomes a problem. So you have to split between many files and the files still don't have any update logic etc etc unless you explicitly have the agent do that. They're also really slow to traverse through. So you'll have to do agentic discovery to find out any context to answer any question. Like for example, if I have something like implement this workflow, it will have to you know first look through everything it knows in the memory all the workflows etc etc and then it comes to the answer. Now I think this is a very hot take but I think that they could like one is personalization which I'm talking about but then there's also code indexing and they could index the code and cursor does but flot code does not and I believe this is also because they are not incentivized to utilize less tokens by the end user because they're just offsetting the cost of indexing etc etc to tokens and time that the user takes to run the agent which is which is what they want. So theoretically you could add like code indexing, you could add personalization, it would be much better and faster. And I'm not just saying it. We actually ran a benchmark just yesterday. I published this blog. I'll share my screen again. Um I published this like extremely technical report which also kind of blew up but we ran a benchmark on long against three things. Oh, the screenshot is in one of the code tweets I think. Uh how do I view quotes? Twitter UI keeps changing here. Um so the claw code one performs the worst and open class slightly more than that and super memory is the highest and you can see that you know it's like a pretty significant difference like almost 50%.

</details>

### MemoryBench：让基准测试透明化

**[主持人]**: 让我澄清一下，这是你对 Claude Code 方法的复现，以及你对 OpenClaude 的复现，还是你实际使用了它们？

<details>
<summary>Original English</summary>

**[Host]**: Let me let me clarify this is your reproduction of the cloud code method and your reproduction of open claw or you actually use cloud code.

</details>

**[Dhravya Shah]**: 不，是我们的复现。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: No it is our reproduction. So it's like pretty much

</details>

**[主持人]**: 这一点很重要。

<details>
<summary>Original English</summary>

**[Host]**: important I say yeah

</details>

**[Dhravya Shah]**: 确实很重要。而且你知道，我们也认为基准测试不应该被完全信任，也不能被完全信任。

所以，实际上你不该听我的。为此我们构建了这个开源的基准评估平台，就像 Groq 的 OpenBench 一样。它叫 **MemoryBench**。这是我们对它们具体做法的实现。事实上，我们甚至深入研究并用同样的公式、同样的逻辑实现了 OpenClaude 的**混合模式**（hybrid method）。你可以查看 PR 来了解具体的做法。

简而言之，MemoryBench 是一种在相同的基本规则下，针对任何基准测试、任何评测器来测试任何供应商的方法。这让你能量化所有指标：不仅是记忆系统的性能质量，还有延迟、成本以及其他启发式指标，如 Top-K 召回率、NDCG 等。这是做记忆基准测试的一种非常好且简单的方法。我实际上要求每一个竞争对手都使用它，因为它让我们的竞争对手更容易与 Super Memory 进行比较。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: it is pretty important and uh you know we also think that benchmarks should not be trusted and cannot be trusted. So like you know you should not listen to me actually. So we built this open-source kind of benchmarking evaluation platform like Gro's open bench. It's called memory bench which I'll also share my screen. So we like this is our implementation of exactly how it's doing. In fact we also literally like went into it. We implemented open clause hybrid method with the same formula with the same everything and you can just view the PR to find out exactly what's being done. But in short this memory bench is a way to benchmark any providers against any benchmarks against any judge on the same kind of the BL rules and this lets you quantify all the things. So not only the quality of how the memory system performs but also the latency cost and other like you know uristics like the top K recall NDCG etc. So this is like a really good way of doing you know benchmarks for memory and it makes it really simple as well. I actually ask every single competitor to use this because it actually makes it easier for our competitors to compare against soup memory as well.

</details>

**[主持人]**: 是的，我认为这是一个非常好的基础设施。人们应该尝试一下。除了基准测试之外，还有 LongMemEval，它有哪些不足之处？

<details>
<summary>Original English</summary>

**[Host]**: Yeah, I think that's a very good infrastructure. Okay. Yeah, people should try that out. Other than uh just just while we're on the topic of benchmarks and all that, there's long memory val um what's not so good. Whatever you want to say.

</details>

**[Dhravya Shah]**: 是的，我认为我们在记忆基准测试领域还没有达到理想水平，这背后有很多原因。我也可能会写一篇详细的帖子。

我认为 LongMemEval 是一个非常好的基准测试，因为它测试了正确的东西。数据集很棒，一切都很好，除了一个事实：你可以通过“尽可能多地记住东西”来赢得 LongMemEval。提取的记忆数量与你在 LongMemEval 上的得分直接正相关。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah. So, I think we are still not there in the memory benchmarks space and there's a lot of reasons behind this. I might also write a detailed post about this. But I think that long my mal is a very good benchmark because it calculates it tests for the right things. It tests for the right things. The data set is great. Everything is really good in long mual except for the fact that you can win long meal by remembering as many things as possible like there's a direct correlation to the number of memories extracted and the score you get on long meal. Um that doesn't seem bad

</details>

**[主持人]**: 因为……

<details>
<summary>Original English</summary>

**[Host]**: because

</details>

**[Dhravya Shah]**: 是的，这不算太糟，但在现实世界中你会花费更多成本。在现实世界中你不想提取所有东西，因为为了赢得基准测试而进行的提取并不是免费的。所以它对某些用例有好处，但在现实世界中，人们并不期望记忆是这样运作的。所以我们觉得那还行。但 LongMemEval 也不测试遗忘机制，因为你怎么测试某样东西是否应该被遗忘呢？它测试更新，但不测试遗忘和一些其他东西。所以我们仍然使用 LongMemEval，因为那是我们目前拥有的最好的。

然后是 **LoCoMo**，LoCoMo 真的很糟糕，几乎每个人都知道 LoCoMo 不是衡量标准。原因是 LoCoMo 本质上是在测试**检索能力**，而不是在测试真正的记忆。你基本上可以在 LoCoMo 中倾倒所有上下文，然后在最新的模型中获得 100% 的分数。首先，它只有 30 个问题，数据集太小了。其次，它不测试知识升级、时间推理、多会话以及所有其他重要的东西（如偏好）。除了检索它什么都不测。而在 Gemini Flash 或其他模型中，会话本身足够短，你可以把整个会话放入这些上下文窗口中，它立即就能奏效。我认为它现在也太旧了，在那个时代它可能确实有意义，但现在已经过去了三四年，模型已经变得好得多了。

还有 **ConvoMe**，我实际上很喜欢这个。那是 Salesforce 开发的，它测试了更多“助理式”的用例，比如助理应该同时做 RAG 和记忆等等。所以那挺好的。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: yeah it's not too bad but like in real world you would spend more cost like in real world you don't want to extract everything because extraction is not free to win against the benchmarks. So it's good for like some use cases but in the real world that's not how people expect memory to work. So we think that that's fine but long also does not test for forgetfulness because how would you test if something should be forgotten or not? It test for updates but not for forgetfulness and a few other things. So we still use long man well because that's the best we have. Then there's locomo and locomo is like really bad cuz like and and people actually it's not just me like pretty much everyone knows that locom is not the right thing to to say. So the the reason is like locomo is essentially testing for retrieval capacity and it's not testing for the real memory things like you can essentially just context dump everything in locomo and get like 100% in the latest models. So one is the there's only 30 questions like the the data set is really small. Second is it does not test for like knowledge upgrade, temporal reasoning, multi session, all of the the other things like the important things like preferences. It doesn't test for anything but retrieval and and like in Gemini flash or whatever like you can just literally the the questions the sessions themselves are short enough that you can put the entire session in these context lens and it will work right away. So I think and it's also very old now. Like in that age it it probably did make sense but now it's been 3 4 years since that and the models have gotten much better. There's also convo me which I actually like. It's a really good one. It's by Salesforce and it tests for more assistanty use cases like like assistants should do both rag and memory etc etc. So that's pretty good and sometimes you need both which I also want to come to actually but that's what I think about the the the benchmark space.

</details>

### 非字面检索与个性化

**[Dhravya Shah]**: 有一件重要的事情，目前还没有“**用户画像基准测试**”的概念。所有这些基准测试都非常偏向检索。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: There's one important thing which is there's no concept of benchmarking user profiles. So all of these benchmarks are very retrieval heavy

</details>

**[主持人]**: 就像事实性信息。

<details>
<summary>Original English</summary>

**[Host]**: like factual information.

</details>

**[Dhravya Shah]**: 是的。你本质上是想获取某些东西，得到一个答案，回答问题。但那并非所有用例。我很快给你看一张幻灯片，这会让你看得很清楚。

传统上，你会进行这种检索。你得到一个问题，检索一些东西，然后基于此生成答案。但我们认为这对于大多数**非字面意思**的问题不起作用。比如“为我找一个最好的显示器”。如果我从未谈论过显示器（我可能确实没说过），它就不会返回任何结果。它会给你一些通用的回答。但 Agent 可能随时需要知道关于我的很多默认信息，比如“用户是一名 CEO”。但它也需要知道一些**插叙性信息**（episodic information），比如“用户最近筹集了资金”、“上周搬进了新办公室”等等。在这种情况下，它会想：“噢，你整天写代码，而且刚搬进办公室，所以这台显示器可能你应该买，虽然有点贵，但它是最适合你的。”

这只有在你拥有一种极其精简的（比如 500 token）关于用户的信息时才能做到，这种信息同时捕捉了静态特征和最近发生的动态片段。我们在 Super Memory 中内置了这种功能，但目前还没有办法对其进行基准测试。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah. Like you you essentially want to you know fetch something get an answer answer the question. But that's not all use cases. I I'll show you one a slide real quick which will make this very clear. I have it ready right here luckily. So traditionally you have this retrieval thing that happens. So you get a question, you retrieve something and an answer is generated based on that. But we think that it will not work for most nonliteral questions like find the best monitor for me. If I've never spoken about a monitor which I probably have not, it will not return anything. It'll be like oh it'll give some generic answer but agent probably needs to know a lot of default things about me at all times like user is a CEO but it also needs to know some episodic information like user recently raised fund fundraising moved into a new office last week etc etc and in which case it will be like oh you code all day and you just moved into an office so this is probably the one that you should buy it's a little expensive but this is the one for you. And this can only be done if you really have like a very extremely small like 500 token information about the user that captures both the static things and theodic things like some recent episodes that's been going on. And we also have this built into Super Member, but there's no way to benchmark it.

</details>

**[主持人]**: 是的，这基本上是个性化，对吧？所以有点难。好的，我想结束关于 OpenClaude 相关话题的讨论。我想人们正在使用很多东西。还有什么其他问题会出现吗？比如秘密泄露、上下文混淆（如果他们做了类似的事情），你知道，在检索和准确性，或者召回率和准确性之间存在权衡，对吧？

<details>
<summary>Original English</summary>

**[Host]**: Yeah, it's basically personalization, right? So, it's a bit hard. Okay. Uh, you know, I just want to close the loop on anything open claw related. I think people are using a lot of things. What other issues crop up? Like things like secrets, things like context confusion if they've done like similar things, you know, like there's a there's a trade-off between retrieval and accuracy or like recall and accuracy, right?

</details>

**[Dhravya Shah]**: 是的。OpenClaude 的做法是本质上发回对话中的最后 15 条消息，并利用这种往返。这种方法本身并不理想，因为你没有利用任何**缓存 token**。正因为你没有利用缓存，你支付的费用可能比正确做法高出 10 倍。那是 OpenClaude 的一个问题，我们没法做任何事情。

另一件事是人们给予它访问秘密之类的权限，作为记忆系统，我们必须确保没有秘密最终落入我们手中。OpenClaude 的很多用户还连接了浏览器、心跳包之类的，心跳每小时都在发生，这些心跳最终也进入了记忆，造成了一些污染。有些人想让他们的 OpenClaude 记忆和 Claude Code 记忆共享，我们实际上不想那样，它们应该是隔离的。但人们想要那个，所以我们提供了配置召回。

否则，Super Memory 有时最终不会给出正确的结果，这就是为什么我们最近为 OpenClaude 发布了一个新东西，这对我们来说是一个巨大的学习经历，叫做**混合模式**（Hybrid Mode）。在记忆系统中，你想要记住什么之间总是存在权衡。你总是必须准确选择你想记住的东西，这很重要，因为你想保持更新、保持新鲜、遗忘某些东西。但有时你不知道用户会问什么，有时用户会说一些没有被记住、或者当时看起来不那么重要的事情。

那么你如何处理这些情况呢？我们的做法是，因为我们同时做记忆和**托管 RAG**（managed RAG），如果记忆存在，我们会展示记忆，但我们会回退到 RAG 答案。如果某些东西没有被记住，它会返回原始数据块（raw chunk），然后在后台将其也添加到记忆中。这基本上确保了 Super Memory 几乎永远不会忘记任何事情，因为只要用户在询问，我们总是在给 Agent 正确的上下文。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah. So I think like so the way OpenCloud does it is it essentially sends back the last 15 messages in the conversation and it essentially uses that back and forth and I mean the approach itself is not ideal because you will like you are not going any like you're not utilizing any cash tokens and because you're not utilizing the cash you're essentially paying like insanely like 10x more than if you would do it the right way. So that is always a problem. So like we think so that but that's like a open floor issue you you know we cannot really do anything about that. The other thing is people are giving it access to their secrets and stuff like that and we have to like as a memory system we have to like make sure that no secrets end up to us like in any case. Um a lot of users in open cloud claw also have like really like browsers attached and stuff like that and heartbeats and heartbeats are all going on you know every hour and the heartbeats are also ending up in memory causing some pollution and some people want to use their open claw memories along with their claw code memories and we actually want don't want to do that like it should be siloed like it's their own things but people want that so we are offering configuration recall Otherwise like you know super memory sometimes does not end up giving the right results and that's why we recently shipped a new thing for open claw so it was a a huge learning experience for us so it's called hybrid mode there's always a trade-off between what you want to remember in a memory system you always have to choose exactly what you want to remember which is important because you want to keep them updated you want to keep them fresh you want to forget things but sometimes the user you don't know what the user will ask about sometimes the user will say something that was not remembered it was not very significant. So how do you handle those cases? So the way we do it is we have because we do both memory and like managed rag we can show up the memories if they exist but we have a fallback to rag answers like it will just return the raw chunk if sum did not remember it and then in the background it will add that to the memory as well. So this this essentially gives you like you know like we say that summe should almost never forget anything because of the fact that we are always giving the agent the right context as long as the user is asking for it. So yeah.

</details>

**[主持人]**: 太棒了。这就是混合模式的东西吗？

<details>
<summary>Original English</summary>

**[Host]**: Amazing. Are we going to the hybrid stuff?

</details>

**[Dhravya Shah]**: 是的，这就是混合模式。本质上我们会先返回记忆，如果有任何匹配的原始数据块，我们也会返回那些，以确保 Agent 拥有足够的信息来回答问题。目前没有其他供应商这样做。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah. Yeah. So this was the hybrid stuff. So essentially you we'll return the memories first and then if there's any raw chunks that match up we also return those to make sure the agent knows just enough information to answer the question. And no other provider does this right now. So yeah.

</details>

### 优化至 100 万 token 仅需 2 美分

**[主持人]**: 成本有多重要？我的感觉是人们对成本非常不敏感，但显然任何真正的工程师都会关心缓存命中率之类的事情。我不知道，人们在意吗？

<details>
<summary>Original English</summary>

**[Host]**: How how important is cost? Like my perception is people are very cost insensitive but you obviously like anyone who's like a real engineer um does care about cash hits and all that. Uh I I don't know I don't do people care.

</details>

**[Dhravya Shah]**: 是的，我认为人们实际上非常在意成本。我认为我们处于一个巨大的泡沫中，我们的很多用户，特别是那些专业用户，确实在意成本。因为人们会将记忆系统与他们使用的 LLM 进行比较。如果记忆系统的价格是 100 万 token **$10**，而他们使用的 LLM 是 100 万 token **$2**，他们会觉得：“噢，这用起来没道理，太贵了，我不该用这个。”这种情况确实会发生，我们要确保给他们带来很多满意度，让他们在使用记忆时感到快乐，而不是担心成本。

所以对于我们来说，我们已经将基础设施优化到 100 万 token 的成本仅为 **2 美分**，因为我们拥有自己的模型、自己的数据库，拥有自己的一切。所以我们给用户的定价也非常低。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah I think people care a lot about cost actually. Okay. Like I think again we are in a huge bubble and a lot of our users especially like you know they do care about the cost because like because people would compare a memory system against the LLM they use. So if the memory system is you know $10 for a million tokens and the LLM they use is $2 for a million tokens, it will be like oh like this does not make sense to use. It's too expensive. I should not use this. And this happens to us and we want to make sure that like we're giving them a lot of you know lot of satisfaction on like they should be happy about using memory and it should not be something that you know they have to be concerned about. So for us we have optimized our infrastructure down to it cost us 2 cents for a million tokens because we have our own model our own database our own everything. So we have to price our users also really low which we do. So yeah.

</details>

### 2026 年展望：语音 Agent 与深度个性化

**[主持人]**: 好的，太酷了。这是一场关于记忆、记忆现状以及关于评估等侧面讨论的高质量大师课。Super Memory 接下来的计划是什么？2026 年人们应该关注哪些开放方向？

<details>
<summary>Original English</summary>

**[Host]**: Okay cool. It's a really good sort of master class in everything sort of memory uh state of memory including a side tangent on on evals and all that. What's next for super memory like what is sort of the open directions uh for 2026 that people should think about?

</details>

**[Dhravya Shah]**: 是的，2026 年是我们意识到记忆的“专业消费者”（prosumer）方面是人们非常兴奋的一年。这种“拥有一个可以连接到任何地方的记忆，可以在不同供应商之间互操作”的想法很受欢迎，我们将继续做这样的事情。我们今天就要发布 **Cursor 插件**，我们已经有了针对 Claude Code 和 OpenClaude 的插件。

接下来，我们将发布针对**语音 Agent** 的功能，与几乎所有的语音 Agent 公司合作，因为 Super Memory 运行速度非常快，非常适合语音场景。那会很棒。我们在评估方面也会做更多工作，构建我们自己的评估系统。我们将深入研究个性化，因为我们认为目前还没有人在个性化方面做大量工作。我们还在构建我们数据库的新版本。所以，这会非常令人兴奋。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah, so 2026 was the year we realized that the proumer aspect of memory is something that people are really excited about. like this idea of having this one memory that you can connect everywhere you can interop between providers and stuff like that and we are continuing to do things like that like we're going to launch the plug-in with cursor today and we already have the claw open claw open code all of those that's good next up we are going to do a launch on voice agents partnering with pretty much every voice agent company because of the fact that super memory is so fast at at the work it does so it's really good for Um that would be amazing. We're doing more on evals. We're building our own eval. We are going going deeper into personalization because we think that no one has done a lot of work in personalization yet and a lot of other like we are building a new version of our of our database. So yeah, it's it's going to be really exciting.

</details>

**[主持人]**: 太酷了。谢谢你能来。我认为这对于 Lane Space 的听众来说，是对 Super Memory 的一个很好的介绍。显然你通过自己的项目已经相当出名了。我已经邀请你参加 World's Fair 了，我们会在那里看到你做更多的演讲。总的来说，我开始看到真正的初创公司和人们开始认真对待记忆，相比两三年前全是向量数据的时代，现在进步很大。

<details>
<summary>Original English</summary>

**[Host]**: Cool. Well, thanks for jumping on. I think this is uh a great introduction at least for space listeners to Super Memory. obviously like you've been plenty famous on your own with your with your projects, but I I think I already invited you to World's Fair. We'll see you like do more talks for for that kind of stuff. And I think just generally I'm starting to see real startups and people taking memory seriously compared to two three years ago when it was all like vector data.

</details>

**[Dhravya Shah]**: 那时简直是个笑话。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: That was a joke.

</details>

**[主持人]**: 我认为这真的很好。未来还会有更多东西。我想 LangChain 也有他们自己的看法。

<details>
<summary>Original English</summary>

**[Host]**: Uh I think it's really good. Uh there's there's more coming, you know. I think Lchain has their own take.

</details>

**[Dhravya Shah]**: 是的。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Yeah. You know, I think all all the others

</details>

**[主持人]**: 还有 Letta、Mem、Zep。

<details>
<summary>Original English</summary>

**[Host]**: there's letter chain mem Zap. Yep.

</details>

**[Dhravya Shah]**: Letta 和 Zep 都举办过研讨会，所以我想现在轮到你了。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Both Leta and Zep have done workshops, so I think it's your turn.

</details>

**[主持人]**: 期待。好的，太酷了。很高兴能和你交流，网上见。

<details>
<summary>Original English</summary>

**[Host]**: Yep. [laughter] Looking forward to that. Okay, cool. Um, good to catch up and I'll see you online.

</details>

**[Dhravya Shah]**: 太棒了，非常感谢。

<details>
<summary>Original English</summary>

**[Dhravya Shah]**: Great. Thank you so much.

</details>

[music]