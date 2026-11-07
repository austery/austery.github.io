---
author: Ryan Peterman
date: '2026-04-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YPObBOwIrHk
speaker: Ryan Peterman
tags:
  - database-systems
  - postgres
  - distributed-systems
  - text-to-sql
  - operating-systems
title: 图灵奖得主 Mike Stonebraker 访谈：炮轰 Google、揭秘 Postgres 演进与 AI 时代的数据库困局
summary: 图灵奖得主、Postgres 之父 Mike Stonebraker 回顾了数据库架构从 Ingres 到 Postgres 的演进，尖锐批判了 Google 的 MapReduce 和 AWS 的产品策略。他深入探讨了 DBOS（数据库操作系统）的前沿实验，并用 Beaver 基准测试证明了当前大模型在真实企业数据仓库（Text-to-SQL）中 0% 准确率的尴尬现状。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people:
  - Mike Stonebraker
  - Larry Ellison
  - Ted Codd
  - Jeff Dean
  - Matei Zaharia
companies_orgs:
  - Oracle
  - Google
  - Amazon
  - Databricks
products_models:
  - Postgres
  - Ingres
  - MapReduce
  - Spanner
  - DBOS
media_books:
  - Readings in Database Systems
status: evergreen
---
### 数据库事业的起点

**主持人**: 计算机科学在未来可能不再是一个增长行业。坐在我面前的是 **Mike Stonebraker**。他是图灵奖得主，因对数据库系统的基础性贡献而闻名，比如创建了 **Postgres** 等。那个实现中最难的部分是什么？查询优化器。这在算法上非常困难。你如何识别那些不聪明的人？嗯，这其实很容易。他分享了来自其经验的有趣技术见解。在我们的基准测试中，大语言模型得到了 0% 的分数。你为什么这么不认同 **MapReduce**？那不是 Google 唯一愚蠢的地方。我很想听听你对数据库中未解决问题的看法，以及你认为未来会是什么样子。以下是完整剧集。我想谈的第一件事是 Postgres 是如何开始的故事。但在此之前，我想从头开始。你是如何进入数据库系统领域的？

<details>
<summary>Original English</summary>

**Host**: Computer science may well not be a growth industry going forward. This is Mike Stonebreaker. He's a Turing Award winner, famous for his fundamental contributions to database systems, like creating Postgres and more. What was the hardest part of that implementation? Query optimizer. It's just algorithmically difficult. How do you identify the people who aren't smart? Well, I mean, it's it's very easy. He shared interesting technical takes from his experience. On our benchmarks, large language models get zero percent. Why did you disagree so much with MapReduce? That wasn't the only thing Google was stupid about. I'm curious your thoughts on unsolved problems in databases and what you think the future might look like. Here's the full episode. The first thing I want to go over is the story of how Postgres got started. But for that, I kind of want to start the beginning. How did you get into building database systems?

</details>

**Mike Stonebraker**: 当我毕业时，我有幸被伯克利聘用，很明显，继续做我博士期间的研究是行不通的。无论在过去还是现在，如果你能得到一位熟悉内情的**导师**提携，你就会领先很多。当时还在世且依然活跃的 **Jean Wong** 把我收入麾下，说：“咱们一起做点什么吧。”那是 1971 年，也就是 **Ted Codd** 在 CACM 发表那篇开创性论文后的第二年。Jean Wong 说：“咱们来看看数据库相关的东西。”当时，竞争对手是一个叫 **Coddiesel** 的提案，你可能太年轻了，没听说过。那是一个低级别的“意大利面条式”网络提案，你通过跟随指针来执行查询。另一个替代方案是 **IBM** 的提案，即更高级的 **IMS**，现在仍在使用。它是分层数据，呈树状结构。你把数据组织成树。甚至在当时，IBM 已经意识到树状结构不够通用，无法解决很多人的问题。所以他们搞了个蹩脚的补丁，试图让它变成有限的网络结构。显然那是极其糟糕的手段。Coddiesel 提案除了级别低、极难调试外，还有各种负面属性。它还有一个特性：如果你现在的所谓 **Schema（模式）** 发生了任何变化，你基本上必须扔掉所有东西重新开始，因为它绝对扎根于物理层。相比之下，Ted Codd 的研究非常有道理。Jean 就说：“咱们造一个这小玩意儿吧。这显然是下一步值得尝试的方向。”于是，1972 年我在伯克利担任助理教授时，我们开始构建 **Ingres**。如你所知，如果你是助理教授，你有大约五年的时间来证明你是个大人物，否则他们要么开除你，要么给你终身教职。Ingres 就是我获得终身教职的门票，那是在 1976 年。这就是一切的起点。然后，还是偶然。当时很多人会构建原型，代码写得像学生作品——意思是你能跑通，但给别人就跑不通了。我们投入了前 90% 的精力让它能跑起来，然后出于某种原因，我们又投入了接下来的 90% 精力让它真正达到好用的程度。所以加州大学版的 Ingres 是真正好用的。在接下来的几年里，大约有一百所大学开始运行它，因为 **Unix** 变得非常流行，而这是一个运行在 Unix 上的免费数据库系统，所以在学术界很受欢迎。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: When I graduated, I had the good fortune of being hired at Berkeley, and it was clear I had to, you know, continuing what I did for my PhD was not going to go anywhere. Then, as well as today, you're way ahead if you get adopted by a mentor who knows the ropes. So Jean Wong, who is still alive and still still kicking, took me under his wing and said, "Well, let's do something together." And this was 1971, which was the year after Ted Codd wrote his pioneering paper in in CACM. Jean Wong said, "Let's let's take a look at database stuff." And at the time, the the competitors were a thing called the Coddiesel proposal, which you're probably too young to have ever heard of. And so it was a low level spaghetti network proposal where you where you executed queries by following pointers. And then the the alternative was the IBM proposal, which was a higher a thing called IMS, which is still available. And it's hierarchical data. It's a tree. You're organized your data as trees. And even at the time, IBM realized that trees were not general enough to to solve many people's problems. So they hacked on a way to make it a limited network structure. So it was clear that was a horrible hack. The Coddiesel proposal had all kinds of bad properties besides being low level and and really hard to debug. It also had the property that if anything changed in your what's now called your schema, you basically had to throw away everything and do it all again because it was absolutely rooted at the physical level. Whereas Ted Codd stuff made perfect sense. And so Jean said, "Well, let's build one of these puppies. That's clearly the next thing to try." So we started building Ingres in 1972 while I was an assistant professor at Berkeley. As you know, if you're an assistant professor, you have to you have about you get five years to prove that you're a big shit, and they fire you or they give you tenure. So Ingres was my ticket to getting tenure, which happened in 1976. That was where it started. And then again, you know, happenstance. At the time, you know, a lot of people would build prototypes, which were sort of studenty like code, which means you could get it to run, but if you gave it to anybody else, they couldn't. So we put in the first 90% to get something we could run, and then for whatever reason, we put in the next 90% to get it to where it really worked. So the University of California version of of Ingres was really worked. And so over the next couple years, about a hundred universities started running it because Unix became the big thing, and so this was a database a free database system that ran on Unix, and so it was quite popular in in the academic world.

