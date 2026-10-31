---
author: AI Engineer
date: '2026-10-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=L4dUFimVDKU
speaker: AI Engineer
tags:
  - agentic-search
  - backtesting
  - version-control
  - overfitting
title: Exa 智能体网络搜索与快照回测应用介绍
summary: Exa 工程师 Ryan 介绍了其智能体网络搜索能力及其在代码与金融等领域的应用，重点阐述了通过快照功能对历史非结构化网络数据进行版本控制与模型回测，并结合现场比赛强调了防范过拟合与设置保留测试集的重要性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Exa
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/4 -->

### Exa 与智能体网络搜索介绍

>> 大家好。首先，我是 Ryan。我是 Exa 的全栈工程师。非常兴奋能带大家了解这项非常酷的能力。我们基本上很快就会为 AI 智能体带来完美的搜索，但至少现在大家已经可以对它进行版本控制了。今天我要带大家了解几件事。首先，先简单介绍一下什么是 Exa，什么是智能体网络搜索（agentic web search），为什么大家需要关注这个东西？

<details><summary>Original English</summary>

[music]

>> Hello everyone. First of all, I'm Ryan.

I'm a full stack engineer here at Exa.

Very excited to walk you all through

this very cool capability. Um we

basically have perfect search for AI

agents coming soon, but at least now you

can version control it. Um what I'm

going to take you through today is a few

things. So, first off, just a little bit

like what is Exa, what is agentic web

search, why do I even care about this

thing?
</details>

讲完第一点后，大家就会觉得：我需要智能体网络搜索。不管我做不做金融相关的事情，我的项目中都需要它。第二点，好的，我知道自己想要这个东西了，但为什么要在意版本控制呢？讲完第二点后，大家就会明白为什么要在意了。而且这会非常重要，因为在第三点会有一个小小的动手实践环节，大家可能会也可能不会赢得奖品。希望这能激励大家在听第一点和第二点时集中注意力。

<details><summary>Original English</summary>

At the end of point one, you're going to

be like, I need agentic web search. I

need it in my thing, regardless of

you're doing anything financial or not.

Number two, okay, I know I want this

thing, but why do I care about version

control? At the end of number two,

you'll know why you care. And it'll be

very important cuz on number three,

there'll be a little hands-on exercise

where you may or may not win a prize.

Hopefully that motivates you to pay

attention through points one and two.
</details>

所以，我先举手表决一下，以此了解一下情况。请问在座有谁以前听说过 Exa 吗？

<details><summary>Original English</summary>

So, um I'm going to start off a little

bit with like a show of hands just to

situate. So, who here has heard of Exa

before?
</details>

好的，有一些人听说过，但也有几个人没听说过，这很完美。你们当中有多少人在以前的岗位上用过像 Google 这样的搜索引擎来做桌面研究（desktop research）？比如仅仅是在家里、工作中或其他任何地方用 Google 到处搜索东西。希望大多数人都用过，太棒了。最后一部分是，大家现在有多少次不再使用 Google，而是改用 ChatGPT 或 Claude 或其他智能体，然后说“嘿，你能帮我查一下这个东西吗”？如果大家现在会这样做，请举手。

<details><summary>Original English</summary>

Okay, we have a good few people, but a

few people that haven't heard, which is

perfect. How many of you have used like

a search engine like a Google to do

desktop research in a

prior prior role?

Like using Google just to search things

around, at home, at work, whatever.

Hopefully like most people, sweet. Then

the last piece is going to be, hey, how

many times have you now stopped using

Google and instead use ChatGPT or Claude

or some other agent and say, hey, can

you find this thing out for me? Raise

your hands if like now you do that.
</details>

太棒了，非常好。好的，完美。我们要把这三件事串联起来，因为刚才那么多人举手所反映的情况，正是我们现在所看到的。

<details><summary>Original English</summary>

Sweet, great. Okay, perfect. We're going

to tie all of those three things

together because um the exact same thing

that so many people just put their hands

up, that's what we're seeing right now.
</details>

如今 AI 进行搜索的频率其实比人类高得多。为什么？因为它可以处理大量的来回交互，对吧？它可以访问外部，进行多次搜索，找到大家真正想要寻找的内容，可以检索多个页面，并且非常努力地为大家获取所需的答案。我们开始看到越来越多的人正在使用 AI 来搜索，而且 AI 搜索得更多，搜索效率也比人类更高。人类往往有点懒。大家通常会想，好吧，我在找这个东西，我就输几个关键词，希望能出现在第一页，否则我根本不在乎。而 AI 系统，它们非常渴望去满足需求。它们往往非常顺从，不知道大家有没有发现这一点。因此它们会一直搜索，直到找到该内容为止。所有这些因素都意味着搜索量非常庞大。

<details><summary>Original English</summary>

So, AI is actually searching a lot more

than humans do nowadays. Why? Cuz it can

handle so much like back and forth,

right? It can go out, it can do multiple

searches, it can find what you're really

looking for, can search through multiple

pages, and work really hard to get you

the answer you need. And we're starting

seeing way more people are using AI to

search and AI searches more and it

searches more efficiently than humans.

Humans are kind of lazy. You'll be like,

all right, I'm looking for this thing.

I'll put in a few keywords. Hopefully

it's on page one, otherwise I don't

care. Whereas AI systems, they really

want to satisfy. These are the tend to

be quite agreeable. I don't know if you

found that out. And so they'll continue

to searching until they find the thing.

It's like all of these things mean

there's a lot of search.
</details>

而所有那些工具，当你向它提问时，它会觉得：“我需要查阅知识窗口之外的内容，我需要查阅互联网。”它就会使用像 Exa 这样的工具。这就是我们所提供的。所以我们实际上在为世界上一些最大的代码智能体和智能体应用提供搜索服务。每当大家使用 Cursor 时，Cursor 觉得“哎呀，要是我知道文档内容就好了，我就能帮上大忙了”，它就会使用 Exa 外出查找该文档，并将其带回给它的编排智能体（orchestration agent），从而回答问题。或者大家在使用 Gamma 时心想“天哪，要是我知道比如美国银行在 2019 年的财务回报率是多少就好了，这张幻灯片就会很出彩”，它就能利用 Exa 外出找到那项信息。这就是我们的定位。我也顺便简单提一下金融方面，因为这次活动是“华尔街遇上 AI”。希望大家要么从事金融行业，要么对这方面感兴趣。我们在很多这类领域都有合作。这也是我个人特别感兴趣的一个领域。我在这些主题上与一些对冲基金、主权财富基金、资产管理公司和风险投资机构合作，因为他们需要信息。要么他们像对冲基金那样，寻找阿尔法（alpha）来进行财务决策；要么他们是资产管理公司，试图预测风险；要么他们是风险投资机构，想着“噢，我希望把最热门的新初创公司纳入我的储备项目中，我必须赶在 The Verge 或类似媒体发表相关报道之前找到他们”。他们全都利用了 Exa。

