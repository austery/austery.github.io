---
author: House of El - AI
date: '2026-05-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Jbh8QteVM5g
speaker: House of El - AI
tags:
  - ai-deployment
  - business-strategy
  - human-ai-collaboration
  - system-design-failure
  - organizational-impact
title: 企业盲目部署AI，如今付出代价
summary: 本文深入剖析企业在AI部署中将人工智能视为人类判断替代品而非增强工具的案例。通过Pizza Hut和Klarna的失败经验，揭示了缺乏系统性测试、并行运行和对人类激励机制理解的风险。强调了AI应增强现有团队而非取代，呼吁负责任的AI整合以避免广泛的负面影响和公众反弹。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Yum Brands
  - Pizza Hut
  - Klarna
  - OpenAI
  - DoorDash
  - Nvidia
  - Salesforce
  - Workday
  - Forrester
  - Gartner
  - Infotech Research Group
products_models:
  - Dragontail
  - Bite by Yum
  - QT
  - GPT-4o
media_books: []
status: evergreen
---
### AI的危险幻象：Pizza Hut的“超级经理”何以失灵？

当**Pizza Hut**（必胜客）的一个特许经营商提起高达1亿美元的诉讼，声称母公司强制推行的AI系统**Dragontail**（龙尾）彻底摧毁了其业务时，AI在企业应用中的深层问题浮出水面。据诉讼描述，导入该系统后，外送时间翻倍，顾客满意度直线下降，披萨在保温架上放置长达20分钟无人问津。吊诡的是，**Dragontail**本被其创造者誉为“超级经理”，旨在确保“绝不会出现餐点在等待司机”的情况。然而，讽刺的是，它恰恰制造了其设计初衷力图避免的局面。本文将深入探讨两个AI部署灾难性失败的案例，并剖析问题症结所在，因为答案可能与普遍预期大相径庭。

<details><summary>Original English Source</summary>

A Pizza Hut franchise filed on a $100 million lawsuit claiming that an AI system, one that the parent company mandated across its restaurants, destroyed its business. Delivery times doubled, customer satisfaction collapsed, pizzas sat on metal racks going cold for up to 20 minutes before a driver bothered to pick them up. The AI system responsible was called Dragontail and it was specifically designed to make sure that never happened. Its creators literally described it as a super manager, an algorithm that would ensure there is never a situation where the meal is waiting on the bench waiting for the driver to show up. The super manager's first act of management was to create the exact situation it was specifically designed to prevent, which to be fair, it does make it sound like a real manager. In this video, I'm going to look at two cases where AI deployment went badly wrong and cost companies enormous amounts of money, reputation, and trust. And I'm going to unpack who is actually at fault because the answer might not be what we expect. I'm L, I have a PhD in computer science and I analyze AI developments to understand what's actually happening beneath the hype. But before anyone assumes this is an anti-AI video, it is not. I think AI is a generally powerful set of tools and I think companies should be using it. What I want to examine is something more specific. What happens when companies treat AI as a replacement for human judgment instead of an enhancement of it. And why the consequences of getting that wrong extend far beyond the companies themselves. So, what exactly did Pizza Hut do? In 2021, Yum Brands, the parent company of Pizza Hut, KFC, Taco Bell, and Habit Burger and Grill, acquired an Australian AI company called Dragontail Systems for approximately $72 million.

</details>

### AI“超级经理”的失误：信息透明与激励错配

**Dragontail**在纸面上是一款近乎完美的AI平台，专为披萨外送链设计，能够管理从订单到派送的全流程：优化厨房排单、烤箱时间、配送路线、地理位置合并订单，并自动调度司机。它甚至配备了名为**QT**的AI摄像头系统，实时监控食物准备质量。**Yum Brands**（百胜品牌，**Pizza Hut**的母公司）以7200万美元收购了开发**Dragontail**的**Dragontail Systems**公司，并将其作为“超级经理”强制推广到旗下餐馆，整合进其**Bite by Yum**（百胜数字平台）技术平台。

然而，当“超级经理”**Dragontail**抵达像**Chuck Pizza Northeast**这样在AI引入前已表现卓越的特许经营商时，问题出现了。**Chuck Pizza Northeast**拥有111家门店，曾实现两位数销售增长，顾客满意度高于平均水平，并保持90%的订单在30分钟内送达。这家门店不雇佣自己的配送司机，而是完全依赖**DoorDash**（外卖平台）。在**Dragontail**之前，门店经理会手动将订单输入**DoorDash**平板，控制司机接单，甚至可以阻止表现不佳的司机。这种直接的人工协调虽然不先进，但行之有效，保证了90%的准时送达率。

**Dragontail**的介入改变了信息环境。它与**DoorDash**平台集成，让司机首次获得了厨房运作的实时可见性：他们可以看到披萨何时进烤箱、何时出炉、小费金额甚至是否是现金订单。问题并非AI技术本身失灵，而是它无意中制造了新的激励结构。如果一个独立接单、按单计费的**DoorDash**司机，在优化自身收入时，发现8分钟后有另一份去往同小区的披萨即将出炉，他们会怎么做？答案显而易见：等待。这正是“超级经理”带来的意外后果。**Dragontail**赋予了零工工人“完美信息”，结果他们也“完美地”利用了这些信息来最大化自身利益，导致了“叠单”（stacking）等行为，严重拖慢了服务时间。

<details><summary>Original English Source</summary>

It was their third technology acquisition that year. Dragontail's product was on paper exactly what a delivery-focused pizza chain would want, an end-to-end AI platform that manages the entire journey from order to delivery. The algorithm sequences kitchen orders, times when each pizza should go into the oven, plans delivery routes, combines order by geographic proximity, and dispatches drivers all automatically. It also [snorts] includes an AI camera system called QT that monitors food preparation quality in real time, checking for toppings, temperature, even cleanliness, that sort of thing. The pitch to franchises was very straightforward. Dragontail replaces the coordination work that a human shift manager currently does. Instead of a person juggling kitchen timing, driver availability, and order prioritization in their heads, an algorithm does it faster and more accurately. The system was marketed as the super manager, and Yum mandated its deployment across Pizza Hut restaurants, folding it into their broader proprietary tech platform called Bite by Yum, which launched in February 2025 and now covers roughly 38,000 restaurants globally. Now, one of the franchises that received this mandatory upgrade was Chuck Pizza Northeast, an operator running 111 Pizza Hut locations across New York, New Jersey, Maryland, Washington D.C., and Pennsylvania. Before Dragontail arrived, Chuck was one of Pizza Hut's strongest performers, double-digit sales growth, guest satisfaction scores above the system average, and critically, more than 90% of their pizza deliveries arrive within 30 minutes. That number matters, remember it. So, what happened when the super manager showed up? Here's where most coverage of the story says the AI broke and just moves on. But, if you actually read the lawsuit, the mechanism is far more interesting and far more instructive than a simple malfunction. Chuck Pizza is a delivery-only and carryout operation. It does not employ its own delivery drivers. it relies entirely on DoorDash. Before Dragontail, Chuck's managers manually entered orders into the DoorDash tablet. They controlled which drivers received which orders, they could block poorly rated drivers from accepting deliveries, they managed the timing between kitchen output and driver pickup through direct human coordination. It was not exactly glamorous, it was not cutting edge, but it worked demonstrably, measurably, 90% of deliveries on time worked. Dragontail changed the information environment. The system integrated with DoorDash's platform and gave drivers something they had never previously had, real-time visibility into kitchen operations. Drivers could now see when specific pizzas were going into the oven and when they would come out. They could see tip amounts before accepting a delivery, they could see whether orders were cash transactions. Now, ask yourself a question. If you were an independent gig worker paid per delivery optimizing for your own hourly earnings, and could suddenly see that another pizza would be coming out of the oven in 8 minutes, and it was going to the same neighborhood as the one already sitting on the rack, what would you do? You would wait. And that's exactly what happened. Dragontail gave gig workers perfect information, and then was surprised when they used it perfectly. This is the AI equivalent of handing somebody a map to your vault and being shocked when they show up.

