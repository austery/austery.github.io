---
author: The Pragmatic Engineer
date: '2026-09-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0GzwuYGvKA4
speaker: The Pragmatic Engineer
tags:
  - code-generation
  - storage-architecture
  - vertical-scaling
  - ai-tooling
  - system-design
title: 从手动编码到AI辅助的软件开发历程与架构演进
summary: 文章回顾了从早期手动编写代码到利用AI辅助生成高质量代码的转变，重点探讨了软件开发中的技术里程碑（如纠删码），以及在数据存储架构重构、垂直扩展测试和利用AI作为新型建筑材料进行系统构建方面的思考与实践。
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
<!-- chunk 1/8 -->

### 序言与精彩回顾

**Host**: 在本期节目的精彩片段中，我们将聊到一些令人惊叹的经历。比如谷歌创始人拉里·佩奇（Larry Page）和谢尔盖·布林（Sergey Brin），当时他们其中一人联系并面试了彼得。那是在谷歌刚成立三年的时候，而彼得当时拒绝了谷歌的录用邀约。

<details>
<summary>Original English</summary>

**Host**: In today's preview: Larry and Sergey from Google. Somehow one of them reached out for an interview at Google. Google was three years old. Three years in, and I rejected them. You'd agree that's quite something.

</details>

**Peter Mattis**: 我一直以来都是一个极高产的程序员。翻看我在 GitHub 上的公开记录，在巅峰期的一年里，我大概手写了十万行代码。

<details>
<summary>Original English</summary>

**Peter Mattis**: I have always been a very prolific programmer. Looking at what was published on my GitHub, in my peak year, I probably wrote something like 100,000 lines of code a year.

</details>

**Host**: 那可是在 AI 出现之前，对吧？这完全是你一行一行纯手动写出来的代码。看着这些，我只能由衷地赞叹并感到不可思议。我们后面还会聊到他们完成纠删码（erasure coding）的历程，那是一个相当巨大的技术里程碑。比如将数据切分成 9 个分片，只需要任意 5 个分片就能重建完整数据；这意味着你即使丢失了 4 个副本，依然能够完整恢复数据。在你看来，回顾四年前 AI 崭露头角之前的软件开发状态，与今天的软件开发相比，有什么不同？我们的雄心壮志是否应该进一步提升？

<details>
<summary>Original English</summary>

**Host**: And that's before AI came along, right? This is you doing it manually by hand. Looking at this, I can only shake my head in awe. We also talk about the course on erasure coding they completed. That was a pretty big milestone: having nine shards of data where any five shards can be used to reconstruct them, meaning you could lose four copies and still recover their data. In your opinion, looking at software development four years ago before AI compared to software development today, should ambition grow?

</details>

**Host**: 今天的嘉宾在大学期间就创建了著名的图像编辑软件 GIMP，后来为主导 Gmail 底层的基础架构开发了开创性的数据存储系统，并在其职业生涯中构建了众多庞大、复杂且被广泛应用的系统。他就是 Cockroach Labs 的联合创始人兼首席技术官（CTO）彼得·马蒂斯（Peter Mattis）。彼得告诉我：“在过去的 30 年里我写了无数代码，但最近发生的事情简直不可思议。不仅写出了各种风格的代码，而且在强大编码模型的辅助下，竟然能产出适用于高性能数据库的高质量代码。”今天，就让我们一同走进他多次在职业生涯中从 B- 跃升至顶尖水平的历程，探寻他是如何持续写出卓越系统的。如果你对如何利用人工智能打造极其强大的软件感兴趣，那么这一期播客绝对不容错过。

<details>
<summary>Original English</summary>

**Host**: He created the GIMP image editor while studying in college, developed the original storage system that Gmail was based on, and has built many other large-scale, complex, and widely used systems. This is Peter Mattis, co-founder and CTO of Cockroach Labs. As Peter told me: "Over the past 30 years... but my current results are a little crazy. From writing throwaway vibes to high-quality, high-performance database-ready code with powerful coding models." Today, let's explore how he repeatedly leveled up throughout his career and how he built diverse systems. If you're interested in successfully using artificial intelligence to build production-ready systems, this episode is for you.

</details>

### 赞助商 Turbobuffer 介绍

**Host**: 在深入对话之前，先向大家介绍本期的赞助商 Turbobuffer。我和他们团队的技术人员聊过，他们正在做的事情非常酷。他们从第一性原理出发，彻底重构了存储架构，使得搜索在大规模场景下变得更快、更具成本效益且更可靠。如果你一直在关注 Turbobuffer，就会知道其底层的存储架构是他们早期成功的关键基石。

重新设计核心架构绝非易事：一方面要求业务层请求通过完备的单元测试，另一方面必须证明新架构与旧系统完全平齐，甚至在吞吐量、延迟和可靠性上全面超越生产标准。最令人兴奋的是，Turbobuffer 正将这一过程完全公开。对于他们称之为 T-Puff V3 的全新存储架构，他们不仅应对了复杂系统的各项演进挑战，还将设计决策与测试结果毫无保留地分享出来。他们正在撰写公开工程日志，第一篇博文刚刚发布。欢迎访问 turbobuffer.com/v3 关注最新动态。

<details>
<summary>Original English</summary>

**Host**: In this episode—I really enjoyed spending time with them—the engineering team at Turbobuffer is doing something genuinely cool. They completely redesigned their storage architecture from first principles to make search faster, cheaper, and more reliable at massive scale. If you follow Turbo Buffer, their storage architecture was critical to their early success. Redesigning a winning architecture is no small feat: one business requirement is passing all unit tests, and the other is proving parity or superior performance and production reliability. But here is the most interesting part: Turbo Buffer is documenting all of this. Their new storage architecture, which they call T-Puff V3, tackles complex systemic challenges, and they are publicly sharing design decisions and benchmark results as they release them. They are keeping a development log, and the first post was published today. To follow the updates, visit turbobuffer.com/v3.

</details>

### 编程启蒙与转向计算机科学

**Host**: 彼得，欢迎来到播客！

<details>
<summary>Original English</summary>

**Host**: Peter, welcome to the podcast.

</details>

**Peter Mattis**: 谢谢，非常高兴来到这里！

<details>
<summary>Original English</summary>

**Peter Mattis**: Oh, I'm glad to be here.

</details>

**Host**: 很高兴你能来。我们先从头聊起吧，你是如何进入科技领域的？最初是什么时候意识到计算机如此吸引人的？

<details>
<summary>Original English</summary>

**Host**: It's perfect. I'd love to dive in. How did you get started in technology? When did you realize computers were interesting?

</details>

**Peter Mattis**: 我其实在小学和高中时代就感受到了这种吸引力。对我和许多其他软件工程师来说，游戏往往是最初的引路人，就像一种独特的“成瘾剂”。另外，在我成长的早期阶段，我母亲曾在 IBM 担任程序员。虽然我当时并不完全清楚她具体从事什么工作，但家里一直都有电脑，比如 Apple II Plus 和 Apple II GS。

不过，后来当我进入大学时，我的最初想法是：“我不能靠电脑来谋生，我想成为一名机械工程师”，想要继承我父亲的事业。

<details>
<summary>Original English</summary>

**Peter Mattis**: I realized this back in elementary school and high school. Gaming was, for me as well as for many other software engineers, the gateway drug. Well, in my early years, my mother programmed at IBM. I didn't entirely understand what she was involved in, but we always had computers at home, like the Apple II Plus and Apple II GS. But then, when I entered college, I thought, "I'm not doing computers to make money. I'm going to be a mechanic," following my father.

</details>

**Host**: 专攻机械工程？

<details>
<summary>Original English</summary>

**Host**: Majoring in mechanical engineering?

</details>

**Peter Mattis**: 是的，那是我的专业。虽然我之前就有计算机背景，但我当时心想这太傻了，直到我选修了一门计算机科学课程。那门课对我来说简直太轻松惬意了，而其他所有工科课程却让我备受折磨、不堪重负。我当时意识到：“这不对劲，我不适合那个行业，我得转专业。”

<details>
<summary>Original English</summary>

**Peter Mattis**: That specialty, yes. I had done computer stuff before. It felt really silly until I took a computer science course, and it was so easy. Meanwhile, everything else was completely overwhelming. I felt like: "I am not myself here. I don't belong in that industry. Please let me switch."

</details>

**Host**: 于是你就转到了计算机科学专业。

<details>
<summary>Original English</summary>

**Host**: And so you switched.

</details>

**Peter Mattis**: 是的，转系了。

<details>
<summary>Original English</summary>

**Peter Mattis**: Then I switched, yeah.

</details>

### 大学时光与 GIMP 的诞生

**Host**: 你在大学时期打造的第一个真正意义上的软件是什么？是在哪个阶段你意识到：“这才是一个真正拿得出手的、令我自豪的完整软件项目”？

<details>
<summary>Original English</summary>

**Host**: What was the first software you built in college where you thought, "Okay, this is real software that I'm proud of, a serious software project"? Must have been during your college days.

</details>

**Peter Mattis**: 那肯定是大学时代。当时我和大学室友选修了一门课，好像是编译原理之类的课程吧，时间过去整整 30 年了，记太不真切了。当时我们觉得那门课程有点枯燥。由于我在高中的最后一年曾做过校刊出版方面的工作，懂得一些电脑图形学排版知识，很想做一个类似于 Adobe Photoshop 那样的软件。

于是我们便开始动手实验，最终做出了一个大家都耳熟能详的项目——那就是 GIMP。在开发 GIMP 的过程中，我完成了大量的图形界面工作，并构建了 GTK 图形库，后来它演变成了一个极其庞大的生态系统。

非常有趣的是，大学毕业后我就彻底放手了这个项目，大学第一年后我就基本没有再深入参与过它的维护。但直到今天，人们依然因为 GIMP 而认识我，这成了我职业生涯中一段极为奇妙的印记。

<details>
<summary>Original English</summary>

**Peter Mattis**: Well, it had to be college. I had this course with my roommate in college. What was it—a compiler course? I don't quite remember, it was 30 years ago. We were a bit bored with it. I had worked on high school journalism in my senior year and knew about computer graphics, and I wanted to make something like Adobe Photoshop. So we simply started experimenting, and we built what many people know today: it was called GIMP. With GIMP, I did a ton of work on the GTK graphics library. From there, it evolved dramatically. What's very interesting is that after college, I walked away from it. I was not very actively involved after that first year out of college, yet people still know me for it, which has been an interesting recurring theme throughout my career.

</details>

**Host**: 当你着手开发 GIMP 时，你心里想的是：“好吧，我要做一个类似 Photoshop 的工具”，你当时是否抱着一种初生牛犊不怕虎的执拗？那时你并没有在大学系统学过图形学，对吧？完全是凭自己的摸索：如何构建渲染引擎、绘图系统、数据结构等等，全靠你自己搞清楚？

<details>
<summary>Original English</summary>

**Host**: When you started GIMP, thinking "I'm going to make something like Photoshop," were you being as stubborn as possible? That wasn't what you were learning in college classes, right? It was just you figuring out how to build a graphics rendering engine, drawings, data structures, and all that kind of stuff, right? You had to figure it all out.

</details>

**Peter Mattis**: 是的，全靠自己摸索。我记得当时尝试翻阅了各种能找到的技术文档，我和室友一起通读论文和参考书，努力把所有机制都搞明白。这正是那种“如果你预先知道有多难、要付出多少代价，你根本就不会开始”的事情。

要达到那种工程复杂度，如果你一开始就清楚知道需要跨越多少难关，你可能早就被吓退了。但一旦你启动了它，它就会像滚雪球一样不断壮大，越做越多。有时回头看，会感叹“这真的太酷了”。

不过这里还有一个鲜为人知的有趣小插曲。我以前可能提到过，当时我们开发到了一个阶段，决定正式对外发布代码。在那个年代，大家都在 Usenet 新闻组里交流发帖，讨论各种图形学和开源项目。我记得就在我们计划发布 GIMP 第一个版本的前几周，突然有人在新闻组里发帖说：“我正在开发一个全新的图形处理软件”，并且列出了功能清单，其能力几乎与 GIMP 不相上下，甚至列出了更多高级功能。

我们当时看到那个帖子，心都凉了半截，心想：“糟糕，被抢先了，太让人沮丧了。”但转念一想，我们已经倾注了这么多心血，而且过程非常享受，那就还是坚持把我们的版本发布出去吧！

于是我们正式发布了 GIMP。而出人意料的是，从那之后，新闻组里的那个竞争者就彻底销声匿迹、音信全无了。

<details>
<summary>Original English</summary>

**Peter Mattis**: Exactly. I remember trying to read whatever documents we could find back then. My roommate and I reviewed docs, and we were just trying to figure it all out. It's one of those things where, if you knew beforehand how much effort it would take, you never would have started. To take on that level of work, if you truly understood what it entailed, you wouldn't touch it. But once you start, it grows like a snowball, getting bigger and bigger, and at times you think, "This is truly amazing." But there's an amusing, little-known story. I might have mentioned it before, but it's simple: we reached a point where we decided we should release it publicly. Back then, there were newsgroups where people posted about various topics, including graphics. A couple of weeks before we planned to release the first version of GIMP, someone else showed up and said, "I'm working on this graphics program," and described what it could do—matching GIMP and claiming even more. We were just like, "Oh, this is terrible." But we decided to keep going and finish our work because it was fun. Then we released GIMP, and after that, complete radio silence from that other guy.

</details>

### 创业者的心智模型：直面竞争与执行力

**Peter Mattis**: 我从这件事中汲取到了一个极其重要的教训：在任何时候，世界上总会有其他人在做着和你相同的构想。你绝不能因为别人抢先发表了声明或概念，就放弃自己的项目。仅仅口头宣传是产生不了任何实际成果的。

在商业和市场营销中，我们经常听到类似的焦虑：“要是别人抢先一步夺走了所有的荣光怎么办？”我其实至今都不知道那个发帖者身上到底发生了什么，但这个教训深深烙印在我的脑海中。

哪怕你未来看到各种宣传通告，看到有人高喊“我正在做这个全套系统”，如果你心里犯嘀咕：“有人已经在做了，那我还是回去做点别的吧”，那么 GIMP 就永远不会诞生了。

<details>
<summary>Original English</summary>

**Peter Mattis**: I took away a valuable lesson from that: someone else is always working on your idea. You shouldn't be discouraged or back off just because they announce it ahead of time. Nothing came of his announcement. In marketing, you often hear worries like: "What if they steal our thunder?" I never found out what actually happened to him, but the lesson stuck with me. If you read an announcement where someone claims, "I'm doing all of this," and you think, "Someone's already done it, I'll go do something else," then GIMP never happens.

</details>

**Host**: 说的太对了。尤其在审视当今的初创生态时，这种现象随处可见。无论你的点子听起来多么新颖，你总会遇到竞争。

<details>
<summary>Original English</summary>

**Host**: That's right. Especially looking at startups today, that's exactly how it feels. Whatever you want to do, explain it, right?

</details>

**Peter Mattis**: 我给很多创业者的建议也是如此：在这个世界上，任何看似独一无二的想法，几乎在同一时刻都有十来个人也想到了；甚至可能已经有几个人开始着手推进了。但绝大多数人仅仅停留在想法阶段，根本无法跨越执行的鸿沟。

所以，当你听说别人正在做着和你一模一样的事情时，很可能确实如此。我们现在公司做的一些非常酷的技术方向，我敢肯定市场上绝对有竞争对手也在暗中探索。关键在于坦然理解并接受竞争，享受竞争带来的推动力，而不是陷入恐惧。

<details>
<summary>Original English</summary>

**Peter Mattis**: The advice I give people is: as unique as you think you are, in this world there are roughly a dozen people thinking the exact same thing. And probably a few of them are actively working on it. But most people never execute beyond the idea phase; they just can't bring it to life. So when you hear that someone else is working on your exact idea, they probably are. We're working on some very cool things at my current company, and I can guarantee competitors are working on them too. You just have to know what competition feels like, embrace that aspect, and enjoy it rather than fear it.

</details>

### 初遇谷歌与拒绝早期录用

**Peter Mattis**: 大学毕业后不久，我加入了另一家初创公司。当时谷歌的拉里·佩奇或者谢尔盖·布林——我记得大概率是谢尔盖——甚至早期版本的 Google 徽标都是用 GIMP 制作的。所以他们很早就知道我们的存在。

不知通过什么渠道，他们找到了我的联系方式，并邀请我到谷歌面试。那是在 2001 年，当时谷歌才刚刚创立三年。然而，在拿到录用机会后，我却说了“不”。

<details>
<summary>Original English</summary>

**Peter Mattis**: So, a bit after college, I was at another startup. Larry and Sergey from Google—I'm pretty sure it was Sergey—in fact, early versions of the Google logo were made using GIMP. So they knew of us. Somehow, one of them tracked me down and invited me for an interview at Google. This was back in 2001, when Google was about three years old. And I said no.

</details>

**Host**: 你竟然拒绝了？你当时完全可以顺理成章地加入啊。

<details>
<summary>Original English</summary>

**Host**: You didn't have to say no! You said no?

</details>

**Peter Mattis**: 是的，我拒绝了。当时我脑子里的盘算是这样的：谷歌的办公室在山景城（Mountain View），而我住在旧金山市区，我实在不想每天长途通勤去那里上班。于是我选择留在了旧金山的一家初创公司工作了一年。

后来那家初创公司发展陷入停滞，根本走不通。就在那时，谷歌再次给我打来了电话，问我：“嘿，你愿意重新回来面试聊聊吗？”我回答说：“当然可以。”

但他们当时告诉我：“我们无法再为你提供像三年前那样丰厚的原始股票期权待遇了。”我说：“没问题，我明白。”

虽然我已经记不清具体差了多少倍，但我至今依然清晰地记得第一次面试时他们开出的期权数字。如果我一开始就接受了，那笔财富无疑会极其惊人。

不过话说回来，我后来的回报也已经相当不错了。我不是那种怨天尤人的人，但这段往事每每回想起来，都会感叹人生选择的奇妙。

在更早的时候，红帽（Red Hat）上市时，由于 GIMP 的开源贡献，他们实际上给许多开源社区贡献者提供了定向配售股票（Friends and Family IPO allocation）。这让我赚到了人生的第一桶金。虽然数额绝对值不算天文数字，但对于刚走出大学校门的我来说，那是一笔极其关键的资金支持。因此，我在大学刚毕业那段日子过得非常体面。我也正是借着开发 GIMP 赚到的这点底气，买下了自己想要的东西，开启了后续的工程师生涯。

