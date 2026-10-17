---
author: a16z
date: '2026-09-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=K5yGLO8c6T0
speaker: a16z
tags:
  - customer-relationship-management
  - world-model
  - autonomous-agent
  - enterprise-software
  - startup-pivot
title: 从2000万用户的AI明星产品到硬核企业级转型：Lightfield如何构建AI原生商业世界模型重塑CRM
summary: 本期对话Lightfield创始人Keith Peiris，深度复盘其从现象级AI演示文稿产品Tome向企业级AI CRM（商业世界模型）的艰难硬核转型。探讨了传统CRM对现实商业数据的严重失真、AI智能体对统一业务事实真相的底层依赖，以及如何将邮件、通话与会议等非结构化交互沉淀为驱动AI自主行动的高保真世界模型。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Lightfield
  - a16z
  - Tome
  - Facebook
  - Instagram
products_models:
  - Lightfield
  - Tome
  - GPT-3
  - GPT-4
  - Salesforce
media_books: []
status: evergreen
---
### 序言与精彩亮点

**Keith Peiris**: 我们五位创始团队成员中有三位来自 **Facebook**。构建收入与销售团队是一个极其丰富且充满挑战的课题，也是所有人都在意的事情，而且这项工作永远都有改进空间。

<details>
<summary>Original English</summary>

**Keith Peiris**: Three out of our five founding members came from Facebook. Building a revenue team is a very rich problem set. It's something that everyone cares about. It could always be done better.

</details>

**Joe Schmidt**: 目前有人用 **Lightfield** 做过的最令人兴奋的事情是什么？

<details>
<summary>Original English</summary>

**Joe Schmidt**: What's the most exciting thing someone's doing with Lightfield today?

</details>

**Keith Peiris**: 有一家名为 **Power** 的公司，他们搭建了一个患者撮合平台，聚集了大量患有各种复杂疾病、正在寻找前沿疗法的患者。他们把所有这些复杂的业务与患者匹配流程都建模在 **Lightfield** 中。**Lightfield** 实际上在几天之内就帮助一位阿尔茨海默病患者找到了前沿临床治疗方案。

<details>
<summary>Original English</summary>

**Keith Peiris**: This company Power, they have this marketplace where they're aggregating folks that have various illnesses and complications that are looking for frontier treatment. So, they've modeled all of this in Lightfield and Lightfield actually helped someone with Alzheimer's find frontier treatment within days.

</details>

**Joe Schmidt**: 在这个人工智能时代，你们在做法上有什么与众不同的地方吗？

<details>
<summary>Original English</summary>

**Joe Schmidt**: Is there anything that you've done differently in this kind of AI era?

</details>

**Keith Peiris**: 作为一家身处红海赛道的 **CRM** 公司，我们必须成为一家依靠网络效应持续扩张的公司。如果我们能帮助你完整地建模你的商业逻辑和客户业务现实，那么剩下的事情就水到渠成了。

<details>
<summary>Original English</summary>

**Keith Peiris**: As a CRM company in a red ocean space, we have to be an expansion company. If we can help you completely model your business and your customer reality, then the rest will be easy.

</details>

**Alex Rampell**: 如果你能回到刚开始创业的时候，你会给自己哪一条核心建议？

<details>
<summary>Original English</summary>

**Alex Rampell**: What would be the one piece of advice that you'd go back and give yourself if you are just starting again?

</details>

### 开篇介绍与嘉宾背景

**Joe Schmidt**: 欢迎回到 **a16z Podcast**。我是 **Joe Schmidt**，今天和我一起主持的是我的合伙人 **Alex Rampell** 以及我们的嘉宾 **Keith Peiris**。Keith 是 **Lightfield** 的 CEO。Lightfield 刚刚完成了由我们领投的 **4700 万美元 A 轮融资**，他们正在构建一个**商业世界模型**（Business World Model）。

