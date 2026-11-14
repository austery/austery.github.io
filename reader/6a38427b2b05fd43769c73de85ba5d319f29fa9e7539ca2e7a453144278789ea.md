---
author: The Pragmatic Engineer
date: '2026-06-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=xafwfGVBxos
speaker: The Pragmatic Engineer
tags:
  - coding-interview
  - skill-evolution
  - effort-vs-shortcut
  - agentic-workflow
title: 编码面试的未来预测、优秀工程师的区分标准与AI时代的技能演变
summary: 文章探讨了编程面试在AI辅助编程背景下的现状，指出数据结构和算法面试仍是评估思维模式的关键。核心观点在于，随着AI普及，真正的价值在于解决问题的能力、沟通技巧以及持续学习的努力，而非单纯的代码编写技能。强调了软技能的重要性，并建议工程师应专注于提升对业务的理解和迭代反馈的能力。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/13 -->

### 关于编码面试的预测与现状

**Speaker A**: 过去有很多预测说，编程面试将会成为历史。现在已经有用于面试的作弊工具了。谷歌在这一点上几乎已经转向现场测试（on-sites），回到传统的白板模式。某个人会看着你写代码，而你可能无法通过那种方式作弊来应付它。

<details>
<summary>Original English</summary>

**Speaker A**: There's been so many predictions that coding interviews will be dead. >> There's been cheating tools for interviews. Google has pretty much gone to on-sites at this point, back to the traditional whiteboard. Somebody's going to be watching you code, and you're probably not going to be able to cheat your way through that.

</details>

**Speaker B**: 你的一个观点是2026年。构建东西变得从来没有这么容易过，但我会说这只是让真正创造价值变得困难了十倍。你说现在个性特质比编码技能更重要了。

<details>
<summary>Original English</summary>

**Speaker B**: One of your hot takes is 2026. It's never been easier to build things, but I would say that it just makes 10 times harder to actually build value. You said that personality traits are now more important than coding skills.

</details>

**Speaker A**: 我几个月前雇佣了一个人。他甚至还没有毕业。我给这个人布置任何任务，即使他完全不知道从哪里开始，一周后他都会对这件事学到所有东西。这才是最重要的。

<details>
<summary>Original English</summary>

**Speaker A**: I hired somebody a few months ago. They still haven't even graduated. Anytime I give this person a task, even if they have no idea how to start it, a week later, they'll have learned everything about it. That matters the most.

</details>

**Speaker B**: 你提出了一个相当有争议的观点，一些人应该放弃技术职业。

<details>
<summary>Original English</summary>

**Speaker B**: You've had a pretty contentious hot take, which was some people should just give up on tech careers.

</details>

**Speaker A**: 你应该知道自己将进入什么领域，因为……

<details>
<summary>Original English</summary>

**Speaker A**: You should know what you're getting yourself into because...

</details>

### 优秀工程师的区分与AI的影响

**Speaker B**: 什么能将优秀的工程师与其他人区分开来？Neet Dhiman Singh，或者正如许多人称他为Neet，他创建了NeetCode，这个帮助无数开发者在大型科技公司被录用的编程准备平台。在今天的节目中，我们将讨论如何准备数据结构和算法面试，这在工作中很有用，以及它更多是关于思维模式而不是算法本身。工程师与那些在没有AI辅助时仍然能思考的人，以及那些在有AI辅助时会冻结的人之间的差距正在扩大。Neet那个认为有些人应该放弃技术职业的有争议的观点……

<details>
<summary>Original English</summary>

**Speaker B**: What separates strong engineers from everyone else? Neet Dhiman Singh, or as many call him Neet, he created NeetCode, the coding preparation platform that helps countless devs get hired at big tech. In today's episode, we cover what preparing for data structures and algorithms interviews that's useful on the job, and how it's more about mindset than the algorithms. The growing difference between engineers who can still think without AI at their fingertips and those who freeze without it. Neet's contentious hot take that some people should just give up on tech careers...

</details>

**Speaker A**: 如果你想了解哪些入门技能会随着职业生涯累积，以及AI正在悄悄侵蚀的那些技能，本集就是为你准备的。本集由Antithesis制作。Antithesis会在你的整个系统里运行一个敌对模拟，并在你的用户做之前找到每一个Bug。这听起来像科幻小说，但它实际上是硬核工程。访问antithesis.com/pragmatic了解更多信息。

<details>
<summary>Original English</summary>

**Speaker A**: If you want to understand which entering skills compound over a career and the ones that AI is quietly eroding, this episode is for you. This episode is presented by Antithesis. Antithesis runs your whole system in a hostile simulation and finds every bug before your users do. It sounds like science fiction, but it's actually hardcore engineering. Understand how at antithesis.com/pragmatic.

</details>

**Speaker B**: 这集由Sentry带来。Sentry是我在Uber工作时用来进行应用监控的一个工具，我现在也用它来管理我所有的项目，包括Pragmatic Engineer的后端。我对Sentry的一个新功能非常喜欢，那就是他们的Sear AI代理，它可以帮助调查生产错误。例如，这里有一个我在我的应用程序中遇到的实际错误。我可以问Sear它可能是什么根本原因，它会提供上下文，并且还可以通过网页界面制定一个修复计划。哦，它在Slack上也能工作，不只是网页。

<details>
<summary>Original English</summary>

**Speaker B**: This episode is brought to you by Sentry. Sentry is a tool I used for application monitoring back when I worked at Uber, and I now use it on all my projects, including the Pragmatic Engineer backend. One new feature I'm really liking about Sentry is their Sear AI agent, which helps investigate production errors. For example, here's an actual error I had in my application. I can just ask Sear what might be the root cause and it brings context and it can also make a plan to fix it all from the web interface. Oh, and it also works in Slack as well, not just the web.

</details>

**Speaker A**: 我发现Sentry在代码X或云代码中使用Sentry MCP使用它更方便。当你连接到MCP服务器后，你可以做一些非常有用的事情。例如，当一个已经解决的Sentry问题再次出现时，你可以启动一个代理来调查回归问题，阅读相关的代码，并提交一个带有建议修复的PR。要实现这一切需要一些工作：将Sentry连接到你的代码仓库，将Sentry MCP添加为游标（cursor），定义游标代理的调查指令，配置启动自动化触发器的设置，并测试它是否都能正常工作。但一旦你把它设置好并运行起来，你就可以在继续审查每一个修复的同时更快地修复回归问题。我不是一个单纯为了AI工具而使用它的粉丝，但我真的很喜欢那些我可以更快、更有上下文地修复错误的实际集成。请查看sentry.io/pragmatic上的Sentry，今天就开始监控和修复回归吧。

<details>
<summary>Original English</summary>

**Speaker A**: One place that I find even more handy to use Sentry is from code X or cloud code using Sentry MCP. After you hook up the MCP server, you can do some very useful things. For example, when an already resolved Sentry issue resurfaces, you can kick off an agent to investigate the regression, read the relevant code, and open a PR with a suggested fix. There's a little work involved to get all of this going: to connect Sentry to your code repository, add Sentry MCP as a cursor, define the instruction for cursor's agent to investigate, configure the trigger that launches the automation, and test that it all works. But once you have it up and running, you can get regressions fixed faster while still reviewing every and all fixes. I'm not a fan of using AI tools just for the sake of it, but I really like the practical integrations where I can fix errors faster and with more context. Check out Sentry at sentry.io/pragmatic and start monitoring and fixing regressions today.

</details>

### 编码面试的持续性与评估难题

**Speaker B**: 很棒。欢迎来到播客。是的，我很高兴能在这里。很高兴有你。让我们从我想过的一件事开始。有很多预测说，如果AI足够好到可以写代码了，你知道，在日常工作中我们不再需要编写代码，那么编码面试就会死掉，因为……现在大多数工程师的工作不是写代码，而是工作中的提示（prompting）。然而，在同样的公司里，编码面试仍然没有死掉。你对此有什么看法？

<details>
<summary>Original English</summary>

**Speaker B**: Neat. Welcome to the podcast. Yeah, I'm happy to be here. It's awesome to have you here. Let's start with something that I've been thinking about. So, there's been so many predictions that if if and when AI will be good enough to like write code, you know, coding interviews will be dead because uh on the day-to-day we will not be writing code. Now, most engineers are not writing code, they're prompting at work. And yet at the same companies, coding interviews are still not dead. What is your take on this?

</details>

**Speaker A**: 是的，我觉得这很有趣。看看过去几年和特别是最近几个月，编码面试变化有多大，而编码面试却是唯一保持相当一致的领域。我知道有些人喜欢谈论它们发生了很大变化，到目前为止，它们只是随着AI辅助编程面试而有点改变了，公司也在尝试这种方式。但令人惊讶的是，数据结构和算法的编码面试格式仍然非常顽固。这让很多人感到困惑，包括我自己，因为我们已经到了一个可以问像AI机器人任何关于代码库的问题，它都能给你相当好的答案的地步。你可以让它实现某个功能，你可以做几乎任何事情。而且它可能不会达到100%的程度，就像连人类都无法写出无Bug的代码一样，但它可以达到至少90%的程度，非常接近了。所以这让很多人感到困惑，我认为这回到了如何评估某人是否是好员工的问题。有一个方面是他们是否具备硬技能？他们是否具备技术能力？他们能否思考？数据结构和算法面试从来都不是评估这些方面的最佳方式。嗯，思考是肯定的，但在工作上这种技能能转化为你实际做的事情吗？它从未真正转化成那样。更多的是关于评估某人是否会思考。所以我认为这是原因之一，而第二個保持顽固的原因是公司根本不知道如何评估……他们可能从来没有这样做过。我记得我当时在亚马逊的朋友史蒂夫提到，他们进行了一些研究，而且要弄清楚一个人在工作上表现如何非常困难，无论你拥有多少数据，无论你运行了多少面试流程，都很难知道某人实际的表现会如何。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think it's really funny with how much coding has changed the last few years and especially the last few months that coding interviews are the one area that have surprisingly stayed pretty consistent. I know some people like talk about them changing a lot and so far they're kind of like changing a bit with like AI-assisted coding interviews, companies are trying that. But surprisingly, the coding interview format of data structures and algorithms is really really sticky. And it's confusing to a lot of people, myself included, because like we've gotten to a point where you can ask like an AI bot any question about a code base it can give you a pretty good answer. You can ask it to implement some feature, you can uh do anything pretty much. And it might not get 100% of the way there like even humans can't write bug-free code but it can get at least 90% of the way there like pretty close. So it's confusing to a lot of people and I think that it goes back to like how do you even evaluate if somebody's a good hire or not there's one aspect of it which is like do they have the hard skills do they have the technical skills can they think and DSA interviews were never the best for that. Well, thinking sure but in terms of like does that skill translate to what you're doing on the job? It never really translated to that. It was more about evaluating like does somebody think? So I think that's one of the reasons and the second reason that's stayed sticky is that companies just have no idea how to evaluate like and they probably never did. I think I was talking to a friend of mine Steve from Amazon and he mentioned that like they've run some studies and it's like very hard to know like whether somebody like when you hire somebody no matter how much data you have no matter how like you've run the interview process that it's just very hard to know like how somebody's actually going to perform on the job.

</details>

**Speaker B**: 如果他们会成功工作？

<details>
<summary>Original English</summary>

**Speaker B**: If if if they're going to work out right?

</details>

### 员工动机与流程的复杂性

**Speaker A**: 这是个非常困难的问题，因为即使某人很优秀，你怎么知道他们会保持动力？你怎么知道他们会喜欢团队环境、氛围等等这些东西呢？所以我觉得这真的很复杂。

<details>
<summary>Original English</summary>

**Speaker A**: It's a very hard problem because even if somebody is good how do you know they're going to be motivated? How do you know they're going to enjoy the team environment the vibe and all that stuff. So I think it's just really complicated.

</details>

**Speaker B**: 另一个原因可能是它如此顽固，并且仍然是顽固的。也许它很简单，就像如果它没坏就不要修它这种心态？

<details>
<summary>Original English</summary>

**Speaker B**: And could another reason be that it has been so sticky and it's still a sticky that maybe it's just simple as there it's kind of like if it if it ain't broken don't fix it type of mentality?

</details>

**Speaker A**: 我想是这样，因为任何时候你试图改变某件事，都有风险让它变得更糟。所以首先，在大型公司改变那个流程需要很多工作，它是非常官僚的。会有大量的再培训，我们已经看到Meta等公司试图运行AI编码面试了。训练很难做到，因为它就像面试官根本不好。比如，大多数面试官不喜欢面试。

<details>
<summary>Original English</summary>

**Speaker A**: I think so because anytime you try to change something you risk making it worse and so it's like first of all it's a lot of work to change that process at big companies like it's very bureaucratic. There's going to be a lot of retraining and we're already kind of seeing that with companies like meta trying to run AI coding interviews. The training is really hard to get down cuz it's like Interviewers are just not good. Like the most Interviewers do not like interviewing. They hate it.

</details>

**Speaker B**: 当你说训练时，你的意思是面试官培训，比如在一家大型公司里，要让一千个面试官变得相似？

<details>
<summary>Original English</summary>

**Speaker B**: When you're saying training, you mean interviewer training, like training your interviewers like at a large company like a thousand of them to like be similar.

</details>

**Speaker A**: 完全正确。因为在大型公司，你希望流程是标准化的。你希望对每个人都是一样的。这在一般情况下很难做到。当你引入更多变量时，比如新的评估流程、以不同的方式培训面试官……现在你得检查AI提示词，像所有这些变量。所以它不是精确的科学。测量这些东西很困难。实际上是不可能的。所以我认为我们肯定会看到公司尝试不同的方法。我认为我们会看到不同的面试格式被引入。我只是觉得过渡会比大多数人想象的要慢。

<details>
<summary>Original English</summary>

**Speaker A**: Exactly, yeah. Because at a big company, you want the process to be standardized. You want it to be the same for everybody. And that's very hard to get right in general. And it's even harder to get right when you have like more variables introduced, like a new evaluation process, training interviewers differently. Now you got to check the AI prompts, like all these variables. And so, it's not like an exact science. It's hard to measure these things. It's It's practically impossible. So, I think we're definitely going to see, I think, companies trying different things. I think we probably will see different interview formats introduced. I just think it is going to be a slower transition than most people think.

</details>

### 回顾早期职业生涯与编程基础

**Speaker B**: 我想回到你早期的日子。比如，你是如何进入技术领域的？你第一次接触编程编码是什么时候？

<details>
<summary>Original English</summary>

**Speaker B**: I want to rewind a lot back into your early days. Like how did you get into tech? What was your first introduction with programming coding?

</details>

**Speaker A**: 是的，我大学在学习电气工程的时候。因为我真的很喜欢数学。我真的很喜欢物理学。我知道很多程序员不喜欢。有些人显然喜欢，但很多程序员不喜欢。但他们真的喜欢编程。所以当我接触到我们的编程时，我是在……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I was actually studying electrical engineering when I was in college. Because I really liked math. I really liked physics. I know a lot of programmers don't. Some Some of them obviously do, but a lot of programmers don't. But they really like programming. And so, when I got into our programming, I was...

</details>

<!-- chunk 2/13 -->

### 课程介绍与编程的转变

**Speaker A**: just taking our intro to C class. It was required for electrical engineering. I didn't really want to take it. And I was not very good at it initially. I remember trying to learn printf and the you know, percent S, percent C, like I don't know why. Like I looked around. Everybody around me was learning it so quickly. And to me, it was just a very different way of thinking. Even though it's kind of related to math, you'd think it'd be easy to pick up, but it really wasn't initially for me. But then, I think a couple months went by and we learned about variables, conditions, loops, functions, and all these kind of concepts. And then it really like something just kind of clicked where it's like initially, programming felt kind of boring. It's like you just have variables and numbers. But then when you introduce all these things, then you realize there's like this infinite complexity that can be introduced. And and you see that with like all the software that is built today, where it's like you took these like simple primitive things, these zeros and ones, and all of a sudden you just have this enormous like universe of software solving insane problems. You have databases like Google Spanner, which not only take programming, but they take physics, they take like atomic clocks and GPS systems and all these things, and they solve like these really hard problems. And so, I guess to go back to my story and well once I really started enjoying programming, I just fell in love with it and I was like, "Okay, I'm going to I'm going to do this for the rest of my life. I'm going to love it." And then I went through a transition where once I got into the real world, I realized that programming is not something you can just kind of do the way you enjoy. Like it's a business at the end of the day, and so that in a lot of ways took some of the fun out of it for me, where it's like you don't get to work on the languages that you like, the problems that you enjoy solving. You have to focus on like the business problems. And so, yeah, I I I have a love-hate relationship with programming because of that reason. And I think a lot of people do.

<details>
<summary>Original English</summary>

just taking our intro to C class. It was required for electrical engineering. I didn't really want to take it. And I was not very good at it initially. I remember trying to learn printf and the you know, percent S, percent C, like I don't know why. Like I looked around. Everybody around me was learning it so quickly. And to me, it was just a very different way of thinking. Even though it's kind of related to math, you'd think it'd be easy to pick up, but it really wasn't initially for me. But then, I think a couple months went by and we learned about variables, conditions, loops, functions, and all these kind of concepts. And then it really like something just kind of clicked where it's like initially, programming felt kind of boring. It's like you just have variables and numbers. But then when you introduce all these things, then you realize there's like this infinite complexity that can be introduced. And and you see that with like all the software that is built today, where it's like you took these like simple primitive things, these zeros and ones, and all of a sudden you just have this enormous like universe of software solving insane problems. You have databases like Google Spanner, which not only take programming, but they take physics, they take like atomic clocks and GPS systems and all these things, and they solve like these really hard problems. And so, I guess to go back to my story and well once I really started enjoying programming, I just fell in love with it and I was like, "Okay, I'm going to I'm going to do this for the rest of my life. I'm going to love it." And then I went through a transition where once I got into the real world, I realized that programming is not something you can just kind of do the way you enjoy. Like it's a business at the end of the day, and so that in a lot of ways took some of the fun out of it for me, where it's like you don't get to work on the languages that you like, the problems that you enjoy solving. You have to focus on like the business problems. And so, yeah, I I I have a love-hate relationship with programming because of that reason. And I think a lot of people do.

</details>

**Speaker B**: It's interesting how you know, you got really excited it was boring, and then you got excited about the complexity and the possibilities, and you kind of came back to down to earth. One thing we were just talking about before we started the podcast is the CAP theorem. On how you also had a similarly weird relationship with it. Can we talk about it? And also for those of us those listening who who don't know exactly what the CAP theorem is. Let's start with that.

<details>
<summary>Original English</summary>

It's interesting how you know, you got really excited it was boring, and then you got excited about the complexity and the possibilities, and you kind of came back to down to earth. One thing we were just talking about before we started the podcast is the CAP theorem. On how you also had a similarly weird relationship with it. Can we talk about it? And also for those of us those listening who who don't know exactly what the CAP theorem is. Let's start with that.

</details>

### 关于CAP定理的讨论

**Speaker B**: Yeah, of course. Uh so, it's a pretty simple theorem. It's kind of described awkwardly sometimes, where it's you have like three choices, and you can pick two of three. There's consistency, uh and that's data consistency, so in like a distributed system where you have data that's like partitioned in different regions or something. It can go out of sync. Like one database might be more up-to-date than the other. And then there's availability, where are both of these uh you know servers or databases available to read or maybe one went down. And then the third one is a partition or partition tolerance. And so that basically means in a distributed system if there's a partition if maybe the system becomes disconnected one thing goes down the how is it going to behave? And so the two out of three framing is used a lot. It's not super accurate. And the entire theorem is very like incomplete. And so when I was learning it for the first time I thought you know I like to go deep into things I like to really really understand things. That's what I love about programming it's deterministic. Like if you really want to you can go down to the exact line of code the line of assembly the zeros and ones to know exactly like what was happening. And so CAP theorem felt like hand-wavy to me and I didn't really like that and that that goes back to why I don't like certain things about working on the job because I think like you don't get to go as deep as you like you have to solve the business problem even if it means you don't really understand some of the technical details. But that's fine. But later on I felt so validated when I saw a blog post from Martin Kleppmann talking about how much he didn't like CAP theorem. And it was actually a little bit controversial where I think there were plenty of smart people in the comments of that blog post that said that you know maybe he's like technically right but maybe he's you know being a little little bit nitpicky and I think that's like a personal preference but I just felt very validated that somebody like him agreed with me and I think it's it's kind of funny because I think I never saw anybody mention that about CAP theorem before like I saw like posts on Stack Overflow nobody really mentioned it's kind of incomplete. And so the thing that came after it is like PAC else which is like if there's a partition you can choose either availability or consistency but if there's not then there's still a trade-off to be made which is latency and consistency. So it's much more complete. I don't understand why anybody would learn the CAP theorem when that theorem exists because it's just more complete. It's not that much more complicated. I think it's more simple to understand.

