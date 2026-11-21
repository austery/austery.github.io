---
author: All-In Podcast
date: '2026-11-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1bR0gtecoHU
speaker: All-In Podcast
tags:
  - ai-agent
  - data-governance
  - machine-learning
  - enterprise-ai
title: Databricks CEO Ali Ghodsi 探讨公司发展历程、AI 应用及企业数据治理
summary: Databricks CEO Ali Ghodsi 分享了公司从加州大学伯克利分校实验室起步的历程，强调了在企业环境中处理数据、安全与治理的复杂性。他指出，虽然 AI 实验室预测变革可能迅速发生，但他认为由于企业内部的“上下文差距”和陈旧架构，实现真正的 AI 价值可能需要 10 到 15 年。此外，他提到了公司在药物研发、危机干预等领域的 AI 应用。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Databricks
  - UC Berkeley
  - Netflix
  - Merck
products_models:
  - Genie
  - Teddy
  - Transformer Enabled Drug Discovery
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

所以，某种程度上是因为绝望，我们才创立了 Databricks，因为当时根本没有其他人在听。在那个时候，人们对人工智能毫无兴趣。而现在，我认为我们已经拥有了彻底改变地球所需要的全部智能。
<details><summary>Original English</summary>
So, it was kind of out of despair that we started Databricks because no one else is listening to it. At that time, there was zero interest in AI. Now, I think we have all the intelligence we need to completely transform the planet.
</details>

>> 现实地讲，让一千个智能体去办事是不可能的。我说得对吗？
<details><summary>Original English</summary>
>> It's not possible to have a thousand agents doing stuff realistically. Am I correct?
</details>

>> 他们只是在以非常初级的方式使用人工智能。他们仅仅是把它当作一种美化版的谷歌搜索在使用。
<details><summary>Original English</summary>
>> They're just using AI in very rudimentary ways. They're just using it as a glorified Google search.
</details>

>> 我们实际上正在进入类似于管理上的“点球成金”（Moneyball），不是吗？
<details><summary>Original English</summary>
>> We're actually getting into like management money ball, aren't we?
</details>

>> 那么，如果 token 成本呈指数级上升，你公司的收入是否也在呈指数级上升？但实际上我认为 GDP 的变动会非常缓慢，这需要几十年的时间。
<details><summary>Original English</summary>
>> So, if the token cost is going up exponentially, is your revenue at your company going up exponentially? But I actually think GDP will move very slowly and it's going to take decade.
</details>

>> 他们是不是有点被自己的成功冲昏了头脑？
<details><summary>Original English</summary>
>> Are they a little drunk on their own success?
</details>

>> 仅仅因为 98% 的代码是由 AI 编写的，并不意味着我们就拥有了 RSI（递归自我改进）。如果它把剩下的 2% 也自动化了，谁在乎呢？
<details><summary>Original English</summary>
>> Just because 98% of the code is being written by AI, we don't have RSI. If it automates the last 2%, who cares?
</details>

>> 你们什么时候上市？
<details><summary>Original English</summary>
>> When are you going public?
</details>

>> 我要全力以赴。
<details><summary>Original English</summary>
>> I'm going all in.
</details>

>> 如果你今天从第一性原理出发构建一个全球金融体系，你不会把它建立在有 50 年历史的陈旧轨道之上。你会构建 Aerovox，一个面向全球账户、卡片和支付的 AI 原生平台。它的设计初衷是让整个世界感觉像一个本地市场。其他公司是将 AI 强行拼凑在残破的基础设施之上，但 Aerovox 从第一天起就是为智能时代而生的。停止支付陈旧架构带来的遗留税，并开始在 aerovox.com/allin 构建未来。Aerovox，为未来而生。
<details><summary>Original English</summary>
>> If you were building a global financial system from first principles today, you wouldn't build it on 50-year-old legacy rails. You'd build Aerovox, one AI-native platform for global accounts, cards, and payments. It's designed to make the entire world feel like a local market. Others are bolting AI onto broken infrastructure, but Aerovox was built for the intelligent era from day one. Stop paying the legacy tax and start building the future at aerovox.com/allin. Aerovox, built for the future.
</details>

### 对话开始与 Databricks 概况

>> 好的，各位。欢迎回到 All-In 专访。我们非常幸运，因为（清嗓子）世界上所有这些杰出的领袖，无论是 CEO、政治家还是科学家，他们都在看我们的节目。他们是这个社区的一部分。而 Ali Ghodsi 就是这些人中的一员。他当然是 Databricks 的 CEO，这是一家表现极其出色的非上市公司。我不知道它为什么还没有上市。我认为很多人都在问这个问题。我们今天会聊聊这个话题。

在 2015 年，他们的营收是 150 万美元。到了 8 月——或者我听到的传言是，在 2026 年 8 月，Ali，年化运行率达到了 70 亿美元，同比增长 80%。显然，你们面临着很多竞争，比如世界上的 Snowflake 等等。但这真是一门了不起的生意。我们今天会详细聊聊你们是如何利用 AI 来经营这家令人赞叹的企业。我们会聊到递归自我改进（RSI）。不过首先欢迎来到节目中。接着或许你可以向观众稍微介绍一下你在 Databricks 的工作，以及它是如何变得如此成功的。
<details><summary>Original English</summary>
>> All right, everybody. Welcome back to the all in interview. We're so lucky because [clears throat] all of these amazing leaders in the world, CEOs, politicians, scientists, they they watch the show. They're part of the community. And Ali Ghodsi is one of those individuals. He, of course, is the CEO of Databricks, a private company that has been doing incredible. I don't know why it's not public yet. I think a lot of people are asking that question. We'll talk about it today.

In 2015, they were doing 1.5 million in revenue. It's August or the the rumor I heard, August 2026, Ali, $7 billion run rate growing 80% year over year. And obviously, you got a lot of competition, the snowflakes of the world, etc. But this is a tremendous business. And we're going to talk a lot about how you're using AI to run this incredible business. We're going to talk about recursive self-improvement. But welcome to the program. And then maybe you could tell the audience a little bit about what you do at Databricks and how it became so successful.
</details>

### 从加州大学伯克利分校 Amplab 到创立 Databricks

>> 好的，非常高兴能聊这个。谢谢你们邀请我来。我很兴奋。

是的，我们是在 2013 年创办了这家企业。但如果把时间稍微往前倒回一点，当时我们都在加州大学伯克利分校。我们大概有 20 个人。我们当时属于一个叫作 Amplab 的实验室，我想那是当时全世界最大的人工智能研究实验室。你看，我们当时一直试图搞清楚，怎样才能将数据处理与人工智能结合起来。

你知道，我们提出了非常有趣的东西，但业界当时根本没有做好准备。所以我们试图让业界采用这项技术，但他们没有。因此，某种程度上是因为绝望，我们才创立了 Databricks，因为我们想，如果不围绕它成立一家公司，就没有其他人会听。在那个时候，人们对人工智能毫无兴趣。实际上在当时它被称为机器学习，而人工智能在当时仅仅指机器人学。所以那差不多就是故事的开端。
<details><summary>Original English</summary>
>> Yeah, happy to do that. Thanks for having me on. Excited for this.

Yeah, so we started the business in 2013. But if you rewind a a little bit before that, we were all at UC Berkeley. There were about 20 of us. And we were actually part of a lab called Amplab, which was I think the largest AI research lab in the world at that time. And you know, we were trying to figure out how can we combine data processing with AI. And you know, we came up with really interesting things, but the industry was just not ready for it. So we were trying to get the industry to adopt this technology and they weren't. So it was kind of out of despair that we started Databricks because we thought, you know, if we don't start a company around this, no one else is listening to it. At that time there was zero interest in AI. Actually it was called machine learning at the time and AI was just robotics. So that's kind of like the beginning of the of the story.
</details>

>> 对于那些平时不用该产品、不在这个行业里的人来说，Databricks 产品套件的目标是什么？你们是做什么的？我知道你们今天发布了一些新产品，所以也很乐意谈谈那些。但从概念上讲，你们涉足得非常早。显然在机器学习方面，谷歌就是建立在它之上的，Facebook 以及他们的广告网络也是，还有很多有趣的服务，比如 Uber 及其路线算法。也许我们可以稍微聊聊 Databricks 从何处起步，如今变成了什么，以及它是如何创造数十亿美元收入的。
<details><summary>Original English</summary>
>> And for people who don't use the product day in and day out, who aren't in the industry, what what's the goal of the Databricks product suite? What do you do? I know you released some new products today, so happy to talk about those as well. But conceptually, you got there so early. Obviously machine learning, Google was built on that, Facebook and their ad network, a lot of interesting services, Uber and their routing algorithms. Maybe we can talk a little bit about where Databricks started and and what it's become and and how it's generating billions of dollars in revenue.
</details>

### 第一个用例与企业落地的障碍

>> 是的，第一个用例其实，有史以来的第一个用例是在加州大学伯克利分校，当时我们想帮助 Netflix 推荐更好的电影，以便让人们观看更多的电影。所以它就像是一个推荐算法，是一个开启了整件事情的人工智能用例。然后我们想，更多的机构，大概每一个机构都会需要一个能够做这种 AI 工作的数​​据科学团队。

这在当时算是一个大胆的想法。有很多人说，不、不、不，AI 只是用于广告技术，是广告公司才需要的。但我们当时认为，不、不、不，这将会是一个更大的市场。实际上我们内部进行了很多争论，我们并不确定它是否真的会爆发。所以我们就投入去做了。

接着当我们创办公司时，我们意识到他们为什么不这么做，为什么会这么难。因为基本上世界上所有的组织机构都陷入了停滞。他们拥有已经使用了 30 年、40 年、50 年的陈旧软件。有些公司甚至已经存在了 100 年。

各种事情进展缓慢。他们有大量的流程。有大量的合规要求，大量的监管要求，大量的安全问题。顺便提一下，近年来随着生成式人工智能的出现，所有这些问题都变得更严重了。

所以基本上我们在加州大学伯克利分校的研究中所欠缺的，就是我们当时没有考虑安全性与治理问题。因此，我们在最初的几年里所做的，就是弄清楚如何运用这项技术，让你能够处理企业内部的所有数据。你看，组织机构拥有大量的数据。他们所拥有的最重要的数据，实际上人们并不谈论它。任何一家公司所拥有的最重要的数据，就是关于他们核心产品的数据。比如对你们这里的各位来说，就是这个播客，也就是关于这个播客的数据。另外某个人可能在卖保险。还有人可能在做某种药物。这就是从中产生的数据。

这些数据不在 CRM（客户关系管理系统）里，也不在人力资源管理系统里。
<details><summary>Original English</summary>
>> Yeah, so the first use case actually, it was the first use case ever was at UC Berkeley when we wanted to help Netflix recommend better movies so that people would watch more movies. So it was like a you know, recommendation algorithm, AI use case that started the whole thing. And then we thought, you know, more organizations probably probably every organization will need a data science team that can do this kind of AI stuff.

And it was kind of bold at the time. There was a lot of people that said, no, no, no, AI is just for ad tech, the ad companies need it. But we we thought, no, no, no, this is going to be a bigger market. And actually we had a lot of debates internally. We weren't sure it was going to explode. So we got into it.

And then we realized when we started the company, we realized why they're not doing it, why it's so hard. Because basically all the organizations out there in the world are bogged down. They have legacy software that they've had for 30, 40, 50 years. And some some of them, you know, companies have been around for 100 years.

You know, things are moving slow. They have a lot of processes. There's you know, a lot of compliance, a lot of regulatory, a lot of security. By the way, all these things have gotten worse with generative AI in the recent years.

So basically what was missing from our research at UC Berkeley was that we didn't think about the security, the governance. So what we did the first bunch of years is that we figured out how do we take this technology that lets you process all your data in an enterprise. So you know, organizations have a lot of data. The most important data they have actually people don't talk about it. The most important data any company has is the data on the core product that they have. Like for you here, it's this podcast, you know, the data on that. Someone else might be selling insurance. Someone else might have, you know, a drug. It's the data that comes out of that.

That data doesn't sit in CRM. It doesn't sit in human resource management.
</details>

### 云计算、存储分离与三大豪赌

>> 对，事实上，以前甚至可能根本没有追踪这些数据。我记得在互联网早期，他们会说：“嘿，你想要这个日志文件吗？”我会说：“好啊，全部保留。”然后他们会说：“好吧，那你的存储账单是每月 8,000 美元。”我就说：“那好吧，删掉它。”

然后他们说：“嗯，我们可以进行汇总汇总，保留其中一部分。”我就会想：“谁会去用我们电子邮件的打开率呢？谁在乎那个？我们把邮件发出去就行了。”但随后情况发生了变化。那么存储、算力和云计算是不是这次大数据浪潮的主要加速器？进而最终催生了机器学习，这些算是这场浪潮中的关键里程碑吗？
<details><summary>Original English</summary>
>> Yeah, in fact, it probably wasn't even tracked. I remember in the early days of the internet, they'd be like, hey, would you like this log file? And I'd say, okay, yeah, keep everything. And they'd say, okay, well, you got $8,000 storage bill a month. And I'd be like, okay, delete it.

And they're like, well, we could roll it up and keep some of it. I'm like, well, who's ever using the open rate on our emails? Who cares about that? You know, we send the emails, that's it. But then that changed. And was storage and compute and cloud computing a major accelerant to this big data movement? And then eventually machine learning, those were kind of the waypoints in this movement?
</details>

>> 是的。在我们 2013 年起步之前，人们基本上是在运营自己的数据中心。而在运营自己的数据中心时，你必须购买机器。机器是存储和计算绑定在一起的。所以如果你用光了存储空间，你就必须购买更多的机器。每个组织的 IT 部门都在忙于应付这件事。

云计算实现的是将这一结构彻底解耦，并将计算与存储分离，这样你就可以设想自己拥有无限的存储空间。你只要把所有东西丢到那里就行了，明白吗？如果数据变冷了——也就是数据变旧了——它知道该如何进行归档，从而使存储成本变得几乎免费。呃，接着你就能获得想要多少计算资源就有多少计算资源的虚构体验。然后，你当然可以开始在上面运行机器学习，随后 GPU 也终于登场了。

呃，所以这在某种程度上改变了一切。我们把一切、整个身家都押注在成为一家纯云计算公司上。我们把一切押在人工智能、押在人工智能的用例上，而且我们押注在开放与开源上。在当时，其实这三个押注都充满了争议。人们当时——我和业内最重要的一家分析机构打过一个长期的赌，他们说这是一个战略性失误，你会因为押注云计算而倒闭。事实证明，我们之所以成功的唯一原因正是由于这些押注，因为它们是逆向的，因为其他人并不认同它们。所以我们在很多很多年里抢占了先机。呃，后来当我们恰好被证明是正确的时候，我们已经走得很远了，规模已经变得非常大，积累了太多的势头去……
<details><summary>Original English</summary>
>> Yeah. Before we started in 2013, basically people were running their own data centers. And when they're running their own data centers, you had to buy machines. And the machines came with storage and compute combined. So if you ran out of storage, you had to buy more machines. And the IT departments of every organization were busy with this.

What the cloud enabled was to just completely decentralize this and separate computer storage so that you could just imagine you have infinite storage. You just dump everything there, okay? And if it's gotten cold, so the data is old, it knows how to archive it so that it becomes almost free to store it. Uh and then you could get the illusion of as much compute as you wanted. And then of course you could start running machine learning on it and then eventually GPUs showed up. Uh so it kind of transformed everything. We bet everything, the whole farm, on just being a cloud company. We bet everything on AI, the use cases of AI, and we bet on open and open source. And at the time actually all three of these bets were controversial. People were I had a standing bet with one of the most important analyst firms out there where they said it's a strategic blunder. You're going to go under because you're betting on the cloud. And it turned out actually the only reason we succeeded was because of these bets because they were contrarian, because other people did not agree with them. So we got a head start for many many years. Uh and then eventually when we you know happened to be right then we had you know we were so far along and we gotten too big that you know there's too much momentum to to
</details>

<!-- chunk 2/9 -->

阻止它。
<details><summary>Original English</summary>
stop

 it.
</details>

### Netflix 奖与 AMPLab 的起源

>> 很有意思你提到了 Netflix 的算法。显然，Netflix 起步于湾区，当时是通过信封邮寄 DVD，然后你会有个待播队列。当时极其重要的是——对于不了解 Netflix 奖的人来说，这是在 2008、2009 年期间，他们设立了百万美元大奖，奖励给任何能把电影评分预测（预测你会给四星还是五星）算法提升大约 10% 的计算机科学团队。于是他们拿出了所有数据并公开发布，然后全球计算机科学家的工作成果大概为他们创造了价值 5000 万美元的产出。那是第一次有类似 X Prize 的形式，我认为 X Prize 和这个大概在同一时期，它们都是受到那些古老奖项的启发。比如谁能环球航行，谁能像阿梅莉亚·埃尔哈特那样单人飞行，谁能独自飞越大西洋或太平洋。那在当时是一个非常有趣的时刻，这也触动了 AMP，对吧？AMP 这个组织代表的是算法（algorithms）、机器学习（machine learning），我不知道 P 代表什么。
<details><summary>Original English</summary>
>> It's

 so

 funny

 you

 mentioned

 this

 Netflix





algorithm.

 Netflix

 started

 uh

 obviously





in the

 Bay

 Area

 as

 DVDs

 that

 were

 mailed





to

 you

 in

 an

 envelope

 and

 then

 you

 had





this

 queue.

 And

 it was

 critically





important

 uh for

 people

 who

 don't

 know





the

 Netflix

 prize.

 This

 was

 in

 the





2008

 2009

 time

 period.

 They

 put





a

 million

 dollar

 prize

 out

 to

 any





computer

 science

 team

 that

 can

 make

 the





algorithm

 I

 think

 10%

 better

 at





predicting

 what

 movie

 you

 would

 give





four

 or five

 stars

 to.

 So

 they

 just

 took





all

 their

 data,





they

 released

 it,





and

 then





they

 got

 probably

 $50

 million

 worth

 of





work

 from

 computer

 scientists

 around

 the





world.

 It was

 the

 first

 time

 an

 X

 Prize





and

 I think

 X

 Prize

 and

 uh

 this

 were





around

 the

 same

 time

 and

 they

 were

 all





inspired

 by

 those

 old

 prizes.

 So

 like





who

 could

 circumnavigate

 the

 globe,

 who





could

 solo

 fly

 over

 Amelia

 Earhart,

 who





could

 who

 could

 solo

 fly

 over

 the





Atlantic

 or

 the

 Pacific.

 It was

 like

 a





very

 interesting

 moment

 at

 time

 and





that

 hit

 amp,

 right?

 And

 amp

 the

 group





was





algorithms,

 machine

 learning.

 I

 don't





know what

 the

 P

 stands

 for.
</details>

>> 实际上代表“人”（people），因为我们当时觉得，你知道，AI 还不够好。
<details><summary>Original English</summary>
>> It

 was

 for

 people

 actually

 cuz

 we





thought

 that

 you

 know

 the

 AI

 is

 not

 good





enough

 yet.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mm.
</details>

>> 所以它需要一点人类的介入引导。所以它其实就是，你知道，人类反馈（human feedback）当时就已经存在了。我们当时觉得，我们确实需要人类反馈，因为这最后一公里对 AI 来说完全靠自己解决实在太难了。所以我们当时也把人纳入其中。
<details><summary>Original English</summary>
>> So

 it

 needs

 a

 little

 bit

 of

 human





