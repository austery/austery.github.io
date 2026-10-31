---
layout: post.njk
source: https://yage.ai/share/claude-advisor-tool-20260609.html
speaker: yage.ai
title: |-
  Fable 5 很贵，但省钱的答案 Anthropic
  两个月前就发布了
date: '2026-06-09'
summary: Anthropic发布的Advisor工具让强模型（Opus）担任顾问，弱模型作为主执行者，降低了Agent的成本并解决了模型规划越界问题，成为当前多模型架构下的最优成本控制策略。
area: tech-engineering
category: ai-application
tags:
  - agent-optimization
  - cost-efficiency
  - model-orchestration
  - llm-planning
people: []
companies_orgs:
  - Anthropic
products_models:
  - Claude
  - Fable 5
  - Mythos
  - Opus
  - Sonnet
  - Haiku
  - Ministral 8B
media_books: []
draft: true
status: evergreen
---

今天 Anthropic 发布了 Claude
Fable 5，也就是两个月前在私下部署中震动过华尔街的
Mythos 的公开版本。定价每百万 token 输入 $10、输出 $50，是 Opus 4.8
的两倍、Sonnet 4.6 的三倍多。订阅用户有一个窗口期：Pro、Max、Team 和
Enterprise 计划从今天到 6 月 22 日免费包含 Fable 5，之后改为消耗 usage
credits；API 上则从第一天起就是按 token
计费。换句话说，两周之后，“要不要在 agent
里用最强的模型”第一次变成了一道有明确价签的选择题。

这道题的答案，Anthropic
自己在两个月前就发布过，只是当时几乎没人注意。2026 年 4 月 9
日，他们上线了 advisor
tool：让便宜的模型当主力干活，把最贵的模型做成一个随叫随到、按次计费的顾问。巧的是，同一天我发过一篇《你的
Agent 管线里，最贵的模型可能在最错的位置》，讲 AgentOpt
论文的一个实验结果：在 planner-solver 管线里，把 Claude Opus 放在
planner 位置，准确率在 81 种模型组合中排名倒数；换成参数量小一个数量级的
Ministral 8B 做 planner、Opus 做 solver，准确率反而翻了一倍多。

一篇论文和一个 API
feature，同一天发布，方向看起来相反，背后是同一个判断。在 Fable 5
把价格问题摆上桌面的今天，这个判断比两个月前更有现实意义。

## 一个只出主意的 Opus

advisor tool 的机制一句话能说完。executor（Haiku 4.5 或 Sonnet
4.6）端到端跑任务：调工具、读结果、迭代。遇到拿不准的决策时，它调用
advisor（Opus 4.7 或 4.8）。advisor
读完整个对话记录，给一段建议，典型长度 400 到 700 个
token，内容是一个计划、一次纠偏，或者一个停止信号。executor
拿着建议继续干。整个回路发生在单次 /v1/messages
请求内部，由 Anthropic 服务端完成，客户端不写任何编排逻辑。

这套设计真正的看点在 advisor
的权限上。它没有工具，不产生面向用户的输出，连自己的 thinking
都会在返回前被服务端丢弃。它能做的只有一件事，就是把判断写成一段文字交给
executor。从头到尾，方向盘在便宜模型手里。

Anthropic 在官方博客里明确说，这个设计反转了常见的
sub-agent 模式。以往的多模型架构是大模型做
orchestrator，在上层分解任务、把活分给一群小模型；advisor
模式里没有任务分解、没有 worker
pool、没有编排逻辑，小模型自己往前推进，只在需要时升级求助。

## 表面矛盾，同一个判断

把这两件事并排放，第一眼像是冲突的。AgentOpt 的结论是弱模型该做
planner、强模型做 solver；advisor tool 反过来，让强模型出
plan、弱模型执行。两个方向相反的结论，怎么会是同一个判断？

答案在 AgentOpt 的失败机制里。Opus 做 planner
失败，原因并非不会规划。它不守角色边界：九次实验里有七次，它跳过对下游
solver
的工具调用，直接自己把问题答了，给出一个质量不高的直接回答，整条管线的推理链路就此中断。Ministral
8B
反而合格，因为它清楚自己答不上来，于是老老实实分解任务、调用工具、把子问题交给下游。

所以真正的变量不是哪个模型更会规划，而是握着控制循环的模型会不会越界。advisor
tool 的设计恰好把这个风险从源头上去掉了：Opus
的智能还在，但工具被收走了，控制权被收走了，它的输出只能以建议文本的形式注入回路，想越界也没有手段。AgentOpt
用实验暴露的问题，advisor tool 用权限设计做了回答。

