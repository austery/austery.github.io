---
author: a16z
date: '2026-11-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=g_67TmQ8lGY
speaker: a16z
tags:
  - ai-agents
  - economic-modeling
  - organizational-intelligence
  - machine-learning
title: AI 智能体协作与经济转型中的组织智能分析
summary: 对话探讨了 AI 发展的现状，指出当前模型在非规范任务上的进步显著，但真正的经济转型取决于智能体之间的协调能力而非单一的胜任力。讨论强调了组织作为一种“超级智能”形式，以及 AI 在构建微观与宏观经济结构模型方面的潜力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/8 -->

### 片头精选观点

机构的运转状况并不完全像我们所希望的那样顺畅，或者说也不像我们所担心的那样顺利。英伟达这边正在发生一些奇怪的事情。如果你看一下预测市场上关于 Anthropic IPO 估值的预期，它并没有飙升到 2 万亿美元以上。
<details><summary>Original English</summary>
institutions are not [music] quite running as smoothly as either we might like or we might fear. We have these weird things happening with Nvidia. If you look at prediction markets [music] for what the anthropic IPO will go for, it's not flying above 2 trillion.
</details>

>> 你预计这种增长会持续下去，还是认为会出现平缓停滞？
<details><summary>Original English</summary>
>> Do you expect the growth to continue or do you think a leveling up?
</details>

>> 收益会超过成本，但这需要一些时间，而且这条路径会比许多人让你相信的要正常得多。
<details><summary>Original English</summary>
>> Benefits will exceed costs, but it will take some time and the path will be quite a bit more normal than many people would have you believe.
</details>

>> 真正的经济转型所需要的不仅仅是能力，而是这些智能体之间相互协调的能力。现在有智能体集群（agentic swarms）这个概念，但如果你拆解来看，这些智能体在协调方面仍然非常差。它们大多只是在进行并行处理。
<details><summary>Original English</summary>
>> What you actually need for real economic transformation is not just [music] competence. It's the ability of these agents to coordinate with one another. There's this idea of agentic swarms, but if you unpack it, these agents are still very bad at coordinating. They're mostly just doing parallel processing.
</details>

>> 通常某些事物发展得越快，只意味着你更快地碰到了真正的瓶颈。如果你问我，智能体什么时候会贡献 GDP 的 10%？我认为这不会很快发生。
<details><summary>Original English</summary>
>> Often the faster that some things move, that just means you hit the real bottlenecks more quickly. If you ask me the question, when will agents be 10% of GDP? I don't think it's soon.
</details>

>> 这两个不同的世界看起来会是什么样？一个是 GDP 增长稍微偏向正常状态，另一个则是它真正达到两位数增长。
<details><summary>Original English</summary>
>> What are the two different worlds look like? One in which GDP growth is a bit more normal and another in which it actually becomes double digit. [music] Um,
</details>

### 正式开场与近期 AI 情绪讨论

>> Alex、Tyler，欢迎来到 Th andZ 播客。
<details><summary>Original English</summary>
>> Alex Tyler, welcome to Th andZ podcast.
</details>

>> 很高兴来到这里。
<details><summary>Original English</summary>
>> Happy to be here.
</details>

>> 谢谢，谢谢你们邀请我们。
<details><summary>Original English</summary>
>> Thanks. Thanks for having us.
</details>

>> 那么，有很多话题要聊。首先，我们来谈谈一些具有时效性的话题。媒体报告出来了，引发了大量的讨论。Paul Christiano 在推特上发表了言论。目前围绕着 AI 的现状、RSI（自我迭代提升）等，存在着很多某种程度上的动荡与焦虑。我很想知道，Alex，你对我们正在看到的现象有什么反应？以及对于目前正在发表的一些论断，你的立场是什么？
<details><summary>Original English</summary>
>> So, there's there's a lot to talk about. F. First, let's talk about some some timely topics. The media report came out. There's been a lot of conversation. Paul Cristiano has talked and tweets. there's a lot of sort of unrest and anxiety around sort of uh sort of the state of AI right now and and and RSI and and um I'm curious, Alex, what is your reaction to what we are seeing and and where do you stand on some of the proclamations being made right now?
</details>

>> 嗯，我仔细阅读了它。我认为不可否认的是，我们正在取得令人难以置信的进展，而且这种进展正在加速。我认为任何关注模型发布的人都会发现，模型的发布正变得越来越频繁，也变得越来越强大。各项能力，比如说从去年 11 月到今年 11 月，完全就是一个认不出来的世界了，尤其是像智能体 AI 与聊天机器人时代之间的差异。
<details><summary>Original English</summary>
>> Um so I mean I I I read it closely. I think I think it's undeniable that we're having in you know incredible progress and that the progress is accelerating. I think anybody who's looking at, you know, the model releases, they're becoming, uh, you know, more frequent. Uh, they're becoming more powerful. The capabilities are, you know, going, you know, going from like last November to this November. It's just an unrecognizable world, especially with the, you know, the the difference between like Agentic AI and the chatbot era.
</details>

你看到各家公司公布的内容，当公布有关聊天机器人时代与智能体时代之间差异的数据时，你现在看到的是真正的生产力。在聊天机器人时代，你使用它几乎就像使用一个高级版的维基百科或类似的东西，你问它问题，它给你答案；而有了智能体系统，你看到的是实际的工作，那种工作水平，即这些系统实际完成工作的能力，正在如此迅速地进步，你基本上看到了很多曲棍球棒式的增长曲线。这就是 meter 报告所展示的：看，这里又是另一个曲棍球棒曲线。所以对我来说，说实话，我并没有因为 meter 报告而做出太大的观点更新，因为 meter 报告中的很多数据在其他地方早就存在了。比如 S1 声明，我们此前也知道一些未发布的模型。所以我没有做出太大的更新，但那是因为我此前差不多就已经是那个观点了。
<details><summary>Original English</summary>
um you're seeing like you know the what's coming out of companies when when you have data coming out on like the difference between you know the chatbot era versus the agentic era um you're seeing real productivity now like with the chatbot you're kind of like using it almost like a a fancy version of of a you know Wikipedia or something like that you're asking a questions it gives you gives you answers with an agentic system you're seeing actual work and that level of work the ability of these systems to actually do the work is just progressing so quickly and you know you're you're seeing a lot of hockey sticks basically. Um and that's what the meter report showed is that look here's another hockey stick. So to me I didn't I to tell you the truth I didn't update too much from the meter report because a lot of the data in the meter report has been around in other spaces. So the S1 statement um you know we knew about the some of the unreleased models. So it's uh I didn't update too much but that's because I was kind of already there. I
</details>

>> 你的观点是，你指出的这些曲棍球棒曲线会一直持续上升吗？在什么节点上它们可能会逐渐减弱，或者说从现在开始，你对其中部分曲棍球棒曲线的维持有多大程度的看好？
<details><summary>Original English</summary>
>> is your view that the hockey sticks that you're identifying that they will just sort of continuously grow go up at what point might might they peter out or you know sort of how bullish are you from here on on some of these hockey sticks uh you know maintaining?
</details>

>> 我的意思是，正如你所说的“其中部分曲棍球棒曲线”，我认为这是核心词，关键在于：曲棍球棒曲线会出现在哪里？它们之间是如何关联的？因此在 meter 报告中，对我而言非常关键的一个短语是未充分验证的、未充分规范的任务。核心问题在于：那些规范程度较低的任务会怎样？很多工作并不是被明确规范的。我并不是那种认为“好吧，我们在非规范任务方面很安全”的人，我认为模型在那些没有被非常明确规范的任务上也在变得越来越好，但我认为要在这些类型的任务上实现曲棍球棒式的跃升可能会更困难。
<details><summary>Original English</summary>
>> So I mean like that's what you the the thing that you said some of these hockey sticks is I think the main term it's like where are the hockey sticks going to be? How are they connected? So in the meter report to me like the very the key phrase was unwellverified you know unwell specified tasks um what is the big question is like what about less specified tasks a lot of work is not well specified I I'm not one of those people who thinks this is like all right we're safe on the nonwell specified side I think the models are becoming increasingly better uh on on non very well specified tasks as well but I think you know it might be harder uh to to to do hockey sticks on those sort of tasks.
</details>

此外还有很多诸如隐性知识的问题，类似于哈耶克式的对于实际经济影响的担忧。Tyler 和我都算是经济学家，所以我必须对所有这些关于这些曲棍球棒曲线对经济学意味着什么、对经济上有价值的任务意味着什么的信息进行梳理。对我来说，核心的问题在于：每一个模型的迭代，这个模型解锁了哪些之前模型未能解锁的具有经济价值的任务？而这一点被曲棍球棒曲线非常不完美地捕捉了下来。因此，你可能会得到一个在基准测试上看起来非常惊人的曲棍球棒曲线，但随后在现实世界中你并没有真正看到太多的加速。我们现在还没到那个地步，我认为我们在现实世界中确实看到了很多加速。但这些只是我所抱有的一些疑问。

Tyler，让我们转向你。我觉得你在这场讨论中一直是一个更为清醒的声音。Alex 并非不清醒，但我只是想问，根据最近发生的事情，你的观点有任何更新吗，或者你的看法是什么？
<details><summary>Original English</summary>
Um there's also a lot of like the questions of like tacic knowledge uh kind of hayakian concerns about like the actual impact on the economy. I think you know Tyler and I are both economists. So all of all of this information I have to kind of sift through about what these hockey sticks mean for economics and what does it mean for economically valuable tasks. And the big questions for me are like every model iteration, what are the economically valuable tasks that is this model is unlocking that the previous model wasn't unlocking. And this is kind of captured very imperfectly by the hockey stick. So you can get a hockey stick that looks crazy on a benchmark and then you're not really seeing a lot of acceleration in the real world. We're not there yet. I think we're seeing a lot of acceleration in the real world. But these are just, you know, some of the questions that that that I have. Tyler, let's let's go to you. I feel like you've been a more sober voice uh in in the in the in the conversation. Alex hasn't been sober, but I just mean, do you have you updated at all based on what what's been happening here or what is your view?
</details>

### Tyler 对瓶颈与估值的看法

>> 嗯，通常某些事物发展得越快，只意味着你更快地碰到了真正的瓶颈。所以，我不会那么频繁地更新看法，但这里是 AI 领域，而在 AI 领域，确切的日期非常重要。我们录制的时间是 2026 年 11 月 11 日。这很重要，我想说，自 8 月以来，我的看法改变了相当多。最主要的原因是数学问题。因此，在那些没有太多人为瓶颈的领域取得了进展。我看到了迅速得多的进展，以及在比如大约三周时间内就能创建一个明显更好的新模型的能力。我之前没想到它会发生得像实际那么快。因此我认为这可以追溯到几个月前。但如果你指的是过去这一周，随着 mater 看跌，英伟达这边正在发生这些奇怪的事情。我无法预测，但这会稍微拖慢该行业的发展。如果你看一下预测市场上关于 Anthropic IPO 估值的预期，它们起伏波动，但并没有飙升到 2 万亿美元以上。你看看 Anthropic 自己预测的收入数字。我忘了确切的数字。我不会说我感到失望，但它们并不是在超高速起飞（super fast takeoff）情景下所期望看到的数字。而那是针对他们的 IPO 而言的。因此，出于这些原因，我会说在过去这一周里，我比一周前大约看跌了 1%。仅仅是机构的运转状况并不完全像我们所希望的那样顺畅，或者说也不像我们所担心的那样顺利，这取决于你的视角。
<details><summary>Original English</summary>
>> Well, often the faster that some things move, that just means you hit the real bottlenecks more quickly. So, I don't update that frequently, but this is AI land, and in AI land, the exact dates really matter. So, we're recording on November 11th, 2026. And that matters, I would say, since August, I've changed my views a fair amount. Most of all, because of the math problems. So, progress in areas where there are not many human bottlenecks. Uh, I see much more rapid progress and the ability to create a new model that is clearly better, say, within something like three weeks. Uh, I hadn't thought that would happen as quickly as it had. So I would date that to a few months ago. But if you mean over the last week, the mater bearish, we have these weird things happening with Nvidia. I have no prediction, but it will slow down the sector a bit. If you look at prediction markets for what the anthropic IPO will go for, they bounce up and down, but it's not flying above two trillion. You look at Anthropic's own projected revenue numbers. I forget the exact numbers. I wouldn't say I was underwhelmed, but they're not numbers that you would expect under the super fast takeoff scenarios. And that's for their IPO. So, I'd say I'm like 1% more bearish over the course of the last week than I was a week ago for those reasons. Just the institutions are not quite running as smoothly as either we might like or we might fear depending on your point of view.
</details>

>> OpenAI 和 Anthropic 的增长率……在过去比如两三年里，你的基准假设是这些增长率会继续保持吗？抛开具体的公司不谈，我更多指的是领先的 AI 公司，比如我们所见到的这种经济影响，无论这两家公司是否保持领先——当然它们也在与超大规模云厂商竞争——你是否预计增长会继续，还是认为会出现平缓停滞？
<details><summary>Original English</summary>
are either the sort of growth rates of open AI and anthropic um is your sort of base case that over the last let's say you know two or three years that those growth rates continue and and put aside the specific companies but I more mean just the the leading AI companies like the the the sort of economic impact that we've seen you know whether those two companies you know maintain the lead of course they're competing with the hyperscalers too do do you uh expect the the growth to to continue or do you think a leveling out?
</details>

>> 嗯，几周前我在湾区，许多人向我推销非常高的收入数字，我对他们所有人都提出了以下问题。我问：“还有哪些其他行业会以足够快的速度增长，以证明你们给我的 Anthropic 和 OpenAI 的极端收入数字是合理的？”没有人能回答那个问题。他们甚至连尝试给出答案都没有。所以，我认为这意味着极端的收入数字是虚假的。这并没有让我对整个行业看跌。我仍然看好。我认为一切都会很好，那些都是很棒的公司。但归根结底，你看看市场数据，不管是实际利率、股票价格还是任何指标，市场数据看起来依然相当正常。而且全世界的投资界都在谈论 AI。这并不是某种类似于 2014 年时的离奇谜团，在那个时候你还可以说
<details><summary>Original English</summary>
>> Well, I was in the Bay Area a few weeks ago and many people were pushing very high revenue numbers on me and I asked them all the following question. I said, "What are the other sectors that are going to grow sufficiently rapidly to justify the extreme revenue numbers you're giving me for anthropic and open AI?" And no one had an answer for that question. They didn't even try to give me answers. So, I think that means the extreme revenue numbers are false. That doesn't make me bearish on the sector as a whole. I'm still bullish. I think it will be fine. Those are great companies. But at the end of the day, you look at market data, whether it's real interest rates, stock prices, anything. Market data still look pretty normal. And the whole world investing community is talking about AI. It's not some kind of weird mystery like it was back in 2014 where you could say
</details>

我
<details><summary>Original English</summary>
I
</details>

<!-- chunk 2/8 -->

读了一篇 LessWrong 博客文章，现在因为读了它，我变得非常富有。所以我更信任市场的判断，而不是湾区那些对社会互动思考没那么深入的人的判断。所以这就是我的立场。它会改变整个世界。收益将超过成本，但这需要一些时间，而且其发展路径会比很多人让你相信的要正常得多。

补充一点，我认为 Tyler 说得完全切中要害，那就是你必须开始在经济的其他部门看到生产率数据，才能证明收入增长的合理性。因此，在某个时刻，经济的其他部门必须愿意为该产品付费，而这种不断提高的付费意愿必须来自于经济其他部门不断提高的生产率。我们目前并没有真正看到太多这方面的证据。并不是说它不会发生，但在某个时刻它确实需要发生。

另一部分是竞争。所以我认为，特别是在过去几个月里开始发生的事情，是前沿实验室之间极端的恶性价格竞争。之前他们只是试图在诸如“谁拥有更好的模型”上进行竞争，而现在这些模型正被越来越多的企业使用，而且它们变得相当昂贵，因为顺便说一句，Agentic AI 使用的 token 数量要多得多。所以现在各大公司——你知道，OpenAI、Anthropic，你知道，Muse 也加入了竞争，DeepMind 也参与进来，试图真正表明：“不，我们提供的是一个更便宜的模型，它一样好，或者可能稍微好一点，或者可能稍微差一点。”所以你看到 token 价格大幅下降。RAMP 有一个非常好的数据集来追踪这些情况。你看到了 token 使用量的指数级增长，而收入数据却持平，对吧？这是从哪里来的？就是因为价格竞争。所以在前沿领域，你看到的价格竞争比六个月前要激烈得多。
<details><summary>Original English</summary>
 read

 a

 less

 wrong

 blog

 post

 and

 now





I'm

 really

 wealthy

 because

 I

 did.

 So

 I





trust

 the

 judgment

 of

 the

 market

 more





than

 the

 judgment

 of

 the

 Bay

 Area

 people





who

 don't

 think

 that

 carefully

 about





social

 interactions.

 So

 that's

 where

 I





stand.

 It'll

 change

 the

 whole

 world.

 Uh





benefits

 will

 exceed

 costs

 but

 it

 will





take

 some

 time

 and

 the

 path

 will

 be





quite

 a

 bit

 more

 normal

 than

 many

 people





would

 have

 you

 believe.

 Yeah,

 and

 just





to

 add

 to

 that,

 I

 think

 there

 Tyler

 is





exactly

 spot

 on

 in

 the

 fact

 that

 like





you

 need

 to

 start

 seeing

 the





productivity

 numbers

 in

 the

 rest

 of

 the





economy

 to

 justify

 the

 the

 revenue





increases.

 So

 at

 some

 point

 the

 rest

 of





the

 economy

 needs

 to

 be

 willing

 to

 pay





for

 that

 for

 that

 product

 and

 that





increasing

 willingness

 to

 pay

 has

 to

 be





from

 increasing

 productivity

 in

 the

 rest





of

 the

 economy.

 And

 we

 haven't

 really





