---
author: The Pragmatic Engineer
date: '2026-04-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JiWgKRgdgpI
speaker: The Pragmatic Engineer
tags:
  - agent-acceleration
  - software-craftsmanship
  - developer-productivity
  - ai-impact
  - product-development
title: DHH：AI代理如何重塑软件开发与开发者价值
summary: 本期访谈中，**37signals**联合创始人**DHH**分享了AI代理如何彻底改变他及团队的软件开发工作流。他强调了软件美学和设计的重要性，并解释了AI赋能下，高级开发者生产力如何实现指数级提升。DHH还讨论了AI对行业和开发者角色的深远影响，认为编程的黄金时代可能正在结束，未来更需要兼具品味、判断力和商业洞察力的工程师。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - David Heinemeier Hansson
  - Kent Beck
companies_orgs:
  - 37signals
  - OpenAI
  - Anthropic
  - Google
  - Apple
  - Amazon
  - Shopify
  - Work OS
  - Sonar
  - Static
products_models:
  - ruby-on-rails
  - umachi
  - basecamp
  - hey
  - chatgpt
  - opus
  - openclaw
  - fsd
media_books:
  - Extreme Programming
  - Small Talk Best Practices
  - Terminator 2
status: evergreen
---
### 软件工程的价值与美学

**采访者**: 我觉得你非常看重**软件工程**这门手艺。

<details>
<summary>Original English</summary>

**采访者**: I feel that you very much value software engineering as a craft

</details>

**David**: 非常看重。我认为**美学**即真理。当一件东西很美时，它很可能是正确的。我认为这在**数学**、**物理学**以及许多不同领域都是如此。

<details>
<summary>Original English</summary>

**David**: hugely. I mean I think aesthetics is truth. When something is beautiful, it's likely to be correct. I think this is true in mathematics. This is true in physics. This is true in a lot of different domains.

</details>

**采访者**: 我想知道**AI**是否在某个方面，关于我们以前从未做过的工作的影响。

<details>
<summary>Original English</summary>

**采访者**: I wonder if there's a part of AI about the impact of doing work that we would have not done before.

</details>

**David**: 我们内部处理的项目数量众多，这些项目我们以前甚至从未想过要启动。我们最受**代理加速**的人之一**Jeremy**说：“我们要优化P1。”字面意思就是，对于最快的1%的请求，我们要让它们更快。现在有点紧张的是，我发现大多数全身心投入的人，他们工作比以往任何时候都更努力。我现在在自己身上也看到了这一点。当你能够通过对这些代理的一小时监督，变得如此有效和有影响力时，这真的令人陶醉。我需要告诉自己，这不像是一次限时销售。

<details>
<summary>Original English</summary>

**David**: The number of projects we have tackled internally that we would never even have contemplated starting on or Legion. Jeremy, one of our most agent accelerated people, went like, "We're going to do P1. We're going to optimize P1." Literally the fastest 1% of requests, we're going to make them even faster. There's a bit of tension right now is that most of the people I find who are all in, they're working harder than they ever have. And I've seen that with myself now, too. When you can be this effective and impactful on an hour of supervision of these agents, it's really intoxicating. And I need to go, do you know what? This is not like a limited sale.

</details>

### DHH的AI观转变与软件哲学

**采访者**: 在**Lex Friedman的播客**上，你当时对**AI**仍持非常怀疑的态度，这是理所当然的。

<details>
<summary>Original English</summary>

**采访者**: on Lex Freriedman's podcast. You were still rightfully so very skeptical of AI.

</details>

**David**: 这是一个细微之处，也许有点自私，但我实际上不认为我的观点改变了。改变的是环境。

<details>
<summary>Original English</summary>

**David**: This is a nuance point and maybe it's self- serving, but I don't actually think my opinions have changed. What have changed is how has the creator of Ruby on Rails changed how he builds software now with AI agents?

</details>

**采访者**: **Ruby on Rails**的创造者**David Heinemeier Hansson**（通常被称为**DHH**）现在如何使用**AI代理**来构建软件？**DHH**是**Ruby on Rails**的创造者和**37signals**的联合创始人。六个月前，他在**Lex Friedman的播客**上抨击了**AI编码工具**的能力。然后，在冬季假期的几周内，他来了个180度大转弯，在所有事情上都采取了**AI优先**的策略。在今天的对话中，我们探讨了**David**和他在**37signals**的团队今天如何构建软件，以及**AI工具**如何让他们比以往任何时候都更有雄心。为什么**Ruby on Rails**和**Analytics**可能会比现在更受欢迎，因为它们都非常适合与**AI代理**协作。为什么品味和漂亮的软件变得更加重要，以及为什么杰出的设计师和工程师，那些关心手艺的人，需求量可能会更大，还有更多。如果你对科技行业最有经验的开发者之一如何看待**AI工具**的实用性，以及这些工具如何影响关心工艺的软件工程师感兴趣，那么这集节目就是为你准备的。本集节目由**Static**呈现，这是一个统一的平台，用于功能标志、分析、实验等等。请查看节目笔记，了解更多关于他们以及我们的其他季节赞助商**Sonar**和**Work OS**的信息。**David**，很高兴你来到这里。

<details>
<summary>Original English</summary>

**采访者**: how has the creator of Ruby on Rails changed how he builds software now with AI agents? David Hayam Hire Hansen often referred to as DHH created Ruby on Rails Omachi and is a co-founder of 37 signals. He bashed capabilities of AI coding tools on Lex Friezen's podcast 6 months ago. Then over the course of a few weeks over the winter break, he did a 180 turn and went AI first on everything. In today's conversation, we cover how David and his team at 37 Signals build software today and how AI tools are making them more ambitious than ever before. Why Ruby on Rails Analytics could become even more popular than they are today as they are both well suited working with AI agents. why taste and beautiful software are becoming more important and why both standout designers and engineers who care about the craft could become more in demand and many more. If you're interested in what one of the most experienced builders in the tech industry thinks about the practical utility of AI tools and how these tools could impact software engineers who care about the craft then this episode is for you. This episode is presented by static the unified platform for flags analytics experiments and more. Check out the show notes to learn more about them and our other season sponsors sonar and works. David, it's awesome to have you here.

</details>

**David**: 谢谢邀请。谢谢你的到来。我应该说你在**哥本哈根**。这是我目前选择的城市。它是一个美丽的城市，有很多优点。那么，你最近在忙些什么呢？

<details>
<summary>Original English</summary>

**David**: Thanks for having me. Thanks for coming. I should actually say you're in Copenhagen. That's my city of choice at the moment. It's a beautiful city. It's got so much going for it. And so, what have you been up to?

</details>

### DHH的项目与开源哲学

**David**: 我总是在建造东西。在**互联网**上，我建造东西已经整整三十年了。我记得是94年开始接触它，然后就再也没有停止过。在过去的六个月里，我一直在建造各种东西。其中之一是一个新的**Linux**发行版，叫做**Umachi**。

<details>
<summary>Original English</summary>

**David**: I'm always building stuff. I have been building stuff for a good damn three decades now on the internet. I got started back in 94, I think it was, when I first got exposed to it and basically just never stopped. And in the past six months, I've been building a variety of things. One of them is a new Linux distribution called Umachi.

</details>

**David**: 我大约在两年多前转向了**Linux**。一开始在**Ubuntu**上玩了一段时间，然后意识到我实际上想从零开始构建自己的系统，基于**Arch**和**Hyperland**。所以，我投入了很多时间在**Umachi**上。它是在**勒芒24小时耐力赛**期间作为暑期项目开始的。那一周有很多空闲时间，所以我开始捣鼓它，很快就发展起来了。看到即使在像**Linux发行版**这样拥挤的市场中，这也真是一段鼓舞人心的旅程。市面上大约有7000种不同的发行版，其中一些历史悠久，许多甚至基于类似的理念。仍然有新事物的空间，这提醒我们，世界上所有的想法可能都已被提出，但这不重要，因为你的独特之处尚未被采纳。我把我的独特之处放到了**Linux**上。**Umachi**为我打造了一个完美的电脑系统，我看到了和以前完全一样的事情。每当我构建出真正击中我个人痛点的东西时，就会有成千上万的人和我一样，或者足够接近我的喜好，他们也能从中找到乐趣。无论是**Ruby on Rails**、Kamal，还是摆脱云，都是如此。是的。对于**Rails**，你**解决自己的痛点**。你只是构建自己的组件，然后开源它们。这就是它的开始方式吗？基本上，我在2000年代初期学习了**Ruby**，并在2003年我们开始构建**Basecamp**时，真正对其进行了测试。当时我没有规定必须使用什么来构建它。在此之前，我为许多客户项目工作，他们会说：“我们要用**PHP**构建这个，因为我们有懂得**PHP**的人。”所以你必须使用它。然后我们构建自己的系统，我们正在构建**Basecamp**。我可以自由选择。所以我选择了**Ruby**，当时**Ruby**在**Web应用程序**方面几乎没有任何工具。所以我不得不自己构建所有东西，这变成了**Ruby on Rails**，它仍然发展得很好。我仍然深度参与其中。我认为在某些方面，**Ruby on Rails**正在经历一次复兴，因为它是构建**Web应用程序**最**Token高效**的方式之一。它非常适合我们现在处理的**代理工作流**。我们会看看这能持续多久。也许所有的代理会在五分钟内编写**机器代码**或**汇编语言**。所以也许会结束。但目前，**Token效率**仍然很重要。代理生成人类能够阅读和验证的代码仍然很重要。这在某个时候也可能结束。但就目前而言，这真是一段有趣的旅程，看到这些解决我个人痛点的项目与更广泛的社区产生共鸣，然后人们出现并愿意提供帮助。我的意思是，对于**Umachi**，它才问世六个多月，我们有大约400名贡献者对这个发行版进行了代码更改。除此之外，我们还有数万人安装并将其用作日常驱动。所以，我总是喜欢发现一些新颖、鼓舞人心的东西，**Ruby**，或者说发现一个自91年以来就存在的操作系统听起来很奇怪，但对于很多人来说，**Linux**现在就是那个发现，因为他们以前没有在个人电脑上使用过它。我帮助了一批新的**Linux**用户，希望他们甚至能成为爱好者，因为我稍微降低了门槛。我让它更容易上手。我让默认安装看起来很棒，这样他们就不必投入100小时来调整系统才能开始使用，这真的很有趣。但更有趣的是，**Ruby on Rails**和**Umachi**这两个项目，它们不仅仅是爱好项目。我喜欢爱好项目，我将永远做这些，但我也喜欢将它们应用于商业。所以在**37signals**，我们基于**Ruby on Rails**建立了20多年的整个业务。我们现在在大多数开发者机器上运行**Linux**，因为我们现在有了自己的发行版。

<details>
<summary>Original English</summary>

**David**: I switched to Linux about a little over two years ago, I think, now. First spent some time on Ubuntu, having fun with that, and then realizing I actually wanted to make my own system from scratch, building it on top of Arch and Hyperland. So, put a lot of time into Amachi. It got started as a summer project in between racing at the 24 hours of Lama. there's a lot of downtime in that week. So, I just started hacking on it and it really took off very quickly thereafter. It's been a truly inspiring ride to see that even in a market as crowded as Linux distributions, there's about 7,000 different distributions out there, some of them with long pedigrees and many of them even based on sort of kind of similar vibes to some extent. There's room for something new and it's a great reminder that all the ideas in the world may be taken and it doesn't matter because your spin on it isn't. And I put my spin on Linux. Billachi built the perfect computer system for me and saw exactly the same thing I've ever seen. And whenever I build something that really just hits the spot for me personally, there are thousands of others just like me or close enough to what I like that they find the same pleasure and joy in it. Whether it was Ruby on Rails, Kamal, getting out of the cloud, any of these things, it's the same syndrome. Yeah. With with Rails, you were literally scratching your own itch. You were just building your own components and then open sourcing them. Is that how it started? Basically, I picked up Ruby in the early 2000s and really put it to the test in 2003 when we started building Base Camp and I did not have a mandate of what to use to build it. Prior to that, I'd been working for a lot of client projects that would say, well, we're building this in PHP because we have someone who knows that. So, this is what you have to use. And then we were building our own system. We're building Basec Camp. And I was free to choose. So I chose Ruby and at the time Ruby didn't have any tooling or ve not very much when it came to web applications. So I had to build it all myself and that turned into Ruby on Rails which is still going strong. I'm still very heavily involved with that. I think in some ways Ruby Rails is having a little bit of a renaissance now that it is one of the most token efficient ways of building web apps. It's ideally suited for the agent workflows we're dealing with now. We'll see how long that lasts. Maybe all the agents are going to be writing machine code or assembler in about five minutes. So maybe that comes to an end. But for the moment, token efficiency still matters. And it still matters whether the agents produce code that humans are able to read and verify. That may also come to an end at some point. But as it is right now, it's uh been a fun ride to just see these kinds of projects where I'm scratching my own itch resonate with a much larger community of people who then show up and want to help. I mean for Umachi which has only been around for what is that just over 6 months now we have what 400 contributors who've made code changes to the distribution and on top of that we have tens of thousands of people who've installed it and uses as their daily driver. So, I always love that discovery of something new, novel, and inspiring like Ruby or it sounds weird to talk about discovery of a operating system that's been around since what 91, but for a lot of people, Linux now is that discovery because they have not been using it on their personal computer. So, they're seeing it for the first time. And for me to help a new cohort of Linux users and hopefully even enthusiasts come to be because I'm flattening the curve a little bit. I'm making it easier to get started. I'm making the default installation just look amazing so that they don't feel like they have to invest 100 hours into tweaking the system to get going is really fun. But what's also fun of course is that both of these things, both Ruby and Rails and Amachi were not just hobby projects. I love hobby product and I will always do those, but I also like to apply them to business. So at 37 Signals, we built an entire business for 20 plus years on top of Ruby and Rails. We're now running Linux on the majority of developer machines because we now have our own distro.

</details>

**采访者**: 所以这是**Uber**？人们可以选择吗？

<details>
<summary>Original English</summary>

**采访者**: So it's obi people can choose, right? can they

</details>

**David**: 差不多吧。我们一开始提供了开放选择，但到某个时候，它就不再有意义了。就像在**37signals**，如果有人说我想用**Django**来写这个东西，我们要用**Python**和这个其他框架，即使你用的是**Ruby on Rails**，这也是没有意义的。所以我们从早期的邀请试用转向了，那是我第一次转用**Linux**的时候，我只是说，嘿，如果你想试试，就试试看。后来，当**Umachi**变得更严肃时，我只是说，所有技术方面的人都全身心投入吧，**iOS开发者**当然除外，但任何从事**Web**开发、**Ruby**开发、**DevOps**的人都应该使用**Linux**，因为首先，这更接近我们部署的环境。我们从第一天起就在服务器端部署**Linux**。对于开发者和系统操作员来说，我确实认为更接近生产环境并更熟悉工具是一种实质性的优势。除此之外，我们正在构建这个发行版，我们应该有尽可能多的双手来帮忙。鉴于我是这家公司的**CTO**，我来设定技术方向，这就是我们前进的方向。

<details>
<summary>Original English</summary>

**David**: well sort of kind of we started with a with an open choice and then at some point it just doesn't make sense anymore in the same way it would not make sense for someone to be at 37 single and say I want to write this thing in Django we're going to use Python and this other framework even if you have Ruby and Rails and you're doing that so we pivoted from an early invitation to play around that was what when I first switched to Linux just said like hey if you want to check it out check it out then when things got a little more serious with Amachi I just said let's go all in for everyone who's on the technical side of things, not the iOS developers of course, but anyone who's working with the web, who's working with Ruby, who's doing DevOps, they should be on Linux because first of all, that's closer to what we deploy. We've always deployed on Linux. We've been a Linux shop on the server side since day one. For developers and system operators, I actually think it is a material advantage to be closer to your production environment and just be more familiar with the tools. Then on top of that, of course, we are building this distribution and we should have as many hands help out as possible. And given the fact that I'm the CTO of this company, I get to set the technical direction and this is the direction we're going.

</details>

**采访者**: 能否简单回顾一下，你现在的工作状态是怎样的，以及公司的整体业务情况如何？你不断地构建、发布新的、令人兴奋的酷产品。我想**Fizzy**是最新推出的。

<details>
<summary>Original English</summary>

**采访者**: Can you just like do a like just a very short recap of of you know like how you right and right now where are you like where where is the business as a whole and you know you keep you keep building you keep launching new and exciting and just cool stuff. I think Fizzy was the latest one.

</details>

### 37signals的创业历程与产品理念

**David**: 是的。**37signals**成立于1999年。它最初是一家**网页设计**公司，然后我在2001年，也就是两年后加入，和**Jason**合作了几年咨询项目。直到2003年，我们开始开发**Basecamp**，并在2004年发布。实际上，这发生在**Facebook**上线的前一天或后一天，这是一个有趣的巧合，我们属于同一时代和同一批人。大约一年内，我们意识到这个项目正在腾飞，于是我们全职投入，从咨询公司转型为一家**软件公司**。

<details>
<summary>Original English</summary>

**David**: Yes. So 37 signals was founded in 1999. It started as a web design firm and then I joined up in 2001, two years after and for a couple years, collaborated with Jason on these consulting projects and then it was in 2003. We started work on Base Camp, released it in 2004. Actually, either the day after or the day before Facebook went live, which is kind of a funny coincidence that we were of that same time and cohort. And within about a year, we realized this thing was taking off and we went full-time and switched from being a consultancy to being a software company.

</details>

**采访者**: 太棒了。

<details>
<summary>Original English</summary>

**采访者**: Awesome.

</details>

**David**: 现在已经22年了，甚至更久。在这段时间里，我们发布了大量产品。**Basecamp**是第一个，至今仍是最大、最重要的产品，这也有点有趣，因为你有时可能会产生这种错觉：随着你学习更多，经验更丰富，你会变得更聪明，有更好的想法。但实际上，对于许多人来说，他们的第一个想法就是最好的想法。我毫不羞愧地说，**Basecamp**是我们有史以来最成功的商业想法。我非常自豪我们能够让它持续发展和繁荣20多年。很少有**软件公司**，更不用说**软件产品**，能拥有如此长的寿命和遗产。但这些年我们也尝试了很多事情，并取得了一些其他巨大的成功。我们在2020年推出了我们的电子邮件服务**Hey.com**，这在你看来是一项疯狂的任务。

<details>
<summary>Original English</summary>

**David**: And that's now 22 years ago, a little more than that. And in that time, we've released a ton of products. Basec camp was the first. Remains the biggest and most important, which is also kind of funny because you sometimes perhaps have this delusion that as you learn more and as you get more experience, you'll get smarter and you'll have better ideas. And like, no, there's tons of people for whom their first idea was the best idea. And I have no shame in saying that Base Camp was the best idea objectively in terms of a business that we've ever had. And I'm incredibly proud that we've been able to keep that going and growing and flourishing for over 20 years. Very few software companies, let alone software products, can boast of that longevity and legacy. But we've tried a ton of things over those years and had some other great successes. We launched hey.com our email service back in 2020 which was a crazy mission when you think about it.

</details>

**采访者**: 这是一个完全被**Google**的**Gmail**主导的行业，**Gmail**是一款好产品。

<details>
<summary>Original English</summary>

**采访者**: Here is a sector completely dominated by a single player Google with Gmail that's a good product.

</details>

**David**: 它17年来没有真正改变，但它非常稳定，很多人对此非常满意。他们认为自己头脑中存在这种二元性：他们既讨厌电子邮件，但不知何故又没有将其与使用**Gmail**这一事实联系起来，我觉得这很奇怪。但无论如何，我们推出了这款产品，它不仅与这个根深蒂固的产品竞争，而且这个产品在任何主要类别中的市场份额可能都比我能想到的任何其他美国产品都要大。我认为**Gmail**占据了**85%**的电子邮件流量，这听起来很疯狂。也许是**80%**。它非常高。基本上是**Gmail**，然后所有其余的都在这个微小的一小部分中。所以，我们认为，在使用**Gmail**之后，我不知道我什么时候注册的，几周后，我得到了一个邀请码。那是一个非常聪明的发布，从那以后我就一直在使用它。所以，这**Gmail**的使用历史**17年**了。在这段时间里，我对那些不尽如人意的地方积累了很多看法。我们将所有这些看法都融入到一个新的**软件产品**中。我们花费了将近两年时间开发它，累计投入了数百万美元的研发资金。并于2020年夏天发布了它，顺便说一下，这是一个发布产品的好时机。2020年由于各种原因不太好过。我们当时有点想找个空档，有没有一周是整个世界不那么疯狂的？

<details>
<summary>Original English</summary>

**David**: It hasn't really changed in 17 years but it was really solid and lots of people are perfectly content with it. They think they hold this duality in their head where at once they both hate email but somehow don't connect it to the fact that they're using Gmail which I find curious but either way we launched this that is not only a competitor to this very entrenched product that has probably a greater grasp on market share in any major category than any other product I can come to mind of in the US I think Gmail is something like 85% of all email traffic, which sounds insane. Maybe it's 80%. It's incredibly high. It's basically Gmail and then all the rest is in this tiny little part of the graph. So, we thought that after using Gmail, I used it since I don't know when I signed up, a few weeks into it, I got one of those invite codes. That was a really clever launch and I used it ever since. So, that's literally 17 years or something of that of Gmail usage. And over that time, I built up a lot of opinions about things that didn't work quite like I would prefer it to work. And we put all those opinions into a new software product. Spend about almost 2 years developing it. Millions of dollars in accumulative R&D funds. And launched it in the summer of 2020, which by the way, time to launch a product. 2020 wasn't great for a whole host of different reasons. We were kind of trying to slot in a can there just be a week where the whole world is not just insane.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah.

</details>

**David**: 我们最终选择了一周。我们上线了，然后就与**Apple**展开了一场生死之战。

<details>
<summary>Original English</summary>

**David**: We finally picked a week. We went live and then we had the battle of our lives with Apple.

</details>

**采访者**: 和**Apple**。我记得那件事。

<details>
<summary>Original English</summary>

**采访者**: With Apple. I remember that.

</details>

**David**: 最终...

<details>
<summary>Original English</summary>

**David**: And ultimately

</details>

**采访者**: 他们不想批准你的应用。

<details>
<summary>Original English</summary>

**采访者**: they didn't want to approve your your app.

</details>

**David**: 他们不想批准我们的应用，除非我们支付过路费，也就是**30%**。

<details>
<summary>Original English</summary>

**David**: They didn't want to approve our app unless we paid the toll fee, the 30%.

</details>

**采访者**: 他们基本上是说你不能进入**App Store**，对于像这样的电子邮件产品来说，那无疑是死刑。

<details>
<summary>Original English</summary>

**采访者**: And they were basically willing to say you can't be in the app store, which for an email product like that is a death sentence.

</details>

**David**: 是的。你不仅必须在手机上使用，而且必须在**iPhone**上使用。如今也是如此。大多数**Hey**的付费客户都是**iPhone**用户，因为那是美国最大、最富裕的市场，而美国是世界上最富裕的软件市场。所以为了业务能正常运转，我们必须在**iPhone**上。经过两周史诗般的拉锯战，幸运的是，时机恰好与**WWDC**相吻合，**Apple**当时不希望看起来像**歌利亚**（Goliath）一样压垮一个...

<details>
<summary>Original English</summary>

**David**: Yes. you have to be on not just mobile phones but specifically the iPhone. This is true today. The majority of hey paying customers are iPhone users because that's the largest most affluent market in the US and the US is the most affluent and market software market in the world. So for that business to work we needed to be on the iPhone. After a twow weekek epic struggle back and forth, thankfully time to perfection with WWDC where Apple preferably didn't want to look like the Goliath squashing a

