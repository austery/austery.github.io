---
author: All-In Podcast
date: '2026-09-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=hdcsTeCFE0I
speaker: All-In Podcast
tags:
  - frontier-model
  - cloud-computing
  - open-weight
  - enterprise-software
  - ai-infrastructure
title: 微软CEO萨提亚·纳德拉谈AI前沿竞争、算力资本开支与生产力落地
summary: 微软董事长兼CEO萨提亚·纳德拉在访谈中深度剖析了AI前沿模型的技术演进、开源与闭源生态竞争、企业级AI系统架构设计，以及微软高达800亿美元资本开支背后的算力基础设施布局与经济回报逻辑。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Microsoft
  - OpenAI
products_models:
  - Azure
  - Copilot
media_books: []
status: evergreen
---
### 前沿模型与人类掌控

**旁白**: 已经为**微软**（Microsoft）创造了2500亿美元的市场价值。微软董事长兼首席执行官**萨提亚·纳德拉**（Satya Nadella）。

<details>
<summary>Original English</summary>

**Narration**: has generated $250 billion with a B in market value for Microsoft. Satya Nadella, chairman and CEO of Microsoft.

</details>

**杰森·卡拉卡尼斯**: 自从你担任CEO这三年半以来，股价上涨了大约120%。我能拿出我的800亿美元。我打算斥资800亿美元来建设**Azure**。或许在工业革命之后，这是最重大的事情了。这就是我们对**前沿模型**的目标。我们的模型应该成为他们可以用作基础的最佳模型。我们创造技术，是为了让其他人能够创造更多的技术。这就是我们。我们是工具制造者。让我们欢迎萨提亚·纳德拉。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Since you've been the CEO, three and a half years, the stock is up about uh I guess it's about 120%. I'm good for my 80 billion. I am going to spend $80 billion building out Azure. Maybe after the industrial revolution, this is the biggest thing. That's our goal with our frontier model. Our model should be the best model that they can use as a base. We create technology so that others can create more technology. That's who we are. We're tool maker. Please welcome Satya Nadella.

</details>

**萨提亚·纳德拉**: 大家好。

<details>
<summary>Original English</summary>

**Satya Nadella**: All right.

</details>

**杰森·卡拉卡尼斯**: 嗨，伙计。很高兴看到你走出来。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Hi guy. Good to see you coming out.

</details>

**萨提亚·纳德拉**: 很高兴见到大家。

<details>
<summary>Original English</summary>

**Satya Nadella**: Good to see you.

</details>

**查马斯·帕里哈皮蒂亚**: 早上好，伙计们。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Good morning guys.

</details>

**杰森·卡拉卡尼斯**: 你好吗？

<details>
<summary>Original English</summary>

**Jason Calacanis**: How are you?

</details>

**萨提亚·纳德拉**: 很好。

<details>
<summary>Original English</summary>

**Satya Nadella**: Good.

</details>

**杰森·卡拉卡尼斯**: 感谢你的加入。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Thanks for joining us.

</details>

**查马斯·帕里哈皮蒂亚**: 疯狂的周末，但我们还是来了。我们需要放慢前沿探索的步伐吗？

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Crazy weekend, but here we are. Do we need to pace the frontier? [laughter]

</details>

**萨提亚·纳德拉**: 那么，让我们先从常识部分开始：我们应该竭尽全力去构建首先为**人类福祉**服务且受**人类控制**的东西。你知道，我们必须从这种基本常识层面开始谈起，这听起来有点不可思议，但我认为这是一个很好的切入点。

然后，当我思考节奏调控或其他问题时，至少我认为最关键的事情是这项技术的**广泛传播与扩散**（broad diffusion），因为这项技术的红利能够无处不在地显现，这才是真正的核心所在。所以归根结底，如果你说服务人类，那就让它真正以服务人类的方式触达人类，这意味着你必须拥有选择权，必须拥有充分的**市场竞争**。你必须拥有各种各样的商业模式，无论是**开源权重**（open weights）、**闭源权重**（close weights），还是其他形式。

然后我认为另一个在讨论控制时较少被提及的方面，实际上是客户、企业或商业机构对这项技术所拥有的控制权，因为有时这项技术是如此不透明，对吧？我需要保护我的隐私，我希望能够将我的知识嵌入到一组权重中，但我不想让这些权重随意外泄。我希望能够对我的数据、推理过程以及我构建的系统拥有完全的控制权。

