---
author: The Pragmatic Engineer
date: '2026-03-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5Kn32cIWPSY
speaker: The Pragmatic Engineer
tags:
  - whatsapp
  - engineering-culture
  - lean-startup
  - distributed-systems
  - career-development
title: 30人团队造就190亿美元奇迹：WhatsApp 早期工程师 Jean Lee 深度访谈
summary: 前 WhatsApp 第19号员工 Jean Lee 分享了这家传奇公司的内部运作机制。在仅有30名工程师的情况下，WhatsApp 如何通过“零流程”、极简架构（Erlang）和对质量的偏执，服务4.5亿用户并被 Facebook 收购。访谈还揭示了大厂生存真相、早期招聘策略以及 AI 时代下精简团队的永恒价值。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Jean Lee
  - Jan Koum
  - Brian Acton
companies_orgs:
  - WhatsApp
  - Facebook
  - Meta
  - Skype
products_models:
  - Erlang
media_books:
  - Surrounded by Idiots
  - A Random Walk Down Wall Street
  - The Hunger Games
status: evergreen
---
### WhatsApp 的反传统初创之路

**主持人**: 我有种感觉，**WhatsApp** 并不是一家标准的初创公司。

<details>
<summary>Original English</summary>

**Host**: I have a feeling WhatsApp was not exactly a standard startup.

</details>

**Jean Lee**: 没错。我们没有代码审查（code reviews），我唯一一次被审查代码是我提交第一个 commit 的时候。

<details>
<summary>Original English</summary>

**Jean Lee**: So, we didn't have code reviews, but the only time I got my code reviewed was the first time I made a commit.

</details>

**主持人**: 你提到过联合创始人 **Jan Koum** 经常说“不”？

<details>
<summary>Original English</summary>

**Host**: And you said that Jan said no a lot.

</details>

**Jean Lee**: 99% 的时间他都会拒绝。在我看来，所有酷炫的功能都缺失了，但这正是设计使然。因为我们真正的优先级是确保在偏远小镇的**老奶奶**也能随时随地使用我们的 App。

<details>
<summary>Original English</summary>

**Jean Lee**: 99% of the time he would say no. All the cool features were missing in my mind, but that was by design because we really wanted to prioritize again the quality of a grandma in a remote town being able to use our app at any given time.

</details>

**主持人**: 那些所谓的 Scrum、大写的 Agile（敏捷开发）、TDD（测试驱动开发），你们在 WhatsApp 用过吗？

<details>
<summary>Original English</summary>

**Host**: Scrum agile with a capital A TDD. Did you use any of these at WhatsApp?

</details>

**Jean Lee**: 我很惊讶听到有人觉得用了这些就能发版更快，我们一个都没用过。

<details>
<summary>Original English</summary>

**Jean Lee**: I'm surprised to hear they thought they were shipping faster because of it. We didn't use any of it.

</details>

**主持人**: 所以你们当时已经实现盈亏平衡了？

<details>
<summary>Original English</summary>

**Host**: So, you were break even.

</details>

**Jean Lee**: 是的，每年的那 **1 美元**年费足以支付服务器成本、员工薪水和短信验证码的费用。

<details>
<summary>Original English</summary>

**Jean Lee**: Yeah, that $1 was enough to pay for the server cost, the salaries, and the SMS code every year.

</details>

### 从小镇女孩到硅谷工程师

**主持人**: **Jean Lee** 是 WhatsApp 的第 19 号员工。她加入时，美国几乎没人听说过这个应用。她见证了用户增长到 4.5 亿，并在 Facebook 以 **190 亿美元**收购消息传出时，正戴着降噪耳机坐在办公桌前。今天，我们将讨论 30 人的团队如何原生构建 8 个平台，以及这种极致精简的流程对今天的 AI 初创公司有什么启发。Jean，欢迎来到节目，很高兴见到你。在你加入 WhatsApp 之前，你是如何进入科技行业的？

<details>
<summary>Original English</summary>

**Host**: Gene Lee was number 19 at WhatsApp. She joined when hardly anyone in the US had heard of it, saw it grow to 450 million users, and was sitting at her desk with noise cancelling headphones on when news broke that Facebook bought them for $19 billion. In today's conversation, we discuss how WhatsApp built natively eight different platforms with a team of 30 engineers. Why the founders said no to almost every feature request for years. How WhatsApp's team operated with no code reviews, no stand-ups, no sprint planning, and many more. If you want to understand how a tiny team with almost no process built one of the most successful products in history and what today's AI native startups can still learn from them, this episode is for you. Gan, welcome to the podcast. It is amazing to to meet you. You have quite the story early engineer at at WhatsApp. But before we get into WhatsApp, how did you get into tech?