</details>

**采访者**: ...开发者，小开发者，我们最终被允许进入，**Apple**在事后修改了规则以适应。这是一个小胜利，不是最终胜利，但至少让我们得以存在。而**Hey**最终取得了巨大的成功。讽刺的是，部分原因在于**Apple**给了我们两周的**铺天盖地**的报道。回顾过去，我想我当时不会那样赌博，因为结果会是零，对吧？**Apple**拒绝了我们的应用。

<details>
<summary>Original English</summary>

**采访者**: developer, tiny developer, we ended up being allowed in and Apple sort of rewrote the rules after the fact to make it fit. Um, it was a small victory, not the ultimate victory, but at least it allowed us to to be there. And hey, ended up being an enormous success. In part, ironically, because Apple gave us wall-to-wall coverage for two weeks. When I look back upon that, I think I wouldn't have gambled like that because the outcome would have been zero, right? Like, uh, Apple refuses our app.

</details>

**David**: 我们签了200人，然后应用就死了。相反，发生的是他们给了我们一个价值数百万美元的**发布活动**，并在所有主流媒体上进行报道，我们在最初几周内签下了数万人。那是一场疯狂的事件，但也非常令人满意。另一个令人满意的事情是，我就是喜欢**Hey**。我每天都使用它。我基本上使用**Basecamp**来处理**Web应用程序**方面的工作，那是我们所有协作工作的场所。而我的第二大应用，很多时候甚至是我的第一大应用就是**Hey**，因为我所有的工作都在电子邮件中完成。我不断与人沟通，我在写作，我在电子邮件中做了很多事情，就像很多人一样。让它成为一种愉快的体验，一个良好的环境，以及我的收件箱比**Gmail**那样更神圣一点，**Gmail**里世界各地的陌生人可以随意让你的口袋震动，如果你的通知默认是开启的，这对我来说简直是疯狂。是的，这种想法是，可以直接访问我最重要的日常优先事项列表，任何人都可以往里面添加东西，这太疯狂了。无论如何，**Hey**不会那样做。我们有**筛选器**，在你表示愿意听取某个人的意见之前，没有人可以进入你的收件箱。大多数时候，我都会拒绝大部分人，对吧？东西会进入筛选器，我们可以点赞，我愿意听这个人说话，点踩，我永远不想再听到这个人说话。

<details>
<summary>Original English</summary>

**David**: We sign up 200 people and the app is dead. What instead happened was they gave us a multi-million dollar launch campaign and coverage in all major media and we signed up tens of thousands of people in those first weeks. That was uh an insane event but uh also very satisfying. And the other satisfying thing was I just love Hey. I use it every day. I basically use base camp in terms of web applications. That's where we do all our collaborative work. And then my number two app and many days it's my number one app is hey because I just do all my stuff in email. I am constantly communicating with people. I'm writing. I'm doing a lot of stuff in email as many people do. And having that be a pleasurable experience and a nice environment and my inbox being a little more sacred than what happens with Gmail where total strangers around the world can just make your pocket buzz if you have notifications turned on which they are by default. Just seems insane to me. Right. this idea that there's direct access to one of my most important daily priority lists like anyone can put something on that insane. Anyway, hey doesn't do that. We have the screener and no one gets to reach your inbox before you've said I want to hear from this person. And most of the time I say no to most people, right? Like things end up in the in the screener and we have thumbs up. I will hear from this person, thumbs down, I'll never hear from that person again.

</details>

**采访者**: 这就是我联系你的方式。我的意思是，我确定我们没有在**X**上连接，但我发了一封电子邮件，因为你的电子邮件是公开的，而且你的筛选器似乎奏效了，因为它给了我一个赞。

<details>
<summary>Original English</summary>

**采访者**: This this is how I reached out. I mean, we were I'm not sure we were connected on on X, but I I sent an email cuz your email is out there and your screener seems to have worked cuz it gave me the thumbs up.

</details>

**David**: 它确实奏效了，因为筛选器就是我。所以，甚至没有**AI**试图判断我是否想听你的。因为事实证明，每天检查你的筛选器并选择是或否其实并没有那么麻烦，因为世界上没有那么多人。如果你对那些烦人的、不断纠缠的推销员说不，他们通过**Gmail**设法七次阅读你的收件箱，那么工作量就会少很多。我还要说，这也非常令人满意，因为当我使用**Gmail**时，我会被他们依赖的销售策略所束缚，那就是你回信说：“不，谢谢，我不感兴趣。”然后他们会再次回复。现在你觉得：“等等，我现在有义务回复这个人吗？我有点觉得我有。”偶尔我最终会回复，即使我不回复，他们仍然可以访问我的收件箱。所以下周我还会收到他们的来信。他们有一整套**滴灌营销**活动，他们都这样做，对吧？任何外联都是七封电子邮件，而不是一封。如果你表现出任何生命的迹象，那可能是52封。这根本不是**Hey**的工作方式。我点踩一次，就再也不会收到那个人的来信。你能够多快地将你的花园从杂草中整理出来，这真是令人惊叹。然后突然间，只有美丽的花朵。突然间，电子邮件不再是一件苦差事。所以你想去闻闻玫瑰花香。突然间，我收到的电子邮件中，大多数都是我愿意阅读的，都是我愿意收到的人发来的。这真的是我们**Hey**的根本使命：我们能让电子邮件再次变得可爱吗？电子邮件被那么多人讨厌，因为系统太差了，因为它们基于最初的假设，即电子邮件只是大学用来让科学家相互交流的，而科学家非常有礼貌，不会因为一些愚蠢的应用而烦你52次。不，他们是受人尊敬和美好的，对吧？美好的理想，美好的想法，美好的协议，都是为了那些规范和那些人而设计的，然后你把它放到大世界中，你意识到，啊，不是每个人都拥有这样的规范和礼貌，尤其是当推销员介入时。你需要更好的防御，对我来说，对我们来说，以及对我们所有众多客户来说，**Hey**就是那个防御。它是一种再次爱上电子邮件的方式，我发现拥有一个宏大的“为什么”真的很重要，这可以追溯到**维克多·弗兰克尔**（Victor Frankle）的《活出生命的意义》（The Meaning of Man Finding A Why）。找到一个“为什么”能让你在寒冷、不适和烦恼时（就像你用电脑构建东西时经常遇到的那样）穿过雪地。虽然大多数时候不应该这样，但偶尔会遇到。如果你有一个非常强大的“为什么”，为什么我们要构建这个？它是为谁服务的？我们正在努力改善世界吗？即使这不像让人们再次爱上电子邮件那样宏大，那么携带任何你需要承担的负担都会更容易，也更愉快，如果你能这样安排的话。

<details>
<summary>Original English</summary>

**David**: It did because the screener is me. So, there's not even AI trying to sus out whether I want to hear from you or not. Because what turns out to be true is it's actually not that ownorous to once a day go through your screener and say thumbs up or down because there aren't that many people in the world. And if you say no to the annoying pestering salespeople who within Gmail managed to read your inbox seven times, then the workload is much less. And it's very satisfying, I will say too, because when I was using Gmail, I would get roped into this sales tactic that they of course rely on, which is that like you write back and say like, "No, thank you. I'm not interested." And then they would respond again. And now you feel like, "Wait, am I now obligated to respond to this person? I kind of feel like I am." And occasionally I would end up writing and even if I wouldn't write, they still have access to my inbox. So I would hear from them again next week. They have a whole drip campaign. They all [ __ ] do, right? That any outreach is seven emails. It's not one emails. It's seven emails. And if you show any sign of life, it's probably 52. That's just not how it works. And hey, I say thumbs down one time, never hear from that person again. It's actually amazing how quickly you can curate your garden from that weed. And then suddenly there's just beautiful flowers. Suddenly email is not a chore. So you want to go smell the roses. Suddenly the majority of things that end up in my email or things I want to read is from people I want to hear from. And that was really the fundamental mission for us with hey can we make email lovable again? Email is so hated by so many people because the systems are so poor because they're based on the original premise that email is just what universities use for scientists to talk to each other and scientists have really good manners and will not pester you 52 times about some stupid app they want to sell you. No, they're respectful and beautiful, right? beautiful ideal, beautiful thought, beautiful protocol designed for those norms and those people then you let it into the world at large and you realize ah not everyone is endowed with such norms and such politeness and especially when sales people get involved. you need better defenses and for me and for us and for all our many customers hey is that defense it is a way to love email again and I find that it's really important actually to have a grand why this is all the way back to Victor Frankle the meaning of uh of man finding a why allows you to walk through the snow when it's cold and uncomfortable and annoying which many things are when you're building with computers they are cold and uncomfortable and annoying. Now, it shouldn't be that most of the time, but occasionally that will be there. And if you have a really strong why, why are we building this? Who is it for? What are we trying to do to improve the world? Even if that's not more grand than just letting people love email, it's a lot easier and it's a lot more enjoyable to then carry whatever burdens you got to pack if you can set it up that way.

</details>

### 企业级功能与产品开发流程

**采访者**: 现在是谈论我们的季节赞助商**Work OS**的好时机。拥有一个强大的“为什么”能让你构建出伟大的东西。但当你构建并开始将其销售给企业客户时，他们会期望拥有**SAML**、**SSO**、**目录同步**、**审计日志**和**细粒度权限**等功能。这些并非小功能，它们是**系统**。这些系统可能需要数月才能构建和维护。**Work OS**可以在几天内而不是几个月内为你提供**API**、企业级开箱即用的**用户管理**。所有这些都旨在与你的产品无缝集成。这就是为什么像**OpenAI**、**Traffic**和**Cursor**这样的公司都在使用**Work OS**。专注于构建你的产品，让**Work OS**处理企业基础设施。接下来，让我们回到**David**，谈谈旧的思维方式与新的思维方式。戴上你的开发者帽子，你能告诉我你是如何构建它的吗？你说花了两年时间，但最初只有一两个人开始构建吗？我确定你作为技术人员肯定大量使用了**Ruby on Rails**。然后，我不知道，可能还有一些**原生**的东西。但两年似乎很长，尤其是考虑到你是一家小公司。你很灵活，你是一位优秀的开发者。你雇佣了优秀的开发者。突然之间，两年过去了。到底是什么原因花了这么长时间，当然它是一款漂亮的产品。但从表面上看，我认为作为开发者，我们可能会有这种想法，我会觉得，一个有才华的团队花了两年时间。

<details>
<summary>Original English</summary>

**采访者**: This is a good time to talk about our season sponsor, Work OS. Having a strong why is what gets you to building something great. But after you build it and start selling it to enterprise customers, they expect things like SAML, SSO, directory sync, audit logs, and fine grain permissions. And those are not small features. They're systems. Systems that can take months to build and maintain. Works gives you APIs, enterprise ready off, and user management in days instead of months. All designed to fit cleanly into your product. That's why companies like OpenAI and Traffic and Cursor run on Work OS. Focus on building your product. Let Work OS handle the enterprise infrastructure. With this, let's get back to David and the old way of thinking versus the new way of thinking. Putting our your developer hat on like can you talk talk me through on how how you built it? You said it was two years, but was it just one or two people starting to build it? I'm sure as tech you obviously must have used Ruby on Rails a lot. Uh, and then I I don't probably some some native stuff as well, but the two years seems a lot especially because you know you're you're a small company. You're a nimble. You're a great developer. I'm you hire great developers. Suddenly it's been two years. What what took so long for and of course it's beautiful product. But right on the surface I think as developers we might have this this thing where I look at it as like two years with with a talented team.

</details>

**David**: 这就是**Hacker News**上对所有事情的嘲讽，对吧？就像我可以在一个周末内完成它一样。我的意思是，众所周知，**Dropbox**曾经被这样说，我可以在一个周末内完成它。**iPod**刚推出时，我们可以用它做同样的事情。它当时只有5GB，没有**Wi-Fi**，速度比**Modem**还慢。所以我理解这一点，因为我也有同样的本能。我认为那是我们作为开发者的盲点。我们认为我们是神，可以在瞬间实现任何事情。你也完全可以做到。你现在可以在几个小时内完成一个**原型**，比一个周末还快。

<details>
<summary>Original English</summary>

**David**: That's the hacker news quip to basically everything, right? Like I could have built that in a weekend. I mean famously stated with Dropbox that I could have built that in a weekend. We could have at the original iPod when it launched. It was like 5 GB bits uh no Wi-Fi uh whatever less speed than Nomat lane. So I get that because I also have that same instinct. I think that is our hoopers as developers. We think we are gods and we can make anything happen in no time at all. And you totally could. You can make a prototype happen in these days faster than faster than a weekend, right? like in in in a few hours we should be able to have

</details>

**采访者**: 启动一个代理，是的。

<details>
<summary>Original English</summary>

**采访者**: kick off an agent. Yeah.

</details>

**David**: 但弄清楚你到底想构建什么需要更长的时间，而要发布值得发布的东西则需要更长的时间。至少对我们来说是这样，我认为对于任何能做出好东西的人来说都是如此。最初的**Hey**项目技术方面只有我一个人。我们大多数主要产品都是这样开始的，要么只有我一个人，要么再加一个开发者，但都是在一个非常小的团队中，直到我们形成一个**构想**，直到我们有一个**架构**，直到我们有一个产品方向。我发现如果你把一群人投入到一个不确定的方向，你实际上会走得更慢。如果你不知道你想要什么，一百万人也无法为你构建它。你必须弄清楚你想要什么。我们稍后可以讨论这一点，但这正是**AI**近期进展正在戏剧性地改变事情的地方。现在更快地弄清楚我想要什么。但对于**Hey**来说，是我，然后是**Jason**，以及一个设计师，两个设计师，一个非常非常小的团队，试图弄清楚产品的形态，试图弄清楚如果你要挑战**Gmail**，你不能只是做一个蓝色的**Gmail**。没有人会买账。没有人会感兴趣。它必须是**新颖**的，这意味着它必须是好的，它必须解决人们甚至没有明确表达的**Gmail**问题，因为人们对**Gmail**问题的表达是“我讨厌电子邮件”，这正如我们所讨论的，有点误导。我的论点是你讨厌**Gmail**。不仅仅是**Gmail**，而是大多数基于旧的“任何人都可以访问你的收件箱”方式构建的电子邮件系统。但弄清楚这些，弄清楚产品的形态需要一段时间，而且以这种方式进行也很有趣，你可以不断调整，而且你没有无限的能力。最初的**Basecamp**也是以同样的方式构建的。技术方面只有我一个人。这是一种**Shape Up方法论**吗？在尝试让设计师具备“它应该如何运作”而不是“它应该如何看”的意图时，存在**Shape Up**的思维。同时也要弄清楚它应该如何看，产品应该美观、独特和吸引人等等。所以这也需要时间。但弄清楚它应该如何运作是首要的。弄清楚核心是什么，最重要的部分是什么，并将其一一解开。但对于**Hey**，就像我们所有主要产品一样，我们从一个绝对小的团队开始，通常只有一个编程人员，然后是一两个设计师。然后我们不断前进。突然间，某个东西点击了，我们觉得“这个不错，这里有些东西”。然后就会有一个加速期。我们会再招几个人，然后当我们在距离完成**20%**左右时，我们就会说，好的，现在我们知道地形是什么样的了，如果所有人都投入进来，我们可以走得更快。

<details>
<summary>Original English</summary>

**David**: But figuring out what you actually want to build takes a lot longer and arriving at something that's worth publishing takes longer still. At least it does for us and I think it does for anyone who arrives at anything good and the original hey construction was just me on the technical side. This is actually how we've started majority of our major products is either it's just me sometimes it's one additional developer but is in a tiny tiny team until we have a shape until we have a an architecture and we have a direction of where the product is going to go. I've found that you actually go slower if you pour a bunch of people into a direction that is uncertain. If you don't know what you want a million people is not going to build it for you. You have to figure out what you want. We can talk about this later, but this is where AI's very recent progress is changing things dramatically. It is now quicker to arrive at what do I want? But for hey, it was me and then it was Jason and uh one designer, two designers, very very small team trying to figure out the shape, trying to figure out if you're taking on Gmail, you can't just do Gmail in blue. No one's going to buy that. No one's going to be interested in that. It's got to be novel, which means it's well, not just novel, it's got to be good. It's got to solve problems that people haven't even articulated they have with Gmail because the articulation people have of their problems with Gmail is I hate email, which as we talked about is a bit of a misdirection. My contention is you hate Gmail. And not just Gmail, but most email systems built on the old way of anyone has access to your inbox and all that stuff. But figuring that out, figuring the shape out takes a while and it's also fun to do in this way where you noodle with it and you don't have infinite capacity. The original base camp is built the same way. It was just me on the technical side. Is this a shape uplogy? There's shape up thinking in trying to actually endow the designer with an intention of how should it work not just how should it look and figuring out it's also how it should look product should be beautiful and they should be unique and appealing and so forth. So that also takes time. But figuring out how it should work is primary. Figuring out where's the epicenter, what's the most important part and teasing all that apart. But with Hey, as with all the major products we've done, we start with an absolutely tiny team, often just one individual on the programming side and then one or two individuals on the design side. And then we go, we go, we go, we go. Suddenly something clicks and we go like, this is good. There's something here. And then there's a bit of a ramp. we take on a few more people and then when we get within maybe the last 20% we go okay now we know what the terrain looks like we can go way faster if everyone piles in.

</details>

### 设计师在产品开发中的新角色

**采访者**: 所以有一点非常有趣，你可能觉得理所当然，但这与大多数**风险投资**资助的**初创公司**以及**Uber**、**Facebook**这样的大公司启动项目的方式非常不同。在这些公司，你找来**产品经理**...

<details>
<summary>Original English</summary>

**采访者**: So one thing that is super interesting and you might take it for granted but it's very different to how most startups uh that raise VC money which I'm very familiar with uh and and big companies Uber Facebook you name it the way projects would start there is you take the product manager

</details>

**采访者**: ...与大约半个设计师合作...

<details>
<summary>Original English</summary>

**采访者**: who works with maybe maybe half a designer

</details>

**采访者**: ...然后制定规范，之后开发者才参与进来。而我听到的是，你让一两个设计师和一个开发者合作，这对我来说非常新颖。你如何看待设计师？你最近甚至还雇佣了一位设计师，**Zoltan**，我正在和他聊天。一个很棒的家伙。

<details>
<summary>Original English</summary>

**采访者**: and comes up with a spec and then developers get involved later and what I'm hearing what is very novel to me is you take one or two designers and a developer how you think about designers Even you recently hired a designer, Zultan actually, who I'm I'm chatting with on the side. A great guy.

</details>

**采访者**: 但我的感觉是，你对设计师的看法可能与行业中其他公司有所不同。

<details>
<summary>Original English</summary>

**采访者**: But my sense is you think of designers a little bit different than potentially the rest of the industry does.

</details>

**David**: 我们确实如此。**37signals**的设计师不仅仅是来让规范看起来漂亮。他们是来寻找规范应该是什么的。他们在很多方面是**产品经理**。他们是“如何”和“为什么”的发现者，在某些情况下是通过推断客户反馈，在其他情况下则是纯粹的直觉，并将这些提炼成我们应该构建什么以及它应该如何运作，然后在此基础上，他们还负责构建它。他们负责编写**CSS**，他们负责编写**HTML**，他们经常至少涉猎**JavaScript**和**Ruby代码**，以实现某些功能。现在有了**代理加速**，他们可以完成整个过程，不一定是最终合并的代码，而是整个产品的最终形态和设计。但我认为我们在这方面非常独特。我们在招聘设计师时发现，许多在其他公司工作的设计师不习惯同时扮演**产品经理**的角色，思考我们应该构建什么，也不习惯扮演**实现者**的角色，将其塑造成**CSS**和**HTML**。我发现当你将这三顶帽子结合在一起时，你就会拥有一个了解他们所使用的材料，了解它们如何拉伸，了解接缝应该如何切割的人，因此他们可以与**互联网**的**结构**进行原生地工作。当你直接使用**CSS**，当你直接使用**HTML**时，你对这个媒介的需求会更加敏感。我发现这可能与你是**珠宝设计师**的情况非常相似。你应该了解黄金的特性。你应该了解它如何弯曲以及它的强度。**建筑师**应该对承重结构等具有一定的工程理解。这并不是说建筑师将设计整个东西，然后我们开始浇筑混凝土。你仍然有工程师帮助你，但你越了解你正在使用的材料，你就越有可能做出顺应纹理的东西，因此最终会感觉正确，感觉良好。

<details>
<summary>Original English</summary>

**David**: We very much do. Designers at 37 Signals are not just here to make a spec look pretty. They're here to find what the spec should be. They're product managers in many ways. They are the finders of the how and the why in many cases deducing in some cases customer feedback in other cases just pure intuition and distilling that into what should we build and how should it work and then on top of that they're also responsible for building it they're responsible for doing the CSS they're responsible for doing the HTML they're quite often responsible at least dabbling in the JavaScript and the Ruby code to get to something functional now with agent acceleration. They do the whole thing, not necessarily as it will be merged, but the whole thing in terms of here's the final shape and design of what it should look like. But I do think we are very peculiar in this sense. And we have found this when we've been trying to hire designers that many designers working other companies are not used to also wearing the product manager hat, figuring out what we should build and wearing the implementation hat, shaping it into CSS and HTML. I found that when you combine these three hats into one, you have an individual who know the materials they're working with, know how they stretch, know which way the seam is supposed to be cut, and therefore works natively with the fabric of the internet. When you're working directly in CSS, when you're working directly in HTML, you're just much more in tune with what this medium wants. And I find that that's probably quite similar if you're a jewelry designer. You should know the properties of gold. You should know how it bends and the strength. An architect should have some engineering understanding of loadbearing structures and so on.

</details>

### Apple产品设计理念的变迁与AI的影响

**David**: 并不是说建筑师将设计整个东西，然后我们开始浇筑混凝土。你仍然有工程师帮助你，但你越了解你正在使用的材料，你就越有可能做出顺应纹理的东西，因此最终会感觉正确，感觉良好。快速谈谈**Apple**。我认为这就是为什么像**Daring Fireball**和**Gruber**这样的历史超级粉丝对新方向感到失望的原因之一，因为**Apple**过去代表着那些设计精美的原生**Mac应用程序**，这是一种正在消亡的品种，它们基本上已经死了。现在我们有了**Electron**，我们也可以讨论一下它，它在我看来受到了太多不公正的批评。它有糟糕的实现，但它只是一个“盒子里的Web”。但失望在于失去了那种感觉，我认为这与**Mac**的**原生感**相似，它有一种延展性。就像按钮的布局，所有你称之为**原生应用程序**的东西，要么感觉是**合成**的，要么感觉是**真实**的。而今天，它们都是合成的。没有什么真实感留下了。我认为对于**Web**来说也是如此。现在**Web**是一个更大得多的平台，因此受到了更多的关注。所以有更多的人在努力提高它的质量。但在大公司，拥有那种动态是非常罕见甚至不存在的。我认为其中一些将会改变。**代理加速**将使设计师在这方面更具能力。所以这个行业正在向我们的基本立场靠拢，这也很滑稽，因为编程方面也是如此。当我谈到**Basecamp**最初发布时，技术方面只有我一个人，这在很长一段时间内听起来是**缺乏抱负**的，甚至是**错误的**，甚至有人说我在撒谎，认为你不可能构建任何真实、有意义、大型的东西，除非你有一个更大的团队，因为那只会是一个玩具产品。而我从一开始的见解就是，那当然是错误的，因为你没有使用**Ruby on Rails**，你没有使用更好的工具可能带来的**加速**。现在我们都在意识到，如果使用**代理加速**，一个人实际上可以构建出非常有价值的团队。

<details>
<summary>Original English</summary>

