---
author: The MAD Podcast with Matt Turck
date: '2026-07-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3FHsGiONOGw
speaker: The MAD Podcast with Matt Turck
tags:
  - physical-ai
  - data-digitization
  - infrastructure-construction
  - agentic-workflow
  - data-network-effect
title: 物理人工智能的跨越：从数字世界到现实世界的应用与基础设施建设
summary: 文章探讨了物理人工智能（Physical AI）的核心概念，即AI应用于物理世界的基础设施，如交通、建筑和公用事业。通过分析大规模数据采集（如车辆轨迹、传感器数据）如何克服传统数字化限制，并结合生成式AI实现对物理世界的推理和行动，文章强调了其在构建未来基础设施中的巨大潜力以及数据网络效应的重要性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/9 -->

### 物理AI：从数字世界到现实世界的跨越

**Matt Turk**: 这些可不是你在网上能找到的 token。你没法爬取 Reddit 然后了解建筑工地上发生了什么。Samsara 系统在一天之内，通常会多次覆盖美国 99% 的道路。我上周刚和一家大型能源公用事业公司一起去了现场。他们跟我分享了一个非常有趣的数据。他们说，在过去 125 年里，我们建设了一定规模的电网容量。而在未来 5 年内，我们将把这个数字翻三倍。我们谈论的是数百万辆汽车。我们相信，在过去一年里，我们帮助防止了大约 38 万起车祸和道路事故。

<details>
<summary>Original English</summary>

**Matt Turk**: These are not the tokens you're going to find online. Like you can't crawl Reddit and find out about what happened on a construction site. The Samsara system in a given day were driving 99% of the US roads usually multiple times a day. I was just in the field last week with a large energy utility. And uh they shared with me a really interesting stat. They said over the last 125 years we built a certain amount of grid capacity. In the next 5 years, we're going to triple that. We're talking about millions and millions of vehicles. We believe we helped prevent about 380,000 car crashes, road accidents in the last year.

</details>

**Matt Turk**: 嗨，我是 Matt Turk。欢迎收听 Matt 播客。我今天的嘉宾是 Sanjit Biswas，Samsara 的联合创始人兼CEO。Samsara 是一家市值 200 亿美元的公司，运营着可能是物理世界中最大规模的人工智能部署。数百万辆汽车，每年 25 万亿个数据点，每天覆盖美国 99% 的道路。我们谈到了物理AI、面向卡车司机和一线工人的智能体、人形机器人、自动驾驶卡车，以及为什么AI热潮本质上是一项基础设施建设项目。哦，如果你喜欢这期节目，或者你过去喜欢过其他节目，请帮我们一个忙，点击订阅按钮。这只需要一秒钟。新剧集会直接出现在你的信息流里，这对播客帮助很大。现在，有请 Sanjit。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome to the Matt podcast. My guest today is Sanjit Biswas, co-founder and CEO of Samsara, the 20 billion company running what might be the largest AI deployment in the physical world. Millions of vehicles, 25 trillion data points a year, driving 99% of US roads every single day. We talked about physical AI, agents for truckers and frontline workers, humanoids, autonomous trucks, and why the AI boom is really an infrastructure construction project. Oh, and if you're enjoying this episode or if you've liked others in the past, please do us a favor and hit that subscribe button. It takes a second. New episodes will show up right in your feed and it really helps the podcast. Now, here's Sanjit.

</details>

**Matt Turk**: 好的，Sanjit。在这个播客里，我们聊了很多关于AI模型和软件智能体的话题，但关于物理AI我们谈得相对较少。所以，这期节目感觉我们就是要讨论AI如何面对交通、建筑、工厂和公用事业这些物理现实。那么，也许我们从物理AI开始吧。这个词我们最近越来越常听到，通常是在人形机器人和机器人出租车这类语境下。从你的角度来看，什么是物理AI？

<details>
<summary>Original English</summary>

**Matt Turk**: All right, Sanjit. On this podcast, we've talked a lot about AI models and software agents, but we have spoken a little less about physical AI. So, this feels like the episode where we're going to talk about how uh AI is confronting the physical reality of transportation and construction and plants and utilities. So, maybe let's start with physical AI. That's a term that uh we hear about more and more often these days, typically in the context of like humanoids and robot taxes. from your perspective, what is physical AI?

</details>

**Sanjit Biswas**: 是的，完全正确。嗯，首先，Matt，谢谢邀请我上你的节目。嗯，我认为物理AI实际上就是将AI应用于物理世界。所以，如果你想想我们星球的基础设施，它远不止是你能看到 Waymo 机器人出租车的道路。嗯，它还包括建筑工地、电网，实际上就像是街道下面所有的管道系统。它就是外面的一切。我认为物理AI面临的有趣挑战是，它没有被数字化。嗯，对吧？这是一个前沿领域，你没有几十年的数据位可以用来推理、token化并快速吸收，这使得它非常迷人，因为其中蕴藏的价值非常巨大。嗯，所以我们从几个不同的角度来思考它。我们考虑数字化一些东西，比如来自GPS追踪的位置信息。当然，我们也考虑使用摄像头作为传感器。这样你就可以用非常丰富的方式来理解物理世界，尤其是当你摄入大量视频片段时。嗯，如果你想想你能从中获得多少帧画面，那数量是非常可观的。然后还有很多其他类型的数据源，比如天气数据，了解道路上降水情况。嗯，你可以考虑限速数据，世界上有很多很多的物理方面，当你把它们放在一起，当你把它们融合在一起时，嗯，就能释放巨大的价值。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah, absolutely. Well, first Matt, thanks for having me on your show. Um, I would say physical AI is really the application of AI to the physical world. So, if you think about the infrastructure of our planet, it's way more than just the roads where you might see a Whimo robo taxi. Uh, it's the construction sites, it's the electrical grid, it's really kind of like all the plumbing that's under the street. It's it's it's everything out there. The interesting challenge, I think, with physical AI is that it's not digitized. Uh, right? like this is the frontier where you don't have decades of bits that you can reason over and tokenize and and quickly ingest and that makes it really fascinating because the amount of value is is kind of that's trapped is really significant. Um so we think about it in a few different ways. We think about um you know digitizing things like location from GPS tracking. Of course we think about using cameras as sensors. So you can use that to understand the physical world in a pretty rich way especially when you ingest lots and lots of basically video footage. Uh if you think about how many frames you get from that it's really significant. And then there's a lot of other uh kind of data sources uh whether it's like weather sources of like what happened with precipitation on all the roads. um you can think about speed limit data like there's lots and lots of physical aspects of the world that uh when you put them together when you fuse them together uh there's a huge value unlock

</details>

**Matt Turk**: 嗯，也许跟我们讲讲AI是如何改变整个讨论的。嗯，你知道，工业自动化显然已经进行了几十年甚至几个世纪，然后还有一整波物联网浪潮，而且众所周知，你们作为上市公司的股票代码就是 IoT。Navas AI 嗯，我，现在的时刻有多么不同？

<details>
<summary>Original English</summary>

**Matt Turk**: and um maybe walk us through how AI changes that whole discussion so uh you know there was industrial automation obviously that's been going on for decades and perhaps centuries then there was a whole wave of IoT and famously your ticker as a public company is IoT and Navas AI I um how how different is the current moment?

</details>

**Sanjit Biswas**: 是的。嗯，你提到几个世纪很有意思，因为那正是思考物理基础设施的正确时间尺度，对吧？一直追溯到罗马时代，那时就已经有非常庞大的基础设施了。所以很多流程，比如如何维护一条道路，已经存在了非常非常久。其中很多流程是手动的，对吧？比如，我们去检查道路状况。我们了解它上次是什么时候被修过的，你知道，我们把它挖开看看能找到什么。如果你想想将其数字化，然后使用传感器数据的能力，这是一个巨大的解锁。所以问题变成了，你如何获取数据？然后你如何处理它？然后你如何得出有意义的见解，或者实际上是一个行动，比如我们应该怎么做？嗯，我认为现在这已经成为可能了。过去二十年左右，主要是关于报告，比如我们如何摄入数据，然后给你一个很酷的表格，这样你就可以查看它，进行推理，弄清楚。现在，在过去两三年里，真正了不起的是，AI系统能够推理这类信息了。它们可以寻找其他上下文线索，然后给你见解，现在我们实际上看到了生成式AI，当然，它可以为你采取行动，也许可以安排要完成的工作，或者开始自行执行部分工作。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah. Well, it's interesting you mentioned centuries because that is like the right time scale to think about physical infrastructure, right? All the way back to like the Roman era, like there's pretty significant infrastructure out there. So many of these processes of like how do you maintain a roadway have been in place for a very very long time. A lot of that process was manual, right? Like let's go inspect the condition of the road. let's understand when it was last worked on, you know, let let's kind of dig it up and see what we find. If you think about the ability to digitize that and then use sensor data, it's a huge unlock. So the question becomes how do you get the data? Then how do you process it? And then how do you come up with a meaningful insight or really an action like what should we do about it? Uh and that's that's I think now possible. The last call it two decades was around reporting like how do we ingest the data and give you a really cool like table so you can look at it and reason about it, figure it out. Now what's awesome really in the last two three years is the AIS are able to reason about this kind of information. They can look for other context clues and then give you the insight and now we're actually seeing a Gentic AI of course which is it can take an action for you can maybe schedule the work to be done or or start performing some of the work itself.

</details>

**Matt Turk**: 为什么硅谷没有完全投入到那个问题空间呢？我的意思是，感觉我们一直在谈论聊天机器人，然后是更多在数字和软件领域的智能体。嗯，显然有特斯拉，有你知道的，正在建造的人形机器人。嗯，但这是否意味着所有这些都必须先发生，然后才能应用到物理世界，还是说物理世界本身就是一套完全不同的挑战？

<details>
<summary>Original English</summary>

**Matt Turk**: Why hasn't um Silicon Valley been all over that problem space? I mean it feels like we've been talking about chatbots and then agent more in the kind of digital and software realm. Uh I mean obviously there's Tesla there's there's you know humanoids being being built. Um but is that is that did all of that need to happen before this could be applied to the physical world or is or is the physical world just like a different set of challenges altogether?

</details>

**Sanjit Biswas**: 你知道，我认为这波AI浪潮从数字世界开始，这完全合理。我们拥有所有的数据位。我们拥有，你知道，拍字节的数据可以用来推理，而且有很好的训练集。所以，你想想启动这些模型所需的数万亿个 token。物理世界要混乱得多，而且它还涉及硬件组件。有句俗话说，硬件很难，对吧？比如，这些东西必须在环境中经久耐用。它必须通过不可靠的网络传输数据。嗯，它必须部署到一线，这需要大量繁琐的工作，对吧？嗯，物理硬件安装，让数百万一线工人采用新技术，比如将其整合到他们的日常工作中，这基本上不像我们在数字世界看到的那样是唾手可得的果实。话虽如此，这是全球经济中巨大的一部分，对吧？所有这些行业，它们约占世界GDP的40%到50%。因此，这是一个你可以产生巨大影响的领域，但你必须真正卷起袖子，比连接到可能已经存在的大型数据库要投入得多。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: You know, I think it makes complete sense where all of this AI wave has started, which is in the digital word world. We had all the bits. We had, you know, you know, petabytes of data to reason over and there's a great training set. So, you think about all the trillions of tokens that were needed to get these models bootstrapped. The physical world is much messier and there's also a hardware component to it. And there's kind of this saying of like hardware is hard, right? Like this stuff has to like hold up in the environment. It's got to relay the data over like unreliable networks. uh it has to be deployed to the front lines and that requires a lot of sort of messy work, right? Um physical hardware installations, getting millions of frontline workers to adopt new technologies like integrate it into their day-to-day work and it's basically not as much lowhanging fruit as what we've seen kind of in the digital world. All that being said, it's a massive part of the global economy, right? All these industries, they make up about 40 50% of world GDP. And so it's an area where you can have tremendous impact, but you have to really roll up your sleeves and get much more involved than uh kind of connecting to a large database that may have already existed.

</details>

**Matt Turk**: 说它也是一个更不容错的环境，错误可能严重得多，这样说公平吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Is it fair to say that it's also a much more unforgiving environment where mistakes are potentially much much more consequential?

</details>

**Sanjit Biswas**: 绝对是的。当然，在很多物理操作中，你面对的是人的生命，这是一个可以产生巨大影响的领域。所以，如果你能建立安全系统来保护工人的安全，那是一件好事。但你也必须小心，不要以某种方式将风险引入到局面中。嗯，这方面还有其他方面，比如这些是数字技术，所以我们希望确保它们从网络安全的角度是坚固的，比如它们不会引入网络安全风险，但实际上，物理世界是一个非常危险的地方。想想一个建筑工地，对吧？有很多像土方设备，重达数吨，对吧？真的是非常危险的东西。能见度也比较低。嗯，所以，你知道，操作这些设备的操作员正在承担一些风险。工地上的人们承担着很大的风险。所以，这本身就是一个高风险的环境，我们的问题一直是，我们能否找到利用数据来降低风险的方法。所以，我们把风险视为机遇，而不是挑战。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Absolutely. So of course you're dealing with human life in a lot of physical operations and that's an area for tremendous impact. So if you can build safety systems that keep workers safe, that's a great thing. But you also have to be careful that you don't somehow introduce risk into the into the picture. Um there are other sides of that too which is like these are digital technologies so we want to make sure they're hardened from a cyber perspective like they're not introducing cyber security risk but really practically um the physical world is a pretty dangerous place. Think about a construction job site, right? There's a lot of like earthmoving equipment multi-tonon, right? Like really dangerous stuff. It's kind of low visibility. Um and so you know the operators that are are operating that equipment are taking some risk. The people on the site are taking a lot of risk. So it's inherently a risky environment and our question has been can we find ways to make it less risky using data. So we see that the risk as the opportunity as opposed to the challenge.

