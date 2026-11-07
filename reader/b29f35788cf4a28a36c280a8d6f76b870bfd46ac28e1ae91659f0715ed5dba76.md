---
author: How I AI
date: '2026-06-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=QE_1hRLsehM
speaker: How I AI
tags:
  - coding-agents
  - evals
  - continuous-integration
  - ai-observability
title: AI 时代的软件工程：利用智能体应对复杂架构与自动评估
summary: 在本期播客中，Braintrust 首席执行官 Ankur Goyal 深入探讨了如何将 AI 智能体应用于高度复杂的架构和基础设施问题。他们不仅详细解析了自动化评估（Evals）的重要性与实操细节，还分享了如何优化开发者工作流、强化持续集成（CI），以及为何优秀的工程团队必须将构建数据反馈循环作为核心任务。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Braintrust
products_models:
  - Claude
  - Codex
media_books: []
status: evergreen
---
### 开场预告

**Clara**: 我们仍身处 2026 这样一个 Claude 的时代。但即便如此，我还是会听到工程师们说：“在面对我们最复杂的系统时，AI 无法做好这项工作。”

<details>
<summary>Original English</summary>

And still in, as I say, the year of our claude 2026, I still talk to engineers that say AI on our most complicated things cannot do a good job.

</details>

**Ankur**: 我在内心深处极其不认同这种看法。没有哪位主任工程师在手动运行那么多严谨的基准测试、尝试各种算法并分析想法时，能比那些使用智能体的人做得更多。每个人都应该对着镜子审视自己，重新评估他们是如何分配时间的。你每天有很多的互动交流、给出指导或是做各种决策，对我来说，其中的很多事情现在都处于“智能体能力基准线”之下了。我认为这条智能体能力基准线还在不断上升。

<details>
<summary>Original English</summary>

I so viscerally disagree with there's no staff engineer who is running as many rigorous benchmarks and trying out different algorithms and analyzing ideas manually than someone who's using an agent. Everyone should take a hard look in the mirror and re-evaluate how they spend their time. There's a lot of interactions that you have or direction that you're giving or decisions that you're making and I think like many of these things to me fit below the agent line. I think the agent line keeps going up.

</details>

**Clara**: 你为什么认为理解这个概念如此重要？对于那些对 AI 感到有些畏惧的人，你如何帮他们打破这种神秘感？

<details>
<summary>Original English</summary>

Why do you think this concept is so important to understand? How can you demystify it for folks who are a little intimidated by it?

</details>

**Ankur**: 既然模型在实际编写代码方面已经非常出色，我们能做的最重要的事情之一，就是创建难度极高的**评估标准（Evals）**。如果你为模型设定了正确的测试用例和成功标准，那么它就能发挥出强大的创造力，在后台处理这些工作，并真正尝试去改进一堆问题。

<details>
<summary>Original English</summary>

Now that models are so good at actually writing code, one of the best things that we can do is create really hard evals. And if you create the right tests and success criteria for a model, then it can be really creative and it can work on this stuff in the background and actually try to improve a bunch of things.

</details>

**Clara**: 我听到很多人说：“哇，如果我甚至要把自己的品味、技能或者专业知识都转化为一套系统，那我从功能上来说，就是在构建一个替代我自己的东西。”

<details>
<summary>Original English</summary>

I have a lot of people saying, "Wow, if I go as so far as to turn my own taste or my own skills or my own expertise into a system, I'm functionally just building my own replacement.

</details>

**Ankur**: 这样一来，我们就能够将 David（设计师）的品味应用到更多的事物上。我认为我们现在能够达到的质量标准变得更高了，因为我们能让更多的事物达到那样的标准。

<details>
<summary>Original English</summary>

We're able to have David's pallet applied to more things. I think the quality bar that we're able to hit is higher because we're able to get more things to that bar.

</details>

### AI 时代的软件工程

**Clara**: 欢迎回到《How I AI》。我是 **Clara**，一位产品负责人和 AI 狂热爱好者，我在这里的使命就是帮助你们利用这些新工具构建更好的产品。今天我请来了 **Braintrust** 的首席执行官 **Ankur Goyal**。这期节目非常硬核。所以，如果你是一位高级工程师或主任工程师，或者是工程副总裁和首席技术官，你绝对会想认真听这期节目。我们将讨论编程智能体如何帮助你解决那些极具技术挑战的架构和基础设施工作，且所能达到的效果是以前任何人类工程师都无法做到的。我们还会为观众揭开评估测试的神秘面纱，准确地向你展示如何利用它们来改进你的 AI 产品，而你几乎不用亲自动手去干预。让我们开始吧。本期节目由 Guru 赞助，它是贵公司知识的 AI 事实层。我们面临的痛点是：你的 AI 输出质量完全取决于你喂给它的信息。大多数公司之所以从 AI 那里得到看似自信却存在错误的回答，是因为它们底层的知识是过时的、不完整的甚至完全错误的。糟糕的信息不仅会拖慢你的速度，还会让你损失金钱并带来风险。Guru 通过在贵公司知识库和 AI 工具之间添加一个验证层，解决了这个问题。Guru 不会让你盲目指望 AI 把事情做对，而是会自动对内容的准确性进行评分，标记过时信息，并确保你的团队每次都能得到值得信赖的答案。它可以与你现有的工具协同工作，所以你不需要改变你的工作方式。数千家公司都信任 Guru 能够保持其 AI 系统的准确合规。准备好停止拿公司知识玩俄罗斯轮盘赌了吗？请访问 getguru.com 了解更多。欢迎来到《How I AI》，很高兴你能来这里。

<details>
<summary>Original English</summary>

Welcome back to how I AI. I'm Claraveo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have Anker Goyel, the CEO of Brain Trust. And this is a technical one. So if you're a senior or staff engineer or a VP of engineering or CTO, it's one you're really going to want to pay attention to. and we're going to talk about how coding agents can help you bite off really technical architecture and infrastructure work in a way that no other human engineer could before. We're also going to demystify evals for folks and just show you exactly how you can use them to make your AI products better without having to touch a thing. Let's get to it. This episode is brought to you by Guru, the AI layer of truth for your company's knowledge. Here's the problem. Your AI is only as good as the information you feed it. Most companies are getting confident but wrong answers from AI because their underlying knowledge is outdated, incomplete, or just plain incorrect. Bad information doesn't just slow you down. It costs you money and puts you at risk. Guru solves this by adding a verification layer between your company's knowledge and AI tools. Instead of just hoping your AI gets it right, Guru automatically scores content for accuracy, flags outdated information, and ensures your team gets trustworthy answers every time. It works with the tools you already use, so you don't have to change how you work. Thousands of companies trust Guru to keep their AI accurate and compliant. Ready to stop playing Russian roulette with your company's knowledge? Visit getguru.com to learn more. Welcome to How I AI. I'm excited to have you here.

</details>

**Ankur**: 能来到这里我超级激动，谢谢你邀请我。

<details>
<summary>Original English</summary>

I'm super excited to be here. Thanks for having me.

</details>

**Clara**: 说出来你可能会笑，但我最近做了一期关于 GPT 5.5 模型发布的节目，而且我知道你和我都在使用 **Codex**。在那篇文章里最搞笑的一条评论是：“Clara，你能做一整期关于技术债的节目吗？”我们录音前还在聊，你问：“这些听众懂多深的技术，有多硬核？”我说，放马过来吧。所以我们今天要聊聊你对工程开发的态度，以及你如何利用 AI 来优化那些慢查询。那么我们就切入正题吧。能跟我说说在 AI 时代，你对于软件工程开发的方法论吗？

<details>
<summary>Original English</summary>

So, I'm going to make you laugh, but I recently did an episode about the recent GPT 5.5 model release, and I know you and I use Codex, and one of the funniest comments in that post was, "Claire, can you do an entire episode about tech debt?" And we were talking before we got on the recording. You're like, "How technical and how nerdy is this audience?" And I'm like bring it on. So we are going to talk a little bit about how you approach engineering and then how you use AI to do things like optimize slow queries. So let's let's hop in. Tell me tell me about your approach to to software engineering in the age of AI.

</details>

**Ankur**: 你知道，我花了很多时间致力于评估和可观察性软件的开发，这深刻地塑造了我自己对于软件工程的看法。既然现在大模型在实际编写代码上已经那么出色了，我们能做的最好的一件事就是去创建难度极高的评估测试。我指的不仅仅是“AI 模型评估测试”，我指的是诸如“为什么这个查询这么慢？”这类的评估。如果你为模型设定了合适的测试条件和成功标准，那么它就能极具创造力，并在后台自动处理这些任务，真正帮你去优化各种问题。

举个例子，我现在花了很多时间在优化用户在我们的产品中运行的查询速度上。人们可以随意运行各种查询，比如在海量的数据追踪中“大海捞针”：在他们产品的数十亿条追踪记录中，他们试图找出那 5000 条匹配某种特定互动的记录。而且这可能是跨越 90 天之久的庞大数据量。这就是一种典型的慢查询。在数据库文献里，你可以找到一堆解决这类问题的办法：比如建立各种不同的索引、采取不同的数据预读取策略等等。但是，你要如何逐一去尝试所有这些方案？你要怎样才能跑完验证这些想法所需的大量实验？

