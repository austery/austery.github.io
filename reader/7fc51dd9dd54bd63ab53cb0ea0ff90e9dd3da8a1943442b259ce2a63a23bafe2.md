---
author: Latent Space
date: '2026-06-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=h5dlIPM0X18
speaker: Latent Space
tags:
  - infrastructure-efficiency
  - organizational-culture
  - compute-grid
  - end-of-life-care
  - output-maximization
title: 为什么拥有无限GPU的AI实验室仍然失败——Anjney Midha谈文化、对齐与输出最大化
summary: Anjney Midha深入探讨了AI基础设施中的浪费问题，指出文化而非资金或算力才是决定AI实验室成败的关键。他介绍了Amp Grid作为独立系统运营商的愿景，并分享了自己在斯坦福大学关于临终预测的研究经历，以及如何通过输出最大化和全栈对齐来解决AI领域的系统性挑战。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Amp
  - Anthropic
  - Google
  - DeepMind
  - Matrox
  - Nvidia
  - OpenAI
  - Periodic Labs
  - Stanford
products_models:
  - Claude
  - GPT-4
  - H100
media_books: []
status: evergreen
---
### 文化是瓶颈

**Anjney Midha**: 但更具体地说，如今有很多AI实验室拥有他们需要的所有现金。他们拥有他们需要的所有算力，但他们仍然无法交付任何实质性的产品。然后你开始看到人员流失等等。我的诊断是——这是文化问题。如果你停止采取那些能证明使命一致性的行动，停止向你的团队和世界展示你所重视的东西，那么你的文化就会开始瓦解。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: But more concretely, there are so many AI labs today that have all the cash they need. They have all the compute they need and they're still not able to ship anything soda. And then you start seeing people leave and so on. And my diagnosis it's is it's the culture. If you stop taking the actions that demonstrate the mission alignment to what you've said to your team and to your the world matters to you, then your culture starts to fray.

</details>

**主持人**: 在我们进入今天的节目之前，我想对听众们说几句话。谢谢你们。如果没有你们选择点击并收听我们的内容，我们就无法为你们带来你们如此渴望的AI工程、科学和娱乐内容。几乎每天都有赞助商联系我们，但幸运的是，有足够多的你们订阅了我们，让我们能够在没有广告的情况下维持这一切。我们希望保持这种状态。但我只想请大家帮一个忙。你们能做的最有力、完全免费的事情就是点击那个订阅按钮。这是我唯一会请求你们做的事情，它对我和我辛勤工作的团队来说意味着一切。如果你们订阅了，我保证我们会继续努力，让这个节目变得更好。现在，让我们开始吧。

<details>
<summary>Original English</summary>

**[Host]**: Before we get into today's episode, I just have a small message for listeners. Thank you. We would not be able to bring you the AI engineering, science, and entertainment content that you so clearly want if you didn't choose to also click in and tune into our content. We've been approached by sponsors on an almost daily basis, but fortunately enough of you actually subscribe to us to keep all this sustainable without ads. And we want to keep it that way. But I just have one favor to ask all of you. The single most powerful, completely free thing you can do is to click that subscribe button. It's the only thing I'll ever ask of you and it means absolutely everything to me and my team that works so hard to bring the week. If you do it, I promise you we'll never stop working to make this show even better. Now let's get into it.

</details>

### 算力利用率与对齐问题

**主持人**: 我们在Periodic Labs，和Anjney Midha，Amp的CEO兼创始人在一起。

**Anjney Midha**: 欢迎。

**主持人**: 谢谢邀请我。

**主持人**: 在Google，如果你看利用率，通常有两种利用率指标。一种是节点分配率，另一种是MFU（模型浮点运算利用率）。节点利用率通常是指数据中心中显卡的使用百分比。如果它没有达到95%...

**Anjney Midha**: 那是不可原谅的。

**主持人**: 那是不可原谅的，对吧？我认为在Google，我的联合创始人Seb就是从那里来的，他在Google构建了Borg X和Borg GQM调度器。在那里，我认为95%的利用率被视为一次故障。所以，96%的节点利用率应该是标准。而大多数单租户集群并没有达到这个水平。这是第一点。然后，MFU利用率，我认为目前行业最佳水平在60%到70%之间。我认为这是一个领导力问题，对吧？从根本上说，这是一个对齐问题，即资助集群和部署集群的人是否真正对齐？有时理论上他们是对齐的，但在实践中，从资本到集群管理者再到衡量产出的人，这个供应链中的人数太多了，你知道，相隔的层级太多了。你听过那个弧度隐喻吗？在一个弧线的起点，如果两条线只偏离了几度，那么在规模上，它们就会扩散开来。我认为很多集群实施和基础设施，很多前沿实验室和其他团队，正在发生的情况是，他们启动了一个计划，这个计划有点像没有一个北极星，团队想做得好，但他们被要求以极快的速度扩展，而不是迭代式地扩展，导致浪费在规模上迅速复合。所以，我认为我们知道答案，那就是进行迭代式的启动。如果你和那些在半导体行业或DSA行业待了很久的人交流，这并不新鲜。我认为AI不应该成为借口。当然，有些东西是新的，我们有了很多新能力，但这并不意味着可以抛弃常识。常识应该永远流行。

<details>
<summary>Original English</summary>

**[Host]**: We're in Periodic Labs with Anjney Midha, CEO founder of Amp.

**[Anjney Midha]**: Welcome.

**[Host]**: Thanks for having me.

**[Host]**: At Google, uh if you utilize So, there's two types of utilization usually, right, that you're measuring in these clusters. One is node allocation and the other is MFU. So, node utilization is usually like what percentage of cards in the data center are just like used. And that if it's not at like 95%

**[Anjney Midha]**: There's no excuse.

**[Host]**: There's no excuse, right? Like I think 95% at Google, which is where my co-founder Seb uh came from, uh he built the Borg X Borg GQM scheduler at Google. And there I think 95% is considered an outage. So, 96% node utilization is should be standard. And most single-down clusters are not running at that. So, that's one. And then MFU utilization should be I would say the best in class today somewhere between 60 and 70%. I think it's a leadership question, right? Is is there an And and fundamentally it's an alignment question, which is are the people who are funding the cluster and then deploying the cluster actually aligned? And sometimes theoretically they are, but in practice the number of people in the chain, the supply chain between like the capital and all the way to whoever's managing the cluster and then whoever's measuring what the output is are just so many, you know, degrees of separation away that like the you know, have you ever heard that sort of you know, radian metaphor, which is at the beginning of of of an arc, if you have two arcs that are two lines that are just off by a few degrees, that it spreads out, right? At scale. And I think what's happening is a lot of cluster implementations and infrastructure a lot of frontier labs and other teams, that's what's happening is they're they they initialize the plan, which is kind of like not North Star with a team that wants to do good, but then they're required to scale so fast instead of iteratively that the wastage just compounds really fast at scale. And so, I I think we know the answer, which is just do iterative bring-ups, you know, if you spend time with people who've been in the semiconductor industry or the DSA industry for a long time, this is not new. And I don't think AI should be an excuse. Like sure, something What is new? Okay, we have a lot of new capabilities, but that doesn't mean just abandon common sense. Common sense should always be in fashion.

</details>

**Anjney Midha**: AI扩展并没有改变这一点。事实上，如果说有什么不同的话，AI扩展应该更加重视常识和基础设施的价值，因为现在的误差范围要小得多，浪费的成本要高得多。顺便说一句，浪费的成本不仅仅是经济上的。我显然是一个投资者，我背景是投资者。过去几年，我们运营着一个AI基础设施业务，叫做Amp。我认为在能力方面，说“这次不同了”是可以的。我们确实在获得前所未有的能力。但这并不意味着你可以借口说“这次不同了”适用于所有事情，尤其是基础设施。所以，听着，我喜欢黑客心态和 hustle 心态，这对初创公司来说很棒。但你们还记得扎克伯格从“快速行动，打破常规”转变为“快速行动，稳定基础设施”的那个时刻吗？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: You know, AI scaling doesn't change the In fact, if anything, AI scaling should be putting a premium on the value of common sense and infrastructure because the the margin of error now is so much lower and the cost of wastage are so much higher. And the cost of wastage by the way is not just economic. I'm obviously I'm I'm an investor or I'm an investor by background. Over the last few years now we're running an AI infrastructure business called, you know, Amp and I think that it's okay to say this time is different on the capabilities front. Like we are genuinely getting capabilities at of of the of a kind we haven't had before. That doesn't give you an excuse to say this time is different for everything, especially infrastructure. So, look, I love the hacker mindset and the hustler mindset and that's great for the startup mindset. But you you remember this moment where Zuck went from saying uh move fast, break things to like move

</details>

**主持人**: 快速行动，稳定基础设施。

**Anjney Midha**: 快速行动，稳定基础设施。我认为现在我们需要的是快速行动，但要有负责任的基础设施。

<details>
<summary>Original English</summary>

**[Host]**: faster, stable infrastructure.

**[Anjney Midha]**: Move faster, stable infrastructure. I think now we need to move fast with like responsible infrastructure.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

### 数据中心与社区共赢

**Anjney Midha**: 他们会问，影响在哪里？你知道吗，昨天在我们的课上，Scott Nolan，General Matter的创始人，来到斯坦福谈论能源瓶颈。他有一个绝妙的想法。他说，如果你看看每小时的边际单位算力经济学，假设是每小时4美元。如果你要在新社区建立一个新的数据中心，为什么不直接说我们要收取4.5美元一小时，然后把那额外的边际收入直接作为现金给当地社区？作为那个算力的客户，我可以告诉你，我会喜欢这样。我很乐意每小时多付50美分，在规模上。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: They're going to say like where is the impact, you know, there was a really in in our class yesterday Scott Nolan, who's the founder of General Matter, came by at Stanford to speak about energy bottlenecks. And he had a phenomenal idea. He said, if you look at the marginal unit economics of compute per hour, let's let's call it like $4 an hour. If you're having to bring up a new data center in a new community, why not just say we're going to charge 450 an hour and that marginal impact or that marginal increase, we just literally take that and give it to the local community as cash. I can tell you as a customer of that compute, I would love that. I'd be happy to pay an additional 50 cents per hour. at scale.

</details>

**主持人**: 哇，是的。

<details>
<summary>Original English</summary>

**[Host]**: Wow, yeah.

</details>

**Anjney Midha**: 因为如果这意味着对数据中心所在社区的公共利益如此明确，我会觉得那个算力可靠得多。你知道吗，今年美国有多达20%的数据中心，据我所知，面临风险。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Because if that means the public benefit is so clear to the communities that the data centers are coming up in, I'm going to feel like that compute is much more reliable. You know, up to 20% of all data centers this year in in the US, my understanding is are at risk.

</details>

**主持人**: 社区反弹的风险？

**Anjney Midha**: 是得不到他们需要的社区支持来建立数据中心。

<details>
<summary>Original English</summary>

**[Host]**: Of community backlash?

**[Anjney Midha]**: Of not getting the community support they need to get brought up.

</details>

**主持人**: 哇。这个数字很大。

<details>
<summary>Original English</summary>

**[Host]**: Wow. That's a huge number.

</details>

**Anjney Midha**: 是的。不过，我认为我们应该深入探讨这个数字。我认为它可能有点被夸大了。这些事情可能会被过度报道。但是...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah. Now, we I think we should dig into what that number is. I think it's a little bit of overstated. Um these things can get over reported. But it

</details>

**主持人**: 他们不仅仅关心工作。他们关心周围所有其他的事情，对吧？他们关心电网，他们关心环境。

<details>
<summary>Original English</summary>

**[Host]**: They don't just care about jobs. They care about all the other stuff around it, right? Like they they care about power grid, they care about environment.

</details>

**Anjney Midha**: 许可等等。想象一下，如果你说，有一个新的AI协议：如果我们在你的社区建立数据中心，我们实际上会降低你的电费。好了，现在我们有得谈了。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: permitting and so on. And and imagine I think if you said but there's a new AI deal if we're bringing up a data center in your community, we're actually going to reduce the cost off your electricity bill. Okay, now we're talking.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 对吧？社区会说，“好吧，现在这是一笔交易。我感觉自己是其中的合作伙伴。”

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Right? The The community is going, "Okay, now now this is a deal. I feel like a partner in this."

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 但现在，这种情况并没有发生。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Right now, that's not happening.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**[Host]**: Mhm.

</details>

**Anjney Midha**: 会有审计，会有调查。当监管机构来的时候，我不知道什么时候会来。那些以AI进步为名快速行动、打破常规的人最好做好准备。这当然不是我们采购算力的方式。我们尽可能与有长期记录的合作方合作。顺便说一句，他们中的许多人并不是AI提供商。我认为整个“新云”作为新类别的概念，很大程度上是营销话术。美国有一些非常优秀、可靠、值得信赖的数据中心提供商，他们已经存在了20多年。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: There will be audits. There will be investigations. And when the when the regulators come, I don't know when it's going to be. The folks who are moving fast and breaking things in the name of AI progress better be prepared. That's certainly not how we're procuring compute. Oh, we're trying as much as we can to work with partners who have long-term track records. Many of whom, by the way, are not like AI providers. I think this whole idea of neo clouds being somehow this new category is a lot of marketing speak. There are really good, reliable, trusted data center providers in America who've been around 20-plus years.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 我喜欢这些人。他们知道如何...当然，他们会在NeurIPS赞助欢乐时光吗？不会。他们是根据苦涩教训构建的吗？不是。他们会出现在那些...你知道，情境感知的派对上吗？不会。但他们是成年人。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I love those folks. They know how to Sure, have have they Are they sponsoring happy hours at NeurIPS? No. Are they legibly bitter lesson built? No. Are they hanging out in my you know, in like situationally aware parties? No. But they're adults.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 我信任他们。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I trust them.

</details>

**主持人**: 他们能处理土地，能处理电力。

<details>
<summary>Original English</summary>

**[Host]**: They can run land. They can run power.

</details>

