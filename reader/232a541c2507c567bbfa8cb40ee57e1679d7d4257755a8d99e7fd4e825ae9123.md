---
author: Dwarkesh Patel
date: '2026-06-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TfyPshgMbug
speaker: Dwarkesh Patel
tags:
  - math-progress
  - ai-capability
  - frontier-research
  - knowledge-connection
title: 人工智能在数学领域的进展及其对通用人工智能的启示
summary: 文章探讨了人工智能在数学领域取得的快速进步，特别是与国际数学奥林匹克竞赛和千禧年大奖难题相关的讨论。核心观点包括：AI的进步更多是由于其数字心智固有的并行化和知识融合优势，而非单一天才的灵光一闪。作者分析了从特定领域的突破（如几何题的暴力求解）到跨领域连接（如黎曼猜想与随机矩阵理论的联系）的转变，并探讨了这种能力对未来经济和社会结构的影响。
insight: ''
draft: true
series: ''
category: science
area: knowledge-meta
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

### AI与数学的交汇

**Interviewer**: 今天，我正在和格兰特·桑德森（Grant Sanderson）交谈，他运营着 3Blue1Brown，现在正在做一个记录 AI 在数学领域取得的进展的新项目。我想和你谈谈这件事，因为在所有领域中，AI 在数学方面取得的进展是最快的。无论这里发生了什么，以及无论我们看到 AI 的进步以何种方式发生或不发生，都会告诉我们在 AI 变得越来越好时，世界的其他地方将会发生什么。我想从我三年前第一次采访你时问过你的这个问题开始。我当时问你，一旦我们有了能够在国际数学奥林匹克竞赛中获得金牌的 AI，那不就是通用人工智能（AGI）了吗？考虑到这些问题有多难，它不就应该能够做任何人类能做的事情了吗？你当时的回答回过头来看非常明智和正确。你说这将会是另一个基准测试，就像 AI 正在通过的所有其他这些基准测试一样。显然，从那以后 AI 在各个方面都变得更好了，但当这件事发生时，并不会有什么“顿悟”的时刻。首先，我很想了解一下你是根据什么启发式规律判断出这会成为现实的。其次，我很好奇你认为这种局限性还能持续多久。到 AI 解决了千禧年大奖难题的时候，你认为经济中是否仍然可能存在许多人类正在做而 AI 仍然无法自动化的任务？

<details>
<summary>Original English</summary>

**Interviewer**: Today, I'm chatting with Grant Sanderson, who runs 3Blue1Brown and is now working on a new project documenting the progress AI is making in math. I wanted to talk to you about this because AI has been making the fastest progress in mathematics out of any other field. Whatever is happening here, and whatever way we're seeing AI progress happen or not happen, will tell us about what will happen to the rest of the world as AI gets better and better. I wanted to start with this question I asked you when I first interviewed you three years ago. I asked you, once we have AIs that can get gold in the International Math Olympiad, wouldn't that just be AGI? Wouldn't this just be able to do anything any human can do, given how hard these problems are? You had an answer, which in retrospect turned out to be very wise and correct. You said it'll be another benchmark, like all these other benchmarks that AI are passing. Obviously, AI has gotten better in a general way since then, but there won't be some "aha" moment when this happens. First, I'd be curious to get your heuristics on why that turned out to be true. Second, I'm curious how long you think this narrowness can continue to be true. By the point that AI has solved a Millennium Prize problem, do you think it's still possible that there are lots of tasks humans are doing that AI still can’t automate in the economy?

</details>

**Grant Sanderson**: 这是一个有趣的问题，因为在没有提前知道解决方案是什么样子的情况下，很难给出答案。如果我们以 IMO 为例，你三年前那个问题的核心在于，人们看到这些问题的一些解决方案似乎真的需要创造力。这些问题的设计者试图想出那些你无法轻易通过训练来应对的题目。而关于 IMO 鲜为人知的秘密是，你实际上真的可以通过训练来解决其中的很多问题。正如你指出的那样，随着整个 AI 和数学项目的进行，它之所以有趣，原因之一是 AI 的前沿领域是呈尖刺状的，而数学恰好就在其中一个尖刺上。但这种尖刺状具有分形特征，因为当你放大观察数学内部的具体进展时，你会发现有些东西比其他东西容易得多。如果我们只看 IMO，现在它已经是旧闻了。它们表现得非常出色已经有两年时间了。如果不是因为下面这个原因，它们在 2024 年本来可以拿到金牌的。它们非常厉害。它们基本上就是冷启动直接解决了几何问题。IMO 有这四类问题：几何、数论、代数和组合数学。对于几何题，自 2024 年以来它只需十九秒就能解决，因为它是一个暴力求解器。鲜为人知的秘密是，对学生来说，同样也有一种暴力求解的方法可以去应对。组合数学则是一个未知数：这些问题要有趣得多，看起来更像谜题。那年的试卷上有两道组合数学题，但情况并非总是如此。总共有四个类别和六道不同的问题，所以哪个类别会有两道题就像抛硬币一样随机。如果是几何题多一点，它们那年就能拿到金牌了。但它在那些组合数学题上陷入了挣扎。那些试图为人类保留数学最后一点阵地的人可能会说，那些正是需要更多创造力的题目。即便如此，你问题的核心——如果它们正在解决千禧年大奖难题，那是否也意味着可以胜任许多白领工作？——这暗示着，无论我们目前所处位置与那目标之间的速率限制器是什么，它与让 AI 更好地胜任白领工作的速率限制器是相同的。我们可以描绘几种不同的情况。如果我们将焦点放在黎曼猜想上，解决它会是什么样子的？这些事物在特定知识领域非常厉害，能极其深入地了解它，然后又了解另一个领域，再了解另一个。你之前指出了这一点。拥有这种能如此精通各个领域的超人类广度，却找不到将它们联系起来的灵感火花，这很奇怪。我认为我们已经开始看到它在自己擅长的领域之间寻找联系的火花。我相信我们稍后会谈到这个。如果黎曼猜想的解决方案本质上是类似这样的东西，我觉得这与胜任白领工作所需的能力截然不同。而且有理由相信，这可能就是该解决方案的本质。我不知道你是否了解休·蒙哥马利和弗里曼·戴森在高等研究院的故事。这是一个题外话，但很有趣。我不知道那是不是在午餐期间或是类似场合发生的，但有位名叫蒙哥马利的数论学家当时正试图理解黎曼ζ函数零点对之间的统计相关性。黎曼猜想的核心就在于这些零点是否都位于一条直线上。他发现了你可以提出的这个定量问题，并写下了一个公式。它看起来像一除以正弦平方或者类似的形式。而物理学家弗里曼·戴森看到后说：“我知道这个表达式。在研究随机厄米矩阵的特征值时会出现这个表达式，”这是在研究原子核能级时出现的东西。这两个看似不同的事物的统计规律竟然相同，这个想法促使人们去探索随机矩阵理论中是否有哪些方面可能与黎曼ζ函数相关。我认为那里是否能取得成果还是一个有点悬而未决的问题。但这种将两个不同领域连接起来的做法——如果事实证明黎曼猜想的解决方案是进一步探索类似这样的想法——这具有你所期望的大语言模型擅长数学的特征。它们是量子物理学的专家。它们也是解析数论的专家。它们应该能够看出这种相似性，而且不需要蒙哥马利和戴森正好在一起吃午餐并碰巧谈论起这件事。这跟白领工作完全不同。在某种程度上，如果你发现很难让 AI 担任编辑，那并不是因为它们无所不知而你只需要它们在事物之间找到灵感的火花。另一种可能性会是……合适的类比是什么呢？也许我们可以想想费马大定理，从费马提出这个问题到解决方案本身的样子，这个解决方案最终涉及到了数学中非常庞大的理论机器。这个问题的美妙之处在于你可以用非常简单的方式来表述它。你问关于 xⁿ + yⁿ = zⁿ 的问题。当 n 大于 3 时，这是否有整数解？你可能认为这应该有初等数论的方法可以解决，但就我们目前所知，就是没有。虽然真正的解决方案也许存在更简单的方法，但这可能就是它必须呈现的样子。这是一个如此复杂的思想集合，建立在几个世纪以来围绕椭圆曲线展开的工作基础之上。然后还有另一座思想的大山，是围绕这些被称为模形式的东西建立起来的。你必须先把这两座大山都建好，然后才能提出将它们连接起来的正确问题。如果黎曼猜想的解决方案涉及到建立一座新的大山，那么这种能力——提出正确的新想法的能力——感觉与它们现在的智能特征有着很大的不同。这并非你对雇佣的视频编辑所要求的那种技能。但是，如果它有能力建立起作为正确的新理论的大山，从而理清我们应该如何思考一个学科，这代表着一种如此之高的智能水平，如果它除了在数学本身构建大山之外，没有渗透到经济的其他方面，那才是令人惊讶的。或者至少，即使它不能原封不动地做白领人类能做的每一件事，它也会产生变革性的影响，而这与在 IMO 获得金牌没有对世界产生变革性影响的方式截然不同。

<details>
<summary>Original English</summary>

**Grant Sanderson**: It's an interesting question because it's hard to answer without knowing what the solution looks like ahead of time. If we take the IMO, the spirit of your question three years ago was in looking at how some of the solutions to these problems really seem to require creativity. The designers of these problems try to come up with things that you can't train for as easily. The dirty secret with the IMO is that you really can train for a lot of them. With the whole AI and math project underway, as you point out, one of the reasons it's interesting at all is that there's a spiky frontier to AI, and math is just right there in one of the spikes. But there's a fractal nature to that spikiness, because when you zoom into the specific progress within math, you have some things that are a lot easier than others. If we just think about IMO, which is old news at this point. It's been two years since they're really doing quite well. They would have gotten a gold in 2024 if not for the following reason. They're very good. They just cold-solved geometry basically. The IMO has these four categories of problems: geometry, number theory, algebra, and combinatorics. Geometry, it just solves it in nineteen seconds since 2024 because it's a brute force solver. The dirty secret is that for students, there's also a brute force way you can go at it. Combinatorics is the wild card: much more playful, puzzly-seeming problems. There were two combinatorics problems on that year's test, and there's not always. There are four categories and six different problems, so it's a toss-up which one is going to have two questions. Had it been more geometry questions, they would have gotten a gold that year. But it struggles on those combinatorics ones. Someone who's trying to keep that torch of the last holdout of math for humanity might say those are the ones that require more creativity. Even then, the spirit of your question—if they're solving a Millennium Prize problem, does that also service a lot of white-collar work?—suggests that whatever the rate limiter is between where we are now and that is the same as the rate limiter for making things better at white-collar work. We could paint a couple of different ways. If we focus on the Riemann hypothesis, what would it look like to solve that? These things are extremely good at a specific domain of knowledge, knowing it very deeply, and then knowing another domain, and another. You've pointed this out. It's bizarre to have something with this superhuman breadth that knows all the fields so well, and yet isn't finding those lightning bolts that connect them. I think we're starting to see sparks of it actually finding connections between the things it's an expert at. I'm sure we'll talk about it. If the nature of the solution to the Riemann hypothesis was something like that, that feels pretty distinct to me from what's necessary to get good at white-collar work. And there's a reason to believe that might be the nature of the solution. I don't know if you know the story of Hugh Montgomery and Freeman Dyson at the IAS. This is a side tangent, but it's a fun story. I don't know if it was over lunch or something like that, but you have this number theorist who is just trying to understand the statistical correlation between pairs of zeros of the Riemann zeta function. The Riemann hypothesis is all about whether all these zeros sit on a straight line. He finds this quantitative question you could ask, and he writes down a formula. It looks like one over sine squared or something like that. Freeman Dyson, a physicist, is like, "I know that expression. That expression comes up in studying the eigenvalues for random Hermitian matrices," which was something that comes up in studying the energy levels of a nucleus. The idea that the statistics of those two seemingly different things were the same prompted an exploration of whether there are aspects of random matrix theory that might be relevant to the Riemann zeta function. I think it's a little bit of an open question whether there is fruit to be had there. But that bridging together of two different fields—if it turned out that the solution to the Riemann hypothesis was exploring an idea like that even further—has the character of how you expect LLMs to be good at math. They're experts at quantum physics. They're experts at analytic number theory. They should be able to see that similarity in a way that doesn't require Montgomery and Dyson to be having lunch and happen to talk about it. That's totally different from white-collar work. To the extent that you have a hard time using an AI as an editor, it's not because they know everything and you just need them to find that lightning bolt in between. A different possibility would be… What's the right analogy? Maybe if we think of Fermat's Last Theorem, between the moment of Fermat phrasing the question and what the solution itself looks like, where the solution ultimately involves such heavy machinery in math. The beauty of that problem is you can phrase it so simply. You ask about xⁿ + yⁿ = zⁿ. Do you have integer solutions for this when n is bigger than three? It's something you might expect there to be an elementary number theory approach to, but as far as we can tell, there's just not. Whereas the actual solution, maybe there is something simpler, but this might be what it has to be. There’s such a complicated set of ideas that build on centuries of work centered around elliptic curves. Then there's this other mountain of ideas centered around these things called modular forms. Both of those mountains have to be built before you can ask the right question that connects them. If the solution to the Riemann hypothesis involved building a new mountain, that's a kind of skill—the ability to come up with the right new ideas—that feels sufficiently different from the character of how they're intelligent right now. It's not like that's what you need from your hired video editor per se. But if it's capable of building mountains that are the correct new theory crystallizing how we should be thinking about a subject, that's just such a level of intelligence that it would be surprising if it didn't permeate into other aspects of the economy besides just the mountain-building for math itself. Or at the very least, even if it couldn't literally do every single thing white-collar humans can do, it would just have transformative effects in the way that getting gold in the IMO did not have transformative effects on the world.

</details>

**Interviewer**: 首先，我确实想指出，我在这里完全是在移动球门。两三年前我采访达里奥时，我问了这样一个问题：为什么他们没能利用自己渊博的知识将各种想法联系起来，从而以此方式做出新的发现。这似乎是这样一种事情：即使是一个中等聪明的人，如果他们掌握了这么多信息，也能够从“这种药物会引起偏头痛，而另一种东西有这个作用，也许正是同一种药物可以治愈这两种症状”的事实中得出医疗诊断。从一个外行人的视角来看，数学显然是一个这样的领域，比如找到单位距离问题猜想的反例就是这种事情的一个例子。所以这完全是在移动球门。但是接下来我们可以问，下一个基准测试是什么？既然 AI 可以做这件我们本以为它们能做的事情，那么下一件会非常令人印象深刻的事情是什么？这里有几个候选的想法。一个是能够首先提出有趣的问题，另一个是想出能够创造或统一各个领域的新的对象或概念化方法。关于第一点，现在我们有这些千禧年大奖难题，是因为数学家们注意到了它们。黎曼提出了黎曼ζ函数这个概念，因为他认为这个函数的零点会与素数的密度有某种联系。首先要弄清楚为什么我们认为这是一个值得研究的有趣事物，为什么我们要构建这个对象并试图回答有关它的问题——并回答这个特定问题——这似乎就是那种能成为下一个基准测试的事情。

<details>
<summary>Original English</summary>

**Interviewer**: First of all, I do want to point out that I'm totally moving the goalpost here. When I interviewed Dario two or three years ago, I asked this question about why they haven't been able to use their vast knowledge to connect ideas together and come up with a new discovery that way. That seems like the kind of thing where even a moderately intelligent person, if they knew this much information, would be able to come up with a medical diagnosis from the fact that this drug causes migraines, and this other thing does this, and maybe it's the same drug that can cure both things. From an outsider's perspective, mathematics seems clearly like a field where finding the counterexample to the unit distance problem conjecture was an example of this kind of thing. So it’s total goalpost moving. But then we can ask, what is the next benchmark? Now that AIs can do this thing we should have thought they'd be able to do, what is the next thing that would be quite impressive? There are a couple of candidate ideas here. One could be coming up with interesting problems in the first place, and the other is coming up with new kinds of objects or conceptualizations that create or unify fields. On the first one, right now we have these Millennium Prize problems because mathematicians have noted them. Riemann came up with this idea of the Riemann zeta function because he thought the zeros of this function would have some connection to the density of prime numbers. Figuring out why we think this is an interesting thing to study in the first place, why we are building this object and trying to answer questions about it—and answer this particular question about it—seems like the kind of thing that would be the next benchmark.

</details>

**Grant Sanderson**: 你在那里强调了两个非常好的例子。对于任何对单位距离猜想感到好奇的人，有一个名为 Polylog 的数学频道制作了一个非常棒的视频，他们在那里讨论了这个问题。所有这些讨论都促使人们反思做数学的过程。他们会想，“哦，这个东西能做这些令人印象深刻的事情。这对我们意味着什么？”那个视频里的一个人强调了这句名言：“优秀的数学家证明定理，伟大的数学家提出猜想，而最伟大的数学家提出定义。”这或多或少正是你在这里所表达的框架。我们需要猜想生成器，然后是定义生成器。那才是高级层次的数学家。我不太明白你究竟会如何把这个做成一个基准测试。通常，当我想到基准测试这个词时，我想到的是像球门柱一样的东西。球要么穿过了球门，要么没有。你可以很清楚地说，“是的，这件事完成了。”这在一定程度上是为了能够做像 RLVR 这样的事情，但也是为了知道你在回答问题时没有移动球门。OpenAI 可以把他们证伪单位距离猜想的事迹作为头条新闻，因为这是一件清晰明确的事情。它做到了。然而，想象一下如果头条新闻是关于 GPT-5.4 提出了一个非常好的猜想。“我们保证，每个人都认为这是一个很好的猜想。”这给人带来的感觉就是不一样。但也许这并不能否定它是一个值得思考的正确方向这一事实。如果它真的呈现出一种基准测试的形式，即我们有一个分数来表明它通过了测试，因为我们可以量化一个猜想有多好，我会感到非常惊讶。它要实现这一点，可能需要的本质在于，你会感觉到在与数学家们的对话中发生了基调的转变……

<details>
<summary>Original English</summary>

**Grant Sanderson**: You highlight two pretty good examples there. For anyone curious about the unit distance conjecture, there's this really nice video by a math channel called Polylog where they talk about it. All of these discussions cause people to reflect on the process of doing math. They're like, "Oh, this thing can do this impressive stuff. What does that mean for us?" One of the people in that video highlights this quote: "good mathematicians prove theorems, great mathematicians come up with conjectures, and the greatest mathematicians come up with definitions." That's more or less exactly your framing here. We need the conjecture generator and then the definition generator. That's the premium-tier mathematician. I don't understand how exactly you'd make that a benchmark. Usually, when I think of the word benchmark, I'm thinking of something that is a goalpost. The ball is through the goal or it's not. You can clearly say, "Yes, this is done." Partly that's to be able to do things like RLVR, but also partly just to know that you haven't moved the goalpost in answering. OpenAI can have their headline on disproving the unit distance conjecture because it's a clear, distinct thing. It did it. Whereas imagine trying to have a headline on GPT-5.4 coming up with a really good conjecture. "We promise, everyone thinks it's a good conjecture." It just doesn't land the same way. But maybe that doesn't negate the fact that it's the right thing to be thinking about. I would be surprised if it ever took the form of looking like a benchmark, where we have a score saying it's passed because we can quantify how good a conjecture is. The nature of what it would take is probably that you'd feel a tone shift in conversations with mathematicians

</details>

<!-- chunk 2/9 -->

### AI发展带来的语境转变与基准测试的局限性

