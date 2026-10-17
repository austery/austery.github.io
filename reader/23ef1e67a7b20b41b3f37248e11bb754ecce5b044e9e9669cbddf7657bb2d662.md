---
author: The Pragmatic Engineer
date: '2026-05-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=K-Xv8D8NjTk
speaker: The Pragmatic Engineer
tags:
  - language-design
  - tooling-support
  - verification-testing
  - performance-optimization
title: 编程语言设计与演进的深层思考
summary: 本文探讨了从早期编程环境到现代语言设计的多个关键里程碑，包括对特定技术（如快速迭代、面向对象设计）的追求。文章分析了特定语言的命名由来、核心设计目标（如托管代码、垃圾回收）、成功要素（如工具支持的可擦除类型系统），以及在人工智能时代下，关于测试和验证的瓶颈问题，并总结了开发者工具与编程语言的不可分割性。
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
### 名字的由来

**主持人**: 为什么它被命名为 **Turbo Pascal**？

<details>
<summary>Original English</summary>
**Host**: Why was it called Turbo Pascal?
</details>

**Anders Hejlsberg**: 因为它非常快。那是 **Audi** 推出 Quattro 和 Turbo 系列的时候。这个东西运行飞快，而且具有超强的交互性。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Cuz it was fast. This was when Audi had their quattros and their turbos. And this thing was fast and super interactive.
</details>

### C# 的设计目标

**主持人**: 当你开始构建 **C#** 时，你的设计目标是什么？

<details>
<summary>Original English</summary>
**Host**: When you started out building C#, what were your design goals?
</details>

**Anders Hejlsberg**: 我们知道我们想构建一种**面向对象**的语言。我们想要**托管代码**或字节码，以便我们可以针对不同的运行时环境。我们想要**垃圾回收**和**异常处理**，但同时也想要诸如**统一对象系统**之类的东西。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: We knew we wanted to build an object-oriented language. We wanted manage code or bite code so we could target different runtime environments. We wanted garbage collection and exception handling, but also things like a unified object system.
</details>

### TypeScript 成功的关键

**主持人**: 你认为是什么让 **TypeScript** 如此受欢迎？

<details>
<summary>Original English</summary>
**Host**: What do you think made Typescript this popular?
</details>

**Anders Hejlsberg**: 绝对是因为更好的**工具支持**。我们完全看准了这一点：添加一个**可擦除的类型系统**，并利用它来实现强大的工具支持，这才是真正实现生产力提升的地方。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Absolutely. Because of the better tooling. We were totally right there that adding an erasable type system and then using that to enable great tooling is where the productivity boost is realized.
</details>

### AI 与编程语言

**主持人**: 对于修改现有语言以适应 AI 使用，或者开发一种更适合 **AI Agent** 使用的新语言，你有什么看法？

<details>
<summary>Original English</summary>
**Host**: What is your take on either modifying existing languages for AI usage or coming up with a language that is more suited for AI agents to use?
</details>

**Anders Hejlsberg**: 唔，我一个比较轻率的回答是……

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, my flippant answer there is...
</details>

---

### 传奇背后的故事

**主持人**: **Anders Hejlsberg** 是科技行业最伟大的在世传奇之一。他创造了 **Turbo Pascal**、**Delphi**、**C#** 和 **TypeScript**。他对编程语言和开发者工具产生的影响是巨大的。

今天，我们将与 Anders 讨论：如果不是因为 **Sun** 与 **Microsoft** 关于 **Java** 的诉讼，C# 可能根本不会诞生；TypeScript 幕后的故事，以及为什么将其**开源**在微软内部是一件大事。他从 40 年的语言设计中学到了什么，包括为什么 **IDE** 和编程语言是相辅相成的，等等。如果你想深入了解历史上最常用的三种编程语言是如何构建的，以及 AI 如何改变我们对编程语言的使用，本期节目非常适合你。

在开始之前，我想介绍本季的赞助商 **Antithesis**。我看到行业内的一个明确趋势是更加关注**测试**，这在 AI 的推动下并不令人意外。我们知道软件很难测试，而 AI 正在通过生成越来越多、越来越复杂的代码使情况变得更糟。瓶颈正在变成代码审查、测试和信任。

我们倾向于认为代码审查是瓶颈，因为你无法随着 Token 支出的增加而线性扩展人工审阅者。但问题其实超出了代码审查的范畴。实际上，它是关于**验证**。我们知道 AI 无法自我验证。要验证 AI 生成的软件的正确性，我们需要捕捉传统测试会遗漏的问题，包括在以超人速度变化的代码库中我们甚至没有想到的问题。而且，我们需要在部署到生产环境之前完成所有这些工作。验证软件运行的唯一方法是在现实的错误环境下运行它。而这正是 Antithesis 所做的。

Anders，欢迎来到播客。

<details>
<summary>Original English</summary>
**Host**: Anders Hejlsberg is one of the biggest living legends in the tech industry. He created Turbo Pascal, Delphi, C#, and TypeScript. The impact he has had on programming languages and developer tools is immense. 

Today with Anders, we discuss how C# might have not been born if it was not for the Sun versus Microsoft lawsuit over Java. The behind-the-scenes story of TypeScript and why open sourcing it was a huge deal inside of Microsoft. What he's learned from 40 years of designing languages, including why IDEs and programming languages go hand in hand, and many more. If you want a behind-the-scenes look at how three of the most used programming languages in history got built and how AI might change our usage of programming languages, this episode is for you. 

Before we start, I'd like to introduce our presenting sponsor for this season, Antithesis. A definite trend that I'm seeing across the industry is a lot more focused on testing, unsurprisingly, thanks to AI. We know that software is hard to test. And we also know that AI is making it worse thanks to producing increasingly more code and more complex code. The bottleneck is becoming reviewing the code, testing it, and trusting it. Or is it? We tend to think that code reviews are the bottleneck because you cannot scale human reviewers with token spend. But the problem actually goes beyond code review. Really, it's about verification. We know that AI cannot verify itself. To verify the correctness of AI generated software, we would need to catch issues that traditional tests miss, including issues that we did not even think of in a codebase that is changing at superhuman speed. Oh, and we need to do all of this before deploying to production. The only way to verify that software works is to run it with realistic faults. And this is exactly what Antithesis does. You can bring the system you work on under test and verify that it works as it should. Anders, welcome to the podcast.
</details>

**Anders Hejlsberg**: 谢谢。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Thank you.
</details>

### 与计算机的初次邂逅

**主持人**: 很高兴见到你。你创造了这么多广泛使用的编程语言，包括我最早学习编程时使用的 **Turbo Pascal**。你是如何进入编程领域的？

<details>
<summary>Original English</summary>
**Host**: It's brilliant to meet you. You've created so many widely used programming languages, including the one that I learned first to program with, Turbo Pascal. How did you get into programming?
</details>

**Anders Hejlsberg**: 我很幸运，我读的高中——那是在哥本哈根——为学生提供了接触计算机的机会。那是丹麦最早这样做的几所高中之一。那是 70 年代中后期。我当时就被迷住了，就在那时，通过这种可以编程并让它做事的机器，以及弄清楚它是如何组合在一起的奇妙过程。

当然，按照现代标准，它完全是古董。那是一台 **HP 2100**，拥有 32K 的磁芯存储器。你真的可以打开它，看到里面的磁芯。那太神奇了。有纸带阅读机，后来我们有了一个 1 兆字节的 14 英寸硬盘，那在当时就是顶级配置。**引导程序**在纸带上，因为机器里没有 ROM。所以启动时它什么都不知道，你必须打入指令序列来加载引导程序，然后引导程序再从硬盘加载操作系统。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, I was lucky enough to attend a high school, this is back in Copenhagen, that offered students access to a computer. It was one of the first high schools in Denmark to do so. And we're talking mid to late '70s now. And I sort of got bitten by it then, just this idea that you could program this machine and make it do things. And, you know, the wonder of figuring out how it was put together. Of course, it was like completely ancient by modern standards. It was like this HP 2100 with 32K of ferrite core memory. You could literally open it up and see the ferrite cores. I mean it was amazing, you know, paper tape reader and then we got a 1 megabyte 14in hard drive and that was just state-of-the-art. The bootloader was on paper tape cuz there was no ROM in the machine. So it started up and knew nothing and so you had to type in the instruction sequence to load the bootloader that would then load the OS off of the the hard drive.
</details>

**主持人**: 作为一个孩子，你开始在上面编写什么程序？是什么捕捉了你的想象力？

<details>
<summary>Original English</summary>
**Host**: And as a kid what did you start to program on it? What captured your imagination?
</details>

**Anders Hejlsberg**: 那是一台惠普。所以它有 **Fortran**，我觉得非常奇葩。它有一个非常慢的 **BASIC** 解释器，但它也有 **Algol**——惠普版本的 Algol，这是一个有趣的编译器实现，因为它不支持**递归**，这挺离谱的。

那台机器的调用指令会将返回地址存储在子程序的第一字里，然后执行；返回时，你就跳转到那个字所指向的间接地址。所以如果你调用自己，你就会陷入死循环。当然，当时没有任何调试器来帮你弄清楚这些。你必须非常小心地选择算法。但它是编译成机器码的，运行得很快。你可以构建游戏，那是我们主要做的事情，比如月球着陆器之类的。那很有趣。那时候一切都那么简单，你可以一眼看穿到底层。没有分层，什么都没有。你就直接在硬件之上。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, this was a Hewlett-Packard. So, it had Fortran, which I found to be very quirky. It had a very slow BASIC interpreter, but then it had Algol, Hewlett-Packard's version of Algol, which was an interesting compiler implementation because it didn't support recursion, which is kind of bizarre. You know, the call instruction of that machine would store the return address in the first word of the sub routine and then just execute and then to return you would jump to that indirect through that word. So if you called yourself you'd just be gone forever you know so and of course there were no debuggers or anything to help you figure this out. So you just had to be real careful about which algorithms you used. But but it was it was compiled in machine code and they ran you know and it was like you could build games which is what we mostly did like lunar landers and what have you kind of thing right? So yeah it was fun. Back then things were so simple right you could see all the way to the bottom. I mean there was just no layering and nothing. It was you right on top of the hardware.
</details>

**主持人**: 我想那时你也确实需要能一眼看到底层。

<details>
<summary>Original English</summary>
**Host**: I guess you needed to see all the way to the bottom as well pretty much right back then.
</details>

**Anders Hejlsberg**: 是的，它就是这么简单，你可以做到。这就是那些早期的美妙之处。对于 8 位微机，甚至早期的 PC 都是如此。随着时间的推移，我们增加了越来越多的层。现在我们确实有很多层，这是肯定的。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, I mean you it was just so simple that you you could right and that was the beauty of those early and that was true with the 8-bit micros and even you know the early PCs and whatever right and then we've just added more and more layers over time. We have a lot of layers right now. That's for sure.
</details>

### 第一个编译器的诞生

**主持人**: 你是如何从开发游戏转向构建你的第一个编译器的？那个编译器是什么？

<details>
<summary>Original English</summary>
**Host**: And how did you go from building games to actually building your first ever compiler? And what was that compiler?
</details>

**Anders Hejlsberg**: 我是在 79 年进入丹麦技术大学的。那时，8 位微机刚刚开始出现。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: I started in 79 at the Danish Technical University. At that time also, you know, this was right when 8-bit micros were starting to become available.
</details>

**主持人**: 8 位微处理器，对吧？

<details>
<summary>Original English</summary>
**Host**: 8 bit microprocessors, right?
</details>

**Anders Hejlsberg**: 没错。通常是你买回来必须自己焊接的套件，当然它们往往无法工作，然后你得弄清楚为什么不工作。所以你也学到了很多关于硬件的知识。我买了一台英国的基于 **Z80** 的套件电脑，叫做 **NASCOM**，并开始在那上面学习汇编语言编程。

