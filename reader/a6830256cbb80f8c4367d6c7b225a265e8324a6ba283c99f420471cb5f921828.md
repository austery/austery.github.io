---
author: All-In Podcast
date: '2026-07-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-ILKiOU5iAQ
speaker: All-In Podcast
tags:
  - semiconductor
  - ai-application
  - token-economics
  - quantum-computing
  - software-development
title: 英特尔的失落与 AI 编程的革命：对话帕特·基辛格与安东·奥西卡
summary: 本期访谈深入探讨了半导体巨头英特尔在财务导向下的战略失误与重塑之路，分析了苹果自研芯片与英伟达 CUDA 生态的崛起。同时，Lovable 创始人分享了 AI 时代下 Vibe Coding 与定制化软件的革命性演进。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Intel
  - TSMC
  - Nvidia
  - Apple
  - Lovable
products_models:
  - CUDA
  - Claude
media_books: []
status: evergreen
---
### 辉煌与迷失

**主持人**: 你在**英特尔（Intel）**工作了很长时间。
<details>
<summary>Original English</summary>

**Host**: spent a long time at Intel.
</details>

**帕特·基辛格**: 是的。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah.
</details>

**主持人**: 而且……
<details>
<summary>Original English</summary>

**Host**: And uh
</details>

**帕特·基辛格**: 也就 34 年而已。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: only 34 years.
</details>

**主持人**: 34 年。
<details>
<summary>Original English</summary>

**Host**: 34 years.
</details>

**帕特·基辛格**: 是的。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah.
</details>

**主持人**: 这可能是美国历史上最伟大的公司之一。然后它彻底偏离了轨道，被**英伟达（Nvidia）**、**台积电（TSMC）**，在某种程度上还有**苹果（Apple）**给彻底击败了。曾经我们经历过辉煌的 **Intel Inside** 时代。我们买电脑都是看，嘿，是不是奔腾处理器，还有那个经典的标志性声音。
<details>
<summary>Original English</summary>

**Host**: Probably one of the greatest American companies uh ever. And then absolutely went off the rails and got absolutely demolished by Nvidia, TSMC, uh and I guess Apple to a certain extent. So you had this incredible Intel inside moment. We bought our computers based on, you know, hey, the Pentium and that sound
</details>

**帕特·基辛格**: 没错，兄弟，Intel Inside。那么，我们来谈谈事情是怎么变糟的。什么做对了，然后……
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Intel inside, baby. Intel insideum. And so, let's talk about how things went wrong. What went right and then
</details>

**主持人**: 以及你在那里待了那么久，后来离开了一段时间，然后又回来了。但期间似乎发生了一些关键的错误，是我们可以吸取教训的。所以，让我们直接切入正题。作为一家美国公司，英特尔曾经取得了巨大的成功，现在我认为它正在合理地回归。但当我们回顾并进行复盘时，当年的错误是什么？如果从方向上来看，我们会改变这家公司的什么走向？
<details>
<summary>Original English</summary>

**Host**: how did it and and you were there for a long time. You took a break and then you came back. But there seemed to be have been some critical mistakes that we can learn from. So, let's just embrace it and go right into it. tremendous success as an American company coming back now I think uh reasonably but when you when we look back on it and we do our post-mortem what were the mistakes a and what would we change in terms of the direction of that company
</details>

**广告播报**: 如果你今天从基本原则出发去构建一个全球金融系统，你绝对不会把它建立在有 50 年历史的传统架构上。你会构建像 **Airwallex（空中云汇）** 这样的平台——一个专为全球账户、卡片和支付而设计的原生 AI 平台，旨在让整个世界感觉像一个本地市场。其他公司只是将 AI 拼凑在破碎的旧基础设施上，但 Airwallex 从第一天起就是为智能时代而生的。停止支付传统税，开始在 airwall.com/allin 构建未来。Airwallex，为未来而建。
<details>
<summary>Original English</summary>

**Ad**: if you were building a global financial system from first principles today you wouldn't build it on 50-year-old legacy rails you'd build airwalls one AI native platform for global accounts cards and payments it's designed to make the entire entire world feel like a local market. Others are bolting AI onto broken infrastructure, but Airwall was built for the intelligent era from day one. Stop paying the legacy tax and start building the future at airwall.com/allin. Airwall built for the future.
</details>

### 财务人治国

**帕特·基辛格**: 在我的一生中，有很大一部分时间是在那里度过的。我 18 岁就加入了英特尔。我是在英特尔度过青春期的，对吧？我常开玩笑说，我来得太早了。**安迪·格鲁夫（Andy Grove）**、**罗伯特·诺伊斯（Robert Noyce）**、**克雷格·贝瑞特（Craig Barrett）**，对吧？我是在这些人的熏陶下长大的。他们是我的导师，是我崇拜的人，而且他们都是深厚的技术领袖。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Having spent so much of my life there, you know, I view it. I joined when I was 18. I went through puberty at Intel, right? I joke, right? I was just like, you know, I am so early. uh Grove, Noise, Bar uh Barrett, right? Uh and uh uh you know, they they were the people I grew up at, right? You know, so on. They were my mentors. They were the people I adored uh for it and they were deeply technical.
</details>

**主持人**: 安迪·格鲁夫。
<details>
<summary>Original English</summary>

**Host**: Andy Grove,
</details>

**帕特·基辛格**: 安迪·格鲁夫、**戈登·摩尔（Gordon Moore）**、罗伯特，这些都是深度技术型领袖。我记得当我第一次加入执行委员会时，在座的 20 人中大概有 15 人是博士。就是这么专业。而我认为英特尔偏离轨道的一个根本原因，就是当它开始由生意人来掌管的时候。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Andy Grove, Gordon Moore, Bob, you know, co-inventor, you know, these were deeply technical leaders. I remember when I joined the executive staff for the first time, you know, there was, you know, probably 15 of the 20 people that were in the room were PhDs, right? You know, it was just that technical. And, you know, I view one of the things that went off the rail was when it started to be run by business people
</details>

**主持人**: 而不是技术人员。
<details>
<summary>Original English</summary>

**Host**: as opposed to technical,
</details>

**帕特·基辛格**: 也就是那些只看账目的财务人员（Bean Counters）。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: the bean counters, the finance people.
</details>

**帕特·基辛格**: 是的。当我成为技术领袖并重回英特尔时，这已经是基本上 15 年来第一位重掌大权的技术背景 CEO。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah. And you know when I became uh CEO uh in 2001 that was the first technical leader in essentially 15 years
</details>

**主持人**: 对，这与此息息相关。如果你有一个商业背景的领导者，他会提拔谁？当然是商业背景的下属。所以我认为最根本的一点是，当你观察今天伟大的科技公司时，它们大多拥有深厚的技术底蕴。
<details>
<summary>Original English</summary>

**Host**: right you know associated with it you know and if you have a business leader who does he promote business leaders and you know right you know so I think one of the fundamental things is and you know as you look at the great technology companies uh today you know they're deeply technical
</details>

**主持人**: 而且通常是由创始人主导的。
<details>
<summary>Original English</summary>

**Host**: and founderled typically
</details>

**帕特·基辛格**: 没错。即使他们不是创始人，比如萨提亚·纳德拉（Satya Nadella）不是创始人，桑达尔·皮查伊（Sundar Pichai）也不是创始人，但他们是非常资深的技术专家。当你需要做出那些涉及数十亿美元、极其硬核的技术决策时，你不能通过看 Excel 电子表格来做决定。如果光看表格，那看起来就像是个糟糕的投资，除非技术趋势证明它才是正确的投资。我认为这是最根本的事情之一。显然，在我回来的前五六年里，英特尔把 1000 亿美元回馈给了股东。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: you know and even if they're not you know Satcha is not a founder no right? You know, Sundar is not a founder as well, but they're deeply technical individuals. And when you're making these hardcore technical, you know, decisions that affect billions of dollars, you don't do that through a spreadsheet. That's a lousy investment, right? Unless the technology trends make it the right investment. And I think that's one of the fundamental things. And obviously you know in the five years uh five six years before I came back you know Intel gave $100 billion to shareholders.
</details>

**主持人**: 哦，股息……
<details>
<summary>Original English</summary>

**Host**: Oh the dividends
</details>

**帕特·基辛格**: 还有股票回购。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: and stock buybacks
</details>

**主持人**: 一千亿。如果把这一千亿用在别的地方该多好。你会用它来做什么？你可能会去为 iPhone 制造芯片，而当年英特尔错过了这个机会。
<details>
<summary>Original English</summary>

**Host**: a hundred. What I wouldn't have done for another hundred billion dollar on the uh what would you have done? You probably would have made chips for iPhone which Intel passed on. Yeah.
</details>

**帕特·基辛格**: 是的，没错。但在我回到公司之前，英特尔已经有十年没有建造过新工厂了。这简直不可思议，你怎么能不建新厂？你怎么能不去购买 **EUV 极紫外光刻机**？所有这些决策，只有技术专家才会坚持去做，因为单纯从眼前的财务数据来看，这些投资的经济回报并不好看。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah. you know, but you know, it hadn't built a new factory in a decade when I got there. It's like, you know, how can you not be building? How could you not buy EUV machines? You know, there's just all of these things, you know, that you would only do as a technologist because the economics behind them by themselves were not good.
</details>

