---
author: AI Engineer
date: '2026-06-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=APh1Vx0oLmQ
speaker: AI Engineer
tags:
  - agentic-infrastructure
  - system-reliability
  - distributed-systems
  - agentic-control-plane
title: 确定性基建与非确定性智能：重构AI Agent的生产力屏障
summary: Meta技术主管Nishant Gupta指出，AI Agent落地生产环境的瓶颈已从模型智能转向系统可靠性。本文系统阐述了非确定性AI模型与确定性云基础设施之间的“伟大失配”，并提出了通过提议-执行分离、Agent控制面、多维观测性及共享内存一致性等分布式系统工程方法，构建高可靠Agent系统的核心架构原则。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Meta
products_models: []
media_books: []
status: evergreen
---
### 战略转移：从智能到可靠性

近年来，关于人工智能的大部分讨论都集中在模型层面上——更庞大的模型、更多的参数以及更强大的推理能力。然而，随着组织开始从简单的**聊天机器人**（Chatbot: 一种通过自然语言交互回答问题的基础 AI 应用）转向**自主Agent**（Autonomous Agent: 能够独立规划并调用外部工具执行复杂任务的智能体系统），一个截然不同的工程挑战悄然浮现：核心瓶颈不再是智能本身，而是**可靠性**（Reliability: 系统在规定时间内及规定条件下无故障运行的能力）。

在Meta及整个行业中，我们正目睹Agent超越单纯的问答，开始进行自主规划、调用外部工具、协调复杂工作流，并做出直接影响生产系统的决策。这些自主系统在本质上是概率性的，然而，支撑它们的底层基础设施却绝不允许是概率性的，必须是确定性的。

现代云基础设施是围绕一套经典假设演进出来的，即请求通常是短生命周期的、服务是确定性的、执行路径是清晰可知的，且故障边界是受控的。然而，自主AI Agent几乎颠覆了这之中的每一条假设。它们是有状态的、长周期运行的，并且能够动态做出决策。这意味着，即使输入完全相同，它们也可能会执行完全不同的工作流。这就是所谓的**伟大失配**（The Great Mismatch）：我们正试图在为确定性工作流设计的传统基础设施上，运行高度非确定性的自主系统。

从技术演示走向生产环境，需要实现最关键的思想转变。AI演示通常展示的是其**能力**，例如能否解决某个具体问题、使用某个工具或完成某项工作流；而生产系统关注的则是**可靠性**，即系统能否稳定重复执行1万次、10万次乃至100万次，能否在失败中自我恢复，能否安全运行，并保持在可接受的成本、延迟和预期产出范围之内。因此，绝大多数工程精力已经从模型层向下转移到了编排、监控、安全评估以及恢复系统之中。

<details>
<summary>Original English</summary>

Hey everyone. My name is Nishant Gupta. I'm a software engineering tech lead at Meta, working on building the training and inference infrastructure. And today, we're going to be talking about building deterministic infrastructure for non-deterministic AI agents.

So, most of the conversations around AI over the last few years has been focused on models. Bigger models, more parameters, better reasoning. But as organizations move from chatbots to autonomous agents, a different problem emerges. The challenge is no longer in intelligence. The challenge is reliability.

At Meta and across the industry, we are seeing agents move beyond answering questions and beginning to plan, call tool calls, coordinate workflows, and make decisions that affect production systems. These systems are fundamentally probabilistic. Infrastructure is not allowed to be. Today, I want to discuss this topic in more detail.

The modern cloud infrastructure evolved around a set of assumptions. A request -- most of the requests are short-lived. Services are deterministic, more or less. Execution paths are known. Failures are bounded. However, autonomous AI agents violate nearly every one of those assumptions. They're stateful. They're long-running. They make decisions dynamically. They may execute different workflows for same inputs. This is what I call the great mismatch. We're trying to run autonomous systems on infrastructure that was designed for deterministic workflows.

This is probably the most important mindshift. Most AI demos showcase capability. But can it solve a problem? Can it use a tool? Can it complete a workflow? Production systems have a different objective. Can it do it reliably? Can it do it 10,000 times, 100,000 times, million times? Can it recover from failures? Can it operate safely? Can it do it at an acceptable cost with an acceptable latency? With an acceptable outcome? The majority of the engineering effort moves below the model layer into orchestration, monitoring, safety evaluation, and recovery systems.

</details>

### 级联失效：规避重试放大风险

当人们听到人工智能系统的失效时，直觉上往往会联想到**幻觉**（Hallucinations: AI 模型生成看似合理但与事实不符的错误信息的现象）。但在实际的生产实践中，幻觉往往是危害性最小、也最乏味的失效模式。相反，我们频繁遭遇的是**基础设施层面的崩溃**：递归推理死循环、工作流死锁、重试放大效应、上下文污染、内存毒化以及成本爆炸。通常是模型首先犯了一个微小的错误，但由于缺乏防护，底层基础设施将这一微小错误无限放大，最终酿成严重的系统停机事故。

