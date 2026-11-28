---
author: a16z
date: '2026-10-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=blkIGLlZePg
speaker: a16z
tags:
  - systems-thinking
  - distributed-systems
  - system-operations
  - economic-equilibrium
title: 系统思维视角下的 AI 编码与系统运维及经济现实
summary: 对话探讨了从系统思维角度看 AI 对软件工程与运维的影响。对话指出 AI 在代码生成与基准优化上表现显著，但在复杂分布式系统运维中仍处于早期阶段，面临现实复杂性挑战，其实际落地与商业价值受到经济均衡的制约。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Nick McKeown
  - Balaji Prabhakar
  - Nickolai Zeldovich
  - Ramesh Chandra
companies_orgs:
  - Greer
  - Nicira
  - Stanford University
  - MIT
products_models:
  - OpenFlow
  - DataDog
media_books: []
status: evergreen
---
<!-- chunk 1/8 -->

### 开场与运维系统的复杂性

AI 所生存的世界完全是数字化的，而现实世界并非如此，这两者之间并不必然相同。

<details><summary>Original English</summary>
The world that the AI lives in is all digital and there's the actual world and like those things are not necessarily the same.
</details>

>> 当我们开始将 AI 用于编程时，它还只是代码自动补全。当时谁也不知道在多大程度上能真正用 AI 构建复杂的软件，然后它基本上突破了预期，因为我们能够在系统中对越来越高的复杂性进行建模。

<details><summary>Original English</summary>
>> When we started doing AI for coding, it was autocomplete. Nobody really knew to what extent you can actually build complex software using AI and then it basically broke through the expectations because we were able to model more and more complexity in the systems.
</details>

>> 我只是不知道运维是否以同样的 [音乐] 方式受到约束。甚至去哪里找数据来学习如何构建一个理解所有运维环节的系统？我的设想是，我们拥有所有的数据。我认为问题可能在于复杂性，以及在多大程度上你能将你所描述的运维内容，转化为 AI 可以推理的形式？长久以来，仅仅依靠人类来管理分布式集群，这就是其中的灰色秘密。你认为我们现在是否已经到了可以用 AI 来运行其中某项服务的地步？我认为已经有足够的基础能够……

<details><summary>Original English</summary>
>> I just don't know if operations is constrained in the [music] same way. Where's even the data to learn how to like build a system that understands like all of the operations? My assumption is that we have all the data. The question I think is maybe about complexity and like to what extent can you take the things that you've described that are operational and convert them into something that an AI can reason about the dirty secret for the longest time of running like a distributed cluster with just human beings managing it. Do you think we're at a spot where you could like use AI to run one of these services? I think that there's enough to be able to
</details>

### 嘉宾介绍与斯坦福回忆

好，Jad，感谢来参加我的播客。对于那些不了解的人，Jaden 是 Greer 的 CEO，不过我们当年也在读研时的同一个课题组。我第一次见到你的时候，我们来了一位新学生。[笑声]

<details><summary>Original English</summary>
All right, Jad. thanks for joining me on the podcast. For those of you who don't know, Jaden is the CEO of Greer, but also we uh went to grad school in the same group. And when I first met you, I we we had a new student. [laughter]
</details>

>> 我走进办公室，看见里面有一个摩托车头盔和一包万宝路香烟。[笑声] 我心想：“这家伙肯定酷毙了。” 所以我的问题是，你当年的那份酷劲儿都去哪儿了？[笑声] 问题一，[笑声]

<details><summary>Original English</summary>
>> I I walked into the office and there was a motorcycle helmet and a pack of Maros. [laughter] I'm like, "This guy must be unbelievably cool." So my question is is what happened to all your coolness? [laughter] Question number one, [laughter]
</details>

>> 也许……也许只为了补充背景，先简要介绍一下你的经历。只是跟正在收听的各位说明一下，你们知道的，Jad 是我认识的最优秀的系统思维者之一。我很喜欢和他交流。我们将从系统角度深入探讨工程，以及 AI 如何对我们产生影响。我们会深入探讨，尤其是涉及到像运维这样的事情时，但为了建立基础，或许可以先讲讲你的背景。

<details><summary>Original English</summary>
>> maybe maybe maybe just for a context, maybe give give um a quick um uh overview of your background. So just just for those that are listening, you know, dad is one of the best systems thinkers I know. I love talking to him. We're going to go kind of to a deep dive of like engineering from a systems perspective and how AI is impacting us. We're going to kind of especially when it comes to things like operations, but just to ground it maybe a bit about your background.
</details>

>> 没问题。[嗤笑] 你见到我的时候，正是我酷劲儿的巅峰期之一。

<details><summary>Original English</summary>
>> Sure. [snorts] So, uh, you met me at, uh, one of the peaks in my coolness.
</details>

>> 是的，你当时非常酷。[笑声]

<details><summary>Original English</summary>
>> Yeah, you're very cool. [laughter]
</details>

>> 摩托车加上万宝路香烟。

<details><summary>Original English</summary>
>> Motorcycle and Marorrow cigarettes.
</details>

>> 我记得当时心里想：“哇，抽烟甚至还合法吗？” [笑声] 感觉太违和了。

<details><summary>Original English</summary>
>> I remember thinking I'm like, "Wow, are cigarettes even legal?" [laughter] It was like so discordant.
</details>

>> 我记得有一天 Nick 看到我在 Gates 大楼外面抽烟，看着我，露出这样的神情：[笑声] “天啊……” Nick McKeown 是我们的导师。Gates 是那栋大楼的名字。

<details><summary>Original English</summary>
>> I remember Nick seeing me one day smoking outside of uh outside of Gates and looking at me and going like, [laughter] "G Nick Bun is our adviser. Gates was the the building." Yeah,
</details>

>> 顺便说一句，我最喜欢的一件事……不知道你还记不记得 Balaji Prabhakar 教授？当然。

<details><summary>Original English</summary>
>> actually one of my favorite thing I don't do you remember Balaji Prabakar the professor of course
</details>

>> 关于他我最喜欢的一点就是他也抽烟。我就觉得他是唯一一个抽烟的教授，[笑声] 我只是觉得这太棒了。

<details><summary>Original English</summary>
>> my favorite thing about him is that he smoked I was like the [laughter] only professor I just thought it was like great
</details>

>> 说明一下，我现在已经不抽烟了。

<details><summary>Original English</summary>
>> just to be clear I don't smoke anymore
</details>

>> 抽不动了，到了这个年纪人到中年抽不来了。[笑声] 不过我们看看，当时我和你一起在斯坦福。你一直是我仰望的人，我会觉得：嘿，

<details><summary>Original English</summary>
>> no too old too middle-aged for that now [laughter] um but let's see so you know I went to Stanford with uh with you you were always the guy I had to look into to look to look up to and be like hey
</details>

>> 这就是我长大后想成为的人。

<details><summary>Original English</summary>
>> this is the guy I want to be when I grow up
</details>

>> 我当时……我想我比你早入学四年，所以我比你资深。

<details><summary>Original English</summary>
>> I was I think it was I it was a I started started four years before you did. So I was ahead
</details>

### 学术研究与职业路径转变

>> 所以你比我早了四年。你比我早毕业好一阵子。你去创办了 Nicira。而我留下来了，

<details><summary>Original English</summary>
>> and so you were four years ahead of me. You graduated a while ahead of me. You went and started Nicer. I stayed and
</details>

>> 继续留在那里做 OpenFlow 的工作。从安全角度参与构建了硬件方面的一堆东西。实际上，

<details><summary>Original English</summary>
>> stuck around worked more on OpenFlow. Helped uh build a bunch of stuff on the hardware side from a security perspective. Actually,
</details>

>> 我在那儿参与过的最有趣的项目之一，是我构建了人们当时正在考虑采用的第一批 SHA-3 硬件实现。我用硬件构建了它们，[嗤笑] 来验证它们能否正常工作之类的，这也是我毕业论文的项目之一。那很有意思。

<details><summary>Original English</summary>
>> one of the one of the, you know, most fun projects that I worked on there was uh I built the first set of uh Shaw 3 implementations that people were considering using and um I built them in hardware [snorts] to kind of show whether they work or not and whatever for one of my for uh one of my projects for my thesis. That was fun.
</details>

>> 是的，是的，很酷。[清喉咙]

<details><summary>Original English</summary>
>> Yeah. Yeah. Cool. [clears throat]
</details>

然后过了一阵子我发现，我其实不喜欢网络，因为网络说白了就是把比特从一个地方搬运到另一个地方。

<details><summary>Original English</summary>
And then I decided after a while that I actually don't like networking because it's just about moving bits from one place and putting them in another place.
</details>

>> 能有多难呢？[笑声]

<details><summary>Original English</summary>
>> How hard can that be? [laughter]
</details>

>> 我觉得这取决于你在哲学上是否认同它具有深度。大多数人认为它不深，我认为它非常深奥。[笑声]

<details><summary>Original English</summary>
>> I think that would have to either be philosophically aligned that it's deep or not. Most people assume it's not. I think it's very deep. [laughter]
</details>

>> 我是说它确实有意思的地方，但归根结底对我来说……它算不上……

<details><summary>Original English</summary>
>> I mean there's something interesting about it, but ultimately to me that's like it's not
</details>

>> 是的，提不起你的兴趣。

<details><summary>Original English</summary>
>> Yeah. It doesn't do it for you.
</details>

>> 是的。后来我其实去了 MIT 做博士后，跟着 Nickolai Zeldovich，他也是个极具深度、极其聪明的人。

<details><summary>Original English</summary>
>> Yeah. Um and then uh I actually went and did a posttock at MIT with Nikolai Zelda who's also amazingly deep and super smart.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Um
</details>

>> 他非常杰出。

<details><summary>Original English</summary>
>> he's phenomenal.
</details>

>> 当时我做了一些应用安全方面的工作。后来基于我和 Ramesh Chandra 在那里合作的一些研究创办了一家公司，他当时是一名博士生。但最终这项技术出现得太早了。

<details><summary>Original English</summary>
>> I did some application security work at the time. Started a company um based off some of the research I had worked on with Ramsh Chandra over there who was a PhD student at the time and ultimately technology was too early.
</details>

>> 是什么样的技术？

<details><summary>Original English</summary>
>> What was it?
</details>

我们做的事情是……其实很多工作实际上主要来自 Ramesh，他的博士研究课题是：如果你遭到了攻击并被利用漏洞入侵，你是否可以通过把与该应用程序相关的整个系统的状态进行回滚，然后将其迁移应用到修补后的应用程序版本上，从而消除入侵利用并恢复？

<details><summary>Original English</summary>
So what we did was um well you know ultimately a lot of the work was actually really Romeshes and his PhD was on well hey if you get attacked and you get exploited can you recover from that by rolling back the state of the whole world that's related to that application and then roll it over on top of a patched version of the application to remove the exploit.
</details>

>> 是的。于是我们在现实世界中尝试这么做，然后我们发现，哎呀，这听起来太难了。[笑声] 这其实跟我们正在聊的内容有些关联，[嗤笑] 也就是在多大程度上你能够真正界定运维系统的状态边界，我认为这是极其困难的，但……

<details><summary>Original English</summary>
>> Yeah. And so we started doing that in the real world and we're like ah that sounds really hard. [laughter] It's actually kind of relevant to what we're talking [snorts] about which is like to what extent can you actually bound the state for like operational systems which I would argue is very hard but
</details>

>> 是的，我……我们差点就把它做成功了。[笑声]

<details><summary>Original English</summary>
>> yeah I we almost got it working [laughter]
</details>

>> 差点成功了。

<details><summary>Original English</summary>
>> almost
</details>

我感觉对于所有长尾领域来说，这也是为什么聪明人会陷入像捕蝇纸一样的陷阱：你看到了一点进展，但你其实是在做渐近线式的挣扎。不过扯远了，我们继续。继续聊你的经历……

<details><summary>Original English</summary>
I feel like for all longtail disciplines this is why people get in like the fly track for smart people is like you see a bit of progress but you're as toing but anyways I digress. Let's keep going. Let's keep going with your uh
</details>

### 从风投到产品与可观测性洞察

>> 后来我加入了 AppDynamics。我在那里待了大约三年半。公司规模从大概 200 人增长到 2,000 人。后来被思科收购了。我当了一天的思科员工。然后我说……接着你就说：“Jad，

<details><summary>Original English</summary>
>> So then I joined App Dynamics. I was there for about three and a half years. They went from about 200 people to 2,000 people. Got acquired by Cisco. I was a Cisco employee for one day. And I said, and then you're like, Jad,
</details>

>> 我懂。我 [笑声] 很喜欢你。来跟我一起共事吧。

<details><summary>Original English</summary>
>> I know. I [laughter] love you. Come work with me.
</details>

>> 来跟我一起做风险投资吧。”

<details><summary>Original English</summary>
>> Come do this VC thing with me.
</details>

>> 我心想：“这搞什么……

<details><summary>Original English</summary>
>> I'm like, what the
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 什么是风险投资？什么鬼？我是一个架构师，我做的是工程类的事情。你到底在……” 他说：“太棒了。

<details><summary>Original English</summary>
>> What What is VC? What? Like I'm an architect. I do like engineering stuff. What do you He's like, great.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你知道得越少越好。”

<details><summary>Original English</summary>
>> The less you know, the better.
</details>

>> 确实，这完全就是你当年说的话。

<details><summary>Original English</summary>
>> Yeah. Literally what you said.
</details>

>> 确实如此。然后我来这里上班的第一天，你对我说：“慢下来。” [笑声]

<details><summary>Original English</summary>
>> It's true. And then the first day I started here, you said slow down. [laughter]
</details>

>> 实际上，那些从运维一线……从实际的运营工作转到风投行业的人，往往需要对大脑进行大量的重塑。

<details><summary>Original English</summary>
>> It's actually people that move from operate like from like actually an operating world to VC. It requires a lot of reworking the brain.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是啊。顺便说一句，就像从博士转向实际运营工作一样。你必须得把被损害的脑子纠正回来。[笑声]

<details><summary>Original English</summary>
>> Yeah. Just like going from a PhD to operating by the way. Like you have to like undo the brain damage. [laughter]
</details>

>> 这就是我的经历。

<details><summary>Original English</summary>
>> This is my experience.
</details>

>> 原来现实世界是这样的。

<details><summary>Original English</summary>
>> This is what real world is like.
</details>

>> 我明白。

<details><summary>Original English</summary>
>> I know.
</details>

>> 接着我在风投这边待了几年，和你一起做了不少工作。那是一段非常开心的时光。和许多优秀的人一起工作，比如 Jennifer、Mark 和 Ben。

<details><summary>Original English</summary>
>> And then um I stayed here for a couple of years. Did a bunch of work with you. It was a really fun time. Worked with a lot of great people like Jennifer, Mark, and Ben.
</details>

>> Satish。

<details><summary>Original English</summary>
>> Satish.
</details>

>> Satish。Matt 当时……在我快离开的时候，他刚好在那儿。

