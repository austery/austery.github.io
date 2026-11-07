---
author: New York Times Podcasts
date: '2026-04-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=KJyQNwVj-_4
speaker: New York Times Podcasts
tags:
  - ai-augmented-programming
  - prompt-engineering
  - software-abstraction
  - technological-unemployment
  - knowledge-decay
title: AI 正在接管代码：程序员转型‘架构师’的真实观察
summary: 《纽约时报》记者 Clive Thompson 通过对 75 名软件工程师的深度调研，揭示了 AI 如何彻底改变编程范式。程序员正从“建筑工人”转向“建筑师”，通过苏格拉底式对话甚至情绪化指令引导 AI 生产代码。尽管生产力迎来爆发式增长，但行业仍面临“去技能化”、初级岗位缩减及长期代码维护等深层隐忧。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - Microsoft
  - Amazon
products_models:
  - GitHub Copilot
media_books: []
status: evergreen
---
### 深入硅谷一线的调研

**Natalie Kitroof**: 我是 Natalie Kitroof，欢迎收听《每日新闻》（The Daily）。在过去的几年里，全世界的人都在询问 **AI** 将如何改变他们的生活或影响他们的工作。答案从彻底的救赎到绝对的毁灭不等。而处于这一切最前沿的是**软件开发人员**，他们使用人工智能的频率如此之高，以至于 AI 已经接管了他们的许多日常任务。今天，我与《纽约时报杂志》撰稿人 **Clive Thompson** 交谈，讨论他最近对科技行业的调查，以了解当人们邀请 AI 来完成他们的工作时，情况会是什么样子。今天是 4 月 14 日，星期二。Clive Thompson，传奇科技记者，一位我仰慕已久的人。欢迎来到《每日新闻》。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: For the New York Times, I'm Natalie Kitroof. This is the Daily. For the past few years, people all over the world have been asking how AI will change their lives or affect their work. And the answers range from total salvation to absolute doom. At the front lines of all of this are software developers who are using artificial intelligence so much that it's already taking over many of their day-to-day tasks. Today I talked to Times magazine writer Clive Thompson about his recent survey of the tech industry to find out what it looks like when people invite AI to do their jobs. It's Tuesday, April 14th. Clive Thompson, legendary tech reporter, a person whose work I have admired for a very long time. Welcome to the Daily.

</details>

**Clive Thompson**: 很高兴来到这里。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah, it's good to be here.

</details>

**Natalie Kitroof**: 你来到这里是因为你广泛报道了 AI 在多大程度上影响着那些真正作为硅谷支柱的员工——**程序员**。他们编写的代码驱动着我们使用的每一款软件。这是一个你非常熟悉的群体，尤其是因为你写过一本关于他们的书。最近几个月，你花了很多时间与他们交谈。那么你发现了什么？请带我们了解一下你的报道过程，包括它涉及了什么以及揭示了什么。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: So you are here because you've been covering extensively the question of how much AI is affecting the workers who are really the backbone of Silicon Valley—programmers, the people who write the code that powers every piece of software we use. This is a group of people you know well not least of all because you wrote a book about them. You spent a lot of time talking to them in recent months. So what did you find? Walk us through that reporting, what it entailed, and what it unearthed.

</details>

**Clive Thompson**: 当然。我关注 AI 作为一种编写代码的工具已经有几年了，但去年它的发展开始大幅加速。我真的很想弄清楚，在软件开发的日常阵地中到底发生了什么。于是我出发了，与全国各地约 **75 名不同的软件开发人员**进行了交谈。是的，75 个。

<details>
<summary>Original English</summary>

**Clive Thompson**: Sure. Well, I'd been following the arrival or the advent of AI as a tool that can write code for a couple years now, but it started to accelerate a lot last year. And I really just wanted to find out, you know, what was going on in the everyday trenches of software development. So, I just hit the road and I talked to about 75 different software developers all around the country. Yeah. 75.

</details>

**Natalie Kitroof**: 哇，那可真不少。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Yeah, that's a lot.

</details>

**Clive Thompson**: 的确很多。我可能做得有点过头了，但我真的很想全面了解情况。因为不同的软件开发人员有非常不同类型的工作，对吧？所以，我想和在田纳西州为地区银行做咨询的人交谈，也想和在硅谷只有两个人的时髦初创公司、试图创造新事物的人交谈。还有那些在 **Google**、**Amazon** 和 **Microsoft** 等软件巨头工作的人，那里有数万名开发人员，必须维护那些已经存在了 20 年的**代码库**。

<details>
<summary>Original English</summary>

**Clive Thompson**: That's a lot of them. Yeah, I might have overdone it, but I really wanted to know what was going on kind of across the board because different software developers have very different types of jobs, right? So, I wanted to talk to people who were doing consulting work for regional banks in Tennessee, people who were doing buzzy little startups, just the two of them in Silicon Valley trying to like make something new. And then, you know, the people that are working at the big software giants like Google and Amazon and Microsoft where you've got, you know, tens of thousands of developers having to take care of these code bases that have been around for 20 years, right?

</details>

### 从物理接线到 AI 抽象层

**Natalie Kitroof**: 那他们告诉你了什么？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: And what do they tell you?

</details>

**Clive Thompson**: 非常有趣。我发现很多程序员编写的代码量大大减少了。有些人甚至根本**不再编写代码**。他们让 AI 替他们写。

<details>
<summary>Original English</summary>

**Clive Thompson**: Well, it was really interesting because what I found was that a lot of the coders, they're writing a lot less code. Some of them are writing no code at all. They are having the AI write it for them.

</details>

**Natalie Kitroof**: 哇。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Wow.

</details>

**Clive Thompson**: 这种转变发生得非常快。我会说它在过去六个月里开始大规模爆发，在过去三个月里加速，因为这些 AI 编码工具变得越来越好，并开始赢得许多程序员的信任，包括那些以前可能有点怀疑的人。与一两年前的情况相比，这是一个非常剧烈的变化。

<details>
<summary>Original English</summary>

**Clive Thompson**: And this transition has happened really quickly. I would say it began heavily in the last six months. It accelerated in the last three months as these AI coding tools have just gotten a lot better and they have started to gain the trust of a lot of programmers, including ones that might have been a little skeptical before. And it's a really stark change from what things looked like even a year or two ago.

</details>

**Natalie Kitroof**: 所以你是说程序员不再编程了，是这样吗？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: So you're saying coders aren't coding. Is that right?

</details>

**Clive Thompson**: 并非所有人。这有一个程度的差别。但在我交谈过的人中，大多数人都将大量的日常编程工作外包给了 AI。确实有些程序员编写的代码极少，甚至为零。这是一种**沧桑巨变**。

<details>
<summary>Original English</summary>

**Clive Thompson**: Well, not all of them. It's a gradation. But of the people that I spoke to, a majority of them were outsourcing a lot of their day-to-day programming to AI. There are definitely coders who are writing very little to zero code. It's a sea change. It's a big sea change.

</details>

**Natalie Kitroof**: 他们对此感觉如何？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: And how do they feel about that?

</details>

**Clive Thompson**: 当我最初开始这项研究时，我曾在想是否有些人会感到不安或不快。因为我通过几十年来与软件开发人员的交谈了解到，他们经常从编写代码行中获得巨大的乐趣。这就像解决一堆小谜题，完成后会感到非常愉悦。所以我认为这可能会让人感到泄气或沮丧。但实际上，我交谈过的绝大多数人都对 AI 赋予他们的新能力感到兴奋不已。他们只需要用平实的语言说出：“这就是我想创建的东西”，然后 5 到 10 分钟后，就能看到生成的、可运行的代码。他们都说，他们一直热爱的是“建造东西”。身为开发人员的乐趣在于，你把一个想法，通过汗水和劳动，把这些神奇的词变成一台能为你做事的机器。这感觉就像魔法，就像托尔金小说里的东西。

