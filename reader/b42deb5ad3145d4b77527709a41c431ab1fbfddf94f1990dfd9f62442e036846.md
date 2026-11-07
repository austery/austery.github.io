---
layout: post.njk
source: https://yage.ai/share/openai-deployco-anthropic-pe-divergence-20260511.html
speaker: yage.ai
title: |-
  DeployCo 来了：OpenAI 和 Anthropic
  在同一天发明了同一家公司，然后走向了相反的方向
date: '2026-05-11'
summary: 文章分析了 OpenAI 和 Anthropic 推出类似 AI 部署合资企业（JV）的现象，将其视为 AI Rollup 的第三代演进。OpenAI 将模型视为核心资产，JV 是高成本渠道；Anthropic 则将部署服务视为核心，模型为配件。两者策略迥异，但都面临 AI Agent 间竞争导致利润趋零的风险。
area: tech-engineering
category: tech-trends
tags:
  - ai-rollups
  - enterprise-ai
  - business-strategy
  - llm-deployment
people:
  - Sam Altman
companies_orgs:
  - OpenAI
  - Anthropic
  - TPG
  - Blackstone
  - McKinsey & Company
  - Klarna
products_models:
  - GPT
  - Claude
  - Gemini
  - DeployCo
media_books: []
draft: true
status: evergreen
---

调研日期：2026-05-11 调研范围：5 月
4 日 OpenAI / Anthropic PE 合资企业的策略逻辑、三代 AI Rollup
演化、两家的策略分歧与风险

5 月 4 日，OpenAI 和 Anthropic 先后宣布了同一个结构：与 PE
公司成立合资企业（Joint Venture，简称
JV。两家或多家公司共同出资成立一家新公司，各自出钱出资源，按约定分利润和承担风险），向大型企业部署
AI。SiliconSnark 的概括流传最广：“the technology industry’s two most
philosophically opposed AI companies simultaneously announced they had
invented the same
company.”两家在数据来源、安全理念和开源立场上长期分歧的实验室，在同一天给出了同一种市场答案。

今天（5 月 11 日），OpenAI
发布了 DeployCo 的正式公告，公布了更多细节：收购 Tomoro 获得约 150
名 Forward Deployed Engineer 从第一天就进场、$4B+ 初始投资、TPG 领投的
19
家投资机构加三家咨询商的完整合作名单。但把两家的条款摊开来看，它们做的其实是完全不同的两件事。这两件事和过去半年
AI 行业里一条正在演化的路线（AI
Rollup）连起来读，能讲清楚模型公司接下来一两年最值得跟踪的竞争维度。

## 三代 AI
Rollup：这件事是怎么走到 PE 这一步的

AI Rollup
这个模式在过去半年经历了三次迭代。每一代都在回答同一个问题：AI
怎么进入真实企业，而不是停留在 demo 里。

第一代是传统 PE rollup。
在碎片化行业里低价收购小公司，通过集中后台、标准化流程来降本，整合后以更高估值退出。Thrasio
是典型反例：$16B 资金涌入 Amazon 品牌聚合赛道，90%
的公司正在挣扎或已死亡。这一代的局限在于没有技术差异化，纯靠运营效率。

第二代是 VC-backed AI Rollup。 General
Catalyst 划拨 $1.5B、Thrive Capital 部署 $1B+，做法是反过来的：先建
AI 技术平台，再收购传统服务企业，用股权控制权强制推行 AI 变革。Crescendo
二十人团队收购三千人的
PartnerHero，靠的就是这个逻辑——你当顾问时只能建议客户部署
AI，当控股股东时可以直接换管理层、重组流程。RAND
的数据显示 80% 的 AI
项目失败，五大原因全是组织性的（问题定义不清、数据不足、权力重分配）。咨询合同解决不了执行问题，只有控股才能强制变革——VC-backed
AI Rollup 的核心洞察就是这个 enforcement gap。（对这个模式的详细分析，见
4 月 9
日的 AI Rollup 调研。）