<details>
<summary>Original English</summary>

**Peter Mattis**: Yes, I said no. Here was my calculus at the time: Google was down in Mountain View. I lived in San Francisco and didn't want the commute to work. So I went and worked at another startup for its first year. As it turned out, that company went nowhere. Then Google called me back and asked, "Hey, would you like to re-interview?" I replied, "Of course." They warned me: "We can't offer you the same stock options we offered before." I said, "Understood." I don't recall the exact math now, but I still remember the numbers from the initial offer. Obviously, it would have amounted to significantly more money if I had joined at the start. But I still did very well. I'm not one to complain, but whenever I recall this, I think, "Yeah, that turned out to be quite a story." Similarly, when Red Hat went public, they offered a Friends and Family IPO share allocation to many open source contributors. We were offered shares, and I made some money. While it wasn't a massive fortune, right after graduating college, it was a meaningful cushion. So I came out quite well, and working on GIMP made me realize: "Oh, I can actually afford things."

</details>

<!-- chunk 2/8 -->

### 加入 Google 与 Caribou 项目：Gmail 的秘密诞生

**主持人**: 像 Photoshop 和 GIMP 这样的工具，能为人们带来积极正面的影响，能够使用它们是一件非常棒的事。这就是它的本质——面向所有人的免费软件。回想那个时候，我是谁？当时的软件生态和今天完全不同，如今免费和开源软件已经非常普及了。

<details>
<summary>Original English</summary>

**Interviewer**: Tools like Photoshop and GIMP, and things like that—I was really into using this opportunity to make a positive impact. That was the essence of it: free software for everyone. You know, back then, who was I? Software at that time versus today was so different; free and open source is common today.

</details>

**Guest**: 是的，没错。而且更重要的是，我学会了编程，如今成为了一名优秀的软件工程师与程序员。之后，我第二次加入了 Google。

<details>
<summary>Original English</summary>

**Guest**: Yes, yes. And furthermore, that was where I learned how to program, becoming a good engineer and programmer now. And then I joined Google for the second time.

</details>

**主持人**: 当时他们对你说：“好，那你具体负责做什么呢？已经开始着手工作了吗？”

<details>
<summary>Original English</summary>

**Interviewer**: And they said, "Okay, what are you doing? Have you started working?"

</details>

**Guest**: 是的，当我到了那里之后，他们对我说：“嘿，你知道的……”那是在 2002 年初。具体来说是 2002 年 4 月 1 日，那可真是一个吉利的日子——愚人节。

<details>
<summary>Original English</summary>

**Guest**: Yes, yes. When I arrived there, they said something like, "Hey, you know..." It was in early 2002. It was April 1st, an auspicious day.

</details>

**主持人**: 哈哈，你是在愚人节那天入职开始工作的。

<details>
<summary>Original English</summary>

**Interviewer**: Well, you started on April 1st, 2002.

</details>

**Guest**: 没错，2002 年 4 月 1 日。我到了之后，他们对我说：“好，我们要开发一款电子邮件服务，叫‘Google Mail’。”不过那时候它还不叫 Gmail，内部代号叫做“Caribou”（北美驯鹿）。

<details>
<summary>Original English</summary>

**Guest**: Yes, April 1st, 2002. And I arrived there, and they were like, "Yeah, well, you know, we're going to build an email service, 'Google Mail'." At that time, it wasn't called Gmail yet; internally, the codename was Caribou. Caribou.

</details>

---

### 构建海量邮件存储流与 B-Tree 索引架构

**Guest**: 是的，我接下了这个任务，开始投入工作。我被分配负责消息流处理系统、底层存储以及索引构建。在最初的一年半时间里，我全力以赴攻关，那是一段相当艰苦的高强度开发期。实际上，在这个项目正式发布之前，我前后大约投入了三年时间。最终，它在 2004 年 4 月 1 日正式发布。你还记得那次发布吗？因为选在 4 月 1 日，很多人甚至以为这只是一个愚人节玩笑。

<details>
<summary>Original English</summary>

**Guest**: Yes, so I started this work, and I was tasked with working on the message flow processing, storage, and indexing system. And I ended up working on this intensely during the first year and a half. In fact, I worked on it for maybe three years up until launch, which actually dropped on April 1st, 2004. Do you remember this? People thought it was an April Fools' joke.

</details>

**主持人**: 是的，我印象非常深刻！如果我记错了请纠正我：当时 Gmail 发布时直接承诺提供 1GB 的海量存储空间，或者几乎说是无限存储，打出的标号就是 1GB。要知道在那个年代，绝大多数免费网络邮箱服务商（比如 Hotmail 或 Yahoo Mail）只给用户提供 2MB 到 4MB、至多 10MB 的存储空间；如果付费，或许能升级到 50MB 或 100MB，但费用极其昂贵。结果 Google 突然宣布推出免费邮箱，而且容量直接翻了 20 倍、50 倍甚至 100 倍！我们在业内激烈讨论，这在当时的整个行业引发了巨大的震动。

<details>
<summary>Original English</summary>

**Interviewer**: Yes, I remember. Correct me if I'm wrong, but at launch time, Gmail came out offering 1GB of storage capacity—or something like virtually unlimited storage, starring 1GB. Back then, most webmail suppliers offered you only 10MB or even 4MB of free storage, like Hotmail or Yahoo Mail. And to pay for maybe 50MB or 100MB was super expensive. This launch showed someone could provide a free email service offering 20 to 50 or 100 times larger storage. We discussed this internally; it was a shocking and reverent campaign for the industry.

</details>

**Guest**: 没错，Hotmail 和 Yahoo Mail 当时普遍只有 4MB 左右。而且我们的优势不仅是容量大，更关键在于所有邮件都能被极其迅速地建立索引。所以你在里面执行全文搜索时，搜索结果几乎是瞬间返回。

<details>
<summary>Original English</summary>

**Guest**: I think so. It was actually 4MB in the case of Hotmail or Yahoo Mail, and then you had this. And not only was there much more storage, but it was indexed very fast, so running a search returned results almost instantaneously.

</details>

**主持人**: 能跟我们讲讲内部的技术细节吗？当团队启动这个项目、决定做一款 Google 邮箱时，你们是如何看待存储和检索速度的？毕竟在那个时代，磁盘还是相当昂贵的，而且当时用的完全是机械硬盘（HDD），甚至还根本没有现代意义上的固态硬盘（SSD）。如果把你带回那个时刻，当时的硬件限制到底有多严苛？你们究竟是如何实现这种前所未有、从未有人做过的技术创新的？

<details>
<summary>Original English</summary>

**Interviewer**: But tell us internally: when the project started for Google Mail, how did the team address storage and speed? Because disk storage was still expensive back then, and we are talking about HDDs, definitely not SSDs if my memory serves me right. If you can take us back, what were the constraints, and how did you implement an innovation that had literally never been done before?

</details>

**Guest**: 是的。关于这一点，当时 Google 内部已经有了大规模分布式文件系统，也就是大家熟知的 Google 文件系统——GFS（Google File System）。我们在估算数字后认为：“是的，我们完全有能力开发出这样的系统。”团队在如何利用已有搜索系统进行检索和数据抓取方面积累了极其深厚的知识。早期有人做过一个原型，但后来被彻底重写了——实际上，正是我完成了彻底的重写工作。当我接手时，现有的原型已经在那儿了，但我把它推倒重来，全面重写了数据流系统。

我们从一开始就确立了“消息流”（Message Streams）架构，这在当时是一项极具颠覆性的创新，而如今已成为各大邮件系统中的通用范式。在消息流架构下，底层数据端需要专门的数据结构来承载存储空间，并且要能应对高并发的读取吞吐。这正是 B-Tree（B 树）发挥核心作用的地方。在我的职业生涯里，这已经不是我第一次实现 B 树了，我之前大概已经亲手写过十几次 B-Tree。

<details>
<summary>Original English</summary>

**Guest**: Yes. At that time at Google, there was the large-scale distributed file system named GFS, the Google File System. We looked at the numbers and thought, "Yes, we can develop it." They had a wealth of knowledge on how to execute search and retrieval from existing search systems. They had started creating a prototype, and then it was completely rewritten. That was actually exactly what I did: when I started, a prototype already existed, but then I completely rewrote it from the stream side. We decided from the beginning to implement message streams, which was quite innovative. This is a common phenomenon in mail systems today. And in the stream, the message flow required specific underlying data structures for storage, and you needed high read throughput. This is where B-trees were involved. I had already implemented B-trees about a dozen times before.

</details>

**主持人**: B 树在 Gmail 的邮件流处理中具体扮演了怎样的角色？它是如何与邮件流对接的？

<details>
<summary>Original English</summary>

**Interviewer**: How were B-trees connected with the stream in email?

</details>

**Guest**: 具体来说，每当一封新邮件到达时，它都带有特定的会话线程 ID（Thread ID），系统必须在存储中快速定位。它利用搜索索引匹配对应的主题，并将邮件唯一标识符归入讨论线程中。此外底层还有很多并发处理逻辑，因为我们必须实时追踪每个会话分支中的未读邮件数量等等。

如今回想起来，这些细节恍若古代史一般遥远。那可是 2004 年的事，距离今天（2026 年）已经过去 22 年了！所以凭借我的记忆，当时在底层不仅实现了 B 树，还构建了倒排索引（Inverted Index），所有这些底层代码当时都是从零重新编写的。

<details>
<summary>Original English</summary>

**Guest**: Well, for specific storage with thread IDs of incoming messages, you have to look them up. It used search indexing to match topics and associate the message identifier with the discussion thread. A lot of other things were happening under the hood because we were tracking the number of unread messages across discussion branches, and so on. Looking back, I can recall all these details now—it feels like ancient history. This was 2004. Here we are 22 years later. So from my memory, B-trees and inverted indexes were used there, and all this code was completely rewritten from scratch.

</details>

---

### 商业模式博弈、Paul Buchheit 与邀请制策略

**主持人**: 提供如此庞大的免费容量，你们内部肯定做过精密计算吧？难道当时不担心这会带来难以承受的巨额亏损吗？

<details>
<summary>Original English</summary>

**Interviewer**: Offering this for free—surely you calculated the economics. Wasn't there a risk of terrible, massive losses?

</details>

**Guest**: 是的，绝对有过这方面的担忧。但在某个阶段，团队里诞生了一个构想：“嘿，也许我们可以在界面中展示相关的文本广告。”在当时，这被很多人视作一个天马行空的离奇想法。

其实我个人并没有直接参与广告商业化这部分。主导这项创新的是保罗·布赫海特（Paul Buchheit）——他后来创办了 FriendFeed，并在加入 Facebook 后大放异彩，最终成为了 Y Combinator 的合伙人。当时某天晚上，保罗说：“不，我可以在现有的广告功能基础上搞点突破，把它直接集成进邮箱界面里。”结果很快就做出来了，并最终演化成一门难以置信的庞大商业帝国。

所以回顾起来，必须先从经济可行性上算清账。例如，“我们算过，每位用户每年会消耗我们几美元的成本。我们究竟该如何实现商业变现？”我们打定主意不想向普通用户收费。虽然后来在企业级 Google Workspace 中有付费版本，但在当时，大家的核心焦点是：“我们真的能做到完全免费开放吗？从经济模型上算得过来吗？”这确实需要冒巨大的商业与工程风险。

<details>
<summary>Original English</summary>

**Guest**: Yes, yes, absolutely. At one point, the idea emerged: "Hey, maybe we can serve ads here." And this was considered one of those wild, crazy ideas. I wasn't personally involved in that part; that was Paul Buchheit, who later went on to build FriendFeed, do great things at Facebook, and eventually become a partner at Y Combinator. But one evening, he said, "No, I can take some of our existing advertising capabilities and integrate them right into the interface." It happened very quickly, and this grew into an unbelievable, massive business. So it comes down to understanding what is economically possible: "We know this costs a few dollars per user per year. How do we monetize it?" We didn't want to charge users for it. Eventually, there was pricing for Google Workspace, but at that time the question was: "Can we do this for free? Is it economically viable?" Taking that risk took real courage.

</details>

**主持人**: 你还记得当时的上线过程吗？之所以问这个，是因为我记得 Gmail 最初采用了非常严格的“邀请制”（Invite System）。并不是任何人想注册就能直接注册的。这么做是为了控制激增的访问需求吗？毕竟你们把原本市场上极其昂贵的存储直接免费提供，显然会引发井喷式的巨大需求。你们当时是如何监测服务器负载并决定放量的？

<details>
<summary>Original English</summary>

**Interviewer**: Do you remember the launch? The reason I ask is because I remember it was based on an invitation system. Not just anyone could get in. Was that done to control the anticipated demand? Again, offering something for free that was previously paid was obviously going to create huge demand. How did you think about monitoring demand and making decisions?

</details>

**Guest**: 说实话，这是一个跨团队紧密协作的成果，我没有直接主导邀请制的运营，因为我主要负责底层的负载与性能支撑。当时提出“基于邀请注册”的机制承担了双重使命：一方面，它在工程上起到了一定程度的流量控制与削峰限流作用，防止服务器瞬间被挤爆；另一方面，它在市场上引发了极其强烈的病毒式渴望与话题发酵。哈哈，你应该能理解当时大家对拿到一枚 Gmail 邀请码有多么痴迷吧？大家都在到处求邀请码。

<details>
<summary>Original English</summary>

**Guest**: Honestly, this was teamwork. I didn't directly run that; I was primarily focused on handling the system load. The idea of "invite-only" served a dual role: to some extent, it throttled hyper-growth to manage capacity and prevent overload, but at the same time, it generated immense buzz and social heat. You know what it felt like when people were desperate for Gmail invites back then, right? People wanted them so badly.

</details>

---

### 从单体 Makefile 到 Google3 与分布式构建系统 Blaze

**主持人**: 在 Gmail 之后，你的工作重心转移到了哪里？当时的工程代码库与构建环境是怎样的？

<details>
<summary>Original English</summary>

**Interviewer**: And after dealing with Gmail, where did you move on to? What was the codebase and build collection like?

</details>

**Guest**: 当我刚加入 Google 时，公司内部的代码库刚从早期的历史版本迁移到了所谓的“Google2”。但在运行了一段时间后，Google2 暴露出了严重的问题——整个工程竟然是由一个巨大的、单体的 Makefile 来组织的。虽然其中包含了一些分散的子 Makefile，但整体上就是一个结构极其庞杂臃肿的单体构建脚本。

当时有人找到我对我说：“我觉得在构建工程这一块，我们大有可为。”而我本身对构建与编译系统（Build Systems）一直抱有浓厚兴趣。于是，我作为核心主力之一，为后来的“Google3”构建架构打下了基石。当然，许多优秀的工程师都参与其中，而我负责前期的架构探索与初始设计。

在 Google3 的早期工作中，核心痛点是：“大家写这些复杂的 Makefile 体验实在太糟糕、太痛苦了。”因此，我提出了一套全新的描述方案：通过在各目录下定义专门的构建文件（BUILD 文件），用声明式的方式列出文件依赖。我决定采用一种高度精简的 Python 方言来定义规则，因为 Python 语法非常清晰易读。这一演进在经历了一系列迭代后，演变成了后来的 Gconfig 与 Blaze——在工程层面，开发者再也不需要手写痛苦复杂的 Makefile 命令，构建逻辑与源码解耦并标准化。

随着时间推移，这套内部被称为 Blaze 的构建系统在工业界催生了深远的影响。开源社区的 Bazel 就是它的外部开源实现，Facebook 也根据相同理念开发了 Buck 构建工具。

<details>
<summary>Original English</summary>

**Guest**: When I arrived at Google, it was prior to my arrival that they moved forward to Google2. At a certain point, we saw the consequences of Google2: Google2 was essentially driven by a single, monolithic Makefile. I think there were actually a few sub-makefiles, but it was really this huge, heavyweight Makefile. Someone approached me and said, "I think there's something we can do here." I was interested in assembly and build systems, so I laid the foundation for Google3. Many people were involved, but I was doing the initial design work on Google3. The initial insight for Google3 was: "Look, writing these makefiles is somehow terrible." I presented this concept based on declaring file collections. I decided to make it a simplified Python language, keeping the syntax clean. Subsequently, instead of a monolithic build file, you didn't have to write low-level build scripts like that anymore. Over time, this evolved internally into Blaze. Externally, Bazel was open-sourced from it, and Buck at Facebook came from people who worked on this.

</details>

**主持人**: 这对工程维护和开发体验来说真是一次巨大跃升。当时手写依赖关系到底有多痛苦？它给开发生产力带来了怎样的改变？

<details>
<summary>Original English</summary>

**Interviewer**: Did it significantly improve convenience and maintenance? Was defining dependencies before like writing assembly language?

</details>

**Guest**: 是的，以前管理依赖关系就如同手写汇编语言一样晦涩且极易出错。谁也不希望在刀耕火种的原始配置中手动声明复杂的构建依赖。一旦遗漏或写错某条依赖链，整个编译就会崩溃。而通过引入声明式的抽象规则，开发人员只需要声明“我的组件依赖什么”，底层系统便会自动解析整个依赖图并执行增量编译。

这为工程生产力带来了质的飞跃。在 Google 庞大的单一代码库（Monorepo）环境中，清晰规范的依赖结构让数万名工程师能够高效协同，构建流程变得极其干净、模块化且高可靠。大家自发地迅速拥抱了这套新体系。

<details>
<summary>Original English</summary>

**Guest**: Yes, exactly. It was like dealing with dependencies in assembly language. Nobody wanted to write their dependencies in assembly language where a single mistake meant missing something. Instead, you express dependencies declaratively, and from this, the build system handles the direct compilation and dependency tree. This brought massive productivity improvements. In Google's massive repository, a clean codebase structure helps improve productivity, making builds demonstrably simpler, cleaner, and faster. So we experimented, created these build files, and people enthusiastically adopted them.

</details>

---

### 下一代分布式存储：从 GFS 到 Colossus 的架构演进

**主持人**: 在做完构建系统之后，你又将精力聚焦到了什么方向？

<details>
<summary>Original English</summary>

**Interviewer**: What did you focus on next?