**帕特·基辛格**: 对我来说，回归技术核心是最根本的事情。作为领导者，你总会做出好的或坏的决策，每个企业在发展过程中都是如此。但从根本上说，这是一门技术业务，你需要技术专家来运行技术，然后技术专家再去雇佣技术专家，组建专业团队，再吸引最优秀的人才。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: So, you know, it's getting back to the core of technology to me that was, you know, the fundamental thing. You know, you make good decisions, you make bad decisions as leaders. Every business uh does that uh as they go along but uh you know fundamentally this is a technology business and you need technologists running technology uh that then hires technologists that are sitting at the staff that then hire the best technologist you know you know
</details>

### 抉择自研芯

**主持人**: 并且要在未来可能产生重大影响的领域进行大刀阔斧的押注，就像滑冰要滑向冰球将要到达的位置一样。如果你看苹果，他们在过去 15 年里做着同样的事情：股票回购、发放巨额股息。直到今天，他们依然是所有公司中持有现金量最大的。他们买下了什么公司？他们只在边缘进行一些非常小规模的收购。我认为他们最大的一次收购是 Beats，因为他们想进入某些特定的用户群体，比如他们无法打入的安卓阵营。但这真是一个巨大的时间浪费。正如你所说，他们本可以做这么多惊人的事情。跟我说说 2008、2009 年的**史蒂夫·乔布斯（Steve Jobs）**，他决定我们要研发自己的芯片。那次决策的影响极其深远。那是一个秘密项目，还是说你们当时已经知道他在做这个？他通知你们了吗？
<details>
<summary>Original English</summary>

**Host**: and take big swings at you know categories that could matter in the future like skating to where the puck's going. If you look at Apple, they did the same thing for the past 15 years, buying back the stock, tremendous amount of dividends. They're the largest holder of capital of any company, I believe, to this date. And what if what companies do they buy? They buy little tiny acquisitions on the margins. I think the largest ones was was Beats cuz they wanted to get inroads into, you know, certain uh demographic segments like in the Android space that they couldn't get into. But my god, what a colossal waste of time. Like you said, they could have done so many amazing things. Tell me about Steve Jobs in 2008, 2009 deciding, I think we're going to make our own silicon and that impact because was that a covert product project or did you guys know he was doing that? Did he inform you?
</details>

**帕特·基辛格**: 嗯，那似乎是另一个分水岭。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Well, that seemed to be another one of those forks in the road.
</details>

**帕特·基辛格**: 史蒂夫是一位令人难以置信的领袖，但他也是一个极其无情且难以对付的领导者。你可以去读沃尔特·艾萨克森（Walter Isaacson）写的那本关于他的传记。这些年来，我和史蒂夫进行过很多很多次谈话。当时他们转向英特尔并采用 **Centrino（迅驰）** 芯片时，这是一件大事。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah, you know, Steve was an incredible leader. You know, he was also a ruthless leader, right? You know, very difficult. you know, read Walder Isaxson's book on him uh as well. I had many many conversations with Steve over the years uh you know, for it. Um but you know, when they moved to Intel and the Centrino chip, it was a big deal.
</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: Yeah.
</details>

**帕特·基辛格**: 没错。他们对英特尔提出了极其苛刻的要求。比如把芯片做小、降低功耗，他们是一个极其挑剔的客户。当他不再相信英特尔能持续做到这些时，他就启动了自研项目。他们收购了 **P.A. Semi** 这样的小公司，开始建立核心能力。起初只是内部做一些小芯片，这并没有引起太大反响，但随后这些小芯片变得越来越大。史蒂夫是这方面的大师，他通过启动这些小型项目在公司内部逐步建立起核心能力。我记得当我们第一次与史蒂夫讨论将 Mac 操作系统从之前运行的 PowerPC 架构移植到英特尔 x86 架构时，英特尔对自己在硅片、软件、编译器和操作系统方面的能力感到非常自豪。我们说：“史蒂夫，我们来帮你把操作系统移植到 x86 上吧。”我清楚地记得史蒂夫回答道：“在过去的四个版本里，我一直在悄悄做这件事。”
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. And they were putting extraordinary demands on Intel. You know, make the chip smaller, drive lower power. They're demanding uh customer. And when he was no longer convinced that we could continue to do that, you know, he started the project, right? You know, and if you remember what was it, you know, you know, uh, P semi, you know, they acquired some small companies, started to build some competency, but, you know, they did a few little chips internally. It wasn't a big deal and then the little chips got a little bit bigger, you know, and Steve was a master of this, you know, just starting, you know, these small efforts to build core competence inside the company. Uh I remember when we had the first conversation with Steve about uh porting the uh operating system to the Intel chip from the power chip that they were running on before they moved to Intel. And we were quite proud of the silicon software competencies that we had and compilers and operating systems, you know. So Steve, we'll help you port the operating system to the x86. And I remember that Steve said, \"I've been working on that for the last four releases.\"
</details>

**帕特·基辛格**: 他一直在苹果内部为可能发生的事情储备核心技术。这让我感到极其震惊。“我已经默默移植了过去四个版本。”
<details>
<summary>Original English</summary>

**Pat Gelsinger**: He had been preparing the core technologies inside of Apple for something that might happen uh in the future, you know, and he was already, you know, to me, I just remember I was just shocked. I, you know, I've ported the last four releases
</details>

**主持人**: 没错。
<details>
<summary>Original English</summary>

**Host**: Yeah.
</details>

**帕特·基辛格**: 就是这样。这就是他们如何跨入半导体领域并开始自研芯片的。史蒂夫当时心想：“我不确定我能一直依赖英特尔来保持行业领先，但我可以开始将系统设计与芯片设计进行深度协同优化，而不是依赖一个主要针对 Windows 环境优化、却不一定完全契合 iOS 系统的通用芯片。”这绝对不是普通的供应商关系，他没有抱怨“你这个供应商搞砸了”，而是直接说“我可以自己提供更好的解决方案”。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. You know, it was that kind of thing. And that's how they got into the semiconductor, you know, doing their own semiconductor. Hm. I'm not sure I can rely on Intel to be that much ahead of the industry and I can start optimizing the system design with the silicon design as opposed to relying on one that's been somewhat optimized for a Windows environment versus an iOS environment, you know, in their uh operating system. And you know, it was just, you know, uh, you know, it was never that kind of thing. They sort of said, you know, right, you failed as a supplier. No, I can supply myself better.
</details>

### GPU的崛起

**主持人**: 没错。然后**黄仁勋（Jensen Huang）**决定全力以赴开发这些显卡。这简直是难以置信的机缘巧合，这些显卡恰好也非常适用于加密货币和运行 AI 任务。
<details>
<summary>Original English</summary>

**Host**: Yeah. and Jensen uh decides, hey, he's going to go all in making these video cards and talk about just incredible uh serendipity that these happen to be also very applicable for cryptocurrency and running these AI jobs.
</details>

**帕特·基辛格**: 是的。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah.
</details>

**主持人**: 这到底是运气、实力，还是两者的结合？
<details>
<summary>Original English</summary>

**Host**: Was that luck or skill or combination of both there?
</details>

**帕特·基辛格**: 嗯，回看那段历程，黄仁勋当时只是在构建高性能计算机，即吞吐量机器。当英特尔在 CPU 领域处于鼎盛时期时，我们对他的机器嗤之以鼻。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Well, you know, when you think about that progression, you know, Jensen, he was just building high performance computers, you know, throughput machines. You know, when we were at the height of our strength on CPUs, uh, at Intel, we sort of scoffed at his machines. Yeah.
</details>

**主持人**: 没错。你们当时可能会觉得：“哦，那只是个显卡机器，只有一些游戏玩家想用那种东西，对吧？”行业里永远是大 CPU 搭配小 GPU。但是，当他们开始为其构建一个真正的软件栈时……
<details>
<summary>Original English</summary>

**Host**: Right. You like, oh, that's a graphic machine. You, you know, there's some gamers who want to use that kind of stuff, right? You know, it was always the big CPU and those little GPUs. But when they started to build a real software stack, Yes. with it, right?
</details>

**帕特·基辛格**: 没错，就是 **CUDA** 平台和 SIMT（单指令多线程）技术。他们每个版本都把它做得更好一点，让它变得更强大。突然之间，日本的高性能计算（HPC）极客们说：“嘿，我们可以用这些显卡来运行高性能计算。”
<details>
<summary>Original English</summary>

**Pat Gelsinger**: you know, sort of, okay, this CUDA thing and SIMT as a technology, you know, uh, you know, uh, multi-threading and so on. And it just sort of kept getting a little bit better and a little bit better and it was a little bit jobslike in that way. You know, we're just making it better every release and it's becoming more robust and all of a sudden, you know, the crazy, you know, uh, Japanese HPC guys said, \"Hey, we could take those graphics cards and maybe start using them in HPC.\" H,
</details>

