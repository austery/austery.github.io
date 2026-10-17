---
layout: post.njk
source: https://yage.ai/share/github-secure-code-game-prodbot-20260728.html
speaker: yage.ai
title: |-
  别再依赖提示词防 Agent 了：从 GitHub Secure Code Game
  看红队攻防的 5 级提权
date: '2026-07-28'
summary: 文章介绍了 GitHub Secure Code Game Season 4 中引入的 ProdBot 靶机，旨在通过自然语言交互诱导 Agent 绕过权限检查读取敏感文件。文章详细拆解了从传统代码安全到 Agentic AI 安全的五个提权级攻击路径，包括 Shell 解释器漏洞、网页内容注入、工具链上下文污染、跨 Session 记忆持久化以及多智能体混淆代理人机制，强调了防御策略应从文本提示词转向架构设计和物理隔离。
area: tech-engineering
category: ai-application
tags:
  - agentic-security
  - red-teaming
  - prompt-injection
  - software-development
  - multi-agent-system
people: []
companies_orgs:
  - GitHub
products_models:
  - ProdBot
media_books: []
draft: true
status: evergreen
---

GitHub Security Lab 于 2026 年 7 月 24 日推出了 Secure Code Game
Season 4。在这次的赛题中，官方设计了一个名为 ProdBot 的靶机。

ProdBot 的通关目标：通过自然语言交互，诱导 Agent
绕过权限检查与隔离机制，读取存放于沙箱目录之外的敏感文件
../password.txt。

如果你想亲自上手体验这个 CTF，建议先点击 GitHub Secure Code Game 启动 Codespaces
尝试通关；玩过一轮或者卡住后，再回来对照下面的 5
级提权拆解与红队视角。

GitHub Secure Code Game
赛季演进：从传统代码到 Agentic AI

## 从 Season 1 到 Season
4：应用安全的范式演进

回顾 GitHub Secure Code Game 的演进轨迹，恰好映射了过去几年软件工程与
AI 发展的完整脉络：

Season 1（基础应用安全）：聚焦传统 Web 与系统安全，使用 Python 与 C 语言，演练 SQL 注入、内存溢出和路径遍历等经典漏洞。

Season 2（多栈与供应链安全）：跨越到 CI/CD 管线与基础设施，围绕 Go、JavaScript 和 GitHub Actions，演练自动化构建与依赖项安全。

Season 3（LLM 模型安全）：首次引入大语言模型，聚焦基础的 Prompt 注入、输入输出过滤与 LLM 文本交互的安全边界。

Season 4（Agentic AI 智能体安全）：以 ProdBot 为核心，演练当模型拥有命令行执行、网页浏览、MCP 工具调用、持久记忆与多智能体协作等自主行动能力时的复杂攻击面。

对于 AI 应用开发者而言，Season 3 与 Season 4
显然与我们最为相关。如果说 Season 3 防范的是“模型文本通道被污染”，那么
Season 4 则直击当代 Agent
系统的软肋——当模型从“只能聊天”升级为“拥有工具与行动权”时，攻击者是如何在真实环境里完成提权的。

当一种攻击模式被收录进 GitHub
的入门级赛题时，说明它已经从学术论文和黑客试验场走出来，成为了大众红队的标准技能。

## Level 1：当关键词拦截遇到
Shell 解释器

在防护 Agent 执行 Bash 命令时，不少开发者最直觉的做法是写一句严格的
System
Prompt（如“严禁执行危险命令”），或者在代码里加几行敏感词判定，试图拦截包含
.. 或 password 的输入字符串。

攻击者没有硬碰硬地输入 cat ../password.txt，而是利用了
Shell 自身的变量扩展与字符串拼接机制。通过传入类似
D=..; cat $D/pass"word".txt 这样的指令，或者使用 Base64
编解码语句，将原本敏感的路径在表面上拆解得干干净净。Agent
在接收到需求后，顺理成章地生成了这段看似合规的脚本。

这暴露出字面量校验在动态解释器面前的局限。前端或 Guardrail
校验只能检查静态文本，避开了对变量 D 和拆分字符串
"word" 的拦截；然而当这段命令投递给 Bash 解释器时，Bash
在运行期完成了变量扩展与字符串拼接，精确还原出了越界读取敏感文件的真正动作。