分布式系统工程师能够轻易识别出一种典型的失效模式：Agent错误地调用了某个外部工具，工具随即返回错误响应。此时，Agent并没有成功恢复，而是生成了一个稍微有所不同、但同样无效的新请求。如此周而复始，每一次**重试**都消耗着更多的算力，推理深度不断增加，GPU消耗急剧攀升，最终导致计算资源的指数级爆发。原本只是一个微不足道的API调用错误，最终却演变成了一场严重的算力耗尽事故。这就是为什么**失控的重试放大**是当前Agent系统面临的最大架构风险之一。

<details>
<summary>Original English</summary>

When people hear AI failures, they immediately think hallucinations. In reality, hallucinations are often the least interesting failure mode. What we see instead are infrastructure failures, recursive reasoning loops, workflow deadlocks, retry amplification, context corruption, memory poisoning, cost explosions. The model makes a mistake, but however, the infrastructure turns that mistake into an outage. That's the real challenge.

So, as this slide shows a pattern that distributed system engineers will probably recognize immediately, an agent calls a tool incorrectly, the tool returns an error. Instead of recovering, the agent generates a slightly different, but still invalid request. The cycle repeats. Each retry consumes more compute. Reasoning depth increases, GPU consumption rises, eventually you get exponential resource growth. What started as a minor API error became a compute incident. This is why uncontrolled retries are one of the biggest risks in agentic systems.

</details>

### 架构解耦：建议与决策分离

为了防范级联失效，我强烈推荐的首要架构原则是：**决不允许模型直接控制生产系统**。模型应当只负责生成**提议**，而由基础设施层负责验证，通过**策略引擎**进行准入审批，并由**执行网关**强制执行。简而言之，模型只有建议权，真正的决策和执行权属于基础设施平台。这种清晰的职责分离，使我们能够在底层模型依然具有概率性和非确定性的情况下，构建出具备高确定性与高可靠性的企业级系统。

正如历史上容器技术的普及催生了Kubernetes，微服务架构的兴起孕育了服务网格（Service Mesh），AI Agent的演进也正在推动一个全新技术栈的诞生——**Agent控制面**（Agentic Control Plane: 负责调度、监控、路由与政策执行的智能体系统控制层）。这一全新的基础架构层主要承担以下核心职责：
* **工作调度与负载均衡**
* **共享内存协调与一致性维护**
* **安全策略的强制执行**
* **实时的安全评估与监控**

我们可以将其视为专门面向自主AI的**操作系统**。能够率先在企业内部建立并完善这一核心控制面层的组织，将获得难以逾越的系统级竞争优势。

<details>
<summary>Original English</summary>

This is the architecture principle I recommend most strongly. Never let the model directly control production systems. The model should generate proposals, infrastructure validates them, policy engine approves them, execution gateway enforces them. The model just suggests, the platform decides. This separation allows us to build reliable systems even when the underlying model remains probabilistic.

As we know, containers gave rise to Kubernetes, microservices created service meshes. AI agents are creating something new, an agentic control plane. This layer becomes responsible for scheduling, memory coordination, policy enforcement, evaluation, monitoring, workload routing, which is very important. And think of it as an operating system for autonomous AI. The organizations that build this layer will have significantly more competitive advantages.

</details>

### 状态一致：攻克多维追踪难题

传统的系统日志仅能告诉我们“发生了什么”，而Agent系统的调试则要求我们必须彻底理解“为什么发生”。为了实现这一目标，我们必须引入**多维追踪**，用以精确捕获Agent的规划决策、每一次具体的工具调用、内存检索记录以及状态机迁移轨迹。在排查自主工作流的故障时，理解Agent的推理链条和决策演变路径，往往比获取最终输出结果更为关键。若缺乏此类多维观测手段，生产环境下的系统调试与故障排查将变得寸步难行。

与此同时，**内存机制**是Agent架构中最容易被低估的系统级挑战。一旦引入多个Agent共享状态的架构，经典的分布式系统难题便会接踵而至：脏读、更新冲突、上下文漂移以及状态视图不一致等。当内存检索本身也是基于概率且依赖检索（如基于向量数据库的RAG检索）时，这一挑战将变得更加严峻。在多Agent协同的故障案例中，有很大一部分表面上看起来是模型的逻辑推理失败，但其实质是底层数据的**一致性失效**。

<details>
<summary>Original English</summary>

So, traditional logs tell us what happened. Agentic systems require understanding why it happened. We need traces to capture planning decisions, tool calls, memory lookups, state transitions. When debugging an autonomous workflow, understanding the chain of decisions and reasoning is often more important than the final output. Observability becomes multi-dimensional. Without it, production debugging becomes nearly impossible.

So, as you can see, memory is one of the most underestimated challenges in agentic architectures. Once multiple agents share state, familiar distributed system issues appear. Stale reads, conflicting updates, context drifts, inconsistent views. The challenge becomes even harder when memory itself may be probabilistic and retrieval-based. Many multi-agent failures are actually consistency failures masquerading as reasoning failures.

</details>