**David**: Not to the degree that the architect is just going to design the whole thing and then we start pouring concrete. you still have uh engineers helping you out, but the more you understand the materials you're working with, the more you're likely to come up with something that cuts along the grain and therefore ends up feeling correct, feeling good. Just a quick hop to Apple. I think this is one of the reasons why some of the historic super fans like Daring Fireball and others uh Gruber have been disappointed by the new direction is that Apple used to stand for these exquisitly designed native Mac applications which is an dying breed like they're essentially dead. Now we have Electron which we can talk about that too gets way too much hate in my book. There's crappy implementation of that, but it's just a web in a box. But the disappointment with losing that sense, and I think it's about the same thing that the Mac, its native feel has a stretch to it. Like the button placements, everything you would call a native application either feels synthetic or it feels authentic. And today, it's all synthetic. There's no nothing authentic about it left. And I think for the web it's the same thing. Now the web is a much much larger platform and therefore it's gotten much more attention. So there are way more people working on that quality of it. But at the large companies it's exceptionally rare to non-existent to have that kind of dynamic. I think some of that is going to change. Agent acceleration is going to empower designers to be more capable in these ways. So the industry is coming a little towards our fundamental stance which is funny too because the same is true on the programming side. When I talked about base camp being a product of just me on the programming side for launch that for so long sounded unambitious or even wrong or even to the point of lying from some quarters of the internet like yeah but you can't build anything real anything meaningful anything big unless you have a team that's much larger because it's just going to be a toy product right and my insight from the start was that's of course [ __ ] because you just haven't used Ruby on Rails you just haven't used the acceleration that's possible if you use better tools. Now we're all realizing that we're using realizing oh so if you use agent acceleration a single individual actually can build something highly valuable team.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yes.

</details>

**David**: 看到行业正在走向“小团队更好”的方向，这很有趣，因为现在沟通成本的**对数曲线**所带来的成本节约开始变得相关。这也许是我们接下来可以讨论的话题之一，**代理加速**正在真正改变初级开发者和高级开发者之间的谈判条件。

<details>
<summary>Original English</summary>

**David**: And that's just fun to see that like the industry is coming towards oh smaller teams are better because now the cost savings you have on the logarithmic curve on communication cost starts to be relevant. And this is one of the things maybe we can talk about this where agent acceleration is really changing the bargain between junior developers and senior developers.

</details>

### 美学与效率：软件开发的驱动力

**采访者**: 让我们谈谈这个。但在那之前，我是否觉得你非常重视**软件工程**这门手艺，这非常明显，但我的感觉是，你重视**设计**、**用户体验**、**软件设计**，就是说，构建出感觉良好的东西。无论是软件还是硬件，你也同样重视它作为一门手艺，你也在寻找它。我这样理解正确吗？

<details>
<summary>Original English</summary>

**采访者**: Let's talk about this. But before we go into that, do I feel that you very much value software engineering as a craft, which is very obvious, but what I'm sensing is you're valuing design, user experience, design, designing on software design, like you know, like building stuff that feels good. May that be software, hardware, you also value that as a craft and and you look for it like the these two things. Do I sense this correctly?

</details>

**David**: 非常正确。我的意思是，我认为**美学**即真理。当一件东西很美时，它很可能是正确的。我认为这在**数学**、**物理学**以及许多不同领域都是如此，当你达到某种具有正确**美学品质**的东西时。这就像我们有一种直觉，引导我们走向那种**美**，因为它恰好也是正确的、高贵的，值得我们追求的。我也碰巧相信，这就是让人快乐的原因。被美丽、功能良好的事物包围是幸福的关键部分。事实上，我也会从负面角度来说。焦虑和沮丧的一大来源就是当一切都变得糟糕时，当一切都延迟时，当触摸界面没有响应时，当你必须重新启动它时，当你打电话给旅行社，他们却无法处理，因为他们陈旧的糟糕**Cobalt系统**不允许时。对吧？这个世界充满了“**劣质化**”，也就是说，从好变坏，甚至变得非常糟糕的东西。我认为这是文明的严重困扰之源。如果我们能被更多美丽的事物、更美丽的系统包围，我们就能真正提高人类的幸福感。这既包括其**美学外观品质**，也同样包括其**美学内在品质**，因为我发现这两者通常完美和谐。**史蒂夫·乔布斯**（Steve Jobs）之所以关心盒子内部，是因为他直觉地知道，那些关心**电路板布局**的人，也会是那些在**用户界面**上精益求精的人，也会是那些关注**打开外壳**的人机工程学的人。所以我认为，如果你是一个被这些美学吸引的人，那么基本上别无选择，我认为每个人都是如此。只是对你是否被吸引有不同程度的认知，但你希望让一切都变得美丽。对我来说，特别是**Ruby**，它一直是一种标志性的语言，因为它产生了我的书籍中最美丽的代码，几乎没有竞争对手。当然也有其他东西可以以某种方式变得美丽，比如我发现**Smalltalk**的极简主义非常美丽，但那不是我想居住的房子。**Ruby**是我想要居住的房子，因为它拥有那种**美学品质**，同时又不对其**意识形态**僵化，这非常罕见。我发现现在我们再次谈到**AI**，当某人以这种方式痴迷时，他们会有点偏执，这就是权衡，这就是代价。我发现**Ruby**以某种方式设法做到了**广阔**而又**高度专注**于此。但总的来说，我们必须拥有美丽的事物，我们必须使用美丽的工具，我们必须产生美丽流畅的交互，这就是我们应该将自己视为**匠人**的方式，我们关心把它打磨到没有一丝瑕疵。

<details>
<summary>Original English</summary>

**David**: Hugely. I mean, I think aesthetics is truth. When something is beautiful, it's likely to be correct. I think this is true in mathematics. This is true in physics. This is true in a lot of different domains that when you arrive at something that has the correct aesthetic quality. It's like we have an intuition that guides us towards that level of beauty because it also happens to be correct and noble and something to aspire for. I also happen to believe it's what makes people happy. Being surrounded by beautiful, well functioned objects is a key part of happiness. In fact, I'll put it in a negative way, too. One of the great sources of anxiety and frustration is when everything is [ __ ] When everything is laggy, when that touch interface doesn't register, when you have to restart it, when you're calling a travel agent, they can't do something because their old shitty cobalt system won't let them. Right? The world is full of not just in shitification. That is things that went from being good to being bad to just plain bad, just plain awful. And I think it is a serious source of malaise for civilization. that we could literally raise the bar of human happiness if we were surrounded by more beautiful items, more beautiful systems. Both in the sense of its aesthetic exterior qualities, but just as much in terms of its aesthetic interior qualities, because I find those two things are usually in perfect harmony. The reason why Steve Jobs cared about the inside of the box was because he intuitively knew that the kind of people who care about the layout of the print board will be the kind of people who sweat the details on the user interface will be the kind of people who sweat the ergonomics of opening the case. So I think there's essentially no choice if you are a person who is attracted to these aesthetics which I think is everyone. there's just varying levels of u awareness about whether you are or not but that you want to make it all beautiful and for me Ruby in particular has been this seinal language because it produces the most beautiful code in my book there's barely even competition like there are other things that can be beautiful in a way like I find looking at small talk for example very beautiful in its minimalism but not the house I want to live in Ruby is the house I want to live in because it's got that aesthetic equality while not being rigid about its ideology which is a very rare aspect too. I more often find now we can refer to IV again is that when someone is obsessed in this way they are a little narrow-minded like that's the trade-off that's the price and I find that Ruby has somehow managed to be both broadscoped yet also intensely focused on on this but overall we have to have beautiful things we have to work with beautiful tools we have to produce beautiful fluid interactions this is how we should see ourselves as crafts people that we care about polishing it until there are no splinters left.

</details>

### AI如何改变软件开发工作流

**采访者**: **AI**如何改变你的工作方式？你认为它如何改变你的手艺，或者我们只是谈谈手艺？你正在**37signals**招聘人员，他们同样关心**设计**和**软件工艺质量**。它如何改变你从手艺中获得的东西，或者它如何让它变得更好或更糟？我只是想从你对**AI**的看法开始，因为上次你长时间谈论这个是在**Lex Friedman的播客**上，你当时对**AI**仍然非常怀疑，这是理所当然的。那时的工具不同，效果也不好，我想你当时非常严厉地抨击了它，但从那以后情况发生了变化。

<details>
<summary>Original English</summary>

**采访者**: How is AI changing how you work and how do you think it's changing your craft or just let's just talk about the craft of again you're you're hiring people in 37 signals who similarly care about design and and software craft's quality how it's changing what you get out of the craft or how it's how it's making it better or or worse in some ways I I I just want to you know start with like how has your view changed because the last time you you talked in in length about this that was on Lex Freriedman's cast and you were still rightfully so very skeptical of of AI. It was a different set of tools. It didn't work as well and I think you you went there bashing it pretty hard but things have changed since.

</details>

**David**: 这是一个细微之处，也许有点自私，但我实际上不认为我的观点改变了。改变的是**环境**和**事实**。我在那期节目和许多其他文章中都指出过，从一开始我就能看到我们有了一个新的、新颖的东西，它将改变一切。**ChatGPT**的发布，大约三年前，当时就非常清楚地表明，这是你可以在时间轴上标记的东西。你会想，这是**计算机科学**或世界历史上发生的所有重要事件。天哪，这是**ChatGPT**的发布。以这种方式与计算机交互，并看到它们进行推理，即使这可能仍然是一个有争议的术语，但对我来说，很明显这些东西非常聪明，在许多方面比我更聪明。至于这些聪明是否来自**权重**和**数据**，那又如何？我们不知道人类意识是如何运作的。我们几乎不知道人类智慧是如何运作的。所以，我们不要对什么构成意识或智能如此武断。至少，我发现这种区别没有用处，即使思考它很有趣。但我发现早期模型和早期**人机工程学**（例如**自动补全**，或者你编辑器中的**Copilot**和**Cursor**试图猜测下一个字符）的体验是...

<details>
<summary>Original English</summary>

**David**: This is a nuance point and maybe it's self- serving but I don't actually think my opinions have changed. What have changed is the circumstances and the facts which uh is is something I called out on that show and in many other writings was right from the get-go I could see that we had something new and novel here that was going to change things. Chat GBT its launch what three years ago was clearly and obviously even at the time something you would mark on a timeline. You're like here are all the important things that happened in the history of computer science or the world. Yoinks, there is the launch of Chat GBT and interacting with computers in this way and seeing them reason, even if that's still a disputed term perhaps, but to me it seemed obvious that these things were freaking smart, smarter than me in many ways, whether those smarts came from parenting weights and data. So what? We don't know how human consciousness works. We don't know how human wisdom or intelligence works. barely. So, let's not be so categorical about what constitutes consciousness or intelligence. At least, I find no utility in that distinction, even if it's fun to ponder. But what I found with the early models and the early ergonomics where it was autocomplete, where it was co-pilot and cursor in your editor trying to guess the next character,

</details>

**采访者**: ...有时会搞得一团糟。

<details>
<summary>Original English</summary>

**采访者**: it it would be sometimes littering it. Right.

</details>

**David**: 是的。我发现它令人恼火。我发现它就像我们试图进行对话一样。你不会让我说完一句话。你总是试图问：这是你说的意思吗？这是你说的意思吗？你会想：闭嘴。我能把话说完吗？我当时认为，即使它偶尔能够加速，但它也经常出错，以至于那种加速感觉像是一种麻烦，即使它在某种程度上是**净积极**的，但对我来说并不是。也许我放弃得太早了。但我就是不喜欢那样。我认为模型不够好。我认为使用**自动补全**与**代理协调器**的方式简直是糟糕透顶，令人恼火。事实上，我一度对这个行业的方向感到有点悲观，因为我以为我们都会这样做。我们都会坐着敲键盘。不，谢谢。

<details>
<summary>Original English</summary>

**David**: Yes. I found it infuriating. I found it as we're trying to have a conversation. You won't let me finish a sentence. You're constantly trying. Was this what you meant? Was this what you meant? You're like, shut the hell up. Can I just finish a thought? And I thought, even if it is capable of occasionally accelerating, it's also wrong so often that that acceleration feels like a nuisance, even if it's somehow net positive, which it wasn't for me. Or maybe I gave up too soon. But I just did not enjoy that. I didn't think the models were good enough. I thought the way of using the models with autocomplete versus agent harnesses was just dreadful, annoying. In fact, to the point that I got a little pessimistic about the direction of the industry for a hot second because I thought this was what we were all going to do. We're all going to sit and do tap tap tap. No, thank you.

</details>

**采访者**: 嗯，**Cursor**甚至有，我甚至得到了他们的一些赠品，是一个**敲击键**。

<details>
<summary>Original English</summary>

**采访者**: Well, cursor even have they had I even got one of these one of their swags was a tap key.

</details>

**David**: 没错。这感觉很，而且我从他们那里得到了它。它真的很酷，设计得很好，而且所有这些漂亮的设计，但是...

<details>
<summary>Original English</summary>

**David**: Exactly. which which felt very and I I haven't I I got it from them. It's really cool, very well designed and all that beautiful design, but

</details>

**采访者**: ...但**反乌托邦**。

<details>
<summary>Original English</summary>

**采访者**: but dystopian

</details>

**David**: **反乌托邦**。

<details>
<summary>Original English</summary>

**David**: dystopian

</details>

**采访者**: 当我看到那个，我记得那一度是个梗，我们只需要键盘上的三个字符，对吧？

<details>
<summary>Original English</summary>

**采访者**: when I see that and I remember that was a meme for a while just we only need three characters on the keyboard, right?

</details>

**David**: 我想起了**《辛普森一家》**的那一集，**Homer**把一只机械鸟放在键盘上，它只是向下敲击并按下**回车键**，因为他一直在做的就是按**回车键**。除了突然有一个关于核核心过载的警告，鸟只是按了**回车键**，然后整个事情就烧毁了。我想，“哇，这真是个巧合。”**《辛普森一家》**确实预测了所有事情。但我不喜欢那种使用方式。尽管我仍然对这个总体的**发展方向**保持热情，因为它确实令人惊叹。对我来说，我试图将这种惊叹作为一种**导师模型**，一个不主导的**结对程序员**。拥有**ChatGPT**和其他模型在身边真是太棒了，比如“我不完全理解这个，这里有一段代码，这里有一个问题，你能告诉我它为什么这样运作吗？你能告诉我它有什么问题吗？”因为我从第一天起就一直在使用**互联网**，对吧？**Google**就是为此而生。这里有一个错误消息。这里有一个概念。也许我在**Stack Overflow**上找到了一些东西，一些**被动攻击**的宅男在那里告诉所有人他有多聪明，然后底部有我正在寻找的解决方案。或者我根本找不到，这有点令人沮丧。使用**ChatGPT**模型，我经常能得到一个非常好的解释。

<details>
<summary>Original English</summary>

**David**: I thought of that episode of uh The Simpsons where Homer puts a mechanical bird on the keyboard that just dips down and hits enter because all he's been doing is hit enter. Except suddenly there's a warning about the nuclear core overloading and the bird just hits enter and the whole thing burns down. I'm like, "Wow, that's quite a parallel." The Simpsons really does predict everything. But I did not like that style of using it. As much as I retained my enthusiasm for the general direction of travel because it truly is amazing and the amazement to me I tried to embrace as a tutor model as a pair programmer who doesn't drive it was amazing to have chat GBT and the other model just be there for like I don't understand this fully here's a piece of code here's a question can you tell me why it works like that can you tell me what's wrong with it because that's how I've been using the internet since day one right that's what Google was for here's an error message. Here's a concept. Maybe I find something on Stack Overflow with some passive aggressive nerd telling everyone why he's so smart and then at the bottom there's the solution I'm looking for. Or I don't find it at all and that's just kind of frustrating. With the chat GBT model, I very often got a really good explanation.

</details>

**采访者**: 是的，这实际上是我和游戏开发者**Jonas Tyroller**聊过的，他开发了一款非常酷的畅销游戏。我喜欢玩它，这正是在标签补全的时期。他说他的工作方式是关闭了**IDE**中所有**自动补全**功能，因为他觉得很烦人。然后偶尔他会向**ChatGPT**提问，或者进行更长的对话，然后他会进入思考模式，我在做这些事情，哦，我需要一些帮助，好的，这里是具体细节，我正在接受。不知何故，他觉得他一整天都通过控制它来保持专注。不知何故，这些习惯听起来像你说的同样的事情。它有点夺走了你的控制权。

<details>
<summary>Original English</summary>

**采访者**: Yeah, this was actually I talked with a game developer Jonas Tyroller who who built this really cool bestselling game. I loved playing it and this was during this time of of the tab completion and he said that in his the way he works is he just turned off all auto completions in his ID uh because he got annoyed by it and then every now and then he went to chat GPT to ask something or have a longer thing and then he had the mode of like I'm thinking and I'm doing this stuff oh I need some help okay here's the specifics and I'm taking and somehow it felt that you know like he just he was in the zone the whole day by controlling it and and somehow those habits sounds like You know, you're saying the same thing. It kind of took it away from you. Us.

</details>

**David**: 完全正确。我当时确实有点担心这会成为我们所有人的方向，我们都会成为那只鸟，我不想成为那只鸟。然后我想，那我还应该做什么呢？也许**种土豆**。那在**丹麦**有很长的传统。也许我可以尝试一下。

<details>
<summary>Original English</summary>

**David**: Exly. Exactly. And I did get a little worried that that was going to be the direction that we were all going to be the bird and I didn't want to be the bird. Then I was like, well, what should I do instead? Maybe like farming potatoes. Like that's a long tradition here in Denmark. Maybe I could take that up.

</details>

### AI代理：从辅助工具到工作流核心

**采访者**: 但后来幸运的是，两件事发生了。**Claude**的代码大约在春天开始，夏天逐渐发展，到秋天，在一种新的使用代理来帮助你编写代码的方式上获得了一些牵引力，那就是**代理协调器**，对吧？这才是我们从**AI**向**代理**过渡的地方。突然间，**AI**有了工具。它可以使用**Bash**。它可以使用你终端上所有的一切。它可以调用**互联网**来获取适当的信息。它能够做的不仅仅是推理你给它的东西，或者来自源上下文文件的输入。然后模型**Opus 4.5**，对我来说，是我们将在生产线上拥有的另一个点，它是第一个能够持续不断地以其输出质量让我震惊的模型。它基于模糊输入进行分析的质量，更重要的是，它输出的质量。它生成的代码我想要**合并**，几乎不需要任何修改。如果我想修改，我可以告诉它，它会记住，并且下次不会犯同样的错误。对我来说，这两者的结合是解锁的关键。

<details>
<summary>Original English</summary>

**采访者**: But then thankfully two things happened. A clot code in what is that? starts in the spring, gets going sort of over the summer, then by the fall has some traction on a new way of using agents to help you code where with the agent harnesses, right? This is really where we transition from AI to agents. Suddenly the AI has tools. It can use bash. It can use everything you got on your terminal. It can call the internet in for appropriate information. it it just is capable of doing more than just reasoning about a thing you gave it uh or input from a source context file. And then the models opus 45 to me is the other one of the other points we're going to have on the line where it's the first model that continuously and consistently would shock me with the quality of its output. it quality of its analysis on the basis of vague inputs and even more importantly the quality of its output. It produced code I wanted to merge without very much if any alteration and if I did want to do alteration I could tell it and it would remember and it would not make the same mistake next time. that to me the combination of those two things was the unlock

</details>

**采访者**: 而且你的标准很高，你的标准非常高。

<details>
<summary>Original English</summary>

**采访者**: and and you have a high bar like you have a really high bar

</details>

**David**: 高得令人难以置信。正如我们现在详细讨论的，输出的**美学**确实很重要。如果我要看它，我要审查它，我稍后会给你另一个例子，那里甚至没有发挥作用，但当我在使用代理来处理**Ruby**代码时，我希望它们的代码看起来和我的代码一样好。如果代码很草率，我不会合并它们的代码，就像我不会合并一个尚未完全内化我们风格的初级开发者的工作一样。所以，我希望它能达到同等水平，而早期模型做不到。这并不意味着它们无法生成可工作的软件。至少在某些时候它们可以。这给我留下了深刻印象。我的意思是，我记得我第一次做**贪吃蛇**游戏时，我心想，天哪。我从6岁起就一直想做这个。我想把它做成一个游戏，我能在短短30秒内看到它完成。复制粘贴**HTML**，多么神奇的体验，对吧？

<details>
<summary>Original English</summary>

**David**: incredibly high bar I as we've talked about now at length like the aesthetics of the output really matters if I'm going to look at it and I'm going to review it I'm going to give you another anecdote in a second where those things don't even play in but when I'm using agents to work on Ruby code I want their code to look as good as mine I'm not going to merge their stuff if it's sloppy no more than I would merge the work of a junior developer who has not yet fully internalized our style and so forth. So I wanted to be on par and on parody and the early models just couldn't. That didn't mean they couldn't produce working software. At least some of the time they could. I'm very impressive. I mean I remember when I did my first snake game and I'm like holy smokes. I've been wanting to do this since I was 6 years old. Like I've been wanting to I have this idea. I want to get it into a game and I was able to see that in I don't know a few 30 seconds. It was done with the game. copy paste the HTML magical experience, right?

</details>

**采访者**: 所以，我认为这种转变非常有趣，因为它实际上花了一段时间才找到**代理协调器**、**终端界面**的这种形式。

<details>
<summary>Original English</summary>

**采访者**: So, I think that ramp was very interesting because it actually took a while until we found this form factor of the agent harness of the terminal interface.

</details>

**David**: 对我来说，这是从“这很有趣，我想和它对话”到“我希望它能写我的代码”的巨大突破。我现在开始的任何项目都会**代理优先**，这是一个巨大的转变，它发生在去年**11月27日**，我相信那是**Opus 4.5**发布的时候。现在其他人有不同的观点，他们觉得是**Opus 4.0**，或者也许有人谈论**Sonic 37**。还有其他更早的检查点，但我确实觉得存在一种普遍共识，我可以依靠**Capy**和其他人表达的那种共识，那就是“是的，大约在11月底到12月初。”所有在大型科技公司工作的人，那正是**冬季假期**，因为人们，你知道，整个行业都会关闭两周，除了少数需要**待命**的地方，但同样，整个行业都没有生产工作发生。

<details>
<summary>Original English</summary>

**David**: That to me was the the big unlock from this is interesting. I want to have a conversation with it to I wanted to write my code. I will now start any project I'm starting with. I'm starting agent first and that's a massive shift and it just happened from November 27th I believe is when Opus 45 dropped. Now there are other people who have different points they felt like oh is Opus 40 or

</details>

**采访者**: ...行业也在玩这个。

<details>
<summary>Original English</summary>

**采访者**: industry to play with this.

</details>

**David**: 我的感觉是人们都在玩它，因为你把你的**副项目**交给它，你从来没指望完成，然后他们也被震惊了。

<details>
<summary>Original English</summary>

**David**: My sense was that people were playing with it because you give it your side project you never finish expecting not to finish and then they also got shocked.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah.

</details>

**David**: 你完成了，那真是一个彻底的突破，对吧？就像如果这是一部电影，你会听到刮擦声，你就像，“等等，什么？倒带，发生了什么？”

<details>
<summary>Original English</summary>

**David**: You're done and that was just a complete sort of break, right? Right? Like if this was a movie, you'd hear the scratch sound like you're like, "Wait, what? Revine, what happened?"

</details>

