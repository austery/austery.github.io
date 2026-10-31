---
author: AI Engineer
date: '2026-05-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3_gYbhABcAE
speaker: AI Engineer
tags:
  - ai-agent
  - prompt-engineering
  - system-design
  - software-architecture
  - evaluation-metrics
title: 从流量控制到任务调度：AI Agent 开发范式转换
summary: Philipp Schmid 在 Google DeepMind 的实践经验基础上，深度解析了构建 AI Agent 与传统软件工程的五个核心差异，包括从确定性流程到目标导向、语义化状态管理、错误处理机制、从单元测试到评估体系的演进，以及 API 设计原则的变革。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - DeepMind
products_models:
  - Gemini
media_books: []
status: evergreen
---
### 范式转换：从交通控制器到调度员

传统软件开发与 **AI Agent**（人工智能代理：能够自主感知环境并采取行动以实现目标的系统）的构建逻辑存在本质差异。在传统开发中，工程师更像是一个“交通控制器”，严格定义了每一条道路、每一个路口以及每辆车的行驶规则，系统是高度确定性的。而构建 Agent 时，工程师的角色更像是一个“调度员”。我们不再定义实现目标的精确步骤，而是设定明确的目标。Agent 可能会通过我们预料之外的路径达成结果，关键在于如何通过观察其行为、调整提示词（Prompt）与工具调用，形成一个持续改进的迭代闭环，以提升 Agent 的可靠性。

<details><summary>Original English Source</summary>

We're going to talk today 10 minutes about why engineers struggle to build agents and I see this every day internally at Google but also externally at Google and I brought five example on like what's really different to how we built traditional software a few years ago and to now how we build agents. And if we like on a high level compare them, right? When we wrote software, we created a spec, a PRD, wrote code, sometimes created tests to make sure our code works. We deployed it and then our user used it. And when building agents, things are a little bit different. We define instructions on what we want our agent to do. We run it, we observe what it does, we maybe adjust our prompts, maybe we adjust our tools. We run it again and we have like this iterative loop of how can we improve and make our agent way more reliable, which is very different to how we build software. And like something I like to compare it to is like traditional software is more like we acted as a traffic controller, right? We had control over the street lights or how fast you can go, which roads you can use, basically how the car drives. And now with agents, we are more of a dispatcher. We tell the agent, "Hey, I want to go to London and I'm from like Germany. I could use the train, I could fly, I could use my car and go like under the water." And it's more about, "Okay, we define the goal on what we want the agent to do, but we don't define the exact step the agent needs to take to achieve that goal. And I mean every one of you has probably seen in their coding agent that sometimes it does something very weird, but at the end it achieves the outcome. And that's what we want to do.

</details>

### 语义化状态管理：文本与上下文的崛起

传统软件依赖结构化数据，状态被清晰地映射为布尔值或标志位（Flags）。但在 Agent 开发中，文本和上下文（Context）成为了新的核心状态。**大语言模型**（Large Language Model: 基于海量文本训练的 AI 系统）能够理解语义含义，这使得 Agent 在面对复杂任务时具备了动态处理能力。例如，当 Agent 执行深度研究任务时，我们不再需要处理复杂的单步确认逻辑，而是可以直接在 Agent 提出的计划基础上提供额外的指令——这不再是简单的“接受”或“拒绝”，而是语义层面上的动态调整。此外，对于个性化需求（如 Celsius 与 Fahrenheit 的切换），Agent 能够基于用户上下文动态响应，而无需维护死板的配置文件或标志位。

<details><summary>Original English Source</summary>

