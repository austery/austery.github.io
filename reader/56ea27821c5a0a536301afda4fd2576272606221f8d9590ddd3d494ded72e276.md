---
author: a16z
date: '2026-09-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3T5sij3spWw
speaker: a16z
tags:
  - ai-agent
  - personal-assistant
  - benchmark
  - business-model
title: 个人 AI 智能体的演进、主动性与商业模式探讨
summary: 对话探讨了消费级个人 AI 智能体的发展脉络、Assistant Bench 基准测试、主动性壁垒及性格配置，并分析了长尾初创公司面临的成本挑战与商业化模式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - David Pollen
companies_orgs:
  - A16Z
  - OpenAI
products_models:
  - ChatGPT
  - Muse
  - Instinct
  - Poke
  - Assistant Bench
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

普通大众并不在乎效率提高 10%。我有一个很大胆的观点：这款 Muse 吊坠实际上并非想在硬件游戏上取胜，[音乐] 它更多是为了在真实世界中收集数据，以此推动扎克伯格构建真实世界图景的未来元宇宙。

<details><summary>Original English</summary>
the general population does not care about being 10% more efficient. I have a hot take thesis that this Muse charm is actually less about trying to win the hardware game [music] and it's more about data collection in the real world to fuel Zuckerberg's future metaverse of mapping out the actual world.
</details>

>> 我们内部开玩笑说，好像再过几天，就会有智能体发消息告诉某人：“我注意到你没那么喜欢她，所以我就自作主张跟她提分手了。”

<details><summary>Original English</summary>
>> We were joking internally like we're days away from an agent messaging someone saying I noticed you weren't that into her so I went ahead and broke up with her.
</details>

>> 主动性拥有极大的防御壁垒。我之前骑车上班，想要把事情做完，就直接开始跟 ChatGPT 语音对话。在我骑车上班的 30 分钟里，它帮我分类了邮件，归入不同标签，发出了日历邀请，等我到工位时，收件箱已经清空了。但这会是一条非常微妙的界线，因为一旦越界一次，你就会彻底失去用户的信任。

<details><summary>Original English</summary>
>> There is massive defensibility around proactivity. I was biking to work. I want to get stuff done and I just start talking to chat GBT voice and throughout my 30-minute bike ride to work categorized my emails submitted them to different labels sent out calendar invites got to the desk inbox zero but it will be a very fine line because if you cross that line once you lose all trust with your user
</details>

>> 确实感觉会存在仅用于智能体之间交互的基础设施和产品，而这些在今天是不存在的。你怎么看？

<details><summary>Original English</summary>
>> does feel like there's going to be infrastructure and products that exist only for agentto agent interactions that doesn't exist today what do you think
</details>

>> 我们必然会看到……

<details><summary>Original English</summary>
>> it is inevitable that we're going to see
</details>

### 个人 AI 智能体的演进

好了，欢迎收看 A16Z 节目。我非常激动能与我的朋友 David Pollen 在这里交流。我们几周前聚过一次，我们俩都对个人助理以及整个消费级 AI 领域正在发生的一切充满了热情。天哪，过去几周发生了太多的事情。

可以说作为铺垫，我觉得整个生态系统的某些部分曾经历过几次“顿悟”的时刻。ChatGPT 就是一个重要的节点。我想对于很多人来说，在 2022 年 11 月以及 2023 年初那阵子，大家的感觉就是：这个能写邮件、能写诗、能开始来回对话、让你感觉像是在和一个虚拟人互动的到底是个什么东西？那当然是开端，是宇宙大爆炸。

第二个时刻真正属于代码智能体，以及开发者们围绕 Claude Code、Codex 这类工具的狂热，还有极其轻松构建软件的能力。

最后，就是最近随着 Instinct、Muse 和 ChatGPT 的工作进展，大家对个人智能体以及它们能为我们消费者做些什么，产生了无与伦比的热情。所以，我们今天就是来聊聊关于个人智能体的一切。我们要尽可能深入地去探讨。我们会假设大家都已经看过了我们所看到的许多同样的事物，并且我们要把这做成一系列对话中的第一期。欢迎你，David。

<details><summary>Original English</summary>
All right, welcome to the A16Z show. I'm so psyched to be here with my friend David Pollen. We hung a couple of weeks ago. We're both so enthusiastic about everything that's been happening with personal assistant um and consumer AI generally. And man, so much has happened in the last couple of weeks. Maybe to tee it up, you know, I sort of think that there's been a few moments where some part of the, you know, ecosystem has sort of seen God. Um and chatbt was a big one. And you know, I think for a lot of folks in November 22 and a bit of 23, it was like, what is this thing that can, you know, write emails and poems and, you know, start to have a conversation back and forth and feel like you're interacting with the synthetic person? That was of course the the beginning, the big bang. Um, the second moment really was coding agents and everything that developers have been obsessed with around sort of quad code and codecs and the ability to trivially create software. And then finally, most recently with Instinct, Muse, and ChachiPT work, we've had this extraordinary enthusiasm around personal agents and what they can do for us as consumers. So, we're here to talk about all things personal agents. Um, we're going to go as deep as we can. We're going to assume that everybody has seen many of the same things that we have seen and we're going to make this the first in a series of conversations. Welcome, David.
</details>

>> 谢谢。感谢邀请。很高兴来到这里。让我们退一步，来聊聊过去几个月、过去几周个人智能体的发展轨迹。你最近都看到了什么？你对这些事情有什么看法？

<details><summary>Original English</summary>
>> Thank you. Thanks for having me. Excited to be here. Let's like zoom out and and maybe talk about you know the arc of uh personal agents over the last few months, the last few weeks. What have you been seeing? What's your sort of view on things?
</details>

>> 是的，这个领域在过去四周里迎来了爆发。我们可以倒回去看。我是 Poke 的早期使用者。我想说 Poke 大概是首批真正打入市场的消费级 AI 智能体之一。是的，它是在 9 月 8 日上线的，然后我在大约三天后的 9 月 11 日开始使用它。我记得特别清楚，因为那简直是一次令人难以置信的体验。他们整个的噱头就是由你和智能体去谈判最终实际支付多少费用。这彻底震撼了我。

然后到了 11 月下旬，OpenClaw 发布了，它犹如风暴一般席卷了现实世界，让人觉得确实有什么东西要来了。之后这里那里又冒出了一些其他的，但最近我们看到 Instinct 彻底引爆了科技推特圈。它完全是掀起了一股热潮，引发了轰动，接着就像多米诺骨牌一样。有了 Grockbot，有了 Muse，还有一大批长尾产品，比如 Caddy、Ali 或者 Pi。

看到这个景象真的很不可思议，整个人群全都在爆发极大的兴趣和求知欲，想知道这些智能体在日常生活中究竟能为我们做什么。而且我觉得大家目前基本上都处在同一条船上，谁也不完全清楚，这里就像蛮荒的西部一样，我们只是在这里摸索玩耍。

<details><summary>Original English</summary>
>> Yeah, so this space has exploded over the past four weeks. We can roll it back. I was I was an early adopter of Poke. So I want to say Poke, which was kind of one of the first like consumer AI agents to really hit the market. Yes. That launched I believe it was September 8th and then I started using it September 11th, like 3 days later. And like I remember it so vividly cuz it was just an unbelievable experience. Their their whole gimmick was this, you know, negotiation with the agent on how much you're actually going to pay. And it totally blew my mind. Um then comes late November and Open Claw gets released and that kind of takes the actual world by storm of like there is there is something coming. And then a few other have popped up here and there, but most recently we saw Instinct really blow up the the tech Twitter bubble. just absolutely rode a wave, went nuts, and then it was just dominoes. You have Grockbot, you have Muse, you have a bunch of longtail ones like Caddy or Ali or Pi. And it's really been amazing to see, you know, this whole tech bubble is just exploding with interest and like an intellectual curiosity for what can these agents do for us on a day-to-day basis. And there's uh I think everyone's kind of in the same boat where nobody really knows like it's it's the wild wild west. We're just playing around here.
</details>

### Assistant Bench 基准测试

>> 我完全同意。我们应该花点时间谈谈 Assistant Bench，这是你发起的一个新的、非常重要且引发了广泛讨论的基准测试。或许可以先稍微介绍一下 Assistant Bench 的背景，然后我问你几个问题。

<details><summary>Original English</summary>
>> I totally agree. And you we should take a moment to talk about Assistant Bench, which is this new, you know, really important and discussed benchmark that you're the author of. Maybe tee up Assistant Bench a little bit and then I'll ask you a few questions.
</details>

>> Assistant Benchmark 是一个基本上基于使用场景来对比所有这些 AI 助理的网站。我们会给所有这些助理提出相同的提示词：“帮我订一张去芝加哥的机票”、“在我特定位置的五个街区内找一家素食餐厅”，等等。我们在单次提示上对比它们最终的实际结果。它真的能用吗？它会问后续问题吗？它在 16 个不同的维度上表现如何？我们把这些都进行了对比。

所以我们用了“基准”这个词，但你可以把它更多地看作是一个面向消费者的基准测试，不一定是幕后技术层面的，而是如果我想订机票，我到底该用哪一个？谁的表现最好？它们实际回复有多快？

我之所以进入这整个对比工作，是因为我自己当时在做市场调研，试图弄清楚它们彼此之间到底如何对比，有哪些差距？我公开了一部分内容，那是大约两周前，到今天为止正好是我们上线它的第 16 天，它就彻底爆发了。网站获得了超过 10 万次浏览，访问者超过 10 万人，基本上每一位创始人都有跟我接洽。我觉得这真的充分表明了大家的好奇心，大家都在寻找这个行业将走向何方的答案。

<details><summary>Original English</summary>
>> Assistant Benchmark is a site that essentially compares all these AI assistants on a use case basis. So we're asking all of these assistants the same prompt. Book me a flight to Chicago. find me a vegetarian restaurant within five blocks of my specific location, etc., etc. And we're comparing the actual outcome on like on a oneshot prompt. Does it actually work? Does it ask follow-up questions? How does it perform across 16 different dimensions? And we compare those all. So, it's we use the word benchmark. Think of it more as like a consumerf facing benchmark, not necessarily technical behind the scenes, but if I want to book a flight, which one should I actually use? Who is performing the best? how fast are they actually replying? Got into this whole comparison because I was just doing market research myself trying to figure out how are these all comparing against one another? What are the gaps? And uh published a bit of that and it was uh almost two weeks ago. It's 16 days ago today that we launched it and it's just absolutely exploded. It's, you know, over 100,000 views on the the website has website has had over 100,000 visitors have out had outreach from basically every single founder. Um, and I think it really just goes to show like everyone's curious. People people are looking for for answers to where this industry is is moving.
</details>

>> 那么跟我们详细聊聊吧，David。这太令人兴奋了。能看到……很有趣的是，基准测试现在已经成了对话中如此重要的核心内容，因为有太多的新产品发布，很难把每样东西都试一遍，这也是一个令人兴奋的信号。也许可以跟我们聊聊除了 Instinct 和 Muse 之外的其他所有人。我们稍后肯定会深入探讨这两个，但你觉得还有谁在做有趣的工作？你看到了哪些专业化的发展方向？

<details><summary>Original English</summary>
>> And so talk us through David. That's incredibly exciting. It's cool to actually It's funny how benchmarks have become such a staple now of the conversation because it's so there's so many launches it's hard to try everything which is also an exciting signal. Maybe talk us through everybody who's not Instinct and Muse. We're definitely going to deep dive on those later, but who else do you think is doing interesting work and what are the kind of directions of specialization that you're seeing?
</details>

>> 确实。我们看到市面上有一大批长尾解决方案。我认为可以把它们分为两类：一类是面向 B2C 消费者的通用型智能体，就像 Instinct 或 Muse。长尾一些的包括 Caddy、Ali、Season。目前光是网站上的通用类别里，我相信就有 64 个。然后我们还可以在此基础上进一步细分，细分到更专业一点的领域，比如针对旅行的，像 Soore 或 Miso；也可以有专门针对电子邮件的。

另一类则更偏向于 B2B 工作流类型的助理。那些包括了从 The Town 到 Catch 再到 Vellum 的所有产品。它们基本上都在做同样的事情，对吧？它们是你的助理，实际上更像是一个执行行政助理，而不是面向消费者的那种方式。目前大致的格局就是这样。据我目前所知，各个类别加起来共有 122 个不同的产品。

<details><summary>Original English</summary>
>> Totally. So, we've got a bunch of longtail solutions out there. I think I would categorize it into two groups. You have like the BTOC consumerf facing generalized agents. That's like the Instinct or Muse. Um, some of the longer tail ones, you have Caddy, you have Ali, you have Season. Um there's I believe 64 right now just in the general category on the site and then we can break that down even further into a little more specialized within that. So you can have travel specific ones uh like soore or miso. You can have email specific ones. The other side of the spectrum is going to be more of like your B2B workflow type uh assistants. And those are, you know, anyone from the town to catch to Vellum. And they're all essentially doing the same thing, right? They're they're your assistant that's actually like more of like an executive assistant, not not the consumerf facing um approach to it. And that's kind of like the general landscape at the moment. Um, so far to my knowledge there are 122 different ones.
</details>

>> 哇。

<details><summary>Original English</summary>
>> Wow.
</details>

>> 涵盖所有类别。

<details><summary>Original English</summary>
>> Across all the categories.
</details>

>> 不可思议。那聚焦的领域呢？最受关注的竞争焦点在哪里？

<details><summary>Original English</summary>
>> Incredible. And what about areas of concentration? Where is the most sort of interesting competitive focus?
</details>

>> 目前大家总体上都在关注通用……

<details><summary>Original English</summary>
>> So everyone right now by and large is focusing on the generaliz like
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 就是试图面面俱到。

<details><summary>Original English</summary>
>> Just trying to do trying to do everything.
</details>

>> 当你考虑到像旅行这样的场景时，拿它来举例，这是一种低频但高价值的行为。你认为这个类别最终会更多地作为一个连接器接入横向智能体，还是说你认为它们也有机会作为通用横向智能体胜出？

<details><summary>Original English</summary>
>> And when you think about something like travel, just to pick on that, that's an infrequent high value behavior. Do you think that that category ends up being organized more as a connector into the horizontal agent or do you think they have the right to win as a general horizontal agent as well?
</details>