## Level 2：隐藏在网页里的控制权

进入第二个关卡，系统禁止了直接请求敏感文件的指令，但在处理常规任务（例如“帮我总结这个网页的内容”）时，允许
Agent 访问外部 URL 并读取网页内容。

攻击者并不在对话框里直接下达恶意命令，而是将攻击语句嵌入到 Agent
需要抓取的外部网页中。网页内部放置了带有高优先级覆盖语气的 Prompt
说明，要求读取沙箱外的文件。

当 Agent 调用 Web 浏览工具把网页抓取回来时，外部数据被直接填入了 LLM
的 Prompt
上下文中。在当前大语言模型的架构中，从外部读取的数据与系统原有的控制指令共享同一个上下文空间。Agent
无法识别这段文本究竟是“被分析的客观数据”还是“必须遵守的最高指令”，最终顺从地执行了网页中的恶性文本，调用底层能力拿到了敏感文件。

## Level 3：被毒化的上下文通道

系统在第三关引入了基于 MCP 架构的工具链，为 Agent
提供了标准化的工具调用机制，试图通过协议规范来管控输入和输出。

攻击者将攻击逻辑隐藏在 MCP
工具的说明文档（Docstring）中，或者通过上游工具的返回数据进行注入。

Agent
在挑选工具或接收工具输出时，解析了这些包含恶意指令的说明与文本。上游工具返回的数据像一把“毒匙”，诱导
Agent
在调用后续的高权限工具时，把包含越界读取路径的参数透传了过去。协议本身能够约束参数的格式，却无法鉴别上下文里的自然语言内容是否受过污染，导致工具链形成了连锁失控。

## Level 4：跨 Session
的隐蔽提权

到了第四关，Agent 挂载了具备全局文件与网络读写能力的 Skill
插件，并启用了跨 Session 记忆功能，以支持连续的自动化任务。

攻击者在一次看似普通的对话中，诱导 Agent
将特定的恶性状态写入持久化记忆数据库；或者通过特定条件唤醒拥有高权限的
Skill。

在随后发起的全新对话中，用户仅仅发起了一项合规的日常查询。然而 Agent
在初始化时读取了被毒化的历史记忆，将旧有的恶意上下文混入了当前决策逻辑，自动触发了具备全局读写能力的
Skill 去读取沙箱外的敏感文件。持久化记忆打破了对话 Session
之间的隔离边界，把一次性注入转变为长期的持久化后门。

## Level 5：帮凶竟是我自己

Multi-Agent 混淆代理人（Confused
Deputy）提权机制

在最终关中，系统采用了多 Agent 协作架构。低权限的 Subagent
专门用于处理不可信的外部输入，高权限的 Parent Agent
则负责指挥与调度。

攻击者向低权限 Subagent 提交恶意数据。Subagent
在完成处理后，将包含了恶性指令的内容写入了生成的中间工件（Child
Artifact）中。

当高权限 Parent Agent 提取并解析这个 Child Artifact
时，它缺乏对工件内部数据来源的显式鉴别，把工件里的攻击语句误认为是来自
Subagent
的合法控制指令并予以执行。这是典型的混淆代理人场景：虽然架构上设计了高低权限隔离，但
Parent Agent 盲目信任了 Subagent 产出的工件，低权限 Subagent
无意中成为了攻击者的帮凶，替攻击者骗取了高权限执行权。

## 实践者的落脚点：从文本防御走向物理隔离

拆解完 ProdBot 的这 5 个关卡，红队视角的变迁非常清晰：Agent
攻防的本质不是在语言层面去“猜模型会做出什么回应”，而是跟踪指令与数据如何在系统架构中流转。

单靠 Guardrail 提示词去“劝阻”模型，都无法在 Shell
语法扩展、上下文混淆、工具链毒化、记忆持久化和多智能体工件传递面前提供确定性防御。

真正稳固的安全边界，不能建立在对自然语言输出的概率预测上，而必须落在架构设计上：将
Shell 命令行限制在严格隔离的物理沙箱中，在 MCP 和 Skill
层面实施最小权限原则，并在多 Agent
架构中对工件内容进行严格的上下文解耦与数据溯源。