<details>
<summary>Original English</summary>

Yeah, of course. Uh so, it's a pretty simple theorem. It's kind of described awkwardly sometimes, where it's you have like three choices, and you can pick two of three. There's consistency, uh and that's data consistency, so in like a distributed system where you have data that's like partitioned in different regions or something. It can go out of sync. Like one database might be more up-to-date than the other. And then there's availability, where are both of these uh you know servers or databases available to read or maybe one went down. And then the third one is a partition or partition tolerance. And so that basically means in a distributed system if there's a partition if maybe the system becomes disconnected one thing goes down the how is it going to behave? And so the two out of three framing is used a lot. It's not super accurate. And the entire theorem is very like incomplete. And so when I was learning it for the first time I thought you know I like to go deep into things I like to really really understand things. That's what I love about programming it's deterministic. Like if you really want to you can go down to the exact line of code the line of assembly the zeros and ones to know exactly like what was happening. And so CAP theorem felt like hand-wavy to me and I didn't really like that and that that goes back to why I don't like certain things about working on the job because I think like you don't get to go as deep as you like you have to solve the business problem even if it means you don't really understand some of the technical details. But that's fine. But later on I felt so validated when I saw a blog post from Martin Kleppmann talking about how much he didn't like CAP theorem. And it was actually a little bit controversial where I think there were plenty of smart people in the comments of that blog post that said that you know maybe he's like technically right but maybe he's you know being a little little bit nitpicky and I think that's like a personal preference but I just felt very validated that somebody like him agreed with me and I think it's it's kind of funny because I think I never saw anybody mention that about CAP theorem before like I saw like posts on Stack Overflow nobody really mentioned it's kind of incomplete. And so the thing that came after it is like PAC else which is like if there's a partition you can choose either availability or consistency but if there's not then there's still a trade-off to be made which is latency and consistency. So it's much more complete. I don't understand why anybody would learn the CAP theorem when that theorem exists because it's just more complete. It's not that much more complicated. I think it's more simple to understand.

</details>

### 对深度理解的看法与职业实践

**Speaker A**: I wonder if it's only a smaller subset of people who actually go deep. You know, CAP theorem, you actually like, all right, let me understand the whole thing and then you realize it's incomplete. But most people might have just like looked at it, you know, took it, okay, it's the law, two out of three, simple enough, move on. And I guess in in most part of their lives, it's enough or they might not even use it or if when they they think they know, but they don't know it exactly. So, it's interesting cuz we're talking about software engineers and you would think that most software engineers go into the details, but I guess maybe not.

<details>
<summary>Original English</summary>

I wonder if it's only a smaller subset of people who actually go deep. You know, CAP theorem, you actually like, all right, let me understand the whole thing and then you realize it's incomplete. But most people might have just like looked at it, you know, took it, okay, it's the law, two out of three, simple enough, move on. And I guess in in most part of their lives, it's enough or they might not even use it or if when they they think they know, but they don't know it exactly. So, it's interesting cuz we're talking about software engineers and you would think that most software engineers go into the details, but I guess maybe not.

</details>

**Speaker B**: Yeah, I think it goes to like solving the business problems and just like this is what I didn't like when I started working professionally because okay, so you go through like documentation, right? You're going through onboarding. Like at Google, there's so much documentation, there's so many internal tools. And I want to go deep. Like I want to do depth-first search on all of the document links. Like, you know, you have one blog or you have one site and it has it references like five others. That one is going to reference five others. Like I want to go through every single one, have like a complete understanding of everything. But that's just not how it works at jobs. Even a code base, no one is going to understand this massive code base unless you like write all of it by yourself, which is just not how companies work. And now we're kind of seeing a similar transition I think a lot of people are going through now with like agentic coding because it's kind of a similar concept where it's like now you might not even be looking at the code that you're actually producing yourself. So, it's it's kind of similar and I think this whole transition kind of reminds me of that where it's like you don't get to do some of the things that you used to enjoy, but it's it's still you know, that's that's life, [snorts] that's business.

<details>
<summary>Original English</summary>

Yeah, I think it goes to like solving the business problems and just like this is what I didn't like when I started working professionally because okay, so you go through like documentation, right? You're going through onboarding. Like at Google, there's so much documentation, there's so many internal tools. And I want to go deep. Like I want to do depth-first search on all of the document links. Like, you know, you have one blog or you have one site and it has it references like five others. That one is going to reference five others. Like I want to go through every single one, have like a complete understanding of everything. But that's just not how it works at jobs. Even a code base, no one is going to understand this massive code base unless you like write all of it by yourself, which is just not how companies work. And now we're kind of seeing a similar transition I think a lot of people are going through now with like agentic coding because it's kind of a similar concept where it's like now you might not even be looking at the code that you're actually producing yourself. So, it's it's kind of similar and I think this whole transition kind of reminds me of that where it's like you don't get to do some of the things that you used to enjoy, but it's it's still you know, that's that's life, [snorts] that's business.

</details>

### 职业发展与求职经历的背景

**Speaker B**: So, you graduated from University of Washington and you started work at the most obvious choice in Seattle. I guess the in Seattle the two obvious choices are Amazon or Microsoft and you got into Amazon and it should have been a smooth ride. Like you you made it into big tech into the big leagues and then you quit after 2 months. What happened there?

<details>
<summary>Original English</summary>

So, you graduated from University of Washington and you started work at the most obvious choice in Seattle. I guess the in Seattle the two obvious choices are Amazon or Microsoft and you got into Amazon and it should have been a smooth ride. Like you you made it into big tech into the big leagues and then you quit after 2 months. What happened there?

</details>

**Speaker A**: Yeah, first I want to say I actually went to Washington State University because I Yeah, I was actually not accepted to University of Washington. I wanted to go there, but I was not the best student in high school. So, I was fortunate enough that I grinded super hard for interviews, had a pretty good GPA. So, I got some interviews at Amazon, and it was DSA related, so I was able to, you know, crank that out. And then once I actually got into the world, and this is something I was self-aware about where I

<details>
<summary>Original English</summary>

Yeah, first I want to say I actually went to Washington State University because I Yeah, I was actually not accepted to University of Washington. I wanted to go there, but I was not the best student in high school. So, I was fortunate enough that I grinded super hard for interviews, had a pretty good GPA. So, I got some interviews at Amazon, and it was DSA related, so I was able to, you know, crank that out. And then once I actually got into the world, and this is something I was self-aware about where I

</details>

<!-- chunk 3/13 -->

### 关于工作环境和职业发展经历的看法

**Speaker A**: 我以前不是一个全面发展的人，尤其是在与人合作、处理各种软技能方面。我可以在自己待着，通过阅读文档、做一些事情，但与其他人合作对我来说非常困难。在亚马逊，我所在的组织是 Alexa，这听起来现在跟大语言模型（LLMs）的讨论相比有点让人感到失望，但我认为Alexa这个组织总体上并不是最好的地方。它不是一个运作顺畅的机器，有很多手动操作的事情在发生。那是一个压力非常大的环境。我想当我加入的时候，我在内部频道上看到了一条信息。我想是他们当时用了“chime”之类的词，但他却说：“这感觉像一份没有回报的工作。”我当时正在回顾团队频道的历史。那是在我加入前一周。我当时想，“哇，好吧。所以，现在这显然不是一个积极的团队环境。”

<details>
<summary>Original English</summary>

**Speaker A**: I was not a well-rounded person in that like working with people, people skills, and just anything of that. Like I could sit by myself, go through like documentation, work on things, but like working with other people was very very like difficult for me. At Amazon, the org I was in Alexa, which is kind of been gutted from what I hear nowadays with LLMs, but the team I was specifically in and I think Alexa the org in general was not the best place. It was not a well-oiled machine, a lot of manual stuff going on. It was a really stressful environment. I think when I joined I saw a message on the internal thing. I think it was I think they use chime at the time, but he said, "This feels like a thankless job." And I was like I was going through the history of the team channel. This was like a week before I joined. I was like, "Whoa, okay. So, this is like clearly not a positive team environment right now."

</details>

**Speaker A**: 我认为他们都是不错的同事。我并不责怪任何个人。我甚至对亚马逊没有怨恨。那只是一个糟糕的情况。所以，回想起来，如果我当时要重来一次，我可能也能挺过去。我确实知道一些事情。无论情况多么有压力和糟糕，我都能挺过去。但在当时，我真的不知道。而且当时我有一些个人问题。所以，出于某种原因，我只是下了一个非常冲动的决定辞职。事后，我有点后悔，因为你知道的，我感觉有一点解脱感，但然后我感觉更糟了，因为我在想，“好吧，现在我该怎么办？”

<details>
<summary>Original English</summary>

**Speaker A**: I think they were all like decent people. I don't blame any of the individuals. I don't even hold a grudge against Amazon. It was just a crappy situation. And so, I think in hindsight, like if I had to do it over again, I'd probably be able to survive. Like I kind of know things. It would have been stressful and and crappy either way, but I would have been able to get through it. But at the time, I just didn't really know. And like I had a lot of like personal issues at the time. And so, for whatever reason, I just made a very like impulse decision to just leave the job. Afterwards, I kind of regretted it because like, you know, I felt like a little bit of a relief, but then I just felt a lot worse because I was like, okay, now what do I do?

</details>

### 关于入职初期的感受和团队动态

**Speaker B**: 然后你能告诉我加入的时候感觉如何吗？你知道，最初的印象是什么？入职过程是怎样的？哪些事情让你觉得不太对劲？

<details>
<summary>Original English</summary>

**Speaker B**: And then can you tell me through on like what it felt joining, you know, like the first impressions, what the onboarding was like, and what were the things that were just were like not adding up?

</details>

**Speaker A**: 那非常紧张。所以，我们开了一个会议，因为在短短一到两周内，有五六个应届毕业生加入同一个团队。

<details>
<summary>Original English</summary>

**Speaker A**: It was very intense. So, we had a meeting cuz there were like five or six new grads who joined like within a one to two-week period. For the same team?

</details>

**Speaker B**: 是的，而且我想当时已经有四位经验丰富的工程师了。所以他们把团队人数翻了一番，大部分都是新人。你会想，“好吧，如果你介绍一大批新人，你当然得让他们快速上手。”但他们手头有很多截止日期要处理，所以感觉是经验丰富的人在工作，而我们其他人则有点像是在各自为战。所以我们开了一个会议，那就像是那种介绍新人的会议一样，对吧？而且再次说，我并不责怪任何个人，但没有人说什么。那些经验丰富的人也没有说任何话。经理不得不不断地提示他们多说话、要友好等等。我想他们只是想让会议结束，这样他们就可以回去完成他们的工作了，因为他们有截止日期要赶上。我看到一些人，我不是说每一位经验丰富的工程师都在凌晨三点工作，而我们明天早上八点或九点的会议。有些人在同一时间正在审查PR。所以我不知道这是否是那种文化，我并不认为经理会告诉他们你必须在凌晨三点做这件事。我认为是隐性的，你知道的，你大概知道现在是一个压力很大的环境。如果你是那个不在凌晨三点工作的人，你很可能会成为第一个被公司开除的人。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, and I mean, Amazon at the time, they had a target of 6% unregretted attrition every year, which meant that managers or like directors at their level had to have 6% of people leave the company unmarked as unregretted, which meant that either people quit on their own and you said like, oh, actually, this person was not great, unregretted, or you need to put people on performance improvement plans, and then have them leave and say like, "Yep, that was unregretted attrition." So, it's somewhat cutthroat in some of the orgs or most of the orgs.

</details>

### 关于离职的看法和对不同公司的对比

**Speaker B**: 是的，我几乎有一些关于那的阴谋论，因为我觉得我提交了三次辞职申请，他们才最终以某种方式接受了它，这让我感到惊讶。我在想，“为什么他们会在第二次之后还接受辞职？”我在想也许是因为看起来很糟糕，因为那是“非悔离职”，意味着你没有让他们走，他们选择了离开。而且因为那时太早了，我认为我甚至还没有资格进入绩效改进计划（PIP）。我想你通常在三到六个月后才会得到那个。我只待了两个月。再次说，我并不责怪任何个人。我对任何经理，甚至跳过经理都没有怨恨，因为我记得我辞职的时候，他们告诉我，“是的，有时候我们会让一些人走，之类的，但我不是这么看的。我只是把它看作是文化不匹配。”所以，他们试图表现得友好，但再次说，他们甚至没有试图隐藏它。很明显，那是一种紧张的文化。有些人会说有毒（toxic）。我会用“紧张”这个词来更宽容一些，但是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I almost have like some conspiracy theories about that because I think I gave my resignation actually three times before they finally like accepted it in a way, which was surprising to me. I was like, "Why don't like they accept the resignation even after like the second time?" I was thinking like maybe this is like because like it looks bad because it's regretted attrition where it's like you didn't let them go, they chose to leave. And and since it was so early, I think it was too early for me to even be on PIP. I think you get that like within 3 to 6 months or something. I left like 2 months in. And again, I don't blame any of the people. I have no grudges against any of the managers, even the skip manager, because I remember when I was quitting, they told me like, "Yeah, like sometimes we do get let people go and stuff like that, but I don't see it that way. I just see it as like a bad culture fit." And so, they were trying to be nice about it, but again, it was it was they weren't even trying to hide it. Like it was obvious that the culture is like intense. And some people would say toxic. I'll use the word intense to be more generous, but yeah.

</details>

### 亚马逊与谷歌的对比体验

**Speaker A**: 后来，你几个月后进入了谷歌。加入谷歌的感觉和在亚马逊上相比如何？

<details>
<summary>Original English</summary>

**Speaker A**: Later on, you were able to get into Google many months later. How did joining Google feel compared to Amazon?

</details>

**Speaker B**: 那是完全相反的经历。而且它们在很多方面都是截然不同的公司。比如商业文化，甚至技术文化等等。但我当时处于一种亚马逊PTSD模式，我当时想，“好吧，那是我第一次真正接触到专业经验。”我将这种感觉外推到了大科技领域，甚至在一般职业上。所以我当时想，“好吧，你就不应该提问题，你不应该和人说话，你不应该友好，你只是应该工作，并且尽可能地紧张。”但人们对我非常友好，所以我有点回报了这一点。但我没有问问题。我非常害怕。所以，我大部分时间是自己独立工作的。我接了一个项目，来自我的经理，结果这个项目比预期的要困难得多。但我仍然处于那种“我只是得把它做完”的状态。比如，“这是我的项目。我必须独立完成它。”因此，我很幸运地有了一位非常支持的经理和一个非常支持的团队。因为我选择自己做大部分工作，经理和团队都把我当成是独立的，而这正是你从初级到中级的晋升所需要的。我因为这一点得到了非常快的晋升，这也帮助我建立了很大的自信。这让我意识到，“好吧，我现在可以开始提问题了”，这很有趣。在被晋升之后，当我更习惯于像一个初级工程师那样提出问题时，我才更自在地提出问题。

<details>
<summary>Original English</summary>

**Speaker A**: Later on, you were able to get into Google many months later. How did joining Google feel compared to Amazon? It was the opposite experience. And they're kind of opposite companies in a lot of ways. Like the business culture, even the tech culture, and all that. But I was kind of in like Amazon PTSD mode where I was like, "Okay, like that was my first kind of real professional experience." I extrapolated that to be like everywhere in big tech or even just professionally in general. So, I was like, "Okay, you you're supposed to not ask questions, you're supposed to not talk to people, you're supposed to not even be friendly, you're supposed to just like work, and and just be as intense as possible." But people were very friendly to me, and so I kind of reciprocated that. But I didn't ask questions. I was very scared to. So, I worked on my own for the most part. And I was given a project uh from my manager that turned out to be more difficult than it was supposed to be. But I was still in the mode where I was like I just got to get it done. Like this is my project. Like I have to do it independently. And so that I was very fortunate in that where I did have like a very supportive manager, a very supportive team. And because I chose to do pretty much all the work by myself, the manager and team saw me as like independent, which is what you need to do to get promoted from like junior to mid-level. I was very lucky to get promoted like very quickly because of that. And that helped me build my confidence a lot. That made me realize like okay, like I can start asking questions now, which is funny. Where like after I got promoted is when I was like more comfortable like asking questions when like you'd expect that from a junior engineer more.

</details>

### 行业文化和领导层背景的思考

**Speaker B**: 这非常有趣，因为你只有在那个阶段才有了可能在亚马逊工作了两个月左右的专业经验，而加入谷歌时又多了六个月或更久。而且你如何能让那么多根深蒂固的反射在你进入一家公司时？你可以几乎想象一个以前有两三个工作经历的工程师，你知道，他们可能已经积累了来自其他公司文化的这些成见，或者他们学到了什么。当他们加入时，他们很难适应这家公司。是的，我不确定我们是否在行业内考虑过这个问题。

<details>
<summary>Original English</summary>

**Speaker B**: This is so interesting because you've only at that point had maybe 2 months of professional experience working at Amazon when you joined Google another 6 months or so later. And how you can have a lot of reflexes ingrained in you coming into a company. So you can almost imagine like another engineer who had like two or three jobs before, you know, they might have built up all these onset things that are coming from other companies' cultures or what they've learned. And they when they join, it it can be hard for them to adapt to the company. Yeah, I'm not sure we think about this in the industry.

</details>

**Speaker A**: 是的，我觉得你提到这一点很有趣，因为我在谷歌云的时候，很多领导层来自其他公司，比如亚马逊。我们有一个副总裁或总经理。他从亚马逊在那里待了几个月。而且他后来也很快离开了。我不知道那背后的确切故事，但我认为在整个行业中，很多文化是可以被映射的。谷歌的一些人不喜欢亚马逊。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think it's kind of funny you mentioned that because I was in Google Cloud where a lot of the leadership was from other companies like Amazon. And we had a VP or or GM. He joined it from Amazon for a few months. And he actually left shortly after that as well. Like I don't know the exact stories behind that, but I think there is a lot of like in the industry a lot of culture can get like mapped. A lot of people at Google didn't like the Amazon

</details>

<!-- chunk 4/13 -->

### 关于职业发展和技术路径的讨论

**Speaker A**: 经理们，因为……这就像是，他们不太可能带我们去旅行或者为我们付钱，因为他们知道亚马逊有那种节俭的文化，而谷歌没有。但是慢慢地，在我待在那里的时候，尤其是在裁员和所有这些事情之后，那个方向开始慢慢发展起来。

<details>
<summary>Original English</summary>

**Speaker A**: managers because it's like oh, they're going to be less likely to like take us on a trip or pay for us because they know that Amazon has like the frugality and Google doesn't. Uh but slowly like while I was there, it slowly started to get going that direction, especially with the layoffs and all that.

</details>

**Speaker B**: 在谷歌晋升，需要什么？这意味着什么？我知道有晋升文件。我知道有委员会。从你的角度看，你看到了什么？

<details>
<summary>Original English</summary>

**Speaker B**: Getting promoted at Google, what does it take? What does it mean? I know there's promotion packets. I know there's committees. What did you see from your perspective?

</details>

