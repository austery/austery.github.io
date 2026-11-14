---
author: AI Engineer
date: '2026-11-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=AYFcmnQrZCg
speaker: AI Engineer
tags:
  - ai-agent
  - investment
  - hedge-fund
  - decision-making
title: Coatue Frank Long：AI Agent 对投资的颠覆将超越编程
summary: Coatue 的 Frank 阐述了将对冲基金抽象为函数的框架：输入外部与内部上下文，压缩输出包含标的、仓位与时机的元组。他指出投资系统的核心挑战在于极其庞大的超参数搜索空间，需为信息收集、过滤、分析及决策等各节点合理匹配确定性代码、统计机器学习、LLM 与人类四种执行器，并通过科学评估实现爬山式优化。
insight: ''
draft: true
series: ''
category: investment-assets
area: finance-wealth
project: []
people:
  - Frank Long
companies_orgs:
  - Coatue
  - KKR
  - Kensho
products_models: []
media_books: []
status: evergreen
---
### 投资与对冲基金的函数抽象

[音乐]

>> 我叫 Frank。我在 Coatue 工作，这是一家横跨一级和二级市场的科技投资机构。在我们的业务中，你真正需要做的是能够对大主题下高确信度的注，并见证它们的展开。坦白说，我认为职业生涯也是如此。去年当我加入 Coatue 时，我想下的注是：我认为智能体（Agent）在投资领域产生的影响，甚至会比在编程领域更大。
<details>
<summary>Original English</summary>
[music]

>> My name's Frank. I work at Coatue, which is a technology investment firm across public and private markets. So, in our business, what you really need to do is be able to take high conviction bets on big themes and watch those play out. I think honestly a career is the same way. And last year when I joined Coatue, the bet that I wanted to make was I think that agents will have an even bigger impact in investing than they did at coding.
</details>

我知道这是一个很大的论断。我们大家今天聚在这里，都是因为 AI 在编程领域所带来的颠覆性影响，但我对此确实深信不疑。今天我想谈一谈我们用来真正实现这一影响的框架。
<details>
<summary>Original English</summary>
I know that's a big statement. We're all here because of the transformat- transformative impact that AI has had in coding, but I really believe it strongly and today I want to talk a little bit about the framework that we use to actually realize that impact.
</details>

从高层面上看，你可以把对冲基金想象成一个接收两个参数的函数：外部上下文（Context External）和内部上下文（Context Internal），然后吐出一个元组：选股、仓位、时机。
<details>
<summary>Original English</summary>
So, at a high level, you can think about a hedge fund as a function that takes in two parameters, context external and context internal, and spits out one tuple, selection, size, timing.
</details>

什么股票？买多少？什么时候买？对吧？我认为这是一个很好的框架，能够把我们的工作落地。我们试图解决的是一个压缩问题：你如何吸纳全世界的所有信息，并吐出这一个简单的元组？而我们提供的产品，本质上就是由构建出投资组合的这个元组构成的时序序列。
<details>
<summary>Original English</summary>
What stock? How much? When? Right? And I think this is a good framework to actually to ground our work, which is we're trying to solve this compression problem of how do you take all the information in the world and spit out this one simple tuple and the product that we that we provide is essentially a time series of this tuple that constructs a portfolio.
</details>

### 输入端：外部与内部上下文的构建

那么，让我们从最顶层的输入端开始。这是一个非常简单的理念：我们盯着屏幕，看东西，做工作。凡是人类在屏幕像素上能看到的每一件事物，你机构里的智能体都应该能够通过 API 看到。
<details>
<summary>Original English</summary>
So, let's start from the top, which is the inputs. Very simple philosophy. We use our screens, we look at stuff, we do work. Every single thing that a human can see in pixels on the screen, an agent in your building should be able to see via API.
</details>