**Speaker A**: 关于它如何有用的工作方式。你提到的那个系列——目前还没有完全制作出来，大概还要等几个月——采取了我们采访许多数学家的形式。有趣的是，我们从一年多以前就开始做这件事了。看到他们从2025年中期到现在（2026年）谈论人工智能时的语境发生了轻微的转变，这很有意思。在现实世界中，这是一段很短的时间。但在人工智能领域，这就像是经历了无数个纪元。我们能够看到这几个纪元中语境的转变。我认为你衡量（AI）提出猜想能力的方式，将基于这种语境的转变，变得更加主观。那将会是数学家们说，他们不仅在使用它来解决自己的问题，而且当他们退一步，决定自己的研究领域究竟应该是什么时，与某个特定模型的对话对此真的很有帮助。我不认为你可能会在头条新闻上看到“这又是一个被攻克的基准测试”这样的形式。这非常有趣。那些你无法为其制定基准测试的事情，至少在目前的范式下，也是你无法轻易针对其进行训练的事情。基准测试和训练环境之间实际上没有根本的区别。人们很容易提出某种二分法，比如“这就是为什么人工智能无法做某事的深层原因”，然后事实证明，你只是以错误的方式在思考它，并且它实际上很快就能做到了。但我会想出——

<details>
<summary>Original English</summary>

**Speaker A**: about the way it's useful to work with. This series you referenced, which is not at all produced yet and probably won't be for a couple of months, takes the form of us interviewing a lot of mathematicians. What's interesting is that we started doing this over a year ago, and it's fun to see a little bit of a tone shift in the way they talk about AI between mid-2025 and where we are now in 2026. In the real world, that's a very short amount of time. In the AI world, that's eons. We're able to see this tone shift over those eons. I think the way you'd measure conjecture-generating ability is going to be more subjective, based on that tone shift. It will be mathematicians saying they're not just using it to solve their problems, but that as they step back and decide what their research field should even be, a conversation with such-and-such model was genuinely helpful for that. I don't think it's likely you'd see it in the form of a headline saying this was yet another benchmark knocked down. It's very interesting. The kinds of things you can't make benchmarks for are also the kinds of things, at least in the current paradigm, you can't easily train for. There's really no fundamental difference between a benchmark and a training environment. It's very easy to come up with some dichotomy of, "here's a deep reason why AI can't do a certain thing", and then it turns out you're just thinking about it the wrong way, and actually it can do it pretty soon thereafter. But I'm going to come up with—

</details>

**Speaker B**: 反正你总会想出几个。也许结果会证明，在相对较短的时间内，我们有办法训练人工智能来做这些事情。但这似乎必须与目前的RLVR（基于强化的逻辑推理验证）训练有所不同。我很好奇的是——在我看来，这通常是推动数学和科学取得重大进展的动力——想出一种思考问题的新方法，或者一种理解世界的新方法，从而统一不同的领域，催生全新的领域，并解决我们最初甚至没有打算解决的问题。爱因斯坦思考广义相对论（GR）的原因，并不是因为他想解释光为什么会弯曲，或者黑洞为什么存在。这些现象他最初甚至都不需要去解释。在数学中，作为一个完全不知道自己在说什么的外行，这看起来就像是：通常有一些证明特定问题的方法能够激发一种新的概念化，这种概念化会产生一个全新的领域和全新的思维方式，且极具生产力；而另一些方法则不能。我很想听你谈谈伽罗瓦（Galois）提出群论（group theory）的故事，他在五次方程没有求根公式的解法中运用了这一理论，以此来区分阿贝尔（Abel）几年前提出的没有涉及群论的另一种证明。如果你想对“群论是否是一个有趣的概念”进行验证循环（verification loop）——这里到底做出了什么有用的东西？或者为什么这个证明更好？——这个验证循环可能长达一百年。它涉及到密码学的出现和物理学的进展，而且群论中的思想与理解物理学中的对称性息息相关。关于“为什么这首先是一个富有成效的概念”，存在一个长达百年的验证循环。

<details>
<summary>Original English</summary>

**Speaker B**: You're going to come up with a couple anyway. It'll probably turn out that there are ways we can train AIs to do these kinds of things in the relatively near term. But it seems like it would have to be different from current RLVR training. The thing I'm curious about—and the thing that seems to me to drive a lot of the big progress in mathematics and in science generally—is coming up with a new way to think about a problem or a new way to understand the world that unifies different fields, spawns entire new fields, and solves problems we weren't even trying to solve in the first place. The reason Einstein was thinking about GR is not because he wanted to explain why light bends or why black holes exist. These are phenomena he didn't even need explained in the first place. In mathematics, as a total outsider who doesn’t even know what he’s talking about here, it seems like there are often ways to prove a specific problem that can motivate a new conceptualization—one which results in a whole new field, a whole new way of thinking, which is immensely productive—and ways which don't. I'd be curious to hear you talk about Galois coming up with group theory, distinguishing his solution to the quintic having no formula for the roots, and Abel coming up with a different proof a few years earlier that didn't come up with group theory. If you wanted to do a verification loop on whether group theory is an interesting concept—was something useful done here, or why is this proof better?—potentially that verification loop is a hundred years long. It involves cryptography coming around and physics making progress, and the ideas in group theory being relevant to understanding symmetries in physics. There's a hundred-year verification loop on why this is a productive concept in the first place.

</details>

### 伽罗瓦理论与跨越百年的验证

**Speaker A**: 你戳到我的兴奋点了，因为我在2022年原本打算做一个关于伽罗瓦的项目，虽然后来被搁置了，但我花了一年的生命去思考他到底做了什么。我可能会不小心在细节上讲得太长，你可以随时打断我。对于你的观点，这是一个完美的例子，因为要解释为什么它是一个有价值的洞见，并不能从直接的实用性中得出。当然，如果你考虑的是RLVR环境，这将是非常困难的。但有趣的是，即使有当时的人类验证者，也花了很长的时间才认识到它的有用性。对于爱因斯坦和广义相对论，人们立刻就能感觉到这是一个好理论。伽罗瓦理论之所以成为一个如此有趣的例子，是因为你切实地看到了一个思想经历了长达百年的时间，流经了许多不同人的大脑，然后才沉淀为数学界公认的好东西。稍微退后一步……你想听听这个问题的背景吗？我们在学校都学过求根公式。

<details>
<summary>Original English</summary>

**Speaker A**: You struck a nerve, because I had this project about Galois I was going to do in 2022 that I put on the shelf, but I spent a year of my life thinking a lot about what he did. There's a risk of me accidentally talking too long on the specifics, which you can hold me back on. It's a perfect example for your case, because describing why it was a valuable insight does not come from immediate utility. Certainly, if you're thinking about RLVR environments, this is going to be really hard to do. But it's interesting to note that even with human verifiers at the time, it took a really long time to recognize it as being useful. With Einstein and GR, people could feel this was a good theory right away. What makes Galois theory such an interesting example is that you literally have this hundred-year segment of an idea that flows through many different people's heads before it settles into something the math community agrees is good. To back up a little bit… Do you want the background on the problem at all? We all learn about the quadratic formula in school.

</details>

**Speaker B**: 我以为你要说我们在学校都学过群论，但我错过了那节课。

<details>
<summary>Original English</summary>

**Speaker B**: I thought you were going to say we all learn about group theory in school, but I missed that class.

</details>

**Speaker A**: 我们都学过群论……不，是求根公式。这是已知的。从某种意义上说，希腊人可以解二次方程，但他们并没有真正用代数来写出那些东西。真正写下那个公式的是阿拉伯人。有一个关于意大利数学家决斗的有趣故事——不是真正的决斗，只是智力上的挑战——他们秘密地找到了三次方程的公式，然后在此后不久，又找到了四次多项式的公式。所以对于数学家来说，一个自然的悬而未决的问题是：你能找到一个解五次方程的公式吗？四次方程的公式是个怪物。把它写下来会非常疯狂。你通常不会把它完整地写下来。你会把它分解成一个程序性的过程。你可能会认为这些东西的复杂性呈指数级增长。所以好几百年来，没有人真正回答这个问题。通常我们说阿贝尔是第一个证明它的人。他是一位年轻、早熟的挪威数学家。他证明了这根本是不可能的。并不是说你能找到一个五次方程的求根公式。最初他以为自己找到了一个，但他后来证明了那是不可能的。但我认为真正的功劳，你必须退后一步谈谈拉格朗日（Lagrange）。他找到了针对这个问题该提出的正确问题。我会在一个非常高的层次上解释一下。他研究了这个问题，并认识到能够解出这些多项式与理解某些代数表达式的对称方式密切相关。如果我写下 a + b + c + d，只是把四个变量加起来，即使我排列它们的位置，也不会改变表达式的值。但如果我写下 a + b * c + d，某些排列不会改变它，而另一些排列会。他有一个非常棒的洞见：如果你能找到包含四个自由变量的表达式，并且无论你如何排列，它们只取三个不同的值，这与能够将四次方程降次到三次方程有着一种意想不到的联系。他开始通过思考是否能扩展这种方法，来探讨我们是否能找到一个五次多项式公式。为了扩展这种方法，你必须拥有一个包含五个自由变量的表达式，这样当你对它们进行5的阶乘（5!）种排列时，它最多只取四个值或更少。你可以把它放进拼图书里。你可以把它放进十二岁孩子也能参与的脑筋急转弯里。你不难发现，你会觉得那是一个不可能完成的任务。拉格朗日坐在那里说：“这是解决寻找五次多项式公式这一问题的一个策略。至少从这个策略来看，它似乎是不可能的。”但那是历史上人们第一次凭直觉意识到，某种关于对称性的问题才是研究这些多项式的正确方法。在他看来，这仅仅是一种方法。它还有待被发现其中存在着更紧密的联系。或许，我们不仅应该寻找公式，还应该反问一个问题：你能证明这是不可能的吗？他在某种程度上播下了这颗种子。

<details>
<summary>Original English</summary>

**Speaker A**: We all learn about group theory… No, the quadratic formula. This was known. In some sense, the Greeks could solve quadratics, but they didn't really write things in algebra. It's really the Arabs who wrote down that formula. There's this delightful story about dueling Italian mathematicians—not real duels, just intellectual challenges—who secretly found a formula for the cubic, and then very shortly thereafter found a formula for degree-four polynomials. So a natural open question for mathematicians is, can you find a formula that solves degree-five equations? The degree-four formula is a monster. It would be wild to write it down. You usually don't write it down in full. You break it up as a procedural thing. You might believe these things have this exponentially increasing complexity. So for many hundreds of years, nobody was really answering that question. Usually, we say Abel was the first to prove it. He was this young, precocious Norwegian mathematician. He showed it's simply impossible. It’s not that you can find a quintic formula. He thought he found one initially, but he showed it's impossible. I think the real credit though, you have to back up a bit and talk about Lagrange. He found the right kind of question to ask about this. I'll give it at a very high level. He was studying the question and recognized that being able to solve these polynomials is very related to understanding the way certain algebraic expressions are symmetric. If I write down a + b + c + d, just adding four variables, and I permute those, it doesn't change the value of the expression. Whereas if I write a + b * c + d, some of the permutations don't change it, but some of them do. He had this really nice insight about how if you can find expressions that have four free variables, but all the permutations take on three distinct values, that has this unexpected relationship with being able to reduce degree four into degree three. He started approaching the question of whether we can find a quintic polynomial by wondering if he could extend that method. To extend that method, you would have to have an expression that has five free variables such that as you permute them over all the five factorial permutations, it takes on only four values or fewer. You could put that in a puzzle book. You could put that in a brain teaser that a twelve-year-old could engage with. It's not too hard to find yourself feeling like that's an impossible task. Lagrange is sitting there saying, "Here is a strategy to solve this problem of finding a quintic polynomial. It seems like it might be impossible, at least from this strategy." But that was the first time in history that people had the instinct that some kind of question about symmetry was the right way to study these polynomials. In his mind, it was just a way. It had yet to be discovered that there was actually a tighter connection. Also maybe rather than searching for the formula, we should be asking the opposite question: can you prove that it's impossible? He sort of planted that seed.

</details>

### 伽罗瓦的抽象与被拒的奖励信号

**Speaker A**: 大约五十年后，阿贝尔肯定读过拉格朗日的著作，并受其影响。我们知道伽罗瓦在迷上数学的时候非常崇拜拉格朗日。很难想象这两个年轻的天才围绕这个问题得出非常相似的见解，不是源于拉格朗日。但至于你提出的“你是否能够验证这是一个好主意”的问题，拉格朗日并没有得出任何结果。他没有解决这个问题，所以这并不是一个基于解决方案就知道这是正确提问的案例。他只是提出了这个问题。这个问题本身就存在某种内在的趣味性。在当时，它对数学来说也不是非常重要。大多数人对它在物理学中的应用更感兴趣。这几乎是次要的、娱乐性质的、业余爱好者才会搞的东西。阿贝尔开始研究五次方程的内容，但他后来被建议把更多的精力花在研究椭圆函数上，所以在他英年早逝之前，他的大部分工作都在那上面。他在二十六岁时死于结核病。然后伽罗瓦把这两个想法推向了正确的方向，他真正理解了抽象的本质。他在监狱里写下了一篇非常棒的文章。我们可以谈论他一生的所有故事。非常疯狂。但还是个少年的他，身处监狱，他曾试图提交他的数学论文，但都被拒绝了。所以，再次思考关于“可验证的奖励”，在当时充当“验证者函数”的科学院拒绝了他所写的东西。坦率地说，那写得不是很连贯。它不是一个完整的证明。他也没有清楚地表达出这个理论实际上是什么。他只是一个刚刚起步、还在摸索方向的年轻数学家。那里的验证奖励是：“不合格”。但他有一种直觉，那里有一些有价值的东西。所以他写了这篇长篇大论，探讨数学的本质是随着时间的推移经历这些转变的东西。他谈到了代数本身的出现，以及从仅仅用数字思考，到对纯代数表达式具有一定的熟练度，也就是你不再被束缚于去解释那些表达式。他有一种直觉，似乎我们应该进行另一层面的抽象，我们不应该考虑公式本身，而应该考虑隐藏在这些公式背后的对称性是什么。但这仍然是一个定义不太明确的理论。如果你试图说验证奖励是他解决了一个别人没有解决的问题，那么，阿贝尔已经证明了五次方程是无解的。所以伽罗瓦在做什么？原则上，伽罗瓦理论允许你拿一个特定的多项式，并给你提供规则来说明该特定多项式是否具有你可以写下来的根。例如，对于 x⁵ - 1，你知道一个解是1。或者对于 x⁵ - 2，你可以写下 2 的五次方根。所以，并不是说你不能写下所有五次多项式的解，而是你能否找到一个特定的多项式，在那里你证明你不能用根号写出它的解？他也并没有准确地解决这个问题。他没有证明对于一个具体的例子他做不到。甚至连描述他解决了什么问题都非常棘手。然后他就去世了。有一个关于他参与决斗的非常浪漫的故事。关于他在决斗前一晚据说写下了他所有思想的传闻有很多，但实际上，他在此之前已经尝试过五次让它们发表。

<details>
<summary>Original English</summary>

**Speaker A**: Around fifty years later, Abel definitely read Lagrange and was influenced by it. We know that Galois loved Lagrange when he was falling in love with math. It's very hard to imagine that these two young geniuses coming up with pretty similar insights around that problem wasn't born from Lagrange. But to your question on whether you are able to verify that this was a good idea, there wasn't any result that Lagrange came to. He didn't solve the problem, so it wasn't a case of knowing it was the right question to ask based on a solution. He just asked it. There's some intrinsically interesting thing about it. It also wasn't very important for math at the time. Most people were more interested in the applications to physics. This was almost a side, recreational, hobbyist-type thing. Abel started working on quintic stuff, but then he was advised to spend more of his efforts studying elliptic functions, so more of his work was on that before he died young. He died at twenty-six from tuberculosis. And then Galois pushed both of those ideas in the right direction, where he really understood the nature of abstraction. He had this really nice piece that he wrote while he was in prison. We could talk all about his life story. It's pretty wild. But he's this teenager, he's in prison, and he had tried to submit his math papers and they had been rejected. So again, thinking about verifiable reward, the verifier function that is the academy at that time is rejecting what he wrote. Frankly, it was not very coherent. It wasn't a complete proof. He wasn't giving a clear thought of what the theory actually was. He was just a young fledgling mathematician getting his bearings. The verified reward there is, "No good." But he has some instinct that there's something there. So he's writing this diatribe on the nature of math being something that undergoes these shifts over time. He talks about the advent of algebra itself and going from just thinking in terms of numbers to having a certain fluency with pure algebraic expressions, where you're not tied to interpreting those expressions. He has this instinct that there seems to be another layer of abstraction that we should be doing, where rather than thinking about the formulas themselves, we're thinking about what symmetries underlie those formulas. But it was still a pretty ill-defined theory. If you're trying to say the verified reward is that he solved a problem that other people haven't, well, Abel already proved that quintics are unsolvable. So what was Galois doing? In principle, Galois theory lets you take a specific polynomial, and it gives you the rules to say whether that specific polynomial has roots that you could write down. For example, with x⁵ - 1, you know that a solution is 1. Or x⁵ - 2, you can write down the fifth root of two. So it's not that you can't write down the solution for every quintic polynomial, but could you find a specific one where you prove you can't write the solution using radicals? He also didn't even solve that exactly. He didn't show for a specific example that he couldn't. Even describing what problem he solved is very tricky. He then dies. It's this very romantic story of him having this duel. There's a lot of myth around how he supposedly writes up all his ideas the night before the duel, but really, he tried to get them published five times before.

</details>

**Speaker B**: 研究五次方程似乎对你的健康没有好处。

<details>
<summary>Original English</summary>

**Speaker B**: Working on the quintic doesn't seem to be good for your health.

</details>

**Speaker A**: 非常糟糕。如果你是一个年轻的天才，别去研究五次方程。他让他的兄弟和密友把他的笔记交给高斯（Gauss），把这些笔记交给当时重要的数学家，因为他认为那里面有价值。即便如此，它也没有真正被接受。他的兄弟和朋友试图把它们传播出去，但直到又过了二十年……

<details>
<summary>Original English</summary>

**Speaker A**: It's very bad. If you're a young genius, don't work on the quintic. He asks his brother and his close friend to get his notes to Gauss, to get these notes to the important mathematicians of the day, because he thinks there's something there. Even then, it didn't really take. His brother and his friend tried to get them out, but it was another twenty years until 

</details>

<!-- chunk 3/9 -->

### 数学发现的价值与衡量标准

**Speaker A**: 刘维尔（Liouville）看到这些笔记，发现里面可能有些东西，于是试图将它们整理清楚，并理解伽罗瓦（Galois）到底想表达什么。即便如此，又过了大约二十年，若尔当（Jordan）才真正整理出类似现代群论的内容，并将其归功于伽罗瓦。你很容易想象历史会有不同的走向，这些想法可能从数学的其他领域产生，而如果伽罗瓦不是一个如此引人注目的人物，他可能就会在历史中被遗忘了。但从拉格朗日（Lagrange）隐约察觉到也许“根的对称性”是正确方向，到它最终看起来像现代群论，中间经历了漫长的跨度。很多时候，它甚至无法通过人类审查者的“可验证奖励（verified reward）”。它被放到某个人的桌上，他们会说：“我真不知道这到底有什么用。”你必须要有那么一个人能赏识它。即便如此，在当时它也并没有真正解决实际问题。你提到了密码学和物理学之类的内容。你得等到二十世纪，才会出现盖尔曼（Gell-Mann）认为，理解某些群如何破缺的本质，可能与粒子的构成有联系。他纯粹基于一个群论问题预测了夸克的存在。那是群论最有趣的应用之一：甚至连预测夸克的存在本身，也是一个群论问题。这距离拉格朗日的时代已经过去很久了，你才看到类似这样的成果。所以你必须思考，什么样衡量进步的方式不是基于解决问题，而是某种程度上捕捉到了伽罗瓦说“我觉得这里有些东西”时内心的直觉？拉格朗日说“我认为这是正确的思考方式”时，他内心的直觉是什么？刘维尔说“这个早已死去的年轻人留下的这些零散笔记可能有些价值”时，他内心的直觉又是什么？这真的很难确切描述。我现在正在制作的另一个系列视频，是关于“压缩即智能（compression is intelligence）”这个观点的。尽管这不完全是我采用的视角，但“更具预测性的简短表达式让人感觉更智能”这种想法，确实有一定道理。所以我很好奇，能在多大程度上不仅围绕“你是否解决了它”或“它解决了什么”来给予某种可验证的奖励，还能围绕“完成它所需概念的简练程度”来给予奖励。

