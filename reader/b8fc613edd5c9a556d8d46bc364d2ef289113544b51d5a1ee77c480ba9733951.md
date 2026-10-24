---
author: AI Engineer
date: '2026-05-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=svCnShDvgQg
speaker: AI Engineer
tags:
  - agent-durability
  - stateful-compute
  - snapshot-restore
  - llm-agents
  - backend-architecture
title: 探析Agents的持久化之路：从重放模型到快照恢复
summary: 本文探讨了构建持久化Agents的挑战与解决方案。从Web后端历史演进到LLM Agents的涌现，作者对比了'重放模型'与'快照恢复'两种持久化Agent的途径。重点阐述了上下文持久化（日志）与执行持久化（快照）的结合，以及Firecracker微虚拟机在此中的作用，预示着Backend基础设施将向有状态计算演进。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Trigger.dev
  - IBM
products_models:
  - CRIU
  - Firecracker
  - FCRun
media_books: []
status: evergreen
---
### Agent的生产化挑战

当我们将Agent部署到生产环境时，它们需要具备处理长期、有意义工作的能力，这种工作需要能够跨越多个回合（turns）和代码版本保持持久性，并具备从错误中恢复的能力。演讲者Eric Allam，Trigger.dev的创始人之一，分享了他们在过去几年中如何致力于简化这类Agent的生产化部署。他通过一个关于Agent与人类角色的趣 meme，引出了Agent对后端基础设施提出的根本性转变，以及实现Agent持久化的构想。

<details>
<summary>Original English</summary>

When we want to sort of deploy these two production backends and, you know, run them on our servers? So, what do we want them to do, right? When they run on our servers, we want them to do, you know, long-running meaningful work. Uh should be durable across turns and and versions of our code, and it should be able to, you know, recover from errors. So, I'm Eric, I'm one of the founders of trigger.dev, and we've been sort of trying to make it easy to deploy these types of agents to production for the last few years. Um what I like about this uh little meme here is, which one is the agent and which one is the human?

</details>

### Web后端演进史：从CGI到共享无状态架构

为了理解如何实现Agent的持久化，首先需要回顾Web后端基础设施的演进历程。从1993年的CGI（通用网关接口）开始，其模型极其简单：接收HTTP请求，服务器fork一个新进程，处理数据，将响应写入标准输出，然后进程销毁，这种方式是完全无状态的。紧随其后，PHP和LAMP（Linux, Apache, MySQL, PHP）栈的出现，虽然复用了PHP进程，但核心原则依然是“请求+数据库=响应”，即**共享无状态架构（Shared-Nothing Architecture）**。这种架构将状态存储在数据库中，计算层保持无状态，并在过去30年内成为Web后端的主导范式，Ruby on Rails、Node.js、Serverless等后续技术都遵循此模式。

<details>
<summary>Original English</summary>

So, the very first dynamic web backend was CGI back in 1993. Anyone here ever done CGI stuff? Cool. Nice. Uh so, the model was really simple. Uh HTTP HTTP request comes in, the server forks a whole new process. Request data goes in, the process does some stuff, and then it writes the response to standard out, and then the process goes away. Go So, it's completely stateless. Um shortly after that, uh PHP came out, which sort of turned into the LAMP stack. Um and oops. Um so, sort of uh the LAMP stack sort of reused the PHP process, right? Um but, it kept sort of the principle that like all you needed to do to create a response was the request, some state from the database, um and then it would do the request. So, the second request would come in, and it would do all the same work again, and it would produce the response. So, this is sort of request plus DB equals the responses sort of became known as the shared nothing architecture, right? So, looking at another way, shared nothing sort of means that the compute layer is stateless, right? There's nothing There's no meaningful state like in the compute. The state is in the in the database, right? So, this became the dominant backend infrastructure for the last 30 years, right? Everything that followed from this, like uh Ruby on Rails, Node.js, serverless, it all follows the same paradigm, right?

</details>

### 工作流引擎与重放模型：应对异步任务

随着Web应用日益复杂，它们开始执行请求和数据库生命周期之外的“副作用”，即**异步任务（Async Tasks）**。这些任务最初可能很简单，如发送邮件、处理支付、调整图片大小。但很快，它们演变成多步骤的副作用，例如一个订单处理流程可能包含多个顺序步骤。若在执行中发生失败（如发送收据失败），简单的重试可能导致重复收费。约10到15年前，**工作流（Workflow）和持久化执行引擎（Durable Execution Engines）**被引入以解决此问题。开发者开始将每个副作用封装成一个“步骤”，这些步骤的执行结果会被缓存。当订单处理被调用第二次时，系统会跳过已完成的步骤，仅执行需要完成的部分，避免了重复收费。这被称为“重放模型（Replay Model）”，它在无状态计算之上构建了持久化执行能力，并提供了执行历史（审计跟踪）和从特定点恢复的能力。

