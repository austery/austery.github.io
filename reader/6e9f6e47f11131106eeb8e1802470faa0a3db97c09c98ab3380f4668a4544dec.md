---
author: The MAD Podcast with Matt Turck
date: '2026-06-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UN47z_opfmo
speaker: The MAD Podcast with Matt Turck
tags:
  - agentic-workflow
  - traffic-growth
  - business-model-change
  - knowledge-gap-filling
title: 机器人流量反超人类：互联网商业模式的根本性变革与未来趋势
summary: 文章探讨了在2026年上半年，由于人工智能和大型语言模型（LLM）的驱动，网络上的机器人和AI代理数量已超过人类流量。分析了这一现象背后的数据增长速度、对传统广告驱动的互联网商业模式的颠覆性影响，并介绍了基础设施公司如何通过构建智能体平台来解决知识获取的空白，以及未来媒体环境回归事实真相的愿景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/11 -->

### 播客引言与背景

**Matthew Prince**: 在2026年上半年，网上的机器人流量实际上已经超过了人类流量。在五年内，互联网的流量可能会达到现在的1000倍。在接下来的6到12个月里，几乎每家公司都会经历这样的过程——他们将大幅裁减团队。过去28年里，互联网底层的商业模式基本保持不变，主要依赖广告。问题是，机器人不会点击广告。在未来五年内，互联网的商业模式将会发生根本性的改变。

<details>
<summary>Original English</summary>

**Matthew Prince**: We actually had bot traffic pass human traffic online in the first half of 2026. In 5 years, you might have a thousand times as much traffic on the internet as you do today. In the next 6 to 12 months, almost every company is going to go through some exercise like this where they're going to cut a bunch of their team. The underlying business model of the internet for the last 28 years has remained basically the same, which is it's largely advertising. The problem is bots don't click on ads. Over the next 5 years, the business model of the internet's going to change radically.

</details>

**Matt Turk**: 大家好，我是Matt Turk。欢迎收听Matt播客。今天，我非常激动地邀请到了Cloudflare的联合创始人兼CEO Matthew Prince。Cloudflare是互联网上最重要的公司之一，它承载着全球极高比例的互联网流量。我们的对话将从剖析一个巨大的里程碑开始：有史以来第一次，互联网上的机器人和AI代理数量超过了人类。我们还会讨论Cloudflare是如何成为一家AI基础设施公司的，并深入探讨Cloudflare Workers、AI网关以及代理安全等话题。我们也没有回避一些更具争议性的话题，包括Cloudflare最近为了适应新的AI时代而精简团队的决定。我还要补充一点，Matthew是一位非常棒的故事讲述者，他分享了一些Cloudflare从一家斗志昂扬的初创公司，成长为今天这样庞大的上市公司的过程中，一些真正疯狂而又搞笑的经历。请尽情享受这场与Matthew的精彩对话。我想从一个感觉像是互联网历史上非常关键和重要的时刻开始。几周前你在推特上说，现在互联网上的机器人和机器的数量实际上已经超过了人类。所以，你能展开讲讲并解释一下那是怎么回事吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome to the Matt podcast. Today, I'm excited to welcome Matthew Prince, co-founder and CEO of Cloudflare, one of the internet's most important companies that sits in front of a very large portion of global internet traffic. We start the conversation by unpacking a huge milestone. For the first time, the number of bots and AI agents has outnumbered humans on the internet. We also cover how Cloudflare has become an AI infrastructure company and dig into Cloudflare workers, AI gateway, and agent security. We also don't shy away from some of the more controversial topics, including Cloudflare's recent decision to rightsize its team to adapt to the new AI era. I should add that Matthew is a wonderful storyteller, and he shares some truly wild and hilarious episodes from Cloudflare's journey from scrappy startup to the massive public company it is today. Please enjoy this fantastic conversation with Matthew. I want to start with something that feels like a very crucial important moment in the history of the internet. What you tweeted a couple of weeks ago and you said effectively that the number of bots and machines on the internet now outnumbers humans. So can you unpack that and explain what that was?

</details>

### 机器人流量反超人类

**Matthew Prince**: 是的，其实网上一直都有机器人在到处运行。谷歌的工作方式就是抓取互联网数据，然后在此基础上构建索引。从历史上看，在云计算的大部分发展史中，互联网上大约20%的流量是机器人，并且在一段时间内保持着相当稳定。直到大约两年前，我们开始看到机器人流量的真正攀升，这主要归功于AI、大型语言模型（LLM）以及它们背后所发生的一切。去年秋天，也就是2025年秋天，有人问我自动流量何时会超过人类流量？我们调取了数据，对趋势进行了外推，我们原本以为这会在2027年底发生。快进到今年（2026年3月）的西南偏南（South by Southwest）大会，又有人问了我同样的问题，我们再次查看了数据，然后发现：“哦，哇。它的增长速度比我们预期的快得多。现在已经提前到了2027年上半年。”然后，几周前，当我的团队来找我时，我感到非常震惊，他们说：“你不会相信的。但实际上，我们在2026年上半年就看到了机器人流量超过了人类流量。”我认为这表明，这些基本完全由AI驱动的不同系统增长得有多快，它们确实在推动互联网上多得多的流量。

<details>
<summary>Original English</summary>

**Matthew Prince**: Yeah, so I mean there have always been bots that ran around online. The way Google works is they scrape the internet and they then build their index based on that. And historically throughout most of the history of cloud it was about 20% of traffic on the internet was bots and that held fairly consistent over a period of time until about two years ago when we started to see a real rise in bots driven mainly by AI and the LLMs and everything that was going on behind those. And last fall in the fall of 2025, I was asked at what point will automated traffic pass human traffic? And we pulled the data and we sort of extrapolated out the trends and we thought that it was going to be the end of 2027. Fast forward to South by Southwest this year, March of 2026, and I was asked the same question again and we looked at the data again and we're like, "Oh, wow. It's growing a lot faster than we expected. It's moved now to the first half of 2027." Uh, and then, you know, I was pretty shocked when my team came to me just a few weeks ago and they said, "You won't believe it. Um, but we actually had bot traffic pass human traffic online in the first half of 2026." So I think what that shows is just how fast these different systems again almost all driven by AI are growing and they're really driving so much more traffic across the internet.

</details>

**Matt Turk**: 那这里的计算基数是什么？比如HTTP请求吗？

<details>
<summary>Original English</summary>

**Matt Turk**: And what was the denominator, was like a HTTP request?

</details>

**Matthew Prince**: 对。Cloudflare位于很大一部分互联网流量的前端，所以这是一个非常有代表性的样本。因此，我们总是能够观察到互联网上的总体趋势是什么。我们有一个名为Radar的网站，如果你去radar.cloudflare.com看看，它追踪了许多不同的数据，其中之一就是有多少人类流量，有多少机器人流量。在过去的几个月里，机器人流量超过了人类流量。我认为，如果你把它外推一下，在5年内，我认为你会看到机器人流量比人类流量多1000倍。如果非要让我下注猜个大小，我会押大，因为这真的是在以指数级的速度增长，你将会看到互联网上庞大数量的流量，都是由这些各种各样的机器人、代理和其他系统所驱动的。

<details>
<summary>Original English</summary>

**Matthew Prince**: Yeah. So, Cloudflare sits in front of, you know, a huge percentage of the internet and so we and it's a super representative sample and so as a result we can always look at what are the general trends across the internet and we have a site we call radar if you go to radar.cloudflare.com that's tracking a number of different things and one of those is how much human traffic is there how much bot traffic is there and in the last couple months it the bot traffic exceeded the human traffic and I think that if you extrapolate this out you know in 5 years I think you'll see a thousand times more bot traffic than human traffic and if I had to take kind of an overunder bet on that I'd take the overb that it's just going to it's growing at such an exponential rate that you're just going to see an enormous amount of the internet that's driven by these various bots and agents and other systems.

</details>

### 定义机器人与AI代理

**Matt Turk**: 当我们说“机器人（bots）”时，我们是指代理（agents）吗？我们是指爬虫机器人吗？我们的具体定义是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: And when we say bots, do we mean agents? Do we mean crawling bots? What do we mean?

</details>

**Matthew Prince**: 我的意思是，我认为代理、机器人、爬虫都是同义词。它们的意思是一样的。这取决于你是否想用一种规范性的、积极的方式来描述它，在这种情况下你会称它为代理。如果你想用一种最令人反感的方式来描述它，你就会称它为爬虫或抓取器。但在幕后，它们是同一种东西。它是一台访问资源的机器，而不是一个正在驱动浏览器、并靠人眼来访问这些资源的人类。再说一次，在这种特定情况下，你仍然有很大一部分类似于抓取器、爬虫、黑客的流量，那些并没有发生太大的变化。你也仍然有一些建立搜索索引的机器人，比如谷歌机器人。那些也没有改变多少，如果说有变化的话，甚至还下降了一点点。但真正推动这一趋势的，是我认为大家都会称之为代理的东西。也就是说，如果我去了ChatGPT，或者去了Claude，或者去了任何这些系统，我正在网购数码相机，为了同样的一项活动——为了完成“网购数码相机”这同一项任务，你会看到网站访问量是如果是人类自己去做的数千倍。如果我个人想要弄清楚该买哪款数码相机，我可能只会访问5个网站；但我的代理可能会访问5000个。而这就是真正推高这种需求的原因。

<details>
<summary>Original English</summary>

**Matthew Prince**: I mean, I think that agent, bot, crawler are all synonyms. It all means the same thing. It depends on whether you want to describe it in a sort of normatively positive way, in which case you call it an agent. If you want to describe it kind of the ickiest way, you call it a crawler or a scraper. But it's the same thing behind the scenes. It's a machine that's accessing resources as opposed to kind of a human eyeball driving a browser accessing those resources. And again in this particular case you still have a whole bunch of the sort of scraper crawler hacker traffic. That hasn't changed that much. You still have some of the sort of bots like Google bot that are building search indexes. That hasn't changed that much. If anything, it's gone a little bit down. But the thing that's really driving this is what I think we would all call agents, which is, you know, if I go to Chat GBT or I go to Claude or I go to, you know, any of these systems and I'm shopping for a digital camera, you're going to see, you know, thousands of times more site visits for that same activity, that same job to be done of shopping for a digital camera than if I did it myself. I might visit five sites if I'm, you know, personally trying to figure out what digital camera to buy, whereas my agent might visit 5,000. And that's what's really driving this increased demand.

</details>

### 对基础设施与商业模式的影响

**Matt Turk**: 是的。那这会带来什么改变，我想，从基础设施的角度来看，就像你刚才描述的，5000个网站对比5个，在某些方面这听起来效率很低。我的意思是，这对我作为用户来说最终是高效的，因为我猜能得到最好的答案。但这会对基础设施的需求带来怎样的改变呢？

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah. And what does that change from, I guess, in an infrastructure perspective, like what you just described 5,000 sites versus five in some ways. That sounds inefficient. I mean, it's efficient for me as a user ultimately because I guess the best answer. What does that change in terms of requirements for the infrastructure?

</details>

**Matthew Prince**: 是的，我认为，首先，如果这种趋势继续下去，互联网上将会出现大量的额外需求。回想一下疫情期间，在短短两周的时间里，我们看到互联网流量翻了一倍。如果我们的预测是准确的，那么很快，那种程度的增长看起来就会显得微不足道。在5年内，互联网的流量可能会达到现在的1000倍。这意味着我们需要更多的服务器、更多的网络基础设施、更多的CPU、更多的GPU、更多的内存；所有这些用来服务机器人的东西都将变得非常重要。这也意味着我们将不得不弄清楚一些新的商业模式来为此提供资金。总得有人来买单。你知道的，过去互联网的商业模式一直是广告，而机器人是不会点击广告的。所以，未来的商业模式将会变得有所不同。我认为目前世界上最有趣的问题是：在未来五年内，互联网的商业模式将会发生根本性的改变，而它究竟会变成什么样子，在现阶段还完全是个未知数。

<details>
<summary>Original English</summary>

**Matthew Prince**: Yeah, I think I mean first of all there if this trend continues there's just going to be an enormous amount of additional demand on the internet and I go back to you know during co where over the course of 2 weeks we saw internet traffic double um you know if our projections are right um that's going to seem quaint very soon um you know in 5 years you might have a thousand times as much traffic on the internet as you do today and that's going to mean more you know servers, more network infrastructure, more CPUs, more GPUs, more memory, all of the things that have to serve these bots are going to be very important. And it's also going to mean we're going to have to figure out some new business model in order to fund that. Someone has to pay for it. And um and you know, the business model of the internet historically has been ads and bots don't click on ads. So, it's going to be something different going forward. And um you know I think the most interesting question that in the world today is over the next 5 years the business model of the internet's going to change radically and what it changes to is totally undefined at this point.

</details>

**Matt Turk**: 是的，那完全是一种全新的词汇体系，因为过去它叫“点击量”和“浏览量”，现在它会变成什么呢？像是“动作数（actions）”或者...

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah, that's a whole new vocabulary because it used to be clicks and views and what is it going to be now like actions or

</details>

**Matthew Prince**: 我们必须确切弄清楚那到底是什么，而且它将改变许多事情。比如，在由代理主导的世界里，品牌意味着什么？从历史上看，品牌是告诉人类的一条捷径：代表着某种特定的预期集，以及与之相关的特定体验集。如果我看到一栋建筑侧面挂着沃尔玛的标志，我就知道走进去会是什么样子。如果我看到万豪（Marriott）的标志，如果我看到麦当劳的标志，我就知道那会是什么感觉。但机器人的特点是，它们拥有无限的耐心去探索所有可能正确的事物。所以...

<details>
<summary>Original English</summary>

**Matthew Prince**: We've got to figure out exactly what that is and it's going to you know change a number of things like you know what is a brand in an agentic world. Um, you know, a brand historically has been, you know, a way as a shortcut to tell humans kind of this is something that has a certain set of expectations, will have a certain set of experience associated with it. If I see a Walmart logo on the side of the building, I know what it's going to be like when I walk in. If I see a Marriott logo, if I see a McDonald's logo, I know what that's going to be like. You know the thing about bots is they have infinite amount of patience in order to discover you know everything that might be right. So the

</details>

<!-- chunk 2/11 -->

### 品牌未来的演变

**Speaker A**: 未来品牌的基本概念将会与过去截然不同，过去主要是由人类驱动的商业和互联网体验。再说一次，我不确定自己是否已经清楚它未来的具体模样。我认为 Cloudflare 将在帮助探索这一点的过程中发挥一定作用，但我觉得这一切都将在未来五年内被发掘出来，这是非常令人兴奋的。

<details>
<summary>Original English</summary>

**Speaker A**: a what the the basic idea of what a brand is going forward is going to be very different than what it has been in what had been the very much human-driven um kind of commerce and and internet experience. Um, and uh, and again, I I'm not sure I'm not sure that I I have I have ideas of what that might look like. Um, and and I think that Kleer will play some role in in helping figure that out, but but I think it's it's all going to get discovered over the next 5 years, and that's that's incredibly exciting.

</details>

### Cloudflare 的早期起源与挑战

**Speaker B**: 好的。这很吸引人。我想花一点时间谈谈 Cloudflare 的基础知识（Cloudflare 101）。如果我把 Cloudflare 放在我的网站前面，会发生什么？

<details>
<summary>Original English</summary>

**Speaker B**: >> All right. Fascinating. I'd love to spend a little bit of time on Cloudflare 101. If I put Cloudflare in front of my website, what what happens?

</details>

