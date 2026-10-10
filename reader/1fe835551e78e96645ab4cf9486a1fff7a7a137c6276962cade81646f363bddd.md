---
author: Bloomberg Podcasts
date: '2026-06-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=OhTTEtcCdB4
speaker: Bloomberg Podcasts
tags:
  - vibe-coding
  - data-transparency
  - market-benchmark
  - niche-market
  - commodity-pricing
title: Odd Lots：19岁大学生用AI重塑干草市场，打造草料界的彭博社
summary: 彭博社Odd Lots播客采访了年仅20岁的Haywire创始人Aiden Johnson。他利用AI技术，将零散的美国农业部数据和地方拍卖数据整合，为缺乏透明度的干草市场提供价格基准。对话探讨了AI（尤其是Vibe Coding）如何降低创业门槛，解锁以往难以变现的长尾数据市场，以及极端天气对农业大宗商品价格波动的影响。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Aiden Johnson
companies_orgs:
  - Haywire
  - Bloomberg
  - USDA
products_models: []
media_books: []
status: evergreen
---
### 从Reddit发现的干草市场

**Tracy Aloway**: 大家好，欢迎收听新一期的 **Odd Thoughts** 播客。我是 **Tracy Aloway**。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Hello and welcome to another episode of the Odd Thoughts podcast. I'm Tracy Aloway.

</details>

**Joe Weisenthal**: 我是 **Joe Weisenthal**。Joe，我最近在 Reddit 的 Homestead（家园）版块潜水，就像人们平常做的那样。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: and I'm Joe Wisenthal. Joe, I was uh lurking on the Homestead subreddit recently, [laughter] as one does, and

</details>

**Tracy Aloway**: 就像 Tracy 平常做的那样。最近有许多关于干草价格以及干草变得越来越贵的帖子。最疯狂的是有一个家伙，有一个发帖人一直在谈论干草价格。在其中一个帖子里，有人进来评论说，“你应该上 All Thoughts（节目）”。

<details>
<summary>Original English</summary>

**Tracy Aloway**: as one, as Tracy does, um there have been a number of posts recently about hay prices and hay getting more expensive. And the craziest thing is there's one guy, one poster who keeps talking about hay prices. And on one of his posts, someone came in and said, they commented, "You should go on All Thoughts."

</details>

**Joe Weisenthal**: 我喜欢以这种方式诞生的节目。好吧，我能在这里坦白一件事吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: [laughter] I love episodes that come about that way. All right. Can I make a little confession here?

</details>

**Tracy Aloway**: 请说。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Please.

</details>

**Joe Weisenthal**: 我对这期节目完全没有做功课。我的意思是，我通常不如你那么勤奋，但我当时就想，你知道吗？我知道干草是存在的。我见过一捆捆的干草。我想它应该是风干的东西。我知道它是被消耗的。我没有做任何研究。我只是……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I've done no prep for this episode. I mean, I, you know, I'm often not as diligent as you are, but I was just like, you know what? I know that hay exists. I've seen it in bales. I figure something is dried. I know it's consumed. I have done no research. I've just Yeah,

</details>

**Tracy Aloway**: 你对干草还是了解一点的，因为我们曾经和……那是新墨西哥州还是亚利桑那州来着？我记不清了，我们和一个种植紫花苜蓿（alfalfa）的农民交谈过。

<details>
<summary>Original English</summary>

**Tracy Aloway**: you know a little bit about hay though because we spoke with um that was it New Mexico or Arizona now? I can't remember the farmer growing alalfa.

</details>

**Joe Weisenthal**: 是的，它是像发酵过的一样，对吧？干草不就是某种发酵并风干的东西吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah, it's like fermented, right? Isn't hay like sort of like fermented and dried or something?

</details>

**Tracy Aloway**: 是的，类似那样吧。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah, something like that.

</details>

**Joe Weisenthal**: 但在沙漠里种植干草的一个好处是，你不用担心在风干过程中它会被淋湿。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I mean, I guess we'll But one of the reasons it's good to grow hay in the desert is because you don't have to worry about it getting wet in the drying process.

</details>

**Tracy Aloway**: 是的。哦，对了。我确实记得，我们确实学到了这一点。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah. Oh, right. I did. We did learn that.

</details>

### 不透明的干草市场

**Joe Weisenthal**: 好吧。这就是我们大家都知道的关于干草的唯一事实。所以，我们今天将要讨论干草价格。但除此之外，我觉得干草市场真的很有趣，因为现在市面上像这样不透明的市场已经不多了。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: All right. So, that's the one hay fact that we all know. So, we're going to be talking about hay prices today. But beyond that, I find the hay market really interesting because [laughter] there are No, seriously. No, no, I believe you. I believe you. There aren't that many markets out there nowadays that are like non-transparent. I want to say

</details>

**Tracy Aloway**: 我们的终端机上有任何干草指数吗？

<details>
<summary>Original English</summary>

**Tracy Aloway**: do we have any hay indices on the terminal?

</details>

**Joe Weisenthal**: 有一个 PPI（生产者价格指数）。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: There's a PPI index.

</details>

**Tracy Aloway**: 哦，有吗。你可以查一下比如紫花苜蓿干草的价格指数。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Oh, it is. Yeah. Okay. So, you can look up like alphaalfpha hay pi.

</details>

**Joe Weisenthal**: 看起来怎么样？我猜一切都在上涨。我的意思是，如果你说出世界上存在的任何东西，它的价格可能都在上涨。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So, how's that been looking? I assume I mean everything is up. I I just like if you name something that exists in the world, it's probably up.

</details>

**Tracy Aloway**: 这个甚至是最新的吗？我甚至找不到一个指数。我不知道。但这就是我的意思。这不是一个透明的市场。它根据干草的类型变得非常零碎。所以我之前没有意识到这一点，但有比如梯牧草（Timothy）、有紫花苜蓿（alfalfa）、有极品干草（supreme hay）。我刚才是想说，正如我所说，我没有做任何功课，我对干草一无所知。我决定要在节目中现学现卖，但我也对我们即将请到的嘉宾做了一点研究。

<details>
<summary>Original English</summary>

**Tracy Aloway**: But what is US hay seeds? Yeah. Well, no. I don't know. Is this even up to date? I I can't even find one. I don't know. But this is what I mean. Like it is not a transparent market. It's very fractured by type of hay. So, I didn't realize this, but there's like Timothy, there's alalfa, there's supreme hay. Um, so I was just going to say, like I said, I haven't done any I don't know anything about hey. I decided I would just learn it all on the fly, but I also I did do a little bit of research about our upcoming guest who you identified

</details>

**Joe Weisenthal**: 就是在 Reddit 上发帖的那个人。我已经说过了，他的生意非常酷，我们会谈论它的，但我只想说，他建立的这个生意，让他成为了解干草的行家，这也是我给那些向我寻求职业建议的年轻记者的建议。我原话就是这么说的，我一直认为，作为一名年轻记者或任何人，你可以建立一项业务的一种方式是：找到一份存在的、公开的、可以免费获取但没有人经常查看的公共数据，把它收集起来，成为它的中央资料库，然后偶尔对其发表评论。世界上有各种各样的数据，数以百万计的各种公共机构每月都会发布关于这个或那个的报告以及没有人看的 PDF。如果你说，你知道吗，我想了解 X，我想发一份关于 X 的新闻通讯，每周或每月更新 X 的动向，你就可以成为这个领域的行家、专家。而你为今天节目找到的这位嘉宾，我认为他完全做到了我告诉许多年轻人应该做的事情。所以，我们将看看，我对干草很好奇，但我也对这个人的商业模式感到好奇。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: the guy posting on Reddit. the guy posting and I have said this his business is very cool and we'll talk about it but I just want to say the business that he has built in terms of like becoming the man who knows about hay is advice I've given to young journalists who have like asked me like for career I've literally said this and I'm going to drop some alpha uh no I'm going to drop some that was an I'm going to drop some alalfa alpha here and but now it'll be commoditized by the time I say it I've always thought that one way you could like build a business as a young journalist or someone is find a find a piece of public data that exists that is out there that is consumable for free that nobody is regularly looking at gather it become the central repository for it and then occasionally comment on it there's all kinds of data in the world a million public agencies of all sorts are producing monthly reports on this or that and PDFs that nobody is looking at And if you say, you know what, I want to learn about X and I want to end a newsletter, write update what X is doing each week or month or whatever, you can become the man, the axe on this topic. And the guest that you have found for today's episode, I think has done exactly what I've told numerous young individuals to do. So, we'll see if this I'm curious about hay, but I'm also curious about uh this individual's business model.

