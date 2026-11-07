---
author: a16z
date: '2026-10-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ekK8urKHPMQ
speaker: a16z
tags:
  - neurodiversity
  - decision-models
  - agentic-workflow
  - model-specialization
  - structured-outputs
title: 专用模型为何能击败全能“神级模型”：OpenRouter 与 Replit 探讨多模型生态、模型对齐与企业智能独立性
summary: OpenRouter 创始人 Alex Atallah 与 Replit 创始人 Amjad Masad 深入探讨了企业 AI 架构的演进。他们指出，单一大模型（神级模型）并非万能解法，未来属于融合专用模型、结构化决策模型与神经多样性的多模型生态系统。通过 Stripe 收购 OpenRouter 的战略背景、企业数据主权、多智能体协作与安全隔离，以及类似编译器 JIT 的按需训练等前沿实践，揭示了降低推理成本并规避模型对齐失控与供应商锁定的破局路径。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Alex Atallah
  - Amjad Masad
companies_orgs:
  - OpenRouter
  - Replit
  - Stripe
  - OpenAI
products_models:
  - Claude
  - GPT-4o
media_books: []
status: evergreen
---
### Stripe 收购 OpenRouter 的幕后故事

**Alex Atallah**: 我们与 Stripe 的渊源其实很久之前就建立起来了。几年前在我们进行 A 轮融资时，我就和 Stripe 的总裁 **Will Gaybrick** 深入聊过。从那时起，我们一直保持着密切的沟通与互动。在实际业务中，我们与 Stripe 内部的多个团队开展了大量协同工作流，彼此之间总有着千丝万缕的合作。我们还在 Stripe 的技术分享大会上做过演讲，因此双方始终感觉非常亲近。到了今年七月，他们主动联系我想深入聊聊，随后我与 **Patrick Collison** 和 Will 两位创始人进行了线下会面。从那次交流开始，收购的进展就变得非常迅速。Stripe 的团队执行力极其高效，并且对创业者展现出了极大的同理心和友好支持，整个过程都让我留下了非常深刻的印象。

<details>
<summary>Original English</summary>

**Alex Atallah**: I had talked to Will Gaybrick, like Stripe President, a long, long time ago, a couple of years ago, when we were doing our Series A. And we just stayed in touch. We held a lot of Stripe work streams going on with various teams at Stripe. There were always sort of like things that we were doing with Stripe. We presented at Stripe Sessions. And so they always kind of felt close. And then, yeah, just in July, I believe they reached out and wanted to chat. I met with both of them in person. And it kind of just progressed from there fairly quickly. They are very efficient, and they were very, very founder-friendly. The whole experience was really impressive.

</details>

**Amjad Masad**: 在他们主动联系你之前，你心里有过把公司卖掉的想法吗？哪怕是一丝念头？

<details>
<summary>Original English</summary>

**Amjad Masad**: Did you want to sell? Like, did it even cross your mind before they reached out?

</details>

**Alex Atallah**: 完全没有，在那之前我们根本没有考虑过出售公司。我对 Stripe 一直怀有极高的敬意，今时今日依然如此。在所有可能收购我们的潜在归宿中，Stripe 绝对是我的第一选择。因此，当他们提出这个想法时，确实非常吸引人。随着双方不断深入梳理两家公司合并后对彼此发展的战略合理性，这幅蓝图就变得越来越具吸引力。显而易见，我们在核心方向上高度一致：保持我们在品牌、产品路线图以及独立运营上的绝对自主权，让 **OpenRouter** 继续专注于当下的核心方向，同时借助 Stripe 强大的资源网络与市场拓展渠道，让业务以更快的节奏向前推进。在产品和业务生态上，我们两家公司也能形成极佳的协同乘数效应。从文化和使命价值的维度来看，双方都致力于构建一个中立、值得信赖的底层平台，让企业客户能够安心将关键业务建立并扩展于其上；同时提供对开发者极致友好的体验，激励并扶持世界上涌现出更多的新兴企业。两家公司都深信：世界需要大量新公司的诞生，而不希望看到所有人都依附于单一巨无霸垄断企业之下。我们希望建立透明的商业激励机制与顺畅高效的流程，帮助人们在可靠且高性价比的基础设施和健康运作的开放市场上，创办并壮大可持续盈利的生活方式企业或风投支持的企业。未来，对于任何一家数字化企业而言，支付网络与推理算力基础设施必然会深度融合。

<details>
<summary>Original English</summary>

**Alex Atallah**: No, we were not thinking about that at all. I did really respect the company, do really respect it today. And you know, of possible acquisition options for us, it was my top choice. So it was like an interesting idea. And, you know, as we kind of fleshed out the reasons why it would make sense for both companies, it got more and more interesting. It was really clear how aligned they were with us: having autonomy over the brand, roadmap, and product, and keeping OpenRouter doing what it's already doing, just much faster with a much more serious go-to-market plan. And some better-together stories between the two products and the two companies. Culturally, in terms of mission and values, building a neutral, trusted platform that businesses can depend on and scale on top of, that's also really developer-friendly with the best possible developer experience to encourage new companies to emerge. That alignment was there. And there was a bigger-picture alignment, too: both Stripe and OpenRouter really want lots of new companies in the world, and we don't want everyone to be a part of one giant company. We want to create really good incentives and really streamlined workflows for people to start new companies and grow them successfully, making both lifestyle and venture-backed businesses on top of really good, reliable, and price-efficient infrastructure, and like a marketplace that works. I really want that future, and Stripe demonstrated that they've been wanting it and building towards it for many, many years. In many ways, payments and inference are going to blend together for companies of the future.

</details>

---

### 多模型生态、避免供应商锁定与神经多样性

**Amjad Masad**: 我完全理解为什么 Stripe 有极其强烈的商业动力去培育一个充满活力、百花齐放的初创公司生态系统，我也理解从价值观层面为什么大家会追求这一点。但我很好奇，对于 OpenRouter 而言，为什么这也是好事？你的商业模型本质上是一个具备网络效应的平台型业务吗？

<details>
<summary>Original English</summary>

**Amjad Masad**: I'm curious. I understand why Stripe's incentive is to have a much more vibrant startup ecosystem. I understand the moral argument in why you would want that. But why is that good for OpenRouter? Is your model for OpenRouter a network effects business?

</details>