</details>

**Jean Lee**: 我一直是个小镇女孩。我爸爸是个“老派文青”（OG hipster），他非常迷恋酿造啤酒，甚至决定去读一个**啤酒酿造学**的博士。

<details>
<summary>Original English</summary>

**Jean Lee**: I've always been a small town girl. My dad was an OG hipster. He was really into brewing beer. So, he decided to get a PhD in beer.

</details>

**主持人**: 啤酒博士？

<details>
<summary>Original English</summary>

**Host**: In beer?

</details>

**Jean Lee**: 是的，酿造学。1999 年我搬到了旧金山，那是我第一次接触到各种不同的科技角色。成长过程中，我从未想过当工程师是一份职业。虽然我用电脑，觉得能用 **Yahoo** 搜索东西很酷，但除此之外，我对硅谷的认知全来自住在这里后的耳濡目染。我遇到了很多科技从业者。青少年时期我玩过一点编程，但不算认真。但我确实觉得，写几行代码就能让它一遍又一遍地为你做事，这简直像魔法一样。我热爱那种创造出能够运行的东西、调试（debugging）并修复它的成就感。

直到上大学我才真正深入编程。我当时在纠结是当设计师、建筑师还是工程师，于是我和不同行业的人聊天。我发现只有科技行业的人对自己的工作充满热情。在硅谷，当你问人们的工作时，他们往往对未来充满希望，并为自己正在建造的东西感到自豪。相比之下，其他大人总是很消极，会说：“哦，千万别当建筑师，别当设计师。”这对我早期产生了很大影响。后来我在 **USC（南加州大学）** 学习计算机科学。

我的第一份编程实习是在一家只有三个人的初创公司。那是一个**视频共享网站**，虽然不像后来的 YouTube，但当时有很多类似的版本。当时的一个痛点是，你得访问 12 个不同的网站来搜索视频，所以我们做了一个聚合器。有趣的是，最近我看到很多 AI 平台可以让用户在不同模型之间切换，感觉非常相似。

<details>
<summary>Original English</summary>

**Jean Lee**: Yeah. In brewing. In brewing. Yeah. So, I moved to San Francisco in 1999 and that's when I got really exposed to all the different tech roles. Like, growing up, I didn't really even think about engineering as a job. Um, of course I use computers and I thought it was really cool to be able to use Yahoo and search things online, but beyond that, uh, my first exposure to Silicon Valley and tech came from living here. I got to meet a lot of people who work in tech. I dabbled around with coding when I was a teenager, but not too seriously. But I did think it was really cool that you can just write a few lines and it will just do things for you over and over and over. It was almost magical. I I love the feeling of creating something that that actually runs um and debugging something and fixing it and it runs again. That that was really joyous and I didn't really get into like super into coding until I went to college. But one of the reasons why I decided I wanted to go into coding was I talked to different people. So I thought maybe I want to be a designer, maybe I want to be an architect, maybe I want to be an engineer. And I talked to different adults who work in the in the industry. After talking to a lot of adults, I realized people who are in tech were the only ones who were really excited about their jobs. So in Silicon Valley, when you ask people like tell me about your work, people are often very hopeful for the future and very proud of what they're building. Compared to many other adults that I spoke with, they were not so encouraging. They're like, "Oh, don't become an architect. Don't become a designer." So that that was one of the influences um for me early on. I studied computer science at USC. Um, one of my first internships, actual like coding internships was at a small company. It was a threeperson startup started by one of the new grads from USC. And you'll probably uh understand it was a video sharing website, but it was not like YouTube, but there were so many versions of YouTube back in the days before what YouTube was dominant, right? So you probably remember dozens of these like video sharing platforms everywhere and one of the issues of having so many options is that you have to be visiting 12 different sites to search for new things. So we had a website where you can aggregate all the different types of videos from different sources which is actually kind of funny because lately I've been seeing a lot of AI platforms where you can just switch between the models very similar to that.

</details>

### 从 IBM 的稳定到初创公司的挑战

**主持人**: 你是怎么进入 **IBM** 的？

<details>
<summary>Original English</summary>

**Host**: Yeah. How did you get into IBM?

</details>