我们现在的做法，也是我个人最近一直在做的，就是弄清楚用户运行这些慢查询的模式是什么——以前我们靠人工找，但用自动化甚至更好。接着，我们会复现这些查询，然后让一个**编程智能体**去尝试数据库文献中的各种思路。比如在本地下载一部分数据，然后尝试不同的方案。目前，我正在测试不同的**列存储格式**。我们在底层用了一个叫 tanty 的索引，它内置了一个列存储格式，但表现并不出色。它整体是个很棒的工具，但在列存储上差强人意。所以我们现在做的事情，就是让 AI 穷举测试市面上所有开源的列存储格式，然后穷举测试所有的列存储执行引擎，并自动计算出它们组合在一起的表现矩阵。说真的，这简直不可思议。

<details>
<summary>Original English</summary>

You know I spent a lot of time working on software for doing evals and observability and that's kind of shaped my own perspective about software engineering. Like now now that models are so good at actually writing code. One of the best things that we can do is create really hard evals and not I'm not talking about like AI evals. I mean things like why is this query so slow and if you create the right tests and success criteria for a model then it can be really creative and it can work on this stuff in the background and actually try to improve a bunch of things. So um one of the things that I spend a lot of time on right now is making the queries that people run in our product faster and people can just write arbitrary queries like you know they can there's an example someone is trying to find like needle in a haststack of some um specific kind of interaction someone had in their product and they're looking at like billions and billions of traces and they want to find like the 5,000 or something that match. And this is over like a 90-day period or something like a lot of a lot of data. And that's one example of of a query. And like okay, there are all these things that you can do in database uh literature like different indexes you can build and different ways you can prefetch data and blah blah blah all this stuff. But how do you try all those things and and and how do you um run all the experiments required to to actually do something like this? So what we do and what I've personally spent a lot of time working on is trying to figure out you know manually is fine but automatically is even better like what are the patterns of queries that people are running that are slow and then we will reproduce those things and use um a coding agent uh to try out a bunch of ideas from database literature. So like download a bunch of data locally and then maybe try different in this case right now I'm trying out different column store formats. So we use an index underneath the scenes called tanty which has a built-in column store um but it's not that great. Like the thing overall is great but their column store is not like that great. And so what we're doing right now is like exhaustively trying every open- source column store format out there and then exhaustively trying every column store execution engine out there and sort of computing the matrix of this and it's you know it's like it's amazing.

</details>

**Clara**: 我完全同意。作为一个长期领导工程团队的人，当你试图对应用的核心基础设施、平台组件做出调整时，由于实施成本高昂，且存在未知的风险盲区，团队在进行重大平台迁移或重构时往往是非常厌恶风险的。在工程方面，你很容易被当初交付的架构给困死。

而我现在非常喜欢 AI，尤其是这些**编程智能体**和 **Codex** 的一点是：引入 Codex 再配合这些 GPT 模型，这是我遇到的唯一一种能够搭建起类似流程的配置。你可以设定明确的目标：比如我们需要达到 XYZ 的结果。我们需要用程序自动对着那些长尾且复杂的数据结构进行测试，找出哪些潜在的方案能让我们离目标更近。在你的例子中，目标是数据库查询速度和延迟；在我这儿，你一定能感同身受——我当时正在进行一项非常复杂的由 AI 生成的结构化和非结构化数据的数据迁移。它一开始就是一团糟，然后我得把它迁移到一个新 Schema 中，那可是涉及数以百万计的数据行，还有极多的边缘边界情况。作为人类，要做完这些工作简直遥遥无期。你可以写个脚本，或者用一些系统去硬跑它，但人类再去管理这些循环、判断那是对还是错、或者这是否暗示我们该选左边的方案还是右边的方案的能力是很有限的。所以我确实觉得，当你拥有一个高度明确的结果目标，配合上一个聪明到能够在一大堆长尾问题中不断试错、并且对技术栈有一定认知引导的智能体时，它表现得非常好。

我还从未听过在数据存储端有类似的做法，这真的非常有趣。但我只是想对各位工程负责人说：我已经参与过太多次关于我们该用哪种数据存储、如何优化性能、哪些技术该引入技术栈而哪些不该引入的讨论了。而你现在可以通过迭代的方式去运行这些测试闭环。我假设你是在生产环境类似的数据集上，或者真实的代表性查询上来做测试，对吧？

<details>
<summary>Original English</summary>

I completely agree as somebody who has led engineering organizations for a really long time when you're trying to make infrastructure platform core component changes in your application because of both the cost of implementing those being very high and then the unknown unknowns being quite risky. Teams are actually pretty riskaverse in terms of making big platform shift shifts or changes to their core implement. It's like the thing that you shipped is the thing that you get stuck with certainly on on the engineering side. And what I love about AI right now and these coding agents in particular and then codecs in particular particular is it has been the only setup codec plus these GPT models has been the only setup where I have been able to set up a very similar process which is the outcome I want is XYZ. We need to programmatically test against pretty longtail data structures to figure out which of these potential solutions are going to get us closer to the outcome we want. In your instance, it's database query speed and latency. In my instance, I was doing a very, you can appreciate this very complex data migration of store like stored structured and unstructured data generated by AI. It was all like messed up to begin with and then I had to migrate it to a schema and so it was like schema to schema migration millions and millions and millions and millions of rows and lots of edge cases and doing that as a human takes forever. you know, you could script it and you can like bang um some systems against it, but then your human ability to manage those cycles and say yes, that's right or no, that's wrong or this gives us indication that we should go left or that gives us indication we should go right. And so I do feel like this combination of like a very precise outcome and an agent that's smart enough to bang its head against a really really long tale of problems with a guided sense of the technical space, it does really well. And I have not heard this on the kind of like data store side. It's really interesting. But I just think hey engineering leaders out there I've had I've been so many debates about what we're using for our data score, how we optimize performance, what technologies we should bring into the stack versus not. And you can run those like very very iterative loops on I'm I'm presuming you're using production-like data um or or real representative queries to to test that. Is that right?

</details>

**Ankur**: 你甚至可以直接用生产环境数据，但仅针对某个子集。只要把工程设施搭建到位，你完全可以直接跑在生产数据上。

<details>
<summary>Original English</summary>

You can actually use production data too, but for some subset of things and with the right engineering in place, you can just run on production data.

</details>

**Clara**: 是的。

<details>
<summary>Original English</summary>

Yeah.

</details>

**Ankur**: 而且在很多方面，这比让人类去在生产数据上做测试要安全得多，因为这样一来，没人真的在看那些数据。

<details>
<summary>Original English</summary>

And in many in many ways, it's a lot safer than having humans test on the production data because no one no one's looking at it.

</details>

**Clara**: 没错。而这正是我看到许多主任工程师对“AI 究竟能否在他们的代码工具中占有一席之地”表现得极其愤世嫉俗和怀疑的地方。就像我刚说的，在 Claude 大放异彩的 2026 年，我仍然听到工程师跟我说，AI 根本无法处理我们最复杂的问题。

<details>
<summary>Original English</summary>

Yeah. And this is where I have so many staff engineers be really really um cynical about does AI have a place in their their their coding tools. I'm still in, as I say, the year of our cloud 2026, we still I still talk to engineers that say AI on our most complicated things cannot do a good job.

</details>

**Ankur**: 噢，我发自内心地完全不认同这种看法。

<details>
<summary>Original English</summary>

Oh, I I I so viscerally disagree with that.

</details>

**Clara**: 我也是。跟我说说你为什么不认同。

<details>
<summary>Original English</summary>

Same. Tell me why you disagree.

</details>

**Ankur**: 嗯，我是这样想的。我在数据库领域深耕了将近二十年。没有什么比“从头构建一个数据库”更能套用那些关于资深工程师、厌恶风险等等的刻板印象了。我们最近在 Braintrust 里引入了一种非常炫酷的、基于**布隆过滤器**的索引功能。顺便一提，我们是在连续跑了整整一周针对不同索引类型的实验之后，才发现布隆过滤器是解决那个问题的实用方案。布隆过滤器名声可能不是很好，但在我们那个场景下，事实证明它们极为有效。

如果你在开发这样的功能，通常情况是：最出色的工程师会跑上几个基准测试，然后你发给你的同行评议，同事们会一顿狂喷，把你的方案批得体无完肤：“你没对这块做基准测试，你没测那个！”然后你怎么做？你会挑前几个最关键的基准测试优先跑一跑，剩下的可能就随缘或者糊弄过去了。你会说：“哎呀，那个情况我没测。不过你看代码嘛，复杂度又不是 O(N²)，而是 O(log N)，所以不会出什么岔子的。”而现实是，你有一半的时间是错的。

现在呢？现在**再也没有理由不去做那些基准测试了**。现在我们爱死了这件事。并不是说我要自己花时间坐在那儿一行行敲基准测试的代码；而是我们在讨论、看代码、看整个功能，然后我们会说：“好，我们已经通过基准测试验证了这让查询快了多少。那我们有没有好好测过它让索引过程变慢了多少？”“糟糕，还没测。”于是我们就会花时间去测，然后发现我们在索引效率上做得很差。接着我们就会花大量精力去优化那一块。

