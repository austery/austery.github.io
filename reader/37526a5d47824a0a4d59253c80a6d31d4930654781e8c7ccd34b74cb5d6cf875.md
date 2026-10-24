---
author: AI Engineer
date: '2026-10-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mUQoVz7THu0
speaker: AI Engineer
tags:
  - agent-evals
  - observability
  - llm-evaluation
  - data-infrastructure
  - agent-quality
title: 构建AI Agent质量评估平台为何远比想象中复杂：Braintrust深度解析评测闭环与底层工程挑战
summary: 来自Braintrust的演讲者深度解析了构建AI Agent质量评估平台的核心难题。大模型的非确定性使评测与可观测性成为保障Agent可靠性的基石。文章梳理了评测工具从电子表格、定制UI到参数对比与双向数据飞轮的演进历程，剖析了高吞吐半结构化Trace存储、BTQL实时查询等底层系统工程挑战，并展望了AI编程Agent自主闭环评测与迭代的未来趋势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Braintrust
  - Salesforce
  - Databricks
products_models:
  - BTQL
media_books: []
status: evergreen
---
### 为什么构建AI Agent质量平台极其困难

**Speaker 1**: 感谢大家参加本场关于“为什么构建Agent质量平台极其困难”的主题分享。我是来自 **Braintrust** 的解决方案工程负责人，目前主管我们西部地区的团队。在加入Braintrust之前，我在 **Salesforce** 和 **Databricks** 累计度过了15年的解决方案架构与工程生涯。我一生都是个不折不扣的技术狂热者，五岁的时候就开始自己动手组装电脑了。正因为我对技术有着永不满足的渴望，这也顺理成章地让我来到了当前人工智能的最前沿领域，加入了Braintrust。

<details>
<summary>Original English</summary>

**Speaker 1**: thank you for joining this session on why building agent quality platforms is hard. My name, so saying, I lead the solution engineering organization on the west for Braintrust. Um I spent 15 years in solutions between Salesforce and Databricks. I've been a lifelong technologist. I built computers since I was five years old. So I have like an insatiable appetite for technology, which finds me kind of on the bleeding edge of AI here at Braintrust.

</details>

**Speaker 0**: 没有异议。

<details>
<summary>Original English</summary>

**Speaker 0**: 没有异议 for those of you.

</details>

**Speaker 1**: 我知道在座的各位中，刚才有些人参加了前一场会议。当时会场里有人举手讨论过关于Evals（评估）的话题。我想先做个现场调查：现场有多少人了解Braintrust？知道我们这家公司究竟是做什么业务的？请大家举个手示意一下。很好，我看到现场有一两位举手了。简单概括来说，**Braintrust** 是一个完全专注于 **Agent Quality（智能体质量）** 的平台。我们最核心的理念，就是帮助技术团队在交付和发布其AI功能或AI Agent时，能够建立起足够的信心并持续维持这种质量确定性。

<details>
<summary>Original English</summary>

**Speaker 1**: I know some of you were in the room earlier when just did her session. I saw some hands about evals. How many of you know what Braintrust is, and what we do as a company? Just show of hands. Perfect. I see one or two. So at a glance, Braintrust is a platform focused around agent quality, and the core idea is helping teams build and maintain confidence with the AI features or the AI agents that they are shipping.

</details>

### Agent质量的两大支柱：评测与可观测性

**Speaker 1**: 保障Agent质量有两大核心支柱：第一个支柱是 **Evals（评估评测）**，也就是我们前面提到的内容。Evals是指在你的Agent正式进入生产环境之前所必须进行的所有工作。在这个阶段，开发团队会进行充分的实验探索、测试Agent的具体行为表现，并建立起将系统推向生产环境之前所亟需的确定性与信心。第二个支柱则是 **Observability（可观测性）**。可观测性是在你的Agent已经部署上线到生产环境，并且正在与现实世界中的真实终端用户进行实时交互时所发挥作用的。它记录并生成所有的真实交互。此时的目标是：将你在离线开发流程中所建立起来的假设模型，通过生产环境下的持续监控与反馈进行验证和强化。Evals与可观测性本质上是紧密关联且服务于同一个核心问题的——一个发生在离线开发期，另一个发生在生产运行期，二者的共同目标都是为了深入理解并持续提升Agent的质量。

