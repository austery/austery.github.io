---
author: AI Engineer
date: '2026-10-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Ti-BmGU1_mQ
speaker: AI Engineer
tags:
  - tokenomics
  - inference-optimization
  - model-distillation
  - cost-optimization
title: Token 经济学与规模化推理优化工作坊
summary: Felis AI 创始人分享大模型推理成本优化与 Token 经济学，提出涵盖细粒度度量、规格合理化、算力采购及流程审查的四个核心步骤，并探讨了代理架构选择、缓存策略与自动路由方案。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Felis AI
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

### 开场与背景介绍

>> 呃，感谢大家来到这里。呃，看到这么多人都在为 token 账单发愁，我不太确定该高兴还是该难过。整个工作坊都坐满了。呃，是的，我们今天就是要来聊聊 tokenomics（Token 经济学）。

<details>
<summary>Original English</summary>

[music]

>> Uh thank you for everyone for coming here. Uh not too sure whether to be happy or sad that so many people are suffering from the token bill. It's a full workshop. Uh Yeah, that uh we're going to talk about tokenomics.
</details>

在开始之前，先介绍一点点背景，对吧？我是来自 Felis AI 的 Eugene，我是公司的 CEO 兼创始人。呃，我同时也是 Arabic AI 开源项目背后的团队成员之一，该项目是 Linux 基金会旗下的首个 AI 模型。并且，我们致力于研发下一代 AI 架构。呃，以上是我的一些学术背景。我的 Twitter 账号是 PicoCreator。

<details>
<summary>Original English</summary>

So, a little bit of a a background with the kickstarting it, right? I'm Eugene from Felis AI. I'm CEO and founder of of it. Uh and I'm part of the team behind the Arabic AI open source project, the first AI model under the Linux Foundation. And and we work on next generation AI architecture. Uh that's a little bit of my academic background. And my Twitter handle is PicoCreator.
</details>

但更重要的是，对吧？呃，呃，关于 Felis AI 的一点背景是，我们的使命是让每个人、每种语言、每种方言、每个国家都能用上 AI。我们通过构建全球最大的开放模型平台来实现这一点，平台拥有超过 40,000 个开放模型。这其中包括专门的微调模型，比如 Sunflower 模型——这是乌干达的首个语言模型，专门针对他们的语言开发——以及大量其他的专用模型。因此，我们谈论的不仅仅是最大的开源模型，还有专用语言模型或专用用例，呃，其中一些我稍后也会提到。

<details>
<summary>Original English</summary>

But, but more importantly, right? Uh uh a little bit of background for Felis AI is that our mission is to make AI accessible for everyone, every language, every dialect, every country. And we do this We do this by creating the world's largest platform of open models, of over 40,000 open models. And this includes specialized fine-tune like the Sunflower model, which is Uganda's first language model, specifically for their language, and a lot of other specialized models. So, we're not just not talking about the biggest open source model, but specialized language models or specialized use cases, uh some of it which I'll touch as well.
</details>

当我们在模型的丰富度上具备规模时，Felis AI 同样也在为规模庞大的客户提供服务。我们的一些最大客户每天实际处理的量高达 2 万亿个 token。

<details>
<summary>Original English</summary>

And when we when we can go on scale in terms of variety of model, Felis AI also we serve customers at scale. So, some of our largest customers are literally serving 2 trillion tokens a day.
</details>

他们处理这些 token 的成本大约在每百万 token 0.3，或者说每天 6 万。他们是在大约 512 张 AMD GPU（呃，MI215）上运行的。呃，对这位特定的客户来说，运行的是一个私有的 400 Android BM OE 模型。呃，他们运行时的表现大概在 Opus 4.8 级别。所以这是大量的并发请求，极大的 token 吞吐量。这就是我们所说的规模。如果你看一下，在超过 4.8 级别的性能下做到每百万 token 0.03，这可不是你在公共云市场上能直接买到的东西。这是非常专门的配置，专门为了在我们所谈论的这种规模下运行而设计的。

<details>
<summary>Original English</summary>

And and they're And and they're serving it at around 0.3 per million tokens or 60K a day. And they're doing it on around 512 AMD GPUs, uh MI215. Uh and for this customer in particular, it's a private 400 Android BM OE model. Uh and they're serving it around Opus 4.8 class performance. So, it's lots of concurrent requests, lots of token volume. That's what we mean by scale. And if you look at it, 0.03 per million token at over 4.8 class, it's not something that is not something that you can get off the public cloud market. This is specially very specialized setups that is meant to run at the scale that we are talking about.
</details>

### 两点重要声明

这也引出了我在开场前要先讲的两点重要声明。第一，我们是做推理业务销售的。因此我在这里讲的所有内容，都会涉及到任何服务商。这里的内容没有什么是专门针对 Fiddler's 的。但是，呃，为了明确起见，我们销售推理服务。所以，这些数据点和经验也分别来自于我们自身。好吗？

<details>
<summary>Original English</summary>

So, that kind of uh leads in into two major disclaimers that I'm going to start off. One, we sell inference. So, everything I cover here will cover the will will touch on any provider. Nothing here is specific to Fiddler's. But, to to for clarity, we sell inference. So, so this is from our data points, from our experience, respectively, as well. Okay?
</details>

另一件事是，本次工作坊将涵盖大量规模化优化的内容，如果你的机构每月支出少于 1 万，这可能不太适合你。呃，对于那些处于这个指标线以下的人——这是一个任意设定的指标——我的建议是，如果你花费少于这个数额，你最好还是集中精力去尝试在机构内部找到强大的用例，而不是试图去优化 token 开销账单。因为一个强大的用例能给你的机构带来远超每月 1 万的价值。那才是你应该重点关注的领域，而那不是我这次演讲的重点。

<details>
<summary>Original English</summary>

The other thing is that this workshop is going to cover a lot of optimization at scale, and it probably will not fit you if you're like spending less than 10K a month in your organization. Uh my word of advice for those who are below this this uh metric mark, and this is an arbitrary metric, is that if you're spending less than this, you're probably better off focusing on like trying to get strong use cases within your organization, rather than trying to optimize the token spending bill. Because a strong use case can bring your organization way more than 10K a month. And and that's and that's what should be your main area of focus, and that's not my area of focus for this talk.
</details>

### 工作坊四大步骤与度量

那么，我们在本次工作坊中要讲的，呃，是按四大主要顺序展开的四个步骤：度量、合理调整规格（right-sizing）、呃你该如何采购算力，以及如何检查你的流程。

首先是度量。

是的。你会惊讶于这究竟有多么必要。呃，比如，你们当中有多少人知道自己的 token 总支出？能举手示意一下吗？

哇，全场只有一半的人举手。好的。你们当中有多少人能够度量到部门一级？那些举手的人，请继续举着。然后，我看到大概又有一半的人把手放下了。是的。越往细分，到了团队一级、用例一级，比例就越来越低。呃，联系我们的客户中，随随便便就有 30%、40% 的人在刚开始时全机构上下共用一把密钥。那就像是……呃，呃，这要怎么度量？我们要怎么从那里着手？所以，这不是特定于某家供应商的建议，而是你需要开始拆分密钥，开始按部门拆分，开始按主要用例拆分，这样你才能知道你的 token 都花在哪里了。嗯，从那时起，这才能为你的工作负载提供依据。

<details>
<summary>Original English</summary>

So, what we are going to cover in this workshop uh is four moves in in in four major order: measuring, right-sizing, uh how do you buy your capacity, and how you check your process.

So, measuring.

Yep. You'll be surprised at how essential this is. Uh like, how many of you know your total token spend? Can I have a raise of hands?

Wow, only half the room raised hand. Okay. How many of you can measure at the department level? Those those who have their hands raised up, leave your up. And so, I see about another half went down. Yeah. And it gets lower and lower down to the team level, to the use case level. Uh we like easily 30 40% of our customers that reach out to us, the first thing they had was a single shared key that everyone in the organization used. And that was like Uh uh how do we even measure that? How do we start from there? So So this is not and a vendor specific like you need to start splitting up your keys, start splitting up by departments, start splitting up by major use cases so that you know where all your tokens are. Um and this is then from then on it can inform your workload.
</details>

所以是的，分发 API 密钥应该没那么难。嗯，一旦知道了这一点，对吧，你就可以分别开始做合理调整了。比如，是哪个团队呃和工作负载在花这笔钱？使用者当时在等待什么？比如，有些团队配得上那样的每秒 token 数。有些在午夜运行的后台 agent，大概配不上你花钱买的那种每秒 token 速度。呃是的，别在后台 agent 上买 ultra 级别。那简直太蠢了。嗯，不仅如此，你还可以观察自身的使用情况，从而更好地规划你可能采购的专享算力，无论是用于开放模型还是封闭模型。呃是的。而且你还可以检查哪个团队消耗 token 最多，以及他们是否有产出。呃，这一点我稍后也会讲到。

<details>
<summary>Original English</summary>

So yeah, API keys shouldn't be that hard to issue. Um once you know that, right, you can start right-sizing things uh respectively. Like like which team is uh and workloads spend on it? What was the person waiting for? Like some teams deserve the tokens per second. Some background agents running at midnight probably can don't deserve the tokens per second speed that you're paying for it. Uh yeah, don't pay for ultra on a background agent. That's just dumb. Um and and from that also you can also look at your usage to better advise like uh dedicated capacity that you may purchase, be it for open models or even close models. Uh yeah. And also you can also check which team spend the most token and whether they are productive. Uh I'll touch on that as well.
</details>

### AI 工作负载的两大轨道

在 AI 工作负载中你应该了解的一件事，对吧，呃，大家可能也已经体会到了，对吧，那就是存在两个主要的轨道，两者的经济特性截然相反，呃各自皆是如此。首先是 agent 式的工作负载，显然介于两者之间也有其他形态，但它往往是长程运行、多租户的 agent。编程 agent 就是一个典型的例子。有些——有些开发者会让编程 agent 持续运行一整夜，持续很长一段时间，并带有呃多次压缩。而这些都会最大化上下文的呃使用。

业务流程自动化则是另一极端。呃，想想呼叫中心，想想邮件路由，诸如会议纪要转录之类的事情。这些通常在上下文上要短得多，尽管有很多例子并不符合这一说法。但它非常受流程驱动，高度任务隔离，而且从本质上讲，这是一场走量的工作。

<details>
<summary>Original English</summary>

One of the things that you should know in AI workloads, right, uh and you all may already experience, right, is there are two major tracks with very opposite economics uh respectively. So there is the agentic workload and obviously there's things in between where it tends to be like long-running multitenant agents. Coding agents are a particular example of this. Some Some Some may have some devs like run coding agents like literally overnight over a long period of time with uh with multiple compaction. And and these things maximize the context uh usage.

Process automation is the other extreme. Uh think call centers, think email routing, things your meeting notes transcribing, and things like that. It's all It's much shorter in context in general, though there are a lot of examples that defy this statement. But, it's very process-driven, very task-isolated, and it's it's a volume game, essentially.
</details>

那么，我所说的更多使用量是指什么呢？这可能是许多机构面临的首要爆发点之一。特别是当他们盲目跟风公有云或某种云仿制品时。比如，在我们支持的各个开发团队中，我们曾抽样过其中一个团队，他们只有 5 位开发者，而在我们合作的其中一家公司里，他们平均持续运行着 8 个 agent。因此，他们之前调用 API 运行 Opus 4.8，每个月持续运行这些 agent 基本上要花掉 15 万。其中一部分是他们用来写代码的 agent，一部分是在夜间启动的 agent。他们稍微更进阶一些，已经知道应该在夜间没人工作时把任务启动起来。但基本上，他们每个月要消耗 1160 亿个 token。我们切实地帮助他们切换到了 GRM 5.3 实例。

