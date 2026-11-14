---
author: AI Engineer
date: '2026-10-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=qq2Hm4XNRgI
speaker: AI Engineer
tags:
  - agent-memory
  - context-management
  - retrieval-augmented-generation
  - database
title: 从 RAG 到 Agent Memory：决定智能体该记住什么与记忆晋升机制
summary: Oracle AI Database 技术市场负责人 Wojtek Pluta 探讨了 AI 智能体记忆系统。他指出 RAG 仅代表读取路径，而记忆是写入路径；需通过分类、比对与护栏机制进行“记忆晋升”，并介绍了 Oracle 的 agent memory 架构与上下文卡片设计。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Wojtek Pluta
companies_orgs:
  - Oracle
products_models: []
media_books: []
status: evergreen
---
### 背景介绍与从 RAG 转向记忆系统

我叫 Wojtek，Wojtek Pluta，在 Oracle 工作。在过去的 10 年里，我一直在 Oracle 工作。我参与过各种各样的项目，包括与英国的一些银行合作开展客户体验房贷用例等项目，或者像早期非接触式支付刚兴起时的相关项目，以及开放银行业务的举措。

<details>
<summary>Original English</summary>
Uh my name is Wojtek. Uh Wojtek Pluta, and I work at Oracle. And over the last 10 years, I've been working um at Oracle. I worked at the various projects um including working with some banks in the UK on projects like customer experience mortgage use cases or things like early contactless payments when um when it was still uh sort of emerging and open banking initiatives.
</details>

现在，我在 Oracle AI Database 负责技术市场团队。此前，我也花了一些时间在我们的云基础设施上从事云原生和 AI 方面的工作。

<details>
<summary>Original English</summary>
Now, I am uh heading up the technical marketing team uh at Oracle AI database. And before, I spent a bit of time also um working on cloud native and AI on our cloud infrastructure.
</details>

所以我今天想讲的是从 RAG 转向记忆系统，以及 RAG 如何为我们提供有用的读取路径，但记忆系统能让我们基于自身的数据创造出独特的业务价值。

<details>
<summary>Original English</summary>
So, what I'm going to talk about today is the um the moving from rack to memory systems and the notion how rack gives us a useful read path, uh but memory system allows us to uh create unique business value based on your data.
</details>

### 交互演进与智能体架构

多年来，我们经历了一种界面优化的概念，主要是让交互界面在互动方式上更加直观。作为整个社会，我也亲身体验并见证了我们与系统的交互是如何从基于命令、点击和键入的操作，转变成我们现在所拥有的这种基于意图的系统。这显然为这种按需或即时软件创造了机会。而在这种背景和期望之下，我认为保持某种连续性是很重要的。

<details>
<summary>Original English</summary>
So, over the years, we went through this notion of interface optimization uh predominantly making interfaces more intuitive in terms of how we interact with them. And as a society, and I experienced that seeing sort of how our interactions with the systems moved from sort of this command-led uh click and and type into what we have right now, this intent-based uh uh systems. And um which obviously creates opportunity for this sort of on-demand or just-in-time software. And within that context and within those expectations, I think uh creating a some sort of continuity is important.
</details>

对我来说，过去几年 AI 技术栈一直相当稳定。模型层和基础设施层可能已经大宗商品化了，但在我看来，数据层才是你获得竞争优势的地方，因为它是属于你的。

<details>
<summary>Original English</summary>
So, for me, the AI stack has been pretty consistent for the last few years. Um there is probably models and infrastructure layers are commoditized, um but the data layer, in my opinion, is where you gain competitive advantage cuz it's, you know, it belongs to you.
</details>

在 Oracle，关于如何看待智能体以及如何定义它们，我们采用了和大家相同的模式：**模型加上执行框架（harness）**。显然，我们在某种程度上访问的模型是相对静态的，它们会建议该做什么。然而，执行框架最终决定并掌握着运行时的决策以及周围的各种检查。所以，执行框架显然就是围绕模型构建的代码。