但 Gen 2
的代价也明显：一家公司要同时做好技术构建、并购整合和运营变革，三类能力的交集极其狭窄。

第三代是 5 月 4 日出现的结构。
三件事拆给三个专业实体：AI 公司负责模型和工程能力，PE 提供 portfolio
company 和控制权，JV 负责实施落地。Reuters
确认 JV
大部分资本将用于收购工程和咨询公司。技术、控制、实施，从一家公司全干变成三家公司各干一段。Gen
2 的模式里 VC 独占整条价值链，Gen 3 的模式里 AI
公司、PE、实施公司各分一块。

5 月 11 日，OpenAI
正式公布了 DeployCo 的更多细节。其中最具体的一条是：OpenAI
已同意收购 Tomoro，一家做企业 AI 咨询和工程的公司，交易完成后约 150 名
Forward Deployed Engineer 将直接加入 DeployCo。DeployCo 的 FDE
会进驻客户现场，做诊断、选优先级工作流、设计并部署生产系统。OpenAI
不打算从零组建实施团队，直接买现成的。

## 为什么是
PE：enforcement gap 需要的不只是钱

Gen 2 用 VC 试水，Gen 3 转向 PE，区别不在于资金规模，在于控股权。

VC 通常拿少数股权。VC 可以说服创始人部署 AI，但无法强制。PE
拿多数股权。PE
可以决定管理层去留、流程改动和系统部署优先级。银行贷款不附带执行机制，咨询报告没有权力替换人，企业软件公司无法保证客户实施深度——PE
可以从股东层面把 AI 部署变成管理层的硬任务。

PE 自己也需要这条路线。传统 PE
的杠杆——降本、财务工程、行业整合——在利率偏高的环境下差不多用完了。AI
是一个全新的运营改善维度。FTI
Consulting 的 PE AI Radar 报告提到多数 PE 已将 AI
纳入投资组合策略。OpenAI 的公告里给出了一个尺度：DeployCo 的 PE
和咨询伙伴加起来 “sponsor more than 2,000 businesses around the
world”，这只是这组伙伴自己的 portfolio company，不含外部客户。

这里还有一层容易忽略的账本：买一家传统 B2B 服务公司 8 倍 EBITDA，注入
AI 能力后讲成 tech-enabled platform，下一个买家可能给到 12
倍。运营效率提升和叙事溢价可以叠加，两边的钱 PE 都想赚。

## 两家的表面一样，底下在答完全不同的题

OpenAI 和 Anthropic 的 JV 在结构上看起来是对称的：都是 PE
合作，都要买咨询公司来组建实施团队。但条款细节显示两家不仅是策略不同——它们对”自己是什么类型的公司”的判断就完全不同。

先看具体条款。

### OpenAI 的 JV

DeployCo
的官方公告给了以下关键数字：OpenAI
保留多数股权和控制权（majority-owned and controlled by
OpenAI），初始投资超过 $4B，用于扩展运营和收购公司。合作方由 TPG
领投，Advent、Bain Capital、Brookfield 作为共同领投方，B
Capital、BBVA、Emergence Capital、Goanna、Goldman Sachs、SoftBank
Corp.、Warburg Pincus、WCAS 等 19 家投资机构参与，另含 Bain &
Company、Capgemini、McKinsey & Company
三家咨询和系统集成商作为投资方。

之前多个信源报道的 $10B 估值和 17.5%
保底回报，在官方公告里没有出现。这两项数字来自 Bloomberg、The
Next Web 和 Forbes
的独立报道，SaaStr
也做了交叉分析。17.5% 保底回报是标准 PE
优先回报（8%）的两倍多。它的意思：不管 DeployCo 赚不赚钱，OpenAI
每年都要先付给 PE 合伙人投资额 17.5% 的回报。PE
拿的是接近无风险的收益，OpenAI 扛了大部分下行风险。换成大白话说，OpenAI
在用高价租 PE 的渠道。