<details><summary>Original English</summary>
>> Satish. Um Matt was uh here when I first uh what almost towards the end when I was leaving.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 之后我加入了 Imply 担任他们的首席产品官。帮助他们组建了工程和产品团队。规模从大约 15 人扩张到涵盖产品、工程、信息安全和设计的 90 多人。大约三年后，我负责的每个业务模块都有了负责人，而我每天基本上只是闲坐着到处协调和开会，所以想去做点别的事情。于是我离开了，之后开始与许多工程技术负责人交流，了解他们面临的问题以及他们想做的事情。当时是在 2023 年，所有人都在说：“嘿，我们正在试图削减开支。” 问他们：“你们的钱都花在什么地方了？” 所有人都会说可观测性。你知道，其实最开始是基础设施，然后是可观测性。于是我开始研究这个问题，试图弄明白到底是怎么回事，为什么大家觉得它太贵了？[清喉咙] 结果发现有几方面的原因。首先，人们在可观测性上的花费，大约占到了他们在基础设施上花费的 5% 到 20% 之间。但归根结底，他们真正想买的是可靠性。他们想要购买的是可靠性，以及……

<details><summary>Original English</summary>
>> And then um and then joined Apply as their chief product officer. Um helped them build uh their engineering product teams. Kind of scaled from about engineer like 15 people to over 90 across product engineering infosac and design. And after about 3 years, um, I kind of had a head for each one of these pieces that I owned and I kind of was sitting around just coordinating and doing meetings all day and wanted to go do something else. So left and then um started talking to a lot of engineering leaders about the problems that they're facing and what they're trying to do. Everybody at the time, this was in 23, everybody was saying, "Hey, we're trying to reduce spend." And ask them, "What are you spending money on?" Everybody would say observability. And you know well first actually it was infrastructure and then observability. And so I started looking at that problem trying to understand like what is why do people think it's too expensive? [clears throat] Turns out there's a few things. First people were spending somewhere between 5 and 20% of what uh they spend on infrastructure on observability. But ultimately what they were really trying to spend it on was reliability. They wanted to buy reliability and um
</details>

>> 开销的可靠性？比如开销的可预测性？

<details><summary>Original English</summary>
>> of spend like predictability of spend
</details>

>> 是他们基础设施和应用程序的可靠性。

<details><summary>Original English</summary>
>> reliability of their infrastructure and applications.
</details>

>> 懂了。懂了。懂了。

<details><summary>Original English</summary>
>> I see. I see. I see.
</details>

>> 没错。所以他们把钱投在可观测性上，作为可靠性的一种替代手段。长久以来，你花的钱越多……

<details><summary>Original English</summary>
>> Right. And so they were putting money into observability as a proxy for reliability. And for the longest time, the more money you spend,
</details>

>> 越……

<details><summary>Original English</summary>
>> the more
</details>

<!-- chunk 2/8 -->

### 可观测性演进与上游信号提取

你所获得的可靠性。但随着架构发生变化并演化为规模小得多、垂直整合度高得多的微服务，每一层收集的数据量都膨胀了。可观测性的市场渗透率深得多，你所收集的数据量——以及可观测性的成本——实际上开始增长得比你产出的功能单元还要快。而且……每在可观测性上多花一美元所带来的边际可靠性增长正在趋于平缓。

<details><summary>Original English</summary>
reliability

 you

 got

 out.

 But

 as





architectures

 changed

 and

 turn

 into





microservices

 that

 are

 much

 smaller,





that

 are

 much

 more

 vertically





integrated.

 The

 volume

 of

 data

 that's





being

 collected

 at

 every

 layer

 expanded.





there

 was

 much

 deeper

 market

 penetration





for

 observability

 and

 kind

 of

 the

 uh





volume

 of

 data

 that

 you're

 collecting





and

 the

 cost

 of

 observability

 was





actually

 starting

 to

 grow

 faster

 than





the

 units

 of

 function

 that

 you're





outputting.

 And

 um

 and

 the

 marginal

 rate





of

 or

 like

 the

 marginal

 increase

 in





reliability

 for

 every

 additional

 dollar





you

 were

 spending

 on

 observability

 was





just

 flattening

 out.
</details>

[gasps]

嗯，所以这就是为什么人们觉得它昂贵，但人们仍然愿意为可靠性支付 5% 到 20%。所以问题就在于，我们是否真能解决那个问题，并带回……那种可靠性的提升，那种边际可靠性的提升，

<details><summary>Original English</summary>
[gasps]





Um,

 and

 so

 that's

 why

 people

 thought

 it





was

 expensive,

 but

 people

 were

 still





willing

 to

 pay

 5

 to

 20%

 on

 reliability.





And

 so

 the

 question

 was

 like,

 can

 we





actually

 solve

 that

 problem

 and

 bring





back

 the

 um

 that

 increase

 in





reliability,

 that

 marginal

 increase

 in





reliability,
</details>

>> 不一定是通过在可观测性上花更多钱，而是通过某种别的方式。所以当时的想法就是，好吧，太好了。如果我们能弄清楚什么是信号，什么是噪声，我们是否真能转变你收集的可观测性数据——这些数据在当前大多是无关紧要的杂质、大多只是买个保险——并在上游进行那种信息提取，在上游做你需要做的一切，并最终能够在下游大幅降低可观测性的成本。如果你能在上游实时提取那个信号，那么第一你可以降低成本，但第二你现在可以把它输入到其他系统中，之后用它来驱动可靠性运维

<details><summary>Original English</summary>
>> not

 necessarily

 by

 spending

 more

 money





on

 observability,

 but

 some

 other

 way.





And

 so

 the

 thinking

 was

 like,

 okay,





great.

 If

 we

 can

 figure

 out

 what

 is

 the





signal,

 what

 is

 noise,

 can

 we





actually

 turn

 the

 observability

 data





that

 you're

 collecting

 that

 it's

 mostly





fluff

 and

 mostly

 insurance

 at

 this

 point





and

 do

 that

 kind

 of

 extraction

 of





information

 upstream,

 do

 whatever

 you





need

 upstream

 and

 be

 able

 to

 ultimately





massively

 reduce

 the

 cost

 of





observability

 downstream.

 And

 if

 you

 can





extract

 that

 signal

 in

 real

 time





upstream

 then

 you

 can

 one

 reduce

 the





cost

 but

 two

 you

 can

 now

 feed

 it

 into





other

 systems

 and

 use

 it

 for

 driving





reliability

 operations

 afterwards
</details>

[clears throat]

>> 当时在远方，有一种被称为 AI 的事物正在进入视野，我们当时就觉得，好吧，太好了，如果我们身处数据流之中并且正在提取信号，那我们就处在向未来将要出现的任何事物进行输送的战略位置上，因为那将是必不可少的。

<details><summary>Original English</summary>
[clears throat]





>> and

 the

 distance

 at

 the

 time

 there

 was





something

 that

 was

 called

 AI

 coming





coming

 into

 the

 picture

 and

 we're

 like





well

 great

 if

 we

 are

 in

 the

 data

 stream





and

 we're

 extracting

 the

 signal

 then

 we





are

 in

 a

 strategic

 position

 to

 feed

 that





to

 whatever

 is

 going

 to

 come

 in

 the





future

 because

 that's

 going

 to

 be





necessary.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以那就是我们构建出来的东西。嗯，Greer 帮助各家公司——你知道，我们最初是帮助他们大幅减少遥测上的支出。所以你把我们放在数据流中，即插即用，把数据传过来，就能降低 90% 的成本。

现在我们正在构建第二层，把那些信号输入到 AI 层，该层现在会去进行故障排查，弄清楚事情何时出错并加以修复。我很想聊聊你在 AI 通常如何改变研发方面的经验，比如很多人被问到这个问题，很多人回答，但我总觉得就像那种工程师眼中的工程师，比如你做过架构师，你管理过产品，你带过工程团队，实际上你现在的公司有多大，有多少人？

<details><summary>Original English</summary>
>> And

 so

 that's

 what

 we

 built.

 And

 um

 so





Greer

 helps

 companies,

 you

 know,

 we





started

 with

 helping

 them

 reduce

 their





spend

 on

 telemetry

 massively.

 And

 so

 you





put

 us

 in

 the

 data

 stream,

 plug

 and





play,

 pass

 the

 data

 through,

 reduce

 your





cost

 by

 90%.





And

 um

 and

 now

 we're

 building

 out

 that





second

 layer

 where

 we're

 feeding

 those





signals

 into

 the

 AI

 layer

 that's

 now





going

 and

 troubleshooting

 and

 figuring





out

 when

 things

 are

 going

 going

 wrong





and

 fixing

 them.

 I'd

 love

 to

 just

 talk





through

 kind

 of

 your

 experience

 on

 how





AI

 is

 changing

 dev

 generally

 which

 is





like

 a

 lot

 of

 people

 get

 asked

 this





question

 a

 lot

 of

 people

 answer

 but

 I





just

 feel

 like

 kind

 of

 like

 the





engineers

 engineer

 like

 you've

 been

 an





architect

 you've

 run

 product

 you

 run





engineering

 teams

 like

 you

 know

 like





actually

 how

 big

 is

 your

 company

 now

 how





many

 people
</details>

>> 我们有十……

<details><summary>Original English</summary>
>> we're

 t
</details>

>> 是的，所以你知道，而且你带有一支……我是说，你在用一支相对高效的团队构建大量的软件，所以

<details><summary>Original English</summary>
>> yeah

 so

 you

 know

 and

 you've

 got

 a

 I

 mean





you're

 building

 a

 lot

 of

 software

 with

 a





relatively

 efficient

 team

 so
</details>

>> 也许只是高维概括一下，比如你……好吧，如果你是像你这样的资深工程师，你知道，拥有架构经验，比如你认为人们看到了什么样的收益？也许可以聊聊你是如何使用 AI 的、你实际看到了哪些收益、技术栈是什么、你的流程是什么、你是如何思考它的。

<details><summary>Original English</summary>
>> maybe

 just

 a

 highle

 sketch

 on

 like

 you





Well,

 if

 you're

 a

 senior

 engineer

 like





you,

 you

 know,

 that

 has

 architectural





experience,

 like

 like

 what

 sort

 of

 gains





do

 you

 think

 people

 are

 seeing?

 Maybe





talk

 through

 like

 how

 you

 use

 AI,

 what





gains

 you're

 actually

 seeing,

 what

 is





the

 stack,

 what

 is

 your

 process,

 how

 you





think

 about

 it.
</details>

### AI 在工程团队中的演进与 harness 交互

>> 所以也许我可以给你一个历史视角的观察，讲讲在带团队等方面一直在发生什么。

<details><summary>Original English</summary>
>> So

 maybe

 I

 can

 give

 you

 like

 a





historical

 view

 of

 like

 what's

 been





happening

 in

 terms

 of

 like

 running

 a





team

 and

 so

 on.
</details>

>> 所以在我们刚开始的时候，AI 某种程度上还停留在自动补全，

<details><summary>Original English</summary>
>> And

 so

 what

 you

 know

 when

 we

 first





started

 AR

 was

 still

 kind

 of





autocomplete,
</details>

>> 对吧？我记得当时我们在用 Copilot 和 IntelliJ，我们当时觉得，天哪，看，它把这些测试自动补全了，

<details><summary>Original English</summary>
>> right?

 I

 remember

 like

 at

 the

 time

 we





were

 using

 uh

 co-pilot

 and

 uh

 intelligj





and

 we're

 like

 oh

 my

 god

 look

 it





autocomp

 completed

 these

 tests
</details>

>> 我们觉得，对啊，但这只是自动补全。然后事情非常迅速地开始演变，而我所注意到的是，真正优秀的工程师能够以某种方式把它融入到自己的工作流中，在那种方式下，AI 开始反过来训练他们。

<details><summary>Original English</summary>
>> uh

 we're

 like

 yeah

 but

 it's

 just





autocomplete

 and

 very

 rapidly

 things





started

 evolving

 and

 what

 what

 I've





noticed

 is

 that

 really

 good

 engineers





are

 able

 to

 somehow

 put

 it

 into

 their





workflows

 in

 a

 way

 where

 they

 the

 AI





starts

 training

 them.
</details>

哦，很有意思。

<details><summary>Original English</summary>
Oh,

 interesting.
</details>

>> 在如何与它对话、如何从它那里获得最佳结果方面。

<details><summary>Original English</summary>
>> In

 terms

 of

 like

 how

 to

 talk

 to

 it,

 how





to

 get

 the

 best

 out

 of

 it.
</details>

>> 顺便问一句，你认为这是特定于模型的吗？也就是说，你是学会了从大体上使用 AI，还是说你对某个特定模型变得高效？

<details><summary>Original English</summary>
>> And

 what

 I

 do,

 as

 an

 aside,

 do

 you

 think





that's

 model

 specific?

 Like

 is

 it

 do

 you





learn

 how

 to

 use

 AI,

 you

 know,

 writ





large

 or

 do

 you

 get

 efficient

 at

 a

 given





model?
</details>

>> 我认为不同模型确实会带来一些细微差别。嗯，看你的推文我确信你已经[笑声]……嗯，这里面有细微差别，但是存在一种与 AI 协同工作的方式。而且我认为也存在一种与不同 harness 协同工作的方式，我认为，比如我们尝试过使用 Open Code 或者不同的 harness，或者使用 Codex 对比 Claude、比如 Claude Code，不同的工具在管理上下文、深入思考问题、或者何时启动合适的子代理以及给它指令（比如提示词的类型）方面，各有不同的方式。比如……

<details><summary>Original English</summary>
>> I

 think

 there's

 like

 some

 nuances

 that





different

 models

 bring.

 Um,

 I'm

 sure





looking

 at

 your

 tweets

 you've

 [laughter]





um

 there's

 like

 nuances,

 but

 there

 is

 a





a

 way

 to

 work

 with

 AI

 and

 like





I

 think

 that

 there's

 also

 a

 way

 to

 work





with

 different

 harnesses

 and

 I

 think





like

 you

 know

 we

 tried

 for

 example

 using





open

 code

 or

 like

 different

 harnesses

 or





like

 using

 codecs

 versus

 claw

 like

 claw





code

 like

 different

 ones

 have

 different





ways

 of

 managing

 context

 or

 thinking





through

 problems

 or

 when

 to

 spin

 up

 the





right

 sub

 agents

 and

 what

 to

 tell

 it





like

 the

 kind

 of

 prompts

 like

 for





example
</details>

>> 对于 Claude Code，我发现如果我不告诉它别启动，

<details><summary>Original English</summary>
>> uh

 with

 cloud

 code

 I

 find

 that

 if

 I





don't

 tell

 it

 don't

 spin

 up
</details>

>> 你知道，20 个 fable agent 去做基础研究，它就会去启动 20 个 fable agent 做研究，烧光你所有的 token。所以像很多这类的东西，你开始了解 harness 和模型，以及它们彼此之间如何交互，进而它们又如何与外面的世界交互。但我扯远了，我只是想说……

在我脑海里，这差不多就是我开始注意到的：有些人能够去适应、学习并以那种方式去做，嗯，而另一些人则没有那么强的适应力。

<details><summary>Original English</summary>
>> you

 know

 20

 fable

 agents

 to

 do

 basic