**Anjney Midha**: 他们有信用记录。我们坐下来交谈。他们中的许多人住在硅谷。他们经历过互联网的繁荣和萧条周期。我喜欢这些人，你知道吗？他们是稳定的基础设施合作伙伴和思考者。我认为在算力层有很多短视的想法。这会给我们带来麻烦。这不会是好事。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: power shell. They have credit histories. We sit down, we have conversations. Many of them live in Silicon Valley. They've, you know, they've had to deal with the boom and bust cycles of the internet. And I love those folks, you know? They They are stable infrastructure partners and thinkers. And I think there's a lot of short-term thinking going on in the compute layer. And it's going to catch up to us. It It's not going to be good.

</details>

### Amp Grid：算力的独立系统运营商

**主持人**: 你谈到对齐激励。你知道，我会认为对齐激励意味着在一个公司内拥有全栈，比如xAI和OpenAI，对吧？那么，作为一个独立的基础设施层，你如何比那些拥有整个体系的人更能与你投资的公司对齐呢？

<details>
<summary>Original English</summary>

**[Host]**: You talk about aligning incentives. Um and you know, I would think that aligning incentives means you have the full stack in one company, which is XAI and OpenAI, right? So, you as a standalone infrastructure layer, why are you somehow more aligned to your portfolio companies than people who just own the whole thing?

</details>

**Anjney Midha**: 在系统设计中，有两种架构模式，对吧？一种是集成，另一种是池化和利用。提高利用率的方法通常是：你可以进行系统集成，将许多流程合并到一个节点中；或者你可以从一个节点中抽出一个流程，并在多个不同节点之间共享该资源。因此，我们看到的Amp Grid，就是我们在这里构建的系统，基本上是一个算力网格。我们试图为算力做的事情，就像电网为电力做的事情一样。这是一个跨云的池化和利用层。所以，我们实际上是全栈集成的反面。它更像是一个水平层。它是多云、多芯片的。目标是让兆级浮点运算像兆瓦一样流动。这在今天由于很多原因非常难以实现。比如，到处都有孤立的算力池，而且没有可互换性。所以，目前我们在调度层面做这件事，也经常在经济层面做。但随着我们开始宣布我们的工作，有非常多的人涌现出来说，“嘿，我实际上正在研究一种方法，让算力在栈的这部分和那部分变得可互换。”作为一个网格，我们希望所有这些人都能参与进来。人们经常问我，“Anjney，你是一个新云吗？”我说，“不，实际上，新云是供应商。”有时你会嘲笑我作为一个风险投资家这么说，我说，“不，实际上，他们是需求方，是网格的承购方。”我们把自己看作所谓的独立系统运营商。所以，如果你研究电网的历史，一旦许多工厂和工业参与者意识到，“嘿，原来池化是个好主意。我们应该把我们的发电机连接起来，而不是每个人都在后院运行一个半负荷的发电机。”这时就需要一个独立的实体来协调所有这些方：输电线路、发电设施、输电线路、工厂。这个中立的协调机制非常关键。如果你研究电网的历史，最持久的那些是那些从不拥有自己资产的。它们通常是从拥有长期锚定客户开始的，这些客户是需求不相关的来源，比如某个城镇的钢铁厂或鞋厂，它们不是竞争性的——钢铁厂想在晚上用电高峰，鞋厂想在白天用电高峰。然后你就把它们连接起来共享，对吧？这样每个人都能保证一定的基本负荷，但你可以安排各自的高峰期，以提高整个城镇的峰值利用率。可以说，历史上的黄金标准是像美国东北部的PJM Interconnection这样的公用事业公司，经过很多很多年，它们成为了所谓的ISO，即电网的独立系统运营商。这就是我们看待自己的方式。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: In systems design, right? there's there's two regimes of architecture, right? You have integration and then you have pooling and utilization, right? So, or rather the way to increase utilization often is you can do systems integration where you collapse a lot of process into one node, or you can pull out a process from a node and share that amongst various that resource amongst several different nodes. And so, we see the the Amp Grid, which is the the system we're building here, which is basically a compute grid. You know, we're doing trying trying to do for compute what the electric grid did Yeah, what the power grid did for electricity. This is a pooling and utilization layer across clouds. And so, we're actually the opposite of a full stack integration. It's like a It's much more horizontal. And it's, you know, it's multi-cloud, it's multi-silicon. Um the goal is to try to make mega flops flow like megawatts. And that is very hard to do today for many reasons. Like there's stranded pools of compute all over the place and and there's no fungibility. And so, right now we do it at the level of scheduling, and we often do it at the economic layer. But as we start to announce what we're working on, it's extraordinary like how many folks are coming out of the woodwork saying, "Hey, I'm actually working on a way to make compute fungible at this part of the stack and that part of the stack." And as a grid, we'd like all of these folks to participate on the grid. This you know, people will often ask me, "Andre, you're a neo-cloud?" And I go, "No, actually, neo-clouds are suppliers. Oh, sometimes you laugh at how you venture capitalist from I go, "No, actually, they are they are demand like sort of off-takers of the grid." We see ourselves as what's called an independent system operator. So, if you study the history of the electric grid, once it became legible to a lot of factories and industrial sort of participants that, "Hey, actually turns out pooling is a good idea. We should pull our generators instead of all having a half a generator running at half capacity in our backyard." There was a need for an independent entity who could coordinate all these parties. Transmission line, power generation facilities, transmission lines, factories. And that neutral coordination mechanism is very critical. In order if if you study like the history of grids, the most enduring ones were those that never owned their own assets. They were ones that had or often started with long-term anchors who were uncorrelated sources of demand, a steel factory or shoe mill or whatever in a particular town who weren't competitive where the steel factory wanted to spike up at night, the shoe mill wanted to spike up during the day. So then you pull and you share, right? So each of you is guaranteed some base load, but then you you kind of schedule your spikes to drive a peak utilization across the town. The gold standard, so to speak, historically has been these utility companies like PJM Interconnection in the Northeast of America where they over many, many years became this what's called an ISO, an independent system operator of the grid. So that's how we see ourselves.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 嗯，从经济上讲，这就是我们。从技术角度来看，我们从调度层开始，因为负责工程工作的Sab和Mihai在Google构建了那个调度器。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Um economically, that's what we are. From a technical perspective, we started at the scheduling layer because Sab and Mihai who run engineering here built that scheduling They they did that at Google.

</details>

**主持人**: 你们也有来自Discord的基础设施团队。

<details>
<summary>Original English</summary>

**[Host]**: And you have infra shops from Discord as well.

</details>

**Anjney Midha**: 我不知道Discord是不是主要的身份标识什么的。我只是...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I I I don't know I don't know if Discord is like the primary identity of what whatever. I'm just

</details>

**主持人**: 不，Discord是...

<details>
<summary>Original English</summary>

**[Host]**: No, Discord was

</details>

**Anjney Midha**: 选一个知名的名字。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Choosing a well-known name.

</details>

**主持人**: 嗯，我当时在那里负责开发者平台。内部基础设施不是我的责任。那实际上是一个叫Mark Smith的人负责的，他非常出色。是的，Discord确实是一个反例。我有机会在那里学到了很多关于全栈基础设施的知识。

<details>
<summary>Original English</summary>

**[Host]**: Well, I I I So I was running the developer platform there. The internal infrastructure I was not responsible for. That was actually a guy by the name of Mark Smith who was extraordinary. And yes, Discord did pull So Discord is actually a counter example. I had the chance to learn a lot about fully full stack infra there because

</details>

**Anjney Midha**: 嗯，这是另一种架构，Discord构建了自己的WebRTC，也就是语音和视频基础设施。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Um it's the it's the other architecture which is um Discord built its own WebRTC so voice and video infra.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**[Host]**: Mhm.

</details>

**Anjney Midha**: 所以Discord没有使用第三方基础设施进行通信。一切都是内部构建的。然后，最大化利用率的方法是从全球超过2亿月活跃游戏玩家那里汇集需求，对吧？这就是那些栈的构建方式。你知道，在系统设计中，反复出现的两个概念是抽象和组合。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: So like Discord did not use Yeah, did not for communication Discord did not use third-party infra. It was all built in-house. And then the way you maximize utilization was you pull demand from the world's 200 million plus monthly active gamers, right? And so so that's that's how those stacks were were constructed. You know, again in system design the two concepts that keep coming up over and over again are abstraction and and composition.

</details>

**主持人**: 对吧？捆绑和拆分。

<details>
<summary>Original English</summary>

**[Host]**: Right? And bundling and unbundling

</details>

**Anjney Midha**: 抽象和组合。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: abstraction and composition,

</details>

**主持人**: 比如垂直化和水平化。所以在这个意义上，Amp是电网的独立系统运营商。我们从我们信任的合作伙伴那里汇集供应，规模约为4年内1.3吉瓦。然后我们从一些世界上最好的研究实验室等汇集需求。我们坐在Periodic Labs这里，他们需要非凡的长期需求。这个想法是，他们每个人都能保证在电网上的基本负荷，但他们可以根据需要灵活地上下波动算力需求，时间周期短得多。这大致就是我在A16Z提出的名为Oxygen的项目的设计。这也是Mihai和Seb在Google构建的GQM Borg X Borg GQM实现的设计。那就是：如何让Google内部的团队在内部基础设施上保证其基本工作负载的容量，但当他们需要为研究增加算力时，如何确保有足够的算力可用？当然，大约三四年前在这个基础设施领域实现的一个重大创新（不是发现，而是实施）是可中断需求的概念。对吧？你只需排队一堆任务，通过某种信用系统，可以有一个竞价机制。这基本上是动态优先级排序，任务可以根据其他人的出价被中断，比如有人说，“你知道吗？我有10个代币，10个信用点，我想花在这个任务上。”另一个团队负责人、研究负责人可能认为“Genie 3”只值5个信用点，而“Nano Banana 2”值10个信用点。所以Nano Banana任务获得优先权。这只是一个例子。

<details>
<summary>Original English</summary>

**[Host]**: like verticalization and and horizontalization. So in that sense Amp is an independent system operator of the grid. We pull demand we pull supply from a number of partners we trust at about 1.3 gigawatt scale over 4 years. And then we pull demand from some of the world's best, you know, research labs and so on. We're sitting at one, you know, periodic labs who need extraordinary long-term demand. And the idea is that you know, each of them is guaranteed base load on the grid, but they can spike up and down flexibly on for compute with much shorter timelines as needed. That that was roughly the design of the program I came up with at A16Z called oxygen. The same that was the same design of the the GQM Borg X Borg GQM implementation at Google that Mihai and Sevin built. Which was that how do you allow uh teams inside of Google on the internal infrastructure to be guaranteed capacity uh for their base workloads, but when they need to spike up on research, how could they ensure that that was sufficiently there? And of course the big innovation that was discover not discover but it kind of implemented in the space this infra space maybe 3, 4 years ago at Google was the idea of interruptible demand. Right? Where you just queue up a bunch of jobs and through this like sort of credit system there can be a bidding mechanism. It's it's dynamic prioritization basically and and jobs can get interrupted based on somebody else who's saying, you know what? I have 10 tokens, 10 credits I want to spend on this job. Another like team lead, research lead is like genie 3 or whatever is only worth five, you know, credits and nano banana 2 is worth 10 credits. And so the nano banana job gets priority. I That's a That's that's up example.

</details>

**主持人**: 这是非常真实的。Brain Marketplace是真实存在的。

<details>
<summary>Original English</summary>

**[Host]**: It's very real. Brain Marketplace was real.

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 我们在播客中和大卫讨论过这个。

<details>
<summary>Original English</summary>

**[Host]**: And uh we've we've covered this on the pod with David who was

</details>

**Anjney Midha**: 哦，太好了。好的，太棒了。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Oh great. Okay. Awesome.

</details>

**主持人**: 批评意见是，嗯，实际上有时你需要中央命令来全力以赴做某件事。而且，有时通过信用点进行的资本主义行不通。

<details>
<summary>Original English</summary>

**[Host]**: Uh and the the criticism is that well, actually sometimes you need central commands to go all in on the thing. Uh and actually sometimes capitalism via credits doesn't work.

</details>

**Anjney Midha**: 不，这不是对Amp的批评。我只是说，这是Google内部尝试过的东西，它导致了Google错过了GPT。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Not not it's not a criticism of Amp. I'm just saying like this is a thing that has been tried uh internally within Google and it led to Google missing GPT.

</details>

**主持人**: 我们的结构本质上和Google非常相似。我们被构建为一个控股公司。所以，你知道，Alphabet Holdings就是Alphabet Holdings，然后他们有子公司叫Google和其他赌注等等。我们有Amp Holdings，我们有我们的基础设施业务，然后我们有一个资本业务叫Foundry，它孵化新的前沿AI实验室，并作为风险资本投资它们。比如Periodic，你知道，今年早些时候我们从我们的基金中向Anthropic投入了几亿美元。所以，无论我们在哪里看到团队在取得进展，尤其是在现有实验室（如DeepMind）内部推动前沿的研究人员，我发现，你知道，总有一个时刻，他们会感到与Alphabet Holdings的“独裁”不一致，而有时“独裁”也不再需要他们，他们会说，“谢谢。你在这里完成了你的工作。你帮助我们度过了从零到一的阶段，但出于某种原因，我们将降低你出色的全能模型等的优先级，转而优先考虑编码。”我认为这是一个悲剧，但我理解。你知道，Sergey和Demis在那里经营他们自己的业务，但这并不意味着我们其他人应该坐等这些进步为世界和人类解锁。我的意思是，想想过去10年DeepMind内部产生了多少非凡的研究。我的意思是，Demis和Sergey以及那些家伙做得非常出色，但归根结底，其中很多从未见天日。

<details>
<summary>Original English</summary>

