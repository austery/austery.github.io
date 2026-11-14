---
author: AI Engineer
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KdG9OSOtJOA
speaker: AI Engineer
tags:
  - tokenomics
  - observability
  - cost-management
  - ai-agent
title: Tokenomics 的多维定义与企业级 AI 成本观测实践
summary: Pratyusha Duvvuri 探讨了企业在 AI Token 成本核算上的分歧，指出 AI 正从盲目消耗转向效率优先与定制化定价。针对工程师、工程经理和财务人员三类核心受众，团队耗时 10 周打造了 Tokenomics 观测平台，用于整合多供应商数据、解决对账与组织架构归属映射难题。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cisco
  - Splunk
  - Galileo
  - OpenAI
  - Anthropic
products_models: []
media_books: []
status: evergreen
---
### 闭眼思考：Tokenomics 对你意味着什么

闭上眼睛 7 秒钟，因为再久一点你们就该睡着了，我想让你们思考一下 Tokenomics（代币/Token经济学）对你们意味着什么。

配合我一下，闭上眼睛想一想。

好，大概 7 秒了。问题就在这里：我敢打赌一百万美元，在座的各位绝没有两个人的答案是一样的。无论是那位朋友还是那边的 Christy，这里没有任何人的答案会完全相同。我能自信地这么说，是因为我们调研了至少 100 家不同的客户/公司。

<details>
<summary>Original English</summary>
[music]

>> For 7 seconds, cuz longer than that you'll sleep, um close your eyes and I want you to think about what tokenomics means to you.

Humor me for a second. Close your eyes and think about that.

Okay, that's about 7 seconds. Now here's the thing. I'm willing to bet a million dollars that no two of you in this room have the same answer. Whether it's hi there or Christy there, like nobody has the same answer here and I can tell you this with confidence because we surveiled at least 100 different customers/companies.
</details>

我们和工程师聊过，和产品经理聊过，和工程总监聊过，也和首席财务官（CFO）聊过，可以说是覆盖了整个群体，对吧？

而我们收到的答案跨度极大：有的人觉得只要有可观测性就行，比如“我的 Token 到底花了多少钱”；有的人则希望详细拆解每个团队在财务层面的投资回报率（ROI）。

这跨度确实非常惊人。

现在可能正好适合告诉大家：关于 Tokenomics 究竟是什么，我也没有标准答案，但我可以诚恳地尝试给出我所理解的版本。

<details>
<summary>Original English</summary>
We talked to engineers, we talked to PMs, we talked to engineering managers, CFOs, like the whole spectrum, right?

And the variety of answers we got from yes, just about observability, right? Like how much what is my token costing to know we want a full financial breakdown of the ROI on every single team.

It was a pretty crazy wide spectrum.

This is probably a good time to tell you that I don't have an answer to what tokenomics really is, but I can humbly try to give you my version of tokenomics.
</details>

### 自我介绍与 AI 领域的三大趋势

现在也正好向大家打个招呼。我是 Pratyusha。我之前在 Galileo 工作，后来公司被 Splunk 收购，而 Splunk 本身又被思科（Cisco）收购了。所以我们这算是一种俄罗斯套娃的情况。

我曾是智能体可观测性（Agent Observability）、分布式追踪的技术负责人，最近则负责这个极具挑战性的话题——Tokenomics。

虽然我很想直接给大家演示产品，但我希望我们所有人能共同经历这段探索之旅。所以，让我们先在 AI 领域的三大趋势上达成共识。如果有任何不同意见，欢迎提出来，我很乐意在会后与大家交流。

<details>
<summary>Original English</summary>
It's probably also a good time to say hi. I'm Pratyusha. Um we well I was at Galileo, which was acquired by Splunk, which itself was acquired by Cisco. So we have a Russian doll situation.

Um and I was a tech lead for agent observability, distributed tracing, most recently this crazy topic, tokenomics.

And while I'd love to just jump in and show you a product, I want all of us to sort of sail together on this crazy journey. So let's come to the same page on three trends in AI. And if you dispute me, like please do. Like I'd love to hear from you after the session.
</details>

**第一点**是，我们都知道，狂刷 Token（Token Maxing）曾经绝对算是一种身份象征，对吧？或者说是炫耀的资本。