</details>

**Guest**: 我之前提到了 Google 早期的分布式文件系统 GFS。随着公司业务规模呈指数级膨胀，在某个时间节点，我们清醒地意识到 GFS 遇到了严重的物理瓶颈和单 Master 节点的可扩展性瓶颈。

因为我之前长期负责 Gmail 的端到端海量存储架构，在此期间我也自主实验探索过多种新型存储引擎，这些预研探索为下一代架构积累了关键的经验。因此，当 Google 决定启动 GFS 的下一代继任者项目时，我受邀成为了创设团队的核心成员——这个下一代分布式存储系统就是后来广为人知的“Colossus”。

据我所知，Colossus 至今仍然作为 Google 云端最核心的基础设施在运转。多年来它经历了多次重构与迭代，作为 Google 的第二代分布式文件系统，它彻底解决了元数据瓶颈并支持了前所未有的集群规模。

<details>
<summary>Original English</summary>

**Guest**: Well, I mentioned GFS earlier. At a certain point, we realized GFS had severe limitations and bottlenecks in scalability. Because I had worked across the entire storage layer for Gmail, I had actually experimented with alternative storage systems—research that laid the groundwork. So we worked on this, and I was invited to join the founding team for Colossus, the successor to GFS. Colossus is still running today, having gone through multiple iterations at Google. It is the second-generation distributed file system.

</details>

**主持人**: 那么，对于外部的工程师和架构师来说，Colossus 究竟是一个怎样的系统？从系统架构的外部视角来看，它该如何理解？

<details>
<summary>Original English</summary>

**Interviewer**: So what exactly is Colossus? When you describe the system from an external architectural perspective, how should we think about it?

</details>

**Guest**: 是的。当我们在宏观上审视这套系统时，从外部抽象视角来看……

<details>
<summary>Original English</summary>

**Guest**: Yes. When talking about the system and thinking from the outside...

</details>

<!-- chunk 3/8 -->

### 对象存储演进与纠删码引入

**Colossus 工程师**：你看类似 S3 这样的系统，它属于一种对象存储（Blob Storage）。当时拥有的是一个扁平命名空间（flat namespace），就像 S3 那样，每个对象都有名字，但它的能力其实非常受限。它并不是一个 POSIX 文件系统。因此在目录层面，甚至都没有一套完善的权限体系，其中很多功能都是后来才补充添加进去的。然而文件实际上是存放在离你很近的物理机器上。整个系统就是一个庞大的服务器集群（机房车队），承载着此类服务，里面存放着所有文件。客户端在访问时，系统会把数据写入磁盘，如今则更多采用 SSD。所有这些数据都需要进行副本复制，以防故障发生。

<details>
<summary>Original English</summary>

**Colossus Engineer**: みてください S3 のようなもの。BLOB ストレージの一種彼が持っていた物フラットネームスペース、S3 のようなもので、名前があり、しかし彼女はとても限定。えっと、でもこれはファイルシステムではない POSIX。だから、カタログには、完成すらしていなかった許可制度。その多くは後から追加されました。しかしファイルは保存先お近くの車。全体がある公園だよ、君のねそういう種類のサービスすべてのファイルが含まれています。彼らはそれを書き留めるか、今は SSD に搭載されています。クライアントはアクセス。そしてこれらすべてが複製するためもしそれらが起こるなら。

</details>

**Colossus 工程师**：虽然我不确定具体是什么确切时间，但后来 S3 逐步引入了纠删码（Erasure Coding）。而在 Google 内部，我们也在 Colossus 中实现了纠删码。这在当时算得上是一项重大的技术突破。

<details>
<summary>Original English</summary>

**Colossus Engineer**: いつなのかはわかりませんが、時々 S3 エンコーディングを受信しました消去、私たちはエンコードコロッサスにおける消去。それある種の大きな突破口。

</details>

**主持人**：等一下，这具体指的是什么编码技术？

<details>
<summary>Original English</summary>

**Host**: 何、何のエンコーディングですか？

</details>

**Colossus 工程师**：哈哈，我们采用的是里德-所罗门算法（Reed-Solomon Algorithm）。

<details>
<summary>Original English</summary>

**Colossus Engineer**: ハァ。私たちは使用済みリードのアルゴリズムソロモン。

</details>

**主持人**：说到这里，听众听到纠删码时会联想到什么吗？比如有人会说“我想要多条冗余校验”，或者类似 RAID 阵列那种机制？

<details>
<summary>Original English</summary>

**Host**: えっと、それで、聴衆が消去によって、何か思いつきますか？例えば「私は欲しい線がある」、ええと、そしてそのようなもの、ええと、RAID と呼ばれる。

</details>

### Reed-Solomon 纠删码与存储成本优化

**Colossus 工程师**：对我来说，传统完全多副本机制并不是绝对必需的。如果采用更高级的方案，如今这种方法也变得越来越普及。在当时，我们不得不强制让分布式文件系统支持这种机制。我们的关注点在于，如何获得更高效的数据存储机会。相比传统的全量副本存储，纠删码要高效得多。在老一代的 GFS（Google File System）中，存在各种各样的开销。过去为了保证可用性，往往不是存两份或者单副本，而是必须存三份数据副本。而引入里德-所罗门算法之后，存储开销大幅削减。我虽然记不清最初采用里德-所罗门的确切细节，但它实质上节省了近两倍的冗余开销。

<details>
<summary>Original English</summary>

**Colossus Engineer**: 私はあまり完全必須レプリカ。私はできる A プラスを取るなら、.そしてますます今はあると思います。方法によっては、そうですね。はい。And we had to, uh- 強制的にそれは働くことです分散型ファイルシステム？あなたは集中していましたね。保留、保留機会より効果的データストレージ。それは彼らよりも効果的ストレージ。つまり、GFS では、ええと、さまざまな費用があります。保存しない場所 2 部または 1 部データのコピーまたは 2 部、3 回保存になるだろう使用。そしてリード・ソロモン大幅にそれを減らす。私はそうではない最初から覚えている私たちが用途リード＝ソロモンだが、それは実質的に 2 倍。

</details>

**Colossus 工程师**：不过，采用这种方式也是带有保留条件的。虽然表面上看开销减少了，但背后需要技术权衡。对于未经深思的天真想法，通常会说：“好的，我的数据要在 3 个位置做副本”，也就是 3 个节点、3 台物理机器。然后你说：“这里一份拷贝，那里一份拷贝，总共 3 处拷贝。非常完美。如果其中一台机器故障爆炸了，我还剩下两份完整的拷贝，完好无损。”但是纠删码算法并不是傻傻地存储 3 倍数据，而是通过聪明的数学方法把原本 2 倍左右容量的数据切分打散到多台机器上。即使其中某些机器离线或损坏，数据依然完好保留，因为它已经被智能分片了。

<details>
<summary>Original English</summary>

**Colossus Engineer**: でもあなたはあなたもこれを受け取ります留保付きで。それで、少ないように見えるが、上記の予約について。だからこそ、私は思うのですが、世間知らずは世間知らずだあなたが言うとこうなります：「はい、私は私のデータは 3 つの複製場所」3 つのノード、3 つのマシン、物理的な機械、そしてあなたはこう言います。「1 つのコピー 1 つのコピー、コピー 1 つ。私は３箇所。完璧です。もしそのうちの 1 つが爆発する、私はすべてを持っている 1 つは 2 つのまま残る、完璧に。そしてあなたはアルゴリズムはあなたなのいいえ 3 倍のデータ、そしてデータ量は 2 倍に賢く分割するそれらを機械間で、または、もしかしたらあなたはそれらを取り上げて下げてください。例えば、それらは爆発するだろう、私は私のデータはすべてまだ残っています。分割されているため半分に。右。

</details>

**Colossus 工程师**：为了在高层次上理解这一点，你可以建立这样一个心智模型：假设你想要 8 份或 9 份数据碎片。Google 官方在公开场合也介绍过这种架构。比如总共有 9 个数据分片，只要其中任意 5 个分片存在，就可以完整重建出原始数据。这就意味着你即使丢失了多块磁盘或机器，依然能恢复数据。很多时候的典型配置是：前面 5 个分片是精确的数据载荷，剩下的 4 个分片是奇偶校验分片（Parity）。具体的参数细节我有些淡忘了，但核心原理就是这样。

<details>
<summary>Original English</summary>

**Colossus Engineer**: あなたも使用メンタルモデル、もしあなたがただ望むならこれを理解する高レベル、つまり次のように言うことができます。「私は 8 人欲しい。このデータのコピー。」または、私には無理だと思います。使用九。彼らはすでに公の場で発言したこれについて。持っていますか約 9 データの断片だが、これらのうちどれか 5 つ断片は彼らのために使う再建。それつまり、失う君ならできるデータ。多くの場合、これはむしろ、ほら、最初の 5 人断片は正確ですレプリカ、その他 4 部パリティ。私は少し詳細をいくつか忘れていました。以上です。

</details>

**Colossus 工程师**：你能从数学上证明这个算法到底可行还是不可行。这种可证明性非常关键，也是它能迅速落地应用的原因。它在工程上确实能够完美运转。至于背后的数学推导，坦白讲我并没有完全搞懂背后的所有高深数学。我有时挺后悔大学时没能多学点数学，但对于构建系统来说，其实并不需要你重新发明数学。里德-所罗门编码早在 1970 年代通信网络领域就已经被发明出来了。所以工程团队要做的是直接吸纳这项已有理论经验，并结合顶尖的系统工程能力，把它真正在大规模分布式存储系统中实现并稳定运行起来。

<details>
<summary>Original English</summary>

**Colossus Engineer**: でも、あなたはそれを証明できますこのアルゴリズムうまくいくか、それともうまくいかないか？はい？これは少し非常に重要な理由できるだけ早くうまくいくでしょう。うまくいくよ。そして、そんな感じ。私はわからない、私は私には全く理解できませんでした。すべての数学背後にいるのは私いつも後悔していたそれ以上はしなかった数学大学ですが、そうではありませんそれは必要だった。あなた、どのように読書と飛行、改良版どのように機能したか、そうですよね？これはそれは 1970 年代のいつ頃だったか何か関連のあるコミュニケーションネットワーク。だからあなたはこれを取ってあなたが知っている、これを使っていますか？経験はありますが、使ってみてそしてあなたはすべてをしなければならない優れたエンジニアリングこのため、これがシステム内で作業しましたデータストレージ。

</details>

### GFS 扩展瓶颈与 Bigtable/Colossus 循环依赖

**主持人**：在构建类似 Colossus 这种既要保证数据高可靠、又要追求极致效能的分布式存储系统时，当时还需要解决哪些核心问题？

<details>
<summary>Original English</summary>

**Host**: そして、あなたが作成する分散システムデータストレージ、コロッサスなど、まだ物事は、普通だよ、君保存したいデータは安定しているが、効果的な方法で？他に何か問題はありますか？それは必要だった解決する？

</details>

**Colossus 工程师**：我认为关键问题集中在分片（Sharding）、动态重新分片（Re-sharding）以及元数据管理（Metadata）上。特别是在早期，Google 依赖 GFS 支持业务，但 GFS 面临着极其严峻的可扩展性限制。我记得当时的上限大概只能支撑约 1000 台机器构成的集群。从现在的角度来看可能觉得有趣，觉得这怎么可能够用呢？但在 2004 年那个时期，1000 台服务器已经是极其庞大的集群规模了。然而 Google 的业务发展迅猛，系统迫切需要扩展到能够支撑 10,000 台机器的规模。

<details>
<summary>Original English</summary>

**Colossus Engineer**: 私は思う潜在的に重要シャーディングのようなもの再シャーディング、またはメタデータ、そういったこと。ええと、特に Google が GFS で働きたいこの制限があった拡張性。私あれが全てだったと思います。千人かもしれない車、そしてそれは何かどのような、どうやらこれは面白いそれだけでは足りないですよね？2004 年にしてはかなり多いように聞こえる年。そしてグーグル「いいえ、私たちはそれは必要だった最大 10,000 まで拡張可能機械」

</details>

**Colossus 工程师**：随之而来的就是严重的系统瓶颈。在 GFS 架构中，GFS Master 节点陷入了巨大的困境。系统需要一个能够支撑海量对象的分布式主元数据存储系统。当时 Google 已经有了名为 Bigtable 的系统。于是 Colossus 选择将自身的文件元数据全部存储在 Bigtable 内部。这也是我个人引以为傲的解决方案之一。但实际上，我们将文件拆分为一个个分布式的 64MB 数据块分片（Fragments of 64MB），每个文件都是如此，并且配套了自动修复机制（Repair Work）。简而言之，这就是整体机制。因此，为了让 Bigtable 正常工作，Bigtable 需要运行在 Colossus 之上；而 Colossus 的元数据又存放在 Bigtable 中。

<details>
<summary>Original English</summary>

**Colossus Engineer**: そしていくつかボトルネック。こんなのがあった GFS マスターノード、ちょっと窮地に立たされている。必要分散型メインノードメタデータストレージ for all objects. そしてシステムと呼ばれるビッグテーブル。コロッサス彼はメタデータ内部 Bigtable. そして、その一つは、私はそれを誇りに思っていますし、解決策の一つしかし実際は私たちは分散型分散型断片。これは一体何ですか？だった？Fragments of 64 メガバイト。そして各ファイル。はい。そして, repair work. そして That's it for short. したがって、最大の Bigtable なので、私たちは、Bigtable を動作させるにはコロッサスの頂上。

</details>

**主持人**：也就是说，这里形成了一个环状概念，就像韦恩图（Venn diagram）中的交集循环，对吧？数据加载时，它到底是怎么启动运行的？肯定需要某个地方来为这种依赖关系建模吧？

<details>
<summary>Original English</summary>

**Host**: つまり、円の概念、見てくださいベン図、お分かりですか？ええ、まあ、読み込み中ですよね？はい、読み込み中です。ああ、そうだね。はい。どれか動いていますか？のように、どこかが必要何かをモデル化するということですよね？

</details>

**Colossus 工程师**：其实既是又不是。事实是在当时那个阶段，这种做法确实能够正常工作。虽然后来团队对这个架构进行了替换改造，但在一开始起步阶段，你必须利用手头现有的系统组件。尽管最终我们会消除这种循环，但早期 Bigtable 确实是构建在 Colossus 之上的，而 Colossus 又使用 Bigtable 来保存元数据，Bigtable 实例就常驻在 Colossus 顶层。这就是当时的实际架构，而且它稳定运行了很多年。我记不清他们具体是哪一年彻底重构移除这种依赖的。但在系统演进过程中，这种务实的工程 Hack 起到了决定性作用，它帮助团队走出了停滞不前的死局，让系统能够向前迈进。因为如果我们非要在最底层重新实现一套独立于 Bigtable 的元数据存储层，从零开始的话，那势必会造成巨大的工程延期，拖累 Colossus 整体系统的面世进程。

<details>
<summary>Original English</summary>

**Colossus Engineer**: はい、いいえ。つまり本当のところは当時働いていた、そしてそれ以来彼らは交換したんだよ、なぜならそれは始め方とそれを使うには、あなたが持っているもの、そして最後にあなたは取り除くこれだが、いくつか Bigtable 財団は、 Bigtable はコロッサスを使用しました。巨像があり、 Bigtable を使用し、そしていつものように大型テーブル（立ち見）コロッサスの頂上。私が言っているのはこのことです。そして、すべてうまくいった。何年も前から、だから私はそれらがいつのものかは分かりません。これを処分しました。彼らはこれを削除しました一瞬だけど、えーと…えっと、あれは…でも、私は…そう思うのですが…何が作れるのか進行中のハッキング長い間、これらはハッキングであり、あなたを助けています死者から蘇るポイントですよね？移動ど真ん中ですよね？はい？なぜなら、もし私たちがそうしなければならなかったんだ、ほら、このようなことを実施する Bigtable レイヤーは、始めれば、簡単だろう遅延時間、必要コロッサスの創造。

</details>

### 存储硬件演进与 NVMe 的低延迟革命

**主持人**：在类似 Colossus 这样的分布式文件系统中，最令人震撼的是它们对外所承诺的性能指标——无论是在 Google 内部还是业界的分布式文件系统中，它们都承诺高吞吐能力、高可用性以及极低延迟。但在我看来，这一直是存在争议的技术权衡。在我有限的认知里，构建一个高吞吐或高容量的分布式系统可能不算太难，但每一次操作都要经过多条网络线路传输，这必然会带来高延迟。正如你刚才所描述的架构，分布式文件系统到底如何才能在保证高吞吐的同时，把访问延迟压到极低？

<details>
<summary>Original English</summary>

**Host**: 私がシステムの中で衝撃的、コロッサスと同様に、彼女が約束すること、あるいは少なくともこれ約束されるだろう、それは Google 内部では、しかし、分散ファイルシステムは外部の、彼らは約束する高スループット能力、高いアクセシビリティと低遅延。そして私にとってはいつもやや物議を醸す、例えば、そうですね、私は思うこれはとても簡単です建てる分散ファイルシステムシステム。私の限られた知識おそらくできるでしょう。何かをする私は高い容量、しかしレイテンシーが高く、なぜなら毎回 This is for all the lines. あなたすでに述べたもの方法だが、どのように例えば、同意する、低くなる方法遅延、高スループット能力、また起こっているファイルシステム？

</details>

**Colossus 工程师**：其实早期这些分布式文件系统的绝对延迟并没有想象中那么低。在机械硬盘为主的时代，不论是 Colossus 还是 AWS S3，你都能非常明显地感知到延迟。作为生产级系统，AWS S3 以及 Google 的竞争产品 GCS（Google Cloud Storage），在架构上都是优先针对带宽吞吐做优化。单次机械硬盘读取的延迟通常在 20 到 30 毫秒之间，这个延迟很大程度上直接受限于机械硬盘的物理寻道时间。即使后来部署到了普通 SSD 上，虽然延迟有所下降，但也受限于当时的 SSD 控制器架构。

<details>
<summary>Original English</summary>

**Colossus Engineer**: つまり、これらの分散型ファイルシステム遅延はそれほど大きくない低い。つまり一生懸命にコロッサスが作った円盤今のところ、何をしているのでしょうか S3、あなたは本当に遅延に気づきます。非常に生産的システム、Google、うーん、GCS、 Google の競合相手、を基盤として構築された帯域幅、読書は 20～30 ミリ秒、そしてそれは限られている遅らせるハードディスク。もしインストール先 SSD、レイテンシーは SSD ですが、実際にはそうではありません最もモダンな SSD のレイテンシは、私たちの産業、単にどれだけ速く機器になった。