**[Host]**: Like we structured ourselves essentially very similarly to Google. We we are structured as a holdings company. So, you know, Alphabet Holdings is Alphabet Holdings and then they've got these subsidiaries called Google and other bets other bets and so on. We've got um you know, Amp Holdings and we've got our infrastructure business and then we've got a capital business called Foundry that incubates new frontier AI labs and invest in them as venture capital um like periodic, you know, we put a few hundred million dollars into Anthropic from our fund earlier this year. So, wherever we feel like teams are making progress, especially researchers and so on who push the frontier inside of existing labs like DeepMind, I find, you know, there comes a point where they feel misaligned with the dictatorship of Alphabet Holdings and at that point sometimes the dictatorship doesn't want them anymore and they're like, "Thank you. You've done your job here. You've kind of helped us through the zero-to-one phase and for whatever reason we're going to deprioritize your amazing like omnimodel or whatever it is and instead we're going to prioritize coding and uh I think that's a tragedy, but I get it. Like they're, you know, Sergey and Demis are running their own business there, but that doesn't mean we should the rest of us should sit around waiting for that progress to get unlocked for the rest of the world and humanity. I mean, if if you think about how much extraordinary research has happened inside of DeepMind over the last 10 years. I I I mean, Demis and Sergey and those guys did such a great job, but at the end of the day, so much of that has never seen the light of day.

</details>

**主持人**: 或者它们只是论文，但从未真正投入生产。

<details>
<summary>Original English</summary>

**[Host]**: Or they they're like papers only, but they never actually shipped into production or

</details>

**Anjney Midha**: 我的意思是，更糟糕的是，论文甚至不再发表了，因为DeepMind内部有六个月的禁运期，对吧？我们听说过这个，一篇论文出来后，我认为有一个6个月的禁运窗口，如果业务团队中有人说这可能很有趣，它就会被终身禁运。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I mean, what's worse is the paper is actually not even being published anymore cuz there's a six-month embargo inside of DeepMind, right? Like we've heard about this where a paper comes out and then I think he has a 6-month embargo window where if anybody on the business team says this could be interesting, it's embargoed for life.

</details>

**主持人**: 完全正确。

<details>
<summary>Original English</summary>

**[Host]**: Exactly.

</details>

**Anjney Midha**: 所以发表出来的东西是不够好的。所以基本上存在一个逆向选择问题。是的。在这一点上...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: So the stuff that gets published is the stuff that's not good enough. So there's a adverse [laughter] selection problem, basically. Yeah. At this point

</details>

**主持人**: 顺便说一句，这是NeurIPS上常见的抱怨。就像，“嗯，我为什么要看那些GDM的垃圾论文？”

<details>
<summary>Original English</summary>

**[Host]**: It's It's a common complaint at NeurIPS, by the way. Like it's like, "Well, why would I look at the papers that are the trash of GDM?"

</details>

**Anjney Midha**: 再说一次，我认为这是一个悲剧。我的意思是，我理解。他们在经营自己的业务，但在这个领域的其他部分，我认为研究被囤积会产生负外部性。所以这是一个市场失灵。需要有人来解锁这些研究。我们无法独自完成。我们只有1.3吉瓦的算力。这不算什么。这大约是400亿美元的云支出。我们还需要更多。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Again, I think it's a tragedy. I mean, I get it. They're running their business, but the rest of the space I I I think there's negative externalities of uh research being hoarded. And so that's a There's a market failure. And And somebody needs to unlock that research. And uh we can't do it on our own. We only have 1.3 gigawatts of compute. That's nothing. That's about $40 billion of cloud spend. Uh we're going to need a little more.

</details>

**主持人**: 这是一个我还没见过的数字，那个吉瓦数。这太巨大了。

<details>
<summary>Original English</summary>

**[Host]**: said That's a new number I haven't I haven't come across that uh that gigawatt number. That's huge.

</details>

**Anjney Midha**: 是的。需要说明的是，我们还没有全部锁定。这是我们开始锁定的需求量。我认为公开地，我们实际上还没有确认今年我们有多少。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah. And And to be clear, we haven't secured all of it. That's how much demand we have started to secure. I think publicly we haven't actually confirmed how much we have for this year.

</details>

**主持人**: 你想达到什么目标？

<details>
<summary>Original English</summary>

**[Host]**: Where do you want to get to?

</details>

**Anjney Midha**: 我认为稳态是，我们始终拥有一个1.3吉瓦的基本负荷池。对于峰值容量，目前我的估计是，在未来4年内，我们大约需要6吉瓦，才能让我们所有的团队感觉他们能够继续推进他们正在研究的任何前沿领域，无论是这里的超导体发现，还是我们正在研究的一个新投资，即医疗保健领域的临终预测。你能给予人们的东西是不可思议的。你知道吗，这实际上是我研究生时期的工作。我在斯坦福医学院攻读生物信息学研究生。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I think the steady state would be that we have a base load pool of 1.3 gigawatts at all times of base load capacity. For spike capacity, right now my estimate is we need roughly 6 gigawatts over the next 4 years for all our teams to feel like they were able to keep moving the frontier whatever they're working on, whether it's like superconductor discovery over here. There's a new investment we're working on right now, which is in the end-of-life prediction space in in healthcare. It's extraordinary how much you can you can give people You know, this was actually my graduate school work. I went to graduate school for bioinformatics at Stanford Med.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yes.

</details>

**Anjney Midha**: 我知道我们...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: And I know we

</details>

**主持人**: 经济学、数学与计算科学、生物信息学。

<details>
<summary>Original English</summary>

**[Host]**: Econ MCS bio.

</details>

**Anjney Midha**: 嗯，所以我是一个很奇怪的家伙，我从不满足于我的专业选择。所以有一次我是经济学专业，然后是计算机科学专业，然后是一个叫数学与计算科学的专业。他们决定取消那个专业。所以我把所有课程学分都用来申请研究生院，攻读生物信息学的硕士学位。然后我以为我会读博士。我最终没有读。我辍学了，去了Cliner工作，但我很幸运地师从斯坦福医学院的一位教授。他叫Nigam Shah，他当时在研究临终预测。斯坦福是美国少数几个拥有大规模纵向患者数据集的研究机构之一。我认为它至少有1200万患者生命数据。唯一更大的数据集是在VA，美国退伍军人事务部。为了在那个数据集上进行研究，比如做任何深度学习之类的工作，当时它被称为Stride数据集，你必须是斯坦福医学院的附属人员，这就是为什么我去生物信息学系注册的原因。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Uh so my I was this really weird cat where like I was never satisfied with my major options. So at one point I was an econ major, then I was a CS major, then I was a MCS major called mathematical computational science. And they decided they were going to end that major. So I took all that coursework and I applied it to grad school my graduate degree in bioinformatics, uh which was the master's program. And then I thought I was going to do a PhD. I never ended up doing it. I got I I dropped out and went work at Cliner, but I was lucky enough to apprentice with this professor at Stanford Med. His name is Nigam Shah and he was working on end-of-life prediction. Stanford is one of the only research facilities in America that has a longitudinal patient data set that's larger at scale. I think it's at least 12 million patient lives. The only larger data set is at the VA, the Veterans Affairs, you know, of America. And to do research, like do any deep learning and so on on that data set, it was called the stride data set at that time, you had to be a Stanford Med School affiliate, which is why I went and enrolled in the bioinformatics department.

</details>

**主持人**: 哇。

<details>
<summary>Original English</summary>

**[Host]**: Wow.

</details>

**Anjney Midha**: 嗯，你看，深度学习当时还处于早期。Nigam Shah有远见，认为你可以通过临终预测来帮助姑息治疗。你知道吗，在美国，当时超过30%的医疗保险和医疗补助支出都花在了临终关怀上。而且，你知道，我们在亚洲长大，所以我们都有，至少我，我不会代表你，但我对死亡的态度与美国长大的人非常不同。在美国，从精神和文化上讲，尤其是在基督教传统的西方社会，死亡被视为一个终点。嗯，通常有审判日等等。我们看待死亡的方式是终结性的。在印度文化中，在印度教文化中，死亡是...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Um and look, deep learning was early. Nigam Shah had the visibility like the the vision to see that like you could do end-of-life prediction to help palliative care. In you know, in America, the like over 30% of all Medicare Medicaid spend, at least at that time, was spent on end-of-life care. And what's, you know, we we grew up in Asia, so we all, you know, at at least I I I won't speak for you, but I have a very different relationship with death than I find folks who grew up in America do. In America, spiritually and culturally, especially in Western societies where Christianity the Christian tradition sort of frames death as this terminal point. Um there's often a judgment day and so on. The the way we view death is with a finality. In Indian culture, in Hindu culture, you know, death is one

</details>

**主持人**: 佛教也是如此。

<details>
<summary>Original English</summary>

**[Host]**: Buddhist as well.

</details>

**Anjney Midha**: 你是佛教徒，是的。所以它只是多世旅程中的一步，对吧？所以，我在印度南部的金奈市长大，当人们去世时，你会在街上跳舞。你知道，会有一种游行，你的遗体被抬去火化，你的家人会庆祝。有鼓声等等。这说明了什么。这是因为，这个想法是你将会转世。你从这一生的责任中解脱出来，现在你进入下一世。这就像去一所新大学之类的，对吧？所以，当我作为本科生来到这里时，我感到非常陌生，医疗系统的工作方式与那个假设背道而驰，即我们必须将死亡视为终结性的东西，并推迟它、延缓它。这是一件坏事。所以，在当时，美国的临床决策支持是一个非常原始的领域。即使在今天，美国的医生通常会在你被诊断出绝症时告诉你，“我们诊断了你，这很好。我们诊断你的能力是非凡的。你大概还有6个月到6年的寿命。你拿这个信息怎么办？”

<details>
<summary>Original English</summary>

**[Anjney Midha]**: You're a Buddhist, yeah. So it it's one it's one step in a journey of many lives, right? And so, uh I grew up in the city called Chennai in the south of India, and when people die, you dance on the street. You know, there there's like a procession where your your body is carried to to be cremated and your family like like celebrates. And there's drums and so on. It's to say it's thing. And, uh it's because the idea is that you you're going to be reincarnated. You know, you've been liberated from the responsibilities of this life, and now you're on to your next. It's a new It's like going off to a new college or whatever, right? And so, it was so alien to me when I got here as an undergrad that it the medical system works backwards from that assumption that we have to view death as this terminal thing and delay it, postpone it. It's a bad thing. And so, at the time, clinical decision decision support in in the United States was this very primitive field. Even to this day, physicians in the United States often will tell you when you have a terminal disease, this is your we we've diagnosed you, which is great. Our Our ability to diagnose you is extraordinary. You have somewhere between 6 months to 6 years to live. What do you do with that information?

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 误差范围如此之大，以至于在不确定的时候，我们会默认诉诸文化。当文化是“这是一件坏事。我必须延长我的生命”时，你就会开始做各种事情。从系统的角度来看，那里发生的情况是，医生常常觉得他们需要提供非常高的标准，因为临终诊断总是存在一些不确定性。如果你给病人提供了错误的诊断或建议，你可能会因医疗事故被起诉。然后你的执照可能会被吊销。这对你的职业生涯可能是灾难性的。相比之下，在不是这种情况的国家，你经常观察到的是，医生在给出建议时非常明确。他们说，“嘿，这是你的情况。文献表明你可能还剩下这么多时间。我的专家意见是，你是一个例外等等。”他们试图更明确。这赋予了病人力量，对吧？因为这样病人可以说，“我相信我的医生。他们说平均我还有6个月的生命。但如果我做这些事情，由于我的特定体质或遗传史等等，我可能还有机会。”这让你能够以更科学的方式度过余生，而不是依赖宗教、文化、灵性等等。相比之下，在这里，由于医疗事故的阴影笼罩着医生，他们从不给你明确的建议。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: It The error bars are so high that that then you you you when in times of uncertainty, we default to culture. And when the culture is let's This is a bad thing. I've got to prolong my life, then you start doing things like And and and just to to sort of from a systems perspective, what's going on there is physicians often feel like they need to provide such higher bars because there's always some uncertainty in end-of-life diagnosis. And if you provide the wrong diagnosis or recommendation to your patient, you can be sued for medical malpractice. And then your license can be taken away. It can be catastrophic for your career. In contrast, if in countries where that's not the case, what you often observe is that patients like physicians are quite prescriptive with their recommendation. They say, "Hey, this is your condition. The literature says that you probably have this much time on Earth left. My expert opinion is that you are an outlier or whatever." And they try to be more prescriptive. And that empowers a patient. Right? Because then a patient can say, "I trust my doctor. They said on average I have 6 months to live. But if I do these things, I may have a shot because of my particular predispositions or or my genetic history or whatever." And that empowers you to go about your life in a actually more scientific way than leaning on religion, culture, spirituality, and so on. In contrast, here because of that medical malpractice sort of thing looming over your your your head, a physician never gives you a clear recommendation.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**[Host]**: Right.

</details>

**Anjney Midha**: 所以相反，你会说，“好吧，医生。那我们就都试试吧。”然后你开始接受一整套药物和疗法。然后你经常在医院里待上数周。这会降低你的生活质量。当你的生活质量下降时，你不是在最后的日子里和你爱的人做你喜欢的事情，而是在医院的病床上度过。而这最终占了医疗保险和医疗补助支出的30%。所以这对病人更糟。医生感觉很糟糕。美国纳税人支付了巨额资金。这就是为什么斯坦福的教授Nigam Shah说，“老实说，如果...”，我坐下来和他谈。我当时是个年轻人，21岁。我说，“我想解决一个大问题。”他说，“大问题就是临终关怀。”所以我们尝试用深度学习来做这件事。我们开始在这些Stride患者数据集上学习深度学习，目的是：“能否让AI系统做出比人类精确几个数量级的预测，告诉你一旦被诊断出绝症，你还有多少时间？”然后，如果我们可以让精确度足够高，就可以赋予病人力量。事实证明，技术是可行的。一旦你有了数据集，强化学习就行得通。老实说，即使是回归模型也行得通。你不需要搞得太花哨。有一半时间我们只是在运行非常简单的神经网络。今天，我们用强化学习能做的事情是非凡的。但当时和现在的问题仍然是监管问题。因为你实际上不能把错误临床诊断的责任从医生转移到AI系统上。所以当时，10年或12年前，我感到非常失望，因为我觉得我没有资源去影响监管。今天我非常幸运。我处于不同的位置。我年纪大了很多，所以我花了很多时间在我的下一个孵化项目上，那就是如何通过训练AI模型以更高的精度进行临终预测来解锁患者赋权。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: So instead you you say, "Okay, doc. Well, let's try it all." And then you start a whole regime of drugs and therapies. And then you often spend weeks and weeks in the hospital. And that deteriorates your quality of life. And when that deteriorates your quality of life, like you instead instead of spending your last few days doing the things you love with your family, you're spending it on a hospital bed. And that ends up being 30% of Medicare Medicare and Medicaid. So it it's worse for the patients. The doctors feel terrible. The American taxpayers paying a huge amount of money. And so this is why Nigam Shah, who is this professor at Stanford, said, "Honestly, if there's I I kind of sat down with him. I was this young guy, you know, I was 21. And I was like, "I I want to work on a big problem." He's like, "The big problem is end-of-life care." And so we tried to do deep learning to say So we start trying to learn deep learning on these stride patient data sets to say, "Could you have an AI system make a recommendation that is orders of magnitude more precise about how much time you have left once you've been diagnosed with a terminal condition than a human?" And then if we can get that precision to be high enough, then you can empower the patient. And it turns out the tech works. They get Once you get the data set, like RL works. Honestly, even regression models work. You don't need to get that fancy. Half the time we were just running doing like very simple neural nets. Today, I what we can do with RL is extraordinary. The problem remains then and now is regulatory. Because you actually can't shift the burden of the wrong clinical diagnosis from the physician to the AI system. And so at that time I got quite disillusioned 10 years ago. For 12 years ago where cuz I felt I just didn't have the resources to influence regulation. Today I'm very lucky. I'm in a different place. You know, I've I'm a lot older and so I've been spending a lot of time on my next incubation, which is how can we unlock the like patient empowerment by training AI models to do end-of-life prediction much with much more precision.