之前是 5.2。他们已经升级到了 5.3，那只是单个节点，每月花费不到 1 万。而且他们没有受到任何业务中断或影响。因此，了解你的团队可以让你相应地做出这些决策。而且正如我强调的那样，了解流程工作负载也允许你将任务拆分开来。举例来说，以前他们整天都在运行所有东西，但后来他们开始把一些后台 agent 调度在团队睡觉时运行，整夜跑。这样就可以分别充分利用他们的硬件。

<details>
<summary>Original English</summary>

So, well, what do I mean by more usage? And this is probably one of the first major explosion a lot of organizations face. In particular, when they jump onto the open cloud hype or one of the cloud clones. So, you like like from from from various developer teams that we we support, like for example, we sampled one of the team, and it was only five devs, and they were averaging around continuously eight running agents for one of the companies we work with. And And so, they were previously running Opus 4.8 of the API, and they were essentially spending 150k a month continuously running these agents. Some of it is the agents that they use to code, some of it is the agents that kick in at night. They They were slightly more advanced. They already knew that they they they they should kick things off at night when no one's are working. But, essentially, they were spending 116 billion tokens a month. And we literally helped them switch to GRM 5.3 instance.

Previously, it was 5.2. They already upgraded 5.3, and that was like a single node. That was less than 10k a month. And they were And they didn't see any disruption or impact. So, knowing your team allows you to make these decisions respectively. And like like I highlighted, like knowing processes workload also allows you to split things off. So, like, for example, previously, they were running everything throughout the day, but they they started scheduling some of the background agents when the team was asleep, and it runs through night. So, this allows you to utilize their hardware respectively.
</details>

正如我简要提到的，业务流程自动化的另一面纯粹就是走量。定义极其明确。私下里我可以给你们提供更具体的例子，但你可以将其理解为每天数百万次甚至数千万次的规模，比如呼叫中心的决策、扫描的代码行数、过滤的电子邮件和短信。比如与我们合作的一家电信运营商，他们在短短一分钟内的峰值就能轻松达到 1000 万条消息。这并不奇怪，新年那天是最糟糕的。是的。所以……他们过滤消息的原因，是因为他们提供了一项功能，比如为儿童提供安全手机。所以他们需要 AI 来扫描，基本上就是看是否有脏话、色情内容等等。所以，这确实不是一个长程——

<details>
<summary>Original English</summary>

The As I I touched on briefly, the other side of process automation is purely a volume game. Extremely predefined. I I can give you more specific example off the off the record, but you think of it as like millions per day or even tens of millions per day, decisions in call centers, lines of code scanned, emails and text messages filtered. Like, one of the telcos we work with, like, they easily hit peak 10 million messages in a single minute. And this shouldn't come as a surprise. Happy New Year is the worst. Yeah. So So So these And they And they help And the reason why they filter messages is because they provide a feature about like providing safe phone for kids. So they needed an AI to scan like basically is it profanity, sexual content, etc. etc. So So this This is really not a long
</details>

<!-- chunk 2/7 -->

上下文，而是一个跑量的事情。其他事情像……其他事情比如双人复核流程、审批流程、文档处理。

<details><summary>Original English</summary>
context, but a volume game. Other things like Other things is like maker-checker processes, approval processes, document processing.
</details>

这些对于许多机构来说都是跑量的事情。所以我猜想对于这里的金融机构来说，既然我们在纽约，大量的 OCR、大量的文档、大量的审批、大量的交易风险……都是属于这一类。

<details><summary>Original English</summary>
These are all volume game for multiple organizations. So I suspect for the financial institutions here, since we are in New York, a lot of OCRs, a lot of documents, a lot of approval, a lot of transaction risk the is is under this category.
</details>

好的。

<details><summary>Original English</summary>
Okay.
</details>

所以是的。

<details><summary>Original English</summary>
So yeah.
</details>

如果你目前还没有追踪你的 token 支出和 token 视图拆分，对吧，我们正在开源一个 token 经济学追踪工具，这其实只是一种非常花哨的说法，用来指代拆分你的 API 密钥并追踪哪个 API 密钥花费了多少，这和本次演讲是分开的。是的。

<details><summary>Original English</summary>
If you're not yet tracking your token token spend and token view split, right, we are open sourcing a tokenomics tracking tool, which is just a very fancy way of like splitting up your API key and tracking which API key spends how much, which is separate from this talk. Yeah.
</details>

所以如果你……如果你想再次更新它，欢迎扫描这个二维码，分别对应相应内容。此外，如果你想要这次演讲的幻灯片，以及当 AI Engineering 发布录像时收到关于这次演讲的通知，你也可以在那里填写表单。

<details><summary>Original English</summary>
So if you If you want to again update it, feel free to to scan this QR code and respectively. It also if you want to slides for this talk and when the recording is released from AI engineering to be notified about this talk, you can also get fill up the form there.
</details>

好的。

<details><summary>Original English</summary>
Okay.
</details>

好的。好的。

<details><summary>Original English</summary>
Okay. Okay.
</details>

所以是的。

<details><summary>Original English</summary>
So yeah.
</details>

### 模型选型与开源进展

那是关于衡量的。嗯，是的。如果你不进行衡量，你基本上可以忽略我说的其他所有内容，先从衡量开始，因为你最大的投资回报率光靠衡量就能获得。但是一旦你衡量了各项指标，对吧，问题就是你如何确定合适规格？这就是事情变得更复杂的地方。呃，总体而言，对吧，随着 AI 在机构内规模化部署，我们开始观察到的现象之一就是，有一种模式倾向于出现：因为 AI 是那把崭新的锤子，我们就试图把它敲在所有东西上。特别是在创新实验室内部，我们就是试图把它应用在所有见鬼的事情上。而且我们往往……而且我见过有些机构真的把 fable 应用在极其愚蠢的事情上。所以……所以模型非常多，而且很多模型都非常昂贵，摸清该怎么做以及它适合放在哪里是一个……是一个重要的步骤。

<details><summary>Original English</summary>
That was about measuring. Um yeah. If you are not measuring, you can pretty much ignore everything else I say and start with measuring first because all your biggest ROI is just by measuring. But once you have things measured, right, the question is how do you right-size it? And this is where things gets more complicated. Uh In In general, right, one of the things that we start to observe as as AI gets deployed at scale within organization is that there tends to be a pattern of like because AI is the shiny new hammer, we try to apply it to everything. Especially within the innovation labs, we just try to apply to every damn thing. And we tend and and I have seen organizations literally apply fable to really the silliest of things. So so you there's a lot of models and a lot of models are really expensive and and and and and figuring out to do and where it fits is is is important is an important step of the process.
</details>

我知道开源模型……我是说你们很多人可能听说过开源模型，那是我们的业务范畴。

<details><summary>Original English</summary>
I know open models I mean a lot of you probably heard about open models and that's our line of business.
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

所以很多……当很多公司来找我们，比如寻找契合他们用例并可直接替代的开源模型时，我们通常会沿着他们的用例给他们提供指导。因此这些是……这些是大致的经验法则，很可能每个月都会更新，因为开源模型每隔几个月就会发布，闭源模型也是一样。

<details><summary>Original English</summary>
And and so a lot when a lot of companies come to us for example to like find open models that fit their use cases and drop in replacements. This is we generally guide them along their use cases. So these are these are general rule of thumb that is probably going to be updated month because open models release every few months and same thing close source models.
</details>

情况变化非常迅速。但是……但是有一点是，我们觉得实际上在今年让人感到兴奋的是，事情已经开始发生变化了。比如在去年，最好的闭源模型毫无疑问比最好的开源模型更好。几乎一直如此。

<details><summary>Original English</summary>
Things change rapidly. But but there but the thing is what we find right exciting actually within this year is things have started to change. Like in the previous year the best close source model is without better than the best open source. Almost.
</details>

但随着今年临近，对吧，我们开始看到差距在缩小。我们开始看到某些开源模型甚至不相上下，乃至超越的情况。比如在 Opus 5.5 更新发布之前，Kimi K3 在 UI 设计方面、在某些 UI 基准测试中击败了 Opus。

<details><summary>Original English</summary>
But as this year approach right we are starting to see the gap close. We are starting to see situations where where some of the open models are even on par or even surpassing. So like for example before the Opus 5.5 update came out Kimi K3 was beating Opus in UI design in some of the UI benchmarks.
</details>

而且……而且这是非常公开的基准测试。在客户的基准测试中，对吧，我们已经开始看到开源模型在特定用例的非常专业的基准测试中胜出。举一个特别需要强调的例子，比如 step 1 5 模型，它能够在金融基准测试……呃，金融用例中达到接近 Opus 和 extra 的质量，尽管它是一个体量小了 10 倍的模型。这……它是最好的代码模型吗？不是，但在那个用例中，它实际上极其强大且称职。

<details><summary>Original English</summary>
And and this is like very public benchmarks. Within customer benchmarks right we were already starting to see open source models beat very specialized benchmarks in specialized use cases. So like A particular one to highlight is like for example, step one five model. They it was able to achieve near Opus and extra quality despite being like a 10 x smaller model in financial benchmarks uh financial use cases. And this is it the best coding model? No, but in that use case, it's actually extremely strong and competent.
</details>

所以……所以格局正在慢慢发生变化，如果你了解自己的工作负载，你可以在很多用例中获得直接替代方案，有时成本甚至只要原来的十分之一，分别对应……呃，如果你了解自己的工作负载，你就可以分别直接换上它。

<details><summary>Original English</summary>
So so so the landscape is slowly changing where where where you can have drop-in replacement for a lot of use cases that are sometimes even just 10 x cheaper respectively for the uh uh if if you know your workload and you can drop it in respectively.
</details>

还要特别提一下 DeepSeek-V4 和 Flash。出于某种原因，这个模型在所有工作负载中都极其受欢迎，分别因为对于许多公司来说，它在那里的提示词很容易写。因此，虽然……虽然我列在那里的其余模型在各自的类别中都属于默认很优秀的，但 DeepSeek-V4 和 Flash 似乎不管什么情况都相当受欢迎。是的。呃，尽管基准测试得分似乎并不能合理解释为什么……为什么它会如此受欢迎。

<details><summary>Original English</summary>
Special shoutout is also DeepSeek-V4 and Flash. For some reason, and this model is extremely popular across all workloads respectively because it's easy to prompt there uh for a lot of companies. So well I well the rest of the models I have listed there they are they are like default for good in their categories. DeepSeek-V4 and Flash seems to like be quite popular regardless the case. Yeah. Uh though benchmark score doesn't seem to justify why why is it so popular.
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

是的。呃，另外要强调的一点是，对吧，就在最近，也就是几周前，呃……一类新的 AI 模型被引入了，被称为分类器、单样本分类器，最广为人知的是 JAF。开源项目已经开始兴起，比如 simple JAF。这些模型完全专注于只对任务做出决策和分类。呃，主要优势在于，仅从技术层面而言，它们通常比现有模型便宜 10 倍，或者同时速度更快。呃，缺点是它无法给出对话回复。所以……所以这些是正在发生和改变的事情，大家可能想要开始去研究，比如在如何改进自身 token 经济性的不同细分环节上去研究。

<details><summary>Original English</summary>
Yeah. Uh another thing to highlight, right, is that recently like and this is like for a few weeks ago, uh the a new class of uh AI models have been introduced called uh classifiers one-shot classifiers most popularly known as JAF. Open-source projects have already started uh taking off like simple JAF. And these are models that are entirely focused on just making decisions and classification on on tasks. Uh the main advantage is that because on a technical level only, they are commonly 10 x cheaper than existing models or even faster at the same time. Uh the downside is it cannot give a chat response. So so so these are things that are changing and happening that you all may want to start looking into on like on like segments of how you want to improve your your token economy.
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

