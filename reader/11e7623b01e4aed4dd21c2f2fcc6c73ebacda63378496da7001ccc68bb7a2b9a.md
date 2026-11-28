---
layout: post.njk
source: https://yage.ai/share/harness-genes-multi-agent-20260727.html
speaker: yage.ai
title: |-
  都是 Multi-Agent，各家 AI 编程 Harness
  的基因与信仰到底有何不同？
date: '2026-07-27'
summary: 文章对比了 Claude Code、Codex CLI、Cursor 和 Antigravity 这四种主流 AI 编程 Harness 在多 Agent 协作方面的底层设计哲学和工程信仰。它分析了每种工具在通信拓扑（Claude）、算力效率（OpenAI）、无感融合体验（Cursor）以及显式工作流治理（Antigravity）上的差异，帮助开发者根据具体业务场景进行 AI 编程工具的选型。
area: tech-engineering
category: ai-application
tags:
  - multi-agent
  - coding-harness
  - architecture
  - workflow-design
  - model-efficiency
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - Google DeepMind
products_models:
  - Claude Code
  - Codex CLI
  - Cursor
  - Antigravity
media_books: []
draft: true
status: evergreen
---

<!DOCTYPE html>

都是 Multi-Agent，各家 AI 编程 Harness 的基因与信仰到底有何不同？

现在随便打开一个主流的 AI 编程工具，不管是终端里的命令行 CLI
还是编辑器里的插件，官宣日志里基本都写着支持多 Agent
协作。大家可能觉得，它们干的事情大同小异，无非都是在给大模型外包一层函数调用循环：主进程开几个子线程，调调模型接口，分发几个搜代码、写文件的工具，表面看没什么两样。

但如果把这几家的 Harness 拿到实际生产工程里折腾，翻开它们的 CLI
源码、配置文件以及底层的进程通信日志，就会发现情况并非如此。这些工具表面上都在叫多
Agent，但底层落地的工程路径、状态同步机制以及对未来软件工程形态的假设，完全是四条不同的路。它们各自选择的架构，背后都有一套鲜明的产品基因与设计信仰。

### Claude
Code：网络拓扑与双轨阵列的探索

先看 Anthropic 的 Claude Code。它虽然运行在终端里，但 Anthropic 对
Agent 之间的通信拓扑有着持续的探索。

在树状派生这条主线上，Anthropic 一直在积极完善纵向深度的可控性。在
v2.1.219 版本里，它将子 Agent 的默认派生深度设为 3 层（可通过
CLAUDE_CODE_MAX_SUBAGENT_SPAWN_DEPTH 配置最高放开至 5
层）。为了解决深层递归带来的思考盲区，它配合 –forward-subagent-text
命令行参数，把深层子节点的思考上下文逐级向上回传，并按创建该 Agent 的
tool_use ID
进行精确归属。这种设计让层级拆解在保持上下文隔离的同时，依然拥有全局可追踪的调试能力。

在横向探索这条支线上，Claude Code 推出了实验性的 Agent Teams
机制，通过开启环境变量 CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS=1
就能激活。这一机制尝试打破传统的主从汇报关系，转向点对点的网络拓扑。为了支撑平级协作，它引入了一个叫
tasks.md
的共享账本机制，所有的任务状态、领取记录和产出依赖都被写进去中心化的账本文件里，Agent
之间可以通过解析 tasks.md 动态抢占任务与交接中间结果。

此外，Anthropic 在其拓扑体系中还引入了 Dynamic Workflows
动态工作流概念。系统不是盲目启动无限多的
Agent，而是根据具体任务的依赖图动态规划 Agent
规模与流转顺序。官方在动态工作流中默认建议将单次协同的 Agent 数量控制在
15
个以内，同时也允许开发者通过设置进行覆盖，尝试在自动化拓展与系统资源开销之间寻找平衡。从这些设计来看，Anthropic
的基因里带着强烈的网络拓扑色彩，把软件工程视为一个在树状与网状之间灵活演进的通信阵列。

### OpenAI
Codex：异构算力与推理亲和度匹配

跟 Anthropic 追求通信拓扑的美感不同，OpenAI 在 Codex CLI
里展现出的是一种现实的工程实用主义（自 0.145.0 版本引入 Multi-Agent V2
架构）。

在多 Agent
派发中，传统的默认行为大多是让子节点继承主节点的模型配置（或仅做粗粒度的子模型指定）。但在真实开发里，去跑一个简单的静态语法检查，或者翻找某个配置文件的路径，根本不需要顶级的深度推理能力。很多时候终端里几十个子节点全在调最贵的模型或进行高强度推理，不仅响应慢，还会烧掉大量的
Token 预算。

OpenAI 在 Codex Multi-Agent V2
里解决问题的核心逻辑是因材施教，也就是任务与推理能力的亲和度匹配。主节点在调度子
Agent 时，拥有精细的控制权限。它可以根据子 Agent
的角色模板，动态指定不同的基础模型，甚至精细调控每个子 Agent
的推理力度，可以在 low、medium、high
三档之间灵活切换，同时严格限定并发调度的上限。

