---
author: AI Engineer
date: '2026-11-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ktbAVYsAxpk
speaker: AI Engineer
tags:
  - ai-agent
  - developer-tool
  - software-engineering
  - infrastructure
title: Harvey的Agent平台实践：坏掉的不是Agent本身，而是它周围的工程基建
summary: Harvey工程师Joey分享了内部云端Agent平台Spectre支撑超过10,000个PR后的经验教训。演讲指出核心痛点不在于模型代码能力，而在于环境隔离、CI跟进循环、Git检出延迟、警报引发的并发风暴及并发合并队列等周围工程支撑与护栏体系。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Joey Wang
companies_orgs:
  - Harvey
products_models:
  - Spectre
  - Cursor
  - Claude Code
  - Codex
media_books: []
status: evergreen
---
### Agent并非瓶颈，周围的一切才是

让我先从上个月的一个数字开始。平均而言，在我们的平台上，不论白天黑夜，每一分钟都有不止一个Agent启动运行。

老实说，Agent本身反而是最容易搞定的部分。

<details>
<summary>Original English</summary>
Let me start with one number from last month. On average, more than one agent has started on our platform every single minute, day and night.

And honestly, the agents were the easy part.
</details>

嗨，我是Joey。我参与构建了Harvey内部的云端Agent平台。

在产生10,000个PR之后，我能分享的最大教训就是：出问题的不是Agent，而是围着它们转的周围所有东西。

<details>
<summary>Original English</summary>
Hi, I'm Joey. I bu the cloud agent platform we built inside Harvey.

After 10,000 PRs, the biggest lesson I can share is this. The thing that broke was an agent. It was everything around them.
</details>

那么，每一分钟都在提交最终累积成了什么？

累计成了Agent写出的10,000个PR。而且这不仅仅是技术团队在自娱自乐。上个月，Harvey内部大约有460位不同的人在使用它。到了夏天，它的用途已经不再局限于写代码。人们开始在Slack里提数据分析问题并获取答案。我最近最喜欢的一个例子是，我们市场团队的一位同事把一个原型设计和一段讲稿文案丢进Slack，让它为一段产品视频制作故事板。

一旦这个运行底座（harness）建立起来，人们就会把各种你从未预料过的工作交给它。

<details>
<summary>Original English</summary>
So, what does one submit add up to?

10,000 PRs that an agent wrote. And it isn't just Tavac team playing with a toy. Last month, about 460 different people at Harvey use it. And over the summer, it stopped being only about code. People started asking a data question in Slack and getting answers back. My favorite recently someone on our marketing team dropped a prototype and a talk track into Slack and ask for a story book for a product video.

Once the harness exists, people bring the work that you never planned for.
</details>

### 这不是关于模型的演讲，而是关于运行底座

所以先在开头做个声明：这不是一场关于模型、评测或排行榜的演讲。

这是一场关于底座的演讲，关于模型周围那些零碎事情：检出代码仓库、保管密钥、开启PR，以及让代码合并进主干。

当我们在四月份第一次撰写关于Spectre的文章时，我们是这样表述的：在某个时刻，运行底座本身变成了产品。

现在，每当我跟别人说起这些，总会听到同样的问题：“既然已经有了Claude或Cursor，你们到底为什么要自己造这个？”

<details>
<summary>Original English</summary>
So a promise up front. This is not a talk about models, evos or leaderboard.

This is talk about hardness, odd things around the model, checking out the ripple, holding the key, opening the PR, getting the merged.

When we first wrote about Spectre back in April, we put it like this. At some point, a harness become the product.

Now, whenever I tell people this, I get the same question. Why on earth would you build this when clock or cursor already exist?
</details>

我的回答是：我们不跟它们竞争，我们运行它们。我个人的看法是这样的：笔记本电脑上的Agent很强大，但它们无法扩展规模。在现实中，你最多同时跑5到10个。

