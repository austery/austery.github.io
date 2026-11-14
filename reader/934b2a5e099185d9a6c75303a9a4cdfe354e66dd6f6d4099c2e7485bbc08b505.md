---
author: AI Engineer
date: '2026-08-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=jQDXzEVHMSE
speaker: AI Engineer
tags:
  - vector-database
  - napkin-math
  - database-design
  - cloud-infrastructure
  - venture-capital
title: 对话 Turbopuffer 创始人 Simon Ericson：用‘估算思维’重构向量数据库，Cursor 创始人的第一选择
summary: 本文是《Pragmatic Engineer》作者 Gergely Orosz 对 Turbopuffer 创始人 Simon Ericson 的深度技术访谈。Simon 分享了他从自学编程、加入 Shopify 搞基础架构，到凭借‘估算思维’（Napkin Math）优化数据库成本并创立 Turbopuffer 的传奇经历。访谈深入探讨了如何利用 S3 极速冷热缓存降本 95%、与英伟达 CEO 黄仁勋的趣味互动、当下云端 CPU 算力短缺的行业内幕，以及独特的远程团队管理模式。
insight: ''
draft: true
series: ''
category: data-engineering
area: tech-engineering
project: []
people: []
companies_orgs:
  - Shopify
  - Turbopuffer
  - Nvidia
products_models:
  - Turbopuffer
  - Cursor
media_books: []
status: evergreen
---
### 电脑初恋

**Gergely**: 好的。很高兴来到这里。今天和我在一起的是 **Simon Ericson**，他是 **Turbopuffer** 的创始人兼 CEO。Simon 是一位技术背景非常深厚的 CEO。我们今天将进行一场非常硬核的技术讨论。不过在正式进入主题之前，Simon，我想先问问，你是从什么时候开始爱上电脑的？

<details>
<summary>Original English</summary>

**Gergely**: All right. It's great to be here and today with me here I'm I'm Gerge, author of the pragmatic engineer and I'm excited to have a chat with Simon Ericson uh founder CEO of Turbopuffer a very technical CEO and we're going to have a pretty technical discussion but before we jump into it Simon I wanted to ask where did you fall in love with computers?

</details>

**Simon**: 额，是通过 **PowerPoint**。

<details>
<summary>Original English</summary>

**Simon**: um through PowerPoint.

</details>

**Gergely**: **PowerPoint**？

<details>
<summary>Original English</summary>

**Gergely**: PowerPoint

</details>

**Simon**: 我不知道你们知不知道这个，但大家可能知道，在 **PowerPoint** 里，你可以制作图表之类的东西，当你点击它们时，就会跳转到另一张幻灯片。这很容易变得具有“图灵完备性”，对吧？你可以用它制作非常复杂、令人眼花缭乱的游戏。然后到了某个阶段，在探索完整个微软办公软件套件后，你发现了 **FrontPage**。你还记得 **FrontPage** 吗？

<details>
<summary>Original English</summary>

**Simon**: you I don't know if any of you know this but in power well you probably know this but in PowerPoint right you can make the the diagrams and stuff when you click them go to another slide that becomes touring complete real quick right you can sort of you know create very complicated convoluted games and then at some point you know you make it through the Microsoft Office suite and you discover Front Page. Do you remember Front Page?

</details>

**Gergely**: 是的，我记得 **FrontPage**。它在当时被认为是能够消灭所有前端开发人员的神器。

<details>
<summary>Original English</summary>

**Gergely**: Yeah, I remember Front Page. It it it was supposed to eliminate the need for all any front-end developers.

</details>

**Simon**: 确实。而且它当时只在 **Internet Explorer** 浏览器里能正常运行。我记得有一天，当有人在 **Firefox** 浏览器里打开我制作的网站时，我简直伤透了心，因为整个页面彻底乱套了。后来有一天，我无意中在 **FrontPage** 里点击了 HTML 源代码视图，看到了那些完全看不懂的代码。我开始仔细研究它，然后在网上寻找一些小代码片段复制进去，比如改变光标样式之类的各种小玩意儿，慢慢地，技术就从那里起步了。再后来，你升级到了 **Dreamweaver**，开始真正写代码，然后你就会想：“如何动态生成网页呢？”于是你学会了 **PHP**。至于我，当时我已经把丹麦语的编程教程全部看光了。

<details>
<summary>Original English</summary>

**Simon**: Exactly. And it it only worked in Internet Explorer. I remember a heartbreak I had one day when someone opened a website I created in Firefox and it just it was it was all over the place. And then one day I accidentally clicked the HTML thing in front page and it just showed all of this stuff that I couldn't make sense of and it just started looking at it and then going online and finding little snippets that you could add in to make the cursor change and all of these different uh different things and then it just sort of escalated from there. Then you upgrade to Dreamweaver and now you're coding and then you're like well how do you make the pages dynamically? you learn PHP and then for me I exhausted the internet on Danish language programming advice.

</details>

**Gergely**: 嗯哼。

<details>
<summary>Original English</summary>

**Gergely**: Mhm.

</details>

### Shopify 缘起

**Simon**: 当时我大概 11 岁或 12 岁，然后我迷上了《**魔兽世界**》（World of Warcraft），一玩就是四年。但这也让我的英语变得非常好（笑）。所以你就这样开始自己折腾，并逐步深入。在正常情况下，合乎逻辑的下一步应该是去读大学，系统性地学习这些技术。但你并没有这么做，对吧？

我当时就是……我开始玩电脑游戏，学会了英语，然后面对着这个庞大的万维网。如果现在有大语言模型（LLM）就好了，因为它们可以直接对我说丹麦语，我就不会像当年那样撞墙了。那肯定会非常有趣，也许我的编程水平会更高，哈哈。接着，我在读高中期间开始接各种零工。高中的时候，我还接触到了一项叫作**国际信息学奥林匹克竞赛**（IOI）的项目。你听过这个比赛吗？

<details>
<summary>Original English</summary>

**Simon**: Um and I was I was around 11 or 12 and so I just you know went and got addicted to World of Warcraft for four years but that gets you really really good at English. [laughter] So you kind of start hacking get into deeper. Now the logical step would have been to just you know go to university and learn properly about this stuff. But that's not what you did did you? I mean I just um I I started just I I mean you know then I learned video games then I learned English and then you know this like massive arsenal of the web. I now it'd be very interesting because the LLMs would just speak Danish to me and you could just you wouldn't have hit the wall like I did. Um, so that would have been very interesting. Maybe I would have been better at programming. That would have been nice. And then I Yeah. Then I just started picking up jobs and things like that throughout high school. And when I was in high school as well, I got exposed to this thing called the International Olympiad in Informatics. You heard of this thing?

</details>

**Gergely**: 听过。

我有一个网友住在澳大利亚，她是澳大利亚国家队的成员。她告诉我，丹麦应该也有类似的队伍，但我之前从未听说过。于是我在一个神秘的网站上找到了报名入口，提交了申请，然后去解决那些和我之前写 HTML 和 PHP 完全不同的算法问题。

<details>
<summary>Original English</summary>

**Gergely**: Yeah. Um, and I had a I had an internet friend and she lived in Australia and she was on the Australian team and she told there's probably something for the Danish team as well, but I had never I'd never heard about it before. And so I found it on some like little mysterious website and then applied and then solved these programming problems that look very different from the HTML and PHP things that I'd solved until

</details>

**Gergely**: 那些是更偏算法类的程序。

<details>
<summary>Original English</summary>

**Gergely**: were like the algorithmicalish programs.

</details>

**Simon**: 没错。其实那些问题并不是我们在日常工作中会遇到的，但我认为它很好地展示了你需要面对的挑战。比如你可以想象一个问题：这里有 $N$ 辆卡车和 $M$ 个包裹，每个包裹都有特定的尺寸，你需要计算出哪些卡车应该装载哪些包裹以达到最优分配。这是一个 NP 完全问题，你无法完全解决它，但你可以在比赛中通过设计最好的近似方案来和其他人竞争。就是这一类的问题。

然后我开始做这个。在高中时我也在一家初创公司工作。接着，在我还在读高中的时候，**Shopify** 找到了我。

<details>
<summary>Original English</summary>

**Simon**: Exactly. It's sort of like this is not actually the kind of problem you would see there but I think it illustrates well the kind of problem that you might get right is you could imagine something like okay here's like n trucks here's m packages the m packages have these dimensions give me which trucks which packages should be in right and then do something optimal like that's an npmplete problem you can't solve that but you could compete with everyone else in the competition of doing the best thing so it's these kinds of problems right um and so I started doing that. In high school, I was working um I was working as well um for a startup. Um and then I just Shopify found me while I was still in high school.

</details>

**Gergely**: 关于 **Shopify** 找到你，是通过你的开源贡献，还是别的原因？

**Simon**: 是因为我写了一篇文章。我当时摔坏了我的 **iPhone**。你知道，在过去那个时代，一旦你把 **iPhone** 摔在地上，屏幕基本上就彻底报废了。

<details>
<summary>Original English</summary>

**Gergely**: And and the whole like Shopify found me, was it through your open source contributions? Was it was it something else?

**Simon**: It was because I had written an article where I had I had I dropped my iPhone and it was you know the iPhones are a lot like there used to be a time right where you drop your iPhone and you just knew it was over for the screen.

</details>

**Simon**: 现在的屏幕好多了，不太容易摔坏，但当时那一摔，手机就彻底废了，没法再用。所以我换回了老款的诺基亚（Nokia）搬砖手机。那是 2013 年，当时大家还没有普遍意识到智能手机带来的负面影响。于是我写了篇文章，说：“天哪，我重新开始给别人打电话了，而且我的方向感也找回来了。”我把这篇文章发到了网上，它短暂地上过 **Hacker News** 首页，接着《纽约时报》也决定报道这个故事。

<details>
<summary>Original English</summary>

**Simon**: It doesn't really happen as much anymore like the screens have gotten a lot better but back then it was like yeah one drop and it was dead and it just couldn't use it anymore. And so I went back to one of these old Nokia brick phones. And this is back in 2013. And people hadn't really realized all the pernicious effects of smartphones at the time. And so I wrote this article about how oh my god I'm like calling people and I have my sense of direction back. Um and I wrote an article about it. And this article it went on hacker news briefly and it um New York Times decided to feature it.

</details>

**Gergely**: 不会吧！

<details>
<summary>Original English</summary>

**Gergely**: No way.

</details>

**Simon**: 是的。所以这篇文章带来了巨大的流量。然后一些非常敏锐的 **Shopify** 招聘人员注意到了它。他们联系了我，我跟他们聊得很开心，我想当时他们可能根本没意识到我还在上高中。他们邀请我去加拿大渥太华总部面试。我当时根本不知道渥太华在加拿大哪里，我回复邮件时甚至问过：“渥太华是什么？”。

总之，我去了那里。当我走进大楼的那一刻，感觉非常对路。我完成了面试，然后对他们说：“我得先读完高中，然后再搬来加拿大。”于是在 2013 年高中毕业后，我来到了加拿大，加入 **Shopify** 工作。

