---
author: AI Engineer
date: '2026-06-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ZRM_TfEZcIo
speaker: AI Engineer
tags:
  - personal-knowledge-management
  - deep-research
  - context-management
  - memory-management
  - rag
title: 将 10,994 条笔记转化为活体研究记忆：构建个人 AI 研究操作系统
summary: Paul Iusztin 和 Louis-François Bouchard 分享了他们如何用 18 个月时间，将 Obsidian、Readwise 等工具中的上万条笔记，通过一个基于纯文件、无数据库的三层架构（原始内容、索引、Wiki），构建成一个可查询、可演化的个人 AI 研究操作系统。他们详细介绍了从简单深度研究算法到集成第二大脑，再到最终加入 Wiki 层的演进过程，并展示了如何通过 Claude Code 插件实现自动化研究、代码库分析和知识沉淀。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Paul Iusztin
  - Louis-François Bouchard
companies_orgs:
  - Decoding AI
  - Towards AI
  - OpenAI
products_models:
  - Obsidian
  - Readwise
  - NotebookLM
  - Claude Code
  - Gemini
media_books:
  - LM Engineers Handbook
  - Building AI systems for production
status: evergreen
---
### 构建个人研究操作系统

**Paul Iusztin**: 我花了 18 个月的时间，把我的第二大脑变成了一个活体的研究记忆。让我来解释一下。在我的第二大脑中，我目前在 **Obsidian** 里有超过 5000 条笔记，在 **Readwise** 里还有另外 5000 条，还有一些散落在 **Notion** 和 **Google Drive** 里。所有这些还在增长，每周增加 250 个文件，每月就是 2500 个文件。

<details>
<summary>Original English</summary>

**[Paul Iusztin]**: I spent 18 months turning my second brain into my living research memory. Let me explain. So, within my second brain, I currently have over 5,000 notes in Obsidian and another 5,000 notes in Readwise and some scattered in Notion and Google Drive. And all of this is growing on every week 250 files per month.

</details>

这就是我想要的。在左边，你可以看到我整个 Obsidian 库，这一大堆东西。每当我开始做某件事，比如写一篇文章、一个新项目、一个新代码库、一个新功能或其他什么，我都希望能真正拉出那些对我的当前工作有用的高信号笔记。

<details>
<summary>Original English</summary>

And this is what I want. On the left, you can see my whole Obsidian vault, this huge mass. And whenever I start working on something such as an article, a new project, a new code base, a new feature, or whatever, I want to actually pull high-signal notes that are actually useful for my current work.

</details>

你可能会问，为什么不直接用 **Claude Code** 或 **NotebookLM**？我觉得我确实在用。但你需要一个系统，它位于那些工具和你的第二大脑之间。好，让我们回到问题的根源，那就是我总是在丢失我的研究。比如，我的阅读列表就是一个坟墓。当我在刷社交媒体时，保存了一条很酷的 X 帖子、一篇新文章、一个新的 YouTube 视频、一个 GitHub 仓库，不管是什么。每当我真正想开始做某件事时，我从来想不起我的第二大脑里有什么，或者我必须花大量时间去寻找那些能用于工作的有意义的笔记。

<details>
<summary>Original English</summary>

And you would ask yourself, why not use directly Codex Cloud or Notebook LM? And I think it's that I am. But you need a system that sits between those harnesses and your second brain. Okay, so let's go back to the root of my problem, which is that I'm always losing my research. For example, my reading list is a graveyard. When I'm scrolling social media and I save that cool X post, a new article, a new new YouTube video, a GitHub repository, it doesn't matter. Whenever I actually want to start working on something, I never recall what I have in my second brain or I have to spend a ton of time actually finding meaningful notes that I can use in my work, right?

</details>

我的另一个问题是，我希望这个系统能真正锚定在我的个人笔记、个人价值观和个人信念中。我希望这个系统是个人化的，能反映我自己的想法。这就是为什么在今天这个视频里，**Louis-François** 和我会教你如何构建你自己的 AI 研究操作系统。这也附带了代码，所以你也可以自己尝试。

<details>
<summary>Original English</summary>

And another problem that I have is that I want the system to actually be anchored into my personal notes, into my personal values, into my personal faith. I want the system to be personal to reflect my own thoughts, right? And that's why in today's video, Louis François and I will teach you how to build your own AI research OS. This also comes with code, so you can also try it out yourself.

</details>

我是 **Paul Iusztin**，我是 **Decoding AI** 的创始人兼 CEO，在那里我制作了大量关于如何交付 AI 产品的内容和课程。我也是畅销书 **《LM Engineers Handbook》** 的合著者。我今天要教你的这个系统，这个 AI 研究操作系统，就是我在日常工作中使用的系统。现在，我把接力棒交给 Louis-François。

<details>
<summary>Original English</summary>

And I'm Paul Yushin. I'm the founder and CEO of Decoding AI, where I do a ton of content on courses on how to ship AI products. And I'm also the co-author of the LM Engineers Handbook bestseller. And the system, the AI research OS that I will teach you in this video is the system that I use in my daily work. And now I will pass the torch to Luis François.

</details>

**Louis-François Bouchard**: 谢谢，Paul。我是 **Louis-François Bouchard**，**Towards AI** 的联合创始人兼 CTO，我们构建教育课程。我也是 **What's AI** 这个 YouTube 频道的创建者，在那里我讲解 AI 工程技术。我以前讲解 AI 研究，现在专注于 AI 工程。我还是 **《Building AI systems for production》** 这本书的作者。在那之前，我是一名博士生。所以，老实说，我是靠做研究为生的。正如我说的，我以前读 AI 博士，做了大量的研究工作。现在，我靠构建课程、写视频、为视频做研究、为公司做培训为生。我做的所有这些事情都始于一个非常好的研究。同时还要利用我们在 Towards AI 为客户构建东西时获得的大量知识和见解。所以，我也有大量的笔记，就像 Paul 一样。我们试图尽可能地利用它们。

<details>
<summary>Original English</summary>

**[Louis-François Bouchard]**: Thanks, Paul. So, I'm Luis François Bouchard. I'm the co-founder and CTO of Towards AI, where we build educational courses. And I'm also the creator of What's AI, a YouTube channel where I explain AI engineering techniques. I used to explain AI research before. Now, I'm focusing on AI engineering. I'm also the author of the book Building AI systems for production. And before that, I was a PhD student. So, I honestly make research for a living. I used to do a PhD, as I said, in AI and doing tons of research and research work. Now, I build courses, I write videos, I research for videos, I build trainings for companies for a living. And all of these things that I do start with a very good research. And also leveraging tons of knowledge and insights that we get at Towards AI from building for clients. So, I have tons of notes as well, just like Paul. And we try to leverage them the best possible.

</details>

正如你将看到的，我们会构建某种工具来利用我们的第二大脑，你会看到我使用它的方式和 Paul 使用它的方式会有一些不同。这就是我们构建这个仓库和这个项目的核心目标：我们希望你能根据自己的需求来调整它。整个目标是如何让研究变得更好，但更具体地说，我们如何更好地利用我们已经拥有的东西？那么，让我们深入探讨一下。

<details>
<summary>Original English</summary>

And as you'll see, we'll build some sort of tool to leverage our second brain, where as you'll see, there will be some differences between how I use it and how Paul uses it. And that's the core goal of the repository that we built and on this project is that we want you to adapt it for your needs. The whole goal is how can we make research better, but more specifically, how can we better leverage what we have? So, let's dive into it.