**采访者**: 我觉得那是最普遍的集体震惊，它发生在个人身上，然后人们在一月份回来，每个人，尤其是因为很多决策者，比如**CTO**、**工程师**等，他们不那么亲力亲为，但他们确实亲力亲为，很多人都遇到了这种情况。这很奇怪，他们回来后开始强制执行，或者说，你们需要使用这个，因为我已经看到了未来。我真的使用过它，你们需要看到它。所以，我们有点回到硬件方面，人们试图把新的硬件交到人们手中，说你们需要体验它，因为你们不会相信，对吧？这方面也有些类似，你真的不相信。我们可以谈谈这个，任何没有尝试过或者没有那种**“顿悟时刻”**的人，我想我们无法说服他们。

<details>
<summary>Original English</summary>

**采访者**: I feel it was the most collective shock which happened individually and then people came back in January and everyone especially because a lot of the decision makers who are you know like CTO engineers etc were not as hands-on but they were hands-on and a lot of them it's this weird thing where they came back and they start to mandate or like say all right you guys need to use this because I've seen the future. I've literally used it you need to see it. So, it's we're going back to a little bit of hardware like people were trying to give, you know, like the the new hardware into people's hands saying you need to experience it cuz you're you're not going to believe it, right? There's something with this as well where you you really don't believe it. We can talk about this and whoever's not tried it or not had that aha moment. I don't think we can convince them.

</details>

**David**: 这是另一个言语无效的例子。你需要坐在**Open Code**或你使用的任何**协调器**前，使用一个**前沿模型**，从它开始。我会说从**Opus**开始。它是最好的**前沿模型**。其他模型在其他方面更好，等等。但如果你只是要处理一段代码，并且你想看看当前的**前沿**是什么，如果你，我的意思是，如果你的听众中还有人没做过，我会感到震惊，但如果还有一些人没做过，现在就是时候了。我甚至不想说，我发现**X**上的这种趋势非常令人反感，即除非你已经内化了所有关于**AI**的东西，否则你就落伍了。闭嘴。首先，这显然不是真的。你可以在接下来的三周内学会所有东西。这就是这种项目神奇的另一点，对吧？如果我们在去年春天进行这场对话，每个人都会说**MCP**，**MCP**，**MCP**。但你知道吗？你现在可以直接跳过所有这些，直接进入**CLI**和**技能**。这值得记住，那种“除非你全程关注，否则你就落伍了”的**错失恐惧症**（FOMO）是完全没有道理的。话虽如此，我仍然可以理解有些人起步较早。对我来说，**Shopify**的**Tobi Lütke**是主要人物，他比我早得多地看到了这一点以及随之而来的变化，并不断给我发信息，比如“嘿，看看这个，看看这个”，真的把我拉了进来。我确实认为这很有帮助。被那些更有信心或眼光更长远的人包围是很有帮助的。我的眼光倾向于比较短，只关注眼前的事情，而有些人眼光更长远，有时他们会看到一些不会发生的事情。在这种情况下，**Tobi**两年前就准确地看到了我们未来的方向。而我最终看到了它，因为在去年**12月**，这个方向自然而然地展现在我面前。这很有趣，因为一路走来，我一直说：“是的，当模型足够好时，当它们能做所有这些事情时，它会非常棒。”我以为会是18个月，两年，也许是五年，很难预测这些**拐点**，我认为行业本身甚至没有预测到这个拐点，对吧？整个**硅谷**及其周边地区**旧金山**都致力于实现这一目标，但要准确预测**“曲棍球棒曲线”**何时开始爆发是非常困难的，但它确实发生了，现在我的日常工作已经非常不同了。

<details>
<summary>Original English</summary>

**David**: This is another one of those cases where words just are not effective. You need to sit down in front of Open Code or whatever harness that you use, use one of the frontier models, start with that. Start with Opus. I'd say start with Opus. It's the best frontier model. Other models are better at other things, blah blah. But if you're just going to work on a piece of code and you want to see what the current frontier is and if you I mean I'd be shocked if any of your listeners haven't done it already, but if there should be some left, now is the time. And I don't even want to say in the sense I I found it really offputting this trend on X where unless you've internalized everything there is about AI, like you've been left behind. Shut up. First of all, patently not true. you could literally pick up everything in the next three weeks. This is the other magical thing about this kind of project, right? Like or or progress when if we had been having this conversation in spring of last year, everyone been like MCPs, MCPS, MCPS. And do you know what? You can now manage to just have jumped over that entire things and go straight to CLI and skills. That's just worth having in mind that this FOMO that unless you're up on all of it as it happens play by play, you're left behind is complete and utter nonsense. That being said, I can still appreciate that some people were early. And for me, Toby Lutki at Shopify is the main individual who saw this and saw the changes that were coming from it way earlier than I did and have really helped drag me into this by constantly sending me like, "Hey, you look at this, look at this." And I do think that's actually quite helpful. It's quite helpful to be surrounded by people who have a higher faith or maybe their eyes are a little further up. Like my eyes tend to be relatively close to the road like right in front of me and some people have a gaze that a little higher up and sometimes they see things that don't come to pass. In this case, Toby saw exactly where we were going two years ago. And I finally saw it because the road came to me in December. And it's funny because along the way I kept saying like, "Yep, when the models get good enough, when they can do all this thing, it's going to be amazing." and thinking wow it's going to be I don't know 18 months two years maybe it's five years it's very hard to predict these inflection points and I think the industry itself didn't even predict the inflection point right you have an entire city Silicon Valley and surrounding areas San Fran focused on making this happen but predicting exactly when the hockey stick starts hockeying is very difficult but then it happened and now my daily work is very different

</details>

**采访者**: 那么你现在每天的工作是怎样的？

<details>
<summary>Original English</summary>

**采访者**: so so what is your daily work. Now,

</details>

**David**: 我每天的工作都是**代理优先**。

<details>
<summary>Original English</summary>

**David**: my daily work is agent first on everything.

</details>

### AI与代码质量

**采访者**: 采用**代理优先**的工作方式，正好可以提到我们的季节赞助商**Sonar**。当转向**代理优先**的工作方式时，一个必然会出现的问题是**代码质量**。**Sonar**，**SonarQube**的制造商，坚信**代码质量**和**代码安全**是内在相关的。高质量的代码天生更具弹性，随着代理开始大规模编写代码，**验证层**成为你最重要的**安全参数**。这就是**SonarQube**等高级安全解决方案的价值所在。通过其新的**恶意软件包检测**功能，**高级安全**提供了**实时断路器**，自动阻止代理在进入你的**流水线**之前拉取未经验证或有风险的**第三方库**。其影响也是可衡量的。根据**Sonar**发布的2026年代码开发者状态调查报告，使用**Sonar**验证代码的开发者，因**AI**导致宕机的可能性降低了**44%**。这实际上是在弥合**AI**的速度与生产安全现实之间的差距。**Sonar**还在做些什么来帮助减少宕机、提高安全性并降低与**AI**和**代理编码**相关的风险？请访问sonarsource.com/pragmatic了解更多信息。接下来，让我们回到**David**的**代理优先工作流**。

<details>
<summary>Original English</summary>

**采访者**: Going agent first is a good time to mention our season sponsor, Sonar. When shifting to agent first work, one thing that inherently comes up is the quality of the code. Sonar, the makers of Sonar Cube, is deeply rooted in the core belief that code quality and code security are inherently linked. High quality code is naturally more resilient and as agents start writing code at a massive scale that verification layer becomes your most important security parameter. This is where solutions like Sonar Cube advanced security are valuable. With this new malicious package detection, advanced security provides a real-time circuit breaker automatically stopping agents from pulling in unverified or risky thirdparty libraries before they ever hit your pipeline. The impact is measurable, too. Developers who verify their code with Sonar are 44% less likely to report experiencing outages due to AI as per Sonar state of code developer survey 2026 report. It's really about closing the gap between the speed of AI and the reality of production security. What else is Sonar doing to help reduce outages, improve security, and lower risk associated with AI and agenda coding? Head to sonarsource.com/pragmatic to find out. With this, let's get back to David's agent first workflow.

</details>

**David**: 所以，具体来说，**Claude**代码。我用**Open Code**。你用**Open Code**。

<details>
<summary>Original English</summary>

**David**: So, specifically cloth cloth code. Uh I use open code open code. You use open code.

</details>

**David**: 那是我的主要**协调器**。我也用一点**Cloud Code**。他们不幸地获得了早期领先。**Opus**目前是最好的模型。所以他们开始思考，游戏是单场比赛而不是多轮比赛，然后他们从**Open Code**撤销了他们的订阅。所以如果你想使用你的**Mac**订阅，你必须使用他们的**协调器**，我不太喜欢它。我认为这是一个错误。但先放下这个，我们只是庆祝他们拥有最好的模型，**Opus 4.5**和**4.6**也很好，但**4.5**对我来说是**拐点**。

<details>
<summary>Original English</summary>

**David**: That's my main harness. I also use cloud code a little bit. They unfortunately got that early lead. Opus is currently the best model. So then they started thinking a little bit in that like the game is single match instead of thinking it's multiple rounds and yanked their subscription from open code. So if you want to use your Mac subscription, you kind of have to use their harness, which I don't love it. I think it's a mistake. But leave that be for a second and let's just celebrate the fact that they have the best model and Opus for 45 46 is also nice but 45 to me was the inflection point

</details>

**采访者**: 而且它产生了大量的竞争，因为每个人都想现在追赶并超越他们。

<details>
<summary>Original English</summary>

**采访者**: and it creates a lot of competition because everyone wants to catch up and overtake them now

</details>

**David**: 当然，尤其当你看到**Anthropic**的收入时，我想在年初他们是**90亿美元**，几周后他们达到了**140亿美元**，现在他们达到了**190亿美元**。这简直是你所能想象的最疯狂的火箭式增长，它激发了所有这些资本被部署用于竞争者等等，这非常棒，非常乐于看到。所以，即使我不喜欢他们所做的一切，而且**Cloud Code**也不是我首选的**协调器**，你也要学会在头脑中同时处理两件事。这就是我即使在**Apple**身上也尝试做的事情，我对他们的运营方式、他们作为**看门人**以及我们讨论过的所有其他荒谬之处都深感不满，然后我又戴上我热爱电脑的帽子，想，我喜欢新的**Neo**，我甚至可能会买一个新的**Neo**，看看**500美元**能做什么。对于**Opus**，我毫不犹豫地使用它。事实上，每当我遇到一个真正棘手的问题时，我都会去使用**Opus**。但我也使用其他模型。我将两个模型同时以不同速度运行，这已成为我工作流程的一部分。我使用**T-Max**，并在**Umachi**中内置了一个布局功能，它会在左侧启动我的新**Vim**编辑器，然后右侧启动两个面板。顶部是运行**Kimmy K25**的**Open Code**，底部是运行**Opus**的**Cloud Code**，最底部有一个**终端**条。我几乎所有事情都从其中一个代理开始，我告诉它们我想要什么。然后我跳到**Neoim**。首先我敲击**Space + gg**查看**lazy git diff**。如果更改看起来正确，我就会提交。我们完成了。太棒了。有时它不正确，我会自己修改代码。但这种比例以及比例变化的速度仍然令人震惊。去年11月初，我还是**代码优先**，所有事情都是如此。我打开编辑器，花多长时间就花多长时间，然后在某个时候如果我卡住了或者想听取第二意见，我就会去问我的友好**Clanker**给我第二意见。现在已经不是这样了。现在我从代理开始。现在它会给我草稿。我审查草稿，如果需要，我会进行修改。最近我又进一步改变了。我们正在为**Basecamp**开发一个**CLI**，这样我们就可以为**Basecamp**获得全面的**代理可访问性**。这太惊人了。

<details>
<summary>Original English</summary>

**David**: of course and especially because you see Anthropic's revenues I think start of the year they're at 9 billion few weeks later they're at like whatever 14 now they're at 19 or something it's just the craziest rocket ship you could possibly imagine which is inspiring all this capital to be deployed for competitors and so forth which is wonderful great to see so even if I don't love everything that they do and cloud code is not my preferred harness manage to hold two things in your head at the same time this is what I also try to do even with Apple which I have serious griefs about how they operate and act as the gatekeeper and all the other nonsense we've talked about and then I also keep my I just love computers hat on and go I like the new Neo I might even buy a new Neo and just see what is possible at $500 for Opus I have no qualms s about using Opus. In fact, whenever I feel like uh this is a really hard problem, I go to Opus right now, but I also use other models. And one of the things I've incorporated into my flow is to kind of have two models going at the same time at different speeds. So, I use T-Max and I have this layout thing that's built into Amachi where it'll start my new Vim editor on the left side and then it'll start two panes on the right side. On the top is open code running Kimmy K25 and on the bottom is Opus running in cloud code and then at the very bottom I have a strip of terminal and almost everything I started in one of the agents and I tell them what I want. Then I hop over to Neoim. First I do uh space gg to look at the um lacy git diff on it. Once this is changing if it looks correct I'll just commit. We're we're done. Great. and then sometimes it doesn't. It'll correct and I'll I'll go in and alter the code myself. But the ratio and how quickly the ratio changes is still astounding. I went from early November last year, I'm code first everything. I started the editor, I'll spend whatever long it is and then at some point if I get stuck or if I want a second opinion, I'll go ask my friendly clanker to give me a second opinion. That's just not how it is anymore. Now I start with the agent. Now he'll give me the draft. I'll review the draft and I'll make alterations if need be. And then just recently I flipped it even further. So we're working on a CLI for Base Camp so we can get full agent accessibility for Base Camp. It's astounding.

</details>

### AI代理的自主能力与Unix哲学

**David**: 首先，实际上，让我回溯一下。当我意识到代理有多好、能力有多强时，我立刻试图将目光投向终点，思考我们甚至还需要**MCP**吗？我们甚至还需要**CLI**吗？我们甚至还需要任何东西吗？代理难道不能自己解决所有问题吗？

<details>
<summary>Original English</summary>

**David**: First, actually, let me rewind. As soon as I got pilled on how good the agents were and how capable they were, I immediately tried to raise my gaze up towards the end of the road and think, do we even need MCP? Do we even need CLI? Do we even need anything? Can't the agent just figure it all out?

</details>

**David**: 我安装**OpenClaw**就是在这时候。我把**OpenClaw**安装在一个**虚拟机**上，然后想，我应该在这里做什么？让我们看看我们能把它推到多远，它能自己做些什么。所以我想把这个“爪子”放到**Basecamp**里。我想把这个“爪子”放到**Fizzy**里。我**邀请它**，就像邀请一个人一样。所以我写道：“你能注册**Fizzy**吗？我不会给你任何工具。我不会给你任何**MCP**。我不会给你**CLI**。我只是告诉你它的网址是fizzy.do。去注册吧。”然后你看到它慢慢地进行。然后，“是的，我已经注册了，但它要求提供电子邮件地址”，或者说“我正在尝试注册。它要求提供电子邮件地址。”我想，“哦，对了。你需要一个电子邮件地址。一个代理没有电子邮件地址。”“嘿，去注册**hey.com**吧。”我想，“这个它肯定会失败。”然后它慢慢地进行。“我已经在**Hey.com**注册了。这是密码。把它写在安全的地方。我现在也注册了**Fizzy**。我在收件箱里收到了确认邮件。一切都很好。你希望我做什么？”我心想，“什么？你是说你可以**一站式地通过浏览器注册**这些东西？”现在，也许这不应该令人惊讶。也许**Sonnet 3**或某个早期模型已经能够做到这一点。我不知道。但当你亲身在你的“爪子”上体验时，你通过**Telegram**告诉它做某事，然后它自主地注册产品，这相当令人震惊。对我来说就是如此。然后下一步，我想，“既然它可以注册**Hey**，也可以注册**Fizzy**，那我就邀请它加入**Basecamp**吧。”所以我给它的电子邮件地址发送了一个邀请：“这是**Basecamp**的邀请链接。你能跳进我们**AI实验室**的项目，然后向团队介绍自己吗？”它会说：“嘿，我是**David**的助手。很高兴见到你们。我读了一些对话记录。我看到你们都对这些事情很兴奋。”你又会再次惊讶，“什么？什么？”这很有趣，因为它向我展示了，即使需要一些时间，它确实花了一些时间。这在代理术语中，我不知道，花了七分钟。那感觉就像永恒。但它能够做到。这似乎是最终状态。最终状态是代理不需要我们任何迁就。它们不需要任何入门。它们不会坐着轮椅来。它们会穿上**仿生腿**，在两秒内比你跑得快五倍，我们稍后会讨论速度方面的问题。但接着你也会意识到，好吧，我不能只是坐着无所事意，等着**AGI**发生。让我们为今天而构建。这就是我们一直在为**Basecamp**构建的。我们一直在构建**CLI**。我们也将为**Hey**构建它，我们将为**Fizzy**构建它。我们将为所有东西构建它，甚至可能包括一些旧产品。我喜欢**CLI**的地方，就像我喜欢这些**协调器**的地方一样，是它们验证了从**71年**以来基本的**Unix哲学**。你应该只构建可以相互协作的小工具。

<details>
<summary>Original English</summary>

**David**: This was when I installed OpenClaw. So, I installed OpenClaw on a VM and I thought, what should I do here? Let's see how far we can push it and what it can do by itself. So I thought I want this claw in base camp. I want this claw in Fizzy. Let me just try to invite it as it was a human. So I just wrote it. Can you sign up for Fizzy? I'm not giving you any tools. I'm not giving you any MCP. I'm not giving you CLI. I'm just telling you it's at fizzy.do. Go sign up. And you see it. Chuck along. And then yeah, I've signed up, but it's asking for an email address or I'm trying to sign up. It's asking for an email address. I'm like, oh yeah, right. You need an email address. An agent doesn't have an email address. Hey, go sign up for hey.com. I'm like, it's going to fail this one. And it's Chuck, Chuck, Chuck. Uh, I've signed up for Hey.com. Here's the password. Write it down somewhere safe. I'm now also signed up for Fizzy. I got the confirmation email in my inbox. We're all good. What do you want me to do? I'm like, what? Are you telling me that you could one-shot signing up through a browser to these things? Now, maybe that shouldn't be surprising. Maybe that was already possible with Sonnet 3 or one of the early models. I don't know. But when you experience it yourself on your own damn claw that you're just telling over Telegram to do something and it's signing up for products autonomously, that's pretty startling. It was for me. And then the next step I went like, well, if it can sign up for Hey, and can sign up for Fizzy, let me invite it to Base Camp. So, I send it an invitation to its own email address. Here's the invitation link to Base Camp. Can you just jump into the AI labs lab uh project that we have and introduce yourself to the team? go, "Hey, I'm David's assistant. It's very nice to meet you all. I've read back the transcript a little bit. I see you're all excited about these things." And you just go again, "What? What?" And that was fun because it showed me that even if it was going to take a while, it did take a while. It took a while. This is um agent terms. It took I don't know, seven minutes. That was like, "Oh, it feels like eternity." But it was able to do it. And that seems like the end state. The end state is that agents will not need any of our accommodations. They do not need any on-ramp. They're not coming on a little uh wheelchair. They'll be coming on bionic legs and running five times as fast as you in about 2 seconds, which we'll get to in a second to the speed aspect of it. But then you also realize, okay, well, I can't just sit around fiddling my thumbs until AGI happens. Let's build for today. And that's what we've been building for Basecam. We've been building CLI. We're going to build it for Hey, we're going to build it for Fizzy. We're going to build for everything, even probably some of the legacy products. And what I love about the CLI, as much as I also love it about these harnesses, is that they validated the fundamental Unix philosophy from like whatever 71. You should just build small tools that can interoperate with pipes and you can

</details>

**采访者**: 那是哲学，对吧？

<details>
<summary>Original English</summary>

**采访者**: that's philosophy, right?

</details>

**David**: 这完全是**Unix哲学**。对我来说，看到所有东西都有一个**CLI**，这真是神奇之处。并不是说**Basecamp**现在有了**CLI**就更容易使用。不，不是这样的，而是**GitHub**也有**CLI**，**Sentry**我不知道他们有没有**CLI**，但他们有一个**MCP**，你可以把所有这些东西连接起来，现在你可以告诉一个代理：“嘿，**Sentry**里有一些错误。你能去检查一下吗？然后写一份报告发到**Basecamp**，说明出了什么问题。然后去**GitHub**，提出一个**拉取请求**，完成后再在**Basecamp**上发布一条评论。”现在我们有了一个中央的**Basecamp**，我们在那里跟踪工作进展，同时有一个代理在做工作，查找东西。再强调一次，当我们试图谈论它并转述它时，我想有些人可以看到它。现在**OpenClaw**在**YouTube**上有很多视频，你可以至少像乘客一样体验一下。但请你自己尝试一下，用你自己的产品，你自己的任务，你自己的提示，你就会被深深吸引。你会同时对我们能够用**硅**、**芯片**、**权重**等所有东西制造和实现的东西感到无比兴奋。然后也会对未来走向何方感到有点焦虑。正是在这种张力中，我和其他可能被这种现象吸引的人活在当下，对吧？等一下。如果我们已经走到这一步，18个月后会是什么样子？如果在过去的三个月里，我对计算机可能性的全部理解都被颠覆了，那么接下来的三个月会是什么样子？接下来的九个月会是什么样子？

<details>
<summary>Original English</summary>

**David**: It's the total Unix philosophy. And that is actually the magic to me about seeing everything having a CLI. It's not that Base Camp is easier to use now with a CLI. No, no, is that GitHub also has a CLI and Sentry, I don't know if they have an CLI, but they have an MCP that you can tie all these things together and now you can tell an agent, hey, we have some errors in Sentry. Can you go check them out? Then post a write up to Basecam iterating what's wrong. Then go in GitHub, come up with a pull request, post a comment back to Base Camp when you're done. And now we have a central right base cam where we're following the work as it's going on while we have an agent doing work looking things up. And again, when we try to talk about it and relay it, I guess some people can see it. And now OpenClaw has enough videos on YouTube and so forth so you can get at least a passenger ride. But try it yourself with your own product, with your own tasks and with your own prompts and you will be pilled. You will be simultaneously incredibly excited for what we've been able to make sand do. The silicon, the chips, the weights, the whole thing. And then also a little bit anxious about where it's all going to go. And it's in that tension that I and probably anyone else who's been pilled on this live, right? Wait a minute. If we're already here, what does n 18 months from now look like? Like if at the last 3 months we've upended my entire understanding of what's possible with computers, what's the next 3 months look like? What the next nine months look like?

</details>

**采访者**: 是的。这这这就像我长期以来都有点像你一样，我认为有效的东西才值得相信，我总是对预测持怀疑态度。**摩尔定律**在某个时候失效了。我经历过每个人都说它会永远持续下去，然后它果然失效了，正如我们所有人预料的那样。

<details>
<summary>Original English</summary>

**采访者**: Yeah. This this this is where like I I was a little bit on on your end for a long time and I think I still am where I believe what works and I'm always skeptical of projections. Mo Moore's law broke down at some point. I I live through everyone said it will continue forever and you know and then it broke as we all suspected it would

</details>

**David**: 但后来它找到了另一种方式。我认为这是**摩尔定律**的优点，对吧？它对单个核心失效了。是的。你能把单个核心推到多远？然后我们想，如果我们有最新的芯片，AMD的10个芯片上有256个核心呢？

<details>
<summary>Original English</summary>

**David**: but then it found another way. I think it's the good point about the Moors law, right? It broke for individual cores. Yes. How much can you push that? And then we just went, well, what if you just had what's the latest chip? 256 on the AMD 10 chips, right?

</details>

**采访者**: 即使性能下降，我们也会转向功耗和尺寸等方面。所以，是的，我很难说它会在这里停止，因为我们已经看到它在增长。我们知道他们正在采用这种越来越大的**训练数据集**的方法，而且到目前为止一直有效。还有**“苦涩的教训”**（The Bitter Lesson），我认为那是一篇非常短的论文，非常值得一读。我认为这可能是学术圈之外最受欢迎的论文之一。

