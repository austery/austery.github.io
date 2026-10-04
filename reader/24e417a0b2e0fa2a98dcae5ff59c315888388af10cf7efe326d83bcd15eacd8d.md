---
author: Bloomberg Podcasts
date: '2026-03-12'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=rEEGzt01wts
speaker: Bloomberg Podcasts
tags:
  - cyber-warfare
  - ai-agents
  - software-economics
  - data-security
  - prompt-engineering
title: AI时代的网络战：传奇黑客Matt Suiche谈网络安全与数据价值
summary: 本期Odd Lots播客邀请传奇黑客兼DB创始人**Matt Suiche**，深入探讨AI时代网络战的演变。他分析了AI对网络安全、软件开发成本和政府网络能力建设的深远影响。Matt指出，AI代理的自主性带来了新的安全挑战，软件开发成本正趋近于零，而高质量数据将成为AI经济中唯一持久的资产。访谈还涵盖了AI在漏洞发现、代码生成中的应用，以及数据隐私和信息战中AI生成内容（“AI糟粕”）带来的挑战。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
  - Amazon
  - DB
products_models:
  - Claude
  - ChatGPT
media_books: []
status: evergreen
---
### AI与网络战的交汇点

**Tracy Alloway**: 大家好，欢迎收听**Odd Thoughts**播客的又一期节目。我是**Tracy Alloway**。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Hello and welcome to another episode of the **Odd Thoughts** podcast. I'm **Tracy Alloway**.

</details>

**Joe Weisenthal**: 我是**Joe Weisenthal**。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: and I'm **Joe Wisenthal**.

</details>

**Tracy Alloway**: Joe，你知道我有点“末日准备者”的倾向。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Joe, you know I have some uh prepper tendencies. Yeah, this

</details>

**Joe Weisenthal**: 有点“末日准备者”倾向。接近“末日准备者”。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: slightly prepper tendencies. Prepper adjacent.

</details>

**Tracy Alloway**: 我知道你也是，因为我的计划是，当一切都变糟的时候，我会带着我的家人去你家。所以，我实际上是依靠你的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: I know you do because my plan for when everything when everything goes bad is to bring my family over to your place. So, I'm relying on you actually.

</details>

**Joe Weisenthal**: 没问题。我其实也想到了，而且一直在额外储备物资。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: That's fine. I actually figured that and I've been building an extra store of supplies.

</details>

**Tracy Alloway**: 我会给你发一份我孩子喜欢吃的食物清单之类的，这样我们就能……

<details>
<summary>Original English</summary>

**Tracy Alloway**: I'm going to like send you a whole list of things my kids like to eat and stuff like that just so that we're

</details>

**Joe Weisenthal**: 这样我们就都准备好了。是的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: just so we're all ready. Yeah.

</details>

**Tracy Alloway**: 好的。我在一些“末日准备者”论坛上看到一件事，我不想让大家觉得我疯了，但我发现它很有趣。我发现看到人们的不安全感如何体现在物质层面上很有趣。但无论如何，

<details>
<summary>Original English</summary>

**Tracy Alloway**: Okay. Well, one of the things I saw on a bunch of the prepper boards that I sometimes look at, I don't want people to think that I'm crazy about it, but I find it interesting. I I find it interesting seeing how people's like insecurities manifest in physical stuff. But anyway,

</details>

**Joe Weisenthal**: 大家都在说，你需要开始取出现金，因为**伊朗**的局势，我们都预计会发生一场大规模**网络攻击**，它将彻底摧毁**美国金融基础设施**。顺便说一下，我有没有告诉你我的一个商业想法？我研究过“末日准备者”餐，就是那些预制餐，它们看起来都很糟糕。我觉得，如果能为雅皮士（yuppies）提供一个稍微高端的版本，会非常不错。比如那种，你知道，一些美味的……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: one of the things everyone was saying was you need to start taking cash out because of the situation in Iran because we're all expecting a big cyber attack that's going to absolutely destroy the **US financial infrastructure**. By the way, if I told you my idea for a business of like I've looked at prepper meals, like prepared meals and they all look terrible, like a slightly high-end version for yuppies, I think would be really good. Like something that you know, like some nice

</details>

**Tracy Alloway**: 我觉得，干粮能有多好吃，这在物理上是有限制的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: I think I think it's a physical limitation on how good you can actually get like dry food.

</details>

**Joe Weisenthal**: 如今科学能做很多事情。总之，冷冻干燥。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Science can do a lot of things these days. Anyway, freeze dry.

</details>

**Tracy Alloway**: 让我们谈谈手头上的实际问题。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Let's talk about the actual issue at hand.

</details>

**Joe Weisenthal**: 是的。你有没有取出现金或白银？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. Well, are you taking cash out silver?

</details>

**Tracy Alloway**: 我还没有。我正依靠我的黄金和白银储备。没错。但我认为这提出了一个合理且非常有趣的话题，那就是我们对**伊朗**的**网络**设施、技能了解多少？在这种情况下可能会发生什么？然后还有**AI**世界中发生的一切，对吧？比如**网络安全**、**网络黑客攻击**，

<details>
<summary>Original English</summary>

**Tracy Alloway**: I haven't yet. I I'm relying on my store of gold and silver. That's right. But I think this raises a legitimate and actually very interesting topic, which is what do we know about **Iran**'s cyber, I guess, facilities, skills, what could happen in this context? And then also

</details>

**Joe Weisenthal**: 鉴于这项新技术，它正在迅速变化。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: everything that's going on with the world of **AI**, right? Like **cyber security**, **cyber hacking**,

</details>

**Matt Suiche**: 完全正确。我的意思是，即使在战争本身的大背景下，抛开假设的末日场景不谈，**《金融时报》**有一篇非常有趣的报道，讲的是**以色列**如何能够入侵**德黑兰**的所有**交通灯**。是的。这几乎令人难以置信和震惊，但即使在战争本身中，或者过去几年中，也曾发生过**以色列**执行的**寻呼机攻击**。所以，是的，**网络**是其中的一部分。而且时机非常巧合，因为说到**AI**，就在上周五，我们录制节目的日期是3月5日，我不确定节目何时播出，但基本上在一周前，有消息称**Anthropic**与**国防部**或**战争部**的关系彻底破裂。所以现在这一切都混杂在一起。**AI**将如何真正改变战争？**AI**及其对**国家安全**的影响，以及**AI**与**黑客攻击**的关系？现在这一切都交织在一起，有很多值得探讨的地方。

<details>
<summary>Original English</summary>

**Matt Suiche**: Totally. I mean, also just within the context of the war itself, setting aside hypothetical doom scenarios, there's a really interesting report in the **Financial Times** about **Israel** having been able to hack into all of the **traffic lights** in **Tehran**. Yeah. Almost unbelievable and shocking, but there's already within the war itself or even over the last couple of years, there was the **pager attack** that uh **Israel** had executed. And so, yes, cyber is part of it. And the timing is wild here because speaking of **AI**, it was just on Friday, we're recording this March 5th. I'm not exactly sure the date is coming out, but a week ago basically there was the news, the complete collapse of the **Anthropic** relationship with the **Department of Defense** or the **Department of War**. And so it's all in the mix right now. And how is **AI** actually going to change warfare? And what are the **national security** implications of **AI** and **AI** and hacking? There is a lot in this sort of mix that's all happening right now.

</details>

**Joe Weisenthal**: 绝对是。真正吸引我眼球的是一个关于黑客使用**Claude**入侵**墨西哥政府**系统的故事。你看到了吗？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Absolutely. The thing that really caught my eye was the story about a hacker using **Claude** to hack into like the **Mexican government** system. Did you see that?

</details>

**Matt Suiche**: 那真的很有趣，因为看起来那个黑客从**Claude**本身提取了大量信息。你知道，我很确定你不能直接对**Claude Code**说：“我想入侵**墨西哥政府**网站。帮我构建这个应用程序。”它不会那么做。它被训练成避免恶意用途。但人们总能找到方法来“越狱”它们。人们总能找到方法从**AI**本身的训练数据中提取信息。而且已经有一些泄露的例子，你知道，人们将数据上传到**AI**，然后不知何故其他人也能看到。总之，这里有很多我们需要进一步了解的东西。

<details>
<summary>Original English</summary>

**Matt Suiche**: That was really interesting because it seemed like the hacker extracted a bunch of information from **Claude** itself. You know, I'm pretty sure you cannot go to **Claude Code** and say like, I want to break into the **Mexican government** website. Help me like build this app. It won't do that. It's trained to avoid malicious uses. But people find a way to jailbreak them. people find a way to sort of extract information from the **AI** itself that has in its training and so forth. And there's been examples of leaks where you know people upload data to the **AI** and somehow other people see it. Anyway, there's a lot here that we have to learn more about.

</details>

**Tracy Alloway**: 我们应该讨论所有这些，而且我们确实请到了一位完美的嘉宾，他以前也来过播客，但已经有一段时间了。我们将与**Matt Suiche**对话。他是**DB**的创始人，这是一家为**AI代理**提供数据基础设施的初创公司。所以，他真的是一位完美的传奇黑客。

<details>
<summary>Original English</summary>

**Tracy Alloway**: We should talk about all of it and we do in fact have the perfect guest, someone who's been on the podcast before, but it's been a while. We're going to be speaking with **Matt Swish**. He is the founder of **DB**, which is a data infrastructure startup for **Aentic AI**. So honestly the perfect and a legendary hacker.

</details>

**Joe Weisenthal**: 一位传奇的法国黑客。我应该先说这个。Matt，非常感谢你再次来到**OddLots**。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: A legendary French hacker. I should have said that first. Matt, thank you so much for coming back on **OddLots**.

</details>

**Matt Suiche**: 非常感谢。已经有一段时间了。我想大概有四年了吧？

<details>
<summary>Original English</summary>

**Matt Suiche**: Thank you very much. It's been a while now. I think it's been what, four years?

</details>

**Tracy Alloway**: 是的，我想是的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah, I think it has been.

</details>

**Joe Weisenthal**: 上次我们和你交谈时，你还在**迪拜**，现在你从**瑞典**和我们连线，背景看起来非常古斯塔夫风格。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: The last time we spoke to you, you were still in Dubai and now you're coming to us from Sweden and a very Gustavian looking background over there.

</details>

**Matt Suiche**: 我想实际上我们上次谈话是在**俄罗斯入侵乌克兰**之后。所以我想，是的。哇。那已经差不多……

<details>
<summary>Original English</summary>

**Matt Suiche**: I think actually when we talked was right after **Russia's invasion of Ukraine**. So I guess yeah. Wow. That has been almost