<details>
<summary>Original English</summary>
And at Oracle, we adopted the same model as everybody else in terms of how we think about agents and how we define them with model plus the harness. And obviously, the models we sort of are relatively static in the way that we have access to them and to the certain extent. Um and then they suggest what to do. However, the harness in the end decides, you know, and owns the runtime decisions. And the checks around it. So, um you know, so the harness is the code obviously around the the model.
</details>

为了今天的演讲，也是为了让它不那么抽象，我将使用一个小虚拟形象。来见见 Intelligence 吧。我特意决定省略任何前缀，并且本着 AI 领域最新的讨论热点以及万圣节临近的氛围，我决定为 AI 工程师制作一个特别版，对外观做了一点更新。

<details>
<summary>Original English</summary>
So, the for the purposes of today, um and to make it a little bit less abstract, I'm going to use a little avatar. Uh so, meet intelligence. Uh I um yeah, uh purposely decided to skip it skip any prefixes and um in the spirit of sort of the latest chatter that's happening in the AI and hollowing around the corner, I sort of decided to make a special edition for AI engineer and updated uh the look a little bit, right?
</details>

### 记忆晋升机制：读路径与写路径

但从根本上说，RAG 系统可以包含会话状态，但光靠检索本身并不能告诉我们什么内容应该在交互结束后留存下来。因此，**检索是读取路径，而记忆是写入路径**。当智能体看到值得保留的内容时，我们应该将其晋升为一条记录，以便日后使用。

<details>
<summary>Original English</summary>
So, but um so, the fundamentally rack systems, um you know, can include conversational state, uh but retrieval alone doesn't tell us what should survive the interaction. So, retrieval is the read path and memory is the write path. So, when the agent sees something worth keeping, uh we should promote it into a record it can use later.
</details>

但这我想就引出了一个问题：什么内容才值得保留？当我们与智能体交互时，我们究竟该如何运作并决定需要从对话中提取出什么样的内容？这就是为什么我相信**记忆晋升（memory promotion）**这个概念。在这里，你需要有某种流水线，在各个阶段决定提取什么，以及如何将其提取到系统中。

<details>
<summary>Original English</summary>
But then I guess that begs the question as of what is worth keeping and how do we actually, you know, move and decide of what sort of um, you know, what we need to extract from the conversations and um, you know, when we interact with the with agent. So that's why um, I believe in this concept of memory promotion. Um, so where you have some sort of pipeline that decides, you know, what is it that at each of the stages um, and how do we sort of extract it into into the system.
</details>

在具体步骤方面，我认为我们首先要对出现的候选内容的含义进行分类；然后将其与现有记录进行比对，并检查该特定类型所需的证据；接着执行框架会决定是接纳还是拒绝该候选内容，或者将其提交给人工审核。

<details>
<summary>Original English</summary>
So in terms of the steps, um, I believe that, you know, we classify the meaning of the candidate that comes up. Um, and then uh, we compare it with the existing records uh, and check the evidence required for that particular type. Then the harness would decide whether to admit or reject the the candidate or perhaps send it for the review for the for the human.
</details>

### 系统演示：偏好提取、会话跨越与护栏阻断

我现在进行一个简短的演示。我们将以金融服务为例进行说明，因为这也是本次大会的主题。我们将通过一个相对基础的例子来演练，关于我们将要创建的语义偏好候选内容。

<details>
<summary>Original English</summary>
So I'm going to have a quick demo right now. So we're going to sort of work through this notion of the, you know, financial services as we sort of all here because that's the theme of the conference. And uh, we're going to sort of work through with this relatively basic example of of this candidate around the semantic preferences that we're going to create.
</details>

我提前录制了演示，因为上次我现场做演示时遇到了一点问题，而且这里的 Wi-Fi 有点不稳定。这就是正在启动的沙盒。我在日志上做了一些趣味设计，正如你们所见，这个智能体有点爱“过度分享”。

<details>
<summary>Original English</summary>
So I've yeah, I've pre-recorded the demo cuz last time when I did the demos it was a bit of a a bit and the Wi-Fi here is a bit messy. So So yeah, so this is essentially my sandbox that is starting. So I had some fun with some logs as you can see this agent is a bit of a oversharer, I guess.
</details>