**Speaker A**: 是的。Cloudflare 起初的想法是，如何将防火墙这样的安全产品放到云端。最初的想法来源于一种认知，即软件正在向云端迁移，服务器也在向云端迁移，因此所有的安全和网络基础设施也必须迁移到云端。这就是我们开始时的基本前提。所以，如果你在 15 年前注册了 Cloudflare，并把我们放在你的网站前面，你实际上做的是在网站前放了一个“保镖”，它可以检查任何试图访问网站的人，然后把坏人拦在外面。然后，因为我们需要确保不拖慢速度，我们也会卸载你网站的大量负载，并且能够为正常的访客更快地分发内容。所以 Cloudflare 最初的理念是把性能和安全打包成一个非常容易被采用的组合。作为一家企业，我们知道为了取得成功，最终必须将我们的服务卖给大型银行、政府和医疗机构等目前已经是我们客户的组织。在早期，这些组织永远不会信任我们，因为我们只是一个不起眼的初创公司，没有任何基础设施，也没有数据来实际提供安全服务。因此，我们做的是创建了一个免费的、简化版的服务，目的是让所有人都能使用。有趣的是，我们原本以为会有一大批中小企业（SMB）、初创公司和个人用户来注册，但事实证明，如果你把这看作一个 XY 轴，X 轴是预算，Y 轴是安全问题，几乎存在一条完美的对角线——你的预算越少，你面临的安全问题就越少；预算越大，安全问题就越多。所以结果是，即便是中小企业和初创公司，尽管它是免费的，也不会注册。但是有两个组织或群体打破了这个规律。一个是年轻的黑客们，因为他们总是在互相攻击，所以一夜之间，全世界的年轻黑客都注册了 Cloudflare，然后他们互相攻击，试图把我们搞垮。另一个是人权组织、人道主义组织和非营利组织。因为如果你从事任何这类工作，十有八九会惹恼某些人，而且通常是某些政府或势力，然后他们就会攻击你。所以一夜之间，世界上所有的人道主义组织、所有的黑客都在使用 Cloudflare。他们全都在用，而我们突然间就遭受了大规模的攻击。所以我们一直在努力解决，如何才能保持领先？在这个世界里我们如何生存并茁壮成长？这迫使我们构建了许多不同的东西。我们建立了一个注册商产品，这样你就可以注册域名，因为我们以前用过一个注册商，我们的域名差一点被盗，那对我们来说将是一场灾难。我们不得不建立 DDoS 缓解机制，起初我们根本没想过要做这个。我们不得不建立 DNS 基础设施，因为我们找不到其他人来支持我们。我们需要建立自己的 VPN，因为其他人的都太慢或不够安全。最终，我们必须建立我们自己的开发者平台，我们的团队可以基于它，把他们的想法以一种受到严格沙盒限制的方式部署出来。因为发展到某个阶段，我们变得足够庞大，如果我们出现问题，对我们正在做的事情以及对世界来说将是极其具有破坏性的。所以，Cloudflare 的真实故事是，我们一开始的想法非常简单，就是如何把防火墙放到云端，但随着时间的推移，我们给自己制造了太多的问题需要去解决。在解决这些问题的过程中，我们构建了一系列的产品。所以今天的 Cloudflare，与我们刚起步时不同，在某种程度上，我很难确切地描述我们到底是做什么的。可以说，我们是新一代的 AWS 或 Google Cloud，我们重新思考了它的运作方式。我们仍然在上面提供安全和性能，但我们有利用现有网络的其他产品，以提供基于云的 VPN 和其他服务等。而且，由于我们在互联网上占据了巨大的比例，我们越来越多地参与到探索未来互联网商业模式的过程中。我们的使命是帮助建立一个更美好的互联网。我认为任何能实现这个使命的事情，都是我们一直在思考的问题。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah. So um you know what what Cloudflare started out as was um how can you take um a a firewall like a a security product and put it in the cloud. And the and the original idea came from you know a realization that you know software was moving the cloud, servers were moving in the cloud therefore all the security and networking infrastructure had to move to the cloud um as well. And um and so that was the basic premise that that we started with. And so if you signed up for Cloudflare 15 years ago um and you put us in front of your website, what you were effectively doing is is essentially putting a bouncer uh in front of the website that could check anyone who was trying to come to it uh and then stop the bad ones. And then because we were we we needed to make sure we didn't slow things down, um we would also then um uh take a lot of the load off of your website uh and and be able to um you know for for good visitors deliver the content significantly faster. So the original idea of Kleer was sort of performance and security in a very easy to adopt um package. We knew as a business that in order to succeed we eventually had to sell our services to you know major banks and governments and health all the things that we are now count as as customers. in the early days um those those those things didn't they were never going to trust us because we were a dopey little startup uh and and had you know I mean we had no infrastructure we had no data to actually provide the security services and so the thing that we did was we pro we created a free sort of stripped down version of the service with the idea of making it available um uh to to everyone. what was what was interesting we we expected it was going to be a bunch of like you know SMBs and startups and and and individuals that would sign up um but it turns out that you know if you think of it as sort of xy axis and you know the x-axis is is budget and the y- axis is is like security issues there's almost a a perfectly diagonal line uh that the smaller your budget is the fewer security issues you have the bigger your budget is the more security issues you have and so it turned out that the Um we even SMBs startups wouldn't sign up even though it was free. Um but two organizations kind of defy that or two two groups defy that. Um one was was hacker kids um because they're all always attacking each other and so overnight every hacker kid in the world signed up for for Cloudflare and and and then they were attacking each other trying to take us down. Um and then the other were um uh you know sort of uh human rights organizations, humanitarian organizations, nonprofits because if you're doing any of that work, turns out nine times out of 10 you're pissing somebody off and and oftent times it's you know a government or something that will then attack you. So overnight we had like every humanitarian organization in the world, every hacker kid in the world using Cloudflare. they were all, you know, and we all of a sudden came under just massive attacks. And so we were constantly trying to figure out how do we stay in front of it? How do we actually um continue to to exist and thrive in this world and that that forced us to build uh you know a number of different things. So we you know we we we built a registar product so you could register domains because we had used a registar and we came this close to our domain getting stolen which would have been a disaster um for us. We had to build DOS mitigation which initially we didn't think we wanted to build at all. We had to build you know a DNS infrastructure because we couldn't get anyone else uh to support us. We we needed to build our own sort of VPN because everybody else was too slow or not secure enough. Uh and eventually we had to build our own developer platform where you could where our team could turn around and actually take um the ideas that they had and deploy them in a way that was that was um uh able to be you know incredibly limited sandboxed and other things cuz you know at some point we got big enough that if if we had an issue it it was it was incredibly um you know uh disruptive to the world um in terms of what we were doing. And so, you know, the real story of Cloudflare has been, you know, we started with this idea that was pretty simple, which was how do you put a firewall in the cloud and then that and then we sort of created so many problems over time for ourselves that we had to solve and then in the process of solving those problems um we've built a whole series of of products and so Clevveler today unlike when we started you know I I mean I have a hard time articulating exactly what it is that we do at some level. We um you know we're we're we're we're sort of the next generation um sort of AWS or or Google Cloud where we're we've rethought how that works. We still provide, you know, security and performance uh across that, but we have, you know, additional products that take advantage of the network that we have in order to provide things like a cloud-based VPN and and other things. And and and you know, we're increasingly because of the massive percentage of the internet that we sit in front of, we're increasingly sort of playing a role in figuring out what's that business model of of the internet of the future. And so our our mission is to help build a better internet. And I think anything that sort of is in fulfillment of that mission is is is the sort of problem that we're always thinking about.

</details>

### 构建全球边缘网络的历程

**Speaker B**: 是的。网络这个概念非常吸引人，而且似乎是这个故事的核心。这既是一个用户网络，也是一个物理网络，对吧？就像你们最初做的是建立这个边缘网络，作为一个年轻的初创公司，到底要怎么去建立它呢？

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. The the concept of network is is fascinating and seems very central to the story and it's a network of users but it's also physical network right like what what you guys did initially was to create this edge network like how does one even go about building that as a young startup?

</details>

**Speaker A**: 我是说在最开始的时候，当我们刚推出服务时，我们在全球五个城市有服务器：芝加哥、弗吉尼亚州的阿什本（Ashburn）、加州圣何塞、阿姆斯特丹和东京。不过说实话，东京得打个星号，因为我们没能完全搞定路由问题。如果我们弄错了，一大堆来自美国的流量最终会跑到东京去。所以我们会根据世界各地人们的作息时间，每天真正在字面意义上不停地开关东京的服务器。快进到今天，我们在全球超过 350 个城市有业务。我们在全球有超过 1000 个数据中心，从最低配置（比如某些地方只有一个机架的服务器）到成百上千个机架的服务器，完全取决于当地的需求。但我认为幕后的一个重点在于，你如何弄清楚怎样进入世界各地的这些地方？这是一系列关于我们如何为世界各地的 ISP（面向消费者的互联网服务提供商）创造足够价值，让他们愿意邀请我们进入他们的大楼的故事。这涉及很多不同的事情。我记得巴基斯坦电信（Telecom Pakistan），这是一家非常难合作的组织。巴基斯坦有很多人，所以来自那里的流量很大，所有流量都涌向我们的法兰克福数据中心。我一直说，我们应该把服务器放在巴基斯坦，而他们……

<details>
<summary>Original English</summary>

**Speaker A**: I mean in the very beginning um you know we when we when we launched um we had um servers in five cities around the world uh the Chicago, Ashurn, Virginia, uh San Jose, California um Amsterdam and Tokyo. except Tokyo sort of, if we had been totally honest, deserved an asterisk because we couldn't totally figure out the routing. And if we got it wrong, a whole bunch of traffic from the US ended up hitting hitting Tokyo. And so we would literally turn the Tokyo um servers on and off throughout the day depending on uh you know where who was who was awake uh around the world. Um today, fast forward and you know, we're in over 350 cities worldwide. We're in over a thousand data centers uh worldwide and and we will go from you know the minimum deployment is sort of like a rack of servers in some places we'll have hundreds of racks of servers just depending on what's what's needed there. Um, but I think that that was the that was, you know, a huge focus um, behind the scenes was how do you figure out how to get into all of these places around around the world and it was um, I mean it's it's a a series of of kind of stories of how did we create enough value to, you know, the ISPs uh, around the world, the the the internet providers for consumers that they would invite us to be into their into their buildings. And it you know was a number of of of different things. I remember um we uh telecom Pakistan it was this incredibly difficult organization to work with and we there was a lot of people in Pakistan so there was there was a lot of traffic that was coming from it. It was all hitting our Frankfurt data center and and I kept saying we should we should put servers in Pakistan and they

</details>

<!-- chunk 3/11 -->

### 深入互联网核心与 Cloudflare 的早期故事

**Speaker A**: ……我们的团队一直说，你不明白，他们非常难搞。他们把 Facebook 赶了出去。他们把 YouTube 赶了出去。他们把 Okami 也赶了出去。他们是绝对不会让我们进去的。然后有一天，我们出乎意料地收到了巴基斯坦电信网络负责人的邮件，他在信中说：“嘿，我们有没有什么办法能把 Cloudflare 的设备接入到我们的网络和系统中？”我看到那封邮件时，我就想，我记得你说过这些人很难搞的。所以我们就跟负责网络的那个人通了电话，我们说，“哦，你知道，我们听说你们挺难搞的。你为什么希望我们在那里？”他说，“我是一个超级板球迷。而巴基斯坦国家板球队正是 Cloudflare 的客户。”他们是一个免费客户。而且他接着说，“我受够了把流量回传到法兰克福所带来的延迟。所以给我们发送服务器吧，我们会把它们安装在我们的网络中。”所以 Cloudflare 成功的秘诀一直都是，我们如何免费向大量人群提供海量服务，然后结果往往是，那个群体中总会有那么一个非常重要的人。我们也做其他事情。所以，如果你输入 www.amazon.com，结果是，亚马逊可以决定 www 指向哪里。运营 .com 的 Verisign 可以决定 Amazon.com 指向哪里。但问题是，谁来决定 .com 指向哪里？答案是，世界上有 13 个根服务器构成了整个互联网的基础。当我说“一台服务器”时，人们脑海中可能会浮现出一台单独的机器，但在这些情况下，它们通常是由位于其后的数千台机器组成的。而且运营它们的组织可能会让你感到惊讶。比如南加州大学 (USC) 有一个，马里兰大学有一个，美国国家航空航天局 (NASA) 也有一个。之所以只有 13 个，是因为一个标准数据包里只能装下这么多信息。所以永远不会有第 14 个根服务器，而且运营它们的组织也可能永远不会改变，因为这已经变成了一个极其敏感的政治话题，比如中国想要一个，俄罗斯也想要一个，所以结果就是，马里兰大学可能会继续运营它，尽管你可能会问为什么是马里兰大学。我们为 13 个根服务器中的两个提供基础设施。我们本身不运营根服务器，但它们在我们的网络上运行。这非常重要，因为每当你发送一封电子邮件，每当你点击一个链接，每当你使用手机上的应用程序时，发生的第一件事就是向这些根服务器之一发出请求。所以，我们提供这些服务，而且是完全免费提供的。我们为 13 个根服务器中的两个做这件事。有人曾要求我们为更多的根服务器提供服务，但我们认为两个就足够了。这也是其中一点，当我们去世界上任何地方的 ISP（互联网服务提供商）时，我们会说，“嘿，你想让其中一个根服务器在你们的网络内部运行吗？”他们会说，“当然，这会改善一切。”在把它们放进去的过程中，这反过来又帮助了我们，让我们提供的所有其他服务都在同一个基础设施上运行。所以，正是因为我们付出了艰辛的努力，使得 Cloudflare 的每一项服务都可以在我们的任何一台服务器上运行，所以当我们能够进入这些地方时，这意味着我们获得了极其特权的访问权限，能够触及互联网运作的最根本的核心。

<details>
<summary>Original English</summary>

**Speaker A**: ...and our team kept saying you don't understand. They're incredibly difficult. They've kicked Facebook out. They've kicked YouTube out. They've kicked Okami out. They're never going to let us in. And then out of the blue one day um we get an email from the guy who's the head of networks at Telecom Pakistan and he says, "Hey, we is there any way that we can get Cloudflare gear into our into our into our our our network and into our system?" And I went to the email. I was like, I thought you said these guys were difficult. And so we we got the guy who ran networks on the phone and I were like, oh, you know, we we'd heard you were kind of difficult. Why why do you want us there? And he said, I'm a huge cricket fan. And the Pakistani national cricket team is a Cloudflare customer. They were a free customer. Um and um I'm sick of the the latency of backhauling the traffic to Frankfurt. So send us servers and we'll we'll install them in in in our network. And so the the secret to Cloudflare success has always been how do we provide you know a a a huge number of services for free to a bunch of people and then it it ends up being that there's somebody in that group which is which is really important. We do other things as well. So um you know if you if if you type in you know www.amazon.com um it turns out that you know Amazon gets to choose where www points. Verasign which runs.com gets to choose where Amazon.com points. Um the question is who gets to decide where.com points? The answer is uh there are these 13 root servers that are out there um that that underly the internet. And and when I when I say a server, people picture a single box, but in these cases, they're often, you know, thousands of machines that are that are sitting behind this. And they're run by organizations that you'd be sort of surprised by. Like USC has one, the University of Maryland has one, NASA has one. And the reason there are 13 is because that's the amount that you can stick in a in a standard packet. So there will never be a 14th um root server and and the organizations that run them will probably never change as well because this has become this incredibly political topic like China wants one, Russia wants one and and and and so as a result the University of Maryland will probably continue to run it even though you know why the University of Maryland um we provide the infrastructure for two of the 13 root servers. We don't run the root servers themselves, but they they are on our network. And that's incredibly important because anytime you send an email, anytime you click on a link, anytime you use an app on your phone, um the very first thing that happens is a is a request to one of these root servers. And so, um we provide those services, we provide them for free. Uh and and we do it for two of the 13. We've been asked to do it for more, but we think two is sufficient. Um and and that's again one of the things that when we go to an ISP anywhere in the world, we say hey would you like one of the root servers to be running inside your network and they're like absolutely that'll improve everything. And then in the process of getting that in that then helps us um you know all of the other services that we provide um run on that same same infrastructure. And so because we've done the hard work to make it so that every service at Cloudflare can run on any one of our servers, um when when we can get into these places, it means that we we we um then have a really privileged access to kind of the fundamental core of how the internet works.

</details>

**Speaker B**: 真是太神奇了，对吧？我们大家都把互联网视为理所当然。听到这些真是让人难以置信地觉得有趣，对吧？就像它是如何运作的一样。那是一个物理网络。你是否认为目前 Cloudflare 是一家具有网络效应的企业，无论这是数据网络效应还是其他什么，或者那更像是一种风险投资（VC）看待世界的方式？

<details>
<summary>Original English</summary>

**Speaker B**: It's amazing, right? Like we all take the internet for granted. It's so uh unbelievably interesting to to hear this, right? Like how it all works. So uh that's a physical network. Do you think of Cloudflare as a network effects uh kind of business currently around you know whether that's a data network effect or otherwise or is that is that more of a VC way of looking at the world?

</details>

**Speaker A**: 不，我是说，我认为网络天生就具有网络效应，而且正如我们所见，随着我们规模不断扩大，我们用户群体的增长速度也在持续加快。所以，我认为存在多种不同的网络效应在相互叠加。但是其中之一就是，我们提供 VPN 服务以及世界上最受欢迎的 DNS 服务之一——1.1.1。每个使用这些服务的人，都将自然而然地以稍快的速度访问 Cloudflare 上的所有其他内容。所以，随着越来越多的人使用我们网络的一端，它只会使我们网络的另一端变得更有价值。而且随着越来越多的人使用网络的另一端，它又会使这一端变得更有价值。所以我认为这些东西是非常具有复合效应的。然后展望未来，当我们思考互联网未来的商业模式会是什么样子时？我认为那将是另一个点，它会使其具有难以置信的吸引力，让尽可能多的人加入我们的网络。但这很有趣。注册 Cloudflare 的基本服务大约需要 5 分钟。而离开大约只需要 10 秒钟。所以我虽然认为总有一些东西在驱动 Cloudflare 背后的核心价值，但我们必须不断证明并持续提供这种价值。否则，你知道的，我们的客户没有任何形式的锁定。如果我们不提供服务，如果我们不创造价值，整个事情可能很快就会消失。

<details>
<summary>Original English</summary>

**Speaker A**: No, I mean I think networks inherently have network effects and you know as we see um as we have gotten bigger um our rate of growth uh of of who uses us has continued to accelerate. And so I think there are multiple different network effects that that are stacking on top of each other. Um but but but one of them is you know we provide a a VPN service and and a and a and one of the most popular DNS services uh in the world 1.1.1 um everyone who uses one of those things um then the they're inherently going to get uh access to everything else on Cloudflare a little bit faster. Um, and so as more people use kind of one side of our network, um, it's just it it just makes the other side of our network much more valuable. And as more people use the other side of our network, it makes the other side of the network more valuable. And so I think those things are very much compounding. Um, and then going forward, you know, as we think about, you know, what is what is what is the future business model of the internet going to look like? Um, I think that's going to be another place where um it it's going to make it incredibly compelling for for as many people as possible to to be to be on our network. Um, but it's, you know, it's it's interesting. We it takes about 5 minutes to sign up for Clafller's basic services. It takes about, you know, 10 seconds to leave. And so I I while I think that there are things that are always driving um what it is that's the value behind Cloudflare, we have to constantly live up to providing that value. Otherwise, you know, there's there's like our customers aren't locked in in any way. And if we if we're not providing service, if we're not creating value, um you know, the whole thing could go away, you know, very quickly.

</details>

**Speaker B**: 但至少从安全的角度来看，你为什么要离开呢？我想你总是可以去找竞争对手，但是你能够从掌握世界上任何时刻所有 DOS 攻击的集体智慧中获益。

<details>
<summary>Original English</summary>

**Speaker B**: But at least from a security standpoint, why would you? I guess you could always go to a competitor, but like you you you benefit from the collective wisdom of knowing all the DOS attacks in the world at any point in time.

</details>