</details>

### 系统失灵：从90%到50%的“优化”

这种信息透明导致的**“叠单”**行为，使得披萨从做好到被取走的时间（rack time）从不到5分钟飙升至20分钟。平均配送时间从30分钟延长到超过45分钟，准时送达率从90%暴跌至50%。这个“超级经理”将一个90%高效的系统“优化”成了50%的效率。

更糟的是，**Yum Brands**在推广**Dragontail**的同时，还集中管理了**Pizza Hut**与**DoorDash**的合同，剥夺了特许经营商与**DoorDash**的直接关系，以及阻止表现不佳司机的能力。这意味着，AI替代了人工协调层，而母公司同时移除了人工的备用选项。

核心问题在于：AI系统本身并未“故障”。它没有崩溃，也没有错误计算路线或排序订单。**Dragontail**所做的，是改变了信息环境，从而为系统中的人类参与者创造了新的激励结构。**Dragontail**假设所有参与者都会像输入数据一样，为它的优化模型服务。然而，**DoorDash**司机却像他们本来的身份一样——独立的经济主体，为自身收益最大化而优化行为。两个独立的优化系统——**Dragontail**的算法和**DoorDash**的零工经济市场——在没有充分建模其交互方式的情况下被连接起来，导致了双方都未曾预料的“涌现行为”。

这在计算机科学中是一个众所周知的问题类别：当独立优化的系统在没有建模其交互的情况下被连接时，会产生任何单个组件都未曾预料的结果。这本质上是**系统设计失败**，更深层次地说是**商业战略失败**。**Yum Brands**的决策者在没有测试AI算法在特定运营环境下（例如，完全依赖第三方零工配送司机）的假设是否成立的情况下，就将其强制推行到整个特许经营网络。

<details><summary>Original English Source</summary>

DoorDash drivers began waiting inside or near the store for up to 15 minutes to batch multiple deliveries together. They cherry-picked orders based on tip visibility, cash orders got deprioritized. The lawsuit uses a phrase that I think is technically precise and quietly devastating. Dragontail invited stacking and other algorithmic behaviors that significantly slow service time. The result was that rack time, the time a finished pizza sits waiting before a driver collects it, went from under 5 minutes to as much as 20 minutes. Average delivery time went from 30 minutes to more than 45. Only approximately 50% of orders were delivered within 30 minutes. Remember that 90% figure from before? Cut almost in half. The super manager took a system that was working 90% of the time and optimized it down to 50%. It sounds like a downgrade with a press release, doesn't it? And there was a compounding layer. Simultaneously with a Dragon Tail roll out, Pizza has centralized its DoorDash contract, taking it away from individual franchises and moving it to a national agreement. So, Chuck lost his direct relationship with DoorDash. It lost the ability to block underperforming drivers. It lost the informal management tools that had made the 90% delivery rate possible. The AI replaced the human coordination layer, and the parent company simultaneously removed the human fallback options. So, here is the question I want to sit with for a moment. Did the AI malfunction? No, the algorithm did not crash. It did not miscalculate routes. It did not sequence orders incorrectly. What it did was change the information environment in a way that created new incentive structures for the human actors in the system. Dragon Tail assumed all participants would behave as inputs to its optimization model. The DoorDash drivers behaved as what they actually are, independent economic agents optimizing for their own earnings. Two optimization systems, Dragon Tail's algorithm and DoorDash's gig economy marketplace, were connected without anyone modeling how they would interact. And the result was an emergent behavior that neither system was designed to produce. In computer science, this is a well-understood category of problem. When you connect independently optimizing systems without modeling their interactions, you get outcomes that no individual component intended. It is a systems design failure and more fundamentally it is a business strategy failure. Someone at Yum Brands made the decision to mandate an AI system across a franchise network that included operators exclusively dependent on third-party gig delivery drivers without testing whether the algorithms assumptions held in that specific operating environment. I think about this in terms of nuclear

</details>

### 核能的警示：AI部署的“切尔诺贝利”时刻

这让人联想到**核能**（nuclear energy）的部署。核能是革命性的，但明智的做法并非一夜之间关闭所有燃煤电厂，而是并行运行系统、建立测试设施、制定安全协议，并逐步扩展。那些不这样做、急于部署而缺乏充分测试和冗余的运营商，最终导致了**切尔诺贝利**（Chernobyl）灾难。这场灾难不仅伤害了相关运营商，更使整个核能行业倒退了几十年。公众信任崩塌，监管变得惩罚性而非支持性。许多本可从清洁核能中受益巨大的国家，因为鲁莽的实施而将其全盘否定。

AI目前的发展与此惊人地相似。这引出了第二个案例。**Pizza Hut**的故事并非孤例。2023年，瑞典金融科技公司**Klarna**（克拉纳）与**OpenAI**（开放人工智能）合作，用AI聊天机器人取代了约700名客服人员。**Klarna**的CEO塞巴斯蒂安·谢米亚特科夫斯基（Sebastian Siemiatkowski）高调宣称，该聊天机器人能处理三分之二的客户对话，效率堪比被取代的700名人工坐席。到2024年底，他公开吹嘘**Klarna**在过去一年中没有招聘一名人工员工，并切断了与**Salesforce**（销售易）和**Workday**（工时）的合作，声称AI使这些平台变得不必要。**Klarna**的IPO（首次公开募股）故事核心正是AI带来的效率提升。

<details><summary>Original English Source</summary>