research

 it'll

 go

 and

 spin

 up

 20

 fable





agents

 to

 do

 research

 and

 burn

 all

 your





tokens

 and

 so

 like

 a

 lot

 of these

 things





kind

 of

 you

 start

 learning

 about

 the





harness

 and

 the

 and

 the

 models

 and

 like





how

 they

 interact

 with

 each

 other

 and





then

 how

 they

 can

 interact

 with

 the

 rest





of

 the

 world

 but

 I

 digress

 like

 I'm

 just





going





in

 my

 mind

 like

 this

 is

 kind

 of

 what

 I





started

 noticing

 is

 that

 like

 some





people

 were

 adapting

 and

 learning

 and





kind

 of

 doing

 it

 that

 way

 um

 and

 others





weren't

 as

 adaptive.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 人才差距与认知复杂度

>> 随着我们开始招募更多人加入团队，普通工程师与真正优秀工程师之间的差距直接放大了 10 倍。

<details><summary>Original English</summary>
>> And

 then

 as

 we

 started

 hiring

 more





people

 into

 the

 team

 that

 disparity





between

 you

 know

 okay

 engineers

 and





really

 good

 engineers

 just

 multiply

 10x.
</details>

>> 那你能否预测谁会……你能预测谁会表现好吗？是优秀的工程师变得更优秀，而不好的工程师没有变好，还是真的是这样？好的。是的。所以，如果你是一个优秀的工程师，你只会变成一个更优秀的优秀工程师。并不是说某些不好的工程师突然之间就变成了优秀的工程师。

<details><summary>Original English</summary>
>> Was

 it

 can

 you

 predict

 who

 will

 who





could

 you

 predict

 who

 would

 be

 good?

 Was





it

 like

 good

 engineers

 got

 better

 and





bad

 engineers

 didn't

 or

 was

 it

 it





really?

 Okay.

 Yeah.

 So,

 like

 if

 if





you're

 a

 good

 engineer,

 you're

 just

 a





better

 good

 engineer.

 It's

 not

 like





there's

 some

 like

 bad

 engineers

 all

 of a





sudden

 became

 good

 engineers.
</details>

>> 不是。

<details><summary>Original English</summary>
>> No.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 不是，不是。归根结底总是这样：你必须真正从根本上理解整套体系架构，因为你的大脑能承受的复杂度越高，你就越能拆解任务并进行分配。我认为这实际上可能是一个非共识观点，比如……我的意思是我有时确实听到过，但那种认为优秀的工程师会变得优秀得多……[笑声]那些人则要少得多，而且你发现这几乎是普遍成立的。

[叹气与喘气] 我是说，看，我的团队仍然很小，我们还没有在 100 个人身上做过验证。

<details><summary>Original English</summary>
>> No.

 No.

 It

 it

 always

 ends

 up

 being

 like





you

 have

 to

 really

 understand

 ultimately





the

 the

 setup

 because

 the

 more





complexity

 that

 your

 brain

 can

 handle,





the

 more

 you

 can

 break

 down

 the

 tasks





and

 kind

 of

 assign

 them.

 I

 think

 this





might

 actually

 be

 uh

 like

 non-

 consensus





opinion

 that

 like

 uh

 I

 mean

 I

 I

 do

 hear





it

 sometimes

 but

 the

 idea

 that

 like

 the





better

 engineers

 like

 are

 much

 better





[laughter]

 those

 are

 are

 less

 and

 you





you

 found

 this

 to

 be

 pretty

 universally





true

 [sighs and gasps]





I

 mean

 look

 my

 team

 is

 still

 small

 we





haven't

 done

 it

 across

 100

 people
</details>

>> 是的。[清嗓子]

<details><summary>Original English</summary>
>> yeah

 [clears throat]
</details>

>> 根据我的经验，对于我们所做的事情来说情况确实如此，因为我们构建的是分布式系统和分布式算法，你的大脑必须能够承受这种复杂度，因为……

<details><summary>Original English</summary>
>> in

 my

 experience

 for

 the

 things

 that

 we





do

 that

 is

 the

 case

 because

 we

 build





distributed

 systems

 and

 distributed





algorithms

 and

 like

 your

 brain

 has

 to





handle

 the

 complexity

 because

 like
</details>

>> AI 做不来。

<details><summary>Original English</summary>
>> AI

 doesn't

 do

 it,
</details>

>> 对吧？对。对。对。

<details><summary>Original English</summary>
>> right?

 Yeah.

 Yeah.

 Yeah.
</details>

### 语法与语义的区别

>> 所以对于我们解决的问题，[清嗓子并咳嗽] 现有的模型其实没有一个能真正把我们所做的事情想透彻。

<details><summary>Original English</summary>
>> And

 so

 for

 the

 problems

 that

 we

 solve,





[clears throat and cough]





none

 of

 the

 models

 can

 actually

 think





through

 the

 things

 that

 we

 do.
</details>

>> 比如有很多，举个例子，我们有一个查询转换层。我们刚才正好在聊查询优化。

<details><summary>Original English</summary>
>> Like

 there's

 a

 lot

 of

 for

 example,

 we





have

 a

 query

 translation

 layer.

 We

 were





just

 talking

 about

 query

 optimization.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以你必须真正理解查询的语义，以及如何探寻到查询的语义，然后再向模型解释清楚，

<details><summary>Original English</summary>
>> And

 so

 you

 have

 to

 really

 understand





the

 semantics

 of

 the

 query

 and

 how

 to





get

 to

 the

 semantics

 of

 the

 query

 and





then

 explain

 it

 to

 the

 model
</details>

>> 然后让模型去构建转换层，比如说。是的。那么对于正在收听的、可能在计算机科学方面没有那么深背景的人来说，你说的“语义”是什么意思？[笑声]

<details><summary>Original English</summary>
>> and

 then

 have

 the

 model

 go

 and

 build

 the





translation

 layer,

 let's

 say.

 Yeah.

 So





for

 for

 for

 the

 people

 that

 are





listening

 that

 that

 may

 not

 be

 so

 deep





in

 computer

 science,

 what

 do

 you

 mean

 by





semantics?

 [laughter]
</details>

>> 额，语义实际上就是事物的含义。比如狗这个语义——dog 这个词的语义——就是指那种实际上用四条腿走路并汪汪叫的动物。

<details><summary>Original English</summary>
>> Uh

 so

 semantics

 are

 really

 the

 meanings





of

 things.

 Like

 the

 semantic

 of

 a

 dog

 of





the

 word

 dog

 is

 the

 animal

 that

 actually





walks

 on

 four

 legs

 and

 barks.
</details>

>> 而语法则是指它仅仅是三个……一个三个字母组成的词，

<details><summary>Original English</summary>
>> And

 the

 syntax

 is

 the

 fact

 that

 it's





just

 three

 a

 threeletter

 word
</details>

>> 它有三个不同的字母。词的形状是不同的，那种形状在不同的词之间可以不一样。[清嗓子]

嗯，但不同的词实际上也可以表示相同的事物。因此它们可能具有相同的语义，但它们可能有不同的语法。所以 dog 和 puppy 的语义可能会稍微有点不同。

[清嗓子] 它们指的是同一个，

<details><summary>Original English</summary>
>> and

 it

 has

 three

 different

 letters.

 the





shape

 of

 the

 word

 is

 different

 and

 that





shape

 can

 be

 different

 between

 different





words.

 [clears throat]





Um,

 but

 different

 words

 can

 actually





also

 mean

 the

 same

 thing.

 And

 so

 they





might

 have

 the

 same

 semantics,

 but

 they





might

 have

 a

 different

 syntax.

 So

 a

 dog





and

 a

 puppy

 might

 be

 slightly

 different





semantics.





[clears throat]

 They

 refer

 to

 the

 same,
</details>

>> 但它们仍然被称为狗。所以针对计算机科学，我非常简单描述它的方式就是：语法，你知道，就像是你敲击的字符，而语义则是机器实际执行的操作，对吧？所以它就像是……就像是系统的实际运行时属性。

<details><summary>Original English</summary>
>> but

 they're

 still

 called

 a

 dog.

 So

 the





way

 that

 and

 just

 for

 for

 like

 computer





science,

 the

 way

 that

 I

 describe

 it

 very





simply

 is

 syntax,

 you

 know,

 is

 like

 the





the

 characters

 you

 type

 and

 semantics

 is





what

 the

 machine

 actually

 does,

 right?





And

 so

 it's

 like

 like

 the

 actual

 runtime





properties

 of

 the

 the

 system.
</details>

>> 所以你学了计算机科学，我学了电子工程，[笑声]

<details><summary>Original English</summary>
>> So

 you

 did

 computer

 science,

 I

 did





electrical

 engineering,

 [laughter]
</details>

>> 你成了计算机科学家，我成了风险投资人。所以[笑声]就是这样。

<details><summary>Original English</summary>
>> you

 became

 a

 computer

 scientist

 and

 I





became

 a

 VC.

 So

 [laughter]

 there

 we

 go.
</details>

>> 问题就出在这儿。

<details><summary>Original English</summary>
>> That's

 the

 problem.
</details>

<!-- chunk 3/8 -->

我明白了。

<details><summary>Original English</summary>
I see.
</details>

对。

<details><summary>Original English</summary>
Yeah.
</details>

>> 不管怎样，我只是想让在听的人明白，你看，有实际的语法，也就是写代码本身。嗯，当你谈论语法时，你只是在谈论代码本身。然后当你谈论语义时，你实际上是在说你有一台机器来解释那段代码，不管它是编译好的还是没编译好的。而那台机器会执行某些操作。语义就是机器实际做的事情。这些东西显然是非常不同的，对吧？例如，有些语义你甚至无法通过查看语法来推导出来，对吧？你不知道机器将要做什么，因为无论如何你都得去测试它，你得测试它，你知道，当你测试它时，它可能会出现各种各样不同的情况。一个非常经典的例子就是 SQL。比如你可以写某个 SQL 查询，但它实际性能如何、执行多长时间，完全取决于比如架构是什么样，或者数据库里的数据是什么样等等。

<details><summary>Original English</summary>
>> Anyways, I just wanted for people that are that are listening, I just want to understand like there's the actual syntax which is writing the code, you know. Um, and then when you're talking about syntax, you're just talking about the code itself. Then when you talk about semantics, you're literally talking about you have a machine that interprets that code whether it's compiled or not. And that machine does something. The semantics is what the machine actually does. And these things are, you know, clearly very different, right? Like so for example, some semantics you can't even derive by looking at the syntax, right? you don't know what the machine is going to do because whatever you kind of have to test it you have to test it you know like and it can go all sorts of different ways when you test it and like a very classic version of this is is um uh is SQL for example like you can write you know some SQL query but like how it actually performs how long it performs depends entirely on like say what the schema looks like or what the data looks like in the database etc
</details>

不过我不会把那叫做语义，我会把那叫做性能特征。

[清喉咙]

<details><summary>Original English</summary>
but that's I would not call that semantics though I would call that performance characteristics.

[clears throat]
</details>

>> 哦，当然。是的。我想那会像……

<details><summary>Original English</summary>
>> Oh, sure. Yeah. I think that would be like
</details>

>> 就像我会说，其中的语义部分会是比如……嗯，取决于数据的形态是什么，或者配置是什么，你最终可能会得到不同的语义，因为就像你说的，你希望把 null 当作 false 来处理。嗯，除非你也知道系统的配置等等，否则你不会知道这一点。好的。好的。好的。所以，就本次对话而言，我认为我们应该只说，存在你写的实际代码，以及存在系统的行为方式。为了方便交流，我们把后者称为语义。[笑]

<details><summary>Original English</summary>
>> like I like I would say like a the semantics part of that would be like um depending on like what the shape of data is or like what the configuration you might end up with different semantic because like you said you want null to be treated as false. Um and you won't know that unless like you also know the configuration of the system and and and so on. Okay. Okay. Okay. So, for the purpose of this conversation, I think we should just say that there's like the actual code you write and there's how the system behaves. And we'll call the second one semantics just so we can have a conversation. [laughter]
</details>

>> 有一个……

<details><summary>Original English</summary>
>> There's a
</details>

>> 那你想怎么称呼它们？

<details><summary>Original English</summary>
>> Well, what do you want to call them?
</details>

>> 我们需要深入探究它的语义，确保它们是清晰的。

<details><summary>Original English</summary>
>> We need to dive into the semantics of this and make sure they're clear.
</details>

>> 没错。[笑]

<details><summary>Original English</summary>
>> That's [laughter] right.
</details>

>> 因为有很多……

<details><summary>Original English</summary>
>> Because there's a lot of
</details>

### 工作流与 AI 辅助开发实践

>> 我知道。好的。好的。我们保持高层视角。好的。所以，非常抱歉。那我们回到刚才的切入点。所以，嗯，你知道，实际上在我们开始录播客之前，你和我正在闲聊，你当时谈到你现在如何能够在一个星期内完成过去一个团队要花几个月才能完成的产品、项目。你能不能带我们了解一下，比如你个人……

<details><summary>Original English</summary>
>> I know. Okay. Okay. We'll keep it high level. Okay. So, so sorry. So, let's go back. So, um, you know, actually before we started the podcast, you and I were just shooting the [ __ ] and you were talking about like how you can do products, projects now that take a week where in the past would take a team and months. Can you maybe walk us through a little bit about like how you personally
</details>

>> 算是如何做项目，以及你看到的收益？[嗤笑]

<details><summary>Original English</summary>
>> kind of well do projects and then kind of the gains that you see? [snorts]
</details>

>> 比如稍微谈谈你的技术栈和你的流程。那么，我使用的是 Claude Code。嗯。我要说一件其实挺搞笑的事，但我用的是 Windows。

<details><summary>Original English</summary>
>> So like a little bit about like your stack and your process. So, I use um cloud code. Um I'm going to say something that's actually pretty funny, but I use uh Windows.
</details>

>> 那个[笑]是由微软这家公司做出来的吗[笑]？

<details><summary>Original English</summary>
>> What [laughter] was that created by this company Microsoft [laughter]
</details>

而且我用 WSL？所以对于像开发等等的一切，我都使用 Linux。上面没有像 X 或 UI 这类东西。我就只用命令行提示符。嗯，

<details><summary>Original English</summary>
and I use WSL? So, I use Linux for everything like development and so on. There's no like X or UI for it. I just use the command prompt.

Um,
</details>

>> 你怎么会用 Windows 呢？

<details><summary>Original English</summary>
>> how do you use Windows?
</details>

>> 因为我从来都不太想去记那些键盘快捷键。

<details><summary>Original English</summary>
>> Because I just never really wanted to learn the keyboard shortcuts.
</details>

>> 你是个游戏玩家吗？[笑] 就比如你 Tab 键切来切去去打反恐精英什么的。

[笑] 还能是因为什么呢？我不是讨厌 Windows。我的意思是，你看，我 90 年代用过它。

<details><summary>Original English</summary>
>> Are you a gamer? [laughter] It's like you tab tab over to Counter Strike or whatever.

