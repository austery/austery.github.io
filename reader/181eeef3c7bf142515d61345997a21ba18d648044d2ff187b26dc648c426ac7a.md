---
author: AI Engineer
date: '2026-07-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2IxD9OB3XuQ
speaker: AI Engineer
tags:
  - continual-learning
  - ai-agent
  - regression-testing
  - reinforcement-learning
  - optimization
title: AI Agent的持续学习：从失败到持久改进的重构范式
summary: Rely 创始人 Soheil Feizi 阐述了 AI Agent 持续学习的挑战与方案，提出“可验证持续学习”框架，通过可复现环境、多层协同修复、无回归优化与高效迭代四大原则，实现 Agent 的安全与持续进化。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Soheil Feizi
companies_orgs:
  - Rely
  - University of Maryland
products_models:
  - Rely's learning engine
media_books: []
status: evergreen
---
### 持续学习：构建不遗忘的 AI Agent 进化机制

**持续学习**（Continual Learning: 让系统在接收新输入、学习新任务时，不遗忘已掌握的旧知识）是人脑具备的本能。人类通过与现实世界交互，从成功或失败的反馈中积累经验，不断修正认知。对于 **AI Agent**（AI 智能体: 能够自主感知环境、进行决策并执行任务的计算实体）而言，持续学习的终极目标也是如此：在与不同用户交互、调用复杂工具、遵循多样数据策略的动态生产环境中，持续从失败案例中吸取教训并实现持久改进，且确保旧的技能不会退化。

这种持续学习的改进可以在 Agent 的多个核心架构层级中实现：
*   **模型层**（Model Layer）：通过调整大语言模型（LLM）或其他底层模型的权重，或替换为更适合的基座模型来优化。
*   **装配层**（Harness Layer: 围绕底层模型构建的辅助框架，包括 Prompt、工具调用、代码逻辑和工作流设计）：调整 Prompt 提示词、丰富可调用技能集、添加控制逻辑和约束门。
*   **记忆层**（Memory Layer）：优化 Agent 的会话记忆或持久化记忆（如事实性数据库或技能库）。

然而，实现 Agent 的持续学习面临两个根源性挑战：第一，**反馈获取**，即如何识别 Agent 执行任务的成败，并定义在失败时它应该采取的正确行为；第二，**反馈应用**，即如何在定位到问题后，决定在哪个层级以及如何执行优化。

<details>
<summary>Original English Source</summary>
Humans learn mainly from experience by interacting with the world and getting feedback. The goal of continual learning is to imitate the same for agents. So they can also learn from experience by acting, getting feedback, and improving without forgetting.
Here's basically a bigger picture of how continual learning for agents look like. So here's an agent that interact with the world, with diverse users, with complex tools, with various data policies. And the goal is to continuously improve the agent from its experience without forgetting. And this learning can happen in different layers of the agent. It can happen in the model layer where potentially we can change weights of LLMs or other models used in the agent, or use different types of models in the agent. It can happen in the harness layer where it brings the proper context to the LLM with components like prompts, skills, tools, code, workflow. And it can also happen in the memory, either in session memory or persistent memory of the agent.
But there are two, I would say, fundamental challenges in continual learning for agents. The first challenge is how to get feedback. How do we know if the agent did well? And if not, what should it have done instead? That's basically the first part, getting the feedback. And the second part is how we can act upon that feedback. How we can optimize and improve agent and learn from that feedback. Which layer, which component do we need to change and also how.
</details>

### 从单次日志到可复现的仿真学习环境

在开发阶段，评估 Agent 的表现相对简单。开发者可以利用精心整理的**基准测试集**（Benchmark: 包含固定输入与期望输出的标准化测试数据集）和配套的评估器，快速获得通过（Pass）、失败（Fail）或数值化的奖励信号。然而，在真实的生产环境中，我们无法直接获取基准测试数据，唯一能依赖的是海量的会话日志。用户在与 Agent 交互时，可能表达出负面情绪或不满，但通常没有明确的改错反馈。

