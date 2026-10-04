---
author: The Pragmatic Engineer
date: '2026-07-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ddHQQtjIOpw
speaker: The Pragmatic Engineer
tags:
  - extreme-programming
  - agile-manifesto
  - tdd
  - career-development
title: 软件工程的演变史：从极限编程到敏捷宣言与人工智能时代的思考
summary: 本文回顾了核心软件工程实践（如TDD、极限编程）和理念（如敏捷宣言）的起源故事，探讨了编码在整个开发过程中的角色。文章深入分析了大型语言模型对开发步伐的影响，并总结了作者关于如何通过持续尝试与迭代来应对技术变革的哲学，强调了建立信任的重要性。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/16 -->

### 播客引言与片段预告

**Kent Beck**: 软件工程中最难的部分是“人”。这是有史以来最大的宇宙级恶作剧。曾经有人向我们承诺：“这是一台计算机，只要你完全弄懂这台计算机，你就万事大吉了。这就是你需要做的全部。”

<details>
<summary>Original English</summary>

**Kent Beck**: The human part is the hardest part in software engineering. This is the biggest cosmic practical joke ever. We were promised, "Here's this computer and if you completely understand this computer, you'll be fine. That's all you need to do."

</details>

**Host**: TDD 是什么时候出现的？

<details>
<summary>Original English</summary>

**Host**: When did TDD come along?

</details>

**Kent Beck**: 我当时只是在瞎折腾，我会在写代码之前先把测试写好。我记得当时自己放声大笑，因为这主意太蠢了。你为什么要写一个明知道会失败的测试呢？TDD 就是一个很好的例子，它几乎完全过时了。其中很大一部分原因是我在某个东西上做了一段时间，然后我就转向其他事情了。我继续做下一件事。TDD 就那样被放在那里，然后有一些人把它当作一种道德大棒，就像是……如果你不用 TDD，你就是不专业的。
极限编程（Extreme Programming）就这样诞生了。我绝不想让 Grady Booch 说他也在做这个东西。所以我必须选一个足够缺乏吸引力的名字，免得有人试图剽窃它。这也带有一点对传统体制嗤之以鼻的意味。当时极限运动（Extreme Sports）很流行。我喜欢用极限运动来打比方。

<details>
<summary>Original English</summary>

**Kent Beck**: I was just kind of farting around and I would write the test before I wrote the code. And I can remember laughing out loud cuz it was such a stupid idea. Why would you write a test that you know is going to fail? TDD is a good example where it almost went out of style completely. The big part of it is I work on something for a while and then I switch to something else. I moved on to the next thing. TDD is out there [music] and then there were people who used it as a moral cudgel like you should be... if you're not using TDD you're not professional. 
Extreme programming was born. I didn't want Grady Booch to ever say that he was doing this thing. So I had to pick a moniker that was unattractive enough that somebody would try and steal it. A little bit of thumb the nose at the establishment. Extreme sports were there. I like the analogy with extreme sports.

</details>

**Host**: 17 个人参与其中，但你是第一个被列出来的。关于《敏捷宣言》。

<details>
<summary>Original English</summary>

**Host**: 17 people rolled, but you're the first one listed. The Agile Manifesto.

</details>

**Kent Beck**: 当时进展并不顺利，因为有这么多人，大家都说：“我想把我的东西加进去。”“不行，我想加我的，但这跟你的东西冲突了。”于是我们休息了一下。我们走出去，而 Martin 和 Jim Highsmith 留在了里面。等我们休息完回来时，《敏捷宣言》的基础框架就已经在那里了。

<details>
<summary>Original English</summary>

**Kent Beck**: Things weren't going very well because there's all these people and, "I want my stuff in." "No, I want my stuff in, and that contradicts your stuff." And we took a break. We walked out and [music] Martin and Jim Highsmith stayed behind. When we came in from the break, there was the basics of [music] the manifesto.

</details>

**Host**: 几年来，我们有了大语言模型（LLMs）。其中一个影响是，开发步伐肯定加快了。我一直在想……Kent Beck 是这个行业中活着的传奇之一。他极大地塑造了软件工程这个职业，直到今天仍在产生影响。但是，一直没有一期播客节目涵盖他从入行到现在的整个职业生涯，直到今天。
在这次对话中，我们聊到了 Kent 在 70 年代是如何伴随着计算机成长的，以及他是如何爱上 Smalltalk 的。TDD、极限编程和《敏捷宣言》背后的起源故事，以及为什么“敏捷（Agile）”这个词是个错误。还有一些鲜为人知的故事，比如他是如何被苹果公司解雇的，Kent 在 2000 年代“失去的十年”，以及为什么他认为 TDD 已经失败了。他如何看待和使用 AI，在写了 40 多年代码之后，还有什么能让他对编程感到兴奋，以及更多精彩内容。
如果你想了解真正的传奇是如何被行业塑造，又是如何亲自塑造软件工程的，这期节目就是为你准备的。这期节目比我大多数的播客都要长，但我真心希望你会觉得，花时间听 Kent 进行他有史以来最长的一次个人故事讲述，是物有所值的。
本期节目由 Antithesis 呈现。如果你在开发 AI 智能体（Agents），你的工作不再仅仅是编写代码，而是对其进行规范化和测试。而 Antithesis 是目前验证智能体代码最有效的方法。
本期节目由 Turbopuffer 赞助播出。关于 Turbopuffer 的一件趣事是，他们如何成为了 AI 智能体的搜索引擎。似乎每个星期，他们都会增加一个来自顶级 AI 公司的新用例。RAM、Lorra、Harvey、Granola，他们都在使用 Turbopuffer。或者用他们团队的话说，他们都在“puffing”。Turbopuffer 提供了一整套搜索工具：向量搜索、全文搜索、属性过滤、正则表达式等等，全都在一个 API 中。它建立在对象存储作为唯一有状态依赖项的基础上。因此，它具有极高的可扩展性、可靠性，而且价格便宜。得益于其智能缓存层，它的速度也非常快。关于 Turbopuffer 还有个很酷的地方，你可以拥有无限的搜索索引。因此，它非常适合多租户的 AI 应用程序。为每个租户建立一个索引，数据默认隔离，你可以毫不费力地进行扩展。最棒的是，Turbopuffer 上周刚刚宣布，他们已将基础价格从每月 64 美元降至每月 16 美元。所以，现在是体验它的最佳时机。请访问 turbopuffer.com/pragmatic。

<details>
<summary>Original English</summary>

**Host**: For a couple of years, we've had AI alums. So, one of the things is that the pace of development is definitely accelerated. One thing I wonder... Kent Beck is one of the living legends of the industry. He's greatly shaped the software engineering profession and keeps impacting it even today. But there's not been a podcast episode covering his whole career from start to present, until today.
In this conversation, we cover how Kent grew up with computers in the 70s and how he fell in love with Smalltalk. The origin stories behind TDD, Extreme Programming, and the Agile Manifesto, and why "Agile" the word was a mistake. Lesser known stories like how he got fired from Apple, Kent's lost decade in the 2000s, and why he thinks TDD has failed. How he thinks about and uses AI, and what still excites him with coding after 40-plus years, and many more.
If you'd like to understand how true legends were shaped by the industry and shaped software engineering himself, this episode is for you. This episode is longer than most of my podcast episodes, and I do hope that you'll find that it's worth the time to listen to Kent longer than he's ever told his story in one setting before.
This episode is presented by Antithesis. If you work with agents, your job is no longer just writing code. It's specifying and testing it. And Antithesis is the most effective method of verifying agent code today.
This episode is brought to you by Turbopuffer. A fun fact about Turbopuffer is how they became the search engine for AI agents. It seems like every week they add a new use case from one of the leading AI companies. RAM, Lorra, Harvey, Granola, they're all on Turbopuffer. Or as the team likes to say it, they're all puffing. Turbopuffer offers a full set of search tools: vector search, full text search, attribute filtering, regex, and more in one API. It's built on object storage as a sole stateful dependency. So, it's extremely scalable, reliable, and cheap. But it's also very fast thanks to its intelligent caching layer. One cool thing about Turbopuffer is you can have unlimited search indexes. So, it's perfect for multi-tenant AI applications. Build an index per tenant, data is isolated by default, and you can scale without thinking about it. Here's the best part. Turbopuffer just announced last week that they've dropped their base price from $64 per month to $16 per month. So, there has never been a better time to test it out. Head to turbopuffer.com/pragmatic.

</details>

### 人与代码的边界

**Host**: 很高兴能邀请您亲自来到播客节目。老伙计，很高兴再次与您交谈。是的，我想从一个非常合时宜的话题开始。Dario 发了一条病毒式传播的推文，我引用一下他的话：“编码将先于整个软件工程消亡。”您对此有一些看法。

<details>
<summary>Original English</summary>

**Host**: And it's so good to have you in person on the podcast. Guy, it's great to talk to you again. Yeah, I wanted to kick off with something really timely. There was this tweet going viral by Dario where he said, I quote, "Coding is going away first than all of software engineering." You had some things to say about it.

</details>

**Kent Beck**: 是的。我的回应是，这是一个不了解软件工程的人说出的话。编码是你工作的一部分，但它只是你工作的一小部分。即使它占用了相当多的时间，你在这个过程中其实是在建立信心，建立与他人的联系，建立你自己的理解。所有这些事情都是在你写代码的时候发生的。而编码实际上是巩固理解的绝佳方式。你编程编得越多，你对所从事的领域就理解得越深。所以，那种“好吧，我们要把这一切都交给机器”的说法，显然没有看到事情的全貌。

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah. My response is that that's a statement by someone who doesn't understand software engineering. Coding is part of what you're doing, but it's only a small part of what you're doing. Even if it takes up a fair amount of time, you're building confidence, you're building connections with other people, you're building your own understanding. All those things are happening while you're coding. And coding's actually a great way to cement understanding. The more you program, the more you understand the domain that you're working in. So to say, "Well, we're just going to pass all that off to a machine." Well, you're... that's not all there is to it.

</details>

**Host**: 这很有意思，因为大语言模型非常明显的一个特点就是它们写代码真的很快，对吧？过去我们需要花很多时间把它敲出来，还要花时间去思考，但您的意思是，在那个过程中也包含了思考和理解，对吗？

<details>
<summary>Original English</summary>

**Host**: Interesting because one thing that is so obvious with LLMs is they just code really quickly, right? Like, it used to take us a lot of time to both type it out and also thinking out, but you're saying that there was thinking involved and understanding involved as well in that process, right?

</details>

**Kent Beck**: 前几天我看到一句话，它真的触动了我：我们积累代码的速度超过了我们积累信任的速度。而那种信任感来源于我努力去理解某个领域概念。我弄懂了它，在代码中把它表达出来。我编写测试来证明我确实理解了它。现在，我信任我的程序了。但如果我们一起编程，一起编程的行为意味着我们更加信任彼此了。如果我们和最终用户交谈，并且展示我们理解他们的需求，当他们告诉我们：“我想要一个具备这个功能的按钮。”我们会问：“那你到底想解决什么问题？”然后我们来回沟通探讨。这同样建立起了人际信任。这些都无法被自动化。如果我们只给机器发指令，那些事就不会发生——你知道的，就像精灵打了个响指说：“好的老板，全都搞定了。”这时候你就会觉得：“等等，搞定了？什么搞定了？”

<details>
<summary>Original English</summary>

**Kent Beck**: So a couple of days ago I saw a phrase and it really hit me that we're accumulating code faster than we're accumulating trust. And that sense of trust comes from me struggling to understand some domain concept. I get it. I represent it in the code. I write tests that demonstrate that I really did understand it. And now I trust my program. But if we're programming together, that act of programming together means that we trust each other more. If we talk to someone, an eventual user, and we demonstrate that we understand their needs and we, you know, they tell us, "Well, I want a button that does this." We're like, "Well, what problem are you really solving?" And we go back and forth and back and forth. That builds human trust as well. None of that can be automated. None of that occurs if we prompt the—we get the finger guns, you know, the genie goes, "Yeah, it's all finished, boss." And it's like, "Well, hang on. Finished? What's finished?"

</details>

**Host**: 当我们在讨论软件工程时，您提到了信任、联系、理解。您没有提到技术，没有提到编程语言，甚至没有提到重构。这真的很有意思。您从事这一行大概有 50 多年了。我可以理解为，在软件工程中，“人”的部分是最难、或者说是最重要的部分吗？

<details>
<summary>Original English</summary>

**Host**: As we're talking about software engineering, you mentioned trust, connection, understanding. You didn't mention technologies, you didn't mention programming languages, you didn't mention... wouldn't even mention refactoring. This is really interesting. You've been doing this for what, 50 plus years now. Do I understand that the human part is the hardest or most important part in software engineering?

</details>

**Kent Beck**: 这是有史以来最大的宇宙级恶作剧。作为年轻人——其中有些人，像我一样，并不是很懂人类——我们曾得到承诺：“好吧，这是一台计算机，只要你完全弄懂这台计算机，你就万事大吉了。这就是你需要做的全部。”所以在我职业生涯的初期，我下定决心要成为我所能成为的最优秀的程序员，因为那是取得成功的必经之路。然后……惊喜来了！竟然还有整整一面属于“人”的部分，而你改变世界的能力，取决于你与人沟通、共情的能力……共情并非我天生的强项……去说服、去沟通、去安抚、去理解其他人。而这些，恰恰是我曾经以为不需要学习的技能。所以我先是被承诺“只要懂电脑就行”，然后又被告知“开个玩笑，你要懂人”，而当时我在这一块已经落后了十年。

<details>
<summary>Original English</summary>

**Kent Beck**: This is the biggest cosmic practical joke ever. As young people who—some of whom, like I, don't understand humans very well—we were promised, "Okay, here's this computer, and if you completely understand this computer, you'll be fine. That's all you need to do." So I set out the first part of my career just to become the best programmer that I could be, because that's what it would take to be successful. And then... sorry, there's this whole human side, and your ability to affect change in the world is gated by your ability to communicate with, empathize with... empathy is not my natural strong suit... to convince, to communicate with, to soothe, to understand other human beings. And those are exactly the skills that I thought I didn't need to learn. So I was promised, "Just understand the computer," and then, "Just kidding, understand people," from a position where I was already 10 years behind.

</details>

### 回溯起源：早期计算机岁月

**Host**: 所以我想回到那里，回到最开始的地方。因为很多人是通过你的书，通过许多你参与创造或推广的技术认识你的：极限编程（XP）、测试驱动开发（TDD）、以及许多小型重构等等。但回顾过去，这一切是如何开始的呢？你第一次接触计算机是什么时候？我知道你父亲是一位电气工程师。

<details>
<summary>Original English</summary>

**Host**: So I'd like to go back to right there, to the very beginning. Cuz so many people know you from your books, from a lot of the techniques that you've co-created or made a lot more popular: XP, TDD, a bunch of other just small refactorings and so on. But going back, how did it all start? How did you have your first contact with computers? I know your father was an electrical engineer.

</details>

**Kent Beck**: 是的。我父亲起初就是一名电气工程师。在朝鲜战争期间，他在海军担任无线电操作员。退役后，他去上学，拿到了电气工程学位，开始在航空航天领域做电气工程师。然后我们搬到了桑尼维尔（Sunnyvale），那里是后来硅谷的前身……

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah. So, my father started out as an electrical engineer. He was in the Navy in the Korean War as a radio operator. Came out of that, went to school, got an electrical engineering degree, started working in aerospace as an electrical engineer, and then we moved to Sunnyvale, Silicon Valley before it was Silicon...

</details>

<!-- chunk 2/16 -->

### 硅谷早期的编程启蒙

**Speaker B**: 谷。那还是在“硅（Silicon）”被发明出来之前的事情。

<details>
<summary>Original English</summary>

**Speaker B**: Valley. This is before the invention of Silicon.

</details>

**Speaker A**: 噢，那是在这之前。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, this was before.

</details>

**Speaker B**: 是的。在这之前，那个时候在埃尔卡米诺（El Camino）还有樱桃园。我差不多就是那个时候出生在那里的。所以，当时我上六年级。他带回家一个可编程计算器，那个计算器有……没这张桌子这么大，可能只有这张桌子的一半大。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Before there was this is when there were still uh cherry orchards on El Camino. And I was born there about the time So I was in sixth grade. He brought home a programmable calculator which was as big as not as big as this table, maybe half the size of this table.

</details>

**Speaker A**: 估计重达……

<details>
<summary>Original English</summary>

**Speaker A**: Probably weighed 

</details>

**Speaker B**: 65或70磅。是的，是的。大概是……

<details>
<summary>Original English</summary>

**Speaker B**: 65 or 70 lb. Yeah. Yeah. It was 

</details>

**Speaker A**: 65磅。

<details>
<summary>Original English</summary>

**Speaker A**: 65 lbs.

</details>

**Speaker B**: 它有，呃，它有数码管（Nixie tubes）。数码管就是，这是在七段发光二极管（LED）出现之前，因为那时LED还没有被发明出来。嗯，你会有，呃，一个里面有10根灯丝的白炽灯泡，灯丝的形状就是数字。我的第一个程序是，呃，是一个只会向上数、向下数、再向上数、向下数的循环，因为那些灯丝是一个接一个排在前面的。0、1、2、3、4、5、6、7、8、9。所以，我，我就，呃，写了一个向上数和向下数的程序，因为我喜欢看着这个数字来来回回，来来回回地变动，能看上好几个小时。我就是可以……当时真是……

<details>
<summary>Original English</summary>

**Speaker B**: And it had uh it had Nixie tubes. Nixie tube is this is before seven segment LEDs cuz LEDs hadn't been invented. uh you'd have a uh an incandescent light bulb with 10 filaments in the shape of the numbers. And my first program was uh was a loop that would just count up and down and up and down because the filaments were set one in front of the other. 0 1 2 3 4 5 6 7 8 9. So, I I just uh wrote a program that would count up and down cuz I loved watching this go back and forth and back and forth and back for hours. I could just was 

</details>

**Speaker A**: 令人着迷。噢，

<details>
<summary>Original English</summary>

**Speaker A**: mesmerizing. Oh,

</details>

**Speaker B**: 绝对的。那是我第一次亲手接触到真正的硬件。不过我也发现，我爸爸会带一些书回家，而我是那种有点强迫症、有点泛自闭症谱系特征的孩子。我会强迫症般地阅读这些书，最近在，呃，在搬家期间，我找到了其中的一本，是《Burroughs B6700指令集手册》。这是一台非常有趣的、能在早期给人留下深刻印象的机器，因为它有一个硬件堆栈。它不是基于寄存器的，而是基于堆栈的。他们是如何用离散晶体管做到这一点的，我永远也弄不明白。但这确实是一个非常有趣的架构。那本书我就一遍又一遍地读那些书页，我什么也看不懂，但我就是对这个机制着迷。所以，当我得到一台真正的机器，并且我可以玩它，还有些类似于汇编语言的东西，并且我能让它做事情的时候，我可以在脑子里产生一个想法，如果我理解了这个机制，我就可以让它做我脑子里的事情，而这又会激发出下一个想法。真正让我入迷的正是这一点，就是那种创造的冲动与对机器的了解相结合，我能够在世界上创造出我想要看到的东西，而且这非常早，那是70年代，对吧。微软大概是72年，所以微软甚至还没有成立……成立于75年。

<details>
<summary>Original English</summary>

**Speaker B**: absolutely. That was the first time I had my hands on any real hardware. Although I did find my dad would bring home books and I was a kind of obsessive spectrumy kind of kid. I would obsessively read these books and I found one of them lately in uh in during a move, the Burroughs B6700 instruction set manual. And this was a really interesting machine to imprint on early because it has a hardware stack. It wasn't register based, it was stack based. How they did that with discrete transistors, I will never know. But it's just a really interesting architecture. And that book I would just read the pages over and over and I understood nothing but I was just fascinated with this mechanism. So when I got an actual machine and I could play with it and something that that resembled assembly language and I could get it to do stuff, I could have an idea in my head and if I understood this mechanism, I could get it to do the stuff in my head which would spark the next idea. That's what really hooked me is is that that creative impulse coupled with knowledge of the machine together I could create things in the world that I wanted to see and this was very early '7s right Microsoft 72 maybe so Microsoft wasn't even founded founded in 75

</details>

**Speaker A**: 那时是什么样的？就这些机器有多常见或多罕见而言。我的意思是，你当时在多大程度上认为它们会有发展前景，或者这只是一个刚刚被发明出来的有趣东西？

<details>
<summary>Original English</summary>

**Speaker A**: what was it like in terms of how common or uncommon were these machines means how much or little did you even think that they would go anywhere or was it just just a a fun thing that has just been invented?

</details>

**Speaker B**: 微型化的第一波浪潮很可能就是可编程计算器。

<details>
<summary>Original English</summary>

**Speaker B**: Probably the first wave of miniaturaturization was the programmable calculator.

</details>

**Speaker A**: 嗯哼。

<details>
<summary>Original English</summary>

**Speaker A**: Mhm.

</details>

**Speaker B**: 就是你爸爸带回家的那个。

<details>
<summary>Original English</summary>

**Speaker B**: So the one that your dad brought home.

</details>

**Speaker A**: 不是的，是那种像掌上计算器一样的。好的。所以，所以，所以那种大的桌面计算器是一回事，但后来有了这些小计算器。我记得我爸爸花400美元买了一台HP35，也就是……我不知道这在今天相当于多少钱，但光是买这个小东西就是一大笔钱。

<details>
<summary>Original English</summary>

**Speaker A**: So no, the like handheld calculators. Okay. So, so, so the the big tabletop calculators was was one thing, but then there were these little calculators. I remember my dad buying an HP35 for $400, which is I don't have no idea how much that would be today, but a lot of money just for this little thing.

</details>

**Speaker B**: 在当地估计得值2000美元吧。

<details>
<summary>Original English</summary>

**Speaker B**: It'll probably $2,000 location.

</details>

**Speaker A**: 是的。所以你，你必须在脑子里记住堆栈，我想按什么顺序放入操作数，你知道，确保我把所有的东西都压入堆栈，然后你按下加号（+），那就会把东西从堆栈里弹出来。然后HP45出现了，它会有……它里面有自己的小编程语言，那就感觉像是，好的，这真是太酷了。后来微处理器开始问世，我们有了Z80，还有808，以及6800，我爸爸和我一起焊接了我们的第一台基于6800的机器。然后我们用汇编语言编程。之后Basic语言出现了，然后……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So you you had to keep the stack in your head of what order do I want to put the operands in and you know make sure that I stack everything and then you go plus+ and that would pop stuff off the stack. And then the HP45 came along and it would it had its own little programming language in it and that was just like okay this is really really cool. And then microprocessors started to come out and we had the Z80 and the 808 and the 6800 and my dad and I soldered together our first 600 6800based machine. Then we were programming in assembly language. Then out came basic then

</details>

**Speaker B**: 这已经是70年代中期了。

<details>
<summary>Original English</summary>

**Speaker B**: this was mid70s.

</details>

**Speaker A**: 是的。是的。所以，所以那是真的……我，我花了很多时间在那台机器上工作。同样，我不会说我在一个精英层面上理解它，但我被迷住了。我能了解到的关于它的一切，都让我在那种创造的冲动、对世界上某个事物的想象以及执行上变得更加有效。世界上有这么个东西。那对我来说感觉一直都很棒。然后当到了上大学的时候，你，你选择了俄勒冈大学（University of Oregon），对吧？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah. So, so that was really I I was spending a lot of time working on that machine. Again, I wouldn't say I understood it at a at an elite level, but I was fascinated. I Everything I could learn about it made me that much more effective at that creative impulse, imagination of a thing in the world, execution. There's a thing in the world. And that just has always felt great for me. And then when it came to college, you you chose University of Oregon, right?

</details>

**Speaker B**: 嗯，其实算是俄勒冈大学选择了我，因为我申请的其他地方都没有录取我。

<details>
<summary>Original English</summary>

**Speaker B**: Well, University of Oregon kind of chose me because no none of the other places I applied accepted me.

</details>

**Speaker A**: 不会吧。

<details>
<summary>Original English</summary>

**Speaker A**: No way.

</details>

**Speaker B**: 是的。那你在那里学了什么？你的大学岁月过得怎么样？

<details>
<summary>Original English</summary>

**Speaker B**: Yep. And what did you study there? How how did your college years go?

</details>

**Speaker A**: 嗯，第一年是计算机科学。而且……

<details>
<summary>Original English</summary>

**Speaker A**: Well, the first year was computer science. And

</details>

**Speaker B**: 所以他们那时已经有计算机科学专业了。是的。是的。那时我们已经发明了计算机科学。第一年是计算机科学。而且，我也很喜欢它，但我，我仍然不是一个伟大的程序员，但我能轻而易举地通过课程。所以，我有一点觉得无聊。于是，在大二开学前，天气非常热，我当时正走过音乐楼，那里有一些，一些报名参加试音的海报。我心想：“哦，我会弹吉他。让我看看我能做些什么。”接下来的事情你大概猜到了，我成了一名音乐专业的学生。所以，[笑声]

<details>
<summary>Original English</summary>

**Speaker B**: so they already had a computer science. Yes. Yes. We had invented computer science by then. The first year was CS. and and I enjoyed it, but I I still wasn't a great programmer, but classes I breezed through. So, I was a little bit bored. So, before the start of my sophomore year, it was really hot and I was walking through the music building and there were some some flyers for uh signing up for auditions. I thought, "Oh, I play guitar. Let me see what I can do." Next thing I knew, I was a music student. So, [laughter]

</details>

**Speaker A**: 哇。

<details>
<summary>Original English</summary>

**Speaker A**: wow.

</details>

### 从音乐到软件的转折

**Speaker B**: 所以，我一直在弹吉他，我是从八岁开始弹吉他的，差不多是民谣热潮的末期。卡德夫人（Mrs. Card）在暑期学校的课上，然后，呃，呃，我们家周围放着一把吉他。所以我就，我就去了，并且又一次痴迷了。她会教我们一些东西，我回家后就会一直弹，直到手指流血，第二天去的时候，其他人差不多还在原来的进度，但我已经掌握了一些拨弦模式，一些扫弦模式，因为我就那样弹了三四个小时。所以，我非常喜欢音乐，在高中时我在合唱团，这可是件大事。我们高中没有太多体育运动，但我们绝对有音乐。所以我会学习音乐是很自然的事情。在学了一年音乐之后，我想念编程了，所以我又回到了编程。然后我又回到音乐专业，这样我就能完成我的毕业独奏会。之后我又回到编程领域攻读硕士学位，呃，又花了一年时间，并且，呃，完成了它。所以，就像我说的，我只是在错误的一年结束了。是的。因为我，我查了一下，我想总共是八年。呃，就是你在俄勒冈，在俄勒冈大学度过的时间。

<details>
<summary>Original English</summary>

**Speaker B**: So, I'd been playing I started playing guitar when I was eight, kind of the end of the folk boom. Mrs. Card at a summer school class and uh uh there was a guitar laying around at our house. And so I I went and and again just obsessed. She'd show us something and I'd go home and I'd play it until my fingers bled and come in the next day and and everybody else was kind of where they were before, but I would have mastered some picking pattern, some strumming pattern because I just played it for three, four hours. So, I was very into music and in high school I was in the choir and which was the big deal. We didn't have a lot of sports at our high school, but we certainly had music. It was kind of natural that I would study music. At the end of a year of music, I missed programming, so I went back to programming. Then I went back to music so I could do my senior recital. Then I went back to programming for a master's degree uh in another year and and uh finished that. And so and as I say, I just ended on the wrong year. Yeah. Because I I I checked I think it was eight years in total. uh that you spent at Oregon at University of Oregon.

</details>

**Speaker A**: 5年全日制，然后我在完成硕士论文时遇到了一段艰难的时期。

<details>
<summary>Original English</summary>

**Speaker A**: 5 years full-time and then I had a hard time finishing my master's thesis.

</details>

**Speaker B**: 为什么会觉得困难？你的硕士论文是关于什么的？

<details>
<summary>Original English</summary>

**Speaker B**: Why did you have a hard time? What was your master's thesis on?

</details>

**Speaker A**: 是一种新颖的查询语言。不出所料，我和那些权威人物相处得不好，这也是我职业生涯中的一个主题。是的。就是觉得很难去走完那些过场，然后把整个事情完成。人们说：“哦，如果你放弃，你会后悔的。我当时就是准备不干了。”我就是觉得：“是啊，你们知道的，这些全是走形式，和编程毫无关系，而且那时我已经作为一名程序员赚取了不错的收入。所以，哦，但是如果你没拿到学位，你一定会后悔的。如果你不完成，你离成功就差那么一点了。”但就我目前所知，这从来，从来没有对我有一点帮助。所以，但是你完成了。

<details>
<summary>Original English</summary>

**Speaker A**: It was a novel query language. Not surprisingly, I did not get along with the authority figures, which is a a theme of my career. Yeah. Just had a hard time like checking off all the boxes and getting getting the whole thing finished. People said, "Oh, you're gonna be sorry if you I was just ready to quit." Just like, "Yeah, you know, this is all hoop jumping and has nothing to do with programming and I was making a good living as a programmer by then. So, oh, but you're going to regret it if you don't get your degree. If you don't finish, you're so close." And it's never never helped me one bit as far as I can tell. So, but you completed it.

</details>

**Speaker B**: 我的确完成了。把事情做完是很重要的，在从对世上某物的愿景，到细致的操作，再到该事物在世上呈现的这个过程中，必须要有某种形式的完成，即便我……呃……就像杰西·杰克逊（Jesse Jackson）牧师说的那样，呃，我是一个摇树的人，而不是一个做果酱的人，那绝对就是我。是的，这在你的工作上也是千真万确的，在软件领域也是如此。好吧，我一直，我一直在切换话题。那……那可能是我们在谈论我曾从事的各种事情时会涉及到的。

