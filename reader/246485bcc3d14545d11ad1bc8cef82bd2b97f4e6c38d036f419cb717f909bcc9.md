---
author: AI Engineer
date: '2026-10-24'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kspZP5BgkEU
speaker: AI Engineer
tags:
  - coding-agent
  - software-engineering
  - product-engineering
  - code-review
title: AI 编写代码后，工程师还剩下什么：产品工程师的兴起
summary: Laurie 探讨了编码智能体让写代码成本归零后软件开发面临的瓶颈转移。随着代码审查与交付链路逐步自动化，软件本质复杂度依然存在。工程师的核心职能正转向探寻用户真实需求、定义“什么是好”并转化为规格说明，工程角色正向产品工程师演进。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people:
  - Laurie Voss
  - Swyx
  - Eliyahu Goldratt
  - Fred Brooks
  - Andrew Ng
companies_orgs:
  - Arize AI
  - npm
  - GitHub
  - OpenAI
  - Amazon
  - Anthropic
  - Cognition
  - Google
  - IBM
products_models:
  - GitHub Copilot
  - Devin
  - Claude
  - BugBot
media_books:
  - The Goal
  - The Mythical Man-Month
status: evergreen
---
### 智能体革命：从 AI 工程师到所有工程师的变革

[音乐]

>> 我叫 Laurie。我是 Rise AI 的开发者关系负责人。在上一段职业经历中，我联合创立了 NPM Inc.。所以你们有些人可能在 JavaScript 时代就认识我。但这些日子我在思考 AI 智能体，而在今天这种场景下，是思考它们对我们工作的影响。

大约 3 年多前，Swix 写了一篇名为《AI 工程师的兴起》的文章，他的核心论点是：当涉及到交付 AI 产品时，你需要的是工程师而不是研究员。我认为这是一个引起所有人共鸣的信息，尤其是来到这个大会现场的人。因此他确立了“AI 工程师”这个职位，自那以后各大公司一直在招聘该岗位。我今天来到这里的部分目的，就是想让你们相信，事实上他走得还不够远。

发生变革的不仅仅是 AI 工程师。一场革命正在席卷每一种工程师。

所有的工程工作都在被一种新型工作所取代，而且不是每个人听到这个消息都会感到高兴。

<details>
<summary>Original English</summary>
[music]

>> My name is Laurie. I'm head of developer relations at Rise AI. Uh in a former life I co-founded NPM Inc. So some of may you some of you may remember me from JavaScript days. Uh but these days I think about AI agents and uh in this case what they are doing to our jobs.

Uh so a little bit over 3 years ago um uh Swix wrote an essay called the rise of the AI engineer and his argument was that when it comes to shipping AI products you want engineers not researchers. I think that is a message that resonated with everybody especially who the people who come to this conference. Uh and so he created the job title of the AI engineer and companies since then have been hiring for it. Um and part of what I'm here to do today to do is to convince you uh that he did not in fact go far enough. Uh

there's not just an AI engineer revolution happening. There is a revolution happening to every kind of engineer.

Um all engineering jobs are being replaced by a new type of job and not everybody is going to be happy to get that news.
</details>

### 瓶颈转移与约束理论

引发这一切的根本性变化在于，智能体基本上已经让编写代码免费了。就像你确实为 token 付费，但相对于过去花费你时间的成本而言，它基本上等于免费。但在编写代码之后的一切，并没有在同一时间变得免费。因此瓶颈发生了转移：过去是写代码非常慢，而所有其他事情大致以相同的速度发生；现在变成了写代码极快，而我们被卡在了新的事情后面。眼下，就在这个月，这个瓶颈正是代码审查。

但我的论点是，它不会停留在那里。我们会找到自动化代码审查的方法。我们会让代码审查跟上智能体的速度，然后我们会撞上另一个瓶颈，再下一个瓶颈，以及接下来的瓶颈。到了某个时刻我们会停下来，撞上一个我们无法逾越的瓶颈。而那个瓶颈，就是留给人类去做的东西——无论那是智能体无法跨越的什么瓶颈。因此我打赌，我能想到一件智能体真正做不到的事情。一旦我们触及那个瓶颈，我们就必须想办法如何培养下一代工程师来胜任那份工作，因为我们现在并没有在这方面培养他们。

所以，先做一个简短的预警兼道歉。我有 18 分钟时间，因为这就是 Swiss 给演讲分配的时长。我有一大堆数据。我为此做了大量的调研。但我没有时间把它们全都展示给你们。我没有时间去援引我的来源以及做所有那些事情。所以，我只能在幻灯片上放一堆引用并向你们抛出数字，然后我只能对你们说类似“老兄，信我一次”的话。

>> [笑声]

<details>
<summary>Original English</summary>
Um the underlying change that kicked all of this off is that agents have made writing code basically free. Like you pay for the tokens but relative to the cost of the time it used to take you uh it is basically free. Um everything that comes after writing the code did not become free at the same time. So the the bottleneck moved from writing code is really slow and all of this other stuff happens at roughly the same speed to writing code is super fast uh and now we get stuck behind new things. So the first the thing it's stuck behind right this second like this month is code review.

Um uh but my thesis is that it's not going to stop there. We are going to figure out how to automate code review. We are going to make uh code review move at the speed of agents, and then we are going to run into another bottleneck, and another bottleneck, and another bottleneck, and at some point we're going to stop. We're going to hit one that we can't get past. Uh and that is what is going to be left for the humans to do. Whatever the bottleneck is that we can't get agents past. So, I'm making a bet that I can think of a thing that agents really are not going to be able to do. Uh and then once we've come to that bottleneck, we're going to have to figure out how do we train the next generation of engineers to be able to do that job because we're not training them to do that job right now.

