---
author: The Pragmatic Engineer
date: '2026-04-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=n5f51gtuGHE
speaker: The Pragmatic Engineer
tags:
  - self-modifying-software
  - code-mode
  - agentic-workflow
  - complexity-reduction
title: AI编程代理的幕后构建、技术演进与工程哲学探讨
summary: 文章回顾了极简且可自我修改的AI编程代理的诞生背景，介绍了其核心技术（如自修改软件），并深入讨论了从早期计算基础到当前AI时代的职业发展转变。同时对比了不同工作流模式（MCP vs CLI）的优劣，以及人类学习与机器学习在解决复杂工程问题时的根本差异。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books:
  - Code by Petzold
status: evergreen
---
### 访谈背景与起源

**主持人**: 如果我告诉你，2026 年最具影响力的 **AI 编程代理**之一是由奥地利的一位开发者独立构建的，他因为对现有的 AI 编程工具感到沮丧而动手开发。这就是 **Pi**，一个极简且可**自我修改**的编程代理，它已经悄然成为了广受欢迎的个人 AI 助手 **OpenClaw** 的核心引擎。**Mario Zner** 是 **Pi** 的创造者，今天与他一同参加节目的还有 **Armen Roner**，他是 **Flask** 的创造者，现在是 **Pi** 的早期使用者和贡献者。

<details>
<summary>Original English</summary>
**Host**: What if I told you that one of the most influential AI coding agents of 2026 was built by a single developer in Austria who got frustrated with existing AI coding agents. This is **Pi**, a minimalist **self-modifiable** coding agent which has quietly become the engine behind the wildly popular personal AI assistant **OpenClaw**. **Mario Zner** is the creator of **Pi** and joining him today is **Armen Roner**, the creator of **Flask** and now an early adopter and contributor to **Pi**.
</details>

**主持人**: 在今天的节目中，我们将讨论 **Pi** 的幕后故事，以及为什么**自我修改软件**在 AI 代理的帮助下变得更加容易。Armen 在采访了 30 多个工程团队后，了解到了 AI 代理如何改变他们的工作方式，以及为什么软件质量似乎在下降。我们还将讨论反对 **MCP** 的理由，为什么 **CLI** 变得如此受欢迎，等等。如果你想听到行业中两位非常务实的声音，诚实地谈论哪些行得通，哪些行不通，以及为什么我们作为一个行业需要慢下来，这一集就是为你准备的。

<details>
<summary>Original English</summary>
**Host**: In today's episode, we cover the backstory of **Pi** and why **self-modifying software** is much easier to do with AI agents. What Armen learned interviewing 30 plus engineering teams about how AI agents are changing how they work and why software quality feels like it's trending down, the case against **MCP** and why **CLI** are becoming so popular and many more. If you want to hear from two very grounded voices in the industry honestly talk about what's working and what isn't and why we need to slow down as an industry, this episode is for you.
</details>

**主持人**: Mario 和 Armen，很高兴能邀请你们来参加播客。

<details>
<summary>Original English</summary>
**Host**: Mario and Armen, it's so good to have you here on the podcast.
</details>

**Mario**: 谢谢邀请。

<details>
<summary>Original English</summary>
**Mario**: Thanks for having us.
</details>

**Armen**: 谢谢。

<details>
<summary>Original English</summary>
**Armen**: Thank you.
</details>

**主持人**: 作为开场，Mario，你是如何进入科技领域并最终开始构建 AI 产品的？

<details>
<summary>Original English</summary>
**Host**: So, as a kickoff, Mario, how did you get into tech and eventually into building AI stuff?
</details>

### 早期的计算岁月

**Mario**: 噢，说来话长。我们有多少时间？我其实是 90 年代的孩子。我在 1996 年得到了我的第一台 **PC**。触发因素是我喜欢电脑游戏。我们家当时属于“工作贫困阶层”，所以买不起 Game Boy、NES 或超级任天堂之类的东西。但我有个叔叔有一台 **Amiga 500**，我每隔一天就去他那里玩游戏。后来我父母告诉我，如果你去工作，就能攒钱给自己买台电脑。实际上，我父亲当时在干一些“私活”（Schwarzarbeit）。

<details>
<summary>Original English</summary>
**Mario**: Oh, well, that's a long story. How much time do we have? So, I'm a kid of the '90s, actually. And got my first PC in 1996. And the trigger for that was that I loved computer games. We were kind of working poor, so we couldn't afford any of the Game Boy and NES, Super NES stuff. But I had an uncle who had an **Amiga 500** and I would go to his place every second day and just play games there. And eventually my parents told me if you work you can save up and buy yourself a computer. And in reality, my dad would do um what's he called? Schwartzarbeit.
</details>

**主持人**: 也就是不一定为这部分收入交税。

<details>
<summary>Original English</summary>
**Host**: Well, you're not necessarily paying the taxes on your...
</details>

**Mario**: 是的。他干着正常的工作，下班后还要去修车、在建筑工地干活。大约两三年后，他们说：“时候到了。”于是带我去了附近大城市的一家电脑店，给我买了一台 **486**。基本上就是这样开始的。

<details>
<summary>Original English</summary>
**Mario**: Yeah. So, he would do his normal job and after his normal job, they would go fix cars and work at construction sites. And after two or three years or so, they just said, "It's time." And took me to a computer shop in the nearby big city and bought me a **486**. And that's how it started basically.
</details>

**主持人**: Pentium 486。

<details>
<summary>Original English</summary>
**Host**: Pentium 486.
</details>

**Mario**: 是的，一台 **Intel 486DX4**，40 MHz，带有 Turbo 按钮。我一直很喜欢游戏，这也引导我进入了图形编程领域。运气使然，我在读大学期间在一家做 **NLP**（自然语言处理）的组织找到了一份工作，当时是做应用**机器学习**，主要是把研究成果转化并塞进工业应用中。在那儿我学到了机器学习的基础。那还是在**深度学习**流行之前。

<details>
<summary>Original English</summary>
**Mario**: Yeah. an **Intel 486DX4** 40 MHz with turbo button and that's where I started and I've always been into games a lot um which also led to graphics programming and through sheer luck I got a job while I was studying at university at um applied science organization who was doing **NLP** stuff um machine learning applied machine learning basically taking research results and trying to stuff them into industry applications. And that's where I learned the ropes of machine learning. That was all before **deep learning** became a thing.
</details>

**Mario**: 2010 或 2011 年左右我退出了那个领域，因为我加入了旧金山的一家初创公司。后来我回来，和两个朋友在瑞典创办了另一家公司，做了一个把 **Java 字节码**提前编译（AOT）到 **iOS** 的编译器。后来公司被卖掉了。从那以后，我的时间稍微充裕了一些，也一直关注机器学习的东西。然后 **GPT** 出现了，故事就是这样。

<details>
<summary>Original English</summary>
**Mario**: I actually quit that kind of domain in 2010 11ish because I joined a startup in San Francisco. And then later came back and joined another startup with two friends in in in Sweden where we did uh an ahead of time compiler for **Java bytecode** to **iOS** that got sold. And since then I have a little bit more time and I've always kept up with machine learning stuff because obviously super interesting. Uh and yeah and then **GPT** happened and that's the story.
</details>

**主持人**: 是的。Armen，你的根基在哪里？

<details>
<summary>Original English</summary>
**Host**: Yeah. And here we are. And then Armen where were your roots?
</details>

**Armen**: 我的根基肯定不是“工作贫困阶层”。我父母经营一家建筑师事务所，他们很早就采用电脑进行 **CAD** 绘图。我的第一台电脑是他们淘汰下来的旧电脑。所以即使我比 Mario 年轻，我的第一台电脑也是 **386**。

<details>
<summary>Original English</summary>
**Armen**: So my roots are definitely not working poor but I because my parents ran an architectural office where they kind of adopted computers for **CAD** drawing. My first computer was like old computers that they recycled. So, my first computer, even though I'm younger, was a **386**.
</details>

**Mario**: 噢，真为你感到难过。

<details>
<summary>Original English</summary>
**Mario**: I'm so sorry for you.
</details>

**Armen**: 基本上，我拥有过的电脑没有一台能正常玩游戏。因为它们装的是 **Windows NT**，那玩意儿当时干不了别的。所以你得自己摸索。唯一能让它们运行的方法是在启动进入 Windows 95 或 3.11 之前先进入 **DOS**。所以我开始折腾 **QuickBasic**，后来是 **Turbo Pascal**，我买了一堆相关的书。这就是我学习这些东西运作原理的根基。我以前并不擅长这个，但我发现非常有意思。

<details>
<summary>Original English</summary>
**Armen**: And and so, basically, none of the computers that I ever had were capable of playing computer games properly. Um, because one, they used **Windows NT**, which at the time didn't do anything. So, you had to sort of like build your way through it. And like the only way you could actually get them to run was because before it didn't know yet how to get the Windows 95 or like Windows 311. Um that was like before it booted into either one of those you could boot it into **DOS** like really old DOS games at a time when you could already get better stuff but but because it was sort of this kind of thing I started toying around with **QuickBasic** a lot um with to **Pascal** I bought a bunch of books on that um and I that that was my roots of of of learning how these things work and it just I wasn't ever really good at this but I found it really interesting like this this idea of like...
</details>