</details>

**主持人**: 哦，哇。你仍然专注于这个。

<details>
<summary>Original English</summary>

**[Host]**: Oh, wow. And you're you're still focused on this

</details>

**Anjney Midha**: 在过去的14年里，我没有一天能把这个想法从脑海中抹去。这是我想为之奋斗的山丘。不过，我也想说，你知道吗？我其实更希望不要死。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I I haven't been able to get it this out of my mind a single day for the last 14 years. This is the hill I want I would like to die on. This too, I would say. You know what? I actually prefer not to die.

</details>

**主持人**: 是的，没错。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, exactly.

</details>

**Anjney Midha**: 但我认为美国有两个应该两党一致的问题：一是如何赋予病人在生命末期做出正确临床决策的权力，从而通过科学减轻纳税人的负担。这只是好的老科学，AI可以在这方面提供帮助。第二是净正效益的数据中心。因为我认为这是训练足够好的AI模型来帮助人们生命末期的最大关键瓶颈。所以它们基本上是同一个扩展瓶颈曲线的两个方面。我们成立Amp作为一家公益公司。我和我的妻子，你见过她，她的热情是教育。她的家族是教育家和物理学家的世家。所以这门课是我试图不再做家族中的害群之马，成为一名教育者的尝试。但如果我不教书，我会做的事情就是致力于这两个问题，无论是在政治领域，还是作为某个实验室的研究人员。我的希望是，如果有人正在收听这个播客，如果他们对这两个话题中的任何一个充满热情，我很乐意听到他们的消息。我们可以在节目说明中分享联系方式，但我们正在寻找加入这两个使命的人，无论是在政治方面，还是在医学研究方面。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: But [laughter] but I I think two bipartisan issues I think two issues that should be bi- bipartisan in America are how do we empower patients to make the right clinical decisions at the end of their life such that we're reducing the taxpayer burden with science. It's just good old science and AI can help here. And the second is, you know, net positive data centers. Cuz I think that's the biggest critical bottleneck on training and good enough AI models to help people at the end of their life. So So they sort of two sides of the of the same scaling bottleneck curve, but those two we formed Amp as a public benefit corporation. My wife and I, who you've met, you know, you've met with

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 嗯，她的热情是教育。她的家族是教育家和物理学家的世家。所以这门课是我试图不再做家族中的害群之马，成为一名教育者的尝试。但如果我不教书，我会做的事情就是致力于这两个问题，无论是在政治领域，还是作为某个实验室的研究人员。我的希望是，如果有人正在收听这个播客，如果他们对这两个话题中的任何一个充满热情，我很乐意听到他们的消息。我们可以在节目说明中分享联系方式，但我们正在寻找加入这两个使命的人，无论是在政治方面，还是在医学研究方面。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Um her passion is is education. You know, her family is a long line of educators and so on and of physicists. And so this this class is my attempt to stopping the black sheep of the family and be a an educator. But if I'm not educating the thing I would be doing is working, you know, on on these two problems whether on the political spectrum or as a researcher back at at in some lab. Um and my hope is if anyone's listening to this podcast if you know if if they're passionate about either of those two topics, I'd love to hear from them. We we we can share the contact in the show notes, but uh we're looking for people to join both of those missions on the on the political side as well as on the medical side on the research side.

</details>

### 输出最大化与全栈对齐

**主持人**: 你知道，你说这是一门你想要形成的学科。它被不同地称为前沿系统，也被不同地称为单人前沿实验室。这个学科的理想名称或形态是什么？使命是什么？

<details>
<summary>Original English</summary>

**[Host]**: You know, you said uh this is a discipline that you want to form. You call it it's called various variously called frontier system. It's variously called one person frontier lab. Uh what is the ideal name or shape of this? Like the what is the mission?

</details>

**Anjney Midha**: 你是指这门课吗？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Of the class?

</details>

**主持人**: 嗯，是你正在探索的学科。我的意思是，这门课叫前沿系统，但对我来说，也许一个短语是，你只是反浪费，对吧？浪费GPU，浪费人力和医疗保险。但有没有一个更广泛的主题，也许你可以更简洁地概括？

<details>
<summary>Original English</summary>

**[Host]**: Uh of the discipline that you're I guess exploring, right? Like I I the class is called frontier systems, but like for me maybe one phrase is like uh you're just anti-waste, right? Which is wasting wasting GPUs, wasting in human and Medicare. But like is there is there a broader theme that I'm that maybe you can encapsulate more succinctly?

</details>

**Anjney Midha**: 是的，是的。从工程角度来看，它基本上就是输出最大化。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah, yeah. The from an engineering perspective it's basically it's output maxing.

</details>

**主持人**: 输出最大化部门。

<details>
<summary>Original English</summary>

**[Host]**: Department of output maxing.

</details>

**Anjney Midha**: 你知道，就是输出最大化部门。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: You know, it's the it's the it's the department of output maxing.

</details>

**主持人**: 对我们所拥有的东西进行输出最大化。

<details>
<summary>Original English</summary>

**[Host]**: of what we have.

</details>

**Anjney Midha**: 完全正确。我坚信最优结果。我认为在美国和其他国家，我们正在失去对细微差别的欣赏，AI也是如此，对吧？苦涩的教训成立。好吧，行。但这并不意味着你可以把50万块GB300扔到次优的模型扩展上，浪费大量算力。这也不意味着最优化就是有50种不同的架构，而没有足够的标准化。Anthropic之所以有非凡的进展速度，原因之一是他们选择了Transformer架构，并说这很简单，让我们加倍下注，对吧？现在幸运的是，有足够的投资进入这个领域，我们可以负担得起其他架构，但在当时，投资过于分散到其他架构中。所以，这可以说是解锁了扩展。所以，我认为有一种哲学，我们都应该致力于在全球范围内利用AI这一新能力进行输出最大化。如果我要在斯坦福大学创办一个新系，取决于我想让它有多模糊或多技术性，我可能会称之为对齐系。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Exactly. I'm a huge believer in optimal outcomes. You know, I I think both in America and other countries uh we are losing our appreciation for nuance and this is the thing of AI is the same case, right? Oh, the bitter lesson holds. Okay, fine. But that doesn't mean you just like throw 500 GB300 500,000 GB300s at your like you know, sub-optimal model scaling and you waste a bunch of compute. It also doesn't mean that, you know, the most optimal have like 50 different architectures where there isn't enough standardization. Like one of the reasons Anthropic has had extraordinary sort of velocity is cuz they picked the transformer architecture and said this is simple, let's double down on it, right? And now luckily there's enough investment going in the space that we can afford other architectures, but at the time investment was just too fragmented into other architectures. So, that arguably unlocked scaling. So, I think there's a philosophy I think we all owe it to ourselves to do output maxing with a new capability called AI on a global level. I think if I was starting a new department at Stanford, depending on how fuzzy or technical I wanted to be, I'd probably call it the Department of Alignment. Uh

</details>

**主持人**: 这是一个被过度使用的术语。

<details>
<summary>Original English</summary>

**[Host]**: It's an overloaded term.

</details>

**Anjney Midha**: 但确实如此，对齐确实是一个难题。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: But it is but alignment really is a hard problem.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**[Host]**: Mhm.

</details>

**Anjney Midha**: 我认为当你解锁它时，全栈对齐在任何组织和任何系统中都是超级困难的。比如，在一家风险投资公司，如果你能在你的有限合伙人和创造价值的创始人以及最终拥有IPO股票的公众之间实现全栈对齐，那将是一份不断给予的礼物。当你研究这些系统的历史时，它们通常从小规模开始，反馈循环非常紧密，以至于存在对齐。然后你越试图扩展，劳动分工就越多，专业化就越多，每一步你都会添加抽象层。只要有API接口，就会有损失。有通信损失。所以，我认为一件非常酷的事情是，我们能否找到一种方法，让我们鱼与熊掌兼得，作为一门工程学科，有没有一种方法可以在扩展规模和范围的同时，不失去任何对齐，不进行有损传输？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: And I think when you unlock it, full stack alignment is super hard in any organization and in any system. Like in a in a venture capital firm, if you can have full stack alignment between your limited partners and you know, the founders who are creating the value and ultimately the public that owns the IPO stock, that is a gift that keeps giving. And when you study the history of these systems, when they start off, they usually start out small scale where the feedback loop is actually so tight that there's alignment. And then the more you try to scale, the more division of labor happens, more specialization happens, and at each step you add abstractions. And wherever there's an API interface, there's like loss. There's communication loss. And so I think a really cool thing would be for us to figure out is there a way for us to have our cake and eat it, too, as an engineering discipline, is there a way to actually scale up and scale out without losing any alignment, without you know, lossy transmission?

</details>

**主持人**: 我的意思是，标准。

<details>
<summary>Original English</summary>

**[Host]**: I mean, standards.

</details>

**Anjney Midha**: 所以，标准是一种方式。另一种方式是拥有全新的能力。所以，就像我们在这里试图做的是发现新的超导体。室温超导体将是一种无损的能量传输机制。我的意思是，我们将在几年内拥有飞行汽车。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: So, standards is one way. The other way is you just have net new capability. So, like sup you know, what we're trying to do here is discover new superconductors. A room temperature superconductor would be a lossless transmission mechanism for energy. I mean, we would have flying cars.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 是的，在拥有室温超导体后的几年内就能实现。所以，我认为有两种方法。你要么必须标准化协议或API规范，以实现无损通信；要么你可以提出一种全新的能力，解锁如此多的丰裕，以至于标准化不再重要，因为你只是解锁了全新的容量。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah, right within a few years of having a new room temperature superconductor. So, I think those are the two. You either have to standardize on protocols or or API specs that allow lossless communication, or you can come with a whole new capability that unlocks so much abundance that standardization doesn't matter, cuz you just unlock net new capacity.

</details>

**主持人**: 是的。这就是我这些天一直在思考的事情。

<details>
<summary>Original English</summary>

**[Host]**: Yeah. This So, that This is what I spend my days thinking about [laughter] about these days.

</details>

**Anjney Midha**: 我的意思是，不。我认为每个想要扩展和最大化输出的基础设施人员最终都会思考这个问题。我们没有时间深入探讨，但我们和SF Compute做过一期节目，他们正试图标准化算力的期货合约。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I mean, no. I think every infra person at who wants scale and wants to output max does eventually end up thinking about this. Uh we don't have time to go into it, but we have done an episode with SF Compute that is trying to standardize the futures contract for compute.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**[Host]**: Right.

</details>

**Anjney Midha**: 嗯，我不知道进展如何，但总有一天，这将成为...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Uh I don't I don't know how that's going, by the way, but like at some point this this will be part of

</details>

**主持人**: 我认为Evan很棒，SF Compute是我希望我们能加速的那种努力，因为通常这些交易所很难启动。对吧？因为它们通常需要...各方之间存在许多低效率。基础设施中存在信任边界低效率，因为栈的一部分不信任另一部分给予它们可见性。存在资本市场低效率。存在运营效率。所以，如果你能向系统注入一个单一的冲击，比如大量的算力需求或供应，那么你就可以加速这些新的飞轮。所以，我的希望是有一天，或者很快，如果SF Compute需要额外的容量，或者有多余的容量，他们只需将其接入电网，就会被我们的需求淹没。另一方面，如果他们有很多需求但没有供应，他们同样可以接入电网，这是一个双向协议，他们可以接入我们的容量。我认为我们今天离那并不遥远。我们目前的实现主要是通过一组实验室、大学和一些感觉彼此对齐的受信任方，借用这个被过度使用的词。但我们的希望是让它成为一个开放的协议，任何人都可以接入。

<details>
<summary>Original English</summary>

**[Host]**: think Evan is awesome and SF Compute is the kind of effort that I hope we can accelerate because what what often happens is these exchanges are really hard to get uh it's hard to bootstrap them. Right? Because they often require there there's many inefficiencies between parties. There's trust boundary inefficiencies in infrastructure because you don't trust, you know, one part of the stack doesn't trust another part of the stack to give them visibility. There's capital markets inefficiencies. There's operational efficiencies. So, if you can inject like a a single shock to the system of a ton of compute demand or supply, then you can accelerate uh these new flywheels. And so, my hope is one day, you know, or or soon, if if SF Compute needs extra like has excess capacity, they just hook it up to the grid and they get flooded with demand from us. And on the other side if they have a ton of demand, but they don't have supply, they again hook up to the grid and it's a two-way protocol where they can just hook up to our capacity. And I don't think we're too far from that, you know, today. Our working implementation of it is mostly through a group of labs, um universities, and a few like uh sort of trusted parties who are who all feel like they're in alignment to borrow an over sort of used word. Um but our hope is to just have it be an open protocol that anyone can hook up to on

</details>