<details>
<summary>Original English</summary>

**Speaker 1**: And there are two key pillars of agent quality. The first is evals, which we talked about earlier. Evals is what you do before your agent reaches production. This is when teams experiment, they test the behavior, and they build the confidence that they want to have before they ship to production. The second pillar is observability. Observability is once your agent is in production and is interfacing with real life users. It's creating interactions. And the goal is to take that hypothesis that you built in your offline development process and then reinforce that in your production scenario through continuous monitoring. Evals and observability are closely related to the same problem. So one happens in production, the other one happens in development, and both is the understanding to improve agent quality.

</details>

**Speaker 1**: 现在我不会在这个概念上花太多时间。让我们直奔今天的主题。

<details>
<summary>Original English</summary>

**Speaker 1**: Now I won't spend much more time here. Let's talk about why we're here,

</details>

**Speaker 0**: 没有异议。

<details>
<summary>Original English</summary>

**Speaker 0**: which is 没有异议.

</details>

**Speaker 1**: 为什么Evals（评测）如此重要？大家知道，Evals至关重要，根本原因在于 **LLM（大语言模型）天生具有非确定性（Non-deterministic）**。它们的输出具有极高的变异性（Variability）。然而，恰恰正是这种不可预测的变异性，才赋予了它们如此强大的能力——它们可以跨越诸多截然不同的垂直领域进行逻辑推理，能够解决形态各异的复杂问题，并且能够处理来自用户的各种宽泛需求。但是，硬币的另一面是，正是这种极高的灵活性带来了巨大的工程与业务风险。如今各种Agent都把LLM作为其核心大脑，而且Agent交互体验正在迅速成为终端用户与企业产生连接的主流交互方式。因此，团队必须对他们的Agent建立起充足的信心，确保它们在运行中表现出高度的可靠性，并持续输出符合预期的确定结果。

<details>
<summary>Original English</summary>

**Speaker 1**: Why are evals important? You know, evals matter, because LLMs by nature are non-deterministic. They are highly variable. That variability is exactly what makes them so powerful. They can reason across many different domains. They can solve different kinds of problems, and they can handle a wide range of user needs, but that same flexibility also creates risk. But agents use LLM as their brain and agentic experiences are starting to become the primary way in which users will interact with companies. So teams need confidence in their agents that they will behave reliably and produce the outcomes that they expect.

</details>

**Speaker 1**: 如果没有科学严谨的Evals评估体系，企业将面临极具杀伤力的现实业务风险。如果Agent出现前后不一致的行为逻辑，**品牌声誉风险（Brand Risk）** 就会立刻显现；如果Agent说错了话或者执行了越权与错误的操作，就会面临极其严重的 **合规风险（Compliance Risk）**；如果底层系统过于黑盒、极度脆弱以至于根本无法排错调试与精确控制，更会引发巨大的 **成本与维护风险（Cost and Maintenance Risk）**。因此，做Evals的终极目标，就是在产品正式面向用户发布之前，尽可能消除这些不可控的不确定性，确保客户能够获得稳定优良的交互体验，并让Agent的行为始终保持在既定轨道之内。

<details>
<summary>Original English</summary>

**Speaker 1**: And without evals companies face real risks. Brands become a risk if there's inconsistent behaviors; compliance, if the agent says, or does the wrong thing; and there's a cost and maintenance risk if the systems are hard or unreliable to debug or control. The goal of evals is to reduce that uncertainty before launch, so that customers have a good experience, and the agents behave the way that you expect them to.

</details>

### 从电子表格起步：评测系统的初级形态与局限

