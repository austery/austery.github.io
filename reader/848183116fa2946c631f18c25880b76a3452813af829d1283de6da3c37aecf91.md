---
author: Latent Space
date: '2026-10-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DWHyPWnzGAI
speaker: Latent Space
tags:
  - recommendation-system
  - financial-nlp
  - commodity-trading
  - vision-language-model
title: Moshi：大宗商品交易员的 AI 推荐引擎与实时洞察平台
summary: 前摩根大通大宗商品交易员、Moshi 创始人 Anekha 与主持人探讨了如何利用推荐系统、图谱与多模态数据为能源和大宗商品交易员打造实时市场洞察引擎，并分享了 AI 与金融跨界创业及技术落地的实际经验。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Anekha Sokhal
companies_orgs:
  - Moshi
  - JPMorgan
products_models: []
media_books: []
status: evergreen
---
### 背景介绍与从交易员到创业者的转型

**Host**: 好，我们现在在演播室。这是我在本次 AIE 的最后一场播客，嘉宾是来自 Moshi 的 Anekha。欢迎。

<details>
<summary>Original English</summary>

**Host**: Okay, we are in the studio. Last podcast of AIE for me with Anekha from Moshi. Welcome.

</details>

**Anekha**: 非常感谢。

<details>
<summary>Original English</summary>

**Anekha**: Thank you so much.

</details>

**Host**: 我念对你的名字了吗，Anekha？

<details>
<summary>Original English</summary>

**Host**: Did I get it right, Anekha?

</details>

**Anekha**: 是的，念对了。

<details>
<summary>Original English</summary>

**Anekha**: Yes, you did.

</details>

**Host**: 你的背景引起了我的兴趣，因为我以前也是个交易员，而你现在是一名创始人。

<details>
<summary>Original English</summary>

**Host**: So your background caught my interest because I was a former trader and you're now a founder.

</details>

**Anekha**: 是的。

<details>
<summary>Original English</summary>

**Anekha**: Yes.

</details>

**Host**: 你刚才也正好在跟我讲你的经历。我想听你亲自聊聊。据我所知，这是你第一次来 AIE。你是怎么听说我们的？做演讲的体验如何，演讲之后又发生了什么？

<details>
<summary>Original English</summary>

**Host**: And you also were telling me just about your experience. I kind of want to hear about it from you. As far as I know, this is your first AIE. How did you hear about us? What was the experience like giving your talk and what happened after?

</details>

**Anekha**: 好啊，首先感谢 AIE 的所有人，因为这真是一次棒极了的体验。也谢谢你邀请我来上播客。能分享我的经历我感到非常兴奋。而且，我认为我们生活在一个节奏极快的时代，我接触到的每个人都感到非常不知所措。所以能够分享我所经历的一切真的很有帮助，因为我本科读的是统计和数学，也就是现在大家口中的 AI。因此能够探讨这些内容、它的演变过程，而且总能与一位前交易员交流，这真的很有意思。还能一起聊聊在那行留下的“战斗伤疤”。

<details>
<summary>Original English</summary>

**Anekha**: Yeah, well, first of all, thank you to everyone at AIE because it's been such a fantastic experience. And thank you for inviting me on the podcast as well. I'm so excited to just share my experience. And also, I think we're living in such a fast moving time and everyone I speak to is like very overwhelmed. So it's really helpful to be able to kind of share everything that I've had in my experience because I did my undergrad in statistics and math, which is now what everyone calls AI. And so it's really interesting to speak about that and the evolution of that and also to always speak to a former trader as well. And just to share like war scars on that.

</details>

**Host**: 你当时学了金融微积分，比如随机微积分吗？

<details>
<summary>Original English</summary>

**Host**: Did you do financial calculus, like stochastic calculus?

</details>

**Anekha**: 是的，我学过。我的本科学位是华威大学（Warwick）的 MORSE 专业，即数学、运筹学、统计学和经济学。当时大家都会觉得：“天呐，太书呆子气了。”我过去很讨厌告诉别人我的专业。而现在大家都觉得：“哇。”

<details>
<summary>Original English</summary>

**Anekha**: Yeah, I did that. And I so my undergraduate degree was mathematics, operational research, statistics and economics, Morse at Warwick. And it was what everyone was just like, oh, my God, so nerdy. And I hated telling people. And now it's like, wow.

</details>

**Host**: 是啊，现在每个人都在惊呼：“天呐，机器学习，AI。”

<details>
<summary>Original English</summary>

**Host**: Yeah, everyone's like, oh, my God, machine learning, AI.

</details>

**Anekha**: 是的。是的。然后是衍生品。所以我学了那些。我的背景始于英国华威大学，之后我就知道自己想从事交易工作。我不知道你走上交易这条路的故事是什么，但我想要一份快节奏且与数据紧密相关的工作，我极度热爱数据。当我读到交易到底是什么时，我无法想象自己从事任何其他职业。所以我一门心思就想做这个。因此我拿到了投资银行和交易领域的第一份实习，之后在摩根大通（JP Morgan）实习，并在那里开始了全职工作。我最初是在新兴市场交易台，然后转到了大宗商品部门做衍生品交易。所以我职业生涯的大部分时间都在做能源衍生品。

正因为我有数据背景，我总是从想要把市场拆解成各个不同组成部分的角度来看待市场。举个例子，在大宗商品领域，很大程度上取决于基本面、各种新闻以及实际发生的现货情况。所以我一直对从零开始搭建模型非常着迷。因此当我在做交易时，我看到了这种转变：有了数据，接着就会有事情发生。就在那时我离开了摩根大通，实际上是因为我想成为一名创业者和创始人。但我想要做一家数据公司。所以我拿了富布赖特奖学金（Fulbright scholarship）来到美国，因为你们这里有着令人难以置信的风险投资环境。

<details>
<summary>Original English</summary>

**Anekha**: Yeah. Yeah. And then derivatives. So I did that. So my background was started in that at Warwick in England and then knew I wanted to work in trading. I don't know what what your story to go into trading was, but I wanted something which was fast paced and to do with data, like absolutely love data. And it was when I read about what trading was. I could not imagine myself being in any other career. So I was just set on doing that. So I got my first internship in investment banking and trading and then got an internship at JP Morgan where I started. And I started on the emerging markets desk and then moved to commodities and did derivative trading there. So most of my career has been in energy derivatives. And because I have that data background, I always looked at the market from I wanted to break it down into all the different parts. So, for example, in commodities, a lot is about the fundamentals and about the different news and the different the physical happening. And so I was always fascinated by like building out from zero. And so when I was trade trade trading, I saw this shift where it's like a data and then something was going to happen. And that's when I left JP Morgan to to actually I wanted to be an entrepreneur and and a founder. But I wanted to have a data company. So I got the Fulbright scholarship to come to the US because you guys have such an incredible venture.

