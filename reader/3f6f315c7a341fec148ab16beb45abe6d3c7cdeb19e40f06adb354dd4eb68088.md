---
layout: post.njk
source: https://yage.ai/share/agent-skills-harness-portability-20260720.html
speaker: yage.ai
title: Agent Skills 统一了文件格式，Harness 仍然各自为政
date: '2026-07-20'
summary: 文章探讨了Agent Skills在不同客户端（如Claude Code, Gemini CLI等）中的实现差异和兼容性问题。核心观点是，尽管Skill的发现层趋同，但私有字段、加载机制、资源解析和执行权限仍由各Harness决定，导致跨客户端的完全统一存在困难。建议开发者应维护一个克制的通用核心Skill，并在目标Harness中进行薄适配，将特定逻辑留给应用层实现。
area: PAI
category: ai-tooling
tags:
  - agent-skills
  - cross-client-compatibility
  - harness-logic
  - skill-management
people: []
companies_orgs:
  - Anthropic
products_models:
  - Claude Code
media_books: []
draft: true
status: evergreen
---

## 把
release-check 放进项目目录，哪些客户端能找到它

如果你写好了一个用于检查发布流程的 release-check
Skill，想让本地 AI 助手直接调用它，最直观的办法是在项目根目录下创建
.agents/skills/release-check，把说明文档
SKILL.md、Python 脚本 scripts/check_release.py
和策略文件 references/release_policy.md 都放进去。

截至 2026 年 7 月 17 日，Codex、Cursor、OpenCode、Gemini
CLI、Antigravity 2.0、Antigravity CLI 和 Antigravity IDE
都会扫描这个项目级共享目录，从中发现
release-check。如果在同一个项目里使用 Claude
Code，它却不会从这里寻找 Skill。在本文核查的这组主流本地客户端里，Claude
Code 是唯一的例外。

这种选择有些出人意料。Agent Skills 本身就是 Anthropic
发起并维护的项目。Anthropic 在 2025
年 10 月 16 日先把 Skills 作为 Claude 的产品和 API 能力推出，又在 2025 年 12 月 18 日将
Agent Skills 发布为开放标准。项目官方的客户端实现指南建议，客户端扫描自身专用目录时，也考虑项目级
.agents/skills/，并将它称为广泛采用的跨客户端惯例。Cursor
和 OpenCode 甚至主动加入了对 .claude/skills/ 的扫描；Claude
Code 的官方文档却只列出专属的
.claude/skills/、个人目录和其他 Claude 来源。

团队可以把 .agents/skills/release-check
保留为唯一内容源，再在 .claude/skills/ 下创建一个指向它的
symlink，也可以让安装器把它映射到 Claude Code 的目录。Claude Code
官方支持 symlink，所以不必复制两份
Skill；但无论选哪种办法，项目都要维护一段只为 Claude Code
存在的部署逻辑。Anthropic 的做法没有违反格式规范，因为规范确实没有强制安装路径，但额外适配工作仍然落在开发者和其他工具身上。

同一个 release-check Skill
通过共享目录被多个客户端发现，Claude Code
则需要一个指向同一内容源的薄桥接

## 找到同一个
Skill，不代表私有字段也会生效

即便 Claude Code 已经能找到
release-check，兼容问题依然没有解决。打开
SKILL.md，文件开头的 frontmatter 还藏着另一组差异。

开放规范要求 frontmatter 提供 name 和
description，还允许选填
license、compatibility、metadata
和实验性的 allowed-tools。Claude Code 的字段表又加入
when_to_use、argument-hint、arguments、disable-model-invocation、user-invocable、disallowed-tools、model、effort、context、agent、hooks、paths
和 shell。

这些字段不是普通说明。model 和 effort
会影响 Claude 如何处理任务，context 与 agent
控制是否进入 subagent，paths 可以按文件匹配
Skill，hooks
会在指定时机执行命令。disable-model-invocation: true 禁止
Claude 自主调用该 Skill，disallowed-tools 则在 Skill
激活期间移除指定工具。作者一旦依赖这些设置，就不再只是使用一份通用的
Markdown 指令。