超过这个规模，你就需要云端环境。而云端需要我们的密钥、我们真实的系统环境、我们的警报和工单系统、统一的一套规则，以及足够的资源容量以保证没有人被饿死。单一工具无法为我们包揽这一切。所以我们构建了这一层，而这一层恰恰就是出现各种故障的地方。

今天我想分享三个故事：我们如何不再卷写代码；我们如何让任何Agent来驱动工作，以及当它们驱动起来后哪些地方崩掉了。

<details>
<summary>Original English</summary>
My answer, we don't compete with them. We run them. And here's how I see it as my own view. Agents on your laptop are powerful, but they don't scale. You can realistically run five to 10 of them.

Pass that you need a cloud. And cloud needs our secrets, our real stack, our alerts and tickets, one set of rules and enough capacity that nobody gets starved. Those single two owns that for us. So we build layer and that layer exactly what broke. So I want to tell three stories today. How we stopped competing on writing code. how we let any agent drive and were broke once they did.
</details>

### 故事一：不再纠结谁写代码，建立底层闭环

第一个故事从我们反复听到的一个问题开始。

我们越来越多的工程师开始使用Cursor，他们问：我怎么才能在里面拿到我们的密钥？我怎么针对真实的系统技术栈跑测试？我们本可以在Cursor里面把这套东西全部重做一遍，然后换下一个工具时再重做，接着再为后面的工具做一遍。

相反，我们的回答精简成了一句话：只要让Cursor去调用Spectre即可。

这其实就是整套思路的核心。人们总会有自己偏爱的Agent，而且喜好一直在变。所以选择你喜欢的就好：Claude Code、Codex、Cursor，或者你自己手写的东西。

在你的笔记本上开启任务，把会话推送到云端，再取回结果。这就是Spectre在这一切之下所处的位置。

<details>
<summary>Original English</summary>
The first story start with the question we keep hearing.

More of our engineers were using cursor and they ask how do I get our secret there? How do I test against our real stack? We could have rebuilt all that inside cursor and then again for next to and the one after that.

Instead, the answer became one sentence. Just ask cursor to use vector.

And that's really the whole idea. People will always have a favorite agent and the favorite keeps changing. So pick yours. Cloud code, codeex, cursor, trag your own hands.

Start on your laptop, push the session to the cloud, put it back. That's how Spectre sits underneath all of that.
</details>

因为一旦代码写完，真正的工作闭环才刚开始。

设想这样一个场景：凌晨2点，Slack里触发了警报。一个Agent接手了任务，无需任何人手动输入。它编写了修复方案，拉起一套我们环境的真实副本，并在PR上附上了验证证据。当CI构建失败时，后续跟进循环（follow-up loop）读取错误日志，趁大家还在睡觉时再次推送了另一版修复。

到了早上，这个PR已经排在统一的代码审查队列里，遵循与其他PR相同的规则，不管它是由哪个Agent写出来的。只有当你的工作日开始时，负责人才会收到提示；一旦审核通过，Agent就能将其自动合并。

如果你在我描述的这些阶段里只挑一个去构建，那就去构建**后续跟进循环（follow-up loop）**。我们在10月初为所有人开启了这项功能，而在那个月里，合并进我们后端仓库的Agent PR中，有五分之四都经过了它。

这就是“仅仅会写代码的Agent”和“能够把事情彻底办成的Agent”之间的差别。

<details>
<summary>Original English</summary>
Because once the code was written, the real group starts picture appears day. Alert files in Slack at 2 in the morning. An agent picks up nobody typing. It writes a fix, spins up real copy of our stack and post the proof on the PR. When CI fails, the follow-up loop reads the failure and pushes another fix while everyone still sleep. By morning, the PR sits in one review queue under the same rule as other PR whichever agents wrote it. The owner gets a notch and only once your working day starts and once approved a agent can automerge it.

If you only build one of those stages that I described, build a follow-up loop. We switched on for everyone in early October and that months. Four out of five agent PRs merged into our backend PR had been through it.

That's the difference between agent that write code and an agent that finished the job.
</details>