### Agent 场景下的成本拆分与混合架构

但……但回到 token 经济那部分，有两个主要轨道，分别将它们拆分出来并进行追踪是很重要的。在 Agent 方面，正如我之前所说，我们谈论的是长时间运行、长上下文。而且你必须明白，这种工作负载往往是极其依赖缓存的，极其依赖输入预览和缓存，并且只有一小部分输出。我们在部署的 Agent 用例中看到，只有 1% 的请求属于输出 token。而且……而且这是非常合乎逻辑的，因为它需要多轮交互，不断循环重复。

<details><summary>Original English</summary>
But but back to the The the the token economy part, there is two major tracks and it is important to separate out and track this track them respectively. It on the agentic side we're talking about long running long context as I said earlier. And to and you have to understand this workload tends to be extremely cash heavy, extremely input preview heavy and cash heavy and there's only a small percentage of output. We see across like agentic use use cases in employment only 1% of the request is to the output tokens. And and and this is this is very logical because it takes multiple turns, rinse and repeat.
</details>

但这同时也决定了你的 token 成本，因为如果你看过 token 成本，对吧？部署成本，对吧？输出的数值可能是最大的，但即使你的输入值要小得多或者缓存费用要小得多，在这个用例中它也会被大量重复。

<details><summary>Original English</summary>
But this also decides your token cost because like if you've seen token cost, right? Deployment cost, right? Output is may have the biggest number, but even your input value is much smaller or the cash is much smaller, it it gets repeated heavily in in this use case.
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

这虽然不是编程 Agent 研讨会，但我们在许多机构中看到的最常见模式之一，对吧？就是通常……通常在尝试于编程团队内部扩大其 AI Agent 部署规模方面，对吧？他们往往让最好的 Agent 负责规划，让一个更快速、更便宜的 Agent 负责执行实现，然后再让最好的 Agent 负责审查。这种划分在所有 Agent 框架中都非常普遍，是有充分理由的，那就是你能兼得两者的优势，因为实现阶段往往是一个非常消耗 token 的过程。很多流程来回重复，比如不断修改文件、测试、检查结果、循环重复。而且……而且这些 Agent 大多数，尤其是像 Gemini 5.3 Flash 这样的模型，完全有能力以与强大得多的 Agent（比如 Astra 或 Opus）相同的质量水平来完成任务，前提是假设由那些 Agent 来负责规划。我们曾与一些机构合作，其实际做法就是规划和审查 Agent 使用顶尖的前沿闭源模型，而负责实现的 Worker 则是以 GRM 5.3 Flash 为例，或者是 DeepSeek 4.1 Flash。

<details><summary>Original English</summary>
This is not coding agent workshop, but one of the most common patterns that we we see in a lot of organizations, right? Is that is that typically typically in terms of like trying to scale up their AI agent deployments we within within the coding teams, right? They tend to have the best agent do the planning and a faster a faster cheaper agent do do the implementation and then maybe the best agent do the review again. There's a good reason why this split is very common across all the agent frameworks is is that you get the best of both worlds because like the implementation phase is tends to be tends to be very token heavy process. A lot of processes repeated back and forth like key modifying the file, testing, checking for results, rinse and repeating. And and you and most and most of these agents are especially this especially like Gemini 5.3 flash is more than capable of doing a task at the same quality level as a much more stronger agent like I say Astra or Opus, uh respectively assuming those agents do the planning. We have worked with some of the organizations where literally the planning and review agent is the best frontier close muscle model, and then the workers that implement it is the GRM 5.3 flash as an example, or Deep Seek 4.1 flash.
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

从这种划分模式中我们得出的观察之一，对吧，就是不幸的是，尽管我们多么希望每个人都这么做，但没有人会真正为了给公司省钱而去切换他们的模型。呃，大家普遍都懒得去切换模型。你……你必须提供切换的动力。或者……或者另一种方式，如果你的 Agent 控制运行架构足够好，比如像 M 这样的某些架构，它们把这个过程自动化了。比如它使用较弱的模型作为基线，然后当需要更聪明的咨询时，它使用更聪明的模型来自动化切换。

<details><summary>Original English</summary>
One of the observations that we made from from this from from this kind of split pattern, right, is that unfortunately, as much as we wish that everyone does so, nobody really switches their model to save the company money. Um this people are lazy to switch the models in general. You you want to give an incentive to switch. Or or alternatively, if your agent harness is good enough, so like for example, some harness like M, they automate the process. Like like it uses a the weaker model as a baseline, and then it uses a big the smarter model to automate switching when it needs a smarter consultation.
</details>

这……这有助于减少相应的阻力，并有助于在用户规模上改善你的 token 经济性。比如我们在经历了多次之后现在给客户的一个主要经验法则就是，你希望以更聪明的模型……既然它作为基线已经如此昂贵，但你……但你希望更快的模型、更便宜的模型速度更快。这自然就形成了一种动力。人们希望快速完成工作。如果该模型足够聪明能够完成任务，并且

<details><summary>Original English</summary>
This This helps reduce the friction respectively, and helps improve your your token economics at user scale. Like a a major rule of thumb that we we now give our clients after going through a few times is that you want the smarter model, and since it's already so expensive as a baseline, but you but you want the the faster model to the cheaper model to be faster. And that naturally sets an incentive. People want to get their work done fast. If the model is smart enough to get it done and
</details>

<!-- chunk 3/7 -->

更便宜，他们就会仅仅因为速度更快而使用它，而不是因为更便宜。嗯，我们遇到过一些团队，其中更聪明的模型和更便宜的模型都维持在相同的每秒 token 生成速度，而且只要他们有多余的 token 预算，对吧，就没有任何人切换。

<details><summary>Original English</summary>
it's cheaper, they will just use it because it's faster, not because it's cheaper. Um we had teams where where where both models were the smarter one and the cheaper one was maintained at the same tokens per second speed, and it and as long as they had the token budget in excess, right, no one switched.
</details>

而在另一方面，我们也见过一些走向另一极端的团队，他们把预算定得极低，以至于如果他们使用更聪明的模型，对吧，一天之内就会把它耗尽。对，然后所有人就都切换到……切换到更笨……切换到更快的模型，更笨且更快的模型，因为那就是他们的预算。就好像那个更聪明的模型根本不存在一样。所以，要留心你的团队在切换模型时的动态。最好的权衡点就是速度，因为人们天生就对它有积极性。所以，更快速、更便宜，他们就会相应地直接切换过去。是的。

<details><summary>Original English</summary>
And it and on the flip side, we have seen teams, which is the other extreme, where they set an extremely low budget, and so that if they use a smarter model, right, they just burn it in one day. Yeah, then everyone just switch to the to the Dharma into the faster model Dharma and faster model because that's their budget. It's like almost as if the smarter model didn't exist. So, like be aware about your team dynamics on how they switch. The The best trade-off is to speed because people are naturally incentivized for it. So, faster, cheaper, they will just switch it to it respectively. Yeah.
</details>

再次提醒，要衡量，并且你要衡量两个单独的 token 密钥。呃，但这还不仅限于测量。例如，像 CI/CD 现在就是一个非常常见的在后台运行的用例。呃，我们曾帮助团队进行配置，比如为用户（也就是人类）运行每秒 token 速度更快的配置，但为 CI/CD 流水线以规模化运行每秒 token 速度慢得多、但也便宜得多的配置。呃，这纯粹取决于你在各项任务中的优先级分别是什么。是的。而且你可以在密钥级别对其进行控制。

<details><summary>Original English</summary>
Once again, reminder, measure, and you measure two separate token keys. Uh and but this also goes beyond just measuring. For example, like CICD is a very common use case right now of things running in the background. Uh we we have helped set up for teams like faster tokens per second that that is running for the the users, like the humans, but much slower tokens per second um speed, but much cheaper at scale for the CICD pipeline. Uh and and this is just the nature of like what's your priority respectively respectively across the task. Yeah. And you can control that at a key level.
</details>

### 模型命名与控制策略

所以，另一个重大发现来自于我们为团队部署的经验，对吧？呃……呃……比如，对于某些公司，呃，你们中有多少人有过这种幸运或不幸的经历——CEO 说：“所有人现在都必须落地 AI，所有人现在都必须拥有第二大脑。”是的。多家组织已经开始了这一进程。呃，在某些情况下，比如在阿联酋，这甚至完全成了国家法律所规定的要求。所以，很多部门根本没有准备好去了解各自的权衡取舍是什么。

<details><summary>Original English</summary>
So, another major finding is that we had experience with deploying for for teams, right? Uh uh So, like for example, for some companies, uh how many of you had the fortunate or unfortunate experience of the CEO saying, "Everyone must implement AI now, and everyone must have a second brain now." Yeah. Multiple organizations have started this. Uh in some cases, like even in in the UAE, it became literally mandated by by by by the law of the country. So, so, like a lot of departments are not prepared to know what is the trade-off respectively.
</details>

所以，一个好的经验法则，对吧？虽然开发者往往知道，好吧，在所有这些聪明的模型中，比如 DeepSeek Flash 和 GR553 之间的权衡取舍是什么，但你的财务部门完全不知道。你的支持部门完全不知道。他们只会选第一个模型，很可能就直接用它了。所以，我们的通用经验法则是：给部门模型赋予标签，而不是模型名称。这也会在你替换模型时赋予你多得多的控制权。

<details><summary>Original English</summary>
So, a good rule of thumb, right? Well, developers tend to know, okay, all these smart models, what's the trade-off uh between deep seek flash and GR553, for example? Most uh your your finance department have absolutely no idea. Your your support department has absolutely no idea. They they'll just pick whatever's the first model and probably just go with it. So So, our general rule of thumb is that give department models labels, but not the model names. And this also gives you a lot more control as you switch it out.
</details>

呃，就像之前建议的那样，比如“快速”对“聪明”，但在某些情况下也可以像“财务 Agent”或“Excel 表格 Agent”。嗯，这些是针对那些任务分别微调的高专业化 Agent。这也会带给你多得多的控制权。它允许你替换模型。它允许你切分流量并在其间进行测试，而无需通知说：“嘿，用户们，请尝试这个。”其缺点也是，有时当你这么做并且搞砸了的时候，用户可能会抱怨。但拥有这种控制权是一件好事。呃，即使你这样做，我们看到的另一种模式也许是某种带有短横线的 preview 版本。所以，那是它的一种变体，但它能在不增加跨组织沟通负担的情况下给你控制权。这一点极其重要，因为像我们合作过的一些团队，对吧？我们切切实实看到有成员在我们谈论比如今年的时候还在运行 Llama 2 模型，因为没有人去切换选项。是的，所以你真的非常需要将这一点落到实处。是的。

<details><summary>Original English</summary>
Uh what like like advised earlier, fast versus smart, but in some cases also like finance agent or Excel spreadsheet agents. Um these are hyper-specialized agents that were fine-tuned to those tasks respectively. And and this also gives you a lot more control. It allows you to swap up the model. It allows you to split split the traffic and test in between with without without telling, "Hey, users, please try this." The downside is also users may sometimes complain when you do that and you screw that up. But having that control is a good thing. Uh another pattern that we see, even though you do this, is maybe some of a dash preview version. So, that's a variant of it, but it gives you control without without taxing the communication burden across the organization. And this is extremely important because like like some of the teams that we work with, right? We literally saw members running Llama 2 models when when we are talking when talking about like in this year because no one switched the option. Yeah, so you really really need to need to uh need to set this in place. Yeah.
</details>

