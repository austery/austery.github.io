---
author: AI Engineer
date: '2026-10-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=u_jvuCjuvEk
speaker: AI Engineer
tags:
  - vector-search
  - data-retrieval
  - access-control
  - ai-agent
title: TurboPuffer 与桥水基金：为企业级 AI 分析师构建带权限隔离的向量检索
summary: TurboPuffer CTO 与桥水基金产品工程负责人探讨了如何在大规模私有数据场景下为 AI 分析师实现带权限过滤的快速向量检索。桥水基金分享了包含约 1 亿文档的非结构化数据库 Vault 的权限挑战，TurboPuffer 介绍了基于对象存储的架构，并通过结合预过滤与后过滤的原生过滤聚类策略，在 4.5 亿向量规模下实现 120 毫秒的 P90 检索延迟。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people:
  - Nick Hill
  - Aaron Linsky
companies_orgs:
  - TurboPuffer
  - Bridgewater Associates
products_models:
  - Vault
  - Delorean
media_books: []
status: evergreen
---
### 引言与企业 AI 分析师的权限挑战

**>>**: 好的，大家好，感谢大家的到来。我是 Turbo Puffer 的 CTO Nick Hill。
<details><summary>Original English</summary>
**>>**: All right. Hello, everyone. Thank you all for coming. I'm Nick Hill, CTO of Turbo Puffer.
</details>

**>>**: 我是桥水基金（Bridgewater Associates）的产品工程负责人 Aaron Linsky。
<details><summary>Original English</summary>
**>>**: And I'm Aaron Linsky, the head of product engineering at Bridgewater Associates.
</details>

**>>**: 我们今天来这里是想和大家聊聊，如何构建一个能够“保守秘密”的 AI 分析师。接下来我会稍作解释这究竟是什么意思。

在这里，这是一个关于如何构建 AI 分析师的极度简化视图，但它的目的是捕捉围绕“权限”的一个重要维度。

在这个图表中，用户与这个 AI Agent 进行交互，首先提出一个问题，比如“为什么上个月代币价格下跌了这么多？”然后你将该问题输入给大语言模型（LLM），LLM 开始思考这个问题，进行调查和研究。

在展开调查的过程中，它需要搜索事实来作为其信息的依据，并引导其调查方向。其中一些事实可能来自公共网络，但其他事实可能来自您组织内部的私有文档。现在，公共网络从某个维度来看，比您组织内部的私有信息要容易检索得多。根据定义，公共网络是公开的。组织中的每个人看到的都是完全相同的文档。因此，那里不存在权限问题。无论提问者是谁，每一份公共网络文档都可以立即提供给 AI 分析师。

但您组织内部的信息看起来则截然不同。每封电子邮件、每份会议记录、每篇报告，都可能附带有一组完全不同的权限设置，属于不同的群组，或者在这些文档上配置了独立的个人权限分配。

你可以看到，我们这里用不同的颜色来反映这样一个事实：该私有数据集中的每一份文档都有一套不同的权限。这是信息检索领域一个非常经典的难题，也是我们在设计 Turbo Puffer 时明确致力于解决的问题。

但在深入探讨之前，我先将发言权交给 Aaron，让他来谈谈为什么这些私有信息对桥水基金的 AI 分析师至关重要。
<details><summary>Original English</summary>
**>>**: And we're here to talk to you today about how you build an AI analyst that can keep a secret. And I'll explain a bit more about what that means.

Here.

Now, this is a very oversimplified view of how you would go about building an AI analyst, but it is meant to capture an important dimension around permissions.

So, in this diagram, you're user interacting with this AI agent, you start with a question, maybe something like, "Why have token prices come down so much in the last month?" And you feed that question into an LLM, which will begin thinking about that question, investigating, researching.

