---
author: AI Engineer
date: '2026-06-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iUWwcG-C8OU
speaker: AI Engineer
tags:
  - internal-tooling
  - data-analytics
  - ai-agent
  - dashboard-generation
  - context-injection
title: WorkOS 内部效能工具 Studio：非技术人员如何通过 AI 代理跨数据源查询业务数据
summary: WorkOS 产品负责人 Garrett Galow 详细分享了内部自研的 AI 数据工作台 Studio。该工具允许支持和销售等非技术团队通过自然语言与 LLM 代理交互，直接跨越 Snowflake、Linear 等数据源查询业务信息，并自动生成可复用的前端查询组件（Widget）。他深入探讨了底层基于 LangGraph 的代理编排机制、规避上下文窗口超载的实时上下文注入策略，以及防范 SQL 查询幻觉的强制预验证手段。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - WorkOS
products_models:
  - Studio
  - Snowflake
  - LangGraph
  - Claude 3 Opus
  - Radar
media_books: []
status: evergreen
---
### WorkOS 简介与背景

**Garrett Galow**: 大家下午好。今天是大会的最后一天了。希望大家都在坚持，还没有因为不停地讨论人工智能而感到太疲惫。是的，今天的分享会有些不同。我在 **WorkOS** 工作，我的名字叫加雷特（Garrett）。我是团队的产品负责人。

<details>
<summary>Original English</summary>

**Garrett Galow**: Good afternoon, everyone. Now, it's the last day. Hopefully, you're still holding on, not too tired of talking about AI yet. Um Yeah, today's going to be a little different. Um so, I work for WorkOS. My name's Garrett. I run product for the team.

</details>

**Garrett Galow**: 今天我其实不打算详细介绍我们的商业产品。所以我只会花大概 10 秒钟简单提一下 WorkOS，把这事交代过去，因为毕竟我的公司还是比较在意这个的。我们提供企业平台功能。我们是一个开发者平台。最简单快速的解释是，如果你曾经登录过 **Cursor**，那你就用过 WorkOS。

<details>
<summary>Original English</summary>

**Garrett Galow**: Um I'm not exactly talking about our product today. So, I'll do like 10 seconds about WorkOS just to, you know, get that out of the way since um my company cares about that. We do enterprise platform features. We're a developer platform. Uh the quick and easy is if you've ever logged into Cursor, you've used WorkOS.

</details>

**Garrett Galow**: 无论那是通过用户名和密码登录，还是通过你们公司的企业身份提供商（IDP）进行的单点登录。我们为 Cursor、**Anthropic** 和 **OpenAI** 这样的公司提供企业平台功能的底层支持。不过在今天，我打算谈论一些稍有不同的内容。我将分享一下我们在内部是如何运作的，以及我们为了让自己变得更高效而开发的一些工具。

<details>
<summary>Original English</summary>

**Garrett Galow**: Whether that was like username password or you went through your enterprise IDP. We power enterprise platform features for the likes of Cursor, Anthropic, OpenAI. Um today though, I'm going to talk about something a little bit different. I'm going to talk about how we operate internally and things that we've built to make ourselves more productive.

</details>

### 非技术团队的数据获取痛点

**Garrett Galow**: 我想在座的大多数人可能都是工程师，或者是从事技术相关工作的。你可能会遇到关于你们公司的一些问题，比如客户是如何使用你们的产品的，或者各项功能运转得怎么样。你们的市场进入团队（Go-to-market teams）或者支持团队肯定也会遇到一些关于客户如何使用产品的疑问，他们需要去寻找各种问题的答案。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, um I imagine most of you are probably engineers uh or on the technical side. Um you might have questions about things about your company, about how customers are using the product, how things are working. Uh your go-to-market teams or your support teams definitely have questions about how customers are using your product, trying to figure out uh answers to questions.

</details>

**Garrett Galow**: 你们公司内部可能会使用像 **Retool** 这样的工具。你也可能已经为大家搭建好了各种数据看板（dashboards）之类的东西。当然，这些工具往往是非常刻板和固定的，对吧？你构建了一个非常具体的东西。然后有人跑过来说：“哦，实际上我还额外需要这部分数据。我需要找到答案，我得去回答另一个数据看板无法提供答案的不同问题。” 于是，你要么得去开发这个新功能，要么去修改现有的东西，对吧？

<details>
<summary>Original English</summary>

**Garrett Galow**: You might have like retool inside your company. You might have built like dashboards and things like that. Uh of course, those can be fairly rigid, right? You build a very specific thing. Someone comes and says, "Oh, actually, but I need this extra bit of data. I need to find out answer this different question that the dashboard doesn't answer." And so, either you go and build that, you change it, right?

</details>

**Garrett Galow**: 我们经常看到一个大概是这样的工作流：某人提出了一个问题，通常是关于业务的。但他们可能没有足够的技术能力去自己寻找答案。他们往往需要用到像 SQL 这样的技能，或者是需要找一个有数据访问权限的人。他们不得不去解释自己的问题，解释为什么要问这个问题、以及回答这个问题所需要的上下文信息。然后他们只能等待。而像你这样的技术人员，就必须去回答这个问题，并将数据提供给他们。

