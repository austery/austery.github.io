---
author: Latent Space
date: '2026-06-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=cFNI2FORAc0
speaker: Latent Space
tags:
  - ai-ecosystem
  - agentic-workflow
  - token-economy
  - platform-strategy
  - ai-infrastructure
title: 萨提亚·纳德拉：定义 AI 时代的生态系统与元认知生产力
summary: 微软 CEO 萨提亚·纳德拉深入探讨了 AI 平台的本质演进，强调从单一模型向“生态系统”协作的转变。他提出了企业级“治理架构（Harness）”、私有评估体系（Private Eval）以及“元认知（Meta-work）”等核心概念，并分享了微软在 SaaS 模型重组、自动化运维及 AI 社会契约方面的深度战略思考。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Satya Nadella
  - Mustafa Suleyman
  - Jensen Huang
companies_orgs:
  - Microsoft
  - OpenAI
  - GitHub
  - LinkedIn
products_models:
  - Azure
  - GitHub Copilot
  - Microsoft 365
  - MAI-1
media_books: []
status: evergreen
---
### 平台演进：从单一模型到生态系统协作

在微软的发展历程中，**平台（Platform）**的定义始终在于其创造价值的能力——即平台外部所创造的价值必须远大于平台本身捕获的价值。纳德拉指出，当前的 AI 浪潮不应被视为单一模型或单一平台的孤立竞争，而是一场**生态系统博弈（Ecosystem Play）**。微软的目标是为所有企业（无论是原生 AI 初创公司还是传统巨头）提供一套完整的“配方”，涵盖技术栈、工具链和方法论，让他们能作为一等公民参与其中，并指着这些成果说：“这是我们创造的 AI”。这种转变意味着微软的角色是构建基础设施，让开发者能够定义自己的 AI 路径，而不仅仅是消费他人的技术成果。

<details>
<summary>Original English Source</summary>

I would say there are perhaps the biggest one for me is let's sort of conceptualize this more as an ecosystem play as opposed to a single model or even a single platform right I mean you know whenever I at least for me having grown up at Microsoft having seen whatever four major platform shifts u I sort of fall into that um camp where a platform is defined by fundamentally its ability to create more value about the platform versus what's captured in the platform. And so if you you view what's happening right now, I think this morning's keynote was how can any company whether it's an AI native company or a traditional enterprise company participate as a firstass participant where they can point to AI they created. Right? It's not that they don't use other people's AI. Of course they will. But to me, what's the path? What's the recipe? How do I do it? What does a stack look like? What does the tooling look like? What is valuable? How do you do that? That's it. That's sort of our job to do.

</details>

### 寻找认知核心：MAI 模型与爬坡脚手架

在模型训练策略上，微软追求的是寻找**认知核心（Cognitive Core）**。纳德拉强调了构建清晰血统（Lineage）模型的重要性，这需要极其高质量的数据预处理和消融实验。他批评许多开源模型虽然在特定基准测试中表现出色，但在实际应用中却不尽如人意。微软的策略是为企业提供一个**爬坡脚手架（Hill Climbing Scaffold）**：企业不应仅将模型视为通才工具，而应通过收集自身的交互踪迹（Traces）、构建**私有评估体系（Private Eval）**，在通才基础上培养自己的“专家级”能力。这种端到端的平台叙事，让企业能够通过持续的反馈循环，在私有语境下实现能力的阶梯式提升。

<details>
<summary>Original English Source</summary>

So, so the thing that we wanted to do with the MAI models was to build and as Mustafa talked about first of all a great lineage right starting with pre-training uh with very good data quality uh doing all the abilations making sure because in in some sense it's become even harder to build a clean lineage model just because there's so much stuff out there um that you truly need to ablate out to be able to have a fantastic pre-trained model. In fact, that's one of the challenges of a lot of the open rate models is they look great on one benchmark or two, but they're not great on practice. So, that's why in fact even in our FDES are are pretty gone really excited about these MAI models because how the heck can a small 5D model hill climb? uh and it goes back a little bit to what I think is ultimately the key thing to do which is try to pursue finding that cognitive core. Uh so to me starting with with a clean lineage then creating that ability for companies to be able to use this right not just as a generalist but to create their own specialist by building this hill climbing scaffold around it right so it's not just the model but you have a hill climb scaffold around it then you will start building your rle you will start collecting the traces most importantly you'll have private eval because we know all the eval out there are good, interesting, but they're not really that critical at this point because they all can be maxed. And so the point is each company will have its own private eval. And so that end to end platform story around our models is sort of uh what I think is interesting.