<details>
<summary>Original English</summary>

**Clive Thompson**: When I first started the research, I kind of wondered whether some of them were going to be uneasy or unhappy about it, right? because I had known from decades of talking to software developers that they often derived enormous pleasure from writing lines of code. It was like solving a bunch of little puzzles and it was just delightful when they did it. And so I thought maybe this was going to be deflating or demoralizing, you know, but in reality, the great majority of everyone I spoke to was really kind of jazzed and excited about the new powers that the AI was giving them to be able to just say in plain language, here's what I want created, and then 5 10 minutes later have the working code back and they're looking at it. What they all said was that they've always loved building things. That's the fun of being a developer is you take an idea you have and through sweat and work you turn these magic words into a machine that does things for you. And that that feels like magic, right? That feels like something from Tolken.

</details>

**Natalie Kitroof**: 确实如此。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Totally.

</details>

**Clive Thompson**: 尽管他们自己编写的代码越来越少，或者干脆不写，但他们仍然觉得自己像个**巫师**，思考着需要制造什么，然后使用这些工具让它迅速问世。有些人说，他们感觉“成功的循环”更快了，因为 AI 的动作比他们自己要快。所以这很有趣，很多人真的非常兴奋、非常有干劲。

<details>
<summary>Original English</summary>

**Clive Thompson**: And they still feel that even though they're not writing as much or any of the code themselves, they still feel like they're a sorcerer who's thinking about what needs to be made and then using these tools to bring it into being really quickly. Some of them said they feel that loop of success more quickly because the AI moves faster than they would have done. So it it was interesting. A lot of them were really really pumped, really really stoked.

</details>

### 编程范式的巨变：从工人到架构师

**Natalie Kitroof**: 好的，我想谈谈这种兴奋感，以及这种魔法，它碰巧也是该行业的巨大变革。但首先，我想了解这种转变到底有多大。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Okay, I want to talk about that. I want to ask you about this excitement about this magic that also happens to be this massive disruption in their industry. But first, I want to just understand how big this shift actually is.

</details>

**Clive Thompson**: 是的。如果你想了解这种变化有多大，你必须了解一些**软件开发的历史**。这个领域大约只有 50 或 60 年的历史。它本质上是一个新领域。自从我们发明了计算机，我们就在摸索与它们交流的方法。我们一直在让这些交流方式变得更容易、更接近人类语言。而现在 AI 所带来的，可能是迄今为止发生的最大变化。

在 20 世纪 40 年代，你有了第一台计算机，美国的 **ENIAC**。当时的程序员（一个女性团队）编程的方式是物理上重新连接整台机器的线路。她们在机器周围爬行，有时甚至爬进机器内部，重新布线以创建一个新的逻辑系统来解决问题。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah. If you want to understand just how big this change is, you sort of have to understand a bit of the history of software development. So, it's been around for maybe 50 or 60 years. It's essentially kind of a new field. Ever since we invented computers, we've been figuring out ways to talk to them. And we've been making those ways to talk to them get a little easier and a little closer to human language. So, what's happening now with AI is probably the biggest change it's undergone yet. So you the 1940s you have the first computer, the ENIAC computer here in the US. And the way that they programmed it, the programmers was a team of women and they had to literally rewire the entire machine to do something different. So they're crawling around, sometimes crawling inside the machine and rewiring it to create a new logical system to solve a problem. Right.

</details>

**Natalie Kitroof**: 令人惊叹。劳动密集型编码。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Amazing. Laborintensive coding.

</details>

**Clive Thompson**: 非常劳动密集。当然，当计算机开始进入工业界时，要求人们爬进内部为每一个新问题重新布线是不切实际的。

<details>
<summary>Original English</summary>

**Clive Thompson**: Very labor intensive. Yeah. And of course when computers started to go into industry, it was impractical to require people to crawl around inside them and rewire them for every single new problem.

</details>

**Natalie Kitroof**: 当然。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Sure.

</details>

**Clive Thompson**: 所以他们开始制造计算机语言，你可以输入这些命令，它们会被翻译成本质上像数字布线一样的指令。但老实说，早期的语言非常难，我研究过它们，也和编写过它们的人交谈过。因为在那个年代，要求计算机做某件事的每一个细微步骤，你都必须非常明确。比如，把这个数字存入这里的内存，把另一个数字存入那里的内存。现在，你要把它们加在一起，然后把和放在这里。

<details>
<summary>Original English</summary>

**Clive Thompson**: So they started making computer languages that you could type these commands and they would get translated into the instructions that are essentially like you know digital wiring. But honestly, the early languages, I mean, I've poked around in them and I've talked to people that had to write them, and they were really hard because back in those days, every single little thing in the process of asking a computer to do something, you had to be very specific. Like, put this number in your memory here, and then put this other number in your memory here. Now, you're going to add them together and put the sum in here.

</details>

**Natalie Kitroof**: 听起来简直是场噩梦。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: And so, sounds like a nightmare.

</details>

**Clive Thompson**: 老实说，就像是在抛接 900 个球，只为了让它完成最基本的数学运算。随着时间的推移，程序员们说：“让我们自动化一些劳动吧。让我们让它变得更容易。”他们有一个有趣的说法，叫作“增加一层 **抽象（Abstraction）**”。所以，那些在 60 和 70 年代拖慢你速度的所有繁琐步骤都消失了。现在我可以更快地编写代码，它更容易编写，更像人类语言。每当他们意识到想要加速编写代码的步伐时，他们就会增加另一层抽象。所以，事情每十年都会变得容易一点。

<details>
<summary>Original English</summary>

**Clive Thompson**: Honestly, it it was like juggling 900 balls just to get it do the most basic piece of math. And then over the years, coders said, "Let's automate some of that labor. Let's make that easier." And they they have a funny phrase for it. They call it adding a layer of abstraction. So all these little finickity steps that slowed you down a lot in the ' 60s and '7s. Those are kind of gone. Like I can write code much more quickly. It's much easier to write. It's kind of more like human language, right? Every time they realized that they wanted to accelerate the pace at which they wrote code, they would add another layer of abstraction. So things just kept on getting a little easier every decade.

</details>

### 与 AI 的“苏格拉底式对话”

**Natalie Kitroof**: 听起来你描述的是一个过程，从实际的人类做艰苦的体力活来实现编码，到随着时间的推移变得更加复杂。但听起来仍然挺乏味的，你仍然得自己写很多东西，处理你的问题等等。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: It sounds like what you're describing is a process where you move from actual human beings doing real grunt work to make coding happen. People putting wires into different slots and computers to something much more sophisticated over time. But it's still sounding quite tedious. like you still have to write much of this and deal with your problems etc.

</details>

**Clive Thompson**: 是的，绝对是。我的意思是，编码以前真的是一种磨练。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah, absolutely. I mean coding was really a grind.

</details>

**Natalie Kitroof**: 那么现在呢？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Okay. So what about now?

</details>