<details>
<summary>Original English</summary>

**Speaker B**: I did complete it. It is important to complete things that in that in that process from vision of thing in the world to careful activity to the thing in the world there has to be some finishing even if I'm uh as the Reverend Jesse Jackson said uh I'm a tree shaker not a jelly maker and that's definitely me. Yes it's true true for your work as well also for software. Well, I keep I keep switching topics. That's uh that's something that'll probably come up as we go through the various things that I've worked on.

</details>

**Speaker A**: 你的第一份工作是什么？那是在你快要毕业的那几年吧。你开始做程序员了，对吗？

<details>
<summary>Original English</summary>

**Speaker A**: What was your first job? It was while you were still finishing your degree the the last few years. You started to work as a programmer, right?

</details>

**Speaker B**: 没错。所以在那个，呃，读研究生的那一年，泰克公司（Tektronix）的一个团队下来做了一个关于他们正在做的编程环境工作的演讲。泰克公司，呃，最初是波特兰（Portland）的一家电子测试设备公司。在他们的小利基市场里做得很好，但他们，他们像当时很多公司一样，开设了一个工业……呃……工业实验室来进行基础研究，而这项基础研究的一部分就是关于，呃，编程环境的。他们来做了一个演讲。呃，我问了他们一些他们无法回答的问题，所以他们请我出去吃晚饭，这带来了一次面试，进而促成了一份工作。

<details>
<summary>Original English</summary>

**Speaker B**: Correct. So during that uh graduate student year, a team from Tektronics came down to give a presentation about the programming environment work they were doing. Tektronics was uh started out as an electronic test equipment company in Portland. Did well in their little niche, but they they opened up an indust uh industrial lab as lots of companies at that point did to do basic research and part of that basic research was on uh programming environments. They came and gave a presentation. Uh, I asked them questions they couldn't answer and so they invited me out to dinner which led to an interview which led to a job.

</details>

**Speaker A**: 泰克公司是一个很有意思的经历，因为你就是在这里认识沃德·坎宁安（Ward Cunningham）的，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: Tektronics was an interesting one because this is where you met Ward Kunigum, right?

</details>

**Speaker B**: 是的。所以，呃，泰克公司很早就投资了这种疯狂的面向对象编程语言。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, uh, Tektronics had invested early in this crazy object-oriented programming language

</details>

<!-- chunk 3/16 -->

### 初识 Smalltalk 与其魅力

**Speaker A**: ……叫做 Smalltalk，并试图将其商业化。我到了那里，看了在俄勒冈（Oregon）展示的研究，发现它已经差不多发展到头了。但这个叫 Smalltalk 的东西，哇，太酷了。所以我一头扎了进去。

<details>
<summary>Original English</summary>

**Speaker A**: ...called Small Talk and was trying to make a commercial go of it. And I got there and the looked at the the research that had been presented down at Oregon and it kind of played itself out. But this small talk thing, wow, that's cool. So I dove right into that.

</details>

**Speaker B**: 对于我们这些没接触过 Smalltalk，可能只是听说过的人来说，到底是什么让 Smalltalk 如此受欢迎？是什么吸引了你？这门语言是什么样的？

<details>
<summary>Original English</summary>

**Speaker B**: For those of us who have not touched small talk, might have heard of it. What made small talk so such a hit? What pulled you in? What is the language like?

</details>

**Speaker A**: 丹·英格尔斯（Dan Ingalls）写过一篇很优美的论文，叫作《Smalltalk 背后的设计原则》（The Design Principles Behind Smalltalk），开篇第一句就是：“Smalltalk 是为每个人身上的创造精神提供计算机支持的。”这里面有两大主题。其一是编程语言，也就是 Smalltalk 语言本身；其二是交互语言，比如重叠窗口、作为指针设备的鼠标、窗格（panes）、滚动条等，这些都是由它的用户界面开创的东西。如今这些东西都很常见了。但是，Smalltalk 这门语言，是基于极少数的基本原语构建出来的。这门语言实际上只有三个原语：发送消息、变量赋值，以及返回值。真的就只有这些。所以，嗯，也许在快结束的时候我们可以聊聊我现在的项目，其中之一就是从头开始重新构建一个新的 Smalltalk，只是因为现在这对任何人来说都是触手可及的事情了。

但我发现它最美妙的地方在于，这门语言将自身的机制推向了绝对的极限。所以在 Smalltalk 中，万物皆对象，包括数字在内。你不需要去调用一个将两个整数相加的函数。你是向一个整数发送一个 `plus` 消息，这个整数接收消息并把另一个对象作为参数。如果那个对象恰好也是个整数，那么你就能把它们加起来。

<details>
<summary>Original English</summary>

**Speaker A**: There's a beautiful paper called the design principles behind small talk by Dan Engles and the opening line is small talk is computer support for the creative spirit in everyone which had two big themes. One was a language of programming, the small talk language, and another was a language of interaction, overlapping windows, mice as pointing devices, panes, scroll bars, those were all things that uh were pioneered out of the user interface. Those things are kind of ordinary today. But Small Talk, the language, was built out of a very small number of primitives. There's really only three primitives in the language. Sending a message, assigning a variable, and returning a value. And that's really all that there is. And so, um, maybe, uh, towards the end we can talk about my current projects, one of which is to build another a new Small Talk from scratch, just because now that's in within reach for anybody.

But what what I found beautiful was that the language pushed its own mechanisms to the absolute limit. So everything is an object in small talk including numbers. You don't call a function that adds two integers. You send a message plus which is received by an integer and takes another object as a parameter. If that other object happens to be another integer, then you add them together.

</details>

**Speaker A**: 这种设计带来了很有趣的现象，比如它没有定义任何控制结构。所以，像 `if-then`、`if-then-else` 这些，都不是语言的一部分。它们是库的一部分，因为你可以向 `true` 发送 `if true` 消息并带上一个闭包，它就会求值执行那个闭包。如果你向 `false` 发送带闭包的 `if true` 消息，它就什么都不做，直接返回 null。所有的东西都是基于同一种底层基础构建出来的。

在 Smalltalk 里极少有特殊情况，这意味着有时你必须得聪明一点，才能弄明白像条件语句究竟是怎么工作的；但这也意味着，当需要你去构建抽象模型时，不会有一大堆特殊情况来阻碍你。这是一种不同的思维方式，尤其是当我们审视现代编程语言时，你会发现现在这些语言内置了太多的东西。即使我们去想后来的一些语言，比如 Kotlin、Swift 或者其他任何语言，它们都有像控制结构和保留字这样的东西。你为什么要保留字呢？多粗鲁啊，编程语言应该尽可能多地给我提供词汇。

<details>
<summary>Original English</summary>

**Speaker A**: This leads to interesting things like there are no control structures defined. So no if then if then else is not part of the language. It's part of the library because there's a you send the message if true with a closure to true and it evaluates the closure. You send the message if true to false with a closure and it does nothing. Just returns null. Everything is built out of the same kind of substrate.

There there's very few special cases in small talk which means that sometimes you have to get clever to understand things like h how does how do how do conditionals work but also when the time comes for you to build abstractions you you don't have a bunch of special cases getting in your way. It is a different way to think especially looking at the modern programming languages that have a you know the language comes with so many things built in whether even if we're thinking of like later languages like coughlin or swift or any of them they they have things like control structures and reserved words why would you reserve words how rude the programming language should give me as much vocabulary as possible

</details>

### 面向对象的狂热与泡沫

**Speaker B**: 但我确实注意到，对于 Smalltalk，用过它的人往往会变得非常非常充满热情，并且热爱使用它。在做调研时我了解到，曾有那么几年，在这段时间前后，它开始变得极受欢迎。你能告诉我为什么它会变得如此受欢迎，然后后来又发生了什么吗？它好像有点销声匿迹了。

<details>
<summary>Original English</summary>

**Speaker B**: but I do notice that with small talk the people who have used it just get really really passionate about it and love using it and I understand doing my research that there was a time around that time for a few years where it started to become a lot more popular. Can you tell me why it got more popular and then what happened? It seems to have kind of fizzled out.

</details>

**Speaker A**: 是的，说来话长。有些内情我也无从知晓。其中一部分原因是由于商业决策。那个时候“对象”（Objects）正处于风口浪尖。长期以来，我们一直在使用上一代语言——比如 COBOL、FORTRAN、Pascal——进行编程，并且已经习惯了这些语言所带来的种种限制。然后对象出现了，而对象将会改变一切。当时大家真的非常激动，你知道，对象能让程序员的生产力大幅提升，以至于我们甚至不需要那么多程序员了。而且事实上……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, longer story. Some of which I was not privy to. Some of which comes down to business decisions. Objects were were hopping. We'd been programming with the previous generation of languages cobalt forransc alascal for a long time and we were used to kind of the constraints that those provided and along came these objects and objects were going to change everything. People were really, really excited, but you know, objects were going to make programmers so much more productive that we wouldn't need nearly as many programmers. And in fact,

</details>

**Speaker B**: 真的吗。

<details>
<summary>Original English</summary>

**Speaker B**: >> really.

</details>

**Speaker A**: 是的。而且你知道，使用对象来编程实在太简单了，甚至普通人也能写出自己的程序。他们不再需要（去雇人）。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. And you know, it's so much easier to program with objects that ordinary people can write their own programs. They don't have to.

</details>

**Speaker B**: 我最近也听到了这种说法。[笑声]

<details>
<summary>Original English</summary>

**Speaker B**: >> I've heard this recently. [laughter]

</details>

**Speaker A**: 正是如此。但说真的，这就像是行业内大家都在谈论的事情，这成了一股风潮。使用对象或者 Smalltalk，就能花更少的钱、用更少的程序员，做更多的事情。

<details>
<summary>Original English</summary>

**Speaker A**: >> Exactly. But seriously, like this was what they were saying where like inside of the industry, this was a thing. Use objects or small talk and do more with do more with less programmers, cheaper the works.

</details>

**Speaker B**: 是啊。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah.

</details>

**Speaker A**: 而且在某种程度上这也是事实。我们会看到，大家不断加入。泰克公司（Tektronix）制造了一款工作站，在那之前甚至都没有工作站这回事，他们造了一款工作站，并将 Smalltalk 捆绑在里面开始销售。不同领域的技术人员，比如化学工程师、结构工程师或是水利工程师，会走进来，向我们展示他们用 Smalltalk 构建的系统。表面上看，它们太棒了，解决了问题，而且他们非常高兴，为自己的“心血结晶”感到非常自豪。

然而，如果你去看看底下的代码，那简直是一团糟，毫无可维护性可言。但尽管如此，人们能够亲手编写出他们想要的程序，这本身就是一个重大的进步了；因为在这之前，如果作为替代方案，在当时我们只能提供这种流程：我去写一份长达 1000 页的需求文档，然后等上 8 年，最后拿到手的还不是我想要的东西。

<details>
<summary>Original English</summary>

**Speaker A**: And and to a degree it was true. We would people would come in. So built a workstation, there weren't workstations. Tecttronics built a workstation and started to sell it with Small Talk bundled in it. and technical people but in different domains like chemical engineers or structural engineers or hydraulic engineers would come in and show us the systems they built with small talk and on the surface they looked fantastic the solve the and oh they were so happy so proud of their baby.

You look under the underneath though at the code and it was just a horrible unmaintainable mess. But the fact that people could program the programs that they wanted was a a significant step forward as opposed to I'm going to write a thousandpage requirements document and then wait 8 years and not get what I want which was the alternative that we were offering at the at the time.

</details>

**Speaker B**: 所以我们经历过这种扩张已经不是第一次了，因为如果把目光放回今天，类似的事情又在发生。那些不同领域、做梦都想不到能雇得起开发者的人，现在都在构建自己的程序。而正在上演的也是同样的戏码——也就是，如果你深入探究，如果你戴上软件工程的帽子去看看那一团乱麻的底层，里面充满了没有处理的边界情况（corner cases）。根本不可能去修改和演进。是这样吧。但是，就目前为止，Smalltalk 以及泰克公司销售预装 Smalltalk 机器的这个故事，确实让所有人都变得更有生产力了。显然它是物有所值的。听起来很棒。那后来怎么了？

<details>
<summary>Original English</summary>

**Speaker B**: So it's not the first time that we're expanding because again if we jump to today similar things are happening. People in different domains who could never dream of hiring a developer are now building their programs and the same thing is playing out which is if you look under the hood if you put your software engineering hat on and look under the hood of that mess. There's lots of corner cases that aren't covered. It's impossible to to modify and evolve. Yeah. But so far this story with small talk and Tektronics selling machines that come with small talk make everyone more productive. Clearly it pays for itself. That sounds great. But then what happened?

</details>

### 衰落的真正原因

**Speaker A**: 因为出现了更容易理解的替代方案。就比如，Smalltalk 的语法很有些“古怪”。这是一种中缀关键字语法。接着 C++ 出现了，它最初被称为“带类的 C”（C with objects）。而且它的语法看起来很熟悉，尽管它的设计理念和 Smalltalk 完全背道而驰。C++ 里面有很多机制，并且非常复杂。但就因为它容易上手，因为在那时有一个编译器——我们在 Smalltalk 中也是习惯于拥有编译器的。

在 Smalltalk 里，会有一些代码，你编辑它，然后就能立即运行新代码了。没有编译和链接的步骤，它自然而然地就在那里。而且如果你正处在中间状态，你知道，你可以在编辑一些文本时说：“这没达到我想要的效果”，然后按一下 Ctrl-C，你就能进入调试器，顺着调用栈往下找，找到没有按照你期望运行的代码，修改它，然后你可以继续，之后再回到编写状态。这就是所谓的“这是打算作为个人计算机的”那个级别。而那种掌控感的一部分，就在于你能看到所有的东西，也能修改所有的东西。

然而事实证明，如果你有 100 个人在同一个程序上工作，你就需要踩一脚刹车了。不能让所有人都同时以不兼容的方式更改所有的东西。那根本行不通。但如果是从“这是我的电脑，因为我理解它所以我感到有力量，我可以产生更多的想法并将之付诸执行来在这个世界上创造些事物”这个角度来说，它表现得极为出色。

<details>
<summary>Original English</summary>

**Speaker A**: There were alternatives that were easier to understand. So for example, small talk syntax is uh funky. It's this keyword infix syntax. Along comes C++ which was originally called C with objects. And the syntax looks familiar even though it's the design philosophy is entirely the opposite of small talk. There's lots of mechanisms and they're very complicated. But just the fact that it was approachable that you could there was a compiler because we were used to having compilers in small talk.

There'd be some code you'd edit it and now you're running with the new code. There's no compile and link step. It's of course it's just sitting right there. And if you're in the middle of, you know, you could be editing a some text and say, "This doesn't work the way I want and hit control C and you get a debugger and go down the stack and you find the code that's not doing what you want and you fix it and you continue on your way and then you're you're writing again." That was that was that level of this is intended to be a personal computer. And part of that that sense of ownership was that you could see everything and you could change everything.

Now it turns out if you have a hundred people working on the same program, you need to put the brakes on. Everybody can't be changing everything in incompatible ways at the same time. That just doesn't work. But in terms of this is my computer and I feel power because I understand it. I can have more ideas that I can then execute on to create things in the world. It worked great for that.

</details>

### 与 Ward Cunningham 的共事

**Speaker B**: 那么，在泰克工作期间，你与沃德·坎宁安（Ward Cunningham）共事，他后来成了世界上第一个 Wiki 的开发者。他产生了巨大的影响，或者是帮助创立了设计模式。他也参与了极限编程（Extreme Programming）。你能告诉我你们合作时是什么样的吗？你和他当时是如何开始涉足设计模式的，因为那时设计模式根本就不存在对吧，这是你们后来才发明的东西？

<details>
<summary>Original English</summary>

**Speaker B**: Now while at Tektronics you work with War Kunagum who would later become the developer of the first ever wiki. Uh he had a huge influence or he helped create design patterns. He also helped with extreme programming. Can you tell me about what it was like working with him and and how you and him started to get into design patterns which back then didn't exist right this was something you you would invent later

</details>

**Speaker A**: 当时我们需要开设关于 Smalltalk 的培训课程，沃德写过一些 Smalltalk 代码，我们彼此认识，实验室里大概有 60 到 80 人，所以我们看着脸熟。我通过自己的项目学到了很多关于 Smalltalk 的知识，我当时在开发 Prolog 的编程语言，因为逻辑编程在那个年代也是个大热门。所以我给 Prolog 实现过大概三种不同的虚拟机，还做了一些很漂亮的动画，用来展示 Prolog 的统一机制（unification mechanism）是如何运作的。

<details>
<summary>Original English</summary>

**Speaker A**: we needed to give training classes on small talk and Ward had written some small talk code we knew each other there were probably 60 people 80 people in the labs so we knew each other by side I had learned a bunch about small talk working on my own projects I was working on programming language for prologue because logic programming was also a big deal at that time. So I implemented I think three different virtual machines for prologue including some nice animations showing how prologue's unification mechanism worked.

</details>

**Speaker B**: 我想，对于那些不了解 Prolog 的人来说，要解释一下，这是一种声明式语言，是一种非常不同的思考方式。不，不，不。

<details>
<summary>Original English</summary>

**Speaker B**: And I guess for for those who don't know prologue is this declarative language is a very different way of thinking. No no no

</details>

<!-- chunk 4/16 -->

### Early Programming Experiences

**Speaker A**: 变量是……我想……

<details>
<summary>Original English</summary>

**Speaker A**: variables is I I think
</details>

**Speaker B**: 不，不，它有变量。“没有变量”的是 FP box。哦，这个 FP 不好意思，但它确实有一些奇怪的东西。我很久以前用过它。

<details>
<summary>Original English</summary>

**Speaker B**: no no it's got variables. No variables is FP box. Oh, this FP sorry, but it does have some some funky stuff. I I I used it a long time ago.
</details>

**Speaker A**: 挺有趣的。

<details>
<summary>Original English</summary>

**Speaker A**: It's fun.
</details>

**Speaker B**: 事实证明，用它来编写大型程序很困难，但这是一个很好的练习，因为你……那里没有像“做这个，然后做那个，再做那个”这样的控制流。它更像是一个定理证明器。所以，我当时在研究那个。Ward 为那个 Smalltalk 课程编写了这段示例代码，他说，“我只是想带你过一遍这段代码。”于是我在他旁边坐下，他向我展示了名为 plumbing 的代码，我提出了一些改进建议。我们一起讲授了那门课。在那门课上，我遇到了一些后来成为一生挚友的人。然后我们就进入了这样一种节奏，就是，“嗯，我想知道我们能不能让 Smalltalk 做这个”，因为对于计算机支持编程意味着什么的范畴当时正在爆炸式扩张。我们有了这种前所未有的高分辨率屏幕。我们有了这种动态语言，包括我们自己对它的实现，所以如果需要，我们可以对它进行调整，我们当时甚至不知道什么是可能的。

<details>
<summary>Original English</summary>

**Speaker B**: Turns out to be difficult to write big programs in, but it's it's it's a good exercise because you there there aren't control like do this thing, then do this thing, then do this thing. It's it's more like a theorem prover. So, I was working on that. Ward had built this example code for the small talk class and he said I just want to run you through this code. So I sat down next to him and he showed me the code for plumbing called plumbing and I suggested some some improvements. We gave the class together. I met some people who would later become lifelong friends in that class and then we just kind of fell into a rhythm of well, I wonder if we can make Small Talk do this because the universe of of what it meant for a computer to support programming was just exploding. We had the this high resolution screen which nobody had ever had before. we had this dynamic language uh including our own implementation of it so we could tweak it if we needed to and we just didn't know what was even possible.
</details>

**Speaker B**: 所以……起初，Ward 在底层技术方面一直是一个比我优秀得多的程序员。他在更高层次的设计上也有天赋，而且正如你在维基中看到的那样，他有一种天赋，能够挑选出强大的顶层目标，然后创造出实现该目标的东西。而我当时是个24岁的、态度很拽的毛头小子，他有一阵子不让我碰键盘。我只能看着他，后来我终于说，“呃，那些括号不匹配，你需要在这里加个句号。”尽管我只是在吸收，看着一位编程大师工作，但我实际上对他是有用的，只是我并没有真正主导事情。不过，最终我开始理解底层模式，然后一层层地往上建构。然后我会说，“为什么这个叫这个而不是那个？”拿出同义词词典查阅，为事物找到最合适的词，然后继续。最终，我开始提出一些他不能马上理解的建议。所以我会接管键盘一小会儿，写点像这样的东西。“哦，我懂了。我懂了。”然后他会把键盘拿回去。

<details>
<summary>Original English</summary>

**Speaker B**: So uh at first and Ward was always a much better programmer than I was in terms of low-level technique. He also had a gift for design at a higher level and a gift as you see in the wiki of uh picking powerful top level goals and then making something that does that. But I was this 24 year old punk with attitude and he he didn't let me touch the keyboard for a while. I could watch him and then eventually I was like h those parentheses don't balance you need a period here and I was actually being useful to him even though and I was absorbing watching a master programmer at work but I wasn't really driving stuff eventually though I started you know understanding the low-level patterns and then building up to the next level and the next and then I would say why is this called this and not that pull out a thesaurus and look it up and find just the right word for things and then continue. And eventually I started making suggestions that he wouldn't understand right away. And so I would take the keyboard for a little while say something like this. Oh, I get it. I get it. And then he'd take the keyboard back.
</details>

### Evolving a Programming Style

**Speaker B**: 在几个月的过程中，我们发展出了一种键盘在两人之间来回切换的编程风格，我们会在多个层面上进行交流。你知道，我们会讨论：这段代码在这里，它为什么不工作？这到底是不是我们应该着手解决的问题？为了让这件事变得简单，我们需要什么编程工具？设计应该是什么样的才能让整个系统运作良好？从哲学上讲，我们到底应不应该做这件事？在实际编程中，我们会在所有这些层次之间来回跳跃。

<details>
<summary>Original English</summary>

**Speaker B**: Over the course of a few months, we developed both a programming style where the keyboard was going back and forth where we were talking at multiple levels. You know, we talk about here's this code, why isn't it working? Is this the thing we should be working on at all? What programming tools would we need for this to be easy? What should the design be so this whole thing should work well? Should we even be doing this at all philosophically? We would bounce between all those levels in the in the active programming.
</details>

**Speaker B**: 我们有一个每周的节奏，周一早上我们会喝杯咖啡，讨论一下待办事项清单，因为从那些对话中我们会得出结论：“我希望我们有一个能做某件事的东西。”我们会讨论这个，然后说，“好吧，那我们就开始吧，看看我们能走多远。”然后一遍又一遍地，周二、周三，我们会对正在进行的工作取得大量进展。周四，我们会进行演示并加以改进。而周五，我们会写一份技术报告。所以，在六到十二个月的紧张合作中，我们写了一整系列的技术报告。即使其中某一周失败了，你知道，我们仍然会在周一、周二、周三喝咖啡。“啊，这个没起作用。”我们会知道它为什么没起作用，以及为了以后让那件事变得简单我们需要什么。这就进入了下周一咖啡时间的待办事项里。

<details>
<summary>Original English</summary>

**Speaker B**: And we had a weekly cadence where Monday morning we'd have a coffee and we talk about of the list of things because we would then out of those conversations we'd come I wish we had a thing that did a thing. We would talk about that and then we'd say okay well let's go down and see how far we can get. And over and over, Tuesday, Wednesday, we would make a bunch of progress on what we were working on. Thursday, we'd be giving demos and refining it. And Friday, we'd write a tech report. So, there's this whole string of tech reports that we wrote over the course of maybe 6 or 12 months of really working together intensely. Even if one of those weeks failed, you know, we'd we'd have our coffee Monday, Tuesday, Wednesday. ah, this didn't work. We would know why it didn't work and what it was that we needed in order for that thing to be easy in the future. And that goes into the hopper for the next Monday's coffee.
</details>

**Speaker B**: 于是，我们开发了各种各样的编程工具和应用程序，还有一些基础性的东西。我们有一个叫 Hot Draw 的图形编辑器，因为我们有了这种图形界面，而大家很长一段时间以来都习惯了文本界面，但现在我们有了高速图形。天哪，我们能用它做些什么呢？所以我们一直在做图形界面，但这很难做。

<details>
<summary>Original English</summary>

**Speaker B**: So, we developed a wide range we of programming tools and applications, some foundational stuff. So, we had a uh graphics editor called Hot Draw because we we had this graphical interface and everybody had been used to text interfaces for so long, but now we had high-speed graphics. Oh my goodness. What can we do with this? So, we kept making graphical interfaces, but it was hard to make graphical interfaces.
</details>

**Speaker A**: 是的。我有一张早期 Draw 的照片。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I I have a photo of of early draw.
</details>

**Speaker A**: 是的，绝对有。当我看到 Hot Draw，这些方框和箭头，它们确实让我在后来想到了像 UML 和许多其他的……不仅是完全一样的想法，而是可视化的想法。当然，后来我想现在人们已经不用 UML 了，但你依然会走到白板前，画出方框和箭头以及它们是如何连接的。听起来你是在 87 年左右做这件事的。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, absolutely. And and this reminds me when I look at hot draw this, you know, like these boxes and arrows, they do remind me later of things like UML and a bunch of just the not not the exact ideas, but but visualizing and of course later I think these days people don't use UML, but you still you just go to the whiteboard and you draw out boxes and arrows and how they connect. Sounds like so you did this back in in ' 87 or something like that.
</details>

### The Magic of Hot Draw

**Speaker B**: 没错。因为我们拥有当时堪称高性能的图形原语，Hot Draw 中神奇的时刻是，我们画了一系列几乎重叠的矩形。我们隔一个选中一个，点击它，然后开始来回移动它。因为我们大概能实现 10 赫兹的动画，它非常流畅，你就能看到一半的矩形，你知道的，在另一半矩形的后面移动，那种感觉简直是，“太酷了”。我们对此感到非常兴奋。

<details>
<summary>Original English</summary>

**Speaker B**: Correct. And because we had uh high performance for the time graphics primitives, the magic moment out of hot draw was we drew a series of rectangles kind of on top of each other. We selected every other one. We clicked on it and we started to move it back and forth and you could and because we could we could do maybe 10 hertz animation. It was it was smooth and you could just see half of the rectangles, you know, kind of moving behind the other half and it was just this is so hot. We were just really excited about it.
</details>

**Speaker A**: 哦，那就是你叫它 Hot Draw 的原因。这就是它的名字，因为那正是看到这种流畅动画时的反应。在此之前，编写那种流畅的动画是件定制化的事，需要投入大量工作。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, that that's that's why that's why you called it hot draw. That was the name because that was the reaction to being able to see this smooth animation. And before that, writing that kind of smooth animation was a bespoke thing and took a lot of work.
</details>

**Speaker B**: 借助于此，你只需要对图形（Figure）进行子类化，然后你就拥有了能在这个 2.5 维世界里运作的东西，一切就这么开始了。不过，这些图形是为了表示界面中的某些东西。它不仅仅是一个矩形。它可能是一个处理器，一个生成器，或者别的什么。然后你点击它，在这个图形上就会出现这些手柄（Handles），每个手柄代表了某种操作状态的方式，不光是图形层面的状态，它背后同样被赋予了意义。所以你可能有一个手柄用来升高或降低温度，另一个手柄用来改变压力，或者你当时正在研究的任何领域参数。

<details>
<summary>Original English</summary>

**Speaker B**: And with this, you subclass figure and now you have something that works in this 2 and 1 halfd world and away you go. Those figures though were meant to represent something in the interface. It wasn't just a rectangle. It was a processor, it was a generator, or it was a whatever. And then you click on it and you get these handles on the figure which each of which represents some way to manipulate the state, not just of the graphic thing, but again of there was intended to be meaning behind it. So you'd have a handle that would raise and lower the temperature and another handle that would change the pressure or whatever whatever domain you were working in.
</details>

**Speaker B**: 然后你就有了一个方框加箭头的模型。所以你可以建立事物之间的连接，而这些连接同样带有语义上的意义，并且会跟随图形移动。实际上，“图形 (figure)”、“手柄 (handle)”、“绘图 (drawing)” 这些词是 Ward 想出来的。我想出的词就比较平淡，比如“绘图对象 (drawing object)”、“绘图手柄 (drawing handle)”。我一直没有找到好词来形容它。这时候同义词词典就派上用场了：Ward 会想，“好吧，这就好比书中的插图 (figures)”。你知道，我们在这里用了一个类比。对于我们正在做的事情有一个隐喻。但是在计算机世界里，你可以有无数的图形。

<details>
<summary>Original English</summary>

**Speaker B**: And then you had it was a boxes and arrows uh model. So you'd have connections between things and the connections again were intended to be semantic but would follow the figures around. And actually the the words figure handle drawing uh Ward came up with those. Mine were something pedestrian drawing object drawing handle. I I I didn't have good words for it. And this was where the thesaurus came in was Ward would think about okay this is like figures in a book. You know we had an analogy there. there there was a metaphor to what we were doing. But in the computer world, you can you can have figures and figures and figures.
</details>

**Speaker A**: 我理解得对吗？你其实有一本实体同义词词典，就是一本书？

<details>
<summary>Original English</summary>

**Speaker A**: And do I understand that you actually had a physical thesaurus like a book?
</details>

**Speaker B**: 是的。是的。一本真正印满文字的书。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah. An actual book with words in it.
</details>