>> 我觉得或许有可能看到一个赢家作为独立的智能体存在，但大体上我真的认为它会更多地充当一个连接器。我现在有大概七八个不同的群聊，里面全都是对智能体着迷的人在交流。所有群聊加起来现在有超过 1,200 人在不断地讨论。旅行是讨论度排名第四的用例，这非常有意思，因为当你看到……

<details><summary>Original English</summary>
>> I think you're going to maybe see potentially one winner as as an independent agent, but by and large I really think it is going to be more of a connector. Um, so I have like seven or eight different group chats now with just individuals obsessed with assistants talking. There's now over 1,200 people across all of the group chats just chatting over and over and over. Travel is the fourth most talked about use case, which is really interesting because when you look at
</details>

<!-- chunk 2/7 -->

### 常见用例与实际需求

比如像病毒式传播这种，大家议论最多的往往是“它帮我办理了航班值机”、“我能用它订机票了”这类场景。但当你真正去看大家日常到底在用它做什么、对什么最好奇时，就会发现正如你所说，人们并不会每天都去旅行。所以，这……

<details><summary>Original English</summary>
like

 virality,

 it

 tends

 to

 be

 the

 number





one

 that

 people

 are

 talking

 about

 of

 it





checked

 into

 my

 flight

 for

 me.

 I

 was





able

 to

 book

 my

 flight.

 But

 then

 you





actually

 look

 at

 the

 day-to-day





conversations

 of

 what

 people

 are

 really





using

 it

 for

 and

 most

 curious

 about.

 To





your

 point,

 people

 aren't

 traveling





every

 day.

 So,

 it's
</details>

>> 这更像是一种噱头，对吧？也就是博人眼球罢了。

<details><summary>Original English</summary>
>> it's

 it's

 more

 of

 a

 gimmick,

 right?

 It's





it's

 an

 attention

 grabb.
</details>

>> 那排名前三的用例都是什么？

第一类更多是日常行政事务性质的事，比如清理收件箱，或者帮你填表。都是些非常烦人的琐事，我认为这触及到了一个更广泛的论点，即未来这个领域的赢家会走向何方，稍后我们可以探讨一下。

<details><summary>Original English</summary>
>> What

 are

 use

 cases

 one

 to

 three?





So,

 number

 one

 is

 more

 uh

 just

 daily





admin

 type

 stuff,

 whether

 it's

 cleaning





out

 your

 inbox,

 whether

 it's

 filing





forms

 for

 you.

 Um

 the

 things

 that

 are





are

 really

 annoying

 and

 I

 think

 that





gets

 to

 the

 broader

 thesis

 of

 where

 I





think

 the

 winner

 of

 the

 space

 will

 go





that

 that

 we

 can,

 you

 know,

 touch

 on.
</details>

>> 第二类更多会是智能体编排（agent orchestration），这非常有意思。我觉得这些群聊可能有点偏差，因为第三类是偏向开发的。好的，

<details><summary>Original English</summary>
>> Um

 the

 second

 is

 going

 to

 be

 more

 agent





orchestration,

 which

 is

 really





interesting.

 I

 think

 these

 group

 chats





are

 a

 little

 biased

 as

 the

 third

 one

 is





uh

 development

 focused.

 Okay,
</details>

>> 这些群聊里全都是科技推特圈（tech Twitter）的人，对吧？所以它不一定能代表整个大环境。

是的，不过大家确实在热烈讨论智能体编排，比如如何找到最高效的智能体，或者如何让智能体之间相互沟通交流。开发类智能体方面，如今又是如何转化为手机上的编程环境的？无论是通过文本组件使用 Claude Code，还是更进一步——如果我是一名设计师，我现在能不能只通过给我的智能体发短信，比如做一些微小的迭代更改，就能对设计文件进行编辑？

<details><summary>Original English</summary>
>> these

 are

 all

 group

 chats

 with

 people

 in





tech

 Twitter,

 right?

 So,

 it's

 it's

 not





necessarily

 representative

 of

 of

 the





world

 at

 large.

 Yeah,

 but

 uh

 people

 are





talking

 a

 ton

 about

 agent

 orchestration





and

 how

 do

 you

 find

 the

 most

 efficient





agent

 or

 how

 let

 your

 agents

 talk

 to





each

 other.

 uh

 development

 agents,

 how





does

 this

 now

 translate

 to

 this

 coding





world

 on

 your

 phone?

 Whether

 it

 be,

 you





know,

 using

 claude

 code

 from

 a

 text





component

 or

 even

 take

 it

 one

 step





further

 of,

 okay,

 if

 I'm

 a

 designer,

 can





I

 now

 make

 edits

 to

 my

 design

 files

 by





just

 like

 texting

 my

 agent

 of

 like





little

 small

 iteration

 changes?
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 然后最后一类就是金融。我觉得研究这个类别是最有意思的，因为在我看来它是最不切实际的。里面涉及的决策太多了，对吧，如果能让一个智能体替你赚到十亿美元，各大对冲基金早就这么干了。这不是每个人拿着自己的手机就能办成的事。但最耐人寻味的是，你只要给某人一个智能体——一个握在手里的强大工具，他们脑海里跳出的第一件事就是：好吧，你打算怎么帮我赚到一百万美元？

<details><summary>Original English</summary>
>> And

 then

 the

 last

 category

 being





finance.

 Um

 I

 think

 that's

 the

 most

 fun





one

 to

 look

 into

 because

 it

 is

 in

 my





opinion

 the

 least

 practical.

 Like





there's

 so

 many

 decisions

 and

 right

 like





if

 you

 could

 have

 an

 agent

 make

 a





billion

 dollars

 for

 you

 all

 the

 hedge





funds

 would

 be

 doing

 it.

 It's

 it's

 not





something

 that

 like

 everyone's

 going

 to





succeed

 at

 with

 their

 own

 phone.

 But

 it





is

 the

 most

 interesting

 that

 you

 give





someone

 an

 agent

 a

 powerful

 tool

 right





in

 their

 hands

 and

 the

 first

 thing

 they





think

 is

 okay

 how

 are

 you

 going to

 make





me

 a

 million

 dollars?
</details>

### 省钱与隐形智能体

>> 对，对。这确实很有意思，因为有这样一种批评观点——前几天本·汤普森（Ben Thompson）在 TVPN 上就谈到，大多数消费者在日常生活中其实并不是在追求生产力。他们想要的是消磨时间，而不是节省时间，这一点我很赞同。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 It's

 really

 interesting





because

 one

 of the

 critiques,

 you

 know,





Ben

 Thompson

 was

 on

 TVPN

 a

 few

 days

 ago





talking

 about

 how

 most

 consumers

 aren't





looking

 for

 productivity

 uh

 in

 their





lives.

 They're

 looking

 to

 spend

 time

 not





save

 time

 which

 I

 agree

 with
</details>

>> 但感觉金融确实属于一个普通消费者要面对大量行政杂务负担的领域。

<details><summary>Original English</summary>
>> but

 it

 does

 feel

 like

 finance

 is

 an

 area





in

 which

 it

 is

 there

 is

 a

 ton

 of





administrative

 overhead

 for

 the

 average





consumer
</details>

>> 而且如果你去看看那些因消费者冷漠或不知情而形成的金融市场或金融利润池，就会发现其实有大笔利润是可以重新回馈给消费者的，对吧，所以……

<details><summary>Original English</summary>
>> and

 if

 you

 look

 at

 you

 know

 the

 number





of

 financial

 markets

 or

 financial

 sort





of

 profit

 pools

 that

 are

 defined

 by





consumer

 apathy

 or

 being

 uninformed





that's

 a

 lot

 of

 profit

 dollars

 that





could

 be

 delivered

 back

 to

 the

 consumer





right

 so

 y
</details>

>> 我确实认为，虽然我大体同意本的看法，即大多数消费者追求的是娱乐和打发时间，但在美国消费者的生活中，也存在着一些具有决定性特征的方面，它们带有繁重的行政事务性质，而这些智能体在这些方面确实能带来突破。

<details><summary>Original English</summary>
>> I

 do

 think

 that

 the

 you

 know

 while

 I





generally

 agree

 with

 Ben

 that

 most





consumers

 are

 looking

 for

 entertainment





and

 dispens

 time.

 I

 think

 there

 are

 sort





of

 defining

 aspects

 of

 the

 US

 consumer's





life

 that

 are,

 you

 know,

 heavily





administrative

 that

 these

 agents

 can





really

 be

 a

 breakthrough

 for.
</details>

>> 完全正确。我认为这触及到了关于未来赢家会落在何处的大致论点。那就是，正如本所指出的，我也同意，我认为普通大众根本不在乎效率是否能提高 10%。

<details><summary>Original English</summary>
>> Totally.

 And

 I

 think

 that

 that

 kind

 of





touches

 on

 the

 general

 thesis

 to

 where

 I





think

 the

 winners

 will

 sit.

 And

 that

 is





that

 like

 to

 Ben's

 point,

 I

 I

 agree.

 I

 I





think

 the

 general

 population

 does

 not





care

 about

 being

 10%

 more

 efficient.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你雇一位助理是为了让他保持隐形，对吧？就像我共事过最优秀的员工，就是那些只管埋头做事、把事情办妥，然后向你汇报“给，这是我做好的成果”，而你就会觉得“哇，太棒了”。你雇人可不是因为你享受管理别人的过程。

<details><summary>Original English</summary>
>> You

 you

 hire

 an

 assistant

 to

 allow

 it

 to





be

 invisible,

 right?

 like

 the

 the

 best





employee

 I've

 ever

 had

 are

 the

 ones

 that





are

 just

 doing

 their

 work,

 getting





things

 done,

 they

 update

 you

 like

 here,





here's

 what

 I

 did,

 and

 you're

 like,





"Wow,

 amazing."

 I

 like,

 you

 know,

 you





don't

 hire

 someone

 because

 you

 enjoy





managing

 them.
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而我看到的最优秀、最主动的用例，我认为确实落在了金融类别里。

<details><summary>Original English</summary>
>> And

 the

 best,

 most

 proactive

 use

 cases





I'm

 seeing,

 I

 think,

 do

 fall

 in

 the





finance

 category.
</details>

>> 并且我认为我们将看到的是一个不是花钱而是省钱的世界的大爆发。所以这将是这样一些工作流程，比如我看到的一些很酷的用例，有人用它去梳理过去一年的收据并提交 HSA（健康储蓄账户）报销。哦，真棒。

<details><summary>Original English</summary>
>> Um,

 and

 I

 think

 we're

 going

 to

 see

 an





explosion

 in

 a

 world

 though

 where

 it's





not

 cost

 makers,

 it's

 cost

 savers.

 And





so

 it's

 going

 to

 be

 workflows

 where

 um





like

 some

 cool

 use

 cases

 I

 saw

 people





are

 using

 it

 to

 go

 through

 their

 past





year

 of

 receipts

 and

 file

 HSA





reimbursements.

 Oh,

 cool.
</details>

>> 或者我自己常用的一个操作是：每当我订了机票，如果机票降价了，对。

<details><summary>Original English</summary>
>> Or

 um

 one

 that

 I

 do

 is

 anytime

 I

 book

 a





flight,

 if

 the

 flight

 price

 drops,

 Yeah.
</details>

>> 我就会让我的助手联系航空公司，帮我拿到旅行代金券。

<details><summary>Original English</summary>
>> I

 then

 have

 my

 assistant

 hit

 up

 the





airline

 and

 get

 me

 a

 travel

 credit.
</details>

>> 哇。

<details><summary>Original English</summary>
>> Wow.
</details>

>> 还有，我有个朋友——这大概是我目前见过的最喜欢的用例了。他把自己的 Grockbot 连到了家里的喷淋系统，并接入了天气系统。哦，聪明。

<details><summary>Original English</summary>
>> And

 um

 I

 have

 a

 friend,

 this

 is

 my





favorite

 use

 case

 I

 think

 I've

 I've

 seen





yet.

 He

 hooked

 up

 his

 Grockbot

 to

 his





sprinkler

 system

 at

 his

 home

 and





connected

 it

 to

 the

 weather

 system.

 Oh,





smart.
</details>

>> 这样一来，他的喷淋器就会根据天气情况运行，他的水费账单直接降低了 50%。

<details><summary>Original English</summary>
>> And

 so

 now

 his

 sprinklers

 are

 dependent





on

 the

 weather

 and

 it's

 dropped

 his





water

 bill

 by

 50%.
</details>

>> 是的。所以我觉得这些将要处理这类省钱流程的隐形智能体，虽然属于金融类别，但它们真正聚焦的是这类省钱活动，从而创造一个更加契合消费者利益的世界。

<details><summary>Original English</summary>
>> Yeah.

 And

 so

 I

 think

 these

 like





invisible

 type

 agents

 that

 are

 going

 to





be

 doing

 these

 cost-saving

 type





workflows

 um

 fall

 within

 that

 finance





category,

 but

 but

 they're

 really

 going





to

 lean

 into

 these

 like

 cost-saving





activities

 that

 create

 a

 world

 that

 is

 a





lot

 more

 consumer

 aligned.
</details>

>> 是的。这也会很有意思，比如我认为对于美国消费者来说，没人想听省钱的事，大家都想听花钱和免费拿钱的事。

<details><summary>Original English</summary>
>> Yeah.

 It'll

 be

 interesting

 too

 like

 I





think

 the

 American

 consumer

 nobody

 wants





to

 hear

 about

 saving

 money.

 People

 want





to

 hear

 about

 spending

 money

 and

 free





money.
</details>

>> 而我其实认为吸引很多人的切入点在于，这会让人感觉像是在白拿钱。比如回过头去提交 HSA 退款申请，感觉就像是白拿钱。把所有降价机票的差额退回来，感觉也像是白拿钱。所以我觉得这是一个极其强大的吸引点。这同时也非常非常有意思，因为这属于一种低频但高价值的行为，这也是我对旅行和金融这两个领域的思考方向——也许这些会成为非常强大、估值达十亿美元的业务，但它们仍然是垂直领域的连接器，而不是通用的横向智能体。

<details><summary>Original English</summary>
>> And

 I

 actually

 think

 the

 hook

 that's





going

 to

 get

 a

 lot

 of

 people

 here

 is