**Anjney Midha**: 是接入需求还是接入供应？听起来主要是需求。你似乎不想提供需求。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Hook up for demand or hook up for supply? And Primarily demand, it sounds like. Like you wouldn't want to offer demand.

</details>

**主持人**: 两者都有，是的。不幸的是，过去6周发生的情况是，我们原以为到今年年底会有大量过剩容量。现在全没了。

<details>
<summary>Original English</summary>

**[Host]**: Both, yeah. Unfortunately, what's happened the last 6 weeks is, you know, we thought we'd have a bunch of excess capacity by the end of this year. It's all gone.

</details>

**Anjney Midha**: 需求在爆炸。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: It's exploding.

</details>

**主持人**: 是的，全没了。所以，我的短信里全是朋友们的消息，我们认识很多人。这些是在旧金山筹集了数十亿美元的创始人，他们问，“你有没有可能在接下来几周内搞到15个节点？”

<details>
<summary>Original English</summary>

**[Host]**: Yeah, it's all gone. And so, I have my text messages are full of friends, I mean, we know many of these people. These are founders who've raised billions of dollars in San Francisco going on, "Any chance you have like 15 nodes in the next few weeks?"

</details>

### 非英伟达芯片与系统协同设计

**Anjney Midha**: 非英伟达芯片的空间有多大？你有Lisa Su和Reiner Pope。所以，对更高性能、替代架构的需求很大。同时，这损害了你的标准化。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: What is the scope for non-Nvidia, right? The you have Lisa Su coming and Reiner Pope as well. And so, there is a lot of demand for more performance, alternative architectures and all that. At the same time, this hurts your standardization.

</details>

**主持人**: 我不这么认为。实际上，Reiner就是一个很好的例子，对吧？Reiner是Matrox的CEO和创始人。我今天早些时候实际上让他来办公室上了课。他提出了一个我之前没有考虑过的见解，那就是当他们决定为其数据中心选择标准时，他们选择了英伟达的参考架构。所以，Matrox芯片可以直接插入任何有英伟达启动计划的站点。

<details>
<summary>Original English</summary>

**[Host]**: I don't think so. So, actually, Reiner's a great example, right? Reiner's a CEO and founder of Matrox. I actually had him by for office hours in the class earlier today. And there was an insight he brought up that I hadn't considered before, which is when they decided to pick the standard for their data center. They picked the Nvidia reference architecture. So, the Matrox chips just plug in to any site that has an Nvidia bring-up plan.

</details>

**Anjney Midha**: 那只是软件问题，不是硬件问题。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: It's just software then. It's it's not the hardware.

</details>

**主持人**: 嗯，从输入输出IO的角度来看，它的占地面积和英伟达机架是一样的。

<details>
<summary>Original English</summary>

**[Host]**: Well, from an input and output IO perspective, it's the same footprint as an Nvidia rack.

</details>

**Anjney Midha**: 这很有道理。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: That makes sense.

</details>

**主持人**: 据我所知，他们在系统协同设计方面进行了大量创新。这才是收益所在。所以，他选择了...他说，“Anjney，你知道，当你创办一家新的芯片公司时，有太多工作要做。”

<details>
<summary>Original English</summary>

**[Host]**: Where they have done innovated a bunch from what I can tell is on systems co-design. Which is where a lot of the gains are to be had. And so, he, you know, he picked He was like, "Andre, you know, there's just so much work to do when you're building a new chip company."

</details>

**Anjney Midha**: 不能在所有战线上作战。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Can't fight on every

</details>

**主持人**: 就是不能在所有战线上作战。所以，我问他的问题是，“嗯，你在开发这款新芯片。他们的流片是在明年。你打算和谁合作来托管这些芯片？”他说，“谁愿意托管就托管，这不是我的重点。”我说，“但你如何决定...回到之前的系统设计问题，他决定他不想成为一个完全集成的芯片供应商。他们关注的瓶颈是逻辑芯片。他觉得他们可以通过协同设计在那里榨取大量的性能提升。但这意味着你要委托...回到我们之前的问题，他说数据中心提供商是栈的不同部分。所以他依赖于生态系统的那个部分来托管他的芯片，以便将性能提升带给客户。所以现在你有了另一个抽象层。你可能会遇到损失。所以我问他如何防止损失。回到你的观点，他说，“我只是选择了英伟达标准，因为我不想...我想利用现有的协议。英伟达的伟大之处在于其参考架构是已知的。它是开放的。他们已经发布了。所以Jensen实际上让像Reiner这样的人能够创办像Matrox这样的芯片公司。我不认为他们是竞争关系。算力需求如此之高。我认为英伟达无法满足生产需求。所以我们只是需要更多的芯片。我认为Matrox的做法非常聪明，他们说我们不会在数据中心设计上创新，因为实际上谢谢你Jensen，你已经完成了所有艰苦的工作。我们可以在其他地方创新。我认为这非常健康。我认为这就是我们解锁新瓶颈的方式。我的观点是，像Matrox这样意识到协同设计是方法的芯片团队，他们的主要瓶颈是信任边界。要做好协同设计，你需要尽快了解下一代模型，因为流片需要两年时间。所以如果我的芯片上市时你的模型架构已经改变，我就完蛋了。当他在Google内部时，他坐在Gemini团队旁边，或者Palm团队。他的联合创始人是Palm的成员之一，我想。

<details>
<summary>Original English</summary>

**[Host]**: just can't fight on every front. Cuz so, my my question to him was, "Well, you're working on this new chip. Their tape-out is next year. You know, what who are you going to partner with to host the chips?" And he said, "Whoever will host them, that's just not that's not my focus." And I I "But how did you like you decided for you know back to earlier systems design question he he decided that like like he didn't want to be a full fully integrated chip provider. The bottleneck they're focused on is the the logic die. And they he feels they can crank out a ton of performance gains through co-design there. But then that means you delegate you know to our question earlier like it you he's like that the the data center provider is a different part of the stack. And so then he's dependent on that part of the ecosystem to host his chips to get the performance gains to the customer. So now you have another abstraction. And you have you might have loss. So I asked him how how do you prevent loss? And back to your point he said, "I just picked the Nvidia standard cuz I I didn't want to like I I I wanted to piggyback off of an existing protocol. And that what's great about Nvidia is that reference architecture is known. It's open. They've published it. So Jensen's actually enabled someone like Rein Reiner to build a chip company like Matrox. And I don't see them as competitive. The compute demand is so high. Like I don't I think Nvidia's not able to meet the demand of production. So we just need more chips. And I think it's very smart what Matrox has done which is say we're just going to we're not going to innovate on the data center design cuz actually thank you Jensen you've done all the hard work. Where we can innovate is somewhere else. And I I think that's that's very healthy. I think that's how we unlock new bottlenecks. And my view is these you know chip teams like Matrox who have arrived at the insight that co-design is the way the primary bottleneck for them is trust boundary. To do co-design well you need visibility into the next model generation as soon as possible cuz it takes two years to tape out. So if by the time I bring my chip to market your model architecture has changed I'm host. Now when he was inside Google he was sitting next to the Gemini team he He on Palm or whatever.

</details>

**Anjney Midha**: 他的联合创始人是Palm的成员之一，我想。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: His co-founder was the uh was one was one of the Palm guys, I think.

</details>

**主持人**: 是的，完全正确。所以，当你在Google的信任边界内时，你的系统协同设计循环非常紧密。当你作为创始人离开时，你承担的最大风险之一就是你离开了信任边界。所以，我喜欢做的是帮助那些能够帮助我们为独立生态系统解锁更多容量的芯片团队获得信任。因为当我...如果我从一开始就参与一个实验室，我很幸运能与Anthropic合作，然后我是Mistral的董事会成员，并帮助Black Forest Labs起步。我想在这一点上，我参与了六七个不同的团队。

<details>
<summary>Original English</summary>

**[Host]**: Yes. Yes, exactly. So, when you're inside the trust boundary of Google, then your systems co-design loop is super tight. When you leave as a founder, one of the biggest risks you take is now you're outside the trust boundary. And so, what I love doing is helping chip teams who can help us unlock more capacity for the independent ecosystem access to trust. Because when I if if I've been like involved with a lab from day one, and I was lucky enough to work with Anthropic, and then I'm on the board of Mistral, and at Black Forest Labs get started. I think at this point I'm on six or seven different teams.

</details>

**Anjney Midha**: 只有六个？我感觉应该是...我脑子里想的数字是13，但好吧。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Only six? I feel like it would My mental number was going to be 13, but yeah, it's

</details>

**主持人**: 不，我一次只深入参与一个。

<details>
<summary>Original English</summary>

**[Host]**: No, I you know, I go deep with one at a time.

</details>

**Anjney Midha**: 你是Arena的创始CEO？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: You were founding CEO of Arena?

</details>

**主持人**: 不，那不是...那不是...

<details>
<summary>Original English</summary>

**[Host]**: No, that wasn't an That wasn't

</details>

**Anjney Midha**: 行政CEO。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Administrative CEO.

</details>

**主持人**: 那是一个为期5个月的行政工作，当时Waylon和Anastasia正在完成他们的博士学位。他们不需要产品团队。所以，我帮助招聘了工程、产品和设计负责人。但Anastasia一直是那家公司的CEO。我只是扮演了一个替补角色。我是一个实习生。我做了5个月的CEO实习生。

<details>
<summary>Original English</summary>

**[Host]**: It was an administrative 5-month gig where Waylon and Anastasia were graduating from their PhDs. And they didn't need a product team. So, I helped recruit the head of engineering, product, and design. But Anastasia has always been the CEO of that company. I I I played a pinch-hitting job. I'm an intern. I was CEO intern for 5 [laughter] months.

</details>

**Anjney Midha**: 我面试过他。他非常健谈。我的意思是，我认为他以前是辩论冠军，而且非常量化和数学化，这真是个独角兽。你看看他的产出，他是一个输出最大化者。比如，当他去年毕业时，他的论文引用量比年龄是他两倍的人还多。但同时，他已经启动了一个名为LM Arena的项目，作为副项目被数百万人使用。一次又一次，我意识到风险投资家不擅长将人视为动态的个体。他们想把你放进一个盒子里。这就是你的标签。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I I interviewed him. He's like he's very very well-spoken. I mean, I think he's a debate former debate champion, uh but also very quantitative and mathematical, which is such a unicorn. you look at his output, he's an output maxer. Like, by the time he was graduating from his PhD, which he only graduated last year, he had published more work with a citation count than like people twice his age. But at the same time, he'd already started a project called LM Arena that was being used by millions of people as a side project. And time and time again, what I've realized is venture capitalists suck at seeing human beings as like dynamic agents. Where where They want to put you in a box. This is your thing.

</details>

**主持人**: 所以...

<details>
<summary>Original English</summary>

**[Host]**: So

</details>

**Anjney Midha**: 我第一次被介绍给Anastasios时，有人告诉我，“哦，他很棒，但你知道，他是一名研究员。”

<details>
<summary>Original English</summary>

**[Anjney Midha]**: the first time I got introduced to Anastasios, somebody had told me, like, oh, he's amazing, but you know, he's a researcher.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 我说，“你什么意思他是个研究员？他不是CEO，不是创始人。不是CEO，确切地说。”我说，“你疯了吗？你见过Dario吗？Dario是一名科学家。他在4年内从零创建了一家即将成为万亿美元的公司。名义上，做CEO并不那么难。做一个好的CEO很难。做一个伟大的CEO实际上需要那些已经在其领域顶级期刊发表过论文的科学家所达到的那种表现水平。成为一名有竞争力的科学家是超级困难的。在过去的20、30年里，要在学术界发表论文，要在伯克利这样的地方达到你学科的顶峰，你是一名明星运动员。你是思想上的运动员。你在最高水平上表现。要达到那里，无论是Anastasios还是伯克利的Waylon，还是创建了Stable Diffusion的Robin，还是在创立Mistral之前在Meta创建了Llama的Guillaume，你都必须展示出大量的人类领导力才能获得资源、获得组织的信任、发表论文、把它推出来。我的意思是，我会整天资助研究人员，对吧？那些已经为该领域做出贡献的人。如果他们已经有成果了，他们已经是明星运动员了。如果他们还没有成果，听着，他们仍然可以成为好的CEO，但我发现失败模式是他们根本不想成为CEO。他们主要想发表论文。那也没关系。你知道，我们用Ampere Grid做的一件事是，我们将多余的算力捐赠给非营利组织，比如大学实验室。我们留出了几千块H100，但我确实认为大学校园里正在进行非凡的研究。你知道，我的岳父是一名物理学家。他是一名教授。物理学方面有非凡的工作，我们需要这些。但如果你想成为一名CEO，你需要愿意做的事情是在科学之外非常具有对抗性。在科学界内部，一些最好的研究人员对他们的信念非常具有对抗性，对吧？“这个架构是对的。”要成为一名伟大的CEO，你基本上必须愿意在栈的上下都保持对抗性。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I was like, what what what what do you mean he's a researcher? He's not a CEO, not a founder. Not a CEO, exactly. I was like, are you are you crazy? Have you met Dario? Dario is a scientist. He's gone from zero to like what will soon be a trillion-dollar company in 4 years. Being a CEO, nominally speaking, is not that hard. Being a good CEO is hard. Being a great CEO actually requires a level of performance that scientists who have already published at the top of their field have accomplished. It is super hard to be a competitive scientist. To publish in academia over the last 20, 30 years, to make it to the top of your discipline at a place like Berkeley, you were a star athlete. Like you you are an athlete of the mind. And you perform at the highest levels. And to get there, whether you're, you know, Anastasios or Waylon at Berkeley, or you are Robin who with Blackforest and created Stable Diffusion, or if you're like Guillaume at Meta who created Llama before he started Mistral, like the amount of human leadership you have to demonstrate to get the resources, like get the trust of the organization, publish it, put it up I mean, I would just fund researchers all day, right? If who who who have contributed already to the field. If if if they've put Soda out there, they're they're star athletes already. If they haven't done Soda, look, they they can still be good CEOs, but then I find the failure mode is that they just don't want to be CEOs. They primarily want to publish. And that's okay, too. You know, one of the things we do with the Ampere Grid is we donate excess compute we have to nonprofits, like university labs. We carved out like a couple thousand H100s, but I do think there's extraordinary research being done on university campuses. You know, my father-in-law is a physicist. He's a professor. Extraordinary work in physics, and we need that. But if you want to be a CEO, what you need to be willing to do is be super confrontational you know, outside of science. Like within the scientific community, some of the best researchers are very confrontational about their convictions, right? This architecture is right. To be a great CEO, you basically have to be willing to be confrontational up and down the stack.

