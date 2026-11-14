---
author: How I AI
date: '2026-09-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4_SHhSMHzNo
speaker: How I AI
tags:
  - software-factory
  - agentic-workflow
  - self-improvement
  - code-generation
title: Warp 首席执行官解析软件工厂与智能体自愈改进机制
summary: Warp 首席执行官 Zach Lloyd 在访谈中阐述了“软件工厂”概念及其内部运作，介绍团队如何通过 Slack、Linear 和 GitHub 触发并追踪智能体构建任务，并结合裁判模型打分与观察者智能体实现自我改进闭环，同时强调不可脱离传统产品调研与人类输入。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Zach Lloyd
companies_orgs:
  - Warp
products_models:
  - Wilson
media_books:
  - How I AI
status: evergreen
---
<!-- chunk 1/6 -->

我能刁难你一下，指出人类其实才是瓶颈吗？因为如果你看从发起任务到提出 PR 的时间，是 35 分钟；但要是看从 PR 到第一次人工审查，却要 3 个半小时。而且上个月你们处理的 PR 数量好像超过了 2000 个。那你怎样才能让团队里的事情不至于像我说的陷入“混乱主宰”的局面？

<details><summary>Original English</summary>
Can I give you a hard time that humans really are the bottleneck? Because if you look at kickoff to PR time, it's 35 minutes, but if you look at PR to first human review, it's 3 and 1/2 [music] hours. And when you're doing I think it was like over 2,000 PRs in the last month. Like how do you keep things in the team from going as I say like chaos reigns?
</details>

>> 什么是软件工厂？至少对我们来说，它是一个具体的名词。它就像一个产品概念，本质上由一堆代码仓库、一堆 MCP 服务器、一堆配置，然后加上一堆 Agent 组成。

<details><summary>Original English</summary>
>> What is a software factory? For us at least, it's an actual noun. It's like a product concept where it consists of a bunch of repos, a bunch of like MCP servers, like a bunch of configuration and then a bunch of agents essentially.
</details>

比如代码审查 Agent、设计不同的 Agent、不同的自动化流程，全都是用代码定义的。所有运行过程都会进行打分。不过接着还有第二层循环——现在 Twitter 上很流行的一个叫作自我改进（self-improvement）的东西，也就是你有一个观察者 Agent，它可以针对你的工厂生成更新，试图去防止特定的失败模式。其中最有用的一点是，你可以让这些工厂 Agent 去做计算机使用验证（computer use verification）。比如在这个例子里，它录制了一段视频。我简直就像是在和一个正在做着我过去 20 年来所做工作的东西对话，而它现在做这事甚至做得有点比我还好了。剧透一下，问题其实出在人类身上。

<details><summary>Original English</summary>
So like a code review agent design different agents, different automations and [music] it's all defined in code. Scoring happens across all runs. But then there's a second loop popular thing on Twitter right now called self-improvement where you have like an observer agent and it can then create updates to your factory that will try to prevent the particular failure mode. One of the things that's most helpful is like you can have these factory agents do computer use verification. So in this case it made a video. I'm just like talking to this thing that is doing this job that I've done for the last 20 years and it's now it's like doing it kind of better than me. Spoiler alert, the humans are the problem.
</details>

### 走进软件工厂

欢迎回到《How I AI》。我是 Clarvo，产品负责人，也是一名 AI 痴迷者，我的使命就是帮助大家利用这些新工具更好地进行构建。今天我请到了 Warp 的 CEO Zach Lloyd，他将向我们确切展示他所说的“软件工厂”究竟是什么意思。他会向我们展示如何在 Slack 中发起任务、走出软件开发生命周期意味着什么，以及一位技术背景的 CEO 是如何借助 AI 来使用非技术工具的。让我们马上开始。

<details><summary>Original English</summary>
[music] Welcome back to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. [music] Today I have Zach Lloyd, CEO of Warp, and he's going to show us exactly what he means by the software factory. He's going to show us how you can kick off tasks in Slack, what it means to go beyond the software development life cycle, and how a technical CEO uses non-technical tools with AI. Let's get to it.
</details>

本期节目由 DX 赞助播出。在近期针对 500 多家工程研发组织的调研中，DX 发现过去一年里 AI 工具上的支出增长了 28 倍。AI 生成代码的比例在攀升，但整体的创新却保持持平。随着团队生成代码的速度越来越快，代码审查和验证中出现的新阻力正在抵消早期的速度提升。DX 在整个软件开发生命周期中统筹追踪速度、质量和成本，让工程管理者能够清晰洞察 AI 如何影响交付，以及这些投资是否正在转化为切实的价值。欢迎前往 getdx.com/howiaai 下载完整报告。网址是 gdx.com/howiaai。Zach，感谢来参加《How I AI》。

<details><summary>Original English</summary>
This episode is brought to you by DX. In a recent study across more than 500 engineering organizations, DX found that spend [music] on AI tools has grown 28x over the last year. The share of AI authored code is climbing, but overall innovation has remained flat. As teams generate code faster, new friction in code review and validation is offsetting those early velocity [music] gains. DX tracks speed, quality, and cost together across the software development life cycle, giving engineering leaders clear visibility into how AI impacts [music] delivery and whether those investments are translating into real value. Download the full report at getdx.com/howiaai. That's gdx.com/howiaai. Zach, thanks for joining how I AI.
</details>

>> 感谢邀请，很高兴来到这里。

<details><summary>Original English</summary>
>> Thanks for having me. Excited to be here.
</details>

>> 现在的推特时间线上有很多趋势，但我认为对于 2026 年来说将是一个重大趋势、或者说在 2026 年看起来很重大的一个概念，就是工厂。工厂，我们抱有的这种奇妙设想——输入 token，输出企业价值，大概就是这么回事，至少它会输出代码。所以，作为 CEO、工程师和构建者，我很期待你能向我们展示——

<details><summary>Original English</summary>
>> There are a lot of trends on the timeline right now, but one that I think is going to be big for 2026 or seems to be big for 2026 is the factory. The factory. this like fantastical idea that we have that we're going to you know input tokens and output enterprise value something like that at least we'll output code so I you know I'm excited for you to show us as CEO as engineer as builder
</details>

>> 对你而言，究竟什么是工厂，以及它在 Warp 内部是什么样子的。

<details><summary>Original English</summary>
>> you know what what to you is the factory and how it looks inside warp
</details>

>> 工厂这个词最近确实很火。其实我不太喜欢“工厂”这个说法，但这好像是大家都已经约定俗成的用词，在我看来它稍微带了点去人性化的感觉。但是，这个概念确实完全如你所说。它指的是，在一个拥有这些堪称神奇的 Agent 的世界里，你如何以更有组织的方式驾驭它们的力量，让它们基本上根据你的想法来为你构建软件。所以是的，很兴奋能向你展示我是如何使用工厂的，以及它对我意味着什么。我最近去参加了 Lenny 的峰会，我想 Marty Cagan 也说过他讨厌“工厂”这个词。我不知道用“圣诞老人的工作坊”是不是更贴切？就像我们有一群神奇的小精灵，精心打造出带来快乐的美妙事物，还帮我们打包成了精美的礼物。所以我想称之为 AI 神奇工作坊。不说了，快向我们展示一下，在你们那里它究竟是什么样子的？对，你刚才确实说了输入想法、输出产品。这是真的吗？这到底是怎么运作的？

<details><summary>Original English</summary>
>> the factory is definitely trending I actually don't love the term factory but it is the sort of thing everyone has standardized on it feels a little bit sort of like dehuman izing to me. But um but yeah, the the idea is exactly what you said. It's like how do you in a world where we have these sort of magical agents kind of harness their power in a more organized way to have them um you know basically build build software for you from your ideas. And so yeah, excited excited to to to show you how I how I use factories and like what it means to me. I was at Lenny Summit recently and I think Marty Kagan also said he hated the word factory. I wonder if it's more like Santa's workshop, right? Like we have magical elves that craft wonderful things that spark joy um and are delivered uh gift wrapped for us. So I'm going to say the AI the AI magical magical workshop. No, show us you know what does what does this look like for you? Yeah, you did you did say you know you put in your ideas, you output product. Is that real? How how does that really work?
</details>

### 工厂在 Warp 的实际运作

>> 是的。它的运作方式大致就是这样。我对工厂的理解是，使用它们的人基本上可以分为两类画像。接下来我会大致展示一下我们在 Warp 内部是怎么做这套流程的。其中有一类是“构建者”画像。所谓构建者画像，是指那些贡献想法、想要去构建东西的人。对于这类画像来说，至少在我们搭建的这套体系中，它看起来跟我们团队里的工程师、设计师或产品经理用本地 Coding Agent 进行构建并没有那么大的不同。你可以看到这里最大的区别——这是我们的 Slack——最大的区别在于，大部分工作都是从一个公开的场合开始的。所以我们对工厂的构想就是，你基本上可以在一个公开的 Slack 频道里 @ 我们的工厂——我们给它取名叫 Wilson——你可以 @Wilson，然后对它说：好的，我希望你——

<details><summary>Original English</summary>
>> Yeah. So, it kind of works like that. Um the the way that I think of of factories is like there's there's basically two types of personas who are using them. So, there's I'll show you like basically how we do this in warp. There's like the the builder persona. So, the builder persona is someone who is contributing ideas, wants to build stuff. And from that persona, it doesn't look like at least the way that we have it set up, it doesn't look that different from like how one of these engineers or designers or product people on our team might build with a local coding agent. The big difference you can see here. So this is like this is our Slack. Uh is that most work is starting in a public place. And so the way we think of factories is like you um you basically can say in a public Slack channel you can tag we named our factory Wilson. Um you can tag Wilson and be like okay I want you to
</details>

>> 来帮我们构建某个东西。当你这么做的时候，Wilson 会做的基本上就不单单是直接去写代码构建——如果你用 Claude Code 或 Codex 之类的工具，可能就只是直接构建——它还会执行另外几个步骤。它会做的是走完这一整套流程：首先，它会对收到的内容进行分诊（triage）。所以它会把它当作输入到工厂的原材料，而不仅仅是一个直接去编写的任务。也就是说，比如在这个例子里，Harry 说他想改变这个功能的外观样式。他给出了相当详细的说明，附带了一张图片，并说明使用 Computer Use。这便触发了一个流程，工厂所做的第一件事实际上是建一个 issue。所以你可以在这边看到，除了使用 Slack 之外，我们还配合使用 Linear，以便所有内容都被追踪记录。因此工厂不仅仅接入了 Slack，它还新建了一个 issue。接着它进行实际的实现编码；对于这个任务来说，它足够简单，也没有歧义，以至于我们确实能够直接把它实现出来。然后它会创建 PR，所以它还集成了 GitHub。接着它会执行 QA 测试——我认为这在如今非常重要，如果你不想把所有时间都耗在做代码审查上的话。其中最有帮助的一点是，你可以让这些工厂 Agent 去做 Computer Use 验证。于是在这个案例中，它为完成的功能录制了一段视频，展示了这个功能，展示了所有的按键操作。