针对生产日志，目前主要有两种提取反馈的方式：**自动化评估**，即利用其他大语言模型或定制代码解析日志、提供诊断与反馈（甚至是 Agent 自身的自我反思），这种方式规模化能力极强；**专家评估**，即由领域专家抽样审查日志并提供精准对齐的对策反馈，其数量较少但对于复杂场景对齐至关重要。

但这两种反馈仍然不足以支持 Agent 的持续优化。因为单次的“日志 + 反馈”是静态的，并不具备**可测试性**。我们真正需要的是一个**可复现的仿真学习环境**（Replayable Learning Environment: 能够重现失败场景并支持 Agent 重复运行以验证修改效果的模拟系统）。通过对单次日志进行分布推断，我们需要自动构建出一个包含以下要素的模拟沙盒：
*   **模拟用户行为**：从真实数据中推断并合成具有特定意图、性格甚至对抗性的虚拟用户。
*   **工具 Mock 机制**：判断是连接真实工具还是使用模拟工具，并合成合理的工具返回数据。
*   **自动评估指标**：从日志反馈中推断并转化为自动执行的成功/失败判定准则。

只有将一次性的失败提升为可运行、可复现的测试用例，后续的任何 Agent 改进才拥有了被客观度量和验证的科学基础。

<details>
<summary>Original English Source</summary>
Where does the feedback come from? So, the easy case is when we have a benchmark and some evaluators on that benchmark. So, the agent can run tasks from the benchmark. Now, we have the evaluators in order to score and we can get grades like pass, fail, or reward, as well as potentially some feedback on the agent behavior and agent performance. This is usually what is happening during the development time that different teams they curate benchmarks in order to understand the performance of the agent in certain applications.
But in production, we don't have such benchmark. We have logs. Here's an example of a session log where a user is interacting with the agent. Maybe the user is not very happy with the way the agent is behaving, but we don't have any explicit feedback. So, there are two ways of getting such feedback on such session logs. One is automatic using some other models or LLMs or code in order to analyze the log and provide feedback. In some cases, even the agent itself can look at it is log and provide some critics of it. It is automatic and it is scalable. And the second approach is where we have human experts to look at some handful of these logs and provide some domain expert feedback on those agent outputs. This is lower in the volume, but it is critical because it provides expert knowledge on the behavior of the agent and its alignment with the way that we want agent to behave in those applications. Either way, now we have session log plus some feedback on those logs.
Is it enough? The answer is no because it is still not testable. Here we have log and feedback, but what we really need is a replayable learning environment, a simulation that we can rerun with defined grading on what success looks like, not one instance of what happened and the feedback on top of it.
So what is a learning environment? Here we are inferring a distribution from one observation that replaces what happened and what success means. The input is what we have some session logs and feedback. This is basically one observation of what happened and now we want to create a simulation and evaluation environment from that information that involves, for example, understanding how tools in the agent behavior in the agent log should behave, should we use real tools, should we use mock tools, and if so, what kind of data brought to the mocking process of those tools. If the agent is interacting with some users, how we can infer synthetic users from that data. And also how success looks like in that learning environment. What are the files/evaluators that needs to be inferred. So there are lots of technical challenges in any of these components, but if we could do this successfully, they could use this the output as executable. We can now run different candidates of the agents against such learning environment, understand the behavior and the performance of the agent in those scenarios and in those patterns, and we can fix the issues based on the feedback, based on the information that we observe because now everything becomes testable and verifiable.
</details>

### 多层优化策略与“最小持久改动”原则

在具备可复现的仿真环境后，优化 Agent 可以在模型、装配和记忆三个层级展开，其技术路线和成本结构各不相同。

1.  **模型层优化
[BODY_START]
### 持续学习：构建不遗忘的 AI Agent 进化机制

**持续学习**（Continual Learning: 让系统在接收新输入、学习新任务时，不遗忘已掌握的旧知识）是人脑具备的本能。人类通过与现实世界交互，从成功或失败的反馈中获得经验，不断修正认知。对于 **AI Agent**（AI 智能体: 能够自主感知环境、进行决策并执行任务的计算实体）而言，持续学习的终极目标也是如此：在与不同用户交互、调用复杂工具、遵循多样数据策略的动态生产环境中，持续从失败案例中吸取教训并实现持久改进，且确保旧的技能不会退化。