**Speaker A**: 作为一名程序员，你竟然真的会经常翻阅这本满是单词的书，去寻找更合适的词汇。

<details>
<summary>Original English</summary>

**Speaker A**: You would actually as a programmer reach for this book with words and open up to find better words all the time.
</details>

**Speaker A**: 只有你这么做，还是你认识的程序员普遍都有一本同义词词典？

<details>
<summary>Original English</summary>

**Speaker A**: Was this just you doing it or did programmers in general have like people that you knew that they also have the satarist?
</details>

### The Value of Vocabulary in Programming

**Speaker B**: 在这个问题上，我们走到了强迫症这一端的极致。当然，也有其他人为了找到恰当的词而绞尽脑汁。但这仅仅是……这恰恰提醒了我，编程不仅仅是写代码而已。你需要各种技能，例如，如果你博览群书，你可能就能写出更具表现力的程序。或者如果你书读得不多，手头有一本同义词词典——当然你可以在网上查——但我认为，通过翻开书本、浏览并阅读大量其他词汇，你的词汇量会开始增长。因此这会让你成为一个更好的程序员，或者说成为一个能写出更易于理解或维护的代码的人。程序的目标之一是向其他人类，现在还包括向模型传达意图，而后者是一个更加开放的问题。我们更了解如何与其他人交流，无论我们是否运用了这种理解。但我们完全不知道如何有效地与模型交流，人们正在尝试各种各样的方法，这很好，因为这就是你该做的。

<details>
<summary>Original English</summary>

**Speaker B**: We were on the far end of the obsessive scale for this. There were other people certainly who were fighting for the right words. But this just this just reminds me of how programming is is just more than just you know like writing code. how you need the skills of for example if you are well read you can probably write more expressive programs or if you're not well read having a thesaurus of of course you could do it online but I assume that by opening up the book and looking through and reading a lot of other you know words your vocabulary was will start to grow there therefore making you a better programmer or someone who can write a lot more understandable or maintainable part of the goal of programs is to communicate intent to other human beings and now to models as well which which is a much more open-ended problem. We understand a lot more about how to communicate to other human beings whether we apply that understanding or not. We don't understand at all how to communicate effectively to models and people are trying out all kinds of things which is that's great. That's what you do.
</details>

<!-- chunk 5/16 -->

### 设计模式的起源与物理建筑的启发

**Speaker A**: 是的。后来 Ward 继续发展，他非常深入地参与了设计模式的研究。我现在完全能通过 HotDraw 看到，你知道，后来四人帮（Gang of Four）的设计模式中你能看到的方框和箭头，我感觉这和能在显示器上可视化对象有一些相似之处。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And then later Ward went on and he got very much involved with design patterns. I can all now see with hot draw how you know the design patterns in the gang of four later you see boxes and arrows how I see some resemblance on being able to visualize objects on a monitor.

</details>

**Speaker B**: 是的，所有的碎片都在为我们拼凑到一起。关于模式的工作，我那时对俄勒冈大学（University of Oregon）的克里斯托弗·亚历山大（Christopher Alexander）产生了兴趣。我买不起《建筑的永恒之道》（The Timeless Way of Building）这本书，所以我是分好几次在书店里站着读完的，而 Ward 也接触过克里斯托弗·亚历山大和模式。亚历山大想建造具有某种精神的建筑。他用有点神秘的词汇来谈论它，但这没关系。他假设如果人们自己决定建筑的设计，这种精神就会存在，而否则就不存在。当建筑师说：“哦，好吧，你告诉我你需要什么样的建筑，然后我会调整自己去梦想你完美的空间，接着我会告诉你，我来给你提供解决方案。”他希望的工作方式是赋予人们在约束条件下做出决定的能力。就像我设计房子一样，我可能会设计出会塌的屋顶、不匹配的墙壁等等，因为我不懂。所以，我需要约束，但我更了解我自己的生活。因此，我应该是那个做决定的人，比如，哦，家庭聚餐非常重要。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, all of the pieces were working together for us. Um the patterns work I had become interested in Christopher Alexander at the University of Oregon. I couldn't afford the timeless way of building. So I read it standing up in the bookstore uh over the course of several visits and Ward had also been exposed to Christopher Alexander and patterns. Alexander wanted to build wanted buildings with a certain spirit to them. He talks about it in kind of mystical terms, but that's okay. And he hypothesized that if people made their own decisions about the design of buildings that this spirit would exist in a way that didn't. When the architect would say, "Oh, well, you know, tell me what you need in a building and then I will program myself to dream of your perfect space and then I'll tell you I'll bring to you the solution." The way he wanted to work was to empower people to make decisions within constraints. Like me designing a house, I'm going to have roofs that fall down and walls that don't match and whatever cuz I don't know. So, I need constraints, but I know more about my life. So, I should be the one making the decisions about, oh, family dinners are really important.

</details>

**Speaker A**: 哦，所以这是在建筑领域，比如严格意义上的物理建筑。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, so this is in the domain of architecture like strictly physical buildings.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**: 哇。所以你从这个领域获得了很大的启发，尽管软件很大程度上是虚拟的，它存在于我们的头脑中，或者在计算机里。

<details>
<summary>Original English</summary>

**Speaker A**: Wow. So you got a lot of inspiration from this domain even though software is very much a virtual it's in our head right and or in the computer right.

</details>

### 将模式应用于图形用户界面设计

**Speaker B**: 所以模式就是约束。你不能随便做决定。你必须在特定的时间，基于你已经做出的决定所带来的约束来做特定的决定，而这又会为你下一步的决定创造约束。我们希望为程序的用户提供这种体验，将 Smalltalk 个人电脑的理念提升到一个新的水平。当时我们正在为泰克（Tektronix）一个进展不顺的项目提供咨询。一些程序员正在为一些测试工程师编写软件，但项目进行得不好。于是 Ward 提出了最初的一套模式，供我们在设计用户界面时使用。你要知道，当时图形界面还是个全新的事物，没人知道该怎么做。就像在音乐学院里，各种疯狂的想法层出不穷。我们了解过音乐记谱法的演变，在记谱法刚出现时——在此之前完全是口耳相传的传统——有些史上最复杂的音乐就是在 1200 年或 1300 年，即记谱法刚被发明后写出来的，因为没人知道限制在哪里。然后后来他们安定下来了。比如，好吧，四声部经文歌，那很好。我们不需要让 60 种不同的乐器在同一时间做 60 件不同的事情，仅仅因为我们能做到。嗯，这些用户界面的情况也类似。没人知道该如何组织它们。所以我们提供了 Ward 提出的这套最初的模式，我们讨论了克里斯托弗·亚历山大和模式，并且我在波特兰的 Powell's 书店偶然发现了一本《形式综合论》（Notes on the Synthesis of Form），便如饥似渴地读完了，这可以说是模式的理论基础。我们把这些模式交给了测试工程师，并说好吧，我们重新开始。使用这些模式将你们的流程分解成带有窗格的窗口。我们很小心地只允许他们做我们知道自己能实现的事情。所以他们不可能想出天马行空的东西。窗格必须是列表、文本或波形图。波形图比较特殊，但没关系，我们可以做到。你在这个测试过程中需要做的每一个任务都会有自己的窗口，所以大概有四五种不同的模式，最终他们设计出了一个完全可以实现的界面，而且他们觉得这个界面是属于他们的。然后 Smalltalk 程序员会看着它说，好吧，我该怎么实现这个？我该怎么实现那个？所以这是我们在模式领域的初次尝试。人们对这种责任转移非常较真。他们总想：“我，我是界面的设计师，我在这上面投入了大量心血。我想问你一堆问题，然后我要自己思考，接着我会把解决方案带给你，然后你会感谢我，拍拍我的头。”当然，那是不可能发生的。你对别人问题的理解是受限的，因为你并没有身处其中。你没有同样的切身利益（skin in the game）。如果你不是半导体测试工程师，你的切身利益就没有那些真正做这个的人多，因为在你离开很久之后，他们还得继续使用这个界面。

<details>
<summary>Original English</summary>

**Speaker B**: So the patterns are the constraints. You can't just make any decision. You make particular decisions at particular times based on the constraints that come from the decisions you've already made and that creates constraints for the next decisions that you make. We wanted that for the users of programs taking this small talk personal computer ethos to the next level. And so we were consulting on a project that wasn't going well at Tektronics. some programmers were writing software for some test engineers and it just wasn't going well. So Ward came up with the initial set of patterns that we would use for designing a user interface. Again, graphical interfaces were brand new. Nobody knew what to do. There were all kinds of crazy things coming out in music school. We learned about the evolution of musical notation. And when musical notation first came out, before then it was entirely an oral tradition, then musical notation was invented. And some of the most complicated music ever written was written in like 1200 or 1300, right after musical notation had been invented because nobody knew what the limits were. And then then they settled down. It's like, okay, a four-part motet, that's fine. and we don't need to have 60 different instruments doing 60 different things all at the same time just cuz we can. Well, it was the same kind of way with these user interfaces. Nobody knew how to organize them. So we gave this initial set of patterns that Ward had come up with and we'd talked about Christopher Alexander and patterns and I ran across a copy of notes on the synthesis of form at Powell's books in Portland and devoured that which is kind of the theoretical underpinning of patterns. We handed the patterns to the test engineers and said okay we're just going to start over. use these patterns to break your process down into windows with pains. And we were careful to only allow them to do things that we knew that we could implement. So they couldn't come up with anything. The pains had to be lists or text or waveforms. The waveforms were special, but that's okay. We could do that. Each task that you had to do in this testing process would have its own window and so there was you know a four or five different patterns and they came up with an interface that was eminently implementable and they felt like they owned it and then the small talk programmers would look at that and go okay well how do I implement this how do I implement that so that was our first foray into patterns. People get really fussed about this transfer of responsibility. They want to think I am the designer of interfaces and I worked hard at this and I want to ask you a bunch of questions and then I want to cogitate on that and then I'm going to bring you the solution and then you'll thank me and pat me on the head. Of course, that doesn't happen. Your understanding of somebody else's problem is bounded because you're not in the middle of it. You don't have the same skin in the game. If you're not semiconductor test engineer, you don't have as much skin in the game as somebody who is because they're going to have to be using this interface for a long time after you're gone.

</details>

### 海鸥架构师与切身利益

**Speaker A**: 是的。团队里还有一种“走穴架构师”（flyby architect）的概念，你知道，就是这种非常有资历的人，构建过很多东西，而团队正在挣扎。他们会把这人请过来。这个人来了，提些建议，然后就飞走了。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. There's also this concept of the flyby architect on teams who, you know, this very senior person has built a lot of stuff and the team is struggling. They call them and they call him or her in. This person comes, does some suggestions and kind of flies off.

</details>

**Speaker B**: 这就是海鸥。

<details>
<summary>Original English</summary>

**Speaker B**: This is a seagull.

</details>

**Speaker A**: 海鸥。海鸥。因为它应该……

<details>
<summary>Original English</summary>

**Speaker A**: The seagull. The seagull. Because it should

</details>

**Speaker B**: 你飞进来，制造一堆噪音，到处拉屎，然后飞走。是的。

<details>
<summary>Original English</summary>

**Speaker B**: You fly in, you make a bunch of noise, you crap all over everything, and then you fly out. Yeah.

</details>

**Speaker A**: 是的。你要有切身利益（skin in the game）。是的。这很有意思，因为任何在一个有一定规模或历史的团队里工作过的人，都会看到这种事发生。那个人的技术能力有多高并不重要。可能会有少数例外，但通常如果你没有切身利益，你做出的决定就会不同。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And you drop skin in the game. Yeah. And it's interesting because we've anyone who's worked in teams of a certain size or certain tenure, you see it happen. And it doesn't really matter how highly skilled that person is. There might be a few exceptions, but generally if you don't have skin in the game, you just make different decisions.

</details>

### 离开 Tektronix 加入 Apple 

**Speaker A**: 泰克之后，你在苹果（Apple）工作过。我最近才了解到你的这段经历。你是怎么进苹果的？那是在 1987 年。从我的研究来看，那是个非常激动人心的时期。你是怎么进去的？你在那里做什么？

<details>
<summary>Original English</summary>

**Speaker A**: And then after Tektronics, you worked at Apple. I only realized this about you. What how did you get into Apple? This was in 1987. It's a very exciting time from my research. How did you get in there? What did you do there?

</details>

**Speaker B**: 那时候，Smalltalk 就像火箭一样一飞冲天。施乐（Xerox）开发了 Smalltalk。它把这项技术交给了大约四家公司，想看看你们是否也能实现它，或者这只是一些特殊的东西。有惠普（HP）、苹果（Apple）、泰克（Tektronix），我忘了第四家是哪家。惠普确实没用它做什么，但苹果和泰克把它发扬光大了。所以苹果有了自己实现的 Smalltalk，他们不想在销售意义上将其商业化，而是想在另一种意义上将其商业化：拥有某种可以在 Mac 上使用的东西，那正是在 Mac 刚问世之后。所以我知道那个项目。我在泰克有点膨胀了。我学到了很多。你知道，当你的成长速度快于组织能认知到的你的成长速度时，会产生一种压迫感，但同时你的成长也没有你自己想象的那么快。最终，别人看待你的方式和你自己看待自己的方式之间会出现差距，而你真实的水平就在这两者之间的某个位置。如果这些差距变得太大，你就必须离开了。所以我准备好继续前进了。因此，我联系了苹果，在这个 Smalltalk 项目上工作了大约一年，结果这个项目无疾而终，因为它确实没有意义。Smalltalk 可以在相当小的内存占用下运行，但苹果真正需要的开发者工具只有 C 编译器和 Pascal 编译器。

<details>
<summary>Original English</summary>

**Speaker B**: So, Small Talk was going up like a rocket at that time. Xerox had developed Small Talk. It handed it to four I think companies to see can you also implement it or is this something special. So HP, Apple, Tektronics and blanking on the fourth one. HP really didn't do anything with it but Apple and Tektronics ran with it. So Apple had its own implementation of Small Talk and they wanted to not commercialize it in the sense of selling it, but commercialize it in the sense of having something that this was right after the Mac had come out, something that you could use on a Mac. And so I knew about that project. It was getting too big for my britches at Tektronics. I learned a lot. You know, there's a thing there's this kind of compression that happens when you're growing faster than the organization can recognize that you're growing, but also you're not growing as fast as you think you're growing. And eventually that gap between how people see you and how you see yourself and then somewhere in between is how you really are. Those if those gaps get too wide, you just have to move. So, I was ready to move on. So, I contacted Apple and I worked for about a year on the Small Talk project, which ended up going nowhere cuz it really didn't make sense. Small Talk could work in quite a small memory footprint, but the only developer tools Apple really needed was a C compiler, Pascal compiler,

</details>

**Speaker A**: 因为他们主要用 C 语言开发软件。那是他们构建软件的基础。大家都是这么做的。还有繁荣的第三方市场提供其他开发者工具。但 Smalltalk 真正无法为任何人做什么。也许对学生有点用，但它推动不了苹果的销量。买苹果电脑的人通常不想用 Smalltalk。对吧。

<details>
<summary>Original English</summary>

**Speaker A**: because that's what they built their software on mostly C. That's what they built their software on. That's what everybody else did. There was a thriving third market for other developer tools. But the small talk wasn't going to do really do anything for anybody. Maybe school kids or something, but it wasn't driving Apple sales. People who bought Apple computers typically didn't want to do small talk. Right.

</details>

**Speaker B**: 完全正确。

<details>
<summary>Original English</summary>

**Speaker B**: Correct.

</details>

**Speaker A**: 完全正确。所以我们谈到了 Smalltalk 的衰退。我感觉到在这个时候，随着个人电脑开始普及，它似乎只是维持在小众领域，对吧。

<details>
<summary>Original English</summary>

**Speaker A**: Correct. So we talked about the decline of small talk. I'm sensing around this time it's if you know like as personal computers started spreading it seems like it just remained the niche right

</details>

**Speaker B**: 不，当时它非常强劲，发展得很快。和前一年相比，有很多很多人在使用它。有一家名为 ParcPlace 的公司从施乐独立出来，作为大件商品在销售 Smalltalk……

<details>
<summary>Original English</summary>

**Speaker B**: no it was quite strong at that time it was growing fast um lots of people like relative to the previous year were using it a company had spun out of Xerox called Park Place which was selling small as a big ticket item for

</details>

<!-- chunk 6/16 -->

### Apple 经历与 Playground 项目

**Speaker A**: ……开发者们，而且那还是在有开源软件出现之前。所以你能靠一种语言的实现来赚钱的想法，当时有很多人都在做这种事，这也是出于同样的套路。

<details>
<summary>Original English</summary>

**Speaker A**:  developers and this is before there was open-source out there. So the idea that you could set you could charge money for a language implementation was a lots of people were doing that kind of thing and this was running out of that same kind of playbook.

</details>

**Speaker B**: 好的。所以当时还在这么做。只是这不适合苹果（Apple）的客户群。

<details>
<summary>Original English</summary>

**Speaker B**: >> Okay. So it was still doing it. It would just didn't make sense for Apple's customer base.

</details>

**Speaker A**: 正确。

<details>
<summary>Original English</summary>

**Speaker A**: >> Correct.

</details>

**Speaker B**: 以及他们的硬件。

<details>
<summary>Original English</summary>

**Speaker B**: >> And and their hardware.

</details>

**Speaker A**: 是的。不过同时，当时有一大批前施乐（Xerox）的人来到了苹果。所以我的朋友拉里·特斯勒（Larry Tesler）也在那儿，我说的“朋友”指的是我非常尊敬的宿敌。有时候你知道，总有些人只会让你毛骨悚然，而拉里·特斯勒对我来说就是这样的人，我甚至不知道他是否也有同感。他几年前去世了，所以我再也没有机会和他说话了，不过我确实和他说过话，你知道，我们后来也会互相问候。总之，他当时是苹果高级技术小组的主管。艾伦·凯（Alan K）也去了苹果，当时正在开发一种面向儿童的编程语言，另一种叫作 Playground 的面向儿童的编程语言。丹·英格尔斯（Dan Engles）也在那儿。所以，很多施乐的人当时都在苹果，我听说了艾伦·凯的项目，觉得那就是我的梦想。《Byte》杂志曾登过一篇关于 Smalltalk 的文章。我读过关于 Smalltalk 开发的故事。这个项目大概在 71 年就开始了，直到 1980 年他们才公开发布任何东西。仅仅是想象在那种环境下工作，对我来说简直就像天堂。于是，我转到了艾伦·凯的 Playground 项目。然而，我的工作效率低得可怕。呃，结果我被那份工作解雇了。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. Also though at the same time a bunch of the ex Xerox people had come to Apple. So my friend Larry Tesler was there and by friend I mean bitter enemy who I respected a lot. Sometimes you know you there are people who just raised the hair on the back of your neck and Larry Tesler was one of those to me and I don't know if even the feeling was reciprocated. He passed a few years ago, but so I never got a chance to talk to him, but I talked to him, you know, we we would check in afterwards. Anyway, he was the head of the advanced technology group at Apple at that time. Alan K had moved to Apple and was working on a programming language for kids, another programming language for kids called Playground. Dan Dan Engles was there. So, a lot of the Xerox folks were were at Apple and I heard about Alen K's project and thought that was a dream of mine. Bite magazine had an article on small talk. I read about the development of Small Talk. The project started in like 71 and it was 1980 before they released anything at all publicly. And just imagining working in that environment just seemed like heaven to me. So, I moved to the Alan K's playground project. Now, I was horribly ineffective. Uh, ended up getting fired from that job.

</details>

**Speaker B**: 不会吧。

<details>
<summary>Original English</summary>

**Speaker B**: >> No way.

</details>

**Speaker A**: 对。哦，真的。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. Oh, sure.

</details>

**Speaker B**: 作为一个程序员，你居然效率低下。发生什么事了？

<details>
<summary>Original English</summary>

**Speaker B**: >> As as a programmer, you being inefficient. What happened?

</details>

**Speaker A**: 我想做我自己的事。那时我仍然，你知道，我仍然处于那种朋克模式，我会听别人的想法，然后我会说：“不，我不这么认为。我有一个更好的主意。” 如果你是一个人工作，那没问题。但如果你在一个团队里工作，那就不行了。所以，呃，呃，事情到了紧要关头。我是 OOPS 会议的项目主席，我们早些时候可能应该提到这个。嗯，有个这个会议，它是当时最火的会议，所有有头有脸的人物都会去那里，而且它的发展非常快，我也参与其中，算是误打误撞进去了吧。但是在 89 年，我是 OOPS，对，OOPSLA 的项目主席，我花了一个月的时间只顾着读论文，而忽略了我在 Playground 项目中的职责，这差不多是压死骆驼的最后一根稻草。“好吧，你完全没在帮我们，所以你需要离开了。” 然后会议召开了，而我的第二个孩子正忙着‘不出生’。所以我甚至都没能去参加会议，但我之前听说过 Playground 项目。所以我转去了那个 Playground 项目，并且做了一点工作来帮助构建这种儿童编程语言。那是超越面向对象编程的下一个新事物。你今天可能会把它称作响应式编程（reactive programming）。所以你不能发送消息。你只能抛出某个条件，而其他某个对象会一直在等待这个条件。所以这有点像发布-订阅（pub sub）模式，但那是当时唯一的控制机制。

<details>
<summary>Original English</summary>

**Speaker A**: >> I wanted to do my own thing. And this was still, you know, I'm still in this punk mode where I'd listen to somebody else's ideas and I go, "Nah, I don't think so. I have a better idea." And if you're working by yourself, that's okay. But if you're working in a team, that's not okay. So, uh, uh, the it came to a head. I was the program chair for oops conference, which we probably should have mentioned earlier. Um there was this conference and it was the hottest conference and everybody who was ever anybody was there and it was growing fast and I was involved in it kind kind of stumbled into it but I was in ' 89 I was the program chair for oops right for oopsla and I spent a month just reading papers while uh ignoring my duties to the playground project and that was kind of the final straw. okay, you're you're not helping us, so you you need to move on. And then the conference happened and my second child was busy not being born. So I didn't even get to attend the conference, but I had heard about the playground project. So I moved to the the playground project and and did a little bit to help build this programming language for kids. That was the next thing beyond object-oriented programming. You would you would call it today you'd call it reactive programming. So you didn't you couldn't send a message. You could only raise some condition that some other object would would be waiting on. So it's like pub sub but that was the only control mechanism.

</details>

### CRC 卡片与面向对象设计

**Speaker B**: 然后我想问你一下，大概也是在这个时候出现的 CRC 卡片。什么是 CRC 卡片？我知道它们代表“类-职责-协作者（class responsibility collaborator）”卡片，但它们到底是什么？你是怎么想出这个主意的？

<details>
<summary>Original English</summary>

**Speaker B**: And then I wanted to ask you about this this was around this time CRC cards. What are CRC cards? I know they stand for class responsibility collaborator cards but what were they and how did you come up with them?

</details>

**Speaker A**: 你看着那些命令式程序，你会有一个流程图，它能准确地，哪怕有点啰嗦地，表示出一个命令式程序中的控制流。现在我们有了这些对象，并且你会发送具有多态性的消息。所以你在发送消息的时候，你并不完全知道到底会调用哪段代码。人们就会觉得，好吧，你该怎么去将其可视化、内在化呢？对于我来说，我嗯……我有动觉联觉（kinesesthetic synesthesia）。所以，如果我看着某段代码，我能在身体里感觉到它。我能在身体里感觉到：它想往这个方向走。它……

<details>
<summary>Original English</summary>

**Speaker A**: You have this these imperative programs and you have a flowchart which represents accurately if kind of verbosely the control flow in an imperative program. Now we have these objects and you send messages which are polymorphic. So you don't know exactly what code's going to be invoked when you send a message. And people were like, well, how do you even visualize, internalize? For me, I'm um I have kinesesthetic synesthesia. So, I can feel in my body if I'm looking at some code, I can feel in my body. It wants to go this way. It's

</details>

**Speaker B**: 是啊。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 这其实，你知道，我，我不知道我是否见过其他人会用同样的方式来描述他们编程时的体验，但总之就是这样。你如何才能获得一种直觉，无论你是怎么在内心里去理解，关于在这个程序里正在发生什么，在这个程序里你不能只是说我们执行这行代码，然后我们执行那行代码，因为我们一旦发送了一条消息，我们不知道会发生什么。所以沃德（Ward）想出了一个主意，把这些东西写在卡片上，索引卡片上，写出这里正在发生的事情。因为我们一直都是这么说话的。所以你看，我们有一个……我们有一个矩形，它要求渲染器（renderer）去做这个事情，然后这个进入到管道（pipeline）中，然后吧啦吧啦。所以我们说话的时候经常会用到手势。所以他说，"好吧，我们为什么不把这些东西写在卡片上呢？索引卡片。" 所以面向对象编程里的一个巨大挑战就是划分职责，因为你正在将计算移动到数据所在的地方。说 "嗯，这个对象做这个，那个对象做那个" 是一个非常关键的决定，因为你想，你希望计算靠近数据，这样它们之间的耦合度就会更低。这是一个我觉得，嗯，有点被淹没在噪音中的教训。这是设计面向对象程序中最基本的设计步骤，而且我，我认为我坚持这一点。所以，所以，让数据靠近它被使用的地方，也就是计算将要发生的地方。

<details>
<summary>Original English</summary>

**Speaker A**: which is, you know, I've I don't know if I've met anybody else who describes their experience of programming in the same kind of way, but but there we go. How do you get a sense of however you internalize this of what's going on in this program where you you can't just say we execute this line and then we execute that line because as soon as we send a message, we don't know what's going to happen. So Ward came up with the idea to write these things down on cards, index cards, here's what's going on. Because we would we would talk this way all the time. So you know, we've got a we have a rectangle and it asks the renderer to do the thing and then that goes into the pipeline which dah. So we would talk with our hands a lot. So he said, "Well, why don't we write these things down on cards, index cards?" So a a big challenge in object-oriented programming is dividing the responsibilities because you're moving the computation to where the data is. Saying, "Well, this object does this and that object does that is a really critical decision because you want to you want the computation near to the data so that there's less coupling between them." which is a lesson that I I think uh kind of got lost in the noise. That's the fundamental design move in ob in designing object-oriented programs and I I think I stand behind that. So so have have the data be close to where it's used where the computation will happen

</details>

**Speaker B**: >> 呃，反了。

<details>
<summary>Original English</summary>

**Speaker B**: >> uh backwards

</details>

**Speaker A**: >> 反了。

<details>
<summary>Original English</summary>

**Speaker A**: >> backwards

</details>

**Speaker B**: >> 是让，让计算移动到数据已经存在的地方。

<details>
<summary>Original English</summary>

**Speaker B**: >> have have the computation move to where the data already lives

</details>

**Speaker A**: >> 让计算移动到数据所在的地方。所以，比如，如果你有一个包含大量数据的富对象，你希望计算能够移动到那里。所以你希望能够像调用对象那样，只是去获取数据并完成它们需要进行的任何计算。

<details>
<summary>Original English</summary>

**Speaker A**: >> have the computation move to where the data is. So like if you have a rich object with the lots of data inside of it for example, you want the computations to move there. So you want the like objects to invoke and just just get the data and do whatever computation they need to.

</details>

**Speaker B**: >> 如果我要对矩形内部的东西进行操作，比如面积。

<details>
<summary>Original English</summary>

**Speaker B**: >> If I'm going to operate on stuff that's on the inside of a rectangle like area.

</details>

**Speaker A**: >> 是的。我究竟是把高度乘宽度分散到整个宇宙的各个地方，还是我在矩形内部拥有一个能够在其边界内处理高度和宽度的面积？现在我不关心矩形有高度和宽度，这对外面的世界是隐藏的。比如我可以，我可以用两个角来表示这个矩形……

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. Do I have height time width scattered all over the universe or do I have an area inside the rectangle that does height and width at the limit? Now I don't care that the rectangle has height and width that's hidden from the rest of the world. Like I can I can represent the rang rectangle with two corners

</details>

**Speaker B**: >> 或者我可以用一个左上角，加上一个高度和一个宽度来表示这个矩形。嗯。

<details>
<summary>Original English</summary>

**Speaker B**: >> or I can represent the rectangle as a top left a height and a width. Mhm.

</details>

**Speaker A**: >> 对外部世界来说，只要它们都能响应‘面积’，这就不重要。所以现在我可以想出另一种表示方式，然后再想出一种表示方式，而外部世界不需要关心我是否已经将计算移动到了数据所在的地方。

<details>
<summary>Original English</summary>

**Speaker A**: >> To the rest of the world, it doesn't matter as long as they both respond to area. So now I can come up with another representation and another representation and the rest of the world doesn't have to care if I've moved the computation where the data lives.

</details>

**Speaker B**: >> 是的。这就意味着你可以拥有更松散的耦合。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yes. And that means you can have looser coupling.

</details>

**Speaker A**: >> 正确。完全明白。这是个很好的教训。

<details>
<summary>Original English</summary>

**Speaker A**: >> Correct. Understood. It's a good lesson.

</details>

**Speaker B**: >> 是的。是的。是的。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. Yeah. Yeah.

</details>

**Speaker A**: >> 而且即使在今天，因为我们所做的一切在底层，几乎我们所做的一切都是对象。其中很大一部分都是面向对象的。而我不认为我们（经常）思考这些。

<details>
<summary>Original English</summary>

**Speaker A**: >> And and even today cuz everything that we do is under the hood. Almost everything we do is object. A lot of it is object-oriented. And I don't think we think about these.

</details>

### 测试的起源与 SUnit

