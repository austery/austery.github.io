---
author: The Pragmatic Engineer
date: '2026-11-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=x6WqD4qHxSc
speaker: The Pragmatic Engineer
tags: []
title: ''
summary: ''
insight: ''
draft: true
series: ''
category: ''
area: ''
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/10 -->

### 精彩片段与本期介绍

我们需要 500,000 个活跃的 WebSocket 连接。当时我们有一个方案，是在一堆 Kubernetes Pod 中把 Slack 作为无头 Chrome 实例启动。每做 5 小时的压测，每个无头 Chrome 实例就要花费 37 美分。

<details><summary>Original English</summary>We needed 500,000 active websocket connections. We had a solution that would spin up Slack as a headless Chrome instance in a bunch of Kubernetes pods. It was 37 cents per headless Chrome instance per 5 hour tunch of load testing.</details>

>> 是啊，单单那一项测试就得花大概 15 万美元。

<details><summary>Original English</summary>>> Yeah, we're talking about $150,000 for that one test.</details>

>> 当时全 GitHub 所有的拉取请求和 Issue 加起来只有 16 个分片。

<details><summary>Original English</summary>>> There were 16 shards for all of pull requests and issues</details>

>> 整个 GitHub 就只有 16 个，考虑到我们所知道的跟那一整块领域相关的庞大数据量，这个数目真不算多。当时的答复是：“噢，我们不能再加了，因为我们已经有太多的散射查询（scatter queries）了。”

<details><summary>Original English</summary>>> across all of GitHub. across all of GitHub only 16 which is not very many given the amount of data that we know is associated with that whole space. The answer was oh well we can't have more because we already have so many scatter queries.</details>

>> 工作中哪些部分是 AI 帮不上忙的？

<details><summary>Original English</summary>>> What parts of the job does AI not help you with?</details>

>> 它基本上完全没在性能优化方面帮上我。至少排查调研那一块是这样。就目前而言，我发现大语言模型擅长的是……

<details><summary>Original English</summary>>> It has not helped me with performance optimizations basically at all. At least the investigation part. The LLMs right now I find are good at</details>

>> 当底层架构开始不堪重负时，你该如何对一款数百万人日常使用的产品进行扩容？今天的嘉宾在 Slack 和 GitHub 两家公司都做过这件事。Maud Lemaire 是一位主任工程师，也是《Refactoring at Scale》一书的作者。她在 Slack 工作了八年，在 GitHub 做过数据库扩容，还优化过 Cursor 的首 Token 时间（time to first token）。今天我们将探讨用 500,000 个 WebSocket 连接进行负载测试——在这个任务中使用无头 Chrome 实例不仅资源消耗过大，成本也过于高昂；为什么 GitHub 之前所有的拉取请求和 Issue 只有 16 个数据库分片；为什么在像 GitHub 这样庞大的 Rails 单体架构内部，散射查询会是一个巨大的痛点；为什么平台工程师和产品工程师应该在团队之间轮岗；等等。如果你想了解大家每天都在使用的产品内部是如何进行架构扩容的，那么这一期节目就是为你准备的。

本期节目由 Turbopuffer 赞助呈现，基于对象存储构建的向量与筛选搜索，速度快、成本低，且具备极强的可扩展性。

本期节目由 Antithesis 赞助呈现，让你自信发布产品的平台。在今天的节目中，我们将讨论在大型生产系统不断扩张时对其进行重构，这种工程挑战好比在万米高空重造一架波音 747。但为什么在使用 AI 编码智能体（coding agents）时，不能仅仅依靠代码审查呢？因为代码审查正变成一种日益天真且低效的做法，这正是 Antithesis 远远超越这种常规实践的原因。Antithesis 在恶劣的模拟环境中运行你的整个系统，该模拟既包含针对性测试，也包含模糊测试（fuzz testing）。通过运行这种模拟，它会在你的用户遇到 Bug 之前把每一个 Bug 都找出来。并且由于这种模拟是完全确定性的，它不仅能发现 Bug，还能让你对每一个问题进行完美复现，这让修复问题变得容易得多。

当我第一次听说 Antithesis 时，我的第一反应是：自动化 Bug 发现和完全确定性的测试听起来像科幻小说，但实际上它底层是非常硬核的工程技术。Jane Street、Supabase、Rapid、Railway 和 Datadog 都能满怀信心地交付由智能体编写的代码，因为他们知道这些代码已经经过了 Antithesis 的验证。为了让大家了解 Antithesis 是如何为大型生产系统提供助力的：Datadog 在重写其每天收集超过 100 万亿个事件的 Datadog 事件平台时，正是使用 Antithesis 来验证他们的新架构。如今，Antithesis 已成为 Datadog 编码智能体评估测试平台（harness）中所采用的诸多修正策略之一。想要查看更多案例研究和详细信息，请访问 antithesis.com/pragmatic。

Maud，欢迎来到本播客。

<details><summary>Original English</summary>>> how do you scale a product that millions of people use daily when the architecture underneath it is starting to break. Today's guest did this both at Slack and GitHub. Mode Lameir is a principal engineer and the author of the book refactoring at scale. She spent eight years at Slack worked on database scaling at GitHub and improved time to first token at cursor. Today we cover load testing with 500,000 websocket connections, a job where using headless Chrome instances were too resource intensive and too expensive. Why GitHub had only 16 database charge for all port requests and issues. And why scatter queries were a massive headache inside a large Rails monolith like GitHubs. Why platform and product engineers should rotate between teams and more. If you want to understand what scaling up looks like inside of products you probably use every day, this episode is for you. This episode is presented by Turbopuffer Vector and Filtech Search built on object storage. It's fast, cheap, and extremely scalable. This episode is brought to you by Anticys, the platform to release with confidence. In today's episode, we'll talk about rewriting massive production systems as they scale up, which is a kind of engineering challenge as rebuilding a 747 midair. But why not just use code review when using AI coding agents? It's because code review is an increasingly naive and ineffective approach to do so, which is why antithesis goes well beyond this practice. Antithesis runs your whole system in a hostile simulation. This simulation includes both targeted testing and fuss testing. By running this simulation, it finds every bug before your users do. And because the simulation is fully deterministic, it doesn't only find bugs, it gives you a perfect reproduction of every issue, which makes it much easier to fix issues. The first thing I thought when I heard about antithesises is that automated bug discovery and fully deterministic testing sounds like science fiction, but actually it's hardcore engineering under the hood. Jane Street superbased rapid railway and data dog ship agent written code with full confidence because they know it's been verified by antithesis. And to give a sense of how antithesis is helped with large production systems, data log use antithesis to verify their new architecture when rewriting the data log event platform, a system that collects more than 100 trillion events per day. Today, antithesis is one of many correcting strategies being used as part of data logs harness for their coding agents. To see more case studies and details, head to anticysis.com/pragmatic. Mo, welcome to the podcast.</details>

### 从生物学到计算机科学

>> 谢谢你邀请我。

<details><summary>Original English</summary>>> Thank you for having me.</details>

>> 非常高兴你能来。

<details><summary>Original English</summary>>> It is so nice to have you here.</details>

>> 这真是我的心愿单项目之一。非常开心，所以我很……

<details><summary>Original English</summary>>> This is a bucket list item. very much. So I'm very</details>

>> 好吧，这在播客里还是头一次。通常我都是以一个问题开始。这次我不打算直接提问。我要给你看一张照片，然后我会问：我在这里看到的是什么？

<details><summary>Original English</summary>>> well this this is the first in the podcast. Usually I ask start with a question. I'm not going to start with a question. I will show you a photo and I will ask what am I seeing here.</details>

>> 我看到的是一个婴儿，看起来有几个月大？

<details><summary>Original English</summary>>> I'm seeing a baby who who looks like how many months?</details>

>> 大概一岁左右吧。也许差一点才满一岁。是的。

<details><summary>Original English</summary>>> Maybe about a year old. Maybe a little before a year old. Yeah.</details>

>> 坐在电脑前。呃，如果你看的是视频版，我们也会把它放放屏幕上。发型都一样。所以我的我的我的我的问题是，你生来就与计算机为伴吗？

<details><summary>Original English</summary>>> Sitting in front of a computer. Uh we we're also putting this on on the screen if you're watching it on video. Same haircut. So my my my my question is were you born with computers?</details>

>> 嗯，差不多吧。其实还有我比这小得多的照片。大概才几个月大。我我真的，差不多就是头都勉强立不住的那种，我爸让我坐在他腿上，像这样靠着他，而他在……我也不知道他在干嘛。他可能在批改什么作业之类的，呃，因为他在我们搬到美国之前教了教了 17 年计算机科学。

<details><summary>Original English</summary>>> Um very nearly. There are pictures of me much younger than that actually. Maybe like a couple months old. I I truly like I'm barely keeping my head up where my dad has me sitting in his lap like resting against him and he's I don't know what he's doing. He's probably like grading some kind of assignment or um cuz he he was teaching he he taught computer science for 17 years before we moved to the US.</details>

>> 嗯。

<details><summary>Original English</summary>>> Mh.</details>

>> 而且，呃，对，还有好多我拿着 ASCII 码表的照片。嗯……现在回想起来真是搞笑。嗯，但我走上这条路某种程度上算是个意外。嗯，你会以为所有的变量和环境因素本该导向一种非常合乎逻辑的、线性的职业发展轨迹，但这完全不是……总之，他很久以前就得考虑这些事情。嗯，但我当时觉得那听起来无聊透顶。嗯，我当时就觉得，呃，不要不要不要，而且我真的很喜欢我的生物课。我以为自己会成为一名遗传学研究人员。那就是我的计划。我父母总是叫我别那么拼，稍微放松点，因为我当时很有规划。我上大学时，我从微生物学开始学起。我选了分子生物学、有机化学，所有这些课程。我对听节目的所有美国听众说明一下，我当时已经攒了足够的 AP 学分，所以严格来说我相当于大二学生，而不是大一新生。噢，是的。

<details><summary>Original English</summary>>> And uh yeah, know there's a bunch of pictures of me like holding ASI tables. Um which now in hindsight is hilarious. Um but I ended up doing this sort of by accident. um you'd think that all of the variables and the environment would have led to like a very logical sort of linear career trajectory and that is not at all what so anyway he had to think about that like eons before. Um but I thought it sounded really boring. Um I was like uh no no no and I really liked my bio classes. I thought I was going to become a genetics researcher. That was my plan. And my parents always told me to chill the heck out because I had plans. I had when I started university, I started microbiology. I signed up for molecular biology, organic chemistry, all the things. I was already I'd already acred enough AP credits for all the Americans listening that I was technically like a secondyear college student rather than a first year. Oh, yeah.</details>

>> 噢，哇。

<details><summary>Original English</summary>>> Oh, wow.</details>

>> 而不是大一大学学生。

<details><summary>Original English</summary>>> Rather than a first year college student.</details>

>> 所以，你想速通大学？

<details><summary>Original English</summary>>> So, you want to speedrun college?</details>

>> 噢，是的。我当时准备好了。

<details><summary>Original English</summary>>> Oh, yeah. I was ready.</details>

>> 跳过那些好玩的年份。是的，

<details><summary>Original English</summary>>> Skip the fun years. Yeah,</details>

>> 直接去工作，

<details><summary>Original English</summary>>> get straight to work,</details>

>> 我之后一直都是这样。我曾经有一个学期修了大概 19 个学分，到了某一刻我心想：我为什么要这么做？这真是一个糟糕的决定，不过我的意思是，我乐在其中。所以我想，你知道，我对“好玩”的定义大概跟别人对“好玩”的定义不一样吧。然后对，我本来打算走那条路的。接着大概过了 3 周，有几件事让我特别困扰。第一，你擅长做某件事，并不代表你喜欢做它。我觉得在很长一段时间里我都把这两者混为一谈了。话说回来，当你 18 岁的时候，谁又……你能懂什么呢？但我把非常擅长死记硬背和喜欢死记硬背搞混了。我不知道你有没有上过分子生物学课，但那门课需要大量的死记硬背。你要去学生物循环。所以我本来打算从有机化学转到……转到化学工程。要这么做的话，在麦吉尔大学属于不同的学院。我是说，那是一所很大的学校。那里有理学院，我当时是在理学院，还有工学院。我在看工程学院大一新生的所有必修要求时，发现有一门编程课。有一门计算机科学导论。所以下个学期我就把其中一门生物课换成了计算机科学导论课。

<details><summary>Original English</summary>>> which I kept doing that. I had like a 19 credit semester and at some point I was like, why did I do that? That was such a poor decision, but I mean, I had fun doing it. So, I guess, you know, my my brand of fun is I guess different from other people's brand of fun. And yeah, I was going to do that. And then like 3 weeks in, there were a couple things that really bothered me. One, I it's not because you're good at something that you like doing it. And I think I conflated the two for a really long time. I mean, to be fair, when you're 18, like, who like, what do you know? But I conflated being really good at memorization with liking memorization. And I don't know if you've ever taken a molecular biology class, but it is a significant amount of memorization. And you're learning the KB cycle. So, I was going to switch into organic chemistry into um uh chemical engineering. And to do that, that's a different faculty at McGill. I mean, it's a very big school. There's faculty of science. I was in the faculty of science. There's faculty of engineering. and I was looking at all of the requirements for first year engineering students and there was a programming class. There was a intro to computer science. So I swapped out one of my bio courses the next semester with the intro to computer science class.</details>

>> 计算机科学类……

<details><summary>Original English</summary>>> Computer science y</details>

>> 对，嗯，我跟我妈说我换成了一门计算机科学课。“千万别告诉爸爸，求你别告诉他我换成了计算机科学课。就是我不知道……我很害怕自己会不喜欢它，然后他就会很伤心，因为他太爱这个领域了。”他爱得深沉。

<details><summary>Original English</summary>>> and um I told my mom I swapped it out for a computer science class. Please do not tell dad please do not tell him that I swapped it out for a computer science. Like I don't I'm scared I'm not going to like it and then he's going to be sad because he loves this so much. He loves it.</details>

>> 这对他来说就像真爱一样。然后她说：“好啊，没问题。”我敢肯定她大概两分钟后就告诉他了。嗯，因为我妈向来如此。我爱她，但天哪，我觉得她心里知道这不会变成一场灾难。果不其然，最后就像我……我告诉他们我选了这门课，上了 3 周之后，我就觉得：“噢，我真的很喜欢这个。”这跟分子生物学课完全相反，在那门课上我原本以为我很喜欢。这感觉就像是：“噢，有了这种力量”，我相信你也有过这种感觉。就像是，我手里只有一台电脑，我敲打键盘输入内容，然后它就能做事情。“我觉得自己像个神。”

<details><summary>Original English</summary>>> This is like true love for him. And she was like, "Sure, okay." I'm pretty sure she told him like 2 minutes later. Um cuz that's what my mom does. I love her, but like man, I think she knew that it was not going to be, you know, a wreck. And sure enough, eventually like I I tell them I'm taking this class and 3 weeks in, I'm like, "Oh, I really like this." Complete opposite from the molecular biology class where I was like, I really liked it. It was like, "Oh, with the power, I'm sure you have this feeling. It's like I only have a computer and I type into it and then it does things. I feel like a god."</details>

>> 接着你的第一份工作——你做过实习，但紧接着实习之后的第一份正式工作是在 Rent the Runway，对吧？

<details><summary>Original English</summary>>> And then your first job, you did internships, but your first job, which followed the inter was at Rent the Runway, right?</details>

>> 没错。是的。

<details><summary>Original English</summary>>> It was. Yeah.</details>

>> 那是一家挺知名的公司，多亏了……凡是做工程管理的人大概都会知道 Camille Fournier 写的那本《The Manager's Path》。而她当时就在 Rent the Runway。

<details><summary>Original English</summary>>> So, pretty well-known company thanks to thanks to anyone who's injury management will probably know of the book The Manager's Path by Camille Forner. And she was at Rent the Runway.</details>

>> 确实是。是的。实际上那也是我在那里实习之后想回去的一个重要原因，因为我……你见不到太多女性……

<details><summary>Original English</summary>>> She was. Yeah. And actually that was a big part of why I wanted to to go back after my internship there was because I you didn't see very many women</details>

<!-- chunk 2/10 -->

在那个时候担任 CTO 这类职位。而且，我是说，我妈妈当年差一点就成了时装设计师，所以我们从小就从第一季开始看《天桥骄子》（Project Runway）。《天桥骄子》是我唯一被允许熬夜看的东西。所以它把两件我热爱的事情结合在了一起：结合了编程、计算机科学——我当时主要做前端方面的工作——以及时尚。我可以花极便宜的价钱租衣服，要是我想的话，甚至可以穿着像 Monique 那样的晚礼服到处走。这太酷了。我觉得整个团队里普遍有非常多的女性，我认为部分原因是公司所处的行业领域。不过，对于那些有机会和卡米尔（Camille）待在同一间屋子里的人来说，她身上就是散发着一种强大的气场，我对此非常钦佩。我的意思是，即便在层级上我和她隔了好多级，我依然觉得我想向这位女性学习，我真的很钦佩她展现出的这种气场和自信。所以回去工作是一个非常容易做出的决定。但是在我回去几个月后她就离开了，不过一年后她依然对我进入 Slack 工作起到了关键作用。

<details><summary>Original English</summary>
in those CTO type positions at the time. Also like I mean I my mom very nearly became a fashion designer and so we grew up watching Project Runway from the very beginning. That was like the one thing I was allowed to like stay up late to watch was Project Runway. And so it combined two things that I loved. uh combined, you know, programming, computer science. I was mostly doing front-end stuff at the time and and fashion. I could just like rent stuff for dirt cheap and like walk around in a monik like ball gown if I wanted to. It was it was so cool. I think the there were so many women on the team in general. I think partly because of the space that the company was in. Um, but I also just for folks who've had the opportunity to be in a room with Camille, she just commands this presence and I had so much respect for that and I I I mean even if you know I was many levels removed from her, I was like I want to learn from this woman like I really admire this uh this presence that that she has and this confidence. And so it was it was an easy cell. It was very easy cell to go back. But then she left a couple months after I came back, but she was still instrumental in um in helping me land a job at Slack a year later.
</details>

