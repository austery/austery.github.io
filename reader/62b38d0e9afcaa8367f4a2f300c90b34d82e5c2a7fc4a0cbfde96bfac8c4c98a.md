---
author: How I AI
date: '2026-07-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KtmaWUVdnx4
speaker: How I AI
tags:
  - agentic-workflow
  - autonomous-coding
  - context-management
  - software-engineering
  - linear-integration
title: 用手机远程调度自主 AI 编程智能体：OpenAI Symphony + Linear 深度实战访谈
summary: 本期访谈中，Kernel Labs 创始人、Latent Space 播客联合主持人 Alessio Fanelli 详细分享了他如何利用 OpenAI 的 Symphony 框架结合 Linear 任务管理系统，构建在云端 VPS 运行的自主 AI 编码与工程任务流，实现“用手机或 Slack/Linear 随时下发指令、智能体自动提交 PR、人类只需评审”的开发管理范式；并分享了 AI 在线下的实体业务（如高价值宝可梦卡牌扫货定价、传统海鲜配送库存盘点、个人图书整理等）中颠覆传统的低效人工流，推动小型企业与个人数字化生产力的创新探索。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Alessio Fanelli
companies_orgs:
  - OpenAI
  - Linear
  - Kernel Labs
products_models:
  - Symphony
  - Codex
media_books:
  - The Monk and the Riddle
  - Divine Comedy
status: evergreen
---
### AI 改变生产生活与小微企业自动化前景

**克莱尔·沃 (Claire Vo)**: 这其实是我最喜欢的 AI 带来的积极成果之一，也就是小微企业的创立与效率提升。那种能够以一种过去在历史上极其低效、而现在却能非常自然地与物理世界进行交互并重构商业流程的能力，对我个人来说，真的是一种极大的生活质量提升。

<details>
<summary>Original English</summary>

**Claire Vo**: This is my favorite positive outcome of AI, which is small business creation. Just the ability to like intersect the human world in a way that has been historically very inefficient has been a quality of life improvement for me.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 没错，比如我父亲，他们的企业是向餐馆配送鱼类海鲜的。他们有一个装满冷冻食品的冷冻库，还有一些新鲜海鲜。过去每天早上都会有人拿着纸和笔走到库房里，逐项记录那里有些什么货物。有时候他们会突然惊呼：“噢，我的天啊，我们好像漏记了三条金枪鱼！”或者“我们少了一箱大虾！”现在，所有这些繁琐的盘点工作都可以轻松地被自动化。甚至不需要多么复杂的设备，仅仅通过一副 **Meta 智能眼镜** 或者其他带有视觉识别的随身设备，就能自动把库房里的库存扫码并录入系统。

<details>
<summary>Original English</summary>

**Alessio Finelli**: You know, my dad, their business, they deliver fish to restaurants. They got like this freezer with the frozen stuff and like some fresh fish and like somebody's going out there with like the pen and paper every morning kind of like writing down what's there. Sometimes they're like, "Oh, my god, we're missing like three tunas or like we're missing a box of shrimp." All of that work now can easily be automated even with just with the magic glasses or something else.

</details>

**克莱尔·沃 (Claire Vo)**: 确实如此。我们今天还有另一个使用案例要展示，这个案例是我那 9 岁的孩子最想看到的。那么，让我们来展示我们那个利用 AI 来搜寻和定价**宝可梦卡牌**的趣味案例吧。

<details>
<summary>Original English</summary>

**Claire Vo**: And we have another use case, which is the use case that my 9-year-old wants to see. So, let's do our Pokémon card by AI use case.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 好的。在这个案例中，我将 **Codex** 主要用于两件事。第一件是获取 **PSA 证书** 编号，以便能够追踪每一个评分等级的具体卡牌数量。接下来的另一项工作与实体卡牌交易相关。当你去参加所有这些卡牌交易展会时，会有成群结队的人向你走来，向你推销他们的卡牌，你必须在现场实时对这些卡牌进行估价。整个过程以前超级低效，因为大家都在现场用手机在 **eBay** 上手动搜索每一张卡，或者去像 **TCGPlayer** 这样的玩家交易平台上去查历史交易记录以获得最新报价。实际上，你完全可以使用 AI 自动执行这些查询和匹配过程，从而为真实的人节省大量的现场等待时间。

<details>
<summary>Original English</summary>

**Alessio Finelli**: So, I use Codex for two things. The first one is like getting the PSA certificates to keep track of a specific number for each grade. Then the next thing I'm working on is when you go to like all these trade shows, people are coming to you, they're selling you cards, and you got to price them in real time. The whole process is super inefficient because people are like searching each card manually like on eBay or like this DJ player getting the number. You can actually use AI to save clock time for real people by doing these things autonomously.

</details>

---

### 从“智能体提示词编写者”到“智能体管理者”的转变

**克莱尔·沃 (Claire Vo)**: 欢迎回到 *How I AI*。我是克莱尔·沃，一名产品负责人，也是一个致力于帮助大家利用这些新工具构建更好产品的 AI 狂热爱好者。今天，我正与 **Kernel Labs** 的创始人、同时也是 **Latent Space** 播客的联合主持人阿莱西奥·法内利进行交流。他将向我们展示他是如何利用 OpenAI 的 **Symphony** 框架和 **Linear** 项目管理工具，来完全自动化他所有的日常工程任务；以及他是如何让 Codex 智能体在网上替他去搜寻并挑选那些价格极其昂贵的宝可梦卡牌的。让我们直接进入正题。

在正式开始之前，先插入一段我们今天的赞助商 **Firecrawl** 的广告。如果你目前正在构建 AI 智能体（AI Agents），你可能也遇到了相同的痛点：你的智能体需要从网页上获取数据，但是正确的页面极其难找，要么深埋在复杂的 JavaScript 异步渲染之后，要么被登录墙阻挡。Firecrawl 是一款专门的网页数据 API，它能让智能体以极大的规模去搜索、爬取网页并与之交互，获取干净、结构化的数据，以便你的 Agent 能够直接使用。包括我自己在内的超过 100 万开发者都在基于它进行构建。它是开源的，且可以免费开始使用。别再为了获取网页数据而与各种反爬机制苦苦挣扎了，立即访问 **firecrawl.dev**，使用代码 `how I AI` 即可在今天获得 10,000 个免费积分。

阿莱西奥，我今天非常兴奋能看到你的演示。因为我认为我们听过太多人高谈阔论如何在整个项目里自主编排多个智能体，但我们实际上很少看到有人真正把这套流程落地并跑通。我依然看到很多人在做大量的提示词工程，即使他们是将提示词放入一个循环、一个目标或者一些会派生子智能体的框架中，人类实际上依然被重度绑定在这个循环中。因此，我非常希望能听听你是如何走到这一步，开始对你的智能体任务进行更加自主的管理的。

<details>
<summary>Original English</summary>

**Claire Vo**: Welcome back to How I AI. I'm Claire Vo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today, I'm speaking with Alessio Finelli, founder of Kernel Labs and co-host of the Latent Space podcast. He's going to show us how he uses OpenAI's Symphony plus Linear to automate all his engineering tasks and how he has Codex goal shopping for very expensive Pokémon cards. Let's get to it.

Quick word from today's sponsor, Firecrawl. If you're building with AI agents, you've probably hit the same wall. Your agent needs data from the web, but the right pages are difficult to find, buried in JavaScript, or blocked behind logins. Firecrawl is a web data API that lets agents search, scrape, and interact with the web at scale and get that clean structured data they can actually use. Over a million developers, including myself, build on it. It's open source and it's free to start. Stop fighting the web for data and start powering your AI agents and apps with Firecrawl at firecrawl.dev. Use code how I AI to get 10,000 free credits today.

I'm excited about what you're going to show us because I think we have heard a lot of people talk about orchestrating many agents autonomously across a project, but we actually haven't seen many people do it. I still see a lot of prompting, even if you're prompting into a loop or a goal or something that spawns sub agents. People are really really still human in the loop. And so, I'd love for you to tell us how you came to this point of doing more autonomous management of your agentic tasks.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 好的。我在大约三年半前创办了 *Latent Space* 播客，我的联合主持人就在这里工作。他当时开发了一个叫做 **Small Engineer** 的项目，这在当时算得上是首批实现自主化编码探索的尝试。随着时间的推移，大家发现它一直是一个很酷的 Demo，但在当时，底层的 AI 模型性能还不够强大，无法真正去执行那些长时间运行的复杂任务。但在过去的一年里，情况发生了根本性的变化，我想每个身处这个行业的人都对此深有体会。

而真正让我开窍的契机，是我开始将自己的角色从一个**智能体提示词编写者**（Agent Prompter），转变为一个**智能体管理者**（Agent Manager）。这种角色的转变在具体实践中有很多不同的实现方式。最开始，每个人尝试的都是类似于 **Kanban 看板** 的模式——你把所有的任务都放进看板的待办列里，然后把它们在各个状态列之间来回拖动。但我很快发现，在那种模式下，很难让智能体连续自主运行两轮、三轮或四轮以上的迭代。你在看板上创建任务并启动它是很容易的，但一旦任务运行起来，如果你想在中途进行干预或修正，就变得非常困难。而且在本地运行这套环境也存在很多局限性。

所以，对我来说，最关键的改变是**放弃本地运行环境，转而将智能体的整个运行时部署到云端的 VPS 上**。接着，建立不同的沟通通道来与这些智能体进行交互。你可以直接给智能体发短信，可以通过 Linear 任务卡片与它们交谈，也可以直接在终端里对它们下达指令。在过去的一个月里，Codex 推出了移动云端管理，这进一步方便了移动端的任务调度。接下来，我会带你详细看看我的具体工作流，希望大家能从中获得一些灵感。

<details>
<summary>Original English</summary>