</details>

**Colossus 工程师**：在整个存储行业中，硬件设备性能的飙升是革命性的。传统机械硬盘的读取耗时大约在 5 到 10 毫秒，我现在基本上都不会再去碰机械硬盘了。而现在通过 NVMe 接口从现代高速 SSD 读取数据，仅需 50 微秒（50 µs）。50 微秒是什么概念？1 毫秒等于 1000 微秒！两者之间的速度差距足足有几个数量级。现在涌现出许多新兴的初创公司与底层基础设施团队，他们敏锐地抓住了这个技术转折点。他们利用 NVMe 存储层，重塑并拉升了整个存储系统的性能表现。正如你所看到的，当底层物理硬件现实发生质的改变时，软件架构也必须做出相应变革。

<details>
<summary>Original English</summary>

**Colossus Engineer**: ハードドライブから読み込んでいますディスクは現在使用中です 5～10 ミリ秒、つまり、私は私は決して触らない。ハードドライブ。 NVMe 経由で SSD から読み込む 50 マイクロ秒かかります。 50 マイクロ秒。これはマイクロ秒、1 ミリ秒 1000 マイクロ秒。だから私たちは私たちが話しているのは大きな違いだ。さて、今はスタートアップ企業がありますまたはインフラストラクチャ企業が始めるそれを使え彼らができるという事実 NVMe レイヤーがあり、彼ら、彼ら、彼ら物を引き上げる、または予想通り、あるいは予想外だが、おっしゃる通り、例えば、物理的現実変更すれば、システムを作成する使用すべきここに。

</details>

**Colossus 工程师**：毫无疑问，改用 SSD 之后磁盘速度获得了极大的提升。在 Google 或 Amazon 的同可用区（Zone）数据中心内部，延迟表现快得惊人。但是回想我们当年刚开始做 Colossus 时，数据中心可用区内跨机数据交换的耗时依然是毫秒级别的。回想起来，我常常感慨系统居然真的能够把如此高吞吐的服务稳定交付给上层。有时候我们会认为软件应该做得更快，甚至有些软件过于复杂了，我们往往依赖层层封装而忽视了底层开销。

<details>
<summary>Original English</summary>

**Colossus Engineer**: はい、もちろん、あなたもいいですか、それはディスクが SSD を使うとずっと速くなります。もっと早く。つまりそれはまさに狂気だ、どれくらい速いかゾーン内 Google センターの遅延 or Amazon. それははい、しかし私たちがコロッサスを創造し、それらが何だったか覚えている。ミリ秒データ交換、そしてゾーン。つまり、私はこれらのことを考えます。「本当に提供「うまくいった。」はい、時々私はソフトウェアはるかにより速く、そしていくつかのソフトウェア。時々私は多すぎる私たちは皆に頼っています私たちはそのようなことは一切しません。

</details>

### 物理极限思考：光速、光纤与跨地域网络

**主持人**：这就像 Simon Eskildsen（Turbopuffer 创始人）经常提及的“餐巾纸数学估算”（Napkin Math Analysis）。从理论角度来审视硬件物理极限与软件设计的边界：从高速 SSD 读取数据与构建整体分布式系统之间存在巨大差异，人们往往会忽视物理层面的硬性约束。有时我们不仅要考虑人为软件栈带来的开销，更要直面底层存储系统的物理规律。在 Turbopuffer，他们在这方面做得极其出色。

<details>
<summary>Original English</summary>

**Host**: ナプキンのようにサイモン・エリクソンとターボ Buffer はこれについて話しているナプキン数学的解析、つまり、こう思ったでしょう。「さて、理論はこうだ。ハードウェアの制限ソフトウェア; SSD からの読み取りはシステムを構築する、とは異なりええと、人は気づくだろう、私たちは、これ。はい、はい。そして時には、例えば、考える必要がある人為的な遅延もありますが、多くの場合、レベルに対処するストレージシステム Turbo  Popper では、彼らはそこで素晴らしいことをしている。もの。

</details>

**Colossus 工程师**：你需要站在机器与人类感官差异的尺度上来思考速度。机器处理与传输的速度远远超出了人类的感知范围。例如，普通人类能够耐受的操作延迟大约在 100 毫秒左右；如果你在玩即时竞技游戏，可能感知到的帧时间在 4 毫秒左右。但机器对低延迟的渴望与要求远比这严苛得多。正如 Simon Eskildsen 用纯粹的数学数字向我们揭示的那样：跨数据中心可用区之间、跨地理区域之间的物理延迟，最终不可避免地会撞上物理学的天花板——光速在光纤网络中的传播速度。你想听一个令人惊叹的冷知识吗？

<details>
<summary>Original English</summary>

**Colossus Engineer**: あなたには規模について考えてみよう車とスピードはるかに機械人間より速い感知。例えば、ある人が耐えることができる約 100 の遅延ミリ秒、またはあなたはゲームをプレイしています、もしかしたらあなたにはフレームレート約 4 ミリ秒ですが、車はたくさん欲しいそれよりも。サイモンは言う：「数学数字で、そして時には文字通りあなたを…ゾーン間の遅延、間の遅延地域、これ光速と fiber optics. 欲しいですかいくつか聞く驚きの事実？

</details>

**主持人**：我很乐意听，请讲讲这个令人惊奇的冷知识。

<details>
<summary>Original English</summary>

**Host**: 聞くのが好きです。驚きの事実。

</details>

**Colossus 工程师**：在物理世界中，向远方发送数据包速度最快的方式，实际上是把信号发射到太空中去传播。为什么？因为光在真空中的传播速度要远远快于光在玻璃光纤中的速度。光纤并不是真空，光在光纤玻璃介质中的速度只有真空中光速的约三分之二左右。所以在更长地理距离上，通过太空自由空间激光或无线传输，能够覆盖更远的距离并获得更低的网络延迟。

<details>
<summary>Original English</summary>

**Colossus Engineer**: 最速の方法荷物を送る弾丸を発射する彼を宇宙へ連れて行った。これは速度が真空中の光はより高い？はるかに速い。いや、正確には、まだ完成していない。真空。とんでもない。はい。だから、あなたはもっとカバーする距離。はい。

</details>

**主持人**：是的，那在工程实践中，这具体到底该怎么实现呢？

<details>
<summary>Original English</summary>

**Host**: ええと、実際には、どうやってやるの？

</details>

<!-- chunk 4/8 -->

### 空间通信与微波传输的物理瓶颈

**Speaker A**: 请你把它发过去。

<details>
<summary>Original English</summary>

**Speaker A**: Send it over, exactly that.

</details>

**Speaker B**: 确实就是这样。发送之后，Starlink 会将其传输到地球另一端降落接收。也就是说，你需要尽可能快地将信号送出大气层，同时完成数模转换。所有这些环节都需要时间。如果你能做到这一点，传输速度甚至会超过光纤电缆在介质中减速后的传播速度，我说得对吗？

<details>
<summary>Original English</summary>

**Speaker B**: That's right. After that, Starlink transmits it, sending it down on the opposite side. That is, you want to get it out of the atmosphere as quickly as possible, plus the digital conversion. All that takes time. If you do this well, transmission can end up being faster than optical cable where the speed slows down in the medium, right?

</details>

**Speaker A**: 在任何其他物理介质中，传播速度都会变慢。我深入了解过这方面的讨论，有人提到使用卫星和微波链路，但他们并没有把这些方案提供给你使用。

<details>
<summary>Original English</summary>

**Speaker A**: In any other medium, it's slower. I had discussions; I went deep into it. They talked about using satellites and microwaves, but they don't offer those to you.

</details>

**Speaker B**: 但他们很可能会这么做。是的，没错。所以他们使用的高频波段其实波长并不够大，无法在自由空间中随心所欲地传播，因此他们必须依赖微波束。

<details>
<summary>Original English</summary>

**Speaker B**: But they probably will. Yes. Yes. So what they do is, high frequency is not actually big enough to transmit through space freely, so they use microwave beams.

</details>

**Speaker A**: 没错。但如果你真想达到极致的速度，就必须在它们之间建立某种真空管道之类的东西来进行传输……也许他们将来真会这么干。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. But if you really want to be faster, you need to build something between them, like a vacuum tube to send it through... Maybe they will actually do that.

</details>

**Speaker B**: 也许真的会。是的。

<details>
<summary>Original English</summary>

**Speaker B**: Maybe they might. Yes.

</details>

### 深入底层：消除同步与多级缓存层次

**Speaker A**: 在我看来，如今系统的极致性能之所以如此惊人，正是因为你在许多抽象层之上必须为吞吐与延迟付出代价。这是一个非常深的无底洞。你几乎肯定是在一个多线程系统上进行开发，对吧？然后你可能会想：“既然我在写多线程程序，我就必然需要同步机制。”然而，要想获得最顶级的性能，最好的办法其实是尽可能避免同步。这一方面是靠无锁编程技术，但另一方面更依赖于精细的数据排布，使得根本不需要锁。你必须时刻关注处理器架构。

<details>
<summary>Original English</summary>

**Speaker A**: But I mean, in my opinion, performance today is just incredible, exactly because of how many layers you have to pay for performance. This rabbit hole goes extremely deep. You are almost certainly working on a multi-threaded system, right? And you think: "Oh, I need a multi-threaded program, so I need synchronization." To get the best performance, you just avoid synchronization. Part of this is lock-free programming, but part of it is layout so that locks aren't needed at all. You have to pay attention to the processor.

</details>

**Speaker B**: 没错，处理器之上还有整套完整的缓存体系。比如 L1、L2、L3 缓存，然后才是主内存和磁盘。要榨取极致性能，你就必须考虑这些层级。如果你优化了对缓存行的访问，程序的性能就会获得成倍的提升。有些人全天候都在死磕这种极高频的优化，还有许多其他维度的考量。如果你忽视这些，软件的运行效率就会一步一步衰退。

<details>
<summary>Original English</summary>

**Speaker B**: And there is a whole system of caches above the processor: L1, L2, L3, memory, and to disk. You need to work with these levels. If you optimize access to the cache, performance will be massively improved. Some people focus heavily on this all day. There are many other aspects, like this focus. You also get gradual degradation of software performance if you ignore it.

</details>

### B-树对决标准库红黑树：从缓存行颠覆 STL Map

**Speaker A**: 我们再深入聊聊编程和库的构建吧。你构建过好几个底层数据结构，那些设计堪称精妙绝伦。我觉得大众通常只把排序算法当成某种神奇的技术，你能不能简单讲讲？或者它其实要复杂得多？

<details>
<summary>Original English</summary>

**Speaker A**: Let's talk a bit more about programming. You built several libraries, data structures that are quite brilliant. I mean, generally, people just think sorting algorithms are fascinating. Can you explain sorting simply, or is it much more complex?

</details>

**Speaker B**: 我懂你的意思，这些结构确实非常精巧。当你深入到这些底层细节时，就会惊叹：“等等，竟然有人能发明出如此聪明的点子！”以前我在 Google 做兼职时做过一件事，当时有位同事走过来对我说：“你知道吗？我们在代码库里到处都在使用 STL map 结构。”而标准库的 STL map 底层是一棵平衡二叉树，不管它是红黑树还是大学计算机科学专业教给学生的其他平衡树算法。他找到我并提出：“我觉得我们可以把这个做得更好。因为你看，现有的实现存在非常严重的 CPU 缓存命中问题。每次你在二叉树中遍历一个节点，几乎都会跳到一个全新的缓存行（cache line）上去。”

<details>
<summary>Original English</summary>

**Speaker B**: I know. I know all of this. Yes. And you look at it and go: "No, no, but this is clever..." Yes, you reach these levels where you say: "Oh, wait. Someone invented a really clever idea here." So, one thing I worked on when I did some part-time work at Google: a colleague came up to me and said: "You know what? We use the STL map structure everywhere." And the STL map is a balanced binary tree—whether red-black trees or whichever balancing algorithm they teach computer science students at university. And he came to me saying: "I think we can do better, because look, here is actually an issue with cache. Every time you traverse a node, you cross into another cache line."

</details>

**Speaker A**: 于是他就开始构思用别的数据结构来替代单纯的指针链表遍历？

<details>
<summary>Original English</summary>

**Speaker A**: And he thought about using something else instead of pointer paths to do this, some wonderful data structure that everyone should pay attention to?

</details>

**Speaker B**: 是的。当时我想了一下，觉得这实际上非常接近 B-树（B-tree）。在此之前我已经亲手实现过好几次 B-树，非常清楚如何去构建它，而且它几乎可以完整承载 STL map 的全部语义。它之所以能做到这一点，是因为当你向 B-树节点插入数据时，虽然节点内的数据可能需要挪动以腾出位置，从而破坏了直接的指针稳定性，但只要使用场景允许，它就能容纳更多密集排布的数据。

<details>
<summary>Original English</summary>

**Speaker B**: But for a moment I thought: "Actually, this is close to a B-tree." I had already implemented B-trees several times and understood how to build one that preserves almost all the semantics of STL map. It can do this cleanly, though when you insert data into a B-tree node, you may have to shift data around, so you don't get pointer stability. If that's acceptable for your use case, it actually packs much more data together.

</details>

**Speaker A**: 在现实世界中的 B-树也是同样的道理吧？

<details>
<summary>Original English</summary>

**Speaker A**: So the thing is, in the real world, a B-tree works just like that to explain this?

</details>

**Speaker B**: 没错。比如如果你只有很短的一组元素，比方说 8 个元素，想要最快地访问它们，最简单的做法就是对这 8 个元素进行排序存储。此时你根本不需要任何树形指针结构，就是一个极其扁平简单的有序数组，直接在上面做二分查找就行。在很多情况下，这种扁平结构要快得多。你可以设想这样来构建它：从一个拥有 8 个元素的连续节点开始；当需要插入第 9 个元素时，就把它分裂成两半，一部分是 4 个，另一部分是 5 个，然后由一个父节点指向它们。然后你就可以递归地运用这种逻辑。简而言之，这就是 B-树算法的核心。

<details>
<summary>Original English</summary>

**Speaker B**: Exactly. Because if you have a small list of elements, say 8 elements, the best and fastest way to access them is just a sorted set of elements, right? Literally, you have no tree pointers at all. A simple list, a very simple sorted array, and you do binary search. Often that is way better. Think about building it like this: start with one node of 8 elements. Oh, I need to insert a 9th element? I split it into two parts—one with 4, one with 5—and then a parent node points to them. Then you just apply this recursively. That is the B-tree algorithm in a nutshell.

</details>

**Speaker A**: 听起来在工程实现上，其实并没有太多人真正把它彻底优化到位。

<details>
<summary>Original English</summary>

**Speaker A**: In practice, almost no one implements it all the way through like that today, even though there are so many optimizations you can perform on B-trees?

</details>

**Speaker B**: 确实，能在 B-树上进行的底层优化极其丰富。但回到当时的情况，当时已经有现成的 map 实现了，而你的同事看了一眼代码就说：“我觉得我们可以把它做得更好。”作为一个局外人，我以前总觉得那些基础库和核心数据结构肯定都是由最顶尖的大神坐在一起反复推敲构建出来的，现状必然已经是极限，不可能有更快的实现方式了。过去我也经历过类似的争论，比如总有人声称“这是绝对最快的排序算法”。但你能否具体讲讲在工业界内部究竟是怎样的？像你和你的同事们是怎样打破思维定势，提出“如果我们尝试点不一样的方案会怎样”的？

<details>
<summary>Original English</summary>

**Speaker B**: There are a lot of optimizations you can perform on B-trees. But coming back to this: there was an existing map implementation, and your colleague looked at the code and said: "I think we can do better." From the outside, you don't know how these libraries or data structures were built; I used to assume, perhaps naively, that really smart people had sat down, evaluated the state of the art, implemented it, and there was no way it could be faster. I've had disputes in the past where people claimed: "This is definitively the fastest sorting system." But tell us a bit about what actually happens inside, and how people like you and your colleagues end up saying: "Oh, what if we tried something else?"

</details>

### 从 Gaia 内部系统到缓存局部性的暴击

**Speaker B**: 当时他正在负责一个庞大的内部核心系统，我记得那个系统的名字叫 Gaia。相对而言，它的逻辑看似简单：当用户登录时，系统必须根据用户标识符去查询对应的身份认证数据。系统需要比对用户 ID 以及邮件相关的元数据，而这些信息在内存中全部存储在 STL map 结构里。当你打开内存分析器观察性能热点时，这些 map 操作赫然排在最前列。我们当时就在思考：“我们能不能改进它？”这就是整个项目的开端。于是他和我一起开始着手解决这个瓶颈。

<details>
<summary>Original English</summary>

**Speaker B**: He was working on a huge internal system called Gaia, if I recall. In comparison, when logging in, you have an identifier you need to look up. It compares the user identifier and email metadata stored in STL maps in memory. You look at where memory goes, and this shows up prominently in profiles. And we asked: "Can we improve this?" That was the beginning. He and I started tackling this problem: "Let's build our own internal library." At that point, working on our own system, he contributed it back to the shared codebase.

</details>

**Speaker A**: 这正是在复杂软件抽象层中常常会遇到的情况——某天内存消耗或者延迟突然出现爆炸式增长，你就必须刨根问底：为什么会变成这样？我们能不能对此做点什么？

<details>
<summary>Original English</summary>

**Speaker A**: That happens when managing layers. Everything seems fine, and suddenly there's a huge explosion in memory usage. You simply have to ask: "Why is this happening, and is there anything we can do about it?" Right?

</details>

**Speaker B**: 没错。他在早期阶段就敏锐地发现了一个问题：在那个 map 中，键（key）通常只是一个整数标识符，映射到某些数据结构上。但在传统的红黑树中，每一个树节点除了你要存的键值对之外，本身还需要维护左右子节点指针以及父节点指针等额外开销。你的整数 ID 可能只有 4 到 8 个字节，但每个节点挂着的指针开销却达到了十几个甚至几十个字节，对吧？当你仔细审视它时就会意识到：“天啊，这里的内存开销太惊人了！”而如果换成 B-树，不仅空间局部性（spatial locality）大幅改善，CPU 缓存命中率显著提高，整体查询遍历的速度也会快得多。