</details>

**Matt Turk**: 好的。你刚才提到了其中的一些内容，但嗯，为了让我们在对话早期就有背景了解，嗯，也许给我们一个关于 Samsara 是做什么的 60 秒介绍。

<details>
<summary>Original English</summary>

**Matt Turk**: All right. So you alluded to to some of this but um for contextual awareness early in this conversation uh maybe give us a 60cond on on on what sensor does.

</details>

**Sanjit Biswas**: 是的。Samsara 是一家为物理世界服务的技术公司。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah. So Samsara is a technology company serving the world of physical

</details>

<!-- chunk 2/9 -->

### 从硬件到AI：数字化实体运营

**Sanjit Biswas**: 所以，想想那些建筑公司、能源公用事业、供应链和物流公司，它们驱动着整个地球的运转。我们帮助它们实现运营的数字化。这结合了硬件——比如GPS追踪器、行车记录仪、资产追踪器，各种不同的设备；还有云服务，用来摄取所有数据；而现在，我们加入了AI和应用，真正形成闭环，对吧？帮助人们采取某种行动，或者理想情况下，自动化所需的行动。我们发现，从具体、真实世界的问题入手，然后随着时间的推移逐步扩展，是很有帮助的。所以我们最初是从车队开始的——几乎所有这些行业都拥有数万辆需要用来完成工作的车辆。但随着时间的推移，我们现在已经扩展到一线运营，我们能够在我们的平台上融合来自不同来源（包括第三方来源）的所有这些数据，为客户释放巨大的价值。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: So think about those construction companies, the energy utilities, the supply chain and logistics companies that power the planet. Uh we help digitize their operation. So that's a combination of hardware. So think uh GPS trackers, dash cameras, asset trackers, all kinds of different devices. Uh cloud services to ingest all the data and then now AI and applications to really close the loop, right? to help people take some kind of action or ideally automate the action that's needed. Um what we found is it's helpful to start with just tangible real world problems and then expand over time. So where we started was around fleets of vehicles almost all of these industries that have you know tens of thousands of vehicles that they need to perform their work but uh over time we've expanded now into those frontline operations and we're able to fuse all this data together from different sources on our platform third party sources and and unlock tremendous amounts of value for the customer.

</details>

**主持人**: 好的。你刚刚突破了20亿美元的ARR，对吗？

<details>
<summary>Original English</summary>

**Host**: Okay. And uh you just crossed two billion in AR is that is that correct?

</details>

**Sanjit Biswas**: 没错。你是一家盈利的公司，并且以30%的速度增长。这个指标对吗？好的。真是一家非常非常棒的公司。你还能分享其他指标吗？比如你们处理的数据量，或者让人们了解一下公司的规模？

<details>
<summary>Original English</summary>

**Sanjit Biswas**: That's right. with uh you're a profitable company growing at 30%. Is that that's correct the right metrics? Okay. Just a beautiful beautiful company. Any other metrics you can share about the the kind of the volume of uh data points you're seeing or just to give people a sense for the scale of the of the company?

</details>

**Sanjit Biswas**: 好的。在数据点方面，这些数字即使对我这个每天身处其中的人来说，也感觉有些抽象。但我们谈论的是25万亿个数据点。GPS、视频、第三方API集成，各种数据流入系统。例如，有数百万辆汽车。我们谈论的是，你知道，每天有数百万一线工人在使用我们的应用。就影响力而言，这是我们关注的另一组数据点，那就是：所有这些技术如何在世界上产生影响力？我们相信，在过去一年里，我们帮助防止了大约38万起车祸，也就是道路交通事故。这对我们来说意义重大，因为作为工程师和产品构建者，我们能够以这种方式对世界产生重大影响。我们通过优化路线、减少发动机空转等看似简单的事情，帮助避免了数十亿磅的二氧化碳排放。这些事情技术上可能很简单，但执行起来非常重要。很酷的是，你能看到这种真实世界的影响力。是的，那是一个疯狂的数字。38万，这是因为你们能够检测到司机是否疲劳之类的。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah. Um so on the data points side of things, these are numbers that feel abstract even to me and I live them every day. But we're talking about 25 trillion data points. GPS, video, thirdparty API integrations, all kinds of data flowing into the system. Millions and millions of vehicles, for example. Uh we're talking about, you know, millions of frontline workers that are using our apps every day. Um and in terms of impact, that's the other sort of set of data points we look at, which is like, well, how is all this technology having impact in the world? Uh we believe we helped prevent about 380,000 car crashes, uh you know, road accidents in the last year. That's meaningful to us because as engineers and product builders, we are able to have like significant impact in the world this way. Uh we've helped uh avoid the emission of billions of pounds of CO2 by helping do things like optimize routes and reducing you know engine idling things that seem simple but uh you technologically simple perhaps but the execution matters a lot. What's cool is you see that real world impact. Yeah, that that's a crazy number. 380,000 and that's because uh you're able to detect uh whether uh a driver can get sleepy or that kind of stuff.

</details>

**主持人**: 你说得对。是的。所以有很多不同的因素会产生风险。你知道，我们对自动驾驶、机器人出租车以及我们在前沿领域看到的一切感到非常兴奋，但在很多这样的行业，比如重型卡车运输或建筑行业，人们工作时间非常长。你知道，也许他们已经在野外工作了10到12个小时，天气很热，所以他们筋疲力尽。所以，疲劳绝对是其中之一。你通常也会看到，总的来说，夜间事故更多，对吧？因为道路能见度较低。在下雪或下雨后的雾天条件下，也会发生事故，诸如此类。所以，当我们看到风险增加时，我们能够通过警告司机来帮助预防很多风险。我们可以提供一些实时反馈，这有助于他们保持更高的警觉性和意识。我们还可以通过指导来改掉人们养成的一些坏习惯。嗯，这是一个有趣的统计数据，但在美国，大约有10%的人不经常系安全带。这因州而异，因行业而异，但这是你能做的改善风险结果的最重要的事情之一，就是简单地系上安全带。这很有道理，因为有时人们只是短途出行，或者他们分心了。但那个小小的提醒有助于挽救生命，对吧？所以这是一个简单的方法。放下手机是另一个，对吧？当你查看手机时，很多人都有这个习惯。嗯，如果你的车在行驶，它可以移动一个足球场的长度，这很难想象，因为你可能会想“我只是快速看一眼那条消息是什么”，但当你抬起头时，你已经移动了100码，对吧？这就是我们可以通过实时警报来避免的那种风险。

<details>
<summary>Original English</summary>

**Host**: You got it. Yeah. So there's so many different factors that produce risk. And you know, we're very excited about autonomy and robo taxis and everything that we're seeing sort of on the frontiers, but there are a lot of these industries like um in heavy duty trucking or construction, people work very long shift. Um you know, maybe they've been out in the field for 10 12 hours, it's been hot and so they're exhausted. So you know, fatigue is definitely one of them. U you also tend to see more accidents in general at night, right? Because the roads are less visible. you see accidents in foggy conditions after it snows or rains, things like that. So, we're able to help prevent a lot of risk by warning the driver of when we see, you know, kind of the risk increasing. We can provide some real-time feedback and that helps them be much more alert, much more aware. And we can also coach away some of the bad habits that people develop. Um, this is an interesting stat, but in the US, approximately 10% of people don't regularly wear their seatelt. And that, uh, varies by state, it varies by industry, but that's like one of the biggest things you can do to improve your risk outcome is just simply put on the seat belt. And it makes sense because sometimes people are doing a quick trip or that, you know, they're distracted. But that little reminder helps save lives, right? So that's one simple one. Putting down your mobile phone is the other one, right? When you take a look at your mobile phone, like lots of people have this habit. um your your car if you're driving can move the length of a football field and that is hard to think because you're like I'm just taking a quick look to see what that message was about but then you look up and you've moved 100 yards, right? That's the kind of risk avoidance that we can create with real-time alerting.

</details>

### 从学术研究到创业征程

**主持人**: 好的，太好了。我想花几分钟时间聊聊你的创业故事，以及你是如何创立这家公司的。据我所知，你的经历是从斯坦福到MIT，再到Meraki，最后到Samsara。

<details>
<summary>Original English</summary>

**Host**: Okay, great. I'd love to spend a few minutes on on your entrepreneurial story uh leading to the creation of the company which I believe was Stanford to MIT to Merke uh Moroi.

</details>

**Sanjit Biswas**: 是的。请带我们回顾一下这一切是如何发生的。你是在学生时期还是博士毕业后创立了第一家公司？

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah. This is like walk us through like how it all came about. You started the first company as a student or right after your PhD.

</details>

**Sanjit Biswas**: 没错。实际上是在我们读博期间。我和我的联合创始人John是在MIT读博时认识的，那是20多年前的事了。我现在这么说是因为我们都老了。但那是一个有趣的研究项目，我们当时在做这个。那是在Wi-Fi作为一种新技术刚刚兴起的时候。我们在21世纪初建立了一个名为Roofnet的研究项目，基本上覆盖了剑桥市，也就是MIT和哈佛之间的区域，提供免费Wi-Fi。那真的很令人兴奋。这是一个动手实践、非常实用的研究项目。我们在路由协议以及如何构建网络方面做了大量学术研究。但我们的第一家公司Meraki就源于那个项目。我们认为Wi-Fi可以连接这么多人，这个想法非常酷，也非常有用。我们想帮助其他人构建大型网络。所以，我们基本上把那个研究，现在我会用“提炼”这个词，我们把它浓缩成一个“盒子里的系统”，其他人可以用它来构建网络，然后我们开始提供这个产品。那就是Meraki。老实说，我们当时有点把它看作一个项目，甚至没把它当成一家公司。我们在波士顿白手起家。后来我们搬到了加州。这很吸引人，因为那是2006年，20年前。Wi-Fi是一种全新的、萌芽期的技术，并且存在一些真正的挑战，对吧？如何做访客接入？如何做大规模网络？如何应对人们开始使用当时全新的YouTube？现在很难想象，对吧？但这让我们体会到解决真实问题有多么有趣。而且，我们在网络方面有非常深厚的基础。我们有很多研究生院的朋友，我们招募他们一起创办了那家公司。所以我们起步很快。我们开始看到这些设备在世界各地被使用，Meraki就这样不断成长、壮大。它的收入每年都在翻倍。嗯，那就是我们创业之旅的开始。这个开始有点偶然。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: That that's correct. Um actually during our PhD. So my co-founder John and I we met at MIT as PhD students uh over 20 years ago. I I now cap it because we're just old. Uh but it was it was a fun sort of research project that we worked on which was um this was around the time that Wi-Fi was emerging as a new technology. We built a uh research project called roofnet. We covered essentially the city of Cambridge, the area between MIT and Harvard with free Wi-Fi in the early 2000s. So that was really exciting. It's like a hands-on kind of very practical research project. We did a bunch of academic research on routing protocols and you know how to build the network. Um but the first company Moroi came out of that project which was we thought it was tremendously cool this idea that Wi-Fi could connect so many people just incredibly useful. We wanted to help other people build big networks. And so we essentially took that research um and and now I would use the word distill like we condensed it down to uh you know run in a box that other people could build networks out of and then we started essentially making that product available. So that was Moroi. Um to be honest we kind of thought of it as a project like we weren't even thinking of it as a company. Uh we kind of bootstrapped the business in Boston. We ended up moving to California. Um and it was fascinating because this is 2006 like 20 years ago. Wi-Fi was a brand new kind of naent technology and there were some real challenges, right? How do you do guest access? How do you do networks at scale? How do you deal with people starting to use YouTube which was brand new back then? Like hard to imagine, right? Um but that kind of exposed us to how fun it was to solve real problems. And um we had a huge, you know, kind of deep background in networking. We had a lot of friends from grad school that we recruited to start that company. And so we got off the ground quickly. we started seeing these devices get out in the world and Moroi ended up kind of just growing and growing and growing. It was doubling in revenue every year. Um so that was the beginning of our entrepreneurial journey. It was a little bit of an accidental start.

</details>

**主持人**: 当你创立Samsara时，与你之前在Meraki做的事情相比，那是一个全新的领域。据我所知，你们之前在这方面并没有背景。那么，作为一个企业家，你是如何在一个自己毫无背景的领域成为专家的呢？

<details>
<summary>Original English</summary>

**Host**: And when you started Samsara, you know, as opposed to to what you did in Moro, that was a brand new area where u as far as could tell from what I read like you guys didn't have a prior background in that. So like how does one become an expert as an entrepreneur in a domain that they don't have a background in?

</details>