**Alessio Finelli**: I started this podcast called Latent Space 3 and 1/2 years ago and my co-host works here. He built this thing called Small Engineer at the time, which was kind of like the first autonomous coding thing. Over time, it's always been a cool demo, but I feel like the models were not quite as good to really do longer running tasks. Um they definitely changed, you know, in the last year and I think everybody kind of feels the same. And what really clicked for me was like starting to move away from being a agent prompter to kind of be a agent manager. And that has kind of taken a lot of different ways. So, the first thing that everybody tried was kind of like the Kanban board. Uh you would kind of put all these things in there and move them back and forth. What I found is that it was hard to get two, three, four turns through that. Like it was easy to get to the task and kick it off, but then it was hard to intervene on it. And also like having it local just didn't quite work. So, the big thing for me was moving away from um kind of like local runtime to having it in a VPS in the cloud. And then having different channels to talk it to. So, you can kind of like text the agents, you can use linear to talk to them. You can prompt them directly in the shell. And this is also like something that I guess like in the last month, you know, Codex also added Codex mobile cloud is also adding kind of like the the mobile management, but I'll kind of run you through what I do. And then maybe people get some inspiration from it.

</details>

**克莱尔·沃 (Claire Vo)**: 太棒了。我绝对会从你接下来的分享中受益匪浅，因为我现在正盯着我旁边的四台 **Mac mini** 呢。没错，我目前仍然完全在本地跑我的智能体程序，经常得下楼到地下室去，时不时地把它们唤醒并检查运行状态。

<details>
<summary>Original English</summary>

**Claire Vo**: Great. And I will really benefit from this because I'm staring at my four Mac minis over here. So, I'm still running locally. And I just come downstairs and like kick them alive every now and then.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 确实如此，本地运行太折腾了。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Right.

</details>

**克莱尔·沃 (Claire Vo)**: 所以，我想今天你很有可能会说服我，把我的整套智能体设施全部迁移到云端。让我们拭目以待。

<details>
<summary>Original English</summary>

**Claire Vo**: So, I'm you maybe you'll convince me to move all this to the cloud. Let's see.

</details>

---

### 基于 OpenAI Symphony + Linear 的云端工程协同工作流

**阿莱西奥·法内利 (Alessio Fanelli)**: 好的。为了演示，我准备了一些比纯技术工程更加有趣的实际例子。我在圣卡洛斯拥有一家名为 **Merlion Games** 的卡牌商店，因此，交易卡牌（Trading Cards）是我的个人兴趣和副业之一。

我的云端智能体设置是这样的：我有一个名为 **Zoo** 的系统，它基本上是一个包含特定智能体环境的云端 VPS。这台云端机器配置了 32GB 内存和 4 核 CPU，我把我所有的开发智能体都预先登录并部署在里面。当然，如果你更倾向于开源模型，你也可以在上面部署并运行一些开源模型。

在 Zoo 系统之上，我运行着这套卡牌采购和搜寻服务。在这台服务器上，我配置了 OpenAI 的 **Symphony** 架构。Symphony 本质上是一个非常实用的框架，它能够捕捉并监视项目管理工具中的 Issue（工单/问题），一旦有新的 Issue 产生，它就会自动将这些 Issue 转化为实际的编码运行任务，同时它将 Linear 平台作为团队协作和任务进度的唯一事实来源（Source of Truth）。

在我的 Linear 账户中，我为不同的代码库和项目创建了不同的工程板。比如，其中一个看板叫作 **Power Buyer**。我有时候会通过 Symphony 来开发这个项目，有时候则会直接使用本地的 Codex 或者 **Claude Code** 进行快速修改。

当你点进 Linear 的任何一个任务卡片时，你会看到它包含了我最初编写的原始任务说明（Spec），这通常写得非常简单。一旦我决定要开始这项工作，我只需要在 Linear 界面上把这个任务从“待办”（Backlog）拖入**“待处理”（To Do）**状态。这个状态的变更会立刻向 Symphony 发送信号，指示智能体需要开始解决这个任务。

Symphony 接收到信号后，会自动在 Codex 中开辟一个新的工作区（Workpad）。智能体会针对如何实现该功能制定一份详细的计划，这其中包含了它的设计思路、验收标准（Acceptance Criteria）以及不同的验证步骤。Symphony 项目的根目录下会有一个名为 `workflow.md` 的规范文件，智能体就是在这个文件的指导下，明白自己在各种开发场景下应该做什么。

接着，智能体就会开始在云端写代码并跑测试，当它认为开发完成时，它会自动在 GitHub 上提交 Pull Request，并将 Linear 上的卡片状态自动推送到**“人工评审”（Human Review）**状态。

在这个阶段，作为人类开发者的我，就可以直接在 GitHub 上评审它提交的 PR。如果我发现问题，比如某段代码写得太臃肿，我可以像评审普通人类队员的代码一样，在特定的代码行下添加评审意见（Comments）。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Yeah. So, I tried to use some more fun examples for it than like the meta one. So, I own a car store in San Carlos called Merlin Games. And so, one of my interest is trading cards. So, my setup is I have this thing called Zoo. Zoo is basically like an agent plus a VPS. So, this machine, for example, is like, you know, 32 gig of RAM, four cores. I have all my coding agents pre-logged in in here. And you can also use some of the open source models if you want. And what I have here is kind of like the sourcing thing where you can basically use it as your own server. On this, I have the OpenAI Symphony setup. So, Symphony is basically a I mean, you can kind of look it up for a better description, but it's kind of like a loop for turning issues into coding runtime and then having kind of like linear as a source of truth for it. So, what I have on my linear, I basically have all these different projects. So, this one is power buyer, for example. And I work on it sometimes in through Symphony, sometimes I work on it through Codex directly or clock code directly. And if you go into any of these things, basically what you see is you have the original task. So, this is what I've wrote as the initial spec, which is, you know, pretty simple. Then I'll basically move it from here to to do. So, this tells Symphony it needs to work on it. What Symphony does, it creates a Codex workpad. So, the agent kind of makes a plan on how to implement it. And it has a plan, it has a acceptance criteria, different validations. And Symphony has a file called workflow.md, where you basically explain how what what it should do for this. Uh this will kind of go to work and then eventually we'll move it to human review. So, what you can do here is review it on GitHub, and you can add Let me open the PR. I'll show you. You can add all these different comments, you know, I guess now

</details>

**克莱尔·沃 (Claire Vo)**: 看来这些历史评论现在都已经被智能体解决并关闭了。

<details>
<summary>Original English</summary>

**Claire Vo**: They're resolved.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 是的，它们全都被解决了。当时我写了一些评审反馈，比如“这段代码写得太长了”等等。当我提交了这些 GitHub 评论后，我只需要在 Linear 看板上把对应的卡片状态拖回到**“重新修改”（Rework）**。

一旦任务状态被更新为 Rework（我们在录制这期播客的同时就可以当场触发一个），Symphony 就会自动分析你在 GitHub 上留下的所有 Code Review 意见，并自动生成一份详细的“返工检查清单”（Rework Checklist）。它会准确指出哪些行代码存在什么问题，并详细列出应该如何逐行解决这些问题。随后，它会再次自动开展修改工作，直到重新修复完毕提交，并在代码最终并入主分支（Merge）后，把 Linear 任务卡自动标记为**“已完成”（Done）**。这就是整个闭环的工作流。

作为管理者的我，甚至不需要去一行行查阅智能体的底层执行痕迹（Traces），我只需要在宏观上指导智能体去解决对应的 Issue 即可。所以，哪怕我当时人在外面，我也可以掏出手机，在 Linear 的移动端界面上查看项目状态。

例如，如果我们发现当前的卡牌列表界面看起来信息有点杂乱，我可以直接用手机在 Linear 上新建一个任务，写上：“清理界面，使其更加稳定。移除 Spread（差价）列，这列信息太嘈杂了。同时，把卡牌的系列名称（Set Name）变成可点击的超链接，以便我可以快速点击跳转查看同系列的其他卡牌。”接着，我只需要把这个任务随手扔进“待处理”列，然后点击“创建任务”。

每一个在云端运行的 Symphony 实例都有其专属的监控面板。我这里展示的就是 **TCG Buyer** 这个项目的面板，上面能清晰看到之前已经运行完毕以及当前正在后台静默运行的各种开发任务。

另外，我最近在做的一件事是尝试估算：让 AI 去自主编写软件，其最终的账单成本究竟是多少？

大家都知道智能体可以自动帮你写代码，但在很多时候，我们很难提前预估这个任务需要消耗多少个 Token，因此很难去衡量让智能体做这件事情到底合不合算。你可以在面板上看到，我们的大多数常规修改任务可能只花费 15、30 甚至 60 美分左右的 Token 费用；但你看这一项复杂的重构任务，它居然消耗了惊人的 **2.21 亿个 Token**！

<details>
<summary>Original English</summary>

**Alessio Finelli**: They've been resolved. This is like too long, blah blah blah. And then you just move it to rework. So, once you move it to rework, and then we'll do we'll do we'll kick one off while we record this. Uh it creates a rework checklist. So, it goes through all the comments and it's like, okay, um these are all the things that went wrong, kind of addresses them. It tells you how to address them line by line. Um moves it back to rework. Um to from rework to done once it gets merged. And that's kind of like the flow. I don't really look at the traces one by one. I just kind of direct the um the agent to work on it. So, whenever I'm even if you're outside, right? Like I might be on on my phone and I'm looking at something here. And uh let's say here we're like, hey, this is kind of like noisy. Um what I can do is like I can create a new task. I say clean up bring me stable. Let's remove the spread column. It's too noisy. Let's also make the set name clickable. So, I look at that other cards. And here I'll simply put it in to do. Create issue. And then each of these Symphonies has its own dashboard on it. So, this one is TCG bar buyer. These are previous tasks that are running. So, one of the things I'm also trying to do is trying to figure out how much is software going to cost to build. So, I think people understand the idea of like the agents write it, but sometimes it's hard ahead of time to know how many tokens it's going to take and so it's hard to price and understand what it's actually worth doing. So, as you can see most of these tasks are kind of like, you know, 15, 30, 60, but then this one is like 221 million tokens.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 我们点进去看看，这个任务当时的目标是“将应用重构为可以直接一键部署在 **Vercel** 上的版本”。这个项目最开始完全是作为一个本地脚本运行的。为了让它跑在 Vercel  Serverless 环境下，智能体必须重写底层的整个存储逻辑、更改所有的请求和路由处理机制等等。这确实是一个规模非常庞大的重构工程，所以它消耗了巨大的 Token 数量也在情理之中。

通过记录这些数据，我们在未来就可以开始评估：如何通过增加一些中间验证机制、提供更清晰的规范描述文件，或者提供更好的周边辅助工具，来让智能体开发变得更加高效？

