---
layout: post.njk
source: https://yage.ai/share/ai-rewrite-tools-zero-cloudflare-20260518.html
speaker: yage.ai
title: |-
  从 Zero 到 Cloudflare：为 AI 重写工具，不只是把 API
  包一层
date: '2026-05-17'
summary: 文章探讨了当 AI Agent 成为软件工具的消费者时，设计范式需从面向人类转为面向机器。作者以 Zero 编译器和 Cloudflare 的 API 设计为例，指出 AI Native 的工具设计应提供稳定、结构化的输出，避免过度抽象带来的歧义，并向 Agent 注入操作知识体系，以应对 AI Agent 的无记忆特性和决策限制，从而提升 Agent 任务执行的确定性与准确率。
area: tech-engineering
category: ai-application
tags:
  - ai-agent
  - developer-tools
  - api-design
  - compiler-design
  - ai-native
people:
  - Matt Pocock
  - Tom Bedor
companies_orgs:
  - Vercel Labs
  - Cloudflare
  - Anthropic
  - Stripe
  - Salesforce
  - Humanlayer
products_models:
  - Zero
  - MCP
  - Claude
  - Opus
media_books: []
draft: true
status: evergreen
---

五月中旬，Vercel Labs 发布了一门叫 Zero
的编程语言。最值得看的东西不在语法里——语法是给人和 AI
共享的——而在编译器输出里。跑
zero check --json，返回的不是散文式错误信息，而是带稳定
error code 和 repair ID 的结构化 JSON。每条诊断同时有
message（给人读）和 code +
repair.id（给 agent 读）。同一个输出，两条轨道。

为什么一个编译器要做这种事？你可以说这是噱头——毕竟 Zero 现在只有 981
个 star，两个 release，Vercel Labs 而非 Vercel 主线，HN 上有人说它
“brings nothing new”有人说它是 “agent repair loop”
的基础设施。但你也可以换一个问题：当 AI agent 写代码、编译器报错、agent
尝试修复这个循环每天发生几百万次的时候，编译器的输出到底应该长什么样？

传统答案是：应该长成人类能读懂的样子。Zero 的答案是：应该长成 agent
能匹配的样子。这两个答案的区别不是技术上的——是把”谁在消费编译器输出”这个前提改掉了。

## 同一个问题，另一个入口

Cloudflare 从另一个入口碰上了同一个问题。他们的 API 有 2,594 个
endpoint。如果对接 MCP 的方式是给每个 endpoint 建一个 tool，单 tool
定义就要占 244,047 个 token。对话还没开始，context window
已经炸了。他们的解决方案是把整个 API 压缩成两个工具——search
和 execute——让 agent 写 JavaScript 代码来调用 API，在隔离的
sandbox 里跑。Token 从一百多万削到一千出头（Cloudflare Code Mode
MCP）。

这两个场景放在一起，能看到一个共同的东西：它们都在处理 AI
的能力边界。Zero
处理的是歧义——同一个错误在不同编译器版本里措辞不同，agent
会猜错。解决方式是给它稳定标识而不是自然语言。Cloudflare
处理的是选择——agent 在几百个相似 tool 里做决策时准确率会急剧下降（Anthropic
自己的数据：134K token 的 tool 定义下 Opus 4 准确率只有
49%）。解决方式是让它写代码而不是选 tool。

这两件事都不是”把已有的功能暴露给 AI
看”。那不是设计——那是薄封装。

大部分 MCP server 就是薄封装。把 API endpoint 一对一映射成 MCP
tool，格式对了，内容没变。AI
确实能调用了，但调用层的上下文里没有告诉它什么时候该用、以什么顺序用、遇到错误怎么恢复。引导知识——那套本该和工具一起交付给
agent 的操作知识——被漏掉了。杠杆工具——那些把 agent
容易出错的任务封装成确定性操作的东西——也没有。去年我在另一篇文章里讨论过这个框架：当软件的消费者从人类变成
AI 时，你交付的不应该只是核心 API，还应该包括引导 AI
使用的知识体系和帮它绕过弱点的工具。当时用 Stripe
举的例子，现在用编译器和 MCP 看，逻辑是同一套。

把这两类设计放一起看，真正区分它们的不是”有没有考虑
AI”，而是有没有认真对待 AI
的几个基本特征——这些特征和人类完全不同，但大多数”AI-first”产品根本没在设计里回应它们。

## AI 没有记忆

人类工程师有积累——你在这家公司干了三年，知道代码库里哪些模块容易出问题，知道上次重构哪里踩过坑。AI
agent 没有。每次 session 从零开始。人类可以通过经验、同事、代码 review
来补全上下文，agent 只能靠你在启动时喂给它的东西。