nudging.

 So

 it's

 actually

 actually

 just





kind

 of

 you

 know

 uh

 human

 feedback

 was





already

 there.

 We

 were like

 we

 do

 need





the

 human

 feedback

 cuz

 this

 this

 this





last

 mile

 is

 just

 too

 hard

 for

 AI

 to





figure

 out

 itself.

 So

 we had

 people





there

 as

 well.
</details>

### 通用人工智能与超级智能的辩题

>> 把人放进去讲得通，因为伯克利带点嬉皮风格。显然也是弗莱伯格的母校。［笑声］他们当时就觉得，我们需要在中间放些人。前几周本·霍洛维茨来做客，他当时说，关于为什么我们能够控制超级智能的推进，以及通用人工智能（AGI）与能够自我递归、失控发展并导致全人类毁灭终结（P(doom)）的超级智能之间的这一飞跃——他听过对此最好的解释就来自你。所以请阐述一下你的这个论点，然后我还希望你能更进一步，具体谈谈湾区、甚至东湾以及这群人的文化。
<details><summary>Original English</summary>
>> Putting

 the

 people

 in

 there

 makes

 sense





cuz

 Berkeley's

 a little

 hippie

 dippy.

 Uh





Freyberg's

 alma

 mater

 obviously.





[laughter]

 They

 were

 like

 we

 need

 we





need

 some

 people

 in

 the middle

 of

 this.





You know

 we

 had





Ben

 Horowitz

 on

 uh





sat

 in

 the

 other

 week





and





he

 was

 like

 the

 best

 explanation

 I've





ever

 heard





for

 why

 we

 are

 going

 to

 be

 able

 to





control

 the

 rollout

 of





super

 intelligence

 and

 this

 jump

 between





artificial

 intelligence

 or

 artificial





general

 intelligence

 and

 super





intelligence

 that

 gets

 recursive

 and





runs

 off

 with

 it

 and





P

 dooms

 us

 all

 and

 we're

 all

 going

 to





die

 uh





sentiment

 by

 some

 people

 came

 from

 you.





So

 please

 explain

 your

 thesis

 here

 and





then

 I'd

 like

 you

 to

 go

 even

 one

 step





further

 and

 talk

 specifically

 about





maybe

 the

 culture

 in

 the

 Bay

 Area,





perhaps

 even

 the

 East

 Bay





and

 and

 this

 group

 of

 people.
</details>

>> 我很乐意聊聊这个。我觉得这里面同时有两件不同的事情在发生。一方面，我其实认为我们已经拥有通用人工智能（AGI）了。我从去年开始就一直在这么说，我的依据是我们在 AMPLab 达成的共识，AMPLab 在 2009、2010 年时我认为是当时最大的 AI 实验室，而我们大多数人当时对 AGI 的定义，去年就已经实现了。其实我当时并不完全确定这点，所以我还特意去和当年实验室里的一些人核实过，比如问他们：“嘿，是我一个人的幻觉吗？”他们说：“不、不、不，按那个定义绝对是达到了，但我们把目标门槛移高了。”你知道吗？所以，我其实认为我们已经拥有了所需的一切智能。而且说实话，如果碰巧现在所有的进展都停滞，我认为我们拥有的智能也完全足够彻底改变这个星球。好吗？但这就是那个观点。
<details><summary>Original English</summary>
>> I

 mean

 happy

 to

 get

 into

 it.

 You

 know

 I





think

 there's

 uh





sort

 of

 two

 different

 things

 happening





at

 the

 same

 time.

 On

 the

 one

 hand

 I





actually

 think

 we

 already

 have





artificial

 general

 intelligence.

 I've





been

 saying

 it

 since

 last

 year

 and

 I





based

 that

 on

 the

 kind

 of

 consensus

 we





had

 in

 that

 amplab

 where

 it

 was

 I

 think





the

 largest

 AI

 lab

 at

 the

 time

 in

 2009





2010

 and

 that

 definition

 of

 AI

 that

 most





of

 us

 had

 AGI

 we

 already

 achieved

 that





last

 year

 and

 I wasn't

 actually

 sure





about

 this

 so

 I actually

 went

 and





checked

 with

 some

 of

 the

 people

 that





were

 in

 the

 lab

 like

 hey

 is

 it

 just

 me





am

 I

 hallucinating

 and

 they

 said

 no

 no





no

 that

 definition

 for

 sure

 but

 we've





moved

 the

 goal

 post.





You

 know?

 So,

 uh

 so

 I actually

 think

 we





have

 all

 the intelligence

 we

 need.

 And





actually,

 if

 if

 you

 stop

 the

 if

 you





happen

 to

 stop

 all

 progress

 right

 now,

 I





think

 we

 have

 all

 the intelligence

 we





need

 to

 uh completely

 transform

 the





planet.

 Okay?

 But

 that's

 the

 idea.
</details>

>> 人类所有的智力工作，对吧？我是说，如果它能解决最新这一批数学问题，而我们现在才刚开始构建 harness、完善基础设施，我想你的说法是正确的，我大概也赞同你的看法。我们已经触达了通用人工智能，只是它还没有被分发，还没有被平均分发。
<details><summary>Original English</summary>
>> all

 intelligence

 work

 by

 humans,

 right?





I mean,

 if

 it

 solves

 this

 latest

 cohort





of

 math

 problems





and

 we're

 just

 starting

 to

 build





harnesses

 and

 build

 out

 the





infrastructure,

 I

 guess

 your

 statement





would

 be

 correct

 and

 I

 I

 kind

 of

 am

 in

 a





line

 with

 you.

 We've

 hit

 artificial





general

 intelligence.

 It just

 hasn't





been

 distributed,

 equally

 distributed





yet.
</details>

>> 是的。各大实验室和很多研究人员，他们现在有点痴迷于超级智能。好吗？那么当我说超级智能时，我的意思是指博斯特罗姆在 2014 年那本名为《超级智能》的书中所定义的那样。他在那里谈论的是完全不同的东西。他指的是某种能够完成千年级别思考的存在。也就是说人类一千年的思考量，它们可能一分钟就能完成。好吗？全人类的量，一分钟。它在 11 维空间中思考。速度快得多。单单一个智能体就，你知道，高出好几个数量级。想象一下比我们任何一个人都快一千倍。好吗？那是完全另一回事。就像它能瞬间写出一篇全新的博士论文等等。所以，我认为各大实验室目前都在追求那个。顺便说一句，在这当中——
<details><summary>Original English</summary>
>> Yeah.

 So,

 the

 labs

 and

 a lot

 of





researchers,

 they're

 kind

 of

 obsessed





with

 super

 intelligence.

 Okay?

 So,

 when





I

 say

 super

 intelligence,

 uh I

 mean

 it





the

 way

 it

 was

 defined

 by

 Bostrom

 in





2014

 in

 his

 book

 called

 Super





Intelligence.





And

 there

 he's

 talking

 about

 something





completely

 different.

 He's

 talking

 about





something

 that

 can

 do

 a

 millennia

 worth





of

 thought.





So,

 like

 a thousand

 years

 of

 human





thought,

 they

 can

 do

 it

 like

 in

 a





minute.

 Okay?

 All

 of

 mankind

 in

 a





minute.

 It

 thinks

 in

 11

 dimensions.

 It's





so

 much

 faster.

 Just

 a

 single

 agent

 is





just,

 you

 know,

 many

 orders

 of





magnitude.

 Imagine

 a thousand

 times





faster

 than

 any

 of

 us.

 Okay?

 And

 that's





just

 a

 different

 thing.

 Like

 that's

 it





can

 write

 a

 novel

 PhD

 thesis





instantaneously

 and

 so

 on.

 So,

 I

 think





the

 labs

 are

 on

 the

 quest

 of

 that.

 And





in

 that

 by

 the

 way
</details>

>> 稍微总结一下，瞬间写出一篇完整的、独创的博士论文的能力，在你看来，我们今天到底有没有足够的算力来做这样的事？如果大家联合起来说：“嘿，今天作为思想实验，我们在接下来的一个小时里把所有算力都供给这个超级庞大的提示词”，你觉得这真的会发生吗？这是一个计算机算力问题，还是一个模型问题？
<details><summary>Original English</summary>
>> and

 so

 just

 to

 summarize

 that

 there,

 the





ability

 to

 write

 an

 entire

 unique

 PhD





thesis





instantly,





which

 do

 we

 even

 have

 the

 amount

 of





compute

 in

 your

 mind

 to

 do

 something





like

 that

 today?

 If

 everybody

 got





together

 and

 said,

 hey,

 today

 we're





going

 to

 give

 all

 our

 compute

 for

 the





next

 hour,

 just

 as

 a

 thought

 experiment





to

 this

 incredible

 mega

 prompt,

 do

 you





think

 it

 would

 actually

 happen?

 Is

 it

 a





computer

 issue

 or

 is

 it

 a

 a

 model

 issue?
</details>

### AI 落地企业的现实挑战与上下文缺失

>> 嗯，其实现在的 AI 运行起来是比较慢的。我们必须做的是将它们并行化，部署很多个，并让它们互相协作。所以，其实并不完全是他写的那样。他在书中也提到了智能如何构成智能群落。但我只是说，各大实验室和很多其他公司目前都聚焦于此。这就是为什么他们痴迷于数学、克雷数学难题、七大千禧年难题等等。但我认为，我们面临的最大挑战是：我们到底如何把这种 AI 应用到组织内部？这就是 Databricks 所专注的方向。我们只想帮助所有这些组织。而当我出去和那些组织、企业交谈时——
<details><summary>Original English</summary>
>> Well,

 actually

 the

 the

 the

 AI's

 are

 kind





of

 slow.

 What

 we

 have

 to

 do is

 we

 have





to

 paralyze

 them

 and

 have

 many

 of

 them





and

 we

 have

 to

 have

 them

 to

 you

 know,





collaborate

 with

 each

 other.

 Uh

 so,

 it's





actually

 not

 the

 way

 kind

 of that

 he

 he





wrote

 it

 down.

 He

 had

 also

 intelligence





in

 the

 book

 of

 how

 it

 can

 be,

 you

 know,





communities

 of

 intelligence.

 But

 I'm





just

 saying

 the

 the

 the

 labs

 and

 many

 of





the

 other

 companies

 are

 focused

 on

 this.





And

 that's

 why

 they're

 obsessed

 with

 the





math

 the

 clay

 problems,

 the

 seven,

 you





know,

 millennial

 problems

 and

 so

 on.





But

 I

 argue

 that

 the

 biggest

 challenge





that's

 facing

 us

 is

 how

 do

 we

 actually





just

 make

 this

 AI

 applicable

 inside





organizations?

 That's

 what

 Databricks

 is





focused

 on.

 We

 just

 want

 to help

 all





these

 organizations.

 And

 when

 I

 go

 talk





to

 organizations

 out

 there,

 enterprises,
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 我看到他们对 AI 的使用其实非常初级。他们只是把它当作高级版的谷歌搜索。他们整天用聊天机器人。以前是输入谷歌搜索得到 10 个蓝色链接再去查看这些链接，现在 AI 只是帮他们把这步做了。他们做的第二件事是写代码。好吗？而在写代码上，其实他们并没有看到足够的提速，大概只看到了 20% 到 30%。我每天都问他们这个问题。我每天都和客户开会，并问他们这些问题。现实情况大致就是这样。我总是问他们：“你们当中有多少人拥有成千上万个智能体在到处运行，自动化所有工作并为你们处理核心业务等等？”这根本还没有发生。
<details><summary>Original English</summary>
>> I

 see

 that

 they're

 just

 using

 AI

 in

 very





rudimentary

 ways.

 They're

 just

 using

 it





as

 a

 glorified

 Google

 search.

 They're





using

 chatbots

 all

 day.

 And

 instead

 of





typing

 a

 Google

 search

 and

 getting

 10





blue

 links

 and

 then

 looking

 at

 the

 10





blue

 links,

 the

 AI

 just

 does

 that

 for





them.

 The

 second

 thing

 that

 they're





doing

 is

 they're

 doing

 coding.

 Okay?

 And





with

 the

 coding,

 actually

 they're

 not





seeing

 enough

 speed

 ups.

 They're

 seeing





maybe

 like

 20

 30

 %.

 I

 ask

 them

 this





question

 every

 day.

 I'm

 in

 meetings





every

 day

 with

 customers

 and

 I

 ask

 them





these

 questions.

 That's

 kind

 of what





reality

 looks

 like.

 I

 always

 ask

 them,





how

 many

 of

 you

 have,

 you

 know,





thousands

 of

 agents

 running

 around





automating

 all

 of

 work

 and

 doing

 core





work

 for

 you

 and

 so

 on?

 It's

 just

 not





happened

 yet.
</details>

>> 现在，他们可能在运行半打、一打智能体。前沿水平的人可能确实在协同调度这么多，但人类仍然需要参与其中（human-in-the-loop），就像 AMP 那样。仍然需要有人参与在里面，因为它会给出垃圾内容（slop），会给出怪异结果，可能会偏离轨道。现实中不可能有 1000 个智能体在处理事情。我说的对吗？
<details><summary>Original English</summary>
>> Now, they

 might

 be

 running

 a half

 dozen





agents,

 a

 dozen

 agents.

 Like

 somebody





who's

 at

 the

 forefront

 might

 actually

 be





coordinating

 against

 that

 many,

 but

 the





human

 still

 needs

 to

 be

 in

 the loop

 just





like

 amp.

 Like

 there's

 a

 person





who





still

 needs

 to

 be

 in

 there

 because

 it





will

 return

 slop,

 it will

 return





weirdness,

 it

 can

 go

 drift

 off

 course.





It's

 not

 possible

 to

 have

 1,000

 agents





doing

 stuff

 realistically.





Am

 I

 correct?
</details>

>> 对。有些走得更远一些。其实我们在整个 Databricks 内部都在普遍使用这个，我很乐意展示给你看。但现实是大部分企业并没有。这就引出一个你必须去问的问题：为什么会这样？如果它能解决纳维-斯托克斯（Navier-Stokes）方程这种极其困难的数学问题，为什么外面的企业和组织会落后这么多？
<details><summary>Original English</summary>
>> Yeah.

 Well,

 some

 are

 further

 along.

 I





mean,

 I'm

 actually

 using

 this

 all





throughout

 Databricks

 and

 I'm happy

 to





show

 you.

 But

 you

 know,

 the

 the

 the

 the





reality

 is

 that

 they're

 not.

 And

 the





question

 you have

 to

 ask

 the

 question,





why

 is

 that?

 Like

 if

 it

 can

 solve





Navier-Stokes

 very

 difficult

 math





problems,

 how

 come

 enterprises

 and





organizations

 out

 there

 are

 so

 far





behind?
</details>

>> 为什么会这样？对。
<details><summary>Original English</summary>
>> Why

 is

 that?

 Yeah.
</details>

>> 原因有很多，但最主要的原因，或者说看待它的一种视角是：如果我们能收集一家拥有 20 万名员工的大型组织内部的所有信息，录下所有会议——顺便说一句，光是这点，前几天一家大银行的 CEO 就告诉我：“不可能，我们绝不会录制会议，一百万年也不可能录。”但假设你拥有这些信息。

这是法律合规责任问题。顺便提一句，我当时就已经有点震惊了，因为如果你做不到这点，AI 怎么可能帮得上你？这就好比 AI 根本不在会议里。如果它不在会议里，它就毫无用处。就算你有陶哲轩，或者拥有世界上最伟大的数学家，如果他们被晾在外面、不知道你开会做出了什么决定、不知道你在做什么，而你在跟数十万员工开会沟通，那他们绝不可能帮得上你。所以如果你能捕获所有那些上下文，并且能够提供给 AI，他们就能精准解决这些问题。他们就能帮上——
<details><summary>Original English</summary>
>> Well,

 there

 there

 is

 well,

 there's

 many





reasons,

 but

 the

 main

 reason

 is

 or

 maybe





one

 way

 to

 look

 at

 it,

 if

 we

 could





gather

 all

 the

 information

 that

 you

 have





inside

 a large

 organization

 with

 200,000





employees,

 record

 all

 the

 meetings,





which

 by

 the

 way,

 that

 itself,

 one

 of





the big

 bank

 CEOs

 told

 me the

 other

 day,





no

 way.

 We're

 never

 recording

 the





meetings,

 like

 not

 in

 a million

 years.





But

 assume

 you

 have

 that.





Liability.

 I mean,

 by

 the way,

 which

 I





already

 I

 was

 already

 kind

 of

 shocked





because

 if

 you

 can't

 do

 that,

 how

 can





the

 AI

 ever

 help

 you?

 Like

 the

 AI

 is





simply

 not

 in

 the meeting.

 If

 it's

 not





in

 the meeting,

 it's

 useless.

 It

 doesn't





matter

 if

 you

 have

 Terry

 Tao

 or

 you

 have





greatest

 mathematician

 in

 the

 world,

 if





they're

 in

 the

 cold

 and

 they

 don't

 know





what

 decisions

 or what

 you're

 doing

 and





you're

 meeting

 with

 hundreds

 of





thousands

 of

 employees,

 there's

 no

 way





it

 can

 help

 you.

 So

 if

 you

 capture

 all





that

 context

 and

 you could

 feed

 it

 to





the

 AI,

 they

 would

 nail

 the problems.





They could

 help
</details>

<!-- chunk 3/9 -->

……现在就已经影响到我们了。嗯，所以这确实就是上下文问题。现在你可能会说好吧，那我们来把它搞清楚并付诸实施，我们 Databricks 也正在这样做，但这还不够。即使你做到了这一点，你还会面临第二个问题，那就是，你知道，你可以释放像 Open Claw 这样的东西，直接让它访问你各处的所有数据。那这样你就会陷入将要被黑客攻击的问题。网络安全是实实在在存在的问题，所有拥有成功业务的大型机构，眼下都非常害怕遭受攻击，对吧？这是个大问题。头号担忧。
<details><summary>Original English</summary>
 us

 right

 now

 already.

 Um





so

 that's

 really

 the

 the

 context





problem.

 Now

 you

 might

 say

 okay,

 well





let's

 figure

 that

 out

 and

 do

 that

 and





we're

 doing

 that

 at Databricks,

 but





that's

 not

 enough.





Even

 if

 you

 do

 that,

 you have

 a

 second





problem

 which

 is,

 you

 know,

 you

 could





unleash

 something

 like

 Open

 Claw

 and





just

 have

 it

 access

 all

 your

 data





everywhere.

 Well

 then

 you

 get

 into

 this





problem

 that

 you're going

 to

 get

 hacked.





Cyber

 is

 a

 real

 thing

 and

 all

 the

 big





organizations

 that

 have

 successful





businesses,

 they're

 really

 terrified





right

 now

 of

 getting

 attacked,

 right?





This

 is

 like

 a

 big

 concern.

 The top





concern.
</details>

>> 当你接纳这一点时，确实会产生很大的暴露面。我是说，如果是在小公司，一位 CEO 想要连接所有东西，那是特定大小的暴露面；但对于一个 20 万人的机构，哪怕 1 万人，天哪，暴露面直接扩大了 1000 倍。
<details><summary>Original English</summary>
>> certainly

 creates

 a

 lot

 of

 surface

 area





when

 you

 embrace

 this.

 I mean

 if

 a CEO





