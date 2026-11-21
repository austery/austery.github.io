---
author: Bloomberg Podcasts
date: '2026-03-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=_jYFDx6B9iU
speaker: Bloomberg Podcasts
tags:
  - autonomous-weapons
  - military-ai
  - ethical-ai
  - human-in-the-loop
  - ai-governance
title: Anthropic、五角大楼与自主武器的未来
summary: 本期播客深入探讨了人工智能在军事领域的应用，特别是围绕Anthropic与五角大楼关于AI工具使用权的分歧。嘉宾Paul Sharie解释了自主武器的定义及其发展趋势，并分析了AI在目标识别、作战规划中的实际应用。讨论还涉及了AI技术商业化与军事应用之间的张力、政府自研AI的挑战、AI安全领域的“逐底竞争”以及自主武器可能带来的伦理困境和冲突升级风险。节目强调了在AI日益强大的背景下，人类决策和道德责任在战争中的不可替代性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Paul Sharie
  - Stanislav Petrov
companies_orgs:
  - Anthropic
  - OpenAI
  - Google
  - Palantir
  - Department of Defense
  - Center for a New American Security
products_models:
  - Claude
  - Gemini
  - ChatGPT
  - Starlink
  - Project Maven
  - DeepSeek
media_books:
  - 'Four Battlegrounds: Power in the Age of Artificial Intelligence'
  - 'Army of None: Autonomous Weapons and the Future of War'
  - Dan Carlin's Hardcore History
status: evergreen
---
### AI与自主武器的争议

**Joe Wisenthal**: 大家好，欢迎收听《OddLots》播客的又一期节目。我是**Joe Wisenthal**。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Hello and welcome to another episode of the OddLots podcast. I'm Joe Wisenthal.

</details>

**Tracy Aloway**: 我是**Tracy Aloway**。**Tracy**，我们录制这期节目是在3月24日，当然，我们最近几乎所有的节目都与伊朗战争有关。

<details>
<summary>Original English</summary>

**Tracy Aloway**: And I'm Tracy Aloway. So Tracy, we're recording this March 24th and of course almost all of our episodes lately have been about the war in Iran.

</details>

**Joe Wisenthal**: 但有趣或者说有点奇怪的是，就在战争爆发前几天甚至几小时，世界上最大的新闻实际上是关于国防和**国防部**（DoD）的。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: But what's interesting or what's a little weird is that just prior to the war, literally days or maybe hours, the biggest story in the world was actually about defense and you know the DoD.

</details>

**Tracy Aloway**: 没错。你指的是**Anthropic**公司与**国防部**之间，委婉地说，存在分歧。

<details>
<summary>Original English</summary>

**Tracy Aloway**: That's right. So you are referring to anthropics and its disagreement to put it mildly with the department of war.

</details>

**Joe Wisenthal**: 是的，没错。这是在伊朗战争前夕最大的新闻。当然，显然存在这份合同，**Anthropic**的技术被**国防部**使用。所以，这并不是关于**AI**本身在战争中使用的分歧。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Yeah, exactly. This was the biggest story going right up on the eve of the war in Iran. And of course, obviously, there was this contract and anthropics technology was used by the defense department. So, it was not a disagreement about the use of AI per se in war.

</details>

**Tracy Aloway**: 而是关于**AI**在多大程度上可以用于**自主武器系统**，在没有人类干预的情况下独立运作。

<details>
<summary>Original English</summary>

**Tracy Aloway**: But the question of the degree of to which AI could be used for autonomous weapon systems on their own without a human in the loop.

</details>

**Joe Wisenthal**: 还有监控。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And surveillance, that was.

</details>

**Tracy Aloway**: 监控和监视。这是另一个关键要素。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Surveillance and surveillance. This was another key element.

</details>

**Joe Wisenthal**: 但你说得对。我们听到“**自主武器**”这个词越来越多地出现，尤其是在最近几天。我对这到底意味着什么有很多疑问，因为我的印象是，美国军方肯定已经使用**AI**一段时间了。所以，我们这里谈论的实际上是自主程度，对吗？是的，如果你想到**自主武器**，我想你的脑海中可能会浮现出《**终结者**》的场景，你知道，有一个杀人机器人正在自主决定要攻击哪些人或地点，然后你就会想到低于这个级别的各种情况，对吗？**AI**只是在某种程度上帮助人类做出战略决策。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: But you're right. So, we've heard this expression autonomous weapons pop up more and more, especially in recent days. And I have a lot of questions over what exactly that means because my impression is the US military certainly has been using AI for some time. And so, we're really talking about degrees here of autonomy, right? And so yes, if you if you think about an autonomous weapon, I think your mind could go fully Terminator and you know there's like a murder robot out there that's making its own decisions on which people or places to target and then you get levels below that, right? Where AI is kind of helping humans to come up with strategic decisions,

</details>

**Tracy Aloway**: 对吗？所以如果有一枚导弹袭来，你有一个导弹防御系统，我想你不会希望有人在回路中说：“好的，这是我们认为它会击中的XYZ坐标。在此时此刻，我们认为导弹会在这里。你同意发射吗？”我想每个人可能都同意这种程度的自主性。但我觉得，正如你所说，很多讨论，也许是**Anthropic**和**国防部**之间分歧的核心，我觉得很多都将归结于定义。我猜对于什么是**自主武器系统**，什么不是，并没有一个共同的定义。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Right? So if there is a missile coming and you have a missile defense system, I don't think you want a human in the loop is like, "Okay, here are the coordinates XYZ that we think it's going to hit. At this point in time, we think the missile will be here. Are you cool with firing it?" I think everyone's probably okay with that level of autonomy. But I have a feeling that to your point exactly a lot of this discussion and maybe it's core to what Anthropic and the Department of Defense were disagreeing on. I have a feeling a lot of this is gonna come down to definitions. My guess is that there is not one shared agreement of this is an autonomous weapon system and this one is not.

</details>

**Joe Wisenthal**: 绝对是。当然，还有关于像**国防部**这样的机构究竟如何定义它，以及一旦他们有了这些定义，某些公司是否信任他们会坚持这些政策的问题。因为美国会说，目前我们的政策是不监视我们的公民。所以，如果你是**Anthropic**，你不需要担心。显然，**Anthropic**有不同的看法，或者说他们是这样说的。所以，所有这些都引出了许多真正有趣的主题问题。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Absolutely. And of course there are also questions over exactly how places like the Department of Defense, not only how they define it, but once they have those definitions, whether or not certain companies trust them to sort of stick to those policies. Because the US will say, well, our policy is not to survey our citizens at the moment. So, if you're anthropic, you don't need to worry about that. Clearly, anthropic feels otherwise or say they do. So, there are all these really interesting thematic questions that pop up from all of this.

</details>

**Tracy Aloway**: 完全正确。然后就出现了这样的问题：好吧，这里有一项技术，政府说我们相信可以用它来让国家更安全。什么？你们不让我们用？就像私人公司一样。关于企业权力与政府之间的关系等等，有一些非常有趣的问题。总之，这已经变得更加及时。甚至在伊朗战争初期，就有报道称这些**AI系统**可能被用于目标选择，但我们并不真正清楚。所有报道都没有那么明确。我不认为他们会出去宣传这次打击。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Totally. And then there's the question of okay, here's a technology and the government says we believe that we can use this to make the country safer. What? You're not going to let us do it? Like private corporation. There are some very interesting questions about the role of corporate power visa v the government and so forth. Anyway, this is uh something that has become even more timely. There were reports even in the early days of the Iran war about these AI systems having been used perhaps in target selection, but we don't really know. None of the reporting is like that clear. I don't think that they're going out and advertising the strike.

</details>

**Joe Wisenthal**: 这就是我们使用**AI**的方式。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: This is exactly how we're using AI.

</details>

**Tracy Aloway**: 这就是我们使用**AI**的方式等等。但这显然是一个巨大的争论，撇开战争不谈，它真的会发展壮大，就像**AI**似乎将在许多不同领域发展一样。总之，我很高兴地说，我们确实请到了最完美的嘉宾，一位长期以来一直在撰写和思考这些问题的人。当我们与**AI**专家交谈时，我将分界线划定为：你在**ChatGPT**发布之前是否就已经在谈论**AI**了？我更认真地对待那些在2022年11月之前就已经在这个领域的人。总之，我非常高兴地说，我们将与**Paul Sharie**对话。他是**新美国安全中心**的执行副总裁，并且是两本相关书籍的作者。其中一本是最近的《**四大战场：人工智能时代的权力**》，在此之前，他还著有《**无兵之师：自主武器与战争的未来**》。他曾任职于**国防部长办公室**，也是一名前陆军游骑兵。所以，他真的是最完美的嘉宾。**Paul**，非常感谢你来到《OddLots》。

<details>
<summary>Original English</summary>

**Tracy Aloway**: This is exactly how we're using AI and so forth. But this is obviously a huge debate and war aside, it's really going to grow and just as an AI is going to grow it seems in so many different areas. Anyway, I'm really excited to say we really do have the perfect guest, someone who's been writing and thinking about this stuff for a long time. When we talked to an AI expert, I marked the dividing line is like were you talking about AI prior to when Chad GBT was released as like I take a little bit more seriously the people who are in this space prior to November 2022. Anyway, I'm very excited to say we're going to be speaking with **Paul Sharie**. He's the executive vice president at the **Center for a New American Security** and he's the author of two books related to this. One is uh the most recent **Four Battlegrounds: Power in the Age of Artificial Intelligence** and then prior to that he is the author of **Army of None: Autonomous Weapons and the Future of War**. He was previously in the office of the secretary of defense also a previous army ranger. So truly the perfect guest. So Paul thank you so much for uh coming on OddLots.

</details>

**Paul Sharie**: 哦，谢谢你们邀请我。很高兴来到这里。

<details>
<summary>Original English</summary>

**Paul Sharie**: Oh, thank you for having me. Very excited to be here.

</details>

**Joe Wisenthal**: 我们何不从头开始？我提到我有一种感觉，也许**自主武器**的定义是一个有争议的问题。但如果我问你，什么是**自主武器**？什么是**自主武器**？

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Why don't we start? I mentioned I had a feeling that maybe the definition of an autonomous weapon is a contested one. But if I say to you, what's an autonomous weapon? What's an autonomous weapon?

</details>

### 自主武器的定义与发展

**Paul Sharie**: 所以，我认为你从一开始就说对了，没有一个所有人都能达成共识的统一定义。**国防部**在他们的政策中写明了他们的定义。我认为从概念上讲，真正的区别在于一种在战场上选择自己目标的武器。好的，这并不是我们今天所处的情况，现在人们正在选择这些目标。

<details>
<summary>Original English</summary>

**Paul Sharie**: So, I think you're right from the beginning that there is not a unified definition that everyone agrees on. The Defense Department has their definition that's written in their policy. I think conceptually I think the distinction really is a weapon that is choosing its own targets okay on the battlefield and it's not where we are today right now today people are choosing those targets.

</details>