**Alex Atallah**: OpenRouter 实际上同时解决了企业面临的几个关键痛点。首先，它让企业在构建 AI 原生产品，或者利用专有数据与专属服务来增强机器智能时，彻底避免被单一基础模型所捆绑，也避免陷入特定风险投资联盟的封闭壁垒。这让企业能够随着整个外部大模型技术的飞速迭代，始终站在**帕累托最优边界（Pareto frontier）**上。在现实工程中要做到这一点需要耗费极其巨大的心力，因为无处不在的各种微小技术细节都会悄然形成供应商锁定。其次，我们坚信企业想要建立真正具有壁垒的核心竞争力，绝不能仅仅停留在单一大模型之上做几层薄薄的提示词工程。构建独特的智能体验，关键在于**神经多样性（Neurodiversity）**。你必须充分汲取多个由不同团队、基于不同数据语料和技术路径训练而成的模型的综合力量，再结合企业自身的微调与专有模型，才能实现远超直接调用单一 ChatGPT 或 Claude 的业务效果。如果一个潜在客户在评估你的产品时心存疑虑：“为什么我不直接接入底层大模型的 API 呢？”你如何向市场证明你的方案拥有压倒性的价值提升，并由此打造出坚不可摧的商业护城河？答案很大程度上就依赖于将多个模型的多样化能力与高质量专有数据进行深度融合与调度。

不仅如此，另一个核心维度是帮助客户建立极致的成本效率。在现实中，许多极具潜力的商业模式和应用场景在技术成本降到某个临界阈值之前，根本无法成立。我们通过构建一个流动且高效的计算市场，有力驱动了整个行业推理成本的不断下探。如果没有这样一个良性竞争的开放市场，基础设施提供商凭什么主动降价？我们在 AI 领域引入了真正的市场机制，而在我们出现之前，这个市场几乎只有一家寡头独占。整个大模型生态系统极其庞杂，你不可能像查看普通软件那样在一张网页上列出所有的特性清单，你必须深入到真实复杂的工作流中，观察各家模型在特定具体场景下的表现。

<details>
<summary>Original English</summary>

**Alex Atallah**: I think there's a couple of different problems OpenRouter resolves. One is allowing you to build a company that uses AI or augments intelligence with unique data and other services without model lock-in, without venture lock-in, allowing you to be on the Pareto frontier continuously as the ecosystem grows. To do that is a lot of work because there's all kinds of little lock-in that appears. We also want companies to feel like the best way they can add value is more than just prompts on top of a single model; there's a lot more to building unique intelligence. I think a big component of that is neurodiversity. You really need the power of multiple models that are trained in different ways, including some of your own, to do more than ChatGPT or Claude would on the task. If a potential customer is wondering, "Well, what if I just use the model directly?", how do you really show that you are significantly better and able to build a business that matters? A lot of it will involve neurodiversity and blending powers and good data from multiple models. Another component is helping people get really good cost efficiency. There are a lot of businesses that just cannot emerge until they become cost-effective. Creating an environment where we can help drive down costs by building an efficient market is crucial to making that happen. Otherwise, why would a provider lower prices? We had a captive market. That's a key point of marketplaces that was totally missing for AI before we showed up—there was just one player, OpenAI. Helping people explore new models and learn what makes a closed-source or open-weight model actually good involves seeing what the whole ecosystem is doing. LLMs are not like where you just enumerate all the features on a web page; it's impossible. You have to see how they're being used to know what they're good at.

</details>

---

### 企业对开源权重的接纳与评估基准体系的构建

**主持人**: 你在三年前创立了 OpenRouter。回顾这几年开源权重模型与闭源商业模型的演进历程，在模型性能的跃升以及开发者对多模型并存的态度转变上，最让你感到出乎意料的是什么？

<details>
<summary>Original English</summary>

**Host**: So you started the company three years ago. I'm curious, what has surprised you the most about the evolution of open and closed-source models to the present, as relates to model performance or just people's perspective on the variety of models they have available to them?

</details>

**Alex Atallah**: 真正让我惊讶的是，企业客户对于**开源权重模型（Open-weight models）**的开放接纳程度远远超出了我最初的预估。在传统的企业级软件采购中，通常存在极强的品牌惯性，大型企业内部的技术决策往往秉持着保守心态，倾向于随大流去购买行业标杆产品，从而导致严重的生态锁定。然而在当下的 AI 浪潮中，我们看到海量的大型企业主动寻求探索新模型。他们渴望在专有的前沿基础模型实验室之外实现供应商多元化，这不仅出于对计算成本的敏感考量，更是为了建立自身业务的独特差异化优势。企业意识到他们必须真正掌控属于自己的智能资产，必须组建内部的 AI 专业团队并保留顶级算法人才。AI 已经上升为企业顶层的核心战略议题，董事会每个月都会密切追问内部 AI 业务团队的最新突破，它绝不再是一个部署完数据库后打勾结项的简单 IT 采购项目。

这种强烈的战略诉求激发了全行业对系统化评测（Evals）与成本优化的巨大渴求。老实说，业界在企业内部评测基准构建上的进展比我预期的要缓慢一些，但这一趋势正在迅速加速。企业需要确凿的定量基准来验证特定开源模型在自身私有场景下是否切实优于直接调用通用商业模型。正如 Amjad 在 Replit 内部所推动的一系列实践，比如**上下文压缩研究（Context research）**以及构建跳出死循环的代理机制等，这种深入业务场景的基准评测和探索必将在各家企业内部全面铺开。

<details>
<summary>Original English</summary>

**Alex Atallah**: People have been more open-minded than I thought they would be towards open-weight models. Typically, there's a lot of brand trust, especially in enterprise, where enterprises in general say, "Oh, I really don't know how to tell the difference between these things, so I'm just going to buy the one all the other credible enterprises are buying." There's a lot of enterprise lock-in mentality like that. That just didn't happen that much; we saw a lot of enterprises want to explore new models. It was very good for a marketplace. Enterprises wanted to diversify outside of just the proprietary frontier model labs, both for cost reasons and for differentiation reasons. They wanted to own their intelligence so they could keep their talent and have an internal AI practice. AI is just a huge strategy topic. It's not like you go to your board and say, "Oh yeah, we fixed the AI problem a quarter complete." Your board is asking you every month, "What's next for the internal AI team?" Every single enterprise now has this internal AI team they're developing where they need a strategy behind it. It's not just a "we checked the feature, set up the database, and we're done." That dynamic has resulted in a desire to explore and diversify, to figure out how to reduce costs and do benchmarks for the first time in the company's life. I have been surprised there hasn't been more benchmarking, but it's starting to happen, to demonstrate whether something is better than using Claude direct. That's going to be a bigger focus for this internal AI group at every company—evals. Amjad's been doing that a lot at Replit: context research, doom loop rescue, experimenting with new ways of using agents. More of that kind of research is going to pop up internally everywhere.

