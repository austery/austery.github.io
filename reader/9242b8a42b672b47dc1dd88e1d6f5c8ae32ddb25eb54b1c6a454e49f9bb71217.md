---
author: Norges Bank Investment Management
date: '2026-03-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hBGd3DCgRkM
speaker: Norges Bank Investment Management
tags:
  - ai-investment
  - autonomous-agents
  - fintech-innovation
  - productivity-boost
  - responsible-ai
title: 挪威主权财富基金的 AI 实战录：10 个案例解析金融巨头的效率革命
summary: 挪威银行投资管理公司（NBIM）在 2026 年 AI 峰会上详细披露了其全方位的 AI 转型战略。从云计算和数据清洗的基础设施建设，到涵盖投资研究、媒体监测、网络安全、法务谈判及内部对冲等 10 个具体的 AI 代理（Agents）应用案例，NBIM 展示了如何通过自主开发的工具链实现“手动流程减半”的目标，并确立了负责任 AI 的治理框架。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Nikolai Tangen
  - Sam Altman
  - Dario Amodei
companies_orgs:
  - Norges Bank Investment Management
  - OpenAI
  - Anthropic
  - Snowflake
  - Goldman Sachs
products_models:
  - Claude
  - Gemini
  - Cursor
  - Martium Core
media_books: []
status: evergreen
---
### 开场：AI 时代的“技术过剩”与透明度

**Nikolai Tangen**: 热烈欢迎参加**挪威银行（Norges Bank）**的首届 AI 研讨会。这是一个巨大的时刻，因为我们从未见过像这样的技术。它不是以直线方式移动的，它的曲线正在持续上扬，这种技术现在的能力几乎是垂直增长的。

<details>
<summary>Original English</summary>

**Nikolai Tangen**: Warm welcome to this first AI seminar at Norris Bank. And this is just a huge moment because we have never seen a technology like this. And it's moving not in a straight curve. It's continuing to curve up and it's nearly vertical what this technology can do now.

</details>

**Nikolai Tangen**: 所以现在的问题是我们所说的“**技术过剩（Technology Overhang）**”。我们能够利用所有这些技术吗？我认为最困难的部分是让组织去吸收并利用我们所拥有的技术。如你们所知，我们是世界上最透明的基金。为什么透明是件好事？因为它能让人们看到我们在做什么，从而建立信任。但同样重要的是，我们可以向外看，看看世界在做什么。

<details>
<summary>Original English</summary>

**Nikolai Tangen**: And so the issue is what we call the technology overhang. Are we able to utilize all this technology? And that is really the tough part I think is to get the organizations to absorb and to utilize what we have. So we are as you know the most transparent fund in the world. And why is transparency good? Well, I think it's good because people can look in and see what we do. And we believe that that creates trust. But I think equally important is that we can look out and see what the world is doing.

</details>

**Nikolai Tangen**: 我们的梦想是，通过公私合作，从根本上提升这个国家的**生产力**。今天我们从全公司众多的案例中挑选了 **10 个**，希望能让大家领略到我们所做事情的多样性。有些案例帮我们赚更多钱，有些帮我们省钱，有些提高效率、准确性和质量，还有一些只是防止我们做那些无聊的事情。

<details>
<summary>Original English</summary>

**Nikolai Tangen**: And I have this dream of being able that we together, you know, the private and public can basically lift productivity in this country. That's a good ambition. I think we have a lot of user cases across the firm and we could have picked uh you know many many different ones. We picked 10 which we think gives uh a kind of a taste of different things we do. Some of them help us make more money, some make us save money. Some improve efficiency. Some improves accuracy and quality and some just prevents us from doing boring stuff.

</details>

### AI 战略的基石：内包、云端与数据清洗

**Birgitte Bryne**: 自 2015 年以来，我们在 **MBIM（挪威银行投资管理公司）** 进行了多次转型，但今天我想谈谈为我们的 AI 战略奠定基础的三个主要步骤。第一步是**运营内包（Insource Operations）**。以前我们使用外部供应商负责结算、公司行动、基金会计和估值。当我们扩展到新市场时，我们想要更深厚的专业知识和更丰富的数据，所以解决方案是把这些全部收回来。我们拥有流程，我们也想拥有知识。

<details>
<summary>Original English</summary>

**Birgitte Bryne**: So we've done many transformations in MBIM since 2015 but today I want to talk about three major steps that we have done that has built the foundation for our AI strategy. So the first thing we did was to insource operations. So before that we had an external vendor that took care of settlement, corporate actions, fund accounting, valuation, everything. But when we scaled into new markets, we wanted deeper expertise and richer data. So the solution for that was to bring it all home. We own the process and we also wanted to own the knowledge.

