---
author: a16z
date: '2026-06-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ktl8mNiWqMM
speaker: a16z
tags:
  - artificial-intelligence
  - automation
  - software-development
  - technology-adoption
title: 本尼迪克特·埃文斯论AI发展、编程应用落地与技术浪潮的演进
summary: 本尼迪克特·埃文斯在播客中探讨AI演进，指出编程成为当前显现产品市场契合度的首个用例，但模型商业价值、赢家归属及向更广泛经济领域扩展仍存疑问，认为AI变革终将如历史浪潮般化为理所当然的技术底座。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Benedict Evans
companies_orgs:
  - a16z
  - OpenAI
products_models:
  - ChatGPT
media_books:
  - AI Eats the World
status: evergreen
---
<!-- chunk 1/9 -->

Agentic coding 从有点用变成了真正改变一切。它曾经像是魔法。而在二十年之后，我们只会说：“嗯，事情理所当然就是这样。计算机历来就是这么干的。”

<details><summary>Original English</summary>
Agentic coding went from being kind of useful to really changing everything. It was going to be magic. And in 20 years time, we'll just say, "Well, of course that's how it is. Computer's always done that."
</details>

>> 每年，硅谷都在等待本尼迪克特·埃文斯（Benedict Evans）的演讲发布。作为前 A16Z 合伙人，他撰写着业内阅读量最高的通讯之一，也是《AI Eats the World》背后的思想者。

<details><summary>Original English</summary>
>> Every year, Silicon Valley awaits Benedict Evans presentation. Former A16Z partner, author of one of the industry's most read newsletter, The Mind Behind AI eats the world.
</details>

>> 我们处在这种极度稀缺的状态中。比如，我们无法每年在 AI 基础设施上花费 10 万亿美元，因为根本就没有每年 10 万亿美元摆在那里供我们花在它上面。

<details><summary>Original English</summary>
>> We are in this extreme scarcity. Like, we can't spend $10 trillion a year on AI infrastructure cuz there isn't$10 trillion a year there to spend on it.
</details>

>> 你论点中很大的一部分，是模型最终会变成大宗商品（commodities）这个想法。我不认为基础模型是一个产品。我不认为聊天机器人是一个产品。我认为价值会更靠上。

<details><summary>Original English</summary>
>> The big part of your thesis is this idea that models are going to end up as commodities. I don't think foundation models are a product. I don't think a chatbot is a product. I think the value will be further up.
</details>

>> 解释一下关于它们是什么、看起来像什么背后的逻辑。

<details><summary>Original English</summary>
>> Explain the reasoning that they're a bit in what they look like.
</details>

>> 大概有三到四个可以摆在桌面上的积木块。其中之一是——

<details><summary>Original English</summary>
>> There's like three or four building blocks you can put on the table. One of them is
</details>

### 开篇与过去一年的变化

>> 本尼迪克特，欢迎回到 a16z 播客。

<details><summary>Original English</summary>
>> Benedict. Welcome back to the Acing Z podcast.
</details>

>> 谢谢。

<details><summary>Original English</summary>
>> Thank you.
</details>

>> 上次你来这里时，我们讨论了你演讲《AI Eats the World》的最初版本。呃，你知道，从你写下它至今差不多有一年半了。在这个节点，我们——你总是以“那些大问题是什么”来开启你的演讲，但这次在探讨未来有哪些问题之前，我很好奇，我希望你先反思一下，自你最初制作那个演讲以来，我们学到了什么，有哪些情况已经显现，呃，让我们回顾一下——

<details><summary>Original English</summary>
>> Last time you were here, we were discussing the first iteration of your presentation AI use the world. Uh you know, you since wrote it almost a, you know, year and a half ago. At at this point we're get you always begin your presentation with your you know what are the big questions but I'm curious this time first before getting into the what are questions going forward I want you to reflect on what have we learned since you originally uh made the presentation what's played out um and let's reflect back on
</details>

>> 过去一年发生了什么变化。我认为，我们对分化的产品策略有了多得多的认知，对那种超越“仅仅用更多算力更快做出更大模型”的竞争紧张局势有了多得多的认知。呃，特别是 OpenAI 的战略经历了数轮迭代，从昨天的“同时做所有事情”，到“哎呀不，也许我们应该在编程上加倍下注”。呃，显而易见，agentic coding 开始见效了，因此科技界的所有焦点都在一定程度上极度收窄到了这上面，认为它具有绝对的产品市场契合度（product market fit），那种“客户正从你手里抢走它”的感觉。呃，并且，呃，当然那伴随着围绕产能的供应紧缺，以及我们目前看到的供需、产能、资本支出与定价之间的价格失衡。呃，所以这算是很大的转变，比如我们曾经历过一段时期，觉得“这有点管用，也挺令人兴奋，但我们不太确定要拿它做什么”，变成了“对，它在编程上奏效，呃，它在其他事情上行得通吗，比如行，几乎肯定行，但这正是眼下起效的东西”，所以那就变成了——我们有了这种狭窄得多的焦点。呃，在其他方面，呃，你知道，图表上的数字在不断上涨，模型不断变大，资本支出不断增长，使用量不断增加，人们用得更多。但两三年前你可能会有的大多数根本性问题，其实并没有答案。比如我们不知道模型领域是否会出现一个赢家。我们不知道它们能否捕获技术栈上层的价值。我们不知道模型能做到多少。呃，以我们目前拥有的技术，我们看不到消费者每天使用而不是每周使用它的途径。所以所有所有这些问题依然悬而未决。

<details><summary>Original English</summary>
>> what's changed in the last year so I think we have much more of a sense of diverging product strategy we have much more a s of a sense of kind of competitive tension that goes beyond just make a bigger model faster with more about more more compute. Um we've had several iterations of open AI strategy in particular from sort of everything all at once yesterday to oops no maybe we should double down on coding. Um clearly agentic coding started working and so all the focus in tech has kind of narrowed in massively onto that as something that has absolute product market fit in the sense that like the customers are pulling it out of your hands. Um and um and of course that comes with the supply crunch around capacity and price imbalance imbalance of supply demand capacity capex pricing that we see at the moment. Um so that's kind of the big shift like we had a moment of like this is kind of sort of working and kind of exciting but we're not quite sure what we're going to do with it to like right it works for coding um will it work for anything else like yes almost certainly but that's what's working right now and so that's become we've got this kind of much narrower focus. Um otherwise um you know the chartman numbers keep coming up, the models keep getting bigger, the capex keeps growing, the usage keeps growing, people using this more. But most of the sort of fundamental questions you might have had two or three years ago didn't really have answers. Like we don't know if there'll be a winner in the models. We don't know if they can capture value up the stack. We don't know how much the models can do. Um we don't see a way that consumers will use this daily rather than weekly with the technology we have right now. So all all of those questions are still open.
</details>

### 为何编程成为首个爆发用例

>> 是的。仅仅就编程而言，我们本能弄清楚、我们本能预见到那会是真正爆发的用例吗，或者对此有什么样的反思？

<details><summary>Original English</summary>
>> Yeah. And just on on the on the coding, how could could we have figured could we have foreseen that that would have been the the the use case that really would have taken off or what's sort of a reflection on that?
</details>

>> 嗯，宿命论地看，你本可以说，看看是谁在折腾这些东西？软件开发者。软件开发者会试图让什么起效？软件开发。呃，所以你知道，在一个非常朴素幼稚的层面上，嗯对，最先起效的东西理应是软件开发，就像我经常把这个时刻比作 1997、1998 年左右的互联网，但它也像 80 年代初或 70 年代末的个人电脑。它极其令人兴奋，但并不是很清楚它是用来干什么的，而且它目前也还不算完全管用，显然人们用个人电脑做的第一件事就是制造计算机。呃，而人们用大语言模型做的第一件事——在某种意义上，大语言模型就是计算机——就是制造更多算力。呃，所以这并不是非常出人意料。我认为转变发生在今年年初，很明显 agentic coding 从有点用变成了真正改变一切。而且我不确定你能——很显然曾有人会说，“嗯，这绝对能做到任何事情”。于是他们会说，“嗯是的，看吧，我早就告诉过你了”。呃，但我认为没有人本可以确定性地预测出那到底会在何时发生，以及最先起效的会是编程。

<details><summary>Original English</summary>
>> Well, um you deterministically you could have said, well look who's messing about with this stuff? Software developers. What are software developers going to try and make work software development? Um so you know at a very kind of simplistic naive level well yeah the stuff that should work is software develop first is software development just as like kind of I often compare this moment to like the internet in like 9798 but it's also like the PCs in the early 80s or the late '7s. It's incredibly exciting but it's not quite clear what it's for and it doesn't quite work yet and clearly the first thing that people did with PCs was make computers. Um, and the first thing that people are doing with LLMs, in a sense, LLMs are computers, is to make more compute. Um, and so that's not terribly surprising. I think the shift is been at the beginning of this year clearly that agentic coding went from being kind of useful to really changing everything. And I'm not sure you could have you clearly there were people who were going to say, well, this is going to be able to do absolutely anything. And so they will say, well, yes, look, I told you. Um, but I don't think anyone kind of kind of could have deterministically predicted exactly when that was going to happen and that it was going to be coding it would work first.
</details>

### 对工程师和团队结构的影响

>> 那么关于——多谈谈这对工程师、初级工程师、高级工程师意味着什么，以及就业层面的讨论、团队如何组织等等。到目前为止我们学到了什么？

<details><summary>Original English</summary>
>> And and what have we learned about sort of uh, you know, say more about what this means for engineers, junior engineers, senior engineers, sort of the the jobs discussion, how teams are organized, uh, etc. What have we learned so far?
</details>

>> 我不认为我们学到了任何东西。我是说，你知道，这六个月前还行不通。

<details><summary>Original English</summary>
>> I don't think we've learned anything. I mean, you know, this this didn't this didn't this didn't work six months ago.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 每个人都在手忙脚乱地试图弄明白这意味着什么。而且你知道，你很容易陷入到噪音和细节中去，比如昨天某人在聚会上说了什么。于是就成了“天哪，以后全都得这么运转了”。呃，你知道，这需要几年时间才能尘埃落定。你知道，就算只考虑定价因素也是如此，你知道，我们在需求和供应之间承受着巨大的挤压，定价也因此受影响。呃，所以我们不知道，你知道，一个团队将会是什么样子。我认为人们正在提出新的问题，围绕——你知道，显而易见的那个问题是，你知道，你还会雇佣初级人员吗？如果雇，他们在做什么？你过去为什么雇佣初级人员？你当时雇他们真的是去做他们实际做的那件事，还是雇他们去做别的事情？所以如果你把过去由人来完成的一类事情自动化掉了，那么会发生什么？而在软件开发中，这在现在变得实在得多了，因为你确实正在将一堆过去由人来做的事情自动化。所以那些问题现在成了现实问题，而不是理论探讨。但我认为任何人都不可能说自己了解市场结构将会是什么样，或者三年后软件工程师的职业生涯会是什么样。我认为如果你觉得你现在就能知道那个，那你简直是疯了。

<details><summary>Original English</summary>
>> and everyone is scrambling around trying to work out what it means. And you know, you can get very very into the noise and the detail and what did somebody say at a party yesterday. So, oh my god, that's how it's all going to work. Um, you know, it's going to take a couple of years for this all to settle down. You know, if nothing else because of the pricing, you know, we've got this enormous crunch between the demand and the supply and hence the pricing. Um, so we don't know what, you know, what a team is going to look like. I think people are asking new questions around, you know, the sort of the obvious one of, you know, do you hire junior people and if so, what are they doing and why were you hiring junior people in the past and were you actually hiring to do the thing that they did or were you hiring them to do something else? And so if you automate away a class of stuff that used to get done by people, then what will happen? And that's sort of becomes much more real now in software development because you actually are automating a bunch of stuff that used to be done by people. So those questions are kind of now rather than theoretical. But I don't think anybody can possibly say they kind of know what the market structure is going to look like or what the career of a software engineer is going to be in three years time. I think it would be you'd be insane to think that you could know that yet.
</details>

### OpenAI 与 Anthropic 的策略演变

>> 是的。谈谈 OpenAI，谈谈最让你感到惊讶的是什么，或者你是如何理解他们类似战略发展演变的，以及他们未来面临的问题。

<details><summary>Original English</summary>
>> Yeah. the talk about uh open AI uh talk about what's most uh surprised you or how have you kind of made sense of their sort of strategy development and and the questions that they have going forward.
</details>

>> 嗯，你知道，那里历来都是一个如此宁静、毫无戏剧性冲突的环境。所以，你知道，它——而且你知道，显然他们遇到了 Fidji Simo 不得不休病假的问题，呃，这在一定程度上打乱了局面。看，显然在去年的下半年、最后一个季度，他们的问题是“好，模型就是这些模型了，但还有什么？我们如何让人们用它来做其他事情？你知道，向 ChatGPT 询问 15 个关于我们可以在基础设施之上构建什么价值的想法，然后我们把它们全都做一遍”。这几乎就是它实际呈现出来的样子。接着，呃，呃，筹集资金较少的 Anthropic 说了：“不，我们要专注于编程。”然后他们把编程做通了。呃，那究竟是一个深思熟虑的策略，还是他们误打误撞碰上的，这得由别人来说，但显然那是奏效了。然而问题依然存在。就像是，眼下起效的东西是软件开发，以及在一些其他领域的一些事情，接着有很多人对于在边缘场景使用它、在某些事情上使用它感到兴奋，而且在那些买了，你知道，一组 Mac Studio 整天运行 open claw 的硅谷人群，与，呃，你知道，那些说“对，它有点用，呃，我上周用它干了点事”的另外 40% 的人群之间，显然存在着非常广泛的差距——

<details><summary>Original English</summary>
>> Well, you know, it's always been such a such a a tranquil drama-free environment. So, you know, it's and you know, obviously they've had the issue with with with Fiji Simo having to take a medical leave um which kind of shuffled things up a bit. Look, clearly the second half, last quarter of last year, this their question was right, well, the models are the models, but what else? And how do we get people to do other stuff with this? You know, ask chat GP GPT for 15 ideas for what we could do to build value on top of infrastructure, and then we'll do all of them. It's almost literally what what it looked like. And then um um Anthropic with having less capital raised said, "No, we're going to focus on coding." And they got coding working. Um whether that was like a deliberate strategy or kind of they stumbled into it is you know for other people to say but like clearly that worked but the question kind of still remains. It's like the stuff that's working right now is software development and some things in some other fields and then there's a lot of people who are kind of excited about using this around the edges and using this for some things and there's clearly this kind of very widespread between people in the valley who bought you know a cluster of Mac studios and are running open claw all day versus um you know those other 40% of people who say yeah it's kind of useful um I used it last week for something
</details>

<!-- chunk 2/9 -->

我就想，你该如何跨……如何跨过那道坎？而且我不觉得……软件行业确实跨越了那道坎，而很多其他领域的人还在纳闷，只在一定程度上用用它。还有许多地方，大企业用它来自动化某些具体的后台流程，并不要求用户自己去琢磨拿这个新工具来做什么，而是直接说：好了，这里有个问题我们可以解决。你知道，我和美国以外以及科技行业以外的公司聊，和顾问、投资人聊。

<details><summary>Original English</summary>
and I'm like how do you br how do you bridge that and I don't think that question you soft software is a place where that's really really bridge jumped over that bridge and I don't think and then there's a lot of other places where people are kind of scratching their heads and using it up to a point and then there's a lot of places where corporations are using it to automate some like specific back office process where you're not asking the user to work out what they do with the new tool instead you're saying okay here's a problem that we can solve and you know I go and talk to, you know, companies outside America and outside of tech and talk to consultants and um, you know, investors.
</details>