<details>
<summary>Original English</summary>

**Simon**: Yeah. And so a lot of traffic was driven to it and then some astute Shopify recruiter put it all together and um and I had a call with them and then I don'\''t think they realized that I was still in high school but um but I had a great call with them. They invited me on site to Ottawa, Canada. Um I had no idea what Ottawa Canada is. I think the email says something like what'\''s an Ottawa? I had no idea. Um, and so I went there and it was just like walked into the building and it was just a just felt right. Um, and so I I I interviewed with them and then said, "Well, I got to finish high school first and then uh and then I moved to Canada uh to to to work at Shopify." Yeah. In 2013.

</details>

**Gergely**: 我觉得对于不去读大学这事，这确实是一个非常正当的理由。

<details>
<summary>Original English</summary>

**Gergely**: Yeah. I think that's that's a like legit excuse for like not even worrying about college and and university.

</details>

### 系统工程速成

**Simon**: 但我脑子里也纠结过。我当时以为我只是去体验一个间歇年（Gap Year），我想着：“好吧，我去 **Shopify** 工作一年，然后大概率还是会回去读大学。”但当时我对于自己没有系统学习过计算机科学感到非常不安。我唯一的计算机科学背景就是 IOI 竞赛，虽然这对于很多算法基础而言是个非常不错的速成班，但它至少教会了我一件事：只要你花足够的时间，你完全可以直接坐下来阅读一篇论文并搞懂它。

于是在加入 **Shopify** 的第一年，每当我听到任何我不懂的名词，我就把它记在纸上，晚上回家我就去查资料，疯狂自学。因为我感到很焦虑，觉得如果别人提到 TCP，他们肯定对三次握手了如指掌，也知道 TLS 是如何在其上分层的，甚至用过 Wireshark 分析过包。虽然现在我知道事实并非如此，但当时我确实是这么认为的。所以我针对自己遇到的每一个新概念都去做了深挖。

<details>
<summary>Original English</summary>

**Simon**: It did. I thought I was going I thought I was doing a gap year. I thought I was like, "Okay, I'm gonna go work at Shopify for a year and then I'll probably go back and do but I would just I was very insecure at the time about the fact that I hadn't studied computer science and my only exposure had been all the II competitions which is a pretty good crash course in a lot of computer science and if nothing else it had really taught me that you can just sit down and read a paper and just figure it out if you spend enough time on it." So I did I did that repeatedly and in my first year at Shopify I just every time I heard something that I didn't know what was I noted it down on a piece of paper and then I went home and then that evening I would just read about it because I felt insecure that like well if someone mentions mentions like TCP surely they know exactly what's in the three-way handshake and how TLS is like layered on top and they've looked at Wireshark and all of that. I don't think that's true but that's what I thought. So I went and did that for everything that I encountered.

</details>

**Gergely**: 这听起来是一个极好的速成方式。你拥有一种非常天然的危机感，因为你很年轻，没有别人那样的科班学历，而公司又在处理非常前沿的技术挑战。所以你不断地逼迫自己，自学跟进。我可以理解为，你对每一个不懂的概念都会刨根问底，不仅是表面理解，而是买书、查资料，能走多深就走多深吗？

<details>
<summary>Original English</summary>

**Gergely**: So I went and did that for everything that I encountered. Um, so that was a really good crash course and then very quickly it became clear that well I just want to continue doing this. I don't want to go go somewhere else and then come back to this because I felt like I'd already found what I wanted to do. So it sounds sounds like it was a pretty good combination of like you just having this like very natural insecurity like you know you're young, you know, you don't have the education that everyone else has and inside a company that's just doing pretty like cutting edge stuff even at the time and even even to today, right? Like they're they're leading. So you just kept self-seing yourself like just catching up and go and then do I understand that you just went deep in every concept that you understood. You didn't like just like try to understand a surface level but like go as deep as you can search on the internet buy books whatever that is.

</details>

**Simon**: 我觉得只是因为我想弄明白计算机到底是怎么工作的。这也是我现在面试工程师时非常看重的一点：你是否会忍不住去剥开技术的层层外衣。对于我来说，这条探索之路最终通向了基础架构层——也就是 **Shopify** 里那些最接近物理硬件的底层系统。吃午饭的时候我总是坐在他们旁边，尽管我当时在业务产品团队。我就是忍不住想学习，当他们讨论“反向代理”（Reverse Proxy）时，我会想，为什么是“反向”？我至今也解释不清楚（笑）。我的意思是，这就像倒排索引（Inverted Index）一样，名字取得很糟糕。但无论如何，这比 NAT 表查表这些东西有趣多了。

在 **Shopify** 工作期间，有哪些极具挑战性的工程难题、宕机事故或者经验定义了你的职业生涯，并且是你在其他地方很难获得的？

<details>
<summary>Original English</summary>

**Simon**: I think it was just that I just wanted to know keep learning how computers work and I think that this is something that I now look for when we interview engineers is that you just you can't help yourself but trying to peel back the layers and for me that ended up with the infrastructure layer that was you know the people closest to the metal at at Shopify and I would just always sit next to them at lunch because I was working on the on the product side but I just I couldn't help myself. I was so I just wanted to learn what it was when they were talking about a reverse proxy. I'm like, why is it reverse? I I still can't answer that. [snorts] I I I mean, okay, [laughter] you know, well, what's in reverse? Because it's a proxy, right? I don't I don't know. I don't know. It's like an inverted index. Like what's inverted? It's like it's a terrible name. Anyway, yeah, I I mean it's still better when when you get the NAT nat tables, the lookups, some of those things like some of that. But yeah, I hear you there. There's some like weird names with this, but at at Shopify, what were some of the kind of like hard engineuring challenges that you engineering challenges, outages, like like learnings that kind of defined you that were really also fun at the time or interesting to learn, but it would have been hard to get it elsewhere.

</details>

**Simon**: 在 2010 年代，有一大批 SaaS 公司经历了极速的规模扩张，我很幸运能近距离见证这一点。我最终加入了基础架构团队。那是 2013、2014 年左右，**Docker** 刚刚问世，我们正在对所有系统进行容器化。每年我们都要为比上一年更疯狂的“黑色星期五”（Black Friday）做准备。当时我们还在买物理服务器硬件，我们必须在特定时间点下单，并根据流量预测进行外推。

软件层也必须进行扩展。而在扩展大多数软件时，应用层的所有问题最终都会堆积到数据库层。因此，我自然而然地将精力集中在了 Rails 框架和数据库之间的这一层。**Shopify** 当时其实并没有直接给数据库内核贡献太多补丁，我们主要做的是数据库的编排和分库分表（Sharding）。正如我亲爱的老板 Camilo 常说的：“你无法缓存写操作。”所以到了一定阶段，你必须跨越单机，进行分片。

我是在他们做分片期间加入的，他们居然在黑色星期五前一周完成了分片的切换，这简直是疯了，但他们成功了。在随后的几年里，我们致力于多数据中心部署。我们当时还有一个非常神秘的 **Redis** 服务器，内存有 128 GB，这在当时是海量内存，没人知道里面具体存了什么。直到有一天它宕机了，大家都吓坏了，因为人们之前一直把它当成一个单纯的键值缓存。于是我们开始对它进行拆分。我们做了一系列工作，确保当你在访问一个 **Shopify** 店铺时，即使会话缓存宕机了，正确的行为也不是让整个店铺全部崩溃挂掉。然而，这通常是默认的失效模式，除非你所使用的编程语言或系统框架强制你做出更有弹性的设计。

我们构建了一个矩阵，规划当某个组件宕机时服务应该如何响应。我负责为这一整套机制编写测试套件。当时我觉得不能只用 Mock 来模拟这些故障，于是我提出了一个疯狂的想法：我们通过 shell 脚本调用 **GDB** 注入到运行中的进程里，强行关闭指向数据库的文件描述符，以此来模拟数据库在网络底层的彻底失效。虽然我们最终没有把这套机制放进 CI 持续集成系统里，但它确实暴露了 Rails 框架在连接层处理失败时的海量 Bug，后来我们把这些修复贡献回了开源社区。接着，我开发了一个名为 **Toxiproxy** 的代理服务。

<details>
<summary>Original English</summary>

**Simon**: Yeah. So I think it was, you know, in the 2010s there's like a bunch of SAS companies that that scale really quickly and I felt so fortunate to have a front row seat to that and so I ended up on the infrastructure team and this was back in you know 134 and uh Docker was coming out and so we were containerizing everything and we were just every single year we had to you know the growth rates of of of SAS sometimes seems quaint in comparison to the growth rates of companies today but it was a company that was growing at you know 120 40% year-over-year. Um, and so every year we were just preparing for a Black Friday that was going to be a lot worse than the last. And this is back in the day of we're buying physical hardware, right? We have to like place an order at a particular point in time and do some interpolation based on that. Um, and the software also had to scale. And when you're scaling most software, a lot of the application layer problems end up back at the database layer. And so I just naturally found myself at this layer between Rails and the databases. Shopify didn't at the time at least contribute many patches to the databases themselves but mostly just spent time orchestrating. So we were doing sharding because as um my my dear boss Camilo used to say you can't cache rights. So there's a fundamental point where you you just you have to move beyond a single shard. Um so I wasn't I joined around the time and they did the sharding and they did it I think they did the cut over a week before Black Friday which is mindblowing. uh and very but it worked and then the the subsequent years we worked on things like going into multiple data centers. We also had this big mysterious reddish server that was like you know 128 GB of RAM which was a lot at the time. Today it's not that much and no one really knew what was in it and then it went down one day and people were like well that's super terrifying. Um because people had just been treating it as this KV store. Um and so we started splitting it out. We did all this stuff around making sure that if you if you if you go visit a Shopify store and the thing that stores your sessions is down, the right behavior is not just for the entire the of everything to be down. But that's kind of the default failure mode, right? You're not going to rescue all of that. Um unless you're in a programming language that really forces that decision. So we did things like um build this matrix out of okay well this service when this component is down should act this way. Um and I found myself writing the test suite for a bunch of that. And then I was like okay well we can't just mock all of this. And so um I came up with this idea at the time of like oh what we're going to do is we're just going to um shell out to GDB and then into the process and then close the file descriptor to the database to simulate the through the entire layer that the database fails. That was a little crazy and we never shipped that on CI but it did uncover a massive amount of issues in Rails that' be upstream and things like that of around just like handling failures at the connection layer. So then I moved on to create this proxy called Toxyroxy and

</details>

**Gergely**: 你听说过这个吗？

<details>
<summary>Original English</summary>

**Gergely**: have you heard of this before?

</details>

**Simon**: 没有。

<details>
<summary>Original English</summary>

**Simon**: No. No.

</details>