### 加入 Slack 与早期的可扩展性挑战

>> 这是 2016 年的 Slack。我记得特别清楚，因为在 2016 年我加入了 Uber，当时我们还在用 HipChat，那是 Atlassian 的——

<details><summary>Original English</summary>
>> This is Slack in 2016. So at the time I I vividly remember because in 2016 I joined Uber, we still had Hip Chat, which was Atlassian's
</details>

>> ——相当于 Slack 的产品，或者是 Slack 的竞争对手。很多公司都在用它，后来他们遭遇了两次极其糟糕且无法辩解的数据泄露。Uber 几乎立刻迁移到了另一款产品上，我记得当时他们评估了 Slack，但 Slack 无法承受那种规模。呃，我——

<details><summary>Original English</summary>
>> Slack offering uh or like Slack competitor. It was used by a lot of companies and then they suffered two terrible and undefensible uh data leaks. Uber almost immediately migrated off to a product and I remember that they evaluated Slack and Slack would not scale. Uh I
</details>

>> 感到很惊讶

<details><summary>Original English</summary>
>> surprised
</details>

>> 我原本以为这是后来的事，Uber 是在 2019 年才转向 Slack 的。但我在 Twitter 上就此发过一个帖子，我说我们当时开发了一个叫 UAP 的东西，它是构建在 Mattermost 之上的。

<details><summary>Original English</summary>
>> I I I thought this was uh later in in 2019 Uber would move to Slack but I wrote a thread about this on on Twitter and I said like well uh we we we built something called UAP which was built on top of Mattermost.
</details>

>> 对，对，对，对。我当时在想，是不是我们的内部团队单纯想自己造轮子，所以才说对方无法扩展规模？但参与构建 UAT 的一位工程师——因为他们当时与 Mattermost 紧密合作，实际上在对那个开源产品进行扩展——他确实说过，他们曾和 Slack 坐下来谈过，Slack 当时表示无法支持四五万人同时在一个房间里。所以当时根本不可行。也就是说，在 2016 年那个背景下，Slack 在一个房间里服务超过一万人可能都还很吃力，如果我没记错的话，两三万人……

<details><summary>Original English</summary>
>> Yes. Yes. Yes. Yes. And I was thinking like hm did our in-house team just want to build something and did they just like say that's like they didn't scale but one of the engineers who built UAT cuz they they were working hand in hand with matter most they were actually expanding it the open source offering he actually said that they sat down with Slack and Slack said that they cannot support 50,000 or 40,000 people in one room at the time. So there there was no way. So like just to set the stage in 2016, Slack still maybe struggles to serve more than 10,000 people in one room if if I remember 20,000 or 30,000.
</details>

>> 我记得康卡斯特（Comcast）好像是 3 万人，3 万人——

<details><summary>Original English</summary>
>> I think 30,000 was Comcast 30,000
</details>

>> ——但他们支持不了 4 万人。所以这就是 Slack 当时的状况。这是早期的 Slack。它当时已经极其受欢迎了，大家都喜欢它。Teams 还在萌芽阶段，我甚至都不确定它那时候诞生了没有。所以……

<details><summary>Original English</summary>
>> but they they can do 40,000. So this is the state of Slack. This is early Slack. It was it was already wildly popular. People loved the the onboarding teams was in infancy. I'm not even sure if it was born at the time. So
</details>

>> 是的，我觉得那时候还没有。

<details><summary>Original English</summary>
>> yeah, I don't think it was
</details>

>> 你进入了 Slack。

<details><summary>Original English</summary>
>> you you you get to slack.
</details>

>> 是的，是的。

<details><summary>Original English</summary>
>> Yeah. Yeah.
</details>

>> 那么你当时需要处理、或者说有机会去处理的问题是什么？

<details><summary>Original English</summary>
>> And what what were the problems you had to work on that that you got to work on?
</details>

>> 是的。是的。嗯，是的，在 Rent the Runway 的时候我就非常渴望钻研性能问题了。只是那时候我只能在自己的业余时间去研究，但我依然乐在其中。然后当我来到 Slack 时，我的入职导师是一位资深工程师，他当时专门负责性能问题。我很快把入职的新人任务搞定后，就问他：“你在做什么？你那边在忙什么呢，Moist？”他就说：“哦，我给你发几个工单吧，你想做性能方面的工作吗？”我说：“想，我非常想。”于是他就发给了我几项任务。在初创公司那种环境下，这些算是相对容易的事情——当你需要迈向下一个阶段、拿下下一个客户，或者构建自认为能吸引用户的下一个功能时，你往往会做出很多短期决策，而在内心深处你大概知道未来某个时候肯定得重新审视这些决策。我们当时做的很多性能工作，实际上就是在重新审视过去抄的捷径。我的意思是，虽然是经过深思熟虑的捷径，但也是我们明知迟早会反噬我们的捷径。我当时做的很多工作就是这些。而且这是在 Slack 的企业版产品正式推出之前。我在产品 GA（正式发布）前几个月入职，当时 IBM 已经在试用——

<details><summary>Original English</summary>
>> Yes. Yeah. Um yeah, I very much got the the performance itch from from the runway. It just wasn't I just had to work on it, you know, on my own time, but I still enjoyed doing it. And then when I showed up at Slack um I my onboarding buddy was um this like very senior engineer who was working on performance issues specifically at the time and I burned through some of you know my starter stuff and I was like what are you working on? What are you working on over there moist? And he was like oh let me send you some tickets like do you want to work on performance? I was like yes yes I do. So, he sent me a couple things. Um, like relatively easy stuff in startup land when you need to get to the next place and just get that next customer or build that next feature that you think is going to capture like you make a lot of short-term decisions that you know probably inside your soul you will revisit at some point. Um, and a lot of the performance work that we were doing at the time was just a lot of revisiting of shortcuts. Um I mean like well-calulated shortcuts but like shortcuts that we knew were going to like bite us in the butt eventually down the line. So a lot of that um work I was doing and this was before the like enterprise the Slack enterprise product was launched. So I started a couple months before GA IBM was already triing
</details>

>> ——这款产品了。他们在那里算是在进行测试。他们是一家大公司，员工非常多。如果我没记错的话，有十万多人。

<details><summary>Original English</summary>
>> the product. They were sort of on beta there. Um they are a large company. Lots of people work there. left 100k plus people if I recall.
</details>

>> 是的。所以，其中一个不同点其实是，让成千上万的人同时在同一个频道里，其实在某种程度上还算行得通。

<details><summary>Original English</summary>
>> Yeah. So, one of the distinctions actually was um it was sort of fine to have tens of thousands of folks on one in one channel at one time.
</details>

>> 我们把他们分散在同一个 Slack 组织内的不同团队中。

<details><summary>Original English</summary>
>> Um and we were sort of spreading them out across different teams within the same Slack organization.
</details>

>> 显然他们可以互相发私信，还可以做些其他事情，这种模式还算奏效。但是 IBM 那边基本经常崩溃。我当时没有参与那些对话，但事后回想起来，我的印象是我们一旦同意正式发布（GA），他们就同意开始扩大规模并向 Slack 添加更多用户。就像是说，一旦达到 GA，我们就不能再像以前那样限制你们添加人员了。于是我们达到了 GA，他们就开始非常激进地增加人员。最后我们不得不组建一支专门的企业性能团队。而我最终得以加入那个团队，因为我碰巧一直在做各种零散的性能优化事项。在团队里我绝对资历最浅，但我喜欢这样。我觉得在我迄今为止的职业生涯中，很多时候我都是团队里资历最浅的人。过去几年可能没那么明显了，但我就是通过这种方式学到最多东西的，它一次又一次地把我逼出舒适区，这真的是最有意思的。

<details><summary>Original English</summary>
>> Um obviously they could DM each other among some other things but that sort sort of worked. Uh but it was IBM was sort of falling over on a regular basis and I think I was not part of these conversations but I get the impression in hindsight that when we agreed to GA then they agreed that they would start scaling and adding more users to Slack. Like once we reach GA you know we we can't hold the reins on you adding more people as much. Um, so we hit GA and they were started adding more people like pretty aggressively. Uh, we started we ended up having to spin an actual team up that was just the enterprise performance team. I ended up being able to join that team cuz I just happened to be working on odd random performance things. Um, I was definitely the most junior person on the team, but I love that. I feel like I've spent so much of my career to date being the most junior person on the team. might be less so in the last couple years, but I that's how I've learned the most and it's really just like pushed me out of my comfort zone over and over again and it's just like it's the most it's the most fun.
</details>

### 2016–2017 年 Slack 的底层架构

>> 我们能不能简单介绍一下 2016 至 2017 年 Slack 的基础架构，也就是架构入门指南？我们知道现在的 Slack 已经有了翻天覆地的变化，这跟它今天的面貌完全不同。但是当我们想到 Slack 的工作区、频道、私密群组、私信时，在幕后，从数据库的角度、从当你向某人或某个频道发送消息时所发生的事情来看，在扇出或写入方面，它是如何构建起来的？在企业版之前、甚至在企业版推出时，模式都是一切从属于一个公司、一个工作区、一个团队单元。所有数据也是按团队进行分片。所以如果你在一个非常大的团队里，我们就会给你一个更大的数据库，但最终你在亚马逊上能花钱买到的最大规格数据库也会被用尽。但是，你的意思是曾经有段时间这种分片方式是行得通的，大公司可能就拥有自己的独立数据库实例，有一段时间一直运转良好，他们并没有把它装满？是的。

<details><summary>Original English</summary>
>> And can we do a bit of a Slack ar in the 2016 2017 Slack architecture 101 101. Now this is as we know Slack has changed a lot. This is now how not how it will look like today at all. But when we think about Slack workspaces, then channels, private groups, DMs, behind the scenes, how was it built up in terms of databases, in terms of what happened when you sent a a message to someone or to a channel, in terms of fanouts or rights. So the pattern before enterprise and still with enterprise was everything belonged to a company, a workspace, a team unit. And all of the data also was sharded by team. And so if you were on a really big team, well, we just would give you a bigger database and eventually uh you run out of the largest size of database that you can throw money at Amazon for. But but but you're saying that there was a time where this charting worked where a large company might just have its own database instance and for for a while they it would work. They didn't fill it up. Yeah.
</details>

>> 而较小的公司会共享。多个公司会在同一个——

<details><summary>Original English</summary>
>> And smaller companies would share. They would be multiple on the same
</details>

>> ——以多租户的形式共用同一个数据库实例。但作为客户，你的数据不会分散在多个数据库分片上，就只在这一个上面。这也是我们分发消息的方式。对于 WebSocket 连接，当你连接、登录 Slack，建立那个 WebSocket 连接时，你是与一台和你所在公司关联的服务器建立连接。因此，如果你公司里的所有人都在非常忙碌、非常频繁地在 Slack 上聊天，你们所有人都在同一台服务器上。同样，如果我们有非常非常活跃的客户，最终我们可以直接指定：“哦，好吧，这是属于你们的聊天服务器实例。”

<details><summary>Original English</summary>
>> multi-tenant on the same database instance. But you as a customer your data was not spread across multiple database shards. It was just on this one. It was also how we distributed messages. So for the websocket connection, when you were connecting, logging into Slack, establishing that websocket connection, you were establishing that websocket connection with a server that was associated with your company. And so if everyone at your company was very busy, very busy chatting on Slack, you all were on that one same server. And again like if we had really really busy customers eventually we could just say like oh well this is your instance of the chat server
</details>

>> 在很长一段时间里，这种方式大体上运行良好。企业版开始以一些特殊的方式让情况变得复杂，我们……我是说，初创公司往往会做出当时觉得不错、但随后却无法扩展的决定。我们当时做出了一种假设，认为在超大公司内部其实是由较小的公司组成的——

<details><summary>Original English</summary>
>> um and that was mostly fine for a very long time. Enterprise started complicating that um in some special ways in that we I mean again startups you like sort of make decisions that are fine in the moment but then sort of don't scale. We sort of made the assumption that like inside really big companies it was smaller companies
</details>

>> ——比如像 IBM 的市场部本身就是一个独立的公司。所以你会登录 IBM 的市场部工作区，或者工程部……我的意思是，工程部其实太庞大了，应该是 IBM 工程部的某个子集。听起来这有点一厢情愿，以为可以把这个大问题直接拆解成较小的……

<details><summary>Original English</summary>
>> and so like marketing at say IBM is its own company. So you sign into the marketing workspace at IBM or the engineering works I mean engineering actually is too big. It's some subset of engineering at IBM. It sounds like this is a bit of wishful thinking that you could just turn this large problem into smaller
</details>

<!-- chunk 3/10 -->

### 跨团队架构与数据表分立

……问题，对吧？然后你就能直接让你现有的架构运转起来，

<details><summary>Original English</summary>
problems, right? And then you can just make your current architecture work,
</details>

>> 但还是需要有一个总揽全局的实体。嗯，所以我们创建了企业（enterprise），这实际上只是 team 表里的另一行，里面只包含 `is_enterprise = 1`。然后所有与该 enterprise 关联的团队都有一个 enterprise ID。而在 IBM 内部，你肯定还是会想——比如说你在其中一个工程团队工作，我在另一个工程团队工作，我们想协作，我希望能给你发私信。我们明明在同一家公司，我理应能给你发消息。我们当时把一家公司内部的这些团队当成独立的公司来对待，但随后我们不得不创建另一个凌驾于一切之上的实体，让你仍然能够跨团队。

这就非常迅速地变得极其复杂了。但随之变得非常糟糕的部分是，整个 IBM 的所有人，不论是在市场团队、工程团队还是别的什么团队，全都在同一时间向 enterprise 分片查询他们所有的私信、全公司范围的大频道等等所有这些东西。然后在那份数据里，当你启动 Slack 时，频道会显示在左侧边栏。你会以为逻辑很简单，比如根据 user ID 获取所有频道成员关系记录就行了。嗯，事实并非如此。

我觉得最初也是出于好意，因为私信看起来跟常规的公开频道是完全不同的东西，对吧？它们看起来确实不一样。嗯，所以那是一个单独的表，而公开频道就是公开频道，

<details><summary>Original English</summary>
>> but there still needed to be like an overarching body. Um, so we created an enterprise which was really just another row in the team table that just had is is enterprise one and and then all of the teams associated with that enterprise had an enterprise ID and you still within IBM would want to say, you know, say you were working on one of the engineering teams. I was working on a different engineering team. We want to collaborate. I want to be able to DM you. We're at the same darn company. I should be able to send you a message. We pretended that these teams within a company were their own companies, but then we had to create this other entity that overarched everything where you could still cross teams.

And that got very complicated very fast. But then the part that became really terrible was everyone across all of IBM, whether they were on the marketing team, the engineering team, whatever, were all quering the enterprise shard for all of their DMs and the big companywide channels, all of that stuff, all at the same time. And then within that data, when you're booting up Slack, you have your channels that show up in the left sidebar. You'd think that it was just like cool get, you know, for user ID, get all channel membership entries. Um, that was not the case.

And I think it came from a good place in that DMs seemed like a separate thing from a regular public channel, right? Like you they seem different. Um, and so that was a separate table and a public channel is a public channel
</details>

>> 所以那也是一个单独的表。但接着私密频道看起来又不一样了。我觉得从产品角度来看，你完全能理解；从产品安全角度来看，你也完全能理解在查询私密频道时会需要更严格的审查。

<details><summary>Original English</summary>
>> and so that was a separate table. But then private channels seemed different. And I think like from a product perspective, you can totally see it. And from a product security perspective, you can also totally see that you want more scrutiny when you are querying for private channels.
</details>

>> 所以那也是一个单独的表。后来群聊私信（group DM）出现了，它们看起来就像某种私密频道，于是就被直接粘进了私密频道表里。所以当你执行查询去填充边栏时，实际上是在做一次规模非常庞大的 join union。

<details><summary>Original English</summary>
>> And so that was a separate table as well. And then group DMs came about later and it seemed like they were just sort of like a private channel and so they were just glued into the private channel table. So when you were making that query to populate your sidebar, you were actually doing a big big old join union.
</details>

>> 那么，一旦你或者团队有了这个想法，或者搞明白了这些表并不合理，但现在面对的是包括 IBM 之类的海量客户正在施加巨大负载、正在持续使用它的情况，接下来发生了什么？

<details><summary>Original English</summary>
>> So what happened once once you and once a team had the idea or figured out that this tables don't make sense, but now you're talking about a lot of customers including the likes of IBM just, you know, putting a bunch of load on it. They're using it.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 你怎么把这三个正在被高频使用的表迁移合并成一个……

<details><summary>Original English</summary>
>> How do you migrate from these three tables that are actively being used into one
</details>

### 数据迁移与代码重构

>> 一直处于高频使用中。是的，我认为这始于计算提及（mentions）。计算提及——比如获取未读徽标图标——也是一个非常复杂的查询，你必须跨所有这些表进行 join。嗯，对延迟非常敏感，而我们当时已经经历过了尽一切可能去减轻负载的过程。在我的一个队友做一些关于提及的工作时，他说：“我们必须得把这些表合并在一起了。这根本不行，在不得不真正开始自掘坟墓之前，我们能做的事情只有这么多了。”于是我就说：“行啊。好，我来尝试做这件没人想做的极其可怕的事情。这看起来完全没问题。”

事后回想起来，我对此也有了更深的体会。如果你在 GitHub 上看 blame work（Flamework）——那是 Cal Henderson 写完 Flickr 之后开源的 PHP 框架——它会解释很多关于 Slack 早期是什么样子的疑问。

