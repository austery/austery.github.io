---
author: AI Engineer
date: '2026-04-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=WE_Gnowy3uw
speaker: AI Engineer
tags:
  - markdown-as-code
  - agent-skills
  - git-worktree
  - software-refactoring
  - evals
title: Markdown 即代码：Cursor 如何用 200 行 Skill 替换 1.2 万行复杂功能
summary: Cursor 工程师 David Gomes 分享了将 Git Worktree 功能从重量级硬代码重构为轻量级 Markdown Skill 的过程。通过利用 Agent Skill 和 Sub-agents 两个原语，Cursor 成功删除了 1.5 万行代码，同时提升了多仓支持与模型对比（Best-of-N）的灵活性。尽管面临模型遵循指令的“幻觉”挑战，团队正通过评估系统（Evals）和强化学习（RL）持续优化这一 AI 驱动的新型软件开发范式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - David Gomes
companies_orgs:
  - Cursor
  - OpenAI
  - Anthropic
products_models:
  - Cursor
  - GPT-4o
  - Claude-3-Opus
  - Claude-3-Haiku
  - Grok
media_books: []
status: evergreen
---
### Markdown 驱动的架构革新：从硬编码到轻量化 Skill

**Markdown**（Markdown: 一种轻量级标记语言）正在成为 AI 时代的新型代码。Cursor 团队近期完成了一项激进的重构：将原本散落在应用各处、充满复杂依赖和测试的 **Git 工作树**（Git Worktree: Git 的一个特性，允许同时检出同一个仓库的多个分支）功能，彻底替换为了一段简洁的 Markdown 指令，即一个 **Skill**（Skill: 赋予 AI 代理特定能力的一组指令集）。

这一转变的核心在于将原本 15,000 行的硬编码逻辑，浓缩为约 200 行的语义指令。这种“以言代码”的模式不仅极大地降低了维护成本，更释放了 AI 在处理复杂任务时的灵活性。

<details>
<summary>Original English Source</summary>
I'm going to be talking about how markdown is basically the new code. We recently replaced a lot of code in the cursor application with just markdown just a skill... going from a fullblown feature with a lot of code a lot of dependencies a lot of complexity and tests into a much more lightweight streamdown version of the same feature effectively but just with a single skill. I recently opened a PR removing this entire feature from cursor and it was a massive deletion of code like I think it was around 15,000 lines of code deleted.
</details>

### Git Worktree：实现 AI 代理的并行协作与隔离

在深入技术细节前，需理解 **Git 工作树**（Git Worktree: 允许在不同目录中同时操作多个分支）在 Cursor 中的作用。它相当于为 repo 提供了多个独立的“平行宇宙”，使得不同的 **AI 代理**（AI Agent）可以同时处理互不干扰的任务。

当用户在 Cursor 中启动一个 Worktree 代理时，代理的所有操作、命令运行和代码检查（Linting）都被隔离在该工作树范围内，不会影响用户当前正在编写的主分支。这一特性还支持 **并行开发**（Parallel Development），用户可以同时在屏幕上开启多个代理网格，甚至让不同模型针对同一任务进行竞争，这种模式被称为 **Best-of-N**（Best-of-N: 让多个模型生成方案并选优的竞争机制）。

<details>
<summary>Original English Source</summary>
Git work trees are effectively like separate checkouts of your repos that allow you to work in parallel. Different agents can be working on the same task at the same time without interfering with each other. Anytime the agent runs commands or lints or anything it does will be isolated and scoped to that git word tree. With this feature, you can have these grids of agents working for you... you can even give the same task to different models at the same time and then compare what different models do on the same prompt. We call it "best of N".
</details>

### 核心原语：Agent Skills 与 Sub-agents 的协同

新的实现方案依赖于 Cursor 的两个核心原语：**Agent Skills** 和 **Sub-agents**（Sub-agents: 由主代理创建并管理的子代理）。通过这两者的结合，原本需要数千行 TypeScript 实现的 `slashworktree` 和 `slashbestofn` 功能，现在仅需 40 到 200 行的 Markdown 描述。