</details>

### 从学术界到商业竞争

**Mike Stonebraker**: 我们开始在伯克利接待大量访客，他们会说：“天哪，这东西看起来真的很酷。你们最大的 Ingres 应用是什么？”我们被迫承认：“不是很大。”当亚利桑那州立大学考虑在他们所有的 40,000 名学生记录数据上运行 Ingres 时，这一点被无情地揭穿了。他们能忍受必须从贝尔实验室获得一个不受支持的操作系统，也能忍受必须运行来自伯克利这帮家伙的不受支持的数据库系统，但当他们意识到 Unix 上没有 **COBOL** 可用时，项目彻底告吹，因为他们是 COBOL 用户。不受支持的操作系统、不受支持的数据库、没有 COBOL，这注定了我们毫无价值。显然唯一的出路就是成立公司。于是在 1980 年，我们获得了当时形式的风险投资，成立了 **Ingres Corporation**，将 Ingres 迁移到 **Dex VMS**（一个真正的操作系统），我们有了一家真正的公司来支持 Ingres，这就是商业征程的起点。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: And so we got started getting you know lots of visitors at Berkeley who would say, "Gee, this is really nifty looking stuff. What's the biggest biggest Ingres application you have?" And we'd be forced to say, "Not very big." And so this was brought home in spades when Arizona State University considered running Ingres on their student records data, all 40,000 students worth, and they could get over that they had to get an unsupported operating system from Bell Labs. They could also get over they had to run an unsupported unsupported database system from these guys at Berkeley, but the project went down in flames when they realized there was no COBOL available for Unix, and they were a COBOL shop. So unsupported operating system, unsupported database system, no COBOL doomed us to you know irrelevance. And it was clear the only way out of that was to start a company. And so in 1980, we got venture capital as it existed then and started Ingres Corporation to move Ingres to to Dex VMS, you know a real a real operating system, and we had a real company that would support Ingres, and that was the start of the commercial journey.

</details>

**主持人**: 我看到 Ingres 曾与 **Larry Ellison** 在 **Oracle** 提供的产品竞争。我也看到 Ingres 确实比他们当时提供的产品要好，但他们仍然在以某种方式竞争。他们是怎么竞争的？

<details>
<summary>Original English</summary>

**Host**: I saw that Ingres was competing with Larry Ellison's offering at Oracle. Yes. I saw that Ingres was was certainly better than what they were offering, but they were still competing somehow. How how did they compete?

</details>

**Mike Stonebraker**: Larry Ellison 是个极出色的推销员，他当时能让“现在时”和“将来时”变得无法区分，所以他基本上是在**欺骗客户**。他会发运还没法用的东西，让最初的客户帮他调试。我认为他从事的是我所认为的非常阴暗的商业行为，但对客户撒谎是不可原谅的。例如，有一个叫**引用完整性 (Referential Integrity)** 的东西——如果你开除了一名员工，而他是某个部门的最后一个人，你是想删除这个部门，还是让它变成一个幽灵部门？就是诸如此类的事情。Ingres Corporation 实现了引用完整性。Oracle Corporation 写了两页说明书说：“这是引用完整性的定义”，大家都同意这个定义，但在底部写着：“尚未实现”。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Larry Ellison is a fabulous salesman, and he at the time he he would he made present tense and future tense indistinguishable, and so he basically lied to customers. He would ship stuff that didn't work and have his initial customers help him debug it. So I think he he engaged in what I consider very shady business practices, but lying to customers I think is is you know unconscionable. So for instance, there was a thing called referential integrity, which is if you if you fire an employee and he's the last person in a given department, do you want to delete the department or do you want to have it be a department a ghost department? It's it's all that kind of stuff. And so Ingres Corporation implemented referential integrity. Oracle Corporation wrote two manual pages that said, "Here's the definition of referential integrity," which everybody agreed to, and then he then down at the bottom it said, "Not yet implemented."