<details><summary>Original English</summary>
>> to build something for us. And when you do that, uh, what Wilson will do is like essentially do not just like the direct build, which is what you might get if you're using like cloud code or codeex, but we'll also like do a few other steps. So what what it what it will do is it'll kind of go through all the steps of like first it will triage whatever this is. So it'll treat it as like an input to the factory, not just like a direct thing to build. meaning it will um you know for this one Harry's saying he wants to change the way this feature looks. He gives like pretty detailed instructions. He um you know attaches an image. He says use computer use and this kicks off a flow where the the first thing that the factory does is actually kind of open an issue. So you can see over here it's like we use linear in addition to using slack so that everything gets tracked. So the factory integrates not just with slack it opens an issue. Then it does the actual implementation for this one. It's like it was simple enough and ambiguous enough that um we could actually implement it. Then it does um it will create the the PR so it integrates also with like GitHub. Then it does the QA which I think is like really important these days like if you want to not spend all your time doing code review. One of the things that's most helpful is like you can have these factory agents do uh like computer use verification. So in this case it like made a video of the completed feature. So it's like showing the thing showing all the keystrokes.
</details>

所以你在这里得到的，接着它就被合并了，对吧？你得到的不仅仅是去构建这个东西这单一的一步。如果是在进入工厂模式之前的世界里，你用本地的 Coding Agent 来做这件事，通常的做法是调出你本地的 Coding Agent，在本地进行修改，在本地测试，然后推送到 GitHub。但在这里，你获得的是将工单、代码审查、PR、视频全部打包在一起完成的整套流程。然后另一件非常神奇的事情是，这一切都是在公开场合完成的。所以如果有其他人想要介入并查看这项任务是如何完成的，甚至想要参与贡献——我们经常有很多人出现在这些 Slack 讨论串里——你进入的世界是，作为一名构建者，你不再是在这种本地孤岛中闭门造车，而是在一个大家都能看到你在做什么的公共空间里工作。从构建者的角度来看，这就是他们使用工厂的方式。到目前为止这能理解吗？

<details><summary>Original English</summary>
And so what you get here is is not just like and then it gets merged, right? Is not just like the single step of build build the thing like if you were to do this with like a coding agent in like the prefactory world, what you would typically do is like pull up your local coding agent, do the change there, test it locally, and then like push it up to GitHub. But you get the whole thing of like the ticket, the the code review, PR, the video all all done together. And then the other like really um kind of magical thing is that it's all done in public. So if you are, you know, someone else wanted to come in and like look at this and see how the task was done or even contribute to it. And so we all have people like multiple people on these Slack threads. you get to a world where as like a builder, you're no longer sort of working in this local silo. Instead, you're working in a public space where everyone can see what you're doing. And so that's like um from the builder's point of view, how they like use the factory. Does that make sense so far?
</details>

>> 能理解。我觉得我正在为那些可能还在努力理解“什么是 Coding Agent、什么是工厂、两者区别在哪”的人梳理思路。我想我从你这里听到的是：所谓的“工厂”，是为了全面反映你心目中软件开发生命周期应有的样貌而全面设计的。所以它不仅仅是“从想法到代码、到 PR、再到推送上线”这么简单，而是：一个想法需要经历几个步骤，它需要走过产品的传送带，进入工单追踪的漏斗，然后我们需要去编码，再然后我们需要去做 QA，接着我们需要去——

<details><summary>Original English</summary>
>> Yeah. And you know, I think what I'm reflecting for folks who are maybe still trying to grapple with okay, like what's a coding agent, what's a factory, what's the difference? I think what I'm hearing from you is the factory quoteunquote is comprehensive comprehensively designed to reflect your version of what the software development life cycle should be. And so it's not just like idea to code to PR to push. It is okay. An idea needs to go through several steps. It needs to go down the conveyor belt of product and into like the funnel of issue tracking and then we need to code it and then we need to QA it and then we need to
</details>

<!-- chunk 2/6 -->

有这些非常具体的验证闭环，我们可以在上面贴上标签说“质检合格，工号 123”。所以对你而言，以及按你所描述的方式，它超越单纯的编程智能体或 Copilot 的地方，在于它实际上旨在承接非常具体的端到端产品步骤，而不仅仅是工程上的那种输入输出。

<details><summary>Original English</summary>
 have

 these

 very

 specific





verification

 loops

 where

 we

 can

 take

 our





sticker

 and

 say

 quality

 controlled

 by





you

 know

 number

 one

 123

 and

 so

 to

 to

 you





and

 the

 way

 you're

 describing

 it

 where





it

 goes

 beyond

 a

 coding

 agent

 or

 a





co-pilot

 is

 that

 it

 is

 actually

 designed





to

 take

 take

 the

 very

 specific

 end





to-end

 product

 steps





um

 not

 just

 the

 engineering

 kind

 of

 like





input

 output.
</details>

>> 这绝对是其中一部分，可以肯定。就像它承担了更多的软件生命周期。所以它完成了更多这些步骤。

<details><summary>Original English</summary>
>> That's

 that's

 definitely

 part

 of

 it

 for





sure.

 It's

 like

 it

 does

 it

 does

 more

 of





the

 the

 software

 life

 cycle.

 So

 it

 does





more

 of

 those

 steps.
</details>

### 工厂模式与工程管理视角

>> 对我来说，还有另一个更大的部分，我刚才向你展示的，是站在单个构建者的角度。如果你进入我们的 Slack，你会看到这种情况整天都在反反复复发生。我们团队里的人都在以这种方式进行构建。而且顺便提一下，有时候并不只是工程师在发起这样的工作，它也可能是自动发起的工作。比如，我们有——我不知道你是否了解 Sentry，它是一个崩溃报告系统——所以我们有相应的信号，当来自我们终端应用等地方出现崩溃报告时，我们会尝试自动修复它们，这些也会进入这个工厂。所以它既可以由人发起，也可以由外部系统发起，实际上还可以在这些工具中的任何一个里面发起。你可以像我们刚才那样发起整个流程，我们本可以在 Linear 中启动整件事，也可以在 GitHub 中启动整件事，所以它集成了所有工具。但在我看来，工厂方式更大的部分并不在于单个构建者是如何工作的，因为这与单个构建者可能正在做的事情并没有那么大不同——比如进入终端使用投票智能体去做某件事。它是不同的，它是公开透明的。

<details><summary>Original English</summary>
>> The

 there's

 a

 a

 whole

 other





>> bigger

 part

 of

 it

 to

 me

 which

 um

 is

 so

 I





showed

 you

 this

 from

 like

 the





perspective

 of

 the

 the

 individual





builder.

 If

 you

 were

 to

 go

 into

 our





Slack,

 you

 would

 see

 like

 this

 is





happening

 over

 and

 over

 like

 all

 day





long.

 The

 people

 on

 our

 team

 are





building

 in

 this

 way.

 And

 sometimes,

 by





the

 way,

 it's

 not

 just

 like

 the





engineers

 who

 were

 kicking

 off

 work

 like





this.

 It

 could

 be

 work

 that's

 being





kicked

 off

 um

 automatically.

 So,

 for





instance,

 we

 have

 I

 don't

 know if

 you





know

 Sentry,

 but

 it's

 like

 a

 crash





reporting

 system.

 And

 so

 we

 have

 signals





when

 there

 are

 crash

 reports

 coming

 from





like

 our

 terminal

 app

 that

 we

 try

 to





automatically

 fix

 those

 and

 those

 go





into

 the

 factory

 too.

 So

 it

 can

 either





be

 human

 initiated,

 it

 can

 be

 um





initiated

 by

 like

 an

 external

 system

 and





it

 can

 be

 initiated

 actually

 in

 any

 of





these

 tools.

 So

 it's

 like

 you

 can





initiate

 it

 like

 we

 could

 have

 started





this

 whole

 thing

 in

 linear

 we

 could

 have





started

 this

 whole

 thing

 in

 GitHub

 and





so

 it's

 it's

 integrated

 into

 all

 the





tools

 but

 the

 bigger

 piece

 of

 the





factory

 approach

 in

 my

 opinion

 is

 not





like

 it's

 not

 so

 much

 how

 it

 uh

 the





individual

 builders

 work

 because

 it's





not

 all

 that

 different

 from





individual

 builders

 who

 might

 be

 using





like

 like

 who

 might

 be

 going

 into

 the





terminal

 for

 instance

 and

 using

 a

 voting





agent

 to

 do

 something.

 It's

 different.





It's

 in

 public.
</details>

>> 但工厂方式真正不同的地方在于，一切都在云端集中化了。而且它还有完全不同的另一面，这不是面向构建者的，而是面向那些试图在团队中扩大软件开发规模的管理者。

<details><summary>Original English</summary>
>> But

 what's

 really

 different

 in

 the





factory

 approach

 is

 that

 everything

 is





like

 centralized

 in

 the

 cloud.

 And





there's

 a

 whole

 other

 aspect

 to

 it

 which





is

 for

 not

 the

 builders

 but

 for

 the





people

 who

 are

 like

 the

 managers

 who

 are





like

 trying

 to

 scale

 software





development

 on

 their

 team.
</details>

>> 终于有给管理者用的东西了。

[笑声]

<details><summary>Original English</summary>
>> Finally

 something

 for

 the

 managers.





[laughter]
</details>

>> 这正是大家一直想要的，对吧？对构建者关注太多了。不，但严肃地说，如果你作为经营公司的人，我关心的是——这是一个竞争极其残酷的市场，我想看到我们前进的速度有多快，我希望确信我们构建软件的方式实际上是在随着时间不断改进的，我想确保我们没有在浪费太多钱。而在每个构建者都有自己独立的本地环境的世界里，这是非常非常难以实现的。所以这是工程经理的梦想，就像是 CTO 的梦想。并不是说这是世界上最酷炫的事情，但现在我有了这种能力，可以进行集中管理并了解每个人在做什么。比如在这个屏幕上，这是来自我们团队关于我们如何使用工厂的真实数据。能大致感受到工厂的自动化程度如何、我们的交付速度如何、我们发布东西需要多长时间，因此就有所有这些衡量指标。

<details><summary>Original English</summary>
>> It's

 what

 everyone's

 been

 wanting,





right?

 Too

 much

 attention

 on

 the





builders.

 No,

 but

 in

 all

 seriousness,

 if





you're

 like

 like

 my

 concern

 uh

 as





someone

 who's

 running

 a

 company,

 it's





like

 I

 want

 I

 want

 soft

 like

 it's

 a





super

 duper

 competitive

 market.

 I

 want





to

 see

 how

 quickly

 we're

 moving.

 I

 want





confidence

 that

 um

 the

 way

 that

 we're





building

 software

 is

 actually

 improving





over

 time.

 I

 want

 to

 make

 sure

 that





we're

 not

 like

 wasting

 too

 much

 money.





And

 in

 the

 world

 of

 like

 all

 of

 like





every

 builder

 has

 their

 own

 individual





local

 setup,

 that's

 very

 very

 hard

 to





