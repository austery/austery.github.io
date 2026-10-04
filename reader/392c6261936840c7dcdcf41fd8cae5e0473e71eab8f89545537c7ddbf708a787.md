---
author: AI Engineer
date: '2026-07-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=X1kp-ABIIxQ
speaker: AI Engineer
tags:
  - agent-architecture
  - durable-execution
  - system-decoupling
  - observability
  - feedback-loop
title: 重构智能体：通过三层解耦与持久执行层突破半衰期瓶颈
summary: 本文深度解析了智能体系统架构快速迭代下的应对之道，提出了将系统解耦为执行层、上下文层和计算层的三层模型。文章重点论述了执行层在状态持久化、断点续传、柔性编排原语及全链路可观测性中的关键作用，并展示了如何通过自适应审查闭环与基于业务结果的评分机制实现智能体的自我迭代。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people: []
companies_orgs:
  - Inngest
products_models: []
media_books: []
status: evergreen
---
### 架构半衰期：智能体系统的三层解耦

在快速演进的AI时代，智能体（Agent）系统的架构面临着极高的更新频率。如果你开发智能体系统超过六个月，你很可能已经重写过代码，甚至不止一次。无论是新模型的推出、新框架（或其新版本）的迭代、全新的工具调用标准，还是新的设计模式，都可能让现有的架构迅速失效。这并不是一种抱怨，而是当下的现实：技术的迭代速度比以往任何时候都快。在这种背景下，我们需要反思六个月前发布的系统，有多少代码依然在以最初设计的方式运行？那些得以幸存的代码，究竟是因为偶然，还是因为我们在架构设计上做出了深思熟虑的预判？

为了应对这种快速的衰退，我们需要建立一个清晰的**三层概念模型**，而不是仅仅依赖具体的组件图。在智能体系统设计中，主要包含以下三个独立的层级：
* **执行层**（Execution Layer）：这相当于系统的**大脑**。控制流（flow）、状态管理（state）、持久性（durability）以及重试机制（retries）都发生在这一层。
* **上下文层**（Context Layer）：这相当于系统的**知识**。它包含了模型（models）、提示词（prompts）、工具（tools）和记忆（memory）。这是整个系统中变化最频繁的层级。
* **计算层**（Compute Layer）：这相当于系统的**双手**。指的是由智能体自动化操作的沙箱（sandboxes）、运行环境（runtimes）以及浏览器。

这三个层级之所以需要被明确区分，是因为它们的**半衰期**（Half-life：系统或其组件因技术更迭而衰退一半所需的时间）大不相同。**提示词**（Prompts）的寿命如果运气好可能只有几周，甚至仅仅一周；所使用的**模型**（Models）寿命通常只有几个月；而如果设计得当，**执行层**（Execution）的生命周期可以延续数年。然而，目前大多数开发团队面临的问题在于，他们将所有这些层级紧密耦合在一起。当其中一个生命周期极短的层级（如提示词或模型）发生变化时，它的衰退会直接拖累并影响其他组件，从而产生巨大的技术债务。因此，核心的架构理念必须是：**分层思考，实现解耦**。

<details>
<summary>Original English Source</summary>

My name is Dan and I'm here to talk to you about how your agent architecture has a half-life of 6 months. But first who am I? I'm Dan, I'm the CTO and co-founder at Ingest. And why should you listen to me? Well, first I lead an amazing team over at Ingest. We build a system that reliably executes anything from agents to workflows to contact pipelines, whatever you want. I'm deep building AI infra every day and on top of that also building agents, not just pontificating up here in theory about how you should build it.

So speaking of building agents if you've been building agents for more than 6 months, you've likely rewritten something, maybe more than once. A new model a new framework or framework version new tool calling standard, a new pattern, suddenly your architecture doesn't fit. It's not a complaint. It's just the reality. Right, things move faster than ever. You can see if you've been to any of the the sessions or keynotes. So I want you to think about what you shipped 6 months ago and how much of it still runs the way that you originally wrote it. Some parts of your code likely survives. But did they survive by accident? Or did you design it that way? Did they survive by design? How did you actually architect your agent? Did you architect it at all? It's okay. Uh did you use a framework? Did you custom roll something? Was the architecture an intentional design that you really thought through? Or just kind of evolved into what you have now? These are all various ways of where people are these days.

So, a lot of folks have talked about harness architecture, building harnesses. But mostly, I think a lot of people draw diagrams and they talk about specific components. Draw just nice lines. It looks very similar like, you know, kind of simple. But I want to talk about the conceptual layers when you're building a system like this. This is maybe the mental model. Not specific components.