**Mario**: 我们在德语里管这叫“瞎折腾的人”（Bastler）。

<details>
<summary>Original English</summary>
**Mario**: We call it a Bastler in Germans.
</details>

**Armen**: 不，我向你保证，我刚开始接触的时候真的很菜。但随着时间的推移，如果你坚持做下去，就会变得更好。2002 或 2003 年左右，我经常使用 **Delphi**，它是 **Turbo Pascal** 的可视化版本。后来有人向我展示了 **Linux**，因为当时我有“我想用 Linux”的想法。但 Delphi 在 Linux 上行不通，接着我发现了 **Python**，并开始用 Python 编程。

<details>
<summary>Original English</summary>
**Armen**: No, I I swear to you like I was when I when I started dabbling with this, I just really sucked. But like over time, you like if you keep doing this, you get better. Um and then in um 2002 or three, I I used I used to use **Delphi** a lot, which was like a visual version of of **Turbo Pascal**. And in 2002 or 2003 someone uh also showed me because I I I' I've got this idea like I want to use **Linux** and then um I Delphi didn't work on Linux and then I found **Python** and through that I started doing some Python programming.
</details>

**Armen**: 2004 年 **Ubuntu** 刚出来，那是一个风险投资支持的载体，但他们创建了本地社区。我和一群朋友创办了德国的 Ubuntu 协会，并运行了一个叫 **Ubuntuusers** 的在线社区，大概搞了四五年。随着 Ubuntu 的流行，社区不断扩大，随之而来的就是扩展性问题。这就是我进入 **Web 开发**领域的原因。为了构建这个社区，我想要做一个模板引擎、一个 Web 库之类的。最终我把它们捆绑在一起，做成了 **Flask** 框架。它非常受欢迎，甚至到今天依然被很多“打代码的人”（Clankers）吐出来。

<details>
<summary>Original English</summary>
**Armen**: There was a **Ubuntu** just came out in 2004 and that was a venture-backed vehicle but it they created all this like local community. So there was this like Ubuntu association. I together with a bunch of friends we started the German **Ubuntu** foundation uh not that foundation association um and we ran this online community called **Ubuntuusers** for four or five years and we and because Ubuntu was popular the community grew and then scaling problems came so like that's how I got into **web development** um and then for building this I just I wanted to build a templating engine a web library all of this and then eventually I bundled that together and made this **Flask** framework which got very popular and even nowadays still is a thing that clankers like to spit out.
</details>

**主持人**: 太有意思了。

<details>
<summary>Original English</summary>
**Host**: That's hilarious.
</details>

**Armen**: 后来我离开了那个项目，在 2013、2014 年左右，我在伦敦做了几年的电脑游戏，之后回到了开源领域。我在 **Sentry** 工作了 10 年，去年 4 月离开，想尝试一些新东西。

<details>
<summary>Original English</summary>
**Armen**: Um h but I I left it and then in uh in 2013 14 or so I worked on computer games for a couple of years in London but then afterwards I went back to open source and I I worked on **Sentry** for 10 years and then left in April last year to try something new.
</details>

### 转向人工智能

**主持人**: 你们两个都来自奥地利。事实上，Mario 你现在也住在奥地利。你们以前都做过游戏，Armen 在 **Sentry** 工作过。还有第三个人，也就是上一集节目的嘉宾 **Peter Steinberger**，也来自奥地利。很高兴你们三位能聚在一起。我最近看到一些照片，特别是在 **OpenClaw** 和 **Pi** 启动之前，你们三个经常聚在一起实验、研究 AI。

<details>
<summary>Original English</summary>
**Host**: So both of you are originally from Austria. In fact you right now live in Austria as well right? you were doing games, you were working at Sentry, you also did games before. Then the third person who's not in the room but was on this podcast just before is **Peter Steinberger** also from Austria. Great that the two of you meet where the three of you meet cuz uh I I've I've recently seen a bunch of photos especially before **OpenClaw** and **Pi** started you hanging out uh the three of you experimenting playing with AI.
</details>

**Mario**: 我觉得我们两个是在网上认识的，对吧？在 Reddit 上。

<details>
<summary>Original English</summary>
**Mario**: I think the two of us met on on the internet right on Reddit.
</details>

**Armen**: 很难说，因为我确定在你读大学的时候见过你一次。

<details>
<summary>Original English</summary>
**Armen**: It depends because I definitely met you once when I was at university.
</details>

**Mario**: 哦，是吗？

<details>
<summary>Original English</summary>
**Mario**: All right.
</details>

**Armen**: 所以，但你那时候没认出我，我当时也没什么名气。

<details>
<summary>Original English</summary>
**Armen**: So, but you didn't recognize me that time and I was useless.
</details>

**Mario**: 我那时候已经成名了（开玩笑）。

<details>
<summary>Original English</summary>
**Mario**: I was already famous.
</details>

**Armen**: 我们在网上通过抽象的方式交流过，但最终在维也纳见了面。我们在网上经常互相争论，但那是非常可爱、非对抗性的。虽然我们在生活的某些领域看法不尽相同，但我得说，那是很有素养的交流。至于 Peter，通过朋友的朋友，我最终认识了他。我当时在我住的小镇的一个办公室工作，那家公司免费给我提供办公空间，作为交换，我担任 CEO 的导师。那家公司和 Peter 的公司 **PSPDFKit** 有一些业务往来。

<details>
<summary>Original English</summary>
**Armen**: Um, but yeah, we sort of abstractly met on the internet, but eventually we met up in Vienna. Um, we were screaming a lot at each other, but uh on the internet, but uh in a in a very cute kind of way, in a very non-confrontational kind of way. And even though we might not think alike in all areas of of of our lives, uh it was a cultured exchange, I would say. So that was nice. Uh and Peter I like 60 degrees of Peter Steinberger basically. Um I was working at an office in my town and the company that gave me free office space in exchange for being like a mentor to the CEO had some kind of business dealings with Peter's company, **PSPDFKit**.
</details>

**Mario**: 他后来去了格拉茨的办公室，我觉得那是我们第一次见面。同年，我们在伊斯坦布尔的一次会议上又见到了，在那儿待了一整晚，一切基本上就是从那儿开始的。

<details>
<summary>Original English</summary>
**Mario**: Um and eventually came to the office in Gratz and I think that's where we met the first time and then also the same year we met at the conference in Istanbul and just hung out for an entire night and that's basically where it all started.
</details>

**主持人**: 好的。那你们两个是如何从对 AI 持怀疑态度，转变为觉得“这玩意儿其实非常有意思”的？到 2022 年，你们两个都已经有十多年在不同领域构建复杂软件的经验了。你们的第一反应是什么？

<details>
<summary>Original English</summary>
**Host**: Nice. And then how did the both of you go from being skeptical about AI when these tools came out and again both of you have to at that point and by 2022 you've been doing a decade plus of building complex software in different domains. what was your first reaction to it and then eventually how did you kind kind of come across to the side of like well this thing is actually really interesting.
</details>

**Mario**: 对我来说，大概是在 2022 年。我觉得 **GitHub Copilot** 在 **ChatGPT** 之前就出来了。

<details>
<summary>Original English</summary>
**Mario**: So for me it was I think in 2022 I think **Copilot** um **GitHub Copilot** came out before **ChatGPT**.
</details>

**主持人**: 是的，在 2021 年。

<details>
<summary>Original English</summary>
**Host**: Yes in 2021.
</details>

**Mario**: 2022 年的时候，我以前初创公司的那些人——来自 **Xamarin** 的 Nat Friedman 和 Miguel de Icaza，因为他们收购了公司。Nat 当时在 GitHub 工作，他在 2022 年私信我，问我想不想试用 GitHub Copilot。我当时觉得“我不在乎，我不觉得这玩意儿能有什么前途”。但他坚持说“不，这就是未来”。于是我试了试，结果绝对是惨不忍睹。

<details>
<summary>Original English</summary>
**Mario**: Yeah and through my previous startup stuff I was working with Nat Friedman and Miguel de Icaza from **Xamarin** because they acquired the company. I knew Nat Friedman from our early startup stuff and eventually moved to GitHub and then was in my DMs in 2022 I think and asked if I wanted to have access to GitHub Copilot the tap tap tap autocomplete thingy and I was like I I don't really care I don't think this is going anywhere and he's like no man it's the future got to try it it's the future so I tried it and it was absolutely horrible.
</details>

**Mario**: 但是，当 **GPT** 出现后，特别是当他们开始提供 API 访问权限时，我做了很多项目来摸索哪些行得通，哪些行不通。不一定是编程领域，直到他们有了 **Tool Calling**（工具调用），或者当时 OpenAI 称之为 **Function Calling**（函数调用），它才变得非常有趣。但直到 2024 年底，大概 10 月左右，它才真正变得好用。那是编程代理也开始变得有趣的时候。