So, a quick warning {slash} apology. I have 18 minutes because that is how long Swiss gives for talks. Uh and I have a really big pile of data. I did a ton of research for this. Uh and I don't have time to give it all to you. I don't have time to like quote my sources and do all that stuff. So, I'm just going to throw numbers at you with a bunch of citations on the slides, and I'm just going to have to sort of ask you to trust me, bro. Uh

>> [laughter]
</details>

### 当前堵点：人类与机器审查的困局

>> 开启自主编码智能体的开发者写的代码增加了 741%，也就是多达八倍。但是他们交付的速度只快了 30%。30% 的加速并非微不足道，30% 的提升非常惊人。我们确实比过去交付了多得多的代码，但考虑到我们写了八倍的代码，实际交付却只增加了三分之一，这其实有点糟糕，对吧？这意味着我们被卡在某个地方了。

我们卡住的地方就是代码审查。而我们被卡住的原因，是因为人类不可能平白无故审查得更快。思科在 20 年前做过一项庞大的研究，关于你可以多快地进行代码审查，以及你的代码审查能达到多高的准确率。结果表明，人类理解代码所发生内容的能力，在超过大约每小时 450 行代码之后就会急剧下降。因此，如果你用智能体生成了一个 10,000 行的 diff，你合理地审查完那些代码大概需要一周。而现实是根本没人在那么做，对吧？因为如今我们都在随手抛出 10,000 行的 diff。

在上一届 AIE 上，我做过一场关于这种现象的完整演讲，那场演讲叫做《代码审查之死》。如果你想了解关于代码审查之死的所有信息，你可以去观看那场演讲。但是我们现在面临的问题——这与我本场演讲整体试图解决的问题并不完全一样——在于：产生表面合理的代码的成本已经彻底崩溃，而弄清楚能否信任该代码的成本却完全保持不变。

所以，就像我说的，眼前显而易见的代码审查举措就是让机器来做审查。而且这已经发生了。截至上个月，GitHub 的 Copilot 承担了 GitHub 上五分之一以上的代码审查。如果你愿意，你可以选择让 Copilot 作为上生产前的最终审查者。如果你愿意，你可以赋予它审批权限，这太疯狂了。我不知道谁在开启那个选项，但如果你想，你是可以做到的。

OpenAI 表示，在 OpenAI，人类可以审查他们的拉取请求，但并不是强制要求的。

但问题在于机器审查者目前还不是很好。数据显示，我找到的数据对四个 AI 审查工具进行了严格测试，它们都发现了大量的 bug，但没有发现任何相同的 bug。它们在任何单个 bug 上都没有达成一致。它们确实都在代码中发现了实际存在的问题。它们在代码中发现的都是不同的问题。

因此，它们值得运行，但如果你对此态度严肃，你绝不会只运行其中的一个。因为它们目前还不够可靠。

有些人走到了极端。他们就像是，“我干脆不再审查代码了。我直接假定我的智能体一次性就完美搞定了。”在场的 Dexter Horty——我不知道他是否在听众席，大概不在——他花了 6 个月时间告诉人们不要读代码，然后 6 个月后，他站上舞台说：“不，我错了。你实际上根本不能完全跳过代码审查。我们尝试过那样做。那是一场灾难。我们不得不把整个系统全盘推翻重写。”那不是一种可行选项。智能体还没那么出色。它们没有做到一次性写好代码。

亚马逊发生过一系列宕机事件，他们对其做了复盘并认定，这是因为他们的编码智能体生成了一堆劣质代码（slop），而他们不假思索地直接将其发布到了生产环境。所以现在他们不再允许他们这么做了。在亚马逊，高级工程师必须在代码审查上签字确认。Anthropic 也发布了一篇复盘报告，内容关于越过了他们拥有的每一位审查者（包括人类和机器）的 bug。所以问题在于，我们迄今为止构建用来检查代码是否足够好的自动化系统，它们本身还不够好。

Claude 3.5 Sonnet 在标准编码基准测试中能通过 80% 的测试。而 Devin 的制造者 Cognition 构建了一个基准测试，提出了一个不同的问题，该问题不是“它通过测试了吗？”，而是“作为代码库的维护者和审查者，你会合并这个 PR 吗？”如果换成这个问题，通过率就从 87% 骤降至 54%。

因为决定你是否会合并它包含了大量的额外信息。其中包括代码风格、副作用、外部系统，以及没有被编码进代码库的历史经验。它被编码在了维护者的大脑中。

<details>
<summary>Original English</summary>
>> Uh so, developers who switch on autonomous coding agents write 741% more code, eight times as much. Uh and but they ship only 30% faster. Like, 30% faster is not nothing. 30% faster is amazing. We are shipping a lot more code than we used to, but given that we're writing eight times more code, only a third more actual shipping is kind of bad, right? It means that we're stuck somewhere.

Uh and where we're stuck is code review. Um and the reason that we're stuck is because humans can't just review faster. Uh there is an enormous study done by Cisco 20 years ago about how fast you can do code review, and how accurately you can do code review. Um and it turns out that humans' ability to like parse what's going on in code falls off radically after about 450 lines of code per hour. So, if you've produced a 10,000 line diff with your agent, it would take you like a week to reasonably review that code. And the answer is that nobody's actually doing that, right? Cuz we're all throwing 10,000 diffs around willy-nilly these days.

Um so, I did a whole talk about this phenomenon at a previous AIE, and that talk is called the death of the code review. And if you want all of the information about the death of the code review, you can watch that talk. Um but the problem facing us right now, uh which is not the same as the problem I'm trying to solve with this overall with this talk, is that the cost of producing plausible code has collapsed while the cost of knowing whether to trust that code has stayed exactly the same.

Um so, the obvious review move right now is to make the machines do the review, like I said. And that is already happening. Um GitHub's Copilot uh does more than one in five of the code reviews on GitHub as of last month. Uh you can, if you want to, opt in to let uh Copilot be the final reviewer before something goes to uh production. You can make it have the approval power, if you want to, which is crazy. I don't know who's turning on that option, but you can do it if you want to.