So, in my opinion, there are three discrete layers. First, the execution layer. I think of this as the brain. It's where flow, state, durability, retries happen. Then there's the context layer. This is the knowledge. All right, this is models, prompts, tools, memory. This is the layer that changes the most. And then there's compute. There are um this is the hands, right? This is sandboxes, runtimes, browsers that you're automating. I think these layers are important to consider for the following reason. It's your half-life. And what is half-life? All right, it's a scientific term. And it's a scientific term for the time that it takes for your for something to decay by half. And I think that your architecture has a half-life, also. So, prompts last weeks, if you're lucky, maybe maybe a single week. Uh the models that you use, months, again, if you're lucky. Uh but I think that execution can last years, if you do it right. So, the problem is that I think that most teams couple everything together. And what happens then is that one layer's half-life kind of leaks and drags the other components down. You're building it's technical debt by another name. So, my thesis is think in layers. Decouple them.
</details>

---

### 稳定执行层：实现状态持久化与断点续传

在理解了分层解耦的必要性后，我们需要将目光投向那个最稳定的核心——**执行层**。许多团队在选择智能体构建方案时，往往会倾向于使用某些开箱即用的框架。这些框架在起步阶段确实让人感觉非常神奇，或者他们也会从前沿实验室复制一些现成的架构，甚至花费数周时间自己完全手写一套系统。但在这些方案中，要么抽象机制完全缺位，要么抽象层次过高，导致执行层与其他层级融合在一起。比如，编排逻辑（orchestration）被深深埋在调用链或框架内部，以至于你根本无法掌控其运行机制；又或者重试逻辑（retries）与提示词逻辑（prompt logic）交织在了一起。在这种高耦合状态下，你无法在不重写几乎所有代码的前提下替换任何一个组件。

为了解决这些痛点，我们需要明确**执行层**的职责：它是指独立于底层基础设施、负责确保代码可靠运行、并管理每项任务如何、何时以及是否能顺利完成的系统。而在智能体架构中，执行层管理着整个生命周期——从规划、调用模型、运行代码、调用子智能体，到循环、重试和协同。

在执行层的具体设计中，最核心的要求是实现**可恢复性**（Resumability: 系统在发生故障时能够自动恢复并继续执行的能力）。智能体目前处理的任务生命周期越来越长，这意味着它们必须有能力在LLM调用失败、工具调用出错或网络抖动时，从故障点直接恢复运行，而不是从头开始。如果一个智能体在执行到第38步的“自我反思”步骤时失败了，系统应该能够等待并在此处重试，而不是让它重新跑一遍。否则，这不仅会造成Token的浪费，还会极大地增加计算成本、时间以及智能体已完成工作的丢失风险。因此，为了支持这种长达数小时的长任务运行，系统的状态绝不能仅仅保存在临时的内存或本地磁盘中。**状态必须是持久化的，且必须保存在执行工作流的外部**。如果不建立这种外部持久化的状态机制，你可能就不得不勉强拼凑一些手动的检查点（checkpointing）方案，或者采用基于日志的方式来在系统崩溃后重新加载（hydrating）状态，而这些妥协的抽象最终都会渗透到系统的其他层级中，让整个系统变得更加难以维护和变更。

<details>
<summary>Original English Source</summary>

So, let's talk about what I mean. Teams run into a lot of issues with the approaches that they choose. You might choose a framework, it might feel super magical to get going. You might grab a pre-built harness from one of the frontier labs or wherever. And or you might custom roll the entire system yourself, and it might take months or weeks or whatever. But I think in a lot of these situations, the abstractions either are not there at all or they're too high-level or the layers merge. You know, like orchestration is buried deep inside the chain or inside the framework, and you don't know what the heck's happening. Uh state might be kept in a sandbox. Uh retries get tangled with prompts, the prompt logic. And what's hard is you can't re- you can't like swap any of these things out without rewriting almost everything.

So, I think you need to embrace the change. Know that things are going to change. Know that things are moving fast. But I think also with that is I want to focus on a layer that I think is the stable layer here. Where you can invest and think about and get your abstractions right, so you don't need to rewrite a large component every 6 months. So, I'm talking about the execution layer. I don't think enough people talk about this. And I define it as the execution layer as being the system responsible for running your code reliably, managing how, when, or whether each piece of work completes. And that's independent of the infrastructure that it's on.