我们刚刚在手机上创建的那个移除 Spread 列的任务，现在已经在后台启动并进入“运行中”（In Progress）状态了。通常在我的实际开发中，会有四到五个不同项目的智能体任务在云端后台同时并发跑着。我不需要一直盯着终端，只需要偶尔扫一眼看板面板即可。

过一会儿，这个任务就会自动在 GitHub 上提交 PR，并在 Linear 上进入“人工评审”阶段。到那时候，我只需要在手机上打开 Vercel 的预览链接（Preview Link）看一眼前端效果，如果在手机上发现样式有问题，就可以直接在源码上写下改进评论，然后把它打回“重新修改”状态。整个开发迭代流程我完全可以在手机上利用零碎时间随时随地完成。

为了把这个机制推向极致，我之前甚至做过一个叫作 **Pi Q** 的开源探索项目。它的思路是把你的代码仓库加上智能体程序直接丢进云端 VPS，然后向互联网暴露一个接口，任何网友都可以直接通过网页端向你的代码库发送一个具体的开发工单。这非常像未来的开发模式——我们可能不再需要去处理复杂的 Git Pull Request，而是直接通过**“提示词请求”（Request for Prompt）**来传递人类的设计上下文和开发意图。

<details>
<summary>Original English</summary>

**Alessio Finelli**: And so you can kind of go back here and be like, okay, this task was how to make a deployable on Vercel. So, you know, this whole thing was just not working. It was originally built. It's kind of like a local thing. So, I had to like, you know, rewrite the storage, kind of like, you know, change all the request or handle, blah blah blah. So, this is like quite a big task. So, it kind of makes sense that it cost a lot of tokens. Um and so from here you can kind of start to think about how in the future can I make these more efficient by either adding more checks or adding better descriptions or better tooling. So, the task we just created is it just kind of went live. So, here you can kind of see, uh you know, obviously there's usually like, you know, four or five of these in different projects that are running. So, I don't really want to see the whole thing, but I just want to glance. And I'm sure I can make this UI a little prettier. Um maybe once they give us stable five back, um that'll be good enough. Um And so this is working, right? And so in a little bit this is going to go from from in progress to like human review. And once it goes to human review, then we can kind of look at the Vercel preview and we can make comments on the code and on the front end and kind of move it back. But I could be doing this here. I could be doing this on my phone. I could be doing this anywhere, really. Um and to kind of put it to the extreme I had um let me see if I I find it. Um I created this project called Pi Q, which was basically like putting your repo plus the Pi agent in a VPS, and then anybody on the internet could send you, I think I put it in a different project, could send you like a coding task to your product. So, it's almost like in the future, you know, and I think some people now have this idea of like request for prompt instead of like request for pull requests. Everything is just how do you transfer context between people?

</details>

---

### 精简规范：避免智能体指令的“过度工程”

**克莱尔·沃 (Claire Vo)**: 总结一下你刚才展示的工作流：其实任何人都可以为他们现有的代码库创建一个 Linear 项目板，并将其与部署在云端 VPS 上的 Symphony 及智能体进行集成。接下来，你所有的工作就是在 Linear 上通过卡片拖拽来调度智能体的状态机。你可以在手机上、电脑网页端随时随地管理它，而完全不需要操心这个任务在具体执行时是如何被拆解的、代码是怎么写的，甚至连你写下的评审评论如何被智能体读取并重新修改代码的流程都全部被自动化打通了。

这里我也想向大家说明，**Symphony** 是 OpenAI 之前开源的一个用于自动化开发工作流的参考实现。它提供了一种极度规范且结构化的方式来执行软件工程任务，其底层逻辑就是监听 Linear 任务板的变更，在任务被分配时自动拉起智能体，运行完毕后自动提交 PR 并标记完成。

对于那些也想把这套流程跑起来的人来说，在实际落地中，设置 Symphony 的难度有多大？因为很多人看到这些前沿演示时，往往会觉得：“这太棒了，但我到底该怎么在我的 GitHub 仓库里去配置和跑起来呢？”我知道官方仓库提供了两种参考路径：要么直接让你的 AI 编程助手帮你把这套环境搭起来，要么参考他们给出的参考实现。你当时是怎么把它跑起来的？

<details>
<summary>Original English</summary>

**Claire Vo**: So, before we move on to maybe another workflow, what you just showed me was look, you can just create a linear project for any of one of your code bases, you can integrate that with Zoe and with Symphony, and then all you're doing is really tasking linear as sort of like your state machine for all the work that needs to happen in your code base, you can manage that on linear from your phone, you can manage that from your desktop, from the web, and you don't really have to worry about the framework of how that task gets, you know, broken down, how it gets implemented, even how your comments get reviewed, that's all set up. And I just wanted to share for people, Symphony is something that OpenAI open-sourced as sort of a framework for autonomous runs, so it's it's just a very opinionated way to do this work, and it basically does what you just showed, it monitors a linear board, spins up agents when it gets assigned something, and then, you know, you can you can land it in a PR and it gets marked as done. How simple was it for you to like actually set up Symphony? Because I think people look at these things and they're like, "Okay, that makes sense, but what do I actually do with this GitHub repository?" And I know they have these two options here, which is like basically tell your coding agent to build it for you, or there's this reference implementation. How did you actually implement Symphony?

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 好的。我是基于官方提供的 **Elixir** 参考实现版本进行修改的。你实际需要定制的底层核心其实并不多，主要就是修改位于项目主目录下的工作流配置文件，向智能体解释如何在这个特定的项目中执行操作，然后把管理面板的 UI 顺手搭出来。

需要说明的是，原版的 Symphony 默认是没有可视化监控面板的，也没有内置针对每个任务的 Token 花费和资金账单统计，它本质上只是一个后台运行的分布式状态监听器。

但我觉得这套系统的核心难点，并不在底层的框架编排，而在于**你如何为智能体构建更具表现力和实用性的周边工具链**，从而让它们在工程开发中能走得更远。这也是我们 Kernel Labs 最近一直在着手攻克的技术方向。

比如，我们开发了一个名为 **Glimpse** 的浏览器调试工具，它本质上是一个高度定制的 Playwright 浏览器扩展。云端运行的编程智能体可以使用 Glimpse 自动对它们开发的前端页面进行截图，并在代码修改前后进行实时的像素级视觉差异对比（Visual Diffs），甚至可以直接录制操作视频。

因此，与其把所有精力都花在如何写出复杂的智能体调度算法上，不如**多花心思去为智能体提供强大的开发者工具**，让它们能够在一个长达数小时的任务中自主解决各种异常，而不是稍微遇到一点前端样式不对或者测试报错，就立刻中断执行跑回来请求人类进行 review。

这也能解释为什么实时统计智能体的 Token 消耗和执行时长是如此重要。因为这些数据能够非常直观地告诉你，智能体在开发过程中究竟遇到了多少次挫折和死循环。如果在你的预期中，某项修改应该是个很小的工作，但统计显示它消耗了上亿个 Token，这就说明智能体在某些工具的调用上或者在代码库的上下文中陷入了死循环。这时候，你就需要去优化你的智能体工具链，或者为它提供更好的脚手架和测试工具。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Yeah, I took the Elixir implementation. They're really like the core things to change are like the workflow that I'm doing in the main in the main folder that kind of like explains how to do it and then build the UI. So the Symphony itself doesn't have a visual UI for it and I also don't think it has the same it doesn't have by default the ledger for token usage. So it's only like a a state monitor. It doesn't actually look at like you know how much have you spent per task and kind of like all these different things. But yeah I think like overall the hardness you know it's pretty straightforward. I think like the reality is like how do you build tools for it to be more effective and that's kind of like one of the main things also kernel lives have been working on. So we built this other thing called glimpse which is a kind of like a playwright extension that coding agents can use to take screenshots to do visual diffs between screenshots take videos and so it's almost like how do you like these runs kind of go longer and longer? So it's less about the orchestration itself and like the tools you give it to keep going versus coming back to you with the human review. And I think that's also why it's so important to like keep track of how many tokens and how much time it takes because it's usually like directionally it explains you how many issues it ran into you know. So if you expect something you should start to have at some point some idea of like how many tokens you think this will take. You know is this like a 10 million token task? Is this like a 100 million token task? And if the reality is very far away from your expectations there's probably something in the tooling layer that you can do to improve. So that's really where most of the kind of like value comes from for people.

</details>

**克莱尔·沃 (Claire Vo)**: 没错。我希望听众能从这里学到的一个核心经验是：很多人经常跑来问我：“克莱尔，我们到底该如何从头构建一套我们自己专属的、极其复杂的智能体编排平台？”然后他们会发给我一大堆长达几十页的、画满了各种条件分支的复杂架构设计图和工作流图表。

这时候，我往往会直接把他们带去看看 Symphony 的架构规范文件。你会发现，里面针对整个开发工作流的定义，**完全是用非常直观的自然语言（Markdown）写成的**。它只是非常清晰、高度精炼地定义了系统运作的“元原语”（Primitives）——智能体应该在什么状态下记录什么、在什么阶段去哪里读取上下文，以及在遇到冲突时如何推进软件开发生命周期的流转。

这个文件虽然包含很多细节，但它本质上就是一个再普通不过的 `.md` 文本文件。我认为很多企业和团队在最开始就“过度设计”（Over-engineer）了智能体的调度层。而事实上，随着 GPT-4o 等现代先进大语言模型推理能力的提升，你只需要给它们一份用人类语言写得非常清楚的运行规范（Spec），它们在执行任务时就会非常牢固地遵循这份规范，这比用代码写死各种硬编码规则要灵活且健壮得多。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah one of the lessons I want people to take away from this is I get asked all the time like Claire how do we build our own agent orchestration platform and like they they send me these like giant very complicated documents and workflow diagrams and you know, pointing them to just like Symphony spec MD, which just describes how the system is supposed to work. It's in natural language and it just is very prescriptive about what the primitives are of this workflow and what to store and record and how to move things forward and sort of the software development life cycle. Like it's very long, it's very detailed, but it's literally just a markdown file and I think people kind of over engineer at at first what these things can be and ultimately the power of LLMs, especially these newer models is you can just give them a spec for how they will work and they will you know, they will lock to that spec when executing whatever you hand it.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 确实如此。目前大家在内心深处，似乎都渴望能有一份如同“魔法”一般的智能体配置文件，只要把它往项目里一丢，就能立刻自动解决自己企业里所有的业务和工程痛点。但现实情况是，往往是那些**极其精简、字数不多但权重分明的规则描述**，在指导智能体工作时表现得最好。

