---
author: New York Times Podcasts
date: '2026-11-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=i3caJRZscXk
speaker: New York Times Podcasts
tags:
  - technical-debt
  - cybersecurity
  - system-outage
  - vulnerability-patching
title: 近期全美网络与航空故障频发：AI挖出系统漏洞还是巧合？
summary: 《纽约时报》播客讨论了近期美国多起技术中断事件，包括微软邮箱故障、联邦航空局全国地面停飞、银行和美联航中断以及国家安全局机密内网瘫痪。记者指出除航空局事件源于光纤升级与路由器多播问题外，多起中断系机构紧急修补顶级AI挖掘出的底层历史漏洞所致，并非网络攻击。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Rachel Abrams
  - Dustin Volz
  - Karen DeYoung
  - Zolan Kanno-Youngs
companies_orgs:
  - Microsoft
  - FAA
  - NSA
  - United Airlines
products_models:
  - Microsoft Outlook
media_books:
  - The Daily
status: evergreen
---
### 近期全美系统中断事件接踵而至

**Rachel Abrams**: 这里是《纽约时报》[音乐]，我是雷切尔·艾布拉姆斯（Rachel Abrams），这里是《每日新闻》（The Daily）。[音乐] 最近几天，在 Anthropic 警告我们其商业模式面临的风险之一包括毁灭人类之后，一连串神秘的技术[音乐]故障接连发生。
<details><summary>Original English</summary>
From the New York Times, [music] I'm Rachel Abrams and this is the Daily. [music] In recent days, after Anthropic warned us that one of the risks to its business model included wiping out humanity, a cascade of mysterious technical [music] glitches.
</details>

>> 西南航空 2179，提个醒，
<details><summary>Original English</summary>
>> Southwest 2179, just a heads up,
</details>

>> 让飞机停飞了。
<details><summary>Original English</summary>
>> have grounded planes.
</details>

>> 我们进入了全国地面停飞状态。你是指区域性的全国，还是整个国家的全国？
<details><summary>Original English</summary>
>> We went into a national ground stop. Are are you saying national like rean national or national for the whole country?
</details>

>> 银行账户关闭。
<details><summary>Original English</summary>
>> Closed bank accounts.
</details>

>> 所以现在如果你用大通银行，你真的什么都访问不了[音乐]。
<details><summary>Original English</summary>
>> So right now if you have Chase you literally cannot access [music] anything.
</details>

>> 今天早上网络空间出现了更多麻烦，至少
<details><summary>Original English</summary>
>> There's more trouble in cyerspace this morning at least
</details>

>> 把我们所有人都关在电子邮件之外。微软 Outlook 经历重大中断，同时
<details><summary>Original English</summary>
>> shut us all out of our email. Microsoft Outlook experiencing major disruptions as
</details>

>> 万豪、国家气象局[音乐]、查尔斯·施瓦布
<details><summary>Original English</summary>
>> Marriott, the National Weather [music] Service, Charles Schwab
</details>

>> 在苹果、谷歌和国家安全局[音乐]，通常会让人觉得世界要么正在分崩离析，要么正在遭到黑客攻击，或者两者兼而有之。
<details><summary>Original English</summary>
>> at Apple, Google and the National Security Agency [music] and generally created a sense that the world is either falling apart or getting hacked or maybe both.
</details>

>> 我的意思是，如果这全都是巧合，那简直是世界历史上最大的巧合了。所以今天我们请来[音乐]我们的同事卡伦·德扬（Karen Degian/Demerian）、达斯汀·沃尔茨（Dustin Boltz/Voltz）和佐兰·坎诺-扬斯（Zolan Kano/Ko Young's），来解释我们对实际发生的事情了解多少[音乐]，我们对未来可能会有什么预期，也许他们能给我们哪怕一点点的安心。今天是11月19日[音乐]，星期四。
<details><summary>Original English</summary>
>> I mean, if this is all a coincidence, it it's like the greatest coincidence in the history of the world. And so today we turn to [music] our colleagues Karen Degian, Dustin Boltz, and Zolan Kano Young's to explain what we know about what's actually [music] happened, what we might expect going forward, and maybe they can give us just a little bit of reassurance. It's Thursday, [music] November 19th.
</details>

>> 哇，他来了。
<details><summary>Original English</summary>
>> Wow, there he is.
</details>

>> 他来了。
<details><summary>Original English</summary>
>> There he is.
</details>

>> 正准时。
<details><summary>Original English</summary>
>> Right on time.
</details>

>> 还有这位传奇人物。
<details><summary>Original English</summary>
>> And the legend.
</details>

>> 真是太抱歉了。我……呃……
<details><summary>Original English</summary>
>> I'm so sorry. I uh
</details>

>> 达斯汀，你是跑完最后两个街区过来的吗？
<details><summary>Original English</summary>
>> Dustin, did you run the last two blocks here?
</details>

>> 是的。没错。
<details><summary>Original English</summary>
>> I did. Yes.
</details>

>> 我的天啊。女士们先生们，这就是《纽约时报》记者对《每日新闻》的投入程度。
<details><summary>Original English</summary>
>> Oh my god. That is how committed New York Times journalists are to the daily, ladies and gentlemen.
</details>

>> 路上堵车很严重，而且你知道的，呃，互联网正在爆炸什么的。所以……
<details><summary>Original English</summary>
>> There was there was a lot of traffic and you know the uh the internet is exploding or whatever. So
</details>

>> 如果有哪一天可以用这个借口，那就是今天了。嗯，佐兰·坎诺-扬斯，白宫记者。你好，欢迎回来。
<details><summary>Original English</summary>
>> if there was ever a day to use that excuse, it is today. Um so Zolan Ko Young's White House correspondent. Hello. Welcome back.
</details>

>> 嘿，雷切尔。感谢邀请我。
<details><summary>Original English</summary>
>> Hey there Rachel. Thanks for having me.
</details>

**Rachel Abrams**: 卡伦·德梅扬，你报道航空等领域。欢迎来到节目。
<details><summary>Original English</summary>
**[Rachel Abrams]**: Karen Demerian, you cover aviation among other things. Welcome to the show.
</details>

>> 嗨，雷切尔。
<details><summary>Original English</summary>
>> Hi, Rachel.
</details>

**Rachel Abrams**: 达斯汀·沃尔茨，欢迎。
<details><summary>Original English</summary>
**[Rachel Abrams]**: Dustin Voltz, welcome.
</details>

>> 你好。你好。
<details><summary>Original English</summary>
>> Hello. Hello.
</details>

### 从微软故障到全美航空停飞与NSA内网瘫痪

**Rachel Abrams**: 那么，达斯汀，我想先从你开始，因为就你的报道领域而言，你对过去几天发生的所有事情可能掌握着最广泛的全局视角。你最初是什么时候意识到自己手上有一篇重大报道的？
<details><summary>Original English</summary>
**[Rachel Abrams]**: So, Dustin, I want to start with you because you probably have the broadest overview on your beat of just everything that's happened in the last few days. When did you first realize that you had a huge story on your hands?
</details>

