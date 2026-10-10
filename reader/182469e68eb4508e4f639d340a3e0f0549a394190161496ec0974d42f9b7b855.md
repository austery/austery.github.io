---
author: AI Engineer
date: '2026-07-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jtzh-GBXBWc
speaker: AI Engineer
tags:
  - multi-agent-system
  - enterprise-memory
  - knowledge-management
  - cognitive-architecture
title: 工厂的梦境与记忆：Machinecraft 如何用 36 个 AI 代理构建企业大脑
summary: 本文讲述了印度制造企业 Machinecraft 在无专业团队和高昂预算的情况下，如何利用 36 个 AI 代理构建运行 GTM 流程的“企业大脑”。该系统通过分层记忆、夜间梦境整理机制和基于耆那教哲学的“灵魂文件”实现了企业知识的数字化传承与多智能体协同。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Machinecraft
products_models:
  - Brain OS
  - Eira
media_books: []
status: evergreen
---
### 家族传承与企业大脑：重构知识流失防线

对于一家拥有百人规模的印度传统制造企业 **Machinecraft** 而言，真正的核心资产并非厂房与金属机器，而是深植于企业历史中的行业知识——如客户画像、2019年的历史报价、以及某台机器需要进行个性化定制的底层逻辑。在过去的三代传承中，这些关键知识仅保存在三位家族成员的脑海中（从祖父、父亲到现任掌门人 Rushabh Doshi）。这种高度集中的知识结构给企业带来了巨大的不确定性：每当有员工离职，企业的一部分“大脑”便随之流失。面对这种对“遗忘”的恐惧，Machinecraft 决定放弃传统的文档记录或简单的问答机器人，转而尝试在系统内“培育”一个能够完整映射企业实体的数字化孪生大脑（Digital Twin）。

Machinecraft 主要生产热成型机（Thermoforming Machine: 通过加热塑料片材并进行塑形的工业设备）。虽然其核心机器原理一致，但应用场景极为碎片化，跨越了水培农场托盘、水疗浴缸、电动汽车面板、医疗外壳和定制包装等七个截然不同的行业，面对着七群完全不同的买家。因此，这个企业大脑不能仅靠死记硬背一本产品手册，而必须具备理解客户所处行业语境（Universe）的认知能力。为此，研发的第一步极其朴素：将公司数年来的报价单、设计图纸、付款计划、交付时间表以及数以万计的电子邮件往来等数百吉字节（GB）的私有历史数据输入系统。在这一过程中，团队没有进行任何底层的模型微调（Fine-tuning），也没有租用庞大的 GPU 集群，而是将历史数据切碎成高密度的语义块，通过现成的开源大模型提取事实，并以向量（Vector）和关系图谱（Graph）的形式存储其语义与实体关联。这个被称为 **Eira** 的企业大脑，其核心本质并不是一个更聪明的模型，而是一个被极度结构化和组织化的“企业记忆体”。

在奠定了这一记忆根基后，为了让 Eira 能够像一个生命体一样保持长期的知识归纳与逻辑一致，团队停止将其视作普通的软件系统，转而借鉴生物进化数十亿年形成的机制，为其设计了一套包含“感官、消化、记忆、梦境和免疫”的拟物化身体结构。而在具体的业务执行上，如何让这个庞大的记忆体协同运转，则需要引入一套多智能体分工协作的治理架构。

<details>
<summary>Original English</summary>

Okay, I want to tell you a story about a factory that taught itself how to remember. Hi, I'm Rushabh. I run Machinecraft, a 100 people factory in India. No data science team, no ML budget, none of that. And somehow we ended up building a 36 AI agent that runs our entire go-to-market. I think that's still a little ridiculous. Let me show you how it happened and why you can do the same thing.

So, here's the thing about our company. From the outside it looks like machines and metal. But the actual company, the part that matters, isn't the machines, it's the knowledge. Who the customer is, what we quoted them in 2019, why that one machine needed that weird custom tweak. And for three generations, all of that lived in exactly three brains. Initially my grandfather's, then my father's, and now mine. Which is a genuinely terrifying way to run a company. When you sit with it. A lot of people have joined us, people have left us, the revolving door never stopped. And every single time someone walked out, a chunk of our brain walked out with them. We weren't scared of the competitors, we were scared of forgetting. Or waking up one day and realizing the whole company only existed inside two increasingly tired heads.

