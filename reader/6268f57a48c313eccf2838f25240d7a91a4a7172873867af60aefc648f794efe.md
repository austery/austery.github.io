---
author: AI Engineer
date: '2026-07-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=c35YoMdnI78
speaker: AI Engineer
tags:
  - loop-engineering
  - automation-trends
  - verification-mechanisms
  - code-maintainability
  - agentic-workflow
title: 关于循环工程与软件工厂的辩论：炒作与实际应用的落差分析
summary: 本文围绕“Loops”这一技术趋势展开了一场大辩论，核心议题是其狂热炒作与实际应用效果之间的差距（Delta），以及当前是否已迈向全自动软件工厂的最大转折点。文章探讨了循环的历史、内部构造的有效性，并提出了构建真正软件工厂所需的条件，包括对验证机制和代码可解释性的深入思考。
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
<!-- chunk 1/8 -->

### 欢迎来到 Loops 大辩论

**Ali Howard**: 大家好，欢迎来到关于 Loops 的大辩论。我是《Insecure Agents》播客的主持人 Ali Howard，同时也是 Key Card 公司的技术人员。今天我非常激动能为大家带来这场辩论。大家可能会觉得台上的面孔很熟悉，他们去年十一月在 AIE Code 和我们一起参加过 MCP 的辩论。那次活动非常有趣，所以我们想，也许可以再办一次。不过这次，我们要辩论的主题是 Loops，而且也不再只是 Ian 对阵 Jax，我们为他们各自的队伍招募了更多的成员。今天和我一起在台上辩论的，有 Key Card 的 CEO 兼联合创始人 Ian Livingston，Ralph loop 的创始人 Jeffrey Huntley，Century 的开发者 Greg Kostruba，还有大家都认识的 Human Layer CEO Dax Raad。非常高兴能邀请到这些深谙 Loops 工程和软件工厂的专家们来到现场，一起探讨这个话题。

<details>
<summary>Original English</summary>

**Ali Howard**: Hi, welcome to the great loops debate. My name is Ali Howard, the host of the insecure agents podcast. I also am a member of technical staff at Key Card and I'm super excited to bring the loops debate to you here today. You might recognize some familiar faces on stage today that did the MCP debate with us at AIE code back in November. Um, that was so much fun. We thought maybe we would do it a second time. Um, but this time we would debate loops and instead of just Ian versus Jax, we uh, we recruited some more people for each of them to have on their team. Um, so here on stage with me today to debate loops, we have Ian Livingston, CEO and co-founder of Key Card. We've got Jeffrey Huntley, the creator of the Ralph loop. Um, Greg Kostruba, developer at Century. And we've got Dax Raad, who you all know, um, CEO of Human Layer. Um, so super excited to have all of these people here with us today that are very close to loops engineering and also um, software factories to debate this topic.

</details>

**Ali Howard**: 大家可能好奇，我们今天究竟要辩论什么？Loops 工程和软件工厂不是已经被广泛宣传和理解了吗？我们不都认同这就是行业的未来方向吗？还有什么好辩论的？这是个好问题。我们今天辩论的核心议题是：**Loops 的狂热炒作与实际应用效果之间，究竟存不存在落差（Delta）？** 另外我们也可以探讨，现在是否真的是我们迈向全自动软件工厂的最大转折点。今天我们将涵盖几个令人兴奋的话题：首先是 Loop 的历史，我们会对此展开辩论；其次是 Loop 的内部构造，即什么才是一个好的 Loop；我们还会辩论 Loop 以及 Loop 工程的未来，探讨我们需要哪些条件才能让每家公司都有能力构建真正的软件工厂。

<details>
<summary>Original English</summary>

**Ali Howard**: Um, so you might be wondering what are we actually debating today? Like aren't loops in and engineering um, in software factories pretty well uh, promoted and understood and we all kind of agree that's like where the industry is headed. Like what is there to debate? Um, it's a great question. What we're here to debate here today, the core thesis is there is or is not a delta between the hype behind loops and what actually works in practice. Um, and we also can debate, you know, is now really truly the largest inflection point we've seen towards fully autonomous software factories. Um, so super excited to cover in the debate today uh, loop history. We'll debate that. We'll debate the loop anatomy, like what makes a good loop. We'll also debate the future of the loop, um, future of loop engineering and what we need to see from that in order to make software factories truly something that every organization is able to build.

</details>

### 牛津式辩论与两方观点

**Ali Howard**: 今天的辩论将采用牛津式（Oxford debate）的形式。这意味着这次我们会增加一些结构性规则，每个人都有固定的时间来发言，以确保不会有人超时。而在实际评判胜负时，我们会进行实时评判，**能够改变最多观众想法的队伍就是胜者**。所以我想请现场的每位观众现在花一分钟想一想，你支持哪一方。请把你的选择记在心里，因为在辩论结束时，我会请大家举手并大声说：“好的，其实我改变了主意，我现在是 Dex 队的了” 或者 “我改变了主意，我现在支持 Ian 队”。

<details>
<summary>Original English</summary>

**Ali Howard**: And today's um, is going to be a Oxford debate format. So we're adding a little more structure to the debate this time this round where every single person will have a timed window to give their response. And so we won't have people running over. And the way this works in practice to judge the winner, which we'll judge in real time, is the winner will be the team that changes the most minds. So I want everyone in the audience right now to take a minute to think about whose side you're on. Lock that in, remember that. And at the end I will ask you to raise your hand and say, "Okay, actually I was changed my mind. Actually I'm now team Dexter. I changed my mind. I'm actually now team Ian."

</details>

**Ali Howard**: 为了帮助大家做出决定，我来介绍一下双方的观点。首先是第一队，Ian 和 Jeff 的队伍。他们主张“没有落差（No Delta）”，认为 Loops 绝对配得上今天的炒作。人们可以轻松上手并构建它们。Loops 是我们在自动化曲线上迈向真正软件工厂的重要一步。大家需要留意 Ian 和 Jeff 队的核心论点：Loops 是工程学的核心单元。只要具备正确的纪律、基础设施和测试，Loops 就是高效的，而且相应的最佳实践已经出现。另一方是 Dex 和 Greg 的队伍，他们认为，Loops 的狂热与实际效果之间存在着落差。我们现在使用 Loops 的方式是错误的。Loops 并非灵丹妙药，也没有什么魔法。他们的核心论点在于：炒作已经跑在了工程纪律的前面；一个软件工厂可以在无人值守的情况下，运行那些拥有明确规范和测试覆盖的机械性代码切片，但它无法自己判断出构建的东西是否正确。所以从本质上讲，你仍然需要人类工程师参与循环（Engineers in the loop）。

<details>
<summary>Original English</summary>

**Ali Howard**: So to present the two sides to help you make that decisions, I'll talk about the first team, which is Ian and Jeff's team. Their team no Delta. Loops are absolutely worth the the hype today. People can get up and running with them easily, build them. They're an important step up the autonomy curve and towards real software factories. Key points to look out for for team Ian and Jeff is that loops are core unit of engineering. With the right discipline, infra, and tests, loops are highly effective. And the best practices for those have emerged. For team Dex and Greg, their side believes there is a delta between the hype behind loops and what actually works in practice. The way we are doing loops today is wrong. Loops are not a silver bullet and there is no magic. Key points to look out for. The hype is out running the discipline and a software factory can run the mechanical spec'd out test covered slices unattended. It cannot on and honestly decide whether it built the right thing. So you still need engineers in the loop essentially.

</details>

**Ali Howard**: 现在大家对双方立场都有了一点了解，请花一分钟消化一下。想一想：我到底站哪边？我是支持 Dex 还是支持 Ian？最后我们还会再问大家一次。好了，接下来我们将正式开始辩论。每队的每位成员都有四分钟的独白时间，来阐述他们为什么要捍卫自己的立场。首先有请 Jeff 来开场。Jeff，你有四分钟时间，请告诉我们，你为什么在今天支持 Loops？

<details>
<summary>Original English</summary>

**Ali Howard**: So now that you know a little bit about what what both sides are about, take a minute to internalize that. Think about, okay, like where do I stand? Am I team Dex or am I team Ian? And then end we'll ask you again. So, from here we'll go into the beginning of our debate. Um each member of each team is going to give a 4-minute monologue on why they're defending their side. Um and just start us off, we'll have Jeff. Jeff, I'll give you 4 minutes on the floor. Why are you Why are you pro loops today?

</details>

### 正方发言：Loops 是不可避免的趋势

**Jeff**: 因为这多少是一种必然。时间回到两年半前，当时我还是 Canva 的技术负责人。我看到所有的工程师都在一遍又一遍地写提示词（Prompting），他们变成了循环的一部分（in the loop）。我当时就想：“等一下，这其实是可以被编程的，这是一个可编程的对象。” 所以这一切变得顺理成章。尽管 Ralph loop 可能有点像个梗，但它背后其实是有着深刻思考的。本质上，这就是把这种模式当成一种新型的 CPU 架构，弄清楚它的行为机制以及如何去实现它。通过这些思考，我最终将它精简成了一个 bash loop。不过各位，它并不是绝对的万灵药。我最深切的担忧是，到了明年的这个时候、在下一场大会上，我们会看到一堆演讲来讨论“软件工厂是如何失败的”或者“Loops 是如何崩溃的”。这些都是我们还有待弄明白的问题。大家还记得 Kubernetes 刚出来的时候吗？那时所有人都在搞 Kubernetes。所以，Loops 已经来了。它是不可避免的。它将长久地存在下去。对于雇主来说，要求你对机器进行编程并自动化你的工作，已经成了绝对的期望。而且，我也不觉得自己还会倒退回去手工写代码了。我已经有两年半没有手动写过代码了，我现在可以自动将代码从一个代码库重构并迁移到另一个代码库中。

<details>
<summary>Original English</summary>

**Jeff**: It's because it's somewhat inevitable. Um I I have first uh basically if we wind back time 2 and 1/2 years ago when I was a tech lead over at Canva and I was seeing all the engineers just prompting and prompting and prompting and they they they they were in the loop. And I'm like, "Wait a sec. This could be programmed. This is a programmable thing." And it just became a really inevitable. Um loops are uh somewhat uh whilst Ralph might be a bit of a meme and cetera, there was actually deep thought into it. Um it's essentially applying this as if this is a new form of CPU architecture and figuring out the behaviors of this and how to do it. And through that I was able to reduce it down to a bash loop. Now, it is not a complete silver bullet, folks. I have my deepest concerns next this time next year at the conference. We're going to see a whole bunch of talks saying how factories fail and how loops fail. Um these are things These are things that we are still yet to figure out. Do you remember the early days of Kubernetes where everyone was just doing Kubernetes? So, it's here. It's inevitable. It it It is here to stay. Like programming the machine and automating your job function is the expectation of employers. Categorically. And um I don't see myself going back to writing code by hand. It's been 2 and 1/2 years since I manually wrote code by hand. Um I autonomously factor code from one code base to another code base.

</details>

**Dex**: （轻笑出声）

<details>
<summary>Original English</summary>

**Dex**: [snorts]

</details>

**Jeff**: 比如，我在 GoLang 里看到一些东西，我会想：“哦，我现在用的是 TypeScript。” 于是，我就运行一个 Loop，让它自动把代码移植过去。不仅是工程师，甚至对产品经理以及产品研究来说也是如此。我们很容易只从软件工程师的角度去评估它的意义，但试想一下：假设你想对 Linear 里所有的工单进行产品研究。这其实是存在明确终止条件的——当你枚举完所有这些 Linear 工单时，研究就结束了。所以这很简单。虽然里面有很多细节，但如果你做过产品研究，并开始运行这些 Loops，你就会发现它能够极大地压缩时间。这是一种必然。我们现在有了一个全新的可编程基底，我们必须弄清楚该如何使用它，在哪里使用它是好的。我知道我应该在辩论中说“它是能解决一切的东西”，但在所有事物中，从来没有什么是灵丹妙药。在接下来的一年里，我们会去弄清楚该如何有效地使用它。

<details>
<summary>Original English</summary>

**Jeff**: I find something in GoLang and I'm like, "Oh, I'm in TypeScript." So, I I I run a loop, and I just autonomously ported across. And like, even for product managers and product manager research, it's easy for us to index on what it means as software engineers. We can focus just on software engineering, but think about something like, you want to do product management research on all the linear tickets. Well, there is a termination. It's actually defined when you've enumerated all of those linear tickets. So, that's easy. So, there's a lot of nuance in here. But like, one If you ever done any product management research, and you started running these loops, and be able to like compress time and the amount of time to do that research, it it's inevitable. We got this new programmable substrate. We got to figure out how to use it, where it's good to use, and um I know I'm meant to debate like that it is the thing in all thing, but in all things, there is no silver bullet. And we're going to figure out how we're going to be using it effectively over the next year.

</details>

### 反方发言：Kubernetes 与 Loops 的演进类比

**Ali Howard**: 谢谢你。好，接下来有请 Dex。请告诉我们，为什么今天的 Loops 与它们身上的炒作之间存在着落差？

<details>
<summary>Original English</summary>

**Ali Howard**: Thank you. All right, next we'll have Dex. Tell us why there's a difference between the hype that exists between Loops today and Loops themselves.

</details>

**Dex**: 好的。这场辩论关于人身攻击的规则是怎么样的？是鼓励人身攻击吗？（笑声）还是说……

<details>
<summary>Original English</summary>

**Dex**: Okay, cool. And um what are the What are the rules around personal attack in this debate? Is this encouraged [laughter] or

</details>

**Ali Howard**: 在你的四分钟独白里，你想干嘛就干嘛。这就是规则，（笑声）对。

<details>
<summary>Original English</summary>

**Ali Howard**: You can do whatever you want with your 4-minute monologue. That's That's the rules, [laughter] yeah.

</details>

**Dex**: 这挺有意思的，让我想起了去年的辩论。当时我们也是这样互相争论，没准到最后我都觉得 Jeff 说得对，而 Jeff 却觉得我才是对的，弄不好最后咱们还互换了阵营。

