---
author: Latent Space
date: '2026-03-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Iu4gEnZFQz8
speaker: Latent Space
tags:
  - vector-database
  - database-architecture
  - retrieval-augmented-generation
  - search-engine
  - talent-density
title: 搜索的未来：Agent、RAG 与为何检索依然至关重要——访 Turbopuffer 创始人 Simon Eskildsen
summary: 本次访谈深入探讨了 Turbopuffer 的诞生背景及其创新的数据库架构。创始人 Simon Eskildsen 分享了他在 Shopify 扩展 Elasticsearch 的痛苦经历，以及如何利用 S3 的强一致性与 NVMe SSD 构建高性能、低成本的向量与全文搜索引擎。他还详细讲述了为 Cursor 和 Notion 优化 RAG 成本的故事，并提出了“P99 工程师”的招聘哲学。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Turbopuffer
  - Shopify
  - Readwise
  - Notion
  - OpenAI
  - AWS
  - Google Cloud Platform
products_models:
  - Elasticsearch
  - Cursor
  - S3
  - Lucene
  - PostgreSQL
media_books: []
status: evergreen
---
### 丹麦程序员黑手党与背景

**Simon Eskildsen**: 我以前没公开说过这个，但我私下把 Lucky（投资人）称为“本地的 Lucky”。就像是，如果到今年年底这东西还没达到 **PMF**（产品市场匹配），我们就把钱全部退还给你，因为我不想继续做这个了。我真的想在今年全力以赴。我们会雇佣一群非常诚实的人。当我不知道怎么玩一场游戏时，我喜欢明牌玩。Lucky 是唯一一个没有因此被吓跑的人。

<details>
<summary>Original English</summary>

**[Speaker 1]**: i don't think i said this publicly before, but i just call lucky was like local lucky. like if this doesn't have PMF by the end of the year, like we'll just like return all the money to you just saying that i don't want to work on this. i'm less into really working. so we want to give it the best shot this year. and i we're really going to go for it. we're going to hire a bunch of people who were going to be honest with everyone, like when i don't know how to play a game. i just play with open cards. lucky was the only person that didn't that didn't freak out.

</details>

**Swyx**: 他当时觉得“我从没听人这么说过”。欢迎大家来到 **Latent Space** 播客。我是 Alessio，我是 Shawn。

<details>
<summary>Original English</summary>

**[Speaker 2]**: he was like i've never heard anyone say that before. everyone welcome to the latent space podcast. this is alessio on their kernel, and i'm shawn wang at latent space.

</details>

**Alessio**: 我们第一次在 Kernel 工作室录音，非常兴奋。今天我们邀请到了 **Simon Eskildsen**，**Turbopuffer** 的创始人。非常感谢你的到来。我必须提一下，你是“**丹麦程序员黑手党**”的一员，那个群体诞生了许多传奇程序员，比如 Bjarne Stroustrup（C++ 之父）、Anders Hejlsberg（C# 之父）等。你现在主要在加拿大，但丹麦人的存在感真的很强。

<details>
<summary>Original English</summary>

**[Speaker 3]**: so so they recording in the kernel studio for the first time, very excited. and today, we're joined by simon eskildsen, founder of turbopuffer. thank you so much for having me. and i do have to mention that like you are one of you're not my US member, the danish coders mafia, where like there's a lot of legendary programmers have come out of it like bjarne stroustrup, rasmus lerdorf, anders hejlsberg. and the V8 team and google maps team. you're mostly a canadian now, but is it not interesting? there's so much like strong danish presence?

</details>

**Simon Eskildsen**: 是的，我不久前写过一篇关于影响因素的文章。我在丹麦长大，18岁离开去加拿大加入 **Shopify**。所以我仍然觉得自己更像丹麦人。丹麦有一种极度的**实用主义**，同时也非常注重美学。

<details>
<summary>Original English</summary>

**[Speaker 1]**: yeah, i was writing a post not that long ago about sort of the influences. so i grew up in denmark. i left it when i was eighteen to go to canada to to work at shopify. um and so i would still say that i feel more danish than than canadian. this is also the weird accent. i can say TH, because this is like that. i don't you know, my wife is also canadian. um and i think i think like one of the things in in denmark is, like there's just such a ruthless pragmatism. and there's also a big focus on just aesthetics like they're like very people really care about like where what things look like.

</details>

### 什么是 Turbopuffer？

**Alessio**: 让我们聊聊 Turbopuffer 的定位。有些圈子认为它是一个 **Vector DB**（向量数据库），或者是一个搜索层。