</details>

### 选择合适的工具

首先，我们需要弄清楚使用哪种工具以及何时使用，因为我们构建的这个研究系统并不适用于所有查询。如果你只是需要一个快速的答案，比如几个简单的问题，或者一些你本来就会用 Google 搜一下的东西，那么显然，直接用 Google 搜，或者问 **ChatGPT**、**Claude**，任何你想要的系统都行。但这样做的问题是，如果你有很多后续问题，或者这是一个更大的项目，需要你在此基础上构建，并且需要非常长的上下文或分享大量信息，那么依赖 ChatGPT 就不理想了。这也意味着你完全依赖于 OpenAI 或 ChatGPT 团队构建的架构。

<details>
<summary>Original English</summary>

And first, we need to figure out which tool to use and when, because this whole research system that we built is not for every query. If you just need a fast answer, like a few quick questions or just something where that that you would just Google, basically. Well, obviously, just Google it or ask ChatGPT, Cloud, whichever system you want. But, the problem when doing that is that if you have a lot of following up question or it's a bigger project that you need to build on and have basically a very long context or tons of information to share, relying on ChatGPT isn't ideal. And it also means that you are fully dependent on the architecture that OpenAI or ChatGPT's team built.

</details>

所以，下一步是问自己，对于一个更复杂的问题，你是需要快速行动，还是想构建下一个功能，做一些非常困难的事情？如果你只是有一个小仓库要做快速修改，或者写一篇文章，只做一件你知道不会经常重复的事情，那么绝对可以使用 **Claude Code** 或某个你信任的 Agent。但有时，你需要不断深挖，让它变得更好，提高效率，进一步优化。通常，当你需要这样做时，你希望你的研究来源、你的研究能够留存下来，并且能够在未来引用它们。

<details>
<summary>Original English</summary>

So, the next step here is to ask yourself for a more complex problem, do you need to act quickly or do you want to build some next feature and and do something very difficult? If you just have a small repo for a quick change or write one article, just do one thing that you know won't be repeatable that much, definitely use Codex or Cloud Code or some agent that you trust. Sometimes, you need to keep on digging to make it better, to improve efficiency, optimize it more. And so, typically, when you have to do that, you want your research sources, your research to stick and to be able to refer to them in the future.

</details>

如果你想要这样一个过程：你找到的来源、你做的笔记能够随时间留存，并且让 Agent 能够高效地利用它们，能够回来查看这些信息，提出后续问题，甚至进一步消化内容。例如，现在当我制作一个新视频时，我也希望 Agent 和系统能理解我之前做过的视频，以避免内容重复，不重复自己，并能引用其他内容。

<details>
<summary>Original English</summary>

So, if you want a process like this where the sources that you find, the notes that you take stick around in time and have an agent be able to leverage that efficiently and being able to come back to these information, to ask follow-up questions, to digest content even more. And right now, for instance, when I make a new video, I want also the agent and the system to understand the previous videos I made to not duplicate content, to not repeat myself, and to refer to some other content.

</details>

在这种情况下，有一些非常有趣的工具你可能以前试过，比如 **NotebookLM**，它在做研究、高效消化内容以及回顾内容方面非常强大。但 NotebookLM 的问题是，首先，主要问题是你并不拥有它。你不能用它做任何你想做的事。你无法尽可能地个性化。它不是 Agent 原生的。而且它显然在编码任务上很弱，因为它只是基于浏览器的。所以，它远非 Paul 和我所需要的，也远非大多数 AI 工程师普遍需要的。

<details>
<summary>Original English</summary>

In this case, there are some tools that are very interesting that you might have tried before, like NotebookLM, that is super powerful to do research, to digest content efficiently, and to come back to it. But, the problem with NotebookLM is that is Well, first, the main problem is that you don't own it. You cannot do anything you want with it. You cannot personalize as much as possible. It's not agent native. And it's obviously weak for coding tasks since it's just browser based. So, it's far from ideal from something that Paul and I needed and that most AI engineers need in general.

</details>

所以，如果你需要你的 Agent 能够利用你所做的一切，无论是大型研究、新视频、你写的任何东西、你做的任何事、你编写的代码，你通常希望你其他的 Agent、你其他的项目能够利用你从刚刚完成的工作中学到的东西。我们建议的一件事，特别是对于生产环境，显然对于产品来说，是构建某种带有向量数据库的检索 RAG 管道。但这需要基础设施。它不太人性化，无法快速消化、检查笔记、进行编辑。很难手动检查。你需要围绕它构建一切。对于我只是想日常使用的东西来说，这绝对不理想。显然，它在规模上非常强大，非常有趣，尤其是在产品中。但正如我所说，这个项目是为我们自己做的。我不想要一个在线的、超级专业的产品。我只想要一个我会使用的东西，并且我的 Agent 和不同项目能够尽可能好地利用它。

<details>
<summary>Original English</summary>

So, if you need your agents to be able to leverage all you do, whether it is a big research, a new video, whatever you write, you do, you code, you typically want your other agents, your other projects to be able to leverage what you learn from what you just did. And one thing that we advise especially for production, obviously for product, is to build some sort of retrieval rag pipeline with vector databases. But, this needs an infrastructure. It's not really human-friendly to be able to digest quickly, to check notes, to make edits. It's hard to inspect by hand. You need to build everything around it. It's definitely far from ideal for just something I want to use on a daily basis. Obviously, it's super powerful at scale, very interesting especially in a product. But, as I said, this project is for us. And I don't want something live, super professional as a product. I just want something I will use and that my agents and different projects can leverage as best as possible.

</details>

所以，最后一个要问自己的问题是，如果你想要以上所有功能，但需要更多的个性化，也就是一个个性化的研究助手，它能构建某种随时间累积的 Wikipedia，并且易于检查和使用的，你拥有大量的来源、文档、视频、比较、实现、新的研究、新的话题，你不断添加它们，并且你希望轻松地利用和回顾它们，那么这就是你可能想要自己构建一些东西的时候了。在我们的案例中，我们构建了一个个性化的研究操作系统，我们将在本次演讲中分享我们构建的具体内容和方式。但缺点是，它肯定比仅仅打开 Claude Code 需要更多的设置。

<details>
<summary>Original English</summary>

So, the last question to ask ourselves here is that if you want everything there but more personalization, so a personalized research assistant that builds some sort of Wikipedia that compounds over time and and is easily inspectable and usable where you have tons of sources, documents, videos, comparisons, implementations, new research, new topics that you keep on adding and that you keep on wanting to leverage and review easily, this is where you may want to build something yourself. And in our case, we built a personalized research OS that we will share in this talk with exactly what we built and how. But, the downside is that it definitely needs a bit more setup than just opening Cloud Code.

</details>

### 上下文与记忆管理

现在，使用 Claude Code 和其他 Agent 工具的主要问题是，你给 Codex 链接、PDF 和各种信息，比如我最近的 **Loop Engineering** 视频，然后下一次你使用 Codex 时，你必须重新粘贴所有内容，或者要求它使用技能。而 Codex 或 ChatGPT，无论你使用什么工具，它们为了利用你之前所做的工作而即时构建的任何结构、它运行的脚本、它拥有的脚本，你都会全部丢失，或者保留在一个你必须要求它重用的技能里，这通常不理想，而且会随着时间的推移不断膨胀。

<details>
<summary>Original English</summary>

