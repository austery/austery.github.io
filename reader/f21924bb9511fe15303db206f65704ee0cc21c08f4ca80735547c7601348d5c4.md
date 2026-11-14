---
author: AI Engineer
date: '2026-11-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_0SQh8a1Osk
speaker: AI Engineer
tags:
  - agent-infrastructure
  - sandboxing
  - cloud-computing
  - observability
title: Modal CTO 谈 AI Agent 底层基础设施需求与演进
summary: Modal 首席技术官 Akshat 探讨了 AI Agent 对底层基础设施的真实需求。他指出 Agent 需要隔离的工作区、长时状态持久化、弹性算力、多容器沙箱、细粒度安全控制及深度可观测性，并强调不应随意搭建（vibe code）沙箱平台，而应构建可靠的原语支持高并发与动态环境演进。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Modal
  - Ramp
products_models: []
media_books: []
status: evergreen
---
### Agent 对基础设施的真实需求与电子表格场景

大家好。我是 Modal 的首席技术官 Akshat。今天我打算聊聊 Agent 到底需要什么样的基础设施？
<details>
<summary>Original English</summary>
Hey everyone. I'm Akshat, CTO of Modal. And I'm going to talk about what do agents really need from their infrastructure?
</details>

有人告诉我现场的听众大多和金融领域相关。所以我想，不妨聊聊如果电子表格中的每一个单元格都由一个 Agent 来支持，会是怎样一番景象？
<details>
<summary>Original English</summary>
So I'm told this audience is very finance adjacent. So I thought I'd talk about what if every cell in a spreadsheet could be backed by an agent?
</details>

想象一下，你是一家基金公司的财务分析师。你想要对投资组合里的每一家公司都运行复杂的分析。以往通常需要花费数天时间。你必须连接到每家投资组合公司，查看他们的数据源，并分别为它们运行一些 Python 代码。而现在，有了 Agent 之后，这一切显然应该轻松得多。
<details>
<summary>Original English</summary>
And imagine your a financial analyst at a fund. You want to run complex analysis on every company in your portfolio. Normally in the past this would take days. You'd have to connect every portfolio company, look at their data sources, run some Python for each of them. And now obviously with agents this should be much easier.
</details>

实际上，我们的一个客户 Heavy AI 就打造了完全符合这种设想的产品。你现在就可以进入他们的产品：你拥有一张电子表格，可以运行一条查询，其中字面意义上的每一个单元格都由不同的 Agent 在底层提供支持。我想谈谈构建这样的系统究竟意味着什么。
<details>
<summary>Original English</summary>
Well, actually one of our customers Heavy AI built something that's exactly this. You can go in right now in their product, you can you have a spreadsheet and you can run a query where literally every cell is backed by a different agent. And I wanted to talk about what does building this really look like?
</details>

### 沙箱架构：多容器、隔离与共享存储

首先，每一个 Agent 都由一个 Modal 沙箱作为后盾。沙箱是用于运行不可信代码的安全环境。过去，每个沙箱通常与一个容器或微型虚拟机（micro VM）一一对应。但现在情况并非如此了。
<details>
<summary>Original English</summary>
Well, first every agent is backed by a Modal sandbox. So sandbox is a secure environment for running untrusted code. And it used to be that every sandbox was one-to-one with a container or micro VM. That's actually no longer the case.
</details>

如今，Modal 具备了在一个沙箱内运行多个容器或微型虚拟机的特性。要做类似刚才提到的系统，实际上正需要这种能力。在这种架构中，你会运行一个 harness（测试套件/运行回路）。Harness 是 Agent 的循环回路，负责调用 Modal API 进行推理、运行工具调用并进行循环迭代。出于安全性、隔离性等诸多考虑，你会希望将这一部分与真正执行工具调用的场所分离开来。
<details>
<summary>Original English</summary>
Today actually uh, has this, uh, feature where you can run multiple containers or micro VMs inside a sandbox. And you actually need to do that for doing something like this, where, um, in this architecture, you run the harness. Uh, the harness is the agent loop that does things like running the calling the Modal API for inference, uh, running the tool calls, and then looping over it. Uh, you want to separate that from the place where the tool calls actually run. Uh, for security and isolation and a bunch of other things.
</details>