So starting with the first example, text is our new state. I mean traditionally we had data structures and everything was kind of mapped to Boolean or to like flags we could check. So initially when we created for example a deep research agent, deep research agent returns a plan to you, "Okay, I'm going to research this and that." In traditional software, we might have had an exact plan or deny plan, but we couldn't catch semantic meaning. And now what we have with LLMs is they can understand the semantic meaning. So for example, if I have a deep research request on like doing some market research, I can approve the initial plan, but I can also on the same time provide additional information. So maybe I want to focus on like the US market and ignore California. Maybe I want to provide something additional and not have like this multiple steps, right? Traditionally it would probably said decline and then it has a follow up. I might needed to provide more input, create a new plan and continue. And another good example is everything related to memory and personalization we do cannot really be mapped to data structures, right? The example I here I have is like I'm from Europe, so I mostly use Celsius, but what if I would like to use Fahrenheit for cooking, right? Previously we might had some flags on like the user profile is Celsius or is Europe or use Fahrenheit, but I couldn't like dynamically adjust based on the user preference, based on what I provide. So really it's all about text and context. I mean could be images, video, audio as well, but we no longer are really operating in those clear structured data concepts.

</details>

### 信任与控制权：放弃确定性思维

工程师在设计 Agent 时，必须学会适时放权。传统客户支持系统依赖分类模型来判定用户意图，随后走入死板的预定义工作流。这种确定性流程难以应对多样化的用户反馈。如果 Agent 能够理解用户言外之意，并在流程中动态调整策略（例如在用户试图取消订阅时，基于对话语境提供替代方案而非机械地执行取消操作），将能带来更好的用户体验。这意味着我们需要信任 **LLM**（Large Language Model: 大语言模型），放弃在非确定性环境中试图通过死板的“状态机”来控制一切的想法。

<details><summary>Original English Source</summary>

The other thing is we should start handing over control and the the trap or the example which we might have from like previous customer support is like when a user reached out, "Hey, I want to cancel my subscription." I might have had classification model which kind of classified the intent, "Okay, the user wants to churn." And then I had a predefined workflow of, "Okay, do you try to sell it? Do you cancel the subscription?" But there was no like dynamic kind of option to to react to it dynamically. And maybe instead of like um or going through the subscription cancel flow, what if your agent like kind of tries to understand the meaning and like offers something uh in ex- step to like the subscription and the user changes their mind and now you have like a whole different intent. And it's very hard to model all of those differences and uniqueness and to to like all of those stateful workflows we had before. So we need to like trust into the LLM or like hand over control that we are no longer working in those purely deterministic um environments.

</details>

### 错误即输入：设计容错与恢复机制

在 Agent 构建中，应将流程中的错误视为一种正常的输入，而非程序崩溃。在传统的高并发环境中，HTTP 请求成本低廉，一旦失败直接重试即可。但 Agent 的执行通常耗时较长（可能持续数分钟甚至更久），直接从头重试会消耗大量计算资源且丢失上下文。因此，我们必须为 Agent 设计“恢复机制”。如果某个中间步骤失败，应将该错误信息反馈给模型，让其尝试通过其他工作方案、增加检查机制等方式在既有流程中继续推进，而不是简单粗暴地从头开始。

<details><summary>Original English Source</summary>

The third one is errors are just inputs. So if something in your agent flow fails, we need to treat it as a normal input as very similar to a user input. In Go, we already do this, right? A function call can be an error or can be a value and we treat them kind of equally. And we have to do this for agents very similarly. In the past, HTTP requests were very cheap. When some search, some product search failed, you just rerun your request, you redid all of the work, which was okay. But now if you have like an agent which takes 5 minutes, 15 minutes and something in the flow breaks and you would start all all over, you would need to spend you need to spend a lot of compute again to like do all of the previous steps. And you also might lose the existing context. So we cannot like just start over the whole process. We need to kind of understand and treat errors differently, provide them back to the model, maybe have some other workarounds, some additional checks that we basically keep going forward in the flow and not like starting over from the beginning.

</details>

### 从单元测试到评估体系 (Evals)