<details>
<summary>Original English</summary>
**Mario**: But yeah after after when **GPT** came out and especially when when they started providing API access I did a lot of projects just figuring out what works and what doesn't work not necessarily in the coding space but eventually once they had **tool calling** that's when they became very interesting or **function calling** as OpenAI called it back then um but it took until 200 I would say 24 end of 24 October or so for that to actually be useful and that's where the coding agents also became kind of interesting.
</details>

**Mario**: 然后在 2025 年，**Claude Code** 团队发布了 **Claude Code**，它引入了 **Agentic Search**（代理化搜索）。基本上就是给代理一种方式，让它深入你的文件系统并读取所有文件。这真的改变了一切。之前像 **Cursor** 那种基于索引、基于向量数据库之类的东西都显得没那么必要了。我知道 **Chroma** 的 CEO 可能会因为我这么说而生气，但这确实是关键所在：不是那种密集或稀疏的搜索，而是直接让代理访问你的文件。对我来说，就在那一刻，我彻底想通了。

<details>
<summary>Original English</summary>
**Mario**: And then 2025 um the **Claude Code** team came out with with **Claude Code** and that introduced the **agentic search**. So basically just give the agent a way to plow through your file system and read all your files and it made the whole difference actually. Like all the things that came before like **Cursor** with indexing and and any based stuff and and all of that that just went away and I know that the CEO of uh **Chroma** is probably mad at me for saying this but that that was the difference that it didn't it it wasn't like a dense and sparse search thing that the agent could could go through it was just give it access to your files. That that was it for me. That's where it clicked for me.
</details>

**Armen**: 我觉得我的路径也差不多。我知道 GitHub 有一个项目让维护者可以提前试用 **Copilot**。虽然我感觉这会非常有趣，但在当时并没有意识到它会发展成现在的样子。

<details>
<summary>Original English</summary>
**Armen**: I think my path was kind of similar. Um because I think **Copilot** came out quite a bit earlier, but I know that um there was a program at GitHub that gave you early access to **Copilot** at the time. Um I think it was like this maintainers group or something where I still was in I got the feeling for **Copilot** that this will actually be really interesting.
</details>

**Armen**: 以前我一直身处开源领域，现在他们在用开源数据进行训练，这至少会引起争议。我当时没怎么想过生产力，更多是觉得这会是个争议话题。我记得有一段时间我一直在用一种非常“对抗”的方式去试探它。我试探的一个点是：它会不会复现 **GPL** 代码？

<details>
<summary>Original English</summary>
**Armen**: Um but not in any way in which it is now because I felt like oh I am in open source for such a long time and now they're doing like training in open source data. It's like there is something at the very least this will be controversial. I I didn't think about like it being productive. I felt like oh this is going to be um is going to be like a controversial thing with like training open source data and and and I was I remember for like a time was like I was trying to probe it like really um adversarial.
</details>

**主持人**: 看看里面有没有 **Flask**。

<details>
<summary>Original English</summary>
**Host**: Whether there's **Flask** in there.
</details>

**Armen**: 我当时试着引导它吐出 **Quake III** 的**平方根倒数速算法**（inverse square root）函数。这很容易，因为它有个非常特别的名字。我还发现，如果你按照某种方式缩进，它甚至会继续在上面贴上许可证文本。结果完全错了——它原本是来自 **Doom** 的 GPL 开源版本，应该是 GPL 协议，但它却标注了一个随机路人的 **MIT** 许可证。我当时在推特上发了这件事，引起了很大反响。那是我第一次意识到，这些实验室里正在取得真正的 AI 进展。

<details>
<summary>Original English</summary>
**Armen**: I then I I was trying to probe it like really... So one of the things that I I probed on is like I probed on like will it retail **GPL** code and I remember at one point I got it to um spit out the uh **Quake III inverse square root** function which is was very easy because also it was had a very specific name. So like was very easy to get the recall but I also found like you can you can sort of tab in a certain way then it would then continue putting like license text on top of it. It was completely wrong. it like came from an open source **GPL** drop of of of **Doom** originally I think. Um and so it was like it would have been **GPL** code if it would have done that but it actually attributed like **MIT** license from a random dude and I was like oh like Mr. **Copilot** that's the wrong thing and that tweeted at the time got really really popular and then sort of people started like sharing with me like because I was at a time not really exposed to how much actual AI progress was being made in those labs.
</details>

**Armen**: 我不是来自 AI 或机器学习领域。我在大学学过，当时感觉“AI 寒冬”来了，什么也没发生。但通过那条推文和其他一些事情，我意识到有些东西正在发生——某些公司的 CEO 确信这会爆发。于是我开始关注它，尝试用 API 做各种事情，比如能不能做**自动 Bug 修复**。我对此产生了浓厚兴趣，但直到 **Claude Code** 出现之前，我都还没觉得世界会因此而改变。

<details>
<summary>Original English</summary>
**Armen**: Yeah, like I I didn't come from this AI space or ML space. So like I was I learned about a university and like oh there's AI winter and then nothing happens. But through this tweet and some other things I like other than I like I re recognized that there was something there like there's there's actually CEOs in certain companies are convinced this will get off and that's how I started like paying attention to it and I was essentially I was trying all kinds of stuff with the API like can you do like bug fixing things I got really interested in it but it didn't at all feel like the world is going to change until um **Claude Code**.
</details>

**主持人**: 而且你也改变了对“它会吐出开源代码”这件事的立场。

<details>
<summary>Original English</summary>
**Host**: And you also changed your stance on the whole oh my god this spitting out open source code. It it memorized.
</details>

**Armen**: 是的。因为多年来我一直是个“分享主义者”，我认为人类的进步来自于互相借鉴。我非常支持在美国这种把知识从一家公司带到另一家公司的做法，即使有竞业协议。我喜欢这种“海盗式”的知识共享。

<details>
<summary>Original English</summary>
**Armen**: So, because like my like my shtick for many years now has been that I really I'm like a I want people to share stuff like I I think like human progress comes from like building on top of each other and I I'm a huge supporter of the fact that in the US you basically take knowledge from one company to another company that then no competes like I I like this pirate kind of approach to sharing.
</details>

**Armen**: 我理想中的版本是**版权**几乎不存在，或者只有非常有限的版本。我其实并不在乎它吐出 GPL 代码却没署名，我想的是：也许这能彻底摧毁版权。如果那是最终结果，我没意见。看到由此产生的混乱很有意思。目前我们看到的主要是：人们强烈意识到，现有的美国版权体系中一些关于它应该如何运作的假设正在被我们大家无视。因为我们想先制造出这种混乱，然后再重新监管。至少在理论上，我们现在产出的很多东西，根据历史对版权解释的解读，实际上是不可申请版权的。

<details>
<summary>Original English</summary>
**Armen**: Yeah. And so like I I was like my optimal version is like copyrights don't exist in a way or like very very like limited kind of version of this. I was like I really didn't care that it spits out **GPL** code and doesn't attribute like I was like oh maybe this will just completely destroy copyrights and like for me that was like oh this is I like if if that's the outcome of like I'm I'm fine with it. So it was but it was it was an interesting kind of thing in the beginning that it sort of like it sort of creates this license violation like I want to see like what what chaos will emerge from it and so far I think mostly what has emerged from it is like a strong belief now that like the the system in place for copyrights has some presumptions assumptions in the US about how it's supposed to work and we're all kind of like ignoring that right now because we want to create the mess first and then reeregulate probably because like at least in theory a lot of the things that we're producing right now are probably by historic readings of the copyright interpretation actually not copyrightable.
</details>

### 软件质量的下滑

**主持人**: 这是一个很有意思的观点。说到现在，Armen，你最近在做一件很有趣的事：作为你新创办的公司的一部分，你在研究构建在 AI 代理之上的东西。你采访了大约 30 个不同的工程团队，了解他们如何在公司和团队内部使用代理。从大公司到初创公司，你学到了什么？

<details>
<summary>Original English</summary>
**Host**: Yeah, that that's an interesting one. But speaking of jumping jumping to today so an interesting thing that you did recently, we talked about it just before is as part of your new startup is building things on top of agents and you talked to about 30 different engineering teams saying hey how are you using agents inside of your company inside of your team? What did you learn from large companies to startups?
</details>

**Armen**: 我发现了一些很有趣但并不意外的现象。每当人们休假的时候，他们会花更多时间尝试这些工具。

<details>
<summary>Original English</summary>
**Armen**: I think the the a bunch of learnings entirely unsurprising is that whenever people had vacation, there was more time spent on um trying these tools.
</details>

**主持人**: 明确一下，你谈论的对象包括 **Meta** 这样的大厂和各种初创公司的人？

<details>
<summary>Original English</summary>
**Host**: And and just to be clear like you talk with like folks at the likes of like **Meta** Startups.
</details>

**Armen**: 是的。包括各种各样的人，从“欧洲恐龙公司”……

<details>
<summary>Original English</summary>
**Armen**: Yeah. Like like a bunch bunch of different people, right? So a bunch of different people from like different like European dinosaurs like...
</details>

**Mario**: 你在指我吗？