所以我不同意那种观点。我能理解，也对“模型不擅长写高并发代码”或者“写不好对性能极其敏感的代码”这种说法抱有同情。但现实是，没有任何一个主任工程师在人工运行时，能像那些使用智能体的人一样，跑那么多次严密的基准测试、试错那么多算法、分析那么多不同的思路。即便是智能体的那个基准下限，也已经非常不可思议了。

<details>
<summary>Original English</summary>

Well, I I mean, I think so. I've been working on databases for almost two decades. There's not many things that staff, whatever, risk averse, blah blah blah, all that stuff you could apply to than like literally building a database. If you work on a database, uh, we recently added this like fancy index thing into Brain Trust that uses Bloom filters. And by the way, we discovered that that would be a practical solution to the problem after running like a week of continuous experiments with different types of indexes. Bloom filters kind of have a bad reputation, but they they worked out to be very effective in this case. So if you if you if you build something like that, usually what happens is the very best engineers will run a few benchmarks and then you'll send it to your peers and then your peers will all over it and rip it apart and say, "You didn't benchmark this, you didn't benchmark that." And what you do is you prioritize the top few benchmarks and then you probably the rest. Like oh I, you know, I didn't benchmark this. However, if you read the code, you'll see it's not n squ, it's login and so this is not going to happen. And and like half the time you're wrong. Now there is no excuse to not do those benchmarks. So now I we love it. Like we don't I'm not spending my time like sitting and like typing the benchmark code, but I'm talking to people. We're looking at the code. We're looking at the thing. We're like, "Okay, well we index we we benchmarked how much faster it makes the queries. Did we actually do a good job of benchmarking how much slower it makes indexing?" Oh no, we didn't do that. And so we actually spent some time doing that and we discovered that we were doing a terrible job at indexing it efficiently. And so we spent a lot of time on that. And I I could sort of I I don't agree with this. I could some I I can empathize with the argument that models aren't good at writing highly concurrent code or they're not good at writing very performance- sensitive code. But the I there's no staff engineer who is running as many rigorous benchmarks and trying out different algorithms and analyzing ideas manually than someone who's using an agent. And even that baseline is just incredible.

</details>

**Clara**: 我同意。我认为这里存在“理论质量”和“实际质量”的差别，对吧？在一个理想的、理论中的世界，如果我们都不用睡觉，每次我们坐在笔记本前都能写出完美的代码，并且理论上所有的基准测试——不是那些糊弄人的，而是所有的测试都被跑完。在这个理想世界中，你或许可以在理论上说，在某些未经测试的边界情况里，人类亲自动手参与能获得更高的质量。

但实际应用情况是：仅仅过了几天，人类就会对手头这个问题的上下文逐渐失去记忆。面对那些虽然困难但极其枯燥繁琐的问题，你的注意力是在衰减的。因此我认为实际质量必然会下降。所以我总是对大家说，在解决高难度技术问题时，将 AI 整合进你的工程流程中，所带来的实际质量一定会提升，仅仅是因为借助 AI，你向问题发起的冲击力度能有多狠，以及你针对问题能够跑的持续时间能有多长。

这就回到了我刚才想说的另一点：有了 AI 作为你的开发助手，你可以啃下比以前有趣得多、也庞大得多的技术挑战。因为在实际层面上，你的公司现在能承担得起这种折腾的成本了，对吧？试想如果你去跟管理层说：“我想把我们所有的主任工程师都关小黑屋，接下来的整整一年只解决我们的数据库索引问题，我们就一头扎进各种细节里，我们会测试市面上六个不同的开源方案，一年后我们再告诉你到底搞没搞定。”

<details>
<summary>Original English</summary>

I agree. And I think there's this theoretical quality and then there's this practical quality, right? In a theoretical ideal world in which we don't sleep and every time we sit down at our laptop we we end up writing perfect code and in a theoretical world in which those benchmarks are all of them are run not just the BS ones. Like in that theoretical world you could theoretically say perhaps in some untested case you get better quality when when humans are hands-on. But the practical application is you lose context over like the humans lose context on the problem over days. You have a decaying attention span towards hard but tedious problems. And so I do think the practical quality goes down. And and so I tell people like the practical quality of integrating AI into your engineering process on very hard technical problems goes up simply because of how hard you can run at the problem and how long and consistently you can run against the problem. And then you know what I was going to go back to saying which is you can bite off much more interesting technical challenges with AI as your you know sidecar than you could before again practically because your company can support the cost of doing so right if you're like I want to sequester all my staff engineers to solve our database indexing problems for the next year and we're just like really going to go go deep in the weeds and we're going to test these six different open source you know, solutions to this and we'll come back in a year and we'll tell you if we figured it out, not that we figured it out.

</details>

**Clara**: 业务部门和 CEO 肯定会说：“想都别想，算了吧，谢谢。”但如果你说：“嗨，我们会让这个智能体在后台全自动跑测试，我们会定期检查进度并取得快速的进展。”那他们肯定会说：“好啊没问题”，而且同时你们还能兼顾发布其他的产品功能。我觉得这是一个非常容易通过的决策。

<details>
<summary>Original English</summary>

Business is like, "No, you know, you're you're they're a CEO." Like, no, no, thank you. But if you say, "Hey, we're going to have this thing in the background and we're going to check on it. We're going to make expedient progress." Sure. And we can ship other stuff while we're at it. I think that's a really easy Yes.

</details>

**Ankur**: 绝对是这样。我觉得我们现在的座右铭就是：没有任何借口不保持严谨。如果有人抱怨系统的某个方面，那就没有任何借口不去提升性能。如果有人抱怨用户界面里的一点小瑕疵，同样，我们没有任何借口。我们现在几乎没有所谓的积压工作了。就是没有任何借口不去改善这些东西。

<details>
<summary>Original English</summary>

Absolutely. Yeah. I mean, I think the the motto that we have now is there's just no excuse to not have rigor. Like if and there's no excuse to not have performance if someone complains about something. If someone complains about a a paper cut in the UI, you know, whatever it is, there's just no there's no we don't really have a backlog. Like there's there's no excuse to to just not improve these things.

</details>

### 管理多智能体工作流

**Clara**: 是的。对于那些想要寻求“我们没有积压工作”灵感的听众来说，我们刚刚采访了 Intercom 的 Brian，他说他们的目标就是“零积压”，不留任何积压任务，从而让一切开发工作都能直接上线。好吧。那么，我们刚刚探讨了如何解决极其复杂的技术难题，我觉得这个方法非常棒。那你个人在日常中是如何借助 AI 做工程开发的呢？我很喜欢你现在依然亲身投入编程和投入大量时间这一点。关于如何管理你的智能体舰队，你有什么觉得很独特的小技巧或窍门吗？

<details>
<summary>Original English</summary>

Yeah. And and for folks looking for we don't have a backlog inspiration, we just interviewed Brian from Intercom who says their goal is like backlog zero. Nothing in the backlog so that everything can get shipped. Okay. So, we're solving really technical problems. I think this is a great approach. How are you engineering with AI? Because I love that you're still, you know, you're writing code. You're spending time on this. Any tips or tricks for how you're managing your your fleet of agents that you think are unique?

</details>

**Ankur**: 我认为每个人都应该认真照照镜子，重新审视自己是如何分配时间的。你每天会有许多互动交流、需要下达指令或者做决策。在我看来，许多这类工作其实都落在了“智能体能力基线”之下。对我来说，这条基线意味着：如果我和参会的其他人，把我们在会上讨论的信息等效地丢给一个智能体，它能否解决同样的问题？我认为这条智能体能力基线在不断升高。而且我觉得最优秀的人，正通过巧妙地给智能体编写技能和构建集成，来不断推高他们公司内部的这条能力基线。

一旦你这样做了，你就会发现自己实际拥有的时间比想象的要多得多。我下午 12 点之后就不参加任何会议了。这（次访谈）就是我今天最后一个会。这意味着，套用 Paul Graham 关于“创作者与管理者日程安排”的理论，我每天都能进入创作者日程所必需的专注状态。所以我个人写了非常多的代码，我也愿意在这上面花很多时间。我确实好一阵子没写那么多代码了，而我现在极度享受这个过程。

所以，第一点就是：腾出时间去写代码。我的工作流目前非常简单。我们还没有一个很完美的后台智能体配置，我觉得我们还在探索和尝试达到那个阶段。但我通常会在电脑的前台同时跑五到六个智能体。每一个都运行在一个 tmux 会话里。比如我现在手里有 4 个正在做的任务。所以就会有 4 个 tmux 会话。它们分别被命名为 Braintrust 1 到 Braintrust 4。每个会话里面可能跑着一些 UI，或者跑着一些服务。这就带来了一些问题，比如端口冲突。我没法像我希望的那样将每个项目完全隔离运行。如果是很简单的软件，有很多方案能解决这个问题，但对于极其复杂的软件环境，目前还没有现成的好方案。

我很激动，几乎每个我聊过的人都在自己造轮子解决这事。我刚认识一家才成立两个月的创业公司，他们就在内部自己开发了一个用后台智能体处理 PR 的工具。我一点都不觉得这有什么奇怪的，毕竟这节骨眼上他们还能怎么办呢？这事本身很疯狂，但我同时也会跑远程的智能体。