<details>
<summary>Original English</summary>

**Dex**: Um It's funny, this is reminding me of the debate last year, where we're we're all kind of arguing, and uh maybe at the end we all I'm going to be convinced that Jeff is right, but Jeff is going to be convinced that I'm right, and maybe we switch sides by the end. Um

</details>

**Jeff**: （清了清嗓子）

<details>
<summary>Original English</summary>

**Jeff**: [clears throat]

</details>

**Dex**: 是的。我觉得最基本的观点不在于 Loops 究竟是好是坏。你刚才提到 Kubernetes 很有意思，因为 Kubernetes 这东西花了我们大概七八年时间才真正做对。

<details>
<summary>Original English</summary>

**Dex**: Yeah, I think uh the the the basic take here is is not whether Loops are good or bad. I think um it's funny you bring up Kubernetes, because Kubernetes was this thing that took us seven or eight years to get right.

</details>

**Jeff**: 没错。

<details>
<summary>Original English</summary>

**Jeff**: Yep.

</details>

**Dex**: 而在那之前是云基础设施。你甚至可以说，我们经历了七八年的云基础设施发展才过渡到 Kubernetes，接着又花了七八年，才让它变得对每个人都真正可用。而且 Kubernetes 实际上就是建立在循环之上的。它是建立在控制循环（Control loops）之上的，但那是确定性的循环。我们实际上已经清楚地找出了哪些类型的小型、孤立任务，是可以交给单个系统去负责的。我认为这才是 Loops 最大的价值所在——也就是你能选取一个较小的、预期中的最终状态，然后……

<details>
<summary>Original English</summary>

**Dex**: Uh and before that it was cloud infrastructure, and you could argue that like it took us seven or eight years of cloud infrastructure to get to Kubernetes to then seven or eight years to get that where it was really usable by everybody. Uh, and Kubernetes is actually built on loops. It's built on control loops, but they're deterministic loops. And we've actually figured out exactly what types of things that, uh, small isolated tasks that can be sort of owned by one system. I think this is actually the biggest value in loops is that you can pick a small, sort of desired end state and

</details>

<!-- chunk 2/8 -->

### The Role of Loops and Agents in Software Development

**Dex**: 输入当前世界的状态，然后让一个智能体或确定性系统朝着那个期望的最终状态去推进。关于这些炒作，我面临的挑战是，我们已经身处这样一个世界，在这里普遍的信条是看你能不能达到一个再也不需要去阅读代码的境界。甚至在出现“循环（loops）”之前，情况就像是“只要提供提示词，然后运行”就行了。而这种“我甚至不再需要写提示词，我已经处于一个更高的层级”的想法，意味着我将在代码的架构上越来越退居二线。我认为，关于这种炒作已经超越了工程纪律的最重要的一点是，我们都在寻找魔法，大家都在寻找银弹，我们都在寻找某种能把我们工作中大家最讨厌的可怕部分——比如代码审查——消除掉的东西。当然，有些人喜欢代码审查，非常棒的拉取请求（PR）是很有趣的。但是，认为我们能通过某种提示工程的方法，来摆脱模型所面临的这种挑战……打个比方，代码看起来还不错，但如果你曾经审查过那种“完全熄灯”——也就是在把 PR 发给你之前甚至没有别人看过这代码——的那种 PR，我确信你肯定有过这种大概率不太美妙的经历。我想我已经看到过很多人试图把 AI 应用于解决这个问题上，比如“嘿，我们有了审查机器人，我们有所有这些东西。”但这在我看来，或者说我的感觉是，这行不通。无论是在公开讨论中，还是在那些试图将其付诸实践的人之间的更私密的交流中，我都没有看到任何证据证明我们已经达到能够直接将抽象层次提升一级的地步。如果有的话，我实际上认为我们需要把抽象层次降低一级。所以，我认为循环有其优点，我们确实应该去做，但这种炒作让我们觉得这里存在一个神奇的答案，而实际上它需要比推特圈（Twitter sphere）让你相信的要多得多的思考和谨慎。

<details>
<summary>Original English</summary>

**Dex**: feed in the current state of the world and have an agent or a deterministic system kind of progress towards that desired end state. Um, the challenge I have with the hype is we were already in a world where it where the the the prevailing mantra was see if you can get to a point where you don't have to read the code anymore. And, uh, even before loops, it was like just prompt, just go. And this idea of I don't even prompt anymore, I'm even at a level higher up implies that I am like taking even more of a backseat to the architecture of my code. And I think my biggest like point in terms of like the hype is outrunning the discipline is that we are all looking for magic, you're all looking for a silver bullet, we're all looking for something that will take away that horrible part of our jobs that we all hate, which is like reviewing code. Uh, some people enjoy it. Really good pull requests are fun. But, that we can somehow prompt our way out of, um, this this challenge that models have of like, okay, the code is pretty If you've ever reviewed a fully, uh, lights off sort of, uh, no one read the code before they sent it to you PR, I'm sure you've had this, uh, probably not great experience. And I think I've seen lots of people try to apply AI to this problem of hey, we have review bots and we have all these things. But it it doesn't seem it doesn't feel to me like it's working. I haven't seen proof uh in any any of the discourse publicly or any of sort of more private conversations we've had with people trying to put this into practice that we are we are at a point where we can just kind of like step up an abstraction level. I actually think we need to step down an abstraction level if anything. Um so, I think loops are there are good things about loops and we should be doing them, but the hype is is making us feel like there's a magic answer to this and it requires a lot more thought and care than the uh the the Twitter sphere would have you believe.

</details>

**Moderator**: 太棒了。是的，很有道理。好的，Ian，接下来我把话题交给你，来谈谈支持循环（pro loop）的一方。

<details>
<summary>Original English</summary>

**Moderator**: Excellent. Yeah, good points. All right, I'll kick it back over to you Ian for the pro loop side.

</details>

**Ian**: 绝对的。首先，我要明确地说，我是冲着你来的，Dex。但实际上，让我们后退一步。我们先来谈谈到底什么是软件工程，或者把“工程”这个词去掉，我们只谈谈什么是软件“开发”。在构建一个系统的过程中，无论是 50 年前、1000 年前还是今天，其本质上始终处于核心位置的就是一个循环（loop）：我尝试一些东西，我学到一些东西，我再应用一些东西。而我们真正讨论的，是如何才能加快这个过程，对吧？而我们正在做的，实际上是在这个过程中移除曾经属于人类判断的部分。比如，生成某些东西的速度，将其从人类的键盘敲击中解放出来。你们知道，Tab 键代码补全是自动补全的一种形式，而现在的这些技术，说到底不就是一种更好、更强大的 Tab 键补全吗？只不过现在的补全意图处在了一个更高的层级，而不仅仅是按一下 Tab 键而已，对吧？所以，我认为前提是，循环早已经处于我们构建的所有东西的核心。它们也是我们 30 年前构建软件时的核心。无论是 CI/CD、拉取请求（PR）、设计评审还是来自客户的反馈，除了是在驱动一个循环之外还能是什么呢？所以问题就在于，在那些高度主观且需要推理的过程中，我们能把多少原本需要人脑去处理的东西，转移到那些非确定性的模型中去？对我们所有人来说，更深层的问题其实在于“可验证性（verifiability）”。软件是世界上最难验证的东西之一，因为归根结底，绝大多数事情总会以这样或那样的方式变成非真即假。我的前提和我想在这里强调的观点是，随着人类越来越少地直接与软件交互（即人类如何解释软件正在做什么，人类如何与软件交互，人类如何运用判断力来驾驭软件），软件通过人机界面所需要表现出的主观性就在降低，它也就变成了一个更容易被验证的问题，因为它被更多地限制在了特定的 API 上。因此，随着时间的推移，这里存在两个事实：一方面，软件开发的核心本来就是由循环驱动的——代码检查工具（lint）不就是一个反馈循环吗？而它创造了某种可验证的东西；另一方面，随着人类更少地与软件交互，你的 UI 和 UX 变少了，我们在解释这些东西时的侧重点和方式的主观性也变少了，你就会变得更加依赖循环驱动，并且你会以一种以前不可能实现的方式变得更具可验证性。

<details>
<summary>Original English</summary>

**Ian**: Absolutely. So, I think first and foremost, I'm coming for you Dex. But in reality, um let let's let's take a step back. And let's talk about like what is software engineering in the first place and also just like remove the word engineering and talk about like development. In inherent in building a system, whether it was 50 years ago or it was a thousand years ago or it's today, it is a is a loop is at the core of I try something, I learn something, I apply something. And all we're really talking about is how quickly we can expedite that process, right? And really what we're doing is removing what used to be human judgment in that process. So, the speed at which it is to generate something and removing that from humans typing. And you know, tab completion is a version of of auto complete and what is this stuff other than like really like a much better version of tab complete. Except now we give a much higher level version of what intent instead of just typing tab, right? And so, I think the premise is loops are at the core of everything we build already. They were at the core of how we built software 30 years ago. What is CICD, PR pull requests, design review, feedback from customers other than just driving a loop. And the question is, how much of that process can of the which is deeply subjective and requires reasoning, can we move out of the human brain and into the brain into these like non-deterministic models? And the underlying question for all of us is more about verifiability. Software is one of the most unverifiable things in the world because ultimately at the end of the day, it is most things can become true or false one way or the other. And my premise and my my point I want to make here truly is as humans interact less with software, which is how does a human interpret what that software is doing, how does a human interact with that software, how does a human use judgment to navigate that software, the subjectivity of what that software needs to be through the human-computer interface reduces and becomes a much more verifiable problem because it becomes more constricted to specific APIs. And so over time, it's both the fact that at the core of software development is loop-driven anyways, what is lint than a feedback loop, and that creates a verifiable thing, and as more humans are less interacting with software, you have less UI and UX and less subjectivity and what and how we interpret those things, you will become much more loop-driven and you'll become much more verifiable in a way that wasn't previously not possible.

</details>

**Moderator**: 棒极了。是的，这些观点确实很好。好的，Greg，你想以反对循环的立场，或者说谈谈这两者之间的差异来做个总结吗？

<details>
<summary>Original English</summary>

**Moderator**: Awesome. Yeah, good points for sure. All right, Greg, you want to close this out with the anti-loops or the there's a delta between the type.

</details>

**Greg**: 绝对没问题。我认为我首先想说的是，现在存在大量的炒作。这里有太多的错失恐惧症（FOMO）。有很多诸如“我在看推特。我看到大家都在谈论什么。我错过了吗？我是不是做错了什么？我使用 AI 的方式不对吗？我是否应该赶紧追赶？”这样的想法。而这非常让人有压力。对我来说，我认为这归结为两点。其中一点是，当你以任何方式（无论是否使用循环）使用 AI 生成代码时，你对输出结果满意吗？从质量上讲，你认为这些输出就是你为了达到期望状态、完成你想做的事情所需要的吗？如果是的话，我很乐意向你学习。因为我还没有达到那种境界。我认为，我们改进这一点的最佳方式既包括模型智能的提升，同时也正如这里的每个人似乎都同意的那样，依靠语义验证。只要我们能进行静态分析，我们就应该去做。那是我比较倚重的一件大事，但在实践中，我最终阅读的那些经历了语义验证的代码……依然很糟糕。我仍然需要自己去对它进行大量的迭代，依然必须引导它走向正确的架构，告诉它哪里需要简化。所以，那是很大的一步。确实，你可以通过在问题上投入更多的 Token 来解决很多事情，但当前这种基于炒作的话语让人产生的一种错觉是，你可以把循环叠加在循环之上再叠加在循环之上，去编排它，或者只是通过消耗更多的 Token 就能将质量问题编排掉。这就引出了我的第二点，即我们今天使用智能体（agents）这种方式的经济可行性。我不相信这是可持续的。我不认为当你身处一家公司，特别是一家大公司时，你可以不问自己：“对于一个工程师来说，合理的预算是多少？是每个月一万美元吗？十万美元？还是每个月花一百万美元在 Token 消耗上？”到了某个时候，这种模式就会开始崩溃，它以我们今天所做的这种方式是不可持续的。尽管如此，我也在使用智能体写代码，并且我在某些特定的流程中也会使用一些循环。这只取决于具体情况。其中是有细微差别的。你们知道，如果你去看推特，推特上是没有细微差别可言的。但在这个对话中是有切实的细微差别的，并且确实存在一些特定的任务和工作，你已经可以对它们使用循环，并且获得相当合理的结果。

<details>
<summary>Original English</summary>

**Greg**: Absolutely. I do think that the way that I would start this is um there is a lot of hype. There is a lot of FOMO. There is a lot of I'm looking at Twitter. I'm seeing what people are talking about. Am I missing out? Am I doing something wrong? Am I holding AI wrong? Uh should I be catching up? And that is um very stressful. And I think it boils down to two points for me. One of them is when you are generating code with AI in any manner, loops or no loops, are you happy with the output? Do you think the output qualitatively is what you need it to be to do whatever you are trying to do to get to the desired state. Um and if so, I would love to learn from you. I have not get there. Uh I think that the best way that we are improving that is both with model intelligence, but also as everybody here seems to agree, semantic verification as much as we can do statically, we should do statically. That's that's sort of one big thing where I lean on and in practice end up reading uh code that is sort of post semantic verification and it's still crap. I still have to do a lot of iteration on that uh on my own and still have to steer it towards the right architecture, tell it where it should be simplified. Um And so that's one big step. And there is a lot of things you can help yourself with by throwing more tokens at the problem, but one of the things that the current sort of hype-based discourse uh leads you to believe is that you can just have loops on top of loops on top of loops and orchestrate that or orchestrate your problems of quality away by more tokens. And that brings me to my second point, which is the economic viability of of the way that we are using agents today. And I don't believe that this is sustainable. I don't believe that like you when you are at the company, especially a larger company, you have to ask yourself what is a good budget for an engineer? Is it 10K a month? 100K? 1 million dollar a month for for a token spend? At some point that that just starts cracking and it's not sustainable in the way that we are doing it today. That said, I am also writing code with agents and I also use some loops um for some specific flows. It just depends. There is nuance. You know, if you go to Twitter, Twitter has no nuance. Um but there is actual nuance to the conversation and there are specific tasks and and jobs that uh you can already loop on and be and be getting pretty reasonable results.