**Jean Lee**: 我非常喜欢在三人的初创公司工作，因为我能和各地的工程师合作。我负责编写设计文档、制定功能列表，能直接看到代码上线后的影响。那种所有权、速度和可见性非常令人兴奋。但我当时也希望得到更多的**导师指导（mentorship）**，因为我们都是刚毕业的学生，感觉是在盲目尝试。所以我第一份正式工作决定去一家更传统、规模更大的公司。当时，IBM 字面上就是全美最大的公司。

<details>
<summary>Original English</summary>

**Jean Lee**: I really loved working for a small um threeperson startup because I got to work with engineers um we had engineers overseas in China so I got to work with them. I got to also do a little bit of coding myself, but I was coming up with the design docs like the the features list and I was calling a lot of the shots and I could also directly see the impact of my code immediately on the website and I thought that type of ownership and speed and the visibility was really exciting that I get to see the impact of my work immediately. But one thing I wish I had was a little bit more mentorship because we were all new grads and in college um I felt like we were just shooting things to see which sticks. Um and I thought maybe for my first job out of school I would like a little bit more mentorship and training and I started looking at more bigger companies more traditional companies and that's how I ended up at at the time it was literally the biggest company in the US.

</details>

**主持人**: 你在什么时候决定离开，或者尝试别的东西？

<details>
<summary>Original English</summary>

**Host**: At what point did you decide that you wanted to leave or try out something else or did you even decide or something just came up?

</details>

**Jean Lee**: IBM 在导师指导和培训方面确实非常出色，那里有很多愿意分享经验的老兵。但我非常想念小团队的环境。大公司会议多、流程杂，我无法理解我的工作如何为公司整体做出贡献。于是我决定休息一段时间。那是 2009 年，现在回想起来，在经济低迷期辞职真的很勇敢。但当时我想，我才 22 岁，哪怕休息一年也能赶上来。

<details>
<summary>Original English</summary>

**Jean Lee**: One of the reasons why I wanted to go to a more traditional company with more structure was so that I could get more mentorship and training and IBM was excellent for that. There were so many veterans. They had so much experience and they were willing to share with me because they were 20 30 years ahead of me, right? But one thing I really missed was the small team environment. It was just so big. There was a lot of meetings, a lot of process and I I missed seeing the impact of my work. I couldn't quite understand how my work was contributing to the overall company. So then I decided to take some time off and explore and have some fun.

</details>

### 意外加入 WhatsApp

**主持人**: 后来发生了什么？你是怎么加入 WhatsApp 的？那是几年后的事了吧？

<details>
<summary>Original English</summary>

**Host**: Yeah. And what what happened from there? How did you eventually get to WhatsApp? That was years later right?

</details>

**Jean Lee**: 我花时间尝试了各种课程，做了一些现在被称为“零工（gig work）”的工作。我当时在探索自己究竟想要什么样的职业环境。最终我决定回到硅谷，想找一家工程师经验更丰富的初创公司，既能有自主权和影响力，又能得到指导。

2012 年我发现了 **WhatsApp**。当时它主要在欧洲和印度流行，在美国几乎没人知道。

<details>
<summary>Original English</summary>

**Jean Lee**: Yeah. So I took some time off to try out different like classes. I took a lot of classes. I did a little bit of nowadays you call it the gig work but I did all kinds of work. So whatever I needed to you know make a living um while taking all these classes and exploring and really finding out what like what kind of environment or what kind of career do I envision for myself and after I took those time off I decided that I want to go back to Silicon Valley but this time I do want to work for a startup but maybe with people who are a little bit more experienced maybe not new grads and maybe not a threeperson startup but a little bit more stable startup where I can possibly get both the the autonomy and the the impact of the work but also a little bit more mentoring because I was still in my 20s.

</details>

**主持人**: 你是怎么找到这家公司的？当时的面试是什么样的？

<details>
<summary>Original English</summary>

**Host**: Okay. So, how did you find this startup which of course happened to be WhatsApp in 2012? What was the interview like?

</details>

**Jean Lee**: 我们的面试没有 **LeetCode**。大多是关于系统设计的讨论。我和 Jan 讨论了各种即时通讯应用，因为我是韩国人，我跟他讲了很多 **KakaoTalk** 的运作方式。这就是我的面试。

<details>
<summary>Original English</summary>