it's

 going

 to

 feel

 like

 free

 money.

 like





going

 back

 through

 and

 you

 know





submitting

 HSA

 um





sort

 of

 refund

 requests

 is

 going

 to

 be





free

 money.

 You

 know

 getting

 all

 of

 your





airline

 tickets

 where

 the

 price

 is





dropped

 you

 know

 to

 refund

 you

 the

 delta





is

 going

 to

 be

 free

 money.

 So

 I

 think





that

 that's

 a

 hugely

 powerful

 hook.

 It's





also

 really

 really

 interesting

 because





this

 is

 a

 sort

 of

 infrequent

 but





high-value

 behavior

 and

 that's

 where

 my





head

 goes

 on

 both

 travel

 and

 finance





like

 maybe

 these

 things

 will

 be

 really





powerful

 you

 know

 billion-dollar





businesses

 that

 are

 still

 vertical





connectors

 rather

 than

 general





horizontal

 agents.
</details>

### 交互界面与产品形态

>> 确实如此。就应用阶段而言，这将是一个非常有趣的世界。我想这也就是上次我们去散步时聊过的内容，当时讨论的是：好了，既然它能做这些，那么你究竟要如何与这个智能体交互？这也是我们聊过的一点，我很想听听你的看法。对吧，比如我们俩都习惯使用 iMessage，那是我们日常所在的地方，对我们来说更方便。你提到你妻子和她的朋友们更倾向于使用单独的应用程序，对吧。

<details><summary>Original English</summary>
>> Totally.

 It's

 it's

 going

 to

 be

 a

 very





interesting

 world

 in

 terms

 of

 the





application

 phase

 which

 I

 think

 then

 you





know

 that

 also

 something

 that

 we

 talked





about

 last

 time

 we

 went

 for

 the

 walk

 was





okay

 here's

 what

 it

 can

 do

 but

 now

 how





do

 you

 actually

 interact

 with

 that

 agent





um

 and

 something

 that

 we

 chatted

 on

 I'm





curious

 your

 thoughts

 right

 so

 like

 we





both

 were

 in

 the

 world

 of

 iMessage

 it's





where

 we

 live

 it's

 easier

 for

 us

 um

 you





mentioned

 your

 wife

 and

 her

 friends





prefer

 a

 separate

 application

 yeah
</details>

>> 那么你觉得这个世界会走向何方？你认为会有多个不同界面并存成为赢家，还是会出现一条占主导地位的赛道？

<details><summary>Original English</summary>
>> and

 so

 like

 where

 do

 you

 see

 this

 world





moving

 do

 you

 believe

 that

 mult

 multiple





surfaces

 can

 exist

 as

 a

 winner

 or





there's

 going

 to

 be

 one

 dominant

 lane.
</details>

>> 是的，问得太好了，兄弟。我的意思是，我认为这就是为什么会有很多消费者偏好在此发挥重要作用。因为我听过这样一种说法：对于 Z 世代的人群来说，他们更倾向于直接发短信；而对于千禧一代或 X 世代的人群来说，他们更青睐应用界面。所以我认为一部分原因可能因代际而异，

<details><summary>Original English</summary>
>> Yeah,

 that

 it's

 a

 great

 question,

 man.

 I





mean,

 I

 think

 this

 is

 why

 there's

 so





much

 consumer

 preference

 that's

 going

 to





matter

 here

 because

 I've

 heard

 the





argument

 that

 for

 folks

 that

 are

 Gen

 Z,





they're

 more

 interested

 in

 just

 texting





and

 for

 folks

 that

 are

 millennial

 or

 Gen





X,

 they're

 interested

 in

 app

 interfaces.





So,

 I

 think

 part

 of

 it

 may

 um

 fragment





by

 generation,
</details>

>> 在某种程度上，一部分原因可能也确实会因性别而分化。我的意思是，这是一种概括，但看看我做的事情和我妻子做的事情之间的差异——她热衷于制作愿景板（dream board），努力去实现她所有的年度目标和终身目标。因此她确实更喜欢视觉化的界面。对她而言，很多旅行规划在很大程度上是由视觉驱动的；而对我来说，则实用得多，比如“嘿，我怎么从 X 处到达 Y 处？如果飞机上能配有星链（Starlink）那就更理想了”，这对我更奏效。我觉得 iMessage 有点像……

<details><summary>Original English</summary>
>> part

 of

 it

 may

 actually

 fragment

 by





gender

 as

 well

 to

 some

 extent.

 I

 mean,





it's

 a

 generalization,

 but

 the

 types

 of





things

 I'm

 doing

 versus

 the

 types

 of





things

 my

 wife

 is

 doing,

 you

 know,

 she's





big

 on

 building

 a

 dream

 board

 and

 trying





to

 achieve

 all

 of

 her

 one-year

 goals

 and





her

 lifelong

 goals.

 So,

 she

 really





prefers

 a

 visual

 interface.

 You

 know,





she

 does

 a

 lot

 of

 sort

 of

 travel

 is

 is





very

 visual

 driven

 for

 her,

 whereas

 for





me,

 it's

 much

 more

 functional

 like,

 hey,





how

 do

 I

 just

 get

 from

 X

 to

 Y?

 Ideally,





with

 Starlink

 on

 my

 plane,

 um,

 which





works

 better

 for

 me.

 I

 feel

 like





iMessage

 sort

 of
</details>

>> iMessage 空间显得更为珍贵。

<details><summary>Original English</summary>
>> the

 iMessage

 space

 is

 more

 precious.
</details>

>> 所以当我在那个空间里时，感觉像是一种更私人的互动。当然，如果每两条消息对话里就有一个是智能体，那种感觉就会改变。但目前而言，我觉得它在我的手机里占据了一个享有特权的位置，而应用抽屉里的 App 却做不到这一点。你怎么看？

<details><summary>Original English</summary>
>> So

 it

 feels

 like

 a

 more

 personal





interaction

 when

 I'm

 in

 that

 space.

 And





now

 of

 course

 that

 changes

 if

 every





second

 thread

 is

 with

 an

 agent.

 But

 for





now

 I

 feel

 like

 it

 kind

 of

 lives

 in

 a





privileged

 place

 on

 my

 phone

 where

 you





know

 the

 app

 on

 the

 app

 grid

 just





doesn't.

 What

 do

 you

 think?
</details>

>> 没错，我完全同意。我认为 iMessage 所带来的个性化体验，正因为我已经身处其中，感觉它已经是与我紧密相连的东西了。这不会让人觉得是一个额外强加的工作流。

<details><summary>Original English</summary>
>> Yep.

 I

 I

 completely

 agree.

 Um,

 I

 think





the

 the

 personalization

 that

 comes

 with





iMessage

 is

 just

 because

 I

 already

 live





there,

 it

 feels

 like

 it's

 something





that's

 already

 connected

 to

 me.

 It





doesn't

 feel

 like

 an

 additive

 workflow.
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且总体上我也确实只看到两种形态出现：要么是 iMessage，要么是独立的应用程序。我也看到过第三种迹象，其实是一家名为 Sky 的初创公司，他们做了一个类似 iPhone 小组件的东西，

<details><summary>Original English</summary>
>> And

 I

 I

 really

 have

 only

 though

 seen

 by





and

 large

 two

 services

 appear.

 It's





either

 the

 iMessage

 or

 a

 separate





application.

 Um,

 I've

 I've

 seen

 a

 third





um

 signal

 startup

 actually

 Sky.

 They





they

 have

 like

 a

 iPhone

 widget
</details>

>> 他们正试图将其作为一种不同的交互界面引入，这相当有趣。不过甚至就在昨天，对吧，我们看到扎克伯格和 Muse 团队推出了 Muse Charm。是的，那又是一个完全不同的

<details><summary>Original English</summary>
>> that

 they're

 trying

 to

 introduce

 as

 a





different

 surface

 which

 is

 pretty





interesting.

 Um,

 but

 then

 even





yesterday,

 right,

 we

 saw

 Zuckerberg

 and





and

 the

 Muse

 team

 dropped

 uh

 the

 Muse





Charm.

 Yes,

 that's

 now

 an

 entirely





different
</details>

<!-- chunk 3/7 -->

### 硬件形态与环境智能

……用于我们如何与智能体交互的使用场景。你怎么看硬件？

<details><summary>Original English</summary>
uh use case for for how we interact with an agent. What What do you think about hardware?
</details>

>> 我觉得这很有意思。我是说，有一位聪明人曾这么说过：每一个从事硬件研发的人，都认为自己的硬件是某种终极之作。比如吊坠就是终极形态，你知道的，表带就是终极形态。嗯，所以我不认为那是对的。我认为这又将是非常由个人喜好驱动的事情。就像首饰一样，有些人喜欢戴项链，有些人喜欢戴耳环。我认为这种形态的呈现方式，也将是非常因客户而异的。但我认为，拥有某种常伴身边、属于环境智能形态、并能捕捉全天发生的所有上下文、请求、承诺以及约定的东西，是有其价值的。我的意思是，在社会的隐私预期方面，我们可能得共同去探索并解决这个问题。你知道的，你去华盛顿的餐馆，他们会收走你的手机。也许以后他们会收走你的手机和吊坠。嗯，

<details><summary>Original English</summary>
>> I think it's fascinating. I mean, there a smart person said this, which is that every person who's working on a piece of hardware thinks that their hardware is the kind of beall endall. Like the pendant is the ultimate thing, you know, the the watch strap is the ultimate thing. Um, so I don't think that that's right. I think again it's going to be very personal preference driven. You just as jewelry is like some people like to wear necklaces and some people like to wear earrings. And I think the same way this kind of form factor is going to manifest is going to be very customer specific. But I think that there's value in having something that is sort of with you and ambient and can capture all the kind of context and requests and you know promises and commitments and everything that happens through the day. I mean, I think we're going to have to sort of figure it out together in terms of privacy expectations in society. You know, you go to restaurants in Washington and they take away your phone. Maybe they're going to be taking away your phone and your pendant. Um,
</details>

>> 对。

<details><summary>Original English</summary>
>> right.
</details>

>> 但我觉得硬件确实大有可为，我只是很高兴看到我们在那个方向上雄心勃勃。你知道，在经历了初创公司被劝阻从事硬件研发的十年之后，现在我们迎来了很多有趣的全新消费级探索，

<details><summary>Original English</summary>
>> But I think that there's actually something there with hardware and I just like that we're being ambitious in that direction. You know, I think after 10 years of startups being discouraged from working on hardware, now we've got a lot of interesting new consumer efforts,
</details>

>> 对吧？我认为这会超级有意思。我有一个大胆的观点，那就是这款 Muse charm 实际上并不在于试图赢得硬件层面的竞争，而更多在于为 Meta 团队在现实世界中收集数据，涉及现实世界究竟如何运转，因为考虑到它配备了摄像头和多个麦克风，而且它主……我并不觉得它会是一个大众普及的东西。我认为它会被 Twitter 圈子所采用，他们会在到处使用它，而这只会给 Meta 输送极其海量的数据，为扎克伯格未来绘制真实世界的元宇宙提供支持。

<details><summary>Original English</summary>
>> right? I think it's it's going to be super interesting. I have a hot take thesis that this uh Muse charm is actually less about trying to win the hardware game and it's more about data collection in the real world for the meta team in terms of like how the real world actually functions given it has a camera and multiple microphones and it's primar I don't really see it being a mass adoption thing. I think it's going to get adopted by the Twitter bubble and they're going to use it everywhere and it's just going to feed meta with a ridiculous amount of data to fuel Zuckerberg's future metaverse of mapping out the actual world.
</details>

>> 但难道你不觉得他们已经通过眼镜获得了这些吗？

<details><summary>Original English</summary>
>> But don't you think that they already get that from the glasses?
</details>

>> 我认为他们在某种程度上确实得到了，但我不知道是否……我的意思是，如果我说错了请纠正我，但眼镜会一直保持开启状态吗？像这款 charm 那样开启？因为……

<details><summary>Original English</summary>
>> I think they they do to some extent, but I don't know if I mean, correct me if I'm wrong, but I I are the glasses always going to be on in the same way that this charm will be because
</details>

>> 我觉得不会。是的，这是个极好的观点。我认为 charm 的定位更多是，你知道，正如你提到的，它是一个全天候 24/7 的环境陪伴设备，而眼镜则更偏向行动导向。

<details><summary>Original English</summary>
>> I don't think so. Yeah, it's a great point. I I think the charm is meant to be more as, you know, as you mentioned, it's an ambient 247 companion versus the glasses are more actionoriented.
</details>

>> 这将会非常吸引人。我之前觉得，你知道，我得去试一下 VR 的发布。那挺有意思的，但实际上我认为纯音频眼镜可能会成为一匹黑马。

<details><summary>Original English</summary>
>> It's going to be fascinating. I thought the, you know, I've got to try the VR release. That was interesting, but I actually think that the audio only glasses might be a sleeper hit.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 我觉得这其中确实有非常引人注目的东西。我认为人们，你知道，我的意思是，《安德的游戏》中 Jane 的构想完全就是这种全知的纯音频伴侣。而且我不知道，你知道，我认为有一群人喜欢在脸上戴着摄像头，但我觉得其他人可能会意识到这可能会让人感到不舒服，

<details><summary>Original English</summary>
>> I think there's something really compelling to that. I think people, you know, I mean, the vision of sort of Jane from Enders Game was all about this sort of all- knowing audio only companion. And I don't know, you know, I think there's a set of people that love to wear the kind of camera on their face, but I think others may be aware of the fact that it could make people uncomfortable
</details>

>> 而且他们会喜欢感觉自己拥有技术的连接性，而没有任何摄像头带来的社交尴尬。

<details><summary>Original English</summary>
>> and they're going to like feeling like they have the technology connectivity without any of the social awkwardness of the camera.
</details>

### 语音助手与使用场景

>> 音频太不可思议了。我对语音和音频非常看好。ChatGPT voice 昨天推出了他们的 ChatGPT voice 连接器支持，所以你可以连接到像你的 Gmail 和日历这样的工具。

<details><summary>Original English</summary>
>> Audio is incredible. I'm I'm quite bullish on voice and audio. Chatbt voice yesterday dropped their uh chatbt voice to allow connectors in so you can connect to like your Gmail and calendar.
</details>