**Simon**: **Toxiproxy** 是一个主要工作在第四层的代理服务器，介于你的应用程序和数据库之间。它支持通过 API 调用来实现“让数据库下线”、“注入延迟”等操作。后来它还增加了第七层的一些特性。这样你就不需要去 Mock 底层的网络驱动程序，而是可以直接测试真实的驱动程序及其对故障的处理逻辑。这样整个故障矩阵就可以在 CI 中得到自动化验证。

<details>
<summary>Original English</summary>

**Simon**: Yeah. Toxyroxy is it's just like a layer 7 proxy that sits in between um you and well layer four but in between you and the databases. So you basically have just like this proxy and then my SQL whatever doesn't speak the protocol but then you can do an API call say take take uh take the database down make it slow um and over time it also added layer 7 things of like do a bunch of failures this way you're not mocking the low-level drivers but you're testing the drivers and their failure handling as well so then this entire matrix could be implemented in CI so the basically the proxy was just like a really thin layer which like was passed through but you built the functionality to like simulate problems with database or things like data corruption or whatever you wanted to do. So you could just do it in there and then you can anything that built on top of it but but then Oh yeah and then everyone had to like call this proxy or it needed to be on in a layer.

</details>

**Gergely**: 明白。所以开发者可以直接在代码里写类似 `proxy.mysql.down`，然后传入一个 Lambda 函数去执行某些操作，比如“在会话表宕机的情况下请求页面或执行结算”，这在当时发现了 MySQL 驱动程序和 Rails 中的几十个未曾暴露的 Bug。因为以前生态里没人对这些场景做过自动化测试，而在生产环境中，当 MySQL 宕机时，所有人都在忙着让它重新上线，根本没人有精力去排查应用层的鲁棒性细节。

这非常有趣。虽然我们后面还会深入讨论数据库，但我一直在思考，大型系统中最棘手的问题几乎都与“状态”（State）有关。如果有数据库，你就必须面对状态问题。如果只是无状态服务，节点挂了就挂了，影响是局部的。可一旦涉及状态，事情就变得极其复杂，且很难在真实发生前对其进行模拟。这套机制在 **Shopify** 应该运行得非常成功吧？

<details>
<summary>Original English</summary>

**Gergely**: Exactly. So you could do like do like my you know proxy.mmysql downdown and then pass it a lambda of what you wanted to do like get this page do a checkout whatever with the sessions table down and this just uncovered tens of issues right in the myql driver in the rails like it's just like no one in the ecosystem had been testing for this and it was very difficult to see this in prod right because in myql down you're focused on just getting back up and not like what could the application actually have done. Yeah, it's interesting. Of course, we're going to talk a bit more about databases obviously, but just thinking about how a lot of the problems or some of the most gnarly problems in large systems are always to do with state and I never connected until now that I mean state is usually there's a database. If there's no database, if you have stateless services, you know, I mean, you still have problems, you have nodes going down, you have, I don't know, corruption, whatever, but it's usually like more isolated. But basically, like if we have state, we typically have databases. is if we have databases and if you can simulate these problems suddenly you can I mean you you can like predict a lot of things but the problem with state often time is it's really hard to simulate problems happening ahead of time unless when they happen so did you it sounds like you have pretty good success with

</details>

**Simon**: 据我所知，它至今仍然运行在 **Shopify** 的 CI 系统中。我们围绕它编写了大量的测试用例来覆盖各种不同的故障场景，效果非常好。

你在 **Shopify** 一共工作了八年。最开始只打算待一个 Gap Year，结果一年又一年。你是在什么时候决定离开的？你的决策框架是什么？毕竟即便是今天，**Shopify** 发展得也非常好，你完全有理由留在那艘巨轮上。

<details>
<summary>Original English</summary>

**Simon**: yeah I think to my knowledge it's still um running in like the CI system of Shopify today I don't know if anyone in the crowd is from Shopify but I'm pretty sure that it still does um and so we wrote all these tests against it to implement and all of these different uh different failure conditions and it just yeah it was it was it worked out great. So you spent eight years in total at at Shopify. So like starting from like all right just a gap year it just went on a year a year and another year. Um at what point did you think about leaving and why and what was your kind of decision framework? It sounds like you or you were like on Epic right now even today Shopify it's doing wonderful. It's probably doing even way better than like like you know that growth kind of kept on. So I'm sure there would have been an argument to stay and you know stay on their August ship.

</details>

### 估算与 Napkin Math

**Simon**: 我在 **Shopify** 从 2013 年待到了 2021 年。我想在某个时间点，我非常渴望去见识一些不同的东西。我从 18 岁起就待在 **Shopify**，此前只在高中时期接触过另一家初创公司。我想，如果我真的想在计算机领域学得更快、走得更远，是时候给我的生活函数注入一些“新奇性”（Novelty）了。

我在那里参与了许多不同的基础架构项目，比如缓存。我和现在的联合创始人 Justine 一起重写了 **Shopify** 的整个 Storefront 系统，在项目启动 18 个月后，它承载了公司近 100% 的流量。我们还做过多数据中心运行，以及各种数据库扩展和缓存项目。很多扩展性的极限挑战实际上是由卡戴珊家族（Kardashians）在 **Shopify** 上发售产品所带来的瞬间超大流量所逼出来的。但我最终还是选择离开了，离开时我其实并不知道自己接下来要做什么。不过，我在 **Shopify** 期间曾发起过一个名叫 **Napkin Math**（估算思维）的项目。你看过这个项目吗？

<details>
<summary>Original English</summary>

**Simon**: Yeah. So I I spent I spent eight years there from 13 to to 21. Um and I I think there just came a point where I wanted to see something different again. I've been inside of Shopify since I was 18 years old, right? I'd been seen one other startup in high school. I was like if I want to learn more about computers and learn faster, it might be time to inject some novelty into this function. Um, and so I I left in in in 21 and I'd worked on so many different parts of the infrastructure like caching. Um, me and Justine, who's now my co-founder, we wrote the entire storefront um, storefront for Shopify, um, which powered almost 100% of traffic 18 months after we embarked on it. Um, we've worked on running Shopify in multiple data centers. We've worked on so many database scaling projects like caching, all of these different things, right? Um, a lot of the a lot of the scalability came from the Kardashians launching lots of products on on Shopify, which would force a lot of traffic. Um, but that's that's eventually how I left. And so when I left, I didn't really know what I wanted to do. And so I one of the projects I had while I was at Shopify was this napkin math project. Have you seen this

</details>

**Gergely**: 估算思维？没有。

<details>
<summary>Original English</summary>

**Gergely**: napkin math? No.

</details>

**Simon**: **Napkin Math** 本质上是我在 GitHub 上维护的一个表格，记录了各种底层的系统性能常数：比如你能从 DRAM 中榨取多少带宽？一次 **S3** 的往返时延和成本是多少？向 NVMe SSD 写入的带宽是多少？向 EBS 卷写入的带宽是多少？大概收集了 50 个这样的关键数字，并用一个 R 脚本自动生成它们。

还有它们各自的成本，比如：1GB 的内存需要多少钱？2 美元。1GB 的 S3 存储需要多少钱？2 美分。EBS 的成本是多少？10 美分。在抢占式实例（Spot Instance）上是多少？如果签三年合同又是多少？我把这些数据整理成了 flashcards（闪卡），强迫自己把每个格子都背下来。

这源自我当时在 **Shopify** 的核心工作之一：技术评审。经常有业务团队过来说，我们要做一个新功能，需要搭建一套新的基础架构，然后告诉我：“我们在数据库 A 上做了基准测试（Benchmark），效果不好，所以我们决定改用数据库 B。”

我非常讨厌盲目做基准测试。因为那不是一个有说服力的答案。在我看来，根据我的直觉和粗略估算，如果数据库 A 需要 10 秒才能处理完某个查询，那只要我们做对优化，它应该在 10 毫秒内完成。比如一个搜索查询：你要搜索三个词，每个词匹配多少个文档？这对应多少兆字节的数据？我们需要求交集的数据列表有多大？在多核 CPU 拥有每秒 100 GB 的 DRAM 带宽的情况下，这理应只花 10 毫秒。你现在测试测出 10 秒，那我们中肯定有一个人错了。要么是我理解有偏差，要么是你们测错了东西。

而事实往往是，他们根本没意识到自己的基准测试触发了跨越 100 个不同节点的分布式查询，所以 P99 时延才高得离谱。我反复遇到这种基于低质量基准测试做基础架构技术选型的情况。所以我需要一些“理论武器”，让我们能当场通过计算得出理论极限。后来我离开 **Shopify** 后，写了许多关于这方面的文章。我一直在问自己，一个查询理论上到底应该花多少时间？

当时我有一个假设：MySQL 每秒能执行多少次写入？理论上，它每秒的写次数不应该超过它每秒能执行的 `fsync`（文件同步）次数吗？这符合直觉，因为每次写入都要 `fsync` 落盘以确保持久化。那么一个 `fsync` 大概要 1 毫秒，所以每秒只能做 1000 次写入。但实际上这和观测不符，因为数据库每秒可以轻松做超过 1000 次写。为什么能做到？于是我去做了测试，发现 MySQL 在一个很小的配置上居然能跑到每秒 10000 次写。这怎么可能？

<details>
<summary>Original English</summary>

**Simon**: No. Um, so napkin math was essentially just this table that I maintain on GitHub of how much bandwidth can you drive to DRAMM, what does a roundtrip to S3 cost, and how long does it take, how much bandwidth can you drive to an NVME SSD, how much bandwidth can you drive to an EBS volume? Just a collection of probably there's probably like 50 of these numbers and then a RS script that generates them all. um what all these things cost? What do you like? What does a gigabyte of memory cost? $2. What does a gigabyte of S3 cost? 2 cents. What does a gigabyte of um this cost? 10 cents, right? What does it cost on spot? What does it cost on a three-year commit? Like I had just have a massive table and then create flash cards for almost every single cell. So I know all these numbers. And this was a project I started taking on at Shopify because I found myself in um this role a lot where I would go in and review a project, right? So some product team would be like okay we got to do we got to build this thing so we got to build this infrastructure to support the feature and a lot of the times they would say okay well we've gone and benchmarked it on database A but the benchmarks are not very good so we're going to go with database B and I hate benchmarks so much because that's not a satisfying answer to me to me it's like this does not jive maybe my intuition database A that you're saying takes 10 seconds to do this should take 10 milliseconds if you do the napkin math right if it's a search query right it's like okay you're searching for three terms there each term has this many documents that match it that's this many megabytes we inter intersect these many this many lists you have DRAM bandwidth on multiple cores of 100 gigabytes per second this should take 10 millisecond you tell me the benchmark takes 10 one of us is wrong. Either there's a gap in my understanding, which is very likely, or you would benchmark the wrong thing. And in some ways, some reasons, right, it's like, okay, you've done a benchmark. You don't didn't realize that your benchmark is doing a distributed query across a 100 different nodes. And so, of course, the P99 is going to be really, really high, right? Unless you've cut that off or or made some different set of trade-offs. So I just found myself in these discussions repeatedly where people were making infrastructure decisions based on poor benchmarks. And so I needed some I I needed some ammo to go in and just be like okay we can just do the calculation right here and then. Um because I was always doing these like little demos or like writing little prototype scripts to to demonstrate this. But it was just I just the argument of here's how a beach tree works. This is how many pages we have to visit. This is what a random SSD read takes. It takes one millisecond. you have to visit a thousand blah blah blah blah blah and then present it back and see if this is the difference to your query. Well, like is the query plan correct? Like is there a bug in my SQL? Do we have bad discs? Like what's the discrepancy here? And I just got caught with that bug. And so after I left Sha, I was just writing a lot of articles about this. I was just like, well, how long does should this query take? And then I one hypothesis I had at some point is like, okay, well, how many writes per second can MySQL do? Well, shouldn't the amount of writes per second that MySQL do equal the amount of f-syncs that you can do per second? That sort of makes sense, right? Every time you do a write, you f-sync to persist to disk. So, how many f-syncs can you do per second? Well, an f-sync takes one millisecond. So, you do a thousand writes per second. That well, that doesn't really match up. Like, feel like a database can do more than,000 rightes per second. Why can it do that? So, that was one of those things where I tested and it's like, okay, well, my SQL on a little dinky box could do 10,000 writes per second. Well, how is that possible? Mhm.