Um OpenAI says that at at OpenAI, humans may review their pull requests, but aren't required to.

Um but the problem is that the machine reviewers aren't very good yet. Uh the data says that there's uh the data that I found put four AI reviewers through their paces, and they all found a bunch of bugs, but none of the same bugs. They did not agree on any individual bug. Uh they all found actual issues in the code. They all found different issues in the code.

Um so, they're worth running, but if you are serious about this, you're never going to run just one of them. Uh because they are not reliable enough yet.

Um And there are some people who went all the way. They were like, "I'm just not going to review the code anymore. I'm just going to assume my agent has one shot at this perfectly." Um Dexter Horty, who is here, I don't know if he's in the audience, probably not. Um uh he spent 6 months telling people not to read the code, and then after that 6 months, he got on stage and said, "Nope, I was wrong. You can't actually uh skip code review entirely. We tried that. It was a disaster. We had to rip replace whole systems." Uh that's not an option. The agents are not good enough. They're not one shotting the code.

Um Amazon had a run of outages uh that they did postmortems on and decided that it was because their coding agent had produced a bunch of slop and they just released it into the wild without thinking. Uh and so now they don't let them do that anymore. Uh senior engineers must sign off on code reviews at Amazon. Um and Anthropic published a postmortem uh on bugs that had got past every reviewer that they had, both human and machine. So, the problem is that the automations that we've built so far to check whether our code is good enough are not themselves good enough. Um Claude Fable 5 passes the tests uh on 80% of a standard coding benchmark. Um and co- So, Cognition, the makers of Devin, um they built a benchmark that asks a different question, which is not does it pass the tests? The question is would you as the reviewer, as the maintainer of this repo, merge this PR? And if you ask that question instead, the pass rate falls from 87% uh to 54%.

Um because there's a lot of extra information that goes into deciding whether you would merge it. There's code style, there's side effects, there's external systems, there's history that is not encoded into the code base. It is encoded into the brain of the maintainer.
</details>

### 下一个瓶颈：运维、安全与无限的软件需求

所以，维护者所补充的、显而易见增加的东西，正是我们尚未赋予智能体的。那是它们所不具备的信息，是它们未掌握的技能。那是一种关于“何为良好”的感觉。这正是智能体目前还不具备的。这也是我稍后要回溯的一个关键见解。

Eliyahu Goldratt（如果我发音正确的话）原本是一位物理学家，后来成为了管理大师，他在 1984 年写了一本关于经营工厂的小说。这听起来对你来说像一本有趣的小说吗？它叫《目标》。他的核心思想是约束理论。每个系统都有一个瓶颈，而除非你加速的对象恰好是那个瓶颈，否则单纯加速事情是行不通的。

这就是我们在代码审查上面临的问题。我们加快了写代码的速度，却没有加快审查的速度。

他的第二个观点是今天真正重要的观点：当你解决了当前的瓶颈，它并没有凭空消失，它只是发生了转移，并堆积到另一个瓶颈前。那么让我们假设，尽管我刚才说了那么多关于目前代码审查工具如何糟糕的话，我们最终解决了这个问题，我们把自动化代码审查提升到了更高标准并移走了那个瓶颈。那么它接下来会遭遇的下一个瓶颈是什么？

如果我们搞定了审查，下一个瓶颈很可能就是运维。我该如何部署这套系统？我该如何进行扩容？然后你很可能会遇到安全瓶颈。我如何在大规模运行时保证这套系统的安全？我如何确保这套系统的私密性？我如何确保它不会彻底失控？但我在这里要做出本场演讲中最大胆的跳跃。我假设我们把这些问题也一并解决了，因为这些事情在很大程度上已被人类解决。关于它们，外界有着海量的数据。如果我们能够利用越来越先进的智能体弄清楚如何做运维、如何做扩容、如何做安全，那么剩下留给我们做的是什么？在这种情况下，人类的角色到底是什么？

这也是一个大问题，[清嗓子] 并且也是一个长远的问题。我并不是在告诉你们未来 12 个月会发生什么。在接下来的 12 个月里，我认为我们在代码审查上可能会取得一些实质性进展。我不认为从现在起 12 个月内我们能把运维、扩容和安全问题彻底理顺。我认为那将需要 5 到 10 年的时间才能完成。尽管有人叫嚷着“2027 实现 AGI”，但事实并非如此，我们在这类事情上会逐步迭代推进。

但是，要使我的论点成立，你还需要做出另一个假设：我们所需要的软件数量实际上是无限的。我认为这个论点要容易确立得多。想一想你在现实中见过的每一个处于生产环境的网站，它大概都挺糟糕的。而它之所以糟糕，并不是因为我们不知道如何做出非常棒的网站。问题在于没有足够多的人去把所有的网站都做好。每当你在理发店、政府部门或者比如你的银行遇到一个糟糕透顶的网站，并不是因为没有人知道怎么做好那个网站，而是因为：第一，做好它非常昂贵；第二，有能力做这件事的人正忙着做别的事——可能正在交付 AI 智能体。

因此，假设我们能够基本上免费生产我们想要的任意数量的软件，并且构建软件的需求基本上是无限的。那将是一个极佳的处境。我们拥有了无限的需求，同时也突然获得了无限的供给。

那么，瓶颈最终会落在哪里？我们认为智能体无法吞噬的究竟是什么？为了弄清这一点，我把软件开发这项工作拆解成了我能想到的尽可能多的组成部分，并按照智能体触及它们的先后顺序进行了排序。

写代码已经崩溃，审查和维护代码很快也会沦陷。

生产交付与扩容是下一个待宰的对象，尽管那里目前还没有太多数据。再往后，则是那些我认为可能安全的事情：决定构建什么，定义什么是好，以及最终让它令人愉悦。