**主持人**: 这是一个分水岭。
<details>
<summary>Original English</summary>

**Host**: right?
</details>

**帕特·基辛格**: 是的，那是一个定义性的时刻。这不再仅仅关乎图形渲染，而是一个计算密度极高的平台，可以用来解决世界上一些最有趣的计算负载。我相信黄仁勋也会同意这一点。他们意识到这不再仅仅是显卡，而是通用的计算设备。而当时的 AI 社区刚刚度过了它的第五个“寒冬”，大家都觉得 AI 根本不会迎来突破。然而，围绕 CUDA 的社区一直在蓬勃发展，CUDA 的软件一代代变得更好。其实我在英特尔也发起过一个叫 **Larrabee** 的项目，试图用 x86 架构实现类似的事情，但就在我第一次离开英特尔的一周后，这个项目被取消了。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: you know, and that was sort of defining moment where it wasn't just about doing graphics anymore. This was a more computationally dense platform to start attacking some of the world's most interesting workloads. And I think Jensen would agree that was a defining moment and them sort of saying, \"Oh, these aren't just graphics cards anymore. You know, these are generalpurpose computing devices that can start applying to these other uh workloads.\" And you know AI was you know had gone through what its fifth nuclear winter by that point. We're just like man you know you know this is never going to matter right we're never going to you know get the breakthroughs but the community around it was continuing to develop uh you know for it and the CUDA software kept getting better uh generation by generation and uh you know I had a project at Intel Larabe right where we were trying to take the x86 and essentially do the same thing right you know for it and you know in my first departure from Intel the project was killed a week after I left
</details>

**主持人**: 啊……
<details>
<summary>Original English</summary>

**Host**: huh
</details>

**主持人**: 那样的话，世界本会大不相同，对吧？
<details>
<summary>Original English</summary>

**Host**: and the world would have been so much different right I
</details>

**主持人**: 这充分说明了持续创新、承担风险、进行基础研究以及技术复利的力量。威廉·吉布森（William Gibson）曾说，“街头总能为技术找到它自己的用途。”英伟达当年无法预测比特币的爆发，也无法断定显卡会成为挖掘比特币的绝佳方案；他们同样没有预料到 AI 会如此爆发，但因为他们提供了最好的计算底座，极客和黑客社区自然会找到它。当我们结束关于英特尔职业生涯的话题时，我们看到了苹果自研芯片，英伟达的崛起，然后还有台积电，这家台湾公司在芯片制造工艺上变得极其出色，而英特尔也错过了这班车。你能谈谈台积电的崛起吗？我们可以聊聊地缘政治，然后再谈谈 AI 芯片和风险投资。台积电的核心在于，他们一开始就秉持着纯代工（Foundry）的愿景。
<details>
<summary>Original English</summary>

**Host**: I mean it really I think it's illustrative of illustrative of what continuous innovation taking some risks and doing that fundamental research and the compounding power of technology because I think it was William Gibson who said the street finds its own use for technology like Nvidia did not predict that this Bitcoin project would take over and that this would be the best way to do those computations, nor did they anticipate, I think, you know, that AI would take off, but because it was the best solution, the hacker community could kind of figure that out. Well, as we wrap on the Intel portion of your uh career, um, okay, Apple Silicon, that's one. Uh, and then you have Nvidia, and then you have this Taiwanese company, uh, that starts making, you know, really great at fabricating the these chips. Um and Intel missed that as well. Yeah. And and maybe you could talk a little bit about TSMC and their surging and we can even get into a little bit of the the politics of it now and then we'll get into some of these AI chips and venture investing. You know the thing with TSMC was they started with a vision of foundry
</details>

**帕特·基辛格**: 没错，他们想成为全行业的代工厂。这些工厂非常昂贵，需要 200 亿到 300 亿美元的持续投资。这在当时是一个极其惊人的愿景。而英特尔则是所谓的 IDM（整合设计与制造）模式。我们从来没有想过要把我们的工艺和工厂开放给第三方使用。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: right you know they were going to become the factory for the industry and again these factories are so expensive 20 billion 30 billion and uh the engineering and the continuous investment required to do it and you know it was a stunning you know vision uh at that point in time Intel was IDM as we called it the integrated design and manufacturing you We never worked to make our process and our factories available for third parties
</details>

**主持人**: 没错。
<details>
<summary>Original English</summary>

**Host**: right you know it was always this thing hey it's you know we do enough CPUs oursel you know we reuse it for chipsets and some of the other things that we're doing but it was never standardized in a way that it could be made available for a broad ecosystem
</details>

**帕特·基辛格**: 确实，没有通过 PDK（工艺设计套件）和通用设计工具进行标准化。在早期，我们甚至自己研发了许多 EDA（电子设计自动化）工具。我在职业生涯早期启动的项目之一就是 EDA 的奠基工作，包括第一个自动布线工具、第一个标准单元和第一代高级描述语言。但这些技术极其封闭。台积电打破了这种局面，他们表示：“我不关心这是谁的芯片，也不关心你在设计什么，我就是你的制造合作伙伴。”在当时，这部分业务微不足道，英特尔根本不在乎。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: using PDKs and all the design tools you know we did a lot of our own EDA tools ourself you know one of the projects that I started early in my career was the foundations of EDA, right? Uh as well, the first place and route, you know, the first standard cells, the first highle description language, you know, it was so proprietary and TSMC basically cut that in half and says, I don't care whose chip it is. I don't care what you're designing, I'll be your manufacturing partner. And at the time, that was such a trivial piece of the business, Intel didn't even care,
</details>

**帕特·基辛格**: 后来经过长期的稳定积累，加上苹果作为核心客户的强力推动，台积电变得极其强大。当我在 2021 年回到英特尔时，世界的格局已经彻底改变了，台积电的晶圆产量已经是英特尔的 5 倍。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: right? You know, so on. And then over steady progress over a long period of time and Apple as a customer driving them to be could be become really meaningful. You know obviously the world changed and when I came back uh to uh Intel in 2001 TSMC was producing 5x the wafers of Intel.
</details>

**主持人**: 哇。
<details>
<summary>Original English</summary>

**Host**: Wow.
</details>

**帕特·基辛格**: 是的，不是多 10%，而是整整 5 倍。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. Not 10% more 5x.
</details>

**帕特·基辛格**: 突然之间，代工模式成为了半导体行业的核心范式，只有英特尔和存储芯片行业是例外。现在我们看到了市值数万亿美元的芯片设计公司，以及像台积电这样市值万亿美元的纯代工公司。全行业都在高喊：“我们需要更多的晶圆，我们需要更多样化的设计创新，我们需要标准化的 EDA 工具层。”世界已经变了。当我重回英特尔时，新战略的核心逻辑就是：英特尔也必须成为一家代工厂。当时台积电对我们的晶圆产量比是 5 比 1，现在大概已经是 7 比 1 了。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah. And all of a sudden that model of foundry became the model of the semiconductor industry with two exceptions Intel and memory. you know, memory design and manufacture, right, for you know, that is uniquely different. And obviously, you know, we're seeing the, you know, $3 trillion memory companies just extraordinary, you know, and, you know, trillion dollar foundry company uh in TSMC. You know, the industry has said, I want a lot of wafers. I want a lot of innovation of different designs. I have a layer of standardization and EDA tools. And the world changed. And obviously as I came back to Intel that was one of the core thesis of the new strategy. Yeah. We must become a foundry as well five to one and now it's more like seven to one in terms of wafers you know to TSMC to and
</details>

### 芯片在岸化

**主持人**: 我们是否有能力将这些产能带回本土？显然我们通过了《芯片法案》（CHIPS Act）。给我们勾勒一下你认为未来会发生什么。显然台湾局势非常微妙。政府内部有些人认为在川普卸任后（除非他迎来第三个任期）可能会有变数。另一些人则认为可能早在 2027 年甚至 2028 年就会发生变化。那么，我们能否在合理的时间内在美国本土复制台积电的产能？如果中国决定对台湾进行封锁，而台湾决定“烧毁晶圆厂，让所有工程师飞往美国”，这会是一个灾难性的事件吗？
<details>
<summary>Original English</summary>

**Host**: are we going to be able to onshore that obviously we had the chips act and just give us broad strokes what you think is going to happen here in terms of obviously Taiwan is in play. Some people in the administration believe um it's going to happen the year after Trump's out unless he takes his third term. Other people believe like it was going to happen as early as 27 uh or maybe going into 28. So, are we going to be able to replicate that here in America in a reasonable amount of time, or is this like truly could be a cataclysmic event if, you know, god forbid, China decides, hey, we're going to blockade um Taiwan and and the Taiwanese decide, yeah, we're going to burn the fabs and we're going to fly out all of the engineers and ship them to America.
</details>

**帕特·基辛格**: 这个提问包含的信息量太大了。我们能用一个小时来讨论这个问题吗？
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Well, there's a lot in that question, you know. Do we have an hour to talk about this question?
</details>

