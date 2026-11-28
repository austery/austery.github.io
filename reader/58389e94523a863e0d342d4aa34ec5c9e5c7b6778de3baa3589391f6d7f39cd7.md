---
author: AI Engineer
date: '2026-11-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pZWPq_ZAmM4
speaker: AI Engineer
tags:
  - ai-agent
  - software-architecture
  - developer-tools
  - sandbox
title: 释放智能的基石：Lovable 的长程 Agent 架构与沙箱优化
summary: Lovable 联合创始人兼 CTO Fabian Hedin 分享了团队从 2023 年多 Agent 架构挫败到如今运行长程系统的历程。他重点解析了支持 Agent 长时间运行的三大支柱：基于类 Git 追加日志与无状态进程分离的运行时、秒级启动与 CoW 内存克隆的沙箱计算机，以及涵盖构建检查、无头浏览器与业务指标的双层验证反馈回路。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Fabian Hedin
companies_orgs:
  - Lovable
products_models:
  - GPT Engineer
  - GPT-4
media_books: []
status: evergreen
---
### 探索与起步：从过早的多 Agent 陷阱回到现实

>> 大家好，很高兴来到这里。我是 Fabian，Lovable 的联合创始人兼 CTO。过去几年左右，我们一直在打造一个平台，让任何人都能创建软件，并对其进行运维与部署。

<details>
<summary>Original English</summary>
[music]

>> Welcome everyone. Glad to be here. I'm Fabian, co-founder and CTO of Lovable. And we spent the last few years or so building a platform to let anyone create software and then operate that and deploy that software.
</details>

>> 今天的主题是“释放智能需要什么”。对我们来说，这其实要追溯到我们三年前刚起步的时候。不得不说，我和 Agent 的关系经历了一段波折。我来告诉大家为什么。

<details>
<summary>Original English</summary>
And the the topic of today is what it takes to set intelligence free. And really for us this takes us back to when we when we started three years ago. And I have to say I have a bit of a complicated relationship with agents. And I'll tell you why.
</details>

>> 我们公司曾经濒临失败，因为在 2023 年时我们心想：Agent 代表着未来，所以我们现在就为它们去构建吧。现在看来，它们是未来这一点确实被证明是对的，但就 2023 年那个“当下”而言，我们绝对错了。那是处于 GPT-4 的时期，当时模型的智能水平根本无法支撑这种复杂的 Agent 系统。但现在不同了，对吧？现在的智能水平确实已经达到了你可以真正围绕它们构建更复杂系统的阶段。

<details>
<summary>Original English</summary>
We almost failed as a company because we thought back in 2023 that hey, we these agents are the future, so let's build for them now. I think they we kind of turned out to be true that they were the future, but we were definitely wrong on the now piece in 2023. So this was back in kind of GPT-4 days. And at the at that time the intelligence was simply not there to have more of these kind of complex agentic systems. But now it is, right? Now now the intelligence is actually at a place where where you can really build out more complicated systems around them.
</details>

>> 所以我先简单分享一下我们与智能模型或大语言模型（LLM）合作的背景故事。2023 年，我们打造了产品的第一个版本，当时叫做 GPT Engineer。其实它的 UI 和今天非常相似，也是左边聊天、右边预览。但当时的 AI 非常简单：每个用户消息对应一个 Prompt 和一次 LLM 调用。非常朴素，运行良好，你可以用它构建单页应用或更简单的软件。

<details>
<summary>Original English</summary>
And so I'll give you kind of a quick background story here of of our journey in in working with intelligence or or these LLMs. And so back in 2023 we built the first version of our product. We called it GPT Engineer back then. And really the UI was very similar to what it is today where you kind of have a chat and in this preview. But the AI at that point was quite simple. We just had a prompt and a one LLM call per user message. Very simple. It worked fine. But you could kind of build one page apps and and simpler applications with this.
</details>

>> 后来我们想：模型的智能会持续演进，我们必须做好准备以迎接它的发展。于是我们决定去构建一套 Agent 框架。我们动手搭建了一个非常精巧、甚至可以说是优美的 Agent 协作框架。我们有一个主 Agent 负责与用户交流，然后它会衍生出其他 Agent，比如这个例子里的实现 Agent。每个 Agent 都有自己的专长：一个专门负责应用的初版生成，接着还有前端 Agent、后端 Agent。它们之间互相沟通，来回传递消息。