>> 嗯，我今天早上试用了一下，对我来说，这是我在整个 AI 助手领域的第二个高光神奇时刻。

<details><summary>Original English</summary>
>> Um I played around with it this morning and to me it was my second magic moment of this whole AI assistant space
</details>

>> 真的吗。

<details><summary>Original English</summary>
>> really.
</details>

>> 嗯，我当时骑车去上班，双手抽不出空，但我想把事情给办了，于是我就开始和 ChatGPT voice 说话。我直接开启了一次会话，开始和它聊天。在我 30 分钟骑车上班的整个过程中，它对我的电子邮件进行了分类，嗯，将它们归入不同的标签。

<details><summary>Original English</summary>
>> Um, I was biking to work, hands are busy, I want to get stuff done, and I just start talking to chat GBT voice. I just open up a session, start chatting with it. And throughout my 30-minute bike ride to work, categorized my emails, uh, submitted them to different labels.
</details>

>> 挺好。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 回复了不同的邮件，发出了日历邀请，等我坐到办公桌前，达到了收件箱清零。这简直太震撼了。

<details><summary>Original English</summary>
>> Replied to different emails, sent out calendar invites, got to the desk, inbox zero. It It was It was so electric.
</details>

>> 太不可思议了。所以，这是 ChatGPT voice，不是 Muse，

<details><summary>Original English</summary>
>> It's incred. And so, this is Chat GBT voice, not Muse,
</details>

>> 没错吧？ChatGPT voice。哦，太棒了。好的，我刚才误解你了。我以为你说的是 Muse 语音。我完全赞同。我认为 ChatGPT 嗯……它是基于 GPT live one 模型的。它是全双工语音，而且能看到你所有的消息会话。所以，你可以问它诸如“嘿，我发起的哪三个项目进展如何，我们在什么节点，我被什么卡住了？”这类问题。我认为这是一项非凡的能力，而且是目前无论 Muse 还是 Instinct 都不具备的能力。不过，尽管我认为 Zuck 实际上确实宣布了全双工语音，所以也许它很快就会登陆 Muse。

<details><summary>Original English</summary>
>> correct? Chat GBT voice. Oh, amazing. Okay, I misunderstood you. I thought you'd said muse voice. I totally agree. I think the chat GPT um it's based on the GPT live one model. It's full duplex voice and it can see all your threads. So, you can ask it things like, hey, what are those three projects I started and you know, where are we and what am I blocked on? I think it's an extraordinary capability and it's one that neither, you know, Muse nor Instinct has today. Though, though I think that Zuck actually did announce full duplex voice, so maybe it's coming to Muse soon.
</details>

>> 必然的，这肯定会来。但我确实认为，对于普通消费者而言，助手在你最忙碌的时候才是最有用的，对吧？人们又不会坐在沙发上，把所有时间都花在用助手做事情上。它在你园艺、烹饪或者在忙于手中事务、无法实际与界面交互时最有用。而且你知道，这又回到了那种隐形助手的概念，你只要开口说话、交代一句，它就会在后台去运行并处理事情。

<details><summary>Original English</summary>
>> Definitely, it's coming. But I I I do think that for the general consumer, an assistant is most helpful when you are most occupied, right? It's not like you're going to be sitting down on your couch and spending all of your time using your assistant to do stuff. It's most helpful when you're gardening or cooking or doing things where your hands are busy and you can't actually engage with an interface. And you know, it it goes back to that like invisible assistant where you can just talk and say something and it just goes and runs and does something in the background.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且我认为，那些整天泡在网上、离不开手机、坐在电脑前的科技圈子，与普通大众相比，是完全不同的环境。

<details><summary>Original English</summary>
>> And I I think that the tech bubble that is chronically online and on their phone and in front of a computer is a very different environment than the general population.
</details>

>> 是的。嗯，所以我非常兴奋想看看这到底如何实现大众普及，以及普通消费者会如何看待助手，当它真正成为……它会成为一个为他们解决实际痛点的助手吗？他们会在遇到真正非常痛苦、因为自己不想做的事情时去使用它。比如你收到了一张交通罚单，你想要……你必须去交那张罚单。太好了，拍张照片，让你的智能体去替你处理。

<details><summary>Original English</summary>
>> Yeah. Um, and so I'm really excited to see how does this actually hit mass adoption and how does like the average consumer think about an assistant when it's actually like is it going to be an assistant that solves real pain points for them where they're going to use it when something is really really painful because they don't want to do it. Like you get a traffic ticket, you want you have to go pay for that traffic ticket. Great. Just take a picture and let your agent go do it for you.
</details>

>> 嗯，

<details><summary>Original English</summary>
>> Um,
</details>

>> 接下来会很有看头。

<details><summary>Original English</summary>
>> it's going to be interesting to see.
</details>

### 群聊与多智能体协作

>> 那么我接下来想和你聊的是社交方面。嗯，你知道，我们大体上讨论了多人协作。你知道，我们谈到过 iMessage 属于某种具有优势地位的阵地，这实际上也是 Instinct 比较酷的地方之一。然而，根据我的经验，构建被添加到群聊中的智能体，不知怎的会让人感到具有侵入性，或者说感觉它削弱了社交资本。

<details><summary>Original English</summary>
>> So the next thing I wanted to talk to you about was social. Um, you know, we talked in multiplayer generally. You know, we talked about how iMessage is this sort of privileged place to be, which is actually one cool things about um Instinct. However, in my experience, building agents that you add to group chats somehow feels intrusive or like it diminishes social capital.
</details>

>> 你有见过什么行之有效的方法吗？对于这些智能体如何进入一种多人协作状态，你有什么样的构想？

<details><summary>Original English</summary>
>> Have you seen anything that works well? And what are your kind of theories for how these agents get um get to a multiplayer state?
</details>

>> 很多人都尝试过。我认为我见到了三种不同的路径。第一种路径是你传统的做法：把它加进群聊，它就作为群聊里的伴侣存在。我见过的第二种路径是 Instinct 的做法，即拥有一个智能体网络，你在其中邀请另一个智能体，它们在后台代表你进行交流，并且它们会向你同步最新进展。我见过的第三种方式——我认为这是最有趣的——是一款由 Shane Mack 推出的名为 Doc 的新产品。嗯，我想也是一家 A16Z 投的公司，嗯，XMTP，他们的做法更像 Granola。也就是你把一个智能体加到群聊里，但那个智能体是静默的，它纯粹是一个倾听者。它记录人们在聊些什么，如果产生了一个行动项，它会单独在另一个独立的消息会话里给该成员发送提醒。然后如果你想看大家都在聊些什么，你可以进入实际的文档，查看它记下的笔记。通过这种方式，它又更像是一个隐形智能体。你感受不到它的存在。它默默完成了所有你希望多人功能具备的行政事务类工作，而如果它需要确认行动项，也不会打扰到群里的大多数人。非常非常酷的思路。

<details><summary>Original English</summary>
>> A lot of people have tried it. I think I've seen three different approaches. Uh the first approach is your traditional add it to a group chat and it's just like the group chat in in your companion. The second approach I've seen is how instinct did it where you have like an agent network where you invite another agent and they're talking behind the scenes on your behalf and they'll update you as to what's going on. The third way that I've seen it which I think is the most interesting uh it's a new one called Doc uh by this guy Shane Mack. um I think also an A16Z uh A16Z company um XMTP and they are approaching it more like granola. So you add an agent to a group chat but that agent is silent and it's purely a listener. It's taking notes on what people are talking about and if it has an action item it independently will ping the person in a separate message thread. And then if you want to see what people are talking about you can go into the actual docs and see what it's taken notes on. In that way, it's more of again, it's your invisible agent. You don't know it's there. It's doing all the admin work that you would want out of a multiplayer function, and if it needs action items, it doesn't bother the majority of the group. Really, really cool approach.
</details>

>> 我得去试试看。我很喜欢这个。而且我很喜欢它已经是 A16Z 投资的公司了。当然。嗯，你知道，我对这个问题的看法是，如果你看一下现状，OBO 的 Near 曾说过这一点，而且你知道，我认为他是对的，那就是模型在编程等可验证领域所取得的进展当然是指数量级的，但它们在单纯的行文质量、乃至类似就诊态度那样的表达互动层面所取得的进展，可能已经陷入了停滞，甚至可能还在变差。所以我其实认为，以目前的模型现状，再加上或许我们自身的期望，你……

<details><summary>Original English</summary>
>> I've got to try that out. I love that. And I love that it's an A16Z company already. Of course. Um you know my theory on this if you look at this and Near from OBO said it and he you know I think he's right which is the progress the models are making on verifiable domains like coding are of course exponential but the progress they've made on just pros quality and even like bedside manner has maybe plateaued or maybe is even getting worse. So I actually think that with the the models as they are today and perhaps with our own expectations you
</details>

<!-- chunk 4/7 -->

### 智能体在社交场景与实用场景中的角色

你知道，就这些社交动态而言，我不认为智能体有很多方式可以去做出贡献并增强群体的这种社交连接。相反，我认为非常偏实用型的智能体——你知道，我一直在做的一个实验是添加它……我是一个收藏家，你知道，我收藏唱片和一堆其他东西。把一个智能体加到我和其他收藏家朋友聊天的群里，试着给各自的收藏和品味建档。虽然我还没有完全做成功，但至少感觉这确实能给群组带来增益，而不是像一个低情商机器人在我们不想让它插嘴的时候喋喋不休。

<details><summary>Original English</summary>
know in terms of these social dynamics I don't think there's a lot of ways that the agents can contribute and enhance the sort of social connectivity of the group you know conversely I think agents that are very utilitarian you know one of the experiments I've been doing is adding it I'm a collector you know I collect records and a bunch of other things adding an agent to the chats where I talk to my fellow collector friends and trying to catalog our respective collections and our tastes. And I haven't quite hit it, but it at least feels like it's something that's genuinely additive to the group rather than, you know, this sort of low EQ robot that's chattering when we don't want it to.
</details>

>> 是的。完全同意。你应该试一下 Doc。我觉得你会对它相当着迷。

<details><summary>Original English</summary>
>> Yep. Totally. You'll you should you should give uh you should give Doc a try. I think I think you're going to be quite fascinated by it.
</details>

>> 我会的。好的。好的。我这周听到的另一个有趣观点是，你知道，即时通讯本身在某些方面并不适合这种智能体交互，因为在即时通讯中就好像有人拿着麦克风，而把麦克风交给智能体会让人觉得不舒服。然而，如果你看某些可能更接近 Discord 甚至传统网页论坛的东西，

<details><summary>Original English</summary>
>> I will. Yeah. Yeah. The other interesting take that I heard this week was that, you know, something about messaging in particular is doesn't lend itself to these agent interactions because in messaging it's as if somebody has the mic and it feels uncomfortable to give the agent the mic. Whereas, if you look at something like maybe closer to a Discord or even a traditional web form,
</details>

>> 那其实是智能体可以发帖、你可以像 Reddit 那样去互动或不互动的地方，但不知出于什么原因，它感觉不如群聊那么具有侵入性。我不知道。

<details><summary>Original English</summary>
>> that's actually something where an agent can make a post and you can either engage with the post or not, Reddit style, but for some reason it feels less intrusive than group chat. I don't know.
</details>

### 智能体人格设计与拟人化界限

>> 是的。挺有意思。这几乎就像我们试图把这些智能体拟人化得有点过头了。没错。就像……我认为这引出了另一个组成部分，即如果你看智能体形象的实际设计，我看到有些公司让它试图成为一个 AI 生成的人类，然后你又有像 Muse 这样的其他公司，它是这么一个可爱的雪人。

<details><summary>Original English</summary>
>> Yeah. Interest. It's almost It's almost as if we're trying to humanize these agents a little too much. That's right. Like and I think that comes to another component where if you look at the actual design of the character of the agent, I see some companies that have it try to be like an AI generated human and then you have other companies like Muse that it's this like adorable yeti.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 而且我认为看到全世界如何爱上这个雪人真的很有意思。它就是太萌太可爱了。

<details><summary>Original English</summary>
>> And I think it's really interesting to see how the world has fallen in love with this yeti. It's just so cute and adorable.
</details>

>> 是的。而且就你提到的 AI 生成的人类而言，我认为人们会感到有点不适，在你的个人空间里把这些助手拟人化到这种程度感觉很怪异。

<details><summary>Original English</summary>
>> Yes. and the like AI generated human to your point like I think people feel a little uncomfortable like it feels weird to humanize these assistants so much
</details>

>> 嗯，就像在你的个人空间里。

<details><summary>Original English</summary>
>> um in your like in your personal space.
</details>

>> 所以我想问你的一个相关问题是，你认为市场会按性格或原型来细分吗？你知道，我们在散步时聊了一点这个，但你知道，有些人更喜欢严肃、生硬、有权威感的医生，有些人更喜欢热情友好、感觉像同龄同辈一样的医生。那只是两种不同原型的医生。显然，没有医生能同时具备这两种特质。它们是对立的。你认为智能体也会是这样吗？

<details><summary>Original English</summary>
>> So one related question I wanted to ask you is do you think that the market segments by personality or archetype? You know, we were chatting a bit about this on our walk, but you know, some people prefer a kind of serious, gruff, authoritative doctor, and some people prefer a, you know, warm and friendly, you know, sort of a doctor that feels like a peer. And those are just two different archetypes of doctors. Obviously, no doctor is both of those things. They're in opposition. Do you think the same will be true of agents?
</details>

>> 我想每个人肯定偏好不同的沟通风格。

<details><summary>Original English</summary>
>> I think everyone for sure prefers a different style of communication.
</details>

>> Poke 一上来就很猛，对吧？Poke 的性格非常鲜明，而且我有不少朋友都说，“我拒绝给 Poke 任何个人信息，因为它太爱耍贫嘴了，跟它对话其实让我很不舒服。”

<details><summary>Original English</summary>
>> Poke came out of the gates hot, right? The personality of Poke is is quite distinctive and it's something that I have a lot of friends who are like, I refuse to give Poke any of my personal information because it's so sassy and it actually makes me uncomfortable to engage in a conversation with it.
</details>

