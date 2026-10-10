---
author: The Pragmatic Engineer
date: '2026-07-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KSkcgIYQy0U
speaker: The Pragmatic Engineer
tags:
  - formal-methods
  - verification
  - concurrency-modeling
  - property-based-testing
title: 形式化方法与验证在软件工程中的应用及未来趋势
summary: 文章探讨了形式化方法的概念，从将隐式知识显式化的过程入手。重点讨论了该领域如何应用于分布式系统（如AWS的案例），以及基于属性的测试作为折中方案的价值。同时分析了人工智能对形式化验证的主流影响，并总结了在并发问题处理上实践经验的重要性。
insight: ''
draft: true
series: ''
category: testing
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books:
  - Engineering a Safer World
  - Data and Reality
  - 'Debugging: the nine simple rules'
status: evergreen
---
<!-- chunk 1/12 -->

### 什么是形式化方法与验证 (What are Formal Methods and Verification)

**Hillel Wayne**: 让我们来谈谈形式化方法。在你大脑中有一种隐式机制，能够看到代码并知道这个函数应该是做什么的。因此，我使用形式化方法的第一步是问，我们能否将这种隐式知识变得显式化？我们能否弄清楚一个函数实际上应该做什么，并以一种可以向任何人展示的方式将其写下来？

<details>
<summary>Original English</summary>

**Hillel Wayne**: Let's talk about formal methods. There's some sort of implicit mechanism in your brain that can see that and know what the function is supposed to do. So step one of what I do with formal methods is asking can we take that implicit knowledge and make it explicit? Can we figure out what a function is supposed to actually be doing and write that down in a way that can be shown to anybody?

</details>

**Host**: 为什么我们不针对所有东西都做形式化测试呢？

<details>
<summary>Original English</summary>

**Host**: Why are we not doing formal testing for everything?

</details>

**Hillel Wayne**: 当你开始讨论大多数有趣的领域问题时，你必须引入如此多的上下文，以至于甚至写出函数应该做什么都成为了一场噩梦。你说的对，命令式编程在 99% 的情况下已经足够好，几乎可以用于所有情况。

<details>
<summary>Original English</summary>

**Hillel Wayne**: When you start talking about like most interesting domain problems, you have to pull in so much context that basically even writing what the function is supposed to do becomes a nightmare. the imperative program you're right that we'll get 99% of the time is probably good enough to use in almost all cases.

</details>

**Host**: 我听过一个故事，我想你可能也参与其中，就是 AWS 使用了 TLA+。

<details>
<summary>Original English</summary>

**Host**: One story I've heard and I think you might have been involved is AWS using TA plus.

</details>

**Host**: 他们谈到了公司里的几个人对它感兴趣，学习了 TLA+ 以及另一种名为 PlusCal 的语言，并将其应用到 DynamoDB 和 S3 存储系统的各个方面。在这样做的过程中，他们发现了一些相当复杂的、可能导致数据丢失的漏洞。现在我们有 AI 生成了大量的代码，也许进行更多的验证或基于属性的测试会更有用。你认为这会发生吗？

<details>
<summary>Original English</summary>

**Host**: They talked about how a couple of people in the company were interested learned TA plus and another language called Plus Scout and applied it to aspects of the Dynamo DB and S3 storage systems. In doing so, they were able to find fairly complicated bugs that could potentially lose data. we have AI generating way more code maybe for more verification or property based testing could be more useful. Do you think this will happen?

</details>

**Hillel Wayne**: 我自己在这方面做了很多尝试，我认为有一件事 AI 非常不擅长。现在流行一种理论，认为 AI 将最终使形式化验证成为主流，因为当机器编写代码时，人类需要它是正确的数学证明。

<details>
<summary>Original English</summary>

**Hillel Wayne**: I've been doing a lot of experience in this myself and I think the one thing AI is extremely bad at. There's a popular theory going around that AI will finally make formal verification go mainstream because when machines write the code, humans will need mathematical proof that is correct.

</details>

### 本期嘉宾介绍与内容概览 (Guest Introduction and Episode Overview)

**Host**: 今天，和我对话的是回应这个问题的最佳人选之一：Hillel Wayne，一位形式化方法顾问。他在整个行业内教授 TLA+（一种流行的形式化规范语言），撰写了《Logic for Programmers》一书，并且即将加入 Antithesis 公司。在今天的对话中，我们将讨论“跨界项目”（Crossover Project）——Hillel 采访了超过 15 位传统工程师的研究，以回答“软件工程师是否也能被视为真正的工程师？”这个问题。我们还会讨论 AWS 是如何使用 TLA+ 的；简要介绍亚马逊如何使用这种形式化规范语言在 DynamoDB 中发现罕见的 Bug；深入探讨基于属性的测试，以及为什么这是大多数工程师都应该采用的折中方案等诸多话题。如果你想了解更多关于形式化验证的知识，并了解这种方法是否会随着 AI 成为主流，这期节目就是为你准备的。在今天的节目中，我们将讨论这样一个问题：使用形式化方法来验证 AI 编写的代码是否有意义？剧透一下，答案是：使用完备的形式化方法有点杀鸡用牛刀了，但轻量级的形式化方法确实会有所帮助。

这里我需要提一下我们的赞助商，Antithesis 通过在恶劣的模拟环境中运行你的整个系统并发现漏洞来验证你的系统的正确性。它通过一种名为确定性模拟测试 (DST) 的方法来实现这一点，AWS 杰出工程师 Mark Brooker 和 Ankur Desai 将这种方法描述为轻量级形式化方法。先抛开 Antithesis 不谈，如果你作为一名工程师想更严肃地验证你的系统是否按预期工作，你最好的选择将是使用轻量级形式化方法。说回 Antithesis，Antithesis 通过在积极的故障注入下运行你的整个系统来提升测试效率。想象一下 Antithesis 就像是运行着成百上千个版本的马里奥游戏。每个实例都试图通过越来越诡异的输入组合来积极地破坏游戏。通过 Antithesis，你可以指定整个系统级别的属性，而 Antithesis 会主动尝试去推翻它们。因此你可以确信，如果你的系统在 Antithesis 中能够稳定运行，那么它在生产环境中也同样能够稳定运行。像 Jane Street、Fly.io 以及 CCD 社区这样的团队之所以依赖 Antithesis 是有充分理由的。前往 antithesis.com/pragmatic 了解更多信息。

你好，欢迎来到播客。

<details>
<summary>Original English</summary>

**Host**: Today I'm talking with one of the best people to respond to this, Hill Wayne, a formal methods consultant. He taught TLA plus a popular formal specifications language across the industry, wrote the book logic for programmers and will soon be joining antithesis. In today's conversation, we discuss the crossover project. Hill's research interviewing 15 plus traditional engineers to answer the question, can software engineers also be considered real engineers? How AWS used TA plus? an overview of how Amazon found a rare bug inside of Dynamo DB using this formal specifications language, a deep dive into property based testing and why this is a middle ground that most engineers should probably adopt and many more. If you want to understand more about formal verification and get a sense of whether this approach could go mainstream with AI, this episode is for you. In today's episode, we'll get to the question, does it make sense to use formal methods to verify AI written code? As a spoiler, the answer will be proper formal methods are an overkill for this, but lightweight formal methods can actually be helpful. This is where I need to mention our presenting sponsor and antithesis verifies your systems correctness by running your whole system in hostile simulation and finding bugs. It does this by using an approach called deterministic simulation testing or DST which AWS distinguished engineer Mark Burker and Ankor Desai have described as lightweight formal methods. Setting aside in synthesis for a minute, if you as an engineer want to get more serious in verifying that your system works as intended, your best bet would be to use lightweight formal methods. Now back to antithesis. Antithesis is turbocharges testing by running your whole system under aggressive fault injection. Imagine antithesis as hundreds or thousands of versions of the Mario game running. Each instance aggressively trying to break the game with increasingly weird input combinations. With antithesis, you can specify properties at the whole system level and antithesis will actively try to disprove them. So you can be confident that if your system holds up in antithesis, it will hold up in production. There's good reason teams like Jane Street, Fly.io and the CCD community rely on antithesis. Head to antithesis.com/pragmatic to learn more. So hello, welcome to the podcast.

</details>

**Hillel Wayne**: 非常感谢。我很高兴能来到这里。

<details>
<summary>Original English</summary>

**Hillel Wayne**: Thank you so much. I'm really excited to be here.

</details>

### 从物理学到形式化验证 (From Physics to Formal Methods)

**Host**: 很高兴你能来。我很好奇，你因形式化方法、编程、逻辑以及所有这些主题而闻名，但你是如何进入科技行业的？

<details>
<summary>Original English</summary>

**Host**: It's so nice to have you here. I was curious, you're very well known for for meth methods, for programming, for for logic, for all of these topics, but how did you get into tech?

</details>

**Hillel Wayne**: 首先，我从没把自己看成一个纯技术人员。我从小喜欢电脑，也会一点点编程。我父亲是个程序员，他教过我 Visual Basic。但我一直想学物理和数学，那是我的梦想。我在大学申请表里写道，我想聆听宇宙的心跳。千万不要听高中生关于写作的建议，我只是随口一说。但是，在大学里读了三年之后，我意识到我虽然喜欢物理的概念，但我并不享受做物理研究，我也无法想象自己能做 50 年。不过，我真正享受的是实验室里的编程部分，那对我来说是最有趣的部分。于是我想，既然这是我喜欢的，为什么不尝试把它作为全职工作呢？大学毕业后，我去了旧金山，成了一名教育科技领域的 Ruby on Rails 开发人员。过了一段时间，我搬回了芝加哥。然后，在做下一份同样是教育科技行业的工作时，我进入了现在的细分领域，也就是形式化验证和形式化方法。

<details>
<summary>Original English</summary>

**Hillel Wayne**: So, to start, I never really saw myself as a technical person. I like computers growing up and I did a tiny bit of programming. My father was a programmer. He taught me visual basic, but I always wanted to do physics and math. That was like my dream. I put in my college application, I wanted to listen to the heartbeat of the universe. Don't ever take advice from like a high schooler for writing. Just Just saying. But after about 3 years of doing this in college, I realized that I kind of like the idea of physics, but I didn't enjoy doing it and I couldn't see myself doing it for 50 years. What part I did enjoy though was the programming in the labs. That was the most fun part to me. So I thought, well, if this is what I enjoy, why not try to do it full-time? So after college, I left for San Francisco and became a um developer, a Ruby on Rails developer in education technology. After some time, move back to Chicago. And then in the course of the next job I was working in also in education technology I fell into my current niche which is formal verification and formal methods.

</details>

### 软件工程师是“真正的工程师”吗？ (Are Software Engineers "Real Engineers"?)

**Host**: 我第一次读到你的文章（因为你经常写博客，而且我非常喜欢你的文章），就是关于“跨界项目”（The Crossover Project）。在这个项目中，你试图回答一个问题：作为软件工程师，我们真的是工程师吗？

<details>
<summary>Original English</summary>

**Host**: The first time I came across your writing because you you you write a blog a pretty regular one and I I really enjoy your writing. The first time was with the crossover project. This was a project where you attempted to answer are we as software engineers actually engineers?

</details>

**Hillel Wayne**: 是的。

<details>
<summary>Original English</summary>

**Hillel Wayne**: Yes.

</details>

**Host**: 我们能谈谈这个项目吗？

<details>
<summary>Original English</summary>

**Host**: Can we talk about this project?

</details>

**Hillel Wayne**: 当然可以。所以我想我应该从动机开始讲起。我读过很多关于软件的书，也读过很多关于软件的在线文章，软件开发者最喜欢做的事情之一就是争论软件开发是否应该算作工程。有一派人说，我们不配称自己为工程师，我们不应该，他们（传统工程师）远高于我们，我们甚至不应该把自己和他们归于同一个领域。然后还有一派人说，我们所做的事情是如此特别、如此独特，工程学根本比不上我们，他们根本无法与我们相提并论。你会看到像《软件匠艺》（Software Craftsmanship）这样的书，里面谈到了工程学是一个非常无聊、缓慢的领域，而软件是一项极具创造力、特别而美妙的事情。我曾经坚定地属于第一阵营。我认为我们不是工程师。我们不配称自己为工程学或类似的东西。我工作中所做的，是非常仔细地分析软件系统，我想，啊，这才是真正的工程，其他的一切都不是工程。然后我看到了 Glenn Vanderberg 的一次演讲，他读了一堆工程学的书，并将它们与我们在软件领域所做的事情进行了比较。他说，其实这看起来和我们在软件里做的非常相似。我心想，这不可能。我需要更严谨的东西。我必须去和那些既做过工程又做过软件开发的人谈谈，看看他们怎么说。结果，他们都同意他的观点。所以我错了。我们是工程师。

<details>
<summary>Original English</summary>

**Hillel Wayne**: Absolutely. So I guess I should probably start with the motivation which was I've read a lot of books on software and I've read a lot of online articles about software and one of the favorite things that software developers do is argue about whether it should be engineering or not right and there's the camp of people that say well we don't deserve to call ourselves engineers we should not they are so far above us we shouldn't even like consider ourselves in the same space and then there are the people who are like what we do is so special and so unique Engineering doesn't have anything on us. They can't hold a candle to what we do. You see books like software craftsmanship which talk about how like oh engineering is this really boring slow field and software is this incredibly creative special wonderful thing. I was very permanently in camp one. I thought we were not engineers. We didn't deserve to call ourselves engineering anything like that. What I do for work is really carefully analyzing software systems and I thought ah this is real engineering and everything else is not engineering. Then I found this talk by Glenn Vanderberg where what he did was he read a bunch of engineering books and compared them compared them to what we do in software. And he said actually this looks really similar to what we do in software. And I thought that can't be right. I need something more rigorous. I'm going to have to talk to people who did both engineering and software development and see what they say. And they all agreed with him. So I was wrong. We're engineers.

</details>

**Host**: 我们能深入探讨一下吗？

<details>
<summary>Original English</summary>

**Host**: Can can we go a little bit into it?

</details>

**Hillel Wayne**: 所以，当我开始和第一批人交谈时，我意识到这个项目比我预想的要深入得多。我决定我需要尽可能全面地了解传统工程学。工程学有很多种，不仅有造桥，还有设计电路。有研究化学过程的。有工业工程，也就是研究工厂布局以及如何组织各类劳动力的。有非常多不同的种类。我希望能看到每一种工程学的视角，了解他们眼中的工程学是什么样子的，然后将它们全部与软件进行比较。当你仔细想想，当我们说软件不像造桥时，也许确实不像，但它像设计电路吗？像规划化学流程吗？也许这些更接近我们所做的工程类型。我必须弄清楚。我想最后我总共采访了大约 15 到 20 个人，涵盖了大概六七个不同的领域。

<details>
<summary>Original English</summary>

**Hillel Wayne**: So, as I started talking to the first people, I realized that this was a much deeper project than I ever expected. And I decided I needed to have as comprehensive a look at traditional engineering as I could possibly get. There are many kinds of engineering. There's not just building bridges, but there's designing circuits. There's figuring out chemical processes. There's industrial engineering, which is figuring out the layouts of factories and how we organize kinds of labor. There's just so many different kinds. And I wanted to see every single kind's view into what engineering looked like to compare them all to software which when you think about it when we say like oh software isn't like building a bridge maybe it isn't but is it like designing a circuit is like figuring out a chemical flow maybe those are much more closer to the kinds of engineering we do I needed to know I think in the end I talked to about 15 or 20 people in total across about six or seven different fields

</details>

**Host**: 那么你发现软件工程与特定类型的工程，或者说跨领域之间有什么相似之处呢？

<details>
<summary>Original English</summary>

**Host**: and what were the similarities that you found that software engineering has with either specific types of engineering ing or across

</details>

<!-- chunk 2/12 -->

### 迭代与工程的核心张力

**Speaker A**: 如果我必须对我总体上的发现做一个总结，我会这样说：所有人都讨厌瀑布模型。

<details>
<summary>Original English</summary>

If I had to summarize what I found in general, I'd put it like this. Everybody hates waterfall.

</details>

**Speaker B**: 不是吧。

<details>
<summary>Original English</summary>

No way.

</details>

**Speaker A**: 工程学的核心张力在于，犯错的代价有多高，以及你的迭代速度有多快。你能迭代得越快，在迭代之前你需要做的计划就越少。而犯错的代价越高，你需要做的计划就越多。
这就是为什么，比如你在盖一栋楼的时候，你不可能像建造多次并观察结果那样去试错，你必须在前期做大量的规划。但即便如此，你仍然在寻找迭代计划的方法，比如制作比例模型，或者使用软件来模拟这栋建筑，比如建立 CAD 模型等。
而在其他领域，比如电气工程，你有能力提出一个设计，对其进行测试，然后把它扔给晶圆厂并得到反馈结果，所以他们比土木工程迭代得要多得多。

<details>
<summary>Original English</summary>

Core tension of engineering is between how expensive it is to make a mistake and how quickly you can iterate. The faster you can iterate, the less planning you need to do before you iterate. And the more expensive it is, the more planning you need to do. That's why for example when you're building a building where you can't build it multiple times and see what happens you have to do a lot of planning up front but even then you are looking for ways to iterate on the plan you do things like build scale models you use software to simulate the building you do CAD models etc and in other fields like in for example electrical engineering you have the ability to come up with a design test it and then throw it to the fab and get something back so they will iterate a lot more than civil engineering does.

</details>

**Speaker B**: 很有意思，我听说“冒烟测试”（smoke test）这个词最初就是起源于电气工程的。

<details>
<summary>Original English</summary>

Interesting enough I heard the term smoke test originated from electrical engineering. Actually,

</details>

**Speaker A**: 我没有具体研究过这个，但我相信是这样的。

<details>
<summary>Original English</summary>

I did not look into that, but I could believe it.

</details>

**Speaker B**: 是的，据说就是当你有一个测试电路时，你只要把它接通，如果它冒烟了，那说明它已经坏了。这非常有趣。所以，即使在工程领域内，当我们说传统工程时，其实也有着不同层次的工程或者差异，对吧？

<details>
<summary>Original English</summary>

Yeah, apparently it's when you have a test circuit and you just hook it up and if it smokes, it's already bad. That is very interesting. So, even within engineering, when we say traditional engineering, there's just layers of engineering or differences, right?

</details>

**Speaker A**: 迭代的层次。我想说，我最早交谈过的人之一实际上是一位采矿工程师。他在地下深处设计矿井，以确保它们是稳定的，而且不会泄漏有毒化学物质。
他向我指出的第一件事就是，他们在1960年就经历了他们的“敏捷革命”。我相信他们把这称为“维也纳隧道挖掘法”（新奥法，Viennese tunneling method），作为一种真正快速迭代建造矿井并在岩石中挖掘隧道的方法。基本上就是尽可能快地做出改变，观察系统其余部分对此的反应，然后根据结果进行路线修正。

<details>
<summary>Original English</summary>

Layers of iteration. I'd say one of the first people I talked to was actually a mining engineer. He designed mines deep underground to make sure that they were stable and didn't leak toxic chemicals. And the first thing he pointed out to me was that they had their agile revolution in 1960. They called it, I believe, the vianese tunneling method as a way of really quickly iterating through building a mine and tunneling through rock. Basically making the change as fast as they could, seeing how the rest of the system reacted to it and then course correcting based on that.

</details>

**Speaker B**: 好的。所以我猜我们所有人都讨厌瀑布模型。

<details>
<summary>Original English</summary>

Okay. So I guess we all hate waterfall.

</details>

**Speaker A**: 我们所有人都讨厌瀑布模型，或者说讨厌瀑布模型的这种理念。

<details>
<summary>Original English</summary>

We all hate waterfall, or the idea of waterfall.

</details>

**Speaker B**: 是的。那么你遇到了哪些有趣的差异？无论是其他工程领域领先于我们的地方，还是传统工程确实有一些你希望能找到的优势的地方，亦或者是软件工程实际上在某些方面处于领先的地方？

<details>
<summary>Original English</summary>

Yeah. What are some of the interesting differences that you came across either where engineering is ahead of us or traditional engineering does have things on us which you were hoping to find or places where actually software engineering is ahead in some ways.

</details>

**Speaker A**: 在我们实践它的方式上既存在差异，我们所使用“材料”的形态上也存在差异，因为每种工程都涉及不同的材料。它们有不同的约束条件。
虽然每个人都试图尽可能快地迭代，且经常求助于软件来做到这一点，确实软件在这方面是做得最好的。最好的比较对象是化学工程，我与相关人员交谈过，他们说他们会建立实验，让它运行一整夜，第二天得到结果，这在他们看来就已经算是很快了。
而对我们来说，我们基本上可以按一下 F11 键就能得到结果，对吧？这使得我们基本上能够比这些领域迭代得快得多。我想我们大家都多少知道这一点。
作为软件工程师，我们可能没有意识到的一件事是，我们的工作比其他领域的一致性要高得多。我有时会举的一个例子——因为我做过一个演讲——我会拿出一个 CPU 芯片或者一根内存条，我会说，嘿，这是规格说明书，如果你看这个说明书，它说这个电阻器的电阻在100欧姆的20%范围内，只要你把它保持在20到50摄氏度之间。
所以他们基本上是在说，如果他们制造了一千个这种元件，在所有的一万个元件中会有20%的差异。唯一知道确切数值的方法就是去测试它们。然后如果你让它运行太久，或者你把它加热得太多，它又会发生改变。
而在软件方面，假设没有 CPU 漏洞或类似的问题，同一个程序如果在我的电脑上运行，它在你的电脑上运行也会是完全一样的。用同样的排序算法对这个列表进行排序，结果完全相同。

<details>
<summary>Original English</summary>