>> 你知道的，人们总是以为我作为记者会提前知道这些事情，但事实往往并非如此。嗯，我最早知道微软中断是在……我认为那是拉开我们最近几天看到的这一系列技术故障序幕的第一场重大故障。我是从我妻子那里知道的。我自己不用微软，但我妻子用。她是一名律师。呃，我记得她很早就跟我说过……
<details><summary>Original English</summary>
>> You know, people always assume I find out about these things in advance because I'm a reporter, but the truth is that's not often the case. Um, I I first found out about the Microsoft outage, which I think was the first big one that sort of kicked off this spree of technology failures that we've seen in recent days. I learned about it from my wife. I don't use Microsoft, but my wife does. She's a lawyer. And uh, I recall her telling me early on
</details>

>> 微软 Outlook。
<details><summary>Original English</summary>
>> Microsoft Outlook.
</details>

>> 微软 Outlook。是的。我记得她告诉我：“好吧，我猜我今天不用工作了。呃，看来微软挂了。”那实际上是我第一次，呃，听说这件事。我当时老实说完全没当回事。你知道的，这种事情总会发生。话说回来，这算是过去几天我们看到的第一起类似技术中断的事件，而且微软过去也出过问题。其他主要平台过去也出过问题。这并不罕见，尽管它持续了，你知道，两三天。
<details><summary>Original English</summary>
>> Microsoft Outlook. Yeah. And I recall her telling me, "Well, I guess I'm not working today. Uh, seems like Microsoft's out." And that was actually the first time I had uh, heard about it. And I honestly didn't think anything of it. You know, these things happen. Again, this was like kind of the first one that we saw over the past few days that was like a technology outage and Microsoft's had issues in the past. Other major platforms have had issues in the past. It's not unusual even though it persisted for, you know, a couple of days.
</details>

>> 我想让我意识到正在发生某种更重大的事情——或者表面上看起来更重大的事情——是在第二天，当时美国联邦航空管理局（FAA）下令在全美范围内对所有美国境内的航班实施地面停飞。我立刻开始收到大量来自消息人士、朋友以及，呃，多年没联系的人发来的消息，说：“天哪，发生什么事了？出了这事。微软出事了。是有网络攻击吗？是伊朗吗？我们遭到袭击了吗？”
<details><summary>Original English</summary>
>> I think what clued me in that something more significant was happening or seemingly something more significant was happening was the next day when there was a nationwide ground stop ordered by the FAA of all flights in the United States. And I immediately started getting a lot of messages from sources and friends and uh people I haven't talked to in years saying, "Oh my gosh, what's going on? This happened. Microsoft happened. Is there a cyber attack? Is it Iran? Are we under attack?"
</details>

>> 而我当时毫不知情。我和家人以及一些朋友在树林里的一间小木屋里，正准备做智利炖豆牛肉晚餐。我当时有点仓促行动起来，开始问人们：“这里到底怎么了？你们知道什么？”于是我联系了政府内部的人，呃，还有其他，你知道的，多少了解情况的人，他们基本上都说：“嘿，我们不知道发生了什么，但我们没有任何迹象，没有任何情报指向外国威胁或网络攻击。这看起来不像是伊朗干的。这看起来不像是有人策划执行的行动。”
<details><summary>Original English</summary>
>> And I had no idea at the time. I was at a cabin in the woods with my family and some friends trying to get ready for a Chile dinner. And I'm sort of springing to action and start asking people, "What's going on here? What do you know?" And so the folks I reach out to in the government uh and other people who are, you know, sort of familiar with what's going on are basically saying, "Hey, we have no idea what's going on, but we have no indications, no intelligence pointing to a foreign threat, a cyber attack. This doesn't look like it's Iran. It doesn't look like it's something that someone's pulled off."
</details>

>> 对。对。对。然后到了周一，当然，我们开始看到所有这些银行中断。
<details><summary>Original English</summary>
>> Right. Right. Right. And then on Monday, of course, we start seeing all these banking outages.
</details>

>> 没错。所以银行中断很有意思。然后，你知道，同一天周一，美联航也发生了中断。这时我开始试图在自己内心进行权衡，比如，好吧，美联航这次中断很有意思，但这算不算是感知偏差？比如，是不是大家只是因为几天前 FAA 发生了中断而惊慌失措，现在我们开始注意到平时通常不会注意到的事情。所以，我试图在两者之间平衡：好吧，也许情况就是这样；对比，你知道的，好吧，确实有很多人非常担忧。这看起来也许不单单是巧合了。
<details><summary>Original English</summary>
>> Right. So the bank outage was interesting. And then, you know, the same day on Monday, there's a United outage. And this is when I start kind of trying to reckon with myself like, okay, this United outage is interesting, but is this perception bias? Like, are people just freaking out because there was the FAA outage a few days ago and now we're noticing things that we normally wouldn't notice. So, I'm trying to balance like, okay, maybe that's what's going on versus, you know, okay, there are a lot of people who are really concerned. This is seeming like maybe a little bit more than a coincidence.
</details>

>> 感知偏差，意思是说我们都看到所有这些疯狂的事情，然后基本上开始假设存在阴谋。
<details><summary>Original English</summary>
>> Perception bias, meaning like we're all seeing all these crazy things and starting to assume a conspiracy, basically.
</details>

>> 是的。然后到了周二，对我来说事情变得真正有意思了。国家安全局（NSA）——一个由数万人组成、对国家网络安全非常非常重要的机构——他们用于沟通机密信息的内部机密网络发生了故障，而那是他们绝大部分业务所依托的。它瘫痪了，他们无法开展工作，工作人员被告知错峰前往位于马里兰州的总部，与此同时该局正在努力弄清发生了什么。
<details><summary>Original English</summary>
>> Yeah. And then on Tuesday, that's when it got really interesting for me. The National Security Agency, which is a organization of tens of thousands of people who are very, very important to the nation's cyber security, had their own outage of their internal classified network that they use to communicate classified information, which is most of what they do business in. It was down and they could not operate and staff were being told to stagger their arrivals to the headquarters in Maryland as the agency worked to process what was going on.
</details>

>> 哇。需要澄清的是，我们谈论的是最秘密的政府保密机构。所以如果他们遇到了这个问题，真的会让你立刻坐直身子重视起来。
<details><summary>Original English</summary>
>> Wow. And we're talking about just to be clear, we were talking about the secretiest of the secret government agencies. So if they are having this problem, it is really making you sit up straight.
</details>

>> 是的。我是说 NSA，在华盛顿几十年来一直有个笑话，说他们是“没这机构”（No Such Agency）。呃，因为你知道他们的存在曾经是秘密，他们不会，呃，经常公开谈论，实际上只是在2013年爱德华·斯诺登披露事件之后，他们才被迫走向公众。但是的，这些人就是那种，你知道的，会入侵你电脑的神秘人物，或者我猜他们会说自己不入侵美国人的电脑，但他们入侵，你知道的，外国间谍和恐怖分子的电脑，他们对美国政府肩负着非常非常重要的国家安全使命。
<details><summary>Original English</summary>
>> Yeah. I mean NSA the joke in in Washington for decades is they're no such agency. um because you know their existence used to be secret and they don't talk uh publicly very often and really was only after the Edward Snowden revelations of 2013 they were sort of forced in the public but yes these are sort of you know the spooky types that hack your computers or I guess they would say they don't hack American computers but they hack the computers of you know foreign spies and terrorists and they have a very very important national security mission uh to the United States government
</details>

