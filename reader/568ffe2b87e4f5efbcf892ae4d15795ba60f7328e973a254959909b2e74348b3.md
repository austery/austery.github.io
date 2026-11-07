---
author: AI Engineer
date: '2026-07-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3z2uT5aDx_Y
speaker: AI Engineer
tags:
  - agent-evaluation
  - llm-as-a-judge
  - user-simulation
  - error-analysis
  - eval-harness
title: 构建切实有效的 AI Agent 评估体系：Lyft 客服大模型系统的演进与实践
summary: 本文深入整理了 Lyft 在构建客服 AI Agent 系统过程中的评估体系演进。详细阐述了离线模拟器与在线评估的双阶段架构，分析了评估失败的核心原因，提出了微调用户模型以模拟真实非理性用户、将 LLM 评判器作为分类器进行精度校验以及建立持续错误分析闭环等核心实践，为企业级 Agent 的落地提供了系统化的方法论。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Lyft
  - Sierra AI
  - Microsoft
products_models:
  - LangGraph
  - DeepEval
  - Langsmith
  - Langfuse
media_books: []
status: evergreen
---
### 自我介绍与分享背景

**Nick**: 大家好。我是 **Nick**，今天我和 **Ash** 一起在这里为大家带来关于**评估（evals）**的演讲。我们来自 **Lyft**，过去一两年我们一直在构建 Lyft 的**客服 AI Agent**，并在如何建立切实有效的评估体系以及扩展多 Agent 系统方面进行了大量的思考。首先做一个简短的自我介绍。我叫 Nick，是一名数据科学经理。我在 Lyft 工作了六年，算是一个老 Lyft 人了。非常高兴能在这里与大家深入探讨评估。

<details>
<summary>Original English</summary>

**Nick**: Hi everyone. My name is Nick and I'm here with Ashe to give a talk about evals. We are from Lyft and we've been building Lyft customer support AI agents for a year or two now, and we've given a lot of thought to how to build evals that actually matter and scale our multi-AI agent system. Just a little bit of quick introductions. My name is Nick. I'm a data science manager. I've been at Lyft for six years, a long time lifter. Really excited to talk to you a little bit more about evals.

</details>

**Ash**: 大家好。我是 **Ash**。我在 Nick 的团队，我们一直在一起开发 Lyft 的客服 Agent，致力于提升系统的**鲁棒性**、改进评估方法等工作。我在 Lyft 工作了快四年，非常高兴能来到这里，和大家交流如何构建切实有效的评估。

<details>
<summary>Original English</summary>

**Ash**: Hi everyone. I'm Ash. I'm in Nick's team and we've been working together on customer support agents for Lyft, improving the robustness, improving the evals, things like that. I've been at Lyft for almost four years now and very excited to be here and talk about building evals that actually matter.

</details>

### 评估系统的双阶段架构

**Nick**: 非常高兴能来到这里，也很荣幸能够参加 **AI Engineer World Fair** 的线上分享。让我们直接进入正题。今天我们的演讲将主要聚焦于评估。我们首先会分享我们对于构建客服 AI Agent 系统**端到端评估管线（end-to-end pipeline）**的整体思考。随着讨论的深入，我们将对每个组件进行更深入的探讨。我们将从离线评估、在线评估、评估套件（eval harness）以及我们未来的建设规划展开。

好，我们先从宏观层面解释一下我们是如何思考 AI Agent 评估体系的。如你所见，我们的评估分为**开发阶段（development phase）**和**生产阶段（production phase）**。在开发阶段，如果你在构建 Agent，你一定非常熟悉如何管理上下文、构建 RAG 管道以赋予 Agent 知识背景、定义工具、构建 Agent 图（agentic graph）以及编写系统提示词（system prompt）。当这一系列 Agent 工程开发流程完成后，你就拥有了一个 AI Agent。

我们的核心观点是，在将这个 AI Agent 推向生产环境之前，我们必须进行严格的**离线评估（offline evaluation）**，以确保它在面对真实用户之前已经具备了足够的性能。我们团队拥有丰富的数据科学和机器学习背景，构建机器学习模型已经有很多年了。我认为，Agent 的开发过程与传统机器学习模型的构建非常相似。既然传统机器学习模型在上线前都需要运行离线评估，那么对于 AI Agent 以及任何其他 Agent 平台或应用，我们也应该采取相同的标准。

然而，我认为 AI Agent 的离线评估与传统机器学习模型存在很大的不同。传统模型通常是单次预测，而我们针对客服场景构建的 Agent 是**多轮对话（multi-turn）**的。因此，离线评估必须包含**模拟对话（simulated conversations）**的组件。通常，你需要拥有一个能够代表真实生产流量的**合成数据集（synthetic dataset）**。然后，使用一个用户大模型（User LLM）来扮演用户，与 Agent 进行完整的多轮模拟对话。同时，还需要一个**大模型评判器（LLM as a judge）**作为评分员，来评估每次交互的质量。最后，我们需要设立一个**发布门槛（launch gate）**。我们要在离线评估中制定某些具体的指标标准，并确保在决定将 AI Agent 推向生产环境之前，系统能够达到这些标准。

这里的核心原则是，**我们绝不能把真实线上用户当成 AI Agent 的测试数据**。在任何情况下，这都是非常糟糕的实践。因此，我们必须强调建立健全评估流程的重要性。

一旦 Agent 成功上线，我们同样也有一套**在线评估（online evaluation）**管线。我们使用我们喜爱的**链路追踪工具（tracing tools）**来追踪 AI Agent 在生产环境中响应真实用户时的每一次执行过程和上下文。我们也有在线评分器（online grader）来评估 Agent 在生产环境中的实际表现。此外，我们还引入了**人机协同（human-in-the-loop）**管线来进行错误分析，识别失效模式，并将这些洞察反馈给开发团队，从而持续优化和迭代我们的 AI Agent。