</details>

**Host**: 就这么轻描淡写地拿了个富布赖特。

<details>
<summary>Original English</summary>

**Host**: Just casually got a Fulbright.

</details>

**Anekha**: 是的，我说来挺逗的，当时我在伦敦上瑜伽课。我父母是做珠宝生意的。在大学期间创立这家公司之前，我还副业做过一个计算机视觉初创项目。所以当时我就想：“珠宝行业有什么痛点呢？噢，比如虚拟试戴。”这让我产生了成为创始人的想法。然后我就想，如何才能在最适合创业的国家成为一名创始人？并且我想成为一名能真正讲清楚技术的创始人。那是在 2020 年、2021 年左右。我发现富布赖特设立了一个数据领域的奖学金，全英国只有一个名额。我当时就想：我来美国的途径就是这个富布赖特奖学金，而他们只给一个名额。这真的很有意思，因为不知你是否还记得 2020 年疫情期间天然气市场陷入疯狂。当时天然气市场有着极其疯狂的波动率。所以在我参加富布赖特面试时，他们问我：“你如何看待未来？”我谈到了全球面临的能源市场危机这一普遍问题，以及数据与此的关系。每个人都能对我的话产生共鸣，因为当时天然气价格疯涨，大家的电费账单也都高得离谱。

这把我带到了美国。来到这里后，我深入参与机器学习研究，与 Stability AI 合作在 ICLR 发表了论文，还与 NASA 开展了合作，做了很多超级有趣的工作，这些最终引导我创立了 Moshi。

<details>
<summary>Original English</summary>

**Anekha**: Yeah, I guess the way I say a funny story, I was doing a yoga class in London. I was like, so my parents have a jewelry business. I side hustled a computer vision startup before my startup at university. And so I was like, oh, what are the problems in the jewelry space? Oh, like virtual try on. So that led to me wanting to be a founder. And I thought, how could I be a founder in the best country to be a founder in? And I thought, what I want to be a founder who can talk about the technology. So this was back in like 2020, 2021. And I found Fulbright had a data scholarship and they gave one in the whole of the UK. So I was like, my way to get here is a Fulbright scholarship and they only give one. And this is really funny because I don't know if you remember 2020 when it was COVID and gas markets were going crazy. So there was there was like gas markets had insane volatility. And so when I did my Fulbright interview, they asked me, how do you like, how do you see the future? And I talked about the like global issue of everyone is having the energy market crisis and how data relates to that. And everyone could relate to what I was talking to because like gas prices were crazy. Their electricity bills were going crazy. And so led me to the US, came here, was deep in machine learning research, published at ICLR with Stability AI, worked in collaboration with NASA, did a lot of a lot of super interesting work, which then led me to Moshi.

</details>

---

### Moshi 的产品定义：大宗商品与能源交易的智能引擎

**Host**: 那么 Moshi 到底是什么？

<details>
<summary>Original English</summary>

**Host**: And what is Moshi?

</details>

**Anekha**: 那么 Moshi 呢，我们正在打造一款我当年做交易时梦寐以求的软件。我们所做的就是为金融交易员提供实时洞察，从大宗商品、能源市场和宏观市场切入。我们处理的数据量超出了人类的处理极限，目的是告诉你此时此刻对你的投资组合最重要的一切信息。

<details>
<summary>Original English</summary>

**Anekha**: So Moshi, we are building the program that I wish I had when I was trading. So what we do is we provide real time insights for financial traders, starting with commodity and energy markets and macro markets. So what we do is we process more data than is humanly possible to tell you everything that matters to your portfolio right now.

</details>

**Host**: 你们会处理什么样的数据？能不能给我们讲讲具体的类型和数量级？

<details>
<summary>Original English</summary>

**Host**: What kind of data would you be processing that give us an idea of maybe types and an order of magnitude?

</details>

**Anekha**: 类型和数量级。让我先从数量级开始说。我常用来向别人解释的一个有趣说法是：我说完这句话需要四秒钟。而在相同的时间里，Moshi 已经学习了 300 件新事物。这就是我们处理的数据吞吐量。

至于数据类型，这在很大程度上源于我对交易方式的极致极客思考。我会把市场拆解为交易员为了决定建什么仓位以及如何管理风险所关注的所有不同类型的数据。因此，我的做法是观察市场并区分：这里有结构化数据和非结构化数据。有期货市场的时间序列数据，以及围绕它展开的所有技术分析。所以我们在观察所有这些统计指标、各种技术指标、所有的移动平均线。这是一套数据集。显然，它在持续不断地更新。

我们关注的下一个数据集是基本面市场的时间序列。特别是在一些大宗商品市场中，存在大量的供需关系。然后我们再看非结构化数据。新闻显然是其中之一。但除此之外，还存在所有这些另类数据（alternative data）。例如，有来自 X 的数据，有播客中的音频数据。

<details>
<summary>Original English</summary>

**Anekha**: Types and order of magnitude. So let me start with order of magnitude. So a fun way I explain it to people is it takes me four seconds to say the sentence to you. And in the same amount of time, Moshi has learned 300 new things. So that's the type of volume of data that we process. In terms of the types of data, this very much comes to me like geeking out about how I would trade. I would break the market up into all the different types of data, which a trader looks at to decide what trade to put on and how to manage the risk. So what I do is I take the market and I say, well, there's structured data and unstructured data. There's the time series of the futures market and there's all of the technical analysis around it. So we're looking at all of this like statistical indicated, all of the different technical indicators, all of the moving averages. That's one data set. And obviously that is updating constantly. The next data set we look at is the time series for fundamentals markets. So especially in some commodity markets, there's a lot of demand and supply. And then we look at the unstructured data. So the news is the obvious one. But then there's also all this alternative data that exists. For example, there's X data. There's audio data on podcasts.

</details>

**Host**: X Twitter。

<details>
<summary>Original English</summary>

**Host**: X Twitter.

</details>