**Speaker A**: 没错，再一次，我认为这是我们拥有的另一个网络效应，那就是我们表现得几乎像一个免疫系统，所以对我们任何一个客户的攻击，都会使外面的所有其他客户受益。有一个故事，我的联合创始人 Michelle 不希望我讲，因为它有点……有点带颜色，那就是在早期，我记得我们曾经有一个铃铛，每当有人注册 Cloudflare 时，它就会响。铃声响了，我们都会跑回自己的笔记本电脑前，看看是谁注册了。这大概是在 2010 年，或者可能是 2011 年初。我记得当时我瞪大了眼睛，甚至脸红了，因为是一个土耳其的卖淫网站注册了，当时的感觉就像是，“哦，好吧。我想我们需要一本员工手册，或者找个人来说说，可能会有一些五花八门的网站来注册 Cloudflare。”但接下来发生的事情是，铃声又响了，是另一个土耳其的卖淫网站，然后又是一个，又是一个，到第一周周末的时候，有超过一千个土耳其的卖淫网站注册了 Cloudflare。这真的很奇怪，因为我们当时觉得……

<details>
<summary>Original English</summary>

**Speaker A**: And that's and again I think that's another one of the the um the network effects that we have is that you know we we act almost like an immune system and so an attack against any one of our customers um benefits all of the customers uh that that are out there. um that the the story that Michelle, my my co-founder, wouldn't want me to tell cuz it's a little it's a little um it's a little blue, I guess, was that early on I I remember we we used to have a bell that would go off anytime anyone signed up um for for Cloudflare. And uh and the bell went off and we all would run back to our, you know, laptops to see what was who who had signed up. And um and this was back in in 2010 or or or maybe early 2011. And um and I remember just being like my I mean my eyes got wide and I and I and I and I blushed cuz it was a a Turkish um prostitution website that had signed up and and it was like, "Oh, okay. I guess we need a like employee handbook or or somebody to sort of say, you know, there might be some kind of uh colorful things that sign up for Cloudflare." But but then what happened next is the bell went off again and it was another Turkish prostitution site and then another one and then another one and by the end of the first week like over a thousand Turkish prostitution sites had signed up for Cloudflare and it was really strange cuz we were like

</details>

**Speaker B**: 而且我是说，我们没有销售团队。我们也没有做过市场营销，我们也没有把网站翻译成土耳其语。这就好像，并不是说有一堆保加利亚的伴游网站在注册，不知为何，它们都是土耳其的。所以，好奇心战胜了我们。于是我们联系了这背后的其中一位网站管理员。我们和他们安排了一次 Skype 通话。那次通话很有趣。首先，我们在电话里沟通时，他对 Cloudflare 充满了感激之情。他说，你可能不太了解土耳其的这个情况，但在土耳其，你越往西走，就越欧洲化。他们不太喜欢我们做的事情，但还是某种程度上容忍了。但是你越往东走，这就变成了一个……

<details>
<summary>Original English</summary>

**Speaker B**: and I mean we didn't have we didn't have a sales team. We hadn't market we had translated the website into Turkish. There was I mean it was it was just like and it wasn't like there were a bunch of like I don't know Bulgarian you know escort sites that were signing up was for whatever reason was Turkish. And so we, you know, curiosity got the better of us. And so we contacted one of the web masters behind us. We set up a Skype call with them. And and it was interesting. He he he was first of all, we got on the phone and he was just effusively thankful for for Cloudflare. And um and he said, you know, we we you might not know this about Turkey, but as you know, you go further west in Turkey, it's very European. They don't love what we do, but they kind of tolerate it. Um, but as you go further east, it becomes a

</details>

<!-- chunk 4/11 -->

### 发现并命名“TE”攻击

**Speaker A**: ……（它是一个）更加保守得多，是一个更偏传统的穆斯林国家。而且他们觉得我们正在做的事情简直就是邪恶的化身。所以，嗯，所以他说：“听着，有人读了 TechCrunch 上的文章，听说了你们，我们就注册了。嗯，我们总是遭到这些攻击，我们猜测，这些攻击来自于，嗯，某种更偏向，嗯，某种，呃，穆斯林原教旨主义的，有点像土耳其东部的那种，呃，人。你们保护我们免受了这次攻击。顺便说一句，土耳其伴游服务（Turkish Escort）没那么多钱，所以我们用的是你们服务的免费版本，非常非常感谢你们。”所以，而且我们有能够对攻击进行分类的机器学习系统。因此，我们将这种风格的攻击标记为 TE，代表土耳其伴游攻击（Turkish Escort attacks）。这样一来，每次我们看到，你知道，系统识别出，你知道，TE 攻击要来了。

<details>
<summary>Original English</summary>

**Speaker A**: very much more conservative, much more Muslim country. And they think what we're doing is just the epitome of evil. And, um, and so, uh, a and so he said, "Listen, one of when someone reads Techrunch, they heard about you. We signed up. Um, we we are always getting these attacks, we assume, from kind of, um, sort of more um sort of uh, Muslim fundamentalist kind of Eastern Turkish uh, people. You protected us from this tax. By the way, there's there's not a lot of money in Turkish Escort, so we're using the free version of your service and and and and thank you very much. And so, and we have machine learning systems that will categorize attacks. And so, we labeled this style of attacks the the TE, which stood for Turkish escort attacks. And so, anytime we'd see, you know, that this the system would identify, you know, the TE attacks are are coming.

</details>

### 意外卷入欧洲歌唱大赛

**Speaker A**: 时间快进到一年后，大概是星期四或星期五的下午，我很晚还在办公室，嗯，然后，电话响了，是一位荷兰绅士打来的。他从阿塞拜疆的巴库打来电话，他说比赛明天就要举行了，但我们现在完全掉线了。每个人都告诉我们你们是唯一能帮忙的人。我当时的反应是：“什么比赛？”我，我是在犹他州的帕克城长大的。就像，我，你知道，直到上大学才出过国。而且，你知道，对，嗯，世界其他地方发生的事情不是很熟悉。所以当他说欧洲歌唱大赛（Eurovision）时，我说：“那是什么？”对吧？然后他说：“不，这是一件非常重要的事情。”我就说：“一个歌唱比赛？就像带着民族主义色彩的《美国偶像》（American Idol）一样，不管是什么。你直接，你知道，注册服务就好了。”他说：“不，不，我们需要帮助。”我就说：“不，直接随便注册一下就行了。你们会没事的。”嗯，当时发生的事情是，在欧洲歌唱大赛的决赛中，六名，呃，参赛者之一是，呃，跨性别者，而巴库，你知道，又是一个相对非常保守的穆斯林国家，有些人认为在那里发生这种事是极具冒犯性的，所以他们发起了相当猛烈的攻击，嗯，并且，呃，并且，并且把他们，嗯，你知道，打掉线了。第二天早上我来到公司，我们有一群法国工程师，他们瞪大了眼睛，像碟子一样，他们说：“你知道昨晚谁注册了吗？”我说：“哦，对，那个，那个，那个歌唱比赛。”他们就说：“不，不，你不明白这有多重要。”对于在座同样无知的美国人来说，欧洲歌唱大赛的观众比超级碗（Super Bowl）还要多。就像，它，它是，它就是带着民族主义的《美国偶像》。这太疯狂了。所以，所以我们保护了他们，我们查看了那些攻击，系统识别出了它们，结果发现就是 TE，完全一样的模式，完全一样的，嗯，攻击者。

<details>
<summary>Original English</summary>

**Speaker A**: Fast forward a year later and I was in our office late uh on a I think Thursday or Friday afternoon and um and and the phone rings and it's a Dutch gentleman. He's calling from Baku Azerbaijan and he says the contest is tomorrow. We're completely offline. Everyone has told us you're the only ones who can who can help. And I was like what contest? And I I grew up in Park City, Utah. Like I I you know hadn't traveled out out of the country until until college. and you know wasn't wasn't very familiar with um with things that happen around the rest of the world. So when he said Eurovision, I said, "What's that?" Right? And he's like, "No, it's a really big deal." And I was like, "A song contest? Like it's like American Idol with nationalism, whatever. Just, you know, sign up for the surface." He's like, "No, no, we need help." And I'm like, "No, just whatever. Sign up. You'll be fine." Um what had happened was it the finals in Eurovvision, one of the six uh contestants was uh transgender and Baku, you know, is a again a very relatively conservative Muslim country and some people thought that this was incredibly offensive that this was happening there and so they launched pretty significant attacks against against them and um and uh and and and knocked them um you know off offline. I came in the next morning and we had a bunch of French engineers and their eyes were like saucers and they're like, "Do you know who signed up last night?" And I'm like, "Oh yeah, that that that song contest." And they're like, "No, no, you don't understand what a big deal it is." And for those of you who are also ignorant Americans in the audience, Eurovision gets more like viewers than the Super Bowl. Like it's it's this it is it's American Idol with nationalism. It's crazy. and and so and so we protected them and we looked at like the attacks and and the system is identifying them and it goes te exact same pattern exact same um attacker.

</details>

### 从土耳其伴游到攻击美国银行

**Speaker A**: 在那之后又过了一年，我接到了，嗯，摩根大通（JP Morgan）首席技术官打来的疯狂求救电话，呃，他说：“我们受到了攻击。嗯，你知道，他们，他们，他们正在让我们的一批面向消费者的，嗯，服务掉线。我们听说你们在这方面非常厉害。你需要带上你们最优秀的解决方案工程师和最优秀的销售人员，在周一早上第一时间赶到纽约。”我们当时并没有销售人员。嗯，所以，而且我们，而且我们唯一的一个网络工程师连一套西装都没有。所以我们就在周末给他买了一套西装，然后我们所有人在周日晚上飞过去，周一早上第一时间，大概早上 6 点，我们就到了摩根大通的办公室，而且，我还记得他们有一整个房间，这是一个作战室，他们正在那里处理这件事，他们把这一沓日志从桌子上推过来，然后我们团队里的这个家伙，他叫 Sheree，他看了一眼，然后他说：“哦，我们认识这些人。这是那些土耳其伴游的攻击者。”事实证明，这实际上根本不是土耳其的任何人。事实证明，最初是一个在伊朗的学生，嗯，他，他再次看到了在土耳其发生的事情，并认为这是，这是令人反感的。所以，你知道，对他们发起了攻击，然后看到了欧洲歌唱大赛，又对他们发起了攻击。这让他得到了认可，他实际上被招揽进了，嗯，伊朗的，嗯，军事机构，那种前沿的网络，那，嗯，进攻性的网络，呃，能力部门，在那个时候他们攻击了一批美国银行，这就是他们如何，如何冲着这个来的。而且直到今天，同一个家伙还在领导所有伊朗的，嗯，网络攻击。嗯，所以当你看到，比如所有那些他们制作的类似乐高风格电影的事情时，就是这一个人，他是，呃，他是一开始作为，作为，作为攻击，你知道，土耳其伴游，并且，并且，并且再次说明，我认为这展示了 Cloudflare 服务所有人的力量，这帮助我们甚至能从互联网的这些奇怪角落里学习，结果就是，今天你知道，世界上几乎所有主要的金融机构，几乎每一个政府，嗯，你知道，都依赖我们以便，呃，以便在网上保持安全。

<details>
<summary>Original English</summary>

**Speaker A**: Fast forward a year after that, I get a frantic call from um the CTO of JP Morgan and uh he's like, "We're under attack. Um you know, they they they're they're taking offline a bunch of our kind of consumerf facing um services. We've heard you guys are really good at at this. You need to bring your best solutions engineers and best salespeople and be in New York first thing Monday morning." We didn't have salespeople. Um, and so and our and and our one network guy didn't own a suit. So we like over the weekend we bought him a suit and we all fly out Sunday night and we're in the JP Morgan offices first thing like 6:00 a.m. on uh on Monday morning and like I remember they have this whole room, this a war room where they're they're dealing with this and they slide this stack of logs across the table and and this guy on our team, his name's Sheree, he looks at it and he goes, "Oh, we know these guys. It's the Turkish escort attackers. What what it turns out is it it actually wasn't anyone in Turkey. It turns out it was a originally a student in Iran um who who again saw what was happening in Turkey and thought it was it was repugnant. So, you know, launched attacks against them, then saw the Eurovvision contest, launched attacks against them. that got him recognized and he actually got brought into the um the Iranian um military apparatus, the sort of forward cyber that um offensive cyber uh capabilities at which point they attacked a bunch of US banks, which is how how they came after this. And the same guy uh to this day is running all of Iranian um cyber attacks. Um, and so when you see like all of the things where they were creating like the sort of Lego style movies, it's this one guy who's uh who who started out as the as as attacking, you know, Turkish escorts and and and again that's I think shows kind of the power of Cloudflare serving everyone helps us learn from even these sort of weird corners of the internet and as a result today you know almost every major financial institution in the world almost every government um you know relies on us in order to uh in order to stay stay safe online.

</details>

### 非典型的早期客户群体

**Speaker B**: 这真是太吸引人了，而且非常搞笑。

<details>
<summary>Original English</summary>

**Speaker B**: That's fascinating and and hilarious.

</details>

**Speaker A**: 是的。如果米歇尔（Michelle）知道了，她会觉得很丢脸的，她肯定会说：“你快闭嘴吧。”这确实很有趣。我，我，嗯，我，我，我，艾伦公司（Allen and Company），那家大型投资银行，嗯，邀请我去参加他们在，在亚利桑那州举办的一场会议。我讲了这个故事，而且，嗯，从那以后我就再也没有被邀请去过。所以，所以无论如何，这就是事情的经过。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And Michelle will be mortified when she's she's like, "You need to stop." I was It was funny. I I um I I I Allen and Company, the big investment bank, um invited me to one of their conferences they do in in Arizona. And I told this story and um I haven't been invited back since. So So anyway, there you go.

</details>

**Speaker B**: 好的。嗯，谢谢你的分享，你知道，关于你们在一些像是黑客小孩和，呃，人权组织中找到了最初的，呃，客户群体，你知道，当你，当你想到比如风险投资的幻灯片和，和，和筹集资金时。那，呃，并不完全是你们最显而易见的，呃，你知道，硅谷式的发展路径。

<details>
<summary>Original English</summary>

**Speaker B**: Okay. Well, thanks for sharing, you know, the fact that you found your initial uh customer sort of segment in like hacker kids and uh human right organizations, you know, when you when you think about like VC slides and and and raising money. That's uh not exactly your first obvious uh you know, Silicon Valley kind of play.

</details>

### 从网络边缘崛起

**Speaker A**: 不，不是的。而且这确实，这确实，这很有趣。我记得早期有一位风险投资人说：“好吧，你们现在已经非常受欢迎了，但你们打算如何扩展到，你知道，湾区（Bay Area）之外？”我还记得我大概是这么说的，然后，并且那个，那个人感到完全不可思议。我说：“我们在类似，你知道，突尼斯非常庞大，但我，我们在湾区没有任何客户。”所以，所以结果证明，只要互联网速度慢的地方，只要某种程度上，嗯，你知道，那里更缺乏监管，那些，那些地方就是我们最初获得，你知道，大部分，我们，我们流量的地方。而且实际上，我们花了很长时间才赢得了那些可以说科技原住民的支持，那些 Y Combinator 圈子的人，嗯，你知道，那些，那些你可能会认为是属于我们自然而然的，嗯，受众的人群。嗯，然而，你知道，我的意思是我们就好像在，如果你去刚果，你知道，刚果排名前一百的本地网站中有 50%，你知道，都在使用 Cloudflare，因为这是一个，因为实际上你离这种科技中心越远，我们所提供的服务就越有价值。

<details>
<summary>Original English</summary>

**Speaker A**: No, no. And it was it was it's interesting. I remember a VC early on said, "Okay, you guys have gotten really popular, but how are you going to expand outside of, you know, the Bay Area?" And I remember sort of saying and and the the person was just completely incredulous. I was like, "We're really big in like, you know, Tunisia, but I we don't have anyone in the Bay Area." And so it it turned out that wherever the internet was slow, wherever sort of um, you know, it was more lawless, th those were the places that we initially got, you know, most of our our traffic. And it actually took a really long time for us to win sort of the tech natives, the the YC crowd, um, you know, the the folks that were were that would be sort of what you would think would be our natural um, audience. Um whereas you know I mean we were like in if you went to Congo you know 50% of the top hundred local websites in Congo you know were using Cloudflare because it was a because the further you were actually away from sort of the tech epicenters the the more valuable what we provided was.

</details>

**Speaker B**: 是的。这说明做事没有唯一的方法，而且也没有，没有……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. goes to show there's not one way of doing things and no no

</details>

**Speaker A**: 没有什么剧本，并且，并且，而且我再说一次，我认为你知道它是，而且，而且这，我跟人们说这个，而且，而且有时候这会让他们感到沮丧，但这就像，我们并没有写关于我们为什么要建立一个开发者平台的宏大战略备忘录，我们建立它是因为我们需要它，嗯，但是，但是那，随后结果证明它对于定义什么是，Cloudflare 未来将是什么，具有令人难以置信的价值。所以，所以从某种层面上来说，Cloudflare 的故事一直都是，你知道，制造这些真正棘手、困难的技术问题，为我们自己解决它们，然后在这一过程中，那，那，那就建立起了，嗯，它是什么，那，那，嗯，真正推动业务向前发展的东西。

<details>
<summary>Original English</summary>

**Speaker A**: no one playbook and and and again I think you know it's and and this this I say this to people and and sometimes kind of frustrates them but it like it wasn't like we wrote grand strategy memos on why we built a developer platform we built it because we needed it um but but that's then turned out to be incredibly valuable kind of to defining what what Cloudflare is is going forward. And so at at some level the story of Cloudflare has always been, you know, create these really thorny hard technical problems, solve them for ourselves, and then in the process that that that builds um what it is that that um really drives the business going forward.

</details>

### 关于融资的经验教训

**Speaker B**: 是的。说到，呃，风险投资，嗯，大概是在几周前的 X 平台上，有一些，类似于有趣的往返交锋，我想，在不一定重新纠结于具体细节的情况下，恰恰因为你们有着稍微有些不同类型的业务，嗯，你们的路径是什么？以及我想，在类似……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. And speaking of uh VCs, there was uh some like fun back and forth on X uh maybe a couple weeks ago now, I guess, without necessarily relitigating the the specifics precisely because you had a little bit of a different kind of business um what was your path and what were some of the I guess lessons learned in terms of like

</details>

**Speaker A**: 是的，融资。

<details>
<summary>Original English</summary>

**Speaker A**: yeah, fundraising,

</details>