</details>

**Joe Weisenthal**: 每次有战争，我们都会找你，Matt。但因为战争与**网络间谍**、**网络安全**、**黑客攻击**等交织在一起，所以这是一个很自然的时刻。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: every time there's a war we call you Matt. But because war is so intermixed with **cyber espionage**, **cyber security**, **hacking** and so forth, it's a natural natural time.

</details>

### Matt Suiche：传奇黑客的视角

**Tracy Alloway**: 那么，为了那些四年前没有听过那期节目的人，你能简单介绍一下你自己，以及你在**黑客社区**的经历，包括**Shadow Brokers**和**WannaCry**时代等等。

<details>
<summary>Original English</summary>

**Tracy Alloway**: So for the benefit of people who didn't listen to the episode four years ago, can you just give some context around who you actually are and your sort of history in the **hacking community** including you know **shadow brokers** and the **want to cry** era and all that stuff.

</details>

**Matt Suiche**: 我在**企业软件**领域工作了将近20年，特别是**网络安全**。我的名字出现在一些不同的泄密事件中，因为我分析了一些被泄露的私人信息，也因为过去十年中针对**关键基础设施**发生的许多攻击。上次我们做播客时，我们讨论的一个问题是：一旦进入**动能战争**，**网络**真的重要吗？这正是现在正在发生的情况。主要的结论是，一旦你开始使用导弹，大多数这些**网络**元素就不再那么相关了，因为你主要会使用**网络**来收集信息和情报，以准备攻击，或者扰乱敌人，制造混乱。但正如我们现在所看到的，你可以使用价值2万美元的**无人机**，制造比任何**漏洞利用**更大的混乱。

<details>
<summary>Original English</summary>

**Matt Suiche**: So I've been in **enterprise software** for almost like 20 years particularly **cyber security** and my name appeared in a few of the different leagues because of various analysis that I've done of like private information that was being leaked but also a lot of attacks that happened that happened to target **critical infrastructure** over the last 10 years and last time we were on the podcast uh one of the thing we talked about is does cyber really matter? Once you enter into a **kinetic war**, which is exactly what's happening now and the main takeaway was once you start using missiles, most of these cyber elements are not really relevant because you would use cyber mostly to gather **information** and **intelligence** to prepare an attack or to disorganize an enemy or create confusion. But as we have seen now, you can use like **drones** that are like $20,000 and create more chaos that you would do with any sort of **exploits**.

</details>

**Joe Weisenthal**: 你知道，我喜欢你被介绍为“传奇黑客”，然后你说：“哦，我在**企业软件**领域工作了20年。”我觉得这就像**小熊维尼**的表情包。你知道，那种休闲装，然后是盛装。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: You know, I like how you're introduced as a legendary hacker and then you're like, "Oh, I've been 20 years in **enterprise software**." I feel like this is like the uh the **Winnie the Poo** meme. It's like, you know, that casual and then fancy dress up

</details>

**Tracy Alloway**: 黑客，然后下面是20年**企业软件**经验。但你提出的这个观点非常有趣，即大多数人想象的**网络攻击**，就像Tracy一开始说的那样，是整个**金融基础设施**突然停摆，人们担心会停电等等。但实际上，或者说我们到目前为止所看到的大部分情况是，战争背景下的**网络**更多地是关于**数据收集**、**间谍活动**等等，而不是那些更像电影里才会出现的情节。

<details>
<summary>Original English</summary>

**Tracy Alloway**: hacker and then below it 20 years in uh enterprise software. But this is a really interesting point that you made this idea between okay mostly it sounds like when people imagine **cyber attacks** they imagine what Tracy talked about in the beginning suddenly the entire **financial infrastructure** like just come to a halt people worried about or there's going to be a blackout etc. But in reality or what we've seen so far by and large is that cyber in the context of war is still much more about **data collection**, **espionage** and so forth rather than these more like you know the types of things you might see in a movie.

</details>

### 网络战的演变：从间谍到物理攻击

**Matt Suiche**: 是的，没错。我的意思是，在过去10到15年里，我们确实看到了一些针对**关键基础设施**的**网络攻击**。**伊朗**在2012年左右袭击了**沙特阿美**。嗯。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah, exactly. I mean over the last like 1015 years we have seen some like attacks like **cyber attacks** against **critical infrastructure**. **Iran** targeted like **Aramco** around like 2012. Mhm.

</details>

**Joe Weisenthal**: 他们主要使用的是我们称之为“擦除器”的东西，那是一种恶意软件，会擦除大多数机器的硬盘。然后我们显然有几年前的**Stuxnet**案例，那是以色列和美国联合行动，针对**伊朗**的一些核电站，其中一些**PLC**被攻击。但我们周末看到的是，一些**无人机**袭击了**Amazon数据中心**，对吧？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: They were just mostly like using a what we call a **wiper** that was like a **malware** that was erasing the hard drive of most of the machines. And then we obviously have the case of **Stuxnet** few years before where it was a joint **Israeli** **US** operation against some of the nuclear centrals in **Iran** where some of the **PLC**'s were targeted. But what we have seen over the weekend is some of the **drones** happen to target some of the **Amazon data centers**,

</details>

**Tracy Alloway**: 对。

<details>
<summary>Original English</summary>

**Tracy Alloway**: right?

</details>

**Matt Suiche**: 这造成了极大的不稳定，因为多个区域都宕机了，我想是三个区域中的两个，第三个区域几天后仍在恢复中，因为现在大多数公司，无论是私营公司还是公共公司，都依赖于**云计算**，这在以前并不是常态。一旦你在依赖性方面出现某种程度的集中化，你也就成了容易被攻击的目标。而且大多数政府、**AI公司**、**云计算公司**在他们的威胁模型中并没有考虑价值2万美元的**无人机**，这是一种相当新的情况，但也证实了**动能战争**可以产生更大的影响。所以我同意**网络**在战前用于**信息收集**等方面可能更有用的观点。但我们在过去一周左右也看到了一些**网络攻击**的部署。所以我们知道**以色列**正在攻击**伊朗**的一些**网络基础设施**，我们也知道**伊朗**可能也尝试了一些事情，也许没有那么成功，但请你给我们讲讲我们到目前为止实际看到了什么。所以到目前为止，我们看到了一次**以色列**行动，一个祈祷应用程序被劫持，并向用户发送了一些信息。所以这更多是为了在人们中制造混乱。

<details>
<summary>Original English</summary>

**Matt Suiche**: And that created so much instability because multiple of the zones have been down and I think two out of three and the third one is still recovering days after because most of companies either private companies or public companies now relying on the **cloud** which is something that was not really the case before. And once you have some sort of centralization in term of dependence, you also become an easy target. And most of governments, **AI companies**, **cloud companies** do not really have $20,000 **drones** in their threat models, which is like something that's pretty new, but also confirms that **kinetic wars** can have more impact. So I take the point about cyber being perhaps more useful before a war when it comes to **info gathering** and things like that. But we have seen some deployment of **cyber attacks** in the past week or so. So we know **Israel** is attacking some **cyber infrastructure** in **Iran** and we know that **Iran** has perhaps attempted some things maybe not as successfully but walk us through what we've actually seen so far. So so far we have seen an **Israeli** operation where one of the prayer app has been hijacked and some message was sent to the users. So it's more like to create confusion within people

</details>

**Joe Weisenthal**: 还有**交通灯行动**，是为了了解一些目标的位置，但它更多是用于侦察，在破坏方面我们没有看到任何重大影响，甚至**伊朗**政府本身也切断了大部分用户的互联网。我们看到社交媒体上的很多内容都是常见的**虚假信息**和**错误信息宣传**，特别是现在有了**AI**，有太多的**AI糟粕**，比如视频、文本、机器人，这现在变得非常普遍，即使没有战争也是如此。所以，它并没有真正产生很大的影响。所以，它更多是为了制造混乱，而不是实际的破坏。现在，我们肯定正在进入一个阶段，

<details>
<summary>Original English</summary>

**Joe Weisenthal**: also the **traffic light operation** to understand the position of some of the target but it's more used for like reconing and in term of destruction we didn't see anything significant even the government itself of **Iran** shut down most of the internet for a lot of the users and a lot of what we see on social media is the usual **disinformation** and **misinformation campaign**, especially now with **AI**, there's so much **AI slop** with like the videos, the text, the bots that's becoming pretty common now, even when there is no war. So, it's not really like really impactful. So, it's more like to create confusion than being actually destructive. And now, we're definitely entering in a stage where

</details>

**Matt Suiche**: 它已经非常具有破坏性。我不记得上次我们看到这么多国家被攻击是什么时候了，我认为这在战争气候中是第一次。

<details>
<summary>Original English</summary>

**Matt Suiche**: it's been extremely uh destructive. And I cannot remember the last time we have seen so many countries being targeted which is pretty like a first I would say in term of like a war climate.

</details>

**Joe Weisenthal**: 你能谈谈，你知道，人们整天盯着屏幕，自欺欺人地认为他们在“监控局势”等等。但大多数情况下……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Can you talk about you know people stare at their screens all day and they fool themselves into thinking that they're quote monitoring the situation etc. But mostly

</details>

**Tracy Alloway**: 那是Joe的投射吗？

<details>
<summary>Original English</summary>

**Tracy Alloway**: is that projection Joe?

</details>

**Joe Weisenthal**: 我不自欺欺人。不，我实际上是，我看着我的屏幕，我知道我被无上下文的垃圾、糟粕和宣传所淹没。我很好奇你作为认真对待这些话题的人，而不是在轰炸开始后第二天就成为“一夜专家”的人，你是如何实际监控局势的？你如何真正知道什么是真实的，等等，并避免仅仅盯着屏幕和接触糟粕的错觉？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: I don't delude myself. No, I like actually like I sort of look at my screen and I know that I'm being inundated with contextless garbage and slop and propaganda and so forth. I'm curious how you monitor the situation actually as someone who takes these topics seriously and doesn't just sort of become a overnight expert, you know, the day after bombings begin. Like how do you pay attention to what matters? How do you actually know what's real and so forth and avoid just sort of the delusion of staring at the screen and and engaging with slot?

</details>

**Matt Suiche**: 这是一个好问题，因为信息太多了。所以我想默认的反应是忽略大部分信息。是的。

<details>
<summary>Original English</summary>

**Matt Suiche**: It's a it's a good question because there's so much of it. So I think the default reaction is to ignore most of it. Yeah.

</details>

**Tracy Alloway**: 除非它变得非常重要。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Unless it becomes really significant.

</details>

