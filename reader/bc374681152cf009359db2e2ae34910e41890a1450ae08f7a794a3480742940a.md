---
author: AI Engineer
date: '2026-10-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=NaOkR3VSfR4
speaker: AI Engineer
tags:
  - agentic-workflow
  - orchestration
  - saga-pattern
  - deterministic-systems
  - production-ai
title: 大脑与双手：生产环境中安全运行 AI Agent 的 Harness 架构
summary: 本文探讨了在生产环境中部署 AI Agent 的核心挑战与架构范式。作者指出 Agent 不应仅被视为孤立的聊天机器人或单一组件，而应作为完整应用来构建。通过提出“大脑负责非确定性规划，Harness（双手）负责确定性执行与持久化工作流”的核心分离原则，结合基于 Conductor 的后期绑定 Saga 模式与 SRE 故障自愈案例，展示了如何让 Agent 系统安全、可控且持久地稳定运行。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - Conductor
media_books: []
status: evergreen
---
### 超越对话系统：生产环境 Agent 的应用级定位

在探讨生产环境中的 **AI 智能体**（AI Agent: 具备自主规划、工具调用与上下文决策能力的 AI 系统）时，业界早期的“Hello World”式示例往往将视野局限于非常狭窄的范围——一个大语言模型（LLM）配合简单的工具调用，根据上下文和记忆制定计划，最常见的形态便是客服聊天机器人。然而在真实的生产级工程场景中，Agent 的形态正在迅速泛化为多样化的后台常驻系统：它们包括按小时或固定 Cron 周期唤醒以巡检日历与业务排期的定时后台任务（Scheduled Background Workers）、实时监听系统告警与日志流并在异常发生时快速反应的事件驱动型智能体（Event-Driven Agents）、以及长期运行并负责监视其他 Agent 状态与纠偏的协同编排器（Long-Running Coordinators）。

为了防止单点模型承载过多责任而诱发灾难性的模型幻觉，复杂系统必须演进为多智能体网络（Multi-Agent Systems）。正如经典微服务架构倡导的**单一职责原则**（Single Responsibility Principle: 每个服务模块仅对单一业务职责负责），在生产环境中绝不可能上线一个包揽所有功能的超级单体服务。现代微服务依靠编排（Orchestration）与编舞（Choreography）协同支撑完整应用；同理，单一的 Agent 组件并不能独立兑现生产承诺。**执行框架**（Agent Harness: 负责管控智能体执行生命周期、连接企业数据库、串联人类在环审查与工具协议的底层宿主应用）才是真正的应用实体，Agent 必须嵌入在 Harness 建立的控制流与系统防护网中运行。

<details>
<summary>Original English Source</summary>

Cool. Thank you all for joining this morning. I know it's been an exciting week. A lot of talk about agents, building agents, coding agents, everything. And what I want to talk about in the next fifteen to twenty minutes is about building agents in production and things that have come to the top of pretty much everybody's mind when it comes to building agents and running agents harnesses.

Before I get started, I would like to ask in the audience: how many of you are running agents in production today? Awesome, so a lot of hands up. I was in another conference a couple of weeks ago and I asked the same question, and I think I had like one hand. So this is pretty good, it seems like things are going forward.

All right. So when we think about agents, if we go back to kind of the "Hello World" equivalent examples of agents, it always starts with an agent with a tool call and how well an LLM decides to call the tool, maybe use some sort of context or memory and plan things ahead. What we start to realize is that's a very small, narrowed picture. When you think about agents in production, it's not just about chatbots. The early examples that we had seen were all about building a customer service chatbot or some sort of chatbot. But when we start thinking about agents in broader terms, we talk about background agents, background workers, agents that are running on schedule. I would like to have an agent that runs every hour to check what's happening with my schedule, and if there is something new that has popped up that I should think about.

Even event-driven agents, right? Agents that are listening on various events. To give you an example, I have a production system running where my alerts are firing every moment and then I have logs coming out. I would like my agents to listen to those events and react on it and see what's going on there. I could have long-running coordinators. And what I mean by that is, I have an agent running for a longer period of time, and I would like to have an agent monitoring that agent to see, "Hey, what's going on there, and should I nudge that agent to kind of move forward, take a different action?" and things like that.

Also, one more thing is about multi-agent systems—agents talking to other agents. The last thing you want is to have an agent be responsible for multiple things and risk hallucinations. The more we think about agents, the way I would like to think about it is that the agent starts to feel more like an application, not just a component.

If you go back to the old school thought of microservices—and probably we are still building microservices—you are not going to ship a microservice in production that does everything. It kind of stops being a microservice at that point in time. Typically, we are shipping multiple microservices; they are talking to each other through choreography or orchestration, and you have an application that is relying on that set of microservices, which essentially follow single responsibility principles to deliver the goals.

There is kind of a very clear parallel when it comes to agent harnesses. If you think about a harness that is responsible for achieving a specific goal—so let's say I have a harness for doing my SRE work—it's operating on multiple agents to see what's going on there. Maybe it's listening on events coming from my logging system, talking to my Kubernetes cluster as an agent to find out what's going on there, my metric systems, my customer service dashboards, and so on and so forth.