**Speaker A**: 相当直接，我想。从初级到中级的转变可能更容易，我想，而不是从中级到高级，随着你越来越高。在我的案例中，这基本上就是关于独立工作。然后一旦我幸运地被晋升了，我想大概一年后，几乎正好一年，这在谷歌是非常不常见的。我可以坐在这里，可能很谦虚地炫耀一下，表现得好像我就是个超级天才。但我认为真的需要投入精力，要聪明，但我想大多数人足够聪明。我认为它涉及到其他方面，比如合适的团队、合适的项目，因为如果你没有拿到正确的项目，你就没法证明自己。你可能是一个10倍、100倍的工程师，如果你在做相对容易的事情，你就不能真正说你解决了像一个非常困难的问题。所以，我认为这需要很多东西。谷歌有很多文档，比如每件事都需要用一些指标或一些工件来支持，比如一些设计文档。所以他们有一种可能为非常简单的事情制作太多设计文档的文化。有些人不喜欢那样，但我认为从流程来说，在谷歌是必要的恶，因为否则，有些工程师可能会只是做他们觉得可以做的东西，对业务没有影响，所以很难量化这一点。

<details>
<summary>Original English</summary>

**Speaker A**: Pretty straightforward, I think. Like going from junior to mid-level is probably easier, I think, than from mid-level to senior and as you get higher and higher. In my case, it was mostly just about like working independently. And then once like I was lucky to get promoted, I think in about a year, almost exactly a year, which is very uncommon at Google. And I could sit here and probably humble brag and act like I'm just like this super genius. But I think it was really I think there's like you have to one put in the work, two be reasonably smart, but I think vast majority of people are reasonably smart enough. I think it's it goes into the other things where it's just right team, right project, cuz if you don't get the right project, there's no way you can prove yourself. You could be a 10x, 100x engineer, and if you're working on relatively easy stuff, you can't really say that you solved like a really hard problem. So, I think it takes a lot of that. Google has a lot of like documentation where it's like every single thing needs to be supported with like some metrics or some artifact, like some design doc. And so, they have like this culture of probably producing too many design docs for really simple things. Some people don't love that, but I think in terms of like processes, it's just a necessary evil at Google because otherwise, some engineers might just like work on stuff that they just feel like working on, there's no impact to the business, and so it's hard to kind of like quantify that.

</details>

**Speaker B**: 那么在谷歌之前，你开始做现在被称为NeetCode的事情，很多人通过那里观看或听取会认出你或者甚至你的声音。你能告诉我这一切是如何开始的，以及在你还在谷歌工作的时候是如何继续下去的吗？

<details>
<summary>Original English</summary>

**Speaker B**: And then on the side, even before Google, you started what is now known as NeetCode, and a lot of people watching or listening will know you for you or even your voice from there. Can Can you tell me how that all started and how it continued as you were working at Google?

</details>

**Speaker A**: 是的，我最初是在辞去亚马逊之后开始的，我想大概6年前。我当时只是为了好玩和热爱这个游戏。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so I initially started after I quit Amazon, I think, in like 6 years ago. And I was doing it really just for fun and for the love of the game because

</details>

**Speaker B**: 你在录视频，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: You were recording videos, right?

</details>

**Speaker A**: 是的，我当时在做这些教程视频。我当时是：“我现在正在学习这个。我没有什么更好的事情可做。也许我可以帮助其他人。”我发现这非常困难，因为当时并没有真正的教程。只是有很多关于这些非常复杂的解决方案的论坛帖子。我当时坐在那里对着墙敲头，试图理解它。我想大多数人没有理解那些解决方案，因为那非常难。我想大多数人只是看了算法，对它有高层次的理解，但并不完全知道为什么它有效，但通常如果你在面试中看到这个问题，你可能就能通过面试。这回到了深思熟虑，我认为这对我是个性格特质，但我想它在LeetCode方面对我帮助很大。我深入研究了一些当时感觉有点毫无意义的事情，比如你为50个人制作一个视频，你做得很好，但这真的值得花几个小时去做吗？但我继续做，因为我喜欢它。大约在我开始持续制作视频一年后，我想我进入了谷歌。非常幸运地做到了那次面试过程在那时候相当容易。所以我有点退出了视频。当时我觉得这很有趣，但我现在在谷歌工作。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I was making these like tutorial videos. I was like, "I'm studying this right now. I got nothing better to do. I might as well like help some other people." And I found it very difficult because there weren't really tutorials at the time. There was just a lot of like forum posts of these really like complex solutions. And I'm like sitting there banging my head against the wall trying to understand it. And I think most people didn't understand the solutions because it's it's very hard to. Like I think most people just looked at the algorithm, kind of had a high-level understanding of it, didn't quite know why it worked, but it was good enough usually to if you saw that question in an interview, you could probably pass the interview. And uh this goes back to like deep thinking, which I think was a skill that it's more of a personality trait for me, but I think it helped me a lot with like the LeetCode stuff. I went really deep into things that at the time felt kind of meaningless, where it's like you make this video for 50 people watching, and you you you you did a great job, but it like clearly like it's not worth the several hours it takes to do that. But I kept doing it cuz I enjoyed it. About a year after I started making the videos consistently, I think I did get into Google. Very fortunate to do that. Interview process was pretty easy at that point, thankfully. So I kind of backed off the videos. I was like, this is kind of a like like it was fun, but I'm a like I'm at Google now for the rest of my

</details>

**Speaker B**: 你没有你的“是”。

<details>
<summary>Original English</summary>

**Speaker B**: You didn't have your yes.

</details>

**Speaker A**: 是的。然后我看到我实际上做了一个视频，告诉人们：“嘿，伙计们，我是通过这种方式进入谷歌的。你们可能以后不会这么经常看到我了。”而且有趣的是，在那之后，这个频道呈指数级增长，因为我想它增加了大量的可信度。“好吧，这家伙在进入谷歌后没有再制作这些视频。他实际上是在之前就制作了它们。”所以这就是他所做的事情，然后他进去了。所以这就像世界上最好的销售推销。我证明了这一点。我从零到一。所以这大概是一个很好的卖点。这对我个人有点困扰，因为视频没有改变，对吧？品牌变了，但这造成了很大的不同。是的，所以后来它呈指数级增长后，我当时想：“好吧，也许我会做一个网站。”然后那个网站当时是完全免费的，这是一个视频目录，让使用变得容易。而且它也病毒式传播了。然后在我被晋升后不久，我想：“嗯，也许我可以尝试全职做这个。”因为我真的很喜欢它。我在谷歌不能像我想在谷歌那样深入。我必须解决业务问题，但有了算法和数据结构，我可以深入到比大多数人愿意深入这些事情的更深处，但我有理由这么做，因为“好吧，我可以把这些东西解释给人们听。”所以是的，我认为那对我来说时机正好。然后之后，谢天谢地，目前进展还不错。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. And then I I saw that actually like I made a video telling people like, "Hey guys, I got into Google, by the way. You might not see me as much anymore." And and funny enough, after that, the channel like went exponential because I I think it added like so much credibility. It's like, "Okay, this guy didn't make these videos after he got into Google. He actually made it before." And so like this is what he did, and then he got in. So it's like it's like the best sales pitch in the world. Like I I proved it. Like I went from zero to one. And so it was I guess a really good selling point. And it kind of bothers me personally because it's like the videos didn't change, right? Like the branding changed, but that made like a really big difference. Yeah, and so so after it went exponential, I was like, "Okay, maybe I'll make like a website." And then the website was completely free at the time, which is really a catalog of the videos to make it easy to use. And um that went viral as well. And then so pretty shortly after I got promoted, I was like, "Huh, like maybe I can like try this full-time." cuz I really loved it. I I couldn't go as deep as I wanted to at Google. I had to solve business problems, but with algorithms and data structures, I can go super deep, more deep than most people would ever want to go into those things, but I had a reason to because it's like, "Okay, I can explain these things to people." And so yeah, I think it was just it was like the right timing for me. And then afterwards, uh thankfully it's like worked out so far.

</details>

**Speaker B**: 你在谷歌。你只是被晋升到了L4，这仍然是中级水平，但你现在有了到L5的路径，而我意思是，以前那是一个终点级别。现在L4是一个终点级别，但你知道，在谷歌你可以去L6、L7、L8，首席科学家。你有那种留在谷歌做这些事情或者创业或把这变成业务并深入算法编码的路径。你如何考虑这两个选项以及你会放弃什么，或者哪一个风险更大？

<details>
<summary>Original English</summary>

**Speaker B**: you were at Google. You just got promoted to L4, which is still mid-level, but you now had a path to L5, which I mean, it used to be the terminal level at the time. Now L4 is a terminal level, but you know, in Google you could go to L6, L7, L8, principal scientist. You had that path of like staying inside Google, do this stuff or start your business or turn this into business and go deep into algo coding. How were you thinking of the two options and what you would give up or what kind of, you know, how much risk would one or the other have?

</details>

**Speaker A**: 是的，我考虑过很多，因为尽管我并不喜欢谷歌的某些方面。我实际上很喜欢这家公司。我喜欢那里的员工，而且那不是那种超级有压力的环境。当我离开时，我的TL（当时基本上是我的经理）对我说：“我对你这么快晋升感到困惑，而且你可能又可以被晋升。”我确实考虑过这一点很多，因为这似乎是我余生要做的事情。我要在谷歌工作。我要晋升。我要成为我能成为的最好的工程师，但我只是觉得时机不对，我有机会自己尝试一些事情。也许那个机会不会永远存在。谷歌现在让人们甚至可以这样做，如果你离开，只要你和团队关系还不错，比如那样的东西，通常可以在一年内回来。谢天谢地，我当时是这样的。所以这让事情稍微容易了一些。我一直有朋友在做同样的选择。他们问我：“我应该离开谷歌吗？”上周我有一个朋友想全职做内容创作。我想这几乎是一个趋势，现在每个人都在辞掉工作去做自己的事情，但……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I thought about that a lot because even though I I didn't love certain things about Google. I actually really liked the company. I liked the people and it wasn't this super stressful environment. And when I was leaving, my TL, who was basically my manager at the time because my manager had

</details>

**Speaker B**: 那么转变是怎么发生的？你能告诉我你从一个工作日结构非常明确、有团队、一切都已解决的状态，转变为谷歌现在拥有惊人内部基础设施，你可以专注于业务问题仍然是编码的状态，到现在的状态是什么？

<details>
<summary>Original English</summary>

**Speaker B**: Well, I mean, I think a trend that in like we always live in bubbles, right? But but but in in like certain bubbles it it is. How was the switch? Can you tell me like you actually went from like okay, well, you made the decision, you went from like having a really structured work day, a team, everything was figured out. Google has amazing internal infra. You can just focus on okay, the business problem was still coding. And now you're like okay, you have the website, you have Git repository. What What was the switch like? And and you're like

</details>

<!-- chunk 5/13 -->

### 关于学习曲线和团队管理

**Speaker A**: 有点有趣，或者说好玩吗？什么很难？我曾在 Google 遇到过学习曲线的困难，但离开后，我也有过一个艰难的时期，比如要从某些工具上过渡过来，因为你很快就会习惯它们。比如他们有 GitHub，但我个人不太喜欢它。我知道现在很多人都在抱怨它的运行时间问题和类似的事情。但我对用户体验（UX）等方面也有其他问题。我认为 Google 有一些内部工具不是那么好，但也有一些非常棒的。而且有很多公司就是因为你在 Google 那里构建了一些东西，然后他们就说：“嘿，我们可以把它公开发布。” 然后他们离开，然后他们开始做 Cockroach Labs 或者一些疯狂的事情。

<details>
<summary>Original English</summary>

**Speaker A**: was interesting about it or like good and fun? What was difficult? >> I had a tough time with the learning curve at Google, but once I left, I had a tough time like transitioning away from some of the tools because you get used to it very quickly. Like they have like GitHub, I'm just not a huge fan of it. I know a lot of people are hating on it nowadays with like the uptime issues and stuff like that. But I have other issues with it around like UX and stuff.

</details>

**Speaker A**: 我认为 Google 有一些内部工具不是那么好，但也有一些非常棒的。而且有很多公司就是因为你在 Google 那里构建了一些东西，然后他们就说：“嘿，我们可以把它公开发布。” 然后他们离开，然后他们开始做 Cockroach Labs 或者一些疯狂的事情。

<details>
<summary>Original English</summary>

**Speaker A**: I think Google has certain internal tools that aren't so great, but they have some that are just like super super good. And there's have been a lot of companies that have been started just because like some that you had at Google built something and then they're like, "Hey, we could make this public." So, then they leave and then they start like Cockroach Labs or something crazy.

</details>

### 从团队工作到独立负责

**Speaker A**: 你从在一个团队里工作，现在却不得不自己做所有事情。那是个问题，还是对你来说是自然的事情？

<details>
<summary>Original English</summary>

**Speaker A**: What about like you went from from working on a team and now you just had to do everything by yourself. What was that an issue or that was kind of natural to you? >> Yeah, that was actually a huge thing for me where I It was hard to build a team. It was hard to like work with people.

</details>

**Speaker A**: 是的，那对我来说是一个巨大的事情，因为构建团队很困难。和人合作很困难。我刚开始就这么说的。最近大约六个月内，我适应了它，现在我终于感觉可以授权和管理人员了。最后，这对我来说花了很多时间，但一旦它真正起作用，你知道的，你经历了很多事情。你雇佣了一些人，你必须让他们离开。你弄清楚什么有效，什么合适。甚至如何激励人们。和人合作是非常不同的事情，因为每个人都是不同的。他们不是像机器那样，你只是给他们一个任务，他们就会吐出代码。人们是人。所以那些类型的事情对我来说学习曲线非常大。但现在我以前讨厌它，但现在我真的喜欢它，因为它在起作用的时候，当你找到一个合适的人，并且你感觉你可以为他们的成长做出贡献时，你会爱上它。你可以引导他们一点。你可以稍微控制一下方向，然后看到这能给他们带来多大的不同。我现在终于明白了领导力意味着什么，当它有效的时候。比如，当你是一个有效的领导者时，你可以在一个很小的团队中创造巨大的差异，但我想象当你达到更高的级别时，它可以带来巨大的影响。而且你会看到 CEO 有时候当新的 CEO 接管整个公司时，情况可能会好转，或者可能朝另一个方向发展。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah, that was actually a huge thing for me where I It was hard to build a team. It was hard to like work with people. Like I kind of said at the beginning. And I've only just recently, I would say within the last like 6 months, gotten used to it where now I finally feel comfortable like delegating things and like managing people. And finally like it it took a long time for me, but once it finally does click, you know, you go through like so many experiences. You hire some people, you have to let them go. You figure out what works, what's a good fit. And even just how to like motivate people. It's a very different thing like working with people cuz everybody's different. They're not like agents where you just give them the task and they're a machine. They're just going to spit out the code. Like people are people. And so those types of things there was a huge learning curve for me. But now and I hated it before, but now I actually really love it because it's like when it does work when you find somebody and they're a good fit and you feel like you can contribute to their growth. You can like guide them a little bit. Like you can steer the ship a little bit and you see like how much of a difference that makes to them. Like now I finally understand what leadership means when you like when it works. Like when you're an effective leader like you can make a magnitude of difference in like even like in a small team, but I imagine like as you get to higher and higher levels it can make a huge difference. And you see that with CEOs sometimes when a new CEO takes over the entire company either can go like up or maybe it goes in the other direction.

</details>

### 技术栈的演变与产品价值的衡量

**Speaker A**: 当你开始，比如你辞去 Google 时，你有一个列出你视频的网站，我猜非常简单的 HTML、CSS，可能还有一点 JavaScript。你构建了什么？背后的技术栈是什么？

<details>
<summary>Original English</summary>

**Speaker A**: >> When you started so like you quit Google you had a website that listed your videos I guess very simple HTML CSS maybe a bit of JavaScript. Uh what did you build and what what was the tech stack behind it?

</details>

**Speaker A**: 是的，最初当我制作那个免费网站时，我还在 Google 工作。所以我只是选择了一些随机的 Google 工具。我当时在使用 Google Cloud Firebase，因为它很容易使用。我后悔那件事，因为现在我认识很多人。我可能会想我现在应该用 Convex。我本该做别的东西，但我当时也用了 Angular，那是我在 Google 使用的技术。所以这说得通。也许我可以同时学习它。我也后悔那件事。但幸运的是，我们现在已经到了使用大型语言模型（LLMs）的阶段。所以迁移东西变得相对简单了。所以我可能会做那件事。但在构建应用程序本身方面，无论出于什么原因，我没有找到那么有趣的东西，因为通常不会有那么多深层次的问题。我认为有趣的事情来自于创新和以人们在乎的方式做事。没有人会太关心我的网站的性能或者我使用的技术栈，或者这些小事。他们会关心用户体验，比如我在视频中解释得好不好？因为如果解释很烂，没人会在意网站有多漂亮。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah, so initially when I made the free site I was still working at Google. So I just chose some like random Google tools. Uh I was using Google Cloud Firebase uh because it was so easy to use. I regret that one because now I meet so many people. I'm like oh maybe I should do Convex now. I should have done you know something different, but um I also did Angular at the time which is what I used at Google. So I was like it makes sense. Maybe I can just learn it at the same time. Regret that one as well. But thankfully we've gotten to a point now with LLMs. So like migrating things has become relatively trivial. So like maybe that's something I'll do. But in terms of like building the application itself for whatever reason like I I just didn't find that super interesting because there's usually not that many deep problems. I think the interesting things came from like innovating and like doing things in a way that like people care about. Like nobody's going to care that much about like the performance of my site or or the tech stack I use or like any of these like little things. They're going to care about like the UX, like how well did I explain something in a video? Cuz if the explanation sucks, nobody cares like how pretty the site looks.

</details>

### 业务价值与迭代的哲学

**Speaker A**: 这个视频是产品本身，还是大部分产品？

<details>
<summary>Original English</summary>

**Speaker A**: >> the video was is the product or or most of the product, right? >> Yeah, because it's education. So it's like if the education is bad, then nobody really cares. And and I I was very bad at building, but I think the idea, the concept, the value was good enough that no matter how crappy the site looked and like how bad like tech choices I made, the the business value like exceeded everything else. Like that mattered more. And so that taught me a lot about like prioritizing things that actually matter and then you can take shortcuts on the things that don't matter. 我认为这个视频是产品本身，还是大部分产品？ >> Yeah, because it's education. So it's like if the education is bad, then nobody really cares. And and I I was very bad at building, but I think the idea, the concept, the value was good enough that no matter how crappy the site looked and like how bad like tech choices I made, the business value like exceeded everything else. Like that mattered more. And so that taught me a lot about like prioritizing things that actually matter and then you can take shortcuts on the things that don't matter.

</details>

**Speaker A**: 这就教会了我很多关于优先考虑真正重要的事情，然后你可以对不重要的事情走捷径。我认为我看到了埃隆·马斯克有一个优化工作流程的四步或五步流程，一个流程是，你知道，你开始删减东西，有时你删得太多了，你意识到你犯了个错误，然后你可以慢慢地重新引入它。所以我采取了那种方法，因为我当时大部分时间都是自己工作的。我可能应该雇人来更快地移动，但我没有。因此，我采取了很多捷径，而且今天我仍然在采取捷径，因为这非常有价值。我有一个故事可以讲，人们可能会对此生气，但对我来说一直有效。所以我坚持下去。

<details>
<summary>Original English</summary>

**Speaker A**: And so that taught me a lot about like prioritizing things that actually matter and then you can take shortcuts on the things that don't matter. I think I saw Elon Musk has like this four-step or five-step process for optimizing like a workflow and like a process where, you know, you start you start cutting things out and sometimes you cut too much out and you realize you made a mistake and then you can like slowly introduce that back in. And so I took that kind of approach because I was mostly working by myself. I probably should have hired people to move faster, but I didn't. And so because of that, I took a lot of shortcuts and I still take shortcuts today because there's just so much value in it. Like I have a story I can tell that people probably get mad about, but it's worked so far for me. So I stick with that.

</details>

### AI 驱动的效率与基础设施的选择

