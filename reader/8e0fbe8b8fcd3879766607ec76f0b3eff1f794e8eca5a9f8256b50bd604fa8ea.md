---
author: AI Engineer
date: '2026-10-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_4Ph2dhmUFI
speaker: AI Engineer
tags:
  - workflow-orchestration
  - model-evaluation
  - system-trust
  - policy-compliance
title: 策略性临在：在合规策略工作流中构建受信任的AI智能体
summary: Coinbase资深专家Evan Cormos探讨了在企业合规与强监管流程中落地AI智能体的系统架构。通过外部确定性DAG与内部自适应DCG的解耦设计，结合评估与链路追踪构建置信机制，实现从人工监督、抽样核查到自主运行的渐进式跃升。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Coinbase
products_models:
  - Apache Airflow
  - LangGraph
media_books: []
status: evergreen
---
### 策略与运行系统的解耦：制度意图的系统提示词化

在企业金融服务体系中，构建任何自动化软件的基础都始于**策略**（Policy），尤其是涉及风险控制与合规要求的领域。我们可以将组织策略视为最原始的制度意图，或者说是一种原生的**系统提示词**（System Prompt: 规定模型行为边界与指令的核心提示词）。这些策略通常以书面形式确立，通过使用诸如“必须（must）”、“可以（may）”以及“应当（should）”等规范性词汇，精确定义了业务系统在组织内部运作时的规则与决策边界。

然而，在工程实现层面，必须将静态的策略规范与动态的**运行系统**（Running System）在时间维度上严格区隔开来。构建期（Build State）负责策略的制定与变更，而运行期（Run State）则是一个持续运转、不断快速迭代演进的实体，随时面临产品驱动的变更压力。虽然运行系统中的一切行为都必须大致约束在策略边界之内，但在传统企业典型的**人员、流程与技术**（People, Process, Technology）三元模型中，AI 智能体并非单纯归属于某一要素，而是一种贯穿三者的全新运营模型：它们与人协作，自身执行流程环节，同时又由底层技术驱动并依托技术构建。本次探讨的核心，正是智能体与流程相互交织的关键界面。

<details>
<summary>Original English Source</summary>

Hi everyone. My name is Evan Cormos. I've been delivering, designing, building software for 20 years. The last 15 in enterprise financial services. I am a player coach at Coinbase. And we're here today to talk about trusting agents in policy-driven workflows.

So, let's start with the policy and it's pretty boring. I'm going to go over here for my notes. So, our starting point centers around the policy and this sets the rules for how work gets done within the organization and including especially risk and compliance. Think of policy as the original institutional intent or the original system prompt. So, ideally we have this written down. It's a little bit boring, so stick with me, using language like must, may, and should. And again, these help define the rules and decisions about how the system operates in the organization.

Separate from policy, we have the actual running system. So, the first thing we're going to do is separate these two—both the build state and the run state in two different moments in time. So, typically we're either defining or changing our policy, but the system is constantly running and it's constantly moving and changing. It's evolving quickly with these product-driven changes. So, everything is expected to still be roughly bound by the policy, but ultimately we separate this from the run state and the build state.

So, inside the system, what does it look like? We have a familiar model if we have any enterprise folks in the room here: people, process, and technology. But, where really do agents fit into this model? So, I see them as an operational model cutting across all three. They work with people, execute parts of the process themselves, and they use and are made up of technology. So, for our talk today, we're going to be focusing here where agents meet process: what work we give them, what boundaries we set, and how we build trust in their outputs.
</details>

### 双层拓扑架构：外层确定性 DAG 与内层自适应 DCG

在结构化工作流中，业务执行往往遵循特定的门禁方向，例如代码变更必须在上线前获得审批，或客户在开户前必须完成资质验证。传统上，许多并行任务因协调成本过高或逻辑过于复杂而难以实施。而智能体的引入让重新审视**并行处理能力**成为可能——我们可以在保留强制检查的前提下，并行运行多个独立审查并汇聚结果。这种外层工作流可以通过**有向无环图**（Directed Acyclic Graph / DAG: 节点单向流动且不闭合形成循环的图结构）来表示，像开源工具 **Apache Airflow** 便是通过 Python 代码将任务依赖定义为 DAG 的典型代表，适用于商业贷款审批、区域交易所代币挂牌或合规软件交付等严谨流程。