他们关注的是那些针对单一问题的点状解决方案。比如两三天前，我跟一家大宗商品公司交流，他们想用大语言模型更好地预测现金流，因为他们跟各种各样的小生产商打交道，未必清楚发票什么时候能结款，而且这是个利润率非常非常低的行业。所以这是件大事，因此他们想用大语言模型做好现金流预测。这跟去打开 ChatGPT 或者 Claude 说“嘿，帮我总结一下这周的会议”是截然不同的两码事。

<details><summary>Original English</summary>
They're looking at those one at a time point solutions. Um, so like I'm speak couple of days ago to a commodities company and they want to use LLMs to get better predictions on their cash flow because they deal with all sorts of small producers and they don't necessarily know when their invoices are going to get paid and it's a very low low margin business. So that's a big deal and so they want to use LLMs to get better cash flow forecasting. That's very different thing from kind of going to catch EBT or Claude and saying hey you know give me a summary of my meetings this week.
</details>

### 与移动互联网及历代平台的采纳对比

>> 是的。你能分享一下这与移动端或者其他平台相比如何吗？就早期用户采纳，也就是周活或日活用户方面而言。

<details><summary>Original English</summary>
>> Yeah. H can you share how uh how did this compare with mobile um or other sort of platform in terms of you know use user early user adoption on on sort of the you know weekly or daily user.
</details>

>> 我觉得回答这个问题有很多不同的角度。其中之一是，我们始终是站在巨人的肩膀上，增长始终在复合累积。因此，移动端不必去等待互联网或蜂窝网络……比如移动数据。移动互联网确实多少得等蜂窝数据，但它不需要等互联网从无到有地出现，互联网不需要等个人电脑出现，个人电脑也不需要等消费电子和半导体等等。所以技术的采纳一直在加速。你知道，当你老板——也是我的前老板——马克·安德森做网景的时候，整个地球上只有几千万台个人电脑。所以，你不可能拥有 9 亿周活跃用户，因为当时根本就没有 9 亿台 PC。所以这种加速是一直存在的。这是第一点。

<details><summary>Original English</summary>
>> So I think there there's there's there's a bunch of different ways to answer this. One of them is like we're always standing on the shoulders of giants and the growth is always compounding. So mobile didn't need to wait for um the internet or cellular networks like mobile data. Mobile internet didn't need to wait for it kind of needed to wait for cellular data but it didn't need to wait for like the internet to happen and the internet didn't need to wait for PCs and PCs didn't need to wait for consumer electronics and semiconductors and so on. So you've always got this accelerating adoption and you know when when when your boss my old boss Mark Andre was working on Netscape there were like doubledigit millions of PCs on the entire planet. So like no you couldn't have 900 million weekly active users because there weren't 900 million PCs. So there's always that acceleration. So that's one point.
</details>

我觉得第二点是，在任何这些转折的早期阶段，事情具体要怎么运转其实并不明朗，而且什么东西都动不动就出故障。我刚好年纪够大，还记得那些事。我不知道你年纪多大，但是三十几岁的人其实不太记得那个时代了——在当时，你正工作着，屏幕上的一切突然卡死，你只能爬到桌子底下拔掉电脑电源插头，然后祈祷过去一小时做的事情还能保留下一部分，这在当时完全是家常便饭。现在这种事已经绝迹了。

<details><summary>Original English</summary>
I think the second point is like at the early stage of any of these shifts it's not really clear how it's going to work and nothing works. So you know like I'm just about old enough to remember this. I'm not sure how how how old you are, but like, you know, anyone in their 30s doesn't really remember a time when it was completely normal that you'd be working and then everything on the screen would just freeze and you just have to crawl under your desk and unplug the computer and then pray that like some of what you done in the last hour might still be there. That just doesn't happen anymore.
</details>

回到 80 年代，你想买块声卡，要花 300 美元。你的电脑要想发声，好，花 300 美元，然后得搭上一整个周末去把它弄好。我记得当时为了把这些东西弄跑起来有多费劲。互联网也是一样，你得找张装了 TCP/IP 的软盘，网速又慢，你想做的事情很多都根本不存在；移动端也是如此。我们现在差不多就处在那个阶段，当然，谁也看不清这些东西到底哪一个能成。现在也是一样，浏览器能成吗？会是这个，还是会是那个？这一切要怎么组合在一起？在极度令人兴奋的事物与极少数愿意投入精力让东西跑起来的人之间，存在着一道鸿沟，把这些转变成普通人随手按个按键就能用的东西，需要跨过这个鸿沟。

<details><summary>Original English</summary>
And go back to, you know, the 80s and like you bought a sound card. Well, that's $300. You won't have sound on your computer. Okay, that's $300 and it's like a that's the weekend to make that work. I mean, I remember this trying to get this stuff to work. And the same thing with the internet, like you know, you've got to get a floppy disc that has TCP IP on and you know, it's slow and none of the stuff that you need to do existed and the same with mobile. And we're kind of at that stage and of course it's not clear which of these things are going to work. And that's the same thing now like a browser's going to work, is it going to be this? Is it going to be that? How's this all going to fit together? And there's a gap between what's incredibly exciting and the small number of people who are willing to put the work in to get something to work and just turning that into a thing where you can just press a button in real hands.
</details>

### 定价危机与价值捕获：电信网络与大模型

我认为这里的第三点，也是一个更加切实的观察：我们前面提到的定价紧缩，在我看来很像 2009、2010 年移动数据领域发生过的情况。一方面，人们突然收到 5000、10000 美元的流量账单；另一方面，如果是固定包月流量——这有点像美国 iPhone 刚推出时的情形，AT&T 联合 Cingular 推出 iPhone 时采用了固定包月资费，结果不幸的是大家都买了 iPhone，随后用上了 3G，人们开始看 YouTube，整个网络直接瘫痪了，因为他们根本没有足够的容量来承载。有意思的是，科技界至今还有人不明白蜂窝网络是有边际成本的，运营商必须扩容，而这需要花更多钱。于是网络运营商不得不手忙脚乱地让成本曲线与……让定价体系与底层成本匹配，并与用户感知到的价值相匹配，他们后来主要是通过封顶套餐、公平使用原则和限速等等手段做到的。

<details><summary>Original English</summary>
I think the the third point point here is and you know there's a much more tangible observation is that the the pricing crunch that we've already mentioned looks to me a lot like what happened with mobile data instead of 200910 where um suddenly people got bills for like5 $10,000 of data on the one side and on the other hand if you had flatweight data which is kind of what happened in the US with the iPhone the AT&T launches AT&T singular launched the iPhone with flatweight data and then unfortunately ely everybody buys iPhones and starts and then they get 3G and people start watching YouTube and the whole network goes down because they just don't have capacity to do that. It's funny, there are still people in tech who don't understand that cellular networks have have marginal cost and like they have to add more capacity and that costs more money. And so the networks kind of had to scramble to get like the cost curve aligned with the infrastruct the pricing system aligned with the underlying cost and aligned with perceived value which they kind of did with with with capp bundles and fair use and throttling and so on.
</details>

但另一面则是……而这正是你现在能看到的：一方面，你每月付 20 美元，就能得到价值 1 万美元的 token；另一方面，你瞎折腾了几天，就收到了一张 1 万美元的账单，你会想“这到底搞什么鬼？”你现在真的能看到这些报道。这与 2008、2009、2010 年发生的事情如出一辙，也很像 2001、2002、2003 年 GPS 发生过的情况。

<details><summary>Original English</summary>
But the other side of that com and that's exactly you know you where you see now it's like on the one hand you're paying $20 a month and you get 10 grand worth of tokens and on the other hand like you know you messed about for a couple of days and you get a bill for 10 grand and you're like what the hell is this? Um that's exactly what you know you see little literally see these stories now um which is exactly what happened in kind of 2009 8 9 10 also what happened in like 2001 and 2 and three with GPS
</details>

但我认为这个类比或对比中另一个有意思的部分在于：从那时起，移动数据流量增长了大概一千五到两千倍，移动网络运营商总共坐拥约 1 万亿美元的收入，每年投入约 2000 亿美元的资本开支，而股票整整横盘了 20 年，所有酷炫的东西全都是别人做出来的。而他们当初差不多都以为所有酷炫的东西会由自己来做。比如我以前在一家拥有银行牌照的电话公司工作过，因为他们觉得他们能做移动银行——现在看来这简直太疯狂了。但这恰恰切中了核心：他们建造了极其精巧、极其昂贵的全球基础设施，使用量一直保持巨大增长，它改变了我们所有人的生活，我们所有人都在为它付钱，但他们自己却没有从中赚到钱，因为所有价值都向上转移到了技术栈的上层。

<details><summary>Original English</summary>
um but I think the other interesting part of that analogy is or that comparison is that since then mobile data traffic has risen by something like one and a half to 2,000 times and the mobile networks collectively have revenue of about a trillion dollars and they spend about 200 billion dollars a year on capex and the socks have been flat for 20 years and all the cool stuff got built by somebody else and they kind of all thought that they were going to build all the cool stuff like I worked for a phone company that had a banking license because they thought like they would they would do they would do mobile banking um which now seems absolutely insane um but that's kind of the point is they built this amazing piece of global incredibly sophisticated very expensive global infrastructure with enormous growth in use all the time and it changed all of our lives and we all pay for it and they didn't make any money from it because all the value moved up stack
</details>

正如我刚才所说，这当然是大语言模型绝对核心的问题：究竟是模型本身能包办一切，还是你必须在模型之上构建 300 个应用？你可以直接找模型说“帮我把税报了”，还是说你需要一个在内部可能以 10 种不同方式使用某些 AI 的报税工具？如果不是模型包办一切，那么作为基础模型提供商又算是什么？这是否只是按边际成本出售的大宗商品级基础设施？现在大家似乎很难理解这个概念，因为你生产多少 token 就能卖出多少，所以你可以按投入产出比来定价。但在接下来的几年里，我们将有大概 1 万亿到 2 万亿美元的资本开支陆续落地，模型效率每年都在提升 100 倍、200 倍，接着又会有新模型出来；至于模型消耗的 token 是会更多还是更少，无论如何我们都会达到一个新的平衡。而当所有模型都大同小异、用同样的芯片做着大同小异的事情时，凭什么这样一个平衡会让模型公司拥有定价权？他们凭什么会有定价权？

<details><summary>Original English</summary>
and this is of course absolutely as I said earlier this is the absolutely central question for for LLMs is can the model do the whole thing or do you have to have 300 apps built on top of it can you just go to the model and say do my taxes for me or do you need to have a tax thing that uses that might use some AI in 10 10 different ways inside it um and if not then what is it to be a foundation model provider is this just commodity infrastructure that gets sold at marginal cost which is somehow seems to be a very difficult concept for people to grasp right now because you can sell all the tokens you can make so you can price it at ROI but over the next couple of years we've got like a trillion2 trillion dollars of capex coming down the pipe and the models get 100x 200x efficient more efficient every year and then there's new models and will the models use more tokens or less tokens but wherever like we'll get to a different equilibrium and why would that equilibri would be one where the model companies have pricing power when the models are all kind of the same doing kind of the same thing with the same chips why would they have pricing power
</details>

我觉得这就是……回答你的问题扯得有点远了，但你回头看看历史，芯片公司没有捕获到价值，网络服务提供商没有捕获到价值，移动网络运营商没有捕获到价值。Windows 和 iOS 捕获到了，但它们做的是另一回事，它们拥有向上整合技术栈的各种杠杆。当然，它们还拥有模型所不具备的网络效应。所以核心问题就在于：它们最终会沦为基础设施层，还是会终

<details><summary>Original English</summary>
and I think that's so it's a long answer to your question but you know you go back and look over time like chip companies didn't capture the value um ISPs didn't capture the value mobile network operators didn't capture the value Windows and iOS did but they were doing something else they were they had all these levers to go up the stack back. Um, and of course they have network effects which models don't have. So that's sort of the the question is do they end up like the infrastructure layers or do they end
</details>

<!-- chunk 3/9 -->

向上像操作系统层那样，并攫取价值，嗯，并且真正决定要构建什么，还是他们最终……我的意思是，当然，那里的讽刺之处在于网景（Netscape）。马克·安德森（Marc Andreessen）当年有一句名言，说他要把 Windows 变成一套调试拙劣的设备驱动程序。然后微软有点强行挤进了这个市场，但事实证明网页浏览器并不是关键所在，因为所有的价值都在别的地方。所以我觉得，关于这局面最终如何定型，更多是这种纷繁交织的疑问，这又直接回到了我对你那个问题的所有回答上。就像是，你知道其中的一部分东西，但你不知道它究竟会如何运转。

<details><summary>Original English</summary>
up like the operating system layers and capture value um and actually get to decide what gets built or do they end up I mean the irony of there of course is Netscape where um you know Mark Andre famously said that he was going to turn Windows into a set of badly debugged device drivers and um then Microsoft kind of crowbar their way into the market but it turned out that web browsers weren't the point because all the value was somewhere else and so I think that's kind of the more the kind a swirling mass of questions about how this settles out, which comes back right through to all all my kind of answers to your question. It's like, you know, some of this stuff, but you don't know how it's going to work.
</details>

>> 是的。是的。目前还不清楚它究竟更像，你知道，互联网，还是某种……你知道，软件，在那里很多价值或仅仅是更好的利润率发生在应用层；抑或是某种云，在那里它似乎……你知道，曾经存在于硬件层。目前到目前为止，看起来英伟达以及往上走，看起来呃他们拥有更好的利润率，并且正在获得大量的价值，但目前还不清楚这是否会……你知道，保持不变，或者是否呃会有各种应用程序，呃你知道，我们是否会看起来更像互联网。呃你究竟该如何着手去预测，你知道，针对……针对这个问题的答案？

<details><summary>Original English</summary>
>> Yeah. Yeah. It's unclear whether it looks more like the, you know, internet or sort of um you know, software where where a lot of the value or just better margins happen at the application layer or sort of the cloud where it seems the you know, where sort of existed at the hardware layer. And right now so far it seems like Nvidia and going you know up it seems like uh they have better margins and are curing a lot of the value but it's unclear if that will you remain the same or if u there will be sort of applications uh you know if we'll look more like the internet h how would you even begin to predict you know the answer to to s
</details>

### 技术的周期与不可预测性

>> 嗯，那么对此有两个层面的回答。我的意思是，有各种各样关于历史如何演进的名言，而你知道我最喜欢的一句是：历史除了教会我们总会有事情发生之外，什么也没教会我们。而且你知道，你总是可以事后诸葛亮地说，嗯，事情当然会这样发展，但这在当时通常并不是显而易见的。特别是，我记得你知道大约在 15 年前，科技界很多非常非常聪明的人看着 iPhone 和 Android，然后说，你知道，这又是开放对封闭，Android 将会彻底碾压 iPhone。当然事情并不是这样发展的，随后我也可以去解释为什么，但是你知道，所有这些、所有这些对比都是有用的，却没有一个是具有预测性的。

<details><summary>Original English</summary>
>> well so so two answers to this I mean there's all these sorts of quotes about how history works and you know my favorite one is history teaches us nothing except that something will happen and you know you can always expose factor say well of course it worked out like that but it was generally wasn't obvious at the time and you know in particular I remember you know like sort of 15 years ago a lot of really really clever people in tech looked at the iPhone and Android and said you know this is open versus closed again and Android is going to crush the iPhone which of course isn't what happened and then I can go and explain why but you know all of these all of these comparisons are useful none of them are predictive
</details>