And as it does that investigation, it's going to search for facts to ground its information, to lead its investigation. Some of those facts might come from the public web, but other facts might come from private documents in your organization. Now, the public web is on one dimension much easier to search than the information that's private to your organization. By definition, the public web is public. Everyone in your organization can see exactly the same documents. So, there's no permission issue there. Every public web document can be immediately fed into the AI analyst, no matter who's asking the question.

But the information internal to your organization looks very different. Every email, every meeting note, every report might have a completely different set of permissions attached to it, belonging to different groups, maybe individual permissions assignments on those docs.

And you can see here, we've got different colors here reflecting the fact that every document in that private data set has a different set of permissions. And this is a classically hard problem in information retrieval, and it's something we explicitly designed Turbo Puffer to solve.

But before I get into that, I'm going to hand it over to Aaron to talk about why this private information is so important to Bridgewater's AI analyst.
</details>

### 桥水基金的投资研究演进与 Vault 数据库

**>>**: 好的，谢谢。噢，翻页了。首先，我先简要介绍一下桥水基金是谁、我们做什么，然后我们将深入探讨我们是如何使用 Turbo Puffer 的以及相关的需求。

在过去的 50 年里，桥水基金一直在追求对市场和经济运作机制的最佳理解。随后，我们通过逻辑系统化地将其编码到一个系统中，以便随着时间的推移对其进行压力测试。

大家在左侧黄色便签本上看到的，是我们 1980 年的债券系统。它是一组条件语句（if-then statements），当时我们就是用它来进行债券交易的。

在随后的几十年中，我们将这一过程从黄色便签本演变为 Excel，随后变为 Scala，现在则是 Python……演进为了一个以人类为中心的不同学习过程。

这个我们称之为“研究环”（research circle）的流程包含五个步骤：
- 感知（Perception）：观察外部世界正在发生的事情；
- 假说（Hypothesis）：提出解释其成因的想法；
- 调查（Investigation）：进行研究以验证该想法是否属实；
- 如果属实，我们就会将其系统化并整合进我们的系统；
- 然后工业化运作，每天运行并据此进行交易。

这就是我们的学习过程。我在桥水工作了大约 20 年，这 20 年来我们一直都在以人类为中心进行这样的操作。

现在，我们正朝着将机器置于中心并驱动该过程的方向迈进。

为了让这套流程——无论是对人类还是对机器——顺畅运作，我们需要获取高质量的数据。

我们需要时间序列数据，在这方面我们花费了数十年的时间打造了一个非常优秀的双时态宏观时间序列数据库，我们称之为 Delorean。

最近，我们一直在构建一个非结构化数据库，我们称之为 Vault。

那么，Vault 到底是什么呢？

如今，它包含了大约 1 亿份文档，我们对它们进行索引、组织和安全保护。我们认为它代表了一些最顶级的第三方外部研究以及我们的内部研究成果。我们接入了 135 个不同的外部数据源，要将它们实际谈判并引入进来，对法务和我们的数据团队来说都是一件大事。所有这些数据源都附带有某种权限限制，可能并不是面向桥水基金的每个人开放的。

当然，我们还有内部的非结构化数据源。这包括我们自己的撰写材料、会议录音以及内部报告等。

这些数据都会进入 Vault，随后人类投资者和我们的 AI Agent 都会从 Vault 中读取数据。

我这里尚未展示的是，实际上它是一个闭环。投资者和 Agent 会产生新的内容，这些内容又会重新存入 Vault。

因此，它是在持续不断改进的。

这里是 Vault 中权限机制的一个非常高层级的概览。

假设我有一个用户，其 ID 为 user1。他们属于 B 组和 C 组。不幸的是，这已经是经过极大简化的展示了。

而我们所有的文档集合中，文档可以通过群组或者直接授予的方式赋权给他们。

这里是我们实际用于执行查询的代码，尝试使用与查看者和群组相匹配的任意查询向量去检索数据。

这在某种程度上很简单。事实上，当我们最初在没有使用 Turbo Puffer 的情况下实现它时，我们以为效果还不错。但很快，随着我们开始向 Vault 中添加越来越多的文档，它彻底崩溃了。