<details>
<summary>Original English</summary>

**Garrett Galow**: We kind of see like a workflow that looks kind of like this, where someone has a question, often about the business. They may not be technical enough to go answer it themselves. Uh they often need something like SQL or someone that has access to the data. They have to explain their question, why they need it answered, the you know, context to answer it. They wait. Someone like you has to go answer the question, provide that data back to them.

</details>

**Garrett Galow**: 接下来他们会问：“你真的回答了我的问题吗？你提供的数据细节足够吗？哦，不，不，这很棒，但我实际上需要再深入一层的数据。”于是你又得来来回回地折腾。你们可能是在 Slack 里沟通这些的。这通常是一次性的工作，也很难形成好的规模化效应。我们也遇到了这个问题。如果你没遇到过，那真是幸运，但我们每天都在被这个问题困扰。

<details>
<summary>Original English</summary>

**Garrett Galow**: Did you actually answer the question? Did you provide enough detail? Oh, no, no, that's great, but I actually need the next layer deeper. Got to go back and forth. Uh you probably share that in Slack. Sort of a one-off. Doesn't really scale very well. Um we had this problem. If you didn't, we have this problem every day.

</details>

### AI 工作台 Studio 简介

**Garrett Galow**: 因此，我们开发了一个名为 **Studio** 的工具，它充当了一个内部工作台，人们可以在这里自己解答问题，甚至自己构建这些类似应用程序或数据看板的东西。接下来，我将向你们展示构建出这些东西大致是什么样子的。同时也会给你们看几个案例，展示我们在 Studio 内部日常使用的部分工具。之后，我还会稍微讲讲它在底层是如何运作的。

<details>
<summary>Original English</summary>

**Garrett Galow**: And so we built a tool called Studio uh that serves as kind of an internal workspace where people can answer questions and build these kind of apps or dashboards themselves. So, I'm going to show you both kind of what it looks like to build this out. Also show you a few examples of some of the tools that we use every day inside of Studio. And then I'll talk a little bit about how it works under the covers.

</details>

**Garrett Galow**: 好的，为了防止我完全把这个搞砸，我已经在这里提前准备好了一个提示词（prompt）。一个很常见的场景是，我们会做大量的辅助营销活动。大家知道的，我们在做播客广告，我们在做谷歌广告（Google Ads）。我们吸引人们来到 WorkOS 的网站，无论是访问我们的博客、开发文档，还是我们的营销主页。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, um so I don't uh get this completely wrong, I have a little prompt here already. But so, um you know, a common thing we have we do a lot of sub-marketing. You know, we're doing podcast advertisements, we're doing Google Ads. We're getting people to come to WorkOS site, whether that's our blog, our docs, or our marketing site.

</details>

**Garrett Galow**: 接着，我们就想知道他们正在阅读什么内容，什么内容是真正有效的，对吧？当一个人在我们的网站或者仪表盘上阅读内容后，他们是否转化为了应用的实际用户。所以，我想知道，嘿，**哪些内容带来了最多的新团队（在公司内部，我们将客户称为团队），也就是促成了最多的新团队创建。**

<details>
<summary>Original English</summary>

**Garrett Galow**: And then we want to know what content are they reading and what's effective, right? What is someone reading on our dash on our site and then you converting to actually using the app. So, I want to know hey, what content leads to the most new teams. We call our customers teams internally, so leads to the most new team creations.

</details>

**Garrett Galow**: 我可以将这个问题发送出去，然后 Studio 就会开始运作。它基本上会说：“好的，我想要寻找这些数据。我需要去看看我能够访问哪些内部资源？” 所以它知道它有权限访问我的 **Linear**、我的 **Notion**，以及我的 **Snowflake**。我们连接了这些数据源。它明白该如何使用这些工具，并开始运行查询。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, I can fire this off and we will um Studio starts operating. It basically says, "Okay, I want to find this data. I need to kind of look at like what, you know, internal resources do I have access to?" So, it knows that has access to like my linear, my notion, my Snowflake. So, we have these data sources that we connect to. Um and then basically understands how to use these tools and starts to run queries.

</details>

### 底层架构：LangGraph、Opus 与 Convex

**Garrett Galow**: 在这个例子中，它将运行一系列的 Snowflake 查询，这是我们的内部数据库，也是我们存储大量此类数据的地方。它将梳理信息，理清 schema（数据模式），查看需要用到哪些表，并执行相关操作。在它执行这些操作的同时，因为这可能会花上大概一分钟的时间，我来稍微讲解一下它底层是如何运作的。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, in this case, it's going to run a bunch of Snowflake queries, which is our internal database. It's where we store a lot of this data. Um and it's going to go through, figure out the schemas, look at the tables that it needs to, and do it. While it's doing this, since it might take just a minute, I'm going to talk a little bit about uh how it works uh kind of under the hood.

</details>