get.

 And

 so

 this

 is

 like

 an

 engineering





manager's

 dream.

 It's

 like

 a

 it's

 like

 a





CTO's

 dream.

 Like

 not

 that

 this

 is

 the





the

 coolest

 thing

 in

 the

 world,

 but

 it's





like

 now

 I

 have

 the

 ability

 um

 to

 sort





of

 centralize

 and

 see

 what

 everyone's





doing.

 So

 for

 instance

 on

 this

 screen





here

 it's

 like

 these

 are

 this

 is

 actual





data

 from

 our

 team

 in

 terms

 of

 like

 how





we're

 using

 the

 factory.

 It's

 like





there's

 a

 sort

 of

 sense

 of

 like

 how





automated

 is

 the

 factory

 um

 what's

 our





velocity

 how

 long

 does

 it

 take

 us

 to





like

 ship

 stuff

 and

 so

 there's

 just

 all





these

 measurements.
</details>

### 单 PR 人工交互次数与效率度量

我们能不能在你的生产力指标上稍作暂停，因为我之前确实没见过这个指标，我们见过很多指标，而这个是

<details><summary>Original English</summary>
 Can

 we

 pause

 real





quick

 on

 your

 productivity

 because

 I





actually

 haven't

 seen

 this

 measure





before

 um

 and

 we've

 seen

 a

 lot

 of





measures

 which

 is
</details>

>> 每次 PR 的人工交互次数。请

<details><summary>Original English</summary>
>> human

 interactions

 per

 PR.

 Just

 yeah
</details>

>> 给我们讲讲为什么用这个，因为老实说我之前没听过这个指标，我很喜欢它。

<details><summary>Original English</summary>
>> talk

 us

 through

 why

 that

 because





honestly

 I

 haven't

 heard

 that

 one

 before





and

 I

 like

 it.
</details>

>> 这背后的直觉是，无意冒犯，但在软件生产方面，人类有点像是瓶颈所在。人类同时也是创造力的源泉。但总的来说，企业所希望的——而在 Warp 我们很大程度上也在努力为企业构建产品——就是如何实现更多自动化？如何让那些真正可以通过智能体完成的事情，以近乎全自动的方式去完成？所以，一般的直觉就是，你提示的次数越多，

<details><summary>Original English</summary>
>> You

 know

 the

 sort

 of

 instinct

 underlying





this

 is

 that

 um

 we

 are

 going

 to

 be

 not





not

 to

 put

 this

 the

 wrong

 way

 but

 it's





like

 humans

 are

 a

 little

 bit

 of

 the





bottleneck

 in

 terms

 of

 production

 and





software.

 They're

 also

 the

 the

 creative





force.

 Um,

 but

 in

 general,





what

 companies





want

 and

 we're,

 you

 know,

 we're

 trying





to

 build

 for

 companies

 at

 warp

 largely





is

 like

 how

 do

 you

 automate

 more?

 How

 do





you

 make

 things

 that

 can

 truly

 just

 be





done

 agentically

 be

 done

 in

 an

 almost





fully

 automated

 way?

 And

 so,

 you

 know,





the

 the

 general

 instinct

 is

 like

 the





more

 times

 you

 have

 to

 prompt,
</details>

>> 你去引导或哄劝你的智能体的次数越多，那就会成为吞吐量的一个限制因素。所以，这里你就开始进入

<details><summary>Original English</summary>
>> the

 more

 times

 you

 have

 to

 steer

 or

 like





like

 cajul

 your

 agent,

 that's

 like





that's

 going

 to

 be

 a

 limiter

 on





throughput.

 So,

 this

 is

 where

 you

 start





to

 get

 into

 like
</details>

>> 工厂的世界，这就好比设想你在运营一家特斯拉工厂之类的。这就像是你必须停线多少次？所以，我们试图为工程领导层提供一个视角，让他们看到：好的，你们是否能够随着时间让事情变得更有效率？

<details><summary>Original English</summary>
>> factory

 world

 like

 this

 is

 like

 imagine





you're

 running

 like

 a

 Tesla

 plant

 or





something.

 It's

 like

 how

 many

 times

 do





you

 have

 to

 stop

 the

 line?

 Um,

 and

 so,





you

 know,

 we're

 we're

 trying

 to

 give





engineering

 leaders

 a

 view

 of

 like,





okay,

 how

 are

 are

 you

 are

 you

 are

 you





able

 to

 sort

 of

 make

 things

 more





efficient

 over

 time?
</details>

>> 提个简单的问题，这些只是——因为我脑海里，我是说作为一个曾经当过 CTO 的人，我会觉得，对，这正是我想要的。

<details><summary>Original English</summary>
>> And

 quick

 question,

 are

 those

 just





because

 my

 mind

 I

 mean

 I

 you

 know,

 as

 a





one-time

 CTO,

 I'm

 like,

 yeah,

 this

 is





exactly

 what

 I

 want.
</details>

>> 这些交互，你会将这些交互视为 prompt 这种前置引导吗？你考虑的是 PR 上有多少条评论、经历了多少次循环，还是说这个每次 PR 的交互得分包含的范围有多广泛？

<details><summary>Original English</summary>
>> Are

 these

 interactions

 do

 you

 think

 of





these

 interactions

 as

 like

 the

 prompts,





the

 sort

 of

 like

 upfront

 steering?

 Are





you

 thinking

 about

 like

 how

 many





comments

 on

 PRs,

 how

 many

 loops,

 like





how

 inclusive

 is

 this

 like

 interaction





per

 PR

 score?
</details>

>> 它是所有这些的总和。因为——

<details><summary>Original English</summary>
>> It's

 it's

 all

 of

 those.

 So

 because

 the
</details>

>> 而且话说回来，我认为随着时间的推移这肯定可以进一步完善，请记住我们正在努力探索究竟什么才是合适的一套指标，但这个实际的指标——

<details><summary>Original English</summary>
>> and

 again

 I

 think

 this

 could

 definitely





be

 refined

 over

 time

 and

 bear

 in

 mind





we're

 like

 trying

 to

 figure

 out

 so

 what





is

 the

 right

 set

 of

 metrics

 but

 this





actual

 metric
</details>

>> 因为工厂是——

<details><summary>Original English</summary>
>> because

 the

 factory

 is

 like
</details>

>> 集成到了你所有的知识工作工具中。它包含了所有那些内容：在 Slack 里重新 prompt 了多少次、在 Linear 上评论了多少次、在代码审查中你不得不去修正它多少次。所以，它有点像是，是的，它是代表你为了让它完成工作不得不做多少工作的一种替代指标。

<details><summary>Original English</summary>
>> integrated

 into

 all

 of

 your

 knowledge





work

 tools.

 It

 includes

 all

 those

 things





like

 how

 many

 reprompts

 in

 Slack,

 how





many

 comments

 on

 linear,

 how

 many

 times





did

 you

 have

 to

 correct

 the

 thing

 in





code

 review.

 And

 so,

 uh,

 it's

 it's

 like





a

 kind

 of

 like,

 yeah,

 it's

 a

 proxy

 for





how

 much

 work

 did

 you

 have

 to

 do





>> in

 order

 to,

 um,

 you

 know,

 get

 the

 thing





to

 do

 the

 job.
</details>

### 人类瓶颈与代码审查的演进

>> 好吧。等等，我想刁难你一下。还有一件事，因为甚至在我们开始录制之前，你就问要讲得多硬核，我说好吧，那我们现在至少要戴上 CTO 的帽子。我能就“人类确实是瓶颈”这点刁难你一下吗？因为如果看一下从启动到发起 PR 的时间，是 35 分钟。但如果看从 PR 到第一次人工审查的时间，是三个半小时。三个半小时。所以太搞笑了，周期时间依然是，伙计，这才是你真正必须关注的事情。就是那个数字。

<details><summary>Original English</summary>
>> Okay.

 Wait,

 I

 want

 I

 want

 to

 give

 you

 a





hard

 time.

 One

 more

 thing

 because

 even





before

 we

 started

 recording,

 you

 said





like

 how

 technical

 and

 I

 was

 like,

 okay,





well,

 we're

 going to

 put

 on

 the

 CTO,

 at





least

 the

 CTO

 hat

 right

 now.

 Um,

 can

 I





give

 you

 a

 hard

 time

 that

 humans

 really





are

 the

 bottleneck?

 Because

 if

 you

 look





at

 kickoff

 to

 PR

 time,

 it's

 35

 minutes.





But

 if

 you

 look

 at

 PR

 to

 first

 human





review,

 it's

 three

 and

 a

 half

 hours.





Three

 and

 a

 half

 hours.

 And

 so

 it's

 like





so

 funny

 that

 still





cycle

 time,

 man.

 Like

 it's

 it's

 the





thing

 you

 really

 have

 to

 focus

 on.

 Um





it's

 that

 it's

 that

 number.
</details>

>> 是的。瓶颈依然存在。而且我们，我是说——

<details><summary>Original English</summary>
>> Yeah.

 There's

 still

 the

 bottleneck.

 And





we're

 I

 mean
</details>

>> 我们依然在做人工代码审查。

<details><summary>Original English</summary>
>> we're

 still

 doing

 human

 code

 review.

 Um
</details>

>> 你们所有的 PR 都会接受人工代码审查吗？目前我们所有的 PR 都会接受人工代码审查。

<details><summary>Original English</summary>
>> do

 you

 do

 all

 all

 your

 PRs

 get

 human





code

 review?

 Currently

 all

 of

 our

 PRs





get

 human

 code

 review.

 Oh
</details>

>> 噢，所以现在我认为这是团队的选择，是组织层面的选择。是的。

<details><summary>Original English</summary>
>> and

 so

 now

 this

 is

 like

 I

 think

 a

 team





choice

 an

 organizational

 choice.

 Yeah.
</details>

>> 我们有一点关于这方面的改变是，现在——我们过去曾要求的工作流是，团队中的 A 成员用智能体构建某样东西，然后 B 成员去审查智能体的代码。我们现在不再要求这样了，向智能体发出 prompt 的那个人也可以审查它的代码。

<details><summary>Original English</summary>
>> We

 have

 um

 the

 one

 thing

 that

 we

 have





changed

 around

 this

 is

 now

 like

 we

 used





to

 require

 like

 the

 workflow

 used

 to

 be





like

 person

 A

 on

 our

 team

 would

 build





something

 with

 an

 agent

 and

 person

 B





would

 review

 the

 agent's

 code.

 We

 no





longer

 require

 that

 like

 the

 person

 who





prompts

 the

 agent

 can

 also

 review

 its





code.
</details>

>> 好吧。是的，

<details><summary>Original English</summary>
>> Okay.

 Yeah,
</details>

>> 你让我感觉好点了。

<details><summary>Original English</summary>
>> you're

 making

 me

 feel

 better.
</details>

>> 这是一件更好的事，但这仍然像——你知道，我们目前还没有完全的信任。我认为这后续的演进方式会是，最终有一定比例的内容，我们将有足够的信心可以跳过那一步。