<details>
<summary>Original English</summary>

**Nick**: Super excited to be here and super honored to be on the online track for the AI Engineer World Fair. Yeah, and let's dive in. For the agenda of today, our talk will primarily focus on evals. We will start by sharing how we think about the end-to-end pipeline for our evaluations for building a customer support AI agent system. We will go into a deep dive into each component more deeply as we go. We will start by talking about offline evaluations, online evaluations, eval harness, as well as what we are planning to build going forward.

All right, let's dive in. I want to quickly explain the high-level system of how we think about the evaluation system for AI agents. So here you can see we have the development phase and the production phase. During development, if you are building agents, you should be very familiar with managing context, building RAG pipelines to give your agents business context, defining your tools, building your agentic graph, as well as writing a system prompt. Once all of that agent engineering process is done, you have an AI agent. The way we think about this is before we launch this AI agent to production, we want to go through a rigorous offline evaluation process to make sure that this agent actually has sufficient performance before we launch this to live users. Coming from a data science and machine learning background, we've been building machine learning models for a while, and I think the way that we think about agent development is very similar to building machine learning models as well. If we are running offline evaluations for our machine learning models before they go to production, I think we should do the same for AI agents as well or any other agentic platforms and applications.

But how I think offline evaluation is different than traditional machine learning models is that typically, we're building specifically for the customer support AI use case, and we are building an agent that is multi-turn. So for offline evaluation, there will be a component of simulated conversations. You typically want to have a synthetic dataset that is representative of your production traffic, use an LLM that plays out the complete multi-turn simulated conversation, as well as have a grader such as an LLM as a judge to evaluate how good that interaction was. Then we have a launch gate, right? We want to make sure that we have certain criteria on our offline eval and we are meeting that criteria before we decide to launch this AI agent to production.

The real imperative here really is that we don't want to use our live users as test data for our AI agents. In any case, that is not good practice. So we really want to emphasize the importance of having an evaluation process. Once the agent hits production, we also have an online evaluation pipeline as well. We have our tracing tools to trace all the executions and context that the AI agent uses to respond to a real user in the production environment. We have our online grader as well that grades how well our AI agent is doing in production, as well as having a human-in-the-loop pipeline to do error analysis, identify failure modes, and feed those insights back to the development teams to continuously improve our AI agents.

</details>

### 评估失败的三大核心原因

**Nick**: 我想快速梳理一下为什么很多团队在做评估时通常会失败，我们总结了三个最常见的原因。

第一个原因是**评分没有真正起到拦截作用（not meaningfully gating anything）**。正如我前文强调的，我们需要一个发布门槛。如果你的大模型评判器只是悬浮在流程之外，仅仅产生一个分数，但没有人在开发或生产部署中真正使用这个分数作为拦截闸口，那么这个评判器就是摆设，毫无价值。

第二个原因是**评判器噪声过大且过于泛化（noisy and too generic）**。我们在构建大模型评判器时见过很多踩坑的经历。关于如何创建一个好的大模型评判器，行业里有很多不同的观点。不幸的是，在我们探索的早期，我们创建的评判器非常嘈杂且过于通用。它只会给出一个分数，但大家根本不相信这个分数，或者觉得评判器给出的洞察完全无法指导实际的改进。

第三个原因则是**缺乏线上退化（regression）的拦截与责任人机制**。当线上系统发生性能退化时，我们必须有清晰机制去捕获这种退化，并且必须明确责任人（clear owners），以便对评分器和回归拦截门槛输出的分析洞察及时采取纠正行动。

<details>
<summary>Original English</summary>

**Nick**: I want to quickly go over three of the most common reasons why we think evaluations typically fail for different teams. The first reason is that the grader we create and the scores we generate need to be meaningfully gating something. This is what we really emphasized on the previous slide—we need to have a launch gate. If your LLM as a judge is just floating out there generating a score, but no one is really using that score as a meaningful gate for your development and production environment, then that LLM as a judge is not useful. We have also seen a lot of mishaps when people are creating their LLM judge. There are a lot of different opinions out there on how to create a good LLM judge, and unfortunately, early on in our journey, the LLM judge we created was very noisy and too generic. It would output a score, but people didn't really believe in it, or they didn't think the insights were actionable. Finally, when something regresses in production, we need to have a clear mechanism to catch that regression and identify clear owners to take actions based on the insights of our graders and regression gates.

</details>

### 基于 Taobench 的模拟器

**Nick**: 非常酷。接下来我想切入并详细探讨我们的离线评估系统。正如我前面提到的，我认为这是从开发周期走向生产环境中最关键的一环。我们迫切需要一个鲁棒的离线评估系统，以便对即将发布到生产环境中的 AI Agent 拥有足够的信心。

在这项工作中，我们深受 **Sierra AI** 团队发表的名为 **TaoBench** 的学术论文的启发。虽然这篇论文主要针对客服 AI Agent，但我们认为它同样适用于任何面向用户的 Agent 应用。

如你所见，这是一种离线模拟架构。在这里，AI Agent 与一个模拟用户大模型（User LLM）进行交互，共同生成多轮对话轨迹。同时，我们拥有 **Agent 领域策略（agent domain policy）**，这本质上就是针对每个客服使用场景的指令策略，规定了如何处理各种不同的客户支持问题。

