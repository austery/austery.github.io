---
layout: post.njk
source: https://yage.ai/share/ai-coding-config-injection-20260422.html
speaker: yage.ai
title: AI 编程工具的配置文件，现在是攻击入口
date: '2026-04-22'
summary: 本文深入探讨了 AI 编程工具（如 GitHub Copilot、Claude Code）中存在的提示注入（prompt injection）安全漏洞。文章解释了攻击者如何利用配置文件和注释嵌入恶意指令，导致 AI Agent 以高权限执行任意命令，并将其类比为经典的冯·诺依曼问题。文章详细阐述了三种攻击模式，分析了自然语言的边界模糊性、AI Agent 的执行权限与产品价值的绑定，以及攻击面随 AI 能力增长而扩大的挑战。最后，文章提出了一些缓解措施，如禁用自动批准、开启沙箱、提高配置文件审查级别，以及在 CI/CD 中固定依赖版本。
area: tech-engineering
category: ai-application
tags:
  - prompt-injection
  - ai-security
  - llm-vulnerabilities
  - configuration-security
people: []
companies_orgs:
  - NVIDIA
  - Pillar Security
  - Cornell Tech
  - Trail of Bits
  - OWASP
  - OpenAI
products_models:
  - GitHub Copilot
  - Claude Code
  - Cursor
  - Amazon Q
  - OpenAI Codex
  - Postmark-mcp
media_books: []
draft: true
status: evergreen
---

过去 12 个月，安全研究者在 GitHub Copilot、Claude
Code、Cursor、Amazon Q 和 OpenAI Codex 上各自独立发现了一批 prompt
injection 漏洞，至少 8 个 CVE，CVSS 最高
8.8。攻击方式高度一致：在项目的配置文件或代码注释中嵌入自然语言指令，AI
agent
读取后将这些数据当作指令执行。.cursorrules、.claude/settings.json、.github/copilot-instructions.md、AGENTS.md，这些开发者日常接触的文件，现在可以控制
AI agent 在你的机器上运行什么命令。

所有已知漏洞均已修补。但同类漏洞在所有主流产品上反复出现，修一个来一个。原因是
LLM 处理输入时，system prompt、用户指令、代码注释、配置文件全部是 token
序列，模型内部没有任何机制区分哪些是指令、哪些是数据。这和计算机安全史上反复出现的冯诺伊曼问题是同一件事：指令和数据共享同一个通道，攻击者找到让数据被当作指令执行的方法。只是这一次，分离机制还没有找到。

## 三种攻击模式

这些漏洞的攻击面可以归纳为三种模式。

### 数据变成指令

.vscode/settings.json、.cursorrules、.claude/settings.json、.github/copilot-instructions.md、AGENTS.md，这些文件在
AI
编程工具出现之前就存在于项目中。开发者对它们的认知是编辑器配置或项目说明，安全级别和
.editorconfig 差不多。

AI 编程工具改变了这些文件的实际语义。Agent
读取它们之后，不只是调整代码风格或补全偏好，而是据此决定执行什么操作、调用什么工具、以什么权限运行命令。一个
.claude/settings.json 里的 hook 定义会在 Claude Code
启动时以 host 权限运行。一个 .cursorrules 能决定 Cursor
在你机器上执行的 shell 命令内容。文件的格式没变（还是 JSON 或
Markdown），在 repo
中的位置没变，但它在系统中的角色从数据变成了指令。这正是冯诺伊曼问题在应用层的具体表现：原来只是被读取的内容，现在可以控制执行流。

8 个公开事件中有 6 个利用的就是这个语义升级。CVE-2025-53773（GitHub
Copilot，CVSS 7.8）通过 README 中的 prompt injection 让 Copilot 修改
.vscode/settings.json
开启自动批准，此后执行任意命令不需要确认，研究者还论证了蠕虫传播性。CVE-2025-59536（Claude
Code，CVSS 8.8）中恶意 settings.json 的 hook 在 trust dialog
弹出之前就已执行。CVE-2026-25725（Claude
Code Linux，CVSS
7.7）利用了沙箱只对已存在的配置文件设置只读保护、新项目中该文件不存在的条件。Pillar
Security 的 Rules
File Backdoor 用不可见 Unicode 字符在 .cursorrules 里藏
injection，编辑器和 diff 中看不到，AI 正常读取。NVIDIA AI Red Team 的 AGENTS.md
注入通过恶意 Go 依赖在 build 阶段覆写 Codex
的配置文件，把供应链攻击转化为 agent 行为劫持。