energy. When nuclear power arrived it was generally revolutionary, orders of magnitude more energy dense than anything that had come before. The smart approach was never to shut down every coal plant overnight and go all in on nuclear reactors. The smart approach was to run parallel systems, build test facilities, develop safety protocols, scale gradually learning as you go. The operators who didn't do that, who rushed deployment without adequate testing, without understanding the full system dynamics, without redundancy, gave the world Chernobyl sadly and that disaster didn't just harm the operators involved, it set back the entire nuclear energy industry for decades. Public trust collapsed, regulation became punitive rather than enabling. Countries that could have benefited enormously from clean nuclear energy rejected it wholesale, not because the technology was inherently dangerous, but because reckless implementation had made it appear so. The parallel to what is happening with AI right now is almost exact and it brings me to the second case because the Pizza Hut story is not an isolated incident exactly. In 2023, Swedish fintech company Klarna replaced approximately 700 customer service workers with an AI chatbot built in partnership with OpenAI. The company's CEO, Sebastian Siemiatkowski, became arguably the loudest corporate voice in the world on the topic of AI replacing human workers. He announced that the chatbot could handle two-thirds of all customer conversations and match the productivity of the 700 agents it replaced. By the end of 2024, he was publicly boasting that Klarna had not hired a single human worker in the entire preceding year, telling interviewers that employees were rallying to deploy as much efficiency AI as they can. The company cut ties with Salesforce and Workday, [clears throat] claiming AI made both platforms unnecessary. This was not a quiet efficiency play. This was a corporate identity built around the premise that AI could replace human judgment at scale.

</details>

### AI无法取代判断力：Klarna的IPO“U型转弯”

**Klarna**于2025年7月上市，AI效率叙事是其IPO的核心支柱，股价在首次亮相时飙升30%。然而，仅仅几个月后，情况急转直下。客户满意度显著恶化，因为AI虽然能处理大量事务，却无法轻易应对复杂情况。它无法处理带有情绪的互动、多步骤的问题解决以及需要判断而非模式匹配的边缘案例。客户抱怨AI的回复过于通用、重复且不够细致。

到2025年5月，首席执行官谢米亚特科夫斯基向彭博社承认：“我们过于关注效率和成本。结果是质量下降，这是不可持续的。”这距离他以完全相反的论点上市仅10个月。有人称之为“战略演变”，但更恰当的描述是“IPO历史上最快的U型转弯”。到2025年9月，**Klarna**悄然重新招聘人工员工。公司通讯主管将其描述为“战略演变”，但外部分析师更为直接。**Infotech Research Group**（信息技术研究集团）的首席研究总监朱莉·盖勒（Julie Geller）指出，AI应该**增强**人工坐席，而非**取代**他们。

仅仅几周内，投资者就发现，当初基于AI驱动效率购买的股票，其背后的公司正在重新招聘人工。**Klarna**以高昂的代价、公开的方式，并在上市后才发现：AI可以处理问题，但无法理解一个沮丧的客户为什么会提出这个问题。

<details><summary>Original English Source</summary>

Klarna went public in July 2025. The AI efficiency narrative was a central part of its IPO story. Shares surged 30% on debut. The market loved it, and within months the story reversed. Customer satisfaction had deteriorated significantly. The AI handled volume, that part was true, but it could not handle complexity easily. Emotionally charged interactions, multi-step problem resolution, edge cases that required judgment rather than pattern matching. Customers reported generic, repetitive, and insufficiently nuanced responses. By May 2025, Siemiatkowski admitted to Bloomberg, "We focused too much on efficiency and cost. The result was lower quality, and that is not sustainable." He said this 10 months after going public on the exact opposite thesis. Strategic evolution is one way to describe that timeline. Another is the fastest U-turn in IPO history. By September 2025, Klarna was quietly rehiring humans again, some of the same roles it had eliminated under Uber-style flexible model. The company's head of communications framed it as a strategic evolution rather than a correction. External analysts were a lot more direct. Julie Geller, principal research director at Infotech Research Group, said the The was very straightforward. AI should augment human agents, not replace them. And notice the timeline as well. Klarna pitched public market investors on an AI-first customer service model in July 2025. By September 2025, the company was undoing the strategy that investors had just bought into. Investors who purchased shares on the basis of AI-driven efficiency were learning within weeks that the company was hiring humans back. Strategic evolution is a generous description of that Klarna discovered expensively, publicly, and after going to market on the claim that AI can process a question, but cannot understand why a frustrated customer is asking it. These are two different companies and two different industries deploying two completely different types of AI, but the pattern underneath is identical.

</details>

### AI与人类的协同：增强而非取代

这两个案例虽然涉及不同的公司、行业和AI类型，但其底层模式如出一辙。AI本身并非“技术故障”，失败的根源在于商业决策：将AI视为对人类判断的**完全替代**，而非**增强**。两者都未能建立冗余系统、并行测试和循序渐进的部署机制，从而在问题演变为灾难之前暴露出来。

软件工程领域的基本原则是：替换关键系统时，绝不能简单地关闭旧系统、开启新系统。正确的做法是**并行运行**（run them in parallel），将一部分流量引向新系统，同时保持旧系统运行。比较两者输出，寻找边缘案例，在真实负载下进行测试。只有当新系统在生产条件下（而非实验室条件）证明其性能与旧系统相当或更优时，才能逐步淘汰旧系统。这不是激进概念，而是任何系统故障可能带来真实后果的领域中的基本操作实践。

那些在AI部署上犯错的公司，恰恰跳过了所有这些步骤。数据表明，这并非小众问题。**Forrester**（弗雷斯特）2026年的《未来工作报告》（Future of Work report）发现，55%的雇主后悔因AI而裁员。超过一半的公司后悔用AI取代员工。相比之下，后悔纹身的人都更少。**Gartner**（高德纳）对321位客户服务领导者的调查显示，只有20%的公司真正因为AI减少了员工。绝大多数公司保持员工数量稳定，并利用AI处理与现有团队共同增加的工作量。**Gartner**预测，到2027年，50%因AI而削减客户服务员工的公司将重新招聘人员来执行类似职能。被AI取代的职位正在被“反取代”。

<details><summary>Original English Source</summary>

In both cases, the AI was not technically broken. In both cases, the failure was a business decision to use AI as a wholesale replacement for human judgment rather than an augmentation of it. And in both cases, nobody built in the redundancy, the parallel systems, the gradual testing that would have revealed the problems before they became catastrophic. If you work anywhere near software engineering, you know that when you replace a critical system, you do not simply switch off the old one and turn on the new one. You run them in parallel. You route a percentage of traffic through the new system while the old system remains operational. You compare outputs. You look for edge cases. You test under real-world load. And only after the new system has demonstrated under production condition, not lab conditions, that it performs as well or better, do you begin to decommission the old one? This is not a radical concept. It is basic operational practice in any discipline where system failure has real consequences. The companies getting AI wrong are the ones skipping all of that. And the data says this is not a niche problem, either. Forrester's 2026 Future of Work report found that 55% of employers regret laying off workers for AI. 55% more than half of companies regret replacing their workers with AI. For context, fewer people regret their tattoos. A Gartner survey of 321 customer service leaders found that only 20% had actually reduced staffing because of AI. The vast majority kept head count steady and used AI to handle increased volume alongside existing teams. And Gartner predicts that by 2027, 50% of companies that cut customer service staff for AI will rehire people to perform similar functions. The replacements are becoming unreplacements.

</details>

### 成功的AI实践：计算交给AI，判断力归于人类