<details><summary>Original English</summary>

And all of those tools, when you ask it

a question, it's like,

I need to look outside my knowledge

window. I need to consult the internet.

It will use a tool like Exa.

And that's what we provide. So we

actually provide search for some of the

largest

like coding agents and agentic

applications in the world. So whenever

you're using Cursor, and Cursor's like,

gosh, if only I knew what the docs were,

I could really help. It will use Exa to

go out and find that doc

and bring it back to its orchestration

agent so it can answer the question. Or

you're using Gamma and you're like, gee,

if only I knew like what the financial

returns were of like I don't know, Bank

of America in 2019. This slide would

pop. It's able to use Exa to go out and

find that information. So that's kind of

where we sit. I'm also just going to

like do like a quick thing on finance

cuz this is like Wall Street meets AI.

So hopefully you're either in finance or

you're interested in this. But we work

across a lot of these areas. It's a

particular area of interest to me. I

work with some hedge funds and sovereign

wealth funds and asset managers and VCs

across these topics because they want

information. Either they're like, you

know, hedge fund and they're looking for

alpha to to make financial decisions

against. They're an asset manager,

they're trying to forecast risk. They're

a VC and they're like, oh, I want the

hottest new startup in my pipeline and I

got to find them before like The Verge

or someone like in um um like puts up an

article about it.

They all leverage Exa.
</details>

希望讲完这些之后，大家会觉得，好的，是的，这是一个非常非常有趣的领域。但是，为什么选 Exa？我们到底是做什么的？

<details><summary>Original English</summary>

Um

so

hopefully by the end of this you're

like, okay, yes.

Um this is a really, really interesting

space. But like kind of like why Exa?

Like what do we do?
</details>

### Exa 的核心优势：质量、成本与延迟

我们略有不同之处在于，我们把自身视为一个实验室，在做基础研究以切实推动这一领域向前发展。所以，我将非常快速地谈谈由质量、成本和延迟构成的核心三角，好让大家明白大家确实想要在自己的应用中接入 Exa；然后我们会谈谈版本控制，届时大家就会觉得：“啊，现在我终于能看明白该如何以及在何处使用它来回测我的应用了。”

<details><summary>Original English</summary>

Where we're a little bit different is

that like we we of see ourselves as a

lab and doing fundamental research to

really push this forward. So, I'm going

to touch on like the core triangle of

like quality, cost, and latency really

quick just so you know that you really

want to put Exa in your application, and

then we'll talk about versioning, um

which would be like, "Ah, now I can

actually see how and where this would be

used to back test my application." So,
</details>

首先是质量。大家都希望自己的搜索结果是好的。我们非常在意这一点，以至于构建了自己的可再生基准测试（regenerative benchmark）。为什么要这样做？因为搜索的发展非常迅速。一旦你发布了一个基准测试，所有的搜索提供商以及最终各家实验室就会表示：“我们必须针对它进行训练并攀登高峰。”因此，作为一家真正对自己的产品有信心的搜索引擎，大家真正非常在意的，是希望能创建出用户可以针对自身用例自行构建并保持更新的基准测试，从而让搜索引擎为大家所用，因为大家希望返回最新的信息。这正是大家使用搜索提供商，而不是仅仅向 ChatGPT 或 OpenAI 提问并让其根据权重回答的全部原因。

<details><summary>Original English</summary>

first, quality. You want your results to

be good. We care about that so much that

we built our own regenerative benchmark.

Why do you want to do that? Because

search moves very quickly. You publish a

benchmark and all of the search

um providers and eventually the labs

would be like, "We've got to train on

that and climb the hill." So, what you

really really care about, if you're a

search engine that really believes in

your stuff, is you want to create the uh

you want to create the benchmarks that

people can make for themselves against

their use case and keep it up-to-date so

that your search engine is working for

you because you want to return the

latest information. That's what the

whole uh that's the whole reason why

you're using a search provider and not

just asking uh ChatGPT or OpenAI and

answering from its weights. But, you're
</details>

但大家可能会想：“好吧，我想要质量，但我希望成本最低。”我们不仅在搜索时关注这一点，而且大家知道，搜索涉及大量的 token，而 token 会进入上下文窗口。这意味着什么？大家需要支付输入成本。因此，我们开发了一些技术，试图不仅在单个结果中、而且在所有结果中只返回大家需要的 token，从而让大家的代码智能体或任何应用能够回答问题，而无需在输入 token 成本上花费大笔费用。

<details><summary>Original English</summary>

like, "Okay, I want quality, but I want

it the lowest cost." We care about that

not just at like the search time, but

also, you know, search is a lot of

tokens and tokens goes into a context

window. And what does that mean? You're

paying input costs. So, we developed

technologies to try and return just the

tokens that you need, not just across

one result, but because all the results,

so that your coding agent or whatever

application can answer the question

without having to pay a lot on input

token costs.
</details>

最后是延迟。非常快速地讲一下，它可以做到非常快，所以我们既有亚 300 毫秒级的搜索，一直到比如——我记得我做过一个测试，要求“帮我找出所有的视频游戏发行商”，因为当时我正在尝试做一些评估，它运行了 20 分钟，找到了 3212 家发行商以及与它们合作的开发者。因此在整个光谱范围内，无论大家试图将其实现到架构中的哪一个节点，我们都能满足需求。

<details><summary>Original English</summary>

Lastly, latency. Really quickly, you can

go very fast, so we have like sub-300

millisecond search all the way up to

like, "Hey, work for like

um I think I did one with like, 'Find me

all the video game publishers' cuz I was

trying to do some eval." It worked for

20 minutes and it found 3,212

of them and the developers that they

work with. So, across the full spectrum,

we've got you, no matter what point