What I want to drive there is that your harness is the application. An agent alone doesn't deliver the whole premise, but rather when you start putting things together and you build a harness that controls the execution of the agent and delivers on the premise, that's where you start thinking about an application. You have internal systems, enterprise systems, databases, humans in the loop, and tools through either API or MCP that are all playing together.

</details>

### 大脑与双手：非确定性规划与确定性执行的解耦

构建工业级 Agent 系统的根本要义，在于深刻理解并清晰划分系统的**确定性**与**非确定性**边界。LLM 的非确定性（Non-determinism）在推理、假设分析与宏观思考阶段展现出极高价值；然而在支付交易扣款、生产集群配置调整或服务发布重启等核心环节，绝对不能容忍任何不可控的随机性。例如在管理 Kubernetes 集群的 SRE 场景下，集群重启必须遵循极为严格、步序明确且可审计的预定义工作流。

因此，架构设计的核心黄金法则为**大脑与双手的职责分离**：非确定性 Agent（LLM）扮演大脑的角色，其唯一职责是**规划下一步应采取的行动**，严禁直接触发实际底层副作用；而作为双手的 Harness 则是一个完全确定性的代码容器，专门负责理解、编排并**严格执行具体任务**。在涉及高风险操作（如生产集群重启）时，Harness 必须强制引入确定性的控制栅栏（如向 Slack 推送人工确认卡片并实施 Human-in-the-loop 门禁），确保操作的**幂等性**（Idempotence: 相同操作重复执行多次所产生的影响均与一次执行完全一致）与副作用审计追踪，避免将关键系统的生死大权拱手让给随时可能发生幻觉的大模型。

与传统的瞬时计算不同，Harness 是生命周期长达数秒、数天乃至数月的**长运行进程**（Long-Running Process）。在跨越供应链交付确认、跨系统数据同步或长达数周的人工审批流中，Harness 必须在基础设施网络分区、节点重启等各种硬件故障发生时，具备从故障点无缝自愈的**持久化耐用性**（Durability: 系统在节点崩溃或硬件故障重启后仍能完好恢复执行状态与上下文的能力）。持久化与容灾能力绝不是某种锦上添花的附加特性，而是任何生产级 Harness 进入企业基础设施架构的最低入场门槛。

<details>
<summary>Original English Source</summary>

A harness runs more than just an agent loop. This is an important thing that I kind of learned while trying to build harnesses for real-world production use cases: it is a combination of both deterministic and non-deterministic parts of an application.

Non-determinism is delivered by an LLM in terms of reasoning and thinking processes. And then there is the deterministic part, which you do not want non-determinism seeping into. Think about payments, or let's say if I have an agent harness that is responsible for monitoring my production deployment and how I manage my Kubernetes clusters. I probably want to have a very, very defined workflow in terms of what sequence of steps I execute when I want to restart my cluster. That's a very deterministic set of processes where every time it runs, I know exactly what it does. So I want determinism to be delivered by my harness when it matters.

And of course, the harness is a long-running process. It runs across time; it can run anywhere from a few seconds—if it's something very quick like checking what's going on—all the way to running for days, months, even longer than that. Think about long-running processes like order management systems where you are waiting on third-party services to deliver your shipment, or waiting on humans to take actions and approve things and so on and so forth. Your harness is waiting for events to happen, so when that event happens, you take an action and do something around it.

That brings another important point: when you think about long-running systems, you need durability. You want to be able to recover when things fail, because at the end of the day, these harnesses are running somewhere in your entire infrastructure stack—maybe in the cloud, maybe in a sandbox. But those things can go up, go down; there could be network failures, partitioning, anything that could be happening. So you need the harnesses to be durable. Durability is the cost of admission; that's not a feature that you are looking for in a harness.

The loop that the harness runs spans across the agent and everything else. How does the harness operate? In a loop, essentially what it is doing is: it has a state of the world. It knows what work has completed, what has been recorded in terms of side effects—if I did a cluster restart, I know I have that recorded; if I sent an email, I know that has happened. I know what worked, what didn't work. And then based on the current state of the world and the goal, I know what needs to happen next. That's where the reasoning and the LLM comes into the picture.

What really happens here is that if you think about a clear distinction—and this is the most important thing, if there is one thing that I would like everyone to take away from here, it is this: the responsibility of a non-deterministic agent is to plan what should happen next, not really to do things. And then the harness is the one who actually does the execution.

This is important for various reasons. One being that the harness is a deterministic piece of code that actually understands what is involved in executing a piece of work. As I mentioned, if the harness that runs my DevOps or SRE agents hears from the agent saying, "Hey, this cluster is unhealthy and you should restart," the harness should decide how to restart the cluster and what is involved in restarting the cluster. That has to be—at least in my world—very deterministic.

Also, if it needs an approval—for example, if I'm trying to restart a production cluster—I probably want to have a human gate, probably send a Slack message to somebody to say, "Hey, I'm trying to restart this cluster, do you think it's okay to do that or not?" And I do not want this to be left to an hallucination by an LLM that decides it doesn't need to do it. It needs to be guaranteed in terms of execution.

