---
author: Latent Space
date: '2026-11-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=lCtMq8jegvo
speaker: Latent Space
tags:
  - data-quality
  - human-feedback
  - multi-agent-systems
  - robotics
  - infrastructure
title: G2I 创始人分享人类数据演变与 AI 基础设施建设
summary: G2I 的 CEO Gabe Greenberg 探讨了高质量人类数据在模型训练中的核心作用，强调从“零工经济”式的标注转向由资深工程师参与的复杂数据构建。他介绍了 G2I 在提供前沿实验室数据、多模态数据（如 3D、机器人）以及基于 Rust 构建的多 Agent 编排平台 Orc.AI 方面的业务，并预测未来 AI 竞争将转向更深层次、更复杂的垂直领域。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - G2I
  - AIE
products_models:
  - Orc.AI
  - Swebench
  - Swebench Pro
media_books: []
status: evergreen
---
但如果你把它们出得太难，它们就成了评估（eval），对吧？呃，如果你把它们出得太简单，它们就没用。所以你需要把它们出得恰到好处，只比模型今天能做到的多出几步。这样它们才是可训练的，而且是高效可训练的。好的，我们现在在 AIE Code，这是今天的第一场播客，呃，嘉宾是 G2I 的 CEO Gabe Greenberg。
<details><summary>Original English</summary>
But if you make them too hard, they become eval, right? Uh and if you make them too easy, they're they're worthless. So you need to make them just hard enough that they're a few steps away from what the model can do today. So they're trainable and efficiently trainable. Okay, we're here at AIE Code, first podcast of the day, uh with Gabe Greenberg, CEO of G2I.
</details>

>> 很高兴来到这里。一如既往地愉快。呃，这是 AIE 首次与外部合作伙伴 G2I 联合举办的会议。呃，你们做得太棒了。嗯，和你们团队合作非常愉快。呃，我显然认识你超过 10 年了，也许大概 10 年吧。嗯，你们还运营 React Miami、AIE Miami，现在又和我们联合举办 AI code。嗯，但你知道，那是你的副业。G2I 是做什么的？呃，我们……我们做人类数据和……和 computer use，你知道，为实验室构建基础设施，帮助他们训练模型，你知道，从编程到 computer use，而且我们正在拓展到 3D 模型、呃，你知道，STEM、嗯，机械工程等等，但那个……显然对更好模型的需求非常巨大，你知道，这非常符合杰文斯悖论（Jeban's paradoxy），所以你知道，是的。
<details><summary>Original English</summary>
>> Glad to be here. Always a pleasure. Uh this is the first ever co-organized conference between AIE with a external partner G2I. Uh and you guys are crushing it. Um it's been such a pleasure to work with your team. U I've obviously known you for more than 10 years maybe I think maybe 10 years. Um and you guys run React Miami, AIE Miami, and now you're co-running AI code with us. Um but that you know that is your side project. What is G2I? uh we uh we do human data and uh and computer use you know build infrastructure for the labs to help them train models you know some coding to computer use and and we're branching out into 3D models uh you know STEM um mechanical engineering etc but the uh there's just a massive demand for uh obviously better models you know it's very uh Jeban's paradoxy so you know yeah
</details>

>> 是的，你用得越多，就越会发现想用它来做的事情，然后它就从那里不断增长。嗯，关于你们正在做的事情的规模，有哪些可以公开炫耀的数据吗？
<details><summary>Original English</summary>
>> yeah the more you use the more you find things you want to use it for and and it just keeps growing from there Um what are some of like the bragg public numbers that you can give around the scale of uh what you're doing?
</details>

>> 有的。呃，去年我们做了 1500 万。呃，今年大概会做到 1 亿。没有风投支持。
<details><summary>Original English</summary>
>> Yeah. Uh last year we did 15 million. Uh this year will be about 100 million. No VC backing.
</details>

>> 天哪。
<details><summary>Original English</summary>
>> Jesus.
</details>

>> 你知道，这是一家盈利的公司。嗯，我觉得我们明年可以，你知道，轻松翻三倍。
<details><summary>Original English</summary>
>> You know profitable company. Um I think we could you know easily triple next year.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 嗯，而且……这真的……这是一个解决起来非常有趣的问题。
<details><summary>Original English</summary>
>> Um and uh it's it's just a it's a really fun problem to solve.
</details>

### 客户格局与人类数据的演变

>> 你们只卖给 Frontier Labs 吗，比如，有没有非前沿实验室，或者这个市场是什么样的？就是 Frontier Labs，你知道。
<details><summary>Original English</summary>
>> And you're selling only to Frontier Labs like you know are there non-frontier labs or what is this market like? It's it's Frontier Labs, you know.
</details>

>> 所以，大概有五个客户。
<details><summary>Original English</summary>
>> So, there's like five customers.
</details>

>> 大概有五六个客户，但你会看到其他一些实验室开始，你知道，那些不是前两三名的不同实验室融到了不同金额的钱，然后他们带着这些来到谈判桌，你知道，他们可以购买不同数量的数据。我觉得有趣且尚未公开的一点是——我不会透露具体细节——但你知道，实际上只有一家实验室拥有非常、非常、非常成熟的人类数据运营体系，比如在基础设施、内部人员方面，甚至不仅是他们的 IT，还有他们运营的方式，就像一个非常庞大、成熟的团队；而最近我看到这种能力在实验室内部增长，包括他们如何与……与他们的研究人员打交道，如何与供应商打交道，因为之前有太多都是现成数据（off-the-shelf data）。现在有一些向合作关系转变的趋势，因为基准测试（benchmarks）越来越难，你必须从指令开始一路向下迭代，你知道，才能把数据做对。
<details><summary>Original English</summary>
>> There's like five or six customers, but you you see some of like the other labs starting to, you know, the different labs that aren't the top, you know, two or three raising different amounts of money and then they come to the table with, you know, they can buy different amounts of data. I think what's interesting and is not publicly known and I won't go into specifics but you know only really one of the labs had a very very very mature human data operation like like in terms of like the infrastructure the people in house but not even their it how they run it like a very large mature team and that lately I've seen it grow internally [clears throat] inside the labs of of how they deal with uh with their researchers how they deal with vendors how you know so much of it was off-the-shelf data. There's there's some movement towards partnership because the the benchmarks are getting harder and you just have to iterate on everything from instructions on down you know to get the data right.
</details>

>> 是的。我的意思是，这一直是我在探索的事情，对吧？比如很多人熟悉 RLHF 时代的人类标注，那时你主要是找来自尼日利亚之类地方的人，呃，让他们说这个样本是不是比另一个读起来更好，然后他们会选“delve”这样的词，这也是为什么模型以前很喜欢用“delve”。呃，人类数据发生了怎样的变化，你知道，大家现在想要什么？
<details><summary>Original English</summary>
>> Yeah. I mean this is something I've been exploring right like a lot of people are familiar with the RLHF [snorts] era of human labeling where you're mostly getting like people from like Nigeria or whatever uh to say like does this read better than the other sample and they'll choose words like delve delve like why models used to like delve a lot um how has human data changed you know like what what do people want now
</details>

>> 每 6 个月就是一次巨大的转变，就像总体上模型也是那样，你知道，明显地……2023、2024 年这刚开始起飞的时候，呃，你会看到有 6000 名工程师参与的项目。他们是中级工程师。他们的报酬不算特别高。那种感觉……更像是零工经济（gig work）。嗯，你知道，快进到去年和今年，你真正看的是资深工程师（staff level engineers）。嗯，这是非常复杂的数据集构建。嗯，这其中涉及品味（taste）工作。嗯，你不再处理那些庞大的项目了。形态已经改变了。现在你展望机器人之类的领域。那里的数据收集是极高体量的。它又从头开始了。所以它是质量差距。它，你知道，它是细微差别。你帮忙做过的那个基准测试，你知道，基准测试正在变得更好，而且更……你们对如何去做这件事更聪明了。你看看 Swebench 或 Swebench Pro，从一开始指令就很糟糕，你知道，就是有巨大的漏洞。
<details><summary>Original English</summary>
>> every 6 months it's a massive shift like in general the models are like that you know on uh overtly um 2023 24 when this really started to take off uh you'd see projects with 6,000 6,000 engineers on it. They'd be mid-level engineers. They weren't paid exceptionally well. That kind of like it it was a more gig work. Um you know, fast forward, you know, last year and this year, you're really looking at staff level engineers. Um it's very complex data set building. Um there's taste work involved. Um, and you're no longer dealing with these massive, you know, projects anymore. The shape has changed. Now you look forward to robotics and things like that. The data collection there is like extremely high volume. It's it's starting all over again. So you're it's quality gaps. It, you know, it it's the nuances. The benchmark that you helped with, you know, the benchmarks are getting better and more, you know, you're smarter about how you go about it. you look at Swebench or Swebench Pro, it was just from the out the get-go the instructions were bad, you know, like there was just massive holes.
</details>