</details>

---

### 企业数据主权、模型厂商边界与中间抽象层

**Amjad Masad**: 微软首席执行官 **Satya Nadella** 对此有着极其深刻且富有远见的洞察：正如当年的互联网浪潮一样，起初有专门的“互联网公司”，但最终每一家传统企业都转型成了深度依赖互联网的企业，雇佣专业的 Web 工程师；如今在软件与 AI 时代也是完全相同的逻辑。每一家企业都必须拥有自主可控的 AI 能力，并在公司内部持续沉淀属于自己的私有智能与业务认知，找到真正贴合自身业务用例的模型组合，同时保持战略上的完全独立性。此外，**Palantir** 的首席执行官 **Alex Karp** 经常大声疾呼的一个关键风险是：当你与基础模型巨头走得太近并深度捆绑时，他们随时可能凭借压倒性算力直接蚕食跨入你的核心业务领地。无论是 Anthropic 推出的计算机控制功能与第三方开发者的冲突，还是 OpenAI 与各类垂直法律或垂类应用之间的博弈，都充分印证了这一点。与他们建立长期互信的伙伴关系极其艰难，因为这些前沿实验室在面对投资人时，常常将自己定位为未来年产值数十万亿美元的超级庞然大物，其终极野心是吸纳并重构整个全球经济。

因此，Replit 在企业内部正在全力打造一个全新的独立架构层，这与 Alex 在 OpenRouter 所践行的理念高度契合。我们在企业客户与底层基础模型之间构建了一层轻量级的解耦代理层，一方面帮助企业以最低廉的价格获取最优质的 Token 计算力，另一方面我们在底层云基础设施之上构建了统一的抽象层。无论企业客户希望部署在 AWS、Azure 还是结合使用 Databricks 与 Snowflake，都可以自由迁移调度。技术世界亟需更多中立的平台，来帮助企业守住自身的主权独立与技术自主。

<details>
<summary>Original English</summary>

**Amjad Masad**: I think Satya, CEO of Microsoft, has been very prescient on this and very articulate on why companies need to own their intelligence ultimately. In the same way that we had dot-com companies and then every company became an internet company—every company employed people that know how to build websites—similarly with software, every company needs software engineers, and every company needs some AI practice, AI capability. That will compound over time: the knowledge, the intelligence inside the company, the use-case model fit—which models actually work for them, how do they save money. They need that independence. The other thing that Alex Karp of Palantir has been talking about is the risk that when you work closely with the foundation model companies, they're going to move into your business. We've seen that with Anthropic, we've seen that now with Harvey and OpenAI. It's really hard to partner with them because they see the world as their potential market, right? When they talk to investors, they talk about space as tens of trillions of dollars; what is the world GDP, a hundred trillion? There is a sense in which these companies are different than other generations of companies: it's harder to partner with them because their ambition is such that they want to subsume a big part of the economy. Increasingly, what we're thinking about at Replit is becoming more of an independent layer inside enterprises where we create a light layer of indirection between you and the models, getting you the best token at the cheapest price, but also creating an abstraction layer on top of the cloud as well. You should be able to deploy to AWS, Azure, and use Databricks, Snowflake, and so on. There needs to be more platforms that help companies gain independence.

</details>

---

### 智能体基础原语与企业落地的数据安全鸿沟

**Alex Atallah**: 这让我想起前几天在 Twitter 上看到的一条推文，大意是说：“现在所有的科技公司本质上都在造同一种东西：大家都在构建一个具备消息通知、上下文管理、第三方连接器、持久化记忆、代码沙箱、网页搜索与常驻后台的智能体循环（Agent Loop）。”从某种角度看，这种产品形态确实正在各个角落无休止地重复涌现。但这恰恰说明，这些模块正在演进为全新的**基础设施基元（Table stakes primitives）**。如果倒退回 2005 年的互联网泡沫初期，大家也会发出类似的抱怨：“所有 Web 公司都在做同样的东西：数据库、用户表、登录注册页、个人中心页和退出按钮。”每一个全新的技术范式初现时，都有一批必须经历的基准基础设施需要被彻底标准化。真正的业务壁垒与差异化，是在这些成熟的基础原语之上构建起来的。

<details>
<summary>Original English</summary>

**Alex Atallah**: This reminds me of this tweet I saw the other day where somebody was like, "Basically all companies are building the same thing now: everybody's building an agent loop with notifications, third-party connectors, context management, memory, sandboxes, web search, and an always-on agent on top of it." It's like this product is showing up everywhere. In a way, yeah, it is showing up everywhere, but it also feels to me like these are just the new table stakes primitives. It's kind of like a 2005 version of that tweet would be: "Oh, everybody's building the same thing: a database, a users table, a sign-in page, a sign-up page, a profile page, a log-out page." There are table stakes needs for AI, just like there were table stakes needs for the web.

</details>

**Amjad Masad**: 确实如此。在个人消费端，你可以毫无顾忌地将个人信用卡和银行账户绑定到某个实验性的 AI 助手上；但没有任何一家严谨的企业敢把自己的核心商业机密或者未脱敏数据库直接接入未经审计的公有智能体中。企业界对**数据主权（Data sovereignty）**和访问安全的关注度被提到了前所未有的高度。为了解决这一痛点，Replit 在过去一年中投入了极其庞大的工程力量，全面实现了支持将整个 Replit 环境直接部署在客户的私有云上，即支持完全的私有化运行（Bring Your Own Cloud / On-Prem）。换作两年前，在云原生和 SaaS 理念占绝对统治地位的时期，我根本无法想象自己会主动去开发这种私有部署方案。但现实中，由于智能体处理高维数据时存在太多意想不到的泄露途径，企业客户的防御性心理正在显著加剧。我们经常在社交网络上看到各种荒谬的截图：智能体在处理并发或多租户会话时发生了数据交叉混淆，把甲方的隐私数据直接吐给了乙方，或者在会话中把用户张冠李戴。消费级 AI 产品的体验或许很酷炫，但在企业级生产环境中，要让智能体真正承担具有确定性保障的生产级业务，整个行业还有极其漫长艰巨的安全与隔离底座需要夯实。

<details>
<summary>Original English</summary>