<details><summary>Original English</summary>
>> That's

 a

 better

 thing,

 but

 it's

 still





like

 we,

 you

 know,

 we

 we

 don't

 have

 yet





complete

 trust.

 I

 think

 the

 way

 this





will

 evolve

 is

 like

 some

 percentage

 of





some

 percentage

 of

 stuff

 will

 um

 will





eventually

 we'll

 feel

 confident

 enough





that

 we

 can

 skip

 that.
</details>

>> 是的，我最近录了一期节目。我构建了一个名为 Merge Mommy 的 Eve 智能体。这也是我在即使很成熟的工程组织中也经常看到的流程：

<details><summary>Original English</summary>
>> Yeah,

 I

 did

 an

 episode

 recently.

 I

 built





um

 an

 Eve

 agent

 called

 Merge

 Mommy.

 Um,





and

 this

 is

 this

 is

 the

 flow

 that

 I





often

 see

 in

 even

 mature

 engineering





organizations
</details>

>> 你的做法基本上是给每个 PR 自动评定风险分数。

<details><summary>Original English</summary>
>> is

 what

 you

 do

 is

 you

 basically

 like





risk

 score

 every

 PR
</details>

>> 梳理并进行风险评分，然后任何低风险或极低风险的内容都会获得 Merge Mommy 的盖章批准，接着人类就可以直接按下按钮进行合并。任何中等、高风险或诸如此类、在风险上有某种异常值的，都需要人工审查，这样就能让你把队列中最底部的那一部分处理掉。另外也让你有充裕的精力，对真正重要的事情进行高质量的人工审查。

<details><summary>Original English</summary>
>> automatically.

 So

 go

 through

 risk

 score





it

 and

 then

 anything

 that

 is

 low

 or





extra

 low

 risk

 gets

 a

 stamped

 approval





from

 merge

 mommy

 and

 then

 a

 human's





allowed

 to

 just

 smash

 the

 button

 and





merge.

 anything

 that's

 like

 medium

 high





or

 whatever

 or

 has

 some

 like

 outlier

 on





risk

 requires

 human

 review

 and

 that

 just





like

 lets

 you

 get

 that

 bottom

 trunch

 of





the

 queue

 out.

 Um,

 also

 just

 so

 you

 have





good

 capacity

 for

 high

 quality

 human





review

 on

 the

 things

 that

 really

 matter
</details>

>> 100%。我认为代码审查变成了一项风险管理的实践。我认为这是对的。我想向你展示工厂里的其他一些东西，只是想向你展示

<details><summary>Original English</summary>
>> 100%.

 Um,

 I

 think

 code

 review

 becomes

 an





exercise

 in

 risk

 management.

 I

 think





that's

 right.

 I

 want

 to

 show

 you

 some





other

 stuff

 in

 the

 factory

 just

 to

 show





you

 like
</details>

>> 这与标准的交互式智能体有何不同。所以

<details><summary>Original English</summary>
>> how

 this

 is

 different

 than

 just

 standard





interactive

 agent.

 So
</details>

>> 你能得到——成本是当下每个人都在考虑的问题，所以

<details><summary>Original English</summary>
>> you

 get

 um

 cost

 is

 on

 everyone's

 mind





right

 now

 and

 so
</details>

>> 你能得到像

<details><summary>Original English</summary>
>> you

 get

 like
</details>

<!-- chunk 3/6 -->

这是 Asian 成本（注：语音疑为 agent cost）。目前它没有把人员成本这类因素考虑在内，但就像……

<details><summary>Original English</summary>
this is Asian cost. It doesn't factor in the sort of cost of the people at the moment but it's like
</details>

>> 你知道，你可以看到，几周前我们的成本真的很贵。我们对模型配置做了一些更改，把这个成本降了下来，而且我们希望继续压降它。不过，能为你的整个团队提供针对这一块的集中视图本身就很关键。嗯……

<details><summary>Original English</summary>
>> you know you can see like we we were really expensive a few weeks ago. We made some changes to our model configuration and we've driven this cost down and we want to continue to drive it down but just like having the centralized view for this across your whole team. Um
</details>

>> 能问你一个关于成本的问题吗？

<details><summary>Original English</summary>
>> can I ask you a questionable cost?
</details>

>> 一个关于成本的快速提问。所以我的意思是，这相当……你可以看到这里的下降。嗯……

<details><summary>Original English</summary>
>> Quick question cost. So I mean this is a pretty you can you can see the the drop here. Um
</details>

>> 我在跟工程组织交流时经常看到这种情况。他们经常会看到，在引入 AI 时每个 PR 的成本会出现上升——你们也是这样——然后随着你们做优化，就会看到这种下降。你觉得目前最大的杠杆是模型吗？

就是说，那个是杠杆所在吗？

<details><summary>Original English</summary>
>> I I see this a lot when I'm talking to engineering organizations. They often see like a rise in cost of PR as they're per PR as they're adopting AI which you all already have and then we see this drop as you're doing optimization. Do you feel like the biggest lever here is model right now?

It's like that the is that the lever?
</details>

>> 是的，是模型。呃，我认为模型是最大的。我觉得像上下文，比如那种……

<details><summary>Original English</summary>
>> Yeah, it's it's model. Uh I think model is the biggest. I think like context like the way
</details>

>> 上下文管理

<details><summary>Original English</summary>
>> context management
</details>

>> 比如上下文管理作为次要因素也很重要。嗯，要我说模型是最大的。

<details><summary>Original English</summary>
>> like context management matters as a secondary thing. Um I would say model is the biggest.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 嗯……

<details><summary>Original English</summary>
>> Um
</details>

>> 而且真正弄清楚这一点的方法其实是去测试，这也是我想展示的内容。

<details><summary>Original English</summary>
>> and that the the the way to really figure this out actually is to test which I is something I want to show as well.
</details>

>> 不过基本上来说，是的，我认为模型是最大的一个。嗯，关于开销视图还有其他问题吗？要是没有的话……

<details><summary>Original English</summary>
>> But um basically yeah I think I think model is is the biggest one. Um any other questions on the just like the spend view otherwise
</details>

### 软件工厂视角与自动化评分

>> 那太好了。

所以另一件事，就是这里真正变得有点面向工厂化的地方，就是我们改变开发的方式。而且这我认为对于正在观看、试图管理这些团队并扩展编码智能体规模的人来说是最相关的：我们现在正在衡量一切。所以这里面的最后一项，我们称之为评分（scoring），基本上能为你提供一个跨所有智能体运行的视图，看看它们在不同维度上的表现如何。

所以我们基本上，因为工厂是一个闭环系统，智能体在工厂里每执行一次任务，该任务就会被记录下来。这就为你打开了一种可能性，让你能够回过头去回溯性地查看任务完成得有多好。你可以由人工来做这件事，你完全可以自己回过头去看那些任务。但你也可以做另一件事，那就是让智能体来做这事，这正是我们所做的。比如，看看我能不能找一个有趣的例子。嗯，比如这里有一个很有趣的：冗余测试。所以如果你……

<details><summary>Original English</summary>
>> that's great.

So the the other thing like this is where it really gets kind of factory oriented is like the the way that we're changing development and this is I think this is most relevant for folks who are watching we're trying to manage like these teams and scale coding agents is like we now we're like measuring everything and so this last thing in here which we call scoring basically gives you a view um across all your agent runs of like how they're doing on different dimensions. And so we we basically because the factory is like a closed kind of like closed loop system like every every time an agent does a task in the factory that task gets recorded and what that opens is the possibility for you to go and like like go back retroactively and look at how well the task was done. And so you could do this as as a person. You could literally just go back and look at at tasks. But the other thing that you can do is you can have agents do this, which is is what um is what we do. And so for instance, let me see if I can find an interesting one. Um like here's an interesting one like redundant tests. So if you're
</details>

>> 如果你用过……你知道我在这里指的是什么，就像……

<details><summary>Original English</summary>
>> if you're working with um you know what I'm talking about here, it's like
</details>

>> 哦，我知道你在说什么。我每推一个 PR，就搞得像是我得运行并设置 135 个测试。

<details><summary>Original English</summary>
>> oh I know what you're talking about. Every PR I push, it's like I have run and set up 135 tests.
</details>

>> 没错。［笑声］

<details><summary>Original English</summary>
>> Exactly. [laughter]
</details>

>> 废话，确实是这样。它之所以会这样做，是因为，你知道的，它们写测试不一定是为了防止回归，也是为了顺便测试过程中的行为。于是最终就会留下一堆你不需要的测试。所以我们……你知道，如果你采取工厂化方法，你大致就会知道这可能是一种失效模式。而你能做的，就是编写一个评分器，利用 LLM 作为裁判，比如我想去查看所有智能体的运行，看看有多少次——另一个智能体，不同于执行任务的那个智能体——认为存在冗余测试。这能理解吗？

<details><summary>Original English</summary>
>> It's it's duh. It's like it's it's like and the reason it does this is because uh you know they're writing tests not to like prevent regressions necessarily, but also just like test behavior along the way. And so you end up with a bunch of tests that you don't need. And so we um you know, if you take the factory approach, you kind of know this might be a failure mode. And what you can do is you can write essentially a um like a scorer that uses LLM as a judge to be like okay I want to go and look at um you know all the agent runs and I want to see how often we're you know an agent thinks a different agent than the one that did the task thinks that there's redundant test. Does this make sense?
</details>

>> 是的，完全明白。

<details><summary>Original English</summary>
>> Yeah, totally.
</details>

>> 所以你基本上就是，好吧，我要选一个裁判模型。这是一个中等聪明的裁判模型。你不希望它太贵，否则你最终会在评分上花很多钱。你让它根据“对于这项任务，它表现看起来如何”来进行分类。呃，在具体操作方式上，你会选定某种抽样率，然后随着时间推移，你会得到一组运行记录，在其中你可以看到，有时这个智能体会认为存在一些多余的测试。这就是我所说的真正的衡量。然后你能做的，就是作为人类，你确实可以去查看这里正在发生什么。但我会向你展示，在工厂的世界里其实还有一种更好的做法，那就是你实际上可以……

利用智能体来找出这些运行中出了什么问题，并尝试改进工厂。这能理解吗？

<details><summary>Original English</summary>
>> And so you basically are like okay I want I I'll pick a judge model. This is like a kind of medium smart judge model. You don't want it to be too expensive otherwise you end up spending a lot of money on scoring. You have it classified in terms of like for this task like how did it look? Uh you pick like a sort of sampling rate on in terms of how you want to do this and then you get over time a set of runs where you can see that like sometimes this agent thinks that there were some like surplus tests. And so this is what I mean by like the real measurement. Then what you can do is like you can go and you can actually you know as a human you can go and kind of look at what's happening here. But I'll show you there's also a better way to do this in the factory world where it's like you can actually um

use agents to sort of identify what's gone wrong in these runs and try to improve the factory. Does this make sense?
</details>

>> 是的。我很好奇，你们做这个是在单次运行的基础上做，还是跨一组 PR 在汇总的基础上做？