Right now, the main problem with using Cloud Code and other agentic tool is that you give Codex links, PDFs, and different information, for example, my most recent Loop Engineering video, and then the next session you use Codex, you have to paste it all again or ask it to use skills. And whatever structure that Codex or ChatGPT, whatever tool that you use, build on the fly to leverage what you did, the scripts it ran, the scripts it had, you all lost it or kept it inside a skill that you have to ask it to reuse, and that usually isn't ideal and just grows and grows over time.

</details>

问题在于，你给模型的所有这些信息并不是瓶颈。瓶颈在于你未来如何利用它。这意味着，对于一个 Agent 来说，上下文窗口变成了一切：数据库、文件系统、记忆、推理空间。它必须包揽一切，当你停止对话时，它就失去了一切。关键是，我们不一定需要为更好的研究提供越来越多、越来越多的上下文。你需要的是恰当的记忆和上下文管理，理想情况下还要带有个性，尤其是在我制作视频的时候。

<details>
<summary>Original English</summary>

And the problem is that all this information that you give to the model is not the bottleneck. The bottleneck is how can you leverage it in the future? Meaning that with an agent, the context window becomes everything, the database, the file system, the memory, the reasoning space. It has to do it all, and when you stop the conversation, it loses everything. And the thing is that we don't need necessarily to provide more and more and more context for a better research. You need a proper memory and context management, and ideally some personality with it, especially in my case when I do videos.

</details>

所以，我们决定构建一个基于纯文件的系统，主要是 **Markdown** 文件，这样我们可以轻松利用，Agent 也可以轻松利用。我这里不会详细说明，因为 Paul 会深入讲解。正如我所说，Paul 有大约 5000 条笔记。我只有几百条，但这只是想说明我们不是从零开始的。我们俩都已经有了某种大型数据库。

<details>
<summary>Original English</summary>

So, what we did is that we decided to build a system with plain files, mostly markdown files, that we can leverage easily and that agents can leverage easily. I won't detail it very much here because Paul will talk about it in depth. And as I said, Paul has like 5,000 or something notes. I have just a few hundred, but that's just to say that we need to consider that we didn't start from nothing. We already both had some sort of large database.

</details>

就我而言，我制作了数百个视频，并且做了很多笔记。所以，我仍然需要利用我已经制作的这些年的内容，以及我与团队、客户在为他们构建东西时的大量会议，我也想利用这些，因为我们在为别人构建东西时学到了很多。我有我看到的有趣推文、有趣文章的高亮，我希望我所有的项目都能利用我的 Agent 技能。所以，我决定转变方向，不再为 Claude Code 技能设置一个文件夹，不再把会议记录放在 **Granola** 里，不再把多年的笔记放在 **Apple Notes** 里，不再把推文保存在 Chrome 标签页里，而是把所有内容自动移入 Obsidian。它只是一个笔记阅读器，显然，你不一定非要用它。你可以只在本地保存，但我用 Codex 设置了所有东西，这样 Granola 会自动保存在那里，我的笔记现在都在 Obsidian 里，只是因为它有一个不错的 UI，我喜欢它，而且我可以在手机、电脑、Windows、Mac 等各种设备上使用它。总之，我把所有东西都移到了 Obsidian，这意味着它保存在我本地的文件系统中，这意味着它基本上是我现在研究和构建一切事物的伴侣。

<details>
<summary>Original English</summary>

In my case, I made hundreds of videos and I take many notes. So, I still need to leverage these years of content that I already made and tons of meetings that I have with my team, with clients when we build for them that I want to leverage as well because we learn a lot by building for people. We have highlights from interesting tweets that I see, interesting articles that I see, and I want all my projects to be able to leverage my agent skills. So, I decided to pivot and instead of having a folder for Cloud Code skills and having all my meeting recaps in Granola and having years of notes on Apple Notes and the tweets on the saved Chrome tab, instead, I moved everything automatically into Obsidian. It's just a note reader, obviously, so you don't have to use that. You can just save it locally, but I used Codex to set up everything so that Granola is automatically saved there, my notes are now on Obsidian just because it's a nice UI, I like it, and I can use it from my phone, my computer, my Windows, Mac, everything. So, anyways, I moved everything to Obsidian, which means that it's saved locally in my file system, which means it's basically my companion for researching and building everything I build now.

</details>

### AI 研究 OS 仓库

我们构建的东西显然利用了这一点。我们为这个工作坊构建了一个名为 **AI Research OS** 的仓库，它基本上只是 Claude Code 和 Codex 的技能，带有插件，能够对一个主题进行非常深入的研究，或者进行更简单的搜索或提炼，你可以使用不同的工具。最有用和最完整的一个是我使用的研究工具，例如，当我启动一个新视频主题时。这个仓库的目标是让你实现它，从中安装云插件，并根据你的需求进行调整。目前，它可以连接到，正如我所说，我的本地笔记所在的 Obsidian。它可以使用 Readwise、NotebookLM、你的 GitHub 仓库、你发送的任何 GitHub 或 YouTube 视频链接，以及网页链接和文档。但还有很多缺失的东西，我们将在最后讨论，你可以通过简单地要求 Claude Code 或 Codex 来轻松实现。例如，我实现了 YouTube 视频转录功能，老实说只用了几秒钟，一个提示就搞定了。对于 Codex 来说，实现它非常容易。所以，整个仓库和整个项目对我自己的工作来说是一个非常有用的伴侣。但正如我所说，它实现了大量的功能和最先进的上下文管理和记忆管理技术，我相信 AI 工程师需要了解这些。

<details>
<summary>Original English</summary>

And what we built, obviously, leverages that. We built a repo called AI Research OS for this workshop where it's basically just skills for Cloud Code and Codex with plugins to be able to do a very deep research about a topic or a simpler search or distillation, different tools that you can use. The most useful and complete one will be the research tool that I use, for example, when I kick off a new video topic. And the goal of this repo is to have you implement it, install the cloud plugins from it, and tune it to your needs. Right now, it can connect to, as I said, Obsidian with my local notes. It can use Readwise, Notebook LM, your GitHub repos, any links that you send for GitHub or YouTube videos, and web links, obviously, and documents. But there are tons of things missing, as we will discuss in the end, that you can easily implement, just asking Cloud Coder or Codex to do so. Like for example, I implemented the YouTube video transcript in honestly a few seconds, just one prompt. It's super easy for Codex to implement it. So, the thing is that this whole repository and this whole project is a very useful companion for my own work. But, as I said, it implements tons of features and state-of-the-art context management and memory management techniques that I believe AI engineers need to know.

</details>

现在，Paul 将深入探讨我们构建的这个三层系统，包括原始内容、我提到的索引，以及类似 Wiki 的合成版本，它整合了你所有的笔记、研究和所有工作。所以，他会涵盖我们所做的一切，最终结果如何，并展示如何使用它。

<details>
<summary>Original English</summary>

And now, Paul will dive into all this three-layer system that we built with the raw content, the index that I mentioned, and the wiki-like synthesized version of all your notes, all your research, all your work. So, he'll cover everything we did, how it ended up, and show how to use it.

</details>

### 系统演进：V1 到 V3

**Paul Iusztin**: 好的，现在我想回顾一下我们系统的三个版本，以及它是如何随时间演进的，最重要的是，我们为什么要增加复杂性。在第一个版本中，我们只想把它限定在为我们的 **Agent Engineering** 课程创建课程内容。所以，我们希望保持非常简单，输入是一个主题，输出是一个研究 MD 文件。在输入中，我们有主题加上一组**黄金链接**，这些链接是我们手动挑选的。我们应用了这个深度研究算法，输出是一个静态的研究 MD 文件。