There's both differences in how we practice it but also differences in the shape of our material because every engineering concerns a different material. They have different constraints. While it's true that everybody tries to iterate as fast as they can, often turning to software to do that, software is the best at it. The best comparison is chemical engineering where I talked to people saying that they would set up their experiment, run it overnight and get the results the next day and that was fast. With us, we can basically press F11 and get the result, right? And that allows us to basically iterate much faster than even those fields can. I think we all kind of know this. One thing that we might not realize as software engineers is that our work is a lot more consistent than other fields. The example I always do sometimes because I've given a talk about this is I would pull out a CPU chip or a stick of RAM and I'd say hey here's the spec sheet and if you look at the spec sheet it says this resistor has a resistance that is within 20% of 100 ohms as long as you keep it between 20 and 50° centigrade. So they're basically saying that if they make a thousand of these, there's going to be a variance of 20% across all 10,000. And the only way to know is to test them. And then if you run it for too long or you heat it up too much, it's going to change again. With software, assuming no CPU bugs or anything like that, the same program if it runs on this computer, it'll run on your computer exact same. Sort this list the exact same with the sorting algorithm.

</details>

**Speaker B**: 这是否也意味着，我们可能不需要像其他工程学科那样过多地去考虑可变性？

<details>
<summary>Original English</summary>

Does this also mean that we might not account for variability as much as other engineering disciplines do?

</details>

**Speaker A**: 我认为是这样的。我们必须应对的变化其实也是我们自己制造出来的，对吧？我们实际上是在说，好吧，我们有所有这些不同的系统，所有这些不同的 API 要对接其他人，比如，我们有所有这些不同的芯片组。我们有所有这些不同的端口或尺寸，而且，如果你碰巧把一个铁螺丝接触到一个钨螺丝，它们之间就会发生腐蚀。另外，你的一些螺丝可能比其他的稍微大一点，有些可能稍微小一点，或者稍微长一点等等。

<details>
<summary>Original English</summary>

I'd say so. The variation we have to deal with is kind of our own making, right? We're basically saying, okay, we've got all these different systems, all these different APIs versus other people like we have all these different chipsets. We've got all these different ports or sizes, but also if you happen to touch an iron screw to a tungsten screw, they're going to cause corrosion between the two of them. And also, some of your screws are a little bit bigger than others and some are a little bit smaller than others, or a bit longer etc.

</details>

### 软件工程的独特之处：开源与从业者会议

**Speaker B**: 你是如何看待软件工程师往往会与使用软件的终端客户进行互动的？在其他工程领域中，这也同样存在吗——作为一名工程师，你会与客户交流、了解你的客户，还是根本不了解他们？这些相似或不同之处你是如何看待的？

<details>
<summary>Original English</summary>

And how did you see the similarities or differences of software engineers for example often interact with customers with end users who use the software in other engineering fields is this also a thing where as an engineer you will talk or know your customer or just not knowing them at all.

</details>

**Speaker A**: 我认为这取决于具体情况，因为我交谈过的不同领域的工程师有不同的经历。有些人说他们觉得有了软件，他们感觉离客户近得多了，而另一些人则说他们感觉离得远得多了。所以我认为这很难一概而论。

<details>
<summary>Original English</summary>

I think it depends because different engineers I talk to had different experiences. Some said that they felt that with software they felt much closer to the customer, with other ones they said they felt much further. So I think it's hard to really tell there.

</details>

**Speaker B**: 我清楚地记得你指出过的一个不同之处，那是一个非常大的差异，它几乎让软件工程具有了更高的地位，或者说成为了一个更好的领域，那就是开源——开源的概念。

<details>
<summary>Original English</summary>

One thing I remember vividly is a difference that you pointed out which was very different and almost makes software engineering a bit higher status or a better place is open source the concept of open source.

</details>

**Speaker A**: 是的。所以与任何其他领域相比，这似乎是软件领域非常特别的一点。比如，我现在能和你一起在这里（匈牙利）的原因，是因为我要在 Craft 大会上发表演讲，对吧？

<details>
<summary>Original English</summary>

Yes. So that is one thing that seems very special about software versus any other field. Like the reason I'm here in Hungary right now with you is because I'm going to be speaking at Craft conference, right?

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

Yeah.

</details>

**Speaker A**: 大多数其他工程领域，或者实际上人类劳动的任何其他领域，都只有两种类型的会议。一种是讨论研究的学术会议，另一种是供应商试图向公司推销产品的贸易展览会。
软件在这方面有点独特，它拥有第三种类型的会议——从业者会议（practitioner conference），我们在这里聚会只是为了在我们的工作中变得更优秀。我们也是真正唯一一个非常侧重于开源，并让我们的知识免费获取的领域。
对于任何一门语言，你大概都可以在网上找到如何学习它的方法，对吧？你不需要去买书。你不需要去跟供应商交流才能学习它。这是关于软件的非常特别的地方。

<details>
<summary>Original English</summary>

Most other fields of engineering or in fact any other field of human labor has two kinds of conferences. Academic conferences where they talk about research and trade shows where vendors try to sell to companies. Software is kind of unique in having the third kind of the practitioner conference where we are just meeting to get better at what we do. We also are really the only kind to really focus heavily on open source and making our knowledge freely available for any language. You can probably find out how to learn a language online, right? You don't have to buy a book. You don't have to talk to the vendor to learn it. That's something really special about software.

</details>

**Speaker B**: 即使是一些最大的公司，我想到了像 Uber 或 Airbnb，这些都是千亿美元级别的公司，它们也不会刻意隐瞒他们是如何构建那些软件的。Uber 会公开发表文章，并就在所有这些人中使用的应用程序发表演讲，讲述他们确切是如何构建它的，或者至少是大致的过程。
我在想为什么这在软件中变得独一无二，而在工程的其他领域却不是这样。其他工程领域在这上面有什么损失吗？或者我们是做了什么才达到现在的状态的？

<details>
<summary>Original English</summary>

Even some of the largest companies, I think of like an Uber or Airbnb, these are hundred billion dollar companies, they will not particularly hide how they built that piece of software. Uber publishes and does talks about their app that is used by all these people how exactly they built it or approximately. I wonder why this became unique in software and in not the rest of engineering, what does the rest of engineering have to lose with it or what did we do to get here.

</details>

**Speaker A**: 接下来我要进入猜测的层面了，这不是我能以完全权威的身份谈论的事情。但我的猜测是，一部分原因是文化，而另一部分原因是我们所工作的材料和我们的产品是相同的，对吧？
我们是使用软件来编写软件，而不是像使用工具和车床来制造东西，或者使用软件来设计电路那样。我个人认为，这种相似性，基本上就是我们在两端使用相同的材料，使得我们能够更容易地去谈论开源之类的事情。

<details>
<summary>Original English</summary>

I'm going to switch to speculation for a second, this isn't something that I could really speak on with full authority. But my guess is that part of it is cultural, but another part of it is that the material we work with is the same as our product, right? We are using software to write software versus using tools and lathes to build things or using software to design circuits. And I personally think that that similarity, basically that we are using the same materials on both ends is what makes it so much easier for us to talk about things like open source.

</details>

**Speaker B**: 很有趣。我很喜欢这种思考方式，即考察每种工程中所使用的材料，以及我们的材料就是软件本身。当然，这与硬件工程有所不同，我们也知道那肯定是不一样的，但在硬件工程和软件工程师之间，关于他们共享了多少、我们对他们了解多少等方面，已经存在着一道鸿沟。
我在想，我有一些做 3D 打印的朋友，看起来——我还没深入研究过这个——但似乎他们也有一个非常开放的空间，可以自由地分享东西。我在想这是否也是同样的原因，因为它很容易分享，而且因为那里的价值单位是图纸，这是否也在某种程度上导致了相同的结果。我也在想黑客文化是否也在其中发挥了作用。

<details>
<summary>Original English</summary>

Interesting. I like this thinking of materials used in each engineering and how our material is software itself. Of course, it's hardware engineering and we know that's a bit different of course, but already there's a divide between hardware engineering and software engineers and how much they share, how much we know about them and so on. I kind of wonder, I've got some friends who do 3D printing and it seems like, and I haven't looked into this, but it seems like they also have a very open space of sharing things freely and I wonder if that's the same because it is so easy to share and because the unit of value is the schematic there if that kind of leads to the same thing. I also wonder if hacker culture might play a thing.

</details>

<!-- chunk 3/12 -->

### 软件工程与其他工程的对比

**Guest**: 在一些能够轻松负担得起启动成本的领域，比如业余无线电（虽然它不算严格意义上的工程学），那里有一个繁荣的社区，人们会分享设置、探讨问题、交流小型电子设备等等。但追根溯源，软件行业始于大约70年代，当它变得相对廉价、任何人都能买得起电脑，或许还有互联网的出现。当然，这些也只是我的推测。

<details>
<summary>Original English</summary>

**Guest**: in places where it's easy enough to afford to get started on a thing for example ham radios which is not engineering but there's a thriving community where they share the setup the things they talk with each other small electronics might be and then but ultimately software started in the what 70s when it was affordable anyone could buy a computer maybe the internet I'm also just speculating

</details>

**Host**: 是的，这绝对是一个值得跟进的好项目。

<details>
<summary>Original English</summary>

**Host**: yeah definitely something worth doing a follow-up project on Right.

</details>

**Guest**: 嘛，毕竟你已经在这个项目上花了大量的时间了。

<details>
<summary>Original English</summary>

**Guest**: Well, you've already spent a bunch of time on it.

</details>

**Host**: 快别再给我挖那么多坑了。我的生活里已经有太多兔子洞要钻了。

<details>
<summary>Original English</summary>

**Host**: Don't give me so many rabbit holes. There's already too many rabbit holes in my life.

</details>

**Host**: 你提到的另一点是版本控制（Version Control），在软件行业中，我们往往觉得它是理所当然的。我们几乎到处都在用版本控制。而且你还说过，这在绝大多数工程领域中是极其罕见的。

<details>
<summary>Original English</summary>

**Host**: One more thing that you brought up is version control and the fact that in software we just take it for granted. We have version control everywhere. And you said that this is super unique across most of engineering.

</details>

**Guest**: 没错。我为此采访了大概20个人。我想这20个人全都不约而同地提到了版本控制，并表示他们多么希望自己以前的工程领域也能有这套系统。

<details>
<summary>Original English</summary>

**Guest**: Yeah. I interviewed like 20 people on this. I think all 20 mentioned version control as a thing they wish they had in their old field.

</details>

**Host**: 哇哦。

<details>
<summary>Original English</summary>

**Host**: Wow.

</details>

**Guest**: 是的。不过澄清一下，其他领域确实也有类似于“变更管理（Change Management）”之类的东西，但我认为我们所拥有的版本控制系统，比他们所拥有的任何东西都要复杂先进得多。这感觉就像是拿一辆现代汽车去和福特T型车作比较。

<details>
<summary>Original English</summary>

**Guest**: Yeah. Now to be clear, they do have things like change management in like other fields, but I think version control as we have it is so much more sophisticated than anything they have. It's like comparing like a modern car to a model T.

</details>

**Host**: 既然你现在已经和这么多人交谈过，并且深入了解了诸如主动收费文化（active charging cultures）等不同的工程文化，你觉得我们能从他们身上学到些什么呢？或者说，这里面有没有什么能为我们提供启发的灵感？

<details>
<summary>Original English</summary>

**Host**: What do you think there are things that now having talked with so many people and learned about the different engineering cultures like active charging cultures? What could we learn from them? What are some kind of inspiration that might be useful here or there?

</details>

**Guest**: 哎呀，这就比较难回答了。因为尽管所有受访者都提到了“开放性”和“版本控制”这两点，但当我问及“我们可以从你们过去的领域学到什么”时，我得到的答案却非常零散。我大概梳理出了两点：第一，虽然我们在迭代方面比其他领域做得好得多，但我们在计划（Planning）环节却逊色不少。就像我们在迭代之前依然需要做一些规划，而我们之所以不如其他领域那么擅长规划，部分原因是我们常常能侥幸逃避繁重的规划工作。但如果我们能够将两者融合，我们其实可以变得比现在更好。这也算是在为我所从事的工作打个广告吧。另一件让我觉得更有趣、甚至有些震惊的事情是，虽然我们在开源分享各种材料方面做得更好，但在系统性地汇编、整理我们具体工作内容的信息方面，我们似乎要差劲得多。这话听起来可能有些含糊，但我反复提及的一个例子是，我采访过的一位工程师谈到了他最喜欢的两本书：一本是《设计心理学（The Design of Everyday Things）》，他建议每位工程师都去读一读；另一本是《卡扣装配手册（The Snap Fit Handbook）》。你了解过卡扣装配吗？

<details>
<summary>Original English</summary>

**Guest**: Yeah, this is a harder question because while everybody I talked to mentioned those two things of openness and version control, I got a much more scattering set of answers when talking to people about what we could learn from their old fields. The two things I kind of gleaned out is that one, while we are a lot better at iterating than other fields, we're worse at the planning part. Like we still need to do some kind of planning before we iterate and we just aren't as good as those other fields in part because we can get away with not doing it as much. But we could get some sort of fusion of the two and get even better than we currently are. Which, hey, plug for what I do. The other thing that I think is more interesting in terms of being a bit more shocking to me is that while we're better at being open about all of our materials, we seem to be worse at compiling information about the specifics of our job. And that's a bit loosey goosey, but the example I keep coming back to is that one of the engineers I talked about two favorite books. the design of everyday things which he recommends every engineer read and the snap fit handbook. Are you familiar with snap fits?

</details>

**Host**: 不太了解。

<details>
<summary>Original English</summary>

**Host**: No.

</details>

**Guest**: 我正四下张望，看这里有没有实物能直接展示给你看。不过，你应该知道电视遥控器吧，它们背面通常有个能按进去的“小按扣”，用来固定电池盖的。

<details>
<summary>Original English</summary>

**Guest**: Looking around here to see if there's like one if I could just show it. But like you know like how remotes they have that little clicky thing in the back that you use that hold the battery in.

</details>

**Host**: 知道。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Guest**: 那个东西就是所谓的“卡扣”。[清了清嗓子] 它是一种物理装置，能通过“咔哒”一声卡入另一个部件中，从而将两者固定在一起使用。这可是一本足足有500页厚的专业书，专门详细讲解卡扣的原理、工程设计、合适的形状、材质等等。像这种对工程材料信息的系统汇编和梳理，正是其他领域在做而我们却缺失的。换作是在软件领域，类似的情况就等同于有一本厚达500页、专门讲解“如何对API进行版本控制”的书。

<details>
<summary>Original English</summary>

**Guest**: That's a snap fit. [clears throat] It is a physical device that basically clicks into another device to keep them used. And this was a 500page book all about snapets, their engineering, appropriate shapes, materials, etc. And that kind of compiling of information about the materials is something other fields do that we don't do. An analogy that I would think of in software would be something like a 500page book on how to version an API.

</details>

**Host**: 我们肯定都非常需要那样一本书。

<details>
<summary>Original English</summary>

**Host**: We could all use that.

</details>

**Guest**: 是的，我们确实很需要。

<details>
<summary>Original English</summary>

**Guest**: Yes, we could.

</details>

**Host**: 但现实中我们并没有。

<details>
<summary>Original English</summary>

**Host**: And and we don't have it.

</details>

**Guest**: 我们可以从传统工程学那里学到这点。我们本应该拥有这些。

<details>
<summary>Original English</summary>

**Guest**: We could learn it from engineering. We should have that.

</details>

### 程序员究竟算不算工程师？

**Host**: 你当初启动这个项目时，探讨的核心问题是“我们真的是工程师吗？”。而在整个系列接近尾声时，尽管你当时并没有直说，但你个人的倾向似乎是“我们大概不算”。你提到自己仍然不太确定该如何回答这个问题。那已经是五年前的事了。这么多年过去了，你现在的倾向是什么？我们究竟算不算真正的工程师？

<details>
<summary>Original English</summary>

**Host**: You started this project asking are we really engineers? And your personal inclination, which you didn't say at the time, was that we're probably not in the closing of this series. You said you're still a bit unsure of how to answer it. This was 5 years ago. this many years later, what is your inclination? Are we actually engineers?

</details>

**Guest**: 我想是的。我认为这个项目，以及围绕它所进行的写作和思考，让我坚定地从“我们绝对不是”的阵营，转变到了“我们大概是”的阵营。但我必须声明一个大前提：我写这些文章的时候，大语言模型（LLM）还没有火起来。这些模型的出现很可能已经彻底改变了我们认知的软件领域，而且大概率也连带着改变了其他分支领域，只是我还不清楚具体变成了什么样。所以这也许已经打破了两个领域之间的原有平衡。但就目前而言，如果抛开LLM及其带来的改变不谈，基于我的那些采访来看，我们现在所做的事情，与那些传统工程领域的人们所做的事情非常相似。

<details>
<summary>Original English</summary>

**Guest**: I think so. I think this project and writing about and thinking about it has firmly moved me from the camp of we are definitely not to we probably are. I do want to caveat that I wrote this before LLM's thing and this has probably changed our field as we know it and it's probably also changed those other branches and I don't know how. So that could have changed the calculus between two spaces. But as of now, I think excluding LLMs and how they're changing things, what we do now is very similar to what those people in those other fields did according to my interviews.

</details>

### 形式化方法与验证

**Host**: 这真的是一个非常酷的项目，而且至今读起来依然非常精彩。我也会把链接放在下方的节目简介中，强烈推荐大家去深入了解一下。那么接下来，让我们聊聊形式化方法（Formal Methods）。你是如何接触到这门学问的？另外，对于我们这些不太精通此道的人来说，形式化方法到底是什么？

<details>
<summary>Original English</summary>

**Host**: It's it's such a cool project and it's still a very good read. Uh I'll also link it in show notes below. I I do recommend going into it. So let's talk about formal methods. How did you get exposed to them? And for those of us who are not deep into it, what are they?

</details>

**Guest**: 我给你举个例子，假设有一个名为 `max` 的函数，对吧？这个函数的功能是，输入一个列表，返回其中最大的数字。如果是你，你会如何为它编写测试用例呢？

<details>
<summary>Original English</summary>

**Guest**: I'm going to give you a function max, right? Which should given a list return the largest number. What would be a test you'd write for that?

</details>

**Host**: 我会写这样一个测试：传入一个只有两个元素的列表，验证它是否返回了我已知的那一个较大的数。我还会给它传入一个非常长的列表，尝试做一些压力测试。我还可能会传入一个包含相同或相似数字的列表，并努力构想一些边界情况（Edge Cases）。我大概会写个五个测试用例，想想整型溢出的问题，或者尝试一些容易出错的刁钻情况。如果我感觉干劲十足的话，也许会写到八个，然后就大功告成了。

<details>
<summary>Original English</summary>

**Host**: I'd write a test that I do a list of like two items. It returns the the largest one that I know. I give a very long list. I I try to stress test it. I I I give a list where I give like similar numbers. I try to come up with some edge cases. I'll I'll probably write like five tests, try to think about integer overflows, potentially try some tricky, but maybe I'll take it to maybe eight if I'm feeling super ambitious and then I'm done.

</details>

**Guest**: 好的。那么当你执行其中任意一个测试时，你是怎么判断什么是“正确答案”的呢？

<details>
<summary>Original English</summary>

**Guest**: Okay. So, when we take one of those tests, how do you know what the right answer is supposed to be?

</details>

**Host**: 我自然就是知道，因为我学过数学嘛。在学校里，我学过分辨哪个数字更大。说实话，我只要看一眼就能判断出来。这已经成为了我潜意识里根深蒂固的知识。这感觉是非常基础的常识，我甚至都不需要特意去解释。

<details>
<summary>Original English</summary>

**Host**: I just know because I have a I I learned math. So, uh in school I I know which which number is bigger. Honestly, I I look at it I have this I guess ingrained knowledge. It feels very basic knowledge that I don't even have to explain.

</details>

**Guest**: 对吧？你拥有一种根深蒂固、无需解释的知识储备，这就使得你一看到求 2 和 3 的最大值，就知道结果是 3。这就很有意思了。你的大脑中存在某种隐式的机制，看到这些输入就能明白这个函数理应做些什么。而在我使用形式化方法时，第一步要问的就是：我们能否将这种隐式的知识转化为显式的表达？我们能否弄清楚一个函数实际上到底该干什么，并且以一种能够展示给任何人看的方式将其清晰地写下来？所以，在这个过程中，我大概会这么说：一个列表的最大值，它是该列表中的某一个元素，并且满足这样一个条件：列表中的其他任何元素都小于该元素。这就是我们能够严格、形式化地定义“列表最大值”的一种方式。这就是第一部分：学着去审视函数，并且能够说出“好吧，我知道它是干什么的。那我该如何用清晰无歧义的方式，向别人解释它的作用？”。接下来的第二步是，要明白你所写的每一个测试用例，本质上都是在该定义某个侧面的体现，即：它是一个列表中的元素，同时也是列表中的那个“使得其他所有元素都比它小”的数字。既然我们有了这套规范（Specification），那么用什么方式才能最好地证明我们的函数确实满足了这套规范呢？编写测试（Tests）是其中一种方式。测试本质上就是提取出单个的具体值，并展示它们是如何符合这个规范构件的。使用类型系统（Types）是另一种方式。我们可以以此宣称，比如说：“好吧，在任何一种情况下，我们的输入都是一个由元素组成的列表，而输出都是一个单一的元素。”于是，我们就必须确保每一次调用它时，这个命题都是成立的。所以简而言之，找出事物的本质属性及其真实作用的过程，就是“确立规范（Specification）”；而展示代码函数与该规范相吻合的过程，则被称为“验证（Verification）”。而形式化方法所探究的是：我们能否利用数学手段来证明该代码是行之有效的——不仅对你所想到的那几个测试用例有效，而是对你能传入的所有可能的列表都有效。这就需要通过数学证明（Proof）来完成。即提出一套数学上的论证过程，来证明这段代码完美契合了这份规范说明。

<details>
<summary>Original English</summary>