<details>
<summary>Original English</summary>

**Speaker B**: Right. In the early stages, he realized that in a map mapping integer identifiers to something else, look at a red-black tree: each node stores pointers in addition to your data. You might have an integer identifier of 4 or 8 bytes, and then multiple pointers... right? You look at that and think: "Oh, this is a massive overhead." And with a B-tree, you get much better spatial locality, which makes it significantly faster.

</details>

**Speaker A**: 但同时，这在后来也促成了对 Go 语言生态的重要贡献，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: But at the same time, that led to contributions to Go later on, right?

</details>

**Speaker B**: 是的，那都是后来的事情了，我们稍后可以深入聊聊这个。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Well, that came later. Can we talk about that in a moment?

</details>

### 哈希表演进史与 Google Swiss Tables 的突破

**Speaker A**: 好的，另外我还注意到一个事实，那就是哈希表（Hash Table）的研究演进。哈希表是你不需要按顺序存储元素时最常用的核心数据结构。随着时间的推移，构建哈希表的技术不断涌现，从最早的拉链法哈希链（hash chain），到各种开放寻址重哈希探查（re-hashing），再到沿着桶数组向下查找合适槽位来存放数据。我记得曾读到过一项革命性的新技术，是由 Google 的工程师团队研发出来的，似乎正是诞生于他们的瑞士苏黎世办公室，因此得名“Swiss Tables”（瑞士表）。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Okay, another thing I pay attention to is research into hash tables. Hash tables are the data structure when order doesn't matter. Over time, ways to create hash tables evolved: using an array of segments, things called hash chains, or re-hashing and probing down segments to find an empty slot where you belong. I remember reading about this new technique that originated from Google engineers, apparently in their Swiss office, which is why it's called Swiss Tables.

</details>

**Speaker B**: 是的，确实如此。据说这就是该名字的由来，我相信毫无疑问源于瑞士团队。后来当我使用 Go 语言进行开发时，Go 语言内置了 map 结构。那本身就是一个高度优化过的哈希表，因为 Go 运行时团队非常顶尖优秀。当时社区里有很多人尝试为 Go 语言移植并实现 Swiss Tables 算法。我当时看了几个开源实现，心里直犯嘀咕：“他们搞的这个 Swiss Tables 看起来很有意思，我稍后会解释它是如何做到如此高效的。但我看了他们的实现后发现，想要在纯 Go 层面击败精心打磨的 Go 运行时内置哈希表，难度极其巨大，因为官方运行时的原生实现已经极其出色了。”

<details>
<summary>Original English</summary>

**Speaker B**: Yes, exactly. That seems to be why it got that name. I believe that's where the name came from. Later, when I was working with Go, Go had a built-in map structure. It's a hash table, an extremely optimized hash table, because the Go team has very talented engineers working on the runtime. Different people tried writing Swiss Tables implementations for Go. I looked at some of them and thought: "It's very interesting what they are doing with Swiss Tables—and I'll explain in a moment how it works—but looking at this, it's really hard to outperform the Go runtime." The runtime execution is already so good.

</details>

**Speaker A**: 所以你当时也按捺不住想要亲自上手试一试了？

<details>
<summary>Original English</summary>

**Speaker A**: I continued pondering this for a while, and eventually you decided to take on the challenge?

</details>

**Speaker B**: 我心里琢磨了这事好一阵子。直到后来我有一次去印度班加罗尔出差，在路上犹豫了很久，最终决定：“行，我也来动手写一个试试看。”我写了非常详尽严谨的基准测试（benchmarks）。对于工程师来说，这种挑战就像猫薄荷一样让人欲罢不能——你会忍不住想：“我也能写出这种东西吗？我能让它跑得比现有一切都更快吗？”很多人都曾尝试把 Swiss Tables 应用到 Go 语言中，但连很多 Go 语言的专家都会警告你：“这里的坑非常深，你必须巧妙绕过各种运行时机制和边界……”

<details>
<summary>Original English</summary>

**Speaker B**: I kept thinking about this for a while. Eventually, I had a business trip to India, to Bangalore. After hesitating for a long time, I thought: "Okay, let me try to build one." I set up solid benchmarks. It's like catnip for an engineer: "Can I do all this? Can I make it faster than everything else out there?" People had tried using Swiss Tables, and Go experts would say you have to navigate through this and that hurdle...

</details>

<!-- chunk 5/8 -->

### Go 运行时贡献与外部参与

**Peter**: 那时其实提出过一些思路，正是这些想法把大家凝聚在了一起。至于具体的实现，包括基准测试以及在多数场景下的确切验证，后来都是由 Go 核心团队成员在时机成熟时独立构思并落地的。

对我所在的公司来说，我们原本那套实现完全够用；但在 Go 语言的运行时环境层面，它属于截然不同的工程级别。

我们当时所做的，就是把原型实现展示给官方看，他们从中获得了启发并给出了反馈：“太棒了，这正是我们一直想做的方向……”Go 团队始终在寻找让运行时运行得更快的方法。他们看后立即表示：“等等，先别急，我们来梳理这个方案。”经过后续数年的持续贡献，整个方案才逐步演变成型。

<details>
<summary>Original English</summary>

**Peter**: There were a few ideas, and that's kind of what brought them together. And then the implementation, the benchmarks, exactly the quorum, and then the idea came from someone on the Go team once they were able to.

Well, mine was accurate for my company. It worked well for us to use, but actually the implementation at the runtime environment, that's a totally different level.

You just showed them, here's an implementation, and they took inspiration and gave ideas: "Yes, that's great. We want to do everything..." They're always looking for ways to make the runtime faster, and they just said, "Oh, wait." And you made this with many contributions over the years.

</details>

**Gergely**: 你当时其实已经离开 Google 好几年了吧？所有这些贡献，都是你作为外部人员从外部完成的，这确实非常了不起。

<details>
<summary>Original English</summary>

**Gergely**: You left Google years ago, right? Yeah? That's all done from the outside. This is from the outside. That's great.

</details>

**Peter**: 是的，而且不仅是我，还有其他外部开发者也在做类似的贡献。比如我们有位前同事，他就为 Go 贡献了 CRC 的一种底层实现。

<details>
<summary>Original English</summary>

**Peter**: Yeah, and other people are contributing from the outside. You know, we had another colleague. He contributed one of the CRC implementations.

</details>

**Gergely**: 是指对 CRC 算法所做的改动吗？

<details>
<summary>Original English</summary>

**Gergely**: Some changes to CRC?

</details>

**Peter**: 嗯，也就是循环冗余校验码（Cyclic Redundancy Check）。当时英特尔发表了几篇利用汇编指令超高速执行 CRC 计算的论文，他就基于这些成果向 Go 官方提交了一版高性能汇编实现。

在 Go 社区里，经常能看到这种完全来自外部贡献者的优秀代码。虽然我不敢说自己了解所有细节，但一直以来，社区成员都在源源不断地向运行时和核心库贡献成果。

<details>
<summary>Original English</summary>

**Peter**: Um, checksum, cyclic redundancy check. Hmm. Yeah, Intel published some articles on doing very fast CRC in assembler, and he contributed one of the implementations from that. You see a lot of these things where people just contribute from the outside. This is not unusual. I mean, I don't really know all the details, but people regularly contribute to these things.

</details>

---

### 节目赞助：Linear 与团队 AI Agent 协作

**Gergely**: 彼得刚刚讲述了 Go 语言中 Swiss Tables（瑞士表）的演进过程——从最初在 Go 问题追踪器上的 issue 讨论，到各方开发者共同参与，再到 Go 团队最终将其推向终点线。

说到工程协同，这里也顺便向大家介绍本季的赞助商之一：Linear。他们正在致力于构建人类开发者与 AI Agent 之间的工作协同体系。

我观察到的一个普遍现象是：现在大家与 AI Agent 的协作基本还停留在“单人游戏”阶段。你打开一个终端窗口，与 Agent 进行对话，最后生成了一个 PR。但团队里的其他成员完全不知道这个会话里发生了什么，除非你逐字逐句把聊天记录复制给他们。如果每个人都这样各自为战，大量的工程上下文就会沦为团队看不见的盲区。

Linear 的核心理念是：AI Agent 应当成为具备透明协作能力的团队一员。

在日常研发流中，当你在 Linear 中梳理好需求并确定需要执行的任务时，可以直接将工单指派给编码 Agent。无论这个 Agent 是 Linear 原生集成的工具、来自 Codex 体系，还是自定义配置的 Agent，负责委派任务的工程师始终对交付质量把关。

我非常赞赏 Linear 贯彻的设计原则：让协作过程始终处于可视化状态。团队成员可以实时跟进 Agent 的工作会话，检查它所生成的 PR，并无缝参与代码审查。这让我们真正从单人单机的局部敲代码，跨越到多角色并发协作的软件工程形态。

此外，Linear 在成本管理上的考量也格外实用。Linear Agent 内置了智能模型路由机制，能够自动针对特定任务匹配最具性价比的模型；团队也能清晰追踪用量并设置调用预算上限，从而在充分赋能工程师使用 Agent 的同时，将基础设施开支稳稳控制在合理范围之内。欢迎访问 linear.app/pragmatic 了解更多详情。

<details>
<summary>Original English</summary>

**Gergely**: Peter just described how the work on Swiss Tables came out of tracking Go tracker issues, with different people participating in the work, and then the Go team taking it all across the finish line.

Here's a reminder about our season sponsor Linear, which is about work coordination between people and agents.

One thing I've noticed is that, like most of us working with agents, it's pretty much a single-player game. You open a terminal interface, talk to an agent, and that usually results in a PR. But the rest of your team has no idea what happened in that chat unless you tell them and copy the whole history. And when everybody on the team works like that, a lot of work happens invisibly to the rest of the team.

Linear's perspective is that an agent's job is to be a team player. Even today, you decide what work needs to be done. Now in Linear, you can already delegate an issue to an agent coder. This agent can be a Linear integrated agent, for example from Codex, or whatever agent you prefer. In either case, the engineer who delegates the task remains responsible for the outcome.

What I really like about Linear's operating principle is how visible the process remains. Your teammates can monitor the agent's session, check the PRs it creates, and jump into reviews. We've moved from single-user work to multiplayer engineering work with agents.

Oh, and another thing I like about Linear is the focus on costs. Linear Agent's auto-routing chooses the most suitable model for the task. Teams can also check usage and set limits, tracking usage so they can empower developers to use agents without letting costs spiral out of control. Join at linear.app/pragmatic.

</details>

---

### 节目赞助：WorkOS 与企业级权限隔离

**Gergely**: 前面彼得还提到了 Gaia——Google 内部用来验证用户身份与权限的核心登录系统。Google 在基础设施方面构建的技术确实令人惊叹，各项服务井然有序。但对绝大多数团队而言，我们不可能去从头研发一套属于自己的内部 Gaia。

这就引出了我们的另一位当季赞助商：WorkOS。它正是为广大开发者所打造的企业级“Gaia”。如果全靠自主研发，类似的基础设施往往需要耗费几个季度的工程人月。WorkOS 提供了单点登录（SSO）、SCIM 目录同步、审计日志记录、基于角色的权限控制（RBAC）等企业客户所严苛要求的全套能力，并将其封装为简洁优雅的 API。借助 WorkOS，处于成长期的企业无需搭建繁琐的自研认证平台，即可快速拿下财富 500 强级别的客户订单。

不仅如此，WorkOS 还在积极布局下一代身份与权限验证方案。他们最新推出的产品是针对 AI Agent 的授权与隔离网关：WorkOS Airlock。

试想一下：当你将具有数据清理权限的任务指派给一个自动化 Agent 时，最忌讳的就是赋予它毫无约束的长效凭证，否则一旦失控它可能会误删关键业务数据。

Airlock 运行在你的 AI Agent 与其调用的具体工具之间。它能够对 Agent 的调用意图进行精准拦截与审查，进而决定是放行、阻断，还是转交人工审批。简而言之，Agent 永远无法直接接触到底层凭证，每一次函数调用与审批判定都会被完整记录。Airlock 现已无缝适配 Claude Code、Codex 等主流代码编写 Agent 以及 MCP 协议网关。

如果你的团队正在构建并期望将 AI Agent 投入生产环境执行严肃任务，同时又不想授予它们过大权限，不妨访问 workos.com/airlock 详细了解 WorkOS Airlock。

<details>
<summary>Original English</summary>

**Gergely**: Peter earlier mentioned Gaia, the internal system Google uses for user login and authentication. What Google built is amazing; all the systems, including this one, are neatly ordered, but most of us don't have our own internal Gaia.

That brings us to our seasonal sponsor: WorkOS, which is kind of like Gaia for the rest of us. It provides the infrastructure you'd otherwise spend quarters building yourself. WorkOS has single sign-on, SCIM directory sync, audit logs, role-based access control—virtually everything major enterprise security teams ask for—delivered through clean APIs. This way, companies can move beyond basic login and sell to Fortune 500 customers without having to build their own internal identity platform.

And WorkOS is already developing the next version of authentication and authorization. Their latest product is authorization for AI agents: WorkOS Airlock.

Think about what happens when you give an agent a task, like the ability to clean up our sales pipeline. The last thing you want is to give it permanent, wide-open permissions where it could delete everything if something goes wrong.

Airlock sits between your agent and the tools it calls. It evaluates the agent's intent, and then allows, denies, or redirects it to a human for approval. Simply put, the agent never sees your credentials, and all calls and verdicts are registered. It works with coding agents like Claude Code and Codex, as well as via MCP gateways.

So if you're working on ways to let agents actually do production work without giving them excessive permissions, check out WorkOS Airlock at workos.com/airlock.

</details>

---

### 离开 Google 的初衷：探索新边界与 Viewfinder 创业

**Gergely**: 好的，让我们重新把话题切回彼得。在主导构建完 Colossus 之后，你究竟为何选择离开 Google？当时你身处 Google，打造了 Colossus 这种可能是全人类工程史上规模最庞大的分布式文件系统。老实说，在那个时间点，绝大多数人根本不会产生离开的念头，你当时是怎么想的？

<details>
<summary>Original English</summary>

**Gergely**: Now let's get back to Peter and why he left Google after creating Colossus. You're at Google, building the Colossus distributed file system. You were probably working on what is honestly one of the largest systems on Earth. Why did you even think of leaving?

</details>

**Peter**: 确实是这样。其实在 Colossus 项目告一段落之后，我有相当一段时间是在做其他项目，比如 Google Goggles（谷歌护目镜）。不知道你是否还记得那款产品？

<details>
<summary>Original English</summary>

**Peter**: Yeah, yeah. Well, after Colossus, I spent some time busy with other projects, like Google Goggles. Do you remember that?

</details>

**Gergely**: 是指后来的 Google Glass 智能眼镜项目吗？

<details>
<summary>Original English</summary>

**Gergely**: The glass hole project?

</details>

**Peter**: 对。智能眼镜这类形态的想法一直周期性地重回大众视野，直到今天依然有人在探索。Goggles 是 Google 早期尝试计算机视觉与穿戴结合的项目之一。

但在当时，客观硬件技术还没有真正成熟。不仅专用穿戴设备在技术储备上尚不具备条件，即使我们尝试将其移植并在 Android 智能手机上运行，那时的手机芯片算力也远远不够强大。

经历那段探索之后，我内心想要去外部闯一闯的冲动愈发强烈。在 Google 待久了，虽然这里汇聚了最顶尖的事物，但很多人心中其实都有一种相同的渴望：想要走出去，在一家全新的初创企业里检验一下自己的能力极限。

<details>
<summary>Original English</summary>

**Peter**: Yeah. These ideas always come back, and they're still around today. This was one of Google's early projects. And yeah, it was technology whose time hadn't quite come. I don't think it was ready for the moment. Apparently, actually creating the glasses was far more difficult. You know, on Android smartphones, we tried to launch this, but it just wasn't powerful enough. After that, you know, a desire to travel and explore rose up in me. You know, I was standing there at Google—it's the weirdest thing to say, but other people feel it too: you want to test your strength in another startup company.

</details>

**Gergely**: 那次创业最终似乎没有完全达到预期，后来被 Square 收购了对吧？我们稍微停下来聊聊这段经历，那家初创公司叫什么名字？

<details>
<summary>Original English</summary>

**Gergely**: That didn't work out. It was acquired by Square. So, yeah, for a moment I'd like to stop there. What was this company?

</details>

**Peter**: 我们创立的公司叫做 Viewfinder。

<details>
<summary>Original English</summary>

**Peter**: Well, what we founded was called Viewfinder.

</details>

**Gergely**: Viewfinder，好的。

<details>
<summary>Original English</summary>

**Gergely**: Viewfinder, yeah.

</details>

**Peter**: 是的，我们切入的赛道是移动端照片交换与共享。听起来是不是很熟悉？整体概念既有点像 Instagram，又有点像 Snapchat，那是在 2012 年前后。

<details>
<summary>Original English</summary>

**Peter**: Yeah, it was in the space of mobile photo sharing. Sounds familiar. It was like Instagram; it was kind of like Snapchat. In 2012.

</details>

**Gergely**: 正值 Instagram 全面崛起的时代。

<details>
<summary>Original English</summary>

**Gergely**: Yeah, just as Instagram was taking off.

</details>

**Peter**: 没错。但遗憾的是，我们当时始终没有摸索出门道——怎样找到真正契合的商业模式（Go-to-Market），如何高效获取并留存用户，以及怎样触发病毒式的爆发增长。

<details>
<summary>Original English</summary>

**Peter**: Yeah, yeah. No, we didn't figure out the right go-to-market, how to attract users, how to achieve viral growth, anything like that.

</details>

**Gergely**: 从局外人的角度来看，你作为联合创始人创立了这家公司，随后它被 Square 收购。虽然你肯定怀揣着更大的野心，这个结局可能算不上最初梦寐以求的巨大商业成功，但也绝不算失败。

<details>
<summary>Original English</summary>

**Gergely**: From the outside, reading up on it, I see that you're a co-founder of a startup that got acquired by Square. You probably had bigger ambitions, and while this wasn't a bad outcome, it wasn't the ultimate dream either.

</details>