**Anekha**: X Twitter，是的。

<details>
<summary>Original English</summary>

**Anekha**: X Twitter, yes.

</details>

**Host**: 你们会读 Twitter。好的。

<details>
<summary>Original English</summary>

**Host**: You read Twitter. OK.

</details>

**Anekha**: 去理解所有这些不同类型的数据。我会说这是公开可用的数据部分。此外还有一整类完全不同的数据，那就是用户的私有数据。我相信你当年做交易时也有体会：你有你所关注的分析师。我不能跑来命令你说：“嘿，你应该读这个人的报告”，因为你早已有你信任的人选。而且你会有你在意的订阅源。你还会有你的内部数据，对吧？比如我们接触的一些公司，如果他们在交易能源市场，他们会安排专门的人员来统计穿过霍尔木兹海峡的液化天然气（LNG）船只数量。所以存在所有这些对用户而言非常个性化的数据。

我们将这两组数据融合在一起，进行所有的数据清洗和数据转换。随后我们结合统计学和机器学习，给数据打标签，并在其之上构建出我们完整的本体论（ontology）。接着我们将其输入到 Moshi 的高维图谱（n-dimensional graph）中。最后我们生成输出——一个能主动向你推送数据的软件。所以每次你打开 Moshi，都会看到与你的投资组合相关的新动态。你也可以主动拉取数据。大语言模型可以在 30 秒内给你通常需要数天才能得出的答案。

<details>
<summary>Original English</summary>

**Anekha**: So understanding all of these different types of data. And that I would say is the like public availability of data. And there's this whole other type of data, which is the user's private data. So I'm sure you had that when you were trading, which is you have the analysts you care about. I can't come and tell you, hey, you should, you know, read this person because you have who you need. And then you're going to have your subscriptions that you care about. You'll have your internal data, right? Like some of the companies we speak to, if they are trading markets, trading energy markets, they will have their person for the amount of LNG ships going through the Strait of Hormuz. And so there's all this data which is personal to the user. So we take those two data points together, do all of the data cleaning, data transformation. We then look at the statistics and machine learning, tag it, kind of create our whole ontology on top of it. And then we put it into the Moshi, like n-dimensional graph. And then we produce the output, which is a piece of software which pushes data to you. So every time you open Moshi, you see something new related to your portfolio. And you can pull data. So LLM, I'm going to give you answers in 30 seconds, which would take you typically days.

</details>

---

### “新彭博”还是“彭博、Claude 与 Netflix 的结合体”？

**Host**: 那么大家经常称你们为“新彭博”（new Bloomberg）吗？还是说你不同意这个说法，不喜欢被描述为新彭博？

<details>
<summary>Original English</summary>

**Host**: So do people often say new Bloomberg or is that something that you disagree? You don't like being characterized as new Bloomberg?

</details>

**Anekha**: 哈哈，这是个很有意思的问题。因为很显然那是行业中庞然大物般的巨无霸，或者用英国人的说法来形容那个庞然大物。是的，彭博确实有一些特定功能，比如彭博聊天工具（Bloomberg Chat），那是该平台非常出色的一个组成部分。

<details>
<summary>Original English</summary>

**Anekha**: Yeah, that's an interesting question. Because obviously that's the 800 pound gorilla or whatever the British version of saying 800 pound gorilla is. Yeah, you know, I think Bloomberg has certain features, which the Bloomberg chat, it's a fantastic aspect of the platform.

</details>

**Host**: 是的，对于不了解的人来说，交易员以前经常在聊天框里达成数十亿美元的交易。而且有一套标准化的格式。当年我进入自然语言处理（NLP）领域的契机，实际上就是把彭博聊天记录解析成结构化的定价单存入日志。我们就是通过这种方式做期权定价的。

<details>
<summary>Original English</summary>

**Host**: Yeah, for those who don't know, like traders would transact billions of dollars in chat. And there's a standardized formula. When my entry into NLP was actually parsing Bloomberg chat into a structured pricing sheet for my logs. And that's how we did option pricing.

</details>

**Anekha**: 没错，彭博聊天确实是其中一方面。我不会说我们是新彭博。我认为我们是一种不同类型的软件。我觉得最简单的表述方式是——虽然不知道这会有多大争议——如果彭博、Claude 和 Netflix 结合生个孩子……

<details>
<summary>Original English</summary>

**Anekha**: Yeah, there's the Bloomberg chat, which is one thing. I wouldn't say we're a new Bloomberg. I'd say we're a different type of software, which is not. I think this is the easiest way to say it. And I don't know how controversial this is. But if Bloomberg and Claude and Netflix had a baby.

</details>

**Host**: Netflix？你们有视频吗？

<details>
<summary>Original English</summary>

**Host**: Netflix. You have videos?

</details>

**Anekha**: 我们内部自主构建了一套推荐系统（RecSys）。它的逻辑是：如果你是一名交易员，你正在看某一样东西，其实你眼下更关心的是二阶和三阶导数效应（间接影响），而这些是你无法立刻察觉的。

<details>
<summary>Original English</summary>

**Anekha**: Netflix. We actually have a recommendation system, which we've internally built, which is if you're a trader and you're looking at one thing, you actually care about the second and third order derivatives right now, which you wouldn't immediately know.

</details>

**Host**: 我明白了。

<details>
<summary>Original English</summary>

**Host**: I see.

</details>

**Anekha**: 所以我们构建了整套推荐系统。举个简单的例子，回到石油交易员的场景，如果有一家能源股票上市公司采取了某种行动，可能会间接对原油产生影响，你需要立刻知道这件事。你不可能从普通的新闻信息流中获取这种关联。你必须通过一个互联图谱（connected graph）将它展示给你。因为如果这两个信息点此时此刻同时出现，能将它们串联起来的途径，要么靠能够建立关联的人脑，要么靠一个模拟人类判断的推荐系统。这正是我们努力在做的事，因为我做交易时特别希望拥有这样的工具。

<details>
<summary>Original English</summary>

**Anekha**: And so we've built a whole recommendation system where a simple thing, if you're, let's bring it back to like an oil trader, and there's an energy equities company that's doing something which would indirectly impact oil, you need to know that right now. You're not going to get that from like a news stream. You will get that from a connected graph, which is showing that to you. Because if those two information points are coming out right now, the only way you can do it is either a human, which is being able to like connect those, or by a mimicking human, sort of like a recommendation system, which can do that. But that's what we try and do, because I like wish I had that when I was trading.