**Guest**: Right? You have some ingrained knowledge that you don't have to explain such that you can look at say the max of two and three and know it's three. Right? That's interesting. There's some sort of implicit mechanism in your brain that can see that and know what the function is supposed to do. Step one of what I do with methods is asking can we take that implicit knowledge and make it explicit? Can we figure out what a function is supposed to actually be doing and write that down in a way that can be shown to anybody. So I would basically in this process say like the max of a list is an element that is in the list such that every other element is smaller than that element. That is a way that we can formally say what the maximum of list is. So that's part one just learning how to look at functions and say like okay I know what this is doing. How would I explain what this is doing in a way that is clear and unambiguous? Then step two is asking every single test you've written is basically some facet of it is an element of the list and it is the number in that list such that every other number in the list is smaller than it. Now that we have that what's the best way to show that our function actually satisfies that specification. Tests are one way. Those are basically taking individual values and showing how those component specification. Types are another way. we could basically say like okay in every single case we are putting in a list of elements and we're getting out a single element. So we have to make sure that every time we call it that's what's true. So basically the coming up with the the properties of the thing like what it actually is is the specification of it and then showing the function matches that specification is the verification and what f methods ask is can we use mathematics to show that it works not just for the cases that you asked for but every single possible list you pass in. And that is done through proof. Coming up with some sort of mathematical argument that this code matches this spec.

</details>

**Host**: 说到数学证明，这又让我想起了大学时光。我依然记得当年我们去推导证明一个数学等式的那些数学证明题。你只能做一些严格的恒等变换。你必须清楚地知道有哪些操作是被允许的。有时候你也能引入一些巧妙的技巧，但这些技巧依然要在你那个严格的“可用操作列表”范围之内。每一次，你懂的，你通常都是从一个极其复杂的方程式开始，然后不断地对其进行变形、转换。到了最后，你把它化简或者变形到了一个连外行也能一眼看懂的平凡状态（Trivial）。这就是我们当年做证明题的方式之一。形式化方法在某种程度上，做的是不是也是一样的事情？

<details>
<summary>Original English</summary>

**Host**: And then in proof, again from university, I still remember the the maths proofs where we would proof an an equation. You do rigid transformations. You know what you're allowed to do. Sometimes you can bring in tricks, but those tricks are also inside of your rigid list. And every time, you know, you typically start from a complicated equation and you keep changing it. And in the end you you shape it in a way that it's now trivial or you transform. Those are one of the proofs we do. Is is this what formal methods also does to some extent?

</details>

**Guest**: 是的。但你得知道如何去把两样东西给……

<details>
<summary>Original English</summary>

**Guest**: Yes. But you know how to basically add two

</details>

<!-- chunk 4/12 -->

### 形式化方法的应用与挑战

**Speaker A**：...手动计算正切值，对吧？你会手算，还是直接用计算器？

<details>
<summary>Original English</summary>

**Speaker A**: tangent numbers by hand, right? Do you do that by hand or do you just use a calculator?

</details>

**Speaker B**：我现在用计算器。如果足够简单，我可能会用大脑当计算器。否则，我直接在计算器上按。

<details>
<summary>Original English</summary>

**Speaker B**: I now use a calculator. If it's easy enough, it might I use my brain as a calculator. Otherwise, I just punch it into the calculator.

</details>

**Speaker A**：是的。同样的，在数学变换中，许多专业的方法，虽然你可以手动完成，但在工业界通常使用被称为定理证明器的工具，这些工具基本上自动化了这一过程的大部分内容。所以你不需要亲自进行每一次单一的变换。例如，你可以说，好吧，我们在开始时有这些条件为真，我希望在结束时这个条件为真，你能计算出来吗？它的回答可能会是：是的，我能证明这些条件匹配；或者，不行，我还需要一点帮助。然后你会说，好吧，在这一点上我还要让你知道这个条件也是为真的；接着它说，好的，我能验证这是真的，这有助于我得出最终结果。你就这样不断进行下去，直到你提供了足够的信息，让计算机能为你完成证明。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So similarly a lot of pro methods that math of transformation while you can do it by hand with like what's called a theorem provert often in industry that it's being done for the most part with tools that basically automate huge parts of this process. So you don't have to do every single transformation yourself. You can for example say okay we have these things are true at the beginning I want this to be true at the end and can you figure this out and it'll be like either yes I can prove these things match or no I need a little bit more help. And you say like okay at this point I'm going to also let you know that this is true and like okay I can verify that's true and it helps me get to the end and you just keep doing that until you actually have enough that the computer can do the proof for you.

</details>

**Speaker B**：是的。关于形式化方法，我觉得这听起来都很符合逻辑，在实践中应该很容易遵循。那么科技行业实际使用了哪些技术、工具或手段来证明某些代码确实有效呢？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So with formal methods this I mean this sounds all logical I think is easy easy to follow in practice. What techniques technologies tools does the industry use the tech industry use to actually prove that you know some some stuff works?

</details>

**Speaker A**：要回答这个问题，我们需要先问另一个问题。为什么这不是所有事情都在用的方法呢？

<details>
<summary>Original English</summary>

**Speaker A**: To get to that we need to ask another question. Why isn't this being done for everything?

</details>

**Speaker B**：好吧，那就让我来问这个问题。这是个好问题。是的，这一切听起来都很合理。如果不必写那五到八个测试用例当然很好。而且我知道这些测试用例可能并没有覆盖所有的边缘情况。我也遇到过那种情况：漏掉了某个测试用例，而且我并没有进行形式化证明。我当时觉得，好吧，是我漏了一个测试用例，我的错。抱歉。让我把那个测试用例加上去。现在我有了九个测试用例，然后我觉得自己做得很棒。那为什么我们不对所有东西都进行形式化测试呢？相比于在一个列表中寻找最大数字，我们为什么不尝试在一个目录中找到行数最多的那个文件呢？

<details>
<summary>Original English</summary>

**Speaker B**: Okay, let let me ask that question. That's a good question. Yeah, this all sounds sounds sensible. It would be nice to not have to write out those five or eight tests. And I know that those tests might not cover all edge cases. Been there, done that where you miss and I I I didn't think that I didn't do a formal proof. I thought like, well, I missed a test case. That's on me. Sorry. Let me put in that that test case. I now have nine tests and now I go and think I did a great job. Why are we not doing formal testing for everything? Instead of finding the largest number in a list, why don't we try to find the file in a directory that has the most lines in it?

</details>

**Speaker A**：好吧，现在我设想以一种命令式风格编写一个程序，通过一个 for 循环遍历列表。对于每一个文件，我列出它的行有多长。我计算行数。我无法轻易断定。

<details>
<summary>Original English</summary>

**Speaker A**: Well, now I'm thinking of writing a program that in kind of an imperative style, it goes through a four list. Each each file, I list how long the the lines are. I count the lines. I cannot tell easily.

</details>

**Speaker B**：好的。我们讨论的是 ASCII 换行符还是 UTF 换行符？如果其中一个文件你没有读取权限会发生什么？你应该直接忽略它，还是应该说，嘿，我的证明、我的函数可能是错的？

<details>
<summary>Original English</summary>

**Speaker B**: Okay. Are we talking about asky lines or UTF at new lines? What happens if one of the files you don't have the file permissions to read it? Should you basically ignore it or should you say like, hey, my proof my my um function might be wrong.

</details>

**Speaker A**：你现在是在尝试考虑，如果其中一个文件是指向另一个文件的快捷方式怎么办？如果它实际上是一个目录怎么办？

<details>
<summary>Original English</summary>

**Speaker A**: You're now trying to What if one of the files is a shortcut to another file? What if it's actually directory?

</details>

**Speaker B**：该死，你现在是在模拟一个二进制文件。

<details>
<summary>Original English</summary>

**Speaker B**: Damn, you're now simulating a binary.

</details>

**Speaker A**：你现在是在模拟真实世界。

<details>
<summary>Original English</summary>

**Speaker A**: You're now simulating real world.

</details>

**Speaker B**：是的。我们遇到的问题就在于此：当你开始讨论大多数有趣的领域问题时，你必须引入非常多的上下文，以至于即便只是写出这个函数应该做什么也会成为一场噩梦。你编写的那个在 99% 的时间里都能正确运行的命令式程序，在几乎所有情况下可能都够用了。而如果你想要一个在 100% 的情况下都能起作用的程序，你就必须弄清楚，好吧，我们使用的是什么文件系统？你必须弄清楚所有细节。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. And that's the problem we have is that when you start talking about like most interesting domain problems, you have to pull in so much context that basically even writing what the function is supposed to do becomes a nightmare. The imperative program you write that will get correct 99% of the time is probably good enough to use in almost all cases. And if you want something that works 100% of the cases, you've got to figure out, okay, what file system are we using? You have to figure out everything.

</details>

**Speaker A**：是的。这就是为什么它[清嗓子]没有被广泛采用的原因。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And that's why it's [clears throat] not done

</details>

**Speaker B**：基本上这会非常不切实际。对于 99% 的人来说，这会是：你为什么要浪费你的时间？这就像是过早优化，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: and basic it would just not be practical. It would be for the for 99% of the people would be why are you wasting your it's like premature optimization right?

</details>

**Speaker A**：是的，特别是正如你所说，写 10 个测试用例可能就能满足你大部分的需求。你在行业某些领域中看到过哪些正在使用的实用技术？即使我假设这些技术会有些笨重，因为听起来确实很笨重。但使用这些笨重技术所带来的投资回报可能是值得的，以至于行业内的团队如今正在使用它们。在这里，我们基本上可以将其分解为这一领域的不同部分。所以，第一部分是看那些确实需要达到这种验证程度的东西。这里常用的词是核武器和 NASA，比如核电站和 NASA；但我可以基于第一手经验告诉你，核电站并不关心这套东西。他们实际上只要有彻底的测试就完全没问题了。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah especially when as you say writing 10 tests might get you most of what you need. What are practical technologies that you have seen used in some part of the industry that even though they will I'm assuming will be somewhat heavyweight because it sounds like pretty heavyweight. It might be the return the return of investment of using this heavyweight stuff is worth it that teams in industry are using it today right and here we can basically start to break this down to different parts of the landscape. So, one part is to look at the stuff that actually does need to be verified to that degree. And the usual term here is nukes and NASA like nuclear power plants and like um NASA, but I can tell you with firsthand experience, nuclear power plants do not care about this stuff. They're actually just fine with with with thorough testing.

</details>

**Speaker B**：好的。好的。那么，第二类就像是程序的非常核心的部分，他们需要程序的某个特定部分得到真正的验证，而其余部分则可以使用非形式化的方法。这通常是一些类似数据库的小部分，或者是密码学原语。我相信 Firefox 中的 HTTPS 栈是作为一个叫 Project Everest 项目的一部分被验证过的，但我可能在一些细节上记错了。

<details>
<summary>Original English</summary>

**Speaker B**: Okay. Okay. So, then category two is like really focused cores of programs where they need like one specific part of the program to be like really verified and the rest of it they can use informal methods. And this is usually things that are like um small parts of databases or like cryptographic primitives. I believe that the HTTPS stack in Firefox is verified as part of something called Project Everest, but I might be getting some details of those wrong.

</details>

**Speaker A**：操作系统的内核会属于这一类吗？或者仅仅是内核中非常关键的特定部分，比如内存分配之类？

<details>
<summary>Original English</summary>

**Speaker A**: Would an operating system kernel fall into this or maybe just a very key specific part of a kernel like memory allocation or something like that?

</details>

**Speaker B**：是的，操作系统内核的部分是很好的应用场景。我能想到的几个例子是，我相信微软在驱动程序加载方面对其 Vista 内核的部分进行了一些规范化验证。著名的例子是有一个叫 seL4 的操作系统，它已经在一种叫做 Isabelle 的语言中进行了端到端的验证。它是一个微内核。它非常小。它主要用于汽车和军事应用，但它是一个完全经验证的操作系统，这里的限制条件是它符合规范。也就是说，它可能依然会做错事，但是在你规定它必须做对的那些事情上，在正确的情况下它确实会把那些特定事情做对。最后一个类别是我所从事的工作，也就是在问：如果我们不去验证整个真实世界的系统（正如我们刚才讨论的，那将是一场噩梦），而是创建该系统的一个简化版本并对其进行验证，会怎么样？那么实际的系统可能仍会存在 bug，但我们可以解决抽象模型中的问题，这样我们实际上就不会将这些问题带入到真实的系统中。所以那是一个你在规划系统，并希望对其进行压力测试以解决问题的主题。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, parts of um operating system kernel are good uses for this. Um, a couple examples I can think of is I believe Microsoft used some polarification of parts of their beasta kernel for the driver loading. Famously there was an operating system called4 that has been endto-end verified in a language called Isabel. It's a micro kernel. It's very small. It's mostly used for um automotive and military applications but it is a fully verified operating system with a caveat meaning that it's matching the specification. So it might do the wrong thing but of the things that you specify that it has to do right it will do those specific things right in the right circumstances. The last category is the kind I work in which is asking okay what if instead of verifying the entire real world system which is a nightmare as we just discussed. We create a simplified version of the system and verify that then the actual system might still have bugs but we can iron out the issues in the abstraction such that we don't actually build them in the real system. And and so that that's a topic where you are planning a system and you want to stress test it to iron out.

</details>

**Speaker A**：是的。对计划进行压力测试。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Stress test the plan.

</details>

**Speaker B**：这些计划大概会是哪种类型的？是在规划类似于数据库，或者是某种分布式系统吗？

<details>
<summary>Original English</summary>

**Speaker B**: What what kinds of plans would these be roughly? Is is it planning like again database or or some sort of distributed system?

</details>

**Speaker A**：在我的工作中，大部分是科技公司的数据库和分布式系统，但我也做过一些其他有趣的项目。比如有一次我的工作涉及对某个设备内核的固件进行形式化验证。说实话，我参与过的最酷的项目之一是验证列车系统的应答器，以确保它们不会给经过这些应答器的列车带来麻烦。那非常有趣。我们在那里面还发现了一个非常古老的 bug。那还挺让人兴奋的。

<details>
<summary>Original English</summary>

**Speaker A**: In my work, it's mostly been um databases and distributed systems for technology companies, but I've had some other like interesting gigs. Like I've had one gig that was involving formally verifying um firmware of a device kernel. And one honestly, one of the coolest projects I ever worked on was um verifying the transponders of a train system to make sure that they wouldn't cause problems to trains going over those transponders. That was a lot of fun. We found a really old bug in that one, too. That was kind of exciting.

</details>

### 赞助商插播：WorkOS 与 Turbopuffer

**Speaker B**：这一整集都围绕着一个问题展开，而随着 AI 编写出更多的代码，这个问题只会变得越来越重要：你如何知道代码是否正确？对于代码库的某些部分，你绝对不希望让 AI 模型去瞎猜，其中身份验证（Auth）就排在这个列表的首位。这也是我必须要提到我们本季赞助商 WorkOS 的原因。如果你正在构建任何 SaaS 产品，特别是一款 AI 产品，你会需要用于应用程序和代理的身份验证。在这一层，“差不多就行”是远远不够的。所以不要让这一层被 AI 随意发挥。WorkOS 为你提供了经过验证的 SSO、SCIM 和细粒度授权实现，专为代理的操作方式而构建，而且以一种对代理而言易于集成、同时又值得你信任的实现方式来提供。去 workos.com 看看吧。我同时也想谈谈我们本季的另一位赞助商 Turbopuffer。但这次我不想去谈论他们是如何在对象存储之上构建起一个快速、便宜且极具扩展性的搜索引擎的。相反，我想谈谈他们的团队。我在 AI 工程师世界博览会的舞台上采访了他们的联合创始人兼 CEO Simon，还与他们的团队在线下亲自相处了几天。这里有几件我了解到关于他们的趣事。这家公司是全员远程办公的，但感觉却非常紧密相连。他们有一种以 Slack 为先的文化。例如，他们所有的客户都有专属的 Slack 频道，工程师们都在这些频道里，能看到来自客户的反馈，且经常为他们修复 bug。团队每年至少会在年度峰会上聚齐两次，并且每个月还会举办好几次炉边会谈。

<details>
<summary>Original English</summary>

**Speaker B**: This whole episode is about a question that only gets more important as AI writes more of your code. How do you know if it's correct? And for some parts of a codebase, you really don't want an AI model to be taking guesses at O is on top of that list. And this is where I need to mention our season sponsor, work OS. If you're building any SAS, especially an AI product, you'll need O for apps and agents. This is the layer where close enough is just not good enough. So don't [snorts] let this layer get improvised by AI. Worker gives you the proven implementation SSO skim and fine grid authorization built for how agents operate and in a way that's easy for them to integrate with an implementation that you can trust. Check it out at work.com. I also want to talk about our season sponsor Turbopuffer. But this time I don't want to talk about how they are fast, cheap, and extremely scalable search engine built on object storage. Instead I'd like to talk about their team. I interviewed Simon, the co-founder and CEO, on stage at AIGO's World Fair and also hung out with their team for a few days in person. Here's a few the interesting things I learned about them. The company is full remote yet feels pretty connected. They have a Slack first culture. For example, all of their customers have a dedicated Slack channel and engineers are in these channels seeing feedback from these customers, often fixing their bugs. The team gets together for annual summits at least twice a year and campfires form several times a month anytime

</details>

<!-- chunk 5/12 -->

### Turbopuffer 的务实工程文化与 TLA+ 演示

**Host**: 多名远程工作的员工聚集在同一个城市。Simon 将他们的工程文化描述为“硬核且异想天开”。他们专注于解决难题，但同时也努力寻找乐趣。他们构建的 The Pragmatic Engineer 登陆页面就是一个很好的例子。我们同意制作一个自定义登陆页面，然后他们的团队决定制作一个很酷的、能随鼠标移动产生动画效果的 Logo。另一个有趣的地方是他们的团队构成。目前在公司工作的人几乎都有 10 到 15 年的经验。对于一家初创公司来说，他们是一支经验异乎寻常丰富的团队。最后，我非常欣赏他们务实的工程哲学。Simon 和团队坚信“简单性能够横向扩展”，这也是对象存储成为 Turbopuffer 唯一依赖项的原因。这个团队会做一些看似愚蠢的事情，比如在对象存储上的单个文件里构建他们的作业队列，因为他们了解核心的原语，并且知道它们是如何扩展的。想要查看那个异想天开的动画，或者如果你正在构建 AI 产品，请访问 turbopuffer.com/pragmatic。说到这里，让我们回到 TLA+ 的工作原理，来看看 Hill 准备的演示。我们能看下演示吗？

<details>
<summary>Original English</summary>

**Host**: several remote employees gather in the same city. Simon describes their engine culture as hardcore and whimsical. They focus on solving difficult problems but also try to have fun. A good example is the pragmatic engineer landing page that they built. We agreed to have a custom landing page and then their team decided to build a cool logo that animates on mouse movement. Another interesting thing is their team composition. Pretty much everyone currently working at the company has 10 15 years of experience. For a startup, they are an unusually seasoned team. Finally, I really appreciate how pragmatic their engineering philosophy is. Simon and the team strongly believe in how simplicity scales and this is a reason that object storage is Turbopuffer's only dependency. The team do seemingly silly things like build their job QE in a single file on object storage because they understand the core primitives and they know how they scale. to check out the whimsical animation or if you're building AI products, head to turbopuffer.com/pragmatic. And with this, let's get back to how TLA Plus works with a demo from Hill. Can we see a demo?

</details>

**Hill**: 好的，没问题。我这里准备了几门语言。嗯，就是我用过的那些。目前，用于这类系统规划的最流行技术是一门叫做 TLA+ 的语言。它是由 Leslie Lamport 发明的，就是那个创造了 Latte（LaTeX）的人，其实就是那个排版语言。

<details>
<summary>Original English</summary>

**Hill**: Okay, sure. So, I've got a couple languages with me. Um, the kinds that I've worked in. So, the most popular technology right now for that kind of planning is this language called TA Plus. It was invented by Leslie Lamport, the same guy who made Latte, the um type setting language actually.

</details>

**Host**: 哦，对。在幕后生成所有 PDF 的其实都是 Latte（LaTeX）。是的，Pet Caesar Latte。

<details>
<summary>Original English</summary>

**Host**: Oh, yeah. All the PDFs behind the scenes are are latte. Yeah, Pet Caesar Latte

</details>

**Hill**: 并且他想要一门能够用来对分布式系统进行建模的语言。所以他基本上创造了这个叫做 TLA+（行为时序逻辑及扩展）的东西。每个人都会问这个名字的由来。你其实不需要知道它的全名，只要知道它叫 TLA+ 就行了。它的作用基本上是表示一个系统的状态机。它能够表示系统可能处于的每一个状态，以及它可能转换到的每一个状态。然后我们可以使用一种暴力的模型检查方法，基本上就是找出每一个初始状态，以及能从这些初始状态演变出来的每一个状态，并检查它们是否具备我们期望的属性。TLA+ 在某些方面是独一无二的，因为它能检查诸如活性（liveness）和精化（refinement）等某些属性，不过我们就不深入探讨这些了。但现在让我们实际看一个演示吧。这是我喜欢用来展示它的演示之一。在这个演示中，我们有一个交易平台的简单模型。平台上的每个人都有一组物品，他们想把这些物品交易给其他人。为了展示这个简化系统，我们设定的方式是：每个物品都被分配给一个人。同时还有一组未处理的报价（offers）。我们将只对发送物品给其他人这一行为进行建模，而不对交换物品进行建模。如果你要提出一个物品的交易，你必须拥有那个物品，然后它基本上会被添加到报价集合中。接着你可以接受一个报价。如果该报价有效，你就把它从报价集合中移除，物品的所有者发生转移。如果你拒绝这个报价，它就直接从集合中被移除。然后我们定义接下来会发生什么。所谓的下一个状态，也就是系统演变的方式之一，是我们选择两个不同的人。这就是代码中 `from dash equals 2` 的含义。再选择一个随机物品，然后你可能会针对那个物品发起报价、接受那个物品的报价（必须是已经存在的报价），或者拒绝一个现有的报价。在下方，我们定义了一个属性：有效的更改意味着如果物品的所有者发生了变化，那一定是因为新所有者接受了前任所有者提出的报价。也就是说，如果物品从你那里到了我这里，一定是因为你把它报价给了我，而我接受了那个报价。最后，我们有一个变更不变量（change invariant），即系统的某种属性，它表明每一次变更都是有效的变更。那么，这里的 Bug 是什么呢？

