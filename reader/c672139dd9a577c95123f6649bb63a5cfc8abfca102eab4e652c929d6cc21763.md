---
author: AI Engineer
date: '2026-10-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=uA4ah-dVHvU
speaker: AI Engineer
tags:
  - legacy-modernization
  - model-context-protocol
  - data-migration
  - event-streaming
  - change-data-capture
title: 先锋领航现代化重构：通过 MCP 与 AI 将遗留系统调研周期从 7 天缩短至 15 分钟
summary: 先锋领航（Vanguard）现金项目技术负责人 Gareth Yoder 分享了现金账本现代化重构历程。团队并行推进数据、生产者与消费者三大迁移支柱，借助 MCP 服务将遗留代码暴露给 AI 工具，使技术调研反馈从 7 天降至 15 分钟，并总结了重构而非平移、持续演进 AI harness 等核心工程经验。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Vanguard
products_models:
  - Kafka
  - GraphQL
  - Snowflake
media_books: []
status: evergreen
---
### 先锋领航的现金账本现代化之路

我的名字是 Gareth Yoder。我是 Vanguard 现金项目的技术主管。我协助管理现金项目中的四到六个团队。本次演讲的主题是“一个都不能少：Vanguard 现金现代化之旅”（No cash left behind, a Vanguard modernization journey）。

<details>
<summary>Original English</summary>

>> My name is Gareth Yoder. I'm the cash program technical lead here at Vanguard. I help oversee four to six teams in the cash program. This is no cash left behind, a Vanguard modernization journey.
</details>

这段历程实际上始于我们在 2022 年向 Vanguard 经纪账户客户推出“现金加成”（Cash Plus）服务之后。在我们完成发布之后，开始听到风声说现代化即将提上日程，并且这将是我们的下一个重大项目。在座有多少人的代码库属于遗留代码？对吧？很多人都是。又有多少人希望这些遗留代码库能自己实现现代化？对吧？很多人也会这么说。

<details>
<summary>Original English</summary>

This journey really starts after we delivered our cash plus offering to our Vanguard brokerage account clients, and we launched that in 2022. And after we did the launch, we started to get the whispers that modernization is now coming down the pipeline, and that will be our next major project. How many here have legacy code bases? Right? That's a lot of you. How many of you wish that legacy code base would just modernize? Right? Many of you would say the same.
</details>

### 什么是现金账本系统？

回顾这一路走来的历程，我们将在今天的演讲中梳理这条时间线，但我首先想向大家讲清楚现金账本（cash ledger）究竟是什么。

<details>
<summary>Original English</summary>

So, looking here at the journey, we're going to go through this timeline in today's presentation, but I want to first talk to you what a cash ledger actually is.
</details>

现金账本涉及所有从外部世界进入我们 Vanguard 经纪账户的资金变动交易，它也涵盖账户之间的资金划转。至于支付轨道，可以联想到 ACH、电汇（wires）等。我们支持 Web 渠道、移动端渠道以及批处理渠道。

<details>
<summary>Original English</summary>

A cash ledger involves all money movement transactions into our Vanguard brokerage accounts from the outside world. It also involves cash being moved between accounts. And so, the payment rails, think ACH, wires, and more. We support the web channels, mobile channels, and batch channels.
</details>

我们的系统运行在双活（active-active）、多区域容灾的高可用生态中。我们的服务每天接收高达 3000 万次调用，我们的客户每天也会生成 50 万笔账本变动。

<details>
<summary>Original English</summary>

Our system runs in an active-active multi-region fault-tolerant ecosystem. And our services will receive upwards to 30 million calls per day. Our clients will generate a half million ledgers every day as well.
</details>

### 三大支柱与并行推进

当我们开始采用这种现代化方法时，我们将其划分为三大支柱：数据迁移、生产者迁移以及消费者迁移。但因为这是一项企业级优先事项，我们必须三者并行推进。

<details>
<summary>Original English</summary>

