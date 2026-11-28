---
author: AI Engineer
date: '2026-06-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UPwGaM2MKHY
speaker: AI Engineer
tags:
  - agentic-architecture
  - event-sourcing
  - state-management
  - data-ownership
title: 日志即智能体：重构 AI 系统的持久化与架构范式
summary: Omnara 首席执行官 Ishaan Sehgal 提出“日志即智能体”的核心理念，主张将智能体定义为只追加的事件历史日志，而非模型或运行时环境。这种架构设计不仅从工程上自然解决可靠性、可扩展性、多端协同和平台迁移等痛点，还能确保用户对智能体最核心的私密数据资产拥有自主所有权，避免日志锁定。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Omnara
products_models: []
media_books: []
status: evergreen
---
### 概念重构：智能体的本质是数据而非模型

**智能体**（Agent: 能够自主感知、决策并执行任务的 AI 系统）的本质究竟是什么？很多人倾向于将其等同于大语言模型本身，或者是它所运行的执行环境，但这其实是一个错误的抽象。实际上，真正赋予智能体身份和灵魂的是它的**日志**（Log: 记录所有事件与状态变更的持久化数据流）。

为了理解这一点，我们可以用电子游戏《上古卷轴5：天际》（Skyrim）来做个类比。你在《天际》中玩了上百小时创建的游戏角色究竟是什么？是游戏引擎吗？是 PlayStation 主机吗？还是手柄？显然都不是。虽然这些底层的硬件和渲染引擎必不可少，它们负责运行和渲染角色，但它们本身 squat 并不是角色。你的角色实质上是数据——也就是那份**存档文件**（Save File）。如果你的 PlayStation 主机突然着火烧毁了，你的角色并没有因此消失。你只需要再买一台新的主机，从云端下载你的存档文件，就能完全恢复到之前的状态，继续进行游戏。这是因为角色的身份、历史和状态全部被捕获并保存在了数据中。

同样的逻辑也适用于 AI 智能体。目前人们在讨论智能体时，往往将目光投向了错误的地方，认为模型或运行环境就是智能体。这些确实重要，但智能体本身是由它的数据定义的，具体而言，就是它的事件日志。

<details>
<summary>Original English Source</summary>
Hey everyone, I'm Ishaan the CEO of Amnara and today I'm going to be talking about the log is the agent. The basic idea of the talk is simple and that is most people think of an agent as the model or the execution environment that it's running in and I think that that's the wrong abstraction. I think that the thing that actually gives an agent its identity is its log and that's what I'm going to be arguing today.
So think about a character you've spent a hundred hours playing in your favorite video game, in this case Skyrim. What exactly is your character? Is it the game engine? Is it the PlayStation? Is it the controller? No, it's not. Those things matter and those things are what will interact with and they'll run the character but none of those things are your character. Your character is data. It's the save file. And this is important because if your PlayStation bursts into flames, your character isn't gone. You can buy another PlayStation, you can download your save file from the cloud and you can resume exactly where they were and that's because the agent and its identity and history and its state is all captured in its data. The character lives in the data and this is the framing that I want to bring to agents. Today when people talk about agents, they usually point at the wrong thing. They'll say that the agent is the model or they'll say that it's the runtime and again as I mentioned earlier, those things matter but they're not the agent. The agent is its data. It's specifically the log.
</details>

---

### 日志主导：事件溯源与无状态执行循环

在最简单的层面上，日志是智能体一个**只追加**（Append-only: 只能在末尾添加新数据而不能修改历史记录）的事件历史记录。它完整地记录了每一次用户输入、每一次模型输出、每一次工具调用及结果、每一次权限获取以及遇到的失败。智能体所经历的每一次状态转换都会被实时写入到这个日志中。

这种架构的精妙之处在于，智能体的身份与运行环境、模型或特定工具彻底解耦了。这些组件的角色只是去解读日志并在其上追加新的事件——它们读取日志、执行操作，然后将下一个事件写回日志。如此循环往复。

基于这一理念，整个系统的运作逻辑变得极其清晰和易于推导：我们可以随时从日志中完全重建智能体的当前状态，将其传递给模型；模型提出下一步的行动方案，并把这个提议追加到日志中；如果模型需要调用工具，系统执行该工具并将执行结果同样追加到日志中，然后重复这一过程。