我常用的类比是：想象一下，你招来了有史以来最聪明的人、当世最伟大的投资家，把他们引进了你们公司，但给他们的电脑却没有你们 75% 服务的登录权限。如果系统没有真正采取行动的工具，它有多聪明几乎毫无意义。
<details>
<summary>Original English</summary>
Uh the analogy I use is imagine you brought the smartest people ever, the greatest investors alive, and you brought them into your company, but you gave them a computer without logins to 75% of your services. It it's almost how smart the system is if it doesn't have the tools to actually action that.
</details>

所以这两个部分：首先是外部上下文，对吧？这里没什么意外的。想想新闻、行情价格、财报文件，所有这些都应该能轻松获取，而且不是通过拖拽、复制粘贴，而是直接通过 API 获取。
<details>
<summary>Original English</summary>
So, the two parts, external context, right? No surprises here. Think the news, prices, filings, all of that should be easily accessible and not via dragging and dropping, copy and pasting, like directly via API.
</details>

内部上下文同样重要，对吧？这是你们公司自身的情况。比如我们当前的持仓、我们对某些标的潜在的流动性和风控要求，以及过往的案例研究，或者对某个行业、股票或管理层的历史交道。这些东西都超级重要。所以这是基石。而且我认为——这绝非我的功劳——KKR 在这方面做出了十多年的卓越表率。这既是技术上的，也是文化上的。我们拥有一支了不起的数据科学团队，拥有极佳的流程和极佳的系统来引入所有这些。同样重要的是，我们拥有一种超级严谨且自底向上建立起来的文化，用来捕捉所有这些洞见。几十年来，我们对每一笔交易都归档了详尽的笔记，记录了我们做出的或没做出的每一个决定、什么是顺利的、什么是不顺利的，这让我们做好了向 AI 开放接口的准备。
<details>
<summary>Original English</summary>
Internal context is just as important, right? So, this is your own firm situation. So, that might be our current positions, potential liquidity and risk requirements we have around certain names, and past case studies or um you know, history with a certain sector or stock or management team. That stuff's all super important. So, this is the foundation and I think uh no credit to me, KKR has been an amazing leader on this for over a decade. It's both technological and cultural. We have an amazing data science team, amazing, amazing processes, amazing, amazing systems that bring all this in. And just as importantly, we have a culture that is super, super rigorous and built from the ground up to capture all this insight. For decades, we've filed every single note about every single trade, about every single decision we made or didn't make, about what went well and what didn't go well, and that's poised us to expose us to AI.
</details>

### 函数分解：收集、分析与决策

所以仔细想想，我大概不能只是把所有这些东西直接塞进上下文窗口，然后变出三个神奇的数字就可以收工回家了，对吧？不可能那么简单。你可能必须把这个函数进一步拆解，对吧？
<details>
<summary>Original English</summary>
So, if you think about it, I probably can't just take all of those things, jam them into a context window, and get my magic three numbers and go home, right? It can't be that easy. You probably have to break down this function a bit further, right?
</details>

所以，也许第一步是我引入外部和内部上下文，并进行收集，对吧？我想收集它，我想过滤掉相关的和不相关的内容。好吧，我抓取了一些关于 NBA 的新闻文章，那可能对股票无关紧要；但是等等，这篇实际上跟某些地方许可审批有关，可能会影响数据中心。在收集这一步里存在大量的细微差别。接着你会看到下一步：我需要分析那些信息并形成一种观点。对吧？我确实需要思考这对公开和非公开市场意味着什么。然后我需要把那种观点转化为决策。一个决策对象包含这三个参数，对吧？这三个子模块。
<details>
<summary>Original English</summary>
So, maybe the first step is I take in that external and internal context, and I gather it, right? I want to gather it, I want to filter out what's relevant and not relevant. Okay, well, I pulled some news articles about the NBA. That probably isn't material to stocks, but oh, well, this is actually related to some local permitting that might actually impact data centers, like there's a lot of nuance in this gather step. Um then you'll see probably next step is I need to analyze that information and form a view. Right? I actually need to think about what that means for the markets, public and private. Uh and then I need to take that view and turn it into a decision. A decision object has these three parameters, right? These three sort of sub sub pieces.
</details>