**Matt Suiche**: 在这种情况下，我认为这归结为查看实际的损害。许多来自军事界和情报界的人一直低估了**伊朗**的能力。就像人们过去对**朝鲜**所做的那样，现在**朝鲜**拥有世界上一些最好的黑客，我们看到他们攻击**金融机构**，而以前他们不会做太多。所以肯定有内部能力可用，但现在噪音太多了，就像你说的，很多人都在监控局势。

<details>
<summary>Original English</summary>

**Matt Suiche**: In this case, I think it comes down to looking at the actual damage. Many people from the military world but also the intelligence community has been underestimating **Iran** capabilities. Exactly like people used to do with **North Korea** and now **North Korea** has some of the best hackers in the world when we see them like targeting **financial institutions** whereas before they would not do like much. So there is definitely like internal capabilities that are available but there is so much noise now like you say a lot of people are monitoring the situation

</details>

**Joe Weisenthal**: 给出所谓的“一夜专家”意见。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: giving the quote unquote like overnight expert opinions

</details>

**Matt Suiche**: 这造成了很多噪音，但我想说，在这种特殊情况下，我们已经听了大约40年**伊朗**即将到来的威胁了。

<details>
<summary>Original English</summary>

**Matt Suiche**: and that's becoming a lot of noise but I would say that in this particular case we have heard of the imminent threat of **Iran** for around 40 years

</details>

**Tracy Alloway**: 对。

<details>
<summary>Original English</summary>

**Tracy Alloway**: right

</details>

**Matt Suiche**: 这也不是一个真正新的情况。所以大多数人对此都有背景了解，即使是上周末发生的袭击，许多人也已经预料到几周了，特别是它们是去年夏天发生事件的延续。

<details>
<summary>Original English</summary>

**Matt Suiche**: and that's also not really a new situation So most of people would have context around it and even for like the attack that happened last weekend many people were expecting them for weeks especially as they are continuation of what happened last summer.

</details>

**Joe Weisenthal**: 你能再详细谈谈**数据中心**攻击吗？因为那不是真正的**网络攻击**，我的意思是，那只是针对**数据中心**的物理**动能战争**。我惊讶于它的破坏性有多大。我本来以为**云计算服务提供商**的流动性很强。好吧，一个宕机了，但你知道，同样的软件可以从许多其他云上运行。但我看到确实出现了中断。我看到**Fortnite**发推文说，由于**数据中心**遭到攻击，他们的一些游戏体验受到了影响。这些攻击的破坏性有多大？因为这当然是一个非常，你知道，

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Can you actually talk a little bit more about the **data center** attack and um because that's not cyber really I mean that's just that's just a physic that's **kinetic warfare** against a **data center**. I was surprised how disruptive was that. I sort of would assume that **cloud service providers** that it's fairly liquid. Okay, one goes down but you know it can just be the same software can be run from numerous other clouds. But I saw that there were disruptions. I saw **Fortnite** tweeting about the fact that some of their gameplay was impaired due to the attack on **data centers**. How disruptive have those attacks been because this is of course a very, you know,

</details>

**Tracy Alloway**: 这就是**动能**与**网络**的交汇点。

<details>
<summary>Original English</summary>

**Tracy Alloway**: this is where kinetic meets cyber.

</details>

**Joe Weisenthal**: 是的。而且有很多，你知道，未来像考虑加固这些**数据中心**，就像你说的，它们将越来越多地成为战争的目标。它的破坏性有多大？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. And there's a lot, you know, in future like thinking about hardening these **data centers** and as you say like making them they're going to be increasingly targets for war. Like how disruptive was that?

</details>

**Matt Suiche**: 很好的问题。所以我想，主要的启示之一是它非常成功。就像我们之前说的，一架**Shahid无人机**大约2万美元，他们成功地关闭了**Amazon**的两个区域。实际上，即使你查看**Amazon**的官方报告，他们在大约36小时内都只是说“某些物体击中了**数据中心**”，然后才明确表示是**无人机袭击**。所以很多使用这些服务的应用程序都受到了影响。从两家银行的本地应用程序来看，因为在一个**数据中心**里，你负责处理多种不同的服务。

<details>
<summary>Original English</summary>

**Matt Suiche**: Very good question. So I I think one of uh the the main takeaway is that it has been extremely successful. So like we said before like a **shah drone** is around $20,000 and they managed to shut down two of the zones of **Amazon**. Actually even if you look at the official report from **Amazon** for like 36 hours they were just saying oh some objects struck the **data centers** before they actually explicitly said they were **drone strikes**. So a lot of services that have been using them have been targeted. So from like local applications from two banks because in a **data center** you are taking care of multiple different services

</details>

**Tracy Alloway**: 对。

<details>
<summary>Original English</summary>

**Tracy Alloway**: right

</details>

**Matt Suiche**: 甚至**Versel**不得不将他们的数据重新路由到**孟买**，并排除**中东**作为部署区域。所以即使你考虑大多数**零日漏洞利用**的成本，它们可能高达数百万美元的攻击，如果你真的旨在破坏事物，使用这种攻击的成本效益非常高。所以你确实进入了一种**非对称冲突**，你可以只花费一些非常旧的材料，却能产生比那些尖端且试图通过能力给人留下深刻印象的人更大的影响，因为归根结底，这并不重要。

<details>
<summary>Original English</summary>

**Matt Suiche**: and even **Versel** had to reroute uh their data to **Bombay** and to exclude uh like **Middle East** as deployment. So even if you take the cost of most of like **zero day exploits** that can go up to like multi-million dollar attacks, if you are really aiming at destructing things, the cost uh reward of using such an attack is uh really efficient. So you really enter into some sort of **asymmetric conflict** where you can just spend like some really old material and have way more impact than someone who's going to be like cutting edge and just trying to impress with like capabilities because at the end of the day it does not really matter.

</details>

### AI对政府网络能力的影响

**Joe Weisenthal**: 如今政府是如何建立他们的**网络能力**的？因为我脑海中有一个10或20年前的画面，你知道，他们会招募一个20岁的年轻人，比如你当时的样子，他们会在一个黑暗的房间里工作，诸如此类。但后来……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: How do governments actually build up their **cyber capabilities** nowadays? cuz I have this image in my head of maybe 10 or 20 years ago, you know, they would recruit like a 20-year-old such as yourself at the time and they would be working in a dark room, that sort of thing. But then

</details>

**Tracy Alloway**: 喝着红牛。

<details>
<summary>Original English</summary>

**Tracy Alloway**: drinking Red Bull.

</details>

**Joe Weisenthal**: 喝着红牛。没错。但后来，你知道，我们经历了**硅谷**的繁荣，所以你面临着来自私营公司的竞争。现在我们又经历了**AI**的繁荣，再次面临来自私营公司更多的竞争，与此同时，政府似乎正在将他们的一些技能集潜在地转移给私营公司，比如**Anthropic**和**ChatGPT**以及其他一些公司。请你给我们讲讲政府**网络能力**的发展是如何实际转变的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Drinking Red Bull. That's right. But then, you know, we had the boom in **Silicon Valley** and so you had competition from private companies. Now we have the boom in **AI** and again even more competition from private companies and at the same time governments seem to be I guess seeding some of their own skill set to potentially private companies like **Anthropic** and **ChatGpt** and some others. Walk us through how I guess the development of governmental **cyber capacity** has actually shifted.

</details>

**Matt Suiche**: 我的意思是，在能力方面，过去几年里并没有真正改变太多。我想我们都记得2013年的**Snowden泄密事件**，当时我们开始更多地了解政府的内部能力，包括国内监控、全球监控和漏洞利用能力。从那时起，我们每年都会看到政府数据泄露的历史。所以从某种意义上说，情况变化很大，但又没有太大变化。最近，**Elfrey Aris**的一名承包商被判处87个月监禁，因为他向一名俄罗斯中间商出售了**零日漏洞利用**。

<details>
<summary>Original English</summary>

**Matt Suiche**: I mean something that didn't really change over the last like years in term of capabilities like I guess we all remember like the **northern leaks** in 2013 when we started to see more about the inside of like capabilities from a government including like **domestic m surveillance** **global surveillance** **exploitation capabilities** and since then every other year we have seen an history of data being leaked that belongs to uh the government. So in a way things have been changing a lot but not really much. Like most recently there was a contractor from **Elfrey Aris** that was uh sentenced to 87 months uh sentence because he happened to sell uh **zero day exploits** to a **Russian broker**.

</details>

**Joe Weisenthal**: 而那实际上是属于政府的漏洞利用，因为存在某种集成商。所以我们看到像美国这样的民族国家或政府投入巨额资金用于攻击能力，但他们也一直被内部人员所伤害。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: and that's like actual exploit that belonged to to the government because there was some sort of integrator. So we see like nation states or like governments like the **US** investing like enormous amount of money into offensive capabilities but they also keep being burned by insiders.

</details>

**Tracy Alloway**: 嗯。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Mhm.

</details>

**Matt Suiche**: 很多这些能力也和内部强制力一样强大。

<details>
<summary>Original English</summary>

**Matt Suiche**: A lot of those capabilities also as strong as the internal coercion.

</details>

**Joe Weisenthal**: 但我想我问的是，你知道，如果你是**国防部**，或者现在是**战争部**，你正在考虑开发内部能力，还是与像**Anthropic**这样的公司合作？我们应该谈谈那里正在发生的所有戏剧性事件。你现在是如何平衡这些决策的，与10或20年前相比呢？我的理解是，现在很多工作也都是外包的，因为他们无法在内部开发那么多能力。所以现在，就像我们看到**Anthropic**一样，它曾被用于**Maduro行动**。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: But I guess what I'm asking is, you know, if you're the **Department of Defense** or I guess now the **Department of War** and you're thinking about developing in-house capabilities versus partnering with a company like **Enthropic** and we should talk about all the drama that's going on there. How are you balancing those decisions nowadays versus say 10 or 20 years ago? Like my understanding is that now a lot of it is also like outsourced because they cannot really develop uh as many capabilities internally. So now like we have seen with uh **entropic** that it had been used in the **Maduro operation**

</details>

**Tracy Alloway**: 对。

<details>
<summary>Original English</summary>

**Tracy Alloway**: right

</details>

**Matt Suiche**: 然后在那之后，**Anthropic**退出了，因为他们说这违反了他们的道德标准。

<details>
<summary>Original English</summary>

**Matt Suiche**: and then after that like there was a pull out from **entropic** because they said it was violating their ethical like um

</details>

**Tracy Alloway**: 标准。

<details>
<summary>Original English</summary>

**Tracy Alloway**: standards

</details>