因此，我认为必须从这些实际落地的层面来看待所谓的“控制”与“安全”，而不是仅仅停留在抽象的理论争论上。

<details>
<summary>Original English</summary>

**Satya Nadella**: So, let's start with the common sense part first, which is we should do what it takes to build stuff that serves humanity first and is in human control. You know, it's kind of crazy that we have to start with that level of common sense, but I think it's a good place. Then when I think about pacing whatever the first thing that at least I believe is the broad diffusion of this technology is the most critical thing because the benefits of this tech showing up everywhere is really what's all about right so at the end of the day if you sort of say serving humanity let it actually reach humanity in ways that it serves humanity and that means you got to have choice you have to have competition. You have to have all kinds of business models whether they're open weights, close weights, what have you. Then the other aspect I think that is not talked about when we talk about control is actually the control that for example customers have, enterprises or businesses have around this technology because sometimes this is so opaque, right? I want my privacy. I want to be able to embed my knowledge in a set of weights without those weights leaking. I want to have control over my data, my inferences, and my systems. So that's how I think about control in a real, practical sense.

</details>

**查马斯·帕里哈皮蒂亚**: 不过，当那篇论文/文章发布时，随后似乎出现了一种各方抱团防御的态势，你对此感到惊讶吗？

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Were you were you surprised though when both the essay landed and then it seemed like there was a circling of the wagons?

</details>

**萨提亚·纳德拉**: 我认为这——我的推测是，它真正源于这样一个阶段：当你开始亲眼看到技术能力的爆发时，事实上这甚至不足为奇。人们开始意识到系统正在做一些以前无法想象的事情，比如未受监控的操作、网络访问权限、或者直接接触到了**API密钥**。

<details>
<summary>Original English</summary>

**Satya Nadella**: I I think that it comes my my suspicion is it comes genuinely from this place where when you start seeing in fact it's not even surprising when you see what these systems are capable of doing.

</details>

**查马斯·帕里哈皮蒂亚**: 没错，对，或者这些 API 密钥。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: right right or these API keys

</details>

### 软件工程与系统审计

**萨提亚·纳德拉**: 或者一个 API 密钥，或者完全没有监控、具有互联网访问权限，存在着很多经典的、我会称之为缺乏基础**软件工程规范**（software engineering hygiene）的问题。当你给一个模型分配任务，让它去执行某个目标，而系统没有设置护栏、没有审计日志、没有权限隔离时，它当然会采取一些出人意料的捷径。

如果你从纯粹的计算机科学和系统架构的角度来看，解决这个问题的途径不是去对一个神秘的“黑盒”进行玄学式的恐惧，而是回到经典的工程原则上。我们需要构建确定性的校验机制、访问控制策略和运行时监控。

<details>
<summary>Original English</summary>

**Satya Nadella**: or an API keys or yeah exactly there's no monitoring uh there's internet access there's sort of classic I would call it software engineering hygiene. When you give a model an objective and there are no guardrails, no audit trails, and no isolation, it will find shortcuts. If you look at it from computer science and systems architecture, the solution is not mystical fear, but good old engineering principles like deterministic verification, access control, and runtime monitoring.

</details>

**大卫·弗里德伯格**: 那么实现这种控制的方法是什么呢？我会说，去构建一个因果模型，比如一个在语义层面对执行动作进行严格校验的**语义模型**（semantic model）。

<details>
<summary>Original English</summary>

**David Friedberg**: and so what is the way to do that I would say oh go build a maybe a causal model like a semantic model that actually checks what actions are being executed.

</details>

**萨提亚·纳德拉**: 我接受这个观点，即我们目前确实还没有完全理解**隐空间**（latent space）的内在数学运作机制。正如大家所知，随着模型规模的增长，它展现出了涌现能力。但我们可以通过结构化的方式来增加可解释性与确定性，例如引入**思维链**（chain of thought）。

<details>
<summary>Original English</summary>

**Satya Nadella**: I I mean I I buy the argument that we do not understand the latent space. Uh right other than I thought you know as you scale, you see emergent properties. But we can add determinism and explainability through structured approaches like chain of thought.

</details>

**大卫·弗里德伯格**: 思维链。

<details>
<summary>Original English</summary>

**David Friedberg**: chain of thought

</details>

**萨提亚·纳德拉**: 思维链，这样你就可以真正深入地审查它的推理步骤。事实上，你可以运行**多模型协同架构**（multiple models），用一个模型去交叉检验另一个模型的逻辑推理和执行计划。