<details>
<summary>Original English</summary>
And then we thought, okay, this intelligence is going to keep on evolving, so we have to be ready for for it as it evolves. And so we thought, let's go out and build this agentic framework. And so we we went and we built this very sophisticated, dare I say, beautiful framework for for agents to work. And we had kind of this one main agent that would talk to the user, and that agent would spawn other agents, like an implementation agent here in the example. And each agent could have a speciality. This agent would kind of specialize in the first generation of an app, and then you would have like a front-end agent and a back-end agent. And they would all talk to each other, send messages back and forth.
</details>

>> 当时我们觉得这太精美了，而且当时还有论文在讨论这种方式效果能有多好。可结果是它根本行不通，反倒把产品做得更糟了。在这一点上我们毫无疑问彻底失败了［清嗓子］［笑声］。

<details>
<summary>Original English</summary>
And we thought, oh, this is beautiful, and there was papers around this and how well this could work. And in the end it it didn't work at all. We just made the product worse. We we definitely failed [clears throat] [laughter] on this one.
</details>

>> 幸运的是，在资金耗尽之前，我们意识到：“还是回归更简单的系统吧。”所以在 2024 年末，我们回退到了一个简单得多的系统。虽然听起来有点遗憾，但在那个系统里，我们只让一些较小的模型做知识检索，然后由一个主模型在同一条消息里回复用户并编写代码。这种方案表现极佳：在 UI 上响应迅速、运行可靠，用户也能紧密地与模型持续迭代。

<details>
<summary>Original English</summary>
But luckily, before we ran out of money, we figured out like, hey, let's go back to a simpler system again. So in late 24 we went back to a much simpler system where it was a bit of a shame where we had like some some smaller LLMs doing some knowledge retrieval and then really just one main LLM kind of writing to the user and and writing the code in the same message. And this worked great. It was very responsive for for users in the UI, and it was reliable, and users were kind of in it and in iterating with with the model.
</details>

### 时机成熟：Lovable 的平台定位与业务成果导向

>> 先把那个窗口关掉。但现在，时机又成熟了。我们回来了，彻底回来了。这一次，Agent 真的起效了。在我们接下来要讲的这些系统上，我们正以每分钟超过十亿 Token 的吞吐量在生产环境中运行它们。

<details>
<summary>Original English</summary>
And so close that down. But now it's time again. We're back. We're so back. Agents this time, they work. And we're running them in production over a billion tokens per minute on on on these systems that I'm going to talk about.
</details>

>> 首先来看看 Lovable 到底是什么。如果把 UI 简化一下——这在 2023 年和今天是一样的——左边是聊天框，用户在这里输入并描述他们的构建意图或需求；右边是预览区，展示你所构建内容的输出或成果。在 2023 年，你只能用它做一些简单的事情。但现在我们切实体会到，在这个抽象层上进行工作，你已经能够构建出非常复杂的系统。我认为甚至可以看到很多面向开发者的工具也正在转向这种界面：你不需要每天紧盯代码本身，而是被抽象到了关注架构层面，或者直接查看工作成果。

<details>
<summary>Original English</summary>
But first, just looking at, okay, what is actually lovable? So uh if you simplify the UI, and this was same back in 2023 as it is today, uh to the left we have a chat where humans come in and they kind of describe their their intents to to build or whatever they want to do, and to the right you have a preview, uh which is the output or or the outcomes of of what you're building. Um and this back in 2023 you could do simpler things with, right? But now we've really seen working at this layer of abstraction you're able to build very complex things, right? And I think we've even seen uh a lot of tooling meant for for developers for example moving to this type of interface where you're not really looking at the code every day and so on and you're getting kind of abstracted and working on on be architecture or looking at some kind of output of of what you're doing.
</details>

