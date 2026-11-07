---
author: All-In Podcast
date: '2026-10-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2Zj6uMv3kTA
speaker: All-In Podcast
tags:
  - product-design
  - software-development
  - generative-ai
  - creator-economy
  - antitrust-regulation
title: 对话Figma创始人Dylan Field：设计即新代码，AI时代的创造力与SaaS未来
summary: Figma创始人兼CEO Dylan Field在All-In访谈中深入探讨了AI时代的软件演进。他提出"设计即新代码"，回顾了Adobe 200亿美元收购案遭反垄断叫停后的组织重建、Claude Design带来的市场冲击与SaaS末日论，并深刻剖析了模型进展与专业产品体验的鸿沟，阐述人类在非验证性创造领域不可替代的核心价值。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Dylan Field
companies_orgs:
  - Figma
  - Adobe
  - Anthropic
  - OpenAI
products_models:
  - Figma
  - Photoshop
  - Claude
  - Cursor
media_books: []
status: evergreen
---
### 纳帕对饮与大会前瞻

**主持人**: **Dylan Field**，欢迎来到 **All-In** 访谈。

<details>
<summary>Original English</summary>

**Host**: Dylan Field, welcome to the All-In Interview.

</details>

**Dylan Field**: 谢谢，非常感谢你们邀请我来。

<details>
<summary>Original English</summary>

**Dylan Field**: Thank you. Thanks for having me.

</details>

**主持人**: 我们现在正身处加州美丽的纳帕谷扬特维尔（Yountville）。

<details>
<summary>Original English</summary>

**Host**: We are here in beautiful Napa, Yanville, California.

</details>

**Dylan Field**: 是啊，你已经喝了三杯了。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah, you're three drinks in.

</details>

**主持人**: 我们已经喝了几杯酒，然后就决定直接开机录制。

<details>
<summary>Original English</summary>

**Host**: We're a couple drinks in and we decided to go on camera.

</details>

**Dylan Field**: 挺好啊，为什么不呢？

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah, why not?

</details>

**主持人**: 为什么不呢？话说回来，你这次来这边是参加什么活动？

<details>
<summary>Original English</summary>

**Host**: Why not? Well, what are you doing here?

</details>

**Dylan Field**: 我是来参加一个活动，你明天也会出席。

<details>
<summary>Original English</summary>

**Dylan Field**: I was uh for this event that you're going to be at tomorrow as well.

</details>

### 设计即新代码

**Dylan Field**: 我明天有个活动，同一个活动。我们主要在聊设计和产品开发。我还顺带夹带了一点关于安全的内容，觉得聊聊挺好的。但总体而言，主要探讨的是产品开发正在如何演变。我的核心观点——也是大家预料我会说的——就是**设计即新代码**（Design is the new code）。

现在正在发生的情况是，随着代码生成模型变得越来越强，我并不是说我们不再需要工程师了。在 **Figma**，我们绝对非常需要工程师，我们热爱我们的工程师团队。但是，编程的本质正在发生改变。随着这种改变，**产品差异化的价值正在不断向最顶层迁移**，对吧？那就是设计、品牌、市场营销的独特视角，是敢于大胆突破，以及你所能激发出的情感共鸣。

我认为很多人忽视了这一点。我们也深入聊了很多关于 AI 的话题。

<details>
<summary>Original English</summary>

**Dylan Field**: I'm at an event tomorrow. uh same event and we were basically talking about design, product development. Uh I stuck in a little bit of security. Thought that'd be nice. Uh but overall a lot about just like how product development is evolving. And my point of view, the thing you'd expect me to say too is that design is the new code. Uh and what's happening right now is as coding models get better, I'm not saying that you don't need engineers. We definitely need engineers at Figma. We love our engineers. But also the nature of programming is changing and as it changes the value is rising in terms of differentiation to the top, right? That's design, that's brand, it's marketing point of view. It's being bold. Uh and it's like the emotional reaction you're able to elicit. Uh and I think that a lot of people are missing that. We also talked a lot about like AI and just kind of like

</details>

**主持人**: 好的，所以你今天在台上做了分享，是和 **Nikesh**（Palo Alto Networks CEO Nikesh Arora）对谈的。

<details>
<summary>Original English</summary>

**Host**: Okay, so you did a thing on stage today. You talk with Nikesh.

</details>

**Dylan Field**: 是的。抱歉，我刚才像是在直接复述白天的采访内容了。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. Sorry, I'm just recapping an interview here.

</details>

### Figma创立与设计本质

**主持人**: 哈哈，没事，挺好的！我们可以稍后展开聊，但我想先退一步。你是已经上市的 **Figma** 的 CEO。或许你可以先给观众做一个简短的电梯演讲：Figma 到底是什么？你最初是什么时候创立这家公司的？

<details>
<summary>Original English</summary>

**Host**: Yeah. No, it's great. Like, it's good. Like, we can fast forward, but I want to back up. You're the CEO of Figma, publicly traded. Maybe you can just give the quick elevator pitch on Figma. And when did you start the business?

</details>

**Dylan Field**: 好的，我们是在 **2012 年 8 月**创办 Figma 的。一句话概括：我们希望让全球最顶尖的团队能够在这里设计、创造并构建出世界上最好的软件。

同时，我们也被广泛应用于各种各样的视觉场景：营销、广告策划、幻灯片制作、白板协作、图表绘制等等，应有尽有。可以说，凡是需要视觉化表达的内容，即使产品初衷并非专门为此设计，也总有人在用 Figma 来完成。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah, we started Figma back in August 2012. And the quick pitch is this is where we want to make it so that the best best teams in the world can design and create and build the world's best software. Uh we're also used for all sorts of stuff. So, marketing, uh, advertising, slides, whiteboarding, diagramming, uh, you know, you name it. Like, if it's visual at all, someone's probably doing in Figma, even if it's not meant for that.

</details>

**主持人**: 人们通常称它为一款“设计软件”。这是一个准确的定性吗？还是说它并没有完全涵盖这项服务的全部光谱？

<details>
<summary>Original English</summary>

**Host**: People call it a design software. Is that a fair characterization or does it not capture the full spectrum of what the service is?

</details>

**Dylan Field**: 不，我认为**设计**确实是我们最核心的立足点与基石。当我在进行产品评审并与团队交流时，我们讨论的始终是设计师群体，讨论他们的核心诉求。

但“设计”这个词非常有意思，因为关于它有一百种不同的定义，对吧？我常常思考其中一个定义：**设计也许就是创造力与问题解决的结合**（creativity meets problem solving）。当然你还能找到无数种解释。此外，设计可以涵盖从室内设计、工业设计到产品设计、品牌设计等各个维度。所以当人们提到设计时，脑海中浮现的东西是非常丰富的。

<details>
<summary>Original English</summary>

**Dylan Field**: No, I I think that design is really our center and our core. Uh, and like when I'm in a product review and talking with the team, we talk about designers, we talk about what they want. Uh, design is also a term that's like so interesting because there's like a 100 definitions of design, right? I I think about a lot of a lot about the definition of like it's uh maybe creativity meets problem solving. Um, but there's like so many others you can find. And then also design can refer to everything from interior to industrial to product design to brand design and so on. And so people think about a lot of things when they think about design.

</details>

### 早期图形设计与Photoshop回忆

**主持人**: 我们梳理一下公司的发展历程：你在 2012 年创办了这家公司，拿到了风险投资，业务开始腾飞。你们向大型企业销售软件，业务规模极其亮眼。然后，**Adobe** 提出了以 **200 亿美元**收购公司的要约。

<details>
<summary>Original English</summary>

**Host**: Just to get caught up on the history of the business. So you started in 2012. You raised some venture money. The business takes off. You're selling enterprise software. You're doing really well and then Adobe offers to buy the business for $20 billion.

</details>

**Dylan Field**: 嗯，没错，你这快进跳跃得可真够快的。

<details>
<summary>Original English</summary>

**Dylan Field**: Uh yeah, correct. Quite the fast forward.

</details>

**主持人**: 那是哪一年来着？

<details>
<summary>Original English</summary>

**Host**: What year was that?

</details>

**Dylan Field**: 那是几年前的事了。你直接把我们从零打磨业务的那段艰辛创业史全都略过了。

<details>
<summary>Original English</summary>

**Dylan Field**: Uh it was a few years back now. I'm skipping through literally building the business like

</details>

**主持人**: 哈哈，你已经苦干了差不多十年、十一年了。

<details>
<summary>Original English</summary>

**Host**: yeah you're like uh you know 10 11 years in

</details>

**Dylan Field**: 不过话说回来，我们一直非常敬佩 Adobe，至今依然如此。那是一家不可思议的时代级公司，从早期的桌面印刷革命，到将 **Photoshop** 打造成行业标准，可以说是开创了整个平面与图形设计的浪潮。