我这么说的意思是，我们的朋友黄仁勋（Jensen）就曾实实在在地讲过——如果我没记错的话是在五月份：如果一名年薪 50 万美元的员工在 Token 上的花销没有超过或至少达到 25 万美元左右，他会感到非常害怕。

然而现在，就在昨天，或者说今天早上我醒来看社交平台 X（Twitter）时，看到 Ramp 的联合创始人之一兼 CEO Eric 发了个帖子，他说：我们的 CFO 不想让我公开讨论这个，但我还是要发出来——我们在单周内花掉了 150 万美元，CFO 彻底抓狂了。

因此，现在的趋势转向了讨论**效率**，对吧？

<details>
<summary>Original English</summary>
The first one is we all know tokenomics was definitely like a status symbol of some sort, right? Or token maxing, sorry.

Um and what I mean by that is our friend here Jensen literally said, this was in May if I remember correctly, if a 500k employee is not spending more than or at least around 250k in tokens or token spend, I am terrified.

Now though, like just yesterday or well I woke up this morning and saw Twitter, there was a post from Eric, I forgot his last name, the CEO of Ramp, uh one of them, and he said, uh our our CFO doesn't want me to post about this, but I'm going to do it anyway. We spent 1.5 million dollars in one week and he freaked out.

So there there's this trend towards let's talk about efficiency, right?
</details>

这也正好顺畅地引出这里的**第二个趋势**：以前对于任何任务，大家都会说“直接用最顶尖（SOTA）的模型吧”，无所谓是什么任务，我都要上 Astra Opus 5.5；但现在大家更关注的是：好的，我怎样才能从工具调用（Tool Calls）和模型使用中挤出最高的效率？

这里有一个细微差别，我希望大家都能思考一下。

比如在 Galileo（现在的 Cisco），我们内部有一个使用场景，使用的是较便宜的模型，比如 Luna 模型，其评测（Evals）得分为 96%。这是个公司内部的使用场景，对吧？

出于好奇，我们改用 Astra 模型（比如 GPT-6 Astra）跑了一下评测，评测得分从 96% 跃升到了 99%。

我们把模型换成 Astra 了吗？并没有，因为对于公司内部场景，我不在乎那点差距，我想要省钱。但如果我是做面向外部的业务，如果我是要和客户交互、使用智能体框架为客户提供最佳实用价值，那么为了换取客户满意度的进一步提升，我很乐意承担那 3% 的性能差距所带来的成本。

<details>
<summary>Original English</summary>
And that's also probably a good time to segue into the second point here, which is before let's just use the soda model for whatever task, right? I don't care what, I'm going to use Astra Opus 5.5, but now it's more about okay, how can I get the most efficiency out of my tool calls, out of my model usage? And there's a nuance here that I want all of us to think about.

For example, at Galileo, well now Cisco, um we had this internal use case where we using a cheaper model, like a Luna model, which gave us 96% in Evals. It was an internal use case, right?

Um just for fun, we ran Evals on like Astra instead, like GPT-6 Astra, and our Evals jumped from 96% to 99%.

Did we change the model to Astra? No, because I don't care, I want to save money, right? When I'm inside the company. But if I'm trying to do anything external facing, if I'm trying to talk to my customers, use an agentic like harness to get the best utility for my customers, I'm willing to take that 3% hit for that extra, you know, like boost of customer satisfaction that I will get.
</details>

**第三个趋势**，这可能是大家最不常去考虑、但影响却极为重大的一点：以前不管是 OpenAI、Anthropic、Cursor 还是其他任何模型供应商，他们都会告诉你：“好的，这是我们每个 Credit 的成本，这些是支持的模型，这是我们的授权方案。多谢惠顾，我们不做任何定制化。”

而如今，当我们与电信巨头、金融科技公司等各行各业交流时，发现大家与这些供应商达成的协议全都各不相同。对某些企业而言是每 Credit 4 美分；对某些是每 Credit 3 美分；还有些人拿到的是“30 美元以内不收费，但一旦超出，每 Credit 收 10 美分”。

每家公司都有自己量身定制的 Token 计费方式，而这正是 Tokenomics 开始变得愈发关键的原因所在。