<details>
<summary>Original English</summary>
Um So, what the maintainer is adding, what maintainer is demonstrably adding, is something that we haven't given the agents yet. There is information they don't have, there is a skill they don't have. Um and it is the sense of what good means. That is what we are That is what the agents don't have yet. Uh and that is a critical insight that I'm going to come back to.

Um Eliyahu Goldratt, if I'm pronouncing that correctly, was a physicist who became a management guru and in 1984 he wrote a a novel about running a factory. Does that sound like an interesting novel to you? Um it is called The Goal. Um and his big idea was the theory of constraints. Uh every system has one bottleneck and speeding things up does not work unless the thing that you were speeding up is the bottleneck.

Uh that is our problem with code review. Uh we've sped up the code and we have not sped up the review.

Um his second idea is the one that matters today, which is that when you fix the bottleneck, it doesn't go away, it just moves and finds another bottleneck to pile up against. Um so let's assume, despite everything that I've said about how bad the code reviewers are right now, that we figured that out, that we get automated code review to a higher standard and we move that bottleneck. What is the next bottleneck uh that it is going to run into?

Um if we figure out review, the next bottleneck is probably going to be operations. How do I deploy this thing? How do I scale it up? Uh and then you're probably going to run into security. How do I make this thing safe at scale? Uh how do I make sure that this thing is private? How do I make sure that it's not radically going off the rails? Uh but I'm going to make and this is the big leap that I'm making in this talk. I'm going to assume we figured those things out as well because those things are very heavily solved by humans. There's an enormous amount of data out there about them. If we can figure out how to do operations, how to do scaling, how to do security using progressively more advanced agents, what is it that we are left to do? Like, what is the role of a human in that situation?

Um it's also it's a big question [clears throat] and it's also a long-term question. I'm not telling you what is going to happen in the next 12 months. In the next 12 months, I think we'll probably make some real progress on code reviews. I do not think 12 months from now we'll have sorted out operations and scaling and security. I think that is going to take somewhere between 5 and 10 years to get done. Uh despite people who are like, "AGI 2027." No, we're going to slowly iterate on this stuff.

Um But the other assumption that you need to make for my for the my thesis to be correct is that the amount of software that we need is effectively infinite. And I feel that one is a much easier case to make. Think of every website you've ever run into uh in the world in production, and it's probably pretty bad. Uh and the reason it's bad is not because we don't know how to make really great websites. The problem is that there's not enough people to make all of the websites good. Every time you run into a terrible website at your hairdresser or the government or like, you know, your bank, like it's not because there's not somebody who knows how to make that website good. It's because A, it's very expensive to make it good, and B, the people who are doing that are busy doing other things. Uh you know, probably shipping AI agents. Um

so assume that we can make as much software as we want basically for free, and that the appetite for making software is essentially infinite. That is a wonderful situation in which to be in. We've got infinite demand and also suddenly infinite supply.

Uh where does the bottleneck end up? What do we think the agents are not going to eat? Um to try and figure that out, I split up the job of software development into as many pieces as I could think of, and I sorted them by how soon the agents uh get to them.

Uh writing code is already collapsed, reviewing and maintaining code is going soon.

Um shipping to production and scaling are next on the chopping block, although there isn't a lot of data there yet. Uh and then there's the stuff that I think is probably safe, which is deciding what to build, uh defining what good means, and finally making it delightful.
</details>

### 本质复杂度与规格定义

剩下的就是弄清楚人们究竟想要什么。每一款软件，都是人类想要达成的某种目标的具象形式化表达。

所以，如果一个客户对你说：“我需要追踪我的订单。”市面上有上万款软件可以追踪订单。它们的功能就是这个。但在这些软件中，如果你运气好，只有一款能契合你开面包店的需求。如果你开的是汽车配件店，情况就会截然不同。如果你经营的是一家大型制造企业，情况又完全不一样了。仅仅说出那个需求是远远不够的。全部的工作就在于搞清楚，当你表达你想追踪订单时，你具体指的到底是什么。这对你的业务意味着什么？它必须做到什么？它具体怎么运转？

而这些知识并不存在于训练数据中。它不在模型权重里。它存在于经营那家企业的人的大脑中。获取这些知识的唯一途径就是摆动你的血肉器官（嘴巴）去和他们交流，并让他们也摆动血肉器官与你交流。你必须和他们当面沟通。这是把那些信息提取出来的唯一方法。

并且这项工作有一个非常重要的属性：它是无法迁移的。如果你去思考日历应用中“好”的定义，以及排程调度应用中“好”的定义，它们解决的几乎是相同的问题，对吧？日历应用和排程 [清嗓子] 应用，但它们是完全不同的软件。即使这两个使用场景如此接近，它们却有着全然不同的需求和完全不同的“好”的定义，更不用说我们拥有数不胜数的使用场景。

任何时候你使用带有无数配置选项却仍然 [哼笑] 满足不了你需求的软件——我说的就是你，Jira——这就是你碰到的那种试图包揽一切却依然一败涂地的软件问题。

所以瓶颈转移到了描述问题并定义“解决该问题意味着什么”，而我对本次演讲以及对未来 10 年的大胆论断是：瓶颈将停留在这里。主管 IBM System/360 项目并写下《人月神话》的 Fred Brooks 在 1986 年就写过这方面的论述。他把软件的难度划分为两类：偶然复杂度（Accidental complexity）是工具、语言、键入或语法的难度；而本质复杂度（Essential complexity）则是问题本身的难度。

他预言没有任何单一工具有可能让我们获得 10 倍的生产率提升，因为本质部分才是困难的部分。Brooks 的预言现在看来相当扎实，因为我们让写代码的速度快了八倍，但我们在实际交付上并没有提速多少，因为最难的部分是本质部分。