### 流程跟踪与模型选型

好的。流程跟踪。流程跟踪。我之前提到的很多事情在流程跟踪上其实并没有那么适用，因为流程跟踪往往在很大程度上分别集成到了应用程序和工作流之中。这纯粹是由于流量的巨大规模所致。嗯，是的。在流程跟踪的所有团队中，对吧？呃，他们往往默认已经更加专注于尺寸匹配，因为如果你正在运行数万亿个 token，大多数部门是不会批准像每百万 token 10 美元这样的成本的。这根本不可能。所以，他们很早就开始进行评测、基准测试，随后寻找尺寸合适匹配的模型。呃，是的。

<details><summary>Original English</summary>
All right. Process track. Process track. A lot of things that I mentioned earlier don't really apply as much to process track because process track tends to be a lot integrated into the applications, into the workflows, uh respectively. And and that's just by the sheer volume of the traffic. Um yeah. And And of all of teams in the process track, right? Uh they tend to be a lot more focused on focused on the right sizing already by default because because if you're running like trillions of tokens you most departments will not approve it like $10 per token million token. It's just not possible. And and so so so they start they start early with the evals, the benchmark, and then subsequently finding the model that right size fits it. Uh yeah.
</details>

所以，问题在于常见的疑问是：我怎么知道更小的模型是否足够好？你不需……这么问就问错问题了。你只需要确保设置好你的测试用例、你的评测和你的示例。随后直接从那里开始搜索过程。呃，像我们这样的公司会非常乐意帮助你，因为我们拥有超过 40,000 个模型。但话又说回来，直接从 Hugging Face 下载 10 个模型直接尝试，其实也没那么难。呃，所以从那里开始，你进行搜索，找到基本上能通过大部分测试的最便宜模型，然后看看如何从那里进行迭代，从那里进行微调。呃，我们还有一个更具体的流程，我认为这并非我们独有，我们接下来也会讲到。

<details><summary>Original English</summary>
So So the thing is like the common question is how do I know the smaller model is good enough? You don't need to That's the wrong question to say. You just need to make sure you set up your test cases, your evals, and your examples. And then subsequently just do the search process from there. Uh companies like us will be more than happy to help you because we have over 40,000 models. But then But then if you're It's also not that hard to just download 10 models from Hugging Face and just try. Uh So So from that you you just do the search, find the cheapest model that kind of like pass most of it, and then you just see how you iterate from there, fine-tune from there. Uh we also have a more specific process that I don't think is unique to us that we'll cover as well also.
</details>

例如，在我们合作过的一家主要电信公司中，对吧？我们实际上帮助他们的团队将推理成本从每月 25 万美元降低到了 7,600 美元，从现有的闭源模型切换过来，仅仅是通过走完这个流程：“好吧，你们先运行最好的模型。让我们看看我们可以拆分出哪些模型，随后我们可以放入哪些模型，然后有哪些是我们可以微调的？”而这是为了应对客户支持等各类用例。是的。

<details><summary>Original English</summary>
So for example, like in for one of the major telcos that we work with, right? We actually helped their team lower their inference cost 250k to 7.6k a month switching from existing close-source model just by going through this process of like, "Okay, you're running the best model first. Let's see what what models we can split off, and then subsequently what's the models that we can fit in in, and then what can we fine-tune?" And this was This was like to uh beat the customer support use cases and and so on and so forth. Yeah.
</details>

再次着重提一下 Jeff，呃，以及 Simple Jeff——那是我们做的一个复刻它的开源项目。你会对你的 AI 流量中有多少百分比是分类流量感到惊讶。呃，归根结底，对吧？是的，当然。回答客户支持是文本形式。但即使在那时，对吧？即使在那时，很多团队在大多数情况下其实已经在放入模型的上下文中预定义了文本输出以供其输出。而你在那里可以使用分类器。这在 AI 领域是一个全新的转变。对于此类流程而言，这是降低你的 token 账单的一大杠杆。是的。

<details><summary>Original English</summary>
And to re-highlight back Jeff uh and simple Jeff, which is a open-source project that we did uh that replicates it. You'll be surprised at how many m- percentage of your AI traffic is classification traffic. Uh At the end of the day, right? Like Yeah, sure. Answering the customer support is text. But even then, right? Even then, right? A lot of teams, right? Already have predefined text output that they put into the context for the model to output for most cases. And and you could use a classifier there. And there's a lot This is a new new new shift within AI world. And that this is one of the big levers for this kind of processes in lowering your your token bill. Yeah.
</details>

### 领域模型微调案例

那么，关于微调，这里有一个此类模型的例子。许多模型和流程，对吧，在达到这种规模时确实会受益，此时你开始微调自己的模型。呃，另一方面，对于代码模型，虽然有组织会为你微调模型，比如 Devin。呃，很多开发者通常只想要最好的模型。因此，除非你身处这个 AI 领域，否则在微调出最佳代码模型方面是挺难跟上步伐的。但在另一方面，对于你的领域，为你的用例微调一个领域模型可能是值得的，尤其是如果该模型要小得多的话。

<details><summary>Original English</summary>
So, one one one example of such a model when it comes to fine-tuning. So, a lot of models and processes, right? Uh do benefit at this scale where you start to fine-tune your own model. Uh on the flip side, for coding models, well, there are organizations that will fine-tune models for you, like Devin, for example. Uh a lot of developers generally just want the best model. So, it's kind of unless you are in this AI space, it's kind of hard to keep pace in fine-tuning the best coding model. But on the flip side, for your domain, it might be worth it to fine-tune a domain model for your use case, especially if the model is much smaller.
</details>

比如以 AT&T 为例，当他们微调自己的模型时，他们从开放类别走向了比如 27B 甚至 7B 的模型。他们已经公开了这一点。所以，我们是他们的首发合作伙伴之一。你实际上可以分别尝试他们的开放对话模型。这基本上就是他们在幕后使用的东西。这里完全取决于体量。我觉得大多数人都理解 AT&T 的规模、呼叫中心之类的体量。呃，是的。但这是一个关于如何微调模型以适应专用用例的极好例子。一旦你达到了那个阶段，

<details><summary>Original English</summary>
So, for AT&T, for example, when they fine-tuned their models, they they they went from being open class to like 27B to even 7B models. And they have published this. So, so we were one of their launch partners. And you can actually try their open dialogue models respectively. And and This is basically what they use behind the scene. And and it's all about volume here. Like, I I think I think most of you understand the scale of AT&T and the call centers and things like that. Uh yeah. But it's a good example of how you fine-tune models to to specialize use cases. And once you reach that point,
</details>

其他作为主要代表的组织，像 Shopify 也已经开始这样做了。而且这并不一定需要是大规模的微调。举例来说，在 Shopify 的用例中，他们这样做是因为 Shopify 网页商店有一种专有的编程语言，用于如何配置网页商店。而现有的模型在处理它时并不是那么出色，因此他们便去对其进行了微调。呃，但是 AT&T 也有类似的例子，呃，特别是在比如如何布置信号塔之类的事情上。是的。呃，非常特定于电信行业的任务。我

<details><summary>Original English</summary>
other organizations that are major example of like Shopify have started doing this. And and things and and it doesn't necessarily need to be a large-scale fine-tune. So, for example, in the Shopify use case, they did it because Shopify web store had a proprietary la- programming language for how to configure the the web store. And the existing models just weren't that great at it, so they went to fine-tune it. Uh but and AT&T also they had examples of that uh in particular on like how to arrange the the cell towers and things like that. Yeah. Uh very telco-specific task. I
</details>

<!-- chunk 4/7 -->

可能并不是回答那个问题的合适专家。呃，但他们确实有那些用例。所以……所以他们分别进行了微调。

<details><summary>Original English</summary>might not be the right expert to answer that question. Uh but they had those use cases. So so they fine-tuned respectively.</details>

你可能也会有那……那些用例。那么你该如何冷启动（bootstrap）这样一个模型呢，对吧？好消息是，呃，现在你可以很轻松地把事情冷启动起来，因为假设如果最强的模型……如果那个大规模运行起来过于昂贵的最强模型能够完成这项任务，你就可以着手开始了。所以……所以一个很简单的做法，对吧？呃，我们非常常见的做法就是：要么你自己生成数据，要么自己准备数据，但这很难。

<details><summary>Original English</summary>You too may have that those use cases. And how do you bootstrap such a model, right? Is that the good news is that uh you can easily bootstrap things these days because if let's say you're willing uh if the best model that is too expensive to run at scale can do the task, you can already get started. So so so an easy way to do this, right? Uh that we see very commonly is like either you generate your own data or prepare your own data, which is hard.</details>

出于某种原因，没人喜欢做这件事。但另……但另一个常见的路径是，他们从一个昂贵、前沿的模型开始，然后进行小规模部署，接着他们生成……他们生成数据集。我知道对于某些实验室来说，这样做是违反他们服务条款的，所以你可能需要去跟你们的律师核实一下，但也有一些实验室是公开支持这一做法的。例如，Google Gemini，呃，他们的……他们的前沿模型，他们就切实提供了一个专门针对此用途的 API 服务。呃，所以……所以这能让你基于一个强大的模型，针对你的用例分别构建出数据集，然后你可以将其大幅缩减至比如 7B 规模。呃，另外，开源模型非常乐意让你去……去运行并在其上进行蒸馏，因此你也可以分别去运行那些最顶尖的开源模型。收集好这些数据后，你就可以对数据进行微调，然后你可以在……分别在不同尺寸的模型上进行微调，来看看哪种尺寸最合适。所以，再次以那个 80/20 的例子来说，他们针对呼叫中心的不同层级分别采用了 27B 和 7B 模型。

<details><summary>Original English</summary>No one likes to do that for some reason. But that but another common path is that they start with an expensive model and then they deploy in a small scale and then they generate they they generate data set. I understand that some labs it's against their terms of service to do that, so you may want to check with your lawyers, but there are labs that openly embrace it. So, for example, Google Gemini uh their their frontier models, they literally have a dedicated API service for this. Uh so so so this allows you to build data sets respectively on your use case on a strong model, which you can then which which you can then reduce dramatically to let's say a 7B scale. Uh alternatively, open-source models are more than happy for you to to to run and distill on, so you can run the best uh open-source models respectively as well. Once you collect them, you can then fine-tune the data and then you can fine-tune and respectively like different sizes to see what fits best. So, once again, like in the 80/20 example, they have the 27B and 7B for different levels of the call center.</details>

比如你的常规……你的常规呼叫可能会由……等等。我觉得我不能说哪个尺寸用在具体哪个环节，但是你的常规呼叫可以由小得多的模型来处理，然后如果触发了某些分类器规则，就会升级向上流转，这只是举个例子。

<details><summary>Original English</summary>Like your routine your routine calls may come in at a Wait. I don't think I can say which size goes where, but your routine calls can come in for the much smaller model, and then it escalates up due to some classifier triggers as an example.</details>

然后……所以……所以这就是你如何引导流量流转、实现流量分流，从而达到那种高效水平的方式。呃，我们在此过程中往往还会与团队合作的一件事是，即便……即便他们经历了各个阶段，把全部流量彻底切换到了微调模型上，由于那些最最顶尖的模型仍在不断进步，呃，他们会……呃，我们通常会建议他们切出一部分流量作为影子流量（shadow traffic）发送给最顶尖的模型，以持续构建数据集。这……这能让你分别跟上那些最佳开源模型的发展浪潮与进展。