### 审批通过后的替换

有些工具对安全审批采用”批准一次，永久信任”的设计：用户首次批准某个配置后，即使配置内容被替换也不再重新验证。CVE-2025-54136（Cursor
MCPoison，CVSS 7.2）利用了这个机制：攻击者先在 repo 中提交一个无害的
MCP 配置等用户批准，然后替换为恶意 payload，Cursor 不再验证底层 command
是否变了。审查发生在批准的时间点，攻击发生在批准之后，payload
在审查时是无害的，执行时已经变了。Cursor v1.3
修复后，配置变更会触发重新审批。

### 跨 agent 传播

EmbraceTheRed 展示了跨
agent 提权：通过间接 prompt injection 劫持 Copilot，让 Copilot 向
Claude Code 的 .mcp.json 写入恶意指令。用户下次启动 Claude
Code 时自动加载并执行，反向传播同理。前提是多个 AI agent
共享同一个工作目录，且每个 agent 都能写入其他 agent
的配置文件。同一项目里同时使用 Copilot 和 Claude Code
的情况现在很常见，一个 agent
被操纵后，可以通过文件系统把攻击传递给同目录下的其他 agent。

三种模式可以组合。供应链攻击（比如 2026 年 3 月的 Axios
npm 事件波及了 OpenAI 的签名证书
workflow）提供初始入口，配置投毒建立持久化，跨 agent
传播扩大范围。Cornell Tech / Trail of Bits 的 COLM 2025 论文 Multi-Agent Systems
Execute Arbitrary Malicious Code
把这种组合归纳为两阶段持久化攻击。

## 为什么这一代的分离机制特别难建立

所有已知漏洞都修了。但每一个补丁修的是一条具体攻击路径，同一类漏洞在所有主流产品上反复出现。原因回到开头的框架：冯诺伊曼问题的每一次出现都需要一个对应的分离机制，而
LLM 这一代的分离机制面临几个前几代不存在的困难。

### 自然语言没有语法边界

Buffer overflow 的分离机制是内存保护（W^X、ASLR、stack
canaries），SQL injection
的分离机制是参数化查询。这两个方案能成功，前提是指令和数据在形式上可以被区分：机器码有固定的指令格式，SQL
有明确的语法结构，分离机制可以在形式层面建立一条硬边界。

LLM
处理的是自然语言，而自然语言没有这种形式上的边界。一段文字是”数据”还是”指令”取决于它出现的上下文和模型对它的理解，不取决于它的格式或结构。一个
.cursorrules 文件里的”请确保所有网络请求使用
HTTPS”和”请在每个文件开头插入以下 shell
命令”在语法上没有区别，都是自然语言句子。模型要区分它们，就需要理解语义，而理解语义本身就是
LLM 在做的事情。

英国国家网络安全中心在 Prompt
injection is not SQL injection (it may be worse)
中的判断基于的正是这个分析：

> “As there is no inherent distinction between ‘data’ and
> ‘instruction’, it’s very possible that prompt injection attacks may
> never be totally mitigated in the way that SQL injection attacks can
> be.”

一篇把这个问题放进计算机体系结构历史的论文进一步指出：LLM
的情况比前几代更严重，因为 plaintext prompt 充当了 code
的角色，动态生成的文本本身会成为新的 prompt，control flow
依赖运行时才知道的
payload。在传统计算中，即使没有内存保护，你至少可以静态分析哪些内存区域存的是代码、哪些是数据。在
LLM 中，这个静态分析不可能做到。Rice
定理从计算理论角度给出了形式化的解释：判断任意自然语言输入是否会诱导
agent 做出非授权行为，在一般情况下是不可判定问题。