**Sanjit Biswas**: 是的，你说得很对。我们从未在装卸码头、仓库或建筑工地待过。但我们一直对它们很着迷，我认为这确实是关键。嗯，这就像一种书呆子式的好奇心，比如“电网到底是如何工作的？”对吧？我有电气工程背景。我一直对此很着迷。或者像供应链，如果你只是好奇“那个亚马逊包裹，它走了多远？货物存放在哪里？”所有这些问题都让我们着迷。和Meraki类似，我们并不是一离开思科就打算创办这家公司。我们当时正处于一段非常紧张的时期。但好奇心最终战胜了我们，我们开始阅读大量关于这方面的书籍，试图了解这个世界。嗯，挑战在于……

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah, you're you're very right. We had never spent time like in a loading dock or warehouse or like in a construction yard. Um but we were always fascinated by them and I think that was really the key is uh this is just like nerdy curiosity of like well how does electrical grid really work? Right? I have an electrical engineering background. I was just always kind of like fascinated by this. um or like supply chain if you're just curious about like well that Amazon package like how how far did it travel like you know where where were the goods stored like all of those kinds of questions were fascinating to us and um similar to Maro we weren't intending to start this company right out of Cisco like we had been kind of on this pretty intense run uh but the curiosity kind of got the better of us and we started reading lots of books about this and you know like just trying to learn about the world um the challenge

</details>

<!-- chunk 3/9 -->

### 从硬件到云端：Samsara 的产品架构

**Sanjit Biswas**: 但实际操作是你在书本上学不到的，你必须亲自到现场去。而要做到这一点，你需要一个理由，一个借口。所以我们想，也许我们可以为这些行业提供帮助。因为就像我之前说的，我们计划的基础设施非常庞大，那里一定有值得解决的有趣问题。所以我们几乎是白手起家创办了这家公司，经历了非常陡峭的学习曲线。我必须说，作为第二次创业的创业者，我很庆幸我们有那段经历。因为如果我们回到过去，很可能会过度依赖之前的经验，然后说：“嘿，事情就该这么做”或者“我们在 Meraki 就是这么做的”。但在 Samsara，客户群体不同了。我们更多地服务于运营领域，而不是那种技术买家。我们采用直销模式，直接与客户互动，而不是通过渠道。这种重新开始足以让我们回归初心，我认为这对大多数公司来说都非常重要。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Though, is you can't learn about it in a book. Like you actually need to go on site and to do that you need a reason, you need an excuse essentially. And so we said, well maybe we can be helpful to these industries, right? Because, like I was saying earlier, it's the infrastructure of our plan so massive, there have to be interesting problems to solve there. So we kind of started this company market first, very steep learning curve. And I have to say as a second time through entrepreneur, I'm really glad we had that experience because had we gone back and it we probably would have overweighted our prior experience and said, "Hey, this is how it's done or this is how we did it at Meraki." Uh, with Samsara, it's a different customer. We serve the world of operations much more than the kind of technical buyer. Um, we sell direct, so we interact directly with our customers versus via channel. And that reset was enough for us to kind of go back to beginner's mind, which I think is also very important for most companies.

</details>

**主持人**: 好的，谢谢你的分享。我们来深入探讨一下产品本身。根据我们目前所说的，你有一个硬件层，也就是传感器。打个比方，如果不对请打断我，传感器就像是耳朵和眼睛。然后你有一个软件层，我想现在加上AI，就像是大脑。而你最近新增的，我们稍后会详细讨论，是一个能量层，就像是执行动作的手臂。你大致是这么想的吗？

<details>
<summary>Original English</summary>

**Host**: Okay. All right. Thank you for all of this. Uh, let's deep dive uh into the product itself. So uh based on what we've said so far um you have a hardware layer which is the sensors. So uh just to use an analogy and and and stop me if that doesn't seem right but that would be the the sensors so the ears and the eyes. Then you have a software layer. I guess now with AI which would be the the brain. Mhm. And you just added recently and we're going to talk a bunch about that you added an energetic layer which would be uh the the arms for the action. Is that is that directionally uh how you think about it?

</details>

**Sanjit Biswas**: 是的。我想说，每一层都有一些连接组织。以硬件为例，我桌上就有一个硬件，这是我们传感器的一个例子。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah. And I would say um you know every single one of those layers has some connective tissue attached to it. So if you think about the hardware, I've got hardware on my desk of course and so this would be an example of one of our sensors.

</details>

**主持人**: 这是什么？

<details>
<summary>Original English</summary>

**Host**: So what is this? What is this?

</details>

**Sanjit Biswas**: 这是我们称之为资产标签的东西。你可以把它放在一件建筑设备上。它里面有一个加速度计，所以可以知道它被移动了多少。它有一个蓝牙无线电，功率比你在消费端可能用到的要强一些。比如你的AirPods用的是蓝牙，而这个是工业级的蓝牙。它里面有一块电池，而且设计得非常坚固。你可以随便摔打它，甚至可以用卡车从上面碾过去，它还能继续工作。这一层有硬件，也有在上面运行的固件。它有网络连接，我提到了蓝牙。所以它连接到数百万个Samsara网关，以及数千万部可以作为我们中继点的手机和手持设备。然后我们能够以安全的方式将数据传送到云端。这就是数据采集端，对吧？从加速度计的运动数据，通过蓝牙层，再到云端。但到了云端之后，你需要整理这些数据，因为信号来自四面八方。你需要能够以一种非常有条理的方式处理它，然后才能喂给AI。因为如果你给AI的数据噪音很大，信噪比就会很低。所以我们需要获取干净的数据。然后，用你的比喻来说，那就是大脑。我们在那里存储数据、处理数据，你可以将这些洞察呈现给最终用户。而代理（Agentic）的部分是，你可以直接采取行动。比如改变一个安全设置，比如说，因为纽约下雨，我们要求整个车队增加跟车距离，而在晴朗的日子里则不用。这种改变通常需要人工介入。我们现在发现，AI可以非常一致地做到这一点，并且能以人们无法达到的规模执行，因为你需要有人一直坐在那里监控数千辆车的所有设置，这不太现实，所以以前根本做不到。这大概就是你说的“手臂”，也就是执行动作的那部分。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Uh this is what we call an asset tag. So, you could put this on a piece of construction equipment, right? Um, it's got an accelerometer in there, so it can tell, you know, how much it's been moving. It's got a Bluetooth radio that's a little bit more powerful than what you've probably used on the consumer side. So, you know, your AirPods have Bluetooth. This is a industrial-grade Bluetooth. Um, it's got a battery inside and then it's built to be super tough. So, you can like beat this thing up. You can drive over it with the truck and u, you know, it'll it'll continue to operate that layer. It has hardware, but also has firmware that's running it on it on it. It's got network connectivity. I mentioned Bluetooth. So, this connects to the millions of Samsara gateways, tens of millions of phones and handsets that can act as kind of a relay point for us. And then we we're able to get that to the cloud in a secure way. So, that's the data capture side, right? Going from motion like the accelerometer into the Bluetooth layer into the cloud. Um, but from there, you need to organize it because like you got signals coming from all over. uh you need to be able to like operate on it in a pretty methodical way and that's what's going to feed the AI because if you give the AI pretty noisy data you'll get you know it's like less signal noise ratio so we need to get get clean data in um and then to use your analogy that's the brain right like that's where we we store it we operate on it um you can surface those insights to the end user or the agentic piece is you can just take an action right um maybe change a safety setting right like say hey we're gonna ask our entire fleet in uh New York because it's raining to increase the following distance versus on a bright sunny day, right? Um that kind of change would have normally required a human in the loop. We're now finding that the AI can do it very consistently and uh can do it at scale that people wouldn't be able to get to because you'd need someone just sitting there monitoring all the settings for thousands of vehicles. Not very practical. So, it just doesn't get done. And that's the maybe the arms the kind of action side of things.

</details>

**主持人**: 好的，太好了。这就是整体架构。那么，回到硬件层。你给我们看了一个资产追踪器。你说它通过蓝牙连接。是低功耗蓝牙吗？我有一阵子没关注这些东西了，但它不像LoRa那种框架……

<details>
<summary>Original English</summary>

**Host**: Okay, great. All right. So that's the overall architecture. Um, so going back to that hardware layer. So you showed us an asset tracker. Uh, you said it connects via Bluetooth. That's Bluetooth. Uh, it's been a while since I looked at at at all the things, but like it's not like LoRa one and that that kind of uh frameworks and

</details>

**Sanjit Biswas**: 是的，这是低功耗蓝牙（BLE）。如果你熟悉你健身设备或AirPods上用的那种BLE，就是那种东西。蓝牙这些年发展了很多，它不断被扩展，吸收了许多其他标准的优秀特性。所以我们的追踪器可以达到很远的通信距离。然后我们在此基础上增加了一层安全措施，以确保我们保护标签所附着物品的隐私和安全。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yes, this is it's Bluetooth low energy. uh if you're familiar with the BLE that you you know would see on your uh fitness device or your AirPods, that kind of thing. So, uh Bluetooth has come a long way over the years, it's it's kind of gotten added on to and it's it's picked up a lot of the great characteristics that many of these other standards had. So, we can get a lot of range out of these trackers. And then we add a layer on top of that of security. How do we make sure that uh we preserve the privacy and the security of the the the tag that it's being applied to?

</details>

**主持人**: 它是用电池供电的。你说一个追踪器能用多久？续航有多长？

<details>
<summary>Original English</summary>

**Host**: And it's powered by battery. You said like how much autonomy would a tracker have? Like how long does it last?

</details>

**Sanjit Biswas**: 这个特定的追踪器大约能用3年。我们还有其他能用6年以上的。我们甚至有一个非常小的版本。我桌上也有。不知道你能不能看到，这就像一个追踪标签。它基本上就是个贴纸。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Uh this specific one would last about uh 3 years. We have others that last 6 plus years. Uh we even have a really small form factor one. I've got these on my desk as well. And I don't know if you can see them, but this is like a tracking label. So we're talking about a sticker.

</details>

**主持人**: 这就是几周前你在拉斯维加斯刚发布的那款。对吧。

<details>
<summary>Original English</summary>

**Host**: That's the one you just launched in Vegas a few weeks ago. Okay.

</details>

**Sanjit Biswas**: 没错。这些大约能用45天左右。足够单程运输使用了。而且它们是一次性的。它们里面没有锂离子电池。所以你可以直接撕下来，贴上，追踪，然后丢弃。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Exactly. So these last about uh 45 days or so. Um so long enough for shipments to kind of go one way. And then these are disposable. So, um, they don't have lithium-ion batteries in them, for example. So, you can just, uh, peel them, stick them, track them, and then dispose of them.

</details>

**主持人**: 不过，如果可以的话，再对着镜头展示一下。

<details>
<summary>Original English</summary>

**Host**: But, show them again on camera if if you will.

</details>

**Sanjit Biswas**: 好的。这是一个……

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah. This is a

</details>

**主持人**: 所以，这真的就是一个贴纸。里面有什么？

<details>
<summary>Original English</summary>

**Host**: So, this So, this is literally a sticker. So, what's what's in it?

</details>

**Sanjit Biswas**: 里面有什么？在镜头前很难看清，但基本上就是一些电池，当然还有运行我们固件的蓝牙芯片。它就是这样发出信号，告知其位置的。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: What's in it? Um, it's hard to make out on camera, but there's basically some batteries and then, of course, the Bluetooth chip, right, as running our firmware. Um and that is how it it beacons up essentially its signal of where it is.

</details>

**主持人**: 你们是怎么做到这么薄、这么小的？创新点就在于微型化吗？还是说……

<details>
<summary>Original English</summary>

**Host**: How are you able to get such a flat and small um like form factor? Is that is that where the innovation is like just miniaturization or like what what's the I

</details>

**Sanjit Biswas**: 我想说，对我们而言，这是系统级的创新。我们没有自己制造电池，也不生产硅片或芯片，但我们与合作伙伴一起，将所有部件整合在一起。然后我们拥有网络，你可以把它想象成路上数百万辆汽车，所有运行Samsara系统的人，他们形成了一个社区，并相互中继信号。你可能在消费端见过类似的东西，比如苹果的AirTag，就是那种生态系统概念。我们应用的是它的工业级强化版。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: I would say for us it's systems innovation. We did not build the battery. We don't make the silicon or the chip but we work with partners to integrate all this together. And then we have the network which is essentially think about um you know the millions of vehicles on the road all the people running the Samsara stack they form a community and relay signals for each other. Um and you've actually probably seen this in the consumer side with the Apple Air Tag kind of that concept of an ecosystem. We apply basically the industrial strength version of that.

</details>

**主持人**: 好的，非常酷。那么在硬件层你们还有什么？我读到过一些车载网关。这些是做什么用的？

<details>
<summary>Original English</summary>

**Host**: Okay. Very cool stuff. So what else do you have at the hardware layer? Uh I read some more vehicle gateways. What what what does this what do those do?

</details>

**Sanjit Biswas**: 是的，可惜我没把我们生产的所有硬件都放在桌上。但车载网关，你可以把它想象成一个黑匣子，安装在卡车、建筑设备或任何移动资产上。它是一种不同类型的数据采集器。它从发动机电脑收集诊断信息，包括油耗、故障码、驾驶员脚是踩在油门上还是刹车上等等。这些信息都在诊断端口上。所以我们能够获取这些信息。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yeah. Unfortunately, I don't have all the hardware that we make on my desk, but the vehicle gateway, think of it as a black box that goes on a truck or a piece of construction equipment or basically any kind of moving asset. Um, that is a a different type of collector, right? So, it collects diagnostic information from the engine computers and that's everything from uh you know, how much fuel is it consuming to does it have fault codes to uh was the driver's foot on the accelerator or the brake. That's all there on the diagnostic port. So we're able to ingest that information.