**Clive Thompson**: 现在发生的是，人们正在使用 **AI 代理（Agents）** 为他们编写代码。它们通常已经变得足够值得信赖，以至于我交谈过的许多程序员都在使用它们来自动化大量的代码编写工作。在 AI 编码中，他们会拥有代理团队。比如你会问主代理：嘿，帮我写这个功能，我们来制定一个计划。AI 会说：这是我们的计划。当我发出“执行”指令时，它会衍生出其他子代理来完成任务的不同部分。你会有一个写代码的，另一个负责查看代码并进行测试。如果出现错误（而第一次几乎总会有错误），另一个代理会查看这些错误消息并说：“哦，好吧，让我们更改代码并再次测试”，然后在这个小循环中不断进行，就像一小队代理在集群中协作。

直到那一刻——当它们觉得：“好的，测试通过了。没有产生任何错误。”它们才会回到人类面前说：“好了，这是代码。这是我们编写的测试。这是结果。你可以看到我们的工作过程。”这真的很有趣。除了计算机程序员，现在很少有人能有这样的体验。

<details>
<summary>Original English</summary>

**Clive Thompson**: Well, what's happening now is that people are using AI agents to write the code for them. So they've generally gotten sufficiently trustworthy that a lot of the programmers I was speaking to were just using to automate a lot of their writing of lines of code. So with AI coding, they will have teams of agents like you will ask the main agent, hey, write this feature for me. Let's work out a plan. The AI will say, here's our plan. And when I say go, it will spawn other sub agents to do different parts of the task, right? You'll have one that's writing code and another one that is looking at that code and testing it. And if there are errors, and you know, there's almost always errors the first time, another agent will look at those error messages and go, "Oh, okay. Let's change the code and test it again and keep on going in this little loop, like a little team of agents all working in a swarm." And only at the point in time where they're like, "Okay, it's passing its test. It's not producing any errors." Then it'll go back to the human and say, "Okay, here's the code. Here's the test we wrote. Here's the results. You can see our work." And that's really interesting. There's really very few people having experiences like that other than computer programmers right now.

</details>

**Natalie Kitroof**: 所以你描述的情况听起来像是我们在编码领域看到的发展过程中的一个巨大飞跃。在实践中，它如何改变程序员的工作？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: So what you're describing sounds like an enormous leap from the progress that we've seen over the course of time in coding. How is it changing things practically for coders?

</details>

**Clive Thompson**: 它让很多事情变得更快了。许多软件开发人员告诉我，它只是极大地加速了他们的工作节奏。为了让你感受一下它有多快：如果你是一家只有两人的小型初创公司（我也访问过其中一些），他们会告诉我，他们的移动速度比两年前试图建立那家公司时快了多达 **20 倍**。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah. Well, it's making it a lot quicker to do a lot of things, right? A lot of software developers will tell me that it's just dramatically accelerating the pace at which they work. And to give you a sense of just how fast it can be, if you're like a small startup, these twoerson shops, and I visited some of them, they would tell me that they were moving up to 20 times faster than they would have if they were trying to build that company two years ago, right?

</details>

**Natalie Kitroof**: 哇，那太疯狂了。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Whoa, that's crazy.

</details>

**Clive Thompson**: 有些人对我说，客户对一个新功能的要求，以前可能需要一整天，现在可能半小时就能完成。20 分钟写完它，10 分钟看一遍确保没问题。当然，我应该说这适用于较小的公司，你在编写全新的代码，不用担心破坏已经存在的东西。当你去那些真正大型、成熟的公司时，他们也在使用 AI，但他们的“新陈代谢”要慢得多。他们更加谨慎。当我去 Google 时，他们说，在一家小型初创公司，100% 的代码行可能都是由 AI 编写的；在 **Google**，这个比例大约是 40% 或 50%。这使他们的整体新陈代谢只加快了大约 10%。尽管 Google 的开发人员告诉我：嘿，对于我们这种规模的公司来说，10% 已经是一个巨大的胜利了。

<details>
<summary>Original English</summary>

**Clive Thompson**: As if some of them said to me, you know, a request from a customer for a new feature that might have taken like a full day could be done in maybe half an hour. 20 minutes to write it, 10 minutes just to look it over it and make sure it's good. Right now, I should say that this is true of a smaller company where you're kind of writing entirely new code and you don't have to worry about breaking something that already exists. So, when you go to the really big mature companies, they're using AI, but their metabolism is a lot slower. they're being a more cautious and so when I went to Google they were saying like at a small startup you know 100% of the lines of code are written by AI at Google it's more like maybe 40 or 50%. And it has sped up their overall metabolism by really only like 10%. Although as the developers at Google told me like hey 10% for a company our size that's a huge win.

</details>

### 情绪化提示词：为何对 AI 吼叫有效？

**Natalie Kitroof**: 所以 AI 让他们编码更快，在某些情况下为他们完成了大量工作，但听起来他们仍然保住了工作。那么对于那些不再编写代码的程序员来说，他们的工作现在实际上是什么样子的？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: So the AI is making them faster at coding in some cases doing a lot of that work for them, but it sounds like they still have their jobs. So for the coders who are aren't doing coding anymore, what do their jobs actually look like now?

</details>

**Clive Thompson**: 某种程度上，他们的工作是思考软件“应该”做什么。这本来就是他们的工作，对吧？他们总是必须思考软件的形式，然后缓慢、辛苦地实现它。因为他们不必在缓慢、辛苦的过程中花费那么多时间，所以他们可以花更多时间进行实验性的迭代。我交谈过的许多开发人员会说，现在我和 AI 交流，由它来编码，我们会运行大约 10 种不同的可能性，然后我挑选绝对最好的一方案。他们说，这感觉就像 **Steve Jobs**，你会对下属说：给我拿九个 iPod 的设计方案，我会逐一过目并挑选最好的。好几个人字面上都用了乔布斯这个类比。所以，他们变得不再像建筑工人，而更像**建筑师**。但在更深层次上，他们真正做的事情只是“交谈”。

<details>
<summary>Original English</summary>

**Clive Thompson**: Well, their job in a way is to think about what the software ought to be doing. Now, that was always their job, right? you know they always had to think about the shape of the software and then slowly painstakingly make it happen because they don't have to spend so much time on the slow painstaking they can spend more time experimentally iterating right like I talked to a lot of developers who would say now that I'm talking to the AI and it's doing the coding we'll run through like 10 different possibilities and I'll pick the absolute best one they said it feels like being Steve Jobs where you'd go to their minions bring me nine designs of the iPod and I will handle them each and pick the best one. Right? Several of them literally said the Steve Jobs comparison. So they're kind of becoming less like construction workers and more like architects. But on a deeper level, what they're really doing is just talking.

</details>

**Natalie Kitroof**: 他们正在与 AI 进行大量的对话。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: They're having a lot of conversations with AI.

</details>

**Clive Thompson**: 是的。他们正在与 AI 对话，并且必须表达得非常清晰。AI 的特点是：如果你不够清晰，它就会跑去干错事。那么他们发现一整天都在沟通的过程如何？他们擅长吗？他们必须培养这项技能吗？

<details>
<summary>Original English</summary>

**Clive Thompson**: Yes. With AI. They're having conversations with AI and having to be very clear. The thing about AI is like it will go off and do the wrong thing if you're not incredibly clear. And how did they find the process of communicating all day long? Are they good at it? Do they have to develop that skill?

</details>

**Clive Thompson**: 绝对如此。有些程序员告诉我，他们惊讶地发现自己变得更擅长沟通了，比如更擅长用英语沟通。他们写的邮件更好了。事实上，为了对 AI 沟通而必须变得更擅长沟通，这让他们对整个世界的沟通能力也提高了。这个机器人可能让他们变得更擅长沟通，甚至可能更有利于处理人际关系。

<details>
<summary>Original English</summary>