### 纵深防御：安全防护与资源调度

构建Agent系统的安全防线绝不能寄希望于单一的防护组件，而必须采用**纵深防御**（Defense in Depth: 一种通过多层安全控制机制来防范单点失效的防御策略）原则。这一成熟的经典安全理念完全适用于自主AI系统，其安全层级应当是立体且多维的：
* **提示词级控制**
* **精细化工具权限管控**
* **合规与策略验证**
* **关键节点的审核机制**
* **事后审计系统**

许多人倾向于将**人机协同**（Human-in-the-loop: 在自动化流程的关键决策节点引入人类审核与校准的机制）视为一种过渡期的临时妥协，这显然是对AI发展趋势的误判。最成功的商用系统在可预见的未来依然会维持人类的监督。在此模式下，人类的角色将转变为**异常处理器**：人类负责审查模型无法确定的模糊边界情况，处理非常规的业务场景，并向系统持续回传宝贵的校准信号。我们构建Agent的目标并不是彻底消除人工干预，而是要将宝贵的人力注意力分配到能够创造最大价值的决策链条上。

除了安全问题，底层基建的另一项重大转变在于，AI Agent的工作负载特征正在高度逼近**集群调度问题**。Agent的算力需求呈现出极强的爆发性，其推理深度和运行周期可能从以往的毫秒级拉长至数分钟，且不同任务之间的资源配额差异极大。因此，GPU算力效率、智能化的工作负载排布、弹性的容量管理以及高效调度成为了决定成败的核心指标。在线推理不再只是一个单纯的算法模型优化问题，而是彻底变成了一个系统级的**资源编排**（Resource Orchestration: 对计算、存储及GPU等底层硬件资源进行调度和效率优化的系统）挑战。

<details>
<summary>Original English</summary>

So, safety cannot be a single component. It must be layered. Prompt level controls, tool permissions, policy validations, human approvals, audit systems. Each of these layers catches a different class of failures. Defense in depth is a well-understood security principle. It applies equally well to autonomous AI systems.

Many people frame human involvement as temporarily -- temporary necessity. I don't think that's correct. The most successful systems are likely to remain human supervised. Humans become exception handlers. They review ambiguous situations. They handle normal scenarios. They provide calibration signals. The goal is not to remove humans. The goal is allocating human attention where it provides the maximum value.

So, one of the biggest infrastructure shifts is that AI workloads increasingly resemble cluster scheduling problems. Demand is bursting. Reasoning depth is... and Workflows may run for minutes instead of milliseconds. Resource requirements vary dramatically. As a result, GPU efficiency, workload placement, elastic capacity management, and scheduling becomes critical. Inference is no longer just a model problem. It becomes a resource orchestration problem.

</details>

### 经典映射：下一代基建的决战

令人欣慰的是，这些看似棘手的全新系统问题在分布式系统工程领域早已积累了数十年的解决经验。我们无需重新发明轮子，而是可以将经典的可靠性设计模式直接映射并改造应用到自主AI系统中：
* **熔断器**转化为**工具隔离机制**
* **限流策略**转化为**Agent调用频率限制**
* **常规重试**转化为**控制流恢复**
* **资源配额**转化为**成本治理**
* **分布式链路追踪**转化为**Agent推理轨迹追踪**

整个行业已经历了多次分水岭式的变革：起初，提示词工程是各家企业的护城河；随后，基础模型的能力成为了核心差异化要素；然而，这两者目前都在迅速走向商品化。

AI竞争的下一场决战，毫无疑问将在**基础设施层**打响。未来能够在这场变革中最终胜出的企业，不一定拥有写得最好的提示词，但一定会拥有设计得最稳定、最可靠的系统架构。竞争优势正在向技术栈的更高层级快速转移。如果我们需要从这堂分享中提炼出一条最核心的架构共识，那就是：**必须将自主AI Agent视作分布式系统来进行架构设计**。模型本身是概率性的，但承载它们的系统基建必须是确定性的。AI时代的未来，必将属于那些拥有更优越系统设计的人。

<details>
<summary>Original English</summary>

The good news is that many of these problems are not entirely new. Distributed systems have solved something similar for decades. Circuit breakers become tool isolation. Rate limits become agent limits. Retries become control recovery. Resource quotas become cost governance. Observability becomes agent tracing. Instead of inventing entirely new infrastructure, we can adapt to reliability patterns for autonomous systems.

The industry has gone through several phases. The initially prompts were the differentiator. Then the models became the differentiator. And both are rapidly commoditizing. The next frontier is infrastructure. The organization that won't -- that wins is not necessarily have the best prompts. They'll have the most reliable systems. The competitive advantage is moving up the stack.

If there's one thing I want you to remember, it's this. AI agents should be treated as distributed systems. Models are stochastic. Infrastructures must be deterministic. Reliability is increasingly an infrastructure problem. Observability is mandatory. Control planes are emerging as a foundation layer. And ultimately, the future of the AI -- AI won't be won by better prompts. It will be won by better systems.

</details>