<details><summary>Original English</summary>
>> all the time? Yeah. I think it came about from calculating mentions. So calculating mentions like to bad get the badge icon uh was also a very complex query whereby you had to join across all these tables. Um very uh latency sensitive and we had gone through the process of doing as much as we possibly could at that time to ease the load. And in one of my teammates doing some work on mentions, he was like, "We got to we got to join these tables together. It will not like there's only so much we can do before we have to like really start digging the hole." So I I was like, "Sure. Yeah, I I will endeavor to do this very scary thing that no one else wants to do. That seems totally fine." I have so much appreciation for this in hindsight too in that if you look at blame work on GitHub which is the PHP framework that Cal Henderson open sourced after writing Flickr, it will explain many things about what Slack was like early on.
</details>

>> 是的，我极力推荐，它是一份很好的……我想它现在还在，依然还在。在理解“原来很多事情是这么回事”方面，它是一份非常值得一读的资料。就代码的组织方式而言，缺乏更恰当的词来形容，我们的一切都极其面向过程。嗯，我们大概有 API 入口点，类似 chat.lo 之类的，对吧？然后就像是：好的，这是 API，而这就是该 API 的全部代码，里面带有一些辅助函数。有极其大量的函数长达很多、很多、很多、很多行，但就是把原生的 SQL 查询直接嵌入在代码内部。在这个世界里 ORM 根本不存在。呃，随便你怎么称呼……

<details><summary>Original English</summary>
>> Yes, I highly recommend it's it's a good I I I think it's still there. It's still there. It's a good it's a good read in terms of like oh this explains so many things. So we had everything was super procedural for lack of of better term in terms of how code was organized. Um we had sort of like API entry points and it was like chat.lo or whatever, right? And it was like okay this is the API and this is all the code for the API with some helper functions in there. There were a wild amount of functions that were like many many many many many lines long but there was just like straight SQL queries like embedded inside the code. like an OM did not exist in this world. Uh whatever you want to call
</details>

>> 你们的数据访问层。我们根本没有这层，而且实际上，嗯，关于我们是否应该做任何事情来隐藏 SQL 查询，当时存在非常多的意见。是的，我现在完全能理解他们为什么持那种立场，以及为什么我们最终采取了那种极其最小化的方案，因为编写一个会一次又一次、反复搬起石头砸自己脚的 SQL 查询实在是太容易了，除非你被迫去真正理解它在被调用的上下文中具体做了什么。但当时我们有四百多个调用点去调用这些频道相关的表……

<details><summary>Original English</summary>
>> your data access layer. We did not have one and there were actually um there was a lot of opinions about whether we should even do anything to hide the SQL queries and yeah now I mean I totally understand why why they had that stance and why we did the super minimal approach that we ended up doing because it is so easy to write a SQL query that will like shoot you in the foot over and over and over again unless you're forced to actually understand what it does in the context that is being called. But we had like 400 something call sites that called into any number of these channels
</details>

>> 大多数调用点（mosaic call sites）。这些就是代码里的 SQL 指令，

<details><summary>Original English</summary>
>> mosaic call sites. These are SQL instructions in the code
</details>

>> 就类似 `select * from teams channels where user_id = ...`。

<details><summary>Original English</summary>
>> just like select star from teams channels where user ID blank.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 比如 `where team_id = ... and user_id = ...`。于是你就直接复制粘贴既有的模式。没错，迁移中总是存在这个问题：你必须极其明确地表明“这是旧模式，别再这样做了”，因为在迁移进行期间，代码库里依然存在大量这样的现成范例。所以我必须写一些……一开始我是通过某种正则表达式的方法去遍历，找出所有进行此类查询的地方。值得庆幸的是，表名非常容易查找和识别。在这点上运气非常好。然后我就是一对一地把调用取出来，直接粘贴到另一个文件里。是的。

<details><summary>Original English</summary>
>> Where team ID blank user ID blank. And so you just copy paste the pattern that exists. Right. That's always the problem with migrations is like you have to make it so clear that like this is the old pattern. Stop doing this because there is still while it's going on so many examples of it in the code. So I had to write some I started off by going through doing some kind of regex approach where I was finding all the places that we were quering for this. Thankfully the table names were like pretty easy to find and identify. Got very lucky there. And then I just one for one took the call and just pasted it into another file. Yep.
</details>

>> 这就是我做的全部事情。

<details><summary>Original English</summary>
>> That is all I did.
</details>

>> 你创建了一个做同样事情的层。是的，

<details><summary>Original English</summary>
>> You created a layer that did the same thing. Yeah,
</details>

>> 基本上就是一个类。

<details><summary>Original English</summary>
>> just a class basically.
</details>

>> 是的，我没有做任何优化。我真的是纯粹复制粘贴，现在我是在调用一个函数，而不是直接调用 SQL。

<details><summary>Original English</summary>
>> Yeah, I didn't optimize anything. I literally just copy pasted and now I was calling into a function instead of straight up calling SQL.
</details>

>> 你可以说是构建了一个最小抽象层。

<details><summary>Original English</summary>
>> And you had a minimal abstraction layer if you will.
</details>

### 双写、影子读取与切换上线

>> 是的。这在当时就已经算有点激进了。嗯，但我尽量确保函数名非常极其清楚地表达它在做什么。嗯，我也让那些态度更激进的人接受了这种做法。所以我觉得那算是一次胜利。于是，我把所有东西都迁移了过去。所有东西都用特性开关（feature flag）控制着。基本上，我都不记得在某个节点上一共有多少个特性开关了，但我做了非常多个独立的开关，只为了确保自己尽可能谨慎地去推进。

即便如此，你懂的，我一路上肯定还是搞砸过一些事情。在某次我认为我们基本上已经搞定、准备好开始切换到生产流量时，我不小心……我已经跑完了所有的历史数据回填（backfills），因为很显然我是在把所有东西迁移到一个新表里。我当时正在做——我们有很长一段时间都在做双写（double writes），以确保各处的数据都能保持最新。

<details><summary>Original English</summary>
>> Yeah. Which already was like a little bit spicy. Um, but I tried to make sure that like the function name was like real darn clear as to what it was doing. Um, and I got the spicier folks to be okay with this approach. So, I felt that felt like a win. And so, I migrated everything over. Everything was feature flagged. Basically, I had I don't know how many feature flags at some point, but I had so many distinct ones just to make sure that I was doing it as carefully as humanly possible. Even then, you know, I still like definitely borked some things along the way. I accidentally when I thought that we were basically there and ready to start flipping on to prod traffic. I'd run all the back fills because obviously like I was moving everything to a new table. I was doing um we were doing uh double rights for a very long time to go places to make sure the data will be up to date.
</details>

>> 是的。所以我们就是从那里开始的。我们开始做双写，确保一切看起来都合理。我也在做——还做了影子操作（shadowing）。

<details><summary>Original English</summary>
>> Yes. So that's where we started. We started doing double rights making sure that that all looked sensible. I was doing a also do also do shadowing.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 影子操作的意思是，你知道的，比如你在正常执行当前操作的同时执行新操作，并对比结果是否一致，对吧？

<details><summary>Original English</summary>
>> The shadowing meaning that you're you know like you're doing whatever you're doing and you're doing a new operation and comparing that is the same result, right?
</details>

>> 对。对。我们也做了大量的这种比对。嗯，但显然我们得先确保所有数据都在那里。所以我们做了双写，完成了所有的回填。嗯，接着我们进行影子读取，对比是否存在差异，显然会扔掉新的调用、新的结果，嗯，并继续从旧表中读取。我当时正准备把整个 Slack 全部切换为从新表中读取，

<details><summary>Original English</summary>
>> Yeah. Yeah. We did a bunch of that as well. Um but obviously we had to you know make sure all the data was there first. So we like did the double writing did all the back fills. Um and then we were shadow reading and comparing if there were any differences throwing away the new uh the new call obviously the new results and um and keeping reading from the old ones. I was about to flip all of Slack to reading from the new table,
</details>

>> 而在那个节点上，你已经确认过它是可行的。所以那本该是一个低风险的变更。

<details><summary>Original English</summary>
>> which at this point you confirmed worked. So that should have been a low rest change.
</details>

>> 是的。对。对。所有数据看起来都是对的。我有一堆数据仓库仪表盘，向我展示在合理范围内两套表之间存在多少差异。然后，呃，接着我正准备把它对，嗯，对整个 Slack 开启。那大概是一个周四，当时我们还有 gather hour（欢聚时光），类似下班后的时间，如果大家想去的话都可以去聚一聚，吃点开胃菜什么的。然后我把它开启了，接着我意识到，噢等等，不对，有些地方不太对劲。嗯，而且……

<details><summary>Original English</summary>
>> Yes. Yeah. Yeah. All the data looked right. I had a bunch of data warehouse dashboards that showed me how many differences existed between the two sets of tables within reason. And uh and then I was about to turn it on to um to all of Slack. This was like Thursdays back when we had gather hour, which was like after after work hours, everyone would sort of hang out if they wanted, have appetizers, whatever. And I turned it on and then I realized, oh wait, no, something's not quite right. Um, and
</details>

>> 噢，而且当时我们并不是只做灰度逐步放量，因为对于这类事情，你其实做不了灰度逐步……

<details><summary>Original English</summary>
>> oh, and then we didn't just do a gradual roll out cuz with these things, you don't really do a gradual roll
</details>

<!-- chunk 4/10 -->

出来。

<details>
<summary>Original English</summary>
 out.
</details>

>> 在公司内部，我们当时规模其实没有那么大。大家都在参加 gather hour，你知道的。我心想：“噢，这看起来很安全。我们一直在做影子读取（shadow reading）。没问题的。”对，我就把它打开了。接着我发现：“噢，数据好像……有些数据好像不太对劲。”呃，而我之前已经非常习惯去……基本上就是运行那个脚本，把所有底层支撑数据删掉然后重新跑回填（backfill），或者至少跑其中的一部分，因为我之前一直看到有差异；说实话，直接把数据清空再重新回填，比试图去准确定位并用手术刀式的手法修复那些调用点要容易得多。所以，我忘了那个 flag 对所有人还是开启状态，然后我紧接着就删除了——

<details>
<summary>Original English</summary>
>> Internally, we were like not that big at the time. Everyone was at gather hour, you know. I was like, "Oh, this seems safe. We've been shadow reading. It's fine. Yeah, I turned it on. I was like, "Oh, there's like data isn't there's some data that's like not quite right." Um, and I had been in so used to uh essentially like running the script that like would delete all of the backing data and rerun the back fill or at least chunks of it because I'd been seeing discrepancies and honestly it was so much easier to just nuke the data rebackfill than it was to try to like pinpoint and like scalpels fix the the call sites. So, I forgot that the flag was still on to everyone and then I promptly deleted
</details>

>> 当时开着的是哪个 flag？

<details>
<summary>Original English</summary>
>> which flag was on
</details>

>> 呃，就是让所有人从新表中读取自己频道成员关系的那个 flag。

<details>
<summary>Original English</summary>
>> uh the flag to have everyone read their channel memberships from the new table.
</details>

>> 好的。

<details>
<summary>Original English</summary>
>> Okay.
</details>

>> 对，我忘了它是对 Slack 全员开启的。不是对外部所有人，只是我们内部；我当时想：“噢，有些差异。”噢，好吧，但我把那些修好了。让我直接清空我们团队的表然后做回填吧。这回填大概花了 25 分钟才搞定。那可不是——

<details>
<summary>Original English</summary>
>> Yeah, I forgot that it was on for Slack. Not everyone externally, like just us and I was like, "Oh, there's some discrepancies." Oh, right. But I fixed those. Let me just nuke the table for our team and backfill. Which like took 25 minutes to do. Like it was not
</details>

>> 噢，但在那之前大家都看不到自己的消息了吗？

<details>
<summary>Original English</summary>
>> Oh, but did everyone lose their messages until then?
</details>

>> 噢，是的。大约有半个小时的时间，所有人的侧边栏完全是一片空白，在整个 Slack 内部都是这样。而且 Slack 显然什么事都用 Slack——

<details>
<summary>Original English</summary>
>> Oh, yeah. People had completely blank sidebars for about half an hour inside of all of Slack. So, like and Slack obviously uses Slack for everything
</details>

>> 什么都用它。

<details>
<summary>Original English</summary>
>> for everything.
</details>

>> 但当时大家都在 Gather Hour。所以只有一个人——就是 Kevin，他之前一直在类似指导、协助我做这件事——他给我发私信说：“我的侧边栏怎么回事？”我当时就说：“实在太抱歉了。我的天哪。我马上切回 flag。”于是在回填期间，我又重新把 flag 切回从旧数据读取。等回填完成后，我才把它切回去。

<details>
<summary>Original English</summary>
But everyone was at Gather Hour. So, it like it was only there was this only one guy, Kevin, who had been sort of like help helping me like coach through this who DM'd me and he was like, "What's going on with my sidebar?" And I was like, "I'm so sorry. Oh my gosh. Let me flip the flag." So I reflipped to read from the old data um while it was backfilling. It finished back filling and then I swapped it back.
</details>

### 负载测试与惊群效应

>> 那么你在 Slack 学到了哪些关于负载测试的经验？我之所以问这个，是因为现在所有系统上的负载都在上升。我们看到 AI 智能体生成了更多拉取请求、更多代码，它们给系统带来了更大负载。我推测我们到处生成更多数据的时刻迟早会到来。但在 Slack，你曾遇到过这样一个有趣的挑战：一个拥有 500,000 名用户的客户想接入这个平台。Slack 当时正在为此做架构设计，原本有一个 18 个月的计划，接着疫情发生了，你们不得不把进度大幅提前。但我更感兴趣的是，你为此构建了一个名为 koi pond 的负载测试系统。不过当你考虑通过负载测试在流量真正来临前检验服务将如何应对这种负载时，你用过哪些技术，并且今天仍然会使用哪些技术？

<details>
<summary>Original English</summary>
>> So what did you learn at Slack about load testing? And I'm asking because right now load is going up on all systems. We see this B AI agents generate more poll requests uh more code uh they put more load on the systems. I assume we will have the point where we generate more data here and there. But at Slack, you you had this interesting challenge where a customer with 500,000 users wanted to go onto the platform. Slack was architecting for it and you had a plan of 18 months and then co happened and you had to bring it up forward. But I I'm more interested in as you you built load testing of something called koi pond on this. But when you think of load testing of checking how a service will be able to handle this type of load before it hits what are the techniques that you've used and would still use today
</details>

>> 在生产环境中测试。

<details>
<summary>Original English</summary>
>> test in production
</details>

>> 但当你在生产环境中根本还没有那种负载的时候，你要怎么做测试呢，对吧？

<details>
<summary>Original English</summary>
>> but how do you test in production something where you don't have the load just yet right
</details>

>> 对，不，我是说，我认为有很多不同的做法。我觉得很多人能够做到的最简单方式，取决于你对产品的哪类使用情况感到担忧，先敲定这些使用模式，以及你真正担心它会在哪里崩溃，这是决定你如何摸索模拟负载的关键因素。

<details>
<summary>Original English</summary>
>> yeah no I mean I think there's a lot of different ways to do it the simplest way that I think a lot of people can manage to do it it depends on what kind of usage you are worried about with your product um and nailing down those usage patterns first and where you're really concerned it's going to fall over is the determining factor in how you figure out how to simulate load
</details>

>> 具体到 Slack 而言，当时的用户模式是什么样的？

<details>
<summary>Original English</summary>
>> in Slack specifically what was user pattern
</details>

>> 历史上它崩溃过几处关键场景。其一是惊群效应（thundering herds）。我是说，我想大多数人在某个阶段都会遇到某种惊群问题，在那种情况下你——

<details>
<summary>Original English</summary>
>> there were a couple couple key ways that it had historically fallen over thundering herds where I mean I think most people have some kind of thundering herd problem at some point where you
</details>

>> 我们能不能具体解释一下什么是惊群效应，给那些遇到过——

<details>
<summary>Original English</summary>
>> can we spell out what the thundering herd is just for those who have
</details>

>> 突然一下子全都涌过来，突然所有人都出现了。突然之间……这就是惊群效应。某件事发生了，然后突然之间所有人都在同一时间出现，做同一件事。

<details>
<summary>Original English</summary>
suddenly herd suddenly everyone shows up. Suddenly like that that is a thundering herd. A thing happens and then suddenly everyone shows up and does the same thing at the same time.
</details>

>> 我想一个很好的例子就是，如果你的服务挂掉了，比如你运行着……我不知道，比方说虚构的类似谷歌搜索这样的服务，不知怎么的你的所有机器因为一个 bug 都挂了，然后你有……比方说一千台机器。显然谷歌有更多，但我们只要想象一下。然后你开始启动机器一、机器二、机器三，但它们每一台都承受了全部流量的冲击，然后再次宕机，对吧？

<details>
<summary>Original English</summary>
>> I guess a good example is if if your service goes down like you're I don't know you're running let's say imaginary like Google search and somehow like your all your machines die for a bug and then you you have like I don't know a thousand machines. Obviously Google has more but we can just imagine. And then you start to bring up machine one, machine two, machine three, but each of them gets hit by the complete traffic and they go down again, right?
</details>

>> 是的。是的。

<details>
<summary>Original English</summary>
>> Yes. Yes.
</details>

>> 这就是一个经典例子。

<details>
<summary>Original English</summary>
>> Like this is a classic example.
</details>

>> 对。对。在 Slack 的经典例子就是，假设 CEO 说：“噢，各位，这个季度干得漂亮。周五大家都放假。”在拥有大概 100,000 名活跃用户的大型全员频道里发布了这条消息。那条通知推送了出去。你看到了那条通知。你非常想在这条通知上砸一个很棒的自定义表情。你点击了那条通知，瞬间进入了频道。在频道里，你在拉取频道历史记录，在此之上，你还在添加表情回应，因为放周五假让你非常激动；但其他人也一样，他们也在那条消息上添加自定义表情，因为他们也——