两边共享同一个原则：控制权交给守协议的模型，智能做成按需调用的资源。一个模型的能力是不是优势，取决于它被放在什么位置上。

## 证据

官方评测给了三组数字。第一组，Sonnet 4.6 配 Opus advisor，在 SWE-bench
Multilingual 上比 Sonnet 单跑高 2.7 个百分点（72.1% 到
74.8%），每个任务的成本反而低
11.9%。成本不升反降的原因在于，好的计划减少了试错回合，advisor
上多花的钱被省下来的 executor 回合补了回来。第二组，同样的组合在
BrowseComp 和 Terminal-Bench 2.0 上分数更高，单任务成本仍然低于 Sonnet
单跑。第三组，Haiku 4.5 配 Opus advisor，BrowseComp 得分从 19.7% 翻到
41.2%；比 Sonnet 单跑分数低 29%，但成本低
85%，适合大批量、对成本敏感的场景。

需要说明的是，这些全部是 Anthropic
自己的评测，目前没有独立复现。发布当天 Bolt、Genspark、Eve
三家客户给了证言，其中 Genspark 提到 advisor 的效果超过了他们自己搭建的
planning
tool，这一条比一般的客户证言有信息量。方向性的信号是一致的，但在你自己的工作负载上跑过
eval 之前，这些数字只能当参考。Anthropic
自己的建议也是把三组配置都测一遍：Sonnet 单跑、Sonnet 加 advisor、Opus
单跑。

## 模式是社区的，原语是 Anthropic
的

弱模型执行、强模型当顾问，这个模式在社区里早不新鲜。Aider 在 2024 年 9
月就发布了 architect/editor
双模型模式，用强模型出方案、便宜模型生成具体的文件编辑，当时拿下了它自家
benchmark 的最好成绩。Sourcegraph
Amp 的 oracle 工具在结构上和 advisor tool 几乎一致：主 agent
自主决定什么时候向一个更强的模型请教调试和规划问题。Cursor 的 Plan mode
也属于同一族。Anthropic
在博客里直接承认，开发者们已经收敛到这个策略，他们做的是把它变成 API
里的一行配置。

不过把它做成服务端原语这一步，目前只有 Anthropic 走了。OpenAI 的
GPT-5 router 只存在于 ChatGPT 产品里，API
不开放，而且是请求级路由：整条请求进某一个模型，没有生成中途的咨询。Agents
SDK 的 agents-as-tools
功能上接近，但跑在用户进程里，每次咨询是一次独立的 API
请求，上下文由客户端拼接。Google 这边，Vertex AI 的 Model Optimizer
同样是按请求挑模型，Deep Think
是单模型内部的推理深度，两者都没有第二个模型在执行中途介入的机制。还有一个旁证：LiteLLM
在适配 advisor tool 时，对非 Anthropic
模型只能自己在网关层模拟整个编排循环。如果别家有原生等价物，它不需要这么做。

## 今天怎么用

API 上是真正的一行配置。文档把它标为
beta，写着需要联系 account team，但实测加上 beta header 就能用：LiteLLM
和 Vercel AI SDK
都已经适配，多个独立开发者发了实测代码，没有人提到审批环节。

```
<code class="sourceCode python"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a>response <span class="op">=</span> client.beta.messages.create(</span>
<span id="cb1-2"><a href="#cb1-2" aria-hidden="true" tabindex="-1"></a>    model<span class="op">=</span><span class="st">"claude-sonnet-4-6"</span>,            <span class="co"># executor</span></span>
<span id="cb1-3"><a href="#cb1-3" aria-hidden="true" tabindex="-1"></a>    betas<span class="op">=</span>[<span class="st">"advisor-tool-2026-03-01"</span>],</span>
<span id="cb1-4"><a href="#cb1-4" aria-hidden="true" tabindex="-1"></a>    max_tokens<span class="op">=</span><span class="dv">4096</span>,</span>
<span id="cb1-5"><a href="#cb1-5" aria-hidden="true" tabindex="-1"></a>    tools<span class="op">=</span>[</span>
<span id="cb1-6"><a href="#cb1-6" aria-hidden="true" tabindex="-1"></a>        {</span>
<span id="cb1-7"><a href="#cb1-7" aria-hidden="true" tabindex="-1"></a>            <span class="st">"type"</span>: <span class="st">"advisor_20260301"</span>,</span>
<span id="cb1-8"><a href="#cb1-8" aria-hidden="true" tabindex="-1"></a>            <span class="st">"name"</span>: <span class="st">"advisor"</span>,</span>
<span id="cb1-9"><a href="#cb1-9" aria-hidden="true" tabindex="-1"></a>            <span class="st">"model"</span>: <span class="st">"claude-opus-4-8"</span>,   <span class="co"># advisor</span></span>
<span id="cb1-10"><a href="#cb1-10" aria-hidden="true" tabindex="-1"></a>            <span class="st">"max_uses"</span>: <span class="dv">3</span>,                <span class="co"># 单请求内最多咨询次数</span></span>
<span id="cb1-11"><a href="#cb1-11" aria-hidden="true" tabindex="-1"></a>        },</span>
<span id="cb1-12"><a href="#cb1-12" aria-hidden="true" tabindex="-1"></a>        <span class="co"># ...你自己的其他工具</span></span>
<span id="cb1-13"><a href="#cb1-13" aria-hidden="true" tabindex="-1"></a>    ],</span>
<span id="cb1-14"><a href="#cb1-14" aria-hidden="true" tabindex="-1"></a>    messages<span class="op">=</span>[...],</span>
<span id="cb1-15"><a href="#cb1-15" aria-hidden="true" tabindex="-1"></a>)</span></code>
```