于是我开始寻找其他可能的服务商。

我们找到了 Turbo Puffer 并对其进行了测试，他们给出了一个解决方案，Nikhil 现在就来为大家做详细介绍。
<details><summary>Original English</summary>
**>>**: Great. Thank you. Oh. There we go. So, first I'm going to go talk a little bit about what who Bridgewater is, what we do, and then we get into how how we're using Turbo Puffer and and the needs there.

So, for the past 50 years, we at Bridgewater have pursued the best understanding of how markets and economies work. We then encode that systematically with logic into a system that we can then stress test over time.

What you see here are on the on the left with the yellow legal pad, that is our bond system from 1980. It's a set of if-then statements that we used to trade bonds back then.

Over the next few decades, we've evolved that process from a yellow legal pad to Excel to eventually Scala and now Python um to to a different learning process with humans at the center.

This five This research circle, as what we call it, has five steps. Perception, that's seeing what's going on the outside world. Hypothesis, which is coming up with ideas of why that might be true. Investigation, which is the research of seeing is that thing true. If it is true, we then systematize and integrate it with our system and industrialize and run that every day and trade on that. That's been our learning process. I've been at Bridgewater for about 20 years. That's been what we've been doing doing for 20 years with humans at the center.

We're now moving towards putting machines at the center and running that process.

In order for even you know, for both humans and machines, in order for that to work well, we need access to high-quality data.

We need both time series data, which we spent decades uh decades creating a great bi-temporal time macro time series database, which we call Delorean.

And more recently, we've been creating a unstructured database, which we call the Vault.

And so, what is the Vault?

Um today, it's about 100 million documents, which we index, organize, and secure that we think represents some of the best third-party and extra third-party external research, and also our internal research. So, we've sourced with 135 different external sources, which is a huge deal for both legal and our data team to actually nego- negotiate and get them in. And all of all of those sources have um some sorts of permissions around it where it might not be open to everyone at Bridgewater.

And then, of course, we also have our inter- internal sources of unstructured data. That's our own writing, our meeting recordings, and and our internal reports, as well.

And both that those all go into the Vault, and then both humans investors and our AI agents read out of the Vault.

What I haven't shown here is actually it circles back. So, the investors and and the agents will create new new content that goes back into the Vault.

So, it's constantly improving.

And so, here's a very high-level view of what permissions in the Vault look like.

So, I have a user we'll just say their ID is user one. They're in groups B and C. This is incre- incredibly simplified, unfortunately.

Um and there's a set of all of our documents where it could be either um uh permission to them via groups or directly.

And then, here we have the actual code of us going ahead and creating a query to try to look for some data with whatever that query vector was that matches the viewers and groups. And so, this is simple in one way. And actually, when we first implemented this without Turbo Buffer, we thought it worked fine. Um but then, pretty quickly, as we started to add more and more documents to the vault, it fell over um tremendously. And so, what I did then was I looked for other possible providers.

We found Turbo Buffer, tested them out, and they had a solution which Nikhil is going to go over right now.
</details>

### TurboPuffer 的架构与搜索成本估算

**>>**: 太棒了，谢谢你，Aaron。

请允许我快速介绍一下 Turbo Puffer 是什么。我们是一个完全构建在对象存储之上的、速度极快、可扩展性极高且成本极其低廉的搜索引擎。这意味着我们直接写入 S3、GCS 或 Azure Blob Storage，取决于你的超大规模云服务商提供什么。

这为我们带来了 S3 级别的经济性。因此，默认情况下，你的数据在 S3 上是静态且冷态的。只有当你开始对其进行查询时，我们才会将其拉入更昂贵的存储介质中，例如 SSD 或内存。这非常强大，因为一旦某个查询变热，一旦该查询访问的数据进入了缓存，它的速度就非常快。