<details>
<summary>Original English</summary>

**Dylan Field**: but the um no I mean we uh have always respected Adobe still do and the generational incredible company that like started everything from printing to making Photoshop what it is and like the entire graphic design revolution.

</details>

**主持人**: 顺便说一句，我从 **1990 年**就开始用 Adobe Photoshop 了。我当年在图层功能出来之前就做平面设计了——咱俩以前从没聊过图层出现之前的时代吧？是的，我还是个小孩子的时候就在电脑上做无图层设计，当时我还把它当成一项服务，给社区街坊和小商户接单赚钱呢。

<details>
<summary>Original English</summary>

**Host**: By the way I was on Adobe Photoshop since 1990. I did graphic design layers actually you and I haven't talked pre layers. Yes. So, I did graphic design pre- layers as a kid on computers and I did it as like a service for like people in the neighborhood and small businesses and stuff.

</details>

**Dylan Field**: 太酷了！你当时是怎么接触到它的？

<details>
<summary>Original English</summary>

**Dylan Field**: So, cool. How did you get access to it?

</details>

**主持人**: 我当时在学校里接触到的，后来我自己有了 **Macintosh**。我买的是 1984 年原版的首代 Mac，我一直对图形设计极其着迷。这完全是我发自内心热爱的业余爱好。我们以前真的没聊过这个。后来我还用了 **Bryce 3D** 以及那些早期的三维工具。然后当 **Kai's Power Tools** 问世的时候……

<details>
<summary>Original English</summary>

**Host**: I was like I at my school and then I had well I was on a Macintosh. I got the first Mac original 1984 and um I was always fascinated with graphic design. It was like something I love doing as a literally a hobby. you and I actually never talked about this and then I used like Bryce 3D and all these early 3D tools and then when Kai's power tools came out

</details>

**Dylan Field**: **Kai's Power Tools** 确实酷毙了。

<details>
<summary>Original English</summary>

**Dylan Field**: Kai's power tools is really cool.

</details>

**主持人**: 它彻底重塑了 Adobe Photoshop！对我来说，那就像是对创作潜能和 Photoshop 功能边界的一次不可思议的爆发式拓展。所以我从最初期就是 Photoshop 的超级铁粉，把它当做个人爱好，小时候还靠做平面设计赚零花钱。

<details>
<summary>Original English</summary>

**Host**: It reinvented Adobe Photoshop and for me it was like this incredible like expansion of creative potential and what you could do with Photoshop. So I've been a big Photoshop fan since the earliest days and a big user as a personal hobby and like I made money on the side doing graphic design and stuff as a kid.

</details>

**Dylan Field**: 确实如此。Photoshop 当然是一款非常成熟、甚至可以说成熟过头的产品，多年来它被塞进了太多繁杂的功能组件。我认为这也是很多大型软件的宿命：如果你不格外克制，软件随着时间推移必然会变得越来越臃肿。但用它确实能创造出令人惊叹的东西，而且 Adobe 作为一家公司历来极具创新精神，所以我从小就对他们抱有深深的敬意。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. Yeah. I mean, Photoshop of course is like a product that is very mature and maybe beyond mature too in that it has so many different parts of it that have been added over the years. Uh which I think is the nature of a lot of software. Uh it gets more bloated over time if you're not careful. But there's just so much that's possible with it and uh you know Adobe as a company has been very inventive. So I've always had respect since I was a kid too.

</details>

### Adobe并购案与反垄断波折

**Dylan Field**: 完全是这样。而且在当时看来，那个时机也很契合：我们有足够的体量能够加入他们，而不至于被全盘吞没。如果我们在规模很小的时候加入，我觉得很可能会被彻底稀释瓦解。所以当时我们签署了协议，我们同意了收购。

然而，世界多国的监管机构决定叫停这笔交易，对吧？

<details>
<summary>Original English</summary>

**Dylan Field**: Totally. And it felt like it was a time when, you know, we could join and not be totally absorbed. Uh if we were smaller, I felt like maybe we would just kind of dissipate. And yeah, we we signed the agreement. We said yes. And then uh various world governments decided that they didn't like it, right?

</details>

**主持人**: 反垄断机构介入并阻止了这笔交易。

<details>
<summary>Original English</summary>

**Host**: Like antitrust got involved and they blocked the deal.

</details>

**Dylan Field**: 是的。“反垄断”是一个比较宽泛的统称，但实际介入的有**美国司法部**、**欧盟委员会**以及英国竞争与市场管理局（**CMA**）。那是一套完全不同的监管氛围。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. Yeah, I mean it's it antitrust is kind of like a broad way to refer to it, but you have the United States, European Union, CMA and you know it's very different vibe and a couple years

</details>

**主持人**: 监管机构认定 Adobe 是想借此干掉一个强大的竞争对手。

<details>
<summary>Original English</summary>

**Host**: ago Adobe would be taking out a big competitor.

</details>

**Dylan Field**: 他们找了很多由头。但对我们团队来说，最关键的是**我们从没有松开过油门**。坦白说，刚签协议时，我还以为审核能顺顺当当地通过。但过了一两个月之后，情况就很明朗了——绝不可能那么轻松。

当时全公司必须达成一个共识：行，作为一家独立组织，我们必须全力以赴顶住压力，继续向前冲刺，持续研发并交付下一代产品。因为如果我们不顶住、不把油门踩到底，谁知道对岸等待我们的是什么？我们无法预知结果，必须确保无论发生什么，公司都能安然无恙、蓬勃发展。

<details>
<summary>Original English</summary>

**Dylan Field**: They said a lot of things but the I think most important part for us was that we just kept putting our foot in the gas. I mean, yeah, I thought it would be like sort of we would just go right through and as soon as a month or two in, it was clear that was not the case. It kind of became, okay, like we got to like really power through as an organization here and ship and build like the next stuff because if we don't power through and keep our foot on the gas, you know, what's on the other side? We don't know what's on the other side. Uh, we got to make sure everything's fine no matter what.

</details>

**主持人**: 那是在 2023 年。你们当时大概有多少员工？

<details>
<summary>Original English</summary>

**Host**: So, this is 2023. How many employees did you have? Uh

</details>

**Dylan Field**: 我记得大概是 1100 到 1200 人左右，具体数字我还得去核对一下。

<details>
<summary>Original English</summary>

**Dylan Field**: I want to say it was about 1100, 1200. I have to double check.

</details>

**主持人**: 好的。当我听到这件事情的来龙去脉时，我感到无比震撼。我记得在 2024 年 3 月见过你，不知道你是否还记得我跟你聊过这个话题：对于一家初创公司的上千名员工来说，原本面临的是商业史上最耀眼的退出机会之一——**200 亿美元**的被收购退出，结果这一切突然泡汤了。

当你必须站到全体员工面前，开全员大会（All Hands）并告诉大家：“伙计们，这笔交易彻底黄了。”那场大会的氛围是怎样的？对于那些原本满怀期待、突然觉得脚下地毯被抽走的人，你又是如何重新凝聚人心、带领大家把注意力拉回到独立做大业务上的？

<details>
<summary>Original English</summary>

**Host**: Okay. So when I heard this story, I was fascinated by and I think I saw you in 2024, March of 24. I don't know if you remember I mentioned this to you, but for me the story of telling,00 employees of a startup, we have one of the most incredible exits in history, $20 billion exit of this company and it's not going to happen. What was the all hands like when you get in front of everyone and you tell everyone, "Guys, this isn't going to happen." And how do you get everyone to realign on building a business and continuing forward when it feels like the floor for some people may have felt like the floor fell out from under them?

</details>

**Dylan Field**: 嗯，我觉得你首先得意识到**监管审查周期的漫长与折磨**，这种机制真的必须改革。因为如果你身处一个真正反竞争的环境中——顺便说一句，我至今依然坚信 Adobe 的收购并不构成反竞争。互联网上很多人当时可能认为它构成垄断，但我认为监管机构的论据非常苍白，他们是在打过去的战争，完全没有着眼于未来以及这个行业即将演变的方向。

我说这些并不是因为我对保持独立感到不满；相反，能作为独立公司运营 Figma，我也超级兴奋！即便在原计划被 Adobe 收购后，我的规划也是继续独立执掌 Figma。无论哪种结局，能掌舵 Figma 我都很开心。而在独立状态下，我们的迭代速度确实极快，我对此心怀感恩。

但回到你的问题：**我们承受了长达 16 个月的监管审查**。对于任何一家企业来说，长达 16 个月的持续审查都是极其折磨人的惩罚。如果在真正的反竞争场景下，这种拖延对交易双方中的任何一方都可能产生毁灭性的打击，对吧？