or

 in

 a small

 company

 you

 want

 to





connect

 everything,





it's

 a certain

 amount

 of

 surface

 area,





but

 for

 a

 200,000

 person

 organization,





10,000

 my

 lord,

 the

 surface

 area

 has

 now





gone

 1,000

 X.
</details>

### AI 落地面临的安全、成本与 IP 主权挑战

>> 是的，没错。所以这就是你碰到的第二个问题，就像是：好吧，我们能访问所有数据了。等等，我们也许不想对智能体开放所有这些访问，因为你知道，现在我们面临内部威胁，而且我们可能会被黑客攻击。那针对这个我们该怎么办？好吧，就算我们也解决了这个问题。现在我们解决了网络安全问题——顺便提一句，我们 Databricks 实际上有做这件事情的方法，很乐意向你展示。

然后你依然面临另一个问题，那就是：好了，现在 Token 成本正在呈指数级上升。如果 Token 成本在呈指数级增长，你公司的收入是在呈指数级增长吗？我不知道有哪家公司开始使用 AI 之后，由于使用了 AI，其收入便开始呈指数级加速并匹配上他们的成本曲线。

所以到头来，一开始 CEO 们会说“快去引入 AI，引入更多 AI，把它用起来，你知道的，我们需要在这上面动作更快”。
<details><summary>Original English</summary>
>> Yes,

 exactly.

 So

 that's

 like

 the

 second





problem

 you

 bump

 into

 which

 is

 like





okay,

 we

 can

 access

 all

 the

 data.

 Well





wait,

 we

 don't

 want

 to maybe

 access

 all





of it

 to

 the

 agents

 because

 you

 know,





now

 we

 have

 an

 insider

 threat

 and

 we





might

 get

 hacked.

 So

 what

 do

 we do

 about





that?

 Well

 let's

 say

 we

 solve

 that

 too.





So

 now

 we've

 solved

 the

 cyber

 problem





which

 by

 the

 way

 we

 have

 actually





ways

 to

 do

 that

 at

 Databricks,

 happy

 to





show

 you.





Then

 you

 still

 have

 another

 problem





which

 is

 okay,

 now

 the

 token

 cost

 is





going

 up

 exponentially.

 So

 if

 the

 token





cost

 is

 going

 up

 exponentially,

 is

 your





revenue

 at

 your

 company

 going

 up





exponentially?

 And

 I

 don't

 know

 any





company

 who

 started

 using

 AI

 and

 as

 of





their

 use

 of

 AI,

 their

 revenue

 started





accelerating

 exponentially

 matching





their

 cost

 curve.





So

 then

 eventually

 first

 of

 all

 CEOs

 are





like

 go

 get

 the

 AI,

 get

 more

 AI,

 get

 it





in

 there,

 you know,

 we need

 to move





faster

 with

 this.
</details>

>> 东西。是的。
<details><summary>Original English</summary>
>> thing.

 Yeah.
</details>

>> 没错。但随后在某个时间点，CFO 找上门来说：嘿，我们的运营支出在这里大幅上升，甚至连销售成本也是，我们对此打算怎么做？我们很快就要开业绩电话会了，接着他们就抓狂了。那么我们要如何解决这个问题？所以你还需要高效地做这件事，关于这点我们在 Databricks 同样有解决办法。

现在，你把这三件事都做完了，然后仍残留着最后一个战略性问题，就像是：行，好的。我们搞清楚了。我们访问了所有数据，做好了安全保障，并且你也知道，我们解决了成本状况。我们怎样才能避免被锁定，以及我们怎样才能拥有我们自己的 IP？因为你知道，不然的话，未来就无生意可做了，因为……
<details><summary>Original English</summary>
>> Exactly.

 But

 then

 at

 some

 point

 the

 CFO





shows

 up

 and

 says

 hey

 our

 OPEX

 is

 going





up

 significantly

 here

 and

 even

 the

 cogs,





what

 are

 we doing

 about

 it?

 And

 we have





an

 earnings

 call

 soon

 and

 then

 they





freak

 out.

 So

 then

 how

 do

 we

 fix

 that?





So

 you

 need

 to

 also

 do

 this

 efficiently





which

 we

 also

 have

 ways

 to

 do

 at





Databricks.





Now,

 you've

 done

 all

 of

 these

 three,





then

 there's

 a strategic

 last

 question





that

 still

 remains,

 which

 is

 like,

 okay,





fine.

 We

 figured

 it

 out.

 We

 accessed

 all





the

 data,

 we

 secured

 it,

 and

 you

 know,





we

 figured

 out

 the

 cost

 situation.

 How





do we

 avoid

 getting

 locked

 in

 and

 how

 do





we

 own

 our

 own

 IP

 because





you

 know,

 it's

 otherwise,

 you

 know,





there's

 no

 business

 to

 be

 made

 in

 the





future

 because
</details>

>> 你指的大概就是数据主权，智能主权。而且如果你使用 Anthropic、OpenAI 或任何这些平台，就存在这种风险：它会泄露，它会被整合进他们的下一个版本中。正如我们所见，一家名为 Anthropic 的公司似乎每两周就发布半打产品，眼下他们正与微软竞争——他们的一家……我认为微软算是他们的庞大合作伙伴之一。而他们刚刚推出了一款基本上是 Excel 杀手的产品。他们正在干掉 Photoshop。我的意思是，他们简直是在全面对所有人下手。
<details><summary>Original English</summary>
>> Data

 sovereignty

 is

 what

 you're

 kind

 of





referring

 to,

 intelligence

 sovereignty.





And

 if

 you

 use

 Anthropic,

 OpenAI,

 or any





of

 these

 platforms,

 there

 is

 this

 risk





that

 it

 will

 leak,

 that

 it

 will

 get





incorporated

 into

 their

 next

 version.





And

 as

 we've

 seen,

 a

 company

 called





Anthropic

 seems

 to

 be

 releasing

 every





two

 weeks

 a half

 dozen

 products

 that





just

 now

 they're

 competing

 against





Microsoft,

 one

 of

 their





I think

 Microsoft

 is

 like

 one

 of

 their





giant

 partners.

 And they

 just

 came

 out





with





uh an

 basically

 an

 Excel

 killer.

 They're





killing

 Photoshop.

 I mean,

 they're

 just





going

 after

 everybody

 wholesale.
</details>

>> 是的，所以这四个……是的。是的。顺便说一下，这些公司太不可思议了。他们正在做惊人的工作，没有他们，我们大概根本不会拥有这种智能。所以你知道，我很感激。这太棒了。我只是在指出，为什么当你环顾四周，所有这些成功的机构，所有的全球 2000 强、所有的财富 500 强、纳斯达克等等，为什么它们目前就只是美化版聊天机器人和一点点写代码？这就是原因。所以你确实需要把这四点全部解决掉。只有那样，你才能开始从中获得成效。
<details><summary>Original English</summary>
>> Yeah,

 so

 these

 four

 Yeah.

 Yeah.

 So

 by





the

 way,

 these

 companies

 are

 amazing.





They're

 doing

 amazing

 work

 and

 without





them

 we

 wouldn't

 even

 have

 this





intelligence

 probably.





So

 you

 know,

 I'm

 thankful.

 This

 is





awesome.

 I'm

 just

 pointing

 out

 why

 when





you

 look

 around

 you,

 all

 these,

 you





know,

 successful

 organizations,

 all

 the





Global

 2000,

 all

 the

 Fortune

 500s,





Nasdaq

 and

 so

 on,

 how

 come

 it's

 just





glorified

 chatbot

 and

 a

 little

 bit

 of





coding?





This

 is

 the

 reason.

 So

 you

 need

 to





really

 tackle

 all

 four

 of

 those.





And

 only

 then

 can

 you start

 getting





something

 out

 of it.
</details>

>> 而且我认为其中一个问题也是机构内部提出开创性想法的自主权。你知道，你可能已经占领了市场的很大一部分份额，你可能正在获得渐进式的收益。因此如果我告诉你，比如，嘿，我们可以给你的福特金牛座再增加 500 马力，那就像是：好吧，我的福特探险者现在多了 500 马力。它会把底盘扯烂的。这……这不行，这东西跑不到时速 500 英里。那么接下来就是，好吧，谁，谁来决定我们要再推出三条产品线？嗯，在 Databricks，有人在做决定。为什么我们不干脆去针对世界上每一门业务？而且他们开始做仪表盘了。这和你们的业务有点贴近，不是吗？在这边搞点仪表盘？
<details><summary>Original English</summary>
>> And

 one

 of

 those

 issues

 as

 well,





I

 believe

 is





the

 autonomy

 in

 an

 organization

 to

 come





up

 with

 a groundbreaking

 idea.

 You know,





you

 may

 have

 captured

 a large

 portion

 of





your

 market.

 You

 may

 be

 getting





incremental

 benefits.

 So

 if

 I

 tell

 you





like,

 hey,

 we

 can

 put

 another

 500





horsepower

 into

 your

 Ford

 Taurus,

 it's





like





okay,

 my

 Ford

 Explorer

 now

 has

 500

 extra





horsepower.

 It's

 going

 to

 rip

 the





chassis

 off.

 It's

 it's

 not

 This

 thing

 is





not

 capable

 of

 going

 500

 miles

 an

 hour.





So

 then

 it's,

 well,

 who,

 who

 decides





we're

 launching

 three

 more

 product





lines?

 Well,

 at

 Databricks,

 somebody

 is





deciding.





Why

 don't

 we

 just

 go

 after

 every

 single





business

 in the

 world?

 And they

 started





doing

 dashboards.





That's

 a

 little

 close

 to

 your

 business,





is

 it

 not?





A

 little

 dashboards

 over

 here?
</details>

### 数据治理与组织架构变革

>> 是的，关于仪表盘，你知道，我们不……我们没有针对仪表盘收费的产品。仪表盘通常由数据支撑，而且你通常希望那些数据是被治理的。所以你，你知道，你不会希望只有数字，然后你知道，那些数字是不准确的。在机构内部这是个大问题。所以这就回到了我说的第二点，治理和安全的层面，好吗？所以就像是，是的，也许我们能获得所有数据的访问权并拿到所有上下文，但我们必须确保它的安全。

所以是的，这很好。因此你实际上可以把所有这些外部智能体连接到 Databricks，但随后我们是受治理的数据仓库。接着当你访问那些数据，并且你知道，有了治理，我们按此收取用量费率。所以实际上这也是你看到我们业务加速的原因之一，因为所有这些公司，只要它们拥有智能体并且在使用它，那么我认为我们还只是处于开端。正如我所说，我依然认为它大部分是谷歌搜索和写代码，但当智能体开始使用它时，它们就，你知道的，向我们发送更多的查询。
<details><summary>Original English</summary>
>> Yeah,

 so

 dashboards,

 you know,

 we

 don't,





we

 don't,

 we

 don't

 have

 a

 product

 where





we charge

 for

 dashboards.





Dashboards

 are

 usually

 backed

 by

 data,





and

 you

 typically

 want

 that

 data

 to

 be





governed.

 So

 you,

 you

 know, you

 don't





want

 just

 numbers

 and

 then,

 you

 know,





those

 numbers

 are

 incorrect.

 This

 is

 a





big

 problem

 in

 organization.

 So

 that





gets

 back

 to

 the

 second

 thing

 I said,





the

 governance

 and

 security

 aspect,





okay?

 So

 like,

 yeah,

 maybe

 we

 can

 get





access

 to

 all

 the

 data

 and

 get

 all

 the





context,

 but

 we

 got

 to make

 it

 secure.





So

 yeah,

 it's

 great.

 So

 you can

 actually





connect

 all

 of these

 agents

 from

 outside





to

 Databricks,

 but

 then

 we

 are

 the





governed

 data

 repository.

 And then

 when





you

 access

 that

 data

 and

 you

 know,

 the





governance,

 we

 charge

 consumption

 rates





on

 that.

 So

 actually

 that's

 one

 of

 the





reasons

 you

 see

 acceleration

 of

 our





business

 because

 all

 these

 companies,





whenever

 they

 have

 agents

 and

 they're





using

 it,

 then

 I

 think

 we're

 just

 in the





beginning.

 As

 I said,

 I

 still

 think

 it's





mostly

 Google

 search

 encoding,

 but

 the





agents

 when

 they

 start

 using

 that,

 they





just,

 you

 know,

 send

 us

 more

 queries.
</details>

>> 当人们真正接纳智能体技术并开始与智能体一起工作时，行为会发生变化吗？比方说像你我这样，每天每个小时、每隔一个小时都在用？
<details><summary>Original English</summary>
>> behavior

 change

 when

 people

 actually





embrace





agentic

 technology

 and

 they

 start





working

 with

 agents,

 let's

 say

 every





hour,

 every

 other

 hour

 of

 the

 day

 like





you

 and

 I

 do?
</details>

>> 我认为机构、组织架构图是这样建立的。你知道，就像树状结构。顶部有一位 CEO，而在这些组织架构图中，所有决策都是某种自上而下和自下而上的。而且你有着所有这些老旧的流程，在一家企业或者任何有规模的机构内部，跨越这种组织架构图达成共识是非常、非常困难的。在邓巴数（即 150 人）以内还算比较容易。你能认识每个人。所以对于初创小团队，那是另一码事，但超过 150 人，这就成了一个协调问题。

但是，如果你看看任何机构实际上究竟是如何向其客户销售产品或服务的，其实并不是这种层级化的形态。它实际上横跨了那个组织架构图。你知道，就像在我们 Databricks 这里，我们有客户，他们给我们反馈。反馈流向产品管理部门。产品管理部门把它转交给工程部门。工程部门打造出产品，然后交给市场部门进行推广，你知道，接着市场部门把它交给销售部门，销售部门再次将其卖给客户。所以你其实想要横向贯通，因此你想要消除那种延迟，从而让你能够变得非常、非常快。

但这就要求你拥有一款真正理解你整个业务、你的 IP 的 AI。它需要理解你的组织架构图。它需要知道谁是谁，谁负责……
<details><summary>Original English</summary>
>> I

 think

 that

 the

 organization,

 the org





charts

 are

 built

 this

 way.

 You

 know,





there's

 like

 a

 tree

 structure.

 There's

 a





CEO

 at

 the

 top,

 and

 all

 decision

 making





goes

 kind

 of

 up

 and

 down

 in

 these

 org





charts.

 And

 you

 have

 all

 these

 old





processes,





and

 getting

 agreement

 across

 this

 org





chart

 is

 very,

 very

 hard

 inside

 of

 an





enterprise

 or

 inside

 of

 any

 organization





that's

 sizable.

 It's

 somewhat

 easy

 up





until

 Dunbar's

 number,

 which

 is

 150.





You

 can

 know

 everyone.

 So

 small





startups,

 it's

 a different

 story,

 but





above

 150,

 this

 becomes

 a coordination





problem.

 But

 if

 you look

 at

 how

 actually





any

 organization

 actually,

 you

 know,





sells

 a

 product

 or

 a service

 to

 its





customers,

 it's

 actually

 not

 this

 kind





of

 hierarchical

 thing.

 It

 actually

 cuts





across

 that

 org

 chart.

 You

 know,

 like





here

 at

 Databricks,

 we

 have

 customers,





they

 give

 us

 feedback.

 Feedback

 goes

 to





product

 management

 organization.

 Product





management

 hands

 it to

 engineering





organization.

 Engineering

 builds





products

 that

 goes

 to marketing

 that





markets

 it,

 you

 know,

 and then

 marketing





gives

 it

 to

 sales

 that

 sells

 it

 to





customers

 again.

 So

 you

 kind

 of

 want

 to





go

 across

 so

 you

 want

 to

 cut

 out

 that





latency

 so

 that

 you

 can

 be

 really

 really





fast.





But

 that

 requires

 that

 you have

 an

 AI





that

 actually

 understands

 your

 whole





business,

 your

 IP.

 It

 needs

 to





understand

 your

 org

 chart.





It

 needs

 to

 know

 know

 who's

 who,

 who's





responsible

 for
</details>

>> 你觉得有多少公司真正理解了你刚才所描述的？10% 的机构理解了这个？5%？
<details><summary>Original English</summary>
>> companies

 actually

 understand

 what

 you





just

 described,

 would

 you say?

 10%

 of





organizations

 understand

 this?

 5%?
</details>

>> 在规模化层面上，我不知道有多少。这个我不知道答案。在规模化层面上，我知道 Databricks 正在这么做。我正在这么做。
<details><summary>Original English</summary>
>> At

 scale,





I

 don't

 know

 how

 many.

 I don't

 know

 the





answer

 to

 that.

 At

 scale,

 I

 know

 that





Databricks

 is

 doing

 it.

 I'm

 doing

 it.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 实话说，我还没看到其他人以这种……你知道……做成这样。我认为大概有由杰克·多西（Jack Dorsey）领导的 Block 和 Square，因为他正在推进——他把它称为公司世界模型。他称之为……我认为跟我描述的大体是同一件事，你知道，不同的看待视角。他把它称为公司世界模型。所以我认为他们大概相当领先。

总的来说，我认为数字原生企业大概更领先。数字原生企业是指那些仅成立了 10 到 15 年的公司。你知道，如果你已经存在了 20、30、40、50 年，这本身就意味着你是一家了不起的公司。也许你是财富 500 强，全美最好的公司。你可能有 10 万名员工。你知道，他们忠诚；你知道，他们热爱你们的产品；而且你知道……但你们在自身业务上是世界上最优秀的。你们只是拥有太多的软件了。你知道，你们面临着如此多的监管，并且围绕安全等等有着如此多的流程，以至于它……
<details><summary>Original English</summary>
>> I

 haven't

 seen

 anyone

 else

 to

 be

 honest





do

 it

 at

 at

 this

 kind

 of





you know,





I

 think

 probably

 Block

 and

 Square

 with





Jack

 Dorsey

 since

 he's

 pushing

 he

 he's





calling

 it

 the

 company

 world

 model.

 He





calls

 the

 same

 thing

 I

 kind

 of

 described





I

 think,

 you

 know,





different

 way

 of

 viewing

 it.

 He's





calling

 it

 the

 company

 world

 model.

 So

 I





think

 that

 they're

 probably

 pretty

 far





ahead.

 In

 general,

 I think

 digital





natives

 are

 probably

 further

 ahead.





Digital

 natives

 being

 companies

 that





have

 only

 existed

 10

 15

 years.

 You

 know,





if

 you've

 been

 around

 20

 30

 40

 50

 years,





which

 just

 means

 you're

 an

 amazing





company.

 Maybe

 you're

 a

 Fortune

 500,

 the





best

 companies

 in United

 States.

 You





have

 maybe

 100,000

 employees.





You

 know,

 they're

 loyal.

 You

 know,

 they





love

 your

 products

 and

 you

 know

 but





you're

 the

 best

 in

 the

 world

 on

 that.





You're

 just

 you

 have

 so

 much

 software.





You

 know,

 you

 have

 so

 much

 regulation





and you

 have

 so

 many

 processes

 around





security

 and

 so

 on

 that

 it's
</details>

<!-- chunk 4/9 -->

对你们来说，采用这项技术会非常困难。但这恰恰是 Databricks 想要为他们解决的问题。所以我们希望，我们希望他们能采用这些技术，从而让 AI……从而让他们基本上能做到我在 Databricks 所做的事情。
<details><summary>Original English</summary>
very hard for you to adopt this. But that is the very problem Databricks wants to solve for them. So we want it we want them to adopt the technologies so that the AI so that they can do what what I do at Databricks basically.
</details>