<details>
<summary>Original English</summary>
>> Yeah. Yeah. The classic example in Slack is say CEO says, "Oh, great quarter everyone. You all get Friday off." Posts this message in the big company channel that has like 100,000 active users in it. That notification gets sent out. You see that notification. you are very motivated to plop a really good custom emoji on that notification. You click that notification, you immediately land in the channel. In the channel, you're fetching channel history and then on top of that, you are adding an emoji reaction because you're really pumped about getting Friday off, but so is everyone else also getting putting custom emojis on that message because they're also
</details>

>> 都在同样的 5 秒钟内。

<details>
<summary>Original English</summary>
>> in the same 5 seconds.
</details>

>> 都在同样的 5 秒钟内。所以通知你周五放假的那条消息，是通过 WebSocket 连接发送过来的，并扇出（fan out）给了所有 100,000 名活跃用户。但是随后所有这 100,000 人在几秒之内都涌入那个频道，发起一次频道读取，紧接着又都在发送表情回应，每一个表情回应也同样通过 WebSocket 扇出。因此，一个自定义表情就变成了向每一个在线连接者发送 100,000 个自定义表情。如果你再加 10 个，好吧，你可以算一下这笔账，它就会这样像滚雪球一样不断膨胀、膨胀、再膨胀。这就是纯粹爆炸式增长的绝佳例子。

而且，尽管我……而且我认为我们之前已经做了一些工作，因为我们知道表情符号的扇出实际上非常消耗资源，所以我们对通过 WebSocket 发送的消息类型按重要性进行了优先级排序。因此，像真正的文本消息是最重要的，而在超高负载的情况下，表情符号就会直接被丢弃忽略，显然这才是该采取的做法。虽然很遗憾，但下一代人，我不知道是 Z 世代还是哪一代，可能会不同意，认为表情符号比文本消息更重要。

<details>
<summary>Original English</summary>
>> In the same 5 seconds. So the message that came in to tell you that you're getting Friday off came in over the websocket connection and it was fanned out to all 100,000 active users. But then all 100,000 within a couple seconds, right, of those people show up to that channel, issue a channel read and then are sending emoji reactions, every single emoji reaction fans out also over the websocket. So, one custom emoji turns into a 100,000 custom emojis being sent to everyone who's connected. And if you add 10, well, then you can do the math and it just like balloons and balloons and balloons. It's like prime example for like pure explosion. And um as much as I and I think we we had done some work because we knew that emoji fan out was like actually really expensive to rate the importance priority order the types of messages that get sent over the websocket. And so like me like actual text messages were the most important and then emojis if you were in a very high load situation would just get dropped on the floor which like is the thing to do obviously. I'm sorry to say, but the next generation, I'm not sure if Jenzi or Jan might disagree that emojis are more important than text messages.
</details>

>> 我必须知道有没有人回应了我的消息。呃——

<details>
<summary>Original English</summary>
>> I need to know if someone reacted to my message. Um,
</details>

>> 不，但我明白，做优先级排序是有道理的——

<details>
<summary>Original English</summary>
>> no, but but I hear it makes sense on prioritizing
</details>

>> 尤其是根据大小来排，对吧？

<details>
<summary>Original English</summary>
>> especially based on size, right?
</details>

>> 是的，完全没错。这其中包含着一定程度的……这就是我认为产品思维所在的地方：你不能只站在纯工程视角去考虑做负载测试。你必须戴上产品经理的帽子。你绝对必须这么做，因为正是在这种时候，理解带有文本的消息比表情符号更重要，这更多是一个产品决策，而不是工程决策。我来找你说：“我们必须丢弃一些东西。让我们一起推演一下丢弃什么才合理。”去理解……有时候情况并不是你预想的那样。我想……我是说，我反复回到这个例子，是因为我曾就此与 Slack 的同事进行过多次讨论：我们应该直接限制一条消息上允许添加的表情符号总数，就这么简单。所以，我们目前限制——或者我想上次我查阅时，Slack 目前依然限制——一条消息上最多只能有 23 个不同的自定义表情作为回应，但在这些表情上你可以随意添加任意数量的点赞同议（+1）。

为什么？第一万零一个表情符号根本无关紧要。我们本应该在某个阈值就直接截断。而且我认为，如果不管谁……我是说，我认为部分问题在于，根本没有人真正负责自定义表情符号业务。我猜本来应该由消息团队负责，但它是属于那种在 Slack 体验中无处不在——这是不是一个词？——并且有点无人认领的东西。那么，究竟该由谁来拍板决定合理的上限是多少呢？但惊群效应绝对是当时大家高度关注的核心问题之一。

<details>
<summary>Original English</summary>
>> Yes, absolutely. And there's some amount of and this is where like I think product thinking is you can't go around thinking you're going to load test strictly from an engineering perspective. You have to be putting your product hat on. You absolutely have to because that's where understanding that like messages with text are more important than emojis. That's more of a product call than it is like an engineering call. I'm coming to you and I'm saying like we have to drop something. Let's reason together about what makes sense to drop. Um and understanding and sometimes it's like not what you would expect. And I think I I mean I I this example I keep coming back to because I had multiple conversations with folks over at Slack about it like we should just limit the total number of emojis that are allowed on a message period. So, we currently limit or I think last I checked Slack still currently limits. You can only have 23 distinct custom emojis as a reaction on a message, but you can have as many like plus ones on those emojis as you would like. Why? The 10,000 and ones emoji does not matter. We should just cut it off at some point. And I think like if whoever I mean I think part of the problem is like no one really owned custom emojis. it would have been the messaging team I guess but like it's one of those things that's just so ubiquitous is that is that a word to the Slack experience and like kind of no one knows it. Um so who would have made the call on like what is the proper limit to put on this? But Thundering Herds was definitely super top of mind as one of those issues.
</details>

>> 我想问一下，事件洪水（event floods）和惊群效应是同一回事吗？

<details>
<summary>Original English</summary>
>> I wanted to ask are event floods and Thundering the same thing?
</details>

>> 不，它们是不一样的。

<details>
<summary>Original English</summary>
>> No, they're different.
</details>

>> 事件洪水是什么？事件洪水是指当你的客户端本身被 WebSocket 连接上传来的事件压垮的情况。所以任何……我是说，在那特定的例子里，可能既算某种惊群效应，同时也可能算是一次事件洪水事件，因为你在事后同样被大量的表情回应疯狂轰炸。不过事件洪水……假设你知道这条消息正在发出，CEO 发了“你们周五放假”，但它是——

<details>
<summary>Original English</summary>
>> What What are event floods? So event floods are when your client is personally overwhelmed by the events coming over the websocket connection. And so any I mean that could be from that specific example that's sort of a thundering herd and maybe an event flood event in that you're getting hammered with emoji reactions after the fact as well. Um but an event flood is uh just say you know this message is happening the co you get Friday off but it's
</details>

<!-- chunk 5/10 -->

### 事件泛洪与超级用户的困境

同时发生在你碰巧所在的 16 个不同频道里。并不是其他所有人都在超级超级繁忙的频道里，但也许你碰巧在。这种事曾经发生在——IBM 当时有位可以说是负责 Slack 的主要负责人，他叫 Jeff Robkkey。他后来成了 Slack 的产品经理，我觉得这是有史以来最耐人寻味的事，因为这家伙曾经承受过无数次的事件泛洪（event floods），我一直都特别同情 Jeff。我是说，我当时在某些频道里，心里都在想“替我跟 Jeff 说声对不起”。

<details>
<summary>Original English</summary>
happening in 16 different channels at the same time that you personally happen to be in not everyone else is in super super busy channels but maybe you happen to be this happened to there was this guy who was our like main Slack Slack guy at IBM his name is Jeff Robkkey he eventually became a PM at Slack which I think is like the most interesting thing ever because this guy was on the receiving end of so many event floods and I felt so bad for Jeff all the time. I mean I was in some channels I'm like I'm like tell Jeff I'm sorry
</details>

>> 但我……我还是没完全搞懂事件泛洪的具体体验是什么样的。你能跟我讲讲到底是什么样的吗？

<details>
<summary>Original English</summary>
>> but I I I still don't fully get like what the event flood experience is. Can you tell me like what what
</details>

>> 会发生在他身上的情况之一，对吧，就是在进行某些架构重构之前，当时并不是针对你登录的每个团队没有一堆独立的 WebSocket 连接。Jeff 当时是 IBM 的管理员。所以他在……

<details>
<summary>Original English</summary>
>> one of the things that would happen to him, right, is that before some of the rearchitecture work whereby you didn't have a bunch of distinct websocket connections for each team that you were logged in. Jeff was an admin at IBM. So he was in
</details>

>> 数百个不同的工作区。

<details>
<summary>Original English</summary>
>> hundreds of different workspaces.
</details>

>> 有一段时间，我认为能同时登录的最大工作区数量大概在 30 多个左右。你是说他在这么多工作区里，是因为 IBM 作为一家大企业，有类似市场团队、财务团队这种概念，也许他们还有个外部客户团队，而作为管理员，他在所有……

<details>
<summary>Original English</summary>
>> At one point I think the maximum number of workspaces you could be logged into was around like 30 something. And and you're saying he was in this because IBM as an enterprise had this this concept of like the marketing team, the finance team, the thing maybe they had an external customer team and as the admin he was in all of
</details>

>> 他在所有的工作区里，他们有非常多的团队，而他在每一个团队里。所以，如果你在一条企业级私聊（DM）或者一个在当前登录的全部 30 个工作区之间共享的频道中收到消息，那么他就会收到该消息 30 次。对此完全没有任何去重机制。

<details>
<summary>Original English</summary>
>> he was in all of them and they had so many teams and he was in all of them. And so if you were getting a message in an enterprise level DM or a channel that is shared across all 30 of those workspaces that he was currently logged into. Well, he would get that message 30 times. There was no dduplication of that whatsoever.
</details>

>> 所以他的客户端、他的机器以及他的通知全都会被压垮，处理负载方面可能稍轻一点，倒还好；但从 UI 层面，从完全看不清发生了什么的恼人程度来看，真是崩溃。

<details>
<summary>Original English</summary>
>> So his client, his machine, his notifications would be both overwhelmed from maybe a little bit less in processing. That's fine. But like from a UI, from a from a being unable to to see what's going on, anno annoyance point of view.
</details>

>> 是的。我是说，他的客户端当时也总是崩溃。

<details>
<summary>Original English</summary>
>> Yeah. I mean, also his client was just dying all the time.
</details>

>> 这确实很糟糕。

<details>
<summary>Original English</summary>
>> Which was not good.
</details>

>> 是的。

<details>
<summary>Original English</summary>
>> Yeah.
</details>

>> 是的。

<details>
<summary>Original English</summary>
>> Yeah.
</details>

>> 挺有意思的。这还是我第一次听说事件泛洪。

<details>
<summary>Original English</summary>
>> And interesting. Like I this is the first time I've heard about event floods.
</details>

>> 是的。而且这些情况非常因人而异。不过对超级用户来说尤其痛苦。这种情况经常发生在超级用户身上。而超级用户往往又是 Slack 最坚定的支持者。所以这是一把双刃剑，一方面是“很抱歉你碰到了我们产品中最差劲的体验”，但另一方面是“我想你依然热爱它，并试图确保大家更多地去采纳它”。这真的非常艰难。

<details>
<summary>Original English</summary>
>> Yeah. And and they were very user specific. Um but they were particularly painful for power users. This happened to power users all the time. and power users were also some of the like biggest champions of Slack. And so it's a double-edged sword of like I'm sorry you get the absolute worst experience of our product, but also you love it, I guess, and you are trying to like make sure that people adopt it more. It's really really rough.
</details>

### 赞助商播报：Entire 与 Turbopuffer

>> Mo 刚才提到，Slack 使用最重度的人遭遇了最严重的事件泛洪。如今，Git 最重度的使用者碰巧是经常并行推送代码的智能体（agents），这就引出了我们本季度的赞助商 Entire。几周前，我告诉过大家 Entire 正在构建一个 Git 托管平台（Git forge）。现在，它终于上线了。你现在可以直接在美国、欧洲、印度和澳大利亚将私有仓库托管在 Entire 上，并且 Entire 刚刚针对智能体时代彻底重构了拉取请求（PR）。PR 的问题在于智能体编写代码的速度远远快于我们任何人审查代码的速度。因此，Entire 用一种叫做“trails”的机制取代了它。一条 trail 将有关工作的所有内容汇总到一处：意图、代码变更以及智能体运行会话。一条 trail 可以跨越多个仓库。这样，对后端和 Web 应用的变更只需审查一次。借助 trail，你可以配置定制化的评估，比如代码审查、安全审查、slot 审查等。它们看起来就像飞机上的平视显示器（HUD），在每次推送时为你的工作打分。你可以看到来自每个智能体的代码如何通过或未通过用户定义的把关门限，然后据此决定何时合并。关键在于由你来控制何时允许智能体合并代码，比如仅在人工审查后或在所有门限通过后才允许合并。哦，还有一件事。Entire 提供了持续记忆（continuous memory）。这会将你的代码仓库变成一个大脑，以便智能体可以搜索过去的编码会话，寻找早期变更背后的上下文。基本上就是解答代码变更背后的“为什么”。记忆会在团队和仓库之间共享。如果你想看看 AI 原生 Git 托管平台是什么样，请访问 entire.io/pragmatic 并了解 trails。

<details>
<summary>Original English</summary>
>> Mo just made the point that the heaviest users of Slack got the worst of the event floods. Today the heaviest users of Git happen to be your agents that often push code in parallel, which brings us to our season sponsor, Entire. A few weeks ago, I told you that Entire was building a Git forge. Well, it's finally here. You can now host private repos directly on Entire in the US, Europe, India, and Australia, and Entire has just reinvented a poll request for the Agentic era. The problem with PRs is how agents write it faster than how any of us can review it. So, Entire just replaced it with something called trails. A trail collects everything about the work in one place. The intent, the code changes, and the agent sessions. A tail can be spread across multiple repos. So the change to your backend and your web app gets reviewed once. With a trail, you can configure customized eval like code review, security reviews, slot reviews, and others. They look like a heads up display on an airplane and score your work on every push. And you can see how each agent from passes or fails your user to find gates and then decide when you merge based on these. The point is that you control when you allow your agents to be allowed to merge code like merging only after human review or after all gates pass. Oh, and one more thing. entire ship continuous memory. This turns your repo into brain so your agents can search past coding sessions to find the context behind earlier changes. Basically answer the why behind the code changes. Memories get shared across the team and across the repo. If you want to see what an AI native git forge looks like, head to entire.io/pragmatic and check out trails.
</details>

我还想提一下我们的特约赞助商 Turbopuffer，他们正在重构其存储引擎，以便在我们在本期节目中讨论的这种规模下，让搜索变得更快、更便宜。这个名为 Turbopuffer V3 的新系统目前尚未在生产环境中上线，但它已经通过了 CI；当重写在 9 月份开始时，它的性能远不如当前的生产版本 V2。Turbopuffer 团队一直在持续极致优化查询计划，直到它们追平甚至超越 V2，所有这些工作在 V3 投入生产之前全都是公开进行的。看到他们的进展真是太酷了。新系统在大多数指标上从最初慢 10 到 100 倍，发展到在冷向量搜索、冷文本搜索或计数等操作上快了好几倍。V3 系统在热全文搜索等领域仍然较慢，但相比极致性能调优开始时的慢 100 倍，现在仅仅慢 1 到 2 倍。Turbopuffer 团队在他们的开发日志中确切分享了他们是如何优化的，涉及诸如向量化查询执行、分组计数聚合、压缩列式编码等技术。不过等等，为什么该团队要进行彻底重写？这是因为搜索正在发生变化，Turbopuffer 也是如此。Turbopuffer 最初是一个向量数据库，但它现在不再只是一个向量数据库了。它已经演进为一个用于搜索的高性能数据库。V3 放弃了向量主索引，所有索引将共享同一套列式存储系统。每个查询都将在向量化查询引擎上运行，这在搜索数据库中并不多见，但这既能带来非常快速的搜索，也能实现整体上极速的数据库。Turbopuffer 团队在为这一历程撰写工作日志。你可以在 turbopuffer.com/v3 跟踪他们的进展。看着它是如何被构建出来的真是一件乐事。

<details>
<summary>Original English</summary>
I'd also like to mention our presenting sponsor Turbopuffer who were rebuilding their storage engine to make search faster and cheaper at the kind of scale we're talking about in this episode. The new system called Turboper V3 is not yet in prod but it already passes CI and when the rewrite started in September it was not nearly as performant as the current production version V2. The Tuff team has been perf maxing query plans until they are as fast or faster than V2 doing all of this in public all the way up to the V3 production launch. And it's so cool to see their progress. The new system went from being 10 to 100 times slower across most metrics to several times faster on things like cold vector search, cold text search or counts. The V3 system is still slower in areas like hot full text search, but only one to two times slower versus 100 times slower when the perfaxing started. And the TUF team is sharing exactly how they optimize things in their development log with things like vectorized query execution, group count aggregation, compressed column encodings, and many more. But hang on, why is the team doing a full rewrite? It's because search is changing and so is turbuffer. T of started as a vector database, but it's no longer a vector DB. It has evolved into a high performance database for search. The V3 discards a vector primary index, and all indexes will share the same colummer storage system. Every query will run on vectorized query engines, which is something that you don't usually see in search databases, but which will both results in very fast search and just generally very fast database. The Turbopuffer team is keeping a worklog of their journey. And you can follow along at turbuffer.com/v3. It's a blast to see how it's being built.
</details>

### 五十万并发连接的压力测试

说到这里，让我们回到 Mo 的话题，聊聊 Slack 是如何为一个预计拥有 50 万用户的客户进行压力测试的。回到压力测试：那么，你们当时是如何模拟在这种情况下预计会承受的负载的？你们知道会有一个拥有 50 万或 100 万用户的大客户要进来。是的，是的。你们不知道 Slack 能否承受得住，但你们想在它们全部进入、在生产环境中测试之前弄清楚。你们构建了定制的压力测试工具吗？你们是怎么做的？

