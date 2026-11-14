---
author: AI Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DxP5aW4VknQ
speaker: AI Engineer
tags:
  - distributed-systems
  - multi-agent-systems
  - consistency-model
  - fault-tolerance
title: 子 Agent 即分布式系统：SAFE 一致性模型与系统设计
summary: 微软首席软件工程师 Girish 提出子 Agent 协作本质上是经典的分布式系统。针对局部失败、脏读、无限制扇出和重试副作用等问题，他提出了 SAFE 一致性模型（Source feeds、At-most-once effects、Fanout budgets、Explicit outcomes），主张在编排器中用代码强校验状态而非仅依赖文本通信。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Girish Konda
companies_orgs:
  - Microsoft
products_models:
  - MCP Peacemaker
media_books: []
status: evergreen
---
### 背景介绍与核心命题：子 Agent 即分布式系统

大家好，我是 Girish，微软的首席软件工程师。工作之余，我为 AI Agent 构建开源工具。其中一个是 MCP Peacemaker，一个保持 MCP 服务器持续运行的受监管桥接工具。在开始之前先做个简短声明：本次演讲中的观点仅代表我自己，不代表我的雇主。

<details>
<summary>Original English</summary>
Hey folks, this is Girish, a principal software engineer at Microsoft. Outside my job, I build open source tools for AI agents. One of them is MCP Peacemaker, a supervised bridge that keeps MCP servers running. Before we start, a small disclosure. The views in this talk are my own and doesn't represent my employer.
</details>

那么，子 Agent 即分布式系统。在过去的一年里，我一直在真正的工程工作中使用 Agent 和子 Agent，包括开发会话、代码审查、即时排障等等。这次演讲讨论的是当一个 Agent 将工作移交给另一个 Agent 时会发生什么。

<details>
<summary>Original English</summary>
So, sub agents or distributed system. Over the past year, I have been using agents and sub agents on real engineering work. Dev sessions, code reviews, instant crashing, what not. This talk is about what happens when one agent hands work to another.
</details>

这里的架构是这样的：编排器将任务拆分，并将各个部分分发给三个不同的子 Agent。它们全部同时运行。它们全都读取相同的共享状态——对话、内存文件、代码仓、工作树、Issue 以及向量数据库。

<details>
<summary>Original English</summary>
So, here's an architecture. The orchestrator splits the task and hands the pieces to three different sub agents. They all run at the same time. They all read from the same shared state, conversation, memory files, repo, working trees, issues, vector stores.
</details>

而且它们不仅是思考，它们还会对真实系统进行工具调用，触及数据库、API、CI 工具和部署流水线。接着它们的结果返回，编排器将它们合并为一个单一的答案。

<details>
<summary>Original English</summary>
And they don't just think, they make tool calls to real systems which touch databases, APIs, CI tools, deployment pipelines. And their results come back and orchestrator merges them into a single answer.
</details>

一个编排器、多个工作节点、共享的可变状态，以及来自并发执行的结果合并——这代表了一个经典的分布式系统。

<details>
<summary>Original English</summary>
An orchestrator workers shared mutable state and results merge from concurrent executions. This represents a classic distributed system.
</details>

几十年来我一直懂得如何对分布式系统进行推理，但目前的整套设置没有任何现成支持。你得到的只是一个接收字符串并返回字符串的函数。

<details>
<summary>Original English</summary>
I have known how to reason with distributed systems for decades, but none of the setup came with it. What you get is a function that takes a string and returns a string.
</details>

### 子 Agent 架构中的经典分布式故障

我们遇到的故障并不是新问题，也不是 AI Agent 特有的。它们是经典的分布式系统故障：

- **部分失败（Partial failure）**：一个中途失败的正常调用本应返回异常错误码，但在子 Agent 场景下，它返回的文本看起来却像是一次成功。
- **脏读（Dirty reads）**：通常我们有隔离级别和版本控制。而在这里，每个工作节点都在读取同一个共享上下文，包括其他工作节点仅仅是推测出来的东西。
- **无限制扇出（Unbounded fanout）**：一个繁忙的服务会通过队列、429 和 503 进行反压。在 Agent 架构中，编排器根本看不到这些，它只在工作节点中发起。
- **重试（Retries）**：在普通的分布式系统中，我们构建幂等性来使重试变得可靠。但在 Agent 中，一个重试的子 Agent 会连同副作用一起把整个任务重新执行一遍。