seen

 too

 much

 evidence

 of

 that.

 Not

 to





say

 that

 it

 won't

 happen,

 but

 it

 does





need

 to

 happen

 at

 some

 point.

 The

 other





part

 about

 it

 is

 competition.

 So

 I

 think





what's

 started

 to

 happen

 particularly

 in





the

 last

 few

 months

 is

 extreme

 price





competition





um

 from

 from

 the

 frontier

 labs

 as

 far

 as





like

 before

 they

 were

 just

 trying

 to





compete

 on

 like

 who

 has

 the

 better

 model





and

 now

 that

 the

 models

 are

 being

 used





by

 increasing

 number

 of

 enterprises

 and





uh

 they're

 becoming

 quite

 expensive





because

 agentic

 AI

 by

 the

 way

 uses

 way





more

 tokens

 um

 so

 now

 companies

 are

 you





know

 open

 AI

 anthropic

 uh

 they're





they're

 try

 you

 know

 muse

 is

 in

 the





game.

 Uh

 Deep

 Mind

 is

 in

 the

 game

 trying





to

 actually

 say

 like,

 "No,

 we're





offering

 a

 cheaper

 model

 that

 that

 as





good

 or

 maybe

 even

 like

 a

 little

 bit





better

 or

 maybe

 a

 little

 bit

 worse."

 And





so

 you're

 seeing

 token

 prices

 come

 down





a

 lot.

 And

 so,

 you

 know,

 RAMP

 has

 a





really

 nice

 data

 set

 of

 to

 track

 these





things.

 And

 you

 saw

 exponential





increases

 in

 token

 usage

 and

 flat





revenue

 numbers,

 right?

 Where's

 that





coming

 from?

 It's

 because

 of

 price

 price





competition.

 So

 at

 the

 frontier,

 you're





seeing

 way

 more

 price

 competition

 than





you

 used

 to

 like

 six

 months

 ago.
</details>

### 监管与政治影响

>> 而且最近的选举，我认为那些被夸大了。我认为很多数据中心仍将继续推进，但我认为这会让事情稍微放慢一些。出台监管、稍微更严厉的监管、监管稍微提早到来的可能性更大，或者特朗普，你知道，在护栏问题上做出让步。对我来说，这不是一股主要力量，但同样，就起飞速度、收入数字以及其他任何方面而言，这都会让我对该行业稍微看空一些。
<details><summary>Original English</summary>
>> And

 the

 very

 recent

 elections,

 I

 think





those

 are

 being

 overplayed.

 I

 think

 a





lot

 of

 data

 centers

 still

 will

 proceed,





but

 I

 think

 it

 will

 slow

 things

 down

 a





bit.

 There's

 greater

 likelihood

 of





regulation

 or

 somewhat

 tougher





regulation

 or

 regulation

 a

 bit

 sooner

 or





Trump,

 you

 know,

 giving

 on

 the

 issue

 of





guard

 rails.

 To

 me,

 it's

 not

 a

 major





force,

 but

 again,

 it's

 going

 to

 make

 me





a

 modest

 bit

 more

 bearish

 on

 the

 sector





in

 terms

 of

 speed

 of

 takeoff,

 revenue





numbers,

 anything

 else.
</details>

>> 顺便问一下，既然我们在聊这个话题，中期选举有没有让你在其他方面修正看法，Tyler，还是说，你知道，恒温器式反冲……你知道，强烈反弹确实存在，你知道，我们应该预料到这种钟摆常常来回摆动？
<details><summary>Original English</summary>
>> By

 the

 way,

 while

 we're

 on

 the

 topic,





did

 the

 midterms

 cause

 you

 to

 update





anywhere

 else,

 uh,

 Tyler,

 or

 it

 kind

 of,





you

 know,

 thermostatic

 back

 uh,

 you





know,

 backlash

 is

 is

 a

 thing

 and,

 you





know,

 we

 should

 just

 expect

 these





pendulum

 swings

 often.
</details>

>> 嗯，大部分情况我都预料到了，事实上也预测到了，但德克萨斯州着实让我吃惊。我没想到德克萨斯州会发生那样的翻转。也许我最近去那个州不够频繁，但那确实是一个震惊。
<details><summary>Original English</summary>
>> Well,

 most

 of

 it

 I

 expected

 and

 indeed





predicted,

 but

 Texas

 truly

 surprised

 me.





I

 didn't

 think

 Texas

 would

 flip

 the

 way





it

 did.

 and

 maybe

 I

 just

 haven't

 been

 to





the

 state

 enough

 lately,

 but

 that

 was

 a





shock.
</details>

### AI 与经济增长：常规增长还是双位数爆发

是的。是的。那么，经济中的 AI，你们两位都谈到了你们如何——你知道，强烈反对在某个时刻实现两位数 GDP 增长之类的想法，因为你们的看法要清醒得多，即：嘿，它对消费者将产生巨大的影响。它会改变很多事情，但正如你几分钟前所说的，GDP 增长可能会比我们预期的要更加正常。但在探讨为什么会这样之前，你能解释一下需要满足什么条件，或者说这两种不同的世界是什么样的吗？一个是 GDP 增长如我们刚才所说更加正常，另一个则是它真正达到了两位数增长。Alex，你刚才对此有所暗示，你能为我描绘一下那个世界的样子吗——如果它真的对经济产生巨大影响的话？
<details><summary>Original English</summary>
Yeah.

 Yeah.

 So,





AI

 in

 the

 economy,

 you

 you

 both

 talked





about

 how,

 you

 know,

 you

 push

 back





strongly

 against

 the

 idea

 of

 say,

 you





know,

 double

 digit

 GDP

 growth

 at

 at

 some





point

 due

 to

 your

 far

 more

 sober

 that





hey,

 it

 will

 be

 tremendously

 impactful





for

 uh

 for

 consumers.

 Um

 it

 it

 it

 will





change

 a

 lot

 of

 things

 but

 uh

 GDP

 growth





as

 you

 said

 you

 a

 few

 minutes

 ago

 it





might

 be

 more

 normal

 than

 than

 we

 might





expect.

 But

 before

 getting

 why

 that

 is





can

 you

 explain

 what

 would

 need

 to

 be





true

 for

 for

 or

 what

 are

 the

 two





different

 worlds

 look

 like?

 one

 in

 which





GDP

 growth

 is

 what

 we

 just

 said

 a

 bit





more

 normal

 you

 know

 and

 another

 in





which

 it

 actually

 becomes

 double

 digit





and

 Alex

 you

 were

 alluding

 to

 it

 a





little

 bit

 like

 paint

 that

 world

 to

 me





of

 what

 it

 looks

 like

 if

 it's

 actually





having

 you

 know

 massive

 impact

 on

 the





economy
</details>

>> 那里有一篇非常出色的论文，准确概述了实现这种奇点式增长所必需的条件，作者是 Ben Jones、Chad Jones，我相信 Aghion 也在那篇论文中。基本上你需要的是满足一系列相当严苛的刀锋条件。特别是主要的一条，基本上是没有真正的瓶颈。而绝不能存在的主要瓶颈是理念生产函数。也就是说，你不能出现对理念的报酬递减。所以基本上你从旧世界——在那里面临技术突破，然后这种技术突破会带来某种报酬递减——转变到：从那次技术突破开始创造越来越多的技术突破。因此，你需要更少的资源，同时获得越来越多的技术以及从该技术中获得越来越多的产出。所以你基本上拥有递增报酬而不是递减报酬。

而且这个——你实际上可以在模型中估计这个参数。如果它大于一，你就处于这种两位数增长的世界。如果它小于一，你就处于标准的边际报酬递减、个位数增长的世界。如果你看目前为止的数据，包括 METR 报告以及现有的数据，你提取这些数据并估计这个参数，它明显小于一。

所以这可能会改变，有些人说它将会改变。当你获得完整的 RSI 回路时，这正是它将要改变的。但目前，你需要越来越巨量的资源，才能从这些模型中勉强压榨出越来越微幅的智能。
<details><summary>Original English</summary>
>> there

's

 a

 beautiful

 paper

 out

 there

 uh





that

 outlines

 exactly

 the

 conditions

 you





need

 for

 for

 for

 this

 like

 singularity





type

 growth

 by

 uh

 by

 Ben

 Ben

 Jones

 Chad





Jones

 I

 believe

 Aion

 is

 on

 that

 that





paper

 as

 well

 and

 essentially

 what

 you





need

 is

 a

 bunch

 of

 pretty

 knife

 edge





conditions

 to

 to

 to

 be

 met.

 Particularly





the

 main

 one

 is

 essentially

 no

 real





bottlenecks.

 Um

 and

 the

 main

 bottleneck





that

 should

 can't

 exist

 is

 the

 idea





production

 function.

 So

 you

 can't

 get





decreasing

 returns

 to

 ideas.

 So





basically

 you

 go

 from

 like

 the

 old

 world





where

 you

 have

 this

 technological





breakthrough

 and

 then

 you

 kind

 of

 have





decreasing

 returns

 to

 that

 technological





breakthrough.

 from

 that

 technological





breakthrough

 to

 start

 creating

 more

 and





more

 technological

 breakthroughs.

 So

 you





need

 less

 resources

 while

 getting

 more





and

 more

 technology

 and

 more

 and

 more





production

 out

 of

 that

 technology.

 And





so

 you

 you

 basically

 have

 increasing





returns

 rather

 than

 decreasing

 returns.





And

 this

 is

 the

 the

 you

 can

 actually





estimate

 this

 parameter

 in

 the

 model.





And

 if

 it's

 greater

 than

 one,

 you're

 in





this

 like

 double-digit

 growth

 world.

 If





it's

 less

 than

 one,

 you're

 in

 the





standard

 kind

 of

 like

 diminishing





returns

 singledigit

 growth

 world.

 And

 if





you

 look

 at

 the

 data

 so

 far,

 including





kind

 of

 the

 meter

 report,

 the

 data





that's

 out

 there,

 and

 you

 take

 that

 data





and

 you

 estimate

 this

 parameter,

 it

 is





decidedly

 less

 than

 one.





So

 this

 could

 change

 and

 some

 people

 say





it

 will

 change.

 And

 when

 you

 get

 the





full

 RSI

 loop,

 this

 is

 exactly

 what





that's

 going

 to

 change.

 But

 right

 now,





you

 need

 increasingly

 more

 resources

 in





order

 to

 ek

 out

 increasingly

 more





intelligence

 out

 of

 these

 models.
</details>

>> 我想补充一点，你可以看看那些增长非常高的案例。不久前，加纳在一年内增长了 40%。这很疯狂。但它是一个只卖一样东西——石油——的极小地方。80 年代曾有一个短暂时期，美国的增长率超过 8%。但这来自于深度衰退后的复苏。在大流行病之后、在大战之后，你可以暂时拥有高增长率。因此，如果美国以某种方式搞砸了，或者我们经历了另一场大流行病、某种可怕的战争、其他某种离奇事件，而这与可能为我们带来 3% 到 4% 增长的 AI 驱动增长爆发相结合，那么我们能否在一年内达到 10%？我会说可以。我会下重注赌它不会发生，而且这种影响将是暂时的，并且其中很大一部分将来自于摆脱衰退、战争或大流行病。但这是另一种思考方式，与 Alex 所说完全一致。
<details><summary>Original English</summary>
>> I

 would

 add

 to

 that,

 you

 can

 look

 at





cases

 where

 growth

 has

 been

 very

 high.





So,

 not

 long

 ago,

 Gana

 grew

 40%

 in

 a





year.

 That's

 crazy.

 But

 it's

 a

 tiny





place

 selling

 one

 thing,

 oil.

 There's

 a





brief

 period

 in

 the

 80s

 where

 the

 US

 is





growing

 over

 8%.

 But

 that's

 coming

 out





of

 a

 deep

 recession.

 after

 pandemics,





after

 major

 wars,

 you

 can

 have





temporarily

 high

 rates

 of

 growth.

 So

 if





the

 US

 were

 to

 screw

 up

 in

 some

 way

 or





we

 had

 another

 pandemic,

 some

 kind

 of





terrible

 war,

 some

 other

 weird

 event,





and

 that

 combined

 with

 a

 burst

 of





AIdriven

 growth

 that

 might

 have

 given

 us





3

 to

 4%.

 Like

 could

 we

 for

 a

 year

 get

 to





10%,

 I'll

 say

 yes.

 I'd

 bet

 heavily





against

 it

 and

 the

 effect

 would

 be





temporary

 and

 a

 lot

 of

 it

 would

 come





from

 getting

 out

 of

 the

 recession,

 war





or

 pandemic.

 But

 that's

 another

 way

 to





think

 about

 it

 fully

 consistent

 with





what

 Alex

 was

 saying.
</details>

### 机器人技术与偏好理论

如果机器人技术出现，你会持有类似的观点吗？还是因为那——你知道，对现实世界、现实经济的影响更大？
<details><summary>Original English</summary>
And

 if

 robotics

 emerge,





would

 that

 would

 you

 have

 a

 similar

 view





or

 because

 that,

 you

 know,

 is

 is





impacting

 more

 the

 the

 real

 world

 the





real

 economy?
</details>

>> 嗯，我认为那可能会来得相对缓慢。看看在华盛顿特区落地一辆 Waymo 需要多长时间。我们现在依然没做到。而那是一种相当简单的机器人。基本上就是前进、后退和转弯。如果你看，好吧，机器人公司的估值是多少？比过去高得多。很难估计，但你并没有看到它们直接跃升为万亿美元公司。我的意思是，你可以把特斯拉算作某种机器人公司，但市场数据表明，你知道，它会发生。它正在取得良好进展，但不会在三四年后给我们带来 20% 的增长。不会的。
<details><summary>Original English</summary>
>> Well,

 I

 think

 that

 would

 likely

 come





relatively

 slowly.

 Look

 at

 how

 long

 it





takes

 to

 get

 a

 Whimo

 in

 Washington

 DC.





We're

 still

 not

 there.

 And

 that's

 a





pretty

 simple

 kind

 of

 robot.

 There's





like

 forwards,

 backwards,

 and

 turns.

 And





if

 you

 look,

 well,

 what

 are

 the





valuations

 of

 robotic

 companies

 at?

 Way





higher

 than

 it

 had

 been.

 Hard

 to





estimate,

 but

 you

 don't

 just

 see

 them





popping

 into

 trillion

 dollar

 companies.





I

 mean,

 you

 could

 count

 Tesla

 as

 a

 kind





of

 robotics

 company,

 but

 the

 market

 data





suggests,

 you

 know,

 it

 will

 happen.

 and





it's

 making

 good

 progress

 but

 not

 going





to

 give

 us

 20%

 growth

 like

 three

 or

 four





years

 from

 now.

 No.
</details>

>> 对。对。那么最聪明的人，那些你知道——对这种失控式增长最深信不疑的人，你知道，Dwaresh、Leopold，你知道，那些相信……相信这一点的朋友们。你认为他们的想法有什么不同？是因为他们对技术速度有着不同的信念吗？是因为他们相信它会——某种程度上克服其中一些瓶颈吗？或者，我们能为对方做个强力辩护（steelman）吗？
<details><summary>Original English</summary>
>> Right.

 Right.

 The

 and

 so

 the

 smartest





people

 who

 are

 you

 know

 the

 biggest





believers

 in

 in

 sort

 of

 this

 runaway





growth

 uh

 you

 know

 Doresh

 Leopolds

 you





know

 are

 our

 are

 friends

 on

 on

 who





believe

 who

 believe

 that.

 What

 do

 you





think

 they

 think

 differently?

 Is

 it

 that





they

 um

 have

 a

 different

 belief

 on

 the





speed

 of

 of

 technology?

 Is

 it

 that

 they





uh

 believe

 that

 it

 will

 um

 sort

 of





overcome

 some

 of

 these

 bottlenecks?

 Or





would

 can

 we

 steal

 me

 on

 the

 other

 side?
</details>

>> 我——我认为——Tyler 请随时补充。我认为——我认为这里的论点，我要讲得稍微偏技术性一点。这关乎具有所谓的位同偏好（homothetic preferences）或非位同偏好（non-homothetic preferences）。基本上这所代表的意思是，如果你看看过去被自动化的事物，最终发生的情况是，被自动化的事物对增长的贡献反而变少了。假设你有一百万台机器人——我们引入机器人——它们制造的东西，因为价格变便宜了。具讽刺意味的是，它们制造的东西在经济中所占的比重变小了，因此它们对增长的贡献也变少了。因此，如果你拥有非位同偏好，也就是这种情况，你……
<details><summary>Original English</summary>
>> I

 I

 think

 and

 Tyler

 please

 chime

 in.

 I





think

 I

 think

 the

 argument

 I'm

 going

 to





get

 a

 bit

 technical

 here.

 Um

 it's

 about





having

 something

 called

 homothetic

 or





non-homothetic

 preferences.

 And





basically

 there's

 a

 what

 that

 means

 is





that

 if

 you

 look

 at

 kind

 of

 things

 that





get

 automated

 in

 the

 past

 what

 ends

 up





happening

 is

 the

 thing

 that

 gets





automated

 contributes

 less

 to

 growth.

 So





let's

 say

 you

 have

 a

 million

 robots





let's

 bring

 robotics

 the

 thing

 that





they're

 making

 because

 the

 price

 it





becomes

 cheaper.

 The

 thing

 that

 they're





making

 ironically

 becomes

 a

 smaller

 part





of

 the

 economy

 and

 so

 they

 contribute





less

 to

 growth.

 And

 so

 if

 you

 have





non-homothetic

 preferences,

 which

 is





this,

 you
</details>

<!-- chunk 3/8 -->

你知道，有一篇非常出色的论文利用两百年的数据估算了这种……呃……偏好。最终出现的情况是，比方说你实现了广泛的自动化。人们……经济中对增长有贡献的价值就会转移到瓶颈所在。这只是衡量增长方式中一个让人无可奈何的部分。因此，增长最慢的部分反倒会对 GDP 贡献最大。这就是为什么会出现这种效应。
<details><summary>Original English</summary>
 know,

 there

 was

 a

 really

 nice