**Clive Thompson**: Definitely. I had some of them say that they were surprised to find that they were becoming better communicators, like better communicators in English, right? Like they're writing emails better. The the fact that they've had they've had to become better communicators to the AI has made them better communicators to the world in general. the bot has made them better at communicating at having human relationships potentially.

</details>

**Natalie Kitroof**: 嗯，我不知道“人际关系”是否合适。虽然……

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Well, I don't I don't know if human relationships would be the way. Although,

</details>

**Clive Thompson**: 确实有点言过其实了。明白了。

<details>
<summary>Original English</summary>

**Clive Thompson**: that's a bridge too far. Got it.

</details>

**Clive Thompson**: 不过，有一位程序员 **Manu Eert**，他是一家小型初创公司 Hyperspell 的软件开发人员。他开玩笑似地说：“我想知道我们是否终于在教所有的书呆子学会**同理心**了，因为他们必须这样做。”

<details>
<summary>Original English</summary>

**Clive Thompson**: Well, although although there is one coder, Manu Eert, he he's a software developer with a small new startup, a company called Hyperspell. He sort of said, you know, kind of jokingly, but he said it like, "I wonder if we're finally teaching all the nerds empathy because they, you know, they're having to do that."

</details>

**Natalie Kitroof**: 我懂的。书呆子也有同理心。我就是个书呆子，我有同理心。他的观点我认为是正确的，即这份工作以前不需要那么多沟通，而现在需要了。跟我谈谈 Manu 的工作是如何变化的。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: I know. I know. Nerds have empathy. I'm a nerd. I have empathy. His point was, you know, I think correct that the job didn't used to require quite so much communication and now it does. Talk to me about how Manu's work is changing.

</details>

**Clive Thompson**: 他很有意思。Manu 当开发人员很久了，曾在大型公司工作过，也创过业。当他刚开始使用 AI 时，他其实并不确定。他担心它会产生**幻觉**，会产生过于臃肿或低效的代码。他说，几个月过去，他的担忧开始烟消云散。当他看到它能可靠地做事时，他变得更有信心了。

Manu 采用了一种我听到好几个开发人员都认同的有趣技术：当他们想要编写一个新功能、新函数或改进代码的某些方面时，他们基本上会与代理进入一种类似**苏格拉底式对话**的交流。他们会说：“好了，向我提问，关于这个软件功能应该如何工作。”代理就会说：“好的，这个功能要做什么？应该用这种方式吗？是用这种语言编写还是那种语言？”通过让 AI “采访”程序员，它引导他们思考软件真正应该做什么。然后，让 AI 代理去执行任务就变得顺理成章了。

问题是——我不想把它拟人化——但它有时会“不听话”。Manu 会告诉我，有些时候 AI 跑去干活，回来后说：“哦，好吧，我没做那些测试。我觉得它们没那么重要。”他就会想：“等等，那些测试非常重要。”所以，他必须想办法训斥它，或者以某种方式哄劝或惩罚它。

<details>
<summary>Original English</summary>

**Clive Thompson**: He is interesting. So, Manu um has been a developer for a long time and he's worked at very large companies. He's done his own startups. And when he first started using AI, he wasn't really sure about it. He he was worried that it was going to hallucinate things that it would produce code that would be too flabby or inefficient. And what he said is that over the months his concerns began to boil away. He got more confident when he could see that it could do things reliably. So, Manu does something that I actually heard several developers have settled on as an interesting technique, which is when they want to write a new feature or write a new function or improve some aspect of code, they will essentially get into a conversation like a Socratic dialogue with their agent. They'll say, "Okay, ask me questions about how this software feature should work." And the agent's like, "Okay, what is this going to do? Should it do it this way? Is it going to be written in this language or in this language? By having it interview the coder, as it were, it it got them to think about what the software should really be doing. And then it was off to the races with having the AI agent do things. The problem is that uh I don't mean to anthropomorphize it, but it can sort of misbehave. Manu would tell me there are times when the air would go off and come back and say, "Oh, well, I didn't do those tests. I didn't think they were that important." And he's like, "Wait a minute. Those tests are completely important." You know, and so they would he would have to figure out ways to sort of reprimand it or ways to cajul or punish it in some way.

</details>

**Natalie Kitroof**: 你怎么惩罚 AI？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: How do you punish AI?

</details>

**Clive Thompson**: 基本上就是吼它。Manu 做的就是编写这些非常严厉的指令列表，就像“摩西十诫”一样。他会有这个文件，然后说：每次你做任何事情，先看这个文件，而且你必须始终遵守这些诫命。非常严厉的命令，比如你必须以这种或那种方式测试代码；你必须做这些事；绝对不能做那件事。软件开发人员会给我展示这些诫命，它们都是**大写字母**，就像在对它大声吼叫一样。他们会一遍又一遍地重复同样的话，就像试图通过纯粹的重复来催眠 AI 代理一样。或者他们会说：如果你不做这些测试，我就会被解雇。他们会使用这种非常……

<details>
<summary>Original English</summary>

**Clive Thompson**: Well, you yell at it. Basically what Manny would do is he would write these very stern list of instructions like a a ten commandments and he would have this file and he would say every time you do anything you look at this file first and you always follow these commandments very stern commands like you must test the code in this way or that you must do these things. You must not do that. and software developers, they would show me these commandments and they would be in uppercase like like they're yelling at it and they would repeat things over and over again like they were trying to hypnotize the AI agent by sheer repetition or they would say things like if you don't do these tests I will be fired. They would have this very

</details>

**Natalie Kitroof**: 哇，真是把筹码拉满了，非常情绪化的语言。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: wow really raising the stakes em very emotional language.

</details>

**Clive Thompson**: Manu Eert 的一个提示词会说：未能完成这些测试是不可接受的，且令人羞愧（Embarrassing）。

<details>
<summary>Original English</summary>

**Clive Thompson**: One of Manu Eert's prompts would say that failure to do these tests is unacceptable and embarrassing.

</details>

**Natalie Kitroof**: 令人羞愧。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Embarrassing.

</details>

**Clive Thompson**: 令人羞愧。我问他：“这有用吗？”

<details>
<summary>Original English</summary>

**Clive Thompson**: Embarrassing. Yeah. I asked him. I said, "Does that work?"

</details>

**Natalie Kitroof**: 是的，我正想问，我们不是应该对这些 AI 客气点吗，万一哪天机器人真的统治了世界呢？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Well, yeah. I was going to ask, aren't we supposed to be being nice to these AIs just in case the robots end up taking over the world?

</details>

**Clive Thompson**: 是啊，没错，别吃掉我。我的意思是，从某种意义上说，我明白为什么这有效。因为大型语言模型（LLM）是语言机器，它们根据词语所处的上下文来理解语言的意义。所以如果它们看到“令人羞愧”这个词，它们理解这个词来自一个“坏街区”，对吧？那里有不好的事情，有尴尬、羞辱等等。这只是有助于提高筹码，让它领会这些话的重要性。所以事实证明，**情绪化语言**、严厉甚至苛刻的语言可能确实有效果。表面上看这有点疯狂，但当你思考大型语言模型的工作方式时，它是有道理的。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah, exactly. Yeah. Don't eat me. I mean, in one sense, I understood why it works. It's because large language models, I mean, they're language machines and so they understand the meaning of language based on the company it keeps. So if they see the word embarrassing, they understand that like, oh, that that word that comes from a bad neighborhood, right? Like there's bad things there and there's embarrassing, humiliation, you know, whatnot. And so that just helps raise the stakes so that it it grasps the import of those words. So it turns out that actually emotional language and stern and even harsh language probably does have an effect, right? Like it it seems kind of nuts on the surface, but when you think about the way large language models work, it it it makes sense.

