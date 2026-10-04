---
author: The Pragmatic Engineer
date: '2026-07-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=h8TBLKyo7Rs
speaker: The Pragmatic Engineer
tags:
  - vector-database
  - serverless-infrastructure
  - napkin-math
  - system-reliability
  - startup-scaling
title: 专访Turbopuffer创始人Simon Ericson：从Shopify基建大拿，到用Serverless重塑向量数据库
summary: 本文专访了Turbopuffer创始人兼CEO Simon Ericson。他分享了自己通过PowerPoint和诺基亚砖头手机开启编程之路、在Shopify深度参与基础设施扩容（如分片与Toxiproxy）的经历，以及他基于Napkin Math（估算数学）理念创立Serverless向量数据库Turbopuffer的过程。同时，他还分享了与Cursor合作降低95%账单的趣事、与黄仁勋的趣味会面、硬件与CPU选型经验、创业融资的六个真实原因，以及独特的远程 campfires 团队文化。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Simon Ericson
companies_orgs:
  - Turbopuffer
  - Shopify
  - Nvidia
products_models:
  - Turbopuffer
  - Cursor
media_books: []
status: evergreen
---
### PowerPoint与早期编程启蒙

**主持人**: 我很高兴今天能与 Turbopuffer 的创始人兼 CEO Simon Ericson 进行交流。他是一位技术背景非常深厚的 CEO，我们将进行一场相当硬核的技术讨论。但在我们深入探讨之前，Simon，我想问一下，你是从哪里开始爱上计算机的？
**Simon**: 额，是通过 PowerPoint。
<details>
<summary>Original English</summary>
I'm excited to have a chat with Simon Ericson, founder, CEO of Turbopuffer, a very technical CEO, and we're going to have a pretty technical discussion. But before we jump into it, Simon, I wanted to ask, where did you fall in love with computers? Um, through PowerPoint.
</details>

**主持人**: PowerPoint？
**Simon**: 对。我不知道你们是否了解这一点，但你们大概也知道，在 PowerPoint 中你可以制作图表之类的内容，当你点击它们时，它们会跳转到另一张幻灯片。这很快就会变得具有图灵完备性，对吧？你可以用它来设计非常复杂、甚至可以说是相当精致的游戏。然后，在某个时候，你接触到了 Microsoft Office 套件，并发现了 Front Page，你还记得 Front Page 吗？
<details>
<summary>Original English</summary>
PowerPoint. you I don't know if any of you know this but in power well you probably know this but in PowerPoint right you can make the the diagrams and stuff when you click them go to another slide that becomes turning complete real quick right you can sort of you know create very complicated convoluted games and then at some point you know you make it through the Microsoft Office suite and you discover Front Page do you remember Front Page
</details>

**主持人**: 是的，我记得 Front Page，它本来是为了消除对所有前端开发人员的需求而设计的。
**Simon**: 确实如此。而且它只能在 Internet Explorer 中运行。我记得有一天我经历了一次极度的心碎，因为有人在 Firefox 中打开了我制作的一个网站，结果整个布局全乱了，完全惨不忍睹。后来有一天，我意外地点击了 Front Page 里的 HTML 视图，它展示了一大堆我根本无法理解的代码。我开始盯着它看，然后去网上寻找一些可以添加进去的小代码片段，比如让光标改变样式，以及各种各样不同的效果。然后一切就开始升级了。接着你升级到了 Dreamweaver，现在你开始真正编写代码了，然后你会想：‘好吧，如何动态生成页面？’ 于是你学习了 PHP。而对我来说，我当时已经看完了所有关于丹麦语编程建议的网页。
<details>
<summary>Original English</summary>
yeah I remember Front Page it it was supposed to eliminate the need for all any front-end developers Exactly. And it it only worked in Internet Explorer. I remember a heartbreak I had one day when someone opened a website I created in Firefox and it just it was it was all over the place. And then one day I accidentally clicked the HTML thing in front page and it just showed all of this stuff that I couldn't make sense of and it just started looking at it and then going online and finding little snippets that you could add in to make the cursor change and all of these different uh different things. And then it just sort of escalated from there. Then you upgrade to Dreamweaver and now you're coding and then you're like, well, how do you make the pages dynamically? You learn PHP. And then for me, I exhausted the internet on Danish language programming advice.
</details>

**Simon**: 额，那时我大概 11 或 12 岁。所以我就去玩《魔兽世界》，并且沉迷了四年。但这让你的英语变得非常非常棒。所以你开始进行一些黑客尝试，进入更深层次的研究。
**主持人**: 那符合逻辑的步骤本应该是去大学，系统地学习这方面的知识。但你并没有这么做，对吧？
**Simon**: 是的，我的意思是，我只是开始……我的意思是，我先是了解了视频游戏，然后学会了英语，然后接触到了网络这门庞大的武器库。如果现在有 LLM，它直接对我说丹麦语，你可能就不会像我当时那样撞墙了。
<details>
<summary>Original English</summary>
Um, and I was I was around 11 or 12. And so I just, you know, went and got addicted to World of Warcraft for four years. But that gets you really really good at English. So you kind of start hacking, get into deeper. Now the logical step would have been to just, you know, go to university and learn properly about this stuff. But that's not what you did, did you? I mean, I just um I I started just I I mean, you know, then I learned video games, then I learned English, and then, you know, this like massive arsenal of the web. I now it'd be very interesting because the LLMs would just speak Danish to me and you could just you wouldn't have hit the wall like I did.
</details>

**主持人**: 额，那确实会非常有趣。也许我当时的编程水平会更好。那会很不错。
**Simon**: 是的，然后我就开始在高中期间接一些工作和项目。当我在高中的时候，我也接触到了一个叫国际信息学奥林匹克（IOI）的东西。你听过这个项目吗？
<details>
<summary>Original English</summary>
Um so that would have been very interesting. Maybe I would have been better at programming. That would have been nice. And then I Yeah. Then I just started picking up jobs and things like that throughout high school. And when I was in high school as well, I got exposed to this thing called the International Olympiad in Informatics. You
</details>

### 国际信息学奥林匹克与Shopify的奇妙结缘

**主持人**: 听过。
<details>
<summary>Original English</summary>
**Host**: heard of this thing?
</details>

**Simon**: 额，我当时有一个网友，她住在澳大利亚，是澳大利亚国家队的成员。她告诉我，丹麦队应该也有类似的选拔，但我之前从未听说过它。所以我在某个神秘的小网站上找到了它，然后提交了申请，接着开始解决这些编程问题，这些问题看起来和我之前解决的 HTML 和 PHP 问题截然不同。
<details>
<summary>Original English</summary>
**Simon**: Yeah. Um, and I had a I had an internet friend and she lived in Australia and she was on the Australian team and she told there's probably something for the Danish team as well, but I had never I'd never heard about it before. And so I found it on some like little mysterious website and then applied and then solved these programming problems that look very different from the HTML and PHP things that I'd solved until
</details>

**主持人**: 那些更像是算法类的程序。
<details>
<summary>Original English</summary>
**Host**: were like the algorithmicalish programs.
</details>

**Simon**: 没错。虽然它实际上不是你在现实中会遇到的那种问题，但我认为它很好地说明了你可能会遇到的问题类型。你可以想象一下：‘好的，这里有 N 辆卡车，这里有 M 个包裹，这 M 个包裹有这些维度，告诉我哪些包裹应该装进哪些卡车里，然后进行某种最优化的规划。’ 这是一个 NP 难问题，你无法完美解决它，但你可以和比赛中的其他人竞争，看谁能做出最好的优化。所以就是这类问题。
<details>
<summary>Original English</summary>
**Simon**: Exactly. It's sort of like this is not actually the kind of problem you would see there but I think it illustrates well the kind of problem that you might get right is you can imagine something like okay here's like n trucks here's m packages the m packages have these dimensions give me which trucks which packages should be in right and then do something optimal like that's an npmplete problem you can't solve that but you could compete with everyone else in the competition of doing the best thing so it's these kinds of problems right
</details>

**Simon**: 额，所以我在高中时就开始做这些了。同时我也在为一家初创公司工作。然后，Shopify 在我还在读高中的时候就找到了我。
<details>
<summary>Original English</summary>
**Simon**: um and so I started Ed doing that in high school. I was working um I was working as well um for a startup. Um and then I just Shopify found me while I was still in high school.
</details>

**主持人**: 那么，Shopify 找到你，是通过你的开源贡献，还是因为其他原因？
**Simon**: 是因为我写了一篇文章。我当时摔坏了我的 iPhone。你知道以前有段时间，如果你的 iPhone 掉在地上，你就知道屏幕彻底完蛋了。
<details>
<summary>Original English</summary>
And and the whole like Shopify found me was it through your open source contributions? Was it was it something else? It was because I had written an article where I had I had I dropped my iPhone and it was you know the iPhones are a lot like there used to be a time right where you drop your iPhone and you just knew it was over for the screen.
</details>

**主持人**: 现在的屏幕好多了，这种情况不太会发生了。但当时确实是摔一下就废了，根本没法再用。
**Simon**: 没错，一摔就坏，完全不能用了。所以我用回了旧的诺基亚砖头手机。那是 2013 年，人们当时还没怎么意识到智能手机带来的所有危害。于是我写了这篇文章，讲述我是如何通过电话与人联系，以及我如何重新找回了方向感。我写了关于这个的文章，它在 Hacker News 上短暂火了一下，然后《纽约时报》决定推荐它。
<details>
<summary>Original English</summary>
It doesn't really happen as much anymore like the screens have gotten a lot better but back then it was like yeah one drop and it was dead and it just couldn't use it anymore. And so I went back to one of these old Nokia brick phones and this is back in 2013 and people hadn't really realized all the pernicious effects of smartphones at the time. And so I wrote this article about how oh my god I'm like calling people and I have my sense of direction back. Um and I wrote an article about it and this article it went on hacker news briefly and it um New York Times decided to feature it.
</details>

