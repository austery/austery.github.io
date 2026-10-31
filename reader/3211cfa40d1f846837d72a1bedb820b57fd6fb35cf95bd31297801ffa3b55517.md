---
author: The MAD Podcast with Matt Turck
date: '2026-05-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=WslkscPp1ro
speaker: The MAD Podcast with Matt Turck
tags:
  - data-pipeline
  - real-time-data
  - ai-integration
  - schema-evolution
  - cdc
title: 实时数据与 AI：Estuary 如何重构企业数据管线
summary: Estuary 首席执行官介绍了其作为“实时数据平台”的理念，该平台融合了批处理与流处理。演讲重点探讨了利用 AI 优化数据管线，包括实时错误诊断、自动化转换、通过提示词自动生成管线，并展示了如何通过 CDC 技术将实时数据同步至 Snowflake、BigQuery 及向量数据库以实现实时 AI 应用。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Estuary
  - Arbor
  - Kafka
  - Snowflake
  - Neon
  - BigQuery
  - OpenAI
products_models: []
media_books: []
status: evergreen
---
### 实时数据平台的定义与架构演进

**Estuary** 作为一个“实时数据平台”（Right Time Data Platform），其核心差异化优势在于能够同时处理**批处理**（Batch）与**流处理**（Streaming）数据。无论是何种数据，平台都能以用户所需的实时速度进行交付。这一平台的构想源于创始团队之前在 **MarTech**（营销技术）领域的公司 **Arbor**。在营销技术领域，尽管看起来不算极具创新，但其对实时数据管线有着强烈需求。为了兼顾实时数据交付与分析报告需求，团队构建了这样一个同时支持流与批处理的架构。这种模式如今在 AI 管线中表现出极佳的适用性，能够实现从任何系统到任何系统的实时数据流动。

<details>
<summary>Original English Source</summary>

I'm the CEO and co-founder of Estuary and we're a right time data platform. And what we mean by a right time data platform is that we are a unique platform that can work with both batch and streaming data. Um so, you know, data at your at your speed whatever you need it. The idea for Estuary came from a previous company that myself and my co-founder made. It was called Arbor and Arbor was in the MarTech space. Um the MarTech space is kind of interesting because you don't think of it as um very new and fresh, but uh it actually has a very strong use case for real-time pipelines. And so we wanted to be able to deliver real-time data to our customers alongside being able to also deliver analytics, reporting, things like that. Um so we ended up building a platform that works for both streaming and batch. And that's a pretty novel thing, right? It It's not something that it really exists today. You know, it turns out that that actually works really well for AI pipelines as well and I'll talk a little bit about that and and how it actually works and what it does. So, let me talk a little bit more about Estuary. I have to remember to stay here. Um Estuary is a as I mentioned a right time data platform. We try to make it possible to get data from any system that you want to any system you want at the time you want and you know, wherever you want. And so we do that in a way that the alternative would be using something like Kafka for streaming um and maybe a homegrown pipeline or a set of you know, batch pipelines that were managed by a vendor for for batch. And you know, I think most companies in the world actually do that today. You'll have a team that's on a a software engineering team that's building with Kafka and most likely a data engineering team or maybe another, you know, marketing team that's building with batch. So, that's pretty common. It has some drawbacks in that the pipelines don't necessarily stay in sync, but overall it tends to to work okay.

</details>

### 数据管线的工程挑战与生产级合规

在构建生产级数据管线时，单纯的实时传输远非终点。诸如**模式演进**（Schema Evolution）这类技术细节对于管线稳定性至关重要，必须确保当源数据增加列或修改数据类型时，管线不会中断。此外，处理诸如**个人隐私数据**（PII）的脱敏（如哈希处理）、**缓慢变化维**（SCDT Type 2）的转换以及合规性（如 **SOC 2**、**HIPAA**）是实现生产级的必要保障。为了实现物理隔离，平台还构建了 **BYOC**（Bring Your Own Cloud）部署方式。目前，尽管 80% 的用户能一次性成功构建管线，但针对余下 20% 遇到的第三方系统错误无法排查的问题，利用 AI 进行实时诊断与反馈成为了关键的技术路径。

<details>
<summary>Original English Source</summary>