这里的核心洞察并非这个循环有多复杂，而是**执行循环是可丢弃的**（Disposable Loop: 随时可以销毁重建的无状态执行过程）。一个工作节点可以随时声明接管当前会话，读取日志，推动智能体前进一步，写入结果，然后彻底消失。随后，任何其他工作节点都可以在未来的任何时刻重新接管并继续运行。

这种设计理念实际上是在重复数据库技术曾经走过的路。几十年来，数据库在外表上看起来非常复杂，有着各种表、索引和物化视图，但其最底层、最核心的其实就是一个日志（如 Write-Ahead Log）。日志是数据变更的持久且唯一的真实数据源，其他的一切（表、视图）都只是基于日志的投影。智能体也需要经历同样的范式倒转。如今智能体系统充斥着复杂的模型、提示词和工具调用，显得极其不透明，但要实现持久化的会话，必须将日志视为核心主权。输入给模型的上下文、渲染给用户的界面、调试和链路追踪、审计乃至日志压缩，全都是基于这份日志的投影。日志本身不是投影，它是所有投影得以生成的唯一持久历史源泉。

<details>
<summary>Original English Source</summary>
So what actually is the log? At the simplest level, the log is the append-only event history of the agent. It's every user input, every model output, every tool called, tool result, permission, failure and the idea is that every state transition that the agent takes is written to the log. This is important because it means that the identity of the agent isn't tied to the runtime or the model or the tools. Those things are all just interpreting and appending to the log. They're reading the log, acting on it, and writing the next event back. And that's important because then just using the log on its own is enough to resume the agent. Once you define the agent as a log, the rest of the system becomes a whole lot easier to reason about because every operation is either reading from or appending to the log. The model is reading from the log and then determining the next action. The tool runner is then executing that action and then it's appending that result. And this is all operating in a loop. Everything coordinates itself around the log. In practice, a simplified loop can look something like this. You can reconstruct the state from the log. You can pass that state to the model. The model can propose the next step and then append that response to the log. If the response asks for a tool, you can run that tool and also append that response to the log and then you can repeat. The important insight is not that this loop is complicated. The important insight is that the loop is disposable. A worker can claim the session, read the log, advance the agent one step, write the result, and then just completely disappear. And then that means that any other worker can pick it up later.
This pattern should feel familiar. Databases had to learn this first. For years, databases looked like these non-transparent systems that were hard to reason about with tables and indexes and materialized views, but underneath every serious database is a log. And that log is the durable sequence of changes. Everything else is a view. I agents need the same inversion. Today, agents are treated as again, these complicated systems that are opaque and they're filled with models and prompts and tool calls, but for the durable session, the log should be primary. The context that gets fed into the model is a projection of that log. The UI that gets rendered on top is a projection of that log. Debugging and traceability is a projection. Auditing is a projection. Compaction is also projection, which we'll talk about. But the log itself is not a projection. The log is the durable history that all of these projections can come from.
</details>

---

### 边际应对：日志压缩与外部非确定性状态

关于“日志即智能体”的设定，有两个非常值得探讨的常见质疑：**日志压缩**（Compaction）和**外部状态变更**。

首先是日志压缩问题。日志可以无限增长，但大语言模型的上下文窗口是有限的，不可能无限制地接收全部历史。因此，我们最终必须将日志压缩成更紧凑的表示形式，以便模型能够进行推理。但需要明确的是，这种压缩工程并不是什么魔法，它并没有打破“日志即智能体”这一论断。压缩本身是**有损的**（Lossy: 会丢失部分细节信息的非完全重现），压缩后的摘要无法在更小的形式下完美复现智能体的完整历史状态，它必然会丢弃部分信息。因此，原始的完整日志才是智能体的终极记录，而压缩摘要仅仅是该日志的一个特定投影。这就像物化视图并不等于数据库，对话的摘要也不等于对话本身一样。只要你保留了原始日志，你就随时可以重新生成新的投影；但如果你丢弃了原始日志而只保留压缩摘要，你就已经永久失去了智能体的一部分。最干净的做法是将压缩视为一次尽力而为的有损分叉（Fork），并将其作为一个新的日志进行恢复和运行。

第二个质疑是：那些在日志之外改变状态的工具该如何处理？例如，智能体在执行过程中编辑了一个本地文件、创建了一个 GitHub Issue 或是发送了一封电子邮件。这些操作显然在日志外部产生了状态改变。然而，日志的职责从来都不是包含整个世界，它只需要记录智能体自身的**世界观**（Agent's View of the World）。这正如在《天际》中，角色的存档文件并不包含整个游戏引擎或地图上的每一个三维资产，它只包含让玩家重新回到那个世界所需的特定玩家状态。智能体也是如此，日志只能忠实地恢复和存储智能体的身份及其对世界的观测，而无法让外部世界变得具有确定性。如果智能体已经发送了一封邮件，你在日志中回滚（Fork）是无法撤销发送的；如果底层的物理文件被外部修改了，智能体也无法凭空感知。但是，日志记录了智能体曾经做过什么、看到了什么、发生了什么改变，以及它继续运行所需的信息。这就是它的唯一使命。