And so, as we start to go down this modernization approach, we broke it down into three pillars: a data migration, a producer migration, and a consumer migration. But, because this was an enterprise priority, we had to do all three in parallel.
</details>

### MCP 带来的转折点：调研耗时从 7 天降至 15 分钟

现在回顾调研与分析阶段，记住我们当时正处于时间线的最初起点，AI 工具当时还不存在。因此，我们经常需要与大型机（主机）工程师合作，与架构师合作，试图搞清楚数据模式（schema）模型应该长什么样。

<details>
<summary>Original English</summary>

So, now, as we look towards the research analysis, remember we're at the beginning of our timeline, the AI tooling wasn't there. And so, oftentimes we would work with mainframe engineers, and we would work with architects to try to determine what that data schema model would look like.
</details>

在这段现代化历程中出现了一个转折点，那就是当我们通过一个 MCP（Model Context Protocol）服务器将遗留代码库开放给 AI 工具使用的时候。

<details>
<summary>Original English</summary>

And there was a turning point in this modernization journey, and that's when we had our legacy codebase being available to our AI tooling via an MCP server.
</details>

现在我们看到了更快的反馈回路。过去大型机工程师需要花费 7 天深入代码进行分析、然后再向我们反馈答案的事情，现在全都可以通过一个 AI 工具的提示词来完成。

<details>
<summary>Original English</summary>

And now we saw faster feedback loops. What was taking 7 days for a mainframe engineer to go into the code, do their analysis, and then kind of and come back to us for an answer, now could all be done via an AI tool prompt.
</details>

我们看到的结果是，反馈周期从 7 天大幅缩减至 15 分钟。这对我们的产品负责人、技术主管和开发人员来说都是一次巨大的胜利。他们都认为正是这个工具帮助我们的现代化取得了成功。

<details>
<summary>Original English</summary>

And what we saw was that the feedback loop was reduced from 7 days down to 15 minutes. It was a huge win for our product owners, our technical leads, and developers alike. They all contribute this tool to helping our modernization succeed.
</details>

### 数据迁移：CDC 与严密校验

接下来谈谈数据现代化。我们采用了行业通用的标准 CDC（Change Data Capture，变更数据捕获）方法，然后必须对两个数据库进行扫描。一个团队负责做每日对账审计。

<details>
<summary>Original English</summary>

So, let's talk about data modernization. We utilize the standard CDC change data capture approach that's common in industry, and we had to then scan both databases. A team did daily audits.
</details>

我们首先通过校验行级数据计数来确保强一致性（strong consistency）；接着我们通过检查单个字段来确保强完整性（strong integrity），确保金额从旧系统到新系统完全吻合，确保账户信息吻合，以及州预扣税、联邦预扣税等信息完全匹配。遗留数据库中的所有属性都必须与云端一致。

<details>
<summary>Original English</summary>

We first made sure we had strong consistency by verifying the row level data counts, and then we ensured that we had strong integrity by checking the individual columns, making sure that the amounts matched from the legacy to the modern, making sure that the account information would match or the state withholding, the federal withholding. All of the attributes in the legacy database had to match to the to the cloud.
</details>

这里有一个重要的诀窍：千万不要过度设计这个方案，因为随着现代化完成，这些迁移代码最终都会被废弃。

<details>
<summary>Original English</summary>

A major tip here is that you don't want to over-engineer the solution because as modernization would complete, this code would then get deprecated.
</details>

### 生产者迁移：重构而非简单平移

现在我们来聊聊生产者迁移。在遗留状态下，我们的生产者通过三种方式调用我们的基础设施：第一种是通过服务请求（service request）；第二种是封装了该服务请求的 API；最后一种、也是可能最令人头疼的方式，是直接向数据库表进行插入操作（direct table inserts）——因为我们常常会在数据库中看到凭空出现的数据，却不知道它是怎么写入的，或者是谁生产了这些数据。

<details>
<summary>Original English</summary>