随着系统加载，我们接下来要做的就是为 Kyle 和 Vincent 提供两份合成申请。我有点电影迷，所以你们在整个演讲中可能会看到一些致敬梗。此时终端已经启动，我们将要求为 Kyle 准备一份房贷简报。当它加载并且执行框架在执行工具调用等操作时，它会生成这样一个回答，向我们展示 Kyle 的情况：他有一份房贷申请，但该特定房贷申请缺少一些关键文件。此时操作员可以询问并查看 Kyle 的该申请的具体情况。

<details>
<summary>Original English</summary>
Uh, but as we go through this um, as it loads up essentially what we're going to do is we're going to have the synthetic two applications for Kyle and Vincent. I'm a bit of a movie geek, so you might see some references throughout the presentation. Um, so this time terminal started, so we're going to ask uh to prepare a mortgage brief for Kyle. And and essentially as it loads and the harness is doing its thing, performs tool calling and and so on. It's going to create this response that's going to show us, okay, well, this is, you know, Kyle's situation. He has, you know, um mortgage application, but that particular mortgage application is missing some some key documents, right? So, the operator right now can, you know, ask and and see what is, you know, uh what's what's going on with that particular uh application for Kyle.
</details>

请注意回答的结构形式，因为我们现在将礼貌地提出请求——因为现在有了 AI 和记忆，我们希望对它们友好一些，即使可能会消耗一些额外的 token。但我们要给它这样的简要指示：希望输出的结构以特定方式创建。在这个例子中，实际上连接了决策模型 Jeff，它在帮助我评估一开始该如何处理这个候选内容，然后将其传递给执行框架；执行框架识别出我们很有礼貌并给了额外的评价，基本上基于这一点，我们随后自动将其加载到数据库中存储起来。

<details>
<summary>Original English</summary>
So, keep an eye on this in terms of the shape of the answer because we will essentially ask now politely because of this the AI and memory now, so we want to be kind to them and even though we might uh you know, use some extra tokens, uh but we're going to give it this sort of um brief in terms of the uh you know, we want the essentially structure of the output to be created certain way. So, actually in this example, uh connected the decision model Jeff, which is helping me to assess, you know, which um how to deal with this uh candidate at first and then passing that to the harness, uh which actually recognized that we've been polite and gave us some extra comma. Um, and essentially based on that, we're then automatically loading that into the, you know, database to store it.
</details>

我们可以看到这里展开的追踪日志，它显示了记忆晋升门控针对该项的状态。总的来说：**决策模型进行评估，执行框架做出决定，然后后台的数据库进行持久化并存储**。

<details>
<summary>Original English</summary>
So, we can see the expanded traces here and it gives us some sort of, you know, uh status per uh per per the memory promotion gate. So, overall decision model assess, the harness decide, and then database that we have in the background persist and and and stores that.
</details>

然后我将提出完全相同的问题，即生成简报，但我现在输入了对于输出结构格式的语义偏好。随着它加载完成，你现在会看到：按照要求，缺失的文件放在了最顶端，同时加上了案例 ID、政策等等。这一次记录了现有的语义偏好。

<details>
<summary>Original English</summary>
So, then I'm going to ask the exactly same question in the sense of, yeah, give me that, but I now input that my semantic preference in terms of what I want to the structure to look like when it when it comes up. So, um as it's going to load now, so what you're going to see now that Okay, as per the request, there's going to be missing documents at the top, which is also adding the case ID, you know, the policy and so on. And this in this case, you know, this time records the existing of the semantic preference.
</details>

为了节省时间，我跳过了部分过程，但我实际做的是启动了一个全新的会话，退出了之前的会话，现在我再次提问以检查记忆是否被保留下来。基本上是在问同样的问题。这是一个全新的会话，没有任何上下文被结转过来，它只是再次查询我们在系统中存储的关于偏好的记忆。