</details>

---

### 推荐系统（RecSys）在 AI 与交互界面中的核心价值

**Host**: 是的。不过你知道，Netflix 也有让人成瘾的机制，那可能不太好。

<details>
<summary>Original English</summary>

**Host**: Yeah. Well, you know, there's a whole addictiveness element of Netflix, which is bad.

</details>

**Anekha**: 确实有。但这非常有意思。我认为推荐系统（RecSys）是人工智能中最重要的组成部分之一。

<details>
<summary>Original English</summary>

**Anekha**: There is. But yeah, it's very interesting.

</details>

**Host**: 作为 AIE 的策划人，我每年其实都会设一个 LLM + RecSys 的专题分支。但工程师们往往意识不到它有多重要。那个分支的参会人数总是不多，尽管驱动这些系统的人是 YouTube 的推荐负责人，或是负责 Netflix、Instagram 和 TikTok 推荐系统的大牛。结果几乎没人来听。我常想：“搞什么？你们难道对推荐系统不感兴趣吗？”

<details>
<summary>Original English</summary>

**Host**: I think like RecSys is one of the most important parts of AI. And as a curator of AIEs, I actually have every year an LLM RecSys track. And engineers often don't appreciate how important it is. Like it's not very well attended, even though some of the people powering these things, I mean, they run RecSys for YouTube, they run Netflix for Netflix, for Instagram and TikTok. And then like nobody shows up. And I'm like, what do you mean? Like you're not interested in RecSys?

</details>

**Anekha**: 我觉得这真的很有意思。我觉得部分原因在于他们把它表现得好像太简单了，大家会觉得：“噢，这也没什么……”

<details>
<summary>Original English</summary>

**Anekha**: You know, I find it really interesting. I think part of it is they make it seem so easy. And it's like, oh, this is so like...

</details>

**Host**: 但这可是整个公司最重要的系统啊。

<details>
<summary>Original English</summary>

**Host**: This is the most important system in the entire, you know, company.

</details>

**Anekha**: 没错。我认为这还与某些公司（比如 Spotify、Instagram）做得非常出色的一个环节有关。现在随着 AI 的普及，每个人都能搭建自己的 Claude 仪表盘，对吧？大家会说：“嘿，我自己搭了这个。”太棒了。但如果你想让别人也来用它，那只是把你的思维装进了一个仪表盘或工具里。想要让一个新手将其融入他们的工作流程，你面临的就不再仅仅是解决痛点的问题了，你面对的是一个 UI 问题——他们如何与它交互？因为用户有时并不一定会主动去用。这些平台做得极好的一点是，它们会主动向你推送数据，牢牢抓住你的注意力。你不知不觉沉浸在平台上，还会想：“噢，我想看那个。不，我其实更想要那个。”

因此作为一家公司，我们一直在内部努力探索 UI 与推荐系统之间是如何关联的。因为我们的核心假设是：如果你解决了其中一个问题，你自然也在解决另一个。我认为这是当下非常重要的一件事：如果大家都在开发软件，你如何让它成为人们真正愿意使用的软件？这是一个挺有意思的视角。

<details>
<summary>Original English</summary>

**Anekha**: Exactly. And I'd say there's arguably something linked to it, which I think some companies do really well, like Spotify, Instagram, which is one thing that people have come out with AI is everyone now can build their own Claude dashboards, right? It's like, hey, I built this myself. Great. Great. If you want to get someone else to use it, that's your brain in a dashboard or your brain in something. Try and get someone new to incorporate that into their workflow. You're then no longer dealing with a problem. You're dealing with a UI problem, which is how did they interact with it? Because sometimes users don't always use that. One thing that these platforms do really well is they push data to you, which like hooks you. So you naturally don't even realize you're on the platform and you're like, oh, I want that. No, no, I actually want that. And so we've been trying to internally as a company understand how does UI relate to a recommendation system? Because our thesis is if you solve for one, you're naturally also solving for the other. And I think that's a big thing right now, which is if everyone's building software, how do you get it to actually be software that people will use? It's a bit of an interesting take.

</details>

---

### 另类数据的噪音、买方顾虑与私有数据整合

**Host**: 是啊，有点鸡生蛋、蛋生鸡的问题。顺便提一下，我忘了交代我自己的相关背景。我以前其实在伦敦做外汇期权交易，之后在利率部门待过一段时间。有着非常相似的职业轨迹：从欧洲、中东和非洲（EMEA）市场起步，然后转向 G10。至少我们在外汇领域是这么称呼的。在交易中需要吸收海量的信息，而大语言模型在这方面的处理能力显然更强。当年我们在十年前做这些时根本没有这样的工具，但现在我看到它的潜力了。

后来我转向了买方，在买方你开始花钱购买另类数据，正如你所说的那样。当时在 Balyasny，我们其实是极少数最早采购 X（即 Twitter）Firehose 完整数据流的机构之一。

<details>
<summary>Original English</summary>

**Host**: Yeah, a bit of chicken and egg. Well, anyway, I forgot to mention also my background to this. I used to trade currency options in London, actually. And then I spent some time in rates. And it had a very similar career path where you start with EMEA and then you go into maybe G10. Yeah. At least that's what we call it for currencies. And you ingest a lot of information and really probably LLMs can process it better. So we didn't have the tooling back when I did this 10 years ago. But now I see that. And then I moved to the buy side where you start paying for alternative data exactly like you did. We were actually one of the very first few at Balyasny to do the X fire hose or Twitter fire hose.

</details>

**Anekha**: 是的。

<details>
<summary>Original English</summary>

**Anekha**: Yeah.

</details>

**Host**: 那是贵得离谱的玩意儿，为了获取所有推文，每个月得付大概 30 万美元的数据费。

<details>
<summary>Original English</summary>

**Host**: That's something like a stupidly expensive, like $300,000 a month data thing that you have to pay for to get all tweets.

</details>

**Anekha**: 以前曾经是免费的。然后你再去解析它们。

<details>
<summary>Original English</summary>

**Anekha**: It used to be free. And you sort of parse them.

</details>

**Host**: 我不确定它对所有人免费过。

<details>
<summary>Original English</summary>

**Host**: I don't think I don't know if it was ever free.

</details>

**Anekha**: 对研究人员是免费的。

<details>
<summary>Original English</summary>