**Speaker 1**: 听到这里，你可能会想：“好吧，Evals说到底不就是在电子表格上搭个UI界面吗？这有什么难的？”说到这里我想再调查一下：现场有多少同学曾经亲自跑过Evals评测，然后顺手把跑出来的结果一条条记录到Excel或Google Sheets电子表格里的？有这么干过的举个手看看？好，确实看到有一两位举手了。其实这完全没有什么好难为情的，相反，这通常是一个非常好的第一步。真正关键的地方在于，团队开始正视并承认这是一个实打实的业务挑战，大家需要一种手段来了解Agent面对不同的输入时究竟会产生怎样的输出。

<details>
<summary>Original English</summary>

**Speaker 1**: So you might be thinking, okay, well, evals is just a UI on a spreadsheet, right? And I guess I should not ask the audience just show of hands, how many of you have run evals and logged the results into a spreadsheet as that happened? Okay, I see one or two. So there's no shame in that. By the way, it's actually a good first step. The important thing is that teams acknowledge that this is a real problem, and they need a way to understand how agents behave based on different inputs.

</details>

**Speaker 1**: 在最简单的抽象层面上，一个评测系统通常具备三个基本要素：第一，有一套能够针对测试输入执行Agent逻辑的机制；第二，有一种查看输出结果或评分的方法，哪怕这些分数只是被手动写进电子表格；第三，准备一组测试输入示例或测试集，用于触发并驱动Agent运行。所谓测试输入，就是启动Agent端到端执行所需的上下文信息，它可以是一个Prompt提示词、一段用户请求文本，或是任何能促使Agent采取动作的数据输入。因此，基于电子表格来做Evals不仅没有错，它反而是大多数团队构建实用评测工作流的必经初始阶段。

<details>
<summary>Original English</summary>

**Speaker 1**: At the simplest level, an eval system stands against it has three different kind of criteria. It has a way to execute agents against test inputs. Second, a way to view the outputs or the scores, even if those are being logged in a spreadsheet. And third, a set of test inputs or examples that could invoke the agent. An input example is whatever information is needed to start the agent end-to-end. It could be a prompt, a request or text that causes the agent to act. Now spreadsheet-based evals are not wrong. However, they're often the first step for a useful version of eval workflow.

</details>

### 冰山之下：多角色协作与持续爬坡的复杂性

**Speaker 1**: 但是正如大家所能想象的那样，浮在水面上的这部分只不过是冰山一角。如果所谓的Evals仅仅只是“执行一下Agent、看一眼输出、然后在表格里打个分”，那我这场演讲现在就可以宣布结束了。但事实绝非如此，在水面之下、在系统底层，隐藏着极其庞大的工程体量。一个真正成熟的系统，背后需要无数跨职能团队共同配合：构建高质量的数据集、开发智能化的评分系统（Scoring Systems）、建立人工审核与标注机制、打造全链路的调试工具栈，以及最关键的——打通预发布测试与线上生产环境真实行为之间的双向连接。今天我们会触及其中一部分核心难题，任何未尽细节欢迎大家在会后直接找我交流。

<details>
<summary>Original English</summary>

**Speaker 1**: But of course, as you can imagine, there's more to the iceberg than just what we just talked about. And if evals were only, you know, run the agent, view the output and then score in a spreadsheet, this talk would be over right now. But there's a lot more that happens behind the scenes or underneath the iceberg. There are many supporting teams that eventually need to build better datasets, scoring systems, review processing, debugging tools and the way to connect pre-production testing with production behavior. We'll touch on some of these today. Anything I don't get to, feel free to come up afterwards, and we could chat about it.

</details>

**Speaker 1**: 而这正是整个体系变得无比棘手的开端。首先，底层的技术栈本身就极为复杂，LLM根本不是传统的确定性软件。其次，**Agent质量治理是一个多角色参与的协同问题（Multi-persona Problem）**。参与其中的绝不仅仅只有纯粹的软件工程师和AI算法工程师；还有产品经理（PM）——他们过去负责撰写PRD文档，现在则需要亲手运行Evals来校验业务逻辑；此外还有深谙垂直业务领域规则的业务专家（SMEs，领域专家）。不仅如此，Evals本身也绝非一次性的阶段性任务，而是贯穿了整个软件开发与线上运营完整生命周期的核心工作流。过去那种“写好代码、通过单元测试和回归测试、上线后就万事大吉”的软件开发模式已经彻底一去不复返了。在AI时代，Evals是你用来朝着唯一核心目标不断迭代、持续向上爬坡（**Hill Climbing**）的关键驱动力，而这个终极目标就是Agent的高质量。