**主持人**: 真的吗？
<details>
<summary>Original English</summary>
**Host**: No way.
</details>

**Simon**: 是的。所以它带来了大量的流量，然后一些敏锐的 Shopify 招聘人员把这一切拼凑在了一起。我和他们通了个电话，我觉得他们当时甚至没有意识到我还在上高中。但我们聊得非常开心，他们邀请我到加拿大渥太华去面试。我当时根本不知道加拿大渥太华是什么地方。我记得邮件里写着类似于‘什么是渥太华？’ 的内容，我完全不知道。于是我去了那里，走进那栋大楼，感觉一切都非常对劲。我和他们进行了面试，然后说：‘好吧，我得先完成高中学业。’ 之后我在 2013 年搬到了加拿大，入职了 Shopify。
<details>
<summary>Original English</summary>
**Simon**: Yeah. And so a lot of traffic was driven to it and then some astute Shopify recruiter put it all together and um and I had a call with them and then I don't think they realized that I was still in high school but um but I had a great call with them. They invited me on site to Ottawa, Canada. Um I had no idea what Ottawa Canada is. I think the email says something like what's an Ottawa? I had no idea. Um, and so I went there and it was just like walked into the building and it was just a just felt right. Um, and so I I I interviewed with them and then said, "Well, I got to finish high school first." And then uh and then I moved to Canada uh to to to work at Shopify. Yeah. In 2013.
</details>

**主持人**: 是的，我想这绝对是一个无需担心上大学的完美借口了。
<details>
<summary>Original English</summary>
**Host**: Yeah. I think that's that's a like legit excuse for like not even worrying about college and and university.
</details>

### 拒绝大学与Shopify的“狂野成长”

**主持人**: 但你脑海中曾经闪过上大学的念头吗？
<details>
<summary>Original English</summary>
**Host**: But I did it crossed your mind.
</details>

**Simon**: 闪过。我本以为我只是去度过一个间隔年（Gap Year）。我想着：‘好吧，我去 Shopify 工作一年，然后我可能会回去读书。’ 但当时我对于自己没有学过计算机科学感到非常不安全，我唯一的接触就是所有的 IOI 竞赛，而这正是很多计算机科学的极佳速成课。如果说它教会了我什么，那就是它让我懂得：只要你花足够的时间，你完全可以坐下来读懂一篇论文并把它弄明白。所以我重复地这么做。在 Shopify 的第一年，每当我听到我不懂的名词，我就会把它记在纸上，晚上回家后就去阅读相关资料。因为我当时很焦虑，觉得如果别人提到 TCP，他们肯定知道三次握手的每一个细节，以及 TLS 是如何分层的，并且他们都在 Wireshark 里观察过。虽然我现在不觉得大家都懂，但当时我是这么想的。
<details>
<summary>Original English</summary>
**Simon**: It did. I thought I was going I thought I was doing a gap year. I thought I was like, "Okay, I'm gonna go work at Shopify for a year and then I'll probably go back and do but I would just I was very insecure at the time about the fact that I hadn't studied computer science and my only exposure had been all the II competitions which is a pretty good crash course in a lot of computer science. And if nothing else, it had really taught me that you can just sit down and read a paper and just figure it out if you spend enough time on it. So I did I did that repeatedly and in my first year at Shopify I just every time I heard something that I didn't know what was I noted it down on a piece of paper and then I went home and then that evening I would just read about it because I felt insecure that like well if someone mentions mentions like TCP surely they know exactly what's in the three-way handshake and how TLS is like layered on top and they've looked at Wireshark and all of that. I don't think that's true but that's what I thought.
</details>

**Simon**: 所以我对遇到的所有事物都进行了深入研究。这是一次非常棒的速成，很快我就明白，我只想继续做这个，而不想去别的地方，然后再回来。因为我觉得我已经找到了我想做的事情。
**主持人**: 听起来这非常完美地结合了你内心那种自然的焦虑感（毕竟你很年轻，没有其他人拥有的那种学历背景）以及一个当时就在做非常前沿技术的公司。即使是今天，Shopify 也是领先者。所以你一直在自我驱动，不断追赶。我理解你对每个概念都进行了极度深度的钻研，而不仅仅停留在表面，对吧？
**Simon**: 我觉得我只是想不断了解计算机是如何工作的。我认为这也是我现在面试工程师时会寻找的特质：你无法克制自己去层层剖析它的原理。对我来说，这最终落脚在了基础设施层——也就是 Shopify 中最接近物理硬件的那群人。虽然我当时是在产品端工作，但我吃午饭时总是坐在基础设施团队旁边。因为我忍不住，我太想学习了。当他们谈论反向代理（reverse proxy）时，我会想：‘为什么它叫反向？’ 我到现在都回答不了。我的意思是，好吧，你知道吗？它反向了什么？因为它就是一个代理，对吧？我不知道。这就像倒排索引（inverted index）一样，什么被倒排了？这反正是一个糟糕的名字。
<details>
<summary>Original English</summary>
So I went and did that for everything that I encountered. Um, so that was a really good crash course and then very quickly it became clear that well I just want to continue doing this. I don't want to go go somewhere else and then come back to this because I felt like I'd already found what I wanted to do. So it sounds sounds like it was a pretty good combination of like you just having this like very natural insecurity like you're young, you know, you don't have the education that everyone else has and inside a company that's just doing pretty like cutting edge stuff even at the time and even to today, right? like they're they're leading and so you just kept self-seing yourself like just catching up and go and do I understand that you just went deep in every concept that you didn't like just like try to understand at surface level but like go as deep as you can search on the internet buy books whatever that is I think it was just that I just wanted to know keep learning how computers work and I think that this is something that I now look for when we interview engineers is that you just you can't help yourself but trying to peel back the layers And for me ended up with the infrastructure layer. That was, you know, the people closest to the metal at at Shopify. And I would just always sit next to them at lunch cuz I was working on the on the product side. But I just I couldn't help myself. I was so I just wanted to learn what it was when they were talking about a reverse proxy. I'm like, why is it reverse? I I still can't answer that. I I I mean, okay. Do you know? Well, what's in reverse? Because it's a proxy, right? I don't I don't know. I don't know. It's like an inverted index. Like, what's inverted? It's like it's a terrible name anyway.
</details>

### 数据库分片与系统可用性的极限挑战

**主持人**: 哈哈，是的，在表查询之类的事情上，名字确实很奇怪，但我懂你。这里面确实有一些奇怪的命名。但是在 Shopify，有哪些艰难的工程挑战、服务中断或经验教训塑造了你？这些挑战在当时很有趣，而且在其他地方很难体验到。
**Simon**: 是的。我认为在 2010 年代，有一大批 SaaS 公司规模扩张得非常快，我感到非常幸运能够亲眼见证这一过程。我在 2013、2014 年左右加入了基础设施团队。当时 Docker 刚刚推出，所以我们正在对所有服务进行容器化。每年我们都必须为比上一次更糟糕的黑色星期五做准备。当时我们还在购买物理硬件，我们必须在特定时间点下单，并据此进行插值预测。软件也必须进行扩展。当你扩展大多数软件时，应用层的大多数问题最终都会归结到数据库层。
<details>
<summary>Original English</summary>
Yeah. I I mean, it's still better when when you get to not tables, the lookups, some of those things like some of that. But yeah, I hear you. There there's some like weird names with this, but at at Shopify, what were some of the kind of like hard engineuring challenges that you engineering challenges, outages, like like learnings that kind of defined you that were really also fun at the time or interesting to learn, but it would have been hard to get it elsewhere. Yeah. Yeah. So I think it was, you know, in the 2010s there's like a bunch of SAS companies that that scale really quickly and I felt so fortunate to have a front row seat to that and so I ended up on the infrastructure team and this was back in you know 13 14 and  Docker was coming out and so we were containerizing everything and we were just every single year we had to you know the growth rates of of of SAS sometimes seems quaint in comparison to the growth rates of companies today but it was a company that was growing at you know 1204 40% year-over-year. Um, and so every year we were just preparing for a Black Friday that was going to be a lot worse than the last. And this is back in the day of we're buying physical hardware, right? We have to like place an order at a particular point in time and do some interpolation based on that. Um, and the software also had to scale. And when you're scaling most software, a lot of the application layer problems end up back at the database layer.
</details>