Ideally, I want this to be idempotent. And if not, I want it to be recorded that it is not idempotent and this is what has happened, so I can handle the side effects separately.

So this is the most important thing: the clear separation between the brains and the hands. Harness is the hands; the brain is the LLM. The agent creates the plan, and the harness executes the plan.

</details>

### 后期绑定 Saga 模式与 Conductor 故障自愈实践

从分布式计算的发展历史来看，这种编排思想并非全新发明，其深层理论根植于经典的分布式事务设计范式。在传统微服务中，工程师通常以硬编码方式显式编写包含补偿逻辑的工作流。在 Agent 架构中，Harness 本质上实现的是一种**后期绑定 Saga 模式**（Late-Bound Saga: 在运行时由大模型根据环境上下文动态组装确定性步骤与补偿操作的分布式事务流）。与在代码编写期穷举并硬编码所有可能分支路径的传统方式不同，智能体面对有限且确定的一组工具与任务，在运行时根据现实反馈动态生成最贴合当前场景的执行路径分支，同时完整继承传统 Saga 事务在可视化追踪、步序干预与异常回滚机制上的全部确定性优势。

在具体的工程实现中，开源工作流编排引擎 **Conductor**（Conductor: 一款支持复杂分布式微服务与任务流编排的高可用开源引擎）可作为坚固的底层执行基座。在一个生产级 SRE 智能体自愈演示中，整个系统运行着严谨的双阶段循环：
* **首轮规划与执行阶段**：LLM 大脑感知系统输入并评估全局状态，一口气提出包含多个关联步骤的宏观计划——“采集异常证据、分析日志、必要时回滚部署、验证恢复指标”。该计划随后被送入专门的 `plan-and-compile` 工具，直接编译为可由 Conductor 引擎稳定驱动的确定性工作流并落地执行。
* **次轮验证与闭环阶段**：首轮执行完成后，Agent 重新捕获最新系统状态启动下一轮循环。此时 Agent 观察到回滚已在上一轮成功完成，遂做出“跳过回滚，仅执行下游链路检查与最终状态确认”的决策。

这种让大模型负责宏观连续步骤规划、底层引擎负责工作流编译、执行保障与状态幂等追踪的架构，成功兼顾了通用人工智能的灵活适应力与核心生产环境对零容忍事故率的绝对确定性要求。

<details>
<summary>Original English Source</summary>

Is this a new concept? This is not necessarily a new concept; this has been around for a while. If you think about workflows or Sagas, which we used to write ourselves and define exactly what happens, it is a very deterministic set of processes. When you think about agentic harnesses, they are essentially late-bound Sagas. What I mean by that is they have a very finite and deterministic set of tools and tasks that they can operate on, but instead of putting them together upfront, the agent is proposing and building them at runtime.

Therefore, they are essentially late-bound Sagas, but you get all the benefits of a traditional Saga in a workflow out of the box in terms of visibility into what's happening, being able to control things, and iterating upon how far ahead in the future the agent is able to plan. You are able to plan one step at a time or multiple steps at a time. It's more like a branching workflow: if only you could build a workflow with every possible combination of a branch, it kind of builds that thing for you. With agents, it simplifies the work. If you have any number of tools, they can do any different combinations of executions, which otherwise could be almost impossible to think of ahead of time and do.

Let's take a look at it. What I am going to do is quickly show a completed run of what I talked about earlier. It is one of my example agents that essentially is acting like an SRE agent. What its job is to do is understand what's going on in the current system, try to plan what should happen next, and execute on those things.

It's essentially a remediation loop that runs twice. In the first iteration, it tries to understand the root cause of the problem, tries to react to that, observes the output of it, and then runs another loop and plans another set of steps to see what should happen next.

So as an input to my agent: step number one makes a call to the LLM. It's an SRE agent demo, and the LLM proposes a sequence of steps to do instead of just doing one step at a time: "You should gather evidence, you should analyze logs, and if required based on the evidence, you should raise a rollback on deployment and then verify recovery."

This is then given to a specialized tool called "plan and compile." This plan that the agent gave gets compiled into a very deterministic workflow. We are relying on Conductor as our workflow execution engine here. The output is a fully runnable workflow that gets executed.

In the first step of execution, we analyzed the logs, looked at the metrics, decided to do a rollback, and verified recovery. When step number one is completed, it runs another loop. In the next iteration, it decides: "Okay, looks like these things have been done. Let's check downstream, and if required verify recovery and complete it." And then the next one runs and accomplishes the task.

Here is an example of an agentic loop looking at the current state of the world, planning multiple steps at a time, executing that, verifying, and completing the loop. Now, this can run in production as many times as you want, triggered on events or running on a schedule. In the second iteration, we decided not to do a rollback because it was already done in the first iteration.

That's about harnesses in agents and how they bring determinism to your production application. The example I showed you runs on Conductor. Conductor is an open-source workflow orchestration platform that supports building agentic loops as well as agentic systems. Feel free to try it out, join our Slack, or stop by our booth at Orkes if you want to see a live demo. Thank you.

</details>