但如果你没有访问特定的命名空间或某个命名空间的特定区域，那么这些数据就只需要保留在对象存储上，你只需为其支付极低的价格。因此，这种架构使得 Turbo Puffer 能够以极低的成本扩展到数 TB 的数据；而在其他系统中这可能需要花费数千万美元，而我们通常能以十分之一的成本实现，并且在数据变热后，其性能与传统基于磁盘的搜索系统相当。

我们支持所有类型的搜索：支持关键词搜索、正则搜索，以及 Aaron 刚才展示的向量搜索。

因此，对于在 Turbo Puffer 中如何搜索数据，我们并没有固定的偏好，我们希望提供通用的检索能力。

但在接下来的演讲中，我将重点关注向量搜索，因为深入探讨一种特定的搜索类型是有益的。

我们来进行一点简单的粗略估算（napkin math）。这是我们在 Turbo Puffer 非常喜欢做的事情，它有助于我们锚定在尽可能最简单的解决方案上。我们绝不想向 Turbo Puffer 引入不合理的复杂性。承担复杂性的合理理由之一就是性能所需。

进行搜索绝对最简单的方法就是把所有内容放在一个列表中，每次有人过来说：“我想找匹配这个的内容，我想要匹配此查询的文档”，你就去扫视每一条数据。

保守起见，我们假设你在 Turbo Puffer 中存储的每份文档大小为 1 KB。这是一个极其保守的估计。一个向量嵌入通常有 1024 个维度，如果每个维度仅使用一个字节，那就是 1 KB。在实际应用中，文档通常比这更大。但为了举例说明，我们假设每份文档 1 KB。

即使你将所有这些数据都常驻在内存中，并且以最快的速度去处理它——在现代硬件上大约是每秒 20 GB。

一旦文档数量达到 1 亿份，这将需要 5 秒钟。对于大多数搜索工作负载而言，这都太慢了。在实际应用中，我们看到大多数人希望其搜索结果能在大约 100 毫秒内返回。

因此，这里的简单方案是行不通的。如果你只有 1 万份文档，那没问题，只需要半毫秒。Turbo Puffer 怎么做都能足够快。但随着规模扩大，一旦达到 1000 万或 1 亿份文档，你就真的需要开始考虑如何表达你的数据，从而避免对所有数据进行全量遍历。

当然，我刚才给出的还只是内存中的数据。那还只是在缓存处于热态的情况下。如果这些数据存放在 S3 上，要从 S3 拉取这些数据需要一分钟甚至更久。因此，在桥水基金的业务规模下，这种做法根本行不通。
<details><summary>Original English</summary>
**>>**: Awesome. Thank you, Aaron.

Let me very quickly talk about what Turbo Buffer is. We are an extremely fast, extremely scalable, extremely cheap search engine built entirely on top of object storage. And what that means is we write directly to S3 or GCS or Azure Blob storage, whatever your hyperscaler provides.

And that gives us S3 economics. So, by default, your data is inert, cold on S3. Only when you start querying it do we pull it into more expensive storage mediums, like SSD or memory. And this is really powerful because once a query is hot, once the data query is accessing is in the cache, it's fast.

But if you're not accessing a particular namespace or a particular region of a namespace, that data can just hang out on object storage where you pay rock-bottom prices for it. So, this architecture allows Turbo Buffer to scale cheaply to terabytes of data, which would cost tens of millions of dollars in in other systems, and we can often do it at a tenth of the cost at performance that's comparable once you get the data hot uh to what you get with traditional disk-based search systems.

And we support all types of search. We support keyword search. We support regex search. And what Aaron was showing earlier, vector search.

Um so we're really not uh opinionated about how you search your data in Turbo Puffer. We want to do search generically.

But for the rest of this talk, I'm going to focus on vector search because uh it's it's good to zoom in and go deep on one particular type of search.