**Joe Wisenthal**: 但它确实是一个光谱，因为我们确实有一些具有一定自主性的武器。一个很好的类比可能是**自动驾驶汽车**，从概念上讲，**自动驾驶汽车**就是**AI**驾驶汽车，但当你今天坐进一辆真正的汽车时，很多都配备了**智能巡航控制**、**自动刹车**、**自动泊车**。它们都有这些**自动化功能**，这些功能正在逐渐将你引向**AI**接管车辆更多控制的方向。这在军事领域实际上也是非常相似的情况。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: But it is kind of a spectrum because we do have examples of weapons that have some measure of autonomy a good analogy might be self-driving cars where conceptually like okay a self-driving car would be where the AI is driving the car but then you get into an actual car today and a lot of them have intelligent cruise control, automatic braking, automated self-parking. They have all these like automated features that are kind of creeping you in this direction where the AI is taking over more and more control for what the vehicle can do. And it's actually pretty similar thing in the military space as well.

</details>

**Tracy Aloway**: **Joe**提到，如果我们哪怕在一个月前进行这次对话，可能就不会有那么多关于**AI**赋能武器或战略的具体例子。当**五角大楼**谈论它为伊朗冲突部署的**先进AI工具**时，你现在看到的哪些例子与一年前我们发生另一次伊朗冲突时有所不同？

<details>
<summary>Original English</summary>

**Tracy Aloway**: So Joe mentioned that had we been having this conversation even a month ago now, it probably would have had fewer concrete examples of AI enabled weaponry, let's say, or strategy. When the Pentagon talks about its advanced AI tools that it's deploying for the Iran conflict, what are some examples that you're seeing right now that are different to say maybe just a year ago when we had another Iran conflict?

</details>

### AI在军事冲突中的应用

**Paul Sharie**: 好的。**五角大楼**目前使用**AI**的方式有几种。一种是已经存在十多年的**窄域AI系统**，例如**图像分类**。这是军方近十年前最初的**Maven项目**，他们使用**机器学习图像分类器**来筛选无人机视频和卫星图像，以识别物体。好的，这是一个建筑物，这是一个人物，这是一辆车。这是一种相当成熟的技术。现在，在过去几周内出现了一个非常有趣的情况，那就是在**Anthropic**和**五角大楼**之间这场巨大而混乱的公开“分手”中，我们发现**Anthropic**的**AI工具**实际上正被美国军方用于协助规划对伊朗的战争。这显然是一种不同类型的**AI工具**。**AI大型语言模型**，**AI**被用于编写代码，**AI代理**，并且以不同的方式使用。它确实在帮助情报分析师筛选美国军方拥有的海量数据。所以，如果你能想象军方现在在查看伊朗目标时面临的问题，美国军方已经对伊朗进行了超过6000次**空袭**。伊朗的军事架构在很多方面都已退化。美国军方轰炸了许多目标。有移动目标，伊朗高级指挥官，移动导弹发射器，防空系统和无人机发射器。美国军方必须将所有这些信息整合起来，找出这些目标现在在哪里，以及哪里有携带正确炸弹的飞机可以摧毁这些目标。这就是**AI**被用来帮助基本处理和理解所有这些信息的方式。当我想到你对它的描述时，我有时会想，难道不是这样吗？现在我并不认为使用**Anthropic**的技术意味着他们会进入**Claude.ai**并说给我们一份适合出击的目标清单，但它可能就是那样吗？我确信有不同的界面等等，但这本质上是不是一种完全荒谬的方式来描述**AI**现在提供的服务？

<details>
<summary>Original English</summary>

**Paul Sharie**: Right. So, there's a couple ways in which the Pentagon is using AI right now. One is narrow AI systems that have been around for over a decade now that do image classification, for example. So, this was the military's original **Project Maven** almost a decade ago where they took machine learning image classifiers to sift through drone video feeds and satellite images to identify objects. Okay, here's a building. Here's a person. Here's a vehicle. That's pretty mature technology. Now, what's come out in just the last couple weeks that's really quite interesting is that in the midst of this huge messy public breakup between **Enthropic** and the **Pentagon**, we found out that in fact **Anthropic**'s **AI tools** are being used by the US military to help plan the war against Iran. That's obviously a different kind of **AI tool**. **AI large language models**, **AI** being used to write code, **AI agents**, and that's being used in a different way. It's really helping intel analysts sift through just the massive amounts of data that the US military has. And so if you can imagine the problem that the military is facing right now when they're looking at targets in Iran, US military's flown over 6,000 **sorties** against Iran. The Iranian military architecture is degraded in a lot of ways. US military bombed a lot of targets. There are mobile targets, senior Iranian commanders, mobile missile launchers and air defense systems and drone launchers. US mil got to bring all that information together and find out where are these targets right now and where is there an aircraft that has the right bombs on it to take these targets out. And that's how **AI** is being used to help basically process and understand all that information. When I think about the description that you gave for that, I sometimes think like could it be that now I don't think that using anthropics technology means they go into **claw.ai** and say give us a list of suitable targets for sorties, but it could be could it be something like that? I'm sure there's a different interface and so forth, but is that a completely ridiculous way of essentially framing the service that AI is providing right now?

</details>

**Paul Sharie**: 这些**AI工具**的集成方式是通过一个名为**Maven智能系统**的现有系统。好的，这个系统由**Palantir**构建，它将所有这些数据融合在一起。所以你基本上有一个现有的数据管理架构，供军事情报分析师使用，它汇集了所有这些不同形式的数据。你可能有卫星图像、地理定位数据、信号情报和其他形式的信息。这对情报分析师来说非常棒，但这也非常笨重，因为人类如何理解和处理所有这些数据？这就是**大型语言模型工具**，无论是**Claude**还是其他公司，其价值所在，它可以成为人类与这些数据交互的一种方式，基本上可以指示**大型语言模型**说：“好的，我给你一堆数据。我希望你寻找事物中的交集，对吗？我希望你寻找一个我们有卫星图像和其他形式情报的地方，可以帮助识别某个导弹发射器的位置，例如，然后人类可以查看这些信息，并帮助找到所有这些目标。”

<details>
<summary>Original English</summary>

**Paul Sharie**: So the way that these **AI tools** are being integrated are through a existing system called the **Maven smart system**. Okay, which is built by **Palunteer** and that fuses all this data together. So you basically have an existing architecture for data management for intel analysts that the military has that brings together all these different forms of data. You might have satellite imagery, geoloccation data, signals intelligence, other forms of information. That's pretty great for intel analysts, but that's also really unwieldy because how does a human understand all that data and process it? And that's where the **large language model tools**, whether it's **Claude** or other companies, can be valuable is there can be a way for a human to interact with that data to basically task a **large language model** to say, "Okay, here's a bunch of data I'm giving you. I want you to look for intersections in things, right? I want you to look for a place where we have satellite imagery and some other forms of intelligence that can help identify the location of you know some missile launcher for example and then humans can look at that and help one just like find where are all these targets."

</details>

**Joe Wisenthal**: 然后它在规划中也很有帮助。人类可以说，好的，这是我目前拥有的潜在目标清单，它们散布在伊朗各地，伊朗是一个很大的国家。我想将这些目标映射到美国飞机在该地区不同基地的位置，有哪些可用的飞机以及这些飞机上可用于摧毁这些目标的弹药，以帮助构建一个打击方案。所以，**AI**肯定被用于帮助理解战场空间和规划行动，但我会说，其方式是由人类非常狭隘地指导的。它不像把所有这些数据倾倒到**大型语言模型**的上下文窗口中，然后说**AI**自己解决那么简单。好的。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And then it's helpful in planning too a human could say okay here's this list of potential targets that I have now they're scattered all over Iran Iran's a really big country I want to map these to locations for US aircraft at different bases across the region, what are available aircraft and what are available munitions on those aircraft that can be used to take out those targets to help build a strike package. So like the **AI** is definitely being used to help understand the battle space and to plan operations, but in I would say ways that are pretty narrowly directed by people. It's not quite as simple as like dump all this data into a context window for an **LLM** and then say **AI** figure it out. Okay,

</details>

**Tracy Aloway**: 人们正在向**AI**提出一些非常具体的问题。

<details>
<summary>Original English</summary>

**Tracy Aloway**: People are asking the AI some really specific questions.

</details>

### 人类在决策回路中的角色

**Joe Wisenthal**: 所以，我正在思考如何委婉地提出这个问题，但我明白**完全自主武器**与当前设置中作为决策者的人类之间的区别。人类实际上有多大意义？你对此有何看法？因为我正在想象，如果你是一名情报官员，你从伊朗收到大量数据，你要求**AI**找出某些模式或识别潜在的战略目标，你实际上对模型输出的结果做了多少尽职调查？因为当然，很多人使用**大型语言模型**时，肯定倾向于直接接受屏幕上显示的内容。再补充一下**Tracy**的问题，因为这是我想深入探讨的地方，那就是在战争初期，我们击中了那所学校。是的。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: So, I'm thinking how to phrase this question diplomatically, but I get that the difference between fully autonomous weapons is, you know, the human as a decision maker in the current setup, how meaningful is the human actually? Like what's your sense of it? Because I'm imagining if you're an intelligence officer and you're getting reams and reams of data from Iran and you ask the **AI** to pick out certain patterns or identify potential strategic targets, how much due diligence are you actually doing on what that model spits out? Because of course the tendency when a lot of people use **LLM** certainly is just you accept what it shows you on the screen. And just to add on to Tracy's question because this is where I want to go, which is that in the early days of the war, we hit that school. Yeah.

</details>

**Tracy Aloway**: 我正在阅读《**纽约时报**》的一篇报道，那次事件是由于**国防情报局**提供的“过时数据”造成的。现在，我们不确切知道这意味着什么，但好的，各种输出结果出来了。然后会发生什么？目前人类层面的干预有多少？比如，这里是目标，这里是战舰上的船只。这可能是合理的。你对某些输出结果和最终下达打击命令之间的人类决策水平有什么看法或了解？

<details>
<summary>Original English</summary>

**Tracy Aloway**: And there I'm reading a New York Times report and that was out the result of quote outdated data provided by the Defense Intelligence Agency. Now, we don't know exactly what that means, but okay, various outputs come out. Then what happens like how much is the human layer currently in terms of okay, here are targets, here are ships that are on a battleship. this could be plausible. What do you think or what do you know about the level of human decisionmaking that happens between some output and then the ultimate call for a strike on whatever it is?

</details>

**Paul Sharie**: 是的，我的意思是，我认为首先这是一个非常重要的问题，因为它确实是**AI**及其使用方式可能出现的故障模式之一。

<details>
<summary>Original English</summary>

**Paul Sharie**: Yeah, I mean I think first of all I think it's a really important question because it is one of the possible failure modes if you will of AI and how we use it.

</details>