嗯，而且你知道，事后看总是显而易见的。我……你知道，这很有意思，我……我最近录了几期播客，并且发布了这个演示文稿，关于这些东西有一类评论，大意是说：“你知道，本尼迪克特（Benedict），你没有尽到你的职责，你应该告诉我们将会发生什么，你应该做出预测，而你似乎所做的就只是说‘嗯，我们不知道’。”这其实存在两方面的问题：其一，在很多地方我其实确实说了，比如我认为这个不会奏效，我认为它会像那样运转，比如我认为基础模型不是产品，我认为聊天机器人不是产品，我认为价值会处在更上层。

<details><summary>Original English</summary>
um and you know it's always obvious in hindsight I you know it's funny I I' I've done a couple of podcasts recently and I've published this presentation and there's like a there's like a a class of comment on this stuff which is to say you know Benedict you're not doing your job you're supposed to tell us what's going to happen you're supposed to make predictions and all you seem to do is say well we don't know and there's kind of two problems with that one of them is there's a bunch of class of places where I actually do say like I don't think this is going to work I think it's going to work like that like I don't think foundation models of a product I don't think a chatbot is a product I think the value will be further up
</details>

但这一点的另一面是，当你处于周期的这个阶段时，存在着很多条路径，而你并不知道它会是其中的哪一条路径。如果硬要试着说，“嗯，我认为会是那一条”，你可能是对的，但你确实必须意识到这有多大的不确定性，以及它可以走向多少条不同的路径。嗯，这就是周期中这一阶段的本质：一切都还悬而未决。你知道，当我们到达 S 型曲线向上弯曲并收窄的节点。你知道，曾经有过一个时刻，Windows Phone 或许本可以成功。事后来看，不，它大概是不可能成功的。但是你知道，曾经有过一个时刻，移动领域究竟会如何发展并不明朗。然后到了一个时刻，情况变得很清楚了：对，事情就是这样了。现在，我们转向下一个问题。科技的特征之一就是，当你理解了某件事物、明白了它是如何运转以及将发生什么的那一刻，就是你应该转向其他事情的时刻。

<details><summary>Original English</summary>
but the other side of this is like when you're at this stage in the cycle you there's there's there's many paths and you don't know which of those paths it's going to be. And to try and say, well, I think it's going to be that one is, you know, you might be right, but you do have to kind of be conscious of of like how uncertain this is and how many different paths it could take. Um, that's the nature of this part of the cycle is all bets are open. You know, we get to the point where the scurve kind of curves up and it narrows in. And, you know, there was a moment when, you know, Windows Phone might have worked. In hindsight, no, it probably wasn't going to work. But, you know, there was a moment when it wasn't clear how mobile was going to work. And there's a moment where it was clear, right, this is what's happening. Now, we move on to next quest. The next question. One of the characteristics of tech is that the moment that you understand something and you know how it works and what's going to happen is the moment you should move on to something else,
</details>

你应该永远去寻找那些我们不知道答案的地方，因为，你知道，我已经大概五年没有更新我的苹果电子表格了，因为我们已经知道发生了什么。他们赢了。比如我不在乎明年的……今年……你知道今年的 iPhone 长什么样。我……我不关注他们在中国市场的份额，就像是，它已经尘埃落定了。下一个问题。

<details><summary>Original English</summary>
you should always be looking for the places where we don't know what the answers are because, you know, I haven't updated my Apple spreadsheet in like five years because we know what happened. they want like I don't care what the next year's what what what you know this year's iPhone looks like. I I don't pay attention to their market share in China like it happened. Next question.
</details>

>> 你提到了那个预测，即你不认为基础模型是产品，你认为它会往上走。稍微解释一下那里的……那里的推论，以及那可能会是什么样子。

<details><summary>Original English</summary>
>> You mentioned the prediction of you don't think foundation models are are the product you think it'll move up. Explain that that that the re the reasoning there there a bit and what that could look like.
</details>

### 基础模型与产品形态

>> 所以我认为有三四个可以摆在桌面上的积木模块。其中之一是，嗯，目前并不清楚你该如何构建出一个在某种可持续的、差异化的方式上从根本上优于其他所有人模型的模型。这似乎并不存在网络效应。似乎也没有你可以拉动的杠杆，以及 Instagram 所在、YouTube 所在或谷歌搜索所在的那种策略。而在大语言模型（LLM）上，我们看不到与此等同的东西。现在你会有不同的侧重点。你知道，也许这个比那个更好，也许你喜欢这一个多于那一个，但除了你花钱的意愿之外，模型之间似乎不存在某种根本性的差异化、根本性的竞争差异。

<details><summary>Original English</summary>
>> So I think there's like three or four like building blocks you can put on the table. One of them is that um it's not clear how you could build a model that was fundamentally better than everybody else's model in some sort of sustainable differentiated way. There isn't doesn't seem to be a network effect. There doesn't seem to be sort of levers you can pull and a strate where Instagram is or YouTube is or Google searches. And we don't see an equivalent of that for LLMs. Now you have different emphasis. you know this maybe this one's better than that maybe you like this one more than that but there doesn't seem to be a sort of fundamental differentiation fundamental competitive difference between the models except your willingness to spend money
</details>

嗯，第二个问题是，聊天机器人本身就像是一种奇怪的、有限的 1.0 版用户界面。在某些事情上、对某些人以及某类任务中，它确实非常好用，但在绝大多数其他情况下，你需要一整套其他东西：你需要工具链，它需要被正确配置。它需要拥有正确的数据，需要被配置和控制，拥有合适的用户界面，而且需要有人真正坐下来思考过这应该如何运作。因为通常来说，擅长使用工具和做好需要该工具的工作的人，与擅长决定该工具应该做成什么样的人，并不是同一批人。所以，你知道，非常非常擅长设计印刷出版物的人，不应该是去创建和设计工具的人。那是另一套技能组合。而且你知道，非常非常擅长提供财务建议的人，并不是设计 TurboTax 的合适人选。那些是拥有不同技能的不同人群。

<details><summary>Original English</summary>
um second problem is the chatbot itself is like a kind of a weird limited v1 UI and there's some things and some people and some kind of task where it works really well but there are most of the others you need a bunch of other stuff you need tooling and it needs to be set up right. It needs to have the right data and it needs to be configured and controlled and have the right user interface and people need to have kind of sat down and thought about how this should work because generally people who are good at using the tool and doing the job that needs the tool are not the same people who are good at deciding what the tool should be. So you know people who are really really good at you know designing print publications are not the people who should create and design. That's a different set of skills and you know people who are really really good at doing financial advice are not the right people to design Turboax. Those are different people with different skills.
</details>

所以，嗯，你目前有点在这中间摸索。所以你现在有了，你知道，用于这个的 Claude，用于那个的 Claude，而且你有了 skills 等等。对我来说，这有点像……嗯，一个问题是，究竟由谁来构建 skill？另一个问题就像是，嗯，你知道，这看起来有点像你在 Excel 中点击“文件-新建”所得到的东西，比如这些都是模板，它们能带你走这么远，但在某个特定节点，你知道，人们就会超出模板的范围。嗯，在我的演示文稿里有一张幻灯片，那是多年前有人在 Twitter 上对我说的一句话，你说他们是一名顾问，一半的工作是告诉用 Excel 的人去使用数据库，而另一半工作是告诉用数据库的人去使用 Excel。

<details><summary>Original English</summary>
So um and you have kind of groping around the middle of this. So you now have you know Claude for this, Claude for that and you have skills and so on. To me this is kind of like well one question is well who builds the skill? Another question is like well you know that seems to be a bit like what you get if you do file new in Excel like these are templates and they'll take you so far but a certain point you know people outgrow the templates. Um there's a slide in my presentation which is a quote from that somebody said to me on Twitter years ago you said they were a consultant and half of the jobs were telling people who used Excel to use a database and the other half were telling people who used a database to use Excel.
</details>

所以存在这么一个模糊而多变的领域：你究竟是需要专用软件？需要水平软件？还是需要垂直软件？但你不可能把所有事情都放在 Excel 里做。总会有，你知道，你知道我们都见过靠着一个 10MB 的 Excel 文件来维持运转的部门。现在，我是在 Numbers 里经营我的业务，但也是在电子表格上，然而在某一个节点，比如你会超出它的能力范围。

<details><summary>Original English</summary>
So there's this kind of fuzzy swirly place of like do you need dedicated software? Do you need horizontal software? Do you need vertical software? But you can't just do everything in Excel. There's always, you know, you know, we've all like seen the department that runs along on a 10 megel file. Now, I run my business in numbers, but on a spreadsheet, but like there's a certain point where like you outgrow that. Um,
</details>

嗯，顺着这个逻辑推下去，那么，模型实验室能构建所有这些东西吗？嗯，当然不能。就像微软或苹果不可能去构建每一个 Windows 应用或每一个 iPhone 应用一样。那么接下来，模型实验室拥有杠杆吗？他们是……他们是 Windows 吗？他们是 iOS 吗？再次说到，嗯，存在网络效应吗？比如如果你现在是一家律师事务所，你购买了一款软件，比如你知道，看 a16z 投资的所有那些企业级软件，嗯，那家律师事务所、制造公司或银行有多大几率会说：“噢，那这个是用 Claude 还是用 OpenAI？因为我们……我们是统一基于 Claude 实行标准化的。”嗯，不，事情不再是那样运作的了，正如当初在云计算领域也不那样运转一样——比如你不会说：“嗯，你知道，我们公司在 AWS 上实现了标准化”，比如你甚至都不知道什么公司……什么……什么……

<details><summary>Original English</summary>
and so following that on, well, can the model labs build all of that? Well, of course not. No more than like Microsoft or Apple could build every Windows app or every iPhone app. So then, do the model labs have leverage? Are they are they are they Windows? Are they iOS? And again, well, is there a network effect? Like if you're a law firm right now and you buy a piece of software like you know do the C all the pieces of enterprise software that A6Z is invested in um how often does like the law firm or the manufacturing company or the bank say oh well does this use claude or does it use or open AAI because we we standardize on claude well no that's not how it works anymore than worked like that for cloud like you didn't say well you know our company standardized on AWS like you don't even know what company what what
</details>

<!-- chunk 4/9 -->

### 基础模型与半导体类比

云……那……那……那 SaaS 产品是在……这就是核心所在，它被抽象掉了，它不是你的……

因此，基础模型似乎更像那样。在这层意义上，它们看起来更像超大规模云厂商（hyperscalers），因为它们没有……你知道，它们可能具有竞争优势，但在堆栈更上层，你没有杠杆，你没有网络效应，你没有控制力。嗯，这顺便促使我说，好吧，也许这里恰当的类比是半导体，每一代都变得越来越昂贵，所以玩家越来越少。

<details><summary>Original English</summary>
cloud that that that SAS product one is on that's the whole point it's abstracted away it's not your And so the foundation models seem to look more like that. They seem to more look more like the hyperscalers in that sense in that they don't have you know they might have competitive advantages that further up the stack you don't have leverage you don't have a network effect you don't have control. Um that sort of prompts me to incidentally to to say well maybe the right comparison here is with semiconductors where with each generation it just gets more expensive and so you have fewer players.
</details>

嗯，所以把所有这些综合起来看，好吧，模型有点像不同的大宗商品（commodities），聊天机器人并不是正确的 UI 或合适的产品，而各家公司也无法自己构建所有那些东西。所以，它们是底层基础设施。那么接下来，好吧，它们拥有定价权吗？嗯，你将会有——随便选个数字——三到六家公司制造前沿模型（Frontier model），每年花费——没人知道，没有任何诚实的人知道——大约 2000 亿美元到 2 万亿美元来构建这些模型。此外，还会有大量的边缘端和开源。那么这将在哪里稳定下来呢？

你可能会有差不多半打公司都在竞相销售这些东西。那么价格纪律将从何而来？特别是当其中一些公司还拥有完全不同的其他商业模式时，比如你所知道的 Google 销售广告，所以他们对定价的态度与 OpenAI 不同。

<details><summary>Original English</summary>
Um, so all of that kind of taken together, well, the models are kind of diff commodities and the chatbot isn't the right UI or the right product and the companies aren't going to be able to build all of that stuff themselves. So therefore, they're low-level infrastructure. And so then, well, do they have pricing power? Well, you're going to have, pick a number, three to six companies making a Frontier model, spending no one knows, no one honest knows, like something between $200 billion and $2 trillion a year on building these models. Plus, there'll be a bunch of edge and a bunch of open source. So where's this going to settle down? you're going to have as it might be half a dozen companies that are all competing to sell this stuff. And so where is the price discipline going to come from? Particularly when some of them have got like whole other business models as well like you know um Google selling ads so you know they've got a different attitude to pricing to to open AI.
</details>

### 短期供需失衡与移动数据教训

嗯，所以我觉得这里的挑战在于，我们目前所处的阶段与最终应有的格局之间存在差异，这有点像大一经济学学生的对话。

目前我们正处于供求、价格以及资本支出和产能极度不平衡的时期。但仅仅因为对 token 的需求是无限的，并不意味着你不能达到不同的价格平衡，因为移动数据当时发生的情况当然就是如此。比如对比特（bits）的需求是无限的，在过去 15 年里增长了 1500 到 2 倍。但你仍然迎来了你的供求价格平衡，并且在世界上大部分地区电信运营商之间仍然爆发了极其惨烈的价格战，因为从根本上说，你是在向那些会来回切换的人销售一种大宗商品，当然开发者也会来回切换。

<details><summary>Original English</summary>
Um and so like I think the the challenge here is like there's a difference between where we are right now and where this should end up which is kind of a first year economics student kind of conversation. Right now we're in this period of extreme dis equilibrium of supply and demand and price and capace and capacity. But just because demand for tokens is infinite that doesn't mean that you can't get to a different price equilibrium because of course that's what happened with mobile data. Like demand for bits is infinite. It's grown 1500 2x in the last 15 years. But you still got your supply and dem price equilibrium and you still got a murderous price war between Telkos in most parts of the world because fundamentally you're selling kind of a commodity um to people who will swap back and forth and of course developers will also swap back and forth.
</details>

现在，你知道，我很乐意承认这可能完全是错的。可能我们会进入这样一个世界：只有两家公司能够制造 LLM，并且它们拥有定价权；或者我们进入一个我们所做的大部分事情都被吸纳进模型的世界，或者它们在堆栈更高层拥有杠杆。嗯，你知道，这有点像我对 iOS 与 Android 的看法。仅仅因为你可以说“好吧，过去三次都是那样运作的”，这并不能证明——不能证明这次会发生什么。但这并不意味着你至少不应该去提出这些问题，而且你肯定——我只想把它作为一种初步观察：眼下的情况是暂时的。你知道，我们正处于这种极度稀缺的状态，然后我们有一个定价系统，我们有一个自由市场，我们迎来资本支出的激增，比如上万亿美元的资本支出。所以那些倍数会发生变动，然后呢？

<details><summary>Original English</summary>
Now this is you know I'm happy to say that this might be completely wrong. It may be that we we we get to a world in which there's only two companies that can make an LLM and they have pricing power or we get to a world in which most of what we do gets subsumed into the model or they have leverage further up the stack. Um, and you know, it's kind of my point about iOS versus Android. Just because you can say, well, it worked like that the last three times, that doesn't prove that it's what tell prove what's going to happen this time. But it doesn't mean at least you should sort of ask the questions and you should certainly I'll just say as a sort of a primary observation like this situation right now is transitory. You know, we're in this extreme scarcity and then we have a pricing system and we have a free market and we have a surge of capex and like a trillion dollars of capex. So like those multiples are going to move around and then what
</details>