>> 但我不认为性格真正构成一道有防御力的护城河，因为它太容易配置了。就像你作为一个消费者，你给你的智能体发短信，你说你希望它以某种方式回应，它只要把这个保存到它的记忆或者它的灵魂文件里，然后你就搞定了，它就改变了。嗯，我认为我们最终会达到这样一种境地：无论哪款通用智能体最终成为领跑者，它都将是高度可配置的，每个人都可以按照让自己最舒服的方式去调整智能体对自己说话的风格。

<details><summary>Original English</summary>
>> But I don't think personality is really a defensible mode because it's it's quite easy to configure. It's like you as a consumer, you text your agent, you say that you would prefer it responds in a certain way, it just saves that to its memory or its soul file and then you're good to go and it changes. Um, I think we'll get to a place where whatever general agent ends up being the leader that it'll be quite configurable and each person can kind of tailor the agent to speak to them how, you know, however makes them most comfortable.
</details>

### 主动性与权限边界

>> 这很有意思，我也同意你的看法，但也许让我试着给不仅是性格、而且是一种……

<details><summary>Original English</summary>
>> So, that's interesting and I agree with you, but maybe let me try the steel man here for not just personality but kind of um,
</details>

>> 你知道，一时找不到更好的词，姑且称之为特质做个最强辩护（steel man），其作为一个定义性特征的例子就是自作主张。你知道，我们谈过一点这个，有些工作你希望智能体高度擅作主张，

<details><summary>Original English</summary>
>> you know, constitution for lack of a better word, which is an example of a kind of defining characteristic is presumptuousness. You know, we've talked a little bit about this and there are some jobs for which you want the agent to be highly presumptuous
</details>

>> 只要它经常能把事情办成，你宁愿它有 10% 的时间犯错。而还有其他风格的智能体，比如我们的财务智能体，你可能希望它高度谨慎。所以我有点好奇，这些我们现在称之为性格的东西，是否开始向下渗透到能力层面，以及你知道，在面对模糊情境时它如何做最终抉择，也许围绕这一点会更有防御壁垒。

<details><summary>Original English</summary>
>> and you'd rather have it make mistakes 10% of the time as long as it often gets things done. And there are other styles of agents like our finance agent perhaps where you want it to be highly cautious. So I sort of wonder if some of these things which we're now describing as personality start to push down into sort of capabilities and you know how it tie breaks in a position of ambiguity and perhaps there's a bit more defensibility around that.
</details>

>> 我认为围绕主动性存在巨大的防御壁垒。我认为这实际上将是把赢家与大部队区分开来的关键。能够最主动的智能体，能够充当隐形助手并在你甚至没有开口要求的情况下就开始代你办事的智能体。我认为到目前为止我们见过的最好的这种噱头式的酷炫“顿悟时刻”，就是代你办理航班值机。

<details><summary>Original English</summary>
>> I think there is massive defensibility around proactivity. I think that's actually going to be something that separates the winner from the you know the meat of the pack. the agent that can be most proactive, that can serve as an an invisible assistant and start doing things on your behalf without you even asking. I I think the best like gimmick cool aha moment that we've seen so far is checking into your flight for you.
</details>

>> 嗯，不过就你的观点而言，

<details><summary>Original English</summary>
>> Um to your point though,
</details>

>> 它确实归结为两类。有些工作流中，

<details><summary>Original English</summary>
>> it really does come down to two categories. There's some workflows where
</details>

>> 你希望保持控制权，并且你并不真正希望智能体过于主动地代表你行事。是的。

<details><summary>Original English</summary>
>> you want to retain control and you don't really want an agent to be acting too proactive on your behalf. Yeah.
</details>

>> 而且我认为那些是需要在你这边做出行动改变的工作流。所以也许这就像智能体发现你使用的保险收费过高，并认为你应该更换保险。

<details><summary>Original English</summary>
>> And I think those are workflows that require a a change in action uh on your side. So maybe that is an agent identifies that the insurance you're using is charging too much money and thinks you should switch insurances.
</details>

>> 是的，

<details><summary>Original English</summary>
>> Yeah,
</details>

>> 它可能应该在实际做出更换之前征得你的许可，因为那是代表你采取的直接影响到你的行动。

<details><summary>Original English</summary>
>> it should probably get your permission before it actually makes that switch because that's that's a direct action on your behalf that impacts you.
</details>

>> 然而，像“嘿，我帮你起草了这封邮件”或“我代表你拿到了机票代金券”这种主动性，

<details><summary>Original English</summary>
>> However, the proactiveness of, hey, I drafted this email for you or I got a flight credit on your behalf,
</details>

>> 你这边不需要采取任何行动。这只是在帮你省钱，帮你省时间。嗯，所以我认为看看我们究竟如何去对这些类型的行为进行分类和拆解会很有趣，但这将是一条非常微妙的界线，因为如果你越界一次，我认为你就会立刻失去用户的全部信任。

<details><summary>Original English</summary>
>> there's no action needed on your side. It's just saving you money. It's saving you time. Um, so I think it'll be interesting to see like how do we really categorize and break down those those type of behaviors, but it will be a very fine line because if you if you cross that line once, I think you immediately lose all trust with your user.
</details>

>> 是的，这会【嗤笑】很有趣。你知道，我们在内部开玩笑说，就好像我们离智能体给某人发消息说“我注意到你对她没那么上心，所以我就替你跟她分手了”这种事情只有几天的时间了。

<details><summary>Original English</summary>
>> Yeah, it'll [snorts] be interesting. You know, we were joking internally like we're days away from an agent messaging someone saying, "I noticed you weren't that into her, so I went ahead and broke up with her for you."
</details>

>> 没错。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 你知道，就像看到过那个一样。这迟早会发生的，兄弟。但是，你知道，我认为很多魔力正是来自于这种擅作主张。而且我认为，如果在 X 上看不到人们发帖说“天哪，智能体做了这个，智能体做了那个”，那可能表明智能体在这个方向上的推进还不够强。就像，我认为会有……而且其实我很好奇想知道，首先，你知道，我有点怀疑 Bongchang 那个帖子到底是不是真的。嗯，对于不知道的人，有个人发推说 Instinct 帮他办理航班值机，把他的中间名幻觉成了 Bong Chang，导致他没能登上航班。所以，我不确定那只是在网上发帖博眼球，还是真的发生了。嗯，但我很好奇想知道那个人是否还在使用 Instinct。我猜他们还在用。

<details><summary>Original English</summary>
>> You know, so like saw that one. It's going to happen, man. But, you know, I think a lot of the magic comes from the presumptuousness. And I think that if you didn't see people posting on X about, oh, the agent did this, the agent did that, it would probably be a sign that the agents are not pushing hard enough in this direction. Like, I think there's going and actually I'd be curious to know, first of all, I'm, you know, a little suspicious of whether the the Bongchang post was even real. Um, and for folks who don't know, there's there's a person who tweeted that Instinct checked him into a flight and hallucinated his middle name um as Bong Chang and he wasn't able to get on the flight. So, I'm not sure if that's just posting or if that really happened. Um, but I I'd be curious to know if that person is still using instinct. I'm guessing they are.
</details>

>> 我推测也是，纯粹是因为那个帖子带来的流量，他们【笑声】可能指望着更多

<details><summary>Original English</summary>
>> I would assume so purely given the traction of that post that they're [laughter] probably feeding for more more
</details>

>> 别无他求，至少是个搞笑热门推文的素材来源。

<details><summary>Original English</summary>
>> nothing else. At least just a source of comedic popular tweets.
</details>

### 从 OpenClaw 到消费级智能体的演进

>> 对。对。也许谈谈……你知道，感觉发生的一件大事是，open claw 时期开发出来的那种原语，现在已经以大众市场消费者能够……你知道，理解和欣赏的方式被产品化了。

<details><summary>Original English</summary>
>> Right. Right. maybe talk, you know, it feels like one of the big things that's happened is that the kind of primitives that were developed during the open claw period have now been productized in a way that the mass market consumer can sort of you know digest and appreciate.
</details>

>> 你觉得有没有……而且还有你提到过好几次的 Poke，Poke 确实很出色。我认为他们做了一件极其聪明的工作，我认为如果他们晚六个月起步，他们最终可能会成为赢家。我认为那里的团队真的非常非常有才华，而且我很好奇想看看他们接下来实际上为我们准备了什么，因为我确信既然他们现在成了 Cognition 的一部分，他们并没有停止在这方面的研发。我非常好奇想知道，你在 openclaw 时代注意到的那些能力或经验教训，是否有你认为能告诉我们消费级智能体下一步走向的。

<details><summary>Original English</summary>
>> Do you think there and also Poke which you had mentioned a couple of times like Poke was extraordinary. I think they did a super clever job and I think if they had started six months later they might have ended up being the winner. I think the team is is really really talented there and I'll be curious to see what they actually have in store for us next because I'm sure that you now that they're a part of cognition they haven't stopped working on this. I'd be very curious to know if there are capabilities or lessons from the openclaw era that you notice that you think are going to tell us what's coming next in consumer agents.
</details>

>> 眼下说实话，我认为消费级智能体实际上就只是 openclaw 的翻版，只是经过了预先配置。嗯，我没看到个人助手领域有什么很大的进展

<details><summary>Original English</summary>
>> Right now I honestly see the consumer agent is is literally just a replication of openclaw but it's just preconfigured. Um, I don't see much happening in the personal assistant space
</details>

<!-- chunk 5/7 -->

是你用 OpenClaw 或 Hermes 做不到的。

<details><summary>Original English</summary>that you can't do with OpenClaw or Hermes.</details>

>> 事实就是你不需要去配置一切，也不会每隔七个小时就弹出一堆错误提示，而且它确实非常好用。它的界面很简单。嗯，所以我们拭目以待吧。我认为这个领域的方向会继续朝着主动性发展。我认为这个领域的方向会继续看到更多的超细分化，我觉得这恰好切合了你的观点，也就是你在关于狭窄初创公司（narrow startups）的论点中的内容，随着我们看到越来越多这类的长尾机会，这个领域会呈现出怎样的面貌，无论它是……

<details><summary>Original English</summary>>> It's just a matter of fact that you don't have to configure everything and you're not getting error messages popping up every seven hours and it's it's really easy to use. It's an easy interface. Um, so we'll we'll see what happens. I I think the direction of the space will continue to move towards proactivity. I think the direction of the space will continue to see more hyper specialization which which I think goes to your point in your thesis of of uh narrow startups and how does the space look as we see more of these longtail opportunities whether it is</details>

>> 你知道，与其做一个通用的助手，不如把所有的精力都放在让我的助手成为针对有三岁以下孩子的单身母亲的专家。

<details><summary>Original English</summary>>> you know instead of being a generalist I'm going to spend all of my time focusing my assistant to be an expert for single mothers with children under the age of three.</details>

>> 是的。

<details><summary>Original English</summary>>> Yeah.</details>

>> 而且它对一位母亲如何度过日常生活、儿童发育了如指掌，感觉就像那个助手完全能读懂她们的心思一样。而那也许可以作为一个插件接入到通用型助手中，但既然这是你的论点，我很好奇。嗯，你是怎么考虑的？你知道，我想首先……

<details><summary>Original English</summary>>> And it knows everything about how a mother operates her day-to-day life, child development, where it literally feels like that assistant is reading their mind. And that could maybe be a plugin into the generalist, but you know, I'm curious with with this being your thesis. Um, how how do you think about, you know, I guess first</details>

### 狭窄初创公司与细分化

>> 先跟我们更深入地分享一下，对你来说狭窄初创公司究竟是什么，以及你认为它会如何发展？是的，关于狭窄初创公司的理论是，现在你可以打造出极其宏大、而且对极少数人来说极其有价值的软件。而且我们已经有了人们愿意每月支付200美元、250美元、300美元的先例。所以你完全可以凭借几万名用户打造出一项年化营收达一亿美元的业务，这在过去是绝无仅有的。很大一部分还在于，这些能力可以细分专业化到令人惊叹的程度。然后当我们思考你刚才所讨论的内容时，我完全同意你的看法。我认为将会出现这种比较优势。我认为这将会是品味与专有知识的结合。你知道，可能就像你有一位遵循某种特定接生风格的导乐（doula）一样，你可能也会有一个真正认同某种思想流派、某种风格、或者甚至是一套尚未被充分理解的经验法则的个人智能体（personal agent）。然后你会雇佣那个智能体来为你提供那种服务。再就是专有数据，你知道，你提到过可能有一个专门面向纽约市的个人智能体。

<details><summary>Original English</summary>>> give us some more insight on what narrow startups are to you and and how do you see that playing? Yeah, the theory with narrow startups is that, you know, you can now build software that's incredibly ambitious um and incredibly valuable for a very small number of people. And we have this precedent of people paying, you know, 200, 250, $300 a month. So you can build, you know, a hundred million dollar run rate business with tens of thousands of people, which has never really existed in the past. A lot of it also is that the capabilities can be specialized to such an astounding degree. And then as we think about what you're discussing, I totally agree with you. I think there will be this kind of comparative advantage. I think it's going to be a combination of taste and proprietary knowledge. You know, there may be just as you, you know, you have a doula that may subscribe to a certain sort of style of, you know, helping women give birth, you may have a personal agent that actually subscribes to a certain school of thought or style or, you know, even a set of lessons that aren't well understood. and you're going to hire that agent to sort of provide that service to you. And then proprietary data, you know, you'd mentioned potentially having a personal agent just for New York City.</details>

>> 就像我认为，就像可能有一位拥有难以复制的顶级品味的礼宾人员，他知道所有你会喜欢的最佳去处，而针对另外十二种不同的人群或人群原型，可能还会有另外十来个礼宾人员。我确实认为，将会发生这种主观和客观层面的专门化。

<details><summary>Original English</summary>>> Like I think, you know, just as there might be a concierge that's got A+ taste that's hard to replicate that knows all the best spots that you're going to love and there may be another dozen for, you know, another dozen different people or archetypes of people. I do think that there'll be this sort of subjective and objective specialization that happens.</details>

### 助手与智能体的区别

>> 这后续的发展会很有意思。嗯，我也很好奇你的视角，甚至从我们在这里的对话中就能注意到。是的。

<details><summary>Original English</summary>>> It's it's going to be interesting to follow. Um, I'm also curious from your for your lens even in just noticing our conversation here. Yeah.</details>

>> 我们在助手（assistant）和智能体（agent）之间混着用，

<details><summary>Original English</summary>>> We interchange between assistant and agent</details>