**Garrett Galow**: 你可以直接去我们的内部 Studio 数据大盘，或者在 Slack 中我们也有一个 Slack 机器人，所以你可以向 Studio 提问，这也会触发相同的流程。我们在后台运行了一个小型 API，它接收问题并进行解析，然后将其送入 **LangGraph**。这是一个与大语言模型（LLM）绑定在一起的智能体代理（agent），在这个案例中我们使用的是 **Claude 3 Opus** 模型，同时辅以各类工具，以及关于如何与这些系统进行交互的引导层（guidance layer）。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, uh you can either go to our internal studio dashboard, or in Slack we have a Slack bot, so you can ask questions of Studio. That kicks off the process. We run a little API behind the scenes that takes that, parses it, and then runs it through Lane Graph, which is an agent that's both tied to uh LLM, which in this case we're using Opus, along with the tools and the guidance layer for how it should interact with these systems.

</details>

**Garrett Galow**: 因此，我们搭建了通往数据源的集成代理（integration proxy），主要就是像 Snowflake、Linear 和 Notion 这样我们常用的工具。这个引导层的作用基本上就是定义关于你应该如何查询这些数据的规则，以及为了成功查询数据所需的上下文信息。是的，我们的 Snowflake 是一个庞大且错综复杂的数据库集合，因此代理需要获取一些上下文，弄明白：“我该怎么做？在 Snowflake 中，一个客户的数据表征（representation）是怎样的？我该如何以一种有效的方式进行联表查询（join tables）？”

<details>
<summary>Original English</summary>

**Garrett Galow**: So, we have this integration proxy uh to the data sources, primarily like Snowflake, Linear, and Notion are the tools that we use. Um and this guidance layer basically defines rules around how you should query this data, the context you need to successfully query the data. Right, our Snowflake is a pretty sprawling set of databases, so it needs to like get context around how do I What's the representation of a customer inside of Snowflake? How do I join tables in a way that's effective?

</details>

**Garrett Galow**: 所以，整个过程都是由这个智能体驱动的，它生成由 LLM 运行的查询语句，然后理所当然地返回答案或是对微件（widgets）的更新，一会我会给大家展示这个微件。目前我们将大量的系统状态（state）存储在 **Convex** 中，作为本地保存这些信息的方式，这样就可以在不同会话中保留状态。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, the agent drives all of this, uh makes queries that LLM runs, and then of course it provides back answers or uh updates to widgets, which I'll show you in a minute. And then we store a lot of that state today in Convex as a way to locally store this information, so it's preserved over sessions.

</details>

### 从临时查询到自动生成前端微件

**Garrett Galow**: 我们回到刚才的演示。太好了，看起来我们已经获取了大量的数据。我把它放大一点给大家看。我们可以很明显地看到，例如，有人访问了我们的主页，有人查看了定价页面。我们能看到哪些博客文章在驱动团队注册方面是最有效的。这里有更新日志（change logs）和开发文档。我大概得到了一个概览，这很不错。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, we go back. Um cool, looks like we've actually gotten a bunch of data here. Let me make it a little bit bigger for you. So, we can see obviously like, you know, people go to our home page, people look at the pricing page. Um we can see like the blog posts that are most effective for driving team sign-ups. Um change logs and docs. I'm kind of getting the summary. Okay.

</details>

**Garrett Galow**: 虽然这已经解答了我的问题，但我希望能把它做成一个可以长期存在、可以复用的东西。所以我接着问：“你能否基于这些信息构建一个表格，让我在不同的时间切片下查看这些数据？” 在这里，它不再只是去运行查询、获取答案而已。我实际上是希望它构建一个可复用的工具，让我能和团队成员分享，并在每周的同步会议中使用。

<details>
<summary>Original English</summary>

**Garrett Galow**: But, this is great, so it's like answers my kind of question, but I want this to be like a long-standing thing that I can reuse. So, can you build a table of this that lets me see see this data over various time slices. And so here it's not just, you know, run the queries, get the answer. But I actually wanted to build like a reusable tool that I can that I can share with my teammates, that I can use in like our weekly syncs.

</details>

**Garrett Galow**: 所以它会开始思考如何实现这个目标，然后去构建我们称之为“微件（widget）”的东西。这里的微件基本上就是一段在沙盒中运行的代码。它不仅包含了用户界面（UI），还包含了 API 以及驱动这样一个完全可用的工具所必需的底层数据查询语句。真正创建微件的过程需要让它思考一分钟。在此之前我预先构建了另一个版本，现在我可以展示给大家看看。

<details>
<summary>Original English</summary>

**Garrett Galow**: And so it's going to kind of think through how to do this, and then it's going to go and build what we call a widget. A widget is in this case, uh, basically like sandbox code that runs. Um, and it's both the UI, the APIs, and the query necessary to power like, uh, a fully usable tool. Um, so this is going to think for a minute uh, as it actually creates the widget. Uh, I have another version of it that I can show you.

</details>

**Garrett Galow**: 我们来看看这两个实例是否看起来一样。这就是我在演讲前提前建好的那个。它基本上向我提供了在不同时间跨度下的团队数据。你知道，究竟是什么内容在驱动这些注册？并且这是实时（live）的，对吧？如果我运行它，它会重新执行那个查询。它会提供给我不同时间切片的数据。我可以让它全屏显示。它会全盘思考这个问题。