</details>

**Gergely**: 那你现在会怎么解答这个“如何可能”的问题呢？

<details>
<summary>Original English</summary>

**Gergely**: And now you would just ask how is it possible?

</details>

**Simon**: 因为有“组提交批处理”（Group Commit Batching）。一个 `fsync` 写入通常发生在 4KB 的粒度上。

<details>
<summary>Original English</summary>

**Simon**: Because you batch. So an f-sync happens on usually a 4K.

</details>

**Gergely**: 是的。

<details>
<summary>Original English</summary>

**Gergely**: Yeah.

</details>

**Simon**: 但这并不符合直觉。为了弄清这个问题，我大概经历了一次长达 24 小时的疯狂研究，编写 BPF trace 脚本去追踪内核行为。在有 LLM 之前，干这个极其费劲。我最终发现每次实际写入盘的数据块比我想象的要大得多，因为系统底层在做批处理。我深入阅读了 MySQL 的源码，甚至还找到了一篇由德国巴伐利亚小镇的一位开发者写的非常冷门底层的文章，解释了 MySQL 某些极度深奥的内部细节以及他们提交的补丁。我确信，整个互联网其实是靠巴伐利亚小镇的程序员们在默默支撑着（笑）。

<details>
<summary>Original English</summary>

**Simon**: Right. But it's like that's not intuitive. Like it's actually I I I got caught. It was like just like you know probably some like 24-hour period where I just got obsessed with this question where like you're writing like the BPF traces and all of that to do all of this. This is like pre-LM so it took forever and you and then I found out that oh every f-sync was like much larger than I would have inferred like oh it's batching you go into the code and you read it and then you found some obscure article by it's always somewhere in like a central German town that's like written some article about like how some intricacy of my SQL works and a patch that they did to it's like the entire internet runs on small towns in Bavaria. I'm convinced. Yeah.

</details>

### 创立 Turbopuffer

**Gergely**: 然后你就决定创立 **Turbopuffer**？在做这个决定时，你已经明确知道自己要构建什么了吗？还是仅仅因为你对数据库非常狂热，想做点数据库相关的事情？因为你在推演理论极限的基准测试方面做得非常出色，已经在这个细分领域成了专家。你当时有想过要再次深耕数据库吗？

<details>
<summary>Original English</summary>

**Gergely**: And then you decided to start Turbopuffer. Yeah. Did h how did you decide? Did you know what you wanted to build or was it more like I want to build something something databases because you were clearly very into databases. You you've done an awesome job benchmarking like what is the theoretical like limits? You were very familiar with this probably became you know like world expert in in this niche. And then how did did you want to go into databases again?

</details>

**Simon**: 我认为当时有三件事交织在了一起。首先，我在 **Shopify** 参与的最后一个项目是搜索，那次体验非常糟糕。

<details>
<summary>Original English</summary>

**Simon**: I think it was there's three things that sort of came to a head. Um the last project that I worked on at Shopify was search and I didn't have a good time.

</details>

**Gergely**: 你们当时用了什么？我们不需要指名道姓批评其他数据库公司。

<details>
<summary>Original English</summary>

**Gergely**: What what what did you use back there?

</details>

**Simon**: 它是很多公司都在使用的传统搜索引擎之一。在我的实践中，那些涉及该数据库的项目极难达到我通过 “估算思维” 算出来的机器物理上限。它没有良好的查询规划器，我搞不懂为什么会这样，有些时候它能对得上，但很多时候性能完全偏离轨道。为了弄明白，我尝试去读它的源码，但发现它很难实现预测，运维成本也极高。这成了一个悬在我脑后的阴影。我当时发誓再也不碰搜索了。

第二个因素就是我的 **Napkin Math** 项目，它让我对硬件设备在完美使用时能达到怎样的理论极限有了非常深厚的积累。

<details>
<summary>Original English</summary>

**Simon**: Um I don't we don't need to name names of other database companies but it was uh it was one of the one of the like traditional search companies that a lot of different um companies run and it was just very difficult to get it to do what I did and I was just like the projects that touched that database just I couldn't get them to perform at the napkin math and like there's there's no query planner and like I couldn't figure out why it wasn't there and sometimes it tracked and then sometimes it really didn't track at all and so I tried to learn as much as I could to figure out and like start reading the source code of it and I was just I couldn't get it to track very often. It was very difficult to operate and so I just that was sort of like in the back of my head. I never thought I would touch that again. Then the second ingredient was the napkin math project because it sort of just gave me a lot of facility with all of these napkin math numbers of what might be achievable with the machine if you utilized it perfectly properly. Yeah.

</details>

**Simon**: 第三个因素是，在 2021 年离开 **Shopify** 后的这段时间，我做了一件我称之为“天使工程”（Angel Engineering）的事：我加入了我朋友的初创公司，只拿股权不拿工资，因为我希望亲自动手，看看外面的世界有什么新东西。在这个过程中，我反复遇到同一个问题：2022 年底 ChatGPT 横空出世，我当时正在合作的一家公司想把大量的文档接入 AI，但当时的上下文窗口（Context Window）非常小。所以你必须非常快地引入语义搜索。

<details>
<summary>Original English</summary>

**Simon**: And then the third one was that doing this you know leaving Shopify in 21 having spent eight years there and during that time I did this I called it angel engineering so I like joined my friends companies and then I just vested equity instead of um instead of just investing or something like that and because I wanted to have my fingers in it I wanted to like see what else was out there that's why I left and this problem kept coming up again again and again and again right like ChachiBT came out in 2022 and I was working with with a company then and They wanted to connect a bunch of documents to AI and that's when the context windows were really small. So you had to reach for search very quickly.

</details>

**Gergely**: 当时只有几 KB。

<details>
<summary>Original English</summary>

**Gergely**: So it's like a few kilobytes.

</details>

**Simon**: 根据模型不同，只有 4KB 或 8KB，非常局限。所以你不得不依赖向量搜索。我帮他们写了一个推荐引擎，效果非常好。比如，在这个引擎运行我的一位联合创始人的动态推荐时，我甚至通过推荐内容推断出他的妻子怀孕了。虽然这听起来有点诡异，但确实推荐得很准。

<details>
<summary>Original English</summary>

**Simon**: It was eight kilobytes or four kilobytes depending on the model. It was very very small. So you had to reach for search very quickly. Right. And so I I I worked with them and I was I was I created a little recommendation engine and the recommendation engine was actually quite good. Um, like I s I found out that one of the co-founders wife was pregnant through the recommendations that I was getting when I was running it on his feed. Um, like it was it was it it

</details>

**Gergely**: 确实有点神奇。

<details>
<summary>Original English</summary>

**Gergely**: weird but

</details>

**Simon**: 是的。当时他正在阅读很多相关文章，当然我也拿到了授权。我当时就想，这东西很有用，但当我粗略计算了为所有用户提供这个功能的账单成本后——这是一家叫 **Readwise** 的加拿大独立开发者公司，他们当时在其他所有基础架构上的开销总共也就每个月 5000 美元，而如果跑这个向量推荐引擎，每个月光是向量数据库的账单就要 30000 美元！这在商业逻辑上是无法接受的，因为你必须在你的成本之上保留毛利。由于成本算不过来，我们最终没有上线这个功能。

但我无法停止思考，为什么存储和查询这些用于推荐的向量会如此昂贵？有一天我坐下来做了一次粗略估算：我们能不能把数据全部放在 **S3** 上，做一些聚类并把文件组织好，然后在此之上构建一个数据库？2023 年的整个夏天，我都泡在里面，试图找到一种可以在 S3 上跑出低时延的方法。

<details>
<summary>Original English</summary>

**Simon**: it was recommending. Yeah. I mean it was just like you know he was reading about like and I did get permission. I just like I don't think anyone expected to be good enough and just like okay it's this this thing is working and then I ran the back of the envelope math on what it would cost to do this for everyone like all the users. This is a company called Readwise. So it's like articles that you save and then and insert later. And it was going to cost 30 grand a month. And this was a company. It's a bootstrap Canadian company. They spend about five they at the time they were spending about 5k a month on all the other infrastructure combined. So it just it didn't the you know fundamentally in a company if you're doing an investment you have have to run some gross margin on top of whatever you're paying right and it just didn't line up. Um and so we just didn't ship it. I worked on I you know tuned to autovacuum on postcress or something like that which is a good pastime and then you I just couldn't stop thinking about why it was so expensive to store all of these vectors that we were using for the recommendations and I just sat and did the napkin math one day of like can we just use it all in S3 and do some clustering and then organize the files and just the way and it's like maybe you could build that and then one day I just kind of said [ __ ] it and did it and like sat down and started started to like to write it out. Um, and I spent the summer of of 23 just hammering my head against the wall trying to find an approach where I could get the latency that I wanted. Um,

</details>

**Gergely**: 因为 **S3** 的问题在于虽然可靠性极高，但它的时延通常在几百毫秒级别，对吧？

<details>
<summary>Original English</summary>

**Gergely**: because the problem with S3 is it has really good durability, but latency we're talking hundreds of milliseconds, right?

</details>

**Simon**: 是的。在 S3 上请求一个 256KB 或 512KB 大小的对象，P99 时延在 200 毫秒左右。

<details>
<summary>Original English</summary>

**Simon**: Yes. The P99 on a uh 256 or 512 kilobyte object on S3 um is around 200 milliseconds. Um,

</details>

**Gergely**: 你特意提到 P99，因为在大规模分布式系统设计中，你必须关注 P99 时延，而不是 P50。

<details>
<summary>Original English</summary>

**Gergely**: and and you're saying P99 because like when you're talking large scale, you want to care about the P99, right?

</details>