</details>

**主持人**: 有趣。我采访过曾在 Sun Microsystems 工作的人，他们也有类似的观点，认为 Larry Ellison 有点阴暗。这似乎是一个共识。我还看到你在别处提到过，当 Oracle 收购 **MySQL** 时，大家都对此感到害怕并转向了 Postgres。那是 Postgres 取代 MySQL 成为首选开源关系型数据库系统的转折点。你创建了 Ingres，里面有很多技术创新，比现有的产品都要好，但最终它消失了，你又开发了 Postgres。Ingres 没做到的、而 Postgres 会做的是什么？

<details>
<summary>Original English</summary>

**Host**: Interesting. Yeah, I had interviewed someone who worked at Sun Microsystems, and they had a similar opinion that they Larry Ellison was a little bit shady. So it seems to be a commonality. I also saw somewhere else in something that you had said was that when Oracle acquired MySQL, that everyone kind of got afraid of that and moved to Postgres. That was the genesis of Postgres replacing MySQL as the preferred open source relational database system. So you you created Ingres, and there was a lot of technical innovations in it, so that it was better than the the incumbents, but ultimately it it went away, and you developed Postgres. What what was the thing that Ingres didn't do that Postgres would do?

</details>

### Postgres 的核心创新

**Mike Stonebraker**: 最初引导我们的是：学术版 Ingres 的最初理由是我们要支持邻座教授 Praveen Varia 想要的**地理信息系统 (GIS)**。为了支持 GIS 系统，你需要点、线、多边形、线组之类的东西。很明显 Ingres 做不到，因为我们在 Ingres 中放入的数据类型是标准类型：整数、浮点数、文本字符串，你无法在其之上高效地支持 GIS 类型。作为 GIS，学术版 Ingres 是彻底失败的，这一直印在我们的脑海里。另一件事——这有点脱离时间顺序，但有助于说明问题——大概在 1985 年，ANSI 刚刚提出了关系数据库的日期和时间标准，所以商业版 Ingres 按照标准的格里高利历实现了日期和时间。当时我既参与商业版 Ingres，又仍在加州大学当教授。我接到一个 Ingres 客户的电话说：“你们的日期时间实现错了。”我说：“哈？我们实现了格里高利历，你可以做减法，每个月有 30 或 31 天，除了 2 月，还有闰年。日期减法完全符合预期。”但他却说：“那不是我想要的。”在他的特定领域，他处理的是**债券金融工具**，由于某种原因，无论月份多长，每个月获得的利息是一样的。他有购买日期和出售日期，他想做减法，乘以息票率，算出我们支付的利息。但当然，他的减法版本是：3 月 15 日减去 2 月 15 日等于 30 天，因为那是他日历的定义。所以他必须把两个日期取回用户代码，在用户代码中做减法，再把答案存回去，效率损失了两三倍。他问：“为什么我不能用我想要的定义来重载你的减法定义？”当然，在 Ingres 中这是硬编码的。这个问题和想要点、线、多边形是一样的。所以 **Postgres** 被设计成具有**可扩展的类型系统**，你可以拥有任何你想要的数据类型，而且非常高效。这就是 Postgres 的主要精髓：**灵活性**。如你所知，在商业数据处理中，大多数人满足于标准数据类型，但关系型数据库开始扩展到各种其他地方。所谓的**抽象数据类型 (ADT)** 或存储过程具有巨大的适用性，这就是 Postgres 的亮点。我们还支持了当时 AI 专家想要的**继承**。我们还支持了**时间旅行**，但那个实现烂透了，一段时间后就被删除了。Postgres 中有大量非常精妙的东西。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: The big thing that guided us at the very beginning was the the original reasoning for the academic version of Ingres was we were going to support a geographic information system that the neighboring professor Praveen Varia wanted. And so to support a GIS system, you need points, lines, polygons, line groups, that sort of stuff. And it was clear that Ingres couldn't do it because the data types we put into Ingres were the standard ones: integers, floats, text strings, and you couldn't support you couldn't efficiently support GIS types on top of that. So as a GIS, the academic version of Ingres was a complete failure, and that was in the back of of our mind. The other thing that happened this is a little out of chronicle chronological sequence, but it helps make the point is that the commercial version of Ingres, I think, around 1985, you know, there was ANSI had just proposed a date and time standard for relational databases, and so commercial Ingres implemented date and time, you know, using the standard Gregorian calendar. And so I was associated with the commercial version of Ingres as well as I was still at the University of California as a professor. So I got a call from from an Ingres customer who said, "You know, you implemented date and time wrong." And I said, "Huh? We implemented the Gregorian calendar, and you can subtract, and you know, if it has you know days have 30 or 31 months except for February, except for leap years. So subtraction on dates works exactly the way you would expect it to." But he said, "That's not what I want." In his particular world, he he said he was he was dealing with with bond financial instruments, and for some reason, I mean, you got the same amount of interest on on his financial bonds during each month, no matter how long the month was. So he had the date you bought the bond, the date you sold the bond. He wanted to do a subtraction, multiply it by the coupon rate, and say that's what that's the interest we paid you. But of course, his version of subtraction was March 15th minus February 15th is 30 days, because that's the definition of his calendar. And so he had to retrieve two dates out to user code, do the subtraction in user code, put the answer back, and it cost him a factor of two or three in efficiency. And he said, "Why can't I just overload your definition of subtraction with what I want?" And of course, with Ingres, it was hard coded, and the problem was this is a case where you wanted bond time, just like you wanted points, lines, and polygons. And so Postgres was engineered to have an extendable type system, so you could have whatever data types you wanted, and they were very efficient, and that was the main gist of Postgres was that it had that flexibility. And as you know, in business data processing, a lot most people were happy with the standard data types, but relational databases started to spread to all kinds of other places. What are called abstract data types or you know stored procedures, you know bunch of names they're called, you know had had great applicability, and so Postgres that was that was the big thing in Postgres. We also Postgres also supported what the AI guys at the time wanted in the way of inheritance. We also supported time travel, but the implementation absolutely sucked, and it got taken out after a while. So there were a huge number of of really nifty things in Postgres.

