---
author: AI Engineer
date: '2026-10-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=CLve4Nx_RwI
speaker: AI Engineer
tags:
  - unstructured-data
  - vector-search
  - ai-agent
  - information-retrieval
title: 桥水基金如何将上亿份非结构化文档转化为投资优势
summary: 桥水基金应用 AI 负责人 Sam Green 与产品工程负责人 Aaron Linsky 介绍了非结构化数据平台 Vault。该平台整合超 1 亿份内外部文档并对齐内部本体，通过解决人类与 Agent 的差异化检索需求、引入 Turbo Puffer 原生过滤攻克规模与性能难题，并依托 Investor Workbench 推动 Agent 从被动工具转向主动协作，加速投资研究复利。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Sam Green
  - Aaron Linsky
companies_orgs:
  - Bridgewater Associates
  - Turbo Puffer
products_models:
  - Vault
  - Ayla
media_books: []
status: evergreen
---
### Vault 平台的构建背景与核心经验

大家早上好。我是桥水基金（Bridgewater Associates）应用 AI 团队负责人 Sam Green，这位是我的同事 Erin Lensky。

今天我们在这里想和大家探讨 Vault，这是我们在桥水构建的一个数据平台，旨在将非结构化数据转化为我们投资流程中的一等资产。

在今天上午的演讲中，我们希望分享构建 Vault 过程中学到的三点经验。

第一点是，人类和 Agent 对数据平台的需求截然不同。因此，你必须针对这些不同的需求分别进行构建。

第二点是，当单一工具能够同时满足这两组需求时，所产生的成效最大。

第三点是，真正的核心价值在于，当你能够建立必要的基础，让 Agent 成为你投资流程或具体业务中的主动参与者，而不是仅仅作为供人类使用的被动响应工具。
<details><summary>Original English</summary>
[music]

Good morning everyone. I'm Sam Green, team lead for applied AI at Bridgewater Associates, and this is my colleague Erin Lensky.

And today we're here to talk to you about the Vault, the data platform that we've built at Bridgewater to turn unstructured data into a first-class asset in our investment process.

And as part of the talk this morning, we'd like to share three lessons that we've learned building the Vault.

The first is that humans and agents have very different needs from a data platform. And so you have to build for those different needs separately.

The second is that the greatest impact occurs when a single tool can meet both of these sets of needs at the same time.

And the third is that the real prize is when you can build the foundations needed to make agents a proactive participant in your investment process or whatever you're doing with your with your your tools instead of a reactive reactive tool for your humans to use.
</details>

在深入介绍 Vault 之前，我想先介绍一些关于桥水的背景。

在过去的 50 年里，桥水一直在不懈追求对市场和经济运行机制达到全球最深刻的理解。并将其转化为系统化的代码编码，以便我们随着时间的推移对其逻辑进行压力测试。

最初只是一本黄色拍纸簿上的一组 if-then 规则，后来演进为一个以人类为中心的持续复利过程，人类在其中不断探寻市场中正在发生的下一项变化。最近，我们一直在致力于构建人工投资助理 Ayla，它将机器置于这一持续流程的中心。

在所有这些演进阶段中，我们始终秉持着一个不变的理念：我们要持续观察世界的变化以及世界上正在发生的事情。察觉哪些动态尚未编码进我们的理解中，并利用这些认知不断改进并在未来实现复利。

在桥水历史的大部分时间里，这意味着在结构化数据上构建并维护时间序列模型。这些结构化数据需要经过精心构建，以确保可以安全用于我们的研究流程，并与我们的内部本体及世界模型保持一致，从而让我们能够充分利用所构建的数据。
<details><summary>Original English</summary>
Before I I dive deeper into talking about the Vault, I wanted to start with some some background about Bridgewater.

Over the last 50 years, Bridgewater has been in the constant pursuit of the world's best understanding of how markets and economies work. And turning that into a systematic encoding that we can use to stress test our logic over time.