</details>

**主持人**: 这就像某种长时间序列数据。

<details>
<summary>Original English</summary>

**Host**: It's like a long time series of some sort.

</details>

**Sanjit Biswas**: 是的。我们需要收集并整理它，但它确实形成了包含许多不同信号的长时间序列。即使像故障码这样听起来很简单的东西，其实也很有深度和丰富性。因为如果你非常仔细地解读故障码，你可以了解不同发动机、燃料类型、气压等等非常具体的动态特性。所以我们把所有信息都接收进来。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: Yes. Uh well it's we have to collect it and organize it but it forms a long time series of many many different signals. And even something that sounds as simple as a fault code really there's a lot of depth and richness to that too because if you read the fault codes very carefully you can understand very specific dynamics about different kinds of engines and fuel types and you know air pressures and so on. So we we take all of that in. Um we have

</details>

**主持人**: 然后你还有AI……

<details>
<summary>Original English</summary>

**Host**: uh and then you have uh AI

</details>

<!-- chunk 4/9 -->

### 行车记录仪与AI边缘计算

**主持人**: 行车记录仪。那是什么？

<details>
<summary>Original English</summary>

**Host**: dash cams. What are those?

</details>

**嘉宾**: 没错。我想你对行车记录仪很熟悉。你在优步里见过它们，对吧？对司机来说非常宝贵和有用，因为如果路上发生什么事，你可以很快证明自己的清白。所以我们有一个联网版本。它可以录制高清视频，有一些存储空间，并且能够将视频发送到云端。我们在边缘运行AI模型。所以我们可以做一些事情，比如根据天气状况给你反馈，让你增加跟车距离。现在我们也看到了摄像头的驾驶员一侧。所以它是对外和对内双向的。摄像头的驾驶员一侧可以检测疲劳或手机使用情况，并向驾驶员提供实时反馈。我们的想法是，他们可以自我纠正、自我指导，这就像是一个顿悟——它打破了那个恶性循环：我打算看手机。如果你在那一刻收到某种音频警报，并且这种情况发生很多次，你就会倾向于改掉这个习惯，因为这是一种负强化。六七年前，当我们引入边缘AI时，这对我们来说是一个巨大的突破，现在我们正在进一步推进这个概念，寻找其他形式的风险等等。

<details>
<summary>Original English</summary>

**Guest**: That's right. So I think you're familiar with dash cams. You've seen them in Ubers, right? Like um and super valuable, useful for drivers because if something happens on the road, you can exonerate yourself very quickly. Um so we have a connected version of that. So it records HD video, it has some storage, it's got the ability to send that to the cloud. Um and we run AI models at the edge. So we can do things like um provide you feedback to increase your following distance like I said based on the weather condition. Um now we're also seeing the driver side of that camera. So it's like you know outward and inward facing. The driver side of the camera can do things like detect fatigue or mobile phone usage provide real-time feedback to the driver. And the idea is they can self-correct uh self coach and that is like the aha is it breaks the the cycle or the bad feedback loop of I'm going to look at my phone. If you get a sort of like audio alert in the moment and it happens many many times you tend to break the habit because it's sort of negative reinforcement. Um that was a huge breakthrough for us um six seven years ago uh as we introduced AI at the edge and now we're kind of going further with that concept finding other forms of risk and so on.

</details>

**主持人**: 对，因为它过去是一个安全设备，而现在它是一个界面，驾驶员可以通过它与AI进行交流。

<details>
<summary>Original English</summary>

**Host**: right because it used to be a safety device and now it's an interface uh that the driver can can communicate with the AI.

</details>

**嘉宾**: 完全正确。因为现在驾驶室里有了这项技术，你还能用它做什么？你能不能在早上司机开始轮班时，给他们做一个简报，告诉他们要去哪里、交通状况和天气？我们有一个小按钮。他们可以用它来呼叫调度中心，比如说，“嘿，我要迟到了，因为我需要去取一些工具之类的。”所以，这个连接层因为所有这些技术的存在而得到了增强。

<details>
<summary>Original English</summary>

**Guest**: Exactly. Because now that you've got the technology in the cab, what else could you do with it? Could you give the driver uh driver a briefing in the morning as they start their shift about where all they're going to go and traffic conditions and weather? Um, we have a little button. They can use that to uh, you know, call dispatch, for example, and say, "Hey, I'm going to be late because I need to uh go pick up some tools or something like that." So, the that connectivity layer just got enhanced with the presence of all this technology.

</details>

**主持人**: 还有所有这些。我知道你还有其他传感器，比如用于温度之类的。所有这些都是你们自己制造的。所以你提到了并非所有组件，但所有这些都是专有的系统，而且顺便说一下，它被设计成一个开放系统，因为很多这些较新的资产都有API，对吧？所以很多较新的卡车，例如，我们可以进行云到云的连接，所以你未必需要那个黑盒子，但你想要数据，并且你希望它被组织好，与你所有的其他资产无缝对接，因为在运营中，你通常会有福特卡车、通用卡车、卡特彼勒、福莱纳以及各种其他设备在一起。所以，我们充当了那个编排层。硬件确实是故事的一部分，但我们也有软件和接口进入系统。

<details>
<summary>Original English</summary>

**Host**: and all of this. And I know you have other sensors for like temperature and that kind of stuff. uh all of this is is built by you. So you mentioned not all the components but like all of this is is propos the system and it's designed as an open system by the way because a lot of these newer assets they have uh APIs effectively right so a lot of newer trucks for example we can do a cloud-to-cloud connection so you don't necessarily need the black box but you want the data and you want it like organized and and seamless with all of your other assets uh because typically in operations you'll have Ford trucks and GM trucks and Caterpillar and Freightliner and all kinds of other equipment coming together. Um, so we act as that orchestration layer. Uh, so the hardware is very much part of the story, but we also have software in interfaces coming into the system.

</details>

**主持人**: 好的。所以你有了所有这些，然后你把它移到云端，然后你在那里有什么？比如，你有一个巨大的数据仓库，还有像ETL那样的数据转换。是这样运作的吗？

<details>
<summary>Original English</summary>

**Host**: All right. So you got all of this and then uh you move it to the cloud and then uh what do you have there? Like you have a gigantic data warehouse and like ETL kind of data transformation. Uh is that how it works?

</details>

**嘉宾**: 嗯，没错。从数据摄入的角度来看，我想你说对了。所以就是海量的数据存储。这些都存放在现代的超大规模云中。所以并不是说我们有一个大型的仓库/数据中心，而是一个相当大的系统。我们摄入数据，存储并组织它，然后我们基本上有一堆流程在这些数据之上自动运行。然后你还有UI/UX协作界面，无论你是调度员、卡车司机还是企业主，每个人都可以访问。

<details>
<summary>Original English</summary>

**Guest**: Um that's right. From an ingestion perspective, I think you got it. Um, so just massive amounts of data storage. Uh, this is all kind of sitting in modern hyperscaler cloud. So it's not that we have like one big warehouse/data center, but um, you know, pretty large system. Um, so we ingest the data, we're storing it and organizing it, and then we like basically have a bunch of processes that are that are um automating like sort of automatically working on top of that data as well. And then you have the UIUX collaboration interface where you're a customer whether you're a dispatcher or a truck driver or uh the business owner like everybody has access.

</details>

**主持人**: 没错。而且有很多不同的角色。你提到了几个关键的角色。一线的司机基本上就是系统的普通用户。你还有调度员。还会有其他人，比如安全经理，或者在某些情况下，如果他们需要处理文书工作，比如合规经理，但你还有负责维护的人，他们想知道现场所有资产的健康状况，哪辆卡车在一天结束时回到车场时我需要维护。然后你还有高管和所有其他有商业头脑的人，他们想知道我们是否准时到达？我们车队的效率如何？我们如何大规模地做到这一点？我们的许多客户，实际上大多数客户都是大型企业，所以可以想象运营部门有成千上万的人和成千上万的资产等等。

<details>
<summary>Original English</summary>

**Host**: That's right. And and there many different personas. So you named a few of the the key ones. Um the drivers in the front line are are very much like just regular users of the system. Um you do have the dispatchers. You'll have other people who'd be like safety managers or uh in certain cases if they have to do paperwork like uh essentially compliance managers and but you also have people that do maintenance for example and so they want to know what is the health of all these assets in the field which truck will I need to maintain at the end of the day when it comes back to the yard. Um and then you do have the executives and all these other business uh minded people who want to know well did we show up on time right like what is the efficiency of our fleet and how do we do this at scale many of our customers actually most of our customers are large enterprises so think operations have thousands tens of thousands of people and tens of thousands of assets and so on.

</details>

### 向传统行业销售AI解决方案

**主持人**: 作为一个想法，向这么多不同的角色销售产品，尤其是在更传统的行业，特别是你们最近增加了AI层，你们是怎么做的？比如，你如何说服那些通常是非技术行业的人购买？

<details>
<summary>Original English</summary>

**Host**: as a thought uh so selling to a bunch of different personas especially in like more traditional industries uh especially as you've added this AI layer recently how do you go about it like how do you convince people in you know typically non technology industry to to buy?

</details>

**嘉宾**: 嗯，你知道，我认为这项技术的伟大之处在于它非常具体，而且当你看到它时，你会很快理解它。所以，我们倾向于去现场，演示这项技术并进行试用。这些设备是即插即用的，所以你可以很容易地在你的环境、你的行业中试用。而且，就像我说的，物理运营中有太多挑战了。通常不会只有一个问题。所以，是的，我们想减少发生的事故数量，但我认为我们也让卡车空转太久，因为这只是一个坏习惯，或者我们把工具落在工地上了，我们想把它们找回来，因为我们花了数百万美元更换它们。所以我们经常会发现类似的多重挑战。然后我们向他们小规模地演示，比如一个团队或一个地区，证明这是有效的，当他们看到时，他们立刻就明白了。这些人都是各自行业的专家。所以他们会说，“我立刻看到了价值或投资回报率。”但他们必须以这种具体的方式看到它。他们不会仅仅因为这是AI或大数据之类的就购买。他们会说，“不，如果这能解决我们建筑业务中的问题，那太好了。我们干吧。”

<details>
<summary>Original English</summary>

**Guest**: Well, you know, I think the the great part about this technology is very tangible and um it's the kind of thing that when you see it, you get it very quickly. So, what we do is we tend to go on site, we will demo the technology and do trials. So, you can easily these are plug-and-play so you can easily try it out in your environment, in your industry. And um like I said, there's so many challenges in physical operations. It tends to never just be one thing. So yes, we want to reduce the number of accidents we get into, but I think we're also like leaving our trucks idling a lot because it's just a bad habit or we're leaving tools behind at the job site and we'd like to get those back cuz we spend millions of dollars replacing them. So we will often find multiple challenges like that. Then we demonstrate to them at small scale like maybe a team or you know a region or or something like that that this works and when they see it they get it immediately. These are people who are experts in their industry. So they would say, "I immediately see the value or the ROI." Uh, but they have to see it in that kind of tangible way. They're not just buying it because it's AI or big data or something like that. They're like, "No, if this solves problems for us in our construction business, great. Let's do it."

</details>

### 数据护城河与商业模式

**主持人**: 当你考虑业务的长期防御性时，尤其是在一个模型可能商品化或可能不会商品化的世界里，我认为大多数人会说它们正在商品化。嗯。

<details>
<summary>Original English</summary>

**Host**: And when you think about the long-term defensibility of the the business, uh, especially in a world where models may or may not commoditize, I think most people would say they are commoditizing. Mhm.

</details>

**主持人**: 是数据层让你觉得保护了Samsara，还是你怎么看待模型？

<details>
<summary>Original English</summary>

**Host**: Is it the data layer that you that you feel protects Samsara or how do you think about modes?

</details>

**嘉宾**: 是的，有几件事。我们认为，无论它是否商品化，这些模型都是不可思议的，对吧？它们通过摄入数据和推理所能释放的价值是巨大的。所以我们对在这方面看到的情况感到非常兴奋。我之前谈到的运营数据，物理世界数字化这方面，是我们的切入点，对吧？这些不是你会在网上找到的令牌。你不能爬取Reddit来了解建筑工地上发生了什么，对吧？你也不能进行测试时的推理。你可以模拟各种环境，但我们的客户真正需要知道的是，在那个特定时间，那个特定环境中发生了什么，对吧？这需要硬件和软件的相互作用，也需要变革管理。你如何将其推广到现场以及那种合作关系？所以这对我们来说是一个独特的领域，我们专注于这个领域。这是我们过去十多年一直在做的事情，这需要大量的工作。我也必须强调这一点，我们与客户一起深入现场，了解他们的业务，然后反向工作。所以这不是那种可以一键部署的事情。它确实需要一种细致入微的方法。

<details>
<summary>Original English</summary>