我举个例子，我目前正在改进我们的列存储性能，测试跑在接近真实的数据上，这是在云端远程跑的。它规模大得多，要是放我本地电脑上跑，早就因为算力爆炸死机了。但通过在云端跑，我能够测试诸如：“当我尝试进行 4000 次并发读取时，EC2 和 S3 之间的真实网络延迟是多少？”对于这个工作负载来说，这速度够吗？我可以合理地交错这些请求吗？我这个实验已经跑了好几天了，就是在试图找出最好的方案。现在，因为查询速度的优化已经基本搞定，我甚至开始和智能体探讨最佳的“索引生命周期”该怎么设计了。

<details>
<summary>Original English</summary>

I think that everyone should take a a hard look in the mirror and re-evaluate how they spend their time. There's a lot of interactions that you have or direction that you're giving or decisions that you're making. And I think like many of these things to me fit below the agent line. And to me the agent line is like if I or whoever would be at the meeting or whatever like if we equivalently took the information that we're discussing and we just gave it to an agent would it solve the same problem? And and I think the agent line keeps going up and also I think the best people are pushing the agent line inside of their company by being smart about what skills they're writing and what integrations they're building and so on. So once you do that, you likely have a lot more time than you thought you did. I don't take any meetings after 12. This is the last meeting of the day for me. And uh that means that every day I am able to in the Paul Graham framework of maker versus manager schedule. Every day I'm able to enter the level of focus that's required to be in the maker schedule. And so I I personally write a lot of code and and I spend a lot of time writing code. And I I've I haven't spent as much time writing code in in a while. and I I really love it. So that's number one is like make the time. Um my my workflow is is very simple right now. We don't have a great background agent setup yet. I think that we are uh exploring various things and trying to get there. But I I have usually five or six foreground agents running on my computer. Each one is a T-U session. Right now I have four things I'm working on. So each one is a T-M session. They're named Brain Trust One through Brain Trust 4. And you know, each of these has like um some UI running and it has some services running. There problems like port collisions. Like I can't isolate everything as much as I'd like to. And and I think that there are a lot of solutions for trivial software that do this. There's not a lot of solutions for complicated software yet. And I'm excited. I mean, everyone I talk to is building their own thing. I just met a startup that's like two months old and they built their own internal tool for doing background agent PRs which is I'm I don't judge them for it like I don't know what else they would do but it's kind of crazy and then I also have remote ones. So here's one where I'm I'm working on trying to improve our column store performance and this is running on not real data but close to real data and it's running remotely and it's you know it's it's it's running like much more scale and many and I mean if I ran this on my computer it would it would probably die from just how much uh compute it's using. But but I'm I'm able to to uh in this case test like what's the real latency between EC2 and S3 if I'm trying to do like 4,000 concurrent reads. Is it enough? Is it not enough for this work workload? Can I interle things? Whatever properly. And I've been running this experiment for for several days just trying to figure out like what's the best you know right now I'm I'm talking to it about what the indexing life cycle should be because I think we figured out how to make the queries fast enough.

</details>

**Clara**: 有些人听了肯定会说：“天哪，这也太技术向了。我又没有这种问题。”让我退一步，为听众梳理一下我看到的亮点：第一，你在用 **Codex**，对吧？

<details>
<summary>Original English</summary>

Some people are going to be listening to this be like, "Oh my gosh, this is so technical. I don't have these problems. Let me take a step back for folks and tell you what I I think I'm seeing here, which is one, you're using codecs, right?

</details>

**Ankur**: 是的。

<details>
<summary>Original English</summary>

Yeah.

</details>

**Clara**: 处理硬核问题就得上 Codex，各位。我跟你们说，就是这样。

<details>
<summary>Original English</summary>

Codeex for hard problems, people. I'm telling you, just uh that

</details>

**Ankur**: 我觉得它目前是唯一一个会经常与你提出反面意见的模型。我认为，当你处理硬核技术问题时，这一点至关重要。

<details>
<summary>Original English</summary>

I think it's currently the only model that will disagree with you regularly. And I think if you're working on hard problems, it's very important.

</details>

**Clara**: 还有对于你而言，我听到的是，你在使用前台智能体。你基本上有个人的“并发限制”，我们姑且称之为并行处理 4 个任务的极限。

<details>
<summary>Original English</summary>

And then for you, what I I'm also hearing is you're using foreground agents. You can bas you basically have a personal concurrency limit of like let's call it four.

</details>

**Ankur**: 没毛病。

<details>
<summary>Original English</summary>

Sure.

</details>

**Clara**: 这大概也是我个人的处理极限了。总有人问我：“你是怎么同时处理那么多上下文的？”我的回答是，任何时候我的任务都不会超过我能力范围内的并行极限。而且我面对的问题确实比你简单些。所以我认为你是对的：现成的、你能买到的商用“后台智能体”对标准的 Web 应用程序来说效果非常好。我很满意。如果你所在的是一家正在开发传统 SaaS 的工程组织却还没用上它们，我极其极其推荐。

但我确实从无论是大团队还是小团队那里听到了越来越强烈的两个呼声，也就是你刚刚点出来的：首先，我听到越来越多的人干脆就在内部自己开发后台智能体。这种情况确实在发生，从极大规模的团队到初创小团队都在搞。打造这些工具的基础模块都已经齐备了。所以如果以后听到有公司虽然使用大厂的核心基础设施，但依然选择内部开发并维护一套专有的后台编程智能体时，我们也不会再感到惊讶。

我听到大家频繁提及的第二件事——这我们在 Stripe 团队那儿也听到过——是对云端开发环境和远程计算的投资。还是那个原因：如果你试图在本地机器上跑哪怕是一部分这种数据密集型的负荷，你的电脑声音听起来就像要起飞的飞机。这绝对不行。

最后一点，我听到你说到了端口管理。我老是开玩笑说：“满地都是工作树”。3000 到 3009 的所有本地端口都被占得满满当当。我这里顺带提一下，Vercel 的 Chris Tate 发布了一个叫 `portless` 的小工具，它能帮你更优雅地管理本地的 localhost 端口。对于轻量级需求，可以去搜一搜，我们会把它放在 GitHub 的节目附注里。这些都是当你在个人电脑上运行高并发工程流时必然会碰到的常见痛点。

至于最核心的方法论，其实就是：一定要腾出时间去写代码。各位，你们真的需要这段时间。我现在下午一点以后也不接任何会议了，有时在下午早些时候做做播客，但其余整个下午的时间，我就会进入我最真实的本我状态：穿上连帽衫，驼着背敲代码。

<details>
<summary>Original English</summary>

which is about what about what I can do as well. So I think people ask me all the time, how do you handle all this context? I'm like I don't do more than I think I can do at any one time. And I also I I have more trivial problems than you. So I think you're right in that the current sort of commercial background agents I would call them that you can buy off the shelf uh work very well for web like standard web apps. I'm very happy with them. If you are not using one of them as an engineering organization, maybe it's like doing classic SAS, highly, highly, highly recommend. But I am hearing more and more from teams two things that you called out. I am hearing more and more people are just building their own background agents. So it's happening. It's happening in teams very very big and very very small. I think the primitives are there to start experimenting with it. And so I don't think it's going to be as surprising to us to hear about people building their own internal coding background agents even if like core infrastructure is something from the big the big models model providers. I think the second thing that I'm hearing a lot and we heard this from the Stripe team is investment in cloud um development uh environments and remote remote computing again because if you were to run some of the stuff especially the the data heavy stuff on your computer it starts to sound like an airplane taking off. It's no good. And then the last thing I heard you say which is like ports I I joke with everybody. I say work trees everywhere. Ports 3000 through 3009 accounted for like I am just like every everything. And I have to call out uh Chris Tate at Verscell released a thing called portless which just makes managing multiple ports local host ports on your uh local machine a little nicer. So for simple things I would go look that up. We'll link it in the in the GitHub show notes. uh you know common problems that I think people have running concurrent engineering processes on their own machine and then the like meta thing which is just like make time to code you need it everyone I also don't take meetings after one sometimes I'll do podcasts in the early afternoon for folks but all afternoon I'm just like in my real state which is hoodie on bad posture

</details>

**Ankur**: 肯定你也有同感。以前当我大部分代码都是自己手敲的时候，我经常会进入一种近乎狂喜的心流状态，整个人彻底专注在一个问题上。当我刚开始大量使用智能体协助写代码时，我曾短暂地失去了那种感觉。但现在当我写代码时——对了，Lane 8 昨天刚出了一张新专辑，你应该去听听——戴上兜帽，戴上耳机，我感觉我现在完全找回了那种极致沉浸的心流状态。只是用了一种截然不同的工作流。

<details>
<summary>Original English</summary>

I think that I'm I'm sure you feel this too but like there when I was handwriting most of my code. Um, I would enter this sort of like euphoric flow state where I, you know, I just completely focus on a problem. And then when I started doing a lot of agent coding, I lost that for a little bit. But now when I'm writing code, you know, Lane 8 just released a new album yesterday. You should listen to it. Put it put on your your hood and your your headphones. I'm like way I'm like totally back in that state now. Um, just doing a different workflow.

</details>