<details>
<summary>Original English</summary>

**Garrett Galow**: We'll see if they look the same, uh, across instances. But this is like a one that I had pre-built before this. Um, so it basically gives me this data of like teams over different time spans. You know, what content is driving those sign-ups. Um, and it it's live, right? If I if I run this, it's going to rerun that query. It's going to give me the data for different time slices. I can make it, you know, full screen here, show it. Um, and so it, you know, it's going to think through this.

</details>

**Garrett Galow**: 你看，我们获得了一个非常相似但又有一点不同的视图，但这个预建的版本实际上带有分类过滤器。因此，我可以根据它运行的内容类型进行筛选。然后去查看，哪些是最有效的？我们有很多博客文章，到底哪几篇才是为平台带来流量最有效的？这样我们就能更高效地定制我们的内容了。

<details>
<summary>Original English</summary>

**Garrett Galow**: Um, look, and we get like a pretty similar, slightly different view, but, um, this one actually has like category filters, so I can look at, you know, based on the kind of content that it's running. Um, and see like, okay, what are the most effective, you know, we got a lot of blog posts, which are the most effective ones um, that drive traffic to the platform, so we can tailor our content effectively.

</details>

### 安全排查案例：通过微件分析客诉

**Garrett Galow**: 但这并不是它的全部，这个工具在很多其他场景下都非常有用。举个例子，**Radar** 是我们的内部产品之一。它是一个类似于阻止爬虫（bots）和恶意行为者的安全产品。有时候客户会问：“嘿，为什么这个用户会被 Radar 拦截呢？你能帮我查清楚原因吗？” 为此，我们也自己构建过一些数据看板之类的东西，但这通常意味着我们要翻阅大量支持工程师（DSC）分享的 SQL 查询记录，因为这些都是用来解答客户问题的。

<details>
<summary>Original English</summary>

**Garrett Galow**: Um, but this isn't, you know, this is useful for a lot of things. Like, for example, uh, Radar is one of our internal products. It's like a security product that blocks bots and bad actors and you know, sometimes customers say, "Hey, why did this user get blocked by Radar, right? Can you help me understand?" And so, you know, we've built some of these dashboards and stuff ourselves, but typically that involves like having to go through a lot of our DSCs are like sharing SQL queries that are run to answer these questions.

</details>

**Garrett Galow**: 但现在，我不用再做那些繁琐的事情了，我已经提前构建好了这个微件，它已经连好了 API 和底层查询。我只需要在里面搜索一下我自己的个人邮箱地址即可。你可以看到，在这种情况下，它在对我们的数据库运行真正的查询语句，去拉取并查看这些数据。然后，你可以看到我在这里和它的对话历史：“嘿，你能帮我建一个这样的看板吗？” 接着它运行了一大堆查询。

<details>
<summary>Original English</summary>

**Garrett Galow**: But instead of having to do all that, I can just, you know, uh I've already built this widget that has the APIs or the queries hooked up. And I can just do a search for myself in this case, my personal email. Uh and, you know, in this case, it's it's running a real query against our database to actually pull this data and and look at it. And so, you can kind of see like the conversation history of here of me talking with it, "Hey, can you build me this dashboard?" Uh runs a bunch of queries.

</details>

**Garrett Galow**: 一开始其实有点小差错，但我对它说：“嘿，这里好像有点问题，你能继续进行下去吗？” 然后它搞定了。最后一件事是，它在 `type` 列里有一个视觉 UI 上的 bug。所以我对它说：“嘿，你能修复一下那个视觉错误吗？我希望它是一个整洁的单列。” 大家可以看到这里的数据，Cursor 也是使用 Radar 的客户之一，这里列出了我使用个人邮箱登录 Cursor 的所有记录，以及我是否被拦截了。

<details>
<summary>Original English</summary>

**Garrett Galow**: Uh it actually like kind of messed up at first, but I, you know, say like, "Hey, can you There seems to be an issue. Can you keep going?" Um it did it. And sort of the last thing was like, it had like a visual UI bug in the type column. So, I was like, "Hey, can you can you fix that like visual bug? Like I'd like it to be one nice little column." And so, here we can see like uh for Cursor, which is one of our customers that uses Radar, here's all the times that I logged into Cursor with my personal email and whether I was blocked or not.

</details>

**Garrett Galow**: 我在这里有一个测试记录，在其中一个测试环境里我把自己给屏蔽了。这样一来，这立刻变成了一个自助服务工具，我们的支持团队可以用它来查询此类信息。对我们的支持团队而言，这真是极其强大的能力。他们经常在 Slack 里使用它，因为不同的客户有着截然不同的具体问题。他们可以直接说：“嘿，你能帮我把这个客户所有的会话记录找出来吗？这样我就能找出到底哪里出了错。”

<details>
<summary>Original English</summary>

**Garrett Galow**: Uh I had a test here where, uh you know, I blocked myself in one of our test environments. And so, like this becomes like a self-serve tool that our support team can use to look this stuff up. Um and so, this has been really, really powerful for our support team. They use this in Slack all the time because they don't need um you know, different customers have different, you know, specific issues. And they can say like, "Hey, can you go find me all the sessions that this customer has so I can find out like what went wrong, right?"