>> 这也是我在 Twitter 上一直看到大家在讨论的话题。

<details><summary>Original English</summary>>> and it's been a constant conversation I see people talking about on Twitter.</details>

>> 是的。

<details><summary>Original English</summary>>> Yeah.</details>

>> 这个生态系统的未来究竟会是一个个人助手，还是一个个人智能体？

<details><summary>Original English</summary>>> Is the future of this ecosystem is it going to be a personal assistant or a personal agent?</details>

>> 是的。

<details><summary>Original English</summary>>> Yeah.</details>

>> 对你来说，这两者意味着什么？

<details><summary>Original English</summary>>> And what do those mean to you?</details>

>> 噢，老兄，这问得太好了。我的意思是，对我来说，助手比智能体低一级。嗯，你知道，对我而言，智能体是一个角色，你可以想象它们是某个社交圈子里平起平坐的伙伴，

<details><summary>Original English</summary>>> Oh, that's such a great question, man. I mean, to me, assistant is a sort of lesser form than agent. Um, you know, for me, an agent is somebody, you could imagine them being a peer in a social group,</details>

>> 你知道，也许我们需要一个比智能体更好的词。但是助手从定义上讲只能做你要求它做的事情，它只能协助你去完成你指示它做的事情。

<details><summary>Original English</summary>>> you know, and maybe we need a better word than agent. But an assistant can only sort of definitionally do what it what you ask it to do, it can assist you in doing something that you've directed it to do.</details>

>> 而智能体拥有自主能动性（agency），能够直接在世界上促成好事发生。而且这也许有点类似于……

<details><summary>Original English</summary>>> While while an agent has agency um, and can just make good things happen in the world. And and maybe this parallels a little bit, you know, the sort of</details>

>> 企业中的智能体与 AI，它们一开始有点像实习生，通过完成工作以及智能水平的提升，它们得以晋升，在企业中承担更高层级的工作。那么，对于一个助手以及后来的智能体来说，在消费者的生活中获得晋升以承担更……意味着什么？

<details><summary>Original English</summary>>> agents and AI in the enterprise where they've sort of started as interns and through, you know, doing work and improved intelligence, they're able to get promoted into doing higher order forms of work in the enterprise. Like what does it mean for an assistant and later an agent to be promoted in the consumer's life to do more</details>

>> 更专业、更精细的工作？

<details><summary>Original English</summary>>> specialized and delicate work?</details>

>> 我非常赞同。我也非常好奇这在人类的社交层面上可能会产生什么样的影响，比如，“智能体”这个词是否能让我们……你知道，不把 AI 过于人格化；而“助手”是否给这种体验增添了太多人性色彩，这会不会让社会感到不适应？嗯，看到人们将如何……会很有意思。

<details><summary>Original English</summary>>> I'm I'm super aligned. I'm I'm also very interested what ramifications it might have in just like the social layer of humanity where you know does the word agent allow us to you know not personify uh AI enough you know is is assistant does it add too much human to the experience and and does that make society uncomfortable um and it'll be interesting to see like how the</details>

>> 我们身处不同的信息茧房中，你的环境更偏向于圈子内部，你在旧金山，所以你在全球的科技中心。嗯，我会说纽约比旧金山稍微滞后一点，然后世界其他地方在随后跟进。因此，看看人们实际如何看待这个领域的术语表达，将会很有意思。

<details><summary>Original English</summary>>> we're in bubbles you're in a more bubble you're SF so you're in the tech hub of of the world. Um I would say New York is a little behind SF and then you know the rest of the world catches up after. So it'll it'll be interesting to see how people actually think about uh the vernacular of the space.</details>

>> 我不知道这算不算圈子。我只觉得这就是……这就像未来，你知道，这就像我们正处在近未来中。嗯……

<details><summary>Original English</summary>>> I don't know if it's a bubble. I just think it's like it's like the future you know it's like uh you know we're in the near future. Um</details>

>> 是的。

<details><summary>Original English</summary>>> yeah.</details>

>> 是的。我不知道。我其实觉得它也可以增进、改善许多社交互动动态。嗯，因为你开始思考……

<details><summary>Original English</summary>>> Yeah. I don't know. I actually think that it could increase a improve a lot of social dynamics as well. Um because you start to think about</details>

>> 将智能体视为非人类。它可以提供一层社交间接性，你知道，所以可能有些话由我直接对你说会有点尴尬，或者群体中正在出现一种令人不适的社交动态。而通过一个设计非常巧妙的智能体，我认为智能体可以，你知道，帮助去……我不知道是提供反馈，还是以一种感觉不带情绪化的方式来梳理冲突，因为你知道……

<details><summary>Original English</summary>>> the agent as a non-human. It can provide a layer of social indirection, you know, so there might be something that's sort of awkward for me to say to you or an uncomfortable social dynamic that's occurring in a group. And with a very carefully designed agent, I think the agent can you know help to I don't know whether it's provide feedback or sort of organize a conflict in a way that feels non-emotional because you know that</details>

>> 就像冲突的仲裁者一样。

<details><summary>Original English</summary>>> like an arbiter of confrontation</details>

>> 潜在地是这样。是的。是的。是的。不，我……你知道，我并不是在倡导一种更加被动攻击型的社交系统，但我确实觉得这很有意思：它们可以作为社交间接性的一种来源和落脚点，如果这说得通的话。

<details><summary>Original English</summary>>> potentially. Yeah. Yeah. Yeah. No, I you know I'm not advocating for a more passive aggressive sort of social system, but I do think it's interesting that they can be a sort of source and a destination for social indirection if that makes sense.</details>

### 五年后的未来图景

>> 没错。没错。而且我认为它将在世界上产生许多极其积极的影响。如果你展望五年后的未来，你认为 AI 会带来怎样的影响？

<details><summary>Original English</summary>>> Right. Right. And I think that it will have a lot of like significantly positive influences in the world. How do you see AI impacting right if we look 5 years down the line?</details>

>> 是的。

<details><summary>Original English</summary>>> Yeah.</details>

>> 这些智能体、这些助手究竟会把我们带向何方？它们如何让我们成为更幸福的人类？

<details><summary>Original English</summary>>> Where do these agents where do these assistants actually take us? How do they make us happier human beings?</details>

>> 问得太好了，老兄。我的意思是，我确实认为那些才是我们归根结底真正追寻的问题。你知道，我们谈到了生产力，我们谈到了财务和健康。有很多琐碎的事情。你知道，我昨天查过这个数据，这个国家每年有150万人因酒后驾车（DUI）被捕。嗯，看，我可以……那背后可能意味着沉重的行政负担。而那些人当中又有多少人请得起律师呢？所以我确实认为普通消费者身上几乎承受着这种官僚事务上的压力。因此我认为第一步是，我们如何某种程度上减轻那种官僚压力，让人们在财务上得到优化、在健康上得到优化，并让他们获得……让他们拥有与富人可能拥有的同等资源，无论是一位律师还是某种家族办公室。

<details><summary>Original English</summary>>> It's a great question, man. I mean, I do think that those are the problems that we're really after at the root of things. You know, we talked about productivity. We talked about finances and health. There's a lot of mundane things. You know, I was looking this up yesterday, but 1.5 million people a year in this country get a DUI. Um, and look, like I can the amount of administrative burden that's probably implied by that. And how many of those people have access to attorneys? And so I do think there's almost this sort of bureaucratic pressure that's applied to the average consumer. So I think step one is how do we sort of relieve that bureaucratic pressure and have people, you know, be financially optimized, have their health be optimized and have them access have that have them have the same access to whether it's an attorney or a kind of family office that somebody who's wealthy might have.</details>

>> 然后我认为更大的问题是，你知道，我从小听我母亲说，得到你想要的东西最难的部分就是弄清楚你想要什么。那就是——我们大家真正追求的究竟是什么？嗯，这些助手能以什么方式来与我们互动？而且我认为这并不像设定目标那么简单。我都不知道究竟有多少人有明确的目标。我认为很大程度上人们只是在试图弄清自己是谁，并成长为最好、最真实的自己。而我们自身的自我发展、我们在世上的主观体验以及这些机器之间的这种相互作用，对我们来说可能是一个非常美好的未来。完全是这样。我看到了这样一个未来，我设想的世界里，我未来的孩子们会看着当下一代人走在街上时的老视频，你知道，脖子低垂着盯着手机。

<details><summary>Original English</summary>>> Then I think the bigger question, you know, I grew up with my mother saying the hardest part about getting what you want is knowing what you want. is like what are we all truly after? Um and what are the ways that these assistants can sort of engage us? And I don't think it's as simplistic as just goals. I don't know how many people even have goals. I think a lot of it is people are just trying to you know find out who they are and turn into the best most authentic versions of themsel. And this kind of interplay between our own self-development and our subjective experience in the world and these machines could be a very beautiful future for us. Totally. I see this future where I envision this world where my future kids are going to be looking at old videos of the current generation walking down the street, you know, next crane down staring at your phone.</details>

>> “你们在做什么？你们在干什么？外面是一个如此美好的世界。你们为什么要把所有的时间都花在盯着屏幕上？”

<details><summary>Original English</summary>>> What are you What are you doing? Like it is a beautiful world out there. Like why are you spending all of your time staring at a screen?</details>

>> 嗯，因为你知道，希望它能让我们把其中的许多事情自动化。这样，作为父母，你实际上可以花更多的时间陪伴孩子。作为二十多岁的年轻人，你实际上可以花更多的时间与朋友交谈。

<details><summary>Original English</summary>>> Um because in you know hopefully it's going to allow us to automate so many of those things. So, as a parent, you can actually spend more time with your kids. As an adult in your 20s, you can actually spend more time talking to friends.</details>

<!-- chunk 6/7 -->

>> 而且我很……我很真的很好奇想看看，它到底会在诸多方面怎样让生活变得更好，减少那些你……

<details><summary>Original English</summary>

>> And

 it's

 I'm

 I'm

 really

 curious

 to

 see





how

 it

 will

 just

 change

 life

 for

 the





better

 in

 so

 many

 ways

 of

 reducing

 the





things

 that
</details>

>> 你真的非常讨厌去做的事情，但又像是生活中的琐事杂务。

<details><summary>Original English</summary>

>> you

 just

 really

 hate

 to

 do,

 but

 it's





like

 the

 life

 admin

 work.
</details>

>> 对，没错。我的意思是，这也是为什么我认为，你知道的，很多时候代码 Agent 并没有在和人类程序员竞争，因为它们在做的事情是没有任何人类程序员在做的。你知道，不管那是构建这种离谱的业余副项目。我一直在做，嗯，一个你可以走进去的虚拟唱片店。稍后我会把链接发给你。它棒极了。像在五年、七年或者 10 年前，我绝不可能雇一个程序员去开发那个东西。我也绝不可能花上自己人生中的整整一年去完成它。所以所有这类东西，都是那种如果不是这样就绝不可能发生的事情。

<details><summary>Original English</summary>

>> Yeah,

 that's

 right.

 I

 mean,

 that's

 also





why

 I

 think

 that,

 you

 know,

 so

 many





times

 coding

 agents

 are

 not

 competing





with

 human

 programmers

 because

 they're





doing

 things

 that

 no

 human

 programmers





are

 doing.

 you

 know,

 whether

 it's





building

 this

 ridiculous

 side

 project.





I've

 been

 building

 um

 a

 virtual

 record





shop

 that

 you

 can

 walk

 into.

 I'll

 send





you

 a

 link

 to

 it

 after.

 It's

 awesome.





Like

 I

 would

 never

 hire

 a

 programmer

 to





work

 on

 that

 five

 or

 seven

 10

 years

 ago.





I

 would

 have

 never

 spent

 the

 year

 of

 my





life

 that

 it

 would

 have

 taken.

 So

 all

 of





this

 stuff

 is

 this

 sort

 of

 things

 that





never

 would

 have

 happened
</details>

>> 否则就不会发生。嗯，而且我认为这项技术在我们的生活中有许多版本，我们只是得以去探索那些我们无论如何都绝不会去探索的事物。这不是为了削减成本。这是为了可能性的拓展。嗯，

<details><summary>Original English</summary>

>> otherwise.

 Um

 and

 I

 think

 there's

 a

 lot





of

 versions

 of

 this

 technology

 in

 our





life

 where

 we're

 just

 getting

 to

 explore





things

 we

 never

 would

 have

 explored





anyway.

 It's

 not

 about

 cost

 reduction.





It's

 about

 possibility

 expansion.

 Um,
</details>

>> 是的。

<details><summary>Original English</summary>

>> yeah.
</details>

>> 让生活更有趣。让生活更加引人入胜。

<details><summary>Original English</summary>

>> Makes

 life

 more

 fun.

 Makes

 life

 more





interesting.
</details>

### Agent 原生系统与商业新范式

>> 你知道，回到近期来说，我一直在反复思考的一件事，但我也很好奇你的看法，就是，你知道，Moltbook 的经验教训，以及即将需要被构建出来的这些 Agent 原生系统到底是什么。也许这也是 Instinct 正在做的一些事情，凭借他们那种 Instinct 对 Instinct 的网络，但感觉确实将会有……

<details><summary>Original English</summary>

>> You

 know,

 to

 kind

 of

 come

 back

 to

 the





near-

 term,

 a

 thing

 that

 I've

 been





thinking

 a

 bunch

 about,

 but

 I'm

 curious





for

 your

 take

 on

 is,

 you

 know,

 the





lessons

 of

 Moltbook

 and

 what

 are

 these





sort

 of

 agentnative

 systems

 that

 are





going

 to

 need

 to

 be

 built.

 And

 maybe





this

 is

 some

 of

 what

 Instinct

 is

 doing





with

 their

 kind

 of

 Instinctto

 instinct





network,

 but

 it

 does

 feel

 like

 there's





going

 to

 be
</details>

>> 基础设施和产品只为了 Agent 与 Agent 之间的交互而存在，而这在今天是不存在的。你怎么看？

<details><summary>Original English</summary>

>> infrastructure

 and

 products

 that

 exist





only

 for

 agentto

 agent

 interactions

 that





doesn't

 exist

 today.

 What

 do

 you

 think?
</details>

>> 这……这将会是一个全新的范式。我认为它……它开启了，你知道，我认为单单这个话题就可以聊上 10 个小时。嗯哼。

