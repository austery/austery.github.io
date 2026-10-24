---
author: AI Engineer
date: '2026-05-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=GmAQKINjv1E
speaker: AI Engineer
tags:
  - agent-skills
  - progressive-disclosure
  - evaluations
  - supabase
  - mcp
title: 技能进化论：如何通过 AI 技能赋能 Supabase 智能体
summary: Supabase AI 工具工程师 Pedro Rodrigues 分享了如何通过“技能（Skills）”机制提升智能体的任务执行能力。核心概念包括渐进式披露、Skill.md 的结构化设计，以及如何通过评估（Evaluations）框架实现从手动测试到自动化闭环的转变，解决非确定性输出带来的挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Pedro Rodrigues
companies_orgs:
  - Supabase
  - OpenAI
  - Anthropic
products_models:
  - Claude
  - PostgreSQL
media_books: []
status: evergreen
---
### 智能体体验（DAX）：从传统开发到 Agent 导向的转型

Pedro Rodrigues 介绍了他在 Supabase 的核心工作：**智能体开发体验**（DAX: Developer Agent Experience）。不同于传统的用户体验（DX），DAX 专注于如何让 Supabase 平台对 AI 智能体更加友好。他指出，提升智能体性能的“秘密武器”在于**技能**（Skills）。技能不仅仅是简单的指令，而是一个包含说明文档、工作流脚本和参考文件的结构化文件夹，旨在为智能体提供执行重复任务或处理特定业务逻辑所需的精确上下文。

<details><summary>Original English Source</summary>

My name is Pedro. I'm from Portugal, Lisbon and I work at Supabase as an AI tooling engineer. Essentially my day today is to think of how we can make the Supabase the most agentic friendly as possible and improve the agent experience. So we you've probably heard about development experience the DX. We're more focused on DAX which is the same thing but for agents. In this workshop we're going to talk a bit about skills. Because essentially that's how we've been improving the performance of agents around a product like Supabase or a company like Supabase who has multiple products. The secret sauce has been basically skills.

</details>

### 渐进式披露：解决上下文过载的核心架构

**渐进式披露**（Progressive Disclosure: 根据需求逐步加载信息）是技能机制优于传统工具加载方式的关键。传统的 **模型上下文协议**（Model Context Protocol: 允许 AI 接入外部工具的开放协议）往往在开始时就加载所有工具信息，容易导致上下文溢出。而技能通过 `skill.md` 文件的 **前置元数据**（Frontmatter: 位于文件开头的 YAML 格式描述）实现按需加载：智能体先读取技能描述，只有在判断需要该技能时，才会加载文件内部的详细指令、脚本或关联的参考文件。这种“信封式”的设计让智能体能够高效处理大规模复杂的知识库。

<details><summary>Original English Source</summary>

The main what exactly the skills basically bring that tools like MCP didn't was this concept of progressive disclosure. Progressive disclosure is basically when the agent or all the information about a subject is not loaded straight to context. instead you just load the exact amounts of information that allows the agent to choose to load the rest of the information once it actually needs it. In this case the skill.md file is designed like this. So the front matter will be loaded at first to the context of the agent not the content of the file. This works as an envelope. So the agent knows from the description what the skill does and when it should load the rest of the information inside the file.

</details>

### 技能与 MCP：互补而非替代的博弈关系

Pedro 澄清了关于 **技能** 与 **MCP 工具** 之间的常见误解。他认为两者是互补关系：MCP 侧重于**集成与连接**（Integration: 将智能体连接到远程服务），适用于智能体无法直接访问 Bash 或本地环境的场景；而技能则侧重于**提供深度上下文与定义工作流**（Workflow Definition: 描述具体的操作步骤）。技能可以像一本书的“强化版索引”，不仅包含链接，还定义了如何使用这些工具。此外，技能脚本运行在本地环境，与特定的操作系统环境绑定，而 MCP 则是跨平台的远程调用。

<details><summary>Original English Source</summary>