>> 你知道，我想很多人听到你在某种程度上也抱有其中一些疑问时，会觉得得到了认可。因为你知道我生活中很多人的反应——我不知道你们的生活中怎样，卡伦和佐兰——都在问我类似的事情。我至少收到了两个关于逃难应急包的问题。
<details><summary>Original English</summary>
>> you know it's I think it's going to sound quite validating to a lot of people to hear that you at least somewhat shared some of those questions because you know a lot of people's reactions at least in my life. I don't know about your lives Karen and uh Zolan were asking me similar things. I got at least two questions about bugout bags.
</details>

>> 是的。[哼笑] 特别是像本周早些时候，哪怕没有证据表明这一切都由同一个肇事者关联起来。公众确实注意到了这里的趋势，对吧？他们注意到大范围的数字化中断正在发生，似乎出现在私营部门的各个层面，甚至影响到了政府机构。大家都在问，这既是“到底怎么回事”，也是“联邦政府在哪里……”
<details><summary>Original English</summary>
>> Yeah. [snorts] Particularly like earlier this week when even if there wasn't evidence that all of this was linked by the same perpetrator. Like the public does notice a trend here, right? They're noticing that there are widespread digital outages happening seemingly in various aspects of the private sector and even impacting government institutions. And it was both questions also of like what is going on but also where is the federal government here to
</details>

>> 对，还有我应该有多害怕？是的。
<details><summary>Original English</summary>
>> right and how scared should I be? Yeah.
</details>

>> 没错。
<details><summary>Original English</summary>
>> Right.
</details>

### AI挖掘漏洞引发连锁修补：技术债与系统崩溃

>> 但同样需要明确的是，这不仅仅是某种理论上的担忧，对吧？我们已经看到许多类似的技术故障，甚至是不同程度的黑客攻击。所以你能带我们快速梳理一下这些吗，达斯汀？
<details><summary>Original English</summary>
>> But also just to be clear, it's not just sort of theoretical fears, right? We have seen a number of like technological malfunctions and even hacks of varying degrees. So can you just walk us through those quickly, Dustin?
</details>

>> 没错。我们看到美国发生的网络攻击与伊朗针对水务系统的行动有关。我们最近在法国和整个欧洲看到了制冷系统遭到攻击。因此，重大网络攻击正在发生并扰乱基本服务的说法，是我们最近亲眼目睹的事实。同时，我们看到这些顶级的 AI 模型正在互联网上无处不在的软件中发现未知的计算机漏洞（bugs）。我们距离一种名为 PHP 的编程语言中被发现漏洞才刚过去几周，而互联网上 70% 的网站都在使用这种语言。该漏洞被公布后，当时自己也在应对中断的 NSA 表示，请立即修复此问题，呃，如果无法修复，基本上应该让网站下线。我们现在看到了很多类似的情况，多亏了 AI，如果不加以解决似乎真的具有重大影响或可能产生重大影响的巨大漏洞，现在基本上每天都在暴露出来。
<details><summary>Original English</summary>
That's right. We've seen cyber attacks happening in the US that have been linked to Iran on water system. We've seen recently refrigeration attacks in France and throughout Europe. So the idea that like major cyber attacks are happening and disrupting essential services is something that we've seen happen very recently. And we also at the same time are seeing these topshelf AI models discover unknown computer bugs in software that's ubiquitous throughout the internet. We're just a few weeks removed from the discovery of uh vulnerability in a programming language called PHP which is used by 70% of websites on the internet and that came out and the NSA which has been dealing with its own disruption now at the time said please immediately fix this uh and if you can't you should basically take your website offline and we're seeing a number of episodes like that where thanks to AI enormous bugs that seem to really have significant impact or could have significant impact if they're not addressed are coming out essentially every day now.
</details>

>> 所以，好吧。这正好引出了我的下一个问题，因为大家发短信问你的一个大问题是：这些事件在某种程度上有关联吗，对吧？所以我很想知道，对于这个问题的答案，你的消息人士是怎么对你说的？
<details><summary>Original English</summary>
>> So, okay. So, this sort of leads me to my next question because one of the big questions that people have that they're texting you is are these events related in some way, right? And so, I wonder like what are your sources telling you about the answer to that question?
</details>

>> 他们基本上说情况很复杂。简短的回答是，它们似乎都没有直接关联；但更长的回答是，它们中的大多数在某种程度上是相关的。
<details><summary>Original English</summary>
>> They're saying essentially it's complicated. The short answer is none of them seem to be directly related, but the longer answer is most of them are somewhat related.
</details>

>> 以什么样的方式？稍微解释一下。
<details><summary>Original English</summary>
>> In what way? Just explain that a little bit.
</details>

>> 是的，其中很多事件——先把 FAA 的中断放一边，因为那似乎是另外一个问题。
<details><summary>Original English</summary>
>> Yeah, a lot of them putting the FAA outage aside because that seems to be a different issue.
</details>

>> 大多数其他问题似乎都与银行、航空公司——呃，美联航——以及 NSA 正在其系统中推送的软件更新有关。我想我们都遇到过这种情况：你知道的，你必须关闭 Chrome 浏览器以确保安装更新，或者你必须重启 iPhone，基本上就是，你知道的，把它关机然后再开机。因此，由于这些 AI 发现的漏洞所带来的问题，最近发生的许多事件似乎都与 AI 发现的漏洞有关。
<details><summary>Original English</summary>
>> Most of the other issues seem to be dealing with software updates that the banks, the airline, uh, United and the NSA were pushing through their system. And I think we've all been in a situation where, you know, you have to close your Chrome browser to make sure it installs the update or you have to restart your iPhone and essentially, you know, turn it off and turn it back on again. And so because of the issues that these AI discovered vulnerabilities are presenting, a lot of these recent episodes appear to be linked to AI discoveries of bugs.
</details>

>> 基本上，公司试图通过打补丁来抢在问题前面，结果却导致所有东西都崩溃了，
<details><summary>Original English</summary>
>> Basically, companies trying to get ahead of problems by patching things and then crashing everything,
</details>