<details>
<summary>Original English</summary>
Failures we hit are not new, are not specific to AI agents. They are classic distributed system failures. Partial failure, A normal call that fails halfway through. And returns an exception error code. In a sub agent case it returns text that looks like a success. Dirty reads. Normally we have isolations versions. Here every worker reads one shared context including things other worker only guessed. Unbounded fanout. A busy service pushes back [clears throat] with the queues 429s 503s. In agents orchestrator does not see any of this. It just starts in the worker. Retries. Normal distributed systems we build an idempotency to make retries reliable. In agents a retry sub agent runs the whole task again with side effects included.
</details>

针对上述每种情况，我会点明它对应的概念本质。然后我将把它们整合为我提出的一致性模型，并逐步讲解为什么每一部分都在那里。

<details>
<summary>Original English</summary>
For each of these case I'll name the concept it all it is. Then I'll put them together as a consistency [clears throat] model I'm proposing. And walk through why each part is there.
</details>

### 故障模型与拜占庭行为

从故障模型开始，因为其他一切都取决于它。一种温和的情况是崩溃停机（crash down）：一个原本正常运行的进程停止了，并且保持停止状态。一个在此范围内抛出错误的子 Agent 很容易处理。

<details>
<summary>Original English</summary>
Start with the failure model because everything else depends on it. A friendly case is a crash down. A process that was running correctly stops and stays stopped. A sub agent that throws an error in this box it's easy to handle.
</details>

接下来是无应答（no reply）：调用丢失了，或者响应非常迟缓。我们很快会回到这一点。最棘手的情况来自于拜占庭将军问题：一个给出冲突信息的组件。进程作出了应答，但答案是错误的。一个只完成了一半的子 Agent 就很接近这种情况。它不是恶意的，但从外部看表现相同：它没有崩溃，并且回答得很流畅。

<details>
<summary>Original English</summary>
Next, no reply. The call is lost or it's very late. We'll come back to this soon. The hot case is the one from Byzantine generals problem. A component that gives conflicting information. The process answers and the answer is wrong. A half finished sub agent sits close to the box. It is not malicious but from the outside it looks the same. It does not crash. It answers fluently.
</details>

让我们深入看看这个：完成了一半的子 Agent 并没有抛出异常，它返回了看起来很正常的文本，其返回类型与成功时完全相同。

<details>
<summary>Original English</summary>
Let's jump into this. The sub agent that half finished does not raise. It returns normal looking text with the same type as success.
</details>

我在以往的一次演讲中讲过这种情形的一个版本。我们让一个 Agent 处理告警。这里是我当时用的一张插图，展示了得出相同答案的三种不同路径：
1. 第一条路径，它拉取了遥测数据，并与非良性集合进行了比对。它实际完成了工作。
2. 第二条路径，它将其与之前见过的标题进行匹配，并给出了响应。
3. 第三条告警，它什么都没做，只是随便给出了响应。

这三者都被归类为良性，且具有相同的置信度，下游没有任何东西能够将它们区分开来。编排器可以读取结论，但它无法读取结论背后到底做了多少工作。

<details>
<summary>Original English</summary>
I talked about one version of this in one of my talks. We pointed an agent at an Here's an illustration I used there with three different paths which gave the same answer. The first one, it pulled a telemetry and compared with a non-benign set. It actually did the work. The second one, it matched against a title it has seen before and gave the response. The third alert, it didn't do anything. It just had a resonator. All three are categorized as benign with the same level of confidence and nothing down stream can tell these apart. The orchestrator can read the conclusion, it cannot read how much work was behind it.
</details>

### 超时、怀疑与显式状态

现在，调用没有收到回复。编排器派发了工作，随后超时触发了。从这里看，三种情况表现完全一样：
- 子 Agent 仍在工作中；
- 它崩溃了；
- 回复丢失了。