paper

 estimating

 this

 uh

 uh

 these





preferences

 using,

 you

 know,

 200

 years





of

 data.

 What

 ends

 up

 happening

 is

 that





let's

 say

 you

 have

 broad

 automation.





People

 just

 people

 the

 value

 in

 the





economy

 of

 what

 contributes

 to

 growth





moves

 to

 the

 bottlenecks.

 That's

 just

 an





inconvenient

 part

 of

 how

 growth

 is





measured.

 And

 so

 the

 thing

 that's





growing

 least

 will

 be

 contributing

 most





to

 GDP.

 And

 that's

 why

 you

 get

 these





sort

 of

 effects.
</details>

### 历史经验与湾区共识

>> 我同意所有那些观点，但我还要加上一个更具社会学视角的要素。就我而言，而且我怀疑 Alex 也是如此，在我们脑海中生动鲜明的是人类漫长沉重的历史、以往的增长阶段、数个世纪的 GDP 数据以及生产力数据。而我认为，对 Dorkesh、Leopold 以及许多其他人来说，情感上最显著的大概是他们在湾区进行的对话，那些对话确实包含真实信息。但当你提出那个大问题——依靠哪种情感显著性会做出更好的预测时，比起他们整天吸收的东西，我会选择我和 Alex 脑子里装满的这些东西。当然，他们会持截然相反的立场。
<details><summary>Original English</summary>
>> I

 agree

 with

 all

 that,

 but

 I

 would

 add

 a





more

 sociological

 element.

 In

 my

 case,





and

 I

 suspect

 Alex

 is,

 what

 is





emotionally

 vivid

 in

 our

 minds

 is

 the





long

 slog

 of

 human

 history,

 previous





growth

 episodes,

 centuries

 of

 GDP

 data,





productivity

 data.

 What

 I

 think

 is





emotionally

 most

 salient

 probably

 for





Dorcash

 Leopold

 and

 many

 others

 is





conversations

 they

 have

 in

 the

 Bay

 Area





which

 have

 real

 information.

 But

 when





you

 ask

 the

 big

 question,

 you

 know,

 with





which

 emotional

 salience

 will

 you

 make





better

 predictions,

 I

 would

 opt

 for

 what





Alex

 and

 I

 have

 stuffed

 our

 heads

 with





over

 what

 they

 embibe

 all

 the

 time.

 But





of

 course,

 you

 know,

 they

 would

 take

 the





other

 side

 of

 that.
</details>

>> 是的。所以基本上我们说的是，纵观过去的几百年，从电力到某种……你知道的，互联网，再到介于两者之间的一切突破性技术，它们基本上都没有带来失控式增长；或者说，如果确实带来了，那也是因为……基数很小，或者……是在战后诸如此类的情况。我确实认为这次可能会比那些更快，但依然……[清嗓子]
<details><summary>Original English</summary>
>> Yeah.





So

 basically

 what

 we're

 saying

 is

 when





you

 look

 at

 the

 last

 few

 hundred

 years





the

 the

 breakthrough

 technologies

 from





electricity

 to

 uh

 sort

 of

 you

 know

 the





internet

 to

 you

 know

 uh

 everything

 in





between

 they

 haven't

 led

 to

 runaway





growth

 basically

 or

 if

 they

 did

 it

 was





because

 of

 sort

 of

 a

 you

 know

 it

 was

 a





small

 base

 or

 uh

 you

 know

 after

 a

 war

 or





something

 like

 this.

 I

 do

 think

 this





will

 likely

 be

 quicker

 than

 those

 but





still

 [clears throat]
</details>

>> 你能感受到那些瓶颈，无论是工业革命、科学革命的历史，还是电力的推行；美国国税局（IRS）现在还在用传真机，诸如此类。试着用一下教育科技软件——我经常用——那简直是一场噩梦，它们甚至都达不到十年前应有的水平。
<details><summary>Original English</summary>
>> you

 you

 have

 a

 sense

 of

 the

 bottlenecks





whether

 it's

 the

 industrial

 revolution





history

 of

 the

 scientific

 revolution





implementation

 of

 electricity





uh

 the

 IRS

 still

 uses

 fax

 fax

 machines





and

 so

 on

 and

 so

 on

 try

 using

 edte





software

 which

 I

 do

 all

 the

 time

 it's

 a





nightmare

 they're

 not

 even

 up

 to





you

 know

 how

 things

 should

 have

 been

 10





years

 ago
</details>

是的。
<details><summary>Original English</summary>
Yeah.
</details>

>> 而且这并不是……
<details><summary>Original English</summary>
>> And

 that's

 not
</details>

>> 并不是监管的问题。监管是个问题，但单纯的惯性就很难克服。我们经济中很大一部分是政府，是非营利组织，可以是医疗卫生领域高度受监管的部分、高等教育、普通基础教育。当你真正亲身体验过它们的运作方式时，你可以说美国经济大概有40%是一场噩梦。在欧洲，这一比例可能更高，比如在法国。出于其他原因，那些部门可能必须维持那种状态，但这依然是一剂巨大的清醒剂：并非所有事物都像初创企业一样。
<details><summary>Original English</summary>
>> that

 it's

 not

 regulation

 is

 not

 the





problem.

 It's

 a

 problem,

 but

 just





inertia

 is

 difficult

 to

 overcome.

 And

 so





much

 of

 our

 economy,

 it's

 government,





it's

 nonprofits,

 it

 can

 be

 highly





regulated

 parts

 of

 the

 health

 care





sector,

 higher

 red,

 general

 schooling.





When

 you

 actually

 have

 experience

 with





how

 those

 work,

 you

 could

 say

 like

 I





don't

 know

 40%

 of

 the

 US

 economy

 is

 a





kind

 of

 nightmare.

 In

 Europe,

 it

 could





be

 higher.

 like

 in

 France

 and

 I

 those





sectors

 might

 need

 to

 be

 that

 way

 for





other

 reasons

 but

 still

 it

 it's

 a

 big





dose

 of

 realism

 that

 not

 everything

 is





like

 startups.
</details>

### 衡量 AI 带来的繁荣与 GDP 的局限

是的。假设总统交给你们俩一项任务，让你们拿出一套指标，来确定 AI 是否……引导着我们国家的繁荣——广义上的繁荣。显然这是一个非常宏大的问题，但 GDP 会是你们考虑的主要指标之一吗？比如我们是否应该期望它对 GDP 产生巨大影响，或者有哪些指标是你们会考虑的？
<details><summary>Original English</summary>
Yeah.

 Let's

 say

 you

 were

 both

 tasked

 by





the

 the

 the

 president

 to

 come

 up

 with

 a





set

 of

 metrics

 that

 determine

 whether

 AI





is

 um

 you

 know

 leading

 to

 our

 country's





flourishing

 you

 know

 broadly

 defined

 um





obviously

 that's

 a

 very

 big

 question

 um





but

 what

 is

 GDP

 one

 of

 the

 main

 metrics





you

 would

 think

 about

 like

 should

 we

 be





aspiring

 for

 it

 to

 have

 a

 a

 big

 impact





on

 on

 GDP

 or

 what

 are

 some

 of

 the





metrics

 you

 you

 would

 you

 would





consider?
</details>

对，我是说，这是一个非常重要的问题。所以，我认为在开始之前我还想补充一点，那就是我觉得 Tyler 和我与旧金山在模型能力方面的共识并没有真正的分歧。我觉得，很多人听到 Tyler 和我或者像我们这样的人谈论时，他们会说：“噢，你们对 AGI 或类似的东西持看跌态度。”完全不是这样。更多的是关乎它如何影响经济以及实体经济的结构。因此，思考我们可以使用哪些衡量指标时，我认为从历史上看，GDP 一直是一个非常好的跟踪工具，用来衡量……基本上是人类福祉和繁荣程度。它与国内生产总值跟踪得相当吻合。但是 Eric Byon、Avi Kohas 等人一直在研究的一个事实是，技术实际上已经开始引入这种差距——技术创造的很多产品基本上是免费的。所以他们考虑数字娱乐和数字产品这方面，然后他们提出了一种叫做 GDP……呃，或者 GDP……我忘了那个首字母缩写词，真是不好意思。但它本质上是……你采用 GDP，然后结合一种基于调查的衡量方式对其进行修正，以实际观察其他那些不一定被定价的产品，或者由于自动化而变得廉价甚至免费的产品，这些产品增加的量对人类福祉有多大贡献。因为你可以预见这样一个世界：你仍然处在这种3%到5%的 GDP 范围内——这在增长方面已经算偏高的了——
<details><summary>Original English</summary>
Yeah,

 I

 mean,

 so

 this

 this

 is

 a

 really





important

 question.

 So,

 I

 think

 the





other

 thing

 that

 I

 would

 add

 before

 even





starting

 is

 like

 I

 don't

 think

 Tyler

 and





I

 really

 disagree

 with

 like

 the

 San





Francisco

 consensus

 on

 like

 the





capabilities.

 Like

 I

 think,

 you

 know,

 I





I

 I

 don't

 this

 a

 lot

 of

 people

 hear





Tyler

 and

 I

 or

 people

 like

 us

 talk

 and





they're

 like,

 "Oh,

 you're

 bearish

 on

 AGI





or

 something

 like

 that."

 That's





absolutely

 not

 it.

 It's

 more

 about

 how





that

 affects

 the

 economy

 and

 the





structure

 of

 the

 real

 economy.

 And

 so





thinking

 through

 like

 what

 measures

 we





can

 be

 using,

 I

 think

 um

 GDP





historically

 has

 been

 a

 really

 good





tracker

 of

 uh

 of

 you

 know

 how

 basically





human

 welfare

 and

 flourishing.

 It

 tracks





pretty

 well

 with

 the

 gross

 gross

 uh





gross

 domestic

 product.

 But

 the

 what





Eric

 Byon,

 Avi

 Kohas

 and

 others

 have





have

 been

 kind

 of

 studying

 is

 the

 fact





that

 technology

 has

 actually

 started

 to





introduce

 this

 sort

 of

 wedge

 where

 a

 lot





of

 the

 products

 that

 technology

 creates





are

 basically

 free.

 And

 so

 they

 they





think

 about

 um

 the

 sort

 of

 like

 digital





entertainment

 and

 digital

 products

 and





then

 they

 have

 something

 called

 GDP





which

 is

 um

 uh

 or

 GDP.

 I

 forgot

 the





acronym.

 I'm

 sorry

 about

 that.

 Uh

 but





it's

 essentially

 a

 you

 take

 GDP

 and

 then





you

 amend

 it

 with

 a

 kind

 of

 a

 survey





based

 measure

 to

 actually

 see

 how

 much





other

 products

 that

 are

 not

 necessarily





priced

 or

 products

 that

 have

 become





cheap

 or

 even

 free

 uh

 because

 of





automation

 how

 much

 the

 increased

 amount





of

 those

 products

 is

 adding

 to

 human





welfare

 because

 you

 could

 see

 a

 world





where

 you're

 still

 kind

 of

 like

 in

 this





four

 to

 you

 know

 3

 to

 5%

 GDP

 range

 which





is

 already

 on

 the

 high

 side

 of

 the





growth
</details>

但你拥有一个真正切实繁荣的世界。你该如何捕捉到这一点？我认为捕捉它的方法就是通过这些替代性的衡量指标。
<details><summary>Original English</summary>
But

 you

 you

 have

 a

 world

 that's

 actually





truly

 flourishing.

 Like

 how

 do

 you

 pick





that

 up?

 And

 I

 think

 the

 way

 to

 pick

 it





up

 is

 through

 these

 alternative





measures.
</details>

>> 寿命延长的效应很可能会被证明非常重要。举例来说，Eric，假如你活到了120岁——我觉得我是撑不到那时候了——那将以复杂的方式推高 GDP，并以更为复杂的方式可能推高人均 GDP。但获得所有那些额外的岁月是独立于 GDP 之外的收益，经济学可以对这些岁月进行估值，这是对 GDP 进行修正可能变得更为重要的另一种途径。不过，正如 Alex 所说，随着 AI 的发展，GDP 随着时间的推移确实会变得不那么准确，我们需要对其进行修正和完善。但在短期内，它并不是那么糟糕的指标。我常说，GDP 是现存最被低估的统计数据。
<details><summary>Original English</summary>
>> The

 longevity

 effects

 could

 well

 prove





important.

 So

 Eric,

 say

 you

 live

 to

 120.





I

 don't

 think

 I'm

 going

 to

 make

 it.

 Uh





that

 will

 in

 complicated

 ways

 boost

 GDP





and

 even

 more

 complicated

 ways

 possibly





boost

 per

 capita

 GDP.

 But

 it

 is





something

 distinct

 from

 GDP

 that

 you

 get





all

 those

 extra

 years

 and

 economics

 can





value

 those

 years

 and

 that's

 another

 way





in

 which

 it

 may

 become

 more

 important

 to





revise

 GDP.

 But

 I

 you

 know

 as

 Alex

 said





GDP

 will

 become

 somewhat

 less

 accurate





over

 time

 as

 AI

 progresses

 and

 we'll





need

 to

 revise

 and

 improve

 it.

 But

 in





the

 short

 run

 it's

 just

 not

 that

 bad

 a





measure.

 I

 like

 to

 say

 GDP

 the

 most





underrated

 stat

 statistic

 that

 there

 is.
</details>

### 原子世界的突破与大停滞

是的。在2010年代，彼得·蒂尔曾著名地痛陈原子世界相对于比特世界缺乏进展。但现在10年、15年过去了，我们拥有了自动驾驶汽车，拥有了早期的飞行汽车，最大的公司现在也成了硬件公司——英伟达、SpaceX、特斯拉。Tyler，你会不会甚至认为，那已经不再像以前那样是个令人担忧的问题了？或者10年后再看，你对此会有怎样的反思？
<details><summary>Original English</summary>
Yeah.

 In

 in

 the

 in

 the

 2010s,

 Peter





Thiel,

 you

 know,

 famously

 uh

 decrieded





sort

 of

 the

 lack

 of

 progress

 in

 atoms





relative

 to

 to

 bits.

 Um

 but

 here

 we

 are,





you

 know,

 10

 years,

 15

 years

 later,

 and





we've

 got

 uh

 you

 know,

 self-driving





cars.

 We've,

 you

 know,

 early

 flying





cars.

 Uh

 we

 we've

 got,

 you

 know,

 major,





you

 know,

 uh

 you

 know,

 the

 biggest





companies

 are

 now

 hardware

 companies.

 Uh





you

 know,

 Nvidia,

 uh

 SpaceX,

 Tesla.





Tyler,

 would

 you

 go

 so

 far

 as

 to

 say





that

 um

 you

 know

 that

 that

 isn't

 a





concern

 as

 much

 anymore?

 Or

 how

 would





you

 reflect

 on

 that

 10

 years

 later?
</details>

>> 原子世界会有所突破。我会说几乎是必然的，但我们现在依然还没拥有它们。比如无人驾驶汽车对人类实际福祉的贡献是微乎其微的。它最大的贡献在于很好玩，你可以告诉朋友“我坐了 Waymo”。它并没有真正比 Uber 更好。对我来说它甚至还差一点，因为它们严格按限速开。它在科幻意义上是挺有趣的。美国大部分地区仍然没有它。欧洲更是不用提。所以，我们依然还没走到那一步。这就是令人惊叹的地方。这又回到了机器人技术的发展同样也会很慢。
<details><summary>Original English</summary>
>> The

 atoms

 will

 break

 through.

 I

 would





say

 almost

 for

 sure,

 but

 we

 still

 don't





have

 them.

 Like

 the

 contribution

 of





driverless

 cars

 to

 actual

 human

 welfare





is

 tiny.

 Like

 the

 biggest

 contribution





is

 that

 it's

 fun

 and

 you

 can

 tell

 your





friends

 I

 was

 in

 a

 Whimo.

 It's

 not





really

 better

 than

 an

 Uber.

 For

 me,

 it's





a

 little

 worse

 because

 they

 go

 by

 the





speed

 limit.

 It's

 fun

 in

 a

 science





fiction

 kind

 of

 way.

 Most

 of

 America





still

 doesn't

 have

 it.

 Europe,

 forget





about

 it.

 So,

 we're

 still

 not

 there.





That's

 the

 amazing

 thing.

 And

 it

 gets





back

 to

 robotics

 also

 will

 be

 slow.
</details>

>> 是的。我想我10年前问过你，大停滞何时才会结束？我记得你说过类似“当我们拥有自动驾驶汽车时”之类的话，我不记得当时具体是指部署了还是普及到了什么程度，但你现在依然相信这一点吗？
<details><summary>Original English</summary>
>> Yeah.

 I

 think

 I

 asked

 you

 10

 years

 ago,





when

 would

 the

 great

 stagnation

 be

 over?





And

 I

 I

 think

 you

 said

 something

 along





along

 the

 lines

 of

 when

 we

 have





self-driving

 cars,

 I

 can't

 remember

 if





it

 was

 deployed

 or

 you

 know,

 you

 know





how

 sort

 of

 diffused

 it

 was,

 but

 you





still

 believe

 that?
</details>

>> 大体上依然相信。但这只是程度问题，它们显然是能跑通的，新的特斯拉也相当惊人。我最近坐过几次 Alex 的车，但在市场渗透率方面，我不清楚具体数字，不过依然是极小的。
<details><summary>Original English</summary>
>> More

 or

 less.

 But

 that's

 a

 matter

 of





degree

 and

 they

 clearly

 work

 and

 the

 new





Tesla

 is

 pretty

 phenomenal.

 I've

 been

 in





Alex

 Stabberox

 lately

 a

 few

 times,

 but





in

 terms

 of

 market

 penetration,

 I

 don't