来自 OpenAI 的 Shawn Grove 在两年前——不对抱歉，一年前，今年是哪一年来着？——提出了同样的观点。他说代码是规格说明的有损投影，无论谁编写规格说明——哪怕是产品经理、立法者、工程师还是市场营销人员——他们就成了程序员。因此，写下“什么是好”正是如今价值所在。我的时间开始不够用了，因为我没把控好节奏。

任何你可以低成本验证的事情，如果你是模型厂商，你都可以针对它进行训练直到将其攻克。因此 Cognition 试图写下来——通过他们关于合并门槛的基准测试，探讨到底怎样算作可合并，你知道，“这代码可以合并吗？”他们当时想：让我们看看能否构建一个基准测试来真正定义什么是“可合并”，看看我们能否把所有其他信息都纳入基准测试，然后围绕它训练一个模型。

Cursor 的审查工具 BugBot 把你团队给出的每一个差评都转化为一条规则，他们现在大概有 44,000 条规则。所以一旦维护者将知识从他们的大脑中取出，并写在模型可以据此训练的某个地方，[笑声] 瓶颈就又转移了。

这就是为什么我认为安全可以被自动化取代。这就是为什么我认为运维也可以被取代。我认为我们最终能够把那些东西写下来，即使我们目前还没能做到。

Google Brain 和 Coursera 的联合创始人 Andrew Ng 曾提到，他的团队中有人提议产品经理的数量应该是工程师的两倍，他说那是他人生中第一次遇到这种提议。但自那以后他的解决之道并不是去雇佣更多的产品经理，而是将这两份工作融合在一起。用他的话说，当一个工程师理解用户，能够对构建什么做出决策并直接将其构建出来时，他们能够以令人难以置信的速度执行。我认为我们正是从这里开始触及答案的。

在 20 世纪 60 年代，有一种职位叫系统分析师。他们的工作不是写代码，而是与业务方沟通并弄清楚问题到底是什么。

后来那个分析师演变成了我们今天所谓的产品经理，而原本的一个半工种变成了两个职业。我认为目前正在发生的，是它们重新塌缩为一个角色。我们正在回到 60 年代。所以这不再只是一个 AI 工程师。他们不仅仅在构建 AI，他们也不仅仅在用 AI 构建。他们在构建一切。他们在构建所有的软件。

<details>
<summary>Original English</summary>
What's left is finding out what people actually want. Every piece of software is a formalization of something that a human wanted to get done. Uh

So, if a customer tells you, "I need to to keep track of my orders," there are 10,000 pieces of software that keep track of your orders. That's what they do. Uh but only one of those, if you're lucky, is good if the thing that you're doing is you're running a bakery. If you're running like an auto parts store, that's going to be different. If you are running uh you know, a giant manufacturing concern, it's going to be completely different. The That requirement is not sufficient. The whole job is figuring out what exactly do you mean when you say that you want to keep track of your orders. What does that mean for your business? What does it have to do? How does that work?

Uh and that knowledge isn't in the training data. It isn't in the weights. It is in the mind of the person who runs that business. And the only way to get it out is by flapping your meat parts at them and having them flap their meat parts back. Like, you have to talk to them. That is the only way to get the information out.

Um And that work has a very important property, which is that it doesn't transfer. Uh if you think about what good means for like a calendar app and what good means for a scheduling app, those are solving almost the same problem, right? A calendar app and a scheduling [clears throat] app, but they're completely different pieces of software. They have totally different requirements and a totally different definition of good, even though [clears throat] those two use cases are so close together, and we have a zillion use cases.

Um Anytime that you've used software that has a zillion configuration options and it still doesn't [snorts] do what you need. I'm looking at you, Jira. Uh like that is the problem you're running into of software that is trying to do everything and still failing at it.

Um so the bottleneck moves to describing the problem and defining what it means to have solved the problem and my big bet for this talk and for the next 10 years is that is where it stays. Uh Fred Brooks, who ran IBM System 360 project and wrote uh The Mythical Man-Month, uh he wrote about this in 1986. He split the difficulty of software into two kinds. Accidental complexity is the difficulty of the tools or the languages, the typing, the syntax, and then there's the essential complexity, which is the prob- difficulty of the problem itself.

Uh and he predicted that no single tool would make us 10 times more productive because the essential part is the hard part. Uh and Brooks's prediction is looking pretty solid because we made code eight times faster and we still didn't get very much faster at shipping because the hard part is the essential part.

Um Shawn Grove from OpenAI made the same point uh 2 years ago. Uh no, sorry, a year ago. Uh what year is it? Um he said that code is a lossy projection of the specification and whoever writes the spec, if it's a PM or a lawmaker or an engineer or a marketer, they become the programmer. Uh and so writing [clears throat] down what good means is where the value is now. Uh I'm beginning to run out of time because I haven't timed this well. Um

anything that you can verify cheaply, you can train against until you beat it if you are model maker. Uh so uh Cognition tried to write down because of their benchmark about what what it counts to merge something, does it, you know, is is this code mergeable? They were like, let's see if we can figure out a benchmark that defines what mergeable really means. Let's see if we can get all of that other information into the benchmark, and then we can train a model on it. Um uh

Cursor's reviewer BugBot turns every thumbs down that you that your team gives it into a rule, and they have like 44,000 rules now. Uh so the moment the maintainer takes knowledge out of their brain and puts it somewhere written down that a model can train on it, [laughter] uh the bottleneck moves again.

That is why I think security can go. That is why I think operations can go. I think we can write those things down eventually, even though we haven't done it yet. Uh

Andrew Ng, the co-founder of Google Brain and Coursera Coursera, says that one of his team proposed having twice as many product managers as engineers, uh and he said that that was a first in his life, uh but his answer is since then hasn't been hire more PMs. It's to blur the jobs together. In his words, when an engineer understands users and can make decisions on what to build and build it directly, uh they can execute incredibly quickly, and that is where I think we are beginning to hit on the answer.