[laughter] Like why else? I'm not hating on Windows. I mean, you know, like I used it in the '9s.
</details>

>> 那确实就是唯一的原因，我从来都不想去记那些快捷键。我讨厌单键鼠标。我讨厌单键那套东西。我讨厌为了快捷键等等必须按下的修饰键数量，我就是从来都不想，我觉得为什么、为什么、为什么要浪费时间。[笑]

<details><summary>Original English</summary>
>> That's really like the only reason is I never wanted to learn the the shortcuts. The I I hate the onebutton mouse. I hate the one button stuff. I hate the number of modifiers you have to type for shortcuts and stuff like I I just I just never I'm like why why why waste time. [laughter]
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 所以就用 Windows。是的。

<details><summary>Original English</summary>
>> So like yeah use Windows. Yeah.
</details>

>> 嗯，因此 WSL 我用 Claude Code。

<details><summary>Original English</summary>
>> Um and so WSL I use cloud code.
</details>

>> 什么是 WSL？

<details><summary>Original English</summary>
>> What is WSL?
</details>

>> 那是 Windows Subsystem for Linux。

<details><summary>Original English</summary>
>> That's Windows Subsystem for Linux.
</details>

>> 所以它是，他们实际上在 Windows 内的虚拟机监控程序中运行 Linux 内核，并为你提供访问权限。它非常棒。他们做得很好。

<details><summary>Original English</summary>
>> So it's uh they actually run the Linux uh kernel within Windows in a hypervisor and provide you access to it. It's great. They've done a great job.
</details>

>> 太好了。Windows、WSL……

<details><summary>Original English</summary>
>> Great. Windows WSL
</details>

>> 还有 Claude Code。

<details><summary>Original English</summary>
>> and Cloud Code.
</details>

>> Claude Code。

<details><summary>Original English</summary>
>> Cloud Code
</details>

>> 然后，比如我最近、我最近做的事就是我用 Opus 5.5。我告诉它……

<details><summary>Original English</summary>
>> and uh like my latest the latest thing that I do is I use Opus 5.5. I tell it
</details>

>> 那是一个非常好的模型。

<details><summary>Original English</summary>
>> which is a really good model.
</details>

>> 它是一个极棒的模型。

<details><summary>Original English</summary>
>> It's an amazing model.
</details>

>> 非常好。是的。

<details><summary>Original English</summary>
>> Really good. Yeah.
</details>

>> 它是，过去两周里我已经交付了这些包含 20 个 PR 的庞然大物，我就直接甩给我的团队去审查，他们就[笑]……我说你们别担心。

<details><summary>Original English</summary>
>> And it's I've shipped in the last two weeks these massive 20 PR things that I just dump on my team to go and and review and they're like [laughter] I'm like don't worry about it.
</details>

>> 太可怕了。这就像是，这就是新的汇报结构吗，下属替 CEO 审查 PR？我们已经变成那样了吗[笑]……

<details><summary>Original English</summary>
>> Horrible. It's like is like the new reporting structure like the people below review the PRs for the CEO. Is that is that where we become [laughter] like
</details>

>> 不，大家也都在写同样的 PR。

<details><summary>Original English</summary>
>> No, everybody's like writing the same PRs too.
</details>

>> 是的。我审查我团队的 PR，就像每个人都在……全都是 PR 满天飞。

<details><summary>Original English</summary>
>> Yeah. I I review my people PRs and like everybody's like just just PRs flying around in PR.
</details>

>> 是的。但在审查周期中发生很大变化的一点是，我们开始更多地关注，开始更加关注测试，比如做基准预期之类的事，以及它们是否在以不同的方式发生变化等等。但是 Opus 5，以及我最近学到的技巧是，你不用子 agent，而是基本上告诉 Claude 去启动命令行子 agent，因为那些子 agent 会随着时间推移保持其持久会话。

<details><summary>Original English</summary>
>> Yes. And but like the thing that has changed a lot in the review cycle is that like we started much more focused on to focus much more on like the the tests and like doing things like golden expectations and like are they shifting in different ways and so on. But um Opus 5 and like the the trick that I've recently learned about is that you instead of using sub agents, you basically tell Claude um to spin up command line sub aents because those maintain their persistent session over time.
</details>

>> 这样你就可以让它分别启动这些 agent。你实际上可以从其他会话运行它们等等。那能让你从上下文的角度变得高效得多。

<details><summary>Original English</summary>
>> And so you can have it spin up these agents separately. You can actually run them from other sessions and and so on. And uh that allows you to be much more efficient from a context perspective.
</details>

>> 你运行多少个 agent？多少个……

<details><summary>Original English</summary>
>> How many agents do you run? How many
</details>

>> 多少个……

<details><summary>Original English</summary>
>> how many
</details>

>> 多少个什么 agent？

<details><summary>Original English</summary>
>> how many what agents
</details>

>> agent。通常我同时在三到四个会话窗口中工作，因为我发现超过这个数量，我就会开始在不同的事情之间丢失上下文，因为它们开始完成得更快，然后我就……然后它们就处于等待状态。

<details><summary>Original English</summary>
>> agents um typically I work on like three or four session windows at the same time because I found that more than that I just start losing context um between the different things because like they they start finishing faster and then I I then they wait.
</details>

>> 那它们是通过……它们是通过 PR 交互吗？是这么运作的吗？

<details><summary>Original English</summary>
>> And do they interact via the do they interact via the PR? Is that how it works?
</details>

>> 子 agent 之间一起？不，它们直接通过命令行交互。

<details><summary>Original English</summary>
>> The sub agents like together? No, they interact directly through the command line.
</details>

>> 哦，哇。好吧。

<details><summary>Original English</summary>
>> Oh, wow. Okay.
</details>

>> 是的。所以，比如我让主要负责实现的核心部分配备一个技术主管审查员，他们基本上会向其提问。这样合理吗？这样不合理吗？审查我的 PR，等等。所以它们一起在这些 PR 上进行迭代。嗯，[嗤笑]然后它们有一份共同编写的 PR 文档，里面包含设计文档和所有内容。我做的第一件事就是让那个 agent 去做这件事。让技术主管审查那份 PR 文档。我通读 PRD。我通读设计文档。确保它合理。详细过一遍每一个部分。确保所有算法都能正常工作，所有模块都能正常工作，分工明确，各个 PR 之间的划分以及它们的关系都能理顺。然后我就告诉它，放手开始做吧。看看是否有你可以进行的并行化处理，然后启动其他 agent 去实际执行。嗯……

<details><summary>Original English</summary>
>> Yeah. So, like I asked like the the main like the main thing that does the implementation to have a tech lead reviewer and like they basically ask it questions. Does this make sense? Does this not make sense? Review my PR, etc. And so they iterate on these PRs together. Um, [snorts] and then they have a PR doc that basically they work on with a design doc and everything in it. Like the first thing that I do is I ask that agent to do it. Ask the tech leads to review the PR doc. I go through the the PRD. I go through the design doc. Make sure it makes sense. Go through each piece in like detail. Make sure that all the algorithms work and like all the pieces work, the division of labor works, the division between PRs and their relationships work. And then I tell it just go start start doing it. Figure out if there's like paralization that you can do and then spin up other agents to actually go do them. M
</details>

>> 但最终你还是得把所有东西重新放回一个技术栈中，并且能够作为人类逐一梳理，因为否则它就会变得混乱而繁杂，你就无法真正去应对它了，你懂吗？

<details><summary>Original English</summary>
>> um but ultimately you have to kind of put it all back in one stack and be able to go through it as a human one by one because otherwise it just gets messy and bushy and you can't really tackle it, you know?
</details>

>> 那么花多少时间……你能给出概念说明一下，比如你现在做的项目与我不清楚六年前相比，时间上的差异。

<details><summary>Original English</summary>
>> So how much time so can you give a sense of like a project you do now versus I don't know six years ago like time differences.
</details>

我最近交付的项目是某个……

<details><summary>Original English</summary>
So the latest project that I shipped was something
</details>

>> 顺便说一句，要明确的是，这是生产代码。这不是演示样机之类的。所以你将要陈述的是你在交付生产环境代码时获得的收益。

<details><summary>Original English</summary>
>> by the way this is like to be clear this is production code. This is demo mockups whatever. So like the statement you're about to make is the gains that you get for like shipping production.
</details>

>> 是的。所以我给你举一个最后的例子，我做的最后一个 PR，或者说最后一组 PR，是我们所谓的在数据湖中的自动、自动提升。

<details><summary>Original English</summary>
>> Yeah. So I'll give you the example of the last there there's the last PR that I worked on or like the last set of PRs was what we call auto auto promotion in a data lake.
</details>

>> 是的。在数据湖中你存储所有数据，通常数据是按列组织的 Parquet 文件和 Iceberg 等等。当你从日志中获取数据时，它们是半结构化的，包含任意列等等。为了让它具有最佳的数据布局，并且能够高效快速地查询它，理想的情况就是日志事件中的每个字段都变成一列，让你可以独立于其余各行对其进行过滤。

<details><summary>Original English</summary>
>> Yeah. So in a data lake you store all the data and um typically the data is um column oriented parquet files and iceberg and so on. Um and when you get data from um logs they're semistructured they're arbitrary columns and so on. In order for it to to have the best layout of the data and to be able to query it efficiently and fast, you kind of the ideal situation is that every field in the log event becomes a column that you can filter on independently of the rest of the rows.
</details>

>> 所以我们称之为自动提升或数据分片。

<details><summary>Original English</summary>
>> And so we call that autopromotion or shredding.
</details>

>> 嗯，做类似的事情是极其复杂的，对吧？比如你必须弄清楚元数据系统是如何运作的，元数据系统的提交是如何运作的，如何在不同的写入器之间进行协调等等，而那大概花了 10 天左右。在……

<details><summary>Original English</summary>
>> Um, and doing something like that is incredibly complicated, right? like you have to go and figure out how does the the metadata system work, how do the commits of the metadata system work, how do you coordinate across different uh writers and so on and um that took maybe about 10 days.

In
</details>

<!-- chunk 4/8 -->

前几天，那大概得花上 6 个月左右。

<details><summary>Original English</summary>
previous days that would have taken maybe about 6 months.
</details>

>> 哇。

<details><summary>Original English</summary>
>> Wow.
</details>

>> 对单个人来说。

<details><summary>Original English</summary>
>> For a single person.
</details>

>> 哇。

<details><summary>Original English</summary>
>> Wow.
</details>

>> 而且这只是你一个人，还是……

<details><summary>Original English</summary>
>> And was this just you or
</details>

>> 那就只是我一个人。太疯狂了。是的。差不多是 10 倍、20 倍的提升。

<details><summary>Original English</summary>
>> that was just me insane. Yeah. Sort of like factor of 10, factor of 20 improvement.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是针对新产品的生产环境代码。

<details><summary>Original English</summary>
>> For production code for new products.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

### 分布式系统与运维层面的 AI 挑战

>> 你知道，有一个、你知道，我一直有的一个问题就是，我非常能理解，你知道，这些模型是在所有曾被写出来的代码上训练的，咱们就这么说吧，对吧？所以，我能理解为什么它们能够生成代码，也就是语法部分。嗯，但是随后比如针对你知道你正在做的核心基础设施，比方说你在做分布式算法，比如比如它的属性，比如它在运行时的自身表现是非常非常不同的。比如通常你甚至不能光看语法就知道会发生什么，对吧？比如很多，比方说，比方说你在，我不知道，你在，比方说你正在编写某种分布式系统，然后它像它将表现出的性能，它的可用性，嗯，甚至正确性，都将取决于工作负载是什么样子的，你知道，比如访问模式是什么，流量是什么。

<details><summary>Original English</summary>
>> You know, one, you know, one one um question I always have is like I can very much understand, you know, the these models are trained on all the code ever written, let's call it, right? So, I can understand why they're able to generate code, which is the syntax piece. Um but then like for you know you're doing core infrastructure let's say you're doing distributed algorithms like like like the properties like how it handles itself when it's running is very very different like often you just can't even look at the the syntax to know what's going to happen right like a lot let's say let's say you're I don't know you're you're let's say you're writing some distributed system and then like the way that it like it will perform the the availability um the correctness even is is going to be dependent on what the workload looks like you know like like what are the access patterns what is the traffic
</details>

>> 但你指的是它性能方面的表现，还是你指的是像这种……

<details><summary>Original English</summary>
>> but are you talking about like the performance aspects of it though or are you talking about like this the
</details>

>> 嗯，我在想比如可用性，比如你可能必须对某些东西加锁，所以它在一段时间内是不可用的；我说的是正确性，比如也许你决定做最终一致性，所以如果你进行读取，它不会是一致的，因为并没有加锁，对吧；

<details><summary>Original English</summary>
>> well I'm think like availability like you may have to lock things so it's not available for a period of time I'm talking about correctness like maybe you've decided to do eventual consistency and so like if you do a read it's not going to be consistent because there isn't a lock right
</details>

>> 嗯，然后是性能，比如你知道也许你做了缓存，也许你没做缓存，这些都是设计空间中的权衡，对吧？

<details><summary>Original English</summary>
>> um and then performance like you know maybe you cache maybe you don't c these are all kind of trade-offs in the design space, right?
</details>

>> 而且除非你知道访问模式，否则你不会知道它在这些方面的表现如何，对吧？因此我就暗自琢磨，好，我有一个 AI，我能理解它会怎样编写，比如说，一个通用分布式数据存储的代码。我不理解的是，它将如何知道怎样去做出所需的权衡，因为它甚至都不知道访问模式是什么。而且这些东西又不可能，比如从哪里能获得数据去学习如何构建一个理解所有这些运维细节的系统？对吧，比如今天我们依赖人类去管理集群、去优化数据库等。所以你能不能谈一谈你是怎么看待的？比如我明白编写代码这部分，但是你有这些纵深的运维系统，你如何把 AI 应用到那个问题上？以及，第一，我们到底有没有取得任何进展，或者这仍然是一个悬而未决的问题？我认为这个问题可能关乎复杂性，以及在多大程度上你能把那些你描述过的、属于运维性的且在生产环境中发生的事情，转化为 AI 能够进行推理的东西……

<details><summary>Original English</summary>
>> And like unless you know like the access patterns, you won't know how it's going to perform in these things, right? And so I just think to myself, okay, I've got an AI, I can understand how it will write, you know, like like code for a generic distributed data store, for example. What I don't understand is how it will know to like make the trade-offs needed because it doesn't even know what the access patterns are. And it's not like these things can like like where's even the data to learn how to like build a system that understands like all of the operations right like today we rely on human beings to like manage clusters and to like you know optimize databases etc. And so can you maybe talk about how you think of like I get the writing the code but like you have these deep operational systems like how do you apply AI to that problem and like a have we made any progress at all or is this still an outstanding problem? The question I think is maybe about complexity and like to what extent can you take the things that you've described that are operational and like that happen in production and convert them into something that an AI can reason about
</details>

>> 并且呃，具体来说，AI 怎么能够对这个系统进行推理？

<details><summary>Original English</summary>
>> and uh exactly like how can an AI reason about this system
</details>