>> 是的，让我们看看吧。你说过你愿意向我们展示一下你是如何用智能体和 AI 来管理 Databricks 的。我整天都在期待这个，因为在你调出界面的同时，我确实正在将我播客制作和早期投资的整个生活……我把这些事情的各个组成部分看作一项项服务、一个个智能体，并且去定义目标，然后倒推：朝着目标迈进的成功迹象有哪些，而不是你已经达成了目标。达成目标有点非黑即白，是或否。你做成了这笔销售，或者没做成。但前置的先兆信号是什么？然后尝试让这些机器人之间来回交接任务。这……
<details><summary>Original English</summary>
>> Yeah, let's see it. You said you would be willing to show us like how you run Databricks with agents and and with AI and I I'm been looking forward to this all day because I I literally am taking the entire while you queue it up my entire life on podcasting and on early stage investing and I'm looking at each of the components of those things as services, as agents, and defining the goal, working backwards to what are the signs of success that you're heading towards the goal, not that you've achieved the goal. The achieving the goal is kind of binary, yes or no. You made the sale, you didn't. But what are the precursor signals? And then trying to have each of these bots hand off things back and forth. It's
</details>

>> 对。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你必须是一个真正的系统思考者。这有点像一边骑马一边同时下五盘国际象棋。我的意思是，你……从智力上来说，我真的觉得这超级令人兴奋。我能看出来你也这么觉得。所以这里你可以共享屏幕了，然后……
<details><summary>Original English</summary>
>> you have to be a real systems thinker. It's like kind of playing five chess games at once while riding a horse. I mean, you're it's really like intellectually I find it super stimulating. I I can tell you do, too. So here you can share your screen and
</details>

### Genie 与企业本体图谱

>> 那我们就直接切入吧。好的。这里关键的一点是，我们有一款名为 Genie 的产品，但 Genie 具备的关键之处在于——因为你知道，市面上有那么多聊天机器人，有那么多助手，市面上有那么多协同工作产品以及后台智能体——最关键的是它拥有一个本体库（ontology）。
<details><summary>Original English</summary>
>> So let's jump in. So okay. So the key thing here is that we have a product called Genie, but the key thing that Genie has cuz you know, there's so many chatbots out there and there's so many assistants and there's so many co-work products out there and agents in the background. The key thing is that it has an ontology.
</details>

这个本体库是它不断为你的公司构建的一张图谱。这张图谱理解所有人：谁向谁汇报，他们在从事什么工作，收进来的邮件有哪些，开过了什么会议，所有那些会议的文字记录是什么，会上做出了哪些决定，Slack 上有什么内容，正在沟通交流什么。
<details><summary>Original English</summary>
The ontology is a graphs that it constantly it's constructing for your company. That graph understands all of the people, who reports to who, what are they working on, what are the emails that are coming in, what meetings have happened, and what's the transcripts of all those meetings and all the decisions that are being made there, what's on Slack, what's being communicated.
</details>

所以它能访问所有这些内容，此外还能访问你正在创建的所有文档、所有的 Excel 表格、所有的 PowerPoint 演示文稿。所以它能访问所有这些。这就是我们这里所称的 Genie，正如你在屏幕上所看到的。我早上醒来，你知道，我有……它有一个收件箱。早上当我到岗时，它基本上已经为我完成了大量后台工作。它是 7×24 小时运行的。如你所见，它能访问我的日程表。事实上，我可以随口问它，比如：
<details><summary>Original English</summary>
So it it has access to all of these things and then also all of the docs that you're creating, all the Excel sheets, all the PowerPoint presentations. So it has access to all of those. That's what we call Genie here so that you can see here. So I wake up, it you know, I have an it has an inbox. In the morning when I come in, it basically has done a bunch of background work for me. It's running 24/7. As you can see, it has access to my you know, calendar. In fact, I could just ask it like you know,
</details>

>> “我今天在 All-In 节目上跟 Jason 讲了什么？”你看它开始运作了。
<details><summary>Original English</summary>
>> What did I tell Jason on all in today? Here it goes.
</details>

### 员工调研分析：相关性与因果性

>> 马上就能看到它会说什么了。不过我们来看看我做过的一些事情。其实前几天有件很有意思的事，我当时在看我们人力资源部门给出的反馈，他们说：“嘿，我们对整个 Databricks 做了一次调研。”你知道，我们有超过 10,000 名员工对这次调研提交了回复。我查看了结果，HR 负责人在梳理结果，我说：“帮我针对这些结果做一个仪表板。”目前这里还没有什么神奇之处。然后它告诉我：“看，目前的表现是这样的。你在某些方面表现优异，但是……”
<details><summary>Original English</summary>
>> So you see what this is going to say. But let's look at some of the stuff that I've done. So like actually the other day, one of the interesting things is I was looking at our HR department came back and they were saying, hey, we've done survey on all of DataBricks. You know, so we had over 10,000 people, employees that responded to the survey. And you know, I looked at the results and she was going through it and you know, I said, hey, make me a dashboard of the results. Uh, you know, nothing magical here yet. So it told me like, look, here's how you're doing. You're doing great on some things, but you know
</details>

>> “高管领导力，88%。”你们做得挺不错的。
<details><summary>Original English</summary>
>> Executive leadership, 88%. You're doing okay.
</details>

>> 是啊，你知道……
<details><summary>Original English</summary>
>> Yeah. You know, it's
</details>

>> 工作生活融合度，60%，看来你们那边把员工逼得挺紧的。不过我的意思是，大家都会这么说，对吧？
<details><summary>Original English</summary>
>> blend, 60% that you're working people pretty hard over there. But I mean, everybody says that, right?
</details>

>> 没错。并不是……但我们想了解……但这一项一直是……所以我们希望能提升这两项。而“采取行动”（action）这一项真的让我很困扰，因为，你知道，所谓 Action，顺便提一下，它的含义是指当我们向他们征集反馈时，他们向我们提供了反馈，比如改进这个、改进那个，而他们觉得管理层根本没有在听他们的意见。
<details><summary>Original English</summary>
>> Yeah. No, but we want to know but this is this has been So we want we wanted to improve these two. And this action one really bothers me because um you know, it's Action, by the way, it means that when we we ask them for feedback, they give us feedback, improve this and that. And they feel like you're you're not listening to us.
</details>

>> 呃，这么说来，三分之二的人觉得你们在听，三分之一的人觉得你们没在听。顺便说一句，你们表现还可以，不算太差。这数据完全有可能是 30%。
<details><summary>Original English</summary>
>> Uh, so two out of three feel you are. One out of three feels you're not. Just to You're doing okay. It's not terrible, by the way. This could be like 30%.
</details>

>> 60% 可算不上好。而且，特别是如果你考虑到每年这个数据都很低，而每年我都向全公司承诺我们要解决这个问题，但每年都没能兑现。所以，我们在过这些结果，并在与管理团队讨论。当他们在讨论时，大家都在猜测。我的首席财务官说：“我认为这是因为工作与生活的融合问题。工作与生活的融合很糟糕，导致了 Action 指标下滑。”也就是说，工作生活融合度差导致了 Action 得分低。我当时的反应是，这根本说不通啊。不过在讨论的同时，我直接把它输入到了这里，系统立刻调出了结果：“好的，这是这两者之间的相关性。情况是这样呈现的。”接着我想，好吧，哇，也许他是对的。但随后系统显示：不，实际上它们之间不存在因果关系，并不是它导致的。这里有确凿的论据。我们可能需要把这些人的姓名匿名化，但这里有一位管理者，其团队的工作生活融合度只有 44，相当糟糕；但 Action 得分却高达 77%。所以，你看……
<details><summary>Original English</summary>
>> 60% is not great. So but and especially not great if you actually take into account that every year it's low, and every year I promise the company we're going to fix this, and every year it doesn't happen. So, you know, we're going through the results, and you know, we're discussing it with the staff, and while they're discussing it, they're speculating. Um, you know, my CFO says um you know, hey, I think it's because of work-life blend. Work-life blend is bad, you know, and that's causing action to go down. So it's causing Work-life blend is causing low action. And I was like, that doesn't make any sense. Uh, but I just entered it here immediately as we were discussing, and it immediately pulled up. Okay, this is the correlation between these two. And this is how it's looking. But then I was like, okay, wow, maybe he's right. But then it says, no, actually it's not causal. It's not causing it. And here's the exact proof point. We probably have to anonymize these folks, but it's a Here's a manager that has work-life blend 44. That's pretty bad. Action is 77%. Uh, so you know,
</details>

>> 员工工作很辛苦，而他在认可员工的关切并采取行动解决。所以……
<details><summary>Original English</summary>
>> They're working hard, and he's recognizing and taking action on their concerns. So
</details>

### 下钻部门反馈与组织架构洞察

>> 所以当时我就说，这才是你要找的人。他严格要求大家，同时也倾听大家的声音。我喜欢他身上的这一点。于是我说，好吧，现在我正在逐步了解这个组织的情况。这太棒了。如果让数据团队为我做这种分析，本来得花上大概一周时间，但这只是我获取信息的过程。这很有用。我们算是在一定程度上缩短了整个组织架构上下传达的延迟。但我接着想，好吧，那为什么这项指标会低呢？于是让它梳理所有的评论。它给出了一些原因。我对那些原因并不满意。于是我进一步明确了问题，我说：“你能帮我按部门进行切片分析吗？”
<details><summary>Original English</summary>
>> So then I said, that's your guy right there. He's pushing people hard, and he's listening to them. I like that about him. So I said, okay, so now I'm learning stuff about the organization. This is amazing. It would have taken me like a week to get the data team to do this analysis for me, but that's just me getting information. That's useful. So like we're cutting this, you know, latencies up and down the org chart a little bit. But then I'm like, okay, why is it low? And look through all of the comments. And it gives me some reasons. I didn't like the reasons. So then I actually clarified the question and I said, hey, can you slice it by department for me?
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mm.
</details>

>> 然后它真的梳理出来了。它指出：产品管理部门的 Action 得分低，是因为他们不喜欢决策制定过程，认为利益相关者太多、太多了。工程部门则是不喜欢当前的工具和系统，觉得负担太重。销售运营部门反映的是职业发展等等。所以……
<details><summary>Original English</summary>
>> you know, and then actually figured it out. It said, look, product management has low action because they don't like decision making is too too too many too many stakeholders. Engineering, they don't like the tools and systems. There's too much. You know, sales operations is career growth and so on and so forth. So
</details>

>> 这很合情合理，因为销售人员总觉得自己应该升职，毕竟他们是销售，而且他们的佣金也该提高；[笑声] 而产品人员则认为公司只要听他们的就行了……
<details><summary>Original English</summary>
>> That makes sense because sales people always think they should get a promotion because they're sales people and they should get their commissions raised. [laughter] And product people think you should just listen to them
</details>

>> 没错。
<details><summary>Original English</summary>
>> Exactly.
</details>

>> ……而不是让六个人一起去试图设计一件艺术品。有了数据和 AI，这一切现在都对得上号了。我很喜欢。
<details><summary>Original English</summary>
>> of, you know, six people trying to design a piece of art. This all starts to track now with the data and the AI. I love it.
</details>

>> 是的。那么它是如何做到这一点的？它能访问自己的本体库。所以它并不仅仅是去实时搜索。它实际上发现自己的图谱中早已经存在这些人了。已经有五个人为这个内容贡献过信息，而且你可以在这里看到它实际利用的 19 条信息，这些都是它此前就已经掌握的。它没有去进行实时检索，这些都存在于本体库中。例如，我们可以看看这一个特定的条目。如果你点击它，它包含一个定义，这是一项指标，并且有一张图表。这张图表你可以在这里看到。这里有一个满意度指标，它来源于……这是创建者。你可以点击创建者，因为系统理解组织架构图，它们理解这个人是谁。这个人名下其实有 29 个代码或文本片段。他们拥有大量不同的资产，是系统从他们那里学习掌握的。所以它在不断学习掌握你企业的智能或本体信息。所以这是一个很典型的场景。这里还有另一个例子，可能也很有意思。我想了解……实际上在过去 59 分钟内这里有了新的结果。这些我其实还没有全部看过来，但我想要了解组织架构图，了解组织架构的现状以及管理跨度。我去问它，它开箱即用的分析结果着实让我震惊。邮件告诉我，说 Databricks 内部有一个层级非常深的组织。这个人向这个人汇报，这个人又向这个人汇报，再向这个人汇报，但他们分别只有三个人向其汇报、五个人向其汇报、四个人向其汇报、五个人向其汇报。这可不是一个扁平化的组织。那么你就可以研究，好的，对此我们能做些什么？同样，因为它理解所有人，所以它开箱就能立刻理解他们。工程部门的成本，你知道，成本是我们……
<details><summary>Original English</summary>
>> Yeah. So how did it do this? It has access to its ontology. So it's not going and searching live only. It actually found that there's already already had in its graph these people. You know, already five people had already contributed to this and there's 19 pieces of information here that you can see that it's actually leveraging that it already had. It didn't search for them live. These are in the ontology. So we can look at, for instance, this particular one. If you click on it, it has a definition, it's a metric, and there's a graph. And this graph you can see it here. You know, so there's a favorability and it came from, you know, this is the author. You can click on the author and because it understands the org charts, they understand who this person is. This person actually has 29 snippets. You know, they have lots of different assets, you know, that they've you know, that it's learned from them. So this constantly is learning the intelligence or ontology of your organization. So that's a that's a, you know, typical thing. Here's another one that, you know, is maybe interesting. I wanted to know actually there's new results here in the last 59 minutes. I haven't actually looked at all of those, but I wanted to understand the org chart and what's going on with the org chart and, you know, span of control. And I ask it and already out of the box it was actually it's I was shocked by this. The email told me like, hey, there is an org inside DataBricks, which is very deep. You know, this person reports to this person reports to this person reports to this person, but they have three people reporting to them, five people reporting to them, four people reporting to them, five people reporting to them. So, that's not a flat organization, you know? So then you can look at, okay, what can we do about that? Again, it understands, since it understands all the people, it can immediately out of the box understand them. Engineering, you know, cost. Cost is, you know, something that we
</details>

<!-- chunk 5/9 -->

完全不去看。你知道，所以这也是我们想看看能否弄清楚的另一件事。
<details><summary>Original English</summary>
 look

 at

 at





all.





And,

 you

 know,

 so

 that's

 that's

 another





thing

 we

 wanted

 to

 see

 if

 we

 could





understand.
</details>

>> 而且这样做的好处还在于，作为领导者，你不用再说“嘿，听着，如果有意见分歧，就按我的来”，而是创造了一个让大家以数据为先、去验证理论的平台。大家不必偏执于究竟是谁提出了某个理论，只要保持求知欲并对各种可能性保持开放态度即可。

最终，如果这就是我们今天的水平，你能想象一两年后会是怎样吗？到那时，它不再只是通过一份企业文化报告来呈现，而会像安装在公司里的温度计一样。就像你查看公司里的恒温器，然后发现“哇，今天温度好像有点高，怎么回事？”然后发现“哦对，我们这个周末让员工来加班了，可能我们该给大伙买点披萨，或者感恩节期间给大家放一天调休假”。
<details><summary>Original English</summary>
>> And

 what's

 great

 about

 this

 too

 is





instead

 of

 you

 as

 the

 leader





saying,

 hey,

 listen,

 if

 we're

 going

 to





have

 an

 opinion,

 let's

 go

 with

 mine,





you've

 now

 created

 a

 forum





where

 people

 can

 be

 data

 first,

 test





theories,

 and

 you

 don't

 have

 to

 be





dogmatic

 about

 who

 came

 up

 with

 the





theory.

 You

 just

 have

 to

 be





intellectually

 curious

 and

 open

 to





possibilities.





And

 eventually,

 if

 this

 is

 where

 we

 are





today,

 can

 you

 imagine

 like

 in

 a

 year

 or





two,





it's

 going

 to

 just





be

 giving

 you

 these

 instead

 of

 through

 a





culture

 report,

 it's

 going

 to be

 like

 a





a

 temperature

 gauge

 in

 your

 company.





It's

 just

 like

 you're going

 to

 be





looking

 at

 the

 nest

 in

 your

 company

 and





it's

 like,

 oh

 wow,

 looks

 a little

 hot





today.

 What's

 going

 on?

 And

 it's

 like,





oh

 yeah,

 we

 we

 made

 people

 come

 in

 this





weekend

 and

 yeah,

 maybe

 we

 should

 buy





some

 pizzas

 or

 give

 people

 a

 comp

 day





during

 Thanksgiving.
</details>

### 研发效能的 L 型分布与成本控制

>> 是的，这是我最喜欢的一个。这个其实是出自 Genie。这里展示的是我们的 2000 名工程师，以及他们实际提交并上线到生产环境的代码合并请求（pull request）或代码量。你看中间这里，大概是每周的数据。但它呈现出一种 L 型分布，你看这个 L 型，排名最靠前的人实际提交的代码量要高出非常多。
<details><summary>Original English</summary>
>> Yeah,

 this

 is my

 favorite.

 So

 so

 this





one

 actually

 is

 came

 out

 of

 Genie.

 So





this

 is

 our

 2,000

 engineers

 and

 this

 is





how

 many

 pull

 requests

 or

 how

 much

 code





they've

 actually

 shipped

 into





production.

 Can

 you

 look

 at the

 middle





here,

 it's

 maybe

 per

 week

 roughly.

 But





it

 has

 this

 L

 shape,

 you know?

 And you





look

 at

 this

 L

 shape,





you

 know,

 the

 top

 people

 are

 actually





committing

 way

 more.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 到底是怎么回事？到底发生了什么？我们深入调查后发现，原来他们在运行自动化流水线，而其他人没有。所以我们去推动其他人。顺便提一句，我当时还问了一个很有意思的问题：“嘿，能把成本加进去吗？在这条线上加上成本。”我们发现的一个很有意思的现象是，那些人的成本并不一定更高。你看最前面的这些人。
<details><summary>Original English</summary>
>> You

 know,

 so

 what's

 going

 on?

 Yeah,

 so





what

 the

 hell

 is

 going

 on?

 So

 we

 looked





into

 this

 and

 it turns

 out

 they're





running

 automated

 factories,

 the

 rest





are not.

 So

 we

 push

 them

 and

 actually,





by

 the

 way,

 interesting

 thing

 I

 asked





is,

 hey,

 can

 you

 like

 add

 cost

 to

 this,





add

 the

 cost

 to

 this

 line?

 And one

 of





the interesting

 things

 we found

 is

 that





it's

 not

 even

 the

 case

 that

 cost





necessarily

 is

 higher

 for

 those

 people.





So

 look

 here

 at

 the

 top.
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mm.
</details>

>> 排在最前列的人当中，有些人的花销其实并没有其他人那么多。顺便说一句，这就又回到了那个问题——其实有更聪明的方法来消耗 token。你可以使用开源模型，可以把更简单的问题路由给更简单的模型，我们其实就有这样一款产品。你可以大幅降低成本。

这就是这类事情。顺便提一下，把会议录下来也非常重要。比如，我听说了某场客户会议，想了解那个会议的情况。我就直接问它：“嘿，最近有和这位客户开会吗？情况怎么样？”它开篇就直接说那次会议开得很糟。
<details><summary>Original English</summary>
>> The

 top

 folks,

 some

 of

 them

 are

 actually