因此你的沙箱内会运行多个容器，包括一个 Sidecar（边车容器）。此外，你还需要共享存储，因为你希望 Agent 之间能够互相通信。具体如何进行数据条带化存储由你决定，比如可以让每一行获得相同的卷，这样电子表格该行中的 Agent 就能进行协作。在某些情况下，你也希望在主容器和 Sidecar 之间共享存储。
<details>
<summary>Original English</summary>
Uh, so you have the sandbox that's running multiple containers, including a sidecar. Uh, you also want shared storage, uh, because you want your agents to be able to talk to each other. And it's up to you how you uh, stripe it. Like maybe you have every row uh, gets the same volume, and agents in that row in the spreadsheet can collaborate. Uh, and you also want to share storage between your main container and the sidecar for some cases.
</details>

最后，所有这些都必须能够极其快速地启动，因为你的电子表格可能包含大量的单元格。一旦有人发起查询，你希望瞬间拉起数千个 Agent，并在任务结束时再将它们销毁关停。
<details>
<summary>Original English</summary>
And finally, you need all of this to spin up really, really fast, because your spreadsheet can have lots of cells. If someone has a query, you want to launch thousands of agents, and then you want to spin them back down when it's over.
</details>

### Modal 平台定位与工作区持久化需求

在深入探讨之前，先简单插一句，介绍一下 Modal 是什么。Modal 是一个专为 AI 应用构建的原语平台。我们基本上是从零构建了这个平台，打造了自己的文件系统、调度系统以及运行时，旨在为各类用例提供极佳的性能和开发体验——包括大语言模型推理等推理任务、沙箱、模型训练、函数计算，以及运行海量批处理等场景。今天我将重点探讨沙箱，说明这一原语是什么，以及它是如何演进的。如果你想构建类似的应用，甚至走得更远，你需要哪些底层原语？
<details>
<summary>Original English</summary>
So, before I talk more about, uh, that, uh, just wanted to take a quick aside to talk about what is Modal. Uh, Modal is a platform of primitives that is built for AI applications. Uh, so we've basically built this platform for, uh, from scratch. We've built our own file systems and scheduling and, uh, the runtime, uh, to give you really great performance and dev ex for use cases like inference, including LM inference, sandboxes, training, and, uh, functions, running a lot of batch processing and whatnot. Uh, and today in particular, I'm going to talk about sandboxes, what this primitive is, and how it's evolving. Uh, so if you want to build something like this, uh, or even further, and we'll talk more about what that means, uh, what are the primitives you need for that?
</details>

首先，如果你在构建 Agent，你需要一个工作区。我这里有一些来自我们现有客户的示例。大家可能听说过 Ramp Inspect。Ramp Inspect 是 Ramp 内部的代码 Agent，我想目前 Ramp 几乎每一个 PR 都是由它提交的。如果要构建代码 Agent，你需要将代码仓库（GitHub 仓库）、依赖项和开发服务全部放置在同一个工作区内供每个 Agent 使用。
<details>
<summary>Original English</summary>
So, the first thing is if you're building an agent, you need a workspace. And I have some examples from some of our current customers. Uh, you might have heard of Ramp Inspect. Uh, Ramp Inspect is uh, Ramp's internal coding agent that, uh, I think at this point, pushes almost every single PR at Ramp. Uh, and if you're building a coding agent, you need your, uh, repo, uh, your GitHub repo. You need your dependencies. You need your dev services all in the same workspace, uh, for each agent.
</details>