</details>

### 真实世界的复杂性：超越“智能即算力对数”

回顾过去两三年的跨越，纳德拉坦言，虽然**缩放法则（Scaling Laws）**——即“智能是算力投入的对数函数”——在大方向上是成立的，但行业低估了将这些模型部署到现实世界并交付价值的复杂性。真正的评估标准（True Eval）不是基准测试，而是用户能否完成那些过去无法想象的独特任务。他认为行业目前对“Token 成本”的过分焦虑，其实是因为我们还没有意识到如何通过 Token 在每一步流程中创造价值。这种认知的滞后阻碍了更深度的集成，而现在的关键是将意识从简单的“最大化 Token 输出”转向“通过 Token 驱动现实世界成果”。

<details>
<summary>Original English Source</summary>

I mean I think the the thing when that I reflect quite a bit, right, which is sort of obviously I got into all this when I got excited by the the scaling laws paper and you know when you know even the open AI partnership came about when those folks said hey we're going to really throw a lot of computer transformers uh and they've helped right the thing that I always look back and say wow these things um do have capability that they're climbing up I mean this you know this crude way of saying it is intelligence is log of comput kind of works. Now what I think we underestimated perhaps is the real world complexity of deploying these so that they actually deliver the value in the real world. Right? So the outcomes as measured by any benchmark is interesting important but the true eval is when people out there are able to do unique things that they only can value and it's very measurable right that I wish we had sort of even like had more in our consciousness right which is as an industry because right now I think when people say wow I don't want a token max it's an artifact of us not having thought ourselves as an industry that we are using tokens to create value every step of the way.

</details>

### Agentic 时代的 UI 重构与“粘合工作”的自动化

AI 的成功正在反逼基础设施的变革，最典型的例子就是编程。纳德拉提到，因为 AI 编程效果太好，开发者现在面临着数百个 Agent 会话带来的极高认知负荷，这要求我们必须重构 **IDE**，引入类似 **Canvas** 的新界面，而不仅仅是对话框。在更广泛的企业领域，大量的**人力资本（Human Capital）**被消耗在“粘合工作（Glue Work）”上——即协调、同步和微观管理。通过引入长期运行、具有持久性的 **Agent**，这些工作可以被 Token 化和自动化。未来半年内，人们会习惯于让具有“委派授权”的 Autopilot 连夜处理工作，并在第二天通过摘要告知：“我做了什么，进展如何”。

<details>
<summary>Original English Source</summary>

coding is worked so well that we now have to rebuild the IDE right I mean it's kind of nuts to see what we launched is like oh my god I have these 100 agent sessions I the cognitive load it transfers back to me as a human is so excessive that now I need a new UI oh by the way like the the chat as the only artifact was also impossible. So that's why we need a canvas. So it's kind of interesting for all the things about where is software needed or where is UI needed. Uh you kind of need that even for code right in a fully agentic world. But that said, one of the things that we are starting to see, we started seeing with co-work, but even some of the work we we showed with auto um um autopilot, right, on what you see with claws is a good one because if you sort of think about a lot of human capital is doing the glue work, right? If you now can augment that with tokens slash agents that are longunning, durable, right? then your ability to scale even what is still judgment and glue work gets amplified like coding does. Uh so you can like I'm positive that 6 months from now we'll all be saying oh wow like all through night the night there was a bunch of stuff that all these autopilots that I have working on my behalf with my delegated authority so to speak right I can sort of given even my identity did a bunch of work then of course I'll need my new ad to say what did you do like am I did I do this work and so on so I think that that's where compressing of workflows uh complete reading of tasks. Uh that's where I think a lot of the value gets created.

