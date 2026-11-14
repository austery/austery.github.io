---
author: All-In Podcast
date: '2026-05-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=10MdOvK-aG4
speaker: All-In Podcast
tags:
  - compute-economics
  - regulatory-capture
  - monopoly-dynamics
  - economic-productivity
  - cyber-defense
title: 马斯克与 Anthropic 联手：AI 算力霸权、垄断隐忧与“AI 版 FDA”的监管风暴
summary: 本期 All-In Podcast 深入探讨了 Elon Musk 的 xAI 与 Anthropic 达成的 Colossus 算力租赁交易，分析了 EWS（马斯克网络服务）作为第四大超大规模云服务商的崛起。嘉宾们就 Anthropic 的指数级增长是否会导致历史性垄断展开激烈辩论，并针对白宫可能设立“AI 版 FDA”的传闻及其对创新的潜在破坏性进行了深度解析。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Elon Musk
  - Dario Amodei
companies_orgs:
  - OpenAI
  - Anthropic
  - xAI
  - SpaceX
  - Nvidia
products_models:
  - Claude
  - Grok
  - Colossus
  - GPT-5.5
media_books: []
status: evergreen
---
### 洛杉矶市长竞选与 Spencer Pratt 的政治广告

**Jason**: 大家好，欢迎回到全球排名第一的播客——All-in Podcast。今天和我们在一起的有 **Chamath Palihapitiya**、**David Sacks**，还有我们的第五位好兄弟 **Brad Gerstner**。David Friedberg 好像得了某种“社会主义流感”，他读了太多关于社会主义的东西，感觉很不舒服。不过他下周会带着两个精彩的访谈回来。

<details>
<summary>Original English</summary>

**Jason**: All right everybody, welcome back to the number one podcast in the world. It's the All-in podcast. With us today, Chimoth Polyatia, David Saxs, and our fifth bestie, Mr. Brad Gersonner is here. I think David Freeberg is suffering from some socialist related flu. He's very sick of reading about socialists, but he'll be back next week with two incredible interviews.

</details>

**Brad**: 你们看到 **Spencer Pratt** 的广告了吗？哇，那是我见过最好的政治广告之一。

<details>
<summary>Original English</summary>

**Brad**: You guys see those Spencer Pratt ads? Wow. It's one of the best political ads I've ever seen.

</details>

**Sacks**: 无论那个社交媒体团队是谁，他们都火了。如果你有一个好的社交媒体团队和广告制作团队，那就是下一代。Spencer Pratt 如果能赢得洛杉矶的选举，原因就是 Brad 说的：那些广告太不可思议了。他还是个很棒的辩论者。他面对的是市长 Karen Bass，她基本上是非常左翼的，还有一个市议员比她更左，简直快到菲德尔·卡斯特罗的程度了。Pratt 指出，那位批评市长解决无家可归问题不力的市议员，实际上正是负责这些项目的人。

<details>
<summary>Original English</summary>

**Sacks**: Whoever that social media team is is on fire. If you get a good social media team and a good ad production team, I think it's nextgen because these things go crazy. And Spencer Pratt, if he wins this election, which I think he's going to in Los Angeles, the reason is what Brad said. Those ads are incredible. Well, he's also quite a good debater. He's up against Karen Bass, who's the mayor, who is basically extremely leftwing. And then there's someone who's a city council woman who's even further to the left of Karen Bass. I mean, she's often like Fidel Castro territory. Pratt pointed out that this council woman is actually in charge of all these homeless programs already.

</details>

**Jason**: 他彻底击溃了她。他提出了关键点：这里的问题不是缺乏住房，而是成瘾和精神疾病。

<details>
<summary>Original English</summary>

**Jason**: He eviscerated her. And he basically made the key point, which is, look, the problem here is not lack of housing. It's an addiction issue, and it's a mental illness issue.

</details>

### 马斯克向 Anthropic 出租 Colossus 超级计算机

**Jason**: 好了，进入正题。**Elon Musk** 刚刚把他的 **Colossus 1** 数据中心全部租出去了，租给了 **Dario Amodei** 和 **Anthropic**。Chamath，你在上周的播客里说 Elon 和 Dario 应该达成协议，结果 5 天后就成了。由于明显的算力限制，Anthropic 刚刚增加了超过 **220,000 块 Nvidia GPU** 和 300 兆瓦的电力。这笔交易已经产生了影响：**Claude** 的代码生成限制翻倍了，取消了付费用户的峰值限制。马斯克在算力上的豪赌正在产生回报。我们可以聊聊 **EWS（马斯克网络服务）** 的崛起了，他现在是与 Google Cloud、AWS 和 Azure 竞争的超大规模云服务商。