</details>

### 人才、架构与“一刀切”的谬论

**主持人**: 你提到你想雇佣非凡的软件工程师，我想你以前说过，找这些人对你来说没困难。你在招聘中如何识别那些非凡的人？

<details>
<summary>Original English</summary>

**Host**: You mentioned you you want to hire extraordinary software engineers, and I think you've you've said before that you have no trouble finding those people. How do you identify those people in your hiring that they're the extraordinary ones?

</details>

**Mike Stonebraker**: 通常很明显。我对事情的难度有很好的直觉。如果他们在学校里完成的工作量是我认为合理的 3 倍，那他们就很不可思议。另一方面，你有一句很有意思的话，我记下来了：“我受不了那些不怎么聪明的人。跟他们说话很具挑战性。”你如何识别不聪明的人？

<details>
<summary>Original English</summary>

**Mike Stonebraker**: It's usually pretty obvious. I mean, I have a good feel for how difficult stuff is. If they get three x the the amount done, you know, in school that I think is reasonable, then then they're incredible. On the flip side, you had this interesting quote. I wrote I wrote it down. He said, "I can't stand people who are who aren't really smart. It's challenging to talk to them. How do you identify the people who aren't smart?"

</details>

**Mike Stonebraker**: 唔，这很容易。你跟他们聊聊，很快就能发现他们聪不聪明。比如：“你的硕士论文写的是什么？你做了什么？它是怎么运作的？你怎么处理错误条件的？你有多少个进程？为什么不用线程？”你会问他们非常深刻的技术问题。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Well, I mean, it's it's very easy. You talk to them, and and it it rapidly you can rapidly surface whether they're smart or not. You know, what was your master's thesis? What did you do? Well, how did it how did it exactly work? Well, how did you deal with error conditions? How many processes did you have? Why didn't you use threads? I mean, you you ask them technical deep technical questions.

</details>

**主持人**: 你做过一次演讲，好像后面还有篇论文，观点是“**一刀切 (One size fits all)**”的数据库系统并非最优。“一刀切”其实一个都不合适，你真正想要的是针对特定需求的数据库解决方案。你现在看到哪些数据库产品是“一刀切”的？

<details>
<summary>Original English</summary>

**Host**: You you gave a talk, and I think there's also a paper behind it of this idea that one size fits all database systems not optimal. One size actually fits none, and that what you really want is database solutions that target specific needs. What database offerings you see today that are one size fits all?

</details>

**Mike Stonebraker**: 2004 年我写那篇论文时，我们有一个学术项目，就是构建后来的 **Streambase**。流处理引擎看起来一点也不像关系型数据库。我们还有关于数据仓库**列存 (Column Stores)** 的构思，后来由 **Vertica** 普及，这看起来和行存完全不同。这里有三种截然不同的实现，彼此毫无相似之处，而在每种情况下，它们都比其他竞争对手快一个数量级。所以很明显，如果你运行的数据库系统不是为你的业务类型设计的，你就会损失一个数量级的性能。我认为这在今天依然成立。**ClickHouse** 是列存；**Pinecone** 在基于文本的向量处理上比用户定义类型快。我认为在多个实现之上放一个通用的解析器并无困难。Postgres 到目前为止选择了不这样做。他们没有实现列存，所以在大规模数据仓库上没有竞争力。他们也没有多节点支持，对于拥有大数据仓库的人来说，那是基本要求。我认为今天和以往一样正确。真实情况是：如果你想开始做一个数据库项目，答案是选 Postgres，那里有庞大的编程社区和各种类型实现，它是免费的，人才也好找。所以它是“**最低公分母**”的绝佳选择。在你试图达到每秒百万次事务或支持 PB 级数据仓库之前，它都表现良好。在低端，它是绝对正确的“一刀切”方案。在高端，那就不对了。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: In 2004, when I wrote the paper, we had an academic project which was building what became Streambase, and so a stream processing engine looks nothing like a relational database, and we had the gist of an idea for column stores for the for data warehouses, which was popularized by Vertica, looks nothing like a row store. So here were three wildly different implementations that had no resemblance to each other, and in each case, they were an order of magnitude faster than the other guys. So it's pretty clear that one side you know that in with those three instances, you give up an order of magnitude when you're running a database system that isn't that isn't architected for your kind of stuff. I think that's still true. I mean, I think ClickHouse is a column store, Pinecone is faster than user defined types on on text based vector processing, and so I think it's it's still very much the case, and I think there's no difficulty putting a common parser on top of multiple implementations. Postgres has so far chosen not to do that. They don't implement a column store, and so I think they are not they are not competitive, you know, on sizable data warehouses. They also don't have multi node support. Again, for people with big data warehouses, that's table stakes. So I think it's just as true today as it ever was. I think that what is true is that if you want to get going, you have a database problem. You know, the answer is choose Postgres, and there's a huge programming community, all kinds of all kinds of you know data type implementations. It's free, and you can find Postgres talent easily and get going. And and so I think it's it's it's a great choice for lowest common denominator. And until you're trying to do a million transactions a second, it works just fine. Until you're trying to support a petabyte data warehouse, it it I say the low end, it's absolutely the right one size fits all. At the low end, it's Postgres. At the high end, that's just not true.