Zero
的做法是把这份引导知识和编译器一起发布：zero skills get zero --full
这条命令让 agent 从编译器里直接读取一份 Markdown
格式的操作指南——语法规则、构建流程、常见陷阱——这份指南和编译器版本一起打包，始终精确匹配。agent
不会像查网页文档那样读到一份描述的 API 和实际安装的版本对不上的内容。AGENTS.md
也是同样的逻辑：把项目背景、构建命令、代码规范注入每次 session
的上下文。Matt Pocock
引用过 Humanlayer 的 “instruction budget” 概念——前沿 LLM
能稳定遵循的指令在 150-200 条之间。这意味着 AGENTS.md
不能膨胀，每多一条规则都在抢占模型理解任务的注意力。和人类读 README
完全不同：人类可以跳过、扫读、选择性忽略，agent
会把你写的每一行当指令执行。

这层限制也解释了为什么 Salesforce
Headless 360 的动作不只是”加了个
API”——它把过去需要人类登录、点进界面才能获取的业务上下文（客户有没有未关闭的
escalation、30 天后到期的续约、被违反的 SLA）编码成了 agent
在写代码时就能拿到的数据。不是 agent
变聪明了——是这些信息以前只存在于人的记忆和 UI 操作路径里，现在有了 agent
可以直接消费的接口。

## AI 不会浏览，只会执行

人类面对一个几百条菜单的界面，可以扫一眼找到自己需要的。agent
不行。给它 100 个 tool，它在前 5 个里选对的概率就不高，到了第 50
个基本在猜。Anthropic 建议 Claude Code 的核心 toolset 保持在 12
个左右。不是模型不够好——是 tool 选择这个任务本身和 LLM
的决策模式不匹配。

Cloudflare 的应对是极端的：不是优化 tool
描述让它更容易选，而是彻底不要让它选——给它 search 和
execute 两个 tool，让它写代码来调用 API。agent
做代码生成准确率远高于做 tool 选择。

Stripe 的
Agent Toolkit 用的是温和版本：精选 surface area。Stripe 有几百个
endpoint，全暴露给 agent 等于让它在一个超长的菜单里盲选。Toolkit
挑出十几个 agent 最可能需要的操作，每个带精确的 schema
和描述。这十几工具本身做的事情和传统 Stripe SDK 完全一样——都在调支付
API。区别是接口层的设计假设变了：传统 SDK 面向读文档的人类开发者，Agent
Toolkit 面向运行时发现能力的 AI 系统。

## AI 需要精确，人类需要抽象

这是超越 DRY
那篇文章里讨论过的激进透明原则。传统 API
设计面向人类开发者，核心是以保护为目的的抽象——隐藏复杂性，提供简洁接口，防止用户犯错。AI
原生设计正好反过来：agent
不会被复杂的报错吓跑，但它会被模糊的报错困住。

一个具体的例子：传统 API 在捕获底层网络超时后，通常会抛出一个抽象的
APIFailureError，附带一行”操作失败，请稍后再试”。这对人类是友好的——他不需要知道底层到底是
TCP 握手超时还是 DNS 解析失败。但对 agent 是致命的。agent
的有效性依赖于一个”尝试-反馈-修正”的循环。模糊的错误信息直接中断这个循环——agent
不知道具体哪里出了问题，只能瞎改一通再试。

正确的做法是保留原始的 ConnectTimeoutError，带着完整的
stack trace 和上下文。agent
一看就知道是某个特定步骤网络超时了，可以针对性重试或换
endpoint。信息量对人是过度，对 agent 是刚好。

Zero 的 repair ID
是同一个原则的不同应用。自然语言的错误信息有歧义——同样的错误在不同版本里措辞可能不同，同样的措辞
agent 可能解析成不同的修复。NAM003 →
declare-missing-symbol
这个映射是稳定的。修复循环里每一步的确定性都比”让 AI
理解自然语言”更值钱。

## 现在到了哪个阶段

各层进展差距很大。平台层最快——Salesforce、Stripe、Atlassian、AWS 的
agent-first
产品已经是路线图上的核心交付。协议层在标准化，安全层还在早期。编译器层的实验能不能活下来，不知道。

有一种常见的批评值得认真对待。Tom Bedor 在 MCP is a Fad 里说与其为
agent 建新协议，不如把人类接口做清晰。这个批评碰到了一个真问题——很多为
agent 做的事确实只是薄封装。但它漏掉了另一种：编译器输出、CRM
平台、支付系统这些东西，几十年的设计里”另一端是人类”这个假设太深了。不是你写一个更好的
README 就能解决的。