</details>

**Garrett Galow**: 我们不再需要一支专门的平台团队或者数据团队去构建那些注定需要不断修改的数据看板。如果只是一次性的请求，我们的支持团队可以依靠自己获取答案；如果他们发现某个问题被频繁问起，就可以构建这样的微件在内部共享给其他人使用。我们就这样以自助服务的方式，构建出了自己的数据面板和工具体系。

<details>
<summary>Original English</summary>

**Garrett Galow**: And so, we're not trying to build you know, we don't need to have some sort of like platform team or data team building these dashboards that are going to be used and need to be constantly modified. Uh our support team can basically, if it's a one-off get the question answered themselves and if they're finding that they're actually asking the same question a lot, they can build these and then, you know, we can share them internally to other folks. And so, we kind of build out our own dashboard and tooling um, in a self-serve manner.

</details>

### 工程落地经验：保证工具高可用与防幻觉

**Garrett Galow**: 所以，我接下来稍微总结一下。为了让这个工具既有用又可靠，我们到底做了些什么呢？在构建它的过程中，有三件事情变得极其重要。第一点是**顺序执行 (Sequencing)**。也就是当代理收到一个新问题或新提示时，它应该如何介入处理？我们让它在执行前运行大量的前置检查（pre-flight checks）。比如，所有的工具都正确连接了吗？你是否有足够的上下文来回答这个问题？如果没有，那就提出澄清问题，并通过核对清单来确定应该调用哪些具体的工具。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, I'll kind of, uh, wrap up with a little bit of like, what did we have to do here to make it, uh, like useful and reliable? So, there's kind of three things, um, that became really important in building this. The first is sequencing. So, this is, uh, how should the agent like approach when it gets a new question, when it gets a prompt, how should it do this? So, we make it run a lot of pre-flight checks. Um, so this is, you know, are all the tools connected correctly? Do you have enough context to be able to answer the question? If not, ask clarifying questions, um, and then sort of determine, run through a checklist to determine the tools that it should actually use to call.

</details>

**Garrett Galow**: 第二个核心点是，恰好在它决定调用某个工具的那一刻，才是我们注入有关“如何使用该工具”的**上下文信息 (Context Injection)** 的时机。以 Snowflake 为例，我们拥有自己嵌入的特定上下文。这份上下文并不简单，篇幅相当长，因为它编码了我们内部数据库的 schema（表结构），让模型理解，如果要将团队对象与开发环境连接起来，或者与他们所使用的资源建立关联，到底应该怎么做。

<details>
<summary>Original English</summary>

**Garrett Galow**: Um, we actually, at the time it decides to invoke a tool, that's when we inject context around how to use the tool. So, um, for example, if I show some of the, uh, tooling that we use, like for Snowflake, here for example, we have this context that we embed. And it's it's not trivial, it's fairly long cuz it encodes basically the schema of our internal database and how to like understand how do you connect teams to the environments to the resources that they're using.

</details>

**Garrett Galow**: 这些上下文是在 Snowflake 被调用并在运行时才动态注入的。我之前在另一个演讲里听到有人讨论过，你绝对不想在一开始就预加载所有工具的所有上下文信息，因为那样会瞬间撑爆你的上下文窗口（Context Window）。另一个重要机制是**分层 (Layering)**。对于 Studio 的初始化，我们有一个基础提示词作为起点，那是默认配置。然后我们会有机构级别的规则（org rules）。

<details>
<summary>Original English</summary>

**Garrett Galow**: And so, like for example, this gets injected, uh, at runtime when Snowflake is being adjusted. I saw someone earlier in a talk talking about how you, you know, you don't want to preload all that context of all your tools cuz it blows out your context window. Second is layering. Um, so we have sort of the base prompt that Studio uses to start off with. We have sort of the defaults and then we sort of have like org rules around, um,

</details>

**Garrett Galow**: 在针对某个特定工具的特定设置中，可能会有专门的上下文。如果有人去修改配置一个工具，我们希望这个特有上下文能被保持下去。最后我们还会特意告诉 LLM：在涉及我们产品的相关知识时，请保持怀疑态度，不要轻信。这往往是因为模型的训练数据可能已经过时了。我们的产品迭代得非常快，一切都在不断变化。我们通过指令明确告诉它：“不不不，去查第一手资料，去我们的技术文档里查数据。不要仅凭模型自以为对 WorkOS 的了解来作答。”

<details>
<summary>Original English</summary>

**Garrett Galow**: in a given like setup for a given tool, there might be a specific context. If someone's going in editing a tool, we want that context to be maintained. Um and then actually last um we tell the LM to specifically like distrust uh knowledge around our product often just because like sometimes the model training is using outdated data. Our product changes very quickly. Things are moving all the time. And so we actually use uh we tell it to like no no no, go for primary sources, look up data in our docs and things like that. Don't just rely on like what the you know model knows about WorkOS necessarily.

</details>