**Speaker A**: 你有一个服务，我以前每月为它支付 3000 美元的服务费。然后我想在去年底或今年年初，当像 AI 驱动的代码生成的东西变得非常疯狂的时候，我还是个新人。我可能可以写出这个服务的自己的版本。你构建了什么服务？

<details>
<summary>Original English</summary>

**Speaker A**: >> What what's the story? >> So I have this service that I was paying like 3,000 a month for service and then I think late last year early this year when like the AI vibe coding stuff went really crazy, I was I was new. I could probably write my own version of this service.

</details>

**Speaker A**: 是一个代码执行服务。所以我想我可能可以在一个月或两个月内写出这个服务的自己的版本，但每月 3000 美元的机会与我能做其他事情相比，有更有影响力的东西可以做。但我当时想，好吧，有了这种“氛围编程”，也许我能在更短的时间内完成它，如果我运气好，可能几周时间。结果我实际上在两天或三天内就完成了它。这确实需要编码技能。如果我不知道如何写代码，我就做不了。但我三天就完成了。然后我部署了服务。现在我管理它，每月成本是 200 美元，而不是 3000 美元。但服务中有一个 Bug。我认为是内存泄漏或其他什么问题。所以，你部署了一个服务。每隔一两天，一个或两个实例就会崩溃，对吧？所以这显然存在问题，这是一个生产问题。我可以花时间去深入研究它并修复它。这是那种你会深入到“氛围编程”代码中，遇到问题，然后你就得真正深入挖掘问题出在哪里。所以我认为找到这个问题可能比三天要花更长时间。所以我甚至没有为此费心，因为我当时想，好吧，如果一个实例宕机了，我会让几个实例同时运行，对吧？我会让四个。所以如果其中一个宕机了，而且这种情况不会经常发生。

<details>
<summary>Original English</summary>

**Speaker A**: >> What service was it? >> It was like for code execution. And so I thought like probably I could write my own version of this for like within like a month or two, but the 3,000 a month opportunity of that versus like other things I could be working on, there were other more impactful things that I could be doing. But I thought, okay, with vibe coding like maybe I could get this done in less time, maybe a couple weeks if I'm lucky. And so, I actually got it done in like two or three days. And it did take coding skills. Like if I didn't know how to code, I would not have been able to do it. But I got it done in like three days. And then so I deployed the service. And so now that I'm managing it, it costs me like 200 a month versus like 3,000. But there's a bug in the service. I think there's a memory leak or something. And so so what happens is I have this service deployed. Every couple days, like one or two instances will crash, right? So there's clearly an issue, there's a production issue. I could spend the time to go into that and fix it. This is like one of those things where it's like you get into to vibe coding coding uh and you run into an issue and it's like, okay, now you're going to have to actually dig into the details to really understand like where the issue is coming from. So I think it would actually take me much longer than three days probably to find the issue. So I haven't even bothered with that because I'm like, well, okay, if one instance goes down, like I'll just have several instances running at the same time, right? I'll have like four. So if one goes down, and it doesn't happen that frequently.

</details>

### 总结与云平台解决方案

**Speaker A**: Neet 只是在谈论运营服务的时候，你不得不管理自己的基础设施，并在一个实例崩溃时处理新实例的启动。这是讨论本集赞助商 Google Cloud Run 的完美时机。作为软件工程师，我们真的只想写代码，而不是管理服务器或处理复杂的规模和配置。Google Cloud Run 是一个完全托管的平台，旨在让你在谷歌世界一流的基础设施上运行任何代码，而无需任何管理开销。无论你运行的是 Web 服务、批处理作业、代理还是微调后的 LLM，部署都像输入 `gcloud run deploy` 或连接你的 GitHub 仓库一样简单。让 Google Cloud Run 脱颖而出的一点是自动扩展和内置的冗余。Cloud Run 可以瞬间扩展以处理巨大的流量高峰，在空闲时缩放到零，所有这些都没有手动操作。

<details>
<summary>Original English</summary>

**Speaker A**: Neet was just talking about operating a service when you have to manage your own infra and taking care of spinning up new instances when one crashes. This is a perfect time to talk about this episode's sponsor, Google Cloud Run. As software engineers, we really just want to write code, not manage servers or wrestle complex scale and configurations. Google Cloud Run is a fully managed platform built to let you run any code on Google's world-class infrastructure with zero management overhead. Whether you're running web services, batch jobs, agents, or fine-tuned LLMs, deploying is as simple as typing gcloud run deploy or connecting your GitHub repository. One thing that makes Google Cloud Run stand out is auto scaling and built-in redundancy. Cloud Run scales up instantly to handle massive traffic spikes and scales down to zero when idle, all with no manual

</details>

<!-- chunk 6/13 -->

### 基础设施与自动故障转移的对比

**Speaker A**: 这意味着你对那些安静的项目支付绝对不花任何钱。我个人最喜欢的功能是 Cloud Run 如何为你内置了区域冗余和自动故障转移。在你不把这视为你可能不需要的东西之前，我最近刚报道了 Coinbase 因为其全球交易服务没有区域冗余而宕机了 10 个小时的情况。他们很可能没有它，是因为即使对于一个区域级别的自动故障转移，构建它也需要大量的工程工作。我个人很难说出许多其他基础设施服务能像这样直接提供开箱即用的这种故障转移能力。所有这些功能都让你能够专注于你的代码，而 Google 负责管理基础设施和日常运维。停止为基础设施发愁，开始部署吧。今天就去 cloud.run 试试看。

<details>
<summary>Original English</summary>

**Speaker A**: intervention. This means you pay absolutely nothing for quiet projects. Personally, my favorite feature is how Cloud Run handles zonal redundancy and automated failover for you out of the box. And before you dismiss this as something you might not need, I just recently covered how Coinbase was down for 10 hours because they did not have zonal redundancy in place for their global trading service. And the reason they most likely did not have it is because it's a ton of work to build automatic failover even for a zone level. And I personally cannot name many other infra services where you get this kind of failover out of the box. All these capabilities let you focus on your code while Google manages the infrastructure and operations. Stop worrying about infrastructure and start deploying. Try Google Cloud Run today at cloud.run.

</details>

**Speaker A**: 我还想提到我们的赞助商 Antithesis。Neet 在一个系列中谈到了内存泄漏，他知道这件事但只是没有时间去追根究底。如果你在分布式系统上工作过，你就知道那里存在深层 Bug。你没有办法溯源它们，所以你只能希望没有什么事情会真正灾难性的。有了 Antithesis，你不再需要依靠希望。Antithesis 让你能够轻松高效地修复和找到各种类型的 Bug，这样你就再也不必在发布质量和快速发布之间做出选择。让我来解释一下如何做。

<details>
<summary>Original English</summary>

**Speaker A**: I also want to mention our presenting sponsor Antithesis. Neet talked about memory leaks in a series that he knows about but just doesn't have the time to chase it down. If you work on distributed systems, you've been there. You know there are deep bugs there. You have no way to root cause them so you can only hope there's nothing really catastrophic. With Antithesis, you no longer have to rely on hope. Antithesis lets you fix and find all sorts of bugs easily and efficiently so you no longer have to choose between shipping quality and shipping fast. Let me explain how.

</details>

**Speaker A**: Antithesis 会在你的整个系统中运行一个恶劣的模拟。通过这样做，它在你用户发现问题之前就找到了每一个 Bug。而且由于这个模拟是完全确定的，Antithesis 不仅能找到 Bug，还能给你提供每个问题的完美重现。我知道这听起来更像科幻小说，但实际上它是底层硬核工程。Jane Street、Flight Data IO 以及 etcd 社区的 ship agent 编写的代码都对 Antithesis 进行了验证，因为他们知道它已经被验证过。要查看更多案例研究和细节，请访问 antithesis.com/pragmatic。这就是 antithesis.com/pragmatic。

<details>
<summary>Original English</summary>

**Speaker A**: Antithesis runs your whole system in a hostile simulation. By doing so, it finds every bug before your users do. And because the simulation is fully deterministic, Antithesis doesn't only find bugs, it gives you a perfect reproduction of every issue. I know this sounds closer to science fiction but it's actually hardcore engineering under the hood. Jane Street, Flight Data IO, and the etcd community ship agent written code with full confidence because they know it's been verified by Antithesis. To see more case studies and details, head to antithesis.com/pragmatic.

</details>

**Speaker A**: 还有关于 Neet 和他为什么很高兴离开一个未修复的生产 Bug 的故事。

<details>
<summary>Original English</summary>

**Speaker A**: And with this, back to Neet and his story on why he's happy leaving a production bug unfixed.

</details>

### 工程师的权衡与业务价值

**Speaker B**: 这是一个有趣的权衡，就像我认识的工程师一样，讨厌这种感觉，因为它就像有一个问题。修复它。但商业价值并不重要。比如，几乎没有停机时间。我的停机时间比 LeetCode 还少，而且我像有几个人在做这件事。所以，我只是觉得这是一种权衡。人们可以一方或另一方争论，但我认为现在对我来说，不修复它就很有意义。

<details>
<summary>Original English</summary>

**Speaker B**: It's an interesting trade-off where like engineer like the engineer in me hates that because it's like there's an issue. Like fix it. But the business value makes no difference. Like there has been practically zero outages. I have less outages than LeetCode and I'm like like a couple people doing it. So it's like I I just think it's like a trade-off. And people could argue one way or the other, but I think it just makes so much sense right now for me to not like fix it.

</details>

**Speaker A**: 但这非常有趣。所以，你为引擎支付了费用或者授权它，如果你理解它，它运行的是代码，对吧？所以当人们在你的编辑器中输入东西时，它会运行它，你可以检查它，它可以像运行其他解决方案一样运行你的问题。你使用 AI 辅助工具时，你知道你想构建什么。你以一种你认为应该有效的方式构建了这个引擎。你测试了它。它似乎在任何地方都有效。所以，你部署了它，花了 2 或 3 天时间。而现在你有了这个质量回归，但它对事情没有造成巨大影响。但我希望推动你思考这个问题。比如，你难道不认为这有点像我们看到的人工智能辅助编码或 AI 编程的典型情况吗？很多人都会说：“哦，有这个 SaaS 是我的公司在付费的。我是一个创始人，我在为它付费。我可以替换它。”然后你构建了一个次优的东西，并且勉强能用。然后又来了，修复它没有商业意义，或者现在太难了，因为你没有写所有代码，但当然更快了。

<details>
<summary>Original English</summary>

**Speaker A**: But this is so interesting. So, you paid for an engine or or licensed it that if I understand it it was executing code, right? So, when people like type out stuff in in your editor, it runs it and you can check it it can like run your problems as as other solutions. You used with AI assistance, you knew what you wanted to build. You built this engine in a way that, you know, you think it should work. You tested it. It seems to work everywhere. So, you deployed it and it took you 2 or 3 days. And and now you have this quality regression, but it it doesn't make a huge difference to the thing. But I want to push you on this. Like do you not think this this is a little bit typical of what we're seeing with AI-assisted coding or AI coding of like a lot of people are like again, like oh, there's this SaaS that my company is paying for. I'm a founder. I'm paying for it. I can replace it. And you build up something that is subpar and you kind of get by. And and then again, it it makes no business sense to fix it or it's now too difficult cuz you didn't write all of it, but of course it was faster.

</details>

**Speaker B**: 我认为我思考这个问题的方式是，如果我修复了问题，我可能可以分配一个更小的服务器池。所以也许我可以节省多花几百美元。而且我确实在想，这真的有区别吗？我真的想了很多。我是不是应该就修复它，因为它将来会成为一个问题？我最初测试它的时候，我只向这个服务发送了一小部分流量，而大部分仍然流向原始的那个。所以我只是运行了它几周，我当时就会写出这段代码。我确信会有问题。但我看到了几乎没有问题。就像服务器偶尔会宕机一次，一个服务的服务器会下线，但然后它在几分钟内就替换了。这就是我的想法。这根本不重要。比如，我的服务在技术上更快，因为我把它运行在更好的硬件上。是的，我只是觉得没人关心。用户没有向我提到过任何关于那方面的信息。现在更好。

<details>
<summary>Original English</summary>

**Speaker B**: So, the way I think about it is like if I did fix the issue, I could probably allocate like a smaller pool of servers. So, maybe I could save like a couple like a hundred bucks more. And I do think about like okay, does this actually make a difference? Like I've actually thought about it a lot. I'm like should I just fix it because like is it going to be an issue later on? And I like I initially tested it. I was only sending like a small amount of like traffic to this service and I still had most of it going to the original one. So, I just ran it for a couple weeks and I was like I would have coded this. Like I'm pretty sure there's going to be issues. And I saw like literally no issues. Like it's just up like okay, once in a while the servers will go one one of the services servers will go down, but then it just like replaced in like a couple minutes. That's just how I think about it. It's like it just doesn't matter. Like my service is technically faster because I run it on like better hardware. Yeah, I I I just see that like nobody cares. Like, no user has mentioned anything about that to me. It's better now.

</details>

**Speaker A**: 所以，是的。所以，我想也许从更宏观的角度来看，它整体上更好，因为它更便宜、更快，而且当然，确实存在权衡。在工程领域，现在有一个回归导致其中一个服务器崩溃了。所以你运行一个额外的。如果你需要的话，你有复制。而且总体来说仍然更便宜。所以，总的来说，当你打包它时，比以前更好。砰。这有点明显的商业决策。而且我想在工程中，当一个问题已经解决了并且足够好时，你需要变得多完美？

<details>
<summary>Original English</summary>

**Speaker A**: So, so yeah. So, I guess maybe to look at a bit better is is it's overall like better because it's cheaper, it's faster, and yeah, there is of course, there's trade-offs. Like, within engineering, there there is now a regression that crashes one of the servers. So, you run an additional one. You have like replication if if you will. And it's still cheaper overall. So, like overall as as you package it, it's better than before. Boom. Like, it is kind of a obvious business decision. And like I guess in engineering, like you there's a question like how perfectionist you need to go when a problem is already solved and is good enough.

</details>

**Speaker B**: 是的，没错。我一开始提到，这让我觉得你不能深入挖掘。即使对于这个问题，它实际上也让我感到困扰。但我猜我已经习惯了在优先考虑业务和思考实际价值方面，人们关心什么，什么将真正产生影响，不仅仅是短期内，也是长期内。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, that's right. I mentioned at the beginning that it like bothers me that you can't go super deep. And so, even for this, it actually does bother me. But, I guess I've gotten used to it in the sense of like prioritizing the business and just thinking about like the actual value, what do people care about, what's actually going to make a difference, like not just in the short-term, but also in the long-term.

</details>

### 准备面试与职业发展

**Speaker A**: 让我们谈谈这一点，作为一个创始人，尤其是一个软件工程师，在某个阶段你需要在思考业务。但是，人们在接受 NEET 代码的面试以进入大科技公司时，你知道，首先你需要跳过编码面试的门槛。你认为为这些数据结构和算法编程面试做准备能给人们带来什么对工作真正有用的东西？我说的不是算法本身，而是通过准备获得的实际其他东西。

<details>
<summary>Original English</summary>

**Speaker A**: Let's talk about this, the how like as especial especially as a founder, but even as a software engineer, like at some point you need to start to think about the business. But, the interviews that people are taking with NEET code in order to get into big tech, you know, they you first you need to to jump the hoop of coding interviews. What do you think preparing for these data structures and algorithms coding interviews gives to people that is actually useful on the job? And I'm not talking about the algorithms, but but but the actual the other things that you you gain by by preparation.

</details>

**Speaker B**: 是的，我想是这样。从我的角度来看，至少我经历了这个四年制学位。我没有作弊。所以我确保我理解了所有的基础知识和那些东西。然后我进入亚马逊，然后我就离开了。在那之前一年，当我进入谷歌时，我真的只是在做 NEET 代码。我制作解释视频，这让我学到了关于演讲和沟通，以及深入思考一个问题，也许是算法和数据结构之间的权衡等等。但我并没有真正做太多开发工作。然后当我进入谷歌时，我仍然能够晋升，尽管我认为就纯粹的原始编码和编码经验而言，我可能不如大多数人。但我仍然能够对于一个我以前从未用过的内部工具来解决的一个难题，我有那种可以坐下来，我可以梳理这些东西，我可以制定计划去尝试各种事情的能力。而且我大量地锻炼了我的沟通能力，这样我就可以对我的经理说：“好的，这是我在想的。”这有点像你在面试中做的事情，对吧？“好的，这是我的想法。这是我在想的。我要去做它，这样你才能和我保持同步。也许你有时间去研究一下并给我反馈，或者也许你没有。但只是为了让你知道我将要做什么。”所以很有趣的是，我确实从算法和数据结构中获得了很多思考方面的收获。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think so. From my perspective at least, I like went through this four-year degree. I didn't cheat through it. So, I made sure I understood like all the fundamentals and things like that. And then I got in Amazon, and then I I left. And then so, for that like year before I got into Google, I was really just doing NEET code. I was I was making the explanation videos, and that kind of taught me about like speaking and communicating, and like thinking deeply about like a problem and maybe like the trade-offs between like algorithms and data structures and stuff like that. But, I didn't really do much development. And then so, when I did get into Google, I was still able to get promoted even though I I think like in terms of just regular like raw coding and coding experience, I was probably sub par compared to most people. But, I was still able to like for a hard problem that I had no idea how to solve like using internal tools I've never used before, I had the skill of okay, I can sit down, I can go through this stuff, I can kind of make a plan of how I'm going to try things. And I worked a lot on my communication so that I could go to my manager and say, "Okay, so this this is what I'm thinking." Kind of like you do in an interview, right? Like, "Okay, this is the approach I'm thinking. Like, this is what I'm thinking. Like, I'm going to go ahead and do it just so you're on the same page. Like, maybe you have time to like look into it and give me feedback or maybe you don't. But, just so you're on the same page, like this is what I'm going to be doing." So, funny enough, like I do think I've gained a lot from algorithms and data structures in terms of like just thinking. Also on

</details>

<!-- chunk 7/13 -->

### 关于工程思维与技能的讨论

**Speaker A**: communication side. And also on the trade-off side, which I think is really what engineering is about. And it goes back to like what people are experiencing with like agent to coding and stuff. Everything is a trade-off. It's not really in engineering, there's no correct answer like there is in math or science. Engineering is about the best solution at the time. Like we're talking about like the memory leak issue with my service, right? It's a trade-off. Like, there's no correct answer, especially in business. There's no correct answer. And so, I think that's what a lot of people are maybe like missing nowadays where they're focusing maybe too much on the hard skills of like, "Okay, like can I write this loop? Do I know this particular data structure? Do I know like all these little things?" When I think they're forgetting to like zoom out and look at the bigger picture of like what engineering is even about in general. Because what you see in the real world is you'll see a really good engineer going from like one domain to another or really smart person like going from one to another and you you you see that and you think like what do they have that other people don't? It's usually not some like very specific skill that like they know this programming language super well. It's usually something related to that like it could be whether it's a data structures and algorithms or like some hard skill. It's like what you gain from that in general and I think that's like education in in general as well where like you go through like 20 years of your life learning about all sorts of subjects and that like molds you in a way that's very hard to articulate. It's very hard to be precise about like what exactly did you gain by like learning math and physics and speaking and writing and history but clearly there's a lot there.

<details>
<summary>Original English</summary>

communication side. And also on the trade-off side, which I think is really what engineering is about. And it goes back to like what people are experiencing with like agent to coding and stuff. Everything is a trade-off. It's not really in engineering, there's no correct answer like there is in math or science. Engineering is about the best solution at the time. Like we're talking about like the memory leak issue with my service, right? It's a trade-off. Like, there's no correct answer, especially in business. There's no correct answer. And so, I think that's what a lot of people are maybe like missing nowadays where they're focusing maybe too much on the hard skills of like, "Okay, like can I write this loop? Do I know this particular data structure? Do I know like all these little things?" When I think they're forgetting to like zoom out and look at the bigger picture of like what engineering is even about in general. Because what you see in the real world is you'll see a really good engineer going from like one domain to another or really smart person like going from one to another and you you you see that and you think like what do they have that other people don't? It's usually not some like very specific skill that like they know this programming language super well. It's usually something related to that like it could be whether it's a data structures and algorithms or like some hard skill. It's like what you gain from that in general and I think that's like education in in general as well where like you go through like 20 years of your life learning about all sorts of subjects and that like molds you in a way that's very hard to articulate. It's very hard to be precise about like what exactly did you gain by like learning math and physics and speaking and writing and history but clearly there's a lot there.

