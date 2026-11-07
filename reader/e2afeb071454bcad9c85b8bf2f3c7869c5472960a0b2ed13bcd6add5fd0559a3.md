---
author: Latent Space
date: '2026-04-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=yyuVR-ML9X8
speaker: Latent Space
tags:
  - knowledge-graph
  - rag
  - ai-engineering
  - context-graph
  - agentic-systems
title: Neo4j CEO Emil Eifrem 谈图数据库、AI与知识转化
summary: Neo4j CEO Emil Eifrem 在访谈中深入探讨了图数据库在现代AI应用中的核心作用，特别是如何将数据转化为知识。他阐述了图数据库在高准确性、开发者生产力及可解释性方面的优势，并讨论了向量数据库的演变。Eifrem还分享了Neo4j在生命科学、金融等领域的AI驱动客户案例，并提出了代理（agent）数据源的“四象限”模型：操作型数据存储、云数据仓库、代理记忆和语境图。他强调了语境图在捕捉组织机构知识方面的价值，以及初创公司和大型企业在采用Neo4j时面临的不同挑战与实践。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Neo4j
  - Pfizer
  - Novo Nordisk
  - Salesforce
  - YouTube
  - Apple
  - X
  - Pinterest
  - Cloudera
products_models:
  - Cypher
  - GQL
  - Opus 4.5
  - GPT
  - Aura
media_books: []
status: evergreen
---
### 采访开场与 Neo4j 介绍

**主持人**: 好的，我们正在一个远程工作室，与 **Neo4j** 首席执行官 **Emil Eifrem** 进行访谈。欢迎您。

<details>
<summary>Original English</summary>

**Host**: Okay, we're in a remote studio with Emil Eifrem, uh CEO of Neo4j. Welcome.

</details>

**Emil Eifrem**: 很高兴来到这里。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Great to be here.

</details>

**主持人**: Emil，我等这次访谈等了一段时间了。您是第一届 **FOSS Fair** 的主要演讲者之一，去年我们还和您的团队一起举办了完整的**图 RAG** 专题活动。今年您又回到了 FOSS 的图 RAG 环节。今天您会如何介绍 **Neo4j**？

<details>
<summary>Original English</summary>

**Host**: Uh Emil, you I've been waiting for this for a while. Uh you were one of our top speakers at the first FOSS Fair, and then then we did the full graph rag track with the rest of your team last year. You're back this year at FOSS in Graph Rag. How do you introduce Neo4j today?

</details>

**Emil Eifrem**: 这取决于受众，对吧？我想我们最广为人知的是一个数据库，一个专门的**图数据库**。但如今它不仅仅是一个数据库，而是一个更广泛的平台。我通常会以“我们将数据转化为**知识**”来开场。所以它是一个实现这一目标的平台，当然这就引出了“知识”的含义，因为那是一个定义不清的术语。我通常会谈到它如何从噪声中提取信号，并以一种**知识密集型**的方式表达出来，而**图**就是其中之一。其核心当然是数据库，但如今我们的平台中还有许多其他功能。你们已经存在一段时间了。基本上每个人都在使用你们的产品，包括**伦敦交通局**。这应该很有趣。

<details>
<summary>Original English</summary>

**Emil Eifrem**: It depends on the audience, right? Like I think we're most well known as as a database, right? As a graph database uh specifically, right? But it's a broader platform than just a database these days, and I tend to start with the you know, we transform data into knowledge, right? So it's platform to do that, and then of course leads down the path of what do you mean with knowledge? Cuz that's kind of a ill-defined term, and I talk about how actually it takes about extracting the signal out of the noise and express that in a way that is a knowledge-dense way, and the graph is is one of them. And it at the core of it of course is the is the database, but then you know, we there's many other things in part of the platform as well now these days. Uh you you guys have been around for a bit. You're used by basically everyone, including Transport for London. Uh it should be fun.

</details>

**主持人**: 这确实非常符合图论的思维。您到了那里就会发现，地铁网络就是一个**图**。

<details>
<summary>Original English</summary>

**Host**: It's a very graph thing. Like you'll see when you get there. The tube network is a graph.

</details>

**Emil Eifrem**: 哦，是的，当然。嗯，你知道，这取决于你对**图**的执着程度，一切都是图，对吧？

<details>
<summary>Original English</summary>

**Emil Eifrem**: Oh oh yeah, of course. Yeah. Well, you know, depending how graph pills you are, everything's a graph, right?

</details>

### 图智能的优势：准确性、生产力与可解释性

**主持人**: 是的，没错。我也曾深陷其中。是的，大约十年前我学习编程时，参加了一个编码训练营，并在一个会议上参加了一个工作坊，这让我接触到了 **Cypher** 和 **Neo4j**。我认为很多人可能都是这样第一次接触到 Neo4j 的。我们想谈谈，自那以后发生了什么，以及**图智能**到底是什么？它指的是你们一直在构建的系统中的其余部分。

<details>
<summary>Original English</summary>

**Host**: This is true. And I've been down that that rabbit hole as well myself. Yeah, when I was I so when I learned to code uh 10 years ago, I did a did a coding boot camp, and there was a workshop at some conference I attended that introduced me to Cypher and Neo4j. And I think that that's how a lot of people maybe first come across a Neo4j. We wanted to talk about you know, what what's happened since, and what what is graph intelligence just generally, right? Like what what is the um I guess the the the rest of the system that you've been building.

</details>

**Emil Eifrem**: 好的，我们先谈谈这背后的“为什么”，对吧？所以，如果你从 AI 工程师的角度来看，你之前提到了**图 RAG** 这个词，这似乎是描述检索的一种流行方式，即在 R 路径中包含一个**知识图谱**。有很多理由这样做。我从用户那里听到最响亮的声音是**更高的准确性**，因为你拥有非常丰富的数据表示。然后，令许多人惊讶的是，它还提高了**开发者生产力**。这里有一个隐含的假设，那就是你拥有图，我们可以讨论这个问题。但当你拥有图时，如果将其与**向量空间**进行比较，向量空间是非常不透明的。如果你搜索并找到前 K 个文档，你不知道为什么。它就像某个余弦欧几里得空间中的 0.7 值。相比之下，在图中，它是明确的，你甚至可以直观地检查和查看它。我有一个苹果和一个橘子，它们因为都是水果而相关。然而，一个苹果和一个网球可能在欧几里得空间中是 0.7，因为它们都是圆的，或者因为它们都是绿色的，你不知道。所以这是第二个原因。我们听到非常响亮的第三个原因是**可解释性**。人们喜欢这样一个事实：他们可以实际审计为什么选择了这前 K 个文档，而不是再次面对不透明的向量空间。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, so let's first talk about kind of the why behind it, right? And so you know, if you come in at it from like an AI engineer's perspective, right? You mentioned the word graph rag before, and that tends to be a popular way of describing retrieval that in the R path you include a knowledge graph, right? You know? And there's plenty of reasons to do that, right? The ones that I hear most loudly from from users is higher accuracy because you have a very rich representation of your data. And then actually surprisingly to a lot of people, but improved developer productivity. And there's a built-in assumption there, which is you have the graph, and we can talk about that, but when you have the graph, and if you compare that to vector space, it's very opaque vector space. If you search and find the top K documents, you don't know why. It's like 0.7 in some cosine Euclidean space kind of thing, right? Compared to in the graph, it's explicit, and you can even visually inspect it and look at it. And I have an apple and an orange, and they're related because of their fruitness, right? Whereas it like an apple and I don't know, a tennis ball might be 0.7 in Euclidean space, right? Because they're both round, or is because they're green, you don't know, right? So that's kind of the second thing. And then the third reason that we hear very loudly is around explainability. People love the fact that they can actually audit why I chose these top K documents compared to just again opaque vector space.

</details>

**主持人**: 嗯，我没听到任何关于查询速度的说法，我想那也是其中一部分。但我总是这样思考图：好吧，你想这么做的原因是因为你可以遍历**图**，而且这可能比做一堆查询和连接更好。这是一种老派的思维方式，还是只是你刚才说的另一种说法？

<details>
<summary>Original English</summary>

**Host**: Yeah. Um I don't hear anything about query speed, which I guess it's it's it's part of it, but always think about graphs in terms of like, well, okay, the reason you want to do this is because you can you can walk a graph, you can traverse a graph, and that's probably better than doing a bunch of queries and joints. Is that a old school way of thinking about it, or is it is that [clears throat] actually just another way of saying the same thing that you just said?

</details>

**Emil Eifrem**: 是的，我认为这可能包含在**准确性**中，对吧？因为你通常可以涵盖很多领域。通过快速执行，你可以遍历并接触到大量文档或节点。我想这是一个有趣的观察。我想我们听到的比较少，甚至我听到的也比较少。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, I think it's probably built into the accuracy thing, right? Because frequently you can kind of cover a lot of ground. Like you can can traverse and touch a lot of documents or nodes by virtue of doing it really fast, right? I guess it's an interesting observation. I guess we hear less of it, and even I hear less of

</details>

**主持人**: 说是速度。是的。

<details>
<summary>Original English</summary>

**Host**: said it's speed. Yeah.

</details>

**Emil Eifrem**: 是的，没错。从 AI 工程师的角度来思考，对吧？AI 相关的用例，我想我们也习惯了 LLM 消耗如此多的延迟，所以它可能很少因为这个原因而出现，但它却是我们能够获得更高准确性的根本原因，我想。所以我认为这可能就是它相关的原因。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, exactly, right? Like in in kind of thinking about it from an AI engineer perspective, right? AI-ish type use cases, I guess we're also used to kind of the LL eating up so much latency anyway that it's maybe kind of rarely pops up for that reason, but it's like a fundamental reason why we can get the higher accuracy, I think. So I think that's probably why it relates.

</details>

**主持人**: 是的，是的。我的意思是，如果你有速度，你就可以投入更多时间来获得更高的准确性。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah. I mean, if you if you have speed, you can just throw more time at it to get more accuracy.

</details>

**Emil Eifrem**: 完全正确。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Exactly.

</details>

### 向量数据库的演变与“好用即足够”原则

**主持人**: 好的，酷。然后我想另一个经常出现的问题是，您认为**向量数据库**发生了什么？作为一个中立的数据库首席执行官，为什么它没有成为一个更持久或独立的类别？

<details>
<summary>Original English</summary>

**Host**: Yeah, okay, cool. And then I think the the other question that comes up a lot is what happened to vector databases in your mind? You know, as a as a neutral sort of database CEO, how come that has been a less I guess how should I call it? Persistent or independent category? Yeah, durable maybe.

</details>

**主持人**: 也许是更持久。现在每个人都有**向量索引**了，但我认为可以说**向量数据库**作为一个独立类别已经结束了。

<details>
<summary>Original English</summary>

**Host**: Durable maybe. Everyone has vector indexes now, but like I would I think it's fair to say vector databases are as a standalone category are over.

</details>