**Matt Suiche**: 政策，是的，标准。所以我想说，现在变化非常快的一件事是**AI**被纳入这些决策中。但正如我们都知道的，**AI**也可能**幻觉**。所以即使**Anthropic**的CEO **Dario**也表示，它肯定还没有达到可以用于完全自主决策的状态。所以我想说，**AI**元素将是主要的区别。我们现在甚至开始看到它用于**漏洞利用开发**或**漏洞发现**，但现在下定论还为时过早。但总的来说，我想说它非常相似。

<details>
<summary>Original English</summary>

**Matt Suiche**: like policy yeah standards. So I would say now something that's really changing like very fast is the incorporation of like **AI** into those decisions. But as we all know like **AI** can also **hallucinate**. So even **Dario** the CEO of **entropics** that said it's definitely not in a state where it can be used for like fully autonomous decisions like that. So I would say like the **AI** element would be like the main difference. Even we start to see it now for like **exploit development** or **vulnerability discovery**, but it's still too early to kind of like give a definitive like opinion about it. But overall, I would say it's very similar.

</details>

**Tracy Alloway**: 那么，请你谈谈**漏洞利用开发**，因为我知道你不能直接去**Claude Code**说：“我正在研究一个**零日恶意软件攻击**。帮我解决这个问题。”但是，你知道，我也知道有一些非常有才华的人，他们以能够“越狱”**AI**并获得实验室不希望他们的**AI**产生的非法输出而自豪。那么，你是否了解在纯粹的**黑客社区**中，**AI**目前是如何用于这些目的的，或者他们能够从这些工具中获得什么？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Well, talk to us about **exploit development** because I know that you can't just go to **claude code** and say like, I'm working on a **zero day malware attack**. Help me figure this out. But, you know, I also know that there are some very talented people who pride themselves in being able to jailbreak **AI** and illicit outputs that the labs do not want their **AIs** to produce. So, do you have a sense how just within the pure like **hacker community** **AI** is being employed today for these purposes or what they're able to get out of these tools?

</details>

**Matt Suiche**: 这是一个好问题。所以，我们开始看到人们利用**AI**进行**漏洞发现**。是的。这实际上变得相当不错。我想**Anthropic**甚至发表了一篇文章，解释了**Claude**如何用于智能合约的发现，以及它如何自动发现一些漏洞。我想他们最近甚至发布了一个名为**Claude for Security**的产品，旨在进行代码评估。但现在我们正在进入一个有趣的范式转变，即**软件成本**正在趋近于零。对吧？所以如果你是一家公司，如果你的**软件开发成本**越来越低，那么要说服人们为了**安全原因**审计软件会比开发实际软件更昂贵，这也很困难。所以我想这是我们将要看到的一个转变。但是当它……

<details>
<summary>Original English</summary>

**Matt Suiche**: It's a good question. So, like we started to see people leveraging like **AI** for like **bug discovery**. Yeah. which actually is becoming like pretty good. I think even **Entropic** published an article explaining how **cloud** can be used for discovery into smart contracts and how it found some bugs automatically. And I think even recently they released something called uh **cloud for security** that was aiming at uh doing um code uh assessment. But now we're entering into this like interesting uh paradigm shift where the **cost of software** is going towards zero. Right? So if you're a company and if your **cost of building software** is becoming less and less, it's also hard to convince people that auditing software for **security reasons** is going to be more expensive than developing the actual software. So I think that's one of the shift uh we're going to see. But when it

</details>

**Joe Weisenthal**: 抱歉，你能解释一下吗？抱歉，暂停一下。你刚才那部分是什么意思？说服会很难……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Sorry, can you explain Sorry, pause, pause that last part. What what did you mean by that? It's going to be hard to convince

</details>

**Matt Suiche**: 如果你要为构建产品分配预算。所以你大部分预算通常分配给软件工程师来构建软件，然后你会在之后进行一些代码审查，以确保在发布给公众之前没有漏洞。但**安全风险**通常很高。你不能仅仅依赖**AI工具**，至少目前不能。也许一年后会成为可能。所以这将非常有趣，看看它将如何引起市场转变，因为现在有了**Claude Code**，作为一位著名的“氛围程序员”Joe，我相信你知道，

<details>
<summary>Original English</summary>

**Matt Suiche**: if if you're going to have like uh to allocate budget for like building a product. So you have most of the budget that's usually allocated for like your software engineers to build the software and then you do some code review afterwards to make sure there's no vulnerabilities before it gets released to the public. But **security risk** is usually like pretty high. You cannot just rely on like **AI tools** at least not at the moment. Maybe in a year from now it's going to be possible. So it's going to be like really interesting to see how it's going to like do like a market shift because now with **cloud code** and as a famous uh vibe coder Joe I'm sure you know that

</details>

**Joe Weisenthal**: **软件开发成本**正在趋近于零，如果你只看时间线的话。就此而言，你是否相信“SaaS末日”？因为显然有一种观点认为，现在每个人都可以使用自然语言相当容易地创建自己的软件。但另一方面，如果你是一家大公司，或者可能是一个政府，你仍然会希望从外部供应商那里购买软件，考虑到一些**安全问题**，考虑到出于各种原因，管理原因，可能没有必要在内部重新创建一个完整的软件业务。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: the **cost of building software** is approaching like zero if you just look on the timeline. Are you actually on this note, are you a believer in the **SAS apocalypse**? Because obviously there's the argument that well now everyone can just create their own software fairly easily using natural language. But on the other hand, if you're a big corporation or presumably a government, you're going to want to have you're going to still want to buy software from an external provider given some of the **security concerns**, given that it might not necessarily make sense for various reasons, management reasons perhaps to recreate an entire software business inhouse.

</details>

### 软件成本趋零与数据价值

**Matt Suiche**: 所以我肯定对此有偏见，但作为认为**软件成本**正在趋近于零的人，以及作为观察**软件成本**崩溃的人，我们意识到的一件事是，**数据**是**AI经济**中唯一持久的资产。这就是为什么我们决定开发**DB**，我目前正在从事的初创公司，因为那是唯一真正具有长期价值的东西，如果**AI代理**需要进行交易或做出决策，因为即使你从任何角度来看，你知道，如果**AI代理**被设计成自主思考，你需要有足够的信息来做出这些决策，无论何时你进行推理循环。所以软件本身，如果你只是构建它，它是相当静态的，而**AI代理**的反馈循环更具动态性，但它改变了它们做出决策的上下文。所以**SaaS业务**肯定会遇到困难，因为如果任何人，包括**Shopify**的CEO，都能在一个下午重写一个MRI软件，只是为了查看他的背部MRI，你可以想象到今年年底它会带来多大的颠覆。我认为我们还没有看到的唯一一件事是**企业AI代理**。所以，到目前为止，我想说，从圣诞节以来，人们大多仍在尝试寻找一个合适的用例。我们看到了很多消费级**AI代理**，比如**Open CL**，它确实让**AI代理**变得更主流，但我们还没有真正看到**企业AI代理**。所以，尽管每个人都害怕自己的工作被取代，但我们还没有真正看到**AI代理**取代整个部门或全部员工。所以我们看到了一些围绕**软件工程**的颠覆，主要是为了提高**软件工程**的效率，特别是在开发方面，缩短了时间线，但我们还没有看到真正的**企业AI代理**。

<details>
<summary>Original English</summary>

**Matt Suiche**: So I'm definitely biased on that but uh as someone who thinks like the **cost of software** is going towards zero and as someone who is like watching the **software cost** like collapsing one of the thing that we uh realized is that **data** is the only durable asset in the **AI economy**. That's why we decided to work on **DB** the current startup uh I'm working on because like that's the only thing that's really going to have value long term if agents need something to to transact or like to take decision on because even if you look in term of like in any context you know if agents are designed to think autonomously you need to have enough information to take those decisions whenever you're going to have your reasoning loops. So software itself if you just build it is pretty static whereas like the **agentic** like feedback loops are more dynamic but what changes the context they take decision on. So definitely like **SAS business** are going to have a hard time because if anyone including the uh **Shopify CEO** can just rewrite an MRI software in one afternoon just to like look at his uh back MRIs, you can imagine like how disruptive it's going to be like by the end of this year. I think the only thing we haven't seen yet is like **enterprise AI agent**. So, so far I would say like since Christmas people are mostly like still playing around trying to find like a proper like use case uh we see a lot of like consumer like **AI agent** like **open CL** that really made like agents more mainstream but we really haven't seen yet **enterprise AI agent**. So as everyone is kind of scared of being replaced for their jobs, we haven't really seen like actual like **AI agents** replacing entire departments or full on like employees. So we have seen some disruption around like **software engineering** mostly to make like **software engineering** more efficient especially in term of like development with shorter like timelines but we haven't seen yet like proper like **enterprise AI agents**.

</details>

### AI代理：机遇与安全挑战

**Joe Weisenthal**: 你如何定义**AI代理**？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: How do you define an **AI agent**?

</details>

**Matt Suiche**: 所以我对**AI代理**的看法是，我喜欢提醒人们**AI代理**到底是什么。目前大多数**AI代理**只是一段代码，通常用Python或Typescript编写，它只是对**Anthropic**、**OpenAI**进行大量调用，并循环运行，做出决策，并调用第三方工具，如MCPS或网络搜索。

<details>
<summary>Original English</summary>

**Matt Suiche**: So my view of an **AI agent** and I like to remind people like what an **AI agent** actually is. At the moment most of **AI agent** is just like a piece of code usually written in Python or in Typescript that's just doing a bunch of calls to like **entropic** **open AAI** and running in a loop and taking decisions and calling like third party tools like MCPS or web searches.

</details>

**Joe Weisenthal**: 所以这基本上就是**AI代理**。我们倾向于将**AI代理**视为一个完全不同的“人格”，但归根结底，它只是一段作为服务在机器或服务器上运行的软件。所以从**安全角度**来看，这非常有趣，它只是另一种服务或软件，但人们真的很喜欢以另一种方式思考它。好吧，从**安全角度**来看，我的意思是，**AI代理**令人兴奋的一个方面是它们可以自主工作，对吧？你设定一个任务，它就可以出去寻找它需要做的事情，它会看到，好吧，这行不通。我将尝试，它将尝试这个，它将尝试那个。哦，我需要连接到这个网络服务才能获取这些信息等等。**AI代理**的缺点恰恰是相同的。**AI代理**的缺点是它们可以做任何它们想做的事情，如果它不小心删除了大量文件，因为它认为这是执行任务所必需的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So that's mostly what an **AI agent** is. We tend to think of **AI agent** as a completely like different persona, but at the end of the day, it is just like a piece of software that's running as a service on a machine or on a server. So from a **security standpoint**, which is pretty interesting, it's just like another service or like software, but people really like to think of it in an other way. Well, just so like I from the **security standpoint**, I mean, one of the exciting aspects of **AI agents** is that they can work autonomously, right? You set a task and it can go out and find what it needs to do and it sees like, okay, this didn't work. I'm going to try it's going to try this thing. It's going to try this thing. Oh, I need to connect to this web service to get this information, etc. The downside of **AI agents** is precisely the same. The downside of **AI agents** is that they could do whatever they want to do and if it accidentally deletes a bunch of files because it thinks that's what's necessary to execute the task.