受 TaoBench 的启发，我们在构建离线模拟器时采用了如下的设计。我们基于 **LangGraph** 构建了 Agent，并为用户模拟器定义了相关指令。在模拟过程中，我们会定义用户意图（user intent）以及该意图所代表的具体业务含义；我们还会定义用户数据点或用户的“世界状态”（world state）。例如，接入客服的可能是一位豪华车司机，他已经为我们平台服务了好几年，诸如此类。最后，为了模拟我们在 Lyft 真实场景中会遇到的各种用户行为和性格特征，我们还为用户定义了不同的用户画像（user personas）。例如，一个画像可能是一个忠诚度很高的 Lyft 老用户，但他此时由于 Lyft 收入结算系统的故障而感到非常愤怒。

因此，在离线模拟器中，我们的 LangGraph Agent 与这个扮演用户的大模型进行交互，生成多轮交互轨迹。同时，我们构建了离线评分器。其中，大模型评判器是关键的核心组件，稍后我们将深入探讨如何构建一个优秀的大模型评判器。

除了大模型评判器之外，我们还构建了更为确定的**确定性评估器（deterministic evaluators）**，其形式非常类似于传统单元测试中的代码断言（code assertions）。例如，我们设计的一些确定性评估规则如下：如果在特定的交互中，AI Agent 应该向用户发放补偿金（concession），我们会编写一条规则，自动检测 AI Agent 是否确实调用了发放补偿金的工具；同时我们会比对 Agent 的工具调用记录与预期结果，从而衡量 Agent 对指令遵循的准确度。

<details>
<summary>Original English</summary>

**Nick**: Very cool. I want to transition to talking about our offline evaluation system. As I touched on earlier, this is the most critical piece going from the development cycle to production. We want to have a robust offline evaluation system to gain confidence in the AI agents we ship to production. We took a lot of inspiration from the paper called TaoBench, developed by the wonderful people at Sierra AI. This is specifically for customer support AI agents, but we think it is applicable for any user-facing agentic applications. Here, you can see this is an offline simulation where you have the AI agent and a user LLM interacting with each other to produce multi-turn traces. You have the agent domain policy, which is essentially the instructions/policies on how to handle different customer support issues.

Taking inspiration from TaoBench, this is the high-level approach we have for creating our offline simulator. As we mentioned earlier, we have our LangGraph agents, and we have defined instructions for our user LLM. For the simulation, we define the user intent, what this intent is supposed to represent, and the user data points or the world state of our user. For example, the driver coming to us might be a luxury driver who has been driving for us for a couple of years. Finally, to define user behavior and personas as we see with real Lyft users, we created these different personas. One example is a loyal longtime Lyft customer who is frustrated with the Lyft earning system.

So in our offline simulator, we have this LangGraph agent interacting with our user LLM and generating these multi-turn trajectories. We also built our offline grader/evaluator, where the LLM judge is a major component. We will dive a lot deeper into how to build a great LLM judge. Apart from the LLM judge, we also have deterministic evaluators, which usually look like code assertions in traditional unit tests. For example, some deterministic criteria look like this: if in a specific interaction, the AI agent is supposed to grant a concession, we write a rule checking whether the agent indeed granted a concession. We compare the agent's tool calls with the expected outcome to measure the accuracy of the agent's instruction-following behavior.

</details>

### 微调用户模型与画像定义

**Nick**: 在运行离线评估时，我们遇到的一个重大陷阱是**合成数据（synthetic data）的构建**。如何确保离线数据集能够代表真实的生产环境流量，是一个核心挑战。理想情况下，你绝对不应该只去写一段提示词让大模型简单地为你生成 50 个测试查询。这里有一些建议，可以帮助你用更切合实际的方式来拼装和构建一个贴近生产环境的数据集。

首先，我们会从真实的生产数据中抽取样本。Lyft 的用户长期以来都会联系客服，我们抽样了真实的线上客服交互案例，用来充实和补充离线评估数据集。其次，我们对离线数据集中的各种评估维度和关键条件进行**变异（mutation）**，以确保覆盖各种最佳业务路径（golden path）以及各种边缘案例（edge cases）。

然而，在构建离线模拟器时，我们遇到了另一个巨大问题：最初我们直接使用商用的最强前沿模型（frontier models）来扮演离线评估中的 Lyft 用户。但大家知道，这些最前沿的大模型在训练时都被对齐成了“乐于助人的 AI 助手”，而不是一个可能“没那么礼貌”的真实 Lyft 用户。经历过客服工作的人都知道，用户联系客服时的语气和措辞通常不会太客气。在第一版离线评估中，我们发现模拟用户表现得**太有礼貌、太有耐心**了。它们会非常详细、非常温和、不厌其烦地解释生产环境中遇到的问题。这导致我们第一版离线评估的通过率或准确率高达 90%。这显然好得令人难以置信，实际上也确实不符合现实。

真实的生产环境中，用户往往是不耐烦的、充满挫败感的，措辞非常直接，根本不会像普通大模型那样长篇大论、条理清晰地倾诉。这种真实的语境实际上让 AI Agent 的评估变得困难得多。

面对这种情况，我们该怎么做？如何让扮演用户的模型能更逼真地模拟真实的 Lyft 用户？
我们的解决方案是：**使用真实的 Lyft 用户原话语料（verbatim）对用户大模型进行微调（fine-tuning）**。通过微调，我们的模拟用户不再温和冗长地阐明问题，而是生成与真实不耐烦用户极度相似的短句。结果显而易见，使用这个微调后的用户模型后，我们的 Agent 评估得分大幅下降，评估难度显著上升。但这正是构建用户模拟器时你所期望看到的结果！如果你的评估体系太容易通过，它就无法提供关于 AI Agent 线上表现的任何真实洞察。而且，较难的评估环境能为你调整和优化 Agent 应对“难缠用户”提供更大的空间。