>> 回到你……你……这是个很好的过渡，承接你早些时候提出的观点，比如“嘿，你知道，我们知道，你知道苹果……苹果一号”。下一个问题，作为过渡，你最关注的接下来的一些问题是什么，或者你知道我们最应该关注什么？

<details><summary>Original English</summary>
>> going back to your your it's a good segue to your point you made earlier of like hey you know we know you know Apple's Apple one next question to to as a segue what are some of the next questions that you're most focused on or that you know we should be paying most attention to.
</details>

### AI 边界的外移与行业内部重构

所以我想回答的一种方式是，我们已经谈过的一些问题，比如模型能走多远、模型是否能分化等等。我认为另一个显然是，我们在什么节点上会看到越来越多类型的用例，在这些用例中模型已经足够好，我们不需要云端最昂贵、最快、最大、最沉重的模型，而且你可以使用较旧的模型，你可以使用开源模型，你可以让模型在设备端运行？显然这就是苹果几周后要谈论的内容。你知道，你能把多少东西推向设备端，那里的算力是免费的，或者对你来说无论如何是免费的，对开发者而言没有边际成本。

<details><summary>Original English</summary>
So I think one way to answer what so so some of the questions we've already talked about like well how far do the stand do the models go can the models differentiate and so on I think another is obviously is is at what point are there do we see more and more classes of use case where the models are good enough and we don't need the most expensive fastest biggest heaviest model in the cloud and you can use an older model you can use an open source model you can have a model running on device obviously this is what Apple's going to be talking about in a couple of weeks um you know how much can you push onto the device where the compute is free or free to you anyway doesn't have marginal cost for the developer.
</details>

另一个经典的问题是，这个问题几乎就像是脱离了技术本身。因此，如果你观察一家律师事务所，或者一家咨询公司，或者一家投资银行，或者基本上任何专业服务领域，在那里你传统上拥有这种金字塔结构，而你可以把金字塔底层人员所做的大部分工作自动化，那会发生什么？在那里你唯一能说的是，如果你从未在律所工作过，或者从未在贝恩、波士顿咨询、麦肯锡工作过，可能对这是如何运作的不会有很好的概念，因为你可能并不真正知道所有那些初级员工（associates）在做什么，你也不真正知道客户付费买的到底是什么，以及这些事情会如何重新配置。

<details><summary>Original English</summary>
Another classical question is it's almost like the question is move out of technology. So if you're looking at a law firm or a cons consultancy um or an investment bank or basically anyone in professional services where you traditionally have this pyramid structure and you can automate a great chunk of what the people at the bottom of the pyramid were doing, what happens and the only thing you can say there is if you have never worked at a law firm or never worked at Bane BCG McKenzie probably not going to have a good idea of how this works because you probably don't really know what it is that all those associates are doing and you also don't really know what it is that the client is paying for and how do those things kind of get reconfigured.
</details>

嗯，所以比如 AI 对金……这对金融意味着什么，无论是在内部招聘结构方面、你能创造的产品种类方面，还是在利润率结构方面？这对咨询顾问意味着什么？这对四大、对三大、对埃森哲、对大型律所，以及对广告业意味着什么？你可能大概能知道其中的一些问题。嗯，但如果你不在那个行业，你并不真正知道答案。这让我联想到很多我在 a16z 时写过的一篇东西，我称之为《内容不是国王》（content isn't king）。我也写过一篇说“Netflix 不是一家科技公司”。我想要表达的观点是，如果你看看 Netflix，这整件事是由科技行业构建的东西所赋能的。但关于 Netflix 的所有问题都是洛杉矶的电视问题，比如什么节目、多少节目、什么类型的节目、你应该付给艺人多少钱、你应该把目标定在拿奖吗、你应该拍电影吗、你应该购买体育转播权吗、哪种体育？这些全都是洛杉矶的问题，这些不是旧金山的问题。比如在旧金山根本没有人知道正确的问题是什么。它们是媒体行业的问题。这就是我的观点，所有对 Netflix 而言重要的问题都变成了媒体行业的问题。这显然也是围绕特斯拉的巨大分歧点：它是一家汽车公司，还是一家科技公司？

<details><summary>Original English</summary>
Um, and so like well what does AI mean for fin what does this mean for finance both for that that internal like hiring structure and the kind of products you can create and like the margin structure? What does it mean for consultants? What does it mean for the big four for the big three for Accenture um for big law firms um and for advertising? and you kind of probably can know some of those questions. Um, but if you're not kind of in that industry, you don't really know the answers. The thing this reminds me a lot of is there something I wrote when I was at A6C, which I called content isn't king. And I also wrote something that said Netflix isn't a tech company. And the point I was kind of getting at is that if you looked at Netflix, this whole thing is enabled by stuff the tech industry is built. But all the questions for Netflix are are TV LA questions like what shows, how many shows, what kind of shows, what should you pay the talent, should you aim for awards, should you do movies, should you buy sports, what kind of sports? These are all Los Angeles questions. These are not San Francisco questions. Like no one in San Francisco even knows what the right questions are. They're media industry questions. And this was kind of my point that that that that all the questions that matter to Netflix have become media industry questions. You this is obviously the great tension point about Tesla. Is it a car company? was it was technology company.
</details>

### 与以往平台转型的物理限制差异

嗯，所以我想要表达的是，你知道，这些东西对法律意味着什么，在很大程度上是属于律师的问题，或者是属于那些非常了解律所及其运作方式、初级人员实际在做什么、以及客户实际从他们那里购买什么的人的问题。同样的事情也适用于比如生成式视频对好莱坞意味着什么？比如，你知道，本·阿弗莱克（Ben Affleck）可能比我懂得多得多。他创办了一家公司，并以大约 1000 亿……1 亿美元的价格卖掉了它。所以显然他确实懂，但你知道，那是第二类问题，即问题移到了 AI 之外，它们变成了可以说是半 AI、半其他领域的问题。

嗯，然后是第三层，我认为——我可能早些时候就该说明这点——所有这些与以往平台转型根本不同的地方在于：在 3G、iPhone 或互联网等等出现时，你不知道接下来会发生什么，但你知道物理限制。比如，你知道 1995 年你知道电信运营商下周不会给全世界每个人都提供宽带，并且你知道全世界每个人都不会跑出去买一台 PC，因为一台 PC 要花大约 3000 美元。所以，你大致知道可能发生和不可能发生的基本物理限制。而对于生成式 AI，显然我们不知道，比如我们可能在结束这次录制后看手机，就会看到一条推送通知说 OpenAI 的新模型发布了，而价格只有 2%，因为他们搞定了一些东西……

<details><summary>Original English</summary>
Um, and so what I'm kind of getting at is is that, you know, what does this stuff mean for law is kind of a question for lawyers as much as it is or people who understand a lot about law firms and how they actually work and what they're actually doing and what the clients actually buying from them. Same thing for like what does generative video mean for Hollywood? Like, you know, Ben Affleck probably knows a lot more about this than I do. he built a company and sold it for like 100 billion hundred million dollars. So obviously he does but like you know that so that's kind of a second question which is the questions move outside of AI and they become sort of half AI questions half something else kind of questions. Um and then the third level which is I think and I probably should have said this earlier what the way that all of this is sort of fundamentally different from previous platform shifts is that with you know 3G or the iPhone or the web or whatever it was you didn't know what was going to happen next but you knew the physical limits like you know 1995 you knew that Telos weren't going to give everybody in the world broadband next week and you knew that everyone in the world wasn't going to go out and buy a PC cuz a PC cost like $3,000. So, you kind of knew the basic physical limits of what what could and couldn't happen. And with generative AI, obviously, we don't like we might like like look at our phones when we get off this recording and there's a push notification that says that like Open AI's new model is out and it's like 2% of the price because they worked something
</details>

<!-- chunk 5/9 -->

### 模型的未解之谜与编码之外的场景

出来。我的意思是，在这一点上我认为这不太可能发生，但像这类问题我们根本不知道答案。那么，模型还会变得多大？会变得多好？多快？多便宜？在哪些方面，模型的特性会发生改变？我们都不知道。这与以往的平台变革不同，过去你是知道那些基本的限制条件的。因此，这就会衍生出各种各样的问题。从某种意义上说，这正是我之前指出的那一点——我说过，眼下真正找到产品市场契合度（PMF）的领域就是编码，目前其他任何领域都没有同等程度的产品市场契合度。我不……你知道，我觉得我很保险地可以说，当它从去年年底的所谓 90 亿美元运行率增长到 470 亿美元运行率时，那全都是软件，不是吗？那么，当其他人在其他某个领域把事情做成了，又会发生什么呢？

<details><summary>Original English</summary>
out.

 I

 mean,

 I

 don't





think

 it's

 very

 likely

 at

 this,

 but

 like





we

 don't

 know

 those

 kinds

 of

 questions.





So,

 how

 much

 bigger

 will

 the

 models

 get?





How

 much

 better?

 How

 much

 faster?

 How





much

 cheaper?

 how

 much

 you

 know

 pick

 up





you

 know

 in

 what

 ways

 will

 the





characters

 as

 models

 change

 we

 don't





know

 and

 that

 is

 different

 to

 previous





platform

 shifts

 where

 you

 did

 know

 the





sort

 of

 fundamental

 constraints

 um

 and





so

 that

 will

 that

 will

 kind

 of

 spin

 off





your

 questions

 and

 in

 a

 sense

 this

 is





something

 I

 pointed

 to

 earlier

 I

 said





like

 the

 place

 that's

 got

 product

 market





fit

 right

 now

 is

 coding

 nothing

 else

 has





equivalent

 product

 market

 fit

 right

 now





I

 don't

 you

 know

 I'm

 think

 I'm

 pretty





safe

 in

 saying

 that

 you

 know

 when

 swap





it's

 gone

 from

 whatever

 it

 was

 9

 billion





run

 rate

 at

 the

 end

 of

 last

 year

 to

 $47





billion

 run

 rate





That's

 all

 software,

 isn't

 it?





So

 what

 happens

 when

 someone

 else

 in





some

 other

 field

 gets

 something

 working?
</details>

>> 是的。我是说……

<details><summary>Original English</summary>
>> Yeah.

 The

 I

 mean
</details>

>> 哪个领域？比如法律、银行，我不知道具体是哪里，但总会有点什么……

<details><summary>Original English</summary>
>> which

 field

 like

 law

 bank

 I

 don't

 know





where

 but

 something
</details>

>> 如果让你猜的话，除了编码之外，有哪些用例有可能带来日常活跃度？

<details><summary>Original English</summary>
>> if

 you

 had

 to

 guess

 what

 are

 the

 use





cases

 outside

 of

 coding

 that

 could





potentially

 yield

 you

 know

 daily





activity.
</details>

### 自动化逻辑与杰文斯悖论

嗯，所以，我应该提一下，我几周前发布的那篇演示文稿大概有三个部分：其中一部分谈的是资本、资本支出、基础设施、基座模型和差异化，也就是我们刚才讨论的那些内容；第二部分则是探讨你将如何用它来构建软件、这对软件行业意味着什么、如果这样做软件会变成什么样、以及利润率、各家公司和所有其他方面会发生什么；第三部分我称之为“变革”，这就触及到你提出的这个问题了。我同样是以那句似乎总会惹恼某类人的话作为开篇——引用了约吉·贝拉（Yogi Berra）的那句名言：“预测很难，特别是关于未来的预测。”而且我认为这里有一个类似回测的视角，那就是设想一下在 1997 年就互联网提出这类问题，你能猜中什么？又会遗漏什么？

<details><summary>Original English</summary>
M

 so

 there

 there

 I

 should

 say





the

 sort

 of

 presentation

 that

 I





published

 a

 couple

 of

 weeks

 ago

 there's





sort

 of

 three

 sections

 and

 one

 of

 them





is

 talking

 about

 capital

 and

 capex

 and





infrastructure

 and

 foundation

 models

 and





differentiation

 which

 is

 the

 stuff

 we





talked

 about

 and

 the

 second

 is

 well

 how





would

 you

 build

 software

 with

 this

 and





what

 does

 this

 do

 for

 the

 software





industry

 and

 what

 would

 software

 look





like

 if

 you

 and

 what

 what

 does

 the





margins

 what

 happens

 to

 the

 margins

 and





the

 companies

 and

 everything

 else

 and





the

 third

 section

 I

 called

 change

 which





is

 kind

 of

 getting

 to

 this

 point

 um

 and





I

 opened

 it

 with

 again

 what

 appears

 to





upset

 certain

 category

 of

 person

 where

 I





said

 you

 know

 the

 yogi

 bear

 quote

 that





you

 know

 predictions

 are

 hard

 especially





about

 the

 future

 um

 and

 I

 think

 there's





a

 sort

 of

 a

 back

 test

 point

 which

 is





imagine

 asking

 these

 kind

 of

 questions





about

 the

 internet

 in

 1997

 what

 would





you

 have

 got

 what

 would

 you

 have

 not

 got
</details>

但我认为你可以从一个角度来看待这个问题：这就是自动化，它使得过去人们常常做的一类无法被自动化的事情，现在你可以将其自动化了。然后你就可以问，那这意味着什么？我提出了大概三到四种可以按下的“按钮”或者说路径：

第一个是：这仅仅是价格弹性吗？这其实也就是所谓的杰文斯悖论（Jevons paradox）。比如，如果你把做某件事的成本降得更低，你是会花更少的钱做同样数量的事，还是花同样的钱做更多的事，亦或是花更多的钱做多得多的事？因为做这件事变得太便宜了。以前是否有某种你做不到的事情，现在变得便宜了？是否存在以前成本昂贵、因而被你当作进入壁垒的事情——比如作为报社拥有一台印刷机？是否存在某种原先在成本层面上构成进入壁垒的东西，现在不复存在了？在你的商业模式或竞争空间中，是否有某些东西因为这项事物变得廉价而被解锁了？

然后，最后一个问题大概会是：有哪些事情是以前完全不可能的——比如成本过高、完全令人望而却步，以至于根本没人去考虑过它，而现在却变得触手可及了？我以前在这里举过的例子是：蒸汽机使得火车成为可能，而不管你买多少匹马，你都不可能拥有一列火车或特快列车。

现代得多的例子可以指向像 YouTube、或者确实可以指向 Spotify 这样的产品。比如 Spotify，你可以回顾过去 25 年的音乐行业：前半段是如果你不必为了听那一首歌去买一张 15 美元的 CD 会怎样；而后半段则是如果每个月 15 美元就能让你拥有现存的所有音乐会怎样——这在以前是完全不可能的事情。

<details><summary>Original English</summary>
but

 I

 think

 one

 way

 you

 can

 look

 at

 this





is

 to

 say

 well

 this

 is

 automation





that

 this

 makes

 a

 class

 of

 thing

 that





people

 used

 to

 do





that

 couldn't

 be

 automated

 now

 you

 can





automate

 that

 and

 say

 then

 well

 what





does

 that

 mean

 and

 I

 proposed

 like

 three





or

 four

 way

 the

 sort

 buttons

 to

 press.





First

 one

 is

 is

 this

 just

 price





elasticity,

 which

 is

 really

 what

 the





jeans

 paradox

 is.

 Like

 if

 you

 make

 it





cheaper

 to

 do

 stuff,

 do

 you

 do

 the

 same





amount

 of

 stuff

 for

 less

 money

 or

 do

 you





do

 the

 same

 more

 for

 the

 same

 money

 or





do

 you

 more

 do

 more

 for

 more

 money?

 Um





because

 it

 becomes

 so

 much

 cheaper.

 Um





do

 you

 was

 there

 something

 that

 you





