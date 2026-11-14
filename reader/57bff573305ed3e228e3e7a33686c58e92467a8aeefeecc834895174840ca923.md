---
layout: post.njk
source: https://yage.ai/share/claude-p-subscription-workarounds-20260615.html
speaker: yage.ai
title: |-
  claude -p 自动化调用 6.15 改计费了：PTY 模拟还是走
  ACP，两条路怎么选
date: '2026-06-15'
summary: 文章分析了 Anthropic 对 Claude API 调用计费模式的变更，即从订阅额度转向按月信用额度计费。作者探讨了两种自动化调用路径的选择：PTY 模拟方案（伪装交互式使用以走订阅额度）和 ACP 协议方案（标准化 Agent 驱动的通信）。文章指出 PTY 方案依赖特定 UI 界面，而 ACP 方案更具长期稳定性和跨平台能力，最终建议生产级应用应直接使用按量付费的 API Key。
area: tech-engineering
category: ai-application
tags:
  - api-pricing
  - agentic-workflow
  - subscription-limits
  - protocol-standardization
people: []
companies_orgs:
  - Anthropic
products_models:
  - Claude Code
media_books: []
draft: true
status: evergreen
---

## 你的 cron job 开始吃 credit
了

过去几个月你可能一直这样用：claude -p "review this PR"
挂在 GitHub Actions 里跑代码审查，或者
claude -p "generate release notes" 接了 cron job
每周生成变更摘要。因为你有 Pro 订阅，这些调用直接走 subscription usage
limits，不会多花钱。

6 月 15 日之后，这个逻辑变了。Anthropic 把
claude -p、Agent SDK、GitHub Actions 这类程序化调用从订阅
usage limits 里剥离，走一个新的 per-user 月度 credit 额度。交互式 Claude
Code 保持原有订阅计费，你在终端或 IDE 里手动用的那种不受影响。

具体数字：Pro 每月 $20 credit，Max 5x $100，Max 20x $200。Credit 按
API token 价计费（Sonnet 3.5 约 $3/M input、$15/M
output），自领取后每月自动刷新，月底清零。用完以后如果开了 usage
credits，继续按标准 API 价走；否则请求停止。

Anthropic 官方支持页把事情讲清楚了：Use
the Claude Agent SDK with your Claude
plan。文章里的判断是：个人自动化用 credit 够用，大规模生产自动化该转
Claude Platform API key 做 pay-as-you-go。全文没有提任何
workaround，也没有封号相关表述。

## 你受影响吗，花 30 秒对一下

只在终端或 IDE 里手动用 Claude Code → 不受影响

用 claude -p 跑 cron job 或 CI pipeline → 受影响，调用开始消耗 credit

用 Agent SDK 编排自动化任务 → 受影响

用 GitHub Actions 调 Claude → 受影响

属于后三类的，下面两种社区方案是当前主要选项。

Claude Code
自动化的三条计费路径

## 选项一：PTY
模拟，让自动化调用走得像是人在打字

你在终端里手动敲 claude，走订阅额度。你的脚本调
claude -p，走 API credit。Anthropic
区分这两种使用方式，靠的是看谁来启动进程：人在终端里启动的算交互式，脚本自动跑的算程序化调用。

PTY 方案利用的就是这个区分。你的脚本不再直接调
claude -p，而是先开一个模拟终端环境（叫
PTY），在里面启动交互式的
claude，再用程序模拟人敲键盘来提交
prompt。服务端看到的是有人在终端里正常用 Claude
Code，于是走订阅额度。全程用的是你自己的真实订阅凭证，没有伪造任何东西。

这个思路下有两个代表项目。

toll-free-harness（npm，Apache-2.0），作者
Reddit u/Yolo-8848。用法是把命令改成
npx toll-free-harness claude -- -p "prompt"。它自动帮你处理交互式
Claude Code 里那些需要人操作的步骤：提交 prompt、审批工具调用、确认
plan。你只需要告诉它做什么，它把你的指令翻译成键盘事件发给 Claude
Code。临时插件用完即弃，不碰你的全局配置。作者在 r/ClaudeCode
的发布帖里给的用法就是改一行命令。

clarp（npm，MIT），作者
GitHub dn00。定位是 claude -p 的 drop-in 替换，用法就是把
claude 换成
clarp：clarp -p "explain this function"。它比
toll-free-harness 多做了一步：在本地起一个代理拦截 Claude Code
的通信，在转发给 Anthropic
的同时把响应复制一份出来。这样你的脚本能拿到和 claude -p
一样的结构化输出（assistant 消息、tool
调用结果等），方便下游程序解析。toll-free-harness
只能拿到终端屏幕上的文本，解析起来麻烦。

同类项目还有 claude-pty-wrapper、jinn 和 Open Claude Proxy /
OCP，技术路线基本一致。

这些工具能活多久，取决于 Claude Code
的终端界面长什么样。对话框按钮在哪个位置、提示文案写了什么、plan
模式分几步，这些都是内部实现。Anthropic 每次更新 CLI
都可能改这些细节，改了之后模拟的键盘事件就对不上号了。失效方式也难调试：程序看起来在正常运行，但按键打到了错误的位置，输出悄悄变了。clarp
还多一层风险：它的 README 直接承认，如果 Claude Code 不再支持
ANTHROPIC_BASE_URL 这个环境变量，整个代理方案就失效。