**Simon**: 所以我自然而然地发现了自己处于 Rails 和数据库之间的这一层。Shopify 当时至少没有向数据库本身贡献很多补丁，但主要花时间在编排上。我们当时在做分片（Sharding），因为正如我亲爱的老板 Camilo 常说的：‘你无法缓存写入。’ 所以在某个基础点上，你必须超越单个分片的限制。我是在他们进行分片切换时加入的，而且他们是在黑色星期五前一周进行的切换，这简直令人难以置信，但它确实成功了。随后的几年里，我们致力于多数据中心运营。我们还有一个神秘的 Redis 服务器，当时有 128 GB 内存，在当时这非常大，没人真正知道里面装了什么。有一天它宕机了，大家觉得这超级恐怖，因为人们一直把它当作一个简单的键值存储。于是我们开始对它进行拆分。我们做了很多工作，以确保如果你访问 Shopify 商店，而存储你 Session 的组件宕机了，正确的行为不应该是让整个系统都崩溃。但这通常是默认的失效模式，对吧？除非你的编程语言强迫你做出其他决定。因此我们制作了一个矩阵，定义了‘当此组件宕机时，该服务应该如何表现’。我发现自己正在为其中很多内容编写测试套件。然后我觉得我们不能只是去 Mock 这一切。所以，我当时想出了一个主意：‘我们要做的就是直接调用 GDB，注入到进程中，然后关闭到数据库的文件描述符，以在整个层面上模拟数据库完全失效。’ 这在当时有点疯狂，我们从未在 CI 上运行它，但它确实揭示了 Rails 中大量由于连接层失效处理不当而产生的问题，我们也向上游提交了补丁。接着我开始着手创建了一个名为 Toxiproxy 的代理。
<details>
<summary>Original English</summary>
And so I just naturally found myself at this layer between Rails and the databases. Shopify didn't at the time at least contribute many patches to the databases themselves but mostly just spent time orchestrating. So we were doing sharding because as um my my dear boss Camilo used to say you can't cash rights. So there's a fundamental point where you you just you have to move beyond a single shard. Um so I wasn't I joined around the time and they did the sharding and they did it I think they did the cut over a week before Black Friday which is mindblowing. uh and very but it worked and then the subsequent years we worked on things like going into multiple data centers. We also had this big mysterious reddish server that was like you know 128 GB of RAM which was a lot at the time. Today it's not that much and no one really knew what was in it and then it went down one day and people were like well that's super terrifying. Um because people had just been treating it as this KV store. Um and so we started splitting it out. We did all this stuff around making sure that if you if you if you go visit a Shopify store and the thing that stores your sessions is down, the right behavior is not just for the entire the of everything to be down. But that's kind of the default failure mode, right? You're not going to rescue all of that. Um unless you're in a programming language that really forces that decision. So we did things like um build this matrix out of okay well this service when this component is down should act this way. Um and I found myself writing the test suite for a bunch of that. And then I was like okay well we can't just mock all of this. And so um I came up with this idea at the time of like oh what we're going to do is we're just going to um shell out to GDB and then into the process and then close the file descriptor to the database to simulate through the entire layer that the database fails. That was a little crazy and we never shipped that on CI but it did uncover a massive amount of issues in Rails that'd be upstream and things like that of around just like handling failures at the connection layer. So then I moved on to create this proxy called Toxyroxy and
</details>

### Toxiproxy的诞生与混沌工程实践

**主持人**: 你以前听说过这个吗？
<details>
<summary>Original English</summary>
**Host**: have you heard of this before?
</details>

**主持人**: 没有，没听过。
<details>
<summary>Original English</summary>
**Host**: No. No.
</details>

**Simon**: 是的。Toxiproxy 就像是一个 7 层代理，实际上是 4 层，介于你和数据库之间。你有一个代理，MySQL 等服务不需要理解这个协议，但你可以通过 API 调用它说：‘让数据库下线，或者让它变慢。’ 随着时间的推移，我们还添加了 7 层的功能，比如模拟各种故障。这样你就不需要 Mock 底层驱动，而是直接测试驱动及其故障处理机制。从而整个故障矩阵都可以在 CI 中实现。
<details>
<summary>Original English</summary>
**Simon**: Yeah. Toxyroxy is it's just like a layer 7 proxy that sits in between um you and well layer four but in between you and the databases. So you basically have just like this proxy and then my SQL whatever doesn't speak the protocol but then you can do an API call say take take  take the database down make it slow um and over time it also added layer 7 things of like do a bunch of failures this way you're not mocking the low-level drivers but you're testing the drivers and their failure handling as well so then this entire matrix could be implemented in CI
</details>

**主持人**: 所以基本上这个代理只是一个非常薄的透传层，但你构建了模拟数据库故障、数据损坏或任何你想模拟的故障的功能。所以你可以在其中进行测试，任何基于它构建的系统也都可以测试。但后来是所有人都需要调用这个代理，还是它必须作为其中的一层存在？
<details>
<summary>Original English</summary>
**Host**: so the basically the proxy was just like a really thin layer which like was passed through but you built the functionality to like simulate problems with database or things like data corruption or whatever you wanted to do. So you could just do it in there and then you can anything that built on top of it. But but then Oh yeah and then everyone had to like call this proxy or it needs to be on in in a layer.
</details>

**Simon**: 没错。你可以这样做：
<details>
<summary>Original English</summary>
**Simon**: Exactly. So you could do like
</details>

**Simon**: 比如调用 `toxyroxy.mysql.down` 然后传入一个 Lambda，定义你想做的事情。比如在 Session 表下线的情况下请求这个页面或执行结账。这直接在 MySQL 驱动和 Rails 中找出了几十个问题。在整个生态系统中，之前根本没有人测试过这个，而在生产环境中也很难发现这些，因为当 MySQL 挂掉时，你所有的精力都放在如何让它恢复运行上，而不是去观察应用层究竟会发生什么。
**主持人**: 这确实很有趣。我们显然还会谈到更多关于数据库的事情，但想想大型系统中的很多棘手问题总是与状态（State）有关。我之前从未把它们联系起来，也就是状态通常存在于数据库中。如果没有数据库，如果你拥有无状态服务，虽然也会有节点下线、数据损坏等问题，但它们通常更孤立。但基本上，如果我们有状态，我们通常就有数据库。如果你能模拟这些问题，你就可以预测很多事情。状态的问题在于，在它们发生之前，你很难提前去模拟它们。所以听起来你在这一块取得了很大的成功。
<details>
<summary>Original English</summary>
do like my SQL you know toxyroxy mysql.down down and then pass it a lambda of what you wanted to do like get this page do a checkout whatever with the sessions table down and this just uncovered tens of issues right in the MySQL driver in the Rails like it's just like no one in the ecosystem had been testing for this and it was very difficult to see this in prod right because when my SQL down you're focused on just getting back up and not like what could the application actually have done yeah it's interesting of course we're going to talk a bit more about databases obviously but just thinking about how a lot of the problems or some of the most gnarly problems in large systems are always to do with state and I never connected until now that I mean state is usually there's a database if there's no database if you have stateless services you know I mean you still have problems you have nodes going down you have I don't know corruption whatever but it's usually like more isolated but basically like if we have state we typically have databases if we have databases and if you can simulate these problems suddenly you can I mean you you can like predict a lot of things the problem with state oftens often time is it's really hard to simulate problems happening ahead of time unless when they happen. So did you it sounds like you had pretty good success with
</details>

**Simon**: 是的，据我所知，它今天仍在 Shopify 的 CI 系统中运行。我不知道观众席里有没有来自 Shopify 的人，但我敢肯定它还在运行。我们针对它编写了所有这些测试，来模拟各种不同的故障条件，效果非常好。
**主持人**: 你在 Shopify 一共度过了八年。从最开始以为的间隔年，一年又一年地待了下去。是在什么时候你开始考虑离职，为什么？你的决策框架是怎样的？听起来即使是今天，Shopify 发展得也非常好，增长一直在持续。所以当时肯定有很多理由让你留在这艘火箭船上。
<details>
<summary>Original English</summary>
Yeah, I think to my knowledge it's still um running in like the CI system of Shopify today. I don't know if anyone in the crowd is from Shopify, but I'm pretty sure that it still does. Um and so we wrote all these tests against it to implement all of these different  different failure conditions and it just yeah it was it was it worked out great. So you spent eight years in total at at Shopify. So like started from like all right just a gap year it just went on a year a year another year. Um at what point did you think about leaving and why and what was your kind of decision framework? It sounds like you or you were like on epic right now even today Shopify it's doing wonderful is probably doing even way better than like like you know that growth kind of kept on. So I'm sure there would have been an argument to stay and you know stay on their rocket ship.
</details>

### Napkin Math（估算数学）与拒绝盲目基准测试

**Simon**: 是的，我从 2013 年到 2021 年在那里工作了八年。我想到了一个时间点，我想去看看不同的东西。再次强调，我从 18 岁起就待在 Shopify，高中时只见过另一家初创公司。我想，如果我想学到更多关于计算机的知识，而且学得更快，可能是时候给这个函数注入一些新奇的变量了。于是我在 2021 年离职了。我在那里参与过很多不同部分的基础设施，比如缓存。我和 Justine（她现在是我的联合创始人）重写了 Shopify 的整个 Storefront 系统，在项目启动 18 个月后它承载了几乎 100% 的流量。我们致力于让 Shopify 在多个数据中心运行，参与了许多数据库扩容项目（如缓存和各种事情）。卡戴珊姐妹在 Shopify 上发布大量产品时经常会带来海量流量，这倒逼了我们的系统扩展。但最终我离职了。当我离职时，我并不确定自己想做什么。在 Shopify 期间我做过一个项目，叫做 Napkin Math（估算数学）项目。你见过这个吗？
<details>
<summary>Original English</summary>
**Simon**: Yeah. So I I spent I spent eight years there from 13 to to 21. Um and I I think there just came a point where I wanted to see something different. Again, I've been inside of Shopify since I was 18 years old, right? I'd been seen one other startup in high school. I was like, if I want to learn more about computers and learn faster, it might be time to inject some novelty into this function. Um, and so I  left in in in 21 and I'd worked on so many different parts of the infrastructure like caching.  Um, me and Justine, who is now my co-founder, rewrote the entire storefront um, storefront for Shopify um, which powered almost 100% of traffic 18 months after we embarked on it. Um, we worked on running Shopify in multiple data centers. We worked on so many database scaling projects like caching, all of these different things, right? Um, a lot of the a lot of the scalability came from the Kardashians launching lots of products on on Shopify, which would force a lot of traffic. Um, but that's that's eventually how I left. And so when I left, I didn't really know what I wanted to do. And so I one of the projects I had while I was at Shopify was this napkin math project. Have you seen this
</details>

**主持人**: Napkin Math？没有。
<details>
<summary>Original English</summary>
**Host**: napkin math? No.
</details>