</details>

**Birgitte Bryne**: 第二件大事是将我们所有的 IT 基础设施和系统迁移到**公共云（Public Cloud）**。此前我们租用外部数据中心，并将技术外包。但我们发现自己面临着某种“数据天花板”。而我们要的是“数据地平线”，想要按需实现瞬时扩展，并摆脱服务器更新周期的困扰。迁移后我们发现旧数据库无法满足云端的扩展要求，于是我们决定将旧数据库方案迁移到现代架构中。

<details>
<summary>Original English</summary>

**Birgitte Bryne**: So the next big thing we did was to move all our IT infrastructure, all our IT systems to public cloud. So before that we used to rent space in an external data center, outsource the technology with it. But what we saw was that we had a data uh ceiling in a way. But what we wanted was to have a data horizon. We wanted instant scale on demand and we wanted to get away from server refresh cycles.

</details>

**Nikolai Tangen**: 清洗数据有趣吗？

**Birgitte Bryne**: 一点也不有趣。

**Nikolai Tangen**: 这是有史以来最无聊的工作。有人会因为你清洗了数据而感谢你吗？

**Birgitte Bryne**: 没有。你只需要告诉他们，1 月 31 日我们要关闭旧数据，如果你第二天坐在那里发现没数据可用，你会显得非常蠢。所以全公司进行了大量的清理和代码重写工作。现在我们拥有一个统一的、高质量的内外数据存放地，专门用于 AI，它被称为 **Martium Core**。

<details>
<summary>Original English</summary>

**Nikolai Tangen**: And is it fun to clean data?
**Birgitte Bryne**: It's no fun at all.
**Nikolai Tangen**: So it's the most it's the most kind of boring job there ever is. Does anybody thank you for cleaning your data?
**Birgitte Bryne**: No. How do you get people to clean data? You basically tell them that 31st of January we are going to turn the old old data off. And if you sit there the day after and have no data, you are going to look very stupid. So we had a lot of late nights and an enormous work by the whole... that was a lot of tidy up and rewrite of code for basically everyone in the company but uh now we have one place for internal and external data with high quality and it's tidy up and it can be used for AI and it's called martium core.

</details>

### AI 转型之旅：全员赋能与习惯改变

**Stian Peersen**: 我们的 AI 之旅始于两年前，当时 Nikolai 在他的播客中邀请了 **OpenAI 的 Sam Altman** 和 **Anthropic 的 Dario Amodei**，他发现我们应该提高 20% 的效率。Nikolai 就像一个永不耗尽能量的“金霸王电池（Duracell Battery）”，在过去两年中推动着整个组织。

<details>
<summary>Original English</summary>

**Stian Peersen**: So I'll I'll take you through our AI journey and having a good data warehouse and a lot of compute in the cloud has absolutely been necessary for us to get on with the AI journey. And it all started about two years ago when Nikolai had Sam Alman from OpenAI and Dario Amodai from Antropic on his podcast and he found out we should be 20% more efficient. So um to see how he actually got that working is that him being a a battery durel battery that never goes out of the energy on the top is pushing the organization throughout the last two years and he has pushed everyone.

</details>

**Stian Peersen**: 每个人都获得了工具、时间和实验机会，但这还不够。要提高 20% 的效率，我们必须改变习惯。所以我们创建了一个**大使网络（Ambassador Network）**，由来自全公司的 20 名志愿者组成，任务是在各自团队中找到一个有价值的 AI 使用案例，并与 AI 团队及 Anthropic 合作解决。Anthropic 连续两个月每周两次为这些大使提供培训。

<details>
<summary>Original English</summary>

**Stian Peersen**: If we're going to be 20% more efficient and we're going to start using AI, we have to change our habits. So, we needed to push everyone a lot and nudge them again and again and again. So, we created a uh add upskill program for everyone. And we also created an ambassador network to help people get going here. There were 20 uh volunteers from all over the organization. They were given the task of finding the one use case in your team that you think can be a valuable project with AI... with the help of entropic. So twice a week Antropic help us get started by doing uh creating training for these ambassadors and the AI team for two months.

</details>