**Simon**: 没错，因为在 S3 上你通常不是只发一次请求，而是会并发或串行发起多次请求。

<details>
<summary>Original English</summary>

**Simon**: Yeah. I think when you're designing a system, you want to optimize for the P99. And especially because when you're designing a system on on S3, generally in every roundtrip, you're not doing one request. You're often doing lots of requests, right?

</details>

**Gergely**: 也就是说，多步操作会非常快地把整体时延推高到 P99 甚至更糟。

<details>
<summary>Original English</summary>

**Gergely**: You're going to hit the P99 real quick.

</details>

**Simon**: 没错。如果你在 S3 上检索一个树状索引，获取树的上层需要 200 毫秒，获取中间层需要 200 毫秒，最后获取叶子节点又需要 200 毫秒。所以在设计系统时，你必须把 P99 甚至 P99.9 作为硬性约束，尽可能减少往返请求的次数。

我画出了方案草图，尝试了多种方法，最终在 2023 年 7 月跑通了一个端到端可行的原型。后来我重写了大概两次，并在同年 10 月发布了最初的版本。

起初这只是我个人的一个兴趣项目，我压根没想过要拿着它去融资 1000 万美元成立一家公司。我当时甚至都不知道风险投资（VC）是什么。我只是疯狂地着迷于解决这个问题，因为我很清楚，如果我不做，其他人也迟早会做出来。

第一个版本极度简单，这符合我务实的工程风格。我甚至没怎么去读 LSM（日志结构合并树）学术论文，因为实现那些太耗时间了。我们采用的最简单的架构是：对向量运行聚类算法，将聚类后的结果分别存入名为 `cluster_1`、`cluster_2` 的文件中，再维护一个包含这些聚类质心的文件。搜索时，先下载质心文件，找出最近的 $N$ 个聚类，然后再去下载对应的聚类文件。在这个过程中，为了控制成本和提升性能，我们只做了一些针对 JSON 文件的合并优化。

至于怎么让它变快？在最初的版本里，我甚至没有写任何专用的缓存层。我只是用 **Nginx** 作为一个反向代理挡在 S3 前面，用它来缓存 S3 对象。

<details>
<summary>Original English</summary>

**Simon**: Exactly. So, it's like if you're navigating a tree on S3, right? It's like, okay, you get the upper layer of the tree 200 milliseconds. You get like another layer of the tree 200 milliseconds. You get a bunch of leaves of the tree in 200 millonds. So in aggregate you have like you want to look at the P99 probably even the P999 to design the system properly because you will need to minimize the number of round trips that you had to make. So, I just sat and sketched that out um and tried a bunch of different approaches and then and then finally in in in July of 23, I I I got something end to end that seemed to work and then rewrote it probably twice and then released it in in October of of 23 based on um based on just that that summer of of of working through it. And then you kind of you built it on on top of S3 because I guess durability and and all of and just really good. How did you make it fast? We didn't in the beginning or I didn't in the beginning. Um it was just me at the time and it was really like it was it was it was a project. It was not a company. It was not it was it was it was to satisfy a curiosity. It was not I did not set out to do this like I'm going to go like raise $10 million and do like I was like I barely knew what a VC was. Like I was like I just had to do this thing and I was so focused on doing it. so clear to me that if I wasn't going to do it, someone else was going to do it and I just became fully obsessed that summer with it. And so the first version was the simplest possible thing. I think I'm a very pragmatic person like I I didn't get buried. I barely read any like of the literature on LSM. I sort of like you know read a bunch of it just like got the basic idea barely implemented that because that would have been too much time. It was the simplest possible version of what it could be. Like really what you have to imagine is that the simplest way you could do this is you run some clustering algorithm on the vectors. You get the clusters and then you put the clusters in files. The cl the files are called cluster one, cluster two, cluster three and then you have another file called centroidids of the clusters and then you do the search by downloading centroidids looking at the centrids and then downloading the n closest clusters. There was a few optimizations around merging some clusters that were JSON in files and so on just to like control some cost and some performance but that was basically it and then getting that to scale. That was the first version. And then how do we make it fast? Well, I didn't even implement a caching layer. I just put the reverse proxy in front of S3 with Engine X and then had it

</details>

**Gergely**: 看来你终究还是搞明白了什么是反向代理。

<details>
<summary>Original English</summary>

**Gergely**: know what a reverse proxy is.

</details>

**Simon**: 确实（笑）。这个架构里，反向代理通过缓存所有的 S3 对象来加速读取。为了清理缓存，我们甚至直接通过 shell 脚本调用 `xargs` 并在 Nginx 的缓存目录结构里进行硬删除。最初它就运行在一个跑着 tmux 实例的单台机器上。我想看看有没有人会对这个感兴趣。

<details>
<summary>Original English</summary>

**Simon**: I like I do know what it is. I just still don't know what what the reverse is about. But anyway, um the reverse the reverse proxy reverse things. Um the the performance in this case um maybe that's what it's about by caching right all of the all of the S3 objects. It again it was the simplest like it's like I'm just going to put that in front. I knew how to configure engine X like I've written more enginex Lua than u than a lot of engineext Lua very good software. um just had that cache in front and then the way that I would do things like deleting in the cache was just like shell out to XRX and just remove like things in the in the cache and reverse engineer the directory structure on engine X and that's what we shipped and it was just running on a single server in a T-Ox instance. I was like okay let's see if anyone gives a [ __ ] Yeah.

</details>

### 拿下 Cursor

**Gergely**: 这是一个非常硬核且务实的 side project。那 **Cursor** 是怎么参与进来的？因为当我跟 **Cursor** 团队聊到他们后台的扩展和技术选型时，他们告诉我，他们以前用过 PostgreSQL，但性能不行；后来迁去 AWS Aurora 托管服务，也遇到了极大的痛点。最后他们改用了 **Turbopuffer**，并且运行得非常好。他们还说他们是你们的第一个客户。这简直不可思议，因为 **Cursor** 那时候已经有相当大的规模了。你们是怎么认识的？

<details>
<summary>Original English</summary>

**Gergely**: So so far I mean this is kind of like cool engineering and like a cool side project and like a bunch of novel ideas and I you know like I think just some hardcore engineering. How did cursor come into play? Because like when I learned about Turbopuffer, I was talking with Cursor about like how they built their their back end, their database, how they scaled, and they're telling me all these migrations and they were telling me like, oh yeah, so we we were on Postgress, but it didn't no they did something else in Postgress. It didn't even work that well. They went to AWS Aurora, which is managed service of Postgress, and it didn't work well, which is very surprising. And they're like, "Oh, yeah." And then we went to this thing called Turbopuffer, and they worked well. And I was like, what's turbuffer? And they're like, oh yeah, turbopuffer. I think I think they said like we were one of their first customers. And this never computed to me. Curser was already massive at that point. How did you meet the folks? And how did they become would were they the first customer? One of the first.

</details>

**Simon**: 他们是我们的第一个客户。

<details>
<summary>Original English</summary>

**Simon**: They were the first customer.

</details>

**Gergely**: 真正的第一个？

<details>
<summary>Original English</summary>

**Gergely**: The first the first.

</details>

**Simon**: 是的。

<details>
<summary>Original English</summary>

**Simon**: No.

</details>

**Simon**: 他们是在我把项目发在 Twitter 上之后主动联系我的。我当时发推说：“嘿，我做了一个新玩意。”说实话，我当时已经对这个项目感到厌倦了，我整整写了一个夏天，不知道有没有人在乎。我当时甚至想，如果没有人在乎，我就不干了。

当时它就跑在 GCP 的一台 8 核虚拟机的单台主机上。我想，如果有客户要把它用在生产环境，我再去搭多节点。这是最极端的 MVP 方式。任何在传统数据库公司工作的人，可能都因为过于高傲而不敢发布如此简陋的系统，但我是把它当成一个 SaaS 项目在迭代。如果有人开始用，我们再用正确的方式重构。我知道怎么去运行高可用服务。

在 Twitter 上，我宣传“存 100 万个向量只需要 1 美元”。而当时市场上其他能用的方案，价格大概是每百万向量 100 美元左右。

<details>
<summary>Original English</summary>

**Simon**: Um they they they reached out um after I just launched on on Twitter. I was like, "Hey, I built this thing." And frankly it was like in I exact you it was like hey launch this thing and to me I was like I am so sick of working on this like I was like I've been working on this all summer I don't know if anyone cares I only want to work on this if anyone cares. Let's put it on Twitter again single Tox instance on a 8 core node somewhere in GCP. I was like if someone goes to prod I'll I'll set it up properly on multiple and like I'll just block on that but let let's see if anyone cares. It was like the MVP of MVP. Anyone who's actually worked in the internal on databases would never have had like would have had too much pride to ship anything like that. Um, and I've just, you know, I've worked on I was just releasing it like a SAS project. Why can't you work on a database like it's SAS? I don't, you know, it's like if anyone uses it, we'll do it properly. I know how to run software with a lot of nines. Um, but it was not a proper LSN like it was very very it was the simplest version of what it could be. And then I released on Twitter. I was like, "Yeah, you could do a million vectors for a dollar." And before that, I think the the cheapest was maybe $100 per million for something that actually worked.

</details>

**Gergely**: 嗯。

<details>
<summary>Original English</summary>

**Gergely**: Yeah.

</details>

**Simon**: 我知道它虽然简单但很可靠，它的状态是不变且落盘的：即使你关掉所有虚拟机，数据也不会丢，因为写入是直接提交到对象存储中的。

**Cursor** 团队看到后联系了我。当时他们团队大概只有 8 个人。我猜他们当时面临的困境是：所有向量都存在内存（DRAM）里，随着用户规模迅速扩大，这种模式的单位经济学（Unit Economics）彻底崩溃了。为什么没有人在 S3 的基础上构建数据库呢？对于用户正在活跃编辑的代码库，可以把向量保存在内存中，而对于其他绝大多数不活跃的代码库，直接扔进廉价的对象存储，需要时再加载进内存。这太有说服力了。

<details>
<summary>Original English</summary>

**Simon**: Um, and I knew it was reliable, right? I knew like I had these invariants like if you shut down all the VMs, like no data is lost, like all the rights are committed directly to object like it has all the same invariants it had today. Um and cursor reached out and knowing them now I'm sure at the time the cursor was maybe eight people and knowing the founders now I am sure that they had sat at the dinner table one day and we're like the unit economics of what we have right now where all the vectors are in DRAM are not working why hasn't anyone built it where we can put it in S3 and the actual code bases that are actively being used we can put in memory and everything else just sit in opic stores and then we just hotload it in and out of the cache

</details>

**Gergely**: 确实如此。只要用户打开项目，几秒钟内把向量加载到内存，查询速度就和全内存数据库一样快，但成本却低了几个数量级。

<details>
<summary>Original English</summary>

**Gergely**: makes so much sense right you open the codebase few seconds and it's in RAM and then the queries are as fast as anything else. It made so much sense. So I mean at the time they were if you look at some of Aman one of the co-founders early tweets he talks about uh using S3 for KV caching and things like that which barely anyone is still doing even though