<details>
<summary>Original English</summary>
And with this, let's get back to mode and how Slack load tested for a customer expecting to have 500,000 users. And then back to a load testing. So, how did you simulate the load that you would be expecting to get in this case? You knew that a big customer will be coming with 500,000 or a million users. Yeah. Yeah. And you didn't know if Slack could handle it, but you wanted to figure out before testing in production before they all came in. Did you build a custom load testing tool? How did you go about it?
</details>

>> 是的。嗯，我们此前只有过几种构思不太完善的压力测试方案。大部分只测试了 API 吞吐量，以确保我们能够承受底层负载，主要是在数据库上的负载。因此，如果你在加载一个频道，它会发出一个特定的 API 请求——我记得是 conversations.view，除非他们后来改了——然后这会发出一个特定的数据库请求，呃，在那个频道分片上执行一次 SQL 读取（现在因为所有的线程处理方式不同了有所变化），但它会发出一个特定的请求。我们希望能够……我们想知道自己能够承受那样的 RPS。问题在于，在这个特定时刻之前的所有压力测试解决方案中，没有一个拥有活跃的 WebSocket 连接，而我们刚才讨论的两个具体案例中，WebSocket 在某种程度上正是问题所在。嗯，我是说，我们在通过 WebSocket 发送消息方面从来没有遇到过延迟问题。像那些有状态服务，其中一位联合创始人就像是这一切背后的主谋，他在把它们打造得尽可能高效上投入的时间和精力是令人钦佩的。它们从来都不是真正的瓶颈。瓶颈要么是客户端如何处理它，要么是你看到并接收到该消息所引发的下游已读事件（read downstream event）。那才是进一步的瓶颈。因此，我们需要一个拥有活跃 WebSocket 连接的系统，才能充分测试整个流程。这不仅仅是发送像……

<details>
<summary>Original English</summary>
>> Yeah. Um, so we we'd had a couple of like half conceived load testing options to date. Um, mostly that tested just API throughput and making sure that we could withstand the underlying load primarily on the database. And so if you are loading up a channel that issues a particular API request, I think it's conversations.view unless they last changed it and that makes a particular database request uh a SQL read on on that channel shard now because everything is threaded differently but it makes a particular request. We wanted to be able to we wanted to know that we could handle that RPS. The problem with that is and and any of the load testing solutions before this particular moment in time was none of it had active websocket connections and the two uh particular cases that we just talked about the websocket is the problem in some ways. Um, I mean, we've never really had latency issues with sending messages through the websocket. Like those stateful services have one of the co-founders was like the mastermind behind all of these and like the amount of time and energy he sank into making them as performant as humanly possible is commendable. They were never really a bottleneck. It was either how the client handled it or the red downstream event caused by you seeing and receiving this message. That was the further bottleneck. And so we needed a system that had an active websocket connection in order to be able to adequately test the whole flow. It's not just sending like
</details>

>> API。所以我们确实……而且这也不仅仅是用类似手段去冲击数据库……

<details>
<summary>Original English</summary>
>> API. So we really and it's not just like flooding a database with like
</details>

>> 但是你说需要一个活跃的 WebSocket 连接，为了针对 50 万的负载进行测试，你就需要 50 万个活跃……

<details>
<summary>Original English</summary>
>> but when you say you need an active websocket connection to to test for 500,000 load you need 500,000 active
</details>

>> 50 万个活跃的 WebSocket 连接。是的，我们确实需要。

<details>
<summary>Original English</summary>
>> 500,000 active websocket connections. Yes we did.
</details>

>> 好吧。

<details>
<summary>Original English</summary>
>> Okay.
</details>

>> 是的。是的。这做起来可不容易。所以在这个客户入驻之前，我们曾有套方案，

<details>
<summary>Original English</summary>
>> Yeah. Yeah. Which is not easy to do. And so we had a solution before this this customer came in,
</details>

<!-- chunk 6/10 -->

我现在有 90% 的把握这已经公开了，客户就是亚马逊。但我们当时有一套方案，会在一大堆 Kubernetes pod 里把 Slack 作为无头 Chrome 实例启动起来。
<details>
<summary>Original English</summary>
which I'm 90% sure it's public knowledge now that it's Amazon, but we had a solution that would spin up Slack as a headless Chrome instance in like a bunch of Kubernetes pods.
</details>

>> 嗯。
<details>
<summary>Original English</summary>
>> Mhm.
</details>

>> 然后尝试运行一小段 JavaScript 脚本，去点击按钮，假装成一个 Slack 用户……
<details>
<summary>Original English</summary>
>> And try to run a tiny little JavaScript script um and like click buttons like pretend to be a Slack user
</details>

>> 假装成用户。对。
<details>
<summary>Original English</summary>
>> the user. Yeah.
</details>

>> 这表面上还行。但我不知道你有没有试过在 Kubernetes 里去对付 50,000 多个无头 Chrome 实例……我觉得我们当中没几个人干过，我觉得听众或观众里也没几个人干过……
<details>
<summary>Original English</summary>
>> Which like was sort of fine. Um but I don't know if you've tried to wrangle um more than like 50,000 headless Chrome instances in Kubernet I don't think many of us have I I don't think many people listening or viewing have
</details>

>> 那绝不是什么愉快的经历。我是说，无头 Chrome 实例的问题在于，光是在你笔记本上跑 Slack 和大概 200 个 Chrome 标签页之类的，就已经够呛了。现在你上面还要跑大语言模型。但这真的能把你的笔记本电脑推向极限。而现在你是在每个 pod 里尝试跑差不多 10,000 个 Slack 的无头 Chrome 实例，而 Slack 本身就已经是一个非常吃内存和 CPU、主要是非常吃内存的应用了。我们在……上花的钱，当时我……
<details>
<summary>Original English</summary>
>> it is not a good time. Um I mean the problem with the headless Chrome instance right is like just running Slack and like 200 Chrome tabs and whatever on your laptop is like kind of a time. Um, and now you're running like, you know, LLMs on top of it. But like it's an experience in really pushing your laptop to the limit. And now you're running like per pod like attempting to run like 10,000 headless Chrome instances of Slack, which is already like a very memory and CPU mostly memory intensive um application. the the amount of money we were spending in I was
</details>

>> 关于 EC2 实例。
<details>
<summary>Original English</summary>
>> about EC2 instances
</details>

>> 问题似乎在于，每个节点、每个虚拟机节点取决于规格，你能够跑，大家都知道，跑 10 个、20 个、50 个、100 个，我不知道，你自己去算能跑多少，但你得为你拥有的每一个虚拟机、每一个节点付费，数量有一大堆。
<details>
<summary>Original English</summary>
>> the the problem seems to be that per per node per per VM node depending on the size you will be able to run you know you you you all know like I don't know like 10 20 50 100 I don't know you figure out how much but then you pay for every one of those VMs those nodes you have number of them
</details>

>> 我是说，你看，Slack 融了一大笔风险投资，所以我想……
<details>
<summary>Original English</summary>
>> I mean look like slack slack raised a bunch of VC money so I guess
</details>

>> 当然，当然，是的。
<details>
<summary>Original English</summary>
>> sure sure yeah
</details>

>> 所以我们知道有些钱花到哪儿去了，当然也来自客户。
<details>
<summary>Original English</summary>
>> so we know where some of that went and also from customers of course
</details>

>> 是的，是的，是的，当然。
<details>
<summary>Original English</summary>
>> yeah Yeah. Yeah. Of course.
</details>

>> 那可真是贵得离谱。
<details>
<summary>Original English</summary>
>> That that is wicked expensive.
</details>

>> 确实是。每次 5 小时的压测，每个无头 Chrome 实例合 37 美分。
<details>
<summary>Original English</summary>
>> It is. So it was 37 cents per uh per headless Chrome instance per 5 hour tunch of load testing.
</details>

>> 是啊，单单那一次测试，我们谈的就是 150,000 美元。
<details>
<summary>Original English</summary>
>> Yeah. We're talking about $150,000 for that one test.
</details>

>> 嗯。是的，是的，是的。这就好比说，行吧，这在经济上根本讲不通。我们……它根本行不通。
<details>
<summary>Original English</summary>
>> Mhm. Yeah. Yeah. Yeah. Which like okay, that's like financially not sensible. Like we like it just didn't work.
</details>

>> 但是，不过我想如果你拿它来比较，当然……
<details>
<summary>Original English</summary>
>> But but but I guess if if you compare it like of course
</details>

>> 我来充当一下反方。对，150,000 美元，听起来很多。但如果一个客户带着 500,000 个席位找上门，就算他们拿到折扣，他们每个月也要付 500 万美元。你会觉得投入这笔钱以确保服务对他们管用、让他们不抱怨是有意义的。我不知道这笔账具体怎么算，但是的，单次测试花 150,000 美元感觉依然相当过分。
<details>
<summary>Original English</summary>
>> I'm playing devil's advocate. Yeah, $150,000, great. But if you have a customer coming up with $500,000 seats, if they would get a discount, they they would pay $5 million per month. Like, you would think there is there is a point of investing to make sure that it works for them and they don't complain. I don't know where that comes in, but but yes, the $150,000 still feels like pretty excessive for that one test.
</details>

>> 噢，是的。是的。我觉得就那一次来说，我是说，那仅仅是一段 5 小时的时长，而且这还是假设你能够……对，那只有 5 个小时。
<details>
<summary>Original English</summary>
>> Oh, yeah. Yeah. I think for and for that one, I mean, that's only a five hour chunk of time, and that's assuming that you're able Yeah. That's only five hours.
</details>

>> 好吧，是的，
<details>
<summary>Original English</summary>
>> Okay. Yeah,
</details>

>> 这就成问题了。
<details>
<summary>Original English</summary>
>> that's getting a problem.
</details>

>> 而且这还是假设在那 5 个小时里，你测试了所有你想跑的功能测试，
<details>
<summary>Original English</summary>
>> And you're that's assuming you're testing all of the feature tests that you wanted to run during that 5 hours,
</details>

>> 而事实并非如此。
<details>
<summary>Original English</summary>
>> which was not the case.
</details>

>> 我懂了。事实并非如此，因为我们有一半时间都花在尝试把崩溃的 pod 重新拉起来上。
<details>
<summary>Original English</summary>
>> I get it. That was not the case because we were spending half the time trying to bring pods back up because they were crashing.
</details>

### 轻量级压测替代方案

>> 好吧。你们最终找到更好的办法了吗？
<details>
<summary>Original English</summary>
>> Okay. Did you figure out a better way to do it in the end?
</details>

>> 是的，我们找到了。保真度低一些，但绝对是更好的办法。我们放弃了整个无头 Chrome 实例那一套，虽然如果你想确保真正测出 Slack 的实际运行情况，那显然是保真度最高、最好的选择。但相反，我们启动了一批 Go 轻量进程，每个进程建立一个 WebSocket 连接，并跑完一系列 API 请求，让它们看起来像真正的客户端。嗯。
<details>
<summary>Original English</summary>
>> Yeah, we did. Um, lower fidelity, but definitely a better way. We gave up on the head whole headless Chrome instance situation, which was obviously like the highest fidelity and best option if you wanted to make sure that it was truly testing how Slack would work. Um, but instead we spun up a bunch of little Go processes that would each establish a websocket connection and run through a series of API requests that made it look like they were actual clients. Mhm.
</details>

>> 这样它们依然会通过 WebSocket 接收所有内容，按你预期的那样通过 WebSocket 发送所有内容，并且依然与客户端发起请求的常规 API 保持连接，还有我们的边缘缓存。我们刚才根本没谈到我们的边缘缓存，但是当你启动 Slack 时，有一大堆数据需要极其迅速地加载出来。比如当你要切换频道时，频道列表存在离你更近的边缘缓存里，因为所有主 API 请求依然会打到 US East 1，这固然很好——我是说，如果 US East 1 挂了，我们就彻底完蛋了。所有那些主请求依然会打到 US East 1。所以，我们还必须测试向那些边缘缓存发起请求所产生的延迟。因此，我们也在那里建立了那种请求模式。
<details>
<summary>Original English</summary>
>> Um, and so they would still receive everything over the websocket, send everything over the websocket as you would expect and still have a connection to the regular API that the client was making requests to, and also our edge cache. We didn't talk about our edge cache at all, but there's a bunch of data that needs to be really snappy to load when you load up Slack. like when you go to switch channels, the channel list is um is in an edge cache closer to where you are because all of the main API requests still hit US East1, which is great. I mean, we are so boned if US East one goes down. All of those main requests still hit US East one. So, we still had to also test the latency associated with making requests to um to those edge caches. And so, we also establish that request pattern there.
</details>

>> 是的。在我听来，关于压测，从你这里听到的就是，第一步是理解你的产品会如何被使用、什么东西可能会把它压垮。因为一旦你知道了，你就不会只是胡乱去压测，你实际上可以针对这一点来进行测试；然后在清楚资源限制的情况下，构建出模拟得足够好的东西。所以在这个案例中，不是在无头 Chrome 里启动整个 Slack，而是构建出你关心的那条关键路径，而不是去模拟。如果你把这一点与你的领域知识和专业技能结合起来，了解产品是如何运作的，并且知道它以前是怎么崩掉的，你现在就可以合理地确信，就算它崩了，也不会是以这种方式崩。它可能是以另一种方式，但我觉得我们讨论测试的成本是件好事，尤其是像我们讨论过大语言模型的成本那样，这里有成本考量，还有可重复性，它有多轻量，控制它、甚至调整它有多容易。听起来对于你的方案，如果后来发现另一种失效场景，你完全可以直接针对它重写，这没什么大不了的。
<details>
<summary>Original English</summary>
>> Yeah. It was it sounds to me that with low testing with well all I've heard from you is like you know step one is understand how your product will be used what will likely top it over which because once once you know you're not going to just randomly load test you actually can test target it for that and then building something that simulates it good enough knowing the resource constraints. So in this case, don't boot up a whole Slack in a headless Chrome, but just mock not mock out, but build out that critical path that you care about. And if you combine this to your domain knowledge and your expertise, knowing how the product works and knowing how, you know, you you knew how it used to fall over, you can now be reasonably confident that if it falls over, it will not be this way. It might be a different way, but I think it's nice that we're talking about the cost of of testing, especially like we've talked about the cost of LM, but like there is cost considerations and also repeatability, how lightweight it is, how much easier it is to control it and and to to even tweak it or or it sounds like to your solution, you could you can later if if you find a different failing those case, you can just rewrite it to to that. It's not a big deal.
</details>

>> 是的。是的。它非常轻量。它只做它需要做的事情。我们创建了一个相当……我是说，我们逐步演进出一套系统，你可以创建例程发送给这些假用户，让他们随时间逐步执行。起初它只是一种非常不起眼的 JSON 数据块，类似于调用这个，然后调用那个，再调用那个。我写了一个微型的录制工具，我可以通过 Slack 里的斜杠命令输入类似 /start recording，然后在 Slack 里走完一整套流程。它会录下我发起的所有 API 请求，无论是发给常规 Web 应用后端的还是发给我们边缘缓存的。我会录下每一个发出的和收到的 WebSocket 消息，然后对其进行筛选，只留下我想模拟的部分，接着注入到我写的另一个工具里，将其转换成一段脚本，然后发送给模拟客户端。因为另一半的难关在于弄清楚：当我在产品里走这一个流程时，究竟会调用哪些 API？这可不是个小数目。
<details>
<summary>Original English</summary>
>> Yeah. Yeah. It was really lightweight. Um it just did what it needed to do. We created a a pretty I mean we evolved the system whereby you could create like routines to send to these like fake users to run through over time. At first it was just like a very sort of silly like JSON blob of like call this thing then call this thing then call this thing. I wrote a like mini recorder tool where I could via slash command in Slack say like slash start recording go through a whole flow in Slack. It would record every single API request I made across both to the um normal web app back end and to our edge cache. it would request. I would record every single outgoing and incoming websocket message and then I would sort of sort through it all to just the pieces that I wanted to simulate and then inject that into another tool that I wrote that like turned that into a script that I could then send to the simulated clients because h the other half of the battle was figuring out what are all of the APIs that get called when I do this one product flow which is like not a small number
</details>

>> 你想确保自己抓取到了完整的流程。所以那就是录制工具派上大用场的地方。我们反反复复地使用它。我想再次回到产品这件事上，因为我会不断强调产品的重要性。我认为最优秀的产品经理都会意识到，性能和可靠性是任何给定功能的重要方面，最优秀的 PM 懂得这一点，关心这一点，并为此进行优化。在我留在那里的最后几年里，我一直尝试把更多工具交到 PM 手中，对他们说：“嘿，你想把你的用例加入到用我们压测系统进行的自动化测试中吗？这是录制工具。去把你希望我们测试的流程录下来。把文件发回给我们。我们会把它放进系统里，并按照你希望的频率去运行它。”因为他们知道，比如，“哦，当我们打开一个 Canvas 时，文件会出现这种奇怪的现象，它会这样那样。”而我并不清楚，我使用 Canvas 的方式可能和我们大多数用户不一样。但你清楚，你是 PM。所以去把它录下来，然后交还给我们，我们直接塞进我们写好的系统里就行了。
<details>
<summary>Original English</summary>
and you wanted to be sure that you captured the entire thing. So that that's where the the recorder tool came in came in pretty handy. And we used that over and over and over again. And I would again to go back to the product thing because I'm going to keep hammering the product thing. I think like the best product managers are mindful of like performance and reliability are important aspects of any given feature and the best PMs know that and care about that and optimize for that. And I was trying the last like several years that I was there, I was always trying to push more tools into the hands of PMs and say like, "Hey, you want to add your use case to be automatically tested with Quipond with our load testing system. Here's the recorder tool. Go record the flow that you want us to test. Send us back the file. We'll plop it into the system and we'll run it at the frequency that you want it to run at." because they knew, you know, oh, files do this weird thing when we like pop open a canvas and it like does this thing and like I don't know. I don't use canvases the way that like most of our users probably use them. You do. You're the PM. So like go record it and then bring it back to us and then we'll just shove it into the system we wrote.
</details>