后来我遇到了一些大学伙伴，我们最终成立了一家公司。我们在哥本哈根开了第一家电脑店，你可以走进去买一台这种套件电脑。后来我们卖 **Apple II**、VIC-20、**Commodore 64** 等等，各种不同的电脑。我在那些机器上做了很多编程工作，发现编程才是真正让我享受的事情。

当然，它们都带微软的 ROM BASIC，虽然慢，但可以让你写程序。但我总觉得缺少一种真正的编程语言，比如我学过的 Algol。然后我的搭档，也就是和我一起开公司的那个人，他说：“有一种新东西叫 **Pascal**，你应该看看，据说它甚至比 Algol 还简单。” 实际上我们创造的每种语言都是如此，随着时间的推移，它们变得越来越简单。Pascal 并不难实现，所以我产生了尝试的兴趣。然后我写了一个小编译器，可以塞进 12K 的 ROM 里，它能编译 Pascal 的一个子集。你可以拔掉微软的 ROM BASIC，插上我们的 ROM。启动机器时，你就在这个小环境里，可以输入 Pascal 程序并运行。这就是 Turbo Pascal 的早期前身。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Yes. Exactly. And it was usually these kits that you bought that you had to solder together yourself and then of course they didn't work and then you have to figure out why they didn't work. So you learned a lot about the hardware too. And I bought a British Z80-based kit computer called a NASCOM and started learning assembly programming on that one. And then I also met with some college buddies and we ended up founding a company and we had the first computer store in Copenhagen where you could walk in and buy a computer, one of these kit computers and later we sold Apple IIs and VIC-20s and Commodore 64s and blah blah blah, you know, all of those different ones, right? TRS-80s. So I did a lot of programming on those and found that programming was really the thing that I enjoyed. And of course they all came with Microsoft's ROM BASIC and which was slow but it allowed you to write programs. Um but I always like missed having a real programming language uh something like Algol that I had been taught right and then my my buddy the guy that I founded the company with he was like well there's this new thing called Pascal you ought to check it out and it's it's even supposed to be simpler than Algol which was which was actually true of every language we had created. they got increasingly simpler as time went on. And Pascal was not that hard to implement. And so I got interested in trying to do that. Um, and then wrote a little compiler that fit into a 12K ROM um, that would compile a subset of Pascal and you could then yank out the Microsoft ROM BASIC and stick in our ROM instead. And then when you booted your machine, you were in this little environment where you could type in Pascal programs and run them. And that was sort of the early precursor of of Turbo Pascal, if you will.
</details>

### Turbo Pascal 与 Borland 时代

**主持人**: 许多年后，你加入了 **Borland**，我想是在 1989 年。在那里你创造了 Turbo Pascal 编程语言，还有 IDE，对吧？

<details>
<summary>Original English</summary>
**Host**: Many years later, you joined Borland and I think it was in 1989. And there you created Turbo Pascal, the programming language, but also the IDE, right?
</details>

**Anders Hejlsberg**: 唔，那个故事还有一点曲折。在我们当时的那家公司里，我最终为 8 位的 CP/M-80 写了一个完整的 Pascal 实现。然后我们与 Borland 成立了合资企业，Borland 最初也是在丹麦成立的一家丹麦公司。我们签订了一份版税合同，由他们销售我们的编译器并支付版税。这就是我如何参与到 Borland 中的。我们在 83 年发布了第一款产品，即第一个版本的 Turbo Pascal。然后它火了起来，超出了我们所有人的预期。最终，那成了我全职做的事情。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, there there's a little more to that story. In that company that we had back in then, I ended up writing eventually a full implementation of Pascal for 8 bit CP/M-80. And then we ended up doing a joint venture with Borland, which was also a Danish company was originally founded in Denmark. And we made a royalty contract where they would sell our compiler on a royalty. And that's how I got involved in Borland. And we shipped that first product in 83, the first version of Turbo Pascal. Um and then that took off more than any of us had expected. And eventually that ended up being the thing that I did full-time.
</details>

**主持人**: 为什么叫 Turbo Pascal？我理解你在 Pascal 的基础上添加了一些东西。

<details>
<summary>Original English</summary>
**Host**: Why was it called Turbo Pascal? I understand you added things on top of Pascal that was there.
</details>

**Anders Hejlsberg**: 叫 Turbo Pascal 是因为在那个年代它很快。Turbo 就像……那时 Audi 有他们的 Quattro 和 Turbo 系列，Turbo 就意味着快，对吧？这个东西很快，而且交互性极强。所以就叫 Turbo Pascal。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, I mean it was called Turbo Pascal cuz it was fast back then. Turbo was like this was like when Audi had their quattros and their turbos and whatever, you know, turbo just meant fast, right? And this thing was fast and super interactive, right? And so Turbo Pascal it was.
</details>

**主持人**: 当 Turbo Pascal 变红时，是因为编译器，还是因为有一个专门为它设计的 **IDE**？

<details>
<summary>Original English</summary>
**Host**: When Turbo Pascal became big, was it big just because of the compiler or also there was an IDE, a dedicated IDE for Turbo Pascal, right?
</details>

**Anders Hejlsberg**: 是的，那是核心理念。甚至可以追溯到 Turbo Pascal 的前身，这种理念认为它不只是一个编译器，而是一种**体验**。你不仅要编译程序，还要编辑、运行、调试它们，还要有一个运行时库。这一切都必须有机地结合在一起。Turbo Pascal 的重点一直是构建整个循环，并试图让它像解释型的 BASIC 语言一样具有交互性，同时给你编译型语言的性能，以及 Pascal 优于 BASIC 的语义和语法。所以这是从第一天起就有的理念：专注于整个生命周期。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Yes, yes, that was always the idea and that that goes back even to the predecessor of Turbo Pascal, this idea that it's not just a compiler, it's an experience, right? I mean you don't just compile your programs you also edit them you also run them you also debug them you also have a runtime library. It all has to like fit together. Do you know what I mean? And so Turbo Pascal was always about building that whole cycle and try to make it as interactive as BASIC was as an interpreted language, right? But giving you the performance of a compiled language and the better, you know, semantics and syntax of Pascal versus BASIC. And so that was sort of the the idea from from day one, you know, focus on the whole cycle.
</details>

**主持人**: 所以当你构建编译器时，你已经在考虑 IDE 可以如何发挥作用，或者提供哪些对编辑和调试有帮助的功能。

<details>
<summary>Original English</summary>
**Host**: And so when you were building the compiler, you were already thinking of ways that the IDE, for example, could make sense or could have helpful features for maybe that editing or debugging for example.
</details>

**Anders Hejlsberg**: 噢，绝对是这样（笑）。最初版本的 Turbo Pascal 没有调试器。你只能使用 `write` 语句，看看发生了什么。但通常如果你遇到错误导致崩溃，报出运行时错误，我们会打印出运行时错误的地址，也就是当时的程序计数器。

我们在编译器中有一种模式，我们可以说“编译，但停在这个地址”。编译器非常简单，它只生成对象代码，一旦碰到那个地址，它就会说：“好的，我现在语法上正在看的这个地方，肯定就是错误发生的位置。” 这就是你如何定位到发生错误的行。我们没有行映射（line maps）或调试器之类的东西，我们只有编译器，让它停在对象输出的某个特定地址，然后在源代码中显示出位置是非常容易的。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Oh, absolutely. [laughter] You know, the first versions of Turbo Pascal didn't have a debugger. You would just use write statements and then you just see what happened, right? But often if you had some error and it blew up, you know, with a runtime error, we would print out the address of the runtime error, which is where the program counter was at that point. And then we had a mode in the compiler where we would say compile but stop at this address. And so the compiler was real simple. it would just produce object code and then once it hit that address it would just say well whatever I'm syntactically looking at right now that must have been around where the error was. So that was like how you could go to the line where the error had occurred. Do you know what I mean? It's it's not like we had like line maps or debuggers or any of that stuff. We just had the compiler and it was just easy to make it stop at a certain address, you know, in the object output and then show you where it was in the source code.
</details>

**主持人**: 你认为为什么 Turbo Pascal 如此受欢迎？我记得那是我第一次编程体验。它被用于学校，也用于学校之外的生产软件。你自己也说过，它像野火一样蔓延。

<details>
<summary>Original English</summary>
**Host**: Why do you think Turbo Pascal was so popular? I remember back again, this was my first programming experience. It was at schools. It was outside of schools for production software. And you said yourself that it spread like wildfire.
</details>

**Anders Hejlsberg**: 它就是比所有竞争对手都好。更快、更小、交互性更强。而且更便宜。它比竞争对手好十倍，而价格只有十分之一。当时的编译器通常要 500 美元，而且仅仅是编译器，你还得自己找编辑器之类的。那是一个漫长且繁琐的过程，得插入不同的磁盘来运行第一遍、第二遍编译。而这个东西让这一切都消失了。你只要 49.95 美元就能得到它。

为了这 49.95 美元，光是随之而来的手册都值回票价了。所以几乎没有盗版，因为它太便宜了。虽然说到盗版，我们总有一个关于“俄罗斯站点授权”的笑话——我们卖给俄罗斯一份拷贝（笑），然后它就在那里被复制得到处都是。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: It was just better than all the competition. It was faster. It was smaller. Um it was more interactive. And it was also cheaper. So it was like 10 times better at a tenth of the price of the competition. Right? Compilers back then used to cost $500 and they were just compilers. And then you have to have an editor and blah blah blah. And it was like this whole long-winded cycle of inserting different discs with compiler pass one and two and what have you. And here was this thing that just like made it all go away. And you could get it for $49.95. And for $49.95, I mean, heck, that was worth it just to get the manuals that came with it, right? I mean, so so there was very little piracy because it was so cheap. Although speaking of piracy, we always had the joke about the Russian site license, how we sold one copy to Russia [laughter] and then that got copied everywhere.
</details>

### Delphi：图形界面的革命

**主持人**: 在 Turbo Pascal 之后，你构建了 **Delphi**，在很多方面它是一个更大的体系。这是针对 Windows 开发的集成环境。你是如何让 Turbo Pascal 的理念演变成 Delphi 的？

<details>
<summary>Original English</summary>
**Host**: But after Turbo Pascal, you built Delphi, which was an even bigger setup in many ways. This was now a integrated environment for Windows development. How did you evolve ideas from Turbo Pascal and Delphi?
</details>

**Anders Hejlsberg**: 在 Turbo Pascal 和 Delphi 之间发生的大事是**图形用户界面 (GUI)** 的出现。我们从在文本模式下运行 DOS 切换到了在 GUI 中运行 Windows，这意味着你必须创建一种新型的应用程序。

同时，在竞争方面，微软创造了 **Visual Basic**，这是一款非常令人印象深刻的产品，但它仍有一些我们知道如何与之竞争的缺陷。比如解释型与编译型的差异，以及可扩展性的问题——我们的语言有类和面向对象等等。起初我们打算构建一个 Visual Basic 的竞争对手，但后来我们也意识到，仅仅这个角度是不够的。

当时正在发生的另一个现象被称为**客户端/服务器**应用程序。市面上有一大堆用于数据库连接的客户端/服务器应用的 4GL 开发工具。所以我们着手构建一个工具，它像 Visual Basic 一样具有交互性和快速应用开发 (RAD) 能力，但背后有一个编译器，同时也针对客户端/服务器的企业应用。这就是 Delphi 的意义所在。它运行得非常好。直到今天，这款产品仍被许多程序员活跃使用。Skype 被微软收购后我曾在那里工作，当时我非常惊讶。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: The big thing that happened there between Turbo Pascal and Delphi was the advent of the graphical user interface, right? We switched from running DOS in text mode to running Windows in a GUI and that meant a new kind of application that you had to create. And at the same time, competitively, Microsoft had created Visual Basic, which was a very impressive product, but still had some of the very same flaws that we knew how to compete with, right? In terms of interpreted versus compiled and extensible versus not extensible versus ours that had classes and object orientation and blah blah blah. First we set out to build a Visual Basic competitor but then we also realized that well that's not really enough of an angle. And then there was this other phenomenon that was happening at the time which was called client server applications. Um and there were a whole bunch of 4GL application development tools for database connected client server apps. And so we set out to build a tool that was like as interactive and rapid application development as Visual Basic, but with a compiler behind it, targeted also at client server enterprise apps. That was what Delphi sort of was about, right? It worked out really well. I mean that product to this day is still being used actively by a whole number of programmers. I was very surprised when I worked at Skype right after Microsoft bought it.
</details>