<details>
<summary>Original English</summary>

**Speaker A**: Liouville sees these notes, sees that maybe there's something in them, and tries to clean them up and understand what Galois was getting at. Even then, it was another twenty years or so until Jordan actually puts together something like a modern treatment of group theory that they attributed to Galois. You could easily imagine history turning differently, where these ideas were coming about from other points in math, and Galois could have been forgotten in history if he was a less florid character. But between the time of Lagrange having this inkling that maybe symmetries of roots is the right way to go, to where it all looks like modern group theory, you've got this long span. A lot of the time, it's not even passing the verified reward of human reviewers. It gets on someone's desk and they say, "I don't really know if there's anything here." You have to have this one person recognize it. Even then, it's not really solving practical problems at that point. You pointed out cryptography and physics and things like that. You have to get into the twentieth century before you have Gell-Mann thinking that maybe understanding the nature of how certain groups break down has a relationship with what particles are made out of. He anticipates quarks based on a purely group-theoretic question. That's one of the more interesting applications of group theory: to even predict the existence of quarks is a group-theoretic question. That's so long after Lagrange before you have anything like that. So you have to ask, what is the way of measuring progress that's not based on solving a problem, but that is somehow capturing the instinct inside Galois's mind when he says, "I think there's something here"? What's the instinct inside Lagrange's mind when he says, "I think this is the right way to think about it"? What's the instinct inside Liouville's mind when he says, "These scattered notes from this long-dead youngster might have something to them"? It's so hard to put a finger on that. A different series of videos I'm making right now is about the whole "compression is intelligence" idea. Even though this isn't really the angle I'm taking, there is something to the idea that the smaller expression that's more predictive feels more intelligent. So I wonder the extent to which you can give some kind of verifiable reward around not just whether you solved it or what it is solving, but around the smallness of the concepts required to do it.

</details>

**Speaker B**: 回到解决黎曼猜想（Riemann hypothesis）的话题，如果是由AI解决的，那会是什么样？

<details>
<summary>Original English</summary>

**Speaker B**: Going back to Riemann hypothesis solutions, what would that look like if an AI solves it?

</details>

**Speaker A**: 我认为可能发生的第三种方式是，它只是单纯地比人类更努力地去算。就好像你可能会得到一个费马大定理（Fermat's Last Theorem）的初等证明，只是它被铺陈了数千页，读起来让人觉得不知所云。但更清晰的视角是通过椭圆曲线等方法来审视它。或许存在某个长达千页的黎曼猜想证明，但没有人能从中真正获得任何启发，而你真正想要的，是那些概念的简洁、压缩版本，随后才能让人类去理解。也许你可以把柯尔莫哥洛夫复杂性（Kolmogorov complexity）引入到尝试量化“优雅”的考量中。我不认为这很容易，但我确实认为，为了奖励这种“类似伽罗瓦的直觉”，而不仅仅是奖励你是否解决了一个问题，这是你必须要做的事情。

<details>
<summary>Original English</summary>

**Speaker A**: I think a third way it could happen is it just straight-up works harder. In the same way, you could maybe have an elementary proof of Fermat's Last Theorem that's just spelled out over thousands of pages that would be incoherent. But the cleaner way to view it is with elliptic curves and all that. Maybe there's some thousand-page proof of the Riemann hypothesis that no one's really getting anything out of, and what you actually want are the succinct, compressed versions of those ideas that would then lend themselves to human understanding. Maybe you throw Kolmogorov complexity into your attempt to quantify what you mean by elegance. I don't think it's easy, but I do think it's something you would have to do in order to reward the Galois-like instinct, rather than just rewarding whether you solved a problem.

</details>

**Speaker B**: 为科学发现制定出启发式算法（heuristic）是非常困难的。但很明显，人类以某种方式一直在这么做，而且很显然，AI在未来的某个时刻也会做到这一点。

<details>
<summary>Original English</summary>

**Speaker B**: It's very hard to come up with the heuristic for science. But it's clear humans have been doing this somehow, and obviously, AIs will do it at some point.

</details>

**Speaker A**: 它不仅仅在“可验证奖励”方面具有相关性，最终的目标大概率还是为了理解，人类的理解。即使你确实得到了一个关于某个数学问题或某个宏大物理新理论的长达千页的证明，目标依然是理解。如果目标只是为了预测性，你也许可以直接让自动化的工程师去建造火箭，我们完全不知道它们是如何运作的，但我们能借此在星际间穿梭。但一定会有许多人想要弄清楚其中的原理。你依然会需要某种“简洁函数（concision function）”，将这种复杂的思考方式提炼成正确的那一种，就像牛顿发现万有引力定律那样。你还是会希望训练AI能够做到这一点，并找到这种经过压缩的知识表达。

<details>
<summary>Original English</summary>

**Speaker A**: It's relevant also not just in terms of verified reward, but presumably, the end goal is understanding, human understanding. Even if you do have some thousand-page proof of some math thing or some grand new physical theory, the goal is understanding. Maybe if the goal is predictiveness, you can just have automated engineers go off and build rocket ships where we have no idea how they work, but we can get between stars. But there are going to be a lot of people who want to understand. You're still going to want whatever the concision function is that distills down this complicated way of thinking into the right one, like the equivalent of the universal law of gravitation for Newton. You would still want to train AIs to be able to do that and find the compressed representation.

</details>

### 插播赞助 (Gemini 3.5 Live Translate)

**Speaker B**: 我八岁之前都在印度长大，所以除了英语，我也会说古吉拉特语（Gujarati）。既然谷歌（Google）刚刚发布了 Gemini 3.5 Live Translate，我觉得在节目的中插环节测试一下它应该会很有趣。[古吉拉特语] Gemini 3.5 Live Translate 能自动识别超过 70 种不同的语言，并在几乎实时的情况下将其翻译成目标语言。当你说话时，它能按照你原本的语速和表达方式进行实时翻译。就像它现在正在做的那样。我曾在 2024 年去过中国，我记得当时想，如果我能将在中国与研究人员或街头偶遇的人们的对话进行实时翻译，那趟旅程会高效得多。现在我们有了这种技术。所以，如果你正在开发一款需要实时翻译功能的应用，你百分之百应该试试 Gemini 3.5 Live Translate。现在它可以通过 Gemini Live API 以及在 AI Studio 中使用。前往 ai.studio/live 即可开始体验。

<details>
<summary>Original English</summary>

**Speaker B**: I grew up in India until I was eight, so in addition to English, I also speak Gujarati. And since Google just released Gemini 3.5 Live Translate, I thought it'd be fun to put it to the test in this mid-roll. (Gujarati) Gemini 3.5 Live Translate automatically detects more than 70 different languages and translates in almost real-time into the target language. Live translate your original speed and format while speaking. Just like it’s doing right now. I visited China back in 2024, and I remember thinking at the time that the trip would've been so much more productive if I'd been able to live-translate the conversations I was having with researchers and random people I met on the street. Now we have that technology. So if you're building an app that needs live translation, you should 100% check out Gemini 3.5 Live Translate. It's available now via the Gemini Live API and in AI Studio. Go to ai.studio/live to get started.

</details>

### AI 证明与数学理解的未来

**Speaker B**: 大家尤其对数学有这样一种担忧，即 AI 可能会证明黎曼猜想，而我们对数学的理解却不会因此变得更好。关于这一点我有几个问题。第一个问题是，这是否是我们应该预期发生的事情。当我们在研究一个重大问题时，人类会提出具有普适性的自然对象和子目标，不正是因为这在尝试解决复杂重要的问题时很管用吗？理论上讲，难道这不比单纯想出与思考该问题相关的自然抽象概念，成为一种更简单解决黎曼猜想的方法吗？然后第二个问题，从经验来看，这是目前我们观察到 AI 在问题上取得进展时的情况吗？当 AI 提出那个反驳“单位距离猜想（unit distance conjecture）”的反例时，你可以直接阅读它的思维链（chain of thought）。我看不懂，因为我对数学一窍不通，但对其他数学家来说似乎是可以理解的。它利用了已知的数学概念并证明了它们之间的关系，全都是用自然语言写成的。结果是，它加速了我们对这个对象和这个猜想之间联系的理解。从经验上看，这是我们应该担心的事情吗？

<details>
<summary>Original English</summary>

**Speaker B**: People have this worry about mathematics in particular that AIs will prove the Riemann hypothesis, and our understanding of mathematics won't be any the better for it. I have a couple of questions about this. The first one is whether this is something you should expect. Isn't the reason humans come up with general, natural objects and subgoals when we're working on a big problem that this is just useful when you're trying to work on a complicated, important problem? Theoretically, would this even be a simpler way to solve the Riemann hypothesis, as opposed to just coming up with the natural abstractions that are relevant to thinking about the problem? And then two, empirically, is this what we observe when AIs make progress on problems today? When the AI came up with that counterexample to the unit distance conjecture, you can just read its chain of thought. It's not understandable to me, because I don't know anything about mathematics, but it seems that to other mathematicians it was understandable. It made use of known concepts of mathematics and proved relationships between them, all in natural language. As a result, it accelerated our understanding of the connection between this object and this conjecture. Empirically, is this a thing we should be worried about?

</details>

**Speaker A**: 我认为这取决于其本质……如果我们把解决黎曼猜想的三种可能方式分解开来看……今年另一个重大的突破是某个编号为 1196 的埃尔德什（Erdős）问题，关于被称为本原集（primitive sets）的东西。它带有一种从看似不同的领域引入某个想法的特征。只要你向数学家展示了这个基本想法……你告诉他们：“如果我们尝试一种马尔可夫链（Markov chain）过程，用概率的方法自下而上而不是自上而下地证明这个东西是 1，并使用冯·曼戈尔特函数（von Mangoldt function），会怎么样？”如果你对懂行的人这么说，他们就会知道该怎么接着往下做。你有了这个非常微小的一个想法，它表现形式是结合了一个领域的专长与另一个领域的专长，并在两者之间画了一道小小的闪电。这会是非常易于人类理解的，因为你只需要展示这些连接的起点和终点是什么。如果它的特征是“造山（mountain building）”，你必须投入更多的时间去理解那座刚建立起来的新山峰，因为它是一条全新的脉络，而不只是两者之间的一道闪电。而如果这种进步的本质只是纯粹的死磕算力——一条超级长且没有任何新理论的推理链——那么你确实会有这种关于整个消化过程的担忧。所以我觉得并没有一个明确的单一答案。这取决于最终的解法会是什么样子。在造山那一侧，那实际上会非常有意思。它会不会默认就是非常容易被人类理解的，就像我们看到伟大数学家提出新理论那样？还是说，它会是一座奇异的、有别于人类思维的新山峰，以至于我们必须重新处理我们所接触的各种抽象概念？最接近的例子是目前对 abc 猜想（abc conjecture）的尝试性证明。我们或许不该深究那个话题，但它很可能并不是一个正确的解答。基本上，那是这位在日本原本声誉良好的数学家所提出的一种全新的思考方式。数学家们花了很长时间才勉强理清他到底在说什么，但它带有一种奇异数学的味道，那是在进行理论构建，而不仅仅是一长串推理。他称之为“宇宙际几何（inter-universal geometry）”。最大的担忧就是 AI 也做出这样的事，然后就像 abc 猜想一样，人们花了好几年的时间去攀登那座山峰，最后说：“该死。这根本就不对。”如果最后证明是错的，但它看起来真的很像对的。甚至即使它是对的，攀登一座新山峰也需要耗费巨大的努力。

<details>
<summary>Original English</summary>

**Speaker A**: I think it depends on the nature… If we break down the three possible ways of solving the Riemann hypothesis… The other big one from this year was a certain Erdős problem numbered 1196, about these things called primitive sets. It had that character of bringing an idea from a seemingly different field. As soon as you present the basic idea to a mathematician… You say, "What if we try the Markov chain process where we show that this thing is one from the bottom up probabilistically rather than the top down, and use the von Mangoldt function?" If you say that to someone in the know, they’d know how to run with it. You have this very small idea that has the form of expertise in one field and expertise in another, drawing a little lightning bolt between them. Those are going to be very human-parsable, because all you have to do is show the start and end point of what those connections are. If the character of it is mountain building, you have to put in a lot more time to understand that new mountain that was built, because it's a new thread, not just a lightning bolt between them. And if the nature of the progress was just raw hustle—a super long chain of reasoning with no new theories—then you would have that worry of this whole digestion process. So I don't think there's one clear answer. It depends on what the solution would look like. On the mountain building side, that would actually be really interesting to see. Is it by default very human-understandable, the way we see new theories from great mathematicians? Or is it an alien, different kind of mountain being built where we have to reprocess the kinds of abstractions we engage with? The closest example here would be the attempted solution of the abc conjecture. We maybe shouldn't get into that one, but it probably is not a correct solution. Basically it's this whole new way of thinking that this otherwise reputable mathematician in Japan had come up with. It took mathematicians a long time to even parse what he was saying, but it had the feeling of an alien bit of mathematics that's theory building, not just a long chain of reasoning. He called it inter-universal geometry. The biggest fear would be that an AI does that, and then much like the abc conjecture, people work for years to go up the mountain, and they're like, "Dang it. This just isn't right." If it turns out to be wrong, but it really looked right. Even if it was right, there's just a lot of effort to hike up a new mountain.

</details>

**Speaker B**: 如果我们最终陷入那种情况，大卫·贝西斯（David Bessis）写过一篇非常棒的博客文章，叫作《定理经济的衰落（The Fall of the Theorem Economy）》。他谈到，正如你所说，从历史上看，数学就是提出这些定义和问题，并围绕它们去证明定理。“证明定理”的这部分工作揽获了所有的赞誉，但它实际上只是“提出定义”这部分工作的寄生者。在历史上，这在声誉分配上并不是问题，因为如果你提出了一个定义，你多半也就是那个提出定理的人。但现在我们处在这样一种情况：如果最有价值的工作在于想出那个深刻见解，而 AI 自动化了后半部分（证明的部分）……想象一个场景，AI 就世界上许多重要的猜想提出了类似阿贝尔（Abel）那样直接的论证，然后我们就有了这些证明。现在需要由人类或者未来的 AI 来进行巩固和整理了。再次重申，我对这个论证的课题层面内容一无所知，但我确信如果你能获取到它，那将使你更容易思考到底发生了什么。有没有某种更深层的方法，能让我们理解这个证明为什么行得通，从而让我们更容易想出群论背后的那些理念？

<details>
<summary>Original English</summary>

**Speaker B**: If we end up in that situation, David Bessis had a really great blog post called "The Fall of the Theorem Economy". He's talking about how historically, as you were saying, mathematics is coming up with these definitions and problems, and it's about proving theorems about them. The theorem-proving stuff is what gets all the credit, but it's really a parasite on the coming-up-with-the-definition stuff. Historically, this has not been a problem in terms of credit apportionment, because if you come up with a definition, you're probably going to be the guy who comes up with a theorem. But now we're in a situation where if the valuable work is coming up with the insight and AI automates the latter part… Imagine a scenario where an AI comes up with Abel-like direct arguments about a bunch of important conjectures in the world, and then we just have these proofs. Now it's up to humans or future AIs to consolidate. Again, having no object-level understanding of this argument whatsoever, I'm sure that if you had access to it, it would make it easier for you to think about what's going on. Is there some deeper way in which we can understand why this proof works that would make it easier to come up with the ideas behind group theory?

</details>

**Speaker A**: 我认为那会有巨大的帮助。努力发现新数学的过程中，大部分时间都在犯错。你在试图解决一个问题，它的感觉并不像是在不断踏出正确的步伐登上山峰。绝大多数时候，它感觉像是在醉汉漫步，你做了一件事，然后发现自己错了，并且在不断地发现这一点。如果至少你能知道，努力消化你所拥有的东西最终能导向一个正确的答案，这就感觉像是一种进步，仅仅是因为那种确知它能通向解答的确定感。在近代数学史中，有太多这种感觉“手伸得比眼界长（reach has exceeded the grasp）”的例子，事情在被人们理解之前很久就已经被证明了。我最喜欢的一篇论文的开场白之一——那甚至不是一篇研究论文，而更像是一篇解释性的文章——是来自一位名叫 Timothy Chow 的数学家，他当时试图理解一个被称为“力迫（forcing）”的概念。这里有一个被称为连续统假设（continuum hypothesis）的问题，它大体上在问：你有一个自然数大小的无穷，还有一个实数大小的无穷。在这两者之间还有别的什么吗？

<details>
<summary>Original English</summary>

**Speaker A**: I think it would be hugely helpful. So much of trying to discover new math is mostly being wrong. You're trying to solve a problem, and it doesn't feel like constantly taking the correct step up the mountain. Mostly it feels like a random drunken walk, where you're doing a thing and then you're wrong and constantly discovering that. If at the very least you know that trying to digest what you have is ultimately leading to a correct solution, that feels like progress, simply because of the sense of knowing it leads to a solution. There are plenty of instances in the recent history of math where it feels like the reach has exceeded the grasp, where things are proven long before they're understood. One of my favorite openings to a paper—it's not even a research paper, it's more like an expository one—is from a mathematician named Timothy Chow, who was trying to understand a concept called forcing. There's this problem called the continuum hypothesis that more or less asks: you have a size of infinity for the natural numbers, and a size of infinity for the real numbers. Is there something in between?

</details>

<!-- chunk 4/9 -->

### 未决的解释性问题

**Speaker A**: 答案既是肯定的，也是否定的。这取决于你的公理。它超出了我们通常的公理系统的范围，这是一个有趣的答案。但是描述它的方法真的很难理解。这被称为“力迫法”（forcing）。

在这篇论文的开头，他写道：大家都知道未决的“研究”问题这个概念。我想提出一个未决的“解释性”问题的概念。当然，我们已经证明了它，但我们并不真正知道它为什么是真的。然后他提出了那个解释性问题的一个部分解决方案。你可以想象为什么我喜欢这种框架，因为这就是我的整个生活。我不做研究数学。我的工作完全是关于如何最清晰地理解这个东西，即使它已经被证明了。

<details>
<summary>Original English</summary>

**Speaker A**: The answer is both yes and no. It depends on your axioms. It's outside the scope of our usual axiom systems, which is an interesting answer. But the method to describe it is really hard to understand. It's this thing called forcing.

In the beginning of this paper, he writes, everyone knows the idea of an unsolved research problem. I want to propose the idea of an unsolved expository problem. Sure, we've proven it, but we don't really know why it's true. Then he proposes a partial solution to that expository problem. You can imagine why I loved that framing, because this is my whole life. I don't do research math. It's wholly about what's the most clear way to understand this, even if it's proven.

</details>

**Speaker B**: 证明和解释之间确实存在差异，我认为你正好触及了这种区分的重要性。

<details>
<summary>Original English</summary>

**Speaker B**: There is a difference between proof and explanation, and I think you're getting at the importance of that distinction.

</details>

**Speaker A**: 是的。那将是主要的激励因素。或者说，这种激励机制必须发生改变——不仅在数学领域，在其他科学领域也是如此——从证明关于世界的现象，转变为将这些证明整合为问题或更高层次的洞察。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. That will be the main incentive. Or the incentive would have to change, not just in mathematics but in other areas of science, from proving things about the world to consolidating proofs into problems or higher-level insights.

</details>

### 解释就是现实本身

**Speaker B**: 我们午餐时早些时候就在讨论你最近做的一个关于“设计以及它如何帮助我们理解事物”的演讲。在极限情况下，一个概念的构建与这个概念本身真的有区别吗？

如果你想想狭义相对论、时空图以及闵可夫斯基时空，这正是我们用来说明为什么存在长度收缩和时间膨胀的方式。但这其实就是现实……所以在某种意义上，在这里，解释似乎就是解释本身。

<details>
<summary>Original English</summary>

**Speaker B**: We were having a discussion earlier at lunch about a recent talk you were giving on design and how it helps us understand things. In the limit, is there really a difference between the conceptualization of an idea and the idea itself?