</details>

**Simon**: 没错，价格相差悬殊。

<details>
<summary>Original English</summary>

**Simon**: um the economics

</details>

**Gergely**: 这在业界非常罕见，但我认为这代表了未来的趋势。

<details>
<summary>Original English</summary>

**Gergely**: yeah price wise yeah it's and it's it's very it's very uncommon and I think it will happen right but they were ahead of their time

</details>

**Simon**: 他们当时也在考虑要不要自己写一个这样的数据库，正好这时候发现了 **Turbopuffer**。我们交换了邮件，接着我直接飞去了旧金山。我当时对 B2B 销售一窍不通。

不过我现在非常热爱 B2B 销售。当时我只想去帮他们解决账单算不过来的问题。当我去到他们的办公室时，他们正在激烈讨论一个 PostgreSQL 的技术问题，也就是 AWS Aurora 相关的痛点。

<details>
<summary>Original English</summary>

**Simon**: and they I think they were I don't know if they were thinking of building it themselves I think that's quite likely um and they found Turboper and it just perfectly pattern matched into that again I don't know if this dinner conversation happened or if this was just inside Harvey's head. Um, but it pattern matched something and so we exchanged a bunch of emails and then something compelled. I didn't know anything about B2B sales. Now I love B2B sales. Um, I didn't know anything. I was just like I just want to help them cuz they they were they had some unit economics that didn't line up. So I just went to San Francisco, right? I live in Canada. I went to San Francisco and I showed up at the office and when I showed up at the office they um they were having some Postgress problem that they were discussing. Yeah, the AWS aurora problems. Yes.

</details>

**Simon**: 我当时问：“你们开启 `PG_Analyze` 了吗？”他们说没有。我说那我们先把这个跑起来。结果发现问题非常经典：自动清理（Autovacuum）运行频率不够，导致很多本该走索引扫描（Index Scan）的查询退化成了全表扫描（Seq Scan）。我的数据库工程基因立马动了，帮他们排查了这一堆问题。

我认为这为我们之间建立了足够的信任：如果这家伙对如何调优关系型数据库如此在行，他写的向量数据库大概率也靠谱。

同时，我邀请了我在 **Shopify** 时的老同事，也是我认为最强的工程师 Justine 作为我的联合创始人加入。她加入后干的第一件事，就是用基于文件的轻量缓存替换了 Nginx 代理缓存。这让我们的 S3 架构变得更加坚固。

就在那天晚上，**Cursor** 决定全部迁移到 **Turbopuffer**。他们在大概一两周内完成了迁移。我们帮助他们把向量数据库的账单降低了 95%。

<details>
<summary>Original English</summary>

**Simon**: Yeah. Early on. And I was like, "Oh, do you guys have PG analyze?" And they said, "Oh, no, we don't." I let's let's get that going, right? Let's look at it. And it was the same thing as it always is with Postgress, which is autovacuum hadn't run enough and so they had all of these like going to heat when they should be doing index scans and blah blah blah. So, we were talking about all of that. And so, it's just helping them, right? It was like my, you know, my database genes just like kicked in. And I think this built enough trust with them that okay, well maybe if he knows how to help us with the database, maybe he also would know how to build one. And um at this time I'd also approached who I thought was the best engineer who ever worked at Shopify, my co-founder Justine. um and she'd come on and the first thing that she did was um remove the reverse proxy enginex cache with a file-based cache just a direct cache which again great like the S3 thing worked um and so she was online she was starting to work on it and um and cursor cursor cursor then that night was like okay well we're going to migrate and so they migrated everything over the course of like a week or two after that um but cursor was a small company back then right yeah and they were they just in the beginning of their massive rapid growth. Exactly. And I I told them that I was going to reduce their bill by 95%. And I did like we did. Justine and I did. We like they came on and their last bill with their previous vendor and the first bill with us, it was 95% lower. Yeah. And you're you're nice for not saying vendors, but I I can say talks to them and and it's in the deep dive about cursor. It was it was a it was Aurora specifically. Uh so

</details>

**Gergely**: 这是真正的降维打击。

<details>
<summary>Original English</summary>

**Gergely**: this was this was not this was not Postgress. No, this was a

</details>

**Simon**: 确实。他们之前在其他平台上的主要痛点是稳定性，虽然价格也是一个重要因素。这成了我们最宝贵的种子案例。

<details>
<summary>Original English</summary>

**Simon**: it was a different one, but it's probably still in the write up. We don't we don't need to name names, but uh yeah, but they were the reason they went there is reliability was their main main pain point. I'm sure the unit economics would have been there, but yeah, this was and then what Swallow told me is he said like look like there's a few things that we did never ever do and he said one of them you should never ever bet your business on a tiny startup where you are their only or biggest customer except for Turbopuffer and he said I love love those guys. So I guess it just comes to show that even in your case like to me what this story is shows is is you can do things when you build highquality things and you're pushing for things good things can happen and on the other side of cursor when you're a startup it's okay to take sometimes irrational risks when you have conviction and it sounds to me that you gave them conviction by showing up in person by helping them by showing that you know you know your stuff like you suddenly brought in your your 10ish or eight years of Shopify experience and your curiosity and They probably took a risk because of that, not because you were some, you know, random vendor. They probably never done that. So, fast forward today, uh, Turbopuffer is now a lot bigger. You're you're working on some some some cool things, but you have this very interesting business where for you CPUs are important, right? You run on mostly CPUs. And you told me a story over dinner yesterday that uh you met Jensen uh and Jensen he really wanted to sell you on GPUs. Can you tell me how that meeting went?

</details>

### 与黄仁勋聊天

**Simon**: 你是指**黄仁勋**（Jensen Huang）吗？

<details>
<summary>Original English</summary>

**Simon**: Um yeah, Jensen Hong, right?

</details>

**Gergely**: 是的。

<details>
<summary>Original English</summary>

**Gergely**: Yeah. I just I never met uh I'd never met uh Jensen before. We were we were at an event at uh at at Nvidia and we were just doing um presentations in a big HQ. Super impressive.

</details>

**Simon**: 我们当时在英伟达总部参加一个闭门活动，很多公司代表在台上向英伟达高管层介绍自己的业务，探寻合作机会。我那天心情比较放松，上台后我说：“大家好，我是来自 **Turbopuffer** 的 Simon。如果大家对我们这个名字感到好奇——不用担心，如果数据库这条路走不通，我们随时可以转型去卖电子烟（Vapes）。”

<details>
<summary>Original English</summary>

**Simon**: Yeah, exactly. they've invited a couple of companies to go and and um and and and talk about um uh talk about our businesses and how we can partner with Nvidia and so on. And I I don't I I don't know. I was like I think I was in a goofy mood that day. And so I went up on on stage and I said, "Um, hey, I'm Simon from from Turbopuffer." And uh and yeah, if you're wondering about the name, it's like if everything goes south, we can always pivot into vapes.

</details>

**Gergely**: 哈哈。当时台下坐着谁？黄仁勋本人在场吗？

<details>
<summary>Original English</summary>

**Gergely**: [laughter]

</details>

**Simon**: 黄仁勋就在台下，旁边是他的高管团队。我讲完那个玩笑后，他直接对我说：“看你们这 PPT 讲得，也许你们确实应该转型去卖电子烟。”（笑）我当时愣住了，不知道怎么接话，脑子一抽问道：“老黄，你抽电子烟吗？”他没有回答我的问题。

活动结束后，我们团队的人在群里发：“Simon 刚才在台上问老黄抽不抽电子烟。”

在去英伟达之前，团队曾反复叮嘱我：“Simon，记住，千万不要在老黄面前提 CPU 这个词，那是他们的禁忌词。”但在交流时，我根本管不住自己的嘴，一开口全是 CPU：“我们太爱 CPU 的 **AVX-512** 指令集了！**SIMD** 加速简直太棒了！而且 CPU 供应非常充足，我们根本不需要 GPU 就能跑得飞快！”虽然我没有直接说“我很高兴我们不需要英伟达的 GPU”，但老黄显然听进去了，并对我们产生了一些兴趣。

<details>
<summary>Original English</summary>

**Simon**: It was it was Jensen and then I don't he has like I don'\''t know if it's just 50 direct reports or it was like you know it was there was it was Jensen and then a bunch of the um like Nvidia Nvidia leadership, right? Um cuz you go there and then you talk about that you find opportunities to partner and work together, right? And so I said, "Yeah, you know, so plan B could be that we could pivot into vapes." And then he said, I was already nervous. He said, "Judging by your slide, maybe you should." [laughter] No, he did not. [laughter] And and [gasps] I didn't know what to say back to that. So I said, "Well, Jensen, do you vape?" [snorts] [laughter] He didn't he didn't answer the question. [laughter] And then someone um someone on the um someone on the on the team um wrote to the whole company, Turop Puffer Company, Simon just asked Jensen if he vapes. Um, and then you know this is this is a great start, right? And um, and then the team had team team had sort of talked to me beforehand. I was like, Simon, we got to make sure we don't say the C-word. We can't say CPUs. And so I just couldn't stop talking about CPUs. I was like, AVX 512 is so sick. Like we love SIMD and um, like we we we like there's so many CPUs. They're so easy to get. like um it's just a riot in CPU land. Like you know I I don't think I stopped short of saying I'm so glad I don't need GPUs. [laughter] But but it was just it I just couldn't stop talking about CPUs. Yeah. And so you know Jensen took an interest in that. Yeah. So who who knows like I'm sure you made you made a memorable impression. Maybe he made it his mission now to like at some point get you guys onto GPUs. But speaking of CPUs, can you tell me a bit what you're seeing inside of the hypers scale, the cloud providers? You're now in AWS, you're you're in GCP, you're on Azure. What I would think naively is there's a GPU shortage and when I talk with inference companies, they are and and and AI labs, they're just getting whatever they can do. I would think getting CPUs is should be easy. Is it?

</details>

### 云端算力之战

**Simon**: 事实并非如此，现在连 CPU 也很难拿到了。

<details>
<summary>Original English</summary>

**Simon**: No, it's not anymore. Why? What's happening? Can you tell us about dynamics on on on the why and what you've learned? Yeah. So, I think that GPUs will probably continue to be scarce. Like, I don't know, maybe there's going to be some surplus. I I refuse to speculate too much about the macro, but I think as as RL is becoming a very very large amount of the workloads that needs a lot of CPUs. So, the labs are sucking up a lot of CPUs because you need CPUs to be like, okay, we need to like teach this model how to how to search. We need to teach it how to use GP. We need to teach it how to boot up bash. We need it needs to run real things and learn from that takes a lot of CPU.

</details>

**Gergely**: 为什么？发生了什么？