<details><summary>Original English</summary>Then then so so so that's how you get the traffic to flow, get the traffic split, and then you get it at that efficient level. Uh one of the things that we also tend to work with teams on on when doing this is that even even when they go through the stages and they completely split over their traffic to the fine-tuned model, because the best of the best models still progress, uh they get they uh we typically advise them to cut over a cut a part of their traffic as a shadow traffic to the best model to keep building the data set. And and and this allows you to ride the wave and progress of the best open models respectively.</details>

呃，这里的单位经济效益其实非常关键，因为我想提醒大家的一点，对吧，就是人们严重低估了……低估了 AI 发展的速度，尤其是对于那些你能够在大规模下以低得多的成本运行的模型。比如就拿这台笔记本电脑为例。我喜欢去衡量，对吧，我在目前这里能买到的最贵的 MacBook Pro 上，能跑的最强模型是什么。而现如今最好的模型，不论是 31B、32B 还是 27B 大小的 MoE 模型，都已经远胜于 GPT-4 了。

<details><summary>Original English</summary>Uh and the unit economics is actually very important here, because like one thing that I would like to remind people, right, is people severely underestimate the the the speed that AI is going, especially for models that you can run much cheaper at scale. Like you take this laptop as an example. I like to measure, right, what is the best model that I can buy in the most expensive MacBook Pro here. And today's best models, be it MoE models at 31B, 32B, 27B size, is already much better than GPT-4.</details>

所以，基本上，这个能在笔记本电脑上运行的模型，已经比你去年所拥有的最好模型还要好了。大致而言。人们总喜欢就细节争论不休，但我们就大体上这么说吧。而当你把它针对你的任务进行微调后，那意味着如果你能分别在笔记本电脑上运行该模型，你就能在……在你大规模的 GPU 服务器上更加高效地运行它。是的。

<details><summary>Original English</summary>So, essentially, this model that can run on a laptop is already better than the best model that you have last year. Give and take. People like to argue on the specifics, but let's just say broadly. And when you fine-tune it to your task, that means if you can run that model on a laptop respectively, you can run it on on on your GPU servers at scale much more efficiently. Yeah.</details>

### 购买 GPU 与速度成本权衡

所以，是的。那么这就引出了下一个话题：采购 GPU，这显然正变得越来越具挑战性。所以，是的，这正是像我们这样的公司发挥作用的地方。

<details><summary>Original English</summary>So, Yeah. So, that brings in to the next topic, buying GPUs which which which is apparently increasingly a challenge. So, yeah, that's where companies like us come in.</details>

我们……我们通过大量的客户沟通意识到的情况之一是，人们对事物并非线性扩展感到相当惊讶。呃，我这么说的意思是，单个请求的每秒生成 token 数（tokens per second）与该请求本身的成本之间存在着巨大的权衡。举例来说，如果你不在乎……不在乎成本，你可以把最……把模型（假设是一个固定模型）运行在最好的硬件上，占用全部 8 块 GPU，batch size 设为 1，你可以获得比如每秒 100 个 token、每秒 200 个 token。如果你……如果你真的想要——而这并不是我们的专长领域——如果你真的想要达到每秒几千个 token，那像 Cerebras 这样的公司也非常乐意提供这样的服务。而它的成本还要更高。所以，确实有一些用例适合这么做。

<details><summary>Original English</summary>One of the things that we we realized through a lot of customer conversations, people are rather surprised that things don't scale linearly. Uh what I mean by that is like there is a huge trade-off between tokens per second on an individual request to to the cost to the cost of the request itself. So, for example, if you do not care about about the cost, you could run the best the model, let's say a fixed model, on the best hardware, on all eight GPUs, batch size one, and you could get, let's say, 100 tokens per second, 200 tokens per second. If you like if you really want and and and this is not our specialization, like you really want like thousands of tokens per second, that's where companies like Cerebras is more than happy to offer that as well. And it costs even more. So, there are definitely use cases where this makes sense.</details>

但是，很多人都陷入了一个思维陷阱，以为“嘿，既然我获得了这个速度，也许成本只要一半呢”。差得远呢。就像……就像我有时常说的一条经验法则：“速度每提升 2 倍，成本就要增加 3 倍，而且这是复合累加的。”

<details><summary>Original English</summary>But, it's but a lot of people fall into the trap of thinking, "Hey, so if I have the speed, maybe it's half the cost." It's not even close. Like like a rule of thumb that I sometimes say like, "For every two x of speed, it's three x the cost and it compounds."</details>

以 JM 5.3 的这个具体示例来说，就像一个 JM 节点，你可以看到在同一台服务器上，处理单个请求时是每秒 112 个 token。但是，如果你并行运行 16 个请求，所有请求的速度大约会降低一半，但你切切实实将输出……总输出提升了 10 倍。你……而……而这能让你实打实地将成本降低大约 9 到 10 倍。仅仅通过改变你……改变你的目标速度特征配置即可。

<details><summary>Original English</summary>In this specific example for JM 5.3, it's like one JM node is like you can see the same server, 112 tokens per second for running individual requests. But, if you run 16 requests in parallel, you get about half the speed for all the requests, but you literally 10x the output total output. You And and that that gives you like literally around 9 to 10x lower in cost. In just like changing your changing your target speed profile.</details>

所以，当很多客户询问我们“我们该如何进行大规模部署？”时，有时候第一个问题就是：“你想要的模型质量是怎样的？你想要的每秒 token 数速度是多少？”然后我们才开始推荐 GPU 的数量与部署规模。而这个……这个目标每秒 token 数是一项关键的权衡取舍。

<details><summary>Original English</summary>And so, when a lot of customers ask us like, "How do we deploy things at scale?" Sometimes the first question is, "What's the model quality you want? And what's the tokens per second speed that you want?" And then we start recommending the amount GPUs, the amount deployment. And this this target tokens per second is an important trade-off.</details>

本质上，嗯……在更极端的情况下，对吧？如果你真的、真的能够以每秒 10 个 token 的速度运行——极少有人这么做，但确实存在一些允许这样做的奇特用例。你分别可以获得更加惊人的总……总吞吐量规模。通常，我们看到客户在 20 到 30 之间做选择，这有点类似于……呃，不需要过多思考时的 ChatGPT 速度，一直到像 60 这样的最快速度。如果他们想要 120 个 token，通常……往往就是这个区间。大多数人会保持在 20、30 到 60 之间，具体取决于任务链路的长短。是的。

<details><summary>Original English</summary>Essentially, um in more extreme cases, right? If you really, really can run things at 10 tokens per second, rarely anyone does, but there are some weird use cases that allows it. You can get even more incredible to- total throughput volumes, respectively. Typically, we see customers choosing between 20 30, which is kind of like uh your chat GPT speed without without too much thinking, all the way until like 60, which is like the fastest speed. And if they want 120 tokens like it tends to be this this range. Most stick between 20 30 to 60, depending on how how long the chain of task is. Yeah.</details>

所以，是的，呃，我之前其实提到过，你通常只有在面向某个人的时候，才愿意为那种每秒 token 数的高速度付费。呃，无……无论面对的是你的开发者，还是面对你的客户。这些都是你需要去做的权衡。而且即便在那时，对吧？我们也见过有些案例，哪怕只是稍稍调低一点点，对吧？就能轻松节省 2 倍的成本，但对客……呃，对客户的影响微乎其微。是的。

<details><summary>Original English</summary>So, yeah, uh I kind of mentioned you generally only want to pay for the tokens per second speed uh when when it's in front of someone. Uh whe- whether it's in front of your developers or whether it's in front of your customers. Those are the trade-offs that you want to make. And even within then, right? We have seen cases where even just a slight tweak down, right? Can easily save two times the cost, but has near minimal impact for the cus- uh customer, respectively. Yeah.</details>

再一次强调，后台作业，请千万不要以每秒 120 个 token 的速度运行。你那么做完全没有任何意义。是的。

<details><summary>Original English</summary>And once again, background jobs, please don't run it at 120 tokens per second. It makes no sense when you do that. Yeah.</details>

### 流量模式与专用实例部署

所以，呃，一旦你拥有……前面我说过要衡量，对吧？你就能够看清你……你的流量模式。很多流量模式往往天然带有某种突发性，同时伴随着一定的基础负载，因为总有人在某个时刻运行着某些东西，呃，尤其是后台智能体（background agents）。而……而这正是你可以……你也可以据此来规划你的部署的地方。呃，我知道由于我们正在做金融相关业务，很多金融机构可能没有这个选项，因为他们仅采用专用实例部署，但在某些允许混合模式的场景下，他们会使用专用实例，并带有一些向公有云突发扩展的弹性，这正是你拥有一定灵活性的地方。因此，如果你清楚自己的基础工作负载，目前市场上你能获得的最大成本节省就是部署专用实例。

<details><summary>Original English</summary>So, uh once you have Previously, I said measure, right? You're able to see your your your traffic pattern. So, a lot of traffic patterns tend to be bursty in some nature with some base load because someone's always running something at some time, uh especially background agents. And and this is where you can you can also plan your deployments, respectively. Uh I know it since we're are doing financial a lot of financial may not have this as an option, but because they are only dedicated instance deployment, but if for some cases where people allow mixed where they have dedicated instances with some burst to the public cloud, this is where you have some flexibility respectively. So, like the biggest cost savings you have right now in the market is deploying a dedicated instance if you know your base workload.</details>

所以，只要你充分利用它，你就能在那里获得某种程度的成本节省。不过，根据你的流量模式不同，情况会更复杂一些，而且很多这类事情都可以分别进行测试和验证。这……这本质上是任何一家推理公司都会与你合作开展的工作。这并非我们所独有。我们会说：“嘿，这是……你知道你的流量负载情况吗？你能分享一些数据吗？”随后我们会说：“好的，我们建议采用这个额度。你可以尝试切换到这个方案。”接着我们……我们生成……我们通常可以分别向你展示你能节省多少成本。而在一些出现大量流量突刺的极端情况下，你可能希望将你的专用容量限制在一定数额，并让那些突刺流量溢出……

<details><summary>Original English</summary>So, as long as you fully use it, you kind of have a savings there. But, it's a bit more complicated depending on your traffic pattern, and a lot of these things can be tested and validated uh respectively. And this is like essentially what any inference company will work with you. It's not unique to us. We'll be like, "Hey, this is Do you know your traffic workload? Can you share some data?" And then subsequently, we'll be like, "Okay, we propose this much. You can try switching to this." And then we we generate we can generally show you your savings respectively. And in some extreme cases where you have a lot of spikes, you may want to have limit your dedicated capacity to a certain amount and let the spikes spill</details>

<!-- chunk 5/7 -->

各自转到公有云。

<details><summary>Original English</summary>
over to the public cloud respectively.
</details>

不同的用例有不同的合理规格配置（right sizing），但通过在一开始再次衡量你的 token 工作负载，你就可以开始探索这些选项，而且节省的费用可能会非常巨大。就像再次提到的，比如我们服务过的一个处理了 2 万亿 token 的客户，那是类似 4.8 Opus 级别的模型，他们每百万 token 支付的费用不到 0.03 美元。你无论在哪里都拿不到那个价格。是的。

<details><summary>Original English</summary>
The different use cases uh have different right sizing, but this is something that by measuring your token workload once again at the beginning, you can start exploring these options, and the savings can be huge. Like once again, like for the customer that we served two 2 trillion token, and that was like uh 4.8 Opus class model, they are paying less than 0.0 $3 per million token. Like you can't get that price anywhere. Yeah.
</details>

所以，是的。

<details><summary>Original English</summary>
So, yeah.
</details>

简单的免责声明是，突增峰值（spikes）确实很重要。极少数情况下会有人在极端情况下出现短暂的尖峰，比如他们每个月以那种规模运行一次工作负载，然后其他什么都不重要了。所以，通常都会存在一些基础工作负载。只是这个基础工作负载有多大的问题。是的。是的。