If you think about special relativity and spacetime diagrams, and Minkowski spacetime, this is a way in which we illustrate why there's length contraction and time dilation. But that is the reality… So, the exposition does seem to be the explanation in some sense here.

</details>

**Speaker A**: 这里有几点很有意思。首先，能够提出真正新颖见解的人与能够非常清晰地将其传达出来的人之间，似乎存在着极其强烈的正相关性。

你可能会认为情况恰恰相反，因为一个大学生的经历往往是：教他们的专家未必是那个学科最好的解释者，因为他们被自己的专业知识宠坏了。但至少在某些情况下，似乎事实是：那些真正提出非常新颖想法的人——比如爱因斯坦、克劳德·香农之类的人——当你阅读他们的论文时，你会发现非常清晰易懂。你不会觉得这只是写给专家看的，或者你必须拿着砍刀在丛林中劈砍才能读懂。他们是非常优秀的阐释者。理查德·费曼也有这个特点，他是个极佳的阐释者。也许大脑中在研究层面上提出正确新思维方式的同一区域，也正好拥有善于解释的诀窍。

我认为这与人工智能有关。我过去常常认为，AI 会成为这些自动化的定理证明器，而数学家的角色将转向我的工作，也就是解释这些东西。但现在我怀疑，实际上 AI 在解释方面也会非常擅长，可能比大多数人类在解释和提炼方面都要好。因此，由这些事物的发展本质来看，消化和解释正在发生的事情，或许实际上也不再是留给数学家做的事情了。我们可以讨论这种预测可能不准确的地方，但很可能，那个能够想出解决新问题的极好新想法的东西，同样也擅长解释它。这就是我的信念发生改变的地方。

<details>
<summary>Original English</summary>

**Speaker A**: There's a couple of interesting things there. One is that there seems to be a really strong correlation between the people who come up with genuinely novel insights and the people who are actually quite clear in their communication of it.

You might imagine the opposite, given that the experience of a university student is often that the expert teaching them is not necessarily the best explainer of that topic, because they're so spoiled by their expertise. But what seems, at least in some cases, to be the case is that the people who are really coming up with something quite novel—you've got Einstein or Claude Shannon or someone—you read their papers, and they're really lucid. It doesn't feel like this is just for the experts and you have to chop through it with a machete. They're very good expositors. Feynman has this characteristic too, he’s a very good expositor. Maybe the same part of the brain that comes up with the correct new way of thinking about it at a research level also has this knack for good explanation.

I think this is pertinent to AI. I used to think that AIs would become these automated theorem provers, but the role of mathematicians was going to shift towards my job, explaining these things. Now I suspect that actually they'll also be quite good at doing that, probably better than most humans are at explaining and distilling. So digesting and explaining what was going on is probably actually not what's left for mathematicians, by the nature of how these things are going. We can talk about ways this might not be it, but probably the same thing that comes up with the really good new idea that solves some new problem is also just good at explaining it. That's a way my beliefs have changed.

</details>

### 数学家未来的角色：策展人

**Speaker B**: 那么你认为你最后会做什么？包括你个人，也包括人类数学界整体会做什么？

<details>
<summary>Original English</summary>

**Speaker B**: What's the last thing you think you'll be doing? Both you and also what the human mathematical community will be doing.

</details>

**Speaker A**: 我大概会一直做我现在正在做的事情，直到我死去。如果那些末日论者说得对，也许这也是出于同样的原因。是的。你给一个人一团火，他能温暖一个晚上；但如果你把一个人点燃，他下半生都温暖了。这就是我现在对 AI 的看法。

作为解释者或教师的部分功能，是为某人好奇的事物增加清晰度。这是一方面。但其中也有一部分功能更偏向于人际关系，那就是提供动机和一种“策展”的感觉。

我听到过一个关于数学家最终会变成什么的有趣观点，那就是他们实际上会变得比任何其他职业都更像艺术博物馆的策展人。AI 解决了这个问题，所以这件艺术品已经存在了。它们甚至知道如何把它解释得非常好。但是你仍然需要有人帮助你在几乎无限的思想空间里导航，指出哪些想法值得去接触。即使 AI 在某种意义上在这个任务上做得更好，我认为我们总是仍然更喜欢一个与我们有关系的人类，因为我们对事物产生兴趣的动机本身就是一种社会现象。

如果你正在尝试构建某种特定的技术，那可能有所不同。但听这个播客的人，首先是信任你在筛选“什么是有趣话题”上的眼光。他们并不是因为你下一个话题刚好是他们本来就想了解的东西才来到这里的。他们信任你作为一个策展人。所以我的角色，可以说其他数学家的角色，可能实际上只是微妙地转向那种筛选哪些想法值得追求的策展方向。这也是我现在工作中的很大一部分。

我认为人们常以为制作视频的大部分时间都花在了视觉效果上。确实如此，那不是一蹴而就的。但实际上，很大一部分时间只是在决定一开始什么值得说，什么值得放在那里。我想要参与其中，我认为我与某些人之间建立了信任，即使 AI 比我做得更好，他们也好奇我会选择提出什么样的内容。这与人类音乐家永远都会有一席之地是出于同样的原因：即他们背后的故事所具备的社会功能，即使从某个模型输出的 MP3 文件的客观质量更好。这就是我预见的我的工作将会发生的变化。

<details>
<summary>Original English</summary>

**Speaker A**: I will probably be doing something like what I am until I die. If the doomers are right, maybe it'll be for the same reason. Yeah. You build a man a fire, and he's warm for one night. But set a man on fire, and he's warm for the rest of his life. So that's where I am with AI.

Some of the function of an explainer or a teacher is to add clarity to a thing that someone's curious about. That's one thing. But some of it is more relational, providing motivation and a sense of curation.

One interesting take that I've heard about what mathematicians will end up being is that it's actually more analogous to art museum curators than anything else. The AI solved the thing, so the art exists. They even know how to explain it really well. But you still want someone to help you navigate this nearly infinite space of what ideas are worth engaging with. Even if AIs were in some sense better at that, I think we would always still prefer a human that we had a relationship with, because the way we get motivated to be interested in things is a social phenomenon.

If you have some specific technology you're trying to build, that might be different. But the people listening to this podcast trust your curation on what's an interesting topic in the first place. It's not that they're landing here because whatever your next topic is, that's what they wanted to understand in a prior sense. They're trusting you as a curator. So my role, and arguably that of other mathematicians, might actually just shift subtly into that curation direction of what ideas are worth pursuing. That's a lot of my job right now.

I think people assume a lot of the time for a video goes into the visuals. Sure, it does. It’s not immediate. But actually a lot of it is just deciding what's worth saying in the first place, what's worth putting there. I want to engage with that, and I think I have a trust with certain people, and they're curious what I would choose to put forward even if the AIs are better than that. It's the same reason human musicians are always going to have a role: that social function of the story behind them, even if the objective quality of the MP3 file coming out of some model is better. That's what I see happening to my job.

</details>

### AI 作为思想的连接器与朗兰兹纲领

**Speaker B**: 我想回到早前的一个问题。正如 AI 已经跨越了这个门槛，这个能够连接现有思想以得出新发现，或者证明/证伪某事物的重要基准，我们就在想：“好吧，但下一步是什么？”

<details>
<summary>Original English</summary>

**Speaker B**: I want to go back to a question from earlier. Just as AI has crossed this threshold, this important benchmark of being able to connect existing ideas to come up with a new discovery or prove or disprove something, we're like, "Okay, but what's the next thing?"

</details>

**Speaker A**: 顺便说一句，在这个问题上还有很多事情要做。这仅仅是因为现在出现过几次灵光乍现的时刻……我认为在接下来的几年里，“真正地进行连接”会有一个繁荣发展的未来。

<details>
<summary>Original English</summary>

**Speaker A**: There's a lot more to do on that one, by the way. Just because a couple lightning bolts have been thrown… I think there's this flourishing future over the next couple years of really connecting.

</details>

**Speaker B**: 对。所以在极限情况下，你甚至可以说——我不知道这是否准确，但潜在地——许多最大的突破在某种层面上看起来就是这样的。以广义相对论为例，你只是把黎曼几何和狭义相对论连接在一起。因此，随着 AI 在建立连接这件事上变得越来越擅长，也许许多重大突破在性质上并没有什么本质的不同。我不知道你对此有什么看法。

<details>
<summary>Original English</summary>

**Speaker B**: Right. So in the limit, you could even say—I don't know if this is accurate, but potentially—a lot of the biggest breakthroughs look like this at some level. With general relativity, you're just connecting together Riemannian geometry and special relativity. So as AIs keep getting better and better at this connection thing, maybe a lot of big breakthroughs are not really of a different qualitative nature. I don't know if you have a take on that.

</details>

**Speaker A**: 很多关于数学的讨论都集中在解决问题上，比如攻克埃尔德什问题之类的事情。但我要说，甚至不是大多数数学家会把他们的工作特征描述为瞄准下一个要解决的问题。你熟悉朗兰兹纲领（Langlands program）吗？

<details>
<summary>Original English</summary>

**Speaker A**: A lot of the conversation has focused on problem-solving and that nature of math, ticking off Erdős problems or something. But I'd say it's not even a majority of mathematicians who would characterize their work as really targeting the next problem to tick down. Are you familiar with the Langlands program?

</details>

**Speaker B**: 不熟悉。

<details>
<summary>Original English</summary>

**Speaker B**: No.

</details>

**Speaker A**: 它甚至不能说是一个数学分支，而更像是一种研究思潮。费马大定理就是其中的一个例子。你有这两个看似毫不相干的东西，而它们之间建立的连接引出了一个解决方案。朗兰兹是一位数学家。他有一封著名的信，基本上阐述了：看起来很有可能还存在着大量类似的连接。他甚至对这种连接的性质做了一些更具体的描述，这样你就可以想象出一张巨大的地图，这里有个山谷，这里有座山，那里是一片平原。有许多数学家会认为，他们的工作属于试图理解这张地图上千丝万缕的线索的一部分。

那里的进展甚至不是说：“我们知道这一个特定的问题会因为那个连接而被解决。” 而是说，一次又一次地，存在许多重大问题因发现连接而被击破的案例，以至于现在的方向几乎变成了先发制人地去寻找连接。这其实非常有趣。任何时候你遇到一位数学家，问问他们：他们的工作性质是更类似于朗兰兹纲领，还是更类似于针对一个特定问题。你会在那里得到一种确定的分化现象。

AI 有可能成为超级连接器，感觉这可能是追求这一目标时的放大工具。

不过这很难衡量。这切中了我们早先说过的话：你如何打分来判定：“是的，你成功了”？如果它是解决了一个问题，你就有明确的方法可以说：“是的，你成功了。” 你可以写个新闻头条。作为 AI 公司，你可以进行公关宣传说：“我们做到了。” 相比之下，如果你感觉那就是该建立的正确连接，你能够围绕它写定理。这就是该领域论文看起来的本质。但我认为这需要更多的“人在回路”（human in the loop）来判断：“我们想要去建立的那种连接究竟是什么？”

这就是我对这些模型在未来五年内会产生的大多数有用进展的猜测。那真的就是在填补那张连接的全景图——如果你是横跨多个领域的专家，你本可以建立这些连接。正如你所指出的，我们现在还没有实现这一点，其实有些令人惊讶。

<details>
<summary>Original English</summary>

**Speaker A**: It's not even a field of math so much as it is a research ethos. Fermat's Last Theorem is one inkling of this. You had these two seemingly disparate things, and a connection between them led to a solution. Langlands was a mathematician. He has this famous letter essentially spelling out how it seems likely that there's a lot more connections like that. He even got a little bit more specific about the nature of the connections, such that you might imagine this large map, and you've got this valley over here and this mountain over here and this set of plains over there. There's a lot of mathematicians who would characterize their work as being part of trying to understand the threads on this map.

The progress there, it's not even "Here's this one specific problem that we know will be solved by that connection." It's more that time and time again, there have been cases where big problems were knocked down by finding connections, such that it's almost preemptively finding the connections. It's actually very interesting. Anytime you run into a mathematician, ask them whether the character of their work is more akin to the Langlands program or to targeting one particular problem. You get a certain bifurcated split there.

The possibility of AIs being supercharged connectors feels like it might be an amplifying tool in that pursuit.

It's hard to measure, though. This cuts to what we were saying earlier: How do you assign a score to say, "Yes, you've done it"? If it's knocking down a problem, you have a clear way of saying, "Yes, you've done it." You can write the headline. You can have your PR move as the AI company to say, "We did it." Whereas if it feels like that was the right connection to draw, you can write theorems around it. That's the nature of what the papers in that field look like. But I think it will require a lot more "human in the loop" to say, "What was the kind of connection that we were going for?"

That's my guess on what most of the useful progress from these models will look like in the next five years. It's just really filling in that landscape of connections that you can draw if you're an expert in multiple fields. As you've pointed out, it's kind of surprising we haven't already had this.

</details>

### 自回归生成与不太可能的连接

**Speaker A**: 我很好奇，在技术层面上，是什么带来了这里的突破？一方面，你可以为“为什么一个人可能是所有这些领域的专家，却没能画出那些连接”在脑海中描绘一个解释。当推理的方法是这种自回归的思维链现象时……如果你仔细想想，自回归实际上是一种非常奇怪的产出东西的方式。你是一个聪明人。想象一下我把你锁在一个盒子里，你与世界互动的唯一方式是收到一张小纸条，然后有人说：“你能预测接下来会出现什么吗？” 你预测了接下来会出现什么，然后你的记忆被清除了。你又拿到另一张小纸条。想象一下这个过程重复了一大堆次，然后从另一端输出出来的结果。他们说：“看看你写的这篇随笔。” 你看了看可能会说：“这太糟了。那不是我会写出来的随笔。”

这种不断重复预测某物的过程，与你作为作家在构思并思考写作时的思维方式是非常不同的。特别是，最可能发生的情况是你成了你上下文语境的奴隶。你可能在回答有关特定领域的某个问题，所以你调取了周围所有相关的上下文。但那些能产生所有实质内容的连接，就其本质而言，是非常小概率的事件。你可以做任何你想做的强化学习来试图在某些方面变得更好，但究竟是什么在特别增加权重并激励产生这些“不可能的连接”呢？因为这些连接中的绝大多数，都并非顺理成章接下来该预测出的那一个 token。所以，情况可能只是你确实把这种智能锁在那个盒子里了，但这却是一种与之互动的怪异方式。

我好奇的一点是：通过质疑 token 是如何产生的前提，你有没有得到过什么成果？我不认为这会像调节温度参数（temperature）那么简单，但是，有没有什么方法能够利用现有的智能水平，但却找到正确的方式去激发那些连接，从而解锁我们所看到的这类事物？或者，你只是需要稍微多一点的智能，使得在预测的层面上，它能预测到应该是——

<details>
<summary>Original English</summary>

**Speaker A**: I would be curious to know at a technical level what causes the unlock there. On the one hand, you can paint an explanation in your head for why you could be an expert in all of these things and not be drawing those connections. When the method of reasoning is this autoregressive chain-of-thought phenomenon… Autoregression is actually a really weird way to produce stuff, if you think about it. You're an intelligent person. Imagine I've locked you in a box, and the only way you have of interacting with the world is that you receive a slip of paper, and someone says, "Can you predict what will come next?" You predict what will come next, and then your memory's wiped. You get another slip of paper. Imagine that was done a whole bunch of times, and then what comes out on the other end. They say, "Look at this essay that you wrote." You might look at that and say, "This is awful. That's not the essay that I would've written."

The process of repeatedly predicting something is just pretty different from how you would think as a writer to compose it and think it through. In particular, what would probably happen is that you're a slave to your context. You might be answering some question about a particular field, so you draw on all the context around that. But the connection where all the substance is going to come from is, by its nature, a very unlikely one. You can do all the RL that you want to try to get better in some way, but what's the thing that's specifically upweighting and incentivizing making these unlikely connections when the vast majority of them aren't the predictable next token that would come in there? So it might be the case that you just have this intelligence locked inside that box, but it's a weird way of interacting with it.

The thing I'm curious about is: do you ever get any fruit by questioning the premise of how tokens are generated? I don't think it would be as simple as manipulating the temperature, but are there any things that you can do that take the existing level of intelligence but find the right ways of sparking those connections that unlock these sorts of things that we've seen? Or do you just need a little bit more intelligence, such that at the level of prediction, it's predicting that it should be

</details>

<!-- chunk 5/9 -->

### AI与跨领域连接能力

**Speaker A**: 能否将这种灵光一闪的能力带到另一个领域？我认为，相比于思考架构甚至损失函数，从数据的角度来推理会更有成效。我们有处理文本的扩散模型，它们生成的东西并非在性质上完全不同。只是它们还没有被充分探索过。我认为更相关的问题是：无论你使用什么架构或损失函数，你所拥有的数据在激励你生成什么样的结果？

<details>
<summary>Original English</summary>

**Speaker A**: making that lightning bolt to another field? I think it's more productive to reason, instead of architecture or even loss function, about data. We have diffusion models that do text, and the kinds of things they produce are not of a wholly different character. They've just not been explored as much. I think the more relevant thing is: what is the data on which whatever architecture or loss function you have is incentivizing you to produce?

</details>

**Dwarkesh**: 看起来它们确实在变得更好。先不谈数学，我们确实有一些这类事情的例子，但如果你只看为什么它们作为自主智能体变得越来越好……它们所处的环境，让它们自回归地生成“让我们退一步，对整个代码库进行搜索”这样的步骤，然后“让我们退一步，评估我的错误”才是真正有效的方法。

<details>
<summary>Original English</summary>

**Dwarkesh**: It does seem like they're getting better. Forget about math. We did have a couple of examples of this kind of thing, but if you just look at why they're getting better at being autonomous agents… They're in an environment where they’re autoregressively producing the step that says "Let's step back and do a search over the whole codebase," and then "Let's step back and assess my mistake," is the thing that works.

</details>

**Speaker A**: 我猜想在科学或数学取得进展的情况下，你面对的是前沿的类数学问题。数学家专门设计了这些问题，因为它们需要将两个不同的领域连接起来。我猜测有各种聪明的、部分合成的方法可以制造越来越难的此类问题，这些问题需要这种连接——例如，通过消除假设但仍要求AI得出答案——然后，损失函数是什么最终就变得不再重要了。关键在于，你是否能想出一个激励这种能力的环境？

<details>
<summary>Original English</summary>

**Speaker A**: I assume what happened in the case of progress in science or maybe in math is you have frontier math-like problems. Mathematicians have specifically designed them because they require connecting together two different fields. I'm guessing there's all kinds of clever, partially synthetic ways to make harder and harder problems like that that require these kinds of connections—for example, by eliminating assumptions and still requiring the AI to get to the answer—and then it doesn't really end up mattering what the loss function is. It's really about, can you come up with an environment that incentivizes this ability?

</details>

**Dwarkesh**: 感觉上你应该能做到。我当然说不出解锁所有这些的正确方法是什么，但这只是会让人非常惊讶。你不觉得如果未来三年内，没有出现更多那种灵光一闪的时刻，会很让人惊讶吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: It feels like you should be able to. I certainly can't speak to the correct ways of doing that to unlock all this, but it would just be pretty surprising. Don't you think it would be surprising if, over the next three years, there weren't a lot more of those lightning bolts?

</details>

### 数字心智的内在优势

**Speaker A**: 我认为这是一件值得思考的重要事情。我们经常思考单一系统有多聪明。而我们没有考虑到，AI所拥有的优势更多是它们其他特性的结果。所以在这个语境下，关于它们的关键事实是我们可以直接将它们并行化并任意扩展。无论它们具有什么水平的能力，那都不只是数学史上的某一个特立独行的天才，做出了一些联系然后在决斗中死去了。它是将那个水位线普遍应用于该能力水平下所有可触及的问题上。这是数字心智天生拥有的众多优势之一，而我们对此思考得还不够。其他的优势包括它们可以将所有的知识融合在一起——或者至少会有允许这种情况发生的技术——而且你可以生成具有相同知识水平的副本。这种并行化是一个非常重要的属性。