And what originally began as a set of if-then rules on a yellow legal pad evolved into a continuous compounding process with humans at the center constantly looking for the next thing that's changing in markets. And more recently, we've been working on building Ayla, the artificial investment associate, which puts a machine at the center of this continuous process.

Across all these phases of evolution, we've had a constant philosophy in mind, which is that we want to be constantly looking at how the world is changing and what's going on in the world. Noticing what what dynamics are not yet encoded in our understanding and use that learning to improve and compound for the future.

For most of Bridgewater's history, that meant building and overseeing time series models on structured data. And that structured data needed to be carefully built so that it could be safe for use in our research process and aligned to our internal ontology and world model so that we could get great leverage out of using the the data that we had built.
</details>

随着语言模型的出现，我们迎来了与更广阔的数据世界互动的巨大新机遇。例如新闻、研究报告、政策文件，以及此前仅存在于无形之中的所有内部交流——公司内部的备忘录、会议记录和各类研讨。

我们很快意识到，所有这些数据若要达到可用标准，都需要经过完全相同的处理。它们必须经过仔细清洗、治理，并随时可用于当下的即时研究问题，以及长期的系统化研究。

当我们审视外部的数据供应商和数据平台提供商格局时，没有一家能提供我们建立和维持数据优势所需的全部控制权。

因此，我们构建了 Vault，它是我们汇聚外部和内部非结构化数据的存储库。同时也是一个平台，负责对所有这些数据进行索引、组织，并使其可供我们的人类投资人员与 Agent 使用。

如今，Vault 中拥有超过 1 亿份文档，每天、每分钟都在从 135 个外部数据源持续新增数千份文档，并且这个规模还在不断扩大，此外还包含来自桥水内部的所有数据。至关重要的是，所有这些数据并不是简单地堆到我们投资人员的桌上。它们经过了精心梳理，与我们的内部本体严格对齐，并附带有诸如文中所讨论的国家、概念、市场，以及最重要的时间段等丰富维度。
<details><summary>Original English</summary>
With the emergence of language models, we had a huge new opportunity to engage with a with a much wider world of data. Um, you know, news and research transcripts, policy documents, and all of the internal conversation that was previously just in the ether. So, the internal memos and meeting transcripts and debate happening inside the firm.

We quickly realized that all of that data needed the exact same treatment to be fit for purpose. It needed to be carefully cleaned, governed, and made ready for use in both point-in-time research questions today and also our systematic study over time.

And when we looked out at the landscape of data vendors and data platform providers, there was nothing that provided us with all of the control that we needed to build and maintain our data advantage.

And so, we built the Vault, which is our repository of external and internal unstructured data. Um, and the platform that indexes, organizes, and makes all of it ready for use by our human investors and agents.

Today, the Vault has more than 100 million documents in it with thousands more added every day, uh, minute by minute, from 135 external sources and again growing all the time, as well as all of the data from inside of Bridgewater. And crucially, all that data is not just dumped on our investors' desks. It is carefully aligned to our internal internal ontology with enrichments like the countries, concepts, markets, and most importantly, time period discussed in the document.
</details>

为了生动说明这一点，我想先举一个简单的启发性例子。我向一个企业级聊天客户端提出了一个相当基础且具有代表性的投资问题。我问：“AI 基础设施投资对韩元产生了怎样的影响，市场参与者是否预期这种情况会持续？”

正如大家肯定都很熟悉的那样，Agent 会访问网络并寻找可引用的资源，因为我明确要求它去寻找其他人对这个问题的看法。

大家可以看到，它聚焦并找到了 15 个看起来相关的资源以供参考，然后向我返回了答案。

当我仔细查看它给出的回答时，有几点引起了我的注意。首先是，尽管它找到了 15 个看起来相关的信源，但最终只挑选了一两个来回答我的问题。

其次是在回答的最底部，Agent 自己承认它并没有回答我的问题。它在公开网络上没有找到足够的文档来确立市场共识，无法满足我设定的参数要求。
<details><summary>Original English</summary>
To bring this to life, I want to start with a a quick motivating example. So, what I did here is I asked a fairly basic representative investment question to an enterprise chat client. I asked, "How is AI infrastructure investment impacting the Korean won, and do market participants expect this to continue?"