>> 我想很多人不了解 Sweetbench，尽管它作为行业顶级基准测试长达一年多，呃，但它其实像是一个本科生项目。呃……
<details><summary>Original English</summary>
>> I think a lot of people don't understand that Sweetbench uh even though it was like the top industry benchmark for like a year plus uh was like an undergrad project. Uh
</details>

>> 我之前不知道，但这确实说得通。
<details><summary>Original English</summary>
>> I didn't know that but but it but it checks out.
</details>

>> 是的，你知道，它就像是第一篇发表的论文之类的，然后不知怎么就火了……
<details><summary>Original English</summary>
>> Yeah. you know, like it's like a first first thing first paper ever published and then somehow it got
</details>

>> 对，因为再说一次，任何东西只要背后有足够多的推动，它不一定非得很好，你知道，就能……对，就能……
<details><summary>Original English</summary>
>> right because again anything that just gets a lot behind it, it doesn't need to necessarily be good, you know, to get right to get
</details>

>> 而且说清楚，那是我见过的最顶尖的本科生项目之一，对吧？
<details><summary>Original English</summary>
>> and to be clear like one of the top under undergrad projects I've ever seen, right?
</details>

>> 但尽管如此，你知道，当时还是需要大量的验证。
<details><summary>Original English</summary>
>> But still, you know, there's a lot of validation that was needed.
</details>

>> 在它那个时代它很棒，但当你把提示词和指令交给模型，而且这些指令作为基准测试的一部分直接写明了你该如何修复一个 bug，那这可能，你知道，不会是最好的起点。但你知道，我们作为一个行业把这件事弄明白了，而且……你知道，前沿领域真的很有趣，前沿之所以有趣，是因为研究人员太专注于自己正在做的事情，以至于他们需要外部视角。这就是我们介入的地方，你知道，研究之外的视角。我们不只是带来人，我们带来研究。
<details><summary>Original English</summary>
>> It was great for it time, but when you're when you're giving prompts and instructions to the model that like goes into exactly how you'd fix a bug as part of a benchmark, it's probably, you know, not going to be the the best start. But you know, we figured it out as an industry and uh and you know, the frontier is just really interesting and the frontier is interesting because the researchers are so focused on what they're doing that they want outside. This is where we come in, you know, outside of research. It's not just we don't just bring people, we bring research.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你知道，把它带到桌面上，发现差距，我们帮助他们跳出自己的圈子去思考，你知道，这非常高强度。
<details><summary>Original English</summary>
>> You know, to the table and find gaps and we help them kind of think outside of their own sphere, you know, which is intense.
</details>

### 从招聘业务到构建 RL 环境

>> 是的。我想……你知道，有一件事我确实想提一下，你之前有做招聘业务的背景，对吧？在某种程度上，这是那项业务的下一步自然演进，因为你本来就得招人，而且你得招募聪明人、优秀的工程师，所以这很大程度上依赖你的那套技能。我想说唯一让我觉得很有趣的区别是，如果我是这些……这些人类专家中的一员，他们不是在做生产项目，而是在做 RL 环境，或者在为人们制作某种数据集。
<details><summary>Original English</summary>
>> Yeah. I I think um you know one thing I I do want to bring up is that you had a legacy or you had a you came from a recruiting business, right? And in some ways this is the natural next evolution of that like you have to recruit people anyway and you have to recruit um smart people, good people at who are good engineers and so that relies on a lot on your skill sets. The only difference I would say which is very interesting to me if I was one of these people uh these uh human human experts is that they're not working on a production project. they're working on the RL environments or they're working on some kind of data set for for people.
</details>

>> 是的。嗯，我的意思是，很多像 Handshake 这样的平台——它全是 STEM 方向、全是博士——他们之前增长并不快，当时只是某种招聘市场，然后实验室找上了他们。所以，这种事大概发生在我们五个……就像我们大家都在同一时间转型，对吧？所以，就像你说的，这是自然演进。不过，此外，那些专注于自己网络和社区中最顶尖人才的公司，到今天会比两年前更适应当前的需求。就像你当年进来一样，我就是 10 年前通过 G2I 认识你的，对吧？当时我们对让谁加入非常挑剔，基于 React 领域最顶尖的水准是什么，或者，你知道，那里有很多细微的考量。嗯，所以现在当你进入我们的网络时……是的，我们仍然有招聘市场，但现在非常小了，呃，一切都面向实验室。嗯，我觉得 RL 环境有很多反模式（anti-patterns），你知道，就是你本该怎样开发软件，与 RL 环境需要什么、代码质量是什么、或者 RL 环境的质量是什么之间的差异。比如有验证器（verifiers）、有任务、有你放进去的种子数据（seed data）。里面牵涉到太多层级。我觉得这是一个更有趣、也不同的问题，但确实，它不只是做一个功能，或者只是整个代码库那么简单。
<details><summary>Original English</summary>
>> Yeah. Um well, I mean a lot of these handshake which is all like the STEM side, all the PhDs, they were not growing quickly and they were a a hiring marketplace of some sort and then the labs got to them. So, it's happened with like five of our like we were all moving around the same time, right? So, it's a natural evolution like you said. Um, additionally though, like the ones that have focused on the the best people in their envir in their in their kind of network, in their community end up better suited for today than they did 2 years ago. Like you came through, that's how I met you is through G2I, you know, 10 years ago, right? And we were extremely particular with who we let in based on what the the best, you know, of React was or, you know, and and there was a lot of nuances there. Um so now when you come in you know to to our network uh yeah we we still have the the the hiring marketplace it's very small though now uh everything is to the labs. Um, I think RL environments there's a lot of anti-atterns, you know, with how you're supposed to develop software versus what the RL environment needs and like what code quality is or what the quality of the RL environment. Like there's verifiers, there's tasks, there's the C data you put in. Like there's so many more layers involved. I think it's just a more interesting and different problem, but yeah, it's not just the feature or just the code base as a whole.
</details>

>> 然后，呃，同样地，在数据集创建方面，你试图找到……你很容易把任务出得太难。你懂的。但如果你把它们出得太难，它们就成了评估，对吧？呃，如果你把它们出得太简单，它们就没用。所以你需要把它们出得恰到好处，只比模型今天能做到的多出几步。这样它们才是可训练的，而且是高效可训练的。这是一门科学，也是一门艺术。而且你得教大家，几乎就像玩扑克，不是一次只玩一局，你知道，在网上你可以同时玩四五局。你需要教大家，而我们正在培训世界上最优秀的工程师中的一部分人去做这件事，因为他们以前从未做过。嗯，这就是我们的重点，让资深工程师接受培训，去构建 RL 环境，是的。
<details><summary>Original English</summary>
>> And then u again, same thing with data set creation. you're trying to find like you can make tasks very easily too hard. You know this. But if you make them too hard, they become eval, right? Uh and if you make them too easy, they're they're worthless. So you need to make them just hard enough that they're a few steps away from what the model can do today. So they're trainable and efficiently trainable. That's a science and an art. And you have to teach people almost like playing instead of playing one poker game at a time, you know, online you can play four or five. you need to teach people and and we're training some of the best engineers in the world how to do this because they've never done it before. And um that that's been our focus is getting you know staff level engineers trained up to build RL environments and yeah
</details>