**Speaker B**: >> 是的，我看到很多对用面向对象语言编写的程序的批评，那些批评其实并不是针对面向对象编程或设计的。那么在苹果之后，你转去了一家叫做 Maspar 的公司。我在这里注意到的一件事是单元测试。据我了解，正是在那里，你想出了一个叫做 SUnit 的东西。

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah, I see a lot of criticism of programs written in object-oriented languages that aren't criticisms of object-oriented programming or design. So after Apple, you moved to a company called Maspar. And the thing that I notice here is unit testing. This was the place where, as I understand, you came up with something called SUnit.

</details>

**Speaker A**: 当我在泰克（Tektronix）的时候，呃，我对测试产生了兴趣。在那个时候，测试是一个带有社会阶层意味的分水岭。如果你在计算机科学学院拿了 A 和 B，你就可以去编程。如果你拿了 C，你就得去做测试人员。所以，它真的就像是一种地位的象征。“我不打算做测试。我是……我是这些（优秀的）人之一，不是那些人。”但我对你将如何自动化地测试程序产生了兴趣？你怎么能对你正在做的事情建立信心呢？所以我倾向于是一个容易焦虑的人，我的程序越复杂，我就越需要为之焦虑。我对可能存在哪种类型的 bug 的经验越丰富，我就越焦虑。我心想一定有某种方法能缓解这种焦虑，而不用吃药。那将太好了。我尝试了许多不同的编写自动化测试的方法。在那个时候，除了这种，这种，呃，地位的分歧之外，还有工具上的分歧。那些测试工具会有它们自己专属的一类语言，以及某种与被测程序连接的方式。所以我尝试了这个、那个和其他的东西。实际上是在 Maspar 之后，呃，我……

<details>
<summary>Original English</summary>

**Speaker A**: While I was at Tektronics, uh, I got interested in testing. At that point, testing was a sociological divide. If you got A's and B's in computer science school, you got to program. And if you got C's, you had to be a tester. So, it really was like a status. I'm not going to test. I'm I'm one of these guys, not one of those. But I got interested in how would you automatically test programs? How would you get a sense of confidence in what you were doing? So, I tend to be an anxious person and the more complicated my programs were, the more I had to be anxious about. The more experience I had with what kind of bugs could possibly exist, the more anxious I got. And I thought there was just some way to kind of quell this without pills. That would be great. I tried out a bunch of different approaches to writing automated tests. At that point in addition to this this uh status divide there was a tool divide. You had testing tools which would have their own kind of language and some way to connect with the program that was under test. So I tried this and that and the other thing. It was actually after Maspar that uh I

</details>

<!-- chunk 7/16 -->

### SUnit 的诞生背景

**Speaker A**：我想这都是陈年往事了。所以我们得去挖掘一下这些“考古地层”。当时我开始做咨询工作，准备去告诉一位客户他们应该写测试。我第二天就要飞往芝加哥，但我却没有任何方法能让他们来写测试。于是，从我做过的五六个实验中，我综合出了测试用例（test case）、测试套件（test suite）以及测试结果（test result）。那就是大概三个类和 12 个方法的样子。但它是一个框架，在里面你可以编写相互隔离、全自动执行的测试，并且能给你汇总测试结果。

<details>
<summary>Original English</summary>

**Speaker A**: think is all ancient history. So we'd have to go you know dig through the archaeological layers. I started consulting and I was going to tell a client that they should write tests. I was going to fly out to Chicago the next day, but I didn't have any way for them to write tests. So, out of these five or six experiments that I'd done, I synthesized test case, test suite, and test result. That was the it was like three classes and 12 methods. But it was a framework where you could write tests that would execute isolated from each other fully automatic and give you a rollup of the results of it.

</details>

**Speaker B**：所以这差不多就是一个针对 Smalltalk 的单元测试框架。

<details>
<summary>Original English</summary>

**Speaker B**: So this was pretty much a unit testing framework for small talk.

</details>

### Maspar 与高性能计算环境

**Speaker A**：它是用……是的，第一个版本是用 Smalltalk 写的。当时，Maspar 是一家位于硅谷的初创公司，由风险投资支持，旨在构建一种全新的架构，即 SIMD（单指令流多数据流）。因此，我们会有一个处理元素的环面（Torus），数量多达 16000 个。所以，你有 16000 个处理元素，它们连接在一个环形网格中。你可以与你左边、右边、上面、下面以及对角线上的处理元素进行通信。这看起来非常像现在的 Nvidia 架构，但那是在很久以前，它出现得实在太早了。所以有三年时间，我们都在为高性能计算构建编程环境。当时的意图是想获得相当于那时 Cray 超级计算机的性能，但成本只有它的十分之一，并且他们需要一个编程环境。所以我们用 Smalltalk 构建了一个编程环境，做了一些非常酷的事情。你可以单步执行一个 Fortran 程序，同时建立它的性能分析图。

<details>
<summary>Original English</summary>

**Speaker A**: It was written in yeah the first version was written in small talk. So, Maspar was a Silicon Valley startup venturefunded intended to build an entire new architecture which was uh SIMDI single instruction multiple data. So, we would have a Taurus of process processing elements uh up to 16,000. So, you have 16,000 and they're connected in a toridal grid. So you could talk to the the processing elements in your left, right, up, down, and diagonally. And it looks very much like the Nvidia architecture now, but this was way back when, and it was just too early. So three years of that building programming environments for high performance computing. So the intention was to get the kind of performance you'd get out of a cray at that time um but for a tenth the cost and they needed a programming environment. So we built a programming environment in Small Talk that did some really cool stuff. You could you could single step a forran program and build a performance profile at the same time.

</details>

**Speaker B**：不会吧。所以你们构建了一个运行时环境，允许你们在 Smalltalk 中去解释运行例如 Fortran 这样的程序。

<details>
<summary>Original English</summary>

**Speaker B**: No way. So you built a runtime that allowed you to do in in small talk to interpret for example program programs and run them.

</details>

**Speaker A**：不是的，我们有一个标准的编译器，一个优化编译器。但因为我们控制了操作系统，所以我们能够构建非常底层的探针来收集性能分析数据。这样我们就能够获取这些运行在 16000 个处理器上的 Fortran 程序的代码行级别的分析数据，以及海量的数据。

<details>
<summary>Original English</summary>

**Speaker A**: No the we had a a standard compiler an optimizing compiler but because we had we controlled the operating system we could build really low-level probes to collect performance profiling data. So we could get line level profiles for these four trend programs running on 16,000 processors and great gobs of data.

</details>

### xUnit 测试框架的深远影响

**Speaker B**：这太棒了。就像你们不仅仅是走向更底层，比如构建运行程序的基础设施，但接下来我想把话题回到 SUnit 上。所以关于 SUnit 的概念，就是你拼凑出一个测试用例的那些概念。那是什么来着？测试用例（test case），

<details>
<summary>Original English</summary>

**Speaker B**: That's awesome. Like when you're going from not just like you're going to lower level, you know, like building infrastructure that runs programs, but then I want to go back to to SUnit. So the concept of of SUnit, the the these concept you put together a test case. What was it? the test case,

</details>

**Speaker A**：测试套件（test suite）和测试结果（test result）。

<details>
<summary>Original English</summary>

**Speaker A**: test suite and test result.

</details>

**Speaker B**：这真的变得极具黏性（影响力持久），因为后来出现了你和 Erich Gamma 共同创建的 JUnit，并且还有整个系列——用于 .NET 的 NUnit，以及 xUnit.net。所有这些都继承了其中的一些理念，许多现代的单元测试框架也是建立在这些思想之上的。你认为它为什么能产生如此持久的影响？你觉得为什么以前没有人创造出这个东西？

<details>
<summary>Original English</summary>

**Speaker B**: This really became sticky because then there was JUnit which you later created with with Eric Gama and there's a whole suite uh nunit for uh I think that was fornet xunit.net all of them took over some of these ideas and a lot of modern unit testing frameworks are built on some of these ideas. Why do you think it was so sticky and why do you think it wasn't created beforehand?

</details>

**Speaker A**：之所以以前没有，是因为在程序员和测试人员之间存在着这种社交隔阂。测试人员有很大的动力去拥有他们自己的语言。他们觉得：“这是我的工具，我知道怎么运行它，我就是要运行它。”而且在那个时候，双方对立情绪也很严重，甚至带有一种居高临下的态度，就好像在说：“你是个程序员，不能指望你来做测试，你会只会说代码运行良好。我才是来做成人监督的。”有时候，程序员也确实是那副做派。所以，这确实很难反驳，但我认为这助长了一种观念，即测试工具拥有自己独立的世界。使用与被测试代码相同的语言来编写测试，这是一个充满灵感的决定。这是一个很自然的决定，因为我当时在用 Smalltalk，而在 Smalltalk 中你应该能够表示任何东西。所以我早就习惯了思考“我该如何把这个东西表示为对象”。

<details>
<summary>Original English</summary>

**Speaker A**: So beforehand because of this social divide between programmers and testers. There was a lot of incentive for the testers to have their own language. This is my tool. I know how to run it. I'm going to run it. And it was very adversarial at that time too and kind of patronizing like you're a programmer. you can't be trusted to test, you know, you'll just say it works fine. I'm going to be the adult supervision, you know, and sometime and sometimes the programmers really did act that way. So I, you know, hard to hard to argue with, but I think that encouraged this idea that a testing tool is its own its own world. the inspired decision to use the same language to test as you're testing. It was a natural decision because I was in small talk and you should be able to represent anything in small talk. So, you know, and I was just used to how do I represent this as objects.

</details>

### Smalltalk 的设计哲学

**Speaker B**：所以，听起来 Smalltalk 作为一门语言，在很多事情上都起步很早。我感觉到有很多创新都是源于 Smalltalk 的，因为它是首批真正拥有对象概念的语言之一，但同时它又是一门非常简单的语言。所以你需要构建很多东西，这随后导致了需要将很多事物进行表达、进而去探讨它们——比如设计模式，以及现在的状况，也就是能够用它来编写你的测试环境，或者说，如果你想做测试的话，你就不得不用它来编写。

<details>
<summary>Original English</summary>

**Speaker B**: So, sounds like small talk as a language has been early to a lot of things. I sense a lot of innovation coming from small talk because it was one of the first languages that did have objects but it was a very simple language. So you needed to build a lot of things which then led to representing a lot of things to talking about them design patterns and now also you know being able to write your test environment if if you or being forced to do so if if you wanted to do it.

</details>

**Speaker A**：其实，Smalltalk 伴随着一种特有的精神气质。所以，如果你不喜欢那些工具，或者你在运行调试器时发现它缺乏你现在急需的某个功能，你只需要跳进调用栈，把想要的功能实现出来，然后回去继续做你手头的事情即可。这是一件极其自然的事情，因为在这之间从来没有巨大的鸿沟。你想想今天的情况，假如我正在使用一个 C 语言编译器，然后我意识到：“哦，我真希望 C 语言能有这个新功能。”那我们就得开启一个长达数年的项目去实现它，要进入下一个层级有着巨大的门槛。而在 Smalltalk 中，这是它的设计使然。例如，你有弹出式菜单，在里面你可以直接看到所有的选项。这是一个刻意为之的教学选择。它像是在说：“好吧，你知道怎么剪切和粘贴，但你不知道在这里你还能做些其他什么操作。”所以，菜单不仅提供剪切和粘贴，它还会列出所有你可以做的操作，以此来鼓励你去学习。因为最终你会发现：“我看到这里有个‘格式化’选项，那它是干什么用的呢？”所以这在很大程度上是 Smalltalk 精神的一部分，即这个系统会在你不断使用的过程中教导你。所以，是的，用这门语言来构建测试工具是非常自然的事。当然，你也必须在这个过程中对语言进行一些“变通”。在这里，我有一个针对某个测试用例的类，并且我有一个方法，它是其中的一个测试用例，它以 `t` 开头作为某种魔法标记——你知道，这显得有些牵强。然后当你执行它的时候，你会创建这些对象中的一个，发送 `setup` 消息，因为你可能需要构建一些东西；然后你给它发送类似 `test t` 之类的消息，它就会去执行那个特定的功能。然后，无论是怎么假设，总之最后你会去运行它的 `tear down`（清理操作）。所以它并不... 看起来它的语法和这门语言是一样的。对于测试的表达形式，你实际上是从任何普通代码的表达形式中借用过来的，然后由你自己来解释它。所以，它身处这门语言之中，但在某种程度上又并不完全属于这门语言。

<details>
<summary>Original English</summary>

**Speaker A**: Well there was an ethos that went along with small talk. So if you didn't like the tools, if you're running the debugger and the debugger doesn't have some feature that you really need right now, you just hop on the stack, implement the feature that you want, and then get back to whatever it was you were doing. That was just a natural thing because there was never this huge gap. You know, imagine today, uh, I'm I'm using a C compiler and I realize, oh, I wish C had this new feature. We're embarking on a multi-year project to go and like the huge barrier to entry to go to the next level. And in small talk by design, for example, you have pop-up menus and they you can see all of the options right there. That's a deliberate pedagogical choice. It says, "Okay, well, you know about cut and paste, but you don't know the other things that you can do right here." So the menu doesn't just give you cut and paste. It gives you all the things that you can do as a way to encourage you to learn about them because eventually you're going to I see this format item here and I well what does that do? So that was very much part of the small talk ethos that this system would teach you as you kept using it. So yeah it was very natural to build the testing tool in the language. And of course you have to kind of bastardize the language a bit here. Here I've got this this class for some test case and I have a method which is one of the test cases and it starts with t is kind of magic you know uh this is getting squidgy and then when you execute it you create one of these objects you send it setup because you don't you know may have to build some stuff and then you send it the test t something or other and it executes that one thing and then you Then assuming well then regardless you run the tear down from that. So it's not it looks like the the syntax is the same as the language. The the representation of the tests you kind of borrow from the representation of just any kind of code and then you interpret it yourself. So it's it it it it it's in the language but it's not really in the language at the same time.

</details>

### 面向对象项目管理的探索

**Speaker B**：但是人们并不会去想这些。他们只会觉得：“我派生了这个子类，我提供了一个带有测试注解或者以 `test` 开头的方法，然后它就自动运行了”，这样就挺好。我想把时间跳到几年后的 1996 年，你开始参与克莱斯勒（Chrysler）的一个项目，也是在这里你遇到了 Martin Fowler。那是个什么样的项目？

<details>
<summary>Original English</summary>

**Speaker B**: But people don't think about that. They just think I subclass this I give a method with the annotation of test or with starts with tst and then it just starts working and that's fine. I want to jump to a few years later from to 1996 you started to work on a project at Chrysler and this is where you met Martin Fowler. What was this project?

</details>

**Speaker A**：其实我在那之前的一小段时间就见过 Martin Fowler。早在第一届 OOPSLA 会议的时候，就有一个问题：我们该如何管理面向对象项目，使之有别于我们使用上一代工具管理项目的方式？上一代工具提供给你进行变更的选项绝对要少得多。你仍然需要修改代码，但与使用面向对象程序工作相比，难度要大得多。那么这种方法论是什么呢？我们曾经有结构化分析和结构化设计。针对对象的方法论应该是什么？它又应该有何不同？那是 1986 年首届 OOPSLA 大会上的核心难题。等到 1994、1995 年左右，我们开始对它可能的样子有了一点线索。我想，当时的“统一软件开发过程（RUP）”，或者说后来演变成统一软件开发过程的那些东西，在那时就已经存在了，那是由——

<details>
<summary>Original English</summary>

**Speaker A**: I'd actually met Martin Fowler a little bit before that. So as early as the first oops conferences, the question of how do we manage projects with objects differently than we manage projects with the previous generation of tools. The previous generation of tools definitely gave you a many fewer options for change. You'd still have to change code, but it was just a lot harder compared to working with object-oriented programs. So what is the methodology? We had we had the structured analysis, structured design. What is the methodology for um for objects and how should it be different? That was the million-dollar question at the original 86 oops law. By the time 9495 rolled around, we were starting to get a clue what that would look like. There were I think uh the rational and unified process or the the things that would go into the rational unified process already existed by that time which was

</details>

**Speaker B**：Grady Booch 参与了那个。

<details>
<summary>Original English</summary>

**Speaker B**: Brady Buch was involved in that.

</details>

**Speaker A**：Grady Booch，还有 James Rumbaugh、Ivar Jacobson。所以人们正在提出各种各样的答案。Ward 提出了他自己的答案，叫作“Episodes”，并将其写成了一种模式语言。因为我们感觉，你知道的，“我手里并没有一大把戏法，我只能把同样的招数用了一遍又一遍”，而事实证明对每个人来说都是如此。所以你可以在 Ward 的 C2 网站上找到这篇《Episodes》。把这些进行比较非常有趣，因为我从他那里大量地借用了思想。我也从我所看到和经历过的其他所有事物中吸取了经验。但在那个阶段，我已经……我是什么时候离开 Maspar 的？92 年。所以我已经是一个……

<details>
<summary>Original English</summary>

**Speaker A**: Brady BC Evar uh James Rumba Ivar Yakabson. So people were coming up with some kinds of answers. Ward had come up with his own uh answer called episodes written into as a pattern language because we were like you know I don't have a big bag of tricks I have to keep using them over over again and the same is true turns out of of everybody. So you can find that episodes on uh Ward's C2 site. It's really interesting to compare that because I I borrowed heavily from that. I borrowed from everything else that I had seen and experienced. But at that point, I'd been when did I leave Masspar? 92. So I had been an

</details>

<!-- chunk 8/16 -->

### 起源与克莱斯勒项目

**Speaker A**: 那时我已经做了四年的独立顾问。当时在斯诺鸟（Snowbird）举办了几次关于方法论问题的研讨会。我不知道为什么选在斯诺鸟，反正别人决定的。我在我参加的第一次研讨会上认识了马丁（Martin）。他的自我介绍非常经典，典型的马丁式开场白。他说：“我是这里唯一一个我从未听说过的人。”那时他已经在分析模式方面做了一些非常出色的工作，这些我也是知道的。所以我很兴奋能见到他。说回克莱斯勒（Chrysler）的这个项目。这个项目对于应对千年虫（Y2K）问题很重要，但不确定能否及时完成。马丁当时已经在那里担任顾问了。我之前因为做一些 Smalltalk 方面的事情认识了罗恩（Ron Jeff）。我不太记得我们具体是怎么认识的了，长话短说，我当时作为首席顾问之类的身份加入，用一种截然不同的开发风格重启了那个项目。对于那种风格，我把我所知道的所有有用的东西都拿来，并将其发挥到极致（cranked it up to 11），同时摒弃了所有我无法证明我们需要的东西。所以这就是这种全新开发风格背后的价值体系。马丁和我也会定期去那里看看。罗恩是全职在那里的。我最初是作为性能顾问被引进来的，因为我对 Smalltalk 的性能非常了解，而他们当时在使用一个叫做 Gemstone 的数据库。它有着 Smalltalk 的对象和语义，但也结合了持久化、事务、索引等所有数据库的优点，但它的运行速度不够快。所以我说：“那测试用例在哪里？我需要确保在我做一些修改时不会弄坏其他东西。”他们说：“呃，其实它现在还没法算出正确的结果。”我于是回答：“好吧，那我可以让它跑得非常快。”他们不太喜欢这个答案。不管怎样，那是我在一周时间里见过的最大幅度的改变。那周末尾，每个人都筋疲力尽，因为他们工作了很长时间。我说：“让大家都回去休息两周。告诉他们好好休息。我们回来后，会把目前为止写的所有代码都扔掉，然后重新开始。”于是我们以三周为一个节奏重新启动了项目。每三周，薪酬专家玛丽（Marie）就会指定更多的测试用例，我们就继续开发，接着开启下一个三周的周期，周而复始。

<details>
<summary>Original English</summary>

**Speaker A**: independent consultant for four years at that point. And there were a couple of workshops uh held in Snowbird. I don't know why we picked Snowbird, but somebody else did uh about this methodology question. Um, and I met Martin at the first one of those that I attended. And his introduction was, it's just the classic Martin introduction. He said, "I am the only person here I've never heard of." And he was already doing some some great work on uh analysis patterns uh at the time, which I knew about. So, I was excited to to meet him. Get to this Chrysler project. The project's important for Y2K, but it's not clear that it's going to be finished in time. Martin was already there as a consultant. Uh I had met Ron Jeff doing small talky stuff. I don't remember exactly how we met, but long story short, I came in as I know lead consultant or something restarting that project in a very different development style. And for that style, I took everything that I knew that was useful and cranked it up to 11 and discarded all the stuff that I couldn't prove we needed. So that was the value system behind this new style of development. Uh Martin and I would visit there periodically. Ron was there full-time. I was originally brought in as a performance consultant because I knew a lot about small talk performance and they were using a database called gemstone which it was small talk objects small talk semantics but coupled with persistence transactions indexes all that database good stuff but it wasn't going fast enough so I said well where's the test case that makes sure that I don't break something if I make some changes and I said well actually it's not computing the right answers yet. And I said, "Well, then I can make it go really fast." And they didn't like that answer very much. Anyway, most change I've ever seen over the course of one week. At the end of which, everybody was exhausted. They've been working very long hours. I said, "Send everybody away for 2 weeks. Tell them to get some rest. We'll come back. We'll throw away all the code that we've written so far, and we'll restart." And we restarted on this 3-w weekek cadence. Every three weeks we would have more test cases specified by Marie, the payroll expert would be working and then we'd start another 3-we segment and another and another.

</details>

**Speaker A**: 结果发现，当时被我们发挥到极致的那些做法，后来还能再往上提升好几个层次，但在当时，那就是我们能想象到的最密集的重新计划、集成、部署、重构等等。融入其中的想法是我所有这些经验的综合。比如从沃德（Ward）那里学来的经验，当时你们俩开始结对编程，传递键盘，并决定你们要做哪些不同的事情；以及你对于测试作为一种概念的经验——也就是测试不需要专门的测试团队来做，而是你可以用你自己的语言自己做，这在当时是全新的概念。所以所有这些想法全都汇聚在了一起。

<details>
<summary>Original English</summary>

**Speaker A**: No, it turns out those 11s that we turned everything to, there were several notches beyond that, but it was just that was the most intensely we could imagine replanning, integration, deployment, refactoring, and so on. The ideas that went into that was this synthesis of all these experiences that I'd had. And then so this is from from Ward when the two of you started to pair and pass the keyboard and and decide on all the different things that you're going to do your experience with tests as as a concept of that it doesn't needs to be the testing team that does it themselves but you can do it yourself in your own language which was just new new and and so all of these ideas just all came together.

</details>

### 极限编程的诞生与命名

**Speaker B**: 是的。那么你是什么时候给它命名的呢？

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. And then when did you give it a name?

</details>

**Speaker A**: 项目开始进展得很顺利。起初我感到兴奋，也很害怕，随后又是兴奋。后来项目进展得真的非常顺利。

<details>
<summary>Original English</summary>

**Speaker A**: It started going well. At first I was like I was excited. I was scared. I was excited. Then it started going really well.

</details>

**Speaker B**: 所以项目开始有肉眼可见的好转。

<details>
<summary>Original English</summary>

**Speaker B**: >> So like the project started to go visibly well.

</details>

**Speaker A**: 是的。是的。大概六个星期之后，我就很开心地和朋友们分享这件事。“我们现在在克莱斯勒做的这种全新工作方式。”“我们在克莱斯勒做的这种全新风格……”这套说辞反反复复讲，开始显得有些老套了。所以我又去翻同义词词典，试图想出合适的词来描述……

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. Yeah. After my like six weeks and then I was happy to be telling my friends about it. This new style of working that we're doing here at Chrysler. This new style of working we're doing here at Chrysler. This new style. They got kind of old to say that over and over again. So now I'm back with the C thesaurus trying to figure out what are the words

</details>

**Speaker B**: 来称呼我们。

<details>
<summary>Original English</summary>

**Speaker B**: >> called us.

</details>

**Speaker A**: 我觉得我们真的搞出了点名堂，而且这将会是一件大事。所以我想保护它。对格雷迪（Grady）说声抱歉，他现在是我的好朋友了，但当时我不想让格雷迪（Grady Booch）哪天也声称他在做这个东西。所以我必须选一个名字，这个绰号要足够不讨喜，以至于没人会试图把它偷走。就在这个时候……

<details>
<summary>Original English</summary>

**Speaker A**: >> I thought we were really on to something that was going to be big. So I wanted to protect it. Apologies to Grady who's a good friend now. But um I didn't want Grady BCH to ever say that he was doing this thing. So, I had to pick I had to pick a moniker that was unattractive enough that somebody would try and steal it. And this is about the point at which uh

</details>

**Speaker B**: 你现在又流露出那种朋克气质了。

<details>
<summary>Original English</summary>

**Speaker B**: >> you're you're now this punk again.

</details>

**Speaker A**: 是的。好吧，确实。我现在依然是，（笑）只是一个老点的朋克了。是的，是的。但也带有一点对传统体制嗤之以鼻的意味。当时有极限运动（Extreme sports）。我有点喜欢用极限运动来打比方，因为你不能第一次跑到雪崩的坡顶就直接踩着单板滑雪。不行，你必须做好极其充分的准备。你必须做足所有的研究，如果你拥有这些卓越的技能，你才能完成那些壮举。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. Well, yeah. I still am, but [laughter] I'm just I'm just an older punk now. Yeah. Yeah. But but a little bit of thumb the nose at the establishment. Extreme sports were there. I kind of like the analogy with extreme sports because you don't just hop on a snowboard at the top of some avalanche and the first time. No, you have to be supremely prepared. You have to have done all of your research and then if you have these outstanding skills, then you accomplish things.

</details>

**Speaker B**: 是的，还有训练之类的，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. And training and all that, right? 

</details>

**Speaker A**: 那些看似不可能完成的事情，如果你没有做足准备，就绝对是不可能的。所以它很准确，也很前卫，这就是“极限”（extreme）这个词。因此，“极限编程”（Extreme Programming）就这样诞生了。

<details>
<summary>Original English</summary>

**Speaker A**: >> that seem impossible and are impossible if you haven't done all the prep. So it's accurate, it's edgy, it's the that word extreme and hence extreme programming was was born.

</details>

**Speaker B**: 所以那是“极限”这部分。

<details>
<summary>Original English</summary>

**Speaker B**: >> That's so that's the extreme part.

</details>

**Speaker A**: 在“极限”这点上，我知道会有很多人不喜欢它，但这没关系。我一开始管它叫“开发”（development），其实我现在还有点喜欢这个词，因为用软件交付价值不仅仅是“编程”。但是当时的那些方法论将编程视为一项文书工作。我们会画这些图表，画那些图表，构建这个东西，有 14 种将其可视化的方法，然后进行一些编程，接着再画更多的图表。而我认为，编程——手指放在键盘上，盯着代码看——那才是我学习的地方，因为在那里，你要么算出了正确的值，要么没有，你再也没法欺骗自己假装弄懂了。所以我想提升那个“现实与程序交汇”的时刻的地位，这就是“编程”一词的由来。此外，在非常早期的阶段，我也叫它 XP，作为一种与“极限”和“编程”这两个词带来的负面影响相区隔的方法。我们可以直接叫它 XP，这样它更像是一个通用术语。没过多久，微软发布了 Windows XP，在某个平行宇宙里我起诉了他们并胜诉了；而在另一个平行宇宙里我起诉了他们却败诉了，导致我破产，孩子们都饿死了。所以，你懂的。

<details>
<summary>Original English</summary>

**Speaker A**: >> Extreme we had I knew that a bunch of people wouldn't like it but that's okay. I started out calling it development which I still kind of like because there's more to delivering value with software than programming but the methodologies extent at that time treated programming as this clerical task. We'll we'll we'll draw these diagrams and these diagrams and build this thing and the 14 ways to visualize this and then then there's some programming and then we'll draw some more diagrams and I thought programming sitting fingers on keyboard staring at code that's that's where I do my learning because that's where you can no longer fool yourself that you actually understand either you compute the correct value or you don't compute the correct value. So I wanted to elevate that moment of reality meets program and that's where the programming comes from. Now from very early days I also called it XP as uh a way of separating from the downsides of both of those words extreme and programming. So we can just call it XP and it's it's more of a generic thing. Not long after that, Microsoft releases Windows XP and there's an alternate universe in which I sued them and succeeded. And there's another al alternate universe in which I sued them and failed and bankrupted myself and my children all starved to death. So,

</details>

### XP 的时机与影响

**Speaker B**: 对。对。因为这大概是在 90 年代末，然后 XP 发布了。是的。在这之后不久，我想是 2000 年或 2001 年，大概是那个时候。XP，或者说极限编程，是什么时候开始变得有影响力的呢？是在你给它命名并开始告诉别人时，还是在 2000 年你的书出版的时候？

<details>
<summary>Original English</summary>

**Speaker B**: >> Right. Right. Cuz this was right around the year late '9s and XP came out. Yes. Soon after, I think 2000 or 2001, something like that. When did XP extreme programming recall start to become big? Was it as you gave it a name and you started telling people or then there was your book which came out in the year 2000?

</details>