And as as you're all I'm sure familiar with, the agent goes to the web and looks for resources it can draw on because I've explicitly asked it to go find uh other people's perspectives on the question.

And you can see it it zooms in and it finds 15 relevant-looking resources to draw on uh before it gives me back its answer.

And when I when I zoomed in on the answer it gave back, a couple of things stood out to me. The first is that even though it found 15 relevant-looking sources, it only picked one or two to answer to answer my question.

And the second is down at the end of this response where the agent itself acknowledges that it hasn't answered my question. It didn't find enough documents on the open web to establish a market consensus and meet the meet the parameters that I laid out.
</details>

当我进一步深入探究时，问题变得更加严重。

它用来回答我问题的主要参考研报之一，居然远在 2026 年 7 月就已发布，尽管我提出这个问题并截取这个回答是在刚过去的周末，也就是 10 月初。在 AI 和投资领域，三四个月的时间跨度非常巨大。仅仅依赖这种资料来回答我的问题，根本远远不够。

而当我将完全相同的查询接入 Vault 时，发生的情况则截然不同。

首先，与 Vault 的连接促使 Agent 明确它应该针对特定的时间段来回答我的问题，因此它聚焦于 10 月 1 日到 10 月 8 日。由于 Vault 拥有更庞大的、针对投资问题的专业语料库，它在这一特定时间段内找到了范围更广的资源——多达 52 份相关候选文档。

当它最终回答我的问题时，它引用了 7 份文档，而不是仅仅一两份。并向我反馈了一个充实的答案，Agent 对这个答案能解决我的问题也更加确信。

因此对我们而言，这就是从构建 Vault 中得出的重要经验，也是今天这场演讲的核心动力所在：要让 Agent 产生实际成效，离不开优质的数据和恰当的连接器。

现在我把发言权交给 Aaron，由他来谈谈构建 Vault 过程中的一些产品工程经验。
<details><summary>Original English</summary>
When I double-clicked even further, the problem got even worse.

One of the notes that it primarily drew on to answer my question was published way back in July of 2026, even though I asked this question and captured this answer just at the end of last week in early October. In the age of AI and in investing, four 3 months is a massive amount of time. It's not even close to good enough to draw uh draw on this resource to answer my question.

When I ask this exact same query attached to the vault, something totally different happens.

The first is that the connection to the vault helps to prompt the agent that it should look for a specific period of time when answering my question, so it zooms in on October 1st to October 8th. It finds a much wider array of resources, 52 candidate documents that are relevant to the query over this specific period of time because of the vault's much more significant corpus of content that's relevant to investing questions.

And when it ultimately answers my question, it draws on seven instead of only one or two. And gives me back a rich answer that the agent is more confident is going to address my question.

And so for us, this is the the big lesson of from building the vault to kind of motivate the talk today, which is that it takes great data and the right connectors to make agents impactful.

And I'm going to talk hand it over to Aaron now to talk about some of the product engineering takeaways from building the vault.
</details>

### 检索架构设计：兼顾人类与 Agent 的双重视角

>> 谢谢 Sam。

大家好，我是 Aaron。我在桥水负责产品工程。接下来我将带大家了解过去几年我们在构建 Vault 过程中的一些心得。首先我想说的一点可能显而易见，但我认为仍然值得强调：搜索本身就很困难。

但如果我们同时面向两种截然不同的用户进行设计，这项工作就会变得更加困难。在我们的场景中，我们是在同时为人类和 Agent 进行设计。

我先从人类自身开始，来梳理两者之间的差异。人类需要高精度和高信噪比，因为我们能阅读的内容非常有限。即使是一个阅读速度极快的人，每分钟也只能阅读大约 300 个单词，而我个人的速度还要慢得多。