>> 这是我们一直以来的信念，也是 Lovable 背后的核心理念：你不必再像以前那样去关心代码了。现在整个行业似乎正处在某种过渡阶段，有些人会说你完全不需要关心代码，也有人持不同看法。我从小写代码长大，自然对代码有些感情，但最终真正重要的其实并不是代码。抱歉，我还以为我们把最后那部分删掉了，但重要的确实是**成果**，对吧？

<details>
<summary>Original English</summary>
And um this is something that we've always believed in and it's been kind of a core thesis behind Lovable that you won't have to care about the code in in the same way uh that you had had to do before. And I think today we're kind of in this almost a bit in between I think in the industry where you know some people might say oh you don't have to care about code at all and some people might have different opinions um um I of course like growing up coding and these things you get a bit attached, uh but in the end what matters is is actually not the code. Um sorry I thought we removed that last part but what what matters is is the outcomes, right? Um
</details>

>> 那么，成果究竟指什么？对我们的用户而言，成果就是创建一门生意、实现变现，以及以某种形式为他人创造价值。在切入本次演讲的技术细节之前，我先简要概述一下我们为实现这一目标所构建的平台能力。

<details>
<summary>Original English</summary>
and so um the outcomes what is that? Well for for our users the outcomes is um creating a business and monetizing and creating value for for others in in in some type of way. And I'll kind of quickly go over um what we build as a platform to to enable this before I go in kind of on the uh on the technical side of this talk.
</details>

>> 纵观 Lovable，首先可以说的是我们拥有这个 Agent。和其他 Agent 一样，它能执行相当任意的任务，而且非常专精于软件开发。它能够访问浏览器来验证自己构建的内容，它与 GitHub 相连，编写你可以任意处置的代码。这就是基础的编码 Agent。

<details>
<summary>Original English</summary>
So if you if you look at Lovable the first thing that that you can say about the platform is that we have this agent and like any other agent it can do quite arbitrary things and it's quite specialized at at building software and it has access to a browser so it can verify what it's building and it connects to to GitHub and you know it writes code that and you can do whatever you want with that code. So so that's kind of your basic coding coding agent.
</details>

>> 平台的其他部分则是云服务和商业能力。云端部分的目标是无缝向该 Agent 提供各种托管原语：我们搭建了数据库、身份验证、对象存储、各种后端计算，以及安全扫描工具、备份与日志系统。所有这一切都可以由 Agent 直接检查。这让开发变得顺畅无阻，你不需要跳转到各个不同的服务去拼凑系统，我们直接为你备齐了这些底层原语。

<details>
<summary>Original English</summary>
And the the other pieces of the platform is is kind of cloud and and business piece of the platform. And so the cloud part of the platform is is about just giving kind of these hosting primitives just seamlessly to to this agent. And so we we built out databases of authentication, storage, all the types of backend compute and security scanners and like backups and logs for all of these things and all of it can be inspected by by the agent. And this just makes it seamless to to build things. you don't have to kind of go to different services to set this together. We just kind of provide you these primitives.
</details>

>> 这些依然是围绕软件构建与托管展开的。而最后一部分是商业能力。正如前面所说，在我们看来，用户在 Lovable 上的产出绝非仅仅是代码，而是一款产品或一门生意。如果你想在商业上取得成功，需要做的事情远不止写代码。因此，我们协助用户完成接收付款、发送邮件、优化 SEO、在 Google 和 Meta 上投放广告，并通过数据分析了解产品正在发生的情况，比如查看转化率并据此进行优化。Agent 在所有这些环节中都参与其中。这就是我们的能力版图，而这一切的核心，正是一个所有能力都为其量身定制的 Agent。

<details>
<summary>Original English</summary>
So that's still around building software and hosting this, right? But then the last piece is around these business capabilities where again the output of what our users are doing on Lovable, we don't see that output as code. The output is is a product or or a business. And if you want to succeed as a business, you need to do more things than just write code, right? And so we we we we help our users with receiving payments, sending emails, optimizing SEO, doing ads on on Google and Meta, and kind of analyzing what is happening with the product through through analytics and you can look at kind of conversions and and optimize these sort of things. And the agent is in the loop in all of this, right? So that's kind of our capability offering, you could say. And again, the core part of this is an agent that all of these capabilities are built for.
</details>

### 迈向长程任务：三大架构支柱