**Peter**: 这里的关键在于“收购”的具体内涵。在创业领域，公司被收购有时是为了其核心知识产权、产品或既有商业模式；但很多时候，收购的唯一目的仅仅是为了吸纳这支技术团队——也就是所谓的人才收购（Acquihire）。

我们那次基本上就属于纯粹的人才收购。Square 确实买下了相关的知识产权，但我甚至怀疑他们后来是否真正投入使用过。毕竟那与 Square 自身的主营业务相距甚远。但 Viewfinder 拥有一支技术实力极其强悍的工程师团队，这才是 Square 决定收购的核心原因。

具体的财务数字我现在有些记不清了。当时我们融的资金量相对较少，收购后我们得以把投资款基本全额退还给投资人，大家对这个结果还算满意。投资人可能在微观上承受了一点折损，但绝大部分资金都安全收回了。创业者要明白，早期投资人都是阅历丰富的专业人士，他们早就习惯了投资亏损；但如果你让他们损失了大量本金，大家心里难免会沉重，而能够把绝大部分本金退还给他们，作为创始人心里终归会踏实许多。

<details>
<summary>Original English</summary>

**Peter**: So, the term I used was "purchased." Sometimes a company is acquired for their intellectual property, their product, their business, and sometimes they're bought just for the talent. The people. And for us, they really just bought us for the talent. They purchased the IP, but I doubt Square ever did anything with it. That wasn't what they were working on. But we had a very strong technical team, and that was exactly why we were acquihired.

And, well, I don't remember all the details. We raised a small amount of money. We were able to return the capital to our investors, so they were reasonably satisfied. Maybe there was a slight haircut on the funds, but they essentially got their money back. I mean, as a founder—investors are adults, they're used to losing money, but if you lose a ton of their money, it weighs on you. So returning their capital makes you feel a bit better.

</details>

---

### 分布式文件系统与分布式数据库的本质分野：从 Colossus 到 Spanner 与 Pebble

**Gergely**: 随后你在 Square 工作了一段时间，后来内心的探索欲是不是又开始萌生了？

<details>
<summary>Original English</summary>

**Gergely**: Yeah. Yeah. And you stayed for a while after the Square acquisition, and then you started to get that itch again?

</details>

**Peter**: 哈哈，是的。这就回到了我们一直在深耕的领域：分布式文件系统与底层分布式数据存储架构，也就是 Colossus 那一派的体系。

在 Colossus 体系之上孵化并蓬勃发展的核心项目之一，正是 Spanner。

<details>
<summary>Original English</summary>

**Peter**: Yeah, yeah. Because, you know, we work on these distributed file systems and distributed data storage systems, like Colossus. And one of the flagship projects built on top of Colossus is Spanner.

</details>

**Gergely**: 那么，Spanner 与 Colossus 之间的根本区别究竟在哪里？

<details>
<summary>Original English</summary>

**Gergely**: And how is Spanner different from Colossus?

</details>

**Peter**: 本质上讲，Spanner 是一个分布式数据库，而 Colossus 是一个底层分布式文件存储系统。

初看起来，两者之间的边界容易让人困惑：“既然它们都是用来存数据的，到底有何不同？”

<details>
<summary>Original English</summary>

**Peter**: Well, Spanner is fundamentally a distributed database. Colossus is a distributed storage system. And considering the difference between a distributed storage system and a distributed database, someone might think, "Oh, they both store data."

</details>

**Gergely**: 我正想问这个问题。因为任何分布式数据库，最终的落脚点不都得落在一个分布式存储系统之上吗？

<details>
<summary>Original English</summary>

**Gergely**: I was just about to ask that. Because any distributed database eventually has to rely on a data storage system.

</details>

**Peter**: 没错，但它们的工程关注点与设计哲学截然不同。

对 Colossus 而言，它聚焦的是海量的大文件，并且这些大文件仅支持追加（Append-Only）写入。

<details>
<summary>Original English</summary>

**Peter**: Yeah, yeah. For Colossus, you see, it's focused on huge files, and those huge files are append-only.

</details>

**Gergely**: 也就是说，不能直接在文件中就地进行随机修改（In-place Update）？

<details>
<summary>Original English</summary>

**Peter**: 不能随机覆写，只能在文件末尾追加。

Colossus 针对的是巨大的文件块，单文件尺寸通常在 64MB 以上，甚至可以达到数 GB。

但数据库面对的完全是另一类场景。比如对于关系型数据，一张表内可能包含数十亿行记录，每行被划分为不同的列，有具体的类型与索引。数据库工程的核心难点与底层分布式文件系统存在质的鸿沟。

常规的分布式数据库往往搭建在底层的分布式文件系统之上，两者是分层支撑的关系——Spanner 正是构建在 Colossus 的基础之上的。

正因如此，Spanner 中的许多核心设计决策，直接受制于 Colossus 仅支持追加写这一现实：你无法在底层文件中执行原地更新，这就倒逼上层数据库必须依靠不可变文件（Immutable Files）来管理数据状态。

而这正是日志结构合并树（LSM-Tree，Log-Structured Merge-tree）大显身手的领域。LSM-Tree 并不是 Google 发明的，但 Google 确实通过 LevelDB 以及后来的 Spanner，将其真正推向了工程主流应用。后来 RocksDB 更是将这一架构发扬光大。

再后来，我自己也重新独立实现过一套 LSM-Tree 存储引擎，这也正是我们在 CockroachDB（红眼蟑螂实验室）内部所使用的组件，它的名字叫做 Pebble。它的全部底层核心机制，都建立在“将数据保存在一系列只读的不可变文件中”这一原则之上。

<details>
<summary>Original English</summary>

**Peter**: You cannot update in place? You can only append, yeah. Yeah. Huge files that are append-only—meaning they are 64 megabytes, maybe up to gigabytes in size. But if you look at a database—for example, relational data—you could have a table with billions of rows. Those rows are divided into columns and representations. This is a completely different engineering challenge in nature: database systems versus distributed storage systems.

Usually, a distributed database is implemented on top of distributed storage systems. That was the connection: Spanner on top of Colossus. Some of the design decisions in Spanner arose directly from the fact that Colossus files are append-only. You cannot update them in place, so you have to work with immutable files in the database. And that's where Log-Structured Merge-trees (LSM-trees) come in.

Google didn't invent LSM-trees, but Google really popularized them through LevelDB, and by extension, Spanner. Later, they became extremely popular with RocksDB. Later on, I re-implemented one of these engines myself, which is what we use at Cockroach Labs today; it's called Pebble. It's the internal storage engine. But everything rests on that principle: data is stored in immutable files.

</details>

---

### 诞生 CockroachDB：告别 Square 与重聚创业

**Gergely**: 那么，你们后来究竟是如何下定决心创办 Cockroach Labs（红眼蟑螂实验室）的？

<details>
<summary>Original English</summary>

**Peter**: 当时我们还在 Square 工作。我和我的几位联合创始人……

<details>
<summary>Original English</summary>

**Gergely**: So how did you decide to start Cockroach Labs?

**Peter**: When we were working at Square, my co-founders and I...

</details>

<!-- chunk 6/8 -->

### CockroachDB 的雏形与创立缘起

**Spencer Kimball**: 最初我们总是三个人。我们当时都在 Square，其中一个是 Spencer——正如我之前提到的，他曾经参与过 GIMP，也是我大学宿舍的室友；还有 Peter Mattis；另外还有 Darnell，他也曾在 Google 工作过，后来跟我们一起去了 Square。那时我们就在业余项目中尝试摸索，完全基于实际的使用需求来评估技术。当时现有的开源方案我们其实都不太满意。Google 内部的 Bigtable、Spanner 等系统看起来非常出色，但离开 Google 之后，我们对外界现有的系统并不满意。在某个时刻，我们其实已经构思出了 CockroachDB 的最初设计草案。但当时我想：不行，伙计们，我们现在正在做的是一个移动应用（Viewfinder），我们不应该分心去开发一个全新的分布式数据库。所以我们把那个计划暂时搁置了。不过在我看来，这反倒成了一件好事，我们当时专注于做照片应用，一切推进得都很顺利。后来当我们去到 Square 时，看到那些业务场景和痛点，越发坚定了这种需求。管理层甚至对我们说：“嘿，你们可以每周花一天时间来做这个，看看这个设计方案是否可行。”之后这个想法终于引起了广泛的关注，大家都在问：“嘿，我们要不要以此成立一家公司？”事情就是这样，时机终于成熟了。

<details>
<summary>Original English</summary>

**Spencer Kimball**: It was always the three of us. We were all at Square, and one of them, Spencer, as I mentioned, GIMP, he was my roommate in college dorms. Darnell also, he had worked at Google and ended up at Square with us. We were, you know, just playing around with side projects based on actual use cases. We didn't really like the available options. Having seen Bigtable and Spanner, I wasn't completely satisfied with other systems out there. At a certain point, we came up with what became the initial design of CockroachDB. And I thought: no, no, guys, we're building a mobile app, we shouldn't be building a distributed database right now. So we postponed that plan for another time. Which, in my opinion, was definitely the right call; focusing on photos worked out well all things considered. Then we got to Square and saw some of those use cases, and they were so compelling. Management even said, "Hey, why don't you work on this part-time, one day a week, and see if there's a viable design?" Eventually, it started getting so much traction that people asked, "Hey, should we start a company around this?" And that's exactly what happened. The time had finally come.

</details>

**Host**: 也就是说，你们最终成立了公司。据我了解，在 Viewfinder 时期你们就接触过风险投资，是吗？

<details>
<summary>Original English</summary>

**Host**: So you founded the company. But from what I understand, did you raise venture capital funding back then, right?

</details>

**Spencer Kimball**: 在 Viewfinder 的时候确实是这样。我们拿了风险投资的钱。现在回过头来看，我非常推荐创业者接受风险投资。风投机构中有很多非常聪明的人，他们能提供巨大的帮助，协助你克服很多创业路上的挑战。我知道外界有时对风投有偏见，认为他们在各个领域过度施压，或许某些情况下确实存在这种情况。但在我的经历中，我遇到的一些风险投资人非常优秀。他们就像团队的一员，会告诉你他们在市场上看到了什么，尤其是对于技术型创始人来说，他们能帮你理清方向，让你清楚当前应该把精力聚焦在哪里。

<details>
<summary>Original English</summary>

**Spencer Kimball**: That was the case with Viewfinder. We took venture capital money. And looking back, I definitely recommend it. Accepting venture capital funding brings people who are very, very smart and can help you overcome a lot of challenges. You know, I think sometimes there's a negative perception that venture capitalists push you too hard in different directions, and maybe in some cases that happens. But the venture capitalists I've worked with and met were incredible. You're part of a team, and they share what they are seeing across the market with technical founders, helping you figure out what to focus on right now.

</details>

**Host**: 是的。后来对于 Cockroach Labs，你们是不是很快就融到了资金？

<details>
<summary>Original English</summary>

**Host**: Right. And for Cockroach Labs, did you raise funding right away?

</details>

**Spencer Kimball**: 是的，事实上我们很快就为 Cockroach Labs 筹集到了资金。当时我们在旧金山湾区，反响非常热烈，投资人立刻就理解了这个方向的价值。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yes, we actually raised money right away for Cockroach Labs. We were in the San Francisco Bay Area, and there was immediate interest and understanding.

</details>

### 项目命名的由来与生存韧性

**Host**: 不过我必须问你一个关于名字的问题。“Cockroach”（蟑螂）？为什么叫这个名字？

<details>
<summary>Original English</summary>

**Host**: But there is one thing I have to ask you: about the name. "Cockroach"? Why that name?

</details>

**Spencer Kimball**: 哈哈，是的。这有点像当年 Spencer 命名 GIMP 一样，当时他在想：“我该给这个处理图像的新程序起什么名字呢？”后来那个名字就根深蒂固了。在构思这个新数据库的某个时刻，起名字一直是个难题。当时我们说：“我们正在做一个分布式数据库，需要一个能体现其特性的名字。”然后有人提议叫“Cockroach”（蟑螂）。因为蟑螂是杀不死的（impossible to kill），具备极强的生命力。分布式系统需要具备这种打不死、永远在线的韧性。所以大家觉得：“这个名字很贴切，就用它吧！”

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yeah, exactly. It's kind of like GIMP back then—Spencer was wondering, "What should I call this new image manipulation program?" And then it just took root. At a certain point when designing this new database, finding a name was tough. We were like, "We're working on this distributed database, we need something." And the suggestion came: "Cockroach." Cockroaches are impossible to kill; they are unkillable, you know. And it just worked.

</details>

**Host**: 确实如此。那么如今 CockroachDB 发展到了哪个阶段？它的核心特性是什么？

<details>
<summary>Original English</summary>

**Host**: That's great. And where are we today with CockroachDB? What is the main focus?

</details>

**Spencer Kimball**: 这正是我们一直着重证明的一点。除了在恶劣故障条件下保持高性能之外，你可以对它施加极高的工作负载，即便随机杀死节点，甚至杀死整个可用区或数据中心，整个系统依然能够不受中断地持续运行。这就是我们的核心卖点与愿景。在实际客户中我们也反复验证了这一点：有客户的数据中心发生火灾，其他所有传统数据处理系统全部瘫痪中断，而 CockroachDB 依然在正常提供服务。每当听到这样的消息，我都觉得：“这太棒了。”

<details>
<summary>Original English</summary>

**Spencer Kimball**: This is what I always pay attention to and what we set out to prove. Beyond increasing productivity under adverse conditions, you can run heavy workloads against it, kill nodes, kill an entire datacenter region, and the system continues to work. That has been our core marketing point and vision. But we've also seen this with real customers: they had a fire in a datacenter, and while other data processing systems failed, CockroachDB kept running without missing a beat. When that happens, I just think: "That's amazing."

</details>

### 从手动分片到自动化分布式架构

**Host**: 当你们刚起步时，使用 CockroachDB 的都是些什么样的公司？初创企业会用吗？从那时到现在，用户群体发生了怎样的变化？因为如果是小型创业公司，数据量不大，他们可能直接用单机开源数据库就行了，为什么需要分布式架构？

<details>
<summary>Original English</summary>

**Host**: When you started, what kinds of companies were using CockroachDB? Were startups using it? How has that evolved since then? Because for a small startup, they might just say, "I have simple data, why do I need this until I outgrow it?"

</details>

**Spencer Kimball**: 是的，很多公司往往是在遭遇了灾难性故障之后才找到我们，就好像我们是处理故障的急救车一样。在恶劣的天气条件或极端区域性网络断联面前，很多部署在单可用区或普通云数据库（比如单一 Aurora 实例）上的服务无法抵御这些灾难。通常在业务增长后，开发者不得不面对数据拆分的问题。正如大家所知，很多团队往往被迫手动将数据切分成 10 个、20 个甚至 100 个分片（shards）。过去在 Google 内部有很长一段时间也是如此，而这给应用层开发者带来了极其沉重的包袱。在这个阶段，应用开发者被迫去扮演数据库开发者的角色，试图自己在业务层实现分布式事务、全局二级索引等机制，这往往非常痛苦且容易出错。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yeah, companies often call us after a disaster, almost like calling an ambulance. Under severe weather conditions or broad regional outages, typical setups like standard Aurora instances can't survive. And normally, what people end up having to do as they scale is sharding their data into 10, 20, or 100 shards. Google went through a period of this too, and it placed an immense burden on application developers. At that stage, application developers are forced to act like database developers, trying to implement distributed transactions, cross-shard indexing, and so on. It gets messy fast.

</details>

**Host**: 我们能深入聊聊自动分片（Auto-sharding）与手动分片吗？我想大部分工程师都知道分片的大致概念，但我们不妨先从手动分片讲起，它是如何实现的？像 CockroachDB 这样的数据库又是如何彻底免除手动分片负担的？

<details>
<summary>Original English</summary>

**Host**: Can we talk about automatic sharding versus manual sharding? I think most people know generally what sharding is, but let's start with manual sharding: how does it work, and how does a database like CockroachDB remove that burden?

</details>

**Spencer Kimball**: 最简单的分片方式有点类似于哈希表。假设你划分了 100 个分片，数据模型里有很多用户记录，如果使用哈希函数对用户 ID 进行取模，理论上可以得到相对均匀的分布。但核心难题在于数据的再平衡（rebalancing）和再分配。当某个分片过载，或者需要新增节点时，你必须把部分用户迁移到新节点上，这意味着你需要重构整个映射关系，甚至可能要重新分配所有数据。为了解决这个问题，业界引入了一致性哈希（Consistent Hashing）等技术。一致性哈希在添加新节点时，只需要迁移一小部分数据。像 Cassandra 这类系统很大程度上就是基于一致性哈希来工作的。

而在 CockroachDB、Bigtable、Spanner 以及 HBase 这类系统中，设计哲学则有所不同。在这些系统中，整个键空间可以被想象成一条连续有序的巨大空间，系统将其按范围切分成很多相邻的连续区间（Ranges）。然后，系统在这些区间之上构建一个稀疏索引，结构在本质上非常类似于一棵 B 树（B-tree）。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yes. The simplest approach is somewhat like a hash table. For example, say you have 100 shards. Your data model has many users; if you apply a hash function to the user identifiers, you get a reasonably even distribution. The problem is rebalancing and redistribution. When you need to move data or add capacity, how do you handle moving subsets of users? Do you have to rehash everything? That's why consistent hashing was developed. With consistent hashing, when you add a node, only a fraction of the data needs to migrate. Systems like Cassandra rely on that model.

CockroachDB works more like Bigtable, Spanner, or HBase. Rather than purely hashing keys across arbitrary buckets, you can visualize the entire keyspace as one giant contiguous ordered space that is partitioned into contiguous range slices. Then you build an index over those adjacent ranges, which in practice is conceptually very similar to a B-tree.

</details>

### B 树索引的统一抽象与分布式演进

**Spencer Kimball**: 在这套架构的最顶层存在着这样一个范围索引，它能够告诉你：特定的键范围位于哪个节点上。如果退一步、眯起眼睛抽象地看，这其实就是一棵宏观层面的 B 树。无论是哈希表还是 B 树索引，在宏观抽象上殊途同归。随着思考的深入，我意识到很多经典的计算机论文早就在单机数据库中确立了以 B 树为核心的数据结构。过去我们可能不会直接把分布式架构归结为 B 树，但在分布式数据库的设计中，底层逻辑依然反复体现着 B 树的思想——虽然没有人天天把“这就是一棵分布式 B 树”挂在嘴边，但本质上它就是。而在单机引擎内部，数据和二级索引也是通过 B 树组织的，比如对用户邮箱进行范围扫描、排序等操作，底层引擎依然依赖 B 树或其变体。这些概念早在 1980 年代就被提出并写入经典文献，历经几十年，它们依然是单机数据库乃至现代分布式数据系统的坚固基石。