模型配对有约束：advisor 必须不弱于 executor。Haiku 4.5、Sonnet 4.6
这些便宜的 executor，advisor 选项是 Opus 4.7 或 4.8。计费上，advisor 的
token 按 advisor 模型的费率算，在 usage block
里单独列出，max_uses 是主要的成本控制手段。Claude Code
里输入 /advisor 也能直接开。

那 Fable 5
呢？它发布当天就进了兼容表，但只占了对角线上的一格：executor 是 Fable 5
时，advisor 才能是 Fable
5，用途是在执行中途要一个不带工具、通读全场的第二意见。你真正想要的那个组合，Sonnet
或 Haiku 干活、Fable 5 当顾问，还没有开放。不过跨档配对有先例可循：Opus
4.8 在 5 月发布后，很快就出现在了便宜模型的
advisor 选项里。更重要的是，Fable 5
恰好是为顾问位置而生的定价。每百万输出 token $50，端到端跑 agent
很难算得过账；但顾问角色一次只产出几百个 token
的建议，贵的单价乘以小的用量，恰好是这种定价下唯一舒服的用法。在那个组合开放之前，订阅用户手里还有一张免费票：6
月 22 日之前 Claude Code 里可以直接用 Fable
5，这两周是测它上限的窗口期。长期想在 agent
里留住这个等级的智能而不被账单劝退，advisor 模式就是那个结构。

## Caveats

四件事说在前面。第一，Claude Code 的集成目前问题最多。advisor
子推理的 token 会被重复计入主上下文，这个
issue 挂了五个星期没修；CLI 拒绝 Haiku
做 executor，和 API 文档矛盾；经过 LiteLLM proxy
时会断。想认真评估这个 feature，走 API 直连。第二，平台范围有限。只有
Claude API 和 Claude Platform on AWS 可用，AWS Bedrock、Vertex
AI、Microsoft Foundry
都不支持。第三，它有明确的不适用区。单轮问答没有东西可规划；产品如果让用户自己挑模型，再叠一层
advisor 只会把成本模型搞乱；每一步都真正需要 frontier 能力的任务，直接上
Opus。第四，advisor 自己的 prompt caching 是单独的开关，社区实测的经验法则是每个对话三次以上
advisor 调用才回本：长循环开，短任务关。

## 没人鼓掌，但都在接入

发布当天，官方博客在 Hacker News 上拿到
6 个赞和 1 条评论。同一周内，LiteLLM 和 Vercel AI SDK
完成适配，OpenCode 社区提了 feature
request。这两件事放在一起是一个挺准的信号：开发者基础设施在快速消化它，公共注意力还没有看见它，大家盯着的仍然是下一次模型发布。

注意力的错位本身说明了问题。过去两年，“用哪个模型”几乎等于”用最强的模型”，这个等式成立的前提是任务由单个模型完成。Fable
5 的定价给这个等式标了价：继续把最强模型当默认选项，每百万输出 token
收你 $50；把它放进合适的位置，按次付费。AgentOpt
那篇论文说，模型质量是角色和管线交互的函数，不能脱离位置谈强弱。两个月前这还是论文里的实验数据，现在它是
API 里的一个参数，下一步大概率是 Fable 5
出现在便宜模型的顾问选项里。如果你的 agent 正跑在 Sonnet 上，把 Sonnet
单跑、Sonnet 加 advisor、Opus
单跑三组配置各测一遍，半天的工程量，足够你知道这个判断在你自己的工作负载上是否成立。趁
6 月 22 日之前，再顺手在 Claude Code 里感受一下 Fable 5
的上限，你就知道两周后自己愿意为哪个位置上的它付钱了。