比如，在智能体工具本身原生集成“Git Worktree 管理”之前，我自己写了一个工作区管理器。在当时我所有的智能体指令规范（Agent MD）中，我都写了这样一句话：“你必须且只能使用我提供的工作区管理器来切换开发分支。”

现在，随着智能体自身工具链的升级，我已经不再需要这条硬性规则了。但在有些老项目里，如果你忘记清理这些过时的陈旧规范，当你启动一个新任务时，智能体还是会跑去尝试安装并调用那个早已淘汰的管理器。这时候我就得手动去对它说：“别用那个了，现在直接切换分支即可。”

所以现在，很多走在前面的智能体开发者都在提倡一个观点：**我们应该像定期重构代码一样，每隔几个月就彻底清空并重写一次你的智能体系统提示词和 Markdown 规范文件**。这绝对是实践中非常重要的最佳实践。

因为现在的模型依然存在一种倾向：**它们非常喜欢往现有的规则文档里叠加新指令，而不是主动删减不再需要的陈旧指令**。比如，当你对它说“你其实不需要每次都调用分支管理器”时，它并不是去把写有那条规则的代码行删掉，而是选择在后面再加上一行：“但是，在某些特定情况下你也可以不用它。”这导致你的配置文件变得越来越臃肿，最后智能体自己也会被这堆互相冲突的繁琐规则搞得一头雾水。

在我的实践中，我的智能体配置文件写得非常克制。它并没有巨细靡遗地去教智能体如何去写代码，它只是明确规定了云端 Symphony 的架构边界：每个实例的名字是什么、对应的 GitHub 仓库地址是什么、每个开发任务的工作空间放在哪里、Token 账单和运行日志记录在哪个目录下，以及当前任务的状态流转规则。

我会在规则里写明：“如果工具库里已经有你需要的 API，就直接去调用它；如果确实缺东西，你可以停下来询问我，除此之外不要去请求一些无意义的信息。运行任务时的具体指令是这些，需要带上的命令行 Parameter 和 Flags 是那些。”这就足够了。把架构边界划定清楚，把必需的工具交给它，接下来就信任并放手让模型自己去发挥和编写代码。

这就好比我今天在添加一个新项目时，智能体在日志里自动跳出来一行提示：“该项目的信息已经在此文件中注册过了，不应该重复添加。”这就是智能体自主性的一种体现——它在每次运行时都会主动去检索系统中已有的项目状态，而不是机械地按照死板的顺序重复执行所有命令。如果你的规则文档写得太死板，你最终得到的往往是一个经常在运行中卡死或者输出行为非常古怪的半成品程序。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Yeah, I think everybody just wants to have the magic skills file that does everything for them and like the magic MD that solves their business problems. I think the reality is like now more than ever like small sentences of like very a lot of weight, you know, like for example, I built this work tree manager before the coding agents themselves added and in every agent MD I was like, you have to use the work tree manager. And now sometimes I forget ahead in some projects and then I start a task and it's like reinstall I'm like, you don't need anymore. But like because I had a deadline every time it's not doing that. And I think a lot of folks have been talking about purging your markdown files now every few months. I think that's something that obviously makes sense. I think the models themselves of that also have this like tendency to like add rather than remove. So, if you're like, hey, you don't need to always use the work tree manager, instead of removing that line, it's going to add a line to say "But, don't have to use it all the time, though, you know?" And now you're kind of getting more and more confused. So, for example, my the the skill that I'm the it's not super descriptive on what to do, but it's like, "Hey, this is where you put the the symphony. This is how you should architect it. So, every symphony instance has kind of like its own name. It's got the repo that you're working from. It's got the workspaces for each task. It's got logs, which include the token usage. And it's got got the state um of of this run. And then, these are the things that you need. So, if you don't have them, ask me. Otherwise, don't ask for stuff. These are the exact commands. These are the flags. But, I'm not really telling it what to do and what to use. I'm just saying these are like things that you got to keep in mind. And then you kind of let the model work. Um See, this is like a good example. I think it just added this today when I was adding a new project. It's like, "This one is already registered here." And it's like, "This should not be in this file." Like, it should look up every time. It should just search every time what's already there. You know, those are like all examples of like, if you just let the models kind of do their own things, then you just end up with this like very weird things.

</details>

**克莱尔·沃 (Claire Vo)**: 明白了，这就需要定期清理你的智能体规则文档，把过时的东西果断干掉。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay, so red diff your skills and red diff your markdown files and get some stuff

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 没错，保持规则的轻量和干净。我感觉像 Codex 在应用中内置的“自动生成并保存新技能”（Create Skill）的功能，虽然出发点非常好，但在实际使用中常常会给用户带来很多困扰。因为智能体在后台自动总结并写入配置文件中的“技能描述”往往不够精确或过于臃肿，而智能体本身在执行后续任务时又会极度死板地去遵循这些它自己写下的糟糕规则，最后反而导致开发过程越跑越偏。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Yeah, they're not out there. I feel like the create skill thing that the Codex app, for example, added, I think it's like a great idea, but it didn't for a lot of people, it just puts them in a lot of trouble because it's like they're not very descriptive in the skill itself. And then, the model is like very focused on following the skill. And so, they're actually doing um themselves a disservice a lot of time.

</details>

---

### Multiplayer 协作模式与小微企业的赋能

**克莱尔·沃 (Claire Vo)**: 本期节目由 **Jira Product Discovery** 赞助播出。

AI 的普及无疑让每一位独立的产品经理（PM）拥有了不可思议的单兵作战生产力，但是，当团队进入“多人协作模式”（Multiplayer Mode）时，事情往往还是会变得一团糟——如何让团队里的所有人对“究竟应该构建什么”达成高度共识和对齐，依然是日常协作中的最大痛点。很多时候，团队上周做出的关键业务决策其实都散落并深埋在某个 Markdown 文档里，而所谓的项目规划路线图则是一个根本没有人去点开查阅的超大 Excel 电子表格。

Jira Product Discovery 则是专为解决这一痛点而生的平台，它是团队真正凝聚共识、决定产品下一步构建方向的地方。你可以直接在上面收集创意点子、以团队为单位进行协同优先级排序，并实时分享一份所有团队成员都在基于其进行日常开发的动态路线图。它基于 Atlassian 的 Teamwork Graph，因此可以非常方便地引入客户反馈、团队已交付的产品数据，并结合你们当前的业务目标，自动推荐下一步应该开发什么。一旦团队达成了共识，你可以一键将决策无缝派发至 Jira 中，让你的开发人员——甚至直接是你的开发智能体——立刻认领该任务并开始编写代码。目前，来自 Canva、Deliveroo 和 Toast 等公司的超过 25,000 支团队已经在使用它。立即访问 **atlassian.com/howiai** 加入他们，让我们一起构建正确的产品。

阿莱西奥，我们聊回你的 Symphony 智能体系统。在实际使用这套云端编排平台后，你真的觉得自己的工作效率有明显的飞跃吗？它是否为你带来了更好的开发体感，还是说，它最大的价值在于让你即使在旅途中也能随时跟进项目进度？

<details>
<summary>Original English</summary>

**Claire Vo**: This episode is brought to you by Jira Product Discovery. AI has made individual PMs incredibly productive, but multiplayer mode is where it still breaks, getting everyone aligned on what should actually get built. Decisions live in a markdown file from last week. The road map's a spreadsheet no one's looking at. Jira product discovery is where teams actually decide what to build. Capture ideas, prioritize them as a team, and share a living road map everyone works from. It's powered by Atlassian's teamwork graph, so it can pull in customer feedback, what your team shipped, plus your goals, and suggest what to build next. And when a decision is made, you can hand it off straight to Jira, so a developer or even an agent can pick it up and start building. Teams at Canva, Deliveroo, and Toast already use Jira product discovery. Join more than 25,000 teams at atlassian.com/howiai. Start building the right things together.

Do you feel like you're getting a lot more done on this orchestrator? Is it just like better ergonomics and that you can manage it on the go? What's the benefit you feel of using something like Symphony?

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 关于是不是“写了更多代码”或“完成了更多任务”，我其实很难给出一个绝对的肯定答复。如果从理论的极限情况来看，你确实能够处理更多的任务；但在实际的工程开发中，作为一个人类，你每天根本没有精力去深度 Review 智能体提交上来的 100 个全新功能。你的精力是有瓶颈的。

对我而言，这套系统带来最大的幸福感在于：它能**把某一个工程任务的所有开发历史和演进脉络，完完整整地收拢在同一个地方**。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Um I think it's definitely I I don't know about the getting more done. I think it you know, in the limit you get more done, but in practice it's like you can't really like stay on top of like 100 new things a day. Uh the thing that's really helpful is like having the full history of one task in one place.

</details>

**克莱尔·沃 (Claire Vo)**: 没错，上下文的收拢对于 Debug 来说太关键了。

<details>
<summary>Original English</summary>

**Claire Vo**: Yep.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 因为这套系统将 Linear 作为事实来源，所以一张卡片里就完整保存了最初的产品设计 Spec、智能体制定的第一版开发方案、人类在 GitHub 提交的 Code Review 意见，以及智能体后续返工的所有执行方案。每当开发跑偏或者程序报错时，你都可以非常精准地回溯到“事情是从哪一步开始出错的”。

接着，你就可以利用这些教训，在配置文件里针对性地去优化你的智能体工作流规范。相比之下，如果你只是直接在聊天界面里用 Codex 进行一问一答的交互，当你之后想去检索某一次修改的历史上下文和对话记录时，会发现极其困难。

所以说，这一切的本质就是：**你如何去塑形并管理智能体的上下文（Context）**。Symphony 本质上只是一种帮助你收集并规整开发上下文的工具，它本身并没有赋予你任何超越模型本身的魔法，它只是帮助你更好地去驾驭和控制模型的输出。

<details>
<summary>Original English</summary>