另一个例子是 Basis，他们做的是会计 Agent。如果要构建这类系统，你需要将各类文档、会计底稿以及编写的脚本全部集中在一个工作区内。我们还有一家非常有趣的游戏开发客户公司。如果使用 Agent 进行游戏开发，你需要把游戏引擎和资产都放在一处。
<details>
<summary>Original English</summary>
Uh, another example is Basis. They're an, uh, accounting agent. And if you're building that, you need your, uh, documents. You need your accounting work papers. You need scripts you've written, uh, all in one work workspace. Uh, and we have another, uh, very interesting company. They're game dev company. And if you're doing game dev with agents, you need your game engine. You need your assets, uh, all in one place.
</details>

下一步是这些工作区需要能够持久化。回到 Basis 的会计示例：其流程可能是文档送达，触发 Agent 开始处理，但接着它需要等待会计师的回复。你无法预料这需要等待多久，可能是好几天。当会计师回复时，你希望 Agent 能够重新启动，并从上次停下的地方继续进行。
<details>
<summary>Original English</summary>
The next step is you need these workspaces to persist. Uh, so going back to the accounting example with Basis, what it looks like is your documents might arrive. Your, uh, agent is then triggered to work on them. But then it's waiting for a response from the accountant. And you don't know how long this could take. Could take many days. Uh, when the accountant responds, you want the agent to start up again and continue from that last place where things were left off.
</details>

因此你希望随时间持久化状态，甚至可能是无限期持久化。但你并不想在整个等待期间都运行算力，因为计算资源成本高昂。所以你只希望在 Agent 实际工作时才运行算力。这是我们在 Modal 中支持的功能，而且我们意识到用户需要多种不同形式的持久化：有时你可能希望对整个根文件系统打快照；有时可能只想对单个目录打快照，比如 node_modules 文件夹，之后你还想随着时间推移升级基础镜像；还有时你可能需要类似于卷（Volume）这样的共享文件系统。
<details>
<summary>Original English</summary>
Uh, so you want to persist the state over time, uh, potentially indefinitely. But you don't want to run the compute the entire time because compute is expensive. So, um, you only want compute to run when the agent is actually working. Uh, this is something we support in Modal, and we've realized that there's a bunch of different flavors of persistence that people need. Uh, sometimes you might want to snapshot your whole root file system. Uh, sometimes you might want to snapshot just a single directory. And uh, maybe it's like your node modules folder. But then you want to upgrade your base image over time. And sometimes you might need something that looks more like shared file system like a volume.
</details>

### 资源弹性与异构算力（GPU）

一个非常有趣的现象逐渐显现：Agent 在资源消耗上其实需要极大的弹性。我们获得了 Ramp 的许可，可以分享一些来自 Ramp Inspect 的数据。如果观察他们工作负载中随机运行的沙箱，会发现无论是在不同沙箱之间，还是在同一个沙箱随时间推移的过程中，Agent 所使用的 CPU 和内存都存在巨大的差异。
<details>
<summary>Original English</summary>
A very interesting thing that's been showing up is agents actually need a lot of elasticity in resource consumption. So we got permission from Ramp to share some of the data from Ramp Inspect. And if you look at random sandboxes running in their workload, they actually all have a huge amount of variance both
</details>

>> [发出轻嗤声]
<details>
<summary>Original English</summary>
>> [snorts]
</details>

>> 无论是在沙箱彼此之间，还是同一沙箱内部随时间变化，Agent 使用的 CPU 和内存波动都极大。这完全讲得通：如果你正在编译非常消耗资源的内容，或者正在进行需要大量内存的分析，用量自然会发生变化。在第二张图表中，你可以看到每个沙箱的峰值用量。尽管存在一些一致的趋势，但整体分布非常离散。
<details>
<summary>Original English</summary>
>> versus each other but also over time within the same sandbox for how much CPU and memory the agent is using. And it makes sense. I mean, what if you're compiling something that's very resource-intensive or doing some analysis needs a lot of memory. Your usage is going to change. And in the second chart, you can see peak usage for each sandbox. And there's definitely some consistent trends but it's all over the place.
</details>