</details>

**Speaker A**: Sounds like you're saying that the effort of learning, the effort of going through doing hard things that might be pointless at the time or like solving problems that are maybe abstract or not for a specific thing, they add up over time?

<details>
<summary>Original English</summary>

Sounds like you're saying that the effort of learning, the effort of going through doing hard things that might be pointless at the time or like solving problems that are maybe abstract or not for a specific thing, they add up over time?

</details>

**Speaker A**: I think so a lot and this actually reminds me of a conversation I was having with Chip uh Heath. I think you've also had her on the podcast and uh she was cuz every nobody knows what like what's happening with AI. So we were talking about it and she mentioned that in her opinion it's very hard to know like what hard skills are going to be important, right? Like which programming language should you learn today? Like how high level should you go? Do you even need to know how to code, right? But as she mentioned that okay, like those are like impossible questions to answer but the one thing that she did understand is that systems thinking, this like broad concept that applies to engineering and computer science but also to many other disciplines as well. And the way I kind of understand it to use an example is like maybe in a construction, right? Like you walk around, you see like all these buildings being built, you see the workers and whenever I look at that I see like this big complex thing and all these like people doing all these like little things and then at the end of it, you have like this big building built that's like so complex. No one person could probably do that themselves, but it goes back to you have like the workers working on like the individual thing. But then you have this entire system, and somebody set up that system. Somebody set up those rules that, okay, a worker is going to do this. There's going to be this procedure. This is what we're going to check to make sure that there's no issues. We're going to verify things. We're going to have like this big process, this system of like making buildings, making sure that you don't have issues with that. And I think that is a skill that there's no like course for that, right? Like there's no like that's a hard thing. Like most people aren't building the system. They're they're like the worker bees. They're not like the ones architecting this whole system. But I think that's the skill that is so important because that's where like all the value comes from. You can you have these worker bees, but without the system, like nothing's going to get done. And and so, I think that type of thing is not going away. And it it's impossible to learn, but I think it takes like a lot of things to get there.

</details>

**Speaker A**: But I I'm going to push you a bit on that. Like is is is it Is it really systems thinking, or is it being learning a domain? Because systems don't exist in a vacuum, you know? You will have agricultural systems that are very specific to how the agriculture industry works. You will You will have If you're in a legal industry, like it is based on whatever country you're operating in. If If you're in a legal tech startup and healthcare, a healthcare tech startup looks very different in the US versus like the UK versus in Romania, etc. The people who are who are great system thinkers in one domain often are are they just really understand the domain. And you know, payments is one example where I worked in, which is very interesting complex Once once you get into it, like people start to move around in it because you go there. So, I wonder if it's There's There's There's abstract level system thinking, but there is also becoming a domain expert. And somehow they kind of overlap as well cuz if you are a domain expert, you must understand the system of that domain. And maybe if you understand multiple domains, you can get better at abstract level system thinking as well.

<details>
<summary>Original English</summary>

But I I'm going to push you a bit on that. Like is is is it Is it really systems thinking, or is it being learning a domain? Because systems don't exist in a vacuum, you know? You will have agricultural systems that are very specific to how the agriculture industry works. You will You will have If you're in a legal industry, like it is based on whatever country you're operating in. If If you're in a legal tech startup and healthcare, a healthcare tech startup looks very different in the US versus like the UK versus in Romania, etc. The people who are who are great system thinkers in one domain often are are they just really understand the domain. And you know, payments is one example where I worked in, which is very interesting complex Once once you get into it, like people start to move around in it because you go there. So, I wonder if it's There's There's There's abstract level system thinking, but there is also becoming a domain expert. And somehow they kind of overlap as well cuz if you are a domain expert, you must understand the system of that domain. And maybe if you understand multiple domains, you can get better at abstract level system thinking as well.

</details>

**Speaker B**: Yeah, no, I completely agree with that. And I think for me it's definitely hard to like quantify and articulate because it's very kind of like vague and I think you're definitely right though that like the skills, the the hard skills, like the knowledge and like the details of like certain industries and things like that that definitely matters. But I don't know. I guess like when I think about it, I think of it maybe you know people like this as well. Like there's certain engineers that are like they could go from one domain to another and you just trust them. Like you just know from working with them they're smart. Like they think in a certain way where like they could go from payments to like some completely other industry, real estate or something. And there will be like that learning curve for them. But some people for whatever reason they just learn faster, they just get it faster, they just perform better. And I don't think that this is something that was innate, that this was just handed down by like God that some people are just smarter than others. I think there's a lot that goes into it. I can't probably articulate it super well, but I think a lot of the things that people might say that like oh, it was a waste of time to learn this subject cuz I didn't actually use like those details on the job. I think that's wrong way to think about it. And I think that's what a lot of people are doing now with AI. Like hey, what what if I'm not going to be writing for a loops a couple years from now. Um I don't think those things are a waste of time.

<details>
<summary>Original English</summary>

Yeah, no, I completely agree with that. And I think for me it's definitely hard to like quantify and articulate because it's very kind of like vague and I think you're definitely right though that like the skills, the the hard skills, like the knowledge and like the details of like certain industries and things like that that definitely matters. But I don't know. I guess like when I think about it, I think of it maybe you know people like this as well. Like there's certain engineers that are like they could go from one domain to another and you just trust them. Like you just know from working with them they're smart. Like they think in a certain way where like they could go from payments to like some completely other industry, real estate or something. And there will be like that learning curve for them. But some people for whatever reason they just learn faster, they just get it faster, they just perform better. And I don't think that this is something that was innate, that this was just handed down by like God that some people are just smarter than others. I think there's a lot that goes into it. I can't probably articulate it super well, but I think a lot of the things that people might say that like oh, it was a waste of time to learn this subject cuz I didn't actually use like those details on the job. I think that's wrong way to think about it. And I think that's what a lot of people are doing now with AI. Like hey, what what if I'm not going to be writing for a loops a couple years from now. Um I don't think those things are a waste of time.

</details>

**Speaker A**: It sounds like it sounds like you're saying that it's you don't think it's a waste of time to go deep and understand things.

<details>
<summary>Original English</summary>

It sounds like it sounds like you're saying that it's you don't think it's a waste of time to go deep and understand things.

</details>

**Speaker B**: Yeah, absolutely. Especially when it's hard to do so.

<details>
<summary>Original English</summary>

Yeah, absolutely. Especially when it's hard to do so.

</details>

**Speaker A**: Absolutely, yeah. Let's talk about the hiring bar at at Fang and companies the the big tech companies. A lot of people are using NEET code to prepare for these interviews. You're getting feedback from them of you know like they will they will write to you when they succeed or they will write in frustration after many months they haven't. So you get a bunch of signal here. What are you seeing in terms of the just the algorithmic part, you know, the coding interview? Like are things staying the same, getting harder, getting easier?

<details>
<summary>Original English</summary>

Absolutely, yeah. Let's talk about the hiring bar at at Fang and companies the the big tech companies. A lot of people are using NEET code to prepare for these interviews. You're getting feedback from them of you know like they will they will write to you when they succeed or they will write in frustration after many months they haven't. So you get a bunch of signal here. What are you seeing in terms of the just the algorithmic part, you know, the coding interview? Like are things staying the same, getting harder, getting easier?

</details>

**Speaker B**: In terms of the format, like especially like at the early levels like juniors and stuff, it's still a lot of like algorithms and data structures, the format itself. I've definitely seen, I think, anecdotally, like people are mentioning that it's getting harder. At the same time, from the people who do pass the interviews, they still, like at

<details>
<summary>Original English</summary>

In terms of the format, like especially like at the early levels like juniors and stuff, it's still a lot of like algorithms and data structures, the format itself. I've definitely seen, I think, anecdotally, like people are mentioning that it's getting harder. At the same time, from the people who do pass the interviews, they still, like at

</details>

<!-- chunk 8/13 -->

### 关于技术难度和面试形式的讨论

**Speaker A**: 至少在像谷歌这样的科技公司，我可以说，难度与以前在美国的情况没有太大不同。我认为这因国家而异。比如，你会看到一些国家，比如印度，那完全不一样。那里几乎一切都是算法驱动的。就像是LeetCode、超级难的代码之类的。但在美国，我不认为它会那么疯狂，但它……嗯，是的，并没有那么疯狂。

<details>
<summary>Original English</summary>

**Speaker A**: at least at big tech companies like Google and stuff, I'd say the difficulty is not that different from what it was before, at least in the US. I think it varies by countries. Like, you'll see like some some countries, like India, it's very different. Everything's pretty much algorithms there. It's like leak code hards and super hards and stuff like that. But, in the US, I don't think it's that crazy, but it's uh yeah, it's not too crazy.

</details>

**Speaker B**: 是的，但我……我猜你知道，没有白板支持去准备面试是多么困难。这从来都不容易。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, but I I I guess like, you know, going without a without any support like in a whiteboard, it's so it's so hard to prepare for that. It it it's it's never been easy.

</details>

**Speaker A**: 是的，绝对如此。而且我认为发生了很多事情是面试中出现了作弊工具。所以，在过去的五六年里，大部分都是远程面试，这也在变化。我认为谷歌现在已经转向了现场面试，回到传统的白板格式。他们会让你在笔记本电脑上写代码，如果你愿意的话，但它还是需要面对面。有人会看着你写代码，而你可能无法通过那种方式作弊。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, absolutely. And I think the the one thing that's happened a lot is people like there's been cheating tools for interviews. And so, we've had like yeah, mostly remote interviews for the last like 5-6 years, and that's been changing a bit. I think Google has pretty much gone to on-sites at this point, back to the traditional whiteboard format. And they'll let you code on a laptop if you want to, as well, but it's going to be in person. Somebody's going to be watching you code, and you're probably not going to be able to cheat your way through that.

</details>

**Speaker B**: 你看到哪些面试形式，你知道，我们在谈论其他公司，特别是那些规模较小的公司时，他们正在进行什么实验？你认为哪些面试形式是很有前景的？比如，如果你经营一家小型或中型公司，你可能会考虑而不是……（此处语境略有跳跃）

<details>
<summary>Original English</summary>

**Speaker B**: What are interview formats that you're seeing, you know, where we're talking about other companies, especially smaller ones, experimenting? What are interview formats you're you're seeing or you think it they're actually kind of promising? Like, if you were running a small smaller mid-size company, you might actually consider instead of the And I you're talking about against yourself here.

</details>

**Speaker A**: 你在谈论 DSA 面试，尤其是在人工智能作为工具的情况下，什么有希望？任何可以标准化的、可扩展的流程，总有办法绕过它。而且绕过它的最好方法是雇佣一个实习生，然后你看到他们表现如何。我上周和很多公司谈到的是，很多小型公司可以通过试用期来解决这个问题。可能几天，可能一个月，甚至可能几个月，有点像实习期。我跟其他公司谈到那些说这给他们带来了困难的公司，因为如果你想雇佣一个已经有工作的人，那是不现实的。你不能真的那样做。但我相信，或者不相信，我倾向于那个方向，在那里我可以很快地感受到某人的 Lead Code 能力。比如，我不会花四次面试去问数据结构和算法的东西。我只是让他们做一些可能与我在工作中给他们的工作相似的事情，或者只是和他们聊聊。看看他们是怎么思考的。比如，他们能考虑权衡吗？我甚至不在乎他们给我一个问题的答案是什么。我关心的是他们为什么这么说？他们能说什么？这仅仅是因为他们在 ChatGPT 提示中看到过某样东西然后只是照着复述吗？还是他们真的可以深入探讨它？然后当你看看他们做的工作时，是同样的事情。比如，我问他们关于这件事。比如，你为什么这样做的？这个好在哪里？这个哪里不好？有什么可以改进的地方？我认为这对大型公司来说是一个难以规模化的形式。这就是为什么我不认为这会发生在大型科技领域。但对我来说，它有效。对于小型公司有效。但一旦达到某个规模，就更难做。

<details>
<summary>Original English</summary>

**Speaker A**: Any process that you have that's going to be standardized and super scalable, there's always going to be ways to game that. And the best way to get around that would be like hire somebody who's who's an intern and you saw how they performed. And what I've spoken to a lot of companies about the last week is that there a lot of small companies that can get away with it are doing like trial periods. It could be a few days. It could be like a month. It could be even a couple of months, kind of like an internship. And I've spoken to other companies that say that that's difficult for them because if you're hire if you're trying to hire somebody who already has a job, that's not going to be feasible. You can't really do that. But I've, believe it or not, have leaned in that direction where I can get a sense of somebody's lead code abilities pretty quickly. Like I'm not going to spend four interviews going through and asking somebody data structures and algorithm stuff. I just have them do work that might be similar to something I'd give them on the job or even just have a conversation with them. See how they think. Like can they think through tradeoffs? I don't even care about what answer they give me to a problem. I care about like what's like why did they say that? Like what what can they say? Is it just something that they like saw in like a ChatGPT prompt and are just regurgitating it or can they actually like talk through it? And and then when you look at like the work that they're doing, same thing. Like I ask them about it. Like why did you do it this way? Like what what what's good about this? Like what's bad about this? What could be improved? And I think it's a hard format to like scale for big companies. That's why I don't think that that's what's going to happen in terms of like big tech. But it's worked for me. It works for smaller companies. But once you get to a certain size, it's harder to do.

</details>

**Speaker B**: 是的，因为你基本上是人们在做工作，他们使用的工具并不重要。事实上，如果现在每个人都在使用 AI 代理，那么是的，他们也在使用它，你实际上能看到他们与他人相比是如何做的信号的。有趣的是，一种不太可能遇到招聘困难的公司是那些在开源领域工作的公司。他们通常会雇佣那些为他们的仓库做出贡献并已经添加了所有功能的那些人。你知道，对话可能会更多地是软技能方面的对话，因为我们看到了你的工作。比如，你无私地推动了产品的一些功能。很棒。我猜这就是开源的优势之一。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, cuz you're you're basically people are doing the work and it doesn't matter what tools they use. In fact, if if now everyone's using, you know, like AI agents, then yeah, they're using it as well and you actually get the signal of how they're doing compared to others. Interesting because one type of company that doesn't really have trouble hiring is the one ones who are working in open source. And they will often end up hiring the people who are contributing to their repos and adding all the features already. And you know, the conversation will probably be more of a soft skills conversation cuz like yeah, we're seeing your work. Like you've been selflessly pushing features to our our product. Awesome. And I guess that's kind of the upside of open source.

</details>

**Speaker A**: 我想 Dax 提到了这一点，因为我当时正在和一群和他一起工作的​​人谈话，他们刚刚得知他们要么已经在开源代码中做出贡献了，要么是 Dax 从他们之前在自己的项目中做过的开源工作那里了解到的，他们只是收到了他的私信，他就像说：“嘿，你对合作感兴趣吗？”所以他们已经有了可以展示的工作，而且如果你在公共领域做事情，人们可以对你如何工作有一个相当好的了解。

<details>
<summary>Original English</summary>

**Speaker A**: I think Dax mentioned this because I was speaking to a bunch of people that like work with him that that they just got that they were either like contributing to open code already or Dax like knew of them from open source work that they had done on projects of their own and they just got a DM from him and they're like and he's like, "Hey, would you be interested in working?" And so they already had this work that they could showcase and it's like if you if you're doing things in public uh people can get a pretty good understanding of like how you work.

</details>

**Speaker B**: 说到你如何工作，在 Neatcode 上，和你、你的团队，你们是如何工作的？你们使用什么工具？这些天你们实际手动写多少代码？

<details>
<summary>Original English</summary>

**Speaker B**: Speaking of how you work at Neatcode with your business, you and your team, how do you work? What tools do you use and how much code do you actually manually write these days if any?

</details>

**Speaker A**: 是的，我可以说在过去的六个月里，我们实际上一直在大量地产出功能和代码。现在大部分都是由 AI 编写的。在那之前情况不是这样。我过去长期以来是个很反 AI 的人，但人们有时还是认为我是，有时如果我是一个 AI 拥护者，他们会说：“Neatcode，你变了。发生了什么事？现在你成了 AI 的推销员。”但这并不对。我只是试图在它上面保持务实，因为我认为在我使用那些工具之前，它们就不是那么好的。而现在它们已经达到了一个点，我正在做的、主要是 CRUD 的工作，通常没有什么特别有趣的东西，除了代码执行服务。那可能是最有趣的。但我仍然在使用相当过时的技术。我在前端使用 Angular，这是一个没人喜欢的谷歌工具。我还在使用 Firebase，它虽然不是糟糕的，但能完成任务，但到目前为止它有点过时了。我正在使用 Google Cloud 和 TypeScript。但我会说最初，在几年前我写大部分代码的时候，代码质量非常差。我使用了 TypeScript，但我没有使用真正的 TypeScript。我有很多……是的，我有很多糟糕的代码。我把内联 CSS 放在那里。我只是为了尽快完成事情而做各种愚蠢的事情，因为我知道整个代码库。我知道我可以处理的某些技术，所以那对我来说是一种权衡，只是为了更快地移动。但现在有了 AI，我回过头来意识到那个权衡是值得的，因为我用 AI 清理了所有那些混乱的代码，这就是它的作用。它可以清理很多凌乱的代码，它可以重构很多东西，如果我真的想现在，我可以通过 AI 很快地迁移到其他工具。所以回到权衡来说，我认为只是思考一下你可能会做出错误的决定，但即使你做出了错误的决定，你也可以回去然后通过思考来尝试纠正它。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so I would say over the last 6 months actually we've been cranking a lot of features out a lot of code out. Most of it has been written by AI at this point. And before that really wasn't the case. I was actually a really big AI hater for a long time and people still sometimes think I am and sometimes if I'm like pro AI they're like, "Neatcode, you changed. Like what happened? Like now you're an AI shill." But it's not. Like I just try to be pragmatic about it because I think before I was still using the tools but they just weren't as good. And now they've gotten to a point where the work that I'm doing which is mostly CRUD, usually there's not that much crazy interesting stuff other than like the code execution service. That's probably the most interesting one. But I'm using like pretty outdated tech even. I'm using Angular on the front end, a Google tool that nobody likes. And I'm using Firebase which isn't horrible. It gets the job done but it's pretty it's a little bit outdated at this point. I'm using Google Cloud and TypeScript. But I would say initially actually like the first few years when I was writing most of the code very very bad code quality. I used TypeScript but I was not using like real TypeScript. I had a lot of any. Yeah. I had a lot of bad code. I was putting inline CSS. I was just doing all sorts of stupid stuff just to get stuff done as quickly as possible because I knew the entire code base. I knew like this like certain tech that I can just deal with and so that was a trade-off for me just to move quicker. But with AI now actually, I've gone back and I realized that that trade-off was so worth it because I cleaned all of that up with AI because that's what it's for. Like it can clean up a lot of like sloppy code, it can refactor a lot of things and if I really wanted to now, I could probably migrate to other tools very quickly with AI. So just to go back to the trade-offs, I think it's just about thinking like you might make the wrong decision, but even if you make the wrong decision, you can go back and then try to correct it just kind of by thinking about it.

</details>

**Speaker B**: 他也会在社交媒体上发布一堆他的“热言不讳”的观点。我不知道这是否是凌晨两点的事情，但你说的其中一个观点是，正如我引用的那样，现在到 2026 年，构建东西变得从未如此容易，但我会说它让真正创造价值变得困难了十倍。

<details>
<summary>Original English</summary>