<details>
<summary>Original English</summary>

**[Paul Iusztin]**: Okay. So, now I want to go over the three versions of our system and how it progressed over time, and most importantly, why we added more complexity. So, in the first version, we wanted to scope it just to create lessons for our agent engineering course. So, we wanted to keep it super simple, where we had as input a topic and a research MD as output. So, within the input, we had the topic plus a set of golden links, which were manually handpicked by us. We applied this deep research algorithm, and we had as output a static research MD file.

</details>

如果我们放大架构来看，我们首先抓取了黄金链接的内容，因为我们已知它们，并将它们用作深度研究算法的种子上下文，这是一个非常强大的技术，因为我们有更多的上下文来构建我们的问题。在查询轮次中，我们基本上使用了非常经典的深度研究算法，其中有一个主 Agent，即编排器，它根据初始主题和抓取的上下文生成多个问题。每个 Agent 管理自己的问题，并使用 **Gemini**（基于 Google 搜索）来查询 Google 并收集多个资源。每个 Agent 收集这些资源，返回多个链接，并为每个链接创建执行摘要。然后，它将所有这些信息传回给主 Agent，主 Agent 基本上以汇总的方式聚合所有这些信息，这样就不会撑爆上下文。我们这样做了三轮。基本上，经过三轮，每轮生成六个查询，我们最终得到了大约 40-50 个链接。所以你可以想象那里有很多噪音。这就是为什么我们还应用了一个排序算法，我们希望找到信号最高的信息。基本上，我们将每个来源与用户的初始主题进行比较。这样，我们只根据排序分数完全抓取前 K 个元素。对于其余的链接，我们只保留摘要。然后，我们将所有内容编译到这个研究 MD 文件中，作为一个单一的平面文件，在我们的特定用例中，我们用它来为课程的每一课提供内容。

<details>
<summary>Original English</summary>

And if we go zoom into the architecture, we first scraped the links of the golden links, right? Because we already know them and we use them as seed for context for the deep research algorithm, which was a really powerful technique because we had more context on how to frame our questions. And during the query rounds, we basically used the very classic deep research algorithm where we had one main agent, the orchestrator, which created multiple questions based on the initial topic and the scraped context. And each agent managed its own question and used Gemini grounded in Google to to query basically Google and gather multiple resources and each agent gather these resources, which returned multiple links and created some executive summaries of each link. And then [snorts] it passed all this information back to the agent to the main agent where the main agent basically aggregated all this information into a summarized way so it did not exploded the context. And we did this for three rounds. So basically after three rounds of generating six queries per round, we ended up with like 40-50 links in total. So you can imagine that there's a lot of noise over there. So that's why we also applied a ranking algorithm where we wanted to like find the the information with the highest signal. And basically we compared each source against the topic, the initial topic of the user. And like that, we fully scraped only the top K elements based on the ranking score. And for the rest of the of the links, we just kept the summaries. And then we compiled everything into this research MD file as a single flat file which we used for each lesson of our course in in our particular use case.

</details>

但你可以想象，这相当有限。对于课程来说，它立竿见影，效果很好。我们很快生成了 35 课，但我们想要更多。所以，我们开始将这个深度研究循环也瞄准第二大脑。以前，它只针对公共网络，这使得它相当通用，我们必须手动找到所有那些黄金链接。所以，通过将这个深度研究循环瞄准第二大脑，我们基本上有机地跟踪了我们真正想要的所有信息，所有经过我们过滤的研究，我们可以有机地将所有那些黄金链接收集到我们的深度研究算法中。

<details>
<summary>Original English</summary>

But as you can imagine, it was pretty limited. For the course, it worked great right away. We generated 35 lessons really quick, but we wanted more. So, we started to aim this deep research loop to the second brain as well, right? Before, it was targeting only the public web, which made this a pretty generic, and we had to manually find all those golden links. So, by aiming this deep research loop to the second brain, where we basically organically keep track of all the information that of all the research that we really want and is filtered by us, we can organically gather all those golden rings into our deep research algorithm.

</details>

### V2：集成第二大脑

那么，让我们看看这个新算法是什么样的。它基本上是相同的循环，但现在我们针对的是我们自己的来源，而不仅仅是公共网络。现在，输入只有主题，因为我们不需要黄金链接。正如我所说，黄金链接实际上是我们第二大脑系统的反映。理论上，如果你真的想，你也可以添加它们，但这就是这个新策略的美妙之处，因为你只需输入一个主题，我们就会找到它所需的一切。然后，我们只使用这个主题作为种子上下文来生成查询。现在我们做同样的深度研究算法，同样的查询轮次，但不再只针对公共网络，现在我们插入了我们所有的第二大脑，比如我们的 Obsidian、Readwise、NotebookLM、GitHub。你也可以使用，例如，**Gemini Deep Research** 来做这个，类似于我们使用 NotebookLM 的方式，或者你可以用任何你想要的东西来扩展它。例如，YouTube、Google Drive、Notion，或者任何在你的基础设施中有意义的东西。想法是，现在我们将深度研究算法的查询目标对准我们的第二大脑加上公共网络。之后，我们应用相同的算法，如排序、完全抓取、摘要，并将所有内容编译到这个研究 MD 文件中。

<details>
<summary>Original English</summary>

So, let's look at how this new algorithm looks like. It's basically the same loop, right? But now we target our own sources instead of just the public web. Now, for input, we have only the topic because we don't need the golden links. As I said, the golden links are actually a reflection of our second brain system. In theory, you can also add them if you really want to, but that's the beauty of this new strategy because you can just put as input some topic and we'll find everything that it needs. And then we use this topic only as seed for for for the context to generate the the queries. And now we do the same deep research algorithm, right? The same query rounds, but instead of targeting only the public web, now we plugged in all our second brains, such as the our Obsidian, our Readwise, our Notebook LM, our GitHub. You can also use, for example, Gemini deep research for this, like similar to how we we use notebook LM or you can extend this with whatever you want. For example, YouTube, uh Google Drive, Notion, or whatever makes sense on your infrastructure. The idea is that now we are target our queries from the deep research algorithm to our second brain plus the public web. And after we apply the same algorithm such as ranking, fully scraping, summaries, and compile everything into this research MD file.

</details>

但现在我们有了另一个问题。这个研究 MD 文件是静态的。它是一堆静态数据。而研究通常不是静态的。所以，在你最终得到这个文件后，你通常会意识到你想问另一个问题，或者有些信息已经过时，你不再需要了。或者基本上，你想从这个研究 MD 文件中获得更多。这意味着你需要从头开始这一切。而我上面展示的操作是一个庞大的操作。它消耗大量的 Token，并且需要大量时间。所以，你不想从头开始运行它。这就是为什么你需要在它之上添加一个 Wiki 层。

<details>
<summary>Original English</summary>

But now we have another problem, right? This this research MD file is static. It's a pile of static data. And usually research is not static, right? So, after you end up with with this file, you most often realize that you want to ask another question or some information is stale and you don't need it anymore. Or or basically, you want more out of this research MD file. And we which means that you need to start all of this from scratch. And the operation that I showed you uh above is an extensive operation. It consumes a lot of tokens and it takes a lot of time. So, you don't want to run it from scratch. And that's why you need to add a wiki layer on top of it.

</details>

### V3：引入 Wiki 层