**Forrester**的报告直言不讳：C级高管们往往是为AI未来的承诺而裁员，而非基于已被证实的能力，甚至是为了尚未存在的能力。真正获得回报的公司做法则大相径庭：他们利用AI提升现有团队的生产力，而非淘汰他们。

例如：
*   **Unity**每年节省130万美元，通过AI总结工单历史并处理常规请求，而未裁减任何支持人员。
*   **Hiscox**（海斯科普斯）保险团队将理赔处理时间从一小时缩短到十分钟，通过AI整理文件，最终决策仍由人工理赔员做出。
*   物流公司在调度主管的配合下，使用路线优化算法（而非取代主管），减少了18%的配送延误。AI处理计算，人类则处理当地知识、天气、路况以及临时请假的司机等突发情况。

这才是行之有效的模式：**AI处理计算，人类处理判断**（AI handles the computation, humans handle the judgment）。两者协作能达到单一系统无法实现的效果。若割裂开来，则只会得到冷掉的披萨和愤怒的顾客。

<details><summary>Original English Source</summary>

The Forrester report put it very bluntly, too often the C-suite lays workers off for the future promise of AI, not for proven capability, but for capability that does not yet exist. The companies that are actually seeing returns are doing something different. They're using AI to make their existing teams more productive, not to eliminate them. Unity saved $1.3 million annually by using AI to summarize ticket histories and deflect routine requests without cutting a single support agent. Hiscox insurance teams reduced claims processing time from an hour to 10 minutes by using AI to compile documentation for human adjusters who still made the final decisions. Logistics carriers using route optimization algorithms alongside dispatch supervisors, not instead of them, reported 18% fewer delivery delays because the technology handled the maths and the humans handled the local knowledge, the weather, the road works, the driver who calls in sick at the last minute. That is the model that works. AI handles the computation, humans handle the judgment. Together you get something neither could achieve. Separately you get cold pizza and angry customers. And

</details>

### 警惕“AI切尔诺贝利”效应：伤害整个生态

这些高调的失败案例，不仅伤害了涉事公司，更助长了公众对AI的强烈反感。它强化了“AI是企业攫取工具而非真正改进”的观点，并使得对AI施加限制性监管变得更容易。对于那些正在深思熟虑地整合AI的组织来说，这使得他们更难证明这项技术可以普遍改善所有人的结果。

那些**鲁莽的部署者**——在数千个地点强制推行未经测试的AI的公司、在技术尚未证明其能力之前就围绕取代人工员工构建IPO叙事的CEO们——他们不仅在伤害自己，也在伤害整个**AI生态系统**。他们就像那些跳过安全协议、急于启动反应堆的运营商，然后在结果破坏了公众对整个事业的信心时表现出惊讶。这又是**切尔诺贝利**事件的重演，只是这次的主角是AI。

**Yum Brands**似乎并未吸取教训。尽管**Chuck E. Cheese's**的诉讼指控**Dragontail**导致了连锁运营崩溃和1亿美元的损失，但**Yum**却同时与**Nvidia**（英伟达）合作，将更多AI部署到500家餐厅，包括用于免下车点餐的**语音AI**、实时监控员工的**计算机视觉系统**，以及为餐厅经理生成的**AI行动计划**。当被问及算法监控员工所引发的伦理问题时，**Yum**没有回应。

所有这一切都发生在**Pizza Hut**关闭250家美国门店、连续第九个季度同店销售额下降、母公司正在进行战略评估并可能考虑出售该品牌之际。**Yum Brands**在2025年仅在战略评估上就花费了3600万美元。3600万美元来弄清楚一家披萨连锁店出了什么问题？用这笔钱，你可以重新雇佣所有被**Dragontail**取代的班次经理，并给他们加薪。

因此，对于那些正在构建下一波AI部署的管理者们来说，**技术本身不是问题**。在许多情况下，这项技术绝对是了不起的。但是，一个**卓越的工具**，如果在部署时未能理解其将进入的系统、未经测试、缺乏冗余，并且**不尊重其所取代的人类判断力**，那它就不是创新，而是带着昂贵标签的**玩忽职守**（negligence）。

对于那些因为想看到AI失败而观看此视频的观众，我理解这种冲动，但这里的失败并非**人工智能**（artificial intelligence）本身。这是人类鲁莽部署的**非常人性的决策**。**“超级经理”从来不是问题，问题在于那些在不理解其将如何与现实世界互动的情况下强制推行它的真正管理者。**

<details><summary>Original English Source</summary>

here's what generally concerns me personally by the broader trajectory of all of this. Every one of these high-profile failures does not just hurt the company involved. It feeds a growing public backlash against AI as a whole. It hardens the position of people who believe AI is fundamentally a tool for corporate extraction rather than genuine improvement. It makes it politically easier to impose restrictive regulation and harder for the organizations doing thoughtful, AI integration to make the case that this technology can generally improve outcomes for everyone. The reckless deployers, the companies mandating untested AI across thousands of locations, the CEOs building IPO narratives around replacing human workers before the technology has proven it can actually do their jobs are not just harming themselves, they're harming the entire ecosystem. They are the operators who skip the safety protocols, rush the reactor online, and then act as surprised when the results undermine public confidence in the whole enterprise. It's Chernobyl all over again, except with AI. And Yum Brands, for its part, appears to have learned nothing. While Chuck E. Cheese's lawsuit alleges that Dragon Tail caused cascading operational breakdowns and $100 million in damages, Yum has simultaneously partnered with Nvidia to deploy even more AI across 500 restaurants, including voice AI for drive-thru ordering, computer vision systems designed to surveil workers in real time, and AI-generated action plans for restaurant managers. Restaurant Dive noted that Yum did not respond to questions about the ethical issues raised by algorithmic surveillance of workers. All of this while Pizza Hut is closing 250 US locations, posting its ninth consecutive quarter of same-store sale declines, and the parent company is conducting a strategic review that could lead to selling the brand entirely. They spent $36 million on that review process in 2025 alone. $36 million to figure out what went wrong at a pizza chain? For that money, you could have hired back every shift manager Dragon Tail replaced and given them each a raise. So, to the executives building the next wave of AI deployment, the technology is not the problem. The technology is, in many cases, absolutely remarkable. But, a remarkable tool deployed without understanding the system it is entering, without testing, without redundancy, without respect for the humans whose judgment it is replacing, is not innovation. It is negligence with a very expensive sticker on it. And to the audience members who came to this video because they wanted to see AI fail, I get the impulse, but the failure here was not artificial intelligence. It was the very human decision to deploy it recklessly. The super manager was never the problem. The problem was the actual managers who mandated it without understanding what it would do when it met the real world. But, Pizza Hut and Klarna are not the only ones reaching for the wrong lever. Companies across industries are doing the exact same thing, firing people in the name of AI, and the data says it's not working, either. I made a video about what the numbers actually show when companies try to replace their workforce instead of augmenting it, and why the most expensive mistake in AI right now has nothing to do with the technology. That's the one that I would watch next. Thanks so much for watching this one. Subscribe, and I'll see y'all on the next one.

