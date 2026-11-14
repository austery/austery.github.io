---
layout: post.njk
source: https://yage.ai/share/ai-token-quota-management-20260615.html
speaker: yage.ai
title: |-
  Meta 的 73 万亿 token
  账单，和一个管理者早就会解的问题
date: '2026-06-15'
summary: 文章探讨了当前AI应用中Token消耗带来的成本危机，指出解决之道不在于技术手段本身，而在于将AI的资源管理和分配模式类比为传统的人才管理。核心思想是建立分层用工、上下文工程和Prompt缓存等策略，通过按产出评估而非活动量来优化资源配置，实现AI资源的有效治理。
area: tech-engineering
category: ai-application
tags:
  - token-management
  - model-routing
  - context-engineering
  - prompt-caching
people: []
companies_orgs:
  - Meta
  - Uber
  - Anthropic
  - Cursor
  - Klarna
products_models:
  - Claude Opus
  - Claude Code
  - GPT-4 Turbo
  - Mixtral
media_books: []
draft: true
status: evergreen
---

## 一个排行榜和一场补贴周期的终结

2026 年春天，Meta 员工 Ash Bhat 在公司内网搭了个排行榜，取名
Claudeonomics。排行榜追踪约 85,000 名员工的 token 消费，RPG
风格分级，从青铜爬到绿宝石，设置了 Token Legend、Session Immortal、Cache
Wizard 等称号，公开显示 top 250。KuCoin
对事件的还原报道。最猛的那个人 30 天烧了 2810 亿 token，按 Claude
Opus 公开价粗算，约 $420 万。Zuckerberg 和 CTO Bosworth 都没进前
250。

这个 85,000 人的公司 30 天 token 消耗从约 60 万亿攀升到 73.7
万亿，数十亿美元量级（Meta 内部预测，非财报数字）。Claudeonomics
不是孤例。Uber 给 5000 名工程师开通 Claude Code，四个月烧完全年
AI 编码预算，COO Andrew Macdonald 在播客上公开质疑 token
花费和实际产出的链路：「That link is not there yet.」

账单失控的底层原因是补贴结构。Claude Code 的 $200 月订阅背后，据
Cursor 内部估算、重度用户单月消耗可达 $5000 计算，约
25 倍于订阅价的补贴（Anthropic
未确认）。补贴收窄之后，成本显性化的后果很快显现。Klarna 用 AI 替代约
700 个客服岗位后，CEO 承认服务质量「lower quality」，随后以
gig 制重新招人。Meta 自己也在 6 月发给约 6000
名员工的备忘录里定调：「In 2027, we expect Meta will move toward
managing AI tokens in a more structured way—with budgets, allocation
decisions, and supporting tools.」来源
补贴周期正在结束，2027 年是 token 配额元年。

## 这不是新问题

这件事看起来像是 AI 时代新冒出来的成本危机。但它不是。

把 AI
当成一支劳动力来管：分配任务、控制预算、评估产出，这些事每个管理者每天都在做。当
AI 感觉免费时，企业暂停了所有资源分配的纪律：不做路由、不测
ROI、不设预算、把活动量当产出。仔细读 Bosworth
的备忘录，他就是在说同一件事：把你们早就懂的知识工人管理纪律，重新拿出来用在
AI 上。ServiceNow 首席客户官 Chris Bedi 说得更直接：

> “It’s almost like measuring a restaurant based on how many
> ingredients they buy. You don’t measure a restaurant that way. I
> wouldn’t.”

衡量餐厅从不看它买了多少食材，衡量 AI 也不该看它烧了多少 token。来源

如果 AI 成本管理就是人才管理，那管理学的 playbook 具体怎么翻译到 AI
上？四条直觉，每条对应一个可操作的动作。

## 四条直觉，四个动作

分层用工 → 模型路由。
每个经理都知道把最贵的人留给最难的活，日常事务交给便宜的人。AI
场景的对应是模型路由。UC Berkeley 的 RouteLLM 在 coding
和问答这类难度长尾分布的任务上，成本降低 85% 以上，质量保留约 95%（GPT-4
Turbo vs Mixtral，MT-Bench
上的最优结果，换模型对和任务分布会变）。落地最快的路径有两条。交互式
coding 用 Aider 的 architect/editor
模式，贵模型只做规划、便宜模型负责把规划转成代码，o1-preview 在
benchmark 上从 79.7% 涨到了 85.0%，质量和成本双赢。服务端用 LiteLLM
或 OpenRouter 做规则级 fallback，几小时内能接入。

