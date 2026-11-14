---
author: AI Engineer
date: '2026-05-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JT3OzDKrucU
speaker: AI Engineer
tags:
  - agent-guidance
  - context-optimization
  - developer-workflow
  - ai-tooling
  - database-management
title: 弥合上下文鸿沟：Supabase 关于 MCP 与 AI Skill 协同实战录
summary: 本文深入探讨了在 AI 代理开发中，如何结合模型上下文协议（MCP）与 AI 技能（Skill）来提升任务执行的准确性。Supabase 的实践表明，单纯的工具集成不足以应对复杂逻辑，开发者需通过“防跳过”指令设计和主观导向的工作流，引导 AI 遵循安全规范并利用现有文档。文章还分享了通过量化评估验证该方案有效性的具体数据。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Supabase
  - Anthropic
  - OpenAI
  - Braintrust
products_models:
  - MCP
  - Claude 3.5 Sonnet
  - GPT-4o
  - PostgreSQL
media_books: []
status: evergreen
---
### 引导的力量：为何工具集成不足以构建可靠代理

在 AI 代理（Agents）的开发生态中，**模型上下文协议**（Model Context Protocol: 允许 AI 模型与外部数据和工具交互的标准协议）与 **AI 技能**（AI Skill: 一种包含指令、脚本和资源的结构化文档，用于引导 AI 代理完成特定任务）的角色定位曾引发广泛讨论。目前的共识是两者各司其职：MCP 提供工具接口，而 Skill 提供执行指南。

即使是目前最聪明的 AI 代理，在面对其训练数据之外的特定产品逻辑或安全规范时，仍显力不从心。以 **Supabase**（Backend as a Service: 提供即插即用后端功能的云服务模型）为例，AI 经常会忽略**行级安全性**（Row Level Security: 数据库中允许根据用户身份限制数据访问的机制）的配置，或者固执地依赖过时的训练数据而不去获取最新的文档信息。因此，开发者需要通过编写 Skill 来为代理提供针对性的优化工作流和安全防线。

<details>
<summary>Original English Source</summary>
Hello everyone. You might have noticed that the titles changed a bit from the one that we have in on the schedule. That's because when I submitted the talk, there's the MCP versus skill debate was still going on was a topic. I think now we settled on they're both different. They all have their own roles and now the I think the debate is more on the MCP versus CLI. So I thought it would be more useful to come and explain how we've wrote our Superbase skill and the lessons that we got from writing the this document... So we I think we can all agree that agents are already smart enough, right? They can do very they're very capable of doing mundane tasks by themselves. But when you present a task about something that they've haven't seen yet or you've updated since they were trained like your product for example, they need the right guidance. For for example, Superbase we noticed that they would usually either miss some some security pitfalls that we have like row level security instructions that they have to set to to basically not expose your app. They could just usually operate on stale knowledge on their training data and they're very lazy to and very stubborn to admit that they don't know and they do need to find fresh information.
</details>

### 安全实战：Skill 在复杂数据库场景中的效用验证

为了验证 Skill 的实际价值，Supabase 团队进行了一项对比实验：要求 **Claude 3.5 Sonnet** 在启用了 RLS 的表上创建 SQL 视图。实验分为仅提供 MCP 工具和同时提供 MCP 加 Skill 两种条件。在 PostgreSQL 中，如果创建视图时不显式传递 `security_invoker = true` 标志，视图将绕过底层表的 RLS 限制，导致数据泄露。

测试结果显示，仅拥有工具访问权限的代理未能识别这一安全隐患，而加载了 Skill 的代理由于获得了明确的知识引导，能够正确且安全地完成任务。这促使 Supabase 正式推出其官方 **Agent Skill**。编写这类文档的复杂度不亚于撰写硕士论文，因为它需要将复杂产品的精髓浓缩为 AI 可理解的规则。**AI 技能**（Skills）本质上是包含 `skill.md` 指令、执行脚本及参考资源的文件夹，通过 Frontmatter 中的名称和描述触发代理的自动发现与加载。

<details>
<summary>Original English Source</summary>
So skills are folders containing instructions, scripts and resources that agents discover, right? Progressively they discover. This is the main selling point of skills and they they have this envelope called front matter where they have the name and the description. This is how the agent is going to decide when to load the skill. Then they have the actual instructions inside the file the main file called skill.md and then optional bundled resources... We gave them just the the MCP on one condition and the MCP plus the the agents the agent skills. And the result was well the expected. If you don't know in Postgres, if you create a skill over a table on top of a table that has RLS enabled, if you don't explicitly pass that that flag over there the security invoker equals true, it will bypass the RLS. So basically the view will expose data that is not this exposed by default on the table. So the agent with the skill with the knowledge was able to get this this information implemented correctly and safely while the one that only had access to the integration to the to the MCP tool did not.
</details>

### 核心设计原则：从“防跳过”指令到单一事实来源