这是一个硬性限制，而不是工具缺陷。1985 年的 FLP 论文表明，在即使只有一个故障进程的异步系统中，共识可能无法达成。Chandra 和 Toueg 在 1996 年给出的答案是可能出错的故障检测器（failure detectors）：它们只是怀疑，并不是确知。

<details>
<summary>Original English</summary>
Now, the call gets no reply. The orchestrator sent work and the timeout fired. From here, three worlds look the same. The sub agent is still working. It crashed and the reply was lost. It's a hard limit, not a tooling gap. The FLP paper from 1985 showed that in an asynchronous system with even one faulty process, agreement can fail to finish. Chandra and Toueg answered in 1996 was failure detectors that can make mistakes. They suspect, they do not know.
</details>

在我自己的开源项目 MCP Peacemaker 监管桥接中，我遇到了这两个方向的问题：
- 有一个在首次运行时需要自我下载的服务器，它触发了 30 秒的调用超时，看起来像是坏掉了。它只是慢，并没有挂掉。我们通过为初始化操作提供独立的超时时间修复了这个问题。
- 另一种反向情况是，服务器在调用期间崩溃了。随后调用超时，这个超时覆盖了解释崩溃原因的退出码。我们通过仅在它处于存活状态时才记录超时来修复了该问题。

所以，超时只是一种怀疑。应将其记录为未知（unknown），并保留真正的原因。

<details>
<summary>Original English</summary>
I hit both directions in my own open source project MCP pacemaker supervised bridge. A server whose first run downloads itself hit the 30 second call timeout and looked broken. It was slow, not dead. We fixed it by giving initialize its own timeout. Now the other way, the server crashed during a call. The call then timed out and the timeout overrode the exit code that explained the crash. We We it by recording the time out only when it was alive. So, timeout is a suspicion. Record it as unknown and keep the real cause.
</details>

现在，我们要将失败变成一种明确的值（make failure a value）。我们来看这张图示：一个子 Agent 应该返回状态、它做了什么、它没做什么、证据以及任何产生的副作用。在这里，序列化结构体应该是一个正常的应答形式。

<details>
<summary>Original English</summary>
And now make failure a value. Let's take this illustration. A sub agent written the status, what it did, what it did not do, the evidence and any side effects. Marshall is a normal answer here.
</details>

现有协议中其实已经为此预留了位置：
- 在任务模型中，一个任务可以以已完成（completed）、失败（failed）、已取消（canceled）或已拒绝（rejected）结束，或者暂停并请求输入。
- 在 MCP 中，工具调用结果可以声明 `isError: true`。

然而，一个子 Agent 仍然可以在其文本内容表述着其他事情的同时声称 `completed`。如果一个循环仅仅读取文本，它就无法察觉这种差异。

<details>
<summary>Original English</summary>
The protocols already have a slot for this. In A task can end as completed, failed, canceled or rejected or stop and ask for input. In MCP a tool result can say is error true. But a sub agent can still say completed while its text says something else. And a loop that only reads the text now sees the difference.
</details>

另一种区分：检查了某个条件并得出否定结果，与根本无法执行检查完全是两码事。我关于评估状态的个人草案中就讨论了这一点。将这两者混为一谈，会改变后续的处理方式、付费结算对象以及事后的审计结论。

<details>
<summary>Original English</summary>
Another split. Checking a condition and getting no is a different fact from not being able to check at all. My own individual draft on evaluation states talks about this. Collapse the two and you change what gets and who gets paid and what the audit says later.
</details>

### 脏读与 Quorum 的误区

接下来是脏读。让我们看看我某次演讲中的虚构示例：
- 一个子 Agent 在执行过程中，向共享上下文写入“错误率下降了 80%”。它并没有实际测量过该数据，而是推断出来的。
- 现在另外两个子 Agent 从同一个共享上下文中读取。第二个子 Agent 拾取了同一句话并写入产物；第三个 Agent 也拾取了它，并将其作为继续执行的依据。
- 编排器将这三个产物合并。三个产物意见一致。但实际上，这是一句未经证实的话被读了三次。