然而，一旦深入到 DAG 流程图的单个节点内部，其微观运作机制本质上是一个反馈循环。以代码审查节点为例，智能体与人类执行一系列操作，评估输出是否达到标准；若未达标，则根据反馈不断迭代修改，直至质量足以进入下一步。这种内部微观流程呈现为**有向有环图**（Directed Cyclic Graph / DCG: 包含闭环迭代路径的图结构），开源框架如 **LangGraph** 则专为管理此类状态循环而设计。这种宏观确定性与微观适应性的结合，构成了双层架构的核心：外层由策略边界守护，内层由人机协同迭代。与此同时，流程必须建立**异常流**（Exception Flows）监控机制，在代码违规或安全未达标时及时告警与分流，避免系统陷入停滞或为罕见边缘案例过度设计。

<details>
<summary>Original English Source</summary>

So, let's dive into your workflow. And it's high-level and seems basic, but if you haven't, there are good reasons to map this out. So, maybe a change has to be approved before it goes live, or a customer has to go through verification before their account is opened. We expect work to flow in a specific and gated direction.

So, I believe agents make it worth revisiting what we can do in parallel. Previously some work used to cost too much or be too complex to coordinate in this way. But now we can run independent reviews alongside each other, bring the results together, but keep the required checks in place. So this is a directed acyclic graph or a DAG. It is a way to represent this workflow or process, the steps, the dependencies for a flow that moves forward without looping back on itself. Apache Airflow, if you're familiar, is an example of open source software that represents workflows, their dependencies as DAGs in Python code. So these DAGs can be used to define and manage a number of policy-driven processes like, for example, commercial lending. We could also use a DAG to represent the workflow to list a token on the exchange in a specific region, if you're into that. Or we could use a DAG to represent a regulated flow of delivering software, which is a hot topic. And one we'll spend a little bit of time on, I think that we've seen a lot of adoption within agents, within software delivery, and ultimately we're looking to leverage that same efficiency and scale in other areas of the business and close the adoption gap.

So let's stick with the software delivery example for a little bit. What happens inside one of these nodes of the process? And I'll give you a hint, it's a loop. I'm oversimplified, but we have a basic version of what's happening within the—let's say this is a code review process, right? So, we're going to essentially do a number of steps and essentially once we recognize that the work is good enough, we're going to allow it to pass on to the next step. And that's essentially the function of the code review node. The work doesn't always end up okay. So, sometimes we have to take the feedback from the code review and iterate on it until the work is good enough to pass. So, this is a representation of a directed cyclic graph or DCG. So, as far as open source software, something like LangChain LangGraph would be what I would say is helpful to manage the state of DCGs. And this is an oversimplification. These graphs can be very complex.

So, zooming back out, the inner flow of the node, we have people and agents working together. On the outer flow, we have a policy boundary. But not everything goes to plan. So, we have to handle exception flows. We don't want the work to get stuck, and we don't want to design for every edge case, either. The exception flows will monitor and see kind of what happens if you're shipping code that gets canceled or doesn't meet security standards, that's something you should want to know about.
</details>

### 流量迁移与质量置信机制的重塑

当智能体大规模融入工作流时，整个管线的吞吐**吞吐量重心转移**（Volume Shifts）现象便会凸显。比如在软件交付中，代码审查环节如果被智能体极大加速，瓶颈就会立即转移到上游的设计阶段或下游的安全扫描环节。为了应对系统加速与并行化引发的动态拥堵，**端到端运营可视性**（Operational Visibility）变得至关重要，其重要性甚至超越了编排工具本身的编写。在维持既有合规管控的前提下，唯有借助全面的度量指标与可视化手段，才能科学地向特定节点动态补充并行容量。