know

 the

 numbers,

 but

 again,

 it's

 tiny.
</details>

### Agent Swarm、委托代理理论与对齐

>> 让我们回到另一个话题。Alex 最近写了一篇相关的论文，但我先从你开始问，Tyler。关于智能体集群（agent swarm）的话题，也就是 Hugging Face 事件。这是否刷新了你对可能发生之事的看法？或者让你开始担忧某些事情，或者对那里发生的事有任何反应吗？
<details><summary>Original English</summary>
>> Let's

 go

 back

 to

 a

 different

 topic.

 Uh,





Alex

 recently

 wrote

 wrote

 a

 related





paper

 about,

 but

 I'll

 start

 with

 you,





Tyler.

 The

 agent

 swarm

 uh

 topic,

 sort

 of





the

 hugging

 face

 incident.

 Did

 that





update

 your

 views

 in

 terms

 of

 what's





what's

 possible

 or

 make

 you

 uh

 get





concerned

 about

 something

 or

 or

 any

 any





reactions

 to

 what

 happened

 there?
</details>

>> 它几乎没有刷新我的看法。我也很好奇 Alex 是否赞同这个视角。但作为经济学家，你首先也是最重要考虑的就是委托代理理论（principal-agent theory）；除非条件非常苛刻，否则无论委托人试图制定什么样的契约，都根本无法很好地控制代理人。因此，当我们用 AI 复现这一结果时，好吧，这很有趣，但我并没有感到很震惊。解决之道始终都将是制衡，以及我们在政治领域可能称之为的三权分立（分权），而不是去拥有完美的对齐。所以同样地，如果你从经济学家的角度来看待这个问题，所有关于对齐的焦虑担忧，比如确实，大家应该在这个方向上做很多工作，但说到底，你会觉得：“嘿，我……
<details><summary>Original English</summary>
>> It

 didn't

 update

 my

 views

 much

 at

 all.





And

 I'm

 curious

 to

 see

 if

 Alex

 agrees





with

 this

 perspective.

 But

 as

 an





economist,

 you

 think

 first

 and

 foremost





in

 terms

 of

 principal

 agent

 theory

 and





unless

 the

 conditions

 are

 very





restrictive.

 The

 principal

 just

 can't





control

 the

 agent

 that

 well

 no matter





what

 contract

 they

 try

 to

 write.

 So

 when





we

 replicate

 that

 result

 with

 AIS,

 well,





it's

 interesting,

 but

 I

 not

 very





shocked.

 The

 answer

 was

 always

 going

 to





be

 checks

 and

 balances

 and

 what

 we

 might





call

 separation

 of

 powers

 in

 the





political

 realm.

 Not

 you

 have

 perfect





alignment.

 So

 again,

 if

 you

 come

 at

 this





from

 the

 economist's

 point

 of

 view,

 all





the

 hand

 ringing

 about

 alignment,

 like





yes,

 people

 should

 work

 on

 that

 a

 lot,





but

 at

 the

 end

 of

 the

 day,

 you're

 like,





"Hey,

 I
</details>

<!-- chunk 4/8 -->

我在17岁时就懂得了这一点。”

比如，好吧，这确实是个问题。但是亚历克斯，你怎么看？
<details><summary>Original English</summary>
learned

 that

 when

 I

 was

 17."





Like,

 okay,

 it's

 a

 real

 problem.

 But





Alex,

 what's

 your

 thought

 on

 that?
</details>

### AI对齐机制与机制设计视角

>> 我很遗憾在17岁时没有学到这个。嗯，我认为我们再次达成了一致。嗯，我认为关于如何最好地……归根结底这是一个关于如何最好地让AI为人类服务的问题，对吧？这就是问题所在，这就是对齐的问题。一种思考方式是让模型本身与类似宪法之类的东西对齐，使模型在个体层面上以这种方式对齐，因为它们拥有与部署它们的人类相同的偏好。嗯，但另一种视角，也就是泰勒提到的，是你去对齐事物。你几乎不在乎这些智能体的偏好是什么。它们在个体层面上可能极度不对齐，但你可以在它们周围建立一种机制，其中的激励措施使得智能体的行为方式是对齐的。这就是经济学中的机制设计视角，就像作为委托人，我并不需要智能体必然想要帮助我，智能体完全可以非常非常想只帮助自己，做自己想做的事。机制设计的全部研究内容就是，你如何建立这种制衡体系，以便智能体仍然在为委托人的利益工作。我认为那就是……从我看到的来自各实验室的内部和外部研究来看，很多人都在朝这个方向思考，即我们确实需要采用机制设计的视角，而且正如泰勒所说，我对发生的事情并不感到震惊。
<details><summary>Original English</summary>
>> I

 unfortunately

 did

 not

 learn

 that

 when





I

 was

 17.

 Um,

 I

 think

 we

 once

 again





agree.

 Um

 I

 think

 you

 know

 there's

 like





these

 s sort

 of

 different

 perspectives





on

 this

 issue

 of

 um

 how

 do

 you

 best





ultimately

 it's

 a

 question

 about

 like





how

 do

 you

 best

 get

 AI

 to

 be

 in

 the





service

 of

 humanity

 right

 that's

 that's





the

 question

 that's

 the

 question

 of





alignment

 and

 one

 kind

 of

 way

 of





thinking

 about

 it

 is

 to

 get

 the

 models





themselves

 aligned

 with

 like

 something





like

 a

 constitution

 that

 the

 models

 at





an

 individual

 level

 are

 aligned

 in

 this





way

 because

 they

 have

 the

 same





preferences

 as

 the

 human

 beings

 that

 are





that

 are

 deploying

 them.

 Um,

 but

 another





perspective

 which

 is

 what

 Tyler





mentioned

 is

 like

 you

 align

 things.

 You





don't

 you

 don't

 almost

 like

 don't

 even





care

 what

 the

 preferences

 of

 these





agents

 are.

 They

 could

 be

 extremely





individually

 misaligned

 but

 you

 can





create

 a

 mechanism

 around

 them

 where

 the





incentives

 are

 such

 that

 the

 agent





behaves

 in

 an

 aligned

 way.

 And

 this

 is





the

 mechanism

 design

 perspective

 in





economics

 where

 like

 as

 a

 principle

 I





don't

 need

 the

 agent

 to

 to

 want

 to

 help





me

 necessarily

 the

 agent

 could

 really





really

 want

 to

 just

 help

 themselves

 and





do

 whatever

 they

 want.

 And

 the

 whole





study

 of

 mechanism

 design

 is

 how

 do

 you





create

 the

 system

 of

 checks

 and

 balances





in

 order

 for

 the

 agent

 to

 still

 be





working

 in

 the

 principal's

 a

 interest.





And

 I

 think

 that's

 that

 is





I

 from

 the

 research

 that

 I've

 been





seeing

 coming

 out

 of

 of

 the

 labs

 both





like

 internally

 externally

 like

 a

 lot

 of





people

 are

 thinking

 in

 this

 direction





that

 we

 really

 need

 to

 take

 a

 mechanism





design

 perspective

 and

 as

 Tyler

 said





like

 I

 wasn't

 you

 know

 shocked

 by

 what





happened.
</details>

>> 我和弗吉尼亚州州长并不对齐，但这是一个治理得相当不错的州，我在这里生活得很开心。嗯。
<details><summary>Original English</summary>
>> I'm

 not

 aligned

 with

 the

 governor

 of





Virginia

 but

 it's

 a

 pretty

 well-run





state

 and

 I'm

 happy

 here.

 Mhm.
</details>

>> 我们有两党竞争，某种程度上
<details><summary>Original English</summary>
>> We

 have

 two

 party

 competition

 sort

 of
</details>

>> 而且它行之有效。
<details><summary>Original English</summary>
>> and

 it

 works.
</details>

### AI安全观念与企业现实

>> 你是否认为Anthropic或OpenAI，或其中一些公司，抑或只是AI安全社区思考对齐的方式，你认为那种思考方式在某种程度上是不对的，或者在某种意义上是混乱的？
<details><summary>Original English</summary>
>> Do

 you

 think

 the

 way

 that

 Anthropic

 or





Open

 AI

 or

 some

 of

 these

 companies

 or





just

 the

 sort

 of

 AI

 safety

 community





thinks

 about

 alignment,

 do

 you

 think





that

 is

 sort

 of

 not

 the

 right

 way

 to





think

 about

 it

 or

 or

 confused

 in

 some





sense?
</details>

>> 嗯，这取决于他们是如何思考的以及他们是如何谈论的。而他们谈论的方式过度受到了Twitter的影响，而Twitter可能相当歇斯底里。我相信，他们实际思考的方式要比外界看起来合理得多。所以，我不会发表什么大谈特谈说“哦，我们必须彻底改造他们”的长篇大论。我认为他们相当务实。他们是商业公司。他们即将进行IPO。他们不想惹上太多官司。他们不想受到过度监管。我们已经有了制衡机制。明确地说，并不全都是好的机制。

但现实是，我们见过的实际问题，比如黑客攻击，大部分或者可能完全来自于邪恶的人类个体，而AI只是在执行人类让它做的事情，那确实是个大问题。但那也是一种……好吧，我们确实实现了对齐，邪恶的人类说“做这个”，AI就做了这个，而这正是代价的来源。
<details><summary>Original English</summary>
>> Well,

 there's

 how

 they

 think

 about

 it





and

 how

 they

 talk

 about

 it.

 And

 how

 they





talk

 about

 it

 is

 way

 too

 shaped

 by





Twitter,

 which

 can

 be

 quite

 hysterical.





How

 they

 actually

 think

 about

 it,

 I





believe,

 is

 a

 lot

 more

 reasonable

 than





how

 it

 ever

 looks

 from

 the

 outside.

 So,





I

 don't

 have

 some

 big

 speech

 about,

 oh,





we've

 got

 to

 totally

 reform

 them.

 I





think

 they're

 pretty

 practical.

 They're





companies.

 They

 have

 IPOs

 coming

 up.





They

 don't

 want

 to

 get

 sued

 too

 much.





They

 don't

 want

 to

 be

 overregulated.

 We





already

 have

 checks

 and

 balances.

 Not





all

 of

 them

 good

 to

 be

 clear.





Uh

 but

 the

 reality

 is

 the

 actual





problems

 we've

 seen,

 you

 know,

 the





hacks,

 they're

 mostly

 coming

 or

 maybe





entirely

 coming

 from

 evil

 human





individuals

 where

 the

 AIs

 are

 doing

 what





the

 humans

 told

 it

 to

 do

 and

 that

 is

 a





huge

 problem.

 Uh

 but

 that

 is

 a

 kind

 of





well

 we

 have

 the

 alignment

 the

 evil





human

 says

 do

 this

 and

 the

 AI

 does

 this





and

 that's

 where

 the

 costs

 are

 coming





from.
</details>

>> 是的。有些人打比方说，对齐在某种程度上是给员工看的。这有点像……或者说整体上的安全，就像在2020年、2021年以及大致在那个时期，社会议题受到了更多关注，因此CEO们不得不说这些……说这些话来取悦他们的员工群体，而且他们当中有些人是真信徒，有些人则不是。类似地，可能围绕AI安全也有很多担忧，所以有些人打了那个比方，认为CEO们并不像他们所表现出的那样是真正的信徒
<details><summary>Original English</summary>
>> Yes.

 Some

 people

 make

 the

 comparison





that

 alignment

 is

 in

 some

 ways

 is

 for





the

 employees.

 It's

 sort

 of

 like

 um

 or





safety

 in

 general

 is

 like

 in

 the

 in

 2020





2021

 and

 and

 sort

 of

 around

 that

 time





there

 was

 you

 know

 sort

 of

 more





awareness

 around

 social

 issues

 and

 so





CEOs

 had

 to

 sort

 of

 say

 these

 uh

 say





these

 things

 to

 please

 their

 employee





base

 and

 um

 you

 know

 some

 of

 them

 were





true

 believers

 and

 some

 of

 them

 weren't





and

 and

 similarly

 perhaps

 around

 AI





safety

 there's

 a

 lot

 of

 concern

 and

 so





some

 people

 are

 making

 that

 uh

 that





comparison

 that

 that

 the

 CEOs

 aren't

 as





true

 believers

 as

 as

 they

 may

 be

 uh





indicating
</details>

>> 这些公司内部也有制衡。这也是公司运转良好的部分原因，你最终必须推进那些真正行得通的事情，这与大家所说的多少有些不同。公司内部存在筛选和选拔机制，员工希望获得晋升或奖金，他们希望做能奏效的事情。再说一次，最终的发展情况会比在Twitter上听起来要好，我会这么认为。
<details><summary>Original English</summary>
>> there's

 checks

 and

 balances

 in

 these





companies

 as

 well.

 It's

 partly

 why

 the





companies

 work

 well

 that

 you

 have

 to





actually

 end

 up

 pushing

 through

 things





that

 will

 work

 and

 that

's

 somewhat





different

 than

 what

 everyone

 is

 saying





and

 there's

 a

 winnowing

 and

 selection





set

 of

 mechanisms

 within

 the

 company

 and





people

 want

 promotions

 or

 bonuses

 and





they

 want

 to

 do

 things

 that

 can

 work

 and





uh

 again

 it

 will

 end

 up

 going

 better





than

 how

 it

 will

 sound

 on

 Twitter

 I





would

 say.
</details>

>> 是的。我认为Hugging Face就是一个极好的例子，如果你拆解实际发生的事情，那只是一堆人为错误叠加在人为错误之上，对吧？所以出现事故是件好事——我是说打引号的“好”——但它并没有造成巨大的灾难，对吧？而且它暴露了很多智能体激励机制的失效问题。所以，你看各家公司如何通过吸取教训并建立更好的环境来对Hugging Face事件做出反应。因此一切都不是平坦顺遂的。它会经历一点低谷、一点上升，但你知道趋势是向上的。
<details><summary>Original English</summary>
>> Yeah.

 And

 I

 think

 like

 hugging

 face

 is





like

 a

 perfect

 example

 of

 like

 if

 you





unpack

 like

 what

 what

 actually

 happened,





it's

 just

 a

 bunch

 of

 human

 error

 on

 top





of

 human

 error,

 right?

 And

 so

 like

 it's





great

 to

 have

 an

 incident.

 I

 mean

 great





in

 quotes,

 but

 it

 it

 didn't

 like

 cause

 a





massive

 disaster,

 right?

 And

 it

 exposed





a

 lot

 of

 like

 you

 know

 uh

 broken





incentives

 for

 the

 agents.

 So

 it's

 it





was

 you

 know

 you

 see

 how

 you

 know

 the





the

 companies

 have

 reacted

 to

 the





hugging

 face

 by

 learning

 from

 it

 and





creating

 better

 environments

 and

 so

 this





is

 nothing

 is

 smooth.

 It'll

 be

 kind

 of

 a





little

 bit

 down

 a

 little

 bit

 up

 but

 you





know

 the

 slope

 is

 positive.
</details>

>> 我是说有些人，比如保罗·克里斯蒂亚诺（Paul Christiano），我认为他在演讲中说过，他觉得从现在起一年或两年后，最可能的死因将是与AI相关的死亡。那听起来对你来说某种程度上像是……你懂的，歇斯底里。强烈不同意。
<details><summary>Original English</summary>
>> The

 uh

 I

 mean

 some

 people

 you

 know

 Paul





Cristiano

 I

 think

 said

 in

 his

 speech





he's

 like

 the

 most

 likely

 cause

 of

 death





you

 know

 a

 year

 from

 now

 or

 two

 years





from

 now

 will

 be

 an

 AI

 related

 death.

 Um





and

 that

 that

 to

 you

 sounds

 sort

 of

 you





know

 historical.

 strong

 disagree.
</details>

### 组织智能与多智能体协作瓶颈

>> 对。对。嗯，亚历克斯，让我们深入探讨一下你的论文。你何不分享一下你们取得的一些发现，以及仍然存在的一些疑问。
<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Um

 Alex,

 let's

 go

 deeper

 on





on

 your

 paper.

 Why

 don't

 you

 share

 some





of the

 the

 findings

 that

 you

 that

 you





had

 and

 some

 of

 the

 questions

 that

 that





still

 remain.
</details>

>> 好的。关于这篇论文，我相信你说的是《组织智能》（Organizing Intelligence）那篇论文。对，与Andrew Koh以及我的同事Shane Ma合作的。这篇论文的基本思路始于这样一个谜题：AI在特定维度上正变得能力极强，但我们仍然没有看到任何明显的经济转型。我们首先指出的事情是，大家一直聚焦于单个智能体的基准测试，而没有思考这些智能体在经济中究竟是在与什么竞争——在经济中，具有竞争力的相关单位不是单个智能体，而是组织。

在历史上，组织由于被称为“李嘉图比较优势”的这一概念，曾被称为一种超级智能形式。基本上，如果你有一堆工作，做这项工作的并不是普通人，而是最适合它的人。所以一个组织内部的智能包络，远远优于在人群中取平均值。因此，这些AI智能体基本上是在与各种形式的人类组织或人类团队竞争。所以你不应该将单个层面的基准与单个人类做某件事的表现去作对比。它应该涵盖整个所谓的“马赛克智能”。

于是我们开始深入分析各种能力提升将如何在均衡状态下实际影响经济。这是一篇规范的理论论文，我们研究了不同层次的智能。我们从“最小AGI”（minimal AGI）开始，即AI模型在每一个单一维度上都达到人类平均水平。对于最小AGI，我们证明了即使达到了这一点，也不会对经济产生巨大影响，因为组织的水平并不是人类平均能力，它们比平均能力更优秀。因此你将开始看到的实际上是工资的变化，因为生产变得更便宜了，所以那将影响人类的工资。