<details>
<summary>Original English</summary>

**Hill**: and he wanted a language that could be used to model distributed systems. So he basically created this thing called TA plus temporal logic of actions plus everybody always asks about the name. You don't need to know the name just known as TLA plus. And what it does is it basically represents the state machine of a system. Every possible state it can be in and every possible state it can it can transition to. Then we can use a brute force model checking where we basically find every initial state and every state that can evolve from those and check if they have properties. TA plus is unique in some ways because it has certain properties like checking livveness and refinement that we won't get into. But let's actually see a demo right now. So this is one of the demos I like to use to showcase this. And we in this demo we have a simple model of a trading platform. Each person on the platform has a set of items and they want to trade these to other people. The way that we're going to show the simplified system is that each item is assigned to a person. There's also a set of outstanding offers. We're only going to model sending items to people, not swapping items. If you propose an item, you have to own that item and it's basically added to the set of offers. And then you can accept an offer. If that offer is available, you remove it from the set of offers and the owner transfers. If you reject the offer, it's just removed from the set. Then we define what can happen next. A next state as in one of the ways the system can evolve is we pick some two people that are different. That's what this from dash equals 2 means. and some random item and either you propose that item, accept a proposal for that item which must already exist or reject an existing proposal. Below we have a property that a valid change is one where if the owner changes it is because the new person accepted an offer from the old person. So if the item goes from you to me it's because you offered it to me and I accepted that offer. And finally we have a change invariant some property of the system saying every change is a valid change. Now what's the bug in this?

</details>

**Host**: 嗯，首先，这东西有一定的学习曲线。

<details>
<summary>Original English</summary>

**Host**: Well, first of all, this has a learning curve.

</details>

**Hill**: 是的，它确实有学习曲线。这也是为什么它相当小众的原因。我现在可能需要指出，当 Leslie Lamport 在 1994 年发明这个东西时，他主要还是以一个数学家的思维在思考，对吧？所以他运用了他的数学背景，以及就像是学习一个数学家会如何书写那些符号一样。从那以后 30 年过去了，从 1994 年到现在已经 30 年了。许多语言的开发部分借鉴了 TLA+ 的经验教训，使得这些语言对程序员来说更具吸引力。比如你看到的 Quint 和 P 这样的语言，它们看起来更像编程语言，也更容易让人理解。之所以我们很多人最初使用 TLA+，是因为关于这类工作在实际中应用的首个真正备受瞩目的演示，是一篇亚马逊的论文——亚马逊云服务（AWS）在 2014 年使用形式化方法的案例，而他们当时使用的正是 TLA+。所以这就是为什么我们很多人一开始就从它入手了。

<details>
<summary>Original English</summary>

**Hill**: Yes, it has a learning curve. And that's why this is fairly niche. And I should probably point out right now that when Leslie Dumper made this in 1994, he was thinking of it mostly he was a mathematician, right? So he was using his mathematical like background and like learning how a mathematician would write some symbols. In the 30 years since that point it's been 30 years since 1994 already. A lot of languages have been developed in part from the lessons of learn of TA plus that make things a little bit more appealing to programmers. So you have things like Quint and P which are languages that look more like programming languages and are easier for people to gro. The reason a lot of us used TA plus was because like the first really high-profile demonstration of this kind of work in practice was an Amazon paper, the use of formal methods at Amazon Web Services in 2014 and they used TLA plus for this. So that's what a lot of us just have originally started on.

</details>

**Host**: 那么回到这个问题，这个模型在各种关联关系上确实存在一个 Bug，我们该如何找出这个 Bug 是什么呢？系统会帮我们指出来，还是说现在我们需要自己去推敲遗漏了哪种情况？

<details>
<summary>Original English</summary>

**Host**: So going back to this, there is a bug in this one with with with all the associations and how can we how can we figure out what the bug is? Will will the system help tell us or or we now need to think through what case we miss?

</details>

**Hill**: 呃，如果我们必须自己去推敲的话，我们根本就不会用这种难看的语法了，对吧？

<details>
<summary>Original English</summary>

**Hill**: Well, if we had to think through it ourselves, we wouldn't be using this nasty syntax, would we?

</details>

**Host**: 没毛病。

<details>
<summary>Original English</summary>

**Host**: Nope.

</details>

**Hill**: 所以，我所做的就是我还写了一个快速的配置文件，它的意思是：获取一份规范说明，使用 Alice、Bob 和 Carol 这三个人，让他们围绕一根棍子进行交易。然后我告诉系统，确保“变更不变量”这个属性始终成立。

<details>
<summary>Original English</summary>

**Hill**: So, what I've done is I've also written a quick um configuration file saying take a specification, take these three people, Alice, Bob, Carl, and have them trade around a stick. And then I tell it, make sure this property that the change in variant always holds.

</details>

**Host**: 始终成立。现在我只需要运行它。

<details>
<summary>Original English</summary>

**Host**: Always holds. Now I just have to run this.

</details>

**Hill**: 我还让它为你输出状态空间，这样你就可以看看它长什么样。它直接就把错误给我们抛出来了。它说该属性已被违反。它探索了 53 个状态才发现这个错误。它的运行方式是这样的，因为现在屏幕比较小，所以它自动换行了。但如果我来看的话，它大概是这个样子的。本质上错误如下。让我们实际看看能否用一个 `.dot` 文件向你展示这个错误。呃，`biz graph` 不行，我这在说什么呢？所以这只是它生成的状态空间的一个预览。你可以看到它基本上生成了它能发现的所有可能的状态。这还不是完整的状态空间。通常，因为这些状态追踪最终可能会导致状态空间中出现类似于 1 亿个状态的情况。通常这些完整图表不是很有用，主要就是我们有时为了做演示而准备的一个东西。那么，错误如下。Alice、Bob 和 Carol 在系统里，Alice 拥有这根棍子。

<details>
<summary>Original English</summary>

**Hill**: I'm also having it output the state space for you so you can see what that looks like. And it just puts out the error for us. It says the property has been violated. It took 53 states to find it. And the way it works is it's on a small screen so it's being word wrapped. But if I see it kind of looks like this. Essentially the error is as follows. And let's actually see if the error I can show it to you with the um dot file. as um biz graph is not dotiz what am I saying? So this is just um a preview of the state space it's generating. So you can see it's basically generating every possible state it can find. This isn't the whole state space. Usually because these the state traces end up being like 100 million states for like in the state space. Usually these aren't that useful. It's mostly a thing that we have for that we sometimes use for demos. So, the error is as follows. Alice, Bob, and Carol are on the system, and Alice owns the stick.

</details>

**Host**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Yep.

</details>

**Hill**: Alice 向 Bob 提出了一个报价。Bob 现在不在。Alice 厌倦了等待 Bob 回来进行交易，因为她只想赶紧把棍子脱手。于是她向 Carol 提出了报价。Carol 立即接受了。这样一来，棍子就从 Alice 转移到了 Carol 手上。就在这时，Bob 回来了，看到了 Alice 给他的报价，并且心想：“哦，太好了。我想要那根棍子。”他点击了按钮，于是这根棍子现在就变成了 Bob 的了。但这根棍子其实并没有从 Alice 转移给 Bob，而是从 Carol 转移给了 Bob。所以，“如果棍子从 Carol 到了 Bob 手里，那一定是因为 Carol 提出了报价并且 Bob 接受了”这个变更不变量，就被违反了。因此，系统抛出了一个错误。

<details>
<summary>Original English</summary>

**Hill**: Alice makes an offer to Bob. Bob is away. Alice gets tired of waiting for Bob to come back to make the offer because she wants to get rid of her stick. She makes the offer to Carol. Carol immediately accepts. So, the stick transfers from Alice to Carol. Now, Bob comes back, sees the offer from Alice to Bob and goes, "Oh, yeah. I want that stick." Clicks the button, and now the stick becomes Bob's. But it did not transfer from Alice to Bob, it transferred from Carol to Bob. So the change in variant that if the stick went from Carol to Bob, it must be because Carol made an offer that Bob accepted was violated. And therefore the system raises an error.

</details>

**Host**: 那么系统是如何模拟这个过程的呢？它必须模拟出一种状态，也就是 Bob 在等待，或者在一段时间内没有响应，然后后来才做出了响应。

<details>
<summary>Original English</summary>

**Host**: And then how did the system simulate this? It had to simulate a state where Bob was waiting or or didn't respond for a while and responded later.

</details>

**Hill**: 基本上，假设我们处于“Alice 拥有棍子”的初始状态。此时可能会发生两件事，对吧？我们可以向 Bob 提出报价。

<details>
<summary>Original English</summary>

**Hill**: We basically assuming we start in the state of basically Alice owns the stick. There's two possible things that can happen here, right? We have offer Bob.

</details>

**Host**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Yep.

</details>

**Hill**: 然后我们也可以向 Carol 提出报价，对吧？所以这两种情况都会发生，并且它们都是不同的状态。因此，模型检查器会说，好的，我要创建两个新的状态。然后从“向 Bob 报价”这个顶部分支开始，可能会发生三件事。我们可以让 Bob 接受……

<details>
<summary>Original English</summary>

**Hill**: And we have offer Carol, right? So those both happen and those are both distinct states. So the model checker says, okay, I'm going to create two new states. Then from this top one of offer Bob, there's three things that can happen. We can have Bob accept

</details>

**Host**: Bob 拒绝……

<details>
<summary>Original English</summary>

**Host**: Bob reject

</details>

**Hill**: 或者，并发性就在这里体现了——我们可以向 Carol 报价，对吧？

<details>
<summary>Original English</summary>

**Hill**: or and this is where the concurrency comes in. We can do offer Carol, right?

</details>

**Host**: 嗯。

<details>
<summary>Original English</summary>

**Host**: Yep.

</details>

**Host**: 我明白了。

<details>
<summary>Original English</summary>

**Host**: I see.

</details>

**Hill**: 是的。

<details>
<summary>Original English</summary>

**Hill**: Yeah.

</details>

**Host**: 嗯哼。我看到问题是怎么出现的了。然后当你继续运行下去，我们就会撞上那个 Bug。

<details>
<summary>Original English</summary>

**Host**: Mhm. I I see where this is coming. And then when you continue, we will hit the bug.

</details>

**Hill**: 是的。

<details>
<summary>Original English</summary>

**Hill**: Yeah.

</details>

**Host**: 无论在哪一步运行到那里，变更不变量都会失效。

<details>
<summary>Original English</summary>

**Host**: The change in variant will be invalid at whatever step that is run at.

</details>

**Hill**: 没错。而这实际上就是这类工具在分布式系统中变得非常有用的地方，因为通常情况会是：好吧，进程 1 可以做六件事之一，进程 2 可以做六件事之一，进程 3 也可以做六件事之一。而当你使用这种暴力穷举时，你会得到这样的状态序列：进程 1 执行了第一步，然后进程 1 执行了第二步，接着进程 2 执行了第一步……

<details>
<summary>Original English</summary>

**Hill**: Right. And that's actually where a lot of this like becomes useful for distributed systems because often it'll be like okay process one can do one of six things, process two can do one of six things, process three can do one of six things. And when you do this root force you get states like process one takes step one, then process one takes step two, then process two takes step one

</details>

<!-- chunk 6/12 -->

### 状态迭代与 TLA+ 的作用

**Speaker A**: ……进程一执行第一步，然后进程一执行第三步，接着进程三执行第一步和第二步，然后进程二执行第二步和第三步，等等。让普通人去审视这里面的每一种可能的迭代，是非常困难的；但是如果计算机有足够强的 CPU，它只需花个一两晚就能跑完这些可能性。

<details>
<summary>Original English</summary>

**Speaker A**: takes step one, then process one takes step three, then process three takes step one and two, then process two takes step two and three, etc. And being able to sort of see every possible iteration of that is very hard for human beings to do, but a computer with enough CPU can just brunch through to in a night or two.

</details>

**Speaker B**: 是的。所以，这就是 TLA+ 的作用了。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, so this is what TA plus is then.

</details>

**Speaker A**: 是的，基本上就是这样。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, basically.

</details>

### AWS 如何使用 TLA+

**Speaker B**: 我听说过一个案例，我想你可能也参与过，就是 AWS 在使用 TLA+。你能谈谈他们是如何引入这项技术的，他们是如何使用它的，以及就你所知，他们用它来解决什么问题吗？

<details>
<summary>Original English</summary>

**Speaker B**: And one story I've heard and I think you might have been involved is AWS uh using TLA plus. Can you talk about how they onboarded, how they're using it, what they're using it for as far as you're aware?

</details>

**Speaker A**: 好的。关于这方面的开创性论文是 2014 年发表的《在亚马逊 Web 服务中使用形式化方法》（Use of Formal Methods in Amazon Web Services）。他们在论文中提到，公司里有几个人对这方面感兴趣，于是学习了 TLA+ 以及另一种名为 PlusCal 的语言（它可以编译为 TLA+），并将其应用于 DynamoDB 和 S3 存储系统的部分组件中。在应用过程中，他们发现了一些相当复杂的、可能导致数据丢失的 Bug，我记得这应该是在副本复制系统中发现的。论文里写道，展现该 Bug 的最短错误追踪记录包含了 35 个高层级的步骤，如果我没理解错的话，在这个深度下，人类想要坚持排查出问题是非常困难的，或者说你需要有极其坚定的决心……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So the seminal paper on this was in 2014 the use of foral methods in Amazon web services and they talked about how a couple of people in the company were interested it and learned TA plus another language called pluscow which is something that compiles TA plus and applied it to aspects of the Dynamo Dynamob and S3 storage systems. In doing so they were able to find fairly complicated bugs that could potentially lose data and I think it was in the replication system. In the paper it said that the shortest error trace exhibiting the buck contained 35 highle steps which if I understood that correctly it was at at a depth that it would have been very hard for a human to p persevere or you would have need to be really determined

</details>

**Speaker B**: 而且还要非常精确。

<details>
<summary>Original English</summary>

**Speaker B**: and precise.

</details>

**Speaker A**: 当然，我没有参与那个项目，所以我不知道具体的细节。我可以推测，它之所以能发现这个 35 步的 Bug，是因为状态空间可能有一亿个状态那么宽。因此，可能存在大量像 70 步或 80 步这样的执行链是完全安全的，但偏偏就是这条包含 35 步的执行链是无效的。

<details>
<summary>Original English</summary>

**Speaker A**: I did not work on that project of course so I don't know what the details are. I can speculate that the reason it found a 35step bug was because the state base was probably 100 million states wide. So there were like plenty of say like 70 or 80 step chains that were totally safe and it just happened this 135st step chain was invalid.

</details>

### 分布式系统中的经典模式：TOCTTOU Bug

**Speaker B**: 通过与众多使用某种形式化验证的分布式系统客户和团队合作，你在分布式系统中遇到过哪些问题？这些问题是否呈现出一些重复出现的模式——比如它们是如何崩溃的，或者为什么会崩溃？

<details>
<summary>Original English</summary>

**Speaker B**: Through working with a lot of customers and and and teams that that have used form of verifications with distributed systems, what are some problems you've come across with distributed systems that might be a bit of a repeat pattern of of you know how they break down or why they break down?

</details>

**Speaker A**: 如果除了常见的数据竞争和锁死之外还要举出一个例子，那总是会让人有新发现的，那就是经典的“检查时间到使用时间”（TOCTTOU, Time-to-check to time-to-use）Bug。这指的是这样一种情况：你首先检查某项操作是否有效、是否可以被合法执行，你发现它是没问题的；然后过了一小会儿，你执行了这项操作。有时“一小会儿”可能是一天后，有时可能只是一微秒后。但无论如何，在你检查的时间点和实际使用的时间点之间，目标状态有可能从“有效”变为了“无效”。这里有一个很好的例子：想象你从一个银行账户里取钱，然后存入另一个账户。我知道银行实际并不是这么运作的，他们使用的是另一种账本系统，但这只是一个演示性的例子。你会检查：“哦，他们的账户里有 10 美元吗？”“是的。”于是我们扣除 10 美元，然后把这 10 美元存入另一个账户。但实际可能发生的情况是：你检查发现这个账户里有 10 美元，但当你正准备提取时，有其他人迅速介入并把那 10 美元划走了。现在账户里是 0 美元，而你再去扣除那 10 美元，账户余额就变成了 -10 美元。这就是一种“检查时间到使用时间”的 Bug。它们在各处都在发生。

<details>
<summary>Original English</summary>

**Speaker A**: If I can think of like one thing that like besides like just general race conditions and locks, this is the one that like is always a new pull was like yes, it's another time to allow a time to check the time to use bug. And time to check time to abuse is a situation where you are checking to see if something is like valid can be done validly and then you see that it's correct and then a little bit later you do it. Sometimes that little bit later is like a day later. Sometimes it's a microcond later. But is any case where it is possible for something to go from being valid to being invalid in between the time you check and the time you use it. A good example here is imagine you're withdrawing like money from a bank account and putting into another bank account. And this is not how banks work. I know they use a different kind of ledger, but just as a demonstrative example, you check, oh, do they have $10 in their account? Yes, we deduct $10. We put $10 in this account. But what can actually happen is you check, do you have $10 in this account? Yes. And then while you're still getting ready to withdraw, somebody else quickly runs in and grabs those $10 away. And now they're $0 and now you deduct those $10, you have negative $10. That's a time to check the time to use kind of bug. They happen everywhere.

</details>

### “精确投递一次”与工程折衷

**Speaker B**: 是的，这非常有趣。因为当我们在构建 Uber 的支付系统时，我意识到（或者说学习到）在分布式系统中让一条消息“精确投递一次”（Exactly-once delivery）是一个非常困难的问题。因为通常在你只打算进行一次收费时，就需要这种保证。你只想向客户的信用卡收取一次费用，因为如果你为了防止消息丢失而发送了多条消息，最终就会导致重复收费。事实证明，这是一个复杂的问题。实现“至少投递一次”（At-least-once delivery）要容易得多。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And it's very interesting because I when we were building Uber's payment system, I realized or I learned that the problem of having a message delivered in a distributed system exactly once is a very difficult one because typically that's what you need when you want to do one one charge. You want to charge a customer's card exactly once because if you send multiple messages just in case one of them gets lost, you now have double charges. And turns out it's a it's a complicated problem. It's a lot easier to do at least once delivery.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 比起“精确投递一次”要容易。但当然了，你需要在此基础上先构建出“至少投递一次”，然后再去实现“精确投递一次”。

<details>
<summary>Original English</summary>

**Speaker B**: Than exactly one's delivery. But of course you need exactly at least one's delivery to build on to create exactly one delivery.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 我就在想，这会不会就是很多商家干脆直接多收你一笔钱，然后再给你退还一部分的原因，因为从工程的角度来看，这似乎更容易实现。

<details>
<summary>Original English</summary>

**Speaker B**: I wonder if this is why like a lot of like um businesses they just charge you extra and then refund you some amount that seems like easier to do from an engineering perspective as as well.

</details>

**Speaker A**: 同样，从风险的角度来看，通过对信用卡进行预先授权，你也消除很多边界异常情况。你的信用卡有信用额度，如果你只精确授权你当下认为需要的金额，但之后你又需要更多一点，你就可能会陷入稍后难以进行额外授权的边界情况。这就是为什么酒店通常不愿意去处理这个问题。因此，他们只是预先授权一笔较大的款项，因为他们知道这对于酒店住宿来说是一笔不小的开销。否则，他们可能会遇到你的信用额度耗尽的情况，这样他们就不得不走一套完全独立的退款/额外收费流程。但你是对的，一些工程决策的发生可能正是因为某些实现方案更容易达成。

<details>
<summary>Original English</summary>

**Speaker A**: It's also from a risk perspective you eliminate a lot of uh edge cases by authorizing upfront on a credit card you have a credit limit and if you would authorize exactly how much you think you need right now but you need a bit more you might get into that edge case where later you have trouble authorizing it. This is why often hotels don't want to deal with this. So they just authorize a larger chunk and they know because it's it's a larger amount for hotels. Otherwise they might have run into the thing where you would run out of your credit and now they have to do a separate flow. But you're right some engineuring decisions might happen because it's easier to do some some stuff.

</details>

**Speaker B**: 是的，这很有道理。老实说，我原先还以为酒店之所以这么做，只是为了说服你不要损坏酒店的东西呢！因为，就像是，“嘿，如果你知道你要是弄坏了什么就肯定要损失 800 美元，那你大概就不会去搞破坏了”。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, it makes sense. I honestly thought hotels did that because they were trying to convince you not to like break stuff because like hey if if you know that you're definitely going to lose $800 if you break something like you're not going to break stuff.

</details>

### 并发与心智模型

**Speaker B**: 通过与构建分布式系统的工程团队合作，并且介入进去帮助他们学习 TLA+ 以及如何应对系统故障……你学到了什么？在他们了解形式化方法之前，他们通常是如何构思去验证分布式系统的？在学习之后，又发生了怎样的变化？

<details>
<summary>Original English</summary>

**Speaker B**: Through working with engineering teams who are building distributed systems and you're coming in and helping them learn TA plus uh learn how to survive things. What have you learned about how they usually think of verifying distributed systems before they learn about formal methods and what changes after?

</details>

**Speaker A**: 我觉得，关于形式化方法以及它如何影响你构建系统的方式，最有趣的一点不在于该方法的理论本身，也不在于它是如何促使你思考系统的，而在于实践。并发为什么难？为什么我们很难对并发系统进行逻辑推理？你觉得为什么会这么难？

<details>
<summary>Original English</summary>

**Speaker A**: So I think the most interesting thing about formal methods and how it affects how you build systems isn't the theory of the method or how it makes you think about systems. It's the practice. Why is concurrency hard? Why is it hard for us to reason about concurrent systems? Why why do you think it's hard?

</details>

**Speaker B**: 我觉得难点在于你很难在脑海中同时追踪几件事情以及它们可能处于什么状态。这是一个原因。或者，也许仅仅是因为我们缺乏一种心智模型来将它们清晰地描绘出来。我想在白板上画图可能是一种方法，但我不记得我曾经针对并发系统画过白板图。我记得我只在白板上画过方框和指令式的流程，这种流程图确实很适合白板推演。