<details><summary>Original English</summary>
>> Yeah. I'm curious. Do you do this um on a per run basis or on an aggregate basis across a set of PRs?
</details>

>> 汇总。很好的问题。所以……

<details><summary>Original English</summary>
>> Aggregate. Great question. So
</details>

>> 是的，所以我们的做法是，评分——我称这个……我们称之为评分器。评分是跨所有运行进行的。但接着有第二个闭环，也就是目前在 Twitter 上很火的另一件事，叫做自愈/自我改进（self-improvement）：你引入一个智能体，基本上是说，针对所有失败的运行——你需要一个真实的样本，比如大概 20、25 次失败运行，你需要一定的样本量，否则它就会开始……

<details><summary>Original English</summary>
>> yeah, so what we do is like the the scoring and this I call like this thing we call this like the score. The scoring happens across all runs. But then there's a second loop uh which is another like popular thing on Twitter right now called self-improvement where you take an agent and you basically say okay for all of the failed runs and you need like you need like a real sample like maybe 20 25 failed runs. You need some significant sample size otherwise it starts to
</details>

>> 基于单一事件过度纠偏。

你让它看……你让一个观察者智能体去看，然后它可以对你的工厂生成更新，尝试去预防那种特定的失效模式。

<details><summary>Original English</summary>
>> overcorrect based on single uh based on single things. you have it look uh you have like an observer agent look and it can then create um updates to your factory that will try to prevent the particular failure mode.
</details>

>> 所以我们来看看我能不能找到一个，比如……我不知道，我这里纯粹是随便挑一个……

但它发现了驱动工厂的技能存在某些问题。它正在呈现证据并指出：“好的，我们应该以特定方式更改我们某个工厂智能体的定义。”如果你深入底层去看这个，它就像是在更改我们工厂智能体应该执行的第 10 步。这能理解吗？

<details><summary>Original English</summary>
>> And so let's see if I can find one that's like I don't know this I'm just literally picking a random one here

but um this is finding some some issue with our skills that are driving the factory. It's presenting evidence and it's saying, "Okay, we should change the definition of one of our factory agents in a particular way." And if you go under the hood and look at this, it's like it's changing this like step 10 of what our factory agent should do. Does this make sense?
</details>

>> 明白。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 所以这对我说真的很令人兴奋。促成这一切运转的关键，在于你用代码来定义工厂。

<details><summary>Original English</summary>
>> And so this is um to me this is really exciting. Like the way the thing that's like enabling this whole thing to work is that um you define the factory in code
</details>

>> 代码。是的。

<details><summary>Original English</summary>
>> code. Yep.
</details>

>> 所以，你知道，我这么说指的是，如果你去看这种定义，你会说，好吧，工厂……什么是软件工厂？至少对我们来说，它是一个实际的名词，是一个产品概念，它由一堆代码仓库、一堆 MCP 服务器、一堆配置，然后基本上还有一堆智能体组成。比如一个代码审查智能体、设计……各种不同的智能体、不同的自动化流程。

而且它全都是用代码定义的。以这种方式——在 Warp 工作流/工厂（warp factories）中——这样做的价值在于，你获得了实际能够……你可以测试不同的配置，并且知道……你基本上是在特定时间点冻结工厂的状态。所以你可以这样：好吧，如果我们更改工厂定义，然后把所有这些任务再运行一遍，我们就能看出情况是否变得更好了。呃，这也使得……因为这些全都是代码，所以编码智能体实际上可以更新工厂以使其变得更好。这能理解吗？

<details><summary>Original English</summary>
>> And so, you know, what I mean by that is like if if you were to look at the sort of definition, you would say, okay, the factory, what like what is a software factory? It's like it's like for us at least, it's an actual noun. It's like a product concept where it consists of a bunch of repos, a bunch of like

MCP servers, like a bunch of configuration and then a bunch of like agents essentially. So like a code review agent design like different agents different automations

um and it's all defined in code and the the value of doing it that way with like in warp factories is that you get the ability to actually

um you can like test different configurations and know like you're basically freezing the state of the factory at a given point. So you can be like okay if we were to to change the factory definition then like run all these tasks again we could see if things were better. Uh it also let makes it so that like um an agent can actually because these are all it's all code like coding agents can actually update the factory uh to make it better. Does this make sense?
</details>

### 赞助插播与总结

>> 是的。本期节目由创意智能全球排行榜 Open Art Arena 赞助播出。每周都有新的 AI 模型发布，大家都声称自己是最优秀的，但究竟在哪方面最优秀？Open Art Arena 的创立就是为了回答真正重要的问题：哪款模型［音乐］最适合你的具体工作？Open Art Arena 不是选出一个总体赢家，而是在真实的创意任务中对模型进行排名，涵盖广告、电影、动画、［音乐］产品、平面设计、剪辑以及口型同步，同时覆盖图像和视频。这些排名并非基于炒作，而是由专业人士、行业领袖和在职创作者通过双盲评估评判得出的。因此，评委永远不知道哪份产出是由哪个模型生成的。这意味着你可以看到模型在面对你所从事的创意工作时实际表现如何。所以，别再猜该用哪个模型了。探索基于真实创意工作的排名，为你的项目找到合适的模型，节省时间和成本。请在 Open Art Arena 查看排名。

是的，我就是想稍微总结一下我们目前的进展，因为我认为这里面有非常多丰富的内容，尤其是对工程负责人和构建者来说。然后我知道接下来我们要进入一些……

<details><summary>Original English</summary>
>> Yeah. This episode is brought to you by Open Art Arena the global leaderboard for creative intelligence. Every week, new AI models launch, and everyone claims to be the best, but best at what? Open Art Arena is built to answer the question that actually matters. Which model [music] is best for your specific job? Instead of one overall winner, Open Art Arena ranks models across real creative tasks from advertising and film to animation, [music] product, graphic design, editing, and lip-sync covering both image and video. And these rankings aren't based on hype. They're judged by professionals, industry leaders, and working creators through blind evaluations. So judges never know which model produced which output. That means you can see how models actually perform when it comes to the creative work you're doing. So stop guessing which model to use. Explore rankings based on real creative work and find the right model for your project and save time and cost. See the rankings at Open Art Arena. Yeah, I just want to like, you know, kind of sum up where we are so far because I think there's so much rich stuff in here, especially for engineering leaders and builders. And then I know we're going to get to some
</details>

>> 非以工程为中心的工作流，对此我很期待。不过……

<details><summary>Original English</summary>
>> workflows that are not engineering focused which I'm excited about. But the
</details>

<!-- chunk 4/6 -->

### 工作方式与工厂可观测性

你知道，在你讲述这些的过程中，我看到了一两个趋势、主题：第一，工作发生在公开场合。所以我看到，你知道，正在走向这样一种趋势——工作不再是在工单中分配、然后在笔记本电脑上处理工单，呃，工作正发生在公开场合，无论是在 Slack 还是其他渠道，

<details><summary>Original English</summary>
you know a couple trends themes that I've seen as you talk through this one work happens in public. So I'm seeing you know this move towards instead of work being assigned in tickets and then tickets being worked on on laptops um work is happening in public whether it's Slack or some other channel
</details>

>> 然后，然后在云端执行。所以基本上任何人都可以与之互动。呃，工厂确实带有这种软件开发生命周期式的定义，但除此以外，它还具备你在所有行为上所做的这种汇总元分析，这提供了，你知道，正如我们所说，给管理者提供了他们想要的东西，那就是：我们随着时间的推移是否变得更高效了？这个工厂真的有效吗？多少人类，多少智能体？两者之间的内部平衡是什么？剧透一下：现在人类才是问题所在[笑声]。然后，呃，然后你所做的，就是你还在针对工厂中想要纠正的关键行为进行这些 eval。呃，这是我在与工程团队交流时一直告诉他们的事情，这也是当你本地使用某些工具（比如 Cloud Code）时的一大挑战，我说你需要会话级的遥测，因为你需要能够将整个工程团队内部各个会话中的故障汇总起来。

<details><summary>Original English</summary>
>> and then and then executed in the cloud. So sort of anybody can interact with that. Um the factory does have this software development life cycle kind of like definition to it but on top of that it has this aggregate meta analysis that you're doing across all the behaviors which is giving you know as we said giving the people the managers what they want which is are we getting more efficient over time is this factory actually effective how many humans how many agents what's the inner balance between the two spoiler alert the humans are the problem [laughter] right now and then Um, and then what you're doing is you're also doing these eval against key behaviors in your factory that you want to correct. Um, and this is something that when I talk to engineering organizations, I tell them all the time, which is such a challenge when you're using something locally like for example cloud code, is I say you need session level telemetry because you need to be able to aggregate up the failures within sessions across your engineering team.
</details>

所以有些团队的做法确实是把每个本地编码会话抓取到 S3，并自己在自己的平台中运行类似于 eval 的东西。但我坚信，如果你在每一个编码会话中没有对会话、工具调用、MCP 调用、测试失败、计算机使用层面的可观测性，你就会错失大量优化效率、成本、模型以及团队如何使用工具的机会。所以我认为大家做这件事非常重要。然后你增加的额外一层是：太好了，那就利用这些洞察让工厂变得更好，无论你如何定义“更好”。

<details><summary>Original English</summary>
And so some teams do this truly by like sucking up every local coding session to S3 and running their eval kind of like um on on their own in their own platform. But I do believe that if you do not have session tool call MCP call test failure computer use level observability into every single single coding session. you're missing a lot of opportunity to optimize efficiency, cost, model, just like how your team uses the tools. And so I think it's super important that people do this. And then what you've added is this extra layer of great then take those insights and make the factory better, however you define better.
</details>

>> 总结得太好了。呃，

<details><summary>Original English</summary>
>> There's a great summary. Um,
</details>

>> 太好了。我做到了。

<details><summary>Original English</summary>
>> great. I did it.
</details>

>> 太棒了。专业

<details><summary>Original English</summary>
>> Great. Professional
</details>

>> 播客。这里，为了让你感受一下一旦拥有了这些数据你该如何继续、比如如何走得更远，呃，我认为你的总结非常棒。另一件你可以做的事情——并且我认为各组织都会这么做，因为这是，因为未来没有什么比优化构建和交付软件的方式更重要的了。所以，如果你搭建好了刚才所说的一切，也就是你有了追踪，有了 eval，另一件非常强大的事情是，还有一种方法可以让你更进一步：那就是增加基本上利用自己的数据，以不同的配置回放这些会话的能力，从而实际衡量——就像你之前提的问题——呃，如果你用了不同的模型，从成本角度或质量角度来看表现会如何。

<details><summary>Original English</summary>
>> podcast. There's there's what just to give a sense of how you can continue to like you can go even further once you have this data. Uh I think your summary was awesome. The other thing that you can do and like I thinkorgs are going to do this because this is this is how like there's going to be nothing more important than optimizing the way that you like build and ship software in the future. And so one other thing that is really powerful if you set up everything you just said where it's like you have the you have the tracking you have the eval there's one further way that you can make it even more powerful which is adding the ability to basically take your own data and replay those sessions with different configurations to actually measure like to your question earlier like well how would it have done from a cost perspective or quality perspective. uh if you had done like different models.
</details>