**Simon**: 随着**强化学习**（RL，例如 OpenAI 的推理模型）成为主流，这些工作负载需要极其庞大的 CPU 资源来进行模拟和搜索。大模型在学习如何使用工具、运行 Bash 命令、在沙箱中编译和调试代码时，背后都在消耗大量的普通 CPU 算力。

此外，AI Agent（智能体）的运行也高度依赖 CPU 来处理通用逻辑。这使得 CPU 的需求曲线疯狂右移，导致大型 AI 实验室正在疯狂囤积 CPU 算力。这反过来又对云服务商的 CPU 供应造成了巨大的压力，连带 NVMe SSD 也变得极度紧俏。

很多时候，这些基础架构的算力资源被牢牢绑定在了专用的 GPU 服务器集群中。在大厂之间，关于 CPU 和存储资源的分配争夺战已经白热化。我们甚至要和我们的客户一起，去和云厂商争夺 CPU 实例的配额。

<details>
<summary>Original English</summary>

**Simon**: Um and so I think as we RL is consuming a lot of CPU and then also just all of the agents are running on CPUs, right? They need to do all kinds of very general purpose things on a CPU and so as as as the demand curve is sort of shifting to the right and it's becoming more and more applied and that feeds back into RL by the way, right? because as things become more applied like oh the models are not that good at CAD or ship building I don't know and then you know you have to spin up even more RL environments to do that so I think that's what we're seeing and so we're on the other end of that needing these CPUs we need a lot of NVME SSDs as well um and a lot of this right now is tied up in DRAM right of of where like you need a lot of that also for the GPU servers um but I would assume that it gets a lot worse before it gets a lot better on the on the CPU side um and I think even the big companies are fighting amongst each other, right, to get the allocations and even we, you know, we're selling to companies that we also fight for CPU with and against, right? It's uh it's it's it's really difficult and so you write things to try to make sure you get these CPUs as f fast as possible.

</details>

**Gergely**: 昨晚我在你和团队举办的晚宴上，你们的一些大客户（比如一些 AI 实验室和头部初创公司）也提到了这个情况。他们甚至到了买不到更多算力的地步，哪怕他们愿意签最长期的合同。对于外界而言，这种云端底层的算力厮杀是完全不可见的。

**Simon**: 确实如此。我们必须和云厂商密切沟通，弄清楚哪个可用区（Region）还有电力额度，因为电力配额直接决定了他们把新的 CPU 服务器运到哪里。

我们比较幸运的一点是，**Turbopuffer** 的架构设计得非常轻量灵活，我们对具体的机器类型（SKU）没有任何强依赖。我们不需要特定的某一款 CPU 实例，我们可以在 GCP 的 **C4**、**Z4D** 或者 ARM 架构的 **C4A** 实例上运行得非常好。

<details>
<summary>Original English</summary>

**Simon**: Exactly. And I mean you you work with the clouds right you work with them to talk about which regions have um have CPU which regions are getting it comes down to power right of like okay well where is the power which is generally where they're going to ship the new CPUs. Um and so we have to work with some of our biggest customers on that. So these are real constraints right that are that are making our way to us. We're just very fortunate that it's very easy for us to run lots of turbuffer clusters because all we need are like a few CPUs and NVME SSDs and then S3 and then we're in a good place. But there's lots of changes that we can make even to the architecture um to try to protect from from a lot of this. Now I'd rather spend that engineering effort on other things but we are very very good at using a lot of very different SKs, right? So we don't need everything to be a particular CPU or instance type. We can run with many even many different types of machine types. Um Q meaning that's the it's a fancy name for like the different machine types. Yes. Exactly. Right. Like you know C4D or I AG or whatever they're called. What's your favorite one? Um we really like right now the um C4s on uh GCP. GCP. Um the Z4Ds are also performing really well um now that we've done done a bunch of of um of optimizations to them. Um those are really really great machine types. Uh we really like those. Um and then the ARM C4As as well um on on GCP. Um we like those. But I think that in general like when you're yeah when you're small it's very easy to suck up a bunch of but at Shopify I was also part of you know deciding ahead of BFCM right a few months out you have to tell the cloud providers how much you're intending to use. do commits on all of that, right? The the clouds are not infinite as they seem when you're small.

</details>

### 常识与资本

**Gergely**: 另一个获取资源和行业公信力的方式显然是风险投资。比如融个几千万甚至几亿美元。你的客户很多都融了巨资。然而在很长一段时间里，你甚至没有宣布过任何融资消息。你是如何看待风险投资的？因为我觉得你的视角和硅谷主流的“融资竞赛”截然不同。

<details>
<summary>Original English</summary>

**Gergely**: And one way, of course, to like get like infrastructure and and also just like credibility is venture capital. If you raise $100 million, a billion dollars, some of your customers just raised $2 billion. Actually, I talked with them yesterday. You know, it gives you credibility, gives you cash, you can pay for this thing. Your specific Turbopufferers relationship to venture capital seems very interesting. I never heard you announce a raise until m maybe just very recently. Can you tell me how you and and you told me that when you started this thing, you didn't think too much outside of just building some cool stuff. How did you think about venture capital and how do you think about raising because again I feel you have a very fresh and different perspective than what which is typical inside of Silicon Valley.

</details>

**Simon**: 要理解我的资本观，必须回到 **Turbopuffer** 创立的起点。当时我承诺 **Cursor**，我和 Justine 能把他们的账单降到每月 4000 美元。这个数字完全是基于极简架构下机器物理极限的粗略估算。虽然当时我们的软件版本还很简陋，但我始终坚信一点：**极致的简单（Simplicity）高于一切**。

我们在很多场合聊过，什么样的软件生命周期最长？为什么在一家公司长期深耕的工程师写出来的代码最扎实？你在 Uber 待了很久，我在 Shopify 待了八年，我们都见证了：简单永远能击败复杂。

当时我甚至不确定这是否是一个值得风投介入的项目。因为一旦你拿了风投的钱，无论开会时大家笑得多灿烂，投资人都在期望你在特定时间内交出巨额的回报。而风投的钱背后，是加拿大养老基金等一层层需要交代收益的社会资本。我当时觉得这可能只是一个非常细分、垂直的利基市场，根本算不上什么估值十亿美元的独角兽。

所以我当时的想法非常朴素：我看着 **Cursor** 的账单，再看着我的 GCP 账单，作为一个丹麦人，我的商业常识告诉我：前者大于后者，公司就能活下去。

<details>
<summary>Original English</summary>

**Simon**: Yeah. So I think to to understand my how I think about capital you have to go back to the the beginning of Turbopuffer, right? where I promised cursor that Justine and I could get their bill to 4K a month. And this was based on some very rough napkin math on, okay, if if Turbopuffer was a better implementation than it currently is, then it should cost this much. And that's the pricing we ship with and that's what we guaranteed um guaranteed cursor. Um but the software was not that good. Like it was very reliable, but it was very simple, right? And that's like a core engineering principle of me is simplicity above everything. Um you and I have talked before about how software that ages well and some of the advantages of seeing be having long tenures inside of companies. You had a long tenure at Uber. I had a long tenure at Shopify. So you see simplicity just almost always wins. Um and at the time I was not convinced whether this was a venture scale opportunity because I understood that if you take venture capital no matter how many smiles there are in the room everyone's sort of expecting that you have to earn a big return on that on some timeline that makes sense to everyone involved and everyone involved are you know pension funds in Canada like that it's like it there's like a whole stack right of of of people that that need to so at the time I was like I don't you I don't know if this could be a billion dollar company. I didn't know that in the very very beginning. Um it wasn't completely clear to me. It felt like a very niche kind of product, right, to build this particular search engine. Um and that was completely fine with me. So I you know it's it's it was fine. And so then I just I just looked at the cursor bill and I looked at my GCP bill which is what we started on. and you know as like a you know dumb Danish person who's just like okay like this number should just be lower than the other number.

</details>

**Gergely**: 这是最经典的商业常识 101。只要有利润，你就是安全的。

<details>
<summary>Original English</summary>

**Gergely**: Yeah, that's sort of like you know and it's just I don'\''t think I'\''d spend enough time in San Francisco cuz I think the money over here it works a little bit differently. Um that's just that's all I knew. You you were doing business 101 as as long as you're making a profit you're good, right?

</details>

**Simon**: 确实。我和 Justine 当时就没想那么多，只是疯狂去优化系统，直到算得过账。如果我们能拿到更多客户的订单，我们就能给自己发工资。

因为我当时在硅谷没有任何人脉，根本不认识有钱的 VC。直到 2024 年 1 月，我想邀请我在 2012、2013 年参加 IOI 竞赛时认识的一位北马其顿国家队的前队友 Boyan 加入。Boyan 在技术上强到被当时北马其顿国家队称为“神”。我很想招他，但我付不起他的薪水，那时我和 Justine 已经有半年没给自己发过一分钱工资，并且个人账户已经为公司垫付了几万美元的云厂商账单。

于是我联系了我在硅谷唯一认识的一个投资人 Locky，对他说：“我想让研发速度跑得更快一点。我们能融个 70 瓦（70万美元）吗？”我当时盘算着，这笔钱足够我多雇两个优秀的工程师干到年底，我和 Justine 继续不拿薪水，另外留出一点云服务器账单的缓冲空间。如果在年底之前，我们没有跑出产品市场匹配度（PMF），或者发现这其实不是一个足够大的商业机会，我们就直接把公司关掉，把剩下的钱一分不少退还给你。

我跟其他一些硅谷的 VC 聊过这个想法，他们听完后都吓坏了。在西海岸的投资人听起来，这似乎代表着“缺乏野心”。

<details>
<summary>Original English</summary>

**Simon**: Yeah. It was like I'm I'm not kidding in this exaggeration that it was just like that just made sense to me that Justine and I were just going to go optimize this until these numbers were roughly equal. And maybe if if if we could get some other workloads, we could start paying ourselves. But that was like very much the philosophy at the time. Um because I didn't know if I could go raise a bunch of of of money. I didn't know anyone who had the money. I I didn't have any relationships. Um you were an absolute outsider to the I was I was an outsider. I was like an outsider squared, right? I grew up in Aus, Denmark and I um I then moved to Ottawa, Canada. So it's like I'm an outsider to Canada and in Canada I'm an outsider to San Francisco. So I was just thinking about this from first principles like oh you're a venture capital you need this return you need it on this timeline. I don't know if I can deliver that yet. I would need more data to decide that because I want to like I kind of want to keep working on this and now I have to get to this point for it to not be a failure. Um in in in January then I uh there was a person that I was at II with in in uh in 2012 and 2013 and his name is Buen and he was on the North and Macedonian team um at II um and he was he's he was really good. He was so good that the North Macedonian team called him God. Um I don'\''t know why but that was what he went by and he was yeah he was very good grew up and and I really wanted to work with Buen but I couldn'\''t afford to work with Boyan [laughter] um and he was very much like this is what I can live off like you know I just like I want to build this date like that would be like this is what it can be but at this point Justine and I hadn'\''t taken a salary for like 6 months and we'\''d already we'\''d already spent like tens of thousands of dollars on like on GCP bills and all of that and I was like I don'\''t think we can I don'\''t think we can we we can do it. And so I had met one one individual in in Silicon Valley uh his name is Locky and it just I ended up just calling him and saying hey I kind of want to learn a little bit faster here. Can I can we raise like 700K? That's like what I wanted to raise. So it's just like I want to have like two engineers for the rest of the year. Justine and I still don't need to be paid and then a little bit of buffer room. It's like this is what I need and if this doesn't have PMF and is a big opportunity by the end of the year, I don't think we're going to bother and we'll just shut the whole thing down and we won't have it taking a dime. We'll return everything to you. Um I think there was the first time you heard anyone say it like that. Um and um I told some other VCs that at the time and that was terrifying to them. I think to someone on the West Coast this sounds like you have low ambition or something like that. M