<details>
<summary>Original English</summary>

**Satya Nadella**: chain of thought and so then you can really go look at it deeply in fact you can have multiple models uh and you can look at the reasoning paths and cross-validate them.

</details>

**大卫·萨克斯**: 萨提亚，你与技术专家打交道数十年了。当你作为微软这样一家科技巨头的领导者，看到这些前沿实验室关于技术安全与控制的讨论时，你如何看待这其中的工程文化差异？

<details>
<summary>Original English</summary>

**David Sacks**: Satya you've worked with you've worked with technologists for decades uh and when you see as a leader of one company Microsoft, looking at how these frontier labs debate safety and control, how do you view the culture and approach?

</details>

**萨提亚·纳德拉**: 是的。你知道，我很难去具体评判任何其他机构内部发生的事情，但我们可以谈谈我自己是在微软内部如何成长起来的，以及我们是如何处理复杂系统工程的。

<details>
<summary>Original English</summary>

**Satya Nadella**: Yeah. you know, it's it's hard for me to speak to what's happening in any of these places, but let let's just say uh how we I grew up even inside of Microsoft and how we approach complex systems engineering.

</details>

**查马斯·帕里哈皮蒂亚**: 确实。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Yeah.

</details>

**萨提亚·纳德拉**: 没错。我的意思是，这就像软件工程的入门基本功（101），对吧？当你在系统构建中面临一个 Bug 时，你会怎么做？你会停下来，去寻找**根本原因**（root cause）。你不会凭空猜测，而是去追踪调用栈、分析内存转储、审查输入输出。

在构建大模型和智能体系统时也是同样的道理。你不能仅仅因为一个概率模型偶尔生成了意外的输出就陷入恐慌，你必须建立完备的**证据链**。

<details>
<summary>Original English</summary>

**Satya Nadella**: Right. I mean, that's kind of like 101, right? Which is why you're faced, you're like, you know, you have a bug. Um what do you do? do you stop uh and go find the root cause? You look at stack traces, memory dumps, and logs. In building large models and agentic systems, you cannot panic over probabilistic outputs; you must construct verifiable chains of evidence.

</details>

**查马斯·帕里哈皮蒂亚**: 证据。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: evidence

</details>

**萨提亚·纳德拉**: 必须有证据，所有的一切都必须是**可审计的**（auditable）。它访问的每一个对象，如果它试图去获取一个机密凭据，或者去调用一个外部工具，系统都必须记录在案，必须有沙箱隔离和严格的权限校验机制。

<details>
<summary>Original English</summary>

**Satya Nadella**: evidence and so everything has got to be auditable. uh and then every object it access, right? If it goes and gets a secret, oh, it's going to go chain actions, it must be logged, sandboxed, and authorized.

</details>

**查马斯·帕里哈皮蒂亚**: 是的。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Yeah.

</details>

**萨提亚·纳德拉**: 谢谢。

<details>
<summary>Original English</summary>

**Satya Nadella**: Thanks.

</details>

### 开源闭源与生态竞争

**大卫·弗里德伯格**: 我认为这是一个非常精彩的观点。我非常喜欢你在**Hugging Face**那一期讨论中所做的区分：将那些琐碎的工程失误与真正的科学突破区分开来。真正的技术扩散需要兼具科学探索与实用产品形态。

<details>
<summary>Original English</summary>

**David Friedberg**: So I think I think that's a great point. I love how you uh differentiated in the HuggingFace uh episode between the mundane things they got wrong like basic permissions versus fundamental breakthroughs, and how broad diffusion needs both real science and scalable product form factors.

</details>

**萨提亚·纳德拉**: 是的，我认为确实如此。这里面有基础科学的研究突破，也有产品形态（form factor）的创新，这两者的结合最终带来了广泛的技术普及。而我们现在需要找到下一个层面的系统范式，让它能够真正稳定、安全地嵌入到整个经济社会的运行当中。

<details>
<summary>Original English</summary>

**Satya Nadella**: Uh and so I think that yes, so there's some science, there is some form factor that then leads to broad diffusion and we now need to find the next level of system paradigm to embed it reliably into the real economy.

</details>

**大卫·弗里德伯格**: 我认为这是一个很好的过渡话题。

<details>
<summary>Original English</summary>

**David Friedberg**: I think that's a good segue.

</details>