Now, let's talk about producer migration. Our producers called our infrastructure in three ways from the legacy state. One was through a service request. The second was an API that wrapped that service request. And the last and probably the most daunting was direct table inserts because we would see data appear in our database and we weren't sure how it got there or who produced that data.
</details>

因此，我们提取了通用的数据模式，并将其置于网关层之上，由该网关封装负责向云端写入数据的 API。此时，应当将现代化历程视为重新构想整个数据生态契机。

<details>
<summary>Original English</summary>

So, we took that common data schema and we put it onto a gateway that wrapped our APIs that would do our cloud data inserts. Now, take your modernization journey as an opportunity to reimagine your data ecosystem.
</details>

我们借鉴了金融科技（FinTech）领域的概念，例如幂等性（idempotency）。我们还确保了跨多写入者之间的强一致性。因此，我们采用了一种类似于 Snowflake ID 所提供的范式。我们进行了重新设计，而不是做简单的搬迁迁移（lift and shift）。

<details>
<summary>Original English</summary>

We took concepts from FinTechs such as item potency. We also ensured that we had strong consistency across multiple writers. And so, we used utilized a similar paradigm to what a Snowflake ID would provide us. We are reimagined and we didn't do a lift and shift.
</details>

现在，我们有了一套现代化的生产者服务。我们如何迁移现有的生产者呢？我们有 35 个生产者团队必须迁移到我们的新生态中。在早期阶段，我们不得不人工编写文档以协助这次过渡。

<details>
<summary>Original English</summary>

Now, we have a modernized producer offering available. How do we get our producers? We had 35 producers that had to then modernize to our ecosystem. Early on, we had to produce manual documentation to facilitate this transition.
</details>

随着 AI 工具的出现，我们把这些文档放进了公司的 Wiki，然后通过 MCP 服务器将其暴露出来。这带来的效果非常棒，因为在过去，经常会有很多团队找我们沟通，我们必须想方设法去跟进和组织所有这些沟通；而现在，所有这些来回沟通与对接工作都可以由生产者端直接通过提示词交互来完成。在引入 MCP 之后，我们看到我们团队需要处理的聊天咨询和生产者支持工作量大大减少了。

<details>
<summary>Original English</summary>

And as the AI tooling became available, we provided that documentation in our company's wiki, but then exposed it via the MCP server. And that was really great because what it did was we used to have many teams having chats with us, and we had to try to keep all of those organized. Now that communication and that back and forth could all be done via the prompt on the producer side, and we saw that the number of chats and and producer support that our team was doing was greatly reduced when we had the MCP available.
</details>

AI 工具在将状态从遗留生态转换到云端方面也做得相当出色。我们将云生态中的账本枚举（enums）设计成了人类可读的格式，而不是遗留生态中单纯的账本状态码。我们的 AI 工具在弥合从遗留生态到云端的意图差异上表现非常优秀。

<details>
<summary>Original English</summary>

The AI tools also did a really good job of transitioning state from the legacy ecosystem to the cloud. We made our cloud ecosystem, the ledger enums, to be human readable versus just ledger status codes in our legacy ecosystem. And so, our AI tooling did a really good job at bridging the gap of the intent from the legacy ecosystem to the cloud.
</details>

### 消费者迁移：多渠道与 Schema 治理

现在我们来看消费者迁移的路径。访问消费者级别的数据主要有三种方式：实时调用场景、批处理场景和流式处理场景。这之中的共同点在于，无论消费端通过哪种渠道访问数据，我们都提供了一个统一的 Schema 注册表（schema registry）。

<details>
<summary>Original English</summary>

So now let's look at the consumer migration path. We had three ways to access consumer level data. We had real-time use cases, batch use cases, and streaming use cases. And the commonality here is that we provided a schema registry, no matter which channel that your uh consumer would access that data.
</details>