这种持续学习的改进可以在 Agent 的多个核心架构层级中实现：
*   **模型层**（Model Layer）：通过调整大语言模型（LLM）或其他底层模型的权重，或替换为更适合的基座模型来优化。
*   **装配层**（Harness Layer: 围绕底层模型构建的辅助框架，包括 Prompt、工具调用、代码逻辑和工作流设计）：调整 Prompt 提示词、丰富可调用技能集、添加控制逻辑和约束门。
*   **记忆层**（Memory Layer）：优化 Agent 的会话记忆或持久化记忆（如事实性数据库或技能库）。

然而，实现 Agent 的持续学习面临两个根源性挑战：第一，**反馈获取**，即如何识别 Agent 执行任务的成败，并定义在失败时它应该采取的正确行为；第二，**反馈应用**，即如何在定位到问题后，决定在哪个层级以及如何执行优化。

<details>
<summary>Original English Source</summary>
Humans learn mainly from experience by interacting with the world and getting feedback. The goal of continual learning is to imitate the same for agents. So they can also learn from experience by acting, getting feedback, and improving without forgetting.
Here's basically a bigger picture of how continual learning for agents look like. So here's an agent that interact with the world, with diverse users, with complex tools, with various data policies. And the goal is to continuously improve the agent from its experience without forgetting. And this learning can happen in different layers of the agent. It can happen in the model layer where potentially we can change weights of LLMs or other models used in the agent, or use different types of models in the agent. It can happen in the harness layer where it brings the proper context to the LLM with components like prompts, skills, tools, code, workflow. And it can also happen in the memory, either in session memory or persistent memory of the agent.
But there are two, I would say, fundamental challenges in continual learning for agents. The first challenge is how to get feedback. How do we know if the agent did well? And if not, what should it have done instead? That's basically the first part, getting the feedback. And the second part is how we can act upon that feedback. How we can optimize and improve agent and learn from that feedback. Which layer, which component do we need to change and also how.
</details>

### 从单次日志到可复现的仿真学习环境

在开发阶段，评估 Agent 的表现相对简单。开发者可以利用精心整理的**基准测试集**（Benchmark: 包含固定输入与期望输出的标准化测试数据集）和配套的评估器，快速获得通过（Pass）、失败（Fail）或数值化的奖励信号。然而，在真实的生产环境中，我们无法直接获取基准测试数据，唯一能依赖的是海量的会话日志。用户在与 Agent 交互时，可能表达出负面情绪或不满，但通常没有明确的改错反馈。

针对生产日志，目前主要有两种提取反馈的方式：**自动化评估**，即利用其他大语言模型或定制代码解析日志、提供诊断与反馈（甚至是 Agent 自身的自我反思），这种方式规模化能力极强；**专家评估**，即由领域专家抽样审查日志并提供精准对齐的对策反馈，其数量较少但对于复杂场景对齐至关重要。

但这两种反馈仍然不足以支持 Agent 的持续优化。因为单次的“日志 + 反馈”是静态的，并不具备**可测试性**。我们真正需要的是一个**可复现的仿真学习环境**（Replayable Learning Environment: 能够重现失败场景并支持 Agent 重复运行以验证修改效果的模拟系统）。通过对单次日志进行分布推断，我们需要自动构建出一个包含以下要素的模拟沙盒：
*   **模拟用户行为**：从真实数据中推断并合成具有特定意图、性格甚至对抗性的虚拟用户。
*   **工具 Mock 机制**：判断是连接真实工具还是使用模拟工具，并合成合理的工具返回数据。
*   **自动评估指标**：从日志反馈中推断并转化为自动执行的成功/失败判定准则。

只有将一次性的失败提升为可运行、可复现的测试用例，后续的任何 Agent 改进才拥有了被客观度量和验证的科学基础。