So, what does this look like in an agent architecture? So, the execution layer manages the full life cycle. You know, plan, call a model, run code, invoke a sub-agent, loop, retry, coordinate. You can swap the model, swap the context, swap the sandbox, the execution layer should be able to remain the same. It's just the the fundamentals. And that's how you, I think, decouple and you build the system that it can evolve for change.

So, let's talk about what the execution layer has to do. First, resumability. Your execution layer must enable your system to pick up after failures without restarting from the beginning. You know, agents are handling longer-running tasks than ever before. So, they must be able to resume when an LLM call fails, a tool call fails, everything flakes out. We all know. So, if you have a failed reflect step 38, you should be able to retry, wait, continue onwards, instead of having to go from the beginning, and you're going to lose tokens, costs, time, work that your agent might have completed. So, for this this to work, a 3-hour run cannot hold state in memory or in disk. The state must live outside of the work. So, this means that the state must be durable and external. So, without it, you might cobble together maybe some manual checkpointing. You might come up with a system that has like a log-based approach where you're going to be like hydrating the state back if you have to pick up where you left off. But, I think a lot of those abstractions start leaking into the other layers of your harness, right? It gets harder to change.
</details>

---

### 编排原语与沙箱隔离的系统边界

除了可恢复性之外，高保真的执行层还必须具备组合多种调用模式的能力。在实际的企业级应用中，智能体不可能只采用单一的请求-响应模式。你必然会需要定时任务（crons）来触发定期检查，需要基于事件（events）的机制来响应外部系统的变化，需要开放API以便与其他服务交互，同时还需要引入**人机协同**（Human in the Loop: 引入人工干预或确认的机制）来对关键步骤进行把关。此外，智能体之间或动态工作流之间的协同与派发也是不可或缺的。这就要求执行层提供极其灵活的执行与**编排原语**（Orchestration Primitives: 用于描述和控制多步骤任务流的原子操作），使用户能够以同步、异步或延迟调用的方式来编排任务。如果缺乏这种底层的编排能力，开发人员就不得不自己去处理诸如队列（queues）、工作线程（workers）、轮询（polling）、指数退避重试（backoff）和调度（scheduling）等繁琐的工程细节，导致系统的控制逻辑变得极其混乱。

在此基础上，我们还必须理清执行层与**计算沙箱**（Compute Sandboxes）之间的边界。当前，沙箱技术在智能体领域非常热门，因为智能体需要一个隔离的环境来执行生成的代码、浏览网页、处理文件或在磁盘上进行操作。然而，很多团队犯下的一个典型错误是：试图将状态或持久性保存在沙箱内部。事实上，**沙箱在设计上应该是瞬态且无状态的**（ephemeral and stateless by design）。利用沙箱做快照或存储状态是一个典型的反模式。一旦沙箱崩溃，所有的状态都会丢失，重建这些上下文将变得极其困难。正确的做法是保持两者的清晰界定：执行层作为**大脑**，负责管理智能体的序列、上下文和持久性；而沙箱则作为**双手**，仅仅负责执行大脑下发的具体动作。只有这样，大脑才不会因为双手的意外受损而丧失记忆，整个系统才能具备面对变化时的演进能力。

<details>
<summary>Original English Source</summary>

So, next, a key aspect of the execution layer is that it must enable you to combine a lot of invocation patterns. You're going to need crons. You're going to need to trigger things with events. You're going to need APIs, human in the loop. Subagents or dynamic workflows also must be possible. You're going to need to be able to invoke these things synchronously, asynchronously, delaying invocation. And I think the key here is that flexible execution and orchestration primitives will enable you to build the pattern or the system the architecture that you actually need. So, if not, I think again, your harness logic starts absorbing other concepts like queues, workers, polling, backoff, scheduling. And now you end up kind of a mess bad abstractions.

So, lastly, execution needs to provide observability across your entire session. Not just the LLM calls, the tool calls, but database errors, permissions issues, um triggers, performance. So, the full session trace across your entire run is essential. So, if you can't see the entirety of a trace from the trigger through the whole stack, it's really hard to debug it, let alone improve your agent and keep evolving it.

So, what about sandboxes? Sandboxes are so hot. So, agents need sandboxes. We kind of like settled upon that at this point in time. They need to execute code. They need to browse. They need to manipulate files. They might work on disk. But, a sandbox is ephemeral and stateless by design. So, using it for durability, snapshots, or something in state, I think is an anti-pattern. I think it's a difficult thing where the state gets lost and you're kind of trying to peel pull the pieces back together. So, I think when you have the execution layer separate, the execution layer is what gives the sandbox its context, its sequence, its durability. So, I think of the sandbox as the hands and execution as the brain.
</details>