</details>

**主持人**: 对你的团队。

<details>
<summary>Original English</summary>

**[Host]**: To your own team.

</details>

**Anjney Midha**: 对你的团队，招聘，招募，客户。嗯，我会说，是的，几乎对所有人。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: To your own team, hiring, recruiting, customers. Well, I would say Yeah, pretty much to everyone.

</details>

**主持人**: 是的，是的。我在自己的工作中也感受到了一点，但我无法想象Dario必须承受的压力。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, yeah. I see I I feel a little bit of that in my own work, but like yeah, I can't imagine the stakes that Dario has had to go through. It's

</details>

**Anjney Midha**: 这相当不错。我不认为压力和你感受到的有太大不同，对吧？压力是个人的扩展向量，对吧？那些在你看来如此之低的压力，比如做这个播客，你可以和别人交谈，进行对话。我的意思是，你是一个非凡的沟通者，对吧？在这次谈话中，你已经从我这里挖掘出了比大多数人都多的东西。你知道吗，我在过去两周内参加了12个播客。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: It's pretty good. I I don't think the stakes are that different from how you're feeling it, right? Stakes Stakes are personal scaling vectors, right? Like the stakes that seem so low to you, like having this podcast, where you can talk to somebody and just have a conversation. I mean, you're an extraordinary communicator, right? Like already in this conversation, you've pulled more out of me than most people. [laughter] You know, and I've been on 12 podcasts in the last 2 weeks.

</details>

**主持人**: 我们只是见过彼此足够多次，所以有一些基本的信任。而且我知道你知道我做了功课，我知道信任对你来说很重要。

<details>
<summary>Original English</summary>

**[Host]**: we've just seen each other enough that you There's some base trust. And I think And I know that you you know that I've done my homework, and like I I know that trust is a big deal for you, so

</details>

**Anjney Midha**: 没错。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Right.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yes.

</details>

**Anjney Midha**: 我认为信任关乎一致性，你我在这个社区里已经见过彼此多年了，对吧？我不知道我们第一次见面是在新奥尔良的NeurIPS。我不知道你是否记得。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I I think trust is about consistency, and you and I have seen each other in the community for years, right? Like I don't know the first time we met was at NeurIPS in New Orleans. I don't know if you remember that.

</details>

**主持人**: 我记得。

<details>
<summary>Original English</summary>

**[Host]**: I remember it.

</details>

**Anjney Midha**: 天哪。Raiko安排了这次...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: god. Ra- Raiko had set up this

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**[Host]**: Yeah.

</details>

**Anjney Midha**: 你知道，Raiko很棒，他安排了这次午餐会。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: You know, Raiko's amazing, and he set up this luncheon, and

</details>

**主持人**: 是的，我当时想，“这个Discord的家伙是谁？”我想，“好吧，但是...”

<details>
<summary>Original English</summary>

**[Host]**: Yeah, I was like, who's this Discord guy? I'm like, okay, but

</details>

**Anjney Midha**: 不，你没有那样。不，你做了一些投资。你当时没这么客气。你当时想，“这个VC是谁？”

<details>
<summary>Original English</summary>

**[Anjney Midha]**: No, you weren't like No, you made some investment. You were much less polite. You were like, who's this VC?

</details>

**主持人**: 不，我是...哦，天哪，我很抱歉。我当时不知道你是谁。

<details>
<summary>Original English</summary>

**[Host]**: No, I Was I Oh my god, I'm so sorry. I was I didn't know who you were.

</details>

**Anjney Midha**: 我很抱歉。但你没有...介绍得不好。我当时不知道你是谁。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I'm so sorry. But like you weren't you weren't The introduction was bad. I I was I I didn't know who you were.

</details>

**主持人**: 你看，这就是语境的问题，对吧？但后来我听到了你的口音。是的。我就想，“你是新加坡人吗？”你说，“是的，”我说我在新加坡读过高中JC。然后冰就破了。

<details>
<summary>Original English</summary>

**[Host]**: The See, this is the thing about context, right? Like Um but then I I think I like heard your accent. Yeah. And I was like, are you are you Singaporean? And you're like, yeah, and I said I went to high school JC in Singapore. And then the ice broke.

</details>

**Anjney Midha**: 是的，是的，是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah, yeah, yeah.

</details>

**主持人**: 但你知道，在科学界，有时对于那些没有接受过情感...我们称之为情商...辅导和指导的人来说，压力非常大。要有科学影响力，你通常需要成为一个非凡的情感...一个与你想影响的人情感协调的人。所以，对你来说如此自然的事情，对其他人来说实际上是压力非常大的事情。所以，我不会假设Dario比你更紧张。你会惊讶地发现，有时一些世界级领导者面临的问题对你来说是多么相似和微小。这就是我从这门课中学到的。你知道，客座演讲者是Sam、Satya、Jensen，他们是Coachella。是的，他们是Coachella。所以我们请到了所有头条人物，我很幸运，其中一些人多年来指导过我，或者我和他们做过生意，当你去掉表演性的东西和你可能在媒体或Twitter上对这些人的任何假设时，我们都只是人类。我们都试图相处，这个时刻的特别之处在于，AI正在迫使扩展，苦涩的教训正在迫使很多人修正他们对世界运作方式的假设，回到第一性原理，或者回去自我教育。所以，你知道，我不会说出这个人是谁，但我上周在德克萨斯州的一个活动上，遇到一个人说，“Anjney，你知道，我看到了你的课。你对实时动作预测模型怎么看？”你不知道当我听到他们问我这个问题时我有多高兴。我知道他们做了功课。他们挑战了假设，他们没有问我，“你对世界模型怎么看？”他们问的是“你对实时动作预测模型怎么看？”世界模型，别误会，很酷，但你我都知道，那是一个有时不够精确的抽象层。

<details>
<summary>Original English</summary>

**[Host]**: But this is the you know, there there are some in the scientific community sometimes the stakes are very high for people who haven't had the emotional We know what it's called EQ. coaching and mentorship. Right? Which is like to have scientific impact you often need to be a extraordinary emotional like emotionally in tune person with the folks you're trying to influence. And so what comes so naturally to you is actually a super high stakes thing to other people. And so I wouldn't assume that Dario is more stressed out than you. You know, these these things are like you'll be surprised how similar and small sometimes the problems are to you that some of the world's biggest leaders are facing. And that's what I've learned from this class. You know, the the guest speakers are Sam, Satya, Jensen, they are Coachella. Yeah, they they are Coachella. Right? So we got to get all the headliners and they're I'm very lucky that some of these people have either mentored me over the years or I've done business with them and when you you know, take the performative stuff out and any assumptions you may have about about these people that you read in the press or on Twitter and we're all just humans. We're all trying to get along and what's so special about this moment is AI is forcing like scaling the bitter lesson is forcing a lot of people to revise their assumptions for how the world works and go back to first principles or go back and educate themselves. So the people kind of people you know, I was um I won't name who this person is, but I was at an event last week in Texas and ran to somebody who said, "Aonde you know, I I came across the class. What do you think about real-time action prediction models?" And I was you know, don't know how happy it made me feel when they asked me that question. I know they've done the work. They've challenged the assumption they you know, they didn't ask me, "What do you think of world models? They said what do you think of real-time action prediction models? World models, don't get me wrong, are cool and everything, but you and I both know that that is a layer of abstraction that is sometimes not usefully precise enough.

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 对吧？可以说...

<details>
<summary>Original English</summary>

**[Host]**: Right? Arguably

</details>

**Anjney Midha**: 大概有四种不同的世界模型。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: There's like four different kinds of world models.

</details>

**主持人**: 完全正确。

<details>
<summary>Original English</summary>

**[Host]**: Exactly. [snorts]

</details>

**Anjney Midha**: 顺便说一句，我们和General Intuition做过一期节目，他们非常专注于...

<details>
<summary>Original English</summary>

**[Anjney Midha]**: We've done the part with general intuition, by the way, which is very focused on

</details>

**主持人**: 哦，酷。是的。我喜欢他。他很棒。这就是我喜欢那些做过那种层次工作的人的地方，他们意识到他们不是在和世界上其他人认为他们在竞争的人竞争。

<details>
<summary>Original English</summary>

**[Host]**: Oh, cool. Yes. I love him. He's He's great. And this what I love about people who've done that level of work, they realize they're not in competition with people who the rest of the world thinks they're in competition with.

</details>

**Anjney Midha**: 是的。因为他们不在那个类别里，他们在他们试图做的具体事情里。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah. Because they're not in the category, they're in the specific thing they're trying to do.

</details>

**主持人**: 他们专注于自己的使命，对他们试图解决的瓶颈有系统性的理解。当别人说，“我也在研究实时动作预测模型”时，Pim会说，“哦，我喜欢那个人。我想我可以向他们学习。”但一旦他们说，“哦，那是个世界模型的人。”就会变成，“啊，哪种世界模型的人？”但大多数情况下，他们只是在试图弄清楚自己是否在浪费时间，因为我们没有足够的时间。所以，你知道，Pim非常喜欢我们讨论过的另一家公司，Black Forest Labs，他多次向我提到，他认为Flux正在做的事情非常酷。Andy Blatman来过并上了课。我一次又一次地发现，对于那些做实际工作、能够足够精确地描述前沿研究领域实际情况的人来说，同志情谊仍然是真实存在的。但当你不得不用商业术语抽象技术复杂性时，这种感觉有时会消失，然后VC们会问，“你和那家世界模型公司有什么不同？”我说，“我该从哪里开始解释这些东西？”

<details>
<summary>Original English</summary>

**[Host]**: They're focused on their mission and they have a systems understanding of the bottle they're trying to to like, you know, solve. And when somebody else says, "I'm working on a real-time, you know, action prediction models, too." Pim goes, "Oh, I love that person. I want I can learn from them." But the minute they're like, "Oh, that person's a world model person." It's like, "Ah, like which type of world model person?" But mostly they're just trying to figure out if they're wasting their time cuz we don't have enough time. So, you know, Pim, for example, is super loves this other company I work with we've talked about called Black Forest Labs, you know, and he's mentioned me multiple times that he's so he thinks what Flux is doing is really cool. You know, Andy Blatman came by and spoke in the class. And what I find over and over again is for people who do the work, who can be usefully precise enough about like what is actually going on in the world of frontier research, the sense of camaraderie is still real and alive. But it gets lost sometimes when you have to like abstract the technical complexities in like business terms and then the VCs are like, "How are you different from that world model company?" I say,

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 这种错位...是的，我认为听众能感受到在真实层面运作是什么感觉，就像你自己一样，而不是像记者那样，你必须把每个人归入一个粗略的类别，并创造一个关于竞争、谁今天赢了、谁落后的叙事。

<details>
<summary>Original English</summary>

**[Host]**: The misalignment Yeah, I think like people listening get a sense of like what it is like to operate at a real level like you're like yourself rather than like like the journalist level where you have to sort of put everyone in like a rough category and create a narrative of competition and who's winning today, who's behind.

</details>

**Anjney Midha**: 是的。这种“赢”的概念对我来说很奇怪。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah. This idea of winning is so weird to me.

</details>

**主持人**: 你确实想赢。你想竞争，你想和我们竞争。

<details>
<summary>Original English</summary>

**[Host]**: You do want to win. You want to compete you you want to compete with us.

</details>

**Anjney Midha**: 不，我认为你想领导。是的，所以你想推动前沿。你想推动最先进的技术。你想做一些以前没人做过的事情。你想获取价值。但你不希望获取太多价值，以至于人们认为你偏离了使命，或者没有为世界做最好的事情。你想获取足够的价值，以便能够继续创新，对吧？我认为人们想领导。他们并不真正关心输赢这个概念。你知道，再次，我喜欢Jensen。他是一位领导者。他在Dwarkesh的播客上谈到的心态，对吧？他说，“我醒来时没有失败者的心态。”我认为那太棒了，对吧？因为他是一名工程师。Dwarkesh做了功课。所以至少，尽管对我来说很明显他们在谈论同一件事，但他们只是错过了彼此。就像，基本上Jensen有一个五层蛋糕的抽象，关于行业如何运作。而Dwarkesh，我认为从那个播客来看，他更多是预训练、中训练、后训练的系统循环概念。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: No, I think you want to lead. No, I think you want to lead. Yes, so you want to push the frontier. You want to push the state of the art. You want to do something that hasn't been done before. You want to capture value. But you don't want to capture so much value that like people think you're on a line with your mission or trying to do what's best for the world. You want to capture enough value that you can keep innovating, right? And I think that people want to lead. They don't really this idea of winning and losing like you know, again, I love Jensen. He's a he's a leader. The mindset that he talked about on Dwarkesh's podcast, right? He's like, "I didn't wake up with a loser mindset." [laughter] I think that was awesome, right? Because he's he's an engineer. Dwarkesh has done the work. So there's at least even though that to me it was very obvious they're talking about the same thing. They just passed each other. Like they said to on like, you know, basically Jensen has this like five-layer cake abstraction of how the industry works. And Dwarkesh had I I think from that podcast had more of like a pre-training, mid-training, post-training systems loop concept.

</details>

**主持人**: 这只是一个他交谈对象的问题，对吧？很明显。

<details>
<summary>Original English</summary>

**[Host]**: It's just a factor of who he talks to, right? Like it's pretty clear.

</details>

**Anjney Midha**: 这是抽象、心智模型的问题。世界上很多问题都是通过类比推理，然后加上那些无形中持有的假设。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: It's the abstraction, the mental models, the it's the whole dude, so much of the problem in the world is reasoning by analogy. And then the assumptions that are held invisibly.

</details>

**主持人**: 嗯。

<details>
<summary>Original English</summary>

**[Host]**: Mhm.

</details>