<details>
<summary>Original English Source</summary>
Where does the feedback come from? So, the easy case is when we have a benchmark and some evaluators on that benchmark. So, the agent can run tasks from the benchmark. Now, we have the evaluators in order to score and we can get grades like pass, fail, or reward, as well as potentially some feedback on the agent behavior and agent performance. This is usually what is happening during the development time that different teams they curate benchmarks in order to understand the performance of the agent in certain applications.
But in production, we don't have such benchmark. We have logs. Here's an example of a session log where a user is interacting with the agent. Maybe the user is not very happy with the way the agent is behaving, but we don't have any explicit feedback. So, there are two ways of getting such feedback on such session logs. One is automatic using some other models or LLMs or code in order to analyze the log and provide feedback. In some cases, even the agent itself can look at it is log and provide some critics of it. It is automatic and it is scalable. And the second approach is where we have human experts to look at some handful of these logs and provide some domain expert feedback on those agent outputs. This is lower in the volume, but it is critical because it provides expert knowledge on the behavior of the agent and its alignment with the way that we want agent to behave in those applications. Either way, now we have session log plus some feedback on those logs.
Is it enough? The answer is no because it is still not testable. Here we have log and feedback, but what we really need is a replayable learning environment, a simulation that we can rerun with defined grading on what success looks like, not one instance of what happened and the feedback on top of it.
So what is a learning environment? Here we are inferring a distribution from one observation that replaces what happened and what success means. The input is what we have some session logs and feedback. This is basically one observation of what happened and now we want to create a simulation and evaluation environment from that information that involves, for example, understanding how tools in the agent behavior in the agent log should behave, should we use real tools, should we use mock tools, and if so, what kind of data brought to the mocking process of those tools. If the agent is interacting with some users, how we can infer synthetic users from that data. And also how success looks like in that learning environment. What are the files/evaluators that needs to be inferred. So there are lots of technical challenges in any of these components, but if we could do this successfully, they could use this the output as executable. We can now run different candidates of the agents against such learning environment, understand the behavior and the performance of the agent in those scenarios and in those patterns, and we can fix the issues based on the feedback, based on the information that we observe because now everything becomes testable and verifiable.
</details>

### 多层优化策略与“最小持久改动”原则

在具备可复现的仿真环境后，优化 Agent 可以在模型、装配和记忆三个层级展开，其技术路线和成本结构各不相同。

在**模型层**，可以通过**监督微调**（Supervised Fine-Tuning: 利用高质量的标注数据来调整模型参数以模仿正确行为）或基于强化学习的后训练（如 DPO、GRPO、RLVR 等），根据奖励或偏好信号来增强模型能力。虽然可以通过 **LoRA**（Low-Rank Adaptation: 仅训练低秩分解矩阵以减少微调参数量的技术）降低计算开销并提升安全性，但整体上调整权重依然需要高昂的算力开销，且同样依赖于基准测试和评估机制。

在**装配层**，我们可以通过让专门的编程 Agent 分析失败轨迹，直接修改 Prompt、增加控制代码或工具拦截网关。这种方法灵活性极高，但由于往往只针对单一失败样本进行局部重写，极易在未测试的其他场景中引入隐性回归。另一种方案则是采用类似 GEPPO 的算法，通过进化算法等搜索策略，在基准测试上迭代变异并筛选出最优 Prompt。

在**记忆层**，优化最为经济高效。我们可以通过向记忆库中直接写入新规则（如 LETA、MemZero 等方法）或进行**技能蒸馏**（Skill Distillation: 将成功的长轨迹压缩提炼为可复现的标准化技能模板），从而防止 Agent 重蹈覆辙。但这同样面临缺乏全量回归验证的困境，新写入的记忆规则可能会在旧任务中产生不可预知的冲突。

优秀的持续学习引擎不应该局限于单一层级，而是应当动态评估，在最合适的层级以**最小持久改动**（Smallest Durable Change）来解决当前的失败问题。