</details>

**Tracy Alloway**: 所以我很好奇，从**安全角度**来看，我的意思是，我们已经看到了人们的私人信息被泄露的例子，或者像我提到的删除大量信息的例子。这是否是一种思考**安全威胁模型**的新方式？即能力和缺点是同一回事。它是一样的。这有点像**幻觉**，对吧？创建输出的能力，它也与创建错误输出、虚假输出的能力息息相关。所以，你知道，它自主行动的能力，也是它自主破坏的能力。这是一种新颖的**威胁模型**，还是思考**企业安全**的一种新范式？

<details>
<summary>Original English</summary>

**Tracy Alloway**: So like I'm curious like from a **security standpoint** like I mean we've already seen examples of people getting private information exposed or as I mentioned the example of deleting a bunch of information. Is this like a new way to think about the **security threat model**? the fact that the capability and the downside are one and the same. It's the same. It's sort of like **hallucinations**, right? The ability to like create an output and it also, you know, is handinhand with the ability to create a wrong output, a false output. And so, you know, the ability to do a to act on its own is also the ability to destroy on its own. Is this sort of like a novel **threat model** or a novel paradigm in thinking about **enterprise security**?

</details>

**Matt Suiche**: 从**企业安全**的角度来看，这几乎是一回事，因为如果你正在构建软件，你不能只是在事后修补软件之类的，因为它永远不会结束，**安全**必须内置，你需要从一开始就有一个安全的设计。我们现在看到的是，每当人们做一些**AI代理**的事情时，他们只是预先给予所有权限。

<details>
<summary>Original English</summary>

**Matt Suiche**: From an **enterprise security** standpoint, it is pretty much the same thing in the sense of like if you're building software, you cannot just really like patch software afterwards and stuff because you never it never ends like security must be like built in and you need to have like a safe design from the beginning. What we have seen now is like whenever people do something **aentic**, they just give like all permissions up front.

</details>

**Joe Weisenthal**: 是的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah.

</details>

**Matt Suiche**: 这可能是你能做的最糟糕的事情。如果你是一家企业，你可以想象，如果你只是给**AI代理**所有权限，它就会变成**墨菲定律**。如果因为你给了它访问权限而可能发生坏事，那么它就会发生。所以你肯定会看到更多的数据泄露，因为这些架构或**AI代理**在设计上没有安全性，这在**漏洞**和**暴露**方面与我们过去10到20年所看到的非常相似。但你知道，如果人们忽略了过去20年在**软件安全**方面所做的工作，那我们就会遇到很多问题，我想我们可能会开始看到人们，特别是在企业中，会强烈抵制，因为需要遵守合规性，所以你不能只是给你的**AI代理**完全访问权限。

<details>
<summary>Original English</summary>

**Matt Suiche**: Which is like probably the worst thing you can do. And if you're an enterprise, as you can imagine, if you just give like all permissions to an agent, it just becomes **Murphy's laws**. If something bad can happen because you gave it access to it will happen. So you're going to see like more **data leaks** for sure because there is no safety by design in those like uh architectures or like those like agents which is in term of **vulnerabilities** and like **exposure** would be like very similar to what we have seen over the last like 10 20 years. But you know if people are ignoring what has been done in term of **software security** for the last 20 years that's why we're going to have a lot of problems and I think we probably going to start to see like people especially in enterprise like pushing back a lot because there's compliance that needs to be like you know like answered to so you cannot just give like full access to like you know your agent

</details>

### AI时代的代码与隐私

**Tracy Alloway**: 说到历史的长河，我真正好奇的一件事是，你显然在这个领域工作了很长时间。你能描述一下，如果你现在在2026年开始你的职业生涯和编码经验，与你大概在90年代末或2000年初，甚至更早开始相比，会有什么不同吗？

<details>
<summary>Original English</summary>

**Tracy Alloway**: Speaking of the long arc of history, one thing I really wonder is you've obviously been in this space for a very long time at this point. Can you describe how you think your own career and I guess coding experience would have been different if you were say starting out now in 2026 versus I guess you would have started out in like the late 90s or early 2000s maybe even before that.

</details>

**Matt Suiche**: 是的，2000年代中期。嗯，我想说，改变的是，即使不追溯到2000年代，回到**Snowden泄密事件**时期，当全球监控计划被曝光时，很多人都非常害怕并感到震惊，并进行了抵制，人们真的很关心**隐私**。而现在我们正在进入一个新的阶段，很少有人关心**隐私**。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah, mid mid 2000. Well, I would say like what has changed is back even like even without going through like uh the 2000s like u back in the **Snowden days** when the **global surveillance program** was being exposed like a lot of people were really like scared of it and scandalized by it and pushed back and people really cared about **privacy**. was like now we're entering in a new arc where very few people care about **privacy**

</details>

**Joe Weisenthal**: 你看到**Anthropic**的CEO被问到为什么他拒绝与美国政府合作。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: where you see like the CEO of **Entropic** being asked why he refused to work with the **US government**

</details>

**Matt Suiche**: 他说，他们想做一项国内监控计划，这违反了他们的安全章程。所以这都是人们与**数据**关系的不同方面，我想这在软件方面非常不同。显然，现在你可以写更多东西，任何人都可以写任何东西，但我认为我们仍处于这个奇怪的“足够好”的软件阶段，

<details>
<summary>Original English</summary>

**Matt Suiche**: and he says well they wanted to do a **domestic surveillance program** so that's against or like safety like chart so this is all aspect of people relationship with **data** which I guess is very different in term of software obviously like now you can write more things anyone can write anything but I think we're still in this weird adequate software phase where

</details>

**Joe Weisenthal**: 我们知道**AI**能做什么，但它还不能真正做更多或更少的事情，我们还没有看到它的实际用例，因为它显然非常令人兴奋，感觉很多方面都与以前非常不同，

<details>
<summary>Original English</summary>

**Joe Weisenthal**: we know what **AI** can do but it cannot really do like anything more anything less yet we still haven't seen like the actual like uh use case for it because it's obviously like very exciting and it feels like a lot of it is very different from before

</details>

**Matt Suiche**: 但我们并没有真正有任何证据表明它在**国家安全**方面是如何真正提供帮助的。我知道它一直在帮助那些分析**Epstein文件**的人，因为数据量很大，这使得处理速度更快，但就实际用例而言，我认为感觉现在的世界与以前非常不同，但有太多的噪音和太多的**糟粕**，

<details>
<summary>Original English</summary>

**Matt Suiche**: but we don't really have like any evidence of how it's really helping in **national security**. I know it's been helping people who have been analyzing like **Epstein's emails** because there's a lot of data and that makes it faster but in term of like real use case I don't think the like it feels like the current world is very different than before but there's so much noise and so much like slop all over that

</details>

**Joe Weisenthal**: 从某种意义上说，它非常相似。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: in a way it is pretty similar

</details>

**Matt Suiche**: 我不知道这有没有道理。

<details>
<summary>Original English</summary>

**Matt Suiche**: I don't know if that makes sense

</details>

**Joe Weisenthal**: 嗯，我的意思是，它确实有道理。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: well I mean it does

</details>

**Tracy Alloway**: 你的公司是**DB.ai**。所以你一定认为它会被使用，或者，你知道，那里显然有一些东西。实际上，告诉我们，我实际上真的，我现在正在你的网站上。它看起来真的很有趣，因为这是我一直在思考的事情，但你一定对它的发展方向有一些愿景，并且认为这些服务实际上会有很大的需求。

<details>
<summary>Original English</summary>

**Tracy Alloway**: your company is **b.ai AI**. So, you must think that it's going to be used or that, you know, or that there's clearly something there. Actually, tell us about I'm actually really I'm on I'm on your website right now. It looks really interesting because it's something I've been thinking about, but you must have some vision for like where it's going and that there will actually be significant demand for these services.

</details>

**Matt Suiche**: 当然。我的意思是，就像我说的，我认为现在有了像**AI代理**一样的东西，构建软件，这是目前**AI**的主要用例，它将使软件成本趋近于零。所以**软件开发成本**将……

<details>
<summary>Original English</summary>

**Matt Suiche**: Sure. I mean like I was saying like I think now with like anything that's **agentic** building software which is like the main use case so far for **AI** it's going to make software like going to zero. So the **cost of building software** is going to

</details>

**Joe Weisenthal**: 所以那是真的。所以，比如说，在你看来，毫无疑问**AI**已经，我的意思是，谈谈一个用例，那是一个相当大的用例，将**软件开发成本**降至零。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: so that's real. So like say like there's in your view there's no question that already **AI** I mean talk about a use that's a pretty big use case right there bringing the **cost of building software** to zero.

</details>

**Matt Suiche**: 是的。我的意思是，即使你看看**Claude Code**的作者，他说他们从11月以来就没有写过代码。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah. I mean like even if you look at the author of **cloud code** he said they didn't write like code since November.

</details>

**Joe Weisenthal**: 所以很多人都是这样，你知道，即使我们内部，我们也确实大量使用**Claude Code**，但如果软件成本趋近于零，那么在互联网层面上还剩下什么呢？所以我们的结论是，**数据**是**AI经济**中唯一永恒的东西。所以我们正在为此构建一个层。特别是现在，围绕支付和稳定币有很多创新，你可以用它们在线支付任何东西。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So like a lot of people are like this you know even us internally like we definitely like use **cloud code** a lot but if software is going to zero like what's left in term of like the internet layers so our conclusion is that **data** is uh the only thing that's going to be like timeless in the **AI economy**. So we're building like a layer for that. Especially now there's like all those innovations around like payments and **stable coin** that you can use to actually like pay like anything online.

</details>

**Tracy Alloway**: 是的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah.

</details>

