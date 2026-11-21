---
author: AI Engineer
date: '2026-04-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0n3MKk7r60w
speaker: AI Engineer
tags:
  - mcp-protocol
  - ai-agents
  - infrastructure-scaling
  - context-optimization
  - oauth-security
title: 规模化 GitHub 远程 MCP 服务：从工具爆炸到智能治理的实践指南
summary: GitHub MCP 开发负责人 Sam Morrow 分享了构建与扩展 GitHub 远程 MCP 服务器的核心挑战。文章深入探讨了如何通过工具集动态选择、输出 Token 优化、Agent 意图编码以及 OAuth 步进式授权，解决 AI Agent 在面对海量工具时的混乱与安全难题，并展望了组合式工具调用的未来趋势。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Sam Morrow
companies_orgs:
  - GitHub
  - Anthropic
  - OpenAI
  - LangChain
products_models:
  - Claude Code
  - GPT-4o
media_books: []
status: evergreen
---
### GitHub MCP 的起源与“工具爆炸”挑战

GitHub 的 **模型上下文协议**（Model Context Protocol: 一种允许 AI 模型安全访问本地或远程数据的开放标准）之旅始于去年 4 月。作为 GitHub 上当时星标增长最快的仓库之一，开源社区的极高参与度迅速填补了平台覆盖范围的空白。然而，这种繁荣背后隐藏着危机：随着工具数量迅速突破 100 个，开发团队发现 **AI Agent**（人工智能代理：能够自主调用工具完成复杂任务的系统）的表现不升反降。

研究表明，简单地将大量工具塞入上下文窗口会导致 Agent 产生混乱和遗忘。GitHub 作为一个极其庞大的平台，涵盖了仓库、Issue、PR、Action、Project 等多个维度。为了不限制用户对特定工具的需求，团队必须在保持工具丰富性的同时，解决 Agent 因“选择困难”而引发的执行效率问题。

<details>
<summary>Original English Source</summary>

For GitHub, our MCP journey started well, at least in public in April last year. And we actually open-sourced our local MCP in April last year. And we've just turned 1 year's old. Back then, there was a tremendous buzz. We were the most starred repo on GitHub of the particular week. And the exposure meant we got a high volume of public contributions, rapidly filling gaps in platform coverage. 

After a month or so of new features, agents in some ways were getting worse at using GitHub and context windows were getting blown out quicker. And we picked, I think, over 100 tools. And certainly at the time, that was just too many. LangChain had already produced research that more tools don't make better agents, you know, they get confused and forgetful. Well, I say more tools like more context and more tools shoved directly into the context to be precise. GitHub's a really expansive platform. And we provided tools for repos, issues, PRs, actions, projects, like even more things.

</details>

### 动态治理与上下文的深度“脱水”

针对工具过载，GitHub 尝试了多种优雅的解决方案。首先是引入了 **工具集**（Tool Sets）的概念，将相关功能的工具进行逻辑分组，允许用户根据场景进行配置。此外，还开发了动态工具发现机制，甚至实验了基于 **检索增强生成**（Retrieval-Augmented Generation: 通过检索相关文档来增强模型输出准确性的技术）的语义工具搜索。

然而现实反馈令人意外：绝大多数用户倾向于直接使用默认设置，而不愿手动调整 JSON 配置。这迫使团队转向更底层的自动化优化。通过对使用模式的分析，GitHub 成功将初始加载的上下文缩减了 49%，并对 **增删改查**（CRUD: Create, Read, Update, Delete）工具进行了聚合。更显著的进步在于对输出 Token 的精简，例如通过量身定制 PR 列表的输出字段，成功减少了 75% 的 Token 消耗，显著降低了长对话场景下的运行成本。

<details>
<summary>Original English Source</summary>

To try and fix some of this, I quickly added this thing tool sets, which was a kind of grouping concept of related product tools. And users could pick which ones they wanted and configure it. I also added a dynamic tool selection thing where agents could discover sets of tools and then turn on in chunks. And we never released it, but I made a kind of rag version of the same for semantic tool search and discovery. 

Everyone used the default settings. It was really annoying because we had all these elegant solutions. All they did was require users to actually configure the JSON a little bit. And most users just don't. We needed to find better solutions to context reduction. Initially, we cut the amount of context used by focusing the tools more specifically to the general case, leading to about 49% reduction of the initial load. And then we subsequently also grouped CRUD tools and brought that down even more. We've also recently had a massive push to reduce output tokens of a lot of tools. In this example, just by tailoring exactly what comes with the list pull requests, it's actually lost more than 75% of the tokens used in the output.

</details>

### 强化可靠性：编码意图与评估体系

为了将工具调用成功率稳定在 95% 以上，GitHub 采取了一种“服务端重负载”的策略。他们发现， Agent 的许多失败源于对权限感知的缺失（如不知道自己对哪个仓库有写权限）或过度往返导致的逻辑中断。

GitHub 团队的解决方案是在工具表面直接编码 **Agent 意图**（Agent Intent）。与其让 Agent 连续发起五次 API 调用来完成一个动作，不如在服务端将这些逻辑封装成一个更具鲁棒性的复合工具。这不仅减少了网络往返时间，更显著提升了 Agent 的成功率。在评估方面，他们不再纠结于微调单个工具的描述，而是通过 **Eval**（评估系统）测试工具之间的“平衡感”：确保没有任何一个工具的描述因为过于吸引人而导致 Agent 在不适当的时机滥用它，从而实现工具集整体调用的精确性。

<details>
<summary>Original English Source</summary>