**Speaker A**: 我记得我做的第一场关于 XP 的演讲，我准备了一些宣传单发给大家。我想那是在 OOPSLA 大会的一个小组讨论之类的场合。我谈了一些关于 XP 的内容，结束后，人们跑过来找我要资料。绝不仅是一份资料那么简单。大家的反应非常热烈，扯着我的衬衫，都想了解和参与这个东西。而且我认为 XP 抓住了绝佳的时机，正好赶上了互联网发展的上行期，不是泡沫破裂，而是它刚开始起飞的时候。人们看到其他的方法论，比如，你知道的，极其谨慎地准备，写这份分析文档，写那份设计文档，然后进行大量编码，接着再进行大量测试。他们知道，在一个变化如此之快的世界里，随着互联网浪潮开始涌起，开始进入这种超级爆发式增长，这种方式永远行不通。另一方面，我们也知道那种“牛仔风格”（cowboy style）的做法：你喝着 Jolt 可乐——安息吧，Jolt 可乐——像个牛仔一样，找一帮程序员，他们写着别人看不懂的代码，谁也不搭理，你只要从门缝里塞披萨进去，他们就能把代码拿出来。这也一样行不通。而这儿正好有一个看似介于两者之间的东西。它有纪律性，有迭代过程，而且过程透明。你有方法去引导开发方向，有方法去调整流程。你有各种测试来确保东西真的能运行。人员之间，无论是业务人员还是技术人员，或是技术人员内部，都有频繁的对齐和沟通。好，我能看出来这是行得通的。所以他们能看到互联网正在爆发，而我可以用 XP 来抓住这个机遇，除此之外我真的没有其他任何替代方案。

<details>
<summary>Original English</summary>

**Speaker A**: >> I remember the first talk about XP I gave I had some flyers to hand out. So I think it was at an oopsum on a panel or something like that. I I talked some about XP and afterwards people were give me a copy. No, no. Uh uh uh uh uh uh uh. The reaction to it was just tugging on my shirt wanting a piece of this thing. And I think the XP had exquisite timing in that the dot the upside, not the bomb, but the the upside of it was just starting to hit. They looked at other methodologies. It would say, you know, very carefully prepare, do this analysis document, do this design document, then a bunch of coding, then a bunch of testing. They could tell that's never going to work in a world that's changing as fast as the internet wave starting to crest, starting to come into, you know, the this super hyper growth. On the other hand, we know that this cowboy style of just, you know, you have the Jolt Cola, rest in peace, Jolt Cola, cowboy, you have a bunch of programmers, they do incomprehensible stuff, they don't talk to anybody, you just slide pizza under the door, and then you get the code out. That's not going to work either. Here's this thing that looks like it's kind of in between the two. There's discipline to it. There's iteration to it. There's transparency to it. You have ways of steering what goes on. You have ways of tuning the process. You have all these tests to make sure that stuff actually works. You have frequent alignment between people, whether it's business people and technology people or technology people with each other. Okay, I can see how this could work. And so they could see the internet is exploding and I can use XP to take advantage of that opportunity in a way that I I can't I don't there wasn't really another alternative to it.

</details>

**Speaker B**: 基本上，XP 为你提供了一种能跑得相当快的方法，而且……

<details>
<summary>Original English</summary>

**Speaker B**: >> Basically XP was giving you a way to move pretty fast and

</details>

<!-- chunk 9/16 -->

### The Origins of Test-Driven Development

**Interviewer**: 灵活敏捷的同时也能保持一种稳定感，而不是完全失控。有测试作为保障。你们有迭代、有计划、有学习的过程。那么，测试驱动开发（TDD）是什么时候出现的呢？因为我记得你写过一本书，大概是在两年后出版的，叫做《测试驱动开发》（Test-Driven Development: By Example）。它是如何与极限编程（XP）联系起来的？

<details>
<summary>Original English</summary>

**Interviewer**: nimble but also have a sense of stability not just going wild. tests there. You had the iterations, the planning, the learning. And then when did TDD come along? Because there was a book that you you wrote that came out, I think two years later, uh, test-driven development by example. And how did it relate to XP?

</details>

**Kent**: 其实测试驱动开发（TDD）对我来说是更早之前的一次重新发现。记得我还是个孩子的时候，我读了所有这些书。我记得我爸爸带回家的一本书，我现在还没找到它的副本。书上说：“这就是编程的方法。”那是还在磁带对磁带的时代。所以，你会有一条输入磁带，你知道，就像考勤卡一样，然后你把它放入工资单程序中，它会写入一条输出磁带，比如支票金额、预扣款金额等等。

<details>
<summary>Original English</summary>

**Kent**: So TDD was an earlier test development. Test-driven development was an earlier rediscovery for me. Remember, I was a kid. I read all these books. I remember one of the books my dad brought home and I still haven't found a a copy of it. Said, "Here's how you program." This was back in the days of taped to tape. So, you'd have an input tape, you know, like time cards, and then you put it through the payroll program, which would write an output tape, which was like dollars for checks, dollars for withholding, etc., etc.

</details>

**Interviewer**: 是的。所以它总是……然后再……

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. So it was always and then

</details>

**Kent**: 真的就是在过去那个年代，你会有一长串这样的东西。这其实是函数式编程，因为你不能改变输入磁带，但是运行工资单、应付账款或库存盘点，就是一个这样的过程：我拿这些磁带，输入到这个程序里，然后拿着那个输出，再输入到这个程序里，诸如此类。然后你是真的手动去操作，就像是实际上……

<details>
<summary>Original English</summary>

**Kent**: really back in the day and and you'd have these long strings of this and it's actually functional programming because you can't change the input tape but operating payroll or operating accounts payable or operating inventory was a process of I take these tapes I feed them into this program I take the output of that feed them into this program and blah blah blah blah blah blah and then you really manual like actually

</details>

**Interviewer**: 物理上去扯下一条磁带，然后把它移过去。

<details>
<summary>Original English</summary>

**Interviewer**: physically pulling a tape off and moving it over. Yeah.

</details>

**Kent**: 是的。那本书上是这么说的：编写这些程序的方法是，你先拿一条输入磁带，一条你需要处理的实际输入磁带，然后你手动输入你期望它生成的输出磁带。你会说，好吧，对于这个小时数，我应该在输出中得到像这样的一条记录。

<details>
<summary>Original English</summary>

**Kent**: And it so it said here's how you write one of these programs is you take an input tape an actual input tape that you need to process and you manually type in the output tape you expect that to generate. You say okay well this number of hours uh should I I should have a record in the output that like this.

</details>

**Interviewer**: 我明白我们要说到哪里了。你在定义输出。你在开始写程序之前，就已经在定义输出了。

<details>
<summary>Original English</summary>

**Interviewer**: So I see where we're going with this. You're you're defining the the output. You're before you start on the program.

</details>

**Kent**: 没错。所以首先你需要知道，我期望得到什么？我怎么去验证它？

<details>
<summary>Original English</summary>

**Kent**: Yeah. So first you need to know what do I expect? How can I validate it?

</details>

**Interviewer**: 正确。

<details>
<summary>Original English</summary>

**Interviewer**: Correct.

</details>

**Kent**: 我在小时候读过那段话，当时根本就是一窍不通，但它却一直深藏在我的脑海深处。我写了 SUnit，然后最开始使用它。我把它给了 Hal Hildebrand，我认识的最聪明的程序员之一。我原本以为他不需要它。结果他不仅用了，而且很喜欢它。所以，我知道我的这个测试框架是摸到了一些门道的。后来我清了清嗓子，就是在那里随便瞎折腾，突然想起了“先输入输出磁带”的这个做法，然后把它与我用 SUnit 所做的测试对应了起来。我恍然大悟：好吧，如果我遵循那个模式，我就会在编写代码之前先写测试。我还记得我当时忍不住笑出声来，因为这听起来实在是个太蠢的主意了。为什么要写一个你明知道会失败的测试呢？你甚至连类都还没定义。你甚至连方法都还没定义。在它有可能成功之前，它肯定会以各种不同的方式失败。管他呢，酷。我们来试试看会发生什么吧。

<details>
<summary>Original English</summary>

**Kent**: I had read that as a kid, didn't understand diddly squat, but but it's it's back in the back here someplace. I wrote sunit for the first started using it. Gave it to Hal Hildebrand, one of the smartest programmers. I knew I didn't figure he would need it. He used it. He loved it. So, I knew I was on to something with with this this testing framework. And then I [clears throat] was just kind of farting around and remembered this typing in the output tape first and mapped that onto the testing that I was doing with SUnit. I went, well, if I followed that pattern, I would write the test before I wrote the code. And I can remember laughing out loud because it was such a stupid idea. Why would you write a test that you know is going to fail? you you don't even have the classes defined yet. You don't have the methods defined yet. It's just it's going to fail a bunch of different ways before it could possibly succeed. Cool. Let's try it and see what happens.

</details>

### The First TDD Example and "Stupid Ideas"

**Kent**: 于是，我用栈（stack）作为我的第一个例子。所以我新建了一个栈（stack new），压入一个元素（push），然后弹出它（pop）。我应该得到相同的东西。好的。然后我去编程实现它，好吧，满足这个很容易。下一个是什么？你知道，你压入两个东西，然后你以正确的顺序将它们取回。好的。这一个也搞定了。接下来，`dupe pop top` 是空的，结束。之前的那些焦虑都去哪儿了？

<details>
<summary>Original English</summary>

**Kent**: So, I I used stack as my first example. So, I have a stack new and I push something and I pop it. I should get the same thing back. Okay. And then I went to program it and okay, well, that's easy to satisfy that. What's the next one? You know, you push two things and you get them back in the right order. Okay. And this and uh dupe pop top is empty and finished. Where's the anxiety?

</details>

**Interviewer**: 哦，就这么消失了。哦，这是前所未有的。

<details>
<summary>Original English</summary>

**Interviewer**: Oh, just gone. Oh, for the first time.

</details>

**Kent**: 哇。我想不出还有什么测试用例是不会通过的了。所以，我真的完成了，我感觉棒极了。我觉得我完成了，而且我确实完成了。哇。从“这是个愚蠢的想法”变成了“我们不妨试一试”。绝对的。不，我还留下了一句评论。总是去尝试你那些愚蠢的想法，如果你能以低廉的成本并且可逆地去做的话。跳桥可不是一个可逆的决定。我不是在说那个。我指的是像这种事情，你只是觉得，“这有个愚蠢的想法。” 100 次里有 99 次它都会失败。但总有那么一次，你将没有竞争对手，因为没有其他人会蠢到去尝试这个想法。我这种“我才不在乎你怎么看”的朋克态度，促使我去尝试了许许多多愚蠢的想法。其中大部分你都没看到，但确实有一系列想法，其结果远远好于预期。

<details>
<summary>Original English</summary>

**Kent**: Wow. I can't imagine another test case that wouldn't pass. So, I'm really I'm finished and I feel great. I feel finished and I am finished. Wow. Go going from this is a stupid idea. Let's let's try it. Absolutely. No, I made a comment. Always try your stupid ideas if you can do it cheaply and reversibly. Jumping off a bridge is not a reversible decision. Not talking about that. I'm talking about stuff like this where you're just like, "Here's a stupid idea." 99 times out of a 100 it'll fail. But that one time you won't have any competition cuz nobody else is stupid enough to try this idea. Part of this punk attitude, I don't care what you think about this has enabled me to just try lots and lots of stupid ideas. And most of them you don't see, but there had been a string of them which worked out way better than they would have expected to work out.

</details>

### TDD in the Era of AI Agents

**Interviewer**: 没错，后来还有很多人也尝试了这些想法。你知道，我想 TDD 就是一个很好的例子。在你写了那本关于 TDD 的书之后不久，曾经有一段时间……那是一本超级受欢迎的书。我依然记得，我想在 21 世纪头十年的后期，我也有一本，当时人们都在做小组练习，开发者们也都是这样进行开发的。随着时间的推移，它的热度可能下降了，我感觉到了 2010 年代，我看到越来越少的人在做这件事，而且它几乎完全过时了。而现在，随着 AI 智能体（Agents）的出现，这个理念又回来了，因为事实证明，智能体这么做可能会花更多时间或者别的什么，但智能体可以做到这一点。这对它们自己进行测试是非常有用的。虽然短期内会消耗 token，但从长远来看可以为它们节省成本，因为在使用 AI 时一个典型的经典错误就是做出来的东西根本没法工作。那么，你如何才能稍稍勒紧缰绳加以控制呢？以及，为什么 TDD 曾经会过时呢？

<details>
<summary>Original English</summary>

**Interviewer**: Well, and then a bunch of other people tried these ideas as well. You know, like I think TDD is a good example where there was a time where shortly after you wrote the book about it as well. Uh it was it was a super popular book. I still remember I think I had a copy as well back in the the late uh two 2000s people were like doing you know group exercises developers were developing accordingly over time it it probably dropped I would say in the 2010s I saw fewer and few people doing it uh and it almost went out of style completely and now with uh with agents the idea is back because turns out it might take more time what not but agent agents can do that but it's a It's pretty useful for them to test themselves. It costs tokens in the short run, but it can save them in the long run because one of the classic genie mistakes is stuff doesn't work. So, how do you how do you pull in the reins a little bit? And why did TDD go out of fashion?

</details>

**Kent**: 我觉得很大一部分原因在于，我做一段时间某件事，然后就会转向另一件事。对于设计模式如此，对于 JUnit 也是如此。对于 TDD 是这样，对于 XP 同样如此。我就是转移到下一件事情上了。所以我去做了别的。TDD 就留在了那里。然后，就有一些人把它当作道德大棒来挥舞。就像说，如果你不使用 TDD，你就不够专业。那真的是太…… 人们可以通过各种各样不同的工作流写出非常棒的软件。现在，不同的工作流都有其优缺点。TDD 的最佳适用场景，是那种发现与实现相结合的过程。我大概知道我想去哪里。我并不确切地知道我要如何到达那里，但我知道第一步是什么。所以，我迈出第一步，这会让我学到一些东西，从而让我能迈出下一步，然后那又会教会我一些东西。如果你只是想要一直实现、实现、实现、实现，那没问题。还有其他很好的工作流。如果你只是想坐在那里一直学习、学习、学习，我不认为那会很奏效，但你肯定也不需要 TDD。只有当你在“我做一件事、我学到一点东西、我做一件事、我学到一点东西、我做一件事、我学到一点东西”之间进行快速交替时，这才是 TDD 真正强大的地方。但这不是一个道德层面的决定。这是一个非常实际的决定。

<details>
<summary>Original English</summary>

**Kent**: I I think uh there's a big part of it is I work on something for a while and then I switch to something else. That was true of patterns. It was true of Junit. It's true of TDD. It's true of XP. I just move on to the next thing. So I moved on to the next thing. TDD is out there. And then there were people who used it as a moral cudgel. Like you should be if you're not using TDD, you're not professional. And that's just such People can write very good software with a wide variety of workflows. Now, there's advantages and disadvantages to different workflows. The sweet spot of TDD is this combination of discovery and realization. I kind of know where I want to go. I don't know exactly I'm going to get there, but I do know the first step. So, I take the first step and that teaches me something which lets me take the next step. and that teaches me something. I if you can just go implement implement implement implement, fine. There's other workflows that are fine. If you just want to sit there and go learn learn learn, I don't think that works very well, but you certainly don't need TDD. It's when you have this rapid alternation between I do a thing, I learn a thing, I do a thing, I learn a thing, I do a thing, I learn a thing. That's where TDD is really powerful. But it's not a moral decision. It's a practical decision.

</details>

### Sponsor Break: Antithesis and WorkOS

**Interviewer**: 测试驱动开发（TDD）是 Kent 对软件编写和交付方式作出的最持久的贡献之一。在如今的智能体（Agentic）开发时代，它比以往任何时候都更加重要。如果你与智能体一起工作，你的工作就不再是编写代码了。你的工作是定义规范并进行测试。这里我必须要提一下我们的首席赞助商。Antithesis。Antithesis 是如今验证代码最有效的方法。让我来解释一下它是如何运作的。Antithesis 在一个充满敌意的模拟环境中运行你的整个系统。通过这种方式，它能在你的用户发现问题之前找出每一个 bug。而且，因为这个模拟是完全确定性的，Antithesis 不仅能找到 bug，它还能为你提供每一个问题的完美重现。我知道这听起来有点像科幻小说，但其底层实际上是非常硬核的工程技术。Jane Street、Fly.io 以及 CCD 社区都在满怀信心地交付由智能体编写的代码，因为他们知道这些代码已经经过了 Antithesis 的验证。想要查看更多案例研究和详情，请访问 antithesis.com/pragmatic。网址是 antithesis.com/pragmatic。

<details>
<summary>Original English</summary>

**Interviewer**: Test-driven development is one of Kent's most lasting contributions to how software is written and shipped. And today with Agentic development, it's more important than ever. If you work with agents, your job is no longer writing code. It's specifying and testing it. This is where I need to mention our presenting sponsor. Antithesis. Antithesis is the most effective method of verifying a code today. Let me explain how it works. Antithesis runs your whole system in a hostile simulation. By doing so, it finds every bug before your users do. And because the simulation is fully deterministic, antithesis doesn't only find bugs, it gives you a perfect reproduction of every issue. I know this sounds close to science fiction, but it's actually hardcore engineering under the hood. Jane Street, Fly.io, and the CCD community ship agent written code with full confidence because they know it's been verified by antithesis. To see more case studies and details, head to antithesis.com/pragmatic. That's antithesis.com/pragmatic.

</details>

**Interviewer**: Kent 倾注其整个职业生涯打造了我们现在视之为理所当然的基础原语（primitives）。单元测试、设计模式、重构。而构建于坚实的基础原语之上，正是我们本季赞助商 WorkOS 所做的事情。如果你在构建任何 SaaS 应用，尤其是 AI 产品，迟早你需要着手构建企业级功能。诸如为应用程序和智能体提供 OAuth 登录等功能。WorkOS 可以处理这一切。单点登录（SSO）、SCIM（跨域身份管理系统）、以及专门针对智能体实际运行方式构建的细粒度授权。目前增长最快的 AI 公司——如 Anthropic、OpenAI、Cursor、Perplexity——都已经信任 WorkOS 来解决这些问题。快去查看 work.com。

<details>
<summary>Original English</summary>

**Interviewer**: Kent has spent his career building the primitives that the rest of us now take for granted. Unit testing design patterns refactoring. And building on solid primitives is exactly what our seasonal sponsor works is all about. If you're building any SAS, especially an AI product, sooner rather than later, you'll need to get around building enterprise features. Things like O for apps and agents. Work handles it. SSO, skim, fine grade authorization built for how agents actually operate. The fastest growing AI companies entropic open AI cursor perplexity already trust work to solve these problems. Check out work.com.

</details>

**Interviewer**: 话虽如此，让我们回到 Kent 这里，谈谈敏捷宣言（agile manifesto）到底是从哪里来的。我想谈谈这一件你同样也非常、非常……

<details>
<summary>Original English</summary>

**Interviewer**: And with this, let's get back to Kent and where the agile manifesto came from. I wanted to talk about the one thing that you're also very very

</details>

<!-- chunk 10/16 -->

### 敏捷宣言的诞生背景

**Speaker A**: 关于那份有17个人参与起草、而你是第一个署名的《敏捷宣言》。你能带我回顾一下在雪鸟滑雪场（Snowbird）究竟发生了什么吗？当时的行业状况如何？是什么促使你们所有人聚在一起的？

<details>
<summary>Original English</summary>

**Speaker A**: ... the thing that 17 people wrote, but you're the first one listed, the Agile Manifesto. Can you take me back to what happened in in Snowbird? What was the industry like and and what made all of you come together?

</details>

**Speaker B**: 当时有一群人，记得我们在一起讨论面向对象（objects）的方法论到底是什么。那时候有一种占据主导地位的“统一软件开发过程”（Rational Unified Process），我个人认为它既不合理（rational），也不统一（unified），更称不上是一个过程（process）。不过那主要是另一回事了，我那么说很大程度上是为了调侃一下别人。但在当时，那是被认为成年人做软件开发应有的方式。而我们当中有一群人，如果你去和 Grady 谈，或者和 Jim、Ivar 谈谈他们会如何应用，实际上看起来和我开发的方式非常相似，但你们到底怎么做并不重要。重要的是读了你们写的这些东西的人会怎么做。当时它被用在了一种非常瀑布流式的开发中。进行一大堆的分析，一大堆的设计，一大堆的实现，然后是独立的测试，这种灾难一遍又一遍地重演。

<details>
<summary>Original English</summary>

**Speaker B**: There were a bunch of people remember we were talking about what is the methodology for objects and you had kind of this dominant rational unified process which I say is neither rational nor unified nor a process but that's a separate mostly I did that to tweak people's noses but that was the adult way to to do development and there were a bunch of us who if you talk to Grady if you talk to Jim and you talk to Ivar how they would apply I it is actually looks a lot like the way that I would develop but doesn't matter what you would do. What matters is what the people who read the stuff that you write would do. And it was being used in a very waterfall style. Bunch of analysis, bunch of design, bunch of implementation, separate testing, disaster over and over and over again.

</details>

**Speaker B**: 所以我们这群人看着这种情况，各自以自己的方式、在自己的时间线上表达了：“不，我们不应该这样做。我们应该采用另一种方式。” 我们开始发出足够大的声音，以至于开始受到那些支持“统一软件开发过程”的人的攻击。他们会说：“嗯，你不想那么做。你想做我的那一套，来，我卖给你价值几百万美元的工具来帮你做。” 我完全能理解他们为什么要攻击。但我们开始意识到，好吧，如果我们在朝着类似的方向前进，比如 Scrum 或者特征驱动开发（Feature-driven development），我们就必须团结起来。

<details>
<summary>Original English</summary>

**Speaker B**: So a bunch of us looked at that and in our own ways, in our own sequence of time said, "No, we we shouldn't do this. We should do something else." And we started making enough noise that we started getting attacked by the rational unified process people. Well, you don't want to do that. You want to do my thing and here I'll sell you tool for millions of dollars to help you do it. I I can understand why they would attack. But we started realizing, okay, if we're all going in this similar kind of directions, scrum, feature-driven development, we had to come together.

</details>

### 挪威会议与寻求共识

**Speaker B**: 我们在挪威开了一次会，大家聚在一起，做了一个展示。那大约是我在欧洲生活的后期。我在瑞士住了两年，97年和99年。所以在99年，我们飞到挪威的最北端，然后搭乘了那艘叫 Guten Berry 的游轮——我之前还练习过这个词的发音，不过我确定我现在肯定还是念错了。我们乘这艘渡轮南下去了卑尔根（Bergen），那里一整天或者说一整夜天都是亮的。这绝对是一项人生遗愿清单级别的体验。如果有机会你一定要去看看，因为那里的风景简直太壮观了。

<details>
<summary>Original English</summary>

**Speaker B**: We had a meeting in Norway where we got together, gave a presentation. This is towards the end of the time I was living in Europe. I lived in Switzerland for two years, 97 and 99. So in 99 we we flew up to the tip of Norway and took the Guten Berry, which I practiced saying, and I'm sure I still butchered it. Took this ferry down to Bergen and it was light all day or all night. Bucket list item. Definitely take this if you ever get a chance because the scenery is just absolutely spectacular.

</details>

**Speaker B**: 但是当时我们聚会讨论的主题是，我们是否有足够的共同点可以让我们真正一起做点什么。那次会议传递出的感觉是：“是的，我们应该一起做点什么，但是依然存在很多摩擦，也有很多分歧。” 你要知道，我们讨论的是一群有着相当健康自尊心的人……

<details>
<summary>Original English</summary>

**Speaker B**: But we were meeting and talking about do do we have enough in common that we could actually do stuff together. The sense of that meeting was yes, we should do something together, but there's still a lot of friction and there's a lot of divergence. You're talking about people with some healthy egos,

</details>

**Speaker A**: 有着强烈的个人主见。

<details>
<summary>Original English</summary>

**Speaker A**: strong opinions.

</details>

**Speaker B**: 而我，绝对是其中主见最强的人之一。所以，呃，当我们回来之后，Jim Highsmith 和 Alistair Cockburn 在雪鸟滑雪场（Snowbird）又召集了一次会议，也就是我们之前举办这类关于方法论会议的老地方。所以我们都去了那里。至于会议的细节，其他人已经讲述过了，我自己没法那么准确地回忆起那些细节，所以你可以去找找其他人对这部分的回忆记录。但当时对于我个人来说，情况很糟糕。我得了严重的鼻窦炎，正在服用一些药效很强的药物。所以我对这次会议的大致情况真的记不太清了。但我知道情况进行得不太顺利，因为这里有这么多人，他们都在想：“我希望把我的东西加进去。”“不，我希望把我的加进去，而且那和你的内容是冲突的。” 所以我们大家就先休息了一下。我们走了出去，而 Martin 和 Jim Highsmith 留了下来。当我们在休息结束后回来时，宣言的雏形就已经在那儿了。你知道的，就是那个广为人知的格式：“我们重视这些，但我们更重视那些。”

<details>
<summary>Original English</summary>

**Speaker B**: Me, not the smallest among them. So, uh, when we got back, Jim Highsmith and Alistair Cockburn, uh, convened another meeting at at Snowbird, same place that we'd been having these kind of methodology kind of meetings for a while. And so, we all went there and um, other people have told the details of the meeting. I'm not going to be able to recall them precisely enough. So find one of those uh recountings of this, but it was not going well for me personally. I had a nasty sinus infection and I was on some heavy duty drugs. So I don't really remember much of the meeting in general, but I knew that things weren't going very well because there's all these people and they I want my stuff in. No, I want my stuff in and that contradicts your stuff. And so we all we took a break. We walked out and Martin and Jim Highsmith stayed behind. When we came in from the break, there was the basics of the manifesto. You know, we the the that format. We value these things, but we value these things more.

</details>

**Speaker B**: 里面那四个具体的价值观条目，当时都已经确立好了。那就是一个神奇的时刻，但我其实完全没有参与其中。然后我们又一起想出了那些原则。我记得，在那里面唯一属于我的一个词就是“每天”（daily），就是在提到要与用户进行每天的互动那个地方。除了这个，我不觉得里面还有什么是我加进去的。不过，当到了要发布它的时候，这些名字应该怎么排序呢？像是按字母表顺序排？

<details>
<summary>Original English</summary>

**Speaker B**: And the four specific items that was that was all in place. And then the and that was just a magic moment that I had nothing to do with. And then we came up with the principles. And I remember the the only word in there that's mine is the word daily when it talks about daily interaction with users. I don't think I had another thing in there. But when it came time to publish it, what order the names go? Like alphabetical

</details>

**Speaker A**: 完完全全是按字母表顺序。

<details>
<summary>Original English</summary>

**Speaker A**: al absolutely alphabetical.

</details>

**Speaker B**: 对，所以当人们说：“哦，你是签署人之一”，因为他们知道我是按字母顺序排在第一个的签署人。

<details>
<summary>Original English</summary>

**Speaker B**: So So when when people say, "Oh, you're a signator." as they know I'm the first signatory alphabetically.

</details>

### 敏捷宣言的影响与 JUnit 的故事

**Speaker A**: 那么《敏捷宣言》产生的影响是什么呢？

<details>
<summary>Original English</summary>

**Speaker A**: And then what was the impact of the agile manifesto?

</details>

**Speaker B**: 哦，几乎是立竿见影，人们立刻就变得非常兴奋。当时正是互联网泡沫（dotbomb.com）即将破裂发出隆隆声响的时候。但当时一切还在往上走。

<details>
<summary>Original English</summary>

**Speaker B**: Oh, in instant instant people were so excited again were now the rumblings of the dotbomb.com. It it was still going up.

</details>

**Speaker A**: 我觉得是。

<details>
<summary>Original English</summary>

**Speaker A**: I I think so

</details>

**Speaker B**: 那是临近泡沫尾声的时候了。

<details>
<summary>Original English</summary>

**Speaker B**: it was towards the end

</details>

**Speaker A**: 确实是临近尾声，但是人们仍然在寻找，比如我们该怎么做？我们该如何处理这些事情？怎样才能快速、便宜、可靠地构建软件。每个人都在寻找一种具有可选性的方法……

<details>
<summary>Original English</summary>

**Speaker A**: but definitely towards the end like but people were still looking for a like how do we do this? How do we do this stuff? How to build software quickly, cheap, reliably. Everyone's searching for the optional

</details>

**Speaker B**: 具有可选性。

<details>
<summary>Original English</summary>

**Speaker B**: with with optionality.

</details>

**Speaker A**: 具有可选性，没错。

<details>
<summary>Original English</summary>

**Speaker A**: With optionality. Yeah.

</details>

**Speaker B**: 因为当事情充满不确定性时，恰好就是选择权能给你带来最大价值的时候，而我们有一个关于你如何能够保留这种可选性的故事。我们所有人都是以各自不同的方式来实现这一点的。那是另外一个案例了。当时 XP（极限编程）是我第一次经历有人扯着我的衬衫要求了解的情况。而 JUnit 是另一个，在那之前它是 SUnit。我当时开发了 SUnit。而 Erich Gamma 当时正在使用一门名为 Java 的新语言。我们在飞往美国的航班上。他准备向我展示 Java，而我准备向他展示 SUnit。结果，在从维也纳飞往华盛顿杜勒斯机场的航班上，我们自己开发了最初的用于测试 Java 代码的 JUnit 测试框架。

<details>
<summary>Original English</summary>

**Speaker B**: Because when things are uncertain is exactly when options give you the most value and we had a story about how you could preserve optionality. All of us in in our own separate ways. That was another case. So XP was the first time I had people tugging on my shirt. JUnit was another one which was SUnit. I had SUnit. Eric was using Eric Gamma was using this new language Java. We were flying to America. He was going to show me Java. I was going to show him SUnit. So we developed JUnit testing itself in itself on the flight from Vienna to Washington Dulles.

</details>

**Speaker A**: 哇哦。

<details>
<summary>Original English</summary>

**Speaker A**: Wow.

</details>

**Speaker B**: 然后当我们降落的时候……

<details>
<summary>Original English</summary>

**Speaker B**: And when we landed

</details>