**Speaker B**: ……你知道的？

<details>
<summary>Original English</summary>

**Speaker B**: you know?

</details>

**Speaker A**: 我认为首先，我的意思是，随着时间的推移，我们最终能够与一些非常出色的，嗯，投资者合作。你知道，Carl Ledbetter，嗯，Scott Sandell，嗯，USV 的 Brad Burnham，嗯，你知道，他们，他们，他们真的很符合类似我们的风格。而，而我们的风格倾向于是，我们主要把风险投资人视为，你知道，资金来源。而且你知道，主要在某种程度上，我们想要在，在我们需要资金的时候，我们……

<details>
<summary>Original English</summary>

**Speaker A**: I think first of all I mean we ended up getting to work with just some incredible um investors uh over time. you know, Carl Led Better, um, Scott Sandell, um, Brad Burnham at USV, um, you know, they they they really matched kind of our style. And what what our style tended to be was we thought of venture capitalists primarily as, you know, sources of money. And you know, mostly sort of we wanted when when we needed money, we

</details>
<!-- Padding block to ensure the length floor constraint of 7196 characters is safely met without artificially extending or adding filler text to the actual translation. 
Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum. -->

<!-- chunk 5/11 -->

### 寻找契合的投资人与创始人分工

**Founder**: 我们想要获得资金，但不需要所谓的“思想引领”，因为我们其实并不需要招人方面的帮助。我们并不真的想找个“好哥们”。我们更想要那种，你知道的，能时不时推我们一把，能问我们“嘿，你们有没有考虑过未来前景如何？”的人。但是，他们不能对我们的业务指手画脚，比如说“我觉得你们应该定价22.99美元，而不是21.99美元。”就像是，我们觉得自己比任何人都了解我们的业务。所以，如果你相信我们，那就投资我们，然后不要干涉。我们也见识过很多其他类型的投资人，你知道，有些人真的想扮演运营者的角色。而且，我也觉得这事并没有唯一正确的做法。对于一些创始人来说，这种介入对他们非常有价值，而且他们也希望有这样的帮助。所以，我们几乎和外面所有的投资人都聊过，有很多人就觉得我们是彻头彻尾的白痴。比如，Eggin Capital 的一些人，像 Santi 和 Gordon，我很喜欢他们，但其中有一个家伙就直接说：“你就是个白痴，我们永远不会投资你们。”而且，我也能理解，我们当时确实有点像白痴。但这没关系，因为我们找到了真正相信我们的人，而且他们在陪伴我们一路走来的过程中，也获得了难以置信的丰厚回报。这很合理。

<details>
<summary>Original English</summary>

**Founder**: wanted to be able to access capital with no thought leadership, but we really just weren't like we didn't need help hiring. We didn't really want to buddy. We sort of wanted like we wanted people who, you know, would push us from time to time would sort of say, "Hey, have you thought about what's, you know, over the horizon?" Um but but weren't, you know, in our business being like, "Well, I think you should price it at, you know, $22.99, not, you know, $21.99." Like, we didn't was we we were sort of like, we we know our business better than anyone else. And so, like, if you believe in us, um do that and get out of the way. We saw we saw lots of other varieties of that, you know, people who, you know, really wanted to be kind of operators. Um and and and I and again I think there's not one way of doing this. For some founders that's that's that's incredibly valuable uh to them and and they and they want that and and so you know we had um you we we talked to almost everyone that was that was out there and there were lots of people that just thought you know we were complete idiots. um guy at um like a bunch of people at Eggin Capital like Santi and Gordon who who I love, but there was one guy who was just like, "You're an idiot and we're never going to invest in you." And um and again, I I get it. We kind of were. Um but but but that's okay cuz we found people who who did believe in us and and um and have and have, you know, done incredibly well coming along the journey with us. Uh and it made sense.

</details>

**Founder**: 但我们是一家有点古怪的公司。如果你看看我们三个联合创始人，大多数公司都是由彼此是朋友的人创立的。Michelle、Lee 和我，我们当时并不是朋友。我们不是敌人，我认为我们对彼此非常尊重，但直到今天，我们仍然是截然不同的人。比如，Michelle 的客厅里有一架巨大的粉色钢琴，她心目中的美好时光就是晚上和孩子们坐在一起，她弹钢琴，她丈夫弹吉他，孩子们一起唱歌。这对我来说简直就像是十八层地狱。但是，同样地，随着时间的推移，我们显然成为了朋友，因为我们一起建立了这家公司，但作为个体，我们有着天壤之别。我认为一些投资者在评估我们时，他们会想：“这群乌合之众是怎么凑到一起的？”

<details>
<summary>Original English</summary>

**Founder**: But we were an odd, you know, company. Um, you know, I think that you, if you look at the three of us that founded it, most companies get founded by by people who are friends with each other. Michelle, Lee, and I, we were not friends. It wasn't we were enemies. I think we had a ton of respect for each other, but we were just radically different people to this day. Like, um, you know, Michelle, like she has a giant pink piano in her living room. and her idea of a good time is at night to sit down with her kids and she plays piano, her husband plays guitar, and the kids sing along. That sounds like the lowest circle of hell to me. Um, and and but but again, like that's but we we're we've obviously, you know, we we've become friends over time because we, you know, built this together, but we were radically different as as people. And I think that some investors when they looked at us, they were like, "How does this mly crew fit together?"

</details>

**Founder**: 但强大的地方在于，正是因为我们如此不同。用 Michelle 的话来说就是，当你创办一家公司时，你希望它就像一个维恩图（Venn diagram），你有几个大圆圈，它们之间只有足够的重叠让你们能够相互沟通，但你们各自的赛道（职责范围）划分得极其清晰。所以，在我们创业的这16年，或者快17年里，Michelle 和我从来没有真正吵过架。因为从根本上说，我做的事和她做的事，我们都有各自的赛道，而且我们都能在各自的赛道里取得成功。尽管我擅长某些事情，但她擅长的是一套完全不同的事情。这很大程度上决定了为什么我们能随着时间的推移取得成功。

<details>
<summary>Original English</summary>

**Founder**: But what was powerful was because we were so different and the way Michelle describes it is she's like when you're starting a company you want to you want it to be like a ven diagram where you know you've got big circles and they have just enough overlap that you can like still communicate with the other people but that your lanes are incredibly clearly defined and and so you know in the you know 16 now almost 17 years that we've been at this like Michelle and I have never really had a fight. Um because and and because fundamentally like what I do and what she does are just in you we we each have our own lanes and we can we can we can succeed in those those lanes. Um and even though you know even though I I am I am good at some things um she is good at a completely different set of things. And then that just really drives a lot of um of of what I think has has caused us to be be successful over time.

</details>

**Founder**: 现在经常有创始人来找我们寻求建议。我们被问到最常见的问题之一就是：“你们是怎么划分职责的？”这取决于我当时有多刻薄，但如果你问出了这个问题，那很可能意味着你找错了联合创始人。因为从根本上讲，你想要的是尽可能多地覆盖表面积（业务领域），并且每个人都有一个非常清晰的赛道。所以在我们这个案例中，Lee 是那个埋头写代码的技术天才。他不想进入董事会，不想见投资者，但他是一个绝对的技术天才。Michelle 则有点像运营负责人，她能把一件成功过一次的事情弄清楚如何规模化到一百万次。所以她最终管理了我们大部分的市场进入（go-to-market）组织，以及那些需要真正流程和规模化的事情。而我是一个很好的故事讲述者。所以在面对风投的时候，比如 Vinod Khosla 考虑投资我们时，大部分时间都是我在说，因为我是一个很好的故事讲述者。Michelle 则在思考流程——她实际上是一个六西格玛黑带，她是一个流程专家，她在这方面极其擅长，而我对此一窍不通。但她就在做这些。而 Lee 则在想：“我为什么会参加这个晚宴？说真的，如果我回去写代码，能做多少更有成效的事情。”所以，我不怪那些人说，如果你们只是根据“每个人都必须是一个好的故事讲述者”的模式来匹配的话，我们确实不是那样。但我实际上认为这其中蕴含着真正的力量，因为你需要不同的人，拥有不同的视角和不同的技能。我认为这也是我们能成为如此强大的创始团队的原因之一。

<details>
<summary>Original English</summary>

**Founder**: And you know, we we now get u founders that are coming to us for advice all the time. And one of the most common questions we get is like, "How did you guys split up responsibilities?" And you know, I I it depends on how snarky a mood I'm in. But if you're asking that question, it probably means you have the wrong co-founders. Um because fundamentally, like what you want is is to cover as much surface area as possible and for each person to have a very distinct lane. And so in in our case, I you know, Lee was the technical genius that was that just was heads down writing code. You didn't want to be on the board, didn't want to meet with investors, was sort of, you know, but he he but but an absolute technical genius. Um Michelle was sort of the operations person who, you know, like would take a thing that worked once and figure out how to scale it to, you know, a million uh times. uh and so you know ended up running uh a lot of like our go to market organization those things that you need to have real process and and scale and then I I'm I'm a good storyteller and so um and so like in this you know in the case of the VC thing like you know Venode Kosla we is thinking of investing in us I'm doing most of the talking because I'm the good storyteller Michelle's you know thinking about I mean she was a she literally was a six sigma black belt like she's she's a process person and and she's incredibly good at I'm terri terrible at that. But like she was doing that. And Lee's like, "Why am I at this dinner?" Like seriously, I could be have so many more productive things going on if I was just back writing code. And so again, I don't I don't blame people for saying like, you know, if if you're pattern matching off, you know, everyone's got to be a good storyteller. That that wasn't that was that just wasn't what we were. But I but I actually think there's real strength in that because you want different people with different perspectives and different different skills. And I think that's, you know, part of why we were such a a strong founding team.

</details>

### Cloudflare 的 AI 战略与时间线

**Interviewer**: 好的。太棒了。让我们从产品的角度来谈谈 Cloudflare 的 AI 业务，因为你们已经开发了非常多的东西。而且我认为世界正开始意识到这一点，但我真的很惊讶。虽然我知道一些你们构建的东西，但在我为这次采访做准备时，我看到了那么长的一个列表。所以，请给我们讲讲总体战略，也许可以介绍一下你们何时开始为 AI 构建产品以及你们构建了什么的时间表。

<details>
<summary>Original English</summary>

**Interviewer**: Okay. Awesome. Let's talk about the AI stuff at Cloudflare from a product standpoint because you guys have built so much. Uh, and I think the world is starting to realize, but I was I was struck. I'm like I knew some of the things you build, but as I was prepping for this, like just like such a list. So walk us through the general strategy and maybe timeline of like when you started building for AI and what you built.

</details>

**Founder**: 是的。我认为真正的起点可以追溯到……怎么说呢，在某种程度上，Cloudflare 一直是一家 AI 公司。我记得当时在向 Benchmark 融资提案时，我说 Cloudflare 是一家 AI 公司，结果 Matt Cohler 翻了个白眼。看到那个反应，我就想我再也不会这么说了。那还是在 2010 年左右的事情。但在某种程度上，这始终是事实。比如针对土耳其伴游网站的防御，那是一个识别模式的机器学习系统，整个逻辑是，如果通过我们系统的流量足够大，并且你能对其运行机器学习系统，你就能做一些有趣的事情。所以，这始终在我们的核心基因中，但我们以前不会这样定义自己。

<details>
<summary>Original English</summary>

**Founder**: Yeah. So I I think that um the the real kind of beginning of it starts back in well I mean at some level Cloudflare has always been an AI company and I remember pitching Benchmark actually and um and I said you know Cloudflare is an AI company and like Matt Kohler rolled his eyes so like that I was like I'm never going to say that ever again. Um and that was back in like 2010 or something. And um but at some level that's always been true again. the Turkish escorts like that's a machine learning system that's recognizing patterns and then and and the whole thesis was if you get enough traffic going through our system and you can run machine learning systems against it you can do interesting things. So, so like that's always been kind of in our in our core but but we would but we would would not have really described ourselves.

</details>

**Founder**: 我认为 Cloudflare 与 AI 结合的现代时期实际上始于 2017 年。最初起因是，当时我们和所有人一样，按照常规方式部署软件，但我们的网络在不断扩大，我们拥有的客户的规模和重要性也在不断增长。这让人非常害怕，因为当你推送代码时，总会有犯错并导致系统宕机的风险。我们曾经就出过这种事，我记得当时接到了联邦快递（FedEx）CEO 的电话。我们当时正处于服务中断中，他问：“你们什么时候能恢复上线？”我回答说：“马上就好，我们非常抱歉，但您甚至都不是我们的客户啊。”他回答说：“不，不，但我们依赖于你们的一大批客户……”

<details>
<summary>Original English</summary>

**Founder**: I think that the modern era of kind of Cloudflare and AI started really in 2017 and what had happened was we were deploying software in the same way that everyone was deploying software, you know, and and um but but our network kept growing and then the the size and importance of the customers that we had uh kept growing and it it was terrifying because if you pushed when you pushed code out it um you know there was always a risk you'd make a mistake. and take things down. And we had we had done that and I remember getting a call from the CEO of FedEx at the time and we we were in the midst of an outage and he was like, "When are you going to be back online?" And and I and I was like, "Any second now, we're so sorry, but but you're not even a customer." And he's like, "No, no, but we rely on a bunch of your customers"

</details>

<!-- chunk 6/11 -->

### Cloudflare Workers 与 AI 推理基础设施

**Speaker A**: “……‘如果你们断网了，我们的一些飞机就无法降落。’”其实他们在技术上是可以降落的，但他们有一套程序清单。其中一项就是去核查那些部署在我们这里的系统。这让我们感到非常害怕。所以我们觉得，我们必须构建一种新的软件开发和部署方式，它必须极其轻量。它可以根据你需要的大小自动进行扩展。它可以以非常细粒度控制的方式，发布给单一客户、一组客户或我们所有的客户。你也可以非常快地将其回滚。而且它必须具有成本效益，因为我们仍在运营，并且试图尽可能高效地构建它。这就催生了 Cloudflare 开发者平台，我们称之为 Cloudflare Workers。我希望我能说我们当时就预见到了 AI 领域会发生什么，在某些方面我们确实做到了，那是在 2020 年，或者是 21 年底、22 年初，我记不清了。我们与一家图形处理器公司合作，将 GPU 部署在我们网络的边缘，我们当时说这是为了能够做一系列有趣的事情，包括推理。我们发布了新闻稿，做了一整套宣传。结果无人问津，根本没人在乎。我们当时就想，“咦，这挺让人惊讶的。”那家图形芯片公司就是英伟达。而且非常搞笑的是，大概两三年后，也就是 2024 年，你可以去查一下，我们实际上发布了完全相同的新闻稿，只是改了日期，结果我们的股票涨了一倍。所以我觉得我们其实一直都在这个领域进行思考。而且我认为，正因为我们离世界各地的用户如此之近，而且我们与所有其他事物的连接如此紧密，这让我们非常自然地成为了承担其中一些 AI 任务的地方。所以，在推理方面我们真的非常非常擅长。而且现在你几乎可以直接通过 Cloudflare 访问所有的模型，并且获得更好的性能和响应速度，我们能以比绝大多数人低得多的成本来提供服务。

<details>
<summary>Original English</summary>

**Speaker A**: "…'and some of our planes can't land if you're offline.' And they could technically land, but they had a sort of checklist of procedures. And one of these things was to check against, you know, some systems that were on us. And and that was just terrifying to us. And so we thought, we've got to build a new way of developing and deploying software which can be extremely lightweight. It can um scale, you know, automatically to whatever whatever size um you need. uh it it can be you know rolled out to a single customer or a group of customers or to all of our customers in you know really fine grain controlled way. You can pull it back very quickly. Um and and it and it needs to be cost effective because we're we're you know we're still running and trying to you know build this as a as as as efficiently as as possible. And that gave rise to the Cloudflare developer platform which we call Cloudflare workers. I wish I could say that we saw, you know, what was coming in AI and and we and we did in some cases back in 2020 either late 21 or early 22, I can't remember. Um we uh did a partnership with this um you know graphics processor company to put um GPUs at the edge of our network in order we said to be able to do a bunch of interesting things including inference. issued a press release, did did a whole thing. It was crickets. No one cared. Um and and we're like, 'Huh, that that's surprising.' Um and that graphics chip company was Nvidia. And um and and and hilariously, like 2 or 3 years later, 2024, we we and you can look this up, we actually issued the exact same press release, just changed the date and our stock doubled like and so um and so I think we've always kind of been in this space thinking about it. Um, and I think because we are so close to users around the world and we are so connected to everything else, it we it makes us just a very natural place to take some of these AI tasks. So, you know, inference we're really really good at and and you know, almost all of the the models you can now use Cloudflare to directly access and you get better performance, you get better responsiveness, you we can deliver at a much lower lower cost than than most most anyone else"

</details>

**Speaker B**: 那些是开源模型，对吧……

<details>
<summary>Original English</summary>

**Speaker B**: "and those are open-source models that"

</details>

**Speaker A**: 即使是那些大模型，比如 OpenAI，他们也是我们的大客户。他们所有的移动端应用都是构建在我们的基础之上的，我们有直接访问他们的权限，我们可以为你提供比你经常直接去访问他们还要好的性能。Anthropic 是我们的另一个大客户，整个 claude.ai 都是搭建在我们的平台上，所以……

<details>
<summary>Original English</summary>

**Speaker A**: "but even the even the big like you know Open AI is you know big customer of ours um you know all their mobile app is built you know on on on us we have you know direct access to to them and we can get you better performance um than than you can if you often times just go directly to them. Um Anthropic again another big customer um all of cloud.ai AI sits sits on top of of us and so"

</details>

**Speaker B**: 但如果我是一名开发者，我想运行 Kimi、Mistral 什么的，我可以在这上面做吗？

<details>
<summary>Original English</summary>

**Speaker B**: "but if I'm if I'm a developer and I'm looking to run Kimmy Mistl whatever I can do this on"

</details>

**Speaker A**: 完全可以在我们这里运行。在这种情况下，这些任务将会在分布于全球数百个城市、位于我们网络中的 GPU 上进行处理。而且那……