<details>
<summary>Original English</summary>

**[Speaker 2]**: i think i would love to get promote the position of turbopuffer, because i think you could be a vector DB, which maybe a bad word now on some circles, you could be a search engine like let's start there. and then will maybe run through the history of how you get to this point.

</details>

**Simon Eskildsen**: 在现阶段，Turbopuffer 是一个**搜索引擎**。我们做全文搜索和向量搜索，这是我们的专长。你可以把世界上所有的知识、海量的数据压缩成几个 TB 的权重来训练模型，但模型必须连接到外部的、真实的、高保真的数据源。我们现在的核心目标就是成为**非结构化数据**的搜索引擎。

<details>
<summary>Original English</summary>

**[Speaker 1]**: for sure. yes, a turbopuffer is at this point in time a search engine, right? we do full text search and we do vector search. and that's really what we're specialized. then if you're trying to do much more than that, then this might not be the right place yet. but turbopuffer is all about search. the other way that i think about it is that we can take all of the world's knowledge, all of the exabytes and exabytes of data that there is. and we can use those tokens to train a model, but we can compress all of that into a few terabytes of weights, right? how to reason with the world, how to make sense of the knowledge, but we have to somehow connect it to something external. it actually holds that like in full fidelity and truth and that's the thing that we intend to become right. being the search engine for unstructured data is the focus of turbopuffer at this point in time.

</details>

### 构建顶级数据库公司的三个条件

**Swyx**: 人们可能会问，**Elasticsearch** 不是已经在做这些了吗？这和 RAG 有什么区别？

<details>
<summary>Original English</summary>

**[Speaker 2]**: and let's break them. so people may say, well, then an elasticsearch already do this. and then some other people may say, is this search on my data? is this like closer to rag? and it's like a public search thing, how do you segment like the different types of search?

</details>

**Simon Eskildsen**: 我认为要建立一家伟大的数据库公司，需要三个条件，而且通常每 15 年才发生一次。
第一，需要一种**新工作负载**（New Workload）。比如 **Oracle** 时代，或者 15 年后的 **Snowflake** 和 **Databricks**。现在的趋势是：每家公司都需要将海量数据连接到 AI。
第二，需要**底层存储架构**的根本性变革。Snowflake 时代是利用廉价的 HHD 集群和 S3。现在的机会是全速拥抱 **NVMe SSD** 和云原生对象存储，这种架构很难在旧数据库上改造。
第三，随着时间的推移，数据库必须能够支持几乎所有的查询计划。你不能只停留在单一的功能上。

<details>
<summary>Original English</summary>

**[Speaker 1]**: the way that i generally think about this is like there's a lot of database companies. and i think if you want to build a really big database company, sort of you need a couple of ingredients to be in the air and it only happens roughly every fifteen years. you need a new workload. you basically need an ambition that every single company on earth is going to have data in your database multiple times. you look at a company like like oracle, snowflake and databricks. fifteen years later, there is not a company on earth that doesn't indirectly or directly is consuming snowflake or databricks. and i think you're in that kind of moment now. you're going to find a company over the next few years that doesn't directly indirectly have all their data available for search and connected to AI. so you need that new workload. the second thing you need is some new underlying change in the storage architecture that is not possible from the databases that have come before you. the architecture is now possible that wasn't possible fifteen years ago is to go all in on NVMe SSDs, a particular type of architecture for the database that is difficult to rather fit onto the databases that are already there. the second thing is to go all in on object storage. if someone has data in the database, they over time expect to be able to ask it more or less every question. those are the three conditions.

</details>

### 从 Shopify 到 Readwise 的启发

**Alessio**: 你之前在 Shopify 是首席基础设施工程师，那段经历对你有什么启发？

<details>
<summary>Original English</summary>

**[Speaker 3]**: i just wanted to get a little bit of motivation, right? like so you left shopify you're like principal infra guy. and then you consulted for readwise. and it kind of give you that idea. i just want to you to tell that story.

</details>

**Simon Eskildsen**: 我在 Shopify 待了近十年。我们经历了从自己的数据中心迁移到云端的过程，做了大量的**分片**（Sharding）工作。当时最让我痛苦、最难扩展的数据库就是 Elasticsearch。我看到很多项目的雄心壮志都被它限制住了。离开 Shopify 后，我做了一段时间的“天使工程”（Angle Engineering），帮朋友的公司解决基础设施问题，**Readwise** 就是其中之一。
当时 **ChatGPT** 刚火，我想为 Readwise 的阅读器做一个推荐引擎。虽然效果很好，但当我算了一下成本：如果要把所有文章做向量嵌入并存入向量数据库，一个月要花 3 万美元，而他们整个基础设施的预算才 5 千美元。这在商业上完全不可行。这件事一直困扰着我，我在想：如果有办法把成本降低到十分之一，这个功能就能上线了。

