---
author: All-In Podcast
date: '2026-11-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1bR0gtecoHU
speaker: All-In Podcast
tags:
  - ai-agents
  - data-governance
  - machine-learning
  - enterprise-software
title: Databricks CEO Ali Ghodsi 探讨公司起源、AI 落地挑战与企业数据治理
summary: Databricks CEO Ali Ghodsi 分享了公司从 UC Berkeley 研究实验室到商业成功的历程。他强调了企业在采用 AI 时面临的遗留系统、合规与安全挑战，并指出解决企业内部数据上下文差距可能需要 10 到 15 年的周期。此外，他讨论了 AI 带来的自动化生产力、Token 成本优化策略以及对网络安全风险的关注。
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
  - AmLab
  - Netflix
  - Google
  - Meta
  - Uber
  - MIT
products_models:
  - Genie
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

### 访谈预告与开场

所以，某种程度上是在绝望之中，我们创立了 Databricks，因为没有其他人在关注这个。在那个时候，人们对 AI 的兴趣为零。现在，我认为我们已经拥有了彻底改变这个星球所需的一切智能。
<details><summary>Original English</summary>
So, it was kind of out of despair that we started Databricks because no one else is listening to it. At that time, there was zero interest in AI. Now, I think we have all the intelligence we need to completely transform the planet.
</details>

>> 让一千个智能体在现实中做事情是不可能的。我说得对吗？
<details><summary>Original English</summary>
>> It's not possible to have a thousand agents doing stuff realistically. Am I correct?
</details>

>> 他们只是在以非常初级的方式使用 AI。他们只是把它当成美化版的谷歌搜索来用。
<details><summary>Original English</summary>
>> They're just using AI in very rudimentary ways. They're just using it as a glorified Google search.
</details>

>> 我们实际上正在进入管理层面的“魔球理论”（moneyball），不是吗？
<details><summary>Original English</summary>
>> We're actually getting into like management money ball, aren't we?
</details>

>> 那么，如果 token 成本呈指数级上升，你们公司的收入也呈指数级上升吗？但我实际上认为 GDP 的变化会非常缓慢，而且需要几十年的时间。
<details><summary>Original English</summary>
>> So, if the token cost is going up exponentially, is your revenue at your company going up exponentially? But I actually think GDP will move very slowly and it's going to take decade.
</details>

>> 他们是不是有点因自身的成功而冲昏了头脑？
<details><summary>Original English</summary>
>> Are they a little drunk on their own success?
</details>

>> 仅仅因为 98% 的代码是由 AI 编写的，我们并没有达到 RSI。如果它把最后 2% 也自动化了，谁在乎呢？
<details><summary>Original English</summary>
>> Just because 98% of the code is being written by AI, we don't have RSI. If it automates the last 2%, who cares?
</details>

>> 你们什么时候上市？
<details><summary>Original English</summary>
>> When are you going public?
</details>

>> 我打算孤注一掷。
<details><summary>Original English</summary>
>> I'm going all in.
</details>

### 赞助商信息

>> 如果你今天从第一性原理出发构建全球金融体系，你不会把它建立在拥有 50 年历史的遗留轨道上。你会构建 Aerovox，一个面向全球账户、卡片和支付的原生 AI 平台。它的设计初衷是让整个世界感觉像一个本地市场。其他公司正在向破碎的基础设施上强行接入 AI，但 Aerovox 从第一天起就是为智能时代而生的。停止支付遗留税，并开始在 aerovox.com/allin 构建未来。Aerovox，为未来而生。
<details><summary>Original English</summary>
>> If you were building a global financial system from first principles today, you wouldn't build it on 50-year-old legacy rails. You'd build Aerovox, one AI-native platform for global accounts, cards, and payments. It's designed to make the entire world feel like a local market. Others are bolting AI onto broken infrastructure, but Aerovox was built for the intelligent era from day one. Stop paying the legacy tax and start building the future at aerovox.com/allin. Aerovox, built for the future.
</details>

### Databricks 的起源与创立

>> 好的，各位。欢迎回到 All-In 访谈。我们非常幸运，因为（清嗓子）世界上所有这些杰出的领导者——CEO、政界人士、科学家——他们都看这个节目。他们是这个社区的一部分。Ali Ghodsi 就是其中之一。他当然是 Databricks 的 CEO，这是一家表现令人难以置信的私营公司。我不知道为什么它还没有上市。我想很多人都在问这个问题。我们今天会讨论这一点。

在 2015 年，他们的营收是 150 万美元。到了 8 月，或者说我听到的传闻，2026 年 8 月，Ali，年化运营营收达到 70 亿美元，同比增长 80%。显然，你们面临着很多竞争，比如业内的 Snowflake 等等。但这是一项极其出色的业务。我们将深入探讨你们如何利用 AI 来运营这家令人惊叹的企业。我们还会探讨递归自我改进（recursive self-improvement）。但欢迎来到我们的节目。或许你可以向观众介绍一下你在 Databricks 做些什么，以及它是如何变得如此成功的。
<details><summary>Original English</summary>
>> All right, everybody. Welcome back to the all in interview. We're so lucky because [clears throat] all of these amazing leaders in the world, CEOs, politicians, scientists, they they watch the show. They're part of the community. And Ali Ghodsi is one of those individuals. He, of course, is the CEO of Databricks, a private company that has been doing incredible. I don't know why it's not public yet. I think a lot of people are asking that question. We'll talk about it today.

In 2015, they were doing 1.5 million in revenue. It's August or the the rumor I heard, August 2026, Ali, $7 billion run rate growing 80% year over year. And obviously, you got a lot of competition, the snowflakes of the world, etc. But this is a tremendous business. And we're going to talk a lot about how you're using AI to run this incredible business. We're going to talk about recursive self-improvement. But welcome to the program. And then maybe you could tell the audience a little bit about what you do at Databricks and how it became so successful.
</details>

>> 好的，非常高兴能来。感谢你们邀请我，很期待这次交流。

是的，我们在 2013 年创立了这家公司。但如果你把时间往回倒退一点，在这之前，我们全都在加利福尼亚大学伯克利分校（UC Berkeley）。我们当时大约有 20 个人。我们其实是名为 AMPLab 的实验室成员，我认为那是当时全球最大的 AI 研究实验室。我们当时一直在努力探索：如何将数据处理与 AI 结合起来？

我们构想出了非常有趣的东西，但业界根本还没有为此做好准备。因此，我们试图让业界采用这项技术，但他们并没有接纳。所以，某种程度上是在绝望之中，我们创立了 Databricks，因为我们想，如果我们不围绕这个创办一家公司，就没有其他人在关注这个了。在那个时候，人们对 AI 的兴趣为零。实际上那时它被称为机器学习，而 AI 当时指的仅仅是机器人学。所以这差不多就是整个故事的开端。
<details><summary>Original English</summary>
>> Yeah, happy to do that. Thanks for having me on. Excited for this.

Yeah, so we started the business in 2013. But if you rewind a a little bit before that, we were all at UC Berkeley. There were about 20 of us. And we were actually part of a lab called Amplab, which was I think the largest AI research lab in the world at that time. And you know, we were trying to figure out how can we combine data processing with AI. And you know, we came up with really interesting things, but the industry was just not ready for it. So we were trying to get the industry to adopt this technology and they weren't. So it was kind of out of despair that we started Databricks because we thought, you know, if we don't start a company around this, no one else is listening to it. At that time there was zero interest in AI. Actually it was called machine learning at the time and AI was just robotics. So that's kind of like the beginning of the of the story.
</details>

### 企业核心数据与市场痛点

>> 对于那些平时不用这款产品、不在这个行业里的人来说，Databricks 产品套件的目标是什么？你们是做什么的？我知道你们今天发布了一些新产品，所以也很乐意谈谈那些。但从概念上讲，你们涉足得如此之早。显然，机器学习——谷歌就是建立在它之上的，还有 Meta 及其广告网络，许多有趣的服务，Uber 及其路线规划算法。也许我们可以谈谈 Databricks 是从哪里起步的，它演变成了什么，以及它是如何创造数十亿美元收入的。
<details><summary>Original English</summary>
>> And for people who don't use the product day in and day out, who aren't in the industry, what what's the goal of the Databricks product suite? What do you do? I know you released some new products today, so happy to talk about those as well. But conceptually, you got there so early. Obviously machine learning, Google was built on that, Facebook and their ad network, a lot of interesting services, Uber and their routing algorithms. Maybe we can talk a little bit about where Databricks started and and what it's become and and how it's generating billions of dollars in revenue.
</details>

>> 是的，最初的使用场景，实际上有史以来的第一个使用场景是在加利福尼亚大学伯克利分校，当时我们想帮助 Netflix 推荐更好的电影，以便人们观看更多电影。所以它就像是一个，你知道，推荐算法，是这样一个 AI 使用场景开启了整件事情。

接着我们想，更多的机构，可能每个机构都需要一个能够处理这种 AI 工作的数据科学团队。这在当时是相当大胆的想法。那时有很多人说：不，不，不，AI 只是用于广告技术的，广告公司才需要它。但我们认为：不，不，不，这将会是一个更大的市场。实际上我们内部进行了很多争论，我们当时并不确定它是否会爆发。于是我们投身其中。

后来当我们创办公司时，我们意识到他们为什么不这么做，为什么会这么难。因为基本上世界上所有的机构都陷入了停滞。他们拥有使用了 30 年、40 年、50 年的遗留软件。其中有些公司已经存在了 100 年。

事情进展缓慢。他们有大量的流程。有大量的合规要求，大量的监管要求，大量的安全要求。顺便提一下，近年来随着生成式 AI 的出现，所有这些情况变得更加严重了。

所以，我们当时在加利福尼亚大学伯克利分校的研究中所欠缺的，基本上就是我们没有考虑到安全性与治理。因此我们在最初几年所做的事情，就是去摸索如何运用这项技术，让你能够处理企业内部的所有数据。你知道，各个机构都有海量的数据。实际上人们并没有谈论过他们拥有的最重要的数据。任何公司拥有的最重要的数据，都是关于他们核心产品的数据。比如对你们这里来说，就是这个播客，也就是关于这个播客的数据。另一个人可能在卖保险；还有人可能在研发药物。最重要的是从中产生的数据。

这些数据不在 CRM（客户关系管理系统）里，也不在人力资源管理系统里。
<details><summary>Original English</summary>
>> Yeah, so the first use case actually, it was the first use case ever was at UC Berkeley when we wanted to help Netflix recommend better movies so that people would watch more movies. So it was like a you know, recommendation algorithm, AI use case that started the whole thing.

And then we thought, you know, more organizations probably probably every organization will need a data science team that can do this kind of AI stuff. And it was kind of bold at the time. There was a lot of people that said, no, no, no, AI is just for ad tech, the ad companies need it. But we we thought, no, no, no, this is going to be a bigger market. And actually we had a lot of debates internally. We weren't sure it was going to explode. So we got into it.

And then we realized when we started the company, we realized why they're not doing it, why it's so hard. Because basically all the organizations out there in the world are bogged down. They have legacy software that they've had for 30, 40, 50 years. And some some of them, you know, companies have been around for 100 years.

You know, things are moving slow. They have a lot of processes. There's you know, a lot of compliance, a lot of regulatory, a lot of security. By the way, all these things have gotten worse with generative AI in the recent years.

So basically what was missing from our research at UC Berkeley was that we didn't think about the security, the governance. So what we did the first bunch of years is that we figured out how do we take this technology that lets you process all your data in an enterprise. So you know, organizations have a lot of data. The most important data they have actually people don't talk about it. The most important data any company has is the data on the core product that they have. Like for you here, it's this podcast, you know, the data on that. Someone else might be selling insurance. Someone else might have, you know, a drug. It's the data that comes out of that.

That data doesn't sit in CRM. It doesn't sit in human resource management.
</details>

### 云计算与三大逆向押注

>> 是的，事实上，它过去甚至可能根本没有被记录下来。我记得在互联网早期，他们会问：嘿，你需要这个日志文件吗？我会说：好的，保留所有东西。然后他们会说：好吧，那每个月有 8000 美元的存储账单。我就会说：算了，删掉吧。

然后他们会说：好吧，我们可以把它汇总并保留其中一部分。我就想：谁会去看我们电子邮件的打开率呢？谁在乎那个？我们把邮件发出去就行了。但后来情况发生了变化。存储、算力和云计算是否是这场大数据运动的主要催化剂？然后最终演变为机器学习，这些算是这场运动中的里程碑吗？
<details><summary>Original English</summary>
>> Yeah, in fact, it probably wasn't even tracked. I remember in the early days of the internet, they'd be like, hey, would you like this log file? And I'd say, okay, yeah, keep everything. And they'd say, okay, well, you got $8,000 storage bill a month. And I'd be like, okay, delete it.

And they're like, well, we could roll it up and keep some of it. I'm like, well, who's ever using the open rate on our emails? Who cares about that? You know, we send the emails, that's it. But then that changed. And was storage and compute and cloud computing a major accelerant to this big data movement? And then eventually machine learning, those were kind of the waypoints in this movement?
</details>

>> 是的。在我们 2013 年起步之前，大家基本上都在运行自己的数据中心。当他们在运行自己的数据中心时，就必须采购机器。而这些机器是将存储和算力绑定在一起的。所以如果你的存储空间用光了，你就必须购买更多的机器。每个机构的 IT 部门都在忙于应付这件事。

云技术所带来的改变，就是彻底实现了去中心化，并将计算与存储分离，这样你就可以设想自己拥有无限的存储空间。你只需要把所有东西倾倒进去，对吧？如果数据变冷了，也就是数据变旧了，它懂得如何进行归档，从而使存储成本变得微乎其微。然后，你就可以获得想要多少算力就有多少算力的效果。接着，你当然可以开始在上面运行机器学习，随后 GPU 也出现了。所以这彻底改变了一切。

我们倾尽所有押注于成为一家纯粹的云公司。我们倾尽所有押注于 AI，即 AI 的各种使用场景，并且我们押注于开放和开源。而在当时，实际上这三个押注都充满了争议。大家当时——我和业内最重要的一家分析机构打过一个长期的赌，他们说这是一个战略性失误，你们会因为押注云而倒闭。