如果你按照峰值去预配资源，最终就得为每个沙箱都配置例如 15 个 CPU 核心和 15 GB 内存，这在经济上完全是不切实际的。我们在 Modal 投入了大量精力所做的事情，就是让用户基本上无需提前申请这些资源，而是在沙箱需要时可靠地获取它们，并且只需按使用时长付费。
<details>
<summary>Original English</summary>
So if you were provisioning this for the peak, you would end up provisioning like 15 CPU cores and 15 gigs of RAM for every sandbox, which is just doesn't make sense economically. And something we've worked on a lot in Modal is letting users basically not have to request these resources up front and then reliably get them when the sandbox needs them and only pay for them for for that duration.
</details>

另一个正在出现的新趋势是，Agent 需要更丰富的算力类型。比如随着时间推移它们需要 GPU，以后可能还需要 TPU、AMD 芯片等，谁也说不准。Cloud Science 就是一个绝佳的例子，Cloud Science 出厂就自带 Modal 集成。它的使用方式是，当 Cloud 需要执行密集型计算时——例如在 CPU 上预处理数据，或者拉起 GPU 来运行科学模型——它就会将这些任务卸载给 Modal 沙箱。我们在游戏设计、视频编辑、3D 开发（如 CAD）等领域都看到了这种需求，这些场景中的 Agent 全都需要 GPU。
<details>
<summary>Original English</summary>
The other interesting emerging thing is agents need a lot more interesting compute. Like they need GPUs over time, they might need TPUs, AMD, who knows. And great example of this is Cloud Science where Cloud Science actually ships with a Modal integration out of the box. And the way it's used is when Cloud needs to do some intensive compute like pre-process some data on CPUs or spin up GPUs for running a scientific model, it will offload that to a model sandbox. And we're seeing this show up in things like game design, video editing, 3D dev, like CAD, all of those things need GPUs for your agent.
</details>

当然，当前让所有人最为兴奋的莫过于 RSI，即递归自我改进（recursive self-improvement）。这正是 GPU 沙箱所极其擅长的，而 Agent 也非常擅长利用它们。我们写过一篇博文，探讨给 Agent 配备沙箱以在模型训练中进行爬山算法（hill climbing）优化时会发生什么。事实证明它们表现非常出色：它们能够调换 GPU、并行运行消融实验、跑大量实验，然后非常快速地达成目标。
<details>
<summary>Original English</summary>
And of course, the the thing that everyone's really excited about right now is RSI or recursive self-improvement. And that's something that GPU sandboxes are really good at and agents are really good at using them. So we have this blog post about what happens when you give an agent sandboxes to hill climb over training a model. And it turns out they're very good. They can swap GPUs, they can run ablations in parallel, run lots of experiments, and then really get to the target very quickly.
</details>

### 多 Agent 协作、安全控制与可观测性

另一个正在出现的趋势是 Agent 之间的协作显著增多。这意味着你需要与你的子 Agent 共享文件系统，你与人类共享文件系统和文件，大家协同处理同一份内容。这需要快速、具备一致性且开发体验易于理解的文件系统。这也是我们正在通过 Modal Volumes 推进的工作。
<details>
<summary>Original English</summary>
The next emerging thing is agents are collaborating a lot more. And that means that you share a file system with your sub-agent, you share file systems and files with your human where you're all collaborating with the same thing. And this needs file systems that are fast, have consistency, and dev acts you can reason about. Something we're working on with model volumes.
</details>

与之相关的是，我们看到了越来越多的自我改进机制。Agent 会保存并更新记忆，它们会运行后台任务——现在这被称为“做梦（dreaming）”——来随时间更新这些记忆。实际上，这在底层表现出来的形式也只是文件系统中的文件。但同样地，你需要该文件系统具备极佳的性能。
<details>
<summary>Original English</summary>
Related thing is we're seeing a lot more self-improvement. So agents will save and update memory, they'll run background tasks, which is now called dreaming, to update this memory over time. And actually, this also just looks like files in a file system. But again, you want really good performance from this file system.
</details>