>> 对吧？再次说明，这些不是网络攻击。这些不是坏人在做坏事。这些是好人试图在坏人有机会行动之前先发制人。所以这似乎就是大多数其他案例中正在发生的情况：基本上，AI 正在呈指数级发现比以往任何时候都多的漏洞，而这些漏洞是人类根本不可能发现的。这里的部分问题是许多专家所称的“技术债”，本质上就是说互联网在建造之初就根本没有考虑过安全性。从一开始安全就更像是一种事后想法，而现在你知道就像账单到期了一样，因为我们意识到许多旧代码——在某些情况下有数十年历史，就像我刚才写到的一段 Java 代码——包含着人类肉眼从未发现过的问题，但 AI 现在正在识别出来。这确实让我联想到类似于叠叠乐积木，越往底层走，就越难抽出一块积木并替换掉，因为如果你那样做而不小心，整个结构就会轰然倒塌。我认为正在发生的情况就是：你在技术栈中走得越深，就越有可能出现失误，所有东西都会崩溃。
<details><summary>Original English</summary>
>> right? And again, these are not cyber attacks. These are not the bad guys doing something bad. These are the good guys trying to get ahead of something before the bad guys have a chance to act. And so that appears to be what's going on in most of these other cases is that basically AI is finding exponentially more bugs than it's ever found before that humans could ever possibly uncover. Part of the problem here is something that a lot of experts refer to as technical debt and that is essentially the concept that the internet was not ever built with security in mind. It sort of was an afterthought from the beginning and you know sort of the bill is coming due now as we are realizing that a lot of old code you know in some cases decades old like this bit of Java code that I just wrote about contains problems that have never been spotted before by human eyes but AI is now identifying and it does remind me of sort of like a stack of Jenga blocks where the further down you go the harder it is to pull out a block and replace it because if you do that and you're not careful the whole thing will come tumbling down. And I think that's what's going down is the deeper down the technology stack you go, the more likely it is that you're going to have a slip up and everything's going to fall apart.
</details>

>> 当然。除此之外，它们发现的一些漏洞极其严重，可能使黑客能够做出各种疯狂的事情，导致系统彻底瘫痪。因此，一旦发现问题就会出现抢着修复的冲动。同时，一次性应对这么多问题也会带来一定程度的筋疲力尽。我想你现在看到的情况是：从历史上看，一家企业可能会说：“好吧，周六我们要让系统下线。没人在上班。不要登录你需要用的任何应用程序，因为我们要进行修复。”但相反，现在我们看到这些情况发生在周一、周二、周三、周四，因为存在一种紧迫感，觉得我们必须马上、立刻发布这个补丁，因为我们等不起。我们承担不起等待的代价，因为如果有人攻击我们的关键漏洞之一怎么办？
<details><summary>Original English</summary>
Sure. And in addition to that, some of the bugs are finding are extraordinarily severe things that could allow hackers to do all sorts of crazy things that could take systems down entirely. And so there's sort of a rush to fix things as soon as they're discovered. And there's a level of exhaustion as well dealing with so many problems at once. And I think what you're seeing is historically a business might say, "Okay, on Saturday we're going to take systems offline. No one's at work. Don't log into, you know, whatever app that you need to because we're going to fix it." But instead, now we're seeing these happen on Monday, Tuesday, Wednesday, Thursday, because there's a feeling, a sense of we need to get this out right away, right now, because we can't wait. We can't afford to wait because what if somebody like attacks one of our critical vulnerabilities?
</details>

>> 所以基本上你的意思是，为了避免这种情况，整个国家基本上一直在关机然后重新开机。
<details><summary>Original English</summary>
So basically what you're saying in order to avoid that, the entire country has basically been turning it off and turning it back on again.
</details>

>> 是的，我们正在经历一场群体性歇斯底里，以及全国范围内的“关机再开机”事件。我认为大致就是这么回事。
<details><summary>Original English</summary>
Yes, we're going through both a mass psychosis episode and a national turn it off and turn it back on episode. I think that's sort of what's happening.
</details>

### 白宫应对与公众恐慌

>> 哇。好吧。这既让人深感某种安心，又极其令人不安。佐兰，有一点我觉得至少在所有关于中断的新闻出来时很显眼，那就是我们几乎没有听到来自白宫的声音。感觉当大家——我想是有那么一点恐慌的时候——总统似乎有点缺席。我不是说他应该发表评论或不应该发表评论。我只是作为白宫记者有点好奇，你是否觉得他有点缺席，或者谈谈你的看法？
<details><summary>Original English</summary>
>> Wow. Okay. That is both like deeply sort of reassuring and also extremely disconcerting. Zolan, one thing that I thought was notable at least when all this news was coming out about the outages was that we didn't really hear a lot from the White House. It it felt like the president was a little bit absent when people were I guess panicking a little bit. I'm not saying he should have made a comment or should not have made a comment. I'm just sort of wondering as a White House correspondent, did you feel like he was a bit absent or just give us your take?
</details>

>> 是的，因为在某些方面他确实缺席了，对吧？他离开了这个国家，前往亚洲展开外交访问，我们知道这次访问对他非常重要，他预计将在那里与国家主席会面。但他在公众担忧上升、公众焦虑上升的时刻离开，这一点值得注意。总统在抵达亚洲时确实对此发表了评论，但他并没有确切地向公众提供清晰的解释，或者对正在发生和没有发生的事情进行事实澄清。他表现得更像是不以为然。我相信有一句话是：“这就是生活。”
<details><summary>Original English</summary>
>> Yeah, because in some ways he was absent, right? He left the country and and went on this diplomatic trip to Asia which we know is of great importance to him where he's expected to meet with President Xiinping. But the fact that he left at a time where you're seeing this rising concern from the public, rising anxiety from the public was notable. And the president did comment on this when he landed in Asia, but he didn't exactly provide a clear explanation or sort of fact check for the public what was happening and what wasn't happening. He more so was dismissive. And I believe one quote was, "That's life."
</details>

>> 嗯。这就是生活。是的。
<details><summary>Original English</summary>
>> Mhm. It's life. Yep.
</details>

>> 当你是一个强大的国家时，这种事情就会发生。这当然没有平息公众成员的焦虑。不过，自总统发表评论以来，我们看到了我认为可以形容为政府的慌乱应对。
<details><summary>Original English</summary>
>> This is going to happen when you're a powerful country. That certainly didn't quell the anxiety of members of the public. Since the president's comments, we have seen what I would describe as a scramble by the administration, though.
</details>

### FAA全国停飞事件的独立调查与成因

>> 那么，卡伦，我想知道当你在听很多这些技术中断的核心问题是什么时，我想知道这种解释在你具体报道航空领域时是否听起来可信——即面对所有这些威胁，这是一种试图抢在某个拖延已久的问题前面的主动尝试。
<details><summary>Original English</summary>
>> So, Karen, I wonder as you're hearing what the issue has been at the heart of a lot of these tech outages. I wonder if that explanation rings true to you in your coverage of aviation specifically, this idea that it was some kind of proactive attempt to get ahead of a a problem that sort of lingered for a while in the face of all these threats.
</details>

>> 嗯，你看，FAA 故事中有一部分也与尝试进行修复有关，但周五发生的全国地面停飞确实给我们留下了更多疑问而非答案，因为它似乎与该模式的其余部分并不吻合。[音乐] 我们马上回来。[音乐]
<details><summary>Original English</summary>
Well, look, there are parts of the FAA story that also have to do with trying to make fixes, but what happened on Friday with the national ground stop really left us with more questions than answers because it just didn't seem to fit the rest of the pattern. [music] We'll be right back. [music]
</details>