</details>
[BODY_END]
```yaml
[AI_META_START]
title: "企业盲目部署AI，如今付出代价"
summary: "本文深入剖析企业在AI部署中将人工智能视为人类判断替代品而非增强工具的案例。通过Pizza Hut和Klarna的失败经验，揭示了缺乏系统性测试、并行运行和对人类激励机制理解的风险。强调了AI应增强现有团队而非取代，呼吁负责任的AI整合以避免广泛的负面影响和公众反弹。"

area: "tech-engineering"
category: "ai-ml"

project: []

tags:
  - "ai-deployment"
  - "business-strategy"
  - "human-ai-collaboration"
  - "system-design-failure"
  - "organizational-impact"

people: []

companies_orgs:
  - "Yum Brands"
  - "Pizza Hut"
  - "Klarna"
  - "OpenAI"
  - "DoorDash"
  - "Nvidia"
  - "Salesforce"
  - "Workday"
  - "Forrester"
  - "Gartner"
  - "Infotech Research Group"

products_models:
  - "Dragontail"
  - "Bite by Yum"
  - "QT"
  - "GPT-4o"

media_books: []
[AI_META_END]
```
[BODY_START]
### AI的危险幻象：Pizza Hut的“超级经理”何以失灵？

当**Pizza Hut**（必胜客）的一个特许经营商提起高达1亿美元的诉讼，声称母公司强制推行的AI系统**Dragontail**（龙尾）彻底摧毁了其业务时，AI在企业应用中的深层问题浮出水面。据诉讼描述，导入该系统后，外送时间翻倍，顾客满意度直线下降，披萨在保温架上放置长达20分钟无人问津。吊诡的是，**Dragontail**本被其创造者誉为“超级经理”，旨在确保“绝不会出现餐点在等待司机”的情况。然而，讽刺的是，它恰恰制造了其设计初衷力图避免的局面。本文将深入探讨两个AI部署灾难性失败的案例，并剖析问题症结所在，因为答案可能与普遍预期大相径庭。

<details><summary>Original English Source</summary>

A Pizza Hut franchise filed on a $100 million lawsuit claiming that an AI system, one that the parent company mandated across its restaurants, destroyed its business. Delivery times doubled, customer satisfaction collapsed, pizzas sat on metal racks going cold for up to 20 minutes before a driver bothered to pick them up. The AI system responsible was called Dragontail and it was specifically designed to make sure that never happened. Its creators literally described it as a super manager, an algorithm that would ensure there is never a situation where the meal is waiting on the bench waiting for the driver to show up. The super manager's first act of management was to create the exact situation it was specifically designed to prevent, which to be fair, it does make it sound like a real manager. In this video, I'm going to look at two cases where AI deployment went badly wrong and cost companies enormous amounts of money, reputation, and trust. And I'm going to unpack who is actually at fault because the answer might not be what we expect. I'm L, I have a PhD in computer science and I analyze AI developments to understand what's actually happening beneath the hype. But before anyone assumes this is an anti-AI video, it is not. I think AI is a generally powerful set of tools and I think companies should be using it. What I want to examine is something more specific. What happens when companies treat AI as a replacement for human judgment instead of an enhancement of it. And why the consequences of getting that wrong extend far beyond the companies themselves. So, what exactly did Pizza Hut do? In 2021, Yum Brands, the parent company of Pizza Hut, KFC, Taco Bell, and Habit Burger and Grill, acquired an Australian AI company called Dragontail Systems for approximately $72 million.

</details>

### AI“超级经理”的失误：信息透明与激励错配

**Dragontail**在纸面上是一款近乎完美的AI平台，专为披萨外送链设计，能够管理从订单到派送的全流程：优化厨房排单、烤箱时间、配送路线、地理位置合并订单，并自动调度司机。它甚至配备了名为**QT**的AI摄像头系统，实时监控食物准备质量。**Yum Brands**（百胜品牌，**Pizza Hut**的母公司）以7200万美元收购了开发**Dragontail**的**Dragontail Systems**公司，并将其作为“超级经理”强制推广到旗下餐馆，整合进其**Bite by Yum**（百胜数字平台）技术平台。

然而，当“超级经理”**Dragontail**抵达像**Chuck Pizza Northeast**这样在AI引入前已表现卓越的特许经营商时，问题出现了。**Chuck Pizza Northeast**拥有111家门店，曾实现两位数销售增长，顾客满意度高于平均水平，并保持90%的订单在30分钟内送达。这家门店不雇佣自己的配送司机，而是完全依赖**DoorDash**（外卖平台）。在**Dragontail**之前，门店经理会手动将订单输入**DoorDash**平板，控制司机接单，甚至可以阻止表现不佳的司机。这种直接的人工协调虽然不先进，但行之有效，保证了90%的准时送达率。

**Dragontail**的介入改变了信息环境。它与**DoorDash**平台集成，让司机首次获得了厨房运作的实时可见性：他们可以看到披萨何时进烤箱、何时出炉、小费金额甚至是否是现金订单。问题并非AI技术本身失灵，而是它无意中制造了新的激励结构。如果一个独立接单、按单计费的**DoorDash**司机，在优化自身收入时，发现8分钟后有另一份去往同小区的披萨即将出炉，他们会怎么做？答案显而易见：等待。这正是“超级经理”带来的意外后果。**Dragontail**赋予了零工工人“完美信息”，结果他们也“完美地”利用了这些信息来最大化自身利益，导致了“叠单”（stacking）等行为，严重拖慢了服务时间。

<details><summary>Original English Source</summary>

It was their third technology acquisition that year. Dragontail's product was on paper exactly what a delivery-focused pizza chain would want, an end-to-end AI platform that manages the entire journey from order to delivery. The algorithm sequences kitchen orders, times when each pizza should go into the oven, plans delivery routes, combines order by geographic proximity, and dispatches drivers all automatically. It also [snorts] includes an AI camera system called QT that monitors food preparation quality in real time, checking for toppings, temperature, even cleanliness, that sort of thing. The pitch to franchises was very straightforward. Dragontail replaces the coordination work that a human shift manager currently does. Instead of a person juggling kitchen timing, driver availability, and order prioritization in their heads, an algorithm does it faster and more accurately. The system was marketed as the super manager, and Yum mandated its deployment across Pizza Hut restaurants, folding it into their broader proprietary tech platform called Bite by Yum, which launched in February 2025 and now covers roughly 38,000 restaurants globally. Now, one of the franchises that received this mandatory upgrade was Chuck Pizza Northeast, an operator running 111 Pizza Hut locations across New York, New Jersey, Maryland, Washington D.C., and Pennsylvania. Before Dragontail arrived, Chuck was one of Pizza Hut's strongest performers, double-digit sales growth, guest satisfaction scores above the system average, and critically, more than 90% of their pizza deliveries arrive within 30 minutes. That number matters, remember it. So, what happened when the super manager showed up? Here's where most coverage of the story says the AI broke and just moves on. But, if you actually read the lawsuit, the mechanism is far more interesting and far more instructive than a simple malfunction. Chuck Pizza is a delivery-only and carryout operation. It does not employ its own delivery drivers. it relies entirely on DoorDash. Before Dragontail, Chuck's managers manually entered orders into the DoorDash tablet. They controlled which drivers received which orders, they could block poorly rated drivers from accepting deliveries, they managed the timing between kitchen output and driver pickup through direct human coordination. It was not exactly glamorous, it was not cutting edge, but it worked demonstrably, measurably, 90% of deliveries on time worked. Dragontail changed the information environment. The system integrated with DoorDash's platform and gave drivers something they had never previously had, real-time visibility into kitchen operations. Drivers could now see when specific pizzas were going into the oven and when they would come out. They could see tip amounts before accepting a delivery, they could see whether orders were cash transactions. Now, ask yourself a question. If you were an independent gig worker paid per delivery optimizing for your own hourly earnings, and could suddenly see that another pizza would be coming out of the oven in 8 minutes, and it was going to the same neighborhood as the one already sitting on the rack, what would you do? You would wait. And that's exactly what happened. Dragontail gave gig workers perfect information, and then was surprised when they used it perfectly. This is the AI equivalent of handing somebody a map to your vault and being shocked when they show up.