---

### 自适应自主演进：未来的智能体反馈环

展望未来，智能体架构的下一个演进阶段将主要围绕**后台智能体**（Background Agents）、动态工作流和自主循环（autonomous loops）展开。这些模式的共同特征在于，它们是长生命周期的、异步的、且高度委派的。在一个可能需要执行数百步且包含大量工具调用的复杂流程中，哪怕发生一次网络故障，如果没有弹性的执行层支撑，整个系统就会彻底瘫痪。为了让这类复杂的自主系统在生产环境中安全可靠地运行，我们不仅需要全链路的可观测性，还需要在系统设计上引入**自适应评估与优化闭环**。

具体而言，一个自适应的智能体系统应该由以下三个核心功能模块构成：
* **触发与分类**（Triage Agent）：例如，系统可以每30分钟通过定时任务拉取系统的核心性能指标，并传递给LLM进行健康状况评估。一旦检测到异常，便自动唤醒一个专门的分类智能体。该智能体会在沙箱中克隆代码库、分析提交记录（commits）并调用工具，进行深入的问题根因排查。
* **自主执行**（Autonomous Execution）：在沙箱等安全隔离环境中，智能体自主运行诊断工具、分析上下文，并在无需人工干预的情况下尝试解决问题。
* **审查与反馈**（Reviewer Function）：审查模块会定期（如每周）拉取执行层的历史运行日志，对分类智能体的表现进行评估。它会分析智能体具体执行了哪些动作、派发了哪些子智能体、调用了哪些工作流，并以此判断：智能体是否做出了过度反应？现有的提示词是否需要微调？系统收集的数据是否足够？随后，审查模块可以直接修改提示词，或者向工程团队反馈系统的调优建议，从而完成整个系统的自我迭代。

由于执行层恰好处于用户输入与系统实际行为的交汇点，这使其成为进行全链路监测和评分的最佳中心。在这个位置，我们不仅可以追踪LLM的输入输出，还可以捕获数据库错误、权限异常以及各种异步事件。我们可以利用这个中心，在工作流结束后延迟执行评分逻辑，结合完整的链路追踪数据，建立起**基于结果的评分机制**（Outcome-based Scores: 通过最终业务结果而非中间过程来评估系统表现的指标）。例如，与其简单让用户进行“赞”或“踩”的反馈，不如通过事件追踪来判断：针对分类智能体定位的问题，工程团队最终是否真正提交并合并了对应的Pull Request？如果是，这便是一个确凿的正面业务结果。通过将这种基于真实业务结果的反馈直接关联到智能体的执行链上，智能体系统的持续演化将变得更加自然和高效。

这就是我们构建 **Inngest** 的初衷——专为 AI 智能体设计的**持久化执行层**（Durable Execution Layer）。它充当了智能体架构中的大脑，允许你接入任何上下文层（模型、提示词、框架）和任何计算层（沙箱、浏览器），提供断点续传、事件触发、智能体间协同以及全链路会话追踪等原语，帮助开发者在瞬息万变的技术潮流中，构建出能够应对未来变化的稳定智能体系统。

<details>
<summary>Original English Source</summary>

So, what's next? All right, what are the next six months of architectures that you're going to need to handle? So, if you're paying attention, you're joining a lot of these sessions, you'll see what architectures are emerging and what each approach brings new engineering requirements. You know, you have background agents, dynamic workflows, autonomous loops, agent factories, whatever you want to call it, all these emerging trends that we're seeing the last couple days. They're all long-running. They're all asynchronous. They're all delegated. That means that you need to be able to observe them all uh down to the core. All right, they need to be inspectable by human and by an agent. So, the patterns, as you see, they as these things emerge, they must be mixed and combined together. So, what does this all have in common? I think that execution is fundamental to building any of these systems.

So, let's just take one example here, background agents, right? They're not request response. There's no person just waiting there for you for the the the chatbot to respond. So, it could might run for minutes or hours. It's going to have maybe hundreds of calls to you know, maybe 200 tool calls. You're going to probably guarantee to have at least one failure in that. So, you can't even debug your background agent that's running asynchronously without the right infrastructure, without the observability, without everything that's going on in that process or multiple processes.

And another example that we have is is loop architectures. Right? I think we're talking about slash loop commands and whatnot and coding agents, but I think where we're taking this is how are you building actual systems in your products that employ these these these approaches. So, like what is a loop? Right? A loop is a system that basically just runs continuously or on a schedule and it's assessing the state of the system against the the goals that you set or the criteria that you set and determines what to do next. So, you're going to need crons, sub-agent delegation, the history needs to be inspectable, and of course it needs to be reliable because you don't know when things are running or how the system is continuously continuing to evolve. So, the frameworks of 3 months ago were not designed to handle this. Right? Like you're going to need to design these systems yourself. So, I think you're going to need a proper execution layer.