这就是为什么这个系统的 V3 实际上是一个深度研究算法加上一个在其之上的 LM 知识库，也就是 Wiki 层。所以，新算法看起来是这样的：我们有来源输入，Wiki 输出。来源，正如我之前所说，可以是 Obsidian、NotebookLM、Google Drive、YouTube、Notion，甚至是自定义 URL。这也非常强大，你可以使用诸如 **Bright Data** 之类的工具来解析基本上任何单页应用程序、任何类型的网站、任何类型的公开信息。我们可以把它放进去。然后你应用相同的深度研究算法。你将所有内容存储为原始文件，而不是将所有内容编译成一个研究 MD 文件，现在我们单独存储每个文件。我们为所有这些文件创建一个索引。最终，我们在其之上生成一个 Wiki，我们可以查询它。我们基本上可以查询 Wiki 加上索引。好的，这只是新系统的高级架构。让我们放大来看。

<details>
<summary>Original English</summary>

And that's why V3 of this system is actually a deep research algorithm plus an LM knowledge base on top of it, aka the wiki layer. So, the new algorithm looks like this. So, we have sources in and a wiki out. And the sources, as I said before, can be like Obsidian, notebook LM, Google Drive, or YouTube, Notion, even custom URLs, right? That that's also powerful as well, where you use tools such as a Bright Data to to parse basically any single page application, any type of site, any type of public information that's out there. We can put it in. And then you apply the same deep research algorithm. You store everything into raw files, right? Instead of compiling everything into research and D file, now we store each file individually. And we create an index out of all these files. And ultimately, we generate a wiki on top of it, and which we can query. We can query basically the wiki plus the index. Okay, so this is just the high-level architecture of the new system. Let's zoom into it.

</details>

我想首先说的是，你应该忘记你认为你需要的基础设施，比如向量数据库、知识图谱、语义搜索、文本搜索。所有这些都很美好，但增加了大量复杂性，特别是对于这种你想轻量使用的个人 Wiki、个人研究操作系统。所以，我想要一个仅基于文件的系统，一个简单的机制，深深植根于你计算机的工作方式。这就是为什么我们将整个系统建立在文件和引用的基础上。没有数据库，只有一个基于引用的简单索引。

<details>
<summary>Original English</summary>

So, what do I want to start with is that you should forget the infra structure you think you need, such as vector databases, knowledge graphs, semantic search, text search. All that is beautiful, but add a lot of complexity, especially for like this personal wikis, personal research operating systems that you want to use very lightly. So, I want a system just based on files, right? A simple mechanism that's that's very rooted into how your computer works. And that's why we'll create all the system just based on files and just based on references. So, no database, just a simple index based on references.

</details>

这是如何工作的？我们有一个 Agent，它读取一个 **index.yaml** 文件，这个文件基本上是你所有数据的目录，加上每个来源的摘要和一些元数据。例如，在右边，你可以看到一个 index.yaml 文件的一部分，它包含了 10 个来源和 38 个 Wiki 页面作为这些来源的衍生品。在 YAML 文件的来源列表中，我们可以看到第一个来源。正如你所见，它有指向原始文件的链接，加上一些元数据，比如来源、标题、作者、出版日期、摘要等等，这些都可以很灵活。下一步是，基于这个 index.yaml 文件，我们需要指向所有的 Wiki 页面、所有的 Wiki 衍生品、所有的原始来源。所以，基本上，这个 index.yaml 文件是我们 Agent 的入口点。它是我们给 Agent 用来推理如何找到我们数据的东西。它最终是一个索引。

<details>
<summary>Original English</summary>

And how how this works? We have an agent that reads an index.yaml file that's basically a catalog of your all your data plus the summaries of of each source and some metadata around it. For example, here on the right, you can see part of an index.yaml file that contains 10 sources and 38 wiki pages as derivatives of these sources, where uh we can see there into the sources list of the YAML file the first uh source, for example. And as you can see, it has like the the the link to the original file plus some metadata, such the origin, the title, the authors, the the the publication date, the summary, and and things things like this, which can be flexible, right? And the next step is that based on this index.yaml file, we need to point to all the wiki pages, to all the wiki derivatives, to all the raw sources. So, basically, this index.yaml file is an entry point for our agent, right? It's what we will give to our agent to actually reason on how to find our data. It's an index, ultimately, right?

</details>

### Wiki 的结构与查询

下一步是理解 Wiki 的实际样子。在左边，你可以看到 Wiki 的高级结构，我们有 raw 文件夹、wiki 文件夹和索引。在 raw 文件夹中，我们只有原始数据，这是不可变的。你不想碰它。索引指向我们需要的一切。在 wiki 中，我们有由 LLM 创建的衍生品，其中包含诸如多个概念之间的比较、实体，或者仅仅是作为我们问题或我们摄入的仓库的反映的简单笔记，我们可以基于一个仓库创建多个笔记。或者基于我们 LLM 尚无法回答的问题而产生的开放性问题。以及你可以在原始数据之上分析的一切。

<details>
<summary>Original English</summary>

So, the next step is to understand how the wiki actually looks like. So, on the left, you can see the high-level structure of the wiki, where we have the raw folder, the wiki folder, and the index. In the raw folder, we actually just have the raw data, which is immutable. You don't want to touch that. The And the index points to everything that we need. And in the wiki, we actually have derivatives created by the LLM, which contains things such as comparisons between multiple concepts, entities, or just simple notes as a reflection of our questions or repositories that we ingested, and we can create multiple notes based on a on on on a repository, right? Or open questions that based on our questions that LLM couldn't answer yet. And everything that you can analyze on top of your raw data.

</details>

在右边，基于 Obsidian，我们可以看到仅基于这个索引反映出的子图。这只是第一次迭代，但随着 Wiki 的增长，你可以看到实体和概念之间建立的联系。例如，概念是像工具注册表、上下文压缩、沙箱这样的东西，而实体是像开放代码、封闭代码、**MCP** 这样的东西。所以，正如你所见，你可以美妙地开始从视觉上和实际上创建连接。

<details>
<summary>Original English</summary>

And on the right, based on Obsidian, we can see like the sub graph reflected just based on in this index. And this is just like the first iteration, but as the the the the wiki grows, you can see connections made between entities and concepts. For example, concepts are things such as tool registry, context compaction, sandboxing, or entities are open code, closed code, MCP, right? So, as you can see, you can beautifully can start visually and practically create connections.

</details>

现在，下一个显而易见的问题是我们如何实际查询这个 Wiki？正如我所说，Agent 将把这个 index.yaml 文件作为输入，其中包含每个来源的摘要和元数据。但接下来会发生什么？下一步实际上是查看来源 Wiki 页面。来源 Wiki 页面就像是每个页面的执行摘要。它不仅仅是一个摘要，而是每个来源的更扩展的摘要。有时 Agent 只看这个，获取它需要的东西，然后返回。这非常节省 Token。如果它在来源 Wiki 页面中没有找到，我们还需要链接到 Wiki 衍生品，比如概念、实体、笔记、比较等等。只有当它在这个层级没有找到必要的信息时，它才需要并且实际读取整个原始来源。这基本上包含了整篇文章、整篇论文、整个视频或其他任何东西。通过纯引用和创建这个简单的层级结构，这使得一切都非常节省 Token。

<details>
<summary>Original English</summary>