所以你可以看到，每一步都有输入和输出，而后一步骤的输入就是前一个函数生成的输出。作为一名工程师，我认为这是一种以极具合理性的方式将问题概念化的途径。但即使这样，[嗤笑] 它也绝不可能像写三个函数那么简单，对吧？
<details>
<summary>Original English</summary>
So, you can see every single step has an input and an output and the input for the subsequent step is the output that the previous function generated. I think as an engineer, this is a way for me to conceptualize the problem in a way that makes a lot of sense. But even this it [snorts] really can't be as simple as writing three functions, right?
</details>

### 案例剖析：新闻解读与四类执行器

所以，为了真正领会其涉及的范围并理解问题的全部复杂性，让我们深入第一步——也就是信息收集这一步里面极微小的一个子环节。让我们来做一个解读新闻的案例研究，对吧？
<details>
<summary>Original English</summary>
So, let's just to up really appreciate the scope and understand the full complexity of the problem, let's look into the first step, a tiny sub piece of tiny sub piece of just gathering information and let's do a case study on interpreting the news, right?
</details>

对大家来说大概不是什么秘密：来自亚洲的新闻以及韩国媒体的报道在今年极其重要，因为半导体和 AI 已经成为市场上极其重大的主题。我认为这是 AI 有望产生巨大影响的一个领域——阅读韩语新闻的能力比我们完全不懂韩语的员工要好得多，对吧？我认为我有充分的论据表明这可能是一个很好的用例。所以你可以想象，第一步是获取文章，我需要采集文章，对吧？这可以是一个 MCP，可以是一个 CLI，购买数据源授权，清洗数据源。实际上有很多方法可以做到这一点。
<details>
<summary>Original English</summary>
So it's probably no secret to you guys that you know, news from Asia and Korean Korean media outlets has been super important this year because semis, AI have been a huge huge theme in the market, huge theme. And I think this is an area where AI is poised to have a lot of impact is reading uh Korean language news better than our completely non-Korean speaking staff, right? Uh I think I have a good thesis that this might be a good use case. So you can imagine the first step is I have uh articles. I need to collect the articles, right? So, this could be an MCP, this could be a CLI, license the data feeds, clean the data feeds. There's actually a lot of ways to do this.
</details>

哪怕仅仅是写出这个简单的环节，就存在非常多的自由度。我该如何分块（chunk）？当我把它传给 LLM 时，我想把图片作为图片传入吗？还是想拉取图片并转化为文本？这里实际上有大量的旋钮。我几乎把这些旋钮看作传统机器学习系统中的超参数，对吧？我认为每一个旋钮都是我用来进行调优和优化的对象。
<details>
<summary>Original English</summary>
And a lot of dimensions of freedom for how you can even just write this simple piece. How do I chunk it? When I pass it to the LLM, do I want to pull the images as images? Do I want to pull the images and then turn the images into text? There's actually a lot of knobs here, and I almost think about those knobs as like hyper parameters in a traditional machine learning system, right? I think about each of these knobs as something for me to tune and optimize against.
</details>

显然还有过滤，我们谈到过这个。韩国可能也有 NBA 球迷，对吧？很可能会有一堆内容对于我们投资组合中真正极其重要的标的、主题和股票而言是不实质相关的，对吧？所以我想确保把那些过滤掉。
<details>
<summary>Original English</summary>
Obviously, filtration, we talked about it. Korean They're probably Korean NBA fans, right? There's probably a bunch of stuff that's not necessarily material to the the names and themes and stocks in our portfolio that really, really matter, right? So, I want to make sure that I filter those out.
</details>

还有这种“翻译/提取/我是否应该摘要？我是否应该将其提取为某种结构化形式？”同样，有太多太多的做法，有太多方式去实验如何将信息暴露给模型。而这之所以困难的原因之一，就是它一直在变化。
<details>
<summary>Original English</summary>
There's this like translate/extract/should I summarize? Should I extract this into some sort of structured form? Again, so, so many ways to do this, so many ways to experiment how to expose information to the model. And one of the reasons this is hard is it keeps changing.
</details>