<details>
<summary>Original English</summary>

**Speaker A**: I think this is an important thing to think about. We often think about how smart a single system is. And we don't think about AIs having advantages that are more the result of other facts about them. So in this context, the key fact about them is that we can just parallelize and arbitrarily scale them. Whatever level of capability they have, it's not just one idiosyncratic genius in the history of mathematics who makes a few connections and then dies in a duel. It's universally applying that waterline across all problems that are accessible at that level of capability. This is among the many advantages that digital minds inherently have that we don't think enough about. The other ones being that they can merge all their knowledge together—or at least that there will be techniques that allow this to happen—and that you can spawn off copies with identical levels of knowledge. This parallelization is quite an important property.

</details>

**Dwarkesh**: 我很好奇你的预测。即使它们不如人类数学家聪明，但出于公关原因，AI公司正在这方面投入数十亿美元，这意味着数量本身就有一种质量。

<details>
<summary>Original English</summary>

**Dwarkesh**: I'd be curious about your predictions. Even if they're not as smart as human mathematicians, the fact that for PR reasons the AI companies are just throwing billions and billions of dollars at this means that quantity has a quality all of its own.

</details>

**Speaker A**: 那个方向似乎是正确的。如果我们回顾蒙哥马利（Montgomery）和戴森（Dyson）在普林斯顿高等研究院的对话，那次对话暗示了黎曼猜想——或者黎曼zeta函数零点——与随机矩阵之间存在某种联系，这感觉就是你可以尝试自动化的那种事情。你拥有代表所有这些领域专业知识的智能体。我们都知道，一个机构比一个个人更聪明。让人们都待在同一个地理位置的原因，就是你希望那些不期而遇的对话能够发生。在智能体之间设计这些对话会是什么样子呢？

<details>
<summary>Original English</summary>

**Speaker A**: That seems in the right direction. If we take that conversation between Montgomery and Dyson at the IAS that suggests some connection between the Riemann hypothesis—or the Riemann zeta-function zeros—and random matrices, that feels like the kind of thing that you could try to automate. You have agents representing expertise in all these fields. We all know that an institute is smarter than an individual. The reason for having people all in the same geographic location is that you want those serendipitous conversations to happen. What does it look like to engineer those between agents?

</details>

### 打破上下文与增加思维熵

**Dwarkesh**: 这很有趣，因为你指出你可以汇集所有的知识，但我真的很想知道，其中一个优势是否是你能够做与此相反的事情。有时候，当一个AI失败时，是因为它陷入了糟糕的思维链，很难让它摆脱出来。所以你会说：“我干脆重新开始。”人类也是一样的道理。有时候你开始以某种特定方式思考问题，而真正需要的就是退后一步。有很多关于人们为了证明某件事努力了很长时间的故事，然后到了某个时候他们会说：“等一下。如果我尝试证明它是不可能的，或者证明相反的情况呢？”解开你自己的上下文，以一种全新的思维去处理它……你可以想象将其系统化，或者拥有多个不同的智能体，刻意赋予它们不同的上下文片段，并试图在那里进行比较和对比。我们对自身的上下文并没有同样水平的操控能力。

<details>
<summary>Original English</summary>

**Dwarkesh**: It's interesting, because you point out that you can pool all your knowledge, but I really wonder if one of the advantages is that you can do the opposite of that. Sometimes when an AI is failing, it's because it gets into a bad chain of thought and it's really hard to get it out. So you say, "I'll just start again." Same deal with humans. Sometimes you start thinking about it in a certain way, and what's required is to just back up. There are stories about people trying to prove something for a long time, and then at some point they say, "Hang on a second. What if I tried to prove that it's impossible, or prove the opposite?" Unwinding your own context and going at it with a fresh mind… You could imagine systematizing that, or having multiple different agents deliberately given different pieces of context and trying to compare and contrast there. We don't have the same level of manipulation on our own context.

</details>

**Speaker A**: 在这个关于AI和数学的系列中，我们要做的第一集将是关于它们何时解决了国际数学奥林匹克（IMO）问题。我想集中讨论一个它们失败的特定IMO问题，这是一个很多非常聪明的学生也曾失败的问题。陶哲轩（Terry Tao）也曾在这个问题上失败过。人们对这道题非常生气，因为他们称之为“钓鱼题”（troll problem）。我几乎不想剧透它，因为我想围绕引导一个人进入这个问题而他们又不知道它原来有一个简单解的设定来构建这一集。你真的能对作为一个解决这个问题的学生是什么样的感觉产生共鸣。基本上，根据这是一道国际数学奥林匹克题的背景，有一种非常优雅的方法，让你顺着你真正觉得会是答案的方向走下去。这个解的特征真的很诱人，但很难证明它是最优的。原因就在于它并不是。存在一个几乎是不假思索就能得出的解，那才是最优的。这与整个AI故事的相关性在于，对于人类来说，回答那个问题所需的是逃离你的上下文。逃离身处IMO考场的上下文。逃离你为了解决这些竞赛数学题所受训练的方式的上下文。如果你只是像我把它作为一个脑筋急转弯抛给街上的某个人那样去对待它，他们可能很容易就能回答好。你有时也希望在其他环境中的人类研究中能有同样的情况，只是能够刷新你的思维并以完全不同的方式来处理问题。在数字心智拥有的所有优势中，这实际上可能就是其中之一：一种刷新思维的更系统化的方法。衍生出两个智能体，一个试图证明它，一个试图证伪它，一个用这种方法尝试，一个用那种方法尝试。它们刻意拥有不同的上下文。我很好奇，如果我们三年后进行这场对话，有多少登上头条的重大成果具有这种基本上抹去先前的上下文、尝试一大堆不同事情的特征，而不是合并一大堆不同智能体的结果。

<details>
<summary>Original English</summary>

**Speaker A**: In this AI and math series, the first episode we'll do will be about when they solved the IMO. I want to focus on one specific IMO problem that they failed on, which is one that a lot of very smart students failed on. Terry Tao also failed on it. People were very mad at the problem because they called it a troll problem. I almost don't want to spoil it, because I want to construct the episode around leading someone in without their knowing that it turns out to have a simple solution. You can really empathize with what it's like to be a student solving this. Basically, there's a really elegant way of going down what you really feel like is going to be the solution based on the context of it being an International Math Olympiad problem. The character of the solution is really enticing, but it's hard to prove that it's the best. The reason is that it's not. There's this almost brain-dead solution that is the best. The relevance of that to the whole AI story is that for a human, what's required to answer that question is to escape your context. Escape the context of being in the IMO. Escape the context of the way you've been trained to solve these contest math problems. If you just approached it like a brain teaser that I throw at someone off the street, they'd probably answer it well. You want the same sometimes for human research in other contexts, just being able to refresh your thinking and come at it completely differently. Of all the advantages that digital minds have, that might actually be one of them: a more systematic approach to refreshing your thinking. Spin off two agents, one who's trying to prove it and one who's trying to disprove it, one who tries it this way and one who tries it another. They deliberately have different contexts. I would be curious to see, if we're having this conversation three years from now, how many of the significant results that make headlines have that character of basically erasing the context previously, trying a bunch of different things as opposed to merging the results of a bunch of different agents.

</details>

**Dwarkesh**: 这极其有趣，因为人们对AI的一个普遍担忧是这种熵坍缩（entropy collapse），即它们都以相同的方式思考，因为它们是以相似的方式被训练出来的。这就是为什么它们不擅长写作的原因。它们沿着同一条路径走下去，拥有相似的说话模式等等。但也许AI拥有的关键优势是你能够系统地……听起来单位距离图猜想（unit distance problem conjecture）之所以花了这么长时间才被证伪，原因之一是人们假设这个猜想实际上是正确的，所以他们主要是试图找出证明它的方法。也许AI将拥有的一个关键优势是，通过系统地同时尝试证伪和证明任何给定的陈述来增加熵，或者能够系统地赋予不同的智能体不同的偏见。在人类科学史上似乎有一件重要的事情，那就是爱因斯坦真的受到了“事物在不同的参考系中应该看起来相同”这种偏见的驱动。他还有很多类似的其他偏见，但那一个对他的思维形成非常有影响。你可以系统地调查一大堆启发式方法，看看哪些在给定的问题上是有成效的。所以即使在自回归层面有这种不可避免的坍缩，你也会建议在提示词层面系统地增加熵吗？

<details>
<summary>Original English</summary>

**Dwarkesh**: It is incredibly interesting, because a common concern people have about AIs is this entropy collapse where they all think the same way, because they're trained in similar ways. This is why they're bad at writing. They go down the same path and have similar patterns of speaking and so forth. But maybe the key advantage AIs have is that you can systematically… It sounded like one of the reasons the unit distance problem conjecture took so long to be disproven was that people assumed the conjecture was actually true, so they were mostly trying to figure out ways to prove it. Maybe one of the key advantages the AIs will have is to increase the entropy by systematically trying out both the negation and trying to prove the positive of any given statement, or being able to systematically give different agents different biases. It seems like an important thing in the history of human science is that Einstein was really motivated by this bias that things should look the same in different reference frames. He had multiple other biases like these, but that one was very formative in his thinking. You can systematically survey a bunch of heuristics and see which ones are being productive on a given problem. So you would suggest systematically increasing entropy at the prompt level even though you have this inevitable collapse at the autoregression level?

</details>

**Speaker A**: 爱因斯坦会是一个有趣的例子，因为他有这种认为事物是相对的偏见。他也有“上帝不掷骰子”的偏见。你要确保不要不小心让你所有的LLM（大语言模型）都变成爱因斯坦，因为你可能会停止量子力学的进展。这就向你表明了科学并没有一个正确的启发式方法。你只需要多个具有自身启发式方法的独立研究项目。感觉就像是老派的软件。只要你能以某种方式描述它。你用老派的软件来放大这种熵。如果你能够为一个你想要提示的独特思维方式建立一个清晰的本体论（ontology），你去探索那个完整的本体论，然后每一个单独的智能体就会跑去做它该做的事。关于你具体如何描述不同的方法，这其中有一定的设计问题。简单的一个是：你试图证明它还是证伪它？更难的一个是说，你可以采取哪些所有的策略来证明这一点，并确保你正在以足够的广度来探索它们。

<details>
<summary>Original English</summary>

**Speaker A**: Einstein would be an interesting example, because he's got this bias toward things being relative. He also has a bias toward "God should not play dice." You want to make sure you don't accidentally have all your LLMs be Einstein, because you might halt progress on quantum mechanics. Which goes to show you that there's not a correct heuristic for science. You just need multiple independent research programs with their own heuristics. That feels like old-school software. As long as you're able to describe that in some way. You have old-school software that amplifies that entropy. If you're able to put a clear ontology to the distinct ways of thinking that you want to prompt, you explore that full ontology, and then each individual one runs off doing what it is. There's a certain design question there about how exactly you describe the different approaches. The easy one is: are you trying to prove it or disprove it? The harder one would be to say, what are all the tactics you could take to prove this, and make sure you're applying sufficient breadth to exploring them.

</details>

### Cursor赞助插播

**Dwarkesh**: 我认为人们并没有充分认识到，当你给这些模型配备一个像Cursor这样的好安全带（harness）时，它们就能为你处理这些类型的事情。举个例子，我开始在Bilibili上发布我的节目，希望能吸引到正在增长的中国观众——但我在那里上传的所有内容都需要剪掉赞助商的部分。通常这意味着要要求我的剪辑师回头去过一遍所有旧的剧集，剪掉广告，然后重新导出所有东西。但在这个大约只够我给他们发一条Slack消息的时间里，我可以直接让Cursor代劳并省了他们的事。而在播客研究方面，我有一个完整的代码库，我把我准备最近任何一集播客时相关的每一本书和每一篇论文都放在了那里。我能够直接把所有东西都丢进那里，因为Cursor的这个安全带非常擅长帮助模型弄清楚到底该提取什么——无论是从我的代码库还是从网络上——来回答我在研究时提出的问题。所以无论你现在碰巧在做什么工作，只要试着把Cursor指向它。去 cursor.com/dwarkesh 开始使用吧。

<details>
<summary>Original English</summary>

**Dwarkesh**: I don't think people appreciate the kinds of things these models can just go handle for you when you equip them with a good harness like Cursor. For example, I started publishing my episodes on Bilibili for a hopefully burgeoning Chinese audience — but everything I upload there needs the sponsored segments cut out. Normally that would have meant asking my editors to go back through all the old episodes, cut the ads, and re-export everything. But in about as much time as it would've taken me to send them that Slack message, I can just tell Cursor to do it instead and spare them. And for podcast research, I have a whole repo where I've put every single book and paper that's been relevant to prepping any of the recent episodes. I've been able to just throw everything in there, because the Cursor harness is extremely good at helping the model figure out exactly what to pull — whether from my repo or from the web — to answer the questions I have while I'm researching. So whatever you happen to be working on right now, just try pointing Cursor at it. Go to cursor.com/dwarkesh to get started.

</details>

### AI在数学与计算机操作上的差异

**Speaker A**: 显然，AI在数学领域的进展比其他所有领域都要快得多，人们指出该领域的“可验证性”是出现这种情况的关键原因。我认为这是两个重要原因之一，但人们确实忽略了另一个。我在实验室之外，所以我不知道实际发生了什么。这是一个完全天真的理论。一个关于AI为什么在数学上取得如此大进展的切题问题是：为什么它在计算机操作上一直这么慢？计算机是非常可验证的。我的Etsy包裹到了吗？我的活动预定好了吗？这些都是非常可验证的考察事项。计算机操作所缺乏的是“可刷性”（grindability）。因为网站有机器人检测器——而且运行并行演示（parallel rollouts）需要巨大的算力——所以很难在亚马逊上运行一千个同样的结账流程并行演示。你会被安迪·贾西（Andy Jassy）封杀的。

<details>
<summary>Original English</summary>

**Speaker A**: Obviously, AI in math is making much faster progress than everything else, and people point to the verifiability of the domain as the key reason this is happening. I think that's one of the two important reasons, but people really neglect the other one. I'm outside the labs, so I don't know what's actually going on. This is a totally naive theory. A tangential question to why AI is making so much progress in math: why has it been so slow at computer use? A computer is very verifiable. Is my Etsy package coming? Is my event booked? These are extremely verifiable things to survey. What computer use lacks is grindability. Because websites have bot detectors—and it takes a tremendous amount of compute to run parallel rollouts—it's very hard to run a thousand parallel rollouts of the same checkout flow on Amazon. You'll get shut down by Andy Jassy.

</details>

**Dwarkesh**: 还是他亲自来。他按下了“封杀Dwarkesh”按钮上的那个红色大叉。

<details>
<summary>Original English</summary>

**Dwarkesh**: Him personally. He presses the red X on Dwarkesh button.

</details>

**Speaker A**: 完全正确。你可以尝试去构建每一个网站的克隆版本，但这非常耗费人力，并且会拖慢你的速度。目前你需要做这么多的并行演示来用深度学习学习一项技能的原因是，我们还没有解决样本效率（sample efficiency）的问题。

<details>
<summary>Original English</summary>

**Speaker A**: Exactly. You could try to build clones of every single website, but that's very labor-intensive and slows you down. The reason you currently need to do so many parallel rollouts to learn a skill with deep learning is that we haven't solved sample efficiency.

</details>

**Dwarkesh**: 就像卡帕斯（Karpathy）说的，通过一根吸管来吸取监督信号？

<details>
<summary>Original English</summary>

**Dwarkesh**: Sucking supervision through a straw, as Karpathy says?

</details>

**Speaker A**: 完全正确。当然人们正在研究很多……

<details>
<summary>Original English</summary>

**Speaker A**: Exactly. Of course people are working on many

</details>

<!-- chunk 6/9 -->

### AI 训练的反馈分配难题与数学的特殊性

**Speaker A**: 虽然有各种不同的技术，但我们在训练 AI 时从根本上会面临一个巨大的制约。如果是写代码，你可以把某个阶段的进展容器化封装在一个代码库中，然后并行启动数百个容器，告诉它们：“试着实现这个功能”，整个过程是完全确定性的。正因为它是确定性的，你就能解决“反馈分配”（credit assignment）问题，因为你能确切知道，无论是什么导致了这次运行成功而另一次失败，它们之间的差异代码（diff）就是起作用的关键。但如果面对的情境起始点各不相同，这个反馈分配问题就会变得极难解决。现实世界中的绝大多数事物，都很难像这样进行容器化。编程和数学是这个法则的例外。但如果你试图弄清楚如何建立一家成功的新公司，或者如何在市场上交易一天并赚到钱，因为你必须与现实世界互动，而且情况每天都在变化，这就意味着你无法在模拟器中不断重放、刷经验和反复尝试。数学当然是个例外，我觉得这是推动该领域以及编程领域进展的一个重要因素。这不仅仅是因为可验证性，它还必须是“可刷经验的”（grindable）。人们指出 AI 进展神速的第三个原因，是他们非常关注 Lean 定理证明器和形式化。同样，我完全不知道各大实验室里在搞什么。但我感觉对于当前 AI 的进展水平来说，Lean 并没有那么重要。为什么 AI 能够证伪关于单位距离问题的猜想？他们公布了思维链（chain of thought），至少是重写后的思维链。里面根本没有用到 Lean。我认为，Lean 提供的这种确保每一步都正确的过程监督，似乎还不如拥有这种“可验证的、能反复刷经验的结果”来得重要。

<details>
<summary>Original English</summary>

**Speaker A**: different techniques, but fundamentally there's this big constraint in the way we train AIs. With code, you can containerize a given level of progress in a repository and then spin out hundreds of parallel containers and say, "Try to implement this feature," and it's totally deterministic. Because it's deterministic, you can solve the credit assignment problem because you know that whatever caused this rollout to succeed and this one to fail, the diff is the thing that worked. If you have situations that are starting off at different starting points, this credit assignment problem becomes much harder to solve. Most things in the real world are very hard to containerize in the same way. Coding and math are exceptions to this rule. But if you're trying to figure out how to build a new business that succeeds, or how to go trade in the markets for a day and make money, the fact that you have to interact with the real world and things change day after day means that you can't keep replaying and grinding and farming the simulator. Math, of course, is the exception, and I feel like this is an important driver of progress in this domain and also in coding. It's not just verifiability; it has to be grindable. The third reason people point out that AI is making fast progress is they focus a lot on Lean and formalization. Again, I have literally no idea what's going on in the labs. I feel like Lean just doesn't matter that much for the current level of progress in AI. Why is AI able to disprove the conjecture about the unit distance problem? They released the chain of thought, or at least a rewrite of the chain of thought. It didn't have any Lean in it. I think the process-based supervision that Lean provides, where you know each step is correct, seems less relevant than just having this grindable outcome that is verifiable.

</details>

### Lean 形式化在数学探索中的独特潜力