**Alessio Finelli**: So, because it has the original spec, it has the first work pad, it has the rework work pad, every time you're like, "How did things go wrong?" you can kind of pinpoint where that was. And then you can use that to inform, you know, your agents MD in the future like the Symphony workflow that MD versus if you're just using code X, it's kind of it's really hard to search through conversations, you know? Um and so everything is like, "How do you shape the context?" You know? Like Symphony's just a way to shape the context. It's not It's not giving you any new capability that you wouldn't have by using the coding agents directly. It's just helping you wield it.

</details>

**克莱尔·沃 (Claire Vo)**: 我非常赞同这个观点。

你刚刚向我们展示了如何通过云端编排来实现软件开发流程的半自动化。为了让听众觉得这些前沿工具离他们的生活更近、更易落地，我们接下来聊聊你提到的另一个非常接地气的使用案例——这同时也是我 9 岁儿子最感兴趣的，即利用 AI 来对宝可梦卡牌进行智能搜寻和实时定价。

<details>
<summary>Original English</summary>

**Claire Vo**: I I I love that. So, okay, you you've shown us how you're doing sort of this orchestration of of agents or at least like workflow management of agents. Again, like let's make this much more accessible for people. This is just a workflow to manage your your your agents, especially around coding. And we have another use case, which this one was the use case that I wanted to see. This other one is the use case that my 9-year-old wants to see. So, let's do our Pokémon card by AI use case.

</details>

---

### 实战演示：宝可梦卡牌定价与实体业务自动化

**阿莱西奥·法内利 (Alessio Fanelli)**: 好的。世界上可能有很多初创公司（Startups），但宝可梦卡牌的种类和发行数量，绝对比世界上存在过的初创公司总数还要多得多。这也是为什么我决定要开发 **Power Buyer** 这个卡牌搜寻和比价服务，以此来帮我们的实体店铺实时追踪我们想要采购的卡牌库存和价格波动。

在这个卡牌业务中，我主要让 Codex 帮我干两件事。

第一件事，是利用 PSA 的官方 API 去拉取并匹配高价值卡牌的鉴定证书信息。高价值卡牌通常需要寄送给专业鉴定机构 **PSA** 进行品相评分，评分结果（从 1 分到 10 分）会对应一个唯一的证书编号。我们必须知道这个编号，才能在后续的追踪中准确获取该卡牌在对应分数下的市场流通量和历史价格数据。

虽然有公开的证书查询接口，但官方并没有提供一个可以让你一键下载完整数据库的渠道。所以，我写了一个智能体脚本，规则是：“使用内置的浏览器环境，在网上搜寻并整理出所有市场价值在 1,000 美元以上的宝可梦卡牌，找到它们的鉴定证书编号，并提取和识别出对应的卡牌图片信息。”

智能体接到任务后，就会自动在云端打开浏览器，在相关的交易网站上进行浏览、提取信息、下载卡牌的高清图片，并利用视觉模型自动识别并提取出图片上的证书编号。

<details>
<summary>Original English</summary>

**Alessio Finelli**: People think there are a lot of startups. There are way more Pokémon cards than there are ever going to be startups to follow. Um so, one thing the reason why I built this power buyer thing is for us to kind of keep track of, you know, inventory we want to buy and things like that. Um So, I use Codex for two things. The first one is like getting the PSA certificates to keep track of like, you know, basically Pokémon cards so you can get them graded by PSA. Um and then there's kind of like a specific number for each grade. And that's available through an API. But you need one certificate number here to start from. Um there's obviously no way to just download that. So, what I have is like, you know, I have Codex pursue goal, fill out the certificate number for every card that costs more than $1,000. So, I give it browser access, for example here, and it just, you know, going on on the internet and it's looking at things and it's like downloading the images. And it's extracting the number from it. And then, what you can then do is like, you know, use the eBay PSA premium hunt. Let's find some underpriced cards from our you know, list.

</details>

**克莱尔·沃 (Claire Vo)**: 听起来非常高效。你在 Linear 里是把它作为一个特定的开发技能（Skill）配置给智能体的吗？

<details>
<summary>Original English</summary>

**Claire Vo**: Okay, so that's Is that a skill?

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 没错，这在系统里是一个定义好的技能。这个脚本的核心逻辑就是教智能体如何去计算和判定“哪些卡牌是目前最值得关注的”，以及在爬取和比价时如何进行分批处理。

比如，在规则里我会严格限制：“每一批次只查询 5 张卡牌。”因为你不能让智能体以极快的频率去频繁请求 eBay，否则很快就会被 eBay 的防爬虫机制封锁 IP。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Yes. The The skill is basically telling you how to figure out which cards are worth looking for. And then it just says how to batch them, you know? So, just do five per batch. You don't You don't want to get like, you know, captured by eBay or stuff like that.

</details>

**克莱尔·沃 (Claire Vo)**: 哈哈，没错，防爬虫封锁是经常遇到的问题。

<details>
<summary>Original English</summary>

**Claire Vo**: [laughter]

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 另外，不同鉴定公司之间的评分标准也是存在某种映射规律的。比如，评级机构 **PSA** 的 10 分（品相完美），在市场交易上的价值和认可度，往往等同于另外两家鉴定机构 **BGS** 或 **CGC** 的 10 分；而 PSA 的 9 分，则可能会被拿来与其他的特定级别进行折价对比。

我把所有这些复杂的实体交易规则和定价换算公式都写进了智能体配置文件里。这样一来，智能体在通过 API 扫描 eBay 等交易平台的最新挂牌价格时，就能结合我们库房里的目标采购清单，自动判断出哪些卡牌目前的挂牌价是严重偏离市场正常价格的。

我现在尝试在我们的 Zoo 实例上打开它运行时的 eBay 爬取界面。

你可以看到，智能体目前正在后台利用它的内置浏览器在 eBay 上实时检索和匹配这些高价值卡牌。这些卡牌的单价通常在 100 美元、200 美元，甚至高达数千美元。对于单价只有几美元的低价值卡牌，我们显然不会浪费算力去跑这套流程。

在这个过程中，一旦智能体检索到某张卡牌的挂牌价低于市场公允价格，它就会在我们的 Slack 或者 Linear 上向我们发出推送提醒：“发现一张严重低估的卡牌，目前的挂牌价格非常值得立刻入手。”

这就是一个非常典型的如何利用软件工程和 AI 来解决线下物理世界中实体业务痛点的例子。我们开发软件的最终目的，一定要能落地到实际的商业转化或者产生具体的财务收益上。而卡牌交易则是一个天然适合 AI 施展拳脚的场景——它是一个完全基于库存周转的商业模式，你在市场上能扫到多少被低估的优质卡，你后续通过重新评级销售就能赚取多少差价。

如果完全依赖人工去盯着 eBay 等待那些被挂错价格或者便宜出清的卡牌，受限于人类的精力和时间，你一天可能看不了几张卡，而且很容易漏掉那些黄金机会。而利用云端的 AI 智能体，你就可以让它 24 小时不知疲倦地在全网搜寻，一旦出现符合公式的卡牌，就立刻通知人类决策买入。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Um and then there's also things, for example, there's different grading companies. So, you might have, uh you know, a PSA 10 is the same as like a PSA 9 is the same as like a um BGS or CGC 10. Uh and so all these different rules you might want to you might want to have in there. Um and so here just, you know, through the APIs looking on from our power buyers after the cards that we want to look at. Um and then it's using the in-app browser for for eBay. Let's see if I can open it here. So, now it's going here and it's like looking at just searching some of the And these are all like, you know, 10, 20, 50, $1,000 cards. Like, you don't really do this for um $5. Um and so now it kind of goes in here and you know, you'll see it then. Um tell us, you know, this card is underpriced or uh this is card this card this card is, you know, worth buying right now. Um and yeah, this is like, you know, uh a a good example of like you can build anything, but then at some point you got to have some business outcome or like some way to make money with the software that you built. Um and trading cards is actually a great example of like the more money you can put to work, the more money you can make because it's like an inventory-based business. So, you can only make as much as you can sell. Um and so having this to help us um automate looking for some of these like higher value cards, for example, is like super useful.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 此外，我们目前正在尝试攻克的另一个更加深入的实体交易场景，则是关于“展会实时竞价”。

如果你关注过 Instagram Reels 或者 TikTok 上的卡牌交易短视频，你会看到这样的场景：在人头攒动的卡牌交易展会上，成百上千的卡迷会排队走向卖家的展位，拿出他们随身携带的十几张卡牌向老板询价。老板必须在短短几十秒内，在现场对每一张卡牌给出一个合理的收购报价。

这个过程在以前极其低效且充满风险，因为买家老板得在手机上不断切换 eBay 和 TCGPlayer 页面，核对卡牌的版次、卡号、品相和最新的成交价格。有时候因为现场网络卡顿，或者由于老板疲劳看错了一个小图标（比如把普通版当成了限量闪卡版），就会导致极大的经济损失。

在这种高强度的线下实体展会交易中，高延迟的 AI 交互显然是排不上用场的，你需要的是一个极低延迟、极度敏捷的智能识别工具，它能通过摄像头实时识别卡牌品类，并在后台自主调取比价智能体完成多渠道价格汇总和加权平均，在几秒钟内将公允的收购价和建议零售价推送到老板的智能眼镜或者手持屏幕上。

我之所以对 AI 智能体感到兴奋，正是因为它们能让普通的实体创业者拥有这种几乎作弊一般的效率优势。我们终于可以跳出单纯的“用 AI 来写代码去开发更多 AI 工具”的死循环，转而用这套技术真正赋能那些线下的实体小微生意。