**主持人**: 呃，我们只有 6 分钟了，不过，请尽你所能。
<details>
<summary>Original English</summary>

**Host**: Well, I mean we have six minutes, but Okay. Um, yeah, do the best you can.
</details>

**帕特·基辛格**: 好的。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Okay.
</details>

**主持人**: 我还想聊聊 AI 泡沫的话题。
<details>
<summary>Original English</summary>

**Host**: I want to talk also about the AI bubble.
</details>

**帕特·基辛格**: 关于这个，我极其快速地讲三点。首先，《芯片法案》确实正在发挥积极作用。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: So, super, you know, three things about this super quick. You know, one is the chips act is having benefit.
</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: Yeah.
</details>

**帕特·基辛格**: 当我们在 2021 年游说《芯片法案》时，美国本土仅占全球最先进芯片制造产能的 12% 左右。如今，这个数字已经提升到了约 18%。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. You know, when we started the chips act in, you know, in 2001 when I came back, the US was building about 12% of leading edge. Today, that number is more like 18%.
</details>

**主持人**: 好的。
<details>
<summary>Original English</summary>

**Host**: Okay.
</details>

**帕特·基辛格**: 我们正在取得进展，虽然还没达到 50%，还有很长的路要走。英特尔正在转型成为真正的代工厂。这是切实的进步。与此同时，台积电在美国设立的工厂也在逐步实现规模化运营。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: You know, we're making progress. It's not 50%. We have a long way to go, right? You know, Intel is starting to be a real foundry. Okay, that's real progress. Uh, and TSMC's factories are up and operating at scale, right? We have Samsung as well.
</details>

**主持人**: 好的。
<details>
<summary>Original English</summary>

**Host**: Okay.
</details>

**帕特·基辛格**: 第三，地缘政治局势表明台湾是地缘政治的咽喉要道。世界上绝大多数先进制程芯片都产自台湾。如果你去过台湾，你会发现那里几乎没有石油资源。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: And third, you know, the geopolitics say, you know, hey, Taiwan is a geopolitical choke point. You know, the vast majority of advanced silicon is produced in a, you know, in a geography that, you know, if you ever fly into Taiwan, there is no oil.
</details>

**主持人**: 没错，没有石油。
<details>
<summary>Original English</summary>

**Host**: No oil.\" Yes.
</details>

**帕特·基辛格**: 也没有天然气资源，完全依赖进口和海运维持。这非常让人担忧。我们需要更有韧性的供应链。如果台湾海峡真的发生冲突，全球经济将面临巨大挑战。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. No LG, right? You know, that's how the island run. That is scary, you know, to me. We need more resilient supply chains uh associated, you know, with it. And I don't think this is an alternative for the world because if it really does go bad over there, the economic consequence to the globe is cataclysmic.
</details>

**主持人**: 是的。
<details>
<summary>Original English</summary>

**Host**: Yeah.
</details>

**帕特·基辛格**: 这绝非危言耸听。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: This isn't a theory.
</details>

**主持人**: 不，完全不是。他们正在进行军事演练，地缘局势非常复杂。
<details>
<summary>Original English</summary>

**Host**: No, no. They're running exercises. They're being pernitious and
</details>

**帕特·基辛格**: 没错。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: right
</details>

**主持人**: 这非常具有挑衅性。
<details>
<summary>Original English</summary>

**Host**: pretty provocative in terms of
</details>

**帕特·基辛格**: 到底是 2027 年、2030 年还是 2035 年？无论具体哪一年，他们的意图长期以来一直是非常明确的。我们需要更有韧性的供应链来防范未来的风险。这是我倾注了大量时间和精力的事情，我们正在取得进展，但我们需要走得更快、做得更扎实。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Is that 2027? Is that 2030? Is that 2035? their intentions have been clear over a sustained period of time. We need more resilient uh supply chains, you know, forward. So, something, you know, I put a lot of my time and energy into and we're making progress, but we need to go faster, need to go more meaningful.
</details>

### AI泡泡探讨

**主持人**: 是的。让我们来谈谈 AI 的建设。你见证了 PC 革命、服务器时代以及互联网时代的爆发。这些都是非凡的基础设施建设，而目前这个可以说是终极建设——海量的数据中心、无数的芯片、庞大的推理需求。你认为这是个泡沫吗？我好像听你说过，这显然带有泡沫成分，但这里的风险因素是什么？是我们建设过度，还是说技术根本解决不了足够多的实际问题，以至于我们最终溺死在无用的 Token 之中？你在当下的局势中担心什么？
<details>
<summary>Original English</summary>

**Host**: Yeah. And let's talk a little bit about the AI buildout. I mean, you watched the PC revolution, servers, the internet. These were all extraordinary buildouts. And then this is the buildout to end all buildouts. the amount of data centers, the amount of chips, the amount of inference needed. Do you think it's a bubble? I think I've heard you say like it's it's obviously a bubble, but what what's the risk factor here? That we build too much uh or that the technology doesn't solve enough problems and we are swimming in tokens? What what worries you about what you're seeing now?
</details>

**主持人**: 这些公司的估值已经变得相当惊人。如果你运营过一家上市公司，你知道，如果他们的支出过大，而收益却没有跟上，人们很快就会对这些股票失去信心。
<details>
<summary>Original English</summary>

**Host**: the valuations of these companies has gotten quite extraordinary. And you know, if they build too much and they spend too much money and they don't make enough money, well, based on your experience with running a company, a public one, that's a lot of tension on it. When you don't make as much money as you're spending, people tend to fall out of love with these stocks.
</details>

**帕特·基辛格**: 是的。但我认为这里有一道“安全防线”或一线希望，它能确保我们在泡沫化道路上不至于走得太远，那就是**电力能源容量**的物理限制。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah. Well, I do think there, you know, there there is a silver lining here that guarantees we don't get too far ahead of oursel in terms of bubble, you know, and that is energy capacity.
</details>

**主持人**: 确实。
<details>
<summary>Original English</summary>

**Host**: Right.
</details>

**帕特·基辛格**: 没错。全球能源容量的增长率大约在 4% 到 5%。而在美国，我们在过去十几年里的年均增速仅为 1% 左右，这几乎让我们老旧的电网陷入了极为尴尬的境地。尽管目前各地正在积极扩建电力，但归根结底，如果没有足够的电力供应，根本没有人能平地建起数据中心并运行大量的 GPU。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. You know, energy capacity in the world is expanding four 5%. You know, in the US we had a decade at 1%. Right. You know, I mean, it's just hideous what we did to our energy grid, you know, over about a decade and a half. But now that's getting built out. But essentially, nobody's going to build and buy GPUs and build data centers if they don't have energy.
</details>

**帕特·基辛格**: 也就是说，电力能源成了炒作和泡沫狂热的硬上限。这让我感到一丝踏实。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: So essentially, you have an upper bound on how aggressive and how hyped and bubbled that we get. So I take a lot of soloulless in that.
</details>

**主持人**: 明白。
<details>
<summary>Original English</summary>

**Host**: Yeah.
</details>

**帕特·基辛格**: 另外，Token 的边际价值是什么？如果把 Token 看作智能的一种度量，那么它的价值在某种意义上是无限的。如果我有更多的智能，我就能优化供应链，做更好的金融决策，实现更高效的物流等等。所以，我们通过 Token 经济所释放的潜在价值在某种程度上是无穷的。特别是在发达国家面临劳动力短缺的背景下，我非常乐观地认为，这会是一个长达数十年的建设浪潮。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. You know, for it because what then is the incremental value of a token and if it's a measure of intelligence, it's somewhat infinite, right? You know, in the sense if I have more intelligence, I will do, you know, better supply chain. I will do better finance. I will do more, you know, efficient logistics. I will, you know, all of those things. So to me, the the potential value that we unleash in a token economic world is somewhat infinite, right? And particularly with labor shortages and so on that we see right in uh developed countries, I am an optimist, you know, that we're in a couple of decade buildout.
</details>

**主持人**: 哇。
<details>
<summary>Original English</summary>

**Host**: Wow.
</details>

**帕特·基辛格**: 没错，是数十年的建设，而不是一两年。我设定的一个大目标是必须让 AI 技术的性价比提升 10,000 倍。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Right. Not a couple of years, a couple of decades. One of the big objectives I've said is that I have to make AI 10,000x better,
</details>

**主持人**: 的确，现在的成本太高了。
<details>
<summary>Original English</summary>

**Host**: right?
</details>

**帕特·基辛格**: 没错，今天太贵了。我们希望将每个 Token 的成本和能源消耗降低 5 个数量级，从而触发**杰文斯悖论（Jevons Paradox）**，降低门槛，让 AI 的应用呈爆炸式增长，让全社会以更经济实惠的方式获取 AI。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: You know, it's way too expensive today. you know, we want to drop, you know, by five orders of magnitude the cost per token, you know, the energy, you know, per token so that we really do have Jevans law that we just explode the access to AI, right, in much more economic uh ways,
</details>