<details>
<summary>Original English Source</summary>
Now, there are two objections to the log as the agent that are worth discussing. So, I'm going to talk about them now. Now, let's start with compaction. A log can grow indefinitely, but a model's view of it can't. Context windows are finite. So, eventually, you do need to compact the log into a smaller representation that the model can reason about. But the important point is that this compaction is not magic and it doesn't break the claim that the log is the agent. Compaction is lossy. A compacted summary is not going to perfectly reproduce the state of the agent in a smaller form. It's actually going to throw information away. The point is the full log is the record and a compaction is just one projection of it. Just like how a materialized view is not the database or a summary of a conversation is not the conversation. If you keep the raw log, you can always generate new projections from it. But if you throw away the raw log and keep only the compaction, you've effectively lost part of the agent. So, it's cleanest to treat compaction as a best effort lossy fork, one that you can resume as a new log.
The second objection is what about tools that change state outside of the log? And that's true. An agent can edit a file. It can create a GitHub issue. It can send an email. So, clearly, there is state outside of the log. But, the point is is that the log is not supposed to contain the whole world. The log is just the agent's view of the world. It's just like how in the video game in in Skyrim, the Skyrim save file doesn't contain the entire game engine or every asset in the map. It just contains the player specific state, which is needed to drop you back into that world. And the same is true for the log and agents. The log can only faithfully resume or store that agent's identity and its view of the world, but it cannot make that world deterministic. If the agent sent an email, forking back won't unsend it. If some file got changed underneath, the agent won't know about it. But, the log's job is to record what the agent did, what it saw, what changed, and what it needs to continue. It stores that identity, and that's its purpose. And much like that Skyrim character save file, it's not meant to store the entire world. It's just meant to store its view of it.
</details>

---

### 系统红利：从可靠性到多端协同的工程跃迁

一旦你把日志视为最底层的构建基石，一系列极其优秀的系统特性就会自然而然地涌现出来：

* **可靠性**（Reliability）：看看现在的智能体基础设施，如果你的智能体遇到了权限确认提示，而运行该智能体的进程因为某种原因意外挂掉了，当你尝试重新启动它时，权限确认提示已经消失，智能体将陷入暂停或迷失状态。这在生产环境中是绝对不可接受的。当把日志作为智能体本身时，执行器允许是易错的（Fallible Executor）。即使当前的执行进程挂了，新的工作节点也可以随时接管会话，重建状态，它会发现那个权限提示依然完好地保留在它原本所在的位置，智能体不会随着进程的消亡而消亡。
* **可扩展性**（Scalability）：大多数目前的智能体框架都是每个智能体绑定运行一个进程，这意味着智能体被牢牢限制在运行它的特定机器上。如果以日志为主体，这种模式将被彻底颠覆。单个进程可以同时推动成千上万个智能体的运转，因为每个智能体在每一轮迭代中都可以直接从日志中快速重构状态，而不需要与任何单台物理机器或特定工作节点进行强绑定。这使得系统的高可用故障转移（Failover）变得极为简单，横向扩展也仅仅是增加计算节点的工程问题，不需要粘性会话，不需要状态迁移，也没有复杂的协同开销。
* **分叉探索**（Forking）：分叉在以日志为中心的架构中变得非常自然。你不需要被迫沿着单一的线性路径一直走下去，而是可以非常轻松地分叉日志。一个分支可以交由 Claude 运行，另一个分支可以交由 GPT 运行，还有分支可以由你最喜欢的开源模型运行。每个分支都会保留分叉点之前的所有历史，然后各自探索不同的解决策略。
* **多端协同**（Multiplayer）：与他人分享智能体不应该意味着要把聊天记录复制粘贴到 Slack 中。如果日志就是智能体本身，分享就变成了简单地授予该日志历史的访问权限。你的队友可以随时打开会话查看发生了什么，管理者可以在不夺取控制权的情况下进行实时观察，甚至另一个智能体也可以将相同的日志作为上下文进行消费。日志不仅展现了智能体产出了什么，更展现了它是如何一步步推导出来的，这才是智能体的核心价值所在。