>> 面向未来一两年，也就是这个时间跨度。
<details><summary>Original English</summary>
>> for the next year or two which is the the horizon.
</details>

### 人才筛选、培训与长期留存

>> 我的意思是，你们正在发展一家庞大的企业。嗯，我想深入了解一下的是，你们面试时的最低准入门槛是什么，然后哪些东西是你们可以培训的？嗯，你们是怎么设置这套机制的？
<details><summary>Original English</summary>
>> I mean you're you're growing an enormous business. Um I think the what I do want to dig into is what do you interview for as like a minimum like entrance bar and then what do you what can you train? Um how do you how do you set that up?
</details>

>> 所以在 RL 环境这一侧，归根结底它仍然是软件开发，我们寻找的是对 agent 高度认同并深度使用（agentically pilled）的人。就是这样。
<details><summary>Original English</summary>
>> So on the RL environment side which is still software development at the end of the day we're looking for people who are agentically pilled. That's
</details>

>> 就像如果你没有这一点，你就没法构建得更快。
<details><summary>Original English</summary>
>> like if you if you don't have that you can't build faster.
</details>

>> 那怎么测试这一点呢？
<details><summary>Original English</summary>
>> And what's the test for that?
</details>

>> 这已经变了。嗯，我得去问问工程团队。现在我们正在构建很多……我们有 Orc.ai，这是我们的多 agent 编排平台。我们用它构建了自己的软件开发工厂，但它也为我们自主运行安全等很多不同的事情。所以，那是脚手架，但你仍然需要剩下的那 30% 来完成它。嗯，你知道，一开始是和某人坐在一起看他们写代码，但是用 agentic 的方式，你知道，就是那样，并且问他们相关的问题。嗯，我不知道今天是什么样了，因为 3 个月前的标准到今天已经过时了。嗯，我们做很多内推，对吧？我们想要从第一天起就已经达到那个速度的人。
<details><summary>Original English</summary>
>> It's changed. Um, I have to talk to the engineering team. Right now, we're building a lot of We have Orc Orc.ai, which is our uh multi- aent orchestration platform. You we've used it to build our own software development factory, but it runs security. It runs a lot of different things for us autonomously. So, like that's the scaffolding, but you still need that other 30% to finish it. Um, you know, at the beginning it was uh sitting with somebody and watching them code, but agentically, you know, like that that was the and like asking them about it. Um, I don't know what it is today cuz 3 months ago I'm already outdated on on what that looks like. Um, we do a lot of referrals, right? We want like people that are already at that speed from day one.
</details>

>> 内推是指如果有人把人推荐进你们的网络，你们会发奖金吗？
<details><summary>Original English</summary>
>> Referrals as in you you pay a bonus if someone refers people into your network.
</details>

>> 哦，是的。
<details><summary>Original English</summary>
>> Oh, yeah.
</details>

>> 好的。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 哦，是的，我只是……
<details><summary>Original English</summary>
>> Oh, yeah. I just
</details>

>> 多少钱？
<details><summary>Original English</summary>
>> How much?
</details>

>> 呃，[笑声] 200 到 500 美元不等，作为感谢。
<details><summary>Original English</summary>
>> Uh, [laughter] anywhere from 200 to 500 bucks as a thank you.
</details>

>> 不错，不错。
<details><summary>Original English</summary>
>> Nice. Nice.
</details>

>> 你知道，嗯，我们在数据方面也做同样的事情，因为我们购买原始数据并交给实验室。就像，实验室有太多需求了，你知道，而且，你知道，我看 50 年前有只服务 IBM 一家公司的供应商，对吧？所以，呃，我们也会和他们聊反模式，你知道，这是早期 RL 环境（RLE）工作时的做法——我们会聊在生产应用和 RL 环境之间有什么不同，然后让他们设计一个功能，在通话中与我们分享系统设计，如果他们在 30 分钟内没法开始理清其中的返工逻辑，那就不合适。所以我们会开始拆解类似这样的东西，当然还有速度。现在在另一侧，在数据创建方面，比如我们需要用来训练编程或……你知道，工作的原始任务——嗯，我们做大规模培训，最终结果是，如果你能创建一个达到我们质量标准的任务，你就能拿到报酬。
<details><summary>Original English</summary>
>> You know, um, we do the same thing for data cuz we buy raw data and it goes to the labs. like this is just a the labs have so many needs you know and and you know I look there's vendors you know 50 years ago that only served IBM it was just one company right so uh so we we we also talk about the antiatterns you know with them this was like early days RLE work um and we would talk about like what's different in a production app versus an RL environment and then get them to design a feature like share it the the systems design you know with us on a call and if they couldn't in 30 minutes kind of start to figure out the the rework there it wasn't a fit. So we we'd start to pick apart things like that speed you know obviously. Now on the other side on the data creation like the raw tasks that we need to train for coding or for you know work um you uh we do large trainings and and the the end result is if you can create a task that meets our bar of quality you get paid for it.
</details>

>> 如果做不到，你就没法通过。所以我们做了很多前置测试，测试他们思维过程的一部分，比如标注是什么样的、解题是什么样的，你知道，问题的构思，然后是迭代。但……归根结底是：你能做出来吗？这又回到了 10 年前，当时前端世界全都是算法题（algos），而我们说不，你能不能在前端做出点东西。所以我们只是回到了那个本质：你能执行交付吗？
<details><summary>Original English</summary>
>> If you can't you don't move through. So we've done a lot of upfront testing that that tests a piece of their their their thought process around like what does it look like to annotate, what does it look like to solve, you know, the ideation of the problem and then the the iteration. Um but uh at the end of the day it's like can you do it? So it we mapped around back to 10 years ago when the front end world was all you know alos and we were like no can you like do something on the front end. So this we're just going back and like can you execute?
</details>

>> 是的。看产品而不是刷 LeetCode，对吧？是的，是的。嗯，我觉得这很有意思。另外，大家能积累经验吗，你知道，嗯，这听起来可能会有点交易性质，就是“哦，你雇我做一份活，我进来，干一阵挺好玩的”。嗯，但在网络里会建立起某种长期关系吗？我们的很多工程师最终成为了全职的团队负责人（team leads），跨团队工作，我们工程团队到现在招到的几乎每一个人，是的，都来自过去一两年里的初始项目合作。
<details><summary>Original English</summary>
>> Yeah. Product not le code right. Yeah. Yeah. Um, I think that's interesting. Also, do do people build experience, you know, like um this can feel kind of transactional, you know, it's like, oh, you're you're engaging me for like a job and like I I'll come in and, you know, it's it's it's fun for a while. Um, but is there a sort of longunning relationship, you know, that is built up in the network? A lot of our engineers end up team leads full-time working across we almost everyone we've hired at this point from our engineering team. Yeah. Has come from um initial work in the last year or two.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 嗯，甚至我们的工程副总裁（VP of eng），你知道，我的意思是他们是通过内推来的，情况不同。他们进来时是工程经理（EMs），你知道，但他们是为了特定项目进来的，然后他们成长了起来，因为有一种饥渴感和恐惧感，你知道，因为我们都在以不同的方式被取代。所以……
<details><summary>Original English</summary>
>> Um even our VP of venge, you know, I mean they were referrals, it was different. They came in as ems, you know, but they were for specific projects and they have ramped up because there there's a hunger and a fear, you know, in that we're all being replaced in different ways. And so
</details>

>> 你在帮着取代我们。是的。
<details><summary>Original English</summary>
>> you're helping to replace us. Yeah,
</details>

>> 我们在帮着取代我们。
<details><summary>Original English</summary>
>> we're helping to replace us.
</details>

>> 我对此完全没意见。没问题，没问题。
<details><summary>Original English</summary>
>> I have no problem with it. No, no problem.
</details>

>> 这是不可避免的。
<details><summary>Original English</summary>
>> It's inevitable.
</details>

>> 我们会找到别的工作的。我们会找到的。是的。
<details><summary>Original English</summary>
>> We'll find other work. We'll find Yeah.
</details>