所谓的商业世界模型，就是将客户的电子邮件、电话通话以及会议记录转化为一个高度精准的系统记录，供 **AI 智能体**（AI Agents）调用以完成实际工作。在今天的播客中，我们将深入探讨 Keith 极其引人注目的战略转型历程、他们是如何打造出这款初期产品的，以及客户可以用它做些什么。Keith，非常感谢你的加入！

<details>
<summary>Original English</summary>

**Joe Schmidt**: Welcome back to the a16z podcast. I'm Joe Schmidt. I'm joined by my partner, Alex Rampell, and Keith Peiris. Keith is the CEO at Lightfield. Lightfield just raised a $47 million Series A led by us, and they're building a business world model. A business world model turns customer emails, calls, and meetings into a record that AI agents can use to get work done. We'll explore how Keith pivoted, which is very interesting, to Lightfield, how they built the initial product, and what customers can do with it. Keith, thanks for joining us.

</details>

**Keith Peiris**: 非常高兴能来到这里。

<details>
<summary>Original English</summary>

**Keith Peiris**: Excited to be here.

</details>

### 从 Tome 的爆发式增长到硬核转型

**Joe Schmidt**: 或许我们可以先回顾一下你打造 **Tome** 的历程，以及你最终是如何转型到 **Lightfield** 的。这是一段非常不同寻常的旅程。你现在已经让两款产品都实现了爆发式的增长。能跟我们讲讲这段经历，以及你最终是如何创立 Lightfield 的吗？

<details>
<summary>Original English</summary>

**Joe Schmidt**: Yeah, maybe we'll start just going back to the Tome journey and how you got to Lightfield. Very atypical journey. You got two products now to explosive scale. Tell us a little bit about that experience and how you ended up at Lightfield.

</details>

**Keith Peiris**: 我们最早创办 Tome，主要是因为我们团队大多具有 **C 端消费级产品**（Consumer）的基因。当时我们坚信大语言模型（LLM）将彻底改变人们的沟通方式。此前我们在 **Instagram** 和 **Messenger** 从事自拍滤镜与富媒体设计等相关工作，因此我们决定进军“想法的叙事表达”（Storytelling of Ideas）领域。我们在 **GPT-3** 发布的时期推出了这款产品。

<details>
<summary>Original English</summary>

**Keith Peiris**: We started Tome mostly because we were consumer people and we thought like LLMs were going to change the way people communicate, and we were working on selfie design at Instagram and Messenger, and we decided to go into the storytelling of ideas. We got this product out to launch around the time of GPT-3.

</details>

**Alex Rampell**: 是的，能再详细介绍一下那款产品吗？它是一款演示文稿（Presentation）工具，用户只要输入一个提示词，它就能自动生成完整的幻灯片，对吧？

<details>
<summary>Original English</summary>

**Alex Rampell**: Yeah. And tell us a little bit about the product too. So it was a presentation product where you type in a prompt and it creates a presentation, right?

</details>

**Keith Peiris**: 没错。你只要输入一段提示词，它就会为你生成一份完整的幻灯片。它迅速引起了病毒式传播，我们在短短大约一年的时间里就获得了 **2000 万用户**。

<details>
<summary>Original English</summary>

**Keith Peiris**: Exactly. You'd type in a prompt, and it would generate a presentation for you. It went viral, and we grew to 20 million users in about a year.

</details>

**Alex Rampell**: 天哪，这太不可思议了！然而在实现了如此巨大的规模之后，你却做出了停下来并进行彻底“硬核战略转型”（Hard Pivot）的决定。当时的决策过程是怎样的？你是如何做出这个选择的？背后的原因是什么？

<details>
<summary>Original English</summary>

**Alex Rampell**: Wow. Oh my gosh. And so you got that to amazing scale. You then decided to stop and completely hard pivot. What was that decision like? How did you make that choice? Why?

</details>