**Simon**: 好的。Napkin Math 基本上是我在 GitHub 上维护的一个表格。比如：你可以向 DRAM 驱动多少带宽？往返 S3 需要多少成本以及耗时多久？你可以向 NVMe SSD 写入多少带宽？你可以向 EBS 卷写入多少带宽？大概收集了 50 个这样的数字，并用一个 Rust 脚本来生成它们。比如：一吉字节的内存要多少钱？2 美元。一吉字节 of S3 要多少钱？2 美分。一吉字节的这个要 10 美分，对吧？竞价实例上是多少钱？三年承诺期是多少钱？我整理了一个庞大的表格，并为几乎每个单元格制作了闪卡（Flashcards），所以我熟记这些数字。我开始在 Shopify 做这个项目，因为我发现自己经常扮演这样一个角色：去评估某个项目。例如，某个产品团队会说：‘好的，我们必须构建这个功能，所以我们需要构建这个基础设施来支持它， we 已经在数据库 A 上进行了基准测试，但测试结果不太好，所以我们要用数据库 B。’ 我非常讨厌盲目的基准测试（benchmarks），因为这对我来说不是一个令人满意的答案。如果按照估算数学计算，你认为需要 10 秒才能完成的数据库 A 查询，实际上应该只需要 10 毫秒。如果这是一个搜索查询，你搜索三个词，每个词有这么多文档匹配，那就是这么多兆字节，我们对这些列表进行交集操作。你在多个核心上拥有每秒 100 GB 的 DRAM 带宽，这应该只需要 10 毫秒。你告诉我基准测试用了 10 秒，那我们中肯定有一个人错了。要么是我的理解有偏差（这很有可能），要么是你的基准测试测错了东西。有时候他们做基准测试时，没有意识到他们的测试其实是在 100 个不同的节点上进行分布式查询，所以 P99 延迟自然会非常非常高，除非你截断它或者做了不同的权衡。所以我经常在这些讨论中发现人们基于糟糕的基准测试来做基础设施决策。因此我需要一些武器，能够当场进行计算。因为我总是写一些小 Demo 或者写一些原型脚本来演示这个。比如：这是一个 B 树的工作原理，这是我们需要访问的页面数量，这是一次随机 SSD 读取的时间（需要 1 毫秒），你需要访问一千个页面等等，然后展示出来说：‘看，这就是和你查询的差距。查询执行计划正确吗？MySQL 有 Bug 吗？我们的磁盘坏了吗？这当中的差异到底在哪里？’ 我深深迷上了这个方向。所以我离开 Shopify 后，写了很多关于这方面的文章。我一直在想：‘这个查询应该花多少时间？’ 后来我提出了一个假设：‘MySQL 每秒能做多少次写入？每秒的写入次数难道不应该等于你每秒能做的 fsync（文件同步）次数吗？’ 这听起来很合理对吧？每次你写入时，你都要 fsync 以持久化到磁盘。那么每秒你能做多少次 fsync？一次 fsync 需要 1 毫秒，所以你每秒能做 1000 次写入。但这和实际情况对不上，因为数据库显然每秒能做超过 1000 次写入。为什么它能做到？这就是我去测试的事情之一。结果发现，MySQL 在一台很普通的机器上每秒能做 10,000 次写入。这怎么可能呢？
<details>
<summary>Original English</summary>
**Simon**: No. Um, so napkin math was essentially just this table that I maintain on GitHub of how much bandwidth can you drive to DRAM, what does a roundtrip to S3 cost, and how long does it take, how much bandwidth can you drive to an NVME SSD, how much bandwidth can you drive to an EBS volume? Just a collection of probably there's probably like 50 of these numbers and then a RS script that generates them all. um what all these things cost? What do you like? What does a gigabyte of memory cost? $2. What does a gigabyte of S3 cost? Two cents. What does a gigabyte of um this cost 10 cents, right? What does it cost on spot? What does it cost on a three-year commit? Like I had just have a massive table and then create flash cards for almost every single cell. So I know all these numbers. And this was a project I started taking on at Shopify because I found myself in um this role a lot where I would go in and review a project, right? So some product team would be like okay we got to do we got to build this thing so we got to build this infrastructure to support the feature and a lot of the times they would say okay well we've gone and benchmarked it on database A but the benchmarks are not very good so we're going to go with database B and I hate benchmarks so much because that's not a satisfying answer to me to me it's like this does not jive with my intu ition database A that you're saying takes 10 seconds to do this should take 10 milliseconds if you do the napkin math right if it's a search query right it's like okay you're searching for three terms there each term has this many documents that match it that's this many megabytes we inter intersect these many this many lists you have DRAM bandwidth on multiple cores of 100 gigabytes per second this should take 10 millisecond you tell me the benchmark takes 10 Second, one of us is wrong. Either there's a gap in my understanding, which is very likely, or you would benchmark the wrong thing. And in some ways, some reasons, right, it's like, okay, you've done a benchmark. You don't didn't realize that your benchmark is doing a distributed query across a 100 different nodes. And so, of course, the P99 is going to be really, really high, right? Unless you've cut that off or or made some different set of trade-offs. So I just found myself in these discussions repeatedly where people were making infrastructure decisions based on poor benchmarks. And so I needed some I I needed some ammo to go in and just be like okay we can just do the calculation right here and then. Um because I was always doing these like little demos or like writing little prototype scripts to to demonstrate this. But it was just I just the argument of here's how a beach works. This is how many pages we have to visit. This is what a random SSD read takes. It takes one millisecond. you have to visit a thousand blah blah blah blah blah and then present it back and see this is the difference to your query well like is the query plan correct like is there a bug in my SQL do we have bad discs like what's the discrepancy here and I just got caught with that bug and so after I left sha I was just writing a lot of articles about this I was just like well how long does should this query take and then I one hypothesis I had at some point is like okay well how many writes per second can my SQL do well shouldn't the amount of writes per second that my SQL do equal the amount of f-syncs that you can do per second. That sort of makes sense, right? Every time you do a ride, you f-sync to persist to disk. So, how many f-syncs can you do per second? Well, an f-sync takes one millisecond. So, you do a thousand rights per second. That well, that doesn't really match up. Like, feel like a database can do more than,000 rightes per second. Why can it do that? So, that was one of those things where I tested and it's like, okay, well, my SQL on a little dinky box could do 10,000 writes per second. Well, how is that possible?
</details>

**主持人**: 那么，这怎么可能呢？
<details>
<summary>Original English</summary>
**Host**: And now you would just ask, how is it possible?
</details>

**Simon**: 因为有批处理（Batching）。所以，一个 fsync 通常发生在 4K（4KB）大小的数据上。
<details>
<summary>Original English</summary>
**Simon**: Because you batch. So, an F-Sync happens on usually a 4K.
</details>

**主持人**: 明白了。
<details>
<summary>Original English</summary>
**Host**: Yeah.
</details>

**Simon**: 对，但这并不直观。我当时为此着迷，可能有整整 24 小时都在死磕这个问题。你得去写 BPF 追踪脚本等来做所有这些工作，这花了我很长时间。然后我发现，每次 fsync 的大小其实比我推断的要大得多，因为它是批量进行的。你深入到代码中去阅读它，并在网上找到了一篇晦涩的文章——写这种文章的人总是住在巴伐利亚的某个德国小镇，写关于 MySQL 如何工作以及他们提交的补丁的细节。我坚信整个互联网其实都在靠巴伐利亚小镇上的人在运转。是的。然后你决定创立 Turbopuffer。你是怎么决定的？你当时知道自己想构建什么吗？还是只是觉得‘我想做点和数据库相关的东西’，因为你显然非常喜欢数据库，你也做过非常出色的基准测试和理论极限推导。你非常熟悉这些，甚至可能成为了这个领域的顶级专家，然后呢？
<details>
<summary>Original English</summary>
**Simon**: Right. But it's like that's not intuitive. Like it's actually I I I got caught. It was like just like, you know, probably some like 24-hour period where I just got obsessed with this question. Whereas like you're writing like the BPF traces and all of that to do all of this. This is like prelim so it took forever. And you and then I found out that oh every fsync was like much larger than I would have inferred like oh it's batching. you go into the code and you read it and then you found some obscure article by it's always somewhere in like a central German town that's like written some article about like how some intricacy of my SQL works and a patch that they did to it's like the entire internet runs on small towns in Bavaria I'm convinced. Yeah. And then you decided to start Turuffer. Yeah. Did how did you decide? Did you know what you wanted to build or was it more like I want to build something something databases because you were clearly very into databases. You you've done an awesome job benchmarking like what is the theoretical like limits. You were very familiar with this probably became you know like world expert in in this niche and then how
</details>

### 传统搜索的痛点与创立Turbopuffer

**主持人**: 你当时就想再次进入数据库领域吗？
<details>
<summary>Original English</summary>
**Host**: did did you want to go into databases again?
</details>

**Simon**: 我觉得当时有三件事交织在一起。首先，我在 Shopify 负责的最后一个项目是“搜索（Search）”，那次体验并不好。
<details>
<summary>Original English</summary>
**Simon**: I think it was there's three things that sort of came to a head. Um, the last project that I worked on at Shopify was Search and I didn't have a good time.
</details>

**主持人**: 你们当时用的是什么系统？
<details>
<summary>Original English</summary>
**Host**: What What What did you use back there?
</details>