事实证明，我们成功的唯一原因正是因为这些押注，因为它们具有逆向思维，因为其他人并不同意这些观点。所以我们在很多很多年里取得了先发优势。最终，当我们恰好被证明是正确的时候，我们已经取得了长足的进展，规模也变得非常庞大，以至于势头已经势不可挡，无法……
<details><summary>Original English</summary>
>> Yeah. Before we started in 2013, basically people were running their own data centers. And when they're running their own data centers, you had to buy machines. And the machines came with storage and compute combined. So if you ran out of storage, you had to buy more machines. And the IT departments of every organization were busy with this.

What the cloud enabled was to just completely decentralize this and separate computer storage so that you could just imagine you have infinite storage. You just dump everything there, okay? And if it's gotten cold, so the data is old, it knows how to archive it so that it becomes almost free to store it. Uh and then you could get the illusion of as much compute as you wanted. And then of course you could start running machine learning on it and then eventually GPUs showed up. Uh so it kind of transformed everything.

We bet everything, the whole farm, on just being a cloud company. We bet everything on AI, the use cases of AI, and we bet on open and open source. And at the time actually all three of these bets were controversial. People were I had a standing bet with one of the most important analyst firms out there where they said it's a strategic blunder. You're going to go under because you're betting on the cloud.

And it turned out actually the only reason we succeeded was because of these bets because they were contrarian, because other people did not agree with them. So we got a head start for many many years. Uh and then eventually when we you know happened to be right then we had you know we were so far along and we gotten too big that you know there's too much momentum to to
</details>

<!-- chunk 2/9 -->

阻止它。
<details><summary>Original English</summary>
stop

 it.
</details>

### Netflix 奖与 AMPLab 的起源

>> 很有意思你提到了 Netflix 的算法。Netflix 很明显最早是在湾区起步的，当时是通过信封邮寄 DVD 给用户，然后你有一个排队列表。这极其重要，呃，给那些不知道 Netflix 奖的人科普一下，这是在 2008 到 2009 年期间，他们拿出了 100 万美元的奖金设立给任何一个计算机科学团队，只要能把预测你会给某部电影打四星还是五星的算法提升哪怕我认为是 10% 的准确度。所以他们就把所有的真实数据拿出来公开发布，然后大概获得了全世界计算机科学家价值 5000 万美元的研究成果。那是第一次出现类似 X Prize 的大奖，我觉得 X Prize 和呃这个奖项大概是在同一时期出现的，它们都受到了那些历史古老奖项的启发。比如谁能环球航行，谁能像阿梅莉亚·埃尔哈特那样单人飞越，谁能单人飞越大西洋或太平洋。那在当时是一个非常有趣的时刻，而那触动了 AMP，对吧？AMP 这个团队代表算法、机器学习，我不知道 P 代表什么。
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

>> 实际上 P 代表人（People），因为我们当时觉得，你知道，AI 还不够好。
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

>> 所以它需要一点点人类的推动。所以这实际上其实就是你所说的那种人类反馈，当时就已经存在了。我们当时觉得我们确实需要人类反馈，因为这最后的这一英里对于 AI 来说自己搞明白实在太难了。所以我们把人也放了进去。
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

>> 把人放进去是说得通的，因为伯克利有点嬉皮士风格。呃，显然那是弗雷伯格（Freyberg）的母校。［笑声］他们当时觉得，我们需要在中间加一些人。你知道，前几周本·霍洛维茨（Ben Horowitz）上过我们的节目做客，他说，关于为什么我们能够控制超级智能的推广，以及为什么不用担心从通用人工智能跨越到递归演化、失控狂飙并带来 P(doom)、导致我们所有人都会灭绝的超级智能，他所听过的最好的解释就来自于你。所以请解释一下你的论点，然后我想让你再更进一步，具体谈谈湾区、甚至可能是东湾的文化，以及这群人。
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

>> 我很乐意探讨这个话题。你知道，我认为同时有两件不同的事情在发生。一方面，我实际上认为我们已经拥有通用人工智能了。从去年开始我就一直在这么说，我的依据是我们在 AMPLab 时达成的某种共识，我认为它在 2009、2010 年是当时最大的 AI 实验室，而我们大多数人对 AGI 的定义，去年就已经实现了。其实我当时并不完全确定这点，所以我实际上还去和实验室里的一些人核对过，问他们：“嘿，只有我一个人这么想吗？我是出现幻觉了吗？”他们说：“不不不，按照那个定义确实已经达到了，只是大家挪动了球门柱。”

你知道吗？所以，呃，所以我其实认为我们已经拥有了所需要的一切智能。实际上，如果你碰巧在现在停止所有进展，我认为我们拥有的智能就已经足够去完全改变这个星球了。明白吗？但这就是那个想法。
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

>> 人类所做的所有智力工作，对吧？我的意思是，如果它能解决最新一批的数学难题，而我们才刚刚开始搭建测试框架并扩展基础设施，我猜你的说法应该是对的，我也在某种程度上赞同你的看法。我们已经达到了通用人工智能，只不过它还没有被分配，还没有被均匀地分配而已。
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

>> 是的。所以各家实验室和很多研究人员，他们有点痴迷于超级智能。好吗？所以当我提到超级智能时，呃，我的意思是指博斯特罗姆（Bostrom）在 2014 年出版的《超级智能》一书中所定义的那样。

在那里，他谈论的是一种完全不同的东西。他谈论的是一种能够完成相当于一千年思考的东西。

相当于人类一千年的思考量，它们可能在一分钟内就能完成。明白吗？全人类的量在一分钟内搞定。它在 11 维中思考。它快太多了。仅仅单个智能体就高出好几个数量级。想象一下比我们任何一个人都快上千倍。明白吗？那完全是另一回事了。就像它可以瞬间写出一篇崭新的博士论文等等。所以，我认为各家实验室都在追求那个目标。而且顺便提一下，在那之中——
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

>> 那么就总结一下你刚才说的，那种瞬间写出一整篇全新独创博士论文的能力，在你看来，我们今天到底有没有足够的算力去做成那样的事情？如果大家聚在一起说，嘿，今天接下来的一个小时里，仅仅作为一个思想实验，我们要把所有的算力都贡献给这个令人难以置信的超级提示词（mega prompt），你觉得它真的会发生吗？这是一个计算机算力的问题，还是一个模型的问题？
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

### 企业落地与上下文瓶颈

>> 嗯，实际上这些 AI 是有点慢的。我们必须要做的是把它们并行化，部署很多个，并且得让它们相互协作。呃，所以这实际上并不完全是他写下来的那种方式。他在书里也提到了智能，谈到了它可以是智能群体。但我只是说，各家实验室和许多其他公司都专注于这一点。这就是为什么他们对数学、对克雷数学难题、那七个千禧年难题等等痴迷不已。

但我认为，摆在我们面前最大的挑战是，我们实际上该如何让这种 AI 在企业组织内部落地应用？这才是 Databricks 所聚焦的。我们只是想帮助所有这些组织。而当我出去和那些组织、企业沟通时，
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

>> 嗯嗯。
<details><summary>Original English</summary>
>> Mhm.
</details>

>> 我看到他们只是以非常初级的方式在使用 AI。他们只是把它当成高级版的谷歌搜索在用。他们整天都在使用聊天机器人。不是自己在谷歌搜索里输入内容、拿到 10 个蓝色链接再去逐个查看，而是由 AI 帮他们代劳了。他们做的第二件事就是写代码。明白吗？而在写代码方面，其实他们并没有看到足够的提速。他们看到的提速可能只有 20% 到 30% 左右。我每天都会向他们提出这个问题。我每天都在和客户开会，并向他们询问这些问题。现实情况大致就是这个样子。我总会问他们，你们当中有多少人拥有数以千计的智能体在各处跑来跑去、自动化完成所有工作并替你们处理核心业务等等？这根本还没有发生。
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

>> 现在他们可能在运行半打或一打智能体。比如某个走在前沿的人可能确实在协调管理这么多智能体，但仍然需要有人参与其中（human in the loop），就像 AMP 那样。就像必须有一个人在里面，因为它会给出垃圾输出，会产生怪异内容，也可能会偏离轨道。从现实角度来看，拥有 1000 个智能体在做事是不可能的。我说得对吗？
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

>> 是的。嗯，有些走得更远一些。我的意思是，我自己在整个 Databricks 内部都在广泛使用这个，而且我很乐意向你展示。但你知道，现实情况是他们并没有这么做。那你就不得不问一个问题：这是为什么呢？如果它能解决纳维-斯托克斯非常困难的数学问题，那为什么外面的企业和组织会落后这么多？
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

>> 这是为什么呢？是的。
<details><summary>Original English</summary>
>> Why

 is

 that?

 Yeah.
</details>

>> 嗯，有很多原因，但最主要的原因，或者可以换一种角度来看，如果我们能够收集一个拥有 20 万名员工的大型组织内部拥有的所有信息，录制所有的会议——顺便说一句，就这件事本身，前几天一家大银行的 CEO 还对我说，绝不可能，我们绝不会录制会议，就算再过一百万年也不可能。但假设你拥有这些数据。

法律合规责任。我的意思是，顺便说一句，对此我已经有点震惊了，因为如果你做不到这点，AI 又怎么可能帮得上你？就好像 AI 根本不在会议里。如果它不在会议现场，它就毫无用处。无论你有陶哲轩（Terry Tao），还是拥有世界上最伟大的数学家，如果他们被排除在外、身处寒冬之中，不知道做出了什么决策或者你们正在做什么，而你正在与数十万名员工开会，他们绝不可能帮得上忙。所以如果你能捕获所有这些上下文并喂给 AI，它们就能精准解决那些问题。它们就能够帮助——
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

现在就已经在我们身上发生了。嗯，所以这确实就是上下文方面的问题。现在你可能会说，好吧，那我们来把这个问题弄清楚并解决它，而我们在 Databricks 也正在这么做，但这还不够。

即使你做到了这一点，你还会面临第二个问题，那就是，你知道，你可以放出像 Open Claw 这样的工具，直接让它访问你各处的所有数据。好吧，接下来你就会陷入被黑客攻击的困境。网络安全是实实在在的问题，所有拥有成功业务的大型机构，现在都非常害怕遭到攻击，对吧？这是一个重大担忧，最首要的担忧。
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

>> 当你拥抱这项技术时，确实会产生巨大的攻击面。我的意思是，如果是一位 CEO 或者在一家小公司里，你想要连接一切，那是某种程度的攻击面；但对于一个 20 万人的组织来说，哪怕是 1 万人，天哪，攻击面瞬间扩大了 1000 倍。
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

### 安全、成本与数据主权

>> 是的，完全没错。所以这就是你碰到的第二个问题，就像是：好吧，我们可以访问所有数据了。哎等等，我们可能并不想让智能体访问所有数据，因为你知道，现在我们面临内部威胁，而且我们可能会被黑客攻击。那我们该怎么办？好吧，就算我们也解决了这个问题。现在我们已经解决了网络安全问题——顺便提一句，我们在 Databricks 其实有办法做到这一点，很乐意展示给你看。

然后你依然会遇到另一个问题，那就是：好吧，现在 token 成本正在呈指数级上升。如果 token 成本呈指数级上升，那你们公司的收入是否也在呈指数级增长呢？而据我所知，还没有哪家公司在开始使用 AI 后，其收入会因为使用 AI 而开始呈指数级加速增长，以匹配他们的成本曲线。

所以到头来，一开始 CEO 们都觉得：去引入 AI，多搞点 AI，把它部署进去，你知道，我们需要在这方面动作更快一点。
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

>> 这件事。是的。
<details><summary>Original English</summary>
>> thing.

 Yeah.
</details>

>> 没错。但随后在某个时刻，CFO 就会出现并说：“嘿，我们这里的运营支出在大幅增加，甚至营业成本也是，我们该怎么应对？而且我们马上就要开财报电话会了。”接着他们就慌了。那么我们该如何解决这个问题？所以你也需要高效地进行这项工作，关于这一点，我们在 Databricks 同样有应对的方法。

现在，你把这三件事都做完了，然后依然还剩下一个具有战略性的终极问题，那就是：好的，行吧。我们把问题解决了，我们访问了所有数据，做好了安全防护，并且你也知道，我们搞定了成本状况。那我们如何避免被锁定？我们又如何拥有自己的 IP 知识产权？因为你知道，否则的话，未来就无生意可做了，因为……
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

>> 数据主权，你指的差不多就是这个，智能主权。如果你使用 Anthropic、OpenAI 或任何这些平台，就存在这种风险：它会泄露出去，会被整合进他们的下一个版本中。正如我们所见，一家名为 Anthropic 的公司似乎每两周就会发布半打产品，而现在他们正在与微软竞争，微软是他们的……我认为微软像是他们的巨头合作伙伴之一。而他们刚刚推出了……呃，基本上就是一个 Excel 杀手，他们正在干掉 Photoshop。我的意思是，他们简直就是在全面打击所有人。
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

>> 是的，所以这四个……是的。是的。顺便说一下，这些公司太棒了。他们做着了不起的工作，没有他们，我们可能根本不会拥有这种智能。

所以你知道，我很感激，这很棒。我只是在指出，为什么当你环顾四周时，所有这些成功的组织，所有的全球 2000 强，所有的财富 500 强，纳斯达克等等，为什么大家用的都只是高级聊天机器人加一点点写代码？

这就是原因。所以你确实需要把这四个问题全都解决掉，只有在那之后，你才能真正开始从中获得价值。
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

### 数据治理与组织架构突破

>> 我认为其中一个问题还在于，组织内部提出突破性想法的自主权。你知道，你可能已经占据了大部分市场份额，可能正在获得渐进式的好处。所以如果我告诉你：“嘿，我们可以给你的福特金牛座（Ford Taurus）再加 500 马力”，感觉就像是：

好的，我的福特探险者（Ford Explorer）现在多了 500 马力，但这会把底盘扯碎的，这玩意儿根本没办法跑时速 500 英里。那么接下来就是：究竟由谁来决定我们要推出另外三条产品线？好吧，在 Databricks，总有人在做决定。

我们为什么不直接去抢占全世界的所有业务呢？然后他们开始做仪表盘了。那离你们的业务有点近了，不是吗？在这边搞点仪表盘？
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

>> 是的，关于仪表盘，你知道，我们没有、我们没有一款按仪表盘收费的产品。仪表盘通常是以数据为后盾的，而你通常希望这些数据是受到治理的。所以你不会希望只是拿到一堆数字，然后那些数字还是错误的。这在组织里是个大问题。所以这又回到了我说的第二点，即治理和安全的维度，明白吗？就像是，是的，也许我们可以访问所有数据并获取所有上下文，但我们必须保证它的安全性。