>> 嗯，首先，在多大程度上你能看到它编写代码时能真正预测出会发生什么？比如它在这方面做得有多好？第二个是，好的，现在我们该如何让它去对此进行推理？所以我们先问第一个问题，比如如果我用你的方法，也就是写代码的 JAD 方法，并且我构建了某个大型分布式系统，它在性能、正确性方面实际上有多大几率能搞对？

<details><summary>Original English</summary>
>> well a first off like to to what extent do you see that it writing the code that it can actually predict what's going to happen like how good of a job does it do at that and the second one is like Okay. Now, how do we make it reason about that? So, let's ask the first one like like if I if I use your method, the the JAD method of writing code and I built some big distributed system like how often does it actually get it from performance correctness?
</details>

>> 它实际上在运维层面上有多大几率是相当合理的？顺便说一句，我在做这个分布式高斯泼溅（Gaussian splat）渲染器，我只能说它很垃圾，就像简直糟糕透顶。因为你有数以百万计的高斯泼溅点必须换入换出并进行流式传输，这完全取决于正在运行的系统，所以没有一个模型能做好。

<details><summary>Original English</summary>
>> How how often is it like actually operationally like pretty sensible? And by the way, I I work on this this distributed Gaussian splat render and I would say it's [ __ ] Like it's horrible. like because like you know you've got millions of Gaussian splats that you've got to page in and out and stream and like it just totally depends on like the running system and so like none of the models do a good job.
</details>

### 基于性能基准与实验的优化

>> 所以在我们的领域里，我发现的是，我们基本上把性能基准长什么样、以及系统应该如何运行，都定义得非常好；

<details><summary>Original English</summary>
>> So in our world what I found is that we've defined basically really well what performance benchmarks look like and how the system should run
</details>

>> 以及要在我们的流处理器内部构建以获得适当性能，实际约束条件是什么样的。但每隔一段时间它就会做出，比如我最近的项目完全是关于查询优化和查询性能的。所以我就说，嘿……

<details><summary>Original English</summary>
>> and uh what the constraints of actually building within like our stream processor look like to get the right performance. But every once in a while it'll do like my la latest project has been all about query optimization and query performance. And so I was like hey
</details>

>> 这正是那种事情的经典例子……

<details><summary>Original English</summary>
>> the classic example of something that's
</details>

>> 我说我们基本上是在生成与 SQL 对应的代码，并且我们希望在流水线中运行它。

<details><summary>Original English</summary>
>> I was like we are basically generating code that corresponds to SQL and we want to run it in a pipeline.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 然后我们就像，好吧，你生成的代码太烂了，去修好它。

<details><summary>Original English</summary>
>> And we're like okay well you're generating [ __ ] code fix it.
</details>

>> 是的。然后呃它基本上开始逐个排查，而它当时没意识到的是，它最初实际上并没有对代码做任何优化。它就像是，哦，这挺好的啊，看起来有什么问题吗？然后我说，你看，你在这些地方用了合取项（conjuncts），而且这个特定的项重复了，本来应该被拿掉的。然后它就说，啊好吧，让我弄明白这个等等。随后它基本上就顺着一条线索去弄清楚所有的，它围绕着它能去优化以使其变得更好的所有事项，建立了一堆假设。

<details><summary>Original English</summary>
>> Yeah. And uh it started basically going through and what it didn't realize was that it wasn't actually doing initially any optimization on the code. It's like oh it's fine. It looks like what's the problem? And I said well look there's these uh these conjuncts over here you're doing and and like this particular term is repeated and it should have been taken away and then it's like ah okay let me figure this out and so on. And then like it basically went on a thread to try to figure out what are all like it built a bunch of hypotheses around like what are all the things that it can go and optimize to make this better.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 嗯，但归根结底它之所以能够做到，是因为它能够立足于性能基准，我说，你看，这是一个查询的数据集，以及用户在请求什么等等。去在这上面下功夫吧。

<details><summary>Original English</summary>
>> Um but ultimately it was able because it was able to ground that in performance benchmarks and I was like look here's here's a data set of the queries and like what the users are asking and so on. Go work on it.
</details>

>> 嗯，所以通过那种方式，它基本上能完成得相对不错。但当涉及到回答诸如“我应该给这个系统分配多少内存？”这类问题时，

<details><summary>Original English</summary>
>> Um and so it can basically do a relatively good job that way. But when it comes to saying something around like how much memory should I give this system?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 它毫无头绪，而那必须来自在生产环境中运行的实际实验。

<details><summary>Original English</summary>
>> It has no idea and that has to come from actual experiments that run in production.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 因此我认为，在运维方面，这些系统目前似乎做得不错的地方在于，它知道“嘿，我可能回答不了这个问题。让我以某种方式运行一个实验，并得出那项信息”。但是当然，当涉及到运维时，生产系统的表现并不会如你所料，归根结底这就是为什么会发生故障。

<details><summary>Original English</summary>
>> And so what I think actually these systems seem to be doing well at this point in terms of operational stuff is that it knows that hey I probably won't be able to answer this question. Let me run an experiment somehow. and come up with that information. But of course when it comes to operations like production systems don't behave the way that you expect and ultimately that's why incidents happen.
</details>

### AI 在生产运维与根因排查中的应用

>> 那么你有没有发现，或者你是否正在做某种类似 AIS 的事情，即你实际上有一个运行中的系统，它产生日志，然后你将日志输入给 AI，它能在某种程度上帮你进行微调？是的。效果怎么样？

<details><summary>Original English</summary>
>> So have you found or are you doing any of like the AIS stuff where you actually have a running system that has logs and you feed it to an AI and that kind of helps you like tweak it? Yes. And how how well does that work?
</details>

>> 我们才刚刚……

<details><summary>Original English</summary>
>> So we're just
</details>

>> 因为从传闻来看，呃，我从其他做这个的人那里了解到的经验并不是那么好。我听到的那些个案反馈都不是很好。所以有这么几点。第一点是，我们对运维部分和安全部分都在做这个，但我们处理它的方式与其他人在 AISR 角度上的做法不同。那些系统很多基本上都是从滞后指标出发，比如“嘿，这个指标激增了”或者“发生了这个告警”。去在一个非常复杂的系统中往回倒推，试图确定为什么会发生这种情况，

<details><summary>Original English</summary>
>> because anecdotally uh my experience with other people doing this has not been that great. Like the reports I've been getting anecdotally have not been great. So, a couple of things. The first one is we're doing that for both operational pieces and uh and for security, but the way that we're tackling it is not the way that other people are doing it from an AISR perspective. A lot of those systems basically start from a lagging indicator like, hey, this metric spiked or like this alert happened. Go back through a very complex system and try to determine why that happened,
</details>

>> 对吧？

<details><summary>Original English</summary>
>> right?
</details>

>> 就像……

<details><summary>Original English</summary>
>> Like,
</details>

>> 是啊，确实。你看，这就是为什么那些方法行不通，因为往回溯源根本原因实际上是非常成问题的。所以相反，我们正在做的是反其道而行之，也就是我们能否实际上先从查明你的环境中是否存在某些发生了变化的不同寻常之处入手？比如我们能否做一个大规模的聚类，一种大规模的在大海捞针中找出某种异样？然后，所以你是在假设它之前运行正常，而现在不正常了。所以肯定是发生了什么事情，但那也有可能只是正常流量模式的变化，对吧？

<details><summary>Original English</summary>
>> yeah, sure. It's, you know, that's why those don't work because like backtracking into a root cause is actually very problematic. And so instead, what we're doing is doing it the other way around, which is can we actually start by figuring out if there's something different in your environment that has changed? Like can we do a large scale clustering, a large scale kind of figure out a needle in a haststack, something that is different? And then so you're assuming that it was working fine before and now it's not. So something happened, but it could be just like a change in like normal traffic patterns, right?
</details>

>> 那也没问题。那也没问题。所以我们所关注的事情是，当出现问题时，通常系统会以某种方式告诉你出了问题。是的。对吧。嗯，如果它运行良好并且像往常一样伸缩，那就什么都不会发生。但有时你会看到某条消息说错误、连接耗尽。

<details><summary>Original English</summary>
>> That's fine too. That's fine too. And so the the the thing that we're looking at is like when things go wrong, usually the system will tell you something went wrong somehow. Yeah. Right. Um if it's working fine and scaling as normal, nothing will happen. But sometimes you'll see some like message which says error connections ran out.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 或者内存超限，或者资源缓冲区已空，或者某种迹象，比如某种真正早期的预警，表明发生了某些事情，而那就是我们想要捕捉的那条消息，然后从那里开始去探查……

<details><summary>Original English</summary>
>> Or memory exceeded or resource buffer is emptied or like some kind of indication like some kind of really early warning like something happened and that's the one message that we want to capture and then go from there and see
</details>

>> 那是否是一个我们需要调查和处理的实际问题。那么它的效果如何呢？到目前为止它做得相当不错。我是说我们正在我们内部的系统中运行它。我们在，呃，我们在我们的几家客户那里运行了它……

<details><summary>Original English</summary>
>> is that an actual problem that we need to investigate and deal with. So how does it do? So far it's doing pretty well. I mean we're running it internally in our systems. We run it uh we ran it in uh in a couple of our customers
</details>

<!-- chunk 5/8 -->

环境，而在某些情况下……有几次我们忽略了它。

<details><summary>Original English</summary>
environments and in the cases where there was a couple of cases where we ignored it.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 结果那些演变成了生产环境故障。

<details><summary>Original English</summary>
>> And those turned into production incidents.
</details>

>> 真的吗？噢，哇。

<details><summary>Original English</summary>
>> Really? Oh wow.
</details>

### AI 在系统运维与状态空间中的应用边界

>> 是啊。单从直觉的角度来看，我能理解这些模型是如何理解语法的，因为正如我所说，它们是在有史以来写过的所有代码上训练出来的，事实证明这覆盖了大量有用的场景。但我甚至很难想象对软件的实际运维操作设一个边界，对吧？我的意思是，感觉就像——你知道，这是个荒谬——这是个荒谬的说法，但它其实某种程度上是真的。就像每次给程序增加一个比特（bit），它在运维操作上能做的事情的状态空间就会翻倍。所以你很快就会达到，比如[笑声]，你知道，比如比宇宙中的原子还要多的状态。可以说，这就是为什么——

这就是为什么像针对运维的产品化方法从来没有真正奏效过，对吧？比如混沌工程那些东西从来没有真正奏效过，而我们一直以来有点依赖……其实长期以来运行分布式集群的公开秘密，就是纯粹靠人在管理它。所以我在想，然后你知道，然后为了甚至训练一个 AI 去做这件事，你必须有足够的数据和足够的配置。所以，我只是有点好奇，你觉得我们现在到了可以用 AI 来运行分布式集群，或者运行其中某项服务的地步了吗？还是你觉得那仍有待实现？

<details><summary>Original English</summary>
>> Yeah. It's kind of just just from an intuitive perspective like I can understand how these models understand syntax because again like I said they're trained on all of the co code ever written and it just turns out that covers a lot of useful cases. It's hard for me to actually even think of a bound on the actual operations of software, right? I mean, it feel like, you know, this is a ridic it's a ridiculous statement, but it's actually kind of true. It's like every time you add a bit to a program, the state space of like what it can do operationally increases by a factor of two. So, you very quickly get to like, [laughter] you know, like more more, you know, states than atoms in the universe. And arguably, this is why

This is why like product approaches to operations have never really worked, right? Like the chaos engineering stuff never really worked and we've always kind of relied, you know, actually the dirty secret for the longest time of running like a distributed cluster was just human beings managing it. And so I'm just wondering and then you know and then in order to like even train an AI to do it, you have to have like enough data and enough configurations. And so like I'm just kind of curious like do you think we're at a at a a spot where you could like use AI to run a distributed cluster or run one of these services or do you think that's still on the come?
</details>

我觉得[抽了口气]现有的东西已经足够让它开启那个循环了，对吧？我的意思是归根结底，我认为我同意你的看法，比如有无限的空间，有很多不同的事情，但归根结底人类也是依照运维手册（runbooks）来操作的。当然在生产环境中会发生很多事情，你最终需要某个人去说：嘿，这太复杂了，存在一些我所知道的隐藏状态，因为我前几天在饮水机旁跟另一个人聊过，他告诉了我关于他部署的这件东西——可能有很多东西在系统的状态中是不可见的。是的，

<details><summary>Original English</summary>
I think that [snorts] there's enough to be able to have it start that loop, right? Like I mean ultimately like I think that I agree with you like there's infinite space there's a lot of different things but ultimately humans also operate on runbooks and like sure there's a lot of things that happen in the um in production that you ultimately need some human to go and like hey this is too complex there's like some state that's hidden that I know of because I talked to this other guy like at the water fountain the other day and he told me about this thing he deployed like there's a lot of stuff that potentially isn't visible in the state of the system. Yeah,
</details>

>> 但我认为，我们需要能够达到的目标是，拥有足够的遥测数据（telemetry）和足够的理解，从而从“嘿，这是系统的现状，这是它的运行方式，这是某某情况”的角度把所有事情变得真正可见。然后我认为，归根结底，在假设系统之前运行良好的前提下，最终真正出现在运维中的大多数问题，都是由于某种变化引起的。如果你能够仅仅专注于弄清楚那个变化是什么，以及诸如此类的目标——

<details><summary>Original English</summary>
>> but I'll argue that like the goal of what we need to be able to do is to like get to have enough telemetry and enough understanding to like make everything really visible from a hey here's what the system looks like, here's how it's working, here's like whatever. And then I think ultimately most of the issues that end up really showing up in operations assuming you have the system previously running okay is due to some kind of change. And if you're able to just focus on the goal of figuring out what the change was and like what and kind of
</details>

不好意思，关于这个我能问个愚蠢的问题吗？那就是，我、我、我从来不觉得这些生成模型那么擅长预测东西，而听起来你谈了很多关于预测建模的内容，比如你预测一个变化，或者建立基线并检测出异常。是我在这个问题上的思考方式不对吗？

<details><summary>Original English</summary>
sorry can I just ask a stupid question on this which is I I I never think of these generative models that good at predicting stuff and it sounds like you're talking a lot about predictive modeling like you predict a change or you baseline and you detect an anomaly. Like am I thinking about this wrong?
</details>

>> 不，你没有想错。

<details><summary>Original English</summary>
>> I no you're not.
</details>

好的。

<details><summary>Original English</summary>
Okay.
</details>

>> 因为目标实际上并不是让 Agent 去尝试预测，而是让它获取发生变化的信号。

<details><summary>Original English</summary>
>> Because the goal is not actually having the uh agent try to predict but have it uh get a signal that something changed.
</details>

>> 噢，确定性地获取，原来是这样。我明白了。

<details><summary>Original English</summary>
>> Oh deterministically that's something I see. I see.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 等等。所以、所以有、不好意思。所以有一个单独的模型来做预测的事情，然后它会向 AI 发出警报。

<details><summary>Original English</summary>
>> Wait. So so there there sorry. So so there is a separate model that does the predictive stuff and then that will alert the AI.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 好的。是的。