**Speaker B**: 关于“可刷经验性”更重要这一点，非常有意思。大家可能天真地以为，Lean 为数学提供了一些独一无二的东西，因为你能够借此看清它到底能不能证明。你有了这种能给你确切“是”或“否”答案的传统软件，并把它当做你的验证环境（VR）。早期的一些尝试就能佐证你的观点。我又得绕回到国际数学奥林匹克（IMO）的话题上。最初 DeepMind 基本就是那么做的。所有东西都在 Lean 里，但到了第二年，就全都变成自然语言了。所以就像你说的，它并不是必需的。不过，我确实认为这种形式化领域还有一个尚未被探索的好处，那就是目前你仍然需要人类来审查单位距离猜想的那个反例，说一句“看起来没问题”。这在某种程度上为事物的无尽探索设定了边界。如果你回想一下 AlphaGo 或 AlphaZero 风格的系统，它们是在自己的宇宙里自己跟自己下海量的围棋，不断自我探索，这可能会完全脱离任何人类需要关注的轨道，但它们依然有这种自动化的、可验证的奖励机制。这不仅仅意味着你可以基于它做强化学习（RL）。这还意味着你基本上永远不需要人工介入检查，你可以直接倾注大量算力，让它们去探索围棋的宇宙。接下来可能会变得有趣的是——也许这根本行不通，目前还不能断言它是否会有成果——借助 Lean，你可以想象拥有一个基本永不停歇的程序，它一直在试图扩展 Mathlib。Mathlib 是一个 GitHub 代码库，基本上包含了所有用代码写成的数学。它离“所有数学”还差得远，但他们的目标是把它变成全部的数学。它是用代码写成的，你可以在里面问：“这个证明正确吗？”编写这些证明是非常耗费人力的。围绕它有一个完整的子社区。但你可以想象有这样一个 AI，你对它说：“去尽力扩展 Mathlib 吧。”也许它是从原库分叉（fork）出来的，这样里面就不会有垃圾内容，因为人们对于想要保留在里面的东西有一定的品味。所以你有了一个纯粹由 AI 构建的 Mathlib 分叉库，它就这样一直运行下去，永不停止。它不需要任何人去检查。它可以一直运行。它可能会提出自己的猜想。可能会提出自己的理论和不同的定义。也许其中很多都是无用的，但它就是拥有这棵可以不断生长的无限知识树。这是数学所独有、而其他任何领域都不具备的特质：你可以按下启动键，直接倾注算力，然后放任它十年不管，回过头来再问：“你弄出了什么？”肯定会有东西出来的。接着问题就变成了：它有用吗？你如何去甄别？能够做这件事本身就非常有趣。如果它最终没有产生某种有趣的数学洞见，那才是非常令人惊讶的。

<details>
<summary>Original English</summary>

**Speaker B**: It's an interesting point about grindability mattering more. Naively you might think Lean provides something unique for math because you're able to see if it can prove it. You have old-school software that can tell you yes or no, and you use that as your VR. What would corroborate your point is the initial attempts. Again, I'll circle back to the IMO. Initially, DeepMind basically does that. Everything is in Lean, and then the next year it's all in natural language. So to your point, it's not needed. I do think there's a yet-to-be-explored benefit of that formalization domain, which is that at the moment you still need a human reviewing that counterexample to the unit distance conjecture to say, "Looks good." That provides a certain bound on how endlessly explorable things are. If you consider AlphaGo or AlphaZero-style systems, they're off in their own universe playing a bunch of Go and exploring themselves, potentially going off the rails of what any human needs to look at, but they still have this automated verifiable reward. It's not just that you can do RL on that. It's also that you basically never have to check in, and you can just pour compute at them exploring the universe of Go. What stands to be interesting—maybe this won't pan out, but the jury should still be out on whether it'll yield anything—is that with Lean, you could imagine having a basically endlessly running program that's constantly trying to extend Mathlib. Mathlib is this GitHub repository that's basically all of math written in code. It's very far from all of math, but they want it to be all of math. It’s written in code where you can ask, "Is this proof correct?" It's very labor-intensive to write these proofs. There's a whole subcommunity around it. But you could imagine having an AI where you say, "Simply try to extend Mathlib." Maybe it's a fork of it so that it doesn't have trash in it, because people have a certain taste for what they want to be in there. So you have your fork of the pure AI Mathlib, and it just goes and it doesn't stop. It doesn't need anybody to check in on it. It could just keep going. It might come up with its own conjectures. It might come up with its own theories and different definitions. Maybe many of them are useless, but it just has this infinite tree that it can grow out. That's a very unique thing that math has that nothing else has, where you could press go and just pour compute at it, look away for ten years, and then come back and say, "What do you have?" There's going to be something. Then there's a question: is it useful or not? How do you suss that out? That's just an interesting thing to be able to do. It would be very surprising if that didn't yield some sort of interesting mathematical insight from it.

</details>

**Speaker A**: 在这个故事里，Lean 的重要性体现在两个不同的方面。首先是你可以完全放手、甚至看都不看一眼，而进展依然会发生。用围棋你是可以做到的。但我认为用自然语言数学是做不到这一点的。

<details>
<summary>Original English</summary>

**Speaker A**: There are two different ways that Lean is important in this story. The first one is how you could let go, not even check in, and progress will be made. You can do that with Go. I don't think you can do that with natural language math.

</details>

### AI 自主研究的实验与局限

**Speaker B**: 这非常有意思。你看到 Karpathy 的自动研究想法了吗？他写了一个能进行基础 LLM 训练的 Python 文件，然后建了一个代码库，里面让 LLM 智能体尝试去修改这个文件，如果修改能加快运行速度，这个修改就会被保留下来。来给我们讲解 AlphaGo 原理的 Eric Jang，在试图构建一个超强围棋机器人时也做过类似的事情。他有一些有趣的观察。AI 真的很擅长运行实验并顺着那条路径走下去，但它很不擅长在死胡同前停下，也不擅长处理高度并行的事情。不管怎样，这在未来很可能会改变。去思考它的极限形态是什么样，是非常有趣的。

<details>
<summary>Original English</summary>

**Speaker B**: That's very interesting. Did you see Karpathy's auto research idea? He wrote this one Python file that does basic LLM training, and then had a repo where LLM agents would try to make modifications to the file, and if it sped up the speed run, the modification stays. Eric Jang, who came on to explain how AlphaGo works, did a similar thing when he was trying to build a very strong Go bot. He had interesting observations. It's really good at running an experiment and going down that path, but it's bad at stopping at dead ends and doing extremely parallel things. Anyway, this will probably change in the future. It's very interesting to think about what it looks like in the limit.

</details>

**Speaker A**: 这从根本上讲，也就是人类数学研究机构的运作方式。它就是一个向着有趣和有用方向扩展的图书馆。通过这种方式，你没有任何基于结果的监督。没有你想去激励的特定结果，但你拥有一个过程。你知道每一步都是对的，你只是不知道它是否正走向一个有趣的方向。如果你要这么做，你肯定不希望它彻底偏离正轨，在逻辑的空间里做完全随机的游走。你可能需要某个监督模型，来为它提供判定是否有用的启发式规则（heuristics）。你知道人们已经在研究这个了。这属于那种“五年后”的话题，我很好奇五年后的我们讨论起它会是什么样。也许这最终一无所获，但陶哲轩（Terry Tao）谈到过一个研究项目，试图穷举搜索所有可能的代数空间。你可以想象给代数系统应用不同的公理。当我们提出群论（group theory）时，有一套特定的公理系统，如果你不知道它的动机，看起来就像是随意的规则。但如果你把它们全试一遍会怎样？它们中会不会产生有用的东西？绝大多数可能都在某种程度上是垃圾。最终什么有趣的结果都得不出。但偶尔，也会出现这么一小块“孤岛”，这是一种完全不同的公理系统，但至少从它能推导出的定理数量来看，它是非常丰富的。这正是你所能想象到的自动化证明器的家常便饭：探索那片空间，看看其中哪个最终能搞出点名堂。也许其中一个“孤岛”最后真成了某种你可以事后为其赋予动机的东西，并说这就是它试图触达的结构类型。就像你看着群论的公理，一开始不知道这是关于对称性的，但事后你意识到，这跟研究对称性非常相关。你能想象得出这类结果，只不过它不是仅仅探索可能的代数系统，而是在探索任何一种公理的所有可能逻辑推论。

<details>
<summary>Original English</summary>

**Speaker A**: This is fundamentally what the human institution of mathematical research is. It's a library extended in interesting and useful ways. This way you don't have any outcome-based supervision. There's no outcome that you're trying to incentivize, but you have a process. You know the steps are correct, you just don't know if it's going in an interesting direction. If you were doing that, you don't want to completely go off the rails and do a random walk through the space of logic. You'd probably want some supervisor model that's trying to provide heuristics on whether it's useful or not. You know people are working on it. That's one of those "five years from now" things where I'd be curious to get the future version of us talking about it. Maybe that goes nowhere, but Terry Tao was talking about one research project that tries to exhaustively search the space of possible algebras. You could imagine different axioms that you apply to algebraic systems. When we come up with group theory, there's a certain axiom system that looks like arbitrary rules unless you know the motivation. What if you tried all of them? Do any of them yield useful things? The vast majority of them are just trash in some way. It all collapses to no interesting results. But every now and then, there would be this little island of a completely different type of axiom system that at the very least seems rich in terms of the number of theorems that can come out of it. That's bread and butter for what you would imagine automated provers being good for, exploring that space and seeing which one of them turns out to be something. Maybe one of those islands actually turns out to be something you can retroactively put motivation on, to say this is the kind of structure it's trying to get at. In the same way that you could imagine looking at the axioms for a group, not knowing that it's about symmetry, but you retroactively realize this is very relevant to studying symmetry. You could imagine results of that flavor, but instead of just exploring possible algebra systems, it's exploring all possible logical consequences of any kind of axiom.

</details>

### 自然语言证明与自动化验证的未来

**Speaker B**: 关于是否能在没有 Lean 的情况下提供基于过程的监督，DeepSeek 有他们的 DeepSeek Math 模型。他们发布了一篇关于如何训练它的论文，非常有意思。自然语言证明的问题在于，你不知道它对不对。他们有一个验证器，而这个验证器是由一个元验证器（meta-verifier）来训练的，以确保在他们训练这个模型去解决问题求解艺术中的所有问题时，验证器能给出好的反馈。这是行得通的。有趣的是，从目前发表的文献来看，采用某种元验证机制的自然语言验证似乎是有效的。在我们正在使用的公开发布的产品中，它似乎也行之有效。如果你看看编程智能体，它们在编写整洁代码和重构代码方面变得越来越好。我确信存在基于过程的“以大语言模型为裁判”（LLM-as-a-judge）的系统在提供品味，并评判：“这是一种干净的函数写法吗？有没有同类模块化形式的重复代码？”这在数学里应该也行得通，对吧？即使只在自然语言环境中工作，你可以信任一个验证器，这听起来在数学领域比在其他任何领域都更具有说服力。你我之前聊过为什么它们不擅长写作。它们似乎是很好的裁判。如果我给它们两篇学生写的文章，它们能分辨出哪一篇更准确、更有洞见。那么为什么你不能直接用一个验证器来判定：“这是一篇好文章吗？”也许根本上的失败在于，即使它们擅长区分 B 级文章和 A 级文章，它们实际上并不擅长区分 A 级文章和你真正想读的文章，比如那种你会在 Substack 上追更且有深度的文章。它们最后其实会偏好那些缺乏洞见的文章。在数学方面，仅仅判断一个证明是否正确这个步骤，就非常适合交由自动化验证器来完成，即便是自然语言形式的。你可能依然能取得大量进展。我还是喜欢 Lean 输出的逻辑树，只是因为你确实可以无拘无束地偏离常规轨道。它不受以往表述方式的任何约束。大家都在谈论 AlphaGo 的第 37 手棋。是什么促使它跳出了先验启发式规则？在这个探索过程中，切断与外部世界的联系似乎是有益的，可以作为对自然语言数学前沿探索的一种互补性的研究追求。Lean 的另一个相关性在于，假设你有了纯自然语言的 RL 环境和一套纯自然语言的证明。人们说，“继续吧，AI 数学家们”，然后它们每天生成十篇论文。如果这其中存在任何错误率…… Alex Kontorovich 谈到过这一点。对一个数学家来说，这会变得让人无法忍受。每次你看到其中一篇，你都不知道它是否值得你花时间。即便 100 篇里有 99 篇是对的，我也不知道它值不值得我看，因为要找出可能存在的那个错误，实在是太费人力了。把时间全花在一篇垃圾论文上是极其令人沮丧的。如果有一种东西能给你盖上“绿勾”认证，告诉你：“即使这理解起来会很复杂，即使这会让人很头疼，但你至少知道它是正确的”，其他任何领域都会为此疯狂的。数学就有这个。如果模型还能把它们的自然语言证明转化为形式化证明，那就太具颠覆性了。每个领域都会非常想要这样的东西。所以我认为你是对的，Lean 作为总体推动数学进展的虚拟现实（VR）环境的重要性或许被高估了。但我绝对不会将它从这个故事中抹去。

<details>
<summary>Original English</summary>

**Speaker B**: On the point about whether you can provide process-based supervision without Lean, DeepSeek had their DeepSeek Math model. They released a paper on how they trained it, and it was quite interesting. The problem with natural language proofs is you don't know if it's correct or not. They have a verifier, and the verifier is trained by a meta-verifier that makes sure that for all the problems they're training this model to solve in the art of problem-solving, the verifier is giving good feedback. It works. It's interesting that natural language verification with some sort of meta-verification seems to work so far in the published literature. It also seems to work in the published products that we're using. If you look at coding agents, they're getting better and better at writing clean code and refactoring code. I'm sure there are process-based "LLM-as-a-judge" systems providing taste and saying, "Is this a clean way to write this function? Are there duplicates of the same kind of modular forms?" That should also work for mathematics, right? It seems more plausible for math than anything else, even if you're only working in natural language, that you could trust a verifier. You and I were talking earlier about why they're bad at writing. They seem to be good judges. If I give them two essays that students wrote, they'd be able to say which one is more accurate and insightful. So why can't you just have a verifier saying, "Is this a good piece of writing or not?" Maybe the ultimate failure there is that even if they're good at discriminating between a B essay and an A essay, they're not actually good at discriminating between an A essay and a thing you actually want to read, something that would be followable on Substack and insightful. They actually end up preferring uninsightful pieces of writing. On the math front, the step to simply know if a proof is correct or not lends itself to an automated verifier, even in natural language. You could probably still make a ton of progress. I still like the tree of logic out of Lean, just in that you can really go off the rails. There's no constraint on the previous way things had been phrased before. Everyone talks about move 37 in AlphaGo. What is the thing that lends itself to going outside the prior heuristics? It seems productive to have a disconnection from the rest of the world in that exploration, as a complementary research pursuit to the natural language math front. The other relevance of Lean would be, let's say you have your pure natural language RL environments and a pure natural language set of proofs. People say, "Proceed, AI mathematicians," and they generate ten papers a day. If there's any error rate to that at all… Alex Kontorovich has talked about this. It becomes insufferable as a mathematician. Every single time you see one of these, you don't know if it's worth your time. Even if 99 out of 100 are right, I don’t know if it’s worth my time because it's really labor-intensive to find what that error would be. It's really frustrating to spend all your time on a paper that was trash. Having something that's able to give you that green checkmark that says, "Even if this is going to be complicated to understand, even if it’s going to be a pain, you at the very least know it is correct," every other field would kill for that. Math has that. If the models are also able to take their natural language proofs and formalize them, that seems huge. Every field would love to have something like that. So I think you're right that Lean is maybe overrated regarding its importance as a VR environment for progress in math generally. But I definitely wouldn't write it out of the story.

</details>

<!-- chunk 7/9 -->

### AI 写作与人类表达的本质差异

**Speaker A**: 我也很喜欢把 Mathlib 的这种扩展作为我们文明在不久的将来会发生什么的一个隐喻。几千年来，人类建立起了这个关于知识和理解的语料库，我们现在拥有的所有东西都被提取到了这些模型中。在某个时刻，这些模型将会任意地扩展它。顺便说一下，在写作方面，我有一个关于为什么写作比其他领域进展更糟的理论。一个原因就是你说的，它们不仅不擅长判断 A 和 B 的优劣，而且还会被 B* 完全带偏，B* 是一篇糟糕的文章，但它恰好触及了 A 应该触及的所有要点。这种奖励欺骗机制完全脱离了正轨。但另一个重要原因是，写作不像代码和数学那样具有模块化特性。你可以用很多不同的方式编写一个函数，它们做的是同样的事情。当然，你希望它干净整洁，但归根结底，只要能运行，它就是好用的。数学中的引理也是一样。你可以得到一个与生成它的方式不同的最终产品。代码是产生某种最终产品的东西，你想要的是一个功能正常的最终产品。而在写作中，最终产品直接就是 AI 正在生成的东西。每一段、每一句、每一个字都很重要，因为那就是实质内容。它不是从写作中产生出来的什么独立的东西。它不能像代码那样成为一堆垃圾，却仍然产生你想要的结果。但你刚才指出，我们在让智能体不仅编写功能性代码，还能编写整洁代码方面，已经做得好多了。为什么让你从仅仅是功能性的代码进步到干净且可合并的 PR 的那种进步，没有同样导致更清晰的写作呢？

<details>
<summary>Original English</summary>

**Speaker A**: I also love this extension of Mathlib as a metaphor for what's going to happen to our civilization pretty soon. For millennia, humanity has built this corpus of knowledge and understanding, and everything that we have is now distilled into these models. At some point, the models will just extend that arbitrarily. By the way, on the writing front, I have a theory of why writing is making worse progress than these other domains. One reason is what you said, that they're bad at judging not only A versus B, but they get totally derailed by B*, which is this shitty essay that hits all the bells and whistles that A is supposed to hit. The reward hacking thing just goes off the rails. But the other important thing is that writing is not modular in the same way that code and math are. You can write a function many different ways, and they do the same thing. Of course you want it to be clean, but at the end of the day, if it works, it works. Same with lemmas in mathematics. You can have some end product that's different from the way it's produced. Code is the thing that produces some end product, and you want a functional end product. Whereas in writing, the end product is directly the thing the AI is producing. Each paragraph, sentence, and word matters because that is the substance. It's not some separate thing produced out of the writing. It can't be slop in the way that code can be slop and still produce the outcome you want. But you were just pointing out how we've actually gotten much better at agents writing not just functional code, but clean code. Why is it not the case that the same progress that lets you go from merely functional to a clean and mergeable PR also results in clearer writing?

</details>

**Grant**: 这是一个很好的观点。另外，难道没有吗？我同意在很多方面它们都是糟糕的作家。但对于我消费的很多写作，我发现最好只是把它复制粘贴到 LLM 中，然后说：“给我解释一下这个。” 这个解释会比人类生成的那个东西更好。有趣的是，我们说它们是如此糟糕的作家，然而我揭示出来的偏好却是让 LLM 来解释它。即使当我在电话中与一位人类专家进行实时交谈时，如果这是只有他们才掌握的、没有被编码到分布中的知识，我会希望他们向我解释。但是，如果为了理解这一点，我需要理解一个更基础的概念，我更希望在社交上我能被允许说：“我们在这里暂停一下。我只想去问问 LLM 那是怎么运作的，然后我们可以再回到你特别的知识上。” 那是知识蒸馏，是解释。如果我把你的能力看作是一个散文作家——如果我给你一本书去读，我想要一份读书报告——我可能会认为 LLM 给我的读书报告更好。但当人们说它很糟糕时，他们真正想表达的是：什么是写作？它不仅仅是提取预先存在的想法。它也不仅仅关乎你如何清晰地解释，因为它们已经是很好的解释者了。它关乎的是洞见是什么。这就是为什么自回归是一种非常奇怪的生成事物的方式。当你在写作时，你多少知道，为了让它变得优秀，你必须拥有一些不可预测的元素。这不仅仅是提高你头脑中的“温度”。它在于准确地知道你想要做出一个不可预测的举动时的确切节点，而那将会是更有洞见的东西。即使它更擅长解释一个预先存在的事物，那么一开始是什么生成了那本你想要被提炼出来的书呢？那不是 LLM 生成并恰好被你需要的。那是某个作者，通过对世界上大量思想的探索，决定了哪些方面是有趣的，以及什么样的呈现方式能形成一个连贯且动机明确的叙事。他们以某种方式将这些都融合在了一起。如果他们是一位优秀的作者，你大概率会倾向于直接去读他们的书，而不是去读提炼版。那么，到底是什么让它一开始就值得去探索，并且想把它上传分享呢？人们在说 LLM 不擅长写作时，引用的正是这一面。正是这种不可预测的元素，这种故意选择某些新颖事物的做法，与通常生产事物的方式是非常直接矛盾的。

<details>
<summary>Original English</summary>