**Clara**: 是的。这里我得扮演一下“互联网 AI 老妈”的角色提醒大家：我感觉大家正分化成两个极端阵营。一拨人比以往任何时候都感到开心，重新找回了当初吸引他们投身软件工程、技术开发的那种心流状态；而另一拨人则濒临云焦虑、倦怠甚至精神崩溃的边缘，因为他们感受到了一种强烈的生产力焦虑。

他们甚至觉得：如果自己在开会而没有同时在跑智能体任务，那就是做错了；如果自己在和别人聊天，而后台没跑着几个智能体，那也是做错了。我只想说：我更倾向于在 AI 辅助上给自己设定特定的时间块。

<details>
<summary>Original English</summary>

Yeah. And I'll give folks the sort of uh you know AI mom of the internet that I try to be, which is I do feel like a lot of people are they they kind of go into two camps. they are having more fun than they've ever had before and they're back in the flow state of like what got them into software engineering or building or technology or whatever or they're approaching like cloud anxiety burnout breakdown because they feel this like productivity anxiety and they're not I I think I think what I see is that people feel like if they're in a meeting and they're not kicking off agents they're doing something wrong or or if they're talking to somebody and they're not kicking off agents they're doing and I just say like I like the idea of chunking your chunking your time with AI a little bit more.

</details>

**Ankur**: 是的，我认为这让你能把精力更集中在最高效的工作片段上，这也是一种更让人享受的工作方式。确实，我也经历过一个阶段——不过现在我肯定已经克服了。我妻子 Elena，我们基本上每晚都会一起吃晚饭。曾有那么一段时间，我的笔记本电脑虽然不在餐桌上，但却开着放在沙发上。我现在应该已经过了那个阶段了。现在，我的笔记本电脑是合上的。我认为这（区分好工作和生活）是非常重要的一件事。

<details>
<summary>Original English</summary>

Yeah, I think it just narrows you on the more more productive um pieces of it and is also just a more enjoyable way to get stuff done. Yeah, I had a phase which I think I'm over. Um, you know, my wife Elena. Um, uh, where I we would have we we have dinner together usually like pretty much every night. Uh, um, and so I had a phase where my laptop was not at the table but open and on the couch and and I I think I've progressed beyond that phase now. So now the laptop is closed and it I think it's it's an important it's an important thing.

</details>

### 揭开评估测试 (Evals) 的神秘面纱

**Clara**: 我同意。刚开始用 OpenClaude 的时候，我把它装在了一台旧的 MacBook 上，它就那么一直开着搁在我们家那堆满插头的厨房中岛上。无论我们吃晚饭还是吃早饭，它都在旁边“凝视”着我们。如果有人把它挪了个位置，我就会很紧张地问：“Polly 哪去了？她还活着吗？电脑是开着还是关着的？”所以，真的，大家还是要把电脑合上，把电脑合上。

本期节目由 Persona 赞助。你在学习利用 AI 进行构建，但有一个关键问题你必须要问：到底是谁在使用你的产品？那是一个合法的真实用户、一个机器人，还是一个欺诈者？Brex、Figma、Etsy 和 Twilio 都信任 Persona 来给出答案。借助 Persona 的身份验证平台，你可以打造带有品牌特色的体验、自动化欺诈预防并识别屏幕背后的真实人类。这使你能够轻松地给优质用户宾至如归的体验，同时将心怀不轨的作恶者挡在门外，防止他们造成破坏。而对于那些在 AI 智能体领域搞开发的人来说，Persona 可以帮助你们验证这些智能体背后的人、企业和开发者的真实身份。这也正是 Lithic 和 Skyfire 这样具有前瞻性的公司，能借此突破智能代理商业前沿壁垒的关键原因。前往 withpersona.com 了解更多。

好啦，我们在节目的上半场聊完了那些对技术人员来说极具吸引力的话题——如何利用能长期运行的专注智能体去对付技术难题，从而用真实的数据基准测试来评估调整代码带来的性能改变。我太爱这部分了。我们还聊了你的日常编码工作流，包括时间分配以及技术上的具体操作。

现在我们来聊聊**评估（Evals）**。我感觉这是个让许多人都非常生畏的概念。你显然是在开发支持这方面的产品。但我们退一步讲，你为什么认为理解这个概念如此重要？对于那些对这个概念有点畏惧的人，你如何帮他们打破这种神秘感？

<details>
<summary>Original English</summary>

I I agree. I uh when I was first using OpenClaw, I installed it on an old MacBook, and it would like stay open on our kitchen island, which is where all our plugs are, and it would like hover over us at dinner and hover over us at at breakfast. And if it got moved, I was like, "Where is Polly? Is she alive? Is she open? Is she closed?" So, yes, close your laptop, people. Close your laptop. This episode is brought to you by Persona. You're learning to build with AI, but there's an important question you need to ask. Who is actually using your product? Is it a legitimate user, a bot, or a fraudster? Brex, Figma, Etsy, and Twilio trust Persona to answer that question. With Persona's identity verification platform, you can create branded experiences, automate fraud prevention, and know who is human online. That makes it easy to give good users an experience that makes them feel welcome, and to stop bad actors from causing damage. And for those of you building in the AI agent space, Persona helps you verify the identities of people, businesses, and developers behind agents. It's how companies like Lithic and Skyfire are pushing the frontier of agentic commerce. Learn more at withpersona.com. All right, so you know, we covered the first half of this episode, which I think is very interesting for technical folks. how to have kind of like longunning or just really diligent agents run against technical problems to give you real benchmarks about performance on changing things. I love that. Second thing is just your core workflow on how you do coding both how you dedicate time and then technically just what your workflow looks like. Let's talk about evals because I feel like this is something that's very intimidating to a lot of people and obviously you build a product that supports this but taking a step back why do you think this concept is so important to understand and how can you just demystify it for folks who are a little intimidated by it?

</details>

**Ankur**: 机器学习，特别是当下的发展，把编程的核心任务从“定义该如何做”转变为了“定义想要什么结果”。哪怕撇开大语言模型不谈，这点也同样适用。比如回到中学时代你学过的统计回归：你并不是在硬编码定义斜率和 Y 轴截距应该是多少，而是把所有的散点数据喂进去（这就是你要的结果），机器会自己去计算“怎么实现”——也就是求出斜率和 Y 轴截距。

我认为，围绕 Transformer 架构和“预测下一个 token”这一任务所带来的酷炫创新点在于：它建立了一个可以消融 token 的计算底座。它的本质就是在说：“好吧，这是计算基底，这是你要的结果，即预测下一个 token。你能去调用海量的 GPU 弄清楚怎么达成这个目标吗？”如果你能将这个理念作为所有 AI 开发的灵感来源，你就会变得极其高效。

这种理念不仅适用于刚才讨论的传统编程——我不去硬性规定具体的实现方式，甚至不去规定要用哪些算法去解决问题，我只需要极其简洁地定义问题到底是什么、为什么它是个问题、以及如何评估各种解决方案就够了；它同样也适用于开发 AI 软件。评估这套方法论的作用，就是让你能够清晰地表达出“成功到底长什么样”。

在我看来，**Evals 实际上就是现代版的 PRD（产品需求文档）**。以前写 PRD 时，你会用散文式的自然语言描述：“看，这就是功能成功的样子。”Evals 很多时候也是用自然语言编写的，但你会辅以具体的用例。比如，最顶尖的 PRD 往往会有极佳的例子，可能是某人做了一个演示 Demo，或者写了一个用户故事。Evals 也是一回事，唯一的区别在于，你现在以一种能够（在某种程度上）被量化的方式对这些用户故事进行了编码。这样你就可以放手让模型或者系统去搞明白“怎么做”，而你只需要高度聚焦于“你想要什么”。

<details>
<summary>Original English</summary>

Machine learning specifically shifts the task of programming from being about the how to being about the what. And this is true like forget about LLMs like you know it's true with let's say like you're back in like middle school you're doing like remember statistical regression you're not defining the you're you're computing what the slope and the y intercept should be you're not defining it but you give it all the points which are the you know the what not the the how which is the slope and the y intercept and I think that you know the the cool innovation around like transformers and um the next token prediction task which lets to, you know, ablate tokens and do all this cool stuff. It's all about saying like, okay, um, here's like the compute substrate and here's the what, which is the outcome. It's predicting the next token. Can you go and use a lot of GPUs and figure out how to achieve that? And I think that uh if you take that as inspiration for anything you do with AI, then you're able to be more productive. And I think that applies to traditional programming like what we just talked about. I'm not dictating exactly the implementation or even the set of algorithms that we're using to solve problems. I'm just trying to define very succinctly what the problem is and why it is a problem and how to assess the solutions to the problem. It also applies to building AI software and that's what eval methodology for you to say this is what success looks like. In my opinion, EVELs are actually the modern version of a PRD. So, a PRD, you would say, hey, in pros, this is what success looks like. Um, evals are also often written in pros, but you um supplement that with with uh examples. So, you know, the best PRDS, they have good examples like that maybe someone's made a demo or uh written out like a user story or something. It's it's the same thing. Um it's just the difference with evals is you encode those user stories in a way that can be quantified to some extent and then you and then and then you let a model or whatever figure out the how and and you are really focused on the what.

</details>

**Clara**: 能不能举个具体的例子，让大家感受一下你是如何在产品开发中实际运用这一点的？

<details>
<summary>Original English</summary>