<details>
<summary>Original English</summary>
The third trend here, and this is probably the most that the biggest one that people don't think about, which is that before OpenAI, Anthropic, Cursor, you name it, whatever model provider, they would tell you, okay, here's our cost per credit, here are the models, this is our license plan. Thank you very much. We don't do any customization. Today, as we talk to all of the spectrum of like telcos, fintech companies, I mean, you name it, everybody has a different like agreement with these providers. For some people, it's 4 cents per credit. For some people, it's 3 cents per credit. For some people, it's, oh, up until $30 we won't charge you anything, but the moment you cross that, it's 10 cents per credit. Everyone has their custom way of defining like costs for tokens, which is especially why tokenomics starts to become important.
</details>

### 三类核心受众与业务痛点

在再次深入探讨我对该定义的理解之前，正如我前面提到的，我们调研了 100 家不同的企业以及各企业内的各类客户。我必须坦白，要把所有理想客户画像（ICP）归纳进仅仅三个类别是非常困难的，但我们必须做出尝试。毕竟要构建一款产品，唯一的路径就是必须对核心用户群体有某种维度的划分。

我们最终归纳出的三类受众如下：

- **第一类**，也是在座许多人最能感同身受的——**工程师**。
- **第二类**是**工程总监/技术主管**。
- **第三类**则是大多数技术人员几乎不会去考虑的角色，我得承认这点——**财务人员**。

<details>
<summary>Original English</summary>
Um before I jump into my version of that definition once again, we, as I mentioned before, surveyed a 100 different companies and different customers in each of these different companies, right? And I will tell you, it is extremely hard to bucket all of your ICPs into just three categories, but we had to try. I mean, there's only one way you can build a product, right? You got to have some version of ICPs.

And what we came up with are these three.

Number one, probably the most that some of us could relate to, the engineer, right? Number two, the engineering manager. And then the third one, completely something that most tech folks don't think about, I will admit it, the finance folks.
</details>

**工程师**担心的问题是：“我到底该选哪个模型？我这个月有 1 万美元的预算，我是不是要超支了？我现在的开销处于什么水位？我正在使用哪些 Skills？我是不是该用 Sonnet 替代 Opus？”诸如此类。

**工程总监**的顾虑则要广泛得多。他们会想：“假如我手下有一个可观测性团队和一个产品团队。可观测性团队确实交付了成果，但他们的成本也严重超标了；产品团队的花销虽然比较低，但似乎并没有达成我们此前承诺的关键业绩指标（KPI）。这里面究竟发生了什么？趋势是怎样的？”他们更关注更广泛的使用情况和采纳度。

而完全处于另一个维度的则是**财务人员**。这帮人关心的是预算和预警。他们需要向自己的上司、CEO、董事会或相关利益方交代清楚：这笔支出换来的具体 ROI 到底是多少？

我认为今早在 X 上读到的一篇文章非常有趣，有人打了个比方：使用 Token 就像是坐在一辆开了计价器的出租车上，你完全不知道行程结束时计价器上会显示多少钱。感觉就像车停了，司机说：“我们一共花了 200 万。哎呀。”这和预付费模式完全不同。因此，这三类群体的诉求我们都需要兼顾。

<details>
<summary>Original English</summary>
So the engineer is worried about, okay, well, uh what models should I use? How much should I like I have a $10,000 budget for this month? Am I am I blowing past it? Like where am I on that spectrum? What skills am I using? Should I use like Sonnet instead of Opus? You know, whatever it is. The engineering manager has a lot more concerns.

That person is like, okay, I have let's say an observability team and I have the product team. The observability team is getting me results, but they're also blowing past their costs. The product team doesn't seem like they're getting me, you know, the KPIs that we promised. However, the costs are lower. What exactly is happening? What's the trend? That person is worried about like broader usage and adoption.

Um and then the one I you was completely orthogonal, finance folks. These guys are worried about budgets, about alerting. They need to justify to their bosses or the CEO or the board or whoever is there, what exactly is the ROI on this spend, right? And the problem with tokenomics, I think I read a really interesting article like again this morning um on X. It was uh some guy was saying that token usage is sort of like you're driving a taxi with a meter and you have no clue like what the taxi is going to show you at the end. It's sort of like we landed on 2 million. Oops. Um very different from prepaid prepaid plans, right? So we're worried about all three of these folks.
</details>