**Jean Lee**: WhatsApp was still early. They started in 2009 and they did still have a lot of users but they're mostly in Europe and in India. Um they were not very known in America. I don't think we did any leak code until way way later until when we started hiring interns and new grads. Most of the interviews were talking about I I guess you can call it system design interviews. We would talk about how would you design this, how would you design that, like tell me about your past experience building this product and I recall talking to Yan about different messaging apps and being Korean, I told him a lot about Cacao Talk and how it worked. Yeah, that was my interview.

</details>

**主持人**: 就这样你就拿到了 Offer？我记得当时他们在 **Glassdoor** 上的评分只有一星，只有一条评论说不喜欢在这里工作。

<details>
<summary>Original English</summary>

**Host**: Just like that, you you got an offer. I guess it's startup, right? Things move fast. How did you decide that you're going to join this relatively unknown startup? In fact, their glass door rating at the time I remember had a one star. It had one review, one star, someone saying, "Oh, I don't like working here."

</details>

**Jean Lee**: 很有趣，我不记得查过 Glassdoor。当时我手里还有另一个 Offer，但那家公司动作太慢了。Jan 在面试几天后给我打电话，让我马上去办公室，问我：“你要怎样才肯现在就签 Offer？”我当时要求并不高，第二天就签了。我入职 WhatsApp 的第一天，另一家公司才打电话给我。

<details>
<summary>Original English</summary>

**Jean Lee**: Oh, that's so interesting. I don't remember looking up. I must have looked up glass door, but like I was really lucky because I actually had another offer from a different company, but they were a little bit sore. One company was taking weeks to get Gene an offer letter. Another founder closed the deal in person the very next day. It was not a startup and they said, "Oh, hey, like you have my verbal offer. I am going to give you a written offer soon." But then it took them a while and meanwhile um Yan called me few days later after the interview and he said come into the office right like today or tomorrow. And then he asked me what would it take for you to take the offer right now. Love it. What did you say? I mean I wasn't looking for that much. I mean I was in my 20s. So I just told them oh like few things I would like to have then sure I'll take the offer and I saw signed the offer the following day. And I did actually hear back from the other company on the first day I started WhatsApp. They called me and I was like oh I just started a new company.

</details>

### 极致精简的 30 人团队

**主持人**: 你是第 19 号工程师。你提到过你是团队里最年轻的？

<details>
<summary>Original English</summary>

**Host**: So you were engineer or you were employee number 19 at WhatsApp right? And you told me something really interesting that you were the youngest person even though you were like by this time at your mid mid20s or or so.

</details>

**Jean Lee**: 当时 30 岁以下的只有四个人。另外 15 个人都在 30 岁以上，这在当时的初创公司是不多见的。Jan 和 Brian 创办公司时已经三十多岁了，他们在 Yahoo 工作了十多年。前十几个工程师很多都来自 Yahoo，或者来自 Jan 在欧洲挖掘的专家。

<details>
<summary>Original English</summary>

**Jean Lee**: I recall there were about four of us under the age of 30. So I was not the young guest, but there were two people who were new grads and then myself and one other person who were in our late 20s. But the other like 15 or so people above 30 at a startup which is kind of unheard. Jana and Brian they they started this at like mid30s or or so after they spent like more than a decade working at Yahoo and other places. The first 10 or so engineers a lot of them came from Yahoo. Um some came from Europe. Yan used to do that. you would just look up who is the expert in this field and reach out to people and we had a lot of contractors in Europe.

</details>

### 独特的技术栈：Erlang 与八大平台

**主持人**: WhatsApp 的技术栈非常独特。你们要支持 8 个平台，却只有几个工程师。

<details>
<summary>Original English</summary>

**Host**: What was a tech stack like at WhatsApp? we're talking about eight platforms and a handful of engineers.

</details>

**Jean Lee**: 是的。我们有 iPhone、Android、Blackberry、Windows Phone，甚至还有 **Nokia S40、S60** 和 Web 客户端。后端用的是 **Erlang**。

<details>
<summary>Original English</summary>

**Jean Lee**: We were actually pretty unique. I I don't think any startup ever really does this, but we had seven different stacks. iPhone and Android, Blackberry and Windows Phone, Nokia S40, S60, Kyios, and the web client, so it's actually eight. iOS is Objective C, Android was Java, Nokia was Symbian C++. And the back end was Erlang.

</details>

**主持人**: 能讲讲 **Erlang** 吗？这在初创公司里非常罕见。

<details>
<summary>Original English</summary>

**Host**: Erlang can you tell us about Erlang because this that is one of the most exotic tech sack I've heard.

</details>