<details>
<summary>Original English</summary>

**Dylan Field**: Well, I think you have to remember the length of the regulatory review, which definitely needs to be fixed somehow because it's, you know, if you're in a situation where it's actually anti-competitive, which I don't, I still don't believe the Adobe thing was for what it's worth. A lot of people, you know, on the internet probably would say it is, uh, like, or at least they did back then. But I thought their arguments were poor and they were fighting past battles, not looking at the future and what this all would become. Uh, but the um, and I say that not because I'm not like I'm stoked to be independent, too. I'm stoked to be running Figma. That was the plan for Adobe was just run Figma. Uh, either way, uh, running Figma, I'm happy. Independently, we do move fast. I'm gl I'm grateful for that. But uh you go back to your question, it's like we had 16 months of regulatory review. 16 months of regulatory review for any company is punishing and uh in an actual anti-competitive situation that could be like very destructive for one of the parties, right?

</details>

**主持人**: 或者对双方都有毁灭性打击。

<details>
<summary>Original English</summary>

**Host**: Or both.

</details>

**Dylan Field**: 扫地机器人 **Roomba**（iRobot）就是一个绝佳的惨痛教训。

<details>
<summary>Original English</summary>

**Dylan Field**: Um and I think Roomba is a great example actually. Roomba uh was going to be acquired.

</details>

**主持人**: 那还只是一笔体量不大的收购。

<details>
<summary>Original English</summary>

**Host**: Small deal.

</details>

**Dylan Field**: 是的，规模算不上多么惊人，但监管部门就是铁了心想惩罚 **Amazon**，于是直接阻拦叫停。结果导致 **Roomba** 的母公司陷入财务危机破产重组，而当时整个智能扫地机市场版图几乎被拱手让给了中国厂商。所以站在美国国家利益的角度来看，这种监管决策完全毫无逻辑，对吧？

扯得有点远了，但我认为这是一个非常关键的痛点：有些政策往往出自所谓崇高的理想主义，但落到实际执行中，根本无益于美国产业的健康发展。

而且还有更重要的一点：**如今几乎所有的市场空间都远比历史上定义的更加宽广**。任何表面上看起来像是一个固化市场的领域，其实根本不是真正的市场边界所在。现在的市场是由 **AI** 全面重塑的庞大世界，那笔交易即便成了，也顶多只占广义大市场的 1% 到 2%。

你是要站在后视镜的角度、回顾历史去定义市场——这也是监管者唯一符合法条逻辑的做法，还是要作为一名技术远见者，面向未来去定义市场？两者对市场容量和边界的理解会有天壤之别。

<details>
<summary>Original English</summary>

**Dylan Field**: Uh yeah, it wasn't like a crazy deal, but they wanted to pun punish Amazon and so they did not let it go through and because of that Roomba went bankrupt and the entire market at the time basically went to China. Uh so from the United States standpoint, it made no sense, right? Anyway, I go on a tangent, but I do think it's an important point. And there's some policy stuff here that's like when you go for the ideals idealism, it doesn't always practically like help America. But it's also an important point which is almost all markets now are more expansive than they have been historically. And nearly anything that looks like, oh, it's the market. That's not actually the market. The market is AI. turns I mean the market is this massive market and this deal is 1% and 2% of the market like you define the market looking back at the history which is like the only logical way you do it as a regulator or do you do it as a technologist looking forward uh and that could be very different in terms of how you think about markets sizes

</details>

### 交易终止与团队安抚

**Dylan Field**: 不管怎样，回到全员大会——巧合的是，那天正是我们寒假假期的第一天，这说起来蛮有戏剧性的。因为 Figma 是一个办公生产力工具，每到年末假期系统流量都会大幅下降，所以我们在周五就已经跟全员交代：“大家辛苦了，好好享受假期吧。”

结果就在那个周末，我们意识到这笔交易必须画上句号了。周一清晨，我给全体员工发了一条消息：“今天中午召开全员大会，欢迎大家接入会议，我们将同步最新的整体情况和所有细节。”

首先，让我无比感动的是，几乎全公司的人都准时上线参会了。在假期的第一天能有这样的到场率，真的令人动容。

其次，现场最普遍的情绪其实是**如释重负**。这种释怀并不是因为“太好了不用并入 Adobe 了”，而是终于从**长期悬而未决的模糊状态**中解脱了出来。让人悬在半空中长达 16 个月，心理消耗是极其巨大的，每个人脑子里都被迫同时装着两套平行的现实，没人知道未来究竟会怎样。所以大家最初的反应就是整个人轻松了一大截。

从那一刻开始，正如你所问的：如何确保留下来的人都是全身心投入的？

我们的做法非常坦诚：我在公司的 Slack 里发了一段视频，并给每个人发了邮件。我说：“各位，如果你在经历了这段高强度的拼搏后感到心力交瘁；或者你是在此期间加入公司的，原本指望去 Adobe 工作，而现在发现创业公司的高压节奏并不适合你——请务必坦诚相待。未来我们将以创业公司的拼劲全力冲刺，如果你选择离开，我们绝对理解，依然是好朋友。如果你打算走，**我们将提供几个月的全额薪资作为离职补偿**，大家随时沟通，流程极速办理。唯一的约定是：离开后 6 个月内不得重新申请入职；6 个月后如果你想回来，我们非常欢迎你重新申请。”

最终只有非常小一部分人接受了离职补偿方案，但对整个组织而言，这完成了一次非常健康的筛选和新陈代谢。有些人甚至借此机会在职业道路上实现了精彩的华丽转身，迈向了新的人生轨道。我认为这对所有人都是一件好事。

<details>
<summary>Original English</summary>

**Dylan Field**: but um in any case the all hands uh it was actually the first day of a winter break uh which is pretty funny. So, we had told everybody, okay, uh you know, enjoy the holidays. We actually have way less traffic during the holidays because we're a work product. And that was a Friday. And then, um realized sort of over the weekend, okay, this is going to come to a conclusion. and on Monday morning uh sent a message to everybody saying hey all hands at noon and uh dial in if you like and here's what's going on and here's like the full sort of uh details and so first of all so much of the company showed up that was awesome just to see the turnout you know first day of break really and secondly I'd say just like the mood was relief because it wasn't about relief of not Adobe it was relief of not having ambiguity to have ambiguity booty that long is really intense and people have to kind of have two worlds in their head. They're not exactly sure what the future holds. So that was the immediate mood. It was just kind of like lighter. And then from there, uh yeah, I think that the question you asked is right, how do you make sure everyone's all in? And the way that we did it was we said, "Look, I I just kind of put a video out into the company Slack and emailed everybody and said, "Hey, if you're tired after working really hard, if you're someone who joined during this period thinking you're going to go work at Adobe and actually the startup thing is not for you, like please know, we're going to be working very hard, hustling hard, and no shame like we're still on good terms. If you want to leave, here is a few months pay. Uh and you're welcome to just let us know. We'll make it super easy. And from there, uh you know, 6 months before you can reapply. That's the only condition. Uh after 6 months, you can reapply and we'll uh rein you. And it was a pretty small percentage of people that took us up on that, but overall it was healthy. And some people actually ended up doing total career pivots like in wild ways. Uh went on different life paths. Like I I think it was healthy for everyone.

</details>

### Claude Design冲击与SaaS末日论

**主持人**: 之后你们继续打磨业务，公司持续增长，最终成功上市。现在我想把时间快进到今年早些时候：你们宣布了与 **Anthropic** 的合作，随后他们推出了 **Claude Design**。

<details>
<summary>Original English</summary>

**Host**: You continue to build the business. It grows. You go public and I just want to fast forward to earlier this year. You guys announced a partnership with Anthropic Claude Design.

</details>

**Dylan Field**: 不完全是这样。我们原本就一直把 Anthropic 作为生态合作伙伴进行协同，而 Anthropic 随后**独立发布**了 Claude Design。

<details>
<summary>Original English</summary>

**Dylan Field**: We not quite. We we had been working with Enthropic as a partner and Enthropic uh separately announced cloud design. Yes.

</details>

**主持人**: 噢，抱歉，没错。但你们在今年早些时候确实宣布了连接他们的接入方案。

<details>
<summary>Original English</summary>

**Host**: Oh, sorry. Yeah, that's right. But you had a connector with them that you announced earlier in the year.

</details>

**Dylan Field**: 是的，我们构建了 **MCP**（Model Context Protocol）连接器。我们与业内很多顶尖 AI 公司都有广泛合作。但正如你所说，接着他们就对外发布了 Claude Design。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah, we have an MCP. We are partnered with many companies. But yeah, then they announced cloud design.

</details>