Now, the next obvious question is how do we actually query this wiki? So, as I said, the agent will have as input this index.yaml file, which contains summaries and metadata about each source. But what happens next, right? The next step is actually to look into the source wiki page. Where the source wiki page is like an executive summary of each page. Which is basically not just a summary, but a more expanded summary of of each source. And sometimes the agent just looks into this, gets what it needs, and goes back. Which is very token efficient, right? And if it doesn't find within this uh source wiki page, we also need links into the wiki derivative, such as concepts, entities, notes, comparisons, and so and so forth. And only if it doesn't find the necessary information up to this point, it needs and it actually reads the whole raw source, right? Which basically contains the whole article, the whole paper, the the the whole video, or whatever. And this makes just through pure referencing and creating this simple hierarchy, this makes everything very token efficient.

</details>

现在，美妙之处在于这个 Wiki 实际上是活的。例如，每个问题都会在你的 Wiki 中留下痕迹。所以对于每个问题，LLM 可以创建一个新的概念文件、一个新的笔记文件、一个新的比较文件。每个问题都被记录在一个日志中。所以基本上，Wiki 不仅在你摄入新数据或进行深度研究轮次时演变，它实际上在你开始与它对话时也在演变。这就是美妙之处。这样，你可以看到你自己的真实反映，看到你还没有理解的东西，看到你过去的所有问题。另一个美妙之处是 Wiki 永远不会冻结。类似于研究实体文件。在任何时候，你都可以摄入你认为需要的新自定义链接到 Wiki 中，甚至可以运行新一轮深度研究。或者正如我之前所说，Wiki 仅仅基于你的问题而持续演变。

<details>
<summary>Original English</summary>

Now, the beautiful part is that this wiki is actually alive, right? For example, every question leaves a trace into your wiki. So for every question, the LLM can create a new concept file, a new notes [snorts] file, a new comparison file. And every question is is tracked into a log. So basically, the the the wiki doesn't evolve only when you ingest new data or do a deep research round, it actually evolves as you start talking with it, right? That's the beautiful part, actually. And like that, you can see a true reflection of of yourself, of what you haven't understood, of all your questions from the past. And the beautiful part is that the the wiki is never frozen, right? Similar to the research entity files. At any point, you can ingest a new custom link that you think that you need into the wiki, or even run a new deep research round. Or as I said previously, the wiki keeps evolving just purely based on your questions.

</details>

另一个需要理解的重要事情是，这个 Wiki 并不位于你整个第二大脑之上。例如，在我的特定用例中，我使用 **Tiago Forte** 提出的 **PARA 方法**，我所有的数据都按项目、领域、资源和归档进行结构化。我保存的所有笔记资源、来源（无论是文章还是其他）都直接导入到一个扁平的资源列表中。每当我需要什么时，我只是在项目和领域中引用它们。这样，Obsidian 只是一个不可变的快照，LLM 永远不会触碰它。这是我的数据。我真的不希望 LLM 触碰我手动编写的个人笔记。

<details>
<summary>Original English</summary>

And another important thing to understand is that this wiki doesn't sit on top your of your entire second brain, right? For example, in my particular use case, I use the PARA method coined by Tiago Forte where all my data is structured between project, areas, resources, and archive. Where all my notes resources that I save, sources that I save yet article or whatever are just piped directly to the resource a flat list. And whenever I need something, I just references them into projects and areas, right? And like this, Obsidian is just an immutable snapshot that a LLM never touches, right? So, this is my data. I don't really want the LLM to touch my personal notes that I manually write, right?

</details>

那么，我们如何实际使用这个 Wiki 呢？正如我所说，我们有一个大的 Obsidian 快照，那是我们的全局第二大脑。然后，每当我们开始一个新项目时，我们通过我解释过的深度研究算法来引用这个第二大脑，并将其范围缩小到我们自己的项目。所以，基本上，每当我们想开始做某件事时，我们运行这个深度研究循环，或者开始摄入一些特定的仓库、文章、笔记等等。我们通常通过一组插入到工具中的技能来做到这一点。一个项目基本上可以是任何事情，比如写一篇新文章、做一个新视频、做一套幻灯片。我在做这张幻灯片时就应用了这个技术。你甚至可以将它应用于更复杂的事情，比如写一本书、做一个课程，或者跟踪整个代码库。你也可以用它来做这些。所以，基本上，一个项目可以是任何你想把研究转化为工作的事情。项目就是工作，你的第二大脑就是研究。

<details>
<summary>Original English</summary>

So, then how can we actually put this wiki to use, right? So, as I said, we have the big Obsidian snapshot which is our global second brain. And then whenever we start to work on a new project, we reference this second brain through this deep research algorithm that I explained, and we scope it down to our own project, right? So, basically, whenever we want to start working on something, we run this deep research loop or we start ingesting some particular repositories, articles, notes, and so on and so forth. And we usually do that through a set of skills plugged into a harness. And a project can be basically anything such as writing a new article, doing a new video, doing a set of slides. I I applied this technique doing this slide. Or you can even apply it for something more complex such as writing a book, doing a course, or or keeping track of a whole code base, right? You can also you use it for that. So, basically, a project can be anything where you want, as I said initially, to transform research into work. The project is the work, and your second brain is the research.

</details>

### 演示：三个示例

现在，我想给你看几个演示。你需要做的是前往 **AI Research OS workshop** 仓库，在那里你可以找到运行我们在本次演示中展示的所有内容所需的技能。所有内容都打包成一个 Claude Code 插件，但你可以非常轻松地调整它，并将其安装到任何其他工具中。另外，在 README 中，你可以找到如何安装所有其他依赖项的详细信息，因为这个系统依赖于诸如 Obsidian、Readwise、NotebookLM 等工具。所以，你需要设置特定的 CLI 或认证问题。但我不想浪费你任何时间在设置问题上，我想直接进入示例。所以，我在这里准备了三个示例。

<details>
<summary>Original English</summary>

So, now I want to show you a few demos. So, what you need to do is go to the AI research OS workshop repository, and here you can find all the skills required to run what we presented into this presentation. And everything is packed as a cloud code plugin, but you can very easily tweak it and install it with any other harness. And also in the read me, you can find details on how to install all all the other dependencies, because the thing is that this system is dependent on tools such as Obsidian, Readwise notebook elements, and so on and so forth. So, you need to set up specific CLIs or authentication issues. But, I don't really want to waste any of your time with setup issues, and I want to go straight directly into the examples. So, I prepared here three examples.

</details>

第一个示例是关于我先前一篇关于 **Agentic AI Engineering** 的文章的研究，在这些文件中，我有我所有想谈论这个主题的内容的脑力倾泻。除此之外，我还添加了一些我 100% 确定要加入这个 Wiki 的参考资料。要实际在这些文件之上触发算法，我们需要打开一个 Claude Code 会话，然后调用研究技能，并将其指向这个文件。就这样。其他所有内容都直接内置在技能中。它会理解我的意图，即我想基于这些文件和主题创建一个关于 Agentic Harness Engineering 的 Wiki，并且它会在启动深度研究算法之前，知道需要先抓取这些信息，作为构建问题时的上下文。

<details>
<summary>Original English</summary>

The first one is a research on one of my previous articles on agentic AI engineering, and within these files, I have a brand dump of everything that I knew I wanted to talk on this subject. And on top of that, I also added a few references that I knew 100% that I want to add into this wiki. And what we need to do to actually trigger the the algorithm on top of these files is to open up a cloud session, and then just call the skill, the research skill, and point it it to this file. And that's it. Everything else is baked directly into the skill. It will understand my intent that I want to create a wiki on agentic harness engineering just looking at these files and looking at the topic, and it will know that before starting the deep research algorithm, it actually needs to scrape this information to to use it as context when it frames the questions for the deep research algorithm.