**Jean Lee**: 它是电信背景下非常完美的语言，非常擅长处理高并发。我们的工程师曾打过一个比方：维护 WhatsApp 就像是在飞机 **24/7 飞行**的过程中修理引擎。因为应用是全球性的，总有一个地方是早八点。我们由于使用了某种工具偶然发现了 Erlang，并意识到它是最合适的语言。

<details>
<summary>Original English</summary>

**Jean Lee**: There's a really great talk by one of our engineers, Rig Reed, why they started working with Erling and it was the perfect choice. And he describes it as um trying to maintain the engine of an airplane while it's flying 24/7 because if you imagine like WhatsApp is so international, we can't take a break, right? We have to continuously keep running and it's always busy. Someone's it's 8:00 a.m. somewhere in the world, right? and Erling was a really robust um language that was really good at concurrencies.

</details>

**主持人**: 为什么要原生开发这么多平台，而不是跨平台（cross-platform）？

<details>
<summary>Original English</summary>

**Host**: The conventional wisdom has been like look if you want to support all those platforms don't be silly do crossplatform. Why did WhatsApp not do this?

</details>

**Jean Lee**: Jan 常说：“我希望偏远农村的老奶奶也能用我们的应用。”这意味着应用必须非常**轻量**，能在任何老旧设备上流畅运行。这就是我们决定原生开发 8 个平台的原因。

<details>
<summary>Original English</summary>

**Jean Lee**: So, Yan used to always say, "I want a grandma in a remote countryside to be able to use our app." So, what does that mean? They may not have the newest iPhone, the shiniest phone with the biggest memory, right? In the countryside where a grandma is using it, you need the app to be lightweight. You need it to work on any kind of device, and you need the app to be simple.

</details>

### “零流程”的运行模式

**主持人**: 你们在内部是如何推进工作的？有什么工程流程吗？

<details>
<summary>Original English</summary>

**Host**: And then inside WhatsApp how did you get things done? what engineering processes people might have followed?

</details>

**Jean Lee**: WhatsApp 是极致的精简。被收购时，我们服务 4.5 亿用户，却只有不到 30 个工程师。我们没有正式的代码审查。只有 30 个人，大家会读 Git 的提交记录，然后在 WhatsApp 群组里讨论。

<details>
<summary>Original English</summary>

**Jean Lee**: WhatsApp was like the ultimate lean company. By the time we were acquired, we only had 20some engineers, so under 30 people serving 450 million monthly active users. So, we didn't have code reviews. After the first time, we didn't really have a formal code review. But I mean, people read the git commits because there's only 30 engineers. You can read other people's code and they would discuss it on the WhatsApp groups.

</details>

**主持人**: 所以全靠信任？工程师直接把代码推到生产环境？

<details>
<summary>Original English</summary>

**Host**: So, everyone was trusted, all engineers that they just pushed their code to they merged it into production, pushed it to production without a manager review.

</details>

**Jean Lee**: 没错。我们的发布流程非常依赖**内部试用（dogfooding）**。Jan 在 LinkedIn 上的头衔是“首席质量官（Chief QA Officer）”，他会到处寻找并尝试搞挂（break）所有功能。

关于功能的增加，Jan 也是极其克制的。很多酷炫的功能我们都没有。因为我们优先考虑的是质量。我们在发布视频通话前研发了很久，直到 100% 确定质量过关才发布。

<details>
<summary>Original English</summary>

**Jean Lee**: Exactly. We were really big on dog fooding. So, every time we were about to do a release, we would all internally use it ourselves. Yan, his title when he messaged me see it said chief QA officer. He would try to break things as much as he can. He did say no almost as I recall 99% of the time he would say no. We launched groups shortly after I joined. We didn't have voice calls, video calls. We didn't have any of the no stories. All the cool features were missing in my mind, but that was by design because we really wanted to prioritize again the quality of a grandma in a remote town being able to use our app at any given time.

</details>

**主持人**: 这和主流初创公司“尽早发布，快速更迭”的策略截然相反。

<details>
<summary>Original English</summary>

**Host**: It sounds like you did the opposite. It's it's like polish it and then do when you have full conviction.

</details>

**Jean Lee**: 是的，我们内部和家人试用了非常久才公开发布。

<details>
<summary>Original English</summary>

**Jean Lee**: Yeah, we did use it internally with our families. and we used it for a very long time before we launched it with the public.

</details>

### 190 亿美元的那个下午