### 从 Slack 到 GitHub

>> 说到可靠性，在离开 Slack 之后，你加入了 GitHub 担任主任软件工程师，那是 2024 年。所以那个时候 GitHub Copilot 已经规模很大了。事实上，Cursor 和其他竞争对手作为工具，已经开始迎头赶上。GitHub 服务的负载已经开始增加，而 GitHub 的……
<details>
<summary>Original English</summary>
>> Speaking of reliability, uh after Slack you joined GitHub as a principal software engineer and this was 2024. So this was at a time where GitHub copilot was already very big. In fact, cursor and other competitors were were already uh as as tools were were starting to get up there. The load on GitHub services already started to increase and GitHub's
</details>

<!-- chunk 7/10 -->

### 加入 GitHub 与数据库分片挑战

稳定性开始肉眼可见地变差，虽然还没像现在这么糟糕。你在 GitHub 内部看到了什么？你能跟我们讲讲你刚加入时的那种氛围吗？比如能不能帮我们理解并体会一下，GitHub 是构建在这个庞大的 Ruby 单体架构之上的，当你加入时它是什么样子的？

<details>
<summary>Original English</summary>
reliability started to visibly become shakier, not as bad as it is uh these days. What did you observe inside of GitHub? Can you tell us like kind of the the vibe when you joined? you like if you can give us a bit of a an understanding and appreciation of of what GitHub has been built on this this massive Ruby monolith and when you joined it what was it like
</details>

>> 那是一个非常有趣的时期，特别是当时我在 The Runway 的一位朋友——真的得追溯到很久以前了——那时已经在 GitHub 待了很多年，我们一直在关注彼此的职业发展。她告诉我：“Mode，我们的空间快用完了。”比如 GitHub 当时主要还在数据中心里，虽然随着时间推移这种比例越来越低。

<details>
<summary>Original English</summary>
>> it was a really interesting time particularly because um one of my friends from the runway actually like we're going we're going way back um had been at GitHub for many years at that point and we'd sort of been keeping tabs on each other's careers and she told me mode we are going to run out of space like GitHub is still primarily on data centers and it's like increasingly less so over time.
</details>

>> 他们以前有自己的数据中心。是的。现在正在迁往 Azure。这是他们公开分享过的信息。

<details>
<summary>Original English</summary>
>> They they used to have their own data centers. Yes. Now they're moving to Azure. This is public information they shared.
</details>

>> 是的。迁移到 Azure 是最核心的任务，但在当时——至少在我们交谈的时候——仍有相当大一部分负载要走数据中心，他们有整个团队在管理那些裸机。她说：“我们快没空间了。空间快用尽了，我们必须想办法迁移到云端——”

<details>
<summary>Original English</summary>
>> Yes. Um yeah, the move to Azure is um front and center but still a significant at least at the time um when we were talking a still significant amount of load was going through the data centers that like they had whole teams managing the metal and she was like we're we're going to run out of space. the space is running out and we either well we both have to figure out how to move to cloud
</details>

>> “同时我们也得想办法精简业务。”因为我们正在做很多蠢事，正如所有人都会做的那样，都是我们不该做的事情。我们完全可以用现有的资源让系统效率大幅提升，从而为我们争取更多缓冲时间。我当时心想，这听起来是个非常有意思的问题，我很乐意来解决。但当时我已经怀孕七个月了。所以最后的情况就是：我入职了，身怀七个月的身孕。如果你能应付得来，这其实是一种非常棒的加入公司的方式，因为你坐在那里，心想：“太爽了，我就提一堆意见，你知道的，都不怎么固执己见，我就把一堆意见抛给别人。接下来的两个月里我什么都不用负责，然后我就去生孩子，之后再回来——”

<details>
<summary>Original English</summary>
>> and we also have to figure out how to do less um because the the we're doing a bunch of dumb stuff as everyone does that we like shouldn't be doing and we can make the system a lot more efficient with what we have to give buy us more runway. Uh I was like this sounds like a very interesting problem. would love to work on this problem. But I was also seven months pregnant at the time. And so what that ended up being was I I showed up. I was seven months pregnant, which is actually kind of if you can swing it, a really great time way to join a company because you are you sit there and you're like, "Cool, I will just drop a bunch of opinions like you know, nothing very strongly held, but I will just drop a bunch of opinions on people. I will own nothing for the next two months and then I'm going to go have a baby and then I'll come back
</details>

>> 看看发生了什么。

<details>
<summary>Original English</summary>
>> and see what happened
</details>

>> 看看发生了什么。在我最初的几个星期里，我差不多就在各个领域四处了解。由于在 Slack 做过很多数据库迁移，有些我们之前没聊到的内容，是从按团队分片的租户模型迁移到使用 Vitess 的更动态的分片模型，结果发现其实并不是，一个团队的分片实在太大了。

<details>
<summary>Original English</summary>
>> and see what happened. And uh and in my first couple weeks I was sort of floating around some spaces and I having done a bunch of database migrations at Slack and some of the stuff that we didn't talk about was but was moving from this like teamsharted tenantbased model to a more dynamically sharded model with vitess where it turns out uh no a team was too big.
</details>

>> 你提到了 Vitess，什么是 Vitess？

<details>
<summary>Original English</summary>
>> So so you mentioned betas what is betas?
</details>

>> Vitess 基本上是构建在 MySQL 之上的一个封装层，它能让你进行更动态的分片，这样你就有了一个——

<details>
<summary>Original English</summary>
Bess is a it's essentially a wrapper on top of my SQL that lets you shard um more dynamically and so you have a
</details>

>> 这样就不再只是让 MySQL 在单个数据库上运行，一旦容量不够用，就只能祝你好运，得手动迁移表或者复制表之类，那简直是噩梦。它能让你在数据增长、容量超限时，我不知道该说是预测，还是它能提供一种方式，更无缝地迁移到多台机器上，并且——

<details>
<summary>Original English</summary>
>> so instead of just having like my SQL run on one database uh and when you outrow it good luck you you manually move the tables or copy them or whatever it's a nightmare it allows you as it grows and as it outgrows it will I don't know predict or it it will now have a way to more seamlessly move over to multiple machines and
</details>

>> 你重新分片、重新分布数据的过程，会比以往任何方式都顺畅得多。而且你也可以更轻松地选择不同的分片键（sharding key）。比如之前在 Slack，所有东西都是按团队分片的。现在依然有按团队分片的数据，对于获取这些数据来说，团队确实是最合理的逻辑单元。

<details>
<summary>Original English</summary>
>> you can reshard redistribute your data uh a lot more seamlessly than than you would be able to otherwise. Um and you can choose different sharding keys more easily as well. And so like before at Slack, everything was charted by team. There's still data that is sharted by team where team is the logical unit that makes the sense makes the most sense for fetching that data.
</details>

>> 但实际上，最小、最合理的单元其实是频道。所以我们最终把大量数据重新分片为通过 channel ID 而不是 team ID 来获取。这样也能实现好得多的水平分片架构。其理念在于，永远不会有任何一个频道大到——也许有一天会，机器人不断在频道里发帖的话没准会有可能——大到关联的数据无法在一个特大型的单一数据库上运行，对吧？

<details>
<summary>Original English</summary>
>> But actually turns out that the smallest most logical unit was channel. And so we ended up re-sharting a bunch of our data to be um fetchable by channel ID rather than by team ID. And then that allows for much better horizontal sharding structure as well. Um and the idea being that there is no channel that will ever be big enough, maybe one day it will be. The bots keep posting in the channels maybe. um that will have enough data associated with it that it can never run on a single ultra large database right
</details>

>> 从扩展性的角度来看，这是一个好得多的单元。所以 Vitess 其实有一部分根基早已植根在 GitHub 中。这非常有意思，因为在 GitHub 面试时，我和很多后来成为同事的主任工程师（principal engineer）聊过，他们当时也在琢磨：好吧，我们有 Vitess，但我觉得我们并没有真正发挥出它的潜力，没有用在它该用的地方。所以他们问了我很多关于我们在 Vitess 上的设置以及做法的问题。事先声明，我从来没有运维过 Vitess，也没有处理过其内部底层机制。我更偏向是一个做产品平台的人。我只是发现：不行，我们不应该再按这个维度来分片了，我们来迁移它吧。这就是我的切入视角，这也基本是他们的视角。

我入职后开始查看 Vitess 的配置，我当时心想：我们这是在干什么？我们在这里到底搞了些什么？我习惯了每个分片键对应成千上万个分片。就拿频道来说，我们有数不清的分片，因为有数不清的频道，你需要把负载均匀分摊到这些分片中。而当我到达时，我看着 Vitess 的配置，当时——我不清楚现在是否仍是这样——整个 GitHub 的所有拉取请求（pull request）和议题（issue）一共只有 16 个分片。

<details>
<summary>Original English</summary>
>> um it's a much better unit from a scaling perspective so vitess has had some of its nency uh embedded in GitHub actually and it was really interesting because when I was interviewing at GitHub uh I spoke with a bunch of the principal engineers that I would later end up working with and they were sort of trying to figure out okay we have the tests but I don't think we are actually using it to its potential to where we should be using it. And so they were asking me a bunch of questions about like our Vest setup and what we were doing. Caveing this with I did not ever operate Vitess um or deal with the internals. I was more of a I'm a product platform person. And so I just like find that like no, we should not be sharding this thing by this thing anymore. Let's migrate it. And so that was my perspective on it, which was also mostly their perspective on it as well. And I came in and I started poking at the vetest setup and I was like, what are we doing? What are we doing here? I was used to thousands of shards per um per sharding key. So say four four channels. We have a bajillion um because there's a bajillion channels and you want to sort of spread load evenly throughout those. And when I arrived, I was looking at the Vitess setup and there was I mean I don't know if this is still the case, but there were 16 shards for all of pull requests and issues
</details>

>> 涵盖整个 GitHub？

<details>
<summary>Original English</summary>
>> across all of GitHub.
</details>

>> 涵盖整个 GitHub，只有 16 个。考虑到我们都知道与整个领域相关联的数据量有多大，这真的少得可怜。我的第一个问题就是：“等等，为什么我们只有 16 个分片？天呐，这让我非常、非常焦虑。”得到的回答部分是：我们没法再增加了，因为我们已经有太多的广播查询（scatter query）了。也就是那些发过来的查询——

是的。

<details>
<summary>Original English</summary>
>> Across all of GitHub, only 16, which is not very many given the amount of data that we know is associated with that whole space. And my first question was like, wait, why do we only have 16 charts? Oh my gosh, this makes me deeply deeply nervous. And part of the answer was, we can't have more because we already have so many scatter queries. So those are queries that are coming in. Yeah,
</details>

>> 什么是广播查询？

<details>
<summary>Original English</summary>
>> what are scatter queries?
</details>

>> 广播查询就是发过来的那些不包含主键的查询。比方说你要查询一个拉取请求或一个议题，而你手里并没有拉取请求 ID，而这恰恰是数据用来进行分布的依据。那么，你就必须去找它。所以你必须遍历、去查找并匹配那些条件。比方说，我要查询所有由我创建的拉取请求。

<details>
<summary>Original English</summary>
>> So those are queries that are coming in where you do not have the primary key in them. So say you are querying for a pull request or an issue and you don't have the poll request ID which is how this data is being um distributed. Well, you have to find it. So you have to go through you have to find and and match the criteria. So say I'm querying for um all poll requests authored by me.
</details>

>> 是的。

<details>
<summary>Original English</summary>
>> Yeah,
</details>

>> 我不知道这算不算法实际的广播查询，但这种情况是有可能的，我们就这么假设吧。由于我没有拉取请求 ID，我就得去命中这 16 个分片里的每一个。

<details>
<summary>Original English</summary>
>> I don't know that that's an actual scatter, but this could be in the scenario. Let's just assume. Um, and so because I don't have a pull request ID, well, I'm going to hit every single one of those 16 shards.
</details>

>> 哇。这在各个层面上都会很糟糕。

<details>
<summary>Original English</summary>
>> Wow. This is this will be bad in so many levels.
</details>

>> 嗯哼。因为有太多人同时在这么做。

<details>
<summary>Original English</summary>
>> Uh-huh. Because Well, so many people are doing it also.
</details>

>> 那我完全能理解你为什么不想有很多分片了，因为如果有更多分片，你就得命中所有分片。我们谈论的这几乎就像线性扫描一样了。

<details>
<summary>Original English</summary>
>> And I understand then why you don't want to have many shards because if you have more shards, you would need to hit all of them. We're talking like it's almost like a linear scan.
</details>

>> 是的。没错。噢不，这效率极其极其低下。再次说明，我不知道这是不是实际案例中的某一个，这完全是假设的，但当时确实存在大量极具分量的广播查询，在确定能够完成查询并返回结果之前，几乎要命中每一个分片。所以，是的，我能理解为什么那在当时成了一种限制。你不想增加更多分片，但反过来，你也无法把分片做得更大，而它们的负载又极重。

因此，我当时准备直接套用过去几年一直用的应对方案：“好吧，那我们直接消除这些广播查询。把广播查询干掉就行了。”

<details>
<summary>Original English</summary>
>> Yeah. Yeah. Oh, no. It's it's it's quite quite quite inefficient. And again, I don't know that this is an actual example of one of the hypothetical. This is completely hypothetical, but there were still very many um significant scatter queries that were hitting almost every single shard before it knew that it could complete the query and return the result. Um which yes, I understand why that was a constraint then. You don't want to add more shards, but then again, you also cannot make the shards much bigger and they're under very heavy load. Um, and so I was ready to like apply the playbook that I'd been using for the last several years of like, well, let's just burn out burn down the scatters. Let's just get rid of the scatter queries.
</details>

>> 别去搞广播查询。

<details>
<summary>Original English</summary>
>> Don't have scatter queries.
</details>

>> 别搞广播查询就行了，这能有多难。事实证明，当你面对的是一个 Rails 单体架构时，这可能会极其困难。是的。

<details>
<summary>Original English</summary>
>> Just don't have scatter queries. That can't be that hard. Well, it turns out that can be very hard. um when you're dealing with a Rails monolith. Yep.
</details>

>> 而且你用的是 ActiveRecord。我以前总觉得挺好笑的，早期的 Slack 有很多来自 Twitter 的前员工，大家都会说：“哈哈，ActiveRecord。”我当时就纳闷：“你们到底在——”就是在他们彻底转去搞 Scala 和 Java 那套东西之前，对吧？我当时想：“好吧，看来大家都在拿 ActiveRecord 开玩笑。”直到我迎面撞上它，我才彻底明白，当时我就觉得：“噢，我真的不喜欢这个，这太糟糕了。”ActiveRecord 是 Rails 对数据库的抽象层，对吧？所以你是在代码里去定义各种东西，并且——

<details>
<summary>Original English</summary>
>> And you've got active record. And I always sort of um thought it was funny the number of there were a lot of ex Twitter folks at Slack early on and everyone was like, "Haha, active record." And I was like, "What are you like before they did the whole like Scola Java thing, right?" And I was like, "Okay, I guess like we're all, you know, joking about active record." I did not understand until I like came face to face with it and I was like, "Oh, I really don't like this. This is really terrible." So act like the record is it's Rails's abstraction layer for the database, right? So you define things in I guess code and
</details>

<!-- chunk 8/10 -->

它能很好地映射到数据库，只不过可能更难对查询等做微调。

<details>
<summary>Original English</summary>
it kind of maps nicely to database except it might be harder to fine-tune your queries, etc.
</details>

>> 对，我是说它确实很擅长把底层数据模型向你隐藏起来，这同样有利有弊。我之前所处的技术圈子里，出于性能考量，SQL 是必须非常虔诚地手写出来的；然后我被扔进了这个世界，有段时间我们正试图弄清楚——当时我们在做一堆关于领域抽离的工作。那么，我们该如何把与 Pull Request 相关的全部内容从 Rails 单体应用中剥离出来，并抽取成一个独立的 Go 子系统？把所有处理 Pull Request 的逻辑抽出来，比如仍然让请求走单体，但随即立刻转发给另一个系统，这是一种非常标准的迁移流程。

<details>
<summary>Original English</summary>
>> Yeah, I mean it it does a very good job at hiding the underlying data model from you, which again pros and cons. I came from a world where like SQL was, you know, religiously written out by hand for performance reasons and then I was being thrown into this world where at one point we were trying to figure out we were doing a bunch of work around domain extraction. And so how do we rip out everything related to say pull requests from the Rails monolith and extract that into a separate Go subsystem? take everything that deals with pull request just like take make the requests go through say the monolith still but then just like immediately send them over to the other system really standard sort of migration procedure
</details>

我们开始着手做这件事，首先从 stars（标星）入手，我想那个项目最终被废弃了。但我当时正在和一个有极其丰富 Rails 经验的人结对编程。我说：行，你得帮我看看，因为作为一个习惯了阅读非常直白、没有那么多层抽象的代码的人，当你踏入一个抽象之上套抽象、层层抽象的世界时，会感到有些畏惧。当时我和她一起尝试把 Rails 单体内部更多与 stars 相关的查询剥离出来。我们找到了生成这条会查询 stars 表的 SQL 的根调用处，那是一个大概只有五行的函数。我在 Zoom 上和她一起看着这段代码，我说：“等等，Kate，调用在哪里？到底是在哪里发出的 SQL？到底发生了什么？这只是个五行的函数。”她说：“Mode，这就是价值百万的大问题了。”我整个人都愣了，我们到底在看什么？发生了什么？因为我原本多多少少还期待能看到……我是说，到目前为止，我想很多人都在用 Prisma，对吧？在 Prisma 里，它虽然不是那种写在引号里的纯 SQL 字符串，但你大致能看懂正在构建的 SQL 查询的结构。而在这里，你根本看不到任何这种痕迹。它看着就像一个普普通通的函数调用。就在那一刻，我意识到：这就是为什么这件事至今根本不可能做成。也是为什么这个问题会恶化到如此严重的地步，因为根本没有人能看到仅仅写下一行新代码会带来什么样的影响。