此外还有团队知识的沉淀。每个团队都有那么一位成员，确切知道如何测试某个棘手的服务、哪些flag绝对不能动。而这些知识以前只留在他们的脑子里或他们的笔记本电脑里。

所以我们给它安了个家：通过项目文档，大家写下关键事项，Agent写下它们学到的东西，团队固定下值得信赖的技能，并且记录下谁运行了什么。

任何参与该项目的Agent都能在同一个认知基准下工作。我个人的观点是，无论你选用哪种Agent，审计追踪和检查规则都应该保持一致。

<details>
<summary>Original English</summary>
And then there's the knowledge. Every team has that one person who knows exactly how to test the tricky service. Uh which flag you never touch. And that knowledge leaves in their head. of their laptop.

So we gave it a hope projects people write down what matters. Adrian write down what they learn. Team pings the skills you trust and there's a record of who rent what.

Any agent working in the project with the same page. My personal view whichever agent you pick the audit trail and the checks should be the same.
</details>

### 故事二：如果人能点击，Agent就能调用

第二个故事是关于规则的。回看5月份，如果你想让Spectre做点事情，你得打开一个浏览器标签页，或者在Slack里打字触发。整整一个月里，从终端发起的任务刚好只有1个。

于是我们定了一条规则：**只要是人能点击的操作，Agent就能调用**。

启动任务、开启自动合并的跟进循环、发布页面，这一切都可以从CLI直接完成。

这意味着你的笔记本端Agent可以调用它，沙箱内部的Agent也能调用它，甚至CI流程同样可以调用它。

随后大家彻底放开用起来了。到了10月，命令行每月启动大约6,500个任务。Web界面的使用量并没有萎缩，其他场景只是围绕着它成倍增长起来。

从终端发起的任务和从浏览器发起的任务混合并存，并且出现了一种新型用户：他们每月发起数百个任务，却从来不打开Web应用界面。

<details>
<summary>Original English</summary>
The second story is about rule. Back in May, if you want a spectctor to do something, you open a browser tab or tacking Slack. The whole month, exactly one task came out from terminal.

So, we made a rule. If a person can click it, an agent can call it.

Start a task. Turn on the follow-up loop on automerge, publish a page, all from CLI,

which means your laptop agent can call it. A agent inside the sandbox can also call it. Even CI can call it too. And then people ran with it. By October, the command line was starting about 6,500 ts a month. The web app didn't shrink. Everyone else just grew around it.

Task started from the terminal were merging mops and task started in browser and the new kind of users showed up. People who start hundreds of tasks a month and never open the app at all.
</details>

事情在这里变得有趣起来。10月份我接手了一个大任务，所以我开了一个编码会话，让它充当协调器。

它把工单拆成了10个不同的里程碑：留一个给我，其余的拆解为数百个任务分派给Spectre，每个任务都在独立的沙箱里进行端到端验证。

接着到了10月底，我们给大家提供了追踪工具，现在它可以帮我盯紧Spectre。它列出Spectre正在等待确认的问题，帮我起草好回答，一旦我确认同意，就发送回去。

我甚至这样给朋友发私信：我就是用Cursor、Claude Code或者随便什么工具来向Spectre批量派发任务。

这固然很美好，但也带来了新的问题。

<details>
<summary>Original English</summary>
And this is where it gets fun. In October, I had a big task. So I bought code session and asked to be the coordinator.

It split the tickets into 10 different milestones. K one for me and the rest to Spectre with hundreds of tasks. Each has its own sandbox to validate end to end.

Then at the end of the October, our it give everyone trag now watch Spectre for me. It list the question Spectre is waiting on draft my answers and once I say yes, send them back.

I actually DM to my friend like that. I just use cursor clock code or whatever to spam spectre. Now,

well, that's the dream, but it's also the problem.
</details>

这里插叙一个小细节：当我们分析任务时间到底消耗在哪里时，发现最慢的步骤并不是模型思考，而是Git。光是把我们名下的每个仓库检出一遍，平均就要花一分多钟。

我们的修复手段是：在每台机器上保留每个仓库的本地副本，让每个任务直接借用。