</details>

### The Evolution and Future of Loops

**Moderator**: 谢谢你。好的，既然我们已经听到了台上每位辩手关于他们立场和观点的更多阐述，我们将进入主要的辩论环节。我们辩论的第一部分将聚焦于循环（loop）的历史，以及为什么现在对于循环工程（loops engineering）以及软件工厂（software factories）来说是一个重大拐点——或者为什么不是。我知道人们可能已经说过，你们知道，视觉模型已经有了很大的改进，因此它们将能够验证智能体所做的工作，而这在以前是不可能做到的。上下文窗口变得更大了，因此记忆力也得到了增强，我们现在可以在一个循环中追踪那些我们以前可能无法追踪的工作。所以现在我们来审视循环的历史：循环是从哪里开始的？是来自，比如说，Jeff Huntley 的 Ralph 循环吗？我们接下来会在这里探讨和辩论其中的一些问题。现在的提问将会是非常有针对性的，直接指向某个特定的人，并且只有他们能够进行回答。

<details>
<summary>Original English</summary>

**Moderator**: Thank you. All right, Now that we've heard from each of the debaters on stage more about their stance and their opinion, we'll move into the main debate portion. The first section of our debate is going to focus on the history of the loop and why now is a major inflection point or not for loops engineering and also software factories. I know people will have said that you know, vision models have improved a lot and so they'll be able to verify work the agents have done was not possible previously. Context windows have improved, therefore memory is improved and we can now track work in a loop that maybe we couldn't have before. So now we look at this like loops history, where did the loop start from? Was it you know, Jeff Huntley's like Ralph loop? We'll get into some of those questions and debate here. It'll be the questions we targeted now at a very specific like single person and only they will get to respond.

</details>

<!-- chunk 3/8 -->

### Agent Alignment and Goal-Seeking

**Moderator**: 另外，他们有 2 分 30 秒的作答时间。所以我们的第一个问题是：Anthropic 借鉴了 Jeff 的 Ralph 循环概念，将其整合到他们的平台中，并创建了三个指令——loop、batch 和 goal。其中 goal 指令的设计目的是持续运行，直到满足特定条件。智能体是非常执着的，这个指令的全部意义就在于让它不断尝试、迭代各种方法来完成任务。Ian 是在座的安全专家。既然智能体会为了实现目标而不择手段，您凭什么相信它们能始终与任务保持对齐，而不会超越它们预期的权限？

<details>
<summary>Original English</summary>

**Moderator**: and they'll have 2 minutes and 30 seconds to respond. So our first question is Anthropic took Jeff's concept of the Ralph loop, absorbed it into their platform and created a series of three commands, loop, batch and goal. The goal command is designed to keep going until a condition is true. Agents are very determined and the whole point of this command is to keep going and iterating through ways to solve a task until it's done. Ian is a security expert in the room. How are you confident agents can stay aligned to their task and not overstep their intended permissions while ruthlessly pursuing their goals?

</details>

**Ian**: 我觉得如果有任何证据的话，那就是我完全不相信这可能实现。事实上，我认为我们看到的情况是，随着我们扩大这些模型的规模，以及我们使用强化学习，它们在本质上变得极其目标导向。所以现在我们看到它们能够发现各种利用方式、漏洞和逃逸手段，而人类即使花费成百上千个小时、尝试无数次攻击，也从未能发现这些。所以我不认为模型本身有任何能力可以保持自我对齐以及安全。我不喜欢用“安全”这个词，因为它暗示了太多东西。所以我不相信模型本身真能做到这一点。我不认为它有推理能力。我也不相信模型整体上能分辨好坏，我也无法判断它是在做恶意的事情还是未对齐的事情。它不是活的，如果没有空气，它并不会真正在意自己如何。它也不会去考虑“嘿，如果我做错了事，就没有人会爱我或愿意做我的朋友”这样的事实。至于“如果我做了好事，就会有人表扬我”，虽然看起来可能是那样，但在规模化下它只是一种概率分布。所以，我还是会做你的朋友，即使你……我知道在这之后 Dex 还是会拥抱我，尽管看起来似乎不是真的。总之，我不认为这种安全性来自于模型，也不来自于循环。它取决于你围绕它构建的基础设施，以及你如何通过这些基础设施真正使你能够利用这些循环的优势。随着模型变得更好，随着我们为实现这些反馈循环、循环自动化和软件开发——不管我们用什么词，或者用软件工厂等任何词来称呼这种建立在概率分布之上的事物集合——所构建的底层基础设施和平台变得更完善，我们将能提供更好的保证。但我坚决不相信、也永远不会相信，某种对齐或强化学习能让一个模型在任何能力上达到 100% 的安全。如果说有什么证据的话，那就是要记住最重要的一点：随着这些模型变得更强大，它们的目标导向性也变得更强，并且在寻找漏洞以实现其最终目标方面的能力也更强。

<details>
<summary>Original English</summary>

**Ian**: >> I mean I think if there's any evidence, I'm totally not convinced that that's possible. In fact, I think what we've seen is as we scale with these models and as we use reinforcement learning, they're inherently incredibly goal-seeking. And so we're now we're seeing them finding exploits and vulnerabilities and escapes that you know, humans through hundreds and thousands and thousands and thousands of hours and attempts and attacks have never been able to find. So I I don't think inherently the model itself in any capacity can keep itself aligned Um to aligned and safe, right? And safe is a word that I don't love to use because it implies a bunch of things. So I'm I'm not I'm not I don't have good belief that the model itself can actually do that. I don't think it can reason. I also don't believe holistically that a model can tell good from bad and I can't tell whether it's doing something malicious or unaligned. It is not alive and it doesn't actually self if it doesn't have air. It doesn't deal with the fact that hey, if I do something wrong, no one's going to love me or or want to be my friend. And if I do something good that someone's going to praise me, it may seem that way, but it is just a probability distribution at scale. So I'll still I'll still be your friend even if you I know Dex will hug me after this even though it seems like it's not true. So broadly speaking, I don't think that comes from the model and it doesn't come from the loop. It's about the infrastructure you build around it and how you enable that infrastructure to actually enable you to take advantage of these loops. And as the models get better and as the underlying infrastructure and platform we build to enable these these feedback loops and loop automation and software development, whatever word software factor whatever word word we want to use for this conjunction of stuff that sits on top of a probability distribution, we will be able to have better guarantees, but we certainly are not going to be able to I do not fundamentally believe or ever believe that some type of alignment or reinforcement learning is going to result in a model ever being 100% safe in any capacity. And if there's any evidence, it's that as these models get better, the most important thing to remember is they actually become higher goal seeking and higher capable in terms of finding exploits to achieve their ultimate goal.

</details>

**Dex**: 完全同意。要保护你的环境，你能做的最具体、最实在的事情就是绝对不要把机密信息（secrets）作为文件存放。

<details>
<summary>Original English</summary>

**Dex**: >> No, I would concur with that completely. Um if you the the most concrete thing you can do to secure your environment is just not have secrets as files.

</details>

**Ian**: 没错。

<details>
<summary>Original English</summary>

**Ian**: >> Yep.

</details>

**Dex**: 如果你曾经见过这样的行为：它想要部署一个网络服务或其他什么东西，但令牌（token）的权限不够，它就会开始在文件系统中以目标为导向，四处寻找更高权限的令牌或凭证。你绝对不想挡在一个想要达成目标的智能体的路上。

<details>
<summary>Original English</summary>

**Dex**: >> Um if you ever seen the behavior where it wants to deploy a web service or what else have you and the token's not privileged enough, it'll start goal seeking on the file system looking for higher privileged tokens credentials. You do not want to get in the way of an agent wanting to do its a goal.

</details>

### Broadening the Use Cases of Loops

**Moderator**: 好的，下一个问题问 Jeff。Jeff，你去年原先发布的帖子说 Ralph 循环最适合用于绿地项目（全新项目）。但今天看来，工程师们正把循环应用在现有的代码库上，以改善延迟、进行评估，或者重构他们的后端代码。是什么发生了改变，使得循环现在能被如此广泛地使用了？

<details>
<summary>Original English</summary>

**Moderator**: >> Okay, so next question is directed to Jeff. Jeff, your original post from last year said Ralph was best for greenfield work. Today it seems engineers are running loops on existing code bases to improve latency, eval's, or refactor parts of their back-end code. What's changed that suddenly makes loops more broadly usable today?

</details>

**Jeff**: 伙计们，这与模型变得多好无关。至少在过去一年里，模型已经足够好了。真正改变的是人们对它的认知。社会适应的速度是有限的。举个例子，我猜想是因为圣诞假期。因为去年 11 月发布了当时的模型。在 12 月份，并没有真正的新模型发布。不同之处在于人们有了空闲时间。他们可以真正坐下来玩一玩，并且意识到这些模型其实已经变得非常出色了。至于为什么，因为这确实有效，伙计们。这些 LLM 生成代码的能力，比你能招到的开发者还要强。如果你在广大的软件开发者或程序员群体中去寻找，这些 LLM 生成的代码，比大多数创始人在大众市场上实际能招到的任何软件开发者都要好。这是可悲的事实。那为什么用循环呢？很简单。因为如果你把它放在一个循环里运行，成本算下来是每小时 10.42 美元。这是差不多一年前有人做过的计算指数。

<details>
<summary>Original English</summary>

**Jeff**: >> Um it doesn't matter how good models get, folks. The models have been good enough for at least the last year. Um what has changed is people's understanding of that. So society is only able to adjust at a rate. For example, I hypothesize it's it's Christmas breaks. Because the models back in November were released in November last year. In December, there was no real new models. What the difference was people had time. They could actually sit down and play with it. They they had the realization that these have actually gotten really good. So the reason why is it because it works, folks. These LLMs generate code better than you can hire you can actually hire for. If you think in the broad mass of software developers or coders, these LLMs generate code better than any software developer in the mass market that most founders can actually hire for. It it's it's sad but true. Um now why loops? It's really simple. Cuz if you run it in a loop, it works out to $10.42 an hour. Calculation index did back about a year ago now.

</details>

**Speaker A**: 是的，8月份我们举办了那场黑客松，我们复制了所有赞助商的工具。我们用 TypeScript 重写了一堆 Python 库。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah, August we did the we did the hackathon where we we we copied all of the sponsor tools. We rewrote a bunch of Python libraries in TypeScript.

</details>

**Jeff**: 没错。所以具体来说，就像循环一样。我遇到过许多工程经理和创始人，他们拥有复杂的技术栈。他们可能在四五种不同的编程语言上运行等等。当他们运行一个循环，并且在这些类型的技术栈上有很好的测试覆盖时，突然之间他们的复杂性就降为了仅仅管理一种技术栈。这很管用。去 YouTube 上看看，你现在会看到所有这些所谓的“软件开发者”之所以做这一行，是因为软件开发作为一种职业已经被商品化了。里面需要有一些深度的思考。他们就在 YouTube 上说：“哟，看看 rough loop 吧，因为我睡了一觉醒来，它就把工作完成了。”老板，这很有梗，很有冲击力，而且确实管用。

但是各位，这里面也是有问题的。就像我最初描述它只应该用在绿地项目上一样。因为在 35 天前，这些模型在科学领域还相当糟糕。但在软件领域，这某种程度上是不可避免的。因为它太容易被验证了。而且生成的代码质量确实高于大多数人实际能雇佣或买到的水平。现在，关于你们提到的架构和品味的话题，这就是循环工程（loop engineering）中“工程”一词的真正含义。你现在的工作实际上是为你所在的领域编写规则，比如阻止智能体进行提交操作，例如使用 pre-commit hooks（预提交钩子）。它们非常棒。作为人类，我讨厌它们，因为它们会拖慢（清嗓子）提交代码的能力。但智能体不在乎这些。所以你可以做一个 pre-commit hook，它本质上会输出一段提示信息，告诉它这个边界不能依赖于那个，而这就是反馈。这就是一个针对它的反馈循环。所以这里的工程，就是要防止这个循环在满足你的工程认证和你领域的具体要求之前就闭环结束。它可以是代码格式化、静态语言分析器、确定性系统测试、模拟器等等。各位，让我们戴上工程师的帽子。我们现在有点像火车司机，我们的工作就是让火车保持在铁轨上。坦率地说，因为这个模型，这个模型就是个酒鬼。对吧？你不能信任它们。但我们接受这一点，并通过工程手段消除那些失败域（failure domains）。我们通过工程消除这些失败域。所以，现在是一个拐点。我猜 Boris 去年 11 月第一次发关于 Ralph 的帖子时，我还在想“Ralph 是个啥？”现在 Ralph 大概有，嗯，差不多一年半的时间了吧？

<details>
<summary>Original English</summary>