**主持人**: 在过去这一年里，杰文斯悖论似乎确实在起作用。天呐，Token 的价格越来越便宜，工具也变得越来越好。人们可能会想，“好吧，我就整天无限制地使用这些工具，”直到账单寄来时才意识到，“好吧，我还是得想办法从中获取实际的投资回报（ROI）。”但目前我们确实有像 Cerebras、Groq 这样在推理芯片和专用矩阵硅芯片上取得突破的公司。
<details>
<summary>Original English</summary>

**Host**: which it does seem like Jevans uh paradox has been at play over the last year, like, oh my lord, these tokens are so cheap and the tools are getting so good. Yeah, I'm just going to start using these tools all day long until the bill comes in and you're like, \"Okay, yeah, maybe I need to get some ROI out of this.\" But you do have these incredible companies, Cerebrris, Grock, etc. making inference
</details>

**帕特·基辛格**: 是的。如果我们能在降低能源成本、提高可用性并实现数量级的经济效益提升上取得成功，未来的二十年将是非常美妙的。在人类历史上，没有任何一个时期比现在更适合成为一名技术人员。我们将解决化学难题，我们将攻克语言障碍，我们将发明新材料，创造全新的交互形式，攻克癌症，将更多人从贫困中解放出来。现在是最好的时代。作为技术专家，我们正坐在引领时代的驾驶座上。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: dematrix silicon and so you know, and you know, if we accomplish right, you know, these orders of magnitude improving and token economics, availability, reduction in energy costs associated with it. You know, we just have a fantastic couple of decades in front of us. There has not been a time in human history where it's been better to be a technologist than the one we're in right now. We will solve chemistry. We will solve language. We will, you know, invent new materials, re, you know, new forms of, you know, uh, interaction, you know, uh, killing cancer, right? Lifting people out of poverty. There is not a better time to be alive than the one that we're in right now. And as technologists, we get to sit in the driver's seat of it.
</details>

**主持人**: 这非常了不起，你正在通过投资倾注你的热情。那么你对当前的这些估值怎么看？这看起来有点像我们经历过的互联网泡沫时期的估值泡沫。但这些公司似乎略有不同，比如 ElevenLabs 的收入已经达到了数亿美元，Lovable 似乎也有几亿美元的估值。这和当年的纯投机似乎不太一样。
<details>
<summary>Original English</summary>

**Host**: Pretty amazing. and you're investing uh and that's your passion. Now what do you think of these valuations? It's quite seems a you know if you live through the dotcom bubble we did see a disconnect there. These companies slightly different. We just had 11 labs up 600 million in revenue. Lovable I think they're at five or 600 million. So that's quite different than the do speculation. Yeah.
</details>

**帕特·基辛格**: 是的。根本的区别在于这些业务有真实的收入和切实的利润支撑。即便如此，每当估值倍数过高时，进行一些市场修正是好事，这能让市盈率等指标回到合理的区间。我预测接下来会有二十年的繁荣，但其间必定伴随着许多波动和修正。每次市场修正时，我们都应当心存感激，因为这能防止泡沫失控。我们经历过 SAS 软件的洗牌，未来在这个旅程中也还会有其他的洗牌。更不用说当“计算的三位一体”——传统计算、AI 计算和**量子计算（Quantum Computing）**融合时，世界将变得多么激动人心。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah. Well fundamentally we have real revenues you know real margins coming out of these businesses as well. You know that said anytime the multiples get too high okay some corrections you know and to me periodic corrections that keep the multiple you know earnings multiples and you know so on in reasonable things is good because this will not be a smooth curve you know I'm predicting two decades of goodness and there's going to be lots of disruptions along the way it's not going to be a smooth curve and every time we have one of those corrections say thank you right we're not letting the bubble get ahead of itself right you know hey we had the SAS apocalypse there's going to be other apocalypses on that journey when when industries get impacted by the capabilities that will be unleashed and that's even before it gets exciting and what I call the trinity of computing classical computing AI computing and quantum computing and when those three come together okay that's when things get really exciting
</details>

### 量子计算期

**主持人**: 在过去的 25 年里，人们总说“量子计算距离爆发永远只有 5 年”。它到底什么时候才能真正派上用场？
<details>
<summary>Original English</summary>

**Host**: quantum's been about 5 years away for 25 years um when is it actually going to do anything meaningful
</details>

**帕特·基辛格**: 就在这十年内。到 2030 年。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: this decade this decade. So by 2030,
</details>

**主持人**: 真的吗？
<details>
<summary>Original English</summary>

**Host**: yep,
</details>

**主持人**: 那在 2030 年它将产生什么实质性的影响？
<details>
<summary>Original English</summary>

**Host**: it'll be meaningful. What should we expect in terms of its impact in 2030? Like
</details>

**帕特·基辛格**: 你将能够开始运行目前计算机根本无法计算的任务。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: you know, you're going to be able to start doing things that cannot be computed today.
</details>

**帕特·基辛格**: 在化学和生物学领域，会有许多当今无法解决的难题迎刃而解。一些较容易的应用会是在物流领域，比如计算出将物品送达的最佳路径。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: You know, chemistry, you know, biology, there will be things that can't be computed today. You know, some of the easy things will be some of like the logistics where I will compute the best answer to get this thing to you, right?
</details>

**主持人**: 也就是旅行商问题（Traveling Salesman Problem）。
<details>
<summary>Original English</summary>

**Host**: Traveling salesman problem,
</details>

**帕特·基辛格**: 没错。所有这些复杂问题都将迎刃而解。大概在 2032 年或 2033 年，我们将攻克量子加密等底层安全难题。但在这十年里，我们将在多个行业看到量子霸权（Quantum Supremacy）的实际成果。我们知道如何构建量子比特，知道如何做量子纠错，现在我们也有了针对量子的算法。这已经变成了一个纯粹的工程规模化挑战。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: right? you know all of a sudden all of those problems uh obviously it's probably going to be you know 2020 2032 2033 when we solve you know things like encryption right yo you know where you know you'll have the fundamental Qday you know kind of implications but this decade we will see quantum supremacy uh results across multiple industries you know we know how to build cubits we know how to error correct cubits we now have algorithmics right against uh quantum and you know now it's just about engineering scale.
</details>

**主持人**: 谁会在这场量子竞赛中胜出？
<details>
<summary>Original English</summary>

**Host**: Who's going to win?
</details>

**帕特·基辛格**: 作为一个支持硅基光子技术路线的人，我显然看好 **PsiQuantum**，因为它是我们的投资组合公司之一。但你目前可以看到有四到五种量子计算的技术路径都展示出了相当好的成果，包括离子阱、光子路线和自旋路线等。现在的技术路径不再是瓶颈，量子纠错已经被证实是可行的。预测在 2030 年前我们就能看到有意义的业务成果。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Well, obviously I'm a SI quantum guy, right? Since that's one of our portfolio companies. But the thing that you're seeing is that you now have like four, five, six modalities of quantum that are demonstrating pretty good results, right? You know, across trapped ions, across, you know, photonic uh approaches, spin uh approaches. So, you now say modality is not an issue. Error correction's been proven uh across them. And you know, I think the race will be on and my prediction is meaningful results before 2030.
</details>

**主持人**: 哇，那大概就是 40 个月之后的事情。
<details>
<summary>Original English</summary>

**Host**: Wow. You realize thats about 40 months from now.
</details>

**帕特·基辛格**: 是的。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Yeah.
</details>

**主持人**: 这真的非常令人期待。非常感谢帕特与我们分享这些了不起的知识。很高兴见到你。
<details>
<summary>Original English</summary>

**Host**: Okay. Meaningful results. Thanks so much, Pat, for sharing all this incredible uh information and knowledge. Great to see him.
</details>

**帕特·基辛格**: 非常好。
<details>
<summary>Original English</summary>

**Pat Gelsinger**: Very good.
</details>

### 编程新浪潮

**广告播报**: 最有价值的对话很少发生在办公桌前。走廊洗手池旁、晚餐席间，或是与创始人的快速电话沟通。**Plaud Note（挂载式 AI 录音笔）** 可以夹在身上，免提捕获并记录这一切。
<details>
<summary>Original English</summary>

**Ad**: Your most valuable conversations rarely happen at a desk. The hallway sink, the dinner, the quick founder call. Plaude no pins clips on and captures all of it hands-free.
</details>

**主持人（杰森）**: 安东（Anton）是我最喜欢的创始人之一。他是 **Lovable** 的创始人。我为什么喜欢这位创始人？因为他构建了一个让人上瘾的产品。
<details>
<summary>Original English</summary>

**Host (Jason)**: Oika is one of my favorite founders. He's the founder of Lovable. Why do I love this founder? Uh well he's built a product that people are addicted to primarily Anton the
</details>

**安东·奥西卡**: 这基本上就是 Lovable 的使命。
<details>
<summary>Original English</summary>

**Anton Osika**: essentially that's the mission of lovable
</details>

**主持人（杰森）**: 我们的使命是赋予人类更强大的能力。
<details>
<summary>Original English</summary>

**Host (Jason)**: mission I talk about empowering humans. empowering humans
</details>