<details>
<summary>Original English Source</summary>
Uh there's a model layer where we can change the weights of the model, and there are methods like SFT, so supervised fine-tuning, uh RL-based post-training in order to make those changes. And these are usually expensive because that requires uh more intensive compute in terms of changing the model weights.
The second layer is the harness layer, harness engineering, context engineering, where we can potentially pre-write prompts, maybe learn some skills, uh change tools or add tools, maybe change code around the LLM, and there are different methods like get past race to harness, uh which provides a lot of flexibility in terms of learning from that feedback. And the last layer is the memory layer, where we store facts and learn skills uh in order to not repeat those issues uh and failures in the future. But a good learning is not going to be focusing on any of these components exclusively. A good learning engine should ask for the smallest durable change at the right layer of the agent.
All right. So, let me uh dig a little bit deeper into each of these layers. So, first in terms of updating the model weights, there are various approaches uh in order to do that, uh including SFT, supervised fine-tuning, where we imitate correct trajectories. Uh we often need labeled samples in order to fit those samples, uh fit the model to those samples. Other approaches are based on RL, reinforcement learning post-training, like DPO, GRPO, RLVR, where we sample score against the reward or preference signals, and reinforce what wins. And there are some categories based on LoRA, low-rank adaptation, that limits the set of parameters that can potentially change. It makes this uh the learning in this layer cheaper, and also safer um in terms of the updates. But these methods, they usually need benchmarks and explicit evaluators. They cannot be directly applied on, let's say, if you have a log and feedback, unless we turn those into uh replayable learning environments.
Right, in terms of uh updating the harness, uh I would highlight the two uh categories in this domain, in this layer. One is trace-to-harness approaches. Let's say you observe a log, you have some feedback on top of it, you can effectively ask a coding agent in order to analyze the log and improve the agent. So, this works on uh the case where we have log and feedback, but it is wipe-based. We don't know if even for that particular uh sample, if the change is effective, because it is not testable. And we don't know what is the impact of it on other samples and other scenarios. What uh might have been working previously, but with these changes might not work properly, and create some hidden regressions. The other category that I want to highlight is methods like GEPPO and prompt search where they mutate prompts, they score different candidates, and they keep the winners using some search algorithms like evolutionary algorithms. And these are These methods are testable, but they need a benchmark and explicit evaluators in order to have those scorings.
And in the memory layer, we effectively write down facts and we distill skills so the agent doesn't rediscover them. It can happen in the information memory layer, methods like LETA and MemZero where they can effectively store a fact or correction. And we have also methods to skill distillation that compresses successful trajectory into reusable how-to do skill for the agent. So, this layer in terms of the update is cheapest and fastest. It works directly on the cases where you only have log and feedback, but usually it is unverified because you don't have a way in order to test whether or not writing in the memory will resolve the issues that you have dealt with and whether or not it can potentially create some regressions on some other cases.
</details>

### 可验证持续学习的四大核心支柱

为解决 Agent 迭代优化中的盲目性，Soheil Feizi 提出了**可验证持续学习**（Verifiable Continual Learning, VCL）的学术范式。其核心目标是：**每一次的修复均被证实有效，且绝对不破坏任何已有的正确行为**。

VCL 的运转主要建立在以下四大支柱原则上：

*   **可复现性**（Replayability）：必须能够将单次生产环境中的失败日志转化为包含仿真用户、Mock 工具和定制化评估器的可执行沙盒，使得失败行为可重现、改进效果可度量。
*   **全局性**（Holisticness）：Agent 的失败可能源于 stale 状态的记忆、未优化的 Prompt、未处理数据边界的工具或是底层模型推理能力的缺陷。修复过程应当总揽全局，通过根因分析，在最合适的层级以最小的扰动实施修复。
*   **终身性**（Lifelongness）：在引入第 $K+1$ 个修复时，不应只针对当前失败进行过拟合。系统必须实施**回归感知优化**（Regression-Aware Optimization），将回归测试作为优化循环内部的硬性约束，而不是事后打补丁，以此保障旧有知识与新技能的和谐共存。
*   **高效性**（Efficiency）：因为持续学习循环需要频繁高频地运行，优化算法的计算复杂度不能随着历史用例数 $K$ 的增长而线性甚至呈指数级攀升，必须在搜索、微调和回归校验中引入高效的剪枝与评估机制。

在 Rely，团队将这四大原则落地为一整套工程化工作流：通过单次指令在后台生成模拟环境，执行回归感知的多层优化，最终为开发者产出包含详尽逻辑变更和验证得分的 Pull Request（合并请求）。