**Stian Peersen**: 我们还创建了名为“**Tech Year 2025**”的活动，确保无论 MBIM 发生什么，都有 AI 的参与。我们为所有人提供了 7 场每场 30 分钟的主题培训。有人喜欢“强制性”吗？他们讨厌强制，但这必须是强制性的，因为不想参加的人往往是最需要它的人。在工具方面，全公司每天都在使用 **Claude**。超过一半的员工使用 **Claude Code** 编写解决方案。本月我们引入了 **Gemini** 作为补充，已经有超过三分之二的人开始使用。

<details>
<summary>Original English</summary>

**Stian Peersen**: We trained the ambassadors but we also had to train the rest of the organization. So we've created seven 30 minute sessions with different topics... and this was mandatory. Now do people like mandatory? They hate mandatory... It has to be mandatory and you have to be on them like a wasp. Everyone in NBIM is using cloud on a daily basis. With cloud comes cloud code and more than half of the employees are using cloud code to create solution. We just got Gemini this month uh to complement claude and already uh more than twothirds have signed on and started using it.

</details>

### 负责任的 AI 框架与合规治理

**Lydia Toisuta**: 基金充分意识到确保 AI 负责任使用的重要性，因此我们构建了**负责任 AI 框架（Responsible AI Framework）**。首先，我们制定了准则，为每位员工在购买、构建或使用 AI 时设定要求。该准则与欧盟 **AI 法案（EU AI Act）**及全球认可的标准保持一致，涵盖了数据保护以及在涉及投资或人事决策的 AI 系统中保持**人类参与（Human Involvement）**等核心领域。

<details>
<summary>Original English</summary>

**Lydia Toisuta**: Now, at the fund, we're fully aware of the importance of ensuring the AI we use is always done responsibly. And that's why we've built a responsible AI framework. So, first we make the rules. Our responsible AI guideline sets requirements for every employee when we're buying, building, or using AI. The guideline aligns with law like the EU AI act as well as globally recognized AI standards. It addresses some key areas like protecting people's data and ensuring human involvement in all AI systems that help with investments or people related decisions.

</details>

**Lydia Toisuta**: 我们采取的是**基于风险的方法（Risk-based approach）**。处理简单的邮件过滤系统和处理影响人的 AI 系统的方式完全不同。我们的**运营模式（Operating Model）**将准则转化为具体的治理结构，并在中心设立了 **AI 治理工作组**。该小组由各关键团队代表组成，确保负责任 AI 不仅仅是口头说说，而是付诸实践。

<details>
<summary>Original English</summary>

**Lydia Toisuta**: Now the guideline takes a riskbased approach. That means the way we would handle a simple email filtering system is completely different to the way we would handle an AI system that impacts people. Our operating model... sets out key processes that we all need to follow from the development of an AI system all the way through to deployment and beyond. Now, at the very center of this governance structure, we have our AI governance working group.

</details>

### 十大案例展示

**Trond Grande**: 我们最近发布的战略计划中，在每个职能部门都多次提到了 AI。一个大胆的目标是：到 2028 年底，将所有**手动流程削减一半**。下面我们将以每三分钟一个的速度展示 10 个不同的使用案例。

<details>
<summary>Original English</summary>

**Trond Grande**: In our recently released uh strategy plan uh we mention AI a lot across every function... This is just one example of a pretty bold ambition if you ask me to cut all our manual processes in half by the end of 2028. So we'll take you through in rapid succession uh 10 different use cases three minutes each.

</details>

#### 案例 1：投资助理代理网络

**Ola Peter Gjessing**: 想象一下高盛联系你，法拉利的最大股东想出售价值 300 亿克朗的股票。他们需要你在一小时内给出答复：买不买？买多少？什么价格？我们每年会接到约 200 个这样的请求。挑战在于时间极短且数据分散在各处。我们无法仅通过代码或语言模型解决，于是我们构建了 **AI 代理（Agents）**。一个代理负责网页搜索股东背景，另一个提取交易文本关键数据，第三个运行算法计算指数效应。这让我们可以花更少的时间收集数据，花更多的时间进行分析。

<details>
<summary>Original English</summary>

**Ola Peter Gjessing**: Imagine being contacted by Goldman Sachs. Ferrari's largest shelder, wants to sell shares worth 30 billion corners. They need an answer within one hour. Would you buy? In our team, we get about 200 these requests every year. The challenge is that we have very little time and the data is everywhere. We need both [code and LLM]. So we built agents, specialized AI programs with dedicated tasks and tools working together. When Goldman calls we spend less time gathering all data more time analyzing it which leads to better decisions that we make more money.

</details>

#### 案例 2：媒体情绪监测系统 "Echo"