**主持人**: 我听说 Skype 应用程序是用 Delphi 构建的，你应该知道这个。

<details>
<summary>Original English</summary>
**Host**: I heard the Skype application, you probably know this, it was built in Delphi.
</details>

**Anders Hejlsberg**: 在 2012 年或 2013 年，曾有一个重写它并迁移到其他平台的计划。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: In 2012 or 2013, there was a plan to rewrite it and move it onto something else.
</details>

**主持人**: 那个重写工作进行到一年半时停止了。所以我猜直到那个 Skype 应用程序退役（大概是一年前），它一直都是用 Delphi。

<details>
<summary>Original English</summary>
**Host**: That rewrite midway a year in stopped. So, I'm guessing that until the end of that Skype application, which was decommissioned maybe a year ago.
</details>

**Anders Hejlsberg**: 挺神奇的，不是吗？Delphi 在某些方面过去是、现在也是一种构建 Windows 桌面应用的绝佳方式。他们有很棒的 **VCL**（可视化组件库），允许你继承组件并将其安装在调色板上，让你的表单设计器支持拖放操作，使用你自己构建的组件。那非常酷。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: It's amazing, isn't it? I mean Delphi was and is in some ways a wonderful way of building Windows desktop apps. I mean they had a great VCL, the visual class library that allowed you to inherit components and install them on the pallet and make drag and drop work for your forms designers with components that you had built and whatever. It was pretty cool.
</details>

### 加入微软与 Java 的冲击

**主持人**: 我们已经听到了与 Visual Basic 的微软渊源。你于 1996 年加入微软，从事 **J++** 的工作，后来是 C#。你能带我们回到那个时刻吗？当时的编程环境是怎样的？

<details>
<summary>Original English</summary>
**Host**: Yeah. And we already heard the Microsoft link with Visual Basic. So you joined Microsoft in 1996. you worked on J++ and then later C#. But can you take us back to that moment in time? What was the kind of programming environment like?
</details>

**Anders Hejlsberg**: 唔，尤其是在我加入微软的那个时候，即 90 年代中期，**Java** 诞生了。首先浏览器出现了，然后是 **JavaScript**，但当时没人真正关注 JavaScript，因为那只是浏览器里的一个小玩意儿，运行慢，大家觉得“没人会用那个”。

但接着出现了 Java，它可以让你创建 **Applet**。噢天哪，Applet，太棒了！到处运行！是的，据说它可以在浏览器和任何地方运行。这种语言简单却具有面向对象特性，有字节码，而且平台无关。每个人都像无头苍蝇一样乱跑，觉得这是编程语言的终结。Java 将夷平宇宙，我们以后都只写 Java 和 Java Applet，仅此而已（笑）。

我来微软名义上是担任微软 Java 开发工具的架构师，负责 **Visual J++**。我加入时他们有 1.1 版本，基本上就是拿 Visual C++ 拔掉 C++ 编译器，塞进一个 Java 编译器就完事了。但它没有交互性，不是快速应用开发。而我带来了一整套关于如何构建交互式开发工具的知识。这就是我们在 Visual J++ 6.0 中着手做的事情。当然，我们也知道人们会在 Windows 上运行，他们会希望能够构建 Windows 桌面应用。所以，我们构建了一个类库来实现这一点。那是 **WFC**，我觉得是这么叫的，在某些方面它是 **WinForms** 的前身。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, the environment particularly around the time where I joined Microsoft the mid '90s, Java had happened. Well, the browser had happened first of all and JavaScript but JavaScript no one really paid attention to JavaScript because that was just this little whatever thingy that that was in the browser, you know, and it was slow and it was like ah no one uses that. Uh but then there was this Java thing that allowed you create applets. Oh my god, applet. Fantastic. And run everywhere. Yep. Yep. Ran in the browser and everywhere supposedly. And and and this language that was like simple yet had object orientation and bite codes and like like was platform independent. And I mean it was like everyone was running around with like with their heads cut off thinking this was the end of languages. uh you know, Java is going to flatten the the universe and then then we're all just going to be writing Java and Java applets and that that's the that's it, [laughter] you know, and and and I actually came to Microsoft ostensibly to to be the the architect of Microsoft's Java development tools and worked on Visual J++ 6.0 was the version that they had. Visual J++ 1.1 at the time I joined which was basically take Visual C++ yank out the C++ compilers dig in a Java compiler and call it good. Uh but it wasn't interactive. It wasn't rapid application development and whatever. And I came sort of with a whole host of knowledge of how to build interactive development tools. And that's what we set out to do with Visual J++ 6.0. Uh, and we also, of course, knew that, hey, you know, I mean, people are going to be running on Windows and they're going to want to be able to build Windows desktop apps. And so, we built a class library that allowed you to do that. This was WFC, I think it was called, but it was the precursor of Winforms in some ways.
</details>

**主持人**: J++ 的开发进行得如何？最终是如何演变成“好吧，让我们做点别的，做点完全不同的东西”这个想法的？

<details>
<summary>Original English</summary>
**Host**: how did the development of J++ go and and eventually how did it lead to the idea of like, okay, let's do something else, something completely different.
</details>

**Anders Hejlsberg**: 唔，J++ 的开发一直进行得很好，直到那场巨大的 **Sun 诉微软案**挡了路。现在我们谈论的是商业之类的东西，与技术无关，但它实际上意味着 Visual J++ 永远不会成为公司敢于押注的产品，因为他们非常清楚，你不会用一种被圣何塞法官颁布禁令的语言来编写你的应用。

在那时我们也意识到，将你的开发平台押注在从竞争对手那里获得许可的技术上，也许不是一个好的策略。与此同时，当时的开发状况是：微软的主要开发产品分为两个阵营。一个是深受大家喜爱的 Visual Basic 快速应用开发，因为它构建应用非常容易，但在性能上有问题，可扩展性也不好——要写新组件，你必须用 C++ 写。另一个是具有强大表达能力的 C++ 搭配 **MFC**。但人们真正想要的是两者兼得。他们想要一种能将这两者结合起来的东西。他们还想要一些现代化的特性，比如 Java 拥有的垃圾回收，以及异常处理，以及一种更加面向对象和组件化的应用构建方式。所有这些都是促成 **.NET** 和 **C#** 诞生的起源。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, development of of J++ went went great until the big Sun Microsoft lawsuit got in the way. Um, and and there was, you know, and that is like I mean, now we're talking like business and whatever. It had nothing to do with with technical, but it effectively meant that Visual J++ was never going to be a product that companies would make a bet on because they full well knew that, you know, you're not going to write your app in a in a language that has been enjoined by a judge in San Jose, you know, or or whatever. And so we kind of realized at that point too that maybe it's not a great strategy to to place your your development platform bet on technology that's licensed from a competitor and and that in turn along with the sort of dev situation at the time I mean Microsoft's main development products at the time were in two camps. There was visual basic rapid application development loved by everybody because it was so easy to build apps right but performance-wise had problems extensibility wise wasn't so great to write new components you had to write them in C++ and whatever and and then we had C++ with MFC and power and expressiveness but really what people wanted was both they wanted something that rolled both of those up right and then they also wanted like modern things like garbage collection that say Java had for example right and exception handling and a more object-oriented component-oriented way of building your apps and all of that was part of the genesis that led to .NET and to the C# language.
</details>

### C# 的设计与团队协作

**主持人**: 在微软内部，是 .NET 先出现还是 C# 先出现？

<details>
<summary>Original English</summary>
**Host**: So which one was first, .NET or C# inside of Microsoft?
</details>

**Anders Hejlsberg**: 我会说它们是同步的。因为我们知道我们想构建一个**语言无关**的运行时，因为我们知道我们想在上面运行 Visual Basic，我们想要一种运行 C++ 的方式，我们希望其他语言也能在这个运行时上承载自己。但我们也知道，我们需要构建一种既能吸引 Visual Basic 用户又能吸引 C++ 用户的语言，给你中间那个完美的平衡点。坦白说，还要能与 Java 竞争。所以这就是为什么我们开始构建 C#。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, they were simultaneous, I would say, because we knew we wanted to build a runtime that was language independent because we knew that we wanted to run Visual Basic on it and we wanted a way of running C++ on it and we wanted the ability for other languages to to host themselves on this runtime. But we also knew that we needed to build a language that would appeal to both Visual Basic and C++ users and give you sort of that golden thing in the middle, right? And to be frank, something that could compete with Java, right? And so so that's why we we started out building C#.
</details>

**主持人**: 当你开始构建 C# 时，你的设计目标是什么？你提到了垃圾回收和异常处理，但你是如何确定“这种语言到底应该是什么样”的？

<details>
<summary>Original English</summary>
**Host**: And then when you started out building C#, what were your design goals? You mentioned a few things with garbage collection or exception handling, but how did you come up with like, okay, what what will this language be?
</details>

**Anders Hejlsberg**: 正如我所说，总体目标是结合 C++ 的强大生产力与 Visual Basic 的易用性。但这也意味着我们知道我们想构建一种**面向对象**的语言。我们想要托管代码或字节码，以便针对不同的运行时环境。我们想要垃圾回收和异常处理，但也想要诸如**统一对象系统**之类的东西。在 C# 中，任何东西都可以分配给一个对象；如果是值类型，我们就对其进行**装箱 (boxing)**，但它是一个自我描述的对象。

通过**反射 (reflection)**，你可以询问一个对象：“你是什么？” 你可以在运行时获取关于它的所有事实，并以许多其他环境不存在的方式动态操作它。我们知道我们想往那个方向发展。我们想要一种语言，让**属性 (properties)**、方法和事件成为一等公民，因为这就是组件的构建方式，而不仅仅是函数、过程甚至单纯的对象。此外，我们还想创造一种**标准化**的语言。我们想把这种语言交给标准化委员会，试图让竞争环境变得公平。所有这些都融入到了 C# 中。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, like I said, I mean, the overarching thing was this power and productivity of C++ with the ease of use of visual basic in a sense, right? But what it also meant was we we knew we wanted to build an object-oriented language. We wanted manage code or bite code so we could target different runtime environments. We wanted garbage collection and exception handling but also things like a unified object system where and that's true in C# like anything can be assigned to an object and if it's a value type we box it but and it's a self-describing object. So reflection, you can ask an object, what are you? And you can get all of the facts about it at runtime and you can dynamically manipulate it in ways that are just don't exist in a lot of other environments. And we we knew we wanted to go there with that. We wanted a language that made this new model of properties, methods, and events first class because that was how components were built as opposed to just sort of functions and procedures and even objects, right? And then we we actually also wanted to to create a language that was standardized. We wanted to give this language to a standardization committee and try to, you know, level the playing field there. And all of those things were sort of like what was rolled up in C#.
</details>

**主持人**: 你确实做到了。C# 是我第一门专业语言，我用了大约五年。我见证了它的工具能力和语言特性。直到今天，我仍然认为旧版本的 C# 在某些方面领先于现在的某些语言。看到它发布时如此丰富，以及随之而来的开发者喜爱，是非常有趣的。

作为软件工程师，大家习惯于构建 SaaS 应用、后端服务，但不熟悉构建一门语言需要什么，尤其是像在微软内部这样具有巨大野心的项目——你知道理想情况下会有数百万开发者使用它。你是如何制定路线图的？需要多大的团队来完成这项工作？

<details>
<summary>Original English</summary>
**Host**: You definitely did it. C# was my first professional language where I worked with it for about five years and I've seen both the tooling the capabilities of language and I still think to this date in many ways that old version of C# was ahead of some languages today in some ways. So it's very interesting to see how rich that language was when it came out and of course the developer love that followed. But can you take us back of what did it take to build a language like this especially something with such large ambitions inside Microsoft you knew millions developers ideally would be using it how did you get to this how did you come up with the road map how big or large or small team needs to work on this
</details>