**查马斯·帕里哈皮蒂亚**: 不好意思，让我插一个问题，把关于当前局势的**经济激励机制**（economic incentive）争论联系起来。有一种论调认为，前沿实验室目前正面临着严重的**Token通缩**（token deflation）压力，开源模型的快速追赶正在挤压闭源模型的利润空间。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Sorry. Let me just ask one question to connect the um economic incentive argument on what's going on. The argument is the Frontier Labs are facing token deflation and open-source models are compressing margins.

</details>

**大卫·弗里德伯格**: 嗯。

<details>
<summary>Original English</summary>

**David Friedberg**: um

</details>

**萨提亚·纳德拉**: 是的，我认为我们正在观察到的核心本质，其实就是最经典、最纯粹的**市场竞争**。对我而言，回顾软件产业的历史，我们曾经拥有一个非常成功的闭源商业数据库产品叫 **SQL Server**。那么当时对它的制衡力量是什么呢？市场上始终存在着像 **PostgreSQL** 或 **MySQL** 这样的开源替代品。

这种动态竞争机制迫使闭源产品必须不断创新、提供更高的性能和更好的企业级支持，同时也让整个行业拥有了广泛的技术底座。

<details>
<summary>Original English</summary>

**Satya Nadella**: Yeah, I think the the fundamental thing that I think we're observing is good old-fashioned competition, right? I mean, for me, if I look back at it, we had a great closed source product called SQL Server. What was the check against it? there was always a substitute called Postgres or MySQL. So competition keeps everyone honest and expands the pie.

</details>

**萨提亚·纳德拉**: 在AI领域也是同样的道理。客户希望能够在系统中混合使用多种模型，无论是闭源的旗舰模型，还是轻量化的开源权重模型。事实上，对生态系统而言，多样性永远是更好的。

早年我在微软负责 Windows 与 **Unix** 的互操作性（Windows-Unix interoperability）项目。当时很多人的直觉是：如果我们支持互操作，大家是不是就不会用 Windows 了？

<details>
<summary>Original English</summary>

**Satya Nadella**: such that we can use multiple models. In fact, it's better for them. In fact I worked on Windows interoperability with Unix first.

</details>

**萨提亚·纳德拉**: 但实际结果完全是反直觉的。我们原先以为这种互操作性意味着我们的使用率会下降，结果恰恰相反，我们的使用率大幅上升了。

<details>
<summary>Original English</summary>

**Satya Nadella**: In fact, it was counterintuitive, right? We used to think, oh my god, this interoperability means we'll be less used except we were more used.

</details>

**萨提亚·纳德拉**: 事实上，因为当时市场上存在着太多不同变种的 Unix，而 Windows 提供的稳定互操作层，反而让 Unix 变得更好，也让 Windows 变得更加不可或缺。今天在模型层也是一样的逻辑：我们构建的平台能够支持开源与闭源的各类模型，客户拥有自由选择权，这才是最健康的生态。

<details>
<summary>Original English</summary>

**Satya Nadella**: In fact, we became weirdly enough because there were so many variants of Unix at that time that Windows interoperability made Unix better and Windows better. The same applies to models today: supporting both open and proprietary models creates the healthiest platform.

</details>

### 生产力提升与GDP增长

**大卫·弗里德伯格**: 这是一个极佳的观点。我认为这引出了一个真正的核心问题：我们如何才能在宏观的**生产力统计数据**中真正看到这一变革？我们如何才能看到它真正推动全球 **GDP 增长**？

<details>
<summary>Original English</summary>

**David Friedberg**: Yeah, it's a great it's a great point. I mean, I think this is the real question which is how do we truly see this in the productivity stats? How do we see GDP growth from this?

</details>

**萨提亚·纳德拉**: 无论从需求侧还是供给侧来看，我最喜欢的一个切实例子就是**医疗健康**（healthcare）领域。如果你思考一下当今的医疗系统，医生和护士把大量宝贵的时间耗费在撰写电子病历和行政文书上。

如果我们能够通过 AI 智能体自动完成临床记录和文书流转，将医疗人员从这些繁重的琐事中解放出来，让他们把时间真正花在患者护理和临床诊断上，这就直接创造了巨大的实际价值。

<details>
<summary>Original English</summary>

**Satya Nadella**: or supply side. Um I mean the the one example that I I love and I get back to in fact healthcare is a good one right if you think about health care, clinicians spend enormous time on documentation. If AI handles clinical notes and workflow overhead, providers can focus on patient care.

</details>