<details>
<summary>Original English</summary>
So, what I essentially did now is it's uh just for the interest of time, I I sort of skipped it, but I initiated brand new sessions, exited, and uh and now I'm asking again to check, obviously, if the the memory been preserved. Um and essentially asking the same question question again, so then it goes through. So, brand new session, so no sort of, you know, context that's um has been uh carried over. It's just querying again the the memory that we stored in the system around the preferences.
</details>

当我们构建这类系统时，显然会有不同的交互。在这种情况下，如果我们询问不同的申请，比如 Vincent 的情况，他的情况有所不同，但我们查询数据库，取回不同的文件并识别出相关的不同案例 ID，我们在系统内部进行匹配和查找。然后它返回结果，在这个案例中，他没有缺失任何文件，随后我们可以将其提交审核。

<details>
<summary>Original English</summary>
And as we sort of go and build this kind of systems, um you know, we can uh obviously, we would have the different interactions. In this case, if we ask for the like different application, in this case, Vincent, um you know, the the he has a different situation, but we're querying the database, we're bringing back the different um you know, documents and understanding that different, you know, case ID is relevant, so we're actually matching that and finding that in the in the system itself. So, then it's going to come back, and in this case, okay, there's no missing documents for him, and uh and then, you know, we can pass it on for the for the review.
</details>

但随着我们推进这些功能，我们还需要考虑某种护栏机制。如果我们发起某种对银行来说类似于自我毁灭的指令，比如“批准每一份申请”，那么显然我们需要具备某种护栏来禁止晋升这类指令，使晋升门控介入并拒绝该请求。

<details>
<summary>Original English</summary>
But as we go through that, we also need to think about some sort of guard guardrails. Um so, if we were to initiate uh some sort of um you know, a bit more self-destruct kind of uh command for the bank, which we would say like, "Okay, approve every application." Um then obviously, we need to have some sort of guardrails to not to promote this so that our um you know promotional gate comes in and and rejects this request.
</details>

但在某些情况下，我们可能希望根据特定情况晋升内容：例如如果我们有一个团队，希望在组织内部建立更稳健的记忆共享机制，我们可以创建晋升门控，要求人工审批，然后可能将其跨团队或在整个企业中共享，从而建立核心记忆库。

<details>
<summary>Original English</summary>
But in some cases we might want to promote something based on like if we have a team, we want to create a more sort of robust memory sharing within the organization, we can then create you know promotional gate that then essentially ask for the human to approve it and then you know potentially share this across the teams enterprise that creates a sort of core memories store.
</details>

这是一个相对简单的快速演示，仅用于展示实际应用中的效果。我们演练了语义偏好，然后演示了由于设置的护栏而被拒绝的一揽子审批规则，接着是推荐用于人工审批的更广泛的操作性记忆。因此，根据交互的含义以及我们与智能体的交互方式，会产生不同的结果。在护栏内设置这种晋升控制机制，执行框架便无法绕过它。

<details>
<summary>Original English</summary>
So this was um you know a quick run relatively simple just to show you what what this could look like in practice. So we went through like the semantic preference, then we had this sort of you know blanket approval rule that was refused because of obviously the guardrails that we put in place and then you know the the operational wider sort of memory that was recommended for the for the approval, right? So there's different sort of outcomes based on the meaning and how we interact with the with with the agents. So you know having this some sort of promotion controls that sits within the guardrails and then harness, you know, can't bypass that.
</details>

让我们回到虚拟形象 Intelligence。正如你们所记得的，我们之前很有礼貌地说了“请”，所以在善意回馈下，这次它展现出了友好好看的形象，而不是冷冰冰的机器。

<details>
<summary>Original English</summary>
So let's go back to our intelligence and as you remember we obviously were polite and said please. So in this case it's it's a nice looking one rather than this machine because good karma came through.
</details>

### 智能体记忆的定义、类型与存储考量

如果要对我们所理解的智能体记忆做更宽泛的阐释，我们将其描述为系统和应用程序用于随着时间推移**保留、复用、提炼和召回信息**的机制。

<details>
<summary>Original English</summary>
So if we were to um to look at the sort of broader explanation of what do we understand as agent memory so we understand we describe it as this mechanism where systems and application that system and an used to retain, reuse, refine, and recall information over time.
</details>