因此，举个例子，同样，这是我们内置在工厂里的东西，但其实有很多方法可以做到这一点。比如，这个想法就是，就像有 SWE-bench 和 Terminal-Bench 这些基于通用数据的公开基准一样，你可以在自己的数据上，根据过去真实的工厂任务重新构建：比如，如果你换用不同的模型配置，情况会是怎样？所以这就像一种帕累托图，这种图在 Twitter 上随处可见，但很酷的是，如果你采用工厂的方法，并且非常科学地对待，好的，我想知道——比方说你想挑选出一堆前端任务，然后看看：我是否可以在这些任务上使用 GLM-5.3 而不是 Opus？是的，当然可以。我应该使用 Gemini 3.7 Flash 吗？质量会受到影响。呃，所以你可以自己在这里进行权衡选择，然后你可以将这些反馈回模型路由策略中，在策略中你实际上拥有证据表明：好的，在你自己的任务中，针对这些类型的，呃，比如在成本和质量上最佳的模型配置就是你所发现的结果。

<details><summary>Original English</summary>
And so for instance, like again this is what we have built into our factories, but there's lots of ways you could do this. Like the the idea is you can just like there these public benchmarks like Sweepbench and Terminal Bench that um are on like generic data. You can recreate on your own data like from real past factory tasks. How would things have gone had you used a different model configuration for instance? So this is like um a kind of paro chart which again these things are on Twitter all the time but it's like what's cool here is like if you take the factory approach and are like really scientific around okay I want to know like like I want to let's say you want to curate a bunch of front-end tasks and then see like can I be using JLM53 on those instead of using you know opus. Yes, definitely. Should I be using Gemini 37 Flash? You're going to take a quality hit. Uh and so like you get to choose your own sort of trade-offs here and then you can feed this back into a model routing strategy where you actually have evidence that okay on your own tasks for these types of uh like the best model configuration for cost and quality is is like whatever you find.
</details>

你是把它与实际发布的内容进行比较吗？比如你们是如何评估质量的？你知道，写 CSS 有无数种方法。比如，在前端任务上，你到底如何确定这是更好的质量还是不好的质量？

<details><summary>Original English</summary>
Are you comparing that to what actually shipped? Like how are you evaluating quality? You know, there's like seven ways to skin a CSS. Like how do you actually decide, you know, this is better quality or or not on frontend tasks, for example?
</details>

>> 是的，问得太好了。我们在更多工厂里采取的方式是——你在这里可能可以采取不同的做法——我们使用与我之前向你展示的完全相同的评分基础设施。比如，你看，我们这里有所有这些不同的评分维度。所以，如果你对这套评分基础设施有信心，基本上你就是在回放过去的任务，并试图观察是否存在、观察它对这些评分产生了怎样的影响。所以它主要是把 LLM 作为裁判，但你也可以——你可以用人类裁判来做，你也可以用算法来做，但我们构建的是 LLM 作为裁判。

<details><summary>Original English</summary>
>> Yeah, awesome question. So the the way that we do it in more factories and you're going to probably you can do different things here is we use the exact same like scoring infrastructure that I showed you earlier. So for instance, you know, we over here we have all these different scoring dimensions. So you can if you have confidence in this scoring infrastructure, basically you're replaying past tasks and trying to see if there was like how it affected these scores. So it's it's it's primarily LLM as a judge, but you can also it's like you you could do this with human judges, you could do it algorithmically, but the thing that we have built is LLM as a judge.
</details>

### 非技术场景与日常应用

>> 明白了。非常有意思。好的。你给了我很多如何进一步拓展工厂理念的想法。我很好奇，暂时摘掉我们作为构建者的帽子、CTO 的帽子。让我们，让我们戴上——我知道，在我们开播之前我又跟你聊过。我说，人们很想看看非技术人员如何做技术性的事情，以及技术人员如何做非技术性的事情。所以，给我们展示一些你其他的 AI 使用案例，也许少一些关于 eval、基准测试和 MCP，多一些关于，你知道，作为一个 CEO 的日常。

<details><summary>Original English</summary>
>> Got it. Super interesting. Okay. So, you've given me so many ideas on how to take the factory idea further. I'm curious just like take off our builder hat, our CTO hat. Let's let's put on I you know, I was talking to you again before we came on. I was like, people love to see how nontechnical people can do technical things and how technical people can do non-technical things. So, show us some of your other like AI use cases that are maybe less about EVELs and benchmarks and and MCPs and more about, you know, being a CEO.
</details>

>> 好的。我们来看看——我想放眼来看。有这些图表固然很酷。我自己在修改 Figma 时依然很费劲。呃，[笑声]而且我不知道你是不是也这样，但当我去尝试修改类似 Figma 里的东西时，我感觉自己像长了三只大拇指一样笨拙。我就完全搞不懂怎么用它。但我确实知道，如果你——比如我们做幻灯片就是这么做的。比如我们使用的是 Figma Slides。你可以做出看起来非常漂亮的东西。所以，我现在做的一件事就是，如果我需要修改一份幻灯片，我会通过 Figma MCP 和编码智能体来完成。所以，只是为了展示一下那是什么样子的，呃，我们这里有关于云端执行的这样一张有点平淡的幻灯片。所以我向你展示我会怎么做，让你有个概念。我准备在——我在 Warp 中做这个。我使用，我使用 Warp 作为编码智能体。这在 Cloud Code 或 Codex，任何具有 Figma MCP 的工具中也同样适用。呃，所以我把这个粘贴进去，然后我准备对它说话，这是另一件事，我猜大家现在都加入语音的潮流了。

<details><summary>Original English</summary>
>> Yeah. So, we'll get like I think like zooming out. This is cool with all these charts. I still have a hard time making changes to Figma. Um, [laughter] and like I I don't know if you're the same way, but when I go to try and change like a like a Figma thing, I'm like it's like I have three thumbs or something. Like I just I cannot figure out how to use it. But I do know that it's like if you like this is this is how we like do our slide decks for instance. It's like we we are using Figma slides. You can make things that look very nice. So, one thing uh that I do now is like if I need to change a slide deck, I do it through the Figma MCP and the coding agent. And so, like just to kind of show what that looks like, um we have this kind of semiboring uh like slide here on cloud execution. So, I'll show you how I would do this just so you get a sense. So, I'm going to do this uh I do this in warp. I use I use warp as a coding agent. This would also work in cloud code or codeex anything that has Figma MCP. Um and so I'll just paste this in and then I'm going to talk to it which is another thing I I assume people are on the voice train.
</details>

>> 是的，我们——呃，我们把这完全归功于 Hillary Gidley。她称之为话痨 API（Yappers API）。与 LLM 交流最高带宽的方式。

<details><summary>Original English</summary>
>> Yeah, we uh we we give all credit to Hillary Gidley. She calls it the Yappers API. Highest big width way to talk to an
</details>

>> LLM。[笑声]

<details><summary>Original English</summary>
>> LLM. [laughter]
</details>

对。所以我要——我要说的是，比如我想为这张幻灯片制作一个新版本。使用 Figma MCP 获取上下文，复制现有的幻灯片，而不是直接在上面做修改。让它变成这样：呃，宿主框包含运行时框。让——让我想想我还有什么。我得切回来看一下。所以，我们要让宿主包含——抱歉，宿主应该包含沙箱。

<details><summary>Original English</summary>
Yeah. So, I'm going to I'm going to say like I'd like to make a new version of this slide. Use the Figma MCP to get the context, duplicate the existing slide rather than making changes directly to it. Let's have it be so that um the host box contains the runtime box. Let's um let me see what else I got. I got to switch back here. So, we're going to have host contain, sorry, host should contain sandbox.
</details>

呃，我回头再编辑这个。让上下文系统变成某种类似、有点像，你知道的，围绕在这些事物周围并注入它们的云彩。

<details><summary>Original English</summary>
Uh, I'll go back and edit this. Let's make the context system something that's like a kind of like, you know, cloud around these things that feeds into them.
</details>

>> 真正的 CEO，当场随手画个云彩[笑声]。

<details><summary>Original English</summary>
>> True CEO, put a cloud [laughter] on the spot.
</details>

>> 呃，你将在这里看到一些糟糕的设计。

<details><summary>Original English</summary>
>> Uh, you're going to see some bad design here.
</details>

让启动板带有一种火箭之类的主题。顺便说一句，这是我——这不是我的销售团队想要的。呃，

<details><summary>Original English</summary>
Let's make the launchpad have a sort of like rocket type theme. This is my This is not what my sales team wants, by the way. Um,
</details>

还有，让追踪——我不知道。你为什么不想出一些让追踪做得更好的点子呢？这里的总体构想是让这张幻灯片在视觉上比简单的五个框更有吸引力，并且在语义上展示各个框彼此之间的关系。

<details><summary>Original English</summary>
and let's make tracking I don't know. Why don't you come up with some ideas for how to make tracking better? The overall idea here is to make this slide more visually appealing um than the simple, you know, five boxes and semantically show the relation of the boxes to each other.
</details>

所以我这样操作。

<details><summary>Original English</summary>
So I'll do this.
</details>

>> 你知道我对 Figma 说的词是什么吗？

<details><summary>Original English</summary>
>> Do you know what word I say to Figma?
</details>

>> 呃

<details><summary>Original English</summary>
>> Uh
</details>

>> 我总是对 Figma MCP 说“语义上如何如何”。天呐。每一次都是。[笑声]

<details><summary>Original English</summary>
>> I say semantically what to Figma MCP all the time. Oh my god. All the time. [laughter]
</details>

>> 语义颜色，语义化。

<details><summary>Original English</summary>
>> Semantic color semantic.
</details>

它是——它是我的“正交”（高频口头禅）。

<details><summary>Original English</summary>
It is it is my orthogonal.
</details>

[笑声]

<details><summary>Original English</summary>
[laughter]
</details>

>> 太好笑了。

<details><summary>Original English</summary>
>> That's really funny.
</details>

是的。我是说，呃

<details><summary>Original English</summary>
Yeah. I mean um
</details>

<!-- chunk 5/6 -->

额，我们再看吧。所以，而且我最近用——我最近经常用 Grok。嗯，

<details><summary>Original English</summary>
uh
we'll
see.
So,
and

I'm
using

I'm
using
Grock
a
lot
recently.
Um,
</details>

>> 我也是。

<details><summary>Original English</summary>
>> same.
</details>

>> 我不知道你的首选模型是什么。我觉得从成本、速度和质量权衡来看，Grok 相当不错。

<details><summary>Original English</summary>
>> I
don't
know
what
your
model
of
choice

is.
I
think
Grock
is
pretty
good
from

like
a
cost
and
speed
and
quality

quality
trade-off.
</details>

>> 我可以给你演示——我还可以做点别的，你知道的。