**Emil Eifrem**: 是的，我不知道。也许这有点夸大其词。几年前我就明确表示，我不相信这是一个持久的数据库类别。至少不是作为一个数据库类别。它可能更像搜索，对吧？这是我几年前的说法。我想我感到惊讶的是，仍然有一些长尾效应，我们仍然看到很多人在早期尝试使用**向量数据库**。然后在像超高端领域，一些向量数据库仍然比其他数据库的**向量搜索**功能更好。但你称我为中立的一方。我在这里并不中立，因为 Neo4j 也有向量搜索功能，而且它没那么好。是的，所以你的意思是向量数据库……完全正确。但就像每个季度、每年，界限都在提高，对吧？所以它们的生存空间越来越小。你知道，我当然很高兴地观看了几周前你与 **Turbo Puffer** 的 **Simon** 的对话。他将其描述为一个搜索平台，我想，或者搜索工具。我认为这正是那些曾经是向量数据库的人现在所走的道路。而且我认为，当其他人将它作为一项功能添加进来时，这种“够用就好”的原则在大多数情况下是足够的。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, I don't know. Maybe that's overstating it. I've been So several years ago I was very kind of on the record saying that I don't believe this is a durable database category, right? At least not as a database category. Maybe it feels much more like search, right? That is kind of my my statement a couple of of years ago. I guess I've been surprised that there's still I think some kind of long tail thing going on where we still see a lot of experimentation where people try with vector databases early on, right? And then at the like a super high end, then like some of the vector databases are still better than the vector search features of other databases. But like you call me a neutral party. I'm not neutral here like cuz we also have vector search as part of Neo4j, and it's not as good Yeah, so what you're saying is that the vector databases Exactly, right? But like every quarter, every year kind of the line moves up, right? And so there's less and less oxygen for them, you know, I obviously watched with with pleasure, you know, your your conversation with Simon a couple of weeks ago as we're recording this from from Turbo Puffer, and he described it as a search platform, I think, or search Yeah. search tool or something like this, right? I think that's generally where people are going right now who used to be vector vector databases. And I think just the oxygen, you know, between everyone else adding it as a feature, like the good enough ends up being good enough for most situations.

</details>

**主持人**: 是的，明白了。我想这也是真的。而且我认为每个人都应该披露或声明，在什么样的数据规模、复杂性或基数下，您是真正出类拔萃的？您的解决方案之所以遥遥领先于其他所有方案，是因为它是以特定方式架构的。在小规模情况下，谁会在乎呢？随便扔进去就行。但到了大规模，它就开始变得真正重要了。

<details>
<summary>Original English</summary>

**Host**: Yeah, got it. Um I I think I think that's true, too. And I think something that everyone should disclose or disclaim is under what size and what complexity of data or cardinality or whatever, right? Are you like truly excelling, right? Where where your solution is leaps and bounds above everyone else's because you were architected for like in in a in a specific way. At small size, who cares? Just throw it in whatever. But like at scale, it really starts to [clears throat] matter.

</details>

**Emil Eifrem**: 是的，我同意。对我们来说，它的作用方式是：你有一个 **RAG 语料库**，对吧？你有一个管道来使其处于可以查询并最终传输到 **LLM** 的状态。然后我们根据这个摄取管道和嵌入，在我们的向量搜索索引中填充图。但在查询时，我们通常倾向于用它来找到图中的起始点，然后从那里遍历。所以，在经典的客户支持用例中，比如 **Swyx** 刚买了一台新笔记本电脑，权限不工作，于是他去了 **Apple** 的支持网站，输入了一些东西。然后，从自然语言中，通常有一个**向量搜索**，通常还结合了 **BM25** 类型的搜索。这最终会找到大约 100 个文档。然后你从那里遍历以获取完整的上下文。然后你会说，好吧，这不仅仅是这些文档是否被向量搜索找到，还发现它们是由这位排名很高的作者撰写的，可能是通过**PageRank**，或者只是非常简单的星级或某种信号。然后你得到前 K 个结果。所以，这不是图或向量搜索的问题，而是向量搜索与遍历图相结合。这是我们看到的典型模式。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, I agree. And like the way that it fits in for us is So you have call it your rag corpus, right? And you have some kind of pipeline to get that in the state where you can query it and get it kind of out and ultimately to the LLM, right? And then we populate the graph based on that ingestion pipeline and embeddings in our, you know, vector search index, right? But and then at query time we typically tend to use it to find the starting points in in the graph, right? And then we traverse from there. So in the classic kind of customer support type use case, Swyx, you know, just got a new laptop, and the permissions don't work, and so you go to on onto the Apple, you know, support site, and you type in something, then you know, from that natural language, right? There's typically a vector search, typically combined with some kind of BM25 type search as well, right? And that ends up finding some documents, right? Call it 100 documents or something like that. And then you traverse from there to get the full context. And then you end up saying, well, okay, it's not just whether these documents were found by the vector search, but also turns out that they were written by this author who's highly ranked, maybe through a page rank, or maybe just very simple like stars or or some kind of signal like that. And and you get to the top K, you know, something like this, right? And so it's not like graph or vector search, it's like vector search in combination with traversing the graph. That's the typical yeah, kind of pattern that we see.

</details>

**主持人**: 是的，而且这里的工程工作真的很难，因为有很多权衡。如果你有无限的预算，你可以做任何事情，但你没有。

<details>
<summary>Original English</summary>

**Host**: Yeah, and and like the engineering's actually like really hard here because there's so it's just trade-off trade-off trade-off. Like you can do anything if you have unlimited budget, but you don't, and so

</details>

**Emil Eifrem**: 我同意。但我确实认为有一个普遍的趋势。总的来说，抛开 **Neo4j** 不谈，就是试图从摄取管道中提取更多信号，以使下游查询更容易。是的，你可以称之为预处理，但就是提取更多信号。当你在**向量搜索**或其他任何东西中添加内容时，**向量数据库**倾向于将其称为**元数据**，但它实际上是**结构化数据**。我们是这个更广泛趋势的一部分，你可以说**图**是一种非常丰富的结构化数据类型。我认为这通常是正确的思考方式。你可以在上游做的工作越多，在运行时或查询时就越容易。既然你提到了 **Simon** 的那一集，那真是一个有趣的对话。他是一个非常有魅力的人。我很好奇你有没有任何技术上的异议，有没有什么听起来让你觉得奇怪的地方？我可以问你关于他那种以 **Blob S3** 为中心的世界观，很多数据库首席执行官，包括 **Neon**，都在大力押注。大概你对此没有强烈的意见，但我只是想让你随便回应。

<details>
<summary>Original English</summary>

**Emil Eifrem**: I agree. I do I do think there's a general trend, though. Like broadly, setting aside Neo4j, like trying to extract more signal out of the ingestion pipeline to make the kind of down down stream querying. Yeah, well, you could call it pre-process, but just extract more signal. Like in the when you add things into your like vector search or whatever it might be, right? And the vector databases you tend to call that kind of metadata, right? But it's really structured data, right? And we're part of that broader trend, and you could say that graph is a like a very rich type of structured data. And I think that generally tends to be the right way to think about it. Like the more work you can do kind of upstream, the easier it becomes at at runtime or at query time. Since you mentioned the Simon episode, uh that was a really fun one. He's a very charismatic guy. I'm curious if you have any like technical like, you know, any pushbacks, anything sound a weird to you. I can ask you about like the sort of blob S3-centric view of the world that he has, which a lot of database CEOs, including Neon, uh you know, betting heavily on. Presumably you don't have a strong opinion there, but just I I just want to let you respond whatever you want.

</details>

**Emil Eifrem**: 不，我认为总的来说，那只是一种非常强有力的阐述。现在，这是几年前我听到的，因为那大概是三周前左右的事情。

<details>
<summary>Original English</summary>

**Emil Eifrem**: No, I think broadly it's it was just really strong articulation. Now, this was like years ago that I listened to it because it was like 3 weeks ago or something like this.

</details>

**主持人**: 是的，是的，是的。感觉就像很久以前我跟他谈过一样。发布出来了。完美地记住了，是的。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, yeah. It's it feels like forever since I talked to him. of put it out. Perfectly remember, yeah.

</details>

**Emil Eifrem**: 不，我不能完美地记住它，但总的来说，那是一个非常强有力的阐述，听起来非常务实和精明的权衡和选择，对吧？当然，作为一个数据库极客，我很喜欢围绕**比较和交换（compare and swap）**的对话。甚至像你我私下里讨论的 Raft 与两阶段提交等等。我只是喜欢所有这些，因为我记得对我们来说，我以前在很久以前在 CPU 层面做过比较和交换，然后当它通过 **JVM** 暴露出来时，对我们来说是一个巨大的突破。它让我们能够做**无锁并发**，也就是数据库中的**乐观并发**或**乐观锁**。有趣的是，看到他 15 年后也能做同样的事情，但只是基于 **S3**。这似乎是他所针对的用例的非常好的权衡，当然，这与我们所针对的用例非常不同。是的，酷。我们来谈谈一些用例，对吧？我想去年令人惊讶的事情之一是 **Pfizer** 的演讲，那很酷。你有很多客户。

<details>
<summary>Original English</summary>

**Emil Eifrem**: No, I can't perfectly remember it, but generally it was like a very strong articulation which sounded like very just pragmatic and savvy trade-off and and choices, right? And like of course as a database geek I enjoyed the conversation around compare and swap, right? And even as you and I were DMing around it's like raft versus two-phase commit and stuff like that. I just kind of love all all that because I just remember for for us, right? I used to do compare and swap like on a CPU level way back in the days, right? And then it was a big unlock for us when it because we're on the JVM when it got exposed through the JVM. It allowed us to do kind of you know you know, basically lock-free concurrency. So, optimistic concurrency or optimistic locking in the database, right? And it's interesting to see like how he 15 years later can do the same thing, but you have just based on based on S3. Seems like a really good set of trade-offs for like the use cases that that he's targeting which is of course very like very different from what what we're targeting. Yeah, cool. Let's talk about some of the use cases, right? Like I think that one of the surprising things last year was I think the Pfizer talk which is kind of cool and and I just you know, you have lost you have so many customers here.

</details>

### AI 驱动的客户案例：生命科学与金融

**主持人**: 那么，有哪些**AI 驱动的客户**是你们的，而人们可能会惊讶于他们正在使用图数据库或 **Neo4j**？

<details>
<summary>Original English</summary>

**Host**: Just who are the sort of AI forward customers that you that people might be surprised are using graph databases or using Neo4j for something

</details>

**Emil Eifrem**: 是的。有很多事情可以谈。这Certainly是我第一次演讲以来发生的最大变化之一，那是两年前，大概是 2024 年 6 月，或者 5 月。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah. So, lots of things to talk about there. Like that's one of the biggest things that have changed certainly since the first talk that I gave which is now 2 years ago. It was uh June of 2024 I think or maybe maybe May.

</details>

**主持人**: 您在着陆页上，是的，在这里。

<details>
<summary>Original English</summary>