把同一份文件交给 Gemini CLI，它仍可读取标准的 name 和
description，但不会执行 Claude Code
私有字段所表达的模型选择、调用限制、subagent 配置或
hooks。文件可以正常解析，不代表这些设置得到了替代实现。若
release-check 的正确性依赖
disable-model-invocation 或
disallowed-tools，团队就必须在 Gemini CLI
自己的策略与权限配置中重新表达要求，不能把 Claude frontmatter 当成跨
Harness 的安全规则。

Cursor 已经兼容 paths 和
disable-model-invocation 等少数 Claude
字段，但这种选择性适配不代表整个生态对字段含义达成了共识。OpenCode
的公开接口也没有承诺执行这些控制字段。同一个 SKILL.md
能被多个 Harness 读取，具体的调用时机、模型、subagent、hooks
和工具限制仍可能不同。

Agent Skills 在发现层趋同，但私有
frontmatter、加载、资源解析、执行与权限仍由各客户端 Harness
决定

## 真正执行脚本时，各家
Harness 还在使用自己的规矩

当大模型决定调用 release-check 时，各家 Harness
的流程也不相同。

在 Gemini CLI
中，会话开始时模型只能看到 Skill
的名称和描述。模型请求激活后，终端先展示 Skill
的说明和目录访问范围，等待用户确认；获得同意后，Gemini CLI 才把
SKILL.md 正文和目录结构加载进上下文。

OpenCode
则要求模型调用内置的 skill 工具读取 Skill
说明。这个动作只负责把文档交给模型。模型随后要运行
check_release.py，仍需调用普通的 shell
或文件工具，并接受宿主权限系统的检查。

Google 的几种产品也不能合并成一个客户端来讨论。Gemini CLI、Antigravity 2.0、Antigravity
CLI 和 Antigravity IDE
都支持项目级
.agents/skills/，但它们的全局目录和加载流程并不相同。Antigravity
CLI 当前让 agent 用普通文件工具读取 SKILL.md，没有沿用
Gemini CLI 的 activate_skill 流程。

Skill 内部的脚本会把这些差异放大。运行
scripts/check_release.py 时，它可能还要读取
references/release_policy.md。Agent Skills 没有规定 Harness
从哪个工作目录启动 Python，也没有统一
Read、Bash、view_file 或
run_shell_command 这些工具名称。脚本应该通过
__file__ 找到自身所在的 Skill
目录，再定位参考文件；SKILL.md
也应描述“读取文件”或“执行脚本”这样的动作，而不是假定每个 Harness
都提供同名工具。

规范中实验性的 allowed-tools 也不能替代各家 Harness
自己的安全配置。Codex 的 approval 与 sandbox、Gemini CLI 的 policy
engine、OpenCode 的工具权限和 Antigravity 的 permission rules，都独立于
Skill 格式。模型拿到 Skill
说明以后，脚本能否执行、可以访问什么、是否需要用户确认，决定权仍在当前
Harness 手里。

## 自建 Harness
也要自己补齐执行和安全策略

如果开发者希望在自己的代理框架中使用这些
Skill，就需要自己实现格式之外的部分。

OpenAI
Responses API 的 Skills 指南给出了一个例子：hosted shell
接收上传且带版本的 skill_reference，local shell
则依赖调用者提供本地路径。API 不会因为调用者的代码仓库里有
.agents/skills/ 就自动扫描它。

Microsoft
Agent Skills for Python
把这层分工写得更直接。FileSkillsSource 从本地目录读取
Skill，SkillsProvider
将描述提供给模型，SkillScriptRunner 启动关联的 Python
脚本。它们解决了 Skill 如何进入 Python
Agent，却不会替应用决定扫描哪些目录、如何准备依赖、在哪里运行脚本、何时请求用户授权，以及怎样限制文件与网络访问。

要让 release-check
服务多个客户端，团队可以维护一份克制的核心 Skill，再为目标 Harness
添加薄适配。name 和 description
是可靠的共同字段；其他标准可选字段可以保留，但不能承担跨 Harness
的关键控制。正文用通用动作描述步骤，脚本从自身位置解析资源，依赖和环境要求明确写出。Claude
Code 的目录映射、Cursor 的路径触发或 API
的上传版本分别留在适配层，最后在每个实际采用的 Harness
中测试发现、资源读取、脚本执行和默认权限。