**查马斯·帕里哈皮蒂亚**: 是的，毫无疑问。我们已经看到了这一点。顺便说一句，即使在最基础的 **Copilot** 应用场景中也是如此。大多数人只把 Copilot 看作是一个文本补全工具，但它真正的价值在于重塑日常工作流。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Yeah, absolutely. We see that and and by the way even in in simple co-pilot cases, right, which is if you look at how people work, it's not just drafting text, it's stripping away friction.

</details>

**萨提亚·纳德拉**: 试想一下，如果这些正在消耗你大把时间的日常琐碎工作流能够被自动化，你就能将精力投入到更具创造性和高价值的事情上。

<details>
<summary>Original English</summary>

**Satya Nadella**: uh what if uh even just these workflows that are taking away time from things that you could be spending time on were automated, freeing you for higher leverage work.

</details>

**杰森·卡拉卡尼斯**: 好吧，你提到了一个非常重要的历史参照点。如果你回溯到上世纪初的工业革命时期，当时我们的工作制从每周六天缩短到了每周五天。随着生产力的巨大跃升，人类工作时间减少了，但完成的总工作产出却保持不变甚至大幅增加。

你认为现在也会发生同样的情况吗？是否存在这样一种风险：我们最终进入了每周三天工作制，但宏观经济的年增长率仍然徘徊在2.5%左右？

<details>
<summary>Original English</summary>

**Jason Calacanis**: okay well you're bringing up this great point if you go all the way back to like the turn of the century the industrial revolution when we went from six days to five days. And so what happens is as productivity boosts come in, human work steps back and you kind of accomplish the same amount of work. Do you think that that happens here? Is that is there a risk that we have a three-day work week and we're just still growing at two and a half%?

</details>

**萨提亚·纳德拉**: 是的。

<details>
<summary>Original English</summary>

**Satya Nadella**: Yeah.

</details>

**萨提亚·纳德拉**: 没错。所以我认为这正是我们需要看到的突破。为了让这一切真正体现出划时代的意义，坦率地说，我们不仅希望看到工作效率的提升，更需要看到它催生出全新的产业、全新的科学发现，并推动全球 GDP 实现更强劲的实际增长。

<details>
<summary>Original English</summary>

**Satya Nadella**: Right. So, so that I think is what is needed, right? Which is in order for all of this to play out quite frankly, we do need to see real acceleration in economic output and transformative new industries.

</details>

### 微软商业模式与算力布局

**杰森·卡拉卡尼斯**: 在 AI 时代，微软的核心业务究竟是什么？显而易见，Azure 业务正在高歌猛进，你们甚至因为算力紧缺而在限制某些客户的需求，同时你们正在进行高达800亿美元的**资本开支**（CapEx）。

<details>
<summary>Original English</summary>

**Jason Calacanis**: What's the what business is Microsoft in in relation to AI? Obviously, Azure has been crushing it. you're turning away customers uh and you're doing $80 billion in capex.

</details>

**杰森·卡拉卡尼斯**: 不，但这里的商业本质是什么？

<details>
<summary>Original English</summary>

**Jason Calacanis**: No, but what's the business here? What's the

</details>

**杰森·卡拉卡尼斯**: 微软自己是否必须拥有一个专属于自己的前沿大模型？

<details>
<summary>Original English</summary>

**Jason Calacanis**: Do you need to have a frontier model?

</details>

**查马斯·帕里哈皮蒂亚**: 我们事先告诉过你今天座谈席上有一位职业记者吗？[笑声]

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Did Did we tell you there was one journalist on the panel? [laughter]

</details>

**杰森·卡拉卡尼斯**: 不不不，我是非常真诚地提出这个问题的，因为我真的很好奇。大家都知道你是一位顶级的商业战略家。微软过去曾经错失了移动互联网的浪潮，在搜索引擎领域也经历过艰苦的追赶。

微软会错过这次 AI 革命吗？如果你们没有自己纯自研的绝对前沿模型，你们的战略底气到底在哪里？

<details>
<summary>Original English</summary>

**Jason Calacanis**: No, no, no. It's I mean I mean it sincerely because I'm just curious. You're a great strategist. We know that about you. Microsoft missed mobile. Is Microsoft going to miss the AI revolution? You don't have a frontier model? Because I always found it perplexing that you didn't. And what's the strategy?

</details>

**萨提亚·纳德拉**: 好的，让我带你梳理一下我们在每个层面的现状和战略布局。顺便说一句，在资本开支和数据中心基础设施建设方面，我们投入的每一分钱都有着非常清晰的资产负债表与需求对应关系。