**Anders Hejlsberg**: 我认为早期我们就决定了，要由一个团队来设计这门语言，而不仅是一个人。我是负责这个设计小组的人，但我们集合了一个大约六七个人的小组。我们每周在房间里碰头三次，每次两小时，就这样开始了设计。字面意义上的从头开始。

这些人以前都构建过或研究过编程语言，见过所有应该做的事和不该做的事。老实说，对于几乎每种语言，语言设计 90% 是相同的，10% 是创新的。你构建的每种语言仍需要一个编译器。编译器的构建方式大体相同。当然，随着时间推移，人们的要求越来越高。你必须有 IDE，有框架，等等。有很多经验可以借鉴，有很多工作其实并非全新。但在每一轮设计中，你都会尝试解决之前暴露出的问题。

这个语言设计小组在一起合作了很多年。带着一个新想法来上班，然后立刻有五六个人可以坐下来和你进行深入讨论，而不需要先花一小时进行同步（level setting），这种感觉非常好。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: I think early on we decided that we want to have a team of people design this language not just one I was sort of the guy who ran the group of designers but we put together a group of six people or so six seven people and we got in a room three times a week for two hours and just started the design you know like literally let's start from the top what is that we all knew what a I mean these were all people who had built or worked on programming languages before, right? And and had seen all of the things you're supposed to do and all the things you're not supposed to do. And quite honestly, language design is 90% the same and 10% new for pretty much every language. Every language you build still has to have a compiler. Compiler is still built pretty much the same way. And of course, as time marched on, people demand more and more. you have to have IDEs, you have to have frameworks, you have to have blah blah blah, you know, and it's all there there's a lot of experience you want to pull in and there's a lot of work that you're doing that isn't really per se new. Um, but every time around you try to fix the problems that you've been exposed to. This language design group worked together for years on end. And it was lovely to come in to work with a new idea and then immediately have five or six people that you could sit down and have a deep discussion with without first having to spend an hour level setting. Do you know what I mean?
</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>
**Host**: Yeah.
</details>

**Anders Hejlsberg**: 这行之有效，因为我们可以直接切入正题，进行两小时的技术讨论。每个人都明白：如果有人提出一个新想法，现在的任务就是设法击败（shoot down）它。这个想法有什么问题？如果它能经受住那种考验，那么它可能就是一个不错的主意。我们就是这样进行设计的。

我边参加设计会议边编写语言规范。同时，我们有一个小组在同步实现编译器，是用 C++ 实现的，准确说是 C++ 减法（C++ minus），因为在编译器实现中我们并没用到所有的 C++ 特性。直到后来的 **Roslyn** 项目，我们才实现了 C# 编译器的**自托管 (self-hosted)**。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: And that worked really really well because because we could just jump right in, you know, and and have two hours of technical discussion and everyone was cognizant of, okay, if someone comes up with a new idea, now it's our job to try to shoot it down. Well, what's wrong with this idea? Do you know what I mean? And if it could stand the the test of that, then it was probably a decent idea. And so so that was kind of how we ran the design. And then I wrote the specification of the language in parallel with our design meetings. And then we had a group that was in parallel implementing the compiler in actually implementing it in C++ or rather C++ minus because we didn't use all of the C++ features, you know, in that compiler implementation. But it wasn't until the Roslin project that we self-hosted the C# compiler.
</details>

**主持人**: Roslyn 意味着编译器是用 C# 写的，对吗？

<details>
<summary>Original English</summary>
**Host**: and a Roslyn meaning that the compiler is in C#, right?
</details>

**Anders Hejlsberg**: 没错。那是后来构建编译器自身的项目。此外，早期你要记住，IDE 并没有那么花哨。我们有语法着色，语句补全（IntelliSense）刚开始出现在一些 IDE 中，但还不是常态。

所以我们构建了一个典型的编译器，但也构建了一个“微型语言服务”之类的东西，它走了一些捷径，可以实现一些基本的补全和着色。但在某种意义上，我们有两套实现必须并行演进。随着时间的推移，这变成了一个巨大的负担。当我们添加泛型、其他特性、**LINQ** 之类的东西时，天哪，我们得在真实的编译器和语言服务中把这些特性实现两次。这最终引向了 Roslyn 项目，我们构建了一个单一的编译器，它既是命令行编译器，又是 IDE 内部的交互式服务。TypeScript 也是以同样的方式构建的，这样做有很多学校里学不到的经验。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: exactly yes that was the a project that came later to to build the compiler in itself and also early on you know this is you got to remember back then IDE's were not really all that fancy you know I mean we have syntax colorization statement completion was kind of like well some IDEs were starting to dabble in it but it wasn't really a norm so we built like in a sense a classic compiler, but then we also built this like mini language servicey thing that sort of cut some corners and whatever, but could do some rudimentary statement completion and syntax coloring. But in a sense, we had two implementations that we had to evolve in parallel. And over time, that became quite a drag, right? because as we added generics and I added other features and LINQ and whatever and it was like oh my god now now this is like we got to go implement all of these features twice in the real compiler and in the language service right and so that ultimately led us to this project called Roslin where we built a single compiler that really is both it's a compiler that can both function as a command line compiler and as an interactive service inside the IDE Typescript is built that same way also and there's a lot of learnings from from doing it that way that are still not being taught in school.
</details>

---

### 插播：赞助商信息

**主持人**: 学校里有很多有用的东西不教。我要提到的非常有用的工具之一是我们的季赞助商 **Turbopuffer**。

Turbopuffer 是一个极其可扩展、快速且便宜的向量和全文搜索引擎。我第一次听说他们是因为 Cursor 的一位联合创始人。他们当时的向量数据库无法跟上不断增加的代码库数量。Cursor 做了一件看似冒险的事：押注于当时知名度较低的新产品 Turbopuffer。但这得到了回报。Cursor 迁移了语义搜索工作负载，Turbopuffer 确实处理了 Cursor 巨大的负载。这得益于巧妙的工程设计。Turbopuffer 构建在对象存储之上，并在 NVMe SSD 上进行智能缓存。Cursor 对 Turbopuffer 赞不绝口。切换后，他们的语义搜索成本降低了 95%。

提到有用的工具，还得提到 **WorkOS**。今天与 Anders 节目的一个主题是他花了数十年——而不是数月或数季度——思考开发者生产力。WorkOS 对企业级基础设施有着同样的长远目光。SSO、SCIM、RBAC、审核日志，他们花了数年时间完善这些，让你不必花数周去实现。这就是为什么成长最快的 AI 公司信任 WorkOS。

---

### Async/Await：改变异步编程范式

**主持人**: 当你在构建一种语言作为产品时，你如何获取反馈？

<details>
<summary>Original English</summary>
**Host**: And when you're building a a language as as the your product was, I guess the the language itself, how did you get feedback? Of course, you had the the you already said the group criticized it. Did you have an internal beta testers because again for like a backend service, you would typically have dog fooding, alpha testing, beta testing, and then you go public at some point, but this is not your your average software as a service for sure.
</details>

**Anders Hejlsberg**: 幸运的是，我们有内部客户。**.NET Framework** 团队很快就开始用 C# 实现了。之前他们使用过一个修改版的 C++，针对字节码，但这很奇怪，所以他们切换到了 C#。我们还有其他内部团队在使用。通过这种方式我们得到了很多反馈。而且周期并不长。我们 98 年底开始，到 2000 年的 PDC 大会，我们就派发了 Beta 版拷贝，获得了海量的用户。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Yeah. I I mean luckily we had internal clients. The .NET framework very quickly started implementing in C#. They had sort of used a hacked up version of C++ to to implement which was kind of odd because I mean it was like targeting byte codes but not really and so they switched to to uh to C# and that helped a lot. Um and then we had other internal teams using it and so we we got a bunch of feedback that way and then we had you know the cycle was not that long right I mean I think we started in late 98 and by the PDC of 2000 uh we had we signed up I mean we basically gave away beta copies right and and got tons of users onto it.
</details>

**主持人**: C# 引入了许多全新的语言特性。**LINQ** 肯定是其中之一。但另一个极具影响力、被其他语言广泛借鉴的特性是 **async/await** 机制。回顾过去，你认为这个设计的正确之处在哪里？为什么它在 JavaScript、Python、Rust 等语言中如此具有可复制性？

<details>
<summary>Original English</summary>
**Host**: Now C# introduced a lot of new features that were net new I think to to programming languages. LINQ is certainly one of them. But one thing that might have been maybe one of the most influential parts that other languages adopted as inspiration was the async await setup. Looking back, what do you think you got right with this design and and why did it become so copyable across languages like JavaScript, Python, Rust and others?
</details>

**Anders Hejlsberg**: 许多语言是围绕**协作式多任务**构建的，即它们有一个事件循环（event loop）在分发事件。你处理事件，然后放回事件处理循环，这一切都在单线程中协作运行。

问题是，如果你想做一些耗时的操作，如何在一段耗时工作的中间停止并放回事件循环？当结果准备好时，我再回来继续执行。在这样的翻转架构（inverted architecture）中，你必须构建一个**状态机**。而状态机实现起来出了名的难，因为你必须将所有的状态从栈（stack）移到对象中。你得记住执行到哪了，然后你有一个包裹整个逻辑的大 `case` 语句——这简直是噩梦。

但是，将串行执行的代码转换为状态机的这种“延续处理风格 (continuation processing style)”转换，实际上是可以由机器完成的。如果你引入一种语法，允许指明要在哪里出让（yield），编译器就可以帮你写状态机。这就是 `await`。`await` 基本上是在说：“我想在这里出让。我出让这个 Promise，当 Promise 完成时，我希望你回到这里继续执行。”

然后编译器在它周围写一个状态机，实际上把它变成了一个巨大的 `switch` 语句，并将所有在 `await` 之后存活的状态移到堆分配（heap allocated）的对象中。编译器非常擅长做这些。这就是这种新编程风格的想法：使用 Promise，以及出让和回调的能力。JavaScript 以前也深受此苦，全是回调地狱。有了 async/await，你会产生一种错觉，觉得自己在写正常的顺序代码，而编译器为你完成了痛苦的转换，这非常有用。

当然，另一种选择是使用操作系统的线程。但线程的问题在于它们是**抢占式**的，系统可以在任何时刻中断你，这不一定是想要的。而且你的 UI 也必须变成多线程，带来各种问题。加上线程是重量级的。所以各有优缺点。async/await 引入了“函数着色（function coloring）”的问题，即你有异步函数和常规函数两种。红函数可以调用蓝函数，但蓝函数不能调用红函数。这意味着一旦你想要一个红函数，它上面的所有调用者都必须变成红色的。