**Speaker B**: He sends a post a bunch of her hot takes on social media as well. I don't know if it's like a 2:00 a.m. thing or But well one of them you said is as I'm quoting you, and now in 2026, it's never been easier to build things, but I would say that it just makes 10 times harder to actually build value.

</details>

**Speaker A**: 是的，我认为因为现在很容易实现很多事情，而且以前人们不实现那些东西是因为它们不值得做。比如在我的案例中，我转向了代码质量的例子。我认为那值得做，因为它很重要，它可以帮助你更快地前进，更易于维护。但在功能方面，比如一个网站，你现在可以随便扔进去一些没人真正关心的事情，而且你可以很快地做到这一点。比如每天添加一个新功能，但人们真的在乎那个吗？这让它变得更好吗？它可以是让事情……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think because it's so easy now to implement a lot of things and people weren't implementing those things before because they just weren't worth doing. Like in my case, I went to the code quality example. I think that was worth doing because it matters, it can help you go faster, it's more maintainable. But in terms of like features, like a website like you can just throw features in there nowadays that nobody really cares about and you can and you can do it so quickly. Like a new feature every single day, but do people actually care about that? Is that making it better? It could be making things

</details>

<!-- chunk 9/13 -->

### 关于速度与质量的权衡及AI对设计竞赛的影响

**Speaker A**: 事情变得更糟了。它可能会让事情变得更混乱。你现在有像那些杂乱无章的东西，你可能正在让网站运行得非常慢，因为你添加了所有这些没人使用的功能。所以我想速度在商业中很重要，但我认为决策也同样重要。如果你跑得太快，你就没有衡量你所做的更改的影响，你没有时间去做那件事，因为你只是专注于发布。然后事情就会倒退，情况会变得更糟，我们最近在Anthropic那里就看到了这一点，大概是上个月或者更多的时间里，事情出现了倒退，我记得前几天他们发布了一篇博客文章承认了这一点，但对他们来说，他们移动得太快以至于他们没有注意到。我看到鲍里斯说他正在回复很多评论，问我们为什么其他人没有注意到它，而现在他们注意到了。我认为这又回到了权衡的问题上，比如现在也许他们意识到，好吧，也许他们应该放慢一点速度，更专注于质量和这类东西，或者也许不那么快。

<details>
<summary>Original English</summary>

**Speaker A**: worse. It could be making things more confusing. You have like things that are cluttered, you're maybe making the site perform really slowly now with all these features you're adding that nobody's even using. And so I think speed matters in business, but I think decisions matter as well. If you're going so fast, you're not measuring the impact of the changes that you're making, you don't have time to do that cuz you're just focused on shipping. And then things regress and things get worse and we've seen that at Anthropic recently, the last like month or maybe more than that where things have regressed and I think just a couple days ago they put out like a blog post acknowledging that finally but it for them they were just moving so fast that they did not notice like I saw Boris saying like he was replying to a lot of comments asking like we haven't really noticed this like why is everybody else noticing it and and now they have and I think it's again just goes back to trade-offs like now that maybe they've realized like okay maybe they should slow down a little bit focus more on quality and stuff like that or maybe not

</details>

**Speaker B**: 我猜这确实带来了一点安慰，因为你知道我们以前知道，在AI之前，如果你移动得快，你通常会破坏一些你已经知道的东西。Facebook甚至有这个著名的口号。所以你可以更谨慎地行动，破坏更少的东西，但他们几乎就在这个滑块上——你移动的速度有多快，或者你有多鲁莽，与事情的稳定性相比。这在某种程度上是正确的。现在有了AI，我们有一段时间以为也许这不是真的，也许你可以带着质量快速移动，但我们看到Anthropic正在快速移动，而且他们正在破坏东西。我的意思是他们的业务正在增长，别搞错了，但仍然我认为这个真理没有因为AI而改变。

<details>
<summary>Original English</summary>

**Speaker B**: I guess it does give a little bit of relief that you know like we knew like pre AI it was pretty clear that if you move fast you typically you often break things you know Facebook even had this famous motto and so or you can be more deliberate and break fewer things but they're just almost at this slider like how fast you move or how reckless you are versus how stable things are and it was kind of true and now with AI we for a while thought like well you know maybe this is not true maybe you can move fast with quality but we're seeing with Anthropic like they're moving fast and they're breaking things and I mean their business is growing don't get me wrong but but still like I guess this truth did not change because of AI

</details>

**Speaker A**: 是的，这很有趣。甚至OpenAI他们也做过类似的事情，现在他们关闭了Sora，因为他们意识到，好吧，所以Sora就是社交网络，是的，是的，你看到到处都是这些猫视频，然后他们意识到实际上他们做得太多了，现在少做一些事情，现在他们有点重新关注编码，在更小的范围内进行，这实际上产生了更多价值。现在他们有点走Anthropic的路线，而Anthropic正在以相当快的速度前进，但他们主要专注于编码。所以我想这很有趣，因为可以看到像OpenAI这样世界规模最大的那些增长最快的公司甚至也在做这件事，他们不是试图做所有事情，他们正在重新聚焦，现在试图放慢一点速度。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, it's funny because even OpenAI they did like Sora now they're shutting it down because they realized like okay so Sora is the social network yeah yeah yeah the AI videos like these cat videos that you're seeing all over the place and so they realized like actually like they're doing too much like doing less things now and now they're kind of refocusing on like coding in a smaller set of things that's actually producing more value now they're kind of going the Anthropic route where Anthropic is going like pretty quickly but they they were focusing mostly on coding and so I think that's interesting as well to see that like actually playing out at the highest of scales that like this uh like the fastest growing companies in the world like OpenAI are even doing this like they are not like trying to do everything they're they're refocusing now and trying to maybe slow down a bit

</details>

**Speaker B**: 这有点矛盾，因为我们几乎在说，也许我们正在观察到AI，关注比快速执行很多事情更重要。哇。是的，很有趣。就像我记得那个开始这一切的论文，Transformer论文的标题是“注意力就是你所需要的一切”，那很有趣，它关注的是特定的标记，相关的标记最重要。

<details>
<summary>Original English</summary>

**Speaker B**: This is a bit contradictory though like we're we're we're almost saying that well, maybe one thing we're learning observing AI that focus is more important than executing quickly on a lot of things. Wow. Yeah, it's funny. It's like like I think even the the paper that started it all like the Transformers paper was titled like attention is all you need where it was funny it was like focusing on like the certain tokens, the relevant tokens like mattered the most.

</details>

**Speaker A**: 是的。你做的一个有趣的实验是为neatcode设计了一个重新设计竞赛，或者我想是那个网站。你为提交重新设计的任何人提供2500美元。你能告诉我进展如何吗？我仍然会评估结果，但到目前为止，从我所看到的那样，这有点令人失望。我不会试图对任何人生气或与任何人变得个人化，但对我来说非常明显的是，几乎所有的提交都是用AI创建的，这没问题。如果你要使用AI，那完全没问题。但再说一遍，在我与迄今为止谈话并问了他们一些关于你的设计、它看起来你做了一些选择，对吧？你移动了一些按钮，你移除了某些按钮，你移除了某些内容，你添加了某些内容。你为什么这么做？比如这样做有什么优点和缺点？他们无法回答这个问题。如果他们回答了，那显然是一个非常模糊的答案，他们没有考虑过它。当我花五分钟看他们的网站时，我能比他们更好地阐述设计上的事情。这很令人失望。我认为这不是智能的问题。我不认为它是。我认为这是努力、关心和技能集的问题。比如如果你拥有设计东西的技能集。但我不是。我绝对不是设计师。但就一个网站而言，无论业务是什么，你应该能够说“好吧，所以这是关于编码面试，我们试图向人们展示这很有趣，或者试图以非常清晰的方式解释它。”没有人能这么说。他们只是专注于设计的看起来有多漂亮。“哦，这个样式的颜色很疯狂。”但这和我关心的不是那件事。大多数人并不关心网站有多漂亮，如果他们不真正理解它是做什么的，或者它将给他们带来什么价值。我认为这就是用户体验（UX）所关心的东西。它不是关于某物有多漂亮。但我想在公平的意义上，对吧？这本来是一个竞赛。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so I'm still going to evaluate the results, but so far from what I've seen it's been a little bit disappointing. I'm going to try not to get like too mad at anybody or make it personal with anybody, but it's very obvious to me that practically all of the submissions are created with AI, which is fine. Like if you're going to use AI that's completely fine. But again, like with the few people so far that I've spoken to and asked them questions about okay like your design like it looks like you made certain choices, right? You you moved some buttons around, you removed some buttons, you removed some content, you added certain content. Why did you do it? Like what's the pros and cons of like maybe doing it this way? They can't answer it. And if they do answer it, it's clearly like a very vague answer where they didn't think about it. Like me looking at their site for 5 minutes, I can articulate things about their design better than they can. And it's just disappointing. It's like I don't think that's like a matter of intelligence. I don't think it is. I think it's a matter of like effort and caring and probably skill set as well. Like if you're if you just have the skill set of like designing things. Uh but but I don't. I'm certainly not a designer. But like in terms of a site, whatever like the business is, you should be able to say that okay, so like this is about coding interviews and we're trying to maybe show people that this is interesting or trying to explain it in a very clear way. Nobody can say that. They're just focused on like how pretty the design looks. They're like, "Oh, the the colors on this like the styling looks crazy." But, that's not what I care about. That's not what most people care about. Like, nobody cares how pretty a site is if they don't really understand what it's for or like what value it's going to give to them. I think that's what UX is about. It's not about like how pretty something is. But, I guess in all in all fairness, right? Like, this was a contest

</details>

**Speaker B**: 是的，你说的“如果获胜的设计将获得2500美元”有点改变了激励机制，因为这并不意味着你创建重新设计的报酬是2500美元。这意味着如果你赢了，你可以得到那笔钱。当然，提交的人越多，机会就越低。所以，如果我只是在这里逻辑推理，比如投入的努力值得我投入多少，假设有10个参赛者，可能就是250美元，或者如果是125美元。所以，最终，你只需要输入一个提示，把它给AI。而你看到的是很多低强度的提交。而且你看到没有达到同等水平。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, where you're like, "Okay, if the winning design will get $2,500." I guess it kind of flips the incentives a little bit because this doesn't mean that you are paid $2,500 to create a redesign. It means that if you win, you could get that. And of course, the more the more the more people submit something, the lower the chance. Therefore, if I'm just being logical here, like the effort that's worth me putting into it is let's say maybe if it's like 10 contestants, it's like maybe $250 or like if it's $125. So, in the end, of course, you just do a prompt, you give it to AI. And I I guess what you're seeing is you're getting a lot of low effort submissions. Uh and you're seeing there's like not not up to par.

</details>

**Speaker A**: 是的，我曾认为竞赛是做这件事的正确方法，因为那样我就不用雇人，不用筛选人们和那些东西。但回想起来，我想可能不是这样。我可能应该只是找到一个很小的人群，然后直接付钱给他们，然后看看作品，然后根据那来选择，因为我认为有很多低强度的提交。说实话，这很令人失望。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I thought that a contest would have been the right way to do it because then I don't have to like hire, I don't have to like filter people and stuff like that. But, in hindsight, I think it probably wasn't. I probably should have just found like and maybe even just a small pool of people and then just paid them up front and then just saw the work and then maybe chosen based off that because I think there has been like a lot of low effort. It's been disappointing to be honest with

</details>

**Speaker B**: 嗯，你活和学习。但我想这证明了只是给一个AI一个低强度的、低成本的提示，它不会产生神奇的努力，尤其是在设计方面。是的，我想是这样。而且我觉得很有趣，因为我认为有人可以就用笔和纸，只是描述他们试图做什么。比如让某物变得更好的主要选择是什么？就像我在我的网站上，即使是我用AI编写的部分，我也可以准确地阐述为什么一切都以某种方式定位。我可以回到说：“好吧，指标是这样，这个被使用最多，所以我希望它很突出。我想让它不像你在其他网站上看到的，有点不同，所以看起来不无聊。”但提交设计的那些人无法向我阐述这么多这些事情。我认为，就像我说过，如果你只是用笔和纸做，然后给AI，那么AI可以自己做。我不在乎某物看起来有多漂亮。我告诉他们我真正关心的是什么标准。而且我想，有些人只是没有遵循指示或什么的，那没关系，我想。

<details>
<summary>Original English</summary>

**Speaker B**: Well, you live and learn. But, but I guess it it does prove that just giving a prompt to an AI which is low effort, low cost, it will not result in magical effort, especially not with design. Yeah, I think so. And I think it's funny because I think somebody could just use pen and paper, just kind of describe like what they're trying to do. Like, the main choices that make something better. Like, I on my site, even the parts that I've used AI to code, I can articulate exactly like why everything is positioned in a certain way. I can go back to like, "Okay, like metrics, like this is used the most, so I want to make this prominent. I want to uh to make this like a little bit different than you've seen on other sites so it doesn't look boring, stuff like that. But, the people like submitting the designs, they can't really articulate a lot of these things to me. And I think, like I said, if you just do it on pen and paper and then give it to an AI, then the AI can just do it. Like, I don't care how pretty something looks. I I told them like what criteria I actually cared about. And uh I think, you know, some people just didn't follow the directions or whatever, and that's that's fine, I guess

</details>

**Speaker A**: 你几个月前的一个热门观点是，我们所知的编码的终点。让我们来谈谈它。蒂姆·奥雷利（Tim O'Reilly）在一年前写了一篇博客文章，预测事情会发生变化，而你当时正在反思这一点。

<details>
<summary>Original English</summary>

**Speaker A**: One of your hot takes from a few months ago, the end of coding as we know it. Let's let's talk about it. Uh Tim O'Reilly wrote a blog article that about a year ago where where he predicted that that things would change, and you were reflecting on that

</details>

**Speaker B**: 是的，我想这确实是这样。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think it's been really

<!-- chunk 10/13 -->

### 回顾与未来展望：编程、AI 与商业模式的演变

**Speaker A**: 有趣的是，很多人真的不常回过头去看实际情况。他们只是向前看。但我认为回顾一下事情是如何发展起来的非常重要，因为这可以帮助你预见未来会如何发展。而且，在代码变化和模型变得越来越好这一点上，这很有意思。但同时，我有点惊讶的是，我们仍然处于一种非常观望的状态。比如，公司仍在进行裁员等等。但在很多方面，情况并没有像我预期的那样发生太多变化。我的许多大科技朋友现在编码的方式完全不同了。但在商业运作方式方面，他们做的事情是相似的。大多数人仍然没有被裁掉。大多数人仍然在工作。他们比以前做了更多的工作。而且我认为公司有时会意识到，他们可能已经朝着人工智能的方向发展得太远了，所以他们试图重新平衡。这仍然是一场权衡的游戏。它仍然是一场“快速行动并打破现有事物”的游戏。

<details>
<summary>Original English</summary>

interesting

because

a lot of people

don't really go back to actually look at things. They're just like forward-looking. But, I think it's important to like go back and see how like things played out cuz that can help you like see how things are going to play out in the future as well. And it's been interesting like with how much coding has changed, with how good the models have gotten. At the same time, it's kind of surprising to me that we're still in like a very wait-and-see mode. Like, companies are still doing layoffs and things like that. But, in many ways, things have not changed as much as I would have expected. Like, a lot of my big tech friends, they're still like they're they're coding completely differently now. But, in terms of like the way the business is working, they're kind of doing like similar stuff. Like, they're all like most people are not getting laid off. Most people are still employed. They're still doing work. They're doing more work than before. And I think companies are sometimes realizing that they may maybe moved too far in the direction of AI, so they try to rebalance. It's still like a game of tradeoffs. It's still a game of like move fast and break things.

</details>

**Speaker A**: 我认为编程绝对会继续发生根本性的变化，你懂的，可能成为一个完全不同的领域。但对于商业方面的一些事情，了解生产价值以及工程决策中的权衡，这些东西是绝对不会消失的。我从来不这么认为。因为你可以让大型语言模型（LLM）来为你衡量权衡吗？我认为这是一种非常人性化的东西，用来评估工程中真正重要的事情。

<details>
<summary>Original English</summary>

I think programming is definitely going to continue to change definitively, and you know, maybe become a completely different field. But, I think a lot of stuff around like the business, knowing like the value to produce, and just like engineering decisions in terms of tradeoffs, that stuff is absolutely not going away. I I don't think ever. Because how can you have an LLM weigh like the trade-offs for you? I think that's a very like human thing to evaluate what's even important in engineering in general.

</details>

**Speaker B**: 是的，还有比如，你知道在编程的时候，当你思考我们写什么代码时，你需要构建一个功能。你需要知道任务是添加一个按钮，我不知道用户点击它的时候会发生什么，它会不会提交投诉之类的。这很简单。但实际上，点击“提交错误报告”这个简单的操作背后有很多边缘情况。它会检查状态。你需要知道上下文是什么，还有要说什么，什么样的用户是免费用户，付费用户？所有这些边缘情况、条件、领域、商业领域的所有这些东西都被捕获在代码里了，这意味着它们被捕获在你脑子里。但现在你正在提示它时，上下文仍然在那里，而且有人需要知道这有多重要。

<details>
<summary>Original English</summary>

Yeah, and also like for example, things like you know, in programming like when you think of like what is it that we code, you need to build a feature. You need to you know, the task is add a button where I don't know when when the user hits it it I don't know, it's it files a complaint. Something, you know, like so they can report a bug report a bug. That's a simple one. You know, like that is not just a simple behind the scenes of of like if button hit file a bug, it will have a bunch of like edge cases. It will it will check the state. You will need to know what the context is. Like and what what what to say, what kind of users are free user, paid user? Like there's all these edge cases, conditions, the domain, the business domain, all of these things and they were all captured in code, which means it's captured in your head. But now that you're prompting it, the context is still there and someone needs to know how important it is like

</details>

**Speaker A**: 是的，我认为变化是唯一没有变化的，因为变化只是不断发生。我不是想用这个词来玩双关语，但我昨天或今天看到微软正在进行自愿裁员，他们是买断协议。基本上，如果有人选择离开公司并获得一些遣散费。我查过，虽然我还没有确认，但我问了一个朋友，他说这是真的。这些买断协议是真的，但还没到年龄限制的时候。但基本上，他们只向特定年龄和特定工作经验的人提供这些优惠，这有点好笑。比如，如果你是某个特定年龄，我不知道确切的年龄，在微软工作了10到15年，他们只向这些人提供，我认为推测是因为那些人不太容易改变，不愿意学习一种完全新的做事方式。所以微软向他们提供，因为现在他们必须朝着新方向发展。我想当萨蒂亚最初接手的时候，他们做过非常类似的事情。我不知道当时是自愿的，但他们做了大量的裁员。主要是针对

<details>
<summary>Original English</summary>

Yeah, I think like change is the one thing that's not changing because change is just keeps happening and I didn't mean to make that a pun, but um like I just saw I think yesterday or today Microsoft is doing I think voluntary layoffs where they are Yeah, buyouts. Yeah, so basically if somebody chooses to they can leave the company and get like some severance. And I I saw I I haven't confirmed this, but I asked a friend and they they said it's true. The buyouts are true, but not like the age thing yet. But basically they're only offering this to a subset of people at like a certain age and certain amount of experience in the company, which is kind of funny. Like if you were like if you're like a certain age, I don't know the exact age and you have like 10 to 15 years at Microsoft, they're only offering it to those people, which I think to speculate I think it's because maybe those people are less prone to like changing, they're less willing to maybe learn a completely new way of doing things. And so Microsoft is offering it to them because like now they have to move in a new direction. I think they did something very similar when Satya originally took over. I think they did I don't know if it was voluntary at the time, but they did a lot of layoffs. It was mostly to people

</details>

**Speaker B**: 那那不是自愿的，2014年是这样。是的。那主要是针对很多有经验的人，特别是那些新员工不是。所以我想仅仅愿意改变，愿意以你没有享受的方式去做事情，比如我加入谷歌的时候，不得不做一些比我期望的更深入的事情。我认为这会非常重要。

<details>
<summary>Original English</summary>