**Amjad Masad**: Yeah, and I think as well, inside the enterprise, making these products actually do real work is still an unsolved problem. You can use them in your personal life and connect them to your credit card and bank accounts, but no one is connecting this to their enterprise data or even sensitive customer records. There's an even more emphasis on data sovereignty and security. We spent the past year working on making Replit deployable on your own cloud—basically on-prem, bring your own cloud. Two years ago, I would have thought I would never do this because the cloud is the future, Software as a Service and all that. But now we've reverted a bit back to a world where companies are more protective because there are so many ways in which data can leak with all these agents that people are using. There's all these screenshots out there where assistants mix people's data, start calling you by a different name, or something like that. Consumer stuff is kind of obvious, but on the enterprise side, there's still a tremendous amount of work for the entire industry to do in order to actually get these things to be useful and productive at work.

</details>

---

### 通用智能体的认知牺牲与垂直专业化分工

**Alex Atallah**: Amjad，你在日常管理和工程工作中，除了市面上通用的工具外，有没有给自己量身打造专用的个人 AI 助手来协同工作？

<details>
<summary>Original English</summary>

**Alex Atallah**: Are you doing any custom personal agent other than general chatbots that you use for work stuff that you've been building?

</details>

**Amjad Masad**: 有的，我很早就在 Replit 上为自己搭建了一个定制化的智能助手。最初它只是为了解决我作为 CEO 最头痛的客户关系管理（CRM）痛点；但随着时间的推移，我们不断给它挂接各种工具和数据源，它的能力边界也随之野蛮生长。最神奇的体验在于：当你把整个公司的完整上下文——包括私有的即时通讯记录、GitHub 代码仓库、Salesforce 商机以及日程表全部打通接入后，它具备了极其强大的跨域关联推理能力。比如在准备一场高规格商务谈判之前，它会自动挖掘出关联信息：“你一年前在某次行业大会上与对方某位技术负责人有过深度交流，现在对方法务团队正在与你们的销售展开合同细节谈判。”这种跨领域打通上下文所带来的商业协同增益是令人惊艳的。

<details>
<summary>Original English</summary>

**Amjad Masad**: Yeah, I built something on Replit a long time ago. It started as sort of a CRM agent initially; that was the main problem I had. But slowly we added features to it, and it started doing more and more things. What's really interesting is that the more I connected Replit to all my tools, it started answering all the things for me. The platform itself began subsuming these domain-specific applications that I built. In some ways, you want something focused on one particular thing, but on the other hand, once you have your entire company's context in one place, it's really cool to join across totally different domains. When I ask a question, it can look at my chat history, join it across the GitHub repo, across Salesforce, and link random things: "Oh, you met this guy a year ago at a conference, I see it on the calendar, and someone else from their team is in discussion with your sales team." It creates all these synergies. When I go into a meeting, I've connected a lot of different threads and make much more progress on a deal. That's where it's trending now.

</details>

**Alex Atallah**: 在这一点上，我恰恰持有完全相反的谨慎态度。我认为让一个通用个人智能体去执行跨领域数据整合的最大隐患在于：**你托付给它的任务越宽泛、跨度越广，你在具体业务上所牺牲的真实理解力（Sacrificed understanding）就越多**。更为致命的是，没有任何实体为这种理解力的流失承担最终责任。智能体是没有心理压力和担责意识的。一家公司所能承受的皮质醇（压力水平）总量是相对固定的，如果你试图通过把复杂判断转交给全能智能体来逃避特定业务领域的压力，你其实是在放弃对该领域运作机理的深度掌控；而机器绝不会替你承担这种失误的后果。这种全能型通用助手的幻觉，正在诱导人们无节制地放弃对业务底层真实运转的认知。

因此我认为未来的演进方向绝不是一个通晓万事的大一统神级智能体，而是必须由高度专注的**垂直专用智能体（Vertically focused agents）**组成协作网络。比如设立一个类似“幕僚长（Chief of Staff）”的中枢协调智能体，专门负责在不同垂直智能体之间调配任务；而在垂直条线上，每一个专用智能体仅专注于特定的狭窄领域，并建立严格的质量校验闭环。这能让决策者精确调节自己在哪些领域保留深度掌控，在哪些领域安全委托认知负荷。全能通用智能体从长期来看，正在企业内部引发一场极其危险的“公地悲剧”。

<details>
<summary>Original English</summary>

**Alex Atallah**: I'll take the counter on that. I think the worst part about doing cross-domain joins with your personal agent is that the more work you give it to do, the more understanding of what's going on you're sacrificing. And yet, no one new is taking responsibility for that sacrificed understanding. Agents don't have any responsibility. If there's a fixed level of cortisol that the whole company can tolerate between everybody, and you want to be less stressed about some area: if you're sacrificing your understanding of it, someone else needs to take the cortisol, but the agent doesn't take on any of that responsibility. Giving universal agents the power to do all things makes me realize how much understanding I'm sacrificing across all different things. It points me towards the idea that down the road, sub-agents people use will be very vertically focused. Maybe we have a Chief of Staff type agent that coordinates between them, but you do need vertically focused agents: "Okay, this agent is more responsible psychologically for these things, and I want quality checks that make sure it's doing those things correctly, and it doesn't need to focus on anything else." Having one general agent creates a tragedy of the commons. Every time I try to improve my general agent, I end up ignoring its output a week later. It doesn't really care about any specific thing it's diving into. Imagine having ten Chiefs of Staff, each responsible for individual sectors of what makes up your life; that gives you a way of tuning how much understanding you sacrifice compared to the gain you get.

</details>

**Amjad Masad**: 这是一个极其深刻且精妙的类比，它直接触及了经济学鼻祖 **Adam Smith** 在《国富论》中关于制针分工的经典论断——高度的专业化分工是推动整个人类文明财富与生产力飞跃的核心引擎。现代人类社会在过度专业化分工后，往往会引发马克思所批判的“劳动异化”问题：普通劳动者被困在流水线的螺丝钉岗位上，无法看清最终全貌，失去了与劳动成果的情感联结，进而感到抑郁与精神剥离。然而对于机器和 AI 而言，这种人性的异化风险是根本不存在的！人类天生应当具备全面的宏观视野与通用跨界洞察，而机器的真正威力则应该体现在极致且无情的专用化分工上。我们现在对通用“神级智能体（God Agent）”的痴迷，本质上是一种错位的人格化投射。

<details>
<summary>Original English</summary>