</details>

### 系统失灵：从90%到50%的“优化”

这种信息透明导致的**“叠单”**行为，使得披萨从做好到被取走的时间（rack time）从不到5分钟飙升至20分钟。平均配送时间从30分钟延长到超过45分钟，准时送达率从90%暴跌至50%。这个“超级经理”将一个90%高效的系统“优化”成了50%的效率。

更糟的是，**Yum Brands**在推广**Dragontail**的同时，还集中管理了**Pizza Hut**与**DoorDash**的合同，剥夺了特许经营商与**DoorDash**的直接关系，以及阻止表现不佳司机的能力。这意味着，AI替代了人工协调层，而母公司同时移除了人工的备用选项。

核心问题在于：AI系统本身并未“故障”。它没有崩溃，也没有错误计算路线或排序订单。**Dragontail**所做的，是改变了信息环境，从而为系统中的人类参与者创造了新的激励结构。**Dragontail**假设所有参与者都会像输入数据一样，为它的优化模型服务。然而，**DoorDash**司机却像他们本来的身份一样——独立的经济主体，为自身收益最大化而优化行为。两个独立的优化系统——**Dragontail**的算法和**DoorDash**的零工经济市场——在没有充分建模其交互方式的情况下被连接起来，导致了双方都未曾预料的“涌现行为”。

这在计算机科学中是一个众所周知的问题类别：当独立优化的系统在没有建模其交互的情况下被连接时，会产生任何单个组件都未曾预料的结果。这本质上是**系统设计失败**，更深层次地说是**商业战略失败**。**Yum Brands**的决策者在没有测试AI算法在特定运营环境下（例如，完全依赖第三方零工配送司机）的假设是否成立的情况下，就将其强制推行到整个特许经营网络。

<details><summary>Original English Source</summary>

DoorDash drivers began waiting inside or near the store for up to 15 minutes to batch multiple deliveries together. They cherry-picked orders based on tip visibility, cash orders got deprioritized. The lawsuit uses a phrase that I think is technically precise and quietly devastating. Dragontail invited stacking and other algorithmic behaviors that significantly slow service time. The result was that rack time, the time a finished pizza sits waiting before a driver collects it, went from under 5 minutes to as much as 20 minutes. Average delivery time went from 30 minutes to more than 45. Only approximately 50% of orders were delivered within 30 minutes. Remember that 90% figure from before? Cut almost in half. The super manager took a system that was working 90% of the time and optimized it down to 50%. It sounds like a downgrade with a press release, doesn't it? And there was a compounding layer. Simultaneously with a Dragon Tail roll out, Pizza has centralized its DoorDash contract, taking it away from individual franchises and moving it to a national agreement. So, Chuck lost his direct relationship with DoorDash. It lost the ability to block underperforming drivers. It lost the informal management tools that had made the 90% delivery rate possible. The AI replaced the human coordination layer, and the parent company simultaneously removed the human fallback options. So, here is the question I want to sit with for a moment. Did the AI malfunction? No, the algorithm did not crash. It did not miscalculate routes. It did not sequence orders incorrectly. What it did was change the information environment in a way that created new incentive structures for the human actors in the system. Dragon Tail assumed all participants would behave as inputs to its optimization model. The DoorDash drivers behaved as what they actually are, independent economic agents optimizing for their own earnings. Two optimization systems, Dragon Tail's algorithm and DoorDash's gig economy marketplace, were connected without anyone modeling how they would interact. And the result was an emergent behavior that neither system was designed to produce. In computer science, this is a well-understood category of problem. When you connect independently optimizing systems without modeling their interactions, you get outcomes that no individual component intended. It is a systems design failure and more fundamentally it is a business strategy failure. Someone at Yum Brands made the decision to mandate an AI system across a franchise network that included operators exclusively dependent on third-party gig delivery drivers without testing whether the algorithms assumptions held in that specific operating environment. I think about this in terms of nuclear

</details>

### 核能的警示：AI部署的“切尔诺贝利”时刻

这让人联想到**核能**（nuclear energy）的部署。核能是革命性的，但明智的做法并非一夜之间关闭所有燃煤电厂，而是并行运行系统、建立测试设施、制定安全协议，并逐步扩展。那些不这样做、急于部署而缺乏充分测试和冗余的运营商，最终导致了**切尔诺贝利**（Chernobyl）灾难。这场灾难不仅伤害了相关运营商，更使整个核能行业倒退了几十年。公众信任崩塌，监管变得惩罚性而非支持性。许多本可从清洁核能中受益巨大的国家，因为鲁莽的实施而将其全盘否定。

AI目前的发展与此惊人地相似。这引出了第二个案例。**Pizza Hut**的故事并非孤例。2023年，瑞典金融科技公司**Klarna**（克拉纳）与**OpenAI**（开放人工智能）合作，用AI聊天机器人取代了约700名客服人员。**Klarna**的CEO塞巴斯蒂安·谢米亚特科夫斯基（Sebastian Siemiatkowski）高调宣称，该聊天机器人能处理三分之二的客户对话，效率堪比被取代的700名人工坐席。到2024年底，他公开吹嘘**Klarna**在过去一年中没有招聘一名人工员工，并切断了与**Salesforce**（销售易）和**Workday**（工时）的合作，声称AI使这些平台变得不必要。**Klarna**的IPO（首次公开募股）故事核心正是AI带来的效率提升。

<details><summary>Original English Source</summary>