Give me an example of how you use this in in product development just to make it a little bit more tangible for folks.

</details>

**Ankur**: 好，我们就从一个极其简单的案例开始，然后再随着思路深入到那些不那么简单的地方。这里展示的是我们的 UI。我现在正在处理一个非常基础的任务：我正试图编写一段提示词，这个提示词将被放入一个专门负责回答有关 Braintrust 文档问题的智能体中。

我们梳理了人们在浏览我们的文档时常问的一些问题，直接把它们整合成了一个数据集。你甚至可以随便上传一个 CSV 文件——其实什么格式根本不重要，核心就是先列出一堆问题，你甚至可以让 AI 去自动生成它们。万事开头难，随便找个地方起步就行。我们写了一个非常基础的 Prompt，打算使用 GPT-4o-mini 模型。我还挂载了一个 MCP 服务器——也就是连接了 Braintrust 自家的 MCP 服务器。我们私下也一直在测试 Context 7，它可以自动帮你给文档建立索引。当然，你也可以把 MCP 关掉，直接去测试这个底层模型本身对你的产品到底懂多少。实际上，现在的模型在这方面已经变得非常强悍，几乎什么产品都能门清。

好，我现在运行了它。你能看到它输出了一些答案。说实话，让我人工去把这些回答一条一条读完是不可能的，我真不想干这个。所以，我通常的做法是直接对它说：“嘿，你能针对这些输出内容，制定一个好的打分函数吗？我非常在意这几个点：必须只提供极其精简的代码片段；必须只能使用一种编程语言；而且……” 我们就再加一条：“必须完全避免使用破折号。”

<details>
<summary>Original English</summary>

Yeah, let's let's start with something that I think is quite straightforward and then we can venture into the less straightforward stuff as we go. So this is our UI. Um, and like I'm working on a very simple task here, which is I'm trying to create a prompt that will be part of an agent that is good at answering questions about brain trust documentation. So we looked at a few questions that people are asking in our docs and we just put them into a data set. You can like upload a CSV file like it doesn't matter. It's just come up with a list of some questions or you can autogenerate them. What you know, whatever. just start somewhere and wrote like a very basic prompt. Uh we're going to use GPT 5.4 mini and uh I attached an MCP server. So I attached the Brain Trust MCP server. We were also playing around with context 7 which indexes docs for you. Um you could also turn off the MCP and just see what the model already knows about your product. They're getting pretty good at knowing about every product now as well. And uh here I just I just ran it and so you can see some of the answers. I I'm going to be honest though, I don't really want to like read all of these manually. And so what I would usually do is I just start by saying like, hey, can you come up with a good uh scoring function for these outputs? I care about having concise code snippets, only using one language, and um let's say avoiding m dashes

</details>

**Clara**: 总之。

<details>
<summary>Original English</summary>

always.

</details>

**Ankur**: 对，任何时候都避免使用。你看，在这个例子里，GPT-4o（当前最新最强的模型）它真的会帮我去查看所有这些资料，它会审视那些历史输出，它会重新运行各项测试。它就是在自动执行这些琐碎的任务，最后它会给我生成一个全新的打分函数。顺便说一句，我认为整个工作流中非常酷的一点是——而且我预计这种设计未来会在更多产品中普及——你会发现，我此刻等于把一个编程智能体切换到了“完全脱缰”模式。如果你把这样一个脱缰的智能体直接跑在你电脑的本地环境里，让它瞎折腾，那是极其危险的。但现在这个智能体，它被完全隔离在这个安全的沙盒测试游乐场里，它调用的只是测试数据和一些测试 Prompt。所以，让它在这里撒欢尝试各种疯狂的想法，风险实际上是非常非常低的。所以，总体而言，我感到非常兴奋，我期待看到这类智能体能够越来越多地走出本地危险环境，安全地在各种隔离环境里“胡作非为”。就比如此刻，我都不知道它具体正在底鼓捣些什么，但过几分钟我们就会看到结果。

<details>
<summary>Original English</summary>

Um yeah, of course. Uh and so now um in this case, GPT 5.4 before is going to go and actually like look at all this stuff for me and it's going to look at some of the outputs and it's going to rerun stuff and um it'll kind of do its thing and it's going to come up with a new scoring function. One of the things I think by the way that's kind of cool about this workflow in general and I expect to see this in more products over time is that you'll notice like I have this in the equivalent of like unhinged mode of uh a coding agent which is sometimes dangerous to run on your machine but this agent is running inside of this playground and it's using like data and and some prompts and stuff. So the risk of letting it just go and try stuff out is actually very low. And so I I I think uh I I'm excited just generally about seeing agents in more environments outside of my local computer with bash and something that's like very dangerous and you know could screw up my my life if it goes wrong. Um I'm excited about just having more agents that sort of run in in these types of environments and do whatever they want. Like I I don't even know what this is doing right now, but we'll find out in a few minutes.

</details>

**Clara**: 我对此真的感到非常兴奋。给那些听音频没有看视频的听众、或者只是需要进一步了解背景的人简单总结一下你刚才的操作：你先是收集了人们在你的文档站点、搜索框或是聊天机器人里提过的那些关于产品如何运作的实际问题。然后你写了一个简短的提示词，让系统去回答这些问题。而你现在正在做的，是指挥 AI 为你“生成一个打分器”——让这个打分器基于你给它的一系列非常宽泛的规则，来自动评判系统对这些问题的回答究竟有多好。这个打分机制是不是会被应用到所有这些问题上，这样你就能直接对回答质量进行量化排名了？

<details>
<summary>Original English</summary>

I'm I'm really excited about this. And just for people that are not watching or need just another set of context, basically what you did is you took these questions that people are asking in your doc site or search or whatever chat bot about um how the product worked. You built a little prompt to answer those questions. And then right now you're building you're having AI build a scoreer that tells you how well these questions are getting answered based on like a very loose definition of what you want it to do. And then is that score apply that scoring mechanism applied across all of these so you can actually rank it?

</details>

**Ankur**: 是的。对的，完全没错。嗯，不过我觉得目前的运行稍微有点偏轨了。所以我打算切到另外一个效果更好一点的界面上去。

<details>
<summary>Original English</summary>

Yes. Yeah. Yeah. I think it's going a little bit ary actually. So I'm going to switch to this one which is a little bit better. Um

</details>

**Clara**: 纯现场操作。我们就爱看现场翻车的真实演示。

<details>
<summary>Original English</summary>

we do it live. We love a live demo.

</details>

**Ankur**: 是啊。我们换 Claude 来跑跑看。这个版本看起来干净得多，而且它已经成功写出了一个 Prompt。我们用一个更聪明的模型吧，它刚才没挑最聪明的那个。它写出的这个 Prompt，能够接收输入和输出作为参数，然后针对我们制定的标准对其进行评分评估。

<details>
<summary>Original English</summary>

I know. Uh and and let's use uh let's use Claude and give it a shot. So uh this one is a little bit cleaner and it actually wrote a prompt. Um let's use a smarter model. It didn't pick the smartest model. It wrote a prompt which uh takes the input and the output and then it evaluates it on these criteria.

</details>

**Clara**: 手动去一条一条地把这些评估标准和用例写出来简直是个极其折磨人的苦差事。所以，能直接丢给模型让它替你写，这感觉太棒了。

<details>
<summary>Original English</summary>

It is a pain in the ass to write these criteria out by hand. So it's really nice to just let a model do it for you. Yep.

</details>

**Ankur**: 对的。接下来我们能做的就是运行它。它会自动去量化模型表现得有多好，我们在这些标准上达成了怎样的分数。然后我们要么逐条去查看明细，或者——实际上这也是我现在的常态——我会直接看汇总的数据。看，分数现在已经开始弹出来了。

<details>
<summary>Original English</summary>

And what we can do is is run it and it will it will quantify how well um how well the model does uh on um on these criteria and then we can look at it like one by one or or what I actually tend to do nowadays is um look at it in aggregate and so the scores will start coming in here.

</details>

**Clara**: 你觉得如果你不用这套流程，业内其他人作为替代方案在怎么做？有哪些做法你觉得是效率极低的？我能想到的第一个就是干脆彻底不做这事，我知道很多人就是这么摆烂的。

<details>
<summary>Original English</summary>

What's the alternative that people are what do you see people doing as an alternative this that you think is less effective? One is just not doing it. I know a lot of people

</details>

**Ankur**: 是的，我想很多人——包括我在内，尽管我是做这类产品的，有时也依然会掉进这个陷阱，所以这并不是在评判谁对谁错。但我认为很多人常做的一件事是：他们只在那么一两个孤立的例子上测试一下新功能，然后就试图从中总结出普遍性的结论。老实说，我也不觉得这完全是个糟糕的主意，因为直观的感觉测试依然非常重要。

但是，如果你只靠这种方式，你最终就是在玩一场“打地鼠”的游戏。你可能通过微调让系统在这两件事上表现得极其出色，结果一上线，你才发现它在其他所有地方都烂透了。我们公司有一位叫 David 的设计师。David 这个人特别酷，衣品极佳，还深谙各种最前沿的音乐。他总能在某首歌火起来之前就开始听了。他跟我讲过，他小时候踢足球时，全队所有人都穿黑色的球鞋，他就偏要买一双橙色的。结果第二年，所有人都想要橙色球鞋了。他就是那种品味超前的引领者。