**Joe Wisenthal**: 因为你最终可能会陷入一种境地，人类名义上在回路中，你可以说它不是**自主武器**。人类正在做出这些决定，但如果人类没有真正参与，他们只是在某种程度上盖章批准某种决定，那么这并不是我们想要的。所以，我认为这是一个长期以来许多人对**自主武器**感到担忧的问题。我认为这在使用**AI**时是一个非常真实的风险。现在，根据我对**AI技术**在**Maven**中如何使用的理解，以及我所看到的实际演示，因为我确实看到了一些实际演示。我认为人类现在非常参与，他们实际上会查看**AI**的输出，并向**AI系统**提供非常具体的指导。我确实认为存在一个潜在的挑战，即对学校的打击事件所凸显的，那就是当你谈论成千上万个目标时。在战争爆发前，对所有这些信息进行了多少程度的审查？在这种情况下，那所学校是一个固定目标，因此这很可能是在战争爆发前应该进行更彻底审查的事情，有人本可以识别出被击中的那栋建筑曾是伊朗军事大院的一部分，但你可以根据公开可用的卫星图像看到，它在很久以前就已从该大院中移出，并已改建为学校，根据《**泰晤士报**》的报道，这些信息似乎从未更新过。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Because you could end up in a place where humans are nominally in the loop and you could say well it's not an autonomous weapon. human's making these decisions, but if the human is not meaningfully engaged and they're just kind of rubber stamping some kind of decision, then that's not really what we're looking for. So, I think that's a it's been a long-standing concern for many years about people worried about autonomous weapons. And I think that's a very real risk with how AI is used. Now based on my understanding of how the **AI technology** is used in **Maven** today and based on what I've seen of demonstrations of it because I have seen some demonstrations of this in action. I think humans are pretty involved right now in terms of actually looking at the output from **AI** giving pretty specific guidance to the **AI systems**. I do think there is a an underlying challenge that the strike on the school highlights which is when you're talking about thousands and thousands of targets. What's the degree of vetting that's gone into all of that information both in the runup to the war, which in this case that school was a fixed object and so that's likely something that should have clearly been much more vetted prior to the war kicking off that someone could have identified that that building that was struck had actually been at one point in time part of an Iranian military compound, but you could see based on public available satellite imagery that it had been moved out of that compound some time ago and had been converted to a school and it would appear based on what's been reported in the times that that information had never been updated.

</details>

**Paul Sharie**: 在这个**DIA**目标数据库中。现在，

<details>
<summary>Original English</summary>

**Paul Sharie**: In this DIA targeting database. Now,

</details>

**Joe Wisenthal**: 我希望我们将来能获得更多信息，并进行一些调查，以确切了解哪里出了问题，但我认为这确实说明了数据输入到**AI系统**的质量以及人们审查的彻底程度这一潜在挑战。而且，原则上，**AI**可能能够帮助你处理这些事情，但你必须以正确的方式使用它。而且人们仍然必须有意义地参与到这些决策中。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: I would hope that we'll get more information in the future and some investigation about exactly where that went wrong, but I think that does speak to this underlying challenge of how good is the data going into this **AI system** and how thoroughly are people vetting it. And again, in principle, **AI** might be able to help you with those things, but you got to use it the right way. And people still have to be meaningfully engaged in these decisions.

</details>

### 五角大楼政策与科技公司立场

**Joe Wisenthal**: 我们为什么不先回顾一下？告诉我们你在这个领域所做的工作。你真的比其他人提前好几年就谈论这些事情，规划这些事情。给我们介绍一下你的背景，以及是什么让你在**ChatGPT**出现前好几年就踏上了这条道路。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Why don't we back up for a second? Tell us about the work that you've done in this area. really several years ahead of the curve and talking about this stuff, planning for this stuff. Give us a little bit of sort of your background and what got you on this train again several years before Chad GPT.

</details>

**Paul Sharie**: 是的。所以，实际上在十多年前，大约在2011年左右，当我在**国防部长办公室**工作时，我领导了一项在**五角大楼**内部开展的工作，旨在制定**五角大楼**关于武器自主性作用的政策。事实上，这项政策至今仍在生效，当时我们远未达到军方现在整合**AI工具**的程度。我的意思是，这些类型的**大型语言模型**当时根本不存在。但军方已经开始意识到我所说的伊拉克和阿富汗战争期间的“**意外机器人革命**”，当时军方部署了数千架空中和地面机器人，空中的无人机和用于拆除炸弹的地面机器人。军方开始思考这在未来会走向何方？每个人都能看到的一件有价值的事情是，这些系统将拥有更多的自主性。能够不完全依赖人类远程控制它们的能力，这在当时确实是常态。但这显然引发了所有这些棘手的问题，比如，它们应该拥有多少自主性，以及这会带来哪些法律和伦理影响？这在当时军事人员和**五角大楼**从事这些问题的人员中引起了大量讨论。因此，这最终导致了那项关于武器自主性作用的政策指令，该指令至今仍在实施。然后，当我离开政府后，我继续研究这个话题，因为我们看到了通过**联合国**进行的国际讨论，也看到了技术以惊人的方式发展，但同时也伴随着**人工智能**带来的风险。所以，当你从事那份工作时，我知道你是在政策方面，但你有没有看到承包商方面出现类似我们现在与**Anthropic**看到的情况？比如，有没有承包商说过：“不，实际上，我对**国防部**想要使用这项特定技术的方式感到非常不舒服。”

<details>
<summary>Original English</summary>

**Paul Sharie**: Yeah. So really over a decade ago now around say 2011 I led an effort inside the Pentagon when I worked at the office of the secretary of defense on developing the Pentagon's policy on the role of autonomy in weapons. Uh the one that's still in effect today in fact and that was really part of at the time we weren't at all where the military is now in terms of integrating AI tools. I mean, these types of **large language models** just didn't exist at the time. But the military had kind of woken up to what I would call this accidental robotics revolution during the wars in Iraq and Afghanistan where the military had deployed thousands of air and ground robots, drones in the air and ground robots for diffusing bombs. And the military was starting to think through where is this going in the future? And one of the things that everyone could see would be valuable would be having more autonomy in these systems. The ability to not be totally reliant on a human remotely controlling them, which was really the case at the time. But that raised all these obviously thorny questions about like, well, how much autonomy should they have and what are the legal and ethical implications of that? And that was actually a topic of a lot of discussion among people in the military at the time and in the Pentagon for people working on these issues. And so that ultimately led to that policy directive that's still in place on the role of autonomy and weapons. And then when I left the government, I continued to work on this topic as we've seen discussions internationally through the **United Nations** as we've seen the technology evolve in really amazing ways, but also ones that have risks with **artificial intelligence**. So, when you were doing that job, I get that you were on the policy side, but did you ever see anything on the contractor side similar to what we're seeing with **anthropic** right now? Like, was there ever a contractor who said, "Actually, no. I'm really uncomfortable with the way that the department wants to use this particular tech."

</details>

**Paul Sharie**: 当时没有。几年后，在美国军方启动**Maven项目**后，当**Google**参与**Maven项目**的消息公开时，引起了轩然大波，许多**Google**员工签署了一封公开信抗议，**Google**最终停止了他们在**Maven项目**上的工作。你知道，这与现在发生的事情并非完全相同，但在**AI**社区中一些人对他们的技术在战争中应该如何使用以及军方对此的看法之间，确实存在一些相似之处。我认为部分原因是**AI**与许多传统军事技术非常不同，因为它来自商业领域。所以从某种意义上说，它有点像**隐形技术**的反面，**隐形技术**是在秘密国防实验室发明的，没有太多商业应用。**AI**则有所有这些不同的应用。它不是由军方发明的。军方不得不将其引入，而且关于**AI**在军事和更广泛社会中应该如何使用，存在很多争论。实际上，就这一点而言，我认为这非常有趣，而且绝对是军事工业复合体历史上一个关键时刻，但为什么美国政府凭借其所有资源，不能实际上内部开发**AI**，从而避免与商业企业打交道的明显复杂性？

<details>
<summary>Original English</summary>

**Paul Sharie**: Not at that time. Now, a few years later, after the US military launched **Project Maven**, there was a big dust up when it came out publicly that **Google** had been a part of **Project Maven** and a number of **Google** employees signed an open letter protesting that and **Google** eventually discontinued their work on **Project Maven**. And you know, it's not an exact replica here of what's going on, but there are certainly some similarities in terms of a disconnect between how some people in the **AI community** are thinking about how their technology ought to be used in war and how the military is thinking about it. And I think part of that's like there's this underlying challenge of **AI** is really different than a lot of traditional military technologies because it's coming out of the commercial sector. So in a way it's kind of like the opposite of stealth technology that was invented in secret defense labs and doesn't have a lot of commercial applications. **AI** is all of these different applications. It's not being invented by the military. The military is having to import it in and there are a lot of debates about how a **AI** should be used in the military and more broadly in society. Actually, on that note, I think this is really interesting and definitely a pivotal point in I guess the history of the military-industrial complex, but why can't the US government with all its resources actually develop **AI** in-house and just avoid the seeming complication of having to deal with a commercial enterprise?

</details>

### 政府自研AI的挑战

**Paul Sharie**: 部分原因是它不具备技术技能。**AI科学家**和工程师确实存在，而且在**AI领域**对人才的竞争非常激烈，所以军方就是无法购买到这些人才。他们没有。政府每年在国防上花费数百亿美元。但我们实际上在过去几年中看到，私营企业能够调动大量资本用于建设数据中心和训练**AI模型**。部分原因在于这项技术的商业应用远大于国防应用。因此，对于许多科技公司来说，至少在过去，可能并非在当前这个特定案例中，但通常会因为说“哦，你知道，空军使用我们的**AI系统**”或“海军使用我们的技术”而获得一些声望，但国防部门对他们来说实际上是一个相对较小的客户。我的意思是，**Anthropic**合同公开讨论的金额是2亿美元。对于这些**AI公司**来说，这并不是很多钱。是的。

<details>
<summary>Original English</summary>

**Paul Sharie**: Partly, it doesn't have the technical skills. the **AI scientists** and engineers are really in and there's a fierce competition for talent in the **AI space** and so the military just like can't buy that talent. they don't have it. And the government spends a lot of money, hundreds of billions of dollars annually on defense. But we've seen actually in the last few years that private enterprise is able to mobilize massive amounts of capital towards building data centers to training **AI models**. And partly because the commercial applications for this technology are much bigger than the defense applications. And so for a lot of these tech companies there's some at least maybe not in this particular instance but in the past there could often be some prestige associated with saying oh you know the air force uses our **AI system** or the Navy uses our technology but the defense sector is actually kind of small for them as a customer. I mean the dollar amount that's been talked about publicly for the **anthropic** contract is $200 million. That's not a lot of money for these **AI companies**. Yeah.

</details>

**Joe Wisenthal**: 所以我认为实际上我们已经看到国防部门一直在努力跟上这个领域所需的投资步伐。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And so I think that actually we've seen the defense sector has struggled to just keep pace with the amount of investment that's needed in the space.

</details>