针对“可用资金”（funds available）查询，这是我们流量最大、负载最高的实时 API，它直接决定了在客户账户上显示的余额是多少。他们会通过 GraphQL 来调用我们，并且他们只需订阅符合自身业务场景的特定属性。

<details>
<summary>Original English</summary>

And so, for a funds available, that's our most that's our most uh heavy traffic uh real-time API, and that goes into determining what is the balance that's displayed on your account. They're going to be calling us via GraphQL, and they're going to subscribe to only the attributes that meet their use cases.
</details>

对于批处理场景，可以联想到对账（reconciliation）或数据分析。我们的数据仓库会向每个独立的消费者暴露数据共享视图（data share views）。每个消费者告诉我们他们的业务用例，我们据此提供专门满足其数据需求的定制化视图。

<details>
<summary>Original English</summary>

Now, for batch use cases, think of reconciliation or data analytics. We have our data warehouse that will expose data share views to each individual consumer. Each of the consumers tells us their use case, and we provide a a view that's specific to their data needs.
</details>

这得到了我们数据治理团队的大力支持，他们坚决主张：只有需要特定数据字段的消费者才应该看到那部分数据。

<details>
<summary>Original English</summary>

This This was supported by our data governance team that strongly advocated that only the consumers that need the certain data attributes, they should only see uh those pieces of data.
</details>

最后一部分是流式传输。我们有一个 Kafka 事件主题，会把对数据库的所有插入和更新流式分发出去。我们的风控与反欺诈团队利用这一技术，将实时数据注入到他们的风控工具中。

<details>
<summary>Original English</summary>

Our last piece was around streaming. We have a Kafka event topic that we would stream all of the inserts and updates to that database. Our fraud teams were able to take take advantage of this technology to provide real-time data ingestion into their fraud tooling.
</details>

我们提供的是“至少一次交付”（at-least-once delivery）。因此，我们在生产者端贯彻的幂等性概念也延续到了事件流中。当他们订阅这种至少一次交付机制时，我们确保他们具备幂等且安全的操作保障。

<details>
<summary>Original English</summary>

We provided at least once delivery. And so, our concepts of item potency that we did through the producer side, we carried forward through the event streaming. And so, as they subscribe to at least once delivery, we made sure that they had item potent safe uh operations.
</details>

这样一来，如果某个批处理任务在中途失败，相关团队可以直接重试，而我们能够保证不会产生重复的账本记录。同时，事件驱动端的至少一次交付也确保了他们能够接收到所有生成的账本事件。

<details>
<summary>Original English</summary>

So, that if a batch job would would fail halfway through the process, those teams could retry, and we can ensure that we don't have uh duplicate ledgers being created. But, the at least once delivery from the eventing side ensured that they had all of the ledger events that were created.
</details>

### 接入治理与业务感知可观测性

在接入消费者时，我们整个组织内有 50 个不同的消费方需要我们的数据。在 Vanguard，当你接入一个应用程序时，需要注册一个三字符的应用代码（application code）来完成登记。这个应用代码描述了你的应用是什么以及它执行什么功能。

<details>
<summary>Original English</summary>

Now, when we onboarded consumers, we had 50 different consumers across our organization that needed our data. At Vanguard, when you onboard an application, you need to have a three-character application code to register to onboard. This application code describes what your application is and and what it performs.
</details>

但我们更进一步：我们要求消费者向我们提供业务用例的说明描述，以及他们需要这笔数据的业务合理性依据。

<details>
<summary>Original English</summary>

But, we took it a step further. We requested that our consumers would provide us a description and a business case justification for their need for the data.
</details>

试想一下：比如一个交易订单系统需要现金账本数据来履行交易的资金交割义务，这可以是一个业务用例；或者一个退休账户需要执行法定最低提取（mandatory distribution）；又或者一个 529 大学教育储蓄账户需要向大学学费账户注资。

<details>
<summary>Original English</summary>

And so, think about if I am a trade order that needs a cash ledger to fill fulfill the cash obligation of the trade, that could be a business use case. Or for a retirement account that needs to do a a required mandatory distribution. A 529 account could do a contribution to their college tuition account.
</details>