</details>

**Tracy Aloway**: 这是一个很好的市场结构故事，我想也是技术故事和媒体故事。废话不多说，我们确实找到了完美的嘉宾。我们将与 **Aiden Johnson** 谈话。他是 **Haywire** 的创始人。对于这家公司实际做的事情来说，这真是一个非常棒的名字。所以 Aiden，非常感谢你来到 OddLods。

<details>
<summary>Original English</summary>

**Tracy Aloway**: It's a good market structure story and I guess technology story and a media story. Yeah, exactly. All right, so without further ado, we do in fact have the perfect guest. We're going to be speaking with Aiden Johnson. He is the founder of Can you guess? Well, you know what the company is, Haywire. It's such a good name um for what this company actually does. So Aiden, thank you so much for coming on OddLods.

</details>

### 用数据打通干草市场

**Aiden Johnson**: 感谢你们邀请我。从本质上说，我们正在做的事情，也就是我们围绕其建立业务的事情，就是像 Joe 所说的那样，提取公开数据，然后以通俗易懂的新闻通讯的形式提供给我们的订阅者。美国农业部（**USDA**）每周、每两周，甚至每月根据不同地区发布报告。所以我们建立了一个系统和技术，让我们的模型为我们做所有艰苦的工作，然后对其进行分析并用通俗易懂的语言表达出来。经历这些缺陷并确保我们生成最准确的数据，是一个非常棒的学习过程。这很有趣。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah, I appreciate you guys having me on. Yeah. So, essentially what we are doing and kind of what we built our business around is pulling public data just like Joe said and kind of putting it all on plain English newsletters for our subscribers. So, um I mean USDA publishes reports uh weekly, bi-weekly, and then even monthly depending on region. So, uh we kind of built a a system and a technology and our model to kind of do all the hard work for us and then analyze it and put it onto plain English. So, it's it's been a great great um I don't know, like lesson, I guess, learning going through the flaws, making sure were producing the most accurate data. But, no, it's been fun.

</details>

**Tracy Aloway**: 让我们深入探讨一下这个话题。我确信 AI 能够使收集和吸收相关数据的过程变得更容易。但是你能挖掘出哪些报告呢？是谁在制作这些报告？你正在挖掘的公共数据源是什么，你能从中提取什么？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Well, let's go into this a little bit more. And I'm sure that AI makes the process of collecting [snorts] and absorbing the relevant data uh easier. But what are these reports out there that you're able to mine? Who's producing them? what what are the what is the sort of the the public data source that you're mining and what can you pull from it?

</details>

**Aiden Johnson**: 是的，所以我们实际上与美国农业部有直接的 API 集成。所以我们能够严格地从他们那里获取实时动态，这基本上汇入了我们四系统类型的验证过程。美国农业部正在公布基本上是全国各地的拍卖价格。所以每个拍卖行都会报告他们的出价或者他们在当地看到的情况，然后这些信息会被放在 PDF 文件里，但被埋藏在 PDF 中，所以人们很难找到它。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah, so we actually have a direct API integration with the USDA. So we get live feed strictly from them and that basically funnels into our four system type of I guess you could say verification and so we're mining that which publishes every week but the problem we're kind of running into is data. Sorry. Yeah. So, the USDA is publishing basically auction prices throughout the region, throughout the countries. So, every auction house will report kind of what they're paying or what they're seeing on the ground there and then it'll be um put on a PDFs but buried in PDF. So, it's kind of hard for people to find.

</details>

**Tracy Aloway**: 顺便说一句，你实际上还会打电话给一些拍卖行，以获取额外的定价信息，对吧？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah. So, you actually call up some of the auction houses, by the way. I didn't even realize there were auctions. I didn't either for hay, but you call them up to get additional pricing information as well, right?

</details>

**Aiden Johnson**: 我们实际上有爱荷华州的 Rock Valley，Rock Valley 干草拍卖行作为我们的主要数据合作伙伴，它是全国最大的干草拍卖行之一。所以我们从他们那里获取关于他们在当地所见情况的情报，以覆盖美国农业部数据和现货市场之间人们实际看到的灰色地带。我们正在积极尝试建立网络，连接全国不同地区更多的拍卖行，这样我们就能预测当地实际发生的情况。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. So, we actually have uh Rock Valley Iowa uh Rock Valley hay auction as our primary data partner, which is one of the biggest hay auctions in the country. So, having them to kind of get intel from what they're seeing on the ground to kind of cover the gray area between the USDA data and the live market, what people are actually seeing on the ground. And we are actively trying to, you know, branch off and network to more auction houses throughout uh the country to different regions so we can kind of get a forecast what's actually happening there.

</details>

**Joe Weisenthal**: Joe，这让我想起了以前的废金属市场，对吧？当时经纪人实际上必须打电话给所有这些废品场，询问他们的售价。这和 LIBOR（伦敦银行同业拆借利率）并没有太大区别。这绝不亚于废金属这种非常不透明、缺乏流动性的市场。这种我们要打电话给人们或者发邮件，然后三角测量数据的基本理念，正是许多最著名的流动性市场运作的方式。这就是真正的阿尔法（超额收益）。打给人们。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Joe, this reminds me of the old scrap metal market, right? Where like you had a broker who actually had to call up all these junkyards and ask what price they were selling. I don't know if that's still the case, but it might actually still be the case. But if you like and I remember 11 or 12 years ago like very early on talk when I joined Bloomberg talking to one of our reporters uh she was based in London who was covering scrap metal and she talked about that part of it was essentially calling up uh the scrap yards and say what'd you price for and of course you know it's not that different from liebore right it's not like we think of something like these very opaque illquid markets like scrap metal but that fundamental idea of we're going to ring people up or get an email or something and then triangulate the data is how some of the most you know famous liquid markets there are. That's the alpha alpha alpha. That's the that yes that's calling people up.

</details>

**Tracy Aloway**: 关于美国农业部发布的这些报告，我假设，它是只有干草报告，而且他们只发布价格数据、产量数据或质量数据吗？还有其他内容吗？你提取这些数据的背景是什么？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Calling people of wait so just on these reports that the USDA publishes I assume a it's not is it just a hay report and do they just publish price data or volume data or quality data? Is there anything else that like what are the what is the context with which you pull this data from?

</details>

**Aiden Johnson**: 我们可以从许多来源获取数据，但具体到美国农业部的数据，它会显示地区、草捆的类型、重量，以及所生产的干草或紫花苜蓿的质量。所以，这些会自动进入我们的数据库，这让我们变得轻松。当我们获取地面情报时，我们可以将其放入我们的数据轮中，它能够将之与美国农业部的数据以及它预设的表格进行交叉对比。所以我们能够确保来自地面的数据不是……是有价值的，而不是幻觉，可以这么说。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. So there's many sources that um we can pull our data from, but specifically on the USDA data, it'll it'll show the region uh the type of bail, the weight, you know, the quality of hay or alphalfpha that's producing. So, and that automatically goes into our database and it kind of makes it easy for us. So when we take on ground intel that we can put it through our data wheel and it's able to, you know, cross reference it with the USDA data and the table it kind of presets. So we're able to make sure it's not uh the the data that's coming from the ground is, you know, valuable and actually not uh hallucinations, I guess.

</details>

### AI与Vibe Coding开启创业机遇

**Joe Weisenthal**: 你知道，一些非常成功的例子，比如 Flight Radar 24。这类价值连城的东西，本质上就是有些人找到了一种很好的方法来可视化或呈现那些已经是公开的但很不透明的数据。所以我对这种商业模式非常着迷：那里有这么多数据，如果你给它披上一层漂亮的外衣、做一个用户界面，实际上就像“让我只看价格”或者“让我只看它移动的地图”，这突然之间就能成为一个非常赚钱的东西。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: You know, uh I know we're going to get to hay specifically, but just as we're talking about sort of this business model, there have been some really successful, you know, I think like it might be flight radar 24. One of these other uh things that was worth a lot of money was essentially some people who found a really good way to visualize or present Yeah. data that was already public but it's opaque etc. And so I'm very fascinated by this business model of like there's all this data out there and if you put a nice skin on it user interface you make a user interface and actually like let me just see the price or let me just see the map that it's moving on can suddenly be a very monetizable thing.