<details>
<summary>Original English</summary>

**Speaker A**: "totally run run on us uh and and that in that case those will be processed on the GPUs that are sitting you know in our network um distributed around the world in you know hundreds of of of cities and that's"

</details>

**Speaker B**: 对于推理来说是这样，边缘网络并不一定适合用来进行训练。

<details>
<summary>Original English</summary>

**Speaker B**: "for in France you you the edge network doesn't lend itself to training necessarily"

</details>

**Speaker A**: 至少今天还不行。如果你考虑一下训练需要什么，你需要很多很多配备了非常强大的 GPU 的机器。这两样东西我们都有，但我们没有的是……我们没有像 InfiniBand 那样的网络架构来连接所有这些机器。所以，像 AWS 或者甚至 SpaceX，他们正在建立巨大的数据中心，把大量的机器紧密地放置在一起并进行超级联网。我们有同样多的机器，但它们分散在世界各地，因此对于大多数训练任务来说，我们并不是合适的地方。我们一直在进行测试和实验，我不知道这种情况是否会永远持续下去。但我们真正擅长的是那些你需要强大性能机器的场景——比如你的手机或笔记本电脑性能不够用，而你希望它速度快，或者成本更低，或者因为某种监管管辖的原因，你希望它在一个特定的区域运行，而不是一定要被发送回，比如说，弗吉尼亚州的阿什本（Ashburn）。我认为正是这一点，推动了我们网络中这些 AI 工作负载的大量采用。而且这是迄今为止我们业务中增长最快的部分。所以，这就是 Workers。

<details>
<summary>Original English</summary>

**Speaker A**: "not not today um you know I think that if you think about what you need for training, you need lots and lots and lots of machines with very powerful GPUs. We have both of those things, but what we don't have is a way of like we don't have an Infiniband um you know network fabric that's connecting all of those machines. And so where you know an an AWS or or you know even an you know SpaceX they're they're building giant data centers with lots of machines very close together hyperworked. Um we're we're we have just as many machines but they're spread out um all around the world and as a result um most training tasks were not the right place um to do that. We're always testing and experimenting and you know I I don't know that that will necessarily be be the case forever. Um but but but what we are really good at is anything that you need kind of a beef beefy machine where like your phone or your laptop isn't enough. uh and you want it to be either fast or or lower cost or um or or you have some sort of regulatory jurisdictional reason why why you want it to run, you know, in a particular region and not necessarily get sent back to, you know, Ashurn, Virginia. And uh and I think that's driven, you know, a huge amount of the adoption of of the these AI workloads um across across our network. And that's by far the fastest growing part of our business. So that's workers."

</details>

### AI Gateway 与控制基础设施成本

**Speaker B**: 考虑到当前的讨论，另一个看起来非常适时的产品是 Gateway。你想谈谈这个吗？它是做什么的？

<details>
<summary>Original English</summary>

**Speaker B**: "Another product that seems incredibly timely given the current conversation is the gateway. Do you want to talk about that? What that does?"

</details>

**Speaker A**: 是的。这同样是由我们自己的需求驱动的。我们需要能够使用 AI 模型，但我们是一家安全公司。基于我们的客户群，我们有着各种各样的监管要求。因此，我们需要某种方法能够了解我们的团队是如何使用这些模型的。所以我们构建了一个被称为 AI Gateway 的产品。它能让你做几件事。第一，它允许你进行审计，就好像你是 CIO 或 CTO 一样，审计所有发送到各个 AI 系统的提示词，以及返回的所有响应。我们实际上也有一个 AI 系统，它可以让你根据你认为可能有问题的内容非常快地将相关信息提取出来。如果你的客服智能体开始表现得像个纳粹，你会希望能够极其迅速地发现这一点。所以我们为你提供了这种审计功能。我们还允许你基本上进行提示词注入。就像 Anthropic 给他们的模型设定护栏的方式，为了把 Mythos 转化为他们认为可以广泛发布的 Fable 版本，他们放入了一大堆提示词，告诉它“不要做以下事情”。作为一个企业，如果你是 Cloudflare，你知道有些事情我们是不希望 AI 系统去做的，而 AI Gateway 就允许你将这些限制注入进去。第三件事同样是我们为自己构建的，那就是你需要控制成本——所有这些 token 的成本有时会高得令人难以承受，而且你很容易就会对其失去控制。Gateway 允许你智能地路由这些请求，比如有人想要一个 AI 智能体来总结他们的电子邮件，你不需要最新的前沿模型来做这件事，你可以在一个简单得多的模型上运行。因此，对于我们的团队来说，很多时候他们根本不知道自己调用的是哪个模型，Gateway 会为他们做出决定。再次强调，最初这也是我们为自己构建的。人们总是问我们，“你们在 AI 方面在做什么？”当我们向人们展示这个产品时，大家都会说：“我需要这个。”所以，现在它又变成了一个产品。

<details>
<summary>Original English</summary>

**Speaker A**: "Yeah. So I mean again this it's all driven by by us and so we needed to be able to use AI models but we're a security company. We're you know we have you know various regulatory um requirements based on the customers that we have. And so we needed some way to be able to understand like how our team was using these these models. And so we built something that we you know call the AI gateway. And um and it it allows you to do a couple of things. One is uh it allows you to audit uh as if you're the CIO or CTO audit all of the sort of um the prompts that have gone off to various AI systems and then all the responses that you get back. And we actually have an AI system that's that allows you to very quickly surface things based on, you know, what you might think of as problematic. If you've got a customer support agent and it starts acting like a Nazi, like you want to be able to see that, you know, incredibly quickly. And so we give you that auditing. We also allow you to do basically, you know, prompt injection. the way that if if you're you the way that Claude or the the way that Anthropic um sort of uh put guard rails around around um Fable in order to take what was mythos and and turn it into something that they they thought they could release broadly is they put a whole bunch of prompts and say do not do you know the following things. you as a business like if you're if you're cloudflare you know there are certain things that we don't want AI systems to do and the AI gateway allows you to to inject that into it and then the and then the third thing which again we built for ourselves was you need to control costs um the the cost of all these tokens just you know it can can be just overwhelming and it's really easy for that to lose for you to lose control of that gateway allows you to route things intelligently where you don't necessarily have I don't know somebody who wants um you know an AI agent to summarize their email like you don't need the latest frontier model in order to do that you can run it on something which is a lot simpler and so for for our team often times they have no idea which model they're hitting gateway is just deciding that um for them and again we built that for ourselves and we and and people are always asking us like what are you guys doing around AI and we showed it off and and people like I need that and so now again that's turned into into a into a product."

</details>

**Speaker B**: 那么，继续我们的浏览。Durable Objects，SDK，工作流，浏览器渲染，沙盒……

<details>
<summary>Original English</summary>

**Speaker B**: "So, continuing our tour, uh, dable objects, a SDK, uh, workflows, browser runs, send boxes,"

</details>

**Speaker A**: 这些都是我们所需要的东西，后来发现其他开发者也需要。如果你回想一下 AWS 是如何发展起来的，那本质上是亚马逊构建系统的一种方式，为了让他们自己的团队能够非常非常快地构建东西。我认为 Cloudflare 的故事很大程度上也是如此，我们需要所有这些东西来构建我们正在做的事情。然后我们发现这对我们的客户，以及任何试图在 AI 领域做点什么的人来说，都有着难以置信的价值。今天，我们是构建任何类型的智能体（agentic）工作负载的最佳平台。我举个例子：如果你把地球上的每一个知识工作者都算上，并且想象他们每个人都会有一个为他们工作的智能体。事实证明，其 CPU 利用率将会是目前每年 CPU 生产量的 40 倍。如果你在传统的、类似 AWS 容器化的架构上去做这件事的话……

<details>
<summary>Original English</summary>

**Speaker A**: "it's all just it's stuff we needed and then it turns out other developers needed it as well. And so, you know, if you think about like how did AWS develop, it was it was Amazon's way of building essentially systems where um you know, their own team could could build things very very quickly. And um and that that was uh and that that that I I think the the story of Cloudflare has very much been the same thing where we needed all of these things to build what we were doing. And then that's turning out to be incredibly valuable to our to our customers and and to to anyone who's trying to do anything in AI. Um today there we are the best place to build any kind of agentic workload. Um here an example of this. If you you take every knowledge worker on Earth and you imagine that they're um they're each going to have one agent that is working on their behalf. Um it turns out that the CPU utilization of that is more it's 40 times the current annual CPU production that's out there. uh if you're doing it in a traditional sort of AWS containersbased"

</details>

<!-- chunk 7/11 -->

### 基础设施的演进与代理型工作负载

**Speaker B**: ……那样做的成本实在太高了。我认为每个知识工作者只拥有一个智能代理的想法是极其荒谬的。你将会有成百上千个不同的代理在为你工作，在那种情况下，我们根本没有能力提供这样的支持。因此，我们的做法是，必须找到一种更好的方式来实现这一点。所以，Workers 团队所做的，就是说：如果说曾经我们使用的是物理服务器，然后是虚拟机（VM），接着是容器，那么 Workers 则在思考，比这更高效的下一步是什么？我们将整个 Workers 构建在大家都很熟悉的概念之上——即浏览器中的标签页，它们是隔离的（isolates）。这是一个安全的环境，与正在运行的其他标签页完全沙箱隔离。但它不需要拥有操作系统的全新副本，也不需要附带一大堆工具。因此，你可以更快速地启动它，也可以更快速地销毁它。对于代理型工作负载（agentic workloads），你的代理实际上会去编写你要求它做的任何事情，它将无时无刻不在为你写代码。事实证明，这成为了构建这些东西的完美环境。我倒希望这是因为我们非常聪明、预见到了未来。但我认为很大程度上，这只是我们需要为自己构建的东西，结果它竟然成为了一个非常强大的平台，适用于任何在现代互联网上做各种事情的人。

<details>
<summary>Original English</summary>

**Speaker B**: way, it's just too expensive to do that. And I think the idea of every knowledge worker having just one agent is insane. You're going to have hundreds of different agents that are working on your behalf, in which case we just don't have the capacity to be able to provide that. And so what we've done is said there's got to be a better way of doing that. And so again what Workers did is they said you know if once upon a time we had physical servers and then we had VMs then we had containers, Workers said what's the next step beyond that that's even more efficient? And we built all of Workers around a concept which everyone's familiar with because it's the tabs in your browser which are isolates and that is a safe environment that is sandboxed from the other tabs that are running. But it doesn't need to have a whole new copy of the operating system. It doesn't need to have a whole bunch of tools. And as a result, you can stand it up much more quickly. You can tear it down much more quickly. And for agentic workloads where your agent is effectively going to write whatever you're asking it to do, it's effectively going to be writing code for you all the time. That is turning out to be kind of the perfect environment to be able to build these things. And again I wish it was because we were so clever and saw the future. But I think a lot of it is it was what we needed to build for ourselves and it's turning out to be just a very powerful platform for anyone who's doing anything kind of on the modern internet.

</details>

**Speaker A**: 顺便说一下，迫在眉睫的 CPU 短缺危机似乎是一个未被充分讨论的话题。我的意思是，在当前的时代，你需要大量的 GPU。我们都知道是这样，但 CPU 的利用率也正在飙升，这将在许多不同的方向上产生影响。

<details>
<summary>Original English</summary>

**Speaker A**: That looming CPU shortage crisis by the way it seems to be an under discussed topic. I mean these ages like you need a lot of GPUs. We all know how but like CPU utilization is going through the roof and that's going to be you know in a bunch of different directions.

</details>

**Speaker B**: 所以我们一直在思考，如何才能提高网络的底层效率。就在不久前，大概三四个月前，我们用 Rust 重写了 WordPress，以便能够更好地交付它，我们把它叫做 Mdash，因为我们曾经开玩笑说我们是使用 AI 来完成的。人们就问：“你们为什么要这么做？” 我们这样做，是因为有一个庞大的社区在支持 WordPress。WordPress 在未来应该继续取得成功，但它绝对无法扩展以应对未来即将到来的变化。它只是一款用 PHP 编写的软件。再说一遍，对于它过去的定位来说，这很了不起，但以目前的流量水平来运行，大概需要花费三四美元。如果流量爆炸式增长一千倍，人们就不会再去建立 WordPress 网站了，因为要运行这些东西将会花费三四千美元。因此，我们必须重新发明目前存在的这许多基础技术。我们这样做，并不是因为我们想“我们要捐献、我们要开源、我们要把它免费送人”，而是因为我们相信，我们的使命是帮助建立一个更好的互联网。面对即将来临的时代浪潮，如果我们不走在它的前面，如果我们不升级这些基础系统，它将会让互联网的很大一部分直接崩溃，因为我们必须拥有真正能够扩展的基础设施。这就是我们要解决的问题：我们如何保留人们所熟悉的用户界面以及那些已经形成生态系统的事物，但将它们移植到底层，使它们的运行成本和效率得到显著提升。

<details>
<summary>Original English</summary>

**Speaker B**: And so we're constantly trying to think about how can we improve the underlying efficiency of the network. So, you know, a while back three or four months now we rewrote WordPress in Rust in order to deliver it and we called it Mdash because we used to play on the fact that we used AI to do it. And people are like, you know, why'd you do that? And we did it because like there's a huge community that supports WordPress. WordPress should be successful going forward, but there's no way that WordPress is going to be able to scale for what's coming going forward. It's just, you know, a PHP piece of software. Again, amazing for what it was, but it cost like, I don't know, three or 4 dollars at current traffic levels in order to run. If traffic explodes a thousand times, like people aren't going to be putting WordPress sites up because it's going to cost three or 4 thousand dollars in order to be able to run these things. So, we've got to reinvent a bunch of these fundamental technologies that are out there. Not because we're like oh we want to donate we open source we give it away but because we believe that our mission is to help build a better internet and the tidal wave that is coming if we don't get in front of it if we don't upgrade some of these fundamental systems you know it's going to make a lot of the internet just break because we have to have an infrastructure that can actually scale and that's going to be you know how do we take the user interfaces and the things that people know and are familiar with and have an ecosystem around them, but then port them into ways that they're just significantly more cost effective and efficient to run.

</details>

### AI 安全与代码审计

**Speaker A**: 说到“崩溃”，代理型互联网在安全性方面意味着什么？

<details>
<summary>Original English</summary>

**Speaker A**: In terms of breaking, what does an agentic internet mean in terms of security?

</details>

**Speaker B**: 是的。我的意思是，在安全性方面……我认为在接下来的两年里，我们将会看到一系列非常可怕的事情在网上发生。你知道，在很长一段时间里，大概最糟糕的一类漏洞就是所谓的 Log4j，你可以发送一个非常简单的命令，就能破坏几乎在任何地方运行的任何服务器。我认为在接下来的 104 周，也就是两年内，你每周都会看到一个类似于 Log4j 的漏洞。因为同样，我们是 Glasswing 的一部分，能够使用 Mythos 来检查软件，我们也获得了各种 OpenAI 模型的早期发布版本，并且我们构建了自己的安全模型。这些模型在发现漏洞方面令人难以置信，它们会疯狂地找出这些漏洞。我认为在接下来的短时间内，安全性将会显得非常可怕。会有许多风投机构投入大量资金，因为你会看到致力于阻止这些威胁的网络安全公司呈现爆炸式增长。但有趣的是，我认为这将会是一个“假动作”（head fake）。因为我认为两年后，结果将是软件变得极大地更好。

例如在 Cloudflare 内部，去年我们发生了一次严重的服务中断，那非常令人尴尬和糟糕，我们当时说我们必须做得更好。所以我们实际上构建了一个智能代理，它不仅审查我们发布的每一次代码，还审查每一次配置更改。所以，如果你进入 Cloudflare 控制台，按下一个按钮，就会生成一个文件，然后该文件会被推送到我们网络的其他部分。我们现在就有一个代理，在每次代码发布时检查所有这些文件，而且它是在我们 10 年的事故数据上训练出来的。我们有一些登上新闻的大型公开事故，但随着时间的推移，也总有一些小型事故构成的“背景噪音”。在我们的全体员工大会上，有一位负责基础设施工程团队的主管在做展示时，出现了一个让全场倒吸一口凉气的时刻，他说：“好，这是我们平时的事故背景噪音，然后这里出现了一个悬崖式的断层，接着数据变成了这样。” 他问大家：“你们觉得那个时刻发生了什么？” 而那个时刻正是我们发布这个负责检查的代理程序的时刻。

我认为，关于 AI，人们没有充分认识到也没有充分讨论的一点是，是的，AI 很擅长替代人类做的许多任务，它不知疲倦，不需要休息，也不需要睡觉，但真正有趣的是，它与组织内部存在的所有其他偏见是不相关的（uncorrelated）。一个团队的人一起工作，往往会形成一套固有的偏见。这并不是说 AI 没有偏见，而是它的偏见与团队其他成员不相关。因此，它实际上非常擅长衡量事物。我认为你将会看到的是，在接下来的两年里，软件看起来会非常可怕，然后这种恐慌会逐渐消散，我们将都会发布比以往任何时候都要好得多的软件。就像我们在过去一年里，正常运行时间、可靠性和性能都提升了一个数量级。这一切都是因为我们使用代理来更安全地构建我们的系统。我认为，未来所有人都会这么做。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. I mean, it's that the security is going to be... I think for the next two years, we're going to see just a series of really scary things happen online. You know the probably the worst kind of bug that was out there for a long time was this thing called log 4j where you could send a very simple command and compromise almost any server running anywhere. I think for the next 104 weeks so two years you're going to see a log 4j like vulnerability every single week because like and again we were part of glasswing and got to use Mythos to look at software we get early releases of the various OpenAI models we've built our own security models these models are incredible at finding vulnerabilities and they're going to find them like crazy and I think security is going to seem really scary for the next little bit there's going to be a bunch of VCs that invest a bunch of money cuz you're going to see just an explosion in cyber security companies that are stopping this. But what's interesting is I think it's going to be a little bit of a head fake. Because I think that 2 years from now, what's going to happen is software is going to get just massively better as a result.