<details>
<summary>Original English</summary>

**Speaker 1**: And this is where things start to get complicated. The underlying technology is complex. LLMs are not simply deterministic. Agent quality is a multi-persona problem. It's not just software engineers and AI engineers. There are PMs who used to build PRDs that are now running evals. There are SMEs who have the domain expertise of the product that you're building. And evals themselves are just one part of the development and operating workflow. And gone are the days where you build once with unit tests and regression tests, you ship to production and you don't think about it. Evals are a way for you to continue hill climbing against one target, which is agent quality.

</details>

### Agent质量飞轮：北极星指标与演进阶段

**Speaker 1**: 接下来，让我们梳理一下行业内Evals平台的演进阶段。在展开之前，我们先来看一下众多AI团队心目中的“北极星架构”，那就是打造一个闭环的 **自我改进飞轮（Improvement Loop / Flywheel）**：你在生产环境中上线了一个AI功能或Agent应用；系统能够根据你预先定义的维度，实时观察并捕获所有线上的失败模式（Failure Modes）；你能够一键抓取这些线上真实失败用例，直接将其转化为本地离线开发环境中的测试用例；随后在本地快速迭代修改，在不引入新的回归缺陷（Regressions）的前提下全面提升Agent的输出质量；最后再重新部署到生产环境中。这个循环需要持续不断地运转，因为就像经典机器学习领域面临的挑战一样，数据与模型漂移（Drift）在Agent系统中同样是不可避免的现实——用户与Agent交互的行为模式会随时间发生演变，你构建和迭代Agent代码的方式也会随时间不断变化。

<details>
<summary>Original English</summary>

**Speaker 1**: So let's talk about the different stages of the eval platforms that we see. And before we do that, this is the North Star for many teams. They want to build the improvement loop, which is: I have a feature or application in production. I could observe the failure modes that happen based on dimensions that I define. I want to be able to grab those failure modes and create test cases so that I can iterate offline, so I can improve my agent quality without introducing new regressions. And then you continue iterating over time, because just like in classical ML, drift becomes a real thing. The way users interact with your agents will change over time. The way you build your agents will change over time.

</details>

**Speaker 1**: 那么，**第一阶段（Phase 1）** 是什么样子的呢？前面会场里有几位同学举手提到过电子表格，再次强调，这完全没有什么好尴尬的，因为绝大多数团队都是从这个起点出发的。这种最基础的原型架构其实非常直观：它本质上就是一个简单的 `for` 循环，挂载一组输入样本，并提供一套能够调用并执行Agent的脚本。通过这种方式，你可以反复微调Prompt或逻辑，对同一批测试用例进行多次运行，并在表格中横向观察Agent在不同时间节点的输出演变。这种做法最大的优势在于极低的准入门槛与近乎为零的时间成本，基本上没有任何技术壁垒就可以快速起步。

<details>
<summary>Original English</summary>

**Speaker 1**: So what does phase one look like? There were some hands that were raised around spreadsheets, and there's nothing to be shameful about. This is where many people start. And the basic setup is pretty simple. It's a `for` loop with a set of input examples and a way to execute the agent. And with that, you can run the same examples that you tweak and see how the agent responds with the outputs over time. The biggest advantage is accessibility and time. You can start this with basically zero barrier to entry.

</details>

**Speaker 1**: 但是，这种初级方案的边际效用递减极其迅速。到了这个阶段，你基本上只是在被动地做记录归档而已，根本无法开展真正意义上的科学实验，更不用说去进行跨时间维度的深度对比与归因分析了。在这一阶段，最普遍的痛点包括：第一，数据统计与分析极其繁琐且难以自动化；第二，完全依赖人工手动打分，虽然这些人工反馈价值连城，但操作起来效率极低且不可扩展；第三，团队协同能力近乎为零，业务领域的专家（SMEs）通常被完全排除在这类测试流程之外，无法参与其中。所以总结来说，电子表格确实是一个绝佳的起跑点，但它很难再进一步演进升级。