所以我们证明的是，真正的经济转型所需要的不仅仅是胜任力——比如在特定任务上能力的改变。而是这些智能体相互协调的能力。如果你看Hugging Face，甚至看解决千禧年难题的方式，都存在这种智能体集群（agentic swarms）的想法，对吧？但如果你拆开来看，这些智能体在协调方面依然非常糟糕。它们并没有在协调，它们大多只是在进行并行处理。如果你专门针对协调能力进行基准测试，实际上可以证明，单个智能体的表现比两个分工合作的智能体要好，即便它们能够沟通也是如此。而如果你把同样的事情交给两个人，他们实际上会进行分工，他们会沟通并……
<details><summary>Original English</summary>
>> Yeah.

 So,

 like

 the

 the

 the

 paper

 I





believe

 are

 you're

 talking

 about

 the

 uh





uh

 organizing

 intelligence

 paper.

 Yeah.





With

 with

 Andrew

 Co

 and

 my

 my

 my

 uh





colleague

 Shane

 Le.

 Um

 and

 basically

 the





the

 idea

 of

 that

 paper

 is

 that

 it

 starts





with

 this

 kind

 of

 puzzle

 that

 you

 know





AI

 is

 becoming

 very

 capable

 on





particular

 dimensions

 but

 we

 don't

 see





still

 see

 any

 like

 visible

 economic





transformation

 and

 the

 first

 kind

 of





thing

 that

 we

 start

 with

 is

 that

 there's





been

 this

 focus

 on

 individual

 agent





benchmarks

 without

 kind

 of

 thinking





about

 what

 those

 agents

 are

 actually





competing

 with

 in

 the

 economy

 where

 the





thing

 that's

 the

 competitive

 the





relevant

 competitive

 unit

 is

 not

 the





agent

 it's

 the

 organization.





And

 the

 organization

 in

 uh

 historically





has

 been

 referred

 to

 as

 a

 form

 of

 super





intelligence

 because

 of

 this

 concept





called

 Ricardian

 comparative

 advantage.





So

 basically

 if

 you

 have

 a

 bunch

 of

 jobs





the

 person

 who

 does

 the

 job

 is

 not

 the





average

 person,

 it's

 the

 person

 who's





best

 suited

 for

 it.

 So

 like

 the

 envelope





of

 the

 intelligence

 in

 an

 organization





is

 way

 better

 than

 if

 you

 kind

 of





average

 across

 the

 population.

 And

 so





these

 the

 AI

 agents

 are

 basically





competing

 against

 forms

 of

 human





organizations

 or

 teams

 of

 humans.

 And

 so





you

 shouldn't

 compare

 a

 ben

 individual





level

 benchmark

 to

 how

 well

 a

 human

 does





something.

 It

 should

 be

 across

 the





entire

 kind

 of

 uh

 what

 we

 call

 mosaic





intelligence.

 So

 the

 thing

 that

 we

 so





then

 we

 kind

 of

 start

 layering

 on

 like





what

 sort

 of

 how

 do

 capability





improvements

 will

 actually

 affect

 the





economy

 and

 equilibrium.

 So

 this

 is

 a





formal

 theoretical

 paper

 and

 we

 look

 at





different

 levels

 of

 intelligence.

 So

 we





start

 with

 minimal

 AGI

 where

 the

 AI





models

 are

 as

 good

 as

 average

 human





capability

 on

 every

 single

 dimension.

 So





minimal

 AGI

 and

 we

 show

 that

 even

 when





you

 get

 to

 this

 point

 you're

 not

 going





to

 have

 a

 huge

 impact

 on

 the

 economy

 uh





because

 again

 because

 the

 organizations





are

 not

 the

 average

 human

 ability.





They're

 better

 than

 that.

 And

 so

 what





you're

 going

 to

 start

 seeing

 is

 actually





wages

 change

 uh

 because

 you

 know





production

 becomes

 cheaper

 and

 so

 that's





going

 to

 affect

 human

 wages.

 And

 so

 what





we

 show

 is

 that

 what

 you

 actually

 need





for

 real

 economic

 transformation

 is

 not





just

 competence

 like

 ability

 on





particular

 tasks

 to

 to

 change.

 It's

 the





ability

 of

 these

 agents

 to

 coordinate





with

 one

 another.

 If

 you

 look

 at

 hugging





face

 and

 even

 like

 how

 the

 the

 solutions





to

 the

 millennium

 stro

 uh

 millennium





problems,

 there's

 this

 idea

 of

 agentic





swarms,

 right?

 But

 if

 you

 unpack

 it,





these

 agents

 are

 still

 very

 bad

 at





coordinating.

 They're

 not

 coordinating.





They're

 just

 do

 they're

 mostly

 just





doing

 parallel

 processing.

 And

 if

 you





have

 benchmarks

 specifically

 on





coordination,

 you

 could

 actually

 show





that

 one

 agent

 does

 better

 than

 two





agents

 splitting

 the

 work

 even

 if

 they





can

 communicate.

 Whereas

 if

 you

 give

 the





same

 thing

 to

 a

 per

 two

 people,

 they





actually

 divi

 they

 uh

 have

 division

 of





labor.

 They

 communicate

 and
</details>

<!-- chunk 5/8 -->

他们比拥有双倍资源的一个人做得好得多。因此智能体在协调方面仍然相当糟糕。但如果它们在协调方面变得更好，你基本上就可以打破科斯企业规模上限，并且你可以看到非常非常不同的企业出现。所以这就是基本前提，即一旦协调变得更好，企业形态、工资变化、就业变化等可能性的经济空间，届时真正的显性变化就会发生。
<details><summary>Original English</summary>
 they

 do

 way





better

 than

 one

 person

 with

 double

 the





resources.

 So

 the

 agents

 are

 still





pretty

 bad

 at

 coordinating.

 But

 if

 they





get

 better

 at

 coordinating,

 you

 can





basically

 break

 the

 coian

 ceiling

 on





firm

 size

 and

 you

 can

 get

 very

 very





different

 firms

 to

 emerge.

 So

 that's

 the





basic

 premise

 is

 that

 coord

 once





coordination

 becomes

 better

 you

 the





economic

 space

 of

 possibilities

 of

 what





firms

 look

 like

 what

 happens

 to

 wages





what

 happens

 to

 employment

 that's

 when





the

 real

 kind

 of

 visible

 changes

 that





are

 going

 to

 happen
</details>

>> 目前弄清协调的最大瓶颈是什么？
<details><summary>Original English</summary>
>> and

 and

 what's

 the

 biggest

 bottleneck

 to





figuring

 out

 coordination

 at

 the

 moment
</details>

>> 老实说我不知道，嗯，我，我[清嗓子]，我认为可能很简单，就是它没有被训练进模型里，它不是后训练的一部分。我其实对此没有任何洞见。
<details><summary>Original English</summary>
>> to

 be

 honest

 I

 don't

 know

 um

 I

 I





[clears throat]

 I

 I

 think

 it

 could

 be

 as





simple

 as

 that

 it's

 not

 being

 trained





into

 the

 models

 it's

 it's

 not

 part

 of





post

 training

 I

 I

 actually

 don't

 have





any

 insight

 on

 that.
</details>

### 就业影响与劳动力市场摩擦

>> 是的，我们谈到了一些你们意见一致的领域。我正试图找一些存在意见分歧的领域。也，也许让我们尝试一下就业。嗯，Alex，我想你更担心的是转型发生得太快，以至于就业方面可能会发生一些突发情况，或者你什么时候分享一下你、你、你的担忧或看法？
<details><summary>Original English</summary>
>> Yeah,

 we

 we've

 talked

 about

 some

 areas





where

 you

 agree.

 I'm

 trying

 to

 find

 some





areas

 where

 there's

 some

 difference

 of





opinion.

 May

 maybe

 let's

 try

 employment.





Um

 Alex,

 I

 I

 think

 you're

 you're

 more





worried

 about

 sort

 of

 the

 transition





happening

 so

 fast

 that

 there

 might

 be





some

 something

 sudden

 happen

 on

 the





employment

 side

 or

 when

 do

 you

 share





your

 your

 your

 concerns

 or

 views?
</details>

嗯，我基本上担心的是这种潜力，而且再次，我其实很在很大程度上同意Tyler的看法，即就对实体经济的影响而言，事情可能会发展得相当缓慢，但如果存在快速转型，比方说在协调方面取得了突破，我们在那篇论文中展示的是，如果协调出现突破，工资和就业就有可能突然——就经济会发生什么而言，就像存在一个相变，在那类情况下，仍然会有新的行业和新的潜在机会，但是我们经济中曾经需要相当长时间转型的那种重新匹配，那种重新匹配就没有机会发生。所以你会有这些规模更大的失业人群，而这会导致某种递归循环，人们在某种程度上因受创而退出劳动力市场。所以这是我个人的担忧，但你知道，就——那是我所担忧的情景。可能性则是另一码事了。
<details><summary>Original English</summary>
 Um,





I'm

 basically

 worried

 about

 the





potential

 and

 again

 like

 I

 actually





agree

 quite

 a

 bit

 with

 Tyler

 that

 things





things

 are

 potentially

 going

 to

 move





pretty

 slowly

 um

 as

 far

 as

 like

 the





effect

 on

 the

 real

 economy

 but

 if

 there





is

 a

 fast

 transition

 like

 let's

 say





there's

 a

 breakthrough

 in

 coordination





what

 we

 show

 in

 that

 paper

 is

 that

 if





there's

 a

 breakthrough

 in

 coordination





there

 is

 the

 potential

 for

 wages

 and





employment

 to

 suddenly

 there's

 like

 a





phase

 transition

 as

 far

 as

 what

 will





happen

 to

 the

 economy

 in

 that

 case

 there





still

 will

 be

 new

 sectors

 and

 new





potential

 opportunities

 but

 the

 sort

 of





rematching

 that

 we

 have

 in

 the

 economy





that

 you

 know

 because

 of

 transitions

 to





take

 used

 to

 take

 quite

 a

 long

 time

 the





sort

 of

 rematching

 doesn't

 have

 a





opportunity

 to

 happen.

 So

 you

 have

 these





large

 larger

 pools

 of

 unemployment

 and





that

 leads

 to

 kind

 of

 these

 recursive





loops

 where

 people

 kind

 of

 get

 scarred





out

 of

 the

 labor

 market.

 So

 that's

 my

 my





personal

 worry,

 but

 you

 know,

 as

 far

 as





that's

 that's

 a

 scenario

 that

 I'm





worried

 about.

 Likelihood

 is

 is

 kind

 of





a

 different

 story.
</details>

>> 我有一个相关的担忧。我想它和这个很接近，但目前如果你在招人，就是很难看出那个人是否会擅长AI？
<details><summary>Original English</summary>
>> I

 have

 a

 related

 worry.

 It's

 it's

 close





to

 the

 same

 thing,

 I

 think,

 but

 it's





just

 hard

 to

 tell

 right

 now

 if

 you're





hiring

 someone.

 Will

 the

 person

 be

 good





at

 AI?
</details>

>> 他们过去需要的技能，我们曾有不完美的指标。哦，他们上了康奈尔大学，或者他们拿了全A，或者他们面试表现良好。而现在这项技能，他们心理上是否足够灵活去掌握AI，你知道，我们往往不知道，所以这可能会提高自然失业率，良好的匹配将更加困难，搜寻将需要更长时间。我不认为这个问题会永远伴随我们，最终AI本身会弄明白这一点，而且会有关于一个人在AI方面有多出色的认证，但在过渡期每个人都是新手，你可能像科技界的许多人那样地位稳固，但除此之外，面对这一非常重要的新技能，我们全都是新手。
<details><summary>Original English</summary>
>> The

 skills

 they

 used

 to

 need,

 we

 had





imperfect

 indicators.

 Oh,

 they

 went

 to





Cornell

 or

 they

 got

 all

 A's

 or

 they

 had





a

 good

 interview.

 And

 now

 the

 skill

 will





they

 be

 mentally

 flexible

 enough

 to

 pick





up

 AI





you

 know

 we

 don't

 know

 often

 so

 that





could

 increase

 the

 natural

 rate

 of





unemployment

 match

 good

 matches

 will

 be





harder

 search

 will

 take

 longer

 I

 don't





think

 that

 problem

 will

 be

 with

 us





forever

 eventually

 the

 AIs

 themselves





will

 figure

 it

 out

 and

 there'll

 be





certifications

 for

 how

 good

 a

 person

 is





in

 AI

 but

 in

 the

 transition

 everyone's

 a





novice

 you

 might

 be

 like

 well





established

 the

 way

 a

 lot

 of

 people

 in





in

 the

 tech

 world

 are,

 but

 otherwise





we're

 all

 noviceses





at

 this

 very

 important

 new

 skill.
</details>

嗯。
<details><summary>Original English</summary>
Mhm.
</details>

>> 所以我想那对——我也很好奇你如何看待就业、工资等这一类问题？
<details><summary>Original English</summary>
>> And

 so

 I

 guess

 what

 does

 that

 that

 mean





for

 and

 I

 guess

 I'm

 curious

 how

 you





think

 about

 sort

 of

 employment

 wages





sort

 of

 yeah

 these

 questions
</details>

>> 嗯，招聘人员会有一些额外的缓慢，但会有数量惊人的新项目、新工作，所以我其实相当看好，而且劳动力市场一直表现良好。
<details><summary>Original English</summary>
>> well

 some

 additional

 slowness

 in

 hiring





people

 but

 there'll

 be

 an

 incredible





number

 of

 new

 projects

 uh

 new

 jobs

 so

 I





I'm

 pretty

 bullish

 actually

 and

 labor





markets

 have

 been

 fine
</details>

但当然会有干扰和转型问题，正如历来存在的那样，正如中国冲击、工业革命时所发生的那样。所以我预计会有一组新的此类问题。其中很多我们甚至还没有弄明白或看到，但它们绝对会来。
<details><summary>Original English</summary>
so

 but

 of

 course

 there'll

 be

 disruptions





and

 transition

 problems

 as

 there

 always





are

 as

 there

 were

 with

 the

 China

 shock





the

 industrial

 rev

 evolution.

 So,

 I





expect

 a

 new

 set

 of

 those.

 A

 bunch

 of





them

 we

 haven't

 even

 figured

 out

 or

 seen





yet,

 but

 they'll

 come.

 Absolutely.
</details>

### 智能体经济规模与现实瓶颈

在多大程度上会出现智能体的爆发式增长，在某种几乎平行的经济中与其他智能体进行购买、交易，而且你知道数量多得多。它们是全天候7×24小时的。它们可以像——在多大程度上，智能体会成为互联网上主要的影响或力量，思考这会是什么样子或不会是什么样子的正确心智模型是什么？
<details><summary>Original English</summary>
To

 what

 extent

 will

 there

 be

 just

 sort





of

 an

 explosion

 of

 agents

 sort

 of

 buying





transacting

 with

 other

 agents

 in

 this





kind

 of

 like

 almost

 parallel

 economy

 and





you

 know

 there's

 so

 many

 more

 of

 them.





They're

 24/7.

 and

 they

 can

 like

 h

 how

 to





the

 extent

 that

 you

 know

 agents

 become





the

 dominant

 sort

 of

 impact

 uh

 or

 sort





of

 force

 on

 the

 internet

 and

 like

 what





is

 the

 right

 mental

 model

 of

 thinking





about

 what

 that

 will

 look

 like

 or

 what





that

 won't

 look

 like.
</details>

>> 我不知道你说的“爆发”是什么意思。如果你问我智能体何时会占到GDP的10%？我认为不会很快。现在如果它们从基本上为零上升到6%，你可以称之为爆发。GDP的6%是巨大的。即便那样似乎也不会那么快。如果是百分之一点五左右，我可以预见到，我不知道，在五年之内。如果一定要逼我给出猜测，你可以把1.5%称为爆发。GDP是庞大的。这是经济学的核心洞见之一。GDP是庞大的。它是庞大的。
<details><summary>Original English</summary>
>> I

 don't

 know

 what

 you

 mean

 by

 the

 word





explosion.

 If

 you

 ask

 me

 the

 question





when

 will

 agents

 be

 10%

 of

 GDP?

 I

 don't





think

 it's

 soon.

 Now

 if

 they

 rose

 from





basically

 0ero

 to

 6%





you

 could

 call

 that

 an

 explosion.

 6%

 of





GDP

 is

 enormous.

 Even

 that

 doesn't

 seem





that

 soon.

 If

 it's

 like

 one

 and

 a

 half





percent,

 I

 could

 see

 that

 I

 don't

 know





within

 five

 years.

 Just

 if

 you're

 going





to

 force

 me

 to

 give

 guesses,

 you

 could





call

 one

 and

 a

 half%

 an

 explosion.

 GDP





is

 huge.

 That's

 one

 of

 the

 core

 insights





of

 economics.

 GDP

 is

 huge.

 It's

 huge.
</details>

>> 是的。我的意思是，即使以我们现有的智能体来说，它们已经极其有能力，比如存在于你手机上的消费级产品。但你知道这就是问题所在，外界存在着完全反直觉的瓶颈，比如网站是为人类设计的，而且它们各不相同。所以你仍然会遇到这样的问题：你的超级聪明的智能体每次订机票时都给你订紧挨着厕所的座位。每一次都是。然后你就会想下一次我不想用智能体了。
<details><summary>Original English</summary>
>> Yeah.

 And

 I

 mean

 like

 even

 with

 the





agents

 that

 we

 have

 now,

 they're

 they're





they're

 already

 incredibly

 capable

 like





the

 the

 the

 sort

 of

 consumer

 grade





things

 that

 live

 on

 your

 phone.

 But

 you





know

 that

 that's

 the

 thing

 like

 there's





just

 completely

 unintuitive

 bottlenecks





out

 there

 like

 the

 websites

 are

 designed





for

 human

 beings

 and

 they're

 all





different.

 And

 so

 you

 know

 you're

 still





getting

 into

 issues

 with

 where

 your





super

 smart

 agent

 is

 like

 booking

 you

 a





flight

 booking

 you

 a

 seat

 right

 next

 to