**Anekha**: It was free for researchers.

</details>

**Host**: 好吧。但如果是对冲基金，就必须买。而且里面的噪音非常大。所以我对此心存疑虑，因为我不知道自己会不会依据那些东西做交易，毕竟有时人们只是在胡说八道。有时甚至有人企图通过发言来操纵市场，而那些很多根本无足轻重。但我们当时也会用卫星图像、信用卡消费等各种另类数据。因此站在买方的角度，我最大的疑问是：“你们在看我的数据吗？”显然大概率没有。但你们如何让客户安心？你们如何与那些你们甚至完全看不到的系统进行集成？

<details>
<summary>Original English</summary>

**Host**: Okay. But then if you're like a hedge fund, like you have to buy that. And it's very noisy. And so my eyes go up because I don't know if I would trade on those things because sometimes people do just talk random crap. And sometimes people try to manipulate markets by saying stuff. And it just doesn't matter that much. But we would also have alternative data like satellite information or credit card information or whatever. And so on the buy side, my number one question is, are you looking at my data? Which is probably not. But how do you assure people? How do you integrate with systems that you don't necessarily even see?

</details>

**Anekha**: 是的。我认为这里面包含两个问题。第一个问题是：如果有如此庞大的可用数据，你如何知道哪些是重要的？因此，当我们分析 X 上的数据时，在我们与客户交流的过程中，或者把范围扩大到任何类型的数据，我们发现大家确实会有他们所信赖的特定对象，他们会关注行业内的这些权威声音，尤其是在大宗商品领域。会有大宗商品供应商、LNG 机构，所有这些设施的相关方都会活跃在上面，因为这是他们同步最新状态最快捷的渠道。

<details>
<summary>Original English</summary>

**Anekha**: Yeah. And I think there's two questions in there, which is the first one is, if there's so much data available, how do you know what's important? So when we're looking at X data, it's a natural conversation when we speak to people or let's even expand it out to any types of data. One thing we found with people is they really will have their trusted people who they'll follow of these voices in industry, especially in commodities. There'll be the suppliers of commodities. There'll be the LNG, all of these facilities who will be active on there because it's the quickest way for them to also give a status update.

</details>

**Host**: 哇。

<details>
<summary>Original English</summary>

**Host**: Wow.

</details>

**Anekha**: 所以这很有意思，因为我们发现很多用户都会向我们提及这一点。这就变成了：“噢，好吧，你把它当作可信来源，是因为你相信这个特定的人。”

<details>
<summary>Original English</summary>

**Anekha**: So it's interesting because we found that a lot of our users will tell us about this. So it's like, oh, OK, so you find it as a trusted source because you believe this certain individual.

</details>

**Host**: 听起来有点靠不住。

<details>
<summary>Original English</summary>

**Host**: Sketchy.

</details>

**Anekha**: 确实。所以我们找到了一种尽可能过滤噪音的方法。但当我们向用户呈现信息时，我们会给出一个置信度分数：比如“某人说了这一件事，但在该讨论周围还发生了这些其他事情”。因为对大家而言，真正有意思的是信源之间是否存在分歧。举个例子，比如此时此刻有多少艘船在航行、有多少架飞机在头顶飞过。如果路透社说了一套，彭博说了一套，《华尔街日报》又说了另一套，他们之间的报道可能并不一致。但他们“观点不一致”这一事实本身就是一项数据点，因为这里面是否存在交易机会？因为没人确切知道真相。这就是我们努力向用户提供信息的方式。

至于第二个问题：客户的数据散落在各处。我认为存在不同类型的集成。第一种是：如何处理他们那些杂乱的 PDF 数据？针对这部分数据，我们自主构建了一个视觉语言模型（Vision-Language Model, VLM）来理解它。我们会接收他们上传到 Moshi 云端版本的数据，然后进行拆解，并在我们的数据库中重新建模。另外有些类型的数据，则必须直接接入他们的系统，那通常需要进一步深入商谈。

<details>
<summary>Original English</summary>

**Anekha**: Right. And so it's one of those things where we have found a way to try and filter out as much as possible. But when we are showing it to someone, we give a confidence score of, OK, someone is saying this one thing, but this is everything else happening around the conversation. Because what's interesting to people is if there are divergent sources, like an example would be how many ships are going, how many planes are going above us right now. If Reuters is saying something or Bloomberg is saying something, a Wall Street Journal is saying something, they may not all agree. But the fact that they don't agree is a point of data because is there an opportunity there? Because no one knows. So that's how we try and give people information. And then the second question is, you know, people's data sits everywhere. And I think there's different types of integration. The first one is what about like their messy PDF data? That data is what we've built is like a vision language model to understand it. So we'll take the data that they can upload to their cloud version of Moshi. And then we actually go and we break it down and then build it up in our database. And there are certain types of data where you just have to connect to their systems. And then that's like more of a conversation.

</details>

---

### 自研模型 vs 现成工具，以及团队技术背景

**Host**: 我假设这个视觉语言模型是你们自己运行的。自主拥有模型到底有多重要？还是说你会考虑外包？我是说市面上有很多供应商，比如 Reducto 就是一个专门做非文档处理的。拥有自研模型与直接使用现成工具相比，重要性如何？

<details>
<summary>Original English</summary>

**Host**: Is it important to, I assume you're running this vision language model yourself, is it important to own that? Or would you want to lay out, I mean, there's any number of vendors, Reducto is like a non-documenting processing one. How important is it to have your own models versus just use whatever's off the shelf?

</details>

**Anekha**: 我认为这是很多公司目前都在权衡的一个问题。对我们而言，首要问题在于：如果有人把他们的数据交给我们，我们不希望把这些数据再发送给第三方。虽然市面上确实有能帮你做这些事情的系统，但你必须确保与他们达成了明确协议：他们如何处理这些数据？他们拿数据来做什么？这是第一个考量。

第二个考量是：如果你手头没有工程团队，那现成方案确实是很好的解决方案。但如果你像我们一样拥有一个强大的工程团队——顺便说个趣事，我们团队的大多数成员都曾以某种身份与 NASA 合作过——那么他们自然会希望亲自构建这些模型。但并不是每个团队都有这样的条件。所以，我觉得这真的取决于团队当前的处境。

<details>
<summary>Original English</summary>

