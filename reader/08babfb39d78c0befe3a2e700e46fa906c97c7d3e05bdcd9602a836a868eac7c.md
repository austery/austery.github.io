---
layout: post.njk
source: https://yage.ai/share/skill-plugin-evolution-20260507.html
speaker: yage.ai
title: |-
  面对 Skill 的盈利死结，OpenAI 和 Cursor
  交了同一份答卷——但答的是不同的题
date: '2026-05-07'
summary: 文章分析了 OpenAI 和 Cursor 公司从 AI Skill 转向 Plugin 的原因。Skill 因易于复制而难以盈利，而 Plugin 通过绑定运行环境、认证凭证和分发渠道，将知识转化为可收费的服务。OpenAI 旨在通过 Codex Plugin 构建执行层，锁定用户工作流；Cursor 则希望通过 Plugin 生态系统构建差异化优势，逃离供应商替代风险。两者都将 Plugin 视为战略工具，而非直接盈利产品，预示着 AI 工具生态的演变方向。
area: tech-engineering
category: software-development
tags:
  - ai-plugins
  - monetization-strategies
  - execution-layer
  - vendor-lock-in
people: []
companies_orgs:
  - OpenAI
  - Cursor
  - Anthropic
products_models:
  - Codex Plugin
  - GPT-5.5 Instant
  - Claude Code
  - Composer
  - Kimi
  - SKILL.md
  - MCP
media_books: []
draft: true
status: evergreen
---

OpenAI 和 Cursor 在同一时间窗口里，不约而同地把重心从 Skill 移向
Plugin。OpenAI 把去年重点宣传的 frontend skill 从官方列表里拿掉，转成 Codex
Plugin 的形式发布；Cursor 在自己的 marketplace 上推 plugin-builder
能力，鼓励开发者为 Cursor 生态写 plugin。两件事先后发生在 2026 年 4-5
月，连同 GPT-5.5 Instant 的发布，看起来像是一轮协调的产品更新。

表面看是同一个动作（从 Skill 转向
Plugin），但驱动这个动作的原因在两家公司那里完全不同。OpenAI 和 Cursor
在这场防御战中要解决的问题和面临的生存威胁，几乎不能放在同一个框架里看。

## 同一个诊断

先把起点对齐。如果你写过或者装过一个 AI
skill，你可能已经直觉上感觉到一个问题：这个东西很难收钱。4 月 24
日的文章《Skill
是天生带自杀基因的产品》把这个直觉拆成了三层，一层一层说清楚了为什么。

第一，Skill 是明文文件。买家付完钱就能贴到 GitHub
上，第二个买家就不来了。复制成本为零的东西，定价权也是零。第二，那做成托管服务来收费呢？本质上变成了卖
AWS
转售，因为用户随时可以把文件下载到本地免费跑。第三，数据飞轮也走不通——Skill
执行发生在用户调用 LLM 的瞬间，数据全进了 LLM 提供商的日志，Skill
作者既拿不到钱也拿不到反馈来改进。

三层叠加在一起的结果：社区里出现了 Agensi、skills.sh 等 marketplace
尝试帮 Skill 做分发，但都卡在同一个环节——buyer
拿到文件之后就不再需要平台了。问题不是谁做得不够好，是这种产品形态本身没法独立承载一个商业模式。

Plugin 就是 OpenAI 和 Cursor 对着这个诊断各自写出的处方。

## Plugin 比 Skill 多了什么

OpenAI Codex Plugin 和 Cursor Plugin
在要补的东西上高度一致，说明双方对”问题出在哪”的判断是共享的。

Skill 是一个 .md 文件，Plugin 比它多三样东西。

第一，运行环境绑定。Plugin 不只是指导 AI
怎么做事的说明书，它还会声明自己需要什么运行环境——Codex Plugin 用
agents/openai.yaml 声明 UI 和依赖，Cursor Plugin 用 MCP
server
配置声明外部工具。这意味着用户不是拿到一个文件，是在平台上获得一个能直接运行的能力。平台因此有了收费的理由：我帮你托管运行环境。