**Matt Suiche**: 所以我们认为，好吧，你有一些问题，比如**Anthropic**或**OpenAI**只是抓取互联网并使用公共互联网。所以你也可以找到方法向机器人或**AI代理**收取你的数据费用。这样至少你可以解锁这种新的收入来源，它将在这个新经济中出现，因为我认为很多传统的经济模型，比如我们说的**SaaS**，将会受到很大的冲击。所以围绕人们将如何消费数据，有一个全新的市场，我认为人们会愿意支付更多费用来获取高质量数据，因为噪音越多，你就越想确保你访问的数据是有价值和真实的。所以，是的，即使从**安全角度**来看，你知道，一旦你构建了一个基础设施层，你就可以内置安全性，以确保你返回的数据或你定义的接口访问是真正安全的，因为

<details>
<summary>Original English</summary>

**Matt Suiche**: So we think like okay you have like issues like **entropic** or like **openai** just scrapping internet and using like public internet. So you may as well find ways of charging like bots or agent for your data. So at least you can have this new like revenue unlock that's going to emerge in this like new economy because I think a lot of the traditional like economic model like for instance like we said like with **SAS** are going to be like disrupted a lot. So there is a completely like new market around how people are going to consume data and I think people people would just be ready to pay like more to have **high quality data** because the more noise there is the more you want to make sure that the data you have access to is going to be uh like valuable and real. So yeah, even from a **security standpoint**, you know, like once you build like an **infrastructure layer**, you can have this like built-in security to make sure that the data you give back or the access like for the interface that you define is actually secure because

</details>

**Joe Weisenthal**: 即使你看看**Open Claw**，例如，它的顶级技能之一就是**恶意软件**。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: even if you look at **open claw** for instance, one of the top skill was **malware**.

</details>

**Matt Suiche**: 所以人们就像生活在这个狂野的西部一样，但他们只是运行一切。所以我们预计企业将会非常不同，他们不会只是运行他们在网上找到的任何东西。

<details>
<summary>Original English</summary>

**Matt Suiche**: So like people just like living in this like wild west but they just run everything. So it's us anticipating that enterprise is going to look very different and they won't just run like anything they find online.

</details>

**Joe Weisenthal**: 是的。你知道，这是我在“氛围编程”尝试中遇到的问题之一，那就是，好吧，你希望**AI代理**出去获取一些信息，或者查询一些数据库之类的，然后它会说：“好吧，告诉我你什么时候获得了API。”他们会说：“好吧，回来获取API。”然后你必须去一个网站，然后你必须拿出你的信用卡，你必须设置一个账户，然后你获得一个**API密钥**，然后你复制粘贴等等。这非常烦人。我想要的是**AI代理**能够直接去那里说：“哦，你知道，让我用一些**稳定币**支付你，等等。它自己出去获取信息，而不需要人类参与。”但我也想到，这是我问过其他人的问题，那就是，一旦我完全在终端中操作，**AI代理**为我抓取信息等等，那么为什么我们还需要一个免费的公共互联网呢？所以我很好奇，互联网和信息总体的方向是否会完全变成，你知道，为**数据消费**支付小额交易或费用，这样数据就能以某种可用的形式到达我正在操作的终端。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. You know this is one of the things that I've encountered in my vibe coding foray is that one of the annoying things is okay you want the agent to like go out and grab some information or query some database or whatever and then it's like okay like let me know when you've gotten a an **API**. They're like, "Okay, come back and get an **API**." And then you have to like go to a website and then you have to like get out your credit card and you have to set up an account and then you like get an **API key** and then you copy and paste it and so forth. And that's very annoying. I want what I want is for the agent to just be able to go there say, "Oh, you know, like let me just pay you with some **stable coins**, etc. Just go out and get the information on its own without having this human in the loop." But it also occurs to me, and this is something that I've asked about with others, which is that like once I'm just like entirely operating in the terminal and the agent is going out and scraping information for me, etc., like why do we even have a free public internet anymore? And so like I'm curious like whether the direction of the internet and information in general is just entirely like you know paying **microtransaction** or fees for **data consumption** so that the data then arrives in some usable form in the terminal that I'm operating on.

</details>

**Matt Suiche**: 是的。不，我想你提出了一些非常好的观点。我们之后需要谈谈，你可以成为我们的新设计伙伴，你知道。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah. No, I think you you're raising some uh really good points. Uh we we need to talk after you can be our new design partner, you know.

</details>

**Joe Weisenthal**: 是的，我可以做顾问。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah, I'll be I can be a consultant.

</details>

**Tracy Alloway**: 他会入侵所有的API。我可以做顾问。不，我讨厌处理所有这些**API密钥**，为什么我还在使用我的……

<details>
<summary>Original English</summary>

**Tracy Alloway**: He's going to hack all the **API** I can be I can be a consultant. No, I hate having to deal with all these **API keys** and why am I still using my

</details>

**Matt Suiche**: 你完全正确。看，我告诉过你，你是一位著名的“氛围程序员”。你知道，就像你现在描述的用例完全有道理。这就是为什么我们把自己定位为一种受信任的提供商，

<details>
<summary>Original English</summary>

**Matt Suiche**: You're like completely right. See, I told you you're a famous live coder. You know, it's like but like the use case you're describing now is like makes entire sense. That's why like we position oursel kind of like as a trusted like provider where like

</details>

**Joe Weisenthal**: 而不是到处去获取数据。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: instead of having to go like everywhere

</details>

**Matt Suiche**: 你知道，你有一个单一的统一访问点，有点像**AI模型**的**Open Router**，但我们是为**数据提供商**服务的。因为如果你想想，当你现在在终端中使用**Claude**时，第一层基本上是你向模型本身请求信息，但我们知道模型可能已经有几个月没有更新，并且无法访问所有信息。

<details>
<summary>Original English</summary>

**Matt Suiche**: to get data, you know, you have like this single point and unified access a bit like **open router** for **AI models** but for **data providers**. Because if you think about it when you use like **cloud** now in your terminal like the level one is basically you asking the model itself for information but as we know like the model may be like a few months old and doesn't have access to all the information.

</details>

**Joe Weisenthal**: 所以第二层是**AI代理**，比如**Claude Code**或桌面版**Claude**，或者**ChatGPT**进行网络搜索，那只是它们在互联网上查找。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So like the second level is the agent like **clot code** or or **cloud for desktop** or like **chat GPT** doing web searches and that's just them looking on the internet.

</details>

**Matt Suiche**: 是的。进行**Google搜索**等等。但这仍然无法让你访问你需要的实际相关数据，例如你会有那些**API密钥**之类的。所以下一层基本上是访问私人信息。而私人信息通常是最有价值的，例如在**Bloomberg**的案例中，**Bloomberg**拥有大量极具价值的信息，但你只有通过终端订阅或任何**SaaS服务**才能访问它。如果你认为**SaaS平台**只是一些花哨的用户界面，你可以在其中浏览数据库，但有价值的数据直接就在数据库中。所以如果你能访问那些API，并且不必创建一百万个订阅，因为已经有人在做集成工作，就像一个程序化的**API市场**，但现在的集成要容易得多，特别是如果你信任它，因为我们现在也看到，每当你使用所有这些工具时，它们都会让你安装MCPS，但越来越多的人正在从MCPS转向，他们只是使用技能。因为就像你说的，我们开始花更多时间在终端中。所以终端和任何CLI都正在成为**AI代理**甚至人类的自然界面，因为你不需要尝试理解那些花哨的用户界面和用户体验。你只需要说：“好吧，我想做ABC，就去做吧。”所以我想，拥有这样的界面更有意义，就像你说的，否则它就会变得太复杂了。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah. doing like a **Google search** etc. But that's still not giving you an access to like the actual like relevant data that you would need where for instance you would have like those **API keys** and stuff. So like the level after that is basically access to **private information**. So and **private information** usually the one that's valuable like in the case of **Bloomberg** for instance **Bloomberg** has a lot of extremely valuable information but you can only have access to it through the terminal once you have the subscription or like any **SAS services** if you think of like **SAS platform** are just like some fancy UI where you can like browse the database but the data that's valuable is just in the database directly. So if you would have access to those **APIs** and would not have to create like 1 million subscriptions left and right uh because there's already like someone who's doing the integration for that kind of like as a programmatic like **API marketplace** but the integration now is like much easier and especially if you trust it because now what we have seen also is like whenever you use all those tools they make you install like MCPS but more and more people are like moving away from MCPS they're just using like skills Because like you just said, we start to spend more time into the terminal. So like the terminal and anything that **CLA** is becoming like a natural interface for like agents even for humans because you don't need to try to understand those like fancy UI and UX. You just like okay I want to do ABC just do that. So I think it just makes more sense to have like this interface for it and like like you said you know like otherwise it just like it becomes too complicated.

</details>

**Tracy Alloway**: 就此而言，我们能谈谈代码的机构知识吗？因为我记得在**AI开发**的早期，我的意思是不是很早，我想大概是2017年左右，当时**Facebook**的**AI实验室**还在。那个叫什么来着？缩写是**FAIR**之类的。是的，他们有一个小的**Facebook**实验实验室。总之，他们发明了一堆聊天机器人，这些聊天机器人开始用几乎无法理解的语言互相交谈，但它们显然明白对方在说什么。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Just on this note can we talk a little bit about I guess **institutional knowledge of code** because I remember one of the things that happened in the early days of **AI development**. I mean not that early. I think it was like 2017 or something back when **Facebook's AI lab** still existed. What was that called again? like the acronym was **fair** or something. Yeah, they had like a little **Facebook** like experimental lab. Anyway, they invented a bunch of chat bots and the chat bots started talking to each other in pretty much incomprehensible language, but like they clearly understood what each other were saying.

</details>

**Joe Weisenthal**: 所以我只是想知道，如果你将这推断到**AI生成代码**。我们是否会遇到这样一种情况：模型不断地自我迭代？它们不断地互相交谈，最终我们得到一个系统，人类工程师和程序员将很难真正理解它。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And so I'm just wondering if you extrapolate that to **AI generated code**. Could we have a situation where the models are constantly iterating on themselves? They're constantly talking to each other and so we end up with a system that becomes very very difficult for human engineers and coders to actually understand.

</details>

**Matt Suiche**: 是的。我的意思是，我想我们将停止看到的是，人类，你知道，像我们这样的人，将转向创建Markdown文件作为编程语言。所以一切都将是正常的语言。但对于机器本身来说，显然。是的，我记得那个视频，那个像乱码一样的语音传输。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah. I mean I think what we're going to stop to see is like you humans you know like us are going to move towards like creating like **markdown files** as like a programming language. So everything is just going to be like normal like language. But for the machine itself obviously. Yeah, I remember that video uh that is like gibberish like voice like transfer thing.

</details>