这就是为什么像 **Go** 这样的环境有 Go Routine 和**绿线程**，它们是语言模拟的轻量级线程。它们避免了函数着色。但在像 JavaScript 或 C# 这样已经存在、且依赖 Windows 事件循环的环境中，async/await 是正确的解决方案。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, a lot of languages are are built around cooperative multitasking in the sense that they have an event loop that sits and dispatches events and then you know you handle the event and then you yield back to the event handler loop and it all runs in a single thread cooperatively. Right? The problem with that is if you then want to do some longrunning work, how do I stop in the middle of this piece of longrunning work and yield back to the event loop cooperatively, right? And then and then when my result is ready, then I can come back and continue executing here. Well, in order to do that in in an inverted architecture like that, you have to build a state machine. And state machines are notoriously hard for for people to implement because you got to move all of your state off of the stack into objects. You got to remember where and then you have this big case statement that envelopes your entire logic and it's it's like it's a nightmare to to figure out, right? But the transformation from serially executing code into a state machine that this continuation processing style translation is actually one that you can do in a machine-based fashion. You can have the compiler write the state machine if you introduce syntax that allows you to indicate where you want to yield. And that's what await is. Await is basically I'm saying I want to yield here and then when the promise completes I want you to come back here and continue executing and then the compiler writes a state machine around it and it actually turns it into this big switch statement you know and moves all of the state that survives across the await into something that's heap allocated so it can be brought back and doing all of that work is something that compilers are great at. And so that was sort of the idea that we have this new style of programming where where we're using promises or the equivalent of promises and the ability to yield and then we have callbacks and but trying to write your program in that style that's that's also you know what what JavaScript suffer from a lot right it's like all this callback style stuff and with async await you get sort of the illusion that you're just writing normal sequential code and then the compiler does the the painful transformation for you and that turns out to be really useful. Um, now arguably an alternative way of doing this is to use threads in the OS. But the problem with threads is that they come with preemptiveness and the OS has the ability to preempt you at any point in time and that's not necessarily what you want and and and your UI now you have to be multi-threaded in your UI and all sorts of other problems come along with it. Plus threads are heavyweight and typically not well suited for lightweight tasks like like you could do with async functions. So there are pros and cons um you know like async await introduces this notion of function coloring which is unfortunate where you have two kinds of functions async functions and regular functions and oh the red functions can call the blue functions but the blue functions can't call the red functions and and so that means once you want you know a red function it now all everything above it has to be red and then then so if you want from a sync function to call something async well then you got to turn this function into an async function and its caller has to be etc etc Right. So that's unfortunate and that's why some environments like Go for example has has Go routines and green threads which are really language emulated lightweight threads that kind of do what I'm talking about but but at a much lower cost but you avoid the function coloring. So there is a bunch of different things but but you know but for an environment that already exists like JavaScript or like C# and and the Windows event loop and and whatever this this was the right solution.
</details>

### TypeScript：解决 JavaScript 的规模化难题

**主持人**: 谈到 JavaScript。随着 C# 在初创公司和企业中变得非常流行，它在游戏开发中也呈爆炸式增长。但 JavaScript 也开始变得更受欢迎。你能带我们回顾一下，JavaScript 是如何从 90 年代中期没人当真的脚本语言，变成现在的爆发式流行的？

<details>
<summary>Original English</summary>
**Host**: Speaking of JavaScript as as C# was becoming really popular across startups, enterprises and so on. It was exploding in popular games as well. To this date it's very popular with with games development but JavaScript was starting to become more popular. Can you can you take us back to your observations on on how how JavaScript went from, you know, like the the mid90s to this script language no one really took seriously to just exploding in popularity.
</details>

**Anders Hejlsberg**: 我认为那是 2000 年代初期一系列事情的汇合。首先，JavaScript 的执行平台大幅成熟，比如谷歌在 **V8** 引擎上做的出色工作，突然让 JavaScript 变成了一门性能相当不错的语言。**HTML5** 获得了批准。我们到了一个可以在 JavaScript 中构建真正 UI 的阶段。然后是 iPhone 引发的设备革命，突然间我们有了各种不同的尺寸规格，不再只是桌面上的 Windows PC，而是各种多样的设备。但你瞧，它们都运行带有 JavaScript 的浏览器。真正的跨平台语言不是 Java，而是 JavaScript（笑）。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: I think it was sort of a confluence of a number of things that happened in the early 2000s, right? First of all, the the the JavaScript platform execution platform matured a lot like Google did their excellent work on V8 and all of a sudden make JavaScript a fairly performant programming language. HTML 5 got ratified and and and we were getting to a point now where you could actually build real UIs in JavaScript. And there was this device revolution that the iPhone set off and and and all of a sudden we have all of these different form factors. It's not just Windows PCs on the desktop anymore. It's all sorts of diverse devices. But lo and behold, they all run browsers with JavaScript in. Lo and behold, the real crossplatform language isn't Java. It's JavaScript. [laughter]
</details>

**主持人**: 谁能想到呢？

<details>
<summary>Original English</summary>
**Host**: Who would have thought?
</details>

**Anders Hejlsberg**: 没错。于是世界开始睁大眼睛审视它，并开始在 JavaScript 中构建越来越大的应用。我们不仅在外部看到了这一点，在微软内部也看到了。

触发事件之一是 **Outlook.com** 团队找到 C# 团队，问我们是否可以将一个叫 **Script#** 的东西产品化。我们问：“什么是 Script#？” 这是一个允许你将 C# 交叉编译成 JavaScript 的编译器。这样你就可以把 JavaScript 当作一种指令语言，在浏览器中运行 C# 应用。我说：“为什么有人想这么做？” 对方说：“因为这样你就能拥有一门成熟的语言和成熟的工具支持。你可以使用 Visual Studio，可以使用项目管理，可以做所有这些在 JavaScript 中做不到的美妙事情，因为 JavaScript 只是一种工具简陋的脚本语言。”

我们当时就想：哇，真的吗？那也许更好的方法是**修复 JavaScript**（笑）。如果你告诉人们去写另一种语言，你肯定无法在 JavaScript 生态系统中做到出类拔萃。虽然当时很多人都在尝试，比如 CoffeeScript 等各种针对 JavaScript 的转译语言。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Exactly. And so the world started opening its eyes to that and and started building larger and larger applications in JavaScript. And we saw that externally but also internally and one of the trigger events was when the outlook.com team came to the C# team and asked us whether we would pretty please productize this thing called script sharp. And we go well what is script sharp? It's this cross compiler that allows you to cross-compile C# into JavaScript such that you can basically treat JavaScript as an instruction language and and run your C# apps in a browser. And I'm like, well, why would anyone want to do that? Well, because then you can get a grownup programming language with grown-up tooling. You can use Visual Studio. You can you can have projects. you can do all of these wonderful things, you know, that you can't do with JavaScript because JavaScript is just this scripting language with with shitty tooling. And we were like, wow, really? Well, gosh. Well, perhaps a better approach would be to fix JavaScript. [laughter] I mean, surely you're not going to be best of breed in the JavaScript ecosystem by telling people to write in a different programming language. Although plenty of people were like remember coffecript and all of these other like languages that targeted JavaScript, right?
</details>

**主持人**: 是的，它们是生成 JavaScript 的编程语言，但它们本身不是 JavaScript。

<details>
<summary>Original English</summary>
**Host**: Yes. So they were a programming language, right? Which generated JavaScript, but it wasn't JavaScript itself. Yes.
</details>

**Anders Hejlsberg**: 是的，它们超级流行。但 JavaScript 实际上是一门相当不错的小语言，只是缺少一些东西。这里必须归功于 **Brendan Eich**（JavaScript 之父），他理解函数式编程，他让函数成为 JavaScript 中的一等公民，这太美妙了。但它没有**类型系统**。

我们根据经验知道，没有类型系统就无法构建好的工具。你可以构建尚可的工具，但它永远无法**规模化**。它永远无法扩展到大型团队，因为你无法在代码中描述你的意图。没有办法将这些东西形式化，没法分析，没法在 IDE 中利用它来提供语句补全、重构、转到定义、查找所有引用等等。这萌生了一个想法：我们可以创建 JavaScript 的一个超集，添加类型系统，然后把类型编译掉。这样我们就有了强大工具支持的基础，可以构建出色的开发体验。这就是我们着手做的事情。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Yes. They were super popular. I mean like so many different things did that. But JavaScript is actually a pretty decent little language. There are just some things missing. You got to give credit there to Brendan Eich. I mean he he understood functional programming and he got functions as first class objects right in JavaScript which is godsend and and beautiful but it doesn't have a type system and we knew from experience that you cannot build good tooling without a type system. You can build decent tooling but it's never going to scale. It's never going to scale to large teams because you can't describe your intents in into the code. There's no way of formalizing any of this stuff and there's no way of analyzing it and there's no way of using it in an IDE to give you statement completion and refactoring and go to definition and find all references and blah blah blah blah all of that stuff right that germinated the idea of hey it's we can we could create a supererset of JavaScript that adds a type system and then we could just compile it away but then we have now we have the the foundation for great tooling and then we could build a create tooling on top and actually create a wonderful development experience, right? That was sort of like what we set out to do.
</details>

### 开源之路：从 Codeplex 到 GitHub

**主持人**: 当你决定做这件事时，你不仅决定做，还出于某种原因决定以**开源**的方式去做。这让微软外部的人感到惊讶，因为在史蒂夫·鲍尔默治下的旧微软，被公认为是反开源的。

<details>
<summary>Original English</summary>
**Host**: When you set out to do this, you not only set out to do this, but you set out for some reason to do it as open source, which took everyone outside of Microsoft as a surprise because old Microsoft under Steve Balmer was notoriously perceived as anti-open source back then with Windows and and C# back in the day.
</details>

**Anders Hejlsberg**: 当然。微软当时正在慢慢意识到开源不会消失，开源是开发者想要去的地方。然而，有一种集体 DNA 会把你拉向另一个方向。我们正处于那场风暴的中心。我们非常清楚，如果是微软授权的私有语言，绝对没机会吸引 JavaScript 生态系统。绝对没戏。它必须开源，别无选择。但在微软内部启动这件事需要一些努力。

我们付出了一些代价。最终获得了开源许可，因为我们有两个 Technical Fellow——我和 **Steve Lucco**（TypeScript 的另一位联合发明人）坚持认为必须这样做。没人会争辩这一点。但你必须付点“税”，比如要待在微软自己的开源仓库 **Codeplex** 上，那是基本上没人去的地方。头两年我们就在那里，门可罗雀。直到 2014 年我们搬到 **GitHub**，采用率才真正开始腾飞。

老实说，这彻底改变了我们的工作流程。开源（Open Source）和**开放开发 (Open Development)** 是两回事。一开始我们技术上是开源的，但不是开放开发。我们会把源码丢进仓库，把 Issue 抓取出来放进内部的追踪系统。但一旦切换到 GitHub，整个流程都变成了开放开发。我热爱这种流程，我们已经在那儿待了十多年了，这太棒了。正是这一点让产品变得如此出色。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Of course, I'm talking about, you know, Microsoft was slowly waking up to the fact that open-source was not going to go away and open source was where developers wanted to be and they were voting with their feet. Yet, there's a collective DNA, you know, that has been trained to pull you in the other direction, right? And and and so that battle was we were right in the center of that and we we full well knew that there was absolutely zero chance that we would appeal to the JavaScript ecosystem with a proprietary programming language uh license from Microsoft. No, no one was going to come. It had to be open source. There was just no two ways about it, right? But getting that off the ground inside Microsoft, it took some uh some pulling. Um, and we paid some taxes. We we did eventually get the okay to do open source, because we had two technical fellows, myself and Steve Lucco, who was the the other co-inventor of of of TypeScript, insisting that that was what we had to do. And so, okay, there people weren't going to debate that, but but of course, you have to pay the tax and be on Microsoft's open source repository called Codeplex, where exactly no one was. Um and and so we were there for the first 2 years. Um and it kind of was crickets, you know, and it wasn't until 2014 when we moved on to GitHub that things really started to get moving um with with adoption. And also honestly, it it it totally changed our workflow. You know, there's open source and there's open development and and and we were technically open source in the beginning, but it was not open development. we would sort of lop the source code out in this repository and scrape the issues off of that and put it into our internal issue tracker and then you you know but once we switched to GitHub the entire workflow moved to open development also and that I love that workflow and that's we've been there now for over a decade uh and it's been fantastic uh and it's what made the product uh as good as it is
</details>

**主持人**: 十多年后的 2025 年 11 月，GitHub 的 **Octoverse** 报告显示，TypeScript 已成为 GitHub 上最受欢迎的语言。除了类型系统，你认为是什么让它如此受欢迎？是什么抓住了开发者的偏好？

<details>
<summary>Original English</summary>
**Host**: just over a decade later so the the language moved to GitHub in 2014. And in November 2025, the the GitHub Octoverse report revealed that TypeScript became the most popular language across GitHub. Outside of the type system, what do you think made Typescript this popular? And of course, we've had other languages, Python being the other very popular one. But what captures developers preferences this well?
</details>