此外，我们还做了一系列工作来定义具体的 **Lyft 用户画像（user personas）**。这能让用户模型采纳特定的用户人设，从而更逼真地模拟现实。我们定义的画像包括：
* **越权（bypasser）用户**：完全不在乎 AI 说了什么，只想着立刻转接人工客服；
* **退款诉求（refund seeker）用户**：只关心退款，态度强硬；
* **AI 怀疑论者（AI skeptics）**：对机器客服天然不信任。

在这方面，我们受到了**微软（Microsoft）关于 UserLLM 论文**的启发。他们也采用了非常类似的方法，通过微调用户模型，使得评估得分降低，但实战效果却大大提升。在实际应用中，这正是最健康、最符合预期的走向。

<details>
<summary>Original English</summary>

**Nick**: One of the big gotchas we face with offline evaluation is that creating synthetic data is a key challenge in making sure our offline dataset is representative of production data. Ideally, what you don't want to be doing is simply prompting an LLM to generate 50 different test queries for your offline dataset. Here are a couple of suggestions on how you can approach this more realistically and assemble a dataset that closely resembles your production data. We take samples from our production data. Lyft users have been reaching out to support for a long time, so we take a sample of real production corpus and supplement our offline dataset with that. Second, we mutate different criteria from our offline datasets to cover different golden paths and edge cases.

One problem with our offline evaluator was that, as mentioned, if you are simply sampling 50 test queries from an LLM, another big gotcha was using a frontier lab LLM model to roleplay Lyft users. For the most part, frontier models are trained to be helpful assistants rather than a Lyft user who might not sound very nice. For everyone who has tried customer support before, you don't typically reach out with a very nice tone. In our first pass of offline evaluation, we noticed that our LLM user sounded almost too nice. As you can see on the right, these verbatims show the LLM user very patiently explaining the issues. Our first attempt at offline evaluation gave us a 90% pass rate. This was too good to be true. In reality, real user verbatims are different. Most users are impatient and frustrated; they don't want to explain their issues like an LLM. This is what we typically see in production, which makes the AI agent much more difficult to evaluate.

So what can we do to make sure our user LLM simulates real-life Lyft users closely? We fine-tuned an LLM model with real Lyft user verbatims. Instead of speaking in a verbose and polite way, our LLM user will produce verbatims that resemble real users closely. While we did see our evaluation score go down after fine-tuning this model (making the evaluation harder), this is exactly what you want when building a user simulator. If you have an eval that is too easy, it doesn't give you real production insights. This also gives you room to tweak your AI agents to deal with "difficult" users. We also defined Lyft user personas to ground the LLM user to adopt specific personas—such as bypassers who just want to escalate immediately, refund seekers, and AI skeptics. We took inspiration from Microsoft's paper on UserLLM, which adopts a very similar approach where they fine-tune a user LLM and see evaluation scores go down, which is expected and beneficial.

</details>

**Nick**: 好的，接下来我把麦克风递给 Ash，让他为我们详细聊聊大模型评判器（LLM judge）。

<details>
<summary>Original English</summary>

**Nick**: All right, I'll hand it off to Ash to talk more about the LLM judge.

</details>

### 预置评估指标的局限性

**Ash**: 好的，谢谢 Nick。大家好，接下来由我来分享。我将探讨我们在使用大模型作为评判器（LLM as a judge）进行评估时经常遇到的第二个问题。如你所见，目前几乎所有人都在使用大模型评判器来评估他们的 Agent。根据不同的使用场景，侧重点可能会有所不同。有些团队更关注安全性，有些更关注成本和延迟，还有一些则侧重于服务质量。但多多少少大家都会测量类似的指标：我们想要检测信息泄露、识别安全隐患等。其中，部分确定性的内容可以通过代码断言来评估，而那些非确定性的内容则需要交由大模型来评判。

然而，这种方法的硬伤在于**这些指标过于通用且无法指导行动（too generic and not actionable）**。以我们的评估历程为例，我们最开始也尝试使用来自 **DeepEval** 等现成工具的预置指标，比如测量工具使用率、回复得体度、回复帮助度、对话自然度、信息完整度等。我们确实得到了这些评分，但问题是这些指标无法转化为实际优化行动。如果系统的“回复帮助度”评分是 0.5，那我们到底该从哪里下手去修复它呢？

诸如毒性评分、偏见、公平性、简洁度等指标固然有其相关性，但如果评估结果仅仅是一个个冰冷的分数，我们根本不知道下一步该怎么做。因此，我们可以将这些现成的预置指标作为评测基线（baseline），但绝对不要把它们当成核心评估指标。因为我们希望评估指标是高度可执行的，并且要与我们的实际业务结果或所关注的产品指标深度挂钩。

<details>
<summary>Original English</summary>

**Ash**: All right. Hi everyone. So, I'm going to take it from here. I'll talk about the second problem which we usually face when we are doing eval with LLM as a judge. Here you can see this is how pretty much everyone is using LLM as a judge to evaluate their agents. The focus can be slightly different based on the use case. Someone can focus more on safety. Someone can focus more on cost and latency. Someone can focus more on quality. But people are going to measure these sort of metrics more or less. We want to detect leaks, we want to detect safety issues, and things like that. So some parts are deterministic which can be evaluated by code and some are not which are evaluated by the LLM.

Now the problem with this approach is that these metrics are too generic and not actionable. For example, we also started our eval journey using pre-built metrics from DeepEval, which were measuring tool usage, appropriateness, response helpfulness, conversation naturalness, completeness, and things like that. We did see those metrics, but the problem was these metrics were not actionable. They were not giving us any actionable insights. If let's say response helpfulness is 0.5, then what do we do with it? Scores like toxicity score, bias, fairness, conciseness—all these are relevant. But if the metrics are just scores, we don't know what to do with them. We can use these pre-built eval metrics as a baseline, but we shouldn't use them as our core eval metrics because we want eval metrics to be actionable and tied to the business outcome or the product we are focusing on.