you're trying to implement it into your

architecture. And now you're saying,
</details>

### Exa Snapshot 与历史版本检索

现在大家会说：“Ryan，好的，这很棒。我很喜欢 Exa，但我想对它进行版本控制。”或者“我为什么要对它进行版本控制？”这就是今天讨论的重点，来谈谈我们发布的一项名为 Exa Snapshot 的新功能，它允许大家采用我们今天的搜索，但实际上能查看如果在过去某个时间点进行搜索会是什么样子。

<details><summary>Original English</summary>

"Ryan, okay, that's great. I really like

Exa, but I want to version control it."

Or, "Why do I want to version control

it? Um and that's going to be the uh

kind of focus of this discussion today

to talk about this new capability we

released called Exa Snapshot, which

allows you to take our search as it is

today, um but actually see what it would

look like if you searched at a point in

the past.
</details>

我首先会阐明这是什么，然后再解释大家为什么要在意它。首先，这是什么？我们是一家搜索引擎，所以我们花很多时间浏览网络。每当我们发现这些内容时，我们所做的就是将其放入索引中。当我们发现页面的新版本时，甚至当我们只是发现过去的某个日期的同一页面时，我们都会存储该页面的一个版本。这意味着在我们完整索引中的每一个 URL——这是一个包含大约 1000 亿份文档、追踪数万亿个 URL 的全网索引——大家现在都可以回到过去。

<details><summary>Original English</summary>

I'm going to motivate like firstly what

this is and then why you care about it.

So, firstly, what is this? So,

uh we're a search engine, so we spend a

lot of time looking over the web. Uh and

whenever we find this content, what

we've been doing has been putting it

into our index. And when we find like a

new version of the page, or even when we

just discover the same page at a date in

the past, we store a version of that.

Um and that means that like every URL

across our full index, which is an index

of the entire web with um everything

around 100 billion documents tracking

trillions of URLs, uh

you can now go back in time. Um and
</details>

大家可以通过两种方式做到这一点。第一种是比如我知道一个 URL，但我想看看它在过去是什么样子的。为此有内容版本控制（content versioning）。大家可以进入系统，提供一个日期，我们就会向大家展示截至该日期的内容，或者我们记录的该日期之前最近日期的内容。这样大家就可以确保拥有我们在那个时间点会提供的那一版页面。更广泛地讲，大家可以使用版本搜索（version search），这不仅仅是像查找一个 URL 那样，而是执行一次搜索……

<details><summary>Original English</summary>

there's two ways you can do that. The

first one is like I know a URL, but I

want to see what was that like in the

past. Um and there's content versioning

for that. So, you can go in, you can

provide a date, and we will show you the

content as of that date or the nearest

date that we had before. So, you can

guarantee that you have a version of

that page that we would have served at

that time.

More broadly, you can use version

search, which is not just like finding a

URL, but executing a search
</details>

<!-- chunk 2/4 -->

就像你现在会做的那样，只不过是在过去。

<details><summary>Original English</summary>
as you would have done now, but in the past.
</details>

我们来深入看两个非常非常小的相关例子。嗯，然后可以大概感受一下某些用例。首先，假设你对金融市场感兴趣。这里有谁会对金融、金融市场感兴趣呢？嗯，你可能会尝试做的一件事是弄清楚：“嘿，我该怎样了解那些最新、最热门的初创公司？”也许你们听过 OpenAI。最近发生了一些有趣的新闻，嗯，之前 Axios 和其他几家媒体报道了关于 OpenAI 的年化营收，当时有一些说法，比如哦，可能接近 700 亿左右。然后最近又有很多人在讨论到底是 700 亿还是 500 亿？结果发现这涉及到一些会计处理问题，比如到底是毛营收还是净营收，是否把某些云服务提供商的成本转嫁给你，你是否确认该营收？但如果你是一个从事了解这类业务的人，如果你能这样就会非常有帮助：嘿，我想确保我设计的系统能够审视这些东西，对吧？能够比如在你当时本会进行那次搜索、在你本会拥有那个信息的时刻，它是否经过了针对性的调优，从而能够揭示出这个实际上在交易中可能非常有价值的会计附注？

<details><summary>Original English</summary>
Let's like dive into just like two very very small examples around this. Um and then like can kind of give like a vibe of some use cases. So, first one, let's say you're uh interested in financial markets. Who would be interested in financial financial markets around here? Um and one thing you might be trying to do is figure out like, "Hey, how can I understand the hottest and latest startups?" Maybe you guys would have heard of OpenAI. And there was some interesting news happening recently where um previously Axios and a few other people were reporting around uh OpenAI's uh annualized um like revenue and there's ideas like oh it might be up near like sort of 70 billion. And then more recently there's a lot of news about is it 70 billion or 50 billion? Turns out to be some like you know accounting management about whether it's gross revenue or net revenue, whether you're passing through certain cloud providers costs to you, do you recognize that revenue or not? But if you're a person who is in the business of understanding these things, it would be really helpful if you can be like hey I want to make sure that I'm designing a system that is able to look at these things, right? That is able to like at the point where you would have done that search, when you would have had that information, like is it tuned in such a way that it would reveal this like accounting footnote that could actually be very valuable to trade against.
</details>

再假设你在尝试做一些可能可以说更重要或更不重要的事情，那就是去了解针对非常重要的人、或者可能不那么重要的人的负面舆情。比如 Ed Sheeran，他相对不久前就遇到过一些针对他的负面舆情。但如果你回顾那起事件之前一点点的时间，你可以看到：嘿，还有哪些其他事情曾经存在过，或者你知道他不太擅长保险，也许你就不想为他赞助某种保险产品。但这里的重点在于，当你现在处于比如嘿，我可能是一家保险提供商，并且我想要做一些像交易对手尽职调查或 KYB、KYC 之类的事情，或者你在任何企业工作，你正在尝试开展合作，而你的流程的一部分就是了解另一方。如果能够回溯并表示：嘿，我设计了这个系统，让它去进行大量网络搜索，弄清楚这个人是谁、这个企业是什么、他们可以被如何归类、我们是否要针对他们承保。现在你能够设计该系统，然后通过 Hexo 回溯并对其进行测试。嗯。