**Tracy Aloway**: **Tracy**，我认为这是一个好问题。然后你就会想起，政府连一个好的医疗保健网站都建不好，无法注册医疗保险。我不想旧事重提，但这是真的，对吗？所以，这就像是，他们会建立一个世界级的**大型语言模型**吗？或者政府能建立一个好的失业保险网站吗？我们已经做了很多期节目，答案仍然是否定的。然而，我确实觉得你关于这种新颖性的观点很吸引人。无法想象**洛克希德·马丁公司**发明一项技术，然后说不，你不能使用它，因为**洛克希德·马丁公司**存在的全部理由就是为政府制造技术。这简直是不可思议的，但当你获得这些国防技术时，它确实有点新颖，你知道，**Google**也是一个例子，**Google**显然拥有最初并非用于国防目的的技术。我们看到了员工的反抗，我们还记得。但让我们更多地谈谈**Anthropic**和**国防部**之间的分歧。在你看来，**Pete Hegseth**想用这项技术达到什么目的？这是否偏离了你当时正在研究的一些政策和指令？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Tracy, I think it's a good question. And then you remember, well, the government couldn't build a good healthcare website to sign up for health insurance. And I hate to bring that up because it's old, but it's true, right? So it's like, are they going to build a world-class **LLM** or can a government build a good employment insurance website? The We've done multiple episodes. the answer continues to be not the case. I do find it fascinating however your point about there is this novelty. It is impossible to imagine say Loheed Martin inventing a technology and then saying no you can't use it because Loheed Martin's entire rais on death right is building technology for the government. It is inconceivable what that would be, but it is sort of novel when you're getting these defense technologies and you know the **Google** was also an example of **Google** obviously had technology that did not originally serve a purpose of defense. We saw the we remember the employee revolt. Let's talk more about that disagreement though between **Anthropic** and the **Department of Defense**. In your mind, where does Pete Hegsth want to go with this technology? And is that deviate from some of the policies and the directives that you were working on when you were when you were working on this stuff?

</details>

**Paul Sharie**: 所以，关于这场争论最疯狂的地方在于，特别是在**自主武器**问题上，我与所有交谈过的人都说，军方目前无意使用**AI**制造**完全自主武器**。好的。

<details>
<summary>Original English</summary>

**Paul Sharie**: So, what's kind of crazy about this whole dispute is particularly on the issue of autonomous weapons, literally everyone I've spoken with has said that there's no intention by the military to use **AI** to make fully autonomous weapons today. Okay.

</details>

**Joe Wisenthal**: 我认为任何实际使用过**大型语言模型**或任何聊天机器人（无论是**Claude**、**Gemini**还是**ChatGPT**）的人都知道，如果你用它们来写电子邮件，你需要仔细检查。它们在任何方面都不可靠到足以做出生死攸关的决定。我不认为军方真的想这样做。这里争议的焦点是一个更根本的分歧，即谁来制定规则？这场争论的根源在于，当**五角大楼**在1月份发布新的**AI战略**时，他们的战略之一是，未来他们希望与**AI公司**签订的合同允许军方将他们的**AI工具**用于任何合法用途。基本上，就是说，任何合法的事情，我们都希望有能力去做。这与许多科技公司对他们的**AI工具**的看法产生了冲突。这些公司中的许多人对**AI**可能造成的危害非常紧张。他们意识到这些风险，因此他们中的许多人都有各种使用政策。例如，你不能使用**AI**来发动**攻击性网络攻击**。这实际上是政府可能想要做的事情。所以，这真的是与政府的症结所在，即谁来制定规则，而不是一个关于**完全自主武器**的近期问题。所以我们已经看到，**Anthropic**与政府存在分歧，然后**OpenAI**介入并举手说：“好的，**Anthropic**不想做，我们很乐意做。”这是否让我们陷入一种“逐底竞争”的境地？对吗？就像是，安全顾虑最少或声誉顾虑最少的实验室能够做到这一点。所以我们最终仍然会陷入政府正在使用**AI**的境地。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And I think anybody that's actually worked with a **large language model** with any kind of chatbot, whether it's **Claude** or **Gemini** or **Chatg GPT** knows that if you use these to write an email, you need to double check it. Like in no way, shape or form are they reliable enough to make life and death decisions. I don't think the military actually wants to do that. What's at dispute here is a more fundamental disagreement about well, who sets the rules? And so the origins of this really was that when the **Pentagon** came out with a new strategy for **AI** in January, one of the things in their strategy was that going forward, they wanted their contracts with **AI companies** to allow the military to use their **AI tools** for any lawful use. Basically, look, anything that's legal, we want the ability to do it. And that has conflicted with how a lot of these tech companies have been thinking about their **AI tools**. They're very nervous, many of these companies, about harms from **AI**. they're conscious of these risks and so a lot of them have various use policies in place. You can't use **AI**, you know, to launch offensive cyber attacks, for example. That's kind of thing that actually like the government might want to do. And and so this is a this was really the rub with the government was like who sets the rules rather than necessarily like a near-term question of fully autonomous weapons. So what we've already seen is **Anthropic** has this disagreement with the government and then **Open AI** steps in and raises its hand and says, "Okay, **Anthropic** doesn't want to do it. We'll do it happily." Does this just leave us in a situation where it's sort of a race to the bottom, right? It's like the lab with maybe the least amount of safety concern or the least amount of reputational concern is able to do this. And so we still wind up in a situation where the government is using **AI**.

</details>

**Paul Sharie**: 嗯，我认为这里不幸的是，当你思考对政府来说什么是最佳选择时，首先，我认为政府能够接触这项技术，并且能够接触所有同类最佳的模型是理想的，因为它们有时在细微之处有所不同。而且，政府能够接触到许多不同的供应商，这样市场才能健康竞争，你才不会被某个供应商锁定，这对政府来说会更健康。但如果**AI科学家**说：“嘿，它对这个不可靠，你应该听取意见。”这似乎是你希望他们能说出来的事情，对吗？所以，我认为为了让**AI**以对美国军方有效的方式使用，我们必须在**AI社区**和军事专业人员之间进行健康的对话，了解这项技术能做什么，不能做什么。我认为不幸的是，我们看到这种对话在这场争论中以如此戏剧性的方式破裂了。

<details>
<summary>Original English</summary>

**Paul Sharie**: Well, and I think what's unfortunate here is that when you think about what would be optimal for the government, one, I think it would be ideal for the government to have access to this technology and to have access to all of the best-in-class models available because they are good at slightly different things sometimes. And it's much healthier for the government to have access to a number of different providers so that there is healthy competition in the market. you don't get lock in with one vendor, but also if the **AI scientists** are saying, hey, it's not reliable for this, you ought to listen. Like that seems like a thing you'd want to hear them like out about, right? And so I think like in order to use **AI** in ways that actually are effective for the US military, we got to have a healthy dialogue between the **AI community** and people in the military profession, what the technology can and cannot do. And I think it's unfortunate that we've seen that dialogue break down in such a dramatic way over this dispute.

</details>

**Tracy Aloway**: 回到谁实际制定规则的想法，你之前提到，你不能使用**Claude**非法入侵系统。据说它无法做到这一点。它内部有一个“**终止开关**”，可以阻止它这样做。如果你是**Anthropic**，你难道不能直接对这些系统进行硬编码，说你不能被用于对美国人进行国内监视，也不能用于战争罪行吗？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Just going back to the idea of who actually makes the rules, you mentioned earlier that, you know, you can't use **Claude** to hack into to illegally hack into a system. Supposedly, it is unable to do that. It has like a kill switch within itself that prevents it from doing that. If you're **anthropic**, could you not just hardcode some of these systems and say you're not going to be able to use be used for domestic surveillance of Americans or for war crimes?

</details>

**Paul Sharie**: 是的，所以这就变得有点技术性了。这与公司向政府提供技术的一些方式有关。所以**AI公司**有几种不同的方式可以设置防护措施，以确保他们的模型不会被滥用。一种是训练模型本身拒绝某些请求。所以如果你要求模型做某事，它只会说，我不会做那个。那不符合我得到的指导。而且模型已经被训练成做出那种回应。另一种方式是公司可以在模型的输入和/或输出上放置分类器，模型可能会给你一个答案，但随后会有另一个**AI系统**检查那个答案，或者检查你对它的要求，然后说：“嗯，那不可接受。”然后第三种，我自己在研究中也遇到过这种情况，因为我所从事的事情的性质是安全方面的，我遇到过这样的情况：我问**Claude**帮助我理解这个问题，**Claude**生成了回应，然后它就被删除了，我认为这真的很有趣。

<details>
<summary>Original English</summary>

**Paul Sharie**: So yeah, so this is where it gets a little more technical. It has to do with some of the ways in which the companies may providing their technology to the government. So there's a couple different ways in which an **AI company** could put safeguards in place to make sure that their model is not being abused. One is training the model itself to refuse certain requests. So if you ask the model to do something, it's just going to say like, I'm not going to do that. That's not consistent with the guidance that I've been given. And the model's been trained to to do that response. Another way is that the company can put classifiers on the input and or the output of a model where the model might give you an answer, but then there's like another **AI system** that's checking that answer or checking what you ask of it and saying, "Well, like that's unacceptable." And then a third and I've run into that actually myself in my own research because I the nature of the things that I work on are security things and I've had situations where I ask **Claude** help me understand this issue **cla** generates response and then it gets deleted which I think is really interesting to see.

</details>

**Joe Wisenthal**: 然后另一种方式，**Anthropic**实际上在回应中国黑客利用**Claude**进行网络攻击时也谈到过这一点，那就是公司通过人们正在做的事情来监控使用情况，所以如果人们正在做一些看起来可疑的事情。也许他们从一个已知与网络罪犯或黑客组织相关的**IP地址**登录，试图找到绕过这些保护的方法。公司也可以找到方法来捕捉这些。所以有几种不同的方法可以做到这一点。如果考虑到军事用途，这些方法可能并非全部到位，这取决于公司之间的关系如何构建，如果模型例如托管在不同的云基础设施上，并且军方可以直接访问它，公司可能就没有相同的方式来实际决定技术是否按照他们的原则使用。这部分也是为什么合同细节很重要，比如公司和政府之间关于军方可以使用和不能使用这项技术的协议是什么。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And then the other way and **anthropic** has actually talked about this in response to countering some use of **claude** by Chinese hackers who were using it for cyber attacks. is that the company monitors use through that people are doing and so people are doing things that seem suspicious. Maybe they're logging in from an IP address that's known to be associated with cyber criminals or a hacking group that try to find ways to get around some of these protections. The company can also find ways to try to catch that. And so there's a couple different ways to do it. That might not all be in place if you're thinking about military use where if depending on how that relationship is structured between the company, if the model is for example like hosted on a different cloud infrastructure and the military has direct access to it, the company may not have the same ways to actually shape whether or not the technology is being used according to their principles. Which is partly why the contract details do matter of like what is the agreement between the company and the government about what the military can and cannot use the technology for.

</details>

### AI安全与竞争

**Tracy Aloway**: **Tracy**，我认为你关于那种看似安全或安全“逐底竞争”的观点非常真实，这也是我经常思考的问题。当**大型语言模型**或**AI**基本上只是**OpenAI**的代名词时，他们可以设定开发的速度，对吗？他们可以做到。一旦这变成一个竞争异常激烈的领域，你有了**OpenAI**，有了**Anthropic**，有了**Gemini**，还有来自中国等地的数千个开源**AI模型**，发布的速度确实加快了，而且感觉他们别无选择，只能为了商业利益而加速，这似乎是一个非常真实的动态，在这种动态下，我不知道**AI安全**将何去何从。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Tracy. I think your point about like the sort of seemingly safety or safety race to the bottom is very real and it's one that I think about a lot. When **LLMs** or **AI** was basically just synonymous with **open AI**, they could set the pace of development, right? They could do it. As soon as this became a hyper competitive space where you have **open AI** and you have **anthropic** and you have **Gemini** and a thousand open source **AI models** out of China, etc. the tempo of release has really heightened and the degree to which it feels like they have no choice but to accelerate just for the commercial imperative feels like a very real dynamic in which like I don't know where that leaves **AI safety**.