</details>

### 技能流失与“去技能化”的隐忧

**Natalie Kitroof**: 好的。你非常出色地描述了为什么程序员喜欢这种新的工作方式。从你所说的来看，对于从事这项工作的人来说，显然有很多好处。听起来他们整体上感觉更有力量了。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Okay. You have done a very good job of describing why coders like this new way of working. From what you said, it seems pretty obvious that there are many upsides of this for the people doing this work. It sounds like they just feel much more powerful overall.

</details>

**Clive Thompson**: 是的，我交谈过的大多数程序员都对这种效率提升感到惊讶。他们会说：“这些事情在我的待办事项清单上已经困扰我好几年了，现在我正在把它们一一消灭。我正在搞定它们。”所以总的来说，有一种真正的兴奋感，甚至有时是欣喜若狂。但也有一些担忧。他们担心如果过于依赖 AI，会失去自己的技能。他们担心工作会被 AI 夺走。而且他们担心进展太快了。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah, most of the coders I spoke to were just sort of astonished at how much more productive they felt. They would say things like, you know, I've had this to-do list of things haunting me for years, and I'm knocking it all off. I'm I'm getting it done. So, overall, there is a real sense of excitement, even giddiness at times. But there are some concerns. They're worried about losing their skills if they rely too much on AI. They're worried about jobs being taken away by AI. And they worry that they're moving too quickly.

</details>

**Natalie Kitroof**: 我们稍后回来。

好的，Clive，我想谈谈那些恐惧。我们能深入探讨一下吗？他们对你列出的那些事情感到担心是对的吗？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: We'll be right back. Okay, Clive, I want to talk about those fears. Can we dig into them? Are they right to be worried about the things that you laid out?

</details>

**Clive Thompson**: 是的，绝对如此。关于 **“去技能化（Deskilling）”** 的担忧非常有趣，因为我为这个故事采访的很多人都比较资深。他们是了解代码的那一代人，因为他们仍然必须手工完成。所以他们会告诉我，拥有 AI 代理对我们来说很棒，因为如果它们产生了一些错误或臃肿的内容，我们有经验去审视并说：这不好，重写一遍。他们都会说：那么下一代呢？我们会不会在 5 年或 10 年后发现，下一代软件开发人员根本没有那种深度代码感（Code sense），无法让他们成为真正优秀的工程师？

一个相关的担忧是，因为他们不再编写那么多代码（甚至在某些情况下根本不写），他们担心自己正在失去一点那种代码感。如果你不使用它，你就会失去它。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah, absolutely. The concern about deskskilling is really interesting because a lot of the people that I was talking to for this story were they're a little more senior. So, they're the generation that knows code really well because they still had to do it by hand. And so they would tell me that it's great for us to have the AI agents because if they produce something wrong or flabby, we have the experience to look at that and go that's not good. Do it again. And they would all say, well, you know, what about the next generation? Are we going to discover 5 or 10 years from now that the next generation of software developers, you know, simply don't have that deep code sense that lets them be really, really good engineers? And a related concern there is that because they're not writing code so much anymore or at all in some cases, they worry that they're losing a bit of that code sense. Right. If you don't use it, you're going to lose it.

</details>

**Natalie Kitroof**: 嗯。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Mhm.

</details>

**Clive Thompson**: 我交谈过的一个担心 AI 编码工具正在使她去技能化的人是 **Piaan**。她是一名相对较新的开发人员，还处于职业生涯早期。她的雇主说：“我们希望你使用 Microsoft 的 **GitHub Copilot** 来编写代码。”她每天进行数百次提示，持续了几个月。她开始觉得：“哇，这实际上正在退化我自己的代码知识。我觉得我正在失去编写代码的能力。”这就是她告诉我的。

<details>
<summary>Original English</summary>

**Clive Thompson**: One person I talked to who um was worried about the way AI coding tools were deskilling her was Piaan. She was a reasonably newer developer and so she was in some of her early jobs. Her employers were like, "We want you to use co-pilot by Microsoft to write code." And she was doing hundreds of prompts a day for months. And she started feeling, "Wow, this is actually degrading my own knowledge of code. I feel like I'm losing my ability to code." That's what she told me.

</details>

**Natalie Kitroof**: 听起来对她来说很不安。但是，如果 AI 可以为她代劳，那么她失去编码技能为什么是个问题呢？我不知道如何排版，我不写书法，对吧？这对我来说从来不是问题。难道有些事情我们不能直接说，好吧，作为一个社会，我们已经超越了这个阶段。这难道不是其中之一吗？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Okay, that sounds unsettling for her. But why is it a problem that she's losing her coding skills if AI can do that for her? I don't know how to type set. I don't do calligraphy, right? It's never been an issue for me. Aren't there certain things that we can just say, okay, we've moved past this as a society. Is this one of those things?

</details>

### 对就业市场的深层冲击

**Clive Thompson**: 嗯，这就是伟大的辩论，我也没有答案。我可以告诉你，软件世界中有两个阵营，他们激烈对立。

有一个阵营（可能是大多数开发人员）对此不那么担心。他们认为 AI 已经足够好，并将继续变得足够好，它实际上会比人类更擅长编写代码，因为它不会犯人类那些愚蠢的错误。人们认为编码是件神奇的事情，你必须非常努力，但其实很多工作只是在反复做同样的事情。

<details>
<summary>Original English</summary>

**Clive Thompson**: Well, this is the great debate and I don't have an answer for that. I can tell you that there are two camps of this in the world of software and they are heatedly opposed to each other. There is what I would say is probably the majority of the developers who are a little less worried about that. They think that the AI is good enough and will continue to be good enough that it will actually be better at doing a lot of this code than the humans are because it won't make the stupid human mistakes. You know, people think of code as like this magical thing where you have to work really hard at it, but a lot of it is just doing the same thing over and over and over again. Right.

</details>

**Natalie Kitroof**: 对。极其死板、乏味的工作。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Right. Extremely wrote, tedious work.

</details>

**Clive Thompson**: 乏味且死板。当人类去做时，我们会犯错，而机器人不会。所以你可以辩论——这一群开发人员就是这么认为的——软件实际上会变得更可靠，因为代理完成了所有工作。但另一个较小的阵营提出了一个非常有力的论点：不，当你编写新代码时，它不仅仅是你构建好就完事了。随着你添加与之相邻并与之交互的新事物，你必须维护它。可能会有糟糕或奇怪的交互。所以 AI 现在写的代码可能看起来不错，但随着时间的推移，它可能会与代码库的其他部分产生非常困难或糟糕的交互。可能存在我们现在看不到的细微 Bug，它们会不断堆积，5 年后你就会面临一团乱麻。所以有一群程序员说我们不应该使用这些东西。至少不能像现在这样大规模使用。

<details>
<summary>Original English</summary>

**Clive Thompson**: It's wrote and tedious. And when humans do it, we make mistakes and the robots don't. Right? So you could make an argument and this cohort of developers do that the software will actually be more reliable because the agents are doing all of it. But then there's a very strong argument by a smaller cohort that say no, when you write new code, it's not just something you build and it stays up. You have to maintain it as you add new things to it adjacent to it that interact with it. There might be interactions that are bad or weird. And so the code that the AI is writing might look good right now, but there's a potential that down the line, it could cause really difficult or nasty interactions with other parts of the codebase. There could be subtle bugs that we don't see right now that really start to pile up and 5 years from now, you've got a huge mess. So there's a cohort of coders who are saying we shouldn't be using this stuff. Not at scale, not the way they're using it right now.