<details><summary>Original English</summary>
Let's say you're trying to do something arguably even more or less important, which is to understand the adverse media for like very important folks or maybe less important folks. And so like Ed Sheeran he had some like adverse media against him relatively recently. But if you look back a little bit before that event, you can see like hey what are a few other things that existed or you know he was he was not really good at insurance, maybe you wouldn't want to sponsor him for some insurance product. But the main thing here is that like at the point now where you're like hey I'm maybe I'm an insurance provider and I wanted to do some like counterparty due diligence or KYB or KYC or you're working like any business and you're trying to do partnerships and part of your flow is understanding another party. It would be good to be able to go back and be like hey I've designed this system to go out and do a bunch of web search and figure out what this person is, what this business is, how they could be classified, what whether we would insure against them or not. And now you're able to design that system and then with Hexo go back and test it. Um
</details>

### 利用快照进行系统回测

这刚好给出了几个例子，说明快照可以如何以及在何处发挥作用，用来对这些系统进行某种回测。所以，嗯，这里只是其中的一个例子。嗯，顺便说一下，注意到这一点很重要，因为它可能会有助于你稍后取得一些卓越的成果。嗯，但假设你试图了解有关收购公司的事情。你可能会想：“嘿，我正在尝试设计我的系统。如果我现在进行搜索，我可以看到这家公司已经被收购了，但我可能想回到过去并问：‘嘿，那收购前 1 天、收购前 1 周、收购前一个月呢？我能否找到信息来预测这件事？’”因此，任何实时搜索必然都会保持最新。这正是你付费想要得到的东西，对吧？如果你现在进行搜索，你就会获得最新的信息。

<details><summary>Original English</summary>
So that just gives like a few examples of sort of how and where uh, like snapshot can be useful in order to to kind of like backtest these systems. So, um, here's just like an an example of this. Um, as a note, this is important to take in some some awareness of because it may help with uh, you achieving some some some great excellence later. Um, but let's say you're like trying to understand something around like acquiring companies. So, you may be like, "Hey, I'm trying to design my system. If you do a search right now, I could see that this company is already acquired, but I might want to go back in the past and be like, "Hey, what about 1 day before the acquisition, 1 week before the acquisition, a month before the acquisition? Would I be able to find the information to predict that?" So, any live search necessarily is kept up to date. That's what you're kind of paying for, right? That if you did a search now, you'd have the latest information.
</details>

但是，嗯，这也把对未来的认知泄漏到了对过去的评估之中。如果你正在创建一个预测系统，而它所做的只是：“好的，我查看新闻，上面说这起事件已被收购，所以打勾，它被收购了。100% 成功的真正例率。”这是假定搜索功能足够好，而你也希望它足够好。嗯，快照以及这种版本控制搜索的有用之处在于，你可以限制哪些特定信息在哪个时间点被暴露。

<details><summary>Original English</summary>
But, um, that also leaks kind of the future knowledge of that into an evaluation of the past. If you're creating some predictive system, and all it does is goes like, "Okay, I look at the news and it says that this thing was acquired, so tick, it was acquired. 100% successful true positive rate." It's assuming the search is good enough, which you hope it would be. Um, what's what's helpful with with snapshot and and kind of version version control search, you can constrain like what particular information is exposed at which time.
</details>

所以，在这个小例子中，我可以将快照日期设置为比如结果公布之前的时刻。这样我就知道，为这个系统提供信息的唯一依据，嗯，就是实际上不会泄露该事件确切确认信息的内容，对吧？然后你可以对其进行调优以实现不同的功能。比如，也许我有一个非常关注招聘特征。我想确保找到正确的招聘信号。也许我有一个关注分析财报电话会议、录音文稿或 CEO 播客访谈的特征。无论对你来说重要的是什么，嗯，你都能够对该系统进行某种调优，并看看：“嘿，那到底有没有改善我的预测，还是没有改善我的预测？”

<details><summary>Original English</summary>
So, here in this little example, I might set the snapshot date to like just before the outcome was announced. So, I know that the only thing that's going to be informing this system is uh, information that um, doesn't actually leak the exact confirmation of that thing, right? And then you could tune it to do different things. Like, maybe I have a feature that I really care about hiring. I want to make sure I find the right hiring signals. Maybe I have a feature that cares about like analyzing earning calls or or transcripts or or podcast interviews with the CEO. Whatever it is that's important to you, um, you're able to kind of tune that system and see, "Hey, would that have actually improved my prediction or would it not have improved my prediction?"
</details>

### 回测领域的模式演进

我打算分享一下——我在这里只花一点点时间——聊聊我们最近在回测领域看到的几种模式。第一种是围绕传统模型这一概念。这里的思路是，你只是去收集回测现有模型所需的数据。你可以把这理解为：“嘿，也许我有一些系统，它在现实世界中运行。我不需要、我不需要所有那些智能体网络搜索。我喜欢我的系统。它非常棒。”对吧？但可能有一件事是你无法做到的，那就是在今天回过头去收集你在过去所拥有的特征。对吧？有可能是因为它们基于网页，而那些网页根本没有存储一个你可以回溯的版本。

<details><summary>Original English</summary>
I'm going to share just like and I'll spend like a tiny bit of time here but just talking about like a couple of patterns that we've seen in the backtesting space recently. So, the first one is around this idea of like a traditional model. So, the idea is here is you're just going to gather data that you need to backtest the model that you already have. You can kind of think of this is like, "Hey, maybe I have some system and it operates in the world. I don't need I don't need all that agentic web search. I love my system. It's amazing." Right? But maybe one thing that you can't do is actually go back and gather the features that you had in the past today. Right? Could be that they're based on web pages and those web pages just don't store a version that you can go back to.
</details>

也可能是你想拥有一种获取报纸页面或其他文章的系统，而你无法真正信任发布日期。这里稍微扯开一点，但文章的发布日期实际上一直在更新。既有因为“嘿，我们确实更新了内容”，一直到“嘿，搜索引擎优化非常喜欢最新的文章。所以，我们干脆再更新它一次”。

<details><summary>Original English</summary>
It could be that you're trying to have some sort of system that like takes like newspaper pages or some other articles and you can't really trust the publish date. Very small digression here but like publish dates of articles actually update all of the time. Both for like hey, like we've legitimately updated it all the way down to like hey, like SEO really likes up-to-date articles. So, maybe we just like update it one more time.
</details>