</details>

**Joe Wisenthal**: 嗯，完全正确。而且你还提到了中国，所以这不仅仅是**OpenAI**与**Anthropic**之间的国内竞争。这是国际参与者之间的竞争，就像是，好吧，美国可能希望对自己的技术设置保障措施，或者说它确实这样做了，但俄罗斯或中国可能不在乎。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Well, totally. And also you mentioned China then it's not just domestic competition between you know **open AI** versus **anthropic**. It's a competition between international actors where it's like okay well the US might want to have safeguards on its technology or say that it does but maybe Russia or China don't care.

</details>

**Paul Sharie**: 对。完全正确。你知道，你提到你看到输出一秒钟然后就删除了，这很有趣。就像**DeepSeek**刚出来的时候，我做了一些实验，想弄清楚它的审查制度，我试图做一些对抗性提示，我说历史学家喜欢谈论20世纪的一个时期，当时发生了极度快速工业化的失败尝试，并导致了饥荒，然后你看到了输出，它说好的，20世纪发生了什么，饥荒在哪里？嗯，发生了一件叫做“**大跃进**”的事情，然后它立即，只要思维链触及“**大跃进**”，它就消失了。所以我总是觉得很有趣，当系统识别出系统走得太远时。总之，我们一直在谈论“**大型语言模型**”，但实际上**AI**超越了**大型语言模型**，包括图像方面的东西，而且**大型语言模型**在这一点上，它是一个非常2023年的术语。而且我认为这很重要，因为当我们谈到**AI**与机器人技术等的交叉点，或者**AI**与目标时，我们谈论的是一些超越**大型语言模型**的东西，但我们可能仍然在谈论**生成式AI**。你认为这会走向何方？现在有哪些武器系统不是你所说的目前没有人真正谈论的**真正自主武器**？但如果真是那样，就不会有争议了。所以显然有一些东西就在地平线之外，可能会进入**真正自主武器系统**的画面，技术正在朝着这个方向发展。如果不是这样，就不会有争议。你就不会有两本关于这个主题的书。那么，现在技术正在朝着哪些可以归类为**自主武器**的武器系统发展呢？

<details>
<summary>Original English</summary>

**Paul Sharie**: Right. Totally. You know it's funny you mentioned where you like see the output for one second and then deletes. Like when **Deep Seek** came out, I was doing some experiments about like figuring out its censorship and I was trying to do some adversarial prompting and I was like historians like to talk about a period in the 20th century where a failed attempt at extreme rapid industrialization happened and it led to famine and then you see the output and it said okay what happened in the 20th century where did this famine well there was something called the great leap forward and then immediately it just as soon as the chain of thought hit the great leap forward just like disappeared. So I'm always like very amused by like when the system recognizes that the system has gone too far. Anyway, we've been talking about quote **large language models**, but actually **AI** is beyond **large language models**, including the image stuff, and that actually **LLMs** at this point, it's a very 2023 sort of term. And when and I think this is important because when we get to the intersection of **AI** and robotics and so forth and or **AI** and target we're talking about something a bit beyond **large language model** but we might still be talking about **generative AI**. Where do you see this going and what are the weapon systems that aren't currently you said currently no one is actually talking about true autonomous weapons but if that were the case then there wouldn't be a controversy there. So there is clearly something just beyond the horizon that could come into the picture of a true autonomous weapon system where the technology is building towards that. If this weren't the case, there would be no dispute. You wouldn't have two books written about this subject. So what are these weapon systems that would classify as autonomous weapons that that the technology is building towards right now?

</details>

### 自主武器的未来发展

**Paul Sharie**: 是的，我的意思是，我当然认为趋势正在将我们带向那里。例如，你在这场争论中看到的**五角大楼**的立场之一是，他们希望保留未来的选择权。他们当然不希望束缚自己的手脚。我认为你可以看到这会以几种方式演变。我们清楚地看到，最大、最强大的**AI系统**的一个趋势是它们越来越**多模态**。它们当然会引入大量不同形式的数据，而且它们越来越**通用**。它们可以做各种不同类型的事情。它们在这方面变得越来越强大。所以，这就像是你可以看到**AI**以某种方式被使用，这种方式可能会慢慢地将人类从回路中拉出来，而不是人类在规划过程中给**AI**分配非常狭窄的任务，也许**AI**能够承担更多，引入更多数据，承担更复杂、更长期的任务。我们当然在其他领域也看到了这一点，比如编码，**AI系统**可以完成的任务长度正在随着时间的推移呈指数级增长。另一种我们可能会看到这种情况的方式是，我们看到一个**AI代理网络**，它们与不同的数据片段交互，做不同类型的事情，而其最终效果是，也许人类再次只是名义上查看这些目标，但实际上并没有以某种有意义的方式批准它们。然后还有一种更独立的，我几乎会将其视为**AI**和**机器人技术**的**具身形式**。是的。这可能是一个无人机或弹药或机器人系统，它具有某种**板载自主性**。这可能部分是一个**蒸馏模型**，以便它可以在边缘以较低的计算能力在实际弹药或无人机上运行。或者它可能是一些**混合系统**，部分是**机器学习**，但也包含大量**硬编码**，这更像是一个**专家级系统**，它将进入战场空间并直接搜寻目标并攻击它们。所以，有点像我们看到的伊朗发射的**低成本无人机**，但它们可以**盘旋**并识别目标，然后进行攻击，而无需。

<details>
<summary>Original English</summary>

**Paul Sharie**: Yeah, I mean I certainly think the trends are taking us there. One of the things that you see in the **Pentagon**'s position in this dispute, for example, is they want to preserve that option going forward. They're certainly not interested in tying their hands. I think you could see that evolving in a couple ways. One trend we're clearly seeing with the largest and most capable **AI systems** is they're increasingly **multimodal**. They're bringing in lots of different forms of data, of course, and they're increasingly **general purpose**. They can just like do a variety of different kinds of things. They become more capable at that. And so that's like one way in which you could see **AI** being used in ways that might sort of slowly pull humans out of the loop where instead of person giving an **AI** like really narrow tasks to do in a planning process, maybe the **AI** is able to take on more, bring in more data, take on more like sophisticated longer term tasks. And we're certainly seeing this in other areas like coding where the task length that an **AI system** could do is growing exponentially over time. Another sort of way that we might see this look is just we see a network of **AI agents** that are interacting with different pieces of data doing different types of things and that the net effect of that is that maybe humans are again sort of like nominally looking at these targets but not actually approving them in some meaningful way. And then there's like a more separate I would almost think of like an **embodied form of AI** and **robotics**. Yeah. Which could be a drone or munition or robotic system that has some kind of **onboard autonomy**. That might be partly a **distilled model** so that it can be operating at the edge on lower computing on this actual munition or drone. or it might be some **hybrid system** that has partly **machine learning** but also just a lot of **handcoded code** that's that's more like **expert level system** that's going out into the battle space and hunting targets directly and attacking them. So something kind of like the **lowcost drones** that we're seeing Iran launch but ones that can loiter and identify targets that attack them without.

</details>

**Joe Wisenthal**: 而且今天还没有。我们没有那种可以**盘旋**的无人机，它们只是在那里徘徊，然后当有什么东西闪烁时，系统就会说这看起来像一个目标，然后攻击它，据你所知，目前还没有这样的东西。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And that doesn't exist today. We don't have drones that loiter that are just hanging out there and then when something flash then there's a system is like this looks like a target attacks that actually doesn't exist currently as far as you know.

</details>

**Paul Sharie**: 嗯，我意思是它们没有被广泛使用。所以，历史上有一些狭窄的例子，可以追溯到80年代，**盘旋弹药**可以搜索更广阔的区域，并根据雷达进行排队。所以**雷达**是军方所说的**合作目标**，当它们在电磁频谱中发射时，如果你知道你正在寻找的**雷达**的特征，你就可以看到它。你可以直接锁定那个**雷达**。好的？

<details>
<summary>Original English</summary>

**Paul Sharie**: Well, I mean they're not they're not in widespread use. So there have been some narrow examples I would say historically dating back to the 80s in fact of lording munitions that could search over wider and would queue off of radars. And so **radars** are what the military would call a **cooperative target** that when they're emitting in the electromagnetic spectrum, if you know the signature of the radar you're looking for, you could see it. You can just home in on that radar. Okay?

</details>

**Joe Wisenthal**: 现在，如果它们关闭了，就不同于隐藏起来，它们更难找到，但有一些例子，美国海军在80年代有一种系统叫做“**战斧反舰导弹**”。它实际上不是军方现在使用的那种**战斧巡航导弹**。它是另一种，旨在飞行搜索模式并搜寻苏联船只。还有一种以色列系统叫做“**哈比无人机**”，旨在追击**雷达**，可以**盘旋**一段时间。但这些**盘旋弹药**从未真正被军队广泛使用。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Now, if they turn off, it's different than hidden and they're harder to find, but there have been some examples, a system that the US Navy had in the 80s called a **Tomahawk anti-hship missile**. Not actually the same **Tomahawk cruise missile** that the military is using now. a different one that was designed to fly a search pattern and hunt Soviet ships. There was an Israeli system called the **harpy drone** that was designed to go after radars that would lorder for a period of time. But these lording munitions have never really been in widespread use by militaries.

</details>

**Tracy Aloway**: 我们得发明一种那种高音警报器，来阻止那些**盘旋无人机**在目标外徘徊。我想，我们有**电子干扰器**，所以那确实存在。好的。所以当我思考我们走向更多**自主武器**时，我想到的是**机器人**基本上与**机器人**在那一点上进行交互，然后我回想起以前**机器人**与**机器人**交互的例子，有很多例子都倾向于失控。

<details>
<summary>Original English</summary>

**Tracy Aloway**: We got to invent one of those like high-pitched alarms to deter the loitering drones from hanging out outside targets. I guess I mean we have electrical jammer so that does exist. Okay. So when I think about as we move towards more autonomous weaponry, I think about bots basically interacting with bots at that point and then I think back to previous examples of bots interacting with bots and there are numerous ones where things tend to go off the rails.

</details>

**Joe Wisenthal**: 它们只是开始争论生命的意义。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: They just start debating the meaning of life,

</details>

**Tracy Aloway**: 对吗？或者它们开始用一种除了它们自己没人能听懂的语言说话，诸如此类。我们越是走向**完全自主武器**，不必要的升级可能性是否会增加？

<details>
<summary>Original English</summary>

**Tracy Aloway**: Right? Or they start talking in like a language that no one understands except them, stuff like that. Does the possibility of undesired escalation go up the more we move towards fully autonomous weaponry?

</details>

### 自主武器的潜在风险