**Speaker A**: 在飞机上，完全没有网络。没有网络。

<details>
<summary>Original English</summary>

**Speaker A**: on the plane, no internet. No internet.

</details>

**Speaker B**: 电池只能撑两个半小时。时间真的在滴答作响。

<details>
<summary>Original English</summary>

**Speaker B**: Two and a half hours of battery. Like the clock is ticking.

</details>

**Speaker A**: 是的。而且座位上也没有电源适配器。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And no power adapter in the seat.

</details>

**Speaker B**: 哦，那感觉就像是在用马拉的设备进行计算一样。所以我们降落后，在 OOPSLA 会议上，我们把 JUnit 交给了 Martin Fowler。结果第二天，我就听到有人说：“听说你们有个 Java 测试框架。能给我一份拷贝吗？”于是我们就把那些 3.5 英寸的软盘做成了拷贝，以我们最快的速度把它们分发出去，因为大家对它的需求实在是太大了。这是我第二次经历那种市场对产品有极度需求、即所谓的产品市场契合（product market fit）的狂热情况。

<details>
<summary>Original English</summary>

**Speaker B**: Oh, it was it was like a horsedriven computing. So we landed and and we gave Jayun to Fowler who was at at that oops and um the next day I hear you have a Java testing framework. Can I get a copy? So we made floppy discs, 3 and 12 in discets and and we were handing them out as fast as we could cuz there was so much demand for it. So that was the second time I've been through that kind of a demand product market fit column

</details>

**Speaker A**: 对。没错。确实是产品市场契合。然后，《敏捷宣言》就是这种现象的下一个版本，人们对它真的感到非常兴奋。能够拥有那些最初的签署人，这是一次非常漂亮的营销，而且后来如果你想去签名……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Yeah. Exactly. Product market fit. Um and then agile manifesto was the the next version of that where people were just really excited about it. beautiful piece of marketing to have the original signitories and then if you wanted to sign it,

</details>

**Speaker B**: 你在一段时间内确实是可以去签名的。我想他们后来把它关闭了，因为去签名的人实在太多了，对吧？但这意味着人们觉得自己投入进去了。他们已经买账了。他们已经把自己的名字和这个宣言绑定在了一起。

<details>
<summary>Original English</summary>

**Speaker B**: you could sign it for for a while. I think they closed it after a while because it got too many people, right? But that meant that pe people felt invested. They were already bought in. They'd already attached their names to this thing.

</details>

**Speaker A**: 这是不是很耐人寻味，你懂的，人们一旦投入，或者能够去贡献、能够感觉到自己在做出贡献，这就能带来改变。它确实带来了改变，而且对于敏捷来说毫无疑问是这样的。

<details>
<summary>Original English</summary>

**Speaker A**: Is it interesting, right, how being invested, being able to contribute or feel you're contributing, it it can make a difference. It it has made a difference and and for agile for sure.

</details>

### “敏捷”一词的争议及行业现状

**Speaker B**: 所以关于此，后续要说的一点是，“敏捷（agile）”这个词，其实是我们当时争论的一部分。我们争论的焦点是我们到底要给这东西起个什么名字，然后有人建议了“敏捷”，我不记得是谁了，但肯定是某个人建议的。当时我提出了反对，我不喜欢这个词的原因——无论是当时还是现在我都不喜欢它——是因为这个词是无法被防御（not defensible）的。没有人会说：“我不敏捷”。“哦不，我更喜欢僵化的开发。”“哦，我更喜欢死板的开发。” 不会的，每个人都会宣称自己是敏捷的，而“极限（extreme）”这个词就没有这个问题。如果你在自己的技能上下苦功，去努力掌握结对编程，掌握增量设计，掌握彻底测试以及构建工具的能力，只要你做出了这些投入，你现在就可以说：“好的，我是一名极限程序员。” 如果你没有付出那些努力，如果你不是，你就永远不会自称是一名极限程序员。但是，即使你绝对不敏捷，你也会宣称自己是敏捷的。所以这就是我当时的反对意见，而事实证明这种担忧确实应验了。这个词现在不仅变得毫无意义，它甚至还带上了一些负面的含义。

<details>
<summary>Original English</summary>

**Speaker B**: So uh one piece of followup is that word agile part of the ar argument argument yeah argument was around what are we going to call this thing and somebody suggested agile I don't remember who but probably somebody somebody does and I objected and what I don't like about it I didn't like about it then and still don't like about it is it's not defensible. Nobody's going to say I'm not agile. Oh no, I prefer rigid development. Oh, I prefer inflexible development. No, everybody's going to say that they're agile, which extreme doesn't have that problem. If you work hard at your skills at being able to pair and being able to design incrementally and being able to test thoroughly and and build tools and you make that investment now you say, "Okay, I'm an extreme programmer." If you haven't made that investment, you're never going to say that you're an extreme programmer if you're not. But you're going to say you're agile even if you're definitely not. So that was my objection back then and and that certainly played out. That word does not only doesn't mean anything anymore, it means something negative.

</details>

**Speaker A**: 好的。我们能谈谈敏捷的后续发展吗？也就是那些大写字母“A”开头的“Agile”版本。现在已经发展出了一个完整的产业链，它最初本意是好的，但在很多方面却变成了一个贩卖“万灵药”的行业。我们现在看到有些规模化敏捷框架被高价卖给那些大企业，正如你所知，这让它们陷入了比你能想象的还要多的官僚主义泥潭。你是怎么看待这种演变的？你当时有没有预料到敏捷会发展得如此庞大，成为一个商业故事，并且滋生出所有这些贩卖“万灵药”的环节？

<details>
<summary>Original English</summary>

**Speaker A**: Okay. Can we talk about that of the afterlife of of agile and and some of the the capital, you know, the capital A version, there's a whole uh industry that was grown that initially was meant to do good things, but it turned into a snake oil industry in in many ways. We now have scaled agile frameworks that are sold for massive amounts for huge companies which you know bog them down with even more bureaucracy you can imagine. How did you see this being played out and did you expect agile to to grow this big into both a commercial story and and and and then all all of these I guess snake oily parts?

</details>

**Speaker B**: 在我们将它整理出来的时候，我确实很担心会发生这样的事情。《敏捷宣言》仅仅是当时那个房间里的人们各种思想的一个交集而已。我认为在软件开发中，还有很多其他更深层的东西。

<details>
<summary>Original English</summary>

**Speaker B**: I was certainly afraid that that was going to happen at the time that we put it together. The agile manifesto is the intersection of the ideas of the people in the room. I think there's a lot more to software development

</details>

<!-- chunk 11/16 -->

### 技术基本功与行业泡沫

**Speaker A**: ……这比《敏捷宣言》里包含的内容要多。关于我认为这些东西到底是什么，我已经写了一本又一本的书。如果没有技术基本功作为基础，你可能有最好的意图，比如“我们将能够重新计划”、“我们能够以任何顺序实现”、“我们有一组功能，可以以任何顺序实现它们”、“我们可以随时随地添加新功能”。你可以说你要这么做，但如果你没有技术能力去高效地、零散地编写出可靠的软件，去零散地进行设计以保持并增强可选择性，在需要的时候去编写你自己的工具——这些事情在技术上都是很困难的。这就好比把一个第一次滑雪的人放在雪崩的山顶上。好吧，当你滚下山崖摔得粉身碎骨时，确实有一种所谓的“敏捷”，但这真的不是我们在讨论的东西。你需要那样的基本功。曾经有些人愿意说：“不，不，不，别担心那个。这很容易。你能做到，任何人都能做到。用一半的时间完成两倍的工作。”在我看来，那纯粹是谎言。你能用一半的时间完成两倍的工作吗？是的，绝对可以。但是否需要通过大量的艰苦工作来掌握这些技能？这些技能在计算机科学的学校里是不教的，在你的第一家雇主那里通常也没有人给你做榜样。你将不得不拼命努力，获得这些技能，才能用一半的时间完成两倍的工作。现在这个生成式 AI 的世界只是把这个过程重新上演了一遍。好吧，“每个人都能成为程序员。”是的，但并非每个人都能成为一样的程序员。

<details>
<summary>Original English</summary>

**Speaker A**: ...than is contained in the manifesto. And I've written books and books and books about what I think those things are. Without the foundation of technical skills, you can have the the best intentions of we're going to be able to replan and we're going to be able to implement in any or you know we have a set of features and we can implement them in any order and we can add new features anytime we want and you can say you're going to do that but if you don't have the technical chops to write efficiently write reliable software in bits and pieces to design in bits and pieces to preserve and enhance optionality to write your own tools when you need to do that. Those are things are technically difficult. It's it's like putting somebody at the top of the avalanche on a snowboard for the first time. Well, there's a certain kind of agility as you fall down the mountain and break your body into multiple parts, but this is not really what we're talking about. You need that foundation. And there were people who were willing to say, "Nah, no, no, don't worry about that. This is easy. You can do this. Anybody can do this. Twice the work in half the time." From my perspective, that's just a lie. Can you get twice the work done in half the time? Yes, absolutely. Is it going to be a lot of hard work gaining the skills, which aren't taught in computer science school, aren't frequently modeled in your first employer? You're going to have to work hard to gain the skills to be able to do twice the work in half the time. In the the genie world is just playing this out again. Well, everybody can be a programmer. Yeah, but everybody can't be the same programmer.

</details>

**Speaker B**: 是的，似乎有这样一个模式：当出现一项新技术，或者在当前情况下是一种新方法时——不过我想这可以与“技术”互换。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, seems like there's a pattern where when there is a new technology or a new methodology in this case, but I guess it's interchangeable >> technology. Yeah.

</details>

**Speaker A**: 是的，这是一种技术，一群人、一群受过高度训练的人能够用它获得非常好的结果，然后他们把它发表出来分享：“这对我们很有效，这是结果。”接着周围就会出现一个更大的产业，他们会像你刚才说的那样宣称：“任何人都能得到这些结果，我们会把它卖给你，我们会展示给你看。”当然，等到你意识到这一点时，比如一家大银行意识到这其实并不奏效时，他们已经投入了巨资，也许他们确实得到了一些微小的结果，只是不是预期的那样。然后我想你可能会争辩说，这正是“万金油”（骗局）的本质，对吧？就像万金油，它确实有点作用，只是并非广告宣传的那样。

<details>
<summary>Original English</summary>

**Speaker A**: >> Well, it's a technology that a group of people, a group of highly trained people can get really good results with it and then they publish it and they share this is working for us. Here's the results. There's a bigger industry going around that's saying what you just said that anyone can get these results and we will sell it to you. We'll show it to you. And of course, by the time you realize that, for example, a company like a large bank realizes that it's not really working. They're heavily invested and maybe they're actually getting some minor results, just not the same. And then I guess you can argue of like this is this is the whole point of snake oil, right? Like snake oil, it does something just not what it was advertised.

</details>

### 互联网泡沫破裂与9/11的冲击

**Speaker B**: 让我们谈谈 2001 年之后发生了什么。所以，呃，当时出现了一次大萧条（dot-com bust）。你能带我们回顾一下置身其中的感受吗？所以当时你是在硅谷吗？

<details>
<summary>Original English</summary>

**Speaker B**: Let's talk about what happened after 2001. So, uh there was a big do bus. Can you take us back to what it was like being in the middle? So you were in were you in Silicon Valley at that point?

</details>

**Speaker A**: 87 年到 97 年，我们住在硅谷上方的圣克鲁斯山脉。那段时间的大部分日子里，我都是通勤上班。然后我们在 97 年到 99 年搬到了瑞士。在我们住在圣克鲁斯山脉的博尔德克里克（Boulder Creek）的后期，我们在俄勒冈州南部靠近我祖母的地方买了一块地。所以我们买了 8 公顷全是树的地，开始铺设电力、打井、修路等等。去了瑞士。哦，我们建了办公室，还有一个拖车房，然后我们就去了瑞士，后来又回来了。所以那时候我住在俄勒冈州南部的乡下。

<details>
<summary>Original English</summary>

**Speaker A**: >> 87 to 97 we lived in the Santa Cruz Mountains above Silicon Valley. Much of that time I commuted to work. Then we moved to Switzerland 97 to 99. Then in the last part of when we were living in uh in Boulder Creek in the Santa Cruz Mountains, we had bought acreage near my grandmother in southern Oregon. So we bought eight hectares of just trees and started developing power well road and so on. Went to Switzerland. Oh, we built the office and we had a trailer and then we went to Switzerland and we came back. So I was living in rural southern Oregon at that time

</details>

**Speaker B**: 整个行业刚刚经历了一次巨大的繁荣，正如我现在和从事 AI 的人们交谈时感觉到的，这与当前 AI 领域的繁荣有很多相似之处。紧接着就出现了突然的萧条，我也是从历史书或者翻阅以前的新闻里了解到这些的。但显然它来得非常突然，非常令人震惊。你是如何看待它的？行业内发生了什么？你那些做程序员的朋友们观察到了什么，或者他们受到了怎样的影响？

<details>
<summary>Original English</summary>

**Speaker B**: >> and the industry just went through this massive boom which there are similarities as as I'm talking with people with the current uh boom whenever you're working in AI right now and then there was a sudden bust that again I I've I've learned it from the the his history books or like reading back news but apparently it was sudden uh it was shocking uh how did you see it what what happened in the industry But what what were your friends working as programmers observe or how were they impacted?

</details>

**Speaker A**: 对我个人而言那太可怕了。转折点是 9/11。我当时已经排满了 8 个月的确切工作，而且费率非常高，甚至比我现在能收取的费率还要高，即便算上通货膨胀。然而在 9/11 的第二天，所有人都取消了订单。我当时还在完成我们正在建造的房子。所以，我们马上就要面临一笔巨额账单来把房子建完，而就在同一时间，我的所有收入都消失了。就在一夜之间。

<details>
<summary>Original English</summary>

**Speaker A**: >> It was horrible for me personally. The turning point was 9/11. I had 8 months booked solid work at very high rates, higher rates than I can charge now, even with inflation. And the day after 9/11, everyone canled. I was also finishing the house that we were building. So, we were we were about to come up on some big bills to finish the house at the same time that all of my income disappeared. It's overnight.

</details>

**Speaker B**: 一夜之间。哇哦。

<details>
<summary>Original English</summary>

**Speaker B**: >> Overnight. Wow.

</details>

**Speaker A**: 所以，在此之前情况就已经很糟了。发生了大规模的破产，pets.com 和其他类似的公司，那些事情已经在那时发生了。然后 9/11 直接让一切停摆。那对我来说是一个巨大的打击，结果就是我彻底崩溃了。严重的抑郁。关于“边界”，我学到了非常重要的一课。在那个时候之前，记得吗，经常会有人扯着我的衬衫找我，而且是的，你遇到了三次非常巨大的市场契合（product-market fits），人们都在追捧你。

<details>
<summary>Original English</summary>

**Speaker A**: >> So, things had already been bad. There were there were big bankruptcies and the the pets.com and the whatever that that was already happening. And then 9/11 just shut down everything. That was a big shock for me and I ended up burning out um pretty thoroughly. Severe depression. I had a really important lesson to learn about boundaries. So up until that time, remember periodically I had people tugging on my shirt and yeah, you had three really big part of market fits where people were after you.

</details>

**Speaker B**: 甚至在那之前的模式也是那样的。但你是个明星。

<details>
<summary>Original English</summary>

**Speaker B**: >> Patterns even before that was also like that. >> But you were a star.

</details>

### 名声与心理重建

**Speaker A**: 是的，我当时也有这种感觉。我会收到这样的信息，有人会说：“哦，JUnit 救了我的命。XP 太棒了，我爱死它了，你是个天才，吧啦吧啦吧啦。”看到这样的信息我感觉非常好。然后我开始收到另外一些信息：“呃，XP 毁了我的生活。我失去了工作，我的妻子离开了我，我见不到我的孩子了，我流落街头。”接着我就会感觉非常糟糕。我现在对这件事的想法是：人们对你的认知是一回事，你对自己的认知是另一回事，然后真实的情况又是另外一回事，真实往往与前两者都不一样。当人们给你一大堆反馈，说你比你自认为的还要棒时，那只会让你的自我膨胀。所以你会周期性地在名人身上看到这种情况：某个人非常出名，然后他们的脑袋就“爆炸”了，这就是人们看待你的方式和你自己看待自己的方式之间的落差。我必须学到的是：人们带着那些不成比例的反应来找我，原因在于那正是他们所需要的。他们需要一个英雄，或者他们需要一个反派；而他们对英雄或反派的需求与我毫无关系。如果不是我，他们也会去联系你，他们会去联系别人。这真的不关我的事。但是……但是那种重新校准，就像，我一直在试图说服自己我真的有这么厉害，不，我收到反馈说我并没有。对我来说，那是一次……非常严肃的重置。所以我经历了一系列心理健康问题，没法工作，完全没法编程。我不得不从数独（Sudoku）重新开始，最终我能解开简单的数独，再后来能解开中等难度的，接着我开始玩填字游戏。哦哇。再后来，我终于遇到了一个编程问题。当时我在用 Eclipse 做一些东西，那时它还是个新软件。我遇到了一个编程问题，我完美地解决了他，然后我想：“哦，这依然很有趣。我还是能做这件事。”呃，但是是的，从比如说 2002 年，一直到 2011 年我加入 Facebook，这期间算是“迷失的十年”。

<details>
<summary>Original English</summary>

**Speaker A**: I was Yeah, I was feeling Yeah. And I would get these messages. Somebody would say, "Oh, Junit saved my life. XP was fantastic and I love it and you're a genius and blah blah blah." And I'd feel really good knowing a message like that. Then I started getting messages, uh, XP ruined my life. I lost my job. My wife left me. I can't see my kids. I'm living on the streets. You M and then I would feel really bad. And the way I think about it now is that there's the way people perceive you and there's the way you perceive yourself and then there's what's really true, which is somewhere different than either of those. When people are giving you a bunch of feedback that you're more awesome than you think you are, that just stretches your head. So you see this in celebrities periodically. There'll be somebody super famous and then their their head explodes and that's that gap between how people see you and how you see yourself. And what I had to learn was the reason that people come to me with those out of proportion responses is because that's what they need. They need a hero or they need a villain. and their need for a hero or a villain has nothing to do with me. If it wasn't me, they'd be contacting you. They'd be contacting somebody else. It really doesn't have anything to to do about me. But but that recalibration where I'm like, I'm trying to convince myself that I really am this awesome. No, I I get feedback that I'm not. That was a a a serious reset for me. So, I went through a bunch of mental health problems, couldn't work, c couldn't uh couldn't program at all. I had I started over with Sudoku and eventually I could do sudokus on easy and then eventually I could do them on medium and then I started on on uh uh crossword puzzles. Wow. And then eventually I got to a programming problem. I was doing a bunch of stuff with Eclipse when it was new. I got to a programming problem and I I nailed it and I went, "Oh, this is still fun. I can still do this." Uh but yeah, the kind of a lost decade from 2002, let's say, to to 2011 when I joined Facebook.

</details>

**Speaker B**: 所以你真的经历了从……可以说接近整个行业或职业巅峰的“山顶”，跌落到只是试图去寻找自己出路的过程。

<details>
<summary>Original English</summary>

**Speaker B**: So it you really went from being on close to the peak of of of the industry or the professional, you know, like mountain if if if you will to just I guess just finding your way.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yep.

</details>

**Speaker B**: 你觉得如果不是因为这场突如其来的崩盘，或者没有这种骤然的打击，类似的事情也会发生吗？还是仅仅是因为当时一切瞬间从你脚下被抽离的强烈冲击所致？你觉得真正的原因是什么？

<details>
<summary>Original English</summary>

**Speaker B**: Do you think something similar might have happened? Was it not for this sudden crash or being a this sudden or or was it just the intensity of of of everything just being pulled under out of under your feet? What do you think it was?

</details>

**Speaker A**: 我觉得人们带着这些我自己清楚无法满足的期望来找我，这件事最终肯定会以某种方式爆炸。你不可能余生都那样活着。其实这就是典型的“中年危机”。就是你那些曾经起作用的、或者感觉好像曾经起作用的面具，你意识到，哦，它们在未来不会再起作用了。我必须做回我自己。而且事实上，它们从来没有起过作用。我只是在骗自己以为它们起作用了。是的，我认为这迟早要发生。有人说是在 35 岁，40 岁或者 45 岁，而我的危机发生在了 42 岁。

<details>
<summary>Original English</summary>

**Speaker A**: I think that people are coming to me with these expectations that I know I can't meet that it's going to blow up somehow eventually for sure. You can't just live the rest of your life like that. Then that's what the classic midlife crisis is. Is the masks that used to work that felt like they used to work. You realize, oh, they're not going to work going forward. I have to be myself. And actually, they've never worked. I was just fooling myself that they had worked. Yeah, I think that's it's going to come. It said 35 or 40 or 45 and mine was at 42.

</details>

**Speaker B**: 但后来在 2011 年，你加入了 Facebook。我对这个故事非常感兴趣，因为当时 Facebook 才成立 7 年，这意味着公司的中位数年龄大概只有 24 岁，而你以一个行业传奇的身份再次出现。你已经做出了所有这些贡献：TDD、XP、知道如何构建……

<details>
<summary>Original English</summary>

**Speaker B**: But then you in 2011, you got into Facebook. And I'm really intrigued by this story because at this time Facebook was uh 7 years old which meant that the median age was probably like 24 at the company and there you are an industry legend again. You you've you've had all all these contributions TDDXP knowing how to build

</details>

<!-- chunk 12/16 -->

### Facebook 的开发模式与反馈机制

**Interviewer**: Facebook 正在以一种截然不同的方式构建高效的软件，而你 50 岁的时候出现在那里，和那些只有你一半岁数的人共事。我猜你本可以回去继续做咨询，继续做你以前做过的事情。

<details>
<summary>Original English</summary>

**Interviewer**: Facebook is building efficient software in a different way and now you're showing up when you were 50 with these people half your age. I assume you could have gone back to consulting and do what you've done before.

</details>

**Kent Beck**: 我当时确实想做同样的事情。为了生活我肯定需要赚钱，所以我想继续做我以前做过的咨询工作，但外界根本没有任何兴趣，完全是零。我还有孩子们的大学学费要付。我有五个孩子，我知道我将连续四年要支付两份大学学费。所以我需要一些稳定性和收入。出版书籍的问题在于赚不到多少钱。

<details>
<summary>Original English</summary>

**Kent Beck**: I was trying to do the same thing. So I needed the money for sure trying to do the same things as a consultant that I'd done before and just there was no zero interest out there. I had college to pay for. I have five kids and I knew I was going to have two tuitions for four years in a row. I needed some stability and income. Problem with book publishing doesn't make much money.

</details>

**Interviewer**: 是的。除非对于个别人来说是罕见的例外。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Except in a rare cases for a guy.

</details>

**Kent Beck**: 嗯，在极少数情况下，就我的情况而言，由于亚马逊自助出版的出现。而且人们会大量购买你的书。但除此之外，即使是……是的。确实不赚钱。

<details>
<summary>Original English</summary>

**Kent Beck**: Well, in the rare cases in my case where Amazon self-publishing has been invented. And people buy your books in bulk. But outside of that, even for uh Yeah. It doesn't.

</details>

**Interviewer**: 是的，我喜欢调侃你，因为你是如此成功。我知道，即使你受不了，你也得受着。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. I love teasing you because you're so successful. I know that even if you can't take it, you have to take it.

</details>

**Kent Beck**: 我在这里只能受着 [笑声]，在这个播客里只能受着。所以第一我需要一些稳定性，但第二，这些人做的根本不是我书里写的内容，但他们却在运营一个稳定的网站。它并不完美，但在这种疯狂的规模下，它是稳定的，并且可以说是史无前例的。他们正在扩张。用户和增长都在急剧扩张，而且他们同时还在进行创新。所以，地球上怎么可能有人能做到这点？

<details>
<summary>Original English</summary>

**Kent Beck**: I have to take [laughter] it here and then here on this podcast. So I needed some stability number one, but number two, these people were doing nothing that was in my books and they were running a stable site. It's not perfect, but at this crazy scale, it was stable and kind of unprecedented. They were expanding. Users and growth was expanding dramatically and they were innovating all at the same time. So, how in the world...

</details>

**Interviewer**: 而你正是写了那本书的人。

<details>
<summary>Original English</summary>

**Interviewer**: you wrote the book

</details>

**Kent Beck**: 我写了那本书，你知道，我发明了这些东西。而且他们显然需要它，我能看出来，因为没有人在做这些。那时候几乎没有单元测试，这让我非常震惊。这怎么可能呢？所以我说：“我在报名表上加上了由 Kent Beck 亲自授课的 TDD（测试驱动开发）课程。” 就在我的课之前是一节阿根廷探戈课，在我的课之后是一节高级 Excel 技巧课。当上课时间到了的时候，阿根廷探戈课爆满，高级 Excel 课也爆满，而根本没有人，一个都没有，甚至连出于同情报名的都没有。完全没有人在我的 TDD 课程上报名。所以，这些工程师显然觉得自己已经完全掌握了诀窍，他们不需要从这个老家伙那里学任何东西。于是我决定，你知道吗？我干脆忘掉我认为我所知道的关于软件工程的一切，然后去尝试做事情。我就像“有样学样”那样，去模仿我看到别人在做的事情，然后获得反馈，看看我是否能足够快地学会在这种不同的风格下进行开发。我能快到重新学习软件工程而不被解雇吗？结果我在那里呆了七年。

<details>
<summary>Original English</summary>

**Kent Beck**: I wrote the book I invent you know blah blah blah and they clearly need it I could see because nobody's doing it very few unit tests at that time um which just shocked me how can this be so I said, "I put on the signup sheet TDD class for me from the Kent Beck." Just before my class was one on Argentinian tango and just after my class was one on advanced Excel techniques. When the time came for the classes, the Argentinian Tango class was full, the advanced Excel class was full, and no one, not one, not even like a pity signup. Zero people had signed up for my TDD class. So, these engineers clearly felt like they had it already dialed in and they didn't need anything from this old guy. So, I decided, you know what? I'm just going to forget everything that I think I know about software engineering and I'm gonna try to do things. I'm just sort of monkey see monkey do. I'm going to copy what I see people doing and get feedback and see if I can learn to develop in this different style as quickly enough. Can I relearn software engineering fast enough not to get fired? And I ended up staying there for seven years.

</details>

### 多层反馈系统与代码回滚

**Interviewer**: 那你学到了什么？是什么让这种模式运转起来的？因为，再回到那个时候，Facebook 在外界看来所做的事情是毫无道理的。他们当时没有测试。他们却在运行这个庞大的网站，不知怎么地保持着它的运转。哦，而且他们还聘用了一些年轻的工程师，这些工程师并没有一二十年的经验来知道该避免哪些错误。

<details>
<summary>Original English</summary>

**Interviewer**: And what did you learn? What made it work? Because again, going back there, what Facebook did from the outside would have made no sense. They didn't have tests at the time. They were running this massive site somehow keeping it working. Oh, and they had young engineers who didn't have a decade or two of experience to know what mistakes to avoid.

</details>

**Kent Beck**: 主要是年轻的工程师。

<details>
<summary>Original English</summary>

**Kent Beck**: Mostly young engineers.

</details>

**Interviewer**: 主要是。

<details>
<summary>Original English</summary>

**Interviewer**: Mostly. 

</details>

**Kent Beck**: 所以，我们有一些具备出色领导能力、非常资深的人。

<details>
<summary>Original English</summary>

**Kent Beck**: So, we had some very senior people with great leadership skills.

</details>

**Interviewer**: 没错。

<details>
<summary>Original English</summary>

**Interviewer**: Aha.

</details>

**Kent Beck**: 他们可以起到模范作用。系统内部建立了很多层的反馈机制。我们有运行网站的开发机。所以如果你想把颜色从蓝色改成绿色，你可以在你的开发机上完成。

<details>
<summary>Original English</summary>

**Kent Beck**: uh who could model it. Many layers of feedback were built into the system. So we had developer machines that ran the site. So if you wanted to change the color from blue to green, you could do it on your developer machine.

</details>

**Interviewer**: 你可以在那里检出代码，那是一个类似于 Monorepo（单体代码库）的东西。

<details>
<summary>Original English</summary>

**Interviewer**: You could check out there was a mono repoish thing.

</details>

**Kent Beck**: 是的。所以你可以更改任何东西并看到结果，因为那是 PHP，你可以在几秒钟内看到更改的结果。这就给了你第一层的反馈。然后你有代码审查，这给了你另一层的反馈。你可以更频繁地在内部推出更新。并且每个人都在用 Facebook 处理各种事情，包括个人和内部业务。所以无论你开发了什么功能，人们都会立即开始使用。这样你又获得了一轮反馈。然后我们有这个分阶段的发布流程，你开始逐步推出你的功能。如果出现问题，影响范围将被限制在几百万人。而不是……

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah. And so you could just change anything and see the results because it was PHP, you could see the results of that change in seconds. So that gave you one level of feedback. Then you had code review which gave you another level of feedback. You could roll out internally more frequently. And everybody was using Facebook for all kinds of stuff, personal and internal business stuff. So whatever feature you developed, people would start using it immediately. So you get another round of feedback. Then we had this phased roll out process where you'd start rolling your stuff out. If there was a problem, the blast radius would be limited to a few million people. Not...

</details>

**Interviewer**: 比如基于信号的自动回滚。

<details>
<summary>Original English</summary>

**Interviewer**: like automatic roll back based on signals.

</details>