>> 但别的工作就像 Anthropic 正在做的那样，你知道，他们说：“哦，我们不再需要 GitHub 了，因为它对我们不好用。那我们重建一个吧。”所以就像复杂性，你知道，正在不断增加。因此有趣的地方在于，我们可以在更短的时间内做多得多的事，或者如果我们有更长的时间，它就会复杂得多，而且希望更有用，对吧？嗯，所以是的，他们留下来和我们一起成长，而且当你看到香肠是怎么做出来的（幕后过程），后训练（post-training）就开始变得不那么神秘了，是的，是的。嗯，非常酷。我也在试图弄清楚的另一件事是……买方那一端。他们来找你们时想要什么？嗯，有没有竞争性的招标流程（RFP process）？是那样运作的吗，还是他们会说：“看，这是一次试运行，如果你做得好，你就赢得了下一个真正大单的资格。”
<details><summary>Original English</summary>
>> But the other work is like what Anthropic's doing with like, you know, they're like, "Oh, we don't need GitHub anymore because it doesn't work for us. So, let's rebuild that." So, it's like the complexity, you know, is is uh is just increasing. And so, that's the fun is that we can do way more in a shorter amount of time or if we have a longer amount of time, it's way more complex and hopefully useful, right? Um so, yes, they are sticking with us. are growing and they're being when you see how the sausage is made you the post training starts to be a little bit like less uh mis yeah yeah um very cool I I think one of the things I'm also trying to figure out is the um the the buyer side of the equation what do they want when they come to you know um is there a competitive RFP process does it work like that or do they are they just like look this is a test run if you do well you earned a right for the the next really really big one.
</details>

### 实验室采购模式与市场格局

>> 所以，呃，没有竞争性的 RFP。它和企业级市场正好相反。让我先说一分钟企业级市场，这样你就能看出区别。
<details><summary>Original English</summary>
>> So uh there's no competitive RFP. It's the opposite of enterprise. Let me talk about enterprise for a second and then it gives you like a dis.
</details>

>> 所以企业级市场，如果你走进财富 100 强或财富 50 强，对吧？如果你运气好，采购流程大概也要 6 到 12 个月。其中很多家光是沟通就要 12 个月以上，对吧？所以这简直没完没了，这也是为什么“AI 转型”——我讨厌这个词，但他们就是这么叫的——实际上并没有发生。他们甚至来不及引入合适的供应商，对吧？他们并不总是知道自己想要什么，等等。他们也不总是有大预算。
<details><summary>Original English</summary>
>> So enterprise if you go into Fortune 100 or fortune 50, right? You are going to look at somewhere between 6 to 12 months on a procurement process if you are lucky. Many of them are 12 plus just talking to them, right? So it just takes forever which is why AI transformation I hate that word but that's what they call it is actually not happening. They can't even onboard the right vendors like in enough time, right? They don't always know what they want, etc. They don't always have the big budgets.
</details>

>> 实验室不同，只要你有他们想要的东西，他们的流程要短得多。所以，他们可能有几百万美元的预算分配，几乎就像“这里有点额外的，你知道……”
<details><summary>Original English</summary>
>> The labs are different in that if you have something they want, they have much shorter processes. So, they might have a few million dollars like of allocation almost like here's some extra, you know,
</details>

>> 零花钱。没错。但这就像一个试点，你知道。呃，甚至大实验室，你知道，行动也会非常快，你知道。嗯，他们习惯了非常大的交易。比如一个研究人员在 60 秒内就能花掉 1000 万美元，如果你来自非风投支持的企业级世界，这会让人震惊，但这每天都在发生。嗯，所以它发生得非常快。嗯，而且没有 RFP 流程。那他们今天想要什么？他们想要合作伙伴。你知道，一年半以前，他们想要的是体量和正确的差距（correct gap）。他们希望基准测试总体上往上涨，他们想要原始的正确性。现在则更多关乎行为（behavior）和品味（taste）。你看看 Opus，你知道，看看它相比其他一些模型有多么精致。如果你和那些实验室交谈，你会看到他们思维方式上的差异，而且他们总是在挑战自己的思维方式，对吧？嗯，他们想要差距分析（gap analysis），他们想要合作关系。而现实是，现在市面上有很多原始数据供应商，比如卖公司数据的人等等。但在一个 100 亿到 150 亿美元以上总潜在市场（TAM）中，真正处于顶尖水平、覆盖编程、知识工作等三个领域的供应商其实并没有那么多。因此，实验室会找特定的供应商做特定的事，因为那是他们的口碑框架，就像“我需要律师的时候就找这家”，对吧？嗯，而且如果你理发理得不错，你通常不会去别的地方。所以，除非你搞砸了，或者有人真的能长期把你比下去，否则你不会被替换。而且他们不只是通过价格把你比下去。他们是通过“这个更好”来替代你。他们愿意付费，高质量数据现在比节省 20% 的价格重要得多。
<details><summary>Original English</summary>
>> pocket change. Correct. But it's like a pilot, you know. Uh even the big labs, you know, will move very quickly, you know. um they're they're used to very large deals. Like a researcher in 60 seconds can spend $10 million and it's it's shocking if you come from like not the VC backed, you know, enterprise world, but it happens every day. Um so it happens very quickly. Um and there's no RFP process. And what do they want today? They want partners. You know, a year and a half ago, they wanted volume and they wanted correct gap. They wanted the the the the benchmarks to generally speaking go up and they wanted raw correctness. Now there's so much more about behavior and taste. You look at opus, you know, and and you know, look at how refined that is compared to some of the other models. And if you talk to those labs, you you'll you'll you'll see the difference in how they think and they're always challenging how they think, right? Um they want gap analysis, they want partnerships. And the reality is there's a there's a lot of raw data vendors right now, people selling like company data, etc. But there's actually not that many vendors out there in the market with a 10 to 15 plus billion dollar total accessible market um that are really at the top of their game for three domains, coding, knowledge work, and you know, and and so what happens is the labs go to certain providers for certain things because it's their frame. like this is who you go for for when I need lawyers, right? Um and uh if you get your haircut and it's good, you usually don't go anywhere else. So, it's you're not replaced until you screw up or someone really is able to undercut you over time. And they don't just undercut through price. They undercut through this is better. They will pay quality quality data is now way more important than an a 20% price savings.
</details>

>> 有没有匿名的，你知道，关于别人怎么搞砸的故事，比如……
<details><summary>Original English</summary>
>> any um anonymized, you know, stories about how people screw up, you know, like uh
</details>

>> 嗯，我的意思是……
<details><summary>Original English</summary>
>> well, I mean,
</details>

>> 能有多糟糕？
<details><summary>Original English</summary>
>> how bad does it get?
</details>

>> 我的意思是，看看所有的安全隐患，
<details><summary>Original English</summary>
>> I mean, look at all the the security concerns,
</details>

>> 好吧。
<details><summary>Original English</summary>
>> okay?
</details>

>> 你懂我的意思吧？非常容易搞砸，因为这个市场里，如果你一个项目有 500 个人，你在漏斗的某个环节仍然要面对 6000 个人。你知道，其中有多少人来自朝鲜？有多少次出现供应链问题？你的首席信息安全官（CISO）有多厉害？我的意思是看看外部发生的攻击，或者，你知道，某种训练材料或指令被泄露，或者你在某个项目上的人同时在另一个项目上为竞争对手工作，这类事情确实发生过，也被曝光过，但你知道吗——他们并不总是会彻底失去地位，
<details><summary>Original English</summary>
>> You know what I mean? If you it's very easy to screw up because this this this this market is you're dealing with still you're dealing if you have 500 people on a project, you're still dealing with 6000 people at some point in a funnel. You know, how many people are from North Korea? How many times are there supply chain issues? How good is your CISO? how good it I mean look at the attacks that have that have happened you know externally or you know uh you know some sort of training material or instructions that gets leaked or or you have people on one project working for a competitor you know on the other project like this sort of thing happens and it's been exposed but you know what the thing is um they don't always lose their status completely
</details>

>> 因为就像还能找谁替代他们呢？并没有多少……有几家，大概有两三家估值超过十亿美元的公司。
<details><summary>Original English</summary>
>> because it's like who else is there to replace them there's there's not a lot of there's a there's a few there's There's like two three companies that are over a billion dollars.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 其他所有公司都在十亿美元以下。
<details><summary>Original English</summary>
>> Everyone else is under a billion.
</details>