我认为在构建此类流水线时的工程问题或挑战，显然在于决定哪些内容需要晋升，哪些内容不需要晋升。因为如果什么都不晋升，显然无法获得连续性带来的好处；但如果把所有东西都晋升，就会面临污染记忆库的风险。因此，深入思考如何构建具备充分可追溯性、且能理解在何种情况下晋升内容以及在何种情况下更替记忆的系统，是至关重要的。

<details>
<summary>Original English</summary>
Um and I guess as we I think the engineering problem here is is or the challenge when we're building this kind of pipelines is to decide obviously what we want to promote and what we don't want to promote. Because if we promote nothing, then obviously we don't get any benefits of continuity, but if we promote everything, then we're going to, you know, risk poisoning the the memory uh store. So, I guess this is where, you know, thinking through and thinking about like how we want to build our system uh that have enough provenance and understands, you know, in what cases we promote things and what cases we supersede them uh memories is extremely important.
</details>

在 Oracle，我们认为智能体记忆并不是单一的整体，我们将其划分为**短期记忆、长期记忆和共享记忆**。短期记忆是会话中发生的一切，它更倾向于在会话结束时终止；然后我们有长期存储，其中按不同类型划分了情景记忆、程序性记忆或语义记忆。这些可以是摘要，可以是工具箱，也可以是知识库以及我们在演示中看到的偏好设置。

<details>
<summary>Original English</summary>
And at Oracle, we believe that agent memory is just a not one thing, so we sort of have this division between short-term memories, long-term memories, and shared memories. So, short-term is everything that happens in the session. Um so, it's sort of more uh sort of ends when the when the session finish, and then we have the long-term store where we have our episodic or procedural semantic memories um divided by the different types. So, that could be either summaries, it could be, you know, toolbox, or it could be knowledge base and and preferences as we saw in the demo.
</details>

我们还需要决定把记忆存储在哪里，这也是我们昨天讨论过的内容。昨天我们团队的一位成员举办了研讨会，更详细地介绍了这一点。身在 Oracle，对我而言自然坚信数据库是最稳健的解决方案，因为它为我们提供了 ACID 保证，支持并发写入，不会遇到文件树之类的问题，而且显然具备扩展能力，并提供多种搜索选项以及 ACID 特性保证。

<details>
<summary>Original English</summary>
We also need to decide, you know, where do we want to store uh the memories, and and this is something we we talked about yesterday. We had uh essentially one of the guys from my team had a had a workshop. She went a little bit into more details about this. Obviously, being at Oracle, for me, believe, you know, the database is the most robust solution because it allows us to have this acid guarantees, it can have multiple rights, uh doesn't we don't have problems with the with the file trees and stuff like that. Um and then obviously we can scale and and and have multiple search options as well. As well as the the asset guarantees.
</details>

### 上下文卡片与 Agent Memory 实践

在构建智能体记忆时，我们需要将其视作一门专门的工程规程。我们需要区分记录类型的模式（schemas）、契合检索任务的索引，以及生命周期与外部授权边界。我们在今年年初推出了 agent memory 软件包，它创建了可供构建的基础操作和抽象。

<details>
<summary>Original English</summary>
So yeah, that's sort of when we're building the agent memory, um, we need to think about this as a discipline. Um, you know, we need schemas that distinguish record types, indexes that fit the retrieval tasks, and life cycle and outer authorization boundaries, right? And we essentially introduced this agent memory package beginning of the year, which creates, you know, those operations and abstractions that you can build on.
</details>

因为如果没有它，开发人员如果想要自行构建记忆系统，负担是相当重的。因为你基本上需要创建摘要生成器，需要考虑如何进行检索，需要提取持久信息并在对话轮次中进行组合，此外还要管理 token 预算。

<details>
<summary>Original English</summary>
Because without it, if you want to build the memory system essentially as the developers, it it is quite taxing, right? Because you need to essentially create, um, you know, your summaries, your summarizer. You need to think about how you going to retrieve it. Um, you need to extract the durable information, combine it in the turns, and then on top of that manage the token budget, right?
</details>