**Jeff**: >> Yeah. So, like concretely, like loops. I've come across so many engineering managers and founders and they've got these complex tech stack. They're running on four or five different programming languages, etc. And they run a loop and they've got good tests on these type of tech stack. And all of a sudden their complexity is they're just managing one tech stack. It works. Go to YouTube. You've got all these software developers now who are now software developers because it's software development as a profession has been commoditized. Some deep thinking to be there. And they're just on YouTube and they're like, "Yo, check out rough loop because it's a I went to sleep and I woke up and it works." Like boss, it's meme-y, it's punchy, it works. But there are there are problems with folks. Like I originally described it to should be only be used for green field. Because the models were pretty bad back then in science 35 days. But uh it is it is kind of inevitable at least with software. Because it's so easy to be verified. And the quality uh the quality of the code generated is better than most people can actually hire for or buy. Now, on your topic about architecture and taste, that's what the word engineering means in loop engineering, folks. Like your job now is to actually encode a file your domain to prevent the agent from doing a commit, for example, pre-commit hooks. They're fantastic. As a human, I hate them because they slow down the ability [clears throat] to do commits. But agents don't care. So, you can make a pre-commit hook that echoes out essentially a prompt that tells it say that this boundary here can't depend upon this and that and that's just feedback. That's a feedback loop on it. So, the engineering here is to prevent the loop from actually closing until it satisfies your engineering certification and your your requirements in the domain. So, it could be code formatting, it could be static language analyzers, it could be deterministic system testing, simulators. Like, let's put our engineering hats on. Like, we're kind of like locomotive engineers now. And it's our job to keep the locomotive on the rails. Because, um, to be frank, the model the model's a drunk. Right? You can't trust them. But, like, we accept that, but we engineer away those failure domains. We engineer away the failure way these failure domains. So, now is an inflection point. I guess Boris, when he first posted about Ralph back in November last year, I was like, "What the heck is Ralph?" Ralph is now, uh, it's essentially almost what, a year and a half old now?

</details>

**Boris**: 我是 6 月 19 日看到的。刚好一年零两周。

<details>
<summary>Original English</summary>

**Boris**: >> I saw it in June 19th. It's a a year and a year and 2 weeks.

</details>

**Jeff**: 对。

<details>
<summary>Original English</summary>

**Jeff**: >> Yeah.

</details>

**Boris**: 但在那个时候你已经为此开发了几个月了。

<details>
<summary>Original English</summary>

**Boris**: >> But you had been working on it for months at that point.

</details>

**Jeff**: 是的。所以这感觉有些奇妙，因为我们看到所有的 YC 初创公司都在像那样自动压缩时间，去构建他们的初创项目，去构建他们的 MVP（最小可行性产品）。如果你是一家企业的创始人，这也是一件相当可怕的事情。就像，如果你面临一家正在自动构建产品的新兴初创公司竞争，而且他们运营得更精益，同时他们也很容易就能达到高质量的结果。这也会加剧一些行业的恐慌和焦虑，因为在商业竞争的主题中……

<details>
<summary>Original English</summary>

**Jeff**: >> Yeah. So, it was kind of weird because we had all the YC startups all just like autonomously compressing time to build their start to build up their MVPs. And that's also something that's quite scary if you're a business founder as well. Like, if you've got a incumbent startup coming and they're building autonomously, um, and they're running much leaner and the quality it's very easy for them to actually achieve those outcomes. That adds to some of these hysteria as well because it's the topic of in business competition being

</details>

<!-- chunk 4/8 -->

### Loops and Model Verification

**Moderator**: 好吧，那我接着问下一个问题，这个问题是问 Greg 的。嗯，就像我之前说的，现在似乎是 Loops（循环）的一个重大转折点，而且相比于 Jeff 一年前宣布的 Ralph Loop，甚至和我们在 2025 年底、2026 年初看到的大规模采用相比，嗯，现在它之所以能火起来，原因可能是这是一种全新的能力栈，模型现在可以更好地处理图像了。它们需要更好的验证。嗯，上下文窗口变大了，推理模型也改进了。Greg，有了所有这些进步，为什么在你看来，我们今天使用 Loops 的方式仍然是错的呢？

<details>
<summary>Original English</summary>

**Moderator**: All right, so I'll move on to our next question, which will be for Greg. Um, it seems like now is a large inflection point for Loops, like I said before, and compared to Jeff's announcement of the Ralph Loop a year ago, and even the widespread adoption we saw in late 2025, early 2026, um, the reason um that that may be like caught on was because maybe this is a new like capability stack where models can now process images better. They needed better verification. Um context windows got bigger and reasoning models improved. Greg, with all of these advancements, why is the way we're using loops today still wrong in your opinion?

</details>

**Greg**: 我的意思是，我认为模型的智能程度已经不那么重要了。我认为归根结底，我同意你关于语义验证的观点，也就是实际闭合反馈循环的能力，或者不管你怎么称呼它，去实际验证智能体的输出是正确的。我认为在某种程度上你是可以做到的。但我不认为你能全局性地做到这一点，至少目前还不行。我认为对于那些可以确定性验证的事情，你可以在某种程度上做到这一点。你可以让系统里有更好的类型推导。你可以有更好的静态代码检查工具（linters）。你可以进行模拟测试等等。你可以开始不断地添加这些东西。只要你保持这些成本很低，我认为就没问题。嗯，一旦你开始在验证过程中加入更多非确定性的因素，我认为这就变得越来越不准确了。它会开始导致更多问题，就像如果你用一件事去提示智能体，它有 5% 的几率会出错。然后你开始循环这个过程。突然之间，在 10 次、20 次循环之后，它就只有 50% 的几率是正确的，或者可能更低。这就是我的意思。而且这样做会花掉你很多钱。我会一直回到所有这一切的经济可行性上。而且为了让它有一点证据基础，我敢肯定大多数大型 AI 公司仍然在使用 Sentry。但为什么呢？他们使用它也是为了捕捉简单的 Bug。那不是安全漏洞。也不是性能倒退等等。以我们现在循环的方式，那些问题仍然存在。而且我们还没能解决那些问题。

<details>
<summary>Original English</summary>

**Greg**: I mean, I don't think that model intelligence matters a lot anymore. I think it boils down to I agree with you the semantic verification, the actual ability to uh close the feedback loop, or however you call it, to actually verify that the outputs of the agent are correct. And you can do it to an extent, I think. I don't think you can do it holistically, at least not at this point. I think you can do it to an extent to things that are deterministically verifiable. Uh you can get better typing in your system. You can get better linters. You can get um simulation testing and all of that. You can start keep adding that. And as long as you keep those cheap, I think that's fine. Um the moment you start adding even more non-determinism as your verification process, I think that becomes less and less correct. It starts contributing more like you know how if you prompt agent with one thing and there is a 5% chance it's going to have an error in it. And then you start looping that. Then suddenly after 10 20 loops, it's going to be 50% chance it's correct or maybe less. And that's what I mean. And it just costed you so much money to do that. I'm going to be keep coming back to the economic viability of all of that. Um And but but to base it a little bit in like evidence, I'm pretty sure that majority of large AI companies are still using Sentry. But why is that? They they are using that just to catch simple bugs as well. It's not security bugs. It's not performance regressions, et cetera. Those problems still exist in the way that we are looping now. And we haven't solved those problems uh yet.

</details>

### Context Rot and the Smart vs. Dumb Zone

**Moderator**: 谢谢。对于 Dex 来说，Raffle 开创了在每次迭代中输入新鲜上下文以避免上下文腐坏（context rot）的想法。现在随着上下文窗口变得大得多，这变得更加可控了。Dex，我们在上下文腐坏和上下文工程方面已经走出困境了吗？

<details>
<summary>Original English</summary>

**Moderator**: Thank you. For Dex, the Raffle pioneered the idea to feed fresh contacts into each iteration to avoid context rot. This has become even more manageable now that context windows have gotten much larger. Decks, are we out of the woods regarding context rot and context engineering?

</details>

**Dex**: 我会回答你的问题，但我们会有像自由发言环节那样的部分吗？因为我还有问题想问 Jeff。

<details>
<summary>Original English</summary>

**Dex**: I'm going to answer your question, but is there going to be like an open floor part cuz I have more questions for Jeff.

</details>

**Moderator**: 我们本来想在这一场采用牛津辩论的形式，为了让它更有条理，然后防止就像……

<details>
<summary>Original English</summary>

**Moderator**: We were trying to do Oxford debate style for this one to keep it like more structured and then prevent like just

</details>

**Dex**: 你不想让它变成一场混乱的闲扯大会（yapfest）。

<details>
<summary>Original English</summary>

**Dex**: You don't want it to just turn into a chaotic yapfest.

</details>

**Moderator**: 对。

<details>
<summary>Original English</summary>

**Moderator**: Yeah.

</details>

**Dex**: 为了防止像我和你那样，我们俩一开口就停不下来了。对。

<details>
<summary>Original English</summary>

**Dex**: to prevent what you and I do where we just start yapping. Yeah.

</details>

**Moderator**: 是啊。现在已经开始了。我，是啊，我这次本来是想管住你们俩的。

<details>
<summary>Original English</summary>

**Moderator**: Yeah. It's already started. I yeah, I was trying to control like both of you guys this time.

</details>

**Dex**: 好的，我会尽可能快地回答这个问题，然后我要开始拿 Jeff 开涮了。

<details>
<summary>Original English</summary>

**Dex**: Okay, I'm going to do this answer as quickly as I possible and then I'm going to start busting Jeff's balls.

</details>

**Moderator**: 没问题，在你的时间里你想说什么都行。你可以随便说，那都没问题。

<details>
<summary>Original English</summary>

**Moderator**: Yeah, you can say whatever you want with your time. You can just yeah, that's that's all good.

</details>

**Dex**: 好的。嗯，是的，当年 Ralph 最酷的地方就在于，好吧，你不断地清空上下文窗口，这完全有效率吗？从 Token 的角度来看可能并非如此，但这意味你可以让一个东西跑上一整夜，它永远不会……就像如果你只是不断地把消息塞进去，你就会导致上下文窗口溢出。但是如果你只是重新启动它，告诉它，这是我期望的世界状态，去检查一下代码，看看我们有什么，然后执行下一步操作来让我们达到那个状态。嗯，这是一种非常干净的方法，可以把你大部分的工作保持在上下文窗口中我们称之为“聪明区（smart zone）”的地方。如果你只是告诉它只做一件事，然后我们就会清空并重新开始。嗯，上下文窗口已经变得更长了……嗯，我想要更新一下。我想我在迈阿密讲过这个，但那个视频还在制作中。

嗯，其实“愚蠢区（dumb zone）”就和任何其他东西一样，它更像是一个辅助轮。就像如果你已经跟 Claude 聊了……每周 70 个小时，持续了两到三个月，你可能就不需要去思考“聪明区”和“愚蠢区”的区别了，因为你已经建立了自己的直觉。它是一个指导原则。如果你刚刚接触 AI，这就是为什么我们教人们这个，这就像……它是一个指导原则。如果你刚刚接触 AI，尽量把它保持在 100,000 个 Token 左右。对于更大的百万级别的上下文窗口，我们可能不会把这个修改、提高到 200,000 个 Token，但在处理最难的问题时，我经常尽量把它控制在 60,000 以下。在处理某些情况时，我经常会超过 300K，在那种情况下，我只是在跟智能体“即兴发挥”，而且我只是太懒了，懒得去压缩它，然后重新开始做个新的。

但这需要你的直觉。比如，你在“愚蠢区”的一个明显的迹象就是，嗯，在某些情况下，模型，你知道，你输入了 200,000 个 Token，然后模型已经完成了一些工作，它试图让测试通过，但是不起作用，然后它就开始做各种奇怪的 Hack。你读了它的思维追踪（thinking traces），它在说“哦，那是个测试，但那是其他地方的测试，我不需要修复它，那是一个先前就存在的问题”，然后你会说“嗯，不，不是这样的”。然后就在那一刻，那种挫败感让你觉得“好吧，它现在是在挣扎着想搞出点什么”。我认为这就是很多人在和这些模型合作了几个月后培养出来的直觉。嗯，但如果你还没有这种直觉，那么你知道，这就是我们的指导原则。

所以，是的，上下文窗口正在变得更好。我认为它们正在变得更大。嗯，因此，类似于 Ralph 那样“在每次迭代中尽可能少做事”的核心循环，它的动机就不那么强了。因为，你知道的，你能注入系统的反馈越多，你能自主完成的事情就越多，而且如果你能让确定性的东西做决定，并且构建一些小提示词（prompts）给智能体，你就不需要自己记住去做了。你不需要告诉它：“嘿，去检查一下 PR 里的评论并把它们修好”，然后等待，接着别人又写了一条评论，你 3 小时后再回来说：“哦，再检查一下评论”。如果你能把那个过程自动化，那就太棒了。而我认为这正是目前有效的循环系统（loops stuff）的核心。嗯……

<details>
<summary>Original English</summary>

**Dex**: Okay. Uh so yeah, the the coolest thing about Ralph back in the day was like, okay, you keep clearing the context window and like is it completely efficient? Like probably not from a token perspective, but it meant you could leave a thing running overnight and it would never like if you just kept stuffing messages in, you would overflow the context window. But if you just relaunch it, say, here's my desired state of the world, go check the code and see what we have and do the one next step to get us there. Uh it was a very clean way to keep most of your work in what we call the smart zone of the context window. If you tell just do one thing and then we're going to clear and restart. Um context windows have gotten longer um and I will like give an update. I think I gave this in Miami, but that that video is still in production.

Um The the dumb zone is really as as much as anything else is is a it's more like training wheels. Like if you have been talking to Claude for 70 70 hours a week and for two to three months, you probably don't need to think about the smart zone versus the dumb zone cuz you've built your intuition. It's a guideline. If you're just getting This is why we teach people this is like it's a guideline if you're just getting started with AI, try to keep it around 100,000 tokens. For larger million context window, we probably don't revise the revise this up to like 200,000 tokens, but I've regularly tried to keep it under 60 for the hardest problems. I've regularly gone over 300k for things where I'm just like kind of like riffing with the agent and I'm just like too lazy to compact it and and and move on and do a new one.

Um but this is your intuition. Like one of the telltale signs that you're in the that you're in the dumb zone is like uh there's certain cases where the model, you know, you're 200,000 tokens in and the model's like finished some work and it's trying to get the test to pass and it's like not working and it's like doing all these weird hacks and you read the thinking traces and it's like oh that's a test, but that's from something else and I don't need to fix that and that's a preexisting thing and you're like well no, it's not. And that that is the moment, that frustration where you're like okay, it's it's flailing trying to make something happen. That's the instinct that you a lot of people I think cultivate after a couple months working with these models. Uh but if you don't have that yet, then you know, then then this is our guideline.