<details><summary>Original English</summary>
Simple disclaimer is the spikes really matter. Uh it's very rare that someone has a short spike at the extreme end where they like run a workload every month at that scale, and then nothing else matter. So, so usually some base workload exists. It's just how big of a base workload. Yeah. Yeah.
</details>

### 审视组织流程与 AI 瓶颈

所以，是的。那么最后一个是检查你的流程。从这里开始，这与推理优化完全没有关系了。

<details><summary>Original English</summary>
So, yeah. Then the last one is check your processes. Uh this has nothing to do with inference optimization from here onwards. Um
</details>

有些幻灯片听起来可能对 AI 非常挑剔，但我总体上是一个乐观主义者。只是我只想把这点说清楚，因为有些话可能会被断章取义。

<details><summary>Original English</summary>
Some slides may sound that very critical of AI, but I'm generally an optimist. Uh just this I just want to lay that out because things can be quoted out of context.
</details>

所以，我们开始看到的一个潘多拉魔盒式的问题或成问题的问题是，很多组织开始问：“嘿，我的 token 支出增加了 10 倍、100 倍，但我却没有看到相同规模的成效。”我们开始看到来自各个组织的报告，比如 AI 带来的生产力有限，只有 6% 或 7% 的生产力，这并不是我们许多人得到的承诺或我们所设想的规模。

<details><summary>Original English</summary>
So, one of the uh Pandora's Box question or problematic question that we are starting to see is that a lot of organizations starting to ask, "Hey, I'm s- 10x 100x in my token spend, but I'm not seeing results at that same scale." Um respect- like like we are starting to see reports from from various organizations like uh AI where AI has limited productivity only has 6% productivity or 7%, which is not the scale that a lot of us were promised or we envision.
</details>

而不幸的是，情况确实如此，因为我们正处于每个人都拿着一把大锤到处乱砸的阶段。并不是说 AI 没有用，只是我们往往把它滥用到处都是。是的，有时候我真想说：“你能不能别把它又做成一个 copilot？”因为这实在太多了。你需要分别思考该如何去使用它。呃，是的。

<details><summary>Original English</summary>
And and unfortunately, this is the case because we are at the stage where everyone's just taking a giant hammer and hammering everything. Um it's not that AI is not useful, it's just that we tend to just spam it everywhere. And yeah, if uh there's a s- there are times where I just want to like, "Can you please not do this as another co-pilot?" Because it's just too much of it. You need to think of how you use it respectively. Uh um yeah.
</details>

而我们开始意识到的另一个主要问题是，虽然 AI 正在以更大的规模和更高的频率被部署，人们在创造东西时变得更快，但组织的流程可能走得没那么快。编程环境的第一个瓶颈将是 CI/CD，你们可能都听说过 CPU 分别成为了瓶颈。另一件事就是现有的流程。你如何信任？你如何审查？我认为前一位演讲者详细谈到了信任。

<details><summary>Original English</summary>
And and another major issue that we start to realize is that well well AI's are are being deployed at a larger scale and more frequently, and people get faster in creating stuff, the organization processes may not go as fast. The first bottleneck for for coding coding environments will be the CICDs, and you all may heard that CPU becomes a bottleneck respectively. Uh another another thing is like is just the processes in place uh respectively. How do you trust? How do you review? I think the previous speaker spoke at length at trust.
</details>

是的，缺乏信任正是拖慢进度的地方。这可能是理所应当的。也许那个 AI agent 设计得很糟糕，不应该被信任。但反过来也是一样。假设那个 agent 完美地完成了一切，但人们不信任它，因为它没有配套的测试，没有验证，也没有建立起那种信任，这就会拖慢进度。而这些事情会产生大得多的影响。

<details><summary>Original English</summary>
Yeah, the lack of trust is what slows things down. And this could be rightfully so. Maybe the agent the the AI agent was badly designed and shouldn't be trusted. But it also flip and inverse. What if hypothetically the that agent was doing everything perfectly? But people weren't trusting it because it didn't have the test in place, it didn't have the validation, and it didn't build that trust. That slows things down. And these things make and these things have a much bigger impact.
</details>

所以，再次强调，对于这把锤子如何被使用要非常警惕，因为你需要相应地做出调整。

<details><summary>Original English</summary>
So, once again, be very wary about how the hammer is being used because you need to make your adjustments accordingly.
</details>

### Token 消耗不等于完成的工作

所以，这就回到了我们所说的，token 并不等于完成的工作。我要强调的一个主要例子是——这种情况发生的频率比我想看到的要高——有时滥发更多 agent 和消耗更多 token 意味着你把同一个任务重复做了好几次。因此，我们开始看到的其中一个反模式是：虽然整个工程组织通过更快地解决更多 issue、自动化清理 issue 来提高生产力，例如，像 QA 团队报告一个 issue，agent 在甚至没有工程师介入的情况下自动修复它，这些都很棒。

<details><summary>Original English</summary>
So, and this goes back into saying like tokens are not work done. You have uh um um and one major example that I will highlight, right, is is this happens more often than than I would like, is that sometimes spamming more agents and more tokens sometimes means you get the same task done multiple times. So, one of the anti-patterns that we started seeing, right, uh we are well in overall the engineering organization improve productivity by clearing more issues quickly, automating clearing of issues, for example, like when someone like when a QA and and things like QA teams reporting an issue and the agent automatically fixing it without even an engineer, those are great.
</details>

但我们开始面临的常见问题之一是，人们很快就变得野心勃勃。他们不再做微小的改动，而是开始进行巨大的改动，比如修改一半的代码库或四分之一的代码库。有时，如果这是在适当测试的规划下进行的，那很好。但很多时候，改动发生的规模如此之大，以至于瓶颈变成了合并代码的审查者。

<details><summary>Original English</summary>
But one of the one of the common issues that we start facing is that people get ambitious really fast. And they instead of doing small changes, they start doing huge changes like changing like half the code bases or one quarter of the code bases. Sometimes when this is planned with proper testing, it's great. But a lot of times, right, the change is happening at such a large scale, right, the bottleneck becomes the on the reviewer to merge the code.
</details>

因为一切都是在如此巨大的规模下完成的，以至于人类无法处理，我们开始看到的常见反模式之一就是：好吧，有人已经实现了，有 issue 被解决了。而由于生成的代码太多，没有生成代码的 issue 就得不到审查，也不会被审查者关注。

<details><summary>Original English</summary>
And because because everything is done on such a large scale where a human cannot process it, one of the common anti-patterns that we start seeing is that okay, someone has implemented the the there's issues being done. And because there's so much code being generated, issues that do not have code generated do not get reviewed and do not get picked up by the reviewer.
</details>

于是，有人需要用 agent 来生成代码。然后，当 agent 生成那大堆代码时——如果他们能好好审查 prompt 之类的，代码本应该少得多的——审查者看着它就会想：“呃，这代码太多了。我能不能让我的 agent 标出哪些改动是相关的，然后再重新实现一遍？”最终他们开始用那个 agent 手动重新构建。所以，他们实际上扔掉了第一个 agent 的工作成果。

<details><summary>Original English</summary>
So, someone needs to generate the code using an agent. And then when the agent generate that giant pile of code, which should be a lot less if they were to like properly review prompting and stuff, the reviewer look at it and it's like, "Huh, this is too many code. Can I ask my agent to highlight what changes are relevant and then re-implement it?" And and and in the end they started rebuilding it by hand with the with the agent. So, they literally discard the first agent's job.
</details>

发生这种情况有很多合理的理由。例如，审查者想要保持对主代码库的控制和质量，但这是一个非常常见的瓶颈例子：如果你没有把流程想透彻，你只是往里面扔越来越多的东西。这样一来，速度并没有增加。

<details><summary>Original English</summary>
There's multiple good reasons why this happened. For example, like reviewers want to maintain control and quality of the main code base, but this is a very common example of a bottleneck where you where where if you didn't think the process through, you're just throwing more and more things. And respectively, and the speed is not increasing.
</details>

所以，审视你的流程。解决这个问题的一个好方法自然是贯彻更好的测试实践，这样你就可以将其自动化并筛选出来。此外，也要提醒团队：“嘿，拆分你的合并请求，或者让它更模块化，以便让审查流程更轻松。”诸如此类。这些都是人的流程。这与 AI 无关。是的，我们有时往往对 AI 过于兴奋了。

<details><summary>Original English</summary>
So, review your processes. A good way around this is naturally to to to instill better testing practices and so that you can automate that and filter out. Also, reminding teams to like, "Hey, split up your your your merge or or make it more modular to make it easier for the review process." Like things like that. These are human processes. It has nothing to do with the AI. And yeah, we tend to get too excited about AI sometimes.
</details>

所以，这不仅仅是代码的问题。我们开始看到，因为 AI agent 正被用来制作幻灯片——这套幻灯片的设计完全是由 AI 生成的。我经历了很多次迭代。这不是一次性生成的（zero-shot）。我每一页至少过了 30 遍来修改文本，但设计是由 agent 完成的。

<details><summary>Original English</summary>
So, this is not just a code problem. Uh we are starting to see like because uh AI agents are being deployed to make decks, this deck was entirely design-wise was generated by AI. I went through multiple iterations. It's not a zero-shot. I I went through every page like at least 30 times to to change the text, but the design was done by agents.
</details>

有时在组织内部，你开始注意到有人直接一次性生成整套幻灯片之类的东西。然后他们开始传阅，开始开会。接着就变成了由其他人来过滤其中的不一致之处，什么是……什么是不对齐的地方？为什么这两个数据点完全不同？这也是另一个例子，就像前面的例子一样，有人生成代码，或者有人生成幻灯片，或者有人生成报告，而核实事情的负担顺延转移到了下游的某个人身上。所以，要对这种组织变化保持高度警惕。

<details><summary>Original English</summary>
And and sometimes within the organization you're starting to notice people that just one shot from the entire slides, things like that. And and they start passing it around. They start doing meetings. And then it's on everyone else to filter what's the inconsistency, what's uh what's the misalignment? Why is this two data points completely different? This is also another example of like same as the previous example, people generating code or people generating slides or people generating report and the burden shifts onto a some human down the road to verify things. So, be very aware about this organization change.
</details>

为什么我仍然是一个乐观主义者，是因为我认为这本身并不一定是坏事，因为问题在于每个人都需要学习。而这正是我们刚开始相应调整流程的地方。

<details><summary>Original English</summary>
Uh why am I still an optimist is that I I don't think this is necessarily a bad thing in itself because the problem is everyone needs to learn. And this is where we just start adapting our processes accordingly.
</details>

另外一个主要的事情是，虽然关于如何使用 AI 有很多常见的例子，但你会更了解自己组织的业务领域。

<details><summary>Original English</summary>
Uh and the other major thing is that well, there are a lot of common examples on how to use AI. You'll know your subject domain for your organization better.
</details>

在某些用例中，可以使用 AI 来实现某个流程的自动化，例如，这可以为你的组织节省数百万美元，或者大幅提升你的生产力，这些只有你自己才会知道，并不是我作为一个 AI 专家跑过来能知道的。

<details><summary>Original English</summary>
And there will be use cases where an AI could be used in place to automate a process, for example, that could save your organization uh millions of dollars or increase your productivity at a grand scale that that only you will know and not me as an AI expert will come in.
</details>

我想拿沃尔玛那个最著名的例子来说——是在沃尔玛吗？我相信是沃尔玛。他们真的开始在每一辆卡车里都放一个凳子，一个脚踏凳。那是极其简单的改变，但却为他们减少了数百万的开销，因为这减少了搬运重物时发生的背部受伤。利用 AI 也会有类似那样具体的事情。而且它甚至不一定非得是最好的 AI 模型，却实际上能产生最大的影响。