关于 Agent，令人担忧的一点在于它们可能会犯错，而且它们并不清楚自己何时可能会把你的敏感数据泄露到某个德国论坛之类的地方。因此你必须对它们能做什么、不能做什么拥有高度的控制权。你需要具备诸如控制哪些 IP 能够与 Agent 通信、如何对其进行认证、它能与哪些域名通信等机制。此外，如果你使用凭证访问各类服务，你基本上需要以一种让 Agent 无法实际看到凭证的方式注入它们，防止之后被外发泄露。
<details>
<summary>Original English</summary>
And the scary thing about agents is they can mess up and they don't really know when they might leak your sensitive data to a German forum or something. So you need to have a lot of control over what they can and cannot do. Uh and you need things like controlling what IPs can even talk to the agent, how do you authenticate it? Uh what domains can it talk to? Uh and also if you're using credentials for talking to services, um basically you want to inject them in a way that the agent cannot actually see them and then exfiltrate them somewhere later.
</details>

这一领域的有趣演进在于，我们意识到仅仅基于域名的允许列表实际上是不够的。我们的许多用户其实希望获得非常具体的控制，比如精细到能够访问 DataDog 或 GitHub 上的哪些具体路径。例如，我可能希望能对 Agent 正在执行的具体操作进行逻辑研判。回到 Sidecar 模式，我们看到这正演变成一种通用模式：用户自己编写轻量级代理，配置关于其具体允许行为的自定义规则。Ramp 是成功运用这一模式的又一个公司范例。
<details>
<summary>Original English</summary>
And the interesting evolution of this is we've realized that domain uh related allow lists are actually uh not enough. You uh a lot of our users actually want very specific control over even like what paths can I talk to uh on let's say DataDog or GitHub. Like maybe I want to reason about specific operations that the agent is doing. And going back to sidecars, we've seen this emerging as a pattern where users actually write their own lightweight proxy that has custom rules about what exactly it can do. And Ramp is another example of uh company that's been using this successfully.
</details>

最后一件常被低估、但至关重要的事情是拥有极佳的可观测性。回到自动研究以及 Agent 执行大量训练任务的例子：当训练运行失败时会发生什么？你希望你的 Agent 能够轻松查看失败日志，推断发生了什么，并带上一套不同的参数进行下一次迭代。在训练运行期间，你希望它能够查看指标、查看 GPU 利用率以确保其未停滞；或者你希望查看预算，确保沙箱内的花费没有超标。显然，所有这些对人类而言都非常重要；但随着 Agent 驱动越来越多的计算，我们正投入大量时间把所有这些信息暴露给 Agent 本身，以便它们能够对这一切进行分析判断。
<details>
<summary>Original English</summary>
Uh and the final underrated thing is it's really important to have really great observability. Uh so, going back to the example of auto research and an agent doing a lot of training, uh what happens when the training run fails? Uh you're you want your agent to be able to easily look at the logs of the failure, uh reason about what happened, and do another iteration with uh different set of parameters. And while training is running, you want it to be able to look at the metrics. You want to look at GPU utilization and make sure it's not stalled. Uh maybe you want to look at the budget and make sure you're not spending too much in your sandbox. Uh and obviously all of this is really important for humans, uh but as agents are driving a lot more compute, uh it's we're spending a lot of time exposing all of this to the agents themselves so they can reason about all of this.
</details>

### 为何不应“凭感觉编写”沙箱基础设施

好了，我想我们已经知道需要什么了。那为什么不让 Astra 帮我们搭建一个 Agent 平台呢？
<details>
<summary>Original English</summary>
All right. I think uh we know what we need. Why don't we have Astra build us an agent platform?
</details>