<details>
<summary>Original English</summary>
Next, dirty reads. Let's take this made up example from one of my talk. A sub agent destroys it writes into a shared context saying that error rate fell by 80 %. It did not measure that, it inferred it. Now two other sub agents read from the same shared context. The second sub agent writes the then picks the same sentence up. The third agent writes the and uses it as a reason to proceed. The orchestrator merges all the all these three. Three artifacts agree. It is once unsupported sentence read three different times.
</details>

1995 年对 SQL 隔离级别的批判性论文中将脏读定义为：你在写入者提交或回滚之前读取了某个值。而在共享上下文中，一个推测在被写入的瞬间就是可读的，没有任何东西将其标记为未核实。

<details>
<summary>Original English</summary>
The 1995 critique of SQL isolation levels define a dirty read as you read a value before the writer commits or rolls back. The shared context a guess is readable the moment it is written nothing marks it as unchecked.
</details>

通常的修正方法是询问三个子 Agent 并获得多数派裁决（quorum）。Quorum 之所以有效是有具体原因的：在 1979 年的加权投票算法中，读 Quorum 加上写 Quorum 大于总节点数，因此每次读取必然与最新的写入重叠。这种重叠是一种保证。

而在子 Agent 的情况下，读取同一共享上下文的三个子 Agent 并不能给你这种保证。它们不是独立的副本，它们读取的是同一个推测。它们的共识只是同一个信息源被计算了三次。

<details>
<summary>Original English</summary>
The regular fix to is to ask three sub agents and get a quorum. Quorums do work for a specific reason. In waited voting from 1979 the read quorum plus write quorum is greater than total. So every read overlaps the latest write. The overlap is a guarantee. In sub agent's case the three sub agents that read the same shared context does not give you that. They are not independent copies. They read the same guess. Their agreement is one source counted three different times.
</details>

### SAFE 一致性模型定义

让我们来选择一种一致性模型。在数据库中我们有一系列模型：
- **线性一致性（Linearizable）**：每个操作看起来都在真实的物理时间序列中的单一点发生。
- **顺序一致性（Sequential）**：存在一个遵循每个进程自身顺序的全局全序。
- **因果一致性（Causal）**：存在因果关联的操作在所有地方都以相同的顺序显现。
- **会话保证（Session guarantees）**：向单个客户端作出的承诺，例如“读己之写”（read-your-writes）和“单调读”（monotonic reads）。
- **最终一致性（Eventual）**：如果没有新的更新，读取最终会返回最新的值。

共享上下文没有提供上述任何一种保证，它根本没有任何明示的保证。而且你并不需要最顶层的一致性模型——最强的一致性模型在网络分区时无法保持可用性。因果一致性和会话保证则可以保持可用，只要每个客户端固定在单个接入点。对于子 Agent 来说，那个接入点就是编排器。

<details>
<summary>Original English</summary>
Let's pick a consistency model. In databases we have a for this. Linearizable every operation appears to happen at one point in real time order. Sequential one total order that respects each process own order. Causal operations that are causally related appear in the same order everywhere. Session guarantees they are promises to one client like read your writes and monotonic reads. Eventual if no new updates are made reads eventually return the last value. A shared context gives you none of these. There's no stated guarantee at all. And you don't need the top consistency models. The strongest models cannot stay available when the network splits. Causal and session guarantees can as long as each clients stick to one place. For sub agents that place is orchestrated.
</details>

因此，这是我用于子 Agent 的一致性模型。我称之为 **SAFE** 移交（safe handoff）：

- **S (Source feeds，数据源切片)**：工作节点传递的每个事实都带有其来源、版本、截止时间戳及修订版本。决策只读取新鲜的源事实。
- **A (At-most-once effects，至多一次副作用)**：每次写入都具有唯一身份标识，并且针对该确切动作仅有单次用户审批。执行结果通过回读获得，绝不重放。
- **F (Fanout budgets，扇出预算)**：每个下游都有门控机制和有界等待时间，拒绝请求直接计为失败。
- **E (Explicit outcomes，显式结果)**：每次移交都以具名状态结束，超时被归为未知状态并保留其原本原因。