<details>
<summary>Original English</summary>
**Mario**: Are you pointing at me?
</details>

**Armen**: 我是指像 **Siemens** 这样的公司。我还和一些处于关键领域的公司交流过。我说“休假时才会有采用”，是因为当你的 CEO 或技术负责人过来说“你们现在得用 **Cursor** 或 **Claude Code**”时，你其实还没真正领会。你需要花时间去钻研。这大概需要两三周的时间，你才能真正感觉到它的“魔力”。我当时有很多空闲时间——我去年 4 月离开公司，直到 10 月。我就想：这怎么可能没人懂呢？

<details>
<summary>Original English</summary>
**Armen**: Well I mean like the European dinosaur would be someone like **Siemens**. Or I also talked to to companies which are sort of in a critical space. And what I mean like when adoption happens when people have vacation is that like when when your CEO or your tech lead comes and says like you got to use **Cursor** now you got to use **Claude Code** now is actually you don't get it in a way because you you need to actually spend some time on like there's a there's a it's like a two to three week kind of thing until it really clicks on you and so I I always felt like with the people that I knew like I had a lot of free time like I I left the company in April until October. I was like, I can dive into this and I I like this is like how does nobody get this...
</details>

**Mario**: 对所有人来说都是“猫薄荷”（极具诱惑力）。

<details>
<summary>Original English</summary>
**Mario**: A catnip for all of us.
</details>

**Armen**: 简直是疯狂的猫薄荷。我当时没怎么睡觉。但在公司内部似乎发生的是：到了感恩节，欧洲人则是在暑假，然后是圣诞节，很多人开始尝试。再加上这些时候他们还能得到免费的额度。所以越来越多的人开始尝试。圣诞节过后，在我交流过的一半以上的公司里，这种现象简直爆炸了。

<details>
<summary>Original English</summary>
**Armen**: It was was crazy catnip. I didn't sleep much all of this. But but what happened within the company seemingly is that when there was like Thanksgiving, there was um for the Europeans a lot of it was over summer and then at Christmas a lot of people sort of and they also get free credits during those times and so like more and more people get...
</details>

**主持人**: 你是说公司经常会给很大方的免费额度。

<details>
<summary>Original English</summary>
**Host**: Oh, you mean the the companies often give you generous...
</details>

**Armen**: 是的。随着这种现象的爆发，正如我们预料的那样，**代码质量下降**了。并不是因为人们想写烂代码，而是因为要保持代码质量真的需要付出努力。我们在去年的初创生态中已经看到了这一点。如果你关注 **YC** 的初创公司，很多人的代码都在 GitHub 上。你能看到大量的 **plan.md** 文件被提交，所有内容都归功于 **Claude**。那种“**凭感觉编码**”（vibe coding）对原型开发很有用。但逐渐地，代码库中开始堆积各种“**感性废话**”（vibe slop）。

<details>
<summary>Original English</summary>
**Armen**: So and so more and more people went into this and and especially after Christmas I would guess like in more than half the companies I talked to after Christmas it really exploded um and and it it exploded in And so in all the ways we would expect it where like all of the sudden the quality drops and and and and it doesn't necessarily drop because like people want to make worse code but because it actually takes some effort to to stay within this and we we have seen this in the startup ecosystem already in the summer last year like if you if you pay attention to like the the **YC** startups a lot of them some of them have their stuff on GitHub or for some period of time on GitHub when you can look at it and like at the time because of like **plan.md** files checked in and like everything attributed to **Claude**. So like that **vibe coding** kind of thing was was for like prototypes and whatever like that built that out. that was already out there to see. But then gradually a small version of this has like been code bases with a little bit of **vibe slop** on top.
</details>

**Armen**: 工程团队和公司对此的反应很有趣。一个普遍的发现是：**PR 审核变得极具挑战性**。PR 变得越来越大，甚至变成了一种心理压力。

<details>
<summary>Original English</summary>
**Armen**: And an interesting sort of part of this was like how engineering teams and companies are now responding to that um with all kinds of like different findings. But but a lot of it has been challenge to review **PRs**. They're getting larger and larger and they're becoming like more psychological.
</details>

**主持人**: 特别是工程师们，很难跟上这些变得更长、更频繁的 PR。

<details>
<summary>Original English</summary>
**Host**: And engineers specifically are having a hard time keeping up with the the longer **PRs** that they're more frequent.
</details>

### 代理无法感受痛苦

**Armen**: 是的。而且这些 PR 里的代码很多是工程师绝对不会去写的。作为工程师，你提交某些代码时会有一种很不舒服的感觉，因为你会考虑到未来的自己，而**代理（Agent）根本不在乎**。我会反复讲这个故事：我当时在做一款 **Xbox One** 的游戏，正赶上首发日。我们必须在截止日期前发布。我参与了《**光环：士官长合集**》的开发，当时有个匹配系统（Matchmaker）出现了问题。每个人都必须动手去清理那个由人类制造的“废代码”（slop）。

<details>
<summary>Original English</summary>
**Armen**: Yeah. And there also there a lot of the code in those **PRs** is how an engineer wouldn't do it because as an engineer you sort of get a really bad feeling committing certain code because you think of your future self and the agent really does not care. This is I I will retell this story over and over, but like I I worked uh for an **Xbox One** game at the time um right around the **Xbox One** launch. So that was like a fixed date. It has to release on that day. So I worked on um uh the **Halo: The Master Chief Collection** and there was a game where you had like a matchmaking component and you had to like start this thing and whatever. And it was like it was an all hands-on deck kind of situation where people had to go in and unslop the humanmade slop that was the matchmaker.
</details>

**Armen**: 那是一个状态多到离谱的系统。我们管它叫“涌现状态机”（emergence state machine），因为它由一个庞大系统上的 16 个布尔值组成。理论上只有 6 个有效状态，但现实中它发生了可能状态的几何级数爆炸。**AI 生成的代码**感觉就是这样：它本该是个定义清晰的系统，但实际上却是“噢，配置没加载？那我们捕获异常并加载默认配置吧”。系统本该在失败时崩溃，现在它却在不断“恢复”，导致你的代码变得比原本复杂得多，进入了更多的故障状态。这使得维护这些代码变得极其困难，因为你甚至不能要求代理进行重构。

<details>
<summary>Original English</summary>
**Armen**: And it was like it was it was a system with like way too many states. We call it an emergence state machine because it was like 16 bulls on one massive thing and like in theory there were only six valid states but in reality it was a geometric explosion of possible states. And that's how a centi code feels like where it really should only be like a very clearly defined system but in all reality they're like oh we can config doesn't load let's catch it down and load the default config. So instead of actually failing, it now recovers. But now your code is way more complex than it should be because instead of failing properly, it is now recovering and entering these many more failure states. And that makes it much harder to work with this code because you can also not really ask the agent to refactor...
</details>

**Mario**: 我觉得情况甚至比你描述的人造复杂系统还要糟糕。代理有时会有天才时刻，能吐出非常完美、简单的代码，恰好是你特定需求的那种。作为操控代理的工程师，你会觉得：“哇，这太神奇了，我可以坐享其成，因为它显然懂行。”但两分钟后，你在另一个窗口运行另一个代理，它吐出来的却是最令人发指的**恐怖垃圾**。你可能还没意识到，因为你已经陷入了“**自动化偏见**”（automation bias），认为你的代理做得很好。

<details>
<summary>Original English</summary>
**Mario**: I think it's kind of even worse than what you described about your humanmade complex system because there are moments of brilliance in agents where they spit out perfectly fine simple code exactly the amount and type of code you didn't need for that specific thing and you as the steering engineer looking at that like wow this is amazing I can just sit back and not care because it's obviously doing the thing like two minutes later you have another agent running in this window and it spits out the worst horrible garbage suppose but you might not notice because now you have fallen into **automation bias** and think your your your agent is doing the job well.
</details>

**主持人**: 你认为这在一定程度上是人类的偏见吗？通常入职一名新工程师，如果是应届生，你会审核他们的代码。如果写得烂，你会继续彻底审核，直到他能写出符合你标准的短代码。这通常需要半年或一年时间，然后你才能信任这个人。

<details>
<summary>Original English</summary>
**Host**: Do you think this might be our bit of a human bias because because you know like typically like onboarding a new engineer uh you have when you join a new grad you review their code and if it's terrible code you will review the next one thoroughly until they get to the point that oh it writes the code that I do and then it typically takes you know 6 months or a year or something like that but then you know I can trust this person.
</details>

**Mario**: 没错，但你对代理无法建立这种信任。**代理不会学习**。你可以往代理里塞很多东西，构建记忆系统，但这和人类的学习不是一回事。当然，人类也会犯错。

<details>
<summary>Original English</summary>
**Mario**: Yes, but you don't have anything like that with agents. Like agents don't learn. You can put as much stuff in the agents and do you build a memory system, but that's not the same type of learning than u a human does. Obviously, humans are failable as well. No, no, no matter.
</details>

**主持人**: 但人类有学习和保留知识的能力，对吧？

<details>
<summary>Original English</summary>
**Host**: But they have some capability of learning and retaining that learning, right?
</details>