在构建产品级 Skill 时，Supabase 总结了三大核心原则。首先是坚持**单一事实来源**（Single Source of Truth: 确保所有系统使用的都是同一份最新且准确数据的原则）。开发者不应在 Skill 中重复产品文档，而应引导模型去搜索和阅读最新的在线文档。Supabase 甚至实验性地通过 SSH 暴露其文档系统，让 AI 能够像操作本地文件系统一样使用 Linux 工具远程检索信息。

其次，必须意识到“凡是可以被跳过的步骤，最终都会被跳过”。由于调用工具或读取外部文件成本较高，AI 代理往往表现得非常“懒惰”，倾向于依赖内置的训练数据。因此，绝对不能错过的核心信息（如安全检查清单）必须直接写入 `skill.md` 主文件，而不是放在次级的参考资源中。最后，开发者必须保持**主观引导**（Opinionated），将自己认为最高效的工作流强加给代理，不要害怕对 AI 的行为路径进行深度限制。

<details>
<summary>Original English Source</summary>
The first one is that don't duplicate information... Just point the agent to it to the most up-to-date. Provide the guidance. Tell where to and how to find the documentation, but be very persistent with it to go for it. We're basically exposing our documentation through SSH. The main reason behind it is that the agents can now look for the documentation like it was a file system... The second principle is that if something can get skipped it will be skipped. What I mean by this is that besides newer information on searching online, so agents like fetching information online or tool calling it's expensive for for agents. So they mostly default to their training data. The same is true for reference files... You have to be very critical about what you put on your skill.md file from the beginning. You put information that is likely not to change like in our case a security checklist about Superbase that we didn't really wanted the agent to miss at all. And lastly, the third principle is to be opinionated. You know your product the best... Don't be afraid of guiding the agents on what on workflows that you think are the most effective.
</details>

### 优化工作流：以数据库模式管理为例

在 Supabase 的场景下，管理数据库模式（Schema）的最佳实践被固化到了 Skill 中。典型的“主观工作流”如下：代理首先在开发或分段（Staging）数据库上直接进行 DDL 操作自由修改模式；随后调用内置的 Advisor 检查潜在的安全或性能漏洞并予以修复；只有在确认无误后，才生成最终的迁移文件（Migration File）。

这种设计防止了代理在每次微调模式时都产生冗余的迁移文件。通过将这种行业经验写入 Skill，即使是不熟悉 Supabase 工作流的通用模型也能表现得像专家一样。为了量化这些改进，团队利用 **Braintrust** 平台进行了严密的**模型评估**（Evaluations/Evals: 衡量 LLM 输出质量和行为的系统化测试流程）。通过对 4 种模型在多种场景下的测试，结果一致表明：“MCP + Skill” 的组合在任务完成度得分上全面超越了仅有 MCP 或纯基准测试的情况。

<details>
<summary>Original English Source</summary>
In our case for example, managing a database schema... We found that this for our platform was the best workflow for the agents to efficiently manage the schema. So, in this case run direct DDL operations like change the schema freely on your development or staging database. Once you're happy about it, we provide an advisor to our basically linked to give any security or performance issues that the database could have, fix them, and only then create the migration file. This will prevent the agent to create a migration file every time he changes the schema... We ran a set of six specific scenarios for Superbase... and we ran it against four different agents from two vendors in three test conditions... The results are out here. The skills plus the MCP outperform any other conditions on every model that we tested. We tested on Claude Code for Opus 4.6 and Sonnet 4.6 and also on Codex for GPT 5.4 and GPT 5.4 mini.
</details>

### 未来展望：生态分发与语义检索的潜力

尽管 Skill 的效用已得到证明，但其**分发系统**（Distribution System）仍是目前的行业瓶颈。目前各家厂商（如 Vercel、Cursor）都在尝试不同的标准，但尚未达成统一。Supabase 目前采取的做法是将 Skill 打包在对应的仓库中，使其变得可被发现（Discoverable）。此外，随着向量技术的普及，**向量数据库**（Vector Database: 专门用于存储和检索高维向量数据的数据库，常用于语义搜索）在提升 Skill 能力方面展现出巨大潜力。

通过将文档或代码片段转化为向量嵌入（Embeddings），结合**语义搜索**（Semantic Search），可以为 AI 代理提供更精准的上下文增强。例如，在通过 SSH 暴露文档时，不再仅仅依赖传统的 Bash 工具进行检索，而是通过语义增强工具让代理更聪明地定位信息。正如 Pedro 所言，Skill 的构建应该遵循“极简起步、快速迭代”的原则，不断根据 AI 的反馈来修正指令集，最终实现人机协同的最优解。

<details>
<summary>Original English Source</summary>
Currently one of the downsides or the constraints of using skills is their distribution system, right? We're still finding the there's still some players trying to reclaim either the registry or the way to distribute it... Internally, we are packaging the skills on the the repos themselves. So, if you want to create a plugin, you just create a dot Claude plugin or a dot cursor plugin or whatever in that repo... The use cases for for vectors are mainly for embeddings, right? Yeah. And semantic search, right? That you could use to provide even more context. Uh for example, through the SSH exposing the docs through the SSH, you can now instead of naively let them navigate with the the bash tools, you can augment the tools already known bash tools into all providing some sort of semantic search. So, I would do see a very big potential on vectors.
</details>