>> 在 Lovable 历史上的某个阶段，我们曾将 Agent 的单次工作时长限制在 30 分钟以内，因为当时我们认为它们不足以稳定运行更久。但现在我们已经取消了这项限制，对 Agent 的工作时长不再设限，你可以想象让 Agent 持续工作 10 个小时以上。

<details>
<summary>Original English</summary>
And at some point in Lovable's history, we used to limit our agents to work for only 30 minutes because we thought they weren't reliable to to work for a longer amount of time. But now we've changed this to really be without any any sort of bound in terms of the length an agent can work. And so you can imagine agents working for for 10 hours plus.
</details>

>> 接下来我将介绍我们在架构层面所做的改进来实现这一目标。第一部分关于 **Agent 运行时本身**，以及我们如何让它能够支持更长时间的运行；第二部分是**计算机沙箱**，也就是每个 Agent 实际开展工作、运行开发服务器并实际验证其行为的计算环境；最后一部分则是**验证本身**。如果想让一个 Agent 长时间运转，必须确保建立起反馈回路，避免它偏离预定方向。

<details>
<summary>Original English</summary>
Um, and so I'll I'll go into some of the things that we've done in our architecture to to enable this. And so the first piece is really around the agent runtime itself and how how we enable that to to run for a longer amount of time. And the second piece is the computer where each of these agents are actually doing their work, running a dev server, and actually verifying what it's doing. And so so the last piece then is the verification itself where if you want an agent to to work for a long amount of time, you need to make sure that you have these feedback loops in place so that it's not kind of going off in in in the wrong direction.
</details>

### 支柱一：基于类 Git 日志与无状态进程的 Agent 运行时

>> 先从 Agent 运行时本身看起。与 Agent 交互的来源主要有三种：
>> - 你自己（人类）发送的 Prompt；
>> - 其他 Agent；
>> - 定时唤醒的系统任务。
>>
>> 我们的架构设计是：为每个 Agent 配置独立的收件箱（inbox），任何来源都可以向其投递消息，例如询问“状态如何”。你可以设想这是一个常驻运行的 Agent。在执行了三次操作（一次请求、一次工具调用、拿到部分结果）之后，Agent 此时就可以接收外部消息了。既然任何人都可以向收件箱投递消息，Agent 便能主动将该消息复制进它自己的“轨迹”（trajectory）中，也就是所谓的任务历史记录。如果你使用过 Agent，对这类交互机制应该不会陌生。

<details>
<summary>Original English</summary>
Um, and so if we start by looking at the agent runtime itself, you can imagine that you have really three different sources that can interact with an agent. So it can be yourself kind of prompting this or a human. It could be other agents and it could also be just a system on on a schedule waking up. And the way we chose to architect this is that for for each agent we have a separate inbox where any of these sources would kind of send in messages. And so you might have a message here like what's the status. And you can imagine you have this agent and this agent is kind of an always on agent that that might be working, right? And so you can imagine it has done like three actions here, a request, a tool call, and it got some some result. And then at this point the agent is ready to actually receive messages. So since anyone can drop a message into this inbox, the agent then can copy that itself into its own what we call a trajectory. Basically it's a task history. And this is the type of interaction that I think you're familiar with if if you're using agents overall.
</details>

>> 这是该 Agent 运行时背后的首个设计原则。接下来我再讲几个核心点。Agent 展开工作所在的轨迹，记录了迄今发生的一切历史，它实际上构成了 Agent 所有记忆的基础。我们在设计这个轨迹时，很大程度上借鉴了 Git 的思路。那么轨迹到底是什么？它是一份**仅追加写入的日志**（append-only log），其中的每个事件都指向其父节点（即上一个事件）。

<details>
<summary>Original English</summary>
So that's kind of the the first design principle behind this agent runtime. I'll go through a few more here. And so um the the trajectory in which the the agent is working in, which is kind of the history of what has happened so far, um and really the basis for any sort of of memory for for for the agent, right? Um and we designed this trajectory with really Git as inspiration. And so the trajectory, what is it? It's an append-only log where each event points towards a parent, the previous event.
</details>