**Host**: you on the landing Yeah, the landing page uh yeah, down here.

</details>

**Emil Eifrem**: 是的，是的，是的。当然，其中一个巨大的变化是人们现在已经将其投入生产。在那时，这还处于早期阶段。你提到了 **Pfizer**。我们看到生命科学领域有很多采用。这广泛地属于**科学智能**，这些大型生命科学公司的研究人员每天都在使用。这不仅包括内部同行研究，还包括专利、外部发表的学术论文等。**Novo Nordisk** 是我们在这里的一个公开案例研究，拥有超过 6000 万份文档，数十亿个节点和关系。使用了大量精密的 **NER**，即**命名实体识别**和**实体解析**，顺便说一句，这在当前的 AI 工程领域是一个被低估的领域，我不知道为什么会这样，但这对他们理解所有这些数据至关重要。如果你考虑像生命科学公司，拥有极多的博士，这 100% 是他们提高产品生产力和产出的关键路径。所以，这是一个例子。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, yeah, yeah, yeah. So, and a huge one of this of course is that people now have put it into production. It was such early days back back back in those those those times. You You mentioned Pfizer. We see a lot of adoption inside of life sciences, right? And so this is broadly kind of scientific intelligence that researchers at these big life science companies use on a daily basis. This is access to not just internal peer research, but patents, like external published, you know, academic papers, you know, that those kind of things, right? Novo Nordisk is one of the like public case studies we have here over 60 million documents, you know, billions of nodes and and relationships. Use lots of kind of savvy NER and NER, so that's named entity recognition and entity resolution which is such an under-discussed area right now in in AI engineering by the way which I don't understand what why it is, but but that's like key for them to make sense of all the all that data, right? And if you think about like a life science company, right? Like extremely PhD heavy, right? And this is like 100% on the critical path for them in order to like improve their product productivity and and and output. So, that that's an example.

</details>

**Emil Eifrem**: 仅在 2026 年，我们在银行业看到了大量新增的用户。这里有一个例子，在 2026 年至今，我们 30% 的 AI 对话都是与全球银行进行的。这非常令人惊叹。是的。一个例子，我不知道它是否在我们的网站上，是一家大型抵押贷款公司。他们正在做的是，他们有很多我们称之为银行家的人。他们称之为“代理人”，这让人很困惑，但他们雇佣的是真人。

<details>
<summary>Original English</summary>

**Emil Eifrem**: We have lots and lots of recent uptake just in 2026 in banking. An example here um is like so 30% of our AI conversations these days like in 2026 so far has been with like global banks. Which is pretty pretty amazing. Yeah. One example which I don't know if we have on our website is like a massive mortgage lender company. Um and um what they're doing is they have a ton of let's call it bankers. They call them agents which makes it very confusing, but human beings that they hire.

</details>

**主持人**: 是的，是的，正是人类代理人，对吧？

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, exactly human agents, right?

</details>

**Emil Eifrem**: 他们是二十多岁或二十出头的年龄段。他们的正常任期非常短，不到一年。所以，这场游戏很大一部分是为了让他们快速上手。当他们与客户进行沟通时，如何才能将底部的四分之一的业绩提升上来呢？所以他们建立了一个庞大的系统，查看了所有先前的最佳案例路径以及过去实际转化的案例，并帮助他们将所有这些整合起来。他们实际上公开谈论了这一点，但没有提到 Neo4j，但它将转化率提高了 20%。所以这一切都发生在去年。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And and they are kind of mid-20s, low-20s kind of demographic age-wise, right? And like their normal tenure is super low. It's like less than a year. And so a huge part of that game is to ramp them quickly. And as they do outreach to their customers, how can you get kind of the bottom quartile and move that up up up the stack, right? And so they built this huge system that looked at all prior like kind of the the best case path and what actually converted in the past and helped them pull that all together. And they actually talked about it publicly and didn't mention Neo4j, but that it increased conversion rates by by 20%. And so that all happened uh you know, last year.

</details>

**主持人**: 如果你把它换算成钱，是多少钱？

<details>
<summary>Original English</summary>

**Host**: money is that if you convert it to money?

</details>

**Emil Eifrem**: 是的，我不知道。比他们付给我们的多得多。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, I don't I don't know. Way more than they pay us.

</details>

**主持人**: （笑声和喘息声）

<details>
<summary>Original English</summary>

**Host**: [laughter and gasps]

</details>

**Emil Eifrem**: 嗯，但真正酷的是，他们今年开始将它自动化。所以，在此之前，它只是将草稿提供给银行家，以便他们可以发送短信或电子邮件。现在他们当然正在将人类从循环中移除，并以自动化方式发送。看到人们如此迅速地将这些东西投入生产，并以面向客户的方式进行，这非常酷。当我们去年夏天审查我们的客户组合时，几乎没有人有面向客户的产品投入生产，但在过去大约三个月里，这种情况发生了非常戏剧性的转变。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Um and but the really cool thing is and now what they're starting to do this year is they're starting to now kind of automate that, right? So, prior to that it was just kind of serving up the draft to the banker so that they can send the send the text message or the email or something like this. And now of course they're kind of removing the human in the loop and they just send it out in an automated fashion, right? And that's very cool to see how quickly people are starting to put these things in production in customer-facing ways. When we reviewed our kind of customer portfolio last summer, almost no one had customer-facing things in production, but that has shifted very very dramatically in the last call it 3 months.

</details>

### AI 发展的时间点与自动化趋势

**主持人**: 当你说三个月时，是这样吗？我一直在研究这个理论：2025 年 12 月发生了一些事情，很多曲线都受到了影响等等。你也看到了吗？

<details>
<summary>Original English</summary>

**Host**: When you say 3 months, is it So, there's there's this thesis that I've been investigating, right? Something happened in December 2025 where uh a lot of curves infected and all that. Are you seeing that, too?

</details>

**Emil Eifrem**: 我们也看到了。

<details>
<summary>Original English</summary>

**Emil Eifrem**: We are seeing that.

</details>

**主持人**: 我不敢相信这与 **Opus 4.5** 有关。那似乎是一个完全不同的事情。但 **GPT** 也是如此，但所有数据库的图表都显示了这一点。所以，我显然看到了很多行业范围的统计数据和数字。我的意思是，我是大约 30 家公司的天使投资人，通过认知和人工智能，我看到了很多东西。每个计算图表都是这样的。每个数据库图表都是这样的。显然，每个编码代理图表也是这样的。

<details>
<summary>Original English</summary>

**Host**: I cannot believe that it's related to Opus 4.5. That that seems like a like a separate separate thing. But GPT as well, but uh no no, every chart in both databases So, obviously I see a lot of these sort of industry-wide stats and numbers. I mean, I'm an angel investor in like 30 companies um and you know, obviously through through cognition and and AI AI I see a bunch of stuff. Every compute chart is like this. Every database chart is like this. And obviously every coding agent chart is like this.

</details>

**主持人**: 只是，是的，有些事情正在发生。

<details>
<summary>Original English</summary>

**Host**: Only like Yeah, something's going on.

</details>

**Emil Eifrem**: 有些事情正在发生，对吧？对我们来说，我不确定这是否纯粹是模型质量的问题，但我们确实也看到了。一个巨大的转变就是我刚才提到的，以前只是“帮我起草消息”，现在变成了“帮我发送消息”。因此，这种面向客户的完全自动化现在已经达到了一种信任的临界点。他们正在这样做。另一个例子是，这是关于公司在高层面上正在做什么，但如果你深入到微观层面，在单个开发者、单个应用程序中，这正是我两年前**图 RAG** 演讲的范围。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Something is going on, right? And to us like I'm not sure if it's like purely the model quality, but yeah, we're seeing it, too. And and a big shift is what I just mentioned, right? Which is you know, it used to be just draft me the messages. Now it is kind of send me the messages, right? And so that complete automation in a customer-facing way that's now got into some kind of tipping point around trust, right? Where they where they're doing that. Another example of this is if So, that's kind of high-level kind of what the companies are doing, but if you go down to the micro level and like in single developer, a single application which was kind of the scope of my graph rag talk 2 years ago, right? Like that was kind of the um the the boundary.

</details>

**Emil Eifrem**: 而如果你考虑一下，人们现在如何编写**代理式图应用程序**？好的，所以**图**是一种工具，**向量数据库**可能是一种工具，就是那种东西，对吧？然后你可能会有一些英文输入，一些自然语言输入，对吧？以前的建议是，选择你可能会遇到的最热门的问题类型。再说一次，如果这是一个像客户支持门户网站这样的最明显的例子，我们可以选择很多其他例子，对吧？所以，如果 **Swyx** 去 **Apple** 问一些问题，选择那些最热门的问题。将其表示为 **Cypher** 中的函数或工具。然后使用文本通用文本到 Cypher 作为默认的备用方案，如果它不工作的话。然后客户最终做的是，他们会说，好吧，我要这样做。然后他们坐下来查看了所有回退到文本到 Cypher 的日志。那些不工作的东西，他们会提取到一个单独的函数或工具调用中。所以，这就是人们做事的一般方式，对吧？大约一年前，你在其他数据库和代理式应用程序中也看到了类似的情况。然后在过去的三到六个月中，发生的变化是，以前是先使用专业函数，然后回退到通用函数。而现在则颠倒了过来。所以，现在是，好吧，先从通用的文本到 Cypher 开始，对吧？然后当它失败时，你将边缘情况提取到专业函数中，对吧？

<details>
<summary>Original English</summary>

**Emil Eifrem**: And if you think about that, right? Like how do people actually write agentic kind of graph applications right now? Okay, so so the graph is a tool, kind of vector database might be a tool, you know, that kind of thing, right? And then you have some kind of English coming in, some natural language coming in maybe, right? And then it used to be that what the recommendation was take the most the kind of the hot spot of the type of questions you might get. Again, if it's a like the customer support portal is just this most obvious example, right? We can choose plenty others, right? So, if it's Swix, then okay, Swix goes to Apple and he asks some questions. Take kind of the hot spot of those questions. Express that as a function or tool, right? In Cypher. And then use text generic text to Cypher Cypher as the default kind of backstop if that doesn't work. And then what customers ended up doing was like, okay, I'm going to do this. And then they sat down and they looked at the log of everything that kind of had a fall back to to text to Cypher. The stuff that didn't work, they would extract into a separate function or tool call. So, that is kind of the the general way that people were doing things, right? And you saw similar with other databases and and agentic applications about a year ago. And then in the last 3 to 6 months, what has changed is that it used to be lead with the specialized functions, fall back to the generic. And now that has flipped. So, now it's like, okay, just start with generic text to Cypher, right? And then when that fails, you extract the edge cases into the specialized functions, right?

</details>

**Emil Eifrem**: 我认为整个技术栈中发生了一些事情，导致它在大约三到六个月前发生了转变。

<details>
<summary>Original English</summary>

**Emil Eifrem**: I think it's just across the stack there's a number of things that have happened like that that I think caused it to to flip call it you know, 3 to 6 months ago.