</details>

**Natalie Kitroof**: 好的，我想回到**失业**的问题，这是你提到的另一个恐惧。你认为这一切是否意味着现在的初级程序员在某种程度上是可以被取代的，也许在不久的将来根本不会有“初级程序员”这种职业，因为整个工作类别都会消失，就像“排字工”一样。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Okay, I want to return to the question of job loss, which was another fear that you mentioned. Do you think that all of this means that junior coders right now are actually somewhat replaceable in this field and that maybe in the near future there will be no such thing as a junior coder at all because that entire job category will disappear in the same way that like the job of type setter did.

</details>

**Clive Thompson**: 我认为对新的初级雇员的需求肯定有缩减的风险，而且我认为我们已经看到了这一点。如果你看看斯坦福大学 **Eric Benjolson** 的研究，他分析了职位发布和招聘情况，他发现软件开发人员的招聘人数下降了 **16%**。而且这发生在过去的一年左右。所以，如果这种情况发生在 AI 编码工具还处于“从爬到走再到跑”的阶段，那么当它们开始冲刺时会发生什么呢？

当然，另一个问题是，这是资本主义。我的意思是，所有这些大公司总是在寻找省钱的方法。在高科技公司，最昂贵的开支之一就是这些开发人员的工资。所以，“哦，我们可以用 AI 替换其中的一部分”这个想法非常有吸引力。我们现在在所有形式的白领劳动中都看到了这一点。所有的 C 级高管都喜欢这个想法：要么因为可以用 AI 替换而裁员，要么以此威胁要这样做。因为即使你没有被 AI 替换，如果你被去技能化并导致工作贬值，老板就更容易对你颐指气使。

<details>
<summary>Original English</summary>

**Clive Thompson**: I think there's definitely a danger that the demand for new junior hires is going to soften and I think we've already seen that. You know, if you look at the research of Eric Benjolson at Stanford, he analyzed job postings, job hirings, and he found that in software developers, it was down by 16%. Right? And that was already happening just in the last, you know, year or so. So if that's happening when the AI coding tools are really just going from a crawl to a walk to a run, what might happen when they're sprinting? And the other problem of course is, you know, this is capitalism, right? I mean, all of these large firms are always looking for ways to save money. And at high-tech companies, some of the most expensive money are the salaries of these developers, you know. So the idea of like, oh, we can replace even a chunk of them with AI, that's really compelling. And we're seeing this across all forms of white collar labor right now, right? All the seauite folks love the idea of being able to either lay people off because they can replace them with AI or threaten to do so. Right? Because even if you're not replaced by AI, if you desill and devalue the job, it just gets easier for the owners to push you around.

</details>

### 历史的镜像：当软件变得像纸一样廉价

**Natalie Kitroof**: Clive，如果编码处于 AI 影响工作的最前沿——无论是工作量还是质量——那么对于我们这些不从事编码工作的人来说，这一切意味着什么？其他领域的白领或蓝领工人也会看到 AI 以类似的方式接管吗？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Clive, if coding is at the vanguard of AI affecting work, the amount of it, the quality of it, what does all of this mean for the rest of us who don't work as coders? Will white collar or bluecollar workers in other fields see AI take over in a similar way?

</details>

**Clive Thompson**: 开发人员现在经历的事情可能看起来有点矛盾，那就是：他们花多年时间培养了这些非常、非常高难度的技术技能，结果证明这些反而是最容易被自动化的。难以自动化的是像与同事和客户交谈、弄清楚我们应该构建什么、设定优先级、制定策略。AI 无法做到这些。

<details>
<summary>Original English</summary>

**Clive Thompson**: What developers are experiencing right now is something that maybe seems a little paradoxical which is that they had spent years developing these very very hard technical skills and it turns out those are some of the easiest things to automate right the hard stuff to automate is like talking to our colleagues and our customers and figuring out what should we be building right setting priority setting strategy AI can't do that right

</details>

**Natalie Kitroof**: 仍然存在真正的**人类技能**。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: there are still truly human skills

</details>

**Clive Thompson**: 仍然有真正的人类技能。所以我开始怀疑这是否是我们可能在其他形式的白领工作中看到的模式。就像在 80 年代，国际象棋似乎很难下，计算机根本不可能做到。但说话似乎很容易，计算机当然应该能说话。但结果证明，对计算机来说，下棋比学会像人一样说话要容易得多。他们在 90 年代征服了国际象棋，而学会像人一样说话又多花了二十年。所以我觉得我们在 AI 身上看到的一件事是：那些我们认为“啊，这是我的核心技能”的东西，其实可能并不是。你的技能在于其他地方。

<details>
<summary>Original English</summary>

**Clive Thompson**: there are still truly human skills and So I began to wonder if that's a pattern we might see in other forms of white color work. Like back in the 80s it seemed like chess was so hard to play. There was no way a computer was going to do it. But it seemed like speaking that's easy. Surely a computer should be able to just speak. But it turned out that chess was actually easier for computers to do than to learn to speak. They conquered chess in the '9s and it took like two decades more to learn how to talk like a human. So one of the things I think we see with AI is that things that we thought maybe were like ah this is my big skill. Yeah that's not really your skill. Your skill lies elsewhere.

</details>

**Natalie Kitroof**: 好的。所以你谈论的过程本质上是一个在不同领域中，我们逐渐认识到哪些事情是不可自动化的、机器人做不到的，然后人们将重点放在那里的过程。你认为这种转型需要多长时间才能大规模影响工作？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Okay. So the process that you're talking about is essentially one in which in different fields we kind of learn the thing that is not automatable that a bot can't do and where people sort of focus on that. How long do you think it's going to take for those transformations to hit jobs on mass?

</details>

**Clive Thompson**: 我的水晶球预测是，这会比我们想象的要长，原因如下：我们从计算机历史中学到的是，一项技术对企业生活产生影响的时间可能比我们预期的要长得多。在 80 年代和 90 年代初，个人电脑出现了。公司现在可以用电脑打字，而不是用打字机。当时人们假设这会极大地提高公司的生产力。起初并没有。经济学家们对此感到困惑。原因在于，要真正提高公司的生产力或效率，公司必须围绕计算机**重组其业务模式**。他们必须开始想：“好吧，我们不需要你仅仅把电脑当成打字机，打印一份备忘录发给所有人。直接发邮件给某人就行。这意味着我们所有区域办事处的人都可以同时阅读相同的内容。”一旦他们开始围绕计算机和互联网的便利性来重组信息和决策流程，你才开始看到效率、生产力和 GDP 的变化。但这花了很长时间。我怀疑 AI 也会走同样的路。

<details>
<summary>Original English</summary>

**Clive Thompson**: My my crystal ball was that it's going to be longer than we think for the following reason. What we learn from the history of computers is that it can take things a lot longer to have an impact on corporate life than we would expect. So back in the 80s and early 90s, you get the advent of the personal computer. a company can now instead of having someone type memos on a typewriter, they can do it on a computer. And there's this assumption that it's going to dramatically increase the productivity of companies. And at first it doesn't. And economists are kind of baffled by this. And it was because to actually increase productivity or efficiency of companies, the company had to reorganize the way it did business around the computers, right? they had to start going, "Well, we don't need you to just treat the computer like a typewriter and print up a memo and then send it to everyone. Just email it to someone. That means everyone at all our regional offices can all be reading the same stuff at the same time." And so once they began to reorganize the way that information and decisions flowed around the affordances of computers and the internet, then you began to see changes in efficiency, productivity, and GDP. But it took a long time. And my suspicion would be that it's going to be the same way with with AI.