Uh in the 1960s, there there was a job called the systems analyst. Their job was not to write code. Their job was to talk to the business and find out what the problem was. Uh then that analyst turned into something that we call a product manager today, and we've had two professions uh where there used to be one and a half. I think what is happening is they are collapsing back into one. We are going back to the '60s. So that is not an AI engineer. They're not just building AI. They're not just building with AI. They are building everything. They are building all software.
</details>

### 产品工程师的崛起与初级工程师断层

我决定把这种岗位称为**产品工程师**。这类人负责发掘人们的需求，定义什么是“好”，并通过智能体代为打字将产品交付上线。

Gergo Orosz（我可能把他的名字念错了），他撰写了《Pragmatic Engineer》通讯，早在 2019 年他就将“具备产品思维的工程师”描述为工程师拥有的一项良好特质。而我现在要说的是，它已经从一项良好特质变成了基本要素。它已经从资深工程师曾经拥有的技能，转变为任何工程师如果还想继续当工程师就必须掌握的技能。

你可以看到市场已经在为此买单。形态与产品工程师非常相似的“前线部署工程师”（Forward Deployed Engineers），其招聘岗位数量在 2025 年的 9 个月内激增了 800%。他们无处不在，每个人都在试图招聘他们。在场的人里有谁正在试图招聘前线部署工程师？请举手。好的，比我预想的人数要多，好吧。

顺便提一下，前线部署工程师的平均薪酬是 240,000 美元。也就是说，它的薪资水平堪比资深工程师，因为它本身就是资深工程师。这是一种非常实用的工程师类型。但目前对于如何称呼它还没有达成共识。对于这种我所描述并随性决定命名为“产品工程师”的事物，存在着大概上千种不同的头衔。

此时此刻，你们中的某些人可能会想：那根本不是编程。你们说得对，那确实不是编程。编程是由智能体完成的。然而，这无可否认依然是软件开发。在 2026 年，我们不得不逐渐接受这样一个观念：成为软件开发者与成为程序员，二者已经分道扬镳。

当我说出“我认为难点在于决定什么是好”这样的话时，我意识到自己正掉入 AI 圈子里很多人都会掉入的陷阱：除了我所擅长的事情因为太难而无法被替代之外，关于一切事物的所有部分都可以被 AI 自动化。前几天我听到一位风投这么说，我的反应是：“老兄，别闹了。用不了几天就会有人把你的工作也自动化掉。”

所以大家对此要持保留态度。我是不是只是盲目地以为自己所享受的软件开发部分——即弄清楚问题是什么——就是软件最困难的部分？如果我错了，你们可以指出来。

但假设你们目前认同我的看法：编程走向归零，产品工程走向无限。这带来了一个新的重要问题，那就是初级开发者。因为过去我们培养初级开发者的方式，是给他们规格极其详尽的工单，上面写着：“专门按照这种方式写出这个软件，然后交给我，好让我指出你错在哪里的方方面面。”

而这种方式已经不复存在了，因为那是我们现在对编码智能体做的事情。我们对智能体说：“写出这个东西，然后我来告诉你你错在哪里。”然后我们与它们进行对话。那已经不再需要人类去做了。但我们仍然需要庞大数量的前线部署工程师或产品工程师，而我们必须从某个地方获得他们。我们不能直接抛弃刚刚入行并询问“我该如何做这些事？”的现当代新开发者。我们总不能回答：“我不知道，因为我也不知道你的工作现在到底算什么了。”

>> [哼笑]

这并不是理论上的未来。这是自 2023 年 1 月以来劳工统计数据的真实图表，按年龄进行了分类。红线代表 22 到 25 岁的工程师。他们的就业情况正在崩溃。我们没有在招收初级工程师。这不是我认为将会发生的事情，这是已经发生了两年的事实。他们的求职市场糟糕透顶。与此同时，41 到 49 岁年长工程师的就业率大幅上升，因为资深工程师仍然极具价值，甚至比以前更有价值。但初级工程师正处于极大的困境中，作为一整个行业，我们需要解决这个问题。

如果我们想要享受一个代码产出提升 10 倍、理清了软件供应链其余环节并明确了人类该做什么的世界所带来的红利，那么我们将需要大量的人力去付诸实践。我说过对软件的需求正在走向无限，我们需要无限的人手。我们打算从哪里获得他们？

到目前为止，我们一直只是在偶然间造就他们，而我们需要找到一种有意识培养他们的方法。Google 有一个名为 APM（助理产品经理）的项目，培养出来的人非常像产品工程师。他们每年培养 50 个人，而我们每年需要 10,000 个人。即使算上所有其他拥有类似 Google APM 项目（该项目被广泛效仿）的公司，他们一年也只能培养出大约 1,000 人。为了跟上需求，我们至少需要这个数字的 10 倍。

>> [哼笑]

大学教授数据结构，培训班教授 React，却没有任何人教授“去和面包师坐上一周，然后带着一份规格说明回来”。而那才是我们需要的人才。

所以如果你领导一支工程团队，你必须有意识地去培养他们。

IBM 已经在围绕与客户沟通并撰写规格说明来重新设计其初级岗位，而不是围绕编程本身。你们必须想办法为自己找到出路。你们必须弄清楚该如何培养产品型人才，并且必须尽快行动。因为我们本该在两年前就开始做这件事，现在有一大批非常悲伤且处于失业状态的初级开发者正面临这个问题。我们没有招聘他们，我们必须对此采取行动，否则倒霉的将不仅仅是他们，而是我们所有人。

<details>
<summary>Original English</summary>
Uh and I've decided to call this job the product engineer. This is somebody who finds out what people need, defines what good looks like, and ships it uh with agents doing the typing