We made a big push to reduce tool failures as well. And the success rate is roughly, I think, over 95% at this point. Not all failure is preventable cuz agents don't necessarily know which repos they have write permission on. They still hallucinate. But we've been able to identify significant numbers of areas that could be overcome, mostly by encoding a sort of agent intent into our tool surface. You might have to make five API calls to make it more robust. But we do that in the server side to reduce round trips cuz that saves context, saves time, and makes a massively better experience.

One of the gists is instead of micro-optimizing individual tool descriptions, you try to test them against each other to try and make sure that they're called at the right times and not called at the wrong times. The perfect tool description that makes the agent call it all the time is terrible as is the reverse of that.

</details>

### 安全博弈：从 PAT 令牌到步进式 OAuth

安全性是 MCP 生态中悬而未决的“常客”。在野外环境中，许多用户依然依赖明文存储的 **个人访问令牌**（Personal Access Token: 用户生成的用于访问 API 的凭据），这些令牌通常具有长效且过度授权的特征。

GitHub 致力于将安全连接变为“阻力最小的路径”。他们不仅在 GitHub 授权服务器上增加了 **PKCE**（Proof Key for Code Exchange: 一种增强 OAuth 2.0 安全性的扩展协议）支持，还引入了 **步进式授权**（Step-up OAuth）。在这一机制下，如果 Agent 调用的工具超出了当前 Token 的权限范围，系统不会直接报错，而是会交互式地向用户发起范围挑战（Scope Challenge）。一旦用户确认提权，工具调用即可无缝继续。此外，系统还会根据 Token 的实际 Scope 动态过滤掉 Agent 可见的工具，从源头上减少了因权限不足导致的失败和上下文浪费。

<details>
<summary>Original English Source</summary>

Security is a kind of constant menace in all of this. We've a lot of people using plain text access tokens for MCP in the wild. They're frequently long-lived. They're often over-privileged. And they're kind of sat there just waiting to be abused. Our remote server supports OAuth 2.1. And my team even helped add the proof key for code exchange support (PKCE) to GitHub's authorization server to improve the security posture.

On OAuth, we support step-up OAuth. We could return a scope challenge and then it will interactively ask the user if they want to allow the scope. And if you do, then you can continue the tool call. It doesn't fail. If you log into GitHub MCP with a PAT token, we immediately filter the tools down by the scopes that the token has. By removing those, we're just removing kind of constant sources of failure and wasted context at the same time.

</details>

### 千万级扩展：无状态架构与 Insiders 模式

GitHub 目前每周处理约 700 万次（最高接近 800 万次）工具调用。为了支撑这一规模，他们构建了一个完全 **无状态**（Stateless: 不在服务器端保留客户端会话状态的架构）的系统。

与许多开发者运行的单一、有状态 MCP 进程不同，GitHub 在收到每个请求时，都会在 SDK 层面实例化一个全新的服务器对象。这个实例会根据当前的策略、配置和权限动态挂载工具。这种设计虽然极端，但确保了极高的灵活性。为了加速迭代，GitHub 还推出了 **Insiders 模式**，通过特性开关（Feature Flags）向愿意尝试的用户提供前沿功能。例如，他们正在测试一种 **人为参与**（Human-in-the-loop）的机制，允许用户在 Agent 生成 Issue 后先进行编辑再发布，这在处理专业的开源协作时尤为重要，能有效避免因自动化痕迹过重而被社区误判。

<details>
<summary>Original English Source</summary>

We run a completely stateless server setup and we have been using Redis for session storage. One of the fun things we did is we actually make a brand new in the SDK sense a brand new server instance on every single request and we add the tools to it at the start. So, whatever your configuration is, it just builds this and then you get what you've asked for. We serve around 7 million tool calls a week. We don't have session affinity.

We have this thing that's a Insiders mode. An example of something that we haven't released generally yet is our MCP apps. It's quite nice when you're talking to the agent to have the opportunity to kind of edit the AI-generated issue especially if you're working heavily in professional open source stuff and you want to make sure that it's you posting and it's not going to get closed as a bot-generated thing. This is a nice human in the loop thing that MCP enables.

</details>

### 未来图景：组合式工具与完全自主化

展望未来，Sam 认为工具的使用将向 **组合化**（Compositional）演进，类似于 Bash 中的管道操作（Piping），数据可以在不同工具间流转。随着搜索 API 的成熟，拥有数千个工具将成为新常态，而过去为了优化而减少工具数量的决策可能会被逆转。

在理想的近未来，用户甚至不需要理解 MCP 是什么。他们只需要表达意图，OAuth 配置和工具选择将实现完全的 **自主化**。GitHub 目前已经拥有近 3 万颗星标和 4000 个派生项目，随着工具调用量持续激增，这套基础设施正面临前所未有的压力。Sam 鼓励开发者尝试更“疯狂”的客户端实现，因为在 Agentic 时代的博弈中，下一个改变游戏规则的创新可能就诞生于这些充满勇气的实验中。

<details>
<summary>Original English Source</summary>

I think a near future, server discovery will hopefully be automatic and tool use will probably become more compositional like bash or piping tools into other tools, streaming data through them. I fully expect that like thousands of tools will be normal very soon. I'll probably reverse many of the fewer tools decisions. And users hopefully won't even have to know what MCP is. They'll just convey what it is they want to do and the OAuth setup and the tool selection things will become truly autonomous. 

GitHub itself has got over 11 million Docker downloads of our standard IO server. We've got almost 4,000 forks which blows my mind. Nearly 30,000 stars and we're fast approaching 8 million tool calls a week. This is really intense, right? And it shows no sign of slowing down. I would encourage people to experiment with crazy clients. You never know, you could publish something that goes so viral it totally changes the agentic game.

</details>