Um about I think it was 3 years ago, my co-founder was on this stage and he talked he did our debut. Um, he actually showed our right time data pipelines and it went really well. What we didn't realize at the time was we had really just scratched the surface of what we needed to build to make something valuable. Um, there's so much more that goes into it and Matt can attest to this. Um, you know, it things like schema evolution are absolutely critical for any sort of data pipeline out there. You can't break a pipeline if someone adds a column or misses or, you know, break it if someone changes a data type. So, handle every possible edge case. Do it in a way that you can strip PII if you need to. So, may omission and hashing, things like that. Do it in a way that um, you can also transform data um, and prevent present things like SCDT type two slowly changing dimensions. All these little bits and pieces that go into creating real production grade pipelines. You know, when it comes down to it we also we didn't realize it but um, obviously you'll have to build a lot of compliance related things such as SOC 2 compliance and HIPAA but we ended up having to also build like BYOC where we can deploy in a customer's environment to totally isolate it from everything else. So, that's great and we got to the point where about 80% of our users could go in and build a pipeline with one try but there's still 20% that that they can't, right? And so that's for us that was something that's pretty important. We wanted to make sure that we're optimizing towards that 20%. It turns out that most of the time with those users are doing is they're running into an error message that they can't diagnose from a third party system. You know, it's it's impossible when you have 200 connectors to catch every single error message from every single third party system. So, we wanted to make sure that we could we could do that. And the only way that we found that's possible to do that is really to use AI. So, you know, that's a place that where we've been integrating AI into the platform for real-time feedback and diagnosis.

</details>

### AI 辅助构建与实时数据演示

除了实时诊断，**实时转换**（Real-time Transformations）也是一项复杂任务，而 AI 极大地降低了这一门槛。未来的管线构建将是“提示驱动”的：用户通过自然语言提示（Prompt）生成管线草稿，在 **UI** 或 **CLI** 中通过 **YAML** 规范进行审查，测试确认输出符合预期后，即可发布并纳入 **GitOps** 管理。现场展示中，利用 Estuary 的 **MCP**（Model Context Protocol）服务器和一系列云技能（Cloud Skills），在 30 分钟内构建了一个实时数据管线：通过 **CDC**（Change Data Capture）从 **Neon Postgres** 数据库捕获数据，并实时推送到 **BigQuery**、**Snowflake** 以及另一个 Postgres 库，同时实现了分析、操作数据看板和**向量存储**（Vector Store）这三种实时用例。

<details>
<summary>Original English Source</summary>

Another one is real-time transformations. They're complex and they're something that, you know, I think is um, most operators who have used something like Snowflake or Postgres SQL, they think that, you know, real-time transformations can't be that much harder. They're a little bit more difficult though. But AI makes them really easy too. So, it's another place that I think is really valuable. So, finally, I think there's a huge opportunity just when creating data pipelines to be able to use them differently than we have in the past, right? So, what I want to be doing when I'm creating a data pipeline is to prompt, "Hey, create this data pipeline to me for me." And then get back a draft which I can view in maybe a UI or a CLI using a YAML specification. And then finally, test it and make sure that the output looks like exactly what you'd expect. And and then be able to publish it when you're ready, check it into GitOps. And I think that's the future, right? Like that's where we're all going to be going to. And so, that's what we've been basically building. We're at the point right now where it's built through some Cloud Skills and an MCP server that we can we can show you here. And then I'm going to get into something that's I'll show you how it's actually built. But what you're seeing right here is this is application that we built using Estuary's MCP server and a few Cloud Skills. I see people already figured out what it is. So, basically, this is a real-time data pipeline. And it's powered by Estuary. It was built in about 30 minutes just using using basically Cloud. And so, the the primary amount of time was just getting that QR code to be the right size so you could actually take pictures of it from the background. So, if you all take out your phones and submit, you know, a an app, you'll see submit a submission. What you'll see is a few things here. You're submitting something into a Postgres database. And that Postgres database is managed by Neon. We're then doing using CDC to get it out of the Postgres database and we're putting it into a few different places. A BigQuery, Snowflake, and then a post another Postgres database. And that's all happening in real-time. You can track the latency here. It shows you, you know, P95 latency and all that stuff. So, that's um you know, you can see it all happening. The The point of this is that it's showing you three different use cases. One is analytics um with BigQuery and Snowflake. Another there is a live dashboard for operational data. And then a third is a vector store. So, it's an AI use case that's also um happening in real-time.