**Safraz Farooq**: **Echo** 是我们所有沟通活动的实时概览。去年，基金在近 50,000 篇报道中被提及。对于只有两人的新闻团队来说，追踪这一切是不可能的。所以我们构建了 AI 驱动的情绪分析系统。每篇文章都会通过主代理分发给专门的子代理，对情绪、媒体优先级、报道类型和涉及话题进行分类。数据直接存储在 **Snowflake** 仓库中。我们还建立了一个聊天机器人，可以直接通过对话生成跨渠道的分析报告。

<details>
<summary>Original English</summary>

**Safraz Farooq**: Echo is a live overview of all of our communications activities across channels. In 2025, the fund was mentioned in almost 50,000 articles. That's why we built an AI powered sentiment analysis to help us do exactly that. So, this is an agent-based system where each article goes through a main agent that delegates to specialized sub agents... All of this data is stored directly into our data warehouse, Snowflake. Lastly, we built a chatbot sitting on top of Echo... Instead of digging through the dashboard, we can simply ask.

</details>

#### 案例 3：网络安全自动化分类

**Geir Arild Tierland**: 我们每年收集约一万亿个关于 MBIM 运营的数据点。从中我们会筛选出约 10 万到 100 万件可能存疑的事件。例如，员工访问了有风险的足球直播网站。过去我可能在半夜被叫醒，花半小时去构建整个故事背景。现在我们有一个 **AI 代理**会在我下床的同时立即开始工作，执行相同的判断过程。它能在 5 分钟内完成我过去半小时的工作，而且它永远不会偷懒。

<details>
<summary>Original English</summary>

**Geir Arild Tierland**: We collect roughly a trillion data points about MBIM and MBIM's operation throughout the year. And then from those trillion, we surface down maybe somewhere in the range of a million to 100,000 things that might be considered suspicious. While I'm rolling out of bed uh this agent has started working immediately and it does the exact same process. It produces uh a report... which is very similar to what I would do. It does what would have taken me roughly half an hour in in 5 minutes.

</details>

#### 案例 4：公司会议模拟与准备

**Christina Wiggen**: 2025 年 MBIM 举行了 3,000 多场公司会议，每场准备需 3 小时，一年就是 **10,000 小时**。我们训练了一个多代理系统，加载投资假设和会议记录。一个代理制定计划，三到五个子代理研究不同来源，最后由一个在我们的最佳会议案例和访谈技巧上训练过的代理评估输出。我们即将加入**模拟组件**，利用播客和历史记录预测对方的反应，甚至可以通过语音对语音进行实战演练。

<details>
<summary>Original English</summary>

**Christina Wiggen**: In 2025, MBIM held more than 3,000 company meetings. Each of these meetings take about 3 hours to prepare. So this is nearly 10,000 hours every year. The model loads data that only we have access to... one agent builds a plan. Then three to five sub aents go out and research... A final agent has been trained on our very best meeting prep examples. We'll soon add a simulation component. This will use podcasts, part past meetings... to predict what the counterpart is likely to tell you.

</details>

#### 案例 5：市场监控代理 "Eva"

**Oscar Bathen**: 市场诚信至关重要。我们在 2018 年选择了一个外部系统，它会弹出合规团队需要调查的警报。但该系统不了解 MBIM 的背景（例如是否是指数再平衡）。现在我们引入了 **AI 监控团队**，由 6 个子代理组成，分别专注于交易背景、行业新闻、互动模式等。它们向主代理 **Eva** 汇报，Eva 始终在线并完成完整的审计追踪。只有在真正模糊、无法自动化判断的情况下，她才会转交给人类。

<details>
<summary>Original English</summary>

**Oscar Bathen**: Traditionally relying on the sell side banks... MBIM selected an external system in uh 2018. But this system, it doesn't know MBIM. Introducing our AI surveillance team. Uh we have six sub agents that are each reviewing all alerts... They all feed into a master agent which we call our enhanced vigilant agent or Eva. Uh she's always on, completes a full audit trail.

</details>

#### 案例 6：取证会计与“财务粉饰”检测

**Martin Kulsrud**: 我们的基准指数包含约 7,000 家公司，挑战在于剔除其中的“坏苹果”。每个分析师原本需要两周深挖一家公司的财报。现在我们训练机器去识别“**财务粉饰（Financial Makeup）**”。例如寻找特定关键词，如“应付账款延长”，AI 会自动提取前后几页的相关句子和数值。我们拥有独特的内部数据集，记录了历史上所有财务暴雷案例，并训练机器学习模型来预测一家公司演变成类似案例的百分比概率。