>> 得益于这种设计，你能获得类似 Git 的分支（fork）能力：两个事件可以指向同一个父节点，从而形成一个分支。正因如此，你可以在历史记录中的任意时间点启动并行 Agent，而无需复制所有共享历史。在语义层面上，合并两条轨迹的含义目前还不够明晰，因此与 Git 不同，我们无法对 Agent 轨迹执行 merge，但我们可以将其 fork 出来，让这些衍生出的 Agent 相互通信。

<details>
<summary>Original English</summary>
Um and because of this, you get a nice capability just like in Git where you can fork things, right? So you can have two events pointing to the same parent, which essentially creates a fork. Um and because of that, you can kind of spin up parallel agents at at any point of time in the history without having to duplicate all of the kind of the shared history. Um and semantically, it's a bit unclear what would happen if you merge this. So unlike Git, we cannot merge agent directories, but we can kind of spawn them out, right? And these agents can can talk to each other.
</details>

>> 我们确保实现的另一项设计是：Agent 轨迹包含了完整的历史和 Agent 身上发生的所有细节，包括每次工具调用、平台上的各种操作、工具调用的成败，以及大量可能并不完全适合直接放进 Prompt 的内容。我们维护这样一份仅追加的完整日志，随后再基于它构建出真正喂给 LLM 的 Prompt。你可能会问，为什么要这么做？一个原因是：面对漫长的任务历史，在构建 Prompt 时你可能需要进行某种上下文压缩，对早期步骤做摘要。然而摘要策略因模型而异：使用不同上下文长度的模型时，何时摘要、何时保留全文的考量也会截然不同。通过将 Prompt 生成与实际任务历史解耦，我们能够针对任何类型的模型或任务灵活渲染出最适宜、最优化的 Prompt。

<details>
<summary>Original English</summary>
Um the other thing that we made sure to design for is that this agent trajectory, it includes kind of the full history and everything that happens with the agent. And so every tool call, a bunch of other things happening on the platform, if a tool call like failed or succeeded, um a bunch of things that might not be fully relevant for a prompt. But then what we've done is make sure that we have this append-only log. And and from that, we can actually build a prompt that we would feed into into the actual LLM. And you might ask, why why why would you want to do this? Well, one one reason is that when you build a prompt, you if you have a long history, you probably want to do some sort of compaction and you want to summarize part of that history in in the earlier steps, for example. But this summarization would differ. For example, if you use different models with different context lengths, you would probably think differently about when you should summarize and not. And so by separating the the prompt from the actual task history, we're able to render prompts for for any type of model or or any type of task that that we can kind of find the best and optimal prompt for.
</details>

>> 为了展示这个事件历史的动态效果，我们提供了这样一个调试工具。屏幕上录制的是我在 UI 中拖动滑块的过程：右侧的界面会随着我的拖动实时更新。这里记录了 156 个事件，每一个都对应事件历史中的一个节点。你可以看到 UI 能够渲染出历史中的任意时间点。这表明，正是由于这份记录了一切细节的历史，我们在任何时刻都对 UI 以及平台上发生的其他事情拥有完全的控制力。

<details>
<summary>Original English</summary>
So to show this event history in in progress, we have this debug tool here. So here it's just recording of me dragging this slider in our UI and you can see on the right that the UI is kind of updating as I'm as I'm dragging this along and you have 156 events here and one each of those is an event in this event history. And you can see how how the UI can render kind of any point in history and this is just showcasing that at any point in time we have full control of of say the UI or or anything else happening on the this platform thanks to this history kind of detailing everything that has happened.
</details>

>> 关于运行时我想介绍的最后一点是：运行这些 Agent 的进程与实际的任务历史是完全分离的。负责执行的进程几乎完全无状态，在每次调用、每次工具调用、每个回合（turn）之间，其状态都会直接持久化到任务历史中。因此，后台进程可以随时创建与销毁。为什么我们如此在意这一点？在 Lovable，我们每天向这套系统部署 700 次，大约每两分钟部署一次。你可以想象，当一个 Agent 要连续工作 10 个小时时，你显然不想在它为客户服务时打断它；但与此同时，我们又必须确保 Agent 能够运行在最新部署的版本上——这可能是一个新功能，但也可能是一个 Linux 内核的安全漏洞，需要立即热修升级。