**主持人**: 当他们推出 Claude Design 时，你感到震惊吗？比起你们所提供的产品矩阵，看到他们发布专门的设计工具时，你内心有多大的担忧？

因为当时资本市场和社交网络的舆论直接炸锅了，铺天盖地都是：“我的天，Figma 完蛋了，Claude 将彻底碾压 Figma！”

<details>
<summary>Original English</summary>

**Host**: Was that surprising to you when they did that? And how worried were you when they came out with claude design relative to what you guys were offering? Cuz the market looked at it and said, "Oh my god, Figma's dead. Claude is going to crush Figma."

</details>

**Dylan Field**: 哈哈，现在的网络舆论环境就是这样极端——一会儿是“我们彻底王者归来”（We're so back），一会儿又是“一切彻底完蛋了”（It's so over），永远在这两个极端之间无限循环，对吧？

我想问你，就最近这一个月里，外界宣判你或者你的项目“彻底凉了”有多少次了？

<details>
<summary>Original English</summary>

**Dylan Field**: I mean, the nature of online discourse right now is uh we're so back it's so over and it's just a a cycle, right? I mean, how many times have you been all over uh in the last like month?

</details>

**主持人**: 确实，太多次了。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**Dylan Field**: 大概还有很多次你甚至都不知道。

<details>
<summary>Original English</summary>

**Dylan Field**: Probably, you know, a bunch of times I don't even know about.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yes. And everyone

</details>

**Dylan Field**: 我想在那个时间节点，我对这种舆论风向早就司空见惯了。因为当你被外界判处“死刑”无数次，结果每次你不仅没死，反而活得好好的，对吧？到了某个时刻，你终究会清醒地认识到：**社交媒体上的喧嚣根本就不是客观现实**。

不过说实话，我对那次沟通公布的方式确实有些惊讶。通常来说，我认为绝大多数人的本心都是向善的，大家都想赢，都想把事情做好。但我认为对于一家扩张速度极其惊人的组织——Anthropic 的扩张速度历史上几乎无人能及——在剧烈扩张的阶段，内部沟通难免会发生信息脱节和混乱。正因如此，一些怪异的状况就会产生。但无论如何，那次略显尴尬的沟通小插曲已经过去了。

<details>
<summary>Original English</summary>

**Dylan Field**: I think I'm was kind of used to that at that point cuz you know you when when you kind of die uh so many times and then you're actually like not dead, right? you kind of realized at some point maybe maybe this is like not the truth. Social media is actually like not reality. But um yeah, I I uh was overall surprised at the way that kind of communication happened. Uh I think that you know look everybody wants to do good usually. I mean there's some exceptions but for the most part that's that's what I assume for people. They want to win. They want to do good. And I think that organizations scaling really fast. Anthropic like are there any examples of organizations scaling that fast ever? Never can get very confused and um mixed up internally. And due to that weird stuff can happen and I think that it's just the case that yeah, we're on the other side of kind of like a weird bout of uh communication there.

</details>

**主持人**: 那件事对你们的实际业务有造成负面影响吗？

<details>
<summary>Original English</summary>

**Host**: Did it affect your business?

</details>

**Dylan Field**: 噢，完全没有，丝毫没有产生任何实质性或值得一提的影响。

<details>
<summary>Original English</summary>

**Dylan Field**: Oh, no. Uh, like not that not any degree that was like, you know, significant

</details>

**主持人**: 我后来翻阅了你们在那个发布之后的季度财报：你们的年化营收增速达到了 **48%**，业务非但没减速，反而实质上是在**加速增长**！

所以我当时看到这个数据就在深思：那时候整个硅谷都在疯狂鼓吹所谓的“**SaaS末日论**”（SaaS Apocalypse），很多人认为传统软件公司都要被大模型彻底摧毁，我本人此前也是 SaaS 末日论的忠实拥趸。

但我现在深信，优秀的 SaaS 公司之间是有巨大分水岭的：其一在于是否由**创始人驱动**（founder-led）；其二在于**深度嵌入的用户体验**（embedded user experience）到底有多深厚，以及团队能否以此为阵地，利用 AI 进一步加速并重塑自身的业务基石。而你们的实际业绩用事实证明了业务反而在强劲加速。

<details>
<summary>Original English</summary>

**Host**: cuz I read your quarterly report after that announcement. You guys grew 48% year-over-year and the business basically accelerated its growth. So, I'm looking at that and I'm, you know, this was when everyone had the SAS apocalypse thesis in general and I was a big subscriber to SAS apocalypse, but I do think that there's a bunch of ways to distinguish SAS companies. One of which I think is founderled and I think that there's user experience that matters a lot embedded user experience and the ability to kind of build from there especially if you know how to use AI to accelerate and reinvent your business as a founder particularly but your business accelerated.

</details>

### 模型进展与产品体验的鸿沟

**Dylan Field**: 确实如此。我们的业务一直保持着强劲的上升势头。

我认为核心症结在于：对于底层模型公司而言，做产品最艰难的拷问在于——**究竟什么才是真正的产品**？是底层的模型本身？是架在上面的 UI 交互界面？还是两者的某种复合体？如果是复合体，两者的权重又该如何配比？

<details>
<summary>Original English</summary>

**Dylan Field**: Yep. Um, no, it's been continuing to do well. And I think that look, the hard part about model companies and product is like what is the product? Is it the model? Is it the UI on top? Is it some hybrid of both? If it's a hybrid, how is it weighted? And uh, in any case,

</details>

**主持人**: 你指的是像 Anthropic 或 OpenAI 这样的基础模型公司。

<details>
<summary>Original English</summary>

**Host**: you're talking about like an anthropic, an open AI.

</details>

**Dylan Field**: 没错。包括像 Google 的 **Gemini**。无论它是一个针对代码编程的执行支架，还是像 Claude Design 这样的独立应用。

我认为，**人们极其容易把底层模型的进展误当成产品体验的进展**（mistake model progress for product progress），对吧？

而客观事实是：像 Figma 这样的一款专业级工具，需要耗费极其漫长的岁月去雕琢，需要经历极长时间去反复验证并校准用户的真实工作流。即使到了今天，我们依然有很多未尽的工作要做，我们的核心用户会毫不客气地指出这些不足，我们也时刻在竭尽全力把它打磨得更好。

因此，当模型公司草率推出一个功能时，它未能瞬间引爆市场成为爆款，这根本一点都不让人意外。因为要真正满足严苛的专业人士需求，你必须在核心用户旅程和深层工作流上倾注大量的工程心血。

Claude Design 目前试图做成一个大而全的宽泛产品，涵盖海报排版、图形设计等各种场景。或许他们在某些细分领域能做得不错，但在其他专业场景中未必尽如人意。我不对这款产品盲目唱多或唱空，我的观点非常简单：**为专业人群打造顶尖的设计工具本身就是一件极其困难的苦活累活**。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. Yeah, I mean Gemini like whether it's a harness for coding or it's a product like claw design which you mentioned. I think it's easy to mistake model progress for product progress, right? The reality is a tool like Figma, you know, has taken a very long time to build uh and a very long time to make sure that we get the workflows right for our users. And we still have work to do. Our users will tell you that. Uh and I and we're always trying to make it better. So I think that like it's it's sort of um not surprising that it wasn't an instant hit or something when there's actually quite a lot of work on the just core user journey workflow side that you have to do to meet the needs of professionals. Now there uh they've made cloud design into a product that is is broad. So is trying to do a lot of things like you'll see like posters and stuff as well like graphic design scenarios I believe when you go to their homepage and and like maybe they'll do well in some areas and not other areas. Like I'm not bullish or bearish on the product. I think it's just like hard to make good design tools for professionals.

</details>

**主持人**: 是的，设计的范畴太宽广了，涵盖太多不同的细分品类。

<details>
<summary>Original English</summary>

**Host**: Yeah. There's a lot of things to design and a lot of categories of design.

</details>

**Dylan Field**: **专业工具的交互手感宛如一件精密乐器**。你必须把手感调校到极致，必须把底层操控力学彻底做对。

<details>
<summary>Original English</summary>

**Dylan Field**: The feel of it is like an instrument. You have to get the feel right. You have to get the mechanics right.

</details>

**Dylan Field**: 没错。多年来，我们为画布上的每一个细微末节死磕到底，倾听了海量的用户反馈。用户的感受取决于他们的背景、手头的具体任务以及他们试图解决的目标。使用场景极其繁复。

但总的来说，我认为软件行业的存在形态，远比所谓的“SaaS末日论”所描绘的更加丰富多元。软件绝非一个非黑即白、非生即死的单一品类。作为一家应用层软件公司，你拥有大量的路径去维持长期的生命力，构建可持续增长的壁垒。