显然还有核对。对照这些内容来核对我们自己的内部笔记、内部观点、我们可能进行过的对话、会议录音。我们实际上需要对这些事情进行交叉比对。从不同来源拉取信息并进行交叉比对的想法，是非常强大的。所以在右边你会看到我列了代码、LLM、LLM、代码、人。运行这些函数有非常非常多的方法。
<details>
<summary>Original English</summary>
And obviously, checking. Checking like our own internal notes, our own internal views, potential conversations we've had, meeting recordings against these things. We actually need to cross-reference those things. Actually, the idea of pulling information from disparate sources and cross-referencing them, that's super powerful. So, you'll see on on the right here I have code, LLM, LLM, code, person. There's many, many ways to run these functions. I think about
</details>

啊，对了，最后是更新。我们可能会更新我们的观点。所以，运行这些函数有许多途径。我认为每一行都有一个“执行器”（Runner）。最显而易见的一个就是**代码**。代码非常好：快速、廉价、可靠。因此对于像“如果市盈率小于 15”这样的逻辑，我直接使用确定性代码即可。
<details>
<summary>Original English</summary>
Uh oh, yeah. And finally, update. Potentially, we update our views. So, there's many ways to run these functions. I think of each line as having a runner, and uh the most obvious one is code. Code is very good. It's fast, it's cheap, it's reliable. So, for something like if the price-to-earnings ratio is less than 15, I should just use deterministic code for that.
</details>

第二种执行器是**统计学与经典机器学习**。你可以设想为特定模式拟合一条回归线。这是非常强大的，因为相比纯确定性代码，你可以对复杂得多的关系进行建模，对吧？
<details>
<summary>Original English</summary>
Runner number two is statistics, classical machine learning, and you can imagine fitting a line to a regression for specific pattern. This is very powerful because you can model much more complex relationships than just pure deterministic code, right?
</details>

而对于更复杂的关系——也是我们大家今天聚在这里的原因——**LLM 和 AI 智能体**是另一种类型的执行器，对吧？因此对于摘要之类的事情，这就是前沿水平，对吧？要想通过堆叠一堆 if 语句来做得比现代 LLM 更好地进行摘要，大概是完全不可能的。当然还有**人类**。人类是系统中重要的执行器，对吧？
<details>
<summary>Original English</summary>
And for even more complex relationships, the reason we're all here, LLMs, AI agents, that's another type of runner, right? So, for something like summarization, that's the state of the art, right? It's probably totally impossible to build a a bunch of if statements that can summarize better than a model modern LLM. And of course, uh people. People are important runners in the system, right? So,
</details>

想象一个去见一家公司管理团队的函数。我大概不会想派出——我的意思是，我喜欢宇树科技（Unitree）的新机器人，但我大概不会想派一个 LLM 或 AI 智能体去参加这种会议。我大概也不想派一个 if 语句去开会。我认为在很多情况下，由于判断力、应对现实世界的能力以及所有这些素质，对于该函数的某个特定片段而言，人类就是最佳的执行器。
<details>
<summary>Original English</summary>
uh imagine a function meetings the management team of a company. I probably don't want to send, I mean, I like the new Unitree robots, but I probably don't want to see it send an LLM or an AI agent in to do that. I probably don't want to send an if statement into that meeting. I think there's many cases where, because of judgment and the ability to navigate the real world and all of these things, a person is the best runner for a given piece of the function.
</details>

我认为这是一个超级极其重要的点：为了自动化而自动化毫无光彩可言。对我们来说，目标绝不是把尽可能多的东西都做成 LLM。目标是：对于这个函数的任何给定部分，我能做些什么来最大化绝对质量？
<details>
<summary>Original English</summary>
And I think this is like a super super important point. There is no glory in automating things for the sake of automating things. The goal is not to take as many things and make them LLM as possible for us. The goal is, for any given piece of this function, what can I do to maximize absolute quality?
</details>

### 控制流分支与组合复杂度