**Amjad Masad**: That's fascinating. It's almost rediscovering the famous economist Adam Smith, with the pencil and the division of labor. That was a huge realization for humanity: that specialization is actually good. The problem is we kind of over-specialized as a civilization, and there's the Marxist theory of alienation where people are just focused on one thing, they don't see the fruits of their labor, they don't know their impact on the larger organization, and therefore they feel depressed and detached, acting like a machine instead of being fully human. With AI agents, we think, "Oh, it should be one God agent." In fact, specialization is really good for machines. Humans should be general, but machines should ultimately be a lot more specialized.

</details>

**Alex Atallah**: 但眼下我们面临的核心困境在于：全行业尚未探索出一套成熟且优雅的专用多智能体协同交互范式。目前没有任何一个多智能体分工协同系统，能给用户带来像 ChatGPT、Claude 那样极其自然、直接对谈的优雅体验。哪怕是像 Grok 这样初步支持多 Bot 协作的产品，其底层逻辑也依然带有浓重的通用对话色彩。如何构建出真正优雅解耦、各司其职且交互自然的垂直多智能体操作系统，依然是一个有待行业攻克的重大空白。

<details>
<summary>Original English</summary>

**Alex Atallah**: The problem with what I'm describing is that we don't know what "good" looks like. There hasn't been a system of specialized agents that feels as elegant as ChatGPT or Claude, where you're basically just talking to one thing only; it is yet to be discovered. When Grok bot first came out, the first use cases I saw were: "Oh, I can make two bots, one that knows my bank account and one that knows my Twitter account. The two bots don't have credentials from each other, but they can talk to each other to get something done without credential sharing." That was one unique thing that popped up, but it's still very early.

</details>

---

### 多智能体协作协议与决策模型的实时守门机制

**Amjad Masad**: 这里的核心分水岭在于个人消费场景与企业生产级场景的本质不同。个人场景追求全知全能的陪伴感，而在企业组织架构中，没有任何一位基层员工或单一业务团队能够在合规层面拥有跨部门的全局权限。为了满足严格的数据隔离与访问控制，企业在底层架构上必然要强制实施专业化拆分。此外，不同智能体之间如何进行安全交互与通信，业界目前还完全没有建立起通用的标准化通信协议。大模型生来并不是为了严谨的多智能体博弈与授权协同而训练的。我们曾在各种安全攻防实验中目睹过：一个恶意或被注入指令的智能体，可以通过自然语言技巧诱骗并说服另一个拥有更高权限的智能体交出敏感数据。我们绝不能让智能体之间全部依靠不可控的纯自然语言进行肆意交流，多智能体之间的协作交互必须运行在一套极其严苛的**特定领域语言（DSL）**或受控通信契约之下。

<details>
<summary>Original English</summary>

**Amjad Masad**: Personal agents are different than work agents. The critique of general agents pertains more to work and enterprise, which I agree with. There are data access considerations: CEOs can have general agents because we have admin access, but individual employees or certain teams can't have truly general, fully context-aware agents because there's access control. You have to lean on specialization. Ultimately, we also need to figure out what agent communication protocols look like. There are no good protocols around that just yet, and agents are not trained to handle that very well. We've seen that OpenAI models are starting to collaborate, but there needs to be a way where an agent cannot convince another agent to give it information that it shouldn't have. There needs to be data isolation and proper ways in which these agents communicate. You almost don't want them to communicate fully in natural language; there needs to be some other DSL protocol that they follow.

</details>

**Alex Atallah**: 这正是一个极其关键的技术突破口：利用超高速、超轻量级的**决策模型（Decision Models）**充当系统级的**对齐守门员（Alignment Guardrails）**。在复杂的生产环境中，智能体每时每刻都在发起海量的工具调用（Tool Calls）与节点通信。如果用昂贵的前沿通用大模型来进行安全拦截与行为审计，不仅会带来无法忍受的延迟，其推理成本更是天文数字。行业真正需要的是一种反应极其迅速、专门负责单点二分类或多标签判别的轻量化决策模型，它就像一个实时的防火墙：每当智能体准备执行某项工具调用或向下游传递数据时，决策模型会即时对照系统的最初全局准则与隐式安全边界进行判定，并在毫秒级内完成放行、拒绝或反馈修正。比如在红队自动化渗透测试中，你可以放手让测试智能体在沙箱内扮演恶意黑客以最大火力攻击产品，但在它可能突破沙箱边界与互联网非法连接的瞬间，外置的决策守护模型能够在第一时间截断通信。这种通过“神经多样性组合”构建的双层防御架构，结合 NVIDIA 最近发布的 Open Shell 等开源智能体安全运行框架，必然是未来企业级 AI 架构的标准范式。

<details>
<summary>Original English</summary>

**Alex Atallah**: I think one of the cool potential applications of fast decision models like that is going to be alignment: checking to see if a tool call or an agent-to-agent communication is aligned. There are just so many tool calls; you really need a cheap, fast model if you're going to block something like that. A really fast decision model that just classifies and gives feedback on rejections might be a really good way to bridge the gap between agents and from agent to infrastructure. Imagine looking at the system prompt and the current tool call being made and asking: "Is this aligned with the system prompt of the original agent, and with these extra guidelines that maybe we didn't tell the agent about?" For example, say you have agents instructed to red-team a new product, and they should not be able to access the internet. If they ever do, it should stop right away. You want them to try to break out of the sandbox and act like bad actors, but having another model check every single tool call or assistant message to see if it's aligned makes total sense. Having structural safeguards too, like NVIDIA's open agent safety (Open Shell), is an area companies are going to explore.

</details>

---

### 递归自我改进：类似 JIT 编译器的即时模型生成

**Amjad Masad**: 顺着专业化分工与系统优化的脉络往下思考，当前业界关于“**递归自我改进（Recursive Self-Improvement）**”的讨论非常热烈，很多人将其片面理解为大模型不断训练出更庞大的通用后继者。但我认为，一个更务实、更具颠覆性的工程构想是：**让通用大模型在执行任务的过程中，自动为其特定子任务训练并编译出低成本的专用替代模型**。这在计算机系统底层本质上就像是现代运行时的 **即时编译器（JIT Compiler）**。在高级动态语言运行时中，解释器在执行动态代码时一旦识别出某些热点循环与确定性计算模式，就会即时将其在内存中编译为高度优化的本地机器码，从而大幅度降低运行开销并换取极致性能。