**Anekha**: I think that's a question that a lot of companies are battling with right now. The first question for us is we, if someone's giving us their data, we don't want to be sending it to a third party. Because there are systems out there which can do these things for you. But you want to make sure that you've got that agreement on how are they processing that data? What are they doing with it? That's the first question. The second one is, if you don't have a team of engineers, then that is a great solution. But if you do have a team of engineers like us, a fun fact is most of the team has in some capacity worked with NASA, then they want to build the models. But not everyone has that. And so, you know, I think it really depends like where you are as a team.

</details>

---

### 会议反响、客户拓展与工程师的现实困境

**Host**: 明白了。谈到你的演讲，显然你在演讲后收到了很多业务咨询。这是我们第一次办聚焦金融领域的峰会，所以我之前其实心里没底到底能吸引谁来参会。当然，我们针对金融受众做了非常密集的推介和宣发。你最终都与哪些类型的人交流了？

<details>
<summary>Original English</summary>

**Host**: Yeah, got it. Okay, and then coming into your talk, you apparently had a lot of inbound from it. This is our first finance focused one. So I was genuinely unsure who we could get in the door. Obviously, we like pitch it and market it very heavily for this crew. What kind of people did you end up talking to?

</details>

**Anekha**: 是的，这是一次绝佳的机会，因为我们一直在马不停蹄地跟人开会。超出了我们最初对受众兴趣的预期，就在过去的一个小时里，还有人在 LinkedIn 上给我发私信说：“嘿，我看了你的演讲。你在休斯敦吗？能见个面吗？”或者“你在纽约吗？能约个会吗？”

我们接触到的人群中，有大量来自基金或咨询公司的交易员。另一个有趣的群体是 AI 工程师，因为他们很多人都感受到了来自管理层的巨大压力。

<details>
<summary>Original English</summary>

**Anekha**: Yeah, we, it was a like fantastic opportunity because we have been like back to back speaking to people. And what we initially thought would be the interest, we've had people like, in the past hour messaging me on LinkedIn saying, hey, I saw your court talk. Are you're in Houston? Can we get a meeting? Or hey, are you in New York? Can we get a meeting? The types of people we've had a lot of traders, either at funds, consulting, and then AI engineers was an interesting one, because a lot of them are feeling like overwhelmed with the pressure from management.

</details>

**Host**: 压力来自于要做什么？

<details>
<summary>Original English</summary>

**Host**: To do what?

</details>

**Anekha**: 因为现在的管理层会说：“我们不需要一个团队，你一个人就是团队。”于是就变成了：“天呐，我现在必须一个人把整套系统搭建出来。”但这样的系统通常需要 10 个人来做。所以很多人来找我们聊，他们会说：“嘿，我需要搭一套系统。但是……我是不是得搞个智能体集群（swarm of agents）？要是中途崩溃了怎么办？”

还有一个很有意思的现象：“嘿，我把系统搭好了，大家之前口口声声说需要它。结果系统发到了他们的邮箱里，根本没人去点击。但他们回过头又抱怨说自己被这个问题困扰。我该怎么办？”这是其中一类群体。

另外还有合作伙伴。我们见到了很多人，他们会说：“嘿，你们在做这个啊。有意思，因为我们正好在做这个。会后深入聊聊吧。”

所以我其实延长了在纽约的行程。我原本打算今天就离开的，但现在周四排满了会议，于是多留了一天；周五又排满了，再延期一天；甚至下周一还有会。然后还有人说：“嘿，我们是做能源的，我们在休斯敦聊聊吧。”所以会议结束后我们整整排满了一周的会。

<details>
<summary>Original English</summary>

**Anekha**: Because people now say, we don't need a team, you are the team. And so it's like, hey, I need to now build this whole system myself. But that system would be typically done by 10 people. So a lot of people have talked to us and they're like, hey, I need to build a system. But like, you know, do I need to have a swarm of agents? But then like, what if something breaks? Something interesting is, hey, I built the system. People told me they needed it. It's in their email. No one's, no one's clicking it. But they complain that they have this problem. Like, what do I do? So that was one area. And then partnerships. You know, we've been meeting people and people like, hey, you're doing this. That's interesting, because we're doing this. Let's have a conversation after. So I've actually extended my stay in New York, because we've like now, I was meant to leave today. We've now got meetings on Thursday, extended it another day, Friday, extended it another day, Monday. And then I've got now meetings where people are like, hey, we're in energy. Let's talk in Houston. So we've like filled up a week after the conference of meetings.

</details>

**Host**: 我的天哪。

<details>
<summary>Original English</summary>

**Host**: Oh my god.

</details>

**Anekha**: 是的。我的团队不停跟我说：“Anekha，又有一个人预约了！又有一个人注册了！”所以真的超级酷。

<details>
<summary>Original English</summary>

**Anekha**: Yeah. And my team was like, hey, Anekha, another person signed up. Another person signed up. So it's super cool.

</details>

---

### 会议对接效率与闭门洽谈形式构想

**Host**: 这么逐个做一对一沟通有意思吗？我猜是因为他们需要在私下场合向你咨询。但当你明明可以去拓展业务或打磨产品的时候，安排这么多一对一会议似乎显得非常低效。

<details>
<summary>Original English</summary>

**Host**: Is it interesting to do these one to one? I guess because they need to ask you things in private. It just seems very inefficient to set up so many meetings when you could be doing building a business or building the product.

</details>

**Anekha**: 是的。我们尽量做到提供帮助，我们会先开一次初步会议，但随后的核心目标是理解对方到底在试图解决什么问题，并制定后续计划。由于涌入的咨询量实在太大，我们现在正在采取措施进行精简，比如我们将举办首场网络研讨会（webinar）。我们确实无法一直这样逐个做一对一交流。

<details>
<summary>Original English</summary>

**Anekha**: Yeah. We try and be as helpful to people where we will have an initial meeting, but then really we want to be able to understand what the problem is that you're solving for and then have a plan after that. So we have got things that we're doing now to stream that because like we're hosting our first webinar because of the amount of inbound that we have. We just can't always do these one to ones.

</details>

**Host**: 更普遍的做法是，我当年在买方的时候，投行其实会替我们安排好这类会议。

<details>
<summary>Original English</summary>

**Host**: And so more generally, when I was in the buy side, the banks would actually set up these meetings for us.

</details>

**Anekha**: 是的。

<details>
<summary>Original English</summary>

**Anekha**: Yeah.

</details>