</details>

**Tracy Aloway**: 我预计随着 **Vibe Coding** 的出现，这也将变得更加普遍。那么 Aiden，你为什么决定投入这个特定的项目？如果你不介意我这么说，你看起来非常年轻。我假设你是 Haywire 的年轻创始人。为什么这是你的第一个项目？你的热情所在的项目。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Well I expect with vibe coding it's going to become more common as well. So Aiden, why why did you decide to get into this particular project? And if you don't mind me saying so, like you look you look very young. I assume you're a young founder of Haywire. Uh why was this your your first project? Yeah. Your passion project.

</details>

**Aiden Johnson**: 哎呀。如果你去年告诉我这个，我是不会相信你的，因为这个想法是我爸爸提出来的，他实际上想开一家做紫花苜蓿草块的初创公司。在那个过程中，他需要计算成本，他提出了一个问题：为了算出原材料价格，干草的成本是多少？这就是一切的开端。他说，“Aiden，你可能应该启动这个项目。这是个好主意。” 当时我想，拜托，我才 19 岁。我是个大学篮球运动员。我才不在乎干草呢。那是 2025 年发生的事情。我一直知道我想涉足创业。我当时说，“爸爸，你知道我想经营一家企业，但干草绝对不能帮我找到女朋友。” 等我上了大学，我接触到了 AI。这最初是从为当地企业通过 Vibe Coding 做网站开始的。然后实际上是我的联合创始人 Cole，他在 AI 方面非常聪明，我们刚开始合作讨论这件事，以达到更加 Agentic（智能体化）和自动化的 AI。这就开启了一个兔子洞。它最初只是一个没有任何基础设施或系统的 Vibe Code 项目，后来变成了我们认为可以实现的东西。所以我们就投入进去了。我们基本上每天都会通电话，决定如何改进我们的产品、如何改进我们的技术，以便我们能处理出最大的吞吐量。干草市场是非常不透明的，所以我们发现了一个问题。你商学院第一周的课就会学到，你需要找到一个问题，然后找到一个解决方案，才能开展一项成功的业务。这就是这一切是如何产生的。我们每天都在攻克它。我非常感激我爸爸问了那个问题：紫花苜蓿和干草的价格是多少？

<details>
<summary>Original English</summary>

**Aiden Johnson**: Oh man. Well, if you were to tell me this last year, I wouldn't believe you because the idea was kind of thrown out by my dad who was actually looking to start a startup company for Alpha Cubes. And throughout that process, he kind of needed he was crunching number and he asked the question, what is the cost of hay to, you know, find that raw materials price? So that's kind of how it all started. And he's like, Aiden, you know, you should probably like start this. It's a great idea. And you know, at the time, I'm like, okay, come on. I'm 19 years old. I'm a college basketball player. I don't really care about Hey, which year was it? This was year 2025. Okay. Oh, okay. So this this conversation happened in 2025. And at the time, you know, I'm I'm a college basketball player. Um, I don't really care about hay, but you know, I always knew I wanted to kind of get into entrepreneurialship, I guess. And I'm like, dad, you know, you know, you know, I want to run a business, but you know, hay is definitely not going to get me a girlfriend. So, that's kind of how it started. And that's kind of how it started. And you know, as I got to college, I was introduced to kind of AI, which kind of started out as um you know, vibe coding websites for local businesses. And then I actually my co-founder Cole, who is very intelligent with the AI, we kind of just started working together about it to get to the more agentic and automation type of AI. So that kind of started a rabbit hole. I'm like, which kind of started out as a vibe code project with no infrastructure or no system at all. um kind of turned into something we thought uh we knew that was reachable. So we kind of got into that. Um you know just we we basically hop on a call every day deciding how we can improve our product, improve our technology so we can produce the best volume and you know the hay market is very untransparent I guess you could say. So we found a problem. Uh you know first week of college classes in the business class you're going to learn okay you need to find a problem and then a solution to start a successful business. And uh that's kind of how it all came about. And you know, we've been kind of attacking it every day. And I'm very grateful for my dad to ask the question, what is the price of alpha alpha and hay?

</details>

**Tracy Aloway**: 那你现在有女朋友了吗？你找到了吗？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Uh do you have a girlfriend now? Did you get one yet?

</details>

**Aiden Johnson**: 绝对没有。人们问我经营什么类型的生意，我只是说，我试图把它伪装成非常智能的东西，比如“是的，我经营一家市场智能 AI 基础设施公司”，而不是一家普通的干草市场公司。所以，没有，还在寻找中。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Uh absolutely not. So people ask um what type of business you run and I just say I try to you know mask it as something really intelligent like yeah I run a market intelligent AI infrastructure company and not just a market hey market company. So, no. Um, in the process.

</details>

**Joe Weisenthal**: 好吧。明尼苏达州的 Odd Thoughts 听众们，符合条件的年轻单身汉，20 岁，我们就是帮忙宣传一下，也许我们可以为你做点牵线搭桥的事。如果是 10 年前，你和你联合创始人在现实中做这件事能做成吗？在没有我们所知的 AI 和 Vibe Coding 的情况下？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: All right. Well, odd thoughts listeners in in Minnesota, uh, eligible young bachelor, uh, 20 years old, um, just, uh, we're just putting it out there, maybe we'll do, uh, we can do some matchmaking for you. Um this [laughter] just um had your dad had this idea, I don't know, had this been 10 years earlier, like orders of magnitude, would this have been doable at all to you and your co-founder in a real way prior to AI and vibe coding as we know it?

</details>

**Aiden Johnson**: 哦，不。10 年前，我认为我甚至连现在的表面都接触不到。这仅仅是因为我认为 AI 的基础设施每天都变得越来越智能，它使得像我和我的联合创始人 Cole 这样两个 20 岁的年轻人，能够折腾并创建出整个公司和平台。所以，如果是 10 年前的话，它可能需要一个庞大的团队。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Oh no. 10 years ago, I don't think I would even scratch the surface of getting to the death I am here now. Um, and that's just simply because I think the infrastructure of AI is getting smarter and smarter every day and it makes it able for, you know, two young 20-year-olds like me and my co-founder Cole to, you know, mess around and create a whole company and platform. So, um, yeah, I don't I don't think it would be um it would probably take a big team uh 10 years ago.

</details>

### 干草的区域性与波动性

**Tracy Aloway**: 所以如果我试图查询干草价格，我肯定会去 Haywire，但先不谈 Haywire，我应该去寻找什么呢？目前市面上是否有基准干草价格？就像当我们谈论美国股市时，我们会谈论标普 500 指数或像道琼斯这样的指数。有我应该关注的特定干草价格吗？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Tracy, I I already want to be Aiden Johnson. Like, I'm everything about this is just like so cool to me. Like, in my next life, this is my plan. Well, go out and find that niche market. Find your hay, you know, find your alpha. Yeah. What is your hay? Pursue your Timothy dream. Um, okay. Well, why don't we actually get to hay prices? So, first of all, if I try to look up hay prices, I'm definitely going to haywire, but setting haywire aside, what am I trying to find? Is there a benchmark hay price out there? the way there is, you know, when we talk about US stocks, we talk about the S&P 500 or another index like the Dow Jones. Is there a particular hay price I should be looking at?

</details>

**Aiden Johnson**: 并没有。美国农业部的 NASS 会发布一种干草的平均成本。所以，现在我看到 4 月份的干草是每吨 180 美元，比 3 月份上涨了 167 美元。在紫花苜蓿方面，是每吨 185 美元，自 3 月份以来从 175 美元上涨了。我曾和 Rock Valley 拍卖行的 Levy Russ 聊过，我问他：“人们是怎么知道他们买干草付了多少钱，又是以什么为基准的呢？” 因为除非你有经济学学位并且有时间去找，否则人们真的不会去查阅那些美国农业部的 PDF 文件。他告诉我：“其实我们这个地区很多人，Rock Valley 在中西部，都用拍卖数据作为干草价格走向的基准。”关于干草市场，我发现最疯狂的一点是，它不是一个单一的市场，而是分散在全国各地的破碎市场。由于运输成本很高，每个区域市场都具有极强的**超本地化（hyper local）**特征。你不能在国内进行长途运输。而且考虑到有很多影响干草质量以致影响最终产出的输入变量，明尼苏达州的干草在价格上可能与加利福尼亚州的干草不一样，因为它完全是高度本地化的市场。