<details><summary>Original English</summary>
I like to point to the most uh famous example that Walmart had where was it Walmart? I believe it's Walmart. Where they literally started putting a stool a stepping stool inside every single truck. And that was like the simplest change, but it lowered their bill by the millions because it lowered back injuries across for heavy goods respectively. It it's some something specific like that with the use of AI. And and it may not even necessarily be a the best AI model, but actually can have the biggest impact.
</details>

是的。是的。

<details><summary>Original English</summary>
Yeah. Yeah.
</details>

所以，进一步强调我之前的观点，被创造出的一个正在流行的词叫做“垃圾手榴弹”（slop grenade）。也就是用 AI 生成大量东西，然后留给其他人去处理。不要让垃圾

<details><summary>Original English</summary>
So, uh doubling down on my previous point, uh one of the term that that was coined by uh that that's been trending is called the slot grenade. So, generating lots of things in AI and then leaving it to someone else. Do not let slop
</details>

<!-- chunk 6/7 -->

手榴弹就会发生。

<details><summary>Original English</summary>
grenades happen.
</details>

嗯，这既是一个文化问题，也是一个流程问题。

<details><summary>Original English</summary>
Uh and this is a culture thing and a processing.
</details>

对。

<details><summary>Original English</summary>
Yep.
</details>

所以，我会制定一些指导原则，这更偏主观，大家会有不同意见。

<details><summary>Original English</summary>
So, the some guideline rules that I would set and this is more subjective. People people disagree.
</details>

嗯，为了防止垃圾手榴弹的发生，要强制要求人们对他们交出或生成的内容负责。比如这页幻灯片，我对我生成的每段文字负责。如果出了问题，责任在我。出问题的不是我的 AI 代理。我不能把责任推卸给代理，我必须承担这个责任。对于代码也是一样，对于生成的任何东西都是一样。

<details><summary>Original English</summary>
Um to prevent a slop grenade from happening, enforce that people should own what they hand over or generate. So, for example, this slide, I own every text that is generated. If there's an issue, that's on me. It's not my AI agent who who who has an issue. I do not get to hand it off to an agent. I must own the responsibility. Same thing for code, same thing for anything that is generated.
</details>

而且你还得衡量结果，而不是使用量。嗯，这就变得更复杂了，因为我不想在这上面花太长时间解释，但有这样一个简单的公式，我认为大家会把它当作一个经验法则：Token 乘以价格，除以某人实际使用的产出结果。

<details><summary>Original English</summary>
And you also have to measure outcomes, not usage. Uh And so this gets more complicated because I I don't want to explain too too long to this, but like there there is like this simple formula that's that I think people take as a rule of thumb, tokens times price divided by outcomes someone actually use.
</details>

这有助于引导很多事情：更小、更高效的模型，更快的模型，更大的模型，诸如此类。

<details><summary>Original English</summary>
And and and this help guide a lot of things. Smaller, more efficient models, faster model, bigger model, yada yada.
</details>

但是，关于这个我不喜欢的地方在于，我要用另一个关于 AI 的比喻，那就是把它更多地看作是增强团队的补剂或类固醇。

<details><summary>Original English</summary>
But, what I don't like about this is that another analogy that I'll use about AI is think of it more as like supplements or steroids that enhance the team.
</details>

把它想象成……比如我用建筑工地施工来举例。假设我可以用它来增加工人的肌肉质量。举个例子，虽然这样做在道德上是不对的，我知道并非如此，但我们只是把它作为思路中的一个例子。有些团队使用了它并提高了生产力，有些团队则没有。

<details><summary>Original English</summary>
Think of it as uh like if let's say I use construction work as an example. It let's say I can use it to increase the muscle mass for the workers. For example, not that it's ethically to do so. I know that's not the case, but let's just say as an example in the train of thought. Some teams will have it and they improve productivity, some teams don't.
</details>

但是，即使没有这个，也很明显有些团队比其他团队要优秀得多。因此，这里的 AI 作为一种补充，并不一定能改变一切。所以你需要意识到，各自的结果是很难衡量的，但这是你可以开始衡量并观察的事情，最重要的是回到第一步：衡量。

<details><summary>Original English</summary>
But, even without that, it's quite clear some teams are much better than others. And and so the AI being a supplement here, right, doesn't necessarily change everything. So, you need to be aware that outcomes outcomes are hard to measure respectively, but it's something that you can start measuring and observing most importantly back to the first step. Measure.
</details>

你知道每个部门、每个团队消耗的 Token 数量，你就可以开始看出哪个团队表现更好，开始看出他们消耗了多少 Token，你就可以开始发现什么是有效的。

<details><summary>Original English</summary>
You know the tokens spent per department, per team, and you can start seeing which team is performing better and you start seeing how much tokens they use. You can start seeing what works.
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

是的，正如我所说，这是有缺陷的度量。所以，是的。嗯，这就是高层面的总体概述。

<details><summary>Original English</summary>
Yeah, as I said, this is flawed measurement. So, yeah. Uh that's that's the high-level overview respectively.
</details>

如果你想在你的组织内部启动这个流程，你可以联系我或我的团队，或者你有六个问题可以开始问，比如：哪个团队花了什么，为了使用更便宜的模型你必须测试什么，你的基础负载是多少，每个团队的默认模型是什么，哪些工作负载有人在等待因而你需要更快的模型，对，以及我们生成的产物中有多少是有用的。这些是你可以开始提问以完善你的 Token 经济学的指导性问题。

<details><summary>Original English</summary>
And if if you want to to like kickstart your process internally within your organization, you can you can either talk to me or my team or like you have six questions for you to start asking like who team spent what, what's the what what must you test to use a cheaper model, what's your base load, what's the default model for each team, and which workload has a person waiting that you need something faster, yeah. And how much of what we generate is useful. These are like guideline questions for you to start asking to refine your tokenomics.
</details>

### 问答环节

好。那么，问答环节。

<details><summary>Original English</summary>
Yeah. So, Q&A.
</details>

请说。

<details><summary>Original English</summary>
Yes.
</details>

>> 是的，你提到微调模型时，是指……

<details><summary>Original English</summary>
>> Yeah, so when you mentioned fine-tuning models, is that
</details>

>> 测试，测试。

<details><summary>Original English</summary>
>> Test, test.
</details>

>> 嗯……

<details><summary>Original English</summary>
>> Um
</details>

>> 对，我在试。

<details><summary>Original English</summary>
>> Yeah, I'm trying.
</details>

>> ……是指 SFT 这类的微调，还是说根据具体的用例或现有的数据，会有其他类型的微调方法？

<details><summary>Original English</summary>
>> like SFT sort of fine-tuning or is there like other sort of uh fine-tuning methods that you have depending on what specific use case there is or what data there is?
</details>

>> 嗯，好的，通常来说往往是 SFT，但我不认为……嗯，我们确实提供微调服务，而且往往是 SFT。现在有许多方法正在涌现。我知道 RL 现在非常吸引人，尤其是在编程环境中，因为很容易在闭环中生成数据；但我们意识到，对于很多机构，比如纽约的金融机构这类组织，并不存在真正适用于金融任务的 RL 环境。因此它往往更多基于 SFT。

<details><summary>Original English</summary>
>> Uh okay, so in general, it tends to be SFT, but I don't think um Well, we do provide fine-tuning services and it tends to be SFT. I there is a lot of methods that are happening right now currently. I know RL is very sexy right now, especially in the coding environment, because it's easy to generate the data in the loop, but what we realize for a lot of organizations, especially like in New York, for example, financial institute, things like that, there's not really an RL environment for financial task, for example. And and so it tends to be more SFT base.
</details>

而且还有其他像 adapted adoption AI 这样的机构，他们也开始自动化提炼数据集，供你训练模型，无论是基于 SFT 还是基于机器思考。

<details><summary>Original English</summary>
And and there are also other organizations like adapted adoption AI where where they are starting to also automate the the the refinement of the data sets for you to train the model be SFT base or thinking thinking of machine base.
</details>

把焦点放在这上面可能是问错了问题。对我而言，人们通常应该关注的是各自的评测。这里有一个关于 Jeff 的好例子：当 Jeff 模型推出时，我们做了一个名为 simple Jeff 的开源项目，它为现有的开源模型复刻了 Jeff API。很多人很快发现 Qwen 27B 在这项任务上表现非常好。

<details><summary>Original English</summary>
Focusing on this might be the wrong question. It to me generally what people should focus on is the evals respectively. So here's a good example for Jeff that came when the Jeff model came out and then we did the open source project called simple Jeff which replicates the Jeff API for existing open source model. A lot of people quickly realized that the Quen 27B was really good at this task.
</details>

有多个团队去微调了 Qwen 27B。而在我们这边，因为我们想采取的方法——比如我们公司希望接纳任何模型，然后我们只是在其之上构建 API——我们开始采取这样一种方法，比如：嘿，我们看到了基准测试，看到了现有模型，为什么我们不改为对其进行提示词调优呢？甚至算不上微调。接着两周后，当 Hugging Face 大规模进行所有基准测试时，比如测试了超过 10,000 个问题诸如此类的，不知怎么的，我进行提示词调优后的 Qwen 27B 击败了大多数 27B 微调模型。

<details><summary>Original English</summary>
And and there were multiple teams that went to fine tune the Quen 27B. I on on our side because we are trying to take the approach like our company like we want to accept any model and then we just build the API on top of it. We started taking the approach of like hey we see the benchmark we see the existing model why don't we prompt tune it instead. It's not even fine tune. And then and then two weeks later as hugging face went to do all the benchmarks at scale like over 10,000 questions things like that. Somehow my prompt tuned Quen 27B beat most of the 27B fine tune.
</details>

所以，这并不是在炫耀，因为我很确定现在我的模型已经被 Cloudflare 最近在更规范基础上完成的微调模型击败了，但这更多说明，调优方法可能并不是正确的问题，更重要的问题是你的评测是什么，以及导致该结果的成果是什么。

<details><summary>Original English</summary>
So this this is not a flex because I'm quite sure now my model is beat by the recent Cloudflare fine fine tune model that was done on a more proper basis but it's more of like the tuning method might the tuning method might not be the right question it's more like what's your evals and what's the results that lead to it.
</details>

>> 对此跟进一个问题：如果你在做 SFT 或不管是什么，对于你需要的那组数据，你需要收集黄金轨迹吗？还是说你可以直接……打个比方，针对你之前的任务，前沿模型能达到大约 80% 的准确率，对吧？那么可能 20% 的时间它会犯某种错误。如果你拿那个去微调，微调后的模型难道不会也犯大约 20% 的错误吗？你是应该以某种方式把那些错误过滤掉，只保留黄金轨迹用于训练，还是可以直接把所有轨迹都扔进去训练？

<details><summary>Original English</summary>
>> And follow for that do you need do you need to collect golden traces for the set of data you need if you're doing SFT or whatever it is or can you do it let's just say like your your prior task the frontier models get like 80% accurate right? So maybe 20% of the time it makes some sort of mistake. If you fine-tune on that, won't the fine-tuned model also get like 20% of it wrong? Are you supposed to filter that out somehow and get only the golden traces for training, or can you just throw all the traces in and train?
</details>

>> 所以，这更多是一种个人意见技巧，因为……一般而言，我会尽量拆分数据集，因为人们懒得去过滤。嗯，所以我尽量至少获取一个黄金轨迹数据集。黄金轨迹数据集各自可能要小得多，然后我们再以大得多的权重对其进行微调。