<details>
<summary>Original English</summary>
A quick detour. When we look at where our task time actually went, the slowest step wasn't model syncing. It was get just checking out every ripple we own took over a minute on average.

The fix keep a copy of every ripple on every machine and let each task borrow it.
</details>

### 故事三：当集群崩溃，工程护栏与公平调度

第三个故事发生在系统彻底瘫痪的时候。8月中旬，一次发布带着Bug上线了。那个Bug触发了每个工作区（workspace）都会报一次的警报。于是，这一个Bug演变成了数百个报警，全部砸进同一个Slack频道。

有人设置了一个工作流，在每条报警里都@我们的Agent，而每一次@都会启动一个任务。通常情况下这类任务一天大约触发50个，但那天在短短4个小时内，它们拉起了大约900个任务。

900个Agent同时在排查同一个Bug，直到整个集群连一个节点的位置都没剩下。

随后的修复方案几乎平平无奇：重复的警报现在会直接挂靠到已经开启的调查任务中，不再重复拉起。

<details>
<summary>Original English</summary>
The third story is the one where it broke in mid August. A release goes out with a bug. That bug triggers alert that fires once per workspace. So one bug become hundreds of alerts all landing in one single S channel.

Someone has set up workflow that tag our agent on every alert and every tag started task. On normal day those task started about 50 task. That day in about four hours they started around 900.

900 agents are chasing the same bug until that wasn't room left for a single note.

The fix was almost boring. A repeat alert now joins the investigation that's already open.
</details>

两个月后，类似的情况又发生了一次。而这一次出手的不是机器人。10月的一天，一位工程师完全按照我们倡导的方式操作：把工作甩给Spectre。

他在大约3小时内从命令行拉起了约950个任务，导致我们平台上没有任何其他任务能正常工作。集群被打满了，所有其他人的工作都被迫堵在了一台笔记本电脑发起的任务后面排队。这不是用户的问题，这是我们的系统设计问题。

4天后，我们拿出了真正的解决方案：一个**公平启动队列（fair launch queue）**。现在启动任务会先分配排队位置，调度器在集群有空余容量时才会启动它。守在键盘前的人类用户享有优先权；每个人都能分到公平的配额，但当集群空闲时可以借用更多容量。

每次启动任务时，你都可以看到自己在队列里的排位。在压测中我们用300个任务突发冲击它，任务排队延迟从近2秒下降到了70毫秒。

<details>
<summary>Original English</summary>
Two months later, it happened again. And this time, it wasn't a bot. On October, the engineer did exactly what we've been asking everyone to do. Hand work to Spectre.

About 950 tasks from the command line. In about 3 hours, nothing in our platform can work. The cluster filled up and everyone else work sat in line behind one laptop. That's not a user problem. That's our problem.

4 days later, we had a real fix. A fair launch queue. Now starting a task gives you a place in line and the dispatcher started when there's room. People sitting at keyboard goes first. Everyone gets a fair share and can borrow more than the cluster is quite.

And whenever you start a task, you can see a placing line. When we hit it with a 300 task burst in low test, the task lit went from almost 2 seconds to 70 milliseconds.
</details>

那么这起作用了吗？

回看8月份每周最繁忙的那天，有两千多个任务，大约十分之一未能顺利完成。

到了11月4日，任务量翻了一倍多，完成率大大提高，不过我们仍有改进空间。

客观地说，我们当时同时改动了好几个地方，所以我无法断言哪个修复最关键；但无论突发洪峰怎样越来越大，平台总算能够撑住了。

<details>
<summary>Original English</summary>
So did it work?

When it's the busiest day of every week back in August, two certain task and about one in 10 didn't finish.

Then in November 4th, more than twice that and much better in the finish line, but we still have some room to grow.

I will be modest, we change several things at once, so I cannot tell you which fix mattered the most, but the birds kept getting bigger and the platform kept up.
</details>

### 新的瓶颈：合并队列与自动化Agent潮

正当这套负载得到控制时，瓶颈又转移到了新的地方。