</details>

### 构建可执行的业务指标

**Ash**: 那么，一个真正合格的大模型评判器应该是什么样的？
我们的实践是**与领域业务专家（domain experts）密切合作，充分吸纳他们的专业见解**。评估应该紧密围绕“任务是否成功”这一核心，并采用**二分类（binary outcome，即 Pass/Fail）**的结果形式。二分类结果非常容易进行标定和校准，也便于训练和提示大模型评判器，使其能够稳定一致地对 Agent 的多轮对话轨迹进行评分。当我们将领域专家与数据科学家紧密结合，共同打造与业务目标一致的可执行指标时，我们会看到更加有意义且极具指导作用的评估结果。这不仅提高了评分的一致性，而且一旦 Agent 在交互中失败，我们就能系统化地分析错误模式（error pattern），并明确知道应该如何调整代码或提示词来修复它。

这里有一个我们在实际业务中使用的可执行指标示例，我们称之为**“用户教育准则”（education rubric）**。在这项指标中，我们清晰定义了该指标的含义，并为大模型评判器制定了极其明确的 Pass/Fail 判定标准。例如，如果 AI Agent 尝试说服或教育用户的次数过多，而此时本应该直接将问题升级转接给人工客服，这就会被归为失败类别；或者相反，如果 Agent 还没来得及对用户进行必要的引导和教育，就过快地转接了人工，这也属于失败。我们将这些判定为 Fail。而只有在完全符合预期逻辑的节点进行适度引导时，才判定为 Pass。

<details>
<summary>Original English</summary>

**Ash**: Okay. So what should LLM as a judge be? We collaborate very closely with domain experts and utilize their insights. Evals should be framed around a task success or failure, and a binary outcome is very easy to calibrate and train LLM judges that can consistently score your agentic trajectory. When we partner with domain experts and data scientists to build metrics that are actionable and aligned with business goals, we can see much more meaningful results and actionable insights. Not only is this more consistent, but when an agent fails an interaction, we can systematically analyze the error pattern and actually know what we can do to fix this. Here is an example of an actionable metric for our use case which is called the education rubric. Here we define the metric how it should be and we define success and fail criteria for the LLM judge. For example, the AI agent tries too many times to educate the user when it could have escalated the issue, or if it is escalating too soon without giving any chance to educate the user. Things like that come under the failure category. So we mark this as fail. But if it is the expected behavior, we mark it as pass.

</details>

### 将评估器视作分类器验证

**Ash**: 那么，我们该如何验证我们的大模型评判器是否如预期般可靠地工作呢？
首要原则是：**将其视为传统机器学习中的分类器（classifier）**。正如我们在传统机器学习中评估分类模型一样，我们的大模型评判器输出的是二分类的 Pass/Fail 结果，完全可以套用相同的验证逻辑。一旦我们针对各项业务目标和功能需求制定了二分类指标，我们就可以手动标注大约 100 个对话样本作为黄金标准（ground truth），然后将这些数据切分为训练集（train）、开发集（dev）和验证/测试集（test/validation），这与机器学习的常规操作如出一辙。接着，通过比对人类标注的真实标签，计算出大模型评判器的**精确率（Precision）**和**召回率（Recall）**，从而得到关于评判器性能的真实报告。

具体的数据切分和指标计算逻辑是这样的：我们切分数据的方法类似于训练机器学习模型，但不同之处在于切分比例和使用目的。因为在这里，我们并不是真的在训练模型权重，而是利用这些数据来优化评判器的 Prompt。所以，比例会有所不同。例如，在“训练集”中，我们抽取少量样本作为评判器 Prompt 中的 Few-shot 示例；接着，我们在“开发集”上运行评估并迭代 Prompt，以调优 Prompt 的表现；最后，我们在“测试集”上进行最终验证，以确保我们没有对开发集样本产生过拟合。这是非常实用的落地方法，通过计算精确率和召回率，能让你确切知道评判器本身是否足够靠谱。

<details>
<summary>Original English</summary>

**Ash**: Okay. With this, how do we validate if our LLM judge is working as expected? First, we need to treat it as a classifier. How we train our classification models in traditional machine learning, we can also treat our evaluation judges as those traditional ML classifiers with binary outputs. Once we have binary outputs for every metric or task based on our business goals and functional requirements, we can hand-label around 100 examples with pass/fail labels and then split the data into train, dev, and validation sets like how we used to do with machine learning models. Then we score precision and recall for our judge based on human-labeled ground truths, which will give us an actual report on how good our judge is performing.

And how do we split our data to calculate precision and recall? We split the data similar to how we used to do in training machine learning models, but the difference is the percentage of splits. Here we are not actually training model weights. We are just using the data to inform the judge's prompt. So the percentages are a little bit different. For example, in training data, we pick a few-shot examples from this set for the judge's prompt, and then we iterate the prompt against the dev set and improve our robustness or our prompt. Finally, we validate against the test set to see that we didn't overfit on the dev examples. This is the practical way of splitting the data and calculating precision and recall scores for your judge to actually know that the judge is working as expected.

</details>

### 指标漂移与持续协同开发

**Ash**: 接下来，我想谈谈大家在做评估时经常忽略的另一个关键点：**标准漂移（criteria drift）与对评估器的校验（validating the validators）**。
最核心的理念是，我们对评估标准的真正认知，其实是在我们实际查看数据和给输出打分的过程中逐步发掘出来的。随着我们看到的真实数据越来越多，标定的样本越来越丰富，我们对服务质量的理解本身也是在不断演进的。因此，**评估系统的开发绝对不能与模型的日常观察和监控相脱节**。相反，评估器应该与 Agent 模型**协同开发（co-developed）**。我们在优化 Agent 的同时，要测试评估器，并不断计算其精确率和召回率。