</details>

### 企业治理架构（Harness）：上下文层面的魔力

对于企业生产力，纳德拉提出了**治理架构（Harness）**的概念。这套架构定义了模型、数据与工具之间的循环逻辑。无论是 GitHub Copilot 还是安全副驾驶，其核心都是一个具备工具访问能力的**多模态治理架构**。纳德拉指出，过去两年最惨痛的教训是：为了让计划能够最高效地执行，预处理**上下文层（Context Layer）**所需的工作量大得惊人。这正是“魔力”所在——如何将丰富的上下文喂给 Agent。微软通过在 Foundry 中开放这种架构，允许企业接入任何模型（如 Llama 等），并配合自己的工具、上下文和评估体系进行能力“爬坡”。这种“多模态治理架构”已被证明在发现漏洞等实战任务中比单一模型更为强悍。

<details>
<summary>Original English Source</summary>

so in some sense you kind of want the harness to define the models the the data uh and the tools and so that you have a loop across those three and so what we are trying to first of all make sure is each of our products that we build right whether it's GitHub copilot or the security co-pilot the the stuff we showed with mdash or even the discovery for science it doesn't matter. All of them are multimodel harnesses um with tools access so that you can do this progressive uh disclosure of tools even so that they're token efficient. Uh and then you're feeding it with very rich context because that's sort of the other hard lesson we've learned in the last two years is oh my god the amount of work you need to do to prep the context layer uh such that your plan can execute in the most efficient way is where the magic is. So we have in our case we have the GitHub harness which essentially we're using across all our products. It's available in foundry and we're open like you can use your llama harness whatever or you can use the um uh you know any open harness or any harness of yours and train with your tools and multiple models and your context and so that's the pitch because right now a lot of dialogue is um hey if I train the harness plus tools and the model together you get evals and what we are proving out is and the best example of that is what we did with mdash right because when it launched um it found bugs or vulnerabilities that were not found by mythos. Uh and so there is existence proof I would claim that you can have a multimodal harness uh that can in fact be more uh performant in the real world.

</details>

### 私有评估作为核心 IP：主权智能的愿景

在 AI 原生时代，企业的核心知识产权（IP）正在发生重构。纳德拉认为，**私有评估（Private Eval）**可能是企业未来最重要的资产。如果一家公司能够利用前沿模型进行持续的能力爬坡，且不泄露任何交互轨迹，这就是其核心竞争力。一个衡量标准是：你拥有一套私有评估方案，且能灵活地在模型 A 和模型 B 之间切换并保持能力上升。如果能做到这一点，你就掌握了控制权。微软的愿景是让每家公司都能利用自己的数据，在前沿领域运作自己的**主权智能（Frontier Intelligence）**。这不仅是为了效率，更是为了确保公司在持续复利的平台之上拥有可延续的终端价值。

<details>
<summary>Original English Source</summary>

But the thing that is is it should not be a limiter to other people achieving that same success. Right? That I think is the core difference which is the the network effects this time around around intelligence are such because they learn from data and not really lots of data. It's just the few samples that you have to see to understand what's novel about something. So that's why the game becomes how to protect. So that's why I would say every company having private eval maybe the biggest IP right I think about it like what's that private eval that you can then use even a frontier model to hill climb on and not leak the traces maybe one of the biggest drivers uh of IP like so in other words another asset test is you have an eval that's private you're using a a give model A can you switch it to model B and you climb up. If you can, then you're in control. If you can't, you're not in control. And that's where even the harness decision becomes super important, right? So therefore, having an open harness, letting all models come in, having your evals, your context, your tools help you hill climb, I think is the skills that an AI native startup needs, a SAS company needs or every enterprise needs. Yeah, I think in a very real way you are Microsoft historically as an operating systems company and then become a cloud company. Maybe like the third act is that you're harness or eval whatever whatever the the sort of conglomerate of concepts that you want to put together. Um I I think like enabling every company to have like frontier intelligence or what what I forget the the exact term that you used um is the the mission right that is that is the platform promise that you build with us you will get your intelligence uh for your data.

