---
author: AI超元域
date: '2026-01-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Qydk2wlh4YI
speaker: AI超元域
tags:
  - agent-skills
  - decision-tree
  - prompt-engineering
  - autonomous-agents
  - code-review
title: Agent Skills 灵魂技术：利用结构化决策树实现 AI 助手自主编程
summary: 本文深度解析了 Agent Skills 生态中的核心技巧——决策树逻辑。通过在 Markdown 配置文件中嵌入结构化的条件分支、优先级排序和异常处理，开发者可以让 Claude Code 和 Antigravity 等 AI 智能体具备真正的自主决策能力，减少 50%-80% 的手动干预。文章结合实际的代码审查案例，演示了如何根据任务复杂度自动路由工具，并实现 token 节省与效率提升。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Google
products_models:
  - Claude Code
  - Antigravity
  - Gemini CLI
  - Codex CLI
  - Claude 4.5
media_books: []
status: evergreen
---
### 策略性决策：Agent Skills 的灵魂技术

在上期视频中，我为大家演示了在 **Google** 生态中 **Agent Skills** 的基础用法。视频发布后，很多朋友都在问：**Agent Skills** 是否有更高级的玩法，从而能够进一步提升开发效率？答案是肯定的，而且效果非常显著。本期视频我将为大家演示 **Agent Skills** 生态中被开发者称为“灵魂技术”的核心技巧——**决策树**（Decision Tree: 基于逻辑分支的自主判断系统）。

我们要讲的**决策树**并不是机器学习中那种需要海量训练数据的算法，而是一种需要在 `.md` 配置文件中嵌入的结构化 `if-else` 决策逻辑。这种逻辑能让 **Claude Code**、**Antigravity** 等 AI 智能体在执行任务时，具备真正的自主决策能力。我们在使用 AI 编程助手执行特定任务时，AI 经常会反问：“下一步该怎么做？”这让原本应该自动化的工作流变成了琐碎的人机问答。而决策树就是解决这个问题的终极方案。

### 结构化逻辑：实现 AI 智能体的自主化

根据官方文档，**Agent** 是通过 Markdown 文件教会 AI 如何完成特定任务的。而决策树优化，就是在这个 Markdown 文件中显式定义条件、分支优先级排序以及异常处理。通过这种方式，AI 编程助手能够自主判断并选择最佳方案，从而减少 50% 到 80% 的手动干预，大幅提升任务完成效率。

实现**决策树**是目前社区公认的最强大的 **Agent Skills** 高级技巧。本期视频演示的技巧不仅适用于 **Antigravity**，还适用于 **Claude Code** 以及 **Codex** 等任何支持 **Agent** 的 AI 助手。为了直观展示效果，我开发了一个使用决策树方式实现的“代码审查 **Agent**”。它可以让 AI 助手智能判断代码变更类型，并自动路由到最适合的代码审查工具。

### 实战演示：智能代码审查路由系统

在这个 **Skill** 中，我集成了 **Gemini CLI** 以及 **Codex CLI**。AI 助手会根据任务的复杂度自主决策：是选择 **Gemini CLI** 还是 **Codex CLI** 进行审查。在项目开发中，大家习惯使用这类工具对 **Claude Code** 或 **Antigravity** 写的代码进行二次把关。由于 **Codex** 的审查速度较慢，通常只在面对复杂变更或后端技术栈时才被选用；而前端代码则更适合使用 **Gemini** 进行快速审查。

通过决策树，我们不再需要手动指定工具，AI 会自主判断。这不仅让代码审查更专业，还解决了一个头疼的问题：**Token 成本控制**。如果所有任务都调用内置的大模型，会极快地消耗 **Antigravity** 的配额。将特定任务分配给外部的 **Gemini CLI** 或 **Codex CLI**，可以大幅节省核心模型的用量。简单来说，决策树就是通过层层的 `if-then` 条件判断，从根节点到叶节点逐步筛选，得出确定性的结果。

### 底层逻辑：从复杂度评分到故障转移

为了让大家理解这个 **Skill** 的运行机制，我们可以看一下执行流程图。当进行代码审查时，AI 首先会判断当前是否为 **Git 仓库**；如果是，接着判断 **Gemini CLI** 和 **Codex CLI** 是否可用。在两者都可用的情况下，AI 会分析 `git diff` 并根据评分规则计算复杂度。

**路由决策规则**如下：如果代码包含敏感文件、文件数大于 20、行数大于 500，或者涉及数据库迁移与 API 服务层修改，系统将强制匹配到 **Codex CLI** 进行深度分析。如果是纯前端、Python 生态或纯文档变更，且评分较低（小于 6 分），则由 **Gemini CLI** 进行快速反馈。此外，系统还具备**异常处理能力**：如果调用 **Gemini** 时遇到网络错误，决策树会引导 AI 自动切换到 **Codex CLI** 作为备选方案，确保流程不会中断。

### 配置指南：将 Skill 转化为工作流命令

在 **Antigravity** 的配置文件中，我们可以详细看到这个 **Skill** 的定义，包括环境检查、复杂度评分、路由决策、执行命令以及格式化输出等模块。为了方便日常调用，我们可以将这个 **Skill** 封装成斜杠命令。

具体操作非常简单：在 **Antigravity** 的设置中找到 **Workflow**（工作流），新建一个名为 `review` 的工作流。在描述中输入“代码审查，遵循团队标准”，并在内容中引用我们定义好的 **Skill** 标签（如 `@code-review-skill`）。这样，我们只需要在对话框输入 `/review`，AI 就会自动触发整套决策逻辑，完成从代码分析、工具路由到生成修复建议的全过程。通过将决策树应用于更多场景，你的 AI 助手将从一个“提问者”进化为一个真正的“执行者”。