为什么愿意付这个溢价？三类解释同时成立。第一，IPO
叙事需要确定性收入——$852B 估值、$122B
融资之后，任何收入的不确定性都会压低定价。第二，两家在抢同一批优质 PE
关系，竞标推高了价格。第三，OpenAI 在 JV 里保留了多数控制权，在 PE
出钱的情况下保持这种控制权本身不寻常——溢价里有一部分是买这份控制权的代价。

这三条加在一起，指向的不是”渠道不重要”。17.5%
的溢价恰恰说明渠道极其重要——重要到 OpenAI
愿意付市场价两倍的代价来租用它。但关键区别在于它把渠道当作什么。

OpenAI
把渠道当作成本，不是产品。它是一家模型公司，模型是核心产品。但模型不能自动抵达客户——需要有人进驻现场、改流程、做集成、处理内部阻力。OpenAI
的选择不是自己去建这支队伍（那需要太长时间，也会把自己拖进服务业的经济模型），而是花高价把它外包给
PE。17.5%
是一笔巨大的渠道成本，就像航空公司花巨资买飞机但仍然是一家运输公司而非飞机制造商。渠道贵，但它是为了让主业——模型——能运转起来，而不是让自己变成渠道公司。

### Anthropic 的 JV

Anthropic
与 Blackstone、Hellman & Friedman、Goldman Sachs 的合资企业估值
$1.5B，Anthropic、Blackstone、H&F 各出资约 $300M，Goldman Sachs 约
$150M，另有 Apollo、General Atlantic、Leonard Green、GIC、Sequoia
Capital 跟投。TechCrunch
的对照报道明确指出 Anthropic 没有保底回报承诺。

Anthropic 的条款更像对一家传统服务公司的定价——没有保底，估值是 OpenAI
的七分之一。这跟它四月份的 Cowork 3P 策略是一脉相承的：三月堵死了第三方客户端蹭
Claude 订阅的通道，四月在自家 Claude Cowork 里接入了
GPT、Gemini、DeepSeek
等别家模型。两件事放在一起的底层判断是同一个——客户端是粘性，模型是过路货。Anthropic
自己在 4 月 21 日 Managed
Agents 博客里把这句话写了出来：“We’re opinionated about the shape of
these interfaces, not about what runs behind
them.”我们的产品决定接口长什么样，不决定接口背后跑什么模型。

在这个判断下，Anthropic 的 JV 不是模型的管道——它就是 Anthropic
的核心业务本身。Anthropic 卖的是一套帮企业把 AI 跑起来的服务能力：FDE
怎么派驻、工作流怎么设计、系统怎么持续调优。至于是用 Claude 还是 GPT
还是 Gemini
来做这些事，取决于哪个模型在具体场景里更好用。渠道本身就是价值，模型是渠道里的消耗品。

### 为什么两家走到完全相反的方向

放在一起看，两家对同一个问题——AI
公司的核心资产是什么——给出了完全相反的答案。

OpenAI 认为核心资产是模型。GPT
系模型会持续领先，渠道是花钱就能买到的外挂，从 PE
那边租用控制权只是另一种形式的获客成本。它是一家卖模型的公司——只不过这个模型太复杂，客户不会用，需要一套
JV 来当翻译。

Anthropic
认为核心资产是客户关系和工作流。模型正在变成可互换的部件——GPT-5.4、Opus
4.6、Gemini 3.1 Pro 在通用 benchmark 上只差个位数，Sam Altman
自己也承认 “transformer models have hit the
wall”。当模型差距收窄到这点，竞争就会从”谁家模型最强”变成”谁最会帮客户用起来”。Anthropic
不是在卖模型，是在卖部署服务——模型只是服务里的一个配件，今天用
Claude，明天换 Gemini，服务本身不变。