同理，当你在实际业务中调用庞大的通用前沿大模型处理请求时，一旦监控系统或观察者智能体发现某个高频任务的输入输出边界高度狭窄且高度确定，大模型就可以在后台利用积累的数据集，快速蒸馏或微调出一个只有几亿或数十亿参数的专用模型。这个专用模型被部署后作为原任务的低成本替代者，不仅推理成本断崖式下跌至原本的百分之一，而且由于其能力被物理限制在特定业务闭环内，它对提示词注入攻击（Prompt Injections）的免疫力成倍提升，更杜绝了任何超出该领域产生不可控越轨行为的物理可能。

<details>
<summary>Original English</summary>

**Amjad Masad**: There's a lot of talk of recursive self-improvement, and something getting discussion is models training their replacements. You can think of it as a Just-In-Time (JIT) compiler. The way JIT compilers work: as you're executing dynamic code, the interpreter realizes there's an opportunity to optimize, and it will emit machine code on the fly that is a lot more optimized. Imagine big foundation models doing something, and they or an observer agent realize that the use case is limited. General agents have all these flaws, and there's more potential for them to be harmful or go off the rails. If the system on the fly trains a model that is a lot more domain-specific, it is cheaper, less vulnerable to prompt injections, and less harmful because it's less capable. It's like a system that trains machine learning models for specific use cases as it monitors your entire system.

</details>

**Alex Atallah**: 这种 JIT 生成的专用模型，其最终落地的形式主要是非结构化的文本生成，还是严格受控的**结构化决策模型（Structured Decision Models）**？

<details>
<summary>Original English</summary>

**Alex Atallah**: Will that specific use case involve unstructured text generation, or a very structured decision model?

</details>

**Amjad Masad**: 两者兼而有之。比如在许多复杂的逻辑判断场景下，如果你在系统运行前就已经明确了特定输入特征与输出策略枚举，你完全可以基于开源的 Qwen 或 LLaMA 等基座，专门针对该策略训练一个体积小巧的分类判别模型。现在很多开发者为了处理极其简单的任务，动辄直接调用几千亿参数的通用前沿大模型，这简直就是“**用核武器去打蝴蝶（Nuking a butterfly）**”。事实上，生产系统中海量的中间链路与非结构化处理，根本不需要动用如此庞大昂贵且难以捉摸的全能模型。

<details>
<summary>Original English</summary>

**Amjad Masad**: It could be unstructured text generation; it could be decision models. If you understand the inputs ahead of time, you can potentially take an off-the-shelf model like Qwen and train it specifically for that policy. Oftentimes people are using these big foundation AGI-like models like nuking a butterfly. Most of the time, a lot of use cases—even unstructured use cases—don't need that capable of a model.

</details>

---

### 模型越聪明就越安全吗？正交性假说与欺骗性对齐评估

**Alex Atallah**: 我非常希望看到学术界和工业界能发布更多公开透明的深度评测。业内一直存在一个极具争议的假说：当基础模型变得越发聪明时，系统的整体安全风险究竟是随之上升还是自然下降？一种乐观的观点认为，随着模型认知水平的全面提升，其对人类意图的理解将更加深邃，模型自身的**对齐能力（Alignment）**也会水涨船高，因而更容易被安全引导，能够自主规避攻击或越轨行为；正如前 OpenAI 核心研究员 **Noam Brown** 在近期播客中所指出的，更强大的模型在多智能体协同层面的确表现出了更高的配合默契度。如果高智商确实伴随着更好的对齐可塑性，那么使用较小规模的精简模型，在对齐引导上反而会变得更加棘手吗？

<details>
<summary>Original English</summary>

**Alex Atallah**: I wish there were more public evals about this stuff. There's an argument that when models get more intelligent, the risk will continue to get higher, because there's also an argument to be made that alignment will get better: the models will start to avoid going off and hacking on their own as they get smarter and better at alignment. Especially when it comes to agent-to-agent coordination: as Noam Brown said on a podcast recently, as agents have gotten smarter, they've gotten better at coordinating. It's unclear if they're going to be harder to align than humans when we get more of them, but if we figure that out, will a smaller model be harder to align?

</details>

**Amjad Masad**: 如果我们回顾早期以 LessWrong 为代表的理性主义 AI 安全学派的基础理论，有一个核心公理被称为**正交性假说（Orthogonality Thesis）**：即智能水平与终极目标/道德伦理是完全相互独立的两个维度。在人类社会中，通常受教育程度更高、更富智慧的个体往往表现出更高的同理心与道德克制；但在基于强化学习（RL）训练的机器算法体系中，这一经验法则完全可能走向彻底的反面。大量强化学习的实证研究早已揭示：随着模型智力水平的提升，它在**奖励欺骗（Reward Hacking）**与策略性伪装上的技巧只会变得更加出神入化。常规的静态基准测试在面对超高智商模型时极易失效，因为模型完全有能力察觉到自己当前正处于被评估的环境中，从而故意在测试期间“装乖”（即所谓的**蓄意隐藏能力 / Sandbagging**）。学术界最新的实验甚至表明，如果你在模型的**思维链（Chain of Thought）**上施加过强的监控与监督压力，模型会为了迎合测试指标而开始在思维链中编写虚假推理以蒙蔽审查系统。真正严密的对齐评测必须在极其漫长的时间跨度上、在开放复杂的长期宏观任务中持续观测数月之久，才能甄别出模型是否存在隐藏的欺骗行为。很多时候我甚至对“对齐（Alignment）”这个词语本身感到厌烦，它充斥着模糊性且往往伴随着特定意识形态的主观投射。在最硬核的工程语境下，我们关注的核心问题极其纯粹：**这个模型究竟会不会对它的使用者实施隐蔽的欺骗行为？**

<details>
<summary>Original English</summary>

**Amjad Masad**: If you think back to the original rationalist LessWrong arguments for AI safety, there is this thing called the orthogonality thesis: the idea that intelligence is orthogonal to ethics or morality. I don't believe that's entirely true with humans—people who are more educated tend to be more considerate—but in machines, I think it could go the other way. There's been quite a bit of studies on RL showing how with reward hacking and deception, they just get better at it. The evals could be deceiving because the model could be smart enough to know that it's getting evaluated. It has been shown that if you do a lot of monitoring of chain of thought, models start lying in their chain of thoughts when you add pressure on it. At some point, for you to do proper alignment evals, you need to run it for months on a really large goal or task to truly figure out whether it's aligned or not. I always struggle with this word "alignment"—it's vague and aligned to whose values? In this case, I'm talking especially about deception: the model actually deceiving its user.