**Garrett Galow**: 第三个机制是**验证 (Validation)**。如果它要去我们的 Snowflake 实例中写查询，我们总是强制要求它先执行查询，并验证是否真的有数据返回。有很多时候，LLM 生成的 SQL 查询在语法上是完全有效的，但跑出来的结果为空（zero data）。如果它没注意到这一点，那就一点用也没有。

<details>
<summary>Original English</summary>

**Garrett Galow**: And then last validation. So um if it's going to write a query to our Snowflake instance, we have it always run the query and validate that it gets data back. Uh you know, many times they can have a valid SQL query, but that returns zero data. If it doesn't notice that, it's not very useful.

</details>

**Garrett Galow**: 因此，它实际上会在把这些查询硬编码到微件里面之前，先运行一遍，验证它们。它基本上是在部署到仪表盘之前，先预验证自己的工作成果。开发产品时，我们当然还会运行评测（evals）。评测非常有用，但时间关系，我今天没办法深入探讨如何开发和设计评测集。我们在暂存（staging）和生产环境的实例中都使用了评测机制，我们对待它们一视同仁。这样一来，无论是在我们开发 Studio 时，还是我们的同事在使用它时，得到的体验都是一致的。这就是 Studio，它让我们能够回答关于业务的任何问题。大家有什么想问的吗？

<details>
<summary>Original English</summary>

**Garrett Galow**: So it actually runs queries uh validates them before it hardcodes them into widgets and things like that. So it's basically pre-validating its work before it's deploying it into like a dashboard. Um and then yeah, we we run obviously evals when we're developing the product. Evals are very useful. I don't have time to go into how to develop and design evals. Um but we use evals uh in both our staging and production instances. We treat all of that the same. So that way we get the same experience when we're developing Studio versus when our teammates are using it. So yeah. That's Studio. It uh is our way of basically being able to answer any question about the business. Anything I can answer for y'all?

</details>

### Q&A 问答环节

**观众**: 一个快速的问题。

<details>
<summary>Original English</summary>

**Audience**: One quick question.

</details>

**Garrett Galow**: 是的，抱歉，请讲。

<details>
<summary>Original English</summary>

**Garrett Galow**: Yep. Sorry. Sorry, go ahead.

</details>

**观众**: 你们是否对旧的 Snowflake 数据资产进行了大量的清理工作？

<details>
<summary>Original English</summary>

**Audience**: Um did you have So do you do a lot of clean up on the old Snowflake uh data estate

</details>

**Garrett Galow**: 其实并没有。这里有一个非常具体的问题，比如说，因为种种历史原因，一个客户实体与它所拥有的用户之间的连接关系，在表查询中可能会嵌套整整四层 JOIN。每一个新员工如果想执行这种查询，都必须学习和复制粘贴这段包含复杂 JOIN 的代码块，然后应用到自己的查询中。

<details>
<summary>Original English</summary>

**Garrett Galow**: No, actually. And like we have there's this one specific problem where like the connection between a customer entity to like, you know, the users that they have or whatever is like four joins deep because of reasons. And and like every new employee has to learn like if you want to do that, you have to like copy and paste this join block and use it on all your It's like

</details>

**Garrett Galow**: 现在的情况是，我们只需要把这个逻辑告诉 Studio 一次，对吧？它以后每一次都会知道该怎么做。LLM 在解析表结构 schema 方面实际上表现得非常出色，有很多东西它们自己就能搞清楚。只要你的列名具有较好的自我描述性，它都能看懂。

<details>
<summary>Original English</summary>

**Garrett Galow**: we tell Studio about it once, right? It knows how to do that every time. LLM's are quite good at interpreting table schema pretty well. And so there's lots of stuff they can get. If you have like pretty self-descriptive, you know, column names and stuff it can figure out.

</details>

**Garrett Galow**: 但是，我们确实还是会提供那个上下文信息块，因为在有些场景下它至关重要。举个例子，在 Radar 模块里，我们把用户尝试登录的事件称为 `attempts`，我们还有用来记录被拦截情况的 `detections` 表。我们需要明确告诉它：“哦，你需要连接这个，这些表是按这种方式进行连接的。” 只要告诉了它这些，它就能基本完美地针对该数据运行非常有效的查询了。所以你需要决定你想提供多少这样的上下文信息。

<details>
<summary>Original English</summary>

**Garrett Galow**: But again, we do have that like context block that we provide because it does matter for, you know, example, like in radar we have attempts which is people trying to log in. We have detections for when like things and it's like, oh, you need to join this, these tables join this way. And just by telling it that, it can basically run effective queries for for that data. So there is some uh information you want to provide.

</details>

**Garrett Galow**: 但效果确实出奇地好，比如你其实不需要给所有的表都做检索增强生成（RAG）。我们没有为整个系统建立什么 RAG 知识库，我们只是直接调用工具，并在顶层加上必要的上下文。有问题吗？

<details>
<summary>Original English</summary>

**Garrett Galow**: But surprisingly good, like you don't need to like rag all this stuff, you know, like we there's no rag database for us in all of this. Like we're just invoking tools directly with just context on top. Question?

</details>