### 现有仪表板的局限：分散、对账与组织架构割裂

现在正好可以探讨一个问题：“我明白你的意思，但我们已经有仪表板了啊。我登录进 OpenAI 的后台，就能看到看板，能看到用过的 Skills，能看到花费，甚至能看到预算预测。”

确实如此。但这仅仅是 OpenAI 一家。此外你还有 Anthropic，还有 GitHub Copilot，还有其他三四家供应商，你如何能有一个一站式的地方去统一查看所有这些信息呢？

而且平心而论，在做出我们自己的 Tokenomics 产品之前，我本身就是那些平台仪表板的重度用户。在此之前，我不得不频繁在所有这些后台之间来回切换，而我只是一名工程师，还不是财务人员或工程总监。

所以，即使那些现成产品本身不错，但它们并不能真正服务好所有的目标用户画像。

不仅如此，我稍后几张幻灯片还会提到，存在一个非常棘手的流程叫做**对账（Reconciliation）**。OpenAI 可能会先告诉你“本月我们要向你收取 10 万美元”，但这可能并不是最终真实金额，他们后续可能会回过头来说：“哎呀，其实是 12 万，我们内部的对账流程刚刚才核算出来。”因此，我们需要一种机制来捕捉这一过程，并为你提供一个跨所有供应商呈现真实、准确用量的单一真理源。

还有最后一点：**财务需要将开销精准映射到归属权（Ownership）**。这就截然不同了。在大多数公司里，都有日常的管理汇报体系，比如 Workday 上的架构——从我、我的直属主管、主管的主管一路往上，在我的情况中是直达 Chuck Robbins。

但这并不是财务看待事物的方式。虽然最终面对的是同一位 CEO，但财务部门基于运营支出（OPEX）、主营业务成本（COGS）等维度梳理出的公司财务层级，与管理层级截然不同。他们对所有权的理解，与 Workday 或部门经理眼中的所有权概念存在巨大差异。如果这段话听起来有些绕口，不用担心，我们马上就会回过头来详细说明。

<details>
<summary>Original English</summary>
And now is a good time to talk about okay, well I I hear you but we already have dashboards. Like I log into my OpenAI portal, I can see a dashboard, I can see skills used, I can see my cost, I can see maybe a projection.

Sure. But that's just OpenAI. Then you have Anthropic, then you have GitHub Copilot, then you have like four other providers and then how are you having a one-stop shop to see all of that information?

Plus if you really think about it, I'm a power user of those dashboards, right? Before well my my own token tokenomics product. So um before that I had to a shuffle between all of these and I'm an engineer. I'm not like a finance person or an engineering manager.

So you're not really servicing all your ICPs with those products even though they're good. Plus something I'm going to touch on in like a couple of um a couple of slides is that there's this crazy process called reconciliation where a lot of things that OpenAI might have said oh you know we have 100k uh that we're charging you for this month might actually not be true. They might come back to you and say oops it was 120. It's just our recon process caught it. So we need a way to catch all of that and like give you the one true like honest place for you to see all of your usage across all of your providers.

Um oh also that last bullet point, finance needs spend mapped to ownership. Yeah that's that's a little different. See in in most companies you have your management structure, right? You have the workday structure. So it's me, my boss, that person's boss all the way up to, in my case, Chuck Robbins.

Um, that's not the way finance sees things. Sure, it's the same guy. You have like one CEO, right? But the way they map out the finance hierarchy of a company based on OPEX, COGS, whatever they're thinking about is very different. And their their notion of ownership is very different of like from Workday or my manager, like that notion of ownership. If that was a mouthful, don't worry. We'll come back to that in just a second.
</details>

### 什么是 Tokenomics 与接入准备

好的，现在正好给出我对 Tokenomics 的定义：

**Tokenomics 是对 Token 使用量与成本的可观测性与可解释性。**

我在这里其实避开了更复杂的定义，试图借用这些高大上的词汇来概括。但如果深入思考，什么是可解释性？它是 ROI，是去弄清楚我当前使用的是哪一组模型组合，是根据具体的业务场景去理清合理的使用方式与归类。关键在于，这些词听起来很抽象，但当你真正沉下心去剖析目标用户画像并思考他们的切实诉求时，你才能想明白应当去构建怎样的优秀产品。