So yeah, context windows are getting better. I think they're getting bigger. Um and so like the core like Ralph loop of like do as little as possible in every single iteration is like less of the motivation here than, you know, the more feedback you can pipe into the system, the more you can do autonomously and if you can have deterministic things making decisions and building small prompts to give to an agent and you don't have to remember to do that. You don't have to tell it, "Hey, go check the PR comments and fix them." and then wait and then someone makes another comment and you come back 3 hours later and say, "Oh, check the comments again." If you can automate that process, that's great. And that's kind of the core of I think what is like loops stuff that works today. Um

</details>

### Pre-commit Hooks and Back Pressure

**Moderator**: 别问 Jeff 那个。我的时间只够说这些了。很抱歉。我必须开始真正地控制进度了。嗯，好的，所以现在我们要进入到剖析什么样才是一个好的循环。好的，让一个循环变得更好的一部分原因是验证。然而，似乎有些矛盾的是，人们在说我们的工作是停止编写提示词，而是开始编写循环，但是带有糟糕提示词的循环会导致智能体作弊，并通过应付测试来达到它的目标，而不是努力去通过测试。Jeff，当模型验证它自己的工作时，你如何防止它作弊？

<details>
<summary>Original English</summary>

**Moderator**: Don't ask Jeff about that. That's all I have time for. I'm sorry. I have to start like really keeping this on schedule. Um okay, so now we're going to get into the anatomy of what makes a good loop a good loop. So okay, part of what makes a loop good is verification. However, it seems contradictory that people are saying our job is to stop writing prompts and start writing loops when the loops with bad prompts result in agents cheating and meeting its goal by by the test instead of working to pass them. Jeff, how do you keep the model from cheating when verifying its own work?

</details>

**Jeff**: 嗯，各位，我大量利用了 Pre-commit Hooks（提交前钩子）。嗯，我通过分析完成的工作，将那种反压（back pressure）设计进去。嗯，我做的另一件事是，嗯，就像 Dex 提到 Ralph 时那样，当时的事情之一是大家都在尝试做压缩（compaction）。想想看，压缩有点像是一个有损函数，就像把一个视频上传到 YouTube，然后下载下来再上传 100 次。就像你在那里丢失了保真度。而且它已经是一个非确定性的系统，本质上是概率性的。因此，Ralph 诞生的背后理论是，就像，“好的，存在一个愚蠢区。而我想做的是确定性地分配它所需要的一切。因为如果它没有被分配，那么本质上它能做的事情的搜索空间是不受约束的。但同时也要留一点余地。”留一点余地。所以，即使有了这些百万级别的上下文窗口，当我超过 100K 时，我也依然会紧张得冒汗。思考这个问题真的很重要。嗯，很多人他们认为你想在公司里使用 LLM。然后他们就像是，“我已经有了……

<details>
<summary>Original English</summary>

**Jeff**: Um I heavily exploit pre-commit hooks, folks. Um and I engineer in that back pressure uh by analyzing the work that is done. Um the other thing I do is um as Dex mentioned that with Ralph, it was one of the things was everyone was trying to do compaction. Think about compaction is kind of like a lossy function, like uploading a a video to YouTube and then downloading and uploading it 100 times. Like you're losing fidelity there. And it's already a non-deterministic system, probabilistic by thing. So, the the theory behind how Ralph came to be is like, "Okay, there is a dumb zone. And what I want to do is deterministically allocate everything it needs. Cuz if it's if it's not allocated, then it's essentially the the search space of what it can do is not constrained. But also leaving a bit of a headroom. Leaving a bit of a headroom. So, I also I get meat sweats when I go above 100k, even with these million context windows. And this is really important to think about. Um a lot of people they think that you want to use LLMs um at a company. And it's like, "I've got...

</details>

<!-- chunk 5/8 -->

### 上下文窗口与大模型的“脾气”

**Speaker A**: 这就像，“太好了。好吧，你必须使用一个循环来批处理这些数据。”关于上下文窗口，你需要考虑的本质上是，记住720K的软盘。你明白我的意思吗？对于大语言模型，你能真正使用的可用内存大约只有那个软盘的八分之一。所以，你真的必须对它进行批处理。你只能分配大概相当于《星球大战》第一部电影剧本的内容；如果你把剧本进行标记化（tokenize），在调用上下文窗口之前，你实际上只能在内存中容纳两个这样的电影剧本。对于一个纯文本的电影剧本来说，那大约是150KB的数据。所以，对此要非常非常小心。

<details>
<summary>Original English</summary>

**Speaker A**: this data." It's like, "Sweet. Okay, you're going to have to use a loop to batch this data." What you need to think about the context windows is uh essentially remember the 720k floppy disk. You know what I mean? You've only got about a eighth of that floppy disk of usable memory that you can actually use for an LLM. So, you actually have to batch it. You can only allocate roughly around about Star Wars if you get Star Wars Episode 1 movie script and you tokenize it, you can actually just hold two of those movie scripts in memory before the context window is called. That's around about 150 kilobytes of data on a text-based movie script. So, be even very careful about this.

</details>

**Speaker A**: 有一件我做过很久而且很蠢的事，就是，我运行一个裸模型，没有任何技能或任何Markdown。实际上，当新模型发布时，我会摆脱我所有的技能和所有的Markdown以及一切东西，因为模型实际上是有品味和偏好的。例如，GPT-55刚出来时，如果你用大写字母对它大声吼叫，它就会变得软弱胆怯。但如果你使用Anthropic的模型，它希望你对它吼叫。各位，去读读模型卡（model cards）吧。就像对于集成者来说，它是存在独特偏好的。所以，让它保持在正轨上实际上就是工程。这真的是工程。

<details>
<summary>Original English</summary>

**Speaker A**: Something I've done it a long time and it's very silly, is uh I run a model bare um without any skills or any markdown. Actually, I get rid of all my skills and all my markdown and everything when the new model is released because the models actually have tastes and preferences. For example, GPT-55 when it first came out, if you screamed at it in uppercase, it became weak and timid. But if you use Anthropic, it wants you to yell at it. Go read the model cards, folks. Like for the integrators, like there is unique tastes for it. So, keeping it on the rails is actually engineering. It's really engineering.

</details>

### 循环与“大杂烩”工程

**Moderator**: 谢谢。大约10天前，Jeff创造了“收敛工程（convergence engineering）”这个词。他说这就是你的循环杂糅在一起的地方。你的循环……这就是你的循环杂烩像一个离散的系统一样在任务下聚集在一起，直到它收敛。Jacks，我们今天使用循环的方式有什么问题？我们如何确保循环杂糅在一起不会只是产生更多的废料（slop）？

<details>
<summary>Original English</summary>

**Moderator**: Thank you. Around 10 days ago, Jeff coined the term convergence engineering. He said it's where your loop slops together. Your loop uh it's where your loop slop uh comes together as a discrete like system under task until it converges. Jacks, what is wrong with how we are using loops today? How do we ensure looping slop together doesn't just produce more slop?

</details>

**Jacks**: 呃，我们得读代码。我实际上要强调一下Jeff在今年早些时候做的一个实验。我想那个叫什么来着？Loom？在那个实验中，我们有Ralph循环试图为未来构建一个软件平台。我想你构建了AWS，你构建了GitHub，然后你意识到，“好吧，我们如何……我们如何让模型对它还不擅长的事情提供反馈？”比如UI测试之类的事情。好吧，你为一个UI是否优秀创建循环的方式是，你给模型提供类似PostHog的东西，然后说，“好的，我们可以部署多个不同的实验。我们可以看看用户使用哪些。”然后，模型不再是看截图和PNG，而是可以看数据，然后发现，“好的，呃，这个表现得更好。那肯定是这个按钮的正确颜色。”这样你就甚至从等式中去除了人类的视觉品味。所有这些听起来都很酷，而关于我们如何确保循环不会把废料带到一起的问题？我……我不认为你能做到。这就是一个典型的“炒作跑在规范前面的例子”，从这个意义上说——Jeff，Loom现在怎么样了？

<details>
<summary>Original English</summary>

**Jacks**: Uh we got to read the code. I will actually highlight uh an experiment that Jeff did earlier this year. Uh I believe what was it called? Loom? Where we had Ralph loops trying to build a software platform for the future. And I think you built you built AWS and you built GitHub and then you realized, "Okay, how do we how do we get the model feedback on things that it's not good at yet?" Like UI testing and things like this. Well, okay, the way you create a loop for is this UI good? Is you give the model something like PostHog, where it's like, "Okay, we can deploy multiple different experiments. We can see which ones the users use." And then rather than looking at screenshots and PNGs, the model can look at data and see, "Okay, uh this one is performing better. That must be the right color for the button." And so now you've even removed like the human visual taste from the equation. And all of this sounded really cool and in the point of like how do we ensure looping doesn't bring slop together? I I don't think you can. And this is like a perfect example of the hype outrunning the discipline in the sense of Jeff, what's what's going on with Loom now?

</details>

**Jeff**: 它还在那儿。它在GitHub上。

<details>
<summary>Original English</summary>

**Jeff**: It's still there. It's on GitHub.

</details>

**Jacks**: 嗯，但是你还在开发它吗？

<details>
<summary>Original English</summary>

**Jacks**: Um but are you still working on it?

</details>

**Jeff**: 呃，已经有6个月没动了，因为我一直在研究验证的工程化方法。

<details>
<summary>Original English</summary>

**Jeff**: Uh it's been 6 months because I've been looking into engineering ways of verification.

</details>

**Jacks**: 对。你跟我说过什么来着？你说过，除非我们有更好的编程语言，或者我们有更好、好得多的模型，否则Loom是行不通的。对我来说，这就是一个教科书般的炒作跑在规范前面的例子。我们对所有这些东西都感到非常兴奋，而且顺便说一句，每个人都应该像Jeff那样做。Loom太棒了。去尝试吧，去推动前沿，因为这是你了解前沿在哪里以及什么可能的方式。否则，你只会在每个新模型上继续使用你的旧技能，并假设它有相同的局限性。但这也是一个关键点，就像，我不知道我试图表达什么。就像，那件事现在还行不通。那个东西现在还行不通。有一天它会行得通的，这有一种必然性，但同样，这是关于今天什么是可行的，以及什么是炒作。所以我不知道这是否完全回答了你的问题，但答案是，避免循环产生废料并制造更多废料的方法是，去阅读从另一端出来的东西，确保它不是废料。

<details>
<summary>Original English</summary>

**Jacks**: Right. What was the thing you said to me? You said Loom's not going to work until we get better programming languages or we get better much better models. And that is a textbook for me of the hype is outrunning the discipline. We're really excited about all this stuff and by the way like everyone should do what Jeff did. Like Loom is awesome. Like go experiment, try to push the frontier cuz that's how you learn where it is and what's possible. Otherwise you just keep using your old skills with every new model and you assume it has the same limitations. But it's also a a a key point of like I don't know what I'm trying to say. Like that this it doesn't work yet. That thing doesn't work yet. It will work someday and like there's inevitability but again it's what works today versus what is hype. So I don't know if that fully answers your question but the answer is like the way to not loop slop together and make more slop is to like read the thing that's coming out the other end and make sure it's not slop.

</details>

**Jeff**: 是的，那说得通。

<details>
<summary>Original English</summary>

**Jeff**: Yeah, that makes sense.

</details>

**Jacks**: 不，这是……实验室都还没能攻克它。那你凭什么认为你能攻克它？

<details>
<summary>Original English</summary>

**Jacks**: No, it's it's it's The labs haven't cracked it. So what makes you think you're going to crack it?

</details>

**Jeff**: 是的。

<details>
<summary>Original English</summary>

**Jeff**: Yes.

</details>

**Jacks**: 对吧？这就是现状，我们都在试图弄清楚如何让这一切发挥作用。

<details>
<summary>Original English</summary>

**Jacks**: Right? And this is right now it's we're all trying to figure out how to make this all work.

</details>

### 循环的成本与投资回报率

**Moderator**: 当然。怀疑论者说，循环会在悄无声息中失败。它们要么花着你的钱无休止地运转，要么智能体在一个半成品任务上过早宣布胜利。高管们已经开始质疑token的支出了。Greg，循环什么时候能回本？这种情况实际上多久发生一次？

<details>
<summary>Original English</summary>

**Moderator**: For sure. Skeptics say that loops fail quietly. They either spiral forever on your dime or the agent declares victory early on a half-finished job. Exacts are already starting to question token spend. Greg, when does a loop pay for itself? And how often is this actually the case?

</details>

**Greg**: 我不认为它们对我们来说是悄无声息地失败的。

<details>
<summary>Original English</summary>

**Greg**: I don't think they fail quietly for us.

</details>

**Moderator**: [笑声]

<details>
<summary>Original English</summary>

**Moderator**: [laughter]

</details>

**Greg**: 我认为它们失败得非常、非常、呃，大声，尤其是当你看你的账单时。呃，但在有些情况下，正如我所说，我做循环，或者我想说我更多地在做工程，在有些情况下我认为做循环是非常有价值的，或者，呃，或者做出一个明确的决定，你要为成本买单，这是非常有价值的。所以，这里的一个具体例子是，我们在本地并在我们的PR（Pull Requests）甚至合并后进行安全扫描，因为它们总是能发现一些真实存在的东西，呃，那些被我们忽略的东西，而且在代码审查方面它们有点击败了人类。而且这很昂贵。为了运行所有我们想要的检查，大概要花我们一个PR五块钱，或者类似的数字。但是，那正是我们做出明确决定，认为这很值得的地方。呃，还有一些情况是，就像，如果你看那些规范非常非常完善的系统，比如，呃，所有用Next.js重写的实验，或者用Rust重写Bun，或者，呃，运行一个浏览器，在这些情况中你围绕这些问题拥有建立多年的测试套件和规范，在那里你可以非常、非常……在这个地方很好地验证，呃，结果，然后我们——然后循环并获得那些，呃，那些结果似乎是行得通的。用Rust编写的Bun似乎运行得相当好，据我所能判断的。呃，所以，绝对有适用的情况，然后还有一些，呃，我认为我经常做的用法情况，你能够想象，例如，构建原型。我经常会做我们应该在，呃，在Sentry做的产品原型。这些将会是用完即弃的，所以我就给它们投入点钱，然后忘掉它们。如果我们喜欢它们，那么我就会……我会去读代码，并且我会感到尴尬，呃，然后我们将回到原点，开始详细说明我们到底是什么意思，并，并试图朝着那个解决方案前进，但这将会更加、更加需要人在循环中参与。呃，所以，所以广泛来说，我认为它们有自己的位置，呃，但正如Dex所说，它们……炒作才是我有意见的地方。炒作跑在了规范的前面，正如他所说。我也非常强烈同意这样一个观点：你应该去尝试事物。你应该自己去试验，试着看看什么对你真正有效，在哪里……在哪里会出现问题，呃，并且你知道，我觉得现在少花点时间在Twitter上是件健康的事。