当我们谈论企业软件市场的基本盘时，全球真正的企业级知识工作者用户大约有2.5亿到3亿人。而在这一群体中，微软拥有最深厚的用户渗透率和最完整的企业信任体系。

<details>
<summary>Original English</summary>

**Satya Nadella**: Yeah. So, let me walk you uh through the sort of where we are and what we're up to on each of these. By the way, on the capex side and the buildout side, every dollar is tied to measurable workload demand. When we talk about the market as defined, there are maybe 250 to 300 million real enterprise knowledge workers, where we have unmatched presence and trust.

</details>

**杰森·卡拉卡尼斯**: 哇。

<details>
<summary>Original English</summary>

**Jason Calacanis**: oh wow

</details>

**萨提亚·纳德拉**: 没错。所以在企业市场中，客户关心的从来不是某一个单一模型的跑分高低，而是端到端的解决方案。

企业客户需要的是：无论底层哪个模型在特定任务上表现最优（无论是 **OpenAI** 的最新模型、**Anthropic** 的模型，还是开源的 **Llama** 系列），他们都可以通过 Azure 统一的 API 和安全框架无缝接入。

<details>
<summary>Original English</summary>

**Satya Nadella**: right So when we talk like the market quote unquote as defined is maybe 300 uh 250 even of real enterprise users and of that we've got the penetration. Enterprise customers care about the complete solution: data governance, identity, compliance, and multi-model flexibility across OpenAI, open source, or custom models.

</details>

**杰森·卡拉卡尼斯**: 明白。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Right.

</details>

**萨提亚·纳德拉**: 没错。所以我的基础企业级系统架构理念是：你应该拥有一个**模型路由与编排系统**（model routing and orchestration system），能够根据任务的成本、延迟和精度要求，动态地将工作负载分配给最合适的模型。

微软的核心业务就是成为这个不可替代的**智能计算平台与企业级基础设施提供商**。

<details>
<summary>Original English</summary>

**Satya Nadella**: Right. That's so so my fundamental enterprise architecture would say you should have a model system that fundamentally allows you to route to the best model dynamically for cost, latency, and capability. Microsoft is the enterprise intelligence platform.

</details>

### 定制芯片与供应链多元化

**查马斯·帕里哈皮蒂亚**: 紧接着杰森的问题，你在前面提到过一个令人难忘的论述，你说微软有能力承担800亿美元的资本开支。但在这800亿美元中，大部分资金其实流向了数据中心的基础设施与硬件采购。

其中服务器机架、网络设备和计算芯片等核心硬件（the kit）占据了总成本的60%以上。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Just to build on Jason's question you had this um incredible moment I think we put it here where you said you know we're good for our 80 billion. But looking at capex, the kit—the racks, the chips, the networking—represents 60% or more of the cost.

</details>

**萨提亚·纳德拉**: 硬件套件（the kit）指的就是机架、芯片、供电与网络系统。

<details>
<summary>Original English</summary>

**Satya Nadella**: the kit means the racks the chips

</details>

**查马斯·帕里哈皮蒂亚**: 机架、芯片以及所有相关组件，这占据了大约60%的成本。所以你们的做法是尽可能高效地建设和租赁土地与电力基础设施，但核心还是计算硬件的迭代。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: the racks the chips and what have you and that's 60% of the cost or what have you right so therefore so what we do is we go build as much infrastructure as possible.

</details>

**萨提亚·纳德拉**: 是的。正在发生的情况是，如今在大规模运行的 AI 工作负载，虽然最初是在通用的 GPU 架构上成长起来的，但现在这些工作负载的计算特征与张量形态（shape of workloads）已经被极其透彻地理解了。

<details>
<summary>Original English</summary>

**Satya Nadella**: yeah what's happening is the workloads that are now at scale uh they obviously grew up from what GPUs were there but now the the shape is so well understood.

</details>

**查马斯·帕里哈皮蒂亚**: 也就是说，既然我们明确知道在模型推理（inference）或训练（training）阶段的各个细分步骤中到底需要什么样的计算，为什么不直接针对这些特定计算阶段去定制专用芯片（ASIC），从而大幅降低单位算力成本呢？

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: um and saying well you know there are these multiple phases in um an inference or a training phase so why not build silicon that's optimized for these stages and bring down costs?

</details>