所以是的，这很棒。因此你实际上可以把所有这些外部智能体连接到 Databricks，但我们是受治理的数据存储库。然后当你访问那些数据时，你知道，还有治理，我们对这些收取消耗费用。所以实际上这也是你看到我们业务加速的原因之一，因为所有这些公司，无论何时只要他们拥有智能体并在使用它，那么——我认为我们现在还只是处于开端。正如我所说，我依然认为目前主要还是谷歌搜索和写代码，但是当智能体开始使用那些数据时，它们就只会向我们发送更多的查询。
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

>> 当人们真正接纳智能体技术，并且开始与智能体一起工作——比方说像你我一样，在一天当中的每个小时或每隔一个小时都在使用——行为会发生改变吗？
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

>> 我认为组织结构、组织架构图就是这样建立起来的。你知道，就像一种树状结构。最顶端是一位 CEO，所有的决策制定在这些组织架构图里差不多都是自上而下、自下而上地流动。而且你有着所有这些老旧的流程，在一家企业或者任何具有相当规模的组织内部，要跨越这种组织架构图达成一致是非常、非常困难的。在达到邓巴数（即 150 人）之前，这还算比较容易，你能认识每一个人。所以对于小型初创公司来说，那是另一回事；但超过 150 人之后，这就变成了一个协调问题。

但是如果你看看任何组织实际上究竟是如何向其客户销售产品或服务的，它其实并不是这种层级化的形态，它实际上是横切穿过那张组织架构图的。你知道，就像在 Databricks 这里，我们有客户，他们给我们反馈。反馈流向产品管理部门，产品管理部门把它交给工程研发部门。工程研发部门做出产品，流向市场营销部门进行推广，然后营销部门再把它交给销售部门，销售部门再次把它卖给客户。所以你其实想要横向贯通，你想要消除那种延迟，这样你才能变得非常、非常快。

但这需要你拥有一个真正理解你整个业务、理解你的 IP 知识产权的 AI。它需要理解你的组织架构图，它需要知道谁是谁，谁负责……
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

 you know,

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

>> 在你看来，真正理解你刚才所描述内容的组织有多少？有 10% 的组织能理解这一点吗？还是 5%？
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

>> 在规模化层面上，我不知道有多少，我不知道这个问题的答案。在规模化层面上，我知道 Databricks 正在这么做，我也正在这么做。
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

>> 说实话，我还没看到其他人以这种……你知道……

我认为大概 Block 和 Square 的杰克·多西（Jack Dorsey）在做，因为他正在推进——他把它称为“公司世界模型”（company world model）。他把某种程度上我所描述的同样的东西，我认为，你知道，一种不同的看待方式，他称之为公司世界模型。所以我认为他们大概走得很靠前。总体而言，我认为数字化原生企业可能走得更靠前一些。

数字化原生企业也就是只存在了 10 年、15 年的公司。你知道，如果你已经存在了 20 年、30 年、40 年、50 年，这本身只说明你是一家了不起的公司，也许你是一家财富 500 强企业，是全美最好的公司之一。你可能有大约 10 万名员工，你知道，他们很忠诚，你知道，他们热爱你们的产品，而且你知道，就那些方面而言你们是全世界最优秀的。但你们只是拥有太多的软件了，你知道，你们面临着如此多的监管，围绕安全等等有着如此多的流程，以至于……
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

去采用这个会非常困难。但那正是 Databricks 想要为他们解决的问题。所以我们希望他们能够采用这些技术，让 AI……这样他们基本上就能做到我在 Databricks 所做的事情。
<details><summary>Original English</summary>
very hard for you to adopt this. But that is the very problem Databricks wants to solve for them. So we want it we want them to adopt the technologies so that the AI so that they can do what what I do at Databricks basically.
</details>

>> 行啊，让我们看看吧。你说过你愿意向我们展示一下你是如何利用 Agent 和 AI 来运营 Databricks 的。我整天都在期待这个，因为在你调出界面的同时，我真切地在把我做播客和早期投资的整个生活——我正在把这些事情中的每一个组成部分看作服务、看作 Agent，定义目标，然后逆向推导：哪些迹象表明你正在朝着目标迈进，而不是表明你已经实现了目标。实现目标有点非黑即白，是或否。你达成了交易，或者你没达成。但前置的先行信号是什么？然后试图让这些 Bot 互相来回交接工作。这……
<details><summary>Original English</summary>
>> Yeah, let's see it. You said you would be willing to show us like how you run Databricks with agents and and with AI and I I'm been looking forward to this all day because I I literally am taking the entire while you queue it up my entire life on podcasting and on early stage investing and I'm looking at each of the components of those things as services, as agents, and defining the goal, working backwards to what are the signs of success that you're heading towards the goal, not that you've achieved the goal. The achieving the goal is kind of binary, yes or no. You made the sale, you didn't. But what are the precursor signals? And then trying to have each of these bots hand off things back and forth. It's
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你必须是一个真正的系统思考者。这有点像一边骑着马，一边同时下五盘国际象棋。我是说，你……这真的在智力上让我觉得超级刺激。我看得出你也这么觉得。所以你可以在这里共享你的屏幕，然后……
<details><summary>Original English</summary>
>> you have to be a real systems thinker. It's like kind of playing five chess games at once while riding a horse. I mean, you're it's really like intellectually I find it super stimulating. I I can tell you do, too. So here you can share your screen and
</details>

### Genie 产品与企业知识本体

>> 那我们就直接切入吧。好。所以这里的关键在于我们有一款名为 Genie 的产品，但 Genie 具备的关键之处在于——因为你知道，市面上有那么多聊天机器人，有那么多助手，市面上有那么多协作办公产品，后台还有各种 Agent。
<details><summary>Original English</summary>
>> So let's jump in. So okay. So the key thing here is that we have a product called Genie, but the key thing that Genie has cuz you know, there's so many chatbots out there and there's so many assistants and there's so many co-work products out there and agents in the background.
</details>

关键之处在于它拥有一个知识本体（ontology）。
<details><summary>Original English</summary>
The key thing is that it has an ontology.
</details>

这个知识本体是一个它在不断为你的公司构建的图谱。
<details><summary>Original English</summary>
The ontology is a graphs that it constantly it's constructing for your company.
</details>

那个图谱了解所有的人、谁向谁汇报、他们在做什么项目、正在收到的电子邮件有哪些、开过了哪些会议、所有这些会议的转录文本是什么，以及在会上正在做出的所有决定是什么，Slack 上有什么内容、正在沟通什么。
<details><summary>Original English</summary>
That graph understands all of the people, who reports to who, what are they working on, what are the emails that are coming in, what meetings have happened, and what's the transcripts of all those meetings and all the decisions that are being made there, what's on Slack, what's being communicated.
</details>

所以它可以访问所有这些东西，而且还可以访问你正在创建的所有文档、所有的 Excel 表格、所有的 PowerPoint 演示文稿。所以它能访问所有这些。这就是我们在这里所说的 Genie，这样你就能在这里看到。所以我早上醒来，它……你知道，我有……它有一个收件箱。早上当我进来时，它基本上已经为我做了一堆后台工作。它是全天候 24/7 运行的。正如你所看到的，它可以访问我的日程表。事实上，我可以随便问它，比如：
<details><summary>Original English</summary>
So it it has access to all of these things and then also all of the docs that you're creating, all the Excel sheets, all the PowerPoint presentations. So it has access to all of those. That's what we call Genie here so that you can see here. So I wake up, it you know, I have an it has an inbox. In the morning when I come in, it basically has done a bunch of background work for me. It's running 24/7. As you can see, it has access to my you know, calendar. In fact, I could just ask it like you know,
</details>

>> 我今天在 All-In 节目上对 Jason 说了什么？这就出来了。
<details><summary>Original English</summary>
>> What did I tell Jason on all in today? Here it goes.
</details>

>> 所以你看它会说什么。
<details><summary>Original English</summary>
>> So you see what this is going to say.
</details>

### 分析员工调查与行动反馈问题

不过让我们来看一些我做过的事情。比如前几天，一件有趣的事情是，我看到我们的 HR 部门回过头来说：嘿，我们对整个 Databricks 做了一次调查。你知道，我们有超过 10,000 名员工回复了调查。我看了看结果，她正在过这些内容，我就说：嘿，帮我把结果做成一个仪表板。目前这里还没有什么神奇之处。于是它告诉我：看，这是你们目前的情况。你们在某些方面做得很好，但你知道……
<details><summary>Original English</summary>
But let's look at some of the stuff that I've done. So like actually the other day, one of the interesting things is I was looking at our HR department came back and they were saying, hey, we've done survey on all of DataBricks. You know, so we had over 10,000 people, employees that responded to the survey. And you know, I looked at the results and she was going through it and you know, I said, hey, make me a dashboard of the results. Uh, you know, nothing magical here yet. So it told me like, look, here's how you're doing. You're doing great on some things, but you know
</details>

>> 执行领导力，88%。你们做得还可以。
<details><summary>Original English</summary>
>> Executive leadership, 88%. You're doing okay.
</details>

>> 是的。你知道，这是……
<details><summary>Original English</summary>
>> Yeah. You know, it's
</details>

>> 融合度（blend），60%，说明你们那边让员工工作挺辛苦的。但我是说，大家都会这么说，对吧？
<details><summary>Original English</summary>
>> blend, 60% that you're working people pretty hard over there. But I mean, everybody says that, right?
</details>

>> 是的。不，但我们想知道……但这一直是……所以我们想要改善这两项。而这个“行动”（action）项真的很让我困扰，因为你知道，顺便说一下，“行动”的意思是，当我们向他们征求反馈时，他们给我们反馈，说改善这个改善那个。而他们觉得你们没有在听我们的意见。
<details><summary>Original English</summary>
>> Yeah. No, but we want to know but this is this has been So we want we wanted to improve these two. And this action one really bothers me because um you know, it's Action, by the way, it means that when we we ask them for feedback, they give us feedback, improve this and that. And they feel like you're you're not listening to us.
</details>

>> 呃，所以三分之二的人觉得你们在听。三分之一的人觉得你们没有。只是为了……你们做得还可以。顺便说一句，这并不算糟糕。这数字完全有可能是 30% 左右。
<details><summary>Original English</summary>
>> Uh, so two out of three feel you are. One out of three feels you're not. Just to You're doing okay. It's not terrible, by the way. This could be like 30%.
</details>

>> 60% 算不上好。尤其是如果你真正考虑到每年这个数字都很低，而且每年我都向全公司承诺我们要解决这个问题，但每年都没有兑现。所以，我们正在查看结果，正在和员工们讨论，在他们讨论的时候，他们就在推测。我的首席财务官说：“我认为这是因为工作与生活融合（work-life blend）的问题。工作与生活融合很差，导致了行动反馈得分下降。”所以说是工作与生活融合导致了低行动得分。我就觉得，这根本说不通啊。但就在我们讨论的同时，我直接把它输入到了这里，它立刻就调出来了。好的，这是这两者之间的相关性。情况是这样的。但接着我就想，好吧，哇，也许他是对的。但随后它显示：不，实际上它们不存在因果关系。并不是它导致的。这里有确凿的例证。我们可能得把这些人的信息匿名化，但这是一位管理者的工作与生活融合得分是 44。这相当糟糕。但行动得分是 77%。所以你看……
<details><summary>Original English</summary>
>> 60% is not great. So but and especially not great if you actually take into account that every year it's low, and every year I promise the company we're going to fix this, and every year it doesn't happen. So, you know, we're going through the results, and you know, we're discussing it with the staff, and while they're discussing it, they're speculating. Um, you know, my CFO says um you know, hey, I think it's because of work-life blend. Work-life blend is bad, you know, and that's causing action to go down. So it's causing Work-life blend is causing low action. And I was like, that doesn't make any sense. Uh, but I just entered it here immediately as we were discussing, and it immediately pulled up. Okay, this is the correlation between these two. And this is how it's looking. But then I was like, okay, wow, maybe he's right. But then it says, no, actually it's not causal. It's not causing it. And here's the exact proof point. We probably have to anonymize these folks, but it's a Here's a manager that has work-life blend 44. That's pretty bad. Action is 77%. Uh, so you know,
</details>

>> 他们的员工工作很辛苦，但他认可并针对他们的顾虑采取了行动。所以……
<details><summary>Original English</summary>
>> They're working hard, and he's recognizing and taking action on their concerns. So
</details>

>> 于是我就说，那就是你要找的人。他严格要求大家，同时也倾听他们的声音。我喜欢他这一点。所以我就想，好，现在我对这个组织有了新的了解。这太神了。如果让数据团队帮我做这个分析，本来得花我大概一周的时间，但这只是我获取信息的过程。这很有用。所以我们稍微减少了组织架构上下沟通的延迟。但接着我就想，好的，为什么这个得分会低呢？并查看了所有的评论。它给了我一些原因。我不喜欢那些原因。于是我进一步明确了问题，我说：嘿，能帮我按部门细分一下吗？
<details><summary>Original English</summary>
>> So then I said, that's your guy right there. He's pushing people hard, and he's listening to them. I like that about him. So I said, okay, so now I'm learning stuff about the organization. This is amazing. It would have taken me like a week to get the data team to do this analysis for me, but that's just me getting information. That's useful. So like we're cutting this, you know, latencies up and down the org chart a little bit. But then I'm like, okay, why is it low? And look through all of the comments. And it gives me some reasons. I didn't like the reasons. So then I actually clarified the question and I said, hey, can you slice it by department for me?
</details>

>> 嗯。
<details><summary>Original English</summary>
>> Mm.
</details>

>> 然后它其实就弄明白了。它指出：看，产品管理部门的行动得分低，是因为他们不喜欢……决策过程有太太太多利益相关者了。工程部门，他们不喜欢工具和系统。有太多这类东西了。销售运营部门，则是因为职业发展等等。所以……
<details><summary>Original English</summary>
>> you know, and then actually figured it out. It said, look, product management has low action because they don't like decision making is too too too many too many stakeholders. Engineering, they don't like the tools and systems. There's too much. You know, sales operations is career growth and so on and so forth. So
</details>

>> 这说得通，因为销售人员总是认为自己应该升职，因为他们是销售人员，而且他们应该提高提成比例。［笑声］而产品人员则认为你应该直接听他们的……六个人试图去设计一件艺术品。现在所有这些通过数据和 AI 都能对得上了。太棒了。
<details><summary>Original English</summary>
>> That makes sense because sales people always think they should get a promotion because they're sales people and they should get their commissions raised. [laughter] And product people think you should just listen to them of, you know, six people trying to design a piece of art. This all starts to track now with the data and the AI. I love it.
</details>