<details>
<summary>Original English</summary>

**Jason**: All right, let's get to the dot. Elon just leased all of Colossus 1, his data center. Shocking to Dario and Anthropic. Chamath on last week's pod, you said Elon and Dario should do a deal tomorrow. It happened 5 days later. Because of Anthropic's obvious compute constraints, Anthropic just added over 220,000 Nvidia GPUs, over 300 megawatts of energy. The deal is already having an impact. Claude has now doubled the Claude code rate limits, removed peak usage caps for paid users. Elon made a great bet on compute and built up those data centers really fast and that is now paying off. Let's talk about the emergence of Elon Web Services EWS. He is now in the hyperscaler competing against Google Cloud, Amazon Web Services and Azure.

</details>

**Chamath**: 我认为这笔交易太棒了。首先，正如我几周前提到的，Anthropic 和 OpenAI 的收入表现与需求完全无关，而完全取决于**数据中心和电力的供应限制**。如果他们有无限的电力，我认为他们的收入会呈抛物线式增长。他们真正需要的是更多算力和电力。其次，在这个背景下，Elon 的机会在哪里？人们试图给 **SpaceX** 的估值找茬时，最大的不确定性在于**轨道数据中心**的价值。通过落地大量的地面算力，即使轨道数据中心推迟几个月，他现在也拥有了核心业务来补贴他训练 **Grok** 的能力。他抢在所有人之前看到了算力成为核心资产，现在他成了“造王商”。

<details>
<summary>Original English</summary>

**Chamath**: I think the deal is fantastic. First, as I mentioned a couple weeks ago, Anthropic and OpenAI's revenue performance has nothing to do with demand. It is entirely to do with the supply constraints that exist in data centers and specifically in power. If they had infinite power, I think that their revenues would probably be even more parabolic. The thing that they really need is more compute and more power. The second thing is the opportunity for Elon. When people try to red team the SpaceX valuation, the biggest element is the on-the-c value around the orbital data centers. By actually landing a bunch of terrestrial capacity, he now has this structural core business that will effectively subsidize his ability to train Grock. He built to a level of scale and secured power before most people. It has now become the critical asset. And now he's kind of kingmaking.

</details>

**Brad**: 说得好。地球上没有人比 Elon 更擅长将**电子转化为 Token**。这笔交易预计今年将产生 40 到 50 亿美元的增量收入，这足以抵消他的投资成本，并补贴下一代 Grok 的研发。马斯克拥有三个设施：**Colossus**、**Macro Hard** 和 **Macro Harder**。他把连接性稍弱、适合推理的 H100 租给了 Anthropic，实现了大规模变现。他现在成了超大规模云服务的直接竞争对手。而且我要纠正一个迷思：那些抗议数据中心建设的人不是自发的当地居民，而是资金雄厚的**专业抗议者**，就像 30 年前阻止核电站建设的人一样。而在德州，数据中心建得最多，电费反而下降了。

<details>
<summary>Original English</summary>

**Brad**: Yeah. First we know that there's nobody better on planet Earth than Elon at converting electrons to tokens. I estimate that this is going to generate in this year an incremental 4 to 5 billion of revenue. And that will subsidize all that he's investing to build the next generation of Groth. Remember too that he has three facilities, Colossus, Macro hard, and Macro harder. H100's great for inference to anthropic. He's monetizing it in a big way. Now he becomes an immediate competitor in the hyperscaler. I want to dispel this myth, these are not organic local protests. This is highly organized activists. In Texas, where you're building the most data centers in the country, electricity costs are going down.

</details>

### Anthropic 的“指数级”增长与垄断隐忧

**Sacks**: 让我们准确评估一下现在的 AI 市场。过去三年，Anthropic 每年以 10 倍的速度增长。今年前四个月，他们的 **ARR（年度经常性收入）** 从 100 亿飙升至 440 亿。在硅谷，虽然我们习惯了指数增长，但也从未见过这种规模的增速。如果这一趋势持续，Anthropic 很有可能在今年底达到 **1000 亿 ARR**。这意味着他们可能成为历史上最有价值的科技公司，甚至比“美股七巨头”加起来还值钱。

<details>
<summary>Original English</summary>