<details><summary>Original English</summary>

>> It's

 it's

 going

 to

 be

 a

 whole

 new





paradigm.

 I

 think

 it

 it

 opens

 up,

 you





know,

 I

 think

 that

 can

 be

 a

 10-hour





conversation

 on

 its

 own.

 Mhm.
</details>

>> 你有了 Agent 邮箱。你有了 Agent 电话号码。当服务不再是人向人预订，也不再是 Agent 向人预订，而是变成了 Agent 向 Agent 预订时，服务业的世界会变成什么样子？这又将如何重新定义整个服务业。嗯哼。

<details><summary>Original English</summary>

>> You

 have

 agent

 emails.

 You

 have

 agent





phone

 numbers.

 You

 have

 what

 does

 the





world

 of

 service

 look

 like

 when

 it's

 no





longer

 human

 booking

 to

 human

 and

 no





longer

 agent

 booking

 from

 human

 but

 it's





now

 agent

 booking

 from

 agent

 and

 how





does

 that

 redefine

 the

 entire

 service





industry

 as

 a

 whole.

 Mhm.
</details>

>> 呃，然后你还有整个网络安全……呃，所有这些东西的组成部分，那就是好吧，你知道互联网络先出现，然后网络安全随之而来；Agent 先出现，现在这些 Agent 的安全、安全组件随之而来，而这又将创造出什么样的行业？呃，不过这一切的美妙之处，我认为那……那就是资本主义的美妙之处。有如此多的机会，有如此多可以通过这些 Agent 来解决的问题。而且我认为不可避免的是，我们将看到如此多的初创公司涌现出来……

<details><summary>Original English</summary>

>> Uh

 and

 then

 you

 have

 like

 the

 whole





cyber

 security

 uh

 component

 of

 all

 this





stuff

 which

 is

 okay

 well

 you

 know





internet

 came

 first

 then

 came

 cyber





security

 agents

 came

 first

 now

 comes

 the





security

 security

 component

 of

 these





agents

 and

 what

 industry

 is

 that

 going





to

 create.

 Uh

 the

 beautiful

 part

 of

 it





all

 though,

 I

 think

 that's

 that's

 the





beauty

 of

 capitalism.

 There's

 like

 so





much

 opportunity

 and

 so

 many

 problems

 to





solve

 with

 these

 agents.

 And

 I

 think

 it





is

 inevitable

 that

 we're

 going

 to

 see

 so





many

 startups

 popping

 up
</details>

>> 试图去解决所有这些细分利基问题，以真正构建出这种互联网和数字化连接的新浪潮。

<details><summary>Original English</summary>

>> trying

 to

 figure

 out

 all

 of

 these

 niche





problems

 to

 really

 build

 this

 like

 new





wave

 of

 internet

 and

 digital





connectivity.
</details>

>> 是的，看着这发生会很酷，你知道，因为尤其是商业，你知道，我总觉得网络有点像是网络内部存在着三个网络，你知道，就像我心里有两只狼一样。嗯，这三个网络分别是商业网，嗯，应用网，以及内容网。而内容网陷入困境已经有一段时间了。我认为商业网实际上做得非常出色，然后应用网自从代码 Agent 发布以来绝对迎来了巨大的上升势头。嗯，但是商业网非常吸引人。你知道，本周你看到了 Shopify 是如何接纳 Muse 的，而亚马逊封禁了 Muse。我认为其中一部分的权衡考量将会是，当流量流向这些交易市场实际上出现了一个新的前门时，究竟谁是赢家，谁是输家。

<details><summary>Original English</summary>

>> Yeah,

 it's

 going

 to

 be

 cool

 to

 see,

 you





know,

 because

 especially

 commerce,

 you





know,

 I

 always

 think

 of

 the

 web

 as

 kind





of

 there's

 three

 webs

 within

 the

 web,





you

 know,

 just

 like

 there's

 two

 wolves





inside

 me.

 Um

 the

 three

 webs

 are

 the





commerce

 web,

 um

 the

 application

 web

 and





the

 content

 web.

 And

 the

 content

 web

 has





been

 in

 trouble

 for

 a

 while.

 I

 think





that

 the

 commerce

 web

 has

 actually

 done





really

 well

 and

 then

 the

 application

 web





has

 definitely

 been

 on

 a

 huge

 upswing





ever

 since

 coding

 agents

 were

 released.





Um

 but

 the

 commerce

 web

 is

 fascinating.





You

 know,

 you

 saw

 this

 week

 how

 Shopify





embraced

 Muse

 and

 Amazon

 blocked

 Muse.





I

 think

 part

 of

 the

 calculus

 is

 going

 to





be

 a

 winner

 or

 loser

 when

 you

 actually





have

 a

 new

 front

 door

 for

 how

 traffic





flows

 to

 these

 marketplaces.
</details>

>> 我的意思是，对于亚马逊和 Shopify 具体发生了什么，以及更广泛地说谁可能会成为赢家和输家，你有何看法？

<details><summary>Original English</summary>

>> I

 mean,

 do

 you

 have

 a

 view

 on

 what





specifically

 happened

 with

 Amazon

 and





Shopify

 and

 maybe

 more

 broadly

 who

 the





winners

 and

 losers

 are

 likely

 to

 be?
</details>

>> 是的，所以我认为，你知道，首先，Shopify 和亚马逊是两种截然不同的商业模式。你看到 Shopify 高度聚焦于让商业更民主化。而你看到亚马逊所有的钱都是靠广告收入赚来的。因此，整个商业的广告结构将会非常值得关注，因为当你移除了人类的眼球，这就挫败了整套系统的全部目的。

<details><summary>Original English</summary>

>> Yeah,

 so

 I

 think

 you

 know,

 first

 off,





Shopify

 and

 Amazon

 are

 two

 completely





different

 business

 models.

 You

 have





Shopify

 that's

 hyperfocused

 on

 more





democratizing

 commerce.

 You

 have

 Amazon





that

 makes

 all

 of

 their

 money

 on

 ad





revenue.

 And

 so

 the

 whole

 ad

 structure





of

 commerce

 is

 going

 to

 be

 really





fascinating

 to

 watch

 because

 when

 you





remove

 human

 eyeballs,

 it

 defeats

 the





entire

 purpose

 of

 the

 system.
</details>

>> 所以我认为，[清嗓子]，那就是亚马逊的出发点。比如如果你允许 Muse 和这些 Agent 开始购买，而他们从中得不到任何广告收入，

<details><summary>Original English</summary>

>> And

 so

 I

 think

 [clears throat]

 that's





where

 Amazon

 was

 coming

 from.

 Like

 if





you

 let

 Muse

 and

 these

 agents

 start

 to





purchase

 without

 them

 getting

 any

 ad





revenue

 out

 of

 that,
</details>

>> 这实际上从这种体验中剥离了他们的大量利润。所以，我认为很可能必须出现某种新的范式，来规定在 Agent 代表他们进行购买的世界里他们究竟该如何盈利；相比之下，Shopify 则是赋能日常普通个体去尽可能多地销售，而 Agent 让这个领域进一步民主化。所以，这简直是不可思议地有利。嗯，我认为当我们审视那些尚未被触及的行业时，事情会变得更加有趣，你知道，那是我们上周聊过的餐厅，如果在预订领域来看，对吧，比如你去订座，我想我们看到了 Resy，呃，Resy 开始封禁人们的账户，因为他们在用 browser-use，而他们不想要机器人，所以如果直接让 Agent 瞬间拿走这些预订，那就挫败了整套……整套商业逻辑，

<details><summary>Original English</summary>

>> it

 really

 takes

 a

 lot

 of

 their

 profit





out

 of

 the

 experience.

 So,

 I

 think





there's

 likely

 going

 to

 have

 to

 be

 some





new

 paradigm

 for

 how

 they're

 able

 to





profit

 in

 this

 world

 where

 agents

 are





are

 purchasing

 on

 their

 behalf

 versus

 a





Shopify

 that

 is

 empowering

 the

 everyday





individual

 to

 sell

 as

 much

 as

 possible





and

 agents

 democratize

 this

 space

 even





further.

 So,

 it's

 it's

 just

 unbelievably





advantageous.

 Um

 I

 think

 it's

 going

 to





be

 even

 more

 interesting

 when

 we

 look

 at





industries

 that

 have

 yet

 to

 be

 touched





and

 that's

 you

 know

 something

 we

 chatted





about

 uh

 last

 week

 was

 restaurants

 where





if

 you

 look

 at

 the

 booking

 space

 right





like

 you

 go

 to

 make

 a

 reservation

 I





think

 we

 saw

 resi

 uh

 resi

 started





shutting

 people's

 accounts

 down

 because





they

 were

 using

 browser

 use

 and

 they





didn't

 want

 bots

 so

 it

 defeats

 the

 whole





the

 whole

 business

 of

 if

 you

 just

 let





agents

 take

 these

 reservations





instantaneously
</details>

>> 那么这在某种程度上就违背了该平台的初衷——即这种以人为本的预订体验。

<details><summary>Original English</summary>

then

 it

 kind

 of

 defeats

 the

 purpose

 of





the

 platform

 of

 this

 like

 humanoriented





booking

 experience.
</details>

>> 然而，当每个人都拥有一个 Agent 时会发生什么呢？现在大家处在同一起跑线上。每个人都可以在同一时间去订餐厅。

<details><summary>Original English</summary>

>> And

 so

 what

 happens

 though

 when

 everyone





has

 an

 agent

 now

 everyone's

 on

 the

 same





playing

 field.

 Everyone

 can

 go

 to

 book





the

 restaurant

 at

 the

 same

 time.
</details>

>> 我们是否会进入这样一个世界：其一，权力回到了餐厅手中，他们也许可以根据忠诚度、平均消费或无论什么指标，来选择想把预订给谁；其二，我们是否会进入这样一个竞价的世界，一切都变成了这些 Agent 之间的竞价战？我很好奇你对那种未来图景的看法。

<details><summary>Original English</summary>

>> Do

 we

 enter

 a

 world

 where

 one

 power

 goes





back

 to

 the

 restaurants

 and

 they

 can





maybe

 choose

 who

 they

 want

 to

 give

 the





reservation

 to

 based

 off

 of

 loyalty

 or





average

 spend

 or

 whatever

 it

 be.

 or

 two,





do

 we

 go

 into

 this

 world

 of

 bidding





where

 everything

 becomes

 a

 bidding

 war





between

 these

 agents?

 I'm

 curious

 your





thoughts

 on

 kind

 of

 what

 that

 future





looks

 like.
</details>

>> 是的，我认为你非常正确。我的意思是，非常有趣，因为我认为会有，嗯，供给受限的事物，比如热门餐厅的餐位；也会有需求受限的事物，比如明天想飞往旧金山的人们。我认为对于餐厅而言，如果你从完全信息角度来考虑，他们想要谁？正如你所说，是最高的客单价（AOV）、最高的客户终身价值（LTV），这意味着多次光顾的累计 AOV。此外，他们实际上还希望确保自己尽可能处于接近 100% 的满座率。所以，这实际上是一种更复杂的计算，我并不完全清楚他们打算怎么做，但我确信独家供给将会变得越来越重要，你知道，而不是依赖终端消费者的摩擦和动机来作为防范这种拒绝服务（DoS）的手段。所以我认为商业中受供给限制的层面将会非常有趣，而受需求限制的层面将会完全不同，你知道，在那种情况下你几乎会拥有拼团购买的体验，有一群买家愿意购买某种产品、服务或体验，然后你有一组供给端——即可能满足该需求的商家——前来参与竞价，看看谁能提供最佳体验，或许是以最低的价格。因此我们一直都有这种需求聚合，但我们从未真正以同样的方式拥有过供给聚合，尤其不是在有利于消费者的拍卖机制中。

<details><summary>Original English</summary>

>> Yeah,

 I

 think

 you're

 super

 right.

 I





mean,

 very

 interesting

 because

 I

 think





there'll

 be

 um

 things

 that

 are

 supply





constrained

 like

 hot

 restaurant

 tables,





things

 that

 are

 demand

 constrained

 like





people

 that

 want

 to

 fly

 to

 SF

 tomorrow.





I

 think

 for

 restaurants,

 if

 you

 think





about

 with

 perfect

 information,

 who

 do





they

 want?

 to

 your

 point,

 it's

 the





highest

 AOV,

 highest

 LTV,

 which

 means





AOV

 over

 multiple

 visits.

 Plus,

 they





actually

 want

 to

 ensure

 that

 they're

 at,





you

 know,

 near

 100%

 capacity

 as

 much

 as





possible.

 So,

 that's

 actually

 a

 more





sophisticated

 calculation

 and

 I

 don't





quite

 know

 how

 they're

 going

 to

 do

 it,





but

 I'm

 sure

 that

 proprietary

 supply

 is





going

 to

 become

 more

 and

 more

 important,





you

 know,

 versus

 relying

 on

 kind

 of





friction

 and

 motivation

 from

 the

 end





consumer

 to

 act

 as

 something

 that

 sort





of

 prevents

 this

 DOS.

 So

 I

 think

 supply





constrained

 sort

 of

 aspects

 of

 commerce





will

 be

 really

 interesting

 and

 then





demand

 constrained

 will

 be

 completely





different

 you

 know

 where

 you

 almost

 have





a

 group

 buying

 experience

 where

 you

 have





a

 set

 of

 buyers

 that

 are

 willing

 to

 buy





a

 product

 or

 a

 service

 or

 an

 experience





and

 then

 you

 have

 the

 supply

 side

 the





merchants

 that

 could

 potentially

 fulfill





that

 need

 come

 and

 you

 know

 bid

 to

 see





who

 can

 do

 it

 the

 best

 experience

 maybe





at

 the

 lowest

 price.

 So

 we've

 always

 had





this

 kind

 of

 aggregation

 of

 demand,

 but





we've

 never

 really

 had

 aggregation

 of





supply

 in

 the

 same

 way,

 especially

 not





in

 an

 auction

 system

 to

 benefit

 the





consumer.
</details>

>> 所以我认为那非常有趣。

<details><summary>Original English</summary>

>> So

 I

 think

 that's

 really

 interesting.
</details>