<details>
<summary>Original English</summary>

As web applications became more uh you know, complicated and sophisticated, they started performing these like sort of side effects outside of the request and DB life cycle. Um these side effects are async tasks. So, they you know, started out simple, let's send an email, charge a credit card, you know, resize an image. But soon they became sort of these like multi-step side effects, right? That like this process order example here. Um where you sort of do things in sequence, right? Uh you'd quickly run into a problem how to handle failures in something like this, right? So, if send receipt fails, uh you can't just retry the whole process order thing again um without charging the credit card again twice, which is bad. So, about 10 to 15 years ago, workflow and durable execution engines were sort of adopted to solve this problem, right? So, you'd write your code like this now, where you sort of uh wrap every single side effect in like a step that becomes cached as it's uh executed. So, now that, you know, solves the problem nicely. When you call process order for the second time, uh you skip the things you've already done, and then you do the thing that you want to do originally, right? And you don't charge the credit card twice. So, this is uh I call this model sort of the replay model. Um so, it builds durable execution on top of existing like stateless compute architecture, which is I covered was the you know, that's how everything works, right? So, you know, you get this nice side effect of you get this execution history, this audit trail of everything that happened. Um and also by being able to sort of resume to a specific point in time, you can Yeah, you can re- recover from a failure for that, but you can also like wait for something else to happen, right? Um so, you can wait for like a human to do something, and then you can resume execution.

</details>

### LLM Agents的局限性与新的持久化需求

LLM（大语言模型）的出现起初也契合了重放模型的范式，可被视为工作流中的一个步骤。然而，随着**工具调用（Tool Calling）**的发展，LLM开始反向**编排代码（LLM orchestrates the code）**，形成了“Agent Loop”。在这种Agent循环中，传统的重放模型面临严峻挑战：每一次LLM调用和工具调用都可能成为日志条目，导致日志急剧增长，触及“实际条目过多”或“条目内容过大”的根本性限制。Agent的生命周期与传统的、有始有终的工作流不同，它更像是一个**会话（Session）**，可能持续任意长时间。因此，Agent需要一种超越简单事务的持久化机制。

<details>
<summary>Original English</summary>

Um some of the downsides of this replay system is like because now you sort of have to wrap everything in in these steps, and then everything outside of steps is has to be deterministic, you kind of get this like uh rigid structure. You have to write your code in a certain way, or things break. Um and also like replay journaling uh re- the replay journal versioning is is kind of tricky if you deploy a new version. So, this is sort of the very simple and truncated history of like sort of the state of the world in 2023 when LLMs came out. Um At first, they really fit neatly into this paradigm, right? They would just become another step in a workflow, right? Um they would uh they would classify some text or something, but it was still in this old workflow era, right? Uh not long after that, we sort of got tool calling, and tool calling got good, and we were sort of introduced to the agent loop, right? The big difference there is code is sort of no longer orchestrating the LLM. LLM sort of orchestrates the code, right? So, we're back at our agent loop, right? And like what happens if we uh Yeah, you can see that. Um if you can If basically we want to, you know, make this agent loop durable, and can we do it with this replay model, right? What does that look like? Um so, what does that look like? Every LLM call, right, becomes a a step in in the replay uh journal. Uh every tool call becomes a step. Uh on resume, you know, the function re-executes on top and sort of replays all that stuff, right? Um so, after a single turn of uh the LLM not doing too much, you know, this is sort of what the uh the replay log looks like, right? And as you sort of keep interacting with the agent, the log grows and grows and grows. At a certain point, you might hit into some sort of like fundamental limit of your replay system. Um that could be either like too many actual entries, or it could be like the entries get grow too large. Um but yeah, this sort of kind of falls over once you hit that limit. And sort of uh there's a this measure of like how long agents uh can actually do meaningful work, and apparently it's doubling every 4 to 7 months. So, right now we're on about like a few hours, but like not too long from now we'll be on like multiple days of length as these agents build to actually do meaningful work. So, you know, replay gave us these like sort of durable transactions, but you know, an agent isn't like a transaction, it's like a session, right? And it lasts like as long as the user wants it to last. Uh multi-step workflows are sort of start and end, and sessions keep going for as long as possible.

</details>

### Agent持久化的双轨制：上下文与执行