um Gergo Orosz whose name I have probably butchered he writes the pragmatic engineer newsletter he described the product-minded engineer back in 2019 as a nice trait for an engineer to have and what I'm saying now is it has gone from nice to essential. It has gone from the from a skill that senior engineers used to have to a skill that every engineer has to have if they're going to be an engineer.

um And you can see the market already paying for this. Forward deployed engineers who look very much like product engineers job postings for them rose 800% in 9 months of 2025. They are everywhere everybody is trying to hire them. Who in this room is trying to hire a forward deployed engineer show of hands. Okay, well more I was expecting more hands oh well. uh

So uh The average comp for forward deployed forward deployed engineer by the way is $240,000 which is to say that it pays like a senior engineer because it is a senior engineer. It's a very useful kind of engineer. um But nobody agrees on what to call it yet. There are like a thousand different job titles for this thing that I am describing and have decided arbitrarily to call the product engineer.

um And probably at this point some of you are thinking that isn't programming and you are correct. It is not programming. The programming is being done by an agent. It is however recognizably still software development and we are going to have to wrap our minds around the idea that being a software developer and being a programmer have become divorced in 2026.

um And when I say stuff like well I think the hard part is deciding what good is I realize that I'm falling into a trap that lots of people in AI land fall into, which is all of the parts everything about everything can be automated by AI except the thing that I'm good at because that's too hard. I heard a VC say that the other day and I was like, "Buddy, uh like, no. No, someone is going to automate your job any day now. Um uh so you have to take this with a grain of salt. Am I Am I just thinking that the thing that I enjoy about software development, which is figuring out what the problem is, is the hard part of software? You can tell me if I'm wrong.

Um but say you believe me so far. Programming goes to zero, product engineering goes to infinity. That brings us to a new and important problem, which is junior developers because the way we used to train a junior developer is we used to give them very well-specified tickets that said, "Write this software this way in particular and then give it to me so that I can tell you all the ways that you were wrong."

Uh and that is gone because that's what we do with the That's what we do with the coding agents now. We say, "Write this thing and then I'll tell you how you're wrong." And then we have a conversation with them. Uh and there's That is not a job that we need a human to do anymore. But we still need an enormous number of forward-deployed engineers or uh product engineers and we have to get them from somewhere. We can't just abandon the current generation of new developers who've showed up and said, "How do I do this stuff?" We're like, "I don't know because I don't know what your job is anymore." Uh

>> [snorts]

>> this is not a theoretical future. This is an actual graph of labor statistics since January 2023. It is sorted by age. The red line is engineers aged 22 to 25. Their employment is collapsing. We are not hiring junior engineers. This is not a thing that I think is going to happen. This is a thing that's been happening for 2 years. Job market sucks for them. Meanwhile, the job for older engineers 41 to 49 has gone way up because senior engineers are still super valuable, more valuable than before, but junior engineers are being screwed and we need to fix that as a profession.

Uh so if we're going to reap the benefits of a world where we 10x code output and figured out the rest of the software supply chain and figured out what humans need to do, uh then we are going to need a lot of people to do that. I said that the demand for the software is going to infinity. We need infinity people. Where are we going to get them?

Uh we've been creating them accidentally so far and we need to figure out a way to do them on purpose. Google has a product uh has a program called the associate product manager program which turns out people that look very much like product engineers. They turn out 50 of them per year. We need 10,000 of them per year. Even if you look at all of the other pro all of the other companies that have something a program like Google's APM, it's being extensively copied. They're only turning out about a thousand people a year and we need 10 times that number at minimum uh to keep up with demand. Uh

>> [snorts]

>> universities teach data structures, boot camps teach React, nobody teaches go sit with a baker for a week and come back with a spec and that is the person that we need.

Um so if you lead an engineering team, you're going to have to grow them on purpose.

Uh IBM is already redesigning its entry-level role around talking to customers and writing specs instead of programming. Um you're going to have to figure out how to do that for yourself. You're going to have to figure out how do you train product people? Uh and you're going to have to do it very quickly because the time we should have started was two years ago and there's a whole cohort of very sad unemployed juniors right now who have this problem and we are not hiring them and we need to do something about that or we are going to be screwed and not just them.
</details>

### 手艺的延续与落地行动指南

如果这一切真的发生，还有一件大事我不想轻描淡写地带过或敷衍了事：许多人进入编程领域是因为他们热爱这门手艺。他们热爱清晰的抽象，热爱攻克棘手 bug 时的释怀感，热爱让机器完全按照自己的指令运转。他们当初入行可不是为了去采访面包师在生活里想要什么。那绝不是他们当初签约想做的工作。

他们会痛恨这一点。他们已经在痛恨了。他们正在极其大声地抱怨。我给不了他们什么安慰奖。

但我有一个观察：对于许多自以为热爱打字的人来说，也许你真正热爱的，恰恰是在你动手打字之前的那一瞬间——当你终于把问题理清的那一刻。那一部分并没有消失，那一部分依然存在。当你灵光一闪、心想“我知道该怎么把它做成一个在脑海中闪闪发光的、可复用的系统了”——那种创造性的火花是不会磨灭的。

编程这门手艺将会存活下来，就像木工在家具工厂出现后依然存活下来一样。程序员编写程序，就像歌手放声歌唱，对吧？他们在一个空无一人的房间里、在没有任何人注视的情况下写代码，纯粹只是因为热爱。这不会消失，你依然可以那么做。只是它不再会是别人每年付给你几十万美元让你去做的事情。

所以，这是我的预测：接下来的 10 年将会是艰难难熬的。过去的 2 年已经非常艰难。这些变革的重担在工具彻底成熟之前就已降临。初级工程师的晋升阶梯在我们找到培养更多新人的方法之前就已经断裂。许多热爱这门手艺的人将不得不做出抉择：自己是否热爱正在取代它的这份新工作。