**安东·奥西卡**: 首先是解决构建产品的鸿沟。
<details>
<summary>Original English</summary>

**Anton Osika**: and the first gap is to build a product.
</details>

**主持人（杰森）**: 第二个鸿沟是围绕该产品建立起一门商业业务，对吧？
<details>
<summary>Original English</summary>

**Host (Jason)**: The second gap is to build a business around that product, right?
</details>

**安东·奥西卡**: 没错，Lovable 的每一位成员都在努力填补这两个鸿沟。
<details>
<summary>Original English</summary>

**Anton Osika**: And now at everyone at Lovable, we're we're working on both of these two gaps, right?
</details>

**安东·奥西卡**: 在第一个鸿沟上我们已经取得了巨大进展。我们目前看到每周在平台上创建的新项目多达上百万个。
<details>
<summary>Original English</summary>

**Anton Osika**: The first one, we got very far. We're seeing a million new projects built every single week on the
</details>

**主持人（杰森）**: 太不可思议了。
<details>
<summary>Original English</summary>

**Host (Jason)**: incredible.
</details>

**安东·奥西卡**: 在第二个鸿沟上，我们正在投入大量资源，让用户能够更轻松地运行业务、吸引用户关注、促使人们发现你构建的产品。
<details>
<summary>Original English</summary>

**Anton Osika**: And on the on the second one, we're investing a lot in making it easier to run your business and to get people to care, people to discover what you build and to
</details>

**主持人（杰森）**: Lovable 进入市场有多少个月或几年了？
<details>
<summary>Original English</summary>

**Host (Jason)**: How many years has lovable been in market or how many months now?
</details>

**安东·奥西卡**: 20 个月。
<details>
<summary>Original English</summary>

**Anton Osika**: 20 months since 20.
</details>

**主持人（杰森）**: 是的。我们看到了许多初次创业的创始人，甚至企业级领袖，他们正与团队一起在平台上以极快的速度迭代。
<details>
<summary>Original English</summary>

**Host (Jason)**: Yeah. And and again we're seeing people who are first-time founders. We're seeing enterprise leaders move much faster together with their teams on this
</details>

**安东·奥西卡**: 没错，我们发现许多具有技术背景的人也在使用 Lovable。其中大约有 20% 是软件工程师，他们非常喜欢我们系统提供的高质量和意见性设计（Opinionated Framework）。
<details>
<summary>Original English</summary>

**Anton Osika**: Yeah, we're seeing people use Lovable both with a technical background. about 20% are technical or some type of engineer and they they love that we're quite opinionated.
</details>

**安东·奥西卡**: 而另外五分之四的用户是非技术人员，他们常常首先通过 Lovable 快速探索、验证什么是正确的产品构建方向。
<details>
<summary>Original English</summary>

**Anton Osika**: from the nontechnical people which is four out of five are are nontechnical uh and they're building uh often first to figure out what is the right thing to build
</details>

**安东·奥西卡**: 这正是 Lovable 最擅长的地方。现在我们甚至看到很多用户仅靠 Lovable 构建的产品，就实现了超过百万美元的年营收。
<details>
<summary>Original English</summary>

**Anton Osika**: which is where lovable has always been exceptionally good and uh now what we're seeing is that people are running businesses making more than million dollars of revenue on
</details>

**主持人（杰森）**: 没错，这就是目前非常有趣的 **Vibe Coding（氛围编程/意图编程）** 现象。如果我们去年坐在这里，人们可能还会觉得它只是一个做做原型和 Mockup 的好工具。
<details>
<summary>Original English</summary>

**Host (Jason)**: Yeah. And this is like the really interesting thing about vibe coding. If we were sitting here last year, people would look at it and say it's a great way to make a mockup
</details>

**安东·奥西卡**: 确实是这样。许多工程师现在根本不需要阅读或者亲手编写代码了，这也意味着你不需要成为一个传统的硬件或底层软件工程师，就能创造出实用的应用。
<details>
<summary>Original English</summary>

**Anton Osika**: very much so. So um I would say many engineers they don't look at the code they don't write code anymore and that means that you don't need to be an engineer to create so
</details>

**主持人（杰森）**: 没错。在内部，我给我的团队提供了他们想要使用的各种 AI 工具。其中有一位团队成员就用 Lovable 起步，我之前好像和你提过。
<details>
<summary>Original English</summary>

**Host (Jason)**: Yeah. And I can tell you internally I gave my team all the different tools they could possibly want to use and somebody had started with lovable. I think I told you the story
</details>

**主持人（杰森）**: 我当时说：“嘿，我有一个想法。你能帮我做一份关于目前项目中 50 家公司的经济影响力分析系统吗？”她让 Lovable 帮她做这个。我给了她一些基础的数据和需求。
<details>
<summary>Original English</summary>

**Host (Jason)**: So I said, \"Hey, I have an idea. Can you make for me an economic impact of the 50 companies that are in the program?\" She asked Lovable to do it. I gave her some, you know
</details>

**安东·奥西卡**: 平台商业计划是每个月 50 美元，起步计划是 25 美元。
<details>
<summary>Original English</summary>

**Anton Osika**: $50 a month, I think. Yeah. That's if you're on a business plan. Yeah. It starts at 25.
</details>

**主持人（杰森）**: 没错。你所构建工具的经济影响价值，在两年前如果要我们团队自己来研发，可能会花掉我们 50 万美元。现在仅用了 4 个小时，花费极其低廉，而且能够完美运行。这真是太震撼了。
<details>
<summary>Original English</summary>

**Host (Jason)**: Yeah. So, uh, the economic impact of what you're building is I would equate for what you built to us, it would have cost me $500,000 2 years ago. It was built in 4 hours
</details>

**主持人（杰森）**: 这真的是颠覆性的。我很高兴看到这样的进展。
<details>
<summary>Original English</summary>

**Host (Jason)**: in a year. It's extraordinary. I I'd love to hear more about the progress of the of the internet. Anything that you asked for that you want to forward directed to me.
</details>

**安东·奥西卡**: 此前一些用户可能对安全性以及数据泄露有所担忧，但经过与我们团队的安全验证后，大家对 Lovable 的安全性感到非常放心。
<details>
<summary>Original English</summary>

**Anton Osika**: Uh well, right now, you know, my concern was security and making sure that data didn't leak and they talked to your team and they went through it and it's secure. So, we feel good about it.
</details>

**主持人（杰森）**: 确实，我现在甚至让专业的渗透测试人员去横向对比市场上所有的无代码/低代码 AI 工具，以确保安全性。
<details>
<summary>Original English</summary>

**Host (Jason)**: Well, look, um I'm now asking people who do penetration testing to say, I want you to compare all the tools. Yeah. and uh make sure that there's a all the work that we're
</details>

**主持人（杰森）**: 一年前我们还在谈论 Mock-up 原型，而现在我们已经有了完全可运行、安全且能够直接部署的产品。一年后你会走到哪里？
<details>
<summary>Original English</summary>

**Host (Jason)**: a year ago we were at mock-ups. Now we're at functionality and secure and super viable for deployment. Where will you be in a year?
</details>

**安东·奥西卡**: 是的。此前人们在从“想法”到“构建出产品”之间有很大鸿沟。而你已经在平台上构建了各种极其复杂的全功能应用。
<details>
<summary>Original English</summary>

**Anton Osika**: Yeah. So, what we're seeing is that there's a gap in build being able to build the product, right? And and you built an entire internet on the platform. That's great. Um,
</details>

**主持人（杰森）**: 甚至可以说是 AWS 的有力竞争对手。
<details>
<summary>Original English</summary>

**Host (Jason)**: AWS competitor.
</details>

**安东·奥西卡**: 是的，它让你能够在底层灵活运行你的各种软件，当然我们在底层也与 AWS 等云厂商展开深度的合作。但你最终需要的是一个在商业中能随时对话的智能化伙伴。当你的所有软件、工具都运行在 Lovable 平台之上时，你与 Lovable 的交谈其实就等于它可以直接访问和调用底层的实际应用和数据。
<details>
<summary>Original English</summary>

**Anton Osika**: It it lets you it lets you run all your software and then we're working with companies like AWS under the hood as well. But but what you also want to have is um to use lovable a partner that you talk to about everything in your business. And if you're running your apps, your tools are on the platform, then just talking to Lovable has access to
</details>

### 定制化软件

**主持人（杰森）**: 让 AI 去帮你构建软件，而你把核心精力放在运营和做生意上。
<details>
<summary>Original English</summary>

**Host (Jason)**: for your business to build the software but you stay to build the business
</details>

**安东·奥西卡**: 是的，这样来管理你的业务。而且，我们一直在做的事情就是从用户的实际痛点中进行学习。每次 Lovable 犯了错或者修正了代码，系统都会沉淀经验。
<details>
<summary>Original English</summary>

**Anton Osika**: yes to operate your business and um what we're already doing I've been doing for a very long time is to compound from everything we're learning every time lovable makes a
</details>