因此，在向大家实际演示产品之前，我想先说明我们需要客户提供哪些信息。

假设我明天就要为你上线这套产品并开始使用 Tokenomics：

- 首先，我们需要你们提供 **Workday 组织架构**，或者是 ADP 以及你们用于存储公司团队树状结构的任何工具数据。
- 其次，我们需要你们的 **API 密钥和组织机构 ID（Org IDs）**。无论是 OpenAI、Anthropic 还是其他供应商，我们都需要这些信息。为什么？因为我们每天都要与它们对接以拉取数据，从而以单日新鲜度的更新频率向你们提供最新数据。
- 第三项，也是非常棘手的一项，是**财务层级架构**。每家公司的财务层级都不一样，财务人员处理这些的方式坦白讲非常繁杂。

<details>
<summary>Original English</summary>
Okay. This is a good time to talk about my definition of tokenomics.

Tokenomics is the observability and interpretability of token usage and cost.

I kind of just like shied away from a uh uh more complex definition there and tried to hide behind these crazy words. But if you really think about it, what is interpretability? It's ROI. It's uh trying to figure out like which what is the set of models I'm using. It's trying to figure out the proper usage and categorization depending on your use case. The point is that these words are very like vague, but when you really jump into like your ICPs and think about what they want, that's when you can think of what the best product to build is.

So um before I actually show you the demo itself, I also want to talk to you about what we need from you.

So let's say I'm going to show you my product like you know, you're going to use tokenomics tomorrow. It's going to be great.

Before that, the first thing we're going to tell you is hey, we need a Workday hierarchy from you or ADP or whatever like tool you use to store your like company structure or tree, we need that information.

The second thing we need from you is we need your API keys and org IDs. So for OpenAI, Anthropic, whoever you're using for your provider, we need that information. Why? Cuz we're going to talk to them every single day to get that data and then service you like the latest data on like a cadence of one day freshness.

And the third one, the the really gnarly one is the finance hierarchy which differs from company to company. And it's it's honestly crazy how finance people deal with that.
</details>

### 产品演示：管理者视角与智能预测

好，我们来看产品。

顺便提一个关于员工架构数据的有趣现象：大家对分享的数据非常敏感，这完全合情合理，因为没人会愿意把完整的 Workday 历史记录和盘托出。

因此与客户交流后我们发现，大家通常只想分享姓名、工号 ID 和职务职能，并不想透露工龄、在职时长等其他信息。因此，针对这种实际情况，我们将接入流程简化到极致——直接支持上传 CSV 文件。我们对客户说：朋友，直接发给我们一个包含这六项字段的 CSV 文件就行。如果之后你想提供更多维度，我们可以进行多维细分并展示更丰富的内容；但最低门槛上，我们只需要这六个字段。

回归正题看产品。由于我不想被 Galileo 或思科解雇，且他们没有授权我公开真实数据，所以我不得不对界面上的具体数字做了模糊处理，非常抱歉。但除了具体金额数字之外，产品的其他所有功能都在这里完整展现。

登录进 Tokenomics 仪表板后，大家第一眼看到的是用于筛选的各种时间区间：你可以按月初至今（MTD）筛选，可以按周筛选，财务人员还可以查看专门的财年日历。请注意右上角的“管理者视图（Leader View）”，这个视图虽然财务人员也能访问，但主要是为工程师和工程总监设计的。

<details>
<summary>Original English</summary>
Um, okay, let's jump to the product.

By the way, fun fact about workforce hierarchy, people are very sensitive about what data they share, which makes sense, right? Like they're not going to share their entire like workday history. So what we've noticed when we talk to customers was we just want to share with you like the names, the IDs, the job functions, but I don't want to tell you anything else like tenure, duration, etc. So based on your use case, we have made our workflow so simple that we literally accept a CSV file. We're like, bro, just send us a CSV file with like these six things. If you want to give us more information, we'll slice and dice and show you more stuff. But at the very least, we need these six things from you.