如果你实际思考这个函数，它大概看起来像这样。它大概不仅是一堆不同事物构成的线性语句。其中大概存在各种各样的分支逻辑，以及各种各样将其分叉的方式。
<details>
<summary>Original English</summary>
And if you actually think about the function, it probably looks something like this. It's probably not just a linear statement of a bunch of different things. There's probably all kinds of branching logic and all kinds of ways to actually fork this.
</details>

所以，也许我想收集信息然后翻译它，而我的主要目标是提取引言并对照信源进行核实，以确保这些确实是人们说过的原话，这是我的一种方法。但这可能是完全错误的。也许我真正想做的是去重，然后过滤，然后再拉取外部数据；或者我也许想做完全不同的事：我实际上先传入一份纪要，接着只是想寻找其他验证性的数据点；或者我也许正在尝试编写团队……配置这种流程有成千上万种不同的方式。所以，这又是控制流内部的更多超参数，对吧？
<details>
<summary>Original English</summary>
So, maybe I want to collect the information and then translate it, and my main goal is to extract quotes and check those against sources to make sure that these are actually the things that people said, and and that's my approach. But that might be totally wrong. Maybe actually what I want to do is I want to dedupe, and then I want to filter, and then I want to pull external figures, or maybe I want to do something totally different. I actually want to I'm passing in a note first, and I actually just want to find other confirmatory data points, or maybe I'm trying to write team. Uh there's a million different ways to configure this. So, yet again, more hyper parameters within the control flow, right?
</details>

仅仅是思考这个极简的问题——为 LLM 轮询、过滤、摘要、聚合新闻——就有如此多的思路。而其中的每一个方框大概都有一个最优的执行器，对吧？
<details>
<summary>Original English</summary>
So, so many ways to think about just this very simple problem, a polling, filtering, summarizing, aggregating the news for LLMs. And each of these boxes probably has an optimal runner, right? So,
</details>

对于收集而言，最优执行器可能是确定性代码，对吧？我轮询某个给定信源过去 24 小时的数据，那就是确定性代码。过滤，可能是决策模型、LLM、统计学方法，或者几者的结合，对吧？所以这可能低估了复杂度。现实情况是大多数环节都是多执行器的（Multi-runner）。大多数环节都结合了确定性代码加上 LLM 加上统计学方法，或者是人类与 LLM 协同作业。现实是，这大概是我那四个分类桶之间的组合问题，而且分类桶甚至比这更多，因为在 LLM 这个类别内，我还可以调优模型。
<details>
<summary>Original English</summary>
uh the optimal runner might be deterministic code for collection, right? I'm polling last 24 hours for a given source. That's deterministic code. Filtration, decision models, maybe. LLMs, statistical methods, a combination, right? So, this probably understates the complexity. The reality is most things are multi-runner. Most things have deterministic code plus LLM plus statistical method or human with LLM in conjunction. Uh the reality is this it's probably combinatorics between my four buckets, and there's even more buckets than that because within the LLM category, I can tune the model.
</details>

我可以选择大模型、小模型、中型模型。我可以调整思考力度（Thinking effort）：特高、高、中。我可以调整测试框架（Harness）。我可以挑选测试框架，我可以挑选随测试框架加载哪些技能（skills），我可以挑选随技能加载哪些钩子（hooks）。所以在我的搜索空间内又有更多的超参数。在我的搜索空间里有着绝对极其庞大数量的超参数。
<details>
<summary>Original English</summary>
I can choose big model, small model, medium model. I can tune thinking effort. X high, high, medium. I can tune harness. I can choose the harness. I can choose which skills load with the harness. I can choose which hooks load with the skills. So, yet again, more hyper parameters within my search space. I have an absolutely enormous amount of hyper parameters within my search space.
</details>