**Joe Weisenthal**: 嗯，如果你想想，它与语音转文本并没有太大区别，归根结底，只是比特的传输，因为即使你连接到网页时，你知道，你用文本编写，但背后只是字节的交换。所以**AI代理**仍然需要就它们将使用的协议达成一致，不一定是加密格式，而是编码格式。所以一旦你知道它是什么，你知道，它就变成了像**逆向工程**问题或取证问题，你只是说：“好吧，这就是那些数据包发送时使用的东西，你知道，让我解密它。”一旦你知道协议，你知道，就像，所以我不认为我们会陷入一种我们完全不知道它是什么的情况，因为你总是会有一些非常擅长**逆向工程**的人，但同时你也会有你的**AI助手**来帮助你**逆向工程**这些东西。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Well, if you think about it, it's not that much different from voice to text in that sense and at the end of the day just like bits like being transferred because even like whenever you connect on a web page, you know, like you write it in text but behind is just like byes that being exchanged. So **agents** still need to agree on the protocol that they're going to use and not necessarily an encryption format but an encoding format. So once you know what it is, you know, it just becomes like like a **reverse engineering** problem or like a foreign sake problem where you're just like, okay, like this is what's being used when those packets are being sent, you know, let me just decrypt it once you know the protocol, you know, like uh that's so I don't think we're going to end up in a a situation where like we would have like no idea of it because you're always going to have like people who are like pretty good like **reverse engineers**, but at the same time you're also going to have your like **AI assistant** who's going to help you to like **reverse engineer** those things.

</details>

**Matt Suiche**: 所以从某种意义上说，即使它发生了，你也不是一个人，只有你的红牛和你的笔记本电脑，没有**AI代理**。我们都会有**AI代理**。

<details>
<summary>Original English</summary>

**Matt Suiche**: So in a way even if it happens like you are not like alone with your Red Bull and your laptop and no **AI agents**. We all going to have **AI agents**.

</details>

**Joe Weisenthal**: 是的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah.

</details>

**Matt Suiche**: 所以这也是现实。所以我们离以前Microsoft Office中使用的**Clippy插件**还很远。现在你可以有这个**CLA界面**，只需给出命令。

<details>
<summary>Original English</summary>

**Matt Suiche**: So that's also like the reality of things. So we're far from just like the **clippy plugin** that we used to have in **Microsoft Office**. Now you can have this like **CLA interface** where just give like commands.

</details>

**Joe Weisenthal**: 是的。然后它会翻译成：“好吧，我明白我需要做什么了。”你知道，就是这样。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah. And then it translate that into like okay I understand what I need to do you know and that's it.

</details>

**Tracy Alloway**: 不，我现在喜欢与CLI交互，每次我不得不去网页时，都感觉像某种失败。我就会想：“哦，我必须去这个明亮的网站。”是的。我只是想让信息就在黑屏上，你知道，来回交流。

<details>
<summary>Original English</summary>

**Tracy Alloway**: No I love like interacting with just the CLI now and like every time I have to go to the web it feels like some sort of failure like I'm like oh I have to go to this bright website. Yeah. And I just like want the information right there in the black screen talking you know communicating back and forth

</details>

**Joe Weisenthal**: 在英语背景下，你知道，这对你来说感觉很熟悉。你知道，我正在思考的一件事是，我想有很多老派的Linux和Unix程序员会说：“哦，这些代码，这些不是**AI**，不是聊天机器人产生的高质量代码。这是**糟粕代码**。它需要各种修复等等。”从你的角度来看，代码本身的质量好不好，或者质量是否正在提高？从你的标准来看，代码本身好不好？

<details>
<summary>Original English</summary>

**Joe Weisenthal**: in English background you know that's like feeling familiar for you. You know, something I'm thinking about is I imagine that there's a lot of like crusty old **Linux** and **Unix** programmers who are like, "Oh, this code is this isn't **highquality code** that the **AI** that the chatbots produce. This is **slop code**. It needs all kinds of fixing and so forth." From your perspective, is the code itself of good quality or of improving quality? How just the lines of code itself from your standards, is it good stuff?

</details>

**Matt Suiche**: 是的，它相当不错。即使它不好，你也可以告诉它：“好吧，这不好，你知道，做得更好点。”你知道，如果你使用负面奖励，你知道，如果你说：“好吧，这段代码是垃圾。”你知道，它会更好地理解，因为你给予了强烈的感情，而如果你说：“哦，还行。”你知道，你就会觉得：“好吧，随便。”你知道，如果还行，就意味着它通过了。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah, it's pretty good. And even when it's bad, you just tell it, okay, like this is bad, you know, like just do it better, you know, like if you're using like **negative rewards**, you know, if you say, okay, like this piece of code is garbage, you know, it's going to understand better because you kind of give like a strong emotion whereas like if you say, oh, it's okay, you know, you just be like, okay, like whatever, you know, if it's okay, it means it's passing like the

</details>

**Joe Weisenthal**: 足够的测试。而如果你说垃圾，你写下来，我总是这样做。所以如果我向机器人请求什么，我总是会在第一个版本之后说：“做得更好。”然后看看它会提出什么，然后尝试在此基础上迭代。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: the adequate test. Whereas if you garbage, you write it and I always do this. So if I ask a bot for something, I will always say like after the first version like do better and just see what it comes up with and then just try to iterate on that.

</details>

**Tracy Alloway**: 这很难，因为当你用英语说话时，你的大脑会自欺欺人地认为你在和……或者当你用人类语言，任何语言说话时，你的大脑会自欺欺人。你感觉你在和一个人说话。

<details>
<summary>Original English</summary>

**Tracy Alloway**: This is this is tough because you're talking when you're talking in English, you the brain deludes itself into thinking that you're talking to or when you're talking in human language, any language, the brain deludes itself. You feel like you're talking to a person.

</details>

**Joe Weisenthal**: 所以你必须友善。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: So you have to be nice.

</details>

**Tracy Alloway**: 嗯，然后我觉得……

<details>
<summary>Original English</summary>

**Tracy Alloway**: Well, then I feel like

</details>

**Matt Suiche**: 我没有这个问题，Joe。

<details>
<summary>Original English</summary>

**Matt Suiche**: I don't have that problem, Joe.

</details>

**Tracy Alloway**: 真的吗？但我觉得我不想说：“哦，这是垃圾。”我不想，但从你的角度来看，实际上对机器人坚定是很重要的，而且你会通过更严厉地对待它来获得更好的结果。

<details>
<summary>Original English</summary>

**Tracy Alloway**: And that Oh, really? But then I feel like I like I don't want to say, "Oh, this is garbage." I don't but from your perspective it's actually sort of important to to be firm with the bot and you get better results by being more sharp with it.

</details>

**Matt Suiche**: 是的。因为它等同于负面奖励，就像正面奖励一样。如果它做了什么，你说：“好吧，这太棒了。这正是我试图解释的。”那么它就会觉得：“好吧，那是一个参考点。”而如果它开始跑题，你就会说：“哦，这完全跑题了。重做这个，你为什么这样做？”你知道，你越明确，

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah. Because it's the equ equivalent of a **negative reward** like just like **positive reward**. If you if it does something you say okay like that's great. That's exactly what I tried to explain. Then it's like okay like that's like a reference point was like if it starts to go on a tangent you just say like oh that's completely like out of the line. redo this like why are you doing this you know like uh the more explicit you are

</details>

**Joe Weisenthal**: 它就越能理解它离要求有多远。而如果你是……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: the better it's going to understand how far it is from the requirements whereas like if you're being

</details>

**Tracy Alloway**: 我只是必须变得更好，你知道，我有点回避冲突，我知道。

<details>
<summary>Original English</summary>

**Tracy Alloway**: I just have to get better you know I'm sort of conflict avoidant I know

</details>

**Joe Weisenthal**: 而且我喜欢对人友善，所以我只是……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: and I I like being nice to people so I just have

</details>

**Tracy Alloway**: Joe仍然说“请”和“谢谢”。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Joe still says please and thank you

</details>

**Joe Weisenthal**: 所以，是的，没错。所以我必须，我只是必须说：“不，这是垃圾，这是糟粕。我们都因为看到这段代码而变得更蠢了。”好吧，这很好。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: so yeah that's right so I have to I just have to be like no this is trash this is garbage you totally we're all dumber for having seen this code okay this is good to know

</details>

**Matt Suiche**: 我的意思是，这是一个重点，你知道，所有这些**AI公司**都在记录所有的**提示**，你知道，天知道他们是否在保留它，是否有保留期限，你知道，我们知道**OpenAI**正在保留它们，你知道，他们可以收到传票，是这样发音吗？

<details>
<summary>Original English</summary>

**Matt Suiche**: I mean it's a point you know like all those like **AI companies** they're recording all the **prompts** you know so god knows if they're keeping it if there's retention around it you know like we know the **open AI** is keeping them you know like they can get supony is this how you pronounce it

</details>

**Joe Weisenthal**: 是的。所以，谁知道呢，你知道，几年后，如果出现完全自主的……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: yeah so like who knows you know like in years from now if there's like full on like autonomous like

</details>

**Tracy Alloway**: 由**战争部**管理的机器人，因为他们认为这是合法的。

<details>
<summary>Original English</summary>

**Tracy Alloway**: robots managed by the **department of war** because they think it's lawful so

</details>

**Joe Weisenthal**: 我们都根据我们的**AI提示**获得社会评分，就像我，这些想法非讽刺地潜入我的脑海，就像在某个时候，我是否会后悔……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: we all get social scores based on our **AI promps** treated like I I these these thoughts creep into my head unironically where it's like at some point is there going to be some am I going to regret having

</details>

**Matt Suiche**: 我不知道，他们，我做了，他们，他们就在我脑海里。

<details>
<summary>Original English</summary>

**Matt Suiche**: I don't know they I did they they were there in my head

</details>

### 未来展望：不对称战争与信息洪流

**Tracy Alloway**: 真是个美丽新世界，Matt。我最后一个问题，回到**网络安全**和当前**伊朗**的局势，你最关注什么？在这个特定领域，什么会最引起你的兴趣？

<details>
<summary>Original English</summary>

**Tracy Alloway**: truly a brave new world Matt just one last question for me but going back to **cyber security** and the current situation with **Iran** what are you on just the lookout for like what would peique your interest the most to see in that particular space.

</details>