**Kent Beck**: 是的。而不是整个网站（清嗓子）。Chuck Rossi 的部署团队也是另一层反馈。你们都有星级评定。他们会秘密地给你评星星，如果你是三星级，他们看都不会看你的代码。但如果你是一星级，你的代码就根本推不上去。所以那又是一轮反馈。然后你部署代码并查看结果，就像那些早期的可观测性工具一样。所以你会得到关于你所做事情的更多反馈。所以反馈就像过滤器一样，一层一层地到来。如果你有足够多不同的反馈层……

<details>
<summary>Original English</summary>

**Kent Beck**: Yeah. Not the whole [clears throat] thing. Chuck Rossi's deployment team also was another level of feedback. You had stars. They would secretly give you a number of stars and if you were three stars, they wouldn't look at your stuff. But if you were a one star, you just couldn't get your stuff pushed. So that was another round of feedback. Then you deploy stuff and you'd look at the results like the observability early observability stuff. So you get more feedback about what you're doing. So feedback comes in layers like a filter. And if you get enough different layers,

</details>

**Interviewer**: 就像瑞士奶酪。

<details>
<summary>Original English</summary>

**Interviewer**: Swiss cheese,

</details>

**Kent Beck**: 没错，糟糕的东西会被挡住，而好东西依然会通过。是的。

<details>
<summary>Original English</summary>

**Kent Beck**: it's the bad stuff sticks and the good stuff still goes through. Yeah.

</details>

### 事件复盘与事故问责

**Interviewer**: 是的。所以这就是瑞士奶酪模型，即使到处都是洞……只要六层奶酪的洞没有排成一条线，那你就没事了，也许单元测试会更好。

<details>
<summary>Original English</summary>

**Interviewer**: So the Swiss cheese model even though there's holes everywhere as long as they don't line up for six layers of cheese then you're good and unit test would unit test been better maybe.

</details>

**Kent Beck**: 我为我推出的第一个功能写了单元测试，但我还是导致了一次网站事故，因为有一些我没有发现的其他耦合代码，导致了一次服务中断。

<details>
<summary>Original English</summary>

**Kent Beck**: I wrote unit test for the first feature I rolled out and I still caused a site event because there was some other coupled code that I didn't find meaning an outage.

</details>

**Interviewer**: 是的。是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yeah. Yeah.

</details>

**Kent Beck**: 虽然还没有严重到要进行事故复盘的地步，那是另一层的反馈机制，每个星期五最资深的人都会聚在一起，任何引起事故的人都会走进来解释：“这是发生事情的时间线，这是我们学到的教训，这是我们需要做些什么来避免这种事情再次发生。”如果你进入事故复盘并这样解释，你就会没事；如果你进入事故复盘并说：“哦，是运维做了这个，其他人做了那个，吧啦吧啦吧啦”，你可能真的会被直接解雇。那是另一层的反馈，确保相同的错误不会再次发生，而且这是被认真对待的。

<details>
<summary>Original English</summary>

**Kent Beck**: not a bad enough one to go through a incident review which is another layer of that where every Friday the most senior people would get together and anybody who'd caused an incident would come in and explain here's the timeline of what happened here's what we learned here's what we need to do to avoid this ever happening again and if you went into incident review and you explained it that way you were fine if you went into incident review and said well ops did this and somebody else did that and blah blah blah blah blah you could literally get walked to the door. That was another level of feedback that made sure that the same mistakes didn't happen again and that was taken seriously.

</details>

**Interviewer**: 我知道的，以及很多人都知道的是，Facebook 在很长一段时间里确实，对于大多数东西，他们都不做单元测试。事实上，我想如果有人试图推送代码，他们通常会在代码审查中直接把它删掉。这听起来本身就很糟糕，尤其是在那个时候，大概是 2010 年代初，测试被认为是绝对的最佳实践或基本要求，但我认为人们忽略的是所有这些大多数地方都没有的其他反馈层。据我了解，直到今天，Facebook 网站和移动应用的发布基础设施可能是世界上最先进的，在它如何自动收集信号以及如何进行自动发布和自动回滚方面，这在 99.9% 的公司中是根本不存在的，因为他们没有 Facebook 这样的规模或机会，甚至没有他们这样的业务，对吧？因为我猜，毕竟……自来水公司停水和 Facebook 宕机带来的影响是完全不同的。

<details>
<summary>Original English</summary>

**Interviewer**: What I know and what many people know is well Facebook for a long time did they did not do unit tests for most things. In fact, I think if someone tried to push they would often just delete it in code review. And you know that sounds bad in itself especially at a time this was the early 2010s where testing was considered really best practice or baseline but I think what people missed is all these other layers that most places did not have. My understanding is that to this date, Facebook the website and mobile apps rollout infrastructure is probably the most advanced in the world in how it automatically collects signals and it does the auto roll out and the auto rollbacks which just does not exist in 99.9% of places because they don't have their scale or their opportunities or even their business right because I guess you know outages are just it's a bit different when a utility company goes down versus when Facebook might go down the impact.

</details>

**Kent Beck**: 是的。而且当我在那里的时候，也就是到 2017 年我离开的时候，Facebook 已经成了一个与我刚加入时截然不同的地方。在最初的几年里，Facebook 变得更像……

<details>
<summary>Original English</summary>

**Kent Beck**: Yes. And while I was there, so by the time I left 2017, Facebook was a very different place than when I joined. Over the first couple of years, Facebook became much more like

</details>

<!-- chunk 13/16 -->

### Facebook早期工程文化与机会充沛期

**Guest**: 那时Facebook算是一种公共设施。那些大型的网站事件，或者重大的负面事故，有些著名的事故甚至会被命名。所以当时发生过一次叫做“召唤警察等级（Call of cops sev）”的事件，那是第一次在Facebook宕机时，人们竟然拨打了911报警电话。

<details>
<summary>Original English</summary>

**Guest**: a utility. The big site events, the big negative incidents, we the notable ones would get names. And so there was one called the call of cops sev and it was the first time that people called 911 when Facebook went down.

</details>

**Interviewer**: 哇哦。

<details>
<summary>Original English</summary>

**Interviewer**: >> Wow.

</details>

**Guest**: 感觉就像是，我的天啊，我们需要比以前更加严肃地对待这件事情。

<details>
<summary>Original English</summary>

**Guest**: It was like oh crap we need to take this even more seriously than we've been taking it.

</details>

**Interviewer**: 好的。

<details>
<summary>Original English</summary>

**Interviewer**: >> Okay.

</details>

**Interviewer**: 因为你们已经是社会基础设施了，人们理所当然地期望它能绝对正常运转。那么当时在Facebook内部是什么样的情况？工程文化是怎样的？相比于行业里的其他公司，工程师们是如何工作的？因为你当时处在这个运转方式截然不同的泡沫之中。

<details>
<summary>Original English</summary>

**Interviewer**: >> Because we're social infrastructure and people just expect it to absolutely work. And what was it like inside Facebook? How the engineering culture uh how engineers work compared to the rest of the industry? because now you were now in in this bubble which worked very differently.

</details>

**Guest**: 当时几乎没有什么计划安排，也没有那种所谓的最后期限。扎克伯格（Zuck）可能会说：“我想把照片的清晰度提高，你知道，提高四倍。”然后工程师们就会说：“嗯，我们做不到，因为有各种各样的原因（blah blah blah）。”接着他会回应说：“对，我理解。但我还是希望看到照片变得更清晰。”然后大家就会回去着手去做，这可能需要花费不管多久的时间。或者你先做了一阵子，如果因为某些原因实在做不下去，那你就转去做点别的事情。早期我曾和一个从微软过来的人共进午餐，他说关于Facebook的一点是，如果你在微软，而且你手头有个很棒的问题要解决，你会拼尽全力去捍卫这个问题，因为在那里根本没有足够多好的问题可供大家分摊。而在Facebook，如果你正在解决一个问题，这时候有别人也开始解决它，你只需要直接转向下一个问题就行了，因为总有其他地方起火需要扑灭。而这种状态现在的Facebook显然已经不复存在了。现在是机会极度匮乏，而那时则是机会极其充沛。我在新兵训练营（boot camp）期间，不经意间就每年为公司省下了500万美元。这是真的。我当时在看处理照片的代码，那时它还只是一个单一的PHP文件，我把它打印出来并全部粘在一起，那份完整的照片处理代码足足有18页纸，而那已经是当时世界上最大的照片网站了。我看着它，心想老天，这地方肯定有什么问题。我们当时非常小心地减少前端代码和缓存，甚至是更糟糕的数据库之间的往返次数。所以我看着它就在想，我意识到，哦对了，这个其实可以变得更加并行化。于是我做了调整，结果一周之后，照片业务的主管找到我并且说：“哦，运维部门注意到，当我们把你的代码发布出去之后，照片服务器的负载突然大幅下降，他们可以回收足够多的服务器，相当于一年省下了500万美元。”而我那时候其实只是在瞎鼓捣，你懂吗？所以，那时就像是淘金热，地上到处都是金块，你只需要把它们捡起来就行。但这种情况今天已经不复存在了，甚至到我离开的时候，这种同样意义上的机会也已经不复存在了。但在当时，你只需要做好一个程序员，做程序员该做的事，你就能拥有巨大的杠杆效应，这也是那时Facebook之所以如此神奇的原因之一。那是在公司IPO之前。当时的中层管理人员，中层工程管理人员，比如第一级和第二级工程经理，所有人都持有足以带来世代财富的既得期权，但公司必须上市才能兑现。所以那个层级的人非常关注全局优化，而不是局部优化。他们愿意做出让步。你知道，你和某个团队交流时，他们会说：“嗯，我们确实非常需要你，但我认为你真的应该去那边，因为那才是能让我的股票期权涨得最多的事情。”

<details>
<summary>Original English</summary>

**Guest**: There was very little planning. There were no deadlines as such. Zuck would say, "I want to increase the the resolution of photos, you know, by a factor of four." And the engineers would say, "Well, we can't do that because blah blah blah." And he'd say, "Yeah, I understand. Still want to see the photos looking better." And then people would go and do it. and it would take as long as it would take or you'd work on it for a while and if it just couldn't for whatever reason then you'd switch to something else. Early on I had lunch with somebody who'd come from Microsoft and said the thing about Facebook is if you're at Microsoft and you have a good problem to solve, you will defend that problem tooth and nail because there aren't enough problems to go around. And at Facebook, if you're solving a problem and somebody else starts solving it, you just go on to the next thing because there's always some other trash fire burning someplace else. And that's that's certainly no longer true at Facebook. It's opportunity starved. Then it was opportunity rich. I I accidentally saved $5 million a year during my boot camp. No way. I was looking that the photos code which at that time was a single PHP file that I printed it out and taped it all together. It was 18 pages the whole that was photos and it was the biggest photos site in the world at that time. And I looked at it I thought man there's just there's something wrong here. We were very careful to reduce the number of round trips between the front-end code and the cache or d even worse databases. And so I looked at it and I thought there's some I realized, oh yeah, they this can be made more parallel. So I made that switch and a week later the photos manager came to me and said, "Oh, ops noticed that the demand on the photos machines suddenly dropped when we rolled your stuff out and they they can reccommission enough servers to save $5 million a year." And I was just farting around, you know? So there it was like the the gold rush and there's just gold nuggets sitting on the ground and you just pick them up. That not true today and even by the time that I left it was it was no longer true in that same kind of sense. But you could just be a programmer and do programmer stuff and you had enormous leverage which was part of the magic of it at that time. This is preIPO. The middle management, middle uh engineering management like first and second level of engineering management all had generational wealth in vested options but had to go public. So that tier was very focused on global optimization, not local optimization. they would give up. You know, you you talk to some team and they're like, "Well, we could really use you, but I think you really should go here cuz that's what's going to make my stock options go up the most."

</details>

**Interviewer**: 是啊。

<details>
<summary>Original English</summary>

**Interviewer**: >> Yeah.

</details>

**Guest**: 一旦你陷入这种匮乏的荒漠般的心态，这种行为简直就是疯了。就像没有人会那样做一样。但在那个时候，那真的是非常新奇的。我收集了一整套这样的东西。前几天我还发现了这份名为“Facebook是如何运作的”手稿。其中有一堆我以前从未见过的政策。其中之一就是“50/50目标（50/50 goals）”。那时是六个月为一个绩效评估周期。在六个月开始的时候，你会说：“这，这就是我要做的事情。这些是我的目标。”当你和经理一起回顾这些目标时，如果你完成了一半的目标，你就能得到A+。如果你完成了你设定要做的每一件事，大家就会觉得，你知道的，你是在故意压低目标（sandbagging）。你不够努力。你承担的风险不够。在这六个月的过程里你什么也没学到。如果你一项目标也没完成，那你就会被直接淘汰。所以工程师和工程经理被解雇的速度比我在其他任何地方见过的都要快得多，这确实会产生焦虑感，但这也意味着你知道自己不需要为了防备那些偷懒的人而保护自己。因为其他所有人都承受着同样类型的压力，而且你们都在努力工作，让世界变得更加开放和互联。当然，现在事实证明世界有时候也会变得过于开放和互联，不过那就是另一码事了。

<details>
<summary>Original English</summary>

**Guest**: >> Which is crazy behavior once you get into this scarcity desert kind of mindset. Like nobody's going to act that way. But at that point, that was it it was extremely novel. I collected a whole uh series of this. I found this manuscript the other day, how Facebook works. There were a bunch of policies that I had never seen before. One of which was 50/50 goals. So, six-month performance review cycle. At the beginning of six months, you'd say, "Here, here are the thing. Here are my goals." And when you reviewed those with your manager, if you had accomplished half of the goals, you get A+. If you accomplished everything you set out to accomplish, people, you know, you're sandbagging. you're not trying hard enough. You're not risking enough. You didn't learn anything over the course of the six months. If you accomplished none of your goals, you were just out. So engineers and engineering managers would get fired at a much sooner than I'd ever seen anywhere before, which creates anxiety, but it also like you knew you didn't have to protect yourself from slackers. because everybody else was under the same kind of pressure and you were all trying to work make the world more open and connected. Now it turns out the world can be too open and connected but that's a separate set.

</details>

### 从工程向教练转型的“从优秀到卓越”计划

**Interviewer**: 是啊。但是感觉你见证了那里黄金的岁月。现在的士气很糟糕，所有的工程师都被指派去做数据标注，甚至都不问他们愿不愿意。这一切正转变成一种截然不同的文化。但我想这也说明公司确实是会变的。不过看起来当时确实是一个Facebook正处于成长期的时代。公司的愿景非常有意思。正如你所说的，那是机会极其充沛的时期，而你在那里负责指导工程师。对于那些能进入Facebook，想必已经相当出众的人，你从他们身上学到了什么？你又是通过什么方式去帮助他们，或者说你到底有没有帮助到他们呢？

<details>
<summary>Original English</summary>

**Interviewer**: >> Yeah. But it feels like you were there during the golden years now. Now now it's morale is is terrible with all the engineers are being assigned without asking them to do data labeling. It's all turning into very different uh culture. But I guess it just shows that places do change. But it seemed that was a time where Facebook was growing. The mission was very interesting. There were as you said more it was opportunity rich and you were coaching coaching engineers there. What did you learn about folks who are already I guess pretty stand out if they got into Facebook. How in what ways could you help them or did you help them?

</details>

**Guest**: 我入职大概一年的时候，当时正在为Facebook Messenger产品开发一个C++项目的基础设施，那个产品当时刚推出并变得非常成功，在某种程度上已经超越了它原有的基础设施，急需技术支持。然而我并不是一个优秀的C++程序员，所以我不可能在那里有什么突出表现。我有六个月的时间来扭转局面，而在那些“迷失的岁月”里，我是靠着做远程辅导（coaching）来维持生计并找到心灵寄托的。因此我知道自己积累了，我也不知道具体有多少，可能有几百甚至几千个小时的辅导互动经验。然后我在Facebook的一位老资格的朋友彼得·德莫夫（Peter Demov）对我说：“你一直谈论辅导这方面的事情。为什么你不干脆直接开始做那个呢？”Facebook很大程度上是一个这样的地方：你是一名工程师，你觉得自己想做某件事，那你就去做。如果做不出来，你要承担后果；如果做成了，你就能得到奖励。所以我当时想：“好吧，我现在是一名教练了。”于是我自立门户，找到了我最早的三个学生，并开始了每天一小时的谈话辅导，后来发现对于持续三周或四周的周期来说，这实在有些太多了。那三个学生中有两个辅导效果很好，但其中一个被解雇了。不过，是的，他们把这个告诉了其他人，于是大家就开始来找我，要求参加这种被称为“从优秀到卓越（good to great）”的辅导项目。这个想法的核心是，我会去和那些能力不错但是陷入某种瓶颈期的程序员交流。你知道，人的成长存在这种“间断平衡”现象，人们在能力提升之后，接着会在没有太多成长的情况下不断积累经验，这时候他们需要一点推力才能更上一层楼。这就是“从优秀到卓越”这部分内容的由来。我当时在一对一地辅导别人。我会同时辅导六个人，这非常让人筋疲力尽，但同时我也在安排其他资深工程师为初级工程师提供辅导。然后我们会进行“辅导教练”这种关于辅导的元对话。我会让他们跟我说说这周发生的某件事，也许是一件你不知道该如何应对或者觉得很棘手的事，然后大家一起来讨论。我还请来了一位讲故事（storytelling）顾问来做了一次团队建设（offsite）。我雇佣了艾伦·奥奥尔克（Aaron Oorc）做我的行政主管，因为这种安排对接各种事情实在不是我的强项。她与人力资源部门合作分析了这个项目，并发现那些曾经是我学生的人，在接受辅导后的一年里，获得晋升的可能性是同样背景但未接受辅导的对照组的两倍。所以，它真的起到了加速员工职业发展进程的作用。只是我在处理这其中的办公室政治方面做得不是很好。也就是说，这成了一个存在于公司学习与发展（L&D）部门体制之外的培训项目，而我当时并没有意识到这将会成为一个问题。所以，到我离职的时候，确实有很多人非常支持“从优秀到卓越”项目，但同时也有一部分人并不喜欢这个项目的存在。所以我最后大概辅导了200多个人。

<details>
<summary>Original English</summary>

**Guest**: So about a year in I'd been working on a C++ project infrastructure for the Facebook Messenger product which had come out become very successful kind of out outgrown its infrastructure needed support and I was not a good C++ programmer and so I was not going to stand out there. uh I had six months to turn stuff around and in that uh the missing years I kept body and soul together by doing coaching, remote coaching. And so I I knew I'd had I don't know hundreds of hours, maybe thousands of hours of of coaching interaction. And uh one of my friends at Facebook, a old-timer named Peter Demov said, "You've talked about this coaching stuff. Why don't you just start doing that? And Facebook was very much a you're an engineer. You feel like doing a thing, you do the thing. If it doesn't work out, you take the consequences. If it does work out, you get the rewards. So, I thought, "All right, I'm I'm a coach now." So, I hung out my shingle and I found my first three students and started with daily one-hour conversation, which turns out to be way too much for 3 weeks or four weeks or something. And two of the students worked out well and one of them got fired. But uh yeah, they told other people so people would come to me and ask for this coaching thing which evolved into a program called good to great. And the idea was I'll talk with programmers who who are good but have kind of stalled. You know there's this punctuated equilibrium that happens where people get better and then they they gather experiences without growing much and they need a little kick to get them up to the next. And so that's the good to great part. And I was coaching people one-on-one. I'd coach six people at a time, which is exhausting, but I was also matching up other senior engineers with junior engineers for coaching. And then we'd we would have the meta conversation of coaching the coaches. tell me about something that happened this week that was a you didn't know how to react to or was difficult or we'd all talk. I brought in a a storytelling consultant to to do an offsite. Uh, I hired uh Aaron Oorc uh was my administrator cuz this is not my strong suit. Kind of lining stuff up. And she worked with HR to analyze the program and discovered that the people who'd been my students were twice as likely to get promoted in the year following coaching than a cohort that was the sameish. but didn't get coaching. So, it it really worked to to accelerate the career progression of the people. I didn't handle the politics of it very well. So, this was this was learning and development outside of the learning and development organization which and I didn't understand that that was going to be an issue. So, by the time I left there were big fans of Good to Great, but there were also people who didn't like the fact that it was around. So I ended up coaching probably 200 people

</details>

<!-- chunk 14/16 -->

### 软件工程师的价值与被替代的迷思

**Speaker A**: 个别来说。我会编写课程，亲自授课，然后教其他人去教，让成千上万的工程师参与其中。就在我离开之前，我参加了一个 Facebook 前 1% 工程师的异地会议。在场的 100 多人中，大约有 100 人，其中 10 人是我以前的学生，他们晋升到了那个级别。所以我对这一切的成果感觉非常好。这有点像回到了 Ward 的时代。那是我能够与 Ward 有的那种互动。这并不总是令人愉快的。这不是拍拍你的头说你会没事的。而是像“不，你搞砸了。去试试这个。告诉我效果如何。哦，你没去试。哦，你不想做这个？好吧，我们结束了。”非常不妥协。我说教练的存在是为了识别并引发富有成效的不适感，但整个教练项目，到我离开时，我已经有了曾曾徒孙。我指导过的人成为了教练，他们又指导了成为教练的人，而这些人现在也在做指导。我认为在这种风格的学习方式中，有一种元素是无法复制的。所以当 Darío 说我们要消灭软件工程时，你根本不了解软件工程师是做什么的。我们肯定会改变软件工程中的一些活动。绝对会。我玩得很开心。但是这种认为我们是代码猴子、只要输入需求就能输出代码的想法，拜托。说实话，我确实感觉到 Darío 对开发者——或者我应该说软件工程师——有一种蔑视。或者我从未见过他喜欢他们或他曾经是其中一员的迹象。不，他显然不是。这没关系。你可以是物理学背景或类似背景，这都没关系。你也可以对我说“我要取代你的工作”。我不认为这是不尊重，那只是无知。顺便问一下，我们能谈谈你现在提到的这个问题吗？你在我们的讨论中多次提到过。人们非常想取代我们开发者，我们也许应该反思一下。你已经有时间反思了，为什么这个问题总是被反复提及？

<details>
<summary>Original English</summary>

**Speaker A**: individually. I would write classes that I would give and that I'd teach other people then to give that thousands more of engineers went through it. And just before I left, I went to an offsite with the top 1% of Facebook engineers. And out of the 100 plus people, 100ish people there, 10 of them were former students of mine who had gotten promoted to that level. So I felt really good about how that all worked out. That was a kind of back to Ward. That was a kind of interaction that I was able to have with Ward. It wasn't always pleasant. It's not a pat you on the head and you're going to be fine. It's a don't like no, you're screwing this up. Go try this thing. Tell me how that works. Oh, you didn't try the thing. Oh, you don't want to work on this? Okay, we're done. Quite uncompromising. I say coaches are there to identify and induce productive discomfort but the coaching program as a whole by the time I left I had great great grand students. I'd coached people who became coaches who coached people who become coaches who now were coaching. I think there's an element to that a way of learning in that kind of style that just can't be duplicated. So when Darío says we're going to eliminate software engineering, you don't understand what software engineers do. We're going to transform some of the activities that go into software engineering. Absolutely. I'm having a blast. But this idea that we're code monkeys and jolt col in code out. Come on. To be honest, I do sense that Darío has a disdain for developers, software engineers, should I say. Or I've never seen an indication that he likes them or that he was one. No, he clearly wasn't one. This is fine. You can be it's like a physics background or something like that. That's fine. And you can say I'm going to replace your job to me. I don't consider that disrespectful. That that's ignorant. By the way, can we talk about now you bring this up every you brought this up multiple times in our discussions. People awfully want to replace us developers and we should probably reflect a little bit on that. You've had time to reflect why why does this keep coming back?

</details>

**Speaker B**: 只是因为我们有时……我的意思是，长话短说就是这样。我的观点是，作为一个在自闭症谱系上的人，做了很长时间的工程师，我的父亲是工程师，我的祖父是个极客，你知道，以他自己玩无线电的方式。所以，我完全是天生如此。我们不一定有很好的情绪调节能力。没有天生的同理心。顺便说一句，这就是我打扑克的原因，这样当我的同理心不好时，我能得到反馈。我们通常比其他人能轻易接受的程度更直接。

<details>
<summary>Original English</summary>

**Speaker B**: Just we're kind of sometime. I mean, that's the that is the long and the short of it. My perspective is someone on the spectrum who's been an engineer for a long time, whose dad was an engineer, whose grandfather was a geek, you know, in his own in his radio kind of way. So, I come by this all honestly. We don't necessarily have good emotional regulation skills. Don't have natural empathy. It's why I play poker, by the way, so I get feedback when I have don't have good empathy. We often times are more direct than other people can easily handle.

</details>

**Speaker A**: 是的。在商业环境中。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. In the in the business setting.

</details>

**Speaker B**: “我只是在说实话”或者“我只是问个问题。”这些是我说过的最可怕的话，因为……好吧。是的，你只是在问个问题，但你问那个问题的样子像个混蛋。而且我以前并没有意识到这一点，但我是这样的，因为人们就是那样反应的。所以我不指望任何人对我宽容。有些人会说，“好吧，应该由世界其他地方来适应我的怪癖。”这不可能，因为我的意思是，这不会发生。所以，学习同理心，学习如何解读肢体语言，学习如何解读语气，这虽然不是天生的技能，但它们是技能。它们是可以学习的。我永远无法像我的伴侣那样擅长这些（她是个社交天才），但我在这些技能上可以做到不那么糟糕。比如好斗。对于像我这样的人来说，这是一种常见的社交策略，也一直是我的一种社交策略。我们之间存在一些分歧，我解决它的方式是，你知道，“这需要多长时间？四周。必须在两周内完成。”

<details>
<summary>Original English</summary>

**Speaker B**: I'm just telling the truth or I was just asking a question. Those are the most hideous things that that I say because Okay. Yeah. You were just asking a question, but you're being an ass asking that question. And you I didn't realize it, but I was cuz that's how people react. So I don't expect anybody to cut me any slack. There are people who say, "Well, it's up to the rest of the world to adapt to the ways that I'm weird." It's just not because I mean, it's not going to happen. So, learning empathy, learning how to read body language, learning how to read tone of voice, this is not natural skills, but they're skills. They're learnable. I'll never be as good at them as my partner who's social genius, but I can be not horrible at those kind of skills. things like uh belligerence. That's a common social strategy for people like me and has been a social strategy of mine. There's some disagreement between us and the way I resolve it is you know how long is this going to take? Four weeks has to be done in two weeks.

</details>

**Speaker A**: 是的，那是邀请进行对话。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, that's an invitation to have a conversation.

</details>

**Speaker B**: 当我说四周，而你说不，必须是两周时。我不需要退缩并说：“好吧，我尽量完成它。”我也不需要说：“去你的吧，混蛋。”这两种回应都没有帮助。我会说，“好吧，那让我了解一下你的需求。”这对我来说不是一项简单的任务，但我可以做到。我有一个小清单，你知道，就像第一部《终结者》电影里那样，他有一个回复的下拉菜单。是的，通常感觉就是那样。但有一个回复的下拉菜单，总比做一些疏远对方、在对话真正结束前就终止对话的事情要好。我认为就是这些事情。我们有必要学习如何以一种其他人能真正听进去的方式进行交流。这就是为什么我会引入金融界、体育界、历史界以及我能找到的每一个领域的类比，拼命试图理解别人，并帮助他们以一种他们能真正理解的方式来理解我的观点以及它给情况带来了什么。跳到现在，这几年我们有了 AI LLM，但现在我们只叫它 AI，或者像你所说的“精灵”。

<details>
<summary>Original English</summary>

**Speaker B**: When I say four weeks and you say no, it has to be two weeks. I don't have to shrink and say, "Okay, I'll try and get it done." I also don't have to say, "Yeah, go to yourself, jackass." That neither of those responses help. Say, "All right, well, let me let me understand your needs." Not an easy task for me, but I can I can do it. I have a little checklist, you know, the first Terminator movie where where he's got the little uh pull down menu of responses. Yeah, it feels like that often times. But it's better to have the pull down menu of responses than to do something that alienates the other person and ends the conversation before it's actually finished. I think it's those kinds of things. It behooves us to learn how to communicate in a style that other people can actually listen. Which is why I bring in analogies from the the finance world, from sports, from history, from every place I can find in a desperate attempt to understand other people and help them to understand my perspective and what that brings to the situation in a way that they can actually comprehend it. Jumping to the present times where now for a couple of years we we've had AI LLMs but now we just call it AI or as you call the genie.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 并且

<details>
<summary>Original English</summary>

**Speaker B**: And

</details>

**Speaker A**: 它能满足愿望，但这并非真的是你想要的。

<details>
<summary>Original English</summary>

**Speaker A**: it grants wishes but it's not actually what you want

</details>

### AI 加速与企业适应性

**Speaker B**: 并且它有一些有趣的特征。我想知道，你认为这将如何改变个人开发者的工作，以及正在构建软件的团队、公司和科技公司？到目前为止你看到了什么？我们谈论了很多关于软件工程真正是什么。我们讨论了在编码过程中的理解、沟通和学习，看起来这些肯定在缩减，如果不是被剥夺的话。这是一种选择。但我会让你问完你的问题。

<details>
<summary>Original English</summary>

**Speaker B**: and it has some interesting characteristics. I'm wondering how do you think this will change individual developers work and also teams companies tech companies are building software. What are you seeing so far? Talked a lot about how what software engineering really is. We talked about the understanding the communication the the learning as you are coding and it seems that that is definitely shrinking if not being taken away. That's a choice. But I'll let you finish your question.

</details>

**Speaker A**: 只是纵观整个行业。

<details>
<summary>Original English</summary>