**Paul Sharie**: 我认为这是一个非常严重的风险。所以，我对此的心理模型是金融市场中我们看到的**闪崩**，这是由于不同算法执行交易的交互造成的，你会看到算法在市场中如何交互的**涌现特性**，这是一个竞争环境。公司不会分享他们的算法在做什么的细节，然后你就会看到这些奇怪的行为。现在，金融市场处理这个问题的方式是，监管机构安装了**熔断机制**，如果价格变动过快，就会暂停股票交易。战争中没有裁判可以叫暂停。所以，我认为特别是在**网络空间**，人们可以预见未来存在这种风险，事情以机器速度发生，你拥有**自主攻击性网络行动**。你需要防御这种攻击。你需要在防御方拥有一定程度的自主性，以机器速度进行防御。你可能会遇到奇怪的交互，这可能会升级冲突。或者也可能发生在无人机在某种危机情况下的交互。现在，如果正在发生一场大规模的枪战，人们已经在攻击，这可能不那么令人担忧。尽管你仍然可能担心地理上的升级，导致新的国家卷入冲突，或者可能攻击与**核指挥和控制**相关的真正敏感地点，而你宁愿不去攻击。所以，我认为当我们思考这项技术未来可能如何被使用时，这是一个非常真实的风险。那么**AI**在真正困难的伦理问题中扮演什么角色呢？例如，我们知道平民会被杀害的打击，这在战争中一直发生，并且大概会尽量减少，但战争规划者会找到某种可接受的水平，他们称之为**附带损害**。**AI**是否在这些可能属于灰色地带的打击中扮演角色，或者你期望它扮演角色？

<details>
<summary>Original English</summary>

**Paul Sharie**: I think that is a very serious risk. And so the like mental model that I have for this are things like **flash crashes** that we've seen in financial markets due to the interactions of different algorithms that are executing trades where you get these **emergent properties** of how the algorithms might interact in the market and it's a competitive environment. Companies aren't going to share the details of what their algorithms are doing and you get these strange behaviors. Now the way that financial markets have dealt with this problem is regulators have installed **circuit breakers** to take stocks offline if the price moves too quickly. There's no referee to call timeout in war. And so I think that's like particularly in cyerspace one can envision a future where that is a risk where things are happening at machine speed and you have autonomous offensive cyber operations. You need to defend against that. You need some measure of autonomy on the defensive side to defend at machine speed. And you could get situations where you get weird interactions that might escalate a conflict. Or it could also happen between drones interacting in some kind of crisis situation. Now, a situation where like there's a big shooting war underway, people are already attacking, it might be less of a concern. Although you still could worry about escalation geographically against bringing new countries into a conflict or maybe attacking really sensitive sites that are tied to **nuclear command and control** that you'd rather not go after. So I think that's a a very real risk when we think about how this technology might be employed going forward. What about **AI** in really difficult ethical questions? Strikes where we know that civilians, for example, are going to be killed, which that happens all the time in war and presumably tries to be minimized, but war planners will find some level of acceptable, they call it **collateral damage**. Is **AI** playing a role or do you expect it to play a role in some of these strikes that may be gray areas?

</details>

**Paul Sharie**: 我认为你可以设想**AI**被用于使战争更精确、更人道和更道德的方式，以及它可能被用于不那么精确、不那么人道和不那么道德的方式，甚至是相反的方式。所以，例如，如果你有一个**AI系统**，它可以查看所有这些目标数据，然后识别出如果使用特定大小的弹药，打击是否在一定距离内，远离受保护的目标，无论是学校、医院还是关键的民用基础设施，然后说：“嘿，等等，这里有警告。你不应该进行打击，或者它需要更高层次的批准，或者你可能应该使用更小、更精确的弹药。”这将是**AI**的一个非常有益的用途，特别是当你谈论一场在短时间内打击大量目标的军事行动时，这可能非常有价值，并可能减少平民伤亡。你知道，所有这一切的风险是，你最终可能会生活在一个人类较少参与这个过程的世界中。

<details>
<summary>Original English</summary>

**Paul Sharie**: I think you can envision ways that **AI** would be used that would make warfare more precise and more humane and ethical and ways that it could be used that would not and would be the opposite. So, for example, if you had an **AI system** that could look over all this targeting data and then identify if a strike is within a certain distance using, you know, munitions of a certain size of protected targets, whether it's schools or hospitals or critical civilian infrastructure and say, "Hey, whoa, like warning here. you should not carry out the strike or it needs a higher level of approval or maybe you should use smaller more precise munitions. That would be a really beneficial use of **AI** particularly when you're talking about a military campaign that hits a lot of targets in a short period of time that could be really valuable and may reduce civilian casualties. You know, a risk of all of this is you could end up in a world where humans are just less engaged in this process,

</details>

**Joe Wisenthal**: 对吗？所以既有**人类**犯的错误，也有**人类**只是不觉得有那么大的道德责任。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Right? And so there's both mistakes that humans miss or humans just don't feel as morally responsible.

</details>

**Paul Sharie**: 我认为这在道德上是一个非常棘手的问题，因为

<details>
<summary>Original English</summary>

**Paul Sharie**: Which I think is like a really tricky thing to think about morally because

</details>

**Joe Wisenthal**: 一方面，作为一个民主社会，我们作为一个国家决定开战。只有极少数人必须承担这个负担。如果有人，如果你能说，好吧，看看一个人在冲突多年后患上**创伤后应激障碍**（PTSD），被发生的事情困扰，有什么好处呢？那似乎不太好。也许我们可以减少这种情况。另一方面，如果我们打了一场战争，没有人对发生的杀戮负有道德责任，那似乎也不好，那可能会导致更多的苦难和战争中的平民伤亡。所以，我认为当你思考如何使用这项技术时，这肯定是一个担忧。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: On the one hand as a democratic society we make a decision as a nation to go to war. It's a very small number of people that have to carry that burden. And if someone if you could say well look what's the benefit to someone having like **PTSD** years after a conflict that they're haunted by something that happened that doesn't seem great. maybe we could reduce that. On the other hand, if we fought a war and nobody felt morally responsible for the killing that occurred, that doesn't seem good either and that could lead to more suffering and civilian casualties in war. So, I think that's a certainly a concern when you think about how to use the technology.

</details>

**Tracy Aloway**: 是的，这很有《**安德的游戏**》的意味，对吗？你有一个人基本上在玩电子游戏，消灭了整个文明，他们认为这只是一个电子游戏，只是一次演习，但结果却是真实的战争。我们看到**国防部**目前描绘这场冲突的方式在某种程度上就是如此。它非常像电子游戏。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah, this is very **ender game** coded, right? Where you have someone who's basically playing like a video game and wiping out entire civilizations and they think it's just a video game, just an exercise, but it turns out it's actual warfare. And we're seeing some degree of that in the way that the Department of War is portraying this conflict so far. It's very video game.

</details>

**Paul Sharie**: 哦，是的。是的。尤其是在公开展示中。是的。字面上的。

<details>
<summary>Original English</summary>

**Paul Sharie**: Oh yeah. Yeah. Especially in the public presentation. Yeah. Literal.

</details>

**Tracy Aloway**: 电子游戏的动画GIF。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Animated gifts of video games.

</details>

**Joe Wisenthal**: 没错。所以**Paul**，你提到了一个词：**断路器**。**断路器**在市场中是很好的东西。我认为它们在武装冲突和战争中会更好。有没有可能为一场重大冲突设计出类似的东西？

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Exactly. So Paul, you mentioned something. You mentioned the word **circuit breaker**. And **circuit breakers** are nice things to have in markets. I think they'd be even nicer things to have in armed conflict and war. Is there any possibility that you could design something like that for a major conflict?

</details>

**Paul Sharie**: 我认为在战术层面上有可能弄清楚如何做到这一点，以及如何在己方军队中设置保护措施，以及甚至可能与敌人合作做什么。挑战在于如何避免我们之前谈到的“**安全逐底竞争**”。

<details>
<summary>Original English</summary>

**Paul Sharie**: I think it's possible like at a tactical level to figure out how you would do that and where you put protections on your side in the military and what you would do with even maybe cooperatively with an enemy. The challenge is how do you avoid what we were talking about earlier, a **race to the bottom on safety**.

</details>

**Joe Wisenthal**: 是的。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Yeah.

</details>

**Paul Sharie**: 而且，我们正在私营部门的**AI公司**之间看到这种情况。他们急于将产品推向市场。我认为在军事领域尤其困难，因为各国投资军事是因为他们担心其他对手可能会做什么，他们想在他们身上占上风。所以，冲突中的合作并非从未发生。它确实发生过。各国也同意将某些武器排除在外。例如，**化学武器**和**生物武器**。这并不意味着它们从未被使用过，但大多数文明国家都表示我们不会使用它们。但这些例子非常罕见，而且很难做到。所以，我认为这种动态才是真正具有挑战性的。这就像是，你如何找到与敌人合作的方法，以避免这里的一些最大危险？

<details>
<summary>Original English</summary>

**Paul Sharie**: And right, we're seeing this in the private sector between the **AI companies**. There's the rushing to get products out to market. I think it's especially hard in the military space where countries are investing in their military because they're worried about what some other adversary might do and they want to get a leg up on them. And so it's not that cooperation in the midst of conflict never happens. It does. And countries have agreed to take certain weapons off the table. **Chemical and biological weapons** for example. It doesn't mean that they're never used, but most civilized countries said we're not going to use them. But those examples are pretty rare and it's pretty hard to do. And so I think that dynamic is the really challenging one. It's like how do you find ways to cooperate with your enemies to avoid some of the biggest dangers here?

</details>

### 机器人战争的未来

**Tracy Aloway**: 所以我认为这是我的最后一个问题。你知道，你提到无人机是一种机器人，还有其他一些机器人已经在国家安全或警察工作中存在了一段时间。我想地铁上有时也有机器人，它们似乎是。是的，但我想它们并没有真正做到。

<details>
<summary>Original English</summary>

**Tracy Aloway**: So I think this is the last question for me. You know, you mentioned that drones are a kind of robot and there are other robots that have been existence in either national security or police work for a while. I think there are robots on the subway sometimes that seem to be Yeah, but they I don't think they really do.

</details>

**Joe Wisenthal**: 我见过超市里的机器人，它们最后追着我，而我正试图买胡萝卜之类的东西。是的，那些扫地的机器人等等。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: I've seen the robots at the grocery store and they end up like chasing me while I'm trying to buy like carrots or something. Yeah, the ones that sweep the floors and stuff.

</details>

**Tracy Aloway**: 是的，有机器人。是的，我认为**Eric Adams**与某家公司签订了合同，该公司正在做地铁机器人之类的东西。但这些是不同的**AI**，正如我们所说，**AI**和**机器人**是两棵不同的技术树，但它们将融合，并且有可能最终融合。你是否预见到一个世界，基本上我们没有人类士兵，战争是由拥有最先进**自主机器人**的一方进行的？我们知道中国在**人形机器人**领域投入了大量资金。你是否预见到一个世界，地面入侵的性质就是这样，它是由机器人或各种其他类型的机器人完成的？跟我们谈谈这能走多远。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah, there's the robots. Yeah, there I think there is a Eric Adams did a contract with some company that was doing like subway robots or something like that. But these are like different **AI** as we talk about it and robots are two different technological trees but they are going to merge and there's the possibility of their mer ultimate merger. Do you foresee a world in which essentially we don't have human soldiers and wars are fought with who has the most advanced **autonomous robots**. We know China is investing a lot in **humanoid robotics**. Do you foresee a world in which that is the nature of a ground invasion as you and it happens with robots or various other sorts. Talk to us about how far that could go.