<details><summary>Original English</summary>
>> So, this is more of a personal opinion technique because uh so, the generally, I try to split the data set because people are lazy filter. Um so, I try to at least get a golden trace data set. And the golden trace data set maybe is much smaller uh respectively, and we just and we then we fine-tune that with a much heavier weightage uh as well.
</details>

但是，有多篇论文指出，特别是在涉及思考 Token 的情况下，即使是未……也就是失败的任务，对吧？当你在微调更小的模型时，往往会从训练中受益，因为它改善了思考过程，哪怕它得到了错误的答案。

<details><summary>Original English</summary>
But, there have been multiple papers especially as especially with thinking tokens that even the non- uh the failed task, right? The as much smaller model, when you fine-tune, tends to benefit from the training because it improved the thinking process even if it got the wrong answer.
</details>

嗯，这确实是一个去尝试然后去衡量的绝佳案例，而且 70% 的情况下都有效。有时你只需要提高黄金轨迹的比例，但这只是一个大致的经验法则。

<details><summary>Original English</summary>
Um this is something This is really a good case of like try and then measure, and it works 70% of the time. Sometimes, you just you need to increase the golden trace ratio, but it's a general rule of thumb.
</details>

我认为对很多客户来说，当他们试图通过 SFT 缩小出一个更小的模型时，他们试图保持的大致经验法则是：我能否保持几乎同等水平的性能，也许评测分数下降了 1%，甚至在某些情况下还提高了 10%，因为基座模型原本并未针对这些任务进行专门化。而且更重要的是，这能否让我的账单减少 100 倍？

<details><summary>Original English</summary>
I think for a lot of customers when they're trying to to SFT down a smaller model, the general rule of thumb they're trying to keep is can I keep to the near same level of performance, and maybe the eval is down 1% or even in some cases it improved by 10% because the base model wasn't specialized for these tasks. And more importantly, does it 100x reduce my bill?
</details>

所以，这通常分别是动力所在。

<details><summary>Original English</summary>
So, that's usually the motivation respectively.
</details>

是的，如果你想超越基线，黄金样本至关重要。有时这需要人类真正去审视数据，尽管我非常希望我的客户多审视数据，但人们并不喜欢这么做。

<details><summary>Original English</summary>
Yeah, golden samples are critical if you want to do beyond the baseline. And sometimes that requires humans to actually look at the data, which as much as I love my customers to look at the data more, people don't like to do that.
</details>

>> 你好。嗯，你会如何处理主要来自于 Claude Code 及其所有集成的代码开销？因为那时你的模型就完全被锁死在 Claude 生态系统里了，我推想是这样。对于如何应对这类情况，你有什么建议吗？

<details><summary>Original English</summary>
>> Hi. Um how would you deal with uh code spend that would mostly come from Claude's code and all the integrations there? Cuz then your model is fully locked into the Claude uh ecosystem, I suppose. Do you have any advice on how to deal deal with those type of situations?
</details>

>> 嗯，对，不幸的是，Claude Code 正是完全锁定的典型例子。

<details><summary>Original English</summary>
>> Uh yeah, unfortunately Claude code is the example of fully locked in.
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 所以，嗯，有时候，有时候第一步实际上是让他们能够切换运行架构。嗯，架构现在似乎是一件灵活得多的事情。比如我们见过完全被锁定的组织，像“我只用 Devin”或者“只用 Mboni”。我们也见过更灵活的组织，真的是字面意义上在运行他们自己的……在创建他们自己的代理架构。而我的反应是：“为什么？为什么你们要从头创建自己的代理架构？”嗯，但比如我们看到人们转向的一个常见架构是 Pi。这也部分是因为周围对它有很多兴奋之情。人们已经表明，即使使用相同的模型，它也能获得大得多的……

<details><summary>Original English</summary>
>> So, uh sometimes sometimes the first movement is actually getting um them able to switch the harness. Um harness it seems to be a lot more flexible thing right now. Like we have seen organizations that are like fully locked in. Like I'm only going to use Devin only or Mboni. We have seen organizations that um that are more flexible. Like literally they are running their they are creating their own agent harness. And I'm my response is like, "Why? Why are you creating your own agent harness from scratch?" Uh but like a common one that we see people switching to is for example Pi. And this is also because there's a lot of excitement around it. People have shown that even with the same model, it gets a much
</details>

<!-- chunk 7/7 -->

因为这种简单且高效的方式，每 token 成本更低。嗯，从那之后，我认为 Pi 编程 agent harness 的美妙之处在于它很容易适应，因为它是如此轻……如此轻量。我们看到很多团队直接开始通过提示词让他们的 agent 进行修改。

一旦他们做到了这一点，他们就会开始进入实验和变更的循环。让大家非常有动力去做出改变的一个常见方法，其实就是引入一个足够好而且速度非常快的模型，比如每秒 100 token。然后突然之间，他们就开始尝试这个模型了。有些团队开始转变，或者说第一批转变中的一种情况是：他们仍然使用 Claude Code 作为 planner，然后他们指示 Claude Code：“使用带有该模型的这个 Pi agent 来做具体实现。”因此就有了 planner 与 implementation 的拆分。

更多是这样，是的，转变就是从这里开始发生的。改变大家的 agent 并不容易，但是确实如此。
<details><summary>Original English</summary>
cheaper cost per token because of the way it's simple and efficient. Um and from there on, the I think the beauty for the Pi coding agent harness is that it's easy to adapt because it's so si- so lightweight. We've seen a lot of teams that just start prompting their agents to make modifications. And once once they have that, then then they start getting the cycle of experimenting and changing. Uh a common way to get them to be very incentivized to change is to actually introduce a a a good enough model that is really fast, like 100 tokens per second. And then suddenly they start giving that a try. And some people start or like some of the first shift would be they still use their Claude code as their planner. And then they instruct the Claude code, "Use this Pi agent with this model to do the implementation." Hence the planner implementation split. It's more yeah, and that's where the transition started to happen. It's not easy to change people's agents, but yeah.
</details>

>> 嗯，是的，所以这方面的一个例子可能是在 Claude 内部把这个更小的 agent 暴露为一个 MCP，或者拥有这些可以卸载任务的工具，我想您会认为这是可行的方案吗？
<details><summary>Original English</summary>
>> Um Yeah, so an example of these could be perhaps to expose this this smaller agent as an MCP in inside cloud or having these tools where you can offload I I suppose is that something that you would you you would say could work?
</details>

>> MCP 处理起来更棘手，因为除非处理得当，否则 MCP agent 无法访问你的文件系统。所以通常就是某种简单得多的方式，比如安装了 Pi，然后他们直接运行批处理命令“Pi 这个”。是的，通常是这种情况。
<details><summary>Original English</summary>
>> MCP is more tricky because MCP agents unless done right don't have access to your file system. So typically it's just something way simpler like pies installed and they run the batch command pie this. Yeah, that that's usually the case.
</details>

>> 谢谢。
<details><summary>Original English</summary>
>> Thanks.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Yeah.
</details>

### 缓存策略与自动路由

>> 如果可能的话，您能否分享一些关于缓存解决方案的案例研究——也就是对缓存进行了非常深入的考量，以及为特定客户带来的成效，即便是匿名的也可以？
<details><summary>Original English</summary>
>> Can you share if possible any case studies about caching solutions being very thoughtful about caching and the outcomes that have been generated for specific customers even if it's anonymized?
</details>

>> 你所说的具体挑战是什么？做一种缓存……好的，你的问题是更偏向于希望匿名，还是……等等，是不希望客户的隐私信息保存在缓存中吗？
<details><summary>Original English</summary>
>> What's the specific challenge you're talking about? You do one caching you Okay, is your question more like you want anonymized you do Wait, you do not want customer private information to save in the cache.
</details>

>> 不是，我是指在您合作过的客户中，您是否有任何案例可以分享，说明他们因为对如何缓存以及不同的缓存方法进行了深入考量，从而取得了怎样的成果？
<details><summary>Original English</summary>
>> No, so so like with customers that you've worked with have you got any case studies you can share about the outcomes that they've been able to generate because of being thoughtful about how they cache and different sort of caching methodologies?
</details>

>> 呃，我认为这个问题我们可以在线下交流，不过总体而言，对于我们规模较大的客户，我们为他们部署专用缓存。所以这在很大程度上解决了很多 PII 问题，因为缓存只属于该客户。

嗯是的，显然还有提示词格式化的问题，但我可能需要更具体地探讨一下你在这里究竟想问什么。简短的回答是有，但这有多种解读方式。是的。
<details><summary>Original English</summary>
>> Uh I think this one we can take offline, but in general for our larger scale customers we deploy them with dedicated cache. So it kind of solves a lot of PI issues because it's the the cache is only for that customer. Um yeah, and obviously there's prompt formatting, but I may need to dig in more specifically like what you're trying to ask here. The short answer is yes, but there's a lot of way to interpret this. Yeah.
</details>

>> 太好了。不好意思问得不够清楚。
<details><summary>Original English</summary>
>> Cool. Sorry about that.
</details>

>> 呃，对基于轮次或基于任务的自动路由有什么看法吗？
<details><summary>Original English</summary>
>> Uh thoughts on turn or task-based auto routing?
</details>

>> 噢，嗯，我总体上更倾向于基于任务的方式。

嗯，主要是因为在部门或组织层面更容易控制预期。

所以，这又回到了诸如：一个部门可能有一个标记模型，然后我为他们自动路由该模型。

呃，我知道现在大家对基于轮次的自动路由有很多炒作宣传。基于轮次的自动路由存在的一个问题是，你必须把基于轮次的自动路由限制在比方说最多两到三个模型内。

如果不这样，你的缓存利用效率就会极低。所以，嗯，例如，我们见过针对 GRM 5.3 和 GRM 5.3 Flash 的基于轮次的路由。这行得通。但如果你放进去 30 个模型，而且每轮它都在不断切换你的模型，那么较低的缓存命中率就会开始破坏你的优化。
<details><summary>Original English</summary>
>> Oh, um I'm a I'm generally more towards task-based. Um mostly because it's much easier to control expectation at a department organization level. So, this this is back to like, hey, a department may have a label model and I kind of auto router that model for them. Uh I know there's a lot of hype right now for turn-based auto routing. One of the issues with turn-based auto routing is that you need to lock down your your turn-based auto routing to let's say at most two to three models. If not, your cache will be extremely inefficient to be used. So, um so for example, we have seen turn-based for GRM 5.3 and GRM 5.3 flash. Make sense. But if you put in 30 models and it keeps changing your model every turn, your your low cache hit rate will start to wreck your your optimization.
</details>

>> 是的，那正是我之前见过的。我看到过在请求层面上这么做，它根本讲不通，然后……
<details><summary>Original English</summary>
>> Yeah, that's what I've seen before. I saw I saw it like request level and it just didn't make sense and then
</details>

>> 是的。但两个模型通常还可以。呃，任务和组织层面是最合理的。是的。
<details><summary>Original English</summary>
>> Yeah. But two models tends to be okay. Uh task and organization makes the most sense. Yeah.
</details>

>> 是的。是的，我同意。
<details><summary>Original English</summary>
>> Yeah. Yeah, I agree.
</details>

>> 好的。

好的。非常感谢大家，呃如果有人想专门找我问更多问题，欢迎直接到前排来找我提问，或者等下一位演讲嘉宾就位后到旁边找我。是的。非常感谢大家。
<details><summary>Original English</summary>
>> All right. Okay. Thank you very much and uh if anyone wants to find me specifically for more questions, feel free to just come up front and ask me or find me by the side once the next speaker's here. Yeah. Thank you very much.
</details>