</details>

### Token 资本与平衡表上的“老兵 Agent”

纳德拉提出了一个极具前瞻性的财务概念：**Token 资本（Token Capital）**。他认为，过去人力资本很难被列入资产负债表，因为隐性知识难以捕捉；但现在，通过记录人类与 Agent 之间的协作轨迹（Traces），企业可以训练出具有丰富经验的“老兵 Agent”。随着 Token 资本的比例上升，人类的**机构代理权（Agency）**和雄心将以新的形式表达。企业价值的创造将取决于如何让 Token 与人力资本产生复利。这种能够捕捉并延续 Tacit Knowledge（隐性知识）的 Agent，实质上是企业资产的一种持久化形式，甚至可能引发会计准则在“Token 专家经验”层面的变革。

<details>
<summary>Original English Source</summary>

I'm definitely in the camp that this is going to be about expressing new forms of human agency and ambition even as token capital goes up, right? So let's say a any corporation has lot of tokens and lot of human capital. The question is how do you compound the two? So if you have a like if you take in teams I have a bunch of agents doing work and a bunch of humans doing work and the traces between those that is really important context of how that enterprise is creating value then that goes back to train not a generalist model but to tain the train the company veteran agent uh right that is super valuable again right which is when a company says it should in fact go onto the balance sheet is how I think about it right That's so in fact they may be like human capital was never possible to go put on a balance sheet uh because you then know how to capture the tacet knowledge whereas now I think you can with the agents that have learned through the through time through time through all the traces uh so that's what at least we think will happen.

</details>

### 重构 SaaS：从预设应用到灵活的工作流数据库

针对“软件终结”的讨论，纳德拉提出了 SaaS 模型的主动解构与重组。过去二十年，SaaS 的逻辑是：构建数据模型（Schema）、编写业务逻辑、叠加 UI。现在，这个垂直堆栈正被重新审视。底层的数据模型和实体关系（如总账、语义模型）依然极其宝贵且需保持稳定，但打包方式必须改变。以 **Microsoft 365** 为例，通过 **Work IQ**，微软暴露了公司内部最重要的数据库——这些数据过去被困在邮件、文档和 Teams 频道中。现在，开发者可以要求系统：“我上周参加了一堆关于这个 Repo 的设计会，请捕捉所有讨论并告诉我代码库该怎么改”。这种价值创造潜力比过去高出 10 倍，但也要求架构层能支撑 Agent 而非仅仅是传统的端用户。

<details>
<summary>Original English Source</summary>

Now you kind of get to relitigate that vertical stacking, right? So I still think for example that data model that you built underneath every SAS application is super good, right? Like why reinvent it? Like I my general ledger better be a general ledger. I don't need new schema creation. Uh in fact that entity relationship uh is actually pretty good robust thing that I want to feed. And you want to be stable. That's right. Then same thing with business logic, right? If if you look at uh we have this product called PowerBI, right? It was like dashboards galore people created. The beauty underneath that dashboard is a very rich semantic model, right? Someone took the pain to create a dashboard and do all the measures. And you want that that's business logic, right? I want that to be available to me. So I think the challenge of the SAS business model is we packaged one way we now have to learn how to unbundle these things and rebundle in new ways and discover new business models right I mean if you look at it what's happening today with Microsoft 365 is a great example right we have this thing called work IQ in fact like what we're realizing is oh my god like if you look at in fact there's a historical parallel to right we sold first exchange and share SharePoint and uh you know before teams we had a thing called link server and what have you and we thought oh that's all going to move to the cloud but little did we realize that oh the number of people who will use servers in the cloud is 10x 100x right because people were not buying servers they were just buying a subscription. The same thing is now happening with M365 because with Work IQ, we have exposed what is perhaps the most important database in a company that never got used as a database because it was only captive to our apps, right? It was all email operated on it, Teams operated on it, Word, Excel, PowerPoint, SharePoint. But now, like this is one of the coolest things I get to do with work IQ. I go to a GitHub repo and I say, "Hey, I attended a bunch of design meetings last week related to this repo. Can you capture all that and tell me what changes I should make?" I mean, think about that, right? It literally can go look at all those transcripts, come back with a plan to change a code base, right?