不过在开发中我们也遇到了很多小麻烦。比如，我们在 Codex 中利用 API 调用第三方服务时，如果你的 URL 字符串里不小心带上了美元符号 `$`，Codex 有时候会把它误判为是在调用它内置的某些 Skill（技能变量），从而导致链接解析报错。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Um and then the next thing, you know, I'm working on is um and this is, I guess, getting in the weeds of the business, but uh when you go to like all these trade shows, you might have People might see them on the kind of like Instagram Reels or whatnot. Uh where people are coming to you, they're selling you cards, and you got to price them in real time. That whole process is like super inefficient because people are like searching each card manually like on eBay or like TCGPlayer, getting the number, blah blah blah. Um and so you're actually losing a lot of money. Uh so when people talk about um you know, AI response time, I think for these long-running tasks, it's actually not that useful, but you can actually use AI to save clock time for real people by doing these things autonomously. Um so yeah, it's just been fun to try and apply it outside of like "Hey, I'm building the tool for you to build the tool to build the tool so that hopefully somebody down the line does something that is worth the for someone to use." Um so yeah, for example, we got this amplifier right here. Let's see. I guess it broke the link. See? Even the internet bends to the best of them. This is something actually, it's funny. People talk about software automation, but um Code X has this kind of like the dollar sign. It's like tied to skills. So sometimes when you're like linking with the dollar on the thing, it pre-fills it to a skill. So right now right now it's looking for a skill

</details>

**克莱尔·沃 (Claire Vo)**: 哈哈，没错。它把那个美元符号当成了调用特定 Skill 的标识符，而不是 URL 里的普通字符。

<details>
<summary>Original English</summary>

**Claire Vo**: instead of a URL.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 没错，比如我们刚才调用 TCGPlayer 链接时就遇到了这个 bug。这正好说明了一个现实：即使是最先进的软件系统，在面对这些小细节时依然会掉链子。

<details>
<summary>Original English</summary>

**Alessio Finelli**: You see like TCGPlayer, HTTP, so um yeah. That's a good That's a good example of like, you know, even these small things in software are sometimes broken.

</details>

**克莱尔·沃 (Claire Vo)**: 确实如此。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah.

</details>

---

### 实体资产分类与 AI 视觉技术

**阿莱西奥·法内利 (Alessio Fanelli)**: 但从宏观趋势来看，我们正在进入一个全新的阶段——有大量过去完全无法用传统软件进行标准化和规模化管理的业务，正因为 AI 的出现而变得可以被轻松重构。

在以前，面对海量的、极度非标准化的实体资产数据（比如各种复古 vintage 衣服、二手家具、零散的配件等等），你很难用传统的条形码或数据库系统去进行规范化的分类和定价。

因为在没有 LLM 这种具备极强泛化理解能力的大模型之前，你哪怕用最先进的传统计算机视觉模型去对一件古着衣服进行分类，它也只能告诉你“这是一件红色的衣服”，而无法像人类专家一样结合当前的潮流、面料细节、领口磨损程度以及缝线风格，给出极度精细的估值和真伪鉴定。

现在，随着多模态大模型的成熟，智能体完全可以在后台像人类专家一样去浏览、识别和核对这些复杂的线下实体信息，从而打破了过去困扰线下小生意规模化扩张的“人效瓶颈”。

同样的趋势也正在古着服装交易、二手家具回收等领域悄然发生。

在以前，这类型的实体小店老板往往面临着巨大的“信息不对称和认知带宽限制”。比如，你去 Goodwill（垃圾回收和慈善义卖商店）淘货，你可能会在一堆旧衣服里漏掉一件其实价值几百美元的 Prada 复古包，因为你个人的大脑认知带宽是不可能记下世界上所有奢侈品版型和历史售价细节的。但现在，AI 智能体可以成为你的全能数字化助手。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Um but yeah, just um this is overall one trend where it's like there are a lot of businesses that are based on kind of like um highly heterogeneous data um that have been impossible to scale with software. Because before you have kind of like something as malleable as an LLM that can go through these things, it's really hard to use even like text or image classification for these things. Um and so yeah, I think you're going to see a lot more of of these businesses. Like I think the same I I forget who it was, but the same thing is happening with like vintage clothing, for example. Um some people are doing something similar for for desk stuff. Um because again, you see it all the time, right? Oh my god, I went to Goodwill and I saw this, I don't know, Prada bag that was like in good in the Goodwill thing, and um this has always been kind of like a mismatch between like human bandwidth and like the information that is coming from them.

</details>

**克莱尔·沃 (Claire Vo)**: 这确实是我最喜欢的 AI 使用场景之一，因为它真正赋予了小微企业和个人创业者对抗大型连锁企业的“效率杠杆”。

通过这种方式，由于你拥有了 AI 这个近乎无限的认知放大器，你就可以一个人支撑起一个庞大的垂直细分业务。那些曾经受限于人类体力、时间以及认知上限而无法做大的小生意，在今天正因为大模型的赋能而迎来爆发。

同时，这个场景也非常生动地展示了 AI 是如何帮助我们去数字化并重组物理世界的。

在这里我也分享一个我自己的趣味个人案例。就在几个星期前，因为无法忍受家里堆积如山的东西，我彻底爆发了。我们家里最多的东西就是书，各种书架上、地上堆满了成百上千本图书。

于是，我决定和我的孩子们还有我丈夫打个赌，我问他们：“你们猜猜我们家目前到底有多少本书？”

为了揭开答案，我拿着手机在家里走了一圈，拍下了家里每一个角落和书堆的照片。随后，我把这些照片全部打包发给了 **Gemini**——多模态视觉模型在这类高清晰度照片的文字识别和图书分类任务上表现得特别出色。

Gemini 最终给出的统计结果是：我们家里居然整整存了 **600 本书**！这意味着我们家平均每人拥有超过 100 本书。

但更令我惊喜的是，通过这个过程，Gemini 帮我把这 600 本书全部按书名整理成了结构化的 Excel 表格，自动划分了图书类别（如小说、少儿科普、商业管理等），标记了它们在照片中呈现的具体物理摆放位置，甚至还帮我挑出了十几本重复购买的图书（因为有些书是我买的，有些书是我丈夫在不同时间重复买的）。

这种能够利用 AI 以极低的成本去介入并高效打理混乱的线下物理世界的能力，对我的生活质量产生了极大的正面改善。不仅在个人生活层面上如此，对于广大的小生意店主来说，这种数字化的能力更是直接关乎到企业的生死。

<details>
<summary>Original English</summary>

**Claire Vo**: This is my favorite one in that I I think it enables what a very positive outcome of AI, which is small business creation. And I think, you know, this business uh it clearly trading cards are huge business, but no, what what you're able to create this bigger business because you have the leverage of AI, and this is something that a human would have to manually do, and just the limits of time, space, and human cognitive capacity means you're probably unable to capture as much of this business as you are today. I also think, I love this use case because it shows where AI helps you intersect the physical world in a really effective way, and an example, maybe I'll do a podcast on it, is a couple weeks ago I had a rage out about how much is in my house, and I I and most of it is books. Most of what's in my house is piles of books. And so, I placed a bet with my children and my husband. I said, "How many books do you think we have in this house?" And I went around with a camera, and I took pictures of every like every pile of books. There's books everywhere, and I had Gemini go through it cuz Gemini's like particularly good at this, and I had We have 600 books in this house. It's like more it's a hun- more than 100 books per person in this house. But I was able to catalog all these books, put them into categories, mark where they physically are, find all the duplicates because, you know, I buy a book and then my husband buy a book, and and just the ability to like intersect the human world in a way that has been historically very inefficient has been a quality of life improvement for me with AI and that's on a personal level but I also think as a small business owner that's it's really important.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 确实如此。目前很多人在谈到 AI 时，总是本能地带着过去的“工业互联网经济学”的思维，过度关注这套工具是不是能帮大公司每年多发布 5,000 个无意义的代码特性。

大家都想去追寻所谓的“规模效应”。但事实上，AI 带来的最大革命，恰恰在于为微观的个体和传统的传统行业注入了极强的局部效率杠杆。

就像我刚才提到的我父亲在罗马的海鲜批发小店。他们每天早上要派人走进满是冷气的冷冻库，在寒冷的环境下拿着纸笔一件件清点货物，记录哪些鱼卖完了、哪些虾还剩多少。

如果用传统的数字化方案去改造这个店，你得花大价钱去为库房安装定制的扫码轨道、为每箱鱼贴上 RFID 电子标签，这对于一个小本经营的海鲜配送店来说，其安装和维护成本完全是不可承受的。

而现在，只需要让库房阿姨戴上一副普通的带有视觉识别的 Meta 智能眼镜，或者拿手机摄像头对着冰柜扫视一圈，后台运行的视觉智能体就能在几秒钟内自动识别出里面的鱼类品相和数量，并在后台将数据直接同步到他们的销售管理系统。

通过这种极低门槛的智能技术，即使是只有两三个人的线下夫妻店，也能获得不亚于跨国物流巨头的精确库存管理能力。

去年秋天我第一次去了日本旅游。在日本，你会看到大量的餐馆、手工作坊和零售店，其实都是由两到三个家庭成员在运营，他们把店打理得极其精致且富有生命力，并且非常享受这种小规模经营的状态。

我希望这种依托于 AI 技术而得以实现的高效、精致的小微商业模式，未来也能在包括美国在内的更多地方生根发芽。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Yeah, I think that's like the thing about AI that most people don't want to look at just because every previous technology was like so like the economies of scale will help you get more leverage out of it. versus even the software factories, right? At some point even if you're like Salesforce is not that you can release 5,000 features a week. There's some limit to which you can get leverage out of these models in specific tasks. versus you know, my dad their business back in I grew up in Rome. They deliver fish to restaurants. And they got like this freezer over with the frozen stuff and they have the fresh fish and kind of like somebody's going out there with like the pen and paper every morning kind of like writing down what's there. Sometimes they're like, "Oh my god, we're missing like three tuna." So they're like, "We're missing a box of shrimp." Uh and all of that work now can easily be automated, you know, even with just with the meta glasses or something else. Um and so you're kind of helping actually even at a small scale you can get a lot of leverage out of it. Um and yeah, I was you know, went for the first time to Japan last fall. Uh and I think that's uh a good example of like most things there kind of like smaller businesses that two or three people run. And they're very happy to do it. Um and I hopefully we see a lot more of that in the in the US, too.

</details>

**克莱尔·沃 (Claire Vo)**: 没错，这正是我目前非常享受的个人状态。作为一个只有“1.5 个人”和一群云端 AI 智能体组成的小微企业，我们每天都在快乐而高效地运转着。

阿莱西奥，非常感谢你今天向我们展示了如此开阔的图景——从前沿的云端代码自主开发工作流，一直到极为接地气的卡牌交易和线下实体零售的数字化重组。

在节目的最后，我们照例进入快速闪电问答环节，然后就送你回去工作。