因此，这意味着你无法真正信任发布日期特征，而这非常重要，尤其是当你基于此做出相当重大的决策时，你必须能够信任那个特征到底是什么。所以，你可能就会决定：“嘿，我要使用快照。我知道一些我关心的 URL 或网站。我要回溯过去，仅仅收集我需要的数据，然后将其放入我需要的任何特征中，比如某个数字数组等。”X 甚至不参与预测，但这是一种完全有效且相对直接的方式，你可能已经在利用某些版本数据来回测你的系统了。

<details><summary>Original English</summary>
So, that means that like you can't really trust that like publish date feature feature and is really important especially if you're making quite like substantial decisions around this that you're able to trust what that feature is. So, you may just decide, "Hey, I'm going to use snapshot. I know some URLs or some websites that I care about. I'm going to like jump back and just gather the data that I need and then put it in whatever feature I need, some array of numbers etc." X is not even involved in the prediction but this is like a perfectly valid and like relatively straightforward way that you might already be using some kinds of version data to backtest your system.
</details>

好，这就是现有的领域。

<details><summary>Original English</summary>
Okay, that's the that's the existing space.
</details>

嗯，那么未来呢？完美搜索的未来。好的，这里有两种模式。

<details><summary>Original English</summary>
Um what about the future? The future of perfect search. Okay, so there's two sort of patterns here.
</details>

第一种就像是：我要在传统模型中添加一个智能体特征。这与我们之前讨论的有些类似，但其思路是在线上实时模型中，它实际上将使用 X 或类似 X 的工具去搜索网络，将所有非结构化信息转化为结构化信号，然后针对其进行交易。所以你可以想想类似于之前针对我们朋友 Ed Sheeran 的负面舆情扫描。嗯，你可能正在设计你的系统以便能够进行一些交易对手尽职调查，嗯，而在实际生产系统中，那可能只是其中一个分支，对吧？该系统本身可能没有任何智能体代理能力，它只是去收集一堆特征，然后也许你训练了一个模型，嗯，就像一个传统的机器学习模型，用来判断比如是的，我们要投资，或者不，我们不投资。你可以回过头去，利用 X 对那些智能体特征逐个进行回测，比如针对真正例匹配，其中发生了某些……嗯，比如

<details><summary>Original English</summary>
The first one is like I'm going to add an agentic feature to a traditional model. It's kind of similar to what we were talking about before, but the idea is in the live model, it's actually going to be using X or to like X to go out, search the web, turn all of that unstructured information into a structured signal, and then trade against it. So you could think about something like the adverse media scan like against our friend Ed Sheeran before. Um you you might be designing your system to be able to do some like counterparty due diligence, um and in the live production system, that might just be like one arm, right? It's uh the system itself may not have any agency, it's just going to collect a bunch of features, and then maybe you've like trained a model um um just like a traditional ML model to say like yes, we're going to invest, or no, we're not going to invest. You can uh go back and back test those agentic features one by one with X or and be like hey, uh against like a true positive match where something um like
</details>

>> [清喉咙]

<details><summary>Original English</summary>
>> [clears throat]
</details>

>> 要么比如我不知道，你关心的那件事发生了，要么比如那个企业成功了，或者它没有成功，你可以进行测试并看看我们是否能够正确预测它，嗯，或者我们没有预测对？而最

<details><summary>Original English</summary>
>> either like I don't know, the the the the thing that you care about happened, either like that business succeeded or it didn't succeed, you can test and be like were we able to correctly predict that, um or did we not? And most
</details>

<!-- chunk 3/4 -->

重要的一点是，你随后可以去调优那个系统。因为对于所有这些非确定性系统来说，调优它们的方式真的非常、非常关键。所以，如果你调优让它以某种方式进行搜索，它或许能更频繁地取得成功。如果你选择换一种方式搜索，成功的频率就会降低。你可以控制那个实验，然后像一次一个特征那样，把它加入到你的系统中。

<details><summary>Original English</summary>
importantly, you can then tune that system. Because the way that with all of these non-deterministic systems, the way that you tune them is like really really important. So if you tune it to search a certain way, maybe it succeeds more often. If you choose to search another way, succeeds less often. And that is you can control that experiment and then add it into your system like one feature at a time.
</details>

然后，在最右侧，设想是未来会存在这样一种可能：有一些预测类的初创公司以及其他参与者在运转，其中整个系统可能完全是智能体化的（agentic）。系统本身可能会、也可能不会选择通过某种工具调用去搜索网络。

<details><summary>Original English</summary>
Um then like uh on the far would be right hand side, the idea is like there's this like future where there's some like predictions, startups, and other folks operating where potentially like the full system is agentic. Um so the system itself may or may not choose to search the web through some tool call.
</details>

它可能会结合内部知识，也可能会结合结构化的外部知识。它可以在运行时做这些事情。核心思想是：“这有点像人类外出做某些预测时的行为。他们具备一定的主观能动性，会去搜索这个或搜索那个。”基本上，你可以为你模型的这个接口提供外部世界的现实依据（grounding）。然后，你能够确保该系统在运行之时，仅仅能够检索其当时所掌握的信息。

<details><summary>Original English</summary>
Um it could be uh combining internal knowledge. It could be combining like structured external knowledge. And it can kind of do that at run time. The idea is be like, "Hey, this is kind of what humans do when they go out and do some prediction. They have some agency. They're going to search for this or search for that." And essentially you can ground that uh like interface for your model into the outside world into the outside world. And then you can uh ensure that when that system was operating, it was able to search um only the information that it had at that time.
</details>

这里有一个实际的例子：假设你正试图改进你的编程模型。该编程模型的一部分衡量标准，就是看它能否解决一个 PR。你大可以这样：“我要在那个 PR 于外部代码仓库被合并解决之前那一刻进行冻结，然后让系统运行。随后，如果它能够解决该任务，你就能更有把握地确信，这是模型权重——或者系统里你真金白银花钱通过训练过程来改进的任何组件——所带来的改变，而不是未来的信息泄露到了当下。”

<details><summary>Original English</summary>
So one like practical example of this is like let's say you're trying to improve your coding model. And hey, one part of that coding model would be uh whether it can solve a PR or not. You could be like, "Hey, I'm going to freeze right before that PR was solved uh in an in an external repo and then let the system run. And then hopefully, if it's able to resolve the task, you can have more confidence that that's a change in the model weights or whatever component in the system that you're actually paying to improve through your training process, then it is just like future information sort of like leaking into the current.
</details>