**Anjney Midha**: 是的，我说过，这实际上是人类历史上对第一性原理思考者最好的时代，因为你认为会发生的一切现在都在成真。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah, I I I've said like this is actually the best time in human history for first principle thinkers because everything you think will happen is actually now coming true.

</details>

**主持人**: 正确。风险投资界在这方面臭名昭著，人们在不确定的时候，会紧紧抓住上一个时代被证明是正确的公理。他们自信地宣称它们是真理，但它们不是。区分启发式方法和公理非常重要。

<details>
<summary>Original English</summary>

**[Host]**: Correct. [laughter] And the venture capital community is like notorious for this where people look in times of uncertainty, they like cling to axioms that end up being true from the previous era. And they they kind of like proclaim them with confidence as if they're truths, but they're not. And it's very important to see the distinction between a heuristic and an axiom.

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 公理可以从内部一致性的角度证明。启发式方法是一种捷径。天哪，过去几年我不得不忍受多少人把启发式方法当作公理来评判人，评判哪些公司会成功。我的意思是，有多少人说，“哦，是的，是的，是的，Anthropic，他们现在只是在训练模型。但这家公司...”

<details>
<summary>Original English</summary>

**[Host]**: An axiom can be proven like from internal consistency point of view. A heuristic is a where you kind of a shortcut. And my god, the number of people I have had to put up with over the last few years who proclaim like use heuristics as axioms to judge people to judge which companies are going to succeed or I mean the number of people that are like oh yeah, yeah, yeah, Anthropic, they're just training models right now. But this one continue.

</details>

**Anjney Midha**: 他们会成为B2B SaaS公司。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: They go to be the B SAS.

</details>

**主持人**: 是的，他们就像，随着时间的推移，如果你眯着眼睛看，也许吧，但你到达那里的方式如此重要，以至于你可以直接 dismiss 别人。事实是这样的，对吧？Anthropic基本上在去年10月实现了起飞。那次训练运行...

<details>
<summary>Original English</summary>

**[Host]**: Yeah, they like which which over the fullness of time if you squint at it maybe, but the way you arrive there is so important that you can you just you can dismiss people. Here's what happened, right? What happened is Anthropic basically achieved takeoff in October of last year. That training run

</details>

**Anjney Midha**: 不管F37是什么？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Whatever F37?

</details>

**主持人**: 我现在不记得数字了，但不管那个检查点是什么。

<details>
<summary>Original English</summary>

**[Host]**: I forget the numbers now, but whatever that checkpoint was

</details>

**Anjney Midha**: 我们在Cognition看到了。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: We saw it at Cognition.

</details>

**主持人**: 是的，对吧？你可能...对我们这些社区里的人来说，尤其是当后训练完成并在12月发布时。

<details>
<summary>Original English</summary>

**[Host]**: Yeah, right? You probably the to those of us in the community, especially once post training was done and it was released in December.

</details>

**Anjney Midha**: 是的，我能偷偷问一个问题吗？我不知道你是否有看法，也许你没有。头号问题是Anthropic是如何攻克编码的，对吧？因为Claude 1，Claude 2，好吧，它是其中的一部分，但不是什么大事。主要的假设是，这是一个幸运的骰子，然后被复利了，对吧？就像它只是稍微好一点，然后他们看到了，就说，“好吧，让我们真正投入。”

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah, can I sneak a sneaky question in there? I don't know if you have a perspective, maybe you don't. I just the the number one question is how did Anthropic crack coding, right? Because Claude one, Claude two, okay, like it was part of it, but it wasn't a big deal. And the leading hypothesis, it's a lucky dice roll that was then compounded, right? Like it was like mildly better, but then they saw it and they were like, okay, let's really invest.

</details>

**主持人**: 我有一个非常烦人的老师。

<details>
<summary>Original English</summary>

**[Host]**: I had this very annoying teacher.

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 我去了印度一所叫Rishi Valley的寄宿学校，那是一个鸟类保护区，在印度乡村有350英亩的鸟类保护区。那里7年没有科技。有一位老师，我不会说出名字，但他总是对我说一句话，我每次听到都很讨厌。他说，“运气青睐有准备的头脑。”这是一句常见的谚语，但他表达的方式总是让我恼火，因为他总是试图...我小时候是那种不费很大力气就能取得好成绩的孩子。因为高中和初中并不难，如果你一般能专心听讲的话。有一次，我得了80%的分数，他不断推我，说我之所以没拿到95%以上是因为我不够幸运。我会说，“你什么意思？”因为我认为我应得那个分数，我有时会和他争论。他会说，“你没有准备好的头脑。如果你想再次幸运...”基本上有一次我得了95或96分。然后我觉得自己理所应当。我想，“好吧，我要继续这样做。”但我没有。然后他说，“运气青睐有准备的头脑。你上次幸运了，但你必须保持准备。”我当时不明白他的意思。现在我年纪大了，我想，“好吧，这些成年人确实懂一些东西。”Anthropic是4年来准备最充分的公司。所以当正确的上下文数据进来，正确的开发者开始发送正确的上下文差异时，当然，你可以说他们幸运了，但如果你问我，他们带着偏执准备了整整4年。如果你还记得，他们早期起步非常困难，以至于他们不得不用更少的资源做更多的事情，你必须准备好如此高效。

<details>
<summary>Original English</summary>

**[Host]**: I I went to this boarding school called Rishi Valley in India, which is like this uh bird preserve, like 350 acres of of bird preserve in in rural India. And there was no technology for 7 years. Uh there was this teacher, I won't name them, but they would have this I hated it every time he said this to me. He was like, luck favors the prepared mind. Which is like a common saying, but the way he delivered it like always grated me cuz he's always try Like I was always one of those kids who got like a good grade without trying very hard. Cuz like high school and middle school is not that hard if you if you're generally like paying attention so on. And there was this one time where But but but I I would get an 80% grade, and he would keep pushing me to say like the reason you didn't get the 95 plus percent is because you're not that lucky. And I would say, "What do you mean?" Cuz I I would think that I deserved that grade, and I would sometimes argue with him. And he'd say, "You didn't have a prepared mind. If you want to get lucky again, there was basically one time where I got like 95 or 96 on this on this subject. And I Now that I I felt entitled. I was like, "Okay, I'm going to keep doing this." And I didn't. And then he was like, "Luck favors a prepared mind. You got lucky last time, but you got to stay prepared." And I didn't understand what he meant. Now as I'm older, I'm like, "Okay, these adults actually knew a thing or two." Anthropic has been the most prepared company for 4 years. And so then when the right like context data comes in, the right developers start sending in, you know, the right context diffs, sure, you could say you got lucky, but if you ask me, they're pretty damn prepared with paranoia for like 4 years. And if you remember, it was so hard for them to get going early on that they had to do so much more with so much less that you just have to be prepared to be so efficient.

</details>

**Anjney Midha**: 是的。有关于他们与OpenAI相比的烧钱率的数据。我写过关于这个的文章，但他们在方式上要高效得多。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yes. There's numbers on their burn compared to OpenAI. I've written about it, but they are so much more efficient in the in the way

</details>

**主持人**: 甚至不是...

<details>
<summary>Original English</summary>

**[Host]**: It's not It's not even

</details>

**Anjney Midha**: 差得远。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Not even close.

</details>

**主持人**: 是的。但这很明显，对吧？如何为世界输出最大化。他们准备好了。你可以称之为运气，但...

<details>
<summary>Original English</summary>

**[Host]**: Yeah. But it's so clear, right? Like how to output max for the world. They have been prepared. And you could call that luck, but

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 运气青睐有准备的头脑。

<details>
<summary>Original English</summary>

**[Host]**: Luck favors a prepared mind.

</details>

**Anjney Midha**: 这是我在回顾你的一些旧讲座时发现的事情之一，你说，数据，人们认为它是护城河，但实际上文化才是。实际上是团队。实际上。有不同层次的护城河，而这是决定其他一切的终极护城河。然后你可以复利。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: This is one of the things that I was going over some of your old lectures, and you were like, you know, data, people think it's a moat, and like actually it's culture. And actually it's team. Actually. And and I it's There's different levels of moats, and this is the ultimate one that determines everything else. Which you you can then compound.

</details>

**主持人**: 你是说文化是终极护城河。

<details>
<summary>Original English</summary>

**[Host]**: You're saying culture is the ultimate one.

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yes.

</details>

**主持人**: 是的。但文化的问题是它非常脆弱。所以护城河，我不认为我发现的护城河中有多少是真正的护城河。这是一个不错的概念。但在现实中，你必须不断补充你的文化。你知道，Ben Horowitz周二在CS183上做了演讲。我问他关于团队文化瓶颈的问题，因为你知道，有几个AI团队。

<details>
<summary>Original English</summary>

**[Host]**: Yeah. But the thing about culture is it's very fragile. So moats I I I don't think there's very few moats I found that are actually moats. There is is a nice concept. But in reality, you have to replenish your culture. You know, Ben Ben Horowitz was a the speaker in CS183 on Tuesday. And I I asked him this question about the culture bottleneck in

</details>

**Anjney Midha**: 他的书《创业维艰》。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: His book like Hard Thing About Hard Things.

</details>

**主持人**: 《创业维艰》。但更具体地说，如今有很多AI实验室拥有他们需要的所有现金。他们拥有他们需要的所有算力，但他们仍然无法交付任何实质性的产品。然后你开始看到人员流失等等。我的诊断是——这是文化问题。所以我问他，Ben，你知道，他是AI实验室最激进的投资者之一。他回到了一个在我脑海中引起共鸣的观点。当我在A16Z工作时，我会预订一个会议室，就在离厕所最近的那个会议室外面，因为那是我在Zoom会议间隙最快上厕所的方式。

<details>
<summary>Original English</summary>

**[Host]**: Hard Thing About Hard Things. But more concretely, there are so many AI labs today that have all the cash they need. They have all the compute they need and they're still not able to ship anything Soda. And then you start seeing people leave and so on. And my diagnosis it's is it's the culture. And so I asked him, Ben you know, there were he's been one of the most aggressive investors in AI labs. He goes back to this thing which resonates in my mind a lot. It When I used to work at A16Z, I would book a conference room and right outside the conference room which is closest to the toilet cuz it it was the fastest way for me to go use the bathroom between Zoom meetings.

</details>

**Anjney Midha**: 哦，天哪，我会把水槽放在马桶旁边进行优化。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Oh my god, I'll put my sink by toilet optimization.

</details>

**主持人**: 好吧，算了。事后看来，这不健康，但也许这是太多信息了。但不管怎样，在那个会议室外的墙上，印着一句名言：“文化不是一套信仰。它是一套行动。”这是日本哲学家武士道说的。如果你停止采取那些能证明使命一致性的行动，停止向你的团队和世界展示你所重视的东西，那么你的文化就会开始瓦解。所以，我认为它实际上不是一条护城河。它是一个非常脆弱的东西，需要像花园一样每天照料。但如果你找到了照料那个花园的系统，我认为最终归结为了解自己，因为如果你真实自然，你会自然而然地做出那些对你来说毫不费力的权衡，但这些权衡会强化你的文化。然后这就变成了别人很难追赶的东西。在Anthropic，从第一天起，就有一种传教士般的热情和信念，认为这些能力会扩展。这些系统是随机的，不是确定性的。会有误差范围。在我们攻克可解释性之前，存在风险。

<details>
<summary>Original English</summary>

**[Host]**: Okay, never mind. It was not healthy in hindsight, but maybe this is TMI. But anyway, outside that conference room on the wall was this quote that was printed that said, "Culture is not a set of beliefs. It's a set of actions." And it's by Bushido is a Japanese philosopher. And if you stop taking the actions that demonstrate the mission alignment to what you've said to your team and to your the world matters to you, then your culture starts to fray. So it's not actually a moat, I would say. It's a very very brittle fragile thing that requires daily tending to like a garden. But if you figure out the system to keep that garden tended, which I think ultimately comes down to knowing yourself cuz you most naturally if you're authentic and so on, you'll naturally make trade-offs that seem effortless to you, but that reinforce your culture. And then that becomes this very hard thing for other people to catch up to. And at Anthropic, from day one, you know, there was this mission-like missionary-like zeal and belief that hey, these capabilities will scale. These systems are stochastic, not deterministic. There will be error bars. And until we crack interpretability, there's risk.

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 在某个时候，人们会不再仅仅使用Claude进行编码。他们会将其用于某些关键任务场景，它可能会产生一个错误。然后人们会来指责他们。他们希望站在历史正确的一边，他们说，是的，这是一项强大的技术。我们认为它将改变世界。我们希望非常谨慎和科学地对待这样一个事实：嘿，伙计们，这些是统计模型。统计学就是这样运作的。归根结底，当你训练神经网络时，它只是一个统计系统。我认为那种安全很重要的信念，在早期可能看起来很儿戏，有时你可以说Anthropic完全夸大了风险，比如两年前他们说我们不要发布Claude 1之类的。好吧。也许事后看来是这样，但事后诸葛亮是20/20。在当时，他们不知道那个模型会被如何使用。对他们来说，如果有人来说你不负责任，那感觉是生死攸关的。它写了一个错误。与之相关的责任是巨大的。那么，如何防范呢？日复一日，你说安全，安全，安全，安全。当你开始偏离时，你让团队对你负责。你让世界对你负责。我认为随着时间的推移，这变成了一条护城河。在某个时候，那条护城河会受到挑战，然后它会变得脆弱。我希望它能持久，因为这就是让创始人掌舵的美妙之处。因为他们可以做出非常艰难的权衡来实现使命一致性。最难的部分是在最初的日子里，当你还没有一群一起经历困难、压力、危机的人时，你的文化就不会被足够清晰地定义。这就是我现在担心的。有太多的钱涌入这些实验室，没有困难。没有...

<details>
<summary>Original English</summary>