比如在处理大范围重构时，Codex 会派发一个推理力度设为 high
的子节点去作跨模块的架构设计与类型推导；同时并行派发若干个推理力度设为
low 的轻量子节点去批量更新边缘文件的导入声明和测试用例。另外，它还扩展了
/import
命令行指令，支持把外部的项目规范、历史决策上下文和记忆规则无缝导入到指定子
Agent 的运行空间里。从它的 Rust
调度逻辑来看，这种基因完全是以成本、吞吐量和推理效率为核心导向的，用经济的算力去组合出较高的重构产出比。

### Cursor：无感融合 IDE
状态的模型无偏见引擎

如果说 CLI 工具的战场在终端，那么 Cursor 则代表了另一种方向：把 Agent
抹平在 IDE 的交互体验里。

Cursor 的 Agent 协同建立在其 Composer 界面与 Agent Mode
模式之上。Composer
本身是嵌入在编辑器架构深处的多文件交互界面与调度系统，而 Agent Mode
模式则赋予其自主执行终端命令与多文件改写的能力。这套 Harness
架构与底层具体的语言模型是解耦的。在基因上，Cursor
是彻底的模型无偏见主义者，无论底层接入的是 Claude Opus
5、GPT-5.6、Gemini 3.6 Flash，还是 Grok
4.5，上层的交互体验和上下文感知都是一致的。

Cursor 的特点在于它把 Composer 的 Agent 执行循环与 VS Code IDE
的本地状态做到了深度绑定。在 Multitask 模式下发起多文件修改任务时，Agent
并不是在后台跑 Shell
脚本，而是直接作用于编辑区状态、后台未保存的标签页、.cursor/rules
规则库以及本地的 SQLite 数据库 state.vscdb。

为了在海量文件修改时保持毫秒级的上下文检索，它在后台构建了基于 Merkle
Tree 的仓库索引架构。当多个 Agent
循环同时在后台对不同文件进行局部修改、代码生成和预览时，开发者感觉不到阻塞，甚至可以在前台继续编写代码，随时审查
Agent 生成的修改。在 Cursor
里，这种后台索引、前台呈现修改预览的体验相对顺畅，它追求的是无感与流畅，把复杂的
Agent 调度细节隐化在熟悉的快捷键与编辑界面之下。

### Antigravity：谋定而后动的显式工作流与治理原生

最后再看 Google DeepMind 推出的 Antigravity。如果说 Cursor
追求的是隐形与无感，那么 Antigravity
展现出的则是一种具备明确治理色彩的工程信仰——谋定而后动。

Antigravity
本身真正原生的底层原语，完全围绕着显式工作流和安全治理来设计。

一个是它的 Planning Mode
规划模式。在开启规划模式后，主节点不会贸然去修改任何一行代码或执行破坏性命令，而是必须先生成一份详尽的结构化
Plan，并明确触发 Proceed Gate
执行门禁。只有当开发者在界面上审阅并点击批准后，Agent
才会进入代码修改阶段。

另一个是它拥有原生支持的一等公民产物引擎，所有的计划、架构分析和阶段性交付物都会被结构化持久化写入到
brain/
专属目录中。更难能可贵的是它的透明追踪能力，系统日志里保留了未经截断的
transcript.jsonl，任何一步思考过程、工具调用细节和报错信息都有据可查。

在多 Agent 隔离方面，Antigravity 在 invoke_subagent
原语里原生支持了基于 Git Worktree 的隔离机制，特别是在 share
共享模式下。当派生多个子节点并行探索或修改代码时，它们拥有各自独立的工作目录空间，却共享底层的
Git
仓库目录，既避免了重复磁盘占用的空间浪费，又避免了并发修改同一文件导致的冲突。面对大型关键系统的重构时，这种规划先行、产物落地和独立
Worktree 隔离带来的确定性与可追溯性，是其他工具无法替代的。

### 总结：基因光谱与工程选型

拆解完这四家 Harness 的底层机制，答案就很清晰了。多 Agent
协作绝非一个简单的通用标配功能，每一家工具的设计都深刻印着各自团队的思考痕迹：

如果你面对的业务场景涉及复杂的长链路架构解耦与模块重构，需要 Agent
之间频繁对齐与动态分工，Claude Code 那套基于 Agent Teams 和 tasks.md
的网络拓扑演进无疑是最顺手的；如果你管理着大规模的代码库重构项目，在意
Token 消耗成本、任务吞吐量与不同任务精细化算力分配，Codex
提供的异构模型与推理亲和度匹配会带来非常高效的 Pareto
最优解；如果你习惯在编辑器内完成全流程开发，追求界面的响应速度、本地索引与无缝预览，Cursor
这种基于 SQLite 和 Merkle Tree
的模型无偏见引擎体验依然无可替代；而如果你面对的是高风险生产系统、复杂的多人协作规范，或者需要极其严密的过程审计与显式规划，Antigravity
凭着规划模式、Proceed Gate 门禁校验、产物引擎以及 Git Worktree
共享隔离机制，给出了极具安全感和确定性的工程解法。

软件工程从来没有绝对的银弹。看清了这些 AI 编程 Harness
底层的基因与信仰，我们在为团队做工程选型或者搭建自己的 Agent
工作流时，才能不再被营销概念遮眼，真正选出最匹配自己代码库和团队习惯的那把利刃。