</details>

### GPU、索引与查询优化器

**主持人**: **GPU** 是否提供了优化数据库的新机会？

<details>
<summary>Original English</summary>

**Host**: GPUs do they make available some new opportunities to optimize databases?

</details>

**Mike Stonebraker**: 可能吧，但我认为大挑战在于 GPU 是 **SIMD**（单指令多数据），那是**索引**的天敌。每当索引是正确答案时，GPU 可能就不是个好主意。你还必须设计架构，确保从存储出来的带宽不是瓶颈。如果它们只是 CPU 的插件，连接 GPU 和 CPU 的总线通常就是瓶颈。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Probably, but I think the the big challenge is that GPUs are you know SIMD SIMD you know single instruction multi data, and that's that's the anathema of indexing. And so whenever indexing is the right answer, they're probably not a good idea. And I think also you've got to architect them so that the so that the bandwidth so that the bandwidth from storage is is not not the bottleneck, and so. If they're an add-on to the CPU, as often as not, the bus connecting it to the GPU to the CPU is a bottleneck.

</details>

**主持人**: 你能解释一下为什么在有 SIMD 的情况下索引就不那么有效了吗？

<details>
<summary>Original English</summary>

**Host**: Can you explain why indexing would be not as effective when there's SIMD?

</details>

**Mike Stonebraker**: 假设我在找 Ryan 的薪水，我有一个 **B-tree**。你会去 B-tree 的根部，找到包含 Ryan 两侧的划分点，跟随指针。这肯定是一次内存访问。然后你再做一遍，重复三四次。这很难并行化。所以结论是索引无法很好地并行化。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: So let's let's say I'm I'm looking for Ryan's I'm looking for Ryan's salary and I have a B-tree. So you go to the root of the B-tree. You find you find the divider that has both sides of Ryan. You follow the pointer. That's a memory access for sure. Then you do it all again. And you do this like three or four times. So that doesn't parallelize well. So the answer is indexing doesn't parallelize well.

</details>

**主持人**: 你提到了 B-tree。当你第一次实现那个版本的 Ingres 时，所有这些都是手写的吗？因为我想象当时可能还没有现成的 B-tree 库之类的。

<details>
<summary>Original English</summary>

**Host**: You mentioned B-trees. When you first implemented that first version of Ingress, did you write all of that by hand? Because I imagine there's probably not some existing B-tree library or something.

</details>

**Mike Stonebraker**: 是的，最初版本的 Ingres 全是从零开始写的。那个实现中最难的部分是什么？**查询优化器**。为什么它这么难？它很难，纯粹是算法上的难。如果你问几乎任何资深数据库程序员什么是最难的部分，他们依然会说是优化器。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Yeah, we wrote the original version of Ingress was all written from scratch. What was the hardest part of that implementation? The query optimizer. And why was that hard? It's tough. It's it's just algorithmically difficult. It's still if you ask most any senior database programmer what's the hardest hardest part, they'll still say the optimizer.

</details>

### 炮轰 Google 与 MapReduce

**主持人**: MapReduce 在 2000 年代初问世，风靡了数据界。人们对它印象深刻，认为 Google 真的很懂行，这是继切片面包以来最伟大的发明。但当我查阅文献和你当时的看法时，你似乎非常不认同。你为什么这么反对 MapReduce？

<details>
<summary>Original English</summary>

**Host**: MapReduce came out at some point in the early 2000s, and it kind of took the data world by storm. People were really impressed by it. They thought Google really knows what they're doing. This is the best thing since sliced bread. But it seems like when I look at the literature and what you thought at the time, you kind of disagreed heavily. Why did you disagree so much with MapReduce?

</details>

**Mike Stonebraker**: 唔，我认为有很多不太开窍的人说：“Google 非常聪明，他们一定知道自己在做什么，所以他们说什么我们就做什么。”于是他们就投入到 **Hadoop** 的怀抱。但 Hadoop 的效率低得离谱。当时，包括 Dave DeWitt 在内的参与我们 2011 年论文的人都了解分布式数据库，知道你可以用分布式数据库系统把 Hadoop 打得落花流水，这基本上就是那篇 2011 年论文所说的。当然，那是事实。但那不是 Google 唯一愚蠢的地方。Google 当时还认为**最终一致性 (Eventual Consistency)** 是处理并发控制的正确方法。在那段时间里，Google 从高层设定了这一信条。所有的数据库专家都说：“你们疯了吗？”因为它只解决了一类特定问题，而且在实践中极少发生。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Well, I think there were a lot of not very enlightened people who said Google Google is really smart. They must know what they're doing. And so we'll do whatever they say. And so they would they would they would engage in Hadoop or engage with Hadoop. But Hadoop is ridiculously inefficient. And so at the time, you know others, you know Dave DeWitt and others who who were involved in our 2011 paper, we understood distributed databases and understood that you could beat the heck out of Hadoop with a distributed database system, which is basically what that 2011 paper says. And of course it was it's true. And but that wasn't the only that wasn't the only thing Google was stupid about. So Google also had the opinion that eventual consistency was the right way to do concurrency control. And so that was postulated from on high by Google all during that same period of time. And it wasn't and all the database people said you know you're out of your frigging mind because it doesn't it solves one particular kind of problem but only and that very rarely occurs in practice.