</details>

**Natalie Kitroof**: 嗯，我想问问这个，因为我觉得最近一切都在以极快的速度进行。我是说，创新的步伐，真的感觉像是处于一个完全不同层次的超高速运行。这是错觉吗？还是只是我的感觉？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Well, yeah, I want to ask about that because it feels to me as though everything has been on a really accelerated timeline recently. I mean, the pace of innovation, it truly feels like super speed on a different level. Is that wrong? Is that just me?

</details>

**Clive Thompson**: 的确快了，但很多发生的变化并没有工业影响，对吧？每当有人裁掉一堆人并声称“我们要用 AI 替换他们”时，你通常会发现，六个月后再去追踪，他们又不得不重新雇佣其中的一部分人，因为 AI 根本不管用。所以，是的，在文化层面上存在大规模的加速，这通常是相当令人不安的。但如果你四处走走，去和那些推动经济的大公司谈谈，这种情况在那里还没有真正发生。当然，在我的报道中你也能看到这一点：小公司、初创公司，是的，他们动作非常快。而在 **Google**，他们的速度只快了 10%，我认为这更接近你在大型白领工作中可能看到的实际影响。

<details>
<summary>Original English</summary>

**Clive Thompson**: I mean, it has, but a lot of stuff that has changed doesn't have industrial impact, right? Like whenever someone lays off a bunch of people saying we're going to replace them with AI, often they discover if you follow them 6 months later they had to rehire a bunch of them because it just didn't work. So yes, there is a massive acceleration on a cultural level that can often be quite alarming. But if you go around and talk to companies, big companies like the ones that are, you know, moving the economy, it hasn't really happened there. And you can even see that, of course, in my reporting, right? Small little companies, startups, yeah, they're moving really fast. Google they're moving 10% faster and I think that's that's closer to the impact you might see if you look at white collar work at large

</details>

**Natalie Kitroof**: 我不得不承认，这听起来确实让人稍微松了一口气。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: there is something comforting about that I have to just admit

</details>

**Natalie Kitroof**: 我们一直在谈论开发软件的人员工作的转变。我想问问他们到底在创造什么，以及我们一直在谈论的创新可能会如何改变这一点。换句话说，对于我们这些主要通过与这些人制造的产品互动来与技术互动的人来说，这一切的好处是什么？

<details>
<summary>Original English</summary>

**Natalie Kitroof**: so we've been talking a lot about the shift in the work of the people who are making software I want to ask you about what they're actually creating and how the innovation that we've been talking about might change that like what is the upshot of all of this for those of us who will mostly interact with it by interacting with the products that these people make. In other words, what is the upside for the rest of us of all of this?

</details>

**Clive Thompson**: 我想其中的一个好处是，虽然感觉我们生活在一个软件泛滥的世界，对吧？都是 20 年前不存在的东西——社交网络、即时通讯。但如果你看看工作世界，仍有大量事物从未得到过软件的帮助。我数不清跟多少家公司谈过，他们可能是价值 5000 万美元的混凝土搅拌公司，他们希望能有更好的软件来管理公司，但他们其实什么都没有。因为对于一家 5000 万美元的公司来说，这听起来很奇怪，但他们还没大到能雇得起 5 个软件开发人员来开发定制软件。他们负担不起。所以他们就这么凑合着，整个公司运行在三张 Excel 表格上，电脑还是 Windows XP，他们甚至不敢更新，因为怕一更新就把追踪开支的所有系统都搞坏了。令人惊讶的是，大量中型企业在技术服务方面极度匮乏。如果你在这些公司工作，你肯定深有体会。

所以，如果编写软件变得更容易，如果能有一个这样的世界：我有我的史泰登岛混凝土搅拌公司，年营收 5000 万。我想要软件让员工的生活变得更好，但我以前买不起，因为我雇不起年薪 20 万的五个人。但如果有人过来说：“好吧，只要 6 到 7 万美元，我就能为你构建并维护它”，因为这就是我作为软件开发人员的生产力水平。你就能开始看到日常生活中许多方面的实际改善。我想这是你可能会看到的一个领域。

在最高层面上，将会发生的是，**软件不再是珍贵且罕见的东西**。这让我想起纸张的演变——这听起来可能很奇怪。纸张曾经极其稀少。回到革命前的宾夕法尼亚州，普通人一年只能用到四张纸。然后突然间，纸变得便宜得多，到处都是，你甚至有了像 **便利贴（Post-it notes）** 这样奇怪的纸张形式，它们彻底改变了你生活和战斗的方式。

<details>
<summary>Original English</summary>

**Clive Thompson**: I guess one of the upsides is that it feels like we live in a world where there's tons of software, right? Just stuff that didn't exist 20 years ago. social networks, you know, text messaging. But if you look at the world of work, there is just a massive amount of things that have really never been helped out by software at all. I can't tell you how many companies I talk to. They're like $50 million, you know, concrete mixing firm and they would like to have better software to run their company and they don't really have anything because this sounds weird for a $50 million company, but they're not big enough to to be able to hire like five software people to make custom software. They can't afford to do that. So they just toddle along running their entire company on three Excel spreadsheets on a Windows XP computer that they're afraid to update because that will break everything that they're using to track all their expenses. An astonishingly large number of these midsize firms are horribly underserved by technology. And if you work at one of these companies, you know what it's like. So, if it becomes easier to write software and if you could have a world where like, okay, you know, I've got my, you know, Staten Island concrete mixing company, 50 million a year. I'd love software to make life better for my employees, but I I've never been able to have it cuz I can't hire five people, $200,000 a year. But what if one person came along and said, "Okay, for 60 grand, 70 grand, I can build that for you and maintain it." because that's just how much more productive I am as a software developer. You could start to see a lot of improvements in these kind of actually good ways in everyday life for a lot of people at work. That's one area where I think you might see that happen. And I guess at the highest level, what's going to happen is that software stops being something that is precious and rare. It reminds me maybe a little bit of what happened with like this is going to sound really weird, but with paper. So paper used to be incredibly rare. You go back to pre-revolutionary Pennsylvania and the average person had access to like four pieces of paper a year and then suddenly it becomes a lot cheaper and all over the place and you've got weird things like post-it notes which are these really weird forms of paper that just transform the way that you live your life in this fight.

</details>

**Natalie Kitroof**: 我顺便说一下，我非常喜欢便利贴。我想知道当时人们是否也对这种纸张泛滥感到恐惧。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Totally love post-it notes by the way. I wonder if people were scared of this proliferation of paper at the time.

</details>

**Clive Thompson**: 哦，他们肯定觉得那是坏事。这就是为什么当时会有禁书避孕法（Comstock laws），对吧？他们担心年轻人会互相写淫秽信件。所以，我认为当软件不再是某种特殊而困难的东西，而变得几乎像便利贴一样无处不在时，非常奇怪的事情将会发生。我们为了短期目的而召唤它。它改变了我们交流以及与他人打交道的方式，以我无法预测的方式。但我确实认为这就是我们将面临的情况。

这里有另一个类比。在 70 和 80 年代，文字处理（Word processing）非常困难。你有一台机器，有人花几个小时设计文档，你反复迭代多次以确保正确，然后才敢点击打印。然后在 1980 和 90 年代，**Macintosh** 出现了，它说：好吧，任何人都可以制作文档。突然间，人们开始为自己的生日派对制作难看的传单、制作同人志等等，出现这种奇怪的爆发。如果你在 1983 年问某人：这个文字处理机到底要做什么？你绝不会预测到 1996 年会出现暴乱女孩（Riot Grrrl）同人志，对吧？