</details>

现在，我们需要等待一会儿，让 Agent 在其之上进行推理。我实际上会把它设置为自动模式来加快速度。我已经使用过数百次了，所以我知道它不会删除我电脑上的任何东西，也不会做任何奇怪的事情。好的，现在这是最重要的部分。它问我希望深度研究算法的深度是多少。我们有 **Light**、**Deep**、**Fast** 三个选项。这主要控制你希望每轮运行多少个问题，以及你希望运行多少轮。通常 Light 或 Fast 就足够了，因为记住这个过程会消耗大量 Token。所以，你只在真正想浏览大量笔记时才需要选择 Deep。对于这个用例，我会选择 Light 来加快速度。在这个用例中，它只做一轮，三个查询。对于 Fast 选项，它做两轮，每轮三个查询。所以，我会保持在这个范围内。这个过程大约需要 10 到 20 分钟来实际查看我的 Obsidian、Readwise、NotebookLM，并在此基础上运行这些查询。我实际上已经运行过了。

<details>
<summary>Original English</summary>

Now, we need to wait a bit for for the agent to reason on top of it. And I will actually just put it on auto mode to speed speed this up, right? I use this hundreds of times, so I know it won't delete anything from my computer or it won't do anything weird. Okay, so now this is the most important part, right? So, it asked me how deep I want the deep research algorithm to be. We have light, deep, fast. This mostly controls how many questions you want to run per one round and how many rounds you want to run. And usually light or fast is more than enough because remember this process consumes a lot of tokens. So, you kind of need to do the deep one only when you you really want to look over tons and tons of notes. And for this use case, I will just pick the light one to to to speed this up. And in this use case, it just does one round of three queries, right? And for the fast one, it does two rounds of three queries. So, I would just keep it keep it around that spectrum. And now the process will will take around 10 to 20 minutes to actually look around my Obsidian, to look around my Readwise, my Notebook LM, and run those queries on top of this. And I actually run this, right?

</details>

现在，让我们在 Obsidian 中打开我们之前根据提示创建的 Wiki，看看里面有什么。我们有三个大的对象：**raw files**（原始文件），基本上是我们找到的内容的原始副本；**index**（索引），包含所有指向 Wiki 的引用；在 Obsidian 中，我们还可以看到一个漂亮的子图，我们可以非常快速地了解发生了什么。这是纯粹基于这个文件创建的。然后，最有趣的部分是在 Wiki 内部。我们有 comparisons（比较）、concepts（概念）、entities（实体）和 sources（来源）。来源包含我们原始来源的执行摘要。这样，LLM 就不需要在每次读取时都去读原始来源，它只需要执行摘要，这些摘要在摄入期间只计算一次。例如，对于比较，它开箱即用地理解到需要基于来源进行诸如 Agentic RAG 与文件系统、压缩与递归语言模型等比较。最有趣的部分实际上是概念。所以，它自动从这堆资源中提取了我们需要理解的所有概念。例如，如果我们打开 Agent Loop 资源，我们可以自动查看并得到这个漂亮的摘要，包含图表、标签，并向我们解释这个主题所需的一切。我们可以对 Wiki 中的所有概念或所有实体进行同样的操作。

<details>
<summary>Original English</summary>

And now let's open this wiki that we created based on the prompt before in Obsidian and let's look what's inside the the wiki. So, we have three big objects, the raw files, which are basically a raw copy of what we found, the index, which contains all the references to towards the wiki, right? We can also in Obsidian have this beautiful a subgraph where we can very quickly understand what is going on. This is created purely based on this this file. And then the most interesting part is inside the wiki. Where we have comparisons, concepts, entities, and sources. The sources contain the executive summary of of our raw sources. So, the LLM doesn't really need to every time when it reads them, and it needs them to to read the raw sources, but it needs just the executive summaries, which are computed just one time during the ingestion. And for example, for the comparisons, it understood out of the box that it needs to do comparisons between like adjective rag versus file systems or compaction versus recursive language models or or or anything of interest based on on the sources. And the most interesting part is actually the concepts. So, it automatically extracted all the concepts that we need to understand from this pile of resources. For example, if we open the agent loop resources, we automatically can look and get this beautiful summary containing like graphs, tags, and explaining us everything that we need on this topic. And we can do the same on all the concepts from from from this wiki or all the entities from the wiki and so and so forth.

</details>

好的，现在让我们进入第二个示例。这是一个简单的示例，我想了解更多关于 Harness Engineering 以及 Harness 如何工作的信息。所以，在这个提示中，我只想摄入三个关于 **Open Code**、**Pi** 和 **Hermes** 的开源仓库。我根本不想做深度研究。我只想摄入这些仓库，并探索诸如通用架构、Agent 架构、子 Agent、记忆系统以及 Agent 权限流程等主题。让我们在这个提示之上运行研究。现在，研究将自动克隆所有这些仓库，并在我给出的主题上探索所有仓库，它会在每个仓库的个体层面创建关于它们如何工作、架构如何在仓库层面工作的笔记，然后我们可以创建更高级别的笔记，在 Wiki 衍生品中比较所有架构，或创建聚合架构，总结所有这些 Harness 的通用趋势，并直接从代码中探索和学习我们想知道的关于 Harness Engineering 的一切。

<details>
<summary>Original English</summary>

Okay, so now let's go to the second example. It It's a simple example where I want to learn more on harness engineering and how harnesses work. So, in in this prompt over here, I just want to ingest the three open source repositories on open code, Pi, and Hermes. And I don't want to do deep research at all, right? I just want to ingest those repositories and explore topics such as the general architecture, agents architecture, sub agents, memory system, and the agent permission flow. And let's run the research on top of this prompt. And now what the research will do will clone automatically all these repositories and will explore all the repositories on the topics that I gave here and it will create notes at the individual level of each repository on how they work, on how how the architecture works at the repository level and then we can create higher level notes, right? Within the wiki derivatives and compare all the architectures or create aggregate architectures on on like the general trends of all those harnesses and basically explore and learn everything that we want about harness engineering directly from the code.

</details>

同样，通常我只会使用自动模式，让它自己处理，但我已经运行过了。所以，这里是这些 GitHub 仓库的 Wiki，同样，我们有原始文件、索引和 Wiki。在这里，在仓库内部，我们可以看到所有三个仓库，例如，在 Open Core 仓库内部，我们可以看到解释我们在特定主题（如权限流程、记忆系统等）上所需一切的文件，我们可以在所有其他仓库中看到这一点。这里最有趣的部分是，我们实际上有所有这些的比较。所以，我们可以理解这些 Harness 在架构上的差异。我们还有从这些仓库中提取的所有概念，我们可以理解这些仓库的关键架构决策。所以，我们可以尽情使用它，如果你想要，例如，编写你自己的 Harness，这非常有用。

<details>
<summary>Original English</summary>

And again, usually I just do auto mode and let it do its own gist, but I already run this, right? So here is the wiki for these GitHub repositories and again, we have the raw files and we have the index and the wiki. And here probably within the repos we can see all the three repositories and for example, inside the open core repositories we can see empty files explaining everything that we need on particular topics such as the permission flow, the memory system and so on and so forth and we can see this in all the other repositories and the most interesting part here is actually that we have comparisons on all of these, right? So we can actually understand the differences within the architecture within these harnesses or we also have all the concepts extracted from these repositories and we can understand what are the key architectural decisions from these repositories. So we can go crazy with this and this is super useful if you want to, for example, write your own harness.