<details>
<summary>Original English</summary>
So, here's the consistency model I use for sub-agents. I call it safe handoff. Yes stands for source feeds. Every fact a worker hands on carries its source version as of time and revision. And decisions read only fresh source facts. A at most once effects. Every write has identity and a single user approval for that exact action. An outcome [clears throat] is read back never replayed. F fanout budgets. Each downstream gets a gate and a bounded weight. And refusal counts as a failure. E stands for explicit outcomes. Every handoff ends in a named state. And the timeout is unknown with its cost kept.
</details>

这是我用于自己的子 Agent 的一致性模型。它并非通用普适的模型，而是基于我自己的公开工作成果——部分源于我的 MCP Peacemaker 桥接项目，部分基于我的其他演讲以及我起草的互联网草案。

<details>
<summary>Original English</summary>
This consistency model is the one I use for my own sub-agents. It's not a universal model. It's based off my own public work. Some of it is in my FCP pacemaker bridge and some are based on my other talks and my own internet draft.
</details>

### SAFE 深度拆解：S 与 A

现在让我们看看每个字母背后的具体机制。

**S - Source feeds（数据源切片）**：这是针对脏读的解决方案，防止一个工作节点的推测变成另一个工作节点认定的事实。

有效的方法是将每个事实视为一条记录（record），而不是一句文本。Lamport 1978 年的论文定义了一个事件何时发生于另一个事件之前。事实的出处（provenance）就是那条记录：它是从哪里读取的，以及在何时读取的。

以这个虚构示例为例，记录明确指明：
- 主张及其修订版本；
- 数据源及其版本；
- 作用域；
- 以及三个不同的时间点：数据有效截止时间、我们读取它的时间、以及我们使用它的时间。

新鲜度（freshness）在事实被使用时进行校验。在此图示中，数据截止至 9:05，我们在 9:06 读取，在 9:07 作出决策。在本例中我们选定了 5 分钟的有效限度，因此 9:07 作出的决策是有效的。

到了 9:15，第二个决策到来。因为我们设定的新鲜度限度是 5 分钟，此时记录已失效，我们将其拒绝，并声明下一个决策需要重新读取。这就是如何将观察（observation）与推断（inference）区分开来：观察具备源和读取时间，而推断则没有。

<details>
<summary>Original English</summary>
Now let's see what's behind each letter. S source feeds. It's the answer to let he reads where one worker's guess becomes another worker's fact. What helps is to treat every fact as a record, not a sentence. Lamport's 1978 paper defined when one event happened before another. The facts provenance is that record. What it was read from and when. Let's take this made-up example. The record names the claim and its revision. The source and its version. The scope and three different times, when the data was current, when we read it, and when we used it. Freshness is checked with the fact is used. In this illustration, the data ends at 9 05. We read it at 9 06 and we decided at 9 07. In this case, we picked a 5 minute limit. So the data decision at 9 07 it's fine. Now at 9 15 the second decision came in. Because our freshness limit is 5 this is still record. We reject it. And we say that the next decision needs another read. This is how you separate an observation from an inference. An observation has a source and a read time. An inference has none.
</details>

**A - At-most-once effects（至多一次副作用）**：这关乎重试机制。

这是我关于 MCP Peacemaker 桥接文章中的插图：编排器委托任务，子 Agent 调用一个执行真正写入操作的工具（例如创建一个 PR），随后回复丢失了。编排器只知道一件事：结果是未知的。于是它重试整个任务，写入操作再次发生。

这是个经典问题。在 1984 年关于 RPC 的论文中提到：如果调用正常返回，说明过程精确执行了一次；如果收到异常，说明它可能执行了一次，也可能根本没有执行，而你无从得知究竟是哪一种。

因此，你必须选择投递语义：
- **At-most-once（至多一次）**：不重试，并接受操作可能丢失的事实；
- **At-least-once（至少一次）**：进行重试，并接受可能产生重复；
- **Exactly-once（精确一次）**：发生了至少一次，且我们有机制进行去重。

在 MCP 中，幂等提示（idempotent hint）仅仅是一个提示，且默认为 `false`。如果你需要它，必须自行构建。