<details><summary>Original English</summary>
>> I
could
show
you
I
could
do
some
other,

you
know.
</details>

>> 行啊，趁着那边还在加载，你何不再给我们展示点别的？

<details><summary>Original English</summary>
>> Yeah,
why
why
don't
while
that's

loading,
why
don't
you
show
us
something

else?
</details>

>> 好，我再给你看一个。我也是 Granola 的重度用户。所以再次说明，如果我真的想优化这份销售宣讲幻灯片，我想确保的另一件事就是，让这份销售宣讲能够切中客户实际在谈论的内容。所以我现在要用 Granola MCP 启动第二个任务，我在里面说：“你能用 Granola MCP 回顾我过去四周的销售会议，并试着列出这些会议中与 Warp 软件工厂相关的最常被问及的前 10 个问题吗？不要在总结中列出任何具体的客户信息。把它匿名化。额，因为我在录播客。”

<details><summary>Original English</summary>
>> Yeah,
I'll
show
you
another
one.
So,
I'm

a
big
granola
user
as
well.
And
so

again,
if
I
were
really
trying
to

improve
this
sales
deck,
another
thing

that
I
would
want
to
make
sure
is
that

the
sales
deck
is
speaking
to
the
things

that
customers
are
actually
talking

about.
That's
I'm
going to
start
a

second
task
here
using
the
granola
MCP

where
I'm
like,
can
you
use
the
granola

MCP
to
look
back
over
my
last
four
weeks

of
sales
meetings
and
try
to
build
up
a

list
of
the
top
10
frequently
most
asked

questions
in
these
meetings
as
they

pertain
to
Warp
Software
factories.

Don't
list
any
specific
customer
info
in

the
summary.
Anonymize
it.
U
because
I'm

doing
a
podcast.
</details>

>> 那么，我们把这个任务也跑起来。如果你愿意的话，我还可以再来一个。

<details><summary>Original English</summary>
>> So,
we'll
we'll
get
this
one
cooking
as

well.
I
can
do
one
more
if
you
want.
</details>

>> 好啊，我是说，咱们继续排队加上去。我特别喜欢看一个“深谙 AI 之道”的 CEO 连开一个又一个标签页，把各种事情不断分发下去。

<details><summary>Original English</summary>
>> Yeah,
let's
I
mean,
let's
queue
them
up

again.
I
love
to
see
a
AI
pill
CEO
just

open
tab
after
tab
after
tab
and
kick

stuff
off.
</details>

>> 我是说，这些都是——这些都是顺便提一句，全部都是我平时一直在用 AI 做的真实事情。最后一个任务就像是，我用来重新发掘潜在的非活跃潜在客户的任务，这些客户可能是我在过去大约六个月左右聊过的。你知道我们的产品发生了极大的变化。我可能想重新接触他们。所以，我用来——我用来做这个或者说过去一直在用的是，其实刚开始用 instinct。你用 instinct 吗？

<details><summary>Original English</summary>
>> I
mean,
this
is
stuff
that
this
is

stuff.
These
are
all
by
the
way
real

things
that
I
am
constantly
using
AI

for.
So
the
last
one
is
like
uh
a
task

that
I
use
AI
for
is
trying
to

rediscover

uh
potentially
like
cold
leads
that
I

might
have
talked
to
in
the
last
um
like

you
know
six
months
or
so.
You
know
our

product
has
changed
a
crazy
amount.
I

might
want
to
reproach
them.
And
so
the

thing
that
I

I
use
for
this
or
had
in
the
past
been

using
for
this
actually
just
started

using
instinct.
You
use
instinct?
</details>

>> 噢没有。我之前用 instinct 的体验不太好。

<details><summary>Original English</summary>
>> Oh
no.
I
had
a
bad
experience
with

instinct.
</details>

>> 你有过不太好的体验。所以我通常做所有事情的正常方式依然是通过我的——依然是通过 coding agent。不过我先——咱们我在这里再写一条提示词。“你能用 GOG CLI 查找过去六个月里我与潜在企业客户通过的邮件和日历日程吗？这些客户可能适合针对 Warp Factories 进行再次触达。你可以在 warp.devfactories devfactories 了解 Warp Factories，并为我制作一个包含他们信息的 Google 表格，分享该表格链接，但不要在这个对话串里打印出任何具体的客户邮箱或姓名。”

<details><summary>Original English</summary>
>> You
had
a
bad
experience
in
so
the
the

the
normal
way
I
would
do
everything
is

still
through
my
is
still
through
coding

agent.
But
I
would
um
let's
let's
I'll

do
one
more
prompt
here.
Can
you
use
the

GOG
CLI
to
look
for

emails
and
calendar
events
I've
had
in

the
past
six
months
with
potential

enterprise
leads
who
might
be
um
useful

for
another
outreach
for
Warp
Factories.

You
can
learn
about
Warp
Factories
at
uh

warp.devfactories
devfactories

and
make
me
a

Google
sheet
with
the
info
on
them
and

share
the
sheet
link,
but
don't
print

out
any
specific
customer
email
or
name

in
this
thread.
</details>

>> 我从元层面喜欢这一点的是，你的大脑也是这样运转的吗？就像“我需要做这张幻灯片，派发幻灯片任务；我需要更新一些销售定位，把那个派发出去；我需要跟进非活跃潜在客户”。当你——

<details><summary>Original English</summary>
>> What
I
like
about
this
at
the
meta
level

is
like
is
this
how
your
brain
works

where
you're
just
like
I
need
to
do
the

slide,
kick
off
the
slide.
I
need
to

like
update
some
of
our
sales
position,

kick
that
off.
I
need
to
like
follow
up

with
cold
leads.
Like
is
this
when
you

panel
</details>

>> 这反映了你作为 CEO 的大脑吗？因为这绝对反映了我的大脑。

<details><summary>Original English</summary>
>> is
this
a
reflection
of
your
CEO
brain?

Because
it's
certainly
a
reflection
of

my
brain.
</details>

>> 是的。我是说，如果我处在销售模式下，是的，去市场模式，而我现在相当多时间处于这种模式，遗憾的是比起纯粹的构建者模式或管理者模式还要多。尽管这些不同的事情我都会做。我总是在试图寻找正确的定位是什么？我们在这些会议中的沟通方式是否能打动人？对于我这个完全不会设计或画画的人来说，能够拥有这种能力，拥有现在这种超能力，真是太不可思议了。我们去——咱们看看这边 Figma 做得怎么样了。它开始做了吗？额——

<details><summary>Original English</summary>
>> Yeah.
I
mean,
if
I
were
if
I
were
in

like

sales
mode,
Yeah.
go
to
market
mode
and

like
I
am
in
that
mode
quite
a
bit
now

unfortunately
more
more
so
than
like

straight
up
builder
mode
or
manager

mode.
Although
I
do
all
these
different

things.
I'm
constantly
trying
to
find

like
what
is
the
right
positioning?
Are

we
are
we
communicating

um
in
these
meetings
in
a
way
that
lands

and
like
it's
so
amazing
to
have
a
this

ability
like
for
me
who
can't
design
or

draw
at
all
or
like
to
have
this
now

superpower
and
we
can
go
let's
let's
see

how
this
Figma
is
doing
over
here.
Has

it
started
to
do
it
yet?
Uh
</details>

>> 噢，开始动了。

<details><summary>Original English</summary>
>> oh,
it's
starting.
</details>

>> 噢，它还有不少工作要做。不过它会越做越好的。不过是的，如果我处于销售模式，就像我正试图弄明白我们定位对不对？大家在问些什么？嗯，是的，而且这是对的，这是来自我们实际销售通话的内容，而且就工厂——也就是我们所处的这个产品类别而言，我认为排在第一位的问题就是自购还是自建，并且这有事实依据支撑，在我看来也是合理的。嗯，安全问题被频繁提及。嗯，工作流，工作流是怎样的？衡量标准是什么？我们如何管理成本？这太酷了。所以我要做的就是，比如我想接下来去确保我们的销售宣讲、我们的网站，所有这些内容都在回应人们所关心的问题。我可能会把这些整理成一份名副其实的 FAQ。我觉得我们可能具备改进这一点的能力，或者我们直接尝试将此融入到我们的定位中。但是，额，我一直在做这件事，一直在试图理解我们正在构建的东西是否正确，以及我们是否以正确的方式对其进行定位。

<details><summary>Original English</summary>
>> Oh,
it's
got
some
work
to
do.
But
it
it

will
it
will
do
better.
But
yeah,
if
I

was
in
sales
mode,
like
I'm
trying
to

figure
out
are
we
positioning
it
right?

What
are
people
asking
about?
Um

yeah,
and
this
is
this
is
right
like

this
is
from
our
actual
sales
calls
and

like
this
is
the
what
I
would
say
is
the

number
one
thing
for
the
factory
like

the
product
category
we're
in
is
like

buy
versus
build
and
it's
backed
up
by

evidence
and
it
makes
sense
to
me.
Um

security
comes
up
a
lot.
Um
workflow,

what's
the
workflow?
What's
the

measurement?

How
do
we
manage
costs?
It's
so
cool.

And
so
it's
like
what
I
would
do
is

like,
you
know,
I
want
to
then
go
make

sure
that
our
our
sales
deck,
our

website,

all
this
stuff
is
speaking
to
the

questions
people
have.
I
I
might
turn

this
into
like
a
literal
FAQ.
Like
I

think
we
we
have,
you
know,
probably

ability
to
improve
that
or
I
we
just
try

and
work
this
into
our
positioning.
But,

uh,
I'm
constantly
doing
this
and
trying

to
understand
if
if
what
we're
building

is
the
right
thing
and
we're
positioning

it
the
right
way.
</details>

>> 我们弄出了个火箭。抱歉，对于没在看画面的观众，我们切回了 Figma。我们得到了一个火箭飞船，得到了一团某种云朵。它正在努力尝试，不会一直这样，它会变好的。

<details><summary>Original English</summary>
>> We
got
a
rocket
ship.
Sorry,
we're
back

at
Figma
for
those
that
are
not

watching.
We
got
a
rocket
ship.
We
got
a

cloud
of
some
sort.
It's
trying
not.
It

will
get
better.
</details>

>> 火箭画得不算差。

<details><summary>Original English</summary>
>> The
rocket
ship's
not
terrible.
</details>

>> 还不错。嗯，Zach，这太有意思了。我想进入简短的快问快答环节，然后我们就放你回——

<details><summary>Original English</summary>
>> That's
not
bad.
Um,
Zach,
this
is
this

is
so
fun.
I
want
to
go
to
quick

lightning
round
questions
and
then
we'll

get
you
back
to
</details>

>> 好的。

<details><summary>Original English</summary>
>> cool
</details>

### 快问快答与研发管理