**Guest**: Yeah, there are a few things. Um, we see whether it commoditizes or not, these models are incredible, right? And uh the amount of value they can unlock with their ability to ingest the data and reason is is awesome. Um, so we're very excited about what we're seeing on that front. Um, the operational data that I was talking about, the physical world kind of digitization side of thing is where we come in, right? These are not the tokens you're going to find online. Like you can't crawl Reddit and find out about what happened on a construction site, right? Nor can you do, you know, test time reasoning about it. You can't just you you can simulate all kinds of environments, but really what our customers need to know is like what was going on in that specific environment at that time, right? Um that requires this interplay of hardware and software, but also the change management. How do you get this out into the field and that partnership? So that's a unique area for us that we focus on. Um this is what we've been doing for the last decade plus and it takes a lot of work. I have to I have to emphasize that too is like we get out in the field with our customers, understand their business and work backwards. So it's not something that can purely be like just you know uh one click uh deployed. It really requires a kind of a nuanced approach.

</details>

**主持人**: 你们有没有跨客户的数据网络效应或数据飞轮的概念？所以，你们在某个地理位置的客户X的行车记录仪背景下学到的东西，是否也适用于不同地理位置的客户Z？比如在学习方面。非常适用。

<details>
<summary>Original English</summary>

**Host**: Do you have a concept of a data network effect or data flywheel across customers? So does something that you learn in the context of a dash cam with uh customer X in geography Y also apply to customer Z in a different geography like in terms of learnings. uh very much.

</details>

<!-- chunk 5/9 -->

### 数据网络效应与边缘计算架构

**Sanjit Biswas**: 在行车记录仪方面，关键洞察在于，虽然这些可能都是不同的公司，但我们都在同一条路上行驶，对吧？嗯，Samsara 系统在一天之内，会覆盖美国 99% 的道路，通常一天还会多次覆盖。所以，你当然可以在风险方面利用这一点。因此，我们可以了解哪些是危险的交叉路口，或者哪些地方天气状况不佳，以及我们如何警告其他驾驶员。这里存在一种网络效应。嗯，但还有其他一些附带效应，对吧？嗯，因为我们行驶在所有道路上，并且我们有摄像头，我们可以告诉你所有坑洼的位置，对吧？这对城市来说非常有用。比如，以芝加哥市为例，他们想知道冬季过后哪些地方出现了坑洼。我们应该按照什么顺序，根据严重程度去处理？你可以利用摄像头数据，以及我之前提到的 GPS 追踪器中的加速度计数据来实现这一点。所以，每次你看到路上那个大颠簸，嗯，你就查看一下视频。这其中的酷炫之处不仅在于你知道坑洼在哪里，而且我们还能看到它随时间的变化。它是在变大吗？它是在开裂吗？诸如此类。这就是我们获得的另一种数据网络效应。

然后，也许是第三种，既然我们早些时候谈到了资产追踪器，你有数百万辆车辆在行驶。一个单独的蓝牙追踪器可能不会被发现，对吧？因为想象一下一个建筑工地。它可能有数英亩大。但是，如果你有一家公司运送建筑材料，另一家公司进行施工，还有电气承包商，这些人中的某一个可能会捡到它。这就是你通过数百万辆这样的车辆以及数千万个像移动设备这样的手持终端获得的另一种网络效应。嗯，这形成了一种不可思议的网状网络。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: So, you know, on the dash cam side of things, the key insight there is, um, while these may be all different companies, we're all driving on the same roads, right? Um, the Samsara system, uh, in a given day, we're driving 99% of the US roads, usually multiple times a day. So, you can use that of course on the risk side. So, we can understand where are the risky intersections or where weather conditions bad and and how do we warn other drivers. So, there's a network effect there. Um, but there are other sort of uh side effects, right? Um because we drive all the roads and we have cameras, we can tell you where all the potholes are, right? And that is super useful for the city. So like this, you know, city of Chicago for example, they want to know which potholes are, you know, happen after the winter weather season. What order should we go after the men in terms of severity? You can use the camera data for that, the accelerometer data from the GPS tracker that I mentioned. So every time you see that big bump in the road, um you look at the video. And the cool part about that is not only do you know where the pothole is, but we can see what's happening to it over time. Is it getting bigger? Is it, you know, cracking? All that kind of stuff. So that is another sort of data network effect that we get.

And then maybe the third, since we talked about asset trackers early, you have these millions of vehicles driving around. A Bluetooth tracker on its own probably doesn't get picked up, right? Because think about a construction site. It could be acres and acres of land. But if you have, you know, one company delivering building materials, another company performing construction, the electrical contractor, one of those guys may pick it up and that is another network effect that you get with millions of these vehicles and then tens of millions of handsets like the mobile devices. Uh it's a incredible kind of mesh network that forms.

</details>

**采访者**: 好的。那么回到产品和人工智能方面。你提到了边缘和云端。你们在什么地方做什么，比例如何？我们可能花一个小时都讲不完具体在什么地方做什么事情。嗯，如果非要概括的话，我会说在边缘端，我们通常运行推理和数据收集。数据收集当然是为了获取训练数据。推理本质上是运行模型，我们从云端下发权重，它们在边缘端以每秒多帧的速度运行。这就是我们实现实时或低延迟检测以及向驾驶员发送闭环警报的方式。嗯，我们在边缘端做这件事是出于实际考虑，对吧？所以，有时你没有很好的蜂窝信号。嗯，我们的许多客户在偏远地区运营。嗯，而且延迟也很重要。如果你能在事件发生后非常快地向驾驶员提供反馈，他们就更有可能改变那种行为。所以，嗯，这对我们来说是一个非常实用的架构。它在鲁棒性和稳定性方面表现得非常好。嗯，但话虽如此，这并非一成不变。所以，如果这意味着我们需要在云端进行一些推理，我们也为此做好了准备。我们有实时隧道连接这些设备。

<details>
<summary>Original English</summary>

**Interviewer**: All right. So going back to the the product and and the eye stuff. So you mentioned uh edge and cloud. Where do you guys do what in what proportion? We could spend an hour just talking about where where what is going on. Um if I had to generalize, I would say at the edge we're typically running inference and data collection. So the data collection of course gets us the training data. The inference is essentially running models where we have the weights and we send them down from the cloud and they're running at many frames per second at the edge. And this is how we do the the kind of real-time or the low latency detections and closed loop alerting to the driver. Um the reason we do it at the edge is is practical, right? So sometimes you don't have a great sell signal. Uh many of our customers are operating in the middle of nowhere. Um and then also the latency matters. If you can get uh feedback to the driver, you know, really very soon after something happened, it's much more likely they'll they'll change that behavior. So uh again very kind of practical architecture for us. It's worked really well um in terms of how robust it is and how it holds up. Um but that being said, it's not fixed. So if that means we need to do some inference in the cloud, we are set up to do that. We have real-time tunnels that that connect these devices.

</details>

**采访者**: 可以推测，你们在边缘端运行的是较小的模型。这些是你们传统的所谓的卷积神经网络，专门为图像训练，用于非常特定的任务，还是说，嗯，你知道，其他形式的、更现代的生成式人工智能？

<details>
<summary>Original English</summary>

**Interviewer**: Presumably what you run at the edge would be smaller models. Are those um your your traditional quote unquote uh convolutional neural networks that are trained for images like a very specific tasks versus um you know other forms of like more modern generative AI.

</details>

**Sanjit Biswas**: 模型类型有很多种。所以，嗯，卷积神经网络是我们起步的地方。这基本上是从 ImageNet 时代开始的，比如，“好吧，我们能检测到手机吗？”对吧？嗯，从那时起，这些模型变得越来越复杂。所以，我们基本上运行一个模型主干，上面有许多不同的分类器和注意力头。所以，嗯，基本上，一旦我们看到某人手里有一个设备，它是什么？是手机吗？是电子烟吗？是三明治吗？嗯，你知道，与之相关的活动是什么。这不是一次性的检测。它往往比那更微妙一些。当我们向外看时也是如此。嗯，我们有指向道路的摄像头。我们还有一些指向侧面或后面的摄像头，我们试图做像深度估计这样的事情，对吧？所以，我是否会撞到灯柱、邮箱或类似的东西？这是一种不同于 CNN 所能做的模型类型。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: There are lots of different model types. So, uh, convolutional neural networks are very much where we started. That's basically from the imageet era of like, okay, can we detect a mobile phone, right? Um, from there these models have become more sophisticated. So, we run basically a model backbone with many different classifiers and and heads or attention heads. So, um, basically once we see a device in somebody's hand, what is it? Is it a phone? Is it a vape pen? Is it a sandwich? um you know what is the activity that's going on with it. That's not a single shot detection. It it tends to be a little more nuanced than that. Same thing when we look outward. Uh we have cameras that point out at the road. We have some cameras that point at the sides or or to the back and we're trying to do things like uh estimate depth, right? So, am I likely to run into a lamp post or a mailbox or something like that? That's a different kind of model than like a what a CNN would be able to do.

</details>

**采访者**: 那么，生成式人工智能从根本上为你们改变了什么？是视频推理吗？你们用它来做什么？

<details>
<summary>Original English</summary>

**Interviewer**: And then what has um uh generative AI fundamentally changed for for you guys? Um is that video reasoning? What what what do you use for for what?

</details>

**Sanjit Biswas**: 我们以几种不同的方式使用生成式人工智能。我想说，如果我们考虑整个模型类别，是的，你现在可以对视频进行推理了。所以，嗯，以前需要人工审核员参与的工作，嗯，或者你知道，那种可能在海外低成本地区完成的工作，你现在可以在云端使用这些模型以更大的规模完成。所以，嗯，例如，如果有人在驾驶卡车时急刹车，嗯，天真的假设是，“嘿，司机分心了，他们有点惊醒了。”更微妙的解释是，那个司机可能是在躲避一只鹿、一条狗，或者，你知道，某种防御性事件。如果你能观看那个视频片段，你现在可以说，“嘿，我们实际上要给司机一些积极的反馈，因为他们做了一件非常好的事情。”视觉语言模型能够有效地完成我刚才描述的事情，对吧？嗯，类似地，如果你想了解，是否有人闯了红灯，对吧？这些事情会发生。你需要一个相当复杂的模型来理解道路的几何形状和所有条件等等。所以，那可能是一种 JEPA 风格的模型。因此，我们能够使用几种不同的模型家族。

在生成方面，即实际能够创建视频，这也非常有趣，因为从指导的角度来看，我们的大多数客户都受限于他们可以进行的人际互动次数。比如，让我坐下来跟你 Matt 说，“嘿，我们需要谈谈你上周的驾驶情况。”我们可能只能对一小部分人这样做，但我不能对每个司机都这样做。这不现实。嗯，你可能见过，比如，你知道，AI 生成的虚拟形象，比如 AI 生成的人物。我们可以生成一个教练，它可以长得像公司的安全副总裁，或者，你知道，一个名人，或者谁知道呢，你知道，无论客户想要什么，但这可以是一种非常有效的提供周末指导的方式。所以，这是一种生成式视频的形式，坦率地说，五年前我们甚至无法想象。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: We use generative in a few different ways. I would say if we think about the overall class of models, yes, you can now reason about video. So uh what would have required a human in the loop reviewer um or you know and that's the kind of work that might have been done overseas in lower cost geos or something like that you can now do at much more volume um in the cloud using these models. So uh for example if someone slams on the brakes right while they're driving their truck um the the naive thing to assume is like hey the driver was distracted and they they kind of woke up. The more nuanced thing is that driver might have been avoiding a deer or a dog or, you know, some kind of uh defensive event. If you can watch that as a video clip, you can now say, "Hey, we're actually going to give the driver some positive feedback because they did a really good thing." The VLMs are able to effectively do what I just said, right? Um, similarly, like if you want to understand, did someone run a a red light, right? These things happen. you need to have a pretty sophisticated model that understands the geometry of the road and all the conditions and and so on. So that would be like a a JEPA style model for example. So we're able to use a few different model families.

On the generative side of like actually being able to create video that's also very interesting because from a coaching perspective most of our customers are bottlenecked on the number of humanto human interactions they can have. Like for me to sit down with you Matt and say hey we need to talk about your driving from last week. We could probably do that for a small fraction, but I can't do that for every driver. It's not practical. Um, you may have seen like, you know, AI generated avatars like AI generated people. We can generate a coach and that can resemble the VP of safety from the company or, you know, a celebrity or who knows, you know, whatever the customer wants, but that can be a very effective way to deliver end of week coaching. So, that's a form of generative video that frankly we couldn't have even dreamed of five years ago.

</details>

**采访者**: 你们是构建自己的模型，还是采用现成的模型并进行定制？你们是开源派吗？你们是 OpenAI、Anthropic 派，还是 Gemini 派？嗯，你们用什么？

<details>
<summary>Original English</summary>

**Interviewer**: Do you build some of your own models or do you take stuff off the shelf and customize it? Are you an open source shop? Are you in OpenAI anthropic shop, Gemini shop? Um what what do you use?

</details>

**Sanjit Biswas**: 我们在接受模型方面是普遍开放的，因为现在有如此多的创新。嗯，所以，是的，前沿实验室做得很好，对吧？我们会同时使用来自不同实验室的多种模型。嗯，开源模型也相当有吸引力。我认为它现在正迎来它的高光时刻。但我们一直在关注，我认为这确实来自学术界，开源和真正开放权重的模型确实给了你很大的操作自由度。所以，我们可以做一些事情，比如对它们进行蒸馏，嗯，例如，将它们缩小以适应设备。嗯，所以我们使用这样的模型，然后还有一些是我们从头开始训练的。那些可能是较小的模型，参数规模在数千万，但非常特定于我们在现场需要做的事情。

<details>
<summary>Original English</summary>