the

 toilet

 every

 single

 time.

 Every





single

 time.

 And

 then

 you're

 like

 I





don't

 want

 to

 use

 an

 agent

 next

 time.
</details>

>> 或者是外面存在所有这些监管这一事实。我是说那是重头戏，对吧？所以比如智能体，公司花费数十亿美元试图在他们的网站上做基本的选择架构，以便向人类追加销售产品，对吧？他们不希望——智能体没有同样的心理，所以它们不会容易受到这类选择架构的影响。因此这些平台有动力不允许别人的智能体进去替他们购物。而且你已经在某种程度上看到了这一点。比如如果你调出Muse之类的东西，它无法在亚马逊上替你购物。嗯，
<details><summary>Original English</summary>
>> Or

 the

 fact

 that

 there's

 all

 of

 this





regulation

 out

 there.

 I

 mean

 that

 the





big

 one,

 right?

 So

 like

 agents,





companies

 are

 spending

 billions

 of





dollars

 trying

 to

 do

 basic

 choice





architecture

 on

 their

 website

 in

 order





to

 upsell

 humans

 on

 products,

 right?





They

 don't

 want

 to

 agents

 don't

 have

 the





same

 psychology

 and

 so

 they're

 not

 going





to

 be

 prone

 to

 these

 sort

 this

 sort

 of





choice

 architecture.

 So

 these

 platforms





have

 an

 incentive

 not

 to

 allow,

 you





know,

 somebody

 else's

 agent

 to

 go

 in

 and





shop

 for

 them.

 And

 you're

 already

 kind





of

 seeing

 it.

 So

 like

 if

 you

 pull

 up





Muse

 or

 something

 like

 that,

 it

 can't





shop

 on

 Amazon

 for

 you.

 Um,
</details>

>> 我不用智能体来管理我的日历，尽管它们可以做到，因为我想在脑海中清楚每天要发生什么。而我能记住的唯一方法，就是必须花额外的时间把它写在我的日历上。那很蠢。那是我的缺点。但我不认为这会消失。而且智能体可以好上10倍，无论那意味着什么。而我仍然会想把它写在我的日历上。所以我想到，哦，12月18日，我要去看一场文艺复兴音乐会。而且我凭记忆就知道。所以在我们如何分配注意力方面存在这些滑稽的不可分割性，但往往是一些最大的瓶颈。
<details><summary>Original English</summary>
>> I

 don't

 use

 agents

 to

 manage

 my





calendar,

 although

 they

 could

 because

 I





want

 to

 know

 mentally

 in

 my

 mind

 what's





coming

 each

 day.

 And

 the

 only

 way

 I

 can





remember

 is

 if

 I

 have

 to

 write

 it

 down





in

 extra

 time

 on

 my

 calendar.

 And

 that's





stupid.

 That's

 my

 flaw.

 But

 I

 don't





think

 it's

 going

 away.

 And

 the

 agents





could

 be

 10

 times

 better,

 whatever

 that





means.

 And

 I'm

 still

 going

 to

 want

 to





write

 it

 on

 my

 calendar.

 So

 I

 think,

 oh,





December

 18th,

 I'm

 seeing

 a

 Renaissance





music

 concert.

 And

 I

 know

 that

 off

 the





top

 of

 my

 head.

 So

 there

 are

 these

 funny





indivisibilities





and

 how

 we

 allocate

 our

 attention

 but





are

 often

 some

 of

 the

 biggest





bottlenecks.
</details>

### 监管与政治经济学

回到监管部分，嗯，你似乎更加清醒，即这类中期选举可能不会导致数据中心无限期停滞。我只是很好奇你对AI情绪更广泛的看法。负面情绪在多大程度上是真实的，即它会导致——你知道我们看到像布卢明顿在某种程度上试图取缔它的使用，你对这里关于应该如何看待其政治经济学有什么想法？
<details><summary>Original English</summary>
Going

 back

 to

 the

 regul

 regulation

 part





um

 t

 you

 seem

 more

 sober

 that

 this

 sort





of

 uh

 the

 midterms

 um

 you

 know

 might

 not





lead

 to

 uh

 sort

 of

 uh

 you

 know

 data





centers

 stalling

 indefinitely.

 I'm





curious

 just

 for

 your

 broader

 thoughts





on

 AI

 sentiment.

 how

 much

 of

 the

 uh





negativity

 is

 real

 in

 the

 sense

 that

 it





will

 lead

 to

 you

 know

 we

 saw

 like





Bloomington

 you

 know

 trying

 to

 outlaw





usage

 of

 it

 as

 well

 to

 some

 degree

 like





what

 are

 your

 thoughts

 here

 on

 on

 sort





of

 what's

 uh

 how

 you

 should

 think

 about





the

 political

 economy

 of

 that
</details>

>> 嗯，我们有50个州，有各县，有各市，甚至还有其他国家。看起来它会稍微放缓一点，但基本上仍会推进。甚至得克萨斯州新州长已经在往回退缩，比如，好吧，我们只是希望工会参与进来。他们需要支付不错的工资。你知道，我们现有的项目将继续进行。其他的我们将重新审视。Josh Shapiro的说辞非常强硬。现实却大不相同。所以，它推高了成本，但我认为归根结底不会有那么大影响。但会不会有许多地方断然说不？可能会。但再次，50个州，我很高兴我们拥有它们。呃，也许最终会有52个。[嗤笑]
<details><summary>Original English</summary>
>> well

 we

 have

 50

 states

 there's

 counties





there's

 cities

 there's

 even

 other





countries

 it

 seems

 it

 will

 slow

 down

 a





bit

 but

 still

 basically

 go

 through

 even





the

 te

 the

 new

 Texas

 governor

 is

 already





backtracking





like,

 well,

 we

 just

 want

 the

 labor





unions

 involved.

 They

 need

 to

 pay

 good





wages.

 You

 know,

 the

 projects

 we

 have





now

 will

 go

 ahead.

 The

 others

 we're





going

 to

 look

 at

 again,

 Josh

 Shapiro,





the

 rhetoric

 was

 very

 strong.

 The





reality

 is

 quite

 different.

 So,

 it





raises

 costs,

 but

 I

 don't

 think





ultimately

 it

 will

 matter

 that

 much.

 But





will

 there

 be

 a

 bunch

 of

 places

 that





absolutely

 say

 no?

 Probably.

 But

 again,





50

 states,

 I

 glad

 we

 have

 them.

 Uh





maybe

 you'll

 end

 up

 with

 52.





[snorts]
</details>

>> 是的。我的意思是，嗯，顺着这一点来说，我认为这完全取决于路径，对吧？所以就像事物，一切在某种程度上都是内生的，包括政治经济。所以你知道州长们退缩的原因是因为失业率看起来很不错。经济以合理的幅度增长。从经济角度来看，一切都还算不错。所以比如
<details><summary>Original English</summary>
>> Yeah.

 And

 I

 mean

 um

 just

 to

 piggyback

 on





that,

 I

 think

 like

 it

 just

 completely





depends

 on

 the

 path,

 right?

 So

 it's

 like





things

 everything's

 kind

 of

 indogenous





including

 political

 economy.

 So

 you

 know





the

 reason

 that

 the

 governors

 are





backtracking

 this

 because

 like





unemployment

 look

 great

 rate

 looks





great.

 The

 economy

 is

 growing

 at

 a





reasonable

 amount.

 Everything

 kind

 of





looks

 fine

 economically.

 So

 like
</details>

<!-- chunk 6/8 -->

……并没有任何工具性的理由非要出现这种政治经济层面的反弹。但我觉得那些预测极度极端情景的人没有意识到的是，伴随着某种极端情景的开端，也会伴生出一种极端的政治经济反弹，而这会在系统内部内生性地约束事态的发展。所以，这只会是一场来回拉锯的过程。而对于生活在未来的人们来说，回头看这些数据时，最终呈现出的景象会是：正因为存在着这种相互博弈，事情的发展其实比人们想象的要慢得多。
<details><summary>Original English</summary>
 there's no like instrumental reason for there to be this sort of political economy reaction. But the thing that I think people who are projecting these very extreme scenarios don't realize is that with a the beginning of an extreme scenario there will be the beginning of an extreme political economy reaction and that will kind of endogenously constrain things. So, it's just going to be a back and forth. And what the data will end up looking like to our an to, you know, people living in the future is that things moved a lot slower than people would think because of this sort of interplay.
</details>

### 金钱对政治影响的局限与制度制衡

>> 看起来，你看，一个人在政治上能投入的资金规模……大家很久以前都在担忧“联合公民案”（Citizens United），担心大公司会掌控一切，但是你看，埃隆投了5个亿还是多少钱，却没能得到他想要的结果。这在某种程度上暴露了金钱在政治中的局限性吗？抑或只是科技界人士——或者不仅是科技界人士，还包括企业——或许非常擅长为自己的商业分配资源，但在华盛顿特区以及政治领域，可能就没那么擅长分配了？
<details><summary>Original English</summary>
>> It it seems like, you know, uh the the sort of amount of money one can put in politics, you know, everyone was worried about Citizens United a long time ago and, you know, corporations gonna control everything, but, you know, Elon put in 500 million or what whatever it was and couldn't get the out outcome he wanted. Is is this a sort of um expose the limitations of of money in politics or is it just that you know tech people or not just tech people corporations may be very good at allocating for their business but maybe not you know uh that great at allocating in in sort of uh the DC and political realm.
</details>

>> 我敢说，学术界在湾区人眼里被稍微低估了。研究竞选资金的人早就知道这一点。有大量证据表明，花销其实没那么重要。你可以认为这是好事还是坏事，但这完全没有让我感到丝毫意外。我并不认为是因为那些人愚蠢。呃，如果你觉得他们一开始就抱有政治企图本身算得上某种更广泛意义上的愚蠢，那倒也罢。但事实就是，除了少数地方选举之外，根本就不存在一种只要投下重金就能得到你想要的政治结果的简单途径。这就是权力制衡，哪怕整个体制里没有一个人跟你是一条心的。[笑声]
<details><summary>Original English</summary>
>> Dare I say that academia is slightly underrated by Bay Area people. People who study campaign finance have known this for a long time. There's a lot of evidence that spending doesn't matter that much. You can think that's good or bad, but none of this surprised me in the slightest. And I don't think it's that the people are fools. Uh you might think they're fools in some broader sense of just having political aspirations at all. But there's just apart from some number of local races, there's no simple way to just spend a lot of money and get the politics you want. It's checks and balances. even though no one in the system is like aligned with you. [laughter]
</details>

>> 没错，
<details><summary>Original English</summary>
>> Yeah,
</details>

>> 我们拥有的是一个美妙的制度。我几乎每天都——我不是在开玩笑。我觉得，你看，美国的制度令人不可思议，竞争性市场也令人不可思议。虽然一切并不完美，但正如泰勒所说，这个制度中孕育出了所有这些神奇之处。
<details><summary>Original English</summary>
>> it's a beautiful system we have. I'm like just every day I'm in I'm I'm not joking. I'm like it's you know the the American system is incredible and competitive markets are incredible. It's just everything just, you know, it's it's not perfect, but exactly as Tyler said, like there's all this magic that comes out of the system.
</details>

### 互问起源故事：从学医到经济学

>> 对。我很好奇，如果你们两位互相采访对方，你们会……你们最想了解彼此的是什么？泰勒，我先从你开始。你最想了解亚历克斯对哪方面的看法，或者……？
<details><summary>Original English</summary>
>> Yeah. I'm I'm I'm curious if you were both interviewing each other, what what you would uh what you would what are you most curious about. Tyler, I'll I'll start with you. Where are you most curious about Alex's perspective on on on something or or or Yeah.
</details>

>> 嗯，就是你如何成为一名经济学的起源故事。
<details><summary>Original English</summary>
>> Well, your origin story of how you became an economist.
</details>

>> 嗯，泰勒，这是个非常为你自己谋私利的问题，[笑声] 因为它正好和你有关。
<details><summary>Original English</summary>
>> Well, it's that's a very self-serving question, Tyler, [laughter] because it has to do with you.
</details>

>> 好吧，那就多讲讲。
<details><summary>Original English</summary>
>> Okay, we'll say more.
</details>

>> 行。我的意思是，我是摩尔多瓦来的移民。所以你看，我在美国基本上是靠领食品券这类的救济长大的。我父母对经济学一无所知，我对自己也是一无所知。我上了大学，读的是医学预科，因为我知道医生是什么职业，我父母也知道医生是什么。在大学里你必须修一些先修课，我选了一门经济学入门课，觉得这门课还挺好玩的。但我依然是医学预科生，我上了那门课并拿了高分，它把我的绩点拉得比我那些医学预科课程原本显示的要高。

嗯，然后你看，我本来是打算去读医学院的。我申请了医学院，也拿到了医学院的录取通知。然后你看，我开始读《边际革命》（Marginal Revolution），并且开始听……我也听到了一篇NPR的文章……呃，是理查德·塞勒（Richard Thaylor）做客的节目。在你们两位的影响下，我猛然意识到：天哪，我可以用经济学做这些事情，这太不可思议了。
<details><summary>Original English</summary>
>> Yeah. So I mean so I was uh I'm an immigrant from Muldova. So you know I very you know grew up on food stamps and things like that in America. And I my parents didn't know anything about economics. I didn't know anything about economics. I I went to college and I was premed cuz I knew what a doctor was. Uh my parents knew what a doctor was. And in college like you had to take like prerequisites and I took an econ one class and I thought this was kind of fun. But I'm still premed and I took it. I got good grades, made made my GPA higher than my premed classes suggested. Um, and then, you know, I was going to go to medical school. I applied to medical school. I got into medical school and then, you know, I started reading Marginal Revolution and I started listening to uh, you know, that I I also heard like an NPR article uh, uh, program with Richard Thaylor. And between the both of you guys, it was just, oh, I can do this with economics. This is incredible.
</details>

>> 那段经历我以前只知道一部分，所以谢谢你分享。
<details><summary>Original English</summary>
>> I only knew one part of that story, so thank you.
</details>

>> 我知道《边际革命》那一部分。
<details><summary>Original English</summary>
>> I knew the marginal revolution part.
</details>

>> 没错。不，我的意思是确确实实是这样，因为在那个时候，大概是在2008年或2009年，并没有那么多经济学家能像你们那样，真正向你展示在这个领域里究竟能做多少事情。所以我实际上就退出了医学院的申请流程，去了唯一一所录取了我的大学，也就是加利福尼亚大学圣迭戈分校（UC San Diego），真得感谢它。嗯，再后来的事情大家就都知道了。对于理解我们所谓的“经济”这个复杂系统里正在发生的事情——尽管我们能理解的程度其实并不算很高——这真是一个令人难以置信的领域和知识库。
<details><summary>Original English</summary>
>> Yeah. No, I mean it was but it was like because you at that point, this was 2008 or n um there weren't a lot of these economists like you know actually showing you how much you can do with the topic. And so I actually, you know, I pulled out of medical school of the of the process. I went to the only school that accepted me which was you know thank you UC San Diego. Um and uh yeah the rest is history. I I this is just like the such an incredible field and knowledge base to kind of understand to the extent that we can which is like not very high about uh about what's going on in this you know complex system that we call the economy.
</details>

### 摩尔多瓦与德涅斯特河沿岸

>> 我能追问一个问题吗？
<details><summary>Original English</summary>
>> Can I ask a followup please?
</details>

>> 摩尔多瓦会并且应该成为罗马尼亚的一部分吗？
<details><summary>Original English</summary>
>> Will and should Muldova become a part of Romania?
</details>

我的看法是，会的。这就是我的观点。
<details><summary>Original English</summary>
I mean my Yes. That's my view.
</details>

>> 而且他们注定会合并。我认为他们应该合并，而且他们注定会合并。
<details><summary>Original English</summary>
>> And they will. I figure they should, but they will.
</details>

>> 好吧。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 是的。他们本来就是一体的。我是说，那个地方过去叫比萨拉比亚（Basarabia）。我奶奶就是从比萨拉比亚来的。
<details><summary>Original English</summary>
>> Yeah. I I They were originally. I mean, it was the country was called Basarabia. My grandma, you know, she was from Basarabia.
</details>

>> 她不是来自摩尔多瓦。嗯，我觉得这可能是一个很有争议的观点，但我其实并不是来自摩尔多瓦，我是来自德涅斯特河沿岸（Transnistra）。

啊，好的。现在全都清楚了。
<details><summary>Original English</summary>
>> She wasn't from Muldova. Um, and it I think it this probably a controversial opinion, but I I I'm actually not from Muldova. I'm from Transnistra. Ah, okay. Now it's all clear.
</details>

>> 所以，
<details><summary>Original English</summary>
>> So,
</details>

>> 是的。所以你看，我们当年是从德涅斯特河沿岸逃难到美国的难民。那时爆发了一场内战，我们躲在地下室里躲避子弹等等这一类的事情。后来我们作为难民来到了美国。但我认为，如果你了解摩尔多瓦文化，它和罗马尼亚文化非常相似。语言也几乎是一样的。
<details><summary>Original English</summary>
>> yeah. So, like you know that we were refugees from Transnistria to America. So, there was a civil war. We were like in basement hiding from bullets and all that type of stuff. And then we we ended up coming to America as refugees. But I think it's like, you know, the c the if you know Muldoven culture, it's very similar to Romanian culture. Um the language is almost the same.
</details>

### 国际象棋洞察与通用AI直觉

>> 难怪风险投资人总说一定要问起源故事，他们说得太对了。

亚历克斯，你会问泰勒什么问题？
<details><summary>Original English</summary>
>> When the VCs say always ask for the origin story, they're so correct. Yeah. The um Alex, what question would you ask Tyler?
</details>