not

 spending

 as

 much

 as

 some

 of the





other

 folks.

 So

 which,

 by

 the

 way,

 goes





back

 to

 there

 is

 a

 way

 to

 spend

 tokens





in

 a smart

 way.





You

 can

 use

 open

 source,

 you

 can

 route





simpler

 questions

 to

 simpler

 models,

 and





we actually

 have

 a product

 for

 this.

 Uh,





and

 you can

 cut

 your

 costs

 down





significantly.

 Um,

 so

 this

 is

 the

 kind





of

 stuff.

 By

 the

 way,

 it's

 it

 also





recording

 the

 meetings

 is

 really





important.

 So,

 um,

 you know,

 one

 of the





things

 I

 heard

 that

 there

 was a

 customer





meeting,

 and

 I wanted

 to understand

 how





that

 product

 uh





how

 that

 meeting

 went.

 And,

 you

 know,

 uh





and

 I

 just

 asked

 it,

 you

 know,

 hey,

 was





there

 a

 meeting

 with

 this

 customer





recently?

 How

 did

 it

 go?

 And

 it





literally

 started

 by

 saying

 the

 meeting





went

 poorly.
</details>

>> 噢。
<details><summary>Original English</summary>
>> Ooh.
</details>

>> 然后它逐一列出具体谁说了什么，他们需要哪些功能。所以，这就是利用 AI 可以做的一些事情。而且，在后台，当我醒来时，它已经为我做好了所有这些深度分析。我不用一醒来就给别人打电话、开会，它已经把工作替我做了，在替我向他们发消息核实，为公司发送所需的任何材料。它直接压缩了完成各项事务所需要的时间。
<details><summary>Original English</summary>
>> And it

 list

 and

 it

 listing

 exactly

 what,





who

 said

 what,

 what

 are the

 features





they

 need.

 Uh,

 so,

 you

 know,

 um,

 these





are

 just

 some

 of the

 things

 that

 you can





do,

 you

 know,

 with

 the

 AI.

 And

 you know,





in

 the

 background

 it'll

 when

 I wake

 up,





it

 has

 all

 these

 deep

 dives

 for

 me.

 So





instead

 of

 waking

 up,

 calling

 people,





doing

 meetings,

 it's

 doing

 the

 work

 for





me.

 It's

 pinging

 them.

 It's,

 you

 know,





sending

 uh you

 know,

 whatever

 material





is

 needed

 for

 the

 company.

 So

 it

 just





compresses

 the

 time

 it takes

 to

 do





things.

 Uh,
</details>

### 管理中的“侦探工作”与客观事实

>> 但你知道，做管理、当创始人，很大程度上是在破案。我管它叫当神探可伦坡（Colombo），如果你还记得那部电视剧的话。我觉得这可能暴露了我们的年龄，但你就像是在说：“哦，对了，还有一件事。能跟我说说那场会议、客户会议吗？情况怎么样？电话里谁讲得最多？他们讲了多大比例的时间？客户到底是怎么想的？”然后，作为创始人的你就会被员工灌迷魂汤。

你会被粉饰过的话糊弄。这并不是说员工一定存心想糊弄你。团队成员倒不一定是冲着粉饰太平来的，这种事会有，但不是绝大多数情况。大多数人都是好人。
<details><summary>Original English</summary>
>> But

 you know,

 it's

 a

 lot

 of

 being

 in





management

 and

 being

 a founder

 is





detective

 work.

 I

 call

 it

 like

 being





Colombo,

 if

 you

 remember

 that

 TV

 show.

 I





think

 it

 might

 show

 our

 age,

 but

 you're





kind

 of

 like,

 oh,

 you

 know,

 it's

 one





more

 thing

 there.

 Can

 you

 tell

 me

 about





the

 meeting,

 the

 client

 meeting?

 How

 did





that

 go?

 And

 who

 talked

 most

 on

 the





phone?

 And

 how

 what

 percentage

 of

 time





did

 they

 talk?

 And

 what

 did

 the

 customer





actually

 think?

 And

 then

 you

 as

 the





founder

 are

 getting

 spun.





You're getting

 spun.

 And

 it's

 it's

 not





that

 an

 employee

 necessarily

 wants

 to





spin

 you.

 A

 team

 member

 is

 not

 looking





to

 spin

 you

 necessarily.

 That

 can





happen,

 but

 that's

 not

 the

 majority.





Most

 people

 are

 good

 people.
</details>

>> 是的。是的。
<details><summary>Original English</summary>
>> Yeah.





Yeah.
</details>

>> 他们只是凡人，对吧？他们是置身放大器中的人。
<details><summary>Original English</summary>
>> they

 have

 they're

 humans,

 right?

 They're





the

 people

 in

 the

 amp.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而在这里，你把人为因素从讨论中抽离出来，摆出第一性原理、透明地呈现到底发生了什么。现在我们有了基本事实，就可以直接展开讨论，CEO 也不必再充当大侦探了。而且，两年前如果花两个小时去破案，那种挫败感不用我说你也能体会。你开了三次会之后，心想如果大家直接把实际情况告诉你，或者如果你手头有那份企业文化报告，问题早就解决了，也就不用经历连续三周的焦虑不安了，对吧？
<details><summary>Original English</summary>
>> And

 here

 you

 take

 the

 people

 out

 of

 that





discussion

 and

 you say,

 here's

 first





principles,

 transparently,

 what





happened.

 Now

 we

 have

 ground

 truth,

 and





we can

 start

 the discussion

 without

 you





being

 the

 CEO

 having

 to

 be

 Mr.





Detective.

 And

 you

 know,

 it

 is





so

 I mean,

 I don't

 know

 about

 how





frustrating

 it

 it

 was

 for

 you

 two

 years





ago

 to

 spend

 two

 hours

 being

 a





detective.





You

 get

 three

 meetings

 into

 this,

 and





it's

 like

 if

 people

 had

 just

 told

 you





what

 happened

 or

 if

 you had

 that

 report





on

 culture,

 the problem

 would

 have been





solved.

 You

 wouldn't

 have

 had

 three





weeks





of hand-wringing,

 yeah?
</details>

### 自动化产品反馈与减少组织阻碍

>> 确实是这样，还有客户反馈也是一样，对吧？我可以立即查清所有客户的情况。有些情况下，我不仅让它自动从我们所有客户会议的逐字稿中提取所有客户请求的功能，收集整理之后直接提交给工程团队，而且我们工程部门还有自动化流水线可以直接构建这些功能。

所以这彻底改变了规则。就像我们小时候玩过的传话游戏，对吧？当人们必须开会传达时，信息就会失真。所以我们的主要目标之一就是减少人为造成的阻碍（human blockers）。我们在整个组织中对此进行衡量并保持观察。
<details><summary>Original English</summary>
>> Yeah,

 I mean,





or

 the customer

 feedback,

 right?

 That

 I





can

 immediately

 find

 out

 all

 the





customers

 I,

 you

 know,

 I have

 some

 some





of them

 where

 I'm

 not

 just

 having

 it





look

 at

 features

 that

 are

 requested

 from





all

 of

 our customers

 automatically

 from





all

 the

 transcripts

 of

 all

 the

 customer





meetings

 that

 we

 have.

 And

 it's

 just





gathering

 those

 and

 they're

 immediately





going

 to

 engineering,

 and

 then

 we

 have





factories

 in

 engineering

 that

 can

 build





features

 automatically.





Uh so

 it's

 a

 game

 changer.

 You

 know,





it's

 just

 that

 game

 of

 whispers

 that

 we





played

 when

 we

 were

 kids,

 right?

 It's





like

 when

 you have

 people

 have

 to

 meet,





they

 have

 to

 tell.

 So

 one

 of

 our

 main





goals

 is

 uh

 reduce

 number

 of human





blockers.

 So

 we

 measure

 that

 throughout





the

 organization

 and

 we

 just

 see,

 you





know.
</details>

>> 请解释一下在这种语境下的阻碍（blocker）。这个我可以学习借鉴一下。
<details><summary>Original English</summary>
>> explain

 a blocker

 in

 this

 context,





please.

 This

 is

 something

 I

 can

 learn





from.
</details>

>> 是这样的，AI 的速度非常快，对吧？它在后台不断迭代、推进工作、准备材料等等。但在某个时刻，情况就变成了：“好的，现在我们得去找法务，确认我们是否被允许做这件事；或者现在我们得去找财务，拿到这笔预算的批准；或者现在我们得确认市场部门对这个方案没有异议；甚至只是在同一个大部门内部，我们得去找兄弟团队，跟他们开个会听听他们的想法，并且必须达成一致。如果达不成一致，我们就再安排一次会议重新讨论。如果那次会议还是不行，可能就得升级上报给管理者，以此类推。”所以这些就是拖慢整个组织速度的阻碍。
<details><summary>Original English</summary>
>> Yeah,

 I

 mean

 the

 AI

 is

 very

 fast,

 right?





It's

 just

 iterating

 in

 the

 background





and

 it's

 doing

 its

 work

 and,

 you know,





it's

 preparing

 material

 and so

 on.

 But





at

 some

 point

 it's

 like,

 okay,

 well

 now





we

 need

 to

 go

 to

 legal

 and make

 sure





that

 we

 are

 allowed

 to

 do

 this

 thing.

 Or





now

 we

 need

 to

 go

 to

 um

 you

 know,





finance

 to get

 approval

 for

 this

 budget.





Or

 now

 we

 need

 to

 make

 sure

 that





marketing

 is

 okay

 with

 the





uh

 with

 this.

 Or

 actually

 just

 within





the

 same

 organization

 we

 need

 to

 talk

 to





a

 sibling

 organization,

 get

 a meeting





with

 them

 and

 see what

 they

 think

 and

 we





have to

 get

 an

 agreement.

 And

 if

 we





can't

 reach

 an agreement

 we'll

 schedule





another

 meeting

 where

 we

 look

 at

 this





again.

 And

 then if

 that

 meeting

 doesn't





work

 maybe

 we

 escalate

 it

 to

 the





managers

 and

 then

 so

 on.

 So

 these

 are





the

 blockers

 that

 slow

 down

 the





organization.
</details>

### 决策追踪机器人与组织决策透明化

>> 查找器，如果你是 CEO 的话这太棒了，因为接下来就是另一件事。一是你得扮演侦探，另一个就是互相推诿甩锅的游戏。我们总在问“是谁的原因？为什么还没搞定？”当你身为领导者，不管面对你的团队还是别的团队，总会说：“嘿，我们本来应该今天把这个做完的，本来应该达成这个目标的，谁负责？”然后就会出现像那个表情包里三个蜘蛛侠互指的场面。
<details><summary>Original English</summary>
>> finder,

 which

 is

 great

 if

 you're

 the

 CEO





because

 there

 here's

 the

 next

 thing.

 One





you have

 to

 play

 detective,

 the

 other





one

 is

 the

 blame

 game.

 Who's

 why

 isn't





this

 done

 is

 what

 we

 always

 ask.

 And





when

 you're

 a

 a

 leader

 whatever

 your





group,

 another

 group,

 hey,

 we

 were





supposed

 to

 do

 this

 by

 today,

 we were





supposed

 to

 hit

 this

 target,

 who's





responsible?

 And

 then

 you

 get

 three





Spider-Mans

 pointing

 at

 each

 other

 if





you

 know

 the

 meme.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而在这里，情况就变成了：“哇，原来是这块具体数据还没解决，而你的团队什么都还没跑起来。”

我也遇到过类似的事。我当时想出了一个机器人，本来打算在全公司推广，谢天谢地我最后没这么做。我弄的这个机器人叫作“重大决策”（major decisions）。

我对它说：进入 Slack，以我的身份加入每一个群聊。直接以我的身份进入每一个频道——有些人都愣住了：“等等，你到底是怎么知道我们有这个群的？”——加入每一个群，读取每一个 Notion 页面，不管我有没有被邀请进去；获取每一封邮件。然后按月以及每隔几天为我查找并生成一份报告，列出最重要的决策、参与决策的人员、处理结果以及尚未解决的事项。

接着我说，再把在这类讨论中参与度最高的人列给我。然后我意识到，哇，这些人才是组织里真正在做决策的人，这些人反应最快。我的下一份报告将是：谁对这些讨论的贡献响应最快。在风投机构里，这类讨论会是像“我们要不要投资？要不要行使按比例追加跟投权（pro rata）？如果有老股转让报价（secondary offer），我们要不要出售所持股份？”而在播客业务里，就会是“我们要不要约这位嘉宾？要不要用这段素材还是那段素材？”

然后它还抓取到了人事方面的讨论。

上面写着像“我们该不该开除这个人？我们要不要搞绩效改进计划（PIP）？”而我的态度是，我们不搞 PIP。我觉得 PIP 太荒唐了。如果绩效没达到预期，就像是这个人根本没去上班一样。
<details><summary>Original English</summary>
>> Here

 it's

 like,

 wow,





this

 actual

 piece

 of

 data

 has

 not

 been





resolved

 and

 your

 team

 has

 run

 nothing.





I

 had

 a

 similar

 thing.

 I

 came

 up

 with

 a





bot

 and

 I was

 going

 to

 share

 it

 with

 the





whole

 company

 and

 thank

 God

 I

 didn't.





But

 I

 came

 up

 with

 a

 bot

 just

 called





major

 decisions.





And

 I just

 said

 go

 into

 Slack,





join

 every

 room

 as

 me.

 Just

 join

 every





channel

 as

 me,

 which

 some

 people

 are





like,

 wait

 a

 second.

 How

 did

 you even





know

 we

 had

 a room?





Join

 every

 room,

 read

 every

 notion

 page,





even

 if

 I

 was

 invited

 to

 it

 or not.

 Get





every

 email

 and

 find

 for

 me





for

 the

 month





and

 every





couple

 of days,

 give

 me

 a report

 on

 the





most

 important

 decisions,

 who





participated

 in

 them,

 and

 what

 was

 the





resolution,

 and

 what's

 not

 resolved.





Then

 I

 said,

 give

 me

 the

 people

 who





participate

 the

 most

 in

 these

 kind

 of





discussions.

 And

 then

 I realized,

 oh





wow,





these

 are

 the

 people

 who

 are

 actually





making

 decisions

 in

 the

 organization.





These

 are

 the

 people

 who

 are

 quickest.





And

 my

 next

 report's

 going

 to

 be

 is





who's

 quickest

 to

 contribute

 to

 those





discussions.

 Now,

 in

 a

 venture

 firm,





that's

 going

 to

 be

 a

 a

 discussion

 like,





should

 we

 invest

 or

 not?

 Should

 we

 take





our

 pro

 rata

 or

 not?

 Should

 we

 sell





our

 shares

 if we

 got

 a secondary

 offer?





In

 the

 on

 the

 podcast

 it's

 like,

 should





we

 book

 this

 guest

 or

 not?

 Should

 we





you

 know,

 use

 this

 clip

 or

 that

 one?





And

 then

 it

 picked

 up

 employment





discussions.





And

 it

 was

 like,

 should

 we

 fire

 this





person

 or

 not?

 Or

 you

 know,

 do

 we

 do





pips?

 And

 I'm like,

 we

 don't

 do

 pips.





And

 like,

 I

 just

 think

 pips

 are





ridiculous.

 Like,

 the

 performance

 isn't





here.

 That's

 like





the

 person

 didn't

 show

 up.
</details>

<!-- chunk 6/9 -->

>> “让我们折磨他们两个季度吧。”
<details><summary>Original English</summary>
>> Let's torture them for two quarters.
</details>

>> 是的，就像你错过了训练，比赛迟到了。那是基本门槛。如果你做不到这些，你就不能留在队里。所以你现在我们要折磨你，试图逼你准时来上班，或者做你不想做的体能锻炼。那么，也许你可以谈谈，作为创始人和 CEO，这在帮你弄清谁是团队中的全明星方面会起到什么作用？到底谁在真正做出贡献？因为我们现在基本上是在做商业上的点球成金（Moneyball），就像电影《点球成金》一样。布拉德·皮特演的，那是一部非常棒的电影，一本非常好的书。我们实际上正在进入类似管理学的点球成金，不是吗？
<details><summary>Original English</summary>
>> Yeah, like you you missed practice and you showed up late for the game. That's table stakes. You can't be on the team if you can't do those things. So you now we're going to torture you to try to make you come into work on time or do a workout you don't want to do. So maybe you can speak to what this is going to do for you as a founder and a CEO in terms of figuring out who are your all stars on the team. Who are the ones who are actually contributing? Because now we're getting to essentially business moneyball, like that movie Moneyball. It's fantastic, Brad Pitt. It's such a good movie, such a good book. We're actually getting into like management moneyball, aren't we?
</details>

### 用 AI 洞察组织文化与管理决策

>> 是的，确实如此。不过我的意思是，我最喜欢问的问题之一就是去观察不同的组织，因为我们有特定的文化原则：求真、第一性原理等等。我会问：嘿，这些领导者中谁遵循了这些原则？去查看他们的整个组织，去查看所有的会议，你可以从中推导出来。顺便说一句，你甚至可以问：嘿，这位领导者实际推行的是什么文化？它会给出不同的——你知道，他们会告诉你，不，实际上那里的文化是这个，而不是公司的文化，嗯，这非常关键，对吧？
<details><summary>Original English</summary>
>> Yeah, absolutely. But I mean, one of my favorite questions is just look at different orgs because we have certain culture principles, truth seeking, first principle, and so on. And I say, hey, which of these leaders follow these principles? Look in their whole orgs, look at all the meetings, and you can derive from those. And by the way, you could even ask, hey, this leader, what is the actual culture they're implementing? And it'll come up with different, you know, they'll tell you, no, actually the culture there is this, not the company culture, uh, which is essential, right?
</details>

>> 偏离了核心原则。这种偏离对你作为创始人来说就是毒瘤——或者可能是你需要改变的事情，也可能是一个早期预警信号。
<details><summary>Original English</summary>
>> deviating from the core principles. That's that drift is cancer- for you as a founder, or it could be something you need to change and could be an early warning sign.
</details>

>> 不管怎样，我们需要保持一致，对吧？也许他们是对的，而组织的其他部分，包括我，都是错的，但至少它告诉我存在分歧，我们可以，你知道，所以这种事情以前几乎是不可能做到的。就像许多其他事情你原本也可以做，但像这样一个问题：去了解一个拥有 12——你知道，12,000 人的组织中这个子团队的文化，你知道，弄清楚 Data Bricks 在日本的组织情况。我甚至不会说日语，你知道，我们在那里有数百人工作。那里的文化是怎样的？我们如何做决策？它与欧洲、中东和非洲地区（EMEA），或者我们拥有的拉丁美洲拉美（Latam Latam）地区有什么不同？所以这些都是颠覆性的改变。

对我们来说，关键在于我会把所有这些信息分享给员工。他们自己都可以访问所有这些信息，然后我告诉他们，这就是我们想要的。就像那条 L 型曲线，我们希望将它向右移动。所以大家，让我们来改变它。让我们向着我们共同拥有的北极星前进。