<details><summary>Original English</summary>
>> Okay. Yes.
</details>

>> 所以是的。我们做的事情基本上就是，你每天把 PB 级的日志交给我们。

<details><summary>Original English</summary>
>> So yeah. So like what we do like what we do is we basically you give us your pabyte of logs per day.
</details>

>> 明白。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 我们扫描所有日志，每次我们在你的日志中看到出现某种新的模式，一种我们以前从未见过的新事物，我们就会把它提交给 AI。

<details><summary>Original English</summary>
and we scan all of them and we we like every time we see a new kind of pattern emerge in your logs, a new thing that we haven't seen before, we lift it up to the AI.
</details>

>> 我懂了。所以那是一个预测模型，它实际在做预测模型所擅长的事情，即确定异常事物之类的，然后把那个送给 AI，AI 就利用它来弄清楚该怎么做。

<details><summary>Original English</summary>
>> I see. So that's that's a predictive model that actually does like does what predictor models are good at which is determining out of norm things or whatever whatever and it's like the that goes to the AI and the AI kind of uses that to figure out what to do.
</details>

>> 没错。因此 AI 基本上接着就可以进行推理并把那个——

<details><summary>Original English</summary>
>> Exactly. So the AI basically can then reason and drive that
</details>

>> 我明白了

<details><summary>Original English</summary>
>> I see
</details>

>> 顺藤摸瓜排查下去。所以它可以说：“噢，这条消息，让我实际看一下代码，弄清楚它来自哪里，并理解这段代码在做什么。让我看看它之前是否实际发生过。让我看看。”所以它基本上会运行所有这些假设和启发式规则，试图去理解这是否合乎情理？它是否在某种程度上具有意义，然后它就可以决定如何处理它。

<details><summary>Original English</summary>
>> that down. So it can say, "Oh, this message, let me actually look at the code and figure out where it comes from and understand what the code does. Let me see if it's actually happened before. Let me see." So it basically runs all these hypotheses and heristics to try to understand does it make sense? Does it need meaningful in some kind of way and then it can determine what to do with it.
</details>

### 查询优化与集群运维的人机代际讨论

那么你认为我们距离——咱们先回到查询优化（query optimization），先不说日志或类似的事情。你认为我们距离让 AI 基本上完成以往人类在查询优化方面所做的工作还有多远？

<details><summary>Original English</summary>
So how far away do you think we are for let's just go back to query optimization, not like logs or something like so. How far away do you think we are from having an AI basically do the job that a human used to do when it comes to query optimization?
</details>

我认为非常接近了。

<details><summary>Original English</summary>
I think very close.
</details>

>> 真的吗？

<details><summary>Original English</summary>
>> Really?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

哇。

<details><summary>Original English</summary>
Wow.
</details>

>> 我认为，额——

<details><summary>Original English</summary>
>> I think uh
</details>

>> 运行分布式集群呢。

<details><summary>Original English</summary>
>> running a distributed cluster.
</details>

>> 我只是想，比如你有一个麻省理工学院（MIT）博士毕业的詹姆斯·考英（James Cowing）在运行分布式集群，如果集群宕机了，公司就无法运转；如果集群正常，系统就能跑起来。我不知道，我们现在到了你会说 AI 可以做那件事的地步了吗？

<details><summary>Original English</summary>
>> I just think of like okay you've got like James Cowing PhD from MIT who runs a distributed cluster and like if the cluster's down like the company doesn't work and then if it's up it's running. I don't know like are we at the point where you would say that an AI can do that?
</details>

>> 还没有。

<details><summary>Original English</summary>
>> No, not yet.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

我认为——我的意思是我认为，你看，非常非常简单地说，当我们刚开始用 AI 写代码时，它只是自动补全。

<details><summary>Original English</summary>
I think it's I think I mean I think look look very very simply when we started doing like AI for coding it was autocomplete.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 当时谁也无法确切知晓利用 AI 究竟能在多大程度上构建复杂的软件。

<details><summary>Original English</summary>
>> And nobody really knew to what extent you can actually build complex software using AI.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 当我们看着它的时候，我们觉得：啊，AI 永远无法构建出——

<details><summary>Original English</summary>
>> And like when we were looking at it we're like ah like AI is never going to be able to build
</details>

>> X 或 Y 或 Z 之类的。然后它基本上打破了人们的预期，因为我们能够在系统中对越来越高的复杂度进行建模。

<details><summary>Original English</summary>
>> X or Y or Z or whatever. And then it basically broke through the expectations because we were able to model like more and more complexity in the systems.
</details>

我只是——我只是觉得，在这类事情上我是个非常简单直接的思考者，对我来说这些模型就是分布进、分布出（distribution in, distribution out）。事实证明你可以用有史以来创造的所有代码进行训练，而且那个流形（manifold）其实是相当可控的。我只是不知道运维是否以同样的方式受到约束，或者在我看来那是否更像是宇宙那样[笑声]，具有厚尾性（heavy tailed）、基于异常、遵循幂律，以及对这些模型来说所有难以学习的那些东西。但我不知道。我的意思是，你才是身处这个领域的人，所以也许情况并非如此。也许它们是可控的，但是——

<details><summary>Original English</summary>
I just I just feel like like I'm a very simple thinker on this stuff and it to me these models are distribution in distribution out and it turns out like you can actually train on all the code ever created and it's actually like that manifold is pretty manageable and I just don't know if operations h is constrained in the same way if that feels to me more like kind of like the universe [laughter] like heavy tailed and exceptionbased and power laws and all the tough stuff for these models to learn. But I don't I don't know. I mean you're the one that's in the field so maybe that's not the case. Maybe they're manageable, but
</details>

>> 但我要告诉你，如你所知，系统的历史向来就是你总想构建一个高效的聪明算法。聪明的虚拟内存管理，聪明的拥塞控制，聪明的路由算法。而每一次我们实际上是怎么做的？[笑声]

<details><summary>Original English</summary>
>> but I I I will tell you the history of systems as you know is is you always want to build a smart algorithm that does the efficient thing. The smart virtual memory management, the smart congestion control, the smart routing. And what do we do instead? Every single time [laughter]
</details>

>> 我们构建了——

<details><summary>Original English</summary>
>> we build the
</details>

>> 我们超量配置（overprovision）。不，我们每一次都超量配置。不，毫不夸张地说，我们每一次都是这样。比如还记得交换内存（swap memory）吗，就是把内存交换到磁盘？伙计，如果你那么做了，你就完蛋了。就那样了，你的电脑就卡死了。所以我们真的是超量配置内存；还有路由，你知道有多少自适应路由算法，声称我们会对流量做出响应，但随后会出现振荡，去它的，我们就超量配置，我们直接用——你知道，所以我只是觉得系统的历史就是：你不去预测东西，你超量配置是因为你无法预测。而且我觉得——我的意思是，你知道——所以我觉得在运维方面，要么我们构建这个——你知道，我们预先构建好超量配置的系统，这样你就不必去做复杂的运维工作；要么也许 AI 可以像人类那样去做，但我认为这跟代码非常不同，因为你要处理异常情况，数据量不多等等。我只是觉得这是一个不同的领域，但我不知道。我是一个风险投资人（VC），我只是觉得——

<details><summary>Original English</summary>
>> We overprovision. No, we overprovision every time. No, literally we every single time. Like like remember like swap memory where you like swap to disk? Dude, if you did that, you were [ __ ] Like that's it. Your computer was dead. So like we literally overprovision RAM and like routing you know how many like adaptive routing algorithms there are like we will respond to traffic but you have oscillations like [ __ ] it we overprovision we just use you know so I just feel like the history of systems is you don't predict stuff you overprovision because you can't and I feel like I mean you know so I feel like in the operation side so either we build this you know we we'll build the systems up front that are overprovisioned so you don't have to like do kind of complex operational stuff or maybe AI can do the way that a human being, but I think it's very different than code because you're dealing with like exceptions, there's not a lot of data, etc. I just feel like a different domain, but I don't know. I'm a I'm a VC. I'm just like,
</details>

>> 你知道，我……我之所以在这里更乐观一些，是因为我生活在这样一个世界：我们所做的事情实际上是在跟可观测的世界打交道。比如——

<details><summary>Original English</summary>
>> you know, I I I I kind of like the reason that I'm more uh optimistic here is because I live in the world where like what we do is actually deal with the observable world. Like
</details>

>> 我正想说你在这方面是真正的专家。所以对我来说，甚至问你这些问题都很蠢。

<details><summary>Original English</summary>
>> I was going to say you're the literal expert on this. So, it's silly for me to even like ask you these questions.
</details>

>> 不，完全不是。因为在我的世界里，我们……我的假设是，我们拥有所有数据，我们确切地知道什么时候发生了新情况，或者出现了异常，或者工作负载发生了变化，或者诸如此类的事情。在我的世界里，所有这些都已经被收集并通过流式传输进来了，而且——

<details><summary>Original English</summary>
>> No, not at all. Because like in in my world, we We h like my assumption is that we have all the data is that like we know exactly when like a new thing happens or like an exception emerges or like a workload changes or like whatever. Like in my world, all of that has already been collected and streamed through and like
</details>

>> 但、但

<details><summary>Original English</summary>
>> but but
</details>

<!-- chunk 6/8 -->

这个模型并没有针对这类内容在扎实的来源上进行过训练。
<details><summary>Original English</summary>the model that is not trained on a grounded source for that stuff like that.</details>

>> 不，你没有。
<details><summary>Original English</summary>>> No, you're not.</details>

>> 那确实会非常难，
<details><summary>Original English</summary>>> That would be really hard,</details>

>> 对吧？但情况并不是说：“嘿，Claude 先生，这是一堆日志，是不是出什么问题了？”对吧？它必须更有能力去进行实验，深入探究，看看在现有的实际环境中到底契合哪些不同形态的潜在因果链。
<details><summary>Original English</summary>>> right? But the but the story here isn't like, "Hey, Mr. Claude, here's a bunch of logs. Is something going on?" Right? And it has to be much more uh able to run experiments and kind of dive in and see like what are the different shapes of possible causal chains that actually fit in the environment that exists.</details>

>> 我明白了。对，这正对应你之前说的。现在我明白你的意思了。你是说：
<details><summary>Original English</summary>>> I see. So yeah, this is what you said before now. Now I see what you're saying. You're saying that like</details>

>> 这个世界是重尾分布的。可能发生的坏事数量大概属于异常情形，但用来排查调试它的一整套步骤却是可控的。这就是你能教给这类模型的东西，也是你所拥有的；因此，如果你给它正确的信号，它就能一步步执行来真正约束这个问题。
<details><summary>Original English</summary>>> the universe is heavy tailed. The the number of bad things that can happen is is probably ex an exception thing, but like the set of steps used to debug it is a manageable thing. That's what you can you can teach one of these models and that's what you have and therefore if you give it the right signals it can go through a number of steps to actually constrain this problem.</details>

>> 没错。
<details><summary>Original English</summary>>> Exactly.</details>

>> 有意思。
<details><summary>Original English</summary>>> Interesting.</details>

>> 没错。所以它实际上是在扮演人类的角色。因为还记得——还记得整个混沌工程浪潮吗？当时……
<details><summary>Original English</summary>>> Exactly. So it really is taking the role of the human because remember remember the whole remember the whole chaos engineering wave where like</details>

>> 它之所以没有取得任何进展，是因为你极其迅速地……你知道，试图去缩减一个状态空间，而那个空间就像宇宙中的原子数量一样庞大，要想极其迅速地真正把它变得可控，以前全靠人类通过一步步排查来实际进行调试。而[嗤笑]这就是你所说的 AI 要去做的事情。
<details><summary>Original English</summary>>> and and the reason it didn't go anywhere is like you're very so quickly like trying to like you know reduce like a state space that was atoms in the universe like so like super quickly like and actually make that manageable and it was like the human being that would go through a steps that would do that on the actual debugging and [snorts] this is what you're saying the AI would do.</details>

### 排障与安全中的因果链验证

>> 是的。没错。所以目标并不是让模型直接说出“这就是发生的事情”。而是“嘿，按照这个工作流运行，查出到底发生了什么”。比如我们也在安全领域尝试这种做法。在安全领域，你的统计数据中出现了某些不同的变化，比如就存在的实体、存在的各种事物的基数而言出现了一些行为差异，这在……
<details><summary>Original English</summary>>> Yes. Right. So the goal isn't to like have the model just be like this is what happens. It's hey run through this workflow to determine what happened. And like we're trying that also on the security side for example where like hey in security you have a something different changed in your like statistics like some behavioral difference in terms of what entities exist the cardalities of various things that exist and so that becomes a perturbation in the</details>

>> 呃，无论这个系统环境是什么，它成了一种扰动。于是我们捕获那个信号，把它输入给 AI，我们说：“嘿，AI，”
<details><summary>Original English</summary>>> uh whatever the universe and so we take that signal and then we feed it into an AI and we're like hey AI</details>

>> “构想出一堆可能存在的因果链，然后逐一验证，看看其中是否有任何一条符合我们实际观察到的数据模式。”这样一来，它就变成了一种更类似于“嘿，这里有个……呃，我不知道，就像把这个方块放进……找到销钉，或者找到适合这个销钉的孔洞”。这在我看来甚至更难，因为对于运维来说，观点在于……
<details><summary>Original English</summary>>> come up with a bunch of possible causal chains that exist and then go through and verify if any of those fit the pattern of the data that we actually see. And so that becomes a much more like hey here's a here's like a uh I don't know like fit this square into find the peg or like find the hole that fits this peg. And that seems even harder to me cuz the operations one the argument is</details>

>> 系统可能会进入各种状态，进入损坏的[清嗓子]状态，这些状态往往非常罕见，而且存在大量的此类罕见状态。
<details><summary>Original English</summary>>> the system can get in states in into broken [clears throat] states that are kind of like very rare and there's a lot of those rare states</details>

>> 所以单凭这一点，你就无法在这上面训练模型，纯粹是因为它可能进入的糟糕罕见状态实在太多了；因此，或许你可以通过执行那些步骤来对其进行化简。而安全方面似乎还要更难，因为这不仅仅是罕见状态的自然规律，你实际上还面对着一个对手……
<details><summary>Original English</summary>>> and so it's just not something that you can you know train a model on just because there's so many rare states it can get into that are that are bad and so maybe you can reduce that by doing the steps. The security one seems even harder because this isn't just like the natural order of rare states. You actually have an adversary that is</details>

>> 正在试图故意去寻找罕见状态，故意去寻找你……你做不到的东西。因此情况可能是这样：代码问题被解决了；做运维需要多花一点时间，你知道，更久一些；而安全则需要花长得多的时间。
<details><summary>Original English</summary>>> trying to like intentionally find rare states and intentionally find stuff that you you you can't do. And so it may be the case that like code becomes solved. It takes a little while, you know, longer to do operations and it take a lot longer.</details>