</details>

**主持人**: 因为我现在也可以单次完成大多数事情。

<details>
<summary>Original English</summary>

**Host**: Because it I can single shot most things now as well.

</details>

**Emil Eifrem**: 完全正确。你知道，这引发了我关于 **LLM 编码**的常见话题。你知道，我为什么参加 **Cypher** 的工作坊？然后我没有真正使用它。除了那次之外，主要是因为它是一种 **DSL**，我想，我为什么要学习一种 DSL 呢？但现在 DSLs，你知道，一个很好的理由是它们针对其用例进行了优化，而且它们非常简洁。它们可以正确地做很多事情，但缺点是你必须学习它们。现在你不需要学习它们了。你只需要……

<details>
<summary>Original English</summary>

**Emil Eifrem**: Exactly. Yeah. You know, this this triggers a common talk track that I have as well around LM coding. You know how um one of the reasons I did the workshop with Cypher. And then I didn't I didn't really use it. Other than that, mostly because it's a DSL and I'm like, why do I want to learn a DSL? But now DSLs, you know, a good reason is they are optimized for their use case and they are so concise. They can do so many things correctly, but then the the downside is you have to learn them. Now you don't have to learn them. You can just

</details>

**主持人**: （笑）

<details>
<summary>Original English</summary>

**Host**: [laughter]

</details>

**Emil Eifrem**: 你们的恰好是一种拥有大量训练数据的 **DSL**。所以，这就像是，你们达到了一个临界点，存在的时间足够长。你们经历了起起落落，现在，人们可以自由地使用你们，如果需要的话，显然也可以进行优化，但除此之外，你们基本上可以一次性完成这些事情，这非常棒。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And and yours happens to be a DSL that has a ton of training data. So, it's like you you like made the cut-off where you've been around long enough. You survived through ups and downs and now, you know, people actually can freely use you and obviously optimize if they if they need to, but other than other than that, you know, you can mostly one shot these things which is super nice.

</details>

**Emil Eifrem**: 我同意。还有几个想法。一个是我们有幸成为一个完整的、实际的、**ISO 认证**的标准，对吧？所以它最初在 2015 年是作为 **Open Cypher** 开始的，经过多次反复和各种标准战争（或者甚至不是战争，而是标准官僚主义）之后，最终成为了 **GQL**，它是 **SQL** 的第一个姊妹语言。我确实认为这有助于作为 LLM 训练数据的一种信号。所以这是一点。话虽如此，在内部，我们有许多内部的文本到 Cypher 的东西，我们在整个产品组合中使用，就像一个老式的 Co-pilot 类型的东西。如果你进入 Neo4j 的浏览器，在那里你可以输入你的 Cypher 查询，然后你当然可以使用 Co-pilot 来翻译它，你可以在这些之上运行代理，所以我们需要它作为我们平台中的一个基本功能。我们实际上仍然在微调那个。所以每当我们默认使用 **Gemini** 时，我们仍然会做一些微调，甚至一些后处理。当你说微调时，你是说微调一个自定义模型来生成你的文本到 Cypher，还是你正在微调游乐场中的输出？

<details>
<summary>Original English</summary>

**Emil Eifrem**: I I agree. A couple of more thoughts. One is we had the benefit of becoming a complete actual ISO blessed standard, right? So, it started out as open Cypher actually back in 2015 which after so many back and forths and all kinds of, you know, standards wars and whatever, right? Or not even wars, but standards bureaucracy ended up becoming GQL, right? Which is the first sibling language to to SQL. And I actually think that helps as a signal for the kind of LLM training data, right? So that's one thing. Now, having said that, internally, so we have a bunch of in kind of internal text to Cypher things that we use across the product portfolio, like a old school kind of co-pilot type thing. If you go into Neo4j into our browser, where you can type your Cypher queries, right? Then of course you can use a co-pilot to translate that and you can run agents on top of those and then so we we need that as a primitive in our in our platform. We actually still fine-tune that that one. And so whenever we we default to Gemini and we still do like some fine-tuning and even some post-processing. When you say fine-tuning, are you you're saying fine-tuning a custom model to produce, you know, your your text to to Cypher or you're fine-tuning the playground in the output?

</details>

**Emil Eifrem**: 不，不，不。我们正在微调一个实际的模型。

<details>
<summary>Original English</summary>

**Emil Eifrem**: No, no, no. We're fine-tuning an actual model.

</details>

**主持人**: 好的。这不清楚，因为你不能真正微调 **Gemini** 模型，对吧？你不能微调分析模型。

<details>
<summary>Original English</summary>

**Host**: Okay. It wasn't clear because you can't really I don't think you can fine-tune a Gemini model, right? You can't fine-tune an analytic model.

</details>

**Emil Eifrem**: 这就是我们内部可能使用其中一个派生模型的地方。我实际上不知道是哪一个，但我们甚至有一个后处理步骤，我们有时会做一些像正则表达式类型的东西，比如转换一些箭头。你知道在 **Cypher** 中你可以描述不同方向的关系以及类似的东西，对吧？所以它实际上比你想象的要混乱一些，并不是说开箱即用的模型现在在所有情况下都足够好。我当然希望随着时间的推移，它能对 99% 的情况都足够好，但这还没有完全实现。我的意思是，我认为，这就是专家发挥作用的地方，拥有一个良好的生态系统也会发挥作用，而且，至少目前，这仍将是人类专家的领域。

<details>
<summary>Original English</summary>

**Emil Eifrem**: this is where like we probably use some of the one of the derived ones internally. I actually don't know no no no no which one, but we then even have a post-processing step where we do some like real just imperative code like regex type stuff sometimes to like switch some arrows around. You know how like in Cypher you can describe it the relationships in different directions and and stuff like that, right? And so it actually is a little bit messier than you know, it's not that the models out of the box are good enough for all situations right now. I certainly hope like sort of some bitter pill kind of thing, right? that over time it's going to be good for even 99% of all situations, but it's not quite there yet. I mean I I I think, you know, that's where that's where like experts will come in having a good ecosystem will come in and you know, that that will still be the domain of human experts at least for now.

</details>

### LLM 与推荐系统、新工作负载

**主持人**: 我想回到人们正在做的用例和酷炫的事情。您确实认为在传统的**推荐系统**和**欺诈检测**等领域有大量工作。去年我启动了一个 **LLM Rexis** 专题，看起来 **LLM** 正在取代 Rexis。我认为图数据库在那里也有趣的用途。显然，**YouTube** 的所有 Rexis 都是基于 LLM 的。他们……真的吗？他们显然是的。他们将每个视频**令牌化**，并放入一个代码本中，然后在此基础上训练一个 LLM，然后输入你的上下文，就像一个常规的 LLM 一样，并要求它预测你接下来应该观看的视频的令牌。

<details>
<summary>Original English</summary>

**Host**: And I want to come back to like use cases and cool things that people are doing, right? You do think that there's a just a ton of work obviously in like traditional recommendation systems and fraud detection and all that. I did start a LLM Rexis track last year where it looks like LLMs are eating Rexis and I think I think there's there's interesting usage of of graph databases there as well. Apparently all of YouTube, you know, the YouTube Rexis is LLM-based and they Is it really? They they obviously, yeah. They they they tokenize every video every video and put it in a codebook and then they train a LLM on it to and then feed in your your context just like a regular LLM and ask it to predict the tokens of the next videos you should watch.

</details>

**Emil Eifrem**: 太疯狂了。那实际上很酷。我完全不知道。我认识的 Rexis 领域的人，比如 **Eugene**，他是 Rexis 领域的大人物，对此非常看好。显然，这也是新 **X 算法**和 **Pinterest** 的动力来源。这在他们的世界里非常流行，而且很酷。你知道，这肯定让人感到不适。我的算法中肯定有一些奇怪的推荐，像普通系统永远不会推荐的那种，但无论如何，这是一个新世界，每个人都在努力获取信号。我相信如果有人进行 **A/B 测试**，那肯定是 YouTube。所以，是的，基本上，您看到了哪些新的工作负载或用例，您想鼓励人们去尝试？

<details>
<summary>Original English</summary>

**Emil Eifrem**: It's crazy. That that is pretty cool actually. I had no idea. The Rexis people I know, Eugene who's Eugenia who's you know, a big figure in the Rexis world and and all that is very bullish about this. Apparently it's that's also powering the new X algorithm that's also powering Pinterest. It's like all the rage in their world and it's kind of cool. You know, it definitely feels uncomfortable. I definitely have some weird recommendations in my algorithm that like normal systems would never recommend, but whatever, right? Like it's a new world and everyone's trying to get signal. And I'm sure if if anyone AB tests their stuff, it's YouTube. So so yeah, basically like I guess what are the new workloads or use cases that you're seeing that you want to encourage people to check out?

</details>

**Emil Eifrem**: 是的，有很多实验正在进行，我很喜欢，对吧？再说一次，过去十年我们一直专注于全球 2000 强企业，对吧？我提到了很多例子，生命科学、金融服务，我可以滔滔不绝地说下去，但我们也在过去一两年里稍微回归了本源，我们现在有一个**初创公司计划**，我们的云服务 **Aura** 的形式和价格点适合初创公司，对吧？所以这非常非常棒。当然，这里一个非常流行的是**代理式记忆**。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, so there's plenty of experimentation going on which I love, right? Like again, you know, for the last 10 years we've been very focused on the global 2000, right? I mentioned several examples there, life sciences, financial services and I can keep going on and on and on about that, but we've also a little bit gone back to our roots in the last kind of call it year and two or two with like we have a startup program right now and our in our cloud service, which is called Aura, you know, has a form factor and a price point that works for startups, right? And so that's like really really phenomenal. Of course a very popular one here is agentic memory.

</details>

**Emil Eifrem**: 所以有很多人想在**图**上进行记忆。人们不谈论这个，但实际上最初的 **MCP** 版本包含一个微小的内存图数据库。它只有 200 行代码。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And so there there's a lot of people who want to do kind of memory on graphs. People don't talk about this, but like actually the initial MCP release includes like a tiny little in-memory graph database. It's a hard thing to 200 lines of code.

</details>

**主持人**: 是的，是的，我以为是 300 行 **Python**。是的，是的，差不多是那样，对吧？所以它是一个玩具，很小，对吧？它是一个内存中的记忆实现，对吧？但它是图形状的，对吧？这很酷，对吧？我当然喜欢这样。所以有很多人自然而然地这样做。然后当然，在过去三四个月里，所有关于**语境图**的讨论，我们看到了很多人在做类似的事情，这也很棒。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, I thought it was 300 lines of Python. Yeah, yeah, something like that, right?

</details>

**Emil Eifrem**: 这也是我认为图的一个很好的用例。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And it's so it's a toy, it's tiny, right? And it's an in-memory memory implementation, right? But it's graph shape, right? Which is which is cool, right? Of course I love that. And so there's just a lot of people who who kind of naturally do that. And then of course there's all this discussion around context graphs that happened over the last, you know, kind of three three months and so we see plenty of people doing things like that, which is also I think a great use case for graphs.