**Rachel Abrams**: 卡伦，过去一周我们一直听到像线路故障、L3哈里斯（L3 Harris）、Ping（探测信号）、路由器这些词，我们请你来这里的部分原因，就是想让你用浅显易懂的语言解释周末飞机到底发生了什么。你能为我们解释一下吗？
<details><summary>Original English</summary>
**[Rachel Abrams]**: Karen, for the last week, we've been hearing words like circuit failure, L3 Harris, pinging, router, and part of the reason we summoned you here is for you to explain in plain English what actually happened with the planes over the weekend. So, could you do that for us?
</details>

>> 好的，周五在阿肯色州的埃尔多拉多（El Dorado）进行了一次升级。基本上，FAA 一直在推进一项计划，将数十年来支撑空中交通管制网络的铜线替换为光纤电缆。他们大约完成了 70%，这意味着要进入全国各地的这些不同设施进行这些升级。他们往往会在夜间、较平稳的时期处理大型枢纽，但这是一家周五下午相对偏远的设施。他们以为不会出什么问题。我们需要从铜线切换到光纤，并且需要添加一个新路由器来支持新的网络功能。在完成该升级后不久，他们开始发现它发出了大量的 Ping 探测。他们在德克萨斯州阿马里洛的一个雷达设施也发现了一个问题。而这种过度活动基本上开始如同洪水般淹没系统。因此，官员们查看了这一情况，看到了这些异常现象的发生，认定他们无法弄清如何快速关闭它，于是决定直接发布全国地面停飞令，以确保他们正在追踪的技术故障不会演变成实际的事故。
<details><summary>Original English</summary>
>> So, on Friday, there was a upgrade that was being done in El Dredo, Arkansas. And basically the FAA has been trying to pursue this program of switching over the copper wiring that has been holding up the air traffic control network for decades over to fiber optic cable. They're about 70% of the way through and that means going into these various facilities across the country and making these upgrades. They tend to do the big hubs overnight, quiet periods, but this was a Friday afternoon fairly remote facility. They figured nothing's really going to go wrong. we need to switch over from copper to fiber and we need to add a new router to support the new network capability. And then shortly after that upgrade was made, they started to see that it was sending out a lot of pings. There was also an issue that they noticed at a radar facility in Amarillo, Texas. And this overactivity started basically like flooding the system. And so the officials looked at this, they saw these errant things happening, decided that they couldn't figure out how to shut it down quickly and that they were going to just issue a nationwide ground stop to make sure that the technical glitches that they were tracking would not turn into actual accidents.
</details>

>> 对。对。卡伦，我能在这里暂停一下吗，因为我想弄明白，我想我需要你把这讲得再浅显易懂一点。你提到系统接收到了大量的 Ping 信号。你能解释一下 Ping 到底是什么吗？我们谈论的是哪种信息？
<details><summary>Original English</summary>
>> Right. Right. Can I just pause here though, Karen, because I want to understand I think I'm going to need you to dumb this down a little bit more even. You mentioned that the system was getting pinged a lot. Can you just explain what exactly a ping is? what kind of information we're talking about.
</details>

>> 要理解这一切是如何运作的，你得对空中交通管制网络的布局有一张基本图景。它由许多不同的组件组成。有航路交通管制中心——一共有 22 个。它们处理高空交通。有管理进出机场流量的区域设施。然后是机场本身的塔台以及位于弗吉尼亚州的指挥中心。它们全部由一个网络连接，该网络需要能够实时传输飞机所在位置、交通状况以及天气等对管制员和飞行员确保飞行安全至关重要的输入数据。嗯。
<details><summary>Original English</summary>
>> So to understand how this all works, you kind of need a basic map of how the air traffic control network is laid out. There are a number of different components. There are airroot traffic control centers. Uh there's 22 of those. They handle the high altitude traffic. There are regional facilities that manage the flow towards airports and away from airports. And then there's the towers at the airports themselves and the command center in Virginia. They are all connected by a network that needs to be able to transfer in real time information about where planes are, what the traffic is, and other data about weather and other inputs that are important for both the controllers and the pilots to make sure they are flying safely. Mhm.
</details>

>> 但当你开始出现路由器让系统过载的情况，当一个设施——或者在这种情况下是两个设施——开始向系统充斥过多的数据 Ping，试图向通常可能不会连接的各种不同位置建立过多连接时，你基本上就开始挤占空间，网络就变得不可靠了。其最终结果基本上是：如果你是一名空中交通管制员，需要查看诸多数据中的任何一项以防止飞机靠得太近，你将无法真正看到地图，或看到天气，或看到距离，或任何其他试图传输过来的数据。
<details><summary>Original English</summary>
>> But when you start to have a router overload the system, when one facility or two facilities in this case start to just flood the system with too many data pings, with too many efforts to connect to a variety of different places that normally they might not be doing, you start to basically crowd out the space and it becomes unreliable. And the net effect of that is basically if you're an air traffic controller who needs to see any one of many things in order to make the planes not come too close to each other, you're not going to be able to actually like see a map or see the weather or see the distance or any of that other data that's trying to get through.
</details>

>> 需要明确的是，这并不是彻底的断网。但问题在于它变得不可靠，他们不确定下一个故障或下一个加载缓慢的问题会出现在哪里，而他们需要能够获取数据。因为你确实必须拥有实时数据流，他们认为这不安全。我们不知道接下来的另一只靴子什么时候会落地，我们必须彻底关闭它，以免演变成危及生命的现实事故。
<details><summary>Original English</summary>
>> This was not a total blackout. Let's make that clear. But the issue was that it was becoming unreliable and they were not sure where they were going to have the next glitch or the next slow to load issue that they needed to be able to get it. And because you really do need to be able to have that real-time data flow, they figure this isn't safe. We don't know what's going to be the next shooter or drop here and we've got to just shut it all down before it becomes an actual situation of trying to avoid a real life accident where lives would be at stake.
</details>

>> 基本上，出现全国地面停运是因为 FAA 不知道自己收到了什么信息，以及可能没收到什么信息。因此，最安全的做法就是告诉所有人不要起飞。
<details><summary>Original English</summary>
>> Basically, there was a nationwide ground stoppage because the FAA didn't know what information it was getting and what information it might not be getting. And so therefore, the safest thing to do was to tell everybody don't fly.
</details>

>> 是的。你看，在之后的几天里——我的意思是，地面停飞持续了几个小时，但在此后的几天里，整个航空业都在艰难恢复，因为有些机组人员滞留在某些地方，或者因为夜间没有睡觉而超时了。这给试图出行的人们造成了严重的积压延误。我父母就被困在里面了，他们的航班被取消了。我的意思是，这变成了一次极其广泛的出行问题。这让人们格外紧张，因为这发生在感恩节出行季即将开启的一周前。
<details><summary>Original English</summary>
>> Yes. And look, for days after, I mean, it was several hours, a few hours that this ground stop was in place, but for days after that, you really had the whole airline industry struggling to recover because there were crews that got stranded in certain places or timed out because they hadn't slept overnight. And that created real backups for people who were trying to travel. My parents got stuck in that, their flight got cancelled. I mean, it was just a very widespread travel issue. And it made people extra nervous because it happened a week before the Thanksgiving travel season was going to kick in.
</details>