<details>
<summary>Original English</summary>
we started doing that we started with stars and I think that project was eventually abandoned but I was working I was pairing with someone who had like a ton of Rails experience I was like okay you got to like because I as someone who was so used to reading just code that was very sort of straightforward and didn't have so many levels of of abstraction. I it's a little bit daunting when you're going into a world where now there's abstractions upon abstractions upon abstractions. And I was working with her to try to rip out more of the stars related queries inside of the Rails monolith. We had found sort of the the root caller that created this query that would call into the stars table and it was like a fiveline function and I was looking at it with her on Zoom and I said wait Kate where where is the call like where where is the sequel being made like what is happening it's a fiveline function she's like mode that's the million-dollar question and I was like what are we looking at what is happening because I I half expected to see. I mean, at this point, I think so many people use Prisma, right? And Prisma, you can sort of, it's not, you know, plain SQL written out as a string between quotation marks, but you can sort of see the structure of the SQL query being made. You do not get any of that in this case. It's just it just looks like a regular function call. And in that moment is when I realized this is why this has been impossible to date. And there is because no one had and why the problem has gotten so bad because no one sees the impact of just writing a new line of code
</details>

>> 而且现在要想修复它，可能……

<details>
<summary>Original English</summary>
>> and and also fixing it now will probably
</details>

>> 这绝不是微调一下你的抽象层那么简单。你可能必须去改变代码的书写方式、调用方式，开始更多地去调用那些执行 SQL 的函数等等。这就好比，你采用了一项在你规模很小时效果极佳的技术。只要事情还在线性发展，你就能扩展它，他们也摸索出了随之增长的门道。

<details>
<summary>Original English</summary>
>> it's not as easy as just tweaking your abstraction layer. You would probably have to change how code is being written, being called, starting to call more either functions that call SQ etc. Like it's it's just you took a technology that worked great when you were small. You were able to scale it as long as you and and they figured out how to how to grow it as long as things are going linearly.
</details>

### GitHub 的数据库查询瓶颈

>> 是的。是的。我认为最让我震惊的一件事——既让我对他们至今为止的驾驭能力肃然起敬，同时也让我感到无比恐惧——就是，在 GitHub 内部工作时，你显然拥有 GitHub 的管理员视图，页面顶部会有一条工具栏。你在 GitHub 上加载一个页面，它会确切告诉你渲染该页面运行了哪些 MySQL 查询、命中了哪些集群、各自耗时多久，以及相关的汇总数据。

<details>
<summary>Original English</summary>
>> Yeah. Yeah. And I think one of the things that like blew my mind the most that like both gave me a lot of respect for how they've managed to date um and also filled me with much dread was uh when you work inside of GitHub obviously you have like the admin view of GitHub and there's this bar at the top where you can load up a page on GitHub and it'll tell you exactly which my SQL queries were run to populate the page which clusters they hit um how fast they all were totals around all
</details>

内部员工视图。是的。

<details>
<summary>Original English</summary>
the internal employee view. Yeah.
</details>

>> 是的，没错。还有所谓的“文件消除歧义”（files disambiguate）页面，也就是你访问带 README 的代码仓库首页。

<details>
<summary>Original English</summary>
>> Yeah. Yeah. Yeah. Yeah. And the what's called the files disambiguate page which is sort of like the repo homepage that you land on with the read me.
</details>

>> 那个页面，上次我离职前查看时……

<details>
<summary>Original English</summary>
>> That page last last I checked you know before before I left
</details>

>> 在你大概一年前离职之前。

<details>
<summary>Original English</summary>
>> before you left like a year ago.
</details>

>> 实际上不到一年，但也差不多。是的，这是前一段时间的情况了。渲染那个页面需要超过 100 次 MySQL 查询，跨越至少三个不同的 MySQL 集群。而 ActiveRecord 的机制是，只有当查询完全一致时，它才会自动缓存结果。

<details>
<summary>Original English</summary>
>> Actually less than that but yeah. Yeah. Yeah. This is some some amount of time ago um was it was hundred over a hundred MySQL queries to populate that page across at least three different MySQL clusters. And the thing with active record is that it only caches the output automatically if the query is exactly
</details>

>> 一模一样。所以，比方说你获取用户信息，做了完全无条件覆盖的查询，比如 `SELECT * FROM users WHERE user_id = blank`，你拿到了完整的用户数据；但之后你又执行了 `SELECT * FROM users WHERE user_id = blank AND [其他条件]`，它就不会回过头去取第一次查询缓存下来的结果，因为它们不是完全相同的查询。每一个计数——或者至少在我离开时，你在 GitHub 页面上看到的几乎每一个计数——都是实时计算出来的。这些全都没有做缓存。这背后有诸多原因，其实主要是产品层面的原因。但这是我最初看到的几件事之一，当时我就纳闷：为什么非得这样？再回到我那个有点无厘头的 emoji 例子，比如第 10001 个 emoji，根本没人在乎。为什么会有人在乎呢？对吧？如果你面对的是数量很少的事物，那当然，可能在某个几乎没人去动的极小仓库上显示有 3 个待决的 Pull Request 是挺重要的。但一旦到了 99，就干脆不要显示确切数字了，直接写 99+ 就行，别费劲去数了。我们到底为什么要数这个？

<details>
<summary>Original English</summary>
>> the same. And so if say you're fetching user information like full like blanket like select star from users where user ID equals blank and you have that full user but then later on you do select star from users where user ID equals blank and something else it's not going to reach back into the results that it cached for that first query because they are not exact same queries. every single count or at least when I last left almost every single count on you see on a GitHub page is live calculated. None of those are cached. There's a lot of reasons why that is mostly product reasons actually. Um but I that's one of the first things that I was like but why? And to go back to like my sort of silly emoji example of like the 10,0001 emoji, no one cares. Why does anyone care? Right? And if you have low counts of things, sure, okay, maybe it matters that there's three open pull requests on like this very small repo that like no one really does anything with. But once it gets to like 99, don't just don't show anything. Just say 99 plus. Don't bother counting it. Why are we counting this?
</details>

### AI 工具在性能优化中的局限

>> 挺有意思的，到目前为止我们聊了你在 Slack、在 GitHub 做的那些有意思的事。你之后也做过 Copilot Code Review。在那之后，你又在 Cursor 工作过。他们确实极大地推动了我们使用 AI 工具写代码的方式，但到目前为止我们还没真正聊过 AI。刚才只是没自然聊到那儿。我想首先问问，到目前为止你对 AI 怎么看？你平时显然一直在用这些工具，而且用得越来越深入。在你的工作中，AI 在哪些部分帮不上忙？在哪些部分帮到了你？它改变了你的工作方式吗？

<details>
<summary>Original English</summary>
>> Really interesting that so far we talked about you you did interesting thing at Slack at at GitHub. You also worked at Copilot Code Review. Afterwards, you worked at at Cursor again. uh they've they've really pushed how we're coding with with AI tools, but so far we've not really talked about AI. It just didn't come up naturally. And I wanted to ask firstly, what do you think AI so far? You have you obviously use these tools all the time, increasingly intensively. What parts of the job does AI not help you with and what parts of it has it helped and has it changed how you work?
</details>

>> 天哪。是的。在性能优化方面，它基本上完全帮不上忙。至少在排查分析环节是这样，也许在具体实现阶段能稍微快一点……

<details>
<summary>Original English</summary>
>> Oh gosh. Yeah. Um it has not helped me with performance optimizations basically at all. Um at least the investigation part maybe the implementation part is a little bit faster
</details>

>> 一旦你知道自己想做什么之后。

<details>
<summary>Original English</summary>
>> once you know what you want to do
</details>

>> 但对，要想弄清楚我该做什么。举个例子，几个月前，我在 Cursor 研究如何缩短首字时间（time to first token），也就是首个可见字的时间。这里面有很多因素会影响到你多快能开始收到返回的 token。从你敲入 prompt 并点击提交开始，有相当长的一段时间都花在了为即将向大模型发出的请求构建所有相关上下文上。然后，有部分数据我们能够缓存，部分数据我们无法缓存——这有产品层面的原因、隐私层面的原因，但完全也是出于系统负载以及成本的考量。比方说，把你在 Cursor 查过的所有内容在 Redis 里缓存 24 小时，这可一点都不便宜，成本极其高昂。所以我们不会那么做。接着，最终还要把那个请求发送给推理代理，推理代理再把请求转发给底层的 LLM 和模型提供商，鉴于中间有如此多的环节，还有来回往返。这整个流程的许多部分其实并不像体验上让你感觉的那么同步。在常规流程中，如果你足够幸运能够使用 HTTP/2——有些可怜的人只能被困在 HTTP/1 上——你就会与后端服务器建立起 gRPC 流式连接，并且能够把该连接拆分成 4 条或更多的并发流，在这些流之间收发不同的信息碎片。这非常复杂。

<details>
<summary>Original English</summary>
>> but yeah figuring out what I want to do. So say um I was looking at improving time to first token um time to first visible token at cursor at cursor um a couple of months ago where um and there's a bunch of factors that feed into how fast you start getting those tokens back. There's a significant amount of time that goes into when you are typing your prompt um and you hit submit. there's a significant amount of time that goes into building all of the context associated with the request that you are about to make to send to the LLM. Um, and then there's some amount of data that we are able to cache, some amount that we are not able to cache either for product reasons, privacy reasons, but also strictly because of load and like again cost of these systems. It is not cheap to say cache absolutely everything that you have ever queried cursor for in Reddus for 24 hours. Um that cost a lot of money. So we're not going to do that. Uh and then eventually sending that request over to uh inference proxy which then sends the request over to the underlying LLM and and providers given that there's so much that um happens but also back and forth. A lot of this process is not really as synchronous as the experience leads you to believe. And in the regular flow, if you're lucky enough to be able to use HTP2, which some poor folks out there are stuck on HTP1, you establish that um gRPC streaming connection with the backend servers, and you're able to split that connection into like four or more concurrent streams and send and receive different bits of information across those streams. It's very complicated.
</details>

而且，AI 自以为非常擅长为这些系统做埋点插桩（instrumenting）。其实它们不行。事实证明，它们以为自己——这就像写测试一样。它们觉得自己非常擅长写单元测试，但实际上它们只擅长去确认自己刚刚写出来的东西。

<details>
<summary>Original English</summary>
And also AIS think that they're really good at instrumenting um these systems. They are not. Uh turns out they think they're it's like writing tests. They think they're really good at writing unit tests, but they're really good at just confirming what they just wrote.
</details>

>> 是的。

<details>
<summary>Original English</summary>
>> Yeah.
</details>

>> 这就是为什么我最终精心设计的一些 skill 会对代码跑一系列高强度的变异测试（mutation tests），以此迫使 LLM 意识到：“哦，我其实根本没测试任何边界情况。谢谢你，让我重写一下这些测试吧。”所以我发现，目前的 LLM 擅长做非常基础层面的插桩，但并不擅长去判断——尤其是在异步语境下——去插桩什么才合理、该如何做。我非常喜欢 trace。我认为

<details>
<summary>Original English</summary>
>> Which is why some of the skills that I ended up crafting run through like intensive series of mutation tests on the code to then force the LLM to realize, oh, I didn't actually test any of the edge cases. Let me rewrite those tests. Thank you. So the LMS right now I find are uh good at doing the really basic level of instrumentation but not great at figuring out especially in an asynchronous context what makes sense to instrument how I love traces. I think
</details>

<!-- chunk 9/10 -->

### 链路追踪与性能排查

它们非常棒。你可以从它们那里得到非常多、非常好用的调试信息，尤其是从性能的角度来看。我们在 Cursor 曾遇到过这样一个问题：追踪数据既过多又过少。我这么说的意思是，我们有些 trace 包含数以百万计的 span，这些完全没有用。面对一个包含那么多 span 的 trace，你做不了任何有意义的事。然后我们也犯了一个非常经典的错误，基本上所有人都会犯，那就是我们出于成本考虑开始做采样，但并不是在一个集中的地方做。这同样很容易让 LLM 来做，因为就像是说：“哦，帮我找个地方少发点 trace 来省钱。”它就会说：“好的，那我就在发送到 DataDog 或其他什么系统之前进行采样。”不，不，不。千万不要那样做。请不要那样做。一定要在同一个地方做采样。在处理这个问题时，重复造成的麻烦简直要严重得多。

<details>
<summary>Original English</summary>
they're amazing. You can get so much really good debugging information from them particularly from a per performance perspective. We had this problem at cursor where we had like too many and too little traces. And by that I mean that we had traces with millions upon millions of spans which are completely useless. You cannot do anything meaningful with a trace that has that many spans. And then we also did the um very classic mistake that basically everyone does which is we started sampling for cost reasons but not in one place which is again really easy to have an LLM do because it's like oh like find me a place where we can send fewer traces to save money and it's like cool I'll just like sample it right before I send it to Data Dog or whatever. No, no, no. Don't don't don't do that. Please don't do that. Always do it in the same place. the problem with duplication is just like so much worse when you're dealing with this.
</details>

所以，我最终不得不做的第一件事，老实说，就是手动为很多这类流程添加埋点。然后我自己真正去通读代码，搞明白：好，这一块处理是同步的，那一块处理是异步的，并把所有这些整合到一起。我开始着手做这事的方法之一，就是让它生成一张庞大的时序图，展示影响首字生成时间（time to first token）的所有环节。也就是从你点击提交，到你收到第一个可见 token 的全过程。那张图非常庞大。我去了 Staples，让他们把图打印在大张的蓝图纸上，因为我骨子里还是个非常偏好实体纸质的人。接着我就顺着那张图去通读代码，在我那张大纸上做批注，比如：好，这部分是对的，或者这部分是不对的；这部分我们大概能做些处理；而另一部分，不行，它实际上绝对必须在这另一个环节之前发生。

<details>
<summary>Original English</summary>
Um, and so one of the first things that I ended up having to do was like honestly manually instrument a lot of these flows. Um, and actually read through the code myself and understand, okay, this chunk of uh, processing is synchronous, this chunk of processing is asynchronous, and put all of those together. And one of the ways that I started doing that was I had it generate a like big sequence diagram of everything that goes into time to first token. So like from the time you hit submit to when you receive that first visible token and it was huge. And I went to Staples and I had them printed out on like big blueprint paper because I'm still a really analog person. And then from that I went through and I was reading the code and I was annotating in on my big piece of paper like okay this this is correct or this is incorrect. This piece we could probably do something about this other piece no actually definitely needs to happen before this other piece.
</details>

我发现它所做的另一件错得令人非常痛苦的事是，它在寻找那些可能会……

<details>
<summary>Original English</summary>
One of the other things that I was finding that it was doing um really painfully wrong is that it was finding sort of the classic things that could
</details>

>> 它做错了什么？LLM 做错了什么？

<details>
<summary>Original English</summary>
>> what was doing wrong the LM was doing wrong.
</details>

>> 哦，是的。它做错的地方在于……说“错”其实不太贴切。

<details>
<summary>Original English</summary>
>> Oh yeah. So what it was doing wrong was um finding well wrong is kind of the wrong word. Um
</details>

>> 尽管直抒己见吧，我就喜欢这样。

<details>
<summary>Original English</summary>
>> let's let's be opinionated. I like it.
</details>

>> 等等，它天真地……它天真地做的是：假设你有一堆事情，你找到了一堆互不依赖的任务，对吧？但它们对延迟很敏感。经典的解决方案是什么？

<details>
<summary>Original English</summary>
>> Wait, it naively naively what it was doing was say you have a bunch of things. You're finding a bunch of tasks that don't depend on each other, right? But they're latency sensitive. What's the classic solution?
</details>

>> 把它们并行化。

<details>
<summary>Original English</summary>
>> You paralyze them.
</details>

>> 把它们并行化。然而，还是那句话，换上产品思维的角度，对吧？如果基本上根本没有人会把这四件事全都做一遍呢？

<details>
<summary>Original English</summary>
>> You paralyze them. Um however, again, product hat, right? What if basically no one is ever doing all four of those things?
</details>

>> 那你为什么还要同时执行它们所有人？这样既浪费资源、增加延迟，又在等待，平白无故增加了负载。

<details>
<summary>Original English</summary>
>> And why are you doing all of them at the same time? Like you're wasting resources, latency, you're waiting, you're increasing load for no reason.
</details>

>> 所以我记得，好像是……我想是 Opus，当时非常兴奋地觉得自己发现了把这一堆任务并行化的机会。我当时觉得：“哦，乍一看，确实像是一件该做的好事。”但问题在于，哪怕你把它们并行化了，耗时最长的那个无论如何都始终会是瓶颈。而且耗时最长的那个，总是比其他三个长得多得多。另外那三个任务，只有极少数（比如 1%）的用户会触发其中任何一个。所以到头来这完全是白费力气。这根本不是它向我兜售的那种能够改善首字生成时间的灵丹妙药。而很多真正很有帮助的，反而是些非常不起眼的小事，我是指像在合理范围内尽可能提高我们在 Redis 中存储内容的 TTL 这种小改动。

<details>
<summary>Original English</summary>
>> And so I I remember I think it was I for I think it was Opus that was like very excited that it like found this opportunity to paralyze a bunch of these tasks and I was like, "Oh, like on first glance, sure that seems like a good thing to do." Except that the problem, even if you paralyze them, the longest one is always going to be the bottleneck regardless. And the longest one was always so much longer than the other three. And the other three tasks were being run such a small 1% of users were doing any of the other three. And so it ended up being a complete waste of time. like this was not the optimization that it was like selling to me as being like the panacea to improving time to first token. And a lot of the things that were uh actually quite helpful were really silly things like I mean silly like increasing the TTL on what we stored in Reddus where we could within reason.
</details>

### 人工验证与系统地基