</details>

### 代理的数据源：四象限模型

**主持人**: 是的，好的。所以**记忆**是一个完整的话题。我不知道我们是否有时间涵盖它。我对它的快速看法是，理论上图数据库非常适合记忆。实际上，它可能有点杀鸡用牛刀。大多数人的记忆没有那么远，而且我认为我们还没有找出记忆的真实结构，那种能够真正长期有效工作的结构。

<details>
<summary>Original English</summary>

**Host**: Yeah, okay. So memory is a whole topic. I don't know if we'll have the the time to cover that. My my quick two cents on it is like in theory of graph databases are fantastic for memory. In practice it might be overkill. Most people's memory doesn't go that far and I don't think like we have figured out the struct the true structure of memory that that I really really works over a super long period of time.

</details>

**主持人**: 而且可能它能装在一个文件里。

<details>
<summary>Original English</summary>

**Host**: And probably it's like yeah, probably fits in a single file.

</details>

**Emil Eifrem**: （笑）

<details>
<summary>Original English</summary>

**Emil Eifrem**: [laughter]

</details>

**主持人**: 就像我不会发出那么多令牌，你知道的。但是**语境图**，是的，对吧？就像我总是说，我不在乎你的 **LLM 上下文**有多长。我们花了三年时间将上下文从 100k 扩展到 100 万，在每个前沿模型中都是如此，但我们不会达到十亿、万亿的上下文行数。您对语境图的讨论有什么看法？我的意思是它真的爆炸式增长。我们和作者做了一个短播客。

<details>
<summary>Original English</summary>

**Host**: Like like I don't put I don't put out that many tokens, you know. But context graphs, yes, right? Like so, you know, this is where like what I always say is I don't care how long your LLM context is. We we took, you know, three years to go from 100k context to 1 million context in every frontier model, but we're not going to a billion, you're not going to a trillion with context graphs uh context lines. What is your take on the context graph discussion? I mean it's really blown up. We had a we had a short pod with the authors about it.

</details>

**主持人**: 我想他们有点把它留给了不同的解释。我想很多人会构建**语境图**系统，然后我们就会弄清楚它是什么，但您早期的看法是什么？

<details>
<summary>Original English</summary>

**Host**: I I think they're kind of leaving it open to interpretation. I think a lot of people will build context graph systems and we'll figure out what it is, but what are your early takes?

</details>

**Emil Eifrem**: 是的。所以我的看法是，在我看来，它完善了所需数据源的**四象限**，以实现我一直所说的**代理**在生产中的**逃逸速度**。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah. So my view on it is that in my head it completed the quadrant of the types of data sources that are required to reach what I've been talking about as kind of escape velocity for agents in production.

</details>

**Emil Eifrem**: 所以我的意思是，我认为正好有**四种类型的数据源**，我很想听听你的看法，对吧？如果你能找出第五种或第六种，但我认为正好有四种数据源是必需的，而且我认为它不像你必须拥有所有四种那么简单，但越多越好。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And so what I mean by that is I think it's exactly four types of data sources and I would love to hear your take on it, right? If you can identify a fifth or a sixth one, but I think there's exactly four data sources that are required and I don't think it's as easy as you have to have all four of them, but like the more the merrier on some level.

</details>

**Emil Eifrem**: 我认为代理的第一个数据源是**操作型数据存储**，对吧？这就是所谓的**记录系统**，我将其视为当前的记录系统，对吧？所以这就像，好吧，我现在有多少客户？或者这个特定客户现在的价值是多少？就是那种东西，对吧？而且我认为在对话中，我们在称呼像操作型数据库之上的应用程序时，我们称之为记录系统。所以 **Salesforce** 是记录系统。这是一种说法。另一种说法是实际的数据库是记录系统，对吧？但无论如何，我认为这就是操作型数据库在第一个象限中的位置。第二个象限对我来说是**云数据仓库**，对吧？所以对我来说，人们说它们不是记录系统。我实际上认为它们是。它们是过去的记录系统，对吧？所以如果操作型是当前的记录系统，那么这就是过去的记录系统，对吧？所以我们在第三季度从拉美地区获得了多少收入？就是那种东西，对吧？

<details>
<summary>Original English</summary>

**Emil Eifrem**: And the first data source for agents, I think is operational data stores, right? And so this is the like the system of records and I think of them as systems of record for the present, right? So this is like, okay, how many customers do I have right now? Or what's the value of this particular customer right now? You know, that kind of thing, right? And and I think in the conversation we flip between calling the application on top of the like operational database, we call that the system of records. So Salesforce is the system of record. That's one way we talk about it. The other way is like the actual database is the system of record, right? But no matter what, I think that's kind of the operational databases in the first this is the kind of the first quadrant. The second quadrant to me is the cloud data warehouses, right? So this to me is people say that they're not systems of record. I actually think they are. They're system of record of the past, right? So if operational is is system of record of the present, then this is the system of record of the past, right? And so how much revenue did we get from the LatAm region in Q3? You know, that kind of thing, right?

</details>

**Emil Eifrem**: 然后第三个象限对我来说是**记忆**。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And then like the third quadrant to me is memory.

</details>

**主持人**: 是的，那是 **OLAP**，对吧？所以 **OLTP** 和 OLAP 就像…

<details>
<summary>Original English</summary>

**Host**: Yeah, that's OLAP, right? So OLTP and OLAP for like

</details>

**主持人**: 是的，是的，是的。你之前说过 **DSL**，那可能也是一个数据术语，**领域特定语言**，对吧？就像 **OLTP** 和 **OLAP**，对吧？

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, yeah. You you said DSL before, which is probably a data term too, domain-specific language, right? Like but OLTP and OLAP, right?

</details>

**Emil Eifrem**: 是的，编程术语，是的。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, programming term, yeah.

</details>

**主持人**: 是的，是的，是的。嗯，然后第三个是**代理式记忆**，对吧？或者可能是**代理式状态**，就像代理式状态的记录系统，可能是短期、长期状态，类似的东西。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, yeah. Um and then the third one is agentic memory, right? And so or maybe like agentic state, like system of record for agentic state, maybe short-term, long-term state, something like that.

</details>

**Emil Eifrem**: 然后第四个是**语境图**，对吧？那么它到底是什么呢？所以，这就是我们喜欢象限一和二中特定价值观背后的原因，对吧？好的，经典的例子是，我以这个价格点将产品卖给了这个客户。这比标价低了 20% 的折扣，而我们的政策规定我们只能打 10% 的折扣，对吧？好的，那么原因就是，我想打入这个垂直领域或这个地理区域，我得到了销售副总裁的批准，他当时正在电话中，通过 Slack，通过电子邮件。它没有被记录在任何地方。而那些被称为**决策轨迹**的东西，最终构成了他们所说的**语境图**。如果我们现在普遍处于试图将决策从人类大脑转移到代理大脑的领域，对吧？以前是从硬件到软件。我甚至不知道现在该称 **LLM** 为什么，对吧？可能是**潜在空间**，对吧？那么，能够访问这些机构知识，了解事情实际是如何发生的，大型组织中的实际决策，感觉非常有价值。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And then the fourth one is the context graph, right? And so what is it then? So this is the why behind we like the particular values in one quadrant one and two, right? And okay, so, you know, the classic example is the, you know, I I sold into this customer at this price point. That's a 20% discount off of list price and our policies say that we're only allowed to discount by 10%, right? Okay, so the why is, well, I wanted to break into this vertical or into this geo and I got an approval from my sales VP that was on the phone, over Slack, by email. It's not recorded anywhere. And those decision traces is what they call it, right? End up constituting a graph that they call the context graph. And if generally we're in the kind of space right now trying to shift decision-making from, yeah, kind of human brains into agentic brains, right? It used to be from wetware to software. I don't even know what to call kind of the LLMs now, right? Into latent space, maybe, right? Um then you know, then having access to that institutional knowledge of how things actually happened, the actual decisions in big organizations, feels really valuable.

</details>

**Emil Eifrem**: 所以这就是四个象限，然后我可以谈谈更多关于**语境图**的具体内容，但首先，你同意这四个象限吗？你看到第五个或第六个了吗？

<details>
<summary>Original English</summary>

**Emil Eifrem**: And so those are the four quadrants and then I can talk about kind of more context graph specific stuff, but first of all, do you agree with the four? Do you see a fifth or a sixth?

</details>

**主持人**: 我觉得四分之三是显而易见的。抱歉，我非常同意。然后第四个是**代理式记忆**，实际上我觉得它有点弱，有点不那么成熟，有点小。就像一、二和四是非常强大、非常大的类别，我知道如何精确地构建它。第三个就像是某种记忆。我觉得可能会有更多，当我思考二维表格时，**OLAP** 或 **OLTP** 都很棒。那是一个维度，关于你的查询有多宽，你正在处理的事务量。另一个维度应该理想地，理想地，轴应该是正交的，我不一定知道那个轴是什么。所以它不完全符合正常的二维表格，这通常意味着可能有一个第三维度被混入了方程式。因为**代理式记忆**，我们可以称之为，它可能主要是个人化的，也许有一些组织层面的，而**语境图**是完全组织层面的。

<details>
<summary>Original English</summary>

**Host**: I feel like the the the three out of the four is obvious. Sorry, I strongly agree with. And then the the fourth one is agentic memory actually where I'm like that's a little weaker, that's a little less established, that's a little smaller. It's like the the one, two and four are very strong, very large categories where I know exactly how to architect it and everything. The third one is like the I don't know, something something memory. And I feel like there could be more when I would think about two by two, right? OLAP or OLTP is great. That's like a dimension of how wide your query, how what volume of transactions you're doing. The other dimension should be ideally ideally axis should be orthogonal and I don't necessarily know what that axis is. Uh and so it doesn't exactly fit a normal two by two which usually means that maybe there's a third dimension that's kind of being sort of mixed into the into the into the equation here. Because agentic memory let's call it is it probably mostly personal maybe some organizational whereas context graphs is fully organizational. Um

</details>

**主持人**: 嗯，是的，所以这就是我最初的反应，但除非您有更多的想法，否则我很高兴只谈论**语境图**。

<details>
<summary>Original English</summary>

**Host**: Uh and yeah so so that's my that's my initial reactions but I'm happy to just only talk about context graphs here unless unless you have more sort of

</details>

**Emil Eifrem**: 不，但是听到这个真的很有趣。我想**代理式记忆**是某种我想了解那个个体过去发生了什么。我认为这将是许多用例的重要检索来源，但也许不是全部。

<details>
<summary>Original English</summary>

**Emil Eifrem**: No but I I it was really interesting to hear that. I think like agentic memory is some kind of I want to understand what happened in the past for that individual. I think is going to be an important source for retrieval for many use cases but maybe not all and

</details>