**Sacks**: Let's just honestly and accurately assess where the state of this AI market is at right now and Anthropic's place within it. So for the last 3 years, Anthropic has been growing at a rate of 10x a year. In April, they went from 30 to 44 billion of ARR. Nobody in Silicon Valley has ever seen anything like it. It's pretty much a foregone conclusion that they will hit that forecast of 10x this year exiting the year. Call it roughly 100 billion of ARR. And now the only question is whether they hit a trillion in 2027. They'll easily be the most valuable tech company in history.

</details>

**Sacks**: 除非轨迹发生变化，否则 Anthropic 将成为**人类历史上最强大的垄断者**。Dario 称之为 AGI，我称之为历史上最大的垄断。想想**约翰·D·洛克菲勒**。如果他当年懂公关，不叫“标准石油”，而叫“**安全石油（Safe Oil）**”，因为煤油可能点亮家庭也可能烧毁城市，所以他呼吁建立政府机构来监管安全性。人们会纠结于灯芯的厚度，而忽略了他正在建立有史以来最强大的垄断。Anthropic 现在的“安全”话术就像是一种**监管套利（Regulatory Capture）**，旨在巩固垄断地位，阻止竞争。

<details>
<summary>Original English</summary>

**Sacks**: Unless something about their current trajectory changes anthropic will be the most powerful monopoly ever created in human history. Dario calls it AGI. I call it the biggest monopoly in human history. Imagine if John D. Rockefeller was way better at public relations, and instead of calling his company Standard Oil, he called it safe oil. He called for the creation of a new government agency to regulate the safety of his product. People would have gotten so wrapped up in this debate over safe kerosene that they would have missed what was really going on, which is that Rockefeller was building the richest, most powerful monopoly of all time. I do think that a lot of the the safetiest policies are basically calling for a form of regulatory capture.

</details>

**Brad**: 这种说法太荒谬了。AI 比赛才刚刚开始。谷歌、亚马逊也在产生巨额现金流来支持投资。Anthropic 和 OpenAI 还是雏鸟，非常脆弱。我希望看到的是竞争，而不是 DC（华盛顿）介入并设置障碍。

<details>
<summary>Original English</summary>

**Brad**: It's ridiculous to think of this as a monopoly. We're talking about annual run rate revenues, but on a gap basis, they're doing about the same revenue as OpenAI. Google, Amazon, these companies are producing hundred billion dollars of free cash flow to justify their incremental investment. At the same time, you have these two startups that are still fledgling. The last thing I want to be doing is seeing people talk about this and throwing roadblocks into the way of the competition.

</details>

### “AI 版 FDA”的监管风暴

**Jason**: 据报道，白宫正在考虑为 AI 设立一个类似 **FDA** 的机构，用来审核新模型的安全性。甚至有报道称特朗普也在考虑成立一个“AI 工作组”。据说触发点是 Anthropic 的 **Mythos 模型**，它强大的网络攻击能力吓坏了白宫。

<details>
<summary>Original English</summary>

**Jason**: The White House allegedly, possibly is considering, according to reports, an FDA for AI that would vet new models for safety. New York Times reported Trump is considering an executive order to create an AI working group. According to the report the catalyst was Anthropic's mythos model which reportedly spooked people really nervous at the White House.

</details>

**Brad**: 我昨晚和 **Kevin Hassett** 聊过，他不认为 FDA 是正确的类比。他只是想说，政府需要准备好、加强系统安全。没有人真的相信我们会进入一个审批制度，那种模型上线前必须让华盛顿预先批准的做法将是一场灾难。我们不能在 AI 竞赛的起跑线上就开始挑选赢家。

<details>
<summary>Original English</summary>

**Brad**: Actually, I don't think they're slightly different positions. I talked to Kevin last night, and he said I was only bringing it up to say that we want them to show us the models so that we can coordinate them. But he does not think that we're going to move to an approval regime. The approval regime is a disaster. We don't want to put the Washington in the position of picking winners and losers when it comes to these models.

</details>

**Chamath**: 我认为这反映了科技界与大众之间深刻的“氛围转变”。主流社会已经对科技巨头和 AI 感到不安，这种情绪正在渗入华盛顿。我们的问题在于两点：第一，信息传递太烂，没人去宣传 AI 的积极面；第二，人们担心只会产生几个巨头，而剩下的人全是输家。科技领袖在应对这一点上表现极差，我给他们打 **D-**。如果我们只是让三个家伙拥有万亿身家并掌握钥匙，监管必然会到来。

<details>
<summary>Original English</summary>

**Chamath**: I think that there's a pretty profound vibe shift with respect to tech, tech oligarchs, and particularly the AI. That vibe shift has already happened on Main Street, and I think that that's starting to seep into Washington. We suffer from two things. Number one is we have horrible messaging. And two, the idea that there's going to be a few winners and many, many, many potential losers. I'd give the community, the tech leaders a Dminus, trending to an F.

