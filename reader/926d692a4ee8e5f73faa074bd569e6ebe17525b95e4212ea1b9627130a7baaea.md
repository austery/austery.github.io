---
author: AI Engineer
date: '2026-05-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Xfl50508LZM
speaker: AI Engineer
tags:
  - evaluation-framework
  - observability
  - prompt-engineering
  - agentic-workflow
  - llm-reliability
title: AI Agent 评估实战：从“氛围感”驱动转向工程化闭环
summary: 本文基于 Arize AI 开发者体验负责人 Laurie Voss 的深度分享，系统性地阐述了 AI Agent 的评估（Evals）体系。文章探讨了从 Trace 追踪到代码评估、LLM 评判（LLM-as-a-judge）及元评估的全流程，并提出了“数据质量 > 提示词 > 模型”的优化层级，旨在解决 AI 开发中难以量化和回归的问题，助力开发者建立可靠的 Agent 迭代飞轮。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Laurie Voss
companies_orgs:
  - Arize AI
  - Anthropic
  - OpenAI
products_models:
  - Arize Phoenix
  - Arize AX
  - Claude
  - GPT-4
  - Claude Code
media_books: []
status: evergreen
---
### 评估基石：从日志到 Trace 的语义转换

在构建 AI 系统时，传统的服务器日志（Logs）已不足以支撑复杂的非线性交互。我们需要引入 **Trace**（追踪：记录 AI 运行全过程的原始数据）的概念。Trace 是评估的基础，它由多个 **Span**（跨度：执行过程中的单一步骤，如一次 LLM 调用或工具使用）组成。这种嵌套的 JSON 结构不仅记录了输入和输出，还包含了耗时、Token 计数等元数据。通过 **Open Inference**（开放推理：一种专为 LLM 设计的 hotel 扩展协议）等标准，开发者可以自动捕获 Agent 的每一步决策，从而将黑盒化的模型交互转化为可观测的结构化数据流。

<details><summary>Original English Source</summary>
You can think of traces, you can think of ebals as being tests because that is what they are. And the things that power our tests are log data. And the log data we call traces. Um so just as logs record what your server did at runtime, traces record what your AI did. Every agent call, every tool call, every LLM invoc invocation, all of the inputs and outputs from your AI application uh are recorded as traces. uh and the building blocks of traces are called spans. Um each span represents one step uh in the execution. So an LLM call is a span, a tool call is a span, uh a full agent turn is a span that contains other spans inside of it. It's this nested data structure uh that you know can be easily imagined as JSON because it is JSON a lot of the time. Um each span records the its input, its output, but also a bunch of metadata. Uh so things like timing and token count token counts uh stuff that you need to understand what went on.
</details>

### 破解“氛围感”陷阱：为什么 Agent 评估迫在眉睫

AI 开发中普遍存在 **Vibes Problem**（氛围感问题：开发者通过几次随机查询感觉输出“还行”就上线），但这在面对边缘案例或敌对输入时会迅速崩塌。对于 Agent 而言，评估的难度呈指数级增加，因为它们具有 **Cascading Failures**（连锁反应故障：早期步骤的微小偏差会导致后续路径彻底偏移）。传统的单元测试由于无法处理 LLM 输出的非确定性而失效。因此，我们需要 **Evals**（评估：针对 AI 输出的系统化测试套件）来支持系统提示词的优化、模型的无缝升级以及防止回归。只有建立起覆盖多维度（如正确性、语气、安全性）的评估体系，才能确保 Agent 在生产环境中的鲁棒性。

<details><summary>Original English Source</summary>
The reason we need AI eval is because of the vibes problem. Uh a lot of people build an AI feature and test it by running a few queries and sort of going does this look right? Um, then you ship it and it fails on inputs that you didn't test. It fails on edge cases. It fails on people being adversarial... so the usual fix unit test doesn't work here. Uh, and the reason that's true is because the same prompt will produce different text on every single run, but those outputs, those different outputs might all be correct. There's a huge uh, space of potential correct outputs. So you can't just have basic string matching like most unit tests do... but agents make it even harder because agents have cascading failures. Uh, and in an agent, you have not just one thing that you are testing, but a series of things. You have an agent that that can take any number of paths. And an early misstep on one of those paths can uh lead the agent to radically incorrect directions.
</details>

### 评估三剑客：代码、LLM 评判与人类反馈