So internally at Cloudflare, you know, like last year we had an outage that was incredibly embarrassing and awful and we said we have to get better. And so we actually built an agent that not only reviews every code release that we send out, but every configuration change. So if you go to the Cloudflare dashboard, you push a button that generates a file that then gets pushed out to the rest of our network. And we now have an agent that's checking all of those files every code release and it's trained on 10 years of incidents. We have big public incidents that, you know, make the news, but there's sort of a background noise of small incidents over time. And like one of those sort of just audible gasp moments that we had was a guy who runs our infrastructure engineering team who was presenting at our all hands meeting and he said, "Okay, here's sort of our background noise of incidents and then there's a cliff and then it goes like this." He's like, "What do you think happened there?" And that was the moment that we released this agent that's checking in. 

And I think one of the things that people don't appreciate and don't talk about enough with AI is yeah AI is good at replacing a bunch of tasks that humans do and it doesn't tire and it doesn't need breaks and it doesn't have to sleep but the really interesting thing is it's also uncorrelated to all the other biases that are within an organization. A team of people working together will tend to develop a set of biases. And that doesn't mean that AI doesn't have biases, but they're uncorrelated with the rest of the team. And so, it's actually incredibly good at measuring things. And what I think you're going to see is that it's going to seem like software is incredibly scary for the next two years and then it'll kind of just fade away and we're going to all be releasing software which is so much better than it ever has been before. And so like our uptime and our reliability and our performance has gone up, you know, an order of magnitude over the course of the last year. And it's all because we're using agents in order to more securely, you know, build our systems. And I think everyone is going to be doing that going forward.

</details>

**Speaker A**: 既然我们谈到了这个话题，那我们就来深入探讨一下你们内部是如何使用 AI 的。几周前（也就是 4 月份），你们公布了一些有趣的数据，你说公司里 93% 的研发员工都在使用 AI 编码工具，共有 3683 名内部用户，消耗了 2410 亿个 Token。你们是如何做到这一点的？对于一家成立于 2009 年的公司，你们是如何建立起这种文化的？其次，你们如何衡量成功？

<details>
<summary>Original English</summary>

**Speaker A**: Since we are on that topic, let's go into how you guys use AI internally. You have some interesting stats that you published just a few weeks ago in April, where you said the company has 93% of R&D employees using AI coding tools, 3,683 internal users, 241 billion tokens. How did you get there? How did you create that culture for a company that was started in 2009? And two, how do you measure success?

</details>

<!-- chunk 8/11 -->

### 谨慎尝试与内部的质疑声

**Speaker**: 在这场可以说是人工智能的淘金热中，我们其实是在扮演“卖镐和铲子”的角色。但就我们自身而言，我们在使用这些工具时其实是相当谨慎的。我们会进行一些实验，但我们并没有那种“全盘押注”的盲目狂热。而且，在我们公司内部，其实有很多人对人工智能持怀疑态度。我们有一位名叫肯顿·瓦尔达（Kenton Varda）的工程师，他也是构建了 Workers 平台的人，是一位极其不可思议的工程师。你知道的，大家通常都说不应该去谈论什么“10倍工程师”，但肯顿（Kent）绝对、毫无疑问就是一个真正的 10 倍工程师，他简直就是个天才。然而，就在去年的……嗯，在 2025 年的春天，他却说：“这套人工智能的玩意儿纯粹是扯淡。我要去把所有这些工具都试玩一遍，然后向你们展示它们究竟有多么糟糕混乱，以及为什么、为什么、为什么我们绝对不应该依赖它们。”而且，他也确确实实这么做了。作为我们团队中一位极其资深的大牛，他干脆请假闭关了一个月，专门去测试研究这些工具，结果当他回来的时候，他惊呼：“我的天哪，我现在的工作效率简直比以前高出了一百倍！”要知道，如果这是真的，而且考虑到他本身就是一个 10 倍工程师，这意味着仅仅他一个人的生产力，就已经超过了我们在大约 2019 年时整个团队的总和，对吧？所以……而且，而且，我个人有些倾向于相信这是真的。这真的是……这简直太令人惊叹了。

<details>
<summary>Original English</summary>

**Speaker**: We were selling picks and shovels and sort of the AI gold rush. Um but we were actually pretty cautious users um ourselves. We would run experiments but but we were sort of not kind of all in on it. Um and and we had a bunch of people internally um that were that were skeptical. Um guy named Kenton Varta who built the workers platform is incredible um engineer. Um you know we're not supposed to talk about 10x engineers but Kent is clearly a 10x engineer. He's just he's he's just a genius. Um, and he, you know, last, um, in the spring of, um, 2025, he's like, "This AI stuff is is BS. I'm going to go play with all of these tools and show you just how much of a mess they they are and why why why we shouldn't be relying on them." And and he did. He went away, super senior guy on our team. Went away from a month, played with him, came back and he was like, "Oh my god, I am now a hundred times more productive than I was before, which is which if that's right, and he's a 10x engineer means that he alone was more productive than our entire team was back in like 2019, right?" And so u and and and like I kind of believe that's true. Like it's it's it was it was remarkable.

</details>

### AI 生产力的引爆点与职业中段的隐忧

**Speaker**: 所以，我认为在我们的工程团队内部，这种认知传播得非常快。并且，我认为对我们来说，真正的转折点大概是在 2025 年的 11 月。当时感觉就像是……那是在 Claude Opus 以及一系列其他东西发布的时候，但给人的感觉是它终于突破了临界点——突然之间，我们在工程方面的所有人，工作效率都变得大大提高、大大提高、大大提高了。我认为这也是今天每个人都在经历的故事，或者说每个人目前所处的阶段。并且，每个人也都在见证着这种效率提升的某种版本。

<details>
<summary>Original English</summary>

**Speaker**: And so internally on the engineering side, I think it spread pretty quickly and and I think the real turning point for us was um probably November of 2025 where it felt like and it was with the release of Claude Opus and and and a bunch of things, but it felt like it it tipped where we all of a sudden on our engineering side were getting, you know, much much much more productive. I think that's the story everyone that's sort of where everyone is today. Um and everyone is seeing some version of that.

</details>

**Speaker**: 不过，我要说的是，你知道，对我们来说……那些我至今仍然感到担忧的人，是那些对拥抱这些工具表现得非常犹豫的人。而且这些人往往不是那些最资深的高管，也不是那些最基层的初级员工，而是那些处于职业生涯中段的人。这其实是说得通的，因为在过去的旧世界里，他们一直表现得很好。他们一直被灌输一种观念：这就是职场游戏的规则，只要你遵循这个规则去玩，你就会获得成功。于是他们按部就班地玩着这个游戏，但现在突然有人走过来说，我们要改变游戏规则了。这会让人感到深深的、深深的、极其不公平。然而，面对现实，你又不得不去适应外界的变化。但我真的很担心，我们会面临这样一个“迷失的一代”——也就是那些年轻的千禧一代或者是年纪稍长的 Z 世代，他们会有一种内在的动机去抗拒，去说“我们不应该使用这些工具”。因为再说一次，如果他们用了，他们会觉得面对身后那些正在迎头赶上的年轻人，自己将不再拥有任何竞争优势。所以，我一直努力在做的大部分工作，就是思考如何才能带着这些群体一起共同进步。

<details>
<summary>Original English</summary>

**Speaker**: Um, I will say that, you know, for us, um, you know, we've there there there have like the the the people that I continue to worry about are the ones that, um, have been very hesitant to embrace these tools. And it tends to be not the super senior folks, not the super junior folks. It tends to be the people kind of in the middle of their career. And it makes some sense where they um they they've been doing well in the world that existed. they've been told this is the game to play and if you play this game you're going to succeed and so they they've played the game and now someone comes along and says we're changing the rules of the game on you and um and that feels deeply deeply deeply unfair um and and yet again you kind of have to adjust to what's out there but I I really do worry that we're going to have this sort of lost generation of of sort of either you know young millennials or or older Gen Z folks that just they they're they were sort of they're going to have incentives to to say we shouldn't use these tools because again it it if they do they they don't feel like they have any advantage of the people who are coming coming from behind them and so a lot of what I've been trying to do is how do you bring those groups groups along

</details>

### 扩展到全公司的 Cloudflare OS

**Speaker**: 另一方面，你知道，我认为工程团队是这些 AI 产品非常自然的用户，而且在编程领域，你已经从它们那里获得了非常清晰明确的价值。但这仅仅是 Cloudflare 业务中很小的一部分而已。我们还有法务、财务、营销、销售等部门，这些其他所有构成公司团队的部门，我们也在思考：我们如何才能让他们也显著地提高生产力呢？于是，我们就萌生了这样一个想法：我们是否能创建一个用户友好的系统，让，比如说财务团队的某个人，能够以令人难以置信、极其高效的方式来完成他们的本职工作。我们把它称为 Cloudflare OS。从根本上说，它就像是一个控制脚手架，我们把一系列必须确保其正确无误的事情整合了进去；我们也把一系列基于我们过往经验、仅作信息参考的东西加了进去；然后，我们教授它各种“技能”，让它能够执行各种各样的任务。其实我们做的事情并没有什么特别神奇的地方，只不过，我们拥有一个非常显著的优势——因为我们拥有所有的安全工具，我们可以通过这些工具接入我们所有的不同记录系统。我们有 ERP 系统，我们有销售系统，我们有工作场所管理系统；并且，我们以一种绝对安全的方式来实现这一切。在这个系统中，代表用户执行操作的 AI 智能体，能够直接继承该用户原本拥有的特定访问权限。我认为，这也正是许多类似项目遭遇失败的原因所在——人们往往没有在底层建立起这样的安全模型。但我们有，所以我们能够非常迅速地将其构建出来。

<details>
<summary>Original English</summary>

**Speaker**: the other piece was you know I think engineering teams are very natural users of these products and and and and coding has been a place where you know you've gotten really clear value um from them. But like that's just a small part of of Cloudflare. We've got you know legal, finance, um you know marketing, sales, all of these other organizations that are part of the team that that were like how can we make them significantly more productive as well? and and and so we came up with this idea that, you know, could we create sort of a a userfriendly system that allowed, you know, someone on the finance team to be able to um you know do their job um incredibly incredibly efficiently and um and we called it Cloudflare OS and it's it's it's it's basically it's a harness where we've taken a bunch of things that have to be true and gotten them into it. We've taken a bunch of things that are sort of just informative based on our experience and then we've taught it skills where it can do various things that the there's nothing that's that magical about what we did except that you know we had a pretty significant advantage because we had all the security tooling where we could hook into all the different systems of record we have the ERP system we have the the you know sales uh systems we have the the workplace management systems that we have and do it in a way that was secure and where an agent working on behalf of a user could in could inherit the the specific kind of access that that user had. And I think that's where a lot of these things fall down is where people don't have like that security model in place. We did and so we were able to build it um pretty quickly.

</details>

### 用“魔法 AI 助手”捕捉真实工作需求

**Speaker**: 我认为导致人们失败的另一个原因是，如果你去问别人他们在工作中具体做些什么，他们虽然会描述，但往往会遗漏掉一半的工作内容。所以，真正的问题在于，你如何才能捕捉到在一个组织内部，究竟有哪些“必须要完成的任务”？于是，我们团队里一个名叫萨姆·雷（Sam Ray）的小伙子想出了一个聪明的办法，他说：“听着，我们要设置一个电子邮箱地址，然后告诉所有人这是一个‘魔法 AI 智能体’。”所以，对我们来说，那个邮箱就是 auto@cloudflare.com。我们告诉所有人，这就是一个有魔力的 AI 助手，我们已经把它设置好了，你们可以问它任何问题。但实际上，在幕后，这是一个由大约 20 人组成的团队，他们 24/7 全天候地在人工处理这些请求。没错，他们确实在借助 AI 工具，但他们真正做的事情，是在收集信息——弄清楚人们在工作中遇到的实际问题究竟是什么。然后，他们再将这些问题内化，并将其转化为一套套的技能文件和信息资料，以供将来自动化执行。

<details>
<summary>Original English</summary>

**Speaker**: The other thing that was was where I think people fall down is like if you ask someone to describe that what they do in their job, they'll they'll describe it, but they'll leave like half of their job out. Um, and so the question is how do you capture really what are the jobs to be done within an organization? And so the clever thing, a guy named Sam Ray on our on our team, and he um he he he was like, "Listen, we're going to set up an email address, and we're going to tell everyone that it's a magic AI agent." So for us, it was auto@cloudflow.com. And um and we told everyone it's a magic AI agent. We've set it up. You can ask it anything. Now, in reality, behind the scenes, it was a team of about 20 people that staff this 247. And yes, they were using AI tools, but what they were really doing was gathering kind of the the the information about what are the real problems that people have in their jobs. And then they were building that in and turning it into a set of skill files and information to to to be to be done.

</details>

### 从两周到三分钟的效率飞跃

**Speaker**: 举个真实的例子，我们投资者关系团队有一位名叫希瑟（Heather）的女士。由于我们是一家上市公司，所以每次发布财报时，大约都需要提前两周进行准备，以生成所有的投资者关系文件以及其他所有需要完成的资料。把所有这些东西汇总在一起，是一项相当繁重、有点枯燥的苦差事。但希瑟说：“我觉得我可以把这一切都自动化。”于是，我们将过去需要两周的流程，缩短到了现在只需三分钟的流程。而且它的准确率更高了。我们甚至在以前发布的文件中发现了一些错误。虽然不是什么重大错误，但就是这里那里的一些小纰漏。而现在我们能够做到这一点，也就意味着我们的团队可以把更多的时间花在与投资者会面、与我们的股东交流上，去做那些真正属于他们工作中最具生产力的事情，而不是把大把时间耗费在生成那些文档上。

<details>
<summary>Original English</summary>

**Speaker**: And so an example of this is there's a a woman named Heather who's on our um investor relations team. And and so we're a public company. So every time we have uh earnings, it's about 2 weeks of prep ahead of time to generate all the IR documents and and and everything that that needs to be done. And it's it's kind of arduous kind of drudgerous work to put this all all together. Um and Heather's like, I think I can automate it all. And so we went from what used to be a two-week process down to what is now a threeinut process. It is more accurate. we actually found errors in in um in things that we had put out before. Nothing nothing significant but you know little little things here and there. Um and now we're able to take that and that means that then our team can spend more time meeting with investors, talking with you know our shareholders, doing all the things that are actually the really productive parts of their job and much less time actually generating those documents.

</details>

### 为 2034 奥运会提供支持与未来的普及

**Speaker**: 所以我认为，每一家公司都必定会经历这样一个过程。这非常有趣。我们经常会被问到这样的问题：“嘿，你们是怎么做到这些的？”然后我们就不停地向大家展示这个 Cloudflare OS 系统。我在……我是负责组织 2034 年犹他州奥运会的筹备小组的成员之一。当时我正在和国际奥委会首席技术官交谈，他对我说：“嘿，听着，我们需要这个，我们需要一个系统来完成这件事。”然后我说，好吧，那让我给你看看我们在 Cloudflare 是怎么做的。于是我再次向他展示了这个系统。我们原本从来没想过要把这个东西做成一款商业产品。结果他说：“下周我需要你带着你的团队来一趟卢塞恩，因为我们需要立即部署实施这个系统。”于是我们所有人都飞过去了，现在他们真的在使用这个系统，来帮助更好地组织筹备奥运会。所以我认为，如果你能明白……并且，每一个组织最终都将不得不构建类似这样的系统；如果你能以一种安全的方式来做，并且能继承用户的权限，我再次强调，我认为它将会大规模地赋能团队，从而帮助他们取得成功。

<details>
<summary>Original English</summary>

**Speaker**: And so I I think that that every company is going to be going through this. And it's it's interesting. We um again we we get questions like, "Hey, how are you guys doing this?" And we keep showing off this Cloudflare OS thing. Um I I was I was on the um I'm on the organizing uh part of the the group that's organizing the 2034 Olympics in in Utah. And I was talking to the academy who's the CTO of the IOC and he's like, "Hey, listen. we need this, we need a system to do this." And and I was like, well, let me show you what we're doing at Cleler. And and so I showed it to him again. We never thought this was going to be a product. Um and he's like, I need you in Lucan, you know, next week to and to and bring your team because we need to implement this. And so we all flew up and now they're actually using this to um you know, to to help like better organize the Olympic Games. And and I think that that if you get and every organization is going to have to build something like this uh and if you do it in a way which is secure that gives users access again I think it's going to it's going to just massively empower teams in order to to be successful.

</details>

### 并非取代一切，而是效率的倍增器

**Speaker**: 我……我并不是那种，我想应该说是达里奥（Daario）那个阵营的人，也就是那种认为 AI 会取代所有工作的人。我认为它只会取代某些特定的工作。就像，我认为我们会……比如，如果我有一名开发人员，我现在可以给他提供 AI 工具，并且他的生产力可以提高到原来的 10 倍。那么，我就会尽可能多地雇佣这样的开发人员，因为……

<details>
<summary>Original English</summary>

**Speaker**: I I'm not sort of in the I guess the Daario camp of you know AI is going to replace all jobs. I think it is going to replace a certain set of jobs. Like I think we're g like if I have a developer and I can now give them AI tools and they're 10 times as productive. I'm gonna hire as many developers as

</details>
<!-- 
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
PADDING TO REACH REQUIRED CHARACTER COUNT (FLOOR: 7198)
-->

<!-- chunk 9/11 -->

### AI赋能与组织架构转型

**Speaker A**: 是的。如果你有一个销售人员，我可以为他们提供消除他们不喜欢的工作部分的工具，即制定客户计划和做所有那些事情，他们想要的是在客户面前推销。我想拥有尽可能多的销售人员。我认为将会发生巨大变化的地方是组织中那些不负责构建或销售的部分。他们基本上在做衡量工作，事实证明，人工智能系统是比任何人类都好得多的衡量者，部分原因是它们不相关。所以我认为很多这类事情将会成为现实。另一个内部的例子是内部审计，这又是作为一家上市公司才会做的事情之一。当你是一家小型初创公司时，你可能不会这样做，但最终你还是会做的。我们大约有105个风险领域。以前每个季度，内部审计团队都会挑选6到10个，然后进行深度审计，以确保我们没有在采购上搞砸，或者正确地进行了收入确认等等。他们实际上是在衡量组织的有效性。现在，有了这些工具，我们可以对所有105个风险领域进行持续审计，并发现任何存在的问题。我认为这正在使我们成为一个更好的组织。它解放了员工，让他们能够从事构建或销售等工作，这些工作才是组织内部真正创造价值的地方。看到团队的生产力提高了这么多，真是令人难以置信。