That that was not voluntary in 2014, yeah. Yeah, and so that was to a lot of experienced people specifically and not to the new people. So I think just being willing to change, being willing to do things in a way that you didn't you don't maybe enjoy kind of like when I joined Google like having to to do things not going as deep as I would have liked. I think that's going to be pretty important.

</details>

**Speaker A**: 是的，你确实说过，你认为程序员或编程不会消失，即使编程发生变化也是如此，对吧？是的。我认为甚至到这一点，这就像是无法猜测。我的猜测和任何人的猜测一样好，但我就是看不到去思考消失。我看不到问题解决会消失。我认为它将发生剧变。有可能我们需要更少的程序员，但这种情况还没有发生过。比如每次出现重大的创新，比如云计算、更高层次的编程语言，无论出于什么原因，事情都不会导致程序员减少。而我本来期望是这样的。比如当你拥有可以解决那些非常困难的问题的云服务时，比如谷歌曾经不得不努力解决某些分布式系统问题。现在你可以直接使用AWS或GCP，让它为你处理好一切。所以你会认为我们拥有无限的软件，我们只是在做所有事情，一切都很容易，而且我们不需要那么多程序员，但这种情况还没有发生过。基于这一点，我不知道。比如你看到Replit和Lovable，现在任何人都可以成为程序员了。所以我不知道这是否是我们前进的方向，虽然它非常非常高层次了。

<details>
<summary>Original English</summary>

Yeah, and you you did say that you don't think there will be an extinction of programmers or programming even if programming changes, right? Yeah, I think even to this point again it's like it's impossible to guess. Like my guess is as good as anybody else's, but I just don't see like thinking going away. I don't see problem solving going away. I think it'll change dramatically. It is possible like we might need like less programmers, but even to this point that hasn't been the case. Like every single time there's just like the big innovation like cloud computing, like higher level programming languages, for whatever reason things do not like it doesn't lead to fewer programmers. And I would have expected it would have. Like when you have cloud like cloud services that can just solve these huge problems that were so difficult to solve. Like Google had to work so hard to solve like certain distributed system problems. And now you can just use AWS or GCP and just have that taken care of for you. So you would think that we just have infinite software where we're just like just doing everything and everything is easy and now we don't need as many programmers, but it just hasn't happened. And so based on that I don't know. Like you see things like Replit and Lovable where anybody can be a programmer now. And so I don't know if that's the direction we're going to go in where it's just very very high level, but

</details>

**Speaker B**: 但这非常有趣，因为一方面我们拥有这些越来越强大的基本组件，比如云计算。你会认为AWS、Azure和GCP、Oracle之间的组合是存在的。所以价格显然会尽可能低。但然后，你可能会遇到像DHH这样的人说：“好吧，我们在AWS上。我们每年花好几个百万美元。你知道，把亚马逊的服务去掉，然后在本地做。”而每个人都认为这会很贵。他们确实这么做了，现在他们正在进行大规模的节省。所以，这些抽象层运行起来几乎变得越来越昂贵了。这对大多数人来说没问题。但当你达到一定的规模时，你可能会开始投资软件工程师，构建自己的软件并维护它来降低成本，就像37 Signals所做的那样。所以我不知道在某些规模下，是否总是有价值，比如自己搭建你的技术栈，或者比你从预构建的东西中获得的东西更低一个级别。

<details>
<summary>Original English</summary>

But it's very interesting because on one end of course we have these primitives that are getting more and more capable like the cloud. You would think there's composition between AWS, Azure, and GCP, Oracle, and so on. And so, you know, the prices will obviously be as low as possible. But then, you have someone like DHH who is like, "Okay, well, we're in AWS. We're spending a few million dollars per year. You know, like get rid of the Amazon services and and just do it locally." Which everyone thinks is going to be expensive and and so on. And they do it, and they're now doing a massive saving. So, it's almost like the these abstractions are often becoming a lot more expensive to run. Which is fine for for most people. But when you get to a certain scale, you might start to invest in software engineers and building your own software and maintaining it to just reduce costs, which 37 Signals has done. So, I wonder if if anything, there might always be a value in at certain scale, you know, like rolling your own stack or or go a level lower than what you're getting from what whatever pre-built stuff.

</details>

**Speaker A**: 是的，我想是这样。我一直对事情如何发展感到有趣，比如从长远来看。工程不是一个科学。它有很多文化融入其中，你有一些公司在云方面，为什么MongoDB会变得这么大？我认为技术可能只是其中的一小部分，但我认为销售、营销和文化才是大部分。如果一家公司使用它，它可以滚雪球，然后整个行业开始使用某种工具。然后他们可能会意识到我们朝着不需要所有东西都在云的方向发展太远了。这并不更好。它并没有给我们节省那么多钱。而且有些方面，我们看到云计算服务变得非常复杂。现在是云驱动开发。你拥有所有这些东西，就像“好吧，你解决了这个问题，现在又遇到了一个新的问题。”有了LLM也是一样的。即使是AI的成本问题，一旦补贴开始运行（我们开始看到这种情况），我认为这将是一个非常大的问题，也许所有那些拥抱AI编程的公司现在都将减少它。

<details>
<summary>Original English</summary>

Yeah, I think so. I think it's always interesting to see how things play out like in the longer term. Engineering is not a science. Like there's a lot of culture that goes into it, and you have companies that like in the cloud, like why did a company like MongoDB get as big as it did? I think like the tech might be like a small part of it, but I think it a lot of it is just sales and marketing and culture. And if like one company's using it, it can snowball, and then like you have an entire industry using a certain tool. And then maybe they realize like actually like we went too far in the direction like we don't need to have everything in the cloud. Like it's not better. It's not saving us that much money. And some ways like we've seen cloud services get really really complicated. Now it's like cloud-driven development. And and like you have all these things, and it's like, "Okay, you solved one problem, and now you got a new one." With LLMs, it's like kind of the same thing. And even the cost issue with AI is probably going to be like once the subsidies start running out, which we're starting to see, I think that's going to be a really big issue where maybe all these companies that embraced AI programming are now going to like cut back on it.

</details>

**Speaker B**: 是的。你有一个疯狂的火车（指技术发展）。

<details>
<summary>Original English</summary>

Yeah. You had a wacky train

</details>

<!-- chunk 11/13 -->

### 关于AGI的讨论与技术进步的哲学思考

**Speaker A**: 我想谈谈这个话题。它涉及通用人工智能（AGI）。我不是AGI的狂热粉丝，因为我觉得谈论它非常像……你知道，很难定义。但是，让我们来谈谈它。假设存在一个AGI或者一个神一样的奇点。这些模型会非常了不起，我认为我们可以看到它们有局限性，但让我们向前跳跃一下。我们一直在追逐它？

<details>
<summary>Original English</summary>

**Speaker A**: I'd like to talk about it. It It involved AGI. I'm not a huge fan of talking about AGI cuz I feel it's very like you know like hard hard to talk hard hard to define. But but let's talk about it. This this was like you were saying like let's assume that there would be an AGI or a god-like singularity. These models would be amazing which I think we can see they have limitation but let's let's just jump like forward. What was this thought on on like how we were chasing it?

</details>

**Speaker B**: 是的，从哲学层面来说，感觉就像你试图达到无穷大，而你离它越近，你就离它就那么远，对吧？而且我觉得随着技术变得越来越好，你会觉得我们已经解决了生活。比如，我们有大量的资源，如果我们不想要的话，我们离每个人都有足够食物、水和住所的距离并不远。但生活某种东西，也许是人类的本性，或者某些东西就是不会改变。你想要更多，好吧，现在有了更高层次的编程。所以现在人们是在更高的层面竞争，而且随着它越来越高，人们仍然会在某个层面上竞争。比如，现在可能很容易构建一个应用，但营销和边缘情况以及这类事情将是需要解决的新问题。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think like on a philosophical level like it feels like you're trying to get to like infinity and it's like the closer you get you're the same distance away from it, right? And it's like that's where I feel like it feels like as like technology has gotten better you would think that like we've solved life at this point. Like we have like abundant resources and if we don't like we're not that far away from having enough food, water, and shelter for everybody. But it's like something about life like maybe it's human nature or something it just doesn't change. It's like you want more like Okay, now there's like higher levels of like programming. So now people are competing at like the higher level and like as it gets higher and higher the people are still going to be competing like on some level. Like maybe it's easy to like build an app now but there's going to be a new problem to solve like on marketing and like edge cases and things like that.

</details>

**Speaker A**: 但我也认为这可能是一个政治问题，因为我认为存在我们都应该为技术进步而高兴的技术。如果人工智能变得越来越好，如果它在某些方面真的取代了所有工作，那将是件好事，因为现在你可以做以前做不了的事情，比如农业。当那些消失的时候，很多人都很伤心，我肯定如此，但这对我们来说是一个净收益。我认为唯一不会是正面的原因是因为如果你生计取决于它，而且政治上你知道你不能赚钱，政府也不会照顾你。我认为问题就在这里。这更像是一个政治问题而不是一个技术问题。

<details>
<summary>Original English</summary>

**Speaker A**: But I also think like maybe this is like a politics thing because I think there's like technology which we should all we should all be happy that technology is improving. Like if AI keeps getting better if it really does replace every job in some ways that has to be a good thing because now you could do something you couldn't do before like farming. A lot of people were sad about that when when that went away I'm sure but it's been a net positive and I think the only reason it wouldn't be a positive is because like if your livelihood depends on it and like politics you know you can't make money and then the government isn't going to take care of you. I think that's where it becomes an issue. It's like it's more of a politics problem than a technology problem.

</details>

**Speaker B**: 是的，但我有一个有趣的观察是，当我们看到人工智能可以变得更好时。我仍然在等待软件能够让税务对普通人来说更容易申请。为什么我在我生活的每个国家，我都需要雇一个会计来申报我的税款，即使我的税单并不复杂？还有，我们谈论公用事业，当你的管道坏了，当你需要找水管工的时候。所以有一些日常事情上，我欢迎软件让事情变得更简单，但我过去没有看到太多进步，比如15多年了。而且现在连有了AI也不是。所以，我可能会是一个很好的触发点来看到那些事情的改进。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, but I I think know, my an interesting observation is like as we're seeing AI could make things better. I'm still waiting for the software to file taxes to be accessible to a normal person. Why do I in every country I live, I have to hire an accountant to file my taxes even though I don't have very complicated taxes. And that's one and we're talking utilities, when your pipe is broken, when you when you when you want to find a plumber. So there there's some everyday things where like I I would welcome software making things easier and I but I haven't seen much progress in the past like 15 plus years. And not not even right now with AI. So like I'm like could be a nice trigger to like see those things improving.

</details>

**Speaker A**: 是的，这很有趣，因为如果你看看历史，我认为我一直理所当然的一件事是进步总会发生，而且事情总会变得更好。但如果你看看历史上数千年的大部分时间，事情并不总是变得更好。有时你会看到文明变得非常伟大，然后它们就崩溃了，很多技术也随之丢失了。我不认为事情是预先注定会持续不断地变好的。我认为政治和政府方面将会有很多决定，政策将会被制定出来，我认为那将对人们的生活和他们所关心的事情产生非常大的影响。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think it's funny because like you look at history and I think one thing that I always take for granted is that like progress always happens and that things always get better. But if you look at like most of history for thousands of years, things didn't always get better. Sometimes you saw like civilizations get really great and then they kind of collapsed and a lot of the technology from that was lost. I don't think it's like preordained that things are just going to continuously keep getting better. I think like there's going to be a lot of decisions probably on like politics and government side where like policies are going to get created and I think that's going to have like a really big impact on what actually matters to people and like their lives and stuff like that.

</details>

**Speaker B**: 你提出的另一个观点是，过度炒作AI工具只会制造垃圾并侵蚀人们的技能。

<details>
<summary>Original English</summary>

**Speaker B**: Another one of your hot takes is how overhyping AI tools just create slop and erodes people's skills.

</details>

**Speaker A**: 是的，我认为很多人，特别是学生们，不幸地通过大型语言模型（LLMs）学习了一切。所以很多东西并不是真正的学习。他们只是在作弊，他们只是在做所有这些事情。然后他们会失去很多技能，我个人认为从长远来看，那将非常有趣，因为我们正在看到这种情况，甚至对于经验丰富的程序员也是如此。我有一个朋友告诉我他现在正在为面试做准备，但他几个月来没有手写太多代码了。所以现在对他来说很难重新投入到那个领域。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, I think a lot of people, especially students, are unfortunately learning everything through LLMs. So a lot of that isn't really learning. They're just kind of cheating and they're just doing everything like that. And then they lose a lot of their skills and I think long-term, that's going to be really interesting because we're seeing that with the even experience programmers. I had a friend tell me that he he he's like preparing for interviews now and he hasn't like handwritten much code in several months. So it's very hard for now him to get back into that.

</details>

**Speaker B**: 是的，这会是一个更长的时间框架，但我怀疑这是否会是这个副作用之一：更多的公司将进行面对面的面试，因为你消除了任何AI辅助。你可以真正和一个人交谈。然后面对面，你可以真正区分一个投入了努力、能够思考、敏锐并且能够把事情整合起来的人和一个在没有AI在指尖上的情况下变得僵化的人。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, this will be a longer time frame, but I do wonder if one side effect of this could be that a lot more companies will be doing in-person interviews because you eliminate any AI assistance. You can actually talk with a person. And then in-person, you can actually tell the difference between someone who has put in the effort and can think and is sharp and can put things together versus someone who gets like frozen without the AI being there at their fingertips.

</details>

**Speaker A**: 我觉得这真的很有趣，因为我认为也许公司不会在意。我可能就是那些会变得僵化的人之一。即使在我工作的时候，我写代码的能力很差，但我如果看一个文件，我会看到所有的导入、装饰器等等。我在这方面相当擅长编程。我以前有点像一个复制粘贴程序员，我只是复制和粘贴很多代码片段，然后替换变量之类的东西。我想我的观点是，也许某些事情实际上会变得不那么重要了。比如，如果你能写出你理解的长度的代码，人们可能就不太在乎了。就像我在一些AI辅助评估中看到的，他们会说：“好吧，你可以直接用AI去实现这个，如果你愿意的话，如果你有能力做到这一点。”但如果面试官问你，“好的，这个整数数组，这些整数在代码的上下文中代表什么？比如它们是某个东西上的数据点，还是两个东西之间的最短距离，或者其他什么的？” 你必须能够阐述出来并弄清楚。所以我觉得这很有趣。也许我给出的答案和我没有想法是一样的，但看到正在发生的轶事很有意思。

<details>
<summary>Original English</summary>

**Speaker A**: I think it's really interesting because I think like maybe companies won't care. I think I'm probably one of those people that would get frozen. Even when I was working, I was very bad at like writing code from scratch, but if I'm like looking at a file, I see all the imports, I see the decorators and stuff like that. Like I'm pretty good at coding that. I was kind of a copy and paste programmer where I'm just like copy and pasting a lot of snippets and then just replacing the variables and things like that. I guess maybe my hot take is that like maybe certain things actually will be less test Like maybe like people just won't care that much if you can actually handwrite the code as long as you can understand. Like that's what I'm seeing with like some of the AI assisted assessments. It's like, "Okay, like you can actually just go ahead and like implement this with AI like all of it if you want to if you're able to do that." But then if the interviewer asks you, "Okay, this array of integers, what do the integers actually represent in the context of like this code? Like maybe it's like data points on something or it's like the shortest distance between something or whatever, right?" You you have to be able to like articulate that and like figure that out. So, I think it's interesting. Like maybe I'm giving the same answer where like I have no idea, but it's interesting to see like the anecdotes that are happening.

</details>

**Speaker B**: 嗯，你有一个观点是，你认为个性特质现在比编码技能更重要，或者实际上大多数技能都更重要。

<details>
<summary>Original English</summary>

**Speaker B**: Well, one other take you have is you said that personality traits you think are now more important than coding skills or actually most skills.

</details>

**Speaker A**: 是的，也许用个性特质来表述不是最好的方式，但我认为你正在雇佣的人身上有某些东西。他们不是机器，对吧？他们不是“好吧，你看简历，Java程序员什么的”。他们不是那样。我认为人们，尤其是在软件开发这样的领域，非常开放，而且决策很重要，权衡很重要，沟通等等，所有这些都重要。当我招聘时，我几个月前雇了某个人，他有一些技能。显然，他正在通过他的计算机科学学位。他甚至还没有毕业。但他比我以前雇过的任何人都好得多，包括那些有经验的人，包括那些我可能可以雇佣的、在大型科技公司工作并拥有这些非常大的简历的人。然后我问自己，什么让这个人变好而另一个人变坏或效率低？这都归结于那个人。我认为在初创公司中，“代理”（agency）这个词是“高代理”——一个能把事情做完的人，永远不会拒绝任何事情。我认为这种态度非常重要：如果我不知道某件事，我会去学它。我不会说“这不是我的工作”或者“我不会深入研究这个问题”。每当我给这个人布置任务时，即使他们不知道如何开始，比如一周后他们就会对它所了解的一切都学到。那是一个完全新的领域。他们会学习所有东西。我认为这种类型的个性特质很难用语言描述。也许“代理”（agency）是最好的术语来形容它，但我……

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, maybe personality traits isn't the best way to phrase it, but I think there's something about like a person that you're hiring. They're not a machine, right? They're not like Okay, like you look at the resume like okay, Java programmer or whatever. They're not that. I think people, especially in fields like software development, which are very open-ended and like like decisions matter, trade-offs matter, communication, all that stuff matters. When I'm hiring people, I hired somebody a few months ago and they had certain skills. Like obviously they were going through like their CS degree. They still haven't even graduated yet. But they are far better than practically anybody I've ever hired before, including people that are experienced, including people that I probably could have hired that are working at like big tech and like have like these really big resumes. And then I ask myself like what is it that makes like this person good and another person bad or or less effective? It just goes back to the person. I think like in startups the term is agency. Like somebody who's high agency who's just going to get things done, who's never going to like say no to something. I think like that attitude is really important of like okay, if I don't know something, I'll just learn it. Like I'm not going to say like that's not my job or I'm not going to like dig deep into that. Like anytime I give this person a task, even if they have no idea like how to start it, like a week later they'll have like they'll have learned like everything about it. It's like a completely new domain to them. They just like learn everything. I think like those types of personality traits, it's hard to describe that. Maybe like agency is the best term for it, but I

</details>

<!-- chunk 12/13 -->

### 关于信息获取与产品市场契合度

**Speaker A**: 重要的是任何你在这个阶段需要的信息，你可以通过提示来获取，对吧？比如，我有一个特定的编程问题。如果你知道该问什么问题，你就可以从提示中得到答案。而知道该问什么问题，只是付出了努力的问题。

<details>
<summary>Original English</summary>

**Speaker A**: think that matters the most because any information that you need at this point, you can kind of just prompt, right? Like Okay, like I have like this programming specific question. You can just You can just get it out of a prompt if you know the questions to ask. And knowing the questions to ask is just a matter of like I think putting in the effort.

</details>

**Speaker B**: 是的，我也有感觉到你没有提到这一点，但它就像是能量、专注力、想要解决某个特定问题。这很有趣。我一直在和一些正在构建初创公司的人交谈。显然，他们中的许多人都在做人工智能或者构建人工智能基础设施，以及他们如何努力找到产品市场契合度。即使如此，你知道，他们可以比以往任何时候都更快地构建，但要让团队采用也变得没有变得更快了，简单的事情开始变得重要。例如，亲自与潜在客户交谈，比如去参加技术聚会，住在科技中心或者你可以更经常去的地方，获取反馈，在一家大公司内部获得你的第一个客户。而且这些都没有与代码本身有关。当然，他们创造了一些他们认为很酷、很创新、很不同的东西，但现在有太多事情是相似的。顺便说一句，他们都有竞争对手。他们现在需要说服他们为什么他们更值得信赖，他们值得冒险，等等。这很大程度上取决于一个有魅力、擅长说服人的创始人。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, so I like agency. I'm also sensing you didn't mention it, but it's like energy, focus, wanting to solve something specific. And this is something interesting. I I I've been talking to a few of people who are building startups right now. Obviously, a lot of them are to do with AI or like they're building AI infra, and how they're struggling to find that product market fit. Even though, you know, they can build faster than ever, but it has not gotten any faster to get teams to adopt, and simple things start to matter. For example, talking to a potential customer in person, like going to a tech meetup, living in a tech hub or where you can go more regularly, getting feedback, getting your first customer inside of a big company. And none of these have to do with the code itself. And of course, they created something that they think is cool and innovative and different, but there's now so many things that are similar. By the way, they all have like competitors. They now have to need to convince them why they are more trustworthy, they're worth being bet on, and so on. And it's it's it's a lot of it does have to do with like a charismatic founder who is good at convincing people, all right, try my stuff. It It actually helps.