传统软件开发通过单元测试、集成测试保证“输入 A 必得输出 C”的确定性。但 Agent 具有非确定性，无法保证同样的输入产生完全一致的步骤和结果。因此，我们需要从单元测试转向 **Evals**（评估体系）。对于 Agent，我们关注的是其在特定任务中的可靠性（Success Rate）。结果的评估往往是主观的，需要利用“LLM 作为评判者（LLM-as-a-judge）”或人工专家反馈来量化成效。我们需要追踪 Agent 的行为路径，但衡量成功与否的核心依据是最终结果，即便 Agent 在不同用例下采取的步骤数不同。

<details><summary>Original English Source</summary>

The fourth example or step is like we need to move from unit test to evals. So when building software before, right? We wrote integration tests, unit tests, smoke tests and all kind of different tests and we assume that when we provide input A for our code B, we will always get C as an output. And that's no longer the case with agent. Agents are non-deterministic. We cannot always guarantee that the same input will lead to the same steps and the same result. So we need to move from unit tests to eval. We need to test how often something works because agents are only successful if they are really reliable, right? If you have a customer agent and the same prompt only works one out of 10 times, it's nothing really you want to put in production and it becomes very flaky. So we need to test on evals on how many times it passes and compared to traditional software, results are very subjective, right? An outcome can be very different if you ask it to create research report, if you ask it to create a customer feedback kind of scenario. And we need more like qualifying feedback. LLM as a judge or human expert for example is a good way. And we always need to trace what the agent is doing, but we need to create on the output. We Maybe the agent decides for like one user it needs to do like four more steps to do more research than for the other user. It consumes maybe a few more tokens, but at the end the outcome is really what we need to measure and want to measure in terms of success.

</details>

### 语义化 API 与总结

Agent 不具备人类开发者数年积淀的背景知识。一个自解释的 API 方法（如 `delete_item`）在传统开发中清晰明了，但 Agent 只能依赖函数模式、文档字符串（Docstring）和工具定义。因此，我们需要构建“Agent 就绪”的 API，即具备**语义接口**（Semantic Interface）的工具，以明确文档化操作含义和潜在失败场景。

总结而言，Agent 开发的哲学是：**信任，但要验证**。停止强制模型执行死板的单步流程，尊重上下文含义；设计应对非完美模型的恢复机制；建立基于评估的成功指标而非盲目断言；最后，保持“为删除而构建（Build to delete）”的心态，因为软件是可抛弃的，我们会随模型与 Agent 技术的迭代不断重构。

<details><summary>Original English Source</summary>

And then the last part is agents evolve and APIs don't. And if you have worked on the backend and if you have built an API, you might have seen a lot of methods, API endpoints which feel very self-explaining to you like delete item feels very self-explaining if you are working on like the product API. But an agent doesn't see the code, an agent doesn't have the context and the background from all those years from you working on the API. So we need to build APIs or tools which are really agent ready, which are self-documenting with semantic interfaces. I would assume if you have like a product microservice and you have a delete item endpoint with an ID, you don't need to like define a doc string what the ID is or what happens if something fails. But our agents only see like the function schemas and the doc strings and the tool definition. So on the first look, they don't really see what the delete item method does. That's why we need to really adjust to, "Hey, we need methods, tools which are written for agents to be used and not assume long year developer expertise and people who have built the API. So to to summarize everything, we need to give trust, but we also verify. We should stop fighting the model. You should not like try to force the model into this one specific workflow with step one do this, step two do the other thing. We need to preserve meaning. Everything is a context now. We no longer have those very well-defined data structures for all of our applications. We need to design for recovery. Models are not perfect. Agents are not perfect, especially if we have longer running agents. There will be some very weird things happening. So you need to design for recovery. We need to evaluate and then don't only assert. Agents are not 100% reliable. We need to find the right balance between how many times our run need to be successful to provide it to the user. And last but not least, build to delete. Um the bitter lesson is what everyone of us is learning is like software is disposable. We are going to rebuild many, many times the same things with better models, better agents. Things will change. And yes, it's also available on my blog. So if you want to like look a bit deeper with some code examples. And if not, if you have any questions, feel free to to reach out to me and perfect on time. Thanks.

</details>