<details>
<summary>Original English</summary>

**Speaker B**: I think it's hard to keep several things in your mind of like where they could be. That's one. Or maybe we just don't really have a mental model of how to draw them out. I guess whiteboarding would be a way to do it. But I I don't remember whiteboarding on concurrent system. I remember whiteboarding just boxes and and imperative. This flowcharts are good for whiteboarding.

</details>

**Speaker A**: 所以这也正是我经常思考的问题对吧？为什么我们人类很难处理这些系统？而我不确定这是不是因为我们不擅长在脑海中构思它们。我的意思是，当你过马路的时候，你不就是在处理一个并发系统吗？到处都有汽车穿梭。如果你不在脑海中对这个并发系统进行建模，它们就会撞到你，你就会丧命。事实上，我找到过一篇非常酷的论文，叫做《常识计算》（Common Sense Computing），那里面的研究人员试图弄清楚人们是如何思考并发系统的。在与高中生和大学生交谈时，他们将并发问题的表述从“嘿，我们有这些正在执行某些操作的线程”改为了“嘿，我们在售票处有这些负责在音乐会上分配座位的售票员”。然后人们就能快得多地发现其中的 Bug。所以，我确实认为我们是可以变得非常擅长发现并发问题的。我认为之所以这么难，很大一部分原因是我们缺乏练习。通常情况下，当你的系统中存在竞争条件时，你往往在几个月后才会发现，然后你尝试进行修复，几周后你才会知道这个修复是否真的起作用了。相反，使用 TLA+ 这样的工具时，我只需编写系统的模型，然后点击一个按钮，它就会立刻告诉我：“嘿，这里有竞争条件。”然后你把它修复，它又说：“嘿，这里有超时 Bug。”你再次修复，它接着说：“嘿，这里有 TOCTTOU Bug。”这种反馈循环最终会比你在实际开发中得到的快得多。并且我认为，比起其他任何手段，这能极大地帮助人们更轻松地发现竞争条件，以及更从容地思考分布式系统中的问题。我个人发现，当我和新客户合作并为他们的系统建模时，我通常对他们的系统是如何运作的一无所知，对吧？因为他们才是领域专家。我只懂得这种在 30 年前创造的极其古怪的语言。但只要我们完成了建模，我就能在模型中比他们更快地看出 Bug，即使那是他们自己的系统。这完全是因为借助这个工具……

<details>
<summary>Original English</summary>

**Speaker A**: So this is something that I've wondered a lot, right? Like why it's hard for us to deal with these systems. And I'm not sure it's because it's hard for us to think about them. I mean like when you cross the street, aren't you working with concurrent system? You're just there's cars everywhere. They're going to hit you. You're going to die if you don't model concurrent system in your head. And there's actually this really cool paper I found called common sense computing where some people were trying to figure out like how people thought about concurrent systems. when talking with like sort of like high school and college students, they changed the concurrency problem from like, hey, we've got these threads doing some operation to like, hey, we've got these like clerks at a ticket office assigning seats at a concert. People saw the bug much faster. So, I do think we can actually get quite good at seeing concurrency issues. I think a large part of the problem of why it's hard for us is because we don't get a lot of practice. Usually when you have a race condition in a system, you find out months later and then you try a fix and you find out weeks later after that if the fix actually worked. Whereas with the TA plus like I write my model of the system and then I click a button and immedately tells me hey race condition and then you fix it and it says like hey timeout bug and then you fix it again and says hey to bug and that feedback loop ends up being so much faster than you get in practice. And I think that more than anything else helps people find race conditions more easily and think about problems and distribute systems more easily. I've found personally that when I work with new clients and we're modeling their system, I usually have no idea how their system works, right? Because they're the domain experts. I just have know this really weird funky language made 30 years ago. But once we actually have the model, I can see the bug in the model much faster than they can, even if it's their system simply because through this

</details>

<!-- chunk 7/12 -->

### 分布式系统与竞态条件演练

**Speaker A**: ……这主要是改变了人们思考分布式系统的方式。它为人们提供了实际的演练机会，让他们能够更快地观察到这些系统在什么情况下会发生故障以及是如何出错的。

<details>
<summary>Original English</summary>

...main change in how it affects people's ways of thinking about distributed systems. It gives them actual practice of seeing how those systems can go wrong so much faster.

</details>

**Speaker B**: 我想知道这是否有点像代码重构和数据迁移。当你作为一名刚起步的开发者，需要对代码库进行重构时，你需要手动去改——比如说仅仅是更改一个函数名，然后你就需要去更改所有对该函数的引用。你第一次这么做的时候，可能只在几个地方修改了它，然后就把剩下的给忘了。结果要么是编译报错，要么（如果使用的是动态语言）就会出现其他的运行时问题。但只要你多加练习，你就会变得驾轻就熟。

至于迁移（migrations），我见过的大多数工程师在迁移方面都做得非常糟糕，因为你需要制定详细的计划，你需要进行多重检查，你可以进行流量回放（shadowing）、反向流量回放（reverse shadowing）等各种复杂的操作。然后，只有少数做过三四次甚至五次迁移的工程师，到了闭着眼睛都能搞定的地步。

我只是在想，当涉及到竞态条件（race conditions）时，我们大多数人……我个人接触到竞态条件是因为“哦，那次我们发生了重复扣款，然后我们才发现了这个竞态条件”。但是我从来没有处理过第二次类似的情况，所以我肯定不擅长发现竞态条件。我甚至都不擅长去思考它们。

<details>
<summary>Original English</summary>

I wonder if it's a little bit like refactoring and also migrations. So refactoring a codebase when you are starting out as a developer and you need to do a refactoring by hand, you know, let's say just changing a function name, and then you need to go and change all the references to that function. And the first time you do it you change it at a few places and then you forget about the rest, and either it's a compilation issue or if it's a dynamic language it's another problem, but then you get good at it once you practice. 

With migrations, most engineers that I've seen are terrible at migrations because you need to make a plan, you need to do checks, you can do shadowing, reverse shadowing, all that funk. And then there are a few engineers who have done three or four or five and then they close their eyes and they can just do it. 

I'm just thinking that when it comes to race conditions most of us... I was exposed to race conditions by "oh we did a double charge that one and then we found the race condition." But I never did a second one, so I will not be good at finding race conditions. I'm not even good at thinking about them.

</details>

**Speaker C**: 我认为这说得非常在理。听起来你进入团队或者接触这些客户时，你至少为他们提供了一些演练的机会，最起码让他们知道该如何去思考这种类型的错误，哪怕我们甚至抛开工具本身不谈。

<details>
<summary>Original English</summary>

I think that's right on the money. It sounds like you coming into teams or to these clients, you at least give them some practice, the very least of how to think about this category of errors even assuming that taking out even the tooling itself.

</details>

**Speaker A**: 我认为你还会从这些工具中逐渐领悟到一些更微妙的东西，但我认为最直观的一点就是，你会对竞态条件产生一种发自内心的厌恶，这种厌恶感在算法中有了实质的物理体现。

<details>
<summary>Original English</summary>

I think there's also more subtle things that you start to pick up from these tools, but I think that's like the most visceral one—the visceral hatred of a race condition that gets a physical presence in the algorithm.

</details>

### 声明式语言与形式化方法思维

**Speaker B**: 你在这个领域已经深耕很长时间了。对你来说，编写 TLA+ 就像我们大多数人编写 TypeScript 或者我们所熟悉的日常编程语言一样自然。你的思维方式发生了怎样的改变？当你熟练使用命令式语言编程，然后去学习另一种像声明式语言这样需要完全不同思维方式的语言时，两者之间有什么相似之处吗？

<details>
<summary>Original English</summary>

You've been doing this for very long. For you, writing TLA+ is like for most of us writing TypeScript or the language that we're familiar with. How has your thinking changed? And is there any similarities between when you program in an imperative language and then you learn a different one like a declarative language which requires a very different thinking?

</details>

**Speaker A**: 嗯，这也取决于具体的声明式语言。比如我在逻辑编程语言和数组语言中做过很多开发工作，但是如果你给我看 CSS，我就会想，这是什么黑魔法一样的声明式语言？你在说什么？我觉得就是这样的感觉。

不过，要确切地说明这种改变到底是什么，可能会有些困难。比如，现在我常用的用来快速折腾或处理日常杂活的语言是 Python，仅仅因为那是我最早使用的语言之一，而且我非常了解它。而且我认为，至少形式化方法（formal methods）让我更愿意去寻求数学上的解决方案，或者说偏向数学重度依赖的解决方案，而不是简单的、按部就班的可靠解决方案。

<details>
<summary>Original English</summary>

Mhm. And that also depends on declarative language. Like I've done a lot of stuff in logic programming languages and like array languages, but you show me CSS and I'm just like, "what is this dark magic declarative? What are you talking about?" I think so. 

Um, it's going to be hard to sort of pin down exactly what though. Like my usual haggling language is Python these days just because that's one of the first things I used and I just know it very well. And I think at the very least, formal methods makes me much more willing to reach for mathematical solutions or math-heavy solutions than simple reliable solutions.

</details>

### 程序员需要学习哪些数学？

**Speaker B**: 数学也是一个非常有趣的话题。最近你参与了一些关于开发者、程序员或软件工程师是否应该学习数学的辩论。网上有很多来回的讨论。我们能谈谈这个争论的核心观点是什么吗？

<details>
<summary>Original English</summary>

Math is also an interesting topic. You've recently had a bit of back and forth on whether developers, programmers, software engineers should learn math. There was a bit of a discussion back and forth. Could we talk about the core of the argument?

</details>

**Speaker A**: 数学在编程中究竟有什么用，这是一个非常有趣的问题，对吧？

首先，有些数学我们觉得太有用了，以至于我们都忘了它其实是数学。比如数数，数数就是数学。知道一个事物或数字比另一个数字大，这就是数学，对吧？它只是一种我们从小就被教导的数学，因为它太重要了，无论你在生活中做什么，你都需要这种数学。

然后，还有很多数学对特定的专业工作非常有用。比如我和一些网站可靠性工程师（SRE）聊过，他们确实需要微积分，但我认为大多数普通的程序员不需要微积分。

还有一些数学分支在广泛的编程领域中都很有用。我认为像理解图和有向图、了解矩阵、掌握形式逻辑，对很多不同的人来说都非常有用。但我认为对大多数开发者来说，更重要的是广泛接触一下各个数学领域都包含了什么，而不是一看到某个领域就一头扎进去深入学习，对吧？你必须知道有哪些数学工具可用，才能知道哪些对你最有用。而且绝大多数数学对你来说可能是没用的。

<details>
<summary>Original English</summary>

How math is useful in programming is a very interesting question. Right? So first of all, there's math that we all find so useful we forget that it's actually math. Like counting, counting is math. Knowing whether one thing is bigger than another number is math, right? It's just math that we have been taught from a very young age because it is so important that no matter what you're doing in life, you need that math. 

Then there's a lot of math that is useful for very specific specialist jobs. Like I've talked to some SREs who need calculus, but I think most programmers do not need calculus. 

There are some branches of math that are useful in a wide range of programming. I think things like understanding graphs and directed graphs, knowing matrices, knowing formal logic can be very useful for a lot of different people. But I think it is more useful for most developers to have an exposure to what math has in the various fields versus just going all-in on every single field when they see them, right? You've got to know what's available to know what's most useful for you. And most math will not be useful for you.

</details>

**Speaker B**: 这也非常有趣，因为很长一段时间我都觉得，我们在大学里计算机科学专业的数学教育相当繁重，从代数到计算理论，甚至到形式化方法。

在大学里，我学了一大堆高级数学，刚进入业界时，它并没有显得特别有用，或者说我日常工作中并没有用到它。但后来有那么些时候它就变得有些用处了。比如矩阵变换，我学过 3D 图形学，知道如何基于 3D 矩阵变换计算所有的点。后来当 GPU 随着人工智能变得非常流行时，这帮助我理解了其中的原因——因为 GPU 也非常擅长矩阵变换，这碰巧是非常相似的概念。所以，我时不时地觉得，数学有助于你的整体理解，并能让你在面对深奥的问题时不感到畏惧。比如，如果我看到一篇带有形式化证明的论文，我不会退缩。我能开始阅读它，我会知道我的知识极限在哪，但我具备那种基础的理解力。

我想回到我们关于跨学科项目的讨论，我想知道这是否有助于你与其他工程学科建立更紧密的联系，让你能理解那里更多的东西。例如，在电气工程中，确实涉及用数学来描述事物，如果你愿意的话，你会想要掌握那些词汇来理解那部分内容。

<details>
<summary>Original English</summary>

It's also very interesting because for a long time I thought at university we had pretty heavy math education for computer science, from algebra to computational theory to even formal methods. 

At university I learned a bunch of advanced math and at first when I came into industry it wasn't particularly useful or I didn't use it day-to-day. But then there are some times where it's kind of useful. For example, matrix transformation. I learned 3D graphics and how you compute all the points based on 3D matrix transformations, and then it helped me understand when GPUs were becoming so popular with AI why this is—because they're also very good at matrix transformations, which happens to be pretty similar. So every now and then I feel it helps with your general understanding and it helps you be unafraid to go into deep. So if I see a paper with formal proof, I'm not going to shy away from it. I can start reading it and I will know my limits, but I have that understanding. 

And I think going back to our discussion with the crossover project, I wonder if it helps you connect closer with other engineering disciplines in terms of you can understand more things there. For example, for electrical engineering, you do have math involved that is there to describe, and if you will want to have the vocabulary to understand that part.

</details>

### 离散数学与连续数学的差异

**Speaker A**: 关于数学差异，至少有一个有趣的地方是，在几乎所有传统的工程领域，他们需要的数学都是连续数学分析，比如微分方程和微积分。而在美国，如果你能学到那么深的话，高中高级课程里教的就是这种连续数学。

但在软件工程和计算机科学中，我们最常使用的数学是离散数学。像组合数学（基本上就是研究如何计数的数学）、图论、形式逻辑、集合论，这些处理离散实体的数学，通常在美国的高中里教得不多，甚至在大学早期的数学课上也很少教。我有时会想，人们之所以没有认识到数学在软件工程中的用途，是不是因为他们实际需要的数学，并不是他们一直以来所接触的那种数学。

<details>
<summary>Original English</summary>

One of the interesting things at least about the mathematical differences is that in almost every traditional engineering field, the math they need is continuous math analysis, things like differential equations and calculus. And that in the United States is what's taught at an advanced level in high school if you get that far, is this kind of continuous math. 

In software engineering and computer science, the math we most often use is discrete math. Things like combinatorics basically, which is the math of counting things, graph theory, formal logic, set theory—things that work with discrete entities which isn't usually taught at least in the American high school very much or even early in university mathematics classes. And I wonder sometimes if that is the reason people don't recognize the use of math in software engineering is because the math they do need is not the math they've been exposed to.

</details>

**Speaker B**: 有意思，确实是这样，因为我用得比较多的数学是常规网络（common networks）。当然，也许现在这些内容正在过时。但总有这样一个过程：这里有个问题，我们构建一个算法来解决它，然后你会问“这个算法有多高效？”这就引出了大 O 表示法（Big O notation）。我们有了相应的语言来描述它在空间和时间上的效率，你可以进行性能权衡。而且，一旦两个人都掌握了同样的知识，你们就可以就这些事情展开深入讨论。一方面它非常抽象，但另一方面，如果你贴近底层机器，它会非常有用。

我还发现，一旦我理解了背后的数学原理，我对大 O 表示法的理解就变得好多了。因为我认为它通常只是被肤浅地解释为“哦，这个函数以某个特定的速度扩展”，但实际上，它更正式地来说是一种描述函数集合的方式，这背后还有关于我们如何进行渐近分析（asymptotics）之类的数学理论等等。我认为即使在纯粹的技术层面上，数学确实对理解这些概念有极大的帮助。

对。那么具体到 TLA+，在业界你看到在哪些情况下 TLA+ 非常适合解决某些特定的问题？在什么情况下你会考虑使用它？

<details>
<summary>Original English</summary>

Interesting, yeah, because the math that I did use more was common networks. And of course, maybe these days those entries are going out of style, but there's the "here's a problem, build an algorithm that solves it", and then you ask like "okay, how efficient is this algorithm?" And then there's the Big O notation. We have the language to describe how efficient in space and time it is and you can do tradeoffs. And once two people know the same thing, you can have discussions about these things. On one end it's very abstract, but on the other hand, if you're close to the machine it can be very useful. 

I've also found that my understanding of Big O notation got a lot better once I understood the mathematics behind it, because I think it's usually explained as terms of like "oh this function scales at this certain rate", but it is more formally a way of describing a set of functions and then there's the math of how we do asymptotics and stuff, etc. I think even in the technical aspects, math does help a lot in understanding those.

Yeah. And with the TLA+ specifically, what cases have you seen in the industry TLA+ being a good fit for certain problems, and in what cases would you ever consider it?

</details>

### TLA+ 的适用场景

**Speaker A**: 我认为在 TLA+ 以及大多数（不是全部，但大多数）形式化方法（formal methods）的案例中，它们在高度计算性的领域中表现得最出色。在这些领域，大多数问题都是高度技术性的，而不是那种深深嵌入业务逻辑的问题。

我的意思是，比如“如何在两个数据集之间复制节点”，这就是个非常纯粹的技术性问题，对吧？如果是其他问题，比如我在想一个好例子……像“我们如何确保我们的冲刺（sprints）不超时”就……

<details>
<summary>Original English</summary>

I think the case of TLA+ and most—not all, but most—formal methods, they shine the most in highly computational domains where most of the problems are highly technical and not business embedded. And what I mean by that is that something like "how do you replicate nodes between these two data sets" is very technical, right? Something like—I'm trying to think about a good example here—like "how do we make sure our sprints don't go overtime" is...

</details>

<!-- chunk 8/12 -->

### 形式化方法的适用场景与局限性

**Presenter**: 业务逻辑涉及非常复杂的人类行为。我曾经帮客户对这部分进行建模，虽然取得了一些成效，但这真的非常困难。因此，我很多客户最终都是数据库供应商、云计算领域的从业者，或者硬件工程师。他们所处的工作领域对业务至关重要，但距离业务的最前线又有几步之遥。我想说的另一点是，不同的工具擅长解决不同的问题。特别是 TLA+，它往往非常适合处理离散的分布式系统，这类系统的主要挑战在于处理并发问题以及最终可能出现的各种行为可能性。它不支持浮点数计算，不支持小数运算。当你试图弄清楚概率性问题时，它的表现也不太好。哦，我想我还应该补充一点，就是你需要关注的错误类型。如果某个错误有可能发生，那就是一件很严重的事情。如果你觉得：“好吧，这个错误很糟糕，但只要它发生的概率低于百分之一就没关系”，那这种想法是不行的。TLA+ 无法为你进行那种概率推理。虽然市面上有可以做概率推理的工具，但它们缺乏像函数、数组或数字这样的概念。

<details>
<summary>Original English</summary>

**Presenter**: business, right? It deals with like very human behaviors. So, I've had to help model client model that and we got some use out of it, but it was very hard. So, that's why a lot of my clients end up being things like database vendors or like cloud computing people who are or like hardware people who are working in a space that's like very important for business, but several steps removed from like the front lines of that business. The other thing I would say is that different tools are good at different things. TA plus in particular tends to be good at discrete distributed systems where the main challenges are messing with concurrency and possibilities eventually being like behaviors. It doesn't do floating point. It doesn't do decimals. It doesn't do as well with when you're trying to figure out probabilistic things. Oh, that's another thing I guess I should be saying is that like where the kinds of errors you care about are ones where like if it is possible this error to happen, that is a big deal. It's not good if like you're like, "Okay, this error is bad, but as long as it happens less than one out of a 100 times, it's it's okay. It can't do that kind of probabilistic reasoning for you." There are tools that can, but they lack things like functions or arrays or numbers.

</details>

**Presenter**: 此外，这还取决于你需要花多少时间来进行规划。如果你不需要花那么多时间去规划，那使用这个工具就会浪费你的时间。我确实想补充一点：如果你能够通过不断迭代来找到解决方案，而且出现的 Bug 不会造成太大损失，那你可能就不需要这个工具。我认为，作为一个经常讨论非常小众工具的人，不断强调“不，我不是在试图说服你去使用一个对你来说并非最佳选择的东西”是非常重要的。我觉得，很多人对这些形式化方法持怀疑态度的原因之一，是因为他们曾经被像 CASE 工具、UML 建模以及所有那些所谓的“奇迹解决方案”坑过，当时无论如何都有人强迫他们使用这些东西。因此，我认为始终说明“如果这不是适合你的正确工具，我就不会推荐它”是极其重要的。

<details>
<summary>Original English</summary>

**Presenter**: Also depends on how much time you need to spend planning. Like if you don't need to spend that much time planning, this is going to waste your time. I I do want I do want to add that that this like if you can iterate your way through a solution and the bugs aren't going to be that costly then you might not need this tool. I I think it's really important as like a person who who talks about a really exotic tool to like constantly emphasizing like no I'm not trying to convince you to like use something that's not a good choice for you. I think a lot of the reason people are skeptical of these is because they've been burned by things like case and UML and all these other miracle solutions that were forced on them by people who wanted them to use it no matter what. And I think it's really important to always say like if this isn't the right tool for you, I am not going to recommend it.

</details>

### Alloy 简介与访问控制系统示例

**Interviewer**: 那么，我们能谈谈其他的工具吗？或者你能给我们展示几个其他的工具吗？

<details>
<summary>Original English</summary>

**Interviewer**: And then can we talk about other other tools or can you show us a few other ones?

</details>

**Presenter**: 没问题。我这台电脑上安装的另一款工具叫 Alloy，它是由麻省理工学院的一位教授开发的。它属于不同的形式化系统流派（lineage）。就像世界上有许多不同类型的编程语言一样，形式化规范和验证工具也有很多不同的流派。现在的这个例子是一个简单的访问控制系统。我们有一组资源，以及可以读取这些资源的用户。