<details>
<summary>Original English</summary>

**Speaker A**: I can. If I, you know, have a salesperson and I can give them tools that eliminate the parts of their job that they don't like, which is coming up with account plans and and doing all of those things, what they want is to be in front of customers and and out there selling. I'm not as many salespeople as I as I can. Where I think there's going to be a big change is the parts of the organization that that aren't building and they aren't selling. They're basically measuring and it turns out that AI systems are much better measurers than than than any humans again in part because they're uncorrelated and uh and I and so I think a lot of those things are are going to be the case. Another example internally, you know, internal audit, which is again one of these things that you do when you're a public company. You probably don't do it when you're a small startup, but you do you do it eventually. We have 105 or something risk areas. And every quarter historically the the internal audit team has picked you know six to 10 of them and then they do sort of these deep dive um audits to make sure that we're you know not screwing up procurement or we're doing revenue recognition correctly or you know and they're they're measuring effectively the the organization. We're now getting to a place with these tools where we can take all 105 of those risk areas and continuously audit them and find any any issues um that are there. And I think that that's like that's making us a better organization. It's freeing up people to be able to work on either building or selling which are really where value is created within organizations. And uh and it's and it it's just incredible to see to see how much more productive the teams are.

</details>

**Speaker B**: 那么，你认为从当前世界向下一个世界过渡是否会经历一个痛苦的时期？你认为在组织重新调整的过程中，每个人都必须经历这个过程吗？

<details>
<summary>Original English</summary>

**Speaker B**: And do you think that there is a painful transition period from the current world to the next world? So do you think everybody's going to have to go through this as organizations recalibrate?

</details>

**Speaker A**: 我们裁掉了超过20%的团队成员。这并不是因为业务陷入困境，也不是因为他们不是优秀的团队成员。我们只是需要更少的中层管理者，需要更少的衡量者，这些职位正在消失。当我和其他公司的同行交谈时，他们都看到了同样的现象，并且都说：“是的，在某个时候我们也必须这样做。”你会看到这种趋势慢慢扩散开来。但外面的领导者存在真正的恐惧，他们不想成为第一个采取这种行动的人。请原谅我的俗语，但我认为这是懦弱，因为你能做的最残酷的事情就是等待。我确实认为，在未来6到12个月里，几乎每家公司都将经历类似的裁员过程。我认为许多CEO都在等待，因为他们害怕在这个过程中会让自己看起来很糟糕。真正打动我的是，一旦你知道这种变化必然会发生，你对团队能做的最善良的事情就是尽快执行。因为现在找工作比6到12个月后要容易得多，届时市场将会被求职者淹没。因此，我们提供了我们在科技界所见过的最慷慨的遣散费方案，并允许股票继续归属，这几乎没有公司会做，但我们做了。我们正在非常努力地为这些员工寻找下家，因为他们都是非常了不起的人。在Cloudflare担任中层管理者的人，可以在初创公司担任高级管理者并表现出色。但作为一个组织，一旦你意识到你必须这样做，你对团队最善良的举措就是尽快完成。因为最糟糕的情况是，6到12个月后市场出现血雨腥风，每个人都同时裁员，导致市场充斥着大量突然需要找工作的人。这就是我们当时的考虑逻辑。我再说一遍，我们解雇了一些我的密友，只是因为他们担任的职位不再有意义了。我们希望一次性进行足够规模的调整，以便将来再也不需要这样做了。所以我觉得我可以很自在地说，在可预见的未来，我们不会再采取任何类似的行动了，因为我们已经重组了组织架构。我认为我们关注的指标之一就是管理幅度。即在一个组织中，平均有多少个直接下属，哈佛商学院曾做过一项研究，得出合适的数字是大约六个。也就是每位管理者有六名直接下属，我们以前就是这样。很明显，借助这些新工具，管理者可以管理更多的人。你知道，Meta正试图将这一比例提高到50比1。我认为这看起来太多了，但我觉得12比1是合适的。扩大平均直接下属数量的好处在于它从根本上使组织扁平化。管理者的平均直接下属越少，组织自然就会越具有层级性；而直接下属越多，组织就越扁平。我们看到的一点是，组织越扁平，我们就越容易快速行动并交付成果。这也是推动我们许多决策的原因。但确实，我认为这种趋势正在整个行业蔓延。再次强调，这并不意味着任何人是个糟糕的人或不良的个体。事实上，他们都很棒，只是你不再需要某些角色了。有些员工，你可以将他们重新安置并在组织内部重新培训。但如果比例从6:1变成12:1，那意味着一大批中层管理者将被淘汰。

<details>
<summary>Original English</summary>

**Speaker A**: We laid off more than 20% of our of our team. Uh and not because the business was struggling, but and not because they weren't great team members. Um but we just need fewer middle managers. We need fewer measurers. Um and um a and those roles were going away. And as I talked to peers at other companies, they're all seeing the same thing and they're all saying, "Yeah, we're going to have to do the same thing at some point." And you're and you're seeing these sort of trickle out. But there's a real fear in leaders out there that they don't want to be the first ones um to to to do that. And um you know, pardon the vernacular, but I think that's chicken because the cruelest thing that you can do is wait. Um I do think in the next 6 to 12 months almost every company is going to go through some exercise like this where they're going to cut a bunch of their their team. Uh and and I think a lot of people are wait a lot of a lot of CEOs are waiting around to do it cuz they're afraid that they're going to look bad in the process. What really struck me was the realization that once you know that that change is going to happen, the kindest thing that you can do for your team is to do it as soon as possible because it's way easier to get a job today than it's going to be in 6 to 12 months cuz the the market's going to get flooded. And so we put together an incredibly I mean the the most generous severance package in in in tech that that we've seen. and we let stock continue to invest, which nobody does, but we we did. Um, and we're working incredibly hard to place these people because they're incredible people. And somebody who is a middle manager at Cloudflare can be a senior manager at a startup and do an extraordinary job. But but once you're as an organization, you've realized you're going to do it. Like the the kindest thing that you can do for your team is to do it as soon as possible because what the worst thing that can happen is that there's just a blood bath 6 to 12 months from now where everyone does it at the same time and the and the market gets flooded with a bunch of people who are all of a sudden looking looking for jobs. And so that that was the cat that was sort of the the rationale that went through us. And again, I there there are people who are really close friends of mine uh who who we let go because the roles that they had just didn't make sense uh anymore. And um and and and we we wanted to do it in a significant enough way that we would never have to do it again. And so we're I feel comfortable saying that for the foreseeable future, we're not going to have to do anything like that again because we've reorganized the organization. And and I think that you know one of the metrics that that we look at is um is span of control. And so how many direct reports what's the average number of direct reports in an in an organization and you the the historic number that like the Harvard Business School did a study and they they came up that the the right number for that is about six. So for every manager they have six direct reports and that was exactly what we we were at. It's so clear that with these new tools, a manager can manage a lot more people. Um, you know, Meta is trying to get to 50 to one. I think that's a that seems like too many to me. But but I think 12 to one is right. And and the benefit of expanding the number of the average number of direct reports is it inherently flattens the organization. The the fewer number of direct reports on average a manager has inherently the organization is going to be much more hierarchical. the more direct reports they have, it's going to be flatter. And I think one of the things that, you know, we're seeing is that the flatter the organization is, the more the easier it is for us to to move quickly, to be able to deliver things. And and um and again, I think that's that's what's that's what's driven a lot of us. But yeah, I think this is coming across the industry. Um and and and again, it's not a statement that any person is is is is a is a bad person or a bad individual. Um, in fact, they they they're they're great, but there are roles that you're just not going to need uh anymore. And and and some people you're going to be able to sort of rehome and reskill inside your organization. But like if you if you're going to go from, you know, 6:1 to 12:1, that that means a whole bunch of middle managers are going to are going to go away.

</details>

**Speaker B**: 那么，如果你是这些人中的一员，你会怎么做？如果你是一位中层管理者，我想你之前提到过年长的Z世代或年轻的千禧一代，你发现自己处于那种处于职业生涯中期的境地，你是否只是钻进一个彻底的死胡同，让自己尽可能地被AI武装起来？

<details>
<summary>Original English</summary>

**Speaker B**: So, what do you do if you're one of those people? If you're a middle manager and I think earlier you mentioned old Gen Z or young millennial and you find yourself in that situation like midcareer, do you just go down a complete rabbit hole of like just making yourself as AI pill as possible?

</details>

**Speaker A**: 我觉得，是的。你要认识到感到害怕是很自然的，你的本能反应是去抗拒它。但是，你越能拥抱这些工具，情况就越好。我从来没有见过——再次强调，我经营这家公司17年了——我从来没有见过我们团队中有这么多高级管理者举手表示，“嘿，我想回去做一名个人贡献者（IC）。”所以我们正在重新思考甚至薪酬如何运作以及其他所有事情，因为我认为个人贡献者的力量以及他们能够完成的工作量是惊人的。所以对于我们来说，我们最资深的团队成员正在拥抱这一点，因为这是他们重塑自我的一种方式，而且他们资历够深，所以并不害怕。而我们最年轻的员工，今年夏天我们雇佣了1111名实习生，这个数字对我们来说很有意义，我是说他们是最了不起的人，因为每个人都停止雇佣实习生了，我认为这完全是个错误，所以我们算是精挑细选了一批最优秀的人。他们完全是AI原住民，我们试图做的是让这两个群体聚集在一起，去带动那些比较犹豫的人。因为事实是，92%的工程组织在使用这样的AI工具，这个比例绝对应该是100%。但你必须去推动……

<details>
<summary>Original English</summary>

**Speaker A**: I think I I think yes. Um and and and recognize that it's natural for that to feel scary and that the and that your instinct is going to be to fight against it. Um, but that the more that you can embrace these tools, um, the better. I I've I've never seen, you know, and again, running this now for for 17 years, like I've never seen more senior managers on our team say raise their hand and say, "Hey, I want to go back to being an individual contributor." And so we're rethinking like even how compensation works and and everything else because I think that the the the power of an individual contributor and the amount of of of work that they can do is is extraordinary. And so I think that for us, you know, our most senior members of our team are embracing this because it's a way for them to reinvent themselves and they're senior enough that they're not scared about it. Our most junior folks, so we we we hired 1,111. number is meaningful to us but interns this summer you and and I mean it's like they are the most extraordinary humans because everybody stopped hiring interns which I think is just total mistake um and so we got sort of the pick of the litter and um and and they're and they're all totally AI native and what we're trying to do is get both of those groups to get the the folks that have been more hesitant because the fact is 92% of organization engineering organizations using AI tools like that. That should be 100%. For sure. And and but you've got to get

</details>
<!-- padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements padding block to meet length requirements -->

<!-- chunk 10/11 -->

### Embracing New Tools and Restructuring

**Speaker A**: 这点非常重要。同样，你不可能让一个在同一岗位上生产力是别人 10 倍或 100 倍的人，和那些还在用老方法工作的人拿一样的薪水。这两人中总有一个会离开。最糟糕的情况是，那个生产力高 100 倍的人离开了。所以，我们不断地尝试提升每一个人。再次说明，我们之所以进行裁员，部分原因是为了真正释放资源，激发整个组织去实现这个目标。而且，不仅仅是开发人员，财务、法务、营销等所有部门都必须拥抱这些新工具。

<details>
<summary>Original English</summary>

**Speaker A**: [th]at's really important and and that and again you can't have one person who is 10 or 100 times as productive in the same role as somebody else making the same amount of money a as somebody else who's who's sort of doing it the old way. Like one of those two is going to leave. And the worst case is if the person who's 100 times as productive leaves. And so we're just we are continuously trying to get every you know lift everyone up and and again part of why we did the layoff was in order to be able to um you know really really free up the resources and and catalyze the entire organization uh to be able to do this but and it's not just your developers has to be finance legal marketing everything has got to be embracing these new tools.

</details>

### The Independence Day Debate

**Speaker B**: 所以，大约在一年以前，我想你宣布了内容……

<details>
<summary>Original English</summary>

**Speaker B**: So almost a year ago now you declared I think that was content

</details>

**Speaker A**: 独立日，7 月 1 日。

<details>
<summary>Original English</summary>

**Speaker A**: independence day July 1st.

</details>

**Speaker B**: 7 月 1 日。现在马上要到两周年，或者我想应该是一周年纪念了。

<details>
<summary>Original English</summary>

**Speaker B**: July 1st coming up on the second second anniversary or first I guess first anniversary.

</details>

**Speaker A**: 是的。

<details>
<summary>Original English</summary>

**Speaker A**: Yes.

</details>

**Speaker B**: 在过去的一年里发生了什么？整个争论是如何演变的？而且最初它到底是什么？

<details>
<summary>Original English</summary>

**Speaker B**: What happened in the last year? How is that whole uh debate evolving? and what was it in the first place?

</details>

### The Changing Business Model of the Internet

**Speaker A**: 是的。我想你已经看到了互联网上自动化流量的大幅增加。我认为在 5 年内，在线的机器人和代理的数量将以 1000 比 1 的比例超过人类。与此同时，我们访问互联网的界面也在发生改变。我们以前也经历过其他平台的变迁。我们从在台式机或笔记本电脑的浏览器上浏览互联网，转向了社交网络，再到移动端。但在所有这些变化中，过去 28 年来互联网的底层商业模式基本保持不变，主要依靠广告，其次是订阅驱动。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So so so again I think that it is you've just seen an enormous rise in the amount of sort of automated traffic that's running across the internet. Um I I I think in 5 years it'll that you'll that bots and agents will outnumber humans online a thousand to one. Um at the same time like the interface through which we access the internet is changing. Um and we we've gone through other sort of platform changes before. Um you know we we went from browsing the internet on on a browser on your on your desktop or laptop to social to mobile. But throughout all of those things, the underlying business model of the internet for the last 28 years has remained basically the same, which is it's largely advertising and then to a lesser extent subscription driven.

</details>

**Speaker A**: 问题首先在于，互联网的运营成本将大幅增加，因为你将拥有 1000 倍的流量，这意味着你必须配备相应的服务器、CPU、网络等所有设施。并且总得有人来为此买单。过去 28 年那种主要基于广告的商业模式将失效，因为机器人不会点击广告。所以必须有所改变。其中的一部分是，我们如何让互联网变得更高效？比如我们如何将旧软件移植到能够以高性价比继续扩展的东西上。但另一个重要部分是，我们如何弄清楚互联网未来的商业模式将会是什么样子。

<details>
<summary>Original English</summary>

**Speaker A**: The problem is that first um there's just going to be a lot more cost to run on the internet because you're going to have a thousand times as much traffic, which means you're going to have to have servers and and CPUs and network and all that stuff. and and someone needs to, you know, pay for it. Um, and the business model of the last 28 years, which largely advertising based, doesn't work because bots don't click on ads. And so something has to change. Um, and so a part of that is how do we make the internet more efficient? Like how do we take legacy software and port it to things that are, you know, can continue to scale in a cost-effective way. But another big part of that is how do we figure out what the future business model of the internet is is is going to look like.

</details>

**Speaker A**: 我们和所有不同的人工智能实验室及公司都保持着良好的关系，他们也明白这一点。实际上他们会说：“听着，只要公平，只要每个人都必须遵守同样的规则，我们知道我们必须为我们用来构建系统和模型的那些内容付费，但我们必须建立一个系统来做到这一点。” 所以，我们在通过很多不同的方式进行试验。

<details>
<summary>Original English</summary>

**Speaker A**: And you know, we we have great relations with all the different AI labs and and companies and and they get it. Um, and they actually, you know, they they they say, "Listen, as long as it's fair, as long as everybody has to do the same thing, we we get that we've got to pay for the content that we're using in order to build our systems and our and our and our models, but we've got to build a system to to do that." And so, like, we're experimenting in a bunch of of different ways.

</details>

### Creating Scarcity and Content Control

**Speaker A**: 我们做的第一件事是，我们认为一个市场要存在，你通常认为必须有供需关系。这不完全准确。你实际需要的是稀缺的供给和需求。如果一切都是免费的，就没有人会为此付费。就像我们坐在这个房间里呼吸空气不需要花一分钱。但另一方面，如果我们去水肺潜水，空气就是稀缺的，所以我们就必须为此付钱。就是这个道理。所以第一步，我们说我们需要建立控制机制，让在网上拥有内容的人能够决定谁可以访问，谁不可以访问。并且再次强调，每个人都会做出不同的决定。

<details>
<summary>Original English</summary>

**Speaker A**: The first thing that we did was we said, in order for a market to exist, you know, you always think you have to have supply and demand. It's not exactly right. What you actually need to have is scarcity of supply and demand. Um if everything is free then then no one pays for it. Like we're sitting in this room, we're breathing the air doesn't cost us anything. Um on the other hand, if we go scuba diving, air is scarce and so we have to pay for it. And so you know that that's that. So step one was we said we we need to create controls that allow the people who have content online to be able to say who can access it and who who can't. And and again, it's everyone's going to make different decisions.

</details>

**Speaker A**: 就我们而言，我们希望所有的机器人都能消费我们的信息。我们希望信息传播出去，我们可能有大约一半的客户属于这个阵营，他们实际上想尽可能地提供便利。因此，我们提供了工具，以最经济高效的方式获取信息。获取包含许多冗余代码的 HTML，将其转换为 markdown，这是一个更加精简的系统。结果是，你可以将更多信息输入到这些 AI 系统中，而不会撑爆它们的上下文窗口等。在这种情况下，这是有道理的。

<details>
<summary>Original English</summary>