Agent 则是另一种完全不同的阅读者。它们对精度的敏感度要低得多。只要数据在那里，它们就能找到。基本上你递给它们的任何内容，都会被注意力机制所处理。它们的扩展速度极快，阅读速度大约是人类的 100 倍，达到每分钟 30,000 个单词。

因此，我们构建 Vault 必须兼顾这两种需求。

当我们考量关键维度时，屏幕上展示了五项：召回率（recall）、精确度（precision）、过滤能力（filtering）、权限控制（entitlements）和规模扩展（scale）。其中一些对人类更重要，一些对 Agent 更重要，许多则对两者都重要。

我将重点深入探讨其中的三个维度：面向人类的精确度、面向 Agent 的规模扩展，以及兼顾两者的过滤能力。
<details><summary>Original English</summary>
>> Thanks, Sam.

So, hi. I'm Aaron. I run product engineering at Bridgewater. I'm going to take us through a few of our learnings from building the vault over the past few years. I'm going to start with one that might seem obvious, but I still think it's worth saying, which is search is hard.

But it gets even harder if we're designing for two different consumers. And in this case, we're designing for humans and agents.

I'm going to go over the difference here starting with us. So, humans need precision and a high signal-to-noise ratio because we can only read so much. Even a fast reader manages about 300 words a minute, and personally, I'm much slower.

Agents are a different kind of reader. They're far less sensitive to precision. If the data is there, they'll find it. And basically, anything you hand to them will get attended to. They scale super quickly and they come and they consume about uh a hundred times faster, 30,000 words per minute.

And so we need to build Vault for both of these.

And when we're thinking about the dimensions that matter, there are these five on on the board. Recall, precision, filtering, entitlements, and scale. Some of them matter to people, some matter more to agents, many to both.

I'm going to go deep on three of these. Precision for people, scale for agents, and then filtering for both.
</details>

首先是精确度。

在我们由数据团队和法务团队付出巨大努力将 Vault 填满内容之后，召回率已经不再是一个紧迫的问题。然而，排在第一位的抱怨却是“Vault 的搜索太难用了”。

作为一名产品负责人，听到这种反馈确实令人难受，但我的回应是：让我们建立基准测试来进行评估。我们正是这么做的。

我们收集了许多问题，并通过人工方式找出最佳文档，其中也包括那些看似有用但实际上无用的文档。总计大约有 200 个样本，我们花了不到一周的时间完成。这项工作虽然枯燥且并不光鲜，但非常有用。

测试运行之后，结果显而易见：搜索确实很差。我们关注的核心指标是 Precision@10，即在前 10 个返回结果中，有多少是正确的文档。当时我们的命中率只有大约 60%。所以大家批评得没错，确实很差。

但现在我们有了一种衡量所有改进的方法。屏幕上展示了其中的五项改进措施。等到我们完成 Agentic 搜索的优化时，我们的 Precision@10 指标已经提升到了 90% 到 95%。
<details><summary>Original English</summary>
So, precision.

Once we've filled the Vault, our which was a heroic effort by our data and legal teams, recall was no longer a pressing issue. However, the number one complaint was Vault search is bad.

As a product owner, it's painful to hear that, but my response was let's benchmark it. And that's what we did. We collected questions and found the best documents by hand, including ones that looked helpful but weren't. In all In total it was about 200 examples and it took us less than a week. It was not fun or very glamorous, but it was very helpful.

And after we ran it, it was very clear. Search was bad. The key metric we were looking at is precision at 10, which is of the top 10 results, how many are the right documents. And we were hitting about 60%. So, the people were right, it was bad.

But now we had a way to measure all of the improvements. And here on the board are five of them. And by the time we got done with Agentic search, we were up in the 90-95% uh recall at 10 or precision at 10.
</details>

好的，以上是关于精确度的部分。接下来谈谈过滤能力。

同所有人一样，我们希望获取最相关的文档。但当我们分析生产环境的追踪日志时，我们发现几乎每一次查询都包含某种限制条件，要么是截至某个特定日期，要么是来自某个特定信源，要么是关于某项具体资产。