Anyway, back to the product. Oh, I I had to do this thing where I blurred the information because I didn't want like to get fired by Galileo or Cisco and they did not give me permission to show you the actual numbers. So sorry about that. But apart from the actual numbers, you have everything else in terms of the product showcased here.

So as you log on and if I am running out of time, feel free to like pause me for questions towards the end. Um, you log in to the Tokenomics dashboard and the first thing you see here is different ranges to filter, right? Like you can filter month to date, you can filter by like weeks. There's a fiscal calendar for finance folks. Notice that on the top, this is right, yeah, top right, you see the leader view. This is not for finance folks, although they can access this view. This is for the engineers and the engineering managers.
</details>

大家可以看到，这里有**成本看板**和**采纳度看板**。成本看板顾名思义，展示的是资金花销、Token 消耗量等；采纳度看板则完全不同，它展示的是团队是否在积极使用这些 AI 工具、Codex 的使用量是在上升还是在下降。界面上的这些红色数值代表的是趋势，即在所选时间范围内采纳度或成本的升降波动。

接下来这个图表其实是我最喜欢的功能之一。这是我们在与客户深入沟通后加入的，因为很多人反馈，无论是工程总监还是财务人员，最大的痛点就是**预测（Forecasting）**。

大家往往心里没底：预算究竟会在一周还是一个月内见顶？消耗趋势会是什么样？大家所看到的这个半透明幽灵般的图表、这个带有喇叭口扩散形态的图表，正是预测用量。如果你觉得图表中的方差波动很大，我赞同你的看法，但这正是当下 AI 领域的真实写照——新的工具层出不穷，新的模型不断迭代，成本也在时刻变动。

往下看，这大概是整个产品中色彩最丰富的部分，它逐日呈现具体的成本走势。在这里我们可以看到 CEO Chuck Robbins，以及所有向他直属汇报的人员，所有人的用量都会在此层层向上汇总。

我本人是在 Gitu Patel 的团队下。Gitu 是我们的首席产品官（CPO），我的职级通过汇报链间接向他汇报，因此我的用量包含在 Gitu Patel 的总用量之下，而 Gitu Patel 自然是直接向 CEO 汇报的。顺着层级往下展开，可以看到向 Gitu 汇报的下一层成员，层层下钻。基于出色的用户体验，你可以极快地在团队粒度乃至个人层面上查看每个人的使用情况。

<details>
<summary>Original English</summary>
Um, as you see here, there is the cost dashboard and the adoption dashboard. Cost is, well, as the name suggests, how much money am I spending, the tokens, etc. Adoption is very different. It's hey, is is my team adopting these AI tools? Are they is the Codex usage increasing, decreasing? Like you see these like red numbers here, trends. That's the trend over like whatever time range you've chosen for adoption and cost increase and decrease.

And then this one is actually one of my favorites. We got this after talking to customers where a lot of folks mention the biggest stresses for both engineering managers and finance folks is forecasting.

People don't know like are they going to blow through their budget in like a week or a month or like what that looks like? And so this ghost-like graph that you see here, this weird like opening graph um yeah, that's the projected usage. And if you think there's a lot of variance, I agree with you, but that's also because that just is how the AI world is today with like new things coming out, new models coming out and cost.

Um so if we look down here, this is the probably the most colorful part of the product where you actually see the cost trends over each day, right? But then here we have Chuck Robbins and everyone under Chuck Robbins uh as like direct reports, we see all of their usage roll up. So I think I'm under this guy G 2. Let me see if there's a slightly clearer view. Okay. So G 2 is our CPO, Chief Product Officer. I report to him in some way and my usage is under G 2 Patel's usage, right? But and G 2 Patel obviously reports to the CEO, so we have that. And if you like scroll a little past, let me see if I can tease my way here.

Yep, you see that G 2 has people that report to him and and it goes on and on and on and then you can very fast because that's very important for user experience see each person's usage in their team level and also like an individual usage as you keep going down this this path.
</details>

### 职能维度分析与财务层级视图

另一个非常实用的功能是**按职能族（Job Family）查看消耗**。想象一下我主管的主管的主管，他同时管辖着产品团队、销售团队和工程团队。他肯定想知道：“我的销售团队消耗的 Token 是否比工程团队更多？成本是否更高？”这听起来有些不可思议对吧？但有趣的是，这恰恰是我们一个真实客户的案例——他们的销售团队用量居然超过了工程团队，这确实有些令人担忧。但这正是我们这套一站式平台能够为你提供的多维切片分析能力。