**主持人（杰森）**: 软件在未来会变得 100% 定制化吗？甚至是公司内部的各种小工具。我之前看了一下我们的 Slack 账单，即使是最高级的版本，每年大概也就 10,000 美元。如果每个企业都可以极其廉价地定制一切，未来的软件生态会有怎样的改变？
<details>
<summary>Original English</summary>

**Host (Jason)**: Is software going to become 100% bespoke even like the internal tools. I was looking at Slack and our bill for Slack even on the highest version is maybe $10,000 a year.
</details>

**安东·奥西卡**: 我非常喜欢这个问题。我来讲个我最近听到的真实案例，关于一个在这个旅程中走得很远的用户，他来自一家非常领先的公司。
<details>
<summary>Original English</summary>

**Anton Osika**: I I like this question let let me ask answer it but I'll just give you a story about someone I recently heard who's going on this journey. They're quite advanced. So,
</details>

**安东·奥西卡**: 他叫 Nad，在美国一家名为 Nursa 的大型企业工作。他来到我们平台是因为他想推出一条新产品线（针对护士教育培训的垂直软件）。
<details>
<summary>Original English</summary>

**Anton Osika**: NAD, he works at a pretty large company in the US, Nursa, and uh he came to our platform because he wanted to build out a new product lines, nurse study for educating more
</details>

**主持人（杰森）**: 好的。
<details>
<summary>Original English</summary>

**Host (Jason)**: right?
</details>

**安东·奥西卡**: 在过去，由于这个特定的内部工具并不是外部商业化的核心主航道产品，所以公司很难为它争取到内部工程团队的资源。但是用 Lovable，他自己几小时就构建出来了。因此，未来许多特定需求将彻底走向高度定制化（Bespoke）的解决方案。
<details>
<summary>Original English</summary>

**Anton Osika**: So that's that's huge, right? But it's also the case that in some cases you have specific requirements where the tools that you've been using to date they aren't suited for you will have more more bespoke solutions. Yeah,
</details>

**安东·奥西卡**: 同时，Lovable 依然会保持与所有这些传统企业级软件工具的互操作系统性。
<details>
<summary>Original English</summary>

**Anton Osika**: but we're I also expect us to see that lovable continues to interoperate with all of those tools. And uh I'm not sure if you tried this if if you ask for connecting to an
</details>

**主持人（杰森）**: 好的，这种增长速度真的很惊人。
<details>
<summary>Original English</summary>

**Host (Jason)**: Okay. Growth is a phenomenal.
</details>

**主持人（杰森）**: 所以，你们相当于每半年就能实现营收的新突破。
<details>
<summary>Original English</summary>

**Host (Jason)**: So you're dying again by another 100 million in annual revenue.
</details>

**安东·奥西卡**: 没错。
<details>
<summary>Original English</summary>

**Anton Osika**: Exactly.
</details>

**主持人（杰森）**: 但在底层技术上，你们也是站在巨人的肩膀上，利用了各种大模型。
<details>
<summary>Original English</summary>

**Host (Jason)**: So but underneath the hood you're using some of these.
</details>

**安东·奥西卡**: 让我来解释一下。我们一直以来的战略就是一切以客户的最佳利益为依归。在模型智力层面，这意味着我们采用了多模型混合路由。
<details>
<summary>Original English</summary>

**Anton Osika**: Yeah. Let me explain. Yeah. So we've always had this strategy that we do whatever is best for our customers. And in terms of the intelligence that means that we're using
</details>

**安东·奥西卡**: 并且我们越来越多地引入**开源和开权重模型（Open-weight Models）**。当任务被路由到我们自主微调的模型上时，配合我们的智能体框架（Agent Harness），整个系统对特定软件开发任务的执行表现会极其聪明。
<details>
<summary>Original English</summary>

**Anton Osika**: and increasingly it's open weight models where our team when whenever it's get gets routed to an to our own model that model becomes more intelligent for our agent harness
</details>

### 竞合与未来

**主持人（杰森）**: 明白了。所以你们在开源大模型上进行了深度押注，你相信开源是 Lovable 的未来。
<details>
<summary>Original English</summary>

**Host (Jason)**: Right. So, you're all in on open source. You believe that's the future of Lovable. I I'm reading into it. So we have multiple partnerships and we're investing heavily to
</details>

**安东·奥西卡**: 是的。
<details>
<summary>Original English</summary>

**Anton Osika**: right
</details>

**安东·奥西卡**: 我们在斯德哥尔摩拥有一支非常强大的研究团队，专注于大模型的后训练（Post-training）技术，并应用各种行业最佳实践来优化模型在代码生成和意图理解上的效果。
<details>
<summary>Original English</summary>

**Anton Osika**: and uh we have a really really strong research team up in Stockholm who is working on what's called post training so and we're applying all the best practices to do that
</details>

**主持人（杰森）**: 你们是自己做数据标注，还是使用外部的数据标注与训练服务公司来帮助理解最常见的业务模式，并构建你们独有的专有数据？
<details>
<summary>Original English</summary>

**Host (Jason)**: Are you doing or are you using any of the data labeling data training companies to help you understand the most common businesses and build that proprietary data? So, so
</details>

**安东·奥西卡**: 我们的确在做。这些数据和反馈信号对于优化整个系统、尤其是我们的智能体执行框架至关重要。
<details>
<summary>Original English</summary>

**Anton Osika**: We are. Yes. And that's and that's a lot of signals for making the system both the agent harness
</details>

**安东·奥西卡**: 并且在过去的两年里，我们一直在提炼和迭代各种“技能库”。我们的智能体懂得根据我们顶尖软件工程师在开发真实高品质软件时所展现的知识和逻辑，来决定何时记忆或调用特定的软件工程策略。我们每周都在迭代优化这些机制。
<details>
<summary>Original English</summary>

**Anton Osika**: and um what we've been refining over the last two years which is the skills that we have have this like internal type of skills that the agent knows when to remember the facts from our software engineers that know how to build really really good software. We're modifying both of those on every every single week.
</details>

**主持人（杰森）**: 这完全合理。之前有人告诉我，一些公司正在做“Token 倾销”（Token Dumping），比如把价值 100 美元的 Token 以 50 美元的价格售卖，充当中间商亏本赚吆喝。但我相信你们是非常关注商业利润的，或者至少是非常接近盈利的。
<details>
<summary>Original English</summary>

**Host (Jason)**: It makes total sense. And somebody told me some companies are doing token dumping. They're, you know, selling $100 worth of tokens for $50. Um, you know, basically they become token resellers in some ways and they're money losing businesses. You have to you're money you're profitable I believe now or close to it. Um, we we always monitor our margins, but again um we're doing what's best for our customers and that means that often means more intelligence. So we're not we're not looking at oh let's use a we've never had the decision to say let's use a cheaper model here if it's measurably worse for our customers and we can measure that what's best for
</details>

**主持人（杰森）**: 但你们目前是提供 50 美元无限量使用，还是说设置了用量上限（Caps）？
<details>
<summary>Original English</summary>

**Host (Jason)**: but are they is it unlimited for the 50 or you have caps now
</details>

**安东·奥西卡**: 我们有额度限制以及超额付费（Overages）机制。
<details>
<summary>Original English</summary>

**Anton Osika**: we have caps overages and caps are people starting to hit them
</details>

**主持人（杰森）**: 用户真的开始频繁触发这些限制了吗？
<details>
<summary>Original English</summary>

**Host (Jason)**: yeah our customers definitely hit caps and then you can top up you can have a we have multiple subscription tiers
</details>

**主持人（杰森）**: 我只是好奇，大概有多少比例的人会愿意额外付费来获取更多额度？因为他们对这个工具太上瘾了，以至于直接用超了。
<details>
<summary>Original English</summary>

**Host (Jason)**: what number I'm just curious like what percentage of people need to top up. They're so addicted to it that they're blowing past the the
</details>

**安东·奥西卡**: 特别是对于订阅了低端付费套餐的用户。
<details>
<summary>Original English</summary>

**Anton Osika**: so from the lowest subscription tier.
</details>

**主持人（杰森）**: 是的。
<details>
<summary>Original English</summary>

**Host (Jason)**: Yeah.
</details>

**安东·奥西卡**: 我想……
<details>
<summary>Original English</summary>

**Anton Osika**: Um I I think it's the
</details>

**安东·奥西卡**: 好像有高达 60% 左右的客户会选择额外付费购买超额额度。
<details>
<summary>Original English</summary>

**Anton Osika**: uh m it's something like 60% of our customers I think
</details>

**主持人（杰森）**: 我越来越频繁地听到这样的消息：由于 Lovable 带来的巨大价值，人们非常愿意掏超额流量费。我认为这就是这门业务的未来所在。如果我花 600 美元超额用量，或者哪怕每年付 6,000 美元，但它帮我搞定了一个价值 50 万美元的系统，谁会在乎多付这点小钱呢？这依然比 3 年前便宜了 99%。
<details>
<summary>Original English</summary>

**Host (Jason)**: I'm hearing that more and more often that people are willing to pay the overages because they're getting so much value. And I think that's the future of the business is people are looking at it going like I am. Well, if I'm paying $600 and if you token max to 6,000 a year, but this is a $500,000 piece of software, I don't care. I'm still paying somewhere between.1% and 1% of what I would have paid 3 years ago. Who cares?
</details>