第二，认证凭证。Plugin 的认证跑在平台侧——OAuth token、API
key、数据库连接串全部在 Plugin
的托管环境里管理。平台的收费点从”卖文件”变成了”卖服务链”。这和 Skill
自杀基因文章里分析的”托管路线”本质一样，但现在多了分发和发现作为附加价值。

第三，分发渠道。Plugin catalog
提供的是持续的分发——用户能在工具内部直接搜索、安装、更新。Skill
如果是名片，Plugin catalog
就是简历网站：你的能力一直在柜台上放着，随时有人路过看到。

三样东西放在一起，逻辑就清楚了：Plugin
把”知识”变成了”服务”。知识一旦传出去就收不回来了，但服务是持续性的——它需要运行环境、需要认证维护、需要更新迭代。收费点也就有了落脚的地方。

## OpenAI 的真正动机：执行层防线

理解 OpenAI 为什么要做 Plugin，需要先看它在 2026
年面对的生存威胁。

到 2025
年下半年，模型商品化的趋势已经很明显了。各家模型之间的能力差距在缩小，基准测试分数从相差几十个百分点缩到几个点以内。企业也开始精明起来——不再只绑定一家模型供应商，而是根据成本、速度和集成体验来选择和切换（The
Economist）。同时 OpenAI
的运营成本在飞涨，训练一次前沿模型要花数亿到十亿美元。

这种情况下，OpenAI
面临一个风险：如果模型本身变成商品，它就会从”平台定义者”降级为”众多 AI
提供商之一”——有影响力，但利润空间被成本和竞争夹在中间。Forbes
最近一篇报道用一句话点出了 OpenAI
的应对思路：“界面层的优势驱动的是使用量和订阅收入。执行层的优势塑造的是运营依赖和长期锁定。”

翻译一下就是：在模型层卖智能赚的是流水，在执行层管工作流赚的是绑定。Codex
和它的 Plugin 体系，就是 OpenAI 在执行层的布局。

数据可以说明这个布局的规模。Codex 从 2025 年底的 3 万周活开发者增长到
300 万，增长了 100 倍。更值得注意的是，Codex
的用户中接近一半在做非编码任务——它在从一个开发者工具变成一个通用的工作执行环境。Plugin
catalog 是这个执行环境的应用商店：用户装的 plugin 越多，整个工作流对
Codex
的依赖就越深。即使背后换成其他模型，切换的工作流成本也已经很高了。

所以 OpenAI 做 Plugin
的动机跟直接赚钱关系不大。它真正想做的是：在模型能力趋同的世界里，在模型层之上建立一个执行层，用这个执行层把用户的依赖绑在工作流上，而非模型选择上。
Plugin 只是这个策略里的一环——让用户感觉”我用的是 Codex
的弹性和生态”，而不是”我用的是 GPT-5.5 的智能”。

## Cursor
的真正动机：逃离供应商陷阱

Cursor 面对的生存威胁跟 OpenAI 完全不同，但同样致命。

先想一个很简单的商业问题：如果你从批发商进货再卖给客户，批发商突然决定自己开店，你怎么办？Cursor
就处在这个位置上。它自己做 AI 编辑器，同时也自己训练模型（Composer
系列）——不过训练路线是从开源底座做继续预训练加
RL，而不是从零开始完整预训练（Cursor
Composer 2 分析）。这意味着 Cursor 既需要从 Anthropic 和 OpenAI
调用模型，又面临着 Anthropic 通过 Claude Code 直接竞争的风险。TechCrunch
的报道明确指出 Claude Code 是 Cursor 最大的竞争对手。

更紧迫的是另一个数字：截至 2025 年底，Cursor
一直在亏本卖产品。调用第三方模型的成本高于它能向用户收取的费用，毛利率是负数。直到
2025 年 11 月推出自研的 Composer 模型，加上接入了 Kimi
等低成本模型，才勉强实现正向毛利——而且只在企业用户上，个人开发者账户仍然亏钱。

放到一起看，Cursor 做 Plugin
的动机就很清楚了。它必须在模型层之上建立一个差异化层：让用户的开发工作流中有一部分是
Cursor 独有的，不能无缝迁移到 Claude Code 或 Codex。这个差异化层就是
Plugin + .cursorrules + MCP
集成构成的生态。如果用户的代码审查流程、数据库 schema
管理、部署管线全部通过 Cursor 的 plugin 串联，那即使 Claude Code
更好用，切换也不是一键能完成的。