这些指令引导 **父代理**（Parent Agent）执行具体操作：创建子代理、为每个模型分配独立的工作树、运行用户定义的初始化脚本，并最终收集结果进行对比评审。特别是在 `best-of-n` 模式下，父代理会汇总各模型的实现差异，以表格形式呈现优劣，甚至根据用户反馈将不同模型的代码片段“缝合”在一起。这种基于语义的逻辑，比传统的硬编码逻辑更具适应性，且支持跨平台（Windows/Linux/MacOS）指令的动态加载。

<details>
<summary>Original English Source</summary>
We decided that there are two primitives that we could use: Agent skills and the other are sub agents. If we took these two things together, we could basically reimplement both the cursor work feature as well as the cursor best of n feature with just markdown. The best of n skill is very similar... instructing the parent agent to go and create sub agents for each model and then spin up a word tree for each. We tell it to wait for all the subs and when they're done, please provide some commentary. It's only around 40 lines of code and it's all marked down. The previous version was maybe 4,000 lines of code.
</details>

### 权衡之道：灵活性与“幻觉”挑战

虽然新方案极大减少了维护成本并支持了 **多仓并发**（Multi-repo Setup: 同时操作多个独立仓库）等高级场景，但它也带来了挑战。最核心的问题在于 **指令遵循度**（Instruction Following）。

在旧版硬编码中，系统在物理层面禁止代理访问工作树外的文件；而在新版“基于感觉（Vibes-based）”的实现中，团队必须通过 **激进提示词**（Aggressive Prompting）来约束模型不“逃离”其作用域。尤其是在长会话中，较弱的模型（如 Claude-3-Haiku）容易产生 **幻觉**（Hallucination），忘记自己应该待在工作树内。此外，虽然实际运行速度没变，但用户在聊天框看到代理自行创建工作树的过程，在感官上会觉得比系统预处理稍慢。

<details>
<summary>Original English Source</summary>
Now let's talk about some of the cons. It's very hard for the agent to stay on track. With our previous approach, we didn't let the model ever touch any files outside its work. Now we're trusting the model. So it's a bit "vibes based" because we're basically saying "hey operate on this directory" and especially over long sessions it's quite possible that the model will forget. Another con is that it feels slower because you're seeing the agent create the work tree and you're seeing that in your chat.
</details>

### 闭环优化：评估系统、强化学习与未来演进

为了弥补语义指令的不确定性，Cursor 正在利用 **评估系统**（Evals）和 **强化学习**（RL: Reinforcement Learning）进行迭代。通过 **BrainTrust**（BrainTrust: 一种 AI 评估与追踪平台）等工具，团队构建了自动化测试集：在无头（Headless）环境下运行 CLI，使用评分器检查模型是否在正确的目录工作，是否误触了主分支。

目前的评估结果显示，顶级模型如 **Composer**（Cursor 自研模型）和 Grock 表现优异，而小模型仍需通过 RL 针对性训练。未来，Cursor 3.0 将引入更原生、更具“代理感”的界面来优化 Worktree 的交互。同时，团队正在探索超越 Git 的 **并行原语**，旨在解决 Git Worktree 磁盘占用大、创建慢以及仅限于 Git 仓库的局限性，提供更普适的本地并行开发能力。

<details>
<summary>Original English Source</summary>
How can we make this skill better? One is with evals and then using those evals to improve the prompts and then the other one is through RL and training. At cursor, we train our own model called composer. We're working on adding a bunch of these tasks into our RL pipeline. For evals, I've been working on some evals... I spin up the cursor CLI, it's headless. I have two scorers: one checks if the model did work in its work tree, another checks if it did work in the primary checkout. What's next? A much more complete and native work trees implementation in the new cursor agent window. Also looking into other parallelization primitives that are not git work trees.
</details>