>> 是的。不过同时想想看……我的意思是，我不知道，对我而言，整个世界在某种程度上都是量子化的。普朗克长度。[笑]物理学家是这么说的吗？对，我不知道，我不是物理学家。常数。
<details><summary>Original English</summary>>> Yeah. But like also like think about I mean I don't know to me like the whole world is sort of quantized to a certain extent. the plank length. [laughter] Is that what the physicists say? Yeah, I don't know. I'm not a physicist. Constant.</details>

>> 我[笑]认为实际上……我完全不知道我现在在胡扯些什么，但我确实真的认为，比如时空是被离散化为普朗克长度的。不过……不过是的，我的意思是，在某种程度上我同意你刚才说的。但对于运维以及一般的系统来说，可能的状态以及穿行于其中的可能路径，确实存在一种离散化。
<details><summary>Original English</summary>>> I [laughter] think there's like actually I I literally don't know what I'm talking about right now, but I literally actually think that like like like spacetime is discretized into a blank length. But but yes I I mean I agree like to a certain extent what you just said but for operations and systems in general like there is a discretization of like the possible states and the path through them that are possible.</details>

>> 对。
<details><summary>Original English</summary>>> Yeah.</details>

>> 没错。
<details><summary>Original English</summary>>> Right.</details>

>> 我只是觉得，当你面对……
<details><summary>Original English</summary>>> I just think when you're dealing with</details>

>> 可能会有……可能会有非常非常多。
<details><summary>Original English</summary>>> there might be there might be a ton of them.</details>

### MP3 与状态空间的有限性

>> 可能会有极多。我给你讲个事，还记得我们研究生课题组里的 Sundar 吗？
<details><summary>Original English</summary>>> There might be a ton of them. I'm going to tell you remember Sundar who um was in our in our grad school group.</details>

>> 记得。就在耳边。
<details><summary>Original English</summary>>> Yeah. in their ear.</details>

>> 对，对，对，对。我记得有一次他来找我，他……他当时看起来非常悲伤。他说：“Martin，我刚刚有了一个极其悲伤的领悟，”
<details><summary>Original English</summary>>> Yeah. Yeah. Yeah. Yeah. So, I remember he came to me once and he and he he was he was he was looking very sad. He's like, "Martin, I just had this really sad realization</details>

>> “那就是，你知道，如果拿随便一首 MP3 来说——还记得对我们而言 MP3 就代表音乐吧。[笑]”
<details><summary>Original English</summary>>> that, you know, if you take any MP3, remember MP3 is like the [laughter] music for us."</details>

>> 是的。
<details><summary>Original English</summary>>> Yes.</details>

>> 他说，他说 MP3 是有限的，比如说，四分钟。大小大概是 4 兆字节，你知道，这就意味着全宇宙中的歌曲数量是有限的……
<details><summary>Original English</summary>>> He said he said MP3s have a finite, let's say, you know, four minutes. It's like four megabytes, you know, and that means there's a finite number of songs in the universe</details>

>> 能够……不，因为你知道，因为这全都是……这全都是由比特构成的，对吧？它只有 4 兆字节，那就意味着你能够……你完全可以枚举出当中的每一个概念。所以……所以我为这种关于音乐有限性的概念感到非常难过，对吧？真的，当时我们正走在 Dish 那条路上，他跟我聊起了这个，然后我说：“老兄，你他妈的，你知道，”[笑]“你知道你以多快的速度就超过了全宇宙的原子的数量吗？你甚至连 1K 都还没达到，对吧？[笑]这就像……这就像 2 的 2 次方的 2 次方的 2 次方。”我说：“老兄，你在这儿扯什么呢？高兴点吧。”
<details><summary>Original English</summary>>> that can no because you know because it's it's all made of it's all made of bits, right? And it's four megabytes and that means you can you could just enumerate every one of those concepts. So so I'm so sad in this notion of like the the finitness of music, right? Literally, this is like we were walking on the dish when he had this conversation and I'm like, "Motherfucker, dude, you know, [laughter] you know how quickly you've like overcome like the atoms in the universe. You haven't even gotten to a K, right? [laughter] It's like it's like two to the two to the two to the two." Like, what are you talking about here, man? Be happy.</details>

>> 2 的 2 次方的 2 次方，4 兆字节。
<details><summary>Original English</summary>>> Two to the two to the two four megabytes.</details>

>> 4 兆！你知道……这有如此庞大的状态。高兴点吧，那实际上等于无限，对吧？我们到底在讨论什么呢？[笑]所以，在某种层面上，我确实认为我们低估了系统可能进入的状态数量。而且，或许我可以从观察这些公司的风险投资人的角度告诉你，那些试图解决运维问题的公司目前都举步维艰。这……这看起来比那些解决代码问题的公司要艰难得多，因为我认为这是一个难得多的问题。
<details><summary>Original English</summary>>> FOUR MEGA YOU LIKE THIS IS so much state. Like, be happy. That's that's effectively infinite, right? Like what are we talking about here? [laughter] So I I do think at some level like we do underestimate like the number of states that like you know systems can get into and like maybe I will tell you from the perspective of a VC that looks at these companies the ones that are trying to tackle operations are having a tough go at it. It is a it seems much much tougher than those that are tackling the code because I think it's a much tougher problem.</details>

### 运维复杂性与代码演进路径

>> 我 100% 同意。这确实是一个难得多的问题。而且……而且这不仅仅是因为系统本身，你知道，会遇到各种降临在你身上的外部随机负载，或者你知道，有人刚刚发布了一个新东西，部署到了生产环境却没通知任何人，或者……
<details><summary>Original English</summary>>> I 100% I agree. It is a much tougher problem and and it's not just because like the systems themselves are you know there's like external loads that are random that kind of h happened to you or that uh you know somebody just shipped a new thing and rolled it out into production didn't tell anybody or like</details>

>> 呃，当这件事发生、那件事也发生时实际出现某种状态，然后你陷入了死锁。呃，这也因为这里面牵扯到多得多的人类，而且不仅仅是编写代码的那一个具体的人，它实际上还涉及……
<details><summary>Original English</summary>>> uh there's some state that actually happens when like this thing happens and this thing happens and then you end up in a deadlock. Um it's also because it involves humans a lot more and not just like one human who's the coder. It actually also involves</details>

>> 各个知识池也都是分散的。
<details><summary>Original English</summary>>> the pools of knowledge are distributed too.</details>

>> 没错。还涉及像连接各个模块并把它们组合在一起所需要的相互交互……
<details><summary>Original English</summary>>> Exactly. and the interactions between like what it takes to like</details>

>> 把各个碎片拼接并拼凑在一起。
<details><summary>Original English</summary>>> connect the pieces and put them together like</details>

>> 但归根结底，我思考的是 AI 如今所处的位置，思考未来可能的发展，以及所有事物的深度和前瞻性能力。我觉得代码对我来说只是一个缩影，也许……也许我只是太宿命论了，也许我只是对世界的运作方式太悲观了，我总觉得一切都沿着某种概率路径在运行。呃，所以对我来说，如果我们能在代码上把它做通，我们就能一点一点地继续拓展那种复杂性水平，层层累加，直到我们能够处理涉及大量人类的那些问题。
<details><summary>Original English</summary>>> but ultimately I mean I think about like where AI is and like what are the possible futures and like the the depth and the forwardlooking capacity of all the things like I think code is just to me it's a microcosm of like may maybe I'm just too fatalistic maybe I'm just like too pessimistic about how the world works and and I think of everything is like following some kind of probabilistic path. Um, and so to me like if we can make it work in code, we can continue expanding that level of complexity bit by bit and kind of adding layers and layers and layers until we can handle those problems of</details>

>> 大量的人。这不是宿命论，恰恰相反。大家会说这非常乐观。对我来说，我认为宇宙不会那么轻易交出它的秘密，但……走着瞧吧。我的意思是，这算是一个重大问题，而且我想说，迄今为止这还是一个悬而未决的问题。
<details><summary>Original English</summary>>> a lot of people. It's not fatalistic. It's the opposite. That's very optimistic is what people would say. For for me, I don't think the universe gives up its secrets that easily, but like we'll see. I mean like this is kind of the big question and and I would say to as yet it's not an answered question.</details>

>> 不，是的。不是。但是……
<details><summary>Original English</summary>>> No. Yeah. No. But</details>

>> 我不知道，有很多东西……呃，作为人类，我们认为它们是随机的，或者是……
<details><summary>Original English</summary>>> I don't know a lot of things that um as humans we think of as being random or</details>

>> 无法攻克的。是的，我们在编程上也看到了这种情况。你知道，最初人们认为，在代码中能够实现的所有事物构成的可能世界是相对受限的，你无法真正让一个系统去理解人类大脑所必需的全部复杂性。但我认为随着时间的推移，这一切都会……真有意思，我居然在跟你讲这些，而你作为展望未来的风投家，却在表示不同意。好吧，我的意思是，我……我跟你谈谈我的看法。我的看法是，对这些模型的研究就是：你用数据来进行训练，呃，要么……要么你知道，这……我们试着这么说：你用数据来进行训练，而那……
<details><summary>Original English</summary>>> impossible to tackle. Yes. And that's what we saw with with coding like you know initially like people thought like the the possible world of all these things that you can implement in code are kind of limited and you can't really get a system to potentially understand the full complexity of a human brain that's required. But I think over time it'll all It's so funny that I'm actually telling you this and you're like the VC who's looking into the future and being like no well I mean I I'll tell you my view. My view is like the that this the study of these models are you train on data and um either that I that you know the let's try to say so you you train on data and that</details>

<!-- chunk 7/8 -->

### 现实与语言、代码的降维

代表着一种分布。那种分布有用与否，所以比如当你在语言上进行训练时，它很有用这一事实，在我看来表明人类太了不起了，因为他们审视了宇宙——这个非常高维的系统——并将其降维成一个对模型而言确实有用的流形，对吧？

<details><summary>Original English</summary>
represents a distribution that distribution is useful or not and so like when you [clears throat] train on language the fact that it's useful that to me says that humans are so remarkable because they've looked at the universe which is this very highdimensional system and they've reduced it to a manifold that's actually useful for a model, right?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 对。但那和宇宙本身是不同的。就像那存在一种从这种高维度到语言的降维，语言的维度要低得多。

<details><summary>Original English</summary>
>> Right. But that's different than the universe. Like that's there's a reduction from this high dimensionality to the language is much less dimensional.
</details>

>> 而且我认为代码是将机器的所有运行状态降维成让它运行的指令。所以对我来说，在指令或描述与宇宙的实际运行、系统的实际运行之间，依然存在着脱节。我认为我们能够朝着这个方向取得进展。但我会说的是，你有点在向模拟靠拢。比如有些事物在计算上是不可约简的。你必须得去实际运行它才能得到答案。你不能直接……

<details><summary>Original English</summary>
>> And I think that code is a reduction of all the operational states of a of a machine into like the instructions that make it run. And so to me, there's still a disconnect between like the instructions or the the description and the actual like the actual running of the universe and actually running the system. I think we can make gains toward it. But I what I will say is like you're kind of converging on simulation. Like there are things that are computationally irreducible. Like you kind of have to run it to get the answer. You can't just like
</details>

>> 你知道的，去预测它。所以也许我们正好处于一个事件视界，在那里……

<details><summary>Original English</summary>
>> you know predict it. And so like maybe we just are at an event horizon where like
</details>

>> 比如模型能解决任何你不需要真正去模拟就能从中得出答案的事情。但我……为什么，为什么你必须只从“嘿，它现在就必须回答这个问题”的角度来思考，而不是它能够去模拟，并且……抱歉，能够规划它自己的执行以获取所需的信息，从而能够……

<details><summary>Original English</summary>
>> like models will solve anything that you don't have to actually simulate to get the answer from. I but why why why do you have to like just think about it in terms of hey it'll have to answer the question like now as opposed to being able to simulate and and sorry being able to plan its own uh execution to gain the information that it needs in order to be able to
</details>

>> 不，也许那正是我们前进的方向。是的。就像……

<details><summary>Original English</summary>
>> No maybe that's where we're going. Yeah. Like
</details>

>> 那差不多正是我……有道理。

<details><summary>Original English</summary>
>> that's kind of what I'm fair enough.
</details>

>> 是的。而且我认为存在一个更低维度的……存在更低维度的空间，也就是你将采取的这些步骤，我们可以用 AI 大幅减少这些步骤，然后无论你需要什么它做不到的步骤，它都可以生成代码去完成或者可以进行模拟。

<details><summary>Original English</summary>
>> Yeah. And and I think like there's a lower dimensional there's lower dimensional space which is like these steps that you would take that we can reduce a whole bunch with AI and then whatever steps that you need that that can't do it can create the code to do or can simulate.
</details>

>> 但你想表达的观点是，你看，模型实际上无法去弄清楚我们需要去发现并建模到其世界中的那些外部世界的额外维度。那可能是……我是说那可能是真的。但它能否充分地模拟一个科学家，从而达到那个程度呢？也许吧。

<details><summary>Original English</summary>
>> And the point that you're making though is that like hey look the model can't actually go and figure out the additional dimensions of the world that we need to go and find to like model the universe into its world. Like that's probably I mean that's probably true. But can it actually simulate a scientist sufficiently to be able to get to that point? Like maybe,
</details>

### AI 在风投工作中的边界

>> 也许吧。太棒了。我可以问你一个问题吗？你认为 VC（风险投资）的工作中有多少是 AI 可以驱动的？我对 VC 的认知模型是，它是极度由人脉关系驱动的。我觉得是这样。好吧。我只是……我只是相信市场实际上是相当有效的，你知道，所以这不在于去找到一家别人都没发现的公司。我认为大家都会找到合适的好公司。我认为他们是高效的。然后我对 VC 还有这样一种模型，即，额，你知道……

<details><summary>Original English</summary>
>> maybe. Cool. Can I ask you a question? How much of a of uh the VC work do you think is something that an AI can drive? So my model for VC is it's very relationship driven. It's I think so. Okay. I just I just have a belief that markets are actually pretty efficient, you know, and so it's not about like finding the company that nobody else finds. I think people all find like the right company. I think they're efficient. And then I also have the model of VC that [gasps] um, you know,
</details>

科技是向好的，我对所有科技都持乐观态度，我也不担心 TAM（潜在市场规模）。所以我认为关键在于准入与人脉获取能力。在于融资，在于人脉渠道，在于抢到交易份额的能力，以及在交易完成后提供增值服务的能力。而其中很多都是初创公司天生做不到的事情，比如你知道的，招聘知名高管，或者在这方面提供协助。因此，按照我对风险投资的看法，你几乎必须是一个真正的人类才能做这行，就像你知道的那样……因为那才是真正的工作内容。

<details><summary>Original English</summary>
tech tech is positive and I'm kind of optimistic about all tech and I don't worry about TAM. And so I I I think the key is access. It's like raising money. It's access. It's ability to win deals and there's ability to add value after that happens. And a lot of that is like stuff that that startups just can't naturally do like you know recruit you know big execs or help with that. And so the way that I think about venture you kind of have to be a human being to do it's like you know um because because that's the actual job.
</details>