10月底，我们的开发平台团队拉响了警报：全公司的PR数量在单月内激增了约60%。原本需要15到30分钟的代码合并过程，现在要花上一个多小时。合并队列不断被迫手动关闭。于是现在流程变成了：PR rebase到main分支，重新跑CI，测试通过了再合并。一旦main分支被改挂，所有人的CI都会跟着挂掉。坦率讲，这个问题我们目前还没有彻底攻克。

但在结束之前，还有一件事值得注意。

当我们忙着修补这一切的时候，另一股力量正在悄然生长。我之前给你们展示的大多数场景，都是由人提出请求而触发的。

但在Spectre上增长最快的工作来源并非人工：而是**自动化任务**——那些按定时计划或事件触发唤醒的Agent，它们默默执行工作：分流警报、阅读PR、撰写跟进总结。

上个月大约有110人在运行这类自动化，而我们学到的经验是，第一天就必须给它们立好护栏：如果一个自动化连续失败5次，它就会自动关闭；同时它可以附带预算上限或过期时间。因为在没人看管的情况下，一个Agent同样可以在转眼间启动数千个任务。

<details>
<summary>Original English</summary>
And just when that was on the crunch show, the model neck moves.

At the end of the October, our dev platform team raised an alarm. PRS across the company had jumped around 60% in a single month. A merge that used to take 15 to 30 minutes was taking over an hour now. And merge Q kept having to be switched off. So now a PR rebase onto main rerun CI and merge if it's green. If main breaks everyone CI breaks with it. Alterately we haven't cracked this one yet.

But before I go there's one more thing. While we were busy fixing all it something else was quite growing. Most of what I've been showing you start with a person asking.

The fastest growing source of the work on Spectre doesn't these are automations agent that wake up on schedule on an event and just do the work tri alert read the PR write the post.

Last month about 110 people had automation running and we learned to give them a guardrail on day one. If one fails five times in a row, it switch itself off and it can carry a budget or expiry date because when no one's watching, an agent can start thousands of tasks, too.
</details>

所以，以下是我接下来正在探索的问题，老实说我目前也还没有现成的答案：

如果每个Slack频道都有一个永不离线的专属Agent，能够跟进对话并在适当时机自主开启工作，会怎么样？

如果每一个PR在人类肉眼查看之前，就已经完成了可运行的真实证明，会怎么样？（如今只有二十分之一的合并且带有这类证明。）

以及，当Agent永无休止地发起PR时，你到底该如何把它们合并进主干？

6个月后再来问我吧，到时候我再告诉你们又有哪些东西被撞碎了。

如果你在自己的工作中也在构建类似的东西，这里有三点经验我会再次践行：
1. **盯紧代码写完之后发生的每一个环节**。
2. **把每一个操作都做成Agent可调用的能力**。
3. **在Agent、人类或警报真正发现自己的上限之前，尽早给它们所能启动的任务规模设定限额**。

最后留一个观点，这代表我个人的视角：工程师可以用任何他们喜欢的Agent来写代码；真正能够沉淀下来并持久存在的价值，是承载运行、负责校验并最终将代码合并进去的那套底座体系。

非常感谢大家观看。如果你也在构建类似的东西，欢迎在LinkedIn上找我交流。

<details>
<summary>Original English</summary>
So, here's what I'm chasing next, and I don't have an answer yet, honestly.

What if every Slack channel had its own agent that never locks off? One that follows competition and start work on its own. What if every pure prove it works before a human even look at it? Today only one merge in 20 carries that kind of proof.

And how do you merge when agents never stop opening PRs?

Ask me again 6 months. I will tell you what broke. If you're building something like this when you work, here's three things I do again. Oh, what happens after code is written. Make Eric action something an agent can call and cap what an agent, human or alert can start before they find out what they can do with it.

And one last thought, that's my own view. Engineers can write code with whichever agent they like. The work that's lost is the harness that runs it, checks it, and get it merged.

Thank you so much for watching. Come find me on linking if you are building similar things.
</details>