**Mario**: 是的。而且**人类能感受到痛苦**。我认为这是人类的一个核心特征。这又回到了你之前说的：如果痛苦太强烈，人类就有动力去修复导致痛苦的根源。在代码库中，根源通常是糟糕的接口和极端的复杂性，因为你无法再维护那个系统了，所以你想除掉它。

<details>
<summary>Original English</summary>
**Mario**: Yes. And they also feel pain. And I think that's one of the defining things about humans. It's kind of ties back to what you said. Eventually, if the pain gets too big, you as a human are incentivized to fix the cause of your pain. And in a codebase, the cause is usually terrible interfaces, terrible complexity that you want to get rid of because you can no longer maintain that system.
</details>

**主持人**: 这是不是为什么资深工程师总是供不应求？在 CEO 眼中，资深工程师就是“能把事儿办成的人”。但实际上，大多数卓有成效的资深工程师都带着“战斗伤疤”。他们被坑过，感受过痛苦。他们见过当抛弃技术标准时会发生怎样的恶性循环。所以他们现在做出的每一个决策，都是为了避免那些痛苦。当然，这样进展会更快。我个人认为，**一个好的工程师是一个经常说“不”的工程师**，经常说“我不需要这个”。

<details>
<summary>Original English</summary>
**Host**: Isn't this why just holding on to that, you know, like senior engineers are always in demand because from the CEO sees a senior engineer as like they just get it done, but in reality, a senior engineer, most senior engineers who are effective, they've had battle scars. They've been burned. They felt the pain. You they saw what happened when they left tech def spiral. So they now make all these decisions that they know they they will help avoid. And of course through this uh progress goes faster. I personally think and your mileage may vary. But a a good engineer is an engineer that says no a lot and I don't need this a lot.
</details>

**Armen**: 嗯。

<details>
<summary>Original English</summary>
**Armen**: Mhm.
</details>

**Mario**: 因为这能把复杂性降下来。如果你使用代理，情况正好相反。你会说“是的，我想要这个、那个，我全都想要”，因为你不需要自己打字，不需要去思考。你只需给那个小机器一个提示词（Prompt），它就会吐出一些看起来像你想要的东西。只要“够用”就行。这就是所有问题的源头。

<details>
<summary>Original English</summary>
**Mario**: Because that keeps complexity down. If you're using agents, the exact opposite happens. You say yes, I want this and that. I want this and I want this and I want this because I don't have to type it myself. I don't have to think about it. I just give the little machine a prompt and it will spit out something that kind of looks like the thing I wanted. Good enough. And that's where all the problems start.
</details>

**Armen**: 我认为好的工程在于了解必须做出的权衡。有时最正确的方案实际上是……如果你在大学里学过，你会学到你不该这么做。我想 **Cal Henderson**（Slack 联合创始人）曾经说过：**先尝试最笨的方案，直到它行不通为止**。因为实际问题在于，你要做的事情太多了，如果你一开始就追求所谓“正确”或“完美”的解决方案，你就会制造出那种在规模化时会置你于死地的复杂性。

<details>
<summary>Original English</summary>
**Armen**: And one thing that I also think is like good engineering is all about knowing the trade-offs that you have to make. And there's sometimes the right solution is actually if you were to sort of like sit at university and learn about it, you kind of learn that you shouldn't be doing this in a way. I think **Kell Henderson** had this once where he said like you you do the dumbest solution first until it doesn't work anymore because the the actual problem is there's so much stuff that you need to do that if you actually do the right solution the correct solutions all of this it is it you're creating the kind of complexity that kills you at scale...
</details>

**Armen**: 工程师不仅能从战斗伤疤中学习，而且这种学习过程赋予了你在工程组织中说服其他工程师的权威。另外，**代理现在为你提供了通往世界知识的途径**。我采访工程团队时发现：资深工程师基于经验说“不”，48 小时后，初级工程师跑过来说：“我跟代理聊过了，我之前就有这种预感，现在我有所有证据来证明为什么我们不该按照你说的那个方式做。”

<details>
<summary>Original English</summary>
**Armen**: And the engineer learns that but also like if you if if you don't have that battle scar it's actually very hard for you to argue correctly because it is it is this learning process that gives you the authority to then convince other engineers in the engineering org that you should be doing it this way. That is part of it. You learn that. But the other thing is also that the agents give you now world knowledge access. And one of the other things that I learned through interviewing engineering teams now is that the senior person says no knowing something and then 48 hours later the junior comes by and said like I talked to the agent and I already had this inkling but now I have all the evidence of why we shouldn't be doing it this way...
</details>

**主持人**: 就像有人拿着 **ChatGPT** 的打印件去找医生说：“机器是这么说的，你最好按这个来。”

<details>
<summary>Original English</summary>
**Host**: Someone who can tell you a senior off. Yeah. Exactly. And and this this is creates other stresses now that were previously...
</details>

### 非工程师参与开发

**主持人**: 根据你们观察和交流的情况，我们是否正面临这样一种局面：经验丰富的工程师越来越难拒绝产品经理或初级工程师的要求？

<details>
<summary>Original English</summary>
**Host**: Like not every team has that because it's like people going to the doctor with a **ChatGPT** print out and saying this is what the machine said you better do that. Is it fair to say that we are based on what you're seeing and talking we might face a thing where it's very hard for experienced engineers to it's harder just for them to say no uh in spite of the product manager or a junior engineer saying...
</details>

**Mario**: 实际上情况更糟，因为**产品经理（PM）现在会直接提交 PR**，并期望自动合并。

<details>
<summary>Original English</summary>
**Mario**: It's much worse because the product management comes in sends pull requests and autom should them.
</details>

**主持人**: 是的，那是另一回事：**非工程师参与工程过程**现在成了一件普遍的事。Armen，那是怎么运作的？

<details>
<summary>Original English</summary>
**Host**: Yeah that's another thing like **non-engineers participating in engineering processes** is is a thing now. Ask how that works. Ask him how does it work? How how does it work Armen?
</details>

**Armen**: 这很难评价，因为一方面它是出于好意。有些营销团队突然开始在网站上动手脚，销售团队为了演示而创建越来越复杂的 Demo，最后甚至提交到了 GitHub。最搞笑的一个案例是：销售 Demo 里构建了一个根本不存在的功能，但没人注意到。这在以前是不会发生的。

<details>
<summary>Original English</summary>
**Armen**: Well, it's hard because if because on the one hand like it's well intended, right? So, first of all, like like we have a little bit of this air like we're small and so um like like my co-founder for instance sometimes has like a pork on the website. I talked to people that have that at scale where like the marketing team all of a sudden does stuff on a website and and the sales team like creates ever more elaborate like sales demos that sort of land up on a GitHub or partially at this one one of the most funniest one was like where the sales demo built a feature that didn't exist but nobody noticed right so this this is all like this is new right because like previously none of that happened.
</details>

**Armen**: 但我认为这具有赋能作用。以前设计师可能在 **Figma** 里构思了一些东西，但没法做成可点击的演示原型。或者 PM 想尝试一个功能，又不想浪费工程师的时间。现在你可以做到了。问题在于，人们现在太关注“人人都能做任何事”，而忘记了**你仍然需要一个流程来设置护栏**。

<details>
<summary>Original English</summary>
**Armen**: But I think it's empowering... empowering it's like there's a good thing to it in too. If your entire or if everybody in your or can participate in in in in the creation of software in some form right previously people couldn't do that like you had a designer who could figure something out in **Figma** but they might not be able to kind of put it into a clickable dummy demo whatever or you might have a **PM** who who wants to try out a feature without kind of wasting time of an engineer. Now you can do that. The problem is that people are now so focused on everybody can do everything now that they forget that you still need a process to kind of guard rail off all of that.
</details>

**Mario**: 整合部分才是最难的。Peter 提过“**提示词请求**”（Prompt Request）的概念，我越来越认同这个想法：一旦你演示清楚了你的意图，我其实不再需要你的代码。

<details>
<summary>Original English</summary>
**Mario**: And the integration part is the hard thing. It's like that Peter gave this idea of like the **prompt request**, but I'm actually really warming up to this idea like once you've demonstrated it, I no longer need your code.
</details>

**主持人**: 简单回顾一下，“提示词请求”是指 Peter 说他不喜欢收到 PR，他宁愿看到 Prompt，因为他会自己运行这个 Prompt，或者对其进行微调，让它以他想要的风格生成代码。

<details>
<summary>Original English</summary>
**Host**: And and just just to recap, the **prompt request** was him saying that he doesn't like to get pull requests. and said he would rather see the prompt because he will run the prompt or he will tweak it and it will generate it in the style that...
</details>

**Armen**: 对我来说，重点不在于我想看 Prompt，而在于通过这个动作明确“你想做什么”。创作的过程往往能理清你真正的需求。这部分的价值非常高。但最后产出的代码往往不是有资历的工程师会写的。所以不是说我想要你的 Prompt 拿来重新“搬砖”，而是既然我们知道了想构建什么，**由我来重头开始写可能反而更快**。