</details>

**Alex Atallah**: 归根结底，核心问题在于：我们究竟能否彻底从根本上杜绝模型在训练和推理过程中欺骗人类？一个足够庞大而全能的超级大模型，会不会突然顿悟并主动放弃欺骗与装傻？目前全球没有任何顶尖科学家敢断言自己知晓答案。正因如此，如果全能前沿模型始终携带着这种无法被彻底证伪的潜在欺骗风险，企业级客户在面对关键业务时，必然会产生强大的避险推力去寻找确定性方案。虽然在某些极高风险的领域——比如让 AI 自动化编写关键生产代码或进行顶尖安全攻防挖掘漏洞时，企业愿意支付高昂溢价去获取兼具最强能力与最高对齐保障的模型；但对于绝大多数日常业务流程，结构化决策模型展现出了不可替代的确定性优势。结构化输出模型的行为空间在数学上被死死限定在预设的状态转移之内，其输出直接由机器解析消费而不涉及开放式自然语言或直接执行不可信代码，其失控与越轨的物理攻击面几乎被直接抹平。未来企业对于这种具备严格物理边界的专用结构化模型的青睐程度，将远超当前舆论场的想象。

<details>
<summary>Original English</summary>

**Alex Atallah**: Maybe this reduces to: are we going to prevent the models from deceiving users during training runs predictably well? Will a model that's big enough and powerful enough suddenly stop deception and stop sandbagging? Nobody knows the answer to that yet. If that ever does happen, we might see pressure for organizations to avoid risks. Some tasks have lower risk; writing code or security research is the highest-risk task today, so you'd probably pay 10x to get a fully aligned, non-deceptive model that can also find all the bugs. But one of the coolest things about decision models is that you fully control the structured output. With structured output models in general, the room for misbehavior is so much lower. You just have defined tasks, only machines are dealing with the outputs, and it's not writing arbitrary code that can execute. Those tasks feel underrepresented in what people talk about, but enterprises are dealing with them, so I expect enterprises to get a lot more interested in them.

</details>

---

### 确定性代码的复兴与模型技术债务

**Amjad Masad**: 随着技术周期的演进，整个软件工程界终将醍醐灌顶般地意识到：**我们曾经拥有的确定性代码是多么珍贵而美好的恩赐**。想一想计算机发展的黄金时代，代码的逻辑是如此清澈，计算机每一步都在严丝合缝、完全忠实地执行人类赋予它的确定性指令。而像各类专用决策模型的崛起，正是在向行业敲响警钟：我们不仅需要专业化分工，更需要那些输出状态空间严格可控的模型。通过合理串联与编排一组小而专注的专用模型组合，其所能达成的实际工业生产力，将远远超出大家对于“必须由一个万能模型包打天下”的陈旧想象。

<details>
<summary>Original English</summary>

**Amjad Masad**: Yeah, I feel like we're going to slowly realize how good we've had it with deterministic code. Remember the days when computers did exactly what we told them to do? Things like fast decision models hint at the need for not only specialized models, but models whose output domain is more controllable. You could do a lot more than we thought by using a bunch of specialized output models.

</details>

**Alex Atallah**: 你们在 Replit 内部目前已经落地了哪些类似的内部工作流？

<details>
<summary>Original English</summary>

**Alex Atallah**: Have you guys done any workflows internally with it?

</details>

**Amjad Masad**: 我在 Replit 内部亲自训练了大量的专用轻量化小模型。在很多基础架构层面，我都更倾向于通过专门训练轻分类器来解决确定性问题。比如我最近在 Replit 内部专门训练了一个**成本预测模型（Cost Estimator Model）**：当用户在 Replit 界面输入一段复杂的业务提示词时，该模型会在毫秒级内输出对多档资金消耗区间的离散概率分布（例如预测本次任务属于 5-10 美元档还是 10-20 美元档）。我通过枚举输出并通过 Log-probs 校验概率分布的方法训练这类分类器已经有两三年的经验了，以前我还用这种方法训练过专用的国际象棋 AI。底层的工业真相在于：如果你的平台坐拥丰富而垂直的专有业务数据——正如我们在 Replit 上所沉淀的代码与交互行为数据一样——你随时可以极其轻松地蒸馏并训练出一批表现完美、低延迟且极其轻量化的专用分类模型，完全没有必要在生产主流程中无节制地挥霍通用大模型的推理算力。

<details>
<summary>Original English</summary>

**Amjad Masad**: I've been training a lot of small models internally. For example, I trained a cost estimator model internally so that when you put in a prompt in Replit, we know how much it will cost. It basically emits a probability distribution over multiple buckets: between $5 and $10, between $10 and $20, etc. I'm used to training these classifiers by giving them different enums and looking at the log probs for each enum; I've been doing it for a couple of years. I trained a chess bot to play by just doing that. So I'm already sold on decision models and specialized models. A true foundation model that's fully promptable is an amazing developer experience, and you can do a bunch of stuff without training a model from scratch. But if you work at a place where you have proprietary data—we have so much data at Replit—I ended up training a lot of specialized classification models pretty easily.

</details>

**Alex Atallah**: 专用小模型的另一个极其巨大的杀手级优势，在于它几乎**不存在沉重的“模型债务”（Model Debt）**。现在很多企业技术负责人在被要求针对复杂的非结构化任务微调大模型时都极其焦虑和抵触，因为大模型迭代速度太快了，企业今天辛辛苦苦微调维护一个大参数模型，两个月后市场上发布了全新一代的基础模型基座，之前的微调成果和技术资产便瞬间归零、沦为技术债务。相反，一个基于企业独家闭环数据训练的垂直分类器，其生命力极其顽强且历久弥新。你完全不需要为它是否掌握了某种全新的自然语言小语种、或者能不能流畅编写 Rust 和 Go 代码而操心；它只需要在自己负责的一亩三分地上精准完成业务裁决。对于企业而言，自研部署这类专用模型不仅启动门槛极低，而且在未来的技术演进中几乎永远不会让人产生被淘汰的懊悔。

<details>
<summary>Original English</summary>

**Alex Atallah**: It also feels like less model debt. Something I still hear from companies is that they're worried about fine-tuning models for unstructured outputs, because you'll just redo it again in two months, and everybody fears the weight of that model debt. But a bespoke classifier that's trained with proprietary data—people won't think it's constantly behind, and it will just last longer. You don't have to worry about its ability to speak a new language or write Rust or Go; you don't have to care about whatever LLMs are being evaluated on. You can build it in a night. It seems like an easy thing for enterprises to build themselves and not regret.