### 深入图谱结构与管理幅度分析

>> 是的。那么它是怎么做到这点的呢？它可以访问它的知识本体。所以它不只是去进行实时搜索。它实际上发现图谱中已经有了这些人。已经有五个人对这个做出了贡献，正如你所见，这里有 19 条它实际利用的信息，是它早就掌握的。它并没有去实时搜索它们。这些都存在于知识本体中。所以我们可以看，比如，这具体的一个。如果你点击它，它有一个定义，这是一个指标，还有一个图表。你可以在这里看到这个图表。这里有一个支持度（favorability），它来自于……这是作者。你可以点击作者，因为系统理解组织架构图，所以他们明白这个人是谁。这个人实际上有 29 个代码或文本片段。他们拥有许多不同的资产，都是系统从他们身上学到的。所以系统在不断学习你组织的智能或知识本体。
<details><summary>Original English</summary>
>> Yeah. So how did it do this? It has access to its ontology. So it's not going and searching live only. It actually found that there's already already had in its graph these people. You know, already five people had already contributed to this and there's 19 pieces of information here that you can see that it's actually leveraging that it already had. It didn't search for them live. These are in the ontology. So we can look at, for instance, this particular one. If you click on it, it has a definition, it's a metric, and there's a graph. And this graph you can see it here. You know, so there's a favorability and it came from, you know, this is the author. You can click on the author and because it understands the org charts, they understand who this person is. This person actually has 29 snippets. You know, they have lots of different assets, you know, that they've you know, that it's learned from them. So this constantly is learning the intelligence or ontology of your organization.
</details>

所以这是一个很典型的事情。这里还有另一个可能挺有趣的例子。我想知道……实际上在过去 59 分钟里这里有新的结果。我其实还没看完所有这些，但我想了解组织架构图，以及组织架构图和管理幅度（span of control）的情况。我问了它，在开箱即用状态下它其实就……我对这个感到震惊。邮件告诉我，比如：嘿，Databricks 内部有一个层级非常深的组织。这个人向这个人汇报，向这个人汇报，向这个人汇报，但他们有三个人向他们汇报，五个人向他们汇报，四个人向他们汇报，五个人向他们汇报。所以，那并不是一个扁平化的组织。然后你就可以看，好的，对此我们能做些什么？同样，由于它了解所有的人，它立刻就能开箱即用地理解他们。工程部门的成本。成本是我们可以……
<details><summary>Original English</summary>
So that's a that's a, you know, typical thing. Here's another one that, you know, is maybe interesting. I wanted to know actually there's new results here in the last 59 minutes. I haven't actually looked at all of those, but I wanted to understand the org chart and what's going on with the org chart and, you know, span of control. And I ask it and already out of the box it was actually it's I was shocked by this. The email told me like, hey, there is an org inside DataBricks, which is very deep. You know, this person reports to this person reports to this person reports to this person, but they have three people reporting to them, five people reporting to them, four people reporting to them, five people reporting to them. So, that's not a flat organization, you know? So then you can look at, okay, what can we do about that? Again, it understands, since it understands all the people, it can immediately out of the box understand them. Engineering, you know, cost. Cost is, you know, something that we
</details>

<!-- chunk 5/9 -->

根本不看。而且，你知道，所以这也是我们想看看能否搞清楚的另一件事。
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

### 数据驱动的文化与工程交付差异

>> 这点也非常棒，领导者不必再说：“嘿，听着，如果有不同意见，就按我的来”，而是建立了一个大家以数据为先、验证假说的平台。你不必执着于到底是谁提出了这个假说，只需保持求知欲，对各种可能性敞开怀抱。

而且到最后，如果今天我们已经做到了这一步，你能想象一两年后会是怎样吗？到那时，它不再只是通过文化报告来呈现，而是会成为公司里的温度计。就像你看着公司里的 Nest 温控器，然后发现：“噢，哇，今天看起来有点热。发生什么事了？”接着发现：“噢，对，这个周末我们让大家加班了。也许我们该买点披萨，或者在感恩节期间给大家补休一天。”
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

>> 对，这是我最喜欢的部分。这个实际上出自 Genie。这里展示的是我们 2000 名工程师，以及他们实际发布到生产环境的代码或 Pull Request 数量。你看中间这里，大概是每周的数据。但它呈现出这种 L 形，你看这个 L 形，排名最靠前的人实际提交的代码量要多得多。
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

>> 所以这是怎么回事？对啊，这到底是怎么回事？于是我们对此进行了调查，结果发现他们运行的是自动化工厂，而其他人没有。所以我们去督促其他人。顺便提一句，我问了一个很有意思的问题：“嘿，能不能在这个图里加上成本，把成本加到这条线上？”我们发现的其中一件趣事是，那些人的成本其实未必更高。你看最顶部这里。
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

### 会议记录与自动化洞察

>> 最靠前的那批人，有些人花费的成本其实并没有其他人高。顺便说一句，这又回到了那个问题——存在以聪明的方式消耗 Token 的方法。你可以使用开源模型，可以将较简单的问题路由到较简单的模型，我们其实就有一款针对这个的产品。呃，你可以显著降低成本。嗯，所以就是这类事情。

顺便说一下，记录会议也非常重要。嗯，比如我听说有一场客户会议，我想了解那款产品……呃，那场会议开得怎么样。你知道，呃，我就直接问它：“嘿，最近有和这位客户开会吗？情况怎么样？”它开篇就直接说：会议开得很糟糕。
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

>> 它列出了……准确列出了说了什么、谁说了什么、他们需要哪些功能。呃，所以，你知道，嗯，这些只是你可以用 AI 做的一些事情。而且在后台，等我醒来时，它已经为我做好了所有这些深入分析。因此，我不用醒来后四处打电话、开会，它已经替我把工作做好了。它在给他们发消息提醒，在发送……你知道，公司所需的各种材料。所以它直接压缩了做事情所需的时间。呃，
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

### 穿透信息粉饰与消除人为阻碍

>> 但你知道，做管理和当创始人在很大程度上就是侦探工作。如果你还记得《神探可伦坡》（Columbo）那部电视剧的话，我称之为当“可伦坡”。我想这可能暴露了我们的年龄，但你就像是在说：“噢，你知道，还有一件事。能跟我说说那场会议、那个客户会议吗？情况怎么样？电话里谁讲得最多？他们讲了多大比例的时间？客户到底是怎么想的？”然后作为创始人的你，就会被各种粉饰。

你会被粉饰。而且这倒不是说员工一定想糊弄你。团队成员并不一定想糊弄你。这种情况可能会发生，但不是大多数。大多数人都是好人。
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

>> 是的。

是的。
<details><summary>Original English</summary>
>> Yeah.





Yeah.
</details>

>> 他们有……他们是人，对吧？他们是局中人。
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

>> 对。
<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而在这里，你把人从那场讨论中剥离出来，你说：这是第一性原理，透明地还原发生了什么。现在我们有了基本事实，大家可以展开讨论，而无需作为 CEO 的你必须去扮演侦探先生。而且你知道，这实在是……我的意思是，我不知道两年前花两个小时去当侦探对你来说有多沮丧。

你开到第三场会议，就会发现：要是大家当初直接告诉你发生了什么，或者要是你手头有那份关于文化的报告，问题早就解决了。你就不必经历三周的焦虑苦恼了，对吧？
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

>> 是啊，或者说是客户反馈，对吧？我能立刻了解到所有客户……我，你知道，有些客户会议，我不仅让它自动从我们所有的客户会议纪要中提取所有客户请求的功能。它直接收集这些需求，然后立刻传给工程团队，接着工程团队里有工厂能够自动构建这些功能。

呃，所以这是彻底改变游戏规则的。你知道，这就好比我们小时候玩的传话游戏，对吧？就像当人们必须碰面、必须去转述的时候那样。所以我们的主要目标之一就是，呃，减少人为阻碍的数量。因此我们在整个组织中对这一指标进行衡量，我们直接观察，你知道。
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

>> 请解释一下这里的“阻碍”（blocker）。这是我可以学习的东西。
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

>> 好的，我的意思是 AI 非常快，对吧？它在后台不断迭代，做着自己的工作，准备材料等等。但在某个时刻就会变成：好吧，现在我们需要去找法务，确保我们被允许做这件事。或者现在我们需要去找，呃，你知道，财务来审批这笔预算。或者现在我们需要确保市场部同意……呃，同意这个。或者其实就在同一个组织内部，我们需要去跟兄弟部门沟通，跟他们开个会，看看他们怎么想，我们必须达成一致。而如果我们无法达成一致，我们就会再安排一次会议重新讨论。然后如果那次会议还是不行，也许我们就升级到管理者那里，以此类推。这些就是拖慢组织步伐的阻碍。
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

### 决策追踪与机器人监测

>> 发现器，如果你是 CEO 的话这太棒了，因为接下来就是另一件事。一件是你得当侦探，另一件就是推卸责任的博弈。我们总是在问：“是谁？为什么这个还没做完？”而当你是一名管理者，不管是你的团队还是另一个团队，“嘿，我们本来应该在今天之前完成这个的，我们本来应该达成这个目标的，谁负责？”然后你就会看到三个蜘蛛侠互相指责，如果你知道那个梗图的话。
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

>> 而在这里，情况就像是：“哇，实际上是这部分数据还没解决，而你的团队什么都没跑起来。”我也有过类似的经历。我做了一个机器人，本来打算分享给全公司，谢天谢地我没这么做。但我做了一个机器人，就叫“重大决策”。

我直接对它说：“进入 Slack，以我的身份加入每个房间。直接以我的身份加入每个频道”——有些人当时就觉得：“等一下，你怎么连我们有个房间都知道？”“加入每个房间，阅读每一个 Notion 页面，不管我有没有被邀请。获取每封电子邮件，帮我找出这个月的，每隔两三天给我一份报告，列出最重要的决策、谁参与了这些决策、解决方案是什么，以及还有什么是未解决的。”

然后我说：“把在这类讨论中参与最多的人列给我。”接着我意识到：“噢，哇，这些人才是组织里真正在做决策的人。这些人是反应最快的。”而我的下一份报告将是：谁最先对那些讨论做出贡献？现在，在一家风投机构里，讨论会是诸如“我们该不该投资？”“我们要不要追加同比例跟投（pro rata）？”“如果有人提出二级市场要约收购，我们要不要卖出股份？”在播客团队里则是：“我们该不该约这位嘉宾？”“我们应该用这个片段还是那个片段？”

然后它还捕捉到了人事讨论。

讨论就像是：“我们该不该解雇这个人？”或者“你知道，我们要做绩效改进计划（PIP）吗？”我的态度是：我们不做 PIP。我就是觉得 PIP 很荒谬。就像是，绩效根本没达到，这就像是那个人根本没来上班一样。
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

 That

 like





the

 person

 didn't

 show

 up.
</details>

<!-- chunk 6/9 -->

>> 折磨他们两个季度。
<details><summary>Original English</summary>
>> Let's torture them for two quarters.
</details>

>> 是啊，就像你缺席了训练，比赛还迟到了。这是底线要求。如果你连这些都做不到，你就不能留在队里。所以你……现在我们要折磨你，试图逼你准时来上班，或者去做你不想做的体能训练。所以也许你能谈谈，作为创始人和 CEO，这在帮你弄清队里谁是全明星、谁是真正在做贡献的人方面，会带来什么作用？因为我们现在基本上触及了商业层面的“魔球”（Moneyball），就像电影《魔球》那样。那部电影太棒了，布拉德·皮特演的。那真是一部好电影，一本好书。我们实际上正步入管理层面的“魔球”时代，不是吗？
<details><summary>Original English</summary>
>> Yeah, like you you missed practice and you showed up late for the game. That's table stakes. You can't be on the team if you can't do those things. So you now we're going to torture you to try to make you come into work on time or do a workout you don't want to do. So maybe you can speak to what this is going to do for you as a founder and a CEO in terms of figuring out who are your all stars on the team. Who are the ones who are actually contributing? Because now we're getting to essentially business moneyball, like that movie Moneyball. It's fantastic, Brad Pitt. It's such a good movie, such a good book. We're actually getting into like management moneyball, aren't we?
</details>

>> 没错，完全是这样。不过我的意思是，我最喜欢的问题之一就是直接看各个不同的组织，因为我们有特定的文化原则：追求真理、第一性原理等等。然后我说，嘿，这些领导者里谁遵循了这些原则？去查看他们的整个组织，查看所有的会议，你就能从中推导出来。顺便说一句，你甚至可以问，嘿，这位领导者实际在推行的是什么文化？它会给出不同的……你知道的，他们会告诉你，不，那里的实际文化其实是这样的，而不是公司的文化——呃，这至关重要，对吧？
<details><summary>Original English</summary>
>> Yeah, absolutely. But I mean, one of my favorite questions is just look at different orgs because we have certain culture principles, truth seeking, first principle, and so on. And I say, hey, which of these leaders follow these principles? Look in their whole orgs, look at all the meetings, and you can derive from those. And by the way, you could even ask, hey, this leader, what is the actual culture they're implementing? And it'll come up with different, you know, they'll tell you, no, actually the culture there is this, not the company culture, uh, which is essential, right?
</details>

>> 偏离了核心原则。这种偏离对身为创始人的你来说就像毒瘤一样——或者这可能是你需要去改变的事情，也可能是一个早期预警信号。
<details><summary>Original English</summary>
>> deviating from the core principles. That's that drift is cancer- for you as a founder, or it could be something you need to change and could be an early warning sign.
</details>

>> 我们需要保持一致，不论它究竟是什么，对吧？也许他们是对的，而包括我在内的整个组织其余人都错了，但这至少告诉我存在分歧，我们可以某种程度上……你知道的，所以这类事情以前几乎是不可能做到的。就像……就像很多其他事情你本可以做到，但像这样一个问题——比如在一个12……你知道的，12,000人的组织中去了解某个子群体的文化；你知道的，去弄清楚 Data Bricks 日本组织的情况。我甚至不会说日语，你知道的，而我们在那里有数百人在工作。那里的文化是什么样的？我们如何做决策？它与欧洲、中东和非洲地区（EMEA），或者你知道的，拉丁美洲拉美……拉美地区有什么不同？所以这些都堪称颠覆性的改变。对我们来说，我其实会把所有这些信息与员工分享。他们自己也可以访问所有这些内容，然后我告诉他们，这就是我们想要的。就像那条 L 型曲线，我们希望将它向右移动。所以大家，让我们来改变它。让我们……让我们朝着我们共同拥有的这个北极星指标迈进。