**Grant**: That's a good point. Also, has it not? I agree there are many ways in which they're terrible writers. But for a lot of writing I consume, I find it's better to just copy-paste it into an LLM and say, "Explain this to me." The explanation will be better than the thing produced by the human. It's funny that we say these are such terrible writers, and yet my revealed preference is to have an LLM explain it. Even when I'm talking to a human expert live on a call, if it's a piece of knowledge that only they have that's not encoded in the distribution, I want them to explain it to me. But if in order to understand that, I need to understand a more basic concept, I would prefer if it were socially acceptable for me to just say, "Let's pause here. I'm just going to ask an LLM how that works, and then we can come back to your special piece of knowledge." That's distillation, an explanation. If I'm thinking of your quality as an essay writer—if I give you a book to read and I want a book report—I might believe that the LLM gives me a better book report. But what people are really getting at when they say it’s bad is, what is writing? It's not just the distillation of preexisting ideas. It's not just how you explain clearly, because they are good explainers. It's about what the insight is. This is where autoregression is a very weird way to generate things. When you're writing, you sort of know that in order for it to be good, you have to have an element of the unpredictable. It's not just increasing the temperature in your mind. It's knowing exactly the correct point when you want to make an unpredictable move, and that that's going to be what's more insightful. Even if it's better at explaining a preexisting thing, what generated that book that you wanted distilled in the first place? It wasn't an LLM that generated it and you just needed it. It was some author who, through a lot of exploration of ideas in the world, decided what aspects were interesting and what ways of presenting it formed a coherent, well-motivated narrative. They put that all together in some way. If they're a good author, you would probably err on the side of reading their book instead of the distillation. Still, what makes it worthwhile to explore at all in the first place and want to upload it at all? It's that side of it that people cite when they say LLMs are bad at writing. It's that element of unpredictability, of deliberately choosing something novel that is very directly contradictory to the way things are typically produced.

</details>

### AI 的心智理论与移情能力

**Speaker A**: 这个观点很好。我认为它们在建立良好的人类心智模型方面也非常糟糕，而这是写作中一项非常重要的技能。Andy Matuschak 和另一位合作者（我现在忘了他的名字）做了一份有趣的报告，他们试图教 LLM 写出优秀的间隔重复提示。我非常喜欢这个研究，因为尽管这看起来像是一项完全随机的技能……就像，人们都在谈论一年后实现递归自我改进，而我们却无法让这些东西写出好的抽认卡。这到底是怎么回事？他们尝试了许多不同种类的技术，而且他们都是很厉害的人。他们尝试用强化学习来训练开源模型。他们尝试了各种各样的方法，包括思维链，以及给最好的闭源模型发送了一大段提示。在我看来，关键的限制在于，写出一张好卡片在于预测某人三个月后的思维状态。他们将如何关联这个问题？在那一刻他们会想出什么样的答案？这种诱导是否能激发你真正想从你试图制作卡片的段落中带走的那处细节？我认为写作与此类似。如果你在写东西，它之所以是一个如此耗费精力、需要花费那么长时间的过程，是因为对于每一个词或每一句话，你都必须思考：我的读者现在脑子里在想什么？即使我倒换措辞，把最后的短语放到开头，让这成为在你读完句子其余部分之前脑海中浮现的第一个画面……也许自回归不擅长做这个。这也许更像是一种类似扩散的特性，即考虑整体而不是逐句推进。但同时我认为那需要大量的心智化活动，而这些模型在这方面出奇地挣扎。

<details>
<summary>Original English</summary>

**Speaker A**: That's a good point. I think they're also really bad at building really good mental models of people, which is a very important skill in writing. Andy Matuschak and another collaborator, whose name I'm forgetting right now, did an interesting report where they tried to teach LLMs to write good spaced-repetition prompts. I really like this because even though it seems like a totally random skill… It's just like, people are talking about recursive self-improvement in a year, and we can't get these things to write good flashcards. What's going on there? They tried many different kinds of techniques, and they're sophisticated people. They tried to RL open source models. They tried all kinds of things, including chain of thought and a big prompt they sent to the best closed source model. The key constraint, it seemed to me, was that writing a good card is about projecting somebody's mind in three months. What is the way in which they'll associate the question? What kind of answer will they be thinking at that moment? Is the elicitation that inspires the detail you actually want to take away from the passage you're trying to make cards about? I think writing is similar to this. If you're writing something, the reason it's such an enervating process that takes so long is that with each word or each sentence, you have to be thinking: what is happening in my reader's mind right now? Even if I flip the phrasing around so the end phrase goes to the beginning and this is the first image that comes to your mind before you read the rest of the sentence… Maybe autoregression is bad at that. This is maybe a more diffusion-like property of considering the whole rather than going sentence by sentence. But also I think that requires a lot of mentalizing, which these models weirdly struggle at.

</details>

**Grant**: 这是一个有趣的问题。它们在这方面挣扎很奇怪吗？我可能会说错这个。你知道你是如何引用你曾经读过的研究，而也许那个研究并不是真的？有一个非常令人难忘的研究。假设你想测试人们的情商（EQ）。你展示一张某人面部表情的抽认卡，然后让某人试着描述那种情绪。网上有一些非常好的测试，有一张脸，然后有四种可能的情绪。准确地描述出正确的情绪惊人地困难，但你也会觉得确实存在一个标准答案。如果你和生活中的人尝试这个，你会注意到那些社交参与度很高的人在这方面做得非常好，而那些更偏左脑思维的人则不然。这就是你可以做的一种测试。我依稀记得有一个关于这方面的实验，他们找来了刚刚注射过肉毒杆菌的人，做了一次前测和一次后测。后测结果显示，他们在解读别人表情方面的能力差了很多。这感觉很奇怪。

<details>
<summary>Original English</summary>

**Grant**: It's an interesting question. Is it weird that they struggle at that? I might butcher this. You know how you cite studies that you once read and maybe the study wasn't real? There's one very memorable one. Let's say you want to quiz people's EQ. You show a flashcard of someone's facial expression and someone is trying to describe that emotion. There are really good tests online that have a face and then four possible emotions. It's surprisingly hard to describe exactly the correct emotion, but you also get the sense there really is a correct answer. If you try this with people in your life, you'll notice that the ones who are pretty plugged in socially do really well on it, and the ones who are a little bit more left-brain don't. That is a kind of test you can do. I vaguely remember an experiment to this effect where they took people who had freshly gotten Botox, and they did a pretest and a post-test. Post-test, they were just much worse at reading people's expressions. That feels weird.

</details>

**Speaker A**: 等等，他们注射了肉毒杆菌？做测试的人？

<details>
<summary>Original English</summary>

**Speaker A**: Wait, they got Botox? The person taking the test.

</details>

**Grant**: 你做完测试，然后你去注射肉毒杆菌，你的脸就僵硬了，然后你在理解你所看到的情绪方面就变得更差了。有想法认为，理解你所看到的情绪的一部分过程是你自己也在做同样的表情。在面部层面，你在移动你的面部肌肉。你看到那个表情，你模仿它，然后你在某种非常潜意识的层面上会觉得，“哦，是的，那是焦虑。” 所以从这个意义上说，如果模型确实有糟糕的心智理论，当然，它们知道一切，因为它们读过所有人写的东西。但是在能够像我的面部肌肉模仿你的面部肌肉那样——这是帮助我理解你感受的原因——真正设身处地为你着想的层面上，这就一点也不奇怪了。它们没有面部肌肉。它们大脑的工作方式完全不同。这就像一个外星人试图产生共情。它怎么可能拥有心智理论呢？如果要拥有，那将是非常涌现的东西。而我们只需要把它接入我们自己的心智中。我们已经有了现成的硬件，可以直接把它放进去。从那个视角来看，这就不那么令人惊讶了。

<details>
<summary>Original English</summary>

**Grant**: You do the test, and then you go and get Botox and your face is all frozen, and now you're worse at understanding the emotions of what you see. The thought is that part of understanding the emotion you're looking at is doing it yourself. At a facial level, you're moving your face muscles. You see that, you mimic that, and you're like, "Oh yeah, that's anxiety," at some very subconscious level. So in that sense, if it is the case that models have bad theory of mind, sure, they know everything because they've read what everyone wrote. But at the level of actually being able to put themselves in your shoes in the same way that my face muscles are mimicking your face muscles—that's what helps me understand how you feel—it's not surprising at all. They don't have face muscles. Their brain works completely differently. It's like an alien trying to empathize. How could it have theory of mind? It would be this very emergent thing to have. Whereas we can just plug it into our own minds. We've got the ready-made hardware to just place it in. From that lens, it's not that surprising.

</details>

### Jane Street 的独特文化

**Speaker A**: 好了，Grant，我们都是 Jane Street 的合作伙伴。我相信这些年来你接触过很多 Jane Street 的员工——你发现他们或者他们的文化有什么独特之处吗？今年我给他们做了一次采访，那一部分很有趣，因为他们通常没有任何对外公开的东西。我的意思是，在业内，他们以拥有相当惊人的留任率而闻名——人们就是会留在那里——能够内部一窥究竟很有意思。我记得在他们的一条评论中有人说：即使人们有职位头衔——研究员，或者交易员，或者工程师——他们通常也不知道同事的实际职位是什么，因为每个人都在做一点别人的事情。比如，即使你官方身份是一名交易员，你也在做大量的研究；即使你官方身份是一名研究员，你也在写大量的代码。我怀疑这也是他们之所以有如此不可思议的留任率的部分原因。因为任何想成长的人都有机会去做很多不同种类的事情。好了，Grant，这次我来为你打个广告。如果你想看 Grant 在那里和一些人做的完整的坐下访谈，请去 3b1b.co/janestreet。好了，Grant——让我们多聊聊人工智能和数学吧。关于使用 LLM 来学习，你有什么建议吗？

<details>
<summary>Original English</summary>

**Speaker A**: Okay, Grant, we're both partners with Jane Street. I'm sure over the years you've interacted with a lot of Jane Streeters — what have you found that's unique about them, or their culture? I did this interview with them this year, that was partially interesting because they don't usually have anything outward-facing. I mean in the industry they're known for having a pretty wild retention rate — people just stay there — getting an inside view of that. I remember in one of their comments someone saying: even though the people have role titles — researcher, or trader, or engineer — they often don't know what their colleagues' actual role is, because everyone's doing a little bit of everything else. Like even if you're officially a trader, you're doing a lot of research; even if you're officially a researcher, you're doing a lot of coding. And I suspect that's part of why they have the insane retention they do. Because anyone who wants to grow just has the chance to do a lot of different kinds of things. All right, Grant, I'll do the plug for you this time. If you want to watch the full sit-down interview Grant did with some of the folks there, go to 3b1b.co/janestreet. All right, Grant — let's talk more about AI and math. What advice do you have about using LLMs to learn?

</details>

**Grant**: 正如我所描述的，对于很多众所周知的概念，我发现它们非常有帮助。但通常只要再往下发几条信息，我想去理解一些东西时，它们自己就非常困惑，以至于把我也弄糊涂了。它们没有用正确的方式来解释它。我知道，如果和一个合适的人类交谈，三分钟就能消除我的困惑。我们会越来越多地想要使用这些东西来学习。人们经常谈论教育和表征之类的东西。你有没有注意到如何更高效地使用它们来理解概念的方法？我很想听听你对此的看法。

<details>
<summary>Original English</summary>

**Grant**: As I was describing, for a lot of well-known concepts, I find them very helpful. But often, just a couple of messages further down, I'm trying to understand something, and they're so confused themselves that they're confusing me. They don't explain it the right way. I know that talking to the right human could clear up my confusion in three minutes. More and more, we're going to want to use these things to learn. People talk a lot about education and representation stuff. Have you noticed ways to use them more productively to understand concepts? I'm curious to hear your take on this.

</details>

**Speaker A**: 我来说说我的看法。即使在 LLM 出现之前，我觉得学习中一个相关的洞见就是认识到“向谁学”比“学什么”更重要。我对任何大学生的建议是，当他们在选择上什么课时：少关心一点你预先存在的兴趣，因为它们现在在某种程度上是任意的；多关心一点教这门课的人是不是一位优秀的教育者，以及是不是能和你产生共鸣的人。在选择读什么书时，作者是谁也许比它是否符合你之前的兴趣更重要。如果你之前喜欢过某本书，那就去读那位作者写的其他书，而不是去读那个主题的另一本书。关于这一点，我要说到 LLM 了。试图从维基百科页面学习某样东西，与如果这是一个哲学话题你去查阅《斯坦福哲学百科全书》，感觉是有区别的。或者如果这是一个数学话题，你去查阅《普林斯顿数学指南》。这里的区别在于，这些文章是由一个个体刻意撰写的，他试图围绕它真正去打造一种动机。而在维基百科上，它达到的是一个局部最优，即每一句话都必须是正确的。在一篇好的论述中，你会对过程中的正确性少关心一点。你可以刻意去打造那些...

<details>
<summary>Original English</summary>

**Speaker A**: I'll give mine. Even pre-LLM, I feel like a relevant insight in learning was recognizing who matters more than what. My advice to any college student when they're choosing what courses to take: care a little bit less about your preexisting interests, because they're kind of arbitrary right now, and care a little bit more about whether the person teaching it is a good educator and someone you resonate with. In choosing what books to read, who the author is maybe matters more than whether it's a prior interest. If there's a book you've liked before, read what else that author has written rather than reading another thing on that subject. I'm getting to LLMs on this. There's a difference in feel for trying to learn something from a Wikipedia page versus, if it's a philosophy topic, going to the Stanford Encyclopedia of Philosophy. Or if it's a math topic, you go to the Princeton Companion to Mathematics. The difference there is the articles are deliberately written by one individual who tries to actually craft a motivation around it. Whereas on Wikipedia, it's this local minimum that's reached where every sentence has to be correct. In a good exposition, you care a little bit less about correctness on the way. You can deliberately craft things that are a

</details>

<!-- chunk 8/9 -->

### LLM 作为学习工具与解释者

**Speaker A**：……你在过程中纠正的一点小错误，在众包环境中往往会被编辑掉。目前的 LLM 解释给我的感觉很像维基百科，也就是说，非常惊人。想象一下在维基百科出现之前的世界，要花多长时间才能找到并弄清楚所有事情。不过，维基百科页面中最有用的部分是什么？通常只是底部的参考文献。你可以看看那些关键的参考文献，然后去找出来阅读。有时这能让你获得更好的全局认知。所以我经常喜欢直接问 LLM：“我该去读谁的著作？”也许我甚至可以提供一些我想要的具体学习方式。有一次我想学半导体之类的东西，结果被它忽悠了。我觉得这是一个非常直观、需要视觉呈现的话题，但所有的资源都是纯文本的。我就问：“有没有视觉效果很好的视频来解释你提到的这些概念？”Claude 说：“有的，这里有几个。”排名第一的推荐大概是这样写的：“这是 3Blue1Brown 的一个视频”。我当时就想：“我敢保证绝对没有。”那确实是一个真实的视频，链接也是真实的，但它只是把别人的视频错误地归因给我了。不过这其实挺好的。我点开去看了那个视频并从中学习，体验要好得多，而不是试着在那边继续追问下去。从这个意义上说，我基本上就是把它当成一个超级加强版的 Google 来用，以便精准锁定那些人类撰写的、正确的学习资源。你呢？你经常使用这些工具，你觉得最好的使用方式是什么？

<details>
<summary>Original English</summary>

**Speaker A**: little bit wrong that you correct along the way,  

which gets edited out in a 

crowdsourced environment. 

LLM explanations feel to me at the moment a 

lot like Wikipedia, which is to say, amazing. 

Imagine a world before Wikipedia, how long 

it would take to find and suss everything. 

But nevertheless, what's the most 

useful part of a Wikipedia page? 

It's often just the references at the bottom.

You look at the key references,  

and you go to them, and you read them.

Sometimes that gives a much better overview. 

So often I like to just ask 

an LLM, "Who should I read?" 

Maybe I can even give some 

specifics on ways I want to learn. 

I actually got gaslit by this once when I was 

trying to learn about semiconductors or something. 

I felt it was a very visual topic, 

but all the resources were text. 

I asked, "Is there a well-visualized video 

explaining the concepts you're getting at?" 

And Claude said, "Yeah, here's a couple," and the 

top one was like, "Here’s one from 3Blue1Brown". 

I’m like, "I can guarantee that there’s not."

It was an actual video, an actual link,  

but it had just misattributed someone else's.

It was good. I had a much better experience  

clicking over and watching it to learn rather than 

trying to proceed forward with questions there. 

In that sense, I'm basically using it 

like a very souped-up version of Google  

to zero in on the right human-written resource.

What about you? You engage with these a lot. 

What's the best way to use them?

</details>

**Speaker B**：我觉得你说到点子上了。我最高效的学习经历，往往是利用人类制作的某种成果——无论是一篇文章、一本书还是一个视频——它能以正确的方式组织相关的概念。它会为你建立动机，解释为什么下一个观点与解决你即将遇到的下一个问题相关，然后引出下一个观点，再下一个观点。然后，你只需使用 LLM 在这本书所确定的知识分支上做一点修剪和补充。实际上我当时正在读——我记得这好像还是你推荐的——斯蒂文·斯特罗加茨 (Steven Strogatz) 的教科书，关于……

<details>
<summary>Original English</summary>

**Speaker B**: I think you put your finger on it. 

The most productive learning sessions 

I've had are when there's some artifact  

that a human has produced—whether it's an 

article, a book, or a video—that organizes  

the relevant concepts in the correct way.

It builds up the motivation for why the next  

idea would be relevant to solving 

the next problem you'd encounter,  

and the next idea, and the next idea.

Then you use the LLMs to just do a  

little bit of pruning around this 

branch that the book has identified. 

I was actually going through—I think you might 

have recommended it—Steven Strogatz's textbook on… 

</details>

**Speaker A**：是关于混沌的那本吗？《非线性动力学与混沌》(Nonlinear Dynamics and Chaos)？我很喜欢那本书。

<details>
<summary>Original English</summary>

**Speaker A**: The chaos one? Nonlinear Dynamics 

and Chaos? I love that book. 

</details>

**Speaker B**：对，我当时就在读它，那种感觉真是太美妙了。那本书简直就像是把你做的视频变成了文字形式。非常有趣。我学习它的方式是，屏幕的三分之一放他大学里的授课视频，另外三分之一放教科书上的对应部分，最后三分之一放一个 LLM。我当时其实在想，如果我回到大学，坐在现场听这堂课，我肯定会完全听不懂。现在的这些孩子一定非常聪明，因为我在看视频时，需要不断暂停，阅读教科书，和 LLM 对话，然后再继续播放。但多亏了他精心策划的、理解概念的正确顺序，以及用来激发理解的合适问题……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I was going through it, and it was bliss.

It was like your videos in book form. 

It was super fun. The way I was learning it, 

I'd have his university lecture on one-third  

of the screen, that part of the textbook on 

another third, and an LLM on the last third. 

I was actually thinking, if I were back 

in college and watching this lecture live,  

it would totally go over my head.

These kids must be really smart,  

because I'm pausing, reading the textbook, 

talking to LLMs, and then restarting again. 

But with him curating the right order 

to understand concepts and the right  

problems to motivate understanding them…

</details>

**Speaker A**：这是 LLM 极其不擅长的另一点。一个真正优秀的人类能够做到的是，当你提出一个问题时，人类可以告诉你：“实际上，你思考这个话题的方式并不正确。你想问的问题，以及组织这些概念的正确方式，应该是 X。”而 LLM 根本做不到这点。它有点太顺从了。这本质上就是那种阿谀奉承的行为，它总是说，“噢，多深刻的一个问题啊。”你会希望剥离掉这种东西。

<details>
<summary>Original English</summary>

**Speaker A**: Another thing LLMs are really bad at. 

Something a really good human can do, 

when you ask a question, a human can say,  

"Actually, you're not really thinking 

about this topic the correct way. 

The question you want to be asking, the 

correct way to organize these concepts, is X." 

An LLM just can't really do that.

It's a little too placating. 

This is ultimately that sycophantic behavior where 

it's very, "Oh, what an insightful question." 

You want to strip that down.

</details>