>> 卡伦，你之前说过，关于究竟是什么原因导致系统过载，我们的疑问远多于答案。我想知道，目前事情已经过去近一周了。关于上周末发生的事情，我们了解到了什么？
<details><summary>Original English</summary>
>> K, you had said earlier that we have a lot more questions than answers about what exactly caused the system to be overloaded. And I wonder, we're nearly a week out at this point. What have we learned about what happened last weekend?
</details>

>> 嗯，我们知道了出问题的地方：阿肯色州埃尔多拉多和德克萨斯州阿马里洛，一个无线电设施和一个雷达设施。我们了解到只有一家承包商在负责阿肯色州的这次特定升级，并且在整个过程中都由一名 FAA 技术人员在现场监督。我们知道 FAA 并没有预料到会出现任何问题，而且我们知道他们已经查明出错的地方是相关路由器开始进行多播（multicasting）。
<details><summary>Original English</summary>
>> Well, we've learned where things went wrong. Eloro, Arkansas and Amarillo, Texas, a radio facility and a radar facility. We've learned that there was a single contractor that was working on this particular upgrade in Arkansas and that they were being physically supervised by an FAA technician through it. We know that the FAA did not expect anything to go wrong and we know that they have figured out that what did go wrong is that the router in question started multiccasting.
</details>

>> 当你说路由器时，我们说的是类似于我客厅里的那种路由器，还是？
<details><summary>Original English</summary>
>> When you say router, are we talking about a router that like what I have in my living room basically or?
</details>

>> 是的，我是说有点像，对吧？我的意思是，我们谈论的是一种不同类型的系统，但路由器的工作是接收流入的数据并将其提供给其他设备，可能是网络的其他部分。因此存在可预测的流量，当路由器做出不可预测的行为时，就会演变成淹没系统的潜在情况。而据 FAA 称，这是基于一种配置发生的，他们和承包商都没有更改或设置过该配置。我不想涉及太多技术细节，但他们目前仍然感到困惑，他们不知道这是人为错误、设备缺陷，还是安装方式出了问题。即使事情发生至今基本上已经过去了一周，这些仍然全都是悬而未决的问题。
<details><summary>Original English</summary>
>> Yeah, I mean sort of, right? I mean, it's we're talking about a different sort of a system, but a router's job is to take the flow of data that's coming in and make it available to other devices, other parts of a network potentially. And so, there's a predictable flow and when the router does something that is not predictable, it becomes a potential situation where it's flooding a system. And that apparently happened based on a configuration that the FAA says neither they nor the contractor changed or set. I don't want to get too much into the technical details, but they are at a loss right now still. and they don't know if that was human error or if that was faulty equipment or if there was something that went wrong with the way they did the installation. And those are still all open questions even though we're basically a week out from when it actually happened.
</details>

### 网络攻击传言与政界反应

>> 达斯汀，我确实想了解人们关于黑客攻击的所有疑问，因为正如卡伦所描述的，被 Ping 信号和请求等类似东西淹没。我只是有点好奇这是否看起来像可疑活动，而根据你的报道，当谈到这次地面停飞时，官方在这一具体案例中是否已经排除了这种可能性？
<details><summary>Original English</summary>
Dustin, I do wonder though about all of these questions people have about the hacking because the way that Karen is describing getting sort of flooded with pings, right, and requests and stuff like that. I just sort of wonder if that looks like suspicious activity and from your reporting, have the authorities ruled that out in this [clears throat] particular case when we're talking about the ground stoppage.
</details>

>> 官方一直表示，他们不认为网络攻击应对 FAA 中断或任何其他事件负责。当然，当你谈到异常的路由器 Ping 时，那确实可能类似于网络行为，我认为这可能会引导人们相信某些事情。但多位高级政府官员在公开场合、在电视通报会上公开发言，以及我交谈过的那些在该等机构内部不公开发表意见、而是以匿名或背景信息方式发言的人，都在表达同样的看法：他们不认为有任何证据表明这里发生的是网络攻击。你知道，这并不意味着调查已经结束。情况可能会发生改变。
<details><summary>Original English</summary>
>> The authorities have continued to say that they do not think a cyber attack is responsible for the FAA outage or any of the other episodes. Certainly, when you talk about anomalous router pinging, that can resemble perhaps a cyber activity and that is something that I think could lead people to believe certain things. But numerous senior administration officials on the record in public in televised briefings and folks that I'm talking to, you know, in these agencies who are not speaking on the record, but sort of speaking anonymously or on background are saying the same thing that they don't think there's any evidence that that is what's going on here. You know, that doesn't mean the investigation's over. Things can change.
</details>

>> 对。关于这一点，佐兰，至少从远处看，我的印象是每个人——包括白宫——都在真正拼命地试图弄清发生了什么。告诉我们你在事情发生初期的几天里了解到的有关他们应对措施的情况。
<details><summary>Original English</summary>
>> Right. To that point though, Zolan, I got the impression, at least from a distance, that everyone, including the White House, was really scrambling to try to figure out what was going on. and tell us what you have learned about their response in sort of the early days of all of this.
</details>

>> 所以，他们确实在拼命搞清楚发生了什么，同时也在试图就此确定口径，而正是后一点似乎花费了很长时间。是的，有官员站出来召开了新闻发布会——交通部长和国土安全部长——但最初的信息主要是指责拜登政府，并表示我们需要国会拨出更多资金，对吧？但在最近几天，我认为白宫和特朗普政府已经听到，这些担忧不仅仅来自民主党人。共和党参议员乔希·霍利（Josh Hawley）表示，他们需要特朗普政府提供更明确的简报。前白宫新闻秘书卡罗琳·莱维特（Karoline Leavitt）——平时很少批评特朗普政府——也表示此时需要更高的透明度。他们所表达的实际上触及了一些联邦机构的重点，以及联邦政府在此时此刻的真正作用。我现在今天大部分时间都在与国家安全官员、前国家安全官员交谈，他们描述道，你知道，在像现在这样存在信息真空的时刻，填补这一真空确实是联邦政府的职责。因为如果你不填补，公众就会用他们最糟糕的猜测去填补，对吧？肯定是黑客攻击。肯定是网络攻击，尤其是在此时政府缺乏更多信息的情况下。所以看起来他们已经开始注意到这一点了。你看到国务卿马尔科·卢比奥（Marco Rubio）站出来承认美国人的焦虑，并至少尝试对所发生的事情给出解释。呃，你看到在即将出席有关美国所受威胁的国会听证会的政府官员名单中临时增加了一人。杰伊·克莱顿（Jay Clayton）最终出席了，他算得上是特朗普总统的新“沙皇”。是这样吧？比如在涉及人工智能方面。是的，他确实喜欢沙皇。然后你还看到国土安全部长马克韦恩·穆林（Markwayne Mullin）回答不同议员的质询，但此时这些并未平息焦虑情绪。
<details><summary>Original English</summary>
>> So, they definitely were scrambling to figure out what was going on and at the same time trying to figure out a message on this and it's the latter point that seemed to take a while. Yes, there were officials that came out and held the press conference, the Secretary of Transportation and Homeland Security, but the message initially was mainly blaming the Biden administration and saying we need more money from Congress, right? But then in recent days, I think that the White House and the Trump administration has heard that these concerns are not just coming from Democrats. You've had Senator Josh Hawley, who's a Republican, say that they need a more clear briefing from the Trump administration. You had former White House press secretary Caroline Levit seldom to criticize the Trump administration who was saying that greater transparency was needed at this time and and what they're speaking to actually gets to sort of the point for some of these federal agencies and really the role of the federal government in a time like this. I've now spent really most of this day talking to national security officials, former national security officials, and they were describing how, you know, at a time like this when there's a void of information, it really is up to the federal government to fill that void because if you don't, then the public is going to fill it with their worst assumptions, right? It must be a hack. It must be a cyber attack, particularly in the void of any more information coming from the administration at this time. So, it seems like they've started to notice that. You saw Secretary of State Marco Rubio come out, acknowledge the anxiety of Americans, and provide at least an attempt at an explanation of what was going on. Uh, you saw that there was a late addition to the administration officials that were going to appear at a congressional hearing on threats to the United States. Jay Clayton ended up appearing who's sort of President Trump's new SAR. Is that right? Like when it comes to artificial intelligence. Yeah, he does love SARS. And then you also had the Homeland Security Secretary, Mark Wayne Mullen, answering from different lawmakers, but it has not calmed the anxiety at this time.
</details>