>> 回到工厂车间去。好了，第一个快问快答。大家都想要软件工厂，大家都想要一个乐意去翻通话记录的 GTM 实习生，以及一个乐意替 CEO 做那些难看的云朵幻灯片的设计实习生。但当你的工厂高速运转起来，当你们上个月完成了——我想大概是超过 2000 个 PR 的时候，你如何让团队内部不至于像我所说的那样陷入混乱？你如何全面掌控所有这些活动、所有这些工作、所有这些上下文、所有这些任务，并且在最高层面清楚自己做的是重要的事情？这是一个极好的问题。那种比较平淡无奇的回答是，我们作为软件工程师历来所做的很多事情仍然适用，也就是我们一直在做内部试用（dogfooding）。所以我们就是我们所构建产品的重度且持续的用户，确保这个东西的品质依然能良好运转。这里面发生着很棒的知识传递，我不知道你是否也注意到了这一点，但在这些工具的使用方式上存在着一种幂律分布，就我们团队而言，有些成员是超级、超级深度的重度用户，而另一些人则相对更接近平均水平。因此，当你以这种在外部看来非常混乱的方式公开工作，所有人整天都在 Slack 里呼叫这些工厂时，你确实有机会看到那些真正精通的专家是如何使用它的，这在一定程度上提升了团队中其他人的水平。另外就像我之前说的，我们依然在执行——你知道，这并不只是混乱到所有人整天不停把垃圾东西塞进机器里。我们依然拥有一个在很多方面都算比较传统的产品研发流程。所以我们要做大量的用户访谈，观察人们使用产品。我们在开始构建之前会进行设计头脑风暴（design jams），目的倒不主要是为了精确搞清 UI 应该长什么样，而是为了确保我们解决的是正确的用户故事。因为归根结底，你构建软件有多快并不重要，它仍然必须解决用户的某个问题，并且是以良好的方式去解决。所以我们正试图弄清楚如何既不丢失这里面人类投入的关键部分，但同时又能利用这种神奇技术可以让你快得多的事实。

<details><summary>Original English</summary>
>> back
on
the
factory
floor.
All
right,

first
lightning
round
question.

Everybody
wants
the
factory.
Everybody

wants
the
go
to
market
intern
that
will

happily
go
through
your
call
transcripts

and
the
design
intern
that
will
happily

make
your
ugly
cloud
slides
as
a
CEO.

But
when
you
have
the
factory
humming

and
when
you're
doing
I
think
it
was

like
over
2,000
PRs
in
the
last
month

like
how
do
you
keep
things
in
the
team

from
going
as
I
say
like
chaos
reigns

like
how
do
you
keep
your
arms
around

all
that
activity
all
that
work
all
that

context
all
those
tasks
um
and
know
at

the
highest
level
you're
doing
the

things
that
matter?
It's
a
great

question.
Um,
like
the
kind
of
boring

answer
is
like
a
lot
of
the
stuff
that

we've
always
done
as
software
engineers

still
applies,
which
is
like,

you
know,
we're
we're
dog
fooding.
So,

we're
just
like
huge
constant
users
of

the
thing
that
we're
building
and
making

sure
that
like
the
quality
of
the
thing

still
works
well.
Um
there's
like
cool

knowledge
transfer
that's
happening
uh

where
it's
I
don't
know if
you've
seen

this
too,
but
like
the
this
there's
like

a
kind
of
power
law
for
like
how
these

tools
are
used
in
terms
of
like
we
have

some
people
on
our
team
are
super
duper

power
users
and
other
people
are
like

kind
of
more
at
the
average.
And
so

there's
this
um
when
you
when
you're

working
in
this
what
seems
like
a
very

chaotic
way
in
public
with
everyone

slacking
these
factories
all
day,
you
do

get
a
chance
to
sort
of
see
how
like
the

the
really
expert
people
are
using
it

and
that
kind
of
uplevels
other
people

on
the
team.
And
then
like
I
said

earlier,
we're
still
doing

you
know
it's
not
just
like
chaos
like

everyone
like
you
know
slop
stuff
into

the
machine
all
the
time.
It's
like
we

still
have
a
product
development
process

that
uh
you
know
is
somewhat
traditional

in
a
bunch
of
ways.
So
it's
like
we
do
a

whole
bunch
of
user
interviews.
We
watch

people
use
the
product.
Um
we
do
design

jams
before
we
start
building
to
not
not

so
much
like
figure
out
exactly
like
how

the
UI
should
look,
but
just
to
make

sure
that
we're
tackling
the
right
user

stories.
uh
like
because
at
the
end
of

the
day
like
doesn't
matter
how
fast
you

build
software.
It's
like
it
still
has

to
solve
some
user
problem
and
solve
it

in
a
good
way.
And
so
we
we're
we're

trying
to
figure
out
how
to
like
not

lose
the
key
parts
of
like
the
human

input
here,
but
also
you
know
use
use

the
fact
that
there's
this
like
magic

technology
to

that
can
make
you
just
go
much
faster.
</details>

>> 我太喜欢这个回答了，完全赞同，我没法说得更好了。嗯，好，最后一个问题，然后我们就不耽误你了。当你的 AI 没有按照你的意图去做时——而且我也很好奇，当私下单独使用 AI 时，与在 Slack 里公开使用 AI 时，面对它不按你意图办事的情况，你的回答会有所不同吗？你的提示词策略是什么？你会吼它吗？

我最近——我向观众承认这一点——我经常会发问：“你为什么会这样？为什么？为什么？”提很多疑问。

挺有意思的。嗯，我算是一个情绪相当平稳的人。我觉得如果你去问我团队里的人，我从来不会——大吼大叫不是我的风格。嗯，我表现得更偏向——可以说是阴阳怪气，冷嘲热讽吧。［笑声］我会——我会忍不住翻白眼，心想“真的吗，就这……”

<details><summary>Original English</summary>
>> I
love
it.
I
amen.
I
could
not
say
it

better.
Um
okay,
last
question
and
then

we
will
get
you
out
of
here.
when

your
AI
is
not
doing
what
you
want.
And

and
also
I
I'm
curious
if
this
question

is
if
you
answer
this
question

differently
when
you're
working
with
AI

privately
versus
working
in
with
it
in

Slack
when
it's
not
doing
what
you
want.

What's
your
prompting
strategy?

Do
you
yell?

I
am
lately,
I
will
admit
this
to
the

audience,
I
am
doing
a
lot
of
like
why

are
why
are
you
like
this?
Why?
Why?
A

lot
of
questioning.
That's
funny.
Um,

I'm
like
a
pretty
level
guy.
I
like
if
I

think
if
you
ask
the
people
on
my
team,

I
don't
I've
never
like
yelling
not
my

style.
Um,
I
get
like

passive
aggressive
is
kind
of
what
I

would
say.
[laughter]

I
I
get
I
I
get
like
eye
rolly
like

really
like
this
is
</details>

<!-- chunk 6/6 -->

现在在干什么。比如你把这整套东西都做出来了，但根本没人让你去做。所以，我会有一些隐隐的恼火，但我不是那种会大喊大叫的人。所以，我不知道。我也试着保持这样一种视角：这其实是一件非常疯狂的事情，我居然在跟这样一个东西对话，而它正在做的工作是我过去这20年里一直在做的事，而且它现在可以说做得比我都好了。所以，我不知道。我仍然处在一种对它感到有些惊奇的阶段。我不知道你有没有看过路易·C·K（Louis C.K.）的那个小品，他在里面讲到当年互联网、也就是Wi-Fi刚引入飞机上时候的情景。如果你知道这个你就打断我，大意是他当时像个小孩子一样坐在一架飞机上，差不多是20年前的事了，飞机上第一次有了Wi-Fi——

<details><summary>Original English</summary>
what we're doing now. Like you built this whole thing that no one asked you to build. So, I'll get like annoyed like in like subtle undertones, but I I'm not a I'm not a yeller. And so, uh I don't know. And I also try to just keep the perspective that this is just like a bonkers thing that I'm just like talking to this uh talking to this thing that is doing this job that I've done for the last 20 years and it's now it's like doing it kind of better than me. And so, I don't know. I'm still in like I'm in like a little bit of like a wonder phase with it. Um I don't know if you've ever seen that. um Louis CK skit where he he talks about um how when internet like Wi-Fi first got onto airplanes. Stop me if you know this, but it's like he it's a kid. He's like he's riding on an airplane. It's like this like 20 years ago and there's Wi-Fi for the first time
</details>

>> 然后他就觉得这太不可思议了，大家……这太神奇了，结果却没人感到开心。他讲了个故事，说坐在他旁边的那个家伙试着看一段 YouTube 视频，然后摊开双手抱怨说“去他的，我根本连不上信号”，而路易·C·K 的反应则是“这太离谱了，我们可是在飞机上啊，这信号是直通太空的，稍微给它点时间嘛”。所以，[笑声] 我觉得人们太容易忽视这项技术到底有多不可思议了。我个人总体上来说，对它可能比大多数人都要更有耐心一些吧。

<details><summary>Original English</summary>
>> and he's just like this is incredible. Everyone like this is like amazing and nobody's happy. And he tells a story about how like the guy next to him is like trying to watch a YouTube video and like throwing his hands up like screw this like I can't get any signal and and Louis CK is like like this is bonkers. Like we're on an airplane. This thing is like going up to space. Give it a second. And so [laughter] I think it's it's so easy to lose perspective of like how wild this technology is. Like I'm I'm like I'm I'm generally like pretty probably like kind of more patient with it than most I would say.
</details>

>> 太棒了，这个视角非常好。好了，Zach，今天聊得非常开心。大家可以在哪里找到你？我又有什么能帮到你的吗？

<details><summary>Original English</summary>
>> I love it. That's such a great perspective. Well, Zach, this has been super fun. Where can we find you and how can I be helpful to you?
</details>

>> 嗯，大家想找到我个人的话，我在 Twitter 上，我的 Twitter 账号是 Zack Lloyd Tweets。当然也欢迎大家访问 warp.dev 了解 Warp。如果你想构建软件工厂，虽然我刚才基本都没怎么提及，但我们有一款非常受欢迎的开 agents 终端工具，它也是开源的，大家也一定要去看看并使用它。那是与交互式编程智能体协作的极佳去处。不过话说回来，今天真的很棒，非常感谢你能邀请我来。

<details><summary>Original English</summary>
>> Um, so you can find me personally like I'm on I'm on Twitter. I have Zack Lloyd Tweets is my is my Twitter. You should obviously come check out Warp at warp.dev. Um, if you want to build software factories, you know, I hardly even talked about it, but we have an extremely popular uh agentic terminal uh that's open source that you should also come check out and use. It's a great place to work with interactive coding agents. Um, but yeah, this was awesome. I really appreciate you having me on.
</details>

>> 好的，感谢加入 How AI。非常感谢大家的收看。如果你喜欢这期节目，请在 YouTube 上点赞并订阅，或者更好的是，给我们留言分享你的想法。你也可以在 Apple Podcasts、Spotify 或你喜爱的播客应用中收听本播客。请考虑给我们评分和评论，这将有助于其他人发现这个节目。你可以在 howiaipod.com 查看我们所有的剧集并了解更多节目详情。我们下期再见。

<details><summary>Original English</summary>
>> Yeah, thanks for joining How AI. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.
</details>