>> 是的。太棒了。呃，你怎么看待……关于整个市场，你还有什么观察？你知道，大家可能会说，“好吧，就五个客户，也许也就这样了”，你知道。嗯，这里存在 TAM 的问题吗？存在经常性收入（recurring revenue）的问题吗？嗯，还是现在下结论太早了？
<details><summary>Original English</summary>
>> Yeah. Awesome. Um do you uh what how do you think about what else would you observe about the market in general? You know, uh people would say things like, well, okay, there's five customers and like maybe that's it, you know. Um is there is there a TAM question? Is there like a recurring revenue question? Um or it's just too early to tell.
</details>

>> 我的意思是，正确的答案是现在下结论太早了，但我可以试着猜一下。
<details><summary>Original English</summary>
>> I mean, the right answer is it's too early to tell, but I'll take a stab.
</details>

>> 试着猜一下。呃，我的猜测是，一种思路认为接下来几年其实一切都会变得更贵，你们的增长空间是巨大的。另一种关于这些数据供应商增长的思路则认为，大家即使不需要也在囤积数据，对吧？呃，杰文斯悖论的那种因素——就像电力，我们曾经到达某个阶段，并没有真正渴望更多，直到显然这次 AI 热潮出现，但智能（intelligence）不是那样的，它非常……就是我们只想要更多、更多、更多。所以即使你在某个基准测试上拿到了正确率，总还有别的东西：更长的时间跨度（longer horizon）、更深层次，或者“我们如何殖民火星，模型如何解决那些问题”，而且它只会变得越来越具体、越来越昂贵。嗯，所以如果你看那些实验室，那里是有机会的。如果你和实验室的大多数研究人员交谈，就像去洛杉矶在街角随便问一个人“你的电影是关于什么的”，大多数人都能答上来，对吧？所以如果你问实验室的研究人员：“你在考虑做什么创业项目？”他们全都有创业点子。所以你会看到更多的新型实验室（Neolabs）。你会看到更多带有垂直化框架（verticalized harnesses）的初创公司，专门针对某个痛点。我们正在不断往杠杆食物链的更高处走。嗯，我对此很兴奋。企业级市场是一些较大的数据供应商或最大的数据供应商正在押注的领域。呃，每个人都将需要自己的智能，你知道，而且他们不一定有时间和金钱去全部内部自建。嗯，所以他们将需要帮助来购买数据、构建数据集，做每一个实验室都在做的整套事情，而且每家财富 500 强企业内部都会有一堆新型实验室。[笑声]
<details><summary>Original English</summary>
>> Take a stab. Uh the the stab is that uh you have one you have one thought process that actually everything's going to get more expensive uh over the next you know couple years and your ability to grow is massive. You have another kind of thought process around growth of these you know data vendors around well people are storing data even if they don't need it right uh the Jebans paradox you know kind of element that like electricity we came to points where you know we didn't really desire more until obviously this AI boom but intelligence is not like that it's very like it's just we just want more and more and more so how do you once even if you get the correctness on a certain benchmark there's always something it's longer horizon or deeper or you know how do we you know populate Mars and how does the model solve for stuff that's you know um and and but it just gets more specific you know and expensive um so if you look at the labs there's an opportunity there if you talk to most of the researchers at the labs it's like going to LA and asking anybody on the random on on a street corner what what's their uh what's their movie about you know and and most of them will answer right so if you if you talk to a researcher at the labs like what are you thinking about doing in your startup? They all have startup ideas. So you're going to see a lot more Neolabs. You're going to see a lot more startups with, you know, verticalized harnesses that are specific around some pain point. Like we are just continuing to get like higher up in the in the leverage, you know, kind of food chain. And um I'm excited for that. Enterprises is is the space that some of the bigger uh data vendors or the biggest data vendors are betting on. uh everyone's going to need their own intelligence, you know, and uh they're not going to want to they don't necessarily have the the time and the money to build it all in house. Um so they're going to need help buying data, building data sets, doing the whole thing that every single lab and you're going to have a bunch of neolabs inside of every Fortune 500. [laughter]
</details>

### 为什么实验室不自己做内部数据团队

>> 是的。你说过有一家拥有内部数据运营体系。这确实让我想到，到某个阶段如果他们花得够多，他们应该内部自建，对吧？比如他们有内部标准，显然和你打交道的每一家都有某种排他性条款，对吧？“你为我做的工作，我不希望你转身就……”
<details><summary>Original English</summary>
>> Yeah. You said there's one that has an uh in-house uh data operation. Um and it does make me think like at some point if they're spending enough, they should inhouse it, right? like they have internal standards like obviously everyone that you deal with has some kind of exclusivity clause right the work that you do for me you I don't want you to turn around
</details>

>> 不，其实并非如此。
<details><summary>Original English</summary>
>> no that's not actually true
</details>

>> 展开说说。
<details><summary>Original English</summary>
>> tell me more
</details>

>> 呃，他们中的一些实际上并不介意你把数据卖给别人，甚至预期你会这么做，因为如果你把现成数据卖给四家供应商，他们就能拿到降价。
<details><summary>Original English</summary>
>> uh some of them are uh actually okay with you selling the data to and expect it because they get a price decrease if you sell offtheshelf data to four vendors
</details>

>> 这意味着他们付得更少；如果你只卖给一家且是排他的，他们付得就多。
<details><summary>Original English</summary>
>> it means that they're paying less if you sell it to one and it's exclusive they're paying
</details>

>> 是的，但那样的话这就不再是我的竞争优势了。
<details><summary>Original English</summary>
>> yeah but then that's not my competitive advantage anymore
</details>

>> 但他们并不总是在意。
<details><summary>Original English</summary>
>> but they don't always care
</details>

>> 因为……是的，他们并不总是在意，因为当他们去找老板说“嘿，我有这么多预算，我能做这么多事”时，这事儿就这么过去了，对吧？竞争优势只来自最顶尖的那一两家。其他所有人，我不知道他们对此是什么感受。所以，现成数据几乎是一种主要的商业模式，大家心知肚明它会被打包并卖给任何地方。是的。
<details><summary>Original English</summary>
>> because Yes, they don't always care because like it's it's uh it's kind of like uh washed away when they go to their boss and say, "Hey, I got I have this much budget. I can do this much." Right? The competitive advantage only comes from the top one or two. Everybody else, I don't know how they're like feeling about that. So, off the shelf is a almost a primary way of doing business where it is known that it will is packaged and it can be sold anywhere. Yeah.
</details>

>> 所以我会说那是主要模式，而当你进入这种细分领域时，它才开始转变……
<details><summary>Original English</summary>
>> So that I'd say that's the the primary mode and it's starting to switch when you get to this, you know, niche kind of like
</details>

>> 是的。如果我是……听着，如果我是 Anthropic，我可不想让 OpenAI 从我让你为我做的事情中获益，对吧？这是非常简单的道理，但你会向我收更多钱。我懂了，对吧？是的，酷。是的，我的意思是，我确实认为这正变得越来越像知识产权（IP）。我确实觉得在某个时候他们会想内部自建，对吧？所以根本上难在哪里？为什么他们不应该自建内部数据团队？
<details><summary>Original English</summary>
>> Yeah. If I'm look, I'm I'm in topic. I don't want an open eye to benefit from what I asked you to do for me, right? Like that's a pretty simple straightforward thing, but you're going to charge me more. I get it, right? Like Yeah. Cool. Yeah. I mean, like I I I do think that is becoming more and more IP. I I do think like uh at some point they they would want to build it in-house, right? Like I think so basically what is hard? Why should they not build an in-house data?
</details>