通过把所有这些业务描述归集在一起，AI 工具现在能够将其整理汇总，精准勾勒出在我们生态中已经完成了哪些现代化用例，同时我们也能明确掌握系统当前所支持的核心业务功能。

<details>
<summary>Original English</summary>

By grouping together all of these business descriptions, now the AI tooling can compile that together and provide an accurate description of what use cases have been modernized in our ecosystem, as well as we now have what is the top business functionality that we support.
</details>

我们还可以进一步询问：如果违反了 SLA，会造成什么样的影响？这至关重要，因为如果发生重大突发故障，当我们看到某个应用代码的可用性开始跌破 99.999%（五个九）时，我们可以立即查看并判断：对于批处理应用，我们可能有几个小时的响应窗口；但对于一个正在向终端客户报错的实时 API，我们只有几分钟时间，此时快速自愈分秒必争。

<details>
<summary>Original English</summary>

We can also take it a step further by asking what is the impact if our SLAs are breached. And this is critical because if you're in a major incident and if we see an app code that starts to go go below the five nines of availability, we can go in and we can see, okay, a batch application we may have hours to respond. A real-time API where there's a client on the other side that's receiving errors, we have minutes and time is of the essence to self-heal.
</details>

我们正在继续评估如何通过将业务用例合理性与可观测性及日志链路追踪相融合，来实现更快的响应速度。

<details>
<summary>Original English</summary>

We're continuing to evaluate how we can get faster response times by combining the business use case justification into our observability and and log traces.
</details>

### 经验沉淀：团队大脑与修复向前

回顾我们所学到的经验：我们认识到，尽管我们在这段历程的起步阶段甚至还没有现成的 AI 工具，但我们不断调整并持续拥抱新技术。这极大地助推了我们的技术调研、开发与测试。

<details>
<summary>Original English</summary>

So what we've learned, we've learned that although we started this journey before the AI tooling was even available, we adapted and continued to adopt the newer technologies. This greatly aided in our research, in our development, and our testing.
</details>

如今在我们的现金项目中，90% 的工程师每天都在使用这些 AI 工具。我们的团队采用多智能体工作流（multi-agent workflows），并且拥有共享知识库。我们正在持续演进这个 AI 框架环境（AI harness），以满足现代化改造的需求。

<details>
<summary>Original English</summary>

Today our cash program, 90% of our engineers utilize these AI tools on a daily basis. Our teams use multi-agent workflows, and we have shared knowledge bases. We're continuing to evolve this AI harness to meet our modernization demand.
</details>

我们引入了“团队大脑”（team brain）的概念：当工程师在构建产品功能时，这些知识会被存入一个公共存储中，供团队所有成员访问。如果有新工程师刚加入团队，他们可以直接调取这个通用知识库，这样他们提示词中包含的上下文就能与入职 5 年的老员工平起平坐。

<details>
<summary>Original English</summary>

We have the concept of a team brain that as engineers are are building out product features, that knowledge goes into a common storage where it's now accessible by all members on the team. And if there's an engineer that has just joined, they can tap into this common knowledge base, and now they have the same context in their prompt as an engineer that has been here for the last 5 years.
</details>

此外，在现代化进程中，同时维护两套代码库是非常具有挑战性的。你所应该做的是：坚持“向前修复”（fix forward），不要去修补过去。

<details>
<summary>Original English</summary>

Now, when you're in a modernization process, maintaining two code bases is challenging. And what you'll want to do is you'll want to continue to fix forward. Don't fix the past.
</details>

当你遇到可能已经存在了几十年的历史 Bug 时，继续在现代化状态的代码中进行修复，并将此作为驱动生产者和消费者迁移到云端的动力。

<details>
<summary>Original English</summary>

As you encounter bugs that have may have listed have existed for decades, continue to fix the modernized state and allow that to be the incentive for your producers and your consumers to modernize to the cloud.
</details>