</details>

### 内容表达与价值传递的艺术

**Speaker A**: 是的，这也是我从 YouTube 学到的另一件事，因为如果你在制作视频试图解释某事，没有人关心你有多正确。没有人关心你有多聪明。在代码论坛上，人们并不关心你是否有一个超级疯狂的解决方案，那真的很令人印象深刻和很有效，如果你不能解释它的话。因为他们关心的是你能为他们提供什么价值。如果你能用他们能理解的方式说话。当我制作那些视频时，我会更清晰地表达某些事情，我会重复某些内容。我只是想让视频非常易于消化。无论是一个DFS还是滑动窗口或者任何算法，技术上任何人都可以把它做对。到这个地步，你现在可以让一个LLM直接吐出来给你。但我认为它的人性部分，就是了解人们，弄清楚他们到底在寻找什么，他们真正关心什么，我认为那是一件非常重要的事情。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, that's one of the things I actually learned from YouTube as well, because if you're making like a video trying to explain something, nobody cares how correct you are. Nobody cares how smart you are. Nobody cares, like in the lead code forums, if you have this super like crazy like solution that's really impressive and really performing, if you can't explain it. Because what they care about is like the value you can give to them. If you can speak in a way that they can understand. When I was making those videos, I would enunciate certain things more I've like like emphasize certain points. I'd repeat certain things. I just tried to make the video just very digestible. Whether it's a DFS or sliding window or whatever algorithm, anybody can technically get it correct. You can at this point have an LLM just kind of spit it out to you. But I I think like the human part of it, just knowing like people, figuring out like what exactly they're actually looking for, what they actually care about, I think that's something that's Yeah, that's pretty important.

</details>

### 关注度经济与个人魅力

**Speaker B**: 所以 YouTube 很有趣，因为今天的 YouTube 至少我希望它大部分是人类观看的。所以，我希望每一个观看都是一个人类。我确信那里有一些机器人，但谷歌正在与之抗争。这是一种真正的注意力经济，对吧？就像那个最订阅或观看最多的 YouTuber Mr. Beast，他捕获了更多的目光，更多人们的注意力，而注意力就是货币。有八十亿或者更多的人，也许在线视频的访问权限的人更少一些，但这有点像一场游戏。如果你在这个领域——也就是软件工程中——做得很好，你已经很厉害了。你在 YouTube 上学到什么能让你成功的地方，让人们关注你，他们会给你时间，而时间是一种重要的有价值的货币，这可能对科技公司、初创公司尤其相关。

<details>
<summary>Original English</summary>

**Speaker B**: So, YouTube is interesting because YouTube today at least it's I would hope it's mostly watched by humans, people. So, every single view I would hope is a human. I'm sure there's some bots there, but Google is fighting them. And it's a real attention economy, right? Like it's the you know, like the Mr. Beast who's the most subscribed or watched YouTuber, he captures more eyeballs, more people's attention, which is the currency. There's 8 billion or so or a bit more people, maybe fewer of them having access to the online videos, but it's kind of like almost a game. If if it's a game, you've been pretty good at it in this niche, which is software engineering. What is something that you've learned on what works in becoming successful on YouTube where people pay attention to you, they give you their time, which is an important valuable currency that might be relevant for tech companies, startups especially.

</details>

### 真实性与建立信任的难度

**Speaker B**: 我认为很多公司都在努力解决这个问题。我一直在和一些在做同样事情的开发者关系的人交谈，那里有时有点像一场游戏，有点像政治斗争，就像是包装、对吧？比如你如何表达事情，如何呈现事物，如何呈现自己。而且我认为建立真实性也很重要。我认为这是公司可能没有正确处理的一个大问题。有时候他们甚至会和AI实验室一起做，你是在说现在OpenAI和Codex的人都在Twitter上。他们正在与人互动。他们甚至在与那些有时批评他们的人互动。我认为这很重要。因为这种真实性通常非常重要。人们可以察觉到虚假。他们可以……对我来说，即使我说的有些不相信的东西，我觉得那也很明显。然后人们就会失去兴趣。他们不会听你说的某个词了。所以，你说的内容并不那么重要。你必须以一种很难建立的方式来建立他们的信任。这需要时间才能达到那里。但一旦你有了它，它就非常重要了。

<details>
<summary>Original English</summary>

**Speaker B**: I think a lot of companies struggle with that. I was speaking to a couple dev relations people that are working on the same thing where it's it's kind of a game sometimes where it's a little bit of like politicking where it's like, you know, like it's about packaging, right? Like how you say things, how you present things, how you kind of like present yourself. And it's also about I think being like authentic. I think that's a big thing that companies maybe don't always get right. And sometimes they try to like even with like the AI labs where you're saying that like nowadays like OpenAI and like the Codex people, they're on Twitter all the time. They're interacting with people. They're even interacting with people that sometimes criticize them. And I think that matters. Like that authenticity usually matters a lot. People can like smell the fakeness. They can they can tell. Like even for me, if I'm like saying something I don't quite like believe, I think it's so obvious. And people can tell. Then they just get turned off. Like they're not going to listen to a word you say at that point. And then so it doesn't really matter what you say. You have to like build their trust in a way that it's hard to build. It takes time to get there. But once you have it, it matters a lot. It matters a lot.

</details>

### 影响力与人格化

**Speaker B**: 有趣的是，我一直想如果 Claude Code 没有由 Boris 创建，它会像现在这么大吗？Boris 是你在 YouTube 频道上能看到的工程师。他也在这个频道上。他是一个非常容易接近和谦逊的人。至少我是这样认识他的。他在社交媒体上分享他如何使用 Claude Code。有很多关于 Boris 的内容。比如，这不仅仅是一个由 Anthropic 公司这样的公司创建的工具。不，实际上是 Boris 创建了它，他正在致力于它，他修复你的 Bug，你可能会说：“哦，它有这个 Bug。”而他回复：“我在你的提及中。”我现在注意到 OpenAI 是用 Codex 来构建这个东西的，但现在 Tibo 是 Codex 的负责人，他回复，他做和 Boris 类似的事情。所以，我一直在想，这种个人角度——Claude Code 在软件世界中是收入最大的企业之一，我认为它们成本是数十亿美元。很难追踪具体有多少。所以它是一个与一个人紧密相连的巨大企业。

<details>
<summary>Original English</summary>

**Speaker B**: It's interesting because I do wonder if Claude Code had been had become as big as it has if it was not created by Boris. Boris, the engineer who you can see on YouTube channels. He was on this channel as well. He's a very relatable and I think humble person. At least that's how I got got to meet him. He is on social media. He shares how he uses Claude Code. There's a lot of Boris. Like this is not just a tool that is like some by corporate called Anthropic. No, it's actually Boris created it and he's working on it and he's fixing your bugs and you say like, "Oh, it had this bug." And he reply He's in your mentions. And I I now notice OpenAI, it's Codex used to be this thing built by OpenAI, but now it's Tibo who is the the head of Codex and he replies and he does the same similar things as Boris. So, I I do wonder if this, you know, like the personal angle where it's it's here Oh, and Claude Code is one of the biggest businesses in the software world in terms of revenue. I think they cost multiple billions. It's hard to track how much. So, like it's a huge business tied to a person.

</details>

### 成为有影响力的技能

**Speaker B**: 我讨厌“网红”这个词，但似乎一切都在朝着让公司也必须成为一个人的方向发展。他们必须有一个个性。他们必须……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I hate the word influencer, but it does seem like everything is going in the direction of like even for companies like they have to be a person now. Like they have to be a personality. They have to >> Approachable maybe?

</details>

**Speaker A**: 是的，是的，像可接近。是的，有亲和力。就像一个人类一样，对吧？不像仅仅是一个企业人物。甚至对于CEO来说，有时这也有帮助。有时它会适得其反，但我不会说任何名字，但嗯，我认为这很有趣，而且我认为有些公司有很多这样的东西。我想你可能比我更了解 Meta，但 Meta 有一个内部的 Facebook 或者类似的地方，当你发布产品时，你必须展示它。你必须提及它。你必须试图吹嘘它。是的，没错。推广它是一种技能。我没有预料到我会成为网红或 YouTuber，但它是一种技能，我认为每个人都应该向这个方向倾斜。就像不是每个人都必须做 YouTube，但无论是在 LinkedIn 还是 Twitter 上，我认为值得把你自己展示出来，慢慢形成观点，并与人们互动和一些事情。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, well, you said like maybe not everyone has to do it, but really it is you've had a pretty contentious hot take, which was some people should just give up on tech careers. Let's talk about like that. It's a pretty >> big statement. >> It's a very strongly worded statement. And I definitely don't encourage people to give up. So, I I want to make that clear. The only reason I suggested that even in the title was that I think if you have an attitude of like you don't want to try hard or you don't like you don't want to do things yourself and you don't want it to dig deeper into things, like you need to do that. You need to do certain things. And if you're not willing to do that, I think you should know like what you're getting yourself into cuz a lot of people don't know. Like they go through these college degrees, like they kind of just cheat their way through it, and then they expect to have a job at the end of it. And I

</details>

<!-- chunk 13/13 -->

### 关于自我评估与努力的重要性

**Speaker A**: 你需要评估自己是否属于那种会做某事的人，因为这可能对你来说不是最好的选择。不幸的是，人们只是習慣去做那些事情。但是，就像我制作那个视频的时候一样，有很多对我感到不爽的人，但出乎意料的是，绝大多数人他们说也许我本可以更友善一点，而且我认为这是真的。但他们实际上同意了我很多观点。很多人说，你知道的，你是对的。我意识到我一直在朝着仅仅是“提示”事物（prompting things）的方向走得太远了。我在这方面变得越来越差了。我现在做的产品和事情现在更糟了，我也没那么享受它了。这让我想要重新专注于学习以及成为我能成为最好的样子。所以，我想你知道，当我做那些事的时候，我不是试图冒犯任何人，但我认为我没有看到其他人谈论它，所以我只是觉得我必须这么做。我把它放在我的笔记本电脑上，而且我认为它会以那种方式爆发。我并不认为大多数人会看到它。嗯，但是是的，即使我可能因此受到了声誉上的打击，我也留下了那个视频。

<details>
<summary>Original English</summary>

**Speaker A**: think you have to evaluate that if you're going to be one of those people that does that because it might not be the best for you. People have unfortunately just gotten into the habit of doing it. But like when I made that video, I had a lot of people that were pissed off at me, but surprisingly, like the vast majority of people they said that maybe I could have been a little nicer, and I think that's true. But they actually agreed with a lot of my points. A lot of people said that like you know what, you're right. Like I realized I was going too far in the direction of just prompting things. I I got a lot worse at it. Like the products the things that I'm doing are worse now, and I'm not enjoying it as much. And it made me want to like refocus on like learning and being like the best that I can be. So, I think you know, I'm not trying to offend anybody when I did that, but I think I saw nobody else talking about it, so I just felt like I had to do it. And I I I it on my laptop. and think it was going to blow up the way that it did. I didn't think most people were going to see it. Um but yeah, I left that video up even though it maybe I took a reputation hit from that, I'm not sure, but I left that video up.

</details>

**Speaker B**: 是的，但我认为这回到了努力的问题上，对吧？是的。作为建议，你会给软件工程师提供什么建议，无论是早期职业、中期职业，还是更晚期，那些可能在公司工作或者他们只是想成为你所认识的标准工程师——比如你在谷歌工作的那些人，或者你认识的人，或者他们在初创公司工作的人？你认为今天要真正脱颖而出，从一个拥挤的空间中脱颖而出，让你的工作能为自己发声，这需要什么？那意味着什么？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, I think it's a really really good question. I think there probably is some like general advice that would apply to like most cases. I don't know if I can think of that. So, what I'm going to say is I think like you said, like the effort matters. Like even in an interview setting, knowing your audience. It's not like you're not just like living in your own head taking like this standardized test. You're talking to somebody. You're seeing how they're reacting to what you're saying. Like maybe they're not on the same page. Like there's certain shortcuts you can't take. Like if you're in a team, you're at a company, know the people around you. Know what they care about. Ask them questions. Have meetings with them. Don't just make assumptions if you like if you don't have to. Um like I talked to them, figure out what's important, get a sense of things and then go very hard in the direction that you think is correct. Maybe you'll have to recalibrate things. Maybe you'll go too far. Maybe you'll make some mistakes. But I think it's just kind of like that iterative process of like that feedback loop of like, okay, figure out what you're supposed to be doing and then work very intensely to do that and then just keep doing that. It requires a lot of changing. It requires a lot of like course correction and that's difficult. Nobody wants to do that. Like one thing I always did with my manager, I always asked them like, if you have feedback for me, please tell me. Like, I will not get offended. I want to know. I want to know like what I could be doing better. And the way my like all my managers ever reacted to that is they were very surprised. They're like, well, first of all, if you just joined the company you're asking this, like, that's a very good question to be asking because like that tells me that you actually care and you actually want to get ahead. So, I I I think like that aspect of it and that matters a lot cuz then people know you're on the same page. Like, they kind of know about you. They they don't have to guess what you're thinking in your head. You're you're kind of like communicating that with people.

</details>

**Speaker A**: 是的，所以我试着让我们的对话感觉我们一直在重复这一点，就是努力。就像，不要走捷径。我的意思是，当你有一个商业成果时，尤其是在你建立你的业务或者你有你要实现的目标时，但除此之外就投入工作吧。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, so I tried to like I I felt coming through our conversation is is we just keep coming back to it is is effort effort. Like like and and don't take the shortcuts. I mean, take the shortcuts when you have like a business outcome, especially when you're building your business or or you you have a goal that you're going to achieve, but otherwise just put in the work.

</details>

**Speaker B**: 这听起来很简单。在纸面上听起来真的很容易，但将其付诸实践是困难的。比如，对我来说，有时我不是一个喜欢改变的人，实际上。我非常抗拒改变。我讨厌改变。需要我好几年才能改变。

<details>
<summary>Original English</summary>

**Speaker B**: It it sounds simple. It sounds really easy on paper, but it's hard to like put into practice. Like, sometimes, especially for me, I am not a person that likes change, actually. Like, I am very resistant to change. I hate change. It takes me years to change.

</details>

**Speaker A**: 但你网站上仍然有 Angular。

<details>
<summary>Original English</summary>

**Speaker A**: You still have Angular on your website.

</details>

**Speaker B**: 是的。但是，但当你真正去做它的时候，它非常重要，而且非常有价值。我认为这很重要，它会成为一种生活方式。比如，你开始在编码方面投入很多努力，然后在职业生活中意识到，软技能非常重要。我花了很长时间才学会它们。到今天我还在学习它们，但这正是为什么我可能得到了晋升的原因。这就是为什么我的团队喜欢我。变得受欢迎是很重要的。你不想被讨厌。

<details>
<summary>Original English</summary>

**Speaker B**: But um but it's so important and it's so worthwhile when you actually do it. And I think it just matters a lot and it's like it becomes a way of life. Like, you start like I put in a lot of effort on the coding side and then in professional life I realized, okay, like the soft skills matter a lot. Took me a long time to learn them. I'm still learning them to this day, but that's the reason why I probably got promoted. That's the reason why like my team liked me. It's important to be likable. Like, you don't want to be hated.

</details>

**Speaker B**: 最后，你从哪里获得灵感？这可能是书籍、视频，这可能是 YouTube 频道。是的，我认为你只是听了 Martin Clapton 的节目。我非常喜欢他，非常喜欢他的书，因为他深入探讨。即使他探讨得再深入，在每一章的末尾你也会有上百个参考资料。我喜欢这一点，因为我就是那种总会有一个后续问题的类型的人。我总是想深入了解事情。所以，看到像他这样的人，我比对工程师更喜欢科学家、博士、研究人员。所以我真的很喜欢这一点。我认为拥有你可以学习和向其效仿的人是很重要的。而且我认为有很多我可以从中学到灵感的人，包括其他 YouTuber，包括技术人员，包括我过去合作过的人。我总会观察一个人，并试图看到他们身上我非常喜欢的一些特质，然后我也会试图复制和模仿他们。

<details>
<summary>Original English</summary>

**Speaker B**: And as closing, what are places that you get inspirations from? This could be books, this could be videos, this could be YouTube channels. Yeah, I think you just had Martin Clapton on. I'm a huge fan of him, huge fan of his book because he goes deep. And even like as deep as he goes, then you'll have a hundred references at the end of every chapter. And I just love that because I'm the type of person like I just always have a follow-up question. I always want to go a little bit deeper to understand things. And so, seeing people like him, like I relate more to like scientist, people like PhDs, researchers more than I do to engineers. So, I just really like that. I think it's important to have people that you can like look up to and aspire to be like. And I think there's there's plenty of people I take inspiration from, including other YouTubers, uh including technical people, including people I've worked with in the past. And I always I always look at a person and I I try to see like qualities about them that I really like and then I try to like replicate them and imitate them as well.

</details>

**Speaker A**: 很棒。很高兴能和 Neet 录这个节目，特别是以他本人身份。我喜欢他有多诚实，我希望这传达得很好。我发现 Neet 现在招聘的方式很有趣。他经营着一个最大的代码准备网站，然后他会为编码之外的技能招聘。他关心动机，这个人是否能解释自己的思考过程，最重要的是，对于代理（agency）或者完成任务来说。他还很乐意和我谈论他认为公司根本不知道如何评估候选人，而且他们可能从来没有做过。LeetCode 风格的面试之所以存在，不是因为它预测工作表现，而是因为它只是不预测，但因为没有人找到任何更好的可扩展的东西。最后，我欣赏 Neet 的观察，即随着 AI 让其他一切变得廉价，努力正在成为一个差异化因素。任何人都可以提示一个设计、一个功能或一个答案，但你无法提示的是关心以及当有人问“你为什么这么做”时，你捍卫自己选择的能力。请查看下面的节目笔记，了解与技术面试相关的一些务实的工程师深度探讨，它们会深入到更深层次的技术面试相关主题中。如果你喜欢这个播客，请在你的最喜欢的播客平台上并在 YouTube 上订阅。如果能给我一个评分就特别感谢了。谢谢大家，我们下次再见。

<details>
<summary>Original English</summary>

**Speaker A**: I'm glad we finally got to record this episode with Neet. I love how honest he is and I hope this came across as well. I found it interesting how Neet hires these days. He runs one of the biggest coding preparation sites and then he hires for skills outside of coding. He cares about motivation, whether the person can explain their own thinking, and most importantly, for agency or for getting things done. It was also nice to talk with him about how he believes that companies have no idea how to evaluate candidates and they probably never did. The LeetCode style interview survived not because it predicts job performance, it just doesn't, but because nobody has found anything better that scales. And finally, I appreciated Neet's observation that the effort is becoming a differentiator exactly because AI has made everything else cheap. Anyone can prompt a design, a feature, or an answer, but what you cannot prompt is caring and your ability to defend your choices when someone asks, "Why did you do it this way?" Do check out the show notes below for the related pragmatic engineer deep dives that go even deeper into tech interview related topics. If you've enjoyed this podcast, please subscribe in your favorite podcast platform and on YouTube. A special thank you if you also leave a rating on the show. Thanks and see you in the next one.

</details>