**Speaker B**：这个观点很好，我觉得这稍微涉及到心智理论（theory of mind），即认识到学生提出某种问题，其实反映出他们的思维结构与讲解者的并不一样。有时人们在这方面做得过头了。面对一个真正优秀的老师，比方说你在一个初中的数学课堂上。如果一个学生提出的问题表明他正以一种完全不同的方式在思考，其实在那一刻很难认真对待这个思路，去问他“等一下，你能顺着这个思路得出正确答案吗？”，然后再说“别用那种方法，我们来用这种方法”。真正优秀的老师能够巧妙地利用（jujitsu）学生那种富有创造力的思考方式，并将其引入正题。但 LLM 没有这样做。它们不会重塑你的问题，而是顺着你的错误思路跑偏了。至少让人感觉这里有三个层次。LLM 在第一层，好的解释者在第二层，而 A+ 级别的解释者是那种能够巧妙引导你的思维方式并告诉你“那种思路在什么地方很有用”的人。也许到了五年后，会有一个完整的循环，那时 LLM 也将能够做到这一点，并且会以一种更好的方式来做。

对于那些经常发邮件问你这个问题的学生，你会给他们什么建议：“我对研究数学很感兴趣，也对这门学科充满了热情，但看到 AI 取得的所有这些进展，我不知道把它作为我的职业是否还有意义。”这不仅对数学领域的人有现实意义，对任何注意到自己的领域正从 AI 中获得生产力提升的人来说都相关。编程领域和这非常相似。你对这些人有什么建议？

<details>
<summary>Original English</summary>

**Speaker B**: That's a good point, and I think  

it cuts to theory of mind a little bit, 

recognizing that asking a certain kind  

of question reveals that the student's mental 

structures are not the same as the explainer's. 

Sometimes people do this to a fault.

With a really good teacher, let's say  

you have a middle school math classroom.

If a student asks a question that suggests  

they're thinking about it in a different way, 

it's actually really hard to take that seriously  

in the moment and ask, "Hang on, could you get 

to a right answer with that?" before you say,  

"Instead of that, let's do this."

The really good teachers are able  

to jujitsu the creative way the student 

was thinking about it and bring it in. 

LLMs aren't doing that. They 

aren't reframing your question. 

Instead, they kind of run off.

At the very least, it feels  

like there are three levels here.

An LLM is at one, a good explainer  

is at another, but the A+ explainer 

is the one who can jujitsu your way of  

thinking and say, "That's where that's useful."

Maybe there is a cycle all the way around where,  

five years from now, the LLMs will 

be doing that, but in a better way. 

What is your recommendation to students who 

I'm sure email you this question all the time:  

"I was curious about doing mathematics.

I'm really passionate about the subject,  

but seeing all the progress AIs are 

making, I don't know if it makes  

sense for me to pursue this as a career."

This is relevant not only to people in  

mathematics, but to anyone noticing that their 

field is getting productivity gains from AI. 

Coding is very adjacent to this.

What advice do you have for people? 

</details>

### AI 时代的数学职业与价值

**Speaker A**：我不会相信我自己给出的任何建议。这是我给出建议前要作的保留声明。但即使在 AI 出现之前，对于你要从事的任何工作，真正理解……如果我们讨论的是一份工作，而不是作为一个绅士科学家纯粹沉浸在数学世界中或类似的情况，你都应该明白钱是从哪里来的，你实际在创造什么价值，以及这两者之间的联系。让人惊讶的是，很少有人在这方面投入思考，尤其是学生。他们所处的环境往往是，他们可能想从事数学是因为他们一直很擅长这门课。他们在生活中总是因为正确地跳过下一个障碍而获得奖励。当他们认为自己想成为一名数学家时，是因为他们觉得这是继续参与其中的一种方式。他们想的是，“人们在哪里可以做这件事？”而不是去思考，“我正在为他人创造什么价值？这在多大程度上是薪水流向我的原因？”

不同情况下的答案其实大相径庭。在某些情况下，因为这是一位非常有声望的数学家，他们在大学的存在带来了一定的品牌价值，这也是大学想要招揽他们的原因。在某些情况下，获得国家科学基金会（NSF）的拨款，是因为我们对基础科学抱有“它是公共利益”的信念。我们围绕这一点建立了一个机构，以及一个庞大的官僚体系，作为我们所认为的公共利益的代理人，还有一整套繁文缛节，为的是让他们准确地预测你的研究进展将符合那笔资金的初衷。有时它就纯粹是教学。人们喜欢把孩子送到有专家任教的机构。你作为专家提供了品牌价值，作为老师提供了直接价值。无论 AI 是否能证明定理，无论我们讨论的是 2016 年还是 2026 年，这都是那些想着“我想成为一名数学家”的学生们思考得不够的地方。我认为这是值得深思的。

就我而言，我最初并没有刻意去想这些，我误打误撞地走上了一条职业道路，在这里，对数学的探索可以被商业化为一种娱乐形式。我是偶然踏入这个领域的，对此我非常感激，但这是个意外。这并非深思熟虑的结果。如果我能进行批判性的思考，我本来可以避免依赖运气，而是更有规划地去实现它。

回到你的问题——如果我们拥有了几乎自动化的定理证明系统，而且假设它们还是非常优秀的解释者，所以你甚至能从中获得人类层次的理解——我认为数学家所扮演的社会角色，其很大一部分实际上并没有太大改变。作为公众，我们仍然认为基础科学是有价值的，我们相信数学家的判断，由他们来决定把时间花在哪里是最好的。声望来自于这个社区内部。更多是由其他成员来评判一个成果是否出色，而不是由写拨款申请的人去真正搞懂代数数论，从而明白这是一个好成果。社区内部会有一种关于“什么构成了有价值的贡献”的内部文化。也许它会从证明定理转向写出好的定义。也许就是那种博物馆策展人的理念。但只要整个社会仍然珍视基础科学的前提，你就会拥有同样的社区。而且如果我们进入了 AI 带来的物质丰饶世界，从某种意义上说，流向这个方向的资金可能还会更多。

就讲师为机构带来的声望而言，我其实认为教学是后 AGI 时代（post-AGI）最稳定的工作之一，因为它极其依赖人际关系。这是父母在拥有充足财富时最想花钱的地方：优质的教学和优质的教育。它远远超出了简单的解释知识。即使 LLM 是很好的解释者，老师所做的工作更多是一种社交性的、教练式的、导师式的行为，这大概是未来五十年内最稳定的职业之一了。鉴于许多数学家的角色与此有重叠，作为有意进入这个领域的准学生，你可以向这个方向倾斜。实际上我认为，更多的学生应该思考并认可仅仅作为一名数学教育工作者，以及这能为下一代服务所带来的价值。

我要再次重申一下，我认为我并不是那个有资格说“听着，未来的年轻数学家，你应该这样看待未来”的人，因为我是一个 YouTuber。我不在他们打算进入的那些机构里，所以我只是作为一个局外人提出看法。但这感觉像是一个普遍适用的好建议：知道钱从哪里来，知道你在其中扮演什么角色。如果你已经在问自己这些问题了，实际上你就已经领先于所有其他初出茅庐、满怀抱负的准数学家了。

<details>
<summary>Original English</summary>

**Speaker A**: I wouldn't trust any advice that I give.

That's how I'd couch it. 

But even pre-AI, it feels very important for 

any job you're going to go into to really  

understand… If we're talking about a job—not being 

a gentleman-scientist engaging with the math world  

or something—you should understand where the money 

is coming from, what value you're actually adding,  

and the connection between those two.

A surprisingly small amount of thought  

is put towards that, especially by students.

They're in this environment where they probably  

want to go into math because 

they've always been good at it. 

They've been rewarded in life for 

proceeding through the next hoop correctly. 

When they think they want to be a 

mathematician, it's because they think it's  

a way to continue engaging with that.

They think, "Where do people get to  

do this?" rather than thinking, "What value am I 

adding to other people, and to what extent is that  

the reason a salary is flowing in my direction?"

It's actually quite different in different cases. 

In some cases, it's a very prestigious 

mathematician, and their presence at a  

university lends a certain brand value, 

which is why the university wants them. 

In some cases, an NSF grant is 

given because of the public good  

belief we have around basic science.

You've got an institution around that,  

and a whole bureaucracy acting as a proxy 

for what we think that public good is,  

with a whole song and dance around how to 

make them correctly predict that your progress  

will be in the spirit of that funding.

Sometimes it's just straight-up teaching. 

People like to send their kids to an 

institute that has experts teaching them. 

You provide brand value by being an expert, 

and direct value by being a teacher. 

Regardless of whether AIs are proving theorems or 

not, or whether we're talking about 2016 or 2026,  

that is something not enough students thinking 

"I want to be a mathematician" consider. 

I think it's worth thinking about.

For me, I wasn't necessarily thinking about it,  

and I stumbled into a career path where math 

exploration can be monetized as entertainment. 

I stumbled into that and I'm very 

grateful I did, but it was an accident. 

It wasn't deliberate. I could have avoided relying 

on serendipity and done it a little bit more by  

design had I been thinking critically about it.

To your question—if we have almost-automated  

theorem proving, and let's say they're 

also really good explainers so you even  

get the human understanding—I think a lot 

of the social role that mathematicians  

serve actually doesn't change that much.

As a public, we still feel there's value  

to basic science, and we trust 

the judgment of mathematicians  

to determine where their time is best spent.

The prestige comes from within that community. 

It's other members saying that a result 

is really good, more than the grant  

writer really understanding algebraic number 

theory to understand it was a good result. 

There's going to be an inner culture of 

what constitutes valuable contributions. 

Maybe it shifts away from theorem proving 

and towards good definition writing. 

Maybe it's that museum curator idea.

But you're going to have that same  

community as long as society as a whole is 

still valuing the premise of basic science. 

And if we're in the abundance world 

that AI brings, there's probably more  

funding in that direction in some sense.

On the side of prestige to institutions  

for who their lecturers are, I actually think 

teaching is one of the most stable post-AGI  

jobs that there is, because it's so relational.

This is where parents want to spend their money  

if they have an abundance of wealth: 

on good teaching and good educating. 

It goes so far beyond explanations.

Even if LLMs are good explainers,  

the thing that a teacher is doing is such 

a social, coaching, mentor-type thing that  

that's probably one of the most stable careers 

that's going to exist over the next fifty years. 

Insofar as a lot of mathematicians' roles 

overlap with that, as the prospective student  

going into it, you could lean into that.

I actually think a lot more students should  

think about and give credence to the idea of 

being just a math educator and the value that  

can serve towards the next generation.

I'll couch again that I don't think I'm  

the one to say, "Here, prospective young 

mathematician, here's how you should think  

about the future," because I'm a YouTuber.

I'm not in the institution that they're  

thinking of going into, so I'm 

speaking as an outsider looking in. 

But it feels like generally good, universal 

advice: know where the money is coming from,  

know where you plug into that.

And if you're just asking those questions,  

you're actually already steps ahead of all the 

other fledgling prospective mathematicians. 

</details>

**Speaker B**：事实上，想一想这个疯狂的世界吧：在五年或十年内，AI 不仅能想出千禧年大奖难题（Millennium Prize problems）的解决方案，而且一开始就能提出需要解决的全新问题，开辟全新的数学领域和研究对象等等。在那个世界里，首先，物质资源将极其充裕。其次，AI 心智走得最远、在超越我们视野的地方看得最深远的领域，将会是数学。人们将会产生巨大的需求，纷纷询问：“AI 看到了什么？你们能向我们解释一下吗？”在那个世界里，如果还有任何工作存在的话，那么提炼 AI 所学到的知识肯定会是其中之一。而且，这也很滑稽，因为所有这些都预设了那一切是没有实用价值的。我们还没有谈论正在进行的数学研究的实际应用呢。如果它有任何经济效用的话，你可以想象，那些理解它并能决定将其指向何方的人，实际上拥有了多得多的经济价值，因为他们能够作为策展人做出判断，引导这头新数学的巨兽朝着有用的方向前进。突然之间，这成了一个比以前杠杆率高得多的举措。

我能问你一下这个问题吗？显然，对于把 AI 用于数学研究，大家不仅会问它能不能做，还会问它做得好不好？或者它有什么用？你之前描述过，在群论中，我们曾经试图找出关于不同类型函数根的各种随机事实，而现在这些发现都有了跨越多个不同领域的实际应用。你觉得，如果我们完全达到这样一个阶段，人类数学领域的进展被加速了 10 倍或 100 倍，一些极其疯狂的事情随之发生，或者，我们只是会被其他领域卡脖子，成为瓶颈？

<details>
<summary>Original English</summary>

**Speaker B**: In fact, think about the crazy world 

where, within five or ten years,  

the AIs are coming up with not only solutions 

to the Millennium Prize problems, but totally  

novel problems to be solving in the first place, 

novel mathematical fields and objects and stuff. 

It is in that world where, first 

of all, there's a ton of abundance. 

Two, the thing AI minds will have gone furthest 

in, where they will have seen furthest beyond  

our horizons, will be mathematics.

There will be so much demand for,  

"What have the AIs seen? 

Can you explain it to us?" 

In that world, if there are any jobs 

whatsoever, surely distilling what the  

AIs have learned will be one of them.

Also, it's funny because all of  

this presumes that it's useless.

We're not talking about the actual  

practical applications of what math is being done.

Insofar as there's any economic utility to it,  

you would imagine that the people who 

understand it and are able to make the  

decision of where it should point actually have 

a lot more economic value by being able to make  

that judgment as a curator and point this 

behemoth of new math in a useful direction. 

Suddenly, that's a much more levered 

move to make than it had been previously. 

Can I ask you about that?

Obviously, one question for AI for math  

is not only can it do it, but is it any good?

Or is it good for anything? 

You were describing all the ways 

in which, with group theory,  

we're trying to figure out random facts about 

the roots of different kinds of functions,  

and now there are all these different applications 

that are practical across many different fields. 

Do you have some sense of whether, if we 

just totally get to a place where the field  

of human mathematics is accelerated 10X or 

100X and some crazy shit happens, or are  

we just going to be bottlenecked by other fields?

</details>

**Speaker A**：我认为肯定有一些领域大概会成为瓶颈的。

<details>
<summary>Original English</summary>

**Speaker A**: I think there are some fields that probably will. 

</details>

<!-- chunk 9/9 -->

### 数学突破与物理世界的应用

**Speaker A**: 这（指技术进步）是非常不均衡的。随着代数数论的进展，感觉这不太可能立刻解锁什么东西。但我记得和一位做更多动力学和偏微分方程（PDE）求解之类工作的数学家聊过。他提到他的团队有一些想法。让我看看我总结得对不对。这就好像波音公司制造飞机的方式，他们先制造出来，进行一系列测试，然后必须根据这些测试拆解并重新组装它。他的团队基本上对如何在模拟中做更多事情有一些见解，这样你就不必拆解并重建它了。这给波音公司节省了数十亿美元之类的，然后他们就开始资助那个团队了。这显然更贴近应用，因为偏微分方程就是这样。可以想象，那个领域的进展确实会解锁一些东西。我不知道这是否是那些阶跃式的变化，但也许更多的是在引擎设计变得稍微流畅一些，或者找到正确的机翼形状，而不是运行一大堆复杂的计算流体力学（CFD）。也许你能够加速你的 CFD 模拟，因为某些纯数学的见解让它们变得更高效。我敢打赌你会在那里看到很多很棒的渐进式改进。大规模的数学突破似乎不太可能立即转化为这种巨大的经济突破，就像你解决了纳维-斯托克斯问题，然后解锁了模拟更多事物的能力一样。但你可能确实会在那些边缘地带，看到纯数学的见解有意义地外溢到其他事物中。有大量的人在从事人工智能工程、物理工程和材料科学等工作。你完全可以想象，他们将处于一个有利的位置，来审视人工智能数学方面的见解，并决定它们是否在某种程度上相关。这也是另一件我不会坐在这里信誓旦旦地预测肯定会发生的事情。但如果在接下来的五年里，没有出现可以直接归功于人工智能在数学上的进步、具有经济价值的改进，那将会有一些令人失望，也会有一些令人惊讶。如果它只是解决了一堆埃尔德什问题，而其中没有一个做的是真正直接接触物理世界的数学，那就会令人失望。这就回到了你关于数学的大部分历史是如何建立起这些概念和联系的堆叠的观点。有时这些堆叠相互连接，或者你在其他地方发现了应用。至少，你只是建立起了这个巨大的堆叠。然后，随着社会在奇点期间发生更广泛的进步，当我们进入奇点的工业阶段时，你就会拥有所有这些有望在世界其他地方发挥作用的不同想法。正如我所说，正在发生的事情中一个有趣的地方是，它促使人们退后一步问：“什么是数学？”也许其中一个尴尬的结论将揭示它已经变得完全无用了。提出的那种问题已经变得与物理上适用的事物如此脱节，这是数学家们必须接受的一件事。每个人都会看着说，“等一下，你们不是应该……如果在那里有 10 倍的进步，为什么我们在这里没有看到它？”然后数学家们会说，“呃。”每次我们写那些资助申请书说，“相信我们，椭圆曲线的进展将有助于密码学”，它却让人们看到也许并非如此。所以这是一种可能性。Grant，这超级有趣。非常感谢你来参加。

<details>
<summary>Original English</summary>

**Speaker A**: It's super spiky. With progress in algebraic number theory, it feels unlikely that that then unlocks something. But I remember talking to this mathematician who does more dynamics and PDE-solving type stuff. He was referencing that his group had some ideas. Let me see if I summarize this right. It’s like the way Boeing would make planes is that they'd make it, do a bunch of tests, and they had to disassemble it and reassemble it based on those tests. His group essentially had some insights on how to do more in simulation such that you don't have to deconstruct and rebuild it. It saved Boeing billions of dollars or something, and then they just started funding that group. That's much more obviously application-adjacent, because PDEs just are that. Progress in that domain, you would imagine actually does unlock some things. I don't know if it's these step changes, but maybe it's more on the side of engine design becoming a little bit more fluid, or coming up with the right wing shape instead of running a whole bunch of complicated CFD. Maybe you're able to speed up your CFD simulations because certain pure math insights make those more efficient. I bet you'd just see a lot of great incremental improvement there. It seems less likely that the massive breakthroughs in math immediately turn into this massive economic breakthrough, like you solve the Navier-Stokes problems, and then that unlocks an ability to simulate more things. But you probably will see, at those fringes, some meaningful leakage out of the pure math insights into other things. There's a ton of people working on things like AI engineering, physical engineering, and material science. You have to imagine they'd be in a good position to look at the AI math insights and decide whether they're relevant in some way or not. It's another one of these things where I'm not going to sit here and put a flag in the sand predicting that there will be. But it'd be a little bit disappointing and a little bit surprising if there weren't, over the next five years, economically valuable improvements made that were directly referable to the AI progress in math. It would just be disappointing if it was just taking down a bunch of Erdős problems and none of them were doing any of the math that actually directly touches the physical world. To your point about how a lot of the history of mathematics was about building up these piles of concepts and connections. Sometimes the piles connect with each other, or you discover an application somewhere else. At the very least, you just build up this huge pile. Then as broader progress in society happens during the singularity, when we get to the industrial part of the singularity, you just have all these different ideas that hopefully are useful in other parts of the world. As I said, one of the interesting things about what's happening is it causes people to step back and ask, "What is math?" Maybe one of the awkward conclusions will be revealing that it's just become wholly useless. The kind of questions being asked have become so divorced from things that are physically applicable that that's one of the things mathematicians have to come to terms with. Everyone will look and say, "Hang on a second, weren't you guys supposed to… If there's 10X progress there, why aren't we seeing it over here?" And then mathematicians are like, "Ugh." Every time we wrote those grant proposals and said, "Trust us, the elliptic curve progress is going to help with cryptography," it shines a light on the fact that maybe it doesn't. So that's one possibility. Grant, this was super fun. Thanks so much for doing it.

</details>

**Grant**: 绝对的。这是我的荣幸。

<details>
<summary>Original English</summary>

**Grant**: Absolutely. My pleasure.

</details>