**Speaker A**: Just look looking across the industry.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

**Speaker A**: 而且感觉这里有个类比，就像你之前说的，当接口出现时，人们过度使用了接口，感觉现在就像这样。我们有这些 AI 智能体或我们称之为的精灵，人们到处都在使用它，他们快疯了，忘记了一些常识性的东西。

<details>
<summary>Original English</summary>

**Speaker A**: And and it also feels that there's this analogy which what you said when uh when interfaces were out that people overdoing the interfaces and it feels it's it's like this. We have these AI agents or genies as as we call and people are using it everywhere and they're going mad and forgetting some of the sensible stuff.

</details>

**Speaker B**: 是的。这是一个多么开放式的问题。其中一件事是发展步伐肯定加快了。我好奇的一件事是，商业的步伐并没有加快，而这种不匹配将变得越来越明显。所以我在一个客户那里，他们向我展示，他们每年在一个 SaaS 产品上花费 200 万美元。有人仅凭直觉（vibecoded）写出了它的替代品，不仅更符合他们的使用需求，而且每年不需要花费 200 万美元。那个供应商将如何应对？在两年前的旧时代，他们有几年的时间来回应，“是的，我们有这个附加组件。它每年花费 200 万美元，虽然人们不太喜欢它，并且最终会找到替代品。”我们有五年或三年的时间来应对。但现在他们面临的是：“我们有这个附加组件，我们一直能用它收费。但这在一个月内就会消失。”在客户那边，他们能够编写出一个更好的替代品。是的，他们可以编写出代码，他们看到了和其他人一样的加速。但是，寻找替代品的需求会穿过他们的客户服务、营销、销售、业务发展，再到产品组织吗？哒哒，巴拉巴拉巴拉。那条链条设计出来是需要五年的，而现在他们只有一个月的时间，否则他们将失去大笔收入。这不是 AI 的错，这只是一种加速，而他们的业务流程根本没有准备好及时响应。我个人对敏捷的定义就是“及时响应”，而他们并没有准备好应对这种新节奏。就像你一直开着拖拉机，突然间你进了一辆赛车。仍然有轮子，仍然有引擎，但你的技能准备好驾驶那辆车了吗？重要的不是它能跑多快，而是你能在一条蜿蜒的山路上，多快地从 A 点到达 B 点？你习惯了开拖拉机，现在你却在一辆法拉利里。这不是车的错，但我认为这是一种趋势，我预计我们会看到公司因为没有及时响应而倒闭。他们一直以来都脑满肠肥、自满安逸。有点像带分类广告的报纸，这是另一个类比。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. What an open-ended question. So one of the things is that the pace of development is definitely accelerated. One thing I wonder the pace of business hasn't accelerated though and that mismatch is going to become more and more apparent. So I was at a client they were showing they were spending $2 million a year on some SAS product. somebody vibecoded a replacement for it that was better for their uses and didn't cost $2 million a year. How is that vendor going to reply to that? Back in the olden times two years ago, they'd have years to respond to, "Yeah, we have this add-on. It costs $2 million a year, but people don't really like it, and eventually they're going to find a replacement. we have five years to respond to that or three years to respond to that. Now they've got we have this add-on, we've been able to charge for it. That's going to go away in a month. On their side, they could they code up a replacement that was better. Yeah, they could code up they they're seeing the same kind of acceleration everybody else is. But is the need for a replacement going to go through their customer service to marketing to sales to business development to the product organization. Da da blah blah blah blah blah blah. That's that chain is designed to take five years and now they have a month or they're going to be losing big chunks of revenue. This isn't AI's fault. this is just an acceleration and their business process is just not prepared to respond in time. As my my personal definition of agile is uh responds in time and they're not prepared to deal with the new pace. Like you you're driving a tractor and all of a sudden you're in a race car. still wheels, still an engine, but are your skills prepared to steer that car? Not how fast can it go, but how fast can you get from point A to point B on a windy mountain road? You're used to driving a tractor and now you're in a Ferrari. It's not the car's fault, but I think that's that's a trend that I expect to play out that we're going to see companies fail because they don't respond in time. They've they've been fat and happy. Kind of newspapers with uh an another analogy, newspapers with classified

</details>

<!-- chunk 15/16 -->

### 冰山一角与直觉编程 (Vibe Coding)

**Speaker A**: 冰山，冰山的那部分。

<details>
<summary>Original English</summary>

**Speaker A**: the the part the iceberg iceberg

</details>

**Speaker B**: 你能看到的那部分，你可以用直觉编程（vibe code）来处理你能看到的这部分冰山。

<details>
<summary>Original English</summary>

**Speaker B**: you can see that you can vibe code the part of the iceberg that you can see.

</details>

**Speaker A**: 所以，呃，我来说说我自己的经历吧。我在 Gusto 待了三年，这家公司做的是小企业工资单系统。有人说：“好吧，我刚才问了 Claude，我以这个费率工作了这么多小时。我在这个税级。我的工资单应该是多少？” 然后它告诉了我所有的数字。我再也不需要 Gusto 了。而我当时的反应就是，哦，你根本不知道这里面的水有多深。去吧，你自己去跑一个季度的工资单，然后再去弄清楚你需要向各个税务机构和不同的州提交哪些报告，而且我住在这个州，但我在那个州工作，公司又设在这里，那么现在这个数字应该是多少呢？

<details>
<summary>Original English</summary>

**Speaker A**: So uh I'll talk my own book. I was at Gusto for three years does small business payroll. Somebody said, "Well, I just asked Claude, I have this many hours at this rate. I'm in this tax bracket. What should my paycheck be?" And it tells me all the numbers. I don't need gusto anymore. And I'm just like, oh, you have no idea. Go ahead, run your own payroll for a quarter and then figure out what all of the reports you need to submit to the various tax agencies and different states and I live in this one, but I work in that one and the company's based here and now what should the number

</details>

**Speaker A**: 就像什么呢？要正确、合规地执行工资单，除了毛薪和净薪之外，还有很多其他的事情要做。所以，我们会看到人们陷入这种境地，他们会说：“好吧，我用直觉编程解决了冰山一角。我把冰山剩下的部分全扔了，现在我遇到麻烦了，因为现在我不知道该怎么办。现在我遇到了一些我甚至不知道其存在的下游问题。” 所以，我们会看到，在那些想要用直觉编程来替代现有系统的人身上，会上演这种天真的悲剧。

<details>
<summary>Original English</summary>

**Speaker A**: like? There's so much that goes on to correctly, compliantly execute payroll that isn't gross pay, net pay. So, we're going to see people get into those where they're like, "Well, I vibe code the tip of the iceberg. I throw away the rest of the iceberg and now I'm in trouble because now I don't know what to do. Now I get to these downstream problems that I didn't even know existed." So, we're going to see on the on the side of the the the vibe coding replacers, we're going to see that kind of a naivity play out.

</details>

### 软件工程师的未来与 3X 模型

**Speaker B**: 那么对于软件工程师来说呢？因为很多工程师的身份认同，都围绕着能够精雕细琢代码、关注工艺本身、能够将很多这类事物具象化。而这些 AI 工具在完成其中很多工作方面变得越来越出色。你会给这些人什么建议？面对这种新的技术变革，如果你想保持作为软件工程师的顶尖水平，你可以做些什么活动？你应该做出什么样的心态转变？

<details>
<summary>Original English</summary>

**Speaker B**: And what about for software engineers? Cuz a lot of the identity for engineers was around being able to craft code, caring about the craft, being able to visualize a lot of these things. And these tools are getting really good at doing a bunch of that stuff. What advice do you give to to these folks on okay well there's this new technology change if you'd like to stay top of the game software engineer what activities can you do what mentality change should you do

</details>

**Speaker A**: 所以，我用来激励自己的座右铭是“没有人知道”。人们来找我，他们会说，那么 TDD（测试驱动开发）如何在增强编程（augmented coding）的世界中应用呢？我说没有人知道，这不仅仅是我不知道，而是没有人知道。我在 Facebook 学到的最大的教训是关于产品、关于软件开发有三种不同的阶段状态。首先是探索阶段（exploration phase），在这个阶段你必须尝试很多不同的东西，因为你无法预测结果。然后某个东西起飞了，我们在谈论我职业生涯中的例子时提过很多次。一旦火箭点火，驾驭火箭升空的纪律，与探索未知领域的纪律是非常不同的，探索本身也是一门纪律。所以当你在扩张（expanding）时，你非常非常专注，它甚至可能是不可持续的，但它不会持续很长时间；然后进入下一个阶段，你从这个成功的产品中提取（extracting）价值，来为下一轮的探索提供资金。这就是 3X 模型。

<details>
<summary>Original English</summary>

**Speaker A**: so the my inspirational motto is nobody knows so people come to me they say well how does TDD apply in in the augmented coding world I said nobody knows it's not just that I don't know is nobody knows. The big lesson I learned at Facebook was about that there are three different phase states of of product of software development. This exploration phase where you got to try a bunch of different things because you can't predict. Then something takes off and we've talked about a bunch of those examples from my career. And the discipline of riding that rocket up once it's been lit is very different than the discipline and it is a discipline of exploring the space. So while you're expanding you you you focus very intently and it can be and it might even be unsustainable but it doesn't last very long and then there's another you get to extracting value from that to feed the next set of explorations. This this is 3x,

</details>

**Speaker B**: 对吧？探索它（Explore it）。

<details>
<summary>Original English</summary>

**Speaker B**: right? Explore it.

</details>

**Speaker B**: 这是你在 2016 还是 2017 年左右提出的另一个模型。

<details>
<summary>Original English</summary>

**Speaker B**: This is yet another model that you came up sometime in 2016 17.

</details>

**Speaker A**: 是的，2015 还是 2016 年。我终于想通了，想通了。我觉得我终于明白了 Facebook 是如何做到在保持庞大体量和快速增长的同时，还能保持创新能力的。那是通过用完全不同的风格来对待处于不同阶段的项目。所以，“探索”阶段……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. 15 16 I finally figured out figured out. I felt that I understood how Facebook had been able to be large, growing, and innovative at the same time. And it was by treating projects at different phases in a completely different style. So explore

</details>

**Speaker A**: “探索”（explore）就是你仅仅是在寻找某种东西，而且你无法预测它。所以你必须尽可能多地尝试，这是一个数字游戏。你以尽可能低的成本去尝试尽可能多互不相关的实验。然后你“扩张”（expand）……当某个东西起飞后，你就进入了这个扩张阶段。在这个阶段，你不再是每样东西都试一点，而是专注于那个正在奏效的东西，你抛弃其他一切，你克服一个接一个又一个的障碍。接着你达到了特定的规模，现在你可以预测增长了，你可以说，如果你要写一个……“如果我们要在新国家推出我们的产品，我们已经做过五个国家了，这是剧本”，你就知道该怎么做了。那就是“提取”（extract）阶段。你已经达到了规模经济。你可以做一些微小的调整，就能产生巨大的影响。这个阶段的生命周期也很长。所以，你编写代码的方式、管理项目的方式、你雇佣什么样的人、多少人、组织结构是怎样的，在三个阶段中是完全不同的。

<details>
<summary>Original English</summary>

**Speaker A**: explore is you you're just looking for something and you can't predict. So you have to try as many it's a numbers game. You try as many uncorrelated experiments as you can for the cheapest price. Then you expand and then something takes off and then you're in this expansion phase where instead of trying a little bit of everything, you focus on the one thing that's working and you discard everything else and you overcome obstacle after obstacle after obstacle and then you get to a certain size and now you can predict growth and you can say you can write a if we roll out our product in a new country, we've done five countries already, here's the playlist and you know how to do that. That's that extract phase. You've reached economies of scale. You can make small tweaks and it makes a big difference. You have a long life span also. So how you write code, how you manage projects, who you hire, how many people, what the org structure is is completely different in the three phases.

</details>

### 旧剧本失效与新范式的诞生

**Speaker A**: 在过去的 20 年里，我们一直处在那个“提取”状态中。已经有了一套剧本（playbook）。它虽然有一点点演变，但你知道的，哦，我们在生产环境中有太多 bug 了，这里有三种你可以尝试的方法。哦，你知道，我们需要加速开发，这里有你可以做的事情。当然，现在人们有时并没有照着做，但这个剧本是存在的。成为一名高级工程师，意味着你熟知这套剧本。你越了解这个剧本，你的工作就越有效率。如果你知道，哦对了，我也知道如何扩展后端；你知道，我懂幂等性（idempotency），你知道如果我实现它会带来什么好处，等等。现在，没有人知道了。那套旧剧本已经被抹去了，而那些把自己的身份认同建立在“我知道这套剧本”上的人，现在都吓坏了。我到底是谁？

<details>
<summary>Original English</summary>

**Speaker A**: For 20 years, we've been up in that extract stand. There's been a playbook. It's evolved a little bit, but you know, oh, we have too many bugs in production. Here's the three things you can try. Oh, you know, we need to accelerate development. Here's the things you can do. Now, people sometimes didn't do the things, but the playbook existed. And to be a senior engineer meant that you knew the playbook. And the more you knew the playbook, the more effective you could be. If you knew, oh well, I also know how to scale backends. You know, I know about item potency and you know what advantages that brings if I implement it and so on. Nobody knows now. That playbook has been wiped clean and people whose identity is I know the playbook are now terrified. Who who am I?

</details>

**Speaker A**: 现在看来，编写剧本的技能，与应用剧本的技能是完全不同的。我们在面向对象时代做的那些事情，那就是在编写剧本。那是在曲线的“探索”部分。当你没有剧本时，并不是说就没有高效工作的方法。只是说，这是一个不同的游戏规则。而那些没有剧本就缺乏安全感的人，需要转变他们的思维方式，认识到：好吧，没有人知道答案。并不是说存在某种针对基于“精灵（genie）”的开发的秘密剧本，只要我付一百万美元，我就能得到它。它根本就不存在。当我们哪怕窥见它的一角时，下周它又变了。输入端微小的变化会导致输出端巨大的变化。所以，在这个世界里，我们所有人又回到了“探索者”的状态，我们只需尝试越多的东西越好。

<details>
<summary>Original English</summary>

**Speaker A**: Now, it turns out that the skill of writing a playbook is completely different than the skill of applying a playbook. That stuff that we did in the the days of objects, that was writing a playbook. That was that explore part of the curve. It's not that there isn't a way to be effective when you don't have a playbook. It's just that it's a different game. And the people who don't feel safe without a playbook need to turn their heads around to like, well, nobody knows. It's not like there's some secret playbook for genie based development that, you know, if only I paid a million dollars, I could have it there. It just doesn't exist. When we get glimpses of it, it changes next week. like small changes to the inputs cause large changes to the outputs. So we're all back in explorer stand in this where we just the more things we can try the better.

</details>

**Speaker A**: 我经常会被问到这些问题。哦，我觉得我们应该如何如何，与其一次写一个测试，也许我们应该一次写一堆测试。你觉得那行得通吗？没有人知道。去试试吧，然后告诉我们结果如何。如果更多的人在社区里尝试更多的东西，并且像这样交流：我在这里做了这件事，我添加了这个 markdown 文件，它产生了这种效果；然后另一个人说，好吧，我添加了它，却让情况变得更糟了。好的，那么你们的情况有什么不同呢？必须要有这样的对话，这才是最终会孕育出新剧本的东西。敏捷宣言（Agile manifesto）的日期是 2002 年，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: I'll get these questions. Oh well I think we should blah blah blah blah blah instead of writing one test at a time maybe should we should write a bunch of tests at a time. Do you think that would work? Nobody knows. Try it and tell us how it goes. If more people are trying more things in community and communicating like I did this thing here, I added this markdown file and it had this effect. Somebody else says well I added it and made things worse. Okay. Well, what's different about your have to have that conversation that's what's going to result in the playbook. The agile manifesto date 2002, right?

</details>

**Speaker B**: 2001 年。是的。

<details>
<summary>Original English</summary>

**Speaker B**: 2001. Yeah.

</details>

**Speaker A**: 2001 年。第一届 OOPSLA 会议是在 1986 年，花了 15 年的时间才写出那份宣言。这就是为什么现在当我看到各种宣言时，我只会觉得：太早了。这不是个坏主意，我很乐意拥有一份宣言，但确实太早了。面向对象编程的技术变革出现了 15 年之后，我们才能够说：这是它带来的后果。这就是我们如何用一种简单的方式，来表达如何有效利用这项我们日复一日使用了 15 年的技术。现在“精灵”出现了。人们就说：“那新的宣言是什么？” 只是现在还不到写宣言的时候。

<details>
<summary>Original English</summary>

**Speaker A**: 2001. The first oops LA 1986 took 15 years to write that manifesto which is why when I see manifestos today I'm just like too soon. Not a bad idea. Would love to have one just too soon. It took 15 years for the technical change of object-oriented programming to come before we could say here are the consequences of it. Here's how in a simple way we can express how to effectively use this technology that we've been using day in and day out for 15 years. The genie comes along. People are like, "Well, what's the new manifesto? It's just not manifesto time yet."

</details>

### 拥抱未知与重新启航

**Speaker B**: 作为结尾，展望未来，对于 AI 智能体、对于“精灵”、对于所有这些变化、对于我们所处的这张白纸般的新状态，你发现什么让你感到兴奋？是什么给了你能量？

<details>
<summary>Original English</summary>

**Speaker B**: As closing, what do you find exciting looking ahead with with AI agents, with genies, with all this change, with this clean state that we're in? What what gives you energy?

</details>

**Speaker A**: 对我来说，这就像是回到了我的主场。就是“编写剧本”这件事。我就是喜欢干这个。我是那个“摇树的人”（探索者/开拓者），而不是那个“做果酱的人”（提取者/守护者）。所以，我喜欢摇晃这棵树。我喜欢让事情启动起来。我有一系列非常广泛的项目。我有一个叫做 Arlo 的项目，它是一个面向对象的数据库。我做了好几个基础的数据结构。我想看看我是否能用一种我不懂的语言，写出达到库级别质量（library quality）的代码。事实证明，是的，我能。所以我构建了一个 B+ 树，在某些操作上，它甚至比 Rust 原生的 B 树还要快。

<details>
<summary>Original English</summary>

**Speaker A**: This is home base for me. The writing of the playbook. I I just love that. I'm a tree shaker, not the jelly maker. So, I love shaking the tree. I love getting stuff started. I have a very wide range of projects. So, I have a project called Arlo, which is a an object-oriented database. I have uh several fundamental data structures. I wanted to see if I could write code that was library quality code for a language I didn't know. It turns out, yeah, I can. So, I built a B+ tree that's faster than Rust's B tree for some operations.

</details>

<!-- chunk 16/16 -->

### 关于创新的“重头再来”

**Kent**: 哇哦。是的。但同时，我也并不是一个 Rust 专家。打个比方，一个真正的 Rust 专家用这些同样的工具能做出些什么呢？而且，为什么他们没有亲自去写这些东西呢？我不知道，我真的不知道。但我正在为我自己所关心的事情去构建一些零碎的、小巧的应用程序片段。我使用精灵（Genie，指代 AI 助手）来进行商业规划，因为就像你一样，我也经营着一份时事通讯（newsletter）。不过和你不同的是，我的时事通讯规模比较小，但对我来说其实也算挺大了。

<details>
<summary>Original English</summary>

**Kent**: Wow. Yes. But also, I'm not a Rust expert. Like, what could a REST [Rust] expert do with these same tools? And and why didn't they write it? I don't I don't know. But I'm building little bits and pieces of apps for stuff that I care about. I use the Genie for business planning cuz like you, I have a newsletter. Unlike you, my newsletter is kind of small, but it's pretty big.

</details>

**Host**: 我现在做得还不错。

<details>
<summary>Original English</summary>

**Host**: I'm doing okay.

</details>

**Kent**: 那么，我该如何将它转化为一个可持续发展的商业模式呢？嗯，另外，我还专门雇佣了一位商业伙伴来协助我处理这项工作。所以，我写了非常多东西，不断反思我的个人经验。我正在尝试所有可能的方法。如果说我目前正在做的事情里真的有什么“秘诀”的话，那就是：不害怕重头再来。

<details>
<summary>Original English</summary>

**Kent**: Now, how do I turn that into a sustainable business? Um, also I hired a business partner um to help with that. So, I'm doing a lot of writing, reflecting on my experiences. I'm trying everything. If there's a secret sauce to what I'm doing, it's uh not being afraid to start over.

</details>

**Host**: 你的整个职业生涯从非常早期的阶段就向大家展示了这一点。无论是 TDD（测试驱动开发）、XP（极限编程）、3X、Tidy First（先整理代码），还是现在的 Genie。

<details>
<summary>Original English</summary>

**Host**: And your whole career shows this from the very early days. TDD XV [XP] 3X, Tidy First, Genie.

</details>

### AI 时代的编程乐趣

**Kent**: 是的。所以如果你看看我的 GitHub 仓库，你会看到诸如 project、project two、project three、project four，然后又是 new project、new project two、new project three、new project。我会顺着这个思路做下去，我会把它推进到一定的程度，然后当这个精灵耗尽了它的办法，当它自己耗尽了各种选项，无法再取得进一步的实质进展时，我就会把它全部抹掉，重新开始。我不会去尝试做那些微调，我会直接重头再来，然后对自己说：“好吧，如果我以一种完全不同的顺序来实现这些东西呢？如果我用这个 markdown 文件来进行实现，或者我用这个 commit hook（提交钩子）来实现呢？”我们大家作为一个集体，需要去尝试绝对所有的东西。其中一些想法听起来会显得很愚蠢，但结果却出奇的好。而一些听起来愚蠢的想法同样也会带来灾难性的后果。但是，只要我们愿意重头再来，那这些灾难也就无所谓了。我们并没有真正冒那么大的风险。这种创作的冲动，在有了精灵之后又重新回到了我身上。有了这种想法，我就可以去探索：“我想知道一棵 B+ 树在 Go 语言里到底长什么样。这里有一个 B+ 树的替代方案，叫做自适应基数树（adaptive radix tree）。那它又是什么样子的呢？”我是可以去寻找答案的。我和精灵坐下来一起研究。我可以把它弄清楚。然后，这里就出现了一个以前完全不存在的实体成果，它现在之所以能够存在，是因为我的想象力和我的辛勤工作。而我以前早就对编程里那些愚蠢至极的琐事感到厌烦透顶了。比如，哦，为了实现那个功能，你需要把某个东西升级到 7.1 版本，结果这又导致了别的某个东西崩溃，接着又导致了另一个东西崩溃，这就意味着我根本没办法去使用 7.1 版本。我不得不……我只是讨厌那种状况。你投入了极大的情感，你有了一个绝妙的想法，你投入了情感，你努力推进了一段路，结果却意识到：“我根本没办法完成这个项目”，而且完全没有一个合理的、站得住脚的理由。我真的讨厌那样。而那种令人窒息的阻碍，现在根本就不会再发生在我身上了。哦，所以这简直就是程序员的天堂。我积累了整整 40 年的想法。那些“这个做出来会很酷”、“呃，可是它太庞大了吧”的想法，现在突然之间，它们又重新回到了可操作的舞台上。我正在享受这种把脑海中的事物变成现实的巨大乐趣。

<details>
<summary>Original English</summary>

**Kent**: Yeah. So if you look on my GitHub, you'll see project project two project three project four new project new project two new project three new project I I'll take it I'll push it a certain amount and then the genie runs out of g runs itself out of options it can't make further forward progress and so I'll wipe it away start over I won't try and tweak I'll start over and say all right well if I implement things in a different order. If I implement with this markdown file or if I implement it with this commit hook, we collectively need to try absolutely everything. And some of those ideas are going to be sound stupid and are going to work out great. Some of the stupid sounding ideas are also going to be disastrous. But if we're willing to start over, then it doesn't matter. We're not really risking that much. That creative impulse is what's come back to me with the genie. This idea that I can go, I wonder what a B+ tree looks like in Go. Here's an alternative to the B+ tree. This adaptive radics tree. What does that look like? I can find out. I sit down with a genie. I can work it out. And then there's this artifact that wasn't there before that's there now because of my imagination and my work. And I had gotten fed up with the stupid minutia of programming. Oh, for that you need to have the version 7.1 of the upgrade the thing which then causes something else to break which causes something else to break which means that I can't use version 7.1. I have to I just hated that. getting emotionally invested, having an idea, getting emotionally invested, getting a ways in and realize I can't do this for no good reason. I hated that. And that that kind of blockage just doesn't happen to me now. And oh, so it's it this is hog heaven. I've got 40 years worth of ideas. This would be cool. Uh it's too big. That suddenly are back in play. And I'm having so much fun making things that are real.

</details>

**Host**: 我能看出来。而且你也在把这些成果和快乐分享给大家，Kent。这实在是太棒了。特别是这次我们终于能够面对面地进行录制。

<details>
<summary>Original English</summary>

**Host**: I can see it. And you're sharing it as well, Kent. This was awesome. Especially doing it finally in person.

</details>

**Kent**: 是的，这感觉非常棒。很高兴能够来到你的祖国，并在你家里和你坐在一起交流。我们就相聚在这里。

<details>
<summary>Original English</summary>

**Kent**: Yeah, it was great. Great to be able to sit down with you in your home country. Here we are.

</details>

### 播客尾声与总结反思

**Host**: 对我个人而言，这是一期非常特别的节目。录制地点在匈牙利布达佩斯，时间刚好就在 2026 年 Craft 大会开幕的前夕。这也是我第一次能够亲耳听到 Kent 如此详尽地回顾他从最初到现在整个职业生涯的故事，这种深入的探讨方式是他在之前的任何播客中都从未有过的。我脑海中不断回想的一件事，是 Kent 说的那句：“我们积累代码的速度，已经远远超过了我们积累信任的速度。”Kent [音乐] 真的非常擅长一语道破并总结像这样无比真实的道理。当你在理解代码所代表的业务领域时苦苦挣扎，并编写测试代码来证明你的理解是完全正确的时候，你最终会建立起对你自己编写的程序的信任。而当你与其他人一起并肩完成这些工作时，你也会同时建立起对这些同事的信任。Kent 的核心观点是，当你仅仅只是向一个 AI（或者像他称呼的那样，一个 Genie）发送提示词，然后你得到了一段能正常运行的代码，接着 AI 告诉你“一切都搞定了”的时候，上述所有这些建立信任的深层过程根本就不会发生。我也非常喜欢 Kent 在这整整 50 年来所保持的惊人一致性。无论是谈论 Smalltalk、设计模式、TDD 还是今天的 AI，他的直觉始终如一。那就是大胆地去尝试愚蠢的想法，并且永远不要害怕把它们全部抛弃然后重头再来。正如他自己巧妙的比喻，他是一个“摇树人”（tree shaker，寻找机会和创新的人），而不是一个“做果酱的人”（jelly maker，安于现状的人）。而 Kent 这种“摇树人”的原始冲动在面对 AI 技术时，又原封不动地体现在他大胆尝试各种看似荒谬事物的过程中。最后，我非常欣赏 Kent [音乐] 有多么的脚踏实地。人们不断地在问他，关于 AI 时代开发的新宣言究竟会是什么，而他的回答是，现在谈论这个还为时过早。敏捷宣言是在经过了整整 15 年的面向对象编程实践之后，才由像 Kent 这样的人将这些宝贵的经验教训总结出来的。在 AI 的世界里，[音乐] 情况依然在发生着快速的变化，Kent 也很坦诚地说，其实现在还没有任何人知道究竟什么是真正行之有效的。请务必查看下方显示的节目附注（show notes），了解为什么我和 Kent 都一致认为，麦肯锡（McKenzie）在想要衡量软件工程生产力的时候，根本就不知道他们自己到底在谈论些什么。同时，也请查看附注中有关“务实工程师”（the pragmatic engineer）对技术、软件工艺、TDD 以及其他主题的深度分析链接。如果你喜欢这期播客，请务必 [音乐] 在你最喜欢的播客平台以及 YouTube 上订阅我们。如果你还能花时间给本节目留下评分，那我们将致以最特别的感谢。[音乐]

<details>
<summary>Original English</summary>

**Host**: This was a special episode for me. Recorded in Budapest, Hungary, right before Craft Conference 2026. It was a first getting to hear Kent walk through his entire career start to present in a way he's never done in a podcast before. One thing I think back to is how Kent said, "We're accumulating code faster than we're accumulating trust." Kent is [music] so good at summarizing very true things like this. When you struggle through understanding domain, represented in code, and write tests that prove that you got it right, you end up trusting your program. And when you do that work alongside other people, you build trust with these people, too. Kent's point is that none of this happens when you just prompt an AI, or as a genie he calls it, and you get back the code that works, and the AI says, "It's all done." I also loved how consistent Kent has been across 50 years. Whether it's small talk, design patterns, TDD, or AI today, his instincts are the same. Try the stupid idea and don't be afraid to throw it all away and start over. As he put it, he's a tree shaker, not a jelly maker. And Kent's tree shaker impulse is right back on his trying stupid things with AI. Finally, I appreciate how grounded [music] Kent is. People kept asking him what the new manifesto for AI development is, and his answer is that is too soon. The agile manifesto took 15 years of doing object-oriented programming before people like Kent could summarize lessons with AI. [music] Things are still changing quickly and Kent is honest when he says that right now nobody knows what is working. Do check out the show notes below for how Kent and me both thought that McKenzie did not know what they're talking about when they want to measure software engineering productivity. Also check the show notes for related the pragmatic engineer deep dives on topics like tech, software craftsmanship, TDD and others. If you've enjoyed this podcast, please [music] do subscribe on your favorite podcast platform and on YouTube. A special thank you if you also leave a rating on the show. [music]

</details>