这其中最核心的一条，就是**对目标客群做到极致的专业化专注**。你真正懂得你的用户，并百分之百为他们量身打造体验，这是无可替代的价值，对吧？

我认为一个绝佳的标杆就是 **Cursor**。按照常理，Cursor 根本不该取得那样的惊人增长——各大前沿模型实验室都在用自家最强大的模型拼命追赶他们，而在 Cursor 拥有自己的自研模型之前，他们几乎就是在前沿实验室的包围中突围的。然而，Cursor 的团队对开发者的实际体验极度痴迷，他们能够预见行业拐点，具备卓越的战略定力，确保在每一个细节上都做对用户最有利的事情，最终斩获了惊人的成功。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. And we've stressed every detail of that and have had a lot of feedback over the years about what people like and don't like. It depends on where they're coming from. It depends on uh their task and sort of like what they're trying to overall do. And there's so many scenarios. But overall uh you know I think that um there are more modes for software than are implied by the SAS apocalypse. And it's not like software as a category is binary, good or bad. Uh there are plenty of other ways that you can um make sure that you're able to substain yourself long term and have a growing business long term as a software company or app layer company. Uh and part of it is yes, if you're as specialized as possible on a target audience and you know your audience, you're building for them, that is something that matters, right? Uh, and I think a great example of this is Cursor. Um, Cursor like by all means should not have grown the way they did. You've got all these frontier labs that are chasing them with their own models before Cursor had a model of any kind. But yet, Curser really obsessed over the user. They saw around corners. They strategized. They made sure they're doing the right thing for the customer. And they've had an incredible success.

</details>

**主持人**: 没错。我认为这太令人惊艳了，而且我相信这种模式将在许多不同赛道的公司身上反复上演。

<details>
<summary>Original English</summary>

**Host**: Yeah. And I I think it's amazing and I think it's an example that will be repeated uh across many different types of companies.

</details>

**主持人**: 这么说，**SaaS并没有消亡**。

<details>
<summary>Original English</summary>

**Host**: SAS is not dead.

</details>

**Dylan Field**: 嗯，不能说所有的 SaaS 公司都安然无恙；但同样，说所有 SaaS 公司都会死绝也绝非事实。

<details>
<summary>Original English</summary>

**Dylan Field**: Well, I I think that it's not true that all SAS companies are fine. Yeah. And it's also not true that all SAS companies are dead.

</details>

**主持人**: 很有见地。

<details>
<summary>Original English</summary>

**Host**: Fair enough.

</details>

### 突破共识与独特观点

**主持人**: 在一个充满 AI 与智能体（Agentic AI）的世界里，我作为人类拥有通过 Prompt 发出指令的能力，然后让模型帮我生成海量方案。但真正的核心在于人类的判断力。

<details>
<summary>Original English</summary>

**Host**: in a world of AI, agentic AI, I have this capacity to prompt as a human and say,

</details>

**Dylan Field**: 这正是最具人性的部分。而且这不仅关乎人性，更在于**人类往往害怕表达让人不适的独特观点**。大家潜意识里非常害怕说出脱离大众共识（non-consensus）的话。

<details>
<summary>Original English</summary>

**Dylan Field**: That's the human part. It's not just the human part. It's also the part that humans are uncomfortable having. Uh, I think that folks are scared to say something that's not consensus.

</details>

**主持人**: 太真实了！最伟大的艺术家、最卓越的商业领袖、最杰出的政治家，历来都展现出这种非凡的勇气——他们敢于说别人不敢说的话，敢于做别人不敢做的事。这才是推动世界改变的原动力。

<details>
<summary>Original English</summary>

**Host**: It's so true. I mean, this is what the greatest artists, the greatest business leaders, the greatest politicians have always demonstrated is the willingness to to be brave to say and do the things that no one else would say or do. And that's what changes the world.

</details>

**Dylan Field**: 我还想把**脱口秀喜剧演员**也加入这个行列。

<details>
<summary>Original English</summary>

**Dylan Field**: And I would also add comedians to the mix, too.

</details>

**主持人**: 没错，喜剧演员！

<details>
<summary>Original English</summary>

**Host**: And comedians,

</details>

**主持人**: 喜剧演员的价值往往被严重低估了。我去年邀请了 **Tony Hinchcliffe** 来我们的活动演出，在如今充斥着取消文化（cancel culture）的时代，他是少数几个敢作敢当、直言不讳的人之一。

<details>
<summary>Original English</summary>

**Host**: comedians are underappreciated. I had Tony Hinchcliffe fight our thing last year because he's like one of the few guys that is willing to say and do things nowaday in the cancel culture era

</details>

**Dylan Field**: 是的，优秀的喜剧演员总能以一种让人易于接受的幽默方式道出残酷的真相，而换作平时，人们根本听不进这些真话。

他们愿意挺身而出说出那些话。这无关政治正确，关键在于：**你是否拥有能够穿透喧嚣噪音、并且持久立足的核心信息？**

看看如今的社交媒体：任何一个独特的视角、任何一件新鲜有趣的事物，都会在瞬间被社交网络的洪流稀释殆尽。因此，除非你拥有一种能够源源不断产生内容的能力，并且你的核心观点能够因为超越了传统的奥弗顿之窗（Overton window）而历久弥新，否则你根本无法在注意力经济中实现真正的破圈。而**注意力经济是极其残酷无情的**。

<details>
<summary>Original English</summary>

**Dylan Field**: but comedians often like speak truth in a way that people otherwise couldn't hear willing to say things and uh it's not about political correctness. It's about do you have a message that can rise above the noise and do so in a sustained way? Because look at social media right now. Like every unique point of view, everything interesting, it gets diffused into like the ether of social media instantly. And so unless you've got uh something that allows you to kind of keep generating content and a message that is really uh evergreen because it's so outside of the over 10 window, you're not going to be able to actually break through and have any attention. And the attention economy is ruthless.

</details>

### 机器生成与人类创造力本质

**主持人**: 这不也正是人类创造力的本质所在吗？如果你做的事情从未脱离前人的足迹，你根本没有在真正创造，你只是在模仿、抄袭、复印而已。**真正的创造，就是去做前所未有的全新事物**。而新颖性从定义上就要求你去做从未被做过的事情。

<details>
<summary>Original English</summary>

**Host**: Is this also what human creativity is? If you're not doing something that's never been done before, you're not creating something. You're mimicking something. You're copying something. You're xeroxing something. But to do something new is to create. And newness requires doing things that have never been done before by definition.

</details>

**Dylan Field**: 从定义上讲就是如此。

这意味着你必须在**模型训练分布的均值之外**进行探索。如果你只是进行没有任何高阶脚手架辅助的粗糙 Prompt 交互，你所得到的输出必然落在训练集分布的最平庸正中央。只有当你跳出这个分布框架，你才能真正实现破圈并创造出独一无二的作品。

而我相信，市场终将重奖这种独创性。所有人都能清晰地分辨出来。甚至在企业内部的注意力分配中也是如此——我最近已经听到太多管理者的抱怨：“今天我又收到了一份用 AI 批量生成的 PPT 汇报……”

<details>
<summary>Original English</summary>

**Dylan Field**: By definition, and uh therefore you are operating outside of this distribution of training. It's not even about operating outside the mean of the distribution which is where you start if you're just prompting without any like any kind of advanced scaffolding around it. Uh but you're actually doing something that is breaking through and it's unique and I do think that will be rewarded by the market. Everyone's going to see it. I think it's even rewarded by the attention market of organizations. I'm already hearing from so many like uh I got another deck made by AI today.

</details>

**主持人**: 极其真实！你甚至怀疑做那份 PPT 的人自己到底有没有从头到尾读过一遍，他们究竟知不知道里面写了些啥？

<details>
<summary>Original English</summary>

**Host**: Totally. And I don't even know if the person who made it, I like don't know if they read it. Do they even know what's in their deck?

</details>

**Dylan Field**: 在 Figma 内部，我们做了一个非常简单的小规定：如果你在写作或汇报中使用了 AI，请直接在文档顶部标注“**由 AI 辅助撰写**”。非常简洁，执行起来毫无门槛。公司内部有人拿这个开玩笑，但大家都照做了。

这带来了一个巨大的好处：当我们阅读一份材料时，我们能清楚地建立信任，知道作者是否真正投入了足够的心思去打磨，是否值得占用你宝贵的时间去消化。

我认为未来围绕“**信任**”将会发生巨大的分化。而建立信任的核心途径之一，就是**亲手用双手去创造和打磨**（do something with your hands）。