<details>
<summary>Original English Source</summary>
So, once you start treating the log as a primitive, a whole bunch of system properties will fall out naturally. So, the first property is reliability. Consider what happens today with Cloud Code. If you're using Cloud Code and your agent reaches a permission prompt and the process dies for whatever reason, and then you resume it, the permission prompt will be gone, and the agent will be paused. And that is unacceptable in production. The permission prompt should stay there. So, this is just a sign of when you architect your agent in a way where the log isn't the agent. When the log is the agent, the executor is allowed to be fallible. A new worker will pick up the session. It'll reconstruct the state, and it'll see that the permission prompt is there right where it was. So, even though the process died, the agent didn't along with it.
The second property is scalability. Most harnesses will run one process per agent, which means that the agent is tied to the machine running it. When the log is the state, you flip that model. One process can now advance thousands of agents. Each of them can reconstruct their state from the log on each turn, and they don't need to be tied to any single machine or worker. This makes failover trivial, and it also makes scaling just a matter of adding more workers. There's no sticky sessions, there's no state migration, and there's no coordination overhead.
Forking becomes a whole lot more natural, too. Instead of having to force like one linear path, you can easily branch the log. One branch can run on Claude, another branch can run on GPT, another can run on your favorite open-source model. Each of the branches can store some of the history up until the fork point, and then they can explore different strategies.
Multiplayer is another property. Sharing an agent with someone should not mean having to copy some transcript and paste it into Slack. If the log is the agent, sharing means you simply grant access to that history, so that somebody else can view it and edit it. A teammate can open the session, they can see what happened, a manager can observe without taking over, and even another agent could consume the same session as context. This is really important because it means that the value is not just what the agent produced, it's also the log, which indicates how it got there.
</details>

---

### 主权之争：避免日志锁定的开放架构

在当前的智能体基础设施中，数据的迁徙（Migration）也是一个极大的痛点。如果智能体的身份、记忆和数据格式被困在特定云服务商的线程、专有格式以及特定的运行时假设中，更换服务商就会变得极其痛苦。但如果日志是智能体，迁移就仅仅成了一个简单的适配器工程问题。不同的模型可能需要不同的日志投影，不同的运行时需要不同的 Schema，但这些都只是纯粹的工程适配，而不是根本的“身份丢失”问题。智能体可以轻松地在 Claude 上启动，在 GPT 上继续，最终在 Gwen（千问）上完成任务，而在这个过程中不会失去自我，因为日志提供了不间断的连续性源泉。

然而，目前绝大多数的智能体平台都把日志看作是无足轻重的副产品。例如，有些工具会将杂乱无章的 JSONL 文件写入本地磁盘，在 SDK 模式下写入操作甚至采用“发射后不管”的策略，一旦写入失败，宝贵的数据就永久丢失了。还有些平台将状态保存在 SQLite 文件中，导致在 GitHub 上存在大量关于状态损坏和数据丢失的 Issue。而在使用持久化对象（Durable Objects）时，往往又会因为不同分片的数据而难以跨会话重建和查询历史。在这些设计里，日志只是系统执行产生的“尾气”或副产品，而不是系统本身。

这引发了关于**所有权**（Ownership）和**锁定**（Lock-in: 用户因迁移成本过高而被迫绑定在特定平台的现象）的关键思考。我们目前面临的最深层次的锁定，其实既不是模型锁定，也不是 API 或工具锁定，而是**日志锁定**（Log Lock-in）。如果一个云端托管平台拥有你的日志，它就事实性地拥有了你的智能体。因为模型是随时可以替换的，运行时是可替换的，机器是可替换的，唯有日志代表了智能体的持续积累。

智能体将是人类运行的最私密、最亲密的技术之一。智能体要真正发挥价值，必须接触你的个人数据、公司的核心机密、你做出的决策和特定的工作流。而日志就是这一切的唯一载体。如果它完全保存在别人的基础设施中，受制于他们的隐私和审计政策，那么他们拥有的就不仅仅是托管服务，而是直接拥有了你的 AI 智能体资产。

这正是 Omnara 正在努力构建的架构。我们将智能体的执行视为围绕日志协同运转的一组组件。工作节点虽然推动循环，但它并不是智能体本身，它只是个无状态的执行器，负责调用模型、获取结果并写回日志。如果涉及工具调用，它会将工具分发到合适的执行环境中，运行完成后将结果再次追加回日志。这一架构能确保你对智能体的会话日志拥有完全的所有权、可读性和控制权。