<details>
<summary>Original English</summary>
Then the last piece I'll go over here on the on the on the runtime itself is that the process that is running these agents, they're separate from from the actual task history. And so the process is almost entirely stateless in that between each each call, each tool call, each turn, it will actually just persist into the task history. And so you can have a process come and go. And and then the question is why why do we care about this? Well, at Labbable this system we deploy to it 700 times per day. So that's about once every two minutes. And you can imagine if you have a agent working for for 10 hours, you want to not disrupt that agent when it's working, right? This this agent is doing something for for a customer. But at the same time we want to make sure that this agent is running on the latest deploy. And it might be a new feature or something like that, but it might also be like a security vulnerability in in the Linux kernel. And it's like okay, we need to update this ASAP.
</details>

>> 正是凭借历史记录与运行进程的解耦，我们能够保证一个 Agent 专注执行单项任务的同时，由不同的进程无缝接管并提供底层的计算支撑。哪怕任务持续运行 10 个小时甚至更久，它都能一边保持工作，一边无缝经历多次版本发布。

<details>
<summary>Original English</summary>
And and so to do that thanks to this separation between the actual history and and the processes, we can actually make sure that we have one one agent that is working on one task, but we can have different processes taking up and actually doing the compute behind that work. So so this task can keep on working while we have different deploys working on it, be it for 10 hours or or even longer, right?
</details>

### 支柱二：沙箱计算机、秒级快照与 Rust 重写

>> 介绍完 Agent 运行时，平台的第二个支柱就是计算机沙箱，即实际执行工作的地方。在为 Agent 寻找和提供这类沙箱环境的过程中，我们经历了大量的方案迭代与供应商选型。最终，我们落地了一套投入巨大精力自研的系统：**计算机快照**（checkpointing a computer）。

<details>
<summary>Original English</summary>
So that's the agent runtime. The second piece of of this platform, right, is the is the computer. So this is where the work is actually happening. And we've been through a lot of iterations and a lot of vendors kind of working with providing these sandboxes for for the computer for for the agent to work in. And we've landed in in the system that we've worked really hard now to develop, which is checkpointing a computer.
</details>

>> 设想你来到这里开启一个新项目。我们有一个被称为“黄金快照”（golden checkpoint）的通用镜像，其中包含了操作系统、系统级服务、已预装的常用工具，以及一个准备就绪的开发服务器。这份快照涵盖了磁盘数据、内存以及所有正在运行的进程。当创建新项目时，你将免费获得这一切，所有状态在约 230 毫秒内即可完成拷贝并就绪。

<details>
<summary>Original English</summary>
And so you can imagine you come to you start a new project. We have this common what we call a golden checkpoint, which contains the OS and the system services. It has common tools installed and a dev server that is ready to start. And this checkpoint it includes everything on disk, memory, and also running processes. And and so when you start a new project, you get all of that for free. And all of that is copied over in about 230 milliseconds.
</details>

>> 项目启动后，你可能会添加特定代码与依赖项，这些也会随着执行被实时快照保存。每当 Agent 运行并结束一个回合，我们都会对该计算机保存一次快照。这样一来，无论你何时需要，我们都能在亚秒级时间内重新拉起这台机器。这意味着如果用户离开 10 分钟左右，我们可以停机以节省资源；当你返回时，又能以极快速度启动，快到你甚至察觉不到停顿，处于传输中的网络请求在这一架构下也不会发生丢包。

<details>
<summary>Original English</summary>
And so once you start a project, you you might have some specific code and and some dependencies within that project. And that is also checkpointed as you go. And and so each time the the agent is running and it finishes a turn, we will actually save a checkpoint of that computer. And and from that we're able to again like very quickly subsecond spin that computer up whenever you need it. That means we can save on on resources by kind of spinning this down if you leave for say 10 minutes or or so and come back, we can just spin it up extremely quickly so you don't even notice this. And even kind of requests in transit will will not even be dropped in in this setup.
</details>