<details>
<summary>Original English</summary>
A at most effects is about retries. This is an illustration from my article about NCP pacemaker bridge. The orchestrator delegates a task. The sub agent calls a tool which does a real write like creating a PR. The reply is lost. The orchestrator knows one thing the outcomes are unknown. So it retries the whole task. The write happens again. This is a classic problem. In 1984 our PC paper it says that if the call returns [snorts] the procedure ran precisely once. If you get an exception it ran once or not at all. And you are not told which. So you pick a delivery semantic at most once. Don't retry and accept the fact that it may be lost. At least once retry and the duplicates of possibly. Exactly once. It happened at least once and this is a way we can deduplicate. Maybe by using an In MCP, idempotent hint is only a hint and it defaults to false. If you need it, you build it.
</details>

这里是我桥接工具中处理该问题的一个简明设计：当客户端重启后重新连接时，桥接工具会针对一个全新的服务器重放客户端记录的初始化过程。这是安全的，它只是一次握手，并不会恢复工具的状态。它绝不会重放的是处于不确定状态的工具调用。当一个共享服务器被回收时，桥接工具会对其进行清空排空（drain）；在截止期限前仍未得到答复的调用将以“可能已被排除”的状态失败。这种状态是诚实的，它告诉调用者需要去核对确认。

起作用的机制是为每个副作用赋予一个身份标识。审批绑定具体确切的动作，且仅使用一次。调用之后，通过该身份标识进行回读。“已提交”不等于“已确认”，“已确认”意味着你切实验证观察到了该效果。

<details>
<summary>Original English</summary>
Here's a small design from my bridge on how I handle it. When a client comes back after a restart, the bridge replace the client's record initialized against a fresh server. That's safe. It's just a handshake and it does not restore tool state. What it never replace is an uncertain tool call. When a shared server is recycled, the bridge drains it and calls still unanswered at the deadline fail as potentially excluded. That status is honest. It tells the caller to go and check. What helped us giving every side effect an identity. Approval binds the exact action. It's only used once. After the call, read back by that identity. Submitted is not confirmed. Confirmed means you observe the effect.
</details>

A 部分的最后一个环节，出现在任务暂停与恢复的场景中。租约（lease）是带有超时时限的锁。Martin Kleppmann 关于分布式锁的文章指出了这个问题：一个客户端在持有锁的过程中发生了停顿暂停，租约过期，其他人接管；随后第一个客户端苏醒过来并写入了数据。

他提出的解决方案是防护令牌（fencing token）：一个每次锁被授予时都会递增的数字。存储层记住其所见过的最大令牌，并拒绝任何带有旧令牌的写入。

子 Agent 经常暂停和恢复。正如我在另一次演讲中所表达的：**恢复上下文，不要恢复副作用**。因此，要把审批当作防护令牌来对待：一个动作，单次使用。在门控处进行检查，而不是记忆在提示词或对话历史中。我的桥接工具修复了同类 Bug：一个过期的退出事件或被延迟的恢复操作，再也不能错误地移除或拉回一个替代会话。

<details>
<summary>Original English</summary>
The last part of A, it shows up when work passes and resumes. A lease is a lock with a timeout. Martin Kleppmann's post about distributed locking shows this problem. A client passes while holding it. The lease expires. Someone else takes over. In the first client wakes up and writes an email. The fix he proposes a fencing token. A number that goes up every time the lock is granted. The storage remembers the his token it has seen and rejects any write with a older one. Sub agents pause and resume all the time. My other talk, as I put it, restore context, not side effects. So, treat an approval like a fencing token. One action, one use. Checked at the gate, not remembered in the prompt or conversation. My bridge fixed the same class of bug. A stale exit or a deleted resume can no longer remove or bring back a replacement session.
</details>

### SAFE 深度拆解：F 与 E

**F - Fanout budgets（扇出预算）**：针对的是无限制扇出，这涉及流控（flow control）及其缺失。

在我的 MCP 桥接工具对冷启动引入限制之前，我就遇到过这个问题：多个会话同时通过 `npx` 启动它们的服务，它们共享同一个包缓存，结果每一个都因为 npm 的 lock 冲突错误而失败。任何单个请求本身都没有错，失败完全是由并发本身造成的。

而且当下游确实施加反压时，它可能仅仅以纯文本形式返回。这是 MCP 规范中关于工具执行错误的自带示例：将速率限制（rate limit）表述为一句话。模型读到了这句话，但编排器代码可能根本注意不到，接着下一个工作节点就继续盲目发起了调用。