<details>
<summary>Original English</summary>

**Aiden Johnson**: You know, not really. Um, the USDA, USDA, um, NASS is what it's called, will, you know, produce kind of an average cost of hay. So, right now, I'm looking at hay for April, it's $180 per ton, which is up $167 from March. And then for the alpha alpha side of things, it's $185 a ton, which is up from $175 since March. So essentially, I was talking to Levy Russ at Rock Valley and I was kind of kind of explaining this issue and I'm like, how do people really know what they're paying for hay and like what do they benchmark it against? Cuz you know, people aren't really going into those USDA PDF files unless you kind of have a a degree in economics and, you know, have the time to find it. So I kind of talked to him and he's like, "Yeah, actually we have a lot of people in our region, uh, Rock Valley specifically is in the Midwest, um, use their auction data as the benchmark of kind of what hay is going for." So the crazy thing about the hay market is what I realized it's not just one market. Um, it's like fragmented markets across the whole country. Every market, every regional market is very hyper local simply because transportation costs are a lot. you can't domestically transport it across the country and then you you think like there's so many inputs um how it affects the quality of hay to you know produce the output you know Minnesota hay may not be the same as California hay in terms of price because it's just all h very hyper local markets

</details>

**Joe Weisenthal**: 关于缺乏透明度以及不同地区之间的广泛价格差异，正如你所说，这与许多其他大宗商品没有什么不同。我的意思是，甚至石油显然也有区域价格差异。运输成本会影响它。在什么程度上，它们在全国范围内普遍相关？即使从一个地区到另一个地区价差很大，价格通常也会在同一时间涨跌吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: [music] [music] just on the girlfriend thing. You're 66 [laughter] and you can dunk a basketball, I see on Twitter. Okay, sorry. I'm just Oh, you're really doing all you can to help here, Joe. I'm I'm looking at his uh Twitter [laughter] profile and uh and you can dunk. I'm really impressed. I wish I I couldn't. Appreciate that. Appreciate it. Yeah. No, it's uh it's really cool. Let's talk about these um to what degree. All right. There's this lack of transparency and there's this wide variety of prices regionally which again is not unlike many other uh commodities. I mean even oil obviously has regional price variations. The cost of shipping is going to affect it. But you know we talked about this with lumber with Stinson and Dean as an example. To what degree are they generally correlated across the country? Like will they gener will prices generally rise and fall around the same time even if there are wide gaps in the un uh you know wide spreads from one region to another?

</details>

**Aiden Johnson**: 是的。有许多不同的因素会影响不同地区的市场。你想想现在西部正在发生的事情，现在发生了干旱，美国 46% 的紫花苜蓿种植面积实际上处于干旱之中。所以，你可能会看到一些来自西部的需求可能向东转移。但实际上我前几天在研究这个，我有点在观察东海岸，因为我不知道那里是否有太多关于干草的信息。那里有很多业余农场，也有小型的草捆市场，但它有点像是一个独立的生态系统。很酷的是，它不会真正感受到西部干旱的影响，这仅仅是因为运输是其中的一个主要因素。你不可能把干草运那么远，因为最终运费会比干草本身的价值还要高。仅仅是因为这些经纪人和经销商的运费是每英里 5 到 8 美元。这很容易就平均比干草还贵了。这很奇怪。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. So there is a bunch of different factors to kind of how um different regions can uh you know be affected by markets. I mean, you think of what's kind of going on in the west right now. Um, with the the drought kind of going on, 46% of the US alphalfpha acreage is actually in a drought. So, you might see some demand coming from the west maybe moving east, but actually I was kind of looking into this the other day and it's I was like kind of looking at the east coast kind of because I I don't really like there's not really much out there I guess for hay. I mean, there's lot hobby farms and it's like small square markets out there, but it's kind of its own ecosystem cuz it's cool because it it won't really feel the effects of the drought from the west simply because transportation is a big factor in that because you're not going to ship or transport hay that far because it just it will eventually cost more than the actual value of the hay. simply because, you know, these brokers, these dealers will charge anywhere from $5 to $8 per mile to have it shipped. So, that can easily average to be more valuable than the hay. So, it's it's kind of it's kind of weird. So, yeah. Um I guess so.

</details>

**Tracy Aloway**: 我现在正在阅读美国农业部的一份报告，上面写着，“由于牧场主寻找干草，干草价格继续上涨。” 你有没有看到人们试图大量购买或在价格进一步上涨之前确保供应？

<details>
<summary>Original English</summary>

**Tracy Aloway**: If I'm in a location, one of the droughtstricken uh states, droughtstricken states, that's hard to say. Um, I'm reading the USDA, one of the USDA reports right now, and it says, "Hay prices continue to increase as ranchers search for hay." Are you seeing people who are trying to like bulk buy or secure supply ahead of more price increases?

</details>

**Aiden Johnson**: 是的，我目前看到，并且通过与全国各地的农民交流，我看到人们正试图为夏天囤积物资。我听说第一茬割下来的草量非常少。产量并没有达到一定的规模，而 2025 年的结转库存已经基本耗尽了。

<details>
<summary>Original English</summary>

**Aiden Johnson**: I mean, yeah, I'm I'm I'm seeing right now and, you know, just talking with farmers kind of networking across the country, um, I'm seeing people are trying to get their stockpile for summer. I'm hearing that first cut is being extremely light. the yields are not really producing at a volume and carryover from 2025 is essentially gone.

</details>

### 从数据到商业模式

**Joe Weisenthal**: 这引出了我另一个重要的商业问题。任何人都可以收集数据并将其生成。但接下来你必须找到愿意从你这里购买这些数据的人。这是做生意的另一半。一些人在内部进行生产，一些人负责销售。你是如何去寻找农民或者种植者，或者是行业里的任何人的？你是如何让他们发现 Haywire 的？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Sorry, I actually did find uh if you search on the terminal, Tracy, if you search USDA hay prices by state Oh, then you can find some fairly regularly updated price indices. So, I have to say like I mean I understand you have a great business going, but if any listeners just want to spend tens of thousands of dollars on a Bloomberg terminal, they can also any farmers out there want to look up prices. Bloomberg actually offers a uh [laughter] a haywire competitor. You just get a bunch of other stuff. You're probably not uh interested. But no, but this gets to my so like this is another important business question. Anyone can collect data and produce it. Then you have to find people who will purchase it from you. And this is the other half of business. Some people in the house produce and some people sell. How did you how do you go about um finding farmers or or growers or anyone in the business, anyone in the chain? How do you get them to discover haywire?

</details>

**Aiden Johnson**: 主要是建立人脉网络。显然，发现这很大一部分发生在 Homestead 的 Reddit 上，Tracy 就是在那儿发现这一切的。但其实就是主动联系他们。向他们展示，“这就是我们想做的事情。” 试图成为那个透明层，让你们当地的市场对你们来说更容易一些，不用盲目地猜测、盲目地买卖。所以我们去找他们说，“这对你们来说是免费的。告诉我们你们所看到的，这样我们就能为干草价格提供清晰度和透明度。” 我们不可能解决所有的透明度问题。我们会尝试，但可能做不到。但我们至少想让你们当地的地区稍微透明一点。这些农民对自己地区的市场了如指掌。特别是这些老一代的农民，他们不会那么轻易地适应技术。所以要让他们适应，让他们觉得 “好吧，这是现在的技术，这其实能帮到我的生意”，这是相当困难的。所以老实说，就是和他们建立人脉网络，提供我们看到的数据，展示其价值，让他们看到只要和我分享他们的数据其实是没有任何成本的。

<details>
<summary>Original English</summary>