>> 得益于快照机制，我们不仅能像运行时轨迹那样做分支，还可以直接**对计算机环境进行分支克隆**（fork）。我们在 Lovable 中上线了一项名为“Drafts”（草稿）的功能，支持你在不同环境中开展工作，其底层就需要对当前工作的计算机进行克隆。这里展示的是同时启动两个环境的例子，而在实际场景中完全可以并发运行数百个。

<details>
<summary>Original English</summary>
The other thing we can do thanks to this checkpointing is that just like the trajectory itself in the aided runtime, we can also fork the computer. And when we do this, we have for example we have a feature in in level that is called drafts where you kind of work in different environments of what you're doing and and to support that we need to fork the computer that you're working in. And here we have kind of the example of doing two at the same time and you can imagine doing hundreds of these, right?
</details>

>> 为了让这种操作切实可行，我们实施了多项优化：
>> - **内存写时复制（Copy-on-Write, CoW）：** 对计算机进行环境克隆时，基础 RAM 消耗几乎为零。只有当某个进程开始向内存页写入数据时，才会按需拷贝该内存页并分配新内存。
>> - **内存流式预加载：** 每个沙箱通常需要数百兆内存。如果将其存放在冷对象存储中，先下载到磁盘再读入虚拟机的内存，可能需要数秒时间。通过内存流式传输，机器无需等待全部内存就绪即可先行开机：优先加载操作系统所需的内存页，其余进程在内存数据到达后立即开始工作。这进一步削减了冷启动时间。

<details>
<summary>Original English</summary>
And so we've we've had to do some optimizations to make this feasible to to actually run. So one of these optimizations is copy on write on the RAM itself. And so creating one of these forks of our computer is is basically free in terms of of the RAM that it's using. But as soon as you start writing in in a process to to RAM, we will kind of copy that page over and only then will you start having to allocate new memory. And and there's another optimization here also which is that each of these sandboxes they require a few hundreds of megabytes of memory. But and that would take a few seconds to stream in if you have it in like cold object storage and then it has to go to disk and then then into memory of this this VM. But thanks to being able to stream the memory, we can actually boot up the the machine before all of the memory is is actually ready on it. So the the memory the OS uses comes first and then like some processes and so on will will start to work as soon as the memory gets here. And this also shapes off some some extra startup time.
</details>

>> 随后我们思考：如何才能让它更高效、对用户更快速？很多开发者都熟悉 Vite，JavaScript 生态中大多数元框架都在使用这个优秀的开发服务器。我们将其 Fork 出来，并用 **Rust** 进行了重写。这一改动使冷启动速度提升了两倍，预览界面的加载耗时从 40 秒缩减到了 3 秒。性能飞跃的核心原因在于原始 Vite 依赖 Node.js，而我们剥离了对 Node.js 的依赖，将其替换为纯粹的 Rust 二进制程序，从而使虚拟机的内存占用减少了 6.5 倍。

<details>
<summary>Original English</summary>
And then we started asking ourselves, how can we make this even more efficient and even more faster for our users? And so you might be familiar with V8. This is great dev server that most of the meta frameworks out there in the JavaScript ecosystem is using. And so we we took that and we forked it and we rewrote it in in Rust. And that made our code starts two times faster, and we went from getting this preview from 40 seconds to three seconds. And the main kind of thing that we made faster is that V2 uses Node.js, and we're able to like drop that dependency of V itself and just have this Rust binary. So that made the memory footprint be 6.5 times less in these machines.
</details>

>> 通过完全掌控计算机中运行的应用程序，我们也得以精确控制其内存写入行为。一旦掌控了内存写入，就能进一步深化写时复制方案在多沙箱克隆时的优化效果。最终，我们能够极其高效地并发运行海量 Agent，让不同 Agent 并行探索各类解决方案，从而修复 Bug 或优化应用性能。整个研发过程非常有趣［笑声］。

<details>
<summary>Original English</summary>
And by taking control of the applications that we're running in these computers, we're also able to control kind of how we write to memory. And so when we control how we write to memory, we're even more optimizing, if you remember back to the kind of the copy-on-write solution when we're drafting different different computers. And so we're able to run this extremely efficiently so that we can run lots and lots of agents in in parallel and kind of have agents explore different solutions to solving a bug or improving the performance of of your applications and and so on. And so this has been fun. [laughter]
</details>