</details>

**主持人**: 他们为什么追求最终一致性？

<details>
<summary>Original English</summary>

**Host**: Why did they pursue eventual consistency?

</details>

**Mike Stonebraker**: 想法是你有一个东海岸数据库和一个西海岸数据库，互为副本。你希望它们保持一致。如果你说：“我要做一个事务，把西海岸仓库的小部件数量减一。”在提交该事务之前，我得更新东海岸仓库，发消息过去再等回执来更新。为了确保万无一失，还需要一轮消息来确保两者都正确执行了提交。做**分布式提交**非常昂贵，现在依然如此。所以当时的思路是：你只在西海岸更新，减一，然后异步发送一条消息，不在事务中。这样东海岸仓库最终也会减一。与此同时，如果你在东海岸减掉了某种食品，你也发异步消息。最终一切都会结算清楚。但如果你被允许减到零以下，那么如果东海岸和西海岸的人同时卖掉最后一个部件，最终仓库状态将是 -1，有人拿不到东西。如果你像亚马逊那样说“通常 24 小时内发货”，也许你被允许超卖，但大多数企业不能这么做。所以最终一致性行不通。我们刚才聊到**引用完整性**。销售系统中的引用完整性约束是“库存大于 -1”。而在最终一致性下这会失败。Google 的 **Jeff Dean** 终于想通了这一点。当他们做 **Spanner** 时，Spanner 采用了一个传统的事务系统。Google 完全抛弃了最终一致性，也完全抛弃了 MapReduce。权衡基本上是：**正确性 vs 性能**。或者说是性能 vs 数据完整性。如果你不在乎你的数据，你才愿意处理那些糟糕的情况。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Okay, well the idea is that you have an East Coast database and a West Coast database and they're replicas. So you want them to be the same. If you say I'm going to do a transaction, I'm going to decrement by one the number of widgets in the West Coast warehouse. Then I'm going to before I commit that transaction, I'm going to update the East Coast warehouse, pay pay a message over and back to update it. And then to make sure everything goes well, it takes it takes another round trip a message to make sure that both of them actually do the commit correctly. So it's expensive to do a distributed commit. It still is. And so the idea was well you you do the you do the West Coast update, you decrease the widgets by one, you just send a message asynchronously and not in a transaction. So that eventually the East Coast warehouse gets decremented by one. So meanwhile, if you're on the East Coast, you you decrement you know foodstuffs by one, you send an asynchronous message. Eventually the West Coast gets it. And eventually everything settles out. So if you're allowed to to go below zero, then what will happen is if the East Coast guy and the West Coast guy simultaneously sell the last widget, then then eventually the state of the warehouse will be minus one and somebody won't get their widget their widget. And so if if you're allowed like Amazon to say usually ships in 24 hours, then maybe you're kind of allowed to oversell, but most enterprises can't do that. And so eventual consistency just doesn't work. So we talked a million hours ago about referential integrity. So referential integrity in a sales system is integrity constraint is stock is greater than minus one. And that fails with eventual consistency. And so Jeff Dean of Google finally figured that out. And when they did Spanner, Spanner had a conventional transactional system. And so Google completely abandoned eventual consistency and completely abandoned MapReduce. So the trade-offs basically correctness or performance. So it's performance versus data integrity. And if you don't care about your data, then you're willing to deal with with bad things happening.

</details>

### DBOS：将操作系统存入数据库

**主持人**: 你从学术界显著地影响了工业界，我有个想法：为什么不直接去工业界工作？为什么你更喜欢留在学术界发挥影响力，而不是去 AWS 当个杰出工程师之类的？

<details>
<summary>Original English</summary>

**Host**: You've influenced industry significantly from academia, and my one thought that I had is what why not work directly in industry or why why do you prefer the position of being in academia and having influence in the way that you have versus just taking a job at AWS or something like that, being a very distinguished engineer there?

</details>

**Mike Stonebraker**: 因为那会给你找个老板，会有公司规则，限制你的发表能力，限制你去参加会议演讲，限制你去窥探各种竞争对手正在做的事。但最重要的是，我真的很喜欢待在初创公司。在商业版 Postgres 被 Informix 收购后，我在 Informix 兼职，那是一家 2,000 人的公司，我觉得自己无法发挥作用，因为它官僚主义严重，总裁想要什么就有什么。我想我不适合搞政治，我不擅长那个，而且我很难与我认为愚蠢的人互动。所以我对大公司有些抵触。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Because that gives you a boss, and that gives you company rules, limits your ability to publish, limits your ability to go talk at conferences, limits your ability your ability to go go poke at what what various competitors are doing that they won't tell their competitors. But mostly, I really like being in startups, and I and I after the commercial version of Postgres got acquired by Informix, you know, I was working part time for Informix, which was a 2,000 person company, and I didn't feel like I could make a difference because it was bureaucratic and and whatever the president wanted, he got. So I think I'm just not cut out for I'm not cut out for politics. I don't do that very well, and I have a hard time interacting with people I think are dumb. And that again, so I guess I I have I have some problems with with big companies.