这有助于让我们更具竞争力。一旦我们更有竞争力，我们就能打造更多产品，抢占市场份额，并进一步加速我们的增长，你知道。我希望不是每年保持 70% 到 80% 的增长，我希望能达到 100——你知道，远超 100。这样我们就能投入——你知道，我就是这么看的。所以当下这个时代，这就是一种竞争优势。无论谁能把这个做得最好，你知道，在某个时刻也许每个人都在使用，它完全普及开来，每个人都在这么做。但眼下，这是巨大的超额收益（alpha）。如果你能把这做得非常非常出色，胜过任何其他组织，呃——
<details><summary>Original English</summary>
>> We need to be consistent, whatever it is, right? Maybe they're right and the rest of the organization and including me are wrong, but then we need to at least it tells me that there's a there's a divergence and we can sort of, you know, so those kind of things were like nearly impossible to do. Like like many of this other stuff you could have done, but a question like that, like get the culture of this subgroup in a 12 you know, 12,000 person organization, you know, figure out how the Japan organization at Data Bricks I don't even speak Japanese, you know, and we have hundreds of people over there working. Like what's the culture like? How do we make decisions? How's it different from the EMEA or, you know, the Latin Latam Latam, you know, region that we have? So those are kind of game changers. For us, it's really I share all this information with the employees. They have access to all of this themselves and then I tell them like this is what we want. Like that L curve, we wanted to shift it to the right. So everybody, let's change that. Let's let's move towards this, you know, the North Star that we have together.

And that helps us just be more competitive. And then once we get more competitive, we can build more products and we take market share and we can accelerate our growth further, you know. I'd like to not be 70 80% growth every year. I'd like to be 100 you know, way over 100. So then we can put you know, that's that's how I see it. So this is a in this era right now, this is a competitive advantage. Whoever can do this best, you know, at some point maybe everyone is using it's fully diffused and everybody is doing this. But right now, this is big alpha. If you can do this really really well, better than any other organization, uh,
</details>

### 上市时机与二级市场流动性

>> 巨大的超额收益。很多人一直非常耐心地留在你们的股东名册（cap table）上，而现在创始人和资方之间有一场大辩论。保持私有更长时间。如果二级市场相当高效，上市的意义何在？Stripe 保持私有状态，我想，都快 20 年了，而不是 10 年。他们似乎也释放出信号，打算继续保持私有更长时间。SpaceX 耗费了一阵子。Uber 耗费了一阵子。那一次我深有体会，不过幸运的是孙正义出手阔绰。

你们什么时候上市？什么时候，以及你们如何做出这个决定？我知道你面临着很大的上市压力，但你在充满活力的二级市场中也有很多减压阀。
<details><summary>Original English</summary>
>> of big alpha. A lot of people have been very patiently been on your cap table and we have a big debate between founders and capital right now. Stay private longer. What's the point of going public if we have secondary markets that are quite efficient? Stripe has been private [laughter] closer to 20 years, I think, than 10. And they seem to have given the indication they're going to stay private longer. SpaceX took a little while. Uber took a little while. I felt that one, but luckily Masayoshi-san was splashy cashy. When are you going public? When And how do you make that decision? I know you got a lot of pressure on you to do it, but you also have a lot of pressure relief valves in the the vibrant secondary market.
</details>

>> 是的。听着，我的目标是在未来一二十年里让 DataRobot 尽可能取得成功。这就是我的考量方式。实现这一目标的正确策略是什么？我提到了我们在这里所做事情的超额收益，我们正在打造的产品。顺便说一句，我们正在进军新的市场。我们进入了安全市场，我们进入了营销市场。呃，我专注于这些。那么接下来的问题是，通往那里的路径，是对我们而言上市是最好最快的方式，还是保持私有是最好最快的方式。实际上我认为答案——
<details><summary>Original English</summary>
>> Yeah. Look, my goal is to make DataRobot as successful as possible in the next decade or two. That's how I'm thinking about it. What's the right strategy to get there? I mentioned this alpha of what we're doing here, the products we're building. By the way, we're getting into new markets. We got into security market. We got into the marketing market. Uh I'm focused on those. Then the question is the path to get there is the best way and the fastest way for us to be public or to be private. And I actually think the answer
</details>

>> 对你来说，天平的两边各自有什么？
<details><summary>Original English</summary>
>> What's what's on each side of the ledger for you?
</details>

>> 是的，我其实认为，你知道，你能获得资本。你能获得好得多的市场营销。呃，你知道，这就像大家都知道了你。就像每个季度你都有这样一个大型营销活动，你可以一次又一次地讲述你的故事。这些都是巨大的优势。我们每年都必须组织自己的要约收购（tenders）。每年我们做财务都必须经历这个庞大的流程。你知道，我想我们筹集了 200 亿到 300 亿美元。然后我们必须安排这些。这是一项繁重的工作。而公开市场上就有现成的机制做这件事。
<details><summary>Original English</summary>
>> Yeah, I actually think that, you know, you get access to capital. You get much much better marketing. Uh you know, it's like everybody knows about you. Like every quarter you have this big marketing event and you can tell your story again and again and again. Those are huge advantages. We have to organize our own tenders every year. Every year we do finance has to go through this big process. You know, I think we raised $20 $30 billion. And then we have to arrange that. It's a heavy lift. There is a marketplace that just does that.
</details>

>> 我想这很可能相当让人情绪波动且容易分心，对吧？就像人们不得不做决定。然后你可能会失去一些人，嘿，他们套现了 1000 万美元。现在他们就像是，啊，也许我不想再来参加训练了。
<details><summary>Original English</summary>
>> probably a pretty emotional and distracting, I would think, right? Like people have to decide. Then you might lose people that, hey, they take $10 million off the table. Now they're like, ah maybe I don't want to come to practice anymore.
</details>

>> 我觉得流动性——我认为流动性是件好事，因为，你知道，人们知道自己每年都会拿到它，它按时到来，具有可预测性，就像他们拥有这唯一的一次机会。而且实际上在过去，自从我们几年前开始做这些以来，事实证明，你知道，我们为要约收购预留的资金，他们从来没有全部用完过。所以大多数员工都是看好的。是的，所以大多数员工都觉得，不，这是——
<details><summary>Original English</summary>
>> I think the liquidity I I think the liquidity is a good thing cuz, you know, people know that they're going to get it every year and it kind of comes and it's like predictable and that's like the one time they have. And actually in the past it's turned out since we started doing these a few years ago, it turns out that, you know, the money that we set aside for tenders, they never use up all of it. So most employees are bullish. Yeah, so most employees are like, no, this is
</details>

>> 这对你来说是好事。你能从中得到信号，对吧？谁在卖，谁没卖。这算是一种信号。虽然可能是出于个人原因。嗯，但是收购公司是持有股权的一个极好理由，对吧？
<details><summary>Original English</summary>
>> that's good for you. You get signal from that, right? Who's selling, who's not. It's a little bit of signal. It could be personal reasons. Um but acquiring companies is a great reason to have equity, yeah?
</details>

>> 我们能——我的意思是，我们在进行十亿美元规模的收购方面没有任何问题，因为他们了解我们将提供的流动性。而且我认为大多数人都会算一笔账，就像，好吧，如果，你知道，业务规模达到 70 亿美元以上，并且正以 70% 到 80% 的速度增长，他们就会算这笔账：好吧，我本来大多数人说我想要流动性，但随后当你问他们：好吧，那你想卖多少？我们正在增长——你知道，你能算算 1.7 的三次方或四次方的复合增长吗？然后他们就开始挠头了：好吧，也许我就卖个 5% 吧，你知道。
<details><summary>Original English</summary>
>> We can I mean, we haven't had a problem, you know, doing billion dollar acquisitions because they know because of the liquidity that we will provide. And then I think most people do the calculation is like, okay, if it's, you know, the business is $7 billion plus and it's growing 70-80% they do the math like, okay, I could once most people say I want liquidity, but then when you tell them like, okay, well, how much do you want to sell? We're growing you know, can you do compounded growth of, you know, 1.7 to the power, you know, to the power of three or four? And then they start scratching their heads like, okay, maybe I'll sell like 5% you know.
</details>

### 研发效率与产品外围扩张

>> 是的，手握股票按兵不动（sitting on your hands）是对持有这种股票的投资者和员工来说非常重要的一项必修技能。我的意思是，听着，当你进入那个领域时，你确实必须防范下行风险。你现在把谁视为竞争对手？大家都说是像 Snowflake 这样的公司，但我所观察的市场，正如我之前所说的，Anthropic 正在接二连三地推出功能。Cloudflare 正在审视周边相邻的功能。Replit 正在关注与他们相近的功能。每个人似乎都在用余光审视周围，而且因为你们可以快速构建软件，因为你们拥有大量开发者，如果这些开发者继续沿着你展示的那个斜坡往上走——在那个峰值上你只有 10% 的人，这意味着随着那 90% 的人爬上去，你的开发资源将会爆棚。所以你必须做出决定。

我们是只要在长尾低端保留更少的开发者，从而提高盈利能力，还是在他们沿着斜坡向上走时把所有的开发者时间都投入进去？那么，你是如何看待这两个问题的？面对这种效率创造出的海量资源，你会怎么做？另外，竞争对手是谁，你是否只需要不断进行外围的产品布局？
<details><summary>Original English</summary>
>> Yeah, sitting on your hands is a very important skill to learn as an investor and an employee with this this kind of sock. I mean, listen, you do have to protect downside when you when you get in that space. Who do you see as your competition right now? Everybody says something like Snowflake, but I'm watching a market where, as I said earlier, Anthropic is launching feature after feature. Cloudflare is looking at features next to them. Replit is looking features next to them. Everybody seems to be looking in their peripheral vision and because you can build software fast and because you have a lot of developers, if those developers keep going up that ramp that you showed, you only had 10% of people at that peak, which means as that 90% climb up there, your developer resources are going to go through the roof. So you have a decision to make. Do we just have less developers at the low end of the tail and have be more profitable or do we invest all that developer time as they move up the ramp? So so how do you think about both of those issues? What do you do with massive resources that this efficiency is creating and then who is the competitor and do you need to just keep making peripheral product moves?
</details>

>> 是的，我们会采取外围产品动作，但也许我应该先说，好的，这些就是上市的好处。而坏处则是，你知道，这也正是为什么，为了回答你的具体问题，比如，你知道，我们为什么竞争？我们和谁竞争？我们为什么要打造这款产品？我不希望市场迫使我陷入——好的，现在行情下跌了，现在它，你知道——
<details><summary>Original English</summary>
>> Yeah, we will make peripheral product moves, but maybe I should just start by saying, okay, so those are the upsides of going public. The downsides are, you know, is is the reason why, you know, to answer your specific question, like, you know, why why do we compete? Who do we compete with? Why do we build this product? I don't want the market to force me that, okay, now it's down and now it's, you know,
</details>

<!-- chunk 7/9 -->

本周市场情绪非常糟糕，现在你们的股价下跌了。而当股价下跌时，员工实际上等于被减薪了。然后我会说：“好吧，你看，你当初答应我能赚一百万美元。实际上，你说过两三年内会变成两百万，但我现在看着它，额，实际上只有200k。所以你骗了我，我要走了，好吗？”额，然后过了三个月，情况又变成：“哦，不不不，实际上营收正在加速增长，我们之前完全错了，现在一路向右上狂飙。”然后大家就觉得：“哦，好吧，哇，太棒了。”所以就存在着这种反复折腾。额，那样的……
<details><summary>Original English</summary>
sentiment is terrible this week and now your stock is down and when the stock is down, the employees literally are getting a pay cut. And I say, well, you know, you promised me I was going to make a million dollars. Actually, you said this is going to be two million in a couple of years, but I'm looking at it right now. Uh and it's actually two 200k. So you lied to me. I'm leaving, okay? Uh and then, you know, three months later it's like, oh, no, no, no, actually the revenue is accelerating. We were totally wrong. It's up to the right now. It's like, oh, okay, wow, it's great. So there's like back and forth. Uh that's
</details>

>> 这种过山车式的起伏可能会让人压力很大。
<details><summary>Original English</summary>
>> of a roller coaster can be stressful.
</details>

### 上市时机与短期波动的干扰

>> 这正是我想要避免的，这样我们就能专注于长期目标，你知道，朝着我们长远持有的愿景去建设公司，而不受干扰。我们将来会上市，我们是一定要上市的。但目前，我认为在人工智能的这个过渡时期，存在太多起起伏伏，我认为这对各家公司是一种干扰，对CEO们是一种干扰，对CEO们来说也令人沮丧。你知道，他们打电话给我，心情都很沮丧，因为股价下跌了，他们甚至都不明白为什么，然后股价又涨上去了。额，所以这就是我们试图避免的。
<details><summary>Original English</summary>
>> what I want to avoid so that we can focus on that long term, you know, building the company towards the vision that we have in the long run without being distracted. We will go public. We are going to be public, but right now, I think during this transition period of AI, there's just too much up and down and I think it's distracting to companies, it's distracting to CEOs, it's demoralizing to CEOs, you know, they call me, you know, they're like depressed because, you know, stock is down, they don't even understand why and then the stock is up. Uh so that's what we're trying to avoid.
</details>

>> 我觉得这是人们在面对睡眠评分时也开始遇到的问题。你知道，你买了个Whoop手环，我非常喜欢它，但我给我妻子也买了一个Whoop，然后我们就会互相比较睡眠评分。现在这种感觉就有点像每天盯着你的Uber股票看一样。这会让彼此关系变得有点起伏波动，可能会带来挑战。但在其他方面这挺有意思的。对了，我们还没回头聊本·霍洛维茨（Ben Horowitz）说的话呢。他说，你对超级智能的构想是模型、算力以及训练并达到精确所需时间的某种结合。你能给我们详细讲讲吗？你脑子里有现成的思路可以随时展开吗？
<details><summary>Original English</summary>
>> I think it's an issue people are starting to have with their sleep scores, you know, you get a whoop. And I love it, but I got my wife a whoop and then we're like comparing sleep scores and now that it's kind of like looking at your Uber stock every day. You get a little bit of volleying relationship, it could be challenging. Ben in other ways it's it's interesting. Hey, we didn't circle around to what Ben Horowitz said. He said that your formulation of super intelligence is some combination of the model, the power, and the time it takes to train and be accurate. What can you walk us through it? Do you have it off the top of your head there ready to go?
</details>

### 超级智能与递归自我改进的现实条件

>> 我非常乐意讲。我的意思是，这其实很简单。所以，我认为主要问题是上下文问题。我们正在用genie和本体（ontology）来解决这个问题。各大实验室关注的是超级智能，这就是博斯特罗姆（Bostrom）所谈论的内容。博斯特罗姆在他的书里也讨论过，我们如何到达那里？我认为他实际上在2014年定义了RSI，额，即递归自我改进（recursive self-improvement），这意味着AI开始自我改进，然后它变得越来越好、越来越好，接着我们就迎来了起飞，也许是快速起飞。到了那个阶段，你知道，我们达到了奇点，我们就不再处于控制地位了。到了那个阶段，让我们祈祷AI能有良好的对齐，因为如果不对齐，我们所有人都会被当成宠物来养。这就是10%风险……是的，纸夹最大化，以及对人类造成10%风险等等，全都源于那里。
<details><summary>Original English</summary>
>> I happy happy to do it. I mean, it's pretty simple. So I I think the main problem is the context problem. We're solving that with genie and the ontology. The labs are focused on super intelligence. That's what Bostrom talked about. Bostrom in his book also said, how do we get there? He actually in 2014, I believe, defined RSI, uh recursive self-improvement, which means that the AI starts improving itself and then it gets, you know, better and better and better and better and better and then we get this takeoff, maybe a fast takeoff. And at that point, you know, we reach the singularity and we're no longer in control. And at that point, let's hope that the AIs are well aligned because if they're not, we're all going to be made into pets. And this is where the 10% risk. Yeah, paper clip maximizers and the 10% risk to humanity and all of that comes from there.
</details>

但我认为这其中的很大一部分，实际上源于大多数正在构建这种AI的人。他们看到了AI在编程方面变得非常厉害。而且几乎在每家公司里，正如我之前所说，编程工作正由编程智能体来完成。所以他们就看到了这一幕，我认为这在硅谷实际上引发了一场巨大的生存危机。对于我们大多数从小以写代码为生的人来说，你知道，这真是一件大事。就像，你知道，这就像……比如我从三年级开始直到三十多岁，每周7天、每天花10到12个小时一直都在写代码，对吧？我非常擅长编程，掌握了所有这些语言等等。然后突然之间，AI开始做这件事情了。
<details><summary>Original English</summary>
But I think a lot of this is actually coming from most of the folks that are building this AI. They've seen that the AI has become really good at coding. And almost in every company, as I said earlier, the coding is being done by coding agents. So then they're seeing and I think this is actually causing a big existential crisis in Silicon Valley. And it's actually for most of us who started, you know, who grew up coding our whole lives, you know, it's it's it's a big deal. Like, you know it's like like I spent, you know, 10 12 hours, 7 days a week, you know, from third grade until, you know, my 30s just coding all the time, right? And I was really good at it and I knew all these languages and so on. And then suddenly it's like the AI is doing that.
</details>

>> 嗯，而且AI比你强多少？那是另一部分。这就像……
<details><summary>Original English</summary>
>> Well, and the AI is how much better than you? That's the other part. It's like
</details>

>> 是的。所以现在它开始自己编写自己，下一个版本也是它自己编写的。等一下，这不就是递归自我改进吗？但等一下，这样一来速度就会加快，然后我们就会陷入这个循环中。书里……那本书称之为《超级智能》和“纸夹最大化”。所以它可能会失控，所有这些糟糕的事情都会发生。其实很有意思，博斯特罗姆现在在某种程度上已经改变了他的观点。如果你现在真正去关注他，他实际上已经不再持那种态度了。他现在说的是，你知道，我们应该去做这件事。风险当然是有的，网络安全方面肯定有风险。但是，你知道，我实际上认为，你需要更进一步深入思考这个问题。
<details><summary>Original English</summary>
>> Yeah. So now it's writing itself and the next version it wrote itself. Wait a minute. Isn't that the recursive self-improvement? But wait a minute. Then this is going to speed up and then we're going to get into this loop. The books the book called it Superintelligence and the Paper Clip Maximizer. So it might go off and all these bad things happen. Actually, interesting. Bostrom has kind of changed his view now. If you actually follow him now, he's actually not anymore. He's saying that, you know, we should do this. There are risks. Of course, there are risks with cyber. But, you know, I actually think, you know, you need to actually think this through further.
</details>

仅仅因为98%的代码是由AI编写的，并不代表我们就拥有了RSI。如果它把最后2%也自动化了，谁在乎呢？你知道，98%还是100%有什么区别吗？为什么这很重要？其实无所谓。所以我们真正需要满足四个条件。
<details><summary>Original English</summary>
Just because 98% of the code is being written by AI, we don't have RSI. If it automates the last 2%, who cares? You know, does it matter if it's 98 98% or 100%? Why does it matter? Actually doesn't matter. So we really need four conditions to be true.
</details>

这四个条件是：我们需要下一个训练出来的模型，能够用短得多的时间训练出来，好吗？而各大实验室进行的那些大规模预训练运行，他们每年实际上做得并不多，好吗？而且它仍然遵循所谓的缩放定律（scaling laws），这意味着你需要指数级增加的硬件才能获得那种提升。所以需要指数级增加、10倍的算力才能换来一点点线性的提升，明白吗？因此他们正在拼命搜罗并拼凑出他们所能组建的最大数据中心，配置网络并完成所有工程设计。然后，他们让纯人工来做这一切，因为他们真的不想搞砸下一次运行。如果下一次运行搞砸了，那么整个事情就彻底泡汤了。
<details><summary>Original English</summary>
The four conditions is that we need the next model that's trained to, you know, be trained in much shorter amount of time, okay? And still the big pre-training runs that the labs do, they don't do actually that many of them per year, okay? And it's still following the what's called the scaling laws, which means you need exponentially more hardware to get that improvement. So exponential more 10x more compute to get a little linear improvement, okay? So they're scrambling to get all the and put together the biggest data center that they can possibly put together with the networking and do all the engineering. And then, they're having humans do all of this because they really don't want to screw up the next run. If the next run gets screwed up, then, you know, the whole thing falls apart.
</details>

但是，你知道，我们希望下一次训练运行能更快。这是第一个条件。好吗？而且实际上，它不能只是快了一点点。就像这样，你知道，不能像每次把距离减半那样，那样你永远也到不了。所以在某种意义上，它必须是超线性的。其次，我们还希望它消耗更少的资源，对吧？因为你知道，你可以说，好吧，它变得越来越快，但那是因为我们一直在把硬件规模扩大10倍。可是你不能一直玩这种把戏，因为硬件会用完，原子也会耗尽。所以这就是第二个要求。第三个要求是，准确率也至少以线性方式提升，或者说，我们在全局范围内以通用方式获得更好的准确率。不能仅仅是在我们做了强化学习的某一个维度上，或者仅仅在数学上变得更好。它必须在所有任务上面全面提升。好吗？
<details><summary>Original English</summary>
But, you know, we would like that next training run to be faster. That's condition number one. Okay? And actually, it can't just be a little bit faster. It's like this, you know, it can't be like, you know, you're halving the distance every time. You'll never get there. So, in some sense it has to be super linear. Secondly, we also want it to use less resources, right? Cuz you know, you could say, okay, it's getting faster and faster, but that's because we're 10 xing the hardware all the time. Well, you can't do that trick because we run out of hardware and we run out of atoms. So that's like the second requirement. Third requirement is that the accuracy is also improving at least linearly or, you know, we're getting better accuracy across the board in a generalized manner. It can't just be it's getting just better at, you know, this one dimension that we did reinforcement learning on or just math. It needs to be across the board on all of its tasks. Okay?
</details>

即便你把这三项都做到了，依然不够。假设你这样做了五次、六次、七次，那确实很棒，你能得到非常厉害的模型。但这还不是那种超级智能。第四个条件是，你实际上可以把这个过程放入一个闭环中，前面这三个条件需要持续不断地发生，从而让我们最终进入这样一个世界：下一个模型只需要三个月，然后是一个月，再然后是两周、一周，并且它变得越来越聪明、越来越聪明，而且花费可能只需要100块，或者可能一开始花1亿美元，然后是5000万、2500万、1000万、500万、200万、100万，然后不断向下递减。那就是我们……那是我们面临的情景。如果你真正审视它，那就是飞轮效应。
<details><summary>Original English</summary>
Even if you do all of those three, it's not enough. Let's say you do that five, six, seven times, that's awesome. You get really awesome models. That's not that kind of super intelligence. The fourth condition is that you can actually put this in a loop and all the previous three conditions need to be continuously happening so that we end up in a world where the next model takes, you know, three months, then one month, then, you know, two weeks, one week, and it's getting smarter and smarter and smarter and it's, you know, costing us 100 buck or maybe costs us 100 million, then 50 million, 25 million, 10 million, five, two, one, and then it goes down and down. That's what we That's the kind of scenario we have. If you actually look at it,
</details>

那个飞轮目前并不存在。现在的模型需要更长的时间来训练，对吧？并且有更多的数据清洗工作，而且有更多人工的“打地鼠”操作，比如像Mercor这样的供应商必须去从高技能劳工那里获取数据，然后你必须在这些gym环境中进行强化学习，而且你必须在各个领域逐个去打地鼠。所以这是非常特定于领域的。当然，预训练还需要更多的资源，所以，这看起来并不像我们正在进入这样一个循环。顺便说一下，即使你满足了全部四个条件，我也要说，这并不保证意味着你就会拥有一个有自我意识的存在，能够接管一切并且直接……
<details><summary>Original English</summary>
that's the flywheel. That flywheel doesn't exist right now. The models are taking longer to train, right? And there's more data cleaning and there's all more manual whack-a-mooling happening where, you know, you have vendors like Mercor that has to actually go get the data from very skilled labor and then you have to do reinforcement learning in these gyms and you have to kind of whack-a-mole in each domain. So it's very domain specific. And then of course the pre-training requires more resources and, you know, so um it's it's that doesn't look like we're getting into this loop. By the way, even if you satisfy all the four conditions I'm saying that doesn't guaranteed mean that you'll have, you know, a conscious being that's just, you know, taking over everything and just, you know,
</details>

>> 它是发生那种情况的前提条件，而且并不保证它真的会发生。
<details><summary>Original English</summary>
>> it's the precondition for that happening and it there's no guarantee that it actually happens.
</details>

>> 是一个前提条件，但即使你具备了这一点——而我们现在并不具备——要在此时此刻威胁到我，你必须得有一个杀手机器人现在就走进这个房间把我按倒在地，好吗？或者采取某种行动，对吧？而那些东西目前还不存在。所以，额，你知道……
<details><summary>Original English</summary>
>> a precondition, but even if you had that, which we don't have, you would have to to threaten me right now, you would have to have a killer robot come into this room right now and wrestle me down, okay? Or something, right? And those don't exist yet. So, uh you know,
</details>

>> 是的。现在，你可以让一群黑客利用一个能力非常强的模型，然后你可以找到……
<details><summary>Original English</summary>
>> Yeah. Right now, you can have a bunch of hackers take a really capable model and you can find
</details>

<!-- chunk 8/9 -->

发现法国杂货店里的冰箱密码是 admin admin，然后你就可以远程像个脚本小子一样黑进去，把它们调成除霜模式，导致一堆黄油和牛奶变质——对法国人来说这确实是个悲剧，我理解，[笑声] 但这可不是超级智能，我向你保证。这意味着……

我是说，你看到那起黑客事件以及人们对此有多抓狂了吗？我心想：各位，你们知道现在买新路由器时，上面都会有序列号和一个随机密码吧？
<details><summary>Original English</summary>
 out

 that

 the

 refrigerators





in

 grocery

 stores





in

 France





have

 the

 password

 admin

 admin

 and

 that





you

 can

 remotely

 script

 kitty

 into

 them





and

 turn

 it

 into

 defrost

 mode

 and

 make

 a





bunch

 of

 butter

 go

 bad

 and

 milk,

 which





is

 a

 tragedy

 for

 the

 French.

 I





understand,

 [laughter]

 but

 it

 is

 not





super

 intelligence,

 I

 can

 assure

 you.

 It





means





I

 mean,

 did

 you

 see

 that

 hack

 and

 how





people

 were

 losing

 their

 minds

 over

 it?





I'm

 like

 guys,

 you

 know

 how

 when

 you

 buy





a

 new

 router

 now,

 it

 has

 the

 serial





number

 and

 then

 a

 random

 password?
</details>

>> 是啊，admin admin，没错。
<details><summary>Original English</summary>
>> Yeah,

 admin

 admin,

 yeah.
</details>

>> 对，如果他们在冰箱上也这么做，他们就一台也黑不进去了，除非他们潜入现场，拍下 20 台不同冰箱的照片，对比如第八区的某家超市进行物理入侵，那样也就损失，我不知道，10 磅黄油吧。那根本算不上什么大事。
<details><summary>Original English</summary>
>> Yeah,

 if

 they had

 done

 that

 on

 the





refrigerators,

 they

 would

 have

 been

 able





they

 wouldn't

 have

 been

 able

 to

 hack

 one





of

 them

 unless

 they

 got

 into

 the

 place,





took

 screenshots

 of

 20

 different





refrigerators,

 physically

 compromised





you know,

 some

 supermarket

 in

 the

 8th





arrondissement,

 which

 would

 have

 lost,





you

 know,

 I

 don't

 know,

 10

 lb

 of

 butter.





It wouldn't

 have

 been

 a

 big

 deal.
</details>

### 网络安全攻防不对称与代码安全

>> 所以，听着，网络安全我认为确实是个真实存在的问题，我也认为这是个真正的风险。我们在网络空间其实有一整套基于所有这些数据构建的产品叫 Likewatch，它拥有自动化智能体，能实际检测正在发生的这类入侵，并且它们会监控你拥有的智能体。

这是一个真正的问题，我确实认为坏事会在这里发生，但随后我们会做出调整。然而互联网刚出现的时候，坏事也同样发生过。
<details><summary>Original English</summary>
>> So,

 look,

 cyber

 I do

 think

 is

 a real





thing

 and

 I

 think

 it's

 a real

 risk.

 We





actually

 have

 a whole

 product

 in

 the





cyberspace

 called

 Likewatch

 built

 on

 all





this

 data

 that

 has

 automated

 agents

 that





actually

 detect

 these

 kind

 of

 intrusions





that

 are happening

 and

 they

 monitor

 your





agents

 that

 you have.





This

 is

 a real

 problem

 and

 I

 do

 think





bad

 things

 will

 happen

 here,

 but

 then

 we





will

 adjust.

 But

 bad

 things

 happened





when

 internet

 came

 out

 as

 well.
</details>

>> 难道我们不应该……难道我们不应该能解决这个问题吗？因为如果你听听看我说得对不对。我听过一种理论，它让我对某一类黑客行为产生共鸣——不是针对那种，你知道，脚本小子式的黑客，而是真正的黑客——呃，就是你拥有大量的算力，你需要大量的算力来执行某些黑客攻击，比如 Hugging Face 那起，你知道的，上千个智能体之类的。

坏人没有那么多算力。好人拥有的算力要庞大得多。所以，如果你只是做好作为白帽子的本职工作，并且做好适当防御，寻找这些漏洞利用点，假设你拥有千倍的资源，你应该能够远在黑客之前解决这些问题。

你觉得这说得通吗，他们只是……
<details><summary>Original English</summary>
>> Shouldn't

 it





Shouldn't

 we

 be

 able

 to

 solve

 for

 this





because

 you

 tell

 me

 if

 I'm

 right

 or





wrong

 here.

 One

 theory

 I

 heard,

 which





resonated

 with

 me

 for

 a

 certain

 type

 of





hacking,

 not

 for

 the

 you

 know,

 script





kitty

 hacking,

 but

 real

 hacking





uh

 is

 you

 you

 have

 a

 lot

 of

 compute,

 you





need

 a

 lot

 of compute

 to





execute

 certain

 hacks,

 like

 the

 hugging





face

 one,

 you

 know,

 thousand

 agents,





whatever.





The

 bad

 guys

 don't

 have

 that

 much





compute.

 The

 good

 guys

 have

 a massive





amount

 of

 more

 compute.

 And

 so,

 if

 you





just

 did

 your

 basic

 job

 as

 a white

 hat





and





you

 know,

 defended

 properly

 and

 looked





for

 these

 exploits,

 let's

 say

 you

 have

 a





thousand

 times

 the

 resources,

 you

 should





be

 able

 to

 get

 to

 these

 problems

 long





before

 the

 hackers.





Does

 that

 make

 good

 sense

 to

 you

 that





they're

 just
</details>

>> 对。是的，是这样，但问题在于你必须把它与我们面临的以下不对称场景进行权衡：如果我是一个攻击者，你知道，我可以发起成千上万、成千上万个智能体，它们全部失败都没关系，只要有一个成功就行。只要有一个渗透进来，我就彻底成功了。不对称性在于，如果我是一个防御者，你知道，我一直在保护我的边界，但哪怕只有一个漏进来了。
<details><summary>Original English</summary>
>> Yeah.





Yeah.

 It's

 it's

 but

 there's

 a

 the

 the





issue

 is

 that

 you

 have

 to

 weigh

 that





against

 the

 following

 asymmetric





scenario

 that

 we have,

 which

 is if

 I'm





an

 attacker,

 you

 know,

 I

 can

 launch





thousands

 of

 thousands

 of

 thousands

 of





agents

 and

 I

 all

 of

 them

 can

 fail

 except





for

 one.

 And

 if

 one

 of

 them

 gets





through,

 I'm

 completely

 successful.

 The





asymmetry

 is

 that

 if

 I'm

 a defender,

 you





know,

 I

 was

 able

 to

 like,

 you

 know,

 you





know,

 protect,

 you

 know,

 my

 my





boundaries

 all

 the

 time

 except

 one

 got





through.
</details>

>> 这就像自杀式炸弹袭击者，话虽不太好听，但你只需要搞成一次“9·11”就能证明你的观点。而你可以尝试一千次都没成功。
<details><summary>Original English</summary>
>> This

 is

 a

 suicide

 bomber





not

 to

 be

 too

 graphic,

 but

 you

 only

 need





to

 get

 one

 9/11

 to

 make

 your

 point.

 And





you

 could

 try

 a thousand

 times

 and

 not





get

 through.
</details>

>> 必须始终做到 100% 的安全。他们只需要让一件事渗透进来就行。所以，这种风险是非常不对称的。不过，从我的视角来看，为什么我认为我们实际上能够克服这一点，而且最终会完全没问题，原因在于这些实际上是存在于源代码中的潜在漏洞。顺便说一句，我们现在并没有制造更多漏洞，因为几乎我们所有人现在都在进行扫描。我们都有这类产品。我是说，我们实际上就销售一款产品。我们可以扫描新代码的漏洞。因此，正在编写的新代码是不会包含这些漏洞的。顺便说一句，这听起来可能有点傻，但不妨这样想：在接下来的 12 个月里，我们要编写的代码将超过人类历史上的任何时期，对吧？实际上是在不到接下来的 12 个月内。呃，所以所有那些代码都将是安全的。那么……顺便说一下……
<details><summary>Original English</summary>
>> need

 to

 be

 100%

 safe

 all

 the

 time.

 They





need

 to

 just

 get

 one

 thing

 through.

 So,





it's

 like

 very

 asymmetric

 that

 risk.

 But





however,

 the

 the

 way

 I would

 look

 at

 it,





the

 reason,

 you know,

 I

 think

 that

 we're





actually

 going

 to

 overcome

 this

 and

 it's





going

 to

 be

 totally

 fine,

 is

 that

 these





are

 actually

 latent

 bugs

 that

 exist

 in





the

 source

 code.

 By

 the

 way,

 we're

 not





creating

 more

 of

 them

 now

 cuz

 almost

 all





of

 us

 are

 now

 scanning

 it.

 We

 all

 have





products.

 I mean,

 we

 actually

 sell

 a





product.

 We

 can

 scan

 the

 vulnerabilities





of

 new

 code.

 So,

 new

 code

 that's

 being





produced

 is

 not

 going

 to have

 these





vulnerabilities.

 By

 the

 way,

 that

 might





sound

 silly,

 but

 think

 about

 it this





way.

 In

 the

 next

 12

 months,

 we're

 going





to

 write

 more

 code

 than

 ever

 in

 the





history

 of

 mankind,

 right?

 Actually,

 in





less

 than

 next

 12

 months.

 Uh

 so,

 all





that

 code

 is

 going

 to be

 secure.

 So

 then





and

 by

 the

 way,
</details>

>> 现在 AI 已经足够先进，不会犯人类的错误，并且会去寻找错误，而且它更加坚韧执着。
<details><summary>Original English</summary>
>> right

 now

 the

 AI

 is sophisticated

 enough





to

 not

 make

 human

 errors

 and

 to

 look

 for





it

 and

 it's

 more

 dogged.
</details>

>> 是的。你只要把那些东西全部扫描一遍就行。那么剩下的就全都是遗留代码了，顺便说一句，我们完全可以把它们全部重写一遍，这也是我们必须经历的过程。而且……呃，我们也在通过其他方式来做这件事。
<details><summary>Original English</summary>
>> Yeah.

 You

 just

 scan

 scan

 those

 things.





So

 then

 what

 remains

 is

 all

 the

 legacy





code,

 which

 by

 the

 way,

 we

 can

 rewrite





all

 of

 it,

 which

 is

 what

 we

 have

 to

 go





through.

 And





uh

 we're

 doing

 that

 in

 other

 ways.
</details>

>> 80/90，是的。
<details><summary>Original English</summary>
>> 80/90,

 yeah.
</details>

>> 是的。其实还有其他方法来做保护，你知道，在甚至不动现有遗留代码的情况下进行影子补丁（shadow patching）。但是，嗯，所以，你知道，目前正在发生的情况可以看作……你可以把它想象成一个果园，那些被攻击者利用的漏洞就像是低垂的水果，他们在采摘低垂的水果。以前人类能采摘到一定高度的低垂水果，现在智能体能伸得更高，去采摘挂得更高的水果。但我们正在清理那些漏洞，然后他们也许能伸得再高一点点，但代码里的漏洞数量终归是有限的。一旦我们把那个代码库保护好，就没有更多漏洞了。所以这并不是一个无限的事情，也不会永远持续下去。不，到那时它就会停止。然后我们就会处于一个稳态，到那时，你知道，漏洞可能实际上比我们过去的还要少。
<details><summary>Original English</summary>
>> Yeah.

 There's

 other

 ways

 to

 actually





also

 protect,

 you know,

 do

 shadow





patching

 before

 even

 actually

 without





touching

 the

 existing

 legacy

 code.

 But





um

 so,

 you

 know,

 what's

 happening

 is





that

 you

 can

 think

 of it

 as

 like,

 you





know,

 it's

 like

 a

 fruit

 garden

 and





they're

 like

 these

 bugs

 that,

 you

 know,





attackers

 are

 leveraging,

 they're





picking

 the

 low-hanging

 fruits.

 And





before

 humans

 could

 pick

 a certain





low-hanging

 fruit,

 now

 agents

 can

 reach





higher

 and

 pick

 higher,

 you

 know,





hanging

 fruit.

 But

 we're

 going

 to

 clean





clean

 those

 up

 and

 then

 they

 can

 maybe





reach

 a little

 bit

 higher,

 but

 there's





only

 a

 finite

 number

 of

 vulnerabilities





in

 the

 code.

 Once

 we've

 secured





that

 code

 base,

 there

 is

 no

 more.

 So





it's

 not

 like

 there's

 an

 infinite

 thing





and this

 is going

 to go

 on

 forever.

 No,





it

 then

 stops.

 Then

 we're

 at

 a steady





state

 and

 then,

 you

 know,





vulnerabilities

 might

 actually

 be

 fewer





than

 what

 we

 had

 in

 the

 past.
</details>

### 有效利他主义、超级智能风险与现实对策

>> 最终到了那时，你知道，回到你在伯克利搞 AMP 实验室的时候，系统里的人才是真正的漏洞，而且无非就是某个人被攻破了，正如我们在过去一周左右看到的那样。

人类确实存在漏洞。我就说到这儿吧。

嘿，我想以这件事作结。你在伯克利待了很长时间，嬉皮士风格、有效利他主义（EA）群体、加速主义者、减速主义者。

EA 派系这个群体的本质是什么，他们如何看待世界，他们对美国社会的其他人来说为何如此令人困惑？这些人是谁？他们相信什么？他们是有点陶醉于自己的成功，还是他们确实拥有真正重要的洞察，以至于我们需要真正关注他们所说的话并信以为真？这是一个巨大的争议。你知道，达里奥（Dario）在路演期间说癌症和阿尔茨海默病他相信会在 10 年内消失。现在，这话听起来非常美好，除非你……
<details><summary>Original English</summary>
>> that

 eventually

 then,

 you

 know,

 back

 to





amp

 when

 you

 went

 at

 Berkeley,





it's

 the

 people

 in

 the

 loop

 that

 are

 the





vulnerability

 and

 it's

 just

 going

 to

 be





somebody

 getting

 compromised

 as

 we

 saw





the

 last

 week

 or

 so.





The

 humans

 do

 have

 vulnerabilities.

 I'll





leave

 it

 at

 that.





Hey,

 I

 want

 to

 end

 on

 this

 one

 thing.





You

 you

 spent

 a lot

 of time





in Berkeley,





hippie-dippy,

 EA

 community,

 acceleris,





de

 celeris.





What's

 the

 nature

 of





this

 group

 of

 the

 EA

 faction

 and

 how





they

 look

 at

 the

 world

 and

 how





confounding

 they

 are

 to

 the

 rest

 of





American

 society?





Who

 are

 these

 people?

 What

 do they





believe?

 Are

 they

 a

 little

 drunk

 on





their

 own

 success

 or

 do

 they

 actually





have

 really

 important

 insights

 and

 we





need

 to

 really

 focus

 on

 what

 they're





saying

 and

 take

 them at

 their

 word?

 It's





a

 big

 controversy.

 Dario,

 you

 know,





during

 the

 road

 show

 is

 saying

 cancer





and Alzheimer's,

 I

 believe

 will

 be

 gone





in

 under

 10

 years.

 Now,





that's

 very

 beautiful

 to

 say





except

 if

 you're
</details>

>> 已经不在人世了，对吧？
<details><summary>Original English</summary>
>> dead,

 right?
</details>

>> 对，除非你，你知道，父母正死于癌症，你以为“哦，我这里有个能拯救他们时间窗口”，或者我祖母患有阿尔茨海默病。现在你谈论的是给人们虚假的希望，也许你不该做出这样的断言。但我并不怀疑达里奥相信这一点。我实际上认为他是相信的。但是给我们剖析一下这些人，因为你跟他们打交道已经有二十年、三十年了。
<details><summary>Original English</summary>
>> Yeah,

 except

 if

 you're,

 you

 know,

 mom

 or





dad

 are

 dying

 from

 cancer

 and

 you

 think,





oh,

 I got

 a

 window

 here

 that

 I

 could





save

 them

 or

 my

 grandmother's

 got





Alzheimer's.

 Now

 you're

 talking

 about





giving

 people

 false

 hope

 and

 you maybe





shouldn't

 make

 claims

 like

 that.

 But

 I





don't

 doubt

 Dario

 believes

 it.

 I





actually

 think

 he

 does.

 But

 unpack

 these





people

 because

 you've

 been

 around

 them





for

 two

 decades,

 three

 decades.
</details>

>> 嗯，你知道，我认为其实在双方、在所有立场上的大多数人，在他们自己的故事里都是主角英雄，对吧？我们每天醒来都认为自己是好人，都在做正确的事。所以我觉得这源于一种初衷。我认为他们对这种超级智能接管世界感到非常紧张。如果你读过博斯特罗姆（Bostrom）的书，实际上如果你读过那些书，并且在这一切发生之前某种程度上内化了他所写的内容，那你真的会感到恐慌，对吧？我当时读它的时候也确实被吓坏了。

所以我认为他们是从那些假设出发的，然后他们看到，好吧，如果它变聪明的速度这么快，再看看正在发生的所有网络攻击，省略号……我们就会迎来书中描述的那种超级智能。

但那里有几个省略号，并没有弄清楚。然而他们会说，好吧，听着，你知道，我们难道不应该保持谨慎吗，对吧？

所以我认为我们需要，你知道，我们应该关注安全。我认为网络安全是我们需要关注的一件大事。但现实是，我认为我们知道如何处理这个问题。我们将能够应对并渡过难关。我认为眼下最大的风险是网络安全，而且我认为它是可控的。这种递归自我改进（RSI），我没有看到任何证据。如果别人掌握了我没有的数据，那确实，我不知道我所不知道的事情。但根据我在这里与旧金山所有实验室以及我遇到的所有人的交谈，我提到的那四个标准我甚至没看到它们被满足，你知道的。所以我看不到有什么风险需要去担心它会发生，你知道。

然后我说的第二点是，即使我们真的走到了那一步，我也看不到，你知道，在社会中甚至连手段都没有，比如这只是纯数字层面的。比如我们现在直接把电脑关掉就行了。你知道，我确实认为网络安全是……
<details><summary>Original English</summary>
>> Well,

 you

 know,

 I

 think

 that

 most

 people





on

 both

 sides

 actually,

 on

 all

 sides,





they're

 the

 heroes

 in

 their

 own

 book,





right?

 We

 all

 wake

 up

 thinking

 I'm

 the





good

 guy

 and

 I

 'm doing

 the

 right

 thing.





So

 I think

 it

 comes

 from

 a

 place.

 I





think

 they

 are

 seriously

 nervous

 about





this

 kind

 of

 super

 intelligence

 taking





over.

 If

 you

 read

 Bostrom's

 books,





actually

 if

 you

 read

 those

 books

 and

 you





sort

 of

 internalize

 what

 he

 wrote

 before





any

 of

 this,

 then

 you

 actually

 get

 kind





of

 freaked

 out,

 right?

 And

 then

 I

 was





certainly

 freaked

 out

 when

 I

 read

 it.





So

 I

 think

 that

 they're

 starting

 with





those

 assumptions

 and

 then

 they're





looking

 at,

 you

 know,

 okay,

 well

 then

 if





it's

 getting

 smarter

 this

 fast

 and

 look





at

 the

 cyber

 attacks

 that

 are

 happening,





dot

 dot

 dot





we're

 going

 to

 get

 this

 kind

 of

 super





intelligence

 that's

 described

 in the





book.





But there's

 a few

 dot

 dot

 dots

 there





that

 are not

 clear.

 But

 then

 they

 would





say,

 well

 look,





you

 know,





shouldn't

 we

 be cautious,

 right?





So

 I

 think

 we

 need

 to

 take,

 you know,

 we





we

 should

 look

 at

 safety.

 Cyber

 I think





is

 a

 big

 deal

 that

 we

 should

 look

 at.





But

 the

 reality

 is

 that

 I

 think

 we

 know





how to

 handle

 this.

 We

 will

 be

 able

 to





manage

 through

 this.

 I

 think

 it

 will

 be





the

 biggest

 risk

 right

 now





is

 cyber

 and

 I think

 it's

 manageable.





This

 RSI,

 I

 don't

 see

 any

 evidence

 of





it.

 If

 there's

 data

 that,

 you

 know,





others

 have

 that

 I don't

 have,

 yeah,

 I





don't

 I don't

 know

 what

 I don't

 know.





But

 based

 on

 what

 I'm

 talking

 to,

 you





know,

 here

 in

 San

 Francisco

 where

 all





the

 labs

 are

 and

 all

 the

 people

 I meet,





I

 don't

 see

 those

 four

 criteria

 that

 I





mentioned

 even

 being

 fulfilled,

 you





know.

 So

 I

 I

 don't

 see

 any

 risk

 to be





like

 worried

 about

 it,

 you

 know,

 that





happening.

 And then

 the

 second

 thing

 I





said,

 even

 if

 we

 would

 get

 there,

 I





don't

 see,

 you

 know,

 even

 the

 means

 in





the

 society,

 like

 it's

 this

 is

 just





digital.

 Like

 we

 can

 just

 shut

 down

 the





computers

 right

 now.

 You

 know,

 I

 do





think

 cyber

 is
</details>

<!-- chunk 9/9 -->

是真的。比如如果一家医院瘫痪了，关掉了冷藏冰箱，对吧？那确实令人担忧，而且他们……
<details><summary>Original English</summary>
real. Like if a hospital went down and set up a refrigerator, right? That is concerning and they
</details>

### AI 技术部署与应用中的现实担忧

>> 正在使用……孩子们正在使用它，并与 Character.ai 建立了拟社会化人际关系；或者如果你有自杀倾向之类的，它会给你提供错误的信息。比如，对于这项技术如何部署，确实存在一些合理的担忧。我们之前就经历过这种情况——你之前提到了邓巴数（Dunbar's number）。我们经历过这种情况，你看，社交网络及其对社会产生的深远影响。我们现在正在经历真理与新闻，以及通过算法操纵新闻的问题。所以确实有一些事情值得担忧；但变成回形针什么的，可能并不用担心。
<details><summary>Original English</summary>
>> using kids using it and developing parasocial relationships with character AI or it giving you bad information if you're suicidal or something. Like there there are concerns to have about how the technology gets deployed. And we just went through this with you mentioned Dunbars number four. We went through this with you know, social and and the profound impact that had on society. We're going through it now with truth and news and and manipulation of news via algorithms. So there are things to be concerned about being turned into paper clips, maybe not.
</details>

>> 但……但我认为……
<details><summary>Original English</summary>
>> But but I think that,
</details>

### 医疗健康与药物研发案例

>> 你知道，医疗健康方面的事情绝对是真实的。比如在 Databricks，我们实际上……额，我们与再生元制药（Regeneron）合作，他们利用 Databricks 找到了导致慢性肝病的实际基因组。他们那里的研究人员实际上还利用它研发出了针对该疾病的药物……
<details><summary>Original English</summary>
>> know, the healthcare stuff is absolutely real. Like, you know, at Databricks we actually uh we were involved with Regeneron where they found the the actual genome responsible for chronic liver disease using Databricks. Their researchers there and actually came up with drugs for that using the
</details>

>> 在十年内……如果按我们听到达里奥（Dario）提出的说法，未来 10 年内我们治愈癌症的可能性存在吗？这可是个相当大胆的断言。
<details><summary>Original English</summary>
>> in under a decade if you were to take the claim we had Dario make any chance that like we cure cancer in the next 10 years? That's a pretty bold statement.
</details>

>> 这对我来说很难讲。我不知道究竟需要什么。我的意思是，我认为进展会更快，但对于其中的很多事情来说……呃，它还必须经过……嗯，你知道的，人体试验。人体试验可不像……你知道的，我们不能随随便便就在人身上做测试，对吧？而且光是在动物身上做过测试也是不够的，对吧？呃，所以我不知道。也许在 10 年内，也许不在 10 年内；也许需要 30 年，也许需要 50 年。我不知道。也许需要 6 个月。也许或多或少已经解决了。但它已经在提供帮助了。所以我刚才给你举的慢性肝病的用例，那极其重要。顺便提一下，那是我们在 Databricks 使用的上一代 AI。我们现在和默克（Merck）一起训练了一个新的模型，叫做 TEDD，即 Transformer Enabled Drug Discovery（基于 Transformer 的药物研发）。

Transformer Enabled Drug Discovery 是一个模型，一个 Transformer 模型，但它的下一个 token 不是英文，而是基因调控网络（Gene Regulatory Network，GRN）。因此它实际上能够判定：好，这个基因组实际上导致了这种疾病；而这个基因组只是对它做出反应，所以不要把它作为药物的作用靶点。这将加速药物研发。你知道，这是个颠覆性的改变。

呃，除了药物研发，你看，我再给你举一个例子，比如危机短信专线（Crisis Text Line）。它使用 Databricks，并使用大语言模型和这些 Agent，它们实际上能够检测出青少年是否有自残倾向，并帮助加以防范，对吧？呃，Virtue Foundation 也在使用 Databricks。还有 Zipline——这是之前报道过的一个用例——使用 Databricks 来运送食物。呃，他们拥有这些无人机，对吧？用来配送的无人机，关于这些无人机的一切等等，比如它们的路线……
<details><summary>Original English</summary>
>> It's very hard for me to say. I I don't know exactly what's needed. I mean, I think progress will be faster, but for a lot of these things uh it also has to go through um you know, human trials. Well, the human trials like, you know, we can't just test stuff on humans willy-nilly, right? And just because you tested it on animals it's not enough either, right? Uh so I don't know. Maybe in 10 years, maybe not in 10 years, maybe it takes 30 years, maybe it takes 50 years. I don't know. Maybe it takes 6 months. Maybe it's already solved more or less. But it is helping already. So the use case I gave you with chronic liver disease, that's super important. By the way, that was the previous generation of AI that we used at Databricks. We trained a new one now with Merck and it's called Teddy, Transformer Enabled Drug Discovery. Transformer Enabled Drug Discovery is a model, transformer model, but instead of, you know, the next token being English it's the Gene Regulatory Network, GRN. So it actually can say, okay, this genome is actually causing this disease. This genome is just reacting to it. So don't target it for a drug. So this will accelerate drug discovery. It's a game changer, you know. Um drug discovery aside, like, you know, I'll give you another example like Crisis Text Line. It uses Databricks and uses large language models and these agents and they actually detect if kids want to do self-harm and it helps prevent that, right? Um you know, Virtue Foundation uses uh Databricks. Um you know, Zipline uh this was a, you know, use case that was reported before, used Databricks to deliver, you know, food. Uh they had these drones, right? The drones that would deliver, you know, everything about those drones and so on like their their path, the, you know, um
</details>

>> 噢，真的吗？大数据……
<details><summary>Original English</summary>
>> Oh really? Big data
</details>

>> 是的，所有这些都在运行。所以我们看到这些……
<details><summary>Original English</summary>
>> Yeah, all of that was running. So we see these
</details>

>> 很棒的公司。
<details><summary>Original English</summary>
>> Great company.
</details>

### 风险认知、企业落地与普及节奏

>> 是的，我们在 AI 领域一直能看到这些用例，它会让世界变得更美好。风险是存在的，我们也会去应对它们。人们感到紧张，是因为一切都在发生变化。而且我认为在 AI 公司里，有很多研究人员可能非常懂研究，但他们并没有去审视经济层面会是怎样？将要发生什么？这些事情将如何演化？
<details><summary>Original English</summary>
>> Yeah, we see these use cases all the time with AI and it is going to make the world a better place. There are risks. We will deal with those as well. People are nervous because, you know, things are changing. And I think AI companies, there's a lot of researchers who maybe you know, they understand the research very well, but they haven't looked at, you know, how does the economy look? What's going to happen? You know, how does these things going to evolve?
</details>

>> 而且他们看了太多科幻作品了。实话实说吧。他们受到了某种特定叙事的影响。说有 10% 的概率会有 70 亿人因 AI 而死亡，这种想法看起来太荒谬、太离谱了；而当你随便挑出一个数字时，这反而让你在一个普通人眼里显得可信，普通人会觉得：“嗯，这些人很聪明，赚很多钱；如果他们这么想，也许他们是对的。”
<details><summary>Original English</summary>
>> And they've watched a lot of sci-fi. Let's be honest. Like they are being informed by, you know, a certain narrative. And the idea that there's a 10% chance that 7 billion people die because of AI seems so farcical and out there that when you pick a number, it makes you seem credible to an average Joe who's like, well, these are smart people who make a lot of money. And if they think it, maybe they're right.
</details>

>> 毕竟是他们自己亲口说的，对吧？人们就是这么想的。但在我看来，那种风险几乎接近于零。我认为网络安全风险是真实的，确实可能发生非常糟糕的事情——那也是我们关注的重点。

另外，我认为实际上要解决我提到的企业内部的这种上下文差距——也就是我们为了真正在各处创造价值而聚焦的事情——实际上我认为这需要 10 年时间。我认为这需要耗费 10 到 15 年。实验室里的人认为这会在接下来的 6 个月、12 个月或者 2 年内发生。但我其实认为 GDP 的变化会非常缓慢，我们需要十年的时间才能真正走过这个过程。为什么？我的意思是，就像我说的，只要回到一开始提到的那个轶事：那家银行的 CEO 说我们连会议都不能录音。如果你连会议都不能录音，AI 甚至不知道会议中发生了什么，它又怎么可能做到我向你展示 Genie 和本体模型时所讨论的那些事情呢？
<details><summary>Original English</summary>
>> If they're saying it themselves, right? That's how people think. But I for me, that risk is, you know, close to zero. I think the cyber risk is real and really bad things can happen without that's where we focused on it. You know, and then, you know, I think actually for to solve this this context gap that I mentioned in enterprises, the thing we're focused on to actually get value everywhere, actually I think it's going to take 10 years. You know, I think this is something that's going to take 10 15 years. The labs think this will happen like in the next 6 months, 12 months, in, you know, 2 years. But I actually think GDP will move very slowly and it's going to take decade for us to actually get through it. Why? I mean, as I said, I mean, just go back to the anecdote at the beginning, the you know, the CEO of the bank that said we can't even record the meetings. If you can't record the meetings, the AI doesn't even know what's happening in the meeting, how could it possibly do the kind of things that we discussed when I showed you Genie and the ontology?
</details>

>> 可以肯定的是，这必然是一个循序渐进的推广过程。我们当中有些人正跑在前面、在拐角处做着非常酷炫的事情，这与我们当年在互联网上经历的情况完全一样。当互联网最初出现时，那些充分利用它的人会觉得：好极了，这将会改变一切。而当时 99% 的人还在使用拨号上网，从未见过高速连接。所以他们的大脑根本无法想象出 YouTube，或者无限量的免费照片存储。根本讲不通。你怎么可能理解得了呢？
<details><summary>Original English</summary>
>> It's going to be a paced rollout to be sure. And there are some of us who are running ahead around the corners doing really cool stuff, which is exactly what we both experienced with the internet. When the internet first came out, the people who were using it to its fullest extent were like, okay, this is going to change everything. And then 99% of people were on dial up and had never seen a high speed connection. So the their brains couldn't conceive of YouTube or, you know, unlimited free photography story. Doesn't make any sense. How can you understand that?
</details>

### 历史回顾与节目收尾

>> 曾经有个叫罗伯特·莫里斯（Robert Morris）的年轻人，他用一个蠕虫病毒搞瘫了 10% 的互联网。它被称为莫里斯蠕虫（Morris worm）。
<details><summary>Original English</summary>
>> There was a kid called Robert Morris Morris who took down 10% of the internet with a worm. It's called the Morris worm.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 他差点为此坐牢。呃，后来他成了一位著名的 MIT 计算机科学教授，也是个非常出名的人物。但你看，当年那确实导致了整整 10% 的互联网瘫痪。
<details><summary>Original English</summary>
>> You know, he almost got a jail jail sentence for it. Uh and then he went on and he became a famous MIT professor in computer science and he's like a very famous guy. But you know, that took down a whole 10% of the internet uh back in the day.
</details>

>> 这是完全有可能的。就像在某一刻……我今天刚看到有人觉得他们可能在一定程度上破解了 Signal。呃，好吧，当然了。让我们拭目以待。好了各位，又是一期精彩的 All-In 访谈。阿里（Ali），非常感谢你的宝贵时间，我们下期 All-In 访谈再见。太棒了。做得好，阿里。你太出色了。
<details><summary>Original English</summary>
>> Which is completely possible. Like at some point I just saw today somebody feels like they may have cracked signal to a certain extent. Uh okay, sure. Let's see what happens. All right everybody, another great all in interview. Ali, thank you so much for your time and we'll see you next time on the all in interview. Boom. Great job, Ali. You are awesome.
</details>

>> [音乐]

[音乐]
<details><summary>Original English</summary>
>> [music]

[music]
</details>