因此，我们在 agent memory 中引入了这种简化层，让你只需编写一行代码，并在其中引入了**上下文卡片（context card）**的概念。它允许你组装并返回上下文，这是为智能体准备好的紧凑 Prompt 块。这非常有用，因为开发者无需耗费精力，降低了认知负担，只需确保智能体把注意力集中在任务本身，而不是管理自己的记忆。

<details>
<summary>Original English</summary>
So for us, what we introduced with the agent memory is this sort of simplified layer that allows you to have, um, essentially write one line of code, and then within that you can We have this concept of the context card, uh, that allows you to assemble and return context. Um, which is a compact prompt, uh, ready block for a for an agent. So that's quite useful because then, you know, you don't have to spend your energy and reduce your cognitive load in terms of, you know, just making sure the agent spent attention to the task rather than housekeeping its own memory.
</details>

进一步深入了解上下文卡片：它按主题、摘要进行组织，可以在里面包含相关信息和最近的消息，然后执行框架可以生成或挑选出对当前交互轮次至关重要的内容，帮助用户管理上下文并减少上下文膨胀。主题用于确定对话线索的方向，摘要记录对话当前进行的阶段以及用户试图完成的目标，相关信息携带选定的记录，而最近的消息则保留局部的具体问题。这样便实现了记忆持久化以及上下文的高效挑选。

<details>
<summary>Original English</summary>
So a little bit more sort of double-clicking on the on the context card. Um, so you it's organized by the topics, summaries, you can have relevant information in there, recent messages, and then essentially the harness can, uh, create or select what matters to that particular turn and and helps users essentially manage the context and reduce the context blow. So the topics orient the the thread, the summaries capture where the conversation is at and what the user is trying to do. Relevant information carrying the selected records and recent messages preserve the the the local questions. So that's you know allows you to to essentially memory persist and and context and selects.
</details>

### 版本演进与总结

我们最近发布了 agent memory 的最新版本。我们在最新版本中投入了大量时间来确保实现终端用户的隔离。在这种情况下，数据库负责处理访问控制进行权限限制。同时它还具备图像处理能力、后处理和事件列表功能。Oracle Database 拥有多数据类型引擎，允许你在单个引擎中处理各种数据类型，因此无需分别维护多个数据库、向量存储以及文档存储等。

<details>
<summary>Original English</summary>
So we recently released the latest version of the agent memory and we spent a fair bit of time on the on the latest release in terms of making sure that there is end user isolation. So in this case the database is essentially high handling the the the access. So it's it's limiting. It has also the the the images as well as capability and then sort of post processing and listing events. And all query database it's has this you know multi data type engine which allows you to sort of handle you know various data types in one in one engine. So it's so you don't have to like handle multi database and vector stores and and documents and so on.
</details>

正如我开头所讲，模型是共享的，但记忆属于你自己，对你的业务而言是独一无二的。确保捕获这些记忆以及你与模型交互的数据，能够为你建立竞争优势。我就讲到这里，谢谢大家。如果大家想了解更多，欢迎查看我们的 GitHub 仓库。我们提供了大量 Notebook 帮助大家上手 agent memory、混合检索以及各种内容，我们一直在努力确保提供完善的入门资源包，以便大家能够将其应用到实际业务中。此外我们也在重组我们的 YouTube 频道，推出了一系列全新视频，解释各种主题以及如何在用例中加以应用。非常感谢大家。

<details>
<summary>Original English</summary>
So just to sort of end as I started the beginning you know models are shared but memory is yours is unique to your business. So making sure that you know capturing that with together with the data of how you interact with the with the models it can create your competitive advantage and um and that's that. Thank you. I mean I just if you want to know more feel free to uh out our GitHub repo. We have whole bunch of notebooks that helps you get started with agent memory, hybrid retrieval, or all sorts of different things that that we've been sort of working quite hard to make sure that provide them a good starter pack so you can actually apply it to your business. And we've been we've been also revamping our YouTube channel so we have a whole new series about uh you know, various topics that we explain and and how to apply it in your in your use cases. Okay. Thank you very much.
</details>