**主持人**: 2014 年，Facebook 宣布以 190 亿美元收购 WhatsApp。你当时在场吗？

<details>
<summary>Original English</summary>

**Host**: 2014, Facebook announces their biggest ever acquisition, WhatsApp, for $19 billion. What do you remember of this time?

</details>

**Jean Lee**: 我当时正戴着耳机写代码。突然业务主管挥舞双臂让我们停下，进会议室。我们从不开会，更别说是不成文的紧急会议了。Jan 让大家关掉手机，我甚至担心是不是公司破产了。Jan 曾经说过卖掉公司就像卖掉自己的孩子。

然后他们宣布了收购的消息。Jan 和 Brian 脸上的表情很奇怪，我想那是他们在努力掩饰兴奋。我当时有点懵，在想我的期权能值多少钱？190 亿美元的 1% 是多少？然后扎克伯格就走进来了。

<details>
<summary>Original English</summary>

**Jean Lee**: I remember I was coding. I had this Spotify playlist called Let Me Think. I saw Nirage who was the head of business at the time. He's like like stop whatever you're working on right now. Come into the meeting room. And I was like what is happening? Like we never have meetings. "Turn off your phones." And I thought, "Oh my gosh, what's happening? Did we go out of business?" It can't be that we sold the company because Yan used to say he will never sell the company. He used to actually say uh selling your company is like selling your baby. And then they made the announcement WhatsApp has been acquired by Facebook for $19 billion and I realized oh that was them trying to hide their excitement. And then Zuckerberg walked in.

</details>

### 在 Meta 的职场真相：业绩评估与可见性

**主持人**: 加入 Facebook 后，你的角色发生了什么变化？

<details>
<summary>Original English</summary>

**Host**: What changed to the day-to-day once you officially became part of Facebook?

</details>

**Jean Lee**: 变化非常缓慢。我们甚至在两后才搬进门洛帕克的总部。在 Facebook，大家都是软件工程师，没有头衔，但有等级。作为最年轻的几个人之一，我被定级为 **L3（初级工程师）**。我不得不重新往上爬，后来我成了工程经理。

<details>
<summary>Original English</summary>

**Jean Lee**: The changes were very slow in the beginning. We didn't even move into the meta or at the time it was called Facebook headquarters until at least a couple years after the acquisition. So, being one of the five youngest people, I got I got leveled as a junior engineer. L3. I had to like climb climb all over again. I eventually became an engineering manager.

</details>

**主持人**: 那些校准会议（calibration meetings）到底是怎么回事？

<details>
<summary>Original English</summary>

**Host**: As a manager, you were part of calibration meetings, right? What are those meetings like?

</details>

**Jean Lee**: 很多人的误区是认为经理决定了你的晋升。其实中层经理没有权限直接给晋升，我的角色更像是代表客户的**律师**。我要为我的团队成员辩护，说服其他经理同意这个评分。

在 Facebook，那些经常在 **Workplace** 上发帖、拥有最高**可见性（visibility）**的人最容易达成共识。如果你做了很棒的工作但没人知道，你的经理很难为你争取到一致认可。所以，通过发帖、评论和他人互动，建立影响力非常重要。

<details>
<summary>Original English</summary>

**Jean Lee**: The people number one biggest mistake people make is they think your manager is the one giving you a promotion. I think of myself as the lawyer representing my clients. I'm making a case for them. The people who post the most often, who have the most visibility, usually get the easiest consensus because it's just like all very natural. Whereas if you have been actively posting and telling me what type of work you have done and what type of impact that has made then I already know oh okay like when your manager tells me you're ready then I agree.

</details>

### 给新人的建议与 AI 的未来

**主持人**: 在 AI 时代，你会给新毕业的学生什么建议？

<details>
<summary>Original English</summary>

**Host**: If you had to give career advice to a new grad in this kind of AI native world, what would you suggest they focus on?

</details>

**Jean Lee**: 专注于**基础（foundations）**。工具会变，语言会变，但基础知识永远不过时。今天的 AI 团队可以从 WhatsApp 学到：保持团队精简。当你小的时候，沟通成本极低，你可以移除所有的分心和流程，从而获得真正的所有权和建造的自由。

<details>
<summary>Original English</summary>

**Jean Lee**: I say foundations, you know, tools come and go, languages come and go, but foundations don't go anywhere. By having lean teams, you get several benefits. You get to remove a lot of the distractions and process and through that you get two really incredible benefits which is ownership and the the really like the freedom to build things.

</details>