**Simon**: 额，我们不需要指名道姓说出其他数据库公司的名字，但它是很多公司都在运行的传统搜索公司之一。要让它达到我的要求非常困难。我负责的那些接触该数据库的项目就是无法达到我的估算数学预期。它没有查询规划器（Query Planner），我搞不懂为什么会这样。有时候它还算正常，但有时候完全对不上。所以我试着学习尽可能多的知识来弄清楚，并开始阅读它的源码，但我还是无法让它走通。它操作起来非常困难，所以我当时脑子里一直记着这件事。我本以为我再也不会碰搜索了。第二个因素是 Napkin Math 项目，它让我对这些估算数据非常熟悉，知道如果完美利用一台机器，究竟能实现怎样的性能极限。
<details>
<summary>Original English</summary>
**Simon**: Um, I don't we don't need to name names of other database companies, but it was uh it was one of the one of the like traditional search companies that a lot of different um companies run. And it was just very difficult to get it to do what I did. And I was just like the projects that touched that database just I couldn't get them to perform at the napkin math. and like there's there's no query planner and like I couldn't figure out why it wasn't there and sometimes it tracked and then sometimes it really didn't track at all and so I tried to learn as much as I could to figure out and like start reading the source code of it and I was just I couldn't get it to track very often. It was very difficult to operate and so I just that was sort of like in the back of my head. I never thought I would touch that again. Then the second ingredient was the napkin math project because it sort of just gave me a lot of facility with all of these napkin math numbers of what might be achievable with the machine if you utilized it perfectly
</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>
**Host**: properly. Yeah.
</details>

**Simon**: 第三点是，我在 2021 年离开工作了八年的 Shopify，在那期间我做了一些我称之为“天使工程（Angel Engineering）”的事情。我加入了我朋友的公司，通过出力来获取期权，而不是单纯的资金投资，因为我想亲身参与，看看外面还有什么。这就是我离职的原因。然后这个搜索问题一次又一次地出现。ChatGPT 在 2022 年问世，我当时和一家公司合作，他们想把大量文档连接到 AI 上。那时上下文窗口非常小，所以你必须非常快速地进行检索和搜索。
<details>
<summary>Original English</summary>
**Simon**: And then the third one was that doing this you know leaving Shopify in 21 having spent eight years there and during that time I did this I called it angel engineering. So I like joined my friends companies and then I just vested equity instead of um instead of just investing or something like that and cuz I wanted to have my fingers in it. I wanted to like see what else was out there. That's why I left. And this problem kept coming up again again and again and again right like chatbt came out in 2022 and I was working with with a company then and they wanted to connect a bunch of documents to AI and that's when the context windows were really small. So you had to read search very quickly.
</details>

**Simon**: 所以文件大小大概是几个 KB，根据模型不同，大概是 8KB 或 4KB。这就引出了第三个痛点，就是当时很多现有的向量数据库。
<details>
<summary>Original English</summary>
**Simon**: So it's like a few kilobytes. It was 8 kilobytes or four kilobytes depending on the model. ...
</details>

**Simon**: 我和他们一起工作，创建了一个小推荐引擎，发现它的运行成本高得惊人。我当时想：‘等一下。我们只是在做几个字节的向量搜索，为什么我们需要一台拥有 256GB 内存、一个月要花几千美元的机器？’ 这不符合我的估算数学。如果你用 SSD 去做，S3 也可以，为什么所有数据都必须常驻内存（RAM）？这就是我开始研究的地方。我发现，如果你把数据写进文件，并利用 NVMe 的随机读取性能，或者将其放到 S3 上，那么由于内存和 S3/NVMe 之间存在 100 倍的成本差距，你本来是可以极大地降低成本的。
<details>
<summary>Original English</summary>
**Simon**: so I I I worked with them and I was I was I created a little recommendation engine and the ...
</details>

**主持人**: 这确实有些不可思议。
<details>
<summary>Original English</summary>
**Host**: weird but...
</details>

**Simon**: 是的，这很奇怪。因为很多系统其实是在读取类似索引的文件。比如：他在阅读有关如何在大规模数据上进行近似最近邻（ANN）搜索的论文。所有这些算法都是假设你的整个图形和所有索引都放在内存中的。但是对于很多用户来说，他们可能只有很低的查询流量，却要为了让数据常驻内存而支付高昂的账单。这完全没有道理。我们可以把它们放到 S3 上。
<details>
<summary>Original English</summary>
**Simon**: he was recommending. Yeah. I mean, it was just like, you know, he was reading about like an...
</details>

### 存算分离：S3延迟与P99设计的艺术

**主持人**: 没错。但问题在于 S3 提供了极佳的持久性，但延迟却非常高，通常在几百毫秒左右。
<details>
<summary>Original English</summary>
**Host**: because the problem with S3 is it has really good durability, but latency we're talking hun...
</details>

**Simon**: 是防。在 S3 上，对于 256 或 512KB 大小的对象，P99 延迟大约在 200 毫秒左右。
<details>
<summary>Original English</summary>
**Simon**: Yes. the P99 on a uh 256 or 512 kilobyte object on S3 um is around 200 milliseconds.
</details>

**主持人**: 额。
<details>
<summary>Original English</summary>
**Host**: Um...
</details>

**主持人**: 并且你提到 P99 延迟，是因为在谈论大规模系统时，你真正关心的是长尾延迟，对吧？
<details>
<summary>Original English</summary>
**Host**: and and you're saying P99 cuz like when you're talking large scale, you want to care about ...
</details>

**Simon**: 是的。我觉得当你……
<details>
<summary>Original English</summary>
**Simon**: Yeah. I think when you...
</details>

**主持人**: 这就是为什么我们不讨论 P50。
<details>
<summary>Original English</summary>
**Host**: That's why we're not talking about P50....
</details>

**Simon**: 在设计系统时，你必须针对 P99 延迟进行优化。特别是当你在遍历树状结构或图形结构时，如果你需要进行多次连续的 S3 请求，每一次都有 P99 的延迟，那么总延迟很快就会变得不可接受。
<details>
<summary>Original English</summary>
**Simon**: When you're designing a system, you want to optimize for the P99. And especially because wh...
</details>

**主持人**: 你很快就会撞上 P99。没错。如果你需要遍历一个树或多次访问它，这意味着你不可能直接对 S3 进行实时查询，对吧？所以你必须以某种方式把数据加载到内存里，或者使用某种非常快的本地 SSD 缓存。这就是你们架构的核心？
**Simon**: 是的，这正是我一开始为了满足好奇心而开始研究的。我当时并没有想着‘我要创立一家公司并为此筹集资金’。我只是想弄清楚：‘能不能用本地 NVMe SSD 来构建一个向量数据库，实现低延迟的同时，将所有数据归档到 S3？’ 这就是 Turbopuffer 的开端。
<details>
<summary>Original English</summary>
You're going to hit the P99 real quick. Exactly. So it's like if you're navigating a tree o... it was it was it was to satisfy a curiosity. It was not I did not set out to do this like I...
</details>

**Simon**: 它是为了满足好奇心而开始的。我起初并没有打算做这个。我写了一个原型，并尝试把它开源，看看有没有人会感兴趣。我发现人们对成本问题感同身受。很多公司之所以用不起向量数据库，就是因为内存的账单太高了。如果你能够提供一个只在查询时按需加载、数据持久化在对象存储（如 S3）上的 Severless 方案，他们可以省下大笔费用。
<details>
<summary>Original English</summary>
**Simon**: it was it was it was to satisfy a curiosity. It was not I did not set out to do this like I...
</details>

**Simon**: 你可以把这些数据分块，然后把它们存入文件中。这些文件就被称为“簇（Clusters）”。这样你就可以在查询时只加载相关的部分。
**主持人**: 这真的非常巧妙。所以这基本上和搜索引擎的倒排索引分块非常相似。
<details>
<summary>Original English</summary>
You get the clusters and then you put the clusters in files. The cl the files are called cl... Do you know what a reverse proxy is?...
</details>

**Simon**: 是的。
<details>
<summary>Original English</summary>
**Simon**: Do you know what a reverse proxy is?
</details>

**Simon**: 没错。通过这种方式，我们可以在查询时并行发出多路请求，只拉取我们需要的部分，从而将延迟降到最低。
**主持人**: 明白。那么，Cursor 是如何成为你们的客户的？我听说是他们主动联系你们的，因为他们也遇到了相似的问题。能讲讲这个故事吗？
<details>
<summary>Original English</summary>
I like I do know what it is. I just still don't know what what the reverse is about. But an... they were the first customer...
</details>

### 与Cursor的相遇：如何帮客户降低95%账单

**主持人**: 听说他们是你们的第一个客户？
<details>
<summary>Original English</summary>
**Host**: they were the first customer...
</details>

**Simon**: 他们是最早的客户之一。他们在我在 Twitter（现为 X）上发布了这个项目后联系了我。
<details>
<summary>Original English</summary>
**Simon**: the first the first no Um they they they reached out um after I just launched on on Twitter...
</details>

**主持人**: 明白了。
<details>
<summary>Original English</summary>
**Host**: Yeah.
</details>

**Simon**: 我当时知道这个系统是可靠的，因为我设计了一些不变式（invariants），比如即使你强行关闭节点，数据也不会丢失，因为状态都持久化在对象存储里。
**主持人**: 这就是存算分离（Separation of Storage and Compute）的优势。数据永远在安全的地方。
<details>
<summary>Original English</summary>
Um, and I knew it was reliable, right? I knew like I had these invariants like if you shut ... and everything else just sit in object storage and then we just hotload it in and out of th...
</details>

**Simon**: 是的，所有的索引和向量都存在对象存储中，当需要时，我们直接把它们热加载到内存中，用完再释放。
<details>
<summary>Original English</summary>
**Simon**: and everything else just sit in object storage and then we just hotload it in and out of th...
</details>

**主持人**: 这太有道理了。你打开代码库，几秒钟内数据就被加载到 RAM，接着进行极速检索，然后就释放掉了。这对那些不是 24 小时高频查询但数据量庞大的用户来说，简直是救星。但对于云厂商来说，这可能会减少他们的内存实例销量。
**Simon**: 的确。从单位经济学（unit economics）来看：
<details>
<summary>Original English</summary>
makes so much sense right you open the codebase a few seconds and it's in RAM and then the ... um the economics
</details>