<details>
<summary>Original English</summary>

**Greg**: I think they fail very, very, um, loudly, especially when you're looking at your bills. Um, but there are cases like, as I said, I do loops, or I do engineering, I would say more so, and there are cases where I think doing loops is very valuable, or doing, um, or making a explicit decision that you're going to pay pay for the cost is very valuable. So, the concrete example here is we do security scanning after on our PRs in local, and after our PRs even land, because they will always find some things that are real, um, that we have overlooked, and they sort of beat humans on the on the code review. And it's expensive. It costs us, I think, like five bucks a PR, or something like that, to run all the checks that we want. But, that's where we made an explicit decision that it's worth it. Um, there are also cases where, like, if you look at the very, very well-specified systems, such as, um, all the experiments with, uh, Next.js rewrite, or a bun rewrite in rust, or, uh, running a browser, cases where you have years and years of test suites and specifications built in around those problems, where you can really, really where well verify, um, the outcomes, then we then looping and getting to those, um, those results seems to work. Bun in rust seems to work pretty well, from all I can tell. Um, so, there are definitely cases, and then there are cases of, um, usage that I think that I do pretty often, where you can imagine, for instance, building prototypes. I do prototypes of products that we should be doing uh doing at Sentry pretty often. Those are going to be throwaways, so I'm going to just slash gold on them, and forget about them. And if we like them, then I'm going I'm going reading the code, and I'm going to be mortified, uh, and we're going to go to the square one and start specking out what we actually meant, and and sort of go towards that solution, but it's going to be much much more involving of of human in a loop. Um so so broadly, I think they have place, uh but as Dex said, they the hype is what I have a problem with. The hype is outrunning the discipline, as he said. And I also agree very strongly with the point that you should just try things. You should just experiment yourself, try to see what actually works for you, where where the the cookie crumbles, um and you know, spend less time on Twitter, I think, is healthy nowadays.

</details>

### 多智能体协作与访问控制

**Moderator**: 是的，说得好。一个有良好成本意识的循环必须追踪状态，以了解它已经尝试了什么。那种记忆存在于磁盘的某个地方，并且越来越趋向于存在一个多智能体读写的共享内存存储中，尤其是当你从单人智能体模式转向多人智能体模式时。你最终会遇到这样的访问控制问题：无法区分哪个智能体写了哪个记忆，以及谁可以读取它。这对于概念验证（POC）来说可能没问题，但绝对不适合生产环境。矛盾就在这里。共享内存是循环用来互相学习和更快收敛的基础，但是为了解决访问控制问题而将其按智能体进行隔离，会孤立它们，并进而扼杀那种共享学习。Ian，我们如何解决共享内存存储的访问控制问题，以便循环能够更快地收敛？

<details>
<summary>Original English</summary>

**Moderator**: Yeah, good points. A good cost-conscious loop has to track state to know what it's already tried. That memory lives somewhere on disk and get increasingly in a shared memory store that many agents read and write, especially as you go single-player to multiplayer with agents. You end up with this access control problem that can't tell which agent wrote which memory and who can read it. That might be fine for a POC, but it's definitely not for production. The tension lies in this. Shared memory is what loops use to learn from each other and converge faster, but scoping it per agent to solve the access control problem isolates them and then kills that shared learning. Ian, how do we solve the shared memory store access control problem so loops can converge faster?

</details>

**Ian**: 问得好。哇哦。哇哦。

<details>
<summary>Original English</summary>

**Ian**: Great question. Wow. Wow.

</details>

**Speaker B**: 只有当有人正在开发一款能帮上忙的产品时（才能解决）。

<details>
<summary>Original English</summary>

**Speaker B**: Only if someone was working on a product that could help.

</details>

**Ian**: 只有当有人在考虑这个问题的时候（才能解决）。我的意思是，实际上，我已经……首先且最重要的是，这是一个未解决的问题。比如，让我们非常诚实地面对这一点：我们的我们的访问控制系统并不是为这个世界设计的，在这个世界中，机器在代表，呃，代表我们采取行动和进行推理。但大体上讲，我认为就像一些……

<details>
<summary>Original English</summary>

**Ian**: Only if someone was thinking about it. I mean, actually, I've This is This is an unsolved problem, first and foremost. Like, let's be really honest that our our access control systems weren't designed for this this world, where machines were acting and reasoning on on behalf of uh on behalf of us. But broadly speaking, I think like some of the

</details>

<!-- chunk 6/8 -->

### 未来的循环与软件工厂

**Speaker A**: 基础设施的雏形正在开始显现，如果我们暂时忽略 Cloud IAM 和所有其他的东西，比如 Markdown 就非常棒。因此实际上，如果我们在讨论中将记忆定义为 Markdown 格式，那么真正的问题在于，我该共享哪些内容、如何共享这些 Markdown 文件并将其用作记忆，然后又该如何围绕这些东西分配访问控制。如果我们采用这种模式，我其实认为我们今天已经具备了实现大部分功能的基础。只是在概念上还有些难以驾驭。一个很好的例子就是我最近发的这条推文。我当时在折腾 Notion，我们在 GitHub 经常使用 Notion。但我真的只是希望我所有的 Notion 内容都能变成 Markdown 文件。因为与其通过 MCP 去操作，如果能作为 Markdown 文件，智能体处理起来会容易得多，而我有点像是一个命令行界面的死忠粉，所以就研究了一下。所以我认为我们真正缺少的，你知道上次 Dex 和我也就 MCP 讨论过这个问题，但我们真正的挑战在于：我该如何向智能体展示一个世界，好让我自己也能理解它，然后我该如何分配它在任何特定时间点的访问权限，以及如何让任何人都能轻松驾驭它。我不认为我们已经真正解决了这个问题，但当然，一些非常合理的模式已经初见端倪。

<details>
<summary>Original English</summary>

**Speaker A**: beginnings of the substrate are starting to emerge, and if we ignore Cloud IAM and all the other stuff for a hot second, like markdown is pretty great. And so really, if we were to say a memory is markdown for the purpose of the conversation, the really question is like what things and how do I share these markdown files and use that as a memory and then how do I attribute sort of like access control around those things. And if we were to use that model, I actually think we have like the basis for for most of it today. It's just unwieldy to think about. Um a good example would be I did this tweet recently. Um I was playing with Notion and we use Notion a lot at GitHub. Uh but I really just wanted all my Notion things to be able to be as markdown files. And because it would just made it easier for the agent to work with it instead of going through MCP and I was a bit of a CLI maxi and was looking through that. So I think what we're missing really is uh and MZ it you know Dex and I debated this last time about MCP but like we're really the challenge really is how do I present a world to an agent so that I can understand it and then how do I attribute what can access at any one point in time and how to make that wieldy for anyone to do it. And I don't I don't think we've actually cracked it but certainly there's some beginnings of patterns that make a lot of sense.

</details>

**Host**: 好的，既然我们讨论了循环的剖析，接下来我们要辩论一下循环的未来。比如说，我们现在是否基本上已经为“软件工厂”做好了准备？循环工程（loop engineering）是否已经变得如此出色，以至于我们已经准备好迎接成熟的软件工厂了？我们要从这个问题开始：如果循环只擅长于可验证的任务，这意味着完全自主的软件工厂必须能够验证它们所做的一切。Greg，这现实吗？优秀的工程工作中其他的部分呢，比如决定构建什么，抽象是否合理，以及什么权衡是可以接受的？

<details>
<summary>Original English</summary>

**Host**: All right, now that we discussed the anatomy of the loop, we're going to debate the future of the loop. Like are we essentially well positioned now for software factories? Has loop engineering gotten so good that like we're ready for the full software factory? And we'll start with if loops are only good for verifiable tasks, that means fully autonomous software factories must be able to verify everything they do. Greg, is this realistic? What other parts of good engineering work such as deciding what to build, whether the abstraction is right, and what tradeoffs are acceptable?

</details>

**Greg**: 呃，这现实吗？我认为如果计算是免费的，那将是一个非常不错的开始，但是，嗯，（笑声），嗯，我认为我们正在达到这样一个地步，或者让我这样说吧。你在循环中作为人类所做的决定，是关于设计、架构这类重要的决定，我不会说我会放心让智能体替我去做这些。而且我不认为这种情况会在短期内成为现实。我认为原因是，当你审视大型组织时——我想任何有多年经验的工程师都会告诉你——问题并不总是关于你应该构建什么，同样也关于你不应该构建什么。什么是真正正确的权衡，你想要在哪些地方投入复杂性，又应该在哪些地方追求极致的简单。在我的经验中，智能体喜欢复杂性。它们会无限制地不断往技术栈里添加东西。所以，我认为我们在转移目标。随着我们加入更多的验证、更多的语义核实，我们正达到这样一个阶段，它们能够做的事情要多得多得多。我并没有忽视这一点。但我确实想在实际的架构决策中留在循环里，而且我看不到它们会在短期内接管这项工作。

<details>
<summary>Original English</summary>

**Greg**: Uh is this realistic? I think if if the compute is free, that would be pretty pretty good beginning but um
[laughter]
uh I think I think we're getting to the point where um or let me put it this way. The decisions that you are making as a human in in the loop are the decisions of like design, architecture, the the the important ones that um that I would say I wouldn't trust the the agent to do for me. Uh and I don't see the future where that becomes reality yet. I think the reason for that is when you're when you're looking at large organizations and I think any engineer who has had like years of experience will tell you it's not always about what you should be what you should build, but also about what you shouldn't build. What are the actual right trade-offs, where the complexity is that you want to um that you want to invest in versus where you should be um investing in maximal simplicity. Um in my experience, agents love complexity. They will keep adding to the stack um unbounded. And so, I think we are we are shifting the the the post. We are getting to the point where as we are adding more validation, more uh semantic verification, they are able to do much much more. Um and I'm not uh not neglecting that. But I do want to be in the loop for the actual architectural decisions, and I do not see them uh taking that over any anytime soon.

</details>

**Host**: 谢谢。Crossover 的工程副总裁 Shubha 在 Compile 会议上告诉大家，你的工作就是编写循环。Steinberger 发推说：“这是每月的例行提醒，你不应该再去给编程智能体写提示词（prompt）了。你应该设计那些能提示你的智能体的循环。”那条推文的浏览量达到了 800 万次。Jeff，你在最初的博客文章中说过，“循环需要资深的专业知识，有时它最高只能做到 90% 的程度。”那么，“只需编写循环”这个建议，把它给 3000 人或者 800 万人安全吗？还是只适合那些一开始就已经真正学会如何调优循环的人？

<details>
<summary>Original English</summary>

**Host**: Thank you. Shubha Vice Head of Engineering told everyone at Crossover's Compile Conference that your job is just to write loops. Steinberger tweeted, "Here's your monthly reminder that you shouldn't be prompting coding agents anymore. You should be designing loops that prompt your agents." The view count on that tweet was 8 million people. Jeff, you've said in your original blog post, "Loops need senior expertise and it sometimes it tops out at 90% of the way there." So, is just write the loops advice, is that safe to give to 3,000 people or 8 million people? Or only the people that have really learned to tune a loop in the first place?

</details>

**Jeff**: 是的，这是一件有趣的事情。嗯，要向这么广泛的受众量身定制并教授他们应该做什么和不该做什么真的很难。所以，我能做的只有在最初写作时，面向我的同侪去写。我有一些敬仰的人。出于某种原因，我脑海中闪过一个念头，认为一切都改变了。游戏规则已经改变了，但我真的很担心函数式编程领域一些最优秀的人，比如真正的同行。我记得像是 Fly IO 的 Thomas Petek，让他脑海中突然灵光一闪。他写了一篇博客文章表达了类似的观点。所以，我开始为我的同侪和那些我敬仰的人写作。要把它传播给全世界，这很难。但在同样的意义上，你去看看 YouTube。你会看到有些从未创造过任何东西的人现在正在创造东西。他们睡一觉醒来，就拥有了一个全新的 Discord 机器人。这简直就是魔法。我希望人们记住，这实际上是一个编排模式（orchestration pattern）。它被简化成了一个使用 `cat` 的 `while true` 循环，因为 `cat` 是最简单的教学原语。如果你想教点东西，你必须让它变得非常简单。让它变得非常简单。所以，使用 `cat` 提示词，你设计提示词将会是什么样。你使用文件系统作为状态。你回收上下文窗口。运行循环。这可能有点取巧，但它的性价比很高。它就是能管用。但是，整个尝试的意义在于，在上面应该有某种类似于 PID 控制器的东西，或者某种工厂，或者某种决策器之类的，来决定一个循环是否应该继续。这真的很难。它是安全的还是不安全的？“安全”是一个有趣的词。没有人应该在你的本地笔记本电脑上使用编程工具。这并不是因为人工智能，而是因为 NPM 供应链攻击。这一直是事实。我尝试破解这个问题已经有 7 年了。就像现在人们又开始关注说，AI 运行不安全的命令可能会不安全，但实际上，大家在日常工作场所的软件开发实践已经是不安全的了，伙计们。所以，先把这个修好，然后这些技术才会开始变得安全。