智能体绝不仅仅是一次简单的模型调用，也不是一个提示词、一个循环或是一个沙箱。**智能体是工作开展过程中所留下的持久历史，而这历史就是日志。** 只有转变这一认知，将日志从系统的副产品提升为系统本身，智能体系统在可靠性、扩展性、协同和所有权上的工程难题才会迎刃而解。

<details>
<summary>Original English Source</summary>
Migration follows the same pattern. If an agent's identity is trapped in provider-specific threads and memories and formats and runtime assumptions, moving providers becomes really painful. But if the log is the agent, migration is just a adapter problem. Different models may want different projections of the log, and different runtimes may need different schemas, but those are all become just engineering problems. They're not identity problems. The agent should then be able to start on Claude, continue on GPT, and finish on Gwen without losing itself. The log serves as a source of continuity.
Here's the problem with a lot of current agent infrastructure. Most agent harnesses today will treat the log as an afterthought. So, Claude code and Codex will write these messy JSONL files to local disk, and even in Claude SDK mode, those writes are fire and forget, which means that if for whatever reason the write fails, the data is gone. Open code's another example, they store state in a SQLite file, and there's a lot of GitHub issues around how there's corrupt state and data loss. Durable objects often end up holding different shards, that makes reconstructing history difficult, it makes querying across sessions difficult. And in all of these scenarios, the log is just a side effect, it's not the system. And that's a problem, because when you treat the log as a first-class citizen, it makes all of these properties become structural. You don't have to bolt them on, which is what it feels like is being done today, they all just fall out.
The next point is incredibly important. This brings us to ownership. The strongest form, now that we've established that the log is the agent, the strongest form of lock-in isn't model lock-in. Models can be swapped. It's not API or tool lock-in either. Those can be wrapped, and those can be adapted. The deepest form of lock-in is actually log lock-in. If a provider owns your log, then the provider effectively owns your agent and long-term the log is the valuable part because the model is replaceable, the runtimes replaceable, the machines are replaceable, the log is the thing that persists.
I have another slide for this because I think it's really worth taking seriously right now. Anthropic has Claude managed agents, Google has Gemini managed agents, every managed provider is going to own more of the stock. They're going to want to. They're going to want to have the hosted agent loop and manage memory and sand boxes and compaction and background agents. They're going to want to own your agents and agents are arguably the most intimate piece of technology you'll ever run. For an agent to be useful, it needs to have your personal data, your company's data, your workflows, your decisions. The log is the record of all of that and if it lives on someone else's infrastructure under their policies and queryable by their systems, they don't just host your agent. They own it.
This is the architecture we have been building towards at Unara. We think of agent execution as the set of components that are coordinated around the log. The worker advances the loop, but the worker is not the agent, it's just the executor and it'll call out to the model provider, it'll get its results, it'll write it back to the log and then if the model provider requires tools, it will go ahead and dispatch those tools to the right execution environment to finish somewhere else. The tools will complete and then those results will get appended back to the log and then a worker, most likely a different one, will then reconstruct the state and it'll continue and this is very important because this is how real agent systems will have to survive real-world failure because workers will crash, machines will restart, sandboxes disappear, tool calls will time out, providers will fail, users connect. There's so many different things that can go wrong. And if an agent is a running process, that's extremely terrifying. But if the agent is the log, it's simply an execution detail.
And this is important because it's the core of what we're building. It's the core of the open-source managed agents platform that we're debuting. Everything will be built around the session log, which we will make sure that you can fully own, fully inspect, it's fully controlled by you. And that's something we believe in strongly. If you're interested, check it out at amnar.com/managed. It may be released by the time this recording comes out or there may still be a waitlist there.
So, in closing, the main thing I want to leave you with is this. An agent is not just a model call, it's not just a prompt or a loop or a sandbox. It's not any of those things. The agent is the durable history of the work being done, and that history is the log. Once you start to see it this way, a whole lot of things fall into place. Reliability, compaction, forking, migration, multiplayer, ownership, scalability, so many things. Because you're going to stop treating the log as this exhaust from the system, and you're going to treat it as the system itself. And that's super important. So, if this was useful, stay tuned to what we're building at Amnara. We're getting ready to open source, as I mentioned, our managed agents platform, and you can join here. The log as the agent is just one of several pieces that we think are going to be making agents a whole lot more powerful in the future. So, thanks for tuning in.
</details>