**主持人**: 主要是成本考量。
<details>
<summary>Original English</summary>
**Host**: um the economics
</details>

**Simon**: 是的，从价格来看，这是非常罕见的，但我认为未来会发生得越来越多。他们在这方面确实走在了前列。
<details>
<summary>Original English</summary>
**Simon**: yeah price wise yeah it's and it's it's very it's very uncommon and I think it will happen right but they were ahead of their time
</details>

**Simon**: 我觉得他们当时也在考虑自己构建。他们发现了 Turbopuffer，这完美地匹配了他们的需求。我们交换了许多邮件，接着我做了个决定。虽然我当时完全不懂 B2B 销售。
<details>
<summary>Original English</summary>
**Simon**: and they I think they were I don't know if they were thinking of building it themselves. I think that's quite likely. Um, and they found Turppuffer and it just perfectly pattern matched into that. Again, I don't know if this dinner conversation happened or if this was just inside. Um, but it pattern matched something and so we exchanged a bunch of emails and then something compelled. I didn't know anything about B2B sales.
</details>

**Simon**: 现在的我很喜欢 B2B 销售。但在当时，我什么都不懂，我只是想帮他们，因为他们的单位经济学有些问题。所以我直接去了旧金山。我住在加拿大，但我飞到了旧金山，直接出现在他们的办公室里。当我到那里时，他们正在讨论一些 Postgres 的问题。
<details>
<summary>Original English</summary>
**Simon**: Now I love B2B sales. Um, I didn't know anything. I was just like I just want to help them because they they were they had some unit economics that didn't line up. So I just went to San Francisco, right? I live in Canada. I went to San Francisco and I showed up at the office and when I showed up at the office they um they were having some Postgress problem that they were discussing.
</details>

**主持人**: 是的，AWS Aurora 的那些问题。
<details>
<summary>Original English</summary>
**Host**: Yeah. The AWS Aurora problems. Yes.
</details>

**Simon**: 没错，是早期的那些问题。我当时问：‘你们有没有用 PG Analyze？’ 他们说没有。我说：‘好，那我们把这个跑起来，看看是怎么回事。’ 结果发现这和 Postgres 常见的问题一模一样，也就是 Autovacuum 跑得不够频繁。因此，他们很多本该走索引扫描的地方都变成了堆扫描。我们讨论了这些问题，我帮他们解决了很多数据库底层调优。这也建立了足够的信任。他们觉得：‘如果他懂怎么帮我们调优数据库，那他大概也知道怎么构建一个好数据库。’ 此时我找到了我认为在 Shopify 工作过的最好的工程师——我的联合创始人 Justine。她加入后做的第一件事就是用文件缓存替换了 Nginx 的反向代理缓存，直接缓存文件，这也非常有效。那天晚上，Cursor 的团队就决定我们要迁移了，并在接下来的一两周内完成了迁移。但在当时，Cursor 还是个很小的公司，对吧？
**主持人**: 是的，他们刚刚开启他们那不可思议的暴涨期。
**Simon**: 确实。我当时承诺能帮他们降低 95% 的账单。我们也确实做到了。Justine 和我把他们的上月账单和用我们之后的第一个月账单对比，确实降低了 95%。
**主持人**: 你很客气，没有直接说出前一个服务商的名字，但我可以替主说，那就是 AWS Aurora。这真的很神奇。不过这表明，作为一个初创公司，当你有坚定的信念时，有时冒一些看似不理性的风险是值得的。你通过上门帮忙、展示你对底层技术的深厚理解，给他们带来了极大的信心。快进到今天，Turbopuffer 已经大了很多。我昨天吃晚饭时听你讲了一个非常有趣的故事：你见到了黄仁勋（Jensen Huang），而他非常想说服你使用 GPU。你能讲讲那次会面吗？
<details>
<summary>Original English</summary>
Yeah. Early on. And I was like, "Oh, do you guys have PG Analyze?" And they said, "Oh, no, we don't." I was, "Okay, let's let's let's get that going, right? Let's look at it." And it was the same thing as it always is with Postgress, which is autovacuum hadn't run enough. And so, they had all of these like going to heat when they should be doing index scans and blah blah So we were talking about all of that and so I was just helping them, right? It was like my, you know, my database genes just like kicked in and I think this built enough trust with them that okay, well maybe if he knows how to help us with the database, maybe he also would know how to build one. And um at this time I'd also approached who I thought was the best engineer who ever worked at Shopify, my co-founder Justine. um and she'd come on and the first thing that she did was um remove the reverse proxy engine X cache with a file-based cache just a direct cache which again great like the S3 thing worked um and so she was online she was starting to work on it and um and cursor cursor cursor then that night was like okay well we're going to migrate and so they migrated everything over the course of like a week or two after that um but cursor was a small company back then right yeah and they were they just in the beginning of their massive rapid growth. Exactly. And I I told them that I was going to reduce their bill by 95%. And I did like we did. Justine and I did. We like they came on and their last bill with their previous vendor and the first bill with us, it was 95% lower. Yeah. And you're you're nice for not saying vendors, but I I can say vendors talks to them and and it's in the deep dive about cursor. It was it was ads Aurora specifically. Uh so
</details>

**主持人**: 噢，当时他们用的不是 Postgres 吗？那是……
<details>
<summary>Original English</summary>
**Host**: this was this was not this was not Postgress. Oh, this was a
</details>

**Simon**: 它是另一个数据库，但它应该还在我写的总结里，我们不需要提它的名字。但他们选择我们的首要痛点其实是可靠性。当然单位经济学也很重要。后来 Cursor 的联合创始人 Arvid 告诉我，他说：‘有几件事是绝对不能做的，其中之一就是你绝对不能把身家性命押在一家你是它唯一或最大客户的超早期初创公司上，除了 Turbopuffer。因为我太爱这帮家伙了。’ 这说明如果你做出高品质的产品，并展现专业度，好事自然会发生。
**主持人**: 是的，这绝对是一段佳话。那么，跟 Jensen 的见面是怎么回事？
<details>
<summary>Original English</summary>
**Simon**: it was a different one, but it's probably still in the write up. We we don't need to name names, but  uh yeah, but they were the reason they went there is reliability was their main main pain point. I'm sure the unit of comics would have been there, but yeah, this was and then what Swallow told me is he said like look like there's a few things that we did that you should never ever do and he said one of them you should never ever bet your business on a tiny startup where you are their only or biggest customer except for Turboper and he said I love love those guys. So I guess it just comes to show that even in your case like to me what this story is shows is is you can do things when you build highquality things and you're pushing for things good things can happen and on the other side of cursor when you're a startup it's okay to take sometimes irrational risks when you have conviction and it sounds to me that you gave them conviction by showing up in person by helping them by showing that you know you know your stuff like you suddenly brought in your your 10ish or eight years of Shopify experience and your curiosity and They probably took a risk because of that, not because you were some, you know, random vendor. They probably would have never done that. So, fast forward today,  uh, Turbopuffer is now a lot bigger. You're you're working on some some some cool things, but you have this very interesting business where for you CPUs are important, right? You run on mostly CPUs. And you told me a story over dinner yesterday that  uh you met Jensen  and Jensen he really wanted to sell you on GPUs. Can you tell me how that meeting went?
</details>

### 调侃黄仁勋：在Nvidia宣讲CPU的奇特经历

**Simon**: 额，是黄仁勋（Jensen Huang）对吧？
<details>
<summary>Original English</summary>
**Simon**: Um yeah, Jensen Hong, right?
</details>

**Simon**: 是的。我以前从未见过 Jensen。我们当时在 Nvidia 举办的一个活动上，需要做一些演示。那是在他们巨大的总部里，非常震撼。
<details>
<summary>Original English</summary>
**Simon**: Yeah. I just I'd never met  uh I'd never met  uh Jensen before. We were we were at an event at  uh at  at Nvidia and we were just doing  presentations. This is in a big HQ. Super impressive.
</details>

**Simon**: 没错。他们邀请了几家公司去聊聊我们的业务，以及如何与 Nvidia 进行合作。我那天可能处于一种比较搞笑的状态。我走上台说：‘大家好，我是来自 Turbopuffer 的 Simon。如果你们对这个名字感到好奇，我可以告诉大家，如果我们的数据库业务搞砸了，我们随时可以转型去做电子烟（Vapes，因为 puffer 也有吸烟的意思）。’ 我当时很紧张，所以脱口而出。接着他回复说：
<details>
<summary>Original English</summary>
**Simon**: Yeah, exactly. They've invited a couple companies to go and and um and and and talk about um  talk about our businesses and how we can partner with Nvidia and so on. And I I don't I I don't know. I was like I think I was in a goofy mood that day. And so I went up on on stage and I said, "Um, hey, I'm Simon from from from Turbopuffer." And  uh and yeah, if you're wondering about the name, it's like if everything goes south, we can always pivot into vapes. I was kind of nervous and this is what I this is what I said and then and then he said back to
</details>

**主持人**: 等等，当时房间里有谁？Jensen 本人吗？还是直接下属？
<details>
<summary>Original English</summary>
**Host**: wait who was in the room? Was it Jensen? Was it a direct report?
</details>