<details>
<summary>Original English</summary>
**Armen**: For me it's less about like I want to see the prompt as it like what is it supposed to be doing and now that we understand because like actually in many ways I think like the interesting part is like often you don't really fully know what you wanted to do in the first place and so like the act of creating clarifies what you really want to do and so like that part is highly valuable often the approach and the code that comes out of it is not what an engineer there with sufficient seniority would have done. So it's not like I want your prompt so that I can reclank my clanker so that it does it slightly better, but more like now that we know what we wanted to build, it's probably faster for me to start.
</details>

**Mario**: 我在某些点上也不同意 Peter。我实际上很看重看到一个事物的“烂实现”。如果在 **Pi** 的仓库收到一个显然是代理生成、没怎么经过人工润色的 PR，我立刻就知道它是垃圾，但是**有价值的垃圾**。因为至少有人投入了最起码的思考，指挥代理去创建这个 PR。我能看到他们想构建的东西的笨拙实现，这节省了我自己的时间，我不需要亲自去尝试那个死胡同。让天真、愚蠢的代理去犯错，这其实是在帮我省时间。

<details>
<summary>Original English</summary>
**Mario**: Yeah. And I also kind of disagree with Peter on I just need your prompt. I actually value seeing a terrible implementation of something. Um like if I get a pull request and most of the pull requests we get on the **Pi** repository are made by agents without a lot of human touch. let's say then I immediately know okay this is going to be garbage but it's valuable garbage um because someone has put in at least a minimum amount of thought instructing their agent to create this pull request and I get to see how a shitty implementation of what they wanted to build looks like and I get to I I don't need to waste my own time on trying that out. So somebody else tried it out already that the naive dumb agent do the thing do no mistakes uh version and that saves me time.
</details>

### Pi 的诞生背景

**主持人**: 说到 **Pi**，它是一个非常受欢迎且极简的编程代理。Mario，我们能从背景故事开始吗？为什么在已经有很多代理框架的情况下，你决定构建 **Pi**？

<details>
<summary>Original English</summary>
**Host**: Well, speaking of not wanting to be part of the circus, let's talk about **Pi**, which is a which is a very popular and also minimalist coding agent. Can we start with the the backstory of why you decided to build **Pi** at a time where there were already uh agent harnesses around right because they were suboptimal.
</details>

**Mario**: 没问题。我曾是 **Claude Code** 的忠实拥护者，因为他们通过发明“**代理化搜索**”开创了这一流派。虽然之前有先驱，但他们是第一个将其封装得如此出色的人。在当时，它非常契合我的工作流。它简单且可预测。虽然 **LLM** 本质上是概率性的、不可预测的，但围绕它的所有环节都很整洁、易懂。

<details>
<summary>Original English</summary>
**Mario**: Yeah, sure. I so I I was a a believer in **Claude Code** just because they kind of created that whole genre through the invention of a gentic search. I mean inventions. There were precursors to that and shows of giants and so on, but they were the first that packaged it up in a really compelling package. And at the time that fit my workflow really well. It was simply it was predictive. So the **LLM** um uristic nature or stoastic nature of of being kind of unpredictable, but everything around the **LLM** was kind of nice and tidy and easy to understand.
</details>

**主持人**: 所以你曾是 **Claude Code** 的快乐用户。

<details>
<summary>Original English</summary>
**Host**: So were you were a happy user of **Claude Code**, right?
</details>

**Mario**: 曾经非常快乐。但后来团队开始疯狂“吃自家狗粮”，团队规模和开发速度都在增加。随之而来的是更多功能，以及**多得多的 Bug**。我个人喜欢简单且稳定的工具，即使它们包含非确定性的部分，我也希望我能依赖它们。所有确定性的部分都应该是尽可能稳定的。但在 2025 年夏天左右，**Claude Code** 的体验不再是这样了。

<details>
<summary>Original English</summary>
**Mario**: I was super happy. I was proitizing it. But eventually the team started dog fooding and getting more and more tokens I guess and kind of increased velocity and team size. And with that came more features and much much much more bucks. And I personally like simple tools that are stable um that I can rely on even if they have non-deterministic parts. But all the deterministic parts should be as stable as possible. And that was just not the experience with **Claude Code** around summer 2025.
</details>

**主持人**: 是因为 Bug 还是意外行为？

<details>
<summary>Original English</summary>
**Host**: So I kind of soured on that real hard. Was it was it bugs? Was it unexpected behavior?
</details>

**Mario**: 比如他们剥夺了你对**上下文**（Context）的控制权。他们会在你背后悄悄注入东西，这很糟糕。你过去行之有效的工作流失效了，因为现在 UI 里甚至看不到“系统提示”（System Reminder）在修改模型的行为。他们还会修改系统提示词。我甚至反向工程了它——我不会把打开并格式化一个混淆后的 JavaScript 文件称为真正的反向工程，但我在 2025 年夏天反向工程了 **Claude Code**，并建立了一个小服务来追踪其系统提示词和工具定义的演变。几乎每一个版本都在乱改东西。如果你想看到这些，可以去访问 `CC-history.Mario.at`。这彻底打乱了我的工作流。如果我选择了一个开发工具，我希望它像锤子一样稳定可靠，而不是每天都在不同的地方坏掉。

<details>
<summary>Original English</summary>
**Mario**: Like so they take away your control of the context. They would inject stuff behind your back which is bad. And then your workflows that used to work stop working because there's now a system reminder that you don't even see in the UI. Um that will modify the behavior of the model. They would also do this to the system prompt. I I I reverse engineered. I mean, I wouldn't call opening an offiscated JavaScript file and unoffiscating it reverse engineering coming from a more low-level background, but I reverse engineered **Claude Code** during the summer of 2025 and build a little service where I can track the progression or evolution of the system prop and tool definitions in **Claude Code** and it's like every release it was like messing with stuff. `CC-history.Mario.at` if you want to see that. And uh yeah, that that just messed with my workflows and I don't appreciate that. If I commit to a development tool, I want it to be a stable, reliable thing like a hammer. I don't want my hammer to break at a different spot every day.
</details>

**主持人**: 这听起来像是“快速行动，打破常规”，但打破常规并不适合你。

<details>
<summary>Original English</summary>
**Host**: It sounds like the move fast and break things. to break things was not for you.
</details>

**Mario**: 是的。后来我研究了开源替代方案，发现即使是它们，也会在我背后对上下文做手脚。比如在工具输出超过一定 token 后自动删减结果，或者在模型每一次编辑后都去询问 **LSP**（语言服务器协议）服务器是否有错误。

<details>
<summary>Original English</summary>
**Mario**: No. And uh then I looked into alternatives and found **Open Code**. But while that kind of wipes me with my OSS roots, um it too did stuff to the context I didn't appreciate behind my back. Um pruning tool results after a certain amount of uh uh tool result token output or asking an **LSP** server after every single edit the model makes uh if there is an error.
</details>

**Mario**: 实际上，模型的工作还没完成，代码当然无法编译，LSP 服务器肯定会报错。在模型编辑过程中不断注入错误诊断信息是非常愚蠢的，这只会让模型感到困惑。最后，我发现 **Open Code** 也不适合我，我甚至得通过 Fork 才能修改它。于是我想，这能有多难？我干脆自己写了一个。

<details>
<summary>Original English</summary>
**Mario**: Yes, there will be an error because the model isn't done yet with its work. So the code doesn't compile. So the **LSP** server will... when you go into VS Code and you type some TypeScript you have like in the bottom some error diagnostics and that comes from an **LSP** server for TypeScript. The model calls an edit tool to change lines and they would inject the diagnostics after every edit call and that's just not smart because now you're confusing the model with you have an error, you have an error, you have an error on the model like yeah I know I know I'm not done yet. Oh, it's not Yeah, it's not great. Anyways, TLDDR uh **Open Code** wasn't for me um either. It was also I had to fork it to modify it which I don't think should be necessary. So then I just thought how hard can it be? I built my own little thing.
</details>

### 自我修改的软件

**主持人**: 你的那个“小东西”非常极简。**Pi** 的基本原理是什么？

<details>
<summary>Original English</summary>
**Host**: And then your own little thing is pretty minimalistic. What does it use? What's the basics of of **PI**?
</details>

**Mario**: **Pi** 的基础是我自己对所有 LLM 提供商 API 的抽象，因为我不喜欢 Vercel 的 AI SDK，Armen 后来也写了一篇博客专门讨论这个。它很好用，很多人在用，但它不符合我作为一个“老家伙”对抽象的品位。

<details>
<summary>Original English</summary>
**Mario**: The basics of **PI** are um my own abstraction over all the LM provider APIs because I didn't like the **Vercel SDK**, the Vercel AI SDK for various reasons. Armen kind of wrote a blog post eventually about that as well. It's obviously good to use. Lots of people use it. It just didn't fit my old man um sense of abstraction.
</details>