**Host**: 大家会来到像这样的小房间里，搞一个圆桌会，我一次性能见五家。比如假设我是某家公司的首席财务官（CFO），我需要做投资者关系（IR），我一次性面对五家基金，而我就是那五家基金之一。我设想未来我们也可以为你做类似的事情——虽然我目前还没把这项服务落地，但我们完全应该在会议现场举办这些闭门会。大家听了你的演讲，想跟你进一步交流，这很合情合理。他们应该可以现场报名，然后你一次性面对五个客户。而且所有这些问题很可能都大同小异。

<details>
<summary>Original English</summary>

**Host**: And they'd come to little rooms like this. There'd be sort of a round table. I would meet five at once. So like I'd say I'm a CFO of a company and I need to do investor relations. I'm meeting five funds at once and I would be one of the five funds. And I imagine what we could do for you in future, which I haven't, I have not got this off the ground yet, but we should do the meetings on site. Like you've, that makes sense. People like saw your talk. They want to speak more with you. They should be able to sign up and you can do five on one. And probably all these questions are the exact same.

</details>

**Anekha**: 这其实是个非常棒的主意。因为以前在金融圈我们确实经常这么干，这真的是个极佳的切入点。因为我们遇到过这种情况：有时候你甚至不知道要见的人长什么样。

<details>
<summary>Original English</summary>

**Anekha**: And like, that would be a great idea actually, because another, because we used to do this in finance, like that, that is such a good idea. Cause we had one where, um, sometimes you like don't know what the person you're meeting looks like as well.

</details>

**Host**: 好的，所以你得拍照告诉对方你在哪里。

<details>
<summary>Original English</summary>

**Host**: Okay. So you're trying to like take pictures of where you are.

</details>

**Anekha**: 真的！就变成：“嘿，在这儿见，在这儿见”，然后还得打电话。所以像你说的这种模式会非常好。

<details>
<summary>Original English</summary>

**Anekha**: Really? It's like, Hey, meet me here, meet me here and like call them. So an idea like that would be great.

</details>

**Host**: 就像分配一个专门的会议室。

<details>
<summary>Original English</summary>

**Host**: So just like an assigned meeting room.

</details>

**Anekha**: 是的，就说：“嘿，来这里。”

<details>
<summary>Original English</summary>

**Anekha**: Yeah. It's like, Hey, like.

</details>

**Host**: 我的意思是，整个这层楼其实都是用来干这个的，但我们必须提前分配给其他演讲嘉宾。不过我们之前确实想做动态空间分配。我只是不知道该如何具体把它推行起来。我正试着跟你一起琢磨这个方案。这样你就不必大老远飞去休斯敦，甚至对方即使在纽约，你也不用亲自跑去他们的办公室。大家直接聚到这里，开完会，利落搞定。

<details>
<summary>Original English</summary>

**Host**: I mean, this whole floor is that, but we had to pre-assign it to other speakers, but, um, we, we wanted to do some dynamic allocation. I just don't know how to, you know, get that going. I'm trying to fill it out with you. So like, you're not having to like fly to Houston or even like, even if they're in New York, you don't even have to go to their office. Everyone just gets in here, gets their meetings done. You're out.

</details>

**Anekha**: 我真的觉得这个主意太棒了。比如为某个人设定一个 30 分钟的时间段，然后大家现场预约。

<details>
<summary>Original English</summary>

**Anekha**: I actually think that would be a great idea. Like have a 30 minute slot for this person and then like sign up.

</details>

**Host**: 随你挑怎么安排。

<details>
<summary>Original English</summary>

**Host**: Just like whatever you want.

</details>

**Anekha**: 是的，比如小型的一对多闭门会。这想法太棒了，真的。

<details>
<summary>Original English</summary>

**Anekha**: Yeah. Like smaller one, one. That is a great idea. Yeah.

</details>

---

### 会务体验与创业优先级的权衡：招聘 vs 获客

**Host**: 好的。还有什么其他方面是我们能做得更好的，或者这次会议有什么其他体验吗？

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh, I mean anything else that like we, I guess we could do better or like other experiences from the conference that you're,

</details>

**Anekha**: 我觉得这是我参加过的组织得最出色的会议，绝不夸张。我收到的指南质量极高，流程超级清晰，比如讲师接待团队、分会场，还有讲师休息室的配置，我觉得以往的休息室从来没有这么棒过。

<details>
<summary>Original English</summary>

**Anekha**: I think this has been the best organized conference I've been to like, no, no, seriously. Like the amount of good quality guidelines I've had, and it was super clear, like the speaker team, the breakout rooms, um, the speaker lounge having, I feel like the lounge was never this good. Uh,

</details>

**Host**: 是啊，还能理发。

<details>
<summary>Original English</summary>

**Host**: yeah. So haircut.

</details>

**Anekha**: 我知道。我没做面部护理。我做了一个面部护理和一个按摩。

<details>
<summary>Original English</summary>

**Anekha**: I know. I didn't do a facial. I did a facial and a massage.

</details>

**Host**: 是的，我知道你理了发。

<details>
<summary>Original English</summary>

**Host**: Yeah. I know you got your haircut.

</details>

**Anekha**: 我确实理了发。是的。

<details>
<summary>Original English</summary>

**Anekha**: I did get my haircut. Yeah.

</details>

**Host**: 我是说，我们确实很想好好犒劳演讲嘉宾。这次确实有些超规格了，这多亏了 Cognition 的支持。但无论如何，组织工作是一码事，我确实认为就商业价值和效率而言，那是至关重要的因素。我们希望把峰会打造成对你招聘和销售都有实质帮助的平台。我不知道该如何平衡这两点，因为……对你来说招聘和获客哪个更重要？

<details>
<summary>Original English</summary>

**Host**: Um, I, I, I mean, we do want to swallow speakers. Uh, this was definitely, uh, over and above and that's thanks to the cognition for doing that. But, uh, yeah, I mean, uh, organizing is one thing. I do think like in terms of business value and efficiency, I think that's an important, uh, element. Like we want to make this, uh, and you know, something that's useful for you for both hiring and selling, you know, and I don't know how to balance that because yeah, are you even, what's, what's more important to you hiring or selling?

</details>

**Anekha**: 就目前来说，我们刚完成了招聘，并且还在计划继续招人，我们一直在接触候选人，但眼下的头等大事是见客户，获客是当务之急，倒不一定是招聘。因为在招聘方面，我们通过 LinkedIn 就能持续收到大量求职申请。