然而，我们手头有大量的 AI 项目同时推进，让 David 这种顶尖的 Braintrust 品味塑造者亲自去人工检查每一个生成的界面或文案显然是不现实的。所以我实际是怎么做的呢？我会先大规模运行海量的自动化评估，试图通过量化数据来不断迭代改进产品。只有当我觉得各项 Evals 分数都很完美，且我自己那种不怎么讲究的品味也挑不出毛病觉得结果不错时，我才会拿着最终成果去找 David，请他做最后的人工测试。我大概每隔几天才会找他这么做一次。然后 David 会给我反馈，一半的时间里，他会把我所有的得意之作批得体无完肤：“嘿，你可能觉得这挺好，但实际上它烂透了。”

那接下来我会怎么做？我会回去尝试把我这位大师 David 脑子里的规则给提炼出来。我会更新系统说：“嘿，David 其实认为，只要满足特定条件，同时显示两种语言是没问题的，等等等等。”所以，我实际上是在尝试捕捉 David 的品味，将其沉淀到系统中，接着去改进打分器，然后试图去对 David 这种直觉进行量化。这样，下一次我再去找他做测试时，我就不会再犯同样的错误了，但我依然能利用到他超凡的直觉和眼光。

<details>
<summary>Original English</summary>

Yeah. I mean, I think that a lot of people, and I fall into this trap myself despite working on this product, so it's not there's no judgment for for doing this, but I think what a lot of people do is they just try stuff out on one or two examples and they try to generalize from that. And frankly, I don't think that's a bad idea. Like, I think that vibe checks are extremely important. But, uh, what's what happens is that if you do this, you end up playing kind of like a whack-a-ole game. So, you might make it really good at one or two things and then you ship it and then it's not good at something else. And what we do, we have this designer named David. Uh, and David is really cool. Like, he dresses well. He has like like he's into the latest music. He he he like he likes music before other people do. He told me that when he was a kid, he had he played soccer and everyone had black shoes and he wanted the orange ones and then the next year everyone wanted the orange shoes. Um, so he's like that kind of person, right? Yeah. And we have a lot of AI stuff going on. So it's not practical for David who has like the ultimate who's the ultimate brain trust taste maker to look at everything manually. And what I actually do is I run a ton of evals to try to quant quantitatively improve things and then when I feel like the evals are good and my own less sophisticated pallet thinks that the results are good, I will go to David and ask him for a vibe check. And I probably do that like once every few days. And then David gives me the vibe check and like half the time he just completely destroys everything that I've said. Like, hey, you know, you think it's good, but it's actually not very good. And then what what what happens is I will go back and try to capture what David said and I'll say like, you know, hey, David actually thinks um it's okay to show both languages as long as you know, blah blah blah blah blah. And then I will so I'll try to sort of capture David and then improve the scorers and then attempt to quantify David. And then the next time I go to him, I don't like repeat the same mistake, but I still get his vibe check.

</details>

**Clara**: 我必须要指出这里隐藏的一个更高层次的“元命题”，关于你讲的 David 的故事，我实在是太喜欢了。我听到很多人说：“哇，如果我甚至要把自己的品味、技能或者专业知识都转化为一套自动运行的系统，这其实就等于是在亲手打造能够取代我自己的替代品。”而在我看来，正是因为你这么做了，你的团队反而会更加珍视 David 的价值，听起来你也确实是这么想的。

<details>
<summary>Original English</summary>

Well, and I just have to call out the the meta thing here in this David story, which I love, which is I have a lot of people saying, "Wow, if I go as so far as to turn my own taste or my own skills or my own expertise into a system, whether that system is like the David Eval, the David David in a loop judge, or something else, I I'm I'm functionally just building my own replacement." And I am presuming because I do, and it sounds like you do, too. you value David more in this system.

</details>

**Ankur**: 绝对是，百分之百。这使得我们能够将 David 的品味无限放大，应用到更多的事情上。我认为我们最终交付的产品质量下限被拔高了，因为我们有能力让远比以前数量更庞大的项目，全都达到那个高不可攀的卓越标准。

<details>
<summary>Original English</summary>

Oh yeah, yeah, yeah. We're able to have David's pallet applied to more things like the the I think the quality bar is that we're able to hit is higher because we're able to get more things to that to that bar.

</details>

### 产品交付与技术管理的哲学

**Clara**: 我爱死这段讨论了。好，这绝对是能量爆棚的一期节目，是我个人最喜欢的单集之一。我们探讨了大量关于如何用 AI 解决硬核技术问题的方法论，我们为观众打破了评估系统的神秘外壳，我们还展示了——这也是本期播客一个深藏的元主题——只要你能构建一个安全的沙盒空间，放手让 AI 带着极高的自主权去狂奔思考，向它投喂海量的数据，你最终获得的结果质量，将远超你靠纯手工去修复 bug 甚至手工去评估一切时所能达到的上限。现在，我要进入快问快答环节，然后就得放你回去写代码了。这会儿都快中午了。

<details>
<summary>Original English</summary>

I love it. Okay, so this has been a powerhouse episode. One of my favorites. We've talked about a lot about, you know, solving really technical problems with AI. We've demystified evals a little bit for folks and shown how in in a safe space you can actually let AI think that's one of the meta themes of this is in a safe space you can let AI run with a lot of autonomy and you'll you know throw a lot of data at it and you can get higher quality outcomes much more so than if you were to manually fix things or even manually evaluate things. I'm going to do a quick lightning round and then we'll get you back to I mean it's almost noon so back

</details>

**Ankur**: 该回去写代码了。编程时间到了。

<details>
<summary>Original English</summary>

Time to coding. Time to code.

</details>

**Clara**: 第一个问题。你刚才说“没有任何借口留着 bug 不修。不该为任何设计上的瑕疵找借口。现在没理由不解决这些问题”。我的问题是——实际上这可以拆成两个供你快问快答的问题：第一，你如何在这个基础上，在实践层面去管理向客户交付功能的速度？客户有没有跟你抱怨过：“等等，这功能又变了？等等，那又是什么新玩意儿？”他们会不会觉得功能塞得太满、消化不良？第二，在技术架构上，你如何管理这套快速迭代系统的吞吐量？

<details>
<summary>Original English</summary>

One, I have a question. When you say there is no excuse, there's no excuse for bugs. There's no excuse for little design knits. There's no excuse for that. How do you feel like you practically I maybe have two questions that you can answer. They'll be our two lighting run. How do you practically manage the velocity to customers, which is do you ever get customers being like, "Wait, what's this? Wait, what's that?" Like too much features just consumed as a customer. And then two, how do you technically manage the throughput into the system?

</details>

**Ankur**: 产品构建和代码编写现在的性质，看起来已经更像是一种“雕刻”的减法，而不是“堆砌”的加法。因为利用 AI 极其容易就能堆出一个塞满过多功能、过多按钮以及过度臃肿代码的产品，而你需要花大量的时间去把没用的东西删减掉。

实际上我想说，在 90% 的情况下，当有人对产品表达不满或抱怨时，我们的应对措施是——直接把那个引起混乱的功能删掉。通过做减法，让整个系统运转得更顺畅。因为当用户抱怨时，我们真正理解了他们的视角。我们现在有能力去构建出那种从根本上就不需要这层“复杂性”的产品，正是这种一开始添加的复杂性最终导致了他们的困惑。

我给你举个例子。如果你在我们的界面里加载了一条庞大的日志追踪链路，并且在脑海中习惯性地按下 `Command+F` 查找。你可能认为你只是在搜索当前这个页面上的文本；但实际上，页面加载的文本可能是高达几百兆级别的数据，它是在前端被虚拟化渲染的。这涉及跨度庞大的不同数据区间，甚至可能还涉及数据库表。为了支持这种查找，我们原本开发了一个性能极其强悍的搜索功能，它可以穿透那些分布的区间进行搜索，对所有结果进行排序整合……等等一堆听起来酷炫无比的技术实现。结果呢？大量用户跑来抱怨：“这到底是在干嘛？我只想按个 `Command+F` 看当前这一行的东西啊！”

所以我们随着时间推移真的把系统大幅度简化了。我的核心观点是，我们要努力去做减法、去雕刻。而在技术管理层面如何支撑这一切？那就是我们比以前花了多得多的时间去打造坚如磐石的 CI（持续集成）系统。我认为公司投入在底层平台的大量努力已经转移到了这上面。因为只要我们的 CI 足够严苛高效，我们就有底气跑得极快。而一旦我们在交付时感受到了摩擦或阻力，我们绝不会选择强行硬塞一堆半成品的垃圾上去，我们会说：“好，立刻暂停开发，回去优化改进 CI 系统。直到我们重新赢得‘跑得快’的资格为止。”

<details>
<summary>Original English</summary>