**主持人**: 是的。是的，是的，是的，所以也许好吧，也许我用自己的话来说，**代理式记忆**是你和代理一起做的事情，而**语境图**是你和其他所有人一起做的事情。因为我认为是的，实际上所有代理公司都在查询他们自己的过去轨迹，并记忆知识和自我改进，这与语境图无关。只是代理在使用时应该变得更好，对吧？或者就像是的，当然。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah so so so maybe okay maybe one one sort of I'll put this in my own words is agentic memory is is sort of the stuff that you've done with the agent and then the context graph is the stuff you've done with everyone else because I think yeah actually there's a lot of work by all the agent companies on querying their own past trajectories and memorizing knowledge and self-improvement from from there that really has nothing to do with the context graph. It is just the agent should get better as I use it right or it's like yeah of course.

</details>

### 语境图的启动与企业级应用

**Emil Eifrem**: 是的，是的。现在专门针对**语境图**，对吧？所以我认为以某种数字形式编码机构知识是非常有意义的，对吧？这又回到了你遇到的那种博士级别的实习生，他们每天醒来都不知道过去发生了什么，就是那种情况，对吧？所以，所以这很有道理。我想诀窍在于你如何实际地**工具化**你的组织来实现这一目标？

<details>
<summary>Original English</summary>

**Emil Eifrem**: right. Yeah yeah. Now on context graph specifically right? So I think it makes it a lot of sense to somehow encode that institutional knowledge right in some digital form right? And it's back to the PhD level intern that you get that wake up every day and they don't know the past you know that kind of thing right? And so so that that makes sense. I guess the trick is like how do you actually instrument your organization to get there?

</details>

**Emil Eifrem**: 我认为我们都能看到这种未来状态，例如我的代理已经在生产中，就像我之前的例子一样，我有一个**代理式流程**，它会联系我的客户并向他们提供抵押贷款折扣或类似的东西，对吧？如果他们这样做，他们应该被工具化并记录下他们在此过程中所有的决策，并将其用作未来改进的来源，你可以感受到复合效应或飞轮效应，对吧？好的。

<details>
<summary>Original English</summary>

**Emil Eifrem**: I think we can all see this kind of future state where okay I have my agents in production like my example from before like I have some kind of an agentic process that reaches out to my customer and offer them mortgage discount or or something like that right? And if they do that they should be instrumented and record all of their decision-making throughout that use that as a source for improving themselves going forward and you can kind of sense the compounding effect or the flywheel right? Okay.

</details>

**Emil Eifrem**: 一旦我们达到那个目标，那就太棒了，但我们现在还没有达到。我们现在还没有以任何数字形式拥有它。最典型的情况是销售代表打电话给某人，从车里要求折扣，得到同意，然后成交。最好的情况是在 **Salesforce** 中记录下来，对吧？今天就是这样发生的，对吧？那么我们如何启动**语境图**呢？这几乎是我与大型企业客户进行的所有对话。对于初创公司来说，语境图的启动是通过其产品获得采用来实现的，对吧？所以问题就不在于此，问题在于你如何才能让我的产品获得采用，对吧？但在企业环境中，恕我直言，问题就变成了你如何开始这种工具化，以便我能获得足够的决策轨迹来启动这个过程。这最终成为了有趣的讨论。

<details>
<summary>Original English</summary>

**Emil Eifrem**: That's great once we're there but we're not there now we don't have it that in any digital form most typically it's that sales rep calling someone up from a car asking for a discount getting a yes then selling the deal and at best it's recorded in Salesforce right? And that's kind of how it happens today right? Like so how then do we bootstrap the context graph? So that has been almost all the conversations that I've had with big enterprise customers. With startups the bootstrapping of the context graph is by virtue of getting adoption of their product right? And so that's then not the problem then the the problem there is like how do you even get adoption of my product right? But inside the kind of the enterprise context no pun intended that ends up being like how do you even start this instrumentation so I get enough decision trails that I can bootstrap the process. That ends up being the the interesting discussion.

</details>

**主持人**: 那么初创公司对您来说有多大的价值？您与**财富 100 强**中 80% 的公司打交道，您瞄准的是 2000 家公司，初创公司，你知道，免费套餐什么的，它们没那么大的价值。是的。

<details>
<summary>Original English</summary>

**Host**: So how valuable are startups to you? Like you you deal with like 80 of the Fortune 100 you you you target to the 2000s startups you know free tier whatever like they're not that they're not worth that much. Yeah.

</details>

**Emil Eifrem**: 我的意思是，也许我会从创始人兼首席执行官的角度来看待这个问题，对吧？大约十年前，我们查看了我们的收入，发现三分之一、三分之一、三分之一，十亿及以上的收入占三分之一，然后是一些中端市场的东西，然后三分之一是初创公司，对吧？我们只是看到十亿及以上细分市场的所有潜在指标都好得多。

<details>
<summary>Original English</summary>

**Emil Eifrem**: I mean maybe I'll take the the kind of founder CEO kind of point of view on this right? Like like a decade ago right we looked at our revenue and it was like a third a third a third and like a billion and above was a third and then there's like some kind of a mid-market kind of thing right? And then a third was startups right? And we just saw all the underlying metrics of the of the billion and above segment was just so much better.

</details>

**Emil Eifrem**: 然后我们看了所有大规模的数据库公司，也称为 **Oracle**，但我也看过 **DB2** 等等。他们 80% 以上的收入来自全球 2000 强。所以很明显，这就是数据库公司盈利的地方，对吧？所以我们把所有这些加在一起，然后我们说，好的，100% 我们需要做的是专注于企业，那是一个正确的商业决策。我的 CEO 帽子喜欢它，非常成功，这就是为什么我今天能坐在这里，所有这些好东西，对吧？

<details>
<summary>Original English</summary>

**Emil Eifrem**: And then we looked at all database companies at scale also known as Oracle but I've been DB2 as well and stuff like that and 80 plus percent of their revenue was from the global 2000. So clearly that is where database companies monetize right? And so we kind of added all these things together and we said okay 100% what we need to do is lean in on the enterprise and that was the right business decision. My CEO hat love it was super successful that's why I can sit here today all that good stuff right?

</details>

**Emil Eifrem**: 我的创始人帽子有点难过，对吧？因为初创公司的人是我的同类人。对吧？他们代表着未来以及所有类似的东西，对吧？所以我们现在有了新一代的 **AI 原生初创公司**，对吧？我们现在非常重视将我们构建到这些架构中，对吧？不一定是为了产生大量的 **ARR**。我总是会从像 **Bank of America** 这样的通用例子中赚更多的钱，而不是说任何关于 Bank of America 的具体事情，但我们确实有北美 20 家最大的银行中有 20 家是客户，所以你可以从中推断出你想要的东西，对吧？所以我们拥有所有这些客户，对吧？

<details>
<summary>Original English</summary>

**Emil Eifrem**: My founder hat was a little bit sad right? Because startup people are my people. Right? And and they represent the future and all of that kind of stuff right? And so that we have this new generation of AI native startups happening right? We're like now this is really important for us to be built into those architectures right? And not necessarily maybe from generating tons and tons of ARR I will always make more money from Bank of America as a kind of generic example not saying anything specific about Bank of America but except we do have 20 of the 20 biggest banks in North America are customers so you can derive from that what you want right? So we have all of them right?

</details>

**Emil Eifrem**: 但我认为融入时代精神真的非常重要。从这个角度来看，让下一代初创公司基于 **Neo4j** 构建是非常关键和重要的。

<details>
<summary>Original English</summary>

**Emil Eifrem**: But I'm always going to make more money from the enterprise segment but I think it's really important to just be part of the zeitgeist. And from that perspective like getting the next generation of startups built on Neo4j is is really crucial and important.

</details>

**主持人**: 我想初创公司更容易上手，因为它们比大公司有更少的上下文。所以我想，到目前为止，您推荐了哪些最佳实践？无论是哪个领域，老实说，两者都很有趣。他们甚至如何开始？这取决于你操作的高度，对吧？如果它是一家初创公司，它不只是有一个产品，而是产品就是公司。所以那就是一切，对吧？如果你看看企业环境内部，那是非常不同的，对吧？因为那样我们就会在两个层面进行互动，对吧？一个是单个应用程序、单个项目的范围，对吧？另一个是更企业范围的。让我稍微谈谈最后一个，因为这是自两年前的**图 RAG** 演讲以来发生的一个重大变化。我们正在看到一个清晰的模式是，我们倾向于将其称为**知识层**，但我们遇到了很多企业，问题是，好的，每个数据源都将在这里有一个 **MCP** 端点，对吧？好的，我想让我的代理访问它，那么我该怎么做呢？要么我让我的代理访问所有的 MCP 端点，让它自己去解决，对吧？

<details>
<summary>Original English</summary>

**Host**: I presumably startups are easier to onboard because they have less context than the the the larger companies. So I guess what have you prescribed so far in terms of like you know whichever segment you want uh honestly both are interesting to me. What are the best practices so far like you know how do they even get started? It depends on which altitude you operate at right? Like if it's a if it's a single startup it's not just there's one product but the product is the company. So that's then everything right? And that's very different if you look in inside of the enterprise context right? Because then we engage in in two levels right? One is the scope of a single application a single project right? And the other one is more enterprise-wide. This let me talk about the the the last one for a moment because this is a big change that has happened since certainly since the two years ago the the the graph rack talk. A clear pattern that we're seeing happening is we we tend to call it the knowledge layer but we bump into a lot of enterprises and the problem is okay every single data source is going to have some kind of an MCP endpoint here right? Okay I want to give my agents access to that so like what can I do? Either I give my agents access to all of the MCP endpoints and let it figure it out right?

</details>

**主持人**: 他们遇到的问题是，是的，那确实有效，但有些数据会相互冲突。对吧？

<details>
<summary>Original English</summary>

**Host**: The problem that they run into is that yes that works but like some of the data is going to be conflicting. Right?

</details>

**Emil Eifrem**: 所以我们刚才谈到我们有一个云服务，对吧？即使对我来说，当我试图弄清楚我的云服务上有多少客户时，我去了实际的云平台并询问，我们有大约 3000 个客户，对吧？这意味着有多少是活跃的，有一个运行中的数据库的账户。然后我去了财务系统，我有 2800 个客户，因为那些是有信用卡的客户，你知道的，好的，那么你如何理解这一点呢，对吧？我认为我们正在了解到，**LLM** 会给你一个答案，毫无疑问，对吧？你只是不知道它是对还是错。对吧？而且很难发现这一点，对吧？所以我们现在正在与许多大型企业谈论的是，你想要拥有那个层，或者他们想要拥有那个层，对吧？在那里他们整合了数据所在位置的**元数据**，对吧？在他们的企业内部，这给你带来了**一致性**和**信任**和**可解释性**。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And so we just talked about we have a cloud service right? Even for me like when I try to figure out like how many customers do I have on my cloud service? Like I go to the actual cloud platform and I ask and we have let's call it 3000 customers right? That means how many are active have an account with a running database and then I go to like the finance system and I have 2800 customers because those are the ones that were like with the credit card and the you know okay so like so how do you make sense of that right? And I think we're learning that an LLM is going to give you an answer with without doubt right? You just have no idea if it's right or wrong. Right? And it's very hard to find that out right? And so what we're talking to a lot of big enterprises about now right? Is you want to own that layer or they want to own that layer right? Where they consolidate the metadata around where data sits right? Inside of their enterprise and that gives you the consistency and the trust and the explainability