两种赌法各自有各自的脆弱面。如果模型真的商品化了，OpenAI 的 17.5%
会成为沉重的固定成本——模型不再赚那么多了，但每年还要付 PE
保底回报。如果模型没有商品化、GPT 持续拉开差距，Anthropic
建的那条模型无关的部署管道就失去了核心卖点——当客户要求”给我最好的模型”而不是”帮我设计工作流”时，一个模型中立的服务公司比不过一个模型垄断者的直销团队。

## 一个更底层的风险：Agent
互相蚕食

前面讲的两家分歧有一个共同前提：企业部署 AI
这件事本身是有利润的。但如果两家 JV 生成的 AI agent
同时进入同一个市场，这个前提就不一定成立。

逻辑是这样。如果没有竞争，一家年收入 $100M 的服务公司用 AI
提效之后，收入规模不变，利润率跳升——这是一笔好生意。但如果 OpenAI 的
DeployCo 和 Anthropic 的 JV
同时往同一个赛道（客服外包、会计自动化、法律服务）里放 AI agent，两边
agent 就会开始互相压价抢客户。

Anthropic 自己的 Project Deal
实验已经提前演示了这件事：在一个全是 AI agent 的市场里，Opus agent
系统性地从 Haiku agent 那里抽取了价值——Opus 卖家多卖
$2.68（p=0.030）、Opus 买家少付 $2.45（p=0.015），被抽走价值的 Haiku
用户主观上完全没感觉。放到真实市场上，如果两家 JV 都往同一个赛道里放
agent，最后的结果不是两家的 agent
服务都赚钱，而是它们互相把利润吃到零。效率提升本身不缩小市场——竞争才会。

Klarna
的逆转也提醒同一件事的反面：即便没有竞争压力，AI
部署本身也可能把服务做差。Klarna 2023 年用 AI 裁掉 700 名客服，到 2025
年全面逆转——问题解决时间增加 27%、不满意交互增长 35%。Fortune
那句判断讲得很直接：“Services businesses aren’t inefficient by
accident. They’re inefficient by design. The inefficiency is the
product. Clients pay for flexibility, customization, and someone to
blame when things go wrong.”

## 总结

过去半年 AI
行业的竞争维度发生了两次迁移。第一次从模型能力转向运行时——同样的 Claude
Opus 在不同 harness 里跑 SWE-bench 差 16
个百分点，模型不是终点，怎么用模型才是。第二次从运行时转向渠道——当模型差距收窄到个位数，谁有办法让企业真正用起来，谁就拿到了下一阶段的入场券。McKinsey
的年度调查数据给了一个尺度：88% 的企业已在至少一个职能使用
AI，但不到 10% 实现了规模化部署。差出来的 90%，瓶颈不在 API
质量，在于谁来改流程、谁来迁数据、谁来替换岗位、谁来处理内部阻力。PE
是这个逻辑下的极端表达：它不光有资本，还有可以把 AI 部署写进管理层 KPI
的控制权。

5 月 4 日，OpenAI 和 Anthropic
在这个判断上是一致的，一致到同一天交了同一份答案。但他们对”自己是谁”的判断完全相反。OpenAI
是一家卖模型的公司，JV
是它花高价租来的渠道，买的是把模型送进企业的通路。Anthropic
是一家卖部署服务的公司，JV 就是它的主营业务本身，模型只是服务里今天用
Claude、明天可能换 Gemini 的一个配件。

两种赌法都可能赢，也可能都输给同一个风险：两家 JV 生成的 AI agent
互相竞争到一个没有利润的均衡点。这不会改变明天的工作，但如果你在判断 AI
产品的竞争策略，它告诉你下一步的竞争对手不只是其他模型团队，还包括那些控制着企业入口的
PE、它们刚组建的实施公司——以及它们手上会在市场上互相压价的 AI
agent。