>> 正如你所说，佐兰，存在着一种压倒性的焦虑感。这一切的累积效应是一种强烈的猜疑偏执。我绝对不是唯一一个收到父母短信问“你还确定下周要坐飞机回家过感恩节吗？”的人。而在本周大部分时间都缺乏信息的情况下，我觉得唯一能让人安心的话就是：“爸，别上网了。”
<details><summary>Original English</summary>
>> And to your point, Zolan, there is an overwhelming sense of anxiety. The cumulative effect of all of this is a deep sense of paranoia. I am definitely not the only person whose parent texted them, are you still sure you want to fly home for Thanksgiving next week? And the only reassuring thing I have to say, it feels like in the absence of information for so much of this week is, "Dad, get off the internet."
</details>

>> 我不记得什么时候收到过这么多来自各行各业形形色色的人发来的信息了。他们只是很担心，对吧？过着日常生活的人问我：“发生了什么事？我还能指望医院系统和我们的电网等关键基础设施吗？”对吧。呃，目前政府似乎在说是的，但这并未平息目前如此显而易见的焦虑。
<details><summary>Original English</summary>
>> I cannot recall a time where I have received so many messages from just a wide range of people from all walks of life. People that are just worried, right? Going about their every day that are asking me, "What is going on? Will I be able to rely on critical infrastructure like hospital systems and our electric grid? Right. Um, as of now, it seems the government is saying yes, but that has not calmed the anxiety that is so apparent right now.
</details>

>> 你知道，当我观看你谈到的马克韦恩·穆林和肖恩·达菲（Sean Duffy）之间的那场新闻发布会时，他们不仅似乎在指责其他人、其他机构，而且似乎也稍微有点互相针对。你知道，我的普遍感觉是马克韦恩·穆林在归咎于达菲任内发生的事情。我认为所有这些的累积效应是：你看那种动态，当你感觉到除了向公众传达信息之外还有其他因素在起作用时，这难免会加剧人们的紧张情绪。我的意思是，你看，指责拜登政府是本届政府的常用说法，但与国会彻底闹翻并指责他们，你知道，指责他们吝啬，在你试图要更多钱的时候，是不会在国会山为你赢得任何朋友和赞赏者的。
<details><summary>Original English</summary>
>> You know, when I was watching this press conference that you've talked about between Mark Wayne Mullen and Shawn Duffy, not only did they seem to be blaming other people, other agencies, but they also seem to have kind of turned on each other a little bit. You know, I got a general sense that Mark Wayne Mullen was blaming things that had happened under Duffy. And I think the cumulative effect of all of that is you look at that dynamic. And when you get the sense that there's sort of other dynamics at play beyond just getting information to the public, it makes sense that that might, I don't know, underscore people's nerves. I mean, look, blaming the Biden administration is a common refrain with this administration, but picking a real fight with Congress and accusing them, you know, of being stingy is not going to win you any friends and admirers in Capital Hill
</details>

>> 当你试图争取更多资金的时候。
<details><summary>Original English</summary>
>> when you're trying to ask for more money.
</details>

>> 没错。而且他的做法确实激怒了共和党人和民主党人。所以这只会制造更多一点的混乱。无论是出于无意，还是出于真正糟糕的判断，这其实都不重要，因为其最终结果是：它真的没有平息观众的紧张情绪，也没有让他们觉得政府能掌控局面、真正能够推进修复工作。
<details><summary>Original English</summary>
>> Correct. And the way he went about it has really turned off Republicans and Democrats. And so that is just sewing a little bit more chaos. Whether some of it was inadvertent or some of it was just real bad judgment, it doesn't really matter because the net effect was that it really did not calm the nerves of the viewers and did not leave them with a sense that the government's got this and that they're going to actually be able to forge ahead with a fix.
</details>

### 未来展望：AI驱动下的数字阵痛期与“技术大流行”

>> 嗯。鉴于你们三位告诉我们的关于导致这些问题的原因——由于 AI 的存在而以极快的速度试图防止任何漏洞大白于天下。AI 短期内不会消失，看起来不会消失，对吧。所以我只是有点好奇，我们现在是否正处于这样一个时期：过去一周我们所看到的在某种程度上成了新常态。佐兰，除非你有什么重大想法想在这里补充，否则我想请达斯汀做最后的总结。
<details><summary>Original English</summary>
>> Mhm. Given everything that the three of you have told us about what has been driving these issues, this warp speed attempt to prevent any vulnerabilities from breaking out into the open because of AI. AI is not going away anytime soon. it does not appear right. And so I just sort of wonder if we might be in this period right now where what we've seen the last week is kind of the new normal. And Zolan, unless you have a a big thought you want to add here, I'm going to go to Dustin for a final word.
</details>

>> 让达斯汀说吧。我都讲完了，挺好。
<details><summary>Original English</summary>
>> Go to Dustin. I've given all good.
</details>

>> 我……我同意。跳过佐兰的重大想法。嗯，你知道，整件事一直非常引人入胜，因为一方面，解决我们所有人都在谈论的这些问题的唯一方法，就是引起公众的关注。而通常情况下，这只有在发生重大灾难后才会发生。值得庆幸的是，在过去的几天里并没有发生这种情况。没有人丧生。所以，我有一种冲动想告诉人们冷静下来。你知道，要把事情放在宏观角度来看，比如，你知道的，你仍然可以访问你的银行账户。航班仍然在起飞，也许有时会延误，
<details><summary>Original English</summary>
>> I I agree. Skip Zolan's big thoughts. Um, you know, this whole thing has been so fascinating because on the one hand, the only way you're going to fix these problems that we're all talking about is by sort of seizing public attention. And typically, it only happens after a major catastrophe. Thankfully, that hasn't happened in the past few days. No one has died. And so, I have this impulse to tell people to calm down. You know, that put things in perspective like, you know, you're able to still access your banking accounts. The flights are still leaving. Maybe sometimes they're delayed,
</details>