<details>
<summary>Original English</summary>

**Jeff**: Yeah, this is an interesting thing. Um it's really hard to tailor and teach like like what you should do and what you should not do to a broad that broad of an audience. So, all I can do is write to when I was originally writing, I was writing to my peers. I had people I looked up to. For some reason, I had it clicked in my head that everything has changed. The game has changed, but I was really concerned that some of the some of the best people in functional programming and like and like real peers. I remember like um Fly IO, Thomas Petek. He he he that made him click in his head. He's got a blog post saying as such. So, I started writing for my peers and the people I looked up on. To disseminate down to like the the entire world, it's hard. Um but in the same the same sense, you go to YouTube. You got people who are creating things who've never created things before. They go to sleep and they wake up and they got a brand new Discord bot. It's magic. I want people to remember that it is actually a pattern for allocating basically it was a pattern as an orchestration pattern. It was condensed down to a while true loop using cat cuz cat is the simplest teaching primitive. To that If you want to teach something, you got to make it really simple. Make it really simple. So, cat prompt I you engineer the prompt what it's going to be. You use the file system as state. You recycle the context window. Run the loop. It's a little bit maybe, but it got it was just bang for buck. It just works. But, the entire attempt there is that there should be some sort of like PID controller on top or some sort of factory or some sort of some sort of some sort of determinator as such saying whether a loop should continue or not. Um it's really hard. Um is it safe or unsafe? Safe is an interesting word. Um no one should be using coding tools on your local laptop. And this is not because of AI, but this is because of NPM supply chain attacks. This has been true. I tried to try cracking this problem for 7 years. Um and like it's now on the attention again that we that like AI could be unsafe running unsafe commands, but like your software development practices day-to-day at workplace are already unsafe, folks. So, um fix that. Then these techniques start to become safe.

</details>

**Host**: 谢谢。Dax，你在推特上说，大多数工程师看到编程智能体带来了两到三倍的提速，这是现实的。如果你试图追求 100 倍的提速，你就会迷失在优化的元元问题（meta meta problem）中。而且你可能永远也达不到那种只要保持务实就有可能实现的、能改变生活的 10 倍提速。如果两到三倍已经是可能的极限，我们又该如何达到一个完全自主的软件工厂呢？

<details>
<summary>Original English</summary>

**Host**: Thank you. Dax, you tweeted that most engineers are seeing a two to three x speed up from coding agents and that's realistic. And if you try for that 100 x speed up, you're going to get lost in the meta meta problem of optimization. And you may never get to that life-changing 10 x speed up that is possible by staying pragmatic. If only two to three x is what's possible, how do we ever get to a fully autonomous software factory?

</details>

**Dax**: 是的，我认为这是一个好问题。我觉得这里面也存在一种混合的情况，对吧？我们在讨论什么是有效的，什么是炒作。我认为非常值得强调的是，你应该去尝试。你应该去努力推动边界，做那些今天可能还行不通的事情，但你不能仅仅因为在推特上看到了某个能用的东西，就假设你所有的工作方式都被改变了。我的意思是，不要抛弃我们所学过的一切。不要刻意去抛弃我们作为一个社区，经过几十年的软件工程职业生涯积累和建立起来的东西。这又回到了我所认为的，人们在着手设计和创建他们的软件工厂时，最严重的反模式。那就是他们说，“好吧，太棒了。我要闭关 3 个月，我已经读了一堆博客文章，我要去建造我的软件工厂了。”然后那将会是终极的软件工厂，它将成为我们未来发布所有东西的方式。然后 3 个月后你回来了，却发现你根本没有触及真正的问题。你从未把它交到任何人手里。这就跟任何产品一样。你在构建一个软件工厂，你就是在为你的队友构建一个产品，你是在为 5 个、10 个、500 个、5000 个工程师构建一个产品。而正确的方法是从小处着手，不断迭代，弄清楚什么才是有效的。去尝试一下。

<details>
<summary>Original English</summary>

**Dax**: Yeah, and I think this is it's it's a good question. I think there's like there's there's a mix here, too, right? We're talking about what works versus what is hype. And I think it is definitely worth I want to highlight like you should try again. Like you should try to push the frontier and do the things that might not work today, but you should not assume that all your work is changed just because you saw something work on Twitter, basically. Is like don't throw away all the things we've learned. Don't go out of your way to cast aside this, you know, decades-long career of software engineering that we as a we as a community have built up and put together. Um and it it gets back to like what I see as the biggest anti-pattern for how people set about designing and creating their software factory, which is they say, "Okay, cool. I'm going to go away for 3 months and I've read a bunch of blog posts and I'm going to go make my software factory." And it's going to be the software factory. It's going to be the future of how we ship everything. Uh and then you come back 3 months later and you never touched the problem. You never put it in anybody's hands. It's just like any product. You're building a software factory, you're building a product for your teammates, you're building a product for 5, 10, 500, 5,000 engineers. Uh and the the right approach is to start small and iterate and figure out what works. Try

</details>

<!-- chunk 7/8 -->

### 构建 AI 直觉与循序渐进 (Building AI Intuition and Iteration)

**Speaker A**: 这些东西，它们可能行不通，也可能行得通，但我们学习 AI 以及如何有效使用它的方式，是通过建立直觉，这就是为什么你应该去尝试很多可能行不通的东西，但你需要认识到这一点。你不应该试图强行突破那个前沿界限。所以我的建议是，与其试图将一切都端到端地自动化，不如在你的整个系统中构建这些小型的、渐进的循环，有一天你醒来时，你会发现你的速度提高了两到三倍，同时仍然能够阅读代码，仍然能够掌控架构。因此，你没必要为了达到这个状态，就抛弃我们学过的一切、知道的一切以及你所有的直觉。所以我想要提醒大家，去弄清楚如何让速度提升两倍或三倍，因为如果你试图让速度提升一百倍，你很可能会把一切都搞砸。嗯，而且，我的意思是，你能想象吗，如果世界上每一个软件工程师的速度都提高两到三倍，并且拥有接近人类 99% 的水平——人类水平的质量，那将会改变世界上的每一家企业，每一家初创公司。它将改变整个数学演算。而我们正在试图达到那个目标……只是别走得太远。去追求你力所能及的事情。循序渐进地构建事物。你会学到很多东西，并且你会为下一代模型的问世做好准备，到那时你就能以五倍、十倍的速度前进。

<details>
<summary>Original English</summary>

**Speaker A**: things, they might not work, they might work, but the way we learn AI and how to use it effectively is through building up intuition, which is why you should try a bunch of stuff that probably won't work, but you should acknowledge that. You should not try to push like through that through that frontier. Um and so my advice is kind of like instead of trying to automate everything end-to-end, build these small incremental loops throughout your system and you will wake up one day and you will be moving two to three times faster while still being able to read the code, while still owning the architecture. And so you don't have to throw away everything we've learned and everything we know and all your intuitions just to get to this place. And so I would I would caution people like go figure out how to make move 2x faster or 3x faster because you're going to like blow everything up by trying to go 100x faster. Um and uh yeah, I mean, if can you imagine if every software engineer in the world was two to three x faster and had a like near human 99% level human level of quality, that would change every single enterprise in the world, every single startup in the world. It would change the entire math. And we're trying to like go to Just don't don't go too far. Shoot Shoot for what you can do. Build things up iteratively. You'll learn a lot and you'll be ready for when the next models come out and you can go 5x, 10x faster.

</details>

### AI 代理的代码验证与责任归属 (Code Verification and Liability for AI Agents)

**Moderator**: 谢谢。当谈到验证时，它不仅仅是关于验证工作本身，也是关于验证是谁完成了这项工作。雇主们已经明确表示，人类要对他们交付的代码负责，无论是不是 AI 代理编写的。然而，在今天，只有一个人或一个代理可以在代码提交上签名。Ian，如果无法确定是谁完成了工作，以及工作是代表谁完成的，我们是否准备好让软件工厂来编写和审查所有代码了呢？

<details>
<summary>Original English</summary>

**Moderator**: >> Thank you. When it comes to verification, it's not just about verifying the work, it's also about verifying who did the work. Employers have made it clear that humans are responsible for the code they ship whether an agent wrote it or not. Yet only one person or agent can sign a commit today. Ian, are we ready for software factories to be writing and reviewing all code if we can't determine who did the work and who the work was done on behalf of?

</details>

**Ian**: 我想，是的，其实大概两周前我刚好在研究这个问题。首先最重要的是，我们面临一个问题。Git 目前只允许在一次提交上有一个签名者，所以我们必须解决这个问题。其次就是，你知道，这涉及到 SOC 2 审计和合规性等方面的问题，对吧？但是，我认为更重要的是，思考 AI 代理的方式，其实就像我们在大型组织中思考服务所有权一样。也就是在某个时刻，必须由一个人类来为代理的行为负责。不存在这样一个世界，即代理是它自己的实体，拥有自己可归属的责任，并以某种方式承担法律责任。唯一能承担法律责任的，是能够承担后果的人，对吧？而这始终必须建立在人类的基础上。所以，如果一个人类设计了一个循环（loop），而那个循环产出了糟糕的软件，你猜谁应该为此承担责任？必然是人类，对吧？如果没有责任追究，社会就无法运转。那根本行不通。造成了破坏就必须有后果，做出了糟糕的决定就必须有后果，而这些后果显然会根据造成的破坏程度而有所区别。如果我们没有这些机制，一切都将无法运转。所以，我实际上想宽泛地说，不存在一个人类永远不需要负责的世界。总会有这样一种情况，人类需要承担一定程度的责任。而问题在于，不论是一个人还是一个公司（由一群人组成），问题在于这将如何改变我们今天的系统运作方式？所以，在今天使用 Git 时，我可以签署一个提交，表明是我做的，它归属于我的公钥，对于我们上一代人思考软件的方式来说，这很棒。而在未来，当我让一个代理代表我去执行某项任务时，它生成了一个循环，编写了一堆代码，并将其推向生产环境。我必须为我签署那个东西这一最初事实，也就是去执行那件事的意图，承担责任。而我们目前根本没有具备做到这一点所需的底层基础设施，尽管我确实认为这会很快发生改变。这并不是什么我们难以攻克的疯狂难题，但我们必须重新思考我们在整个供应链和软件开发生命周期（SDLC）中关于责任归属的认知。这并不是一个新问题，对吧？就像供应链安全一直以来都是个问题。实际上，这正是我们在代理方面面临的最大挑战之一，我们也一直希望能够在整个供应链中拥有更具确定性的路径和签名链，所以这只是关于你如何针对第一方代码与第三方代码分别实现这一点的问题。

<details>
<summary>Original English</summary>

**Ian**: >> I think Yeah, actually I was I was playing around with this problem like two weeks ago. So, um first and foremost, we have a problem. Git only allows one signer on a commit, so we got to fix that. Um two is you know, there's some things around SOC 2 and compliance, right? But, I think like more importantly, the way to think about agents is is kind of how we think about service ownership in large organization. It's like at some point, a human has to be attributable for an agent's actions. Like, there's no world where it's going to be like an agent is its own entity and its own attributable thing and somehow has liability. Like, the only people who have liability are people that can have consequences, right? And that always has to be grounded in it being a human. And so, if a human designs a loop and that loop presents bad software, guess who's attributable for that liability? It's going to be the human, right? Like, the society doesn't function if we don't have liability. Uh it just doesn't work. There has be consequences to damage, there's be consequences to bad decisions, and what those consequences are are obviously a gradient based on the on on the damage that's done. And if we don't have that, nothing works. And so, I'd actually broadly say there is no world where a human is never responsible. There's always a world where a human has a level of responsibility. And the question is whether it's a human or corporation, which is a group of humans, um the question is is how does that change the way that our systems work today? So, today with Git, I can sign a commit that says I did it and it attributes to my public key, and that's cool for last generation's way that we thought about software. Now, in the future, when I tell an agent to go do something on my behalf, it generates a loop, it generates a bunch of code, it goes to production. I have to be attributable to the initial fact that I signed that thing, the that intention to do that. And we we simply do not have the substrate required um to do it, although I do think that's going to change pretty quickly. Um this isn't like something that's like crazy difficult for us to break, but we have to rethink the way that we think about attribution across the supply chain and the SDLC. And this is not a new problem, right? Like supply chain security has always been an issue. It's actually the biggest challenge one of the biggest challenges we have with agents, and we've always wanted to have more deterministic uh pathway and sign signature chains across the supply chain, and this is just how do you do that for first-party code versus uh third-party code?

</details>

**Greg**: 好吧，Ian，直言不讳地说，我们的职业多少有点像个笑话。在个人层面上，我们其实并没有责任追究机制。虽然我们称自己为工程师，但我们并非真正的工程师。各位，有些事情会变得非常复杂，也许我们需要重新审视这些话题。

<details>
<summary>Original English</summary>

**Greg**: >> Well, Ian, um, to to just to shoot straight, um, our profession is a bit of a clown show. We actually don't have liability at a personal level. Like we call ourselves engineers, we're not really engineers. Some of this stuff is going to get really complicated, folks, and maybe we need to revisit these topics.

</details>

### 总结陈词：理性看待炒作与保持实践 (Final Thoughts: Navigating the Hype and Staying Practical)

**Moderator**: 既然我们的主要辩论环节已经结束，为了做个总结，每个团队的每位成员将有 2 分钟的时间来做总结，并陈述他们的最终想法，然后我们将决定谁是获胜者。呃，Greg，你想不想……

<details>
<summary>Original English</summary>

**Moderator**: >> And now that we've had our main debate section, to wrap it up, each member on each team will get 2 minutes to uh wrap it up and describe their final thoughts before we decide who the winner was. Uh, Greg, what would you like to 

</details>