energy. When nuclear power arrived it was generally revolutionary, orders of magnitude more energy dense than anything that had come before. The smart approach was never to shut down every coal plant overnight and go all in on nuclear reactors. The smart approach was to run parallel systems, build test facilities, develop safety protocols, scale gradually learning as you go. The operators who didn't do that, who rushed deployment without adequate testing, without understanding the full system dynamics, without redundancy, gave the world Chernobyl sadly and that disaster didn't just harm the operators involved, it set back the entire nuclear energy industry for decades. Public trust collapsed, regulation became punitive rather than enabling. Countries that could have benefited enormously from clean nuclear energy rejected it wholesale, not because the technology was inherently dangerous, but because reckless implementation had made it appear so. The parallel to what is happening with AI right now is almost exact and it brings me to the second case because the Pizza Hut story is not an isolated incident exactly. In 2023, Swedish fintech company Klarna replaced approximately 700 customer service workers with an AI chatbot built in partnership with OpenAI. The company's CEO, Sebastian Siemiatkowski, became arguably the loudest corporate voice in the world on the topic of AI replacing human workers. He announced that the chatbot could handle two-thirds of all customer conversations and match the productivity of the 700 agents it replaced. By the end of 2024, he was publicly boasting that Klarna had not hired a single human worker in the entire preceding year, telling interviewers that employees were rallying to deploy as much efficiency AI as they can. The company cut ties with Salesforce and Workday, [clears throat] claiming AI made both platforms unnecessary. This was not a quiet efficiency play. This was a corporate identity built around the premise that AI could replace human judgment at scale.

</details>

### AI无法取代判断力：Klarna的IPO“U型转弯”

**Klarna**于2025年7月上市，AI效率叙事是其IPO的核心支柱，股价在首次亮相时飙升30%。然而，仅仅几个月后，情况急转直下。客户满意度显著恶化，因为AI虽然能处理大量事务，却无法轻易应对复杂情况。它无法处理带有情绪的互动、多步骤的问题解决以及需要判断而非模式匹配的边缘案例。客户抱怨AI的回复过于通用、重复且不够细致。

到2025年5月，首席执行官谢米亚特科夫斯基向彭博社承认：“我们过于关注效率和成本。结果是质量下降，这是不可持续的。”这距离他以完全相反的论点上市仅10个月。有人称之为“战略演变”，但更恰当的描述是“IPO历史上最快的U型转弯”。到2025年9月，**Klarna**悄然重新招聘人工员工。公司通讯主管将其描述为“战略演变”，但外部分析师更为直接。**Infotech Research Group**（信息技术研究集团）的首席研究总监朱莉·盖勒（Julie Geller）指出，AI应该**增强**人工坐席，而非**取代**他们。

仅仅几周内，投资者就发现，当初基于AI驱动效率购买的股票，其背后的公司正在重新招聘人工。**Klarna**以高昂的代价、公开的方式，并在上市后才发现：AI可以处理问题，但无法理解一个沮丧的客户为什么会提出这个问题。

<details><summary>Original English Source</summary>

Klarna went public in July 2025. The AI efficiency narrative was a central part of its IPO story. Shares surged 30% on debut. The market loved it, and within months the story reversed. Customer satisfaction had deteriorated significantly. The AI handled volume, that part was true, but it could not handle complexity easily. Emotionally charged interactions, multi-step problem resolution, edge cases that required judgment rather than pattern matching. Customers reported generic, repetitive, and insufficiently nuanced responses. By May 2025, Siemiatkowski admitted to Bloomberg, "We focused too much on efficiency and cost. The result was lower quality, and that is not sustainable." He said this 10 months after going public on the exact opposite thesis. Strategic evolution is one way to describe that timeline. Another is the fastest U-turn in IPO history. By September 2025, Klarna was quietly rehiring humans again, some of the same roles it had eliminated under Uber-style flexible model. The company's head of communications framed it as a strategic evolution rather than a correction. External analysts were a lot more direct. Julie Geller, principal research director at Infotech Research Group, said the The was very straightforward. AI should augment human agents, not replace them. And notice the timeline as well. Klarna pitched public market investors on an AI-first customer service model in July 2025. By September 2025, the company was undoing the strategy that investors had just bought into. Investors who purchased shares on the basis of AI-driven efficiency were learning within weeks that the company was hiring humans back. Strategic evolution is a generous description of that Klarna discovered expensively, publicly, and after going to market on the claim that AI can process a question, but cannot understand why a frustrated customer is asking it. These are two different companies and two different industries deploying two completely different types of AI, but the pattern underneath is identical.

</details>

### AI与人类的协同：增强而非取代

这两个案例虽然涉及不同的公司、行业和AI类型，但其底层模式如出一辙。AI本身并非“技术故障”，失败的根源在于商业决策：将AI视为对人类判断的**完全替代**，而非**增强**。两者都未能建立冗余系统、并行测试和循序渐进的部署机制，从而在问题演变为灾难之前暴露出来。

软件工程领域的基本原则是：替换关键系统时，绝不能简单地关闭旧系统、开启新系统。正确的做法是**并行运行**（run them in parallel），将一部分流量引向新系统，同时保持旧系统运行。比较两者输出，寻找边缘案例，在真实负载下进行测试。只有当新系统在生产条件下（而非实验室条件）证明其性能与旧系统相当或更优时，才能逐步淘汰旧系统。这不是激进概念，而是任何系统故障可能带来真实后果的领域中的基本操作实践。

那些在AI部署上犯错的公司，恰恰跳过了所有这些步骤。数据表明，这并非小众问题。**Forrester**（弗雷斯特）2026年的《未来工作报告》（Future of Work report）发现，55%的雇主后悔因AI而裁员。超过一半的公司后悔用AI取代员工。相比之下，后悔纹身的人都更少。**Gartner**（高德纳）对321位客户服务领导者的调查显示，只有20%的公司真正因为AI减少了员工。绝大多数公司保持员工数量稳定，并利用AI处理与现有团队共同增加的工作量。**Gartner**预测，到2027年，50%因AI而削减客户服务员工的公司将重新招聘人员来执行类似职能。被AI取代的职位正在被“反取代”。

<details><summary>Original English Source</summary>

In both cases, the AI was not technically broken. In both cases, the failure was a business decision to use AI as a wholesale replacement for human judgment rather than an augmentation of it. And in both cases, nobody built in the redundancy, the parallel systems, the gradual testing that would have revealed the problems before they became catastrophic. If you work anywhere near software engineering, you know that when you replace a critical system, you do not simply switch off the old one and turn on the new one. You run them in parallel. You route a percentage of traffic through the new system while the old system remains operational. You compare outputs. You look for edge cases. You test under real-world load. And only after the new system has demonstrated under production condition, not lab conditions, that it performs as well or better, do you begin to decommission the old one? This is not a radical concept. It is basic operational practice in any discipline where system failure has real consequences. The companies getting AI wrong are the ones skipping all of that. And the data says this is not a niche problem, either. Forrester's 2026 Future of Work report found that 55% of employers regret laying off workers for AI. 55% more than half of companies regret replacing their workers with AI. For context, fewer people regret their tattoos. A Gartner survey of 321 customer service leaders found that only 20% had actually reduced staffing because of AI. The vast majority kept head count steady and used AI to handle increased volume alongside existing teams. And Gartner predicts that by 2027, 50% of companies that cut customer service staff for AI will rehire people to perform similar functions. The replacements are becoming unreplacements.

</details>

### 成功的AI实践：计算交给AI，判断力归于人类