Let's do a little bit of napkin math. That's something we love to do at Turbo Puffer. It helps us anchor in the simplest possible solution. We never want to introduce complexity to Turbo Puffer that's not justified. One of the justifications for taking on complexity is if you need it for performance.

The absolute simplest way to do search is to put everything in a list and every time somebody shows up saying, "I want queries that match this. I want documents that match this query." You look at every single piece of data.

Let's conservatively say that every document that you store in Turbo Puffer is 1 kilobyte. This is incredibly conservative. A vector embedding is often 1,024 dimensions. So if you're using just a byte per dimension, that's a kilobyte right there. Uh in practice, documents are often larger than this. But for the sake of example, let's say it's a kilobyte per doc.

Even if you had all of that data resident in memory and you were ripping through it as fast as you possibly could, which on modern hardware is about 20 gigabytes a second.

Once you get up to 100 million docs, that's going to take 5 seconds. And for most search workloads, that's way too slow. What we see in practice is most people want their search results to be about 100 milliseconds. [clears throat]

So the naive solution here does not work. If you've only got 10K docs, great. That's going to take half a millisecond. Turbo Puffer can do literally anything and it will be fast enough. But as you get to scale, once you're at 10 million or 100 million, you really need to start thinking about how you represent your data so that you're not crunching through all of that.

And of course, I gave you the the numbers for memory here. That's only if the cache is hot. If that data's on S3, you're looking at a minute or more to pull that data off S3. So, this just isn't viable at the scale that Bridgewater operates.
</details>

### 向量索引原理与权限过滤困境

**>>**: 所以，Turbo Puffer 的第一步就是构建向量索引。这是我们在底层自动为您处理的事情。当你在 Turbo Puffer 中存储向量时，一旦数据量达到一定规模，我们就会在后台自动构建该索引。

如果你还不熟悉的话，向量嵌入（Vector embeddings）是 LLM 空间中概念的内部数值表示。我们喜欢用“红鞋”（red shoes）和“栗色凉鞋”（maroon sandals）这个例子。作为人类，你知道这些是非常相似的概念，它们彼此之间的相似度要远远高于与“混凝土块”（concrete block）的相似度。你可能会联想到形状、大小、质地和重量等。

LLM 可以将其转换为这种数值向量。在这里我只展示了两个维度，以便我们可以从二维的角度来思考，但在实际中通常有数千个维度。1024 维是一个非常常见的尺寸。进行如此多维度的思考是非常困难的，因此为了举例说明，我们假设这里只有两个维度。

现在，我们实际上并不知道这些维度代表什么，但同样，你可以将其想象为大小和颜色。然后你可以在坐标系上标绘出来。因此，“红鞋”可能与“栗色凉鞋”一起位于左上方，而“混凝土块”则会位于右下方。
<details><summary>Original English</summary>
**>>**: So, step one in Turbo Puffer is to build a vector index. And this is something that we handle under the hood for you. When you store vectors in Turbo Puffer, we automatically build this index behind the scenes once you get enough data to to justify it.

Vector embeddings, if you're not familiar, are the internal numeric representation of concepts in LLM space. And we like to use this example of red shoes and maroon sandals. You as a human know that these are very similar concepts and much more similar to one another than concrete block is. And maybe you're thinking about shape and size and texture and and weight.

The LLM can translate that into this numeric vector. Here, I've only got two dimensions shown so that we can think two-dimensionally, but in practice, there's often thousands of dimension. 1024 dimensions is a very common size. Thinking multi-dimensionally like that is very hard. So, for the sake of example, we're just going to imagine that there are two dimensions here.

Now, we don't actually know what those dimensions represent, but again, you can think of it as like size and color. And then you can plot that on a coordinate system. So, red shoes might be at the top left along with maroon sandals, and then concrete block is going to be down at the bottom right.
</details>

**>>**: [嗤笑]
<details><summary>Original English</summary>
**>>**: [snorts]
</details>