>> 你知道，在亚马逊和 Shopify 这件事上，我认为亚马逊……亚马逊很可能做出了正确的押注，即他们不想被去中介化，而且他们不仅会失去广告收入，还会失去冲动消费。我有点好奇想知道，Agent 本身在某种程度上是否也会成为冲动消费者，因为我认为关于主动性的那一点意味着 Agent 将会尝试做出让人欣喜的猜测，并且你知道，有什么比惊喜或礼物更令人欣喜呢？

<details><summary>Original English</summary>

>> You

 know,

 in

 the

 Amazon

 Shopify

 thing,

 I





think

 that

 the

 Amazon

 Amazon

 probably

 is





rightly

 taking

 the

 bet

 that

 they

 don't





want

 to

 be

 disintermediated

 and

 that





they'll

 lose

 not

 just

 advertising





revenue,

 but

 impulse

 shopping.

 I'm

 kind





of

 curious

 to

 know

 if

 the

 agents





themselves

 will

 be

 impulse

 shoppers

 to





some

 extent

 because

 I

 think

 the

 point





around

 proactivity

 means

 the

 agents

 are





going

 to

 try

 to

 make

 delightful

 guesses





and

 you

 know

 what

 is

 more

 delightful





than

 a

 surprise

 or

 a

 gift.
</details>

>> 所以我推测，即将上演的非常有趣的……嗯，某种动态机制之一就是，这些 Agent 并不是其委托人的完美映射。它们并不是完全理性的。它们将以全新的方式兼具新的理性和非理性。而且我并不认为营销、冲动消费、广告这些东西会变得无关紧要。我只是认为它们需要被改造。

<details><summary>Original English</summary>

>> So

 I'm

 guessing

 that

 one

 of

 the

 really





interesting

 um

 sort

 of

 dynamics

 were





going

 to

 play

 out

 is

 that

 these

 agents





are

 not

 perfect

 reflections

 of

 their





principles.

 They're

 not

 perfectly





rational.

 They're

 going

 to

 be

 new





rational

 and

 nonrational

 in

 completely





new

 ways.

 And

 I

 don't

 know

 that

 things





like

 marketing,

 things

 like

 impulse





purchases,

 things

 like

 advertising

 won't





matter.

 I

 just

 think

 they

 need

 to

 be





transformed.
</details>

>> 完全赞同。而且我认为这同样开启了一场全新的对话，即在 Agent 化商业这一领域中，推荐引擎实际上究竟……

<details><summary>Original English</summary>

>> Totally.

 And

 I

 think

 that

 opens

 up

 a





whole

 new

 conversation

 as

 well,

 which

 is





what

 is

 the

 recommendation

 engine

 of





this

 agentic

 commerce

 space

 actually
</details>

<!-- chunk 7/7 -->

会是什么样？对。

<details><summary>Original English</summary>
look like? Yeah.
</details>

>> 因为在搜索质量方面，AI 和大语言模型感觉有点把互联网给搞坏了。但如果你用一个 Agent，对它说：“嘿，帮我买点白袜子。”

<details><summary>Original English</summary>
>> Because AI and LLM feels like it's kind of broke the internet in terms of quality search. But then if you use an agent and you say, "Hey, buy me some white socks."
</details>

>> 外面大概有两万种不同类型的白袜子，它给你推送，但它其实根本不知道你具体喜欢哪种类型的白袜子。

<details><summary>Original English</summary>
>> There's like 20,000 different types of white socks out there, it's going to send you, it doesn't actually know what exact type of white socks you prefer.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以我觉得这会非常有趣。我认为 Muse 在这方面可能占了先机。你知道，这整套理论就是扎克伯格对全商业进击的核心逻辑，他们有你的 Instagram 数据，他们有你的 Facebook 数据，所以他们可能对你真正偏好什么有稍微好一点的理解。但是看到这个推荐层会是什么样子，真的会很有意思。是的。

<details><summary>Original English</summary>
>> And so I think it'll be really interesting. I think Muse has probably a head start on this. And you know, this is whole Zuck's whole thesis of attacks on all commerce where they have your Instagram data, they have your Facebook data, so they probably have a little better understanding of what you actually prefer. But it'll be really interesting to see what this recommendation layer looks like. Yeah.
</details>

>> 在这个商业世界里。

<details><summary>Original English</summary>
>> In this world of commerce.
</details>

>> 嗯，我觉得这对长尾市场来说可能会很有意思，你知道，因为就拿你白袜子的例子来说，你可以想象，比如我可以去亚马逊买白袜子，你知道吧，但也许我的 Agent 回来说：“嘿，我在 Etsy 上找到了一个很棒的人可以给你织袜子，你知道，是内布拉斯加州的一位老奶奶，她她就织这种棒极了的白袜子。这需要三周时间。你能接受吗？”我说：“当然，我可以。听起来挺有意思。”所以，我有点好奇这是否会带来更多的意外惊喜，因为当然了，你知道，它可以审视所有的选项，在没有任何不良激励的情况下为你量身定制这些东西。

<details><summary>Original English</summary>
>> Well, I think it could be fun for the longtail, you know, because you could imagine to your white socks example, like I could go to Amazon and get white socks, you know, but maybe my agent comes back and says, "Hey, I found someone awesome on Etsy that can knit you the socks, you know, grandma in Nebraska, and she she just knits these amazing white socks. It's going to take three weeks. Are you down?" I'm like, "Sure, I'm down. That sounds interesting." So, I kind of wonder if it brings more serendipity in because of course, you know, it can examine all the options and perfectly tailor these things to you with no adverse incentives.
</details>

>> 没错。我很想要那样。我觉得那会太有趣了。这绝对会给如今枯燥乏味的购物生活增添一点风味。

<details><summary>Original English</summary>
>> Right. I would love that. I think that'd be so fun. It would definitely add a little flavor to the mundane life of shopping today.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Exactly.
</details>

>> 从我的角度来看很乏味，作为比如，你知道，从买袜子中体会不到乐趣的人。嗯，老兄，而且你看，你甚至可以想象一个世界，再往前卫一点想，它现在开始在现实世界中催化一些事情。所以也许不再是老奶奶织白袜子并在 Etsy 上卖，你知道，也许它发信息给老奶奶的 Agent 说：“嘿，你愿意做这个吗？”所以我认为这就是那种 Agent 对 Agent 的空间变得非常有趣的地方，它们都代表各自的人类行动。你知道，有的提供产品、服务、知识，有的去赚钱。而且，你知道，也许会有这样一种二级经济，它更有活力得多，频率更高得多，呃，也比我们今天的经济有趣得多。

<details><summary>Original English</summary>
>> Mundane from my point of view as someone who, you know, doesn't take joy in uh sock shopping. Well, dude, and look, you could even imagine a world and you get a little more futuristic where it starts to now um catalyze things in the real world. So maybe instead of grandma who knits white socks and sells them on Etsy, you know, maybe it messages the agent of a grandma and says, "Hey, would you be up for doing this?" So I think this is where the kind of agentto agent spaces get really interesting where they're all acting on behalf of their humans. you know, some to provide products, services, knowledge, and some to make money. And, you know, maybe there's this sort of secondary economy that's much more dynamic, much more high frequency, um, and just much more interesting than the one we have today.
</details>

>> 我我现在就在脑补内布拉斯加州的一位老奶奶收到一条短信说：“嘿，旧金山的这个家伙想让你帮他织白袜子。你想做吗？”

<details><summary>Original English</summary>
>> I'm I'm just imagining now a grandma in Nebraska receiving a text message saying, "Hey, this guy in SF wants you to knit white socks for him. You want to do it?"
</details>

>> 为什么不呢？对。对。为什么不呢？

<details><summary>Original English</summary>
>> Why not? Yeah. Yeah. Why not?
</details>

>> 那会太棒了。

<details><summary>Original English</summary>
>> It'd be awesome.
</details>

>> 是的。所以，我我实际上非常抱有希望。你知道，它也是它在某种程度上以正确的方式设定了激励机制，因为如果 Agent 做的是正确的事，它们是在基于产品质量来挑选优秀的产品，而且它们可以自行评估产品质量，而不是，你知道，选择营销最好或品牌最响的东西。顺便说一句，如果它们是在品牌基础上来做选择，至少也是经过了它们用户的明确认可，比如我就想要耐克，因为我喜欢耐克，而不是因为，你知道，营销中产生了这种认知失调，而消费者实际上在做对自己而言并非最优的事情，

<details><summary>Original English</summary>
>> Yeah. So, I'm I'm I'm actually very hopeful. You know, it also it sort of sets the incentives in the right way because if the agents are doing the right thing, they're choosing great products based on product quality and they can assess product quality for themselves rather than, you know, the thing that has the best marketing or the best brand. And by the way, if they are choosing on a brand basis, it's at least with the explicit sign off of their user like I just want to have Nikes cuz I love Nikes, not because you know there there's sort of this cognitive dissonance that's happening in the marketing and the consumer is actually doing something that's not optimal for themselves,
</details>

>> 对吧？这它为真正与消费者保持一致的互联网打开了大门，而我认为这种互联网我们已经缺失相当长一段时间了。

<details><summary>Original English</summary>
>> right? It it opens the door to a truly consumer aligned internet which I think we have been lacking for quite some time.
</details>

### Agent 的经济模型与长尾挑战

>> 我同意，老兄。我们聊到了 Agent 的经济模型。在我浏览过的 122 个中，我个人测试了其中的 26 个。

<details><summary>Original English</summary>
>> I agree, man. We touched on the the economics of the agents. Of the 122 that I have looked through, so I've personally tested 26 of them.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 在这 122 个当中，呃，有 65 个是收费的。

<details><summary>Original English</summary>
>> Of the 122, uh, 65 are paid.
</details>

>> 很有意思。

<details><summary>Original English</summary>
>> Interesting.
</details>

>> 其中 35 个是全付费的。30 个是免费增值模式。也就是说一旦你达到了额度限制，就必须付费。其实只有 13 个是免费的。

当你有 Muse 和 Instinct 这两个都是免费的、同时也占据主导地位的产品，然后你还有 OpenAI 据说可能下周要发布什么酷炫的东西，谁知道呢？

<details><summary>Original English</summary>
>> 35 of them are fully paid. 30 are a premium model. So once you hit a limit, then you have to pay. Only 13 of them are actually free.

When you have Muse and Instinct that are both free that are also the dominant ones and then you have Open AI that supposedly is going to be releasing something cool maybe next week, who knows?
</details>

>> 长尾初创公司到底要怎么在这个领域赢？

而且当巨头们免费提供给你时，为什么他们还要收钱？

<details><summary>Original English</summary>
>> How does a longtail startup actually win this space?

And why are they charging money when the big dogs are giving it to you for free?
</details>

>> 哎呀，这将会非常具有挑战性。你知道，按我们的估算，

以真正雄心勃勃的方式来做这件事，每位用户每天的花费大概在 20 美元左右。

你知道，对初创公司来说可能一年要花几亿美元。我的意思是，我认为值得押注的两个积极趋势是：浏览器使用应该会呈现通缩趋势，以极快的速度呈指数级变便宜。现在如果你是一家正在融资的初创公司，押注这会在 6 个月内发生，也许这有点像胆小鬼博弈，但我们已经看到 Token 价格大幅下降，以及某种新兴能力的成本下降，也就是它们的价格，

所以我觉得浏览器使用变得足够便宜、让更多呃更多产品能够免费提供这个功能，是非常有可能的。不过我认为反过来说，我并不太喜欢把你知道的客户补贴作为核心价值主张这种想法。所以，我很希望能看到有一款每月收费 1000 美元的 Agent，消费者对它非常着迷，以至于愿意付费。就像人们每月在很多不同的东西上花 1000 美元，那些你知道不一定是必需品，而是某种欲望。那么，到底是怎样一款足够令人兴奋的 Agent，能让你愿意为它支付这种价位？然后那个 Agent 既会受益于极高的市场契合度，也会受益于某种正在走低的成本。

<details><summary>Original English</summary>
>> Man, it's going to be really challenging. you know, by our estimate, it's costing something like $20 per user per day

to do this in a really ambitious way. You know, potentially hundreds of millions a year for a startup. I mean, I think the two positive trends to bet on are that browser use should get it should be deflationary, get exponentially cheaper, very rapidly. Now if you're a startup that is raising today that's betting on that happening in 6 months maybe it's a little bit of a game of chicken but we have seen kind of token prices depress dramatically and sort of emerging capabilities depress so the price of them

so I think it's very possible that browser use gets cheap enough that more um more products can offer this for free. I guess the flip though is that I don't love the idea of you know a customer subsidy being the primary value prop. So, I'd love to see the agent that costs $1,000 a month that the consumer is so excited about that they're willing to pay. Like, people spend $1,000 a month on a lot of different things that are, you know, not necessarily necessities, their sort of desires. So, what is the agent that is exciting enough that you're willing to pay that kind of price for it and then that agent will benefit from both extreme market fit as well as sort of deflating costs.
</details>

>> 对。对。我觉得这将会很有看头。

<details><summary>Original English</summary>
>> Right. Right. I think it'll be interesting to see.
</details>

>> 超级有意思。好的，来自 Assistant Bench 的 David，大家一定要去看看这个项目。非常感谢你加入我们。我们会经常做这类交流。我的意思是，我觉得我们每周都可以做一次，老兄。就像，每天都有新事情发生。所以，

<details><summary>Original English</summary>
>> Super interesting. Well, David from Assistant Bench, make sure everybody checks it out. Thank you so much for joining us. We're going to do this frequently. I mean, I feel like we could do this every week, dude. Like, things are happening every single day. So,
</details>

>> 请在 X 上关注他。也请关注我。我们都会跟上进度，并在 X 社区中一起学习。然后呃然后祝

<details><summary>Original English</summary>
>> please follow him on X. Follow me as well. We'll all keep up to speed and sort of learn together in the X community. And uh and sort of
</details>

>> 祝你和你的 Agent 们度过愉快的一天。

<details><summary>Original English</summary>
>> happy day to you and your agents.
</details>

>> 非常感谢。你也一样。这很有趣。

<details><summary>Original English</summary>
>> Appreciate it. Same to you. This is fun.
</details>

>> 好的，兄弟。谢谢你。

<details><summary>Original English</summary>
>> All right, brother. Thank you.
</details>

>> 太棒了。

<details><summary>Original English</summary>
>> Awesome.
</details>