<details>
<summary>Original English</summary>

**Presenter**: Yeah. So the other tool I have installed on this computer is called alloy and it was made by an MIT professor. Different format is lineage. Just like there's many different kinds of programming languages, there's many lineages of formal specification verification tools. So this example is a simple access control system. So we have a set of resources and users who can read those resources. Yep.

</details>

**Interviewer**: 所以，每个资源都对应一些有权限读取它的人，而且资源可能有一个父级资源，也可能没有。L1 的意思是小于等于一个父级资源吧。

<details>
<summary>Original English</summary>

**Interviewer**: So each resource has some people who it's reasonable by and resources may or may not have a parent resource. L1 mean L1 meaning less than equal to one resource.

</details>

**Presenter**: 并且系统里没有循环关系。也就是说，任何资源都不能以自己作为父级资源，也不能把它的父级资源的父级作为自己的父级。

<details>
<summary>Original English</summary>

**Presenter**: There are no cycles. So no resource can have itself as a parent or its parents parent as a parent.

</details>

**Interviewer**: 对。你可以读取访问一个资源，前提是该资源明确表明你可以读取它，或者它的父级资源表明你可以读取。我们设定了这样一个属性：如果你能读取一个资源，那你就能读取它的子资源。

<details>
<summary>Original English</summary>

**Interviewer**: Yep. You can read access a resource if the resource indicates you can read that resource or if it's parent indicates you can read that resource and we have a property that if you can read a resource you can read its children.

</details>

**Presenter**: 是的。但这段代码里有个 Bug。你觉得是什么？

<details>
<summary>Original English</summary>

**Presenter**: Yep. This is has a bug. What is it?

</details>

**Interviewer**: 我粗略看了一下，感觉这一切都很合理啊。我认为逻辑是这样的，因为我们规定了所有拥有父级资源权限的人都可以访问它。我猜测，如果这里真的有 Bug，那它可能和我们之前讨论过的“在特定区域内进行访问”有关。我完全没头绪。我们能运行一下它吗？

<details>
<summary>Original English</summary>

**Interviewer**: I mean I I'm I'm glancing at this and this all made sense to me. I thought this is it cuz we're saying all of the parents can access it. I'm assuming the bug if if there is one is it will it might have to do with something that we talked earlier of like accessing in certain areas. No idea. Can we run it?

</details>

**Presenter**: 当然可以。说明一下背景，这实际上是在一个较早版本的 Alloy 中编写的。大约直到四年前，Alloy 还不具备任何针对状态进行时序推理（temporal reasoning）的能力。所以这是我在那之前使用的一个例子，主要演示如何分析并找出静态配置中的错误。在 Alloy 中，这通常意味着寻找数据结构、数据模型以及领域模型中的 Bug。我发现，领域驱动设计（DDD）社区实际上对这个领域非常感兴趣。我现在要把这段代码复制到 Alloy 他们的 IDE 里面，这个 IDE 界面比较简陋，这也是为什么现在大家都在用 VS Code 的原因。现在，如果我执行它，反例就出来了。

<details>
<summary>Original English</summary>

**Presenter**: Yes, we can. So this was actually made in an earlier version of alloy just for the just for context. Um alloy did not have any sort of temporal reasoning over state up until about 4 years ago. So this is one examples I used from before then of basically how you can analyze and find bugs in static configurations. An alloy that often means finding bugs in data structures or in data models and domain models actually. So there's actually some interesting there's some interest in this in the domain driven design community I found. I'm going to copy this over to alloy their IDE which is a bit more rudimentary and that's why everybody uses the VS code. Now, if I execute this, here's the counter example. All right.

</details>

**Presenter**: 这是 Alloy 特有的一个优点：它可以生成可视化图表。基本上，问题就在这里。我们有一个可以读取父级资源的用户。因为我们如何定义访问权限的缘故，父级资源有一个子资源，我们可以像读取父级一样读取它，所以我们可以读取子资源。

<details>
<summary>Original English</summary>

**Presenter**: And this is one of the nice things about Ali specifically is that it can generate like visualizations. So, basically, here's the problem. We have a user who can read a parent resource. The parent has a child because of how we defined um can access we can read as parent so we can read the child.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yes

</details>

**Presenter**: 可是，这个子资源还有一个孙级资源（grandchild），而我们却无法读取这个孙级资源。原因在于，我们并没有被分配到那个子资源的 `readable_by`（可读取者）集合中，我们仅仅在这个父级资源的集合里。换句话说，`readable_by` 的属性并没有向下传递（不是传递关系）。所以，我们可以读取子资源，但却无法读取子资源的子资源。这就是那个 Bug。

<details>
<summary>Original English</summary>

**Presenter**: the child has a grandchild we cannot read the grandchild. So because we are not in we are not assigned to the readable by for the child only the parent. In other words readable by is not transitive. So we can read the child but not the child's children. And that is the bug.

</details>

**Interviewer**: 嗯，而且它还能帮我们把这些情况可视化出来。

<details>
<summary>Original English</summary>

**Interviewer**: Mhm. and to visualize those for us.

</details>

**Presenter**: 没错。这也相当不错，是人们非常喜欢 Alloy 的原因之一。

<details>
<summary>Original English</summary>

**Presenter**: Yes. Which is quite nice and one of the reasons why people really like Alloy.

</details>

**Interviewer**: 很好。

<details>
<summary>Original English</summary>

**Interviewer**: Nice.

</details>

**Presenter**: 不过，Alloy 在对分布式系统进行建模时稍微逊色一些，这也是为什么我的大部分工作都在使用 TLA+。

<details>
<summary>Original English</summary>

**Presenter**: It's a bit worse for modeling like distributed systems though, which is why most of my work is in TA plus.

</details>

### 布尔可满足性与 Alloy 的底层原理

**Interviewer**: 那么如果要修复这个问题，需要做些什么呢？我们需要把访问权限授予子资源的子资源。

<details>
<summary>Original English</summary>

**Interviewer**: And then to do the fix, what would it involve? We would need to give access to the children's children.

</details>

**Presenter**: 对，我们可以用几种不同的方法来修复它。通常来说，像这样的形式化方法，它们并不会直接告诉你“这就是修复方法”，而是让你自己选择想要如何修复。比如，我可以说：“好吧，我要声明这也是一种传递查找（transitive lookup），我们在所有父级关系上做一个传递闭包（transitively close）。”如果我执行这个修改，就不会再出现反例了。话虽如此，但这在物理现实中可能并不可行。我可能得对人们说：“嘿，在我们的 SQL 数据库中，你必须执行一个传递查询。”而我们的数据库管理员可能会说：“不，那会让数据库崩溃的，你不能那样做。”然后我们就不得不寻找其他的修复方案。

<details>
<summary>Original English</summary>

**Presenter**: Yeah, there's a few different ways that we could fix it. And often like pro methods, they don't really tell you here's how you fix it. It lets you choose how you want to fix it. Like one thing I could do is I could say okay I'm going to say that this is a transitive lookup too that we transitively close over all parents and if I execute that no more counter example that said that might not be something physically implementable I might try to tell like hey people like hey in our SQL database you have to have a transitive query and our database administer is like no that's going to crash the database you can't do that then we have to find a different fix

</details>

**Interviewer**: 所以这就是形式化方法的魅力所在，是的，它为你提供了多种实施修复和修改的机会，然后你可以再次运行它，看看它带来了什么变化。

<details>
<summary>Original English</summary>

**Interviewer**: so this is the beauty of formal methods yes it it it gives gives you opportunities of how you will implement fixes, changes, and then you can rerun it again and see what difference it made.

</details>

**Presenter**: 完全正确。现在，分享一个有趣的小知识，我很喜欢这些关于各种东西的趣事。你看到这里写着“Solver SAT 4J”吗？你听说过 SAT（布尔可满足性）问题吗？

<details>
<summary>Original English</summary>

**Presenter**: Exactly. Now, one quick fun fact. I love just fun facts about stuff. You see how this says solver SAT 4J. So, have you heard of SAT SAT problems?

</details>

**Interviewer**: 没有。

<details>
<summary>Original English</summary>

**Interviewer**: No.

</details>

**Presenter**: 好吧。是否存在某个变量使得命题 P 为真？如果我可以让 P 为真或假，有什么方法可以使那个命题为真？假设 P 是一个布尔值，我有一个命题 P。你能给 P 赋予 True（真）或 False（假）的值，从而使那个命题变为真吗？

<details>
<summary>Original English</summary>

**Presenter**: Okay. Is there some variable that makes the statement P true? If I can make P true or false, is there a way I can make that true? So let's say P is a boolean and I have a statement P. Can you assign some value of true or false to P to make that true?

</details>

**Interviewer**: 通常你可以赋予它为 True，那它就会变成对的……

<details>
<summary>Original English</summary>

**Interviewer**: Typically you can assign true and it it will correct

</details>

**Presenter**: 两个都是 True，是的。

<details>
<summary>Original English</summary>

**Presenter**: both true. Yeah.

</details>

**Interviewer**: 所以这个命题可以通过将 P 设置为 True 来满足。那如果命题是 P 并且 非 Q 呢？

<details>
<summary>Original English</summary>

**Interviewer**: So that statement is satisfiable by setting P to true. What about P and not Q

</details>

**Presenter**: 同样可以通过赋予 P 为 True 并且赋予 Q 为 False 来满足。

<details>
<summary>Original English</summary>

**Presenter**: also satisfiable by by giving giving true to P and false to Q.

</details>

**Interviewer**: 没错。那么如果命题是 P 并且 Q 并且 非 P 呢？

<details>
<summary>Original English</summary>

**Interviewer**: Right. Now what about P and Q and not P?

</details>

**Presenter**: 那是不可满足的（unsatisfiable），因为无论你进行什么布尔赋值，True 和 False 的组合永远、永远不可能是真。

<details>
<summary>Original English</summary>

**Presenter**: that that unsatisfiable because no matter what booleaning you do the the true and false will always will never be true.

</details>

**Interviewer**: 太棒了。你刚才完成的就是一个布尔可满足性（Boolean satisfiability）问题：拿到了一个包含大量布尔变量的逻辑命题——在刚才的例子中是两个变量——并找到了某种使其为真的赋值方式，或者得出它根本无法为真的结论。现在，布尔可满足性是我们所说的 NP 问题，在理论上，这意味着世界上并不存在一个完美高效的、能够解决所有此类问题的算法。但在实际应用中，这意味着我们可以极其快速地解决它们。所以，让 Alloy 变得有趣的往往是这一点：与通常采用暴力穷举的 TLA+ 不同，Alloy 可以被转换成一个可满足性问题。如果我打开这个看，它能够把那个模型变成一个关于布尔概率的命题，比如说 `非 x21 且 x96 且 x15，或非 x72` 等等。正因如此，绝大多数的 Alloy 模型都可以在几毫秒内完成检查，最多也就一秒钟。相比之下，对于大型的 TLA+ 模型，你通常必须让它在夜间通宵运转，才能遍历完那 1 亿种状态。

<details>
<summary>Original English</summary>

**Interviewer**: Lovely. What you've just done is a boolean satisfiability problem taken some sort of statement of a ton of boolean variables in this case two and found some either found some assignment that makes it true or said that it cannot be made true. Now boolean satisfiability is what we call empty and what that means in theory is that there's no such thing as a perfectly efficient algorithm that solves all problems. In practice that means that we can solve them really fast. So often what makes alloy interesting is that unlike TA plus which mostly brute forced alloy can be converted into a satisfiability prop. I'll open this up and it is able to turn that model into a boolean probability saying not x21 and x96 and x15 or not x72 etc. And because of that most alloy models can be checked in like a few milliseconds or a second at most. Whereas often for like a large TA plus model, you have to basically churn it overnight to go through all 100 million states.

</details>

### 其他的形式化验证工具

**Interviewer**: 我们能再谈谈一些对于那些想了解形式化验证的人来说可以考虑的其他工具吗？

<details>
<summary>Original English</summary>

**Interviewer**: Can we talk about some other tools uh on the I guess a table of someone looking into formal verification?

</details>

**Presenter**: 很乐意。我现在电脑上没有更多的演示案例了，但我可以口头讲几个。其中几个比较成功的是……比如 P 语言。我认为它是由微软研究院的一位研究员发明的，后来他被亚马逊挖走了，他发明这门语言的目的是提供一种……

<details>
<summary>Original English</summary>

**Presenter**: Happily. So I don't have any more demos on my PC right now, but I can talk about a few of them. So a couple of the ones that have been success plus is um the P language um which was invented by I think a person at Microsoft research who was then poached by Amazon as a way of making a language that

</details>

<!-- chunk 9/12 -->

**Guest**: ……除了其他工具之外，它比 TLA+ 更容易上手。所以它基本上看起来就像一组状态机，交互式的状态机，它们互相发送消息，几乎就像 Erlang 里的 Actor 模型之类的东西。

<details>
<summary>Original English</summary>

**Guest**: was more accessible than TLA plus among other things. So it basically looks like a set of um state machines interacting state machines that send messages to each other almost like the actor model in like Erlang or something like that.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: >> Yep.

</details>

**Guest**: 所以有这么一个工具。还有一个和 Quint 处于同一领域的工具，基本上是那些原本为 TLA+ 制作另一种模型检查器的人，后来意识到他们可以创造一门完整的、更容易让人上手的语言。他们在银行业，以及我没记错的话，加密货币领域的智能合约方面，获得了很大的关注。所以我用过的另一个，虽然更小众但非常有趣，叫做 Prism。Prism 是一个概率模型检查器。比如，TLA+ 可以告诉你“这个 bug 永远不会发生”或“它可能会发生”；而 Prism 可以告诉你“这个 bug 有 10% 的概率会发生”，或者“如果系统关闭，它有 25% 的概率会发生”。这非常酷，但它也更偏学术性，因为实际上把其他语言翻译成 Prism 需要做更多的工作。如果你对这个感兴趣的话，我基本上用它做过这样一个事……嗯，你听说过犹太游戏陀螺（Dreidel）吗？

<details>
<summary>Original English</summary>

**Guest**: >> So there's that. There's also another one in the same space as um Quint which was basically people who were making a different kind of model check for TA plus and then realized they can make an entire language that was easier for people to pick up. They've gotten a lot of interest in the banking and um I believe cryptocurrency space smart contracts. So another one that I've used which is which is a lot more niche but quite interesting is called Prism and Prism is a proistic mile checker. So like Kila Plus can tell you like this bug will never happen or it could happen. Prism can tell you this bug can happen 10% of the time or it is a 25% chance of happening if you shut down. It's really cool but it's also much more like academic in that there's a lot more work required to actually translate languages into Prism. If you're interested in it, I've basically been doing this like um have you heard of the Jewish game Drrele?

</details>

**Interviewer**: 没有。

<details>
<summary>Original English</summary>

**Interviewer**: >> No.

</details>

**Guest**: 好的。这是你在光明节玩的一种游戏，你旋转一个小陀螺，然后就能赢钱。我不喜欢这个游戏。所以我用 Prism 写了一个由两部分组成的系列文章，通过将其作为一种数学模型进行分析，来证明这个游戏其实并不好玩。

<details>
<summary>Original English</summary>

**Guest**: >> Okay. It's a game that you play on Clanica where you spin a little top and you get money. and I do not like the game. And I have written a two-part series using Prism to show how this game is not fun by analyzing as a mathematical thing.

</details>

**Interviewer**: 哈哈，太喜欢这个了。

<details>
<summary>Original English</summary>

**Interviewer**: >> Love it.

</details>

**Guest**: 我认为这些是一些非常受欢迎的工具。但此外，嗯，我的意思是我还可以继续列举下去。比如 Event-B，我相信它最著名的应用之一是用在巴黎地铁系统的一部分里。还有 mCRL2，我想它来自一所荷兰的大学。还有 Hum X（可能指 Uppaal），它主要用于机器人控制系统，但我认为那主要是在学术界。还有 NuSMV，我认为 NASA 在很多项目上都用过它。我还可以继续说。当然，这些都只是用于规定系统的抽象模型。如果你想谈论验证代码，那么你可以使用像 Dafny 这样的工具，它基本上可以编译成 .NET，并允许你编写可证明的代码。还有用于 Java 代码模型检查的 JML。有用于检查 C 语言的 Frama-C。还有 SPARK Ada。你还有像 Coq、Lean 和 Isabelle 这样的以太坊证明器。我还可以继续列举，我……

<details>
<summary>Original English</summary>

**Guest**: >> Those are I think some of the ones that are like really popular. But there's also um I mean I could just keep listening. There's like there's like event B which is like been used I believe famously in part of the Paris Metro system. Um there's like MCRL2 which I think is come comes from a Dutch university. Hum X which is mostly used for like um robotic control systems but I think that's mostly academic. There's like new SMV which I think NASA's used for a bunch of stuff. I can keep going. Then of course there's all the of course this is only for specifying like abstract models of systems. If you want to talk about verifying code then you've got things like Daphne which is basically something that compiles to like net and lets you basically write provable code. You've got JML for Java check for like model checking Java code. You've got like um Primma C for like checking C. You've got Ada Spark. You've got like and you've got Ethereum provers like um Rock and Lean and Isabelle. And I can keep going. I

</details>

### 基于属性的测试与形式化验证 (Property-Based Testing vs Formal Verification)

**Interviewer**: 我想问一下，基于属性的测试（property based testing）和形式化验证之间是什么关系？在回答这个问题之前，我们先来明确一下什么是基于属性的测试。

<details>
<summary>Original English</summary>

**Interviewer**: >> I wanted to ask how does property based testing relate to formal verification and and before let's just like lay out what property based testing is.

</details>

**Guest**: 好的，让我们回到那个关于求 `max`（最大值）的整个例子，对吧，求列表的最大值。我们可以这样定义 `max` 的规范：它必须在这个列表中，并且对于列表中的所有元素，它都是该列表中最大的元素，对吧？我电脑上其实有一个做这个演示的例子，所以我们实际来看看这个。在这个我为我的书（顺便打个广告）写的文件里，我基本上有三个版本的 `max`：一个正常的版本，它只返回列表的最大值；一个返回前三个元素中最大值的版本；还有一个返回绝对值最大值的版本。

<details>
<summary>Original English</summary>

**Guest**: >> So let's go back to that entire thing with max right max of a list. we can define like the specification of max it is in the list and for all elements of the list it is the largest element of that list right I actually have a demo on my computer of doing that so let's actually go into this so over here in this file that I wrote for my book plug I have a I have basically three variants of max a good version which just returns the max of the list one that returns the max of the first three and one that returns max the absolute value.

</details>

**Interviewer**: 是的。

<details>
<summary>Original English</summary>

**Interviewer**: >> Yep.

</details>

**Guest**: 下面这个就是一个属性测试。它的作用是声明：给定一个整数列表，其中每个列表至少包含一个整数。

<details>
<summary>Original English</summary>

**Guest**: >> This below here is a property test. What it does is it says given a list of integers where each list has at least one integer in it.

</details>

**Interviewer**: 嗯。

<details>
<summary>Original English</summary>

**Interviewer**: >> Yep.

</details>

**Guest**: 该函数的最大值必须在这个列表中，并且所有其他值都必须小于或等于它。

<details>
<summary>Original English</summary>

**Guest**: >> The maximum value of that function should be in the list and all other values should be less than or equal to it.

</details>

**Interviewer**: 嗯。很清楚。

<details>
<summary>Original English</summary>

**Interviewer**: >> Yep. Clear.

</details>

**Guest**: 所以这在很大程度上就像我们的形式化验证规范，我们的形式化规范。我们所做的形式化方法和属性测试之间的区别在于：形式化方法是在问，或者说在表达：“好吧，我们能证明这对每一个可能的列表都成立吗？”而属性测试则是：“好吧，那非常非常难，正如我们之前讨论过的，在实践中很难做到。那么我们能不能改成生成一千个随机列表，然后把这些都试一遍？”我已经设置好了，所以这样它基本上会运行那个无效的 `max` 函数，也就是只取前三个元素最大值的那个。

<details>
<summary>Original English</summary>

**Guest**: >> So this basically a lot like our formal verification spec, our formal specification spec. The difference between the formal methods that we do and um property testing is that the formal methods are ask are saying like okay can we prove this for every possible list and property testing is well that's very very hard and as we talked about very difficult to do in practice can we instead generate a thousand random lists and try all those I have it set so that way it basically has the invalid max max the first three

</details>

**Interviewer**: 我们应该会得到错误，或者它应该能捕捉到一些错误。

<details>
<summary>Original English</summary>

**Interviewer**: >> we should be getting errors or it should catch some errors.

</details>

**Guest**: 嗯哼。让我们运行一下。我直接从命令行运行它，这样更快。呃，`pytest test_max.py`。这是一台我主要在会议上带的旧机器，因为在上面随便跑点东西很方便。所以我们在这里看到，它说这个测试在这一行失败了，对于列表 `[0, 0, 0, 0, 1]`，并不是所有的值都大于 0（注：此处为解释代码结果的口语化表达）。这是因为我刚才说，我们那个错误的 `max` 函数只看前三个值。所以它找到的最大值是 0，但这里的实际列表最大值是 1。在书的某一部分里，我把这个分成了两个子规范：测试 `max` 是最大元素，以及它在列表中。这就是为什么其中一个测试通过了。不过我应该指出，如果我没记错的话，我用详细模式运行它，我试图在这个演示中展示的是，它实际上并不是从最大的列表开始测试的。它实际上是从一个小得多的列表开始的。这里，如果我打印 `max`，如果我打印，然后我像这样操作。我认为它首先会尝试许多边缘情况。所以它基本上会尝试巨大的列表、微小的列表、空列表等等。一旦它找到一个失败的例子，比如这个值，它就会开始将其缩小。寻找最小的、值得关注的失败示例。这就是为什么这能让我们找到 bug。不仅是找到 bug，而且能以一种普通人能理解的方式展示出这个 bug，因为我认为，它最初可能是用这个列表发现了 bug。而如果不借助于此，只看代码，我肯定不知道问题出在哪里。这基本上就是简而言之的基于属性的测试。正如你所看到的，它不如形式化验证那么彻底，但它应用起来要容易得多。