**安东·奥西卡**: 确实是这样。
<details>
<summary>Original English</summary>

**Anton Osika**: Go for it. Um, so
</details>

**安东·奥西卡**: 如今一切的核心在于快。使用 AI 能够帮助团队跑得比竞争对手快得多，因此这些工具的付费投资在商业上是非常超值的。
<details>
<summary>Original English</summary>

**Anton Osika**: yeah, what we're seeing is everything is about moving moving fast these days and and AI more AI usually lets you move much faster. So the spend is usually worth it.
</details>

**主持人（杰森）**: 最后一个问题。我发现现在有些企业里，会有多个人同时尝试用 Lovable 去解决同一个软件问题，进行内部的赛马和竞争。比如我们针对日本市场和美国市场，会有两个不同的员工分别在 Lovable 上独立开辟项目来尝试构建系统。
<details>
<summary>Original English</summary>

**Host (Jason)**: Do your customers a final question for you because I'm starting to see this now where multiple people in the organization try to solve the same software problem and they're competing with each other. So like this internet I'm talking about, we built one for Japan.
</details>

**安东·奥西卡**: 是的。
<details>
<summary>Original English</summary>

**Anton Osika**: Yeah.
</details>

**主持人（杰森）**: 我问他们你们是互相 Fork 了对方的分支代码，还是怎样？他们说没有，我们只是开启了两个完全独立的 Lovable 项目。但这很酷，因为这等于让我们以极快的速度进行了两次尝试，由两个聪明绝顶的人各自制作他们的软件版本。
<details>
<summary>Original English</summary>

**Host (Jason)**: But somebody built the US one. So now I have two pieces of software. So I said to the two different people or do we have did you guys fork each other's code or they're like no we just built two different lovable projects. And I'm like is that the right thing to do because you went faster and I had two swings at bat two different intelligent brilliant people making their version of the software.
</details>

**安东·奥西卡**: 在以前，这种开发模式是不可想象的。
<details>
<summary>Original English</summary>

**Anton Osika**: But you would never have done that
</details>

**主持人（杰森）**: 没错，传统开发中你必须只有一条主干线，然后不断往里面缝合不同团队的各种需求，最后拼凑出一个极其臃肿复杂的“科学怪人（Franken-software）”缝合怪。
<details>
<summary>Original English</summary>

**Host (Jason)**: in the previous way of building software. You would have one track of software and you would be building Franken software where you'd be trying to get all the needs into it from the two different groups.
</details>

**安东·奥西卡**: 没错，我是极其推崇快速且独立的开发实验的。我之前在欧洲的欧洲核子研究组织（CERN，就是运行粒子对撞机的那个地方）工作过一段时间。在那里我接触到了“合作性竞争（Co-opetition）”的概念。他们会有两个完全独立的团队，在同一个粒子加速器上工作但负责不同的点位。在最终发表论文前，他们甚至不共享中间成果。这种竞争能确保团队不陷入单一开发思路的局部最优解。在如今软件工程门槛极低、瓶颈不复存在的情况下，探索“如何做出正确的商业决定和产品选择”才是核心。用 Lovable 我们可以极其简单地调出多个项目，把它们各自最棒的功能进行测试和融合，甚至进行 A/B 测试来决定哪一个对客户而言指标最好。
<details>
<summary>Original English</summary>

**Anton Osika**: I Yeah, I I'm actually a huge fan of very rapid experimentation and I I have a story where for a while I worked at a a place called CERN where they do particle physics. It's it's pretty here in Europe, right? Uh and that's where I was introduced to this concept of co-opetition where they have two actually quite isolated teams working on the same um particle accelerator but different places on it and then they don't share the results until they publish and that way they uh they can kind of over time learn what's working best in the different organizations but you don't get stuck in a local minimum and it's you know free markets work extremely well because of competition and they they they do that in academia as well and now since the engineering is less of the bottleneck. It's more the question of what is the right thing to build. I think it's a great thing to have if you have the sufficiently many humans right to do to try to attempt solving the same problem in different ways. And then if you do that on lovable, what I like to do is I I take I bring up a new project or one of the projects and I I say, \"Hey, can you go and just check out this other one and take this these three things that I really like and and bring them bring them over here and maybe even run an a split test, run an experiment to see if it's if it's improves improving the metrics for for our customers we're trying to serve.
</details>

**主持人（杰森）**: 没错。你看到有人用 Anthropic 的 **Claude（原文转写为 Fable）** 构建出了像 Fortnite 这样的 3D 游戏了吗？
<details>
<summary>Original English</summary>

**Host (Jason)**: Did you see somebody used Fable to build Fortnite
</details>

**安东·奥西卡**: 看到过，还有一些很酷的 3D 游戏。
<details>
<summary>Original English</summary>

**Anton Osika**: and uh
</details>

**主持人（杰森）**: 没错。
<details>
<summary>Original English</summary>

**Host (Jason)**: I've seen the 3D some of the 3D games?\" Yeah.
</details>

**主持人（杰森）**: 你对 Anthropic 最新发布的这个 **Claude 3.5 Sonnet / Claude** 怎么看？我知道他们是你们的合作伙伴。
<details>
<summary>Original English</summary>

**Host (Jason)**: Yeah. What is your take on, you know, this latest version from Anthropic Fable? I know they're a part or I assume they're a partner. I don't know that.
</details>

**安东·奥西卡**: 是的，我们将它作为底层使用的众多模型之一。
<details>
<summary>Original English</summary>

**Anton Osika**: Yeah, we use Fable as well as one of the models.
</details>

**主持人（杰森）**: 与上一代相比，你觉得它更快、更好，还是兼而有之？它是一个巨大的阶跃式函数提升吗？
<details>
<summary>Original English</summary>

**Host (Jason)**: What do you think of it in terms of compared to the last generation faster, better, both? Yeah. Is it a massive step function? Yeah.
</details>

**安东·奥西卡**: 是的。我所观察到的是，它可以在第一次尝试时就生成非常精美、复杂的界面或应用。但随着你不断去深化系统，人依然需要起到核心规划的作用。你必须与智能体协同制定下一步策略，思考什么样的方向才是推动商业指标和用户体验的最优解。模型本身的智力提升很快，但人如何将这些工具、数据结合起来做出正确的商业战略选择，这才是尚未被替代的瓶颈所在。
<details>
<summary>Original English</summary>

**Anton Osika**: What I've seen is that it can in the first attempt create very sophisticated things that look really good. Then when as you're evolving right it's it's still the same thing where you as a human you have to think you often should be planning together with your agent about what is the right thing to do and and that's more of that's again more of the bottleneck uh whereas more intelligence is on some tasks it's great yeah like it creates really beautiful things 3D games for example but on figuring what to what to build figuring out figuring out what are the right strategic directions or experiments you should run to improve outcomes for your business. That's um uh that's not changing as fast is the humans knowing how to use the tool to get and to plug in all the right data to be able to take the right decisions for taking your product forward and to take your business forward.
</details>

**主持人（杰森）**: 听着，我太爱这个产品了。但相比产品和作为创始人的你，我更爱它带来的实际商业成果，它为企业创造的价值是极其惊人的。所以任何听到这段话的人，Lovable 都绝对值得你立刻投入时间。不要再等待了，直接刷你的企业信用卡，开始构建吧！这就是我的建议。再次祝贺你带领 Lovable 实现了爆发式的成长，似乎每过 6 个月你们的营收都要翻一番。每次大模型更新，都有人叫嚣 Lovable 药丸，但你总是通过深挖客户需求不断活下来并活得更好。祝贺你，优秀的创业者。
<details>
<summary>Original English</summary>

**Host (Jason)**: Um listen, I love the product, but even more than I love the product and you as a founder, I love the outcome. The outcome for business is extraordinary. So, anybody who's listening, Lovable is absolutely worth your time. Don't wait. Just put it on your corporate card and start building. That's my message. Just start building with Lovable. It's an incredible product. And uh congratulations on being reborn six times cuz every 6 months you add 100 million in revenue it seems. And then everybody says Lovable's dead because the new foundation model is so good. But you keep studying your customer and and you keep somehow surviving and thriving. So congratulations as an entrepreneur. Thank you so much, Jason. I enjoyed that chat. I hope you enjoy the rest of your stay here in Paris.
</details>

**主持人（杰森）**: 巴黎太棒了，凡尔赛宫非常令人震撼，对吧？也许有一天我们会用 Lovable 和 Tesla Optimus 机器人来重建这一切。
<details>
<summary>Original English</summary>

**Host (Jason)**: It's pretty great. And the Palace of Versailles is so impressive, huh? Uh someday we'll be building this with lovable and optimist robots. I
</details>

**安东·奥西卡**: 我非常期待，我将全力以赴！
<details>
<summary>Original English</summary>

**Anton Osika**: I'm looking forward to it. I'm going all in. I'm going all in. [TRANSCRIPT_END]
</details>