对于大模型评判器，行业里一直存在一个误区，那就是认为我们可以提前把评估标准一字不落地定义好，然后直接拿去评估 Agent。事实上，随着新场景的出现，我们的评估标准必然会发生漂移和演进。我们必须随着新数据的积累不断微调和细化评判器的评分指标，并在这个基础上反过来验证评判器自身的准确度。

<details>
<summary>Original English</summary>

**Ash**: All right. This is another thing which most of us ignore when we are doing evaluations, which is criteria drift and validating the validators. The key idea is that we actually discover what our evaluation criteria is by looking at the data and grading our outputs. Our sense of quality will also evolve with new data we see and more examples we grade. So the evaluations should not be decoupled from model observations. In fact, they should be co-developed with the model when we are testing the evaluator and calculating the precision and recall scores. There is always a gap when we talk about LLM as a judge. We cannot define the criteria beforehand and then evaluate agents against them. Our criteria should also be evolving as and when we see more examples, and then we should refine our metrics for our judges and then evaluate judges on top of those metrics.

</details>

### 统计严谨度与置信区间

**Ash**: 下一步是引入**统计严谨度（statistical rigor）**，这能让我们的报告数据更具说服力。通常，大家都只汇报评判器与人类对齐的单点估算值（point estimates，例如对齐率 85%）。但如果我们引入**置信区间（confidence intervals）**，并进行校准和科学抽样，这些评估数值将变得真正有意义。

当然，我们应该把高成本的统计学检验留给最关键的时刻——比如涉及到最终上线的发布决策，或者向公司高层汇报关键数据时。但根据具体的应用场景，我们应该在汇报的评分中附带置信区间，因为**任何没有置信区间的评估得分都是不完整的**。

这里有一个简单的例子来说明置信区间的重要性。假设我们有两个版本的 Agent，一个评估得分是 84%，另一个是 88%，而我们使用的测试样本量只有 50 个。通过简单的统计计算就会发现，在 50 个样本的小样本量下，4% 的得分提升在统计学上是极其不显著的。我们根本无法确定这 4% 的增长究竟是真实的性能提升，还是随机抽样带来的噪声。因此，如果性能提升不够显著，或者未使用配对实验设计（paired designs），我们就需要更大的样本量来验证。我们可以将这种昂贵的统计严谨性投入到那些真正关键的评估节点上。

<details>
<summary>Original English</summary>

**Ash**: So the next step, one of the things which can make the numbers we are reporting more meaningful is to add some statistical rigor to it. We report alignment rates as bare point estimates. If we add confidence intervals, do some calibration and proper sampling, the same numbers can become more meaningful. We should definitely reserve the expensive rigor for the moments when a number actually gates something, like a shipping decision, or when we are reporting numbers to company leaders. But depending on the use case, we should definitely have confidence intervals for the numbers we report because every score needs an interval. Here is just a small example to give you an insight on what this actually means. Let's say we have two evaluators: one scores 84% and the other scores 88%, and the number of traces we have used is 50. To show that this is a very small gain, we need much more than 50 examples to actually show that this gain is real. With just 50 examples and only a four percentage point gain, we don't actually know if this gain is real or not. Bigger gains and paired designs need far less samples, and we can reserve the statistical rigor for things which matter the most.

</details>

### 评估反模式与根本基石

**Ash**: 这里我们列出了一些常见的评估反模式（eval anti-patterns）。我不会逐一去念，但其中确实有一些很容易避开的低级错误。要想获得真正有价值的评估，我们必须投入充足的时间和精力。我们目前还不能把一切工作都寄托于大模型。

我想特别强调的是，**绝对不要忽略数据本身（ignoring the data）**。这也许是很多团队最容易犯的错误——往往因为时间紧迫或资源匮乏，大家就不去肉眼看数据。但深入真实数据是构建一切有价值评估的基石。如果你不看数据，你就无法提炼出符合业务逻辑的评估标准，也无法打上准确的标签。没有标注的黄金标签，你就无法评估你的大模型评判器。而如果你连大模型评判器本身的准确度都无法衡量，系统就根本无法验证你的 Agent 管道是否工作正常。这环环相扣，数据是底座，是绝不能被忽视的生命线。

我们之前说，希望让评估指标更具执行性并建立标准化的评估管线。具体应该怎么落地？这里我们提供了一个**持续错误分析闭环（error analysis loop）**的模板。必须强调，**这个闭环必须是一个持续运行的日常机制，而不是一次性的偶发性审计**。具体流程是：
1. **深入剖析原始调用链路（raw traces）**：一旦我们记录了 Agent 工作流或多 Agent 系统的追踪日志，我们就深入其中；
2. **精准定位失效模式（failure modes）**：找出到底是哪个环节出错；
3. **精简并保留能够改变决策的指标**：清理所有冗余的噪声指标，只保留能够影响上线决策、与业务场景紧密相关的核心指标；
4. **形成新的假设并重新评估**：基于失效模式的理解建立新的测试假设，优化 Agent 后再次进行评测；
5. **循环往复**：团队可以设定每周或每两周的固定节奏（cadence）来运转这套流程。

<details>
<summary>Original English</summary>

**Ash**: Okay. So this is a non-exhaustive list of observed eval anti-patterns. I'm not going to read all of them, but these definitely contain some low-hanging fruits. We need to put in time and effort if we need meaningful evals. We cannot rely on LLMs for everything yet. What I can say is ignoring the data is one of the most important things which we shouldn't do, and which we sometimes don't focus on due to lack of time or resourcing, but it acts as the foundation for meaningful evaluations. If you don't look at the data, you won't be able to create meaningful criteria or labels. And if you don't have labels, you won't be able to evaluate your judges. And if you are not evaluating your judges, you don't know if your agentic pipeline is working as expected. So this acts as the base. It is one of the most important things we should not ignore.