couldn't

 do

 before

 that

 now

 becomes





cheap?

 Was

 there

 something

 that

 was





expensive

 and

 you

 were

 doing

 as

 a





barrier

 to

 entry

 like

 owning

 a

 printing





press

 as

 a

 newspaper?

 Like

 is

 there





something

 that

 now

 was

 was

 a

 barrier

 to





entry

 in

 a

 cost

 space

 a

 barrier

 to

 entry





that

 now

 goes

 away?

 Is

 there

 something





that

 gets

 unlocked

 in

 your

 business





model

 or

 in

 your

 competitive

 space





because

 this

 thing

 became

 cheap?

 And





then

 like

 the

 sort

 of

 the

 final

 question





would

 be

 like

 what

 stuff

 was

 just





completely

 impossible

 like

 cost

 totally





cost

 prohibitive

 that

 so

 that

 nobody





even

 thought

 about

 it

 and

 now

 that's





within

 reach

 and

 the

 example

 I

 used

 to





give

 here

 was

 like

 well

 steam

 engineers





make

 trains

 possible

 and

 it

 wouldn't





matter

 how

 many

 horses

 you

 buy

 you





couldn't

 have

 a

 train

 or

 like

 an

 express





train.

 um

 much

 more

 contemporary

 example





would

 be

 to

 point

 to

 something

 like





YouTube

 or

 indeed

 point

 to

 Spotify

 like





you

 know

 Spotify

 says

 you

 know

 step

 one





of

 the

 you

 look

 at

 the

 last

 25

 years

 of





the

 music

 business

 the

 first

 half

 is





what

 happens

 if

 you

 don't

 have

 to

 buy

 a





$15

 CD

 to

 get

 that

 track

 but

 then

 the





second

 half

 is

 what

 if

 $15

 a

 month

 gets





you

 all

 the

 music

 that

 there

 is

 which

 is





something

 that

 was

 just

 completely





impossible.
</details>

### 电商广告与重构认知的可能

做出这类预测的问题在于：一方面你会说出一些既聪明又显而易见的话，但另一方面你实际上并不知道这对具体每个行业到底意味着什么。比如，如果我们回到 90 年代末，说我们知道互联网将摧毁实体分发的价值；结果证明，这对报社和电影制片厂来说意味着完全不同的事情——报社被彻底击垮了，而电影制片厂则几乎没发生什么太大变化。所以这又取决于具体情况。

这当中的另一个层面是，在某些领域我认为你可以提出更有用的问题，而让我很感兴趣的一个领域是：这会如何改变广告、电子商务、品牌、营销以及我们购买的一切？因为广告规模有 1 万亿美元，零售规模有 25 万亿美元，所以你知道，这是一个相当可观的潜在市场总量（TAM）。

我过去常常在想的一件事是：谷歌、Meta 和亚马逊其实并不知道那个产品到底是什么。它们知道那是一个 SKU，知道发布者在元数据字段中输入了什么，也知道买过这个的人还买过那个，但它们不知道为什么，也不真正知道那些东西是什么。这就是为什么你会看到这样的笑话：“嘿，亚马逊，我就买了一个马桶坐垫圈，我又不是在收集马桶圈。”因为系统并不真正知道什么是马桶圈，也不知道人们一般不会买两个——其实他们本该知道的，那本该是频次分析能解决的，但他们并不知道。

而在大语言模型（LLM）的帮助下，原则上系统会在某种程度上知道那些东西是什么、人们为什么购买它们、以及人们还会购买其他哪些东西。显然，“知道”在这里是一个很难把握、很微妙的词。你说“知道”到底是什么意思？但至少，这是一个截然不同层级的统计相关性，是 AI 系统能够做到的事情。这当然也就是为什么你会看到谷歌和 Facebook 每个季度的广告数据和转化率都在暴涨，因为它们正把所有这些技术融入到自己的广告系统、推荐引擎和预测算法中。你会被展示更多你可能会喜欢的东西，你所看到的广告更有可能是你想买的东西，因此它们的广告收入出现了这种巨大的、突如其来的加速增长。

<details><summary>Original English</summary>
Um,

 this

 is

 all

 the

 problem





the

 problem

 with

 these

 kind

 of

 making





predictions

 like

 this

 is

 like

 on

 the

 one





hand

 you're

 going

 to

 say

 stuff

 that's





kind

 of

 clever

 and

 obvious

 but

 but

 like





you

 don't

 actually

 know

 what

 it's

 going





to

 mean

 industry

 by

 industry.

 Um,

 so





like

 if

 we'd

 been

 back

 in

 the

 late

 '9s





and

 we'd

 said

 we

 know

 internet

 will





destroy

 the

 value

 of

 physical





distribution.

 It

 turned

 out

 that

 meant





completely

 different

 things

 for





newspapers

 and

 movie

 studios

 like





newspapers

 got

 completely

 screwed

 by





this

 and

 movie

 studios

 are

 kind

 of

 not





really

 changed

 very

 much.

 So

 again

 it





depends.

 The

 other

 kind

 of

 part

 of

 this





is

 you

 know

 try

 you

 can

 there

 are

 some





places

 where

 I

 think

 you

 kind

 of

 can





like

 ask

 more

 useful

 questions

 and

 the





one

 that

 sort

 of

 intrigues

 me

 is

 to

 say





well

 how

 does

 this

 change

 advertising

 in





e-commerce

 and

 brands

 and

 marketing

 and





everything

 that

 we

 buy

 because

 you

 know





advertising

 is

 a

 trillion

 dollars

 and





retail

 is

 $25

 trillion

 so

 you

 know

 is

 a





reasonable

 sized

 tam

 so

 the

 thing

 that





I've

 always

 used

 to

 think

 about

 was

 that





Google

 and

 meta

 and

 Amazon

 don't

 really





know

 what

 that

 product

 is

 they

 know

 it's





a

 skew

 they

 know

 what

 the

 publisher





typed

 in

 the

 metadata

 field

 and

 they





know

 that

 people

 who

 bought

 this

 also





bought

 that

 but

 they

 don't

 know

 why

 and





they

 don't

 really

 know

 what

 those

 things





are

 which

 is

 why

 you

 get

 these

 jokes





about

 you

 know

 hey

 Amazon

 I

 bought

 a





toilet

 seat

 cover

 I'm

 not

 collecting





toilet

 seats

 because

 doesn't

 really

 know





what

 a

 toilet

 seat

 is

 and

 doesn't

 know





that

 people

 don't

 buy

 two

 actually

 they





should

 know

 that

 that

 should

 be





frequency

 analysis

 but

 they

 don't

 um

 and





with

 um

 with

 an

 LLM

 like

 in

 principle





you

 would

 kind

 of

 know

 what

 those

 things





are

 and

 why

 people

 buy

 them

 and

 what





other

 things

 people

 by

 and

 obviously

 no





is

 like

 a

 a

 difficult

 tricky

 term

 to





use.

 What

 do

 you

 mean

 when

 you

 say

 no?





But

 at

 a

 minimum

 like

 a

 much

 a

 very





different

 level

 of

 statistical





correlation

 of

 of

 what

 um

 an

 AI

 system





would

 be

 able

 to

 do

 which

 is

 of

 course





why

 you

 see

 the

 ad

 numbers

 and

 the

 you





know

 the

 conversion

 rates

 shooting

 up

 in





the

 every

 quarter

 from

 from from

 Google





and

 and

 and

 um

 and

 Facebook

 because





they're

 rolling

 all

 of

 this

 into

 their





ad

 systems

 and

 their

 um

 recommendation





engines

 and

 their

 um

 prediction





algorithms

 and

 like

 the

 you

 get

 shown





more

 stuff

 that

 you

 would

 like

 and

 the





ads

 that

 you're

 saying

 are

 more

 likely





to

 be

 things

 you'd

 like

 to

 buy

 and

 So





they

 have

 these

 enormous

 this

 sudden





acceleration

 in

 their

 ad

 revenue

 and

 all
</details>

所有这一切都是为了说明：你看看这些系统目前是如何运作的，现在它们会说“买了那个的人可能会买这个”；而现在你应该能够做到这样——正如我在演示文稿中放的一张幻灯片那样，比如给一张外套的照片，“这是什么？我在哪里可以买到？”这在五年前真的不行，十年前肯定行不通，五年前可能也行不通，而现在这应该能做到了。然后你可以接着说，“好的，推荐 10 件类似但价格不同的外套，告诉我哪里能买到，并说明每一件的优缺点。”你多多少少也能得到这样的结果。

接着你还可以更进一步，说：“看看我的 Instagram，给我推荐一件我该买的冬季外套，它能改变我的造型风格，但又不要改变太大。”同样，这在 3 年前完全是科幻小说，而现在你会觉得，没错，你大概能造出这样的东西，它多少能管用。

而在计算机知道什么、能自动化什么、能给出什么建议这些方面的转变，又回到了最开始的核心：每当出现一项新技术时，你一开始总是拿它来做旧的事情，只是做得更多——更多的电子表格、更多的 PPT、更多的电子邮件、更好的电子邮件。但重要的东西并不是把旧的事情做得更多，而是去做你以前用旧东西根本做不到的新事情。我的意思是，这虽然是一个相当平淡无奇的观察，但我们往往会忽略它。

所以，有哪些全新的事情是唯有依靠这个才能做到，而不是仅仅将旧事物自动化的？我是说，我认为这在企业端的版本会是：你把所有与客户的 Zoom 通话都录制下来，把进出 Salesforce 的所有邮件往来都记录在案，而且你能看到所有的……

<details><summary>Original English</summary>
of

 which

 is

 is

 to

 say

 like

 you

 kind

 of





look

 at

 um

 how

 these

 systems

 work

 and





right

 now

 they

 say

 well

 people

 who





bought

 that

 could

 buy

 this

 and

 you





should

 now

 be

 able

 to

 say

 like

 slide

 I





had

 in

 the

 presentation

 was

 like

 here's





a

 picture

 of

 a

 coat

 what

 is

 it

 where

 can





I

 buy

 that

 and

 like

 five

 years

 ago

 that





really

 wouldn't

 10

 years

 ago

 that





certainly

 wouldn't

 work

 five

 years

 ago





probably

 wouldn't

 work

 now

 that

 should





work

 and

 then

 you

 can

 say

 okay

 suggest





10

 other

 coats

 like

 that

 with

 different





prices

 and

 tell

 me

 where

 I

 can

 buy

 them





and

 suggest

 the

 pros

 and

 cons

 of

 each





one.

 And

 you'll

 kind

 of

 get

 that

 too.





And

 then

 you

 can

 push

 one

 step

 further





and

 say,

 um,

 look

 at

 my

 Instagram

 and





suggest

 a

 winter

 coat

 I

 should

 buy

 that





will

 change

 my

 look,

 but

 not

 too

 much.





And

 again,

 like

 3

 years

 ago,

 that

 would





have

 been

 total

 science

 fiction.

 And

 now





you

 think,

 yeah,

 you

 could

 probably





build

 something

 like

 that.

 That

 would





kind

 of

 work.

 And

 those

 kinds

 of

 shifts





in

 like

 what

 the

 computer

 knows,

 what

 it





can

 automate,

 what

 suggestions

 it

 can





make

 the

 going

 back

 right

 to

 the





beginning

 like

 whenever

 you

 get

 a

 new





technology

 you

 start

 by

 doing

 the

 old





thing

 but

 more

 spreadsheets

 like

 more





powerpoints,

 more

 email,

 better

 email.





Um





but

 the

 important

 stuff

 is

 not

 doing

 the





old

 thing

 but

 more.

 It's

 doing

 something





new

 that

 you

 couldn't

 have

 done

 with

 the





old

 thing.

 I

 mean

 it's

 a

 pretty

 benile





observation

 but

 we

 kind

 of

 lose

 sight

 of





it.

 And

 so

 what

 are

 the

 new

 things

 that





you

 can

 only

 do

 with

 this

 as

 opposed

 to





automating

 the

 old

 stuff?

 Um

 I

 mean

 I





think

 the

 you

 know

 the

 enterprise





version

 of

 this

 would

 be

 you

 know

 you've





got

 all

 Zoom

 calls

 with

 clients

 recorded





and

 you've

 got

 all

 the

 flows

 of

 emails





in

 and

 out

 of

 Salesforce

 and

 you

 can

 see





all
</details>

<!-- chunk 6/9 -->

……基于用户如何使用我们产品的遥测数据、指标和分析结果。那么，我们应该如何调整价格来改善流失率呢？再次强调，这可能是大语言模型（LLM）能够胜任的事情，这与要求它“对打入呼叫中心的电话做情绪分析，告诉我哪些客户生气了”大不相同。你在所能进行的分析层面经历着多种抽象层的跃迁。嗯，当然，这随后会催生新公司、淘汰旧公司，创造出新业务以及其他种种。但这同样像是回到了1997年，而我正试图去预测Uber和Airbnb。如果我真能做到那点——这里其实有一个普遍性的道理，那就是如果我们真能准确预测未来的走向，我们就会生活在一个平行宇宙里了。风投机构的成功率就不会是十分之一，而是十分之十了。看起来确实，我们现在正在问的一个问题是，接下来会发生什么——以前做什么事情昂贵得不合情理，而现在变得可行了？比如某种疯狂的事情，像从零开始重建YouTube，或者从零重写Linux，或者……

<details><summary>Original English</summary>
 of the telemetry and the metrics and the analytics of how people use our product. So how should we change our prices to improve our churn? And again, that's something that an LLM might be able to do, which is very different to saying, you know, do sentiment analysis on calls into the call center and tell me which customers are angry. You know, you get kind of multiple shifts in the layer of abstraction around what analysis you can do. Um, and of course that then creates new companies and destroys old companies and creates new businesses and everything else. But again, we're in 1997 and I'm trying to predict Uber and Airbnb. And um if I could actually do that, there's a sort of general point here, which is if we could actually predict what was going to happen, we'd live in a parallel universe. You know, VCs would have, you know, it wouldn't be a one in 10 hit rate, it would be a 10 out of 10 hit rate. It it seems like yeah, one of the questions we're now asking is what sort of follows is um sort of what was in unreasonably expensive to do before that now is is possible and may you know is it so I don't something crazy like rebuilding YouTube from scratch or rewriting Linux from scratch or
</details>

>> 对，很有意思。我是说，当然，另一个成对出现的谬误是：新事物出现了，大家就会说“我们要用新事物来做旧事物”。当然了，我们会用开源来打造Office，我们要在网页上重构它。结果呢，你懂的，瞧瞧Google Docs，它大概就拿下了20%的市场份额，因为那其实根本不是重点。真正有意思的是去做别的事情，去做全新的事情。嗯，是去提升那个抽象层级，去发现以前从未存在过的问题。在一家风投机构整天听路演，你会有这样一种体验：有些东西你听了会觉得“嗯，听起来还挺有用”，有些东西你听了会觉得“我不太确定那为什么能成”。但还有一些东西，它们就像填补了宇宙中的某处空白，一旦有人向你解释清楚，你就会惊叹：“哇，为什么以前从来没人做这个？为什么没人发现那个东西其实存在？”这也是看创业项目很有趣的一部分。人们利用新技术正是会做这样的事。人们会突然找到一种方法，去发现那个问题的存在，而以前没有任何人——包括那些深陷该问题之中的人——意识到那个问题的存在，然后他们就会着手去做一个东西来解决它。