ToS 风险是社区普遍焦虑但缺证据的话题。Anthropic
官方文档没有点名这类工具，也没有封号表述。网上流传的”明确违反
ToS，可能永久封号”说法来自社区推测和 LLM 聚合，没有 Anthropic
原文支撑。当前也没有任何公开的因使用这些工具被封号的案例。真实风险是 ToS
解释的不确定性：入口分类这一层的判定规则不透明，政策收紧的时间和方式也无法预测。

## 选项二：ACP
协议，把编辑器驱动 agent 这件事标准化

ACP（Agent Client Protocol）是 Zed
Industries 发起的开放协议。它之于
coding agent，大致相当于 LSP 之于 language server：LSP 让任何 language
server 能接入任何编辑器，ACP 让任何 coding agent 能接入任何编辑器。

和 PTY 方案的区别，Reddit 用户 Deep_Ad1959 在 toll-free-harness
发布帖下写了一段最好的总结：

> the pty + keyboard-events path works until the next claude code
> release moves a dialog button or changes the bypass prompt copy, then
> every harness in the wild silently breaks for a day. ACP exists for
> exactly this. JSON-RPC against claude code / codex with prompt
> submission, tool approval, and plan approval as actual protocol messages
> instead of screen scraping.

PTY 方案依赖 Claude Code 的终端界面，每次 CLI 更新都可能让它失效。ACP
依赖的是公开的消息规范：你的程序发一条
session/prompt，agent 回一条
agent_message_chunk，格式写死在协议里，不随 UI
改版而变。而且 ACP 客户端写一次能驱动任何实现 ACP 的 agent（Claude
Code、Codex CLI、Gemini CLI、Grok Build 等），PTY harness 是 Claude Code
专属的。

ACP 官网在 agentclientprotocol.com，registry
目前列了 40 多个已实现 ACP 的 agent。已支持 ACP 的编辑器包括
Zed、JetBrains 2026.1、Xcode 27 和 Neovim（社区插件）。

这里有几点已知限制。交互式 mid-plan editing 缺失，plan 的 reporting
能通过 session update 拿到，但中途修改 plan 这一步还做不到。Xcode 27
里通过 ACP 连接 agent 时，skills 和模型切换受限。WSL 目前不支持。

## ACP 的定价归属还悬着

倾向走订阅的证据：Zed 官方文档的订阅对照表把
Claude Pro/Max 对应到 “External Agent via ACP → Claude Agent”，并注明
“Use Claude Agent or Claude Code where supported if you want
subscription-backed Claude
behavior”。从机制上看，claude --acp
启动的是一个长驻交互式进程，更接近订阅会话。

倾向会被 metered 的证据：HN 讨论中，用户
unshavedyak 认为 Anthropic 在禁用所有 subscription-based 的 SDK
使用，ACP 会被包括在内。Deep_Ad1959 也明确说 ACP “doesn’t solve the
subscription-vs-API pricing question”。

核心问题在服务端如何归类会话来源，不在协议层。如果 Anthropic
在服务端检测到会话来自非交互式的 agentic 调用，不管它是
-p、SDK 还是 --acp，都可能强制
metered。目前的公开信息不足以确认 claude --acp
一定走订阅。如果要用 ACP
做自动化且依赖订阅定价，建议实测当前版本行为，并预期这个行为可能随政策变化而调整。

## 怎么选

三类使用场景，对应三种选择。

第一，个人自动化或玩具级：cron job 跑 lint、偶尔的 batch 处理、个人的
PR review bot。PTY 方案够用。clarp 比 toll-free-harness 更接近
claude -p
的直接替换，结构化输出对接下游更方便。代价是接受它会随 Claude Code CLI
改版失效。调试起来比一般脚本复杂。

第二，跨 agent 编排或想长期稳定：ACP 是唯一可持续的方向。即使 Claude
Code 的 ACP 定价最终走向 metered，ACP 的协议稳定性也远高于 PTY
hack。而且 ACP 客户端写一次能驱动多个 agent，不会把你锁在 Claude Code
一个生态里。

第三，生产级、不可接受中断：直接用 API key。Anthropic
官方的建议也是这个方向，大规模生产自动化用 Claude Platform API key 做
pay-as-you-go。这条路没有不确定性，按量付费，不依赖任何入口分类判定。

## 博弈还在继续

整个事件的底层是 Anthropic 在区分真人交互和自动化调用。PTY
方案伪装前者，ACP 标准化后者。只要 Anthropic
继续用订阅补贴吸引真人用户、同时从自动化调用获取 API
收入，这个张力就会持续存在。PTY hack 是过渡期的产物，ACP
是长期基础设施。中间缺的是一个定价合理的自动化 tier，如果有这个
tier，两套 workaround 方案的紧迫性都会大幅下降。

## Update（6
月 15 日美西时间下午两点）：Anthropic 暂停了这次变更

就在本文发布的同一天晚上，Anthropic
给所有订阅用户发了一封邮件，标题是 “We’re pausing the Agent SDK credit
change”。原文要点：

> We’re not making this change today. We’re working to update the plan
> to better support how users build with Claude subscriptions.
> Nothing changes for now. Agent SDK, claude -p, and third-party app
> usage continues to work with your subscription exactly as it did before
> today, and there’s no credit to claim.

claude -p、Agent SDK 和第三方 app
的调用继续走订阅额度，和 6 月 15 日之前完全一样。本文介绍的 PTY 模拟和
ACP 方案目前没有紧迫需求，但 Anthropic
说他们在调整方案、会提前通知下次变更。社区讨论见 r/ClaudeAI。

本文的分析仍然成立：只要 Anthropic
继续区分交互式使用和程序化调用的定价，PTY hack 和 ACP
协议的讨论就不会消失。这次暂停更像是执行节奏的调整，不是方向上的转弯。