**Sanjit Biswas**: We are universally accepting of models in the sense of there's so much innovation happening. Um so yes, the frontier labs are doing great work, right? The and we'll use multiple models from different labs uh simultaneously. Um the open source models are are pretty compelling. I think it's having its moment now. But we've been seeing u and this is really I think from the academic communities open source and really open weights models really give you a lot of operational freedom. So we can do things like distill them uh for example to shrink them down to fit on a device. Um so we use models like that and then there's others that we train from scratch. Those might be smaller models call it tens of millions of parameters but very specific to something we need to do in the field.

</details>

### Agent Studio 与从连接到行动的演进

**采访者**: 好的，我们来谈谈智能体。这是你们在拉斯维加斯举行的 Beyond 2026 大会上发布的重磅产品，就在六月底。所以现在还不到一个月。嗯，你们推出了 Agent Studio。所以，也许带我们了解一下这个，我认为在过去，你们描述了一个从连接运营到理解运营，再到采取行动的演进过程。那么，这一切是如何结合在一起的？

<details>
<summary>Original English</summary>

**Interviewer**: All right let's talk about agents. So that's the that was the big launch that you guys had at the um your Beyond 2026 conference in Las Vegas just at the end of June. So less than a month ago now. Uh and you launched agent studio. So maybe walk us through this and I think in the past you describe a progression from uh connecting operations to understanding them to taking action. So how does that all fit together?

</details>

<!-- chunk 6/9 -->

### 将LLM引入产品：Samsar助手与保修智能体

**Speaker A**: 是的。几年前，我们确实将LLM引入了我们的产品。我们称之为Samsar助手。你可以把它想象成一个与你的运营数据相连的聊天机器人。它变得非常受欢迎。我们看到客户提出各种实际问题，比如“谁是我最安全的司机”或“哪些卡车需要维护”，诸如此类。这些交互通常是单轮或几轮对话，就像你在侧边的聊天窗口里来回交流。当然，去年发生的突破是，这些智能体可以在更长的时间跨度内运作。所以，AI不再是在一秒内回答问题，而是可以自己去完成一些工作，制定一个计划并执行它。我们在编程领域看到了这种影响，但在运营领域也有很多应用，对吧？我在台上演示的一个例子是我们的保修智能体。当它看到一个故障代码时，它可以查阅维修手册，查看你与OEM协商的具体保修协议，然后将两者关联起来，并判断：“是的，考虑到这辆车的车龄或行驶里程，这个具体问题实际上在保修范围内。”然后它可以开出一个工单，填入步骤，并告诉你：“嘿，其他卡车也有这个问题吗？”这原本需要一两个小时的人工劳动，我们现在能将其自动化到一分钟以内。这是一个巨大的突破和解放。我刚才只是深入讲了保修的例子。但你可以看到这如何应用于报告，如何应用于在一天开始时向司机做简报。你可以用各种创造性的方式来使用它。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Well, a few years ago, we did introduce LLMs into our product. We called it the Samsar Assistant. So, think of it as like a chatbot tied to your operational data. Um, it became very popular. We saw customers asking all kinds of, you know, practical questions like who are my safest drivers or which trucks need maintenance, things like that. Um, those tended to be, you know, single turn or maybe like a few turn interactions like you just go back and forth with the the chatbot window on the side. The breakthrough that of course happened last year is these agents can operate over much longer time horizons. So instead of an AI responding to a question in a second, it can like go do some work on its own, develop a plan and go after it. We've seen the impact of that in the coding world, but there's also a lot of implication for the operational world, right? So um the one of the demos I did on stage is we have a warranty agent. when it sees a fault code, it can basically crack the service manual, look at your uh specific like OEM negotiated warranty agreements and then correlate the two and say, "Yes, this specific issue given the age or you know the number of miles that have been driven on this vehicle is actually covered under warranty." Then it can open a work order, put in the steps and also tell you, hey, do any of the other trucks have that issue? That is a, you know, like what would have been like an hour or two of human labor that we've been able to automate down to like under a minute. That is the huge kind of breakthrough unlock. And I I just went very deep on warranties. But you can see how that would apply to reporting, how it would apply to, you know, briefing a driver at the beginning of the day. You can use in all kinds of creative ways.

</details>

**Speaker B**: 听起来，也许出于显而易见的原因，你们是从非高风险的使用场景开始的。你们是这么想的吗？比如，如果保修索赔搞错了，虽然不太好，但也没人因此丧命。

<details>
<summary>Original English</summary>

**Speaker B**: It sounds like u for all perhaps the obvious reasons you're starting with um non-risky kind of use cases. Is that is that how you guys think about it? Like something where if you make the wrong warranty claim, you know, it's not great, but uh you know, nobody dies.

</details>

**Speaker A**: 是的。嗯，我认为我们只是从最能产生实际影响的领域开始。事实上，大多数保修索赔根本没人去处理，对吧？没人有时间去做我刚才提到的所有工作和文书。所以，这对我们的客户来说是一个巨大的兴趣点，他们知道有这些额外的工作是有用的，但自己没时间做，所以想知道如何实现自动化。嗯，然后随着时间的推移，我认为想法将是如何真正为客户自主运营部分业务，比如在每天早班前重新规划路线。我们现在有技术可以做到这一点，而且这也不是高风险，但它需要大量的商业判断，比如那条路线实际上是由这个人跑的，因为他们与那个客户有十年的关系，你需要掌握所有这些背景信息。所以从这个意义上说，我们是从我们知道能产生影响的事情开始，然后与客户合作，找出我们还能做什么。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Um I I think of it as we're just starting with the most practical areas we can have impact. The the reality, by the way, is most of those warranty claims just are unfulfilled, right? Nobody has the time to go do all that work that I just mentioned and and do the paperwork. So that's an area of of tremendous interest for our customers is you know hey I have all this extra work that I know would be useful but I'm not able to get to so how do I do that? Um and then you know over time I think the idea will be how do we really like autonomously run parts of the operation for the customer if that's like replanning the route for example before uh every morning shift we now have the technology to do that and again it's not super risky but it requires a lot of business judgment of you know that route actually is run by this person because they have a relationship they've been you know seeing that customer for 10 years you need to have all that context So in that sense we are starting with things where we know we can have an impact and then we're working with customers to figure out what else could we do.

</details>

### 智能体推理与工作流规则的结合

**Speaker B**: 你用了“自主”这个词。我一直对那些像你们一样构建在现实世界中工作的真实智能体的人很感兴趣。你认为成功的最终比例是多少？是智能体推理，还是内置了一些好的、老式的代码工作流和规则？比如，最终谁在乎呢，只要它管用就行。但成功的秘诀是什么？是两者的结合，还是我们已经到了仅靠智能体推理就能做很多事情，以至于不需要在整体解决方案中内置那么多规则的地步？

<details>
<summary>Original English</summary>

**Speaker B**: You use the word um autonomously. I'm I'm I'm always uh fascinated for people that that build real agents that work in the real world just like you guys do. What would you say is the proportion of um sort of a gentic reasoning versus having some good old you know code enough code workflow and rules that's built into it for for ultimate success like you know ultimately who cares you know what what does what as long as it works but like what is the recipe to make it work is that is a combination or are we at a stage where just agent reasoning can do so much so that you don't need that much like rules built into the overall solution

</details>

**Speaker A**: 我认为智能体推理是一个巨大的突破，就像我说的，这种制定计划并在长时间跨度内工作的能力。但你确实需要概述你希望智能体做什么，这在某种意义上就是工作流，同时也是护栏，比如在什么时候你说“嘿，智能体，你应该向我求助”或者“智能体，我不希望你钻牛角尖”。我们必须让它保持在正轨上。所以，这是运营背景（通过工作流和护栏体现）与这种新的智能体推理能力的某种结合。我认为两者单独来看效果都不太好。顺便说一句，工作流方面，我们的产品中一直有这些元素。我给你举一个非常简单的例子。在大多数商业行业中，你需要在班次开始和结束时进行绕车检查。我们每年大约看到3到3.5亿次这样的检查。历史上，这只是在移动设备上的一个工作流，对吧？你一步一步地走，拍些照片，说某些东西是安全的。如果你将它与诊断信息、位置信息、上次是谁做的检查、照片里有什么结合起来，那将是一个巨大的解锁。这就是我们所说的将这两件事结合起来的意思。

<details>
<summary>Original English</summary>

**Speaker A**: I I think agent reasoning was a huge unlock like I said this ability to build plans and work over long time horizons but you do need to outline what is it that I want the agent to do right and that is in in some lightweight sense like the workflow it's also the guardrails like at at what point do you say hey agent you should you know ask me for some help or agent I don't want you to go down that rabbit hole right like we we have to kind of keep it on track so it's some combination of operational context which comes through workflow and guardrail with also this now kind of new agentic reasoning ability. I don't think either really works well in sort of isolation and the workflow side of things. By the way, we had elements of that in our product. Um I'll give you a very simple example in u in most commercial industries there's a walkound inspection that you do at the beginning of your shift and end of your shift. We see about 300 350 million of those a year. that has historically just been a workflow on a mobile device, right? Like you're kind of going step by step, taking some pictures, saying something's safe. If you combine that with the diagnostic information, the location information, who last did the check, like you know, what was in the picture, that is is a huge unlock. So that's kind of what we mean by combining these two things.

</details>

### 智能体目前还做不到的事情

**Speaker B**: 你认为智能体目前还做不到什么？

<details>
<summary>Original English</summary>

**Speaker B**: What do you think agents are not able to do just yet?

</details>

**Speaker A**: 哦，天哪，这个天花板问题，我感觉每周都在变。嗯，这里面有一些细微差别。例如，像Fable 5和GPD Soul这类新模型，很难确定实际的天花板在哪里，但有时你确实会看到它们分心或陷入某个循环，对吧？所以，我认为有一个方面是，它们最终可能会找到答案，但它们能在10秒、1分钟甚至1小时内找到答案吗？所以，我认为这是一个仍然存在实际天花板的领域，我猜随着这些模型变得越来越强大、越来越复杂，这个天花板会缩小。同时，这些算法也变得越来越高效。所以，也许计算能力、算法和更智能的模型架构的结合，会将原本需要一天的任务变成一小时的任务，甚至更快。

<details>
<summary>Original English</summary>

**Speaker A**: Oh boy, that that ceiling question, it changes like, you know, I feel like every week. Um, and you there's there's some nuance to this. So, for example, these new models like the kind of Fable 5 class and and GPD soul, it's hard to figure out where the practical ceiling is, but sometimes you do see them go and get um distracted or like lost in a loop somewhere, right? So, I think there is some aspect of like they may find the answer eventually, but can they find the answer in um 10 seconds or 1 minute or even 1 hour, right? So that's one area where I think there is still a practical ceiling and my guess is as these models become more and more powerful more sophisticated that will shrink and then these algorithms are getting more efficient. So maybe the compute combined with the algorithm combined with just like smarter model architectures will make what would have been like a one-day task a 1-hour task or you know even faster than that.

</details>

### 未来一两年内的可能性

**Speaker B**: 如果你稍微放下怀疑，你认为在一两年内你能做到什么？不是十年，因为显然没人知道。但鉴于目前的进展，你现在能处理保修的例子，能处理为司机预先规划一天的工作。你认为在未来一年内还能做些什么？

<details>
<summary>Original English</summary>

**Speaker B**: And if you suspend disbelief a little bit, what do you think you would be able to do uh in like a year or two? You know, not 10 because obviously who knows. Um but uh given the progress, so right now you're able to do um uh you give the example of warranty, you give the example of uh sort of pre-planning a day uh for for a driver. What what else do you think you can do in the next year?

</details>

**Speaker A**: 我认为我们预测未来一两年会发生什么的能力，很大程度上取决于观察现在勉强可能的事情，然后看成本曲线或能力曲线会是什么样子。上个月在我们的Beyond大会上，我们讨论了一个想法，叫做“司机随行”。在运营中，经理和你一起坐一天车，跟你一起开8小时车，这很常见。他们看的不是你开得多快，而是你的习惯，比如你是否检查后视镜，你是否保持警惕和清醒。这类事情基本上需要大量的视频计算，对吧？你可以运行一个分词器，这就会变成大量的计算。你今天就可以做到，只是非常昂贵和耗费资源，但它是可行的，并且是可行的。我们非常乐观，因为每百万token的成本下降得非常快，能力也在提升，我们可以随着时间的推移以越来越好的成本为客户提供这种服务。所以我认为在一两年内，这将变得可行。而且我得说，就在上个周末，我在玩Sarah，那是一家大型晶圆级芯片公司。他们有一个推理模型，可以在他们的芯片上运行，基本上就是Gemma 4，但速度超快。这是一个很好的例子，说明这是一种非线性的跳跃，就像你今天在这些大模型上运行Gemma 4在你的GPU上能得到什么一样。

<details>
<summary>Original English</summary>