所以对于这一点，我不认为 AI 会……如果你给 AI 一个模拟宇宙，在里面它可以，你知道，不管怎么进行奖励黑客攻击来建立信任关系，这很好，但我认为那必须……话虽如此，我得说我也见过由 AI 完成的分析，它们和我合作过的任何分析师做得一样好甚至更好。所以对于分析这部分来说，它们很棒，但我认为这与其说是说明模型有多强大，倒不如说是对风险投资机构自身分析能力的控诉。我只是觉得这一切都是一出歌舞伎表演和混账把戏。我只是觉得合适的 VC 态度就像是，你知道的，科技终究是净增益的。科技浪潮总会创造价值，我们去找到最好的公司并投资它就好。

<details><summary>Original English</summary>
So for that I don't think like an AI if you gave an AI simulated universe where it could like you know like whatever reward hack like building trust relationships fine um but I think that that would have to be to be [laughter] that said I will say I have seen anal analysis done by AI that are as good or better than any you know gene analyst I've ever worked with like so for the the the analysis piece um they're great but I think this is more an indictment on VC's ability to like analyze that than it is like how powerful you know the models are. I just think it's all a kabuki show and [ __ ] I just think the right VCs are like you know you know tech is is is net positive. You know tech waves always add value like let's find the best company and invest in it.
</details>

市场是非常非常高效的，所以我……我只是觉得这个问题的答案几乎有点像是技术层面的……我的回答几乎是一个技术性细节。那么，你知道，我来这里想问你的其中一件事就是这样一个真实的问题，即……

<details><summary>Original English</summary>
The markets are very very efficient and so I I I just feel like the answer to this question is almost kind of a technical like my answer is almost a technicality. So how like you know one of the things you know I came here I wanted to ask you this real this question which is like
</details>

### 数字受限领域与物理世界

>> 你知道，我们一开始专门谈论了运营。

<details><summary>Original English</summary>
>> you know we started talking specifically about ops.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 但在我看来，存在着一个 AI 编写代码的世界，这有点像是它所生存的抽象模拟世界。

<details><summary>Original English</summary>
>> But to me like the there's this world of AI writing code which is kind of like this abstract simulation world that it lives in.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 然后还有世界的其余部分。

<details><summary>Original English</summary>
>> And then there's the rest of the world.
</details>

>> 是的，完全正确。整个讨论就是关于这个。就像存在着……

<details><summary>Original English</summary>
>> Yeah. Exactly. I the entire discussion is is this. It's like there's like this
</details>

>> 就像存在着 AI 所生存的世界，那是纯数字化的，不管它是什么，也就是训练数据、分布内的世界；同时还存在着现实世界，而这两者不一定相同。它们往往非常不同。所以问题在于，你在多大程度上需要去训练一个 AI，使它能够在一个世界中生存下来；以及它实际需要……我不想回答那个问题，比如你需要训练什么，但我对那些尚未开发的开放领域很好奇。

<details><summary>Original English</summary>
>> there's like the AI the world that the AI lives in which is all digital and like whatever it is the training data the indistribution world and there's the actual world and like those things are not necessarily the same. They're quite often not. And so the question is like to what extent do you need to train an AI to be able to survive in a world and like what are the things that it actually I I don't want to answer that question like what do you need to to train but like I'm curious about the open spaces.
</details>

>> 所以我们稍微谈了一下运营。你说你不知道它是否能被解决。我的态度是，能的，Martina，它是会被解决的。而在我心中，还有很多其他的事情，比如自动驾驶汽车，很长一段时间我们都认为那不可能实现，但现在很清楚它实际上会被做成。它一定会实现的。这只是因为很多不同的因素需要花时间。那么，你认为紧跟在代码之后的下一阶段、下一个领域会是什么？

<details><summary>Original English</summary>
>> So we talked a little bit about operations. You said I don't know if it's going to be solved or not. I'm like yeah Martina it's going to be solved. And uh in my mind like there's so many other things like for example self-driving cars like for a long time we thought that that's not going to happen but it's clear that it's actually going to be done. Um and it's going to happen. It's just taking time because of a lot of different things. And so what are like what are the other next stages the next areas that you think are kind of like lined up right after code?
</details>

我的感觉是，AI 在受限领域中将继续如野火般迅速爆发，在那些解空间处于受限领域的领域，对吧？也就是解空间的分布与训练集的分布相同的地方——代码语法的分布与训练集的分布相同，生成图像的分布与训练集的分布相同。在那些领域中，我认为它将继续像野火一样爆发。而那些解的分布属于自然世界的领域，我认为那将会……你知道，会困难得多，耗时更长，而且我认为其经济等效性将要困难得多。

<details><summary>Original English</summary>
I mean my my sense is is you know AI is going to continue to take off in a wildfire for a constrained domain where the where the solution space is in a constrained domain right where the distribution of the solution space is the same as the distribution of the training set the distribution of the syntax for code is the same as a distribution of the training set the distribution of the generated images is the same as the distribution of the training set in those you know areas I think it's going to continue to take off as a wildfire the domains where like the distribution of the solution is the natural world. I think it's going to, you know, have, you know, it's going to be much harder, take longer, and I think the economic equivalency is going to be much more difficult.
</details>

自动驾驶就是一个极好的例子。我还记得当我在斯坦福时 Sebastian Thrun 赢得了 DARPA 大挑战赛。还记得那个吗？当时我们欢呼雀跃，你知道，以为自动驾驶汽车指日可待了。认真的。结果花了 20 年时间以及 1700 亿美元的投资，得到的单位经济效益却比 Uber 还要糟糕，对吧？

<details><summary>Original English</summary>
Self-driving is a great example. I remember when Sebastian Thrun won the DARPA Grand Challenge when I was at Stanford. Remember that? And we're like, hooray. You [laughter] know, self-driving cars is around the corner. Seriously. And it took 20 years and $170 billion of investment to get to worse unit economics than Uber, right?
</details>

所以这就是，你知道的，所以我认为去解决真实的问题，那些你必须应对真实宇宙分布的问题，就是会困难得多得多。因此我将 AI 视为这种通用工具。它是一种非常有效的工具。在其中你拥有数据的某种分布，然后寄希望于能将其应用到某个问题上，我们将把它应用到一大堆事物上，我认为经济平衡将决定什么是行得通的，什么是行不通的，因为我认为它是一个非常非常通用的工具，就像一个通用函数逼近器。

<details><summary>Original English</summary>
So that's, you know, so I think that like solving like like solving real problems where you have to deal with the the distribution of the real universe is just much much harder. And so I view as AI as this general tool. It's a very effective tool. It's one where like you have you know a distribution of data and then hopefully you can apply that to like you know some problem and we're going to apply it to a bunch of stuff and I think economic equilibrium is going to determine what works and what doesn't work because I think it's a very very general tool it's like a universal function approximator
</details>

>> 而无论最终结果如何……我是说再次回到……

<details><summary>Original English</summary>
>> and wherever that nets out I mean again
</details>

>> 你知道，我之前说过的其中一件事是，AI 是如何在训练人类去使用它的。

<details><summary>Original English</summary>
>> you know one of the things that I said earlier was like how AI was training humans to like use it.
</details>

>> 是的。而且我经常在想，比如你知道，某些看起来棘手的问题，是因为世界本身就是那个样子，而我们试图让 AI 或我们正在构建的工具去适应现存的世界。但在某些情况下，我们实际上往往会改变世界，使其适应我们实际能做到的事情……

<details><summary>Original English</summary>
>> Yeah. And I very often think about like you know some of the problems that seem intractable was is because the world is kind of that way and then we're trying to fit AI or the tools that we're building to manage the world as it is. But in some situations we actually tend to change the world to fit to what we can actually do from
</details>

>> 100%。当然，我认为这就是机器人领域的故事。

<details><summary>Original English</summary>
>> 100%. Of course I think this is the story of robotics.
</details>

是的。

<details><summary>Original English</summary>
Yeah.
</details>

>> 自动化数据仓库。所以每当我们在审视这些数据仓库等等时，总浮现在我脑海中的问题就是，唯一行之有效的那一个正是……

<details><summary>Original English</summary>
>> The the automated data warehouse. And so the the question like that always comes to my mind like when we were looking at these data warehouses and whatever and like the only one that worked was the
</details>

<!-- chunk 8/8 -->

其中一个案例就是，你知道的，直接把整套东西全自动化算了。对。
<details><summary>Original English</summary>
one where it was like you know what just automate the whole [ __ ] thing. Yeah.
</details>

>> 嗯
<details><summary>Original English</summary>
>> Um
</details>

>> 而且，嗯，而且我也在想，在多大程度上，随着我们逐渐改进或改变我们……呃，或者说是扩展我们想要用 AI 工具去解决的领域等等，我们实际上会开始对世界进行建模，或者改变这个世界以及实际可能发生的事情，来迎合……
<details><summary>Original English</summary>
>> and um and I wonder to like what extent as we kind of improve or change how we uh or kind of expand the domain of what we want to solve with AI tools and so on that we actually start modeling the world or changing the the world and the things that can actually happen to fit
</details>

>> 迎合 AI 所需要它呈现的样子。
<details><summary>Original English</summary>
>> what AI needs it to look like.
</details>

### 现实世界的均衡与经济约束

>> 对。我的意思是，听着，我认为眼下很多 AI 只是在数字世界里运作。对。
<details><summary>Original English</summary>
>> Yeah. I mean I listen I I think that right now a lot of AI just operates in the digital world. Yeah.
</details>

>> 对于这一点来说，从某种意义上讲，它的解集字面上就和训练集是同一个分布。所以这没问题。而且我……我也认为，还是在均衡的情况下，比如我觉得，当你面对现实世界时，你可以解决任何你想解决的问题。这纯粹就是一个算力和资金的问题，而那个均衡点将是一个经济上的均衡点。而且我认为，你能对你求均衡的那个函数产生影响的一种方式，就是去约束……
<details><summary>Original English</summary>
>> And for that is like literally the solution set is the same distribution as a training set in a sense. And so that's fine. And I I think that again like in the case of equilibrium like I think like when you're dealing with the real world like you can solve any problem you want. It's just a matter of like compute and money and that the equilibrium point is going to be an economic one. And I think one way you can impact that function that you're doing equilibrium over is to constrain
</details>

>> 约束环境，约束系统。所以我想，我们将会……就像我们现在处在这个元经济均衡飞轮中，我们有点像是在用人们看重的解集，去优化这个极其通用但非常低效的过程。我认为，听着，我们还有 30 年的时间来做这件事，而且会创造出巨大的价值。
<details><summary>Original English</summary>
>> the environment is constrain the system. And so I I think that we're going to like we're in now in this meta economic equilibrium flywheel where we're kind of optimizing this super general but very inefficient process with a solution set that people value. And I think you listen we've got 30 years of this and a lot of value is going to be created.
</details>

### 客户买单的现实差异：代码与运维

>> 你知道吗，你想听个有趣的故事吗？好啊。
<details><summary>Original English</summary>
>> You know one you want to hear a funny story? Yeah.
</details>

>> 话说，你知道的，我们做了这么一个 AI 东西，然后我们就在跟人聊。我们去接触客户。我们说：“嘿，我们做了这个 AI 产品。你知道，我们在帮客户提高可靠性。这是我们正在做的事情。”他们就说：“太棒了。我们想跟你们聊聊。”接着我们进入电话会议，我们就说：“嘿，这是我们的功能。你知道，我们构建了这个系统。它能帮你优化数据。它能帮你降低成本。然后它能帮你提高可靠性，因为现在我们可以在这些问题引发故障之前就把它们找出来并解决掉。”结果他们说：“等等，等等，等等，等等。倒回去。你刚才说你们能帮我们省下 90% 的 DataDog 账单。
<details><summary>Original English</summary>
>> So, you know, we built this AI thing and we're like talking to people. We're like reaching out to customers. We're like, "Hey, we built this AI thing. You know, we're helping customers become more reliable. Here's like what we're doing." They're like, "Great. We want to talk to you." And then we go on the call and we're like, "Hey, here's what we do. You know, we built this system. Helps you optimize your data. It helps you reduce your costs. And then it helps you become more reliable because now we can find these problems and solve them before they hit your incident." They're like, "Wait, wait, wait, wait. Roll back. You said you can save 90% of our data dog bills.
</details>

>> 对。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 那才是我想买的。可是……可是……可是那个 AI 的功能呢。然后他们就说：‘不，不，不，不。那才是我们现在就想买的。’”
<details><summary>Original English</summary>
>> Like that's what I want to buy. But but but the but the AI thing. And they're like, "No, no, no, no. That's what we want to buy right now."
</details>

>> 是啊。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 这很有意思，就像很多这种……比如对于写代码，你知道，我经常在想这个。就像是，“噢，对于代码，大家一下就懂了。他们会觉得，噢，真是神了，它就是管用。”
<details><summary>Original English</summary>
>> And it's uh it's interesting like a lot of these uh like for code, you know, I always think about it. It's like, "Oh, for code, people just get it. They're like, oh [ __ ] it just works."
</details>

>> 是的。对。没错。
<details><summary>Original English</summary>
>> Yeah. Yeah. Yeah.
</details>

>> 而在运维端，或者类似超越这个范畴的任何事情上，
<details><summary>Original English</summary>
>> And on the op side or like anything that's beyond that,
</details>

>> 是的。很难理解它的实际价值，也很难给它定个美元价值，然后爽快地付款出手。100%。所以，而且我也认为从……从编码的角度来看，从字面上讲就是工程生产力，而这是这些项目里最高的一项支出之一。所以，这非常直接明了。
<details><summary>Original English</summary>
>> Yeah. it's very to understand the actual value and put a dollar value to it and be a pay out the door. 100%. So, and I also think from from a coding standpoint, literally it's engineering productivity which is one of the highest line items on these things. So, it's just very straightforward.
</details>

>> 没错。但你也可以这么想，这是 S 生产力，或者说是避免你的业务宕机。也许你能挽救一次故障，以及那会带来多大成本。
<details><summary>Original English</summary>
>> Exactly. But you can also think about it, it's S productivity or it's like your business going down. Maybe you can save an incident and what the cost is.
</details>

>> 我不知道。这……这挺怪的。我觉得就像大家在这之外是怎么看待它的……
<details><summary>Original English</summary>
>> I don't know. It's it's weird. I think like how people think about it outside of the
</details>

>> 是啊。我也……我也只是觉得，就像……就像这个代码当时太神奇了，因为它效果太好了，没人想到这能成真。而我认为现在的运维这块，它仍然像是……
<details><summary>Original English</summary>
>> Yeah. I I also I also just think like like this code was so magical because it was so good and nobody thought that could happen. And I think the operations stuff now it's still like
</details>

>> 相当早期。
<details><summary>Original English</summary>
>> pretty early.
</details>

>> 它仍然处在相当早期的阶段。所以，
<details><summary>Original English</summary>
>> It's still pretty early. So,
</details>

>> 是啊。[嗤笑]
<details><summary>Original English</summary>
>> yeah. [snorts]
</details>

>> 好吧。那，听着，聊得很开心。谢谢，J。谢谢，
<details><summary>Original English</summary>
>> All right. Well, listen, it's great to chat. Thanks, J. Thanks,
</details>