**观众**: 是的。非常有趣，这恰好也是我们的做法。我们会直接通过上下文来告诉它如何进行 JOIN，然后它就会记住那些奇怪的关联逻辑。但我们一直在关注的一个问题是，我们的工作流有点类似，那些查询会被转化为微件。有没有人会对这些微件里的查询语句进行审计或数据治理（governed）？我们的担忧是，如果某人生成了一个查询，模型的技能点如果出了偏差导致数据是错的，然后这就成了一个无人查验过的“伪真理”，所有人都信以为真了。你们遇到过类似的情况吗？

<details>
<summary>Original English</summary>

**Audience**: Uh yeah, and that's actually interesting that's exactly what we do. We just go to like a context thing that tells it how to do the joins and then it knows and then it knows those quirks. Um One of the things we've been looking at, though, we we do something similarish, but is those queries get generated so it I mean as widgets, you've got the widgets that do those get audited or governed by anyone? Because our concern is that like someone generates a query, the skill gets it wrong and then it becomes a truth that everyone thinks it's true and no one's ever checked it. So do you have anything like that?

</details>

**Garrett Galow**: 是的，对于这个问题，我们目前的态度可以说是：要信任，但也要验证（trust but verify）。老实说，我在我们跨系统应用中的高准确命中率（hit rate）上留下了非常深刻的印象，它实在是高得惊人。我认为这里存在一类可以通过上下文明确规定的规则。比如你可以在上下文中嵌入指令：“确保你只拉取未被删除的实体数据”，“确保你拉取的状态是活跃的”，对吧？你们的业务数据中肯定有这种在特定状态列上保持一致性的东西。这类规则如果 LLM 不知道，就很容易忽略。

<details>
<summary>Original English</summary>

**Garrett Galow**: Yeah, I mean there's definitely a little bit of like, you know, there's always some trust but verify, you know, I've actually been pretty impressed that uh the hit rate on the cross this is very, very high. I think there's like sort of a category of um which you can actually embed into the like context of like, you know, make sure you only pull non-deleted entities, right? Make sure you pull things in an active status, right? There's kind of things that your data probably have you have consistency around of a status column, right? And like those are the kind of things that I've seen that LLM's will miss if they don't know.

</details>

**Garrett Galow**: 例如，如果在没有上下文的情况下去问：“有多少用户拥有这项资源？” 它可能就会直接利用 `COUNT` 并按照客户 ID 执行 `GROUP BY` 操作，对吧？然后这就错了：“哦，不，你实际上必须加上这些过滤列。” 但只要你在上下文中包含了这些逻辑，它就能防范绝大多数类似的问题。我发现这种机制帮我们排除了非常多的隐患。如果是超出这个范围导致的错误，那往往会错得非常离谱和明显，一眼就能看出来。

<details>
<summary>Original English</summary>

**Garrett Galow**: They're like it's like, you know, how many users have this resource? And it's just doing a count group by, you know, customer ID, right? And it's like, oh, no, you actually need these filter columns. Um, but if you have that in your context, uh, that's kind of thing that protects against a lot of those issues. So, I find that that has removed a lot of the the problems for us. Um, and then, you know, if if it misses from there, it's it's, you know, it's like making a bigger error that's pretty obvious.

</details>

**观众**: 我可以输入来自多个工具的数据吗？比如混合搭配它们？

<details>
<summary>Original English</summary>

**Audience**: Can I send the data for uh, data from multiple tools? So, you mix and match them?

</details>

**Garrett Galow**: 对。是的，目前我们只接了那几个系统。我们正在添加更多的系统连接。不过是的，它可以从不同的工具拉取数据，并把数据融合在一个统一的界面里。

<details>
<summary>Original English</summary>

**Garrett Galow**: Yeah. Yeah, yeah, so so we have, uh, you know, just those few. We're adding more of those connections. But yeah, it can pull from different tools and combine that data into one interface.

</details>

**观众**: 之后你会怎么解析数据呢？你是否需要知道如何按先后顺序关联这些工具？

<details>
<summary>Original English</summary>

**Audience**: And how would you refract the data afterwards? Would you need to like know how to relate those tools, uh, sequentially?

</details>

**Garrett Galow**: 实际上，生成的微件本身就是代码。所以，它写入的是被导出（written out）的 JavaScript 代码，正是这份代码通过工具去向那些底层服务发起 API 调用。因此，一旦微件被创建出来，它就是稳定可靠的。它并不是 LLM 每一次都在那里重新运行工具。

<details>
<summary>Original English</summary>

**Garrett Galow**: >> So, it's actually the widgets are actually code. So, it's writing, um, JavaScript that is >> Writing it out so that that is making the underlying API calls to that service through the tools. So, once the widget is created, it is reliable. It is not the it's not the LLM running the tool every

</details>

**Garrett Galow**: 当我在界面上点击刷新时，它实际上只是在向那些工具重新查询数据而已。微件开发完成后，LLM 就不再参与其中了。除非我回过头去对模型说：“嘿，你能调整一下这个微件吗？能加上这一列吗？” 或者其他的修改请求。在这个意义上，最终的产物是非常可靠的。

<details>
<summary>Original English</summary>