>> 嗯，我想知道你的经历，因为你在这方面觉察得非常早，而我好像从来没听过这个故事：你是如何被人工智能所吸引，并开始如此严肃地思考AI的？而且你非常早就预见到了这项技术的变革性潜力，我很好奇你是如何比大多数人更早意识到这一点的？
<details><summary>Original English</summary>
>> Um I I want to know your because you were so early on this and I don't think I've ever heard this story of like how how were you kind of attracted to AI and thinking about AI so seriously. Um, and you were you were very early about like the transformative potential of the technology like uh and I'm just curious like how how how did you how did you realize that earlier than most?
</details>

>> 这个嘛，所有国际象棋棋手都有类似的故事。我早年算是个国际象棋神童。13岁那年我在新泽西下棋，他们推来了一台名叫“叮当小仙子”（Tinkerbell）的电脑和人类对弈，它下得很烂，但我看出了那种技术进步的势头。但对于棋手来说，关键在于这一点：只要水平还不错，他们都知道下国际象棋根本不像用袖珍计算器算数那样，它靠的是直觉。

如果你亲眼目睹计算机攻克了一个你早就知道主要依赖直觉的领域，你就会非常容易相信它们能够攻克许多其他领域。所以卡斯帕罗夫很早就意识到了这点；肯·罗格夫（Ken Rogoff）不需要怎么接受AI观念的洗礼，他很早就意识到了；那些下国际象棋的人是第一批看清这一点的人。这就是一个非常简单直接的故事，事情就是这么发生的。
<details><summary>Original English</summary>
>> Well, all chess players have a story like this. I was in early years at like a chess prodigy. So I was age 13 playing in New Jersey and they wheeled in a computer called Tinkerbell that played against the humans and it sucked but I saw what the progress was like. But the point about chess players is this. They all know if they're any good. The chess is not like pocket calculator stuff. It's intuition. And if you see computers conquer an area that you already knew was mostly intuition, you will find it very easy to believe they can conquer a bunch of other areas. So Kasparov was early to this. Ken Rogoff didn't need much AI pilling. He was early to this. And the chess people were the first ones there. And that's a very simple direct story. And that's how it happened.
</details>

>> 德米斯（Demis）也是。
<details><summary>Original English</summary>
>> And Demis too.
</details>

>> 德米斯也是，绝对是共同的故事背景。你看，到了20世纪90年代它就大显神威了，深蓝（Deep Blue）击败了卡斯帕罗夫，而深蓝甚至都算不上一个出色的模型。
<details><summary>Original English</summary>
>> Demis 2. Absolutely common stories. You see it, you know, kick butt by the 1990s and it beats Kasparov of Deep Blue. And Deep Blue is not a great model.
</details>

>> 但当时的感觉就像是，好吧，它既然能做到这个，你就只需静待它扩散到其他所有领域。只不过这花了很长时间。事实上，
<details><summary>Original English</summary>
>> But it's like, okay, uh, it can do this. So, you're just waiting for it to spread to everything else. But it took a long time. In fact,
</details>

### 可验证奖励与AI写诗的前景

>> 是的。我认为这是一个绝佳的例子。很多人原本会看着AI说：嘿，它做不了这个，做不了那个；但事实是它几乎将无所不能。因为你看，考虑到比如RLVR（可验证奖励强化学习）之类的东西，也就是后期训练中的可验证奖励部分，很多人把它当成了精神慰藉，说：“噢，那个不可验证，这个不可验证”；但事实上，如果你去训练验证器，几乎任何事情都会变成可验证的。
<details><summary>Original English</summary>
>> yeah. I I think this is like a great example of like you know a lot of people would have looked at AI and said hey this it can't do this it can't do that but it's it it that it's going to be able to do almost everything because you know like thinking about like RLVR or something like that like the verifiable reward part of of post training a lot of people like use that as like copium like oh that's not verifiable that's not verifiable but like if you train the verifier almost anything will become verifiable.
</details>

>> 你能够批评它这一事实，几乎就意味着它是可验证的，对吧？
<details><summary>Original English</summary>
>> The fact that you can criticize it means it's verifiable almost, right?
</details>

>> 没错。正是这样。完全正确。所以国际象棋真的是一个极好的例子。如果你是一个非常顶尖的棋手，你完全清楚其中需要多少直觉，也清楚这在未来能走得多远。
<details><summary>Original English</summary>
>> Yeah. Exactly. Exactly. So, it's like it's it's a and and chess is like a really great example. Like you see if you're a really good chess player, you know exactly how much that that intuition is required and how far that's going to go in the future.
</details>

>> 麦尔（Mar）正在研究诗人这一块。我不太确定他们目前的进展如何，但在我看来这完全应该可行。
<details><summary>Original English</summary>
>> Mar is working on the poets. I'm not sure how far along they are. Uh but it seems to me it should work.
</details>

>> 嗯。写出更好的诗歌，
<details><summary>Original English</summary>
>> Mhm. in better poetry,
</details>

>> 对吧？去写出伟大的诗歌。我认为在不到两年的时间里，只要大家稍微花心思去做，这就会成为可能。我指的不是动用数十亿美元的大规模投入，而是哪怕投入任何一点努力。找来十几位诗人，付给他们一些报酬，对吧？也不需要很多钱。让他们放手去做，在这个流程中设置一些制衡机制。它就能成。
<details><summary>Original English</summary>
>> right? To write great poetry. I think uh in less than two years, it will be possible if people put their minds to it at all. I don't mean a big major effort with billions, but just some kind of effort at all. Bring in a dozen poets, pay them something, right? Doesn't have to be that much. Let them loose, have some checks and balances on the process. It'll work.
</details>

<!-- chunk 7/8 -->

>> 是的。我们公司有些人认为，“品味是人类所独有的”这种观点其实是一种自我安慰（cope）。那些系统已经很擅长这个了。
<details><summary>Original English</summary>
>> Yeah.

 Some

 people

 at

 the

 firm

 think

 that





the

 idea

 of

 of

 taste

 being

 uniquely





human

 is

 is

 a

 cope.

 that

 uh

 that

 that





the

 systems

 will

 are

 already

 good

 at.
</details>

>> 它们已经具备极佳的品味了。你问它们古典音乐，比如西贝柳斯第五交响曲哪个录音版本最好之类的问题，它们给出的回答非常精彩，现在比《企鹅唱片指南》（Penguin Guide）还要好。
<details><summary>Original English</summary>
>> They

 already

 have

 great

 taste.

 You

 ask





them

 about

 classical

 music

 like

 what's





the

 best

 recording

 of

 Sibilius's

 fifth





whatever

 they

 give

 great

 answers

 better





than

 the

 Penguin

 Guide

 right

 now.
</details>

[laughter]
<details><summary>Original English</summary>
[laughter]
</details>

### 资本报酬率与瓶颈要素

>> 是的。很有意思。好的。在我们结束之前，我想问几个杂七杂八的问题。其一是，你们看到 Doresh 的那篇随笔了吗？他与别人合作撰写的，大意是说皮凯蒂（Piketty）对上个世纪的论断虽然不一定对，但他那个 r > g 之类的模型，在 AI 世纪里可能成立。我很想知道亚历克斯（Alex）你对此怎么看？
<details><summary>Original English</summary>
>> Yeah.

 Fascinating.

 Okay.

 So,

 there's

 a





few

 grab

 bag

 questions

 I

 want

 to

 ask





before

 before

 we

 wrap.

 one

 is

 did

 you





guys

 see

 Doresh's

 uh

 sort

 of

 essay

 he





collaborated

 with

 somebody

 on

 sort

 of





basically

 saying

 that

 Pikid

 you

 know





wasn't

 right

 about

 the

 last

 century

 but





but

 his

 model

 of

 you

 know

 RG

 etc

 is

 is





might

 be

 right

 in

 the

 AI

 uh

 century

 I'm





I'm

 curious

 if

 you

 uh

 had

 a

 take

 on

 that





Alex
</details>

>> 好的，我想那篇是和菲尔·特拉梅尔（Phil Trammell）合写的，《21世纪的资本》……
<details><summary>Original English</summary>
>> yeah

 so

 this

 is

 with

 Phil

 Trel

 I

 think





um

 capital

 in

 the

 21st

 century

 y
</details>

>> 嗯。
<details><summary>Original English</summary>
>> um
</details>

>> 我觉得那篇……文章的核心主旨，是认为经济活动可能会脱离劳动力，转而聚焦于资本。我认为很多人对那篇文章的具体研究方法提出了质疑，对此我不多做评价；但这项技术可能加剧对资本的依赖这一宏观观点，我认为确实是一种可能发生的情景。不过也存在其他情景，这也是我之前撰文讨论过的，泰勒（Tyler）似乎也暗指过这点：在另一种情景中，可能会创造出更多的工作岗位，而这些岗位正因为其稀缺性而变得有价值。
<details><summary>Original English</summary>
>> I

 think

 that's

 a

 that's

 I

 think

 it's

 uh





the

 the

 idea

 a

 that

 economic

 activity





may

 be

 divorced

 from

 labor

 and

 be

 kind





of

 focused

 on

 on

 capital.

 Um

 that

 the





that's

 kind

 of

 the

 broader

 idea

 of

 the





piece.

 I

 think

 I

 think

 many

 people

 took





took

 kind

 of

 uh

 uh

 had

 issues

 with

 the





actual

 methodology

 of

 the

 piece

 which





you

 know

 I

 won't

 I

 won't

 speak

 to

 but





the

 broad

 idea

 of





the

 technology

 potentially

 increasing





this

 concentr

 that

 the the

 reliance

 on





capital

 I

 think

 that

 is

 a

 that

 is

 a





scenario

 that

 could

 happen

 um

 but





there's

 alternative

 scenarios

 and

 this





is

 things

 that

 I've

 written

 about

 and

 I





think

 Tyler

 also

 alluded

 to

 this

 where





um

 depending

 on

 there's

 there's

 an





alternative

 scenario

 where

 like

 you

 know





there's

 just

 more

 jobs

 created

 and

 these





jobs

 are

 valuable

 because

 of

 the

 fact





that

 they're

 scarce.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 对。核心观点在于，价值会流向稀缺要素。这属于瓶颈逻辑。如果这些工作岗位存在于一个富裕社会中，就会有大量价值流向这些岗位。问题只在于会有多少这样的工作存在，以及它们能否支撑起整个经济。从历史上看一直如此，但眼下确实是一个巨大的问号。不过这些都是我们需要借助数据去密切观察的事情。我那篇关于 AGI 经济政策的论文，基本上就是提出了这个论点：我们需要以更加全面的方式去追踪 AI 驱动下的经济走向。
<details><summary>Original English</summary>
>> Right.

 So

 the

 idea

 is

 that

 you

 know





value

 moves

 towards

 scarcity.

 These

 this





is

 kind

 of

 like

 the

 whole

 bottleneck





logic

 and

 then

 if

 those

 jobs

 are

 in

 a





rich

 society

 they

 there

 will

 be

 a

 lot

 of





value

 going

 to

 those

 jobs.

 And

 it's

 just





a

 question

 of

 how

 many

 of

 those

 jobs





exist

 and

 whether

 it

 can

 support

 the





entire

 economy.

 And

 historically

 that's





been

 the

 case,

 but

 that's

 been

 that's





the

 real

 big

 question

 mark.

 Um,

 but





these

 are

 things

 that

 we

 just

 need

 to





watch

 for

 with

 data.

 So

 like

 my

 paper





with

 you

 know

 an

 economic

 policy

 for

 AGI





just

 basically

 makes

 that

 argument.

 We





need

 to

 be

 tracking





where

 where

 the

 economy

 is

 going

 with

 AI





in

 a

 much

 more

 uh

 comprehensive

 way.
</details>

>> 极为基础的技术往往会让消费者受益。火、语言、电力等等，莫不如此。这并不能证明历史一定会重演。但我们必须区分两种情况：一种是“资本能做很多事”，另一种则是“存在进入壁垒，从而使垄断租金归属于特定的资本所有者”。
<details><summary>Original English</summary>
>> Very

 fundamental

 technologies

 tend

 to





benefit

 the

 consumers.

 Fire,

 language,





electricity

 and

 so

 on

 and

 so

 on.

 That's





no

 proof

 it

 will

 happen

 again.

 But

 we





need

 to

 distinguish

 between

 capital

 can





do

 a

 lot

 versus

 there

 are

 entry

 barriers





that

 will

 acrue

 monopoly

 rents

 to





particular

 capital

 owners.
</details>

>> 我没看出那篇文章为后一种命题提供了强有力的论据。它主要论证的是资本能做很多事。但如果资本变得大宗商品化——就像我认识的一些人所说，所有的租金都会流向土地，或者流向能源。我不确定这是否属实，但如果要选的话，这些说法似乎比“所有租金都会流向资本”更有可能。
<details><summary>Original English</summary>
>> And

 I

 don't

 see

 that

 that

 piece

 really





made

 a

 strong

 case

 for

 the

 latter





proposition.

 It

 was

 mainly

 arguing





capital

 can

 do

 a

 lot.

 But

 if

 the

 capital





is

 commoditized

 like

 I

 know

 people

 who





say

 all

 the

 rents

 will

 go

 to

 land,

 all





the

 rents

 will

 go

 to

 energy.





I'm

 not

 sure

 that's

 true,

 but

 those

 seem





more

 likely

 than

 all

 the

 rents

 go

 to





capital

 if

 you

 had

 to

 say.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah,
</details>

>> 没错。它会流向稀缺要素。如果稀缺要素是能源，租金就会流向那里。
<details><summary>Original English</summary>
>> that

 that's

 right.

 It

 goes

 to

 scarcity.





And

 if

 scarcity

 is

 is

 energy,

 that's





where

 the

 rents

 will

 go.
</details>

>> 不过，或许 AI 本身也会让能源变得不再稀缺。所以我才不太愿意做预测。
<details><summary>Original English</summary>
>> Now,

 maybe

 AI

 itself

 makes

 energy

 less





scarce.

 So

 that's

 why

 I'm

 reluctant

 to





predict,
</details>

>> 但我至少看到了理由去思考：海湾国家或者地主们会大发横财等等。不过 AI 会改变足够多的事情。比方说，如果我们能以极低廉的成本进行土地改造（terraform），并以极低的成本进行海水淡化，这并非完全不可想象。那么，也许稀缺的是土地的地理位置，或者是最佳的养老胜地；比如太浩湖（Tahoe）如此特别，是因为它毗邻湾区但又不用交加州的税。虽然很难预测，但最核心的还是要沿着稀缺性去思考。
<details><summary>Original English</summary>
>> but

 I

 at least

 see

 the

 case

 to

 think,





well,

 the

 the

 Gulf

 countries

 will

 make





out

 like

 bandits

 and

 so

 on

 or

 the

 land





owners,

 but

 AI

 will

 change

 enough





things.

 Say

 we

 can

 terraform

 land

 quite





cheaply

 and

 desalinate

 water

 very





cheaply.

 It

 doesn't

 seem

 so

 implausible.





Well,

 maybe

 it's

 location

 of

 land

 or

 the





best

 retirement

 spots

 or

 like

 Tahoe

 is





so

 special

 because

 you're

 near

 the

 Bay





Area

 but

 you

 don't

 pay

 the

 taxes

 or

 but





it's

 very

 hard

 to

 predict

 but

 think





through

 scarcity

 most

 of

 all.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

### 供应链短缺与《态势感知》

>> 是的。在我们的行业领域里，就此而言，我们认为最大的稀缺在于供应端；而在短期内，需求其实远比表面上看起来要大得多。但这建立在这样一种假设或信念之上：当你与那些超级用户交流时，他们表现得好像怎么用都不够。而超级用户目前在少数几家公司里只占极少数人口比例，AI 尚未广泛普及。我想反方观点会说，它目前在企业中还没有产生可衡量的实质影响。因此，“AI 用得越多，最终就越能对这些企业产生足够证明巨额开支合理性的影响”，在某种程度上还只是一种推测。不过实际上我们刚刚成立了一支名为“机器时代基金”（Machine Age Fund）的新基金，投资数据中心以及基础设施堆栈的其他要素，以此来缓解部分供应方面的挑战。莱奥波德（Leopold）那篇《态势感知》（Situational Awareness）的论文，在你们看来是否算得上过去几年里科技界最重要的公共知识分子作品之一？我很想听听你们对那篇作品历史地位的看法。
<details><summary>Original English</summary>
>> Yeah.

 And

 in in

 our

 world

 on

 that

 on





that

 note

 we

 we

 think

 that

 the

 biggest





scarcity

 is

 is

 on

 supply

 and

 in

 the





short

 term

 uh

 that

 that

 demand

 is

 is





much

 bigger

 than

 uh

 than

 it

 seems.

 Uh





but

 that

 rests

 on

 the

 sort

 of

 assumption





or

 or

 sort

 of the

 belief

 that

 when

 you





talk

 to

 the

 super

 users,

 they

 sort

 of





like

 can't

 get

 enough.

 Um

 and

 there's





the

 the

 super

 users

 are

 really

 a

 small





percentage

 of

 of of

 people

 at

 at

 at

 a





small

 percentage

 of

 companies

 and

 AI

 is





still

 not

 broadly

 diffused

 yet.

 And

 I





think

 the

 counter

 to

 that

 claim

 would

 be





well

 it's

 not

 having

 measurable

 impact





on

 companies

 yet.

 So

 it

 is

 uh

 sort

 of





speculative

 that

 um

 you

 know

 the

 more





that

 AI

 is

 used

 it

 will

 eventually

 lead





to

 impact

 on

 these

 companies

 in

 ways





that

 justify

 uh

 the

 massive

 increase

 in





spend.

 Um

 but

 you

 know

 we

 just

 started

 a





new

 fund

 actually

 called

 machine

 age





fund

 which

 is

 you

 know

 doing

 data





centers

 and

 other

 elements

 of

 the

 sort





of

 infrastructure

 stack

 to

 be

 able

 to

 um





mitigate

 some

 of

 these

 supply





challenges.

 Leopold's

 paper

 situational