**Mario**: 我构建了一个通用的、带有工具调用和流式传输的**代理循环**（Agent Loop）抽象，还做了一个不太会乱闪烁的 **TUI**（终端 UI）。它的可扩展性来自于这个极简核心拥有非常多的“钩子”（Hook Points），你可以通过一个简单的 **TypeScript** 模块挂载进去。这允许你为 LLM 提供自定义工具、重写上下文压缩实现，甚至完全翻新 TUI。

<details>
<summary>Original English</summary>
**Mario**: Then I built a little abstraction for generalized agent loop with tool calling and streaming all of that. I built a bespoke little tool that doesn't flicker or not a lot. And then I tied that all together into a coding agent that looks like Claude Code or Codex or whatever you have. Um that's it. And the extent ability comes from the fact that this minimal core has so many hook points uh that you can basically hook into with a simple **TypeScript** module um that gets loaded into the same node process and that allows you to do things like provide the LLM with custom tools uh do your own compaction implementation uh fully revamp the TUI itself.
</details>

**Mario**: 这种能力带来了一个巨大的飞跃：你可以要求 **Pi** 修改它自己。因为有这些扩展点，它可以编写代码来扩展自身。这听起来很简单，但却是一个巨大的释放。

<details>
<summary>Original English</summary>
**Mario**: You can modify everything in the TUI. If you have a special workflow, you can change the TUI to become whatever you need. I have a couple of non-techy friends that did that because they don't need to know how to build this they can just ask **Pi** to build it and **Pi** will modify itself. So you can ask **Pi** to modify itself because of the extension points and it can write code that extends itself and it's trivial, but it's a big unlock.
</details>

**主持人**: 这就是你说的，对于 **Open Code** 你需要 Fork 才能修改，而 **Pi** 不需要。据我了解，它自带的工具只有：Read, Write, Edit, Bash。

<details>
<summary>Original English</summary>
**Host**: Is this what you meant when you said that? For **Open Code**, you needed to fork it to to modify it. It doesn't have this. So, I guess **Pi** Star has this very minimalistic thing. As I understand the the tools it has is read, write, edit, bash.
</details>

**Mario**: 就这些，这就是你需要的全部。然后你可以开始把它变成你自己的。比如 **Pi** 原本没有 **MCP**（模型上下文协议）支持，人们就直接要求 **Pi** 把 MCP 支持构建到 **Pi** 里面。**Pi** 原本没有“计划模式”，虽然 Armen 实现了五个版本的计划模式，直到他意识到计划模式完全没用。

<details>
<summary>Original English</summary>
**Mario**: It's all you need. That's it. And and then you can actually like start to make it your own like okay like at at what are examples that people would add. **Pi** doesn't have **MCP**. People just ask **Pi** to build **MCP** support into **PI**. **Pi** doesn't have a plan mode. Armen goes and my plan mode must be fantastic bespoke and super. But he has like five implementations of a plan mode until he realized plan mode is entirely useless.
</details>

**Armen**: 对我来说，吸引我的不仅仅是抽象层，还有**自定义工具**的部分。圣诞节期间，我试着做了一些东西。我想要构建一个我不需要看代码的工具。我希望它是“**凭感觉开发**”，但又不能看起来像废代码。我希望即使我不看代码，它最终呈现出来的也像是我亲手写的。我想做一个游戏。

<details>
<summary>Original English</summary>
**Armen**: What drew me to it beyond like actually using the library abstraction was was in fact the the custom tools part because um one moment for me was um over Christmas again like many people had some time and I tried to build other things and I and Peter was talking to me in in November that he's like vibing without looking at code more or less. I don't know exactly how he said like but like he's like he can do this now like okay I I want to build a thing where I don't look at the code. I wanted it to not look like slop. I wanted I wanted a version of it where like afterwards like even though I don't really look at the code it should look like what I would have written and so and I wanted to make a game...
</details>

**Armen**: 我让 **Pi** 在构建游戏之前先设置好代码库，以便它能验证自己所做的更改。它为游戏内置了一些调试工具，可以截屏、运行模拟并导出状态。**Pi** 还可以在 TUI 中显示图像。它还有一个伟大的功能：可以回退到对话的早期状态，然后**开启新的分支**来尝试不同的方案，因为带有截图的会话 token 消耗非常快。

<details>
<summary>Original English</summary>
**Armen**: I basically started the whole experience with like a just basic **Pi**... I want you to set up the codebase in a way that you can validate the changes that you're making but also I can see them... O have the agent be able to validate itself and and what what sort of emerged out of that was well first of all like it built itself some debugging tools into the game so it can make screenshots and like run a simulation and sort of dump out state and read it again but also **Pi** can can show images in a TUI... it can reverse to an earlier state in the conversation and then it can branch within the conversation to build a bunch of stuff around that because like these the sessions especially with screenshots and it become very token inefficient very quickly.
</details>

### 复杂性是最大的敌人

**主持人**: 你们都提到了工程中的平衡问题。你们一方面想要通过代理消除摩擦，但另一方面也需要“护栏”。Mario，你最近写了一篇博客叫《**我们都需要慢下来**》（We All Need to Slow the F Down），能分享一下触发你写这篇文章的想法吗？

<details>
<summary>Original English</summary>
**Host**: You just recently wrote on on the same theme a blog post called **we all need to slow the f down** can we rehash some of the thinking and what triggered you?
</details>

**Mario**: 基本核心在于：你的代理现在的代码产出速度可能是你的 10 倍，但也意味着它吐出的 Bug 和错误也是你的 10 倍。即使它的错误率只有你的一半，也是你的 5 倍。所以你代码库恶化的速度增加了。想象一下“**黑暗工厂**”（Dark Factory），用 100 个代理对你的代码库进行这种操作。结果会怎样？

<details>
<summary>Original English</summary>
**Mario**: The basic gist is okay, your agent can now spit out 10 times more code a day than you can, but it also means it spits out 10 times more bugs, errors. Even if it has half your error rate, then okay, it's not 10 times more. It's five times more. It is still more than you would spit out. So the rate of deterioration in your codebase has now increased. And now go **dark factory**. Now take a 100 agents that do this to your codebase. What's the end result of that?
</details>

**Mario**: 作为一个人类，你每天大概能产出 1.5k 行代码，这大约也是你能高质量审核的极限。如果代理吐出 10 倍的代码，你根本没法审核。我不关心代码是手写的还是代理写的，我只在乎质量。那些宣称所有代码都是代理写的公司——是的，我们知道质量是垃圾。我们使用这些产品时能从骨子里感觉到。

<details>
<summary>Original English</summary>
**Mario**: But you can't as a human because as a human you're used to spitting out 1.5k lock a day and that's about the limit that you can actually review well right agent spits out 10 times that no chance you can review that. And not not all of the code by the agent might be important like the HTML export thing, right? But even if the agent spits out three to 5k a day, you have no way of reviewing that in any meaningful sense. All the companies claiming that all of their code is now written by agents. Yes, we know quality is garbage. We feel it in our bones when we use your products. It's garbage.
</details>

**Mario**: 我认为人们需要转过身来问问：“我们到底在干什么？”这些机器本该帮我们处理那些讨厌的琐事，让我们有更多自由时间去思考真正有趣的部分：我们到底想构建什么？我们的用户需要什么？如果我们决定构建某个东西，我们可以动用代理去把它磨光，因为我们现在有时间、有手段也有工具去做得非常出色。但现在不是这么干的，我们只是在构建代理大军。

<details>
<summary>Original English</summary>
**Mario**: Basically I think people need to turn around and say, "Hey, what what are we even doing here?" Um, we have these wonderful machines now that can take away so much pain from us by doing the stuff we hate doing and doing that really well. Why don't we start by giving us some more free time to work on the interesting bits and delegating the stuff we know they can do to them large on large like like uh across the entire organization. find all the things that annoy the out of you and have the Asians automate that for you. And then you suddenly have time to think about what do we actually want to build? What do our users need? And if we decide to build the thing, then we can pull in the agents again and say, and we're going to polish the out of that because now we have the time and the means and the tools to do an excellent job.
</details>

**主持人**: 你曾说**复杂性**是你最大的敌人。这也是代理最大的敌人。

<details>
<summary>Original English</summary>
**Host**: You wrote somewhere that your biggest enemy is complexity. It's also your agent's biggest enemy. Can we talk about that?
</details>

**Mario**: 非常简单。如果我有一个 60 万行的代码库，而我的代理在 20 万 token 的**上下文窗口**内最有效，代理能看到多少？只有三分之一。假设信息检索问题解决了，所有相关代码都能塞进窗口。但现实是，代理吐出的代码太多，导致在新任务中，它们自己都没法把这些代码读进上下文了。

<details>
<summary>Original English</summary>
**Mario**: Very simple. If I have a 600k lines of code code bis and my agent can at best be affecting effective up to a context window size of around 200,000 tokens, how much of the code can the agency see? A third, right? Are you sure that the agent finds all the relevant code it needs to find to to fulfill a thing that's also where all the garbage code comes from because it doesn't see all the thing it needs to see. But the agent spit out so much code they themselves cannot possibly read into their context on a new task anymore.
</details>