<details>
<summary>Original English</summary>

**[Speaker 1]**: for sure. so yeah, i spent almost a decade at shopify. i was on the infrastructure team from the fairly early days around 2013. the database that was the most difficult for me to scale during that time and that was the most aggravating to be on call for was elasticsearch. it was very, very difficult to deal with. and i saw a lot of projects that were just being held back in their ambition by using it. so i left, and i decided i was going to, i call it like angle engineering, where i just hopped around my friends' companies for three months and just help them out and solved some interesting infrastructure problem. readwise was one of them. i built a small recommendation engine. it was good enough that when i ran it on one of the co founders, i found out i got articles about having a child. but the company was spending maybe five grand a month in total on all their infrastructure. and when i did the napkin math on running the embeddings of all the articles putting them into a vector index, it's going to be like thirty grand a month. that just wasn't tenable. if the cost had been a tenth, we would have shipped that. and that haunted me.

</details>

### 对象存储与 S3 的强一致性

**Simon Eskildsen**: 于是我开始研究。当时大家都在热炒向量数据库，但我完全不懂那是啥。我坐下来，用我的“**草稿纸计算**”（Napkin Math）估算了一下：DRAM 的带宽是 25GB/s，NVMe SSD 写入是 5GB/s。为什么没人做一个完全基于对象存储的数据库呢？
当数据被使用时，把它拉到内存。唯一的缺点是每次写入会有几百毫秒的延迟，但除此之外全是优点。在 2020 年 12 月，**S3** 终于支持了**强一致性**（Strong Consistency），这是一个重大的转折点。在那之前，你可能需要 **Zookeeper** 或 **FoundationDB** 来管理元数据，但现在你完全可以直接把元数据写在 S3 里。

<details>
<summary>Original English</summary>

**[Speaker 1]**: i couldn't help myself like i didn't know what like a vector index is. i sat down. i have this napkin math. why wasn't anyone build the database, you just put everything on object storage. and then you pull it into DRAM when you use the data. this seems fairly obvious. and actually S3 only became consistent in december of 2020. so now it means you don't have to have like big foundation DB, or like zookeeper, whatever sitting there contending with the keys. snowflake and others have to do it exactly just gone, right?

</details>

**Alessio**: 所以你不再需要共识层（Consensus Layer），直接依赖 S3。

<details>
<summary>Original English</summary>

**[Speaker 3]**: when you say consensus layer, you strongly relying on S3, strong consistency, you are okay. so that is your consensus layer.

</details>

**Simon Eskildsen**: 没错。但当时 S3 还不支持 **Compare-and-Swap** (CAS)。我们在 **GCP** 上开始做，因为 GCP 支持这个特性。后来为了拿下 **Notion** 这个大客户（他们跑在 AWS 上），我们甚至在俄勒冈州的 AWS 区域和 GCP 区域之间买了**暗光纤**（Dark Fiber）来降低跨云延迟，因为我们坚持不使用有状态的共识系统，也不想凌晨 3 点被 Zookeeper 的报警吵醒。

<details>
<summary>Original English</summary>

**[Speaker 1]**: it is the layer. so what compare-and-swap allows you to do is basically just download the file, you make the modifications, and then you write it only if it hasn't changed while you did the modification. that primitive was not available in S3 until late 2024, but it was available in GCP. we got really lucky, and we started on GCP because shopify ran on GCP. and when we started building the database, we really thought we had to build a consensus layer, like have a zookeeper. but then we discovered the compare-and-swap. we were closing deals with notion, actually, that was running in AWS and we were like trust us. you really want us to run this in GCP. and we had so much conviction that we bought dark fiber between the AWS regions in oregon and GCP. i don't want state in two systems. the worst outages are the ones where you have state in multiple places that not syncing up.

</details>

### 与 Cursor 的故事

**Alessio**: **Cursor** 也是你们的大客户。

<details>
<summary>Original English</summary>

**[Speaker 3]**: they were really our biggest our second big customer after cursor, which also was a lot of late nights. right?

</details>