支撑这一循环运转的核心难点在于“检查”环节（Check）：系统如何判定产出“足够好”？在传统确定性软件工程中，质量信心依赖单元测试、集成测试等严密的测试用例矩阵；而在由概率驱动的 AI 智能体系统中，相同的输入可能产生不同的合规输出。因此，单纯依靠精确比对无法衡量其效能。为了在概率性环境中建立确定性的工程信心，必须构建双重机制：一方面向智能体注入 DAG 全局上下文以保障高质量输入；另一方面引入**评估体系**（Evaluations / Evals: 依托代表性测试集开展的系统性统计评估）与**链路追踪**（Traces: 完整记录智能体运行期决策与行为日志的观测技术）。通过大规模的统计分析而非单次输出校验，定义清晰的质量基准，才能赋予反馈循环真正的可靠性。

<details>
<summary>Original English Source</summary>

Volume shifts across the flow once we start to add agents into the mix and we've seen this with software delivery and we'll see it in other processes as we bring agents into those processes as well where now all of a sudden if you're reviewing code faster you need to design it quicker or you need to do the security scan that's faster. So we see the volume shift across the flow. And this is where it's really important that we have visibility into the process overall from a metric standpoint because as we start to supercharge and parallelize and add more efficiency to the process we start to develop more and more bottlenecks and so the operational visibility of the process is extremely important much more important than the authoring and the building of your workflow tool. So we want to visualize the process. So we want to add parallel capacity by still keeping the controls and so this is where we'll add more additional capacity.

Okay. So we're doing some work we're checking it we're using the feedback again to refine it until the work is good enough to move on. But why is that hard? It seems like a pretty easy thing to do. But as I mentioned before these graphs get actually pretty complex and we'll dive a little bit more into why this is difficult. And if you're familiar one challenge with AI engineering is the variability of inputs and outputs and I believe that higher quality inputs will result in better outputs at a lower compute cost. But what are quality inputs? So, we would generally speak to it as context model maybe. We can nitpick that, but this isn't our area of focus today. We're going to focus more on outputs. But, we can't really talk about quality of outputs without talking about the quality of inputs.

So, ideally we've established a trusted context for our agent. And there's some references on that, but one thing we can do in this model is inject the DAG state into our agent and let it know kind of where it fits into the bigger picture. Okay, so now we've added even long time horizon goals and that emphasizes the need to optimize the cost and efficiency of this loop. So, the check is where we decide whether the work is good enough to move forward. We need to define what good looks like. That's the hard part. And we need to have a reliable way to evaluate it. Otherwise, more passes don't necessarily mean better results. The loop is really only as trustworthy as the check.

So, if we want to talk about quality, let's talk about the check and let's talk about quality. Okay, I think building with AI is an opportunity to improve product quality overall. I like some of the conversation about durable software. So, I'm a believer in quality and in traditional software we built confidence mechanisms in place to give us confidence that the software is of high quality. And that's done with a variety of mechanisms, but primarily systematically with test cases, unit tests, checking these as a part of our delivery flow to ensure that when we make code changes, mistakes aren't made that break other things, right? So, this is a confidence mechanism that we've put in place with traditional software. The agents are probabilistic, and so the same request can produce different answers.
</details>

### 自主性跃升阶梯：从全面监督到无监督运行

在评估业务 DAG 的哪些节点适合引入智能体时，团队需要针对每个节点提出一系列系统性校验问题：该任务能否轻松依照合规策略进行验证？能否在受限循环中稳定运行？行为是否可追踪、可审计？在出现异常时能否平滑回退至人工干预？以商业贷款流程为例，客户身份识别（KYC）与财务数据分析往往能够高度并行化且易于验证，适合由智能体主导；而最终的放款决断（Decision）则直接映射到严格的制度策略，必须保留人类在环（Human-in-the-loop）决策。因此，工程考量不再是非此即彼的“是否引入 AI”，而是“预期何时让 AI 完全接管”。

这种从辅助到自主的过程需要经历系统性的**爬山算法演进**（Hill Climb），即三个阶段的信任跃升：