**Aiden Johnson**: I guess just networking. Obviously, Discovery, a big part of that has been on the Homestead Reddit, where Tracy kind of found everything, but you know, just actively reaching out to them, I guess. Kind of just showing them, okay, this is what we're trying to do. Trying to trying to be that transparency layer just to kind of make your guys' local markets a little easier for you and not kind of guessing and buying blind and selling blind. So, we're we're basically going to them and we're like, "Okay, this has no cost for you. just like kind of tell us what you're seeing so we can provide that clarity and transparency for, you know, hay prices. You know, we're not going to fix the whole transparency issue. Like we're going to try, but we probably won't. Um, but we we just at least want to make it a little more transparent for your local region. You know, these farmers know their regional market like the back of their hand, and it especially these old gen farmers, they're not really going to adapt to technology like that. So it's been kind of uh difficult trying to get them to adapt to be like okay like this is technology nowadays like this can actually really help your business. So um honestly just networking with them providing um you know kind of the data we're seeing and kind of the value and see showing them that there's no really cost to just kind of sharing me your data.

</details>

**Tracy Aloway**: 关于购买时机，或者人们试图在面临巨大压力，比如由于干旱等原因导致价格非常高时囤积。你是否看到农民基本上扩大了他们的地理搜索范围，比如他们开始从一家拍卖行、农场或者什么地方买干草，而在正常情况下，向这些地方采购对他们来说并不划算？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Um, so Tracy mentioned the sort of timing of purchases or people trying to uh accumulate or stockpile at times of high stress when prices are really high again maybe due to a drought or whatnot. Do you see farmers essentially expanding their geographical search so such that they start buying hay from an auction house or a hay farm or whatever that wouldn't normally be under typical conditions economical for them to purchase from.

</details>

**Aiden Johnson**: 是的，其实前几天我就被问到了这个问题。我在和 Rock Valley 的负责人通话，那是我主要的联系人，我问他，“你们有没有看到任何从你们以西的地方发来的运输需求或交易？” 因为干旱在这些西部州非常严重，我只是在验证一个假设：西部的买家会不会来到这些东部的州购买产品呢？因为我们确实看到拍卖数据中出现了一个峰值，我们在 Reddit 上稍微提到过，我们称之为密苏里模式。这可以说是我们正在验证的一个假设。所以基本上是在我们发现西部州面临严重干旱、供应非常紧张之后，我们开始观察那些偏西的中西部州，然后我们看到密苏里的价格上涨了，我们就觉得好，我们会关注的。第二周，我们看到 Rock Valley 的价格又稍微上涨了一点，所以也许确实有一些需求是从那里转移过来的。再下一周我们看到它又上升了一点。所以这是我们目前观察到的情况。由于我们在密苏里州追踪的拍卖行是按月发布数据的，而 Rock Valley 是每周发布，所以我无法完全证实这是否为真。但这就像搭乐高积木一样很酷。我一块一块地拼建，就像是在努力解开一个谜题。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. You know, I I actually had this question the other day and I was on a call with Rock Valley, my my main go-to guy, and I was like, "Are you guys seeing any shipping or any transactions coming from more west of you?" Yeah, I just kind of I was kind of testing a hypothesis of okay, so the drought is very tight over in these western states. Are buyers coming over to these eastern states and producing it because we did see a spike kind of in auction data. We kind of covered it a little bit maybe on the Reddit, but it we called it kind of the Missouri pattern. It was kind of hypothesis we were testing. So it basically is so after we figured out that the drought and you know supply is very very tight there in the western states we started watching those western Midwest states so we we saw demand in or prices in Missouri go up and they're like okay well we'll keep an eye on it and then the next week we saw um Rock Valley's prices kind of spike a little bit and they're like okay so maybe there is some demand coming over from there and then the next week we saw it you know get go up a little bit a little bit again. So, it's kind of what we're seeing right now. I can't confirm fully if it's true because auction house we track in Missouri postes their data monthly. So, and then Rock Valley is weekly. So, it's just a kind of cool like I guess I'm kind of it's like a Lego set. I'm kind of just like building piece by piece and it's like a puzzle trying to solve the puzzle.

</details>

### 高昂草价引发的连锁反应

**Tracy Aloway**: 告诉我们关于干草价格上涨的连锁效应。我知道你并不直接从事农业，但我肯定你听说过这方面的事情。在这里我必须向我们的彭博社播客同行 Katie Griffeld 致意，她养了一匹马。我问她是否注意到了干草价格的任何变化，她说因为干草价格的上涨，寄养马的成本也上升了。在我们录制这期播客之前，我看到了另一条关于德克萨斯州一家马匹收容所的新闻标题，因为干草价格和汽油价格的上涨而濒临倒闭。人们是否正在感受到这些高价格带来的影响？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Okay. So, talk to us. I know you're not in agriculture directly, but I'm sure you've heard some things about this. talk to us about the second order effects of higher hay prices. And here I got to shout out our fellow Bloomberg podcaster Katie Griffeld um who has a horse. Oh yeah. And so I asked her if she had like noticed any changes in hay prices and she said like the cost of boarding had gone up because of hay prices. Boarding. Oh, board the horse. And then I saw another headline just before we recorded this podcast about a horse sanctuary in Texas on the brink of closure because of rising hay prices and also gas. So are people feeling the effects of these higher prices?

</details>

**Aiden Johnson**: 是的，绝对是的。我通过与全国各地的农民以及甚至马主交谈，我家自己也养马，所以我能够直接体会到这一点。我一直在和许多农民或者马主交谈，他们基本上都在说，“我们非常爱我们的马，但是目前养马的投资回报率就是……太昂贵了。” 我花了很多钱来维护这匹马，我们不知道究竟该怎么办，因为它太贵了。另一方面，一些乳品企业将会是购买较高质量 RFV（相对饲喂价值） 紫花苜蓿的主力军，用以喂养那些每天产 80 磅牛奶的奶牛。他们实际上会把那些较高质量的 RFV 和较低质量的 RFV 混合在一起，来控制他们的口粮，并且也许能创造出更多的容量。尤其是面对这些高得离谱的价格，他们可以更多地控制他们的使用量。除此之外，我前几天和一位农民交谈，他说，他本来打算把干草放到拍卖会上，但他后来撤回了，因为对干草的需求越来越大，变得越来越紧缺，他自己也需要干草。所以他预测供应会变得更加紧缺。如我所见，很多人都在感受高昂的干草价格带来的后果。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah, absolutely. Um just talking with farmers and you even horse owners across the country. I personally, my family owns horses, so I can kind of see this firsthand. But yeah, I I've been talking to a lot of farmer or horse owners and they're basically saying, "We love our horse so much, but the return on investment on horses right now is just like it's too it's too expensive." No, I'm paying so much to maintain the horse and we don't know like exactly what what we're going to do because it's so expensive. But and then on the other side of things, some dairy houses, um these these dairies are going to be the ones buying the higher quality RF alalfa to um you know, feed these cows that are producing 80 pounds of milk a day. And they're actually taking that high higher quality RF and then mixing it with lower quality RF to, you know, um control their rations and, you know, maybe create a little more volume. So, especially with these crazy high prices, they can kind of control their their volume a little more. And then on top of that, I was talking to a farmer the other day and he said, so he went to go put his hay up up in the auction, but he actually pulled it back because the demand for hay was getting so increasingly like it was getting really tight and he needed the hay. So, he's kind of predicting it to get even tighter. So yeah, as I can tell, a lot of people are kind of feeling the out outcomes of these high high hay prices.

</details>

**Joe Weisenthal**: 退一步讲，你刚才提到了马。牛也吃干草，对吧？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Just to back up for uh so you mentioned horses. Cows also eat hay, right?

</details>

**Aiden Johnson**: 是的，牛会吃……可以说是有不同类型的质量等级。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yes. Yes. So cows cows will eat there's different types of qualities I guess you could say.

</details>

**Joe Weisenthal**: 给我们讲讲这些质量。你说了 RFD 这样的词？你用的术语是什么？相对什么来着？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. Walk through us these qualities. Did you say something like RFD? What was the term you used? Like higher what was it?

</details>