**Simon**: Jensen 本人在，还有大概 50 个他的直属下属或 Nvidia 的高管。因为你去那里就是为了寻找合作机会。所以我说：‘是啊，我们的 Plan B 是做电子烟。’ 然后 Jensen 看着我说（我当时已经很紧张了）：‘从你的幻灯片来看，也许你真的应该去卖电子烟。’ 哈哈，他没有真的这么说，但我当时不知道该回什么，所以我说：‘那 Jensen，你抽电子烟吗？’ 他没有回答。然后有人在我们公司的群里发消息说：‘Simon 刚刚问 Jensen 抽不抽电子烟。’ 这是一个伟大的开端。在去之前，我们团队还特别叮嘱我：‘Simon，千万别说那个以 C 开头的词（CPU），我们不能提 CPU。’ 结果上台后我根本停不下来谈论 CPU。我说：‘AVX 512 简直太棒了！我们超爱 SIMD！有这么多 CPU，而且它们又容易买到，CPU 领域的生态简直是一场狂欢！’ 我想我只差没说出‘我太庆幸我们不需要 GPU 了’。但我当时就是止不住地赞美 CPU。
**主持人**: 哈哈，我想你一定给他留下了非常深刻的印象。也许他现在的使命就是有一天必须让你们用上 GPU。但说到 CPU，你如何看待目前的超大规模云厂商（Hyperscalers）？你们现在在 AWS、GCP 和 Azure 上运行。我天真地以为，既然 GPU 短缺，那获取 CPU 应该很容易，对吗？实际情况是这样吗？
<details>
<summary>Original English</summary>
It was it was Jensen and then I don't I he has like I don't know if it's just 50 direct reports or it was like you know it was there was it was Jensen and then a bunch of the um like Nvidia Nvidia leadership, right? Um cuz you go there and then you talk about that you find opportunities to partner and work together, right? And so I said, "Yeah, you know, so plan B it could be that we could pivot into vapes." And then he said, I was already nervous. He said, "Judging by your slide, maybe you should." No, he did not. And and I didn't know what to say back to that. So I said, "Well, Jensen, do you vape?" He didn't he didn't answer the question. And then someone um someone on the um someone on the on the team um wrote to the whole company, Turbo Puffer Company, Simon just asked Jensen if he vapes. Um and then you know this is this is a great start right and um and then the team had team team had sort of talked to me beforehand was like Simon we got to make sure we don't say the cword we can't say CPUs and so I just couldn't stop talking about CPUs. I was like AVX 512 is so sick like we love SIMD and um like we we we like there's so many CPUs. They're so easy to get. like um it's just a riot in CPU land. Like you know I I don't I think I stopped short of saying I'm so glad I don't need GPUs but but it was just it I just couldn't stop talking about CPUs. Yeah. And so you know Jensen took an interest in that. Yeah. So who who knows like I'm sure you made you made a memorable version. Maybe he made it his mission now to like at some point get you guys onto GPUs. But speaking of CPUs, can you tell me a bit what you're seeing inside of the hypers scale the cloud providers you're now in AWS, you're  you're in GCP, you're on Azure. What I would think naively is there's a GPU shortage and when I talk with inference companies, they are and and and AI labs, they're just getting whatever they can do. I would think getting CPUs is should be easy. Is it?
</details>

**Simon**: 额，其实并不是。
<details>
<summary>Original English</summary>
**Simon**: No,...
</details>

**Simon**: 并不是这样。为什么？因为现在超大规模云厂商的所有资本支出（CapEx）都倾注到了 GPU 上。这导致 CPU 的供应也开始变得紧张。你可以向我们介绍一下在这方面的动态吗？
<details>
<summary>Original English</summary>
**Simon**: it's not anymore. Why? What's happening? Can you tell us about the dynamics on on on the wh...
</details>

**Simon**: 是的。我认为 GPU 会继续保持稀缺。可能未来会有所缓解，但这导致云厂商在 CPU 服务器的更新换代上变慢了。
<details>
<summary>Original English</summary>
**Simon**: Yeah. So I think that GPUs will probably continue to be scarce. Like I don't know, maybe th...
</details>

**主持人**: 确实。
<details>
<summary>Original English</summary>
**Host**: Micron.
</details>

**Simon**: 并且现在强化学习（RL）也消耗了大量的 CPU。所有的智能体（Agents）在运行推理时，也需要做大量的 CPU 预处理和后处理工作。这推高了对 CPU 的需求。
<details>
<summary>Original English</summary>
**Simon**: Um and so I think as we RL is consuming a lot of CPU and then also just all of the agents a...
</details>

### 硬件选型：云厂商CPU的性能与选择

**主持人**: 是的。昨天我和你的团队一起吃晚饭，你们提到你们实际上有自己的一套方法去选择具体的 CPU 型号和配置？
**Simon**: 没错。我们和云厂商密切合作，去探讨我们需要什么样的机器配置。
<details>
<summary>Original English</summary>
Yeah. And yesterday I was at a dinner that you hosted with your team where you actually hav... Exactly. And I mean you you work with the clouds, right? We work with them to talk about wh...
</details>

**Simon**: 比如我们会看不同机型的性能。
**主持人**: 你提到的“Skew（规格）”是那种不同机器类型的代号吗？
<details>
<summary>Original English</summary>
Exactly. And I mean you you work with the clouds, right? We work with them to talk about wh... skew meaning that's the it's a fancy name for like the different machine types...
</details>

**Simon**: 对，这是机器型号的简称。
<details>
<summary>Original English</summary>
**Simon**: skew meaning that's the it's a fancy name for like the different machine types...
</details>

**Simon**: 没错，比如 C4D 或者 GCP 上的其他实例代号。
**主持人**: 你们最喜欢哪一种？
<details>
<summary>Original English</summary>
yes exactly right like you know C4D or IG or whatever they're called... what's your favorite one...
</details>

**Simon**: 额，我们目前非常喜欢……
<details>
<summary>Original English</summary>
**Simon**: um we really like right now the um C4 force on on GCP....
</details>

**Simon**: GCP 上的 C4 实例。
<details>
<summary>Original English</summary>
**Simon**: um we really like right now the um C4 force on on GCP....
</details>

**主持人**: GCP。
<details>
<summary>Original English</summary>
**Host**: GCP....
</details>

**Simon**: 另外，GCP 上的 Z4D 实例在经过我们的一系列 SIMD 和编译器优化后，性能也表现得极为强劲。
**主持人**: 明白了。你之前在多伦多，现在在旧金山，你如何看待这边的创业氛围？听说你一开始对硅谷的某些“商业常识”感到不太习惯。
**Simon**: 是的，我想我当时在旧金山待的时间还不够长。
<details>
<summary>Original English</summary>
Um the Z4Ds are also performing really well um now that we've done done a bunch of of um of... Yeah, that's sort of like you know and it's just I don't think I'd spend enough time in San...
</details>

**Simon**: 我当时不知道如何和这边的投资人或同行沟通，因为他们都在大谈特谈各种复杂的叙事和术语。而在我看来，商业的本质就是你的收入应该大于支出。
<details>
<summary>Original English</summary>
**Simon**: Yeah, that's sort of like you know and it's just I don't think I'd spend enough time in San...
</details>

**Simon**: 额，那是我唯一知道的“商业 101”原则，只要你赚钱，你就是一家好公司。
**主持人**: 哈哈，这非常朴素且正确，但这在硅谷有时候反而成了非主流。作为一个外来者，你是怎么看待融资这件事的？
<details>
<summary>Original English</summary>
Um that's just that's all I knew. You you were doing business 101 as as long as you're maki...
</details>

### 创业融资的六大原因与避坑指南

**Simon**: 我当时觉得自己像是一个局外人的平方。我成长于丹麦奥胡斯，一个安静的地方，然后在 Shopify 待了八年。那里和硅谷的玩法完全不一样。
<details>
<summary>Original English</summary>
**Simon**: I was I was an outsider. I was like an outsider squared, right? I grew up in Aus, Denmark a...
</details>

**Simon**: 对我来说，我不知道该怎么粉饰或包装。我们只是想要做这个，当我们不知道怎么用 PPT 去说服投资人时，我们选择用实际的代码和产品说话。我们非常清楚我们想构建什么。
<details>
<summary>Original English</summary>
**Simon**: um and to me it was just like I I don't know it just came from a when I don't know how to p...
</details>

**Simon**: 所以在 2023 年，我们决定正式推进这个项目。但同时我们也意识到我们需要一些资金来加速这个过程。
<details>
<summary>Original English</summary>
**Simon**: and so I we were it was very clear to us that we wanted to do this and but also it became c...
</details>

**主持人**: 嗯。
<details>
<summary>Original English</summary>
**Host**: Mhm....
</details>

**Simon**: 这就是我们在一月份选择进行第一笔融资的原因，因为在此之前我们全靠自己的积蓄和不领薪水在坚持，研发的沉没成本很高。我们想跑得更快。于是我们雇佣了 Buen 和 Morgan 作为前两位员工。第二个融资的原因是支持增长——当你构建了一些东西，你想告诉世界，并花钱去推广它。第三个融资原因，其实是创始人那该死的虚荣心（Ego）。
<details>
<summary>Original English</summary>
That was the reason that we raised capital in January because we funded R&D with a lot of our  own, you know, opportunity cost and not taking a salary and then paying the bills ourselves. Um, but we wanted to learn a little bit faster and so we hired Buen and Morgan as the first engineers. And then the second reason to raise capital is to fund growth. you've you you've built something and you want to tell the world about it and you want to spend more capital to do that. Um the third reason to to to raise capital is for the founders's ego.
</details>

**主持人**: 额，我很欣赏你这种坦率。
<details>
<summary>Original English</summary>
**Host**: Um it's a very popular appreciate the honesty.
</details>