<details>
<summary>Original English</summary>

**Spencer Kimball**: So at the top level, you have this index that maps which node holds a given range. If you squint at it, it really is like a giant B-tree. Whether it's a B-tree or an indexed hierarchy, this structure governs routing. It started making total sense when I recalled early papers on data structures frequently used in databases. Over and over again, in single-node databases and distributed databases alike, that pattern emerges organically. Nobody explicitly says "this distributed architecture is just a B-tree," but if you look closely, that's what it is. And within single nodes, your secondary indexes—like scanning email addresses in sorted order—are powered by B-trees under the hood. Hash and B-tree indexes are everywhere. Those papers written back in the 80s laid down principles that still serve as the foundation of single-node engines and every distributed system I've worked on.

</details>

### 强一致性与 ACID 事务保障

**Host**: 我想深入请教一下关于强一致性（Strong Consistency）的问题。CockroachDB 主打强一致性。在现代分布式系统中，存在着各种一致性模型。为什么强一致性如此重要？为什么在分布式环境下实现它如此具有挑战性？

<details>
<summary>Original English</summary>

**Host**: I'd like to ask about strong consistency. CockroachDB provides strong consistency. In distributed systems, there are various consistency models. Why is strong consistency so crucial, and why is it so difficult to implement?

</details>

**Spencer Kimball**: 如果你使用过数据库，肯定听说过事务（Transaction）。事务是一种将多次数据修改合并为一个原子操作的方法，也就是大家熟知的 ACID 特性：原子性（Atomicity）、一致性（Consistency）、隔离性（Isolation）和持久性（Durability）。持久性很容易理解，即数据写入数据库后，即使系统崩溃重启，修改也不会丢失；原子性保证所有操作要么全部成功生效，要么全部回滚。而隔离性则负责处理并发事务之间的相互影响。现实中我们不可能让所有事务排队一个个串行执行，我们必须支持高并发。但并发执行时，系统必须表现得如同这些事务是按某种线性顺序先后发生的一样，这就是所谓的线性一致性与隔离级别保障。这样做的最大好处是让上层应用开发者不必在业务代码中去处理复杂的竞态条件。如果隔离级别过低，可能会发生这样的情况：一个操作读取账户说“账户里有 100 美元，准备转账”，另一个并发操作同时读取也是 100 美元，结果导致这 100 美元被扣减了两次，这在金融场景下是绝对无法容忍的。

<details>
<summary>Original English</summary>

**Spencer Kimball**: If you've used a database, you've likely heard of transactions. A transaction is an atomic way to perform multiple mutations. The classic ACID properties stand for Atomicity, Consistency, Isolation, and Durability. Durability is straightforward: once written, if a crash occurs, the changes are retained. Atomicity ensures all operations either commit completely or abort cleanly. Isolation deals with concurrent transactions. We can't just run one transaction at a time serially; we want to launch many transactions in parallel. But under concurrency, the system must guarantee that operations behave as if they occurred in a strict linear order. The primary advantage of this is that application developers don't have to worry about race conditions in their business logic. With weak isolation levels, a transaction could read an account balance of $100 and initiate a transfer, while another concurrent operation reads the same $100 and also transfers it, subtracting that $100 twice. And that would be catastrophic.

</details>

<!-- chunk 7/8 -->

### 一致性模型与系统吞吐的权衡

**Spencer Kimball**: 在某些业务场景下，系统必须极其精确地追踪数据状态，比如你的银行账户余额、信用评分，或者是购物车中的加购与结算结账。在这些核心场景中，可选的架构方案并不是无限宽泛的。如果一旦做出了错误的选择，系统就会暴露非常明显且严重的错误。不过，现在让我们回到一致性模型的话题。在强一致性、线性一致性（Linearizability）之下，还有许多可供考量的一致性级别；但最终一致性（Eventual Consistency）与强一致性有着本质不同。对于最终一致性而言，你可能会执行某项操作，例如执行一次数据更新或续期（renewal），但系统更新在某些时刻并不立即可见。等到某个特定时间点之后它们才会重新同步回来。如果在这一过程中你去查询信用卡余额，查出来的状态可能就是错误的。

<details>
<summary>Original English</summary>

**Spencer Kimball**: You know, we have to precisely track things like your bank score or, you know, adding purchases to a cart. In those cases, the choices and options you can use there aren't infinite. And if you make a mistake, you're going to have very obvious errors. But now, getting back to consistency—below linearizability, or other conceivable levels, there is strong consistency versus, you know, eventual consistency. With eventual consistency, sometimes you perform an operation, like a renewal, but it won't reflect immediately. They will come back eventually, you know, at some point later. But in the meantime, if you check your credit card balance, is it wrong?

</details>

**主持人**: 是的，没错。但采用最终一致性往往是为了追求更高的速度。你可以从系统中压榨出更多的生产力和吞吐量。

<details>
<summary>Original English</summary>

**Host**: Yes, yes. Yes, and this is done to do things faster. You can get more productivity and throughput out of the system.

</details>

**Spencer Kimball**: 但归根结底，这也取决于程序的设计。在分布式数据库中，情况绝非如此简单。不能一概而论地说“这就是最终一致性，事情到此为止”。因为追求吞吐往往会带来额外的系统负载，你必须对此保持警惕。在强一致性系统中，一旦写入完成，数据就被确切地持久化记录下来了。如果数据刚刚写入，那么读取它时得到正确结果完全是合乎逻辑的。为了实现这一点，系统无论如何都需要副本（replicas），对吧？

<details>
<summary>Original English</summary>

**Spencer Kimball**: But once again, this depends on how the program is designed. In a distributed database, it's not simply a matter of saying "no, this is just eventual consistency, and that's the end of it." That approach can create much more load on the system, so you really have to be careful with this. In strong consistency, when you get a write done, it's recorded—there is no problem, this was recorded. If you just recorded it, it's only logical that you should be able to read it back. And to achieve that, somehow you need replicas, right?

</details>

**主持人**: 是的。那你们在 CockroachDB 内部具体是怎么做的呢？

<details>
<summary>Original English</summary>

**Host**: Yes. What are you doing inside CockroachDB?

</details>

**Spencer Kimball**: 我们会将数据记录并同步到所有的副本上，所以……

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yeah, we record everything across replicas, so...

</details>

**主持人**: 啊，明白了。所以你们追求的是极其迅速地完成这一过程，并且以非常高效的方式执行。

<details>
<summary>Original English</summary>

**Host**: Oh, I see. Yes, yes. So you just do it quickly. You've been making it fast and doing it effectively.

</details>

**Spencer Kimball**: 我认为这正是软件行业令人兴奋的地方。我们总能不断发现应对日益复杂需求的方法。在构建程序和软件工程时，我们能够让它们变得极其高产且高效。多年来，整个软件行业都在朝着这个方向演进。在我所熟悉的数据库领域是这样，在其他领域也随处可见这种进步。比如图形学处理也是如此，过去人们逐个像素地去处理画面，而现在的图形处理器（GPU）能在一瞬间处理数十亿个多边形三角形。在当代硬件与算法出现之前，那样的吞吐量是不可想象的。

<details>
<summary>Original English</summary>

**Spencer Kimball**: I think this is what makes software so exciting in our industry. We are constantly discovering ways to handle things that become increasingly complex, allowing us to build programs and deliver software with immense productivity. And as you know, this has evolved over many years. This is true in the database industry that I know well, and it happens everywhere else too. Look at graphics: early on, you were literally manipulating individual pixels. And now graphics processors can process billions of triangles in a split second. None of that was possible with previous figures before you saw today's architectures.

</details>

### Raft 共识协议与副本容灾机制

**主持人**: 另一个问题是关于 Raft 共识算法的。起初众所周知 Paxos 非常难以实现，而 Raft 作为 Paxos 的一种变体被提出。在我看来，现在大家在构建分布式系统时几乎都在普遍采用它。你是否认同 Raft 已经成为一种标准的共识机制？

<details>
<summary>Original English</summary>

**Host**: Another question is about Raft consensus. What happened there was that the original Paxos was known to be notoriously difficult to implement, and Raft came along as a Paxos variant. In my view, today practically everyone uses it. Would you agree that it has become the standard consensus protocol?

</details>

**Spencer Kimball**: 是的，确实如此。共识协议的核心目的，就是为了让集群对某次写入操作已经成功记录达成一致。关于共识机制，假设你想对数据进行副本次级复制，你在生产中绝对不能只配置两个副本。为什么不能只有两个副本？原因在于，如果主节点发生故障，你根本无法判定到底发生了什么，也无法在两个节点间形成多数派仲裁。所以你通常必须保证至少拥有 3 个副本，分布在 3 个不同的位置。在通常情况下执行读操作时，只需要从其中部分节点读取即可。但一旦发生故障节点崩溃，系统需要执行恢复操作时，只要从任意两个副本中读取，就能根据多数派共识获知之前发生过什么确切的写入历史。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yes, yes. So you reach consensus that the recording actually took place. That is what consensus is about. If you want to replicate secondary copies, you really cannot have just two replicas. And the reason why you can't is: what happens if the main node fails? How do you figure out what happened? You can't, right? So you always have three or more replicas across three locations. Normally, when performing reads, you read from some of them. But if a failure occurs and I need to execute recovery, then I can read from two out of the three replicas, and because of consensus, I know what happened previously.

</details>

**Spencer Kimball**: 通常在故障恢复阶段，系统正是通过这种基于共识的仲裁读取来完成状态确认的。在常规状态下，读请求通常只会在单个副本上发生；只有在面临节点宕机或故障切换时，基于共识的读机制才会介入以保障无缝衔接。

<details>
<summary>Original English</summary>

**Spencer Kimball**: And normally, recovery performs this consensus-based quorum read. So under normal circumstances, reading only happens on one replica, but during failure modes and outages, this consensus-based reading is what guarantees correctness.

</details>

**主持人**: 那么在 CockroachDB 中，你们通常为共识组配置多少条副本线路或节点数？

<details>
<summary>Original English</summary>

**Host**: Inside CockroachDB, how many lines or nodes do you select for consensus?

</details>

**Spencer Kimball**: 通常是 3 个副本。对于某些关键的系统级元数据表，可能会配置为 5 副本甚至 7 副本。如果你对容灾特别敏感或者极其担忧故障，你完全可以选择 5 副本。但配置的副本越多，系统速度就越慢，占用的存储空间也成倍增加。我们这里讨论的是节点通信延迟对系统整体速度的拉低。特别是如果机房遭遇地震等灾难，或者跨地域分布时存在网络延迟。这在物理上受限于光速，光在光纤中传播的速度是有限的，对吧？当副本跨越几百公里甚至全球多地部署时，网络延迟会成倍放大。因此，用户在根据自身业务场景设计多副本与网络请求拓扑时，必须格外审慎。分布式数据库的一个普遍真理就是：数据在节点间来回传输是需要成本的。你是否希望系统在极高的网络往返开销下运行？这完全取决于你的架构权衡。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Usually it's three. For certain system tables, you might record across five or seven replicas. Five is there if you're really concerned about resilience; you can use five. However, the more replicas you have, the more it slows down the nodes, and the more storage space it consumes. We're talking about nodes slowing down due to communication latency. And of course, if you're guarding against earthquakes or dealing with delays across regions, it comes down to physics—the speed of light, right? Light travels at a finite speed, and when data traverses hundreds of miles or spans across the globe, latencies increase. So you have to be very careful with how you design your requests. One of the universal truths in distributed databases is that data has to travel back and forth. Do you really want to pay that penalty in a single round-trip? It depends on your needs.

</details>

### 关键业务系统与数据基础设施的责任

**主持人**: 那么在当今的工业界，我们是否能够界定哪些属于真正关键的任务型应用程序？毕竟数据库是企业赖以生存的业务命脉。你能否为我们深入剖析一下，怎样的系统才称得上是真正“生死攸关”的？或者说，我开发一个普通的 SaaS 平台，甚至只是展示广告的系统，它算得上是关键任务系统吗？可能不算吧？

<details>
<summary>Original English</summary>

**Host**: Where are we today with this? I mean, using critical applications—databases are our daily bread. Could you tell us what actually qualifies as mission-critical? Or is my SaaS product, or an ad platform, considered critically important? Probably not, right?

</details>

**Spencer Kimball**: 确实存在差别。我认为深刻理解这一区别非常关键，这几乎是现代商业企业最底层的基石逻辑。对于核心商业系统而言，系统绝不能发生灾难性宕机。如果一个金融交易系统挂掉了，那直接关乎企业的生死存亡。你可能会觉得，有些人在手机外卖 App 上订购一份墨西哥卷饼（burrito），这种配送履约系统能算得上什么至关重要的系统吗？但如果你这么想就错了。如果该系统发生问题，购物车交易中断，对平台而言每一分钟都意味着以美元计价的真金白银在流失。商业基础设施必须像自来水管道一样稳定运行，如果水龙头断了水，整个公共市政服务就相当于瘫痪了。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yes, exactly. It can be tricky to define what is truly mission-critical. Is an ad service critical? Probably not. But I think understanding this distinction is fundamental—it's like zero-level operational secret for running a company. Look at commercial systems, for instance. You know a system cannot just fail and go down. If a transactional system fails, that company is dead. Some people might look at ordering and delivering a burrito and ask whether that is really a critical, important system. Is it wrong to care? Well, if there's a problem, you have a shopping basket converting to dollars every hour. It has to work continuously like running tap water. And if it stops, that public utility service simply vanishes, right?

</details>

**主持人**: 是的，完全没错。所有人都在环环相扣的链条上，人们完全依赖于这些基础设施。

<details>
<summary>Original English</summary>

**Host**: Yes, absolutely. Everyone depends on it in sequence. People rely on it, as you know.

</details>

**Spencer Kimball**: 搜索引擎是绝对不能崩溃的，你明白吗？如果搜索系统中断了，你不仅会眼睁睁看着收入断崖式暴跌，更致命的是，公司的商业声誉会遭受急剧崩塌。这种负面影响会极为深远，会在漫长的时间里演变成一场灾难。最终，相关负责人甚至会被直接开除出局。因此，系统必须以极高的敬畏心来维护这些不可妥协的核心价值。只要系统一宕机，追责邮件立刻就会接踵而至。当你坐在那里，想到自己写的一行代码可能会让整个线上系统崩溃瘫痪，那种心理压力是难以言喻的。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Search cannot break, you understand? If that system goes down, not only do you notice a sudden, steep drop in revenue, but you also suffer a sharp decline in reputation. It leads to terrible, long-lasting consequences. People get evicted over this. You have to behave responsibly toward these critical values. Immediately afterwards, the emails start flooding in: "You're responsible here." Just thinking that a line of code I wrote might break the entire system—you know what that feels like? And I just knew: what is that? I wasn't just writing extra lines of communication; it carries immense weight.

</details>

**主持人**: 是的，完全理解。当用户喜爱并信赖某个产品时，平台必须全力保障系统的稳定运行，并持续对其进行研发投入。而对用户而言，他们期望获得的是免于忧虑的自由，用户根本不希望被迫去关心底层可能发生的问题，他们只期望系统无论如何都能顺畅运行。

<details>
<summary>Original English</summary>

**Host**: Yes, exactly. That's when people truly love a product. Users expect you to support it and invest in it. But the ultimate freedom for users is not having to worry about what I hate worrying about. It just has to work seamlessly anyway.

</details>

### 从高产代码编写到技术管理转型

**主持人**: 那么你们现在有多少工程师？团队规模大概是怎样的？

<details>
<summary>Original English</summary>

**Host**: And how many engineers do you have?

</details>

**Spencer Kimball**: 我们大约有 100 名左右的工程师。具体的研发与工程团队精确人数我没有精确掌握，但大体在这个量级。我们花费了大量的心血和时间来构建底层的分布式数据系统。

<details>
<summary>Original English</summary>

**Spencer Kimball**: We have around 100 engineers. I don't know the exact count between research and engineering, but, you know, we spent an immense amount of time building the database.

</details>

**主持人**: 这可不是几个人能在短期内做成的事，这项工程持续了好多年，历经多次迭代吧？

<details>
<summary>Original English</summary>

**Host**: This is not something a few people do overnight. It took several years, through multiple iterations, right?

</details>

**Spencer Kimball**: 是的，确实经历了很多年与多次架构演进。数据库工程正是如此，为了达到工业级的稳定性，必须经历漫长的时间磨砺。只有具备了坚实的稳定性并修复所有的历史缺陷，团队才能在此基础上持续推陈出新，不断提升系统生产力，最终赢得未来的成功。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Oh yeah, we definitely did. Building a database requires a certain high level of stability. You need that stability: fixing all the errors, and then continuing to innovate and boost productivity for future success.

</details>

**主持人**: 我还特别想问问你个人在编程方面的经历。作为联合创始人，在公司创立最初的几年里，你写了多少代码？

<details>
<summary>Original English</summary>

**Host**: And I wanted to ask you about your own programming. As a co-founder, during the initial period of those first few years, how much code did you write?

</details>

**Spencer Kimball**: 那段时期我写了海量的代码，当时我绝对称得上是一名极其高产的程序员（a prolific coder）。在公司刚刚起步的最初阶段，核心开发人员就只有 Ben Spencer 和我两个人。那是一段极度专注且非凡的特殊时期。

<details>
<summary>Original English</summary>

**Spencer Kimball**: I wrote a tremendous amount of code back then. I was a truly prolific coder. At the very beginning, it was just Ben Spencer and me. And that period was truly exceptional. But, you know, I wrote so much.

</details>

**主持人**: 是的，那段初创期可以说是技术孵化与产出最为密集的黄金时期。

<details>
<summary>Original English</summary>

**Host**: Yes, exactly. That was essentially the most fertile incubation period.

</details>