</details>

**Emil Eifrem**: 那么他们想要拥有的元数据是什么呢？它基本上是**数据资产图景**，对吧？所以你的关系数据库中有什么模式？你的 S3 中有什么桶等等，对吧？以图的形式表达出来，并与面向业务的**本体论**结合起来。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And so what is that metadata that they want to own then? It's basically the data asset landscape right? So what are the schemas that sit in your relational database right? What are the buckets in your S3 and so on and so forth right? Express that in a graph form marry it up with a business-facing ontology.

</details>

**Emil Eifrem**: 客户是什么？对吧？客户如何与供应商相关联，我有什么概念？

<details>
<summary>Original English</summary>

**Emil Eifrem**: What is a customer? Right? Like how does a customer relate to a supplier and what what are the concepts that I have?

</details>

**主持人**: 那太难了。你和五个人交谈，你会得到六个答案。

<details>
<summary>Original English</summary>

**Host**: That's so hard. You talk to five different people you get six answers.

</details>

**Emil Eifrem**: 完全正确，这正是过去阻碍这一进展的关键问题。现在发生的是，我需要解决这个问题，才能让我的代理在这个特定用例中取得成功。所以这迫使他们就一个足以让这些代理工作的方案达成共识。对吧？

<details>
<summary>Original English</summary>

**Emil Eifrem**: That's exactly right and this has been the key problem that has has been holding this back in the past. What is happening now of course is I need to solve this to make my agent successful for this particular use case. So that forces them to kind of converge on something that is good enough to work for those agents. Right?

</details>

**Emil Eifrem**: 然后第三部分是映射，人们谈论**语义层**，人们谈论**语境层**。我喜欢**知识层**这个词，它们都意味着相似但又不同的事物，但这现在是一个非常非常流行的用例。如果你访问我们的网站，如果你搜索“领先媒体公司”之类的，加上 **Neo4j**，你就会看到它，它有一个漂亮的小型架构图，你可以向下滚动，如果你能分享屏幕，你就会看到它。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And then the third piece is kind of the mapping between between people talk about semantic layers people talk about context layers I like the term knowledge layer they all mean kind of the similar but distinct things but this is a very very popular use case that we have right now. If you you were on our website if you Google kind of leading media company or something like this um and Neo4j you're you're going to see this and it has like a nice little architecture in green that that you can scroll down and if you can screen share that you'll you'll see it.

</details>

**Emil Eifrem**: 所以你底部有不同的数据孤岛，他们称之为**语义层**，对吧？然后他们的代理在其之上运行。有两种口味，一种是**零拷贝**，所以知识层会给你一个地图，告诉你实际应该去哪里查询，或者有时我们会将数据（部分数据）内联到知识层，这样你就可以直接在那里进行查询。是的。什么是零拷贝？我想说 **Salesforce** 创造或者至少推广了这个术语。这就是说，而不是在每个单独的，比如 **Snowflake** 和这个那个之间复制你的数据，对吧？相反，你有一个虚拟化类型的层，它指向原始数据源。所以你指向数据包装器。

<details>
<summary>Original English</summary>

**Emil Eifrem**: And so you have like the disparate data silos at the at the bottom and they they call it the semantic layer right? And then they have their agents running on top of that. There's a couple of flavors where you do kind of zero copy so what the what the knowledge layer will give you is the map of where I should actually go and query or sometimes we inline the data like partial data into the knowledge layer so you can just do the queries right in there. Yeah. What what what is zero copy again? I want to say Salesforce has coined or at least popularized this term. This is where it's like okay instead of replicating your data in every single like between Snowflake and this and that right? Instead you have like a virtualization type layer where it points to the original data source. So you're pointing data wrapper.

</details>

**Emil Eifrem**: 是的，没错，完全正确。对吧？你可以看出我非常喜欢 **Postgres**。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, exactly Exactly. All right? You can tell I'm like very Postgres.

</details>

**主持人**: 是的，是的，是的。没错。

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, yeah. That's right.

</details>

**Emil Eifrem**: 所以，在查询路径上，你最终会进入这个层，然后你找出数据在哪里，有时它会物化到那个层，所以你可以直接查询它。所以，这是一种非常流行的企业级用例。但是，我想你最初的问题是，好的。入门的最佳实践是什么？我们谈到了**语境图**。有一个非常棒的 **Python** 包装器叫做 **UVX**，它可以创建语境图，对吧？它为你提供了 22 个不同行业的开箱即用的语境图。它几天前刚刚发布。它建立了一个完整的 **Neo4j**，带有一个前端，你可以……

<details>
<summary>Original English</summary>

**Emil Eifrem**: And so, on the query path, you end up going to this layer, and then you figure out where the data sits, and sometimes it's materialized into that layer, and so you can just query that directly. And so, this is this is a very popular use case kind of enterprise-wide. But, I think your original question was like Okay. What are the best practices for for getting started? We talked about context graphs. Uh there's a uh a really neat Python wrapper called UVX, like whatever create context graph, right? That gives you a context graph out of the box for I think 22 different industries. Uh it was just published like a few a few days ago. And it stands up a full full Neo4j with a with a front end, and you can

</details>

**主持人**: 它是建模的，你会喜欢这个，它是仿照什么？**Create React app**？当然。

<details>
<summary>Original English</summary>

**Host**: It is modeled and you're going to love this with It's modeled after What was it called? Create React app? Of course.

</details>

**Emil Eifrem**: 对吧？当然。所以，你可以拥有这种交互式的它会帮助你处理自己的数据，但你也可以选择现有的领域。然后……

<details>
<summary>Original English</summary>

**Emil Eifrem**: Right? Of course. And so, you can have like this interactive It'll help you with your own data, but you can also choose you know, out of um existing domains. And then

</details>

**主持人**: 现有的领域。哇。

<details>
<summary>Original English</summary>

**Host**: Existing domains. Wow.

</details>

**Emil Eifrem**: 与八到九个不同的代理平台集成。只有一个，而且它不在这里。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Integrate with eight or nine different agent platforms. Only one to one, and it's the one that's not here.

</details>

**主持人**: 不，是哪一个？社交媒体。

<details>
<summary>Original English</summary>

**Host**: No, which one? Social media.

</details>

**Emil Eifrem**: 有趣。是的。是的，我们可以添加那个。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Interesting. Yeah. Yeah, we can add that.

</details>

**主持人**: 是的，是的，是的。**社交图谱**和**社交媒体**。基本上，我有一个观点，就是每个 **SaaS** 最终都会在 SaaS 内部拥有一个带有非系统的社交图谱。你明白我的意思吗？你需要有团队的人。你需要能够相互发消息的人。你需要发送通知。你需要社交媒体的元素渗透到每个领域。它甚至不是一个垂直领域。它只是一个我总是……你知道的特性集。嗯，我以前确实考虑过将这个作为一个业务来做，我发现其他人也做过，但它没有作为一个业务成功。但是，基本上，你知道，作为一项功能，将**社交媒体**或**社交网络**嵌入我的用户群。是嵌入你的终端用户群还是你的员工群？

<details>
<summary>Original English</summary>

**Host**: Yeah, yeah, yeah. Social social graph and social media. Basically, I have a view that every SaaS basically eventually becomes has a has a social graph inside of the SaaS with the off system. You know what I mean? You want people with teams. You want people who can message each other. You want to send notifications. You want to feed elements of social media find their way into every single one of these domains. It's like not even a a a vertical domain. It's just a a a feature set that I always you know, um I actually looked into doing this as a as a business before, and I I found that other people have done it, and and it didn't work as a business. But, basically, you know, the drop-in social media uh social I guess network into my user base as a feature. Into your end user base or into your employee base?

</details>

**主持人**: 不，是终端用户。

<details>
<summary>Original English</summary>

**Host**: No, uh end user.

</details>

**Emil Eifrem**: 是的，是的，是的。是的。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, yeah, yeah. Yeah.

</details>

**主持人**: 所以，你明白我的意思吗？就像因为我的每个用户都在一个团队中工作。他们关注。他们有。他们想要一个动态。他们想要通知。他们想要私信。他们甚至想要屏蔽等等，对吧？他们想要一个主页。所有这些都是社交功能，而这些人都不会自己构建，但他们可能想要一些东西。也许，也许在这里。我不知道。嗯，但无论如何，这真的很酷。**Cloud Co-Work** 的 **William**，我知道他以前在其中一个 AI 公司做过工作坊。

<details>
<summary>Original English</summary>

**Host**: So, you know what I mean? Like like because because every one of my users they work in a team. They follow. They have They want a feed. They want notifications. They want DMs. They want even blocking whatever, right? They want a homepage. It's all social features that none of these people really would would build themselves, but probably they want something. Maybe maybe here. I don't know. Um but yeah, anyway, this is really cool. Cloud Co-Work William I I I know he's a he's done a workshop at one of it AI's before.

</details>

**Emil Eifrem**: 是的，他非常出色。所以它所做的只是帮助你入门，对吧？它会创建一些合成数据。它还集成了许多 SaaS 工具，比如……

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, he's he's phenomenal. And um so, what what it does is it just helps you get started, right? And it creates some either synthetic data. It also integrates with like a bunch of SaaS tools like uh

</details>

**主持人**: 我看到你对那个，怎么说来着？**Google Workspace CLI** 还是类似的东西很感兴趣，对吧？所以，每个人都对那个很感兴趣。我的意思是，你看到了那个有多少赞。我知道。这太令人震惊了，对吧？

<details>
<summary>Original English</summary>

**Host**: I saw you were excited about the What is it called? The Google Workspace CLI or something like this, right? So, Everyone is excited about that. I mean, you see the number of likes on that one. I know. It is shocking, right?

</details>

**主持人**: 好吧，所以我对 **Cloud Co-Work** 如此兴奋是因为我可以用它来导航 **GCP** 控制台。我当时想我不想做那个，太糟糕了。

<details>
<summary>Original English</summary>

**Host**: how Okay, [clears throat] so I got so excited about Cloud Co-Work because I could use it to navigate the GCP dashboard. I was like I don't want to do It's so bad.

</details>

**Emil Eifrem**: （笑）

<details>
<summary>Original English</summary>

**Emil Eifrem**: [laughter]

</details>

**主持人**: 但是，所以它既可以给你真实数据，也可以为你生成合成数据。

<details>
<summary>Original English</summary>

**Host**: But, so so it can kind of get you real data, or it can generate synthetic data for you. And

</details>