有效的评估体系并非单一方法的堆叠，而是遵循 **Swiss Cheese Model**（奶酪模型：通过多层互补的防御来阻断故障）。
1. **代码评估**（Code Evals: 确定性的 Python/TS 函数）：用于校验 JSON 格式、长度限制、禁止词等低成本、高速度的硬性指标。
2. **LLM 评判**（LLM-as-a-judge: 使用更强大的模型作为裁判）：处理语义层面的判断，如正确性（Correctness）和 **忠实度**（Faithfulness: 检查输出是否严格依据上下文而非幻觉）。
3. **人类评估**（Human Evaluation: 黄金标准）：虽然难以规模化，但其产生的 **Golden Data Set**（黄金数据集：经人工标注的已知正确答案集）是校准前两者的基石。通过这种分层架构，开发者可以兼顾评估的成本、速度与准确性。

<details><summary>Original English Source</summary>
I wanted to introduce the Swiss cheese model. Uh this diagram blatantly stolen from anthropics blog post. Uh it's a concept borrowed from safety engineering. Uh you have to imagine each layer of defense as a slice of switch Swiss cheese. There is no set of evals that are going to be perfect... Stacking your eval layers works like that as well. Uh so your code eval catches a bunch of really basic stuff first. Your LLM as a judge catches reasoning gaps but misses subtle hallucinations. Your human review uh captures captures things that got through the first two layers... there are two types of evals. There are code evals uh which are deterministic functions you write yourself... the big advantage of code eval is that they're super fast and super cheap and totally reproducible... with LLM as a judge use a second LLM to judge the output of the first LLM. Usually you use an LLM that is more powerful than the one that you put into production.
</details>

### 编写高标准评判准则：从模糊到可观测

构建自定义 **Rubric**（评分准则：定义评估逻辑的提示词模板）时，必须避开“输出是否优秀”等模糊描述，转而使用具体且可观测的标准。一个成功的准则包含五个核心要素：明确法官角色、具体的判断标准（如“是否包含买入/卖出建议”）、清晰的数据界定（使用 XML 标签）、**Few-shot Examples**（少样本示例：展示正面与负面案例）以及受限的输出格式（如仅输出二元分类结果）。此外，引入 **Chain of Thought**（思维链：要求法官先输出推理过程再给出分数）能显著提升评判的准确度，使评估结果不仅具备得分，还具备可指导提示词优化的解释性。

<details><summary>Original English Source</summary>
Every good eval prompt I've seen has uh five five different parts... First one is defining the judge's role. Uh you have to give the judge domain context... Part two is your criteria and this is where you should be as explicit explicit as you can possibly be. Uh this is where a lot of people underinvest. So like I said, don't say a good response because that is an aspiration... instead, list exactly what makes a report actionable... Part three of a good rubric is you should present the data clearly... Part four is adding labeled examples and this is the part that most people skip and it is by far the most useful thing that you can add... Part five is you should constrain the output... Just tell me whether it's actionable or not actionable... Chain of thought for judges uh demonstrabably improves how the judges work. Uh so you tell it to explain its thinking first before it outputs that label.
</details>

### 闭环优化策略：数据飞轮与影响层级

评估的最终目的是驱动 **Data-driven Prompt Engineering**（数据驱动的提示词工程）。在面对评估失败时，开发者应参考 **Impact Hierarchy**（影响层级）进行优先级排序：
- **数据质量**（Data Quality）具有最高影响力：若检索源有误，任何提示词优化都无济于事。
- **提示词优化**（Prompting）次之：通过 Few-shot 或明确约束解决 80% 的问题。
- **模型选择**（Model Selection）与超参数调节处于底层：通常成本最高且边际收益最低。
通过不断的“观测-评估-标注-实验”循环，开发者能建立起 **Data Flywheel**（数据飞轮），将今日的生产环境故障转化为明日的回归测试用例，从而构建出基于私有数据的竞争壁垒。

<details><summary>Original English Source</summary>
This eval iterate cycle is where the real value lives in evaluation. Uh you get your results, you improve your results, and you slowly improve your app... this is the impact hierarchy that I mentioned right at the beginning. Uh the impact hierarchy tells you where to focus first. Data quality fixes have by far the highest impact... Once you're sure that the data you're giving to your agent is high quality, uh prompting improvements are the next highest thing to do... and then model selection comes third... and then hyperparameter tuning... they very seldom make a meaningful difference... the more expert judgment you add, the bigger your golden data set, the better your evalu... and each iteration compounds. This creates a differentiated data set that becomes a competitive advantage... This creates a moat that other people don't have.
</details>