**Keith Peiris**: 这确实是一个极其艰难的决定。当时每个月都有数以百万计的人在使用这款产品，从表面数据来看，一切指标都显得非常光鲜亮丽。但如果你深入探究商业模式的底层逻辑，就会发现问题：虽然我们拥有海量的个人用户，但由于产品形态定位于轻量级的演示文稿生成，**付费转化率与长期留存率**（Retention）并没有达到构建一家能够基业长青的百亿美元企业级软件公司所必需的标准。

我们意识到，许多人只是出于新奇感来体验 AI 生成幻灯片，而企业客户真正愿意持续买单并深度依赖的，是直接嵌入其核心业务流程、能解决不可替代商业痛点的系统。我们不想沉迷于虚荣的流量指标，而是希望打造具有极高技术壁垒和不可替代价值的企业级平台。于是，我们决定主动打破现状，彻底转型。

<details>
<summary>Original English</summary>

**Keith Peiris**: It was an incredibly tough decision. You have millions of people using the product every month, and all the vanity metrics look amazing. But when you look at the fundamental unit economics and retention, people were using it for novelty rather than mission-critical business workflows. We realized that generating slides is cool, but it's not where durable enterprise value is captured. We wanted to build a foundational, multi-billion dollar enterprise software company that transforms core business operations, not just a viral consumer-tier tool. So we had the courage to stop, reset, and pivot completely to where the real problem lay.

</details>

### 传统 CRM 的困境与商业世界模型的诞生

**Joe Schmidt**: 这确实需要极大的魄力。那么你是如何从那个节点走到 **Lightfield**，并决定重新发明 **CRM** 的？

<details>
<summary>Original English</summary>

**Joe Schmidt**: That takes tremendous courage. So how did you make the leap from there to Lightfield and deciding to reinvent CRM?

</details>

**Keith Peiris**: 当我们退后一步审视现代企业运作时，我们发现所有企业最核心的瓶颈都在于**客户关系与收入引擎**（GTM / Revenue Engine）。然而，现有的传统 CRM 系统本质上只是一个死板的**关系型数据库表单**。

在传统 CRM 中，销售代表每天需要花费大量时间手动输入联系人、商机阶段、跟进记录和备注。现实中发生的绝大多数商业活动——真实的往返邮件、销售电话中的细微对话、Zoom 会议上的客户诉求、合同条款的反复推敲——全都被丢弃在系统之外，或者被高度抽象成几句毫无营养的手动填报。这导致所谓的 CRM 数据库与真实的商业世界严重脱节。

如果我们能够利用大模型的能力，自动捕获所有非结构化交互数据（邮件、通话录音、会议纪要、即时消息），并将其构建为一个**实时动态更新的高保真商业世界模型**，那么企业就拥有了唯一的**事实真相来源**（Single Source of Truth）。

<details>
<summary>Original English</summary>

**Keith Peiris**: When we stepped back and looked at how modern companies operate, the core bottleneck is always the revenue engine. But existing legacy CRMs are essentially just rigid relational database forms. Sales reps spend hours manually typing in fields, notes, and stages. Most of the real business reality—the actual emails, nuanced phone conversations, Zoom meetings, pricing pushback—gets completely lost or reduced to shallow summaries. The CRM becomes detached from reality. We realized if we could use modern LLMs to capture all unstructured interactions and continuously construct a high-fidelity 'business world model', companies would finally have a true single source of truth.

</details>

**Alex Rampell**: 也就是说，传统 CRM 强迫人类把真实世界的复杂动态降维压缩成静态字段，而 Lightfield 则是直接理解和容纳真实世界。

<details>
<summary>Original English</summary>

**Alex Rampell**: In other words, traditional CRMs force humans to lossy-compress real-world dynamics into static fields, whereas Lightfield natively ingests and understands the real world.

</details>

**Keith Peiris**: 完全正确。**人类不应该做数据录入员**。人类擅长的是建立人际信任、进行复杂谈判和战略决策。而让系统自动从每一次交互中提取结构化事实、自动更新业务状态，并为 AI 智能体提供行动依据，这就是商业世界模型的精髓所在。

<details>
<summary>Original English</summary>