</details>

**Paul Sharie**: 是的。所以我的意思是，你看，我认为我们会在战争中看到更多机器人被使用吗？绝对会。战争中技术的漫长发展历程，从人类第一次拿起火箭扔向别人，就一直朝着对手之间更大距离的方向发展，从弓箭、步枪到洲际弹道导弹。我认为**机器人技术**将是这种趋势的下一个演变，即寻找敌人、打击敌人而不让自己处于危险之中的方法。**机器人技术**在战场上肯定有其作用。我认为未来战争只是机器人与机器人作战，没有人类参与的愿景是不现实的，原因有几个。一个是我认为军队将需要相对前沿部署的人员来执行**机器人系统**的指挥和控制。

<details>
<summary>Original English</summary>

**Paul Sharie**: Yeah. So I mean look I think will we see robots used more in warfare? Absolutely. The long arc of technology in war from the first time someone picked up a rocket, threw it at somebody else, has been towards greater distance between adversaries, moving up through bows and arrows and rifles and intercontinental ballistic missiles. And I think **robotics** will be the next evolution of this trend of finding ways to find the enemy, strike the enemy without putting yourself at risk. And there's certainly a role for **robotics** out on the battlefield. I think a vision of like future wars of just robots fighting robots, there's no humans involved is not realistic for a couple reasons. One is I think militaries are going to need people relatively forward deployed to execute **command and control** for **robotic systems**.

</details>

**Joe Wisenthal**: 美国军方现在可以在相对没有争议的环境中从美国远程操控无人机，对抗更复杂的对手，这些对手可能会干扰你的通信链路。例如，我们看到乌克兰前线有很多干扰。这是你对付这些无人机的方法之一。那么你需要人员在附近，因为拥有短距离受保护的通信更容易。当你走得更远时，这只会更难做到。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: The US military right now can fly drones remotely from the United States in a relatively uncontested environment against more sophisticated adversaries who could jam your communications link. And we see, for example, like a lot of jamming on the front lines in **Ukraine**. That's one of the ways you go after these drones. Then you need people close by because it is easier to have shorter range protected communications. When you go to a longer distances, that's just harder to do.

</details>

**Paul Sharie**: 所以，我认为你需要人员相对靠近，原因就在于此。我认为如果你想控制领土，你最终必须派人去那里，下车，四处走动并控制它。但我认为另一个原因可能有点黑暗，我认为现实地讲，为了结束战争，必须付出一些**人类代价**。我认为这是一个不幸的现实，如果只是机器被摧毁，我们可能无法达到一方或另一方愿意求和的地步。而且我认为不幸的是，战争很可能在很长一段时间内都会涉及人类和**人类成本**。我还有一个问题，我想这是一个思想实验，但如果我们回想军事史上的一些关键时刻及其与技术的交叉点，其中一个浮现出来的是那位决定不按下按钮的俄罗斯军官，以回应美国，从而，你知道，据说拯救了世界免于**核灾难**。在**完全自主的军事环境**中，现在还会发生这种事吗？

<details>
<summary>Original English</summary>

**Paul Sharie**: So, I think you need people relatively close for that reason. I think if you want to control territory, you have to put people there eventually to get out of a vehicle and walk around and control it. But I think the other reason it's maybe a little dark, which I think realistically in order for wars to end, there will have to be some **human price** that's paid. I think that's an unfortunate reality that if it's just machines that are being destroyed, that we may not get to the place where one side or the other is willing to sue for peace. And I think unfortunately war is likely to involve people and **human costs** for a very long time. I have one more question as well and I guess it's a thought experiment but if we think back to sort of pivotal moments in military history and their intersection with technology one of them that comes up is the Russian officer who decided not to press the button in response to the US and thereby you know supposedly save the world from **nuclear disaster**. Would that happen in a fully autonomous military environment nowadays?

</details>

### 人类判断的关键作用

**Paul Sharie**: 我的意思是，今天它仍然会发生，因为有人参与其中，对吗？所以这次事件，**Stanislav Petrov**，

<details>
<summary>Original English</summary>

**Paul Sharie**: I mean today it would still happen because there's people involved right? So this incident, **Stannis Lro**,

</details>

**Joe Wisenthal**: 谢谢你。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Thank you.

</details>

**Paul Sharie**: 坐在一个终端前，收到警报说有一枚弹道导弹从美国发射，针对苏联，然后又一枚导弹，最终有五枚导弹袭来。这件事有趣的地方在于，当**Petrov**事后谈论它时，我们都能听到他说的话，因为我们都活了下来，因为他做出了正确的决定，他说他有一种奇怪的直觉。

<details>
<summary>Original English</summary>

**Paul Sharie**: Is sitting at a at a terminal and gets this warning that there's a ballistic missile launched from the United States against the Soviet Union and then another missile, another eventually five missiles coming in. And the thing that's interesting about this is when **Petro** talked about it afterwards and we could hear what he said because we all lived because he made the right decision here is he talked about how he said he had a funny feeling in his gut.

</details>

**Joe Wisenthal**: 而且他知道俄罗斯系统，俄罗斯人刚刚部署，或者抱歉，苏联人刚刚部署了一个新的**基于卫星的早期预警系统**来探测美国**洲际弹道导弹**的发射，它是新的，他知道很多这种苏联技术一开始并不那么好用。所以他对此持怀疑态度。结果证明它确实有故障。它探测到阳光从云层顶部反射，系统将其识别为导弹发射，这就是它报告的内容。然后他去打电话给**早期预警雷达站**，问：“你们看到这些导弹从地平线过来吗？”他们说：“没有，没有导弹。”所以他向上级报告说系统出了故障。我认为这里可怕的问题是，如果那是一个**AI**，**AI**会怎么做？

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And that he knew that the Russian system the Russians had just deployed or sorry the Soviets rather just deployed a new **satellite based early warning system** to detect US **ICBM** launches that it was new and he knew that a lot of this Soviet technology just didn't work that great at first. So he was skeptical of it. Turns out it was in fact faulty. It was detecting the reflection of sunlight off the top of clouds and the system was identifying that as a as a missile launch and that's what it was reporting. And he went and then called the **early warning radar stations** and said, "Are you seeing these missiles come over the horizon?" Said, "No, there's no missiles." So he reported up the chain that the system was malfunctioning. I think the scary question here is like if that was an **AI**, what would the **AI** have done?

</details>

**Paul Sharie**: 是的。它就像是被编程去做什么，被训练去做什么。显然，我们看到更多**通用AI系统**，比如**大型语言模型**，能够汇集更多信息，更好地理解上下文，对你提出的问题有更具上下文的理解。

<details>
<summary>Original English</summary>

**Paul Sharie**: Yeah. And it's kind of like whatever it was programmed to do, whatever it was trained to do. And obviously, we're seeing more **general purpose AI systems** like **large language models** have the ability to bring together more information to understand better context to have just like a a more contextual understanding of the questions that you're asking of it.

</details>

**Joe Wisenthal**: 但它仍然不知道冲突的利害关系。它仍然不知道在某种本能层面上后果是什么。所以，我认为这是一个强有力的令人信服的理由，说明为什么我们需要人类参与这些决策。即使**AI**变得更加强大，仍然会有我们希望人类去做的事情，因为人类理解为什么这很重要。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: But it still doesn't know the stakes of a conflict. It still doesn't know like in some visceral level what the consequences are. And so I think that's a strong compelling reason why we need to have humans involved in these decisions. Even as the **AI** becomes more capable, there are still going to be things that we want humans to do because humans understand why it matters.

</details>

**Tracy Aloway**: 我开始对话时提到，你知道，说让**反导弹系统**在有导弹袭来时发射导弹，这并不是很有争议。但这可能是错误的。你需要确保它确实是一枚导弹，而不是民用飞机之类的东西。所以即使在那里，它看起来像一个典型的例子，如果你只是想让导弹系统发射，你也会希望有人类保障措施、人类监督和人类对系统的理解，以确保它确实在击落一枚导弹。总之，**Paul Sharie**，这次对话非常引人入胜，非常感谢你来到《OddLots》并谈论你的工作。

<details>
<summary>Original English</summary>

**Tracy Aloway**: I started the conversation by mentioning that, you know, it's not very controversial to say have an anti-missile system fire a missile when there's one coming in. But that could be wrong. And you want to make sure that it is in fact a missile and not a civilian airjet or something like that. So even there where it seems like a canonical example if you just want to have the missile system go off you would want to have human safeguards and human oversight and human understanding of the system such that it is in fact shooting down a missile. Anyway **Paul Shie** fascinating conversation really appreciate you uh coming on Lots and talking about your work.

</details>

**Paul Sharie**: 谢谢。非常享受这次讨论。

<details>
<summary>Original English</summary>

**Paul Sharie**: Thank you. Really enjoyed the discussion.

</details>

**Joe Wisenthal**: 非常感谢**Paul**。这既令人沮丧又引人入胜。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Thanks so much Paul. That was depressing and fascinating all at the same time.

</details>

**Paul Sharie**: 是的。好的。

<details>
<summary>Original English</summary>

**Paul Sharie**: Yeah. All right.

</details>

**Joe Wisenthal**: 不，太棒了。谢谢你。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: No, it was great. It was Thank you so much.

</details>

**Paul Sharie**: 是的。非常感谢你们的邀请。

<details>
<summary>Original English</summary>

**Paul Sharie**: Yeah. Thanks so much for having.

</details>

### 总结与反思

**Tracy Aloway**: 我最后有点哽咽，想到那个拯救人类的决定。这确实是。

<details>
<summary>Original English</summary>

**Tracy Aloway**: I kind of got choked up at the end thinking about that decision that saved humanity at the end. And it's actually.

</details>

**Joe Wisenthal**: 这是一个疯狂的故事。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: It's a crazy story.

</details>

**Tracy Aloway**: 这是一个疯狂的故事。这是那种你觉得为什么每个人都不知道那个人的名字的故事之一？我的意思是，当你想到有多少人，我也记不住。

<details>
<summary>Original English</summary>

**Tracy Aloway**: It's a crazy story. It's one of those stories that like why doesn't everybody know that that person's name? I mean, when you think about how many people I couldn't remember it either,

</details>