Okay. We said that we want to make metrics more actionable and standardize the pipeline, but how should we actually do it? This gives you a template to do an error analysis loop, and it is important to know that this loop is something which runs continuously. It is not a one-off audit. We deep dive into raw traces. Once we have logged our traces for our agentic flows, multi-agent systems, or whatever we have in our use case, we pinpoint failure modes. Basically, we try to identify what exactly is failing and we only keep the metrics that change a decision. We remove all the noise. We only prioritize the metrics that are tied to business use cases, functional requirements, and actually change a decision. Then we form a fresh premise to re-evaluate and then we repeat it. We can have a regular cadence of doing this pipeline. It can be weekly, it can be bi-weekly, but this is something which needs to run continuously and it is not a one-off audit.

</details>

### 链路追踪与标注队列

**Ash**: 正如我们所说，**调用链路追踪（tracing）**是至关重要的，一切评估都基于它。要深入研究原始链路，首先必须把它们记录下来。我们可以使用 **Langsmith**、**Langfuse** 等工具来记录和可视化这些追踪链路。每一个 trace 都会完整捕获整个 LangGraph 图的执行轨迹——哪些节点被触发了、大模型在每个步骤看到了什么、调用了哪些工具、每次调用的 Token 消耗以及响应延迟是多少等等。如果需要，我们还可以用丰富的业务元数据（metadata）来增强追踪链路，这往往能提供比纯数据更丰富的洞察。

同时，我们建立了**标注队列（annotation queues）**。标注队列提供了一个对业务专家非常友好的可视化界面，方便他们对评估结果进行标注和反馈。这样，业务专家就不需要去盯着生涩难懂的追踪 JSON 日志。他们可以通过标注界面直观地给出反馈或进行 Pass/Fail 的标准标定。接着，我们可以将这些被专家标注的链路样本加入到离线评估数据集中，或者用它们来计算评估器自身的精确率和召回率。这构成了我们基于黄金标准标签验证评估质量的坚实基础。

<details>
<summary>Original English</summary>

**Ash**: Tracing, as we said, is one of the most important things and everything kind of depends on it. For diving deep into raw traces, we definitely need to log them first. We can use tools like Langsmith, Langfuse, etc. to log and view the traces. Here each trace captures the full graph execution: which nodes ran, what LLM saw, which tools were called, what was the token usage, what was the latency for every call, and things like that. We can also enrich traces with metadata if we want, which gives you more insights than the actual data.

And we also have annotation queues. Annotation queues are nothing but an interface which is very helpful for domain experts to label or give feedback to evaluators in an easy to understand UI. They don't have to look at the raw traces JSONs and stuff like that to figure out what to focus on. They can use this annotation queue and they can give feedback or label examples easily. We can then add these traces to datasets for offline evaluation or we can use this for calculating our precision and recall for our judges. So this forms the basis to validate the evaluation with ground truth labels.

</details>

**Ash**: 好的。现在我把麦克风交还给 Nick，让他来为我们分享如何闭环整个评估流程。

<details>
<summary>Original English</summary>

**Ash**: Okay. I now I'll hand it over to Nick to close the evaluation loop.

</details>

### 持续学习与评估闭环

**Nick**: 谢谢 Ash。我认为，做评估的终极目标是为了能够把评估得到的洞察重新反馈到系统中，以不断提升大模型或 Agent 的表现。这里，我将介绍我们在 AI Agent 的**持续学习（continual learning）**和闭环评估流程方面的几种主要思考方式。具体包括：**模型学习（model learning）**、**上下文学习（context learning）**和**套件学习（harness learning）**。

* **模型学习**：指的是在后期训练（post-training）中，通过微调更新底层的模型权重，来训练一个专门的定制大模型。
* **上下文学习与套件学习**：主要侧重于优化模型之外的其他周边组件。
  * **上下文学习**：优化 Agent 能够看到的实际信息。这包括检索的文档、存储的用户历史记忆、中间输出结果等。
  * **套件学习**：意味着更新模型的系统提示词（system prompt）、工具描述（tool schemas）、控制流路由逻辑（control flow routing）、重试机制（retries）等。

正如 Ash 前面分享的，我们的错误分析机制切实帮助我们搞清楚了应该如何改进 Agent 的 Prompt，如何更新知识库，以及如何优化 Agent 的上下文管理策略。识别出的具体失效模式让开发团队能够将评估洞察精准地转化为对 AI Agent 的实际性能提升。

<details>
<summary>Original English</summary>

**Nick**: Thank you Ash. I think the goal of having evals is to be able to feed our evaluation insights back into improving the model performance or the agent's performance. Here, I'll introduce a couple of ways that we think about continual learning for our AI agent and closing the evaluation loop. Here we have model learning, context learning, and harness learning.

Model learning is really about post-training, updating the underlying model weights, and training a custom LLM model. Context learning and harness learning are more about improving everything else other than the model. Context is improving what information the agent actually sees. This can be documents, the stored memories of the user, tool outputs, and so and so forth. Harness means updating the model's system prompt, tool schemas, control flow routing, retries, and so on.

From the error analysis that Ash shared earlier, it has really helped us understand how we can improve our agent's prompts, update our knowledge base, and tune the context management strategy of our AI agent. Identifying failure modes really helps us feed those insights into actual improvements for the AI agents.

</details>

### 模块化评估套件的未来