</details>

**主持人**: 我想聊聊 **DBOS**。我觉得那是一个非常有趣的技术模型。你能解释一下什么是 DBOS 吗？

<details>
<summary>Original English</summary>

**Host**: I I wanted to talk a little bit about dbos. I just thought it was a really interesting technical model. Can you explain what dbos is?

</details>

**Mike Stonebraker**: 我们在 2019 或 2020 年左右开始了那个学术项目。精髓在于，当时斯坦福大学教员、Databricks 创始人之一、Spark 的最初创建者 **Matei Zaharia** 提到，Databricks 基本上是在云端运行人们的 Spark 任务。他说在任何给定时间，我们可能都在调度一百万个 Spark 任务。所以我们得写一个能在百万规模下决定下一个运行谁的调度器。他说：“我们尝试了所有操作系统专家写的调度器，但都无法扩展。”所以我们把所有的调度数据放进了一个 Postgres 数据库，基本上是用一个 Postgres 应用来做调度。然后我意识到，操作系统中做的大多数事情本质上都是在大规模管理数据，你应该使用数据库技术来做这件事。那为什么不干脆**用数据库系统替换掉 Linux 的上半部分**呢？这就是学术项目的核心，我们在 2020 年代初在伯克利和斯坦福研究它，非常成功。在过程中，斯坦福的同事们编写了一个 JavaScript 扩展。如果你在做一个编程语言，运行在本质上是数据库的操作系统之上，那么显而易见的事就是把所有的状态都放在数据库里。我们有创新的编程语言模型、创新的操作系统模型。当然接着就是：能否开个公司？VC 们一致说：“如果你觉得能取代 Linux，那你是在做梦。不过，这套编程语言的东西真的很精妙。”我们有类似于 JavaScript 扩展的东西，允许任何程序拥有数据库系统的所有优良特性：持久化、事务、故障转移。所以我们在 2023 年获得了投资成立了 **DBOS Incorporated**。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: We started the academic project in 2019, 2020, something like that. And the gist of it was at that point Mate Mate Zaharia, who was on the faculty at Stanford, was also one of the founders of Databricks, was the original creator of Spark. And so he said at the time Databricks you know basically was running people's Spark jobs on the cloud. And so he said at any given time we might be orchestrating a million Spark jobs. And so we have to write a scheduler that's going to decide who to run next at scale a million. And he said there was no we tried all the all the schedulers written by the OS folks and they they couldn't they didn't scale. So we put all the scheduling data in a Postgres database, and basically a Postgres application was doing scheduling. And then it sort of clicked that by and large most everything you do in an operating system is managing data at scale, and you should do that using database technology. So why don't we just replace at least the upper half of Linux with a database system? So that was the gist of the academic project, and we worked on it at Berkeley and Stanford in the early early 20s, and it was it was very successful. It clearly it clearly worked. And in the process, the Stanford folks wrote an extension to JavaScript so that you could program. You need some programming world that can can talk to your implementation. So if you're doing what amounts to a programming language, and you're running on top of what amounts to an operating system that is a database, then the obvious thing to do is put all your state in the database, and that's exactly what they did. And so we had an innovative programming language model, an innovative operating system model, and and of course then the idea was well can we start a company? And so we talked to the VCs who to a person said you're you're dreaming if you think you're going to displace Linux. However, this programming language stuff is really nifty. We had what amounted to extensions to JavaScript that would allow any any program to have all of the nice features of a database system. You know stuff was durable. You could have transactions. If it failed, you'd fail over. You know it's all that nifty stuff. So we got funded to start a company in 2023, and that was dbos incorporated.

</details>

### AI 智能体与 Text-to-SQL 的真相

**Mike Stonebraker**: 目前大约三分之二的客户在做 **智能体 AI (Agentic AI)**。这意味着他们有一个大语言模型，周围环绕着一堆增加信号的东西。到目前为止，大多数智能体 AI 都是只读的，比如预测 Ryan 是否会是一个好客户。但我认为这个世界很快会转向使用智能体处理**读写应用**，这会让它们变得非常“数据库化”，而 DBOS 在这方面表现极其出色。例如，如果你想让一两个智能体把 100 美元从我的账户转到你的账户，你需要借记我的账户，贷记你的账户，这两个智能体必须同意提交，或者全部回滚，也就是说工作流需要是**原子性 (Atomic)** 的。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: And I think the key thing so far is probably two thirds of the customers are doing agentic AI, which means that they have a large language model surrounded by a bunch of stuff that that adds more signal. And so far, most of agentic AI is read only, meaning you want to produce a prediction for whether Ryan is is going to be a good customer or not. And so that just runs some stuff and then produces a new thing that's given to somebody. So basically read only, which means that you're not you're not actually updating Ryan's credit rating, or and so I think fairly quickly this the whole world is going to move to using you know agents to do read write applications, and that's going to make that's going to make them very very databasey, and dbos does that stuff really really well. And so you know for instance if you want to write an agent or two agents that move $100 from my account to your account, and so you debit my account, you increment your account, and these two agents have to agree to commit, or you have to back everything out, which is to say the workflow needs to be what I call atomic, which is it all happens or it looks like it never happened.

</details>

**主持人**: 我对数据库中未解决的问题很好奇，你认为未来会是什么样子？

<details>
<summary>Original English</summary>

**Host**: I'm curious your thoughts on unsolved problems in databases and what you think the future might look like.

</details>