我认为这不是个好主意。我觉得你不应该“凭感觉编写”（vibe code）一个沙箱平台。主要原因有三个：
<details>
<summary>Original English</summary>
Well, I don't think it's a good idea. I don't think you should vibe code a sandbox platform. And there's three main reasons for that.
</details>

第一是可靠性。我想大家都深切体会过把可靠性做好有多难。我们每天使用的某些网站总是宕机。原因在于，即便利弊于 AI，在系统崩溃的极端长尾事件中推演其反馈回路实际上仍然非常困难。这就是为什么构建系统时需要格外谨慎。
<details>
<summary>Original English</summary>
Number one is reliability. I think we're all painfully aware how hard it is to get right. Certain websites we use every day keep going down. And the reason for that is even with AI, it's actually really hard to reason about the feedback loop of like what happens in the case of this tail event when the system breaks. And this is why you need to be very careful in building systems.
</details>

安全性是另一个原因。你可以凭感觉编写出一个沙箱平台，但在一切都在快速演进的时代，谁来持续审查安全边界并确保其坚不可摧？
<details>
<summary>Original English</summary>
Security is another one. You could vibe code a sandbox platform, but who is going to do all the work to like continually reason about the security boundaries and make sure it's defensible in in an age when everything is evolving very fast.
</details>

最后是规模。我们有一篇博文介绍我们如何扩展到支持 100 万个沙箱，这涉及到大量非常有趣的工程设计与系统推演。这同样也是你不希望留给一个凭感觉编写的平台的事情，因为当达到这种规模时，你必须确保它能稳定工作。
<details>
<summary>Original English</summary>
And finally scale. We have a blog post about how we scale to a million sandboxes, which involves a lot of very interesting engineering design and reasoning about systems. And this is again something that you kind of don't want to leave up to a vibe coded platform because when you get to scale, you want it to work.
</details>

关于这一点，我刚才提到的很多方面我们实际上都见证了极大规模的增长。比如前面提到的快照，其增长速度相当快：我们每周见证 2000 万次快照，每天为这些快照处理约 8 PB 的数据。我们的用户每周创建近 260 万个卷。所有这些指标都在飞速增长。
<details>
<summary>Original English</summary>
And on that point, we're we're actually seeing massive scale for for a lot of things I mentioned. So, for example, for the snapshots I mentioned, uh it's growing quite fast. We're seeing 20 million snapshots a week. We're processing about 8 petabytes of data a day for for each of these snapshots. And our users are creating almost 2.6 million volumes a week. And all of this is growing super fast.
</details>

以个人助手的客户工作负载为例：你每秒需要创建 10,000 个沙箱，需要运行近 100 万个沙箱。这些沙箱存活时间不会太长，通常只持续两三分钟；但当它们启动时，你希望它们能在不到一秒的时间内具备交互能力。这就是此类工作负载的真实要求。
<details>
<summary>Original English</summary>
And just to take a customer workload for personal assistant, you need to create 10,000 sandboxes a second. You need to run um almost a million sandboxes. And they're They're going to last very long. They'll just last for like two or three minutes. Uh but when they come up, you want them to be interactive in in less than a second. That's that's what this workload really demands.
</details>

关于规模的另一个有趣之处在于，实际上你无法从单一云平台上获取全部所需的规模。全球不仅在 GPU 方面面临短缺，CPU 同样陷入紧缺。因此我们花费大量时间做的一件事，就是汇聚来自各大超大规模云服务商（hyperscalers）和新兴云厂商（neo clouds）的云算力。这样一来，我们的用户在需要时便能获取遍布全球的 CPU 算力，而我们不能依赖单一云服务商来实现这一点。
<details>
<summary>Original English</summary>
And the other interesting thing on scale is you actually cannot get all of the scale from a single cloud platform. The world is actually getting crunched on CPUs as well, not just GPUs. Uh so one thing we spent a lot of time doing is actually aggregating cloud capacity from a bunch of hyper scalers and neo clouds. Uh so our users have access to CPU capacity across the world when they need it. Uh but we cannot rely on one cloud provider to do that.
</details>