另一个至关重要的逻辑在于：如果你脑海中已经对某个产品的设计、审美或体验拥有清晰的愿景与独特观点，那么先借助 AI 进行快速原型搭建是非常棒的——它能帮你彻底克服面对空白画卷的启动恐惧。你可以基于它生成的雏形迅速做出反应并修正：“这些地方我不满意，我要亲手改掉它们。”这种人机交互的双向往复反馈极具价值。

但反过来，如果你自己胸无点墨、毫无主见，全盘指望把愿景委托给 AI 来实现，那你完全是在透过 AI 的滤镜看世界，而 AI 只会给你它自身训练分布里的均值产物。

<details>
<summary>Original English</summary>

**Dylan Field**: And at Figma, we actually made it so that uh it was just a simple thing, but we said, "Hey, if you are uh using AI in your writing of any kind, just put at the top written with AI." Very simple, very easy to follow. Uh and you know, people made jokes about internally, but people do it. And it makes it so that we can all trust that when we see something, we know that it's been cared for enough that it's like worth your time to process. And I uh I think that we're going to see some bifurcation here around trust. Uh and one way to get trust is to do something with your hands. The other point that's important is if you have a vision or if you have a point of view in your head of how something should be designed or look aesthetically or from an experiential standpoint, you're I I think it's great to start with building with AI. It gives you something to get past like the blank page, blank canvas problem. You can then react to it and say, "Here are all the things I don't like. I'm gonna I'm gonna go fix these things. I'm going to change them up." because it's really helpful to have a back and forth. But if you don't if you have your own vision and you're trusting AI to implement it, you're doing it through the lens of AI and like AI has kind of like its own distribution

</details>

**主持人**: 被模型的固有分布所束缚。

<details>
<summary>Original English</summary>

**Host**: the model fit by it. Yeah.

</details>

**Dylan Field**: 没错，那样你根本无法得到你真正想要的结果。

而如果你能将两者有机结合——这也是我们正在 Figma 中竭力打造的体验：**把代码变成画布上的一种原生材料**。让你既可以通过构建来辅助思考，也可以在需要深入雕琢时，亲自用双手在细节上精益求精，在两者之间实现高速无缝的往复切换。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. And so you're not going to get exactly what you want. Now if you're able to do both and that's what we're trying to enable in Figma make code a material on the canvas make it so that you can go start by building you can build to think if you like uh but also when you want to think and work with your hands you can do that too right and you go back and forth rapidly

</details>

**主持人**: 我想起 Photoshop 最早期的日子：作为一个狂热的用户，我记得当图层功能刚推出时，大家都吓坏了；后来各种滤镜库发布、Kai's Power Tools 问世时，所有摄影师都在惊呼：“摄影师的存在意义是什么？你们正在扼杀摄影的艺术与创造力！”

但事实是，它释放了一个全新的创意纪元！一代全新的数字艺术家借此诞生，他们熟练驾驭滤镜和图层能力，在数字画布上彻底重构了可能性的边界。它本质上是一套全新的工具箱。这并不意味着旧有的创作者可以直接无缝映射到新工具体系中，但这引发了人类创造力与潜能的巨大井喷，从各个维度拓宽了表达的极限。

我们今天似乎正在重新踏入这样一个翻天覆地的时代。

<details>
<summary>Original English</summary>

**Host**: right I remember the early days of Photoshop just having been a user avid user from the early days people freaked out when layers happened and then they freaked out when all the filters came out and when Kai's power tools came out, everyone was like, "What's the role of the photographer anymore?" It's like you're destroying the art of photography, the creativity of photography. But it unleashed a new era of creativity because now these new artists emerged that could use these filters and use these layering tools and capabilities to reimagine what's possible on a canvas. And it was basically a new toolkit. doesn't mean that the old creatives mapped perfectly to the new creative system and tools, but there was an explosion in creativity and human potential that arose from this and we pushed boundaries in all sorts of ways. Feels like we might be entering that era again.

</details>

**Dylan Field**: 我坚信这一点。这完全吻合我刚才提到的市场动力学规律：为了争夺注意力、促成深层互动并让大众真正产生共鸣，你必须拿出全新的东西。你必须真正具备冒险精神，敢于尝试大胆的突破。

人们对变革的抵触情绪是客观存在的。你可以去 Google 搜索一个绝佳的例证：去搜当年 Photoshop 刚引入图层功能时设计社区邮件列表的归档记录，里面全是“这是史上最垃圾的糟糕设计”之类的激烈抨击。那些公开发表的邮件历史今天依然能搜到，上面的抵制反应令人大开眼界。

然而显而易见，图层最终成为了未来的标准范式。在这个过程中，传统摄影大师依然在世上创作着伟大的作品；但真正对摄影产生颠覆性冲击的，其实是**智能拍照手机**的普及。正是手机让人人随身携带镜头，大家不再去买笨重的专用相机，并通过 Instagram 和移动摄影彻底改变了大众与图像的关系。技术彻底重塑了无数人的生活，我无法武断地下结论这究竟是变好了还是变坏了，但时代的巨变是实实在在发生的。

<details>
<summary>Original English</summary>

**Dylan Field**: I'm a big believer in that and I think that part of it is what I described about market dynamics. In order to get attention, order to get engagement, in order to get people to care, you have to do something new. uh you have to actually be daring and try things that are bold. The resistance to change is real and there's a great thing you can Google actually for your point. Look up the mailing list for when layers was introduced and it's like people going this is the worst thing ever. Uh and you can find it if you Google it's like on a a mailing list that's publicly available and you can see all their reactions. Totally. Um, but obviously it became the future and I think that uh there's also still photographers in the world who are doing incredible work. But the bigger disruption, if we're going to be real, it was the camera phone. Uh, that was what made it so that people stopped buying cameras that were dedicated to the task of photography because the best camera is the one that's on you and started treating photography in a different way with Instagram and their camera phone. Uh so it transformed for a lot of people and I can't tell you if it's better or worse as a result. Uh but there was change.

</details>

### 动态媒介与新形态创作工具

**主持人**: 关于人类创造力有一种经典观点：人类的创造本质上是在潜意识中“**连点成线**”（connecting dots）。你在过往人生中接收到了海量的感官输入、人生阅历与观察，基于这些沉淀，你在大脑中把这些点连接起来，向外推演并构建出世间从未有过的全新视野。

你认同这种关于创造力的阐述吗？它与今天 AI 的生成机制有何本质不同？我想再次探寻：在 AI 时代，人类不可替代的独特根基到底在哪里？

<details>
<summary>Original English</summary>

**Host**: There's one view on human creativity that human creativity is basically connecting dots in the unconscious that you've had, seen or experienced all of these things in your life or in your set of inputs, sensory inputs and from those inputs you connect dots and then you extrapolate a forward view of things that hasn't perhaps been seen in the world before. Do you agree with that view on creativity and is it distinct from actually what AI does? And again, I want to go back to the uniqueness of the human in an AI era.

</details>

**Dylan Field**: 我认为人类身上有一个极为显著的特质：**我们永远在主动追求新颖性**（novelty）。人类内在的奖励函数与 AI 截然不同；人类的损失函数同样截然不同。

打个比方：如果我突然拧开面前这瓶水泼你一身，惹得你勃然大怒，我敢向你保证我绝对不会再干第二遍。但是换作 AI 强化学习（RL），你必须反复在海量数据中反复惩罚警告它无数次，它才能记住“不能这么做”。

<details>
<summary>Original English</summary>

**Dylan Field**: Well, I I think that um one thing that happens with humans is they're always seeking novelty. Like our reward function is different than like an AI. Also, our loss function. Like if I was to open this bottle of water and splashed all over you and you got mad at me, like you bet I'm not gonna do that again. But an AI like you know with RL you gota like really tell it a bunch of times uh uh that no you don't do that. Um

</details>

**主持人**: 就像求着说“机器人别再踹我了”。

<details>
<summary>Original English</summary>

**Host**: robots stop kicking me.

</details>

**Dylan Field**: 哈哈没错。随着未来算法架构的演进，这或许会有所改善。但从根本上讲，人类的大脑神经结构与我们目前构建的 AI 系统存在本质差异。在脑神经科学领域，人类未知的谜团太多了；但在创造力这个命题上，人类大脑确实有着完全不同的底层逻辑。

而且我认为，**设计并不等同于纯粹的艺术创造**。设计不仅仅是创意挥洒，更像我之前讲的，它始终是**问题解决**的实践。这两者的融合极其迷人：你面对的是真实的用户，你必须切实解决他们的痛点，同时又要以极具创意的形式与他们产生情感链接；你还必须将作品嵌入更庞大的系统生态中——品牌调性、组织文化、商业目标等等。

在大脑中同时处理不同抽象层级的信息，同时试图在由排列组合引发的爆炸性搜索空间中打磨出完美的界面交互与操作流，这是一件极其美妙的挑战。