<details>
<summary>Original English</summary>

**Anekha**: So in terms of we've just hired and we plan to hire, um, we're always meeting people, but the priority right now is to meet clients and that's a priority, not necessarily hiring. Um, because I think what we have with hiring is we get continuous inbound from LinkedIn.

</details>

**Host**: 真的吗？

<details>
<summary>Original English</summary>

**Host**: Really?

</details>

**Anekha**: 是的。我们之前挂出了一个职位，不得不提前关闭。那个岗位只开放了四天，我们就收到了 2,500 份申请。

<details>
<summary>Original English</summary>

**Anekha**: Yeah. I had, we had one job up. We had to close it. It was open for four days. We had 2,500 applicants.

</details>

**Host**: 好的。

<details>
<summary>Original English</summary>

**Host**: Okay.

</details>

**Anekha**: 所以光是处理这些本身就已经非常棘手了。但见那些真正有购买意向的人……因为我认为市场上有些人虽然面临痛点，但他们并没有购买意愿；而有些人既有痛点，又有强烈的购买意愿。要找到精准匹配的目标客户群体——目前我还没见到谁能完美解决这一对接问题。不过我真的非常喜欢你提到的一对多闭门会构想。

<details>
<summary>Original English</summary>

**Anekha**: Um, and so it's like, that's tough to deal with in itself, but meeting people who like want to buy and people who, because I think there's people who have the problem, but they don't want to buy. And there's people who have the problem and want to buy. And then you who are trying to find that match that is, I haven't found any person who's done that. Um, well, but so I really like your one-on-one idea.

</details>

**Host**: 是啊。其实我基本上就是把以前在对冲基金行业积累的经验迁移到如今 AI 与金融结合的这个市场上。明年我们会努力把这种闭门洽谈做成标杆性的环节。

至于在招聘方面——获客这块很明确了，我认为我绝对能在这方面为你提供更好的支持；而在招聘方面，我也希望能帮到你。2,500 份申请确实太多了，而且其中绝大多数都是噪音，你需要更好的筛选机制。

<details>
<summary>Original English</summary>

**Host**: Yeah. Yeah. I mean, so basically I'm, I'm transferring over what I used to have as a hedge fund person to this market, which is AI and finance. Yeah. Um, well, we'll try to do that next year. We'll try to be the definitive thing. Um, and I think on hiring side, so that that's buying and then that's clear. I think, I think I can definitely help you better there. Uh, on the hiring side, I also want to help you. Right. Okay. Like 2,500 is too much and most of it's noise. And so you need a better filter.

</details>

**Anekha**: 对此我有很明确的看法。

<details>
<summary>Original English</summary>

**Anekha**: I have a strong opinion.

</details>

**Host**: 好，请讲。

<details>
<summary>Original English</summary>

**Host**: Okay. Go ahead.

</details>

**Anekha**: 其中有大量的人动机不纯，他们是以一种暗度陈仓的方式来的，不是真正求职，而是来探行情、来当间谍打探商业机密。这种情况比比皆是。还有一部分人是在法律上根本不具备工作资质。所以这其中充斥着太多噪音，比如签证问题等等，围绕这些的杂音非常多。因为我是一个初次创业者，刚起步时，你根本不了解这些门道，不熟悉其中的市场行情。

<details>
<summary>Original English</summary>

**Anekha**: The amount of people who are also doing it in a way where it's like undercover, not it's they're shopping, they're spying. You have that, but you also have, it's that like legally not allowed to work. So there's so much noise in that. It's like visas and there's so much noise around that as well. And so when I was a first time, like I am a first time founder, when I first started, you don't know those things. You don't know the like market.

</details>

**Host**: 没错，与此相关的噪音确实很大。好的，那我们之后会努力为你们提供更高信噪比的服务。我们立志成为一个高信息密度的会议。

我非常感激你能抽出时间和我们交流，祝贺你取得的成功。

<details>
<summary>Original English</summary>

**Host**: Right. And there's a lot of noise related to that. Yeah. Okay. Well, we'll, we'll try to get that higher signal for you. We want to be a high signal conference. Um, I'm just appreciative that you're spending some time with us and congrats on your success.

</details>

**Anekha**: 非常感谢。我有一个问题想问你：你是如何转型投身 AI 领域的？就是突然下定决心开始做的吗？

<details>
<summary>Original English</summary>

**Anekha**: Thank you so much. I'd love, I have one question, which is how you went, you moved into AI. Uh, just, just decided to start.

</details>

**Host**: 嗯，我离开了对冲基金行业，转行进入科技界。当 AI 浪潮爆发时，我意识到自己必须极其迅速地行动，在这个领域确立自己的位置。因此我写了 AI 工程相关的文章，创办了这个峰会，并开展了相关媒体业务，因为从内心深处讲，我本质上是一个非常喜欢做媒体的人。

<details>
<summary>Original English</summary>

**Host**: Uh, well, I, I left, uh, the hedge fund worlds. I moved into tech and then when the AI wave happens, I realized that I better move very, very quickly to, uh, establish this field. And, um, so I did the AI engineering post and, uh, started this, this conference and the media stuff because I'm, I'm very much of a media person. Yeah. Uh, at my heart.

</details>

**Anekha**: 确实是。

<details>
<summary>Original English</summary>

**Anekha**: Yeah.

</details>

**Host**: 我确实有一点想念做交易的日子，但现在的工作非常有成就感，因为我可以接触到鲜活真实的人，而不是整天盯着屏幕。

<details>
<summary>Original English</summary>

**Host**: Um, I do miss trading a little bit, but this is very fulfilling because I get to meet real people instead of stare at a screen all day.

</details>

**Anekha**: 是的，我感同身受。

<details>
<summary>Original English</summary>

**Anekha**: Uh, yeah, I feel the same.

</details>

**Host**: 好的，谢谢。我想我们该收工了。

<details>
<summary>Original English</summary>

**Host**: Well, thank you. I think we have to go.

</details>

**Anekha**: 非常感谢。

<details>
<summary>Original English</summary>

**Anekha**: Thank you so much.

</details>

**Host**: 谢谢。

<details>
<summary>Original English</summary>

**Host**: Thanks.

</details>

**Anekha**: 谢谢。

<details>
<summary>Original English</summary>

**Anekha**: Thanks.

</details>