### 工作坊动手实操

好了。以上就是对快照（snapshot）以及用它来进行回测的几种方式的一个简要概述。我先概括一下我们目前看到的内容。首先，我们非常喜欢 Exa。为什么喜欢 Exa？因为它搜索非常出色。而搜索对模型而言至关重要，因为它们需要了解当下，而且质量必须很高，必须具有成本效益，并且延迟要在系统合理的范围之内。

<details><summary>Original English</summary>
Okay. So that's just like a little bit of like an overview of like snapshot and a few of the ways that it's being used to backtest. I'm just going to like uh recap what we've seen so far. So first, we really like Exa. Why do we like Exa? Because it's very good search. And search is very important for models because they need to know about uh the current uh and it needs to be high quality. It needs to be like uh cost effective. And it needs to be at the latency that makes sense for my system.
</details>

好了，这些我们都已经了解了。然后我们会想：“嘿，我真的很需要这个。而将其接入我的模型中，很大一部分关键在于能够对其进行版本控制，这样我才能证明它增加了价值，而不是仅仅凭感觉和希望它增加了价值。”现在我们要进行的是本次工作坊中有趣的部分，那就是我们要给各位留出时间，让大家亲自上手体验这个工具。屏幕上有一个小二维码，大家可以用手机扫一扫。你也可以直接把这个小网址输入电脑，笔记本电脑上的界面操作起来可能会更顺手一些。

<details><summary>Original English</summary>
Okay, we've all learned that. And then we're like, "Hey, I really want that. And a big part about putting that into my model is being able to version control it so I can prove that it adds value, not just like vibes and hope that it adds value. Um what we're going to do now is like the fun part of this workshop, which is we're going to give you all time to kind of go hands-on with this tool. So, there's a little QR code on the screen, you can scan it with a mobile. You can also just like enter this [clears throat] little URL into your computer and the uh interface on your laptop will probably be uh more amenable.
</details>

然后，我稍微给大家介绍一下我们在这里要做的事情。思路是这样的，回想一下我们之前的例子，你们将尝试去预测公司在被收购发生之前的收购情况。这里简单讲个情景故事：假设你在某家金融机构工作，你上司的上司的上司的上司去参加了某个 AI 工程师工作坊，然后他们说：“嘿，我听说了这个非常非常酷的网络搜索功能。我觉得我们应该向我们的投资组合经理展示一下。”投资组合经理回答说：“行，我想看看。给你 20 分钟时间。尽量把它做好。”

<details><summary>Original English</summary>
Um and then I'm just going to give you like a little bit of an overview about what we're trying to do here. So, the idea is, if you think back to the example that we had before, um you're going to be trying to uh predict like what are company acquisitions right before they happen. Um to tell like a little bit of the story here. So, let's assume that you're working in some financial institution. Uh your boss's boss's boss's boss like went to some AI engineer workshop and they're like, "Hey, I heard this like really, really cool web search feature. I think we should present it to our portfolio manager." And portfolio manager's like, "Okay, I want to see it. You've got 20 minutes. Um try and see if you can make it good."
</details>

而这里最棘手的混杂变量在于，你手头没有编程智能体可用。所以你必须手动来做，因为你的额度刚刚用完了之类的。这就是我们目前所处的背景情境。

<details><summary>Original English</summary>
Um and the most confounding variable here is you don't have like a coding agent. So, you have to do it by hand because your usage just ran out or something. Um so, that's the kind of context of where we're sitting ourselves at.
</details>

你的任务是找出能够准确预测公司收购的最佳两个特征。然后，Exa 的快照将使用这些特征倒流回收购发生前的 1 天、7 天和 30 天，来测试你的特征；或者如果该公司没有被收购，就取一个随机日期，所以其中包含了一些起混杂干扰作用的案例。

<details><summary>Original English</summary>
Your task is going to be to find the best two features that like accurately predict a company acquisition. Uh and then Access Snapshot is going to use that to go back in time uh 1 day, 7 days, and 30 days before the acquisition and test your feature. Um or a random date if they weren't acquired, so there's a few confounding ones in there.
</details>

所谓“特征”，就是一个你认为可以预测收购的“是/否”问题。你可以随意测试任意多个问题，系统里有几个示例，我会在大家周围走动，和大家聊聊，沿途给大家提供帮助。你可以随心所欲测试很多个。

<details><summary>Original English</summary>
Um feature is just like a yes/no question um that you believe would predict an acquisition. You can test as many as you like, there's a few examples in there, and I'm going to be coming around just to talk with you all um and kind of like help you along the way. Um and you can test as many as you like.
</details>

计分规则方面：如果你的特征判定这家公司在被收购前 1 天、7 天、30 天（170 30 天）会被收购，得加 1 分。如果你判定它被收购了、但实际并没有被收购，得扣 1 分。对于未命中或放弃不判断的情况，则没有任何分值影响，因为我们很宽容友好。系统会自动记录最佳得分，你想尝试多少次都可以。我给大家预留——姑且说是 30 分钟。

<details><summary>Original English</summary>
Scoring, you get plus one point if you uh uh if your feature declares that this company would be an acquired uh on 170 30 days before it did. You get minus one if you say that it got acquired, uh but it didn't. And then, no impact for misses or passes cuz we're very friendly. Best score automatically captured, you can try as many as you want. I'm going to set us up for let's say like 30 minutes.
</details>

所以，我们现在正式开始。你们有 30 分钟的时间来尝试输入你们认为绝对最好的特征。我会在场地里走动。或许我们可以放一点舒缓的音乐，给大家营造一种置身于投资组合管理公司、听着低保真音乐（low-fi beats）工作的氛围。我会走动并与各位交流。

<details><summary>Original English</summary>
Um so uh we'll kick that off now. And you have 30 minutes to try and put in the absolute best feature that you want. I'll be coming around. Maybe we can put on like a little bit of soft music that kind of gives people the vibe of working in [music] a portfolio manager company uh and listening to like low-fi beats. Uh and I'll come around and talk with you all.
</details>

好，我快速演示一个简单的例子，让大家了解一下它的运行机制。如果你已经开始上手并且进展顺利，请随时继续深挖。不过我还是在这里演示一个例子。大家会看到眼前的这个界面，上面会有一系列选项，它会要求你输入一个新特征。你可以选择现成的示例之一，也可以输入任何你想要的内容，然后点击运行。