The debate now is more about MCP versus CLI. But when the skills were released back in November or October last year they basically started this debate about should we use them instead of MCP. And the answer is you should use both to be honest. If you're building anything that it's an integration, you should use MCP. Anything that if your agent doesn't have access to bash, you should use MCP to integrate to your service. Skills actually just provide more context to your agent, right? And you can define workflows everything that you don't have space to define on the MCP tools descriptions you can define them on skills. The main difference is that tools don't need an environment to run... while the scripts are loaded into your machine they run on your local environment.

</details>

### 实战案例：利用安全技能修复数据库权限漏洞

在现场演示中，Pedro 展示了一个性能评估应用的 Bug。当使用 Claude 自动生成一个 PostgreSQL **视图**（View: 存储的查询逻辑，表现得像一张表）时，由于默认情况下视图会跳过 **行级安全性**（Row Level Security: 控制用户只能访问其有权查看的特定行），导致普通员工也能查看到全公司的敏感工资数据。通过引入名为 `supabase-security` 的技能，智能体学习到了在创建视图时必须带上 `security_invoker = true` 标志的知识。加载技能后，智能体不仅修正了 SQL 逻辑，还通过技能定义的检查清单主动验证了安全性，确保了权限隔离的生效。

<details><summary>Original English Source</summary>

We basically created a view. Claude said everything is working because as you can see the information is here. But he missed something specifically for Postgres... when you create a new view, by default it bypasses the role level security that you might have in place already on your table. For this scenario to happen, we have to use a security invoker flag to enable the RLS policies on the view itself. So for the sake of the demonstration of this workshop, I've already prepared a skill for the presentation. Essentially the skill is three main security points about Postgres that the agent should be aware of. Models right now are smart enough to generalize this... every time it's enabled the RLS policies are also enabled on the view itself.

</details>

### 自动化评估：构建 AI 技能的测试闭环

由于 LLM 的输出具有 **非确定性**（Nondeterministic: 同样的输入可能产生不同的结果），传统的单元测试难以胜任。Pedro 介绍了 **评估驱动开发**（Eval-driven Development）流程：首先定义衡量好坏的指标，编写技能，然后运行评估。他特别提到了 **LLM 作为评判者**（LLM as a Judge: 使用一个强大的模型来评估另一个智能体的表现）的模式。通过对比“有技能”和“无技能”两种场景下的执行结果，开发者可以量化技能带来的改进。虽然编写评估用例（Evals）充满挑战且容易出现幻觉，但这是实现技能进入生产环境（Production）的必经之路。

<details><summary>Original English Source</summary>

Since we have an LLM in the loop, you'll have something called evaluations or evals for short. They essentially are a more nondeterministic way of testing the output or the behavior of an agent or a model. This framework was proposed by OpenAI... you start by defining your metrics. Then you create the skill itself. Then you run the evaluations. We instead of having a deterministic output, you can have it's nondeterministic. You can use a technique called LLM as a judge for nondeterministic evaluation. You can give the outputs of an evaluation run to another LLM to give it a grade basically. This is basically your very first evaluation pipeline to test the skill automatically.

</details>

### 生产环境建议：规模化管理与文档化

在问答环节，Pedro 建议将技能视为 **代码库的另一种文档形式**（Living Documentation）。在本地实验阶段，可以大量安装各种技能，利用渐进式披露减轻上下文压力。但在生产环境中，应保持精简，确保技能随业务逻辑同步更新。他推荐将技能文件存放在代码仓库中（如 `agents/` 或 `cloud/skills/` 文件夹），并建议定期审计技能的使用率：如果一个技能长期未被用户调用，就应考虑其存在的必要性。

<details><summary>Original English Source</summary>

For local environment I wouldn't constrain myself on space management or context management because the progressive disclosure is a very powerful thing... Into production, treat them as any artifact that you would have on your CI. Keep it clean. Export skills or make skills available on your repos as like another piece of documentation. So treat skills that you put into production as actual documentation. It's important for you to keep them updated... from time to time you can also create a job to check if the skill is still running a fair workflow.

</details>