### 从“宠物到牛群”到“微生物海洋”的演进

那么，这一切的演进方向是什么？我前面稍有提及：harness 非常擅长利用动态环境。这导致了大脑（即 harness）与手（即沙箱或执行代码的运行时）之间的大量分离。
<details>
<summary>Original English</summary>
Okay, so where is all this going? I I hinted at this earlier, but the harnesses are really good at making use of dynamic environments. And what this is leading to is a lot of separation of the brains, which is the harness, uh from the hands, which is the sandbox or the runtime where stuff is running.
</details>

这意味着——我这里有一个例子——harness 将能够根据当下的需求即时拉起各种环境。它们擅长给环境打快照，并保留它们作为后续所需的构件，并在必要时重新调整这一切。
<details>
<summary>Original English</summary>
And um what this means, I have an example here, is the harnesses are going to be able to spin up environments based on what they need right now. They they they're good at snapshotting them and keeping them around for uh as artifacts that they need later. Uh and again, adjusting all of this as necessary.
</details>

因此，我认为这揭示了我们所熟知的从“宠物到牛群（pets to cattle）”类比的一个有趣演进。回顾一下：在过去，人们把服务当作宠物对待，每一台都是定制的，你必须亲自管理它，必须单独思考这一具体的部署。
<details>
<summary>Original English</summary>
So I I think this points at an interesting evolution of the pets to cattle uh analogy we're all familiar with. Uh to recap, in the olden days, uh people thought of services like pets. Uh each one was bespoke. You had to manage it. Uh you had to reason about this individual deployment uh specifically.
</details>

随着时间推移，伴随着容器化和 Kubernetes 的普及，人们开始将其视为同构模板——这些服务器全都是一样的，你可以对其进行扩容和缩容。如果其中一台宕机了，不会成为大问题，因为系统能够自我修复。我认为这也是今天许多部署 Agent 的人所处的位置：他们正在使用这些同构环境来扩容 Agent。
<details>
<summary>Original English</summary>
Uh and then over time, it um with containerization and Kubernetes, uh people started to think about it as um homogeneous uh templates uh of uh these servers are all the same. You can scale them up and down. If one of them fails, it's It's an issue because our system can heal from that. And I think this is where a lot of people deploying agents are today. They're kind of using these homogeneous environments and scaling up these agents.
</details>

但我认为这种做法非常受限，因为模型非常擅长推演动态环境、进行快照、在需要时创建大量环境并在它们之间协同工作。那么新世界会是什么样子呢？这里有一个类比：它有点像微生物的海洋，充满着各类自我演进、相互协作的有机体。（在此感谢 Six 提出的这一类比）。
<details>
<summary>Original English</summary>
But but I think that's really limiting because the models are so good at reasoning about dynamic environments, snapshotting, uh creating lots of environments when needed, and working across them. Uh so what what does the new world look like? Uh one analogy here is it kind of looks like an ocean of microbes, of all these organisms that are self-evolving and working with each other. Uh and credit to Six for the analogy here.
</details>

我真正感到兴奋的是，当你为 Agent 提供这些在计算、存储和网络方面极其坚固的原语时，它们将能够通过前面提到的方式做更多事情——比如拉起大量环境、彼此协同工作并保持极高的动态性。我和 Modal 团队坚信，优秀的底层原语能让你的 Agent 具备更强大的能力。如果大家有兴趣就此展开更多讨论，欢迎联系我们。谢谢大家。
<details>
<summary>Original English</summary>
Um but one thing I'm really excited about is as you give agents these really rock-solid primitives for compute and storage and networking, they will be able to actually do a lot more um by doing the stuff I talked about, like spinning up lots of environments, working with each other, and being very dynamic. So yeah, I and us at Model really think that great primitives let your agents do more. And uh yeah, if you're interested in talking about this more, reach out to us. Thank you.
</details>