</details>

### 网络安全、KYC 与 AI 的经济账

**Sacks**: 所谓的“AI 版 FDA”很大程度上是**假新闻**。我接触的高层没人支持这个。总统比特朗普更支持创新，苏西·威尔斯昨晚也发了声明驳斥。但关于 Mythos 或网络安全的担忧是合理的。所有顶尖实验室，包括中国的，都会在几个月内拥有极强的网络攻击能力。我们需要加强系统防御，把这些工具交给 **CrowdStrike**、**Palo Alto Networks** 这样的网络安全巨头。

<details>
<summary>Original English</summary>

**Sacks**: Look, I think there's several things going on here. The first one is there's a lot of fake news. This whole idea of an FDA for AI, I don't think any senior official supports it. There is a legitimate thing happening here with let's call it mythos or cyber. We do need there to be a hardening of systems. We should be getting these tools in the hands of our cyber security industry.

</details>

**Chamath**: 你认为模型以后应该加上 **KYC（了解你的客户）** 外壳吗？在使用像 Mythos 这样的模型前必须进行身份识别。

<details>
<summary>Original English</summary>

**Chamath**: Do you think that the models should have a KYC rapper going forward? KYC for the audience is know your customer. Before you can use mythos you have to identify yourself.

</details>

**Sacks**: 我认为在预览期进行 KYC 是合理的，以确保工具不会落入恶意行为者之手。但一旦模型进入公测，KYC 的意义就不大了，因为用的人太多了。我们要防范的是那些利用危机来建立永久性官僚机构的**“末日论者”**。

<details>
<summary>Original English</summary>

**Sacks**: Yeah, look, I think that before giving your API for a super powerful model, you should not give that to a company or an actor. You don't know who they are. So, yeah, some basic KYC makes sense. What they're trying to do is use that issue to try and create a permanent new infrastructure in Washington.

</details>

**Jason**: 我们谈谈经济影响。AI 的负面预期很多，比如抢走工作，但没人谈论它对医疗、教育和科学的巨大推动。我主张那些即将上市的万亿级 AI 公司，应该给每个美国公民一部分股份。

<details>
<summary>Original English</summary>

**Jason**: There's no reason why Nvidia, SpaceX, Anthropic when they go public couldn't give a portion of the IPO to every American citizen. We should really look deeply at the minimum wage and study what happened in New Zealand, Sweden when they raised it. We should opt in to trying to raise the minimum wage company by company.

</details>

**Sacks**: AI 并不受大众欢迎，但在选民关注的议题中仅排第 29 位。选民最关心的是**生活成本和经济**。而 AI 本质上是**通缩**的，它帮助降低成本。今年第一季度，AI 贡献了 **75% 的 GDP 增长**。它不仅带动了硅谷，还带动了建筑业和蓝领阶层的工资增长。

<details>
<summary>Original English</summary>

**Sacks**: AI ranked 29 out of 39. It is certainly not top of mind for voters. What is top of mind for voters? Number one, cost of living. Number two, the economy. And we know that AI is deflationary. It was 75% of GDP growth in Q1. We're seeing a construction boom, a blue collar boom.

</details>

**Chamath**: 目前还没有证据表明 AI 提升了标普 500 指数成分股的利润率。现在仍处于大规模实验阶段。我预测未来 500 天内会有一次清算，那些为 Token 付费的企业需要看到真正的 **ROI（投资回报率）**。要么缩减人力成本提升利润，要么收入通过 AI 增长，否则这个飞轮无法持续转动。

<details>
<summary>Original English</summary>

**Chamath**: To be very clear and blunt, there is literally not a cintilla of evidence that AI has helped lift the operating margins of the S&P 500. There's going to be an important fork in the road, probably two or three years from now. One path will be opex shrinks, hence margins increase. We have kind of call it 500 days where you just got to be net long. The people that are paying for all these tokens need to see an actual benefit.

</details>

**Jason**: 总结一下，今天我们学习了很多，也辩论了很多。恭喜马斯克和 Anthropic 的合作。我们拥有美国最好的竞争框架，我们要坚持这一路线。美国必胜！

<details>
<summary>Original English</summary>

**Jason**: We had a great show, everybody. We all learned. We workshopped some stuff. Let's leave it where it is. I want to congratulate Elon and Dario on their recent deal. We have the best competitive framework in the country. America for the win.

</details>