**Simon**: 这是真的，这非常普遍，大额的融资数字、铺天盖地的媒体报道，这能给人极大的虚荣满足。但我认为这是为了融资最危险的原因。我希望有更多人能公开讨论这一点，因为当你这么做时，你其实是在稀释所有早期员工的股权。你为未来的员工设定了一个极高的估值门槛，挤压了他们的增值空间。对有些人来说，这变成了一场身份和地位的游戏，但这根本不是创业的本质。我们在这里是为了共同做大一家业务扎实的公司，这不应该成为融资的理由。但它确实一直在发生。第四个融资原因是为了回报和激励你的员工。这是一场漫长的旅程，你想和世界上最优秀的人一起工作，而优秀的人往往很稀缺，所以你必须给他们足够的回报。这就是我们在十二月份再次融资的原因——允许员工将他们的一部分股权变现，而不需要等到遥不可及的 IPO。第五个融资原因是战略合作，在旧金山有一些战略融资确实成就了某些伟大的公司。第六个原因可能是进行并购（M&A）之类的。但你必须非常诚实地面对你是出于这六个原因中的哪一个去融资的。我们第一次融资是出于第一和第二点，第二次则是出于第四点。
**主持人**: 第一次是研发，第二次是员工变现。
**Simon**: 没错。
<details>
<summary>Original English</summary>
It's very popular, very very popular, right? big numbers, lots of press, like um and I think this is a very very dangerous reason to raise money. And I wish that it was more talked about because you're diluting all of your employees when you do it. You are um setting a certain price for future employees and their upside. It's it's it for some people it can become a status game and that's not what it's about. We're here to build a big business together and this is not a reason to raise money. Um, but I I do think that it happens. Um, the fourth reason to to to raise capital is to reward your employees, right? It's a you're on a very long journey and you want to work with the best people in the world and by definition there's not that many best people in the world. So, you want to reward them. Um, that was the reason that we took more capital in December um was to allow the employees to liquidate some of their equity um instead of waiting for some like event like an IPO or something like further out. Um the fifth reason to raise is for a strategic partnership. There are strategic partnerships that have been made in this in this city that have made companies. Um and um the sixth reason to raise would be do doing M&A or or something like that. But it's like you have to be very honest about what reason you are raising in those six. First reason we raised was one and second reason we raised was four. Um so which which ones? The first reason to raise was R&D. R&D and the second reason was
</details>

**主持人**: 这非常有利于提供流动性给员工。
<details>
<summary>Original English</summary>
**Host**: um to provide liquidity to the employees
</details>

**Simon**: 员工。是的。
<details>
<summary>Original English</summary>
**Simon**: employees. Yep.
</details>

**主持人**: 我觉得这是一种非常健康和体面的方式。关于虚荣心的部分我们很少谈论，但在离科技生态圈越近的地方，融资的 status 游戏就越明显。最后，我想问问关于你们远程协作文化（Remote Culture）的问题。我注意到目前很多 AI 初创公司，无论是做 AI 基础设施还是 AI 应用，都倾向于线下集中办公，通常在旧金山或伦敦设有一个 HQ，因为他们觉得这样迭代更快、沟通损耗小，而速度就是生命。但你们一开始就是完全远程，并且至今依然如此。它是如何运转的？你们有什么独特的“Turbopuffer 秘诀”吗？
**Simon**: 是的，公司成立于 2023 年，当时正处于新冠疫情过后的转型期，许多公司都是远程运作的。我之前在 Shopify 的团队也是从一开始就完全远程，因为很难把所有优秀的架构师都搬到渥太华。所以对我来说这很自然。我觉得世界上大概只有两个城市能让你快速建立一家数据库公司，那就是旧金山和纽约，也许还有其他城市，但大多数成功的数据库都是在这两地诞生的。
<details>
<summary>Original English</summary>
I I think it's a it's a nice and healthy way and I think yeah the the ego part we don't talk about and the identity and especially the closer you are to to tech ecosystems where a lot of people are raising it it will be part of it. As closing I I wanted to ask you about the way you have a remote culture these days. I'm seeing it especially for companies that do anything with AI. May that be building AI infra or or or just AI products. A lot of them prefer in person having a HQ often times in SF or wherever your headquarters may that be London or somewhere else because you often these companies often find that they have faster iteration.  Uh it's just fewer layers cut in between and of course speed is is very very important. You have started full remote and you're still full remote. how is it working?  Uh, and what kind of quirks or like or turbo buffer ways have you found to to make this work better? Yeah, I think so. The the company started in in 23. So, sort of like on the on the on the cusp of COVID where a lot of companies were just remote.  Um, the Shopify infochain was remote since the very um very beginning because it was very difficult to get them all to move to Ottawa.  Um, and so it was natural to me. It's like, okay, I think there's kind of maybe two cities where you can build a database company fast, and that's San Francisco and and and maybe New York. There are maybe other cities, right? But that's like kind of where it's been done. Y
</details>

### 远程文化与Campfire工作法

**Simon**: 如果你不愿意搬到这些城市，你就必须全面拥抱分布式模型。
<details>
<summary>Original English</summary>
**Simon**: and so if you don't want to do that, I think you have to go allin on on on some distributed model.
</details>

**Simon**: 所以我们一直在探索这种分布式模型对 Turbopuffer 意味着什么。远程并不意味着不进行线下聚会。我们每年会把所有人召集在一起两次，去不同的地方。比如今年早些时候我们在班夫（Banff），之前还去了墨西哥城。这在远程公司里算比较常见的。但在 Turbopuffer，我们引入了一个概念叫做“营火（Campfires）”。营火的概念是：每当有几个人碰巧聚集在某个地方时，我们就称之为一个 Campfire，并鼓励其他任何想去的人加入。比如本周在旧金山就有一个 Campfire，因为我来这里参加会议，还有其他事情。所以我们邀请团队所有人来，一起去拜访客户、举办客户晚宴等。我们把这当成一个正式的活动，花时间在一起。当然，我们不强求每个人每一次都去参加 Campfire。有些人就想关起门来写代码，这完全没问题。我们有员工一年只参加两次全员聚会，其余时间都待在家里陪伴家人，从来不坐飞机，这完全符合我们的模式。但也有人可能每两周就坐一次飞机。前几天有人看到纽约有一个 Campfire，大家从纽约的会议室连线，她觉得太有 FOMO（错失恐惧症）了，直接打了个 Uber 冲去渥太华机场，买票飞到纽约和大家一起聚会。我觉得这太棒了！我们还引入了一个机制：如果你在外面做了技术分享、写了技术博客，或者做了一些对公司有额外贡献的事，我们会给你“Turbo 积分（Turbo Credits）”。Turbo 积分可以让你在下一次出行时将机票升级到商务舱，这鼓励了大家多去线下聚会。现在 Turbo 积分似乎开始有了它自己的生命，有人在讨论要不要建立一个“中央银行”对 Turbo 积分实行利率调节，甚至搞一个 Turbo 积分的预测博弈市场。这非常有趣。对于像今天这样的会议，我们的工程师如果想和客户交流，在展台站一整天是极其耗费精力的，所以如果你去站了两天展台，你就可以获得一个 Turbo 积分。我们就是通过这些有趣的小机制来鼓励大家在想见面的时候去见面。
<details>
<summary>Original English</summary>
And so we've tried to figure out what does that distributed model mean for Turbopuffer? It doesn't mean the absence of in person. we get everyone together twice a year in in some in in some location.  Uh earlier this year we were in in B, right? And then we were in Mexico City and so on. So it's like that's that's not that uncommon.  Um but one of the things that we we we've been trying to do is we have this concept called campfires. And the concept of the campfire is that when a couple of people just sort of randomly congregate in a place, you call it a campfire and you encourage as many people as you want to come and join. So, for example, this week is a Turbo Puffer campfire in San Francisco because I'm here for this conference and a bunch of other things. And so, everyone is invited to come like we're going to go meet customers, right? We're going to put on dinners for our customers and things like that. And we just make a thing out of it and and spend time together. And  uh we encourage everyone to come. We've also gone to the extent now of um we want to encourage that, but not everyone not everyone needs to go to the campfire all the time. Some people just want to, you know, lock in and hacks into 10 and that's great. We have people that just make it to the offsites twice a year and otherwise they're home, they're with their families and they don't they don't spend time on an airplane.  Um, fantastic. Like that is completely compatible with this model. And there are other people at the company who are on a plane probably every two weeks.  Um, we had someone the other day where they saw a campfire happening in New York and everyone was dialing in from a meeting room in New York and she had so much FOMO that she took a Uber straight to the airport in Ottawa and flew to flew to New York to hang out with the team, right? And I think that's fantastic.  Um and we've also introduced these things where um if you if you  uh if you do a conference talk or a blog post or something like that at Turbo or something a bit extracurricular, we give you a turbo credit and a turbo credit allows you to upgrade your next flight to business class which again encourages spending time together with the team.  Um and now I mean Turbo Credits are probably going to take on a life of their own. Someone was talking about doing a central bank and doing interest rates on the Turbo Credits. um and doing a betting market on the turbo credits. And so like this might take on its life on its own. Um and  uh you you know if you  um if you're at a conference like this, there's some of the our engineers here who are just want to interact with customers and be on like and standing on a like expo floor all day is quite taxing. And so if you do that for two days because you want to do it, oh you get a turbo credit, right? And so it's just like these fun little things that we try to do to to to encourage people to meet if they want to meet.
</details>

**主持人**: 非常感谢。在这场交流中，最让我感到有趣的是，虽然有很多 AI 公司将 Turbopuffer 作为基础设施层，但在我们刚才的谈话中，我们其实很少谈论 AI，而是花了很多时间谈论工程原则、追求极致、保持好奇心，以及人与人之间的连接——共同工作、互相信任是多么重要。非常感谢你的分享。让我们为 Simon 献上热烈的掌声！非常感谢！
**Simon**: 谢谢，这棒极了。谢谢大家。
<details>
<summary>Original English</summary>
Thank you. Well, in this session,  uh, what I found very interesting is Turbopuffer is a so many AI companies are using you as an infrastructure layer, but in this conversation, we managed to talk very little about AI and a lot more about engineering principles, pushing, being curious, and the human connection, how important it is for people to work together, to trust each other. So just thank you very much for that. So, let's give a big round of applause for Simon. Thank you so much. This is great. Thank you.
</details>