<details><summary>Original English</summary>
>> yeah it's funny I mean you know the other the the paired fallacy of course is the new thing comes along and says well we're going to build the new thing with the the old thing with the new thing um of course we're going to we're going to build office with open source we're going to rebuild it on the web And you know, it turns out like, you know, guess what? Look at Google Docs. It's got like 20% of the market because that's actually not the point. What's interesting is to do something else, is to do something new. Um, and it's to shift that level of abstraction and and and to kind of spot problems that have never existed. I mean, you know, it's the experience you get sitting in pitches all day at a venture firm is there's some stuff where you think, well, that sounds kind sounds kind of useful. and the stuff where you think I'm not quite sure that why that would work. But there are some things that like kind of fill a hole in the universe and like as soon as somebody explains it to you, you think wow why did never nobody do that before? Why did no one see that that thing existed and that's you know where you know part of the fun part of looking at startups is and that's what people will do with this. people will suddenly work out a way that you could turn that that will work out that that problem existed and no one including the people who have that problem no one realized that problem existed and then they'll go out and make a thing to solve it
</details>

顺便提一句，回到之前的一点，这就是为什么我不认同……我认为那种“模型能把所有事情都包揽搞定”的想法是有问题的。如果你回过头去想想自你加入S6C以来看过的所有路演，其中有多少是行业内人士早已知道存在的问题？很多时候答案其实是否定的，业内根本没人觉得那是个问题。实际上，你需要花上大约两年的时间向他们解释、说服他们那个问题确实存在，并且这个新产品能帮他们解决。这就是那种认为“财务部门的中层经理会用这个工具去解决行业大问题”的观念的问题所在——不可能，因为根本没人知道那个行业问题存在，更不用说摸索出构建工具来解决它的正确途径了。这是否意味着比起AI出现之前，SaaS生态的集中度会降低？也许捆绑销售会减少，或者像微软企业级套件这样的单一庞然大物会减少？

<details><summary>Original English</summary>
this is also incidentally going back to an earlier point this is why I don't see the I think that this is the problem with the idea the model will do the whole thing and if you kind of you kind of go back and think about all the pictures you've seen since you joined S6C how many of them were things where people in the industry knew that was a problem like quite often the answer is actually No, actually no one in the industry thought that was a problem and it was actually took like two years to explain to them and persuade them that that problem actually existed at all and that this new thing would fix that for them. And that's kind of the problem with the idea that you know you know middle manager in finance is going to use this tool to solve this big global industry problem like no because no one knew that industry problem was there let alone could could work out the right way to build a tool to solve it. Does this imply a less consolidated SAS environment than than before AI? Maybe less bundling or single behemoths like the Microsoft Enterprise.
</details>

### AI时代的SaaS生态与企业软件分层

>> 天哪，你真是让我一下子落回现实了。“本尼迪克特，SaaS行业的分散度会变高吗？”那些宏大叙事固然很好，但还是“跟我们讲讲股票吧”。嗯，我们在这里能梳理出哪些基本事实呢？显然，构建软件将会变得便宜得多，也快得多。显然，会有许多过去完全不可能用软件完成的事情，现在变得可行了。嗯，所以竞争会更加激烈。随之而来的会是一种全新的利润结构，但正如我们之前讨论的那样，我们并不真正清楚那种利润结构会是什么样。你会转向基于成果的定价吗？要把企业软件中每次按键操作与损益表挂钩，真的非常困难。有时候在Salesforce或类似系统里或许能做到，但有大量软件，你很难去讲“我今天所做的工作对每股收益产生了这样的影响，所以我们应该为此支付这么多费用，应该为那款软件支付这么多钱”。我认为这说不通。无论如何，随着时间推移，定价结构相比现在会变成什么样？竞争会更多，开发东西会更容易，也更快。

<details><summary>Original English</summary>
>> Gosh, way to bring me back down to earth. Like is a SAS industry going to be less consolidated, Benedict? That's all great, but like tell us about the stocks. Um, what are the kind of building blocks that we can put down here? So, obviously, it's going to be way cheaper and quicker to build software. Obviously, there's going to be a bunch of stuff you could do with software that you just couldn't do before at all. Um, and so there will be more competition. there and of course this comes with a new margin structure but as per our conversation earlier we don't really know what that margin structure is going to look like um are you going to go to you know outcomebased pricing it's really hard to like tie each button press in a piece of enterprise software to P&L sometimes you can in Salesforce or something there's an awful lot of software it would be really hard to say well you know the the work I did today did this to DPS therefore this is what we should pay for it um this is what we should pay for that piece of software I don't think that makes sense and long Anyway, but what does the pricing structure look like over time versus now? Um, there will be more competition. It will be easier to build stuff and quicker to build stuff.
</details>

我想，思考这个问题大概有两种比较有用的框架。其中一种框架是：如果你看一下当今的企业软件组合，可以分为三类。一类是重型横向系统，比如SAP、Workday、CRM、资本管理软件、薪酬管理软件等等。然后你有垂直软件，典型的美国大公司大概有三四百个SaaS应用，此外还有大约一千个购买或自建的、在本地部署运行的内部应用。在这两者之间，则是一片模糊的、即兴拼凑的空间，充斥着Excel、电子邮件和共享文件系统。

<details><summary>Original English</summary>
The way that I sort of thought about I suppose this is there's maybe kind of two framings to think about this that are kind of useful. One of them is to say that if you think about the sort of enterprise software fleet today, you've got like three buckets. You've got like your big iron horizontal systems, so SAP and workday and your CRM and your capital management software and your payroll management software and so on. And then you've got um vertical software and typical big US company has like three to 400 SAS apps and then like another thousand apps that they built bought or built themselves internally running on prem and then in the middle you've got this kind of fuzzy improvised space of Excel and email and the shared file system
</details>

事物在这些类别之间来回流动。原则上，每一个SaaS应用所做的事情，你原本都可以在SAP中完成，或者在Excel中完成。比如你本可以在Workday里管理应届毕业生招聘，但在特定节点上——就像前几天朋友间聊到的——如果你是普华永道（PwC），每年要招募成千上万名毕业生培训成会计师，你很可能拥有一套专门为此自建的软件，或者雇佣了埃森哲（Accenture）来帮你搭建，你可能还很讨厌它；但不管怎样，你拥有这样一套专用的招聘软件，或者买现成的。如果你是一家每年只招五个毕业生的公司，你就在电子邮件和共享Google表格里搞定它，因为何必为了这事专门买软件呢？而在中间地带，你究竟是用Workday？用Excel？还是用专用应用？现在你把chat EVC加了进来。你是在LLM里做这件事吗？是否存在某种LLM工具，让你能够在Salesforce里完成以前无法完成的事？或者在垂直应用中完成以前做不到的事？你会用LLM为自己专门构建一个工具来做这件事吗？正如你可能会看到某个公司部门依赖着一个别人在15年前制作的10兆大小的Excel表格运行，没人懂它是怎么工作的，没人知道其工作机制，但他们至今仍在用它。

<details><summary>Original English</summary>
and so and stuff kind of moves back and forth between those and like in principle every SAS app is doing something that you could have done in SAP or you could have done in Excel like you could have like managed your graduate recruiting in workday, but at a certain point like if you're friends conversation the other day, like if you're PWC um and you hire however many thousand graduates every year to train to be accountants, um you probably got a piece of dedicated software that you built for yourself or maybe you hired Accenture to build and you probably hate it, but anyway, you've got this piece of dedicated hiring software or you bought something. If you are a company that hires five graduates a year, you're doing that in email and a shared Google sheet, like cuz why would you buy software for that? And then like then there's a space in the middle. Do you do it in workday? Do you do in Excel? Do you do it in a dedicated app? And now you add chat EVC to that. Do you do that in an LLM? Is there an LLM tool that means you can do that in Salesforce where you couldn't do it before? Or you can do it in your vertical app that you couldn't do before? Um, do you use the LM to build yourself a tool for that? Just as you might have a company department that runs on a 10 10meg Excel spreadsheet that someone built 15 years ago. No one knows it works. No one know how it works, but they're still using that.
</details>

因此，它融入到了这样一个广泛、碎片化且复杂的格局之中，成为解决该任务的另一套可选方案。这是思考这个问题的一种框架。我认为另一种思考框架是：LLM是置于技术栈的顶层还是底层？一方面，置于底层就意味着它是Salesforce内部的一个功能。你在Salesforce里，“看看与该客户的历史记录，看看我们做过的所有其他销售电话的上下文背景，看看我们的业务目标，然后建议一封邮件，或者向我建议此时我应该做什么，以及在致电客户时该说些什么”。所以它是一个功能，是一个由具体用例驱动、受到受控、配有工具链和护栏等等的按钮。另一种视角则是我之前给出的例子：去查看Salesforce、Workday、我们所有的电子邮件以及Google Analytics，然后综合提炼出某些你原本无法……

<details><summary>Original English</summary>
So it kind of it's it arrives within this kind of broad fragmented complicated landscape and it's another set of options for how you would do that task. So this is kind of one framing to think about to think about it. I think the other framing to think about this is does the yellow lamb go at the top of the stack or the bottom of the stack. So on the one hand bottom of the stack is a feature inside Salesforce. So you're in Salesforce look at the history with this customer. Look at the context of every other sales call we've done. look at our business objectives and suggest an email or suggest me what I should do here and what I should say on the call to call the customer. So, it's a feature. It's a button that's controlled and has tooling and guardrails and everything else that are driven by that particular use case. The other way to look at it is the example I gave earlier which is you know go look at Salesforce and workday and all of our email and Google Analytics and and and then synthesize something that you couldn't have
</details>

<!-- chunk 7/9 -->

在以往完成过。因此，在这两种情况下，核心的张力都在于：你把容易出错的概率型软件放在哪里，又把无法回答这类问题的确定性系统软件放在哪里。也就是说，你把数据库放在哪里，又把大语言模型（LLM）放在哪里？它们之间到底谁在上面、谁在下面？答案大概是两者皆有，取决于你正在做什么以及它的具体应用场景。

<details><summary>Original English</summary>
done before. So the the the the tension in both cases is where do you put the probabilistic software that can make mistakes and where do you put the deterministic system software that can't answer these kind of questions. So where do you put the database and where do you put the LLM and is it like which is at the top and which is at the bottom. The answer is probably both depending on on what you what you what you're doing and where it goes.
</details>

说了这么多，归根结底是在探讨：这对软件意味着什么？答案是带来更多的软件，可以说是极其大量的软件。我的意思是，所有的软件公司存在，都是为了解决其他软件公司制造的问题。这是安全领域过去常说的笑话：所有安全软件的存在，都是为了解决其他安全软件带来的问题。显然，我们在 SaaS 时代经历的正是这种情况。SaaS 让我们拥有的软件数量增加了一个数量级、两个数量级。我们大概也应当对这次的技术变革抱有同样的预期。

<details><summary>Original English</summary>
Um all of which is a long way of saying like what does this do to software and the answer is more software like way more software. I mean all software companies exist to solve problems created by other software companies. That was the joke in in security. Like all security software is exist to solve problems created by other security software. And like clearly that's that's what we went through with SAS. Like SAS gave us an order of magnitude, two orders of magnitude more software. Um and we should probably expect that with this.
</details>

而这之所以会引向所谓的“SaaS 末日”，是因为所有投资者审视所有这些公司时都会说：好吧，我们确实不知道这些公司中到底哪一家会因此遭受重创。其中必定有一些会如此，显然必然会有部分——经历完这一切后，现存的所有 SaaS 公司中会有百分之 X 被此彻底淘汰，但你并不知道具体是哪些。因此你或许不该把整个行业直接杀估值 50%，但显然你会觉得：在弄清这到底是怎么一回事之前，我不确定眼下自己是否还想继续做多软件。

<details><summary>Original English</summary>
Um what that gets to you to the SAS apocalypse is all the investors are kind of looking at all these companies and saying well we don't really know which of these companies are going to get screwed by all of this. Some of them must be like obviously there must be some you know go through the end of this and you know x% of all the SAS companies that are out there are going to get wiped out by this but you don't know which ones so you probably shouldn't derate the whole thing by 50%. But clearly you're going to like go I'm not sure I'm going to be long software at the moment until I have some idea of what the hell's going on.
</details>

### 业务流程与组织复杂性

>> 您在与本·汤普森（Ben Thompson）的交流中曾提到，软件本质上是有人坐下来设计了一套工作流，并规定“从现在起这就是做这件事的正确方式”。但您也说过，流程是从业务的实际运转方式中自然生长出来的。这只是需要时间，还是说您认为我们需要这些垂直领域的 AI 初创公司进行更多的实验和迭代，才能探索出面向未来的正确软件形态？

<details><summary>Original English</summary>
>> You you said in your talk with Ben Thompson that software is someone sat down and designed a workflow and said this is the right way of doing this from now on. But you also said that a process grows out of the way just a business runs. Does that just take time or do you think we need more experimentation, iteration from these vertical AI startups to get this the right shape of software for the future?
</details>

>> 某种意义上说，我认为一个颇有意思的角度是：战略咨询公司与软件公司所做的事情其实是相通的。它们都会审视一家公司内部的运作现状，然后指出：“这种做法很糟糕，那样做会更好，能更好地实现你们的目标。”软件公司把这套逻辑固化在软件中；而战略咨询公司则将其编码为工作流、组织架构图、流程、培训以及目标，或许还会建议客户购买某些软件来执行那件事，或者如今也越来越多地可能直接为他们构建这类软件。

<details><summary>Original English</summary>
>> Well, in a sense, I mean maybe kind of an an interesting turn on this is this is both what what strategy consultants do and software companies do is they kind of look at what's going on inside a company and say, well, this is a crap way of doing it. This would be a better way of doing it. It would achieve your objectives better. And a software company kind of encodes that in software. and you know a strategy consultancy kind of encodes that in you know workflows and or charts and processes and training and you know objectives and you know maybe tells them to buy some software to do that thing or maybe now increasingly maybe builds them that software as well.
</details>

我认为这里需要讨论的另一件事是：一个组织内部完成的工作中，有多少是隐性的、未经文档记录的、不存在于训练数据中的，而且是该组织内的任何人都无法真正坐下来为你画出一张流程图并解释清楚的。贝恩、波士顿咨询（BCG）、麦肯锡的很大一部分价值正在于此：他们拥有进入一家公司并与所有人交谈的特权，甚至能去接触那些身处不同部门、平时你无权与之交谈的人，且不会因此被解雇；他们能深入摸清业务实际上是如何运转的，而非表面上理应如何运转；并查明为什么大家没有执行既定战略——因为说实话，他们的奖金目标恰恰取决于不执行该战略；他们能把所有这些情况理顺，作为一支随时从外部切入的团队为你提供答案，之后你既可以把责任推给他们，也可以直接采用那种现成方案。

<details><summary>Original English</summary>
Um I think um another thing to talk about here is how much of what's done inside an organization is implicit and not documented and not in the training data and not something that anybody in that company could actually kind of sit down and draw you an eflow chart of and explain to you. Um that's what that's a big chunk of the value of Bane BCG McKenzie is that they have license to come into a company and talk to everyone and talk to the people you're not allowed to talk to that are in a different org and not get fired and to go and work out how this actually works as opposed to how it's supposed to work and why it is that people aren't doing the strategy because actually guess what their bonus targets depend on them not doing the strategy and work all of that out and be a team that's ready to come in from the outside and give you the answer and then you can blame them or have that kind of that that pre-baked solution.
</details>

这些问题属于组织管理、人如何运作以及人如何解释自身工作范畴的难题，极难被写下来，也极难打包进某个 Claude skill 里并吩咐道“给你，做个 PowerPoint 吧”。因此，这里存在一个更广泛的“这项技术究竟如何落地”的挑战：你如何促使人们去使用这些技术？人们是如何接纳新工具的？你又如何摸索出怎样协助人们接纳新工具，并想清楚利用它们可以做哪些新事情？这同样也是过去在云计算、万维网、移动设备、互联网、个人电脑以及电子表格等技术出现时所经历过的过程。