Product building and code writing is now looks like carving rather than constructing. So it's very fast to create something that has too many features and too many buttons and too much code and you need to spend a lot of time removing stuff. And so we actually I would say 90% of the time someone complains about something we remove the thing that was causing confusion and just make the system work better because we understand now that the person complained their point of view and we're able to build a product that doesn't even need the complexity that led them to the confusion in the first place. I'll give you an example. If you load a trace and you imagine hitting command F, you might in your brain think that that's just searching what's on the page, but what's on the page might be hundreds of megabytes of text and it's virtualized and there's it's across spans and there's also a table. So, we had a very powerful search implementation that would search across the spans and rank everything and you know blah blah blah all this cool stuff. And then a lot of people complained and they were just like why is this you know I just hit command F. I just wanted to show the the thing and we've just we've we've really simplified it over time. So I think I think we we try to carve and then in terms of technically managing it, we spend a lot more time working on CI than we used to. Uh and so I think that a lot of um platform effort has shifted so that if we are really good at CI then we're able to move faster and if we feel like we're constrained then instead of shipping a bunch of crappy stuff we're like okay let's pause and improve CI so that we earn the ability to move faster.

</details>

**Clara**: 好吧，我要再次对所有躲在后排的工程副总裁们喊话了——在 CI 上狠狠砸钱！我已经无数次被问及：“我该怎么利用 AI 加速我的工程交付节奏？”我的回答永远是：“回去搞好你们的 CI。”

<details>
<summary>Original English</summary>

Okay again for the VP of engineering in the back invest in C I've I've told every they're like how do I accelerate my engineering velocity with AI? I was like fix your CI.

</details>

**Ankur**: 没错。太对了。

<details>
<summary>Original English</summary>

Yeah. Yeah.

</details>

**Ankur**: 现在，每一位工程师其实都在构建一个平台，而在这个之上，正是那些智能体在替代工程师从事以前必须要手动处理的繁杂琐事，对吧？我认为这个逻辑也完全适用于我们刚才说的评估测试（Evals）。如果你身处一个工程团队，而且你们正在开发一款 AI 产品，那么你们最核心的第一要务，就是去构建一个反馈闭环。这意味着你必须搭建起一条流水线，让它能够直接从现实世界的混沌数据海洋中抽取养分，并将这些真实情况转化为清晰可量化的 Eval 测试用例。作为工程团队，构建这条流水线才是你们不可撼动的首要任务。不是去折腾什么 Prompt 工程，不是去纠结选哪个智能体框架，也不是去重构底层的数据库系统。搞定那条数据验证流水线才是一切的基础。同样的道理，CI 就是将同样的反馈循环理念应用到纯软件工程上罢了。

<details>
<summary>Original English</summary>

Every engineer is now building a platform and upon the platform agents are doing the work that the engineers were doing manually, right? And I think that applies to evals. Like if you're an engineering team and you're building an AI product, the number one job for you is to build a feedback loop. Meaning you have a a pipeline that allows you to summon from the ether of real world data and turn that into eval. And as an engineering team, that is your number one job. It is not prompt engineering. It's not picking an agent framework. It's not rewriting your database, whatever. It's creating that pipeline. And the same is true CI is that same idea but applied to software engineering.

</details>

**Clara**: 太棒了，我还想补充另外一个小建议：你可能会觉得只有做 AI 产品的人才需要重视 Eval 这套东西。但我又得提到 Intercom 团队了。我看到他们针对自己公司内部员工使用 Claude 代码助手的行为，运行了大量的 Evals。他们通过这套测试，试图找出自家工程师在使用 AI 时究竟在哪里遇到了痛点？哪些地方让他们中途放弃？这些代码智能体到底在哪里会卡住并向人类请求升级权限？我敢说，针对你自己的研发团队去做这种颗粒度的分析是极其、极其关键的，并且最终能带给你无与伦比的高质量产出。

好了，最后一个问题。你看上去是个极其理性且讲道理的人。所以我预期我接下来的问题也会得到一个理性的答案，但我对每个嘉宾都会问这道题。当你在本地同时开着四个终端标签页指挥着智能体，而其中有一个智能体开始“罢工”或是胡言乱语；当它反复通过不了那个所谓的“David 品味测试”时。你会依靠什么样的“终极压箱底 Prompt 策略”？你会对它大喊大叫吗？还是会贿赂它？

<details>
<summary>Original English</summary>

Well, and I'll give one other tip which is you think that those eval people are always like oh yeah for my AI product I need that. I have seen again I think the intercom team has run a bunch of evals on their internal use of clawed code to figure out where engineers are hitting pain points where people are giving up where the agents are asking for permissions that have to be escalated. And I think that sort of analysis on your team is very very important and ultimately gets you to these these better outcomes. Okay, last question. You seem like a very reasoned person. So I'm presuming I'm going to get a very reasonable answer, but I ask everybody. When a one of one of your four tabs is not doing what you want, when the evals are failing the David test, what is a in your back pocket prompting strategy that you that that you rely on? Do you yell? Do you bribe?

</details>

**Ankur**: 直接关掉会话窗口。然后我会去优化底层的 Evals 评估标准，接着重新开启一个新会话，从头再试一次。真的就是这样。

<details>
<summary>Original English</summary>

Close the session. Um, and then I improve the evals and then I try from scratch again. Yeah. Yeah.

</details>

**Clara**: 这真是一个时刻坚持原则的人啊。

<details>
<summary>Original English</summary>

This is a man who is on message.

</details>

**Ankur**: 是啊。我给你举个具体的例子吧。我们在开源领域有个场景——严格来说是针对开源模型运行的用例。在这个场景中，我们需要每秒处理上百万个 token，这是极大规模的并发。所以在这个层面，哪怕是一分钱的成本波动、每一丁点的性能优化都事关重大。我们目前正试图从 A 模型切换到 B 模型。正如我前面提到的，我每天都在写构建评估测试的软件；而在这个项目里，我当时有点随意，就凭着直觉让 AI 写了一个 Eval 脚本，结果它跑起来直接卡死了。后来我亲自去翻了代码，发现那简直是 3000 行纯粹的垃圾。里面堆砌了各种花里胡哨的打分函数和一堆乱七八糟的玩意儿，整个逻辑完全混乱了。

所以就在上周六，我直接选择了手写代码。没开自动补全辅助。我这么做，部分原因也是为了倒逼自己重新梳理对问题的理解。我亲自一行行手写了那个底层 Eval 测试。然后到了周日结束时，这个问题彻底被解决了。

<details>
<summary>Original English</summary>

Yeah. I mean, I'll give you like a an example. Um, we have this open source use case, sorry, a model, a use case where we run open source models and we're running like millions of tokens per second. It's very very high scale. So, every cent matters and every bit of optimization matters. We are trying to change right now from model A to model B and I again I'm someone who builds software to write EVLs. I uh vibe coded an eval script and it went it just was getting stuck and then I read the code and it's like 3,000 lines of complete trash and it had like all these scoring functions and all this crap and it was getting confused and so I on Saturday I hand wrote like no uh no co-pilot no autocomplete I just I partly to improve my own understanding of the problem I hand wrote the eval and And by the end of Sunday the problem was solved.

</details>

**Clara**: 明白了。所以当事情卡死时，你的绝招就是关闭 AI 会话，卷起袖子亲自上阵去写。

<details>
<summary>Original English</summary>

Yeah. So you shut the session, you do it yourself.

</details>

**Ankur**: 是的，不过仅仅局限在编写那个核心的 Eval 标准上。我只亲手写那个定义成功底线的评估指标。

<details>
<summary>Original English</summary>

Yeah. Just for the eval. Just for the eval.

</details>

**Clara**: 太精彩了。今天的对谈真的非常非常棒。那么，大家可以在哪里找到你，我们又能如何提供帮助呢？

<details>
<summary>Original English</summary>

Great. This has been so great. Where can we where can we find you and how can we be helpful?

</details>

**Ankur**: 如果你对建立 Evals 体系或者尝试解决公司内部庞大复杂的 AI 可观察性问题感兴趣，请务必来看看我们 Braintrust。我们的网址是 braintrust.dev，或者在社交平台 X 上搜 `@ankrgyl`，非常期待与大家交流。同时，我们也在招人。如果你同样热爱钻研这些棘手难题，渴望在代码严谨性及其边界上不断挑战极限，觉得我们今天聊的这些干货很有趣的话，我们非常期待你能加入团队一起共事。

<details>
<summary>Original English</summary>

Uh if you are interested in um evals or you're trying to solve AI observability problems inside your company, please check out BrainRust. We're at brainust.dev brain onx or I'm ankrg yl. Um very happy to chat. We're also hiring. If you like working on these problems and you like maybe pushing the boundaries of rigor and stuff and found this kind of stuff interesting, uh we'd love to work with you.

</details>

**Clara**: 太感谢你的参与了，这次对谈棒极了。

<details>
<summary>Original English</summary>

Well, thank you so much for joining. This was great.

</details>

**Ankur**: 整个过程我也非常享受，非常开心。

<details>
<summary>Original English</summary>

It was a lot of fun.

</details>

**Clara**: 非常感谢大家的收看。如果你喜欢这期节目，请在 YouTube 这里点赞并订阅，如果能给我们留言分享你的看法就更棒了。你也可以在 Apple Podcasts、Spotify 或是你喜欢的播客应用上收听我们的音频版。恳请大家考虑给我们打分和留下评论，这能帮助更多人发现这档节目。你可以前往 howiipod.com 查看所有的往期节目，了解更多精彩内容。我们下次再见。

<details>
<summary>Original English</summary>

Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>