<details>
<summary>Original English</summary>

**Speaker 1**: But the returns diminish pretty quickly at this stage. You're pretty much only documenting. You can't really do true experimentation, let alone do an in-kind type of analysis over time. Common limitations are analytics are hard; they're manual. Human scoring is valuable, but difficult to do. Collaboration is very weak, and domain experts are usually boxed out of these type of results. So again, spreadsheets are a great starting place, but difficult to evolve.

</details>

### 从定制UI到多版本并排对比：工作流的进阶与线上盲区

**Speaker 1**: 于是，通常会有一位产品工程师（Product Engineer）站出来，注意到了这个问题并心想：“好吧，我可以手写一个漂亮的定制化UI界面（Bespoke UI），专门来解决这个协同痛点。”乍一看，定制化界面的确能带来即时收益：它把之前无法参与流程的多角色顺利拉进了评测闭环中，产品经理现在能够直接登录这个专用界面参与日常的Evals运行。然而，正如你可能猜到的那样，其局限性依然无法根除：底层的文档沉淀、审核机制虽然在视觉上比表格更加规整，但跨团队协同依然严重受阻；尽管单次迭代周期有所缩短，但要让用户持久化保存这些历史版本数据，并跨越较长时间跨度进行深度指标分析，依然极其困难——归根结底，它本质上依然只是一个披着漂亮外皮的静态报表工具而已。

<details>
<summary>Original English</summary>

**Speaker 1**: Then someone, usually a product engineer, you know, they see this problem, and they think, okay, I can build a nice UI, a bespoke UI to help solve this problem. And while it might be nice at a glance, it helps you bring in the different personas that you'd otherwise not have access to. This allows PMs to now kind of get into the loop of doing evals. But the limitation that you might have thought about continues: that the documentation, the review process, though it might visually look nicer, still collaboration becomes difficult. And though iteration cycles become quicker, it is still not easy for users to persist that data and do long-horizon analytics on still just a reporting tool.

</details>

**Speaker 1**: 紧接着，评测平台演进到了下一个阶段。团队会提出新的诉求：“嘿，我希望能为非技术背景的同事提供一个不仅能查看打分日志、而且能直接上手做对照实验的交互界面。我想在上面直接调整System Prompt系统提示词；我想在下拉框里随手切换底层基座模型；我想自由调节各种参数取值并快速对比差异。”于是，支持不同模型与Prompt版本之间进行 **Side-by-side（并排对比）** 实验分析的能力，就成了评测演进脉络中的下一座里程碑。

<details>
<summary>Original English</summary>

**Speaker 1**: Then the next evolution becomes: "Hey, I want my non-technical users to have an interface where not only that they just log the results, but they should be able to experiment in it. I want to be able to tweak a system prompt. I want to change the underlying model. I want to iterate on some parameter values." So being able to do this type of side-by-side comparison becomes the next evolution of the eval cycle that we see.

</details>

**Speaker 1**: 但是，这种形态依然存在一个致命的核心缺陷：你在做所有并排对比实验时所依赖的测试用例，依然仅仅是一批人为挑选出来的、停留在离线开发环境中的静态测试集。那么，在真实的生产环境中究竟在发生什么？你在离线环境下做了极其详尽的Prompt调试与版本对比，你对Agent在离线场景下的预期胸有成竹。然而一旦你将其发布到线上生产环境，团队瞬间陷入了彻底的“盲飞”状态（Operating in the blind）——你根本不知道Agent在面对真实用户时一步步执行了哪些内部决策步骤，更无从获知在复杂的生产环境中，系统究竟在何时、何地、由于何种原因真正发生了静默失败。

<details>
<summary>Original English</summary>

**Speaker 1**: But there's still one primary gap. And that is that the test cases in which you use to do these kind of comparisons are still a curated set that arrives in your offline evals. But what happens in production? I've done my iterations here. I have a good idea of what I expect to happen in development. But once I ship to production, I'm operating in the blind. So I have no idea what steps my agent is taking. And when those failures are actually happening in my live environment.