不过，这会干扰审计日志的对比结果，因此你必须具备白名单机制，这一点非常关键。最后一点是确保拥有正确的度量指标、告警和可追踪性，因为随着产品的持续发展，你会经常审查这些内容。

<details>
<summary>Original English</summary>

Now, this will throw off your audit logs, so you'll want to have white listing available, and that's really critical. And the last piece is ensure that you have the right metrics, alarms, and traceability, because you're going to review those often as your product continues to grow.
</details>

### 技术领导力视角的五大核心建议

既然这是一个面向技术领导力的专场，我想着重强调五大核心要点：

第一点：**让你的遗留代码库变得可被 AI 查询**。通过 MCP 服务器开放我们的遗留代码库，缩短了技术调研的周期并加快了反馈回路——从 7 天缩短到了 15 分钟，这是一个巨大的成功。

<details>
<summary>Original English</summary>

Now, because this is a leadership track, I want to call out five main points. Number one was make your knowledge make your legacy code base AI queryable. That exposing that via an MCP server, our legacy code base it cut that research cycle time and gave quicker feedback loops. That's 7 days down to 15 minutes. That was a huge win.
</details>

第二点：**将迁移文档视为产品的一部分**。你的迁移文档与业务功能一样关键，因为这是所有生产者接入应用所必须依赖的指南。虽然在过渡期结束后这些文档最终会被淘汰废弃，但在过渡期内，迁移文档至关重要。

<details>
<summary>Original English</summary>

Treat your migration docs as part of your product. It needs to your migration docs are just as in critical as your business functionality because that's what all of your producers are going to utilize to onboard to your application. Eventually, yes, those will get deprecated out but for that interim process those migration docs are critical.
</details>

第三点：**重新设计与构想，不要只是简单平移（lift and shift）**。我们在协助迁移过程中遇到最大困难的消费者和生产者，恰恰是那些只想直接把旧系统一对一硬搬到新系统的人；而相比之下，那些愿意退一步思考“我们如何利用现金账本生态所提供的现代能力更好地演进自身产品”的团队，迁移往往更顺利。

<details>
<summary>Original English</summary>

Reimagine and don't lift and shift is is the third point. The consumers and producers that we had the most trouble onboarding to our modernized state were the ones that wanted to do a direct lift and shift transfer of old to new versus those that took a moment to step back and say, "How could we better evolve our product by taking advantage of the modern capabilities that the cash ledger ecosystem provides?"
</details>

第四点：**循序渐进地引入 AI**。随着新 AI 工具的出现，你需要不断完善自己的产品。在我们身处的当下，永远不会有完美的起跑点。最重要的是立即行动起来，并随着技术的迭代不断增强和适应。

<details>
<summary>Original English</summary>

The fourth component is adopt AI incrementally. As the AI tools arrived, you continue to enhance your product. There's never going to be a perfect starting point in the world that we live in today. The important thing is that you get started and you continue to enhance and adapt as the technology changes.
</details>

最后一点：**可观测性是不可妥协的底线**。你必须清楚知道谁在生产你的数据、谁在消费你的数据。当你的产品进入日常运维（BAU）状态、现代化改造全部完工后，团队需要将其作为日常运营来提供支撑，这时这一点就显得尤为关键。

<details>
<summary>Original English</summary>

Last piece is observability is non-negotiable. You need to know who's producing your data and who's consuming your data. And this is ever more important as your product goes to BAU and once the modernization is complete, your teams will now have to support this as their uh daily operations.
</details>

非常感谢大家。如果还有时间，我们可以接受提问；如果没有时间，我会在会议室外等候，大家稍后可以与我交流。再次感谢大家给我这次机会。

<details>
<summary>Original English</summary>

Thank you very much, all. If we have time, we'll take questions. Otherwise, I'll be outside of the room. You can connect with me later. And thank you again for the opportunity.

>> [applause]
</details>