<details>
<summary>Original English</summary>

**采访者**: And even when performance broke, we we we went into power consumption and size and all of those things. So, yeah, like but it's it's harder for me to also just to say, oh, it's going to stop here because we've seen it grow. We we know the approaches that they're taking this larger and larger training sets and it's been working so far. And there's also the bitter lesson which I think I I think is a it's it's such a short paper that it's just so worth reading. I think it's one of probably the most popular papers outside of academic circles.

</details>

**David**: 是的。

<details>
<summary>Original English</summary>

**David**: Yes.

</details>

**采访者**: 因为它只是揭示了我们不想相信的这件事情。我们希望相信我们的知识、我们的理解是优越的，你知道，你我懂得编码，或者我投入了15年或者更长时间，这是特别的。有时它表明它并没有那么特别。

<details>
<summary>Original English</summary>

**采访者**: Because it just lays out this thing that we we don't want to believe that. We want to believe that our knowledge our understanding is superior that you know you and me knowing how to code or me putting in these 15 years or however long it's been it's special. Sometimes it shows that it's it's not as special.

</details>

### AI时代下开发者角色的转变

**采访者**: 实际上，有趣的是，就在此刻，这个时间点，有点像**初级开发者**与**高级开发者**之间正在发生有趣的**分化**。我在**37signals**看到最成功、最适用的**代理加速**来自最有经验的人，那些能够验证代理生成的东西是否适合部署给数百万人的人。昨天刚好有关于**亚马逊**一些重大宕机的故事。

<details>
<summary>Original English</summary>

**采访者**: What's interesting actually is like right this second this snapshot in time it a little bit is and this is a funny bifification that's happening junior versus senior developer is that the most successful and applicable agent acceleration that I've seen at 37 signal has been from the most senior people the people who are able to validate whether what the agent produces is suitable to be deployed to millions of people. There was just this story yesterday about some of the major outages at Amazon.

</details>

**David**: 是的。

<details>
<summary>Original English</summary>

**David**: Yeah.

</details>

**采访者**: 而**亚马逊**自己的内部分析基本上指出，我们不能再让初级程序员未经审查就将**代理生成**的代码发布到生产环境。问题在于，首先，我认为这是大多数公司现在普遍认识到的。只要是关键任务的东西，我们都不能完全依赖代理来辅助，而且初级程序员也无法弄清楚。因此，他们的角色突然比六个月前更加岌岌可危，因为高级程序员可以做到，这就是为什么高级程序员获得了如此多的加速。他们首先能够与大量代理并行工作，但更重要的是，他们能够批判性地检查代理输出的质量，并高度确信它是否会奏效，如果不能，就重新引导它们，因为这正是他们成为高级程序员的原因。这就是他们扮演的角色，他们拥有长远的洞察力、历史经验和对架构的整体把握。这会奏效吗？这不会奏效吗？他们对初级程序员扮演的就是这个角色。但现在他们可以对代理扮演这个角色，而代理在遵循指令和重新引导方面更快。突然间，高级开发者可以将个人生产力提高**5到10倍**。现在，这是**二阶效应**。如果你能将一个高级开发者的生产力提高**5到10倍**，那么这个人每小时的价值就提高了**10倍**。现在，这个人不是把时间花在与代理一起处理事情和改进产品上，而是像以前一样，把时间花在教一个初级人类如何把事情做得更好上。这个等式中存在一些正在发生的事情，目前尚不清楚它将如何演变。

<details>
<summary>Original English</summary>

**采访者**: And Amazon's own internal analysis essentially pinned that we can no longer let junior programmers ship agent generated code to production without review. And the problem with that is first of all I think that's the realization most companies are now having across the industry. Whenever it's mission critical for something of that nature, we cannot yet rely on the agents to abet it at all and a and junior programmers are not capable of figuring it out. Therefore, their role is suddenly more tenuous than it was 6 n months ago because a senior programmer can and this is why senior programmers are getting so much more acceleration. They're able to first of all work in parallel with lots of agents but critically examine the quality of the agent output and have a high degree of confidence of whether this is going to work or not and redirect them if not because this is what made them senior in the first place. This was the role that they had that they had the uh long insight and history and overview of the architecture. How does it all fit in? Is this going to work? Is this not going to work? This was the role they played to junior programmers. But now they can play that role to agents and agents are faster at following instructions and redirections. And suddenly you have senior developers who can 5x 10x their individual productivity. And now this is the second order effect. If you manage to 5x or 10x a senior developer, that person's value per hour just went up 10x. Now take that hour instead of that person spending it with the agents just shipping stuff and making things better. They spend that hour as they would before teaching a junior human how to do things better. There's something in that equation that's in play right now and it's not clear how it's going to map out.

</details>

**采访者**: 现在它有一种可能的发展方式是，代理会变得非常出色，以至于它们不再犯错。它们在交付可工作代码的能力上变得成熟。如果展望未来，这可能就是我的预测，因为这正是**汽车**行业刚刚发生的事情。所以**特斯拉**的**自动驾驶**现在开得比人类还好。不是所有人类，不是所有情况，但平均而言是如此。我们能够将致命风险，我们在日常生活中处理的最高风险，即坐在一个金属管里，旁边还有其他以每小时60英里速度行驶的金属管，如果有人犯错，你就会死，我们把这个任务委托给一个代理。那么它们也可能能够弄清楚如何让代码工作，对吧？所以，我确实认为它会到来，但谁知道何时，谁知道如何。现在，我们正处于一个阶段，大部分好处都流向了最有经验的开发者。而且我也在想，就像**自动驾驶**一样，你会意识到总是有**KV**。例如，在那些有影响力的公司内部。当你是一家**初创公司**时，你没有客户。这无关紧要。你可以一次性解决它，即使它不工作，它崩溃了，也无关紧要。但在这些公司内部，**Uber**，我刚刚了解到他们是如何采用**AI**的，他们拥有所有这些工具，**Cloud Code**等等。但我们也意识到，当你把这些东西放进去时，他们有所有的内部**单体仓库**。他们有他们的票务系统。他们有他们的**Slack**。他们有很多东西。他们有他们的**RFC**、**设计文档**，关于他们为什么拥有这种混乱的**微服务**。多年前我们就是这样连接的，这很有趣。但他们发现，他们构建了许多内部系统，其中大部分是为了帮助**NCD**的**代理协调器**，现在它们运作得更好了。但你知道我们现在所处的这个阶段是，这就是为什么如果你是这些公司的高级工程师，或者像**Uber**这样的公司的**员工工程师**，当你跳槽到**Google**时，你突然就不会像以前那样有价值和高效，直到你学习所有系统。所以我在想，就像**自动驾驶**一样，你知道，**自动驾驶**运作得很好。我在**SFN**和**LA**，他们开车开得很好。

<details>
<summary>Original English</summary>

**采访者**: Now one way it could map out is that the agents will get so good that they stop making mistakes. They become senior in their capacity to ship working code. This is what my bet would be if we look x amount of time forward because this is what just happened with cars. So self-driving Teslas now drive better than humans do. Not all humans, not in all circumstances, but on average. It's very possible that if we're able to delegate the mortal risk, the highest criticality we basically deal with on a daily basis sitting in a metal tube along other metal tubes that go 60 m hour where you can die if someone makes a mistake, we delegate that to an agent. Well, they can probably figure out how to make the code work too, right? So, I do think it's coming, but who knows when, who knows how. Right now, we're at a stage where the bulk of the benefits are acrewing to the most senior developers. And also I wonder just like with self-driving like you realize there's always KV. So, for example, inside companies where it matters. When you're a startup, you have zero customers. It doesn't matter. You can oneshot it and it doesn't matter if it doesn't work and it, you know, it crashes. But inside these companies, uh, at Uber, um, I just got details on how they're adopting AI and and they have all these tools, cloud code and and all these things. But what we realize as well when you just put it in there, they have all these internal monor repos. They have their ticketing systems. They have their slack. They have so much. They have their RFC's design documents on on how and why they have this jumble of a mess uh with microservices which which was fun way that we we originally connected like many many years ago. But what they found is they built a bunch of internal systems, a lot of it to help to feed NCD's agent harnesses and now they're working better. But you know this where we are right now is is there's and this is why if you're a senior engineer in one of these companies or a staff engineer at like Uber and you move to Google suddenly you're not going to be as valuable as efficient for a while until you learn all the systems. So I I wonder if just like with self-driving, you know, self-driving works great as well. I was in SFN and LA and way most they they drive so nice. Like

</details>

**David**: 我的**特斯拉**一直在**洛杉矶**载着我们全家去机场。我每次都安安静静地坐着，看着路，但整个旅程中都没有操控方向盘。除了我的**Waymo**曾经卡住，因为一辆卡车停在一条狭窄的街道上，一辆车旁边有一个自行车棚，我知道我不应该去那里，但它不知道。所以，人类驾驶员介入了。但无论如何，即使是**Waymo**，你知道，它们有一些限制，它们在天气好的时候开车开得很好。它们已经被映射出来了。所以我在想，在**软件工程**中，我不知道这是否也有这些相似之处，我们所有的公司都有他们自己专业的**环境**，一旦你映射它，一旦你使用所有工具，一旦你弄清楚这些事情，就像**自动驾驶**花了十年时间一样，对吧？我在**Uber**工作时，他们收购了**自动驾驶**部门，我们当时在新闻中听到，明年司机将完全失业，而且...

<details>
<summary>Original English</summary>

**David**: my Teslas was driving in LA driving us to the airport every time. The whole family I sit peacefully watch the road but do not steer at all on that entire journey. Well, except my my weimo got stuck because a a truck was parking on on a narrow street and a car had a bike shed and I I I I knew that it should I should not go there, but it didn't know. So, human oper operator came in. But anyway, but even with Whimos, you know, like there's there's things like there's they drive in pretty good weather. They've been mapped out. So I wonder if in software engineering I I wonder if this has these parallels where we have all of you know like these companies have their their specialized landscape and once you map it once you do all the tools once you figure out these things and with self-driving it took it took 10 years right like I was at Uber when they bought the self-driving thing and we were hearing in the news that you know next year it's all going to be over for drivers and no

</details>

**采访者**: 是的，方向盘将不复存在。

<details>
<summary>Original English</summary>

**采访者**: yes there are not going to be steering wheels anymore which by the way is an amazing anecdote because it just shows Elon 's total faith in his mission

</details>

**David**: 顺便说一句，这是一个惊人的轶事，因为它展示了**埃隆**对他的使命的完全信任。因为在2017年他做出这个声明时，它是一个**AI**。它是50万行**手写C++代码**。

<details>
<summary>Original English</summary>

**David**: which by the way is an amazing anecdote because it just shows Elon 's total faith in his mission because in 17 when he made that proclamation, it was an AI. It was 500,000 lines of handcoded C++,

</details>

**采访者**: 对吗？

<details>
<summary>Original English</summary>

**采访者**: right?

</details>

**David**: 那个模型永远不会让我们实现完全**自动驾驶**。但他对这个愿景充满了信心。最终，**AI**出现了，它非常出色。如果你用数十亿小时的道路使用数据训练它，它确实可以做到。而且它比大多数人类做得更好。事实上，我是一个相当不错的司机。我想说我不是最好的司机，因为我不知道，我的不耐烦往往会促使我踩油门。这对乘客来说并不总是那么愉快，但对我来说很有趣。当我让**特斯拉自动驾驶**时，它就是世界上最好的司机。它简直完美。

<details>
<summary>Original English</summary>

**David**: Like that model was never ever going to get us to the full self-driving. But he had just total faith in the vision. And then eventually, hey, here come along comes AI and it's so good. And if you train it on billions of hours of road use, it actually can do it. And it can do it better than most humans. In fact, I'm a pretty good driver. I'd like to say I'm not the best chauffeur because my I don't know impatience have a tendency to provoke the throttle. Uh that's not always as pleasant for passengers as it is fun for me. And when I let uh the Tesla autopilot drive, it's just the best chauffeur in the world. It's just perfectly

</details>

**采访者**: 比你强。

<details>
<summary>Original English</summary>

**采访者**: better than you.

</details>

**David**: 比我强，比女王的司机强，我想。它的油门控制和减速简直是神一般的。它实际上是**AGI**般的，或者说在这种狭窄领域中的应用是**AGI**般的。当然，当我们得到这些轶事和例子时，天哪，**自动驾驶**并没有花十年。从声明发布到今天花了十年，但那七年他们所做的事情与他们现在用**FSD**所做的毫无关系，因为基于**AI**的**FSD**运行时间并没有那么长。但我认为拐点是**FSD 1.31**，**FSD 1.31**，就像第一个版本，你会想，“哇，这很不错，但我要注意了。”**1.32**、**1.40**、**1.42**，在18个月的时间里，我们从“是的，这很不错，但我要注意了”变成了“为什么还会有方向盘？”这种加速，在如此短的时间内，当然是人们在编程时会关注的东西，他们会想，如果我们现在在这里，高级程序员仍然需要审查它，否则你就会在**AWS**上遇到所有**四级严重性八小时宕机**，因为一些**AI**推送了一些无意义的代码。当他们像**FSD**在同一时间段内实现那种飞跃时，会是怎样的景象？现在，我也认为你可能会完全疯狂地试图坐下来吸收所有这些。这就是我过去一年一直在做的事情。我想，我对未来发展感到非常兴奋，但我也将处理今天可能做到的、今天令人愉快的事情以及我们现在正在做的事情。我不会试图规划12个月后我的生活会是怎样，那时也许我们有**AGI**，也许没有。现在，还有其他人做得非常好。我刚刚看了**Leopold on Drakesh**去年的一次采访。他在思考2030年会是什么样子？10兆瓦数据中心会是什么样子？我想，我很高兴有人对此进行了思考，因为那不是我最喜欢的地方，而且我认为大多数人都不擅长预测未来。

<details>
<summary>Original English</summary>

**David**: Better than me, better than the queen's chauffeur, I think. like it's throttle actuation and deceleration is godlike. It's actually agi like or as like in its application within that narrow domain. And of course, when we get these anecdotes and these examples of holy smokes, not it didn't take 10 years for the self. It took 10 years from the proclamation, but what they were doing for seven of those years had nothing to do with what they're doing with FSD now because the FSD that's based on AI hadn't been running for that long. But the inflection point of I think it was 131, FSD 131, like the first version, you're like, "Wow, this is pretty good, but like I better pay attention." 132 140 142 over the course of 18 months we went from yeah it's pretty good but like I'm going to pay attention here to why is there steering wheel and that acceleration that short period of time of course is something people look to when it comes to programming go like well if we're here now and senior programmers still have to review it because otherwise you're going to get all your whatever four severity eight down times at AWS because some AI pushed out some nonsense. What is it going to look like when they take the jump that FSD did over the same period of time? Now, I also think you can go completely crazy trying to just sit and soak in all of that. This is what I tried to do over the past year. Go, I'm really excited for where this is going, but I'm also going to deal with what's possible today and what's enjoyable today and what we do right now. I'm not going to try to plan what my life looks like 12 months from now when maybe we do have AGI or we don't. Now, there are other people who do that very well. I just watched an interview with Leopold on Drakesh from last year. He's thinking like what does 2030 look like? What does the whatever 10 gawatt data center look like? I'm like I I'm very glad we have individuals who put thought into that because that's not my favorite spot to be and I think most people are not that good at polishing the crystal ball.

</details>

**采访者**: 不。嗯，我的意思是，这对于**软件工程师**来说有点不安，因为很明显，这是行业希望发展的方向。很多精力都会投入到这方面。将会有很多基于此构建的企业和软件业务。通过这种方式，大量**风险投资**将涌入，他们将解决这个问题，他们要么成功要么失败。这些公司就是这样做的。但今天，你在**37signals**看到了什么？对于**软件工程师**来说？你当然拥有大多数经验丰富的工程师，尽管你也雇佣了初级工程师。他们的工作方式正在如何改变？他们对工作的满意度正在如何改变？因为那也是一个问题，对吧？我们一直在争论这是否让我们更痛苦？这是否是我们想做的事情？它又是如何为你改变的？

<details>
<summary>Original English</summary>

**采访者**: No. Well, I I mean this is a little bit unsettling as a software engineer in the sense of like clearly this is where the industry wants to go. This is where a lot of effort will be put. There will be a lot of businesses, software businesses built on this. A lot of VC money raised on this by the way who are going to tackle this and they will either like succeed or die. That's what that's what these companies do. But today, what do you see at at 37 signals uh with software engineers? You you of course have mostly experienced engineers, although you did hire junior engineers as well. How is their kind of work changing? How is their satisfaction with with work change? Because that's also a thing, right? We keep arguing about like is is it making us more miserable at these things? Is it what we want to do? And how's it changing for you? Right. I think it's

</details>

**David**: 这是最大的启示，甚至超过了代理的能力，就是我运行它们的乐趣。去年夏天我接受那次采访时，我谈到了我不想成为代理的**项目经理**，因为我当时对**人类项目经理**有一个心智模型，我想那不是我喜欢做的事情。我不想离生产那么远。我想参与其中。我想亲手接触代码。我当时没有意识到的是，运行一群代理，感觉不像是在做代理的**项目经理**，而更像穿上了一套**超级机甲服**，突然之间我不再只有两只手臂。我有12只手臂，现在我可以同时看七个屏幕，操作五个键盘。即使我没有以编程的关键字输入，我仍然是那个在做这件事的人。作为一名程序员，我得到了**超加速**。这是一种不同类型的程序员，但它仍然对**美学**有着同样的亲和力，至少在我生成**Ruby代码**时是这样。我能够将这一点与在许多事情上大幅提高生产力结合起来。这也像是在评估问题方面获得了令人难以置信的**大脑升级**。我有一个令人震惊的时刻，是在**Umachi 3.4**发布之前。

<details>
<summary>Original English</summary>

**David**: that's the biggest revelation actually more than even the capacity of the agents is my enjoyment running them. When I was on that leg interview last summer, I was talking about you know what I don't want to be a project manager for agents because I had the mental model of a project manager of humans and I thought like that's not what I enjoy. I don't want to be that far away from the production. I want to be in the mix. I want to have my hands in the code. What I failed to realize at the time was that running a bunch of agents feels less like being a project manager for agents and more like stepping into this super mech suit where suddenly I don't just have two arms. I have 12 and I can now look at seven screens at the same time running five keyboards. I'm still the one doing it even if I'm not typing this as a keyword in a program. I have been hyper accelerated as a programmer. It's a different kind of programmer, but it still has the same affinity to aesthetics, at least when I'm producing Ruby code. And I'm able to combine that while being vastly more productive on a bunch of things. It's also like getting an incredible brain upgrade on even assessing issues. One of the pilling moments I had was before the release of Omachi 3.4.

</details>

**David**: 我进入了**GitHub**，我们有，我不知道，250个**待处理PR**。我有点叹了口气，心想，250个**PR**，如果我每个**PR**花15分钟，那要多久才能处理完？然后我想，你知道吗，让我尝试一些别的东西。我只是尝试让**Claude**来处理。我甚至没有使用系统做任何事情，我只是做**Review URL**，然后**URL**是问题，或者是**PR**。结果震惊了。

<details>
<summary>Original English</summary>

**David**: I went into GitHub and we had I don't know 250 PRs pending and I kind of just sighed a little bit and like 250 PRs if I spend I don't know 15 minutes on each PR like how long is it going to take before I get to the end of it and I thought you know what let me try something else let me just try to ask Claude to I'm not even doing anything with a system I just do review URL and the URL is the issue or is the PR are shocked In

</details>

**David**: 大约**90分钟**内，我想，我处理了**100个PR**。并不是说我合并了所有这些。事实上，我只会说我合并了少数。也许**10%**原样合并了。然后也许**20%**合并了。但有了**Claude**的实现...

<details>
<summary>Original English</summary>

**David**: 90 minutes, I think it was, I processed 100 PRs. And it wasn't that I merged all of them. In fact, I'd say I merged a small minority. Maybe 10% got merged as is. Then maybe 20% got merged. But with Claude's implementation,

</details>

**采访者**: ...程序员正确地识别出了一个问题。

<details>
<summary>Original English</summary>

**采访者**: the programmer had correctly identified an issue

</details>

**David**: ...但我**手写**了一些代码，我能看到我不想保留这些代码，有时我甚至看不到。我只是问**Claude**，他们会说，啊，这不太对。然后我只是问**Claude**，你能**重新编写**一下吗？

<details>
<summary>Original English</summary>

**David**: but hand rolled some code that I could see I didn't want to keep or sometimes I couldn't even see it. I just asked Claude and they say like ah it's not quite right. And then I just asked Claude, can you just clean room this?

</details>

**采访者**: 这正是正确的问题。让我们解决它，但要以正确的方式解决。它会立即以我编写**Umachi**其他部分时完全相同的风格来完成。现在这并不是什么高级代码。它主要就是**Bash代码**，但**Bash代码**也有其形态，以及你希望它看起来怎样，以及它能否与项目的其余部分保持**一致性**。在这种情况下，**Agent Opus**就能完美地做到这一点。然后，它的后半部分，有**25%**是我意识到我根本不想要这个，我们不应该有它。另外**25%**是**Claude**告诉我，也许这里有一些东西，但这并不是一个好的实现。我们无法直接制作出一个伟大的产品。**90分钟**内处理了**100个问题**。我坐下来想。这本来是一周的工作量，至少要几天。天哪？更重要的是，**Claude**对至少一半问题的分析，涉及我一无所知的事情，这无疑是...

<details>
<summary>Original English</summary>

**采访者**: This is the right problem. Let's fix it but let's do it right. It would do it right away in exactly the style as I would have written the rest of Amachi. Now this isn't the high code of something. It's mostly just bash code, but there's still a shape to bash code and how you want it to look and can it feel coherent with the rest of project. Agents opus in this case would just nail it. And then the second half of it was split between 25% thinks I then just realized I just don't want this. It shouldn't we shouldn't have it. And 25% claude telling me maybe there's something here, but it's really not a good implementation. We don't have a straight shot to making a great one. 100 issues in 90 minutes. And I sat back. This would have been a week's worth of work, days at the very least. What the heck? And even more than that, Claude's analysis of at least half the issues pertained to things I knew nothing about where it was undeniably

</details>

**David**: ...一个更聪明、更好的审阅者、程序员，我做梦也想不到能达到这种水平。

<details>
<summary>Original English</summary>

**David**: a smarter, better reviewer, programmer that I could ever dream to be. Well, not dreamed to be, but wasn't that

</details>

**采访者**: 当时没有那种感觉？不，但你不会投入那种精力。这就是为什么**PR**一开始就搁置在那里。在很多情况下，我看了看，然后就放弃了。

<details>
<summary>Original English</summary>

**采访者**: moment? No, but you would have not put in the effort. This was why the PR sat in the first place. In many cases, I would look at it and go that

</details>

**David**: 我觉得这里有些东西，但现在我必须阅读关于这个**调试**的东西。我必须弄清楚这是否是正确的方法。我不想合并一些然后又出现其他问题的东西。能够通过**代理加速**做到这一点，是我编程生涯中最重要的20个时刻之一。我喜欢你使用“**代理加速**”这个词，它听起来特别高效，适用于那些你不想做或者不擅长做，但又很难委托给别人的工作。你有一个团队，对吧？就像你一样，但你可能没有委托出去，因为你可能知道那样做不会更快或更好。所以我在想，**AI**是否有一部分，因为我们经常谈论公司，尤其是大公司，喜欢衡量效率、**PR**，他们希望看到影响，但我们讨论的是做我们以前不会做的工作所产生的影响。

<details>
<summary>Original English</summary>