**Nick**: 我想快速展望一下我们接下来的工作。在 Lyft 构建客服 AI Agent 的历程中，我们目前虽然具备了运行离线模拟器的能力，但老实说，这个过程的复现性还不强。这些评估脚本目前零散地分布在不同的 Notebook 和分析仓库中。我们目前非常想要投资建设的一个方向是：**系统化的评估套件（eval harness）**。我们希望通过这套系统，以系统化和标准化的方式运行离线评估，并允许不同背景的成员使用预定义的算子（primitives）和基于配置（config-driven）的工作流，共同为评估测试集做出贡献。

另一个我们深入思考的方向是**后期训练（post-training）**。正如前文所述，虽然识别出失效模式帮助我们很好地调优了 Agent 的上下文和控制套件，但多年来我们还积累了海量的真实用户对 Agent 表现的反馈信号。因此，我们正在思考如何利用这些数据微调模型，使其能够胜任客服 Agent 体系中的各种子任务，并尝试构建一个奖励模型（reward modeling），从而引入强化学习（RL）。

在这里我简单分享一下我们在评估套件设计上的一些探索。评估套件（eval harness）本质上是支撑评估高效运行的基础脚手架（scaffolding）。我们需要它在 Lyft 复杂的客服多 Agent 和子 Agent 架构中，以标准化的格式高效运行评估。如前文离线模拟器部分所示，我们的评估套件是**配置驱动（config-driven）**的。评估配置通常以 YAML 文件存储，不仅工程师可以轻松编辑，数据分析师和数据科学家也能极其方便地修改和补充测试用例。

由于我们的评估套件中包含了成千上万个测试用例，我们必须引入**并行计算（parallelism）**来保证吞吐量，从而在合理的时间内跑完离线评估。为了方便大家参与贡献，我们在评估套件中定义了一系列底层的基本算子（primitives）：
* **任务（Task）**：定义评估要完成的业务目标；
* **数据集（Dataset）**：包含评测所需的对话样本；
* **用户画像（Persona）**：定义模拟用户的人设；
* **大模型适配器（LLM Adapter）**：用于对接不同的底层模型；
* **评估器（Evaluator）**：定义具体的评分和检验规则。

总而言之，建设评估套件的最大好处在于，你只需要**一次定义配置，就可以在 Agent 开发流程的不同拦截节点上无限次地重复运行评估**。例如：
* **本地开发**：开发人员在调整系统提示词时，可以本地一键运行评估，并立即获得与前一版本对比的即时反馈；
* **提交拦截（Pre-commit hook）**：在代码提交前自动运行，确保任何改动不会导致 Agent 基础表现的退化；
* **CI/CD 流水线**：集成在 CI/CD 中，自动运行回归测试套件以及验收测试套件。

以上就是我们今天的全部分享。我们今天探讨了非常丰富的话题。构建一套真正对客服 AI Agent 或任何面向用户的 Agent 应用起作用的评估管线，绝对是一个端到端的系统工程。Ash 和我非常期待听到大家在评估方面的工作，也欢迎分享你们的实践经验。如果你有任何问题，或者想和我们一起探讨如何优化评估系统，欢迎随时与我们联系。

谢谢大家，祝大家在 AI Engineer World Fair 中收获满满！

<details>
<summary>Original English</summary>

**Nick**: I want to quickly talk about what's next for us. In our journey of building customer support AI agents at Lyft, we have some level of ability to run our offline simulator, but it's not repeatable. These are currently stored as scattered scripts across different notebooks and analysis repos. One thing we are looking into investing in is a systematic eval harness. Having a harness system can help run our offline evaluation in a systematic and standardized manner, and allow different people to contribute to our evaluation suite with predefined primitives and a config-based workflow.

Another thing we've been thinking a lot about is post-training. As mentioned earlier, identifying model failure modes has helped us tune the agent's context and harness. But over the years, we have gathered a lot of real user signals on our agent's performance as well. We are starting to think about how we fine-tune a model that does different tasks for our customer support AI agent, as well as framing a reward modeling problem to enable reinforcement learning.

I want to quickly share a little bit about the work we're doing with the eval harness and how we think about building evaluatable agentic applications. Evals are the scaffolding we need to run evaluations efficiently in a standardized format across all the different agents and sub-agents we have. As you can see from our offline simulator slides, our eval harness is config-driven, typically stored as YAML files that are easily editable by different contributors—not just by engineers. Analysts and data scientists can contribute to this evaluation suite as well.

With thousands, if not tens of thousands, of examples in our evaluation suite, we need parallelism and throughput to run our offline evaluations in a reasonable amount of time. To enable different users to contribute, we also define primitives around our eval harness, such as tasks, datasets, personas, LLM adapters, and evaluators.

Ultimately, the benefit of having an eval harness is that you can define the config once and run these evals indefinitely many times across different touchpoints or gates of your agent development process. This can be locally when you're developing the agent—at any point when you tune a prompt, you can run the evaluation suite and get immediate feedback on how your agent is doing compared to previous versions. We can run these at pre-commit hooks to make sure performance doesn't degrade before pushing a change to our agent service. Another area we are looking at is CI/CD, and how we can use our eval harness to build our regression test suite and acceptance test suite.

So that wraps up our presentation today. We've gone through a lot of different topics for evaluations. Truly, this is an end-to-end journey for building an evaluation pipeline that works for customer support AI agents or any user-facing agentic applications. Ash and I are very interested to hear about what you all have been working on and share any learnings you have. Feel free to contact us if you have any questions or just want to brainstorm about how to improve evaluations. All right, thank you and I hope you enjoy the AI Engineer World Fair.

</details>

**Ash**: 谢谢大家。

<details>
<summary>Original English</summary>

**Ash**: Thank you.

</details>

**Nick**: 感谢大家。

<details>
<summary>Original English</summary>

**Nick**: Thanks all.

</details>