从第一性原理出发，一个Agent的持久化需求可以分解为两个核心部分：**上下文（Context）**和**执行（Execution）**。
1.  **上下文持久化**：包括系统消息、用户消息、工具调用、工具结果以及助手响应等所有与LLM交互相关的数据。这是最重要的部分，可以视为一个**只追加（append-only）的日志**。这种日志可以通过现有的技术（如数据库、对象存储、分布式文件系统）来保证持久性，从而实现跨代码版本和机器崩溃的韧性。
2.  **执行层持久化**：Agent执行的实际计算过程，可能涉及文件读写、内存使用、创建子进程等。这部分状态无法简单地通过日志恢复。为解决此问题，需要**快照与恢复（Snapshot and Restore）**机制。这允许在Agent暂停（如用户去午餐）时，将其机器状态保存到磁盘，并在需要时恢复，从而实现跨回合的持久性，且成本相对较低。

<details>
<summary>Original English</summary>

So, if we sort of take a step back and think about what an agent needs to be durable for like from first principles, um I think of it as like an agent sort of has these two halves, right? Um the first half is the context. So, this is all all your your system messages, user messages, tool calls, tool results, assistant responses, right? So, this is all like the actual context, everything that went in and out of the LLM. Um so, this is extremely valuable, obviously. You want to make that durable, right? Um but, you also have this sort of execution layer. And as agents are like more complicated, doing more things, they kind of want a machine, right? They want to be able to do stuff like they could do on your laptop, right? They want to be able to write files, use memory, like create subprocesses. And so, I I we I think of both of these um as super valuable pieces of state, but they can be treated separately. So, the context is first and the most important, and it's just an append-only log of sort of everything that happened, right? Like I said. Um and you can make this log durable using any sort of like primitive that already exists, like a database, object storage, like distributed file system. You know, there's a a ton of like technologies that are coming out that that are specialized in making this sort of thing durable, right? And when that is durable, you When that context log is saved somewhere, now you can have durability across versions of your code, right? So, you upgrade your harness, and you can still use that same context, right? Um maybe the machine crashes, and you can still that saved somewhere, so you can pick up where you left off, right? Um and append-only logs scale really well. Uh but, what about making this sort of execution side durable, right? Uh for these, you know, as I was saying, the types of agents right now that are doing meaningful work, we there's a lot of state that happens in the compute layer that we might want to save. Maybe you've cloned a GitHub repo, you know, you've installed some packages, you've got some data sets in memory, you're running a dev server, right? You sandbox in a subprocess, whatever it is, right? You can't really make that uh durable using a log. And how do we get this to work, right? So, you you have to wait for some amount of time for the next user message, right? And we can't just keep the machine running. It'd be nice, but we can't. It'd be too expensive.

</details>

### 快照与恢复技术：Agent执行的持久化

与从日志重建状态不同，**快照与恢复（Snapshot and Restore）**是实现Agent执行层持久化的关键。这允许将机器的完整状态保存到磁盘，并在用户消息到来时恢复，从而实现跨回合的持久性，避免了不必要的持续运行和高昂成本。技术演进方面，1966年的IBM大型机已具备**检查点（Checkpoint）和恢复**能力。1966年，CRIU（Checkpoint/Restore In Userspace）出现，实现了用户空间进程的挂起与恢复。然而，CRIU主要针对单个进程，且对文件系统操作有依赖，在容器环境中也面临性能瓶颈。

到2024年，**Firecracker微虚拟机（MicroVMs）**提供了更强大的解决方案，能够快照整个机器。为解决Naive快照的成本问题（如512MB机器快照占用512MB磁盘空间），引入了**可搜索压缩（Seekable Compression）**，仅在需要时解压部分内存页面。通过分层快照等技术，可以将快照压缩至14MB。这种技术使得快照和恢复时间极短，前者不到一秒，后者数百毫秒。

Trigger.dev还推出了**FCRun（FC Run）**，一个类似Docker的CLI工具，用于在Firecracker VM中运行容器，并支持快速快照和恢复。FCRun能够每分钟启动15,000个VM，极大地提升了Agent的响应速度和可扩展性，并将成为未来计算层的核心。

<details>
<summary>Original English</summary>