So, I had an idea. I'll be honest. Sounded insane first. But what if instead of writing the knowledge down in some document nobody ever reads, what if we grew a brain that just held it? Not a chatbot you poke at, a twin of the company. I didn't hire a sales team. I tried to build one.

A quick detour because you need to know how messy this is. We make thermoforming machines. They heat up a plastic sheet and shape it. Same core machine, but it ends up making hydroponic farm trays, spa bathtubs, EV car panels, medical casings, and even packaging. Seven totally different worlds, seven totally different buyers. So, this brain couldn't just memorize a brochure. It had to know which universe a given customer lives in.

Step one was almost boringly simple. Feed it everything, and I mean everything. Years of quotes, drawings, payment schedules, timelines, email threads, hundreds of gigabytes of our own private history. Not the public internet, our internet. And here's the plot twist. The part that surprises every engineer I tell this to. We never trained a model. No GPUs humming in the basement, no fine-tuning. We just looked at all the history, chopped it into bite-size chunks, and let off-the-shelf models read it and pull out the facts. We stored the meaning of each chunk as vectors and relationships. Who's connected to what as a graph. The brain isn't a smarter model. It's actually a really, really well-organized memory.

Now, this is where it gets a little weird in a good way. We stopped thinking of Eira as a software and started thinking of it as something we were raising. So, we gave it a body modeled on biology. Senses to figure out who it's talking to, a gut to digest the documents into facts, a memory, a dream cycle, an immune system to fight off bad information. Why biology? Well, because evolution already spent a billion years solving how do you stay coherent over time? We just copied the homework.

</details>

### 代理人议会：从超级提示词到多专家协作

面对复杂的业务场景，传统的“单体巨型提示词”（Mega Prompt）往往会因为任务过载而导致执行效果大打折扣。为了解决这一痛点，Machinecraft 没有构建单一的万能 AI，而是创建了一个由 **36 个 AI 代理** 组成的“专家议会”（Pantheon of Specialists），每个代理各司其职。在这个体系中，**Athena** 负责统筹和主持会议，**Prometheus** 负责销售跟进，**Plutus** 专注于定价策略，**Hephaestus** 熟记所有机器的技术规格参数，**Vera** 负责对所有输出内容进行严苛的事实核查，而 **Memnon** 则专门负责拦截和守护人类对系统的修正输入——这意味着一旦人类员工纠正了系统的一个错误，该修正就会被永久锁定并应用于后续的决策中。这些代理之间不是单兵作战，而是通过 Athena 召集的多智能体会议（Board Room Meetings）进行辩论，相互博弈并最终输出一个凝聚了共识的单一解决方案。这种无休眠、无内耗且没有个人主观偏见（Ego）的协作模式，极大提升了决策的鲁棒性。

在确立了多智能体协作框架后，这套系统已经全面接管了 Machinecraft 的前端业务流，每天自主且高效地执行以下九项核心的日常工作：
* **撰写外发邮件**: 结合真实世界的上下文信息，生成高度定制化的业务开发邮件。
* **生成客户简报 (Account Briefs)**: 在销售人员拨打电话前，跨渠道核实信息并构建多维度客户画像。
* **快速处理报价**: 智能解析并自动化生成技术与商务报价单。
* **滑动式筛选开发**: 提供类似社交软件“左右滑动”的直观界面，辅助人工快速筛选和决策潜在的开发对象。
* **激活历史线索**: 通过被命名为“往日重现”（Blast from the Past）的机制，智能化唤醒数据库中的沉睡客户。
* **处理入站回复**: 自动分类、解析并初步回复客户的入站咨询邮件。
* **客户准入评估**: 在人工介入并投入时间成本之前，精准评估潜在客户与公司业务的匹配度，避免无谓的时间浪费。