<details><summary>Original English</summary>
Um that's not you know you that's that that's these are sort of problems in organizational management and how people function and how people can explain what they do that are very hard to write down and very hard to kind of bake into a claude skill and say there you are like make a PowerPoint. Um, and so there's a sort of broader how does this always work challenge here of how do you get people to use these technologies? Um, how do people adopt new tools? How do you work out how to help people adopt new tools and work out what new things you would do with them? Which is also what happened with cloud and the web and mobile and the internet and PCs and spreadsheets and so on.
</details>

### AI 原生软件与资本开支

>> 沿着这个思路，您是否认为 AI 原生软件与新型界面之间存在某种协同演化？例如，新型客户服务 AI 平台可能不再需要那么多面向人类的 UI；或者记录系统（system of record）软件在构建时完全不需要前端，因为其主要用户将是直接向其发起查询的 AI 智能体（agent）。

<details><summary>Original English</summary>
>> To that end, do do you think there's some kind of co-evolution between AI native software and new types of interfaces? for example, new customer service AI platforms that might not have had as much human facing UI or system of record software being built without a front end at all because its primary user will be AI agents querying it directly.
</details>

>> 我认为这些都是挺有意思的想法。但我很难对此持有强烈明确的观点，因为我并没有深入卷入到企业基础设施采购的细枝末节当中。我其实在想，这些问题到底有多新。我记得大概十到十五年前，克里斯·迪克森（Chris Dixon）曾说过 API 是新的业务拓展（BD），软件公司不再需要传统拓展方式，只需要开放 API 即可。这就像旧事物换了新包装重新登场。比如现在有人说不再需要 API 了，只需要一个 MCP 服务器，智能体直接接入即可。

<details><summary>Original English</summary>
So I think these are kind of interesting ideas. They're things I struggle to have a strong opinion on because you know they're not kind of not deep deep into the weeds of of how enterprise infrastructure gets bought. I I wonder how new some of these questions are. Um I remember um Chris Dixon saying like 10 15 years ago that you know APIs is a new BD and software wouldn't need come. Software companies could just you know open up your APIs and like well like what's old is new. Um you know you don't need an API anymore. You just have an MCP server and like people will just plug in the agent will just plug into that.
</details>

我不知道。我认为很多这类事情的难点在于，所有的决策实际上都是异常处理。核心问题始终是：有哪些是无法自动化的？有哪些事情需要有人来做决策、进行判断并提出见解，原因可能在于这些尚未被文字记录下来，或者以前从未发生过，亦或眼下的情况与以往的经历并不完全一致？

<details><summary>Original English</summary>
Um I don't know. I think the challenge with a lot of this stuff is that all the the decisions are really exception handling. Like the question is always what can you not automate? What requires someone to make a decision um and some judgment and have an opinion about it because maybe that hasn't been written down or that didn't happen before or doesn't look quite the way it happened before.
</details>

我认为有几种不同的方式来区分哪些能被自动化、哪些不能。我在演示文稿中使用的方法，是探讨什么是任务（task）与什么是工作（job）。用于完成某项工作的具体任务往往会发生改变，但工作本身可能并没有太大变化，或者该工作向客户交付的核心价值并没有太大变化。例如，如果你想想五十年前的会计和今天的会计在做什么，他们花费的时间几乎全都不在相同的事情上，但对客户而言，交付的本质依然是一回事；只是通过一整套完全不同的具体任务、以截然不同的方式去完成罢了。

<details><summary>Original English</summary>
Um I think there's a sort of you know there are various ways of kind of think about separating out what gets automated and what doesn't. Um the way that I used in the deck was to talk about what's a task versus what's what's a job. We often the tasks that are used to accomplish the job might change without the job itself changing very much or without the thing that the job is selling to the client changing very much. Like if you think about what accountants did 50 years ago and what accountants do today. Um they do spend almost none of their time doing the same things but like to the client it's kind of the same thing. Um it just gets done in a completely different way with a whole bunch of different tasks.
</details>

思考这个问题的另一种更为深刻或偏抽象的视角是：在哪些环节你想要的是平庸、平均的常态？在哪些环节你所追求的正是每个人都会采用的处理方式？“大家都会这么做”、“任何人都会这么说”、“任何人都会这么做”、“任何初级分析师都会这么做”、“任何人都会提供给我这样的东西”、“任何人都会给出这个答案”。与之相对的则是：在哪些环节这并不是你想要的？在哪些环节你需要的是针对新问题的答案、一个截然不同的回答，或者一种崭新的想法？因为对于任何你可以清晰描述人们如何操作、且你追求的就是任何人都会采用的常规做法的场景，大语言模型都会极其擅长；而在你无法真正解释为什么这样操作、以及你的做法有别于常规处理方式的场景下，它的表现就没那么好了。

<details><summary>Original English</summary>
Um, and one of the sort of the more sort of either profound or kind of abstract ways to think about this is where is it that you want the ab the average? Where is it that what you want is the way that everybody will do this? That's the way everyone would do it. That's what anyone would say. That's what anyone would make. That's what any associate would make. That's what anybody would give me. That's the answer anyone would give. Versus where is that not what you want? Where is it that you want the answer to a new question or a different answer or a different idea? Um because LLMs are are going to be very good at anything where you can describe how people do it and where what you want is the way anybody would do that and not so good at where you can't really explain why you did it like that and where you're doing it differently to the way people would normally do it.
</details>

>> 包括谷歌首席执行官在内的多位人士都曾表示，投资不足的风险比过度投资更大。资本开支是否存在某个临界水平，一旦超过，这一定论便不再成立？我们目前是否正在接近那个水平？

<details><summary>Original English</summary>
Various people including you know uh CEO of Google said that the risk of underinvesting is riskier than overinvesting. Is there any level of capex where that stops being true and are we getting there now?
</details>

>> 存在一个财务引力问题，即微软、Meta 和谷歌今年的资本开支均有望占到收入的 50% 以上。我们通常认为电信行业属于资本密集型行业，而电信公司用于资本开支的比例大致是收入的 15% 到 20%。四大科技巨头今年给出的指引是 7000 亿美元。电信行业整体是 3000 亿，移动通信是 2000 亿，总的电信行业是 3000 亿。石油和天然气行业（取决于具体的定义以及你把哪些部分计算在内），我凭记忆觉得大概在 7000 亿到 1 万亿美元之间，具体取决于你问谁。因此，就庞大的全球基础设施建造成本而言，每年 7000 亿美元并非一个大到不可思议的金额。它是

<details><summary>Original English</summary>
>> Well, there's a financial gravity problem in that um Microsoft, Meta and Google are all on in line to spend over 50% of revenue on capex this year. And you know we think of telecoms as being capital intensive. telecom spend instead of 15 to 20% of revenue on capex. Um and so you know $700 billion is the guidance from the big four companies this year. Well you know telecoms is 300, mobile is 200, total telecoms is 300. Oil and gas depending on which definition and which bits of it you're counting is anything from 700 billion to a trillion dollars. I think from memory depends which exactly who you ask. Um, so $700 billion a year is not an impossibly large amount of money as of what big global infrastructure costs. It's
</details>

<!-- chunk 8/9 -->

### 资本开支的物理极限与模型迭代

……就是很多钱。显然，那些公司明年不可能支出1.5万亿，或者就算支出了，也得去借钱，而且他们肯定无法在任何一段时间内维持这种支出水平。所以，到了一定阶段，这种增长必须放缓，因为没有更多的钱了。

<details><summary>Original English</summary>
just a lot of money. Clearly, like those companies could not spend 1.5 trillion next year or if they did, they'd have to borrow it and they certainly couldn't sustain that level of spending um for any length of time. Um, and so there's a certain point at which like that growth has to slow down because like there isn't any more money.
</details>

现在显然你可以去谈论投资回报率（ROI），以及你从该投资中产生回报的能力。而且你知道，资本市场在一定程度上愿意为其提供资金，但随手挑个数，比如我们不可能每年在AI基础设施上花10万亿美元，因为根本没有每年10万亿美元摆在那里可以拿来花。所以存在着有限性，对于可支配的资金量来说，有点像存在着物理定律般的上限。眼下我不敢说出比这更具象的内容。

<details><summary>Original English</summary>
Um now clearly you can talk about ROI and your ability to produce returns from that investment. Um and you know clearly the capital markets are willing to fund that up to a point but like pick a number at random like we can't spend $10 trillion a year on inf AI infrastructure because there isn't $10 trillion a year there to spend on it. So there's a finite there are kind of like laws of physics caps on the amount of money um that's available. I'd hesitate to say something more tangible than that at the moment.
</details>

我的意思是，我差不多又回到了我一开始说的话：我们面临着一系列倍数关系。需求远远大于供给。另一方面，效率又在大幅提升。我们不知道下一个模型会是什么样。我们还不知道端侧或开源何时会介入、它们会在何处发挥作用。而与此同时，你总是在追逐下一个模型。因此，贯穿这一切的主线是：模型只在3到6个月内保持其相关性，或者6到9个月，随便你怎么说。而研发这个模型要花费数十亿美元。要做到这一点，你需要多少基础设施？

<details><summary>Original English</summary>
I mean, I kind of almost go back to what I said at the beginning that like we've got a bunch we've got a bunch of multiples. So, um there's far more demand than supply. On the other hand, the efficiency is increasing massively. Um we don't know what the next model will be. We don't know where edge or open source come in yet, when edge and open source come in yet. And meanwhile, you're always chasing the next model. And so this is kind of the line that runs across all of it is is the model is only relevant for 3 to six months, six to nine months, whatever you want to say. And the model costs how many billion dollars. Um, and how much infrastructure do you need to do that?
</details>

我认为这笔账还没有真正算清楚。显然，有一批非常聪明的半导体分析师花大量时间试图把数字算出来。这有点像90年代末试图为互联网带宽量化具体数字一样。你大概知道电子表格里的行项目有哪些，但你并不真正清楚里面的具体数值是多少。你真正能说的只有：看，不可能无休止。这上面显然存在物理极限。

<details><summary>Original English</summary>
Um, I don't think that mass is really shaken out yet. I mean, obviously you can, you know, there's a bunch of very clever semiconductor analysts who spend lots of time trying to put numbers on this. It is kind of like trying to put numbers on bandwidth, internet bandwidths in the late 90s. like you kind of know what the rows in the spreadsheet are, but you don't really know where the values are. All you can really say is, well, look, it can't be you. There's there's clearly physical limits on this. Um
</details>

我认为回答这个问题的另一种方式是，如果你是谷歌、Meta或微软，在某种程度上还有亚马逊和苹果，这算得上是一个生死存亡的问题，而且你也有某种错失恐惧（FOMO）的问题。因为一方面，你目前的投资回报极其可观；另一方面，你不能任由其他人在你不参与的情况下逍遥其外，因为那样你的公司就完了，你不想沦落成2000年代的微软、90年代的IBM，或者2010年代的Meta那样老是被苹果掣肘。如果这就是计算的未来，那你就必须参与其中。但显然，与此同时，首席财务官（CFO）坐在那里会说：“好啊，这固然很好，但我们这里讨论的参与度到底要有多大？”而且我认为，显然到了某个点，这条曲线将不得不逐渐趋缓，因为已经别无它途了。

<details><summary>Original English</summary>
I think you know another way to answer the question is like if you're Google or Meta or Microsoft um to some extent Amazon some extent Apple this is sort of an existential problem and you have a sort of you know a FOMO problem in that um so on the one hand your returns on the investment at the moment are hugely positive. Um, on the other, you can't let other people get away with this without you participating because then your company's gone and you are you don't want to end up like Microsoft in the 2000s or IBM in the '90s or indeed Meta in the 2010s where they are kind of continually getting shafted by Apple. Um, so if this is the future of compute, then you need to be participating in it. Um but obviously at the same time the CFO is sitting there saying well yeah that's great but um how much participation are we talking about here and I don't think we you know it's clearly at a certain point that curve is going to have to taper off cuz like there's nowhere else it can go.
</details>

### ROI测算与消费者剩余

>> 你认为围绕过度消耗Token（token maxing）会不会迎来一次清算？有没有可能企业一直在过度使用AI，而当他们进行适当的ROI研究时，就会缩减开支？

<details><summary>Original English</summary>
>> Do you think there's going to be a reckoning around token maxing? Uh is it possible that companies have been overshooting AI usage and when they do proper ROI studies they'll pull back?
</details>

显然，你知道，以前有人用最昂贵的模型在网上闲逛瞎搞。这有点像2010年移动端发生的情况。比如你收到了一张1万美元的账单，你就会说：“等等，等等，我以为这是固定费率套餐呢，到底怎么回事？”所以你显然会听到一堆类似愚蠢或恶劣的故事。

<details><summary>Original English</summary>
Well, obviously, you know, you've had people like using the most expensive model to dick around on the internet. Um, which is kind of what happened with mobile, you know, in 2010. Like, you know, you you got a $10,000 bill and you would have said, "Wait, wait, I thought this was a flat rate bundle." Like, what happened? Um, so there's like you've got you've got you obviously you've got a bunch of of like silly/mateful stories. Um,
</details>

但我认为还有一个点——或许稍微更有意思的问题是，而且显然会到这样一个时刻，正如我已经多次说过的，我们正处于一个极度失衡的时期，定价必须重新与成本拉平，而使用方式也必须重新与定价和ROI拉平。挑战在于，在这个早期阶段这有点棘手。想弄清楚ROI到底是多少是相当困难的。这很像在90年代末给每个人都连上互联网，然后说“好了，去提高生产力吧”。如果你看德勤的一项调查，还有我演讲里提到的美联储的一项调查，当你去问CFO们究竟在哪些方面看到了效益时，到目前为止大部分效益都是相当难以量化的东西：比如更好的分析、更好的客户支持、更高的生产力，你可以更快地制作更多幻灯片，你可以更快地完成分析。

<details><summary>Original English</summary>
I think there's also a a point of like I think but what what maybe what's slightly more interesting as a question is um and clearly there's going to be a point in which as I've said se several times we're at a moment of kind of massive dise equilibrium and the pricing has got to get back into alignment with the cost and the usage has got to get it into alignment with the pricing and the ROI. The challenge is it's a bit tricky at this early stage. It's quite hard to know what the ROI is. It's it's rather like giving everybody the internet in the late '9s and saying okay go off be more productive and if you look at like there's a survey from deote there's also a survey from the fed that's in my presentation where if you go and ask CFOs where have you seen seen the benefits and most of the benefits so far have been stuff that's pretty hard to measure so like better analytics better customer support um more productivity you can make more slides more quickly you can do the analysis more quickly
</details>

很难对其赋予一个财务价值。它确实有财务价值，但那不同于直接说：“看，我们用AI做出了这个新东西，它带来了这么多收入，或者帮我们省了这么多钱。”那些事情显然需要更长的时间。打造一条新的收入线，要比把这东西发给所有人、让他们用它更快地做电子表格难得多。所以，这里就有点涉及“这到底需要多久”。

<details><summary>Original English</summary>
it's kind of tough to put a financial value on that it has a financial value but It's not the same as saying, well, we made this new thing with AI and it had this revenue or it saved us this much money. Those things just obviously those things take longer. It's harder to build a new revenue line than to give this to everybody and have them use it to make spreadsheets more quickly. So, there's a little bit of like, well, well, how long does this take?
</details>