**>>**: 接下来我要做极其粗略的简化，但在二维空间中，一个非常可行的向量索引就是把事物标绘在图表上。然后你可以放大查看。如果你在寻找“红鞋”——也就是此图中的 Q——你把它标绘在这个二维图表上，放大，并寻找它周围的向量。由于这些向量是由 LLM 创建的方式，彼此相近的向量代表相似的概念，代表应该返回的良好搜索结果。

因此，如果我们只是做相似度搜索，那就太好了。我们在二维坐标网格中查找，找到一些附近的向量，将它们返回，一切顺利。

这为我们节省了大量时间。我们不必搜索整个向量空间。我们可以直接聚焦到与查询相关的文档上。因此，刚才那番粗略估算就可以忽略了。我们在这里可能只需要查看 10,000 个向量，并且我们知道这在 1 到 2 毫秒内就能完成。
<details><summary>Original English</summary>
**>>**: And I'm going to simplify wildly here, but a very workable vector index in two dimensions is just to plot things on a graph. And then you can zoom in. If you're looking for red shoes, that's the Q on this diagram, you plot that on this two-dimensional graph, and you zoom in, and you look for the vectors around it. And because of the way these vectors are created by the LLM, vectors that are near each other represent similar concepts, represent good search results to return.

So, if we were just doing similarity search, great. We look in our two-dimensional coordinate grid, we find some nearby vectors, we return them, and life is good.

And this saves us a lot of time. We don't have to search the whole vector space. We can zoom right in to the documents that are going to be relevant to the query. So, that napkin math from earlier, we can we can ignore. We're maybe only looking at 10,000 vectors here, and we know we can do that in a millisecond or two.
</details>

**>>**: [嗤笑]
<details><summary>Original English</summary>
**>>**: [snorts]
</details>

**>>**: 问题在于，当你引入这些权限设置时，对于给定的查询，并非所有最相关的文档都符合这些权限。大家可以在这张图表中看到，减号表示不符合权限，而加号表示符合权限。

因此，我们的向量索引无法立即发挥作用。在 Turbo Puffer，我们投入了大量时间和精力来解决这个问题。

从直觉上，你可能会尝试“后过滤”（post-filtering）策略。

它的工作方式是：当查询到来时，你可能获取最近的 10,000 个向量，然后将所有不符合权限的向量丢弃。

这种方法效果并不好，因为它无法提供你想要的结果。如果我是那个只能访问右下角数据的用户，并且我搜索 Q，我仍然希望看到从我的视角来看最接近 Q 的文档，也就是包含我能看到的结果。

但是当你做后过滤时，你大致是向外螺旋式扩展搜索，然后在某个节点你不得不放弃，因为已经过了两三秒你还没有找到任何匹配的文档，或者你没有找齐最匹配的前 100 篇文档，可能你只找到了 40 篇。这会让用户很不满意，因为他们可能明确知道存在一篇包含“栗色凉鞋”的文档，而他们搜索的是“红鞋”，你却没有将其呈现出来。因此，你的召回率（recall）非常差。

那么，与其从向量索引开始，如果我们从过滤器开始呢？

Turbo Puffer 会为所有符合过滤条件的文档构建索引。因此，Aaron 可以过来说：“嘿，把我拥有访问权限的所有文档展示给我。”

然后 Turbo Puffer 可以扫描所有这些文档，看看其中哪些距离查询向量最近。

但如果 Aaron 拥有 Vault 中 1 亿份文档中 5000 万份的访问权限呢？现在我们又回到了原点。我们又回到了那个粗略计算的问题中：需要耗费数秒甚至数分钟才能处理完全部数据。我们实际上并没有利用到向量索引。如果大家看这里，就会发现我们只是找出了所有匹配过滤器的文档，然后按顺序依次扫描它们。所以，这种做法效果也很差。
<details><summary>Original English</summary>
**>>**: The problem is when you add in these permissions, not all of the documents that are most relevant for a given query are going to match those permissions. And you can see in this diagram here, the minuses don't match the permissions, while the pluses do match the permissions.