So, let's look at just some examples of code. It's small on here, but in general, let's just look at how we might put it together. In your loop, you're going to need some sort of cron. Maybe that cron here is some sort of health check system runs every 30 minutes, pulls down some key high-level system metrics, and it looks you pass to an LLM. You say, "Is this healthy? Is this looking okay? Should we do more? And it is it is healthy or not? What should we do?" And if it isn't healthy, maybe you just invoke a a triage agent that goes and looks at that individual service and goes and digs more. It's pretty simple looking, right? Now you have this triage agent itself. You've just triggered it. This should maybe pull some more context, pull some detailed metrics. It's just context. And then you're passing to the LLM to start that investigation. Putting in a loop, you're calling some tools, trying to get to the root cause. This may run for a minute. This may run for multiple minutes. It needs to spin up a sandbox, uh maybe clone code, maybe analyze commits. It's going to be doing a lot of work here, and you don't know when this is going to run. It might run, it might not. How do you know? How do you observe that system later?

And then to complete the loop, there you may have a reviewer function, right? Like, are we Is the system actually performing as expected? Right? Like, it's going to run every week and look at the history of what just happened and evaluate how the triage system is working. Do we need to adjust the prompts? Do we need to do better metrics? Does this have the data that it needs? Is it doing anything at all? Is it overreacting? So, it needs to be execution aware. And I think it needs to be execution aware, orchestration aware, because it needs to be able to pull the logs of the system and understand, all right, what was executed? What did this agent choose to execute? What sub agents did it fan out? What workflows did it call upon? And then it needs to be able to analyze that and understand what happened and come back to you, either make the change itself or tell you this is where we performed or underperformed. This is what we can do, how we can improve the system overall. So, this completes this improving loop. It's three functions. It's pretty simple by design. It's flexible to iterate on. I know things get always a lot more complex in production, but I think about when when I think you think about the layers this way, makes things a little bit little bit easier to think about building such a complex system that feels like it's, you know, something that you might not be able to reach right now.

So, in the spirit of the reviewing functions, what do you think about measuring your agent, how your agent is performing? You know, I think what's interesting is this execution layer sits between what your users' input is and what's happening throughout the system. So, user feedback, actions, um and the results of the sessions all flow through this execution layer. And I think this makes it uh an ideal place because it becomes the hub for observability. And it allows you to be able to score and understand what your agent is doing. So, to iterate on your application, you kind of need all this data connected and it needs to be aware of how your code is actually executing. Right? So, I think the the linking of this is is extremely important.

So, this is what we built Ingest for. We're durable execution for AI agents. We're the execution layer. You can plug in any context layer, bring a model, framework, tool, any compute layer. Bring whatever sandbox you want. Bring whatever browser you want. You get durable steps, small primitives, right? Uh event triggers, scheduling, agent-to-agent coordination, full session traces, no infra to manage. And I think like I just mentioned with scores, we also think that that that the middle of the execution layer, when your agent is running, is a key place to instrument and score your agents. When you have access to the data that you need that's all flowing through there or you've just executed something, it's a perfect place to run something after and defer some scoring for with the whole trace information, maybe the inputs and the outputs. So, again, that's just execution orchestration, delayed task deferrals on and since there's also data flowing through, you can also wait for additional events and attach them to the sessions that you're building and understand did this did this actually work, right? If you're if you're running this triage, um was this triage successful? Did it result in an action by the engineering team? Then that means it probably was a positive result. Instead of a thumbs up, thumbs down, it's like did we open the PR, right? If it's a research agent, was this research saved? Was it a good report? That is these these things that are events that you should be able to attach and when you have a system that can connect all these pieces, I think it's really makes doing a lot of those things um like creating outcome-based scores a lot easier.

So, to wrap up, build your harness. You know, understand the layers of the architecture. We have to embrace fast-paced pace of change. And I think if you can get your execution layer right and think about the right primitives, everything else can quickly evolve around it. And the next 6 months, the next 3 months will all be a lot easier for especially as everything continues to change. You all are here. So, thanks for listening. I'm Dan. Um come and find me at the ng-js booth. We're right on the other side of this wall. We're very bright and orange. So, thanks everyone. Appreciate it. Mhm.
</details>