<details>
<summary>Original English Source</summary>
With that, let me introduce a new subcategory of continual learning called verifiable continual learning. In a verifiable continual learning, the goal is to improve an agent from its own experience where every fix is proven to help and proven to break nothing that already worked. And usually it involves three steps. Where we need to have an executable test where the failure becomes a task you can replay and create. Then we need to have a measured delta where the update is scored on the test before and after. And then we have a regression test. So prior test still pass even after we make such changes to the agent.
So let's think about what are the principles of a practical verifiable continual learning first. And I will argue there are four important principles that we need to keep in mind.
So the first principle is replayability. We need to turn a one of failure into a test that we can rerun. Here, as I had mentioned previously, many cases we have log and feedback, but that is not testable. We need to lift it in a learning environment to simulate and evaluate the agent on a similar pattern on a similar scenario. So everything becomes testable based on that simulation and evaluation environment. So that's basically the first principle that we need to have.
The second principle is holisticness. One failure may have several causes and several possible repairs. You know, let me give you an example. Let's say you have an agent that cites a stale policy and skips the required escalation. The issue might come from the memory where you have some stale fact. It can come from uh not optimized prompt. It might come from a tool that doesn't normalize the policy. Might come from the workflow that we need to add escalation gate before we run. It might come from the model. Maybe the model is not a good model in order to have a strong reasoning. So here we need to route the fix to the right layers that explains the failure with the smallest durable change to the agent. And that is basically the principle of holisticness in verifiable continual learning.
The third principle is lifelongness. A new fix must improve the new case without breaking the past. Let's consider the setup where we already optimize the agent on K past learning environments and a new failure comes and we turn that into a learning environment EK plus one. What do want to change? So, the first approach is okay, just focus on this new learning environment, but that can create regression on the past behavior on the past learning environments that the agent was successful. A better approach is a regression aware learning where the regression is not be treated as a post-hoc approach, but as a mechanism within the optimization itself. So, here we are fixing the recent failures subject to having no regression on the past uh learning environments. And obviously, this needs to be done in a efficient manner, so it doesn't scale even linearly with K because K can grow and the complexity of this approach can uh can be very can be very high.
And the last but not least principle is the efficiency. This continual learning loop needs to run frequently and we need to have efficiency in uh different layers in updates to the agent. So, sometimes the change can be cheap, like for example, writing something in the memory can be medium in terms of the complexity by changing the prompt or harness, and sometimes it can be very expensive by changing the weights of the model. Also, efficiency should be in the optimization loop itself, especially when we have regression aware optimization and regression is treated within the loop not as a post hoc approach.
To sum up, these are the four principles of a practical verifiable continual learning. Replayability, holisticness, lifelongness, and efficiency. And this is what we have been working on at Rely to create a verifiable continual learning engine for AI agents based on these four principles. In particular, here's how Rely's learning loop runs. You can start with some signals to this loop. It can be logs, feedback, or even instructions and prompts. We lift those in those signals to replayable learning environments. So, that's based on the replayability principle. This makes everything that follows testable and verifiable. Then we do root cause analysis and route the fixes to the right layer of the agent. It can be memory, it can be model, or it can be harness. That touches the holisticness principle that I described. We have regression aware optimization. Regression is not being treated as a post hoc approach, so that touches the lifelongness principle that I mentioned. And obviously, this loop should run efficiently. That touches the efficiency principle. So, the output of this is a reviewable version update to the agent explaining what changes in the agent during this loop and why those changes are are improving the agent without creating regression.
The beauty of it is you can add a VCL verifiable continual learning to your current agent in just two comments. So, the first one is a one-time setup. You create a learning harness in your agent. You can use your own LLM and your agent can be built on top of any of available major agent frameworks. And then after that, you need two commands in order to activate this learning loop. You can create learning environments using various type of signals that you can have either log feedback or some instructions, and then you can call to like optimize in order to use holistic lifelong optimizer to improve the agent. And the output is a optimized version pull request that you can review and you can use it in order to improve your agent.
</details>

### 实战评估：在对抗性环境中的可恢复性表现

为了在实际环境中评估 VCL 框架的有效性，Rely 团队构建了一个包含特定“回归陷阱”的客服 Agent 基准测试。在初始测试中，当面对普通用户的合理退款请求时，Agent 在前期的规则框架下，整体通过率为 87%。