So, our vector index is not immediately helpful to us. And we've invested a lot of time and energy at Turbo Puffer into solving this problem.

Naively, you might try a post-filtering strategy.

And the way that works is the query comes in, you get maybe the 10,000 closest vectors, and then you throw away all the ones that don't match.

This does not work very well because it doesn't provide the results that you're looking for. If I'm the user that only has access to that data in the bottom right, and I search for Q, I still want to see the documents that were closest to Q from my perspective, that include the results that I can see.

But when you do post-filtering, you kind of spiral outwards, and then at some point you have to give up because it's been a couple seconds and you haven't found any docs that match, or you haven't found the top 100 docs that match. Maybe you were only able to find 40. And this makes users unhappy because they might know that a doc exists with maroon sandals, and they were searching for red shoes, and you don't turn it up. So, you have very poor recall.

So, instead of starting with the vector index, what if we start with the filters?

Turbo Puffer builds an index of all of the documents that match the filters. So, Aaron can show up and say, "Hey, show me all of the documents that I have access to."

And then Turbopuffer can scan over all of those documents and see which of them are closest to the query vector.

But what if Aaron has access to 50 million out of the 100 million documents in the vault? Now we're back to square one. We're back in that napkin math problem where it's going to take multiple seconds, if not minutes, to get through all of that data. We're not actually using the vector index. If you look here, you can see we're just finding all the docs that match the filters and then scanning through them sequentially. So, this also doesn't work very well.
</details>

### 原生过滤方案与大规模检索表现

**>>**: 解决好这个问题的绝妙之处在于“两者兼顾”。

因此，Turbo Puffer 的向量索引会自动对相似的向量进行聚类。你可以看到这里有一组相似的文档标记为 5，另一组标记为 0，还有一组标记为 1。

当我们构建这些权限索引时，我们会说：“嗯，Aaron 可以访问聚类 5 中的文档，也许还可以访问聚类 2，但他无法访问聚类 3 中的任何文档，也无法访问聚类 0 中的任何文档。”因此，我们可以直接丢弃那些聚类，根本不需要考虑它们。

所以，我们首先找到 Aaron 拥有访问权限的所有聚类——即他在这些聚类中至少对一份文档拥有访问权限——然后我们搜索最近的聚类，接着仅在这些聚类内部按顺序进行扫描。目前在 Turbo Puffer 中，每个聚类大约包含 200 份文档。这是我们一直在调优的参数。随着时间的推移，我们可能会增加这个数值以最大化吞吐量。但这种基本策略从根本上使大规模带权限的搜索成为可能。

这里的关键诀窍就是将预过滤和后过滤结合为我们所谓的“原生过滤”（native filtering）。

结果就是：在 4.5 亿个向量的规模下——那 1 亿份文档转化为了 4.5 亿个向量——通过采用这种精细的原生过滤策略，Turbo Puffer 能够实现 120 毫秒的检索速度。这是覆盖所有这些命名空间的 P90 延迟。

所以，使用 Turbo Puffer 时，你带着你的权限逻辑和概念模型前来，然后进行我认为非常简单的转换，将这些权限转换为 Turbo Puffer 的过滤语言。希望大家可以直接对应这里的代码示例：`viewers contains 1`，`groups contains any [B, C]`。希望你能看到如何将其投影到你自己组织的权限结构上。

这在底层转化为非常复杂的系统工程挑战，但 Turbo Puffer 将这一切完全对你隐藏了起来。

这样你就不必为此费心。你只需要以相当直接的方式表达代表你权限的逻辑过滤器即可。

我们在底层处理复杂的查询规划，使得即使在 1 亿文档的规模下，检索也能在 100 到 200 毫秒内返回。