**David**: I think there's something here, but like then I now have to read up on this debug thing. I have to figure out is this the right way of doing it. I don't want to just merge something that then has other issues. And to be able to do that agent accelerated was one of top 20 programming moments. I I like how you put agent accelerated and it sounds like it's especially efficient for work that is waiting on you but you don't want to do it or you're not as skilled of doing it but it's a hassle to delegate because again like you have a team right like like like you but you probably didn't delegate it because you probably knew that it wouldn't make it faster or better. So I I I wonder if there's a part of AI that because we talk a lot about like you know like companies love to measure especially larger ones like efficiency PRs and they want to see impact but about the impact of doing work that we would have not done before.

</details>

### AI与拓展开发边界

**David**: 这对我来说是关键。现在这个**蛋糕**正在**爆炸式增长**。它不是在增长，而是在爆炸。我们内部处理的项目数量众多，这些项目我们以前甚至从未想过要启动。我们有一个很棒的项目，通常在性能工作上，你会担心**P50**、**P95**、**P99**。**Jeremy**，我们最受**代理加速**的人之一，问道：那**P1**呢？那最低性能呢？我们能修复最低性能吗？最低性能是什么？他接着说，现在我们的最低性能是，我忘了是多少了，说是4毫秒，对吧？嗯，实际上，如果你有很多快速请求，4毫秒可能会累积起来，它仍然很重要。他接着说：“我们要优化**P1**。我们正在优化**P1**。字面意思是，最快的**1%**的请求，我们要让它们更快。”他把性能从，我想是4毫秒降低到不到半毫秒。他将性能提高了**10倍**。这让我觉得，我以前绝不会参与这样的项目。他在几天内完成了**P1项目**，作为一个副项目，因为现在他能做到了。

<details>
<summary>Original English</summary>

**David**: That's the kicker for me. That's the fact that the pie is just exploding right now. It's not growing. It's exploding. The number of projects we have tackled internally that we would never even have contemplated starting on are legion. We had a great project where normally on performance work you worry about uh P50, P95, P99. Jeremy, one of our most agent accelerated people went like what about P1? What about the floor? Can we fix the floor? What is the floor? And he went like well right now our floor is I forget what it was 4 milliseconds. Let's say that, right? Well, actually 4 milliseconds can add up if you have a bunch of fast requests. They can still it still matters. and he just went like, "We're gonna do P1. We're gonna optimize P1 literally the fastest 1% of requests. We're going to make them even faster." He took it from, I think it was four milliseconds to less than half a milliseconds. He 10x the performance that I was like, I would never have signed up on this and he did the P1 project over a couple of days as like a side gef because now he could.

</details>

**采访者**: 现在他能够做到，因为他有一个预感。他有一种直觉，觉得这里有些东西。他让代理去运行，然后大量的**PR**就来了，我们修复了这个，我们修复了这个。我想，总的来说，**P1项目**，我可能记错了，但我想大约有**12个PR**，只是修复了各种问题。当我看到单个**PR**时，我心想，是的，确实，有道理。当我看到总数时，你已经修改了2500行代码，你几天内就完成了。

<details>
<summary>Original English</summary>
**采访者**: Now he could because he had a hunch. He had an intuition that there was something here. He let agents run with it and the number of PRs that like all right we fixed this we fixed this I think total the PR the P1 project I maybe misremember but I think it was like 12 PRs like just fixing all sorts of things where I look at the single PRs I'm like yeah actually okay yeah makes sense I look at the total sum of it you've changed 2500 lines of code you're like you've done that in a few days
</details>

**采访者**: 这真是，我从未听过有人做**P1优化**，因为它感觉像是一个虚荣的体验，完全没有商业意义。这不是真的，对吧？因为所有东西都会累积起来。但你知道我的意思，对吧？

<details>
<summary>Original English</summary>

**采访者**: it's so I've never heard anyone do P1 because it just it feels like a vanity experience it makes no business sense I I This is not true, right? Cuz everything adds up. But but you know what I mean, right?

</details>

**David**: 我完全理解你的意思。这正是为什么这种**爆炸式增长**突然让我们能够解决以前从未想过要解决的问题。这很有趣。我记得**《终结者2》**中的一个场景，他们从第一部电影中找到了**终结者**的芯片，他说：“这东西给了我们以前从未调查过的想法。”这里有一些美丽的相似之处，我们可能即将建造**终结者**，这是老生常谈了，但同时我们也获得了以前从未想过的想法和抱负，因为探索一个预感的成本突然降低了**一千倍**。我现在也经常这样做。我只会给它一些模糊的、糟糕的指令，只是因为我有一个模糊的想法。我甚至没有把它具体化成一个清晰的**提示**。我只是想看看一些东西。它会完成。然后我说，“哦，是的，删除”——也就是将代码恢复正常。以前，我对75行代码会更加珍视，因为它可能需要我花两个小时来完成。现在这些东西都没有任何**残留价值**了，我可以直接说，“给我一个草稿。”我感觉有点像一个国王，你只需说：“给我看看**Farrung**地区的分析。我们的**税收收据**情况如何？”然后这个男孩，这个仆人，就会说：“是的，我将去做，三周后回来。”除了，你可以随意挥舞你的手。然后代理就会带着对愚蠢问题的答案，糟糕的想法回来。然后突然间，它不再那么糟糕了。它实际上是一个很棒的想法。你就会说：“什么？”我做过这个，我甚至还没有真正启动它。但是**Umachi**用户从一开始就一直在要求的功能之一是**双启动**。能够在**Windows安装**旁边安装**Linux**，这样他们仍然可以玩所有游戏。我当时就想，你知道吗？我有多台电脑，所以当我玩游戏时，我可以在**PC**上玩。这不是我的问题。

<details>
<summary>Original English</summary>

**David**: I know exactly what you mean. And this is exactly why the explosion of the pie suddenly lets us look at problems we would never have contemplated looking before. It's funny. I remember this scene from Terminator 2 where they found this chip from the Terminator in the first movie and he goes like, "This thing gave us ideas we would never have investigated before." And like there's some beautiful parallels here about like maybe we're about to build the Terminator, the cliche, but also we're getting ideas, we're getting ambitions we would never have looked at before because suddenly the cost of exploring a hunch has just dropped by a thousandfold. I do this all the time now, too. I'll give it some vague crappy instructions just because like I have this fleety idea. I haven't even crystallized it into a neat prompt. I just want to see something. It'll And then I go like, oh yeah, delete as in revert code back to normal. I like before I would be a little more precious about 75 lines of code because it would have taken me two hours to do him. Now there's no residual value to any of this stuff and I can just go like show me a draft. I feel like a little bit like a king where you just go like show me the the analysis of the farrung regions. Where are we with the tax recip? And this boy is like, "All right, this uh servant is like, "Yes, I I shall do so and return in 3 weeks." Except like you can just wave your hands around. And agents just come back with answers to stupid questions, terrible ideas. Then suddenly it wasn't so terrible. It was actually a great idea. And you go like, "Wha, I did this with I haven't even pulled the trigger on it yet." But one of the things with the Machi people have been asking for since the beginning is dual boot. being able to install Linux next to the Windows installation so that they can still play all their games. And I just went like, do you know what? I have more than one computer so when I play play games, I can just do it on the PC. It's not a me problem.

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah,

</details>

**David**: 我完全理解为什么很多人想要。我不太倾向于花四个小时去弄清楚。前不久我只是想，哦，这正是那种问题，我不需要弄清楚。让代理去弄清楚就行了。所以我最初启动了只制定一个计划的过程。这是一个相当大的改变，对吧？如果你搞砸了某个人的**启动记录**，或者你覆盖了他们的**分区**，这风险很高，这也是我不愿参与的原因之一。其次，如果你想在**Linux分区**上进行**Lux加密**，但**Linux分区**不拥有整个驱动器，这有点棘手。我不想承担这种高风险。我想，这非常适合代理来处理。所以它基本上是让**Opus**和**Codeex**来回讨论一个计划。我先问**Opus**，制定一个计划。它思考了几分钟，然后提出了一个好计划。然后我把它扔给**Codeex**，让它**批判**这个计划。然后我让他们来回讨论了几次，最后看着这个计划，心想，是的，这是一个好计划，我们完全应该这样做。我迫不及待地想启动它，然后就说，是的，现在可以**双启动**了，不是因为我做到了，而是因为你的那些有用的**Clanker**。那种雄心壮志我还没有完全内化。我只是觉得，嘿，这里有一些想法或需求，我想做一些项目，也许有一天，你可以在吃午饭的时候把一个想法启动。这是一个新世界。这也是我认为很多人在想的原因之一，模型在不断改进，但即使我们明天碰壁了，**“苦涩的教训”**也不再是真的了。实际上有一个限制。它是**19万亿个令牌**。这就是他们能学到的东西。根本不是真的。但如果真是这样，我们不得不使用这些模型，我们会在接下来的十年里，只是从它们身上获得越来越多的东西，学习如何使用这些工具。你实际上在**老式电脑**上也能看到这一点。所以**Commodore 64**在81年到85年发布时，他们能够制作的游戏，我知道他们制作的时间更长，但后来**Amiga**和其他机器出现了。当时有很多很棒的游戏。我的意思是，我对**Commodore 64**上的游戏很感兴趣，像**Yung Fu**等等。20年后，当有人完全摸透了所有秘密，并调整了那个**1兆赫兹的处理器**时，他们能够做到的事情...

<details>
<summary>Original English</summary>

**David**: I totally get why a bunch of people wanted. I'm not heavily inclined to spend four hours figuring it out. And I just uh a little while ago went like, oh, this is exactly the kind of problem like I don't have to figure it out. Just made the agents figure it out. So I kicked off initially the process of just coming up with a plan. This is a pretty good big change, right? Like if you [ __ ] up someone's boot records or you overwrite their petition criticality high, which was one of the reasons I didn't want to engage with it. Secondly, it's a little finicky if you want uh Lux encryption on the Linux partition, but the Linux partition doesn't own the whole drive. It's a little hairy. I didn't want to take on the criticality. I'm like, this is perfect for the kind of agent stuff. So it started off basically just having Opus and Codeex pingpong a plan. Like I'll just I asked Opus first like come up with a plan for this it thinks for minutes and minutes and come up with a good plan and then I kick it over to Codeex and like critique the plan and then I had him ping pong back and forth a couple times and at the end looking at the plan going like yep that's a good plan we should totally do that and I can't wait to kick that one off and just go yeah now does dual boot not because I did it but uh thank your uh your helpful clinkers. That level of ambition is still something I've yet to internalize. Like even just that that like, hey, here are these hunches or demands, projects that I would like to do and maybe someday and you could kick it up on a hunch while you go to lunch. That is a new world. Which is also one of the reasons I think a lot of people are thinking, well, the model continues to improve, but even if we somehow hit a wall tomorrow, the bitter lesson is no longer true. There's actually a limit. It's 19 trillion tokens. That's how much they can learn. Not true at all. But if it was and we had to be stuck with these models, we would spend the next decade just getting more and more out of them learning how to use these tools. You see this actually with vintage computers. So the kind of games they were able to make on the Commodore 64 when that was released back in 81 to 85 I think was the main run. I know they made it a little longer, but then the AmIgga and other machines came out. Were great games. I mean, I got interested in games of the Commodore 64, Yung Fu, and all that stuff. The stuff they were able to do 20 years later when someone had just noodled all the secrets and tweaked the one MHz processor

</details>

**采访者**: ...当他们为老旧的电脑制作游戏时...

<details>
<summary>Original English</summary>

**采访者**: when they're building games for the old old

</details>

**David**: 是的。

<details>
<summary>Original English</summary>

**David**: Yeah.

</details>

**David**: ...在技术上更加令人印象深刻，因为我们对**PS1**有了更多的了解。我的意思是，同样的事情，你看**PlayStation**，第一批游戏刚发布时，最后的游戏在**PlayStation 2**发布之前，它们看起来就像不同世代的产品。我们完全可以继续用这些模型这样做，但我们不会有那种特别的乐趣，因为三个月后又会有一个新模型发布。但这很有趣，因为如果我们只是沿着这个思路走，当然我们知道会有新的东西出现，但关键是我们将花费大量时间学习，应用它们，构建我们的内部系统，改变我们构建东西的方式，承担新的项目，就像如果你是一个现有的团队，现在人们可以做更多的工作，更具雄心的工作。你如何看待团队承担更多工作，发布更多产品？你是否考虑扩大团队，还是保持现状？我对我团队设置的最佳评估是，同样的人可以做更多的事情。

<details>
<summary>Original English</summary>

**David**: are so much more technically impressive because we just know so much more about the I mean, same thing with the you look at the PlayStation first games come out on launch, last games before we go to PlayStation 2, they look from they're like from different generations. We could totally continue to do that with the models, but we're not going to have that particular enjoyment because there's a new model dropping in 3 months. But this is interesting because if we just run with this thought like of course we know new new things are going to come but the point is like we will be spending so much time learning applying them building either our internal systems changing how we build things taking on new project like if you're an existing team now that people can do more work and more ambitious work. How are you thinking of of the team taking on more work launching more products? Are you thinking of of potentially growing the team or keeping it as is? My best assessment for our setup is that the same people can do much more.

</details>

**采访者**: 让我们内化这一点。但这也足够了。我们已经做得足够好了。我们已经有足够的利润，如果有足够好的想法，我们可以雇佣更多的人。所以我们从团队中获得的这些额外生产力，现在允许我们做像**P1**这样的项目，以及其他很棒的项目，它们也将更快地改进产品。当然会。旧的思维方式，比如交付一个主要功能需要两个月。我的意思是，那已经过时了。当然会有快速加速，它将渗透到我们的**软件方法论过程**中，比如**Shape Up**是基于两个月周期的。这已经完全没有意义了。我们还没有完全重写这些脚本，因为加速仍然如此之快。没有一家公司真正重写了所有这些脚本。当你以如此快的速度发货时，你需要一种方式来控制上线的内容，并衡量它是否有效。现在是提到我们的赞助商**Static**的好时机。**Static**为快速发货的团队提供实验和**功能标志**。**Static**构建了一个统一的平台，可以同时实现实验和**持续发货**。内置的实验意味着每次发布都会自动成为一个学习机会，通过适当的**统计分析**，向你展示功能如何影响你的指标。**功能标志**让你能够自信地持续发货。而且因为它都在一个平台上，使用相同的产品数据，所以你的组织内的团队可以协作并做出**数据驱动**的决策。要了解更多信息，请访问static.com/pragmatic。

<details>
<summary>Original English</summary>

**采访者**: Let's internalize that. But that's also enough. Already we were doing enough. Already we had margin that we could hire way more if we had enough good ideas for that. So all this extra productivity we're getting out of the team allows us now to do things like P1 and these other projects that are awesome and they're going to improve the product faster too. Of course they are. The old way of thinking like it's going to take 2 months to deliver a major feature. I mean that's out the door. Of course there's going to be rapid acceleration that's going to filter all the way into our software methodology process like shape of was built on two-month cycles. That doesn't make sense in the same way at all anymore. We have not fully rewritten those scripts yet because the acceleration is still so fast. No company really has rewritten the scripts on on all that. When you're shipping that much faster, you need a way to control what goes live and measure whether it's working. This is a good time to mention our presenting sponsor stats. Experimentation feature flags for teams that ship fast. Static build a unified platform that enables both experimentation and continuous shipping. Built-in experimentation means that every roll out automatically becomes a learning opportunity with proper statistical analysis showing you exactly how features impact your metrics. Feature flags let you ship continuously with confidence. And because it's all in one platform with the same product data, teams across your organization can collaborate and make datadriven decisions. To learn more, head to stats.com/pragmatic.

</details>

### 程序员的黄金时代与行业转变

**采访者**: 接下来，让我们回到即将影响开发者的转变。但我仍然认为，如果**软件开发者**不认为一场变革即将到来，他们就是自欺欺人。以前，他们是生产力上的瓶颈，因此能够获得高薪。

<details>
<summary>Original English</summary>

**采访者**: With this, let's get back to the shift about to hit developers. But I still think software developers are delusional if they do not think a shift is coming where before they were the constraint on how much could be produced and therefore could command

</details>

**David**: ...流向瓶颈的薪水。如果这些瓶颈突然放松，特别是如果我们快进一点，**产品经理**实际上能够产生可以发布和工作的功能，那么情况将会改变。我确实认为，如果我要打赌，我们已经看到了程序员的**巅峰时期**，就那些通过学校或花费数小时变得非常擅长的程序员的**“习得性内疚”**而言。我们不需要相同数量的人来完成相同数量的工作。现在，**杰文斯悖论**（Jevon's paradox）指出，当某种东西的价格下降时，你得到的东西会更多，或者对它的需求会增加，这是真的，但这并不意味着所有程序员都会因此而获救，仅仅因为软件产量将比以往任何时候都多。这是肯定的。顺便说一句，我认为...

<details>
<summary>Original English</summary>

**David**: the salaries that flow to the constraints. If suddenly those constraints now loosen, especially if we fast forward a little bit where the product manager is actually able to produce changes that can be shipped and work, things are going to change. I do actually think if I was going to bet we've seen peak programmer in terms of the learned guilt of programmers who went to either school or spend hours getting really good at it. we're not going to need the same number of them to do the same amount of work. Now, Javon's paradox where as the price of something goes down, you get more of it or you get more demand for it is true, but that doesn't mean that all programmers are going to get bailed out by it just because more software than ever is going to be produced. That's for sure. By the way, I think

</details>

**采访者**: **GitHub**最近受到了很多批评。

<details>
<summary>Original English</summary>

**采访者**: GitHub has gotten a lot of slack or flak lately.

</details>

**David**: 很多。

<details>
<summary>Original English</summary>

**David**: A lot

</details>

**采访者**: 这是情有可原的。我看到一张图表显示他们有**92%的正常运行时间**，这听起来很疯狂。我不确定那是在测量什么，但我能感受到。我对此有点同情。我也认为犯了一些错误，但同时，目前正在生产的软件数量正在呈**火箭式增长**。作为一个文明，我们在全球范围内生产的软件比以往任何时候都多。我的意思是，**OpenClaw**本身，我想他说有**40万行代码**。这以前需要10年和2000人。

<details>
<summary>Original English</summary>

**采访者**: justifiably so. I saw a chart saying they had a 92% uptime, which sounds insane. I'm not sure exactly what that was measuring, but I feel it. I have a little bit of sympathy in that. I also think there's some mistakes were made, but also that the amount of software that's currently being produced is on a rocket ship. We are producing as a civilization globally way more software than we've ever done before. I mean, open claw itself, I thought um he said it was 400,000 lines of code. That used to take 10 years and 2,000 people. Yeah.

</details>

**David**: 为了实现这个目标。

<details>
<summary>Original English</summary>

**David**: To get to that.

</details>

**采访者**: 嗯，不是2000人，但它确实花了很多时间。

<details>
<summary>Original English</summary>

**采访者**: Well, not 2,000 in and but yes, it it took a long time.

</details>

**David**: 我的意思是，很长一段时间，对吧？你看**Shopify**的主要**单体**代码，我想是300万行代码。那是20年。如果你把所有在这上面工作过的程序员加起来，可能有2万人。是的。现在正在发生巨大的转变。大量的软件正在被生产。我能理解为什么那里有点吃力，因为推动力只会加速，对吧？我们甚至还没有看到任何东西。如果你看**AI采用曲线**，基本上没有人使用它。就像我们都在我们**X**上的小圈子里，觉得“哦，每个人都在用”，不，他们没有。世界上大多数公司根本没有这样做。尽管如此，我认为**ChatGPT**很快就达到了8亿用户。显然，存在**采用率**，但与那些走得最远的公司以及它们如何加速发展相比，这根本算不上什么。所以，我确实认为对于普通程序员来说，认为我们可能已经看到了黄金时代的最佳时期，这是正确的。价格肯定会面临压力，因为像我们这样的公司，拥有无限的范围来开发新功能并做更多事情，然后我们可以将所有这些额外生产力投入到做更多事情中。也有很多公司只需要做一件事，如果他们能以十分之一的成本完成那件事，那实际上就是他们的优势，对吧？他们只需要做这件事。它被非常清晰地定义了范围。它是一个**成本中心**。任何软件开发是**成本中心**的地方，而这实际上可能是世界上大多数软件开发，

<details>
<summary>Original English</summary>

**David**: I mean, a long time, right? Like you look at uh I think uh the main monolith at Shopify is 3 million lines of code. That's 20 years. And if you collectively sum up all programmers who've worked on that, probably like 20,000 people. Yeah. Big shifts are coming right now. Um lots of software is being produced. I can see why it's it's creaking a little bit over there because like the pushes are just going to accelerate, right? And we haven't even seen anything yet. If you look at AI adoption curves, basically no one's using it. Like we all in our little bubble in X are like, oh, everyone's no they're not like most companies in the world are just not doing it. Notwithstanding that like I think uh chatt got to 800 million users very quickly. Obviously, there's adoption, but nothing on the scale of what the companies that are furthest along are doing and how much they're accelerating with it. So, I do think it is correct for the average programmer to think maybe we've seen the best of the golden days. Certainly there will be pressures on price because one thing are companies like ours that have essentially unlimited scope to come up with new features and do more and we can then plow in all that additional productivity into just do more. There's also a lot of companies who just need to do a thing and if they can do that thing at a tenth of the cost that's actually their advantage, right? They just need to do this thing. It's very neatly scoped and defined. It's a cost center. Anywhere where software development is a cost center, which is actually probably the majority of software development in the world,

</details>

**采访者**: ...他们将面临这些压力。

<details>
<summary>Original English</summary>

**采访者**: they're going to face these pressures.

</details>

**采访者**: 是的。听起来如果我是一名**软件工程师**，现在我担心的是，我希望自己处于一个更好的位置。你希望自己处于一个你想摆脱**成本中心**，或者在那里变得真正有价值的地方。显然，你需要提升自己的技能。我也在想，**软件工程师**的招聘标准是否会改变，因为如果我回顾90年代，即使你看电影，你也会看到刻板印象，他们是那些不和任何人说话但懂得编码、懂得**汇编语言**的书呆子。然后到了2000年代，它仍然基于语言，随着时间的推移，我想在2010年代，**初创公司**开始不再根据语言招聘，而是根据**算法**招聘，因为你可以学习这些东西。现在我看到一些公司，一些最新的**风险投资**资助的公司，对于**产品工程师**，他们实际上要求**同理心**、**沟通能力**，而不是只看你的编码能力。所以我在想，如果我只是看着这条曲线，对吧？如果我只是把它描绘出来，就像你开始招募人。哦，我在所有这些公司遇到的开发者，他们都非常友善。他们都非常善于沟通。哦，他们和客户交谈，大多数人觉得这根本不是负担。他们越来越喜欢这样做。这就是**限制价值**。现在，**限制价值**在于弄清楚我们应该构建什么，它应该如何构建，我们应该和哪些客户交谈，我们应该关注哪些方面。这就是**产品管理**。这对我来说也很有趣，因为历史上我并不总是对**产品管理**这个职能抱有最高的敬意。我认为有很多**虚假**的东西，我认为有很多人可能做得不多，其中一个原因就是他们不能，因为受限的资源是**实现**，是**产品经理**可以发现他们想做的事情，我想做这个功能，然后他们必须等待四周，让一些非常昂贵的程序员把它变成现实，在这四周里，我想他们可以去和一些人交谈，他们没有被充分利用，他们不是瓶颈，对吧？瓶颈在于**实现**。这绝对会改变。

<details>
<summary>Original English</summary>