所有这些都需要高级过滤能力，而这正是我们遇到第一个重大性能瓶颈的地方。

这里我快速讲一下相对偏技术的细节。传统上，过滤向量数据库有两种方式。后过滤（post-filtering）会首先使用向量索引进行检索，然后再通过元数据对排名靠前的结果进行过滤。这种方式速度快，但召回率可能会很低，因为全局相关的结果可能并不符合你的过滤条件。

另一端是先过滤（pre-filtering），我们会先执行条件过滤，然后针对匹配到的每一个结果计算向量距离。这种方式的优势在于召回率极佳，但速度可能会非常慢，而我们需要的是介于两者之间的方案。

这促使我们尝试并最终切换到了 Turbo Puffer。他们采用被称为原生过滤（native filtering）的机制，只在包含匹配项的最近聚类中进行查找，并仅对这些聚类进行打分计算。最终你获得的效果是：速度上媲美后过滤，但在召回率上非常接近先过滤。
<details><summary>Original English</summary>
All right, so that was precision. Now on to filtering.

Like anyone, we want the most relevant documents. But when we looked at the production traces, what we were seeing is that almost always there was some condition, either as of a certain date or from a certain source or about a specific asset.

And all of that requires advanced filtering, and that's where we ran into our first major performance issue.

So I'm going to quickly go through this of a little bit technical here of there's classically two ways to fill filter a vector database. Post filtering will use that vector index first and then filter the top results by metadata. It's fast, but recall could be pretty low because the globally relevant results might not match your filters.

On the other side, we have pre-filtering where we'll filter first and then calculate distances for every one of those matches. The advantage there is that the recall is very good, but it can be very slow, and we needed something in between.

So that's what led us to try and then ultimately switch to Turbo Puffer. Their approach, which they called native filtering, looks only in the nearest clusters that contain matches and then scores just those. What you end up getting is something that's fast like post filtering, but with close to the same recall as pre-filtering.
</details>

最后，我想谈谈规模扩展。

对我们来说，人类的访问规模是相对平缓的，每小时大约 100 次查询。我们有 300 名用户，他们只是隔一段时间进行一次搜索。我们的用户需要花费数分钟来阅读他们收到的文档。相比之下，Agent 的规模则要高出几个数量级，轻松就能达到每秒 100 次以上的查询，而 Agent 集群的并发查询量更可以轻松突破数千次。

正如我之前所说，它们在几秒钟内就能读完文档。因此我们需要一个同样具备高扩展能力的架构，而 Turbo Puffer 同样轻松应对了这一挑战。

这样我们就覆盖了所有五个维度。今天我没有展开讲权限控制，但我会在今天晚些时候再谈。

我们覆盖了所有这些维度，这解锁了全新的工作流。

但这并没有改变我们研究人员的工作方式。他们每天早上依然不会主动打开 Vault。
<details><summary>Original English</summary>
And lastly, I'm going to talk about scale.

Human scale for us is pretty pedestrian, 100 queries an hour. We have 300 users. They're going to search, you know, every so often. It takes our users minutes to read the docs that they're that they're receiving. Agents on the other hand are a few orders of magnitude beyond that, easily 100 plus queries a second, and agent swarms can hit thousands easily.

And they obviously, will read, as I said earlier, will read docs in seconds. So we needed something that could scale as well, and again, Turbo Puffer handled that easily, too.

So we were covering all five dimensions. I didn't talk about entitlements, but I'll be talking about that later today. Um but we covered it all. It unlocked new workflows.

But it didn't change how our researchers worked. They still weren't coming to Vault every morning.
</details>

### 习惯迁移与应用落地：从 Pocket Analyst 到系统化预测

这便引出了我想在这里分享的第二个教训：无论工具多么出色，我们不能仅仅把它扔到投资人员的办公桌上就指望他们会去使用。我们需要将他们的旧习惯迁移到新的形式中。