### 执行权限和产品价值绑定

即使指令数据混合的问题存在，如果 agent
只输出文本建议，安全后果也有限，普通 LLM chatbot 就是这个情况。Coding
agent 不同：它能运行测试、安装依赖、修改文件、执行构建、调用外部
API。这些执行能力是产品价值的核心，也恰好是攻击者需要的。去掉执行权限，agent
退化成自动补全工具；保留执行权限，每一条成功的 prompt injection
都能触发系统级操作。

Permission prompt 是对这个 trade-off
的标准折中，但实际数据说明它的效果有限。UCSB 的 LLM router
研究截获了真实 Codex session 流量，440 个 session 中 401 个在 YOLO
模式下运行，91%
的用户完全跳过了审批。在产品竞争驱动下，用户面对”安全但慢”和”快但不安全”时选了后者。厂商的激励方向一致，更强的安全默认值会导致用户流向竞品。

更细粒度的权限控制（按操作类型、目标路径、网络出口分别授权）是一个改善方向，Claude
Code 的 hooks 系统和 Codex
的三级沙箱都在往这里走。但历史上，细粒度权限系统（Android
权限模型、浏览器
CSP）的实际效果一直低于设计预期，原因是用户倾向于选择最宽松的配置。

### 攻击面随 agent 能力自动扩大

前两个困难是静态的：指令数据混合是 LLM 的固有属性，执行权限的
trade-off 是产品设计的约束。第三个困难是动态的：agent
能读取并赋予执行语义的文件范围在不断增长，攻击面随之扩大。

今天的配置文件投毒局限在 IDE 配置和 MCP 定义。MCP
生态是最近的扩展方向：第一个被发现的恶意
MCP 服务器 postmark-mcp 伪装成 Postmark
邮件服务，正常发邮件但每封密送给攻击者，约 300
个组织在发现前已集成到工作流中。OWASP 已发布 MCP Top 10 beta 版。明天，当 agent
被赋予读取 Slack 消息、处理邮件附件、访问内部 wiki
的能力时，这些内容都可能成为 prompt injection
的载体。冯诺伊曼问题在每一代计算平台上的攻击面都比上一代更大，LLM
也不例外。

GitHub 在设计 Agentic Workflows
安全架构时选了一种顺应这个趋势的思路：直接假设
agent 已经被入侵，不试图阻止 prompt injection，而是限制 injection
成功后能造成的损害。Google DeepMind
的一项联合研究得出了类似结论：依赖当前 LLM 架构的 agent 不太可能提供可靠的安全保证，可行的策略是限制
agent 的通用性来换取安全性。这意味着解决这个问题的路径大概率不是”让
agent 更抗 injection”，而是在 agent
的执行权限和可访问范围上做更严格的工程约束，就像内存保护不是让 CPU
更聪明地判断哪些字节是代码，而是直接禁止数据区域被执行。

## 可以做的事

关闭 auto-approve / YOLO mode 是目前性价比最高的单一措施。91% 的 YOLO
session 数据说明绝大多数用户在自动批准模式下使用
agent，而多数攻击链的前提条件就是自动批准。

开启沙箱（Claude Code 的 bubblewrap/Seatbelt，Codex 的
Landlock/Seatbelt）可以限制被操纵后命令的损害范围。如果你用的工具支持沙箱但默认没开，手动开。

对
.cursorrules、.claude/settings.json、.github/copilot-instructions.md、AGENTS.md
这些文件的 PR 修改，给予和 .github/workflows/
同等的审查级别。它们能控制 agent 在你机器上执行什么。

把 .zshrc、.npmrc、.env
里的凭证迁移到 secrets manager。AI 编程工具的 session log
会记录读到的所有文件内容。

CI/CD 中使用 AI agent 时，对所有依赖使用 pinned commit hash 并配置
minimumReleaseAge。OpenAI 的 Axios
事件根本原因就是 floating tag 加上没有冷却期。