**Mike Stonebraker**: 过去三年我们开始研究大语言模型擅长什么。我们一直在尝试让所谓的 **Text-to-SQL** 在真实世界的数据库，特别是真实世界的数据仓库上运作。我们在四个不同的生产数据仓库上尝试了这项技术，获取了实际运行的工作负载。大语言模型理应擅长这个。现有的 Text-to-SQL 基准测试如 **Spider** 或 **Bird**，最好的 LLM 系统表现不错，准确率在 80% 以上。看起来挺好，对吧？

但在我们的基准测试中，**大语言模型得到了 0% 的分数**。如果你用 RAG 和所有技巧增强它们，分数会升到 10%。如果你在提示词中给出 `FROM` 子句（即所有需要访问的表和连接子句），准确率会升到约 35%。结论是：这玩意儿还没准备好进入实际应用，而且在相当长一段时间内（如果不是永远的话）也不会。

为什么差别这么大？
1. **数据仓库数据不在训练集里**。有个说法：如果你没见过这些数据几次，你没机会重构它。
2. **查询复杂度**。Spider 和 Bird 的查询大概 10 到 20 行 SQL，而真实世界的数据仓库是 **100 行 SQL**。
3. **Schema 很乱**。基准测试里的表名和列名都很直观。但在真实数据仓库中，人们总是有物化视图，有冗余，列名经常是像 `_z_blah` 这种完全不直观的名字。
4. **特有数据**。比如 MIT 有个一月份的“J-term”。这种不在通用语料里的特有数据会让大模型完全抓瞎。

所以我们发布了自己的基准测试，叫 **Beaver**。如果你觉得自己真的很擅长 Text-to-SQL，去试试真实的基准测试，别试假的。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Okay, so I think two different things that I'd like to talk about. The first one is like everyone else, three years ago we started to look at what were large language models good for. So we've been trying to get what's now called text to SQL. To we've been we've been trying to make it work on real world databases, especially real world data warehouses. So we've been trying the technology on four different production databases warehouses where we've gotten the workload the actual workload that's run and you know from the actual users using the system, and we've gotten them to reverse engineer the text that corresponds to that SQL. So we have text and SQL for we have four benchmarks. [...] Well, on our benchmarks, large language models get zero percent, and if you enhance them with rag and and all the tricks goes to 10 percent, and if you give as a prompt the from clause, in other words, all the actual tables that need to be accessed and all the actual join clauses that need to be joined, then accuracy goes to about 35 percent. So the definition of this stuff doesn't is not ready for prime time and not going to be for a while if ever. So what what's the difference? Number one data warehouse you know LLMs are trained on the pile. Data warehouse data is not in the pile... Number two, query complexity... Number three, the schema in Spider and Bird is clean... In data warehouses... column names are often underscore z underscore blah... So we've been so what do you do? So well, first of all, we published our benchmark. It's a thing called Beaver, which is an anonymized and abstracted version of these four data warehouses. And so if you think you're really good at doing text to SQL, try a real benchmark, not a fake one.

</details>

### 给年轻人的忠告

**主持人**: 如果你能回到刚毕业的时候，给自己一些建议，你会说什么？

<details>
<summary>Original English</summary>

**Host**: If you could go back to yourself when you just graduated, give yourself some advice, knowing what you know today, what would you say?

</details>

**Mike Stonebraker**: 当我最初在伯克利接下这份工作时，没想太多就说：“咱们写个数据库系统吧。”我们对数据库一无所知，对实现一无所知。我们不是像 Bill Joy 那样熟练的程序员。开始做这么疯狂的事真的很疯狂。但你努力，你让东西运转，你在过程中学习。所以答案是：**跳出框架思考，思考疯狂的想法并尝试去做**。

对我来说，更好的问题是：如果你今天刚开始，你会主修什么？因为我认为**计算机科学未来可能不再是一个增长行业**，我不确定我会建议 18 岁的孩子主修计算机。我认为医疗保健和建筑行业是更稳妥的选择，其他一切看起来风险都大得多。如果你快拿到博士学位了，那就选最有名望的工作，找个愿意帮你的导师，然后选一个不随大流的领域去钻研。

我和我妻子都曾对孩子说过：“追随你的激情，钱总会有的。”但我一分钟也不信这话。不过我想那是你必须告诉孩子和孙子的话。我妻子是个例子，她有计算机本硕学位，但她想当老师，父母说那赚不到钱。我想她从此一直后悔那个决定。她对计算机没有激情。所以，**找个你热爱的事情，你至少不会饿死**。你可能赚不到大钱，但比起做没激情的事，你更有可能获得幸福。

<details>
<summary>Original English</summary>

**Mike Stonebraker**: Back when I first took the job at Berkeley, without thinking about it much, we said let's write a database system, and we we knew nothing about databases, nothing about implementations. We were not skilled programmers like Bill Joy. So starting off doing something that was that crazy was really pretty crazy. [...] the better question is if you were starting out today, what would you major in? Because I think you know computer science may well not be a growth industry going forward, and I'm not sure I would recommend 18 year olds to major in computer science. I mean I think health healthcare and and the building trades are are safe bets, and everything else looks much riskier. [...] Both my wife and I said follow follow your passion. Somehow the money will work out, and I don't believe that for a minute. But I think that's what you have to tell your kids. [...] find something you're passionate about and and you will you know either you won't starve. You may not make a lot of money, but I think chances are you'll be happier than if you do something you're not passionate about.

</details>