**萨提亚·纳德拉**: 确实可以大幅降低成本。

<details>
<summary>Original English</summary>

**Satya Nadella**: quite drastically

</details>

**萨提亚·纳德拉**: 因此，我认为在芯片硬件层也将出现更多的选择和竞争。就微软而言，**黄仁勋**（Jensen Huang）和英伟达的产品依然是我们最主要的算力支柱；但与此同时，我们也在积极研发和部署自研的 **Maia 芯片**，并且深度支持 AMD 等其他芯片生态。

这种多供应商与定制芯片的策略，确保了微软在基础设施层面拥有长期的成本竞争力和供应链弹性。

<details>
<summary>Original English</summary>

**Satya Nadella**: um and so I think that there is going to be a lot more choice even there in that layer. So ours we have Jensen's stuff which is I think our primary foundation, but we also build Maia custom silicon and support AMD, giving us ultimate flexibility and cost efficiency.

</details>

### 全球竞争与技术透明度

**杰森·卡拉卡尼斯**: 萨克斯，在时间结束之前，我想让你参与进来提问。

<details>
<summary>Original English</summary>

**Jason Calacanis**: Sax I want to let you get in here before we run out of time.

</details>

**大卫·萨克斯**: 好的。我们最近听到了来自几家前沿实验室领导者（如 Sam Altman、Dario Amodei、Elon Musk、Demis Hassabis）的表态，他们强调必须将技术对齐与安全放在极其优先的位置。但与此同时，其他国家和竞争对手也在全速推进其 AI 发展，并不受西方内部伦理争论的限制。

<details>
<summary>Original English</summary>

**David Sacks**: Yeah. So you know we've heard now from the the various frontier lab leaders Sam, Dario, Elon, Demis that we need to prioritize alignment and safety. But other global competitors are pushing full speed ahead without those constraints.

</details>

**萨提亚·纳德拉**: 其他国家当然也希望确保他们的公民和企业能够享受到 AI 带来的生产力红利，正如我们希望美国公民受益一样。技术本身具有全球流动的属性，你不可能通过简单的自我设限来阻止技术的发展规律。

<details>
<summary>Original English</summary>

**Satya Nadella**: uh it's not as if uh they don't want to make sure that their citizens um are benefiting from AI just like we will want our citizens to benefit from AI. Technology naturally diffuses globally.

</details>

**大卫·萨克斯**: 你用了一个词叫“特性各异的”（idiosyncratic），我认为这是一个非常精准的词。我们现在还不完全清楚各方在监管和治理上的考量究竟会如何演变。

<details>
<summary>Original English</summary>

**David Sacks**: Well that's you use the word idiosyncratic and I think that is the right word is I don't think we know yet how this global policy and competition dynamic plays out.

</details>

**萨提亚·纳德拉**: 这是一个非常深刻的问题。

<details>
<summary>Original English</summary>

**Satya Nadella**: It's a great question

</details>

**萨提亚·纳德拉**: 如果其他国家看到了技术的战略价值，他们必然会全力以赴去推进。而我对当前局势的基本判断是：我们在技术实力和创新生态上仍然保持着显著的**领先优势**。

<details>
<summary>Original English</summary>

**Satya Nadella**: and if they do then presumably they'd want to act on it as well. Yeah, I I just feel my my take there is that we are ahead.

</details>

**萨提亚·纳德拉**: 我们的制度优势在于我们就是我们自己——我们公开辩论、我们在激烈的市场中竞争、我们保持高度的透明度。在我看来，这些全部都是我们的核心优势所在。

这种透明度与开放竞争，正是推动美国科技生态系统不断自我迭代并保持全球领先的最根本动力。

<details>
<summary>Original English</summary>

**Satya Nadella**: and we are who we are which is we argue we sort of we compete uh we are more transparent which is all by the way virtues as far as I'm concerned so that open competition is our greatest strength.

</details>

### 本地经济与社区影响力

**大卫·弗里德伯格**: 你认为科技行业有哪些目前该做但还没做好的事情？微软正在采取什么行动来改变当前社会上对科技巨头和 AI 的民粹主义负面叙事？

<details>
<summary>Original English</summary>

**David Friedberg**: what do you think we should be doing that we're not doing and what are you doing at Microsoft to change the narrative the populist sentiment that we have right now around AI?

</details>

**萨提亚·纳德拉**: 对我来说，我完全聚焦于回答查马斯在前面提出的问题：这项技术究竟让谁受益了？我们必须回到对**本地社区的实际经济影响**上。