现在，作为 Turbo Puffer 的工程师，我们深知这里仍然存在一些局限性。特别是当遇到嵌套群组时，情况会变得棘手。我没有足够的时间去深入讨论这些细节，但如果你遇到了类似的问题，请随时来找我们交流。我们在处理这些问题方面有丰富的经验，并且一直在寻找改进产品的方法，以便让这些场景能够更加自动化地被处理。

所以，权限过滤在 Turbo Puffer 中其实只是冰山一角。我们正在努力构建一个“原生隔离”（isolation-native）的搜索引擎。这意味着无论是在命名空间内部拥有细粒度权限，还是面临迫使你必须进行区域数据锁定的安全与法规合规义务、将数据保留在你自己的 VPC 内、不仅使用你控制的密钥进行加密，甚至使用你自己客户控制的密钥进行加密。

Turbo Puffer 针对所有这些级别的隔离都提供了解决方案。因此，权限过滤只是在 Turbo Puffer 中构建隔离感知搜索的其中一块拼图。

以上就是我们的全部内容。这就是 Turbo Puffer 与桥水基金如何通力合作，在 1 亿规模下实现快速的原生隔离检索。

谢谢大家。
<details><summary>Original English</summary>
**>>**: And the trick to doing well on this problem is to do both.

So, Turbopuffer's vector index automatically clusters similar vectors. So, you can see there's a group of documents here that are similar labeled five and another group labeled zero and another group labeled one.

And when we build these permissions indexes, we say, "Well, Aaron has access to documents in cluster five and maybe cluster two, but he doesn't have access to any documents in cluster three or any documents in cluster zero." So, we can just throw those clusters out. We don't have to consider them at all.

So, first we find all of the clusters that Aaron has access to, uh i.e. he has access to at least one doc in those clusters, and then we search the closest clusters, and then we just scan sequentially inside those clusters. And in Turbopuffer right now, the clusters have about 200 documents. This is something we're always tuning. Over time, we'll probably increase that number to to maximize throughput. But this basic strategy fundamentally makes search at scale with permissions possible.

And the trick is to combine pre- and post-filtering into what we we native filtering.

And this is the result.

Across 450 million vectors, those 100 million documents turn into 400 million vectors, TurboPuffer is able to get 120 millisecond searches. That's the P90 latency across all of those namespaces. By employing this sophisticated native filtering strategy.

So, with TurboPuffer, you show up with your permissions logic and your conceptual model, and you do what I think is a very simple translation of those permissions into TurboPuffer filter language. And hopefully, you can directly map this code sample here, viewers contains ones viewers contains one groups contains any BC. Hopefully, you can see how you would project that onto your organization's own permission structure.

And that turns into this very complicated systems engineering challenge under the hood, but TurboPuffer hides that all away from you.

So that you don't have to think about it. You can just express the logical filters that represent your permissions in a fairly direct way.

And we handle the complicated query planning under the hood to make that search come back in 1 to 200 milliseconds even at 100 million documents scale.

Now, we're engineers at TurboPuffer, so there are some limitations here. In particular, when you have nested groups, things get tricky. I'm not going to have time to go into that in too much detail, but if you have problems that look like that, please come talk to us. Uh we have a lot of experience working through these, and we're always looking for ways to improve the product so that stuff is handled more automatically.

So, permission filters are really just the tip of the iceberg in TurboPuffer. We're trying to build an isolation native search engine. That means whether you have fine-grained permissions within namespaces, whether you have security, regulatory compliance obligations that force you to regionally lock data, keep that data in your own VPC, encrypt that data potentially not just with an encryption key you control, but that your own customers control.

Turbo Buffer has solutions for all of those levels of isolation. So, permission filtering is just one piece of the puzzle in building isolation-aware search in Turbo Buffer.

So, that's all we got. That's how Turbo Buffer and Bridgewater work together to do fast isolation-native search at 100 million scale.

Thank you, everyone.
</details>

**>>**: [掌声]
<details><summary>Original English</summary>
**>>**: [applause]
</details>