**采访者**: Yeah. Sounds like if I'm a software engineer right now and I'm worried about like well, you know, like just want to make sure that I'm I'm at a place where things are going to be better. You want to be at a place where you want to either get out of a cost center or become really valuable there. Obviously, you know, brush up your skills. And also I'm wondering if if the shape of software engineers who will be hired will be changing cuz if if if I just look back from like the '9s right like even if you look at the movies you you saw the stereotypes they were the nerd who didn't talk to anyone but they knew how to code they knew how to do assembly and then we went in the 2000s it was still based on languages and over time I think in the 2010s startups started to not hire for languages but just hire for algorithms because you could learn the stuff and now I'm seeing companies uh some of the the the latest VC funded companies have for product engineers where they they're actually asking for like empathy communication on top of like it's kind of a given that you you know how to code or whatever. So I wonder if I'm just looking at just just this curve, right? If I'm just painting it up like you're starting to get people Oh, and and the developers I I meet at all these companies, they're all really pleasant. They're all just very communicative, very oh and they talk with customers, most of them just it's it's not even a drag. It's like and more and more of them love doing it. That's the constraint value. Now the constraint value is figuring out what should we build, how should it be built, which customers should we be talking to, where should we be focusing. It's product management. It's so funny for me too because historically I've not necessarily had the highest esteem for product management as a function. I thought there was a lot of [ __ ] and I thought it was a lot of people who maybe didn't do as much right and one of the reason was that they couldn't because the constraint resource was the implementation was the product manager could find out that they want to do something I want to do this feature and then they had to wait four weeks for some very expensive programmers to make that reality happen and in those four weeks I mean I guess they could go talk to some they were underutilized they were not the constraint right they the constraint was on the implementation that absolutely absolutely is going to switch

</details>

**David**: ...现在纯粹的**实现**将在某个时候被解决。我不是说现在就能解决，任何没有尝试过在没有审查的情况下将**Bipod**的东西部署到主要代码库的人，但就像去年夏天在**Lex**上学到的教训一样，我不会冒险说在明年夏天之前不会发生这种情况。

<details>
<summary>Original English</summary>

**David**: and now pure implementation is going to be solved at some point. I I'm not claiming it is right now and anyone who is have not tried to just deploy bipoded stuff with no review to major code bases but as the lesson of last summer on Lex I'm not going to put my heart on the block and saying that's not going to happen before next summer

</details>

**采访者**: 同样，这只是常识，但**实现**将会在一般用例中得到解决，对于**边缘情况**会花更长的时间，对于某些情况则没有意义。就像我知道**自动驾驶**对于这种尺寸的汽车很好，但对于卡车，它要么需要更长的时间，要么如果你专注于此，你就会做。但关键是，会存在一些领域，但这些领域会变得更小。是的，我确实认为那种“我只想坐着编码”的刻板印象。你必须达到**John Carmack**的水平才能保留这种特权，即“我只想坐着编码”。

<details>
<summary>Original English</summary>

**采访者**: again this is just like common sense but implementation one implementation will be solved for for a general use case for the edge cases it will take longer and for some cases it will not make sense same thing as I know self-driving is fine for like these size of cars but for like trucks it'll either take longer or if you're specializ you do but the point is like there will be pockets where but those pockets will be smaller. Yes, I do think the stereotype of I just want to sit and code. You have to be John Karmic levels of good to retain that privilege to just I just want to sit and code.

</details>

**David**: 即使是**John Carmack**也超级支持**AI**。

<details>
<summary>Original English</summary>

**David**: And even John Karmak is also super AI appeal and lead.

</details>

**采访者**: 嗯，但他还看到了一些他可以利用的趋势，比如，你知道，人们会购买什么样的游戏，对吧？他需要具备一些商业技能，或者被那些具备商业技能的人包围。完全，完全，完全。

<details>
<summary>Original English</summary>

**采访者**: Well, but also like he he also saw some trends that he could do like for example like just like you know the type of games that people would buy, right? Like he needed to have some business skills or just surrounded by people who did that. Totally, totally, totally.

</details>

**David**: 但你必须是最好的。不仅仅是最好的，你还必须比代理更好，对吧？如果你想获得只做**实现者**的特权，你必须比市面上现有的代理更好。那么谁是最好的呢？你是一个很好的提问对象，因为无论何时你发布职位，甚至在**AI**出现之前，我记得你曾发布过**软件工程师**和**设计师**的招聘广告。实际上，我想采访你雇佣的设计师，**Zoltan**，因为你公布了薪水，那是旧金山的薪水。你公布了确切的数字，你可以查看。你有**社交媒体影响力**，所以它传播得很广，你收到了很多申请。而且据我所知，你做得很好，你努力做到非常公平。你投入了大量的精力。那么，在**37signals**被雇佣需要什么？因为现在你正在努力雇佣最好的人，基于此，你对那些想在这个时代成为最好的人有什么建议？

<details>
<summary>Original English</summary>

**David**: But like you you need to literally be the very best. And not just the very best, but you need to be better than the agents, right? Like for you to get the privilege to just be an implementer, you have to be better than what's available off the shelf from from agents. So, who are the very best? And you're a good person to ask because whenever you advertise a position, and this was even well before AI, I remember that you you put out a a a job for both software engineer and a designer. And actually I want I'm I want to interview your designer who you hired and because uh you published the salary which is a San Francisco salary. You put the exact number you can check it for it. You have a social media presence so it's kind of go go goes wide and you get a lot of applications and you do a pretty good job as as I understand you try to be very fair. You put a lot of effort into it. So, what did it take to get hired at 37 signals? Because now you are trying to hire some of the best and based off of this, what advice do you give to people who are like, okay, I want to be the best in in this age right now.

</details>

### 招聘的挑战与程序员的职业发展

**David**: 这是一个非常好的问题。没有人弄清楚，我们也没有破解它。我之所以这么说，是因为我管理过一个组织，我们必须审阅过数万名候选人，当然，如果你管理**Google**，你审阅过数百万人，但我们审阅过数万名候选人。我们雇佣的候选人数量很少。我的意思是，在**37signals**整个生命周期中，总共招聘过的程序员数量。大概是多少呢？我不知道，最多100到150人？我甚至没有...

<details>
<summary>Original English</summary>

**David**: Incredibly good question. No one has figured out we haven't cracked it. And I say that as someone who have run an organization where we we must have looked at tens of thousands of now, of course, if you're running Google, you've looked at millions, but we've looked at tens of thousands of candidates. The number of candidates we've hired is quite small. I mean total number of programmers that's been through 37 signals over its entire lifespan. What's that going to be like I don't know 100 150 at the most? I haven't even

</details>

**采访者**: 你们团队现在有多大？

<details>
<summary>Original English</summary>

**采访者**: How big is your team right now is?

</details>

**David**: 整个公司有60人，其中大约20名程序员。

<details>
<summary>Original English</summary>

**David**: Uh we're 60 people at the entire company and we are what is that going to be like 20 programmers something like that.

</details>

**采访者**: 是的，这可能差不多。

<details>
<summary>Original English</summary>

**采访者**: Yeah, that's probably about right.

</details>

**David**: 哦，那么其他40个人呢？

<details>
<summary>Original English</summary>

**David**: Oh, so so who what is the other other 40 folks?

</details>

**David**: 我们有设计师...

<details>
<summary>Original English</summary>

**David**: Uh we have designers

</details>

**采访者**: 大概10个左右。

<details>
<summary>Original English</summary>

**采访者**: uh probably like 10 of those.

</details>

**David**: 哇。哇。然后我们有**客户支持**，有14人。然后我们有一堆支持职能，**HR**、**财务**。然后我们有**运营**。**运营**部门相当庞大。我们有10个人管理我们所有的服务器。是的，差不多就是这样。但是的，我想我总共与大约100名程序员合作过或雇佣过。

<details>
<summary>Original English</summary>

**David**: Wow. Wow. And then we have customer support which is at 14. Then we have a bunch of support functions, HR, finance, and then we have operations. Operations is quite large. We have 10 folks managing all our servers. And yeah, that's about it. But yeah, I probably it's probably about 100 people in total that I've worked with uh or employed at the company's programmers

</details>

**采访者**: ...从数万名候选人中。

<details>
<summary>Original English</summary>

**采访者**: out of tens of thousands

</details>

**David**: 我们审阅了。而且即使所有这些招聘，长期来看也并非都成功。实际上，我想我最近看了这个。我们的**打击率**（成功率）充其量也只是略高于**50/50**。

<details>
<summary>Original English</summary>

**David**: we've looked at. And even all those hires did not pan out in the long term. Like I'd actually say I think I looked at this recently. Our batting average at best I think is slightly better than 50/50.

</details>

**David**: 所以即使这些招聘中有一半...

<details>
<summary>Original English</summary>

**David**: So half of even those hires

</details>

**采访者**: 你经历了所有这些，因为你有一个非常漫长而彻底的过程。你付出了很多努力，对吧？

<details>
<summary>Original English</summary>

**采访者**: you go through all of because you have a really long and thorough process. You you you put in a lot of effort, right?

</details>

**David**: 没有人能做到如此高效地招聘而不犯错误。**Google**很久以前发表了一篇很棒的论文，他们尝试了各种不同的假设。嗯，我们能否根据**常春藤盟校教育背景**、**GPA**等所有这些因素来预测员工的结果？结论基本上是，我们一无所知。

<details>
<summary>Original English</summary>

**David**: No one has figured out just to hire with such efficiency that they don't make mistakes. There's a great paper that Google published quite a long time ago now where they tried it all sorts of different hypothesis. Well, can we predict employee outcomes on the basis of Ivory League education background on GPA on all of these things? And the conclusion was basically like we know nothing.

</details>

**采访者**: 我们无法通过这些东西来预测。我们无法通过**LeetCode**来预测。我们无法通过任何这些指标来预测。

<details>
<summary>Original English</summary>

**采访者**: We can't predict it on any of these things. We can't predict it on lead code. We can't predict it on any of these metrics.

</details>

**David**: 我会说我显然被一些非常优秀的人宠坏了，不仅在我的公司，而且在整个**开源**领域。

<details>
<summary>Original English</summary>

**David**: What I'd say is I've clearly been spoiled by working with some very good people, not just at my company, but in open source in general.

</details>

**采访者**: 是的。哦，是的。

<details>
<summary>Original English</summary>

**采访者**: Yeah. Oh, yeah.

</details>

**David**: 因此，我有时对普通程序员的能力有扭曲的看法。当我们进行招聘时，我有时，不，我的意思是，每次，我都会惊讶于大多数提交的质量有多差，人们在展示自己方面投入的精力有多少。这听起来可能很快就变得像**“老古董”**的言论，但这也是找工作的现实。你必须脱颖而出。我理解这会让人不舒服，对吧？谁愿意这样看，就像我的机会有点渺茫。但这也是一个陷阱，让你陷入以几率来思考这个问题，因为我一次又一次地看到这种误算：人们会说，好的，有1000名申请者，只有一个人能得到这份工作，或者两个人能得到这份工作，所以机会只有**0.1%**。不，根本不是这样。用这种数学计算，你的机会是**0%**。

<details>
<summary>Original English</summary>

**David**: And therefore, I've ended up with occasionally a twisted perspective of what the average programmer is capable of. And when we do hiring rounds, I am sometimes, well, not sometimes, I mean, every time, I'm kind of surprised how poor the majority of the submissions are, how little effort is put into being presentable. And that can sound really boomery very quickly, but it's also just the reality of trying to get a job. Like, you got to stand out. And I understand that that's uncomfortable, right? like who wants to look at this as like well my the odds are kind of against me but it's also a trap to actually fall into thinking of this in terms of odds because what I've seen the miscalculation happened time and again is people go like okay so you have a thousand applicants there's only one who gets the job or maybe two who gets the job so that 0.1% chance no it's not not at all with that math you had 0% chance

</details>

**采访者**: 是的。

<details>
<summary>Original English</summary>

**采访者**: yes

</details>

**David**: 零，而且非常。他们可能有**10%**、**20%**、**30%**的机会。它不是**均匀分布**的。这不是抽奖。我们不会随意挑选一个人，然后说：“哦，就是这个人了，因为他们碰巧被选中了。”根本不是这样。我们一开始就会淘汰至少一半的申请。也许是三分之二，仅仅因为他们要么没有直接针对职位，要么没有遵循我们相对明确的招聘说明，对吧？他们显然不适合，或者我们闻到了一些其他不好的气息。然后可能剩下三分之一，然后我们开始查看一些提交。然后我们历史上会将其缩小到一个大约20人的池子，我们会给他们一个**居家测试**。**居家测试**很棒。有些人讨厌它。他们觉得那是**免费劳动**。我心想，你在说什么？我不会把你的代码测试提交用于任何用途。我会把它部署到生产环境吗？你认为我们是如何想到那个代码测试的？因为它已经存在于系统中了。我这样说有点严厉。我也理解同情，比如我不想投入六个小时去做一个测试，如果它不会有任何结果的话。好吧，我明白了。但没有办法避免，因为如果你脑子里想着你只要寄出简历，就会有人打电话给你，和你进行30分钟的对话，然后说，先生，你被录用了。我不知道那是否曾经存在过，但今天肯定不存在。在我这一生中，它从未存在过。

<details>
<summary>Original English</summary>

**David**: zero and the very They probably had a 10% chance, 20%, 30% chance. It is not equal distributed. It is not a lottery. We don't just like pick a thing out and be like, "Oh, it's going to be this person because they happen to be the one drawn from the bunch." Not at all. We discard off the bat probably at least half the applications. Maybe it's twothirds just because they're either not addressing the job directly, they are not following the instructions in the relatively clear spoken written openings that we have, right? they're obviously not right for it or or whatever or we get some other smells. Then there's like perhaps a third left and then we start looking at some of the submissions. Then we narrow it down historically to a pool of around 20 people that we give a at home test. The at home test is wonderful. Some people hate it. They feel like it's free labor. I'm like, what the [ __ ] are you talking about? I'm not going to use your submission to a code test. What? I'm going to deploy it to production. How do you think we came up with that code test because it already exists in the system? I say that a little harshly. I also get the sympathy of like I don't want to put six hours into making a test if it's not going to go anywhere. Okay, I get it. But there's no way around it because if you have it in your head that you just send in a resume, someone's going to call you up on the phone, have a 30-minute conversation with you and go, you've hired sir. I don't know if that ever existed, but certainly does not exist today. It never existed in the lifetime I've been in this.

</details>

**采访者**: 嗯，它存在的唯一时候，对吧，就是...

<details>
<summary>Original English</summary>

**采访者**: Well, the only time it exists, right, is

</details>

**采访者**: ...通过一个非常**热情推荐**。

<details>
<summary>Original English</summary>

**采访者**: through a very warm referral where correct

</details>

**David**: 如果你跳过了整个流程。

<details>
<summary>Original English</summary>

**David**: where you're starting a typing if you're skipping the whole pipeline.

</details>

**David**: 当你跳过整个流程时，通常只发生在公司非常早期的时候，当你创立一家公司时，而且通常是双向的，风险很高，然后你会说，我的这个朋友，我连续和他工作了两年。我会闭着眼睛相信他们。所以这实际上是整个招聘过程的**“黑药丸”**。如果我们看长期成功率，我们从“我与这个人工作了两年，我们应该雇佣他们”这种方式获得的长期员工比我们通过公开招聘获得的更多。对我们来说，从公开招聘中找到那种能在我们环境中茁壮成长的程序员，确实异常困难。它确实发生过。我们确实以这种方式雇佣过人，我仍然希望相信，即使当你开始计算时，几率看起来疯狂地小，比如，天哪，我们审阅了数万人，然后有多少人被雇佣了，有多少人最终没有成功，就像天哪，从一开始就只剩下少数人，这有点勒索。但直接通过**热情推荐**进行招聘，正如你所说，效果非常好，成功率很高。但这对任何人有什么帮助呢，对吧？这并不是一个非常可操作的建议，除了说，尽你所能做到最好，尽你所能投入精力，并与某人合作，因为我想把它作为反驳。有些人脑子里有这种观念，如果他们在他们认为糟糕的地方工作，他们就不应该努力。

<details>
<summary>Original English</summary>

**David**: And when you skip the whole pipeline, it typically only happens at the very beginning of a company when you're founding a company and often it goes both ways where it's very risky and then you say like this buddy of mine, I work with this person for two years straight. I would like trust them with my eyes closed. So that's actually the black pill on the whole hiring process. If we look at the long-term success rates, we have had more long-term employees from I've worked with this person for 2 years, we should hire them than we have from the open calls. It is actually exceptionally difficult has been for us to find the kind of programmer who thrives in our environment from open call. It has happened. We have hired people that way and I continue to want to believe even if the odds seem insanely long when you start doing the math of like oh my god we've looked at tens of thousands and how many then got hired and how many then didn't work out like Jesus there's only like a handful left from starting with that that that's kind of blackmailing but then hiring directly on the base of warm referral as you call it um has worked very well and that the hit rate there is really high but how does that help anyone right like that's not a very actionable advice except that's to say Get as good as you can get and put in as much effort as you can and work with someone because I want to say that as a counter. Some people have this notion in their head that if they work at a place they consider shitty, they shouldn't try.

</details>

**David**: 你在自作自受，朋友。如果你出现在一个糟糕的工作场所，我们可以客观地一致认为它确实是一个糟糕的工作场所，然后你又说：“嗯，我应该尽量敷衍了事。我应该尽量偷懒。我应该整天看**X**或**Reddit**，对吧？”所有与你一起工作的人都会看到。你知道那份**热情推荐**会从哪里来吗？它会来自那些在糟糕的工作中与他人合作过的人，但他们发现那个人仍然出现，并尽力学习、交付、做所有这些事情。这里没有捷径。你只需要优秀。如果你不练习，你就不会优秀。如果你认为你的工作场所不值得你付出最好的努力，你就是在欺骗自己。

<details>
<summary>Original English</summary>

**David**: You're shooting your own feet, buddy. If you show up at the shitty place of work, and we can even be objectively in unison about that, that it is a shitty place of work, and you then go like, "Well, I should just try to skirt. I should just try to goof off. I should just try to read X or Reddit all day, right? Everyone else you work with, they're going to watch that. You know where that warm refo is going to come from? It's going to come from someone who worked with someone else at a shitty job, but identified that that individual still showed up and did as best as they could to learn, to ship, to do all of this stuff. There is no shortcut here. You simply just have to be good. And you will not get good if you do not practice. And if you think your place of employment is not worthy of your best, you're cheating yourself.

</details>

**采访者**: 如果你没有帮助，即使那是一个糟糕的地方，如果你没有帮助那个地方变得更好，一个只雇佣那些能进一步提高标准的人的优秀公司，为什么要雇佣你呢？

<details>
<summary>Original English</summary>

**采访者**: If you're not helping, even if it's a shitty place, if you're not helping that place get better, why would a great place hire you who only hires people to to further raise the bar?

</details>

**David**: 这完全是一种自我安慰。这既是说，我在一个糟糕的地方工作，如果我不想投入，你可能会感到恼火。我不是说你必须喜欢你的老板。我实际上会说，我以前的大多数老板，我对他们并没有最热情的感情。我仍然非常努力，为了我自己的**修养**，为了我自己的**教育**，为了我自己的感觉，我就是那种会努力工作的人，只是为了在机会来临时，当我的所有才能都被需要，我的所有技能都磨练成熟时，我能做好准备。

<details>
<summary>Original English</summary>

**David**: This is total cope. And it's cope both on the side of I work at a shitty place if I don't want to put things in. You could be annoyed. I'm not telling you you have to love your boss. I'd actually say the majority of people I used to work for, I didn't have the warmest feelings about them. I still tried really hard for my own edification, for my own education, for my own sense of I'm the kind of person who shows up and does a good job just that I will be ready when the opportunity arrives when all my talents are needed and all my skills are honed.

</details>

**采访者**: 对。嗯，嗯，你最终加入**37signals**不就是这样吗？它只是一份合同工作，你知道，就像在合同工作中，你没有所有权，而且正确，但你努力了。

<details>
<summary>Original English</summary>

**采访者**: Right. Well, well, was this not how you ended up at 37 Signals where it was just a contract job or something and you know like on a contract job you have no ownership and correct but you showed up and

</details>

**David**: 正确的，**Jason**最终意识到...

<details>
<summary>Original English</summary>

**David**: correct and Jason ended up realizing

</details>

**David**: ...这个**小混混**最好拿到一些股权，否则他就会走人。这是一个具有里程碑意义的故事，你不应该从这个故事中推断出所有事情。我的意思是，所有创始人的故事在某种程度上都是具有里程碑意义的故事，但基本原则仍然是一样的：努力工作，尽力而为，学习更多。我以前也曾一度有点遗憾地认为，你可以成为一名优秀的程序员，但并不真正喜欢编程。你不需要在工作时间之外关心编程。你当时是这样想的吗？

<details>
<summary>Original English</summary>

**David**: okay this uh punk better get some equity otherwise he's out the door now that's a siminal story and you shouldn't extrapolate everything from that I mean all founder stories by the way are siminal stories in that regard but the fundamental principle is still the same show up do as good as you can get and learn more. There also was to my chagrin to some extent. I perhaps contributed it to it a bit for a while, which was this notion that you can be a great programmer and not really like programming. That you don't have to ever care about programming outside working hours. Was was this what you thought of or like

</details>

**采访者**: 嗯，我错误地这样想，因为我当时在反对**过度工作**、**每周100小时**、**每周120小时**的**疯狂痴迷**，顺便说一句，那从来都不是我的经验。我们不是以这种方式开始**Basecamp**的。在过去的25年里，我们一直以**每周40小时**的平均工作制。但同时，正如我一开始所说的，我真的很喜欢电脑。所以，我在空闲时间玩电脑。我在空闲时间看电脑相关的东西。这不像我正在为**Basecamp**客户发布功能，一周七天，每天24小时。不是那样的。但我确实在玩电脑。我在看新东西。我在探索新系统等等。我认为在2010年代，有一段时间存在一个误解，认为你不需要做任何这些事情。你只需要来上班，完成你的工作，你就会受到追捧，因为编程是一项非常有价值的活动，而且能够做这件事的人很少，所以他们会雇佣任何人，甚至那些几乎不在乎的人。我想那已经结束了，如果它曾经是真的话，我想它确实是真的。

<details>
<summary>Original English</summary>

**采访者**: Well, I thought of it mistakenly because I was pushing back on the overwork 100hour week, 120 hour week maniacal obsession, which by the way never was my experience. We did not start base camp that way. We have worked on a 40hour week rolling average over those 25 years. But also, as I said at the very beginning, I really like computers. So, I play with computers in my free time. I look at computer things in my free time. It's not work in the sense that I'm whatever shipping features to basec camp customers like just 247. That's not what it is. But I am playing with computers. I am looking at new things. I am exploring new systems and whatever. And I think there was for a while in the 2010s a misconception that you didn't have to do any of those things. you could just show up and do your work and you would be so soughta because programming was such a valuable activity and there were so few people who could do it that they'd take anyone even people who barely gave a [ __ ] and I think that's over if it ever was true and I think it was true

</details>

**采访者**: **训练营**就是完美的催化剂，或者说它们就像金丝雀。

<details>
<summary>Original English</summary>

**采访者**: the boot camps were the perfect uh like catalyst or or like they were the canary when

</details>

**David**: 顺便说一句，这也是经济应该如何运作的，当薪水很高时，这意味着劳动力供应不足。因此，我们应该把劳动力引入这个池子。

<details>
<summary>Original English</summary>

**David**: which also by the way is how the economy is supposed to function when salaries are really high it means that there's not enough supply of labor Therefore, we should get labor into the pool.

</details>

**采访者**: 没错。

<details>
<summary>Original English</summary>

**采访者**: Exactly.

</details>

**David**: 所以，我并不是说我对**互联网**有任何不满。我只是说，那已经结束了。