So, instead of recreating the execution state from a log, we should use snapshot and restore. So, this allows us to snapshot the machine, shut it down, save it to disk, and then when the user message comes in, we restore it, right? So, this gives us durability across turns. So, when the user goes to lunch, right? We don't have to run the machine the whole time. Uh it allows us to preserve everything that the agent was doing. Uh, and you know, effectively compared to running the machine um, live, it's pretty cheap. So, I think if you combine these two things, then you sort of get a durable agent, right? Um, you've got the context, so you're sort of uh, yeah, you're context durability and execution durability, right? Um, and this also allows you to cover recover from errors. So, one of the whole whole points of having these like durability guarantees is to recover, right? And so, it depends on what happened, what went wrong, you can come recover in different ways. So, say the LLM isn't working for some reason. That never happens, but you never know, it could happen. Um, and it takes a long time to like retry. Maybe it says like wait wait, you know, 15 minutes, so you retry your next message. Well, you don't want to wait in memory, so you snapshot, and then you restore when you can retry. But, if there's something wrong with the machine, uh, maybe you've like shipped a bug, or maybe there's just a an issue with the machine, right? It crashes. You have the context log, and you can recover that. So, I think, you know, for 30 years we sort of had this, uh, stateless compute as the sort of core of back-end infrastructure. And I think agents are sort of forcing this, uh, move to become stateful compute. So, and sort of at the heart of that, I think, is is going to have to be this snapshot and restore, uh, capability. Um, but sort of, you know, this isn't actually new. Um, this is an IBM mainframe from 1966, and it actually has checkpoint and and restore. Um, cuz they would run these super expensive jobs for hours, and, you know, something went wrong, and they could couldn't afford to run it all again, so they would add these like checkpoints into their code, right? Fast forward to 2011, a thing called CRIU was um, developed. It was a way to like suspend and restore a uh, a process like from user space. So, it would basically like inject a process with this like a parasite, basically. And then they would force the process to like dump everything to memory, and then it would remove all the traces of the parasite, and it actually worked. Um, in 2024, we actually shipped this, um, and we've done millions of snapshot restores since. You know, it's transparent to the process, so the process doesn't have to like participate in it, and it's compatible with container runtimes, which is good. So, the downsides are you sort of can only checkpoint like a process. So, if you're doing stuff with like FFmpeg, or like you've got a Chrome instance running, or anything else, right? It sort of doesn't work. Uh, it only captures open files, so if you're working with the file system, it has to be open at the time of snapshot, or you won't get snapshot. And then it also, if you it yeah, it's nice that it's compatible with containers, but once you are compatible with containers, you have to work with registries and push and pull, and then it gets very slow. Uh, so last year we moved to, um, Firecracker micro VMs. And this allows us to sort of snapshot like the entire machine, right? So, everything that's is on a machine on a VM, we can snapshot it, and then we can restore it, and it pick up right where it left off, no matter what was happening in the machine, right? But, if you do that it's sort of, uh, in a naive way, uh, it can be quite expensive. So, say you have a default machine size of 512 megabytes, you know, uh, if you do a snapshot, it's 512 megabytes on disk. So, that's that's not great. Um, so obviously you've got like network network transfer costs, you've got storage costs, and there's a lot of memory there that's not actually being used. Uh, so we actually solved this with, uh, compressing it. Uh, we actually use a a seekable compression. Um, so when we restore, we actually don't restore all the memory pages at once. We actually like capture when it needs to be restored, and just like decompress like that little bit that needs to be um, restored at time. We also have a couple other techniques for layering the snapshot, and we can get the the, um, snapshot down to like 14 megabytes compressed. And that's sort of like a knob you can tweak, and um, depending on how perform what kind of performance you want. Um, you can compress more or less. Um, so that's pretty much all we had to do other than all of that. Um, and once we did that, uh, we we got super fast snapshot and restore times. So, this is a sort of a stupid graph, uh, comparing CRIU and Firecracker, but it's basically the the moral of the story is that snapshots are like slightly under a second, and restores are a couple hundred milliseconds. Um, we've actually bundled all of this into, uh, tool that's going to be open source here soon. Uh, it's called FC Run, or F Crun, depending on who you ask. Um, so this allows you it's like a Docker-like CLI, so you can drop in replacement for like the Docker command, uh, for running containers in in Firecracker VMs, and snapshotting and restoring them. So, for example, um, you can run Alpine, and it's super fast, and you can snapshot running VM, and it's super fast. You can like fork a VM, also very fast. Um, this is a little benchmark for TTI, so basically how long it takes for the VM to become, uh, interactable with the internet. So, this is, uh, but we're doing like 15,000 VM starts per minute. Um, you can almost render, uh, like a video. The the FPS would be about 30 FPS. Um, so it's it's extremely extremely fast. Um, so this is going to be powering sort of our future like compute layer, but it's open source. Um, not yet, but very soon.

</details>

### 结论：Agent迈向有状态计算的未来

通过结合**上下文日志持久化**和**执行快照恢复**，我们可以构建真正**持久化（Durable）的Agent**。这带来了跨版本、跨回合、跨故障的持久性保证，为Agent的稳定运行奠定了基础。正如Agent正在迫使后端基础设施从传统的**无状态计算（Stateless Compute）**向**有状态计算（Stateful Compute）**转变，快照与恢复能力将成为未来Agent核心技术的一部分。

<details>
<summary>Original English</summary>

Um so, kind of back to where we started with our little agent loop here, and, um, we've sort of made it durable now by doing two different things, context log and execution snapshot. So, we got durability across versions, durability across turns, across failures, and I think this will lead to a future of, you know, stateful compute. That's it. Yeah.

</details>