**Anders Hejlsberg**: 它不是一夜之间发生的。如果你回头看，我们最开始排第 10，然后这些年慢慢爬升。当然，如果把 JavaScript 和 TypeScript 加在一起，我们早就是第一了。随着时间的推移，越来越多的人决定采用它。原因绝对是因为更好的工具支持。我们当时完全看准了这一点：添加一个**可擦除的类型系统**，并利用它来实现强大的工具支持，这才是真正实现程序员生产力提升的地方。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, I think, you know, it didn't just happen overnight, you know, and if you look back at at at that, you know, all of a sudden we we surfaced as number 10 and then we climbed slowly over the years up and and and sat next to JavaScript, right? And of course, if you added JavaScript and Typescript together, then we were already number one. It's just which syntax, were you using type annotations or not? And more and more people over time just decided to adopt that. I mean some it early on we're using JS Doc or or whatever you know and like these types in comments or or that we also supported but gradually I think people just realized hey this is this is the right way to do it and the reason they came I think is absolutely because of the the better tooling and I think we were totally right there that like adding an erasable type system and then using that to enable great tooling is really where the programmer productivity boost is realized.
</details>

**主持人**: 我想这里不能不提到 **VS Code**，它作为免费工具提供了出色的支持。

<details>
<summary>Original English</summary>
**Host**: And I guess this is where we cannot like not mention VS Code which shipped that great tooling also as a free to use for for most people or at least initially for for most people which also made a big difference.
</details>

**Anders Hejlsberg**: 绝对是。那是我们的兄弟项目，也是用 TypeScript 写的，他们是我们最早的一批采用者。直到今天我们仍紧密合作。这种相互作用也导致了 **LSP**（语言服务器协议）的诞生，现在几乎每个工具厂商都使用它在 IDE 中实现交互服务。

有趣的是，直到现在这个 TypeScript 到 Go 的移植版，我们才切换到 LSP。以前我们有自己的 LSP 前身，因为我们最初将 TypeScript 集成到 VS Code 时，LSP 还没诞生。这是一段非常共生且令人满足的经历：在开源环境下并行开发这两个项目。我认为这彻底改变了开发者生态系统对微软的看法。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Absolutely. Yeah, that's our our sister project which is written in Typescript and so they were one of our earliest adopters uh and that we work pretty closely with them um to this day. That whole interplay that in turn is also what led to the invention of uh of LSP, the language server protocol that now pretty much every tool vendor uses to enable interactive services in the IDE. Oddly, it isn't until this port to go now that we're switching to LSP. We had our own precursor of LSP because LSP didn't exist when we first integrated TypeScript into into Visual Studio Code. But there are a lot of learnings from from that. So it's it's been an incredibly symbiotic and and fulfilling uh experience to build these two projects in parallel in open source and I think it has totally changed people's view of Microsoft in in the developer ecosystem
</details>

### 编译器架构深潜

**主持人**: 对于我们这些不熟悉编译器底层的开发者，你能简要概述一下 TypeScript 编译器的流水线是怎样的？

<details>
<summary>Original English</summary>
**Host**: for us developers who again are not as familiar with uh compilers themselves. We of course like I I use TypeScript and I I'm aware that there's some compilation going. Could you give us a brief overview of what the types of compiler pipeline looks like in terms of parts and and what parts you specifically focus on more?
</details>

**Anders Hejlsberg**: 好的。在许多方面它是一个非常典型的编译器，但在许多方面又不是。几乎每个编译器都有：
1.  **词法分析器 (Lexer)** 或扫描器：将文本转换为 Token。
2.  **解析器 (Parser)**：获取 Token，检查其序列，并生成**抽象语法树 (AST)**。这实际上是源代码的地图，但被拆解成了语法原语，并检查语法是否正确。
3.  **绑定器 (Binder)**：这是我们额外的一个环节。一旦有了解析树，我们就把符号信息绑定到上面，找到变量的所有声明，构建符号表，并附加到函数上，以便以后查找名称。在绑定器中，我们还会构建**控制流图 (control flow graph)**。
4.  **类型检查器 (Type Checker)**：这是流水线中最大的部分。它负责语义检查，确保程序正确。它负责推断类型，检查类型关系是否正确，赋值是否匹配，以及你调用的东西是否真实存在。
5.  **发射器 (Emitter)**：一个可选阶段。通常在编译器中这部分很大，因为要从中间表示转为机器码或字节码。但在我们的案例中，我们只是“擦除类型”。

早期，发射器还负责“降级（downleveling）”，将浏览器尚不支持的新 ECMAScript 特性（比如类）重写为构造函数等旧形式。现在浏览器都是常青的（evergreen），这已经没那么重要了。所以现在的发射器主要就是擦除类型注解，喷出纯 JavaScript 代码，并生成声明文件（.d.ts）。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Sure. It's in many ways a fairly typical compiler and in many ways not. Pretty much every compiler has you know what's known as a lexer or a scanner that takes text and turns it into tokens. And then typically on top of that you have a parser that takes the tokens, checks their sequencing and then makes abstract syntax trees which is a you know a tree that you can navigate that effectively is a map of of the source code you know but broken into syntactic primitives and checked that you know like syntactically everything is is or grammatically that everything is correct. So those are the first two stages of the pipeline. Um then we have well we have a a one extra pass that we call the binder which is you know once we have the parse trees then we bind symbol information to them where we find all of the all of the declarations of variables and whatever and build symbol tables and attach them to their function such that we can then later look up names effectively. And we also build in the binder we build a control flow graph and I can talk about what what that helps us do. And then we have the type checker which is the largest part of our pipeline. And that's the the thing that checks semantically that your program is correct. It's the thing that figures out types and checks that the types relate correctly and that you're assigning the right thing to the right thing and then that you know that you're calling something that actually exists and and and so forth. And then we have an an optional stage at the end called our emitter. And normally the emitter infrastructure in a compiler is also quite big because that's where you go from intermediate representation to machine code or bite code. Now in our case we just erase types if you will. Well we kind of do two things in in our compiler actually. Early on it was very much about a erasing the types but b also downleveling your your code. So we would take newer ECMAScript features that weren't yet supported by the runtimes for example classes and then we would downlevel them to constructor functions and whatever and so we would rewrite the code and that was a very popular feature early on. Now pretty much every browser is evergreen and you know like Eggmascript features are are are caught up and and so so that's not as important anymore. So our emitter is effectively, you know, a thing that just erases type annotations and spits out the JavaScript code that can run unanotated and also can spit out declaration files which are summaries of of your modules and and so forth.
</details>

**主持人**: 这里最有意思的是，这个编译器是以一种高度交互的模式构建的。

<details>
<summary>Original English</summary>
**Host**: But those are sort of the stages. Now the thing that's interesting about the compiler though is that it's built in a manner that where it can function in a highly interactive mode which is what the ID uses. 
</details>

**Anders Hejlsberg**: 没错。命令行编译器跑一遍就完了，输出就是结果或错误。但在 IDE 中，编译器是一个**服务**。我们要处理一个在你打字时永远处于损坏状态（broken）的程序，但我们仍要尝试进行语义分析。当你按下“点”号时，我们需要知道后面能接什么。这意味着我们需要知道你点号之前那个东西的类型。

为了弄清楚这一点，我们可能需要解析这儿、看看那儿。所有这些都必须在 **200 毫秒**内发生，否则人们会觉得 IDE 慢。如果你有 50 万行代码呢？你不可能在 200 毫秒内编译完。所以，你必须是超强**延迟加载 (deferred)** 和交互式的，做最少量的工作。我们的编译器就是这样构建的：它是**惰性（lazy）**的、函数式的且可重用的。这与传统教科书教的编译器写法非常不同。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Normally you know command line compilers they just run through these stages and you know the output is just whatever gets emitted or some error messages right but in an IDE you know the compiler is a service and what we do in that service is we basically take a program that is perpetually broken because you're typing and yet we try to syntactically or semantically analyze it and because we need to know when you press dot here what could what could come next? Well, that means we need to know what is the type of the thing you dotted on. In order for to figure that out, we may have to resolve stuff. We may have to look at a over here and whatever. And all of that has to happen within 200 milliseconds or else people think the IDE is slow, right? Well, what if you have 500,000 lines of code? You can't compile all of those in 200 milliseconds. So, you got to be super super deferred and interactive. And so you got to do minimal amounts of work. And that's how our compiler is built is it it tries to frontload like for example like you have 500,000 lines of code. Well let's say in 500 files well we could build the AST for 499 of the files and just sit on them. We don't have to rebuild those because you're not editing in those files. We just have to update the AST of the current file you're in. So that goes 500 times faster right than than if we had to do all of it. And then we don't actually have to figure out all of the types in here either. We can just start where you're at and then just resolve just enough to answer the question that you're that you're needing an answer for right now. And so everything is lazy and deferred and functional and reusable inside the compiler. And it's a very different way of writing compilers than than what the textbooks will traditionally teach you.
</details>

### JavaScript 的局限与渐进类型

**主持人**: 我想这就是所谓的“交互式编译器”。这听起来是一个比传统编译器难得多的问题。

<details>
<summary>Original English</summary>
**Host**: Yeah. I guess I I guess this is now these are interactive compilers if you will, right? It sounds like it's it's it's more than a compiler or a lot more difficult problem to solve. The same engine is there but but you got to build it in a in a manner where it can be very interactive and that was not typically important for compilers, you know. 
</details>

**主持人**: TypeScript 是 JavaScript 的超集。如果 JavaScript 允许，或者你能影响其路线图，有哪些特性是你特别想添加的？

<details>
<summary>Original English</summary>
**Host**: And so Typescript is a supererset of JavaScript. What are some features you would try to add if only JavaScript would allow it or if you were able to influence JavaScript's road map? What what is something that you feel could make Typescript a lot better? But of course there's constraint there.
</details>

**Anders Hejlsberg**: 我们跟踪 ECMAScript 委员会，一旦新特性达到阶段三或四，我们就实现它。我们把定义类型系统看作我们的地盘。但我仍有一些希望能出现在语言本身的特性。我喜欢函数式编程，其中关键的一点是“一切皆表达式”，语句和表达式之间没有界限。

JavaScript 缺少的一个特性是：在表达式中给临时结果赋予符号名称并重用它们的能力。也就是函数式语言中常见的 `let ... in ...`。这很好，因为你可以一直待在表达式语境中，进行流式（fluent）编程；但突然间你需要给某个要重用的东西起个名字，现在你不得不跳出来声明一个变量。有一种叫“do expressions”的提案，可能会在未来实现，但耗时很久。

总的来说，JavaScript 是一门不错的小语言。我们非常擅长用类型检查器把它的问题挑出来。一旦有了能警告你“你正准备做件蠢事”的检查器，它就没那么糟了。让 TypeScript 与众不同的是它的**渐进类型 (gradual typing)**：你可以有类型，也可以没有。其他语言强制你输入一切，因为它们要据此生成机器码；而在 TypeScript 中，类型纯粹是为了开发体验和检查。