>> 没有人完全内部自建过。我提到的那一家，是在供应商管理和基础设施方面比其他所有实验室都更成熟，有些实验室也在效仿，这不仅仅是因为流程，而是当你的 CEO 说“这是买数据的空白支票”，并且他们理解数据有多重要时，就会这样。相比之下，你看看另一家刚刚融资的实验室，我在一个公开场合和他们的人坐下来聊，他说：“是的，我们现在有一大笔钱，而 6 个月前还没有，这改变了一切。”所以，没有好的数据你就无法构建好模型，效率根本不在那儿。
<details><summary>Original English</summary>
>> No one's built it in-house. The one I mentioned was like the vendor management of it and the infrastructure of it is more mature than all the other labs and some are following not like as a just because it's it's the process and it comes from when your CEO is like here's a a blank check for data and they understand how important the data is. Whereas you look at another of the labs that just raised and I sat down with somebody, you know, in a public setting and he's like, "Yeah, um we have a ton of money now and 6 months ago we didn't and it's changing everything, you know." So like you you just can't build good models without the efficiency isn't there.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你知道，嗯，所以他们没有内部自建，他们不内部自建的原因是管理开销（overhead）。
<details><summary>Original English</summary>
>> You know, um so they don't have in-house and the reason they don't have in-house is because of uh overhead.
</details>

>> 我甚至会说，最重要的甚至不是财务开销。是杠杆效应（leverage）。是的，你人数处于劣势。想想看，如果他们知道最终客户是 X、Y 和 Z，而且他们直接为这些公司工作，你会收到多少诉讼，对吧？他们只是想……人们，尤其是有了 GPT，你可以因为任何事起诉任何人，你只要输入……
<details><summary>Original English</summary>
>> I would say more than anything, it's not even financial overhead. It's leverage. Yeah. like you are outnumbered. Think about how many lawsuits you would get if they knew the end customer was X, Y, and Z and they were working directly for them, right? They just want to People, especially with GPT, you can sue anybody for anything and you just type in what
</details>

>> 我收到过威胁信。哦，是的。那不是正式诉讼，但很耗费律师时间，而这就是你要面对的。是的。
<details><summary>Original English</summary>
>> I've been I've been uh sent threatening letters. Oh, yeah. It's not a lawsuit, but it costs lawyer time and that's what you're doing. Yeah.
</details>

>> 所以，如果你每个月要和 6000 人打交道呢？
<details><summary>Original English</summary>
>> So, what if you are dealing with 6,000 people a month?
</details>

>> 如果你要乘以 12 呢？如果你在两年内要乘以 100 呢？所以，他们自己的知识产权问题已经够多了，员工人数增长的问题也够多了。他们不想要这种管理开销和复杂性。核心就是复杂性。他们已经够复杂了。和所有这些个体打交道极其困难。现在，其中一些实验室尝试过保留小团队，但也仅此而已。然后发生的事情是，他们最终全都被裁掉了，因为别的事发生了，这在公关上并不好看，但那是 300 人，不是 3000 人。
<details><summary>Original English</summary>
>> What if you're dealing with that times 12? What if you're dealing with that times 100, you know, over two years? So, you know, they have enough issues with IP, enough issues with their headcount going up. They do not want the overhead and the complexity. It's the complexity. They have enough complexity. Dealing with all these individuals is extremely hard. Now, some of them have tried having smaller teams, but that's it. And then and then what happens is they eventually all get let go because you know something else happens and you know and it's not a great PR look but it's 300 people it's not 3,000 people.
</details>

### 后训练投入、数据定价与原始数据

>> 是的。嗯，我可能会在这里拉出一些图表来佐证这一点，但我真正感兴趣的一件事是，大家确实在后训练（post-training）上投入了多得多的资源，多得多得多。以前它只是很薄的一层。现在它非常厚。有时你在后训练上花的算力（flops）比预训练还要多。而这也需要多得多的数据，这就是你们介入的地方。我觉得有一种“人类数据的缩放定律（scaling law）”非常有意思，比如：好吧，你在算力上花了多少钱，其中多少比例是数据，如果你有更好的数据，你的算力效果会好多少？而答案似乎是，数据支出正从占总算力预算的 2% 到 3% 上升到 4% 到 6%。甚至可以说，我完全可以严肃地提出 50% 的观点——如果你有更好的数据，你就会浪费更少的算力。
<details><summary>Original English</summary>
>> Yeah. Um and so what you know I'll probably try to pull out some charts in here for substantiating this but one thing I'm really interested in is that really people are investing a lot more in post training like a lot a lot more. It used to be a thin layer. Now it's very thick. Sometimes you're spending more inference on uh spending more flops on post training than pre-training. And that also requires a lot more data which is where you come in. And I think it's very interesting to have a kind of like a scaling law of human data where like well yeah what are you spending on your compute spend okay well what percent of that is data and how much better would your compute be if you have better data. And I think like the answer seems to be that it's going from the data spend of like two to 3% of your overall compute budget to like four to six. And arguably you know I could make a case for 50 like straight up with a straight face. if you have better data, you're going to use you're going to waste less compute.
</details>

>> 但与此同时，昨晚我们在晚宴上我和一家实验室聊过，他们说：
<details><summary>Original English</summary>
>> And but at the same time, I talked to a lab last night at the dinner that we were at and they're like,
</details>

>> 归根结底，
<details><summary>Original English</summary>
>> at the end of the day,
</details>

>> 我们把算力闲置在那里就是在烧钱。
<details><summary>Original English</summary>
>> we have a we have we're burning compute by letting it sit there.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以我们需要在此时此刻拿到能拿到的最好的东西。好、更好、最好（Good, better, best）。而它并不总是“最好”，有时只是“好”。
<details><summary>Original English</summary>
>> So, we need to get the best that we could get in at this very moment. Good, better, best. And it's not always best. Sometimes it's good.
</details>

>> 我明白了。
<details><summary>Original English</summary>
>> I see.
</details>

>> 你知道，所以他们有这个时间限制需要去平衡。
<details><summary>Original English</summary>
>> You know, and so they have this time constraint piece that they're balancing.
</details>

>> 所以这就是为什么他们这么大幅度地扩充数据，因为他们反正有这些算力摆在这里，对吧？而且他们意识到自己快没数据了，而你们在为他们采购更多数据。我是说这很合理……
<details><summary>Original English</summary>
>> So, that's why they're ramping up data so much is because well, they have this comput sitting here anyway, right? and they need they realize they're running out of data and you're sourcing more data for them. I mean that makes
</details>

>> 而且要想把这件事做对，你没法一夜之间就造出来。我没法下周五就交付一千个长跨度数据（long horizon data）单元，除非你买现成的，但那样又没法直接针对他们的差距和具体需求。
<details><summary>Original English</summary>
>> and to do it right you can't just like create it overnight. I can't just deliver a thousand units of long horizon data like next Friday unless you have it off the shelf again which is where this come but that's not as directed towards their gaps and their specific needs.
</details>

>> 但你们是那样定价的吗？你说“单元（units）”，什么是数据单元？
<details><summary>Original English</summary>
>> But by but is that how you price it? You say units what what's data units of data um task
</details>

>> 归根结底是一个任务（task），但我的意思是也可以是标注（annotations），也就是，你知道……
<details><summary>Original English</summary>
>> a task at the end of the day but I mean could be annotations as well which is you know
</details>

>> 根据我在前沿代码上的工作经验，一个任务可能非常非常大——它会有变化，从难度等级到里面包含的上下文量，再到你在上面加的评分细则（rubrics）数量，有时一个任务我们有几百条评分细则，那算一个单元吗？如果我在我的任务上花了两周，而你在你的上花了一天，把我的东西也叫做一个单元会非常不公平。[笑声]
<details><summary>Original English</summary>
>> so from my experience working on frontier code a task can be very very big um it it varies right from like difficulty level to like amount of context that's in there versus um the amount of rubrics that you put onto it and sometimes we have hundreds of rubrics on one task and is that one unit it would be very unfair to call my thing one unit when I spent two weeks on it and you spent a day on your thing. [laughter]
</details>

>> 平均处理时间（Average handling time），AHT。
<details><summary>Original English</summary>
>> Average handling time. AHT. A
</details>