**Simon Eskildsen**: 是的。Cursor 的团队非常硬核。那是 2023 年底，有一天凌晨 4 点，他们的创始人发邮件问我能不能开个会。我当时在东海岸，早上 7 点起床回复。我去了旧金山他们的办公室，当时他们的 **PostgreSQL** 挂了，我在那里帮他们调优数据库。
后来他们把所有的向量搜索都迁移到了 Turbopuffer，我们将他们的**成本降低了 95%**，这彻底解决了他们“每个用户的经济模型”问题。Cursor 会对整个代码库做嵌入，他们有自己的嵌入模型，对安全性要求极高。

<details>
<summary>Original English</summary>

**[Speaker 1]**: the way that i remember it was that the day after after relaunch, i was just locked in on building it. one of the cursor co-founders reached out. they just speak in bullet points. so many, many TBs we have. this is what we're paying. i went over the office. postgreSQL was down. i was trying my best to see if i could help. they migrated everything over the next week or two, and we reduced their cost by ninety five percent, which i think kind of fixed per user economics. cursor is code a different workload than normal text. they will embedding entire codebase. they have their own embedding model.

</details>

### P99 工程师与招聘哲学

**Alessio**: 你提到了“**P99 工程师**”的概念。

<details>
<summary>Original English</summary>

**[Speaker 1]**: let's talk about you have this concept of the p99 engineer.

</details>

**Simon Eskildsen**: “P99 工程师”是我们内部用来谈论候选人和构建公司的术语。我们追求极致的**人才密度**。我有一份关于 P99 工程师特质的清单，每次面试后我都会对照。
默认情况下，我们是不雇佣某个人的。只有当团队中至少有一个人愿意为了这个候选人“打一架”（极力争取）时，我们才会录用。P99 工程师有一个特质：他们曾有过“**用意志弯曲计算机**”的时刻，让软件做到了原本认为不可能做到的事。
比如我们的首席架构师 Nathan，他开发的 ANNV3 算法可以在 1.4 毫秒内搜索一千亿个向量。

<details>
<summary>Original English</summary>

**[Speaker 0]**: the p99 engineer was just a term that we started using internally to talk about candidates and talk about how we wanted to build the company. i have a document called traits of the p99 engineer, and it's a bullet point list. i look at that list after every single interview. the default should be we're definitely not hiring this person. i want to see people fight for this person. if one person says it, then okay, let's do it. the p99 engineer has some history of having bent their trajectory or something to their will, some moment where they just made the computer do what it needed to do. our chief architect nathan bent the software to his will. ANNV3 can search a hundred billion vectors with AP50 of 1.4 milliseconds.

</details>

**Simon Eskildsen**: 还有一个有趣的特质：P99 工程师通常喜欢**看地图**。这是一种“武器化的自闭症”（Weaponized Autism），是对某种事物的极致专注。我发现很多顶级工程师都喜欢在手机上漫无目的地翻看地图。

<details>
<summary>Original English</summary>

**[Speaker 0]**: i think another trait is that p99 spends a lot of time looking at maps. generally, it's their preferred UX. this is weaponized autism is what i call it. i love looking at maps. p99 is obsessive.

</details>

### 绿茶、温度与生活哲学

**Alessio**: 听说你对**绿茶**也有这种极致的追求？

<details>
<summary>Original English</summary>

**[Speaker 1]**: you kindly gifted us your favorite. this is from the green tea shop in toronto.

</details>

**Simon Eskildsen**: 没错。我有一张 **Airtable** 表格，记录了我过去 15 年尝试过的数百种茶。我最喜欢的是日本某个小县产的中国风绿茶。
我甚至随身携带一个精密**温度计**。在上周五的团队演示（Demo）中，如果演示的人不够多，我就会花 20 分钟讲解我的茶叶旅行套装和温度监控，作为对大家不演示的“惩罚”。因为绿茶必须在 80 摄氏度冲泡，水烧开了是不行的。

<details>
<summary>Original English</summary>

**[Speaker 0]**: i consume lot of caffeine. i have an airtable table with hundred types of tea i've tried over the past fifteen years. i generally prefer chinese green tea. i have a little travel kit where i bring a thermometer. last friday, when we do demos, i spent twenty minutes walking through my airtable and going through my entire tea travel kit, including the temperature monitor. because you need eighty degrees for it.

</details>

**Alessio**: 今天的访谈非常精彩，Simon，感谢你的分享。

**Simon Eskildsen**: 很高兴来到这里。

<details>
<summary>Original English</summary>

**[Speaker 1]**: thank you so much for having me. it was a pleasure.

</details>