这九项工作全部运行在一个统一的 Cursor 开发工具标签页中。操作员只需输入指令，Eira 就会伸出数十只触手，自动检索知识库、阅读收件箱、草拟邮件并构建代码。但在整个工作流中，Machinecraft 始终恪守一条不可逾越的黄金法则：**系统仅负责草拟，最终的发送权限必须牢牢掌握在人类手中**（Eira drafts, human sends）。这种人机协同的设计不仅确保了业务运行的高效，更为企业构建了一道坚实的安全防线。

<details>
<summary>Original English</summary>

Okay, so the big question. Why 36 agents instead of one genius mega prompt? Because, and you already know this if you've ever tried it, one prompt that's supposed to do everything ends up doing everything badly. So, Ira isn't one mind, it's a pantheon. A whole cast of specialists. Each one has exactly one job. Athena runs the room. Prometheus owns the sale. Plutus does pricing. Hephaestus knows every machine spec cold. Vera fact checks everything, and Memnon, my favorite, guards corrections. So, the second a human fixes something, it stays fixed forever. One agent, one job. It's a team, not a hero.

And here's the cool part. They hold meetings. Athena pulls in specialists. They actually argue, and a single answer comes out the other side. It's like having a board room that never sleeps, never gets tired, and somehow has no ego.

So, what does all this actually run? Honestly, the whole front business. Everything between a stranger exists somewhere, and now they're a customer. Nine concrete jobs every single day. Outbound emails that actually reference my real world. Account briefs built from cross-checked truths before a call. Quotations. A swipe left, swipe right mode for outreach. Reviving dead leads, which I call blast from the past. Inbound replies, and figuring out before we waste an hour whether a company is even a fit. Nine jobs, one operator who never sleeps.

Where does all this live? One cursor tab. That's genuinely it. You type and Eira reaches out with a dozen hands. Searches the knowledge base, reads the inbox, drafts the email, builds the code, and then shows you before anything actually goes out.

</details>

### 神经形态架构：分层记忆、日夜交替与伦理规约

从技术架构的底层来看，Eira 是一套极其扎实的生产级技术栈，而非依靠临时拼凑的演示 Demo。它通过一个统一的协议（Protocol）向外暴露了 213 个工具接口，并融合了向量数据库、关系图谱数据库以及传统的客户关系管理系统（CRM），同时根据不同的细分任务灵活调用三家主流大模型厂商的 API 服务。为了解决大语言模型普遍存在的“金鱼般短暂记忆”与易产生幻觉的行业痛点，Machinecraft 在系统内设计了精密的**分层记忆架构**：
1. **工作记忆 (Working Memory)**: 临时存储过去数分钟内的对话上下文。
2. **固定事实 (Pinned Facts)**: 静态保存关于客户身份与背景的核心事实。
3. **情节记忆 (Episodes)**: 将完整的历史对话打包提炼为简短的故事线。
4. **情感关联 (Relationships with Warmth)**: 模拟人际交往中信任感由弱变强的渐进过程。
5. **重要性网关 (Salience Gate)**: 沟通现实信息流，过滤掉无价值的垃圾信息，防止系统内存过载。当不同的事实产生冲突时，系统默认人类最新的修正具有最高优先级。

在此基础上，Eira 还拥有专属的**夜间梦境循环**（Nightly Dream Cycle）机制。每天夜间，系统会自动重放白天的所有业务记录，提炼并锁入有用的信息，排查和清理相互矛盾的数据，淘汰过时的无用信息，并将日间的工作成果固化为可复用的技能。次日清晨，系统会为管理者呈递一份详细的“梦境报告”，阐明夜间整合了哪些知识、抛弃了哪些垃圾、以及在人类入睡期间自主理清了哪些逻辑。这使得 Eira 能够在物理层面上实现“一夜之间变得更聪明”。