>> 就是这个词。是的。AHT 字面上就是你用来定价的方式。如果这件事要花你那些时薪 250 美元的资深软件工程师 10 个小时，那它很可能是一个长跨度任务。而且其中有很多迭代。你也不想直接把那些扔掉。所以当它发出去之后，可能 80% 到 90% 是“好的，这不错”，剩下 10% 是“我们想要这些迭代”。哦，然后它又退回来。所以这是一个持续的过程。这才是真正的合作关系，你知道，单纯把数据扔给供应商是很难行得通的。不过，
<details><summary>Original English</summary>
>> that's that's the name. That's Yeah. You AHT is kind of how you literally is how you price things. If this is taking your staff software engineers to get paid $250 an hour, you know, um 10 hours. I mean, it's going to be, you know, it's probably a long horizon task. And there's a lot of iteration. And you don't want to just throw that away either. So when it gets sent off, you might have 80 90% that yes, this is good. Here's 10%. We want these iterations. Oh, it goes back. So, it's this constant. It's a true partnership, you know, and it's harder to throw just throw data at vendors. However,
</details>

>> 我们正处于原始数据的零号地点（ground zero）。我喜欢听到有人说：“我做成了一笔百万美元的原始数据交易。”你知道，这就是你有公司数据的地方，比如一家有 50 年历史的化学工程公司，你有一家小型的美容公司，它有日历、Klaviyo（Clavio）之类的，而这正在成为 2026 年的主题，我想。
<details><summary>Original English</summary>
>> we're ground zero on the raw data. I love people saying, I got I I have made a million dollar raw data sale. And, you know, this is where you have companies data, you know, um chemical engineering, you know, firm that's 50 years old. you have a small, you know, beauty firm that has, you know, calendar and and Clavio and like, you know, all these, you know, and and and that's become the 2026 theme, I think.
</details>

>> 其实顺便问个题外话。我不知道这是否相关，但我就是想问一下。嗯，如果我有一家快倒闭的 YC 初创公司，我是不是应该干脆把我的数据卖了？
<details><summary>Original English</summary>
>> Actually, side question. I don't know if this is relevant, but I'm just going to ask it. Um, if I have a YC startup that is dying, should I just like sell my data?
</details>

>> 我的意思是，大概取决于规模有多大，比如如果你……
<details><summary>Original English</summary>
>> I mean, probably depends on how how big like if you're
</details>

>> 我把我的 Slack、我的邮件都给你。
<details><summary>Original English</summary>
>> I give you my Slack, my emails.
</details>

>> 是的，你应该卖。但员工人数和规模需要足够大，才有吸引力，因为……
<details><summary>Original English</summary>
>> Yes, you should. But the headcount needs to and the the size needs to be enough for it to be attractive because
</details>

>> 所以，对，多大规模？
<details><summary>Original English</summary>
>> so yeah what what size
</details>

>> 三个月前几乎什么都行，四个月前什么都可以，现在你至少需要几个 TB 的数据，你需要超过 10 个员工，你需要……有趣的地方在于，computer use 失败的时候，往往发生在处理数据的时候——比如假设有 Gabriel Tivera 和 Gabriel Tivera，两个名字在 Slack、邮件、HubSpot 上略有不同，到第三个环境时，它就会把这两个搞混，把事情搞砸。所以如果你在 GitHub、Linear 还有别的地方都有数据，对吧？而且你们在讨论同一个项目。那非常有价值。这就是他们想要的。他们想看到跨多个系统的连贯性。是的。
<details><summary>Original English</summary>
>> three months ago it was like anything four months ago anything would go now you need at least a few terabytes of data you want more than 10 headcount you want the the the interesting thing is where computer use fails is is when you're dealing with you know data or like let's let's say let's say like uh Gabriel Tivera and Gabriel Tivera two names across Slack email HubSpot and this that are slightly the by the third, you know, um, environment, it's confusing these two and screwing things up. So, if you have if you have data across GitHub, linear, and, you know, somewhere else, right? And you're talking about the same project. That's super valuable. That's what they want. They want to see cohesiveness across multiple things. Yeah.
</details>

>> 对。他们想看……我在所有地方都用同一个邮箱还不够吗？
<details><summary>Original English</summary>
>> Right. And they want to see like, isn't it enough I use the same email across all of them?
</details>

>> 也许需要更多。
<details><summary>Original English</summary>
>> Maybe more.
</details>

>> 但如果你有 50 个人，那比 3 个人要好。
<details><summary>Original English</summary>
>> But if you have 50 people, it's better than three.
</details>

>> 等等，你给了我一个新的创业点子，或者说是一个非常不可接受的[笑声]做法：我应该录下我所有员工的屏幕，然后保存下来作为数据卖掉，对吧？我的意思是那就能解决 computer use 了。
<details><summary>Original English</summary>
>> Wait, wait. you give me a new idea for for a startup or or like a very um unacceptable [laughter] practice, I should record all the screens of my employees and then save that and sell that as data, right? But I mean that will solve computer use.
</details>

>> 听着，我的意思是，我不知道，因为[笑声]那只是我们谈论的一个层面，这里面有太多层面了。
<details><summary>Original English</summary>
>> Look, I mean like there's I don't know because [laughter] that's just one level we're talking there's so many levels here.
</details>

>> 我一直在……我正树立起一个非常恶劣老板的名声，因为我什么都敢干，但我会说：“听着，这是为了科学。”
<details><summary>Original English</summary>
>> I I have been I'm building a reputation as a very toxic boss cuz I'll just like do whatever and but I'm like look it's for science.
</details>

>> 是为了科学。[笑声]这是万金油借口。有些初创公司已经开始研究如何每天从你自己的公司里生成数据，并用它来训练——既是为你自己的智能（intelligence），也是为了卖掉它。是的。各种各样的方式都有。computer use 表面上看起来简单，但当你以 PB（petabytes）级的数据来思考它，当你思考这些 RL 环境的所有表面积时，它就开始变得非常复杂。嗯，这很有趣，甚至让人麻木，你知道，而且即使是最好的模型也开始变得更好，但它们仍然很慢。
<details><summary>Original English</summary>
>> It's [laughter] for science. That's the that's the excuse for everything. There are some there are some startups that are starting to figure out how to create data like like uh on a daily basis out of your own you know company and use that to train company for well yeah for and for your own intelligence as well or to sell it. Yeah. There's there's all kinds of computer use is simple on the on the nose, but it starts to get really complex when you're when you're thinking about this in the pabytes of data and you're thinking about all of the surface area of these RL environments. Um yeah, it's fun like mind-numbingly, you know, and like even the best uh even the best, you know, models are starting to get better, but they're still slow.
</details>

### 明年上半年展望与行业预测

>> 是的，是的，是的。我们会大幅提速的。嗯，我们很快得收尾了。呃，但我本来想请你做个预测，也许是明年上半年，如果你没法预测得更远的话。嗯，你知道，在你提到的所有这些领域里——computer use、通用编程任务，还有比方说金融、科学等等——哪些会是热门领域？
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah. We're going to speed up a lot. Um so we got to wrap soon. Uh but I was just going to make for ask you for predictions for maybe the first half of next year if you can't project out more than that. Um you know out of all these domains you mentioned computer use just general coding task let's say finance and like sciences and what what have you what are going to be like the hot areas
</details>

>> 呃，进入明年吗？嗯，我的意思是，机器人（robotics），你知道，3D 模型，呃，3D，你知道……我的意思是，你开始看到，好吧，在这个领域的早期，3 年前，你可以签一份 3 个月或 6 个月的合同，做其中的一些工作。嗯，现在如果你谈论 6 个月，大家会笑话你，对吧？因为时间跨度不同了。机器人、3D 世界模型（3D World models），今天你还可以签 6 个月的合同。呃，所以那里有很多增长空间。嗯，我的意思是，我仍然认为在法律和金融方面有很多空间。嗯，在 computer use 方面仍然有巨大的增长空间。嗯，然后我认为总体上的一个薄弱领域——3D、任何 CAD……
<details><summary>Original English</summary>
>> uh heading into next year? Well, I mean, robotics, you know, the 3D models, uh, the 3D, you know, um, I mean, that's you're starting to see like, all right, early in this space, 3 years ago, you could sign a three or six month contract, you know, for some of this work. Um, now it's like people will laugh at you if you talk about like 6 months, right? Cuz the time horizons are different. Robotics, 3D World models, you can sign a six-month contract today. Uh so there's there's there's lots of room there to grow. Um I mean I still think there's lots of room you know in the legal and finance side. Um there's still a ton of room to grow in computer use. Um and then I think an area of weakness overall um 3D anything CAD
</details>