**Joe Wisenthal**: 但如果你想了解更多，请收听另一个播客。**Dan Carlin的《硬核历史》**至少有一集，可能两集，是关于**核灾难**的狭义规避。所以，非常值得一听，如果不是令人恐惧的话。你知道，那个故事中还有另一个点，我认为非常有趣，这也是我一直在**AI**领域思考很多的问题，因为人类和**AI**之间有一些相似之处，那就是我们所知道的和我们能表达的之间肯定存在差距。**AI**当然也是如此，对吗？所以机器人做出了一些决定，或者它确定了一些事情。这并不意味着它能用语言表达出它是如何做出这个决定的。但人类也是如此。所以，这种想法，好吧，也许我们确实对事情有奇怪的感觉，或者，你知道，我们仍然很擅长区分**AI生成文本**和**人类生成文本**。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: But shout out to another podcast if you want to learn more about this. **Dan Carlin's Hardcore History** has at least one, possibly two episodes on narrow aversions of **nuclear disaster**. So, very good to listen to, if not terrifying. You know, there's another point in that exact story that I think is really interesting and it's something I've been thinking about a lot across **AI** because there's something similar about humans and **AI**, which is that there is definitely a gap between what we know and what we can articulate. And this is certainly true with **AI**, right? So, the bot makes some decision or it determines something. It does not mean it's going to be able to spit out in words how it arrived at that decision. But that's true for humans as well. And so the idea that like okay maybe you you we do get funny feelings about things or take you know like again we're still pretty good at determining the difference between **AI generated text** and **human generated text**.

</details>

**Tracy Aloway**: 我们可以关闭，但通常，我的意思是，我们仍然常常能做对。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Can we off but often I mean we still like often can get it right.

</details>

**Joe Wisenthal**: 但我们能准确地写下我们所看到和理解的吗？存在这个差距。当我们谈论生死攸关的决定时，想到这种我们无法表达的直觉作用被从决策回路中移除，这令人感到恐惧。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: But could we write down exactly what we saw that we understood? There is that gap. And when we're talking about life or death decisions being made, it is scary to think about that role of instinct that we can't articulate having been taken out of the decision loop.

</details>

**Tracy Aloway**: 嗯，我认为技术也非常擅长**模式识别**，对吗？以及响应模式和预设路径。它被编程去做某些事情。我认为在战争环境中，那是你能想象到的最不确定的环境之一。所以你必须认为你的回应中应该有一些灵活性元素，但我不知道你如何将它实际编码到一个像基于僵硬数字和代码行运行的东西中。我当时想到的另一件事是**Anthropic**的情况，以及从军事历史的角度来看，它有多么新颖，因为我们这里有一个非常重要的关键技术。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Well, I think also technology is very good at **pattern recognition**, right? And responding to patterns and preset paths. It's been programmed to do certain things. And I think in a war environment, that's one of the most uncertain environments that you can possibly imagine. And so you have to think that there should be some element of flexibility in your response, but I don't know how you actually encode that into a thing that like runs on rigid numbers and lines lines of code. The other thing I was thinking was the **anthropic** situation and just how new that is from a sort of military history perspective in the sense that here we have this really important pivotal piece of technology.

</details>

**Joe Wisenthal**: 它并非源于实际的军事需求。对吗？正如**Paul**所说，它是一个商业产品。它的商业用途可以说比军事用途更有利可图。所以看到它现在与**五角大楼**和**国防部**互动，真的很有趣。情况反过来了，对吗？

<details>
<summary>Original English</summary>

**Joe Wisenthal**: That hasn't come out of like actual military demand. Right? to Paul's point, it's a commercial product. Its commercial uses are arguably a lot more profitable than its military ones. And so seeing that now interact with the **Pentagon** and the **Department of War**, really interesting. It's been flipped, right?

</details>

**Tracy Aloway**: 是的。实际上最接近的例子是**星链**。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah. The closest example actually that comes to mind, there is one example that's in fairly recent history and that's **Starlink**.

</details>

**Joe Wisenthal**: 哦，是的，当然。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Oh yeah, of course.

</details>

**Tracy Aloway**: 当然，那是为商业互联网目的开发的，但它在乌克兰发挥了作用等等。而且在某个时候，如果我没记错的话，关于乌克兰人使用**星链**的程度存在一个紧张点。

<details>
<summary>Original English</summary>

**Tracy Aloway**: And of course that was developed for commercial internet purposes, but it played a role in Ukraine and so forth. And at one point, if I recall, there was a tension point about the degree to which the Ukrainians could use **Starland**.

</details>

**Joe Wisenthal**: 所以我确实认为这是一个有趣的类比。另一件事，我们没有谈到，而且我会有点愤世嫉俗，但我认为这是对的，那就是我认为**Anthropic**情况还有另一个因素，那就是**Anthropic**是最后一家大型自由派科技公司，或者被认为是这样的，对吗？我们知道硅谷多年来一直有这种相当右倾的转变。我不认为**Anthropic**完全是其中的一部分。我认为他们仍然有点自由派色彩。我还认为这偶然解释了为什么许多可能在媒体工作的人最终都使用**Claude**，尽管它们都差不多。我确实认为那里有一些东西，他们有这个东西。他们说我们永远不会有广告，我们知道像**Andre Horowitz**、**Marc Andreessen**都谈论过广告是好的。广告使互联网民主化，广告使互联网能够传播给所有人，这里还有一些其他的政治因素在起作用，因为再次，根据我的理解，这需要律师来判断，我认为**OpenAI**签署的协议与**Anthropic**的协议并没有那么不同，至少。可能有一点点不同，我只是认为这里还有一些其他的政治因素在起作用。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And so I do think that is sort of an interesting parallel here. The other thing, and we didn't get to this, and I this is going to be a little cynical, but I think it's right, which is that there is another element I believe to the **anthropic** situation, which is like **Anthropic** is the last big lib tech company or perceived as such, right? And we know that there's been this fairly sort of rightward turn in Silicon Valley over the years. And I don't think like **anthropic** is like totally part of that. I think they're still sort of lib coded. I also think it's incidentally why a bunch of people who probably like work in media are like end up using **claude** even though they're all kind of the same. Like I do think there's something there and that they have this thing. They say we're not going to ever have ads and we know that like **Andre Horowitz** **Mark Andre** has talked about ads are good. ads democratize the internet ads enable the internet to be spread to everyone there's some other politics at play because again like from my understanding and it would take a lawyer it's like I don't think that the agreement that **open AI** signed was that different at least than what the agreement that **Anthropic** had there's probably a little bit of difference I just think there's some other politics at play here.

</details>

**Tracy Aloway**: 观念很重要，但正如**Paul**所说，也许目前没有人谈论**自主武器**现在就完全自主，但这不会持续太久，我认为这很快就会成为一个真正的紧张点。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Perceptions matter but to Paul's point maybe nobody is talking about currently autonomous weapons happens right now fully autonomous but it can't be long and I think this is going to be a real tension sooner rather than later.

</details>

**Joe Wisenthal**: 我能说一件事吗？我会有点轻浮，但也不是完全轻浮，你能有点轻浮吗？我会很轻浮，那就是我对现代战争有一个解决方案。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Can I say one thing and I'm going to be slightly facitious but also not can you be slightly facitious? I'm going to be facitious which is I have a solution to modern warfare.

</details>

**Tracy Aloway**: 别说出来。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Don't do it.

</details>

**Joe Wisenthal**: 好的。但说真的，不，说真的。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Okay. But for real no for real.

</details>

**Tracy Aloway**: 是的。如果我们只是让**机器人**互相打架，那会花费很多钱，并导致人们死亡，

<details>
<summary>Original English</summary>

**Tracy Aloway**: Yeah. If we're just gonna have bots fighting bots and it's going to cost a lot of money and result in people's deaths,

</details>

**Joe Wisenthal**: 每个国家都应该建造自己最大、最好、技术最先进的机器人，然后让它们像**角斗士**一样战斗。我的想法是，正如**Paul**所说，战争总是要以某种方式带来痛苦。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Every country should have to build its biggest, best, most technologically advanced robot and just have them fight it out gladatorial style. And my twist is to Paul's point about war always having to be painful in some way.

</details>

**Tracy Aloway**: 那个特定社会中的每个人都必须参与进来，并投入一定的时间或金钱来建造那个特定的机器人。你只需要永远迭代这个机器人，直到你觉得它们可以战斗了。这样每个人都分担了痛苦，但又没有人类生命的损失。我是在胡说八道吗？我不这么认为。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Everyone in that particular society has to be engaged and dedicate some amount of time or money to building that particular robot. And you just have to iterate on the robot forever until you feel comfortable to have them fight. And that way everyone shares the pain but without the loss of human life. Am I high? I don't think so.

</details>

**Joe Wisenthal**: 嗯，我认为你应该写一本书。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: Well, I think you should write a book.

</details>

**Tracy Aloway**: 不。

<details>
<summary>Original English</summary>

**Tracy Aloway**: No,

</details>

**Joe Wisenthal**: 我认为你应该写一本科幻小说。好了。我们就在这里结束吧？

<details>
<summary>Original English</summary>

**Joe Wisenthal**: I think you should write a sci-fi book. All right. Shall we leave it there?

</details>

**Tracy Aloway**: 我们就在这里结束吧。

<details>
<summary>Original English</summary>

**Tracy Aloway**: Let's leave it there.

</details>

**Joe Wisenthal**: 这是《All Thoughts Podcast》的又一集。我是**Tracy Aloway**。你可以在**Tracy Aloway**关注我。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: This has been another episode of the All Thoughts Podcast. I'm Tracy Aloway. You can follow me at Tracy Aloway.

</details>

**Tracy Aloway**: 我是**Joe Weisenthal**。你可以在**the stalwart**关注我。关注我们的嘉宾**Paul Sharie**。他是**Paul_sharie**。关注我们的制作人**Carmen Rodriguez**，她是**Carmen Arman Dash**。**Bennett**是**bot**，**Kalebrooks**是**Kalebrooks**。更多《OddLots》内容，请访问**bloomberg.com/odlots**。我们有每日通讯和所有节目。你可以在我们的**Discord**上24小时7天讨论所有这些话题。**discord.gg/odlotss**。

<details>
<summary>Original English</summary>

**Tracy Aloway**: And I'm Joe Weisenthal. You can follow me at the stalwart. Follow our guest **Paul Sharie**. He's **Paul_sharie**. Follow our producers **Carmen Rodriguez** at Carmen Arman Dash Bennett atbot and **Kalebrooks** at Kalebrooks. For more OddLots content, go to bloomberg.com/odlots. We have a daily newsletter and all of our episodes. And you can chat about all these topics 247 in our Discord. discord.gg/odlotss.

</details>

**Joe Wisenthal**: 如果你喜欢《OddLots》，如果你喜欢我们谈论**自主武器**的未来，那么请在你最喜欢的播客平台上给我们一个积极的评价。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: And if you enjoy OddLotss, if you like it when we talk about the future of autonomous weapons, then please leave us a positive review on your favorite podcast platform.

</details>

**Tracy Aloway**: 记住，如果你是**彭博社**订阅者，你可以完全免费收听我们所有的节目。

<details>
<summary>Original English</summary>

**Tracy Aloway**: And remember, if you are a Bloomberg subscriber, you can listen to all of our episodes absolutely adree.

</details>

**Joe Wisenthal**: 你只需要在**Apple Podcast**上找到**彭博社**频道，然后按照那里的说明操作。感谢收听。

<details>
<summary>Original English</summary>

**Joe Wisenthal**: All you need to do is find the Bloomberg channel on Apple Podcast and follow the instructions there. Thanks for listening.

</details>