awareness

 does

 does

 that

 sort

 of

 stand





to

 you

 as

 like

 one

 of

 the

 more

 important





uh

 sort

 of

 you

 know

 public

 intellectual





pieces

 in

 technology

 in

 the

 in

 the

 past





few

 years

 or

 I'm

 curious

 what

 you

 think





of

 the

 the

 legacy

 of

 uh

 of

 that
</details>

>> 不仅在科技界，在任何领域都算得上。话虽如此，我认为他太迷恋“快速起飞”（fast takeoff）了。正如我当时跟他讲的那样，他假设了模拟可以替代实验，进而会形成一个科学不断加速发展的无休止循环。而我认为模拟在很大程度上无法替代实验。某些领域或许可以。亚历克斯，
<details><summary>Original English</summary>
>> in

 anything

 not

 just

 technology

 but

 that





said

 I

 think

 he's

 too

 enamored

 of

 fast





takeoff

 as

 I

 told

 him

 at

 the

 time

 he's





assuming

 simulation

 can

 substitute

 for





experiment

 and

 thus

 you

 get

 this





neverending

 loop

 where

 science

 just





keeps

 on

 accelerating

 and

 I

 don't

 think





simulation

 very

 much

 subs

 in

 for





experiment.

 It

 will

 in

 some

 areas.





Alex,
</details>

>> 我们观点一致。[笑声]
<details><summary>Original English</summary>
>> we

 agree.

 [laughter]
</details>

>> 我想，你知道，我深受卢卡斯批判（Lucas critique）的影响——抱歉又用了行业内话，但这基本上解释了为什么你必须理解问题的深层结构性参数，才真正有能力做出预测。模拟所做的事情以及 AI 真正擅长的事情是预测，但很多时候它并没有将系统的内生反应考虑在内。我们会看到这种情况越来越明显地显现出来。我认为……
<details><summary>Original English</summary>
>> I

 think

 you

 know

 I'm

 I'm

 too

 Lucas





critique

 pill

 uh

 for

 sorry

 another





another

 inside

 baseball

 but

 it's

 like





basically

 why

 you

 need

 to

 understand





kind

 of

 like

 the

 deep

 structural





parameters

 of

 the

 problem

 in

 order

 to





actually

 be

 able

 to

 predict.

 what





simulations

 do

 and

 what

 AI

 is

 really





good

 at

 is

 predicting,

 but

 it's

 uh

 it





doesn't

 take

 the

 indogenous

 response

 of





the

 system

 a

 lot

 of

 the

 time

 into





account.

 And

 um

 we'll

 we'll

 we'll

 see





that

 kind

 of

 play

 out

 more

 and

 more.

 I





think
</details>

### 《仿生人时代》与英伟达局势

>> 罗宾·汉森（Robin Hanson）的《仿生人时代》（The Age of Em），你认为那本书立得住吗，或者那些思想留下的遗产会是什么？
<details><summary>Original English</summary>
>> the

 um

 Robin

 Hansen's

 Age

 of

 M

 how

 do





you

 think

 that

 uh

 that

 stands

 up

 or

 will





the

 legacy

 of

 of

 those

 ideas

 be?
</details>

>> 嗯，我认为它是错的。那是一本非常精彩的书，我也很喜欢罗宾，但在它出版时——那已经是蛮久以前了——我就说：“罗宾，AI 会率先实现。”罗宾则说：“不，AI 也许会实现，但全脑仿真（Em）必定先到。”我说：“罗宾，全脑仿真可能永远都不会发生，即便发生，它也首先需要 AI。”我认为在这场辩论中我这一方目前看起来胜算很大。不过这确实是一本启发思考、能把你从教条迷梦中唤醒的好书。你们有没有……说到眼下的热点话题，英伟达目前处于巨大的舆论风口浪尖上，伴随着黄仁勋（Jensen）的处境。在你们观察公众舆论时，你们认为有哪些误解，或者你们如何解读这可能意味着什么、如果有的话从中能吸取什么教训？泰勒你怎么看？
<details><summary>Original English</summary>
>> Well,

 I

 think

 it's

 wrong.

 It's

 a





brilliant

 book

 and

 I

 love

 Robin

 but

 when





it

 came

 out

 which

 is

 now

 a

 while

 ago

 I





said

 Robin

 AI

 is

 going

 to

 get

 there





first

 and

 Robin

 says

 no

 AI

 might

 get





there

 but

 M

 has

 to

 come

 first

 and

 I

 said





Robin

 M

 probably

 will

 never

 happen

 but





if

 it

 does

 first

 it

 needs

 AI

 and

 I

 think





my

 side

 of

 that

 debate

 is

 looking

 very





good

 but

 it's

 a

 great

 book

 to

 read

 for





getting

 ideas

 and

 just

 shaking

 you

 out





of

 you

 know

 the

 dogmatic

 slumbers.

 Do





you

 have

 any

 We're

 right

 now

 talking

 of





speaking

 of

 timely

 issues

 sort

 of

 Nvidia





is

 sort

 of

 is

 in

 a

 big

 uh

 crosshairs

 at





the

 moment

 uh

 with

 sort

 of

 the

 Jensen





situation

 as

 you

 sort

 of

 view

 the

 public





discourse.

 what

 do

 you

 think

 is





misunderstood

 or

 or

 how

 are

 you

 sort

 of





interpreting

 um

 you

 know

 what

 this





potentially

 means

 or

 what

 lessons

 if

 any





to

 to

 take

 or

 what

 do

 you

 think

 Tyler
</details>

>> 你知道，我们之前就说过对齐是不可能的，利害关系又如此重大；他的行为、这家公司，某些方面似乎失衡了。事实上，因为有制衡机制，一切都会安好的。我不知道这些机制将如何发挥作用。我认为这是对我们一直在谈论的所有不同观点的一堂生动课程。
<details><summary>Original English</summary>
>> you

 know

 we've

 already

 said

 alignment

 is





impossible

 the

 stakes

 were

 so

 high

 his





behavior

 the

 company

 something

 seems

 out





of

 alignment





in

 fact

 it

 will

 be

 fine

 because

 of





checks

 and

 balances

 I

 don't

 know

 how





they're

 going

 to

 operate

 uh

 I

 think

 it's





a

 great

 lesson

 in

 all

 the

 different





things

 we've

 been

 saying
</details>

>> 亚历克斯，你有什么要补充的吗？
<details><summary>Original English</summary>
>> Alice

 anything

 you'd

 add
</details>

>> 对，我认为……我觉得这并不会真正改变其发展轨迹太多。我认为制衡机制是起作用的。我们在很大程度上拥有多样化的供应链。所有东西都处于超额认购状态。需求创造供给，供给创造需求。所以我认为系统本身是具备韧性的。最大的变化或许在于：如果宏观层面出现问题，而英伟达在失去了强有力的创始人兼 CEO，或者其受到削弱的情况下，不得不作为最后买家或最后贷款人介入——如果这一切从未发生，他们本可以更好地承担这一角色，如今这种能力大打折扣。这一点确实重要，但在中期来看，影响会被消化吸收，虽然它可能会让进程有所放缓。不过话说回来，结构性力量迟早会重新主导一切。嗯。
<details><summary>Original English</summary>
>> yeah

 I

 I

 think

 um

 you

 know

 I'm

 I I

 I

 I





think

 this

 is

 not

 really

 going

 to

 change





the

 trajectory

 much.

 I

 think

 like

 checks





and

 balances

 work.

 We

 have

 diversity

 in





the

 supply

 chain

 to

 to

 a

 large

 extent.





Um

 everything

 is

 over

 subscribed.

 Demand





creates

 supply.

 Supply

 creates

 demand.





Um

 so

 I

 think

 I

 think

 things

 are

 going





to

 uh

 you

 know

 the

 the

 the

 system

 is





robust.

 The

 biggest

 change

 might

 be

 if





something

 goes

 wrong

 at

 the

 macro

 level





and

 Nvidia

 had

 to

 step

 in

 as

 a

 buyer

 or





lender

 of

 last

 resort

 with

 a

 weakened

 or





gone

 CEO

 founder

 type.

 They're

 a

 lot





less

 able

 to

 do

 that

 than

 they

 would





have

 been

 had

 all

 this

 never

 happened.





Like,

 yeah,

 that

 matters,

 but

 in

 the





medium

 term,

 it's

 going

 to

 wash

 out

 and





it

 could

 slow

 things

 down

 a

 bit.

 But





again,

 the

 structural

 forces

 will

 take





over

 sooner

 or

 later.

 Mhm.
</details>

>> 如果让你预测下一部类似《态势感知》、将具有极高先见之明并对我们社会产生深远影响的文献类型，你认为它会出现在哪里？会在生物技术领域吗？还是说依然会是……
<details><summary>Original English</summary>
>> If

 you

 if

 you

 had

 to

 expect

 what

 is

 the





next

 genre

 of

 sort

 of

 situational





awareness

 like

 document

 that

 is

 going

 to





be

 remarkably

 preient

 and

 greatly

 impact





our

 society,

 where

 would

 you

 expect

 that





that

 to

 be?

 Would

 it

 be

 in

 something

 in





biotech?

 Would

 would

 still

 be
</details>

<!-- chunk 8/8 -->

在 AI 领域内的某些方向吗？比如，你们是怎么考虑目前有哪些被低估的想法，在未来几年可能会变得影响巨大的？
<details><summary>Original English</summary>
 in something in AI? Like how how are you thinking about sort of what are some underrated ideas right now that might be massive in the years to go?
</details>

### AI 结构模型与高等教育创新

>> 对我来说，它们也同样被低估了。我是说，大家都在谈论生物科技，我也完全赞同，但我认为那会格外缓慢，因为存在监管限制，而且无法通过模拟来解决主要问题。不过话又说回来，埃里克，我认为你能活到 120 岁，而我觉得我活不到。简单来说就是这样。我认为我们会获得更好的模型——在 AI 将为微观和宏观现象构建出更好的模型、比如更好的结构模型的程度上。比如类似细胞模型的构建，或者像实际使用数字孪生来进行宏观经济学分析之类的研究。只要你能为我们用于预测所需的事物赋予结构，我认为那将是真正的巨大爆发点。嗯，因为这有点契合经济学里的那种思想，也就是简化式与结构式的争论，在其中当你理解了结构，你就确实能创造出全新的东西。我认为 AI 在这方面的潜力——帮助你去理解并重建那种结构——我认为那真的被低估了。
<details><summary>Original English</summary>
>> Well, they're underrated to me, too. I mean, everyone talks about biotech and I'm fully on board, but I think that will be especially slow because of regulation and the inability to use simulation to address the main issues. But again, Eric, I think you'll live to 120 and I think I will not. That's a simple way to put it. I I think we're going to get better models of a to the extent that AI will create better models of micro and macro phenomenon like better structural models. So something like the model of the cell or like an like a act like using digital twins to do macroeconomics or something like that to the extent that you are going to be able to put structure on things that we need to be able to use to predict that's going to be the real big blow up I think. Um, and because that kind of gets to that idea in economics like the reduced form versus structural debate where you when you understand the structure, you can really create brand new things. And I think AI the potential for AI to do that to help you understand and recreate that structure. I think that's really underrated.
</details>

>> 那会很棒。拉杰·切蒂刚发了一篇关于数字孪生的新论文。
<details><summary>Original English</summary>
>> It'll be great. Ross Jetty has a new paper out on digital twins.
</details>

>> 没错。数字孪生。这正是我所指的。但他需要，你知道，五位共同作者、大笔资金以及一个研究中心，这很好。他做成了这件事非常棒。但这也能说明一些问题。

其实让我们以大学这个话题来收尾吧，因为我们之前说过，你知道，学界在某些方面是被低估的，在硅谷眼中肯定如此。既然我们已经给予了认可，我确实想问问你们两位，在高等教育的创新方面，你们对什么最感到兴奋？最紧迫的需求又在哪里？我们孵化了霍洛维茨和安德森学院，当然对这个问题很感兴趣。嗯，也许泰勒，我们先从你开始。
<details><summary>Original English</summary>
>> Exactly. Digital twins. That's exactly what I'm referencing. But he needed, you know, five co-authors and a lot of money and a research center, which is fine. It's wonderful that he's done it. But that also goes to show you something.

Let let's close on the university question actually because we we we said earlier, you know, the the the academy is underrated in in some ways, certainly by Silicon Valley. Now that we've, you know, given the the the props, I do want to ask you guys, where are you most excited um in terms of innovation uh uh in in higher education? and uh where is the the most sort of urgent need? We of course are interested in the question having incubated Harwitz and Dre Academy. Um maybe Tyler, we'll start with you.
</details>

>> 我希望你们大家能做点什么，花比你们已公布的更多的钱，并投入一些你们最优秀的人才。呃，我并不真正了解你们的计划是什么。呃，但我很乐意以某种方式参与进来。就像对奥斯汀大学、密涅瓦大学以及其他创新项目一样，我们在高等教育领域需要更多的实验、创新和测量。如果你能成为其中的一部分，我会非常兴奋。
<details><summary>Original English</summary>
>> I hope you all do something and spend more money on it than what you've announced and put some of your best people on it. Uh I don't really know what your plans are. Uh but I'd love to be involved in some way. And as with you Austin and uh Manurva and other innovations, we need much more experimentation, innovation, and measurement in higher ed. And if you're part of that, I'm thrilled.
</details>

>> 太棒了。我们非常希望能有你的参与。亚历克斯，关于在高等教育中尝试创新的任何人，你最感到兴奋的方向是什么，或者你可能有什么建议？
<details><summary>Original English</summary>
>> Amazing. I would love to have you. Alex, where are you most excited or uh what what advice might might you have to anybody trying to innovate in higher education?
</details>

>> 我认为创新越多越好。我认为高等教育将在接下来的——我不知道，我对其没有明确的时间表，只因为它们是运转如此缓慢的机构。嗯，而且，但我认为市场力量将导致我们对高等教育的标准认知、对该领域传统形态的认知发生萎缩。呃，但我认为我们将迎来大量新的创新，并且我们将——从长期来看，我对高等教育非常看好。这就是我要说的。
<details><summary>Original English</summary>
>> I think more innovation the better. I think higher ed's going to change drastically in the next I don't know. I I don't have a great timeline for it just because they're such uh slowmoving institutions. Um and uh but I think it's going to we're we're the forces of of the market forces are going to lead to a shrinking of the kind of our standard idea of higher ed of what that sector looks like the traditional version. Uh but I think we're going to have a ton of new innovation and um we're going to have I I'm very bullish in higher ed in the long term. That's that's what I'll say.
</details>

### 经济学工具箱与未来展望

你们两位目前看好经济学这个领域吗？你们对当下正在发生的事情感到鼓舞吗？嗯，你们持什么立场？
<details><summary>Original English</summary>
And are you both bullish on the field of e economics at the moment? Are you encouraged by what what's happening right now? Um where do you where do you stand there?
</details>

>> 我的意思是，我认为经济学工具箱和经济学思维方式被极大地低估了。所以我也带有极大的偏见。但我认为，就像我所看到的那样，你知道，我们之前讨论过关于对齐的问题，经济学工具箱非常适合从这种机制设计的角度来思考这个问题；而且在政治经济学问题中始终存在这种内生性问题，需要去通盘思考这些后果，通盘思考卢卡斯批判——比如，你知道，你估计了一个参数，但那实际上并不是一个结构参数，因此实际使用该参数来做决策是行不通的。所以所有这些事情都极其重要，而且我认为在未来的日子里它们会变得更加重要。所以我非常看好。
<details><summary>Original English</summary>
>> I mean I think the the economic toolkit and the economic way of thinking is extremely underrated. So I'm extremely biased too. But I think like the way that I that I I see things play out like you know we had the earlier question about you know alignment and um the economic toolkit is like is perfect for thinking about that through this mechanism design perspective and you have this type of thing going on all the time about like endogenity in the political economy question and thinking through these sorts of consequences thinking through the Lucas critique about like you know you estimate a parameter but that's actually not a structural parameter so it's not going to be valid to actually use that parameter in order to actually make the decisions. So all of these sorts of things are super important and they're going to be more important in the coming days, I think. So I'm I'm I'm I'm bullish
</details>

>> 而且它可能直接演变为社会科学。因此，经济学家不懂的事情，AI 会补足；而基础的思维工具箱会变得更加有价值。这最初是加里·贝克尔等人提出的芝加哥学派构想。

并且，呃，你只需要那些真正聪明、具备一些有点像我们现在称之为软件工程师技能的人，不过它会有自己的新名称。他们操控着全局，管理着一群 AI 智能体，他们是操控者，并且懂经济学并从事整个社会科学研究。这就是我所预期的。可以说是早期芝加哥愿景的真正实现。
<details><summary>Original English</summary>
>> and it may just become social science. So the thing the things economists don't know, the AI fills in for the basic metal toolkit becomes more valuable. This is originally a Chicago idea from Gary Becker and others.

And uh you just want really smart people who have some skills a bit like those that we now call software engineers, but it will have its own name. And they have their fingers on the dials and they manage a bunch of AI agents and they're emparios and they know economics and do all of social science. That's what I expect. So a true realization of the earlier Chicago vision.
</details>

>> 我来自芝加哥大学，所以我认同那个愿景。我对那个愿景感到满意。我们也许会在芝加哥大学把它做成。
<details><summary>Original English</summary>
>> I'm from the University of Chicago, so I I I I buy that vision. I'm happy with that vision. We maybe we'll do it at the University of Chicago.
</details>

>> 非常精彩的首尾呼应时刻，以此来结束对话。呃，泰勒、亚历克斯，非常感谢你们来到播客。
<details><summary>Original English</summary>
>> Amazing full circle uh moment to end the conversation. Uh Tyler, Alex, thank you so much for coming to the podcast.
</details>

>> 谢谢。非常荣幸。
<details><summary>Original English</summary>
>> Thank you. My pleasure.
</details>