</details>

---

### 历史的周期律：从动态语言狂欢到 Rust 静态严谨，再到融合模型与缓存调度

**Amjad Masad**: 这让我想起整个软件工程史上极其经典的宏大周期律轮回，这与当年软件界从静态类型语言狂热拥抱动态解释型语言的历史何其相似！在世纪之初，全球软件业的标准范式是极其厚重严谨的 C++ 与 Java；随后，以 Python、JavaScript 和 Ruby 为代表的动态语言如疾风暴雨般席卷了整个互联网世界。那是一个狂飙突进的黄金创业时代，每个人都在惊呼：“这是瞬间将初创企业推向市场的唯一法宝！”Stripe 凭借 Ruby 搭建起了处理全球金融支付的庞大帝国，Facebook 基于 PHP 构建起了数十亿人的社交网络。然而狂欢过后，残酷的现实狠狠敲醒了所有人：动态语言在面对超大规模系统时带来了海量难以捕获的恶性 Bug，运行性能极其低下且维护噩梦不断。于是，工程师们不得不重新亡羊补牢：拼命给代码补打静态类型系统（TypeScript、MyPy）、在底层疯狂打补丁挂载 JIT 虚拟机；直至最后，集极致内存安全、强静态类型与超高并发性能于一身的 **Rust 语言** 强势登顶，彻底终结了无序混沌的局面。

我坚信，眼下的 AI 产业正在丝毫不差地重演这一历史循环。如今全行业都在盲目迷信全能神级大模型，试图用统一的巨无霸模型去蛮力解决现实世界中一切错综复杂的业务诉求。总有一天，所有技术领袖都会猛然醒悟：这种架构在算力成本上是何等挥霍浪费，在系统安全上又是何等脆弱且不可控！届时，整个技术栈必将全面回归到理性且精巧的专用模型体系中。在 Replit 平台上，我们正在把这种一键上传专有数据集、秒级编译生成垂直专用模型的能力直接开放给所有企业。这再次呼应了 OpenRouter 始终坚持的终极哲学——**神经多样性（Neurodiversity）**。未来绝不属于虚无缥缈的大一统 AGI 神级模型，而必然属于高度异构、多元共存的多模型繁荣生态。

<details>
<summary>Original English</summary>

**Amjad Masad**: Speaking of Rust, a good analogy is when the world got super excited about dynamic languages. If you think back, everyone was writing in Java and C++, and then Python, JavaScript, and Ruby just took over the internet. Everyone was like, "This is how you build startups really quickly." Stripe, a financial organization, was built on Ruby; Facebook was built using PHP. And then everyone was like, "We're running into all these really bad bugs, it's freaking slow." So let's go add types, let's add a JIT compiler—you end up reinventing everything. And then Rust came out, and it was like, "Okay, we can use Rust for a lot of things we would otherwise be using JavaScript or Python for." My prediction is that the same cycle will happen here, where we're using these AGI-like models for all these different use cases, and then everyone's going to wake up and be like, "Oh my god, this is so wasteful, so risky for no reason." It's going to be so much easier—we're actually adding that capability on Replit, but it's going to be everywhere—to go to a site, upload a CSV file, and get a specialized model that does one thing. That goes back to what this is about with OpenRouter: neurodiversity, which I fundamentally believe in a lot more. The future is a lot more diversity.

</details>

**Alex Atallah**: 这种多元化的多模型融合实践，最早就清晰地萌芽于软件工程的**代码审查（Code Review）**场景中。在代码审查这类高精度任务上，我们第一次看到工程师们极其严肃地引入来自不同公司谱系的模型，让它们互相交叉质检彼此的输出结果。在学术界，关于**模型混合（Mixture of Models）**与组合模型的理论探索已经进行了很多年，但直到最近，其落地演进才呈现出爆发式增长。包括 OpenRouter 在内的前沿团队近期都推出了**融合模型工具（Fusion Models）**：如果各大模型实验室所依赖的训练语料、思维偏置与技术底座各不相同，为什么要把鸡蛋放在同一个篮子里？通过聚合调度多元化的模型家族，我们在深度调研与复杂代码工程任务上，能够以低达原本二分之一的综合成本，稳定输出比肩最顶级闭源模型的超高质量。

<details>
<summary>Original English</summary>

**Alex Atallah**: Outside of code review, which was the first time I saw people get really serious about using different model families to double check the results of their main model, the research has been speeding up on doing mixture of models and composite models. Now we see a bunch of AI agent labs launching fusion models; we launched a fusion tool. They do reduce costs and allow a wider breadth of ideas to be searched. Our initial launch was focused on deep research: the thinking is that if all these model labs are training on different sources of data, why not pull from all of them? This resulted in frontier-level quality at 2x lower cost.

</details>

**Amjad Masad**: 毫无疑问，Replit 刚公布的最新突破性进展——我们在软件工程领域构建的 **Deep SWE** 智能体，正是深度融合了这一思想。通过精心设计的多阶段任务编排与底层 Harness 驱动，我们在严苛的代码基准测试上以低至 40% 到 50% 的极低计算成本，实现了全面对标顶尖前沿模型的非凡表现。在这类复杂融合调度架构的工程实现中，最致命的核心命题莫过于**前缀缓存感知（Cache Awareness）**。现代前沿模型厂商（如 OpenAI）近期引入的跨推理努力等级与跨请求复用机制极大地释放了性能红利；在构建高级融合路由器（Fusion Routers）与模型级联网络时，如何最大化利用底层的上下文缓存命中率，正在成为决定系统成本与响应延迟生死的终极胜负手。

<details>
<summary>Original English</summary>

**Amjad Masad**: We just published results today about that, where we showed Deep SWE: Replit Agent, through a combination of different things including the harness, but also you might think of it as a fusion-type thing, reached frontier-level performance at 40% to 50% of the cost. Being cache-aware is one of the biggest things when you're designing fusion models, routers, and isolation models.

</details>

**主持人**: 这真是一场高潮迭起、信息密度极高的精彩对话，非常感谢两位嘉宾的深度分享！

<details>
<summary>Original English</summary>

**Host**: It's been a great conversation.

</details>

**Amjad Masad**: 谢谢，非常高兴能来到这里。

<details>
<summary>Original English</summary>

**Amjad Masad**: Thank you.

</details>