这解释了为什么 Cursor 的 Plugin 体系特别强调 MCP 集成和.mdc
规则文件——这些东西跟编辑器深度绑定，不像 SKILL.md
那样可以跨平台带走。

## 两份处方为什么去往不同方向

OpenAI 面对的威胁是模型商品化。它的应对是在模型层之上建执行层。Plugin
是执行层的一部分，目的是让 Codex 成为”工作实际发生的地方”：用的是 GPT
还是 Claude不重要，只要工作在 Codex 里完成就行。

Cursor 面对的威胁是供应商替代。它的应对是在模型层之上建生态层。Plugin
是生态层的一部分，目的是让 Cursor 编辑器的体验不能被其他工具复刻：用的是
Claude Code 还是 Codex 不重要，只要你的工作流绑在 Cursor 上就行。

相同点是，两家都不指望 Plugin 本身能产生多少直接收入。Plugin
是战略工具，不是产品。这在商业史上有无数先例：浏览器插件市场本身不赚钱，但它让浏览器成为桌面入口；WordPress
插件生态不收分成，但它让 WordPress 统治了 CMS 市场。

不同点在于，OpenAI 有从模型到执行层的完整控制链，它的 Plugin
体系可以覆盖更深的运行时功能（比如 Plugin 能直接调用 Codex 的 background
computer use 能力）。Cursor 的控制链在编辑器这一层，它的 Plugin
更需要借助 SKILL.md 和 MCP 这类跨平台协议来补齐能力。这决定了两个 Plugin
体系的扩张方向会不一样：OpenAI 能把更多能力绑定到 Codex 运行时上，Cursor
则必须保持对多种模型和工具的兼容。

所以第一个问题的答案是：OpenAI 和 Cursor 的目的不一样，但在
Plugin 这件事上兼容。OpenAI 想建执行层，Cursor
想建差异层，两者使用的工具高度重合（MCP、SKILL.md、Plugin），但出发点不同。这种兼容性让开发者短期内不需要选边站，但也意味着长期的分化压力是存在的。

## 一个架构推演：Plugin 会统一吗

如果把目光放到两年后，两种 Plugin
策略可能走向分化，也可能走向收敛。

分化的逻辑是：OpenAI 的 Codex 运行时和 Cursor
的编辑器体验是两个不同层级的控制点。Codex Plugin 会越来越依赖 Codex
独有的能力（background computer use、跨 session 自动化），Cursor Plugin
会越来越依赖编辑器独有的能力（.cursorrules
的上下文注入、Composer 的交互模式）。两边各自长出自己的高级
Plugin，而且互相不兼容。

收敛的逻辑是：SKILL.md 和 MCP 这两个跨平台协议还在快速进化。如果
SKILL.md 能覆盖 Plugin 需要的依赖声明和认证配置，如果 MCP 能覆盖 Plugin
需要的运行时绑定，那 Plugin 和 Skill
的差异就只剩下”谁来做分发”——这一层可能收敛到统一的标准上，各平台只在发现和支付环节做差异化。

哪种路径更可能？取决于一个更根本的动力：平台的现金流压力。目前三家的状态都是投入期——Anthropic
Enterprise Marketplace 初期 0% 抽成、GPT Store 的分成至今没兑现、Codex
Plugin 也没公开分成方案。投入期持续越久，平台越没动力把 Plugin
生态圈在自己手里，因为社区共享能让生态更快长大。但如果其中一家发现
Plugin 能成为独立收入引擎，统一化的动力就会减弱。

窗口能开多久很难说，但至少 2026 年写一个技能文件在 30
个工具里通用这件事（Noqta），大概率不会在短期内出问题。

调研时间：2026-05-07。关键来源：The
Economist: OpenAI faces make-or-break year、Forbes:
Codex Agents Running Data Platform、TechCrunch:
Cursor $50B valuation、Noqta:
SKILL.md Adoption、Skill
Suicide Gene、OpenAI
Codex Update、Digital
Applied: Codex Plugin Analysis