**Garrett Galow**: So, when I hit like refresh here, this is actually just re-querying, uh, data from those tools. So, the LLM's not involved once the widget is developed. Until I go back and say, "Hey, can you make an adjustment to this widget? Can you add this column?" or whatever. So, so the actual final product is very reliable in that regard.

</details>

**观众**: 如果你需要传入不同的数据，它只是作为代码的一个输入参数（input argument）吗？

<details>
<summary>Original English</summary>

**Audience**: And if you need to pass in different data, is it just an input argument to that, uh,

</details>

**Garrett Galow**: 是的。就像演示里，我给出一个输入值，它就会像普通的 JavaScript 那样把这个输入喂给查询逻辑去执行，对吧？所以在进行这些用户输入交互时，你不再依赖 LLM 每次去正确地解析意图。它是在执行声明式的代码（declarative code）。

<details>
<summary>Original English</summary>

**Garrett Galow**: Yeah, and I, uh, you know, like you can do, you know, here it's like I'm giving an input and that's just being fed into the query like any sort of JavaScript do it, right? So, like when you're doing these user input things again, right? You're not relying on the LLM to better like parse that correctly. It's writing, you know, declarative code.

</details>

**观众**: 明白了。那你如何处理和尊重用户对数据的访问权限控制？你怎么，抱歉，怎么尊重用户访问权限的？

<details>
<summary>Original English</summary>

**Audience**: Yep. And how did you respect user access to the data? How do you what? Respect user access to

</details>

**Garrett Galow**: 哦，对，这是个好问题。目前这些集成（integrations）是基于用户个体的。比如是我自己在连接 Snowflake、Linear 和 Notion 账户。但这正是我们在努力改变的地方，因为这样确实有些繁琐。你其实不希望每个员工都必须去手动进行这番操作。

<details>
<summary>Original English</summary>

**Garrett Galow**: Oh, yeah, that's a great question. Today, uh, the integrations are user based. So, like I connecting Snowflake and Linear Notion myself. Um, that's something we're actually working on changing cuz that's kind of annoying. Like you don't want every employee to have to necessarily do that.

</details>

**Garrett Galow**: 而且很多时候，哪怕你没有 Salesforce 账户，你也可能需要去读取特定的 Salesforce 数据。因此我们实际上正在研究驱动这些集成的机制，我们有一个叫 Pipes 的产品，就是用来做第三方集成的。我们现在正是在使用自己的底层产品，我们在构建我们所谓的“组织级连接器（org connectors）”。

<details>
<summary>Original English</summary>

**Garrett Galow**: And there are cases where like, you know, maybe you don't have a Salesforce account, but you probably should go to read certain Salesforce data. So we're actually working on the thing that drives these integrations, we have a product called Pipes which does third-party integrations. So we're actually using our own product under the hood here. We're building out organ- like what we call org connectors.

</details>

**Garrett Galow**: 这样一来，只需一个人建立好连接，然后就能设定规则，规定当人们查询这些数据时的默认访问级别。比如你可以设定，在 Linear 中，大家默认只拥有只读权限，但某些在 Studio 应用中拥有特定角色的人，会获得管理员权限或编辑权限之类的高级权限。所以，我们是在工具的上层构建一套权限控制层（permissioning layer），因为强制要求每个用户自己登录并授权确实挺折腾人的。

<details>
<summary>Original English</summary>

**Garrett Galow**: So like one person sets up the connection and then can set rules about, you know, what's the default level of access when people are querying that. So you know, for example, you could say by default in, you know, Linear you get read-only access, but certain people based on like roles in the studio application, they get uh, you know, admin or or edit access or something like that. So we're kind of building that permissioning layer on top of it because, yeah, doing the per-user login is kind of annoying.

</details>

**观众**: 酷。最后一个问题，你们怎么把控成本的？使用这种机制，有什么相关的缓存（caching）策略吗？

<details>
<summary>Original English</summary>

**Audience**: Cool. Uh, yeah, sure. Um, yeah, how do you uh, have a handle on costs? So obviously something like this. Is there any like caching that you do?

</details>

**Garrett Galow**: 这些微件一旦生成后就是声明式的代码，所以你不需要在每一次调用或刷新时都付出 LLM 的接口成本。不过说实话，只要它能正确回答业务问题，我们是非常愿意承担这笔开销的。**Claude 3 Opus 模型**在性能上大幅领先其他模型，如果为了省钱而选择牺牲回答的质量，这种权衡在我们看来是无法接受的，所以在这个事情上我们非常乐意掏钱。

<details>
<summary>Original English</summary>

**Garrett Galow**: Um, I mean, the widgets themselves once they're generated are declarative, so you're not paying the LM cost every time, but uh, honestly for us, we're willing to pay the cost for the questions being answered. Like Opus outperforms better than other models so much that uh, like I wouldn't trading the cost off would trade off quality in a way that we wouldn't deem acceptable, so um, I think we're pretty willing to spend the money.

</details>

**观众**: 明白了。

<details>
<summary>Original English</summary>

**Audience**: Cool.

</details>

**Garrett Galow**: 好的。非常感谢大家。

<details>
<summary>Original English</summary>

**Garrett Galow**: All right. Thanks so much.

</details>