分层用工解决了用什么模型。下一步是给模型看什么。

给新人 bounded scope → context 工程。 你不会把整个
codebase 丢给一个新人让他自学，你会给他明确的任务边界。AI 的对应是
context 工程：不把整个 repo 灌进 context，用 RAG 检索、sub-agent
隔离、repo map 把每次调用的 token 量压下来。长 context
有两重负担：每轮要付全量输入价；context
越长模型注意力越容易分散、准确率越低，需要更多重试，成本反向上升。Aider
的 architect/editor
模式把一次代码改动拆成规划（贵模型）和执行（便宜模型），本质就是 context
工程的分工：每个模型只看自己需要的那部分信息。

context 工程压的是每次调用的 token 量。并行的一条线是压单价。

别每次都请顾问 → prompt 缓存。
外部顾问按次计费、单价高，聪明的公司会把顾问的方法沉淀成内部
SOP，下次不请顾问也能做。AI 的对应是 prompt 缓存：把 system
prompt、代码库上下文在 provider 侧缓存成键值对，后续命中只付折扣价。Anthropic
给 90% 折扣，OpenAI
给 50% 且全自动，Gemini
给 90%。接入成本半天，质量零损失。不做这件事等于每轮为同样的 context
全价付费。

技术手段能压成本，但如果考核指标本身是 token
消耗量，再好的技术也白搭。

按产出评估，不按活动量。 Bill Gates
那句被引用了三十年的判断：「Measuring programming progress by lines of
code is like measuring aircraft building progress by weight。」token count
是 AI 时代的 LOC。Bosworth 在六月备忘录里给出了同一个判断的 AI
版本：

> “All motion is not progress and token usage alone is not a measure of
> impact of any kind.”

来源
Jellyfish 对 12,000 名开发者的分析把这个判断落到了数字上：最高用量组每
PR 烧 10 倍 token，PR 吞吐量只有 2 倍；单 PR 成本从 $0.28 飙到
$89.32，质量并不比低用量组更好。来源
考核 token 消耗，团队就会去优化 token 消耗而不是产出。Goodhart 定律在 AI
上照常运转：当一个指标变成目标，它就不再是好的指标。

按产出评估是对的，但它引出一个更棘手的问题：如果团队知道每花一笔
token 都要被算 ROI，他们还会试错吗？

## 成本控制会不会杀死好奇心？

Bosworth 自己给出了教科书式的反面案例。2026 年 4 月他在 Forbes 上力挺
tokenmaxxing（据媒体报道）：「It’s like getting free money. Keep racking
up tokens with no upper limit.」来源
两个月后，他自己发了那封「of any
kind」的备忘录。从「无上限烧」到「全量不算产出」，是两个极端之间的摆荡。

真正要保留的是探索的冲动，真正要加的是升级的信号。分层使用的含义不是禁用，而是用便宜模型自由探索，遇到
hard case 才升级。这是 Lean Startup 的 MVP 直觉在 AI
上的平移：用最小成本验证最险假设。Stage-Gate 的 kill criteria
和路由器里的 confidence threshold 是同一个东西的两个名字。Jensen Huang
在 GTC 上主张 token
预算等于年薪一半，这是把补贴制度化而非精细化的另一个极端。正确的点在中间：给预算，但按产出调配而非按人头平分。腾讯已经在这个方向做了调整：从人均等额转向按工作任务动态调配，不搞
token 消耗量排名。

## 2027 是正常经济学的回归

2027
年是配额元年，但配额不是终点，是正常经济学的回归。补贴周期让很多人忘了
AI
也是资源，也有单价，也需要被分配。当账单显性化，最先适应的人赢：他们早就把
AI 当劳动力在管。会管人的管理者，已经会管 AI 成本了。你脑子里的 playbook
没变，变的只是它在 AI 上的应用。