<details>
<summary>Original English</summary>

**David**: And so, I'm not I don't even have any qualms about internet. I'm just saying like that's over.

</details>

**采访者**: 不，我认为，你看，我们正在谈论的是，这是否是程序员的**黄金时代**？你是否已经度过了**程序员的巅峰时期**？我在想，**程序员的巅峰时期**是否真的意味着，几乎任何想进入这个行业，并愿意付出一些努力，几个月或几年的人都能做到。你可以学习编码。你可以去上大学或去**训练营**，或者投入时间，然后你就能找到工作，因为面试和推荐信都不是必需的。我们没有检查，而且我认为它可能正在结束。你确实需要**推荐信**。我想越来越多的公司会把**推荐信检查**作为我们招聘的一部分，而且不仅仅是检查你是否在那里工作过，比如你会不会，我接到过像**Data Bricks**这样的公司的电话，他们以**推荐信卡**闻名。他们不仅检查推荐信。他们会深入挖掘，不仅仅是你会不会再次和这个人合作，他们的弱点是什么？

<details>
<summary>Original English</summary>

**采访者**: No, I I think looking, you know, we're talking about like is it is the golden age of the programmer? Have you passed peep programmer? And I wonder if peep programmer really meant that almost anyone who wanted to get into the industry and was willing to put in some effort, few months or maybe a few years could do it. You could learn how to code. You could go to either college or to a boot camp or put in the hours and you could get hired at a place because the interviews were the references were not needed. We we didn't check and I it's probably coming to an end. You do need references. You more I think more and more companies will be doing reference checks as part of our thing and it's not just going to be have you worked there like would you I I've had these calls from like data bricks is is famous for reference cards. They don't only check for references. They drill you not just would you work with this person again, how what were their weaknesses,

</details>

**David**: 对吗？

<details>
<summary>Original English</summary>

**David**: right?

</details>

**采访者**: 你会雇佣他们去哪里，等等，等等。

<details>
<summary>Original English</summary>

**采访者**: Where would you hire them, etc., etc. And

</details>

**David**: 不，我理解。奇怪的是，“**程序员的巅峰时期**”听起来像是一个影响所有程序员的事情。但它不是。最好的程序员，甚至不是说全世界只有10个人是最好的。真正优秀的程序员现在比以往任何时候都更有价值，因为他们是那些能够从**AI加速**中获得最多好处的人。这对我改变对此的看法是关键，因为我也发现，也许这并非普遍适用，但在**37signals**内部，根据我自己的经验，我作为程序员享受的时间比2000年代初我刚发现**Ruby**时还要多。这种“我刚发现**Ruby**”的感觉又回来了，能够同时以如此快的速度在这么多层面上前进，能够探索**P1**，能够思考**Umachi**的**双启动**，做所有这些事情，工作本身变得更加令人愉快。我在我们最**AI优先**的程序员身上也看到了同样的事情，他们也许也有一些焦虑，但这些焦虑被纯粹的享受推到了一边，享受着新能力带来的工作。所以这里存在一个**分叉**，我们都应该觉得我们不知道发生了什么，对于一些人来说，这会带来一定程度的焦虑。我理解这一点，尤其当这是你的生计，你可能会想，嗯，我也希望七年后能支付我孩子的大学学费。那会是什么样子？我明白。你无法将这种焦虑转化为任何有成效的事情，除非你投入其中。对吧？因为如果你只是坐着瞎想，试图思考七年后世界会是什么样子，你就是在浪费时间。所以那是唯一的途径。唯一的途径就是要么对此感到兴奋，而这甚至不需要付出太多努力。正如我们所说，如果你坐下来使用这些模型，从壁橱里拿出你的爱好项目...

<details>
<summary>Original English</summary>

**David**: no, I understand it. The weird thing is peak programmer sounds like this is something that affects all programmers. It does not. The best programmers are not even the best as in like it's 10 people around the world. really good programmers are currently more valuable than ever because they're the ones who are able to get the most out of the AI acceleration. And this was the kicker for me in changing my perspective on this is that I've also found and maybe it's not universally true, but certainly within 37 signals in my own experience, I'm enjoying my time as a programmer more than any time since early 2000s when I just discovered Ruby. This has the I just discovered Ruby feel to it that it is so satisfying to be able to move this fast on so many levels at the same time to be able to explore the P1s to be able to think about dual booting omachi to do all of that stuff that the work itself has gotten vastly more enjoyable and I've seen the same thing for the most AI forward programmers that we have maybe also have some of these anxieties but they're kind of pushed to the side just out of sheer enjoyment working with the new capacities. So there is a bifocation here where we should all feel like well we don't know what's going on and for some people that's going to produce some degree of anxiety. I understand that especially when it's your livelihood and you're like well I'd also like to be able to pay for my kids college in seven years. What does that look like? I get it. You're not going to be able to manifest that anxiety into anything productive unless you just plow it into leaning in. Right? Because if you just sit and spin around, try to think about what the world's going to look like seven years from now, you're wasting your time. So that's the only path. The only path is to either get excited about this, which I don't even think takes that much effort. As we said, if you sit down with these models, you pull out one of your hobby projects from the closet

</details>

**采访者**: ...你从未完成过的。

<details>
<summary>Original English</summary>

**采访者**: that you never finished,

</details>

**David**: ...你从未完成过的，你只是尝试一下，我不明白你为什么会真正喜欢电脑却不觉得那个实验很有趣。我在那些开始接触它的人身上看到了这一点。**Kent Beck**就是一个很好的例子。他编程52年了，他说他喜欢编程，他找到了使用代理来构建一些雄心勃勃的东西的平衡点，他一直想构建的东西，他正在构建他的**Smalltalk**服务器，这以前需要永远，现在它越来越接近了，而且仍然需要很长时间。然后他在中间休息，他在湖边有自己的房子，他只是去那里看两个小时的鸟，然后回来继续工作。这太美妙了。顺便说一句，**Kent**是我一直以来的英雄之一。这正是我刚开始编程的时候，在我学习**Ruby**之前，我在2001年丹麦的一个会议上看到了**Kent**的演讲，我完全被他驾驭材料的能力，他的大胆以及他作为一个演讲者的出色表现所吸引。这发生在我读完**《极限编程》**和许多其他书之后。**《Smalltalk最佳实践》**是我向任何想学习如何构建方法和类等细节的程序员推荐的首选书籍。**《Smalltalk最佳实践》**，**Kent**在1995年或1996年出版的书，至今仍是我最喜欢的关于**战术编程模式**的书。所以，很高兴听到他也被**AI**吸引，同时也在享受鸟儿。我的意思是，我也尝试这样做。现在确实有点紧张，因为我发现大多数全身心投入的人，他们工作比以往任何时候都更努力。我现在在自己身上也看到了这一点。当你能够通过对这些代理的一小时监督，变得如此有效和有影响力时，这真的令人陶醉。如果你有一个活跃的**多巴胺回路**，当有东西交付时它会被触发，那现在它就是超活跃的。我需要告诉自己，这不像是一次限时销售。**AI**下个月和接下来的几个月都会在这里。我不能像对待限时销售一样操作，我需要在接下来的两周内收获所有的**多巴胺**。我实际上认为这对于那些走得最远、最投入的人来说是现在的主要挑战，那就是记住，这已经是它们表现最差的时候了，正如老生常谈所说，对吧？你最好找到一种方法，不要完全沉迷于其中，无论它多么令人兴奋。是的，这种沉迷是一个大问题。就像**Steve Yegge**一样，他看起来比视频中更疲惫，但他很诚实，他被拉入其中。他有朋友也是如此，当你在边缘时，你就在那里。你显然被**AI**迷住了，但你如何保持平衡，比如，好吧，退一步，你知道，我知道你以前谈论过睡眠的重要性。显然你没有闹钟。

<details>
<summary>Original English</summary>

**David**: that you never finished, and you just give it a try, I don't see how you really like computers and not find that experiment enjoyable. And I I've seen this with with people who are getting into it. Kent Beck is such a great example. He's been programmer 52 years and he is saying like he he loves doing it and he found this balance between using the agents to build something ambitious that he always wanted to b he's building his small talk server which which used to take forever and now it's it's getting closer and it's still taking a long time and then in between he's chilling at his he has his house on on the lake and he just goes and like just looks at the birds for two hours and then gets back to it. It's beautiful. Kent is, by the way, one of my all-time heroes. This was right when I got started in programming right when I before I was picking up uh Ruby, I saw Kent speak at a Danish conference in 2001 on stage and I was completely mesmerized by his command of both the material, how bold he was and how great of a speaker he was. And this was after having read Extreme Programming and many of these other things. Small Talk Best Practices is my number one recommendation for any programmer who want to learn the nitty-gritty of how to structure a method and a class and the rest of it. Small Talk Best Practices, which is Kent's book from 95, I think, or 96, is to this day my favorite book of all time on tactical programming uh patterns. So, it's wonderful to hear him being agent pilt while also enjoying the birds. I mean, I try to do that, too. And this is actually there's a bit of attention right now is that most of the people I find who are allin, they're working harder than they ever have. And I've seen that with myself now too. When you can be this effective and impactful on an hour of supervision of these agents, it's really intoxicating. If you have an active uh dopamine loop up there that gets triggered when something is shipped, it is just hyperactive right now. And I need to go, do you know what? This is not like a limited sale. like AI is going to be here next month and the months after that. Like I cannot just operate as though it is a limited sale and I need to get all the dopamine in harvested within the next two weeks. That I actually think is the main challenge right now for the people who are furthest along and most pled on it is like remember that this is as bad as they're ever going to be as the cliche goes, right? You damn well better find a way not to get consumed entirely about it as exciting as it is. And and then yeah, there there's this consuming is is is a big deal. Like with Steve Yaggi, he was he looks a bit more drained than like you can see it on the video, but he he has he's honest like he's he's being pulled into this. He's doing he has friends who are and when when you're on the edge, you're there. You've clearly been AI pill, but how are you finding of keeping a balance of like all right, stepping away, you know, like I I know you've I think you previously talked about the importance of sleep. Apparently you don't have an alarm.

</details>

### 工作与生活的平衡：保持身心健康

**David**: 正确。我不使用闹钟，尽管我妻子现在使用了，因为孩子们需要按时上学。但对我来说，每晚**八小时睡眠**是你对自己认知能力最好的投资。所以，每次我睡眠不足八小时时，我都会提醒自己，这真是一个糟糕的交易。如果你从八小时减少到六小时，我会想，嗯，在这种情况下，我将清醒18小时。为了多获得一两个小时，减少睡眠，我要在这18小时里承受多大的拖累？这是一个非常糟糕的数学题。这毫无意义。当然，偶尔这是非自愿的。实际上，我确实有过几次，尤其是在**AI**方面，非常罕见，我可以用两只手指数过来，我曾失眠，大脑运转得有点太快。这对我来说不典型，现在仍然不典型。但我确实有过几次，对吧？所以，我明白那种兴奋的来源。但我也会说，你最不应该牺牲的是睡眠，然后你不应该牺牲你的健康。你不应该试图节省每周锻炼的三小时，去做更多的代理工作。这是一个非常糟糕的交易。保持良好状态。如果你想保持头脑清醒，没有什么是比这更重要的了，就是系统的其他部分，即使不是在巅峰状态，也要在一个良好的可持续水平上运行。我确实认为现在有些人害怕精疲力尽。

<details>
<summary>Original English</summary>

**David**: Correct. I don't use an alarm, although my wife now does because the kids need to go to school on a regular basis. But yeah, for me, eight hours a night is the best investment you can make in your own cognitive capacity. So, I just am reminded every single time I do not get eight hours that it is such a poor trade. If you go from the eight to the six, I go like, well, I'm going to be awake for in that case 18 hours. What is the drag I'm gonna carry for all those 18 hours for getting one more hour, two more hours by cutting back on the sleep? It is such a bad piece of math. It makes no sense. Now, occasionally it's involuntary. I have actually had, especially around this AI stuff, I've had a couple of times, very rare, I can count on two hands the number of times where I've been sleepless, like the ra the brain racing a little too much. That's not typical for me and it's still not typical. But I have had a couple of them, right? So, I get where some of that excitement comes from. But I'd also say the last thing you should trade is sleep and then you should not trade your health. You should not try to save the 3 hours a week of working out to do more agent work. That's a very poor trade. Keep in good condition. like there's nothing this can be more important if you want to keep like sharp up there that like the rest of the system is operating if not at peak capacities than at uh at a good sustainable level right and I do think there are some individuals right now who are at fear of running ragged

</details>

**采访者**: ...关于我们将会长期处理的事情，比如放慢速度，伙计。它不像是一次限时销售。接下来的十年，我们会看到越来越多，它会变得越来越疯狂，所以不要浪费你的健康，不要浪费你的睡眠，不要浪费你的饮食，为了任何事情。因为即使在短期内，它也不起作用。你无法在三周内变得更有效率，通过每晚减少两三个小时的睡眠，然后认为三周后还能保持清醒。你会一团糟的。那么，让我们结束吧。我们谈论了我们不知道的事情。很多事情我们都不知道，但让我们以你所知道的事情来结束。所以你很久以前就可以退休了，然后只是，你知道，放松一下，然后听听鸟鸣。是什么让你继续工作，让你继续建造，让你每天起床？在**AI**出现之前，你会打开你的终端，我想你分享过，你会去写代码，现在你和代理一起做。是什么驱动着你？展望未来，你对哪些事情感到兴奋？

<details>
<summary>Original English</summary>

**采访者**: on something that we're going to be dealing with for like slow down buddy like it's not again a limited sale the next 10 years we're going to see more and more it's going to get crazier and crazier so don't squander your health don't squander your sleep don't squander your diet in the service of anything because even on the short term, it does not work. You cannot get more productive within 3 weeks, let's say, by trying to cut back two or three hours of sleep every night and then think there's anything coherent left after 3 weeks. You will be a hot mess. So, let's close. We talked about the stuff that we don't know. A lot of things we don't know, but let's close with what you do know. So you you could have retired a long time ago and just you know kick back and and like listen to birds. What is it that keeps you doing keeps you building keeping getting up every day and before AI you would open your terminal I think you you shared like like you would go and and write now you're doing with agents like what drives you and and and looking ahead like what what are things you're excited about?

</details>

### DHH：对计算机的热爱与工作的意义

**David**: 我的驱动力仍然是对**计算机**深切的热爱。这简直是度过我时间最好的方式，最有趣的方式。我可以在很多事情上花费时间。我确实在很多事情上花费时间。我不仅仅玩电脑。我开赛车。我花了很多时间。我有三个孩子。我们享受所有这些。但如果我每天要花八小时做一件事，我的最佳选择就是电脑。自从我五岁以来一直如此。无论是**视频游戏**，还是现在感觉有点像**视频游戏**的东西，实际上是操作所有这些代理，以及玩一点**星际争霸**，移动它们。

<details>
<summary>Original English</summary>

**David**: My drive continues to be a deep love of computers. This is simply the best way, the most fun way to spend my time. I could spend my time on a lot of things. I do spend my time on a lot of things. I don't just do computers. I drive race cars. I take lots of time up. I have three kids. We enjoy all of that stuff. But if I'm going to fill eight hours every day with an activity, my best bet is computers. And it has been so since I was literally 5 years old. Whether it's video games or what now feels a little bit like a video game actually instrumenting all these agents and uh playing a little bit of Starcraft with moving them around and

</details>

**采访者**: **Toro**。

<details>
<summary>Original English</summary>

**采访者**: Toro.

</details>

**David**: 是的，没错。所以，我真的很喜欢**电脑**。所以，无论我是否需要出于经济原因这样做，我都会继续玩电脑，看看是什么让它们运转起来，并创造东西。我认为这是有些人对**财富**存在的另一个巨大误解，他们将其视为某种**检查点**。好像一旦你成功了，你就可以悠闲地躺着，好像那就是幸福一样。我们有上百年的**心理学研究**告诉我们，不，那是痛苦。如果你拥有世界上所有的时间，却没有目标，没有使命，**休闲**是行不通的。它不会是一种充实的方式。这应该从字面上每个销售自己生意的企业家身上得到明显的例子。他们会在海滩上坐三周，然后又回到工作中，对吧？因为这实际上不仅仅是他们追求一个目标所做的事情。它本身就是目标。它本身就是使命。它是满足感。它是对作为人类的肯定，我不是一个躺着不动的**blob**。我是一个有用的人，我将我的技能发挥到极致。所以，我将继续这样做。我将继续这样做，无论我是坐在键盘前打字，还是操作这些代理，还是它们在教我，无论以何种方式，我都想玩电脑，我将继续这样做。然后，更具体地说，在过去的三个月之后，我现在正在努力投入**代理可访问性**。例如，这就是我过去几周一直在做的事情。我们一直在开发新的**CLI**，这也让我意识到，我们还没有完全达到**AGI**，对吧？你会想，嗯，直接让你的代理制作一个**CLI**就行了。它会做的，但它还没完全达到那种程度，对吧？我希望它能完美，代理仍然需要一点帮助。我很高兴能为这些代理提供帮助，我们很快就会发布一个很棒的**Basecamp**的**CLI**。也许到这期节目发布的时候，它可能已经发布了，而且对于其他产品也是如此，我想全力投入所有这些。我们如何尽可能多地利用它？然后现在我也只是一个无比好奇的人。我每天早上醒来都有一个新的仪式，那就是不再拿起手机跳到**X**上。就在我醒来的时候。我实际上不认为这很好。但这需要巨大的意志力才能不这样做，因为我太好奇发生了什么。现在发生的事情太多了。我想知道。我想知道。我想享受它。成为它的一部分。所以我不认为这会结束。我不认为对电脑的热爱会消退。事实上，如果有什么不同的话，我现在看到它正在蓬勃发展。我比五年前更喜欢电脑了。这太棒了。太棒了，**David**。这太棒了。非常感谢。

<details>
<summary>Original English</summary>

**David**: Yes, exactly. So, I just really like computers. So, whether I need to do so for economic reasons or not, I will continue to play with computers, see what makes them tick and make things. I think that's the other big misconception that some people have about wealth is that they conceive of it as some sort of checkpoint. Like once you've made it, then you can just kick back in leisure as though that was happiness. We simply have a hundred years of psychological studies telling us no, that's misery. If you have all the time in the world and no purpose, no mission, leisure is not going to cut it. It's not going to be fulfilling way. And this should be obvious by example of literally every entrepreneur who sells their business. They sit on the beach for three weeks and then they're back into the game, right? Because this is actually not just something they do in pursuit of a goal. It's the goal itself. It is the mission itself. It is the satisfaction. It is the affirmation of being a human that I'm not just a blob laying around. I am a useful individual who put my skills to the best use possible. So, I'm going to continue to do that. And I'm going to continue to do it whether I'm sitting typing at the keyboard, whether I'm instrumenting these agents, whether they're teaching me, however which way it is, I want to play with computers, I'm going continue to do that. And then even more specifically after the last three months, I'm leaning in hard now with agent accessibility. For example, this is what I've been doing the last few weeks. We've been working on the new CLI, which also taught me like we're not quite at AGI yet, right? You think like, well, just ask your agent to make a CLI. It will, but like it's not quite there, right? like I want it to be just right and the agents still need a little bit of help. I'm very happy to provide that help to these agents and we'll release a great CLI for Base Camp very very shortly. Maybe by the time this is out it'll probably be out and for the rest of them too and I want to lean into all of this. How can we use this as much as we possibly can and then right now I'm also just an incredibly cur curious person. I wake up every morning I have a new ritual which is not to pull my phone up and start hopping on X. like right when I wake up. I don't think actually that is great. But it takes a tremendous willpower to not do so because I'm just so curious about what happened. There's so much happening right now. I want to know. I want to know. I want to be enjoying it. Be a part of it. So I don't foresee that ending. I don't foresee a love of computers evaporating. In fact, if anything, right now I'm seeing like a a flourishing of it. I'm liking computers more than I did five years ago. And that's amazing. Amazing, David. This was awesome. Thanks. Thanks a bunch.

</details>

**David**: 好的。谢谢邀请。这真棒。

<details>
<summary>Original English</summary>

**David**: All right. Thanks for having me. This is really great.

</details>

**采访者**: 这是一次引人入胜的对话，我喜欢**David**的活力。我希望他身上那种显而易见的能量也传递给了你们。我非常欣赏**David**坦诚地说，他对**AI**的立场没有改变，因为他的哲学没有改变。只是工具变得足够好，可以做有用的事情。对于经验丰富的开发者来说，**AI自动补全**令人烦恼。另一方面，能够自己生成相当不错的可工作代码的**AI代理**现在非常有用。然而，**David**不断回到**品味**、**判断力**和**技艺**。他不仅仅是说让模型随意编写。恰恰相反。他有非常高的质量标准，他希望输出的代码是他真正引以为豪并愿意合并的。感觉**AI**可能会让良好的**判断力**比以往任何时候都更有价值。我也非常喜欢**David**对**设计重要性**的看法。在**37signals**，设计师帮助弄清楚应该构建什么，它应该如何工作，并且越来越多地甚至决定它如何实现。我想知道**37signals**在思考设计师有点像开发者，开发者有点像设计师方面，是否领先于行业一步。最后，我发现**David**关于我们可能已经达到了**软件工程师巅峰**的观点是一个有趣的论点。**David**认为我们将比以往任何时候都生产更多的软件。但他的观察是，我们可能正在接近开发者能够获得高薪时代的终结，仅仅因为他们是瓶颈。我的两分钱是，对于能够构建盈利软件的专业人士来说，肯定会有很高的需求。但这将意味着**软件工程师**不仅擅长编码或使用**AI生成代码**，而且能够监督复杂系统的构建，具备**品味**和**商业意识**。如果你想听更多**David**的访言，请查看节目笔记中他的一集额外节目。另外，请查看节目笔记，了解与**务实工程**、**软件工艺**和**构建软件实用方法**相关的深度探讨。如果你喜欢这个播客，请在你喜欢的播客平台和**YouTube**上订阅。如果你也为本节目留下评分，那将不胜感激。谢谢，下期节目再见。

<details>
<summary>Original English</summary>

**采访者**: This was a fascinating conversation and I love the energy that David has. I hope some of this energy that is obvious in person also came across to you. I really appreciated that David was open that his stance did not change about AI because his philosophy changed. It's just that the tools became good enough to do useful stuff. AI for autocomplete was annoying for experienced developers. AI agent that can produce pretty good working code by themselves on the other hand are now pretty useful. And yet David kept coming back to taste, judgment, and craft. He wasn't just saying just let the model write whatever. It's the opposite. He has a very high quality bar and he wants the output to be code that he would actually be proud to merge. It feels like AI might make good judgment even more valuable than before. I also really liked how David thinks about the importance of design. At 37 Signals, designers help figure out what should be built, how it should work, and increasingly even decide how it gets implemented. I wonder if 37 signals is a step ahead of the industry in thinking about designers a bit like developers as well and developers a bit like designers as well. Finally, I found David's take that we might have hit peak software engineer an interesting argument. David thinks we'll produce more software than ever. But his observation is that we might be nearing the end of the time when developers could command high compensation simply because they were the bottleneck. My two cents is that there will surely be high demand for professionals who can build profitable software. But this will mean software engineers who are not only good at coding or using AI to generate code, but can oversee building complex systems have taste and business sense as well. If you'd like to hear more from David, check out a bonus episode with him linked in the show notes. Also, check out the show notes for related to pragmatic engineering deep dives on software craftsmanship and practical ways of building software. If you enjoyed this podcast, please do subscribe on your favorite podcast platform and on YouTube. And a special thank you if you also leave a rating on the show. Thanks and see you in the next
</details>