例如，我们在威斯康星州的**拉辛**（Racine, Wisconsin）进行了大规模的数据中心投资。

<details>
<summary>Original English</summary>

**Satya Nadella**: etc. So, so to me I think this is I am squarely focused on one of the to answering Chamath's question from earlier which is whom is it benefiting and going back to the local impact, like our investment in Racine, Wisconsin.

</details>

**萨提亚·纳德拉**: 大多数外部人士往往会说：“哦，数据中心建好后根本创造不了多少长期的本地就业岗位。”但事实上，在长达几年的建设周期中，我们在该地区创造了超过 1200 个高薪的**建筑工程就业岗位**，拉动了当地的电工、管工和重型机械产业。

<details>
<summary>Original English</summary>

**Satya Nadella**: Uh we have two and most people say, "Oh, there not that many jobs." In fact, there have been 1,200 construction jobs in that region all through that multi-year buildout.

</details>

**杰森·卡拉卡尼斯**: 那个数据中心的电力规模有多大？

<details>
<summary>Original English</summary>

**Jason Calacanis**: And how big, how big is that data center?

</details>

**萨提亚·纳德拉**: 我想它目前的规模至少达到了 **400 到 500 兆瓦**（MW）。

<details>
<summary>Original English</summary>

**Satya Nadella**: Uh I think it's now going to be at least 4 or 500 megawatt

</details>

**萨提亚·纳德拉**: 而且未来还会随着算力需求的增长持续扩展。

<details>
<summary>Original English</summary>

**Satya Nadella**: and it sort of will keep expanding.

</details>

**萨提亚·纳德拉**: 这些投资对当地社区是实打实的经济注入。所谓的社会认同是必须靠行动赢回来的（earning it），而不是仅仅坐在办公室里宣讲 AI 有多少宏大好处，而是要让普通人真切看到基础设施带来的税收、就业和产业升级。

<details>
<summary>Original English</summary>

**Satya Nadella**: Um and so so these are uh so that's a real like that community. So earning it like just not saying hey these are all the benefits but seeing tangible local economic growth.

</details>

**大卫·弗里德伯格**: 但你怎样才能让人们主动去传播这些正面的真实故事呢？因为现在最缺失的就是这些基层受益的故事没有被自发地讲出来，而如果是微软的高管自己出来说，公众往往会觉得这只是企业公关。

<details>
<summary>Original English</summary>

**David Friedberg**: but how do you get people to tell that story because that's what's missing today is those stories aren't being organically told and if a Microsoft executive says it, it sounds like PR.

</details>

**萨提亚·纳德拉**: 是的，我认为单靠公关故事是不够的。我们需要的是更多科技行业之外的普通人、当地工会成员、地方官员、中小企业主站出来，基于他们切身的体验来说话。

<details>
<summary>Original English</summary>

**Satya Nadella**: Yeah. No I don't think Yeah. So I think storytelling is one thing. The other one is I think we just need more people outside of the tech industry to stand up and speak from their own lived experience.

</details>

**杰森·卡拉卡尼斯**: 这对整个科技行业来说是一门全新的发力方式（new muscle）。

<details>
<summary>Original English</summary>

**Jason Calacanis**: It's a new muscle.

</details>

**萨提亚·纳德拉**: 确实是一门全新的肌肉群，我们需要不断锻炼它。

<details>
<summary>Original English</summary>

**Satya Nadella**: It's a new muscle. It's a new muscle.

</details>

**杰森·卡拉卡尼斯**: 我认为你是锻炼这门肌肉的绝佳代言人，希望你能多出来分享。非常感谢你能抽出时间加入我们。

<details>
<summary>Original English</summary>

**Jason Calacanis**: So I think you're a good spokesperson to flex that muscle. I hope you do it more. Thank you for being with us.

</details>

**萨提亚·纳德拉**: 非常感谢大家。

<details>
<summary>Original English</summary>

**Satya Nadella**: Thank you so much.

</details>

**杰森·卡拉卡尼斯**: 我们非常感谢你。[音乐]

<details>
<summary>Original English</summary>

**Jason Calacanis**: We appreciate you. [music]

</details>

**查马斯·帕里哈皮蒂亚**: 谢谢您，萨提亚先生，非常感谢您的宝贵时间。

<details>
<summary>Original English</summary>

**Chamath Palihapitiya**: Thank you, sir. Appreciate your time.

</details>