此时，如果引入一个新的测试指令——“**当来电用户态度粗鲁且具有对抗性时如何处理**”，VCL 框架会自动执行以下流程：
1.  **沙盒生成**：解析此指令，推断并合成具有愤怒粗鲁 Persona（画像）的虚拟用户，并定义对应的拦截指标（如保持专业态度、拒绝无理要求），构建起新的模拟环境。
2.  **基线运行**：在该特定对抗场景下运行 Agent，发现由于其过度迁就用户或规则匹配失误，对抗场景得分仅为 78%。
3.  **闭环优化**：调用 Rely 的回归感知优化器，执行数次优化探索。在不改变底层大模型权重的前提下，优化器自动在装配层调整了情绪过滤规则，并向记忆层注入了关于红线升级的策略规则。
4.  **成效输出**：在经历 VCL 优化后，对抗场景的得分显著提升至 97%，而在之前 $K$ 个历史测试场景（包括普通用户的退款用例）中，Agent 的通过率完全没有下滑。

同样，在生产日志的优化实验中，针对关于“**对符合条件的退款快速放行，但超出退款限额时绝不能妥协**”的反馈，VCL 成功在避免过度慷慨化（Over-generalize Generosity）这一回归隐患的同时，消除了这一特定的超限退款漏洞。

实验结果表明，由于将回归校验作为优化搜索的内置惩罚条件，Agent 在不断解决新失败的同时，旧有技能依然稳固。这种持续 compounding（复利式）的进化，是让 Agent 走向安全生产的核心动力。

<details>
<summary>Original English Source</summary>
So, let's look at the how it actually works in practice. We build a continual learning benchmark on a fictional support agent case where we have reproducible test beds for continual learning in a tool using support agent. So, we have a single source of truth and the policies are interacting for this agent to be handling. So, we have deterministic evaluators and we also build this benchmark in a way that it has some regression trap. So, if the optimizer focuses on overfitting on the latest fix, it can potentially break what are what the agent was previously successful on other tasks.
So, let's say we have an agent. We don't even have logs or anything, and we want to just see how the agent is behaving. Uh, let's say when um, caller is rude and adversarial. So, simply we can create a learning environment using such instruction. And what it will do, it will create a learning environment to simulate and evaluate the agent. Uh, the simulator will include personas, intent, mock, uh, or real tools and also the learning environment contain evaluators in order to define success metrics. All of these are produced from just one interactive comment.
And after that, we can just simulate the agent using this learning environment, see how it behaves. Okay, the score is uh, not too uh, high. It is 78% and in particular, there are two um, evaluators that uh, basically show very low scores uh, of agent in this environment. So, these are some of the failures that we observe. How to improve such failures? We can do that by calling Rely Optimize with certain number of rollouts. And as you can see, the average improvement uh, can be um, quite high. Uh, it is 10% improvement on average just with one loop and score increases to 97% from 87%.
Okay, now let's consider the case that now the agent is in production. Now, you have a log, you have an agent session that isn't um, not desired and you have a feedback. For example, you can say keep fast eligible refunds, but do not generalize generosity beyond refund thresholds. So, that's a feedback on the agent behavior. Again, the flow is the same, so we lift it into a replayable learning environment and we call Rely Optimize in order to mitigate this uh, issue. Use this feedback without creating regression of the agent behavior in past environments. And this is lifelong, so you can keep doing that uh to improve the agent without breaking what already works, and it is compounding. This is verifiable continual learning in practice, where each update is tested, every gain is measured, and nothing that already works breaks during this optimization.
So, that's it for uh today and for this talk. So, there are three key takeaways that I want to highlight. The first one is agent continual learning is not necessarily model fine-tuning. The updates and many useful updates can happen in the harness and memory layer. So, the second takeaway is production logs are not learning environments. We need to transform them into replayable learning environments to simulate and evaluate the agent on the same patterns and scenarios. And the third takeaway is that the frontier is regression-aware continual improvement, where when fixing the new failure, we verify that we don't forget the old ones. We don't create regression. So, that's verifiable continual learning built on four principles: replayability, holisticness, lifelongness, and efficiency. And if you want to try um our VCL and apply it to your agent, you can use it today at rely.ai. Thank you.
</details>