我的第一个问题是：在目前的 AI 领域中，有什么是你个人非常兴奋、但你觉得大多数人其实还没有开始做，或者在未来几个月内大家才会逐渐意识并开始尝试的？

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah, well, that's that's the life that I live. I'm very I'm very happy to be a small business of one one and a half people and a bunch of agents. Well, this has been awesome. I really appreciate you showing us the range of, you know, coding all the way to sort of more like physical or inventory-based AI. We'll do quick lightning round question and then we will get you out of here. Um you know, my first question is what are you excited about that you think most people aren't doing with AI that you are either starting to do or you think people will start to do in the next couple months?

</details>

---

### 闪电问答：个人理财、经典图书推荐与 Roma 足球队

**阿莱西奥·法内利 (Alessio Fanelli)**: 好的。我最近个人非常兴奋的一个尝试是利用 AI 来打理我的**个人财务**（Personal Finances）。

ChatGPT 在最近更新中加入了与主流银行和金融账户的原生数据接口。前阵子我们刚卖掉了我们的房子，手头多出了一笔资金，我当时就在苦恼：“我该拿这笔钱去做些什么投资组合？”

我尝试让 AI 来帮我做宏观盘点，它的体感出乎意料地好。因为在过去，对于大多数普通人来说，理财最大的痛点在于“你很难长期坚持去手动记账并时刻追踪资金状态”。你得隔三差五去梳理自己目前在各个基金里的仓位、判断要不要把钱换到高息定存里、去查证关于 SpaceX 股权投资的传闻是不是真的等等。

现在，你可以把这些耗费精力的信息梳理和核对工作，安全地“外包”给 AI 智能体。

对于理财，我们普通人往往面临两个极端的焦虑：一方面我们想确保自己不会因为愚蠢的失误而把事情搞砸；另一方面，我们其实也没有精力去天天研究复杂的理财策略。这时候，AI 智能体就能成为你最坚固的“安全防护网”，为你分担走绝大多数的信息焦虑。

另一个相关的例子是，我之前一直在使用一个叫作 **Wafer** 的服务，它为用户提供了调用开源模型的无限 Token 额度。虽然这个服务最近突然关停了，但在它运行期间，我写了一个智能体，让它每隔 5 分钟就自动去读取并分析我的 Gmail 收件箱。

我的要求非常简单：“只在邮件列表里找出那些我确实需要在当天手动回复，或者确实需要我立刻做出决策的重要邮件，并把它们整理出来推送到我的备忘录上。”

在用上这个智能体之前，我整天都在面临一种隐性的压力，总觉得自己可能会漏掉某封关键的商业合作邮件，因此几乎每隔几分钟就会强迫症似地去刷新一次邮箱。而一旦智能体接管了这个工作，我心里 100% 确信：如果有任何紧急和重要的事件发生，智能体一定会第一时间跳出来叫醒我。这种将“上下文检索的负担”彻底外包给 AI 的体验，真的极大地减轻了我日常的心理压力。我强烈建议大家多去尝试这类场景。

<details>
<summary>Original English</summary>

**Alessio Finelli**: For me recently has been personal finances. Um I I mean ChatGPT just added the connectors for for all your accounts. Um we just sold our house and so I was like, what should I do with the money? Um and it it's actually pretty good because it keeps you on track. I think for me in the past I think has been like I don't want to like refigure out what am I doing right now, where do I have invested my money, should I invest somewhere else, is the SpaceX thing real, blah blah blah. Um I think having AI is kind of like a offloading thing. Um because in the past sometimes people are like I'm looking to make sure I'm not [__] it up. You know, it's not like I'm actually adding a lot to it. I'm just kind of stressed I'm going to mess it up. And so if you can have AI be that safety net it kind of frees you from a lot of things. I do the same like I was using this thing called Wafer, which is like a weekly unlimited tokens on the open source models. They just shut it down suddenly. Uh but I was having it read my Gmail every 5 minutes. And I was like, just read is there any email I should actually respond or look at? Um before I was always like, oh maybe I'm missing something, I should like check my inbox, blah blah blah. Now I know 100% that if something important comes in, I'll know about it. And that kind of removes a lot of stress from it. So it kind of being this kind of like context offloading. Um I think people should do more of that.

</details>

**克莱尔·沃 (Claire Vo)**: 我完全同意。

我的第二个快速问答：刚才我们聊到了家里堆满图书的趣事，我这里要把我的视频背景美颜功能关掉，让你看一眼我后面的书架——看，我们后面的书架上摆着一模一样的书！真是太巧了。

<details>
<summary>Original English</summary>

**Claire Vo**: I I completely completely agree. Okay, my second question because we were talking about books and I'm going to make you laugh, which is I'm going to turn off portrait mode. We have we have the same book. Look at us.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 哈哈，确实是那一本。

<details>
<summary>Original English</summary>

**Alessio Finelli**: The

</details>

**克莱尔·沃 (Claire Vo)**: 看来我们的阅读口味非常接近。那么，有没有哪一本书是你在生活中总是会推荐给其他人的？

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. Yeah, I got it. I mean we have I I think we have a lot of the same books, you know, we're very very similar. Bigger or a farmer, you know, with my page of marketers. Love that. So what's a book that you always recommend to people?

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 哈哈。这其实取决于对方目前处于人生的什么阶段，不同的人在不同的时期需要不同的书。

但如果非要推荐一本通用的话，我经常会推荐 **《修士与谜题》** (*The Monk and the Riddle*) 这本书。

这本书的背景虽然是关于硅谷创业和风险投资的，但它在内核上讨论了一个非常深刻的问题。书中描写了一个风投人去面见一位创业者，那位创业者在唾沫横飞地介绍说：“我准备创办一家面向殡仪馆提供数字化采购的垂直 SaaS 公司。老实说，我个人对殡仪馆和葬礼这个行业毫无兴趣，但我经过调研发现，这是一个规模巨大的、且极其传统落后的细分市场，在里面淘金会非常容易。一旦我未来把这家公司做大卖掉、实现了财务自由，我就可以回过头去安心做我自己真正热爱的事情了。”

而那位风投人听完后，非常平静地问了他一个问题：“既然如此，那你为什么不在此时此刻，就直接去开始做你真正热爱的事情呢？”

创业者当时回答说：“这不现实，那太冒险了。我宁愿先花五年时间去做这个无聊但稳赚不赔的项目，赚到钱后我才有资本去谈热爱。”

我认为这个故事切中了目前很多创始人甚至普通人面临的共同困境——我们总是在说服自己，应该先去做那些“别人期望我们去做、或者社会价值体系里看起来更正确、更容易成功的事情”，而把我们内心深处真正有激情和创意的想法不断往后推迟。这本书非常短，读起来很快，我强烈建议每个人去读一读。

而在商业书籍之外，我最想推荐的书则是但丁的 **《神曲》** (*Divine Comedy*)。

我从小在意大利长大。在意大利，每一个中学生都需要花整整三年的时间去逐字逐句精读《神曲》——第一年精读《地狱篇》（Inferno），第二年读《炼狱篇》（Purgatory），最后一年读《天堂篇》（Heaven）。

即使你抛开它的宗教背景不谈，它在今天依然是一面镜子，能时刻提醒你：“在遥远的 13 世纪，在没有任何现代工业和科学的帮助下，仅凭一个人的大脑，能够创造出何等宏大、深邃且震撼人心的精神世界。”它总能带给我无穷的灵感。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Oh, what's a book I I think it depends. I feel like in different times of your life you need different books. One thing I actually always recommend is called The Monk and the Riddle. Um which is kind of like based on startups and venture capital, but uh is basically this VC meeting with this founder and the founder is like, "I'm going to do this startup for like funeral homes." And I don't really like funeral homes, but I think it's a big market. And then once I sell the company, I'll be able to do what I like. Um and the VC is kind of like, "Well, why don't you just do what you like now?" And so he said, "Well, I don't know. It's kind of risky. It's like I'd rather just do this thing that is like big and like then I'll do what I like." And I think I see it a lot in founders where it's like, "I should do the thing that people want me to do." versus like doing the thing you're passionate about. Um I think that's that's one that I always recommend to people. It's It's very short. Um people like it. Um Outside of that, yeah, I don't I I mean the Divine Comedy by Dante. I would say like I grew up in Italy and in Italy for 3 years you have to study the Divine Comedy. Do one year, uh you know, Inferno, Purgatory, Heaven. Um it's just a reminder of like how great the human mind can be. Like, you know, in the in the middle of the 1200s. Um

</details>

**克莱尔·沃 (Claire Vo)**: 太棒了。既然提到了《神曲》，我们在这里插播一段幕后花絮——我儿子亨利其实此时此刻正坐在房间角落里旁听我们的播客录制呢。

亨利，你大声告诉阿莱西奥，我们平时有没有逼着你也去读但丁的《神曲》？我记得我之前跟你讲过关于地狱和灵魂的故事对吧？

**亨利 (Henry)**: 呃，地狱……我不太记得了。

**克莱尔·沃 (Claire Vo)**: 哈哈，没关系。但我确实在尝试教你这些古典文学，还有关于“七宗罪”的讨论。

另外插一个小问题，阿莱西奥，既然你是在罗马长大的，你是一名 **罗马足球俱乐部**（AS Roma）的铁杆球迷吗？

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah. Okay, we're going to do we're going to do a behind the scenes how AI um my son Henry is over here in the corner listening to the podcast. Henry, just say really loudly, are we making you learn about Dante's Inferno as well? Dante's Inferno, I told you about going to h e double l hell. You don't remember? Yeah. Yeah. Yeah, I'm teaching you about that. Yeah. And the seven deadly sins. You know, I also quick aside, are you an AS Roma fan?

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 那是当然！我是坚定的罗马球迷。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Of course.

</details>

**克莱尔·沃 (Claire Vo)**: 哈哈，太棒了，我们全家都是罗马足球队的拥趸。

<details>
<summary>Original English</summary>

**Claire Vo**: Oh, we're we're we're a we're Roma family.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 哈哈，我之所以这么拼命工作赚钱，就是为了以后能直接把罗马俱乐部买下来送给你。

<details>
<summary>Original English</summary>

**Alessio Finelli**: I only do this so that I can buy you one in the future.

</details>