其余功能就更加直观了：你可以按模型维度、按推理思考模式（高/中/低）查看成本，也可以按人员、具体岗位职能、总成本等指标进行过滤筛选。

我本来想在这部分多花些时间讲解，但由于时间有限，我们接着看财务视图。对于纯工程背景的人来说，财务这套逻辑起初确实有些难以理解。但一旦你真正弄懂了财务的运作机制，以及基于 COGS 和 OPEX 的报表汇报架构，就会发现其实并没有那么糟，它本质上也是某种树状层级。

我们在财务视图中同样做了层级架构成本映射树，树上有不同的节点，末端连接着各个部门。从基层员工到 CEO Chuck Robbins，每个人都归属于特定的部门，因此每个人的成本都会汇总到这棵财务树的某个节点中。系统中还设有财务主管（Controller）、分析师等角色。

最核心的一点在于严格的**基于角色的访问控制（RBAC）**与数据查看权限。比如我是 A 团队的管理者，除非我是系统管理员，否则我绝不能看到 B 团队的用量。我们在产品中对权限控制做了完善的处理，确保每个人只能看到被授权查看的数据。

至于演示剩余的部分，本来是讲解设置选项，但考虑到大家的兴趣和时间，我们就先跳过。

<details>
<summary>Original English</summary>
Um another really cool thing and this is just me continually going down until I reach me and people who report to me. But what's also cool here is you see the consumption by job family. Think of my manager's manager's manager, right? That guy is responsible for a product team, a sales team, and uh the engineering team. That person wants to know okay, well uh is my sales team using more tokens or have a higher cost than my engineering team? That's crazy, right? Funny enough, that was actually one of our customer stories where like sales was using more than engineering and that was a little little worrisome. Um but that's exactly the kind slicing and dicing that we provide to you, right? With this sort of like one-stop shop.

Um rest of it is more intuitive, I would say. Like yeah, you want to know your costs per model, per thinking pattern, high, low, medium. Uh you want to be able to filter by the person, their job function, their their total costs, etc. I want to I want to spend more time on this, but I know we're running out of time, so I'm going to move towards the finance view, which again, as someone coming from a pure engineering background was a little crazy.

Um but once you really understand how finance works and like the cogs and OPEX reporting structure, it's it's not that bad. It is also a hierarchy of some sort. So we have the same thing here for finance. We have um their finance hierarchy costs map, uh a tree with different nodes. And then all the way at the end, you hit departments. And when you hit departments, all the way from someone like me to Chuck Robbins, the CEO, everybody is part of a department. And so everybody's cost rolls up into some node in this tree. And then you have a financial controller and an analyst, and I can keep going, but that's going to like make you guys get a little lost in my explanation.

But the point is you have strict RBAK. You have strict viewership rules. Like if I'm a manager of team A, I should not be able to see team B's usage unless I'm an admin. We take care of all of that in our product where you only see what you're supposed to see.

Um though what was left in this demo was honestly just me talking through the settings, but for the purposes of interest and time, we will skip that part.
</details>

### 十周冲刺上线与面临的三大挑战

这是一个处于飞速迭代中的产品。大家可能会感到惊讶：从零开始与客户调研访谈，到构建出完整产品并正式推向全面商用（GA），我们**仅仅用了 10 周时间**。那是一段极其疯狂的冲刺，私下里说，我们搭进去了许多个周末。但既已如此，而且我们也拿到了薪水。

随着与客户接触的深入，我们收到了大量的需求反馈：比如刚才提到的**用量预测**，这项功能尚未公开，请大家先不要对外宣扬，它将在未来几周内发布；还有 **ROI 推断**——如何将业务结果（无论是获客数量、完成的系统迁移，还是吸引眼球的新产品）与实际的 Token 消耗关联起来。功能需求层出不穷，但我希望能留出时间谈谈我们遇到的挑战。

我认为可以用一个比喻来形容 Tokenomics：你驾驶或航行在一艘巨大的船上，而你甚至连目的地在哪里都不知道。当面对一个不断演进的领域且连终点都不明确时，要掌舵并构建出具备可扩展性的产品是极其艰难的。