<details>
<summary>Original English</summary>
F fanout budgets is about unbounded fanout. This flow control or the lack of it. I hit this issue in my own MCP bridge before it had a limit on cold starts. Many sessions start their service at the same time through NPX. They share one package cache. Every one of them failed with NPM's lock compromise error. Nothing in any single request was wrong. The failure was the concurrency itself. And when a downstream does push back, it can arrive as plain text. This is MCP specs own example of a tool execution error. A rate limit as one sentence. The model reads a sentence. The orchestrator code may never look. The next worker starts an EP.
</details>

因此，我在桥接工具中引入了配额预算。使用包管理器的冷启动必须通过门控，默认每次最多允许并发启动两个，其他人排队等待。等待时间被限定在 15 秒以内；超过该时限，启动将在没有门控的情况下直接进行。我记录了为何做出这一权衡的文档：缓存损坏是一个风险，而悬挂停滞的客户端请求则是确定性的失败。这是一个有意做出并记录在案的可用性权衡。

此外我还给会话建立了上限。达到上限时，新会话最多等待 10 秒，随后被拒绝。这种拒绝此时会被明确计入失败指标。

另一个缺陷是：容量必须在同步启动之前预留，而不是之后。否则排队的启动会超额预订上限，导致“先检查后执行”（check-then-act）的竞态条件。对于子 Agent，务必给编排器为每个下游分配一个具体数值指标、一个有界等待时限，以及一个它可观测到的拒绝信号。

<details>
<summary>Original English</summary>
So, I introduced a quota budget in my bridge. Cold starts that use a package manager go through a gate two at a time by default. Everyone else waits. And the wait is bounded at 15 seconds. Past that, the start goes ahead without a gate. And I documented why a corrupted cache is a risk while a hung client request is certainty. That is a choice for availability made on purpose and written down. And I also built a cap on sessions. At the cap, a new a new session waits up to 10 seconds and then it's refused. That refusal now counts as a failure depth. Another bug. Capacity has to be reserved before the synchronous start, not after. Otherwise, queued starts overbook the cap. That is a check, then act race. For sub agents, give the orchestrator a number per downstream, a bounded weight, and a refusal it can see.
</details>

**E - Explicit outcomes（显式结果）**：每次移交都必须以具名状态结束（例如 stale 或 unknown），而不仅仅是返回文本。

最后一点是谁来判定该状态：应像对待来自公网的请求体一样，将 Agent 的输出视为**不可信输入（untrusted input）**。编排器通过代码拥有校验权：
- 结果是否符合 Schema？
- 证据是否存在？是否足够新鲜？
- 重新计算这些数字时是否仍然成立？

如果你的检查失败，该步骤将返回带有明确原因的拒绝，而不是把文本透传过去并在下方附带一段警告段落。如果同一个模型可以跳过检查并单方面宣布其通过，那你拥有的只是一个请求，而不是一条真正的系统边界。

这里是另一次演讲中的虚构示例：一个子 Agent 声称错误率下降了。此前是 1000 次请求中有 10 次错误，之后是 600 次请求中有 6 次错误。错误数从 10 降到了 6，它便据此声称错误率下降了。但当我们重新计算比率时，两者都是 1%。我们重新计算后，该声明被系统拒绝。

有依据支持的答案是没问题的；明确将决策移交给人也是没问题的；但自信的胡乱推测不行。

<details>
<summary>Original English</summary>
Now, E, the explicit outcomes. Every handoff ends in a named state, like stale or unknown, not just text. The last piece is who decided that state. Treats an agent output as untrusted input, the same way you treat a request body from the internet. The orchestrator owns the checks in code. Does the result match the schema? Is the evidence there? Is it fresh enough? Do the numbers hold when you recompute them? If your check fails, the step returns a refusal with a reason. It does not pass the text along with a warning paragraph underneath. If the same model can skip a check and declare it passed, you have a request, not a boundary. Here's a made-up example from another talk. A sub agent says the error rate fell. Before, it was 10 errors in 1,000 requests. After, it was 6 errors in 600 requests. It went from 10 to 6, and it claimed that our rate fell. But when we computed the rate, it's both 1 percent. We recomputed it, and then the claim is refused. A supported answer is fine. A deliberate handoff to a person is fine. A confident guess, it's not.
</details>