**克莱尔·沃 (Claire Vo)**: 哈哈，一言为定。我 6 岁的孩子每周至少有三天都要穿着罗马队的球衣，他衣柜里有三套不同版本的罗马队战袍。我丈夫和儿子们目前都拥有意大利公民身份，我虽然不是，但我们全家都有着极深的罗马情结。

<details>
<summary>Original English</summary>

**Claire Vo**: My 6-year-old is like 3 days out of the week wearing a Roma kit. He's got like three different ones. Um so my my husband and my boys are Italian citizens. I am not, but they are.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 太棒了。不瞒你说，我上个星期甚至尝试去联系了罗马俱乐部的现任总裁。我对他说：“嘿，我很乐意为俱乐部做任何事情，我甚至可以免费为俱乐部提供全套的 AI 转型升级咨询服务，教你们如何利用大模型和数据分析来提升运营效率。只要你们需要，我随时可以飞回罗马帮你们干活。”

<details>
<summary>Original English</summary>

**Alessio Finelli**: Nice. No, I I literally swear to god, I just reached out to like the president of Roma like last week. I was like, "Hey, I'm I can do anything I can do to help you use AI and be a better club, I'll do it. I'll be I'll come out there."

</details>

**克莱尔·沃 (Claire Vo)**: 太酷了！如果这事成了，请务必把我和我丈夫也写进你们罗马俱乐部的 AI 数字化转型顾问清单里，我们绝对会第一时间报名去当志愿者。

<details>
<summary>Original English</summary>

**Claire Vo**: Put us into My husband and I will sign up for the AS Roma AI transformation work.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 没问题，到时候我们在球场见。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Perfect.

</details>

**克莱尔·沃 (Claire Vo)**: 哈哈，太棒了。

回到正题，我的最后一个快速问答：当你在使用智能体或编写提示词时，如果发现 AI 的输出彻底失控、开始在后台胡言乱语或者陷入死循环时，你个人的应对策略和直觉是什么？你通常会怎么做？

<details>
<summary>Original English</summary>

**Claire Vo**: I love it. Okay, uh my last lightning round question, which is when you're prompting and AI's going off the rails, what's your strategy? What do you do?

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 噢，伙计，这确实经常发生，也确实让人头疼。

通常，在我对着屏幕发泄性地骂它几句之后，我会采取以下几个步骤。

首先，因为我购买了市面上几乎所有大模型 API 供应商的付费订阅，所以我最直接的策略是：**换一个底层模型再试一次**。如果 GPT-4o 突然卡住，我就把当前的上下文直接打包丢给 Claude 3.5 Sonnet，换个模型的理解思路往往能收获奇效。

其次，**彻底丢弃当前的会话，重新开启一个新的空白对话**。大模型由于其注意力机制和上下文窗口的限制，一旦它在当前会话的某一步输出了一些错误的代码，这些错误的上下文就会在后续的生成中成为它的精神包袱，导致它越描越黑。重新开启对话是清除这种“历史包袱”最有效的物理手段。

接着，我会尝试去微调我的提示词和配置文件，把可能导致歧义的段落写得更加严密。或者，**尝试把大任务拆解为粒度更小、边界更清晰的子任务**。

如果你在智能体开发中完全没有遇到过失控或卡死的情况，那只能说明你给自己智能体设定的业务目标还不够有野心。智能体的边界就是在不断的失败中探索出来的。

另外，根据我的习惯，如果我只是做一些非常简单的修改，我会快速在终端里打字下指令；而一旦我开始发现智能体理解出现偏差、或者需要下达一些非常复杂的返工逻辑时，我会立刻转用**语音转文字输入（Speech-to-text）**。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Oh, man, it's hard. So, after I swear at it a couple times, uh I usually So, one like, you know, I have this subscription to all the providers. So, I maybe I'll just try another one. Yeah, restarting conversations. I think that's obviously like a great example and kind of like tweaking the prompt to put things in there. Try and break down the problem in smaller pieces, maybe. Um that's been another one. You know, sometimes you're being too ambitious. I think that's really the I think in general, if you're not getting enough failures, you're probably not trying hard enough. You know, you're not being ambitious enough in what you're doing. Yeah, and then yeah, try remember to be That's why sometimes I use I usually like start and I type something.

</details>

**克莱尔·沃 (Claire Vo)**: 没错，口语化的叙述往往包含更丰富的情境上下文。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 没错。当我敲键盘敲得手酸且开始感到沮丧时，我会直接按住麦克风，像跟我的副手交谈一样说一大长串话。

因为当你开始用嘴去描述一个问题时，你的大脑会强迫你去组织逻辑，你会在口头叙述中自然而然地补充进很多你在手动打字时懒得写进去的细节信息——比如你的最终业务意图、可能存在的边界情况等等。而正是这些随口说出的情境细节，能帮助智能体在重新理解任务时瞬间找到解法。

<details>
<summary>Original English</summary>

**Alessio Finelli**: And then once I get frustrated, I go back and I just like use speech-to-text

</details>

**克莱尔·沃 (Claire Vo)**: 没错，这在实际操作中屡试不爽。

<details>
<summary>Original English</summary>

**Claire Vo**: Yeah.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 当你觉得“我实在懒得在键盘上敲这几百个字去向你解释这个逻辑”时，按下语音键吧，它会极大地改善你的交互体感。

<details>
<summary>Original English</summary>

**Alessio Finelli**: for a longer prompt.

</details>

**克莱尔·沃 (Claire Vo)**: 的确是这样。

<details>
<summary>Original English</summary>

**Claire Vo**: Yep.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 这也确实能为智能体提供更优质的推理上下文。当然，具体要怎么做，依然得根据你的具体任务去灵活调整。

<details>
<summary>Original English</summary>

**Alessio Finelli**: I'm like, "All right, I can't I can't like keep typing these things." That helps sometimes because like once you start talking, you maybe just add a few more details that help.

</details>

**克莱尔·沃 (Claire Vo)**: 没错。之前来上过我们节目的好朋友希拉里（Hillary），她来过两次，也是我们节目非常受欢迎的嘉宾，她把这种人机交互方式形象地称为**“话痨式 API”（Yapper's API）**——你只需要按住语音键，对着它喋喋不休地输出你脑子里所有的混乱想法，讲完后直接按下发送，甚至不需要去检查里面的拼写错误，大模型强大的容错和总结能力通常能极其完美地解析出你的真实意图。在大部分情况下，这其实是和 AI 沟通最有效的方式。

阿莱西奥，今天和你聊得真的非常开心。非常感谢你来参加我们的节目。最后，大家可以在哪里关注你的最新动态？有什么是我们可以帮上忙的？

<details>
<summary>Original English</summary>

**Claire Vo**: Yep. Um but I think it really depends on on the task sometimes. Yeah. My my friend Hillary came on the podcast. She's actually been on twice, very popular guest. She calls it the yapper's API, which is she she just goes You just go like this until you've gotten it all out and you press enter, you don't even look at it, and that is is usually the most the most effective thing. Well, this has been super fun. Thank you so much for joining. Where can we find you, and how can we be helpful?

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 谢谢大家。我的 Twitter/X 账号是 **@fanahova** （拼写为 f-a-n-a-h-o-v-a），也欢迎大家在各大音频平台订阅和收听我们的 **Latent Space** 播客。

另外，我在旧金山创办和运营着一个名为 **Kernel** 的物理众创孵化空间。如果你目前人在旧金山湾区、或者打算来这里旅游，非常欢迎随时来我们这里工作和交流。我们这里提供非常开放和自由的联合办公（co-working）空间，我们每个月会举办 15 到 20 场前沿的行业沙龙和社区活动。就在昨天，我们刚办了一场垫上普拉提（Mat Pilates）课程，我们邀请了来自 OpenAI 的一位老朋友来客串我们的教练。

如果你正在开发一些和我们今天聊到的“AI 软件自动化开发工作流”、“智能体辅助工具链”等相关的创新项目，我非常乐意随时和你聊聊。

<details>
<summary>Original English</summary>

**Alessio Finelli**: I'm on Twitter at fanahova, f a n a h o v a, and then yeah, you can subscribe to the Leading Space podcast. Um What else? Well, I also run a space and a sub called Kernel. So, if you want to come work from here, we have a open co-working. We do like 15 20 events every month. We just did a mat Pilates class yesterday with somebody from Open AI as the teacher. Um so, yeah, just come hang, say hi. Um yeah, and if you're building anything interesting in this kind of like, you know, software factory space, I'm always happy to chat.

</details>

**克莱尔·沃 (Claire Vo)**: 太酷了。最后，再提醒一下大家你刚才提到的实体宝可梦卡牌商店的地址和名字？

<details>
<summary>Original English</summary>

**Claire Vo**: And remind us where the the store is.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 好的，我们的店位于圣卡洛斯（San Carlos），名叫 **Merlion Games**，欢迎大家来店里坐坐。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Uh San Carlos, called Merlion Games.

</details>

**克莱尔·沃 (Claire Vo)**: 完美，信息全了。阿莱西奥，非常感谢你来到 *How I AI*。

<details>
<summary>Original English</summary>

**Claire Vo**: Okay, we got it all. Thank you so much for joining How I AI.

</details>

**阿莱西奥·法内利 (Alessio Fanelli)**: 谢谢大家，拜拜。

<details>
<summary>Original English</summary>

**Alessio Finelli**: Bye-bye.

</details>

**克莱尔·沃 (Claire Vo)**: 谢谢阿莱西奥。

非常感谢大家的收看与收听。如果你喜欢本期节目，请点击视频下方的点赞，并订阅我们的 YouTube 频道。或者，更棒的做法是直接在评论区写下你对于我们今天讨论的“云端智能体工作流”或“小企业 AI 应用”的看法。你也可以在 Apple Podcasts、Spotify 或任何你喜爱的音频应用上搜索并收听我们的播客。如果你能花一分钟为我们留下一个五星好评，将对我们非常重要，这能帮助更多和你有相同兴趣的人发现这档节目。你可以访问我们的官方网站 **howiaiipod.com** 查看往期所有节目详情。

我们下期节目再见。

<details>
<summary>Original English</summary>

**Claire Vo**: Thank you. Thanks so much for watching. If you enjoyed the show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaiipod.com. See you next time.

</details>