在座的工程师应该能感同身受：想象一下，你面对着 9 万名需要服务的内部人员，你已经建好了数据模型，万事俱备；然而突然来了一个颠覆性的全新需求，不仅要承载访问平台的 1 万名现有用户，还要兼顾新产品的所有新增用户。对于一个初生产品而言，应对这种情况极为艰难，但我们最终成功做到了，我为团队感到由衷自豪。

<details>
<summary>Original English</summary>
Um this is a very very evolving product. I know I spoke through a lot, but you guys will be alarmed if I say we went from zero, like talking to customers, right? That that zero to building a full-fledged product and shipping it to GA in 10 weeks. That was an insane sprint, off the record, a lot of weekends burned. But it is what it is, and we're getting paid, so.

Um I will say that with our customer like outreach, we're getting a a of like requests. As I mentioned, forecasting, that's something that 's not public yet, so please don't go talk about it, but it's going to come out in like the next couple of weeks. Um, we have ROI inference. So what how do you tie business outcomes, whether that's customers landed, migration completed, a new product that's attracting some eyeballs, how do you tie that to token usage?

And I can keep going on like all the feature requests that are coming, but I want to spend at least a little bit of time on the challenges we faced.

So the way I would describe economics, right? At this point, I think you'll understand me when I say this. You're riding or sailing, I don't know what the right word is, a ship where you don't even know the destination, and it's a big ship. So it's very hard to like steer your product that you're building for scale when you don't even know the destination because it's an evolving subject.

And the engineers in the room will be able to empathize with me when I say imagine you have like 90,000 like people that you're servicing, right? You have this like data model built. You you're like so ready. And then you get a crazy new request that completely changes that. And now you have to account for like 10,000 users accessing your platform while also accounting for the new product users. It's just very hard to do that when you are like a nascent product, but we managed to do it. So I'm pretty proud of the team.
</details>

我们面临的**第二个挑战**在于**三种完全不同的目标受众**。刚才谈及工程师、工程总监和财务人员时，我可能讲得比较轻松，但如果深入思考，一款产品在 AI 时代的真正考验绝不仅仅是开发出来并发布上线，而是如何做到极致的简洁易用，让每个人都能各取所需。面对差异极大的目标用户画像，这非常困难。

**第三个核心挑战**就是我前面提到的**对账（Reconciliation）**。底层数据并非固定不变，它会随着时间推移发生变动，现场的财务人员对此一定深有体会。模型供应商所给出的新数据往往与旧数据存在差异，而此前你可能已经向前承诺数据不会再变，但供应商就是如此运作的。

不仅如此，组织内部的人员流动频繁——可能我明天离职，也可能你明天换了新主管，人事关系一直在变。如何在数据可视化的归属关系中妥善将这些动态变化闭环关联起来？这确实是一个极具挑战的难题。

时间差不多到了最后，我想留出 20 秒左右的时间回答大家的提问。在结束之际，我也想请大家继续思考这个关于 Tokenomics 的定义：现在，它对你而言意味着什么？谢谢大家。

<details>
<summary>Original English</summary>
Um, the second challenge I will touch on here is the three different audiences. I know I made it sound hopefully a little easy when I was talking to you about engineers, engineering managers, and the finance folks, but if you really think about it, the true challenge of a product, especially in the age of AI, is not just building something and like shipping it, right? The true challenge is how do you make it so simple and dumb and easy to use that everybody just gets what they want from it. That's very hard to do when you have crazy different ICPs.

And then the third of many challenges is the thing I mentioned before, reconciliation. It's like this data is not constant. It changes over time, especially the finance folks in the room can empathize with me here. And how do you like fetch that data, the new data that was so different from the old data that you promised you would not change, but that is just how providers are. Um, not just that, your people come and go, right? I might quit tomorrow. You might like have a new manager tomorrow. Like, things can change. And how do you find a nice way to loop that in to your visualization of like attribution? It's It's a pretty hard problem.

With that being said, I know we're towards the end, so I want to leave at least, I will, 20 seconds for questions. And I also want to end with please keep thinking about this definition of tokenomics. Like, what does it now mean to you? Thank you.

>> [applause]
</details>