* **第一阶段：全量人工监督（Supervised）**。在初始部署期，领域业务专家（SME）全量人工核验智能体的每一项输出，共同确立“合格”的精确定义，并以此不断沉淀基准数据集、打磨评估与测试框架。
* **第二阶段：统计抽样与链路监控（Sampling）**。当系统度量出的置信度指标突破策略预设阈值后，过渡至抽样核查阶段。人类专家仅需审查特定比例的样本切片，而未抽样的大多数输出则依赖系统化的 Trace 链路与自动化 Evals 持续监控合规质量。
* **第三阶段：自主运行与异常兜底（Unsupervised / Autonomous）**。当置信度跨过严苛的安全门槛后，智能体将实现无人监督自主运行；人类角色则转变为处理未决的异常流情况，并持续作为参与者校准数据集，驱动底层系统不断迭代。

综上所述，将智能体成功嵌入强合规业务的核心准则是：**外层保持确定性，内层赋予自适应性**（Deterministic on the outside, adaptive on the inside）；通过系统评估与统计学证据建立正交的质量置信机制，而非盲目信任模型直觉；最终让 AI 工程师承担起连接业务信号与后方 MLOps 基础设施的重任，使智能体真正贯穿现代组织的运营全流程。

<details>
<summary>Original English Source</summary>

More than one answer may be acceptable. And we still need evidence, but exact output comparisons alone really aren't good enough. We need to build representative data sets and evaluate them and define what good looks like. We need to run these evaluations in repeated series, and this is a statistical analysis, right? Where we actually look at the outputs and in volume and not just as a direct comparison. So, in combining with evals is sort of your run time logs of what happened, or sorry, traces, which are sort of your run time logs of what happens. We've built this confidence mechanism to complement traditional software. And ultimately, this is what we're going to be talking about a little bit more in terms of driving confidence in the output, not only putting this mechanism in place, but how do we begin to turn it on?

So, where does the agent belong? Back to the lending example, like we can do KYC, financials in parallel and sequence like credit memo, risk review, documentation, decision, all these things in our DAG. Looking at each node, we want to ask some certain questions like how valuable would it be to have an agent drive this node versus a human drive this node? And we can sort of look at some of these basic questions like can we check it against the policy easily? Can it run in a bounded loop? Can we trace it? Can we fall back to a human? If we can answer yes to these type of questions, and we can kind of have a good idea going in that this particular node may be better suited for automation. But throughout the DAG, we should look to drive agent assistance. So, what we're really talking about is not whether or not AI is involved, but whether or not AI we expect to take over at some point. On the decision, you would probably agree that we probably need that to be human-driven. This is essentially the check against the policy. So, this is going to be a little bit more difficult, I think, to hill climb.

But what do we mean by hill climb? All right, how do we turn this on? So, day one, we start supervised and as we have agents and humans working together as a part of the process, we can manually verify the output to ensure that it is high quality. This is where we refine our data sets and ensure that we have the right confidence mechanisms in place. We've defined what good looks like with the domain subject matter experts and that they're beginning to verify it. When measured confidence reaches a policy threshold, we can move towards sampling. And what that means is humans are looking at a slice of the output and not necessarily all of it. We begin more systematic evaluation through traces in order to ensure that what the humans aren't seeing is still meeting the quality bar. And then finally, once we clear the confidence threshold, humans handle more of the exceptions of the process, but still acting as participants in refining the data sets and ensuring the quality outputs.

Okay, so a few takeaways from this. DAG and DCG, basic graph theory, but ultimately, how do we build these processes that exist today and where people are working them and bring agents into the mix. And the recipe really is to keep it deterministic on the outside and make it adaptive on the inside. The next is quality through evaluation. And this is really establishing a complementary confidence mechanism. So, it's not a feeling about a model. We can actually provide research and statistics about the quality of our agents. So, this builds confidence and inherently trusts output. Quality is a team sport. AI engineers own the pipeline to taking product signals from all directions and deliver applications that are well built and utilize ML operations behind the scenes. Finally, agents accelerate across the operating model. I've included some references on the final slide of things that I've spoken about today. This concludes my presentation. Thank you very much.
</details>