<details>
<summary>Original English</summary>

**Martin Kulsrud**: The challenge is to remove the bad apples from the fund. What we need to do is to remove the financial makeup that uh makes these companies look better than they really are. So we're making many different kinds of agents that is uh trying to spot this kind of financial makeup. We have made inhouse quite a unique data set where we have gone through every forensic accounting research shop and gotten all of their historic cases. The output of the model is uh the percentage likelihood that a company is going to develop into such a forensic accounting case.

</details>

#### 案例 7：自动财务报告生成

**Torjus Gylstorff**: 每个季度生成财务报表是一个资源密集型的过程，涉及复杂的 Excel 和手动调整。我们的两人团队（非开发人员）利用 **Claude Code** 和 **Cursor** 从底层会计数据重构了流程。现在，FX 和税收分析在第 2 个工作日通过按键即可完成，而原本需要全职工作一周生成的“附注 14”现在仅需几小时。2025 年年报中的**附注 4** 和**附注 11** 已经是由 AI 自动生成的了。

<details>
<summary>Original English</summary>

**Torjus Gylstorff**: Every quarter we produce NBIM's financial statements... resource intensive. Think complex Excel workbooks. Our team of two are not developers. So we use cloud code and cursor to write the code. FX and tax at the push of a button on business day 2. Note 14... one person spent one full week producing this note. Now, it's done in only a couple of hours. AI enabled us to automatically produce note four... and notes 11... in the annual report 2025.

</details>

#### 案例 8：ESG 风险大规模筛选

**Christina Wiggen**: 作为负责任的投资者，我们需要筛查 7,000 多家公司是否涉及强迫劳动或森林砍伐。如果由人工完成，估计需要 3,000 名分析师工作一整个周末，而我们的团队只有 8 个人。现在的系统分两阶段：第一阶段用轻量模型快速筛查，发现迹象后触发第二阶段。在第二阶段，多个 AI 代理从不同角度研究（如供应链、财务关系等），汇总后由人类分析师做出最终决策。

<details>
<summary>Original English</summary>

**Christina Wiggen**: As a responsible investor, we need to know whether any of these companies are linked to serious issues... child labor, deforestation... If a human analyst were to do that, we estimate we would need 3,000 analysts working an entire weekend and our team is only eight people. The screening process runs in two phases. Phase two, we deploy multiple AI agents, each responsible for researching the company from a different angle.

</details>

#### 案例 9：谈判模拟器

**Kirsty MacGillivray**: 我创建了一个**谈判模拟器**。在规划模式下，它可以预测对方 80% 的论点，帮助我们更快制定策略。在**语音模式**下，我可以在无风险的环境中模拟实时谈判，甚至可以交换角色，看看 AI 坐在我的位子上会如何处理。我们还在规模化处理合同组合，利用 AI 寻找条款模式，例如分析不可抗力条款在不同场景下的综合影响，提取能增加真实价值的战略信息。

<details>
<summary>Original English</summary>

**Kirsty MacGillivray**: If AI can model language patterns, then it can model negotiation patterns. So, I created the negotiation simulator. We're able to predict over 80% of the arguments. Simulation is what sets this apart. In voice mode, I can simulate a live negotiation in a risk-free environment. I can even switch roles to see how AI would handle the situation if it were sitting in my seat.

</details>

#### 案例 10：内部对冲与市场冲击管理

**Yngve**: 随着基金规模的增长，我们成了自己在市场上的“最强劲对手”。由于买卖量巨大，我们的“**市场冲击（Market Impact）**”成本去年估计达 140 亿克朗。AI 帮助我们通过预测市场走势来建立“耐心”：如果预测股票会下跌，买入时可以不必急于求成。更重要的是，AI 帮助我们管理内部 250 个组合之间的相反订单。去年我们在内部对冲了超过 1,200 亿克朗的资金，完全无需进入市场，节省了约 40 到 60 亿克朗的成本。

<details>
<summary>Original English</summary>

**Yngve**: We are now in a place where we ourselves become our own worst enemy in the market. This footprint in the market, this market impact as we call it, we estimated last year to 14 billion of region. AI helps us find patterns in the market and give us probabilities... predictions build patience. Another thing we can do is to look at all the internal portfolios. Last year we parked [internally crossed] more than 120 billion and we don't go to the market. We have saved four, five, maybe even six billion croners in the way we trade for the fund.

</details>