我个人极其兴奋的一个方向是：利用 AI 重新发明既有的艺术与媒介形态，实现更**动态化的内容生成**。创作者的层级被进一步拔高，负责设定核心参数体系，而不再需要亲自逐帧渲染最终产物；最终的产物有点类似于现代电子游戏——在用户眼前实时动态渲染。在游戏背后，庞大的创意团队构建了所有的资产对象、世界观故事线以及情绪叙事流。虽然生成的过程充满动态不确定性，但这种叙事逻辑必将渗透到更多全然不同的全新媒介中。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. Well and maybe that'll change with architectures over time but like overall the brain is different uh than the current systems that we've made with AI. And I I think that uh it's unknown. We don't know much about neuroscience uh overall. I'd love to get to the point where like we all know more about neuroscience, but something is fundamentally different there when it comes to creativity. And I also think design is different than creativity. It's not just creativity. It's also problem solving like I mentioned earlier. And the combination of the two is I I just find it fascinating because you have a user, you're trying to solve their needs, you're trying to do so in a way that stands out as creative and it connects with them. And also like you have to connect to wider systems, the marketing brand, the culture, the business problems uh and so on. and and like holding all that in your head at different levels of abstraction while trying to like deliver a screen or a flow uh that like from a searchbased standpoint can be a comatorial explosion is just pretty cool. It's pretty fascinating. I'm actually personally really excited about the idea of reinventing existing art form and media where AI can enable more dynamic generation where the creator steps up a level, sets a bunch of parameters, but doesn't actually necessarily render the final product, but the final product sort of like in a video game

</details>

**主持人**: 最终产物在面对玩家时即时运算生成，但背后的游戏开发者掌控了所有的底层构件、世界观设定与叙事脉络。这种表现形式更加千变万化，并且必定会蔓延并重塑各种全然不同的数字媒介。

<details>
<summary>Original English</summary>

**Host**: is rendered on the fly with the user in front of it. But the creator, the creative team behind a video game, for example, is building all of the object. They're building the story line. They're building the narrative flow. And the realization of that is much more dynamic, but I feel like it's going to find its way. It's going to leech its way into many more totally different media.

</details>

**Dylan Field**: 我们在 Figma 内部也在积极打造这方面的工具矩阵。比如在 Figma Design 中，我们上线了生成式工具和着色器能力，允许用户进行深度的动态创作。

我们还推出了一款名为 **Weave** 的产品。Weave 本质上是一套基于节点的创作系统，你可以将不同模型的输出结果灵活连接到其他输入端。我们背后的核心理念是：**用 AI 进行生成并没有错，但创作者必须拥有一种像捏陶土一样去精雕细琢的手柄**。在 Weave 中，许多艺术家创作出了令人叹为观止的视频和摄影艺术作品，其最终产出让人拍案叫绝。

只要你心存坚定的审美意图，愿意投入精力深耕，你总能打磨出更卓越的作品。

现在的情况是：每当一个全新的大模型发布，整个行业在算法信息流的助推下，就会陷入为期数天的“**AI集体癫狂**”（AI psychosis）——社交媒体上顶尖的效果被疯狂刷屏，所有人都惊呼“这个模型能搞定一切！”

然而仅仅过了几天，热度迅速降温，大家纷纷冷静下来：“行吧，我摸透这个模型的套路和固定模版了。”人类的适应速度极其惊人，新鲜感转瞬即逝，它不再能刺激你的多巴胺分泌。于是创作者开始思考：“既然它总是输出这种千篇一律的东西，我该如何超越它？”

我们正身处这样一个周而复始的螺旋循环中。但耐人寻味的是：大模型在那些**具有明确验证标准的确定性领域**（如数学逻辑、网络安全攻防）中，IQ 点数正在不可思议地成倍堆叠；然而在**创意和设计**这种缺乏硬性验证标准的领域中，模型整体的演进却显得相当缓慢而渐进。这背后很大程度上是因为这些领域属于“不可硬性自动验证”（non-verifiable）的范畴。

<details>
<summary>Original English</summary>

**Dylan Field**: And we we have products around that too. Like in Figma Design, you can have now generative tools and shaders where you can do very much that or we have a product called Weave. And weave is basically a nodebased system. You can connect model outputs into uh other inputs and such. And the whole idea is like it's not bad to generate with AI, but you need a way to craft that clay. You need a way to mold it. And uh with weave, people do like the most amazing video and photo work. Uh and overall just like the the outcomes that are achievable with it are incredible. Uh so yeah I think that if you've got the intention if you actually care to do the work um you can always get to a better result and people you know new model drops there's like this AI psychosis moment that people are in for a few days and it's like I think also aided by algo feeds totally the best results rise to the top everyone's like this model is everything and then a few days later it's it's okay okay I know the kind of like main tropes of the model. Um, and you adapt fast. Like the novelty is gone. It no longer is a thing that's that's kind of like rewarding you or firing off your dopamine system or whatever. And instead, you're like, "Okay, well, yeah, it always does that thing. How do I move past it?" And that seems to be the continued loop we're in. Uh, which is sort of fascinating because models keep getting so good when it comes to these formal domains, math, cyber security. uh like the IQ points just stack and stack and stack and then for creativity and for design it's very incremental progress overall. Uh maybe that will change at some point, but I think the fact that these are non-verifiable domains has something to do with it.

</details>

### 全民造物时代与数学探索的悲喜

**主持人**: 这或许恰恰说明了人类在 AI 工具链中的核心生态位：**构思、创造、定义设计**，让 AI 分担更多执行层面的工作，从而赋予人类完成更大规模创举的能力。

最近有没有什么正在涌现的艺术形式或数字媒介，让你感到格外兴奋或着迷？

<details>
<summary>Original English</summary>

**Host**: And it's probably the fact that maybe that is the human role in the AI toolkit, which is conceive, create, design, and let the AI do more of the work, but it gives you the ability to do much more work. Any art or media that you're particularly excited about or interested in that's kind of emerging right now?

</details>

**Dylan Field**: 我一直对人们做出的全新 AI 先锋实验格外着迷。比如在数字媒介领域：前几天有位设计师艺术家做了一个网页，实际上是写给 Figma 的一封公开信。它在信息流里击中了我，因为算法推送了 Figma 的关联词。那个网页的巧妙之处在于：**每次只要你的视线移开该网页标签页再切换回来，网页上的内容就会被腐蚀劣化一点点**——它本质上是一篇关于人类注意力的艺术评述，我觉得这太精妙了！

<details>
<summary>Original English</summary>

**Dylan Field**: You know, I I find it fascinating uh when people do sort of like new AI experiments. For example, uh put this in the media category. Um there was a designer artist type that made a web page the other day. Uh and it was like a letter to Figma actually. So it caught my attention because I was, you know, getting the Figma hit on the algo feed. And every time you moved away from it uh and came back, it got slightly more degraded and it was basically a comment on attention. I thought that was really cool.

</details>

**主持人**: 太有意思了，那简直就是一件纯粹的艺术品。

<details>
<summary>Original English</summary>

**Host**: Oh, cool. that was a piece of art.

</details>

**Dylan Field**: 我也这么认为。它表面上是一个普通网页，但他们表达思想的技法与路径独树一帜，极少有人这么做过。而且那封信本身也写得文采斐然。

我一直在密切关注这类创新。让我想起早年间（大概 2019 年前后），当 NFT 刚兴起时，很多人尝试用 AI 制作生成艺术，其中的一些技法令人惊叹。我非常欣赏 **Holly Herndon** 的实验：她将自己的真实人声提取出来，转化为开源式的模型资产，允许全球创作者自由调用创作。这种探索极具开创性，远超那个时代。

在“何为自我”、“何为群体共有”、“何为独特且可拥有的资产”之间的博弈与边界探索，始终让我心驰神往。我一直深深着迷于这个交叉领域。

<details>
<summary>Original English</summary>

**Dylan Field**: I thought so. It was web page. But like I thought that the technique and the way that they went about it was really neat and like not something that many others have done. I've seen a few other things like that, but overall I thought it was a very cool way to do it. Um, and it was also just a very well-ritten letter. Uh, I like the letter, too. But I Yeah, I see stuff like this. Um, and you know, back in the day, I remember um seeing people do like NFT art with AI when NFTs were a thing, you know, so this like 2019 or something like that. But the way they did it sometimes was uh really remarkable. loving Holly Hernand's work around uh taking her voice and making it so that her voice was something that people could use in almost open source way uh that was quite incredible and ahead of its time. Um and I think this like sort of play between uh what is me, what is the collective and what is it that is unique and ownable versus what is not. Uh is is quite fascinating. I've always been fascinated by that intersection.