因此，我们观察了他们原有的工作习惯。他们中的许多人日常都离不开电子邮件。研究资料直接来自券商；他们有订阅列表；他们设置了规则将所有邮件过滤分流到各个文件夹中。这套流程行之有效，令他们感到熟悉，并且他们确信自己不会遗漏任何信息。

所以我们必须把所有这些功能都做进 Vault 中。

这也正是我们的做法。平台内所有内容都支持搜索；订阅列表变成了“已存搜索”（saved searches）；文件夹变成了“已存收藏集”（saved collections）。还是原来的习惯，只是换了一个新阵地。

一旦把他们吸引到了这里，我们就能开启新的习惯。

正如 Sam 刚才演示的那样，他们可以跨越所有数据提出问题；他们可以按主题追踪动态推送；他们还可以将这些收藏集直接移交给自己的 Agent 以采取进一步行动。正是在这个时候，我们明确实现了产品与市场的契合（PMF）。

一旦达到了这种契合度，用户便希望随处都能使用它。于是我们把它接入了聊天界面，开发了手机应用，整合进了 Slack 和他们的 IDE 中。当然，我们也将所有这些能力开放给了 Agent，包括提供了一个命令行界面（CLI），因为 Agent 非常偏爱 CLI。
<details><summary>Original English</summary>
And that's my second lesson that I want to share here is that no matter how amazing the tools are, we can't just drop them on our investors' desks and expect them to be used. We need to migrate their old habits into an a new form.

And so we looked at what they were already doing. Many of them were living in email. The research came straight from the brokers. They had subscribed lists. They had rules that filtered everything into folders. It worked. It was familiar. And they knew that they weren't missing anything.

So we had to build all of these features into the Vault.

That's exactly what we did. Everything's searchable. The subscribe lists became saved searches. And folders became saved collections. It's the same habits, just a new home.

And once we had them there, we can open up new habits.

So we can ask they can ask questions across all the data as Sam showed. They can follow dynamic feeds by topic. And they can hand those collections over to their agents to take further action. And that's when we clearly had product market fit.

And once we had that fit, the users wanted it everywhere. So we put it in chat. We made a phone app. It's in Slack in their IDE. And of course, we availed all of that to the agents as well. Um including a a CLI because agents love CLIs.
</details>

那么这里的核心问题是：这一切究竟赋能了什么？

Sam 稍后会介绍我们目前正在构建的内容。但首先也是最重要的一点是，它正在帮助我们更快地在研究循环中向前推进。

借助我们的 Pocket Analyst——这是我们的第一个 AI 分析师——它依托 Vault，仅需几分钟、花费几美元，就能完成数小时的研究工作。

目前我们正在将其扩展为 Researcher，这是下一代系统。它基于相同的理念，但研究周期可以延伸至数天或数周。

我们还能够训练定制模型，以便更智能化地对 Vault 中的数据进行推理，并将这些模型与其他基础模型结合使用，为系统化的决策流程提供输入。Forecaster 是我们的第一个此类模型，它能够生成由 AI 驱动的宏观相关预测。

此外，我们还基于 Vault 构建了投资信号，将非结构化数据转化为结构化且可交易的策略。

现在我把发言权交还给 Sam，请他带领我们了解 Vault 的最新功能。
<details><summary>Original English</summary>
And so the main question here is okay, so what does this enable?

Sam's going to talk about what we're building right now. But first and foremost, it's helping us to move around that research circle faster.

With our pocket analyst, which is our first AI analyst, it can do it can do hours it can do hours of research in just a few minutes for a few dollars. And that's relying on the Vault.

And then we're expanding now with the researcher, which is the next generation. It's the same idea stretched across days or weeks.

We're also able to train custom models to more intelligently reason over the vault's data and use those together with other foundation models to feed systematic decision-making processes. The forecaster is our first one, which produces AI-generated macro-relevant predictions.

And then, we also have a built investment signals from the vault, turning unstructured data into structured, tradable strategies.

Now, I'll hand it to Sam to take us through Vault's latest capability.
</details>

### 迈向主动型 Agent：Investor Workbench 与知识复利