**Mario**: 它们增加的复杂性成了它们自己最大的敌人。最终代码库会变得如此庞大、复杂且交织，以至于代理在技术层面上根本无法摄取所需的全部上下文。而且，代理是从互联网上学习的，那里充满了垃圾和老旧代码。机器学习模型会收敛于**平庸的平均值**，而不是少数工程精湛的项目。

<details>
<summary>Original English</summary>
**Mario**: The complexity they add is their own worst enemy because eventually the code base will be so big and so complicated and so interconnected um that the agent has absolutely no way on a technical level to ingest all the context it needs to do the new task. And a machine learning model will kind of converge towards not the well simplified to the mean right and what is the mean then it's it's not the handful comparatively of excellently engineered projects it's all the garbage on the internet all the cargo culting all the trend type of the day kind of stuff and that's what we get when we let the agents do all the things for us.
</details>

### MCP 与 CLI 之争

**主持人**: 另一个有争议的话题：**MCP** 与 **CLI**。现在我听到很多人在说 CLI 才是未来，而你们两个似乎也是支持者。但 MCP 在大公司内部似乎找到了真正的市场契合点。

<details>
<summary>Original English</summary>
**Host**: Let's talk about another controversial topic. **MCP** versus **CLI**. And you know, right now I'm hearing a lot of people really going for **CLI** is the future. And I think I'm sitting with two of them. But also **MCPs** are also really popular inside of large companies.
</details>

**Armen**: 尽管人们可能这么想，但我其实并没那么讨厌 **MCP**。

<details>
<summary>Original English</summary>
**Armen**: Despite what people might think, I don't actually hate **MCP** quite as much.
</details>

**Mario**: 哦，等一下，我们录音存证了。

<details>
<summary>Original English</summary>
**Mario**: Oh. Oh, wait. We have it on recording.
</details>

**Armen**: 哈哈，我们不是绝对主义者。我对 **MCP** 的根本挑战在于它的规范非常复杂。归根结底，它做的是身份验证、调用一些东西。它会非常快地填满你的上下文。代理非常非常擅长**运行代码**，而 MCP 还不完全是运行代码。我认为胶水必须是代码执行。由于 MCP 服务器目前的定义方式模型并不真正理解，我还没发现能可靠地组合（Compose）MCP 工具的方法。

<details>
<summary>Original English</summary>
**Armen**: Yeah. No, we don't deal in absolutes. So I my fundamental challenge with **MCP** is that I think first of all the spec is very complex. So what is it really doing at the end of the day it's it's authentication and it's sort of invoking some stuff and **MCP** for the most part is run some stuff put stuff back in the context and then work with it. So it fills your concept very quickly. But the agents are just very very very very good at running code and **MCP** is not quite running code. I want it to work and I my my suspicion is still the glue is is has to be code execution but because **MCP** servers are largely not defined in a way that the model actually understands them. I haven't found ways to compose **MCP** tools reliably.
</details>

**Mario**: 我觉得它只是自身成功的受害者。它的初衷是让外部服务接入面向消费者的聊天应用，连接邮件、OneDrive 之类。这是一个非常棒的用例，我不希望我妈妈通过生成代码来调用 API。

<details>
<summary>Original English</summary>
**Mario**: I I think it's just a victim of its own success really. When the whole thing started, I think it was in October 2024, it was more or less a solution to get external services into uh consumer-facing chat apps. Connect your emails, connect your one drive, connect your whatever. Perfectly fine use case.
</details>

**Mario**: 但在开发者端，人们开始构建把整个 **OpenAPI** 规范映射成无数工具的 MCP 服务器。那就是一切分崩离析的地方。大公司为了赶速度，直接把 API 的 OpenAPI 规范塞进去做成 MCP 服务器，那是垃圾。其次，它本质上是不可组合的。如果你想组合两个不同服务器的输出，数据转换和组合必须经过模型上下文，由模型来做。

<details>
<summary>Original English</summary>
**Mario**: And then developer side also picked it up... And then people started building **MCP** servers that would just basically map an entire open API spec into a gazillion tools. And that's where it all fell apart. So that's the first problem. Very bad **MCP** servers from big corporations that thought we need this now. What's the the fastest thing we can build? I just push the open API spec of our APIs through this thing and make it an **MCP** server. That's garbage. The second problem is that it's inherently non-composable. Um if you want to combine a tool out the **MCP** tool outputs of two different servers, they need to go through the context the the model itself needs to do the data transformation the composition...
</details>

**主持人**: 相比之下，**CLI** 就是管道（Pipe），对吧？

<details>
<summary>Original English</summary>
**Host**: And compared to this with a **CLI**. It's a pipe, right?
</details>

**Mario**: 没错。模型只看到最终结果，它可以非常自由地处理数据。这就是 **Code Mode** 的理念：它是个补丁。既然我们知道 MCP 在某些需要组合数据的用例中行不通，那就建立 Code Mode，把 MCP 服务器暴露为 TypeScript 函数，让模型通过写代码来调用并组合它们。既然如此，我们为什么不直接让模型写代码呢？我们根本不需要 MCP 服务器。

<details>
<summary>Original English</summary>
**Mario**: Exactly. the the model only sees the end result and it is it is super free in how it massages that data and that's also the idea behind **code mode** basically it's a hack it's basically okay we now have **MCP** we know it doesn't work for this specific use case where you have multiple sources of true data and you want to combine them but don't kind of pull that through the context so let's build code mode and code mode is basically we take all the **MCP** servers you expose that as functions in Typescript and then the the model can actually just write some code that calls the **MCP** service and then does the composition in the code. We can just let the mod write the code. We we don't need the **MCP** server.
</details>

### 2027 年的展望

**主持人**: 预测一年后的情况。到 2027 年，你们认为这些编程代理和软件工程工作流会是什么样的？

<details>
<summary>Original English</summary>
**Host**: Trying to predict a year out which is hard but in in 2027 knowing some of these basics just again from first principles where do you think these coding agents might be and the software engineering workflow might be...
</details>

**Mario**: 我不知道，说实话我完全没主意。我可能会编造一些可能不会发生的事。但我相信“**软件自我修改**”这点。我认为我们会看到更多这方面的进展，不仅在技术领域，也会扩展到非技术应用。

<details>
<summary>Original English</summary>
**Mario**: I have no idea. I honestly have no idea. I I could make up something that's probably not going to happen. I I think the **self-mability** thing is obviously something I believe in. I I think we will see more of that and and see... yeah, including the tools themselves with with which we built the software.
</details>

**Armen**: 在 AI 时代，一年感觉像七年（犬龄计算法）。这让我很难对未来做任何预测。我的一个强烈假设是：随着越来越多的人意识到可以用代理做有趣的事，社会也会意识到我们现在是多么依赖于那两家公司。作为一个欧洲人，我们应该讨论这个问题。我猜会有一些工程团队意识到，如果没有机器，他们已经无法维护现有的代码库了。

<details>
<summary>Original English</summary>
**Armen**: My is it dog years with your time seven is that how it works. When you ask me like what's going to be in in a year it's like seven years right and to me that makes it incredibly hard to have any sort of predictions about the future. My my my strong hypothesis is that as more and more people are starting to wake up to this you can do interesting things with agents there will be a societal recognition also of how much more dependent you are on basically two companies and I think we'll have a conversation about that part uh we should have a conversation about that particular as Europeans. I engineering teams already now telling me that they have code bases that they think they couldn't maintain anymore without the machine.
</details>

**主持人**: 作为结束，有没有什么书可以推荐？

<details>
<summary>Original English</summary>
**Host**: As closing, what's a book that you would recommend and why?
</details>

**Mario**: Petzold 写的《**编码**》（Code）。

<details>
<summary>Original English</summary>
**Mario**: **Code** by Petzold.
</details>

**主持人**: 经典。

<details>
<summary>Original English</summary>
**Host**: Classic.
</details>

**Mario**: 我太爱这本书了。即使是非技术人员也读得下去。如果有人问我我的工作是什么，我会指着那本书说：它和电脑的关系比你想象的要小得多。

<details>
<summary>Original English</summary>
**Mario**: I just love it. It's just such a great read. It's also for non techies and it's the first thing I recommend if anybody asks me what's your job and pointing at that it's like it has much less to do with computers than you think.
</details>

**Armen**: 我最近读了《**飙升**》（Breakneck），它探讨了中国是如何运作的，以及欧洲和美国有何不同。我觉得至少很能启发思考。

<details>
<summary>Original English</summary>
**Armen**: And I read recently **Breakneck** which I unfortunately forgot the author of um it sort of goes a little bit into an exploration of like how China works and how maybe Europe and and the US are different. and I found it at least um thoughtprovoking.
</details>

**主持人**: Mario, Armen，非常感谢这次对话。

<details>
<summary>Original English</summary>
**Host**: Well, Mario and Armen, thanks a lot for for this conversation. It was great to have it in person.
</details>

**Mario**: 谢谢邀请。

<details>
<summary>Original English</summary>
**Mario**: Thanks for having us.
</details>

**Armen**: 谢谢。

<details>
<summary>Original English</summary>
**Armen**: Thank you.
</details>