**Emil Eifrem**: 是的。它使用我们的一种**代理记忆**工具包，它既有**短期记忆**，那是对话状态类型的东西。它有**长期记忆**，那是领域中的所有实体和所有概念。它还有**决策轨迹**，也就是**语境图**。所以，它可以将所有这些与一个小型的图可视化用户界面等结合在一起，对吧？所以，这是一个很好的入门方式。这是一个很棒的想法。我不敢相信没有人做过。我不敢相信这只有六天历史。是的，你应该大力推广这个。而且你可以想象，这和以前的故事一样。他是在一个周日下午，也就是五六天前的一个周日下午，在我们举行的一个**语境图**聚会之前，把它搞出来的，人们都很喜欢。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah. It It It uses We have an like an agent memory kind of toolkit, which has either short-term memory. So, that's kind of conversational state type stuff. It has long-term memory, so that those are all the entities and all the concepts in the domain. And it also has the decision traces, so the context graphs. So, can put it all together with a little graph visualization kind of UI UI and all that kind of stuff, right? So, that's a great way to get started. It's It's a great idea. I can't believe no one else has done it. I can't believe this is only 6 days old. Yeah, you should you should uh promote this a lot. And and and you can imagine it's the same story. Like he he hacked it up one Sunday afternoon like this. So, I guess 5 days ago, 6 days ago, Sunday afternoon ahead of a context graph meetup that we that we did, and people love it.

</details>

### 产品编辑与“做减法”的艺术

**主持人**: 是的。是的，是的。好的。好的。如果我对这个有什么反馈的话，那就是它做得太多了。几乎……

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah, yeah. Okay. Okay. I- If If I have one feedback looking at this, it it almost does too much. Almost It's like

</details>

**Emil Eifrem**: 是的，是的。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Yeah, yeah.

</details>

**主持人**: 嗯……它在哪里结束，我的应用程序在哪里开始，对吧？这里有很多东西。所以，我已经对这个自述文件感到有点不知所措了。所以，一些专注是很有价值的。你知道，这是那种事情，就像 **Open Code** 首席执行官 **Dax** 说的：“看，在这个时代，任何功能你都可以在几天内凭感觉编码出来，实际上克制和专注以及符合目的才是最重要的。”因为是的，你可以添加它，但它真的有增加任何东西吗？还是只是更多填充我上下文窗口的东西？我只是想：“好吧，你为我做了什么工作？”然后就把它做得很好，你知道吗？所以，我确实认为这正是其中之一。

<details>
<summary>Original English</summary>

**Host**: Um W- Where does it end, and where does my app begin, right? There's There's a lot here. And so, I I'm already feeling a little bit overwhelmed with this read me. So, some focus is is is valuable. You know, it's it's one of those things where like open code You know, the open code CEO Dax was like, "Look, in an age where any feature you can just vibe code it within days, actually restraint and focus and like, you know, fit for purpose is is the thing." Because yeah, you can add it, but like does it actually add anything, or is it just more stuff that just fills up my context window? And I'm just like, "Okay, what what is the the job that you do for me?" And just just do it really well, you know? So, I I do think like this is one of those things that

</details>

**Emil Eifrem**: 有点像**史蒂夫·乔布斯**，我是产品的编辑那种。当然，编辑最重要的部分就是说不。就像移除东西一样。

<details>
<summary>Original English</summary>

**Emil Eifrem**: kind of Steve Jobs, I'm the editor of the product kind of thing. And of course, the most important part of the editor is saying no. Like removing things.

</details>

### 个人感想：激动与挑战并存的时代

**Emil Eifrem**: 你知道，那是一次快速的概览。显然，你的世界里还有更多正在发生的事情，我们会了解到的。是的，除了你的官方身份之外，还有什么临别感言吗？你骨子里是个黑客。还有什么让你兴奋不已？什么让你超级兴奋？

<details>
<summary>Original English</summary>

**Emil Eifrem**: You know, that that's a that's a quick tour. Uh obviously, there's a lot more going on in your world that we'll we'll learn about. Yeah, any Any parting thoughts outside of your your official hat? You're you're your hacker at heart. What else are you excited by? What do you get you super excited?

</details>

**Emil Eifrem**: 嗯，我的意思是，我们现在生活的这个时代既是最激动人心的时代，也是最令人震惊的时代。我们根本没有谈论**SaaS 灾难**以及所有类似的事情，但是，你知道，作为 CEO，我必须关注这些事情。当然，我们处于最前沿，开始看到**购买与构建**的转变，对吧？因为 **Cloudera** 是第一个例子，你知道，它被关闭了。

<details>
<summary>Original English</summary>

**Emil Eifrem**: Well, I mean, it's we have It's like this era that we live in right now is simultaneously the most exciting time and the most shocking time. We haven't talked at all about kind of SaaS-pocalypse and all of that kind of stuff, but you know, with the other hat as CEO, I have to pay attention to to to things like that. And of course, we were kind of front and center in like starting to see the shift of the buy versus build, right? Because, you know, Cloudera was one of the first examples of you know, shutting down

</details>

**主持人**: 它，然后又回滚了。那是公众的看法，对吧？他们当然，我不会替 **Cloudera** 发言，但我认为这可能存在夸大其词，但显然在**购买与构建**之间存在转变，对吧？但是，对我来说……

<details>
<summary>Original English</summary>

**Host**: it, and then also rolled it back. That that is the public view, right? They certainly I'm not going to speak for for Cloudera, but I I think there is overstatement on both sides of that of that probably, but but clearly there's a shift in that buy versus build, right? But, then for me

</details>

**Emil Eifrem**: 我个人……

<details>
<summary>Original English</summary>

**Emil Eifrem**: personally

</details>

**主持人**: 对我来说，我每年花 20 万购买会议管理软件，我讨厌它，你知道的。也许我花 2000 块就能做一个我喜欢的。

<details>
<summary>Original English</summary>

**Host**: For for me, I pay 200,000 a year for conference management software that I hate like, you know, maybe to pay I pay 2,000 to to make one that I like.

</details>

**Emil Eifrem**: 令我震惊的是，你这个人，竟然没有解决这个问题。

<details>
<summary>Original English</summary>

**Emil Eifrem**: That's shocking that you of all people haven't fixed that.

</details>

**主持人**: 我忙着管理，你知道的，打印徽章，还有搞清楚我的魔术师费用等等，你知道吗？我只是，这不是我的首要任务。而且我有一个团队，他们不像我一样是**代理原生**的。所以，我不能像一个 CEO 一样单方面决定：“哦，现在我的整个公司都要这么做。”并期望我的每个员工都知道该怎么做，因为不，他们需要接受培训。实际上，有时熟悉、有 bug、缓慢、无论什么样的系统，尽管有其所有缺陷，实际上仍然更好。而且这又回到了这些东西的价值是什么？其中很大一部分是理解流程并对这些流程进行规范。对吧？这需要我们花一些时间进行迭代，如果你专注于它，你可以做到。但与此同时，你将要付出双倍的钱，对吧？所以，所以我明白了。

<details>
<summary>Original English</summary>

**Host**: I'm busy running, you know, like printing badges and like freaking figuring out my magician costs and everything, you know? Like I just This is not like top of my list. And I have a team that isn't as agent-native as me. So, I cannot just like unilaterally as like as like a CEO like just decide, "Oh, like my whole company's going to do this now." And expect that every single one of my employees will know what to do because no, they need to be trained. And actually, sometimes the the familiar, buggy, slow, whatever system with all its flaws actually still is better. And and it's it's back to like what what is the value of these things? And a big part of it is understanding processes and being prescriptive about those processes, right? And this takes us some while to iterate there, and you could do it if you focused on it. But, in the meantime, you're going to pay for the two money, right? So, so so I get it.

</details>

**Emil Eifrem**: 但是，所以这有点是可怕的一面，或者说是令人震惊的一面，对吧？然后另一方面就是，天哪，构建的能力。还记得吗？我有点是**后技术人员**，对吧？所以，我写不出代码，**比较和交换**之类的东西，那是我知道的那种东西，对吧？但我已经有十年没有当过现代的专业程序员了，对吧？现在，我又可以了，软件又变得可塑了，这真是太令人兴奋了。

<details>
<summary>Original English</summary>

**Emil Eifrem**: But, but so that's kind of on the terrifying side or like the shocking side or something like this, right? And then on the other side is just man, the ability to build. And remember like I I'm kind of post-technical, right? Like so, I couldn't write the the the code and swap stuff is like that's the kind of stuff that I know, right? But, I haven't been a modern real pro programmer for 10 years, right? And now again, I can like software is malleable again, which is just so phenomenally exciting.

</details>

**主持人**: 是的，但我认为**后技术人员**（比如你我这样的管理者）的一种失败模式是，你认为“哦，AI 可以做到”。然后你就凭感觉编码了一些东西，把它扔给你的员工，然后期望他们能立刻上手。不，我看到，你知道，我确实想鼓励我们中间的领导者也要尊重这样一个事实：并不是所有东西都是凭感觉编码出来的，如果你这样做，你的员工有时仍然需要清理你的烂摊子。真正的手艺。我完全同意。特别是作为一个数据库公司，伙计，那里有一些真正的手艺。是的，但你们测试得很好。你知道我的意思吗？数据库测试是一流的。大多数软件都不是这样的。

<details>
<summary>Original English</summary>

**Host**: Yeah, I but I think one one failure mode of the post-technical, you know, like manager, which you are, which I am, is that you think you you Oh, AI can do it. And then you like, you know, you vibe code something, you throw it to your your employees, and then you expect that they just pick it up. No, I saw like I you know, I do I do want to encourage the leaders among us to also just be respectful of uh the fact that not everything is vibe coded, and your employees still have to clean up your mess sometimes if you do this. Of the real craft. I completely agree. Especially like as a database company, like man, there's there's some some real craft in that. Yeah, but you guys test very well. You know what I mean? Like the database testing is is top-notch. Most software is not like this.

</details>

**主持人**: 你知道吗？所以，是的，实际上我知道，因为你可以测试很多，所以你可以更多地凭感觉编码，因为它太可测试了。你知道我的意思吗？所以，无论如何。

<details>
<summary>Original English</summary>

**Host**: You know? So, yeah, actually I know because you can test so much, then you can vibe code more because it's so so testable. You know what I mean? So, anyway.

</details>

**主持人**: 无论如何，谢谢你，Emil。这次聊天真的很有趣。嗯，我很高兴能和你见面。我想你要来旧金山。嗯，所以我们会在那里见面。好的，我的朋友。回头再聊。好的。好的。

<details>
<summary>Original English</summary>

**Host**: Anyway, thank you, Emma. This is really fun chat. Um and I'm excited to catch up in person. Uh I think you're coming to to San Francisco. Um so, I'll see you there. All right, my friend. Talk soon. All right. All right.

</details>

**Emil Eifrem**: （音乐）

<details>
<summary>Original English</summary>

**Emil Eifrem**: [music]

</details>