>> 你平时是怎么使用 LLM 的？因为到目前为止，我的感觉是……聊过你的职业生涯后，发现你面对一个问题时，会去审视它、理解它、弄清楚该怎么做，偶尔也会失败或犯错，但你能从中吸取教训，也能向他人学习——包括现在这几年 AI 越来越无处不在的环境下。但在让系统变得更可靠、更具性能的过程中，听起来你依然做了大量的独立思考。我现在的感觉是，你只是把 LLM 当作辅助工具来激发一些想法，判断“不，这是错的”或者“不，那是个好主意，行，那我用上”。但与我聊过的很多软件工程师不同（即便是在这个播客上），

<details>
<summary>Original English</summary>
>> How do you use LMS? Because so far my sense is talking through your career you're you look at a problem you understand it you figure out how to do it you fail sometimes or make mistakes you learn from it you learn from others including right now in the last few years where AI is increasingly everywhere but as you're making systems more reliable more performance it sounds like you're still doing so much thinking so much you're now I sense that you're using the LLM on the side to generate some ideas to say no this is wrong No, that was a good idea. Okay, let me use it. But unlike a lot of software engineers I talk to, even on this podcast,
</details>

>> 确实，

<details>
<summary>Original English</summary>
>> yeah,
</details>

>> 他们大多数人都会说：“哎呀，我过去做的很多工作现在都由 LLM 来完成了。我现在能做更多的事情了。我可以把精力集中在更高层面的工作上。”我从你身上完全没有感觉到这一点。

<details>
<summary>Original English</summary>
>> most of them are saying like, oh, so much of my work that I used to do, the LLM does it. I now can do more things. I can focus on higher. I'm not getting that sense from you.
</details>

>> 是的。我是说，我整天都在以某种形式或方式跟 LLM 交流。我觉得我依然在做很多常规的工程工作，比如我还要轮流值班（on-call），有时就是得去修一个莫名其妙的 bug。不过我确实倾向于用它做大量的初步探索。但随后，我会进行手动验证，

<details>
<summary>Original English</summary>
>> Yeah. I mean, I'm spending all day like chatting with an LLM in some way, shape, or form. I think like I still do a lot of the normal engineering stuff, which is like I'm on call. Sometimes I just have to fix a silly bug. Um, but I do tend to I do a lot of sort of preliminary exploration. Um, but then verification manually
</details>

>> 我也深切体会到了这一点。听起来哪怕你从 LLM 或其他地方得到了什么东西，你都会去验证，你会确保自己弄懂了它是正确的。听起来你并不是预先断定它对还是错，而是你必须要去验证它，对吧？

<details>
<summary>Original English</summary>
>> and I I sense that a lot like it sounds like even when you get something from an LLM or whatever, you will verify, you will make sure that you understand that this is right. It sounds like you don't have a judgment if it's going to be right or wrong, but you need to verify it, right?
</details>

>> 对。对。因为我觉得我所处理的很多问题，更多是属于产品平台类的问题。而这种问题的核心在于从全局出发去解决，打造出一个可以供你在其上添砖加瓦的地基，对吧？而如果你打造的地基只覆盖了这栋房子大概 80% 的面积，那意义何在？因为没建在地基上的另外那 20% 会极其不稳定，并且会殃及你在地基上已经建好的那部分房子。既然你在这里已经这么干了，那实际上就没什么能阻止你在地基之外再去硬拼凑上另外 10%，然后问题就会彻底失控，对吧？所以我觉得，尤其是在当下，AI 非常擅长在各处直接复制东西，因为它觉得这样看起来没问题；但它没有那种追问的意识，它很不擅长去问：“你知道吗，但这究竟是为什么？为什么？在追溯了 20 层之后到底是为什么？”

<details>
<summary>Original English</summary>
>> Yeah. Yeah. Because I think a lot of the problems that I work on are more of the like product platform problems. And the whole point is to solve a problem holistically and to create that foundation that you can build on top of, right? And if you only built the foundation to cover like 80% of the house, like what's the point? because that other 20% that was not built on the foundation is going to be really shaky and impact the rest of the house that you did build on the foundation. And if you already did that over here, well, like nothing's really stopping you from say like tacking on another 10% off past the foundation and then that spiraling, right? And so I think especially especially now that like I think AI is so good at just duplicating things in places because that seems fine and it doesn't have a sense of it's not great at going, you know, but why? But why? But like
</details>

>> 嗯。

<details>
<summary>Original English</summary>
>> Mhm.
</details>

>> 追溯 20 层之后的根本原因。它更倾向于“我就顺手搭上，我就在地基外面再多建一个卫生间好了。这挺好的，对吧？既然你让我再多建一个卫生间，那我就建在这儿了”，而不是去质疑底层的根本假设——即“人到底该不该在没有地基的地方建卫生间？”而这些恰恰是我一直在问自己的问题。我觉得部分原因在于，我是从产品平台的视角来看待这些的。

<details>
<summary>Original English</summary>
>> 20 levels removed. It leans more towards I will just tack on I'll just b build an extra bathroom past the foundation. That's fine, right? Like you asked me to build an extra bathroom. That's where I'm doing it. rather than questioning the underlying fundamental assumptions which are should one build a bathroom not on top of a foundation and those are the questions that I'm asking myself all the time and I think part of it is because I'm coming from a product platform perspective
</details>

### 通往平台工程的路径

>> 我有种感觉，产品平台工作、平台工作、可靠性与性能，只会变得愈发重要，因为还是那句话，我们的系统将承担如此巨大的负载，面临如此多的要求。有人问：“对于一位可能经验丰富也可能没什么经验，但对性能和可靠性感到兴奋、希望最终能更接近并进入平台团队工作的软件工程师，你有什么建议？就你所见，人们是通过哪些途径进入到你工作过的平台团队的？他们是如何实现转型的？”

<details>
<summary>Original English</summary>
>> I have a sense that the product platform work the platform work reliably performance it will only be more important because again we'll have systems that have so much load so so much asked, "What advice would you have for a software engineer uh who may or may not have much experience but who is excited about the idea of performance reliability and would like to get closer to eventually work on on platform teams? What are paths that you've seen people make it onto platform that you worked on? How did they transition?"
</details>

>> 我非常非常支持让更多做业务产品的人——实际上是让做业务产品的人与产品平台团队之间有更多的交流互动。我见过很多次这样的情况：产品平台团队最初是由那些非常注重底层基础的产品工程师组建起来的，对吧？他们本身就非常关注可靠性，他们已经在关注性能了，并且一直试图改善这些，将它们融入到自己构建产品的方式中。然后我认为，与我共事过的最优秀的产品平台工程师，都经历过这样一个节点：他们在作为产品工程师构建功能的过程中，见识过某种模式足够多次，以至于他们会想：“我想深入进去，彻底通盘解决这个问题。比如这个特定的问题，由于已经亲自实现过两遍、三遍、四遍，我理解得非常深了。

<details>
<summary>Original English</summary>
>> I am such a strong advocate for more product folks like more interchange actually between product folks and product platform teams. I've seen it so many times where product platform teams are spun up out of product engineers who care a lot about the fundamentals, right? They care about reliability. They care about performance already. They're trying to improve that and inject that into the way that they are building product all the time. And then I think the best product platform folks that I've worked with get to a point where they've seen a pattern enough times in the things that they are building as product engineers and they're like I want to dig in and solve this problem across the board. Like this specific problem I understand really deeply from having implemented it two, three, four times.
</details>

>> 我想一劳永逸地把它解决掉，彻底搞定，然后做出一个其他人也能使用的成果，对吧？”他们对那些繁杂琐碎的重复劳动感到厌倦，然后他们可能会嵌入到某个产品平台团队中，或者和其他人一起组建一个这样的团队，随后着手去做。很多时候，这些人最终会留在产品平台团队，继续由衷热爱产品平台的工作，但之后他们……

<details>
<summary>Original English</summary>
>> I want to go solve it once and for all and be done and like have this thing that other people can also use, right? They get annoyed with the toil and then they go and maybe embed with a product platform team or they like spin one up with some other folks and then they do that and then a lot of times those folks end up staying on product platform teams and continuing to really like the product platform work but then they
</details>

<!-- chunk 10/10 -->

越来越脱离实际的产品开发感受。我认为在那个阶段，你就会看到产品平台团队和产品团队之间最终产生的某种鸿沟，究其原因就是团队之间缺乏足够的交叉交流。因此，我见过的弥合这种鸿沟的方法之一，就是在这些团队之间建立轮岗机制。比如产品平台团队始终保持有一批核心成员来维护他们搭建的主要系统和平台，但同时也始终有一名来自产品团队的人在产品平台团队轮岗，带来这样的声音：“好吧，我不知道你们在这儿都在忙些什么，但在产品团队那边，我们基本上就是在随性地全天候上线各种 AI 拼凑出的粗制滥造内容，比如你们居然还在做代码审查，这什么情况……”

<details>
<summary>Original English</summary>
get further and further detached from what product development actually feels like. And I think that's where you see uh sort of the chasm that ends up being created between product platform teams and product teams is just there's not enough cross-pollination between the teams. And so one of the ways that I've seen that chasm merge back together is having like rotation cycles between those teams. sort of always having someone on the product platform team having a core set of folks who are like maintaining the main systems and platforms that they've built, but sort of always having someone on rotation from a product team on the product platform team bringing like oh well I don't know what you all are doing here but like on product we're just like yolo shipping all this AI slop all the time like what you're reading your code what um
</details>

>> 这到底是怎么回事，这是真实发生的事，我们在产品团队的代码审查完全正在走向消亡。

<details>
<summary>Original English</summary>
>> what's happening it's a thing it's a thing we on on on product code reviews are are totally dying
</details>

>> 完全不同。但如果你不贴近那种实际情况，你也就不知道该如何把自己的平台支撑到最好，以便让他们能够那样去做。在我看来，在这个世界的当前阶段，我作为一名产品平台人员的角色，就是防护栏必须比以往任何时候都更加完善，因为产品人员需要——我的意思是，“需要”这个词有点重了，但在理想情况下应该能够随心所欲地倒出任何他们想要的东西——

<details>
<summary>Original English</summary>
>> completely different But if you're not close to that, then you also don't know how to bolster your platform to be the best that it can be so that they can do that. I see my role in this, you know, phase of of the world right now as a product platform person to be like the guardrails need to be better than they have ever been before because product people need I mean need is a strong word but should ideally be able to slop out whatever the heck they want
</details>

>> 然后平台应该阻止他们，或者警告他们，或者……

<details>
<summary>Original English</summary>
>> and and the platform should stop them or warn them or
</details>

>> 没错。所以，我是不是可以这样理解：你的建议就像是，如果你今天身处一个产品团队，正在构建产品、向客户和用户交付，显然要理解业务所关心的东西，尝试打造高质量的东西，但也要问问自己，你是否在关注性能和可靠性；如果不是，首先，为什么不？

<details>
<summary>Original English</summary>
>> Yes. So, so do I understand that your suggestion is like look if if you today are on a product team you're building products you're you're shipping to customers to users obviously understand what the business cares about build you know try to build quality stuff but also ask yourself like are you carrying out performance and reliability if not first of all why not
</details>

>> 其次，当你开始关心这些时，如果你正在与平台团队合作，就开始与他们协作、多跟他们接触，看看针对你遇到的这些问题，我能否帮忙构建一个解决方案？如果你有转岗到这个团队的选项，那会非常有帮助。而如果你就在这个团队，试着找到一种稍微像是在跟团队一起实现功能的方式来工作。去理解他们为什么交付得那么快、而且看起来那么随意，因为通过这种双向的方式，看起来我们两者都需要，特别是现在产品团队被要求交付得快得多——顺便说一句，他们确实交付得更快了，而且出现了各种新工具。其中有些管用，有些不管用。而你看，这就是我们将如何成为更好的工程师，以及我们将如何构建更好的系统来让我们能够交付可靠且优质的体验。对此我是完全支持的。我讨厌看到软件出现质量下降。

<details>
<summary>Original English</summary>
>> and and second of all as you start caring about this and if you are working with the platform team start working with them hang out with them see how you can these problems that you're having, can I help build a solution for that? If you have the option transfer onto this team, it's it's pretty useful. And if you are on this team, try to have a way to work a little bit like implement the feature with the team. Understand why they're shipping so quickly and so seemingly carelessly because this will both ways will just make like it seems seems like we need need both especially now that product teams are pushed to ship a lot faster and they are shipping faster by the way and there's new new tools. Some of them work, some of them don't. And you know, this is how we're going to be better engineers and how we will build better systems that allow us to like ship reliable and quality experiences, which I'm I'm all for. I I hate seeing quality degradations on software.
</details>

>> 噢，不，不，我知道。而且我的意思是，就像……

<details>
<summary>Original English</summary>
>> Oh, no, no, I know. And I mean, like,
</details>

>> 但我们可以阻止它，或者说我们希望能真正打造出更好的软件。

<details>
<summary>Original English</summary>
>> but we can stop it or we we can actually build better software hopefully.
</details>

>> 是的。是的。我认为是这样。我觉得这对于熟悉 embedded S sur 模式的人来说，两者真的很相似，那种模式之所以非常非常有效是有原因的，我认为产品平台也有真正的相似之处。我之前一直跟我的团队说，我的意思是，我们以前总是得跟意大利面条式代码做斗争，对吧？太容易出现了。但现在我们到了这样一个节点，那些意面就像有了自己的生命一样，而且主动想要从盘子里溢出来；而在以前，人们还会觉得，好吧，我得尽量把它留在盘子里。现在可不是这样了。那些意面就像是自己想冲出来，而我们几乎必须像红队演练一样来审视我们自己的处境。

<details>
<summary>Original English</summary>
>> Yeah. Yeah. I think so. I think it's um it is really similar to for folks who are familiar with like the embedded S sur model like there's a reason why that's really really effective and I think that there's uh real parallels with product platform as well. I kept talking to my team about like I mean we always had to fight against spaghetti code, right? So easy. But now we're at this point where like the spaghetti has like a life of its own and it like actively wants to spill out of the plate whereas before people were like okay like I got to kind of keep it on the plate. No, no, no. The spaghetti like wants out and we have to almost like red team our own situation.
</details>

### 总结回顾

>> 确实是这样。好的，Mo，非常感谢你参与这次对话。

<details>
<summary>Original English</summary>
>> We do. Well, Mo, thank you so much for this conversation.
</details>

>> 非常感谢你邀请我。能深入了解我们大家都熟知并使用的产品（如 Slack、GitHub 和 Cursor）内部的扩展过程是怎样的，感觉很棒。在此之前，我承认我从未想太多自定义表情符号会引发某种规模化问题，但 mold 举出的关于 CEO 向 100,000 名用户发送全员周五放假消息的例子，是一个很好的直观展示。数百人添加了自定义表情符号，这引发了一场在网络和消息中到处发送自定义表情符号二进制文件的事件风暴。Slack 决定用一个非常简单的解决方案来解决这个问题：限制每条消息最多只能有 23 个自定义表情符号回应。我相信他们本可以做出更正规的修复，但无论如何，又有谁会注意到第 24 个自定义表情符号没有显示出来呢？听到 GitHub 16 个分片的限制以及他们为什么不能添加更多分片，也同样引人入胜。这是因为分散查询——那些没有主键、在返回前必须在每一个分片上运行的查询。更多的分片本会让这些查询变得更慢。当然，解决方案就是消除任何没有主键的查询。但当你面对一个有着数百或数千个没有主键的查询的遗留系统时，重写那些查询需要耗费不少时间。更不用说即使在重写的同时，可能还会有没有主键的新查询被添加进来。最后，听到虽然 mode 显然是 AID——我的意思是，在 GitHub 和 Cursor 工作过——但她仍然几乎用手工验证所有东西，这也很有意思，因为她说在做平台工作时，你会希望拥有一个稳定的基础。她还发现 LMS 往往写出的测试只是确认已写好的代码。Mod 现在热衷于使用变异测试来让它们覆盖边缘情况。请务必查看下方的节目单，了解关于 Cursor、GitHub、reliab 工程和性能等主题的相关 Pragmatic Engineer 深度探讨。如果你喜欢这个播客，请务必在你喜爱的播客平台以及 YouTube 上订阅。如果你还能给节目打分，我们将格外感激。谢谢大家，在下一……

<details>
<summary>Original English</summary>
>> Thank you so much for having me. It was nice to get an insider look of what scaling up looks like inside the products we all know and use like Slack, GitHub, and Cursor. Until now, I'll admit I never thought much about custom emojis causing a kind of scale problem, but mold example of the CEO sending out a everyone gets a Friday off message to 100,000 users was a good visualization. Hundreds of people add a custom emoji and this causes an event storm of custom emoji binaries sent all across the network and messages. Slack decided to fix the problem with a very simple solution. Limit each message to 23 custom emoji reactions. I'm sure they could have done a more proper fix, but who will notice the 24th custom emoji not appearing anyway? It was also fascinating to hear GitHub's limit of 16 shards and why they couldn't add more. It was because of scatter queries. Queries with no primary key that had to run on each and every shard before they could return. More shards would have slowed these queries down even more. The solution of course is to not have any queries without primary keys. But when you work with the legacy system with hundreds or thousands of queries without primary keys, rewriting those queries takes a non-trivial amount of time. Not to mention that even as you're rewriting, you might have new queries added with no primary keys. Finally, it was interesting to hear how while mode is clearly AID, I mean having worked at GitHub and cursor, she still verifies pretty much everything by hand because when doing platform work, she says that you want to have a stable foundation. She also found that LMS tend to write tests that just confirm the code written. Mod is now a fan of using mutation tests to have them cover edge cases. Do check out the show notes below for related pragmatic engineer deep dives on cursor, GitHub, reliab engineering, and performance topics. If you've enjoyed this podcast, please do subscribe on your favorite podcast platform and on YouTube. A special thank you if you also leave a rating on the show. Thanks and see you in the next
</details>