</details>

**主持人**: 太酷了。在对谈接近尾声之际，我想聊聊社会上关于 AI 的负面情绪：很多悲观论调认为 AI 正在剥夺人类的自主性（agency），人类的潜能天花板正在被锁死。

能否谈谈你的视角：如何看待在这个时代**每个人都拥有成为创作者、成为设计师的潜能**？AI 将如何赋能每一个普通人，让创造不再局限于象牙塔里的一小撮精英艺术家，而是让全人类都能设计并向世界输出作品？你对此持有怎样的信念？

<details>
<summary>Original English</summary>

**Host**: Yeah, that's cool. Just as we wrap up, a lot of the commentary on AI that's negative is that it takes away human agency, human potential gets capped out. Can you just talk a little bit about your view on the the potential of every human to be a creative, to be a designer, and how AI might perhaps magnify every every person, not just the quote creatives where they're in some elite class of artists in some special building, but the ability for every human to create and the ability for every human to design and produce things in the world and where you sit with that right now?

</details>

**Dylan Field**: 我认为这个命题的格局甚至更加宏大。无论在 AI 时代之前还是之后，作为人类，你始终面临一个根本性的抉择：**你究竟选择做一名被动的消费者，还是做一名主动的创造者？** 你是要选择那条容易走的平坦小道，还是要选择征服艰难的高山？

我观察到当前社会上出现了一种趋势：越来越多的人正在主动放弃独立思考，完全让 AI 代替自己的大脑去思考。在 Figma 内部这种情况较少，但在我与外界更广阔的日常接触中，这种依赖比比皆是。这确实是你可以选择的一条路。

但还有另一条更值得走的路：**利用 AI 来深化你对这个世界的认知**，去学习和掌握那些过去因为门槛过高、耗时过长而不敢涉足的领域，从而极大拓展作为人类在世间体验与创造的边界。对我而言，后者才是真正激动人心的所在。

<details>
<summary>Original English</summary>

**Dylan Field**: I I think it's even broader. I think it's it's um as a human in general, preAI, post AI, you have a choice. Do you want to consumer create? Do you want to take the easy path or do you want to like climb the mountain? And what I'm seeing happen right now a lot is people are letting AI think for them. Uh less at Figma, but like more just like in my interactions with the world. Uh I just see a lot of this at the moment. And that's one path you can take. But the other one is actually you use AI to further your understanding of the world to learn to do things you never would have dared to do before because they were would have taken so much time to learn or it's so hard. Uh and to really expand like the potential ways that you can like live as a human. Uh that to me the latter is the interesting part.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Dylan Field**: 至于前者——我为什么要把自己的思考权拱手让给别的东西？我这辈子最大的追求，就是探索如何独立思考。我真心期盼大家能够利用 AI 去创造美好，成为一股推动世界向前的建设性力量，而不是浑浑噩噩地沦为从众的“蜂巢思维”（hive mind）。

<details>
<summary>Original English</summary>

**Dylan Field**: The former like why would I want something else to think for me? like my entire life has been about like figuring out how to think and um I don't know I just hope that people use AI to create good and to like go be a force for it rather than just kind of like joining the hive mind.

</details>

**主持人**: 人人皆可成为造物者。

<details>
<summary>Original English</summary>

**Host**: Everyone can be a maker.

</details>

**Dylan Field**: **人人皆可成为造物者，人人皆可践行大胆的构想**。这完全取决于你的意志力与好奇心。只要你心怀好奇，并且愿意付出脚踏实地的努力……

<details>
<summary>Original English</summary>

**Dylan Field**: Everyone can be a maker. Everyone can go do bold things. Uh it's about willpower and it's about curiosity. And if you're curious and you're willing to do the work, uh I believe

</details>

**主持人**: 保持无畏，忠于真实发声。

<details>
<summary>Original English</summary>

**Host**: be brave and speak your truth.

</details>

**Dylan Field**: 没错，正是如此！那样你就能成就不可思议的事业。

我们未来的社会形态很可能会发生翻天覆地的重塑：无数我们今天难以想象的事情将成为现实，而很多我们今天习以为常的人类日常行为将彻底退出演讲台。那种未来究竟如何展开，我们俩谁都无法准确预言，但不可否认的是，我们正并肩伫立在波澜壮阔的变革悬崖边。

昨晚 **OpenAI** 投下的“数学重磅炸弹”更是直击我的灵魂——他们针对一系列世界著名数学猜想，一口气发布了 **700 多篇论文**！这绝对是一场前所未有的力量展示。我的内心五味杂陈，甚至不知该如何消化这种冲击。

<details>
<summary>Original English</summary>

**Dylan Field**: Yeah. Exactly. And then I think that you can go do incredible things. Uh we will probably see a vastly different setup in the future where things that we can't imagine are possible and things we take for granted are no longer in sort of the realm of what humans do every day. uh how exactly that will look. I don't think either of us can tell, but it is the case that both were on the precipice of great change. And nothing hit home for me more than the math drop last night uh from OpenAI of 700 plus papers on all sorts of very famous problems. Uh that that was a show of something. Uh I had a lot of emotions. I don't I don't know how to process

</details>

**主持人**: 我认为那是人类认知探索史上最伟大的发现之日！

<details>
<summary>Original English</summary>

**Host**: I thought it was the greatest day of discovery in human history.

</details>

**Dylan Field**: 从客观事实而言，确实如此。

但与此同时，在这份辉煌与震撼之中，又隐隐伴随着某种难以言喻的伤感。

<details>
<summary>Original English</summary>

**Dylan Field**: Oh, I mean factually, yes. And also like something about it was like brilliant and exciting and something about it was kind of sad.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Dylan Field**: 我不知道该如何准确描摹那种伤感……那种感觉就好像是我们在获得前所未有的力量的同时，也永久性地失去了一样极其珍贵的东西。

<details>
<summary>Original English</summary>

**Dylan Field**: And I I don't know how to articulate the sadness, but it felt like we lost something and gained something at the same time.

</details>

**主持人**: 面对这一切，我选择抬起头凝视下一座崭新的前沿边疆。我认为未来的边疆比人类以往任何时候都更加光明、更加宽广、更加触手可及。所以我内心充满着前所未有的兴奋。

<details>
<summary>Original English</summary>

**Host**: I don't know. I lift my head up and I look at the next frontier and I think that the frontiers are brighter and wider and more accessible than they've ever been. So, I'm pretty excited.

</details>

**Dylan Field**: 噢，我也同样无比兴奋！我相信未来的世界会精彩绝伦。我是一个坚定的乐观主义者，前路上必然会伴随重重挑战，但我们终将一一化解。

<details>
<summary>Original English</summary>

**Dylan Field**: Oh, I'm excited, too. And I think that the world will look amazing and uh I'm an optimist. I think there's gonna be a lot of challenges and we'll figure them out.

</details>

**主持人**: 没错。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Dylan Field**: 那些挑战究竟会以何种严峻形态显现，我们尚无法完全看透。但数学始终带有一种神秘而圣洁的特质——就像一个尚未被破解的千古难题：这个猜想究竟是对是错？背后的机理为何如此？人类在那种未知的神秘感中苦苦探索、与谜题博弈的过程，本身就是一种无与伦比的美妙体验。

因此，在为技术进步及其带来的无限潜能欢欣鼓舞的同时，我认为，**为人类失去了一点点神秘感而感到一丝淡淡的怅惘，也是完全合情合理的**。

<details>
<summary>Original English</summary>

**Dylan Field**: Uh how exactly and what the challenges will be in their full form, we have yet to see. But yeah, I do think that like math is uh something that somehow has a quality of mystery to it like an unsolved problem. Uh is it you know is this conjecture true or false? How? why uh grappling with that mystery is something that is special and uh I I'm both excited for the progress and like all the things it'll make possible and also like I don't think it's wrong to like mourn the loss of a little mystery.

</details>

**主持人**: 总结得太精辟了。Dylan，这是一场极其酣畅淋漓的对谈。我们要不要再去整一杯？

<details>
<summary>Original English</summary>

**Host**: Right. Fair enough. Dylan, this has been a great chat. Should we go have another drink?

</details>

**Dylan Field**: 听起来太棒了。

<details>
<summary>Original English</summary>

**Dylan Field**: Sounds good.

</details>

**主持人**: 走，开整！

<details>
<summary>Original English</summary>

**Host**: Let's do it.

</details>

**Dylan Field**: 谢谢你，兄弟。

<details>
<summary>Original English</summary>

**Dylan Field**: Thanks, man.

</details>

**主持人**: 非常感谢。我这就全仓压上（All-In）了！

<details>
<summary>Original English</summary>

**Host**: Thanks. I'm going all in.

</details>