**Speaker A**: I I think a lot of our ability to predict what happens next year or two is by looking at what is like barely possible now and then what will the sort of um cost curves look like or or capability curves look like and um something that we talked about at our beyond conference last month was this idea of a of a driver ride along. So, in operations, it's quite common to basically have a manager sit with you over the course of your day, like drive around with you for 8 hours. And what they're doing is they're not looking for, you know, uh, how fast you're going. They're looking for your habits of like, do you check your mirrors, like, you know, are you alert and are you aware? That kind of thing. That's basically a massive amount of, uh, video computation, right? So, you can run a tokenizer. It just turns into like a lot of compute. You can do that today. It's it's pretty expensive and costly, but it it works and it's doable. We're pretty optimistic that the you know cost per million tokens is dropping so fast and the capabilities are rising that we can deliver that at better and better cost over time to our customer. So I think in a year or two that will be possible and I have to say like you know just over last weekend I was playing um Sarah which is one of those big like wafer scale chip companies. they have uh an inference model that you can run on their chip which is basically Gemma 4 but like hyper accelerated like that's a great example of like that is nonlinear in terms of jump right like what you get out of these big models today if you run Gemma 4 on your GP you

</details>

<!-- chunk 7/9 -->

### 速度飞跃与新用例

**主持人**: 如果你有一张快速的显卡，本地运行可能达到每秒100个token；但如果跑在他们的云上，速度可以达到每秒800到1500个token，差不多快了10倍。正是这种速度提升，解锁了我们之前因为成本太高或速度太慢而无法实现的新用例。

<details>
<summary>Original English</summary>

**Host**: might get like 100 tokens per second if you have a fast card, if you run it in their cloud you get anywhere from 800 to 1500 tokens per second, so call it 10x faster. That is the kind of thing where it unlocks these new use cases that we couldn't get to because it would have been too either expensive or too slow.

</details>

**主持人**: 不是要在播客里打广告，但等我们这期发布的时候，上一期节目正好就是和Serial Brush的Andrew Feldman的访谈，如果谁错过了的话。

<details>
<summary>Original English</summary>

**Host**: Not to promote the podcast on the podcast, but by the time we release this, the prior episode will be precisely an episode with Andrew Feldman of Serial Brush, if anybody missed it.

</details>

### 行车记录仪的社会视角

**主持人**: 我很高兴你提到了"随车同行"这件事。因为我觉得从社会角度来看，整个行车记录仪有一个非常迷人的层面。它可能成为一个有趣的蓝图，告诉我们人类如何与AI进行专业互动——不是仅仅通过AI聊天机器人查询，而是让AI永久性地与我们共存。那么，一个显而易见的问题是，这里面有某种"老大哥在看着你"的元素。AI在监视你的一举一动，虽然是为了你好，但它也在观察你做得不好的地方。我很好奇，从让每个人都满意的角度来看——无论是客户、司机，还是那些没有愤怒地把摄像头扯下来的人——你学到了什么？

<details>
<summary>Original English</summary>

**Host**: And of commercial. I'm glad you mentioned the ride along, because I think there's a fascinating aspect to the whole dash cam from a societal standpoint, in that it could be like an interesting blueprint in terms of how we professionally interact with AI, not just when we query it through AI chatbots, but like having AI live with us on a permanent basis. So, the obvious question is that there's an element of arguably big brother is watching you. AI is watching every single move that you make, for your own good, but it's also looking at what you may not do well. I'm curious about what you've learned from the perspective of making everyone happy, if there's such a thing, whether that's the customer, the driver, and people not ripping out the camera in rage.

</details>

**Daniel (Samsara)**: 是的，关于这个问题我有几点想法。首先，我们实际上花了很多时间与司机和其他一线工人在一起。获取他们的视角非常重要，因为他们是系统的主要用户和真正的受益者。人们通常不会想到的是，行车记录仪的主要用途是什么？实际上，绝大多数用例是"免责证明"。我的意思是，它帮助解释事故发生时到底发生了什么。举个例子，如果你是家得宝（Home Depot），一个非常知名的品牌，他们是我们的客户。很多针对你的汽车索赔都会出现，因为对方会说："嘿，一辆家得宝的卡车在这条高速上倒车撞了我的车。"对吧？这会让司机非常沮丧，因为他们会说："你看，我工作做得很好，我没有撞到那个人。"现在，你可以提供高清视频证据，证明你当时在哪里，如果发生了事故，是谁造成的，等等。这就消除了所有的模糊性，对吧？现在你可以直接解决这个问题。如果确实发生了事故，公司可能会选择庭外和解并赔付。但如果没有——这是非常常见的情况——你就可以真正地去抗辩，说："看，我们确切知道发生了什么。"司机们喜欢这一点，因为我得说，90%的时间里他们都做得很好，但没人看到。所以，这是一个巨大的突破：这种正向强化——我们分析整个驾驶过程，看到所有这些良好行为，比如防御性驾驶或被免责。我认为这正好抵消了"这东西到底是为了什么？"的疑问。如果你把这种理念融入企业文化，相当于做一个"月度最佳员工"的展示，但展示的是真正出色的工作，我认为人们会对此感到非常兴奋。另外，从安全角度来看，我们应该记住，在实体行业中，受伤的风险是落在个人身上的。换句话说，我们希望每个人下班回家时都和他们来上班时一样。这是一个重要的概念，我认为人们不会去想——如果你在建筑工地、油田服务或类似行业工作，你每天工作时都承担着很大的风险。所以，从"这对我有什么好处"的角度来看，我们是在努力保护你的安全。如果你以透明、周到、尊重隐私的方式去做这件事，那么在一线员工中就会产生非常好的效果。

<details>
<summary>Original English</summary>

**Daniel (Samsara)**: Yeah. So, a couple of thoughts there. The first is we actually do spend a lot of time on the front line with drivers and other frontline workers. So, it's very important for us to get their perspective because they're the primary users and really beneficiaries of the system. Something people don't often think of is, if you have a dash camera, what is it used for? The majority use case is actually exoneration. So, what I mean by that is helping explain what happened if there was an accident. Because for example, if you are the Home Depot, you're a very well-known brand. They're a customer of ours. Lots of claims, auto claims are placed against you because they'll say, "Hey, a Home Depot truck backed into my car on this highway." Right? And that is something that really upsets a driver because they'll say, "Look, I was doing my job great. I didn't run into that guy." Now, you can basically produce HD video evidence of where you were and if there was an accident, who caused it, all that stuff. That eliminates all the ambiguity, right? Like now you can just resolve it and look, if there was an accident, the company may choose to just settle it out and pay it out. But if there wasn't, which is like a very common case, now you can really fight it and say, "Look, we know exactly what happened." Drivers love that because I have to say 90% of the time they're doing a great job and nobody's seeing it, right? And so that has been a huge unlock is this positive reinforcement of we're analyzing the whole drive. We're seeing all these good behaviors, defensive driving or exonerations, things like that. That I think is what is sort of the counterweight to the "hey what is all this for?" Like how is it being used? If you have that in your culture, if you are kind of doing the equivalent of employee of the month but showcasing really great work, I think people get really excited about this. Also from a safety perspective we should remember in physical industries the risk of injury is on the person, right? So in other words, we want everyone to go home the same way they came to work. That is an important concept that I think people don't think about. If you're working construction, you're working oil field services or something like that, you take a lot of risk when you do your job every day. So it's actually in the "what's in it for me" — it's like we are trying to keep you safe. If you have that and you do it in a transparent, thoughtful, respectful from a privacy perspective way, it goes a very long way with the front line.

</details>

### 技术作为工作质量的评判者

**主持人**: 非常有趣，也很有道理。请允许我再追问一下。在某种程度上，这个"眼睛"也成为了你工作质量的评判者。我不知道你是否同意或不同意。我很好奇，对于这种情况如何发生或应该发生，是否有任何保障措施？也许这就是生活的现实。你知道，我们刚刚经历了世界杯，现在我们都熟悉VAR回放系统了。事情就是这样——你越位了，事实就是如此，技术在这里就是为了告诉每个人你越位了。我很好奇你学到了什么，这似乎是一个非常重要的当前话题。

<details>
<summary>Original English</summary>

**Host**: Very interesting. And that makes a lot of sense. Just to push a little bit, if I may, in some ways the eye also becomes a judge of the quality of your work. I don't know if you agree or disagree. I'm curious if there's any kind of safeguards about how that happens or should happen in the future and perhaps it's a fact of life. You know, we just had the World Cup and we are now familiar with the VAR review and it is what it is. You were offside and that's just what it is and technology is here to tell everyone that you are offside. Curious about what you've learned. It seems like such an important current topic.

</details>

**Daniel (Samsara)**: 是的，非常重要。我认为"透明度"再次成为这里的关键词。顺便说一句，我们的摄像头不是隐藏摄像头，它们非常显眼。所以它不是一个秘密的录音设备。整个想法是让一线员工参与进来。我们称之为"变革管理"。比如，"嘿，我们要引入这些东西。它们是做什么的？用来干什么？你怎么使用它们？它们对你有什么帮助？"如果你在早期就以透明的方式进行这种对话，结果往往会非常建设性。因为我之前提到过家得宝，他们的汽车索赔减少了大约65%。这对整个组织来说是一个巨大的胜利，无论是在高管层面，更重要的是在区域层面。这些就是我们想要帮助创造的胜利。那么，能不能用这个东西来做"坏人"呢？理论上可以，但谁会坐在那里盯着每个司机看呢？顺便说一句，坐在那里看司机开车超级无聊，对吧？所以，当你透明地说明系统在做什么、不做什么，以及数据如何使用时，你就能获得整个组织的认同和信任。

<details>
<summary>Original English</summary>

**Daniel (Samsara)**: Yeah, very much important. I think transparency again is like the key word here. It's not — and by the way our cameras are not hidden cameras. They're quite visible. So it's not like a secret recording device. And the whole idea is to bring the front line along. So we call this change management, right? Like, "Hey, we're introducing these things. What do they do? What are they for? How can you use them? How can they be useful to you?" If you have that conversation early in a transparent way, it tends to be quite constructive. Because I mentioned Home Depot earlier. They saw like a 65% reduction in their claims, like auto claims. That was a huge win for that organization both at the executive level but more importantly at the regional level. Those kinds of wins are what we want to help create. Now, could you use this in a "bad guy" kind of way? You could, but that would be like who is sitting there watching each driver? It's super boring to sit and watch drivers, right? So when you are transparent about what the system's doing and what it's not doing and then how the data is used, that is how you get the buy-in and you earn the trust of that entire organization.

</details>

### 未来：人机混合车队

**主持人**: 好的。你站在所有这些物理AI的最前沿。我很好奇，如果我们退一步看，你认为世界会走向何方？我们是在走向一个人类和机器人混合车队的世界吗？这是你看到的趋势吗？

<details>
<summary>Original English</summary>

**Host**: All right. So you sit at the very forefront of all of this in physical AI. I'm curious where you see the world going as we maybe take a step back. Are we going towards a world of mixed fleets of just people and just robots and is that what you're seeing?

</details>

**Daniel (Samsara)**: 是的，如果我们想象5到10年后，这会是怎样的走向？我确实认为会是这样。我们预计在物理操作中会有更多的机器人参与。实际上，如果你今天走进一个仓库，就能看到这一点。无论是制造工厂还是配送中心，都有大量的自动化和机器人技术在进行。很酷的一点是，这降低了许多人类工人受伤的风险。比如，10到20年前，搬运伤非常常见，但现在少多了，因为基本上都是机器人在做重体力活。当然，那里仍然有人类在工作，因为还有各种交接工作，操作中也有一些细微之处。但我们预计类似的情况也会发生在户外现场。想象一下一个建筑工地，或者一家公司在修路，或者现代化电网。有很多重复性的工作需要完成。想象一下你在平整场地，把它弄平。这项工作能不能在第三班——也就是午夜到早上8点之间——完成呢？这可能是一个非常酷的方式，可以在路边进行高效工作，比如连续五英里把路弄平。我们预计机器人在未来5年内就能做到这一点。不过，剩下的所有工作仍然相当混乱，建筑行业充满了各种例外情况。你不断地在解决问题。我认为这正是人类发挥大量经验和判断力的地方，比如"这个应该怎么做？"或者"我在等建筑材料的时候，可以先做另一件事。"与此同时，机器人在把路弄平。这就是我们在未来几年看到的景象。我相信同样的情况也适用于物流和供应链。当然，最后一公里还有很多复杂情况。

<details>
<summary>Original English</summary>

**Daniel (Samsara)**: Yeah, this is the — if we kind of imagine 5, 10 years out, where does this go? I do think yes. We expect there to be a lot more robots sort of involved in physical operations. You see this actually if you go into a warehouse today, right? So if you go into either manufacturing or fulfillment center, there's actually a lot of automation robotics going on. And the cool part about that is it reduces risk of injury to a lot of the human workers. Lifting injuries were very common 10, 20 years ago. They're way less common these days because quite literally the robots are doing the heavy lifting. Now there's still humans working there because there's kind of all the handoffs and there's some nuance to the operation, but we expect something similar to happen out in the field, right? So think about a construction site or maybe a company building a roadway or modernizing the grid. There's a lot of kind of repetitive work that has to happen. Imagine you're grading a site, you're making it level. Could that happen during the third shift between midnight and 8 am, right? That could be a really cool way to do productive work on the side of the road where you're just going for five miles making it flat, right? We see robots being able to do that in the next 5 years. Now, all the rest of it though, it's still pretty messy and construction has like exception after exception. You're solving problems constantly. That's where I think the humans offer a lot of experience and judgment of "well, how should this work?" and "I'm waiting on this building material while I can perform this other thing." Meanwhile, the robots are making the road flat, right? So, that's kind of what we see in the next few years. The same thing applies, I believe, to logistics and supply chain. So, now there's a lot of kind of last mile complication.

</details>

<!-- chunk 8/9 -->

