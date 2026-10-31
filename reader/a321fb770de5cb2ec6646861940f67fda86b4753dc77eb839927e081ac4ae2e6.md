---
author: AI Engineer
date: '2026-05-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bSG9wUYaHWU
speaker: AI Engineer
tags:
  - context-engineering
  - ai-coding-agent
  - devops
  - llm-evals
  - software-lifecycle
title: 上下文即代码：构建上下文开发生命周期 (CDLC)
summary: Patrick Debois 提出了“上下文即代码”的核心理念，主张参照 DevOps 模式建立“上下文开发生命周期” (CDLC)。他详细阐述了上下文的生成、测试（Evals）、分发、观察和安全性，强调在 AI 编程时代，优化上下文（燃料）比关注模型（引擎）更为关键，并提倡从个人创作转向团队协作的工程化模式。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Patrick Debois
companies_orgs:
  - Tessl
  - Snyk
  - OpenAI
products_models:
  - Claude
  - Gemini
  - MCP
media_books: []
status: evergreen
---
### 上下文即代码：从 DevOps 到 CDLC 的演进

Patrick Debois（DevOps 术语的奠基人）在演讲中提出了一个极具前瞻性的观点：**上下文是新的代码**（Context is the new code）。随着 AI 编程代理（Coding Agents）的普及，开发者正从直接编写代码转向通过 **提示词**（Prompts）和 **上下文**（Context）来驱动开发。Debois 认为，正如 2009 年 DevOps 将运维工程化一样，现在我们需要将上下文的处理流程工程化，构建所谓的 **上下文开发生命周期**（Context Development Life Cycle: 参照软件开发生命周期，对 AI 上下文进行生成、测试、分发和监控的闭环流程）。

这个生命周期被抽象为一个无限循环：生成（Generate）、测试（Evaluate）、分发（Distribute）、观察（Observe）并不断迭代。他指出，单纯的“氛围编程”（Vibe Coding）是不够的，必须通过严谨的工程手段来确保上下文的质量。

<details>
<summary>Original English Source</summary>

I would say like context is the new code because it's being generated. In 2009, I don't know if there is any DevOps people in the room. It was kind of me saying like what if ops looked more like dev? And then we got like, hey, collaboration, kind of our deployment, all that stuff. So, kind of, you know, last year I started thinking, what if context is the code? How do we deal with this in a more consistent way? And it's basically saying if we have a software development life cycle, how does a context development life cycle look like? Because we're basically shifting somewhere else. It's context, it's not code.

</details>

### 上下文的生成与管理：从碎片到标准

在 **生成**（Generate）阶段，上下文不仅限于简单的提示词，还包括 **可重用指令**（Reusable Instructions，如 `agent.md` 或 `Claude.md`）、实时拉取的库文档、以及通过 **模型上下文协议**（Model Context Protocol: 一种标准化的 API，用于将外部数据源连接到 AI 模型）接入的 GitHub、Slack 或 Jira 数据。

Debois 特别提到了“技能”（Skill）的概念。他举例说，与其编写复杂的逻辑来适配不同的包管理器，不如定义一个“技能”，指导 AI 先识别用户的环境再执行步骤。这种做法将复杂的硬编码转化为可重用的工作流上下文。此外，**规格说明驱动开发**（Spec-driven Development）正成为新趋势，即先编写高层级的 Prompt 规范，再由代理拆解执行。

<details>
<summary>Original English Source</summary>

A little bit more advanced maybe is I see myself having a tendency is I had large pieces of code that I was using maybe some helpers and some other pieces. And I just turned them into a skill. Luckily, there's a little bit of a standardization now happening where it's like an agent.md and some pieces like that. We can also bring other context in. If we have documentation of libraries that we use day to day, we want to pull that in because the LLMs might not have the latest documentation. pull context from wherever. MCP. Get it from your GitLab, GitHub, kind of Slack.

</details>

### 上下文测试：引入 Evals 与 Linter 机制

当你修改了两行 `Claude.md`，你如何知道它的影响？Debois 强调了 **评估**（Evaluate）的重要性。他将上下文测试类比为代码测试：
1.  **Linter（校验器）**: 验证上下文格式是否符合规范（例如描述是否过长）。
2.  **语义检查（类似 Grammarly）**: 询问 LLM 是否能理解你写的上下文，获取其完整性和清晰度的反馈。
3.  **单元测试与评判（LLM as a Judge）**: 设定具体的准则（例如：所有 API 必须带有 `awesome` 前缀），运行 AI 代理生成代码，再让另一个 LLM 充当裁判，通过正则或逻辑判断生成结果是否合规。
4.  **端到端测试**: 给“裁判”提供沙箱工具，让它实际运行生成的代码（如执行 `curl`），验证功能是否真正实现。

他指出，由于 LLM 具有 **不可确定性**（Undeterministic），测试必须多次运行（如 5 次）并观察通过率。

<details>
<summary>Original English Source</summary>

You have to think about how do we test things? It's not just about we have a piece of code and we have a piece of context now. We need to write tests to see what is the impact. The simple one could be linting. Validation of a skill where we say, well, you need to have the description. Think of this as a Grammarly. Can the agent understand what you're writing? If you write two words, it's not verbose enough. You can ask it to kind of judge your code based on your criteria and whether it did the right thing. When you give the judge a tool, and the judge becomes an agent, and it can do things in a sandbox and execute stuff. It can actually do the curl.

</details>

### 分发、观察与安全：构建企业级上下文生态

在 **分发**（Distribute）和 **观察**（Observe）阶段，上下文演变为可安装的包。Debois 预测会出现 **上下文注册表**（Registry），类似于 npm 或 Maven。然而，他也警告这将带来“依赖地狱”和安全风险。**上下文安全性** 需要像扫描代码一样扫描上下文（如 Snyk 的做法），防止凭据泄露或 **提示词注入**（Prompt Injection）。

为了优化上下文，我们需要闭环反馈：
*   **日志分析**: 查看代理日志，识别 AI 在哪些地方因为缺乏上下文而失败。
*   **PR 反馈**: PR 中的人工评审意见实际上是对上下文质量的反馈。
*   **生产环境监控**: 监控生成的代码在生产环境的表现，若失败则自动创建测试用例并反馈给上下文层。

最后，他总结道：LLM 只是“引擎”，上下文是“燃料”。如果我们给引擎加了错误的燃料，它就无法发挥性能。开发者应该通过工程化手段优化上下文，而不是仅仅依赖复制粘贴和祈祷。

<details>
<summary>Original English Source</summary>

Think of this like Imagine you have a reusable context that you want to reuse across multiple projects. So, what if we package kind of pieces of context, and then we are able to install pieces of context that we need for this project. That's a registry. Snyk has a way of scanning context, it's doing some credential handling. I call that a context filter. Think of this as a web application firewall that just filters out any patterns or prompt injections. The way that I see it is they're just the engine. If you give the engine the wrong fuel, which is context, they're not going to perform.

</details>