**[Host]**: And at some point, people will go stop using Claude just for coding. They'll use it in some mission-critical context where there's it'll throw off a bug. And then people are going to come blame them. And they want to be on the right side of history where they said, yes, this is a powerful technology. We think it's going to change the world. And we want to be very measured and scientific about the fact that hey guys, these are stats models, statistical models. That's how statistics works. Like ultimately, when you're training neural nets, it is just a statistical system. And I think that that belief that safety is important and that it might seem toy-like in the early days and sometimes there you could say Anthropic is they totally over exaggerated the risk, you know, like 2 years ago when they said let's not launch Claude 1 or whatever. Well, okay. Maybe in hindsight, but hindsight is 20/20. And at the time, they didn't know how that model would be used. And to them, it felt existential if somebody came and said, you weren't responsible. It this wrote a bug. The liability associated with that is massive. So, how do you prevent against that? Well, day in day out, you say safety, safety, safety, safety. And when you start deviating from that, you have the team hold you accountable. You have the world hold you accountable. And I think that becomes a moat over time. At some point, that moat will get challenged and so on, and then it will become fragile. I hope it endures because that's the beauty of having founders run the show. Cuz they can make really hard trade-offs to do mission alignment. The hardest part is in the earliest days when you don't have a group of people who are going through difficulty, stress, crisis together, then your your culture doesn't get defined sharply enough. And that's what I'm worried about right now. Is there so much money going to these labs, there's no hardship. There's no

</details>

**Anjney Midha**: 21知道。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: 21 knows.

</details>

**主持人**: 没有21知道。而事后看来，这对Anthropic来说是一个特性，而不是一个错误。说“不”的人数，说“对不起，我们已经是OpenAI的投资者了”的人数。那是竞争性防御。它迫使你真正理解，你愿意以牺牲其他一切为代价去死的山丘是什么。什么是P0？他们从第一天起的P0就是编码。那里的推理机制系统是，如果我们攻克了编码，那么我们就会攻克AGI。我们的使命是AGI。我们想安全地到达那里。如果我们专注于编码，这是一个普遍强大的能力。它可以加速计算机上的所有工作。如果我们能加速计算机上的所有工作，我们就能到达AGI。结果，他们不得不对很多其他事情说“不”。在这里，超导是使命。编码不是使命。所以我们使用Claude。我们会用Claude。我们不关心那个。使命定义一切。我认为那些能太快、太早筹集太多资金、不必定义P0是什么的团队，因为当你资源稀缺时，那是你唯一必须投资的东西。那些文化最终是最脆弱和易碎的。它们几乎无法起飞。

<details>
<summary>Original English</summary>

**[Host]**: There's no 21 knows. And that in hindsight was a feature not a bug for Anthropic. The number of people who said no, the number of people who said, "Sorry, we're already investors in OpenAI." That is competitive defense. It forces you to really understand like what is the hill you want to die on at the expense of everything else. What's the P0? And their P0 from day one was coding. The reason mechanism system there was if we crack coding, then we will crack AGI. You know, our mission is AGI. We want to get there safely. If we focus on coding, it's such a generally powerful capability. That it can accelerate all kinds of work on a computer. And if we can accelerate all kinds of work on a computer, we can get to AGI. You know, as a result, they've had to say no to so much other stuff. Here, superconductivity is the mission. Coding is not the mission. So, we use Claude. We'll use Claude. We don't care about that. The mission defines everything. And I I think teams who can raise too much money too fast too early, who don't have to define what the P0 is, because that's the only thing when you have scarce resources you got to

</details>

**Anjney Midha**: 是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah.

</details>

**主持人**: 你必须投资的东西。那些文化最终是最脆弱和易碎的。它们几乎无法起飞。

<details>
<summary>Original English</summary>

**[Host]**: you got to invest in. Those cultures end up being the most fragile and brittle. And they almost don't even make it to take off.

</details>

### Periodic Labs的约束

**Anjney Midha**: 那么，让我们把这个应用到Periodic，因为我们就在这里。当然。他们强迫自己经历的约束或困难是什么？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: So, let's apply this to Periodic since we're here. Sure. What is the constraint or the hardship that they were forcing themselves to go through?

</details>

**主持人**: 老兄，这里？这里？你疯了吗？不。嗯，是的，好吧。从技术层面来说，是物理学。它实际上是现实。

<details>
<summary>Original English</summary>

**[Host]**: Dude, here? Here? Are you crazy? No. [laughter] Well, yeah, okay. So, on a technical level, it's physics. It's literally reality.

</details>

**Anjney Midha**: 我的意思是。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I mean.

</details>

**主持人**: 但有没有另一个，比如公司建设方面的？

<details>
<summary>Original English</summary>

**[Host]**: But like is there is there is there another one that's like the company building

</details>

**Anjney Midha**: 是的。当...Liam是ChatGPT的联合创造者。Doge是Demis在DeepMind的隔级下属。他创建了Gnomics，这是DeepMind最重要的工具之一。当时我是斯坦福物理系的访问科学家，我们开始基准测试前沿模型在物理和科学能力方面的表现，它们不是很好。它们擅长做论文摘要之类的事情。但如果你说，“嘿，你能分析一下凝聚态物理实验室出来的科学数据吗？”我当时在斯坦福的凝聚态物理组。它们糟透了。所以，12个月前它并不受欢迎。你知道，公关...我不会深入细节，但你知道，就在几个月前，有人说他们想加入公司。他们，出于某种原因，接受了其他地方的工作。他们有点违背了承诺。他们接受了另一份薪水更高的工作。然后我们有了一个技术突破。创建了一个实质性的系统。

<details>
<summary>Original English</summary>

**[Host]**: Yeah. When I I Liam was a co-creator of ChatGPT. And Doge was skip level from Demis at DeepMind. Had created, you know, Gnomics, one of the one of the most important tools to come out of DeepMind. You know, at the time I was a visiting scientist at the Stanford physics department, and we had started benchmarking frontier models on physics and science capabilities, and they were not very good. They were good at like doing things like summarization of papers. But if you said, "Hey, could you like analyze the scientific data coming out of a condensed matter physics lab?" I was I was in the condensed matter physics group at at Stanford. They were terrible. So, it was not popular 12 months ago. You know, PR I could have And I won't go into details, but you know, there were people who said you know, as recently as a few months ago, who said they wanted to join the company. And they, for whatever reason, you know, took a job elsewhere. They kind of reneged on their commitments. They took a job elsewhere that offered more money. Then we had a technical breakthrough. Created a soda system and like

</details>

**Anjney Midha**: 好吧。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Okay.

</details>

**主持人**: 我很兴奋。

<details>
<summary>Original English</summary>

**[Host]**: I was excited.

</details>

**Anjney Midha**: 是的，是的，我们会报道的。我们会单独做一期关于Periodic的节目。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yeah, yeah, we'll cover it. We'll we'll be doing a separate part on on periodic.

</details>

**主持人**: 然后他们想回来。我说，“不。没门。你来这里，你已经有过机会了。你已经有过机会了。”

<details>
<summary>Original English</summary>

**[Host]**: And then they wanted to come back. And I said, "No. No way. You If you come here, you had your shot. You you had your shot.

</details>

**Anjney Midha**: 因为这实际上是关于文化。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Cuz it's actually about culture.

</details>

**主持人**: 当然。

<details>
<summary>Original English</summary>

**[Host]**: Of course.

</details>

**Anjney Midha**: 原则，是的。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: principles, yeah.

</details>

**主持人**: 你知道，听着，我相信第二次机会等等，但时间需要治愈。其中一些伤口会留下深深的伤疤，但因为我24、25岁就创办了公司，我经历了背叛和戏剧的整个循环，所以你意识到，硅谷既是一个非常传教士的地方，也是一个非常雇佣兵的地方。有时当大笔资金介入时，人们会失去理智，而从大局来看，这些钱其实很少。就像，你知道，我猜你拿的是...

<details>
<summary>Original English</summary>

**[Host]**: You know, and look, I believe in second chances and so on, but time will need to heal. Some of those wounds were they will leave deep deep for them will leave deep scars, but because I started my company at 24, 25, I had I went through the whole cycle of betrayal and drama, and so you realize you know, Silicon Valley is both a very missionary place, it's also a very mercenary place. Um sometimes people lose their minds with with a when big money gets involved, which is in the grand scheme of things quite small money. Like you know, we I I guess you're taking

</details>

**Anjney Midha**: 对我来说是改变人生的，对你来说可能少一些，但你知道，很多人没有被教导如何对待金钱。是的，我们并非来自那种特权背景，对吧？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Life-changing to me, maybe less to you, but you know, like a lot of people have not been taught how to deal with money. And yeah, we didn't come up from like that privilege of a background, right?

</details>

**主持人**: 一只流浪狗，兄弟。听着，我在Rishi Valley长大。我们没有...那是强制性的粗野主义。Jiddu Krishnamurti创办了那所学校，就像...你会睡在坚硬的石板上。床垫很薄，你知道吗？然后我去了新加坡。当我到新加坡时，我参加了一个奖学金项目，这很棒。我非常感谢新加坡政府。但我在圣安德烈初级学院，我们的宿舍在文庆地铁站附近。

<details>
<summary>Original English</summary>

**[Host]**: a street dog, man. I look, I grew up in Rishi Valley. We We didn't have like This was enforced brutalism. Jiddu Krishnamurti started the school was like you will sleep on a hard slab of stone. Like the mattress was this thin, you know? And then you go up in Singapore. When I got to Singapore, I used to sleep I was a part of the scholarship program, but which which was amazing. I'm very grateful to the Singaporean government. But I was at St. Andrew's JC and our dorm, which was by Boon Keng, you know, MRT,

</details>

**Anjney Midha**: 那不是个高档社区。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Which is not a prestigious neighborhood.

</details>

**主持人**: 那是一个过渡宿舍，因为他们在波东巴西的SAJC校园里建造美丽的住宅区，但我们是最后一批，我想是倒数第二批在过渡地点的，那是一个旧的，我想是外籍劳工宿舍。

<details>
<summary>Original English</summary>

**[Host]**: It was a It was a transition dorm because you're building this beautiful like residential campus on site at SAJC in Potong Pasir, but the we were the last, I think the second last batch to be in the transition site, which was some old like I think I think it's like an immigrant labor

</details>

**Anjney Midha**: 是的。那是我们安置在工厂等地工作的人的地方。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Yes. That's where we keep the people who work on the the factories and stuff.

</details>

**主持人**: 没错。所以我在11和12年级的时候，睡在一个只有从那里到这里的卧室里。是双层床。所以这里一张双层床，那里一张双层床，上面一张，上面一张，这里还有一张，然后这里是我们放洗漱用品和衣服的地方。当一个人爬上那边的床时，这张床就会摇晃。

<details>
<summary>Original English</summary>

**[Host]**: Right. [laughter] So I lived in a my 11th and 12th grade, I slept in a bedroom the size of this like literally from from there to here, right? They were like bunk beds. And so one bunk bed here, one bunk bed there, one on top, one on top, one more here, and then here was where our like we kept our toiletries and clothes and stuff. And when one guy would climb onto his bed there, this one would shake.

</details>

**Anjney Midha**: 哦，天哪。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Oh my god.

</details>

**主持人**: 我的一个室友，太棒了。我热爱每一分钟。我的室友是一个来自中国的顶级Dota玩家，一句英语都不会说。我爱他。了不起的家伙。

<details>
<summary>Original English</summary>

**[Host]**: And one of my roommates who was from and it was amazing. I loved every minute of it. You know, my my roommates were a guy who was a top-ranked Dota player from BRC from China, didn't speak a lick of English. Uh loved him. Amazing guy.

</details>

**Anjney Midha**: 我的意思是，所有的新加坡学者都很棒。老实说，我们应该更好地对待你们，因为你们将要做出的事情，但知道这些很酷。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I mean, all the Singapore scholars are fantastic. And honestly, we should treat you guys better cuz of what you're going to do, but

</details>

**主持人**: 不，我的意思是，我在说的是，我不需要太多就能在生活中快乐。当你经历过那些，金钱是一种...我认为有时我们用它来衡量自己，但当它不再只是副产品而更多是一种衡量标准时，它就失去了意义。

<details>
<summary>Original English</summary>

**[Host]**: No, I mean what I'm saying is I don't need much to be happy in life. You know, when you've lived through that, money is a way I think sometimes we measure ourselves, but you know, when it's when when it stops becoming, you know, it works good hearts law when it stops becoming just a byproduct and more of a measure, it stops having meaning.

</details>

**Anjney Midha**: 你用钱来做更有意义的事情。它是追求使命的资源。我留你的时间已经超过了预期，但我们应该在下一部分继续这个话题。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: You use it to do more meaningful things. It's resources to pursue your mission. Uh I've kept you longer than I am supposed to, but we should continue this in the next part two.

</details>

**主持人**: 知道吗，我真的很享受这次谈话。是的，是的，我的意思是，你太鼓舞人心了，是的，我想深入探讨更多关于你是如何建立一切、你的每一项投资、Amp的进展，但我们时间不够了，但非常感谢你加入我们。

<details>
<summary>Original English</summary>

**[Host]**: know, I really enjoyed this. Yeah, yeah, I mean, you're you're so inspirational and yeah, there's more I want to dig into about how you've like set everything up, every single one of your investments, how amp is going, but we don't we're running out of time for that, but thank you so much for joining us.

</details>

**Anjney Midha**: 很高兴见到你，兄弟。改天一起去吃鸡饭吧。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: to see you, man. Let's get chicken rice sometime.

</details>

**主持人**: 好的。我实际上明天就有。我会把细节发给你。我正在举办一个生日派对。

<details>
<summary>Original English</summary>

**[Host]**: Yes. I'm actually tomorrow. I'll send you I'll send you the details. I'm hosting a birthday party.

</details>

**Anjney Midha**: 我没有收到邀请吗？

<details>
<summary>Original English</summary>

**[Anjney Midha]**: I don't get an invite?

</details>

**主持人**: 这是一个新加坡式的生日派对，是的。你现在就收到邀请了。

<details>
<summary>Original English</summary>

**[Host]**: to be a Singaporean birthday party, yes. Yeah, you get an invite right now.

</details>

**Anjney Midha**: 好的，酷。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: Okay, cool.

</details>

**主持人**: 好的，谢谢你。

<details>
<summary>Original English</summary>

**[Host]**: All right, thank you.

</details>

**Anjney Midha**: 好的，谢谢，兄弟。

<details>
<summary>Original English</summary>

**[Anjney Midha]**: All righty, thanks, man.

</details>