**Spencer Kimball**: 就在那个阶段，正如大家所知，我们底层使用了基于 LSM 树架构的 RocksDB。但在特定领域遇到了一些性能与架构限制后，我几乎是将那部分存储引擎层进行了彻底重写。在那次重构攻坚战中，我个人大概写了四万到五万行代码。在那之后，另一批工程师团队陆续加入进来协助开发。大家看到这个成果时都惊叹不已，说代码量太惊人了。甚至有人调侃说：“你写了十万行代码吧！”而行业的平均基准指标显示，一个软件工程师平均一年大概产出 3.6 万行代码。所以从代码产出量来看，这确实是相当惊人的体量，我们在极短时间内完成了巨大的工作量。

<details>
<summary>Original English</summary>

**Spencer Kimball**: This was when, as you know, we were using RocksDB, which is an LSM-tree storage engine. In certain areas there were limitations, so I ended up rewriting parts of it. That was a huge push where I wrote probably around 40,000 to 50,000 lines of code. Later on, another group came in to help, and people looking at the output were like: "Wow, that's an enormous volume of code!" People would just dial up numbers like, "You know, 100,000 lines of code!" When industry average metrics suggest something like 36,000 lines a year, that was clearly a massive amount of output. We got an incredible amount done.

</details>

**主持人**: 听到这里，很多人估计都会一边赞叹一边难以置信地摇头。这远远超越了业内常态。你们从公司创立伊始就拥有了最出色的技术带头人。但随着公司壮大，你从早期联合创始人兼 CTO 逐渐转向了更高层面的管理角色，是吗？你能跟我们讲讲这段心路历程吗？这意味着你必须去管理团队，在更高维度的公司战略层面思考。

<details>
<summary>Original English</summary>

**Host**: Hearing that, anyone in the industry would shake their head in amazement. That is far better than normal industry output. You had top-tier leadership right from the beginning. But as co-founder and CTO, and eventually moving up to higher leadership, could you tell us about that transition? You had to manage your teams and operate at a higher level, right?

</details>

**Spencer Kimball**: 当时有人劝我放下键盘专注于管理，我当时接受并听取了这个建议。回过头来看，我认为在当时那个阶段，转向管理确实是正确的建议。但从个人编程生产力的角度而言，我离开一线编程后，个人的直接技术产出自然就下降了。我当时非常忙碌，主营业务和日常管理工作占据了全部精力。我曾以为自己这辈子可能再也不会真正动手写程序了，毕竟管理工作本身就像是处于持续的高压电环境中。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Yes, exactly. I was told I needed to step back and manage the team at a higher level. I agreed at that moment, and in retrospect, I think it was the correct advice for the company. But my personal programming productivity decreased dramatically. I was extremely busy with the primary business responsibilities. I honestly thought that was it for me and coding—it was all high-voltage executive management.

</details>

### 人工智能编码革命与重返代码一线

**主持人**: 你是否有这种感觉：公司投入了大量的资金与精力去推动各项业务，而你却不得不远离了自己最热爱的代码？直到后来人工智能（AI）开始崭露头角，你才重新回到了编程领域。你从什么时候开始认真考虑把人工智能引入到日常编码当中的？毕竟早期的 AI 编程工具，比如最初在 GitHub 社区引起热议的初版 Copilot，大家第一次接触它时，感觉它更像是一个升级版的智能自动补全（Autofill），只是单纯地帮你把剩下的半句函数或代码块填满而已。

<details>
<summary>Original English</summary>

**Host**: Did you feel that? You spend all this money and effort running everything, and then you stepped away. But then artificial intelligence started to emerge, and you came back to coding. When did you start seriously considering using AI for programming? Because early versions, like the famous early GitHub Copilot that everyone talked about, felt very basic when encountered for the first time. It looked just like glorified autofill, merely filling out the remainder of a snippet. When you watched it, didn't you wonder if it was slightly crazy?

</details>

**Spencer Kimball**: 确实如此。最初我们只是偶尔尝试一下，或者看着别人使用。当时业界甚至还在争论，觉得有必要专门去教育用户和工程师如何使用所谓“提示词工程”（prompt engineering）。如果你不是专业工程师，你就必须去专门学习该如何跟 AI 对话。但随着技术演进，事情变得非常清晰：AI 的能力必将迎来爆发。起初人们看到它时可能会想：“好吧，这东西看起来不错，但还谈不上彻底颠覆，这真的值得让我重返编程一线吗？”然而，随着模型不断迭代，这种持续的飞速改进打破了大家的预期。在去年年底，大约是在 11 月或者 12 月的时候，我真正开始重度使用它编程。

<details>
<summary>Original English</summary>

**Spencer Kimball**: Exactly. At some point we, or others, tried it out, and people were basically trying to teach users prompt engineering: "Here is how you should talk to it if you're not an engineer." But it was clear that rapid progress was coming. Initially you look at it and go: "Okay, this is neat, but it's not necessarily game-changing. Should I really start getting back into coding?" But then this relentless, permanent improvement happened. And as you know, I started diving back into it late last year, around November or December.

</details>

**主持人**: 非常感谢你的分享，我完全理解。现在你感觉自己就像是拥有了一个全能的自主代理（Agent），所有其他人也都在感受着同样的震撼。

<details>
<summary>Original English</summary>

**Host**: Thank you, I completely understand. You know, you basically became an agent, and everyone else is seeing this shift too.

</details>

**Spencer Kimball**: 是的，长期以来我内心一直渴望能够重新写代码。如今借助 AI 编程代理，我终于能够……例如像你所看到的那样，重新以极高的效率投入到创造当中。

<details>
<summary>Original English</summary>

**Spencer Kimball**: But yes, deep down I had wanted to do this for a very long time. I mean, now you can, for instance...

</details>

<!-- chunk 8/8 -->

### 垂直扩展测试与直觉验证

**Speaker A**：看，各种各样的垂直扩展（Vertical Scaling）：比如，使用了多少个处理器节点，代码仓库的数量，磁盘节点（Nodes）的数量，系统内部节点的数量——需要测试整体性能的矩阵非常庞大。这从来都不是能轻松理清优先级的事情，它虽然看似从来没有到达过危机边缘，但我心里总凭直觉感到，这里面肯定有文章。

<details>
<summary>Original English</summary>

**Speaker A**: ほら さまざま な 垂直 スケーリング ： 例えば 、 いくつ お使い の プロセッサ ノード 、 リポジトリ の 数 ディスク に は 結び目 、 結び目 の 数 システム 内 に は 、 全体 を テスト する この 巨大 な 行列 。 これ は 決し て 適切 に 優先 順位 を つける の は 、 彼女 は 決し て 危機 的 状況 に 見え た 、 でも 私 は いつも 直感 的 に 、 何 か ある 。

</details>

**Speaker A**：后来大约过了4个小时，我真的实现了。我记得当时用了大概47个作品（或任务），或者是45？不管那个具体数字是多少。就我而言，我还记得很清楚，我打字速度其实相当快（I type quickly）。然而就在那一刻，那种感觉就像是神秘的代码符文凭空在我的眼前具象化（materializes）了一样。

<details>
<summary>Original English</summary>

**Speaker A**: その後 約 4 時間 実現 し た 、 私 が 使用 済み 、 確か 作品 47 だっ た と 思う 。 or 45? それ が 何 で あれ 数 値 。 私 として は 覚え てる よ 、 私 は かなり I type quickly. そして それ から 私 は ただ 暗号 の よう な 感覚 単に 具体化 し た 私 の 目 の 前 で 。

</details>

**Speaker B**：关于那种感觉，确实就像无意识的习惯一样，请打印出来，请呈现出来，然后它就真真切切地具象化（materializes）了。对吧？

<details>
<summary>Original English</summary>

**Speaker B**: そう いっ た こと について 。 私 無意識 の 習慣 印刷 し て ください 。 あなた お願い し ます 、 materializes. うん うん

</details>

### 黑客帝国般的编码幻觉与万行Rust代码

**Speaker A**：对，对。如果设想一下，比如程序员坐到工位上，坐在键盘前开始敲击、打印，那种极高的敲击速度。然后就变成了那种效果，对吧？工程师们……我脑海里依然有这种电影画面，还记得电影《剑鱼行动》（Swordfish）吗？大家在电影里看到的黑客敲代码是什么样子的？你知道的，屏幕上不断跳出别人飞速输入的内容，各种特效疯狂闪烁，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: もし あなた が 例えば 、 プログラマー は 席 に 着く 。 キーボード の 前 に 印刷 を 開始 し ます 。 スピード 。 そして これ そう です よ ね ？ エンジニア は 私 は まだ この タイプ を 持っ て い ます 「 ソード フィッシュ 」 を 覚え て いる 。 彼ら が 何 か が どの よう に 見える か わかり ます か ？ 分かり ます か 、 人 が 入力 し た 内容 、 そして この 効果 、 です よ ね ？

</details>

**Speaker B**：是的，没错，哈哈。但你看，这次不同的是，它在现实中是真正起效的。

<details>
<summary>Original English</summary>

**Speaker B**: はい 、 はい 。 でも ほら 、 なぜなら 今回 は 本当に 効果 が あり ます 。 比較的 。

</details>

**Speaker A**：相比之下，过去你可能需要花费整整一个月的时间。可现在你搞定了，只用了短短几分钟。一万行（10,000 lines）高度优化的 Rust（さび）代码！也就是说，这真的太令人震撼了。嗯，那可是一万行代码（for 10,000 rows/lines）啊，这简直是一个疯狂的数量（a crazy amount）。

<details>
<summary>Original English</summary>

**Speaker A**: それ それ より も 。 あなた は できる 月 。 やっ た ね 。 分 。 10,000 lines 高度 に 最適化 さび 。 つまり 、 これ は 本当に 素晴らしい 。 うーん 、 私 は for 10,000 rows. それ a crazy amount.

</details>

### 探索CockroachDB自动扩缩容与架构思考

**Speaker B**：你重新回归并开始动手写代码了。

<details>
<summary>Original English</summary>

**Speaker B**: あなた あなた が 始め た 戻る コーディング 。

</details>

**Speaker A**：我们现在所谈论的，是我们真正开始投入生产环境的过程，而这一切都是从这个工具开始的。在我们公司设有一个专门的技术总监办公室，而技术创新正是核心命脉。我也一直坚信，我们必须不断创新。我们当时迫切希望实现的一件事是——有没有更好的方法，来实现 CockroachDB 集群的自动弹性扩缩容（Auto-scaling CockroachDB cluster）。

<details>
<summary>Original English</summary>

**Speaker A**: 私 たち は 私 たち が 話し て いる の は 私 たち は 本当に 始め た 生産 へ 、 すべて は ここ から 始まっ た この ツール は 、 道具 弊社 に は オフィス が あり ます 。 技術 ディレクター 技術 ディレクター イノベーション こそ が 鍵 と なる 。 そして 私 は 、 私 たち は 革新 。 そして 、 私 たち が 欲しい もの 実装 する こと は 、 そうですね 、 もっと いい 方法 が あり ます 、 自動 スケーリング CockroachDB クラスター 。

</details>

**Speaker A**：而在1月份左右，依我看，只要能打破某种研究层面的瓶颈，就能迎来转机。事情就这样发生了。因为当时我一直在尝试与大模型协作，努力理解并打通这套逻辑。它们不仅擅长给出答案，还能极其出色地协助我们探索架构与设计思路（help explore design ideas）。我觉得这就已经足够强大了。

<details>
<summary>Original English</summary>

**Speaker A**: そして 1 月 頃 私 の 意見 で は 、 一つ あり ます 研究 の 種類 突破 すれ ば 、 言う 。 そして それ は 起こっ た 。 なぜなら 私 は ただ 試し て い た だけ だっ た から モデル と 仕事 を し 、 試し て いる これ を 理解 し て ください 。 そして 彼ら は 良い だけ で なく ヘルプ 探検 する design ideas. そして これ で 十分 だ と 思い ます 。

</details>

### 从小黄鸭调试法到实时对练伙伴

**Speaker A**：这里面最有趣的一点在于，你必须彻底抛弃那种“我必须单枪匹马创造一切”的心态。与其闭门造车，不如转变为这种态度：“嘿，我这里遇到了一个棘手问题，我们一起来讨论讨论吧。来做我的搭档（Be my partner）。”嗯，于是它就成了我日常切磋与推敲方案的对练伙伴（sparring partner）。

<details>
<summary>Original English</summary>

**Speaker A**: それ は 興味深い こと です 取り除く 必要 が ある まるで 私 が 私 は 創造 する つもり だ 。 ふーむ だが 、 むしろ 「 ねえ 、 問題 が 発生 し まし た 。 それ について 話し合っ て みよ う 。 なれ 私 の パートナー 。 」 ふーむ 。 そして 私 は スパー リング を する パートナー 。

</details>

**Speaker B**：一个共事的伙伴。你看，以前当你卡在某个难题里毫无头绪时，你只能去找橡皮鸭（Rubber Ducking）。小黄鸭调试法，桌上摆着一只黄色小鸭子。去吧，尽管对着它自言自语，找人倾诉。但那时候你需要的实质问题是无法被解答的。可是现在，你能直接和它对话交流了，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: パートナー 。 ほら 、 ある ん だ よ あなた は 行き 詰まっ て い ます 問題 、 あなた は ゴム 製 の アヒル 。 ゴム 製 の アヒル 。 が ある 、 黄色い アヒル だ よ 。 行け 、 とにかく 行け 。 誰 か に 相談 し て ください 。 あなた は それ は 必要 で ある 回答 し まし た 。 しかし 今 は 話せ ます か ？

</details>

**Speaker A**：对，这一点在今天依然极其重要。现在的这些模型太惊艳了。无论是 Fable 还是 Astra，表现都棒极了（Fable is fantastic. Astra is fantastic）。它们无所不知，上手又极其简单，就像一本随叫随到的动态百科全书。它能为你提供无数灵感和构思。

<details>
<summary>Original English</summary>

**Speaker A**: 右 。 私 は 着 て いる これ は 関連 性 が ある 今日 でも 。 これら モデル は 素晴らしい 。 Fable is fantastic. アストラ 素晴らしい 。 そして 彼ら は 知る 。 簡単 だ 。 百科 事典 の よう に 。 あなた も アイデア 。

</details>

**Speaker B**：以前我可绝不敢想象会达到这种程度，对吧？而且它给出的反馈往往会是：“完全正是如此。”

<details>
<summary>Original English</summary>

**Speaker B**: その後 私 は そう は 思わ ない 。 右 。 And it will be something 「 全く その 通り です 。 」

</details>

**Speaker A**：看，我当初也总觉得这不过是天方夜谭的科幻狂想。但现在这就是实实在在的现实。这感觉太震撼了，简直具有颠覆性的杀伤力（It's like killing）。或者说，正如你所见的那样，是的，事实正是如此。

<details>
<summary>Original English</summary>

**Speaker A**: 「 ほら 、 私 は 思っ た ん だ 、 ファンタジー 。 これ は 私 です 。 It's like killing. または あなた 右 。 はい 、 以上 です 。

</details>

### 组织管理变革与AI建筑材料

**Speaker A**：为了实现这一目标，技术正在取得不可思议的飞速进展。嗯，这绝对令人难以置信。是的，工程师要想上手并多多少少运用到一定程度，门槛其实很低。代码就这样被源源不断地生成出来。但单纯依靠这些模型本身还是不够的（These models are not enough on their own），我们必须极其审慎地审视真正的生产力。

<details>
<summary>Original English</summary>

**Speaker A**: これ を 実現 する ため に 急速 な 進歩 。 えーっと 絶対 に 信じ られ ない 。 はい 実行 は 簡単 エンジニア これ を 使う 多かれ 少なかれ ある 程度 は 。 そして それ は 創造 さ れる コード 。 These models are not それ だけ で は 不十分 だ 注意深く 見 て い ます 生産性 。

</details>

**Speaker A**：关键在于要引导它们走向正确的方向。事实上，过去任何从事过管理岗位的人，都能深刻体会到这种方式——引导、校准、明确意图。但你的观点很对，它确实极大地帮助了我们精细化地重塑工程体系。

<details>
<summary>Original English</summary>

**Speaker A**: しかし 彼ら に 指示 する 正しい 方向 実際 は 誰 でも 以前 婚約 し て い た 管理 。 これ は ちょっと どの よう に でも あなた の 言う 通り です 助け て 精巧 な エンジニア 。 私 の コンポーネント 。

</details>

**Speaker B**：作为效率提升的反面，许多人其实心存抵触（are resisting）。如果让大家更多地去使用它，我感觉大家反而能更加深度地参与到核心创造中去（more involved）。而那些没有管理经验的人，往往会担心……或者理解成别的东西。但如果你能理解我的意思，这实际上让开发者与架构本质离得更近了。

<details>
<summary>Original English</summary>

**Speaker B**: として 効率 、 are resisting. 彼ら は の よう に 使用 もっと 私 が 私 は そう 感じ ます more involved. 私 持っ て い ない 人 管理 . . . 何 か 別 の こと 。 それ より 近い もし あなた が 私 の 言っ て いる こと が 分かる よ ね 。

</details>

**Speaker A**：是的，我完全赞同。即使你是一位系统架构师，脱离了实操，很多蓝图也只是空中楼阁。如果任由问题堆积，他们根本不会主动去修（They won't fix them）。但有了这种协作模式，我们自己就能迎刃而解。比起过去，我们能做到的远不止于此。

<details>
<summary>Original English</summary>

**Speaker A**: はい 、 私 も 同感 です 。 私 それ を について でも もし あなた が また 、 建築家 。 実用的 あり ませ ん もの 。 もし 彼ら が 続ける こと が でき ます They won't fix them. 私 たち は 私 なら できる 。 それ より も 。

</details>

**Speaker A**：在我看来，最根本的最终结果在于，既然你现在能更安全、更从容地施展能力，为什么不去尝试做更多原本不敢想的事情呢？你可以安全地推进重构与演进。正因如此，我们的系统和业务才能蓬勃生长。另外，正如你刚才所提到的，将人工智能（AI）作为一种全新的底层“建筑材料”来构建系统——我们真的能做到吗？

<details>
<summary>Original English</summary>

**Speaker A**: 私 は 思う 最終 結果 私 にとって は なぜなら あなた は ただ もっと 何 し てる の ？ あなた は できる 安全 に 。 だ から 、 私 たち の 育つ 。 また 、 あなた は 次 の よう に 述べ まし た 。 新しい もの を 使う 建築 材料 AI 。 でき ます か ？

</details>