### 模型边界、权衡与核心总结

关于局限性：因为一致性模型只有在你知道其适用边界时才真正有用。以下是 SAFE 模型**不**做的事情：
- 它并不能保证事实是真实的。一个源事实是可检验的，但不等于一定是正确的。
- 它并不提供绝对的精确一次投递。丢失的应答在被回读之前一直保持未知状态。
- 它不会自动进行任何回滚。撤销部分任务是一个需要你自行设计的补偿步骤，正如 1987 年关于 Sagas 的论文所阐述的那样。
- 最后，在工作节点之间不存在全局顺序，只有针对每个事实的局部因果顺序。

<details>
<summary>Original English</summary>
So, limitations. Because the consistency model is only useful when you know where we should stop. So, here's what safe model does not do. It does not make facts true. A source fact is checkable, not correct. It does not give you exactly one delivery. A lost reply stays unknown until you read it back. It does not roll anything back. Undoing a partial task is a compensation step you design. Like this August paper from 1987. And finally, there's no global order across workers. Only causal order per fact.
</details>

而且这一切都是有代价的。CAP 定理指出，当网络发生分区时，你必须在可用性与一致性之间做出权衡。我的桥接工具在冷启动时特意选择了可用性；而对于写操作，SAFE 选择了一致性优先于可用性——它宁可拒绝，也不进行推测猜测。

PACELC 定理进一步指出，即使在没有故障的情况下，你也是在用延迟换取一致性：每次新鲜度检查都是一次额外的读取操作，而每次拒绝都需要进行有序处理。

那么它在哪些场景下不适用？
- 如果一个子 Agent 仅仅是起草文本，并在任何后续操作发生之前由人工进行审核，那么这些机制中的大部分都是额外的系统开销。
- 它还假设存在一个单一的编排器。如果你有多个编排器，这个模型并不契合；没有单一接入点的对等 Agent（Peer agents）需要其他的架构机制。

这是我用于触碰真实生产系统的自身 Agent 的一致性模型，它并不是普遍通用的。

<details>
<summary>Original English</summary>
And it has a price. CAP theorem says that when the network splits, you trade off availability against consistency. My bridge chose availability for cold starts on purpose. For writes, safe picks consistency over availability. It refuses rather than guesses. PAC LACK adds that even without failures, you trade latency for consistency. Every freshness check is another read. And and every refusal needs an order. So, where it does not fit? If a sub agent only drafts text that a person reads before anything happens, most of this is is overhead. It also assumes that there's one single orchestrator. If you have more, this does not fit. Peer agents with no single place to stick to need something else. This is the consistency model I use for my own agents that touch actual real production systems. It's not universal.
</details>

总结一下，这里有三个核心要点：
1. **将向子 Agent 的每次移交都视作网络调用**：它可能中途失败，可能响应缓慢，也可能返回两次。
2. **返回明确状态，而不仅仅是文本**：如果结果不能明确表示局部（partial）、失效（stale）或未知（unknown），编排器就会默认将其视作已完成（done）。
3. **从 SAFE 一致性模型起步，并在代码中强制执行**：保留适用的部分，修改不适用的部分。

我们早就知道如何构建分布式系统，我们只是需要意识到我们现在正在构建的正是分布式系统。

演讲引用的部分资料如下：左侧是我自己的工作、开源项目、文章、草案和演讲；右侧是背后的规范、标准以及一系列经典学术论文。谢谢大家。

<details>
<summary>Original English</summary>
So, wrapping up, here's three key takeaways. Treat every handoff to a sub agent as a network call. It can fail halfway. It can be slow and it can come back twice. Return a status, not just text. If the result cannot say partial, stale, or unknown, the orchestrator will read it as done. And start with our safe consistency model. And enforce it in code. Keep what fits and change what does not. We already know how to build distributed systems. We just have to notice that we are building one. So these are some of the sources behind this talk. On the left side it's my own work, my open source projects, my articles and drafts and my talks. On right side specs and standards and bunch of papers behind each concept. Thank you.
</details>