<details>
<summary>Original English</summary>

**Guest**: >> Mhm. Let's run it. Let me just run it from the command line. That's faster. Uh um pi test uh test max.py. This is an old machine I mostly bring on for conferences because it's like easy to just throw in something on here. So we see over here that it says that this test failed on this line that for the list 00001 it is not true that all the values are greater than zero. This is because I said our badmax only looks at the first three values. So it found the max was zero but here the actual max of the list was one. I broke this down to two subspects for a part of the book where we have testing that max is the largest element and also that it's in the list. So that's why one of the tests passes. Um I should note though that um if I believe I run this with a verbose what I'm trying to do for this demo is um show that it actually does not start with the um largest list. It actually starts with a much smaller with here we go. If I print max, if I print then I do it like this. I think it tries a lot of edge cases first. So it's basically trying huge list is trying like tiny list is trying like empty list etc. And once it has one that fails, for example, this value, it starts to shrink it. Finding the minimally interesting example. And that's why this lets us like find a bug. Not just find a bug, but also find a bug and present it in a way that is like comprehensible for the average human because I think that it found the original bug with this list. And I do not think that looking at this, I'm going to know what the problem is. That's basically property property based testing in a nutshell. And as you can see, it is less thorough than formal verification, but it's a lot easier to apply.

</details>

**Interviewer**: 所以，听起来作为入门的话，它可以是一个很好的中间地带。

<details>
<summary>Original English</summary>

**Interviewer**: >> So, it sounds like it can be a nice middle ground in terms of getting started with it

</details>

**Guest**: 并且可能就止步于此了。因为我觉得，虽然我很喜欢形式化方法，但对大多数人来说，它仍然是一个相当小众的工具。我认为，通常来说，基于属性的测试会对更多人有用。

<details>
<summary>Original English</summary>

**Guest**: >> and probably just stopping with it because I think that I love formal methods, but I think it's a fairly niche tool for most people and I think like property based testing is in general going to be useful for more people.

</details>

### AI 生成代码的规范验证 (Formal Methods and AI Generated Code)

**Interviewer**: 所以，说到一般的验证，今天我们有 AI 生成了大量的代码。我们有数据可以证明这一点，而且在日常生活中我也在自己身上看到了这一点。我让 AI 生成了我自己大量的代码。我们得到了更多的代码。代码审查变得……人们很难再对代码投入那么多的注意力。所以越来越多的人说，也许我们应该以某种方式更多地验证事情，然后不断出现一种想法：也许形式化验证或基于属性的测试，或者这些东西可能会变得更加有用。你认为这会发生吗？因为我看到很多人在谈论这个，但我并没有真正看到有人采取什么行动。

<details>
<summary>Original English</summary>

**Interviewer**: >> So, speaking of of verification in general, today we have AI generating way more code. We have data to prove this as well, but also dayto-day I I I see it on myself. I have AI generate a lot more of my code. We're getting more code. C code reviews are people are it's hard to pay more attention to this. So there's a growing number of people saying well maybe we should somehow validate things more and there's an idea that keeps coming up maybe for more verification or property based testing or some of these things could be more useful. Do you think this will happen or because I see a lot of people talking about this. I I don't really see anyone doing much about it.

</details>

**Guest**: 在我的客户群体中，我绝对看到了更多的业务需求。人们试图用 AI 生成规范，然后让我帮助处理规范，或者发现其中的问题；而且我也确实看到越来越多的人在使用基于属性的测试。我知道，比如我认为 Kro（可能是指某个如 Cedar 的规范驱动开发平台），就是那个亚马逊的规范开发平台，特别把生成属性测试作为其核心价值之一进行宣传。我也看到了很多关于使用 AI 生成规范的论文。我想说，这实际上非常令人兴奋，因为正如你所见，编写规范的许多挑战（不是全部，但有很大一部分）在于如何去理解和掌握那些非常非常技术性的语法和语义。尽管如此，我自己在这方面做了很多实验，我认为截至 3 月份，AI 非常不擅长的一件事是……我知道 Claude 刚刚发布了新的模型，比如 Claude 4.8（注：口误，可能指 Claude 3 Opus 等），所以也许这一切都过时了。情况每个月都在变。但它非常不擅长想出属性。它在这一点上非常糟糕。

<details>
<summary>Original English</summary>

**Guest**: >> I'm definitely seeing more business from people in my my client as method is people trying to generate specs with AI and then getting me to help like work with the spec or like find issues with that and I'm definitely seeing more people like using property based testing. I know for example I think Kro like the Amazon specri development platform specifically advertises generating property tests as like one of the key values of it and I've been seeing a lot of like papers about generating specs using AI. I will say this is kind of really exciting because as you saw like a lot of the challenge of writing a spec not all of it but like a lot of it is like rocking your head around like very very technical syntax and like semantics. That said, I've been doing a lot of experience with this myself and I think the one thing AI is extremely bad at as of March, I know that claude just released a new like cloud 4.8, so maybe this is all out the window. It changes every month. It is very bad at coming up with properties. It is very bad at that.

</details>

**Interviewer**: 想出属性是什么意思？是指写下实际的形式化验证部分吗？

<details>
<summary>Original English</summary>

**Interviewer**: >> What What does coming up with properties mean? Is it writing the actual form of verification part?

</details>

**Guest**: 是的。所以，如果你给它属性和一个规范，它可以告诉你：“嘿，我们将修复规范，让这些属性通过。”这没问题。但如果你基本上告诉它：“这是一个规范，你也想出这个规范的属性吧。”它就会像这样：“好的，那么我要写的属性之一是……”

<details>
<summary>Original English</summary>

**Guest**: >> Yes. So, like if you give it properties and like a spec, it can tell you like, hey, we're going to fix the spec, make these properties pass. That's fine. What if you basically tell it here's a spec also come up with the properties of the spec. It'll be like, okay, so one of the properties I'm going to

</details>

<!-- chunk 10/12 -->

### AI and Formal Verification

**Speaker A**: ……你定义的是要么 P 为真，要么非 P 为真。然后你就会觉得，这永远都是真的嘛。这就好像，哇，我验证了它。太棒了。我太擅长这个了。特别是当你处理所谓的“活性属性”（liveness properties），也就是关于一个系统在很长一段时间内会如何演进的属性时。你就是很难把它放下。AI 目前在这一块确实还不够好。而且我经常发现，在面对我的客户时，我必须告诉他们，AI 在生成实际设计方面做得很好，但在实际表达该设计应该做什么时，它还做不到。你必须自己完成这部分工作。

<details>
<summary>Original English</summary>

**Speaker A**: specify is that either P is true or not P is true. And then you're like, that's just always true. And it's like, wow, I verified it. Amazing. I'm so good at this. Especially when you deal with what's called liveness properties, properties about how like a system can evolve over a long period of time. It just it's hard to put down. It's just not good at that yet. And often I found with my clients, I have to tell them like it's doing a good job at generating the actual design, but in actually expressing what the design is supposed to do, it cannot do that yet. You have to do that part yourself.

</details>

**Speaker B**: 很有意思，因为在一年多前，也就是 2025 年 3 月，有一篇博客文章——我也会把链接放在节目注释里——标题是《分布式系统即将到来的革命》（The Coming Revolution in Distributed Systems）。作者是一位在 GitHub Copilot 团队工作的工程师。这个人在文章里写道，AI 如何从 Azure 存储的生产环境源代码中自主生成精确的 TLA+ 规范，并发现了一个避开了传统代码审查的微妙竞争条件（race condition）。然后这个人非常热情地说，这可能是一场革命，AI 完全可以像在 Azure 上那样，直接从规范需求中生成 TLA+ 代码。那是一年前的事了，尽管当时的模型还没有那么强大，但我之后并没有听到太多关于这方面的消息。在这个领域你都看到了些什么？

<details>
<summary>Original English</summary>

**Speaker B**: It's interesting because there's a blog post that I'll also link in the show notes from a year ago in March 2025 titled "The Coming Revolution in Distributed Systems". And this was an engineer working on GitHub's Copilot team. And this person wrote how AI autonomously produced precise TLA+ specifications from Azure storage production source code and it uncovered a subtle race condition that had evaded traditional code reviews. And then this person was very enthusiastic and saying well this could be a revolution, AI could just generate TLA+ from specification like it did with Azure. This was a year ago and I haven't heard much on any of this even though the models were not as great. What have you seen in this area?

</details>

**Speaker A**: 实际上，同一个人 Chang Huang 确实提出了一个叫做 Lamport Agent 的工具，他们演示了使用这个工具来规范 CRAQ 的某些部分，我想那部分被称为 DC's CRAQ。我会在资料里附上这两个链接。这是我的回应，因为我当时正在写这方面的内容，然后就看到了他们做的事情。在生成属性方面，他似乎比我成功得多。但是，至少他在后来的文章中展示的例子说明了一点：首先，他是一个专家级的规范编写者，即使没有 LLM，他也已经知道如何自己完成这些工作，所以这让他做起来更容易。是的，他知道如何利用 AI 获得好的结果。

<details>
<summary>Original English</summary>

**Speaker A**: So actually the same person Chang Huang did come up with a tool called Lamport Agent where they demonstrated using this to specify parts of CRAQ I think it's called part of DC's CRAQ. I'm going to link both those in the thing. Here's my response because I was writing about this and then the thing that they did. He seemed to be a lot more successful than I was at generating properties. But at least the example that he showcased in his later piece, one, he's an expert specifier who already knows how to do this stuff on his own without the LLM so that makes it easier. Yeah, he knows how to get good results out of it.

</details>

**Speaker B**: 因为这也是我们观察到的一个普遍现象：想要获得好的结果，你必须已经知道在没有 AI 的情况下该如何获得好的结果，它只是帮你更快地获得好结果。而且，他能够用 TLA+ 为其创建复杂属性的系统之一，已经有了一个用 P 语言编写的非常复杂的规范。所以我不知道这在多大程度上相关，也许 AI 读取了那个规范并且作弊了。也许这也没什么。我不知道。

<details>
<summary>Original English</summary>

**Speaker B**: As that's a general thing we've seen, like to get good results you have to already know how to get good results without it, it just helps you get good results faster. And also one of the systems that he was able to create the complicated properties for in TLA+ already had a sophisticated spec written in P, so I don't know how much that's relevant here, maybe it read that and it cheated. Maybe that was fine. I don't know.

</details>

**Speaker B**: 但我们确实经常看到这种情况：当你是某个领域的专家时，无论是软件工程、后端还是移动端，AI 对你来说会更有效。另外，还有一位非常有趣的人 Claudia Collie 写了一篇报道，因为她刚刚完成了一个在一家大型中国云服务提供商使用形式化方法（formal methods）的多年项目。在报道中，她谈到了在她撰写这篇论文和最终发表的这段时间里，她非常清楚在这家公司人们编写形式化方法需要多长时间，然后 LLM 基本上在她真正发表论文时就已经大大压缩了这个时间尺度。因此，我认为人们正在看到形式化方法的更多应用，但似乎目前最成功的人是那些利用 AI 来增强自身规范编写能力的专家。我们还没有真正看到——我的意思是，人们经常在 Hacker News 上发帖，说他们让 AI 为他们编写了整个规范，但那些往往并不是很好的规范。那么你的看法是什么？我又听到一些声音说，基于这一点，AI 可能会让形式化验证成为主流。但在那些已经知道如何进行形式化验证的小众群体之外，你看到任何实际的进展了吗？

<details>
<summary>Original English</summary>

**Speaker B**: But we do see this a lot where when you're an expert in a domain, and may that be software engineering or backend or mobile, AI works better for you. Then there's also this one interesting person Claudia Collie did write a write up because she just did about a multi-year project in using methods at the big Chinese cloud provider where she talks about how in between her working on this paper and the time she got published she got really sophisticated on how long it took people to write formal methods at this one company and then LLMs basically just compressed the scale by the time she actually had the paper out. So I think people are seeing more use from formal methods but it seems people with the most success right now are specifiers who are using it to amplify their ability to specify and we haven't yet really seen—I mean people post Hacker News all the time like people who they had an AI write the whole spec for them but those tend to not be very good specs. And what's your take on, again I've heard some voices say that AI might make formal verification go mainstream based on this, but outside of this niche of people who already know how to do formal verification, do you see any movement?

</details>

**Speaker A**: 我认为它确实在让形式化验证变得更受欢迎。我不知道它是否会让其成为主流，但它绝对让它变得受欢迎得多。它可能将普及率从 0.1% 提高到了 0.3%。这是一个巨大的进步。

<details>
<summary>Original English</summary>

**Speaker A**: I think it is making it more popular. I don't know if it'll make it go mainstream, but it's definitely making it a lot more popular. It's bringing it from maybe like 0.1% to 0.3%. Which is huge.

</details>

### AI as a Force Multiplier

**Speaker B**: 还有一种观点，我其实在你 2025 年 6 月的通讯中读到过，你说 AI 是一种“规范编写的力量倍增器”。当然，现在我们看到 LLM 在编写规范方面表现很差。从你一年前认为它们做得相当不错或者初露锋芒，到现在我们有更多证据证明它们不够好，这期间发生了什么变化？

<details>
<summary>Original English</summary>

**Speaker B**: There's also this thinking that I've read actually in June 2025 in your newsletter, you said that AI is a specification force multiplier. And now, of course, we see that LLMs are bad at writing specifications. What changed between that time where you saw that they were like a year ago they were pretty decent at doing it or they had signs and now we have a bit more proof they're not as good?

</details>

**Speaker A**: 其实我当时写的是，它在修复语法错误方面非常出色，这非常重要，因为语法错误经常会把人绊倒。它在理解错误追踪（error traces）方面也做得很好，这也是个巨大的优势，因为能够提取一个 35 步的错误追踪，并将其转化为大概两段英文文本，这是一个重大的改进。它还擅长处理样板代码（boilerplate），比如对大量小问题进行批量修改，像是更新样板代码。而且，如果有一个非常精确的描述，它在编写属性方面也表现尚可。但它不擅长修复规范，在为规范提供属性方面则非常糟糕。哈，我现在的观点和当时还是一致的。

<details>
<summary>Original English</summary>

**Speaker A**: So what I wrote that it was really good at was fixing syntax errors which is really big because that often trips people up. It's good at understanding error traces which is huge because being able to take a 35-step error trace and turn that into two paragraphs of English text, major improvement. Good at boilerplate like mass changes to a bunch of small things like updating boilerplate, and it's okay at writing properties from a very precise description. It's bad at fixing specs and it's real bad at providing properties for a spec. Ha, I'm still consistent.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 所以，我觉得我在早期就指出它在这方面真的很差。它擅长将属性从精确的英语转化为规范，但它不擅长自己想出属性。我得到的反馈全都是微不足道的琐碎内容。我知道如果你对实现细节不够了解就会这样。所以，我想最终我要表达的是：我认为它在改进工作流程方面有很大的潜力，但即使在 2025 年那个时候，我也已经注意到它在这一项特定任务上非常糟糕，而且直到今年 3 月，它在这方面的表现依然很差。

<details>
<summary>Original English</summary>

**Speaker A**: So, I think I called that early back then that it is really bad. It's good at translating properties from precise English into a spec, but it's bad at coming up with properties on its own. Everything I got back was trivial. I understand you're too cold with the implementation details. So I think ultimately what I'm going to say is that I think it has a lot of potential to improve things, but even back then in 2025 I was noticing that it was really bad at this one thing that it continued to be bad as of March of this year.

</details>

**Speaker B**: 那么你认为，为了能让 LLM 帮到你，你究竟需要对形式化方法了解多少？可能至少得掌握基础知识。

<details>
<summary>Original English</summary>

**Speaker B**: So then how much do you think you really need to know formal methods to be able to use LLMs to help you at all? You need to get the basics in place likely.

</details>

**Speaker A**: 我认为在这里掌握基础知识是非常有价值的，对吧？因为首先，我的意思是，即使不考虑能够编写属性之类的事情，你也需要能够判断 AI 什么时候做错了，对吧？如果你不懂基础知识，你真的很难做到这一点。

<details>
<summary>Original English</summary>

**Speaker A**: I think getting the basics in place is really valuable here, right? Because for one, I mean, even discounting being able to write the properties and all that, you need to be able to tell when the AI is doing something wrong, right? And if you don't know the basics, you can't really do that very well.

</details>

### Logic for Programmers

**Speaker B**: 在你的《程序员逻辑》（Logic for Programmers）一书中，你提出形式化逻辑可能是日常工程中最有用的部分之一。这是为什么呢？

<details>
<summary>Original English</summary>

**Speaker B**: In your book, Logic for Programmers, you argue that formal logic is probably one of the most useful parts for day-to-day engineering. Why is this?

</details>

**Speaker A**: 首先，我很荣幸你读了我的书，或者至少是早期草稿。我的意思是，官方的回答是：因为逻辑教会我们如何处理布尔值（booleans）和语句，就像我们在小学学习如何处理数字一样。从本质上讲，知道“1 加 1 等于 2”和知道“真且真为真”之间并没有太大的区别，它仍然是对值的操作。而且碰巧布尔值对软件工程如此重要，以至于在这方面拥有一些形式化的基础非常方便，特别是在我们在学校里基本上没有学过这个的情况下。另一个回答是，我只是在学习逻辑、提高逻辑能力，以及在教授 TLA+ 的过程中大量讲授逻辑时，我发现越来越多的应用场景让我觉得：“哦，正因为懂逻辑，我才能做这一件事”，而且我发现那些没有这种背景的人在做这件事时会很挣扎。我想我的意思是，从经验上来看，逻辑不断被证明是一种非常有用的数学形式。

<details>
<summary>Original English</summary>

**Speaker A**: First of all, I'm honored that you've read my book, or at least the early drafts. I mean the official answer is because logic teaches us to work with booleans and statements what we learn in elementary school how to work with numbers right essentially there's not a whole lot of difference between knowing that 1 plus 1 is two and true and true is true it's still the manipulation of values and it happens that booleans are so important to software engineering that having some formal grounding in that is very handy especially when we are not taught that in school for the most part. The other answer is that I've just on learning logic and getting better at logic and teaching logic a lot as part of teaching TLA+ I just finding more and more applications where I'm like oh because of logic I can do this one thing and I find that people who don't have that background struggle to do that one thing. I guess I'm saying that empirically logic keeps coming up as a useful form of math.

</details>

**Speaker B**: 如果我是一名软件工程师，而且我从事的是复杂的分布式系统开发，你会推荐我研究哪些技术来强化这些系统？我们可以假设我已经在做基本的单元测试，可能还有集成测试，但我现在感兴趣的是，我是否应该去研究形式化方法或基于属性的测试（property based testing）？如果是形式化方法，有这么多不同的技术，简直让人眼花缭乱。那么，如果只是想做一些成本较低的实验，从哪里开始比较好呢？

<details>
<summary>Original English</summary>

**Speaker B**: And if I'm a software engineer and I work on complicated distributed systems, what techniques would you recommend that I look into to harden these systems? We can assume that I'm already doing basic unit testing, potentially integration testing, but I'm now interested in like, well, should I look into formal methods, property based testing? If it's formal methods, there's all these different technologies. It's almost overwhelming. What is a good place to start to just do some experiments that are cheap to do?

</details>

**Speaker A**: 在这里我要完全转个 90 度的弯，向你推荐南希·莱文森（Nancy Leveson）写的一本书，叫《设计更安全的世界》（Engineering a Safer World）。她是一名前航空工程师，调查过像 Therac-25 医疗辐射事故和哥伦比亚号航天飞机失事这类事件。她对系统如何发生事故，以及为什么复杂系统中会发生事故非常着迷。我发现她在这一领域的著作极其深刻，对于理解这些系统是如何崩溃的有着不可估量的价值。因此，这是我首先推荐你去查阅的东西。

<details>
<summary>Original English</summary>

**Speaker A**: I'm going to just completely go 90 degrees here and recommend this book by Nancy Leveson called Engineering a Safer World. She was an aeronautics engineer who investigated things like the Therac-25 radiation case and the Columbia disaster and she was really fascinated in how systems have been accidents and why accidents could happen in complicated systems and I found her writing on this to be incredibly insightful and incredibly valuable in understanding how these systems can break. So that's the thing at first I'd recommend is checking out that.

</details>

<!-- chunk 11/12 -->

### 回顾一年前的行业预测

**Host**: ……书。展望一年前的整个行业。你当时写了一篇文章，分享了一些不确定性和焦虑。那是一篇很长的文章。呃，文章开头提到“感觉编程（vibe coding）永远无法像经验丰富的软件工程师那样做出优秀的软件工程”，你写了六件不同的事情。我们能一起读一读这些预测，然后反思一下你现在的感受吗？你认为有哪些可能已经改变了，或许我们也可以聊聊，因为现在的变化实在太多了，我们可能有了哪些新的焦虑。这是肯定的。

<details>
<summary>Original English</summary>

**Host**: book. looking ahead for the industry a year ago. You wrote a post where you shared some of the uncertainties and anxieties. It was a longer post. Uh it started with how VIP coding will be never good as software engineering experienced software engineers and you wrote six different things. Can we read through them and and just reflect on how you feel about them? What you think might have changed and and maybe talk about what potential new anxieties we have because there's so much change going on. That's for sure.

</details>

**Guest**: 我的大致想法是，未来五年的剧本基本上每隔几个月就会被重写一次，对吧？

<details>
<summary>Original English</summary>

**Guest**: >> The way I sort of think about it is that the next five years keep being rewritten every few months, >> right?

</details>

**Host**: 是的。

<details>
<summary>Original English</summary>

**Host**: >> Yeah.

</details>

**Guest**: 所以我写了以下几点，它们可能都是真的。第一，“感觉程序员（vibe coders）”永远无法像经验丰富的软件工程师那样擅长软件工程。这很可能是真的。我的意思是，如果你没有打好基础，你确实无法做到……

<details>
<summary>Original English</summary>

**Guest**: So I wrote the following can all be true. One, bibec coders will never be good at software engineering as an experienced software engineer. Probably true. I mean, if you don't have the basics, you can't really