</details>

### 技术沉淀与未来展望

在处理 AI 相关需求（如 **RAG**）时，核心在于专注于构建基础模块。AI 的演进速度远超人类想象，因此平台的目标是提供诸如 **Python** 转换功能，使其能与未来数据格式无缝协作。现场演示中使用的 Python 转换与 SQL 转换功能，不仅 catalog 了数据请求，还能通过向量化技术处理相似想法的查询，体现了 AI 在文档处理与数据处理中的结合。团队计划在未来几个月内，将这一构建过程从 CLI 进一步演进为应用内的**聊天机器人**（Chatbot）模式，从而实现跨环境的实时交互与管线动态加载。

<details>
<summary>Original English Source</summary>

I love some of these. There's also two transformations that are being applied in real-time. And again, this is all just written by Claude. So, we um we ended up creating these transformations that are doing a very poor job of of uh cataloging what what you're asking for, but they weren't expecting pizza. Um and then another thing, the vector store can take um this and look for similar ideas. So, we can see other submissions that were similar. And the idea here is that that's more of like an AI use case, right? If we're vectorizing documents. Okay, so I want to show you what it actually looks like um in in the app. Um and so, I'm going to show you what was built by Claude. We have 51 submissions that have come into our Neon Postgres database here right now. Um and that's built in a way that can fan out. So, we can on the other side um in Estuary, just refresh it real quick. Uh you can see how many submissions have made it. I guess post Snowflake and BigQuery are a little slower than the Postgres side, which is actually part of the demo. That's what you're supposed to see. Um but what we're doing here is we have basically three transformation two transformations, uh Postgres database, and then these two Snowflake destinations. This one's vectorizing documents. It's using Python under the hood. We offer a Python transformation that you can use for uh you know, really nice um integration with AI type use cases. And then this enriched one is just using a SQL transformation under the hood. And so what I'm going to do is I'm going to get into um a quick video demo that shows how you used it. Cloud was down today, so I didn't want to take risks on trying to live code this on stage. I'll talk over it um and you can you can basically see what what this is doing. So, I put in a quick prompt um that says I want to create a Google Cloud Cloud SQL Postgres capture and capture all tables with CDC. And Cloud loads a skill. Um we have a bunch of publicly available Cloud skills that are on our GitHub right now. Um and an MSCP server that you can also find there as well. And so the cool thing about what this is doing is it's actually proposing um a YAML specification for you that you can review and choose um whether it makes sense, like decide if it makes sense to to be able to publish. Uh and then once you do, you just publish it and it it goes. Uh a quick transformation by a secondary Cloud skill here. Um and you know, while this is loading, I think it's important to say that like this is not the the end state we wanted it to be in. We don't want it to be through a CLI. So, in about 2 months you're going to be able to load a quick chatbot here in the app and be able to see it actually live and and um loading. So, I think that's going to be really nice. Um that's going to allow us to go, you know, back and forth in between environments um in real time. So, you know, Cloud here, what it's going to do is it's um it's loading the skill. It's going to be able to look at the actual tran- the actual schema of the source data, design um a derivation that's using um SQL around this, and this is the the schema of the source data, and then propose that to us. So, we end up getting the SQL transformation that's just using some case statements to uh to end up building. That's really it. From there, there's one more thing. I'm going to ask it to create a a materialization. That's what we call when we push to a destination system. And so Cloud's able to do that pretty easily, too. I don't need to go through the the whole video here, though. What what we've learned over the course of the process. We've been building Estuary for a few years now, and we were we were around and kind of wondering what we should do when Rag came out. I think we were all wondering what made the most sense. So, for us, what we what we learned is that really the building blocks are the most important things to focus on. There's There's going to be AI is going to move faster than anyone here can imagine, right? Any human can really imagine. We need to be able to provide things like Python transformations that can work seamlessly with the future formats that we're working with data in. And that's the goal for us. That's what we want to be able to offer.

</details>