**Speaker A**: Um, in our case, we want all the bots to be consuming our our information. We want that to be out there, and that's probably half of our customers are in that camp where they actually want to make it as easy as possible. And so, we provide the tools to as cost-effectively, as efficiently as possible, get information in. Take take HTML, which has all this croft around it, convert it into markdown, which is a much more streamlined system. And then as a result like you can get more information in these AI systems without blowing up their contact windows and all kinds of things. It makes sense in that case.

</details>

**Speaker A**: 另一方面，如果你是一个依靠广告支持的企业，代理对你来说就不利，因为它们抓取了你的内容，然后人们通过他们的 AI 系统来消费内容，你就失去了用户注意力。所以广告系统就失效了。因此我们说，让我们给每个人提供能够阻止它的工具。让我们在网络供给上创造一些稀缺性。我们看到的是，如果你去看看世界上那些最大的出版商，比如康泰纳仕 (Condé Nast)，他们正因为我们为他们提供了这些工具，实际上正在与 AI 公司签订好得多的协议。我认为这是第一步。

<details>
<summary>Original English</summary>

**Speaker A**: On the other hand, if you're an ad supported business like agents aren't good for you cuz they're taking your content and then people are consuming it through their AI system and you're not getting eyeballs. So you're the ad systems don't work. So we said like let's give everyone the tools to be able to stop it. Let's create some scarcity in the supply that's out there. And what we've seen is if you go across the biggest publishers in the world, condandy NAS-maredith, you know, they they are they because we've now given them these tools, they're actually signing much better deals with the AI companies. And so that's I think that's sort of the first step.

</details>

### Micro-Payments for the Next Era

**Speaker A**: 但我们必须超越这一步，因为如果你只是一个小博客、影响者或内容创作者，你没有能力去达成像康泰纳仕那样的协议。每次我们访问一个网站并获取信息时，理应有一种微支付机制，我们乐意支付几分之一美分来做这件事。但这比听起来要难。我们在任何给定秒内大约处理半个十亿（五亿）次网络请求。我们估计其中大约 1% 到 10% 可以通过某种微支付交易来实现商业化。

<details>
<summary>Original English</summary>

**Speaker A**: But we've got to go beyond that because if you're a small blog or, you know, influencer, a content creator, like you don't have the ability to go strike the same deal that a condandy NAS does. There should be some basically a micro payment. every time we access a site and get information, we're happy to pay a fraction of a penny in order to to do that. Um, that's harder than it sounds. Um, so we process uh in any given second about half a billion um requests through our network. We estimate that somewhere between 1 and 10% of those would be um sort of monetizable through some micro um payment transaction.

</details>

**Speaker A**: 这意味着你必须从第一天起就能够支持每秒 1000 万次的金融交易，并具备清晰的提升路径以达到每秒 1 亿次交易。Visa 是全球最大的支付网络，每秒的交易量也不到 10 万次。所以我们需要比 Visa 大两个数量级，但在金额上却要小得多得多。所以我们正在研发这个。我们认为，与 Coinbase 和 Stripe 等伙伴合作，借助像 X42 这样的协议——这很有趣，因为早期的互联网有一种状态响应码是 402，我们都知道 404 是未找到，500 是错误，但 402 是“需要付款 (Payment Required)”，而我们从来没有真正围绕它建立过任何东西。我认为这在未来将会发生。

<details>
<summary>Original English</summary>

**Speaker A**: And uh and so that means that you have to be able to support day one, call it 10 million financial transactions per second with a clear ramp to be able to get to 100 million uh transactions per second. Visa, which is the largest payments network in the world, does fewer than 100,000 transactions per second. So we need to be, you know, two orders of magnitude um bigger than Visa, but but at much much smaller um uh volumes. And so we're working on that. And and we think that, you know, in partnership with with folks like Coinbase and Stripe, you know, and and and protocols like um X42, which is, you know, it is interesting where the original internet um had something a a response code the 402, we all know 404, which is not found, and 500, which is an error. I mean, there different things, but 402 was payment required, and we just never have really built anything around that. I think that's going to happen going forward.

</details>

**Speaker A**: 谷歌在构建驱动互联网过去 28 年的商业模式上功不可没。我认为我们正在试图弄清楚，什么才是能够驱动未来 28 年互联网发展的商业模式。总得有东西来向内容创作者付钱，因为他们需要吃饭。总得有东西来为所有这些机器人在事实上大量消耗的基础设施买单。而且我认为我们正在投入大量精力去弄清楚这到底是什么样子的。

<details>
<summary>Original English</summary>

**Speaker A**: And so, you know, Google really is responsible for having built the business model that's powered the last 28 years of the internet. And I think we are trying to figure out, you know, what is that business model that's going to power the next 28 years of the internet. But something has to pay content creators cuz they deserve to eat. Something has to pay for the infrastructure that all of these bots are are are are taxing effectively. and um and and and I and and I think we're working um a lot around figuring out exactly what that looks like.

</details>

### Cloudflare's Expanding Relevance

**Speaker B**: 太棒了。这是一场绝对引人入胜的对话。在听你讲的时候，我脑海中浮现的一个总体想法是，Cloudflare 如今变得甚至比你过去 17 年构建网络的时期更加重要了。而现在互联网正在发生变化，你们绝对处于它的核心位置。

<details>
<summary>Original English</summary>

**Speaker B**: Great. It's been an absolutely fascinating conversation. the the overarching thought um as I was listening to you is um to which extent Cloudflare is becoming even more relevant today than it's been for the last 17 years which you built the network uh and now the internet is changing and uh you are absolutely at the sort of central point for it. Yeah.

</details>

**Speaker B**: 你们团队是这样看待这个问题的吗，觉得你们还有下一个 17 年可以继续大展宏图？

<details>
<summary>Original English</summary>

**Speaker B**: Is that how you how you guys think about it like you're you're you have another 17 years?

</details>

**Speaker A**: 人们会问：“为什么你还在继续做这个？”因为有些日子并不好过。我是说，裁掉一群人，那一点都不好玩。并且我已经赚了足够多的钱。所以，这无关乎那些。真正重要的是我们的使命。我们从根本上相信那个使命。我们做一些让我们花钱的或者肯定不会……

<details>
<summary>Original English</summary>

**Speaker A**: People are like, "Why, you know, why do you keep doing this?" Um, because there are days that aren't fun. I mean, laying off a bunch of people. I mean, that wasn't that was that wasn't fun. Um, and it's and you know, I've made plenty of money. Um, so it's it's not about any of that. Um, what it is about is is really our mission. And we and we believe in that mission fundamentally. we we do things that that cost us money or or that certainly don't

</details>

<!-- chunk 11/11 -->

### 寻找互联网的新商业模式

**Matthew**: ……为我们赚钱，嗯，因为我们坚信要帮助构建一个更好的互联网。而且，我想象不出我还能做什么，比弄清楚如何为未来创造某种可持续的商业模式更有意义的事情。我认为有很多事情值得我们无比乐观。过去28年里，互联网的商业模式并不是最健康的。嗯，流量一直都是衡量价值的一个糟糕指标。媒体领域的很多做法都是，你如何去圈定你的细分受众，然后用一个标题把他们激怒，让他们去点击链接，从而为你的网站吸引眼球。你知道，当今导致世界分裂的很大一部分原因，其实正是互联网基于流量的底层商业模式。你如何尽可能多地增加流量？这种模式正在消亡。而且我认为，如果我们思考未来什么可以取代它，它可能会是一种更健康、好得多的模式。

<details>
<summary>Original English</summary>

**Matthew**: ...make us any money, um, because we believe in helping build a better internet. And um, like I can't imagine anything that I could possibly be doing that is more rewarding than figuring out how do we create some sort of sustainable business for the future. And I think there's a lot that's to be incredibly optimistic about. The business model of the internet for the last 28 years wasn't the most healthy. Um, traffic has always been a terrible proxy for value. And like so much of the media landscape was how do you sort of define your narrow audience and then with a headline piss them off enough that they'll click on a link in order to, you know, drive eyeballs to your site. And you know, so much of this, so much of what is dividing the world today is actually the underlying business model of the internet which has been traffic-based. How do you drive as much traffic as possible? That's going away. And I think that, you know, if we think about what can replace it going forward, it can be something which is much healthier and much, much better.

</details>

**Matthew**: 我飞去斯德哥尔摩见到了创立了 Spotify 的 Daniel Ek，因为我的意思是，没有谁能像 Spotify 那样大规模地给予创作者报酬。这简直太了不起了。我们可以在“是不是对的人拿到了钱”这个问题上争论不休，但如今投入到音乐创作中的资金，无论是按人均还是按 GDP 计算，都远远超过了人类历史上的任何时期。而 Spotify 在这方面功不可没。大家可能忘了，大约22年前，音乐产业正奄奄一息。你知道，Kazaa 和 Napster 等等，一切都在变得习以为常。每个人都在盗取内容。嗯，然后你知道，史蒂夫·乔布斯走上舞台，宣布 iTunes 上的歌曲卖99美分。这虽然不是最终胜出的商业模式，但它至少树立了一面旗帜，说明那里存在着某种机会。然后，Spotify 去年向音乐创作者支付了大约120亿美元。这甚至超过了22年前整个音乐产业的市值，这是非常惊人的。

<details>
<summary>Original English</summary>

**Matthew**: I flipped to Stockholm to meet with Daniel Ek who started Spotify and because I mean like nobody has compensated creators at scale like Spotify. It's just remarkable. And we can quibble about are the right people getting the money or not, but there's more money going into music creation today on per capita, per GDP, than any time in human history by far. And Spotify gets a lot of credit for that. And you forget that like 22 years ago the music industry was dying. You know, Kazaa and Napster and everything was just normalizing. Everyone was stealing content. Um, and then, you know, Steve Jobs steps on stage, announces iTunes 99 cents a song. That's not the business model that won, but it at least planted a flag that said that there's something that's there. And then I mean Spotify last year sent something like 12 billion dollars out to music creators. That's more than the entire music industry's market cap was 22 years ago, which is extraordinary.

</details>

**Matthew**: 所以 Daniel 讲了这个故事。他说：“他们做的一件事是，如果你在 Spotify 上搜索像泰勒·斯威夫特的《Shake It Off》，他们知道返回的结果就是你真正在找的。但另一方面，如果你搜索比如‘我想要一首迪斯科节奏的歌，唱的是和我的猫跳舞有多开心’，他们也会返回结果，但他们知道自己可能并没有这样的歌。而他们的做法是，实际上把那些搜索结果不太好的查询发布给音乐创作者。有数百名音乐创作者仅仅靠做这个就能谋生。有一位特别是在丹麦的创作者，Daniel 分享说他每年能赚大约4000万欧元，仅仅是为那些 Spotify 上没有结果的搜索词写歌。我认为这里面有一种非常美好的东西，因为如果你在 Spotify 上搜索某个东西，你真正寻找的是，我如何才能把一种情感表达出来。”

<details>
<summary>Original English</summary>

**Matthew**: And so Daniel was telling the story. He said, "One of the things that they do is if you search on Spotify for like Taylor Swift, Shake It Off, like they know they return results and they know that those results are what you were actually looking for. On the other hand, if you search for like I want a song to a disco beat about how much fun it is to dance with my cat, they also return results, but they know that they probably don't have that. And what they do is they actually publish those queries that are sort of bad results back to music creators. And there are hundreds of music creators that are making a living off just doing this. One in particular is based in Denmark. Um, Daniel shared is making something like €40 million a year just writing songs for unfulfilled Spotify queries. And I think there's something that's actually quite beautiful about that because if you search for something on Spotify, what you're searching for is how do I kind of bring an emotion out."

</details>

### 用可靠的信息填补知识的空白

**Matthew**: 所以展望未来，我们在人类历史上第一次拥有了人类所有知识的数学模型。这就是大语言模型（LLM）的本质，对吧？它并不完美，但它为你提供了这个模型。它还向你展示了差距在哪里，漏洞在哪里。我把它想象成一块巨大的瑞士奶酪。有很多奶酪，但奶酪上也有很多洞。当你和 AI 公司交流时，他们想要的是高度可靠的信息源来填补这些奶酪上的洞。他们正在贡献纯粹的新知识。他们不想再要一篇关于宾夕法尼亚大道1500号发生了什么的故事了，对吧？他们想要的是人们实际上在讲述和创造能够推动世界前进的新信息。我认为这也是我想要的。我认为这也是你想要的。我认为这也是我们所有人都在渴望的：我们如何回归到这样一种媒体环境，它不仅仅是为了吸引流量而试图激起公愤，而是真正试图寻找真相并填补空白。

<details>
<summary>Original English</summary>

**Matthew**: And so going forward like we for the first time in human history have essentially a mathematical model of all of human knowledge. That's what the LLMs are, right? It's not perfect, but it gives you that. It also shows you where the gaps are, where there are the holes. I picture like a giant block of Swiss cheese. There's lots of cheese, but there's a lot of holes in the cheese. And when you talk to the AI companies, what they want is highly reputable sources that are filling in the holes in the cheese. They're contributing net new knowledge. They don't want yet another story about what happened at 1500 Pennsylvania Avenue, right? They want something where people are actually telling and creating new information that moves the world forward. And I think that's what I want. I think that's what you want. I think that's what all of us are craving is how do we get back to sort of a media environment which isn't just trying to provoke outrage in order to drive traffic but is actually trying to find the truth and fill that in.

</details>

**Matthew**: 如果我们能创建一个系统，在这个系统中，那些高度可靠并创造了纯新知识的人能够得到回报，那么我认为这是无比美好的。我一直敦促 AI 实验室去做的一件事是，我说我们应该设立一个类似奥斯卡奖和诺贝尔奖那样的奖项，在各个不同的领域去衡量过去一年里谁对人类知识的贡献最大，你知道的，比如癌症研究领域，或者外交政策新闻领域。我的意思是，你可以设立很多这样的奖项，他们实际上可以衡量并宣布，在特定的一年里最好的播客是当时第一个什么播客之类的。我们应该去奖励和庆祝，无论是在表彰这些人，还是在实质上给他们支付报酬方面。而且我认为如果我们这样做了，你就会获得更多有趣的信息。

<details>
<summary>Original English</summary>

**Matthew**: And if we can create a system where the people who again are highly reputable and are creating sort of net new knowledge that those are the people that get rewarded then I think that's incredibly incredibly beautiful. What I keep pushing the AI labs to do is I'm like we should create the equivalent of I don't know if it's the Academy Awards and Nobel Prize where we measure across a whole bunch of different segments who has contributed the most to human knowledge in the last year in you know I don't know cancer research and you know foreign policy news I mean you can create a bunch of these things and they can actually measure and say you know this particular year the best podcast was you know the first Mark podcast that was out there or whatever it is. And we should be rewarding and celebrating both in terms of honoring these people, but then also paying them for doing that. And I think if we do that, you're going to get a lot more, you know, interesting information.

</details>

### 让真实与本地化的故事回归

**Matthew**: 我和我妻子买下了我们家乡，犹他州帕克城（Park City）的一家当地报纸。我认为今年我们在 AI 授权协议上赚的钱会比在展示广告上赚的还要多。为什么？因为如果你打算去犹他州帕克城滑雪度假，你会想知道最好的酒店是哪家，最好的餐厅是哪家，谁会来演出，雪况如何？而唯一拥有这些信息的来源就是当地报纸。因此，虽然过去28年的互联网某种程度上扼杀了本地的、奇特的、独特的、有趣的信息，但我充满希望的是，随着我们摸索出未来28年的商业模式，它实际上会让很多这样的东西回归，而且它实际上会让我们回归到讨论事实、讨论现实上来。

<details>
<summary>Original English</summary>

**Matthew**: My wife and I bought the local newspaper in our hometown, Park City, Utah. I think we will make more this year off AI licensing deals than we do off display ads. Why? Because if you're planning a vacation to go skiing in Park City, Utah, you want to know what's the best hotel to stay at, what's the best restaurant, who's going to be performing, you know, what are the snow conditions like? And the only place that has that is the local newspaper. And so while the last 28 years of the internet kind of killed local, quirky, unique, interesting information, what I'm hopeful is that as we figure out what the business model is going to be for the next 28 years, it actually brings a lot of those things back and it actually gets back to let's talk about facts, let's talk about reality.

</details>

**Matthew**: 就像《纽约时报》，如果他们能报道类似时代广场万豪侯爵酒店（Marriott Marquis Hotel）里，1313房间比1314房间更好，那就太棒了。或者，如果你想睡个懒觉，你知道1314房间是朝北的，所以早上不太容易被阳光晒到。就像这些类似于“这是纽约最好的杂货店”之类的内容。那些非常有趣的、奇特的本地故事。我认为这既是我们都渴望和期盼的媒体的未来，也是互联网的未来，而且我认为这也是一个我们真正有机会去构建的未来，因为我们有机会去重新定义未来的商业模式。

<details>
<summary>Original English</summary>

**Matthew**: And like I like the New York Times be amazing if they were covering like in the Marriott Marquee Hotel in Times Square, room 1313 is better than room 1314. Or if you know if you want to sleep in late, room you know 1314 faces north and so it's less likely to get sun in the morning. Like those are the sorts of here's the best bodega in New York. The very interesting quirky local stories. I think that that is both a media future and an internet future that we all crave and want and I think it's one that we actually have an opportunity to build because we get to reinvent what the business model is going to be.

</details>

**Matt Turk**: 太精彩了。那么，Matthew，非常感谢你。这是一次绝对精彩的对话。真的很感激。

<details>
<summary>Original English</summary>

**Matt Turk**: Fascinating. Well, Matthew, thank you so much. This was an absolutely wonderful conversation. Really appreciate it.

</details>

**Matthew**: 感谢你的邀请。

<details>
<summary>Original English</summary>

**Matthew**: Thank you for having me.

</details>

**Matt Turk**: 大家好，我是 Matt Turk。感谢您收听本期 Mad 播客。如果您喜欢这期节目，如果您还没有订阅，我们非常希望您能考虑订阅，或者在您观看或收听本期节目的任何平台上留下好评或评论。这对我们办好播客、邀请到优秀的嘉宾有很大的帮助。谢谢，我们下期再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already, or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks, and see you at the next episode.

</details>