### 支柱三：双层验证回路与未来展望

>> 最后一个模块是验证。显而易见，沙箱计算机与开发服务器是验证 Agent 行为的关键基础。谈到验证，核心在于反馈回路：Agent 采取了某项行动，它需要明确知晓这个行动是好是坏。我们可以将其划分为**内层循环**（inner loop）与**外层循环**（outer loop）。
>> - **内层循环（单个回合内）：** 包含一系列即时检查，例如构建是否成功、代码是否存在语法错误或类型报错，以及预览运行时是否存在错误。计算机内还集成了无头浏览器，Agent 可以自主进入并探索正在构建的 Web 应用等。
>> - **外层循环（回合之间）：** 即当 Agent 将控制权交还给用户之间的阶段。在这里可以汇聚来自线上生产环境和真实用户的反馈：访客的行为模式、用户在网上的直接反馈、自动执行的 A/B 测试（如修改文案以观察转化率变化）。此外，还可以直接接入商业指标——正如前面介绍的业务能力，通过掌控这些链路，我们能够捕获支付交易和转化数据。这意味着 Agent 不仅能帮你优化代码，还能协助优化产品的商业策略。

<details>
<summary>Original English</summary>
But the last piece now is is about verification. And of course this kind of computer and this dev service a big piece of being able to verify what an agent is doing. And if you look at verification, you can think of these feedback loops, right? That the agent needs to get information. It took an action. Was this a good action or was it a bad action? And you can think of it as this inner loop and this outer loop. So this inner loop is during the turn of the agent. And you have kind of obvious things such as like the is the build working? Do we have lint errors or type errors in the code that we're running? And then you can check for runtime errors in in the preview that you're running. You can also have within this computer a headless browser where the agent can go in and kind of explore the the web app it's it's building or whatever it's building, right? And and a bunch of other things that we're using to help verify within the turn of an agent. But then you also have this outer loop which is kind of between each turn. And a turn you can think of like when the agent is yielding to you as a user. And between each turn you might get some info on on the product itself from production from your users, right? And so you can look at how your visitors are behavior behaving, what users are telling you online. You can do automatic A B tests and actually see change some copy and see if it's improving conversion and so on. And then you can also take these business metrics and remember this goes back to kind of the capabilities I showed you. By having control over these things we can make sure that we can optimize how the agent is is getting this outer feedback loop so we can make sure that if you're running payments we can actually track those transactions and conversions and make sure that the agent can actually help you optimize not only the the code, right? But the business strategy around around your product.
</details>

>> 这就是我们一直在构建的三大核心要素，我们将继续围绕将 LLM 编排为 Agent 构建更多架构与功能能力。如今，这套系统每分钟处理数十亿 Token；每个 Agent 都可以随时调起专属的计算机沙箱，多个 Agent 也可以共享一台沙箱。我们回到了这种优美的多 Agent 协作体系中，Agent 相互对话与协同，并且得益于底层的工程优化，这一次它们真正起效了，且具备了规模化运行的能力。

<details>
<summary>Original English</summary>
And so those are really the the three things that that we've been working for and we'll continue to kind of build out these these capabilities and these architecture around really orchestrating these LLMs into into agents. And so this agentic system that we're building it's running billions of tokens per minute and these computers, right? We can spawn up with each agent and we can have multiple agents use one computer and now we're kind of back to this quite beautiful setup where you have agents talking to agents and they're orchestrating and and this time it's it's actually working and it's working at scale thanks to some of these optimizations.
</details>

>> 如果大家想体验，可以访问 lab.dev，你会看到预览环境飞速启动。你将体验到一个极其简洁优美的界面，而完全无需为底层的这些繁杂细节操心。非常感谢大家，很荣幸来到这里，希望大家有所收获。非常感谢！

<details>
<summary>Original English</summary>
And so if you're curious to try this out you can head to lab.dev and you'll you'll see our preview spinning up and so on but you'll get a very simple and a nice interface and you won't have to care about all of this stuff. Thank you so much. It's been pleasure and yeah hope you hope you learned something. Thanks so much.
</details>