</details>

**Host**: 感觉确实如此。甚至当我自己尝试在一个我不精通的领域（比如游戏开发）编写软件时，我就能体会到这一点，那绝对是一团靠“感觉编程”弄出来的烂摊子。

<details>
<summary>Original English</summary>

**Host**: >> It feels true. I I I even see it on myself when I try to build a software in a domain I'm not an expert in, like a game, and it's an absolute just vibe coded mess.

</details>

**Guest**: 是的，大语言模型（LLMs）可以显著增强专业软件工程师快速编写高质量软件的能力。我认为这也是真的。我的意思是，即便你不让它写哪怕一行代码，只是能用它来问：“好的，这个 bug 是什么？bug 在哪里？”或者是“嘿，我应该研究哪个库来解决这个问题？”并且我认为，我们开始看到或者开始认识到，那些拥有深厚知识的工程师，他们的效率要高得多。而那些拥抱这些工具、弄清楚如何控制它们，而不是被它们控制——你懂的，比如控制他们的焦虑之类——的人，他们能完成非常多的工作。

<details>
<summary>Original English</summary>

**Guest**: >> Yeah, LMS can significantly augment a sign a professional software engineer's ability to quickly write high quality software. I think also true. I mean, even if you don't have it writing a single line of code, just being able to be like, okay, what's this bug? Where's the bug? Or like, hey, what library should I look into to solve this problem? And we're I think we're starting to see or starting to recognize that engineers who have really deep knowledge are so much more efficient. And the ones who embrace these tools and figure out how to control them and not them to control, you know, like like their anxiety or whatnot, they get a lot done.

</details>

### AI 对软件开发工作机会的影响

**Host**: 绝对如此。大语言模型会导致许多软件开发者失业。

<details>
<summary>Original English</summary>

**Host**: >> Absolutely. Elements will cause many software developers to lose their jobs.

</details>

**Guest**: 这个我不知道。这很难下定论，因为我的意思是，第一，至少在美国，软件工程行业正在开始复苏。比如我们开始看到软件开发开放了更多的工作岗位。所以很难分辨，过去几年的失业到底有多少是因为 AI 造成的，又有多少是因为零利率政策时代的结束以及疫情后的经济衰退造成的。而且我认为主要是后者，但是同样，大语言模型还在变得越来越好。也许它们未来真的会导致失业。

<details>
<summary>Original English</summary>

**Guest**: I don't know. That's a hard one to pin down because like I mean one the software engineering at least in the US is starting to recover. Like we're starting to see more jobs open up for software development. So it's hard to tell how much of like the loss of the past few years was AI versus the end of like zero interest rate policy and like the postcoid crash. And I think it's more the latter but like again LM are still getting better. Maybe they're going to cause job losses in the future.

</details>

**Host**: 是的，这是一个很好的问题。我们在《The Pragmatic Engineer》里的数据显示，美国整体的软件工程职位空缺正在增加，而德国和法国的职位数量同时有略微的下降。而且现在在招聘谁、看重什么技能方面，似乎正在发生巨大的转变，所以现在 AI 工程正在日益扩散到更多的软件工程细分领域中，尽管不是所有领域；同时，我们看到例如前端工程师和移动端工程师的招聘数量在下降。所以我认为行业的形态正在改变，但它在过去也一直在变。如果你回想 20 年前，需求量最大的工程师是 Java 工程师，就是专门写 Java 的，比如那种不管怎样都需要 10 年 Java 经验的岗位，但那已经改变了。好，那么我们将为许多，可能非常多的软件开发者开放新的工作岗位。

<details>
<summary>Original English</summary>

**Host**: >> Yeah, this is a noble question. the data that we had in the pragmatic engineer it did show that we are seeing overall more software engineering openings in the US in Germany and France they're declining a little bit at the same time and there seems to be a big shift on who is being hired and the skill set so now AI engineering is increasingly spreading to more software engineering fields not all of them and we're seeing a decrease in for example front-end engineering hiring mobile engineering hiring so I think the shape is changing but it's always changed in the past if you think about 20 years ago the most in demand engineer was a Java engineer like Java specifically like don't care 10 years of Java experience required and that's changed >> okay then we'll open up new jobs for many possibly far many software developers

</details>

**Guest**: 我认为那也是真的。我认为当你原本需要五名开发者来构建产品，现在基本只需要一名开发者时，你会倾向于只雇佣那一名开发者，对吧。

<details>
<summary>Original English</summary>

**Guest**: I think that's also true I think when you basically need one developer to make your product as opposed to five you're looking to hire one developer right

</details>

**Host**: 那倒是真的，是的。

<details>
<summary>Original English</summary>

**Host**: >> that's been true yeah y

</details>

**Guest**: 大语言模型开启的这些软件工作岗位，薪酬会低于2008年到2022年科技时代的巅峰水平。而最让我害怕的事情是，正如我所提到的，我决定离开之前的领域，就这么成了一名技术人员。我做到了。并且我找到了一份薪水丰厚的工作，这甚至引领我现在能够全职去用数学方法证明系统的正确性。这太疯狂了。还有哪个领域能让人就这样，还有哪个工程领域能像这样，我说“我想成为一名工程师”，然后就直接踏入这个行业？还有哪个领域会把人从美国送到布达佩斯去发表 45 分钟的演讲？我们在这里拥有的一切真的非常宝贵和神奇，我很害怕失去它。我害怕软件行业变成一个仅仅像其他任何白领工作一样的地方，每年你有两周的带薪假期和大概两天的病假，我不想失去这一切。

<details>
<summary>Original English</summary>

**Guest**: >> the software jobs that LLM open up will be lower paid to lower precision the heights of the 2008 to22 tech era and that's the thing that scares me the most is that as mentioned I decided to leave a field and just become a techie. And I was able to do that. And I was able to get a well-paying job that led to me to now full-time mathematically prove systems correct. That's crazy. What other field can somebody just go like what other engineering field like I want to be an engineer and just walk straight into it? What other field is going to send people to Budapest from the US to give a talk for 45 minutes? Like it is really precious and magical what we have here and I'm afraid of losing that. I'm afraid of a place where it just becomes like any other like white collar job where you get two weeks paid vacation every year and like two days off sick and I don't want to lose that.

</details>

**Host**: 我们的意思是不是，我们害怕软件工程可能会变得和其他所有工程工作一模一样？是的。

<details>
<summary>Original English</summary>

**Host**: >> Are we saying we're afraid that software engineering might become just like every other engineering job? Yes.

</details>

**Guest**: 因为那就是许多工程工作的现实。我们确实拥有特权。我觉得在把它和其他工程工作进行比较时，我们并没有探讨到这一点。我们享有巨大的特权。

<details>
<summary>Original English</summary>

**Guest**: >> Because that is the reality of a lot of engineering jobs. We do have a privilege. I I don't think we talked about it when we compared with the rest of engineering. We have massive privilege.

</details>

**Host**: 是的。我们拥有极其巨大的特权，我不想失去它。我的意思是，如果其他所有人都能得到我们现在拥有的这些福利，那就太好了；但我不想通过失去让软件工程如此神奇和珍贵的特质，来让我们被“拉平”。

<details>
<summary>Original English</summary>

**Host**: >> Yes. We have a huge amount of privilege and I don't want to lose that and I I mean it would be nice if everybody else got the same things we are but I don't want to like equalize us by losing what makes software engineering so magical and precious.

</details>

**Guest**: 是啊，所以这是一个担忧。

<details>
<summary>Original English</summary>

**Guest**: >> Yeah. So this is a worry.

</details>

**Host**: 是的，那也是我的恐惧。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. That's my that's my fear.

</details>

### 高薪岗位的竞争与未来预测

**Guest**: 接下来是第六点：高薪的专业软件工程岗位依然会存在，但它们会变得稀缺，竞争更加激烈，并且对开发者的友好程度会降低。

<details>
<summary>Original English</summary>

**Guest**: >> And then number six >> there will be still be high paid professional software engineering jobs but they will be rare, more competitive and more and less developer friendly.

</details>

**Host**: 我担心我们已经看到了一些这方面的迹象。我想知道这是否是不可避免的。嗯，我也在其他一些行业看到了这种情况。例如投资银行，以前很多交易员都拿着极高的薪水，备受尊重。现在他们的人数减少了，依然高薪且受人尊重，但要进入那个领域变得更难了。

<details>
<summary>Original English</summary>

**Host**: >> I'm afraid we're seeing some of this already. I I wonder if this is inevitable. Um I also see it in some other industries. For example, with investment banking, uh the the traders used to be many of them very highly paid, highly respected. There are now fewer of them still highly paid, highly respected. It's harder to get into them.

</details>

**Guest**: 是的，我的意思是，我认为大多数工作随着时间的推移确实都会变得僵化，就像标准被制定下来，并且越来越多的人进入这个领域。嗯，我认为软件工程在很长一段时间里都能够侥幸避开这种情况。

<details>
<summary>Original English</summary>

**Guest**: >> Yeah. I mean, I think I think like most jobs do oify over time like as like the standards are set and more people enter them. Um sovereignty I think for a longer period of time was able to like get away from that.

</details>

**Host**: 确实。然后，一年前你用这样几句话结束了你的预测。

<details>
<summary>Original English</summary>

**Host**: >> Yeah. And then and and then you closed your prediction uh with with with these lines a year ago.

</details>

**Guest**: 我预测在未来 10 年，软件开发将会继续存在，但它会变得像其他任何白领专业工作一样。不再有 20 万美元的起薪、狂热的氛围，或者令人难以置信的员工议价能力。我会因为我们将失去如此神奇的东西而感到伤心，但我想它本来就不可能永远持续下去。自动化终会降临到我们所有人身上，甚至包括我们这些制造自动化的人。这里有一个非常疯狂的结尾方式，其实刚好能跟前文呼应。如果我们从“自动化终会降临到我们所有人身上，甚至包括我们这些制造自动化的人”开始说起的话。一方面，我觉得自己正在失去一些非常特别的东西。另一方面，我的一位医生朋友几个月前跑来找我说：“嘿，我们给医院弄出了一个新的轮班排班平台用来换班，这真的给我们所有人省了大量的时间，让我们所有护士和医生的生活变得快乐多了。”而且我就是靠“感觉”把它弄出来的。我不懂任何代码，但是 AI 让我做到了这件事。我当时的反应是，“哇，它确实在你的医院里帮助到了你们，让你们的生活变得更好。”所以这感觉非常奇怪，我要如何平衡我作为专业软件开发者的需求，与他作为医生的需求呢？到底谁的需求更重要？是我那份轻松惬意的工作，还是他的工作？我不知道。而我们所有人都会在接下来的 10 年里找到这个答案。我想。

<details>
<summary>Original English</summary>

**Guest**: >> I predict that in the next 10 years software development will survive, but it will become like any other white collar professional work. No more $200,000 salaries, a lunification, or incredible employee bargaining power. I feel sad that we'll lose something so magical, but I guess it couldn't have last forever. Automation comes for all of us, even us automators. Here's a crazy way of ending this actually fits in the backling. If we start with automation comes for all of us, even automators. And like on one hand, I feel like I'm losing something really special. On the other hand, a doctor friend of mine came to me like a few months back and was like, "Hey, we managed to like create a new shift scheduling platform for like our hospital like to trade shifts that really saved us all a lot of time and like made all of us nurses and doctors so much happier." And I was able to just vibe it out. I don't know any kind of code, but like AI let me do this. And I'm like, "Wow, it really is helping you like in your hospital make your life better." And it's like it it feels so weird to balance my needs as a professional software developer with like his needs as a doctor. Like who matters more? like my cushy job or his job. Like I I don't know. And it's going to we're going to all find this out in the next 10 years. I guess

</details>

### 软件的民主化与未来

**Host**: Grady Woo 曾对我说，现在这个时代让他想起了 20 世纪 60 年代末和 70 年代初的那个时期，那时人们可以购买电脑并开始用它们进行极客般的黑客式开发。他说那是一个神奇的时代，因为教师，以及完全跟软件不沾边的人，也会攒钱买电脑，并开始折腾它们，这使得计算机技术实现了民主化。我觉得这是我第一次也有了这样的感觉，就像健身房里的另一个人对我说的那样，他们在一起靠“感觉”写出了一些东西。感觉这个领域正在被打开，不管怎么说，越来越多的人正在意识到：噢，软件很酷。我能做到它，而且他们现在也终将开始学习软件工程中困难的部分。

<details>
<summary>Original English</summary>

**Host**: >> Grady Woo told me that this time reminds him of the time in the 19 late 1960s and early 1970s where people could purchase computers and start to hack with them. And he said it was a magical time because teachers and people who had nothing to do with software saved up and start to just hack around and it democratized it. And I feel this is the first time I'm also feeling like this other person in the gym told me that they're vibing something together. It feels it's opening up the field and if anything a lot more people are realizing, oh software is cool. I can do it and now they're starting to learn the hard parts of software engineering eventually.

</details>

**Guest**: 你有没有读过 Clay Shirky 的文章《情境化软件》（Situated Software）？

<details>
<summary>Original English</summary>

**Guest**: >> Did you ever read up Clay Sher's essay situated software?

</details>

**Host**: 没有。

<details>
<summary>Original English</summary>

**Host**: >> No.

</details>

**Guest**: 它的基本内容是，这个人当时谈到了他如何认为，绝大多数软件都应该只为三个人开发，或者为一个家庭、一个社区、或者一所学校开发。然而直到现在，这种情况只有当那个家庭、那个社区、或者那所学校里的人极其热爱计算机时才可能发生。但是现在，每个人都有可能拥有情境化的软件，这必将再次以一些奇怪的、可怕的、以及令人兴奋的方式改变世界。

<details>
<summary>Original English</summary>

**Guest**: Basically what it is is that this person was talking about um how they think like the most important the vast majority of software should be made for like three people or like a family or community or like one school. And up until now that like could only really happen if one of those people in that family that community that school was like really really into computers. But now it's possible for everybody to have situated software and that again is going to change the world in some strange and some terrifying and some exciting ways.

</details>

**Host**: 这太令人激动了。作为收尾，有哪些书……

<details>
<summary>Original English</summary>

**Host**: >> It's exciting. As closing, what are books, a

</details>

<!-- chunk 12/12 -->

### 书籍推荐

**Host**: 有没有什么你很喜欢，或者对你产生过影响的书可以推荐给大家？

<details>
<summary>Original English</summary>

**Host**: few books that you could recommend that you have enjoyed or made an impact on you?

</details>

**Hill**: 哎呀。我们还是把范围限制在软件相关的书吧，好吗？不然我们在这儿聊上一个月也聊不完。在软件领域，有三本书我非常喜欢，我把它们看作是对我影响至深的书籍。

<details>
<summary>Original English</summary>

**Hill**: >> Oh boy. Let's just leave this just for this into just software books, okay? Because otherwise we're going to be here for like a month. So there's three books that I really love in software that I think of as like the books that have influenced me so much.

</details>

**Hill**: 第一本书，我想我在之前的采访中提到过，是 Nancy Leonson 的《Engineering a Safer World》（构建更安全的世界）。我相信这本书在网上是可以免费阅读的。第二本书叫做《Data and Reality》（数据与现实），作者是 Bill Kent。

<details>
<summary>Original English</summary>

**Hill**: The first one I think I mentioned in the interview was um Nancy Leonson's Engineering a Safer World. I believe that's actually free online. The second book is called Data and Reality by um Bill Kent.

</details>

**Hill**: 这本书其实很难找了，因为在，我想是2011年吧，它被重新出版过，但出版商改动了书的内容。所以最后一个好的版本是第二版，你可能得在互联网的某些黑暗角落里才能找到，在网上找确实挺难的。不过，这基本上是一位曾在 IBM 做过数据库的著名数据库设计师写的，他只是在问：什么是数据？某物拥有身份意味着什么？某物具备唯一性意味着什么？如果我们谈论一本书，那是指这本实体书，还是这个系列，又或者是一个版本？

<details>
<summary>Original English</summary>

**Hill**: And this one's actually hard to find because it was republished in 200 I think 11, but the republisher changed the book. So the last good edition is is the second edition which can be found like in dark corners of the internet online is actually kind of hard but like it is basically by this like famous database designer who like worked on like IBM databases who was just asking like what is data? What does it mean for something to have identity? What does it mean for something to have oneness? If we talk about a book is that the book the physical copy is that the series is that an addition?

</details>

**Hill**: 这整本书都在探讨关于什么是数据，以及我们需要如何去表示它的问题。他在书的结尾说道，数据并非现实。它是我们为了自身的实用目的而对现实产生的一种看法。这是一本令人难以置信的书。它完全改变了我思考问题的方式。

<details>
<summary>Original English</summary>

**Hill**: And it's just an entire book about these questions about what data is and how we need to represent it. He ends it by saying that data isn't reality. It is our view of reality for our useful purpose. Incredible book. It totally changed how I think about things.

</details>

**Hill**: 最后一本书叫做《Debugging: the nine simple rules》（调试的九条简单规则），作者是 David Aens。这本书字面上就像是一本关于调试的“战争故事”集，以及一些基本原则。但这是我送给每一位初级工程师的书，因为我觉得好像从来没有人真正把调试当作一门学科来讨论，而不仅仅是一些基本的启发式方法。

<details>
<summary>Original English</summary>

**Hill**: The last book is um called debugging the nine simple rules by David Aens. And it's literally just like a book of war stories about debugging and like basic principles. But this is the book I give to every junior engineer because I think like nobody ever really talks about debugging as like a discipline outside of like basic heristics.

</details>

**Hill**: 这本书至少是在尝试做这件事，在这个类别里，有总比没有强。所以这是一本非常好的书，而且我想买本二手书大概只要10美元。所以任何人都可以轻松买到一本。非常棒。我认为这三本就是对软件工程师来说最有用的书了。如果你想聊聊其他的书，我可以继续讲，但[笑声]

<details>
<summary>Original English</summary>

**Hill**: this is like just at least something that's trying to do that and having something is better than nothing in this category. So really good book and I think it's like $10 for a used copy. So like anybody can just get one. It's great. Those I think are the three most useful books for software engineers. If you want to talk about other books I can keep going but [laughter]

</details>

### 总结与播客结语

**Host**: 这太棒了。大家好，这一期非常具有教育意义，我觉得非常吸引人。谢谢。谢谢。我真的很享受这次对话，尤其是 Hill 展示诸如 TLA+、Alloy 或者 Hypothesis 等工具，以及它们如何捕获 bug 的演示环节。

<details>
<summary>Original English</summary>

**Host**: this this is great. Well hello this was very educational and I found it fascinating. Thank you. Thank you. I really enjoyed this conversation, especially the demos where Hill showed tools like [music] TA+ alloy or hypothesis and how they can catch bugs.

</details>

**Host**: 到对话的最后，我开始更多地理解，为什么即使有了 AI，形式化验证也不太可能成为主流。我的意思是，这些工具对于现实世界来说感觉非常僵硬。对于系统中你可以进行数学建模的特定部分，比如状态空间，它们当然能起作用，但对于日常的程序来说，去创建 TLA+ 规范感觉有点毫无意义。

<details>
<summary>Original English</summary>

**Host**: By the end of the conversation, I'm starting to understand more why it's not likely that formal verification will go mainstream even with AI. I mean, these tools feel very rigid for the real world. For specific parts of a system that you can model mathematically, like state spaces, sure, they can work, but for everyday programs, it just feels like it would be a bit pointless to create TA plus specifications.

</details>

**Host**: 我还在思考的另一件事是，Hill 谈到他认为我们为什么不擅长捕获并发 bug，那是因为我们对它们缺乏足够的实践经验。[音乐声]作为一名开发者，你可能几年才有幸调试一次并发 bug。所以，你当然无法通过这种方式来积累专业知识。

<details>
<summary>Original English</summary>

**Host**: One thing that I was also thinking about is how Hill talked about why he thinks we're not good at catching concurrency bugs, and it's because we don't have much practice with them. [music] As a developer, you're lucky to debug a concurrency bug once every few years. So, of course, you won't be able to build expertise [music] this way.

</details>

**Host**: 这也类似于为什么大多数工程师都不擅长做迁移，因为大多数开发者在几年里也只会做一两次迁移。但如果你是一个做过大量迁移工作的工程师，你就会在这方面变得非常出色。同样，如果你一直在处理有并发问题的系统，你也会成为这方面的专家。

<details>
<summary>Original English</summary>

**Host**: This is also similar to how most engineers are bad at migrations because most devs only ever do one or two migrations over several years. But if you're an engineer who does a bunch of migrations, you're going to be really good at them. Same thing if you're working on systems with concurrency issues and you become an expert in this.

</details>

**Host**: 我还发现其他工程领域与软件工程存在相似之处，这一点非常迷人。比如采矿工程师在20世纪60年代也经历了他们自己的敏捷革命，以及所有的工程师都讨厌瀑布流的概念。[音乐声] 此外，听到源代码控制是我们软件工程师拥有，而其他工程领域羡慕却很少拥有的东西，也觉得很有趣。

<details>
<summary>Original English</summary>

**Host**: I also find it fascinating how other engineering fields have similarities with software engineering, like how mining engineers had their own agile revolution in the 1960s and how all engineers hate the concept of waterfall. [music] Plus, it was amusing to hear how source control is kind of an envy from other engineering fields that we software engineers have, but not many others do.

</details>

**Host**: 请查看节目说明，那里有在 TechDEP 上关于分布式系统的相关深度解析，对我们今天讨论的话题进行了更详细的探讨。如果你喜欢这档播客，请在您最喜欢的播客平台以及 YouTube 上订阅。如果你还能为本节目留下评分，那就特别感谢了。谢谢大家，我们下期见。

<details>
<summary>Original English</summary>

**Host**: Check out the show notes for related deep dives on distributed systems at TechDEP that go into more detail into the topics that we talked about today. And if you've enjoyed this podcast, please do subscribe on your favorite podcast platform and on YouTube. A special thank you if you also leave a rating on the show. Thanks and see you in the next

</details>