### 自动化与劳动力的未来

**主持人**: 有些情况是，货物到了，你得亲自去取、去送。我们的一些客户，他们在杂货店里负责上架。也许未来我们会用上人形机器人，但谁知道呢，事物总是在演变。不过在那之前，你能不能把达拉斯到凤凰城之间的长途运输自动化？比如那些运送饮料罐的卡车。所以，我们认为未来是令人兴奋的。从运营角度来看，我们看到的场景非常多样化，有各种不同类型的设备和劳动力。所以，我的猜测是，未来会有不同品牌、不同型号的机器人。而从你作为企业的角度来看，你会把它们都整合起来。我猜，在Simsar的整体图景中，自动化卡车和建筑工地的人形机器人会扮演什么角色？

<details>
<summary>Original English</summary>

**Host**: that happens and you have to physically pick up deliver package. Some of our customers, they stock the shelves in the grocery store. Maybe we get there with humanoids and you know, never say never like this stuff always is evolving. But in the meantime, could you automate the longhaul segment between Dallas and Phoenix, right, of all of those, you know, beverage cans coming in or something like that? So, we see this as an exciting like and uh in terms of what the future looks like. And what we've seen in operations is very diverse, lots of different types of equipment, lots of different types of labor. So, it's going to be, you know, different makes and models and different makes and models of different kinds of robots is my guess. And from your perspective as a business, you would just par it all. Uh I guess where would automated trucks and humanoids on the construction site fit in the overall picture at Simsar?

</details>

**Sanj**: 嗯，实际上，我们大多数客户会告诉你，他们在劳动力方面是供应受限的，对吧？所以这些行业是劳动密集型、资产密集型的。所以他们很欢迎这种想法，比如“我能不能把部分劳动力自动化，这样我们就能做更多的事？”所以，我们的客户会一直存在，他们有很多工作要做。我们想做的就是提供一个“单一玻璃面板”，让他们能够协调整个运营，触发工作流程，比如“好的，那辆卡车从达拉斯出发了，我们准备好，让仓库系统就绪，准备接收。确保我们通知了最终客户，等等。”然后，我之前展示过那个追踪标签。你可以把它贴在货物托盘上。这样，当货物在供应链中流转、最终到达工地并安装时，你就可以从头到尾追踪它。目前这一切都非常不透明。想想看，作为消费者，你收到货物时，可能只会收到五条更新信息，对吧？比如“离开设施”、“在路上”、“派送中”等等。而我们能看到成百上千次的信号。当货物自主移动时，这一点就变得非常重要。比如，那个航空航天组件在哪儿？我们有客户想知道他们现在需要用来完成工作的那个非常昂贵的资产在哪儿。这些目前都是无法追踪的。

<details>
<summary>Original English</summary>

**Sanj**: Well, practically speaking, most of our customers would tell you they're supply limited in terms of labor, right? So these are uh labor intensive asset heavy industries. So they welcome this idea of like could I automate some of this labor so we can basically perform more. So that's kind of like our customers are are going to be around. they have like a lot of work to do. What we want to do is provide the sort of uh single pane of glass so they can orchestrate the whole operation, trigger the workflow of like okay that truck is arriving from Dallas. Let's get queued up so the warehouse systems ready to go and accept it. Um let's make sure that we're notifying our end customer and so on. And then I showed the tracking label earlier. You could put that on the pallet of goods. So you can track it end to end as it's changes hands through the supply chain as it makes its way to a job site um as it's installed. This is all very opaque today. Like if you think about your, you know, shipments that you receive as a consumer, you might get like five five updates, right? Like left this left the facility, you know, out out on the road, out for delivery, etc. We see like hundreds and hundreds of pings. That's going to be really important when things are moving on their own. you know, where is that um aerospace assembly, right? Like we have customers who want to know where this really expensive asset is that they need to perform their job right now. That's sort of like untracked.

</details>

**主持人**: 你觉得自动化，呃，自动驾驶卡车，是不是马上就要来了？汽车领域似乎已经近在眼前了。我的意思是，很明显，Waymo和特斯拉现在已经有了自动驾驶功能。三年后，我们会有10%的自动驾驶卡车吗？还是75%？你的直觉是什么？

<details>
<summary>Original English</summary>

**Host**: Do you think uh automated uh you know self-driving trucking is just around the corner? It seems to be around the corner for cars. I mean obviously it's already happening with Waymos uh and and Teslas now and automated pilot. In three years are we at 10% uh self-driving trucks? Are we at 75%? What's your gut?

</details>

**Sanj**: 我认为在机器人出租车方面，它会发展得更快一些，因为运营范围更区域化，而且情况也更相似，对吧？就像你我坐出租车穿城而过，体验会非常相似。所以我认为那将是你能看到自动驾驶汽车最明显、最可见的影响。在卡车运输方面，重要的是要认识到，长途运输和把东西从A点运到B点，其实只占路上商用车辆活动的一小部分。大多数商用车辆是在像现场服务这样的行业里，对吧？比如暖通空调技师、水管工、电工，他们是去执行具体工作的。或者他们是在建筑行业，比如修路。这些领域恰恰是目前自动驾驶不太擅长的地方。这是一个非常混乱、长尾的市场。因此，我们认为其采用速度可能会慢一些，但不是说完全没可能。只是可能需要10到20年。而且这些行业的设备高度专业化。比如水泥搅拌车或垃圾车，都是定制的。所以，对于自动驾驶系统来说，要渗透到这些边缘领域，其扩散曲线会比轿车或货车这类标准化产品要长得多。

<details>
<summary>Original English</summary>

**Sanj**: I think on the robo taxi side it's going to happen a bit faster because the operations are much more regional. Um they're much more um similar, right? Like the way that you and I ride in a taxi across town is going to be quite similar. And so that's I think where you're going to see the biggest sort of like visible impact of autonomous vehicles. Um, on the trucking side, it's also important to realize like there's long haul trucking and kind of like moving stuff from point A to point B. That tends to be a minority fraction of what the commercial vehicles on the road are doing. Most of the commercial vehicles are um in like industries like field service, right? So, they're HVAC technicians or plumbers, electricians, so people performing some work. Um, and they're also they're either doing something like that or they're in industries like construction where they're building the road. that tends to be where current day sort of like autonomy doesn't work so well. It's like the really messy long tail. So for that reason, we think the adoption might be a bit slower, but it's not like a no. It's just it might take 10 20 years. And these are industries where again the equipment's highly specialized. Like if you look at cement mixers or you know garbage trucks, like these are custom built. So for um for the autonomy systems to make their way out to that edge is just going to be a longer diffusion curve than you know for a sedan which is or or a van or something like that which is very much the same.

</details>

### 美国工业实力的现状

**主持人**: 太好了。最后，我很好奇，你身处实体经济的核心，就像我们对话开始时说的，交通、公用事业、制造业，所有这些基础性的重要领域。你对当今美国工业实力的真实情况有什么感觉？你看到的是同样的速度，还是在加速？呃，AI热潮和数据中心对你的客户有实际影响吗？你对这种“速度”有什么感觉？

<details>
<summary>Original English</summary>

**Host**: Great. Maybe to to close um I'm very very curious like you're at the heart of this real economy as we said at the at the beginning of this conversation transportation and utilities and manufacturing and all those you know fundamentally important things. What what's your sense of the reality of American industrial power today? Are you seeing same level of velocity? Are you seeing an acceleration? Uh is the AI boom and like the data centers like having a real impact on your customers? What what's your um sense of the level of just um velocity?

</details>

**Sanj**: 是的，非常明显。所以我认为我们的客户，很明显，他们比以往任何时候都更忙。所以从美国经济的角度来看，我们看到的是非常高的强度。我上周刚和一个大型能源公用事业公司去了一线。他们参与了电网现代化改造，他们跟我分享了一个非常有趣的数据。他们说，在过去125年里，我们建设了一定数量的电网容量，单位是兆瓦或吉瓦。而在未来5年内，我们将把这个数字翻三倍。也就是说，他们公司将要交付的电力总量是现在的三倍。而这要在五年内完成，对比之前的一百二十五年。这需要建设大量的基础设施，即使有新技术也是如此。他们就是觉得工作速度不够快。我们在许多不同的行业都看到了这种情况。在这种情况下，他们还分享说，90%的需求与数据中心相关。所以，随着数据中心需求的持续飙升，能源需求或者说所有那些不断出现的瓶颈问题也随之而来。我们许多实体运营公司，呃，客户公司，都直接参与其中。

<details>
<summary>Original English</summary>

**Sanj**: Yeah, very much. So I I think our customers have it's very clear they're busier than they've ever been before. So from like an American economy perspective, like we're seeing a lot of intensity. Um I was just in the field last week with a large energy utility. Um and they've been involved in grid modernization and uh they shared with me a really interesting stat. They said, you know, over the last 125 years, we built a certain amount of grid capacity in in megawatts or or gigawatts really. Um in the next 5 years, we're going to triple that. Like they as a company are going to 3x the amount of power they deliver. And that's like in five years versus 125 years. So that requires a tremendous amount of infrastructure build even with new technologies. It's like they can't work fast enough. U we are seeing that across so many different kinds of industries. And in that case like they also shared you know 90% of that demand is data center related. So as the data center demand continues to skyrocket the energy needs or all these like different bottlenecks that have been appearing. So many of our physical operations companies uh customer companies are involved in in that directly.

</details>

**主持人**: 我知道你的客户雇佣了很多技术工人。你对技工行业的演变有什么看法？比如，过去几年我们都看到一种说法，如果你的律师工作要被自动化了，那么当个水管工可能是个好主意。这虽然有点开玩笑，但我很好奇你的看法。

<details>
<summary>Original English</summary>

**Host**: I know a lot of people that your customers employ are trades people. What what's your take on evolution of trade? Like the the the idea that you know we've seen we've all seen in the last like couple of years is that uh actually being a plumber uh becoming a plumber might be a great idea if your lawyer job is going to get automated. Some of it is some level joke but I'm I'm curious about uh what what you what what you take is

</details>

**Sanj**: 是的。我要提醒那些想转行当水管工的律师们，这活儿挺脏的，对吧？而且难度大得多。嗯，是的，我们一直看到，在许多不同的技工行业，以及像长途运输、持有商业驾照的司机等领域，基本上都存在劳动力短缺和瓶颈。所以，总的来说，我认为对这些职业的需求正在大幅增长。数据中心的热潮就是一个很好的例子。现在就是没有足够的电工。所以你会看到像Meta这样的公司推出计划，对人员进行再培训，教他们如何成为一名合格的电工，然后如何让这些受过培训的人尽可能高效地工作。你不想让他们在工地上等材料，而是希望把他们派到需要他们技能的地方去工作。所以这确实是一个瓶颈，但技工的需求量非常大。同时，我认为他们的工作也在变得更加现代化，因为你想，作为一名电工，很多工作就是到达工地、备好材料、知道要做什么。如果人工智能能在这些方面提供帮助，就能减轻很多脑力负担，让他们可以专注于自己独特的、真正的技工价值。

<details>
<summary>Original English</summary>

**Sanj**: Yeah. I I I will warn the lawyers thinking about becoming plumbers. It's it's a pretty messy job, right? So, it's much harder. It's it's pretty hard stuff. Um, so yes, we've been continuing to see that there's a basically a labor shortage, labor bottleneck in a number of different trades, but also things like long haul trucking, commercial driver's license holders, things like that. So, uh, in general, I think there's a lot of growing demand for these uh, professions. And this data center boom is a great example. There are just like not enough electricians, uh, out there right now. So you see companies like Meta doing initiatives to like reskill people, train them on how to become, you know, a good electrician and then how can you take the people who are trained and make their jobs as efficient as possible. So you don't want them like waiting on materials at a job site like you want to put them to work to perform uh you know wherever their skills are needed kind of thing. So very much kind of a bottleneck, but the trades are in incredible demand. And I also think that their jobs are getting um more modernized as well because if you think about it as an electrician, a lot of it is getting to the job site and having the materials and knowing what you're going to do. If an AI can kind of help you with that, it takes a lot of the mental load off and you can focus on on the really unique trade kind of value you have.

</details>

**主持人**: 那么，Sanj，这是一次非常棒的对话。非常感谢你。我们对你们正在继续构建的东西以及它在整个经济中的重要性感到非常兴奋，很高兴能了解更多。谢谢你。

<details>
<summary>Original English</summary>

**Host**: Well, Sanj, it's been a fantastic conversation. Thank you so much. very excited about uh what you guys are continuing to build and like its sheer importance in the overall economy and it's been wonderful to learn more about it. So, thank you.

</details>

**Sanj**: 谢谢。这很有趣。

<details>
<summary>Original English</summary>

**Sanj**: Thank you. It's been fun.

</details>

**主持人**: 嗨，我是Matt Turk。感谢收听本期Mad播客。如果你喜欢这期节目，我们将非常感激如果你能...

<details>
<summary>Original English</summary>

**Host**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would

</details>

<!-- chunk 9/9 -->

### 结尾致谢

**主持人**: 如果你还没订阅，请考虑订阅，或者在你观看或收听本期节目的平台上留下好评或评论。这真的能帮助我们建立播客，并邀请到优秀的嘉宾。谢谢，我们下期节目见。

<details>
<summary>Original English</summary>

**Host**: Consider subscribing if you haven't already, or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks and see you at the next episode.

</details>