<details>
<summary>Original English</summary>

**Clive Thompson**: Oh, they definitely thought it was bad. I mean that's why the comtock laws existed, right? They were worried about young people writing smutty letters to one another. So I I think something very weird is going to happen as software stops being something that is special and difficult and becomes almost like a post-it note where it is ubiquitous. We call it into being for short-term reasons. It changes aspects of the way we communicate and the way we deal with other people in ways that I can't really predict. But I do think that that is what we're looking at. But here's another parallel. Word processing back in the 70s and ' 80s was really hard to do. you had a machine and you know someone spent hours designing a document and you went through many iterations to make sure it was right before you hit print. And then in the 1980s and 1990s the Macintosh said okay anyone can make a document and suddenly people are like creating really ugly flyers for their birthdays and zenes and what not and this weird explosion and if you'd said to someone in 1983 what exactly is this word processor going to do? You would not have predicted riot girl zenes in 1996, right?

</details>

**Natalie Kitroof**: 的确如此。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Totally.

</details>

**Clive Thompson**: 所以我认为这种转变即将打击我们。我真的没有能力预测这对我们意味着什么，但我认为这将会变得异常奇妙且怪异。

<details>
<summary>Original English</summary>

**Clive Thompson**: And so that is kind of I think this transformation that's about to hit us. I don't really have the ability to predict what that's going to mean for us, but I think it's going to be incredibly weird.

</details>

**Natalie Kitroof**: 嗯，我的意思是，你的回答似乎是：这既很棒，又很怪异，而且潜在地在某些方面很糟糕。我们真的不知道。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Uh in in the same way that those previous transformations are incredibly weird. No, I mean I think your answer is kind of this is going to be both awesome and weird and potentially bad in some ways. We really don't know.

</details>

**Clive Thompson**: 这就是现状。你知道，在技术领域有一句话：多不仅仅是多，**“多”意味着不同**。

<details>
<summary>Original English</summary>

**Clive Thompson**: And that's just kind of the deal. You know, there there's a there's a phrase in the world of technology that more is not just more. More is different.

</details>

**Natalie Kitroof**: 不同的行为会出现。所以我认为这是我们在社会和公民层面可能会经历的事情，随着软件从某种艰巨困难的东西变成某种轻而易举就能召唤出来的东西。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Different behaviors emerge. And so that is something that I think we are likely to experience socially, civically as software goes from being something that is hard and difficult to something that is trivially easy to summon into being.

</details>

**Natalie Kitroof**: 我听到的是，无论发生什么，这种变化都将反映我们自身。我们将得到我们配得上的技术。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: What I'm hearing is that whatever happens, this change is going to reflect us. We will get the technology that we deserve.

</details>

**Clive Thompson**: 是的。正是如此。它将催化所有人类的欲望。有害的、美妙的、可怕的、美丽的。我们有了莎士比亚，也有了关于你生日的十四行诗。我们有人用它们来分析和理解个人医疗记录。我们也面临虚假信息和大学、高中论文的大规模作弊。随着 AI 编码革命的推进，这一切都将大规模供应。

<details>
<summary>Original English</summary>

**Clive Thompson**: Yeah. Exactly. It is going to catalyze all of the human desires. the malign ones, the delicious ones, the terrible ones, the beautiful ones. We've got, you know, Shakespeare and sonnetss about your birthday. We've got people who are using them to, you know, analyze and understand personal medical records. And we've got disinformation and wholesale cheating on essays at college and high school. All that stuff is going to be on offer at scale, as they say in Silicon Valley, as the AI coding revolution goes forward.

</details>

**Natalie Kitroof**: 好了，Clive，你知道什么才是真正的人类技能吗？依然是在《每日新闻》做一名出色的嘉宾。所以，感谢你的到来。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: Well, Clive, you know what is truly a human skill? Still being a great guest on the daily. So, thanks for being here.

</details>

**Clive Thompson**: 很高兴听到我还保有那种人类优势。

<details>
<summary>Original English</summary>

**Clive Thompson**: Glad to hear that I still have that human edge.

</details>

**Natalie Kitroof**: 我们稍后回来。

以下是你今天还需要知道的其他消息。

周一，两名国会议员，加利福尼亚州的埃里克·斯瓦尔韦尔（Eric Swalwell）和德克萨斯州的托尼·冈萨雷斯（Tony Gonzalez），在数小时内相继辞职。两人都面临性行为不端的指控，以及要求他们下台或面临众议院除名的呼声。民主党人斯瓦尔韦尔在《旧金山纪事报》和 CNN 发布了多名女性指控他在周五实施性侵犯或不端行为的报道后宣布了他的决定。他的辞职紧随他周日决定退出加利福尼亚州州长竞选之后。

共和党人冈萨雷斯被指控与一名后来自杀的下属保持强迫关系。冈萨雷斯起初否认存在性关系，后来承认了一个错误，并数月来一直在抵制要求其离职的呼声。

此外，总统特朗普与教皇利奥十四世（Pope Leo XIV）之间的冲突正在升温，教皇一直是美国对伊朗战争最有力的批评者之一。周日，特朗普在社交媒体帖子中猛烈抨击教皇，指责他“对犯罪软弱”、“外交政策糟糕”以及“迎合激进左翼”。

教皇周一作出回应，表示他不害怕特朗普政府，并将继续大声疾呼反对战争。他说：“太多无辜的人被杀害，我认为必须有人站出来说，还有更好的解决办法。”

今天的节目由 Diana Wyn、Nina Feldman 和 Michael Simon Johnson 制作。由 Brendan Clinkenberg 编辑，Paige Cowat 提供协助，音乐由 Dan Pal、Pat McCusker 和 Michael Simon Johnson 创作。我们的主题音乐由 Wonderly 创作。本集由 Chris Wood 担任音频工程师。

这就是今天的《每日新闻》。我是 Natalie Kitroof。明天见。

<details>
<summary>Original English</summary>

**Natalie Kitroof**: We'll be right back. Here's what else you need to know today. Two congressmen, representatives Eric Swallwell of California and Tony Gonzalez of Texas, resigned within hours of each other on Monday. Both men had faced allegations of sexual misconduct and calls for them to step down or face expulsion from the House. Swallwell, a Democrat, announced his decision after the San Francisco Chronicle and CNN published the accounts of several women accusing him of sexual assault or misconduct on Friday. His resignation comes on the heels of his decision Sunday to drop out of the California governor race. Gonzalez, a Republican, was accused of a coercive relationship with a staff member who later killed herself. Gonzalez first denied that there had been a sexual relationship, then later admitted a mistake and had been fighting calls to quit his post for months. And a brewing conflict has escalated between President Trump and Pope Leo XIV, who's been one of the most powerful critics of the US war with Iran. On Sunday, Trump lashed out at the Pope in a social media post, accusing him of being quote weak on crime, terrible for foreign policy, and catering to the radical left. And the Pope responded on Monday saying he wasn't scared of the Trump administration and that he would continue to speak out against the war. Too many innocent people are being killed and I think someone has to stand up and say there's a better way to put this. Today's episode was produced by Diana Wyn, Nina Feldman, and Michael Simon Johnson. It was edited by Brendan Clinkenberg with help from Paige Cowat and contains music by Dan Pal, Pat McCusker, and Michael Simon Johnson. Our theme music is by Wonderly. This episode was engineered by Chris Wood. That's it for the daily. I'm Natalie Kitroof. See you tomorrow.

</details>