在系统底层注入灵魂的是其独特的“良知文件”（Soul File）。这份文件并非源自市面上常规的“友好与无害”安全对齐，而是基于 Machinecraft 家族三代传承的**耆那教**（Jainism: 强调非暴力、真诚与多面性）商业哲学所转化的五条工程铁律：
* **无单一绝对真理**: 任何单一信息源均不代表完整事实，必须经过交叉核验（Cross-check）方可输出。
* **杜绝绝对化表达**: 禁止使用过于绝对的陈述，输出时必须明确引用（Cite）具体的文档源与日期。
* **各司其职**: 智能体必须严格限制在自身的职责范围内，不得跨界干预其他代理的工作。
* **直面丑陋的真相**: 系统必须如实反映客观事实，即便是对企业不利的负面信息也不得隐瞒。
* **禁止单兵作战**: 没有任何一个代理可以独立决策，所有结论必须通过团队协同产出。

在资金投入方面，这种以知识库和多智能体协作为核心的路径，展现出了极高的性价比。在开发之初，外部技术代理机构曾给出了高达 23 万美元的开发报价，但 Machinecraft 最终仅依靠内部约 3 万美元的硬件与研发成本便完成了搭建，且后续的运行费用仅为每月数千美元。为了让更多传统企业能够摆脱对单一服务商的依赖，团队将这一整套“空神经系统”架构进行了开源，命名为 **Brain OS**（开源地址为 [forkmybrain.org](https://forkmybrain.org)）。这套系统不包含任何私有数据，但保留了智能体骨架、分层记忆、梦境循环以及伦理规约的底层框架，旨在帮助全球的制造与实体企业能够将自身的“商业真实”灌注其中，培育出属于自己的、能够永久记忆的企业大脑。

<details>
<summary>Original English</summary>

Under the hood, it's genuinely a real stack. Not a demo held together with duct tape. Databases for vectors, for relationship graph, for the CRM. Three different model providers, each picked for the job it's actually best for. Tools for Google, for swallowing documents, for every communication channel, plus monitoring. So, we can see what it's thinking. All of it, every capability exposed as 213 tools over one protocol. And the golden rule, the one we never break, Eira drafts, human sends.

Now, memory. And this is the part where most AI quietly lies to you, because a raw language model is basically a goldfish. Brilliant for about 30 seconds, and then you close the tab and forgets you ever existed. So, we engineered memory on purpose, in layers. Working memory for the last few minutes. Pinned facts about someone who who is. Episodes, whole conversations as little stories. Relationships with warmth that grows from stranger to trusted. And a bouncer at the door. A salience gate that decides what's even worth remembering, so the brain doesn't fill up with junk. When two facts disagree, corrections win. Continuity without making things up.

And then, I genuinely love this part. At night, it dreams. Every night, Eira runs a sleep cycle. It replays the day, locks in useful stuff, hunts for contradictions, gently forgets the stale junk, and turns the day's work into reusable skills. In the morning, there's a little dream report waiting for me to read. Here's what I consolidated. Here's what I let go of. Here's what I figured out while you were asleep. The thing literally gets smarter overnight.

And here's the part I care about the most. Every agent has a conscience. And it is emphatically not to be helpful, be harmless. It's a soul file written from the principles of a Jain family business that's been doing this for the last three generations. Five old ideas turn into engineering rules. No single source has the whole truth. So, cross-check before you speak. Never say things absolutely. Cite the document and the date. Do your own job, not someone else's. Report the truth even when the truth is ugly. And nobody works alone. Ancient philosophy running as guardrails in production.

Now, let's talk money. Because this is the part that should make the whole industry a little uncomfortable. There was no training bill. Zero. The expensive part was never compute. It was teaching a company to remember itself. An agency quoted us 230 grand to build this. We built it for around 30. That's cheaper than a nice watch. And it runs on a couple of thousand dollars a month.

So, here's the move. We pulled the whole architecture out and made it forkable. We call it Brain OS. It ships as an empty nervous system. The agents, the memory, the dream cycle, the soul file. All there, completely blank. You pour your own company's truth into it and from inside out. Because here's the thing nobody can outsource for you. Only you can build your company's brain. We are a 100 people factory with no data scientists. If we can grow a brain, you can too. We are not selling ours to you. We are helping you build your own. forkmybrain.org. Go build something that remembers. Thank you.

</details>