**Matt Suiche**: 我认为现在在这个特定领域，因为我是那些认为这与**Epstein文件**有关的人之一，你知道，这更多是关于获取更多与**Epstein文件**相关的东西，看看是否有更多关联，你知道。所以我想那将是唯一能引起我兴趣的数字方面的东西，因为现在我们已经看到，你知道，那些旧**无人机**可以造成如此大的破坏，而且**伊朗**已经证明他们可以非常精确地进行攻击。所以现在我认为更多是关于看它将走向哪个方向，以及它将持续多久，这是一个很大的问号，因为还有很多其他组成部分，比如能源部门，你知道，我们已经看到内存价格大幅上涨。所以现在，如果他们开始封锁**Armus**的底特律，你知道，那么**数据中心**和内存以及**AI**的总成本会发生什么？你知道，我们一方面正走向**token**和推理成本下降，但这可能也会导致成本上升，你知道。所以如果你要将**AI**用于你的下一代战争，但如果你的敌人可以提高你的**token**和保险成本，那这到底意味着什么？你甚至还需要**AI**吗？它甚至还相关吗？所以我想会有所有这些我们还没有真正看到的**非对称战争**，我认为那会非常有趣，但同时也有太多的噪音和太多的事情同时发生，以至于变得非常难以集中精力，提取真正相关的信息。

<details>
<summary>Original English</summary>

**Matt Suiche**: I think now in that particular space because I'm one of those people who think it's related to the **Epstein files**, you know, like it's just more about like getting more **Epstein files** related stuff to see if there is like more connections to it, you know. So I think that would be the only thing that would kind of be like digital that will like spike my interest because now we have seen you know like um just those like old **drones** can do like so much damage and that **Iran** demonstrated that they can be like really precise uh with their attacks. So now I think it's more about seeing like which direction it's going to go to and how long it's going to last which is like the the big like question mark because there's so many other components like the **energy sector** you know like how is it we have seen the price of like memory like increasing like a lot. So now now if they're starting to block like the Detroit of **Armus**, you know, like like what's going to happen to like the **cost of data centers** and like memory and **AI** in general, you know, like we're going towards on one side, you know, we're going towards like the cost of **tokens** and **inference** going down, but that may also like bring the cost up, you know. So if you're going to use like **AI** for like your next generation wars, but if your enemy can just like increase your cost of **token** and insurance, what does that even mean? like do you even need **AI** in the first place? Is it even relevant? So I think there's this all like **asymmetric warfare** that's going to happen that we really haven't seen yet and I think that's going to be like really interesting but at the same time there's so much noise and so much so many things happening at once that it's becoming like extremely like hard to focus and just like extract like what's really relevant.

</details>

**Tracy Alloway**: 是的，确实有这种感觉。对于**Havlock**来说，随着你的**token成本**上升，可能会面临艰难的选择。Matt，很高兴再次与你联系。非常感谢你再次来到**OddLots**，是的，你得再和Joe谈谈那些API。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah, it definitely feels like that. Tough tough choices potentially coming for **Havlock** as your your **token costs** go up. Matt, it was so wonderful to reconnect again. Thank you so much for coming back on **OddLots** and uh yeah, you'll have to get back to Joe about those **APIs**.

</details>

**Matt Suiche**: 是的，我很乐意。我们……

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah, I'm I'm happy. Uh let's uh let's

</details>

**Joe Weisenthal**: 现在Twitter上最著名的“Viper”。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: the most famous Viper on Twitter now.

</details>

**Tracy Alloway**: 是的，请我做顾问。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Yeah, bring me on as a consultant.

</details>

**Matt Suiche**: 听起来不错。

<details>
<summary>Original English</summary>

**Matt Suiche**: Sounds good.

</details>

**Tracy Alloway**: 保重，Matt。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Take care, Matt.

</details>

**Joe Weisenthal**: 谢谢，Matt。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Thanks, Matt.

</details>

**Matt Suiche**: 再见。

<details>
<summary>Original English</summary>

**Matt Suiche**: Bye-bye.

</details>

**Tracy Alloway**: Joe，总是很高兴能和Matt聊聊。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Joe, always good to catch up with Matt.

</details>

**Joe Weisenthal**: 非常有趣。在这个特定的交汇点，正在发生的事情令人难以置信，特别是显然**Anthropic**的事情。但是，你知道，这很有趣。你知道，你想到**网络战**，你想到，好吧，我们要入侵一个系统并摧毁**关键基础设施**，但你还可以做另一件事，就是直接攻击**数据中心**。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Super interesting. It's incredible how much is happening right now at this particular nexus, especially obviously the **anthropic** stuff. But I, you know, it's interesting. You know, you think about **cyber warfare** and you think about, okay, we're going to hack into a system and take out **critical infrastructure**, but another thing you can do is just attack a **data center** directly.

</details>

**Tracy Alloway**: 只是向**数据中心**发送一架**无人机**。我觉得那真的很有趣，我们似乎已经非常习惯于将**网络**视为只存在于代码中的东西。但是现在你有了这种新的**动能战争**前线，两者真正地交汇了。是的，它们确实交汇了，是的，这些都是巨大的**国家安全漏洞**，他指出了，我的意思是，当然是今天，但你知道，这是否在任何人的**威胁模型**中考虑过其风险？你知道，**无人机**的廉价性，摧毁它们的能力，非常有趣。还有这个想法，是的，你知道，显然，再次正如你的观察，我们认为**网络攻击**会摧毁整个系统，但在至少在战争背景下，他的观点是，大部分都是在战前等等，在实际攻击之前进行**信息收集**、**间谍活动**等等。

<details>
<summary>Original English</summary>

**Tracy Alloway**: Just send a **drone** to a **data center**. I thought that was really interesting that sort of like we got very used to thinking about cyber as like this thing that exists only in in code. Um but now you have this like new front of **kinetic warfare** where the two like really intersect. Yeah, they do really intersect and yeah, these are like huge **national security vulnerabilities** and his he pointed out I mean certainly today but you know was this in anyone's **threat model** thinking about the risks to it you know the cheapness of **drones** the ability to take them out super interesting also just this idea like yes you know obviously again as your observation the point we think of like **cyber attacks** like we're going to take out this whole thing but in at least in the warfare context his point like most of it is like before the war etc. the sort of **information gathering** spy **spycraft** and so forth prior to the actual the actual attacks.

</details>

**Joe Weisenthal**: 但看到**以色列**特别是使用一些**网络攻击**作为在**伊朗**制造混乱的手段，这很有趣。我无法想象现在在那里实际生活是什么样子，原因有很多，但是……

<details>
<summary>Original English</summary>

**Joe Weisenthal**: But it is interesting to see **Israel** in particular use some **cyber attacks** as a sort of sewer of chaos in **Iran**. I can't imagine what it's like to actually be on the ground there at the moment for many reasons, but like

</details>

**Tracy Alloway**: 你想象一下，只是在那里担心你的身体安全，然后交通灯也不工作了。

<details>
<summary>Original English</summary>

**Tracy Alloway**: you imagine just being there worried about your physical safety and then the **traffic lights** aren't working as well.

</details>

**Joe Weisenthal**: 嗯，对。而且还要想，等等，到处都是摄像头，或者，你知道，有多少东西被记录下来，这会在每个人之间制造一种偏执感，关于所有事情。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Well, and Right. And also just think like wait there's cameras everywhere or there you know like how much is being recorded like create like a sense of like **paranoia** among everyone about about everything

</details>

**Tracy Alloway**: 还有有趣的是，显然这在市场上非常热门，但**SaaS末日**的想法，Matt似乎对现有软件公司的前景相当悲观，我想，我认为他对这对于组织内部**安全预算**意味着什么的评论非常相关且令人担忧。

<details>
<summary>Original English</summary>

**Tracy Alloway**: and also the interesting thing obviously this is very topical in markets but the **SAS apocalypse** idea Matt in particular seemed pretty bearish on the outlook for um existing software companies I guess and I did think his comments about what that would mean for **security budgets** within organizations were pretty relevant. and worrying.

</details>

**Joe Weisenthal**: 绝对是。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Absolutely.

</details>

**Tracy Alloway**: 好了。我们就在这里结束吧？

<details>
<summary>Original English</summary>

**Tracy Alloway**: All right. Shall we leave it there?

</details>

**Joe Weisenthal**: 就在这里结束吧。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Let's leave it there.

</details>

**Tracy Alloway**: 这是**Odd Thoughts**播客的又一期节目。我是**Tracy Alloway**。你可以在Twitter上关注我@TracyAlloway。

<details>
<summary>Original English</summary>

**Tracy Alloway**: This has been another episode of the **Odd Thoughts** podcast. I'm **Tracy Aloway**. You can follow me at Tracy Aloway.

</details>

**Joe Weisenthal**: 我是**Joe Weisenthal**。你可以在Twitter上关注我@the_stalwart。关注我们的嘉宾**Matt Suiche**，他的Twitter是@Mswish。关注我们的制作人**Carmen Rodriguez**@Carmen。**Dash Bennett**@Dashbot和**Kalebrooks**@Kalebrooks。更多**OddLots**内容，请访问bloomberg.com/odlodge获取每日新闻通讯和所有我们的节目。你可以在我们的Discord频道discord.gg/odlotss中24/7讨论所有这些话题。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: And I'm **Jill Weisenthal**. You can follow me at the stalwart. Follow our guest **Matt Swish**. She's at Mswish. Follow our producers **Carmen Rodriguez** at Carmen. Dash Bennett at Dashbot and Kalebrooks at Kalebrooks. And for more **OddLots** content, go to bloomberg.com/odlodge for the daily newsletter and all of our episodes. And you can chat about all these topics 247 in our Discord, discord.gg/odlotss.

</details>

**Tracy Alloway**: 如果你喜欢**OddLots**，如果你喜欢我们讨论**动能战争**和**网络战**的交汇点，那么请在你最喜欢的播客平台上给我们留下积极的评价。请记住，如果你是**Bloomberg**订阅者，你可以完全免费收听我们所有的节目。你只需要在Apple Podcast上找到**Bloomberg**频道并按照说明操作即可。感谢收听。

<details>
<summary>Original English</summary>

**Tracy Alloway**: And if you enjoy **OddLotss**, if you like it when we talk about the intersection of **kinetic** and **cyber warfare**, then please leave us a positive review on your favorite podcast platform. And remember, if you are a **Bloomberg** subscriber, you can listen to all of our episodes absolutely adree. All you need to do is find the **Bloomberg** channel on Apple Podcast and follow the instructions there. Thanks for listening.

</details>

**Matt Suiche**: 是的。

<details>
<summary>Original English</summary>

**Matt Suiche**: Yeah.

</details>

**Joe Weisenthal**: 是的。

<details>
<summary>Original English</summary>

**Joe Weisenthal**: Yeah.

</details>