这很有趣，因为这意味着我们不需要证明 100% 的正确性。在具有递归类型的结构化类型系统中，有些情况是无法分析的。你越想关联两个类型，就钻得越深，直视递归的深渊。但我们可以说：“好吧，我们已经证明到第四层了，这已经足够好了。” 如果你是生成机器码，这会导致不确定的行为；但 JavaScript 有一个定义良好的运行时，如果我们检查了 99% 而不是 100%，嘿，那总比 JavaScript 的 0% 检查要好得多。这给了我们其他语言无法提供的特性，因为它们必须追求 100%。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: We track the Eggmascript committee and and and you know new language features that get developed in Eggmascript we we implement once they reach uh stage three or four in the standardization committee and and then we've sort of been on that train ever ever since the beginning. So there is a pipeline that supplies new language features in a standardized manner. We sort of see it as our purview to define the type system on top. Right? So that is if you will our our playground. Now I still have things that I wish I could have in the language itself. I mean I like functional programming. I like functional programming languages and and key to them is that that everything is an expression. there's really no distinction between statements and expressions. And so one of the the features that JavaScript lacks in my in in my estimate is is the ability to give symbolic names to temporary results in expressions and then reuse them. This is the let let blah equals whatever in some expression that functional programming languages, you know, like camel and whatever all have. And it's nice because you could just stay in an expression context and you can just dot things together and and or whatever and sort of do this more fluent style of programming, but then all of a sudden you need a name for something you want to reuse and now you got to pop out and declare variable or turn it into state. Anyway, you know, that's one thing that I would like to fix. There's there's something called do expressions that may or may not happen at some point, but it's taking a long time. So anyway, but I mean generally speaking, I think JavaScript is a is a nice little language. it just has some issues, you know, and then and I think we're very good at teasing them out with our type checker, right? And so, so once you have a checker that can warn you, hey, you're about to do something stupid here, then it's not so bad. The thing that makes it interesting, I think, and and unlike pretty much any other programming language is the gradual typing. This this notion that you can have types, but you don't have to have types. Other languages force you to type everything, right? Um because they in turn use that information to generate machine code uh you know based on what the type is you know different instructions for float versus int versus whatever where in JavaScript the types or in Typescript the types are there purely for the development experience and the checking. When the program runs they're all gone. Now, of course, there are still types, but they're all dynamically computed. But that's kind of interesting because that means in the language, we don't necessarily have to prove 100% correctness. And a lot of language features that we have, we can't 100% prove correctness. Like in a structural type system with recursive types, there are just cases that you can't analyze because the types are infinitely recurring. the more you try to relate two types, the deeper you go and you're just staring into the the recursive abyss. Do you know what I mean? But you can kind of go, well, well, we've proven it to four levels. That's probably good enough. We're just going to say it's good enough and then, you know, if everything else works out, we're going to go, sure, that you can't do if if you were to go generate machine code that then would have indeterminate behavior, right? But if JavaScript has a runtime where everything is well defined already. So if we're checking 99% instead of 100% well heck that's better than the 0% that JavaScript checked, right? And it gives you like language features that no other languages can provide because they can't get to 100%. [laughter]
</details>

### AI：从效率工具到未来的不确定性

**主持人**: 创新的约束。现在 AI 编码工具无处不在。在你开发语言的过程中，AI 是如何帮助你的？

<details>
<summary>Original English</summary>
**Host**: It's interesting how constraints lead to innovation or even limitations can lead to more innovation. Speaking of innovation, one one of the biggest innovations that is everywhere is the AI agents, AI coding tools that us software engineers, most software engineers are using increasingly using AI agents as well as you're developing languages on on on a more I guess niche team. What kinds of u AI tools are you using or or how is AI helping your language development work? May that be TypeScript or C#.
</details>

**Anders Hejlsberg**: 这一年半以来，我们一直在将 TypeScript 编译器迁移到**原生代码**。在项目初期，AI 远没有现在这么强大，所以没怎么用上。但现在，我们用得相当多。

我们在 GitHub 上使用 AI 进行 **PR 代码审查**。刚开始效果一般，但现在越来越好了。我们用 AI 来实现或修复一些简单的 Issue。在这次编译器移植中，我们有一大堆 PR 需要搬运到新的原生编译器上，我们正在用 AI 帮助我们搬运这些 PR。

此外，我们用它处理各种琐碎工作，比如：“这是个新功能，请按照这些已有测试的风格帮我写一些测试。” 没人喜欢写测试，但 AI 热爱写测试，它会疯狂产出测试，这太棒了。它帮我们摆脱了原本会消耗时间的繁重体力活。但我必须说，目前的阶段还没有到它能免除你对自己所做工作的理解。完全没有。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Day-to-day I work on on TypeScript and I can certainly talk about how we've been in the process of moving TypeScript to native code for the last year and a half or so. In the beginning of that project, AI was nowhere near as capable as it is now and therefore we could not really use much of it in the beginning. At this point though, I'd say we're using we're using AI fairly well. Obviously, we're on GitHub. We use AI to code review pull requests. that in the beginning was not all that great but now it's actually getting a lot better. um we use uh AI to implement issues or or fix issues, simple issues, and then it succeeds some of the time um in this port that we're doing, you know, because we snapped a copy of the source code from a year and a half ago and then ported it. We have a backlog of PRs that need to be moved on to the new native compiler. And so we're using AI to help us move those pull requests. Um, and that's actually going fairly well at at this point. And then we use it for a bunch of grudgery drudgery work like, okay, here's this feature. Please write me some tests in the same style as these other tests, right? And kaboom. It's like no one likes writing tests. AI loves writing tests and it'll just pump out more tests and great, you know? So, so we're trying to use it to get rid of all the toil that otherwise we would spend our time on, right? But I would say we're not at a point where it absolves us from understanding what we're doing. [laughter] Not at all. No.
</details>

**主持人**: 特别是当你处于技术栈的这一层时。

<details>
<summary>Original English</summary>
**Host**: Well, plus your level at the stack, if you will, because you're building a language, it might argue that someone really needs to understand at least one person. Ideally, the whole team needs to understand those fundamental parts, right? 
</details>

**Anders Hejlsberg**: 在 AI 的世界里，语言是非常有趣的。如果没有编程语言，AI 如何达到**确定性 (determinism)**？AI 在设计上就是随机的、不确定的。即使问同一个问题，下次给出的答案可能也不同。然而，如果应用的行为不确定，我们就无法构建应用。银行应用如果开始产生幻觉该怎么办？

所以，必须有一个东西让“橡胶接触地面”，在那里你可以进行推理，并在每次运行应用时复制其行为。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Oh, absolutely. I mean, and and it's language is interesting in the in the world of AI because AI like a lot of like this this conversation, we wouldn't have this conversation if it wasn't for languages because how would AI get to determinism without programming languages, right? I mean, AI is by design stochastic and indeterminate. It might give you a different answer the next time you ask it the same question. either just because random or because there's a new model or there's a whatever. It's non it's not it's there's no determinist yet we can't build applications if they're not if they have non-deterministic behavior. I mean what would a banking app look like if it like decided to hallucinate or or whatever, right? So you have to have something that where the rubber reads the road and where you can reason about and and where you can replicate the behavior every time you run the app. The same thing happens.
</details>

**主持人**: 没错。我发现几乎所有 AI Agent 遇到数据处理任务时，都会开始编写 Python 程序。因为 AI 设计者明白，在某个时刻，你必须将不确定性转化为确定性。

<details>
<summary>Original English</summary>
**Host**: Absolutely. I mean I even see it in a bunch I think almost all AI agents or tools these days when you ask get it something to do with data often times they will start writing a Python program because I think the AI designers figure it out that you at some point want to turn some non-deterministic into a deterministic and exactly what is exactly the thing that we know most efficient.
</details>

**Anders Hejlsberg**: 没错。**不要向 AI 要答案，要让它写一段程序来计算答案。** 你就知道那将是确定性的。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Yeah. Don't ask it for the answer. Ask it to write a program that computes the answer. and and you will know that that that will be deterministic.
</details>

**主持人**: 既然 AI 正在生成海量的代码。你认为在这种“代码由机器生成”的世界里，哪些语言特性会变得更重要？

<details>
<summary>Original English</summary>
**Host**: It's it's very interesting. But speaking of languages for for AI, a question that comes up of course because AI is everywhere is generating a lot more code. What is your take on either modifying existing languages for AI usage based on what you're seeing with the patterns or potentially coming up with would it make any sense to come up with a language that is more suited for AI agents to use? Knowing that we are already seeing a lot more code pushed everywhere and and from at a project level at a at an aggregate level, what do you think language characteristics could be become more important in this world of of just a lot more code often times generated by machines?
</details>

**Anders Hejlsberg**: 我认为我们已经度过了互联网的“真相峰值”，现在每天都有越来越多的垃圾。要从中筛选出有价值的训练数据变得越来越难。

至于适合 AI 的语言，我认为我之前谈到的**类型和推断 (inference)** 非常重要。此外，**局部性 (locality)** 也至关重要。我的意思是，不要搞一堆全局性的东西。如果是那些 `#include` 文件，天哪，谁知道它们的范围在哪？我要怎么把它们放进上下文窗口？如果局部性很好，你清楚地声明了导入了什么，AI 只需分析一个源文件，就能提取其对外协议，而不需要知道更深层的东西。这对于减小**上下文窗口**的大小以及让每个模块更易于总结是非常重要的。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: I mean, you could argue that we we're already past peak truth on the on the on the internet, right? And now there's there's just more and more garbage every every day. it gets harder and harder to sus out the stuff that you do want to include in the training set in order to actually make something more intelligent. So I think that that gradual I mean I'm sure people are working on it. I could see that as as as becoming problematic. Languages that are suitable for AI I I think like I talked about types and inference. I think both of those are important. I think also locality is is important. Well, what I mean by that is like don't have a bunch of global stuff where AI has to grock the entire pro. Oh, these pound include files that are oh my god. Well, who knows where they're in scope and and how do I put that in the context window or not? and then then do I burn like a gazillion tokens on on trying to include but but if you have good locality where you you're clearly stating what you're importing and whatever and and you can analyze just a single source file and from that extract its protocol to the outside world without having to to know anything deeper do you know what I mean? I think those are important aspects uh just simply to reduce the size of the of the of the context window and also make it easier to summarize each module in a program.
</details>

**主持人**: 局部性确实很重要。15 年前 PHP 就因为全局变量被诟病。原本的 JavaScript 也有这个问题，没有模块，全是全局的，任何人都可以猴子补丁（monkey patch）任何东西。现在有了 **ES Modules**，我们正在走向理性。

此外，AI Agent 现在正开始意识到语言服务的存在。AI 喜欢命令行工具。我还想知道**性能**是否会变得更有趣。更快的反馈循环显然是有帮助的，正如 TypeScript 之所以受欢迎是因为 200 毫秒的反馈。如果 AI 能够在其生成代码的过程中，通过语言服务进行语义验证，这将变得越来越重要。

<details>
<summary>Original English</summary>
**Host**: Right? This is so fascinating because I remember this was probably 15 years ago where PHP was very much critiqued for its globals and early on I didn't understand as a young developer why that was a big deal. Original JavaScript suffered from this problem. There were no modules, right? everything was global and anyone could just like monkey patch anything else and it was impossible to know really what what what what am I sitting on top of here but now with eggmascript modules and whatever we're we're we're moving towards sanity and more and more the world is written that way in the JavaScript ecosystem and that's a good thing and I think that will help us down the line uh with uh with AI AI to it's just starting to to become aware of you know the existence of of of language services and agents today. I also wonder if if for example performance will be interesting because we know that these things can can run faster. So faster feedback loops will clearly be helpful which we're now going back to one of the reasons the typescript was so popular. You said the 200 milliseconds of getting you feedback right but there are ways of you know where where you could imagine you know like a server keeping a project hot and and giving you LSP services you know that AI can ask semantic questions and and whatever and then once AI stops asking after 10 minutes the server just dumps it you know and and whatever. There there are ways of putting this together I think where we can make some progress on on because like the ability for AI to semantically validate the code that it's generating as it's generating it will increasingly become important.
</details>

### 软件工艺的转型

**主持人**: 在这个行业几十年后，看到这些工具进入日常使用。你认为软件工程师的**工艺 (craft)** 中，哪些部分会变得不那么重要，哪些会变得更重要？

<details>
<summary>Original English</summary>
**Host**: What about the the software craft? You've you've you've been in this industry for for many decades but it's hard to unsee that these tools are just coming to everyday use similar to how at some point graphical IDs came before that. Knowing that AI agents and AI tools will be part of the craft. What do you think parts of software engineer craft will become less important and what might become more important?
</details>

**Anders Hejlsberg**: 在某种意义上，我们都在变成**项目经理**。我们可以有一支叫 Agent 的初级程序员大军，它们会喷出大量的代码，但必须有人拥有全局视野并审阅这一切。