>> 但事实是这些问题将会持续存在。随着先进 AI 的飞速演进，我们可能会继续看到更多类似的问题，即漏洞被发现并得到修复。而在修复它们的同时，系统会被迫下线。这甚至还没有触及到那个问题：你知道的，黑客会利用他们发现的这些工具做些什么？因此摆在我们面前的将是一段坎坷的旅程。我认为与我交谈过的那些非常聪明的人说，你知道，未来 12 到 18 个月对科技行业来说可能会极其艰难。他们的意思是，AI 正在现代计算机基础设施的技术栈古老代码中暴露并找出所有这些问题，而由于我们没有重视安全，我们已经忽视了这些代码数年甚至数十年。互联网在构建时就没有考虑到安全问题。因此 AI 将能够找到这些问题，并有望修复它们。而在经历过这些之后的某个阶段，有望迎来一个更安全、问题更少的互联网。
<details><summary>Original English</summary>
>> but the truth is that these problems are going to persist. And with the rapid acceleration of advanced AI, we're probably going to continue to see more issues like this where bugs are being found and fixed. And while they're being fixed, systems are taken offline. And that even gets before, you know, the question of, you know, what are the hackers going to do with these tools that they discover. So there is going to be a bumpy ride ahead of us. I think the folks I talked to who are really smart say you know the next 12 to 18 months for technology it could be extremely difficult. And what they mean by that is AI is surfacing and identifying all of these problems in ancient code in the technical stack of modern computer infrastructure that we've neglected for years or decades because we have not addressed security. The internet was not built with security in mind. And so AI is going to be able to find these problems and hopefully fix them. And at some point on the other side of that is going to be hopefully a much more secure internet with fewer problems.
</details>

>> 现在唯一需要说明的是，非常聪明的人在至少过去 8 [音乐] 到 10 个月里一直对我说，要注意接下来的 12 到 18 个月，而且这个时间跨度一直没有改变。
<details><summary>Original English</summary>
Now the one caveat to that is people who are really smart have been telling me look out for the next 12 to 18 months for at least the last 8 [music] to 10 months and the time horizon doesn't change.
</details>

>> 但如果你是个乐观主义者，这会给你一些可以寄托希望的东西，那就是，你知道的，把它想象成一场大流行病。你知道，随着我们发现所有这些新问题，我们现在正在经历这场技术故障的大流行。希望在另一端，是一个接种了更强疫苗、在技术上[音乐]更加安全的互联网。
<details><summary>Original English</summary>
But if you're an optimist, that gives you something to hold on to is that, you know, think of it like a pandemic. You know, we're going through this pandemic of technology failures right now as we're discovering all of these new problems. And hopefully on the other end of that is a much more inoculated, technologically [music] safe internet.
</details>

**Rachel Abrams**: 达斯汀，非常感谢你以乐观的基调结束本期节目。佐兰和卡伦，非常感谢你们两位来到这里。
<details><summary>Original English</summary>
**[Rachel Abrams]**: Dustin, thank you so much for ending this episode on an optimistic note. And Zolan and Karen, thank you both so much for being here.
</details>

>> 谢谢[音乐]你。
<details><summary>Original English</summary>
>> Thank [music] you.
</details>

>> 非常感谢。
<details><summary>Original English</summary>
>> Thank you so much.
</details>

>> 谢谢你，雷切尔。
<details><summary>Original English</summary>
>> Thank you, Rachel.
</details>

### 今日其他要闻与演职员名单

>> [音乐] 我们马上回来。
<details><summary>Original English</summary>
>> [music] [music] >> We'll be right back.
</details>

>> 以下是你今天还需要了解的其他新闻。特朗普总统[音乐]、中国领导人和俄罗斯总统弗拉基米尔·普京周三在中国深圳微笑着握手致意，几个小时前，特朗普总统在机场受到了包括拥抱在内的个人欢迎。[音乐] 在三方峰会前夕，这三位世界领导人展现出的友好姿态，与他们在一些世界上最紧迫问题上的[音乐]分歧立场形成了鲜明对比，包括核军控、[音乐]获取先进 AI 芯片以及乌克兰战争的未来。
<details><summary>Original English</summary>
Here's what else you need to know today. President Trump, [music] Xi Jinping of China, and Russian President Vladimir Putin greeted each other with smiles and handshakes on Wednesday in Shenzen, China, hours after President Trump received a personal airport welcome from Xi that included a hug. [music] The shows of friendliness by the three world leaders on the eve of a trilateral summit contrasted sharply with their [music] divergent stances on some of the world's most pressing issues including nuclear arms control, [music] China's access to advanced AI chips, and the future of the war in Ukraine.
</details>

>> 众议院民主党人以压倒性多数投票提名纽约州众议员哈基姆·杰弗里斯[音乐]在民主党于 1 月接管国会控制权时出任议长。此举使他有望成为首位担任众议院最高领导职务的黑人议员[音乐]，该职务在总统继承顺序中位列第二。[音乐] 杰弗里斯曾面临一些对民主党建制派感到厌倦的进步人士的抵制，但没有人[音乐]站出来挑战他。
<details><summary>Original English</summary>
And an overwhelming majority of House Democrats voted to nominate Hakee Jeff, [music] the New York representative, to be speaker when the party assumes control of Congress in January. The move puts him in line to become the first black lawmaker [music] to hold the House's top leadership role, which is second in line to the presidency. [music] Jeff has faced some resistance from progressives who have been fed up with the Democratic establishment, but no one [music] emerged to challenge him.
</details>

>> 本期节目由杰克·达多罗（Jack Dadoro）、克里斯·本德列夫（Chris Benderev）和阿兰布·克罗普基（Arab Cropki）制作。[音乐] 由 MJ·戴维斯·林（MJ Davis Lynn）和迈克尔·贝努瓦（Michael Benois）编辑。包含玛丽安·洛扎诺（Marian Lozano）和丹·鲍威尔（Dan Powell）创作的音乐，由艾丽莎·莫克斯利（Alyssa Moxley）进行音频工程混音。我们的主题音乐[音乐]由 Wonderly 创作。以上就是今天的《每日新闻》。我是雷切尔·艾布拉姆斯。明天见。[音乐]
<details><summary>Original English</summary>
Today's episode was produced by Jack [music] Dadoro, Chris Benderev, and Arab Cropki. It was edited by MJ Davis Lynn and Michael Benois. It contains music by Marian Lozano and Dan Powell and was engineered by Alyssa Moxley. Our theme music is [music] by Wonderly. That's it for the Daily. I'm Rachel Abrams. See you tomorrow. [music]
</details>