我认为这里的另一个问题当然是消费者剩余，也就是说——这有点像当年在Excel上发生的事情：如果做一次折现现金流（DCF）分析需要花你一周时间，那么你可能只做一两个DCF。如果做一次DCF只需要10秒钟，那你就会做50个DCF，但你可能无法为此多收任何钱。所以，发生的一部分情况就是，这些东西变成了竞争所必需的工具，每个人都必须去购买、去使用。但是你从中获得的成本节约或生产力提升，在竞争中就被稀释掉了。因此你无法为此收取更高的费用。

<details><summary>Original English</summary>
I think the other answer to problem here, of course, is consumer surplus, which is to say that um which is kind of what happened with Excel in that, you know, guess what? you know, if if a DCF takes you a week, then you probably only do one or two DCFs. And if a DCF takes you 10 seconds, then you do 50 DCFs, but you probably can't charge any more money for that. Um, so some of what happens is that, um, these things become competitive necessities and everybody has to buy it, use it. Um, but the cost saving or the productivity gain that you get from it just kind of gets competed away. So you don't get to charge more for it, you
</details>

我的意思是，如果你在麦肯锡，或者贝恩、波士顿咨询（BCG），做那份分析以前要花一周时间，现在只需要一天，你可能会做五倍的分析量，向客户收取的费用却一样，而且你的成本基数也没有改变。这正是思考当年投行和财务分析领域所发生情况的恰当方式。你只是用可能更少的人力做了多得多的分析，并向客户收取相同数额的费用。

<details><summary>Original English</summary>
I mean, if you're, you know, if you're at McKenzie and, you know, doing that or or Bane or BCG and doing that piece of analysis used to take a week and now it takes a day, um, you probably do five times more analysis and charge your customer the same and like your cost base hasn't changed either. So, like, you know, which is exactly the way to think about, you know, what happened with with with with investment banks and financial analysis. You just went did way more analysis with probably fewer people and charged customers the same amount of money.
</details>

### 模型商品化与电信行业的类比

你核心论点很大一部分在于认为模型最终会沦为大宗商品，然而在历史上以最快速度筹集最多资金的层级，恰恰是这些基础模型公司。鉴于此，为了适应这种情况，不管是把他们看作一个整体还是单独针对某一家，你对他们有什么建议吗？

<details><summary>Original English</summary>
part of your your big part of your thesis is this idea that models are going to end up as commodities and yet the you know the layer that's raising the most money uh you know in the in the fastest time in history is these foundation model companies. Um so given that what advice might you have for them either either collectively or we can pick on someone individually um in order to in order to adapt?
</details>

>> 倒不是说我知道它们一定会变成大宗商品。我现在的立场更偏向于：“瞧，这里有一连串的逻辑推导表明，从确定性的角度看这些东西会变成大宗商品，那么请向我解释一下为什么它们不会变成那样。”在承诺上我目前只走到这一步。

<details><summary>Original English</summary>
>> It's not that I know that they're going to become commodities. my position is more more now well like hey here is a here is a chain of argument that says that deterministically it looks like these things will be commodities and explain to me why they won't be um and that's as far as I would commit to that
</details>

我认为筹集这么多资金这件事，我差不多又回到了关于移动通信的观点，这同样不具备预测价值，但却是一个值得注意的观察：移动通信行业规模非常庞大，在基础设施上花费巨额资金，但利润率并不高，所有酷炫的事情都是由别人做出来的。然后你去算资本回报率是多少，答案是这取决于具体市场，取决于你是在美国、欧洲，还是印度、中国。

<details><summary>Original English</summary>
um I think the you know the the raising all this money I kind of go back to my point about mobile which again has no predictive value but it's worthwhile observation is that the mobile industry is very big and spends a lot of money on infrastructure and isn't very profitable and all the cool stuff is done by somebody else and then you do you know well what's the return on capital and the answer is well it depends which mark whether you're in America or Europe or or India or China um
</details>

但与此同时，那是一件值得做的事，也确实为某些人带来了回报；但最终他们并没有掌控整个局面，其他人最终从中获取了比他们更多的价值。你知道，我脑子里没有具体数字，谷歌去年的净利润是多少？500亿美元左右还是多少？整个电信行业的净利润又是多少？我真应该订阅彭博终端，那样我就可以立刻回答这些问题了。但基本上可以笃定的是，谷歌、Meta、亚马逊、微软、苹果创造的利润比整个电信行业加起来还要多。所以这是一个难题：你在建……你在推动……

<details><summary>Original English</summary>
but meanwhile like that was a worthwhile thing to do and it produced a return for somebody but then it didn't ended up not controlling the whole thing and other people ended up getting more value from that um than they did um you know I don't have the number in my head what is Google's net income last year was what $50 billion or something what was net income for you know the total telecoms industry I should really subscribe to Bloomberg then I could just answer these questions instantly. Um but like you're a pretty safe bet that Google, Meta, Amazon, um Microsoft, Apple produce more profits than the entire telecoms industry. Um so this is a um is a puzzle is you're build you're driving the
</details>

<!-- chunk 9/9 -->

前沿向前推进。你有点陷入了这种陷阱：你必须继续竞争，因为否则他们就会去做，而你就会落后。你还有这么一件事，我们完全没有谈到过，那就是，你知道，“嘿，我们不就只是在构建AGI吗，就像我们要把上帝造在一个盒子里一样”，你知道，有些人确实相信这一点，虽然这有点难……很难去分析，但也许……嗯，所以你知道，你打算继续构建这些东西，但实际的问题是，嗯，你如何做出人们想用的、不是软件的东西，不是……不是软件开发？我的意思是，那是一门好生意，嗯，那是唯一的生意吗？有……你知道，随便挑一个几千亿、几百万美元的数字，那就是让软件行业提高生产力，太棒了，然后呢？我的意思是，那……你知道，那也许值一万亿美元，但是……但是然后呢？就像，你如何把这个扩展到经济的其他部分，扩展到其他每个人？这就是为什么你会听到这些关于……你知道，与私募股权合作、与咨询公司合作的对话，在这些对话中，你知道，正如我们一直在讨论的，你猜怎么着，如果你真正在经营一家现实中的公司，实际上很难弄清楚该用这东西来做什么。嗯，所以去找贝恩（Bain）、BCG、麦肯锡（McKinsey），或者Infosys和Cognizant，以及IBM、埃森哲（Accenture），或者私募股权避风港。所以就有这样一种感觉，比如一方面你……所以我有点在一边说一边试图理出答案，但比如一方面，你正在构建这种大……这些越来越大的模型，而且你有点觉得你必须继续做下去，但另一方面，是的，但人们在用它做什么呢？

<details><summary>Original English</summary>frontier

 forward.

 You're

 kind

 of

 caught





in

 this

 trap

 that

 you

 have

 to

 keep





competing

 because

 otherwise

 they'll

 do





it

 and

 you'll

 fall

 behind.

 You've

 also





got

 this

 thing

 that

 we

 haven't

 talked





about

 at

 all

 which

 is

 you

 know

 hey





aren't

 we

 just

 building

 AGI

 like

 we're





going

 to

 build

 God

 in

 a

 box

 which

 you





know

 some

 people

 they

 do

 believe





although

 it's

 kind

 of

 hard

 to

 it's

 hard





to

 analyze

 but

 maybe

 um

 so

 you

 know





carry

 you're

 going

 to

 carry

 on

 building





this

 stuff

 but

 the

 practical

 question

 is





well

 how

 do

 you

 get

 things

 that

 people





want

 to

 use

 that

 aren't

 software

 that





aren't

 that

 aren't

 software

 development





I

 mean

 that's

 a

 good

 business

 um

 is

 that





the

 only

 business

 there's

 you

 know

 pick





a

 number

 of

 that

 many

 hundreds

 of





billions

 millions

 of

 dollars

 it

 is

 to





make

 the

 software

 industry

 more





productive

 great

 then

 what

 I

 mean

 that's





you

 know

 that's

 worth

 a

 trillion

 dollars





maybe

 but

 but

 then

 what

 like

 how

 do

 you





expand

 this

 into

 the

 rest

 of

 the

 economy





into

 everybody

 else

 which

 is

 why

 you

 get





these

 conversations

 about

 you

 know





partnering

 private

 equity

 partnering





with

 consultancies

 where

 you

 know





exactly

 as

 we've

 been

 discussing

 guess





what

 it's

 actually

 quite

 hard

 to

 work





out

 what

 to

 do

 with

 this

 stuff

 if

 you're





actually

 running

 a

 real

 company

 um

 so





you

 go

 to

 Bane

 BCG

 Mackenzie

 or

 Infosys





and

 cognizant

 and

 IBM

 app

 Accenture

 or





private

 equity

 shelters.

 So

 there

 is





this

 sort

 of

 sense

 of

 like

 on

 the

 one





hand

 you

 so

 I'm

 sort

 of

 trying

 to

 work





out

 the

 answer

 as

 I

 speak

 but

 like

 on





the

 one

 hand

 you're

 building

 this

 big





these

 bigger

 and

 bigger

 models

 and





you've

 kind

 of

 feel

 like

 you've

 got

 to





keep

 doing

 it

 but

 on

 the

 other

 hand

 yes





but

 what

 are

 people

 doing

 with

 it?</details>

>> 为什么大多数人看着ChatGPT，在今天却并不真正能想到用它来做什么？

<details><summary>Original English</summary>>> Why

 do

 most

 people

 look

 at

 chat

 GPT

 and





not

 really

 think

 of

 anything

 to

 do

 with





it

 today?</details>

### 历史技术浪潮与AI的未来

>> 最后一个问题。演示文稿里有什么内容是你想确保……呃，听众记住的吗？我……我去年用过、并且我……我又用了一次的东西，是我找到的一则20世纪50年代早期的IBM广告，上面有一张一大群工程师全拿着计算尺的照片，这是一则IBM广告，它上面写着，你知道，“一台IBM电子计算机给你带来额外150名工程师”，这就像……你在a16z见过多少张以此为说辞的照片。嗯，我们有点记得，就像我们每隔10年、15年或20年就会经历一轮这些……这些根本性的技术变革浪潮，它们都令人惊叹，改变了一切，并且完全不同于以往发生的任何事情。因此，AI令人惊叹且具有变革性，完全不同于以往发生的任何事情。移动设备当年也算是一件大事，互联网也是，PC也是，计算机技术也是。那些也全都是非常重大的事情，当时很难说会发生什么。

因此我们大概应该假定一种基准情况：好吧，我们要再次经历那个过程了。而且你知道，那会产生一大堆毁掉人们生活的事情，还会让一大批人失业。嗯，你知道，会有一大堆让我们不是很开心的事情。嗯，也会有一大堆我们全都觉得棒极了的事情。然后20年之后，我们大概就会忘记曾经有过一个计算机无法做到那些的世界。嗯，我的意思是，看看我们现在。我们通这个电话已经一个小时了，我们的电脑没有崩溃，我们正在向彼此流式传输高清视频，这就像，好吧，这当然行得通。事实上，我也在用我的iPhone这样做。所以，我的iPhone正通过Wi-Fi串流到我的Mac，在这里串流视频，就像……它就是好用，就像魔法一样，而我们不再去注意它了。我认为这确实就是我对这一切最终将如何收尾的一句话概括。它将会成为魔法，而在20年之后，我们只会说，嗯，当然就是这样了。计算机一直都是这么做的。

<details><summary>Original English</summary>>> Last

 question.

 Is

 there

 anything

 from





the

 presentation

 that

 you

 want

 to

 make





sure

 uh

 listeners

 leave

 with?

 The

 thing





that

 I

 I

 used

 last

 year

 and

 I

 I

 used





again

 is

 an

 IBM

 ad

 I

 found

 from

 the





early

 50s

 which

 has

 got

 a

 picture

 of

 a





sea

 of

 of

 engineers

 all

 holding

 up

 slide





rules

 and

 it's

 an

 IBM

 ad

 and

 it

 says

 you





know

 an

 IBM

 electronic

 calculator

 gives





you

 150

 extra

 engineers

 and

 that's

 like





how

 many

 pictures

 have

 you

 seen

 at

 A6Z





where

 that

 was

 the

 pitch.

 Um,

 and

 we





kind

 of

 remember

 like

 we

 go

 through





these

 waves

 of

 these

 these

 fundamental





technology

 changes

 every

 10

 or

 15

 or

 20





years

 and

 they're

 all

 amazing

 and

 change





everything

 and

 are

 completely

 unlike





anything

 that's

 happened

 before.

 And

 so





AI

 is

 amazing

 and

 transformative

 and





completely

 unlike

 anything

 that's





happened

 before.

 Mobile

 was

 quite

 a

 big





deal

 too

 and

 so

 was

 the

 internet

 and

 so





were

 PCs

 and

 so

 was

 computing.

 Those





were

 all

 also

 very

 big

 deals

 where

 it





was

 hard

 to

 tell

 what

 was

 going

 to





happen.

 And





so

 we

 should

 sort

 of

 presume

 as

 a

 base





case,

 okay,

 well,

 we're

 going

 to

 go





through

 that

 again.

 And

 you

 know,

 that





will

 produce

 a

 bunch

 of

 things

 that

 ruin





people's

 lives

 and

 it

 will

 put

 a

 bunch





of

 people

 out

 of

 work.

 Um,

 and

 you

 know,





there'll

 be

 a

 bunch

 of

 stuff

 that

 we're





not

 very

 happy

 about.

 Um,

 and

 there'll





be

 a

 bunch

 of

 stuff

 that

 we

 all

 think

 is





great.

 And

 then

 in

 20

 years

 time,

 we'll





kind

 of

 forget

 that

 there

 was

 a

 world





when

 computers

 couldn't

 do

 that.

 Um,

 I





mean,

 here

 we

 are.

 We've

 been

 on

 this





call

 for

 an

 hour

 and

 our

 computers





didn't

 crash

 and

 we're

 streaming

 HD





video

 to

 each

 other

 and

 it's

 like,

 well,





of

 course

 that

 worked.

 In

 fact,

 I'm

 also





doing

 it

 with

 my

 iPhone.

 So,

 my

 iPhone





is

 streaming

 to

 my

 Mac

 over

 Wi-Fi





streaming

 video

 here

 and

 like

 it

 just





works

 like

 it's

 magic

 and

 we

 don't





notice

 it

 anymore.

 And

 I

 think

 that's





really

 my

 kind

 of

 oneline

 description

 of





how

 all

 of

 this

 is

 going

 to

 end

 up.

 It's





going

 to

 be

 magic

 and

 in

 20

 years

 time





we'll

 just

 say,

 well,

 of

 course

 that's





how

 it

 is.

 Computers

 have

 always

 done





that.</details>

是的，这是一个极好的……极好的收尾之处。这个演示文稿的名字叫《AI Essets the World》（AI吞噬世界）。它在Benedict Evans的网站上。它非常棒。呃，还有很多我们没能涉及到的内容，所以一定要去看看。Benedict，这是一次很棒的对话。非常感谢你来参加播客。

<details><summary>Original English</summary>Yeah,

 that's

 a

 great

 place

 to

 great





place

 to

 wrap.

 The

 presentation

 is





called

 AI

 Essets

 the

 World.

 It's

 on





Benedict

 Evans

 website.

 It

 is

 excellent.





Uh

 there's

 a

 lot

 more

 that

 we

 didn't

 get





to,

 so

 definitely

 go

 check

 it

 out.





Benedict,

 this

 has

 been

 a

 great





conversation.

 Thanks

 so

 much

 for

 coming





to

 the

 podcast.</details>

>> 谢谢。聊得非常愉快。

<details><summary>Original English</summary>>> Thanks.

 Great

 to

 chat.</details>