>> 呃，机械工程，比如引擎，任何不是软件工程的工程类活动……
<details><summary>Original English</summary>
>> uh mechanical engineering like the next engine anything any engineering type activities are not software engineering
</details>

>> 你知道，将会开始巩固起来，你会开始看到人们建房子以及做各种那样的事情。
<details><summary>Original English</summary>
>> you know is going to start to just uh solidify and you're going to start to see you know people building houses and doing all that kind of thing.
</details>

>> 是的。建筑设计之类的，但也有 CAD，以及比方说机械工程，就是很多齿轮协同工作的那种。
<details><summary>Original English</summary>
>> Yeah. Architect thing but also CAD and um let's say sort of mechanical engineering as a lot of gears working together.
</details>

>> 芯片，芯片设计，你知道，这是一个巨大的领域，而且……
<details><summary>Original English</summary>
>> Chips, chip design, you know, there's there's just a massive area, you know, and and
</details>

>> 我觉得芯片更像是一种可形式化验证（formally verifiable）的东西，有专门的像 Verilog（very log）那样的语言用于这类事情。是的，但还有更广泛的，比如模拟芯片（analog chips），也在蓬勃发展。我在那个领域有一笔投资。
<details><summary>Original English</summary>
>> I feel like chips, chips is a more of a like a formally verifiable thing that there's [clears throat] like specialized like very log languages for those kinds of things. Yeah. But there's broader like analog chips, you know, are also booming as well. I have an investment in that area.
</details>

>> 嗯，是的。好吧，很多领域……
<details><summary>Original English</summary>
>> Um, yeah. Okay. Well, lots of areas
</details>

>> 而且我想我们将开始看到对当前架构的一些挑战。我目前正在看一笔投资——我们有一家控股公司（holdco）——所以我们正在看一笔对一位研究人员的投资，他正在挑战推理（inference）的现状，你知道，模型是如何工作的，我们如何能把推理成本削减 50%，而数据损失只有大约 1% 之类的。我想我们明年会看到这些。它们能行得通吗？你知道，我们已经看到有人在挑战它了。呃，但我认为会有更公开的挑战。
<details><summary>Original English</summary>
>> and and I think we're going to I think we're going to start to see some challenges on the current architecture. I'm I'm currently looking at an investment, you know, we have a a u a hold co. So, we're currently looking at an investment with a with a researcher uh who is uh yeah, challenging the status quo on um inference, you know, how the models work, you know, how can we cut inference by 50%. You know, and only have like a data loss of like 1%. That sort of thing. We're going to see that, I think, next year. Will they work? You know, we've seen people challenge it already. Uh that'll but I think there will there will be more overt challenges.
</details>

### 结语与 Orc.AI 介绍

>> 是的，是的。好吧，很多令人兴奋的事情。感谢你构建未来。也感谢你帮助建设 AIE。嗯，我想我们下一个合作的项目是 AI Miami。
<details><summary>Original English</summary>
>> Yeah. Yeah. Okay. Well, lots of exciting stuff. Thank you for building the future. Thank you for helping to build AIE as well. Um I think the next one we'll be working together on is AI Miami.
</details>

>> 是的，是的。四月。
<details><summary>Original English</summary>
>> Yeah. Yeah. April.
</details>

>> 四月。嗯，大家可以期待一下。也请给我们一个行动号召（call to action），比如如果有人想作为专家加入你们，或者有人想付钱向你们买数据，他们该怎么做？
<details><summary>Original English</summary>
>> April. Um so people look forward to that. And also give us a call to action like uh if people want to join you on the expert side, if people want to pay you money for for data, how do how can they do that?
</details>

>> G2I.ai。
<details><summary>Original English</summary>
>> G2I.ai.
</details>

>> 就这个。
<details><summary>Original English</summary>
>> That's it.
</details>

>> 就是那个地方。如果你想了解一下，我们有一个用于编程的多 agent 编排平台，有点像是面向企业、军方、政府的，叫 ORC，或者说编排器 Orc.AI，
<details><summary>Original English</summary>
>> That's the spot. If you want to check out, we have a an a multi- aent orchestration platform for coding that's kind of like, you know, for enterprise, for military, government, uh, ORC, or orchestrator Orc.AI,
</details>

>> 你们自己也在用。这就是为什么你们效率这么高，能为大家构建高质量的环境……
<details><summary>Original English</summary>
>> which you use yourself. That's how you're so productive and building like high quality environments for people
</details>

>> 以及我们自己的数据基础设施。我们构建……
<details><summary>Original English</summary>
>> and our own infrastructure for data. We build
</details>

>> 我注意到你不把它叫做“软件工厂”。
<details><summary>Original English</summary>
>> I notice you don't you don't call it a software factory.
</details>

>> 不，因为它是一个操作系统（operating system）。就像，它字面上就是……
<details><summary>Original English</summary>
>> No, because it's an operating system. Like, it's literally
</details>

>> 哦，拜托，每个人都说自己是操作系统。
<details><summary>Original English</summary>
>> Oh, come on. Everyone says an operating system.
</details>

>> 不，但是[笑声]好吧，每个人都这么说。呃，我们会看看谁真能做到。你懂我的意思吧？
<details><summary>Original English</summary>
>> No, but like [laughter] Okay, everyone says it. Uh I we'll we'll see who actually can do it. You know what I mean? Like
</details>

>> 其中有一些是真的……
<details><summary>Original English</summary>
>> some of it's actually
</details>

>> 其中有一些是真的，而且你知道，Theo 把创建它的几位工程师介绍给了我，我从未见过这样的东西。我真的从未见过。但有趣的是，我们并没有只用它来做这一件事。软件工厂是第一号用例。我们有公司开始用它来解决安全问题。军方也想用它来做类似的事情。嗯，还有石油和天然气行业在和我们谈，关于各种各样的事情。你只是需要一种更好的方式来处理多个模型。它不仅仅是一个路由器（router），你知道，是在企业级层面上。嗯，并且为他们提供 SDK。它用 Rust 构建。它可以托管在任何地方。嗯，是的，我想它是一个不同的侧重点，而不仅仅是可组合的组件。它更像是……嘿，它让我想起 React。它更像是一个有主见的框架（opinionated framework），规定了如何做多人协作（multiplayer）、对抗性治理（adversarial governance）、agent 间通信（inter agent comms）。那就是我们负责的部分。其他一切基本上你在自己的环境里想怎么做就怎么做。
<details><summary>Original English</summary>
>> some of it's real and uh you know Theo referred me to a few of the engineers that created it and uh it's I've never seen anything like it. I've really never seen it. And but the fun thing is that we're not using it. Software factory is use case number one. We have uh companies are starting to use it for security issues. Uh the the military wants to use it for things like that. Um, you have like oil and gas industry that's talking to us about, you know, a myriad of different things. You're just, you just need a a better way to deal with multiple models. It's more than a router, you know, um, at an an enterprise level. Um, and having an SDK for them. It's built in Rust. It's hostable anywhere. Um, yeah, it's a it's a different, I guess, uh, it's it's a different focus rather than just composable pieces. It's like, hey, it's more it reminds me of React. It's more of an opinionated framework on how to do um multiplayer, you know, uh you know, uh adversarial governance, you know, inter agent comms. Like that's the part that we're taking care of. Everything else is kind of you you do what you want to do in your environment.
</details>

>> 太棒了。嗯，大家敬请期待，我相信我们还会聊更多。
<details><summary>Original English</summary>
>> Awesome. Um everyone look forward to it and we I'm sure we'll talk more.
</details>

>> 是的，谢谢。
<details><summary>Original English</summary>
>> Yeah. Thanks.
</details>

>> 感谢来做客。Arus。
<details><summary>Original English</summary>
>> Thanks for coming on. Arus.
</details>