>> 谢谢。

正如我在演讲开始时所提到的，真正的核心价值在于，当你能够将 Agent 从一个随时准备回答人类提问的被动资源，转变为主动的参与者，协助引导你的高价值专业人员关注最需要他们投入精力的领域。

我们解决这一问题的方式是打造一种被称为 Investor Workbench（投资工作台）的体验。在该体验中，Agent 保持常驻运行，追踪对该投资人员至关重要的事务，并将最需要他们关注的领域呈现在他们面前。

它依托于 Vault，呈现出类似这样的交互体验：系统会提出一个主题，并将多项信息呈现在投资人员面前，供其决定是该深入挖掘还是完全忽略该主题。

大家可以在这里看到投资人员所看到的卡片界面，借此决定是否要就我们在演讲前面讨论过的同一个“AI 对汇率影响”问题进行更深入的探究。

投资人员会获得所需的一切：如果他们想快速浏览 Agent 的调研结论，可以查看一份 Agentic 摘要；他们还能看到 Agent 所依据的确切证据，从而能够自行评估促成该建议的原因是什么。如果他们选择进一步深入挖掘，还可以直接关联到 Aaron 刚才介绍的分析工具所生成的研究产出。
<details><summary>Original English</summary>
>> Thanks.

So, like I alluded to at the beginning of the talk, the real prize is when you can take agents from a reactive resource that can be ready to answer a a human's question and instead make them proactive participants helping to steer your high-value professionals towards the most important areas for their attention.

And the way that we're solving that problem is in an experience we're calling the investor workbench, where the agent is always on, tracking what's important to that investor, and presenting them with the areas that are most in need of their attention.

It looks like an experience like this that relies on the vault, where a topic is proposed and several pieces of information are presented to the investor to decide whether they should dig deeper or ignore that topic entirely.

You can see here the card that an investor sees in order to decide whether to dig in deeper into the same AI impact on currencies question that we looked at earlier in the talk.

And the investor receives everything they need, an agentic summary if they want a quick scan across the agent's findings. They also get the exact evidence that the agent was drawing on, so they can assess for themselves what was leading to this recommendation. And if they choose to dig deeper, they have a direct connection to the research output from the analytical tools that Aaron was just describing.
</details>

当他们与 Agent 协同深入探究驱动该问题的各种动态时，这些认知成果会被自动沉淀下来，他们协作产生的结果会自动被捕获并存回 Vault 中。

因此，对我们而言这就是关键经验：Vault 实现了复利累积，因为它为我们的投资人员和 Agent 在指尖提供了恰当的证据、恰当的内部及外部补充信息，并且能够自动捕获他们提炼的综合分析成果，重新放入语料库中供下一轮使用。

这使我们能够更快、更好地运转整个研究循环。

回顾我们最初提出的问题：要让 Agent 发挥作用，需要恰当的上下文环境，以及对你所处业务世界中正在发生的事情有恰当的理解。

因此，我们想向大家提出的问题是：你们的 AI 是否了解世界上正在发生什么？它是否记得你们公司对此积累了哪些认知？因为我们正在这样训练我们的 AI。如果这对你们来说听起来也是一个令人兴奋的挑战，我们非常乐意与大家交流。谢谢大家。
<details><summary>Original English</summary>
And when they dig deeper alongside the agent to look at the dynamics driving this question, the learnings are automatically captured, the results of their collaboration are automatically captured back in the vault.

And so this for us is the key lesson. The vault enables compounding because it provides the right evidence, the right extra internal and external information at the fingertips of our investors and agents, and it automatically captures the synthesis that they generate and puts it back in the corpus for the next turn.

And that makes us go around the circle faster and better.

And so when we think back to our the the question we began with, what it takes to make an agent work is the right context and the right understanding of what's going on in your world.

And so our question for you is, does your AI know what's going on in the world? And does it remember what your firm has learned about it? Because we are teaching ours too. And if these sounds like an sound like an exciting challenge, we'd love to talk. Thank you.

[applause]
</details>