**Aiden Johnson**: **RFV**。相对饲喂价值（Relative Feed Value）。它基本上是控制或者获取干草中的蛋白质含量和纤维。它是以 100 为基准的。所以像 150 这种数值就认为非常好了。低于那个数值，你会看到质量较低的干草。就像我说的，乳制品厂会使用那些更高质量的紫花苜蓿和极品干草，也就是更高 RFV 的干草，让他们的奶牛吃最好的。然后你会有马术圈的人、马主也使用这种更高质量的东西，因为他们爱他们的马，他们只想给马最好的。然后你会拥有低质量的干草，那会进入实用和一般市场，用于喂养肉牛。这只是一种以更便宜的价格养肥肉牛的廉价方式，而不是购买高价紫花苜蓿。干草有太多不同的质量等级了。

<details>
<summary>Original English</summary>

**Aiden Johnson**: RFV. a relative feed value. Okay. Which basically is which I think I'm pretty sure it it it controls or it it gets the protein contents and the fiber in the the hay. And it's it's a base of 100. So anything like 150 I think is pretty good. Below that you can see the lower quality hay. So, like I said, the dairies are going to be um using that higher quality alalfa and supreme hay, higher RFV to have their cows on the best. And then you're going to have the the e-cline people, the horses also using this higher quality stuff because they love their horses and they only want what's best for their horses. And then you have the lower quality type of stuff which is going to go to like the utility and fair which is going to go to your beef which are it's just a cheap way to you know beef up your cow for a cheaper price instead of paying the premium alalfa. And then yeah there's there's there's so many different qualities.

</details>

**Joe Weisenthal**: 快速问一句。所以紫花苜蓿制成的干草是高质量的。低质量干草是由什么制成的？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. Yeah. Just real quickly. So hay made out of alalfa is high quality. What is lowquality hay made out of?

</details>

**Aiden Johnson**: 低质量干草，就是 RFV 较低的干草。我不是农村长大的孩子，但我很确定这取决于干燥程度和蛋白质含量。当下雨的时候，降雨影响很大。你需要一个干燥的星期或者干燥的预报才能生产或者收割干草。如果下雨，雨水会降低干草中的蛋白质和营养价值。我认为低质量的干草更干燥，并且不含有高质量干草所含的那种叶子成分。因为蛋白质主要存在于叶子中，而纤维则存在于茎中。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. So lowquality um hay, which will be lower RFV. I I'm pretty sure, you know, I'm not a farm kid, but I'm pretty sure it's the the amount of dryness and the protein contents. So when when it rains, rain affects a lot. You have to have a dry a dry week or forecast to produce um or cut hay. And if it rains, rain can decrease the protein and nutritional value in the hay. I think the lower quality stuff is drier and doesn't have the leaf content um that the higher quality stuff does because that's where the protein is in is in the leaf and then the fiber comes from the stem.

</details>

### 数据中心与农业用地的竞争

**Tracy Aloway**: 你有没有看到任何人因为这些高价而投入更多的土地来种植干草？因为我有点在想，我有两块地，目前除了长入侵杂草什么都没干。也许我可以把它们租出去用于干草生产。

<details>
<summary>Original English</summary>

**Tracy Aloway**: [music] [music] [music] Are you seeing anyone devote more acreage to growing hay as a result of these high prices? Because I'm kind of thinking I got I got two fields. They're not doing anything except growing invasive weeds at the moment. Um maybe I could rent them out for hay production.

</details>

**Aiden Johnson**: 是的，你知道，我并没有真的看到那个。但前几天我正好在想这件事。我开车经过离我往南 20 分钟的地方。我开在高速公路上，我发现谷歌实际上要在离我往南 20 分钟的地方建立一个占地 482 英亩的数据中心，我就在想这会如何影响农业用地。我的意思是，紫花苜蓿在干草中的处境已经有些尴尬了，因为它们已经在与其他农作物竞争，比如玉米和具有更高稳定性的作物大豆。那么这些数据中心将如何……它们会建在农业用地上。所以反过来，你会想它们将如何夺走这些农业用地。同时我也在想，谷歌在这里建的 482 英亩的数据中心将会是风冷的。但如果你把这些建在西部各州，那里气候干旱，而紫花苜蓿又是一种非常耗水的植物。那么紫花苜蓿将不得不与这些大型数据中心争夺水资源。我真的看到了它的另一面，这也正是我个人所观察到的情况。但你确实提到你有 75 英亩土地，据我所知你有四种不同的选择。这其实是我想要涉足的下一个细分市场。我爸爸刚在这里买下了一个 164 英亩的农场，他也有同样的问题：我不知道该用它做什么。尽管我还不是这个领域的专家，但我知道有几个选择。你可以把它租给农场或者农民，基本上就是按英亩收租。美国农业部会付钱给你让你休耕保护它，但坏处是你可能会在 25 到 35 年内失去对这片土地的控制或使用权。第三个选择也是现在最赚钱的作物，我想你可以让那些太阳能电池板公司进来在你的田野上放置太阳能电池板，换取一大笔钱。但你愿意在不断升值的农田上安装太阳能电池板吗？所以说，现在有这几个选择，就像你说的，你也可以开始种植干草或者种植任何最赚钱的作物。这只是我知道的选项。但它真的很有趣。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. You know, I'm not I'm not really seeing that, but um I'm I'm not really sure on that one if I'm seeing people doing that. But I actually was thinking about this other day kind of driving past 20 minutes south of me. And I was driving on the highway and I I realized that Google is actually going to build a 482 acre data center 20 minutes south of me and I was like thinking how could this affect the agricultural land. I mean you know it's already not a lot of people are alalfa is kind of in a weird spot in hay because they're already competing against the other crops um you know the more stable crops like corn and soybeans. So, how are these data centers going to, you know, they're going to go on agricultural land. So, Oh, yeah. kind of vice versa, you were saying, how are they going to take away this agricultural land? And, you know, I was kind of thinking too, the 482 acre um data center Google's building here is going to be cooled by air. But what if you put those kind of in the western states and where the drought conditions are and alalfa is already a very water intrusive plant. So then alalfa is going to have to be competing with these big data centers for water. I I really I really I'm really seeing kind of the flip side of it kind of kind of just what I'm seeing personally. So but yeah, you did mention you had 75 acres and um I think you do have four different options from what I know. That's kind of the next niche I kind of want to get into because once again it's kind of like the hey not my dad's kind of going through the same process. um he just closed on 164 acre farm here and he had the question of I don't really know what to do with it but I don't know I'm not an expert on it yet but um I do know there's a couple options you can rent it out to your farm or to farmers basically like rent per acre and then you can uh the USDA will basically pay you to conserve it and then the the downside of that is you probably lose your land or access to your land for 25 to 35 years. Uh and then the third choice is kind of the money crop right now. I guess you can these solar panel companies are coming in to maybe place solar panel panels on your fields um for a huge chunk of change, but also are you okay with you know putting solar panel on appreciating farmland? So I mean there's there's a couple options and like you said you can also grow start growing hay or grow whatever crop is producing the most money I guess. So there's some options that that's as much as I know right now. But yeah, it's pretty interesting.

</details>

**Joe Weisenthal**: Tracy，你考虑过在你的土地上建个数据中心吗？你知道，是不是可以这样，一半用来装太阳能板，然后这能为另一半的数据中心供电。这就是一笔巨大的收入。这集节目真成了所有我们感兴趣的话题的聚宝盆。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Tracy, have you considered putting a data center on your land? [laughter] You know, uh is that something you you know, you could put maybe half the land solar panels and then they could power a data center on the other. You're getting like so many. [laughter] It's like a jackpot episode of like things that we're interested in.

</details>

**Tracy Aloway**: 太阳能面板那个情况确实是真的，因为在我所在的东北部，我看到很多农场现在都满是太阳能板。巨大的连片太阳能板。面积太大了，实际上每次我开车路过时，在远处看就像一片水域。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Well, the solar panel thing is true because in the Northeast where I'm Yeah. based some of the time. Um I see a lot of farms that are now like just solar panels. Huge fields of solar panels. Yeah. Wow. They're so big. In fact, whenever I drive past one, it's so big. It looks like a body of water off in the distance.

</details>

**Joe Weisenthal**: 看起来也很美。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: It's kind of beautiful.

</details>

**Tracy Aloway**: 确实很有意思。

<details>
<summary>Original English</summary>

**Tracy Aloway**: I don't know. I mean, it's interesting.

</details>