</details>

**Gergely**: 嗯。

<details>
<summary>Original English</summary>

**Gergely**: um

</details>

**Simon**: 但这只是我的底牌。当我不懂一个游戏的游戏规则时，我习惯于把所有底牌公开亮出来。

后来，我们顺利招到了 Boyan，并且公司在同年晚些时候实现了盈利。团队规模也逐步扩大。关于后续为什么还要拿更多的钱，我认为在商业逻辑上，融资通常只有六个合理的理由。

第一是为研发（R&D）提供资金，这符合我们第一笔融 70 万美元的逻辑。第二是为增长（Growth）注入资本。第三是为了创始人虚荣心（Ego）——这在硅谷极度流行，大额的融资数字、媒体的头条报道，但这是一条非常危险的道路，因为你在无意义地稀释所有员工的期权，并强行抬高了后续加入的员工获得收益的门槛。第四是回报员工。当公司走上一条漫长而艰苦的道路时，你需要给早期员工提供一定的流动性（Liquidity）套现机会，而不是让他们干等好几年去指望一个虚无缥缈的 IPO，这也是我们后续决定接受新一轮融资的核心原因。第五是达成关键的战略伙伴关系。第六是进行并购（M&A）。

对我们而言，我们非常清楚自己拿钱是为了第一点（研发）和第四点（回报员工）。

<details>
<summary>Original English</summary>

**Simon**: and to me it was just like I I don't know it just came from a when I don't know how to play a game I just play with open cards like this is how I see it and so I we were it was very clear to us that we wanted to do this and but also it became clear to us that we didn'\''t want to just like keep working on this unless it could become big and we were starting to develop conviction conviction that this actually become really really big and so we we we did that and hired Buen and then became profitable later that year um and then just continued to hire and then it's like to raise more money, you need sort of there's six reasons to raise capital. The first reason to raise capital is to fund R&D. Mhm. That was the reason that we raised capital in January because we funded R&D with a lot of our own, you know, opportunity cost and not taking a salary and then paying the bills ourselves. Um, but we wanted to learn a little bit faster and so we hired Buen and Morgan as the first engineers. And then the second reason to raise capital is to fund growth. you've you you've built something and you want to tell the world about it and you want to spend more capital to do that. Um the third reason to to to raise capital is for the founders'\'' ego. [snorts] Um it's a very popular appreciate the honesty. It's very popular, very very popular, right? big numbers, lots of press, like um and I think this is a very very dangerous reason to raise money. And I wish that it was more talked about because you're diluting all of your employees when you do it. You are um setting a certain price for future employees and their upside. It's it's it for some people it can become a status game and that's not what it's about. We're here to build a big business together and this is not a reason to raise money. Um, but I I do think that it happens. Um, the fourth reason to to to raise capital is to reward your employees, right? It's a you're on a very long journey and you want to work with the best people in the world and by definition there's not that many best people in the world. So, you want to reward them. Um, that was the reason that we took more capital in December um was to allow the employees to liquidate as some of their equity um instead of waiting for some like event like an IPO or something like further out. Um the fifth reason to raise is for a strategic partnership. There are strategic partnerships that have been made in this in this city that have made companies. Um and um the six reason to raise would be do doing M&A or or something like that. But it's like you have to be very honest about what reason you are raising in those six. First reason we raised was one and second reason we raised was four. Um so which which ones? The first reason to raise was R&D. R&D and the second reason was um to provide liquidity to the employees employees. Yep.

</details>

### 远程团队管理

**Gergely**: 这是一种非常务实且健康的视角。在结束之前，我想问问你们独特的分布式远程办公模式。我看到现在很多做 AI 相关（无论是算力底座还是上层应用）的公司都极度强调一定要在旧金山或伦敦搞集中式的线下办公，因为线下能带来极其高效的迭代速度。而你们从第一天起就是全员远程，并且至今依然如此。你们是如何让这套机制良好运转的？有哪些“Puffer 独家秘诀”？

<details>
<summary>Original English</summary>

**Gergely**: I I think it's a it's a nice and healthy way and I think yeah the ego part we don't talk about and the identity and especially the closer you are to to tech ecosystems where a lot of people are raising it it will be part of it. As closing I I wanted to ask you about the way you have a remote culture these days. I'm seeing it especially for companies that do anything with AI, may that be building AI infra or or or just AI products. A lot of them prefer in person having a HQ often times in SF or wherever your headquarters may that be London or somewhere else because you often these companies often find that they have faster iteration. Uh it's just fewer layers cut in between and of course speed is is very very important. You have started full remote and you're still full remote. how is it working? Uh, and what kind of quirks or like or turbo ways have you found to to make this work better?

</details>

**Simon**: **Turbopuffer** 创立于 2023 年。那时候绝大多数基础架构公司都默认支持远程。而且在 **Shopify** 时，我们的基础架构团队从一开始就是分布式远程的，因为当时很难强迫所有人搬去渥太华。

如果我们不强求团队必须搬到旧金山或纽约，那我们就必须在分布式协作上走得更远。

远程并不代表我们从不线下见面。我们每年雷打不动组织两次全员线下大聚会（Offsites）。但除此以外，我们发明了一个概念叫 **Campfires**（营火计划）。当团队中有两三个人因为出差或者开会偶然聚在某一个城市时，这就被定义为一次“营火”。我们会鼓励任何感兴趣的成员前往该城市加入他们。比如这周因为行业大会，我们在旧金山组织了一次“营火”，大家会聚在一起吃晚饭、见客户。

我们鼓励大家参与，但这绝不是强制的。有的人更愿意在家里陪家人，只要参加一年两次的全员 Offsites 即可，平时完全不用坐飞机出差。

我们也发生过很多有趣的 FOMO（错失恐惧症）故事。比如上一次几个同僚在纽约聚会并发了张合照，一个住在渥太华的工程师因为极度眼馋，直接打了个 Uber 冲向机场，买了一张最近的机票飞去纽约现场和大家汇合。

此外，我们引入了 **Turbo Credits**（点数机制）。如果你做了技术演讲或者写了一篇高质量的博客，你就会获得一定的 Credits，它允许你在下一次出差飞行时直接免费升舱到商务舱。我们团队甚至有工程师提议要成立一个“虚拟中央银行”，在此之上发行利息，甚至搞一个围绕 Credits 的博彩预测市场（笑）。这些有趣的小机制很好地鼓励了那些真正渴望面对面交流的工程师走出去。

<details>
<summary>Original English</summary>

**Simon**: Yeah, I think so. The the company started in in 23. So, sort of like on the on the on the cusp of COVID where a lot of companies were just remote. Um, the Shopify infra was remote since the very um very beginning because it was very difficult to get them all to move to Ottawa. Um, and so it was natural to me. It's like, okay, I think there's kind of maybe two cities where you can build a database company fast, and that's San Francisco and and and maybe New York. There are maybe other cities, right? But that's like kind of where it's been done. Yeah. And so if you don't want to do that, I think you have to go all in on on on some distributed model. And so we've tried to figure out what does that distributed model mean for Turppuffer? It doesn't mean the absence of in person. we get everyone together twice a year in in some in in some location. Uh earlier this year we were in in B, right? And then we were in Mexico City and so on. So it's like that's that's not that uncommon. Um but one of the things that we we we've been trying to do is we have this concept called campfires. And the concept of the campfire is that when a couple of people just sort of randomly congregate in a place, you call it a campfire and you encourage as many people as you want to come and join. So, for example, this week is a Turbo Puffer campfire in San Francisco because I'm here for this conference and a bunch of other things. And so, everyone is invited to come. Like, we're going to go meet customers, right? We're going to put on dinners for our customers and things like that. And we just make a thing out of it and and spend time together. And uh we encourage everyone to come. We've also gone to the extent now of um we want to encourage that, but not everyone not everyone needs to go to the campfire all the time. Some people just want to, you know, lock in and hacks into tent and that's great. We have people that just make it to the off sites twice a year and otherwise they're home, they're with their families and they don't they don't spend time on an airplane. Um, fantastic. Like that is completely compatible with this model. And there are other people at the company who are on a plane probably every two weeks. Um, we had someone the other day where they saw a campfire happening in New York and everyone was dialing in from a meeting room in New York and she had so much FOMO that she took an Uber straight to the airport in Ottawa and flew to [laughter] flew to New York to hang out with the team, right? And I think that's fantastic. Um and we've also introduced these things where um if you if you uh if you do a current conference talk or a blog post or something like that at Turbop or something a bit extracurricular, we give you a turbo credit and a turbo credit allows you to upgrade your next flight to business class which again encourages spending time together with the team. Um and now I mean turbo credits are probably going to take on a life of their own. Someone was talking about doing a central bank and doing interest rates on the turbo credits. um and doing a betting market on the turbo credits. And so like this might take on its life on its own. Um and uh you you know if you um if you're at a conference like this, there's some of the our engineers here who are just want to interact with customers and be on like and standing on a like expo floor all day is quite taxing. And so if you do that for two days because you want to do it, oh, you get a turbo credit, right? And so it's just like these fun little things that we try to do to to to encourage people to meet if they want to meet

</details>

**Gergely**: 谢谢。在这场对谈中，最令我触动的是，虽然大量 AI 创业公司都在把 **Turbopuffer** 作为他们不可或缺的底层算力底座，但在今天这一个多小时的对话里，我们其实很少谈论虚无缥缈的 AI 概念，而是把时间花在了坚实的工程常识、打破常规的好奇心、以及团队之间真实纯粹的人际信任纽带上。非常感谢你的分享，让我们把掌声送给 Simon！

<details>
<summary>Original English</summary>

**Gergely**: Thank you. Well, in this session, uh, what I found very interesting is Turbopuffer is a so many AI companies are using you as an infrastructure layer, but in this conversation, we managed to talk very little about AI and a lot more about engineering principles, pushing, being curious, and the human connection, how important it is for people to work together, to trust each other. So, just thank you very much for that. So, let's give a big round of applause for Simon.

</details>

**Simon**: 非常感谢大家，聊得很开心。谢谢。

<details>
<summary>Original English</summary>

**Simon**: Thank you so much. This is great. Thank you.

</details>