**Forrester**的报告直言不讳：C级高管们往往是为AI未来的承诺而裁员，而非基于已被证实的能力，甚至是为了尚未存在的能力。真正获得回报的公司做法则大相径庭：他们利用AI提升现有团队的生产力，而非淘汰他们。

例如：
*   **Unity**每年节省130万美元，通过AI总结工单历史并处理常规请求，而未裁减任何支持人员。
*   **Hiscox**（海斯科普斯）保险团队将理赔处理时间从一小时缩短到十分钟，通过AI整理文件，最终决策仍由人工理赔员做出。
*   物流公司在调度主管的配合下，使用路线优化算法（而非取代主管），减少了18%的配送延误。AI处理计算，人类则处理当地知识、天气、路况以及临时请假的司机等突发情况。

这才是行之有效的模式：**AI处理计算，人类处理判断**（AI handles the computation, humans handle the judgment）。两者协作能达到单一系统无法实现的效果。若割裂开来，则只会得到冷掉的披萨和愤怒的顾客。

<details><summary>Original English Source</summary>

The Forrester report put it very bluntly, too often the C-suite lays workers off for the future promise of AI, not for proven capability, but for capability that does not yet exist. The companies that are actually seeing returns are doing something different. They're using AI to make their existing teams more productive, not to eliminate them. Unity saved $1.3 million annually by using AI to summarize ticket histories and deflect routine requests without cutting a single support agent. Hiscox insurance teams reduced claims processing time from an hour to 10 minutes by using AI to compile documentation for human adjusters who still made the final decisions. Logistics carriers using route optimization algorithms alongside dispatch supervisors, not instead of them, reported 18% fewer delivery delays because the technology handled the maths and the humans handled the local knowledge, the weather, the road works, the driver who calls in sick at the last minute. That is the model that works. AI handles the computation, humans handle the judgment. Together you get something neither could achieve. Separately you get cold pizza and angry customers. And

</details>

### 警惕“AI切尔诺贝利”效应：伤害整个生态

这些高调的失败案例，不仅伤害了涉事公司，更助长了公众对AI的强烈反感。它强化了“AI是企业攫取工具而非真正改进”的观点，并使得对AI施加限制性监管变得更容易。对于那些正在深思熟虑地整合AI的组织来说，这使得他们更难证明这项技术可以普遍改善所有人的结果。

那些**鲁莽的部署者**——在数千个地点强制推行未经测试的AI的公司、在技术尚未证明其能力之前就围绕取代人工员工构建IPO叙事的CEO们——他们不仅在伤害自己，也在伤害整个**AI生态系统**。他们就像那些跳过安全协议、急于启动反应堆的运营商，然后在结果破坏了公众对整个事业的信心时表现出惊讶。这又是**切尔诺贝利**事件的重演，只是这次的主角是AI。

**Yum Brands**似乎并未吸取教训。尽管**Chuck E. Cheese's**的诉讼指控**Dragontail**导致了连锁运营崩溃和1亿美元的损失，但**Yum**却同时与**Nvidia**（英伟达）合作，将更多AI部署到500家餐厅，包括用于免下车点餐的**语音AI**、实时监控员工的**计算机视觉系统**，以及为餐厅经理生成的**AI行动计划**。当被问及算法监控员工所引发的伦理问题时，**Yum**没有回应。

所有这一切都发生在**Pizza Hut**关闭250家美国门店、连续第九个季度同店销售额下降、母公司正在进行战略评估并可能考虑出售该品牌之际。**Yum Brands**在2025年仅在战略评估上就花费了3600万美元。3600万美元来弄清楚一家披萨连锁店出了什么问题？用这笔钱，你可以重新雇佣所有被**Dragontail**取代的班次经理，并给他们加薪。

因此，对于那些正在构建下一波AI部署的管理者们来说，**技术本身不是问题**。在许多情况下，这项技术绝对是了不起的。但是，一个**卓越的工具**，如果在部署时未能理解其将进入的系统、未经测试、缺乏冗余，并且**不尊重其所取代的人类判断力**，那它就不是创新，而是带着昂贵标签的**玩忽职守**（negligence）。

对于那些因为想看到AI失败而观看此视频的观众，我理解这种冲动，但这里的失败并非**人工智能**（artificial intelligence）本身。这是人类鲁莽部署的**非常人性的决策**。**“超级经理”从来不是问题，问题在于那些在不理解其将如何与现实世界互动的情况下强制推行它的真正管理者。**

<details><summary>Original English Source</summary>

here's what generally concerns me personally by the broader trajectory of all of this. Every one of these high-profile failures does not just hurt the company involved. It feeds a growing public backlash against AI as a whole. It hardens the position of people who believe AI is fundamentally a tool for corporate extraction rather than genuine improvement. It makes it politically easier to impose restrictive regulation and harder for the organizations doing thoughtful, AI integration to make the case that this technology can generally improve outcomes for everyone. The reckless deployers, the companies mandating untested AI across thousands of locations, the CEOs building IPO narratives around replacing human workers before the technology has proven it can actually do their jobs are not just harming themselves, they're harming the entire ecosystem. They are the operators who skip the safety protocols, rush the reactor online, and then act as surprised when the results undermine public confidence in the whole enterprise. It's Chernobyl all over again, except with AI. And Yum Brands, for its part, appears to have learned nothing. While Chuck E. Cheese's lawsuit alleges that Dragon Tail caused cascading operational breakdowns and $100 million in damages, Yum has simultaneously partnered with Nvidia to deploy even more AI across 500 restaurants, including voice AI for drive-thru ordering, computer vision systems designed to surveil workers in real time, and AI-generated action plans for restaurant managers. Restaurant Dive noted that Yum did not respond to questions about the ethical issues raised by algorithmic surveillance of workers. All of this while Pizza Hut is closing 250 US locations, posting its ninth consecutive quarter of same-store sale declines, and the parent company is conducting a strategic review that could lead to selling the brand entirely. They spent $36 million on that review process in 2025 alone. $36 million to figure out what went wrong at a pizza chain? For that money, you could have hired back every shift manager Dragon Tail replaced and given them each a raise. So, to the executives building the next wave of AI deployment, the technology is not the problem. The technology is, in many cases, absolutely remarkable. But, a remarkable tool deployed without understanding the system it is entering, without testing, without redundancy, without respect for the humans whose judgment it is replacing, is not innovation. It is negligence with a very expensive sticker on it. And to the audience members who came to this video because they wanted to see AI fail, I get the impulse, but the failure here was not artificial intelligence. It was the very human decision to deploy it recklessly. The super manager was never the problem. The problem was the actual managers who mandated it without understanding what it would do when it met the real world. But, Pizza Hut and Klarna are not the only ones reaching for the wrong lever. Companies across industries are doing the exact same thing, firing people in the name of AI, and the data says it's not working, either. I made a video about what the numbers actually show when companies try to replace their workforce instead of augmenting it, and why the most expensive mistake in AI right now has nothing to do with the technology. That's the one that I would watch next. Thanks so much for watching this one. Subscribe, and I'll see y'all on the next one.

</details>