**Joe Weisenthal**: 是的，很有意思。干草市场到底有多大？总体而言我们是怎么衡量的？我确实不知道。从体积上看、从美元价值上看，它有多大？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah, it's interesting. Yeah, it's interesting. Um how big is the hay market? Uh just generally like what do we like? Again, I I I don't know like Yeah. How big is it volume-wise, dollar-wise, all that stuff?

</details>

**Aiden Johnson**: 是的，干草市场实际上相当相当大。我的意思是，你看看全美的干草种植面积覆盖了 4900 万到 5000 万英亩，单单紫花苜蓿每年就能产出 80 亿美元的价值，是全美第四大最具价值的农作物。这又引回了我的问题：这是一个相当庞大的市场大宗商品，却没有一个坚实的透明度系统。所以是的，它的规模真的很大。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. So, the hay market is actually u pretty pretty dang big. I mean, you you have hay acorage covering 49 to 50 million acres across the US and itself, alalfa itself is producing 8 billion dollars per year, which is the fourth most valuable crop. And that kind of brings my question back to so it's it's pretty pretty big, you know, market commodity and there's not really a firm transparency layer. So yeah, it's it's really big.

</details>

### 构建草料界的彭博社

**Tracy Aloway**: 你现在还在上大学吗？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Are you still in college?

</details>

**Aiden Johnson**: 是的，我刚刚在詹姆斯敦大学完成了我前两年的学业，即将进入大三。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yep. I just finished my first two years at the University of Jamestown going into my third.

</details>

**Tracy Aloway**: 哇哦。那么你在兼顾大学学业的同时还在经营一盘生意。Haywire 接下来会有什么发展？你提到了也许会为土地所有者评估不同的选择，但你想把它发展到什么程度呢？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Oh wow. Okay. So what you know, you're juggling a business um as well as college. What's next for Haywire? you mentioned like maybe evaluating different options for land owners, but where do you want to take this?

</details>

**Aiden Johnson**: 就像我说的，主要目标是站在干草供应链的顶端。你有生产者、农民，你还有经纪人。我们希望处于顶层，成为这些区域性价格的基准数据。我们只是想成为最顶端的信息层，向这些农民提供信息，这样他们就可以根据时机以及他们所在地区市场的实际情况做出更好的决策。我个人喜欢做新闻简报，我喜欢倾听人们的交流，我喜欢回复邮件并向人们请教。最终，我们也希望能够更多地介入纯商业化的一面，比如把我们的 API 数据库提供给某些人，让他们可以用于自己的网站。那是一个商业计划，虽然不一定是我们在这个干草市场想获取的结果，但这就是我们想做的事情，把这层透明度建立得更好。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah. So, I guess like I said, the main goal is kind of be on top of, you know, the kind of hay chain. Uh, you know, you got your producers, your farmers, and then you got your brokers. We kind of want to be at the top, uh, you know, being the benchmark data for these prices regionally. So, we just want to be that information layer on the top and, you know, just providing this information to these farmers so they can kind of make better decisions based off of timing and then based off of um what the market's actually seeing in their region. You know, I would I I like the newsletter. I kind of like um hearing people connect connecting to people. I love answering my emails and kind of picking people's brains. And then we would we would eventually like to also be, you know, just kind of more the business side of things. you know, give someone maybe our API database and they can use it for their website. You know, that's kind of a a business plan, not necessarily what we want out of the hey market. But yeah, that's kind of what we want to do. Just build that transparency layer a little better.

</details>

**Joe Weisenthal**: 你知道，我们供职的这家公司，在某种程度上起初也是建立在相同的前提之下的。所以我毫不夸张地说，对你来说这有一天绝对可以成为一家财富 500 强公司。这种“找到并建立农业数据库并在顶层堆叠产品”的理念，确实非常厉害。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: You know, we work for a company that [laughter] sort of I mean really this I started under like the same premise. So like that you literally, you know, you could you could one this could one day be a Fortune 500 company for you. I mean this the idea of like find agricultural database. Yeah. Find some data niche, make it built, layer on top.

</details>

**Aiden Johnson**: 我想坦白一件事。当我最初开始策划这项业务时，我们的座右铭是“打造草料界的彭博社（Bloomberg）”。

<details>
<summary>Original English</summary>

**Aiden Johnson**: I have a confession. Yeah. Um, so when I first started first planning this business, our motto was the Bloomberg for Hey,

</details>

**Joe Weisenthal**: 太棒了。可以让我说句话吗？我们节目来过很多人，我也听过别人说要做 X 界的彭博、Y 界的彭博。人们总是这么说。但我认为这次是名副其实的。每个人都想成为某个领域的彭博社。但是，当我想到你们是如何从零开始将其构建起来的，你甚至都不需要说出来。这就好像，你们实际上正在构建具有潜力的“草料界彭博”。也许有一天你们甚至会有自己的电视网络。有了这个基准数据，我们就可以建立基于它的期货市场了吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: there we [laughter] go. There we go. You know, we've had So, can I say something? We've had people come on. I've seen the Bloomberg of X, Bloomberg of Y. People always say this. This I find to be legitimate. You know what I'm saying? Everyone wants to be the Bloomberg of something. But when I think about how you're like building this from the ground up, etc. Like you didn't even have to say it. It's like you are building the uh potentially the Bloomberg of hey, one day you may have a TV network and could we [laughter] have futures based on if we had benchmark? Well, like so that's a question. I mean this is that's clearly a theoretical way which is like you can't have a hedgeable tradable financialized market until you first have that index, right? something that everyone agrees on as a reference price at night when you dream about the future like could you see have you thought about the possibility of essentially okay this could be something that financial exchanges could now benchmark something against

</details>

**Aiden Johnson**: 你知道我也思考过这个问题，但这也非常棘手。因为你需要有大自然这个盟友来让事情变得更标准化，或者说更稳定。我猜测干草市场现在非常不稳定。我是说，太多的干旱、过多的降雨，或者过高的温度。所有这些不同的输入条件实际上都会对产量产生影响，这让它变得如此难以预测。所以我觉得，正因为这种波动性，这才是我们需要一个可对冲工具的原因。

<details>
<summary>Original English</summary>

**Aiden Johnson**: you know I have thought about it but it's also very tricky because you have to have mother nature on your side to kind of standardize the or like make it more stable I guess it's it's very unstable I mean too much drought uh too rain, you know, too much heat. Like all these different inputs can really have effects on outputs that just makes it so unpredictable, you know, like this is why we need a this is why we need a hedgeable instrument precisely because of this volatility. So I think um I think there's

</details>

**Tracy Aloway**: 确实这里大有可为。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah, there's something there.

</details>

**Joe Weisenthal**: 那里绝对有可挖掘的空间。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah, there's something there for sure.

</details>

**Aiden Johnson**: 我会很乐意成为去做那件事的人。从你们的角度来看……

<details>
<summary>Original English</summary>

**Aiden Johnson**: I I would I would love to be the guy that does that then. [laughter] So from your perspective,

</details>

**Tracy Aloway**: 比方说在任何行业中，不透明性对某些人来说是个好朋友，对吧？有很多企业就是因为客户不了解市场上的价格才能保持较高的利润率。消费者显然希望有更多的透明度，但有些人却从不透明中获益。在干草或类似产品的供应链中，或者在整个干草市场中，如果消费者和农民对价格有了更多的了解，理论上会有谁蒙受损失吗？

<details>
<summary>Original English</summary>

**Tracy Aloway**: let's say like you know opacity is a friend to some people in any business, right? There are a lot of businesses that sort of you know they can have higher margins because their customers aren't aware of the prices available like the and you know obviously the consumer wants more uh transparency but some people benefit from the opacity. Is there anyone in the supply chain of hay etc or in the market for hay that theoretically stands to lose out if customers are uh and farmers are more informed about prices?

</details>