而这仅仅是针对这一个极小的问题，对吧？我仅仅是在过滤新闻。因此，思考分解这些问题的方式是：我究竟能以什么样的方式将其模块化，从而让我们能够理解和评估？因为那正是我进行爬山式优化（Hill climbing）的基准，对吧？否则，我只是在胡乱调整这些东西：好吧，那实际上应该是一个机器学习系统而不是 LLM；那应该是一个我们训练的小模型；哦不，那实际上根本不应该是个模型，那应该是一个 if 语句；或者天啊，LLM 在把那些转化为投资组合影响方面表现得极其糟糕，那一步真应该由人来做，但他们是在使用一个确定性系统来帮助他们搜索和拉取信息。
<details>
<summary>Original English</summary>
And this is just for this one tiny problem, right? I'm just filtering the news. So, the way uh to think about breaking down these problems is what can I actually compartmentalize in a way that we can understand and evaluate because that's what I'm hill climbing against, right? Otherwise, I'm just tuning these things. I'm okay, well, that should actually be a machine learning system instead of an LLM. That should be a little model that we train. Oh, no, that should actually shouldn't be a model at all. That should be an if statement or Oh, man, LLMs are really, really bad at translating that to portfolio impact. It should really be a human on that step, but they're using uh a deterministic system to help them search and pull the information.
</details>

它可能是所有不同的形态，对吧？如果你没有一个用以爬山优化的北极星指标，你就只是在到处瞎扑腾。
<details>
<summary>Original English</summary>
It could be all different things, right? And if you don't have a North Star to hill climb against, you're just kind of you're just fidgeting around.
</details>

### 全局状态机与更广泛的应用空间

我认为无论我怎么强调都不为过：这仅仅是我们所做的微不足道的一件事。想象一下我们拉取的每一个单一数据源，要将它们转化为中间输出，经历的转换步骤大概远不止三步。所以 Kensho 以及类似 Kensho 的基金的实际图谱，它实际上看起来大概——哦，不是像这样。
<details>
<summary>Original English</summary>
And I think I cannot convey enough that this is just one tiny thing we do. Imagine every single data source that we pull in, there's probably more than just three transformations to get them to the intermediate output. So, the actual graph of Kensho and funds like Kensho, it actually probably looks Oh, not like this.
</details>

这是我的屏幕保护程序。
<details>
<summary>Original English</summary>
This is my screensaver.
</details>

实际的图谱大概看起来像这样，对吧？它可能是极其复杂的。在那些节点中的每一个，我们刚才讨论了至少 10 个超参数，且每个参数至少有 20 个不同的有效取值。因此，搜索空间基本上是无穷无尽的。而搞清楚如何真正把它布局出来，使你既能从技术角度去理解，又能在文化上、组织架构上吸收消化——这正是将 AI 应用于投资领域的巨大挑战。
<details>
<summary>Original English</summary>
The actual graph probably looks something like this, right? It's probably massively complex. In each of those nodes, we just talked about at least 10 hyper parameters with at least 20 different valid values for them. So, the search space is is basically infinite. And figuring out how to actually lay this out in a way that you can comprehend both from technical perspective, but also absorb culturally, organizationally, that is the great challenge of applying AI in investing.
</details>

而在投资之外，我们真正谈论的是构建一个状态机（State machine）：它能够吸纳来自外部世界的信息，并充分理解这些信息以做出连贯的决策。其应用场景远远超出了投资机构的范畴。在公共政策中、在非营利组织中、在药物研发中、在企业战略中。我认为参加像今天这样的论坛，对我而言最令人兴奋的事情之一，就是与来自不同领域、面临不同问题但最终汇聚在同一个问题空间的人们进行交流。我很乐意继续深入探讨这个话题。稍后我会在走廊里交流。这是我的社交账号，感谢大家抽出宝贵的时间。

>> [掌声]
<details>
<summary>Original English</summary>
And beyond investing, what we're really talking about is creating a state machine that can take information from the world and understand it well enough to make coherent decisions. There's use cases for this far and above wider than just investment firms. In policy, in nonprofits, in drug discovery, in corporate strategy, I think one of the most exciting things for me about being in forms like this is talking to other people in dis- different spaces with different problems that kind of congeal on the same problem space. I'd love to keep talking about this. I'll hang out in the hallway afterwards. Here are my socials, and thank you everyone for your time.

>> [applause]
</details>