</details>

### 构建完整的Agent飞轮：端到端追踪与闭环治理

**Speaker 1**: 重新回到我们刚才讨论的自我改进飞轮：到底什么样的系统架构才能真正跑通这个闭环？从最顶端开始梳理：首先，你必须具备捕获所有失败模式的端到端能力，记录每一个输入与输出，完整保留Agent在整个执行链路上采取的每一个中间步骤的 **Trace（追踪执行轨迹）**；其次，进行深度分析，精准定位到底哪一步出了差错；你要基于真实业务场景去定义成功的标准与失败的维度，因为只有你才真正理解自己的业务期望结果；紧接着，精准抓取线上这些真实的失败用例——也就是那些导致用户遭遇糟糕体验的实际现场，在离线评估流程中一键生成对应的全新测试用例；在离线环境下针对这些高价值测试集进行针对性调优与代码重构，在杜绝新引入回归错误的前提下完成能力迭代；最后再次推向生产环境，围绕Agent质量目标持续向上爬坡。

<details>
<summary>Original English</summary>

**Speaker 1**: And when we think kind of going back to the flywheel, when we think about what are the best systems that enable this? Well, you should be able to, starting at the top: observe the failure modes; log every input, output, every step of your trace execution that your agent takes; analyze, understand what went wrong. You create the dimensions of failure and success because you know the outcomes. Then grabbing those failure modes, those different scenarios where your users had poor interactions and creating evals from them in your offline process, iterating on them, so you can create the improvements without developing new regressions, and then shipping to production and hill climbing against this.

</details>

**Speaker 1**: 最终呈现出来的理想结果是：团队成功将这个涵盖离线与线上的自演进飞轮直接嵌入到了平台内核之中，实现了整个软件生命周期的无缝贯通。然而紧随而来的最大痛点在于：**这套复杂的系统必须由你自己全权承担维护成本**。你自己造的轮子，所有运维包袱和架构债都得自己背。在项目初期、在概念验证（POC）阶段或者只是写几个简单Demo演示的时候，自己手搭一套可能觉得轻而易举。但一旦进入真实的生产环境，**Agent Traces是非常可怕且棘手的（Agent traces are nasty）**。

<details>
<summary>Original English</summary>

**Speaker 1**: And when you think about the final outcome of this, well, you get teams building the flywheel. You get that entire development cycle inside of your platform. But then the problem becomes you have to maintain it. You own this product that you build. And especially this is easy to do when it comes to smaller scale or POC and demo environments. But agent traces are nasty.

</details>

### 底层系统级挑战：数据洪峰、BTQL与架构深水区

**Speaker 1**: 它们是深层嵌套的半结构化 JSON 数据。在很多极端案例中，我们看到一些客户的单次交互会话中记录的数据量简直就像一部完整的高清电影一样夸张——单次交互的Trace日志就可以膨胀到数百兆字节（Hundreds of megabytes）。面对这种量级与形态的数据，想要对其进行高效的动态分析和检索是极其艰难的，而传统建立在行存或标准列存上的云端数据仓库，往往会在这种特殊形态的洪峰冲击下直接崩溃瘫痪。

<details>
<summary>Original English</summary>

**Speaker 1**: They are semi-structured JSON. In some cases, we see teams that are logging a movie's type of data in each interaction, hundreds of megabytes. So being able to query that type of data can be difficult, and your typical cloud data warehouses kind of collapse under this type of volume.

</details>

**Speaker 1**: 这恰恰也是我们在构建底层架构时亲自踩过的深坑。虽然今天我不打算花过多篇幅去做Braintrust的产品推介，但核心逻辑是一致的：当海量的生产环境Trace数据实时涌入时，你必须具备在数据落地的瞬间即刻对其进行毫秒级低延迟查询的能力。因为如果线上真实用户正在遭遇极差的产品体验，作为架构师和开发者，你必须能够秒级感知现场：到底发生了什么？用户为什么会遭遇故障？怎样才能以最快的速度予以修复？与此同时，系统还必须能够兼顾超大跨度的长周期分析任务——比如提取数周数月的数据进行模型微调（Fine-tuning），或者让人工专家介入通过标注评判标准来进行RLHF对齐训练。这是两种在IO特征和计算密集度上完全不同、截然对立的计算负载（Workloads）。为此，我们专门自研了一套底层的领域特定查询语言与引擎，命名为 **BTQL（Braintrust Query Language）**。