<details><summary>Original English</summary>
Okay, I'm just going to do like one like real quick example just to kind of show people how it works. If you're already going away and and and winning, keep feel free to keep grinding. Um but I'm just going to put one example in here. So, you'll see this interface in front of you. You have a bunch of um it'll ask you to put in a new feature. You can pick one of the examples or type whatever you want and hit run.
</details>

它所做的是调用 Exa 的快照功能去搜索很多内容。这个执行得很快，因为它是缓存过的，这算是一种性能优化，也向大家证明我们事先确实测试过。但它会向下执行，针对这组包含 10 家公司的集合来运行查询。在这组公司中，有些确实被收购了，有些则没有被收购，它们属于混杂变量。

<details><summary>Original English</summary>
Um and what it'll do is it'll go out, it'll use excess snapshot and search a bunch of them. This one was fast because it was cached, so uh that's a performance improvement to show you that we did test this beforehand. Um but it'll go down and it'll run that against this set of 10 companies. So, within this set of companies, some of them were acquired. Some of them were not acquired. They're confounding variables.
</details>

这里的核心做法是，我们将采用这个具体的查询，比如“这家公司是否失去了 CEO 或 CFO，或者任命了临时领导层”。针对所有这些公司，我们将返回去执行版本化搜索。对于 Delivery Hero，我们可以看到：“看，曾出现过执行领导层变动。答案是‘是’。”而且该公司最终确实被收购了。所以，看，这或许具有预测性。

<details><summary>Original English</summary>
Um and the idea is that like we're going to take this particular query, so has this company lost its CEO or CFO or appointed interim leadership. And for all of this, we're going to go back and do that version search. So, Delivery Hero, we can see, "Hey, um there was an executive leadership turnover. Yes." And the company did end up being acquired. So, hey, maybe this is predictive.
</details>

然而，Quagen——我不知道我的发音准不准——他们也经历过高管领导层变动，但他们最终并没有被收购。噢，糟糕，这就是一个混杂变量。所以，你们的任务是去尝试：“我能向其中添加哪一个或两个最具预测性的特征？”这里我打算再添加一个。

<details><summary>Original English</summary>
Except, Quagen, I don't know if I'm pronouncing that correctly, they also had like executive leadership turnover, but they didn't end up being acquired. Oh, no, that's a confounding variable. So, your task is to try and be like, "Hey, what are the one or two features that I can add to this that will be the most predictive?" So, here I'm going to like add one more.
</details>

比如这个是：“该公司是否有被报道正在寻求出售？”添加这一条会让效果更好还是更差？在这种情况下，你可以看到：“看，我们命中了许多收购案例，所以就发现目标而言我们做得相当不错；但同时，我们也触发了很多误报。”因此，我们在组合这两个特征的方式上可能需要施加更多约束。

<details><summary>Original English</summary>
So, this one is like, "Hey, has it been reported to be exploring a sale?" Does adding that improve it or make it worse? And in this case, you can see, "Hey, we've picked up a lot of the um uh we've picked up like a lot of the acquisitions, so we're doing pretty well in terms of finding stuff, but also like, "Hey, we're picking up like a lot of false alarms here." So, we might need to be more uh constraining in the way that we're combining these two features.
</details>

在这里我设置了一个非常简单的组合逻辑。你可以选择“或（OR）”，即如果你的两个特征中任何一个触发为“是”，我们就会将整条判定视为：“是的，你预测它截至当天将被收购。”你也可以选择“与（AND）”；如果我在这里切成“与”，得分会稍微有所提高，这意味着这两个特征必须同时为真。

<details><summary>Original English</summary>
So, here I've put a very simple like combined thing. You can either choose or, which is if either of your two features trigger yes, then we will count that whole thing as being like, "Yeah, you're predicting that it is going to be acquired as of that day." You can go and, and if I see if I go and here, the score improves a little bit, which means both of these two features need to be true.
</details>

如果对于该公司的当天情况，这两个特征同时为真，那么就会触发“是”。这只是一点友情提示。我会切回排行榜界面，在我们走动期间，有任何问题请随时举手。

<details><summary>Original English</summary>
And if both of those two features are true for that company on that day, then you'll trigger yes. Um that's just like a PSA. I'll go back to the kind of like leadership board there, but feel free to chuck up your hands with any questions as we come through.
</details>

好，还剩 10 秒钟。如果你还没有点击运行，它可能……

<details><summary>Original English</summary>
Okay, 10 seconds left. If you haven't already hit run, it may
</details>

<!-- chunk 4/4 -->

为时过晚。

<details><summary>Original English</summary>
be too late.
</details>

大家可以随意查看合并后的结果，或者抓紧提交最后几项结果。

<details><summary>Original English</summary>
Feel free to nobble over the combined and or to try and get your last few results.
</details>

呼。好了，祝贺大家。那么，Zane、John 还有 Ree，如果你获奖了，能上台来找我吗？如果不在，我们就顺着名单往下找。

<details><summary>Original English</summary>
Phew. Okay, congratulations. So, Zane, John, and Ree, could you come and join me on stage if you won a prize? If not, we'll go further down in the list.
</details>

能给他们热烈的掌声吗？

<details><summary>Original English</summary>
Can we have a big round of applause?
</details>

上来吧，别害羞。别害羞。

<details><summary>Original English</summary>
Come up, don't be shy. Don't be shy.
</details>

精美的奖品和盲盒等着你们。

<details><summary>Original English</summary>
Brilliant goods and mystery boxes await you.
</details>

嘿，恭喜。

<details><summary>Original English</summary>
Hey, congratulations.
</details>

恭喜，John。非常有价值的土地。

<details><summary>Original English</summary>
Congratulations, John. Very valuable land.
</details>

嘿，恭喜。

<details><summary>Original English</summary>
Hey, congratulations.
</details>

额，好的，我来把这些发下去。

<details><summary>Original English</summary>
Um so, yeah, let me hand these out.
</details>

>> 谢谢

<details><summary>Original English</summary>
>> Thank
</details>

你们排好队站漂亮点，我们好拍张合照。

<details><summary>Original English</summary>
You're going to line up brilliantly so we can do a photo.
</details>