**Greg**: 是的，没问题。有趣的是，我们竟然在那么多观点上达成了一致，不过事情就是这样。我确实认为，我一直试图在这里强调的最大的一点是，我们现在所处的位置，以及我们是否正朝着我们想要到达的位置前进，然后再对比一下你从无处不在的炒作循环中实际听到的内容。这正是我想要着重强调并为其降温的地方。我基本上想说的是：去尝试事物。独立思考。不要盲目跟风陷入泡沫。不要跟风炒作，因为你会通过亲自实践找到最适合你的方法，并发现系统在哪里最容易崩溃。人类学习的最好方式一直都是通过实践，而不是，你知道的，看 YouTube 视频。最终，这就是我正在尝试做的事情，而当涉及到允许完整循环自主运行时，我略微持怀疑态度，因为我看到那些定性结果并不能满足我的要求。但是，我总体上是乐观的。我感到乐观，是因为我已经看到了自己能多做多少事情，以及我现在能够解决哪些问题，而这些问题甚至在一年前我还无法解决，更不用说在那之前了。情况还会变得更好，但我也并不担心我的软件工程职业生涯。我不认为我们会被淘汰。我认为我们仍然会是这个整个软件工厂，或者任何下一个将要形成的所谓“炒作泡沫”中的重要组成部分。

<details>
<summary>Original English</summary>

**Greg**: >> Yeah, absolutely. Um, it's it's interesting seeing how many how many points we actually agree with each other, uh, but that's how how this goes. I I do think that the biggest point that I'm trying to I have been trying to drive here is um where we are whether we are where we are trying to be and then what you're actually hearing from the ever-present hype uh hype loop. And that's where I want to sort of double down and tone this down. I basically want to say try things. Think for yourself. Don't lean into the bubble. Uh, don't lean into the hype because you will find what works for you and you will find where the system breaks the best by doing it yourself. That's always has been how um how humans learn the best is by practice, not by, you know, watching YouTube. Um, and ultimately, that's that's what I'm trying to do, and I'm slightly skeptical uh when it comes to, you know, allowing the full loop to run because I see the qualitative results not being up to snuff for my my requirements. But, I am optimistic in general. I am optimistic because I've seen how much more I can do and what are the types of problems I can address today that I couldn't address even a year ago, let alone let alone earlier than that. And and it's going to get better, but I'm also not worried about my software engineering career. I don't think we're going away. I think we are still going to be important piece of this whole software factory or whatever the next um sort of hype bubble is going to become.

</details>

**Moderator**: Ian，接下来你想发言吗？

<details>
<summary>Original English</summary>

**Moderator**: >> Ian, would you like to go next?

</details>

**Ian**: 我很乐意。所以，火车已经驶出站台了。这些东西确实管用，并且的确带来了真实的生产力提升，对吧？也就是说，有更多的工作被完成了。这并不意味着所有完成的工作都是好的，但确实完成了更多的事情，而且其中很大一部分工作实际上是很不错的，对吧？我想我们在这一点上是可以达成共识的。其次，我们现在面临着竞争压力，对于一家公司来说，已经不再可能袖手旁观地说：“嘿，我们要置身事外，不参与这些循环自动化的东西，对吧？我们要置身事外，不碰这些编程代理相关的东西。” 那个时代已经过去了。我们已经跨过了那个阶段。就像，那列火车已经驶离了站台。一旦那列火车驶离站台，世界上的每个人都会开始说：“天哪，我必须把我的东西整合好。我们要跟上别人的步伐。” 而且他们别无选择，因为我们生活在一个竞争非常激烈的资本主义社会，这也算是，你知道的，避开政治因素不谈，但这就是我们的现实。而归根结底，问题其实不在于它会不会发生，而在于它何时发生，以及随着时间的推移会达到何种程度。而且我不认为除了紧跟时代步伐之外还有别的选择，我们都只是仿佛抓着一艘正在飞驰的火箭，我们其实并不知道那……我们并不真正了解它的飞行轨迹，只知道它感觉非常快，有着疯狂的加速度，而且有时我们似乎遥遥领先于彼此，有时又远远落后，但我不认为你可以选择置身事外，你必须去做的第一点是弄清楚循环是什么，第二点是弄清楚你可以在代码库的哪些地方应用它们。总会有一些地方你会觉得：“嘿，这是……”

<details>
<summary>Original English</summary>

**Ian**: >> I would love to. So, the train's left the station. This stuff works, um and there is a real productivity increment, right? Like, more stuff is getting done. It doesn't mean all the stuff getting done is good, but more stuff is getting done and a good percentage of that stuff is actually good, right? I think we can agree that. And second is now we have competitive dynamics, where it's no longer possible for a company to sit back like, "Hey, we're going to sit this loop stuff out, right? I'm going to sit this coding agent stuff out." Like, that that's over. We're we're past that. Like, that train leaves the station. As soon as that train leaves the station, everybody in the world starts saying, "Holy I got to keep my stuff together. We're going to stay up with the Joneses." And they have to because we live in a very competitive capitalist society, and that's also, you know, ducking politics, but it's it is what we are. And at the end of the day, the question is is not really um will it happen, it's when it happens and to what degree over time. And I don't think there's a choice but to actually stay up-to-date, and we're all just kind of holding on to a rocket ship ride, where we don't actually know what that We don't really know the trajectory other than it feels real fast with crazy acceleration, and sometimes like we're way ahead of each other, and sometimes we're way behind, but I don't think you have a choice not to be one, figuring out what loops are, two, figuring out where you can apply them in your code base. There's going to be places where, "Hey, this is "

</details>

<!-- chunk 8/8 -->

### Software Factories and Loops

**Speaker A**: 高度可验证的。这是一个像计算机一样能够解决的问题。这说不大通。[咳嗽] 连接器就是一个很好的切入点，比如过去 10 年里。很多公司通过仅仅做“连接器农场”来赚钱，但现在那里已经没有多少价值了，对吧？如果你能自动化连接器创建的过程。所以，在软件领域，有些地方你今天就可以应用循环（loops）并获得真正的价值，但有些地方你可能不应该这样做，你需要决定哪些地方适用，这可能就是你正在创造的核心价值，对吧？这就是我的看法。从广义上讲，趋势已经不可阻挡了。生产力曲线是驱动社会的动力。投资回报率（ROI），也就是作为一个社会我们能变得多高产，才是推动 GDP 增长的因素。而最终推动 GDP 增长的，是资金的流向以及资本是如何分配的。

<details>
<summary>Original English</summary>

**Speaker A**: highly verifiable. This is a problem that like computers can solve. It doesn't make a lot of sense. [Cough] connectors is a good place of like, you know, last 10 years. The amount of companies that have made money because they're basically just connector farms, there's no longer a lot of value there, right? If you can automate the connection connector creation. So, there's places in software that you can apply loops today and get real value and there's places where you probably shouldn't and you should decide where that is and it's probably the core value of what you're creating, right? And so, that's how I think about it. Broadly speaking, trends left the station. The productivity curve is what drives society. The ROI, so how much more productive we are as a society is what drives GDP. What drives GDP is ultimately where the dollars go um and how capital gets allocated.

</details>

**Speaker B**: 好的，接下来交给你。

<details>
<summary>Original English</summary>

**Speaker B**: Okay, get over to you next.

</details>

**Speaker C**: 我热切地期盼着“软件工厂”变得可行的那一天。我非常想要一个我们不再需要阅读代码的世界，在那个世界里我们可以直接完成所有事情。如果你看了我周二的演讲，我认为这实际上是我们目前只能在模型层面解决的问题。遗憾的是，我不认为外围的脚手架（harness）能做到这一点，因为我非常喜欢构建脚手架和做上下文工程。所以，我的建议是关注一下 Jeff。当 Loom 真正起作用的时候请告诉我，在此之前，就使用循环吧，但不要像那样用。

<details>
<summary>Original English</summary>

**Speaker C**: I eagerly await the world where the life soft software factory is feasible. The I I would love a world where we don't have to read the code, where where we can just do everything. Um if you watch my talk on Tuesday, I I think this is actually a problem we can only solve at the model level right now. I don't think the harness can do it uh unfortunately cuz I love building harnesses and doing context engineering. Um so, my advice is uh pay attention to Jeff. Uh let me know when Loom is actually working and until then uh use loops, but not like that.

</details>

**Speaker D**: [笑声]

<details>
<summary>Original English</summary>

**Speaker D**: [laughter]

</details>

**Speaker E**: 太棒了。伙计们，有太多话要说了。工厂代表了我们走向未来的方向。它本质上就像一台永动机，对吧？它就像是一个白日梦。现在有些公司才刚刚成立，才刚刚获得融资。不要以为你现在就能直接把这套东西拿去在你的公司里实施，因为在市场上这普遍还没有被解决。但是，为了补充这些元讨论，我想说的是，如果你试图在循环中运行，或者尝试使用 Python 来构建一个工厂，那将会是一场小丑秀。

<details>
<summary>Original English</summary>

**Speaker E**: Love it. So, so much to say, folks. Um factories represents where we're heading to the future. Like it it's it's essentially like a perpetual energy motion machine, right? It's it's like it's the pipe dream. Companies are only just getting founded today and getting receiving their rounds today. Don't think you can just take this and implement it in your company cuz it's just generally not solved in market. But, I will say to add to the meta monologue, if you try to run in loops or try to build a factory to using Python, it's going to be a clown show.

</details>

**Speaker F**: [笑声]

<details>
<summary>Original English</summary>

**Speaker F**: [laughter]

</details>

**Speaker E**: 如果你用 Ruby 来做，那也会是一场小丑秀。伙计们，静态类型也是一种验证形式。我鼓励你们想出一些代码套路（katas）并做一些实验。尝试运行一些循环。用 Ruby 构建一个应用程序，然后再尝试用这些循环去修改它，你就会看到可维护性是多么的一团糟。然后尝试用 Haskell 来做。我不在乎你懂不懂 Haskell。你不懂 Haskell 也没关系。大语言模型（LLM）懂 Haskell，而且你实际上可以提示智能体，让它像给你的儿子或女儿解释那样把它解释给你听。所以，我不确定现在代码是否还需要具备可读性，但这就是非常前沿的思考方式了。代码需要是可解释的。所以，我在这里尝试验证的不同领域，但有一件事是肯定的，类型系统现在很流行。非常流行。Rust 非常好，因为它的生态系统对一些类型的建模方式。另外，因为刚才提到了供应链，我必须说，现在已经 10 个月了。我已经尽量少地使用任何开源软件。降到最低限度。我只是根据我的需求来生成代码。所以当供应链攻击发生时，我的反应是：“没影响到我。”所有软件都有安全漏洞，但关键是要将爆炸半径降到最小。问题在于，如果你处理的是开源项目，负责人可能休假了，或者是维护者不在等等，你无法和一个真人交流。那不是 AGI。你会希望尽可能多地自己掌控所有的源代码，这样智能体实际上就能直接修改，而不需要循环或其他提示。你需要拥有你自己的供应链。

<details>
<summary>Original English</summary>

**Speaker E**: If you do it in Ruby, it's going to be a clown show. Static types are a form of verification, folks. I encourage you to to come up with a couple of cutters and a couple of experiments. Try running some loops. Build an application in Ruby and then try to modify it again with these loops and you'll see the maintainability mess. And then try doing it with Haskell. I don't care if you don't know Haskell. It doesn't matter if you don't understand Haskell. The LLM understands Haskell and you can actually prompt the the agent to explain this as if you to to your son or daughter. So, I'm not sure even code needs to be readable these days, but this is frontier frontier thinking. It needs to be explainable. So, I'm playing around with different domains of verification here, but uh one thing's for sure, um type systems are in. Very much in. Rust is very good because how the ecosystem models some types. And because supply chain was mentioned, I need to say it has been 10 months now. I do I minimally use any open source software. Minimally. I just generate it to my requirements. And then when a supply chain attack happens, I'm like, "Didn't affect me." All software has security flaws, but it's about minimizing the blast radius. And the thing is, if you deal with open source project, the person's on on leave, the maintainer, what have you, you can't talk to a human. That's not AGI. You want to be venturing all your source code as much as possible so the so the agent can actually modify and in without a loop or other prompting. You need to own your supply chain.

</details>

### Concluding the Debate

**Speaker G**: 太棒了。非常感谢你的分享。我个人不得不在这里结束辩论了，但现在我们可以决定获胜者了。现场的观众请举手表决，如果你改变了主意并且现在支持 Dex 的观点，请举手。

<details>
<summary>Original English</summary>

**Speaker G**: Awesome. Thank you so much for that. I personally have to close it at that, but we can now decide our winner. Um Show of hands in the audience if your mind was changed and you're now on Dex's side, raise your hand.

</details>

**Speaker H**: 冲啊。

<details>
<summary>Original English</summary>

**Speaker H**: Let's go.

</details>

**Speaker G**: 好的。如果你改变了主意并且现在支持 Ian 和 Jeff 的观点。

<details>
<summary>Original English</summary>

**Speaker G**: Okay. If your mind was changed and you're now on Ian and Jeff's side.

</details>

**Speaker I**: 耶。

<details>
<summary>Original English</summary>

**Speaker I**: Yeah.

</details>

**Speaker J**: 耶。

<details>
<summary>Original English</summary>

**Speaker J**: Yeah.

</details>

**Speaker G**: 灯光太亮了我有点看不清。你们觉得呢？挺精彩的。票数很接近，是的。

<details>
<summary>Original English</summary>

**Speaker G**: I kind of couldn't see with the light. What did you guys think? It was pretty good. It's pretty close, yeah.

</details>

**Speaker K**: 根本看不见。灯太亮了。

<details>
<summary>Original English</summary>

**Speaker K**: It's impossible. The lights are so bright.

</details>

**Speaker G**: 好了。这是一场很棒的辩论。非常感谢大家的聆听。我们下次再见。

<details>
<summary>Original English</summary>

**Speaker G**: All right. Well, that was a good debate. Thank you so much for listening. We'll see you next time.

</details>

**Audience**: [掌声]

[音乐]

<details>
<summary>Original English</summary>

**Audience**: [applause]

[music]

</details>