</details>

### 商业模式的博弈：订阅、消耗与结果导向

关于 AI 时代的定价，纳德拉认为**按人头订阅（Per User Pricing）**本质上是预算管理中对确定性的追求。尽管 Agent 的使用强度已远超人类互动，但“人头费”短期内仍是主流。微软正在引入**消耗量表（Consumption Meter）**来调整这一模型。对于“按结果计费（Outcome-based Pricing）”，纳德拉观察到一个有趣的心理现象：大多数人宣称喜欢按结果计费，直到他们真正拿到了满意的结果——那时他们会觉得按结果分享利润就像是在支付高昂的版税，转而又希望回到按订阅或按量计费。因此，灵活的定价策略对供应商至关重要。

<details>
<summary>Original English Source</summary>

the per user pricing is really an artifact of someone creating a budget needing certainty right because it's the most important thing like somebody wants a budget they need a per user and and per user is just a set of entitlements to usage right that's kind of what it is and so the way is the first bundling will be take some usage bundle it into per user stacks and you know then sell subscription so subscriptions I think are going to be there per user is going to be there then the next big thing will be consumption so people will say I want consumption and it's also possible that people will say I don't even want to pay for any of the subscriptions or the consumption. It's outcome. But remember, most people love outcomes until they have an outcome. Because once you have an outcome, it's like giving away royalty, right? I mean, like I I've talked to customers who love, you know, outcome based pricing and I say, "I'm all in until they oh my god, like what are you talking about? You're sharing in my outcome." No, no, no. I want you to go back to per user pricing and I want you to consumption price. Right? So, I think that debate will go on. uh but and all all the all all of these business models have a particular time and a place versus one to rule them all.

</details>

### 元认知生产力：不可能变为可能的野心

最后，纳德拉分享了关于**组织雄心（Organizational Ambition）**的思考。在 AI 转型中，真正的雄心在于将“不可能变为可能”。他举了 Azure 网络管理团队的例子：这个团队在 15 个月内建设的容量超过了前 15 年的总和，支撑这点的关键是他们重新构想了工作——他们的工作不再是“做网络”，而是“构建一个能做网络的 Agent 系统（代号 Miles）”。这种将工作推向**元维度（Meta-dimension）**的思维，即**元认知（Meta-cognition）**工作，是创造企业价值的关键。就像 80 年代我们无法通过雇佣 40 亿打字员来解决信息革命一样，我们现在也不需要更多的头衔，我们需要的是通过 Token 改变产出。

<details>
<summary>Original English Source</summary>

I think the the thing in these type of transitions is to have a conceptual model of how work can change to go after outcomes that you could hardly imagine previously. Right? In fact, Kevin Scott has this nice line, right? which is um when you can make the impossible like when you're making hard things easier that's sort of one point of leverage but true ambition is about making the impossible possible. So now the thing that is missing a little bit in all of our organizations is what is that new conceptual model of what can we build what was impossible and what can we build and I'll give you one example of this right which is I take great inspiration from sort of the people who were managing the Azure network and they came to the this was from even last year you know we were scaling you saw that I I talked about sort of how we built in the last 15 months more Azure capacity than we built in the first 15 years. I mean, it's crazy, right? It's pretty wild. And it's the same team. So, they saw that and they said, "But this just ain't going to work if we don't reconceptualize our work." So, they built essentially they said, "Our job is not to do Azure networking. Our job is to build the agentic system does that does Azure networking, right? ... so they were saying look I we don't need headcount we need tokens in order to be able to manage uh our operation that reconceptualization of what their work is right they they basically took their work and made it meta right that meta work is now their new work.

</details>