**Keith Peiris**: Exactly right. Humans should not be data entry clerks. Humans are great at building trust, complex negotiations, and high-level strategy. Having a system that automatically extracts structured facts from every interaction, maintains state, and equips AI agents to take action—that is the essence of a business world model.

</details>

### AI 智能体与真实业务落地场景

**Joe Schmidt**: 你们是如何让 **AI 智能体**（AI Agents）在这样一个世界模型之上发挥作用的？能分享一些具体的客户使用案例吗？

<details>
<summary>Original English</summary>

**Joe Schmidt**: How do AI agents actually operate on top of this world model? Can you share some concrete customer examples?

</details>

**Keith Peiris**: 很多团队试图直接让 AI 智能体去给客户写邮件或自动跟进，但往往效果很差，甚至出现灾难性的幻觉，原因就在于**智能体缺乏上下文**。如果你给智能体的输入只是传统 CRM 里的几个标签，智能体根本不知道这位客户两周前抱怨过什么、预算审批卡在哪个部门、或者他们内部的政治结构是怎样的。

但在 **Lightfield** 中，因为拥有完整的商业世界模型，智能体在起草邮件、准备会议简报或推进交易时，能够调取关于该客户的全部历史脉络与真实细节。

举个例子，正如我前面提到的医疗平台 **Power**，他们需要对接重症患者与临床试验项目。这其中涉及到患者复杂的病史、地理位置、纳入排除标准以及与各大研究机构的协调。以往销售和运营人员需要极其繁琐地在多套系统和表格中手动核对。而在使用 Lightfield 后，系统自动构建了包含患者需求和临床试验条件的完整图谱，智能体能够秒级完成精准匹配，让一位阿尔茨海默病患者在几天内就匹配并接入了前沿治疗项目。

<details>
<summary>Original English</summary>

**Keith Peiris**: Many teams try to have AI agents write emails or automate follow-ups, but they fail or hallucinate because the agents lack deep context. If the agent only sees a few superficial CRM tags, it doesn't know what the customer complained about two weeks ago, where the budget is stuck, or what the internal org dynamics look like. But in Lightfield, because we maintain the full business world model, an agent drafting an email or preparing a deal review has access to the full narrative context. In the case of Power, matching clinical trial patients with cutting-edge treatments involves complex medical histories, inclusion criteria, and hospital logistics. Lightfield automatically modeled that entire reality, allowing agents and coordinators to match an Alzheimer's patient to a frontier clinical trial in days.

</details>

**Alex Rampell**: 这在传统 CRM 中几乎是不可能做到的，因为如果要支持这种高度定制化且动态变化的业务逻辑，传统做法需要雇佣一大批 Salesforce 顾问去编写复杂的自定义对象、触发器和 Apex 代码，耗资数百万美元且极易损坏。

<details>
<summary>Original English</summary>

**Alex Rampell**: That's nearly impossible in a traditional CRM without spending millions of dollars hiring Salesforce consultants to write custom objects, triggers, and fragile custom code.

</details>

**Keith Peiris**: 没错。在传统模式下，企业的软件架构永远落后于其实际业务变化；而在 Lightfield 中，系统会随着真实的交互自动演进其对业务的理解。

<details>
<summary>Original English</summary>

**Keith Peiris**: Exactly. In the legacy world, your software architecture is always lagging behind your actual business changes. In Lightfield, the system continuously updates its understanding of your business as interactions naturally occur.

</details>

### 产品构建哲学与红海突围策略

**Joe Schmidt**: CRM 领域被很多人视为一个经典的“红海”市场（Red Ocean），巨头林立。作为一家初创公司，你们是如何思考自身的护城河与扩张策略的？

<details>
<summary>Original English</summary>

**Joe Schmidt**: CRM is often viewed as a classic red ocean market dominated by entrenched incumbents. As a startup, how do you think about your moat and expansion strategy?

</details>

**Keith Peiris**: 在红海市场中，你绝不能只做一个“界面更好看”或“加了一点 AI 包装”的平替产品（Wrapper）。如果你只是做增量改进，巨头凭借分发渠道很快就能碾压你。