但这种事以前就发生过。编译器，然后是框架，接着是开源，每一次都让前一代人大量的手工键入变得多余。而每一次经历这些之后，我们都迎来了更多的软件开发者。我们只是改变了“软件开发”的定义。

我认为这种情况将会再次发生。

10 年后，我们将迎来一个比今天规模更庞大、薪酬待遇基本相当、并且整体形态更偏向产品工程的行业。这就是我今天向大家阐述的论点。

但这全是些高维度的宏观预测，而我向来讨厌空谈预测。这在现实中究竟意味着什么？今天你们实际应该做些什么？

第一，为一个人类几乎不再参与代码生成的时代做好准备。因此，明确圈出你们那些高破坏半径（high blast radius）的代码，让它成为你们唯一还要亲自审查的内容，因为剩下的其余部分，你们的自动审查工具都会处理好。

第二，把所有低成本验证的任务全部委派出去。花大量时间去思考：我该如何构建一种自动化的机制，来判断眼前的这件东西——无论具体是什么——究竟好还是不好？然后把这个判定机制喂给你的智能体，而不是试图去理清审查流程。

最后，把你们最顶尖人才的判断力凝结成规格说明、评估准则（rubrics）和评测集（evals）。你们知道，作为 Arize 的人，我迟早会提到评测（evals）。把那些只存在于人们头脑中的东西转化为代码。作为产品工程师，这就是你们的工作：把对问题的感知转化为对问题的规格说明，以便让智能体代我们去构建它。

同时，去度量正确的事情。多写 741% 的代码从来不是重点。去度量你们实际交付了多少东西。去度量审查者的评论有多高的比例被真正采纳执行。去度量“测试通过”与“维护者愿意合并此代码”之间的差距。

并且记住，最后的审查者是生产环境。在生产环境中观察它的表现，并用另一个模型对其进行打分评估，这就是评测（eval）。我不会在这里推销 Arize，但这正是我们在做的事，也是我们眼下如此受欢迎的原因。我就点到为止。

3 年前，Swyx 写了关于 AI 工程师的兴起，那是指工程师学习如何使用模型进行构建。而产品工程师的兴起，则关乎当模型接管了构建工作之后，还剩下些什么。

发掘人们的需求，写下“什么是好”的定义，并将其打造成人们喜欢的产物——这就是现在的工作。无论我们喜欢与否，这将是在场每个人的工作。我们现在都是产品工程师。

非常感谢大家的时间与聆听。

>> [掌声]

<details>
<summary>Original English</summary>
Uh so if all of that happens, there's one big thing that I don't want to just gloss over or hand wave away, which is a lot of people got into programming because they love the craft. They love a clean abstraction, the feeling of a hard bug finally giving up, making a machine do exactly what you told it to do. They did not sign up to interview bakers about what they want in their lives. Like that is not the job that they signed up for. Um

and they are going to hate this. They already hate this. They are complaining about it very loudly. I have no consolation prize for them. Um but uh I do have an observation, which is that for a lot of people who think they love the typing, maybe what you loved was the moment just before you started typing, when you figured out the problem.

That That part doesn't go away. That part is still there. That creative spark when you're like, I know how to make this into a repeatable system that glows in my brain. That's not going away. Uh and the craft of programming will survive uh in the same way that like woodworking survived the furniture factory. Like programmers program the way that singers sing, right? They do it in an empty room with nobody watching just because they love it and that won't go away. You can still do that. Um it just won't be the thing that people pay you hundreds of thousands of dollars every year to do.

Um so here is my prediction. The next 10 years are going to be ugly. The last 2 years have been ugly. Um the load of this stuff is arriving before the tools are ready. The junior ladder is gone before we have figured out how to train more juniors uh and a lot of people who love the craft are going to have to decide if they love the job that is replacing it.

Um but this has happened before. Compilers and then frameworks and then open source each made a generations worth of typing before them uh unnecessary and each time we came out of it with more software developers. We just changed what software development meant. Uh and I think that's going to happen again.

Uh, in 10 years time we will get a profession that is bigger than today's, pays about as well, and is mostly shaped like product engineering. That is the case that I'm making for you today.

But that is a whole lot of high-level predictions, and I hate those. What does this mean for real? What should you actually do with this today?

Uh, first, be prepared for a world in which humans are barely involved in the production of code. So, write down your high blast radius code, and make that be the only thing that you are reviewing anymore, because the rest of it your automatic reviewers are going to get done.

Uh, then delegate that everything that's cheap to verify. Spend a lot of time thinking about how would I build an automatic way of telling whether this thing, whatever that thing is, is good or not, and then feed that to your agent instead of trying to figure out the review process.

Uh, and finally, put your best people's judgment into specs and rubrics and evals. You know, I the arise guy was going to say evals at some point. Uh, get stuff that exists only in people's heads into code. That is your job as a product product engineer. It is turning the sense of the problem into a spec of the problem, so that the agents can build it for us.

Uh, and measure the right thing. 741% more code was never the point. Measure how much stuff you are actually shipping. Uh, measure how often your reviewers comments get acted on. Measure the gap between the tests [clears throat] passed and a maintainer would merge this.

Uh, and remember that the last reviewer is production. Watching what it does there with another model grading it, that is an eval. I'm not going to pitch arise, that's just what we do, and that's why we're so popular right now. Uh, and I'll leave it at that. Um,

3 years ago, Swyx wrote about the rise of the AI engineer, which is engineers learning to build with models. And the rise of the product engineer is about what's left when the models do the building.

Uh, finding out what people need, writing down what good means, and making it something people like, that is the job now. It is going to be the job for everyone in this room, whether we like it or not. We are all product engineers now.

Thank you so much for your time and attention.

>> [applause]
</details>