<details>
<summary>Original English</summary>

**Speaker 1**: And this is the same problem that we ran into. I won't spend much time talking about Braintrust. But when you have production traces coming in, you want to be able to query that data in real time as it lands in there. Because if your users are having poor experiences, you want to be able to know in real time as it is happening: Why are they having these poor experiences? And how can I remedy that as soon as possible? You also want to be able to do long-running queries, if you think about being able to fine-tune your agent experience, or even have humans who are doing alignment by annotating your judges' outcomes—two different workloads. So we built an instrumentation layer called BTQL, which is another form of complexity, because you want an interface for people to be able to query that data.

</details>

**Speaker 1**: 由此可见，打造一个现代Evals平台，绝不仅仅只是画几个精美UI/UX前端界面的事情，**构建评测平台本质上是一个硬核的系统工程问题（Systems Problem）**。自几年前 ChatGPT 爆发并拉开大模型浪潮以来，一整套全新的系统级技术难题被推到了工程师面前：系统需要支撑极高吞吐的毫秒级实时数据摄入（Real-time ingest）；单次请求的Payload数据体量从几十兆到上百兆不等，而传统基于心跳探测的可观测性日志通常只有区区几个KB大小；数据的几何形态完全异构——深层嵌套、半结构化且混合了大规模长文本的内容，天生极度难以索引与高效检索；此外，底层的读写访问模式（Read/Write patterns）也存在巨大的内在冲突：你既需要在大规模冷热数据上执行高吞吐的批量聚合分析，又需要对特定微秒时间点上的深层调用树进行精准快照下钻。一个真正合格的基础设施，不仅要赋能一线的AI工程师，还要同时满足产品经理以及各垂直领域业务专家的全方位工作流诉求。

<details>
<summary>Original English</summary>

**Speaker 1**: So it's not necessarily that it's just a UI/UX problem, but building an eval platform truly becomes a systems problem. And there are novel set of issues when the ChatGPT boom happened a few years ago: where I need to do real-time ingest; I have huge payloads that are tens of megabytes, hundreds of megabytes in size, sometimes compared to traditional heartbeat observability, which are just kilobytes in size. The structure and the shape of the data is different. Having deeply nested semi-structured full text is difficult to query, and the read patterns are different as well. You want to be able to aggregate in large volumes, but also be able to do snapshots of in-time data. And building the right system should allow you to not only empower the AI engineer, but also the PMs as well as the SMEs.

</details>

### 未来的终局：Coding Agent自主评测与人类仲裁

**Speaker 1**: 最近我们观察到了一个极具启发性的最新演进趋势：**编码智能体（Coding Agents）正在成为这些评估平台的一等公民（First-class Citizen）**。开发者不再需要拘泥于复杂的GUI点击操作，而是可以通过自然语言以完全无头（Headless）的方式指挥你偏爱的AI编码助手：“帮我调取过去24小时内用户反馈不佳或遭遇异常的所有Trace调用链，基于这些失败场景自动帮我运行一组全新的Evals评测。”由于这些现代Coding Agent在权限上能够直接访问你底层的代码仓库、本地环境以及基础设施服务，它们顺理成章地成为了直接驱动评测运行、分析回归表现并持久化回写结果的主动执行载体。

<details>
<summary>Original English</summary>

**Speaker 1**: And more recently, we've seen that agents have become a first-class citizen of these eval platforms, where you want to be able to use natural language and a headless experience, where you can tell your coding agent of choice: "Find me all traces in the last 24 hours where the user had a poor experience, and run the evals for me." And because these coding agents have access to all of your underlying infrastructure in your codebase, they become the mechanism to run the evals and log those results.

</details>