**Aiden Johnson**: 是的，绝对有。这让我想起了我爸爸在我们老家的一个私人经纪公司工作，我实际上和他谈论过这件事。我问，“谁会在这种情况下蒙受损失？” 他说通常在商业中，尤其是在大宗商品中，中间商会最先感受到更加透明带来的后果。因为他们是在做交易的人，尤其是在干草市场上，很多时候是盲目交易，或者只是在猜测。我曾亲眼目睹过，我当时坐在那里，有人打电话给老板，大概就是问：‘157美元可以吗，比如，我可以以每吨157美元的价格买这么多捆干草吗？’ 他就回答说：‘是的，是的，那行。’ 所以这里并没有任何参考基准。没有透明度。这种情况可能对经纪人有利，或者这也可能让利润空间变得狭小。所以我确实认为随着透明度的提高，中间商永远会有所损失。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah, absolutely. So, this kind of ties back to my dad working for a private brokerage here in my hometown and I was actually talking about this with him. I said, "Who kind of who kind of loses out on this?" And he says typically in business, especially commodities, the middleman will always feel the u out or the outcomes of more transparency because they're the ones making deals u especially in the hay market kind of blindly and kind of just guessing. I mean, I call I I witnessed firsthand my I I sat there and someone called the owner and was just like, um, can I do 157, this is example, can I just do $157 um per ton for, you know, x amount of bales or tons? And he was like, yeah, yeah, that works. So, we're not going off anything here. There's no transparency. And that can either work for the broker or that can, you know, maybe make margins a little slimmer. So, I I do think that the middleman will always, you know, have something to lose with more transparency.

</details>

**Tracy Aloway**: 好了，来自 Haywire 的 Aiden Johnson，非常感谢你来到 OddLocks。这次对话真有趣。

<details>
<summary>Original English</summary>

**Tracy Aloway**: All right, Aiden Johnson of Haywire, thank you so much for coming on OddLocks. That was really fun.

</details>

**Aiden Johnson**: 是的，非常感谢你们邀请我。

<details>
<summary>Original English</summary>

**Aiden Johnson**: Yeah, I appreciate you guys having me on. [music]

</details>

### 后记与总结

**Tracy Aloway**: Joe，这是一次非常有趣的谈话。我的意思是，看到有人用 Vibe Coding 写出这种数据库，真是令人着迷，对吧？它似乎也为许多其他不同市场的低垂果实指明了方向。我想说的是，每当我们做这类农业或食品节目时，近年来的一个压倒性主题就是**波动性**。我们会遇到这些巨大的价格飙升，有时候又会大幅下跌，尽管下跌幅度往往不如最初的飙升那么大。所以你可以看到这里不仅需要价格透明，还可能需要某种对冲工具。

<details>
<summary>Original English</summary>

**Tracy Aloway**: So, Joe, that was a really fun conversation. I mean, it is fascinating to see someone like vibe code this kind of database, right? And it does seem like lowhanging fruit for a bunch of other different markets. What I will say though is whenever we do these like agricultural or food episodes, there seems to be this overriding theme in recent years, which is volatility, right? Like we're getting these big spikes. Sometimes we're getting big drops down, although often the drops are not as big as the initial spikes. And so you can see like there is a need here not just for price transparency but also potentially for some sort of hedging instrument.

</details>

**Joe Weisenthal**: 完全同意。绝对是的。我确实认为外面可能还有多得多的数据存在。我也认为这是一个非常有趣的 AI 故事，它明确展示了一种新型业务是如何诞生的，这种业务以前去经营是不划算的。如果你只靠大学生在业余时间去做，可能没有大把愿意花钱的订阅者。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Totally. Absolutely. I do think there's a lot of uh probably a lot more data out there. I also just think this is like a very interesting AI story specifically because it's a very clear example of here is a new type of business that might not have been economical to run. Like you know maybe there's not tons of subscribers willing to pay up. I think for sure you wouldn't have been doing it while you're in college.

</details>

**Tracy Aloway**: 不。所以专业版本。他的新闻简报有一个免费版本，我打算去订阅。还有一个专业版（Pro 版），你知道吗？我也会订阅那个。每月只要 14 美元。说实话 14 美元一个月并不算很多钱，即使你有一千个订阅用户也不算多。但如果只要两个人就能做到，如果你能将其中很大一部分自动化。仅仅因为 AI 使得获取数据、将它们转化为漂亮的图表等事情变得极其简单：维护一个数据库，甚至为人们提供 AI 访问权限。突然之间所有这些原本未被开发的市场理论上就可能被解锁，仅仅因为这些数据存在于那里，而且你可以以一种可用的形式将它呈现出来，而这在以前可能太耗费人力了。

<details>
<summary>Original English</summary>

**Tracy Aloway**: No. So the pro version. So he has a free version of his newsletter which I'm going to subscribe to. And there's a pro version and you know what? I'll subscribe to that too. It's just $14 a month. But okay, $14 a month is like not a ton of money. Even if you had like, you know, a thousand, you know, it's like it's not a ton. But if you could do it with two people and if you can automate a really big chunk of it. Yeah. and automated only because AI makes it really easy to do things like ingest the data, turn them into pretty charts and so forth, keep a database, give people AI access. Suddenly there's all these new market that markets that theoretically could become unlocked simply because here is data out there and you could put it in a usable form in a way that would have just been too laborious prior to it.

</details>

**Joe Weisenthal**: 是的，毫无疑问它是有效的。这是一次**生产力解锁**的明确示例，我坚信它是行得通的。有些使用 AI 做的事情可能没那么靠谱，但我相当确信它已经自动化了，你可以相当自信那是你能建立的东西。我觉得这真的很酷。哦，成为创始成员的价格在 6 月 30 日之后将上涨到每月 17 美元。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. Leelious. Leelius bales of no that was a bit forced. I'm sorry. But it's a it is a uh it is a clear example of like okay this is a productivity unlock and I have no doubt that it works. This is you know some things with AI like don't work as much but I'm pretty sure but automated you can feel pretty confident that that's something that you can build etc. Um I'm I'm very uh I think it's really cool. Oh, the price of being a founding member is going to rise to $17 a month after June 30th. So, get

</details>

**Tracy Aloway**: 随着干草价格的上涨而上涨。我们今天就聊到这里吧？

<details>
<summary>Original English</summary>

**Tracy Aloway**: rising along with the hay prices. Yeah. All right. Shall we leave it there?

</details>

**Joe Weisenthal**: 就到此为止吧。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Let's leave it there.

</details>

**Tracy Aloway**: 本期 Odd Thoughts 播客就到这里。我是 Tracy Aloway，你们可以在推特上关注我 Tracy Aloway。如果你喜欢 OddLotss，如果你喜欢我们谈论干草价格，请在你最喜欢的播客平台上给我们留下好评。记住，如果你是彭博社的订阅者，你可以完全免广告地收听我们所有的节目。你要做的就是在苹果播客上找到彭博社频道并按照那里的说明操作。感谢收听。

<details>
<summary>Original English</summary>

**Tracy Aloway**: This has been another episode of the Odd Thoughts podcast. I'm Tracy Aloway. You can follow me at Tracy Aloway. And if you enjoy OddLotss, [music] if you like it when we talk about hay prices, then please leave us a positive review on your favorite podcast platform. And remember, if you are a Bloomberg [music] subscriber, you can listen to all of our episodes absolutely adree. All you need to do is find the Bloomberg channel on Apple Podcast and follow [music] the instructions there. Thanks for listening. [music]

</details>

**Joe Weisenthal**: 我是 Joe Weisenthal，你们可以关注我的 stalwart。关注 Aiden Johnson，他的账号是 Aiden Johnson_。并且去看看 Haywire，域名是 Haywire.com。关注我们的制作人 Carmen Rodriguez (Carmen Arman)、Dashel Bennett (D-Bot)、Kale Brooks (Kalebrooks) 和 Kevin Lozano (Kevin Lloyd Lozano)。想了解更多 OddLots 的内容，请访问 bloomberg.com/odlots。我们有每日通讯和所有节目剧集，你还可以在我们的 Discord 上全天候讨论所有这些话题，地址是 discord.gg/odlotss。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And I'm Joe Weisenthal. You can follow me at the stalwart. Follow Aiden Johnson. He's at Aiden Johnson_. And check out Haywire. Haywire.com. Follow our producers, Carmen Rodriguez at Carmen Arman, Dashel Bennett at D-Bot, Kale Brooks at Kalebrooks, and Kevin Lozano at Kevin Lloyd Lozano. And for more OddLots content, go to bloomberg.com/odlots. We have a daily newsletter and all of our episodes, and you can chat about all these topics 24/7 in our Discord, discord.gg/odlotss.

</details>