</details>

第三个示例实际上是现实中最简单的，它仅仅基于摄入一些简单的链接。同样，我将退出之前的运行，我想从头开始运行这个示例。在这里，我只想向你展示，你也可以在非常基础的设置下使用它，我只想摄入三个自定义的随机链接。和之前一样，我只需传递这个提示，它就会启动研究过程。我想强调的是，你可以运行示例二（关于 GitHub 仓库）和这个示例，而无需任何其他设置，比如设置 Obsidian、Readwise 或其他任何东西。你只需安装这个插件并运行这些示例，因为它除了 Git 和使用 curl 获取 URL 之外，不依赖任何其他服务。

<details>
<summary>Original English</summary>

And the third examples is the simplest one in in reality, which is just based on ingesting some some simple links, right? And again, I will just exit the the previous run and I want to run this example from scratch. And here, I just want to show you that you can use this also with a very basic setup where I just want to ingest three custom random links. And as before, I just pass this prompt and it will start the research process. And I want to highlight that you can run example two ending on the GitHub repositories and this example without any other setup like without setting up Obsidian, Readwise, or anything else. You can just install this plugin and run this examples because it here is not dependent on any other service than Git and using curl to get this this URLs.

</details>

同样，如果我们进入 Obsidian 并探索从这个示例三创建的 Wiki，我们可以看到索引，我们可以看到 Wiki 本身，包含所有来源，每个来源一个执行摘要，以及所有概念、提取的实体等等。想法是，当你开始在此基础上提问时，一切都会变得更有趣。现在，让我们假设我们想基于从 GitHub 仓库创建的 Wiki 问一个关于 Harness Engineering 的问题。我们需要做的就是再次调用研究技能，指向我们刚刚创建的 Wiki，然后提出我们的问题。假设我想了解更多关于沙箱的信息，更确切地说是远程沙箱如何工作，以及它是如何接入 Harness 的。这基本上可以是任何其他问题。现在，会发生的是，它会基本上查询这个 Wiki，给你一个答案，基于此，你还可以开始创建笔记、比较，或者它可能会提取和发现你关心的新实体。所以，基本上，它会开始更新 Wiki。

<details>
<summary>Original English</summary>

And again, here if we go into Obsidian and explore the wiki created out of this example three, we we can see the index, we can see the wiki itself with all the sources, right? One executive summary for for each source and all the concepts, extracted entities, and so on and so forth. And the idea is that as you start asking questions on top of this, everything starts to get more interesting. So now, let's assume that we want to ask for example a question on harness engineering based on the wiki created out of the GitHub repositories. So what we have to do is just again hit the research field pointed to the wiki that we just created, and then just ask our question. And let's assume that I want to learn more on sandboxing, more exactly how remote sandboxing works and how is plugged into the heart. This can be basically any any any other question. And now what it will happen, it will basically query this wiki, it will give you an answer, and based on this, you can also start creating notes, comparisons, or maybe it will extract and find new entities that you care about. So basically, it will start updating the wiki.

</details>

### 项目现状与未来

**Louis-François Bouchard**: 好的，那么这个项目将走向何方？它是什么？你应该做什么？首先，它在某些方面仍然粗糙。比如，它需要更多的连接器，正如你所看到的。我们需要添加 Google Drive、Notion、Slack 以及大量其他可能对你有用的连接器。但老实说，它们对我当前的工作流程或 Paul 来说并不是特别有用。所以我们还没有添加它们，因为这个项目的核心是对我们自己有用，并让你接手并添加你需要的任何东西。这个项目的另一个主要目标是教授记忆和上下文管理。所以所有这些额外的功能对这个目的来说并不是特别有用。还有其他一些弱点，比如很难知道哪些来源是过时的、弱的或强的，与我们构建的其他系统相比。所以我们知道我们可以改进这一点，但同样，这不是这里的优先事项。最后，它显然仍然是一个构建者工作流程。你通过 Claude Code 和 Codex 使用它，对我来说它就在终端里，我非常喜欢它。所以它不是一个最终打磨好的产品，没有漂亮的 UI 和 UX。老实说，这是设计使然。所以我们并不真正关心这个，因为我们的目标是教授 AI 工程。不是构建下一个最好的产品。

<details>
<summary>Original English</summary>

**[Louis-François Bouchard]**: All right. So now, where is this project going? What is it? What should you do? First, it's still rough at some points. Like it needs more connectors, as you saw. We need to add Google Drive, Notion, Slack, and tons of other connectors that could be useful to you. But to be honest, it's not really useful to me and my current workflow or to Paul. So we didn't add them yet, because the core of this project is to be useful for us and for you to take over and add whatever you need. And the other main goal of this project is to teach memory and context management. So all these extra features aren't really useful towards that purpose. There are other some weaknesses, like it's hard to know which sources are outdated or weak or strong compared to some other system that we built. So we know we can improve this, but again, it's not really the priority here. And lastly, it's still obviously a builder workflow. You use it through cloud code and Codex, and it's just to me in the terminal and I just really like it. So it's not a final polished product with a nice UI, nice UX. And honestly, that's by design. So we don't really care about this, because our goal is to teach AI engineering. It's not to build the next best product.

</details>

尽管如此，我们还有一些近期想要做的改进，从更强的代码检查到更好的记忆压缩，因为这是一个大问题，而且正确管理记忆通常非常复杂，而最先进的技术总是在进步。正如我所说，我们需要更好的来源溯源，以信任来源，能够正确地对它们进行排序，并在需要时正确地重用它们，并且作为用户能够快速了解这个来源是否相关。我们还有其他改进要做。但这些主要是为了优化和未来。关键是，我们实际上将所有这些都构建到了另一个产品中，你甚至可以自己构建。因为我们创建了一个名为 **Agent Engineering** 的课程，我们在其中构建了一个类似的深度研究系统，带有一个写作和研究 Agent，我们构建了一个具有相同目标的系统，以便能够学习最佳的 AI 工程实践。这是一个非常深入的课程，我估计需要大约 60 小时才能完成，最终项目就是我刚才描述的多 Agent 系统，你将为自己构建它。所以，如果这个演示和你看到的演示仓库让你感兴趣，请考虑查看 **Towards AI Academy** 以及我们那里的课程，包括 Agent Engineering 课程，以了解更多关于构建 Agent 及其周边的最佳实践。

<details>
<summary>Original English</summary>

Still, we have a few next improvements we want to do very shortly, from having a stronger linting to a better memory compaction, because that's a big issue and it's just very complicated in general to manage memory correctly, and the state of the art is always progressing there. We, as I said, need better source provenance to trust the sources and be able to rank them properly and reuse them properly if needed and be able to know access quickly as a user if this source is relevant or not. And we have other next improvements to do. But those are mostly for optimization and for the future. And the thing is that we actually build all of that into another product that you can even build yourself. Because we created a course called Agent Engineering where we build a similar deep research system with a writing and research agent where we build a system with the same goal to be able to learn best AI engineering practices. It's a very in-depth course where I assume it takes around 60 hours to complete with a final project being the multi-agent system I just described that you'll build for yourself. So if this presentation and the demo repo that you saw was interesting, please consider checking out the Towards AI Academy with our courses on there including the Agent Engineering course to learn more on the best practices when building around and with agents.

</details>