好的，我们稍后会从那段视频里截一张静止画面。那么，让我们来翻翻看，八卦一下，看看我们的第一名做了什么。那么，Zane——

<details><summary>Original English</summary>
Okay, we'll take a still out of that video later. So, let's just like poke around and be nosy and see like what did our number one person did. So, Zane
</details>

这家公司是上市公司吗？非常有趣的特征。

<details><summary>Original English</summary>
Is this company a publicly listed company? Very interesting feature.
</details>

第二，这家公司是否不是 Qiagen、Vitris、Bank of Cryptos 和 American Electric Power 这几家公司之一？

<details><summary>Original English</summary>
Number two, is this company a company other than Qiagen, Vitris, Bank of Cryptos, and American Electric Power?
</details>

恭喜。

<details><summary>Original English</summary>
Congratulations.
</details>

你就是我想设置保留测试集的原因

<details><summary>Original English</summary>
You are the reason why I wanted to have a holdout
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 我去掉了它，是因为我想保持简单，但这是一个很好的例子，说明了为什么你需要做回测，以及为什么你需要用保留测试集来做回测。额，所以，我打算把没放保留集当作一个特性，而不是一个缺陷，

<details><summary>Original English</summary>
>> I removed it because I wanted it to be simple, but this is a good example of why you need to do backtesting and why you need to do backtesting with a holdout set. Um so, I'm going to take this as a feature, not a bug,
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 这说明了为什么过拟合非常危险，因为我认为这个特定的算法在未来不会成功，但谁知道呢？

<details><summary>Original English</summary>
>> of not including a holdout set and why overfitting is very dangerous because I do not think that this particular algorithm would be successful in the future, but who knows?
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 第二名，Ree。所以，好吧，他抄了 Zane 的。[笑声] 也许之前是坐附近的。最后是 John。在过去的 12 个月里，是否有积极投资者或大股东公开呼吁全盘出售公司，或者该公司目前的股价是否比过去 5 年的高位至少低 60%，或者它的名字叫 Dominion？这里也有点过拟合，但我认为它的表现可能更好。

<details><summary>Original English</summary>
>> Number two, Ree. So, okay, he stole Zane. [laughter] Maybe it would have been seated nearby. And lastly, with John. So, within the past 12 months, has an active investor or significant shareholder publicly called for a supported sale of companies as a whole or is company's current share price at least 60% below its high price during the past 5 years or is it named Dominion? Also, a little bit of overfitting there, but I would argue it probably performed better.
</details>

额，所以这就给出了一个例子，说明为什么做回测很重要，对吧？因为大家知道，这是一个小范围受限的例子。我感觉我有点后悔去掉了保留测试集，虽然如果我真放了，大家可能会困惑得多。

<details><summary>Original English</summary>
Um so, this gives like an example of just like hey, how and why it's important to do backtesting, right? Because, you know, this is like a little constrained example. I I feel like I'm regretting removing my holdout set, although I do feel like people would have been way more confused if I did do that.
</details>

额，

<details><summary>Original English</summary>
Um
</details>

但是，

<details><summary>Original English</summary>
but
</details>

这能让大家明白它为什么有价值，对吧？因为如果你知道现有的数据集是什么，你就可以过拟合它，但理念是，正因为你具备这种能力，你就可以去核查这一点，对吧？你可以回过头来说：“嘿，我要回头翻翻我的记录，比如把我知道发生过某事的这 10 家公司和没发生过的 20 家公司圈出来，来训练和迭代我的模型，对吧？”并确保它在公开可见的数据集之外依然能持续表现良好。

<details><summary>Original English</summary>
this gives you an idea of like why it's valuable, right? Because if you know what the existing set is, you can you can overfit it, but the idea is like because you have this capability, you can check for that, right? You can go back and be like, "Hey, I'm going to go back in my book and be like, hey, I'm going to constrain like these 10 companies that I know something had happened to them, 20 companies that didn't, and train and iterate on my model, right?" And make sure that it continues to perform beyond just like the publicly visible sets.
</details>

额，那么我们来回顾一下重点。我还要——

<details><summary>Original English</summary>
Um so, let's like recap the highlights. I'm also going to
</details>

天哪，这里有好多人。我得往后翻很长一段。我要把大家的名字都放到一个——额，致谢页面上。我现在应该已经在致谢页面上了。在致谢页面上，有一个通往我们文档的链接。我们非常重视文档。还有一个通往我们博客的链接。它比文档更好读，

<details><summary>Original English</summary>
Oh my god, there's a lot of people in here. I have to scroll very far. I'm going to put you all on a uh thank you page. I should already be on the thank you page. On the thank you page, you've got a link to our docs. We love documentation. You have a link to our blog. It's more readable than the docs
</details>

>> [嗤笑]

<details><summary>Original English</summary>
>> [snorts]
</details>

>> 而且更通俗易懂。额，最后，还有一个可以给我发邮件的途径。我现在真的很后悔放这个，因为房间里有 100 个人，所以我预计会收到很多邮件。额，不过这也是一项企业级功能。我们有一些公开使用配额，但如果您有兴趣为团队获取使用权限，请给我发邮件，我会帮您联系我们的企业团队。额，我们来总结一下重点。第一，我们喜欢 Exa。为什么？因为它具备出色的智能体网络搜索能力。它物超所值。非常划算。它能满足我所需的任何延迟水平。我想在自己的模型中用到它。第二，snapshot。它让我可以回测我的模型。它能让我看到 Exa 在改进模型方面究竟有多出色。第三，额，真的考虑一下在比赛中加上保留测试集，否则你可能会过拟合。谢谢大家。

<details><summary>Original English</summary>
>> and is more like human-facing. Uh and lastly, there's a chance to send me an email. I really regret that now because there are 100 people in the room, so I'm expecting a lot of emails. Um but this is an enterprise feature as well. We have some public usage, but if you're interested in having access to this for your team, send me an email and I'll connect you to our enterprise team. Um let's just like recap the highlights. Number one, we love Exa. Why? Because it's great agentic web search. It's good value. It's very cost-effective. It's at whatever latency I need. I want it in my model. Number two, snapshot. It lets me backtest my model. It lets me see just how good Exa is at improving your model. And number three, um consider really adding the holdout set to your competition because otherwise you may overfit. Thank you, everyone.
</details>