所以，我们的工艺正在从“编写代码”转变为“**审阅代码**”、“构建代码架构”和“监督工作”。这是一种不同的工艺，一种不同的享受。我一直喜欢写代码，看到它运行起来让我很有成就感。某种程度上，AI 剥夺了一部分这种乐趣。虽然审阅代码没那么有趣，但我们可以让审阅过程变得比今天更有趣。目前你看到的只是按字母顺序排列的差异（diffs），你得自己去理清头绪。其实可以用更具教学意义的方式来呈现，由 AI 生成评论告诉你改动了什么，并引导你。

我认为认为 AI 会消灭程序员是愚蠢的。“氛围编码（Vibe coding）”在有效时很棒，但一旦偏离轨道，你就完全不知道发生了什么，也没法说服 AI 去修复它。你不能免除自己对发生的事情的理解。那不叫编程。而且最终，程序的**责任**不在 AI 身上，而在程序员身上。你没法对 AI 说：“为你感到羞耻，我要开除你。”

所以，AI 是一个让我们变得更高产的工具，它会改变我们写程序的方式。没必要坐在那儿输入 AI 能快 100 倍输入的东西。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: In a sense, we're all turning into project managers, right? Um and and we can have an army of junior programmers called agents that will just spit out reams of code, but someone's got to have the big picture and review all of that. And so increasingly our craft is going from one of writing the code to one of of reviewing the code and and building the architecture of the code and overseeing the work if if you will. It's a different kind of craft. It's a different kind of enjoyment. Uh I've always liked writing the code. You know, to me that was the fulfilling part, seeing it work. Do you know what I mean? and and and and it in in a in a way AI robs a little bit of that, right? I mean because I I I am less interested in reviewing code, but I think we could also make the process of review of reviewing code much more interesting than it is today, right? I mean, today you see a list of of diffs in alphabetical order and and now it's up to you to to make heads or tails of it. I mean, there are more pedagogical ways of of of of presenting that and and you could have commentary generated by the AI that tells you what the changes are and whatever and then tries to guide you along. Do you know what I mean? So, so that symbiotic relationship, I think we we need to work on that more and so sort of to to to to keep the enjoyment in there. But I think it's foolish to think that AI will just eliminate programmers and then because ultimately that's great, you know, like like vibe coding is wonderful as long as it works. And then the minute it it goes off track, then you're like you have no idea what's going on and you can't convince the AI to fix it. And so what do you do? You can't absolve yourself from understanding what's going on. That that's not that's not programming. And ultimately also, you know, the responsibility for a program does not lie with the AI. It lies with the programmer. You you're not going to go back to the eye and say, "Shame on you. Uh, I'm going to fire you." [laughter] What does that even mean? Right? I mean, now you have nothing. you know it's no you need someone to have that that function of being responsible and so so that's you know so so ultimately AI is a tool to enable us to become more productive I think but it will change the way that we write our programs for sure I mean there's no point in in in in in sitting there and typing in stuff that AI could type 100 times faster you know
</details>

### 设计经验与长线游戏

**主持人**: 创造了三门广泛使用的语言后，你学到了开发者最关心什么？

<details>
<summary>Original English</summary>
**Host**: having created three very widely used programming languages what have you learned about developers about what they care about when it comes to programming languages and stuff that maybe they don't care too much about and don't even think about it, but you might have to think a lot about.
</details>

**Anders Hejlsberg**: 归根结底，开发者关心**生产力**。他们关心是否处于“心流（in the zone）”状态，感觉一切都在契合，工具就像手指的延伸。

所以作为语言设计师，我从不只看语言。你必须看全景图，看整个体验。程序员职业生涯的大部分时间都在这种体验中度过。这就是为什么程序员会深深依恋他们的工具和语言，这几乎是一种宗教信仰，因为它深深融入了工作流，让你进入心流状态。这就是我多年来工作的核心。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: You know, I think at the end of the day, developers care about being productive. They care about being in the zone where they feel like, "Oh yeah, this thing is just clicking for me. It's doing just the right thing and it's like answering me, but it's it's right there. It's an extension of my fingertips." Right? So, for me as a as a language designer, I'm never just looking at the language. It's you're looking you got to look at the whole picture, the whole experience because really what you're doing is you're creating an experience. An experience that programmers will spend the majority of their working life in which is why why programmers become so attached to their tools, you know, and their languages, right? I mean it's it's almost a religious thing which which language you're and which tool you're using and be because it's it's so ingrained in your workflow and and it so enables you to to be in the zone. Right. So that I think is the that's the key to focus on and that's what I've tried to do with with the with the the work that I've done over the years.
</details>

**主持人**: 这就是为什么你从一开始就关注 IDE。

<details>
<summary>Original English</summary>
**Host**: And it sounds like this is why from the very beginning you also focus on the IDE the the tool where developers spend their time in.
</details>

**Anders Hejlsberg**: 是的，缺一不可。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Yeah. You can't have one without the other. Well, you can, but but it's just not it's not nearly as effective.
</details>

**主持人**: 说到效率，你最早的电脑内存极小，你能把编译器塞进 12K。现在我们随便写个文件都比那大。现在的开发者是不是因为资源丰富而不再关注效率了？

<details>
<summary>Original English</summary>
**Host**: What about performance and efficiency? Early on in your career, you just mentioned that your first computer you had on how many kilobytes it had and how you you fit your compiler into 12 kilobytes, which these days I I cannot even create a text a text file that smaller than that. uh or it's very hard to do, right? But it seems in those in the you know like a few decades ago writing efficient programs was important and over time my perception is that it's becoming less of a focus. What is your take on that and do you think it's kind of fine for us developers to forget about efficiency or we're just allowed to do that because of we have more resources or maybe this will change?
</details>

**Anders Hejlsberg**: 这取决于应用。对于某些类型的应用，效率绝对是关键。比如我的团队做的编译器、工具，人们确实在乎。这就是为什么我们花一年半时间将其移至原生代码。对于金融交易、云端大数据分析，性能就是一切。但在很多地方，性能并不重要，因为它已经够快了，即便慢 10 倍你也察觉不出来。不值得在那里优化。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: I think it's a case of it depends. There are certain classes of apps for which efficiency is absolutely key. I mean like the kind of program that my group works on like compilers tooling and whatever. Yeah, people do care. That's why we're we're spending a year and a half moving to native code inference in in the cloud on up against data. I mean oh my god, you know like financial fast trading uh whatever it's all about PF, right? I mean, and the speed of light and like trying to trying to move your trade faster than the other guys. I mean, so so there are lots of places where Perf is king. But there's increasingly also places where where Perf doesn't really matter because, you know, it's so fast anyway that if it even if it's 10 times slower, you still can't detect a difference. And so it's just not worth optimizing there anymore. It depends, I think, on on on the kind of app you're building. 
</details>

**主持人**: 你在微软待了 30 年，从事语言工作 40 年。在大家每 3-5 年换一次工作的今天，是什么让你待了这么久？

<details>
<summary>Original English</summary>
**Host**: it's a good reminder that not all use cases are are born equal. I'm interested what is your personal development setup like these days. I was interested in reflecting a little bit on your career you've now been at Microsoft for for 30 years and you've been working on programming language which is for 40. That's even, you know, a lot to to say. But in this industry, it's pretty much common for people to change jobs every 3 to 5 years or so. What has kept you at a company for for so long and also in in a similar area for even longer?
</details>

**Anders Hejlsberg**: 开发者工具和编程语言就是我的热爱所在。这些是复杂的算法问题。而且它们对其他东西的依赖较少，你可以自己从底层构建。

从事编程语言工作你会意识到，这是一个**长线游戏 (long play)**。我参与的项目通常以 **10 年**为一个周期。版本 1 固然很棒，但会有各种问题；你得做版本 2；到版本 3 才开始真正变得出色；然后你还得说服人们真正去采用它。你必须愿意玩这个长线游戏。

在微软待了这么久，是因为被置于这样的位置：像微软这样的公司全力支持你创造一门语言。这种机会在别处可不多见。而且，微软从根本上说是一家**以开发者为中心**的公司。他们就是这样起家的。是开发者和企业在支付账单，而不是广告商。我喜欢这种感觉：你像是在做艺术家的工作，而人们愿意为此买单。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Well, there's there's just something about developer tools that that is just what I love to do, you know, and and programming languages. And they're they're they're complex uh algorithmically complex problems to solve. And I I I for some reason like that they have fewer dependencies on other things. So you're you're you're building from the bottom yourself. Do you know what I mean? You don't have to like sit on top of someone else's framework and and and swear at them when it when it doesn't do what you want it to do, right? So that kind of works for me, right? But but the thing is like doing programming languages, you come to realize it's a long play. I mean, if if you look back at the the the stuff I worked on, it it it goes in 10 years. cycles at least and Typescript didn't really for example or C# for that matter. I mean it took it it takes 10 years to get to you know version one is great but it has all sorts of issues and you got to do version two and then it's not until version three that it really starts to be great but then now you got to convince people to actually adopt it and and and it it's just it's a long play. You got to be willing to do the long play. Um, and I think look, having been at a at a company like Microsoft is is it's it's been great because to be put in a position where a company like Microsoft is putting their might behind your efforts on creating a programming lace, that's not an opportunity you get in a lot of places, right? And that has been fantastic. But also, you know, the fact that Microsoft is fundamentally a developer focused company and they they always have been. That's how they started. Developers matter. It's not it's not advertisers who are who are paying the bills. It's it's developers and enterprises that you know and and I like that like where you feel like you're doing an artist based work and people are paying you for it and it's it's good stuff you know
</details>

**主持人**: 最后，你推荐哪本书？

<details>
<summary>Original English</summary>
**Host**: as closing what what is a book that you would recommend and why
</details>

**Anders Hejlsberg**: 我总是推荐同一本书，那就是 **Niklaus Wirth** 的《**算法 + 数据结构 = 程序**》（*Algorithms + Data Structures = Programs*）。虽然是 70 年代写的，但读这本书对我来说是一次启示。我从中学习了哈希表，如何构建一个小编译器等等。它案例丰富，虽然我现在是个工程师，但那本书仍非常吸引我，而且在很多方面今天依然适用。

基础知识并没有改变太多，特别是编程语言领域，这已经是一个建立 50 多年的成熟学科了。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: I always recommend the same book which is Nick Viet programs plus data structures uh um equals algorithms it's actually like available online now it was written in the 70s but that was the book that it was a revelation for me to read this book this is how I how I learned about hash tables and the how to construct a small compiler and and whatever and it was it was just wonderful. It's very light on symbolism and very rich on examples and and and I was always an engineer and so that book just appealed to me and I think it's still in in in a lot of ways super relevant today. The basics have not changed have they too much. No. No. Well, I know certainly and and particularly when it when it comes to programming languages. Heck, it's it's a it's a wellestablished discipline quite honestly. Yeah, it's been around for 50 plus years.
</details>

**主持人**: 谢谢你，Anders，谢谢这次深入的对话。

<details>
<summary>Original English</summary>
**Host**: Well, Anders, thank you so much for this in-depth conversation.
</details>

**Anders Hejlsberg**: 噢，这是我的荣幸。非常有趣。

<details>
<summary>Original English</summary>
**Anders Hejlsberg**: Oh, my pleasure. This was a lot of fun.
</details>

---

**主持人总结**: 
我一直在思考 Anders 说的：编程语言设计是一个至少 **10 年**的周期。版本 1 有问题，版本 2 修复，版本 3 才真正出色，然后你还得说服大家采用。大多数开发者习惯于按季度和 Sprint 思考，这确实是一个完全不同的时间维度。

此外，听到 C# 语言设计团队只有 **6-7 人**，并且工作如此精简（每周 3 次会，每次 2 小时），这令人惊讶。这提醒我们，卓越的技术作品往往来自小团队而非委员会。

最后，我非常喜欢 Anders 说的：**IDE 就是语言**。从 90 年代的 Turbo Pascal 到今天的 TypeScript 和 VS Code，Anders 认为编译器不是产品，产品是整个“编辑-编译-运行-调试”的循环。这是对所有构建软件的人的良好提醒。

感谢收听，我们下期再见。