我们认为突围的核心在于成为一家**自驱动扩张型公司**（Expansion Company）。我们从最底层重新定义了数据模型与交互范式。传统 CRM 关注的是**记录状态**（System of Record for Status），而 Lightfield 构建的是**行动与智能的操作系统**（System of Action and Intelligence）。

企业一旦将客户所有的真实沟通数据沉淀在 Lightfield 的世界模型中，其所获得的智能体自动化能力、交易预测精度以及跨部门协同效率，将呈现出指数级的网络效应。这种飞轮效应会让客户越用越离不开，从而实现从单个团队切入，迅速向整家企业的各个部门自主蔓延与扩张。

<details>
<summary>Original English</summary>

**Keith Peiris**: In a red ocean, you cannot win by just being a prettier UI or a thin AI wrapper. If you're doing incremental tweaks, incumbents will crush you with distribution. You have to be an expansion company from the ground up. We redefined the underlying data model. Traditional CRMs are passive systems of record for vanity statuses. Lightfield is a dynamic system of action and intelligence. Once a company's raw interaction reality is captured in our world model, the automation power, deal intelligence, and cross-functional speed compound exponentially. That creates a massive retention flywheel that naturally expands across the entire enterprise.

</details>

### 创始人的心路历程与创业反思

**Alex Rampell**: 回顾你带领团队经历 Tome 的狂飙突进，再到果断清零并创立 Lightfield，如果让你给刚开始创业时的自己一条最重要的建议，你会说什么？

<details>
<summary>Original English</summary>

**Alex Rampell**: Looking back at the meteoric rise of Tome, followed by the bold decision to reset and build Lightfield, what is the single most important piece of advice you'd give yourself if you were starting over?

</details>

**Keith Peiris**: 我会告诉自己：**戴上眼罩，屏蔽一切噪音，极度专注于最核心的本质价值**（Put the blinders on and focus purely on the core）。

在 AI 时代，市场充斥着各种热点、炒作周期、估值泡沫以及表面繁荣的虚荣指标。许多东西可能会在短时间内迅速被重新定价。但诚实地说，这一切都不重要。作为创始人，你必须看穿喧嚣，始终问自己：我们是否在为客户解决真实世界中最坚硬、最核心的痛点？我们构建的技术是否具有不可替代的长期价值？只要你全神贯注于核心业务真相，其余的一切自然会迎刃而解。

<details>
<summary>Original English</summary>

**Keith Peiris**: I would tell myself: put the blinders on, ignore all the surrounding noise, and relentlessly focus on the core fundamental value. In this AI wave, there are endless hype cycles, fleeting trends, and valuation repricing. Honestly, none of that matters. As a founder, you have to look past the vanity metrics and ask: are we solving the hardest, most mission-critical problem for our customers? Is what we are building fundamentally defensible? If you stay laser-focused on the core truth of the business, everything else takes care of itself.

</details>

### 结语

**Joe Schmidt**: Keith，我们对你所做的一切、你所建立的业务以及这款卓越的产品感到无比钦佩。如果你还没有体验过，一定要去尝试一下。欢迎大家访问 **lightfield.app** 查看体验。Keith，非常荣幸能与你携手共事，我们对未来的前景感到无比兴奋！

<details>
<summary>Original English</summary>

**Joe Schmidt**: Keith, we could not be more impressed with what you've done, the business you've built, and the product is absolutely incredible. If you haven't tried it, you need to try it. Go check it out at lightfield.app. Keith, it's an absolute pleasure to work with you and we're so excited for the future. Thanks for the honor.

</details>

**Keith Peiris**: 非常感谢你们邀请我来！

<details>
<summary>Original English</summary>

**Keith Peiris**: Thanks for having me.

</details>

**Alex Rampell**: 谢谢你，Keith！

<details>
<summary>Original English</summary>

**Alex Rampell**: Yeah. Thanks, Keith.

</details>