**Speaker 1**: 那么，为什么这种自动化架构演进如此关键？大家回想一下，我前面介绍的所有传统评估环节，无论是写测试例、打分还是分析Trace，都需要人类工程师和产品经理深度浸泡在巨细靡遗的琐碎细节中，这在实际工程落地中往往极其繁重且耗时耗力。在Braintrust，我们的核心思考是：帮助企业实现大规模的自动化工程运营，而不是逼着人类团队每天疲于奔命去人工定义每一个极其微小的Agent成败判定维度。Braintrust能够自动从海量底层Trace中挖掘高价值的洞察结论，我们在后台自动对这些追踪数据执行推理计算，主动揭示那些你甚至“不知道自己不知道”的潜在盲区（**Unknown Unknowns**）——比如在哪些边界条件下Agent正在发生难以被传统监控捕获的静默崩溃？又或者在哪些真实交互场景下，用户因为Agent答非所问而不得不使用相同的提示词反复重试、产生极大的挫败感？

<details>
<summary>Original English</summary>

**Speaker 1**: And then it becomes a question of like, so why is this important? Well, the goal is: everything that I've shown you so far, it requires the humans, the engineer, the PM to be deeply involved in this process, and it could be laborious at times. At Braintrust, the way we think about this is we want to help you operate at scale, rather than you having to think about these dimensions of success and failure for your AI agent. Braintrust can surface these insights automatically because we log your tracing data into our platform. We can run inference on them, and we can tell you the unknown unknowns: "Hey, what are scenarios when my agent is failing silently?" or "What are scenarios where my users are experiencing frustration by prompting my agent for the same request over and over again?"

</details>

**Speaker 1**: 除此之外，还有太多底层工程细节今天由于时间关系无法一一展开：比如支撑上述能力所必需的定制底层高性能数据库架构；为了保障企业级安全性而必须内建的严密基于角色的权限访问控制（**RBAC**）；以及针对敏感生产数据的动态脱敏遮蔽机制（Data Masking）。平台内建的每一项核心功能，都在用严酷的事实证明：**这绝不是在电子表格上方套一个UI外壳就能解决的问题，而是一套极其庞大深奥的分布式系统工程挑战**。

<details>
<summary>Original English</summary>

**Speaker 1**: And it's a lot of things that we didn't talk about: things like the underlying database that powers it, having to build RBAC into the system to manage controls and permissions, or data masking. You know, each one of these features proves that this isn't just a UI on a spreadsheet, but rather it is a systems problem that powers it.

</details>

**Speaker 1**: 展望自我改进闭环的终局演进形态，正如我此前强调的，早期是纯靠人类肉身在拉动整个反馈循环；而今天，我们已经清晰地看到Coding Agent能够全自动介入这个飞轮，自主针对代码和Prompt做出增量修改，并为开发者主动给出系统调优建议。在这一全新范式下，人类工程师的核心职责最终升华为高维度的架构决策者与审核把关人（Human-in-the-loop Reviewer）——当AI编码助手为你自动生成了多个并行迭代的评测版本时，你只需要审阅各个版本在指标看板上的最终对比表现，拍板决定哪一个版本最安全、最优秀，然后一键将其部署到生产环境中。这就是我今天想要分享的全部内容。非常感谢各位莅临现场，与我们一起探讨构建Agent评估平台背后的挑战。谢谢大家！

<details>
<summary>Original English</summary>

**Speaker 1**: And as we think about the evolution of the improvement loop, I said this earlier, where humans were doing the improvement loop, and now we see coding agents where they could iteratively make changes and suggest what kind of improvements you should be making to your application. And ultimately, the human's responsibility is to review the outcome. If I have different iterations of these evals that are run by my coding agent, I can look at the outcome and make the decision of which version of it is the best for what I want to ship to production. So that is the end of my talk. I appreciate you all coming out and learning about why it's hard to build eval systems.

</details>

**Speaker 0**: 谢谢。

<details>
<summary>Original English</summary>

**Speaker 0**: Thank you.

</details>

**Speaker 0**: 好。

<details>
<summary>Original English</summary>

**Speaker 0**: 好。

</details>