这也帮助我们变得更具竞争力。而一旦我们变得更具竞争力，我们就能打造更多产品，抢占市场份额，并进一步加速我们的增长，你知道的。我希望每年的增长率不是 70% 到 80%。我希望达到 100……你知道的，远超过 100%。这样我们就能……你知道的，这就是我的看法。所以这在当下的时代是一种竞争优势。谁能把这做到最好……你知道的，在某个时刻也许每个人都在使用它，它被彻底普及开来，每个人都在这么做。但眼下，这是巨大的超额收益（alpha）。如果你能把这做得非常非常出色，比其他任何组织都要好，呃……
<details><summary>Original English</summary>
>> We need to be consistent, whatever it is, right? Maybe they're right and the rest of the organization and including me are wrong, but then we need to at least it tells me that there's a there's a divergence and we can sort of, you know, so those kind of things were like nearly impossible to do. Like like many of this other stuff you could have done, but a question like that, like get the culture of this subgroup in a 12 you know, 12,000 person organization, you know, figure out how the Japan organization at Data Bricks I don't even speak Japanese, you know, and we have hundreds of people over there working. Like what's the culture like? How do we make decisions? How's it different from the EMEA or, you know, the Latin Latam Latam, you know, region that we have? So those are kind of game changers. For us, it's really I share all this information with the employees. They have access to all of this themselves and then I tell them like this is what we want. Like that L curve, we wanted to shift it to the right. So everybody, let's change that. Let's let's move towards this, you know, the North Star that we have together.

And that helps us just be more competitive. And then once we get more competitive, we can build more products and we take market share and we can accelerate our growth further, you know. I'd like to not be 70 80% growth every year. I'd like to be 100 you know, way over 100. So then we can put you know, that's that's how I see it. So this is a in this era right now, this is a competitive advantage. Whoever can do this best, you know, at some point maybe everyone is using it's fully diffused and everybody is doing this. But right now, this is big alpha. If you can do this really really well, better than any other organization, uh,
</details>

### 上市时机与流动性考量

>> 巨大的超额收益。很多人一直非常耐心地留在你们的股东名册（cap table）上，而我们现在在创始人和资本方之间有一场大辩论。更长时间地保持私有。如果我们有相当高效的二级市场，上市的意义何在？Stripe 保持私有状态……［笑声］我想已经快接近 20 年而不是 10 年了。而且他们似乎已经释放出还要继续保持私有的迹象。SpaceX 花了一点时间。Uber 也花了一点时间。我感受过那段过程，但幸运的是孙正义先生挥金如土。你们什么时候上市？何时上市，以及你如何做出这个决定？我知道你面临着很大的上市压力，但你同时在充满活力的二级市场上也拥有很多减压阀。
<details><summary>Original English</summary>
>> of big alpha. A lot of people have been very patiently been on your cap table and we have a big debate between founders and capital right now. Stay private longer. What's the point of going public if we have secondary markets that are quite efficient? Stripe has been private [laughter] closer to 20 years, I think, than 10. And they seem to have given the indication they're going to stay private longer. SpaceX took a little while. Uber took a little while. I felt that one, but luckily Masayoshi-san was splashy cashy. When are you going public? When And how do you make that decision? I know you got a lot of pressure on you to do it, but you also have a lot of pressure relief valves in the the vibrant secondary market.
</details>

>> 是的。听着，我的目标是在未来一二十年里让 DataRobot 尽可能地成功。我就是这么想的。实现这一目标的正确策略是什么？我提到了我们在这里所做事情的超额收益，以及我们正在打造的产品。顺便说一下，我们正在进入新的市场。我们进入了安全市场，我们进入了营销市场。呃，我正专注于这些。那么接下来的问题是，通往那里的路径，是对我们来说上市是最好、最快的方式，还是保持私有是最好的方式。而我其实认为答案……
<details><summary>Original English</summary>
>> Yeah. Look, my goal is to make DataRobot as successful as possible in the next decade or two. That's how I'm thinking about it. What's the right strategy to get there? I mentioned this alpha of what we're doing here, the products we're building. By the way, we're getting into new markets. We got into security market. We got into the marketing market. Uh I'm focused on those. Then the question is the path to get there is the best way and the fastest way for us to be public or to be private. And I actually think the answer
</details>

>> 对你而言，天平的每一端分别有什么筹码？
<details><summary>Original English</summary>
>> What's what's on each side of the ledger for you?
</details>

>> 是的，我其实认为，你知道的，你能获得资金渠道。你能获得好得多的营销效应。呃，你知道的，就好像人人都知道了你。就像每个季度你都有这样一个大型营销事件，你可以一遍又一遍、反反复复地讲述你的故事。这些都是巨大的优势。我们每年都必须组织自己的要约收购（tenders）。每年我们做……财务部门都必须经历这个庞大的流程。你知道的，我想我们筹集了200亿、300亿美元。然后我们必须安排那件事。这是一项繁重的工作。而公开市场本身就是一个能直接做这件事的市场。
<details><summary>Original English</summary>
>> Yeah, I actually think that, you know, you get access to capital. You get much much better marketing. Uh you know, it's like everybody knows about you. Like every quarter you have this big marketing event and you can tell your story again and again and again. Those are huge advantages. We have to organize our own tenders every year. Every year we do finance has to go through this big process. You know, I think we raised $20 $30 billion. And then we have to arrange that. It's a heavy lift. There is a marketplace that just does that.
</details>

>> 我想这很可能会让人相当情绪化且分心，对吧？比如人们不得不做出抉择。然后你可能会失去一些人，比如，嘿，他们套现拿走了1000万美元。现在他们就想，啊，也许我不想再来参加训练了。
<details><summary>Original English</summary>
>> probably a pretty emotional and distracting, I would think, right? Like people have to decide. Then you might lose people that, hey, they take $10 million off the table. Now they're like, ah maybe I don't want to come to practice anymore.
</details>

>> 我认为这种流动性……我……我认为流动性是一件好事，因为，你知道的，大家知道他们每年都会获得这种机会，它算是一种按部就班到来的、具有可预测性的安排，那就是他们拥有的一次机会。而且实际上在过去几年——自从我们几年前开始做这些以来——事实证明，你知道的，我们为要约收购预留的资金，他们从未全部用完过。所以大多数员工是看好的。是的，所以大多数员工都觉得，不，这是……
<details><summary>Original English</summary>
>> I think the liquidity I I think the liquidity is a good thing cuz, you know, people know that they're going to get it every year and it kind of comes and it's like predictable and that's like the one time they have. And actually in the past it's turned out since we started doing these a few years ago, it turns out that, you know, the money that we set aside for tenders, they never use up all of it. So most employees are bullish. Yeah, so most employees are like, no, this is
</details>

>> 那对你来说是好事。你能从中得到信号，对吧？谁在卖，谁没卖。这能提供一点信号。虽然也可能是个人原因。嗯，不过收购其他公司是拥有股权的一个极好理由，对吧？
<details><summary>Original English</summary>
>> that's good for you. You get signal from that, right? Who's selling, who's not. It's a little bit of signal. It could be personal reasons. Um but acquiring companies is a great reason to have equity, yeah?
</details>

>> 我们可以……我的意思是，我们在进行十亿美元级别的收购方面没有遇到过问题，你知道的，因为他们知道由于我们会提供流动性。然后我认为大多数人都会算一笔账，就像，好吧，如果这是……你知道的，这项业务规模是70亿美元以上，而且它正在以70%到80%的速度增长，他们就会算这笔账，比如，好吧，我本来可以……一开始大多数人都说我想要流动性，但随后当你告诉他们说，好吧，那你想卖多少呢？我们正在以……你知道的，你能否算一下按1.7的……你知道的，三次方或四次方复合增长？然后他们就开始挠头了，觉得，好吧，也许我就卖个5%这样，你知道的。
<details><summary>Original English</summary>
>> We can I mean, we haven't had a problem, you know, doing billion dollar acquisitions because they know because of the liquidity that we will provide. And then I think most people do the calculation is like, okay, if it's, you know, the business is $7 billion plus and it's growing 70-80% they do the math like, okay, I could once most people say I want liquidity, but then when you tell them like, okay, well, how much do you want to sell? We're growing you know, can you do compounded growth of, you know, 1.7 to the power, you know, to the power of three or four? And then they start scratching their heads like, okay, maybe I'll sell like 5% you know.
</details>

### 研发资源分配与外围竞争格局

>> 是的，对于持有这种股票的投资者和员工来说，按兵不动（sitting on your hands）是一项非常需要学习的重要技能。我的意思是，听着，当你进入那个领域时，你确实必须防范下行风险。你现在把谁视为竞争对手？大家都说是像 Snowflake 这样的公司，但我正在观察这样一个市场：正如我之前所说，Anthropic 正在接二连三地推出功能；Cloudflare 正在盯着与其相邻的功能；Replit 也在盯着与其相邻的功能。每个人似乎都在运用他们的周边视野进行观察，而且因为你能快速构建软件，因为你拥有大量的开发者，如果这些开发者继续沿着你展示的那条坡道往上走——你当时只有 10% 的人处于顶峰——这意味着随着那 90% 的人攀登上去，你的开发者资源将飙升至爆表。因此你面临着一个抉择。

我们是只要较少处于长尾低端的开发者并变得更具盈利能力，还是在他们沿着坡道向上移动时把所有那些开发者时间都投资进去？那么，你是如何看待这两个问题的？面对这种效率正在创造出来的庞大资源，你该怎么处理？另外，谁是竞争对手，以及你是否只需要不断进行外围产品的拓展？
<details><summary>Original English</summary>
>> Yeah, sitting on your hands is a very important skill to learn as an investor and an employee with this this kind of sock. I mean, listen, you do have to protect downside when you when you get in that space. Who do you see as your competition right now? Everybody says something like Snowflake, but I'm watching a market where, as I said earlier, Anthropic is launching feature after feature. Cloudflare is looking at features next to them. Replit is looking features next to them. Everybody seems to be looking in their peripheral vision and because you can build software fast and because you have a lot of developers, if those developers keep going up that ramp that you showed, you only had 10% of people at that peak, which means as that 90% climb up there, your developer resources are going to go through the roof. So you have a decision to make.

Do we just have less developers at the low end of the tail and have be more profitable or do we invest all that developer time as they move up the ramp? So so how do you think about both of those issues? What do you do with massive resources that this efficiency is creating and then who is the competitor and do you need to just keep making peripheral product moves?
</details>

>> 是的，我们会进行外围产品的拓展，但也许我应该先说明，好吧，刚才那些是上市的好处。而弊端在于……你知道的，这也就是为什么……你知道的，为了回答你的具体问题，比如，你知道的，我们为什么……为什么要竞争？我们与谁竞争？我们为什么要打造这款产品？我不希望市场迫使我陷入……好吧，现在市场低迷了，现在它……你知道的，
<details><summary>Original English</summary>
>> Yeah, we will make peripheral product moves, but maybe I should just start by saying, okay, so those are the upsides of going public. The downsides are, you know, is is the reason why, you know, to answer your specific question, like, you know, why why do we compete? Who do we compete with? Why do we build this product? I don't want the market to force me that, okay, now it's down and now it's, you know,
</details>

<!-- chunk 7/9 -->

本周的市场情绪非常糟糕，现在你们的股价下跌了。而当股价下跌时，员工实际上就等于被降薪了。

他们会说：“嗯，你明明承诺过我能赚一百万美元。实际上，你之前还说再过几年就会变成两百万美元，但我现在看着它，呃，其实只有二十万美元。所以你骗了我，我要辞职了，好吗？”

呃，然后呢，三个月后，情况又变成了：“噢，不不不，实际上营收正在加速增长。我们之前完全看错了。现在图表一路向右上扬了。”大家又会觉得：“噢，好吧，哇，太棒了。”所以就会有这种反复震荡。

呃，那种……
<details><summary>Original English</summary>
sentiment is terrible this week and now

your stock is down and when the stock is

down, the employees literally are

getting a pay cut.

And I say, well, you know, you promised

me I was going to make a million

dollars. Actually, you said this is

going to be two million in a couple of

years, but I'm looking at it right now.

Uh and it's actually two 200k. So you

lied to me. I'm leaving, okay?

Uh and then, you know, three months

later it's like, oh, no, no, no,

actually the revenue is accelerating. We

were totally wrong. It's up to the right

now. It's like, oh, okay, wow, it's

great. So there's like back and forth.

Uh

that's
</details>

>> 坐过山车可能会让人压力很大。
<details><summary>Original English</summary>
>> of a roller coaster can be stressful.
</details>

>> ……正是我想要避免的，这样我们才能专注于长期目标，比如朝着我们长远拥有的愿景去建设公司，而不受干扰。我们会上市的。我们将来一定会上市，但目前，我认为在人工智能的这个转型期，起伏波动实在太大了。我认为这会分散公司的精力，分散CEO的精力，让CEO们士气低落。他们会给我打电话，显得很沮丧，因为股价下跌了，他们甚至不明白为什么，然后股价又涨了。呃，所以这就是我们试图避免的。
<details><summary>Original English</summary>
>> what I want to avoid so that we can

focus on that long term, you know,

building the company towards the vision

that we have in the long run without

being distracted. We will go public. We

are going to be public, but right now, I

think during this transition period of

AI, there's just too much up and down

and I think it's distracting to

companies, it's distracting to CEOs,

it's demoralizing to CEOs, you know,

they call me, you know, they're like

depressed because, you know, stock is

down, they don't even understand why and

then the stock is up. Uh so that's what

we're trying to avoid.
</details>

>> 我觉得这是人们对其睡眠分数开始产生的问题，比如你买了个 Whoop。我很喜欢它，但我给我妻子也买了个 Whoop，然后我们就会互相比较睡眠分数。现在这种感觉有点像每天盯着你的 Uber 股票看一样。你会陷入某种互相较劲的关系中，这可能会挺有挑战性的。Ben 在其他方面，这……这很有意思。

嘿，我们刚才还没转回 Ben Horowitz 说的话题呢。他说你对超级智能的构想是模型、算力以及训练并达到精确所需时间的某种组合。你能给我们详细讲讲吗？你脑子里有现成的思路可以讲讲吗？
<details><summary>Original English</summary>
>> I think it's an issue people are

starting to have with their sleep

scores, you know, you get a whoop.

And I love it, but I got my wife a whoop

and then we're like comparing sleep

scores and now that it's kind of like

looking at your Uber stock every day.

You get a little bit of volleying

relationship, it could be challenging.

Ben in other ways it's it's interesting.

Hey, we didn't

circle around to what Ben Horowitz said.

He said that

your formulation of super intelligence

is some combination of the model, the

power, and the time it takes to train

and be accurate. What can you walk us

through it? Do you have it off the top

of your head there ready to go?
</details>

### 超级智能与递归自我改进的条件

>> 我非常乐意讲讲。我是说，这其实很简单。所以我觉得主要的问题是上下文问题。我们正在用 genie 和本体论（ontology）来解决这个问题。那些实验室则专注于超级智能。这就是 Bostrom 谈论的内容。Bostrom 在他的书里也提到，我们该如何达到那个目标？他实际上在2014年（我认为是那年）定义了 RSI，呃，即递归自我改进（recursive self-improvement）。这意味着人工智能开始自我改进，然后变得越来越好、越来越好、越来越好，接着我们就会迎来这种腾飞，也许是一次快速腾飞。到了那个阶段，我们就会达到奇点，失去掌控权。到了那个时候，但愿人工智能是充分对齐的，因为如果不对齐，我们所有人都会沦为宠物。这就是那10%风险的来源。对，回形针最大化器，以及对人类造成10%的风险等等，所有这些都源于那里。

但我认为，这很大程度上其实来自于大多数正在构建这种AI的人。他们看到AI在编程方面变得非常厉害。而且几乎在每家公司里，正如我之前所说，编程工作正由编程智能体来完成。

因此，他们看到这个现象——我认为这实际上在硅谷引发了一场巨大的存在主义危机。对于我们大多数从小到大一辈子都在写代码的人来说，你知道，这……这是件大事。比如，你知道，这就像……就像我从小学三年级一直到三十多岁，每天花10到12个小时，一周7天，一直在写代码，对吧？我当时非常擅长这个，我懂所有这些语言等等。然后突然之间，AI开始做这件事了。
<details><summary>Original English</summary>
>> I happy happy to do it. I mean, it's

pretty simple. So I I think the main

problem is the context problem. We're

solving that with genie and the

ontology. The labs are focused on super

intelligence. That's what Bostrom talked

about. Bostrom in his book also said,

how do we get there? He actually in

2014, I believe, defined RSI,

uh recursive self-improvement,

which means that the AI starts improving

itself and then it gets, you know,

better and better and better and better

and better and then we get this takeoff,

maybe a fast takeoff. And at that point,

you know, we reach the singularity and

we're no longer in control. And at that

point, let's hope that the AIs are well

aligned because if they're not, we're

all going to be made into pets. And this

is where the 10% risk. Yeah, paper clip

maximizers and the 10% risk to humanity

and all of that comes from there.

But I think a lot of this is actually

coming from

most of the folks that are building this

AI.

They've seen that the AI has become

really good at coding.

And

almost in every company, as I said

earlier, the coding is being done by

coding agents.

So then they're seeing and I think this

is actually causing a big existential

crisis in Silicon Valley. And it's

actually for most of us who started, you

know, who grew up coding our whole

lives,

you know, it's it's it's a big deal.

Like, you know, it's like

like I spent, you know, 10 12 hours, 7

days a week, you know, from third grade

until, you know, my 30s just coding all

the time, right? And I was really good

at it and I knew all these languages and

so on. And then suddenly it's like the

AI is doing that.
</details>

>> 而且 AI 到底比你强多少？那是另一部分。这就像……
<details><summary>Original English</summary>
>> Well, and the AI is how much better than

you? That's the other part. It's like
</details>

>> 是的。所以现在它在自己写自己，下一个版本也是它自己写出来的。等等。这难道不就是递归自我改进吗？但等等看。接着这个过程就会加速，然后我们就会陷入这个循环。那些书——那本书称之为《超级智能》和回形针最大化器。所以它可能会失控，所有这些坏事都会发生。其实，挺有意思的。Bostrom 现在某种程度上改变了他的看法。如果你现在真正关注他的话，他其实已经不再持那种观点了。他现在说我们应该推进这项技术。风险确实存在，当然网络安全方面有风险。但是，我觉得大家实际上需要把这个问题想得更深入一些。

仅仅因为 98% 的代码是由 AI 编写的，并不意味着我们就拥有了 RSI。如果它把剩下的 2% 也自动化了，谁在乎呢？是 98% 还是 100%，有区别吗？为什么这会有影响？其实根本无关紧要。

所以我们真正需要满足四个条件。这四个条件是：第一，我们需要训练出的下一个模型在大幅缩短的时间内完成训练，明白吗？而各大实验室进行的那些大规模预训练运行，他们实际上每年并不会做那么多次，对吧？而且它仍然遵循所谓的缩放定律（scaling laws），这意味着你需要指数级增加的硬件才能获得那种提升。所以需要指数级增加的算力——增加 10 倍的算力才能获得一点点线性提升，懂吗？所以他们正争相获取并拼凑出他们所能组建的最大数据中心，搞好网络连接，完成所有的工程工作。然后，他们让全人类来做这一切，因为他们真的不想搞砸下一次运行。如果下一次运行搞砸了，那么整个事情就垮了。

但是，我们希望下一次训练运行能够更快。这是第一个条件。好吗？而且实际上，它不能仅仅是快一点点。它就像……不能是你每次只把距离缩短一半，那样你永远也到不了终点。所以，在某种意义上它必须是超线性的。

其次，我们还希望它消耗更少的资源，对吧？因为你可以说：“好吧，它变得越来越快了，但那是因为我们一直在把硬件规模增加 10 倍。”嗯，你不能一直玩这种把戏，因为我们的硬件会耗尽，我们的原子也会耗尽。所以这是第二个要求。

第三个要求是，准确率也在至少呈线性提高，或者说我们正在以一种泛化的方式全面获得更好的准确率。不能只是在我们进行强化学习的某一个维度上，或者仅仅在数学方面变得更好。它需要在它所有的任务上全面提升。明白吗？

即使你把这三点都做到了，那也还不够。假设你把这个过程重复了五次、六次、七次，那很棒，你会得到非常出色的模型。但那还不是那种超级智能。

第四个条件是，你实际上能把这个放进一个循环中，并且前面那三个条件需要持续不断地发生，这样我们最终进入这样一个世界：下一个模型只需要三个月，然后一个月，接着是两周、一周，而且它变得越来越聪明、越来越聪明，同时成本，原本要花我们 100 块——或者可能要花我们 1 亿美元，然后变成 5000 万、2500 万、1000 万、500 万、200 万、100 万，然后一路往下走。这就是我们……这就是我们设想的那种情景。如果你实际审视它的话：

那就是飞轮。目前这个飞轮并不存在。模型的训练时间正变得更长，对吧？而且有更多的数据清洗工作，有更多的手动打地鼠现象发生，比如像 Mercor 这样的供应商必须实际去向高技能劳工获取数据，然后你必须在这些 gym 里进行强化学习，你必须在每个领域里类似打地鼠一样解决问题。所以它是非常特定于领域的。当然，预训练需要更多的资源，而且诸如此类，所以看起来我们并没有进入这个循环。

顺便说一句，即使你满足了所有这四个条件，我说的是，这也并不保证意味着你就会拥有一个有自我意识的存在，去接管一切，然后……
<details><summary>Original English</summary>
>> Yeah. So now it's writing itself and the

next version it wrote itself. Wait a

minute. Isn't that the recursive

self-improvement? But wait a minute.

Then this is going to speed up and then

we're going to get into this loop. The

books the book called it

Superintelligence and the Paper Clip

Maximizer. So it might go off and all

these bad things happen. Actually,

interesting. Bostrom has kind of changed

his view now. If you actually follow him

now, he's actually not anymore. He's

saying that, you know, we should do

this. There are risks. Of course, there

are risks with cyber. But, you know, I

actually think, you know, you need to

actually think this through

further. Just because 98% of the code is

being written by AI, we don't have RSI.

If it automates the last 2%, who cares?

You know, does it matter if it's 98

98% or 100%? Why does it matter? Actually

doesn't matter. So we really need four

conditions to be true. The four

conditions is that we need the next

model that's trained to, you know, be

trained in much shorter amount of time,

okay? And still the big pre-training

runs that the labs do, they don't do

actually that many of them per year,

okay? And it's still following the

what's called the scaling laws, which

means you need exponentially more

hardware to get that improvement. So

exponential more 10x more compute to get

a little linear improvement, okay? So

they're scrambling to get all the and

put together the biggest data center

that they can possibly put together with

the networking and do all the

engineering. And then, they're having

humans do all of this because they

really don't want to screw up the next

run. If the next run gets screwed up,

then, you know, the whole thing falls

apart.

But, you know, we would like that next

training run to be faster. That's

condition number one. Okay? And

actually, it can't just be a little bit

faster. It's like this, you know, it

can't be like, you know, you're halving

the distance every time. You'll never

get there. So, in some sense it has to

be super linear. Secondly, we also want

it to use less resources, right? Cuz you

know, you could say, okay, it's getting

faster and faster, but that's because

we're 10 xing the hardware all the time.

Well, you can't do that trick because we

run out of hardware and we run out of

atoms. So that's like the second

requirement. Third requirement is that

the accuracy is also improving at least

linearly or, you know, we're getting

better accuracy across the board in a

generalized manner. It can't just be

it's getting just better at, you know,

this one dimension that we did

reinforcement learning on or just math.

It needs to be across the board on all

of its tasks. Okay?

Even if you do all of those three, it's

not enough. Let's say you do that five,

six, seven times, that's awesome. You

get really awesome models. That's not

that kind of super intelligence. The

fourth condition is that you can

actually put this in a loop and all the

previous three conditions need to be

continuously happening so that we end up

in a world where the next model takes,

you know, three months, then one month,

then, you know, two weeks, one week, and

it's getting smarter and smarter and

smarter and it's, you know, costing us

100 buck or maybe costs us 100 million,

then 50 million, 25 million, 10 million,

five, two, one, and then it goes down

and down. That's what we That's the kind

of scenario we have. If you actually

look at it,

that's the flywheel. That flywheel

doesn't exist right now. The models are

taking longer to train, right? And

there's more data cleaning and there's

all more manual whack-a-mooling

happening where, you know, you have

vendors like Mercor that has to actually

go get the data from very skilled labor

and then you have to do reinforcement

learning in these gyms and you have to

kind of whack-a-mole in each domain. So

it's very domain specific. And then of

course the pre-training requires more

resources and, you know, so um it's it's

that doesn't look like we're getting

into this loop. By the way, even if you

satisfy all the four conditions I'm

saying that doesn't guaranteed mean that

you'll have, you know, a conscious being

that's just, you know, taking over

everything and just, you know,
</details>

>> 那只是那种情况发生的前提条件，而且根本无法保证它真的会发生。
<details><summary>Original English</summary>
>> it's the precondition for that happening

and it there's no guarantee that it

actually happens.
</details>

>> ……一个前提条件，但就算你拥有了那个——而我们现在还没有——要想在此时此刻威胁到我，你得让一个杀手机器人现在走进这个房间，把我按倒在地，好吗？或者诸如此类的手段，对吧？而那些东西现在还不存在。所以，呃，你知道……
<details><summary>Original English</summary>
>> a precondition, but even if you had

that, which we don't have, you would

have to to threaten me right now, you

would have to have a killer robot come

into this room right now and wrestle me

down, okay? Or something, right? And

those don't exist yet. So, uh you know,
</details>

>> 对。眼下，你可以有一群黑客拿下一个能力非常强大的模型，然后你能找到……
<details><summary>Original English</summary>
>> Yeah. Right now, you can have a bunch of

hackers take a really capable model and

you can find
</details>

<!-- chunk 8/9 -->

……发现法国杂货店里的冰箱密码是 admin admin，你远程用脚本小子手段黑进去，把它调成化霜模式，导致一堆黄油和牛奶变质——这对法国人来说确实是场悲剧，我理解，[笑声] 但我可以向你保证，这根本不是超级智能。这意味着……

我是说，你看到那起黑客攻击以及人们对此有多抓狂了吗？我就觉得，伙计们，你们知道现在买一台新路由器时，上面都会印着序列号以及一个随机密码吧？
<details><summary>Original English</summary>
out that the refrigerators in grocery stores in France have the password admin admin and that you can remotely script kitty into them and turn it into defrost mode and make a bunch of butter go bad and milk, which is a tragedy for the French. I understand, [laughter] but it is not super intelligence, I can assure you. It means

I mean, did you see that hack and how people were losing their minds over it? I'm like guys, you know how when you buy a new router now, it has the serial number and then a random password?
</details>

>> 对，admin admin，没错。
<details><summary>Original English</summary>
>> Yeah, admin admin, yeah.
</details>

>> 对，要是他们当时在那些冰箱上也这么做，他们根本不可能黑进任何一台——除非他们闯入现场，给20台不同的冰箱拍下截图，在物理层面上攻破第八区的某家超市。那样的话，超市也就损失个，我不知道，10磅黄油吧，根本算不上什么大事。
<details><summary>Original English</summary>
>> Yeah, if they had done that on the refrigerators, they would have been able they wouldn't have been able to hack one of them unless they got into the place, took screenshots of 20 different refrigerators, physically compromised you know, some supermarket in the 8th arrondissement, which would have lost, you know, I don't know, 10 lb of butter. It wouldn't have been a big deal.
</details>

>> 所以，听着，网络安全我认为确实是个现实问题，而且我认为它是个切实的风险。实际上，我们在网络安全领域有一款名为 Likewatch 的完整产品，就是基于所有这些数据构建的，它拥有自动化智能体，能够实际检测到正在发生的这类入侵，并且它们会监控你现有的智能体。

这是个现实的问题，我确实认为这里会发生糟糕的事情，但随后我们会做出调整。但互联网刚问世时，同样也发生过糟糕的事情。
<details><summary>Original English</summary>
>> So, look, cyber I do think is a real thing and I think it's a real risk. We actually have a whole product in the cyberspace called Likewatch built on all this data that has automated agents that actually detect these kind of intrusions that are happening and they monitor your agents that you have.

This is a real problem and I do think bad things will happen here, but then we will adjust. But bad things happened when internet came out as well.
</details>

### 网络攻防的不对称性与代码安全

>> 难道我们不应该能够解决这个问题吗？因为你来评评我说的对不对。我听到过一种理论，它在某种特定类型的黑客攻击上让我产生了共鸣——不是针对那种，你知道，脚本小子的攻击，而是真正的黑客攻击——那就是你拥有大量的算力。执行某些黑客攻击需要大量的算力，比如 Hugging Face 那个事件，你知道，一千个智能体之类的。

坏人并没有那么多算力。好人拥有的算力要庞大得多。所以，如果你作为白帽黑客尽到本职工作，并且做好了正当的防御、去寻找这些漏洞利用点，假设你拥有上千倍的资源，你就应该能够在黑客之前很久解决这些问题。

你觉得这种说法有道理吗？难道他们只是……
<details><summary>Original English</summary>
>> Shouldn't it

Shouldn't we be able to solve for this because you tell me if I'm right or wrong here. One theory I heard, which resonated with me for a certain type of hacking, not for the you know, script kitty hacking, but real hacking uh is you you have a lot of compute, you need a lot of compute to execute certain hacks, like the hugging face one, you know, thousand agents, whatever.

The bad guys don't have that much compute. The good guys have a massive amount of more compute. And so, if you just did your basic job as a white hat and you know, defended properly and looked for these exploits, let's say you have a thousand times the resources, you should be able to get to these problems long before the hackers.

Does that make good sense to you that they're just
</details>

>> 是的。

是的。确实，但问题在于，你必须把这一点与我们面临的以下不对称情景进行权衡：如果我是一名攻击者，你知道，我可以发动成千上万、成千上万的智能体，它们全部失败都没关系，只要有一个成功就行。如果其中有一个渗透进去了，我就彻底成功了。而不对称性在于，如果我是一名防御者，你知道，我一直以来都能够守住自己的防线，唯独有一次被渗透进去了。
<details><summary>Original English</summary>
>> Yeah.

Yeah. It's it's but there's a the the issue is that you have to weigh that against the following asymmetric scenario that we have, which is if I'm an attacker, you know, I can launch thousands of thousands of thousands of agents and I all of them can fail except for one. And if one of them gets through, I'm completely successful. The asymmetry is that if I'm a defender, you know, I was able to like, you know, you know, protect, you know, my my boundaries all the time except one got through.
</details>

>> 这就像自杀式炸弹袭击者——话虽有点过于露骨，但你只需要搞成一次“9·11”就能达到目的。而你可以尝试一千次都没得逞。
<details><summary>Original English</summary>
>> This is a suicide bomber not to be too graphic, but you only need to get one 9/11 to make your point. And you could try a thousand times and not get through.
</details>

>> 必须时刻保持 100% 的安全。他们只需要让一样东西渗透进来就行。所以，这种风险是非常不对称的。然而，以我的视角来看，之所以我认为我们实际上会克服这个问题、并且最终会完全没问题，原因在于这些实际上是存在于源代码中的潜在漏洞。顺便说一句，我们现在并没有制造更多这样的漏洞，因为几乎我们所有人现在都在对它进行扫描。我们都有相应的产品。我是说，我们实际上就销售一款产品，我们可以扫描新代码的脆弱性。所以，正在产出的新代码是不会带有这些安全漏洞的。顺便说一句，这听起来可能有点傻，但可以这样想：在接下来的12个月里，我们要写的代码将比人类历史上任何时期都要多，对吧？实际上用不了未来12个月。所以，所有这些代码都将会是安全的。那么接下来……而且顺便提一句，
<details><summary>Original English</summary>
>> need to be 100% safe all the time. They need to just get one thing through. So, it's like very asymmetric that risk. But however, the the way I would look at it, the reason, you know, I think that we're actually going to overcome this and it's going to be totally fine, is that these are actually latent bugs that exist in the source code. By the way, we're not creating more of them now cuz almost all of us are now scanning it. We all have products. I mean, we actually sell a product. We can scan the vulnerabilities of new code. So, new code that's being produced is not going to have these vulnerabilities. By the way, that might sound silly, but think about it this way. In the next 12 months, we're going to write more code than ever in the history of mankind, right? Actually, in less than next 12 months. Uh so, all that code is going to be secure. So then and by the way,
</details>

>> 现在 AI 已经足够先进，能够不犯人类的错误，能够去寻找这些漏洞，而且它更加坚持不懈。
<details><summary>Original English</summary>
>> right now the AI is sophisticated enough to not make human errors and to look for it and it's more dogged.
</details>

>> 是的。直接去扫描那些东西就行。那么剩下的就全是遗留代码了，顺便说一下，我们完全可以把它们全部重写一遍，这也是我们必须经历的过程。而且……我们正在通过其他方式来做这件事。
<details><summary>Original English</summary>
>> Yeah. You just scan scan those things. So then what remains is all the legacy code, which by the way, we can rewrite all of it, which is what we have to go through. And uh we're doing that in other ways.
</details>

>> 80/90，是的。
<details><summary>Original English</summary>
>> 80/90, yeah.
</details>

>> 是的。其实还有其他方法来进行保护，比如在甚至都不用触碰现有遗留代码的情况下进行影子补丁（shadow patching）。但是……所以，你可以这样理解当前的情况：这就像一个果园，攻击者所利用的那些漏洞就像是果子，他们在摘那些容易摘的水果（low-hanging fruits）。以前人类能摘到一定高度的低垂果实，现在智能体能伸手够到更高的地方，去摘挂得更高的果实。但我们会把那些果子清理干净，之后他们也许能伸手够得稍微更高一点，但代码中的漏洞数量是有限的。一旦我们把那个代码库防护好，就再也没有漏洞了。所以这并不是一个无限的事情、会永远持续下去。不，到那时它就停止了。随后我们就会处于一个稳态，到时候，安全漏洞实际上可能会比我们过去面临的还要少。
<details><summary>Original English</summary>
>> Yeah. There's other ways to actually also protect, you know, do shadow patching before even actually without touching the existing legacy code. But um so, you know, what's happening is that you can think of it as like, you know, it's like a fruit garden and they're like these bugs that, you know, attackers are leveraging, they're picking the low-hanging fruits. And before humans could pick a certain low-hanging fruit, now agents can reach higher and pick higher, you know, hanging fruit. But we're going to clean clean those up and then they can maybe reach a little bit higher, but there's only a finite number of vulnerabilities in the code. Once we've secured that code base, there is no more. So it's not like there's an infinite thing and this is going to go on forever. No, it then stops. Then we're at a steady state and then, you know, vulnerabilities might actually be fewer than what we had in the past.
</details>

### 有效利他主义（EA）阵营与超级智能风险

>> 最终还是，你知道，回到你在伯克利时期参与的 AMP，处于环节中的人才是脆弱点所在，无非就是某个人被攻破了，正如我们在过去一周左右看到的那样。

人类确实存在脆弱性。我就点到为止。

嘿，我想以这样一件事收尾。你在伯克利待了很长时间，那种嬉皮士风格的、EA（有效利他主义）社区、加速主义者、减速主义者。

EA 派系的这群人本质是什么？他们是如何看待世界的？他们为何让美国社会的其他人如此困惑？

这些人到底是谁？他们相信什么？他们是有点因自身的成功而冲昏了头脑，还是确实拥有非常重要的真知灼见，以至于我们必须认真重视他们的言论并相信他们的话？这是一个很大的争议。你知道，Dario 在路演期间曾说，我相信癌症和阿尔茨海默病将在不到10年内绝迹。这话听起来确实很美好，但除非你……
<details><summary>Original English</summary>
>> that eventually then, you know, back to amp when you went at Berkeley, it's the people in the loop that are the vulnerability and it's just going to be somebody getting compromised as we saw the last week or so.

The humans do have vulnerabilities. I'll leave it at that.

Hey, I want to end on this one thing. You you spent a lot of time in Berkeley, hippie-dippy, EA community, acceleris, de celeris.

What's the nature of this group of the EA faction and how they look at the world and how confounding they are to the rest of American society?

Who are these people? What do they believe? Are they a little drunk on their own success or do they actually have really important insights and we need to really focus on what they're saying and take them at their word? It's a big controversy. Dario, you know, during the road show is saying cancer and Alzheimer's, I believe will be gone in under 10 years. Now, that's very beautiful to say except if you're
</details>

>> 已经去世了，对吧？
<details><summary>Original English</summary>
>> dead, right?
</details>

>> 是的，除非你，比如，父亲或母亲正因癌症垂危，而你心想：噢，我还有一线生机能救他们；或者你祖母得了阿尔茨海默病。这样一来，你谈论的实际上是在给人们虚假的希望，也许你不该做出这样的断言。但我并不怀疑 Dario 本人深信不疑。我其实认为他确实相信。但请帮我们剖析一下这些人，因为你和他们打了二三十年的交道。
<details><summary>Original English</summary>
>> Yeah, except if you're, you know, mom or dad are dying from cancer and you think, oh, I got a window here that I could save them or my grandmother's got Alzheimer's. Now you're talking about giving people false hope and you maybe shouldn't make claims like that. But I don't doubt Dario believes it. I actually think he does. But unpack these people because you've been around them for two decades, three decades.
</details>

>> 这个嘛，你知道，我认为其实双方的大多数人——应该说是各方阵营的人——在他们自己的故事里都是英雄，对吧？我们所有人醒来时都觉得自己是好人，自己做的是正确的事。所以我认为这是有出发点的。我认为他们确实是对这种超级智能接管世界感到非常担忧。如果你读过博斯特罗姆（Bostrom）的书，实际上如果你读过那些书，并在这一切发生之前将他在书里写的内容内化吸收，你其实会感到挺害怕的，对吧？而当我读到它时，我也确实感到吓坏了。

所以我认为他们是从那些假设出发的，然后他们看到，好吧，如果它变聪明的速度这么快，再看看正在发生的一系列网络攻击，以此类推……我们就会迎来书中描绘的那种超级智能。

但那里面有几处“以此类推”其实是不明确的。不过他们随后会说，好吧你看，我们难道不应该保持谨慎吗，对吧？

所以我认为我们需要，你知道，我们应该关注安全。我认为网络安全是一个我们应该关注的大问题。但现实是，我认为我们知道该如何应对。我们将能够妥善处理好这件事情。我认为目前最大的风险是网络安全，而且我认为它是可控的。

至于这个 RSI（递归自我改进），我没有看到任何证据。如果别人掌握了我没有掌握的数据，好吧，我确实不知道我所不知道的事情。但根据我和旧金山这里所有实验室以及我接触的所有人的交流来看，我甚至都没看到我提到的那四条标准得到满足。所以我没看到有什么风险需要去为此担心它会发生。然后我说的第二点是，即便我们真的达到了那个阶段，我也没看到在社会中具备相应的手段，就比如这仅仅是数字层面的东西，我们完全可以现在就直接把电脑关掉。你知道，我确实认为网络安全是……
<details><summary>Original English</summary>
>> Well, you know, I think that most people on both sides actually, on all sides, they're the heroes in their own book, right? We all wake up thinking I'm the good guy and I 'm doing the right thing. So I think it comes from a place. I think they are seriously nervous about this kind of super intelligence taking over. If you read Bostrom's books, actually if you read those books and you sort of internalize what he wrote before any of this, then you actually get kind of freaked out, right? And then I was certainly freaked out when I read it.

So I think that they're starting with those assumptions and then they're looking at, you know, okay, well then if it's getting smarter this fast and look at the cyber attacks that are happening, dot dot dot we're going to get this kind of super intelligence that's described in the book.

But there's a few dot dot dots there that are not clear. But then they would say, well look, you know, shouldn't we be cautious, right?

So I think we need to take, you know, we we should look at safety. Cyber I think is a big deal that we should look at. But the reality is that I think we know how to handle this. We will be able to manage through this. I think it will be the biggest risk right now is cyber and I think it's manageable.

This RSI, I don't see any evidence of it. If there's data that, you know, others have that I don't have, yeah, I don't I don't know what I don't know. But based on what I'm talking to, you know, here in San Francisco where all the labs are and all the people I meet, I don't see those four criteria that I mentioned even being fulfilled, you know. So I I don't see any risk to be like worried about it, you know, that happening. And then the second thing I said, even if we would get there, I don't see, you know, even the means in the society, like it's this is just digital. Like we can just shut down the computers right now. You know, I do think cyber is
</details>

<!-- chunk 9/9 -->

是真的。比如如果一家医院瘫痪了，设置了一个冰箱，对吧？那确实令人担忧。还有他们……

<details><summary>Original English</summary>
real.

 Like

 if

 a

 hospital





went

 down

 and

 set

 up

 a

 refrigerator,





right?

 That

 is

 concerning

 and

 they
</details>

>> 比如孩子们使用它，与 Character AI 建立起拟人化的准社交关系，或者在你产生自杀念头之类的时候，它给你提供错误的信息。比如，对于技术具体如何被部署，确实是存在担忧的。我们刚刚经历过类似的情况——你之前提到了邓巴数。我们经历过社交网络及其对社会产生的深远影响。我们现在正在经历关于真相与新闻，以及通过算法操纵新闻的问题。所以确实有一些事情是值得担忧的；至于说人类被变成回形针，可能还不至于。

<details><summary>Original English</summary>
>> using





kids

 using

 it

 and

 developing

 parasocial





relationships

 with

 character

 AI

 or

 it





giving

 you

 bad

 information

 if

 you're





suicidal

 or

 something.

 Like

 there

 there





are

 concerns

 to

 have

 about

 how

 the





technology

 gets

 deployed.

 And

 we

 just





went

 through

 this

 with





you

 mentioned

 Dunbars

 number

 four.

 We





went

 through

 this

 with

 you

 know,

 social





and

 and

 the

 profound

 impact

 that

 had

 on





society.

 We're

 going

 through

 it

 now

 with





truth

 and

 news

 and

 and

 manipulation

 of





news

 via

 algorithms.

 So

 there

 are

 things





to

 be

 concerned

 about

 being

 turned

 into





paper

 clips,

 maybe

 not.
</details>

>> 但我认为……

<details><summary>Original English</summary>
>> But

 but

 I

 think

 that,
</details>

>> 你知道，医疗健康方面的应用绝对是真实的。比如，在 Databricks，我们实际上参与了再生元（Regeneron）的工作，那里的研究人员利用 Databricks 找到了导致慢性肝病的实际基因组，并且利用它研制出了针对该疾病的药物。

<details><summary>Original English</summary>
>> know,

 the healthcare

 stuff

 is

 absolutely





real.

 Like,

 you know,

 at

 Databricks

 we





actually

 uh

 we

 were

 involved

 with





Regeneron

 where

 they

 found

 the

 the





actual

 genome

 responsible

 for

 chronic





liver

 disease

 using

 Databricks.

 Their





researchers

 there

 and

 actually

 came

 up





with

 drugs

 for

 that

 using

 the
</details>

>> 不到十年内，如果按照达里奥（Dario）提出的说法，我们真的有可能在未来十年内治愈癌症吗？那可是一个相当大胆的言论。

<details><summary>Original English</summary>
>> in

 under

 a decade

 if

 you were

 to

 take





the

 claim

 we

 had

 Dario

 make





any

 chance

 that

 like

 we

 cure

 cancer

 in





the

 next

 10

 years?

 That's

 a

 pretty

 bold





statement.
</details>

### 医疗突破与药物研发

>> 这对我来说很难讲。我不知道究竟需要什么。我的意思是，我认为进展会更快，但对于其中的很多事情来说，它还必须经过人体临床试验。人体试验嘛，你知道，我们不能胡乱在人身上做试验，对吧？而且仅仅在动物身上做过试验也是不够的，对吧？

所以我也说不准。也许需要十年，也许十年不行，也许需要 30 年，也许需要 50 年。我不知道。也许只需要 6 个月。也许在很大程度上已经解决了。但它确实已经在提供帮助了。我刚才给你举的慢性肝病的案例，就极其重要。顺便说一句，那是在 Databricks 使用的上一代 AI。我们现在与默克（Merck）一起训练了一个新模型，叫做 Teddy，即“Transformer 赋能的药物研发”（Transformer Enabled Drug Discovery）。

“Transformer 赋能的药物研发”是一个模型，Transformer 模型，但它的下一个 token 不再是英文单词，而是基因调控网络（Gene Regulatory Network，GRN）。因此它实际上能够判定：好，这个基因组实际上导致了这种疾病，而另一个基因组只是对它做出反应，因此不要将其选作药物的靶点。所以这将加速药物研发。你知道，这是一个变革性的东西。

抛开药物研发不谈，我再给你举一个例子，比如危机短信热线（Crisis Text Line）。它使用 Databricks，使用大语言模型和这些智能体，它们实际上能够检测出青少年是否有自残倾向，并帮助加以预防，对吧？Virtue Foundation 也在使用 Databricks。还有 Zipline——这是一个之前报道过的案例——使用 Databricks 来运送食物。他们有这些无人机，对吧？那些负责配送的无人机，关于这些无人机的一切等等，比如它们的路线……

<details><summary>Original English</summary>
>> It's

 very

 hard

 for

 me

 to say.

 I

 I

 don't





know

 exactly

 what's

 needed.

 I

 mean,

 I





think

 progress

 will

 be

 faster,

 but

 for

 a





lot

 of

 these

 things





uh

 it

 also

 has

 to

 go

 through

 um

 you





know,

 human

 trials.

 Well,

 the

 human





trials

 like,

 you

 know, we

 can't

 just





test

 stuff

 on

 humans

 willy-nilly,

 right?





And

 just

 because

 you

 tested

 it

 on





animals

 it's

 not

 enough

 either,

 right?





Uh

 so

 I

 don't

 know.

 Maybe

 in

 10

 years,





maybe

 not

 in

 10

 years,

 maybe

 it

 takes

 30





years,

 maybe

 it

 takes

 50

 years.

 I

 don't





know.

 Maybe

 it

 takes

 6

 months.

 Maybe





it's

 already

 solved

 more

 or less.

 But

 it





is

 helping

 already.

 So

 the

 use

 case

 I





gave

 you

 with

 chronic

 liver

 disease,





that's

 super

 important.

 By

 the

 way,

 that





was

 the

 previous

 generation

 of

 AI

 that





we

 used

 at

 Databricks.

 We

 trained

 a new





one

 now

 with

 Merck

 and

 it's

 called





Teddy,

 Transformer

 Enabled

 Drug





Discovery.

 Transformer

 Enabled

 Drug





Discovery

 is

 a model,

 transformer

 model,





but

 instead

 of,

 you

 know,

 the

 next

 token





being

 English

 it's

 the

 Gene

 Regulatory





Network,

 GRN.

 So

 it

 actually

 can

 say,





okay,

 this

 genome

 is

 actually

 causing





this

 disease.

 This

 genome

 is

 just





reacting

 to

 it.

 So

 don't

 target

 it

 for

 a





drug.

 So

 this

 will

 accelerate

 drug





discovery.

 It's

 a

 game

 changer,

 you





know.

 Um

 drug

 discovery

 aside,

 like,

 you





know,

 I'll

 give

 you

 another

 example

 like





Crisis

 Text

 Line.

 It

 uses

 Databricks

 and





uses

 large

 language

 models

 and

 these





agents

 and

 they

 actually

 detect

 if

 kids





want

 to do

 self-harm

 and

 it

 helps





prevent

 that,

 right?

 Um

 you

 know,

 Virtue





Foundation

 uses

 uh Databricks.

 Um

 you





know,

 Zipline

 uh

 this

 was

 a,

 you

 know,





use

 case

 that

 was

 reported

 before,

 used





Databricks

 to

 deliver,

 you

 know,

 food.





Uh

 they

 had

 these

 drones,

 right?

 The





drones

 that

 would

 deliver,

 you

 know,





everything

 about

 those

 drones

 and

 so

 on





like

 their

 their

 path,

 the,

 you

 know,

 um
</details>

>> 噢真的吗？大数据。

<details><summary>Original English</summary>
>> Oh really?

 Big

 data
</details>

>> 是的，所有那些都在运行。所以我们看到这些……

<details><summary>Original English</summary>
>> Yeah,

 all

 of

 that

 was

 running.

 So

 we

 see





these
</details>

>> 很棒的公司。

<details><summary>Original English</summary>
>> Great

 company.
</details>

### AI 落地节奏与现实预期

>> 是的，我们一直看到 AI 的这些应用案例，它确实会让世界变得更美好。风险是存在的，我们也会去应对那些风险。人们感到焦虑是因为一切都在发生变化。而且我认为在 AI 公司里，有很多研究人员，他们或许对研究理解得非常透彻，但他们还没有关注过经济现实究竟是怎样的？未来会发生什么？这些事情将如何演进？

<details><summary>Original English</summary>
>> Yeah,

 we

 see

 these

 use

 cases

 all

 the





time

 with

 AI

 and

 it is

 going

 to make

 the





world

 a better

 place.

 There

 are

 risks.





We

 will

 deal

 with

 those

 as

 well.





People

 are

 nervous

 because,

 you

 know,





things

 are

 changing.

 And

 I

 think

 AI





companies,

 there's

 a lot

 of researchers





who

 maybe

 you

 know, they

 understand

 the





research

 very

 well,

 but

 they

 haven't





looked

 at,

 you

 know,

 how

 does

 the





economy

 look?

 What's

 going

 to happen?





You know,

 how

 does

 these

 things

 going

 to





evolve?
</details>

>> 而且他们看了太多的科幻作品。说实话，他们是受到了某种特定叙事的影响。说有 10% 的几率导致 70 亿人因 AI 而丧生，这种想法显得极其荒唐可笑，以至于当你抛出一个具体数字时，反倒在普通大众眼里显得可信了。普通人会觉得：“嗯，这些都是赚大钱的聪明人。既然他们都这么想，也许他们是对的。”

<details><summary>Original English</summary>
>> And

 they've

 watched

 a

 lot

 of

 sci-fi.





Let's

 be

 honest.

 Like

 they

 are

 being





informed

 by,





you

 know,

 a

 certain

 narrative.

 And

 the





idea

 that

 there's

 a

 10%

 chance

 that

 7





billion

 people

 die

 because

 of

 AI

 seems





so

 farcical

 and

 out

 there

 that

 when

 you





pick

 a

 number,

 it

 makes

 you

 seem





credible





to

 an

 average

 Joe

 who's

 like,

 well,





these

 are smart

 people

 who

 make

 a lot

 of





money.

 And

 if

 they

 think

 it,

 maybe





they're

 right.
</details>

>> 既然他们自己都这么说了，对吧？人们就是这么想的。

但我个人认为，那种风险接近于零。我认为网络安全风险是真实存在的，确实可能发生非常严重的事情，这也是我们关注的重点。

另外，我认为要真正解决我提到的企业内部的这种上下文差距，也就是我们所关注的真正让价值在各处落地的目标，我认为这需要 10 年时间。我认为这是一件需要 10 到 15 年的事情。那些实验室认为这会在未来 6 个月、12 个月或者 2 年内发生。但我实际上认为 GDP 的变动会非常缓慢，我们需要经历十年才能真正走完这个过程。为什么？正如我所说的，只要回顾一下开头的那个小故事：那位银行 CEO 说他们甚至无法对会议进行录音。如果你连会议都无法录音，AI 甚至都不知道会议里发生了什么，那它怎么可能做到我向你展示 Genie 和本体时讨论过的那些事情呢？

<details><summary>Original English</summary>
>> If

 they're

 saying

 it

 themselves,

 right?





That's

 how

 people

 think.

 But





I

 for

 me,

 that

 risk

 is,

 you know,

 close





to

 zero.

 I

 think

 the

 cyber

 risk

 is

 real





and

 really

 bad

 things

 can

 happen

 without





that's

 where

 we

 focused

 on

 it.





You

 know,

 and

 then,

 you know,

 I

 think





actually

 for

 to

 solve

 this

 this

 context





gap

 that

 I mentioned

 in

 enterprises,

 the





thing

 we're

 focused

 on

 to

 actually

 get





value

 everywhere,

 actually

 I think

 it's





going

 to

 take

 10

 years.

 You

 know,

 I





think

 this

 is

 something

 that's

 going

 to





take

 10

 15

 years.

 The

 labs

 think

 this





will

 happen

 like

 in

 the

 next

 6

 months,





12

 months,

 in,

 you

 know,

 2

 years.

 But

 I





actually

 think

 GDP

 will

 move

 very

 slowly





and

 it's

 going

 to

 take

 decade

 for

 us

 to





actually

 get

 through

 it.

 Why?

 I mean,

 as





I

 said,

 I mean,

 just

 go

 back

 to the





anecdote

 at the

 beginning,

 the

 you

 know,





the CEO

 of

 the bank

 that

 said

 we

 can't





even

 record

 the

 meetings.

 If

 you

 can't





record

 the meetings,

 the AI

 doesn't

 even





know

 what's

 happening

 in

 the meeting,





how

 could

 it

 possibly

 do

 the

 kind

 of





things

 that

 we

 discussed

 when

 I showed





you

 Genie

 and

 the

 ontology?
</details>

>> 可以肯定的是，这必然是一个有节奏逐步铺开的过程。我们当中确实有些人冲在前面、领先一步在做非常酷炫的事情，这正如我们当年在互联网初期共同经历过的一模一样。当互联网刚问世时，那些把它的功能发挥到极致的人会觉得：“好，这将会改变一切。”然而当时 99% 的人还在用拨号上网，从未见过高速连接。所以他们的大脑根本无法想象出 YouTube，或者无限免费的照片存储。这根本说不通，你怎么可能理解得了呢？

<details><summary>Original English</summary>
>> It's

 going

 to

 be

 a

 paced

 rollout

 to

 be





sure.

 And

 there

 are

 some

 of

 us

 who

 are





running

 ahead

 around

 the

 corners

 doing





really

 cool

 stuff,

 which

 is

 exactly

 what





we

 both

 experienced

 with

 the

 internet.





When

 the

 internet

 first

 came

 out,

 the





people

 who

 were

 using

 it

 to

 its

 fullest





extent

 were

 like,

 okay,

 this

 is going

 to





change

 everything.

 And

 then

 99%

 of





people

 were

 on

 dial

 up

 and

 had

 never





seen

 a

 high

 speed

 connection.

 So

 the





their

 brains

 couldn't

 conceive

 of





YouTube

 or,

 you

 know,

 unlimited

 free





photography

 story.

 Doesn't

 make

 any





sense.

 How

 can

 you

 understand

 that?
</details>

### 早期网络历史与访谈收尾

>> 当年有个叫罗伯特·莫里斯（Robert Morris）的年轻人，用蠕虫病毒搞垮了互联网 10% 的网络。那就是所谓的莫里斯蠕虫（Morris worm）。

<details><summary>Original English</summary>
>> There was

 a kid

 called

 Robert

 Morris





Morris

 who

 took

 down

 10%

 of the

 internet





with

 a worm.

 It's

 called

 the

 Morris





worm.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 他当年差点为此被判入狱。后来他继续深造，成了麻省理工学院著名的计算机科学教授，成了一个非常著名的人物。但你知道，在当年，那直接搞垮了整整 10% 的互联网。

<details><summary>Original English</summary>
>> You

 know,

 he

 almost

 got

 a jail

 jail





sentence

 for

 it.

 Uh

 and

 then he

 went

 on





and

 he

 became

 a

 famous

 MIT

 professor

 in





computer

 science

 and

 he's

 like

 a very





famous

 guy.





But

 you

 know,

 that

 took

 down

 a whole

 10%





of

 the internet

 uh

 back

 in

 the

 day.
</details>

>> 这完全是有可能的。就像在某个时间点——我今天刚看到有人觉得他们可能在某种程度上破解了 Signal。好的，当然，让我们静观其变吧。

好了各位，又是一期精彩的 All-In 专访。阿里（Ali），非常感谢你抽出宝贵时间，我们下期 All-In 专访再见。干得漂亮，阿里，你太棒了。

<details><summary>Original English</summary>
>> Which

 is

 completely

 possible.

 Like

 at





some

 point

 I just

 saw

 today

 somebody





feels

 like

 they

 may

 have

 cracked

 signal





to

 a

 certain

 extent.

 Uh





okay,

 sure.

 Let's

 see

 what

 happens.

 All





right

 everybody,

 another

 great

 all

 in





interview.

 Ali,

 thank

 you so

 much

 for





your

 time

 and

 we'll

 see

 you

 next

 time

 on





the

 all

 in

 interview.

 Boom.

 Great

 job,





Ali.

 You

 are

 awesome.
</details>

>> [音乐]

[音乐]

<details><summary>Original English</summary>
>> [music]





[music]
</details>