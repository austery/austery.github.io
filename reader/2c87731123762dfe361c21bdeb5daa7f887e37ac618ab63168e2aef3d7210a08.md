---
author: The Pragmatic Engineer
date: '2026-10-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=mQu0zN4IvSI
speaker: The Pragmatic Engineer
tags:
  - code-refactoring
  - software-engineering
  - cs-education
  - ai-impact
  - developer-productivity
title: Titus Winters 谈 Google 代码重构、AI 时代软件工程与 CS 教育变革
summary: Titus Winters 指出 Google 曾进行人类史上最大规模 C++ 重构，并认为 AI 时代 CS 课程需转向软件工程实践，强调领域深度而非纯代码技能。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people:
  - Titus Winters
companies_orgs:
  - Google
  - Uber
  - Linear
products_models:
  - Test Manager
  - Linear
media_books:
  - Software Engineering at Google
  - Psychology of Software Teams
status: evergreen
---
<!-- chunk 1/13 -->

那大概是人类历史上规模最大的一次重构任务。那可是两亿或两亿五千万行 C++ 代码，其中有两亿五千万行是第一方代码，还不算外部依赖项；而且当时一个月内大概有一万名工程师在对那个代码库进行修改。什么是可读性审查？我离开 Google 时，算是可读性项目的总体负责人。那可能是科技界最大的教育项目了，因为在任何特定时刻都有数以万计的人参与其中。计算机科学的大部分课程自 2000 年以来就没有实质性的变化，甚至可能更早。课程里的大多数内容，恰好是 90 年代构建数据库或操作系统所需的东西。

<details><summary>Original English</summary>That was probably the largest refactoring task in human history. It was 200 or 250 million lines of C++ code with 250 million lines of first-party, not counting external dependencies, and 10,000 engineers probably at the time making edits to that code base in a month. What is readability review? When I left Google, I was kind of the overarching owner for the readability program. That might be the largest educational program in tech cuz there were tens of thousands of people participating in that at any given moment. Most of the CS curriculum hasn't substantially changed since 2000, maybe earlier. The average thing in the curriculum is exactly what was needed to build a database or an operating system in the '90s.</details>

>> 这听起来可不太妙，不是吗？

<details><summary>Original English</summary>>> That doesn't sound good, does it?</details>

>> 对于一个以创新为荣的领域来说，确实不妙。我大力推动的一点是，我们需要跳出纯代码的层面。我们需要进行实质性的提升。计算机科学的入学人数将会暴跌，但软件工程专业将会兴起，因为实话实说，在 AI 时代真正重要且依然能让你找到工作的东西是——

<details><summary>Original English</summary>>> Not for a field that prides itself on innovation. A lot of what I'm pushing for is we need to get out of the code. We need to up-level substantially. CS enrollment is going to plummet, but software engineering programs are going to kick up because, let's be honest, the stuff that's going to matter in a AI era and still get a job is</details>

### 访谈介绍

>> 如果一位协助制定了当今软件工程课程内容的工程师说，这里面的大部分内容都该被推倒重来，会怎么样？一位真正的软件工程师正是这么说的。2023 年，Titus Winters 是 ACM 和 IEEE 本科计算机科学课程指导委员会中唯一的现职软件工程师。此前，他在 Google 工作了 10 多年，是《Google 软件工程》一书的主作者，并掌管着该公司的可读性项目。在今天的对话中，我们将讨论为什么 Google 在 2006 年左右创建了 Test Manager（测试管理器）——当时其旗舰搜索产品由于持续出现的回归问题而无法再保持常规节奏发布；衡量开发者生产力的方法，以及为什么 AI 的价值没有体现在我们今天所衡量的指标中；Titus 会如何改变计算机科学教育，包括他为什么希望根据学生的提示词和测试而不是代码来打分；以及更多内容。

<details><summary>Original English</summary>>> What if an engineer who helped define the contents of today's software engineering curriculum said that most of this should be burnt down? An actual software engineer says exactly this. In 2023, Titus Winters was the only active software engineer on the steering committee for the ACM and IEEE undergraduate CS curriculum. Before, he spent more than 10 years at Google, was the lead author of the book Software Engineering at Google, and ran the company's readability program. In today's conversation, we discuss why Google made Test Manager around 2006 after the flagship search product could no longer be released on a regular cadence due to persistent regressions. Ways to measure developer productivity and why the value of AI does not show up in the metrics that we measure today. Ways that Titus would change computer science education, including why he'd want students to be graded on their prompts and tests, not the code. And more.</details>

如果你想了解 Google 在规模化工程方面的经验教训，或者想知道在 AI 时代现代计算机科学教育应该是什么样，本期节目正是为你准备的。

<details><summary>Original English</summary>If you want to know what Google learned about engineering at scale or how modern computer science education should look like in the age of AI, this episode is for you.</details>

本期节目由 Turbo Buffer 赞助播出，基于对象存储构建的向量与全文检索工具。它快速、便宜，且极具扩展性。

<details><summary>Original English</summary>This episode is presented by Turbo Buffer, vector and full text search built on object storage. It's fast, cheap, and extremely scalable.</details>

在我们开始之前，我想聊聊我们本季的赞助商 Linear。

<details><summary>Original English</summary>Before we start, I'd like to talk about Linear, our season sponsor.</details>

直到最近，我都一直把 Linear 看作是一个帮助规划和组织工作的工具，但它远不止于此。许多团队使用 Linear 来交付从想法到在 GitHub 中合并的修改，全程都无需离开该工具。

<details><summary>Original English</summary>Until recently, I was thinking of Linear as a tool that helps plan and organize the work, but it's much more than that. A lot of teams use Linear to ship changes from idea to merge in GitHub, all without leaving the tool.</details>

我和 Linear 团队的工程师 Dima 坐下来聊了聊，看看 Linear 内部的开发者是如何使用 Linear 来构建 Linear 的全部功能的。这里有一个真实的问题：当你提交包含未发送草稿评论的审查时，Linear 会就这些评论向你发出警告，但它不会告诉你那些草稿在哪里。有一位客户抱怨了这一点，于是 Dima 决定修复它。

<details><summary>Original English</summary>I sat down with Dima, an engineer on Linear team, to see how devs inside of Linear use Linear to build all of Linear. So, here's a real issue. When you submit a review with unsent draft comments, Linear warns you about these comments, but it doesn't tell you where those drafts are. A customer complained and Dima decided to fix it.</details>

在修复之前，Dima 并没有打开他的 IDE。相反，他打开了 Linear 并向 Agent 描述了这个议题。Agent 构建了修复方案，创建了 PR，并附上了 Storybook 截图以便于验证。你可以看到这个修复，屏幕截图上链接着草稿评论。

<details><summary>Original English</summary>Before the fix, Dima did not open his IDE. Instead, he opened up Linear and described the issue to the agent. The agent built a fix, created a PR, and attached Storybook screenshots for easy verification. You can see the fix with the draft comments linked on the screenshot.</details>

在 PR 中有一个 Vercel 预览。你可以从 Linear 一键打开预览来体验这项修改，我们看到它成功生效了。

<details><summary>Original English</summary>In the PR, there's a Vercel preview. You can open the preview with one click from Linear to play around with the change, and we see that it worked.</details>

接下来是我最喜欢的部分，引导式审查（guided reviews），目前还是一项正在进行中的功能。引导式审查是一种全新的代码审查体验，其中重要内容会直接凸显出来。审查的顶部包含了修改的摘要和图表。并且 Pull Request 被分成了不同的章节，引导你了解做了哪些更改。

<details><summary>Original English</summary>And here's my favorite part, guided reviews, which is work in progress. Guided reviews is a new code review experience where the important stuff just pops out. The top of the review has a summary and diagram of the change. And the pull request is divided into chapters that walk you through what's changed.</details>

这些区块以一种更容易理解和审查的方式高亮显示了重要更改。哦，当 Dima 完成这一切后，他直接自行批准了代码，代码就合并到了 GitHub 中，全程都没有离开 Linear。如果你只能记住其中的一点，那就是 Linear 不再仅仅是一个用于规划工单和组织工作的地方。它是所有工作发生的地方：创建 issue、启动 agent、查看预览、进行审查以及合并到生产环境。Linear 是面向团队和面向 AI agent 的产品开发系统，我非常喜欢这种演进。

<details><summary>Original English</summary>These blocks highlight the important changes in a way that's easier to understand and review. Oh, and when Dima's finished with all of this, he just self-approved the code and it's merged into GitHub, all without leaving Linear. If you take one thing away from this, Linear is no longer just a place for planning tickets and organizing the work. It's where all the work happens, creating the issue, kicking off the agent, checking out the preview, doing the review, and merging to production. Linear is the product development system for teams and for AI agents, and I'm loving this evolution.</details>

欢迎访问 linear.app/pragmatic 了解详情并获取 6 个月的试用期。

<details><summary>Original English</summary>Check it out and get a 6-month trial at linear.app/pragmatic.</details>

### 早年经历与求学

Titus，欢迎来到播客。

<details><summary>Original English</summary>Titus, welcome to the podcast.</details>

>> 非常感谢你邀请我。

<details><summary>Original English</summary>>> Thank you so much for having me.</details>

>> 能做这期节目我太兴奋了。能……能再次当面录制真是太棒了。

<details><summary>Original English</summary>>> I'm so excited to have this one. It's It's awesome to to to do this in person again.</details>

>> 是的。对，很高兴能来。

<details><summary>Original English</summary>>> Yes. Yeah, it's a joy.</details>

>> 那么，你是怎么进入科技领域的？在……在成长过程中，你就知道自己要从事与计算机相关的工作吗？

<details><summary>Original English</summary>So, how did you get into tech? Did did growing up did you know that you're going to do something with computers?</details>

>> 我是说，我最早的记忆是以为自己会长大成为一名科学家，但你知道，作为一个三岁小孩，那意味着像白大褂、试管以及我不知道还有什么之类的，对吧？我父亲呃非常富有洞察力地知道计算机将会很重要。其实那根本不是他的领域。他大概是做木工和舞台布景设计之类的事情。所以，家里总有一台电脑。通常都是低端配置，也就是你知道的，无论我们能东拼西凑买得起什么样的东西。

<details><summary>Original English</summary>>> I mean my earliest memories I thought I was going to be a scientist, but like you know as a three-year-old that means like lab coats and test tubes and I don't know what else, right? My dad uh very insightfully knew that computers would be important. Like that was not his field at all. He was kind of in carpentry and set design things like that. So, there was always a computer in the house. It was usually kind of a low-end thing of you know whatever we could scrape together and afford.</details>

呃然后我记得我真正起步——我想大概是在 11 或 12 岁左右，有一年情人节他没有给大家买糖果，而是去了书店，我不知道我弟弟买了什么，但我得到了一本学习 QBasic 的书。从那之后一切就顺理成章地发展下去了。大概接下来的五、六年里我都沉浸在编程中，自学编程成了我的爱好。偶尔我最终会比如遇到，你知道，其他跟我同龄且对此稍微有点兴趣的孩子。我们后来搬到了拉斯维加斯，我去了一所设有计算机科学项目的磁校。

<details><summary>Original English</summary>Uh and then I remember I really got my start I think I was around 11 or 12 and instead of buying candy for everyone for Valentine's one year he went to the bookstore and I don't know what my brother got, but I got a book on learn QBasic. And it was all kind of downhill from there. Like I spent probably the next five, six years like programming, teaching myself to program was my hobby. Occasionally I would wind up like meeting, you know, other kids my age that were a little into it. We moved eventually to Las Vegas and I went to a magnet school that had a computer science program.</details>

嗯那其实如今是一所评价很高的公立高中。当时我根本不知道。对，最初完全就像是自学的，呃在互联网时代之前，当时你真的得去费力摸索。

<details><summary>Original English</summary>Um that is actually a really well-regarded high school these days. I had no idea. And yeah, like just kind of self-taught initially uh pre-internet back when you had to really fight for it.</details>

嗯不过对，就是那本书让我走上了这条道路。在那之后，高中毕业后你去大学读这个专业基本上是顺理成章的了。

<details><summary>Original English</summary>Um but yeah, that that set me on my path, that book. And then you after high school it was kind of obvious you went to college for it.</details>

>> 对。

<details><summary>Original English</summary>>> Yeah.</details>

呃所以我去了哈维穆德学院，呃那是一所很棒的学校，融合了，你知道的，科技和博雅教育。

<details><summary>Original English</summary>Uh so I went to Harvey Mudd uh which is a great school with a mix of, you know, tech and liberal arts education.</details>

嗯就是那种会教你制造武器，也会教你不要使用武器的地方，诸如此类。然后我在那里认识了我的妻子，呃她当时比我低一点年级，所以我不想搬到很远的地方。她还在上学，所以我在加州大学河滨分校攻读了硕士学位，实际上研究的是计算机科学教育。

<details><summary>Original English</summary>Um the kind of place that'll teach you to build weapons and teach you to not to use them, that sort of thing. And then I met my wife uh there and she was a little bit more junior than I was, so I didn't want to move away. She was still in school, so I did my master's at UC Riverside actually in computer science education.</details>

>> 嗯。

<details><summary>Original English</summary>>> Mhm.</details>

>> 嗯。

<details><summary>Original English</summary>>> Um</details>

>> 好的。

<details><summary>Original English</summary>>> All righty.</details>

>> 我经历了一种有点奇怪——我的研究生经历非常奇特，是的，我在河滨分校花了四年时间攻读计算机科学教育方向的博士学位，也就是应用 AI、教育数据挖掘、计算机科学教育。嗯——

<details><summary>Original English</summary>>> I did a kind of weird I had a very strange graduate experience, yeah, I spent four years at Riverside doing a PhD in CS Ed, kind of applied AI, educational data mining, computer science education. Um</details>

所以，在计算机科学教育研究最早的一些学术会议上，我在那里发表了论文。而我的——呃我的导师是系主任。他通常一般不带研究生，也就是说研究领域不是他的工作重点，但他一直担任系主任。他就是那种很有魅力、你知道的、擅长社交、懂政治手腕的人，知晓所有的故事背景。

<details><summary>Original English</summary>So, some of the earliest conferences on CS Ed research, I published there. And my uh my advisor was the department chair. He never generally ran grad students, like the research area was not his focus, but he was constantly the chair. He was this like charming, you know, social, political sort of guy that knew all the stories.</details>

因此，我的研究生阶段学业很大程度上就是去了解我们是如何走到今天的所有故事，并且每当有空缺时就去教授所有的课程，呃每当有空缺的时候在——

<details><summary>Original English</summary>And so, my graduate work was a lot of learn all of the stories of how we got here and teach all of the classes uh whenever there was a hole in the</details>

>> 是的，而且——而且我们在整场对话中可能会不断回到这个比如关于计算机科学教育的话题上。所以，这很——我们之前聊过，所以我知道。不过，让我们——让我们先跳到接下来的事情，比如你——你——你现在从大学毕业了。你当时在找工作。

<details><summary>Original English</summary>>> Yeah, and and we'll we'll we'll keep coming back to probably this like this education computer science thing throughout this thing. So, it's a we we've talked before, so I know. But, let's let's jump next like you you you now graduated from college. You were looking for a job.</details>

>> 没错。

<details><summary>Original English</summary>>> Yep.</details>

>> 你——你找到了什么？

<details><summary>Original English</summary>>> What What did you find?</details>

>> 呃所以，首先我加入了一家咨询类的团队。同样，面临着双职工问题（two-body problem）。我妻子去了圣地亚哥读研究生。我拿到博士学位后没有获得教授职位。所以，我就做了这些咨询工作。我在一家小型初创咨询团队工作，大概 30 到 50 人。我主要间接为 DirecTV 工作，负责机顶盒上的嵌入式系统相关事务。

<details><summary>Original English</summary>>> Uh so, first I did a sort of consulting group. Again, two-body problem. My wife went to grad school in San Diego. I did not get a professorship after my PhD. So, I did this consulting stuff. I was at a small startup consulting group, about 30-50 people. Mostly, I worked for indirectly for DirecTV during the embedded system stuff on the set-top boxes.</details>

>> 嗯。

<details><summary>Original English</summary>>> Mhm.</details>

>> 然后，在做了四年之后，呃我们都从研究生院毕业了，所有那些事情都告一段落。我接受了去 Google 面试的机会。呃拿到了录用通知。呃决定不去湾区。他们把我们安排到了纽约。所以，从那以后我们就一直留在这里。

<details><summary>Original English</summary>>> And then, after four years of that, uh we were done with grad schools, we were done with all of that. I took the offer to do Google interview. Uh got the offer. Uh decided not to go to the Bay Area. And they moved us to New York. So, we've been here ever since.</details>

>> 所以，这正是 Google 在纽约这里开设办公室的时候。

<details><summary>Original English</summary>>> So, this is when the Google was opening an office here in New York.</details>

>> 那间办公室其实当时已经开了

<details><summary>Original English</summary>>> And that office was already open</details>

<!-- chunk 2/13 -->

而且规模相当大。那是在2010年，我想当时那里已经有几千人了。

<details><summary>Original English</summary>

 and

reasonably

 big.

 This

 was

 2010.

 So,

 I

think

 there

 were

 a

 few

 thousand

 people

there.

</details>

>> 然后在2010年，Google是98年创立的，2004年上市。我记得大概在2005年到2010年左右，他们开始真正积累起全球知名度，大家都觉得“哇，Google是个工作的好去处”。所以正好在你申请的时候，它其实是最难进的地方之一。有点像今天的Anthropic，或者去年的OpenAI，或者你知道的，像2010年代中期的Uber。

<details><summary>Original English</summary>

>> And

 then

 and

 in

 2010,

 so

 Google

 was

founded

 in

 in

 '98.

 They

 went

 public

 in

2004.

 I

 I

 remember

 that

 they

 started

 to

really

 accumulate

 a

 global

 brand

 as

like,

 "Wow,

 Google

 is

 the

 place

 to

 work

at

 around

 like

 2005

 to

 2010.

 So,

 right

around

 when

 you

 were

 applying,

 it

 was

actually

 one

 of

 the

 hardest

 places

 to

get

 into.

 A

 bit

 like

 today,

 Anthropic

 or

last

 year

 OpenAI

 or

 the

 you

 know,

 like

in

 in

 the

 the

 mid

 mid

2010s,

 Uber.

</details>

>> 是的。

<details><summary>Original English</summary>

>> Yeah.

</details>

>> 你觉得当时的面试体验和拿到offer的过程怎么样？因为那时候肯定竞争相当激烈。

<details><summary>Original English</summary>

>> How

 did

 you

 find

 the

 interview

experience

 and

 and

 getting

 an

 offer?

 Cuz

it

 it

 must

 have

 been

 pretty

 competitive

at

 that

 point.

</details>

### 面试与入职

>> 确实很激烈。他们给我发offer的时候我还挺惊讶的。我没……我觉得自己表现得并不是特别好。我记得由于某种愚蠢的原因，我当时非常非常不想浪费宝贵的假期，所以我是在面试当天早上从圣地亚哥飞过来的，而不是明智地……

<details><summary>Original English</summary>

>> It

 was

 competitive.

 I

 was

 a

 little

surprised

 that

 they

 gave

 me

 the

 offer.

 I

didn't

I

 felt

 like

 I

 didn't

 do

 that

 great.

 I

remember

for

 some

 stupid

 reason,

 I

 really

 really

didn't

 want

 to

 spend

 a

 bunch

 of

 like

precious

 vacation

 days.

 So,

 I

 flew

 up

from

 San

 Diego

 the

 morning

 of

 instead

 of

sensibly

 like

</details>

>> 而且他们本来是会报销酒店和所有费用的。

<details><summary>Original English</summary>

>> And

 then

 they

 they

 they

 would

 have

 paid

for

 the

 hotel

 and

 everything.

</details>

>> 对，对，对。我就是不想……我不知道，我是个容易焦虑的人。我喜欢我的生活习惯和日常作息之类的。为了重要的面试在早晨5点起床可不是什么好主意，朋友们。热心提示。所以，当时有这么几件事。比如，我记得有一场面试是个相对简单的时钟数学题那一类。技术上说是关于火星探测器的相机视角还是什么之类的。

<details><summary>Original English</summary>

>> Yeah,

 yeah,

 yeah.

 I

 just

 didn't

 want

 to

like

I

 don't

 know.

 I'm

 an

 anxious

 person.

 I

 I

like

 my

 habits

 and

 routines

 and

 stuff.

Getting

 up

 at

 5:00

 for

 a

 big

 interview

is

 not

 a

 good

 plan,

 folks.

 Uh

 hot

 tip.

Uh

 so,

 there

 were

 a

 couple

 things.

 Like,

I

 remember

 one

 interview

 was

 like

 a

relatively

 simple

 like

clock

 math

 sort

 of

 thing.

 It

 was

technically

 camera

 angles

 on

 a

 Mars

rover

 or

 something.

</details>

中间有那么一刻，我想的是：“我很累，脑子在面试时转不动了，而这只是基础数学。所以，这是一个输入和输出都正确的函数，只要我今天早上没犯蠢，它就能跑通。”然后我就完全基于这个去做了。

<details><summary>Original English</summary>

And

 there

 was

 a

 point

 in

 there

 was

 like,

"I'm

tired

 and

 having

 interview

 brain

 and

this

 is

 just

 basic

 math.

 So,

 here's

 a

function

 that

 has

 the

 right

 inputs

 and

outputs

 and

 if

 I

 wasn't

 stupid

 this

morning,

 that

 would

 work."

 And

 I

 just

did

 it

 all

 in

 terms

 of

 that.

</details>

我想我的面试官其实非常喜欢这种方式，就像是说：“对，这并不是重点部分，我们就聊聊吧。”于是，是的。最终，他们给了我offer，然后是的，我搬到了纽约。

<details><summary>Original English</summary>

And

 I

 think

 my

 interviewer

 actually

really

 liked

 that

 approach

 of

 like,

"Yeah,

 this

 is

 not

 the

 important

 part.

Like,

 let's

 just

 talk."

 And

 so,

 yeah.

Eventually,

 they

 gave

 me

 the

 offer

 and

yeah,

 moved

 to

 New

 York.

</details>

>> 你入职了。

<details><summary>Original English</summary>

>> you

 started

 up.

</details>

>> 然后你加入了，拿到了，拿到了Noogler螺旋桨帽子。

<details><summary>Original English</summary>

>> And

 then

 you

 joined

 you

 got

 you

 got

 the

nuclear

 hat.

</details>

>> 嗯哼。是的。确实。那是……

<details><summary>Original English</summary>

>> Uh-huh.

 Yep.

 Absolutely.

 It

 was

</details>

>> 那么，你刚加入Google的时候是做什么的呢？

<details><summary>Original English</summary>

>> And

 so,

 what

 did

 you

 work

 on

 at

 Google

when

 when

 you

 joined?

</details>

### 初入Google与团队匹配

>> 嗯，简短地说，我当时在……而且我觉得Google对新员工的团队分配未必是最好的。

<details><summary>Original English</summary>

>> Uh

 so,

 briefly,

 I

 was

 on

and

 like

 I

 I

 don't

 think

 that

 Google

 had

the

 best

 placement

 for

 new

 hires

necessarily.

</details>

>> 也就是我们常说的入职培训流程。

<details><summary>Original English</summary>

>> Onboarding

 process

 as

 we

 say.

</details>

>> 那段经历有点艰难，因为就像我说的，我感兴趣的事情是开发者效率、解决问题，比如我有网络背景，我有API设计等方面的背景。他们说：“噢，你懂网络，那么我们把你放到这个负责监控流量规模以及流量在Google网络边缘何处交汇的团队吧。”

<details><summary>Original English</summary>

>> That

 was

 a

 little

 rough

 cuz

 like

 I

 said,

the

 things

 that

 I'm

 interested

 in

 are

like

 developer

 efficiency,

 problem

solves,

 like

 I

 have

 a

 background

 in

networks,

 I

 have

 a

 background

 in

 like

API

 design,

 those

 sorts

 of

 things.

 They

said,

 "Oh,

 you

 know

 networks,

 uh

so

 let's

 put

 you

 on

 this

 team

 that

monitors

the

 amount

 of

 traffic

 and

 where

 that

 is

crossing

 the

 edge

 of

 the

 Google

network."

</details>

但这实际上是一个数据库问题，只是你处理的所有数据的主题是网络。我就觉得：“我对数据库一无所知，那从来都不是我擅长的领域。”所以，这并不是一个很好的匹配。然后几乎在那之后没多久，大概入职2个月的时候……

<details><summary>Original English</summary>

Uh

 which

 is

 actually

 a

 databases

 problem

with

 networks

 as

 the

 topic

 of

 all

 of

 the

data

 that

 you're

 doing.

 I'm

 like,

 "I

don't

 know

 anything

 about

 databases.

That

 was

 never

 my

 thing."

 So,

 it

 wasn't

a

 great

 fit.

 Um

 and

 then

 almost

immediately

 after

 that,

 like

 2

 months

in,

</details>

>> 我在这里想稍微反驳一下，“拜托。”你加入的是Google。你当时有什么？你念过大学，有对吧，大概四五年的经验。当你加入一家公司，尤其是一家热门公司时，他们说：“好了，去做X。”而你说：“啊，我不是真的……”他们就会觉得：“难道你不想说‘让我深入钻研一下，看看为什么它对业务很重要’吗？”我在这里是在反驳你的看法。

<details><summary>Original English</summary>

>> I

 want

 to

 push

 a

 little

 bit

 back

 here

already

 is

 like,

 "Come

 on."

 Like

 you're

you're

 joining

 Google.

 You

 had

 like

what?

 Like

 you

 you

 had

 college.

 You

 had

Yeah.

 4

 or

 5

 years

 of

 experience.

 When

like

 you

 join

 a

 company,

 especially

 like

a

 hot

 company,

 they

 said

 like,

 "All

right,

 do

 X."

 And

 you're

 like,

 "Ah,

 I'm

not

 really."

 They're

 like,

 "Would

 you

not

 want

 to

 say

 like

let

 let

 me

 just

 go

 deep

 into

 this

 to

 see

why

 the

 why

 it's

 important

 for

 the

business?"

 I

 I

 I

 am

 I

 am

 pushing

 back

 on

you

 here.

</details>

>> 不，对。不，请便，尽管提。我当然尽了我所能去向那个团队学习。在某些事情上确实存在一点人际间的紧张关系。

<details><summary>Original English</summary>

>> No,

 yeah.

 No,

 please

 do.

 Always.

 I

did

 what

 I

 could

 to

 learn,

 you

 know,

from

 that

 team,

 for

 sure.

 Uh

 there

 was

 a

little

 like

 interpersonal

 tension

 in

some

 of

 those

 things.

</details>

>> 好吧，所以一开始就有点那样了。你心里隐约有这种不对劲的感觉。

<details><summary>Original English</summary>

>> Okay,

 so

 it

 already

 started

 a

 bit

 like

that.

 You

 kind

 of

 had

 this

 nagging

feeling.

</details>

### 转入C++基础设施团队

>> 是的，就像是，“对，这不太合适。”然后有一封发给纽约所有工程师的邮件，上面写着：“嘿，我们正在考虑成立一个新团队，来处理所有那些老旧的基础底层C++代码，这些代码是由员工工号只有两位数的人写的。他们有更重要的事情要做，而不是处理所有这些组件的补丁请求。所以，我们希望有人来维护这些东西。”我和不知道大概九个还是十个人举了手，而到了第二次开会的时候，我是唯一去参加的人。所以我基本上就顺理成章地进了那个团队。

<details><summary>Original English</summary>

>> Yeah,

 like

 it

 was

 just

 like,

 "Yeah,

 this

wasn't

 quite

 right."

 And

 then

 there

 was

a

 like

 email

 that

 went

 out

 to

 all

 the

engineers

 in

 New

 York

 saying

 like,

 "Hey,

we're

 thinking

 about

 spinning

 up

 a

 new

team

 that

 handles

 all

 of

 the

 old

 like

C++

 nuts

 and

 bolts

 infrastructure

 code

that

 was

 written

 by

 people

 whose

employee

 IDs

 are

 like

 two

 digits.

 They

have

 more

 important

 things

 to

 do

 than

 to

handle

 like

patch

 requests

 for

 all

 of

 those,

 you

know,

 components.

 So,

 we

 would

 like

people

 to

 maintain

 that."

 Uh

and

 me

 and

 I

 don't

 know,

 nine

 or

 10

other

 people

 like

 raised

 their

 hands,

and

 I

 was

 the

 only

 person

 that

 showed

 up

to

 like

 the

 second

 meeting.

Uh

 so,

 I

 just

 kind

 of

got

 onto

 that

 team.

</details>

>> 噢，我明白了。所以基本上我觉得背景信息非常重要，因为我想大家听到“噢，我加入了这个团队”会觉得好像一开始不是很喜欢。我觉得所欠缺的背景差异在于，首先，Google当时增长得非常快，新团队到处都在成立。而且换组也是挺稀松平常的事，对吧？而且你当时更多是在寻找，好吧，你知道这个团队无论从业务内容上，还是有时候人员并不很契合的角度来看，可能都不是一个你会待上很多年的地方。是的，你尽了最大努力，然后当看到机会时，你知道那更契合你的强项，你就会觉得，抓住它吧。所以对你来说，是C++底层的内容。

<details><summary>Original English</summary>

>> Oh

 I

 get

 it.

 So,

 so

 basically

 I

 think

the

 context

 is

 just

 important

 cuz

 I

think,

 you

 know,

 folks

 hearing,

 "Oh,

 I'm

joining

 this

 team."

 Like

 I

 didn't

 really

like

 the

 the

 first

 thing

 I

 think

 the

difference

 the

 context

 that

 was

 missing

is

 like

 first

 of

 all,

 Google

 was

 growing

really

 quickly.

 New

 teams

 were

 starting

up

 left

 and

 right.

 And

 also

 like

 moving

teams

 was

 kind

 of

 fine,

 right?

 And

 and

you

 were

 more

 looking

 for

 like,

 all

right,

 like

 you

 knew

 that

 this

 team,

both

 for

 the

 what

 they

 were

 doing

 and

also

 sometimes

 there's

 not

 a

 great

people

 fit,

 it

 would

 probably

 not

 be

 the

one

 where

 you're

 going

 to

 be

 staying

 for

many

 years.

 Yeah.

 You

 did

 the

 best

 you

can,

 and

 then

 when

 you

 saw

 an

opportunity,

 you

 knew

 it

 was

 better

 for

your

 strengths,

 you're

 like,

 let's

 go

for

 it.

 So

 So

 for

 you,

 C++

 low-level

stuff.

</details>

>> 是的，我的意思是，当年我在DirecTV做咨询的时候，就做过像构建UPnP API这样的工作，比如通用即插即用方面的东西，像本地网络RPC之类的东西。

<details><summary>Original English</summary>

>> Yeah,

 I

 mean,

 back

 when

 I

 had

 been

 doing

the

 consulting

 at

 DirecTV,

 there

 was

stuff

 like

 build

 an

 API

 to

 do

 UPnP,

 like

universal

 plug

 and

 play

 stuff,

 like

local

 network

 RPC

 sorts

 of

 stuff.

</details>

>> 嗯，远程过程调用？

<details><summary>Original English</summary>

>> Um

 remote

 procedure

 call?

</details>

>> 是的，没错。所以之前很多人的做法是，各个团队都在手动组装每个请求的XML结构，以此来实现一个简单的客户端调用之类的东西。当时觉得，朋友们，我们可以做得更好。虽然在组装整套API的方式上我可能表现得稍微有点聪明过头了，但那就是……是的，那就是我喜欢的东西。

<details><summary>Original English</summary>

>> Yeah,

 right.

 And

 so

 it

 had

 been

 a

 lot

 of

people

 teams

 were

 manually

 assembling

like

 the

 XML

 structure

 for

 every

 request

to

 like

 implement

 a

 single

 client

 call

or

 something

 like

 that.

 It

 was

 like,

 we

could

 do

 better,

 folks.

 And

 like

 I

 was

probably

 a

 little

 too

 clever

 in

 the

 way

that

 I

 assembled

 all

 of

 that

 API,

 but

 it

was

 like

 it

 Yeah,

 like

 that

 was

 the

thing

 that

 I

 liked.

</details>

>> 这个团队到底更像是一种自发倡议，比如“嘿，Google在这儿那儿有一堆C++代码”，有点像自下而上的，“大家一起在空闲时间看看能不能做点什么”；还是说更偏向于某个管理层的人说“我实际上在考虑组建一个团队，一个全职的团队来做这件事”？

<details><summary>Original English</summary>

>> This

 team,

 what

 what

 was

 it

 more

 of

 of

initiative

 of

 like,

 hey,

 Google

 has

 a

bunch

 of

 C++

 here

 and

 there,

 kind

 of

like

 roots

 up,

 like,

 you

 know,

 let's

 get

together

 and

 initially

 in

 our

 free

 time,

let's

 see

 if

 we

 can

 do

 something,

 or

 was

it

 more

 some

 manager

 type

 said

 like,

 I'm

actually

 thinking

 of

 assembling

 a

 team,

a

 full-time

 team

 on

 this?

</details>

>> 所以我想那应该是在Google真正把“你归属于特定团队并且HC有限”严格制度化之前的最后一年。当时关于这些事情如何运作还有点混乱、有点随意。我也可能说得不对，因为我当时毕竟还是个新人，关于HC如何运作的内部机制可能不是很清楚。

<details><summary>Original English</summary>

>> So

 this

 was

 I

 think

 like

 the

 last

 year

before

 Google

 would

 got

 actually

 pretty

formal

 about

 your

 embedded

 to

 a

particular

 team

 and

 head

 count

 is

limited.

 It's

 a

 little

 chaotic,

 it's

 a

little

 loosey-goosey

 about

 how

 those

things

 work.

 I

 could

 actually

 be

 wrong

about

 that

 cuz

 I

 was

 still,

 you

 know,

new

 enough

 that

 the

 internals

 of

 how

head

 count

 works

 might

 have

 been

 just

not

 clear.

</details>

但无论如何，我转组相当快，而且天哪，那完全就是最适合我的地方。

<details><summary>Original English</summary>

But

 yeah,

 like

 moved

 over

 pretty

 quick,

and

 boy,

 that

 that

 was

 exactly

 the

 place

for

 me.

</details>

### 接手老旧代码与测试文化

>> 好吧，那就给我讲讲看。为什么？为什么会是适合你的地方？我们可以想象那是一种什么样的工作？因为我的意思是，当你向我描述接手别人在Google写的各种C++代码时，对我来说那听起来简直就像是地狱模式，作为一名工程师，尤其是在pre-add阶段，对吧？去理解另一个某个时候可能已经离职的工程师写的东西，某个团队正在使用它而且运行良好，这听起来就像是个两头不讨好的局面，因为如果你接手了它，改了代码，把别人的功能改挂了，他们会对你发火；而如果你接手了并且做得很好，他们可能根本都不会去想这件事，因为反正它一直能用，现在依然能很好地运行。

<details><summary>Original English</summary>

>> All

 right,

 then

 tell

 me

 about

 it.

 Why

Why

 was

 it

 the

 place?

 What

What

 kind

 of

 work

 can

 we

 imagine

 of

 like

I

 mean,

 cuz

 it

 sounds

 like

 when

 you

describe

 to

 me

 like

 taking

 random

 C++

stuff

 that

 people

 wrote

 at

 Google,

 like

that

 that

 sounds

 like

 the

 version

 of

hell

 for

 me,

 like,

 you

 know,

 like

 as

 an

engineer,

 especially

 to

 pre-add,

 right?

Like

 understanding

 what

 another

 engineer

at

 some

 point

 wrote

 who

 might

 have

 left

and

 a

 team

 is

 using

 it

 and

 it's

 working

for

 them

 like

 that

 it

 sounds

 like

 it's

 a

lose-lose

 because

 if

 you

 take

 it

 over

and

 you

 make

 a

 change

 and

 you

 break

someone

 they'll

 be

 mad

 at

 you

 and

 uh

 if

you

 do

 it

 and

 you

 do

 a

 great

 job

 they'll

probably

 not

 even

 think

 about

 it

 cuz

 it

just

 it's

 always

 worked

 it

 still

 works

great.

</details>

>> 幸运的是，在这一切发生之前的几年里，修改代码的敬畏之心和安全网就已经建立得相当完善了。

<details><summary>Original English</summary>

>> Uh

 luckily

 the

 fear

 and

 the

 the

 safety

net

 for

 making

 changes

 had

 been

 pretty

well

 established

 a

 couple

 years

 before

this

 played

 out.

</details>

具体来说，这关乎我们一会儿肯定会聊到的话题。具体而言，Google已经经历过了“是的，你必须写测试”的阶段。

<details><summary>Original English</summary>

Specifically

 and

 like

 this

 goes

 to

topics

 that

 we'll

 get

 to

 in

 a

 second

 I'm

sure.

 Specifically

 like

 Google

 already

went

 through

 the

 phase

 of

 yes

 you

 have

to

 write

 tests.

</details>

对吧？

<details><summary>Original English</summary>

Right?

</details>

>> 在2010年，这在行业里并不是一件理所当然的事。

<details><summary>Original English</summary>

>> In

 2010

 this

 was

 not

 an

 obvious

 thing

 in

the

 industry.

</details>

>> 没错。但我想故事大概是2006、2007年的时候，搜索团队失去了定期发布版本的能力。当时的情况变成了，比如我们本来尝试每月发布一次，而他们大概只能一个季度发布一次，因为……

<details><summary>Original English</summary>

>> Right.

 But

 like

 I

 think

 the

 story

 is

2006

 2007

uh

 search

 lost

 the

 ability

 to

 push

 a

release

 on

 a

 regular

 cadence.

 Like

 it

was

 down

 to

 like

 we

 were

 trying

 for

monthly

 and

 they

 were

 maybe

 only

 get

once

 a

 quarter

 because

</details>

>> 噢，所以这就是为什么Google会痴迷于测试、代码质量以及所有这些东西。

<details><summary>Original English</summary>

>> Oh

 so

 so

 so

 this

 is

 why

 is

 Google

obsession

 with

 tests

 and

 quality

 and

 all

that.

</details>

>> 嗯哼。

<details><summary>Original English</summary>

>> Uh-huh.

</details>

>> 所以核心的赚钱产品在2006年前后基本上像是被束缚住了手脚，无法发布。哇。

<details><summary>Original English</summary>

>> So

 so

 the

 the

 the

 the

 core

 money

 making

product

 was

 kind

 of

 handcuffed

 not

 being

able

 to

 push

 around

 through

 2006.

 Wow.

</details>

>> 而且大约在2006年，你做的几乎任何事情都会……

<details><summary>Original English</summary>

>> And

 circa

 2006

 almost

 anything

 that

 you

did

 had

</details>

<!-- chunk 3/13 -->

比如前端或者搜索之类的地方还有些千丝万缕的联系，整个架构、隔离以及多应用、多产品的体系当时依然不够完善。所以如果你在对 Gmail 做改动，依然有可能同时改动到了搜索。

<details><summary>Original English</summary>
some tendrils in like the front end or search or stuff like that the whole architecture and separation and like multi-app multi-product like world that was still not right. So if you're making changes to Gmail there were still chances that you were like making changes to search.
</details>

>> 哇。

<details><summary>Original English</summary>
>> Wow.
</details>

>> 于是所有事情都被卡住了。所以发布工程师们联合了起来，他们干脆直接说：如果没有测试，就别想合入这个改动。没得商量。我们不管哪个副总裁说了什么，我们不管这个功能有多重要。你们绝对不能那么做，否则我们就会回滚。

<details><summary>Original English</summary>
>> And so like everything was you know held up. So the release engineers like they banded together and they simply just said like you will not merge this change if there is not tests. Period. We do not care what VP says anything. We do not care how important this feature is. You will not do that. Like we will roll that back.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 一旦你划定了明确的界限，哪怕是那些自视甚高、“我这么聪明，你怎敢要求我写测试，这有失我身份”的人，也必须照办。

<details><summary>Original English</summary>
>> And like as soon as you put a line in the sand even the people that are like I'm very smart how dare you ask me to write tests. Like this is beneath me.
</details>

>> 那么基本上，无论是接手维护，还是去修改某个 C++ 库，你都有了测试，因而能有高度的信心：只要重构完这些东西，所有的测试都能通过。要么它正常工作，要么就是测试覆盖率从来都不够。

<details><summary>Original English</summary>
>> And then so basically taking over or taking on maintenance or or even changing any a library C++ library, you had the test so you could have high confidence if you refactor these things all the test pass. Yeah, either it works or there was never enough test coverage.
</details>

>> 对，没错。对吧？而且……

<details><summary>Original English</summary>
>> Right, exactly. Right? And like
</details>

>> 无论哪种情况都是好事，因为暴露出测试覆盖率不足反而更好；即便今天发生崩溃，明天或者一年后，流量无论如何都会翻倍。

<details><summary>Original English</summary>
>> And any day where it's a win because if you it's it's better if you expose the lack of test coverage and okay, you have a crash today, but tomorrow or a year from now you'll have twice as much traffic anyway.
</details>

### 对变更的恐惧与工程可持续性

>> 对，完全没错。而且有一点我深信不疑：如果你因为恐惧而不敢去修改某样东西，你就必须着手去解决这个问题。恐惧绝不是工程可以接受的基础。我想这写在书里的前两三页，我已经讲了十年了：如果面对任何有价值的变更，你都有能力安全地完成这项变更，那么你的代码库就是可持续的，对吧？你也可以选择不做这个变更，那可能是因为技术债，或者不同的产品优先级等等。但如果你没有能力应对变化，那你就是在孤注一掷地押注这个变化并不关键或并不重要。我很不想泼冷水，但这几年安全领域的形势已经变得非常严峻。没有什么是一成不变的。拥有适应变更的能力，其战略优势是难以估量的。

<details><summary>Original English</summary>
>> Right, exactly. And like uh it's one of the things that I believe very deeply is if you are held back from making changes to a thing out of fear, you have to go in and fix that. Like fear is not an acceptable basis for engineering. And I think it's in the first two or three pages of the book uh I've said now for 10 years you know, your code base is sustainable if for any valuable change that comes along, you are capable of making that change safely, right? You may choose not to make that change, right? That could be technical debt or, you know, different product priorities or whatever. But if you're incapable of reacting to change, then you're placing a high bet or high risk bet that the change isn't critical or isn't important. And I hate to break it to people, but like security world has gotten real real bad in the last few years. Like there is nothing that is not going to change. Like the strategic advantage of being able to change is incredible.
</details>

>> 能不能这样说：如果我加入一家公司，无论是初创团队、大公司，还是随便什么公司，我加入团队并审视其代码库，在最初的几周、几个月里，我只是因为担心搞坏系统、搞坏生产环境而不敢提交代码变更，那是不是意味着我所接手的这个系统，可以说它的工程水平很糟糕？

<details><summary>Original English</summary>
>> Is it safe to say that if I join a company, a startup, a large company, whatever company I join the team and I look at the code base and you know, my first weeks, my first months I'm just being afraid of pushing code changes cuz I I worry this thing will break. I'll break production. That I'm working on a system that is just, let's say it's poorly engineered.
</details>

>> 可能是系统工程做得很糟，也可能是没有做好入职培训和指导带教。

<details><summary>Original English</summary>
>> It could be the system is poorly engineered or it could be you there's some onboarding and mentoring that didn't happen there.
</details>

>> 对吧？所以必然是这两者之一的问题。

<details><summary>Original English</summary>
>> Right? So one or the other problem.
</details>

>> 肯定二者必居其一。我认为这也牵涉到某些教育方面的问题。在本科教育中，以及我们在描述这份工作时，往往会传达出一种“存在正确答案”的印象——非对即错，而不是权衡取舍。只要有人查看你的成果，你就是在被评分。

<details><summary>Original English</summary>
>> One or the other for sure. And I think and this goes to some of the educational stuff, like we in undergrad, you know, education and like the way that we kind of portray what the job is like, there is a correct answer. There is right and wrong. It is not just the trade-offs. And you're graded anytime someone looks at what you have done.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 对吧？我认为尤其是对于应届毕业生来说，这会非常艰难。他们很容易陷入一种恐惧中：“我不知道自己做得对不对，我不知道这是不是你想要的答案。”因为他们被灌输了这种错误的观念，以为存在所谓的标准答案，而实际上它自然只是一种权衡取舍，对吧？只是设计空间里的某一个取舍点而已。

<details><summary>Original English</summary>
>> Right? And I think it's going to be for especially for new grads, it's really hard. It's really easy to get into a fear of like, I don't know if I did this right. I don't know if this was the answer you were looking for because they've been falsely given this perspective that there's a right answer instead of of course it's just a trade-off, right? It's at some point in the design space.
</details>

>> 我想你也是在说，这些应届生还习惯了去完成一项有实质意义的付出——通常是一门课或一次考试——然后就能获得反馈。你能拿到一个量表，拿到一个成绩，至少能得到认可、通过或者不及格。我还记得自己刚去第一份工作时，我真该记住那个场景，那感觉真的很奇怪。加入公司后，我完成了这个项目，然后毫无回音。接着我做了另一件事，依然毫无回音。随后我和公司的 CEO 进行一对一面谈，当时我心想他们要解雇我了，因为我很清楚有时候大白天的我会在那儿摸鱼，因为我已经把手头的事情做完了。事后回想起来，我当时的效率其实挺高的，但我只是做完了手头的事就顺手浏览起网页。我告诉他们“我准备好了”，当时心里十分确信自己可能会挨训之类的。结果正相反，他们对我讲：“做得很棒！你上手适应得太快了，我们对你非常满意。”我当时整个人都愣了。但差别在于，在此之前我已经习惯了多年来直接得到反馈的模式，脑子里一时没转过弯来。

<details><summary>Original English</summary>
>> And I guess you're also saying that these new grads they're also used to you do something that is a meaningful effort, typically a class or an exam, and you get feedback. You you get a scale, you get a grade, you get a thumbs up, a pass or a fail at the very least. And I know I should remember when when I went to my first workplace, I should remember this. This is really weird. Like, join the company, I did I built this project, and then nothing. And then I, you know, I I I do another thing and then nothing. And then I have a I have a one-on-one with the CEO of the company, and I I'm thinking they're going to fire me cuz like clearly like I I I I knew that I don't know like middle of the day like I was sometimes slacking off cuz I finished my stuff. In hindsight, I was pretty efficient, but I just finished my stuff and then I was just browsing the internet. I I told them, "I'm ready." And I I was pretty sure like maybe I'll be reprimanded or something. And instead, told me like, "Oh, amazing job. Like, you've onboarded so quickly. We're so happy with you." And I was But the the difference was that up until then I had years of getting direct feedback, and it didn't connect in my mind.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 另一部分在于，在本科阶段，别人看你代码的唯一时刻就是给你打分、评判你。对吧？然而当你成长为一名经验更丰富的工程师后，你虽然也会频繁寻求反馈，但这只是一种核对确认：“我们方向走得对吗？你觉得这样做合理吗？”对吧？你得到的非评判性反馈越多，你的效率就会越高。哎，我真是很反感我们竟然给所有应届毕业生和初级工程师灌输了完全错误的本能直觉。

<details><summary>Original English</summary>
>> The other part of that is like the only time that a human is going to look at your code if you're an undergrad is to grade you, is to judge you. Right? Whereas when you you like become a more experienced engineer, right? Like, you're asking for feedback regularly, but it's just like a check-in like, are we going in the right direction? Does this make sense to you, right? And the more of that feedback that you can get that isn't judgment, the more effective you will be. Like, "Oh, I hate that we've like given all of the new grads and all the junior engineers exactly the wrong instinct."
</details>

### Abseil 项目的起源与重构

>> 那么回到 Google，什么是 Abseil？这个词到底该怎么读？

<details><summary>Original English</summary>
So, go going back to to Google, what is abseil? How how how how do you pronounce it correctly?
</details>

>> 读作 Abseil。

<details><summary>Original English</summary>
>> Abseil.
</details>

>> Abseil。是的。大约在 10 年前，紧接着最初向云原生转型的步伐之后，Abseil 项目启动了。当时有一种动向：“嘿，除了这些惊人的生产环境成果，我们还有这么多出色的开发者工具。也许我们也应该尝试将开发者工具对外开放。”与此同时，Google 也正逐渐转型为 Alphabet。因此，就开发者工具层面而言，面临着一个问题：我们该如何在 Alphabet 伞形架构下的不同公司之间共享这些开发者工具？另外，对于高价值的内部接口、API 以及技术组件，当不再属于单一的公司实体时，我们又该如何去共享它们？

<details><summary>Original English</summary>
>> Abseil. Yeah. So, abseil was starting about 10 years ago, shortly after the initial pivot to cloud, there was a motion to "Hey, we have all of these amazing developer tools in addition to the all this amazing production stuff. Maybe we should try to externalize the developer tools as well. And at the same time, there was also a little bit of Google shifting into Alphabet. So, for both the developer tooling aspects at one level of like, how do we share developer tools amongst different companies within the Alphabet umbrella? And how do we share high-value, like, internal interfaces and APIs and, you know, tech components? How do we share those when it's not one, you know, single corporate one single company?
</details>

>> 而且也不再是单一的单一代码库（monorepo）了，对吧？

<details><summary>Original English</summary>
>> And also not one mono repo, right?
</details>

>> 越来越走向那样了，确实如此。嗯，所以有许多工作是属于常规性质的，比如：要想让这些开发者工具支持多租户，并且稍微减少对内部生态系统的绝对依赖，需要做些什么？

<details><summary>Original English</summary>
>> Increasingly, yeah. Exactly. Um and so, there's a bunch of work that's kind of the normal, like, okay, what does it take to make these developer tools like multi-tenant and like, you know, slightly less completely tied into that ecosystem.
</details>

>> 对于不太熟悉的人，Google 内部所说的“多租户”具体是指什么？

<details><summary>Original English</summary>
>> And and and just multi-tenant for for those who are who are not that familiar with What does multi-tenant mean inside of Google?
</details>

>> 嗯，这里指的是对 Alphabet 伞形架构下的其他公司实现多租户，之后可能还会延伸到云客户。

<details><summary>Original English</summary>
>> Uh well, so this would have been multi-tenant of other companies within the Alphabet umbrella, and then maybe extend that out to cloud customers.
</details>

>> 哦，明白了。也就是说，类似于 Waymo 和 Google 理论上都可以使用它，诸如此类的。

<details><summary>Original English</summary>
>> Oh oh, got it. Yeah, so like a like a way more and the Google could theoretically use it, something like that.
</details>

>> 后来那个方向变得没那么热门了，一两年后他们也就基本放弃了那个想法。但是，对于底层组件来说，如果你想共享那些在单一代码库内部编写的代码，要怎么做才能行之有效？Abseil 本质上就是通用 C++ 惯用法的基石层。它就像是一套通用语言，Google 的一切都是基于它构建出来的。让我们把它开源，以便为所有的 Google 技术提供一套通用基础。与此同时，大家提出的问题是：这里面的某些表达方式很粗糙，属于技术债，在我们承诺永久维护之前，是否应该先清理干净？非常值得称赞的是，大家的答案是肯定的。所以，Abseil 开源项目就是那些经过清理的代码在公开层面的呈现。大部分的工作，我可以十分笃定地坚称，这很可能是人类历史上规模最大的一次重构任务。

<details><summary>Original English</summary>
>> That became not the hottest topic and they they kind of dropped that idea after a year or two. Um but, the low-level components, like, if you wanted to share these things that were written internally in the mono repo, what would it take to do that effectively? And abseil was basically here is the layer of common like C++ idiom. Like this is the vernacular that everything at Google is written out of. Let's open source that so that there's a common substrate for all like Google tech. At the same time, the question was some of this vernacular is gross and tech teddy should we clean that up before we commit to it forever? And the answer was yes to their great credit. So, the Abseil open source project is the public like projection of the stuff that got cleaned up. Most of the work was that was I that would defend pretty strongly. That was probably the largest refactoring task in human history.
</details>

>> 不可能吧。

<details><summary>Original English</summary>
>> No way.
</details>

>> 真的，我们当时有大概 10 到 12 个人全职投入，借助其他外界尚未理解的顶尖工具，专心进行清理，并确保外部的惯用代码能够与内部的惯用代码相兼容。

<details><summary>Original English</summary>
>> Yeah, we had like 10 10 or 12 people working full-time with world-class tools that no one else understands yet just cleaning up and making sure that idiomatic code externally would be compatible with idiomatic code internally.
</details>

>> 很显然，当你谈到清理时，你指的是清理那些正处于世界上使用量最高的一些服务核心中的实用工具和组件——Google 搜索……

<details><summary>Original English</summary>
>> And obviously when you're talking about cleaning up you're talking about cleaning up utilities and components that are in the middle of some of the highest use services in the world, Google search
</details>

>> 对。

<details><summary>Original English</summary>
>> Yep.
</details>

>> Gmail……

<details><summary>Original English</summary>
>> Gmail
</details>

>> 对。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 地图……

<details><summary>Original English</summary>
>> Maps,
</details>

<!-- chunk 4/13 -->

应有尽有。

<details>
<summary>Original English</summary>

 you

 name

 it.
</details>

>> 全部。

<details>
<summary>Original English</summary>

>> All

 of

 it.
</details>

>> 比如你要是弄坏了什么东西，很可能某一时刻就会看到其中某项服务发生故障。

<details>
<summary>Original English</summary>

>> Like

 if

 if

 if

 you

 would

 break

 something,

you

 would

 probably

 see

 at

 some

 point

 an

outage

 in

 one

 of

 those

 services.
</details>

>> 那时候大概有，我想是两亿或两亿五千万行 C++ 代码，而且——

<details>
<summary>Original English</summary>

>> It

 was

 at

 the

 time,

 I

 think

 it

 was

 200

or

 250

 million

 lines

 of

 C++

 code

 with
</details>

>> 两亿五千万行 C++。

<details>
<summary>Original English</summary>

>> 250

 million

 lines

 of

 C++
</details>

>> 是第一方的，还不算外部依赖项。

呃，谷歌当时有那种——我想这是当时公开的数字。当时一个月里大概有一万名工程师在对那个代码库进行修改。所以，我们的工作是——我们开玩笑说——那是个纽约的典故。我们开玩笑说，我们的工作在逻辑上等同于：谷歌搞出了一种用于摩天大楼地基的新技术。我们要给帝国大厦更换地基。我们不能封楼，也不能阻断交通。而且我们还在地下室里发现了核废料。

没事的，伙计们。我们搞得定。那真的——那曾经是一个奇迹般的、很棒的团队。

<details>
<summary>Original English</summary>

>> first

 party,

 not

 counting

 external

dependencies.

Uh

 and

 Google

 had

 that

 kind

 of

I

 think

 that

 was

 the

 public

 number

 at

the

 time.

 10,000

 engineers

 probably

 at

the

 time

 uh

 making

 edits

 to

 that

 code

base

 in

 a

 month.

 And

 so,

 our

 job

 was

 we

joked

 about

 That's

 a

 New

 York

 reference.

We

 joked

 about

 it

 as

 our

 job

 is

 the

logical

 equivalent

 of

 Google

 has

 a

 new

technology

 for

 the

 skyscraper

foundations.

 We're

 replacing

 the

foundation

 under

 the

 Empire

 State

Building.

 We're

 not

 allowed

 to

 close

 the

building

 or

 block

 traffic.

 And

 we

discovered

 nuclear

 waste

 in

 the

basement.

It's

 okay,

 guys.

 We

 got

 this.

 Like,

 it

was

 It

 was

 a

 magically

 It

 was

 a

 great

team.
</details>

### 代码规模与重构挑战

>> 我只是想把这两亿五千万行代码放到一个参照系里来看，因为在今天，有了 AI，AI 能生成——你知道的，就像我们看到的那些疯狂的数字。它能在一个小时里生成几万行代码等等。如果你想的话，完全可以搞出数百万行。坦白说，光靠一个智能体就能做到。

然而，在 AI 出现之前，呃，Uber 的移动应用程序在 iOS 和 Android 上各自大约是一百万行代码，而且那是各自两百名工程师写了好些年的成果。Anthropic 的 Bun 运行时刚刚重写了大约——我想大概是五十万或九十万行代码，那是出自一个小团队之手。我觉得很难找到在 AI 出现之前超过——比方说三百万行代码的项目，而且通常都得是几百名工程师写上好几年。所以，在这……我之所以对两亿五千万感到吃惊，是因为这比我听说过的代码库大概大了一百倍。而且我们说的是——这显然全都是为生产环境写的。你不是在闹着玩，或者到处推点脚手架代码什么的，对吧。而且你说第一方代码的时候——引入开源组件时很容易堆出巨量代码，但并不是这样。

<details>
<summary>Original English</summary>

>> I

 just

 want

 to

 put

 the

 250

 million

 lines

of

 code

 in

 in

 in

 in

 perspective

 cuz

today

 with

 with

 AI

 AI

 can

 generate

 like,

you

 know,

 like

 we

 have

 crazy

 numbers.

 It

can

 generate

 tens

 of

 thousands

 of

 lines

of

 code

 in

 an

 hour,

 etc.

 And

 and

 you

 can

get

 to

 millions

 if

 if

 you

 want

 to.

Honestly,

 just

 an

 agent

 can

 do

 it.

However,

 pre-AI

uh

 Uber's

 uh

 mobile

 application

 was

about

 a

 million

 lines

 of

 code

 on

 iOS

 and

on

 Android,

 and

 that

 was

 each

 written

 by

200

 engineers

 for

 for

 years.

 Bun

uh

 runtime

 at

 Anthropic

 just

 rewrote

something

 like

 I

 think

 it

 was

 like

 500

or

 900,000

 lines

 of

 code,

 and

 that

 was

written

 by

 a

 a

 small

 team.

 I

 find

 it

rare

 to

 find

 examples

 of

 a

 project

 that

has

 more

 than

 pre-AI,

 more

 than

 let's

say

 3

 million

 lines

 of

 code,

 and

 that

will

 typically

 be

 hundreds

 of

 engineers

writing

 it

 for

 for

 several

 years.

 So,

 in

this

 in

 this

 The

 reason

 I

 was

 like

 250

million,

 that

 is

 about

 100

 times

 more

than

 I've

 heard

 for

 codebase.

 And

 we're

talking

 about

 like

 clearly

 this

 is

written

 for

 production.

 You're

 not

 like

just

 goofing

 around

 and

 pushing

 some

scaffolding

 here

 and

 there

 and

 and

right.

 And

 And

 when

 you

 say

 first

 party,

it's

 easy

 to

 to

 have

 a

 lot

 lot

 of

 code

when

 you

 take

 on

 an

 open-source

component,

 but

 no.
</details>

>> 是的。不，那全都是谷歌人写的。所以，我们对于事情是如何运转的有些深入了解。

<details>
<summary>Original English</summary>

>> No.

 No,

 that

 was

 all

 Googler

 authored.

And

 uh

 so,

 we

 have

 some

insight

 into

uh

 how

 things

 go.
</details>

>> 好吧，所以人类历史上当时规模最大的重构，可能——你大概不是在删改削减。

<details>
<summary>Original English</summary>

>> Okay,

 so

 the

 largest

 refactoring

 history

at

 that

 point

 in

 uh

 human

 history

 might

have

 uh

 you're

 not

 expurgating

 likely.
</details>

>> 我的意思是，我无法证明这点，但我——如果不是的话我会很惊讶。

<details>
<summary>Original English</summary>

>> I

 mean,

 I

 can't

 prove

 it,

 but

 I

 I

 would

be

 surprised.
</details>

>> 那么，具体怎么做呢？好吧，当你面对这种局面——你们十到十二个人身处其中。面对这个庞大无比、看似巨大且几乎——你们是如何着手处理的？你们是怎么说——是如何拆解它的？你们是如何做规划的？又是如何提速的？因为显而易见，如果你纯靠手工去做，这完全是行不通的。

<details>
<summary>Original English</summary>

>> So,

 how

 Okay,

 when

 you

 have

 this

 You're

in

 the

 middle

 of

 this

 10

 to

 12

 people.

You

 have

 this

 massive

 massive

 task

 that

seems

 giant

 and

 almost

How

 do

 you

 go

 about

 it?

 How

 do

 you

 say

like

 How

 do

 you

 break

 it

 down?

 How

 do

you

 plan

 for

 it?

 How

 do

 you

 speed

 it

 up

because

 you

 clearly

 if

 you

 just

 did

 it

by

 hand,

 this

 would

 have

 not

 fully

worked.
</details>

### 基于 AST 与 clang-format 的大规模重构方法

>> 没错。所以，呃，促成这一切并源于最开始就在低阶 C++ 基础设施团队的一件事就是：好吧，如果我们掌握了那些接口，也就是构成谷歌一切代码的基础零配件——远在数据库层面之下，就像缓存、容器、字符串处理例程、命令行标志这一类东西。如果我们掌握了这些东西，也许把它们改好是很有价值的。但是，当有五万个调用点，或者改动该 API 需要做出十万处修改时，你该怎么做呢？

于是幸运的是，我和编译器团队成了朋友，最终在组织架构上也成了近邻，特别是 clang 和 LLVM 那帮人。

于是他们开始在 AST 转换这类事情上做探索。

<details>
<summary>Original English</summary>

>> Right.

 So,

 uh

 one

 of

 the

 things

 that

 had

enabled

 any

 of

 this

 and

 that

 came

 out

 of

having

 been

 on

 that

 the

 low-level

 C++

infrastructure

 team

 to

 start

 with

 was

Okay,

 if

 we

 own

 the

 interfaces

 that

 are

kind

 of

 the

 nuts

 and

 bolts

 that

everything

 at

 Google

 is

 written

 out

 of

like

 way

 below

 the

 database

 level

 just

like

 caches,

 containers,

 string

manipulation

 routines,

command

 line

 flags,

 like

 that

 sort

 of

thing.

 If

 we

 own

 those

 things,

 maybe

it's

 valuable

 to

 make

 them

 better.

 But

how

 do

 you

 do

 that

 when

 there's

 50,000

call

 sites

 or

 100,000

 edits

 that

 need

 to

be

 made

 to

 change

 that

 API?

And

 so

 luckily

 I

 was

 friends

 and

 org

chart

 cousins

 eventually

 with

 the

 the

compiler

 team,

 especially

 clang

 LLVM

people.

And

 so

 they

 started

 doing

 stuff

 in

 the

AST

 transformation

 sort

 of

 thing.
</details>

>> AST？

<details>
<summary>Original English</summary>

>> AST?
</details>

>> 呃，抽象语法树。也就是拿解析树来处理。

而且你知道，在谷歌嘛，就像 MapReduce 那样。所以如果你在代码库上跑一个 MapReduce，由 mapper 解析你 C++ 的所有翻译单元，比如所有的构建目标，并生成——这就是解析树，然后你就可以在解析树中匹配具体的——这可不是文本匹配，而是：我保证你就是在特定的语境下调用了这个特定的函数。然后你就可以应用一段代码基于此进行重写。所以我们有了编译器辅助的、半自动化的重构，来生成所有的文本修改。结果发现，一开始真正棘手的事情之一是：我们能生成修改，却无法把空白符放在正确的位置上。

<details>
<summary>Original English</summary>

>> Uh

 abstract

 syntax

 tree.

 So

 like

 you

take

 the

 parse

 tree.

And

 you

 know,

 it's

 Google

 like

 map

reduce.

So

 if

 you

 do

 a

 map

 reduce

 over

 the

 code

base

 uh

 where

 the

 mapper

 parses

 all

 of

the

 translation

 units

 of

 your

 C++

 like

all

 of

 the

 build

 targets

and

 produces

 here

 is

 the

 parse

 tree,

then

 you

 can

 match

 the

 parse

 tree

 for

specific

 like

 it's

 not

 text

 match,

 it's

I

 guarantee

 you

 are

 calling

 this

particular

 function

in

 this

 particular

 context

and

 then

 you

 can

 apply

 some

 code

 to

 rea-

rewrite

 based

 on

 that.

 And

 so

 we

 had

compiler

 assisted,

 you

 know,

semi-automated

 refactoring

 to

 generate

all

 of

 the

 text

 edits.

 Turns

 out

 one

 of

the

 things

 that

 was

 really

 hard

 at

 first

was

 we

 could

 generate

 the

 edit

 but

 we

couldn't

 get

 the

 white

 space

 in

 the

right

 places.
</details>

>> 不可能吧。

<details>
<summary>Original English</summary>

>> No

 way.
</details>

>> 是的，说真的。所以 clang-format 之所以存在，就是因为我许了这个愿。呃，它现在是很多类 C++ 语言的自动格式化工具了。但当时的情况就像是：我实在无法完成这次重构，除非有人想出办法给 C++ 攒出一个自动空白符处理工具。于是你这么做了，生成了一次巨大的修改。但它太大了，无法直接合入代码库，嗯，因为对于任何给定的代码库，其背景中发生的变更量都会有一个自然的基线。如果你试图修改一万个文件、两万个文件，很可能出现的情况是：在某处失去同步之前，你永远也无法完成测试和重新同步。

<details>
<summary>Original English</summary>

>> Yeah,

 seriously.

 So

 clang-format

 exists

because

 I

 wished

 for

 it.

Uh

 this

 is

 like

 the

 auto

 formatter

 for

many

 like

 C++

 sorts

 of

 languages

 at

 this

point.

 But

 it's

 like

 I

 literally

 cannot

accomplish

 this

 refactoring

 until

someone

 figures

 out

 a

 way

 to

 like

 hack

together

 a

 auto

 white

 space

 for

 C++.

 And

so

 you

 you

 do

 that,

 you

 generate

 one

you

 know,

 big

 edit.

 It

 is

 too

 large

 to

fit

 in

 the

 code

 base

 um

 because

 for

 any

given

 code

 base

 there's

 kind

 of

 a

natural

 background

 level

 of

 how

 much

change

 is

 happening.

 And

 if

 you're

trying

 to

 edit

 10,000

 files,

 20,000

files,

it

 is

 likely

 the

 case

 that

 you

 will

never

 be

 able

 to

 test

 and

 resync

 before

something

 has

 gone

 out

 of

 sync.
</details>

>> 是的。

<details>
<summary>Original English</summary>

>> Yeah.
</details>

>> 对吧？别人修改了别的东西。

<details>
<summary>Original English</summary>

>> Right?

 Someone

 else

 edited

 something.
</details>

>> 没错。合并冲突，比如并行变更这类情况。

<details>
<summary>Original English</summary>

>> Yeah,

 exactly.

 Merge

 conflicts,

 like

parallel

 changes,

 that

 kind

 of

 stuff.
</details>

>> 是的，完全正确。你知道，在一家一万多人的公司里，你不可能去要求：“大家停下一个小时别动代码仓库，让我把这事给办了。”这根本无法扩展，对吧？所以技术手段是：你拆解所有……你想方设法做重构，让新旧 API 在拼写上可以并存。

<details>
<summary>Original English</summary>

>> Yeah,

 exactly.

 You

 know,

 you

 do

 not

 want

at

 a,

 you

 know,

 10,000-plus

 person

company

 to

 be

 like,

 "Everyone

 stop

touching

 the

 repo

 for

 an

 hour.

 Let

 me

 do

this

 thing."

 Like

 that's

 not

 going

 to

scale,

 right?

 And

 so

 the

 tech

 is

 you

break

 all

 of

 like

 you

 figure

 out

 how

 to

do

 your

 refactoring

 so

 that

 the

 old

 API

and

 the

 new

 one

 can

 coexist

 in

 spelling.
</details>

>> 明白。

<details>
<summary>Original English</summary>

>> Yeah.
</details>

>> 然后你并行化推进，就按目录结构来切分。比如：“好了，我发给你这批更新，发给你这批更新。”于是最终就是这么一路推进。等一切都清理干净后，接着就是赛跑，确保没人再去复制粘贴旧的那套。呃，然后你删掉旧的，新的就成了默认设置，继续干别的。你只要这么重复几百次，代码库的状态就会好得多。

<details>
<summary>Original English</summary>

>> And

 then

 you

 parallelize,

 like

 just

 cut

by

 like

 directory

 structure.

Like,

 "All

 right,

 I'll

 send

 you

 this

batch

 of

 updates,

 this

 batch

 of

updates."

 So

 you

 wind

 up,

 you

 know,

going

 like

 that.

 And

 then

 once

everything

 is

 clean,

 then

 there's

 a

 race

to

 make

 sure

 no

 one

 copy

 and

 pastes

 the

old

 thing.

Uh

 and

 then

 you

 delete

 the

 old

 thing,

the

 new

 thing

 is

 the

 default,

 you

 move

on

 with

 life.

 You

 just

 do

 that

 a

 few

hundred

 times

 and

 your

 code

 base

 is

 in

much

 better

 shape.
</details>

>> 是啊，哇。而且你做这一切的时候，其他工程师就只管做他们自己的事，他们用着这些东西却毫不知情，他们也不想了解你们的事。我是说——

<details>
<summary>Original English</summary>

>> Yeah,

 wow.

 And

 and

 then

 you

 you're

you're

 doing

 this

 all

 all

 all

 the

 while

while

 other

 engineers,

 they're

 just

doing

 their

 thing,

 they're

 using

 these

things

 they

 don't

 even

 know

 about,

 they

don't

 want

 to

 know

 about

 you.

 I

 mean
</details>

>> 确实如此。

<details>
<summary>Original English</summary>

>> Exactly.
</details>

>> 他们或许知道你们的存在，但不必因此去调整——正如你所说，不必放慢脚步或者——

<details>
<summary>Original English</summary>

>> They

 might

 be

 aware

 of

 you,

 but

 they

shouldn't

 have

 to

 change

 their

 just

 as

you

 said,

 slow

 down

 or
</details>

>> 对。

<details>
<summary>Original English</summary>

>> Yep.
</details>

>> 不过后来我们确实在这方面收到了一些极好的反馈。比如——

<details>
<summary>Original English</summary>

>> But

 then

 we

 did

 get

 amazing

 feedback

 on

some

 of

 this.

 Like
</details>

>> 起初人们会问：“你——你在干什么？你怎么——为什么改我的代码？这……我接受不了。”但很快他们就会说：“噢，太棒了。”就像——我走开一会儿，我的代码就变好了。而且我不需要费心思去查“这样做对不对？”，因为要是那样做不对，你们早就把它清理掉了。就像是，当有专门的人在像保洁一样巡检整个代码库时，针对“这该怎么写？”，复制粘贴反而成了正确答案。只要找一个别人曾经这么写过的地方，复制过来，继续做你的事，而且你有证据表明这大概率是一个合理的方案。因为如果是错的，我们早就把它修好了。

<details>
<summary>Original English</summary>

>> at

 first

 people

 are

 like,

 "What

 What

 are

you

 doing?

 How

 Why

 are

 you

 changing

 my

code?

 This

 like

 I'm

 not

 okay

 with

 this."

And

 very

 quickly

 they're

 like,

 "Oh,

 this

is

 great."

 Like

I

 go

 away,

 my

 code

 just

 gets

 better.

Like

and

 I

 don't

 need

 to

 worry

 about

 looking

up

 like,

 "Is

 this

 the

 right

 way

 to

 do

 a

thing?"

 Because

 if

 it

 was

 the

 wrong

 way

to

 do

 a

 thing,

 you

 would

 have

 gotten

 rid

of

 it

 already.

 Like

 when

 you

 have

someone

 that

 is

 going

 through

 and

 just

janitoring

 the

 code

 base

 like

 that,

copy

 and

 paste

 becomes

 the

 correct

answer

 for

 how

 do

 I

 do

 this?

 Like

find

 someone

 else

 that

 did

 it

 once,

 you

copy

 it,

 you

 move

 on

 with

 life,

 and

 you

have

 evidence

 that

 it's

 probably

 a

reasonable

 answer.

Cuz

 if

 it

 was

 wrong,

 we

 would

 have

 fixed

it

 already.
</details>

### 确定性重构与 AI 重写的对比

>> 这非常有意思，因为在今天，显然如果你要做一次大规模重构，大家自然会去用的工具就是 AI，正如我们看到那么多公司在……方面取得了巨大成功。在这个意义上，AI 有能力……而你当时面临的挑战是，你面对的是一个庞大无比的代码库。纯手工重写是不可行的，但在谷歌，你们想出了一种非常聪明的半自动化方法，它是基于相当硬核的语言解析，并找出了全新的途径，让你能够形式化地、甚至可能形式化地或至少证明这东西会是正确的，这是大多数团队所没有的能力，甚至没有相关专业知识去做的。而现在每个人都有的能力则是：“噢，AI，去搞定这个，去做测试，搞定这一切。”然而，我想谈的是，用 AI 重写感觉依然比你们当时的做法要不可靠得多，你们的做法确定性要高得多。

<details>
<summary>Original English</summary>

>> It's

 very

 interesting

 because

 today,

obviously,

 if

 you

 did

 a

 big

 refactoring,

the

 obvious

 tool

 that

 you

 would

 reach

for

 is

 is

 AI

 as

 we've

 seen

 with

 so

 many

companies

 having

 lots

 of

 success

 with

Well,

 in

 in

 the

 sense

 that

 AI

 is

 capable

of

 The

 challenge

 that

 you

 had

 is

 you

 had

this

 massive

 massive

 code

 base.

Rewriting

 it

 by

 hand

 would

 have

 not

 been

feasible,

 but

 at

 Google

 you

 came

 up

 with

a

 very

 clever

 semi-automated

 approach,

which

 was

 based

 on

 pretty

 hardcore

 uh

language

 parsing

 and

 and

 coming

 up

 with

new

 ways

 where

 you

 could

 formally,

 maybe

even

 formally

 or

 or

 at

 least

 prove

 that

this

 thing

 will

 be

 correct,

 which

 is

what

 most

 teams

 would

 not

 have

 the

available

 capacity,

 even

 expertise

 to

do.

 What

 everyone

 has

 the

 expert

 the

capability

 to

 do

 right

 now

 is

 like,

 "Oh,

AI,

 go

 and

 do

 this

 and

 and

 do

 test

 and

all

 this."

 However,

 where

 I

 wanted

 to

get

 to

 like

 rewriting

 with

 AI

 feels

still

 feels

 so

 much

 more

 janky

 than

 what

you

 did,

 which

 was

 so

 much

 more

deterministic.
</details>

>> 是的。

<details>
<summary>Original English</summary>

>> Yes.
</details>

>> 我在想，你们在谷歌使用的这种技术，是否会在某个时候传播开来，或者大家……

<details>
<summary>Original English</summary>

>> And

 I

 wonder

 if

 this

 technique

 that

 you

used

 at

 Google

might

 at

 some

 point

 spread

 or

 or

 people
</details>

<!-- chunk 5/13 -->

### 确定性重构与零 Token 架构

就只能容忍像 AI 这种，你知道的，它可能行也可能不行的状态。

<details>
<summary>Original English</summary>

will just put up with like AI kind of, you know, like it might or might not work.
</details>

>> 我觉得如果你留心去找，它其实已经存在了。呃，尤其是在 Java 领域，呃，像 OpenRewrite 这样的工具，你基本上，呃，它每次运行只需要一点小小的配置，然后你就说：“这就是我想在 Java 代码里找的模式。这就是重写之后的样子。”然后，呃，它就会扫遍并，你知道的，飞速处理你所有的 Java 源文件，完成这项更新。事实证明，AI 工具在生成 OpenRewrite 规则集（recipes）方面非常非常擅长，这在 token 消耗上要便宜得多，准确率高得多，速度快得多，而且还像是有可审计性的。对吧？这是一种明显好得多的模式，而我——我们已经看过，呃，我想说是 Netflix 和 Uber 的演讲，我也可能记错了，嗯，专门讲大家似乎都在得出同样的结论：你需要的是一个声明重写意图的确定性工具。你可以让 AI，像是写个小技能来教、训练 AI 如何为这些工具创建配置，然后你就可以安心过日子了。在 C++ 领域实际上，我的几个好朋友现在开了一家创业公司。呃，它叫 Brontosaurus，呃，专门就是做那种声明式重写模式，呃，在非常高层次的意图层面，对 C++ 来说非常强大。

<details>
<summary>Original English</summary>

>> I think if you're looking for it, it's already out there. Um in the Java space in particular, uh tools like OpenRewrite, like you basically uh it's a little configuration per run for it and you say like, "This is the pattern I'm looking for in the Java code. This is how the rewrite would look." And uh it goes through and, you know, blasts through all your Java source files and and does that update. Turns out AI tools are really, really good at generating OpenRewrite recipes, which is way cheaper on token consumption, and way more accurate, and much faster, and like auditable. Right? It is a substantially better pattern and I we've seen uh talks from I want to say Netflix and Uber, I could be wrong, um specifically on like everyone seems to be coming to the same conclusion of what you need is a deterministic tool that declares the intent of the rewrite. You can have the AI like write a little skill to tell train the AI how to create the config for those tools and then you move on with life. In the C++ space actually, some good friends of mine have a startup right now. Uh it's called Brontosaurus uh that is specifically just about that sort of declarative rewrite pattern uh at a very high level of intent, very powerful for C++.
</details>

>> 是的，我、我、我喜欢利用 AI 来帮助生成确定性软件工具转换的想法。

<details>
<summary>Original English</summary>

>> Yeah, I I I like the idea of of using AI to help generate deterministic software tools transformations.
</details>

>> 是的。呃，Kelsey Hightower 最近做了一场关于类似“零 Token 架构”（zero token architecture）的精彩演讲。他的整个论点就是——而且我认为所有人都在得出同样的结论——不要把 AI 用作持续不断的推理。用 AI 来生成真正去干活的确定性工具，然后让 AI 去填补你无法解决的那部分问题的空白，或者去决定在哪里调用这个工具，诸如此类的事情。但如果你整个架构从头到尾全靠 token 消耗，那可能有一种更便宜、更有效的方式来做——

<details>
<summary>Original English</summary>

>> Yeah. Uh Kelsey Hightower gave a great talk recently on like zero token architecture. And like his whole thesis, and I think everyone is coming to the same conclusion, don't use AI for constant inference. Use AI to generate the deterministic tool that will actually do the work and then have AI fill in the gaps on the pro- parts of the problem that you can't solve or where to invoke the tool, things like that. But like if your whole architecture is token consumption for all time, it's probably a cheaper and more effective way to do
</details>

>> 是的，我、我最近刚听一位工程负责人跟我说，他们正在使用这些 AI 代码审查工具，这些工具挺不错的，但是非常昂贵而且缓慢。

<details>
<summary>Original English</summary>

>> Yeah, I I just recently heard a head of engineering tell me that they're using these AI code review tools which which are pretty good but very expensive and slow.
</details>

>> 对。

<details>
<summary>Original English</summary>

>> Right.
</details>

>> 这个人就说，等等，要不我们告诉 AI，行，我们偶尔做一次彻底的代码审查，但当它发现问题时，让它生成一条 lint 规则。

<details>
<summary>Original English</summary>

>> And this person said like hang on like what if we told the AI, okay like let's do a thorough code review every now and then but when it finds something let's have it generate a lint rule.
</details>

>> 太好了，求之不得。

<details>
<summary>Original English</summary>

>> Yes, please.
</details>

>> 那样既便宜又可重复，而且它不会再花上 30 分钟，还有那成本，而且它就是非确定性的。下次它可能找得到，也可能找不到。这、这让人很沮丧。就像这个人说的，你看，当我们明明知道存在某些问题。所以现在他们所做的，就是偶尔仍然运行一些这类的审查，当然了，但只要他们发现任何问题，就会启动，呃，推理 AI、几个 agent，然后说，好了，你们能不能给我们的确定性代码检查提出改进方案来帮助它。而且、而且这个灵感实际上来自于这个人听说了 Uber 是怎么做的——其实我、我想是，呃，听、听我说起过当我加入 Uber 时，我第一、第一周几乎都没法提交代码。太痛苦了，因为 linter 就是一直在拒绝，因为 Uber 有这么一种，呃，工程文化——

<details>
<summary>Original English</summary>

>> That which is cheap and repeatable and it will no longer take 30 minutes that the cost and also it's it's just non-deterministic. It might or might not find it next time. That That was a frustrating. Like this person was like look when we know we have certain things. So now what what they're doing is every now and then they still run some of these reviews and of course but whenever they find any issues then they fire up uh inference AI several agents and say all right, can you come up with an improvement in our deterministic linting and help it. And and the inspiration came actually from this person heard about how Uber actually I I think it was uh heard heard me talk about when I joined Uber, I could be wrong the first the first week. It was so painful cuz the linter just kept rejecting it because Uber had this uh engineering culture that
</details>

>> 没错。

<details>
<summary>Original English</summary>

>> Yep.
</details>

>> 在 AI 出现之前，每当你看到有什么东西损坏了，你就直接加一条 lint 规则。架构规则全都在 lint 规则里。你不可能做出类似——我们有我们的架构，而你不可能错误继承，因为 linter 会说，呃-呃，你不能、你不能从比如 Builder 继承自一个我不知道、不知道是 Composer 还是别的什么东西。

<details>
<summary>Original English</summary>

>> pre-AI, whenever you saw something break, you just put a lint rule. Architectural rules were all in lint rules. You could not have something like we had our architecture and you could not inherit the wrong way cuz the linter would say like uh-uh, you cannot you cannot inherit from like a builder cannot inherit from a I don't know what what a composer or whatever that was.
</details>

>> 是的。不，我认为这完全说得通。就像，让我们尽量把吃过的苦头只吸取一次教训，把这些规则固化在某个确定性的地方，平等、恰当且公正地应用它们，像是——并且把代码审查中有意思的部分留下来，像是确保我们在代码审查中关注的部分，仅仅是需要人类去做的事情。对吧？这在当时是成立的。我认为并非所有人都对静态分析和 linting 投入到那种程度。他们本该这么做的。而在当下它同样成立。对吧？就像我们无法审查所有东西，但像是有一些地方确实需要——像是这种人类注意力是花得其所的。

<details>
<summary>Original English</summary>

>> Yeah. No, I think it makes perfect sense. Like let's try to learn our hard lessons only once, codify those rules somewhere deterministic, apply them equally and appropriately and fairly like and leave the interesting parts of code review like make sure that the parts of code review that we're focusing on are only the things that humans need to be doing. Right? Which was true then. I don't think everyone invested in linting and static analysis that quite to that extent. They should have. And then it's equally true now. Right? Like we can't review everything but like there are places that require like this human attention is is well spent.
</details>

### 赞助商播报：WorkOS 与 Turbo Buffer

>> Titus 刚才论证了只吸取一次惨痛教训，然后把它们写成规则，并将人类的注意力留给真正需要它的事情。这与你希望 AI agent 权限运作的方式几乎如出一辙，这就引出了我们本季的赞助商 WorkOS。

WorkOS 为 B2B 和 AI 原生公司提供向企业客户销售所需的认证基础设施，支持 SSO、SCIM、RBAC，以及现在的 AI agent 授权。WorkOS Airlock 是基于意图的访问控制。大多数访问控制只询问你是谁。Airlock 还会查看 agent 在尝试执行操作的那一刻试图去做什么。明确的规则（比如任何 agent 都不能删除云资源）以纯代码形式运行。对于更模糊的判定，则由 AI 在运行时对策略进行评估。你用纯英语编写这些策略，Cloth 可以将你现有的策略从 Notion 或 Jira 中提取并为你导入。无论你的 agent 是 Cloth 还是 Devin，它们都通过单一访问点连接，而你的 MCP 服务器就位于该访问点之后。Airlock 是建立在你现有权限之上的全新层级，这意味着 agent 永远无法获得超出唤起该 agent 的人员以外的更高权限。当出现高风险操作时，Airlock 可以升级呈报给人类审批，比如通过 Slack。这与 Titus 所描述的想法相同：规则只需写一次，并将人类的注意力仅花在需要它的调用上。你可以在 workos.com/airlock 申请早期访问体验。

我还要提一下我们的特约赞助商 Turbo Buffer，这是一款构建在对象存储之上的超级搜索引擎，具有极高的可扩展性、快速且便宜。

你能有多少次机会亲眼见证一场实时的系统重写？有了 TiKV 团队，我们终于可以了。他们正在从第一性原理出发彻底重新设计其存储架构，以实现规模化下更快、更便宜且更可靠的搜索。

名为 Turbo Buffer V3 的新系统尚未进入生产环境，但它已经通过了 CI。而在 9 月份重写刚开始时，它的性能远不及当前的生产版本 V2。

TiKV 团队一直在对查询计划进行极致的性能调优（perf maxing），直到它们达到或超过 V2 的速度，并且这一切都在公开场合进行，一直持续到 V3 正式上线生产环境。看到他们的进展真是太酷了。新系统在大多数指标上从最初比原来慢 10 到 100 倍，变成了在冷向量搜索、按属性排序或混合搜索等方面快了数倍。

V3 系统在全文搜索等领域目前仍然偏慢，但相比性能调优刚开始时的慢 100 倍，现在仅慢了 1 到 2 倍。

TiKV 团队在他们的开发日志中确切地分享了他们是如何优化的，包括分组计数聚合（group count aggregation）、压缩列编码、批量评分等诸多内容。

目前这些成果很多都属于基础底层工作，但在接下来的几周里，该团队将展示一些非常酷炫的系统级工作成果。

不过等等，团队为什么要进行彻底重写呢？

这是因为搜索正在发生变化，Turbo Buffer 也是如此。TiKV 最初是一个向量数据库，但它已经不再仅仅是一个向量数据库了。它已经演进成为一个用于搜索的高性能数据库。

V3 放弃了向量主索引，所有索引将共享同一套列式存储系统。

每个查询都将在向量化查询引擎上运行，这是你在搜索数据库中通常见不到的，但这将带来极快的速度，并且整体上成为一个非常快速的数据库。

Turbo Buffer 团队一直在其工作日志中记录这段历程，你可以在 turbobuffer.com/v3 跟踪关注。亲眼见证它是如何构建起来的真是一件乐事。

<details>
<summary>Original English</summary>

>> Titus just made the case for learning the hard lessons once, then writing them as rules, and saving the human attention for the things that really need such. That is pretty much the same way you want permissions for AI agents to work, which brings us to our season sponsor, WorkOS. WorkOS provides the auth infrastructure that B2B and AI native companies need to sell to enterprise customers with SSO, SCIM, RBA, and now authorization for AI agents. WorkOS Airlock is intent-based access control. Most access control only asks who you are. Airlock also looks at what the agent is trying to do at the moment it tries to do it. Clear-cut rules like no agent deletes cloud resources are run as plain code. For the fuzzier calls, an AI just evaluates the policy at runtime. You write those policies in plain English and Cloth can pull the ones you already have out of Notion or Jira and import them for you. Your agents, whether that's Cloth or Devin, connect through a single access point and your MCP servers are behind this access point. Airlock is a new layer on top of your existing permissions, which means that an agent can never get more access than the person who invoked the agent. When something risky comes up, Airlock can escalate to human for approval, say over Slack. It's the same idea Titus described. Write the rules once and spend human attention only on the calls that need it. You can request early access at workos.com/airlock. I also want to mention our presenting sponsor, Turbo Buffer, a ridiculously scalable, fast, and cheap hyper search engine built on top of object storage. How often do you get to see a rewrite playing out in real time? With the TiKV team, we finally can. They are completely redesigning their storage architecture from first principles to make search faster, cheaper, and more reliable at scale. The new system, called Turbo Buffer V3, is not yet in prod, but it already passes CI. And when the rewrite started in September, it was not nearly as performant as the current production version, V2. The TiKV team had been perf maxing query plans until they are fast or faster than V2, doing all this in public all the way up to the V3 production launch. And it's so cool to see their progress. The new system went from being 10 to 100 times slower across most metrics to being several times faster on things like cold vector search, order by attitude, or hybrid search. The V3 system is still slower in areas like full-text search, but only one to two times slower versus 100 times slower when this perf maxing started. And the TiKV team is sharing exactly how they optimize things in their development logs with things like group count aggregation, compressed column encodings, batch scoring, and many more. A lot of these wins are basic foundational work right now, but the team will be showing some very cool systems work over the next few weeks. But hang on, why is the team doing a full rewrite? It's because search is changing, and so is Turbo Buffer. TiKV started as a vector database, but it is no longer a vector database. It has evolved into a high-performance database for search. The V3 discards the vector primary index, and all indexes will share the same columnar storage system. Every query will run on vectorized query engines, which is something you don't usually see in search databases, but which will result in both very fast and just generally a very fast database. The Turbo Buffer team is keeping a work log of their journey and you can follow along at turbobuffer.com/v3. It's a blast to see how it's being built.
</details>

### 《Google 软件工程》的成书背景

>> 说到汲取惨痛教训并将其沉淀成文档，我们能谈谈《Google 软件工程》（Software Engineering at Google）吗？就是那本你广为人知的书。这个想法是怎么来的？它是如何成形的？你最初的动机是什么？

<details>
<summary>Original English</summary>

>> Speaking of hard hard lessons and and documenting them, can we talk about software engineering Google, the book that you're quite well known for? How did the idea come? How did it come together? What was your motivation to start with?
</details>

>> 所以，这在一定程度上是处于尾声阶段，想着“嘿，也许我们会推出这些开发者工具。也许我们需要解释一下为什么 Google 的开发者工具会是现在这个样子”，因为否则的话就会有点像是——

<details>
<summary>Original English</summary>

>> So, this was uh a little bit at the tail end of hey, maybe we'll ship the developer tools. Maybe we'll need to explain why Google's developer tools are the way they are cuz otherwise it'll be a little bit of
</details>

<!-- chunk 6/13 -->

就像外星人降临，试图给你一些在你的世界里根本说不通的东西。我们之所以有盲目自信去攻克那类任务，部分原因在于我们此前一直在四处进行这种大规模重构。当你撞见所有被某位工程师视为巧妙解决方案的东西时，这意味着我的怪人同袍们经历过太多次：“噢，没错，我能看明白你怎么会觉得那是个好主意，但千万别那么做。”比外面任何人都见得更多。

<details><summary>Original English</summary>
like aliens came down and they're trying to give you something that doesn't make any sense in your world. Part of the reason that we had the hubris to like tackle that sort of task was because we had been doing this refactoring at scale, you know, everywhere. And when you run into everything that any engineer thought was a clever solution to their problem, it meant that the the my my cadre of of weirdos has run into so many Oh, yep, I can see how you thought that was a good idea. Don't do that. Like more than more than anyone else out there.
</details>

>> 嗯，你说的可是业界最历经沙场的一批人，仅仅是因为长年累月在这些大规模系统上工作。

<details><summary>Original English</summary>
>> Well, you're talking some of the most kind of battle-scarred people in the industry just just because you're working on these large-scale systems for such a long period of time.
</details>

>> 而且这还不是生产环境留下的伤痕。这是像测试和本地代码设计方面的伤痕。业界其他人仿佛都有这种生产经验，而我的工作到合并代码就结束了。比大多数人而言，我更懂开发、API设计、测试以及维持作为工件的代码库正常运转。呃，但这确实意味着，我不知道，在某种意义上我更像个局外人。

<details><summary>Original English</summary>
>> And it's not the production battle scars. It's the like testing and like local code design battle scars. Like everyone else in the industry has like all this production experience and like my job ends at merge. Like I know more about development and API design and test and keep the code base as an artifact working than most. Um but it does mean I don't know. I'm kind of an outsider in that sense.
</details>

### 《Software Engineering at Google》成书背景

>> 很有意思的是，我是说，这本书对于代码如何推向生产环境讲解得非常非常透彻，但它并没有涵盖运维部分，我想这大概是这本书的历史缘由吧。

<details><summary>Original English</summary>
>> Well, interestingly enough, the I mean, the book is very very thorough on how it gets to production, but it it it it does not cover the operational part, which I guess it's it's the history of the book.
</details>

>> 并没有这么一本历史书，如果真写的话，那这本书大概得有两倍长了。你们是怎么把那本书攒起来的？因为有些部分是你写的，而谷歌内部其他人撰写了不同的章节。

<details><summary>Original English</summary>
>> There isn't a history book, which Well, then the the this book would be like twice as long. How did you pull that book together? Because you wrote some parts of it. Other folks inside of Google wrote different chapters of it.
</details>

>> 所以，它非常符合SRE系列书籍的精神。呃，也就是设法邀请特定领域的专家来贡献一些有价值的内容。呃，然后书封上的三个名字：我自己、Hiram Wright和Tom Limoncelli。Hiram和我算是那本书的技术领导角色。Tom技术非常过硬，但多年来一直是我们的技术写手朋友。

<details><summary>Original English</summary>
>> So, it's very much in the spirit of the SRE books. Um like try to get the expert on or an expert on given topics to to contribute something useful. Uh and then the three names on the front of the book, myself, Hiram Wright, and Tom Limoncelli, Hiram and I were kind of the technical leadership for that. And Tom has is plenty technical, but is has been our tech writer friend for many many years.
</details>

>> 嗯嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 呃，所以他负责了大量编辑、结构和组织方面的工作。而Hiram和我一直是个搭档组合：呃，Hiram生成了数以百万计的修改，呃，并发给我审查，而我拥有审查代码库中几乎所有内容的权限。因此，人人都知道我们俩就是把一切收拾整洁的那两个人。所以我们带着那些伤痕，由我们来主导。接下来的诀窍就是物色专家去写出高质量的内容。其中有些初稿就很棒，很多内容则经历了一番反复打磨之类的。

<details><summary>Original English</summary>
>> Uh so, he handled a lot of the like editorial, structural, organizational stuff. But Hiram and I had been the tag team of uh Hiram generated millions of edits uh and sent them to me for review, and I had the permissions to review almost everything in the code base. And so, like everyone knew us as like the the those two guys that clean everything up. So, we had those scars, and so we led that. And then the the trick was like finding the experts to to write something high quality. Some of those were great from the start. A lot of that took a, you know, bit of goes right and stuff.
</details>

>> 也就是迭代，对。

<details><summary>Original English</summary>
>> Iteration, yeah.
</details>

>> 呃，整个任务实际上历时将近两年。呃，当然不是全职的。大部分时间里，我们最多可能投入四分之一到一半的精力。呃，但是是的，我们从太多人那里收集整理了过多的文字，而且直到看到那本书的印刷样书，我才意识到我们究竟超出了多少。我当时就想：“哇，真厚。”

<details><summary>Original English</summary>
>> Um the whole task was actually almost 2 years. Uh certainly not full-time. Like we were at most probably putting in quarter to half-time in most of that time. Um but yeah, like we wrangled together way too much text from way too many people, and I don't think I realized just how much we overshot until I saw a printed copy of that book. I was like, "Wow, that's huge."
</details>

### 谷歌的代码可读性机制

>> 是啊，哪怕放到今天，呃，我仍然推荐这本书，因为它能让人极好地理解当年的谷歌是如何运转的。显然自那以后它一直在演进，但一家公司从零起步到构建起重要的生产系统，其间冒出过一堆可能看起来没那么合理的做法。你谈到了诸如单一代码库（monorepo）、严格的代码审查流程、谷歌内部如何设立了可读性审查流程等内容。也许我们可以聊聊这一点：据我所知，谷歌是唯一一家在过去的代码审查中，不仅有负责该系统某部分并了解该部分的工程师进行审查并表示通过，而且还设有可读性审查的公司。什么是可读性审查？

<details><summary>Original English</summary>
>> Yeah, and and even today, uh I I do recommend the book because it gives a really good understanding of how the Google at the time worked. Obviously, there's been evolving since, but how a company going from zero to building important production systems came over with a bunch of stuff that might not make as much sense. And you talk about things like like monorepo, like the the stringent code review process, how there's a readability process at Google, and maybe we can talk about that as as part of Google is the only company I know where for code review, back in the day, they didn't just have code review like an engineer who owns this part of the system and understands reviews it and says it's okay, but that you had a Google had a readability review. What is readability review?
</details>

>> 那么，对于任何提交进来的变更，呃，相关人员——无论是作者还是审查者，或者作者或某位审查者——必须具备两个不同的权限标记。首先是所有权问题。也就是说，必须有人位列获授权修改这些文件的人员名单中。第二点则是必须有人切实通过认证，表明我们相信你懂得在那个代码库中用相应语言写出符合语言习惯的代码（idiomatic code）。这是为了尽量确保所有代码相对一致，具备通用模式，而不是在重复造轮子所迈出的一步，呃，因为一致性具有战略价值。所以可读性流程就是必须要有人为此获得认证。

至于如何获得认证？最初的做法是3号员工与每位新员工坐在一起，带领他们过一遍首个变更。这种方式后来无法拓展了，于是他们找了一批其他人尝试代行Craig的职责。他们会带领你过一遍你的第一个重大的实质性变更。

随着时间的推移，情况演变到大多数变更不再是我从头写一个新组件；变更发生在现有产品上，比如你在这里或那里做些小修小改，添加一个功能等等。因此，要找出一个足够有分量、能一次性证明你掌握了一切的内容变得有些困难，整个过程给人的感觉也有点更像是一种入会折磨仪式。所以，随着岁月流转，呃，我想是Java团队的人开的头，它从那种一锤定音的形式转变为明确的导师培养计划。呃，你做你的日常工作，在你的团队审批通过之后，我们就会以轮流分派的方式，从Java导师池中指派某个人去审视一遍，看看这里是否有任何值得评论的实质性、有趣内容，以此来提升代码质量并确保其符合整体规范。你可能会注意到，这意味着如果你处在一个本来就具备极高标准的团队里，可能就没有什么好评论的，对吧？那你可能很快就能毕业。

<details><summary>Original English</summary>
>> So, for any change that's going in, uh someone that is involved, either the author or the reviewer or author or a reviewer, has to have two different permission bits. First is that ownership thing. So, someone has to be in the list of people that is authorized to change these files. And the second is someone has to actually be certified in we believe you understand how to write idiomatic code in this code base in that language. And this is a step towards trying to make sure that everything is relatively consistent and that there's common patterns and you're not like reinventing the wheel uh because the strategic value of consistency and so the readability process is someone has to be certified for that. How do you get certified for that? And initially that came as employee number three sat down with every new employee and walked them through their first change. That stopped scaling, so they got a bunch of other people to try to proxy being Craig. And they would walk you through your first big substantive change. And over time it got to the point where most change was not like I am writing a new component from scratch. It's an existing product, like you're making little edits here and there, you're adding a feature or whatever. So, finding something that was meaty enough to like demonstrate in one go that you knew everything it was kind of hard and the whole thing felt a little bit more like a hazing ritual. And so, over the years uh I think the I think people in Java started it, it moved from that sort of one shot to being explicitly kind of a mentoring program. Uh you do your normal work and after your team has signed off on it, then we will round robin assign someone from the pool of like Java mentors to go through and see like is there anything like substantively like interesting worth commenting on here to kind of up the quality of the code and make sure that it matches the rest of the the norms. And you might notice that means if you're on a team that already has great standards, there's probably very little to comment on, right? And you'll probably graduate pretty quick.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而如果你不在那样的团队里，并且你选择不去吸取任何教训，那你毕业大概就会非常慢，甚至根本毕不了业。呃，整套机制就演变成了那样。后来我们将那种导师辅导方式推广到了所有其他有可读性认证的语言中，并且许多年来一直是这套规范。自那以后我一直没再关注过它，你知道的，至少有一两年没看了，但是……

<details><summary>Original English</summary>
>> And if you're not and you choose not to learn any of the lessons, you will probably graduate very slowly, if at all. Uh and so that the whole thing kind of grew into that. And we expanded that sort of mentorship approach into all of the other readability languages and that's been the norm for a bunch of years. I haven't checked up on it since, you know, for at least a couple years, but
</details>

>> 但这非常有趣，因为在我看来，这仿佛把代码审查变成了，纯粹变成了对一门编程语言深度的教育培训。这是有意设计的，还是说纯属副产品？

<details><summary>Original English</summary>
>> But it's very interesting because it it feels to me like this turns code review into into just education in the depth of a programming language. Was this by design or was it just a byproduct?
</details>

>> 我认为这绝对是有意设计的。至少在我能够左右局面的那部分里，绝对是有意为之。呃，不过是的，当我大约三年前离开谷歌时，可读性机制有点像……我算得上是可读性项目的总体负责人。我认为这可能是科技界、甚至也许是全世界规模最大的教育项目，因为在任何特定时刻，都有数以万人参与其中。

<details><summary>Original English</summary>
>> I think it's absolutely by design. Certainly at the parts of it where I was pulling any of the strings was definitely by design. Um but yeah, when I left Google, uh you know, almost 3 years ago, readability was kind like I was kind of the overarching owner for the readability uh program. I would argue that might be the largest educational program in tech or maybe in the world cuz there were tens of thousands of people participating in that like at any given moment.
</details>

>> 而且你只要加入谷歌就会参与其中，你别无选择，并不是自愿参加的。

<details><summary>Original English</summary>
>> And then you just participated by by joining Google then you had no choice. It wasn't like a voluntary.
</details>

>> 没错。所以有些人当然对此非常恼火。

<details><summary>Original English</summary>
>> Right. And so certainly some people were super pissy about it.
</details>

>> 不过我猜这里面也有一个目标，它不仅仅是：第一步，你必须处理可读性专家给你留下的意见；第二步，如果你还有点自尊心的话，你大概会说“我想少收到点这种意见”，因为被提意见挺难堪的；然后第三步就像是，“你知道吗？行，我现在能拿到零评论了，我自己其实也想成为一名可读性专家。”那就到了不同的层级了。接着第四步，就是现在轮到你来提供反馈了。而且我猜通过那种反馈，也许你会结识一些人，也许你会开始建立某种，我不知道，师徒关系或友谊，谁知道呢。

<details><summary>Original English</summary>
>> But I guess there was also a goal where it wasn't just about like okay, so step one is you need to address the comments that readability expert puts on you. Step two, you probably say like I'd like to get fewer comments on them if you're if you have any sense of pride cuz it's kind of embarrassing. And then step three is like, you know what? Okay, I now get zero comments. I actually want to become a readability expert myself. And then that's different level. And then step four is now you are giving feedback. And and I guess through that feedback maybe you meet people, maybe you start to form some, I don't know, mentorship, friendships, who knows.
</details>

>> 是的。而且你还能看到代码库的其他部分，看到其他人在做什么，了解到其他可能正在研发的技术，这可以说是一个庞大、微妙、水面之下的信息共享项目。

<details><summary>Original English</summary>
>> Yeah. And you see other parts of the codebase, you see stuff that other people are doing, you learn about other tech that might be happening, like it was a huge, like, subtle, below-the-waterline, like, information-sharing program.
</details>

>> 在书中，你写到了团队的重要性，我想引用你的一段话。呃，在编程领域，孤独的手艺人极其罕见，即使他们确实存在，也无法在真空中取得超人的成就。

<details><summary>Original English</summary>
>> In the book, you write about the importance of a team, and I I I'll quote you. Uh in the realm of programming, lone craftspeople are extremely rare, and even when they do exist, they don't perform superhuman achievements in a vacuum.
</details>

<!-- chunk 7/13 -->

### 团队与 AI 时代的角色转变

……它们始终是灵感火花的结果，紧接着是英勇的团队努力。一支优秀的团队会绝妙地用好超级明星，但整体始终大于部分之和。然而，打造一支超级明星团队极其困难。

<details><summary>Original English</summary>
 Their always the result of a spark of inspiration, followed by a heroic team effort. A great team makes brilliant use of a superstars, but the whole is always greater than the sum of the parts. But creating superstar team is fiendishly difficult.
</details>

>> 是的。我觉得那一章不是我写的。

<details><summary>Original English</summary>
>> Yeah. I don't think I wrote that chapter.
</details>

>> 那是在你作为合著者的一本书里。所以，呃，我想就这一点反思一下，特别是结合 AI，因为现在我开始听到越来越多的人说，是的，过去我们谈论的是 10 倍工程师，直到——直到 22、2023 年。

<details><summary>Original English</summary>
>> It's in the book that you are a co-author of. So, uh I wanted to reflect on this, especially with AI, because now I'm starting to hear a lot more people say, yeah, in the past we talked about the 10x engineer, up to up to one up to 22 20 23.
</details>

>> 在那上面。

<details><summary>Original English</summary>
>> on that.
</details>

>> 但我现在开始听人说，像，噢，现在有了 100 倍工程师，也就是本身是一位优秀的工程师，并且极好地使用 AI；我们还听到许多故事，关于个人靠自己以及一大群 AI 代理做出英勇的努力。所以，我只是想问你，随着我们拥有更多的 AI 工具，团队的概念是如何维系的？以及一支杰出团队的概念。

<details><summary>Original English</summary>
>> But I am now starting to hear people say, like, oh, there's now the 100x engineer, which is this engineer who is a great engineer, uses AI amazingly well, and we are also hearing stories of individuals doing heroic efforts by themselves and with a bunch of AI agents. So, I just wanted to ask you how the concept of a team holds up as we have more AI tools. And the concept of of a standout team.
</details>

>> 是的。所以，我认为，无论你在所谓的 AI 信徒谱系中处于什么位置，我认为团队仍然是至关重要的。

<details><summary>Original English</summary>
>> Yeah. So, I think, regardless of where you fit on the spectrum of, like, AI believerism, I think the team is still critical.
</details>

比如，如果你相信代理是唯一的答案和向前的另一个方向，我们仍然在管理那个代理团队。而且我听到越来越多的声音在讨论这个问题，即眼下的问题在于我们需要把每位工程师变成一个代理团队的工程经理。而我们并没有这样做的培训、技能集或背景。比如，我们在要求他们做一件没有任何脚手架或指导的事情。

<details><summary>Original English</summary>
Like, if you believe that the agents are the only answer and the other direction forward, we're still managing that team of agents. And I've heard increasing number of voices talking about it as the problem right now is we need to make every engineer into an engineering manager for a team of agents. And we don't have the training or skill set or background to be have done that. Like, we're asking them to do a thing with no no scaffolding or guidance.
</details>

另一种选择是，你把 AI 和代理视作你的工具、你的 IDE，但这仍然是你与你周围的人类团队结合在一起。这仍然是团队行为。

<details><summary>Original English</summary>
The alternative is you think of the AI and the agents as your tools, your IDE, but it is still you in conjunction with the team of humans around you. It's still team behavior.
</details>

我认为在你和代理之间，社会动态和类似方面肯定存在差异，我要冒险说一句：代理是没有感情的。

<details><summary>Original English</summary>
I think there are certainly differences in the social dynamics and things like that between you and the agents, which I'm going to go out on a limb and say the agents don't have feelings.
</details>

>> 它们绝对没有。

<details><summary>Original English</summary>
>> They definitely do not.
</details>

>> 对吧？

<details><summary>Original English</summary>
>> Right?
</details>

>> 应该没有。

<details><summary>Original English</summary>
>> Should not.
</details>

>> 让我们暂时坚守这一底线。嗯，不过，呃，是的，像我认为理解、清晰的沟通，以及比如能够把事情写下来并从你脑海里表达出来，仍然是，你知道，一件非常重要的事情。像我——

是的，我认为归根结底无可置疑依然是团队。软件工程是一项团队运动，毫无疑问。

<details><summary>Original English</summary>
>> Let us hold that line for a bit. Um, but uh yeah, like I I think understanding, clear communication, and like being able to write things down and get it out of your head is still, you know, a substantial important thing. Like I Yeah, I think it is still un- unquestionably is still teams at the root of it. Software engineering is a team sport, period.
</details>

>> 另外，我想证明这可能仍然成立的一个相当天真的方法就是，如果我们看一下某些领先的 AI 公司、领先的 AI 实验室，比如 Anthropic、OpenAI。当我与那里的人交流时，我看到的是作为一个团队工作的杰出个人。你知道，比如 Claude Code，他们在两者面前巧妙地安排了一个公众形象，也就是创建它的 Boris Cherny，而且我认为他做得很出色。这让它非常亲切。这是一个人类，但在 Boris 背后有一支团队。

<details><summary>Original English</summary>
>> Also, I guess just one like pretty like naive way to just prove that this is probably still true is if we just look at some of the leading AI companies, the leading AI labs, the Anthropic's, the OpenAI's. When I talk to people there, I see standout individuals who are working as a team. You know, like Claude code, for example, they're they cleverly have a public face in front of both of them, Boris Cherney, who created it, and I think he did an amazing job. It makes it very relatable. This is a human, but there's a team behind Boris.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且——而且那个团队，当你——我和他们见面时，你能看出他们配合默契。他们在一起工作。他们互相信任。你知道，比如在某个时刻 Boris 会去度假。

<details><summary>Original English</summary>
>> And and that team, you can when I met them, you can tell that they gel. They work together. They trust each other. You know, like at some point Boris will be on holiday.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Right.
</details>

>> 你不会察觉，因为事情照样运转。

<details><summary>Original English</summary>
>> You will not know because things just happen.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Right.
</details>

>> 就像你说了重要的关键词，对吧？信任。

<details><summary>Original English</summary>
>> Like you said the important keyword, right? Trust.
</details>

### 心理安全感与学习文化

>> 确实。这其中很大一部分就是心理安全感的维度。另一件事我认为对 AI 实验室来说很自然，但对行业其余部分来说还远未成为主导，那就是边走边学。如果你看所有的研究，你知道，比如 DORA 对这些东西的研究，或者任何关于生产力、团队效能或任何类似方面的研究，归根结底总是归结为文化、心理安全感以及去学习的许可。

对吧，就是承认我不知道某些事情的许可。这是互相学习的激励。这是分享错误的激励，从而让团队只需要犯一次这样的错误。

你的 lint 规则或者 SRE 事后复盘文化，科技界每一个有效的架构和组织，其实都是关于信息流动和学习的。关于这一点，我认为有一个极好的视角。嗯，我很喜欢 Cat Hicks，呃，那位科技领域的心理学研究员。比如她的书《软件团队的心理学》（The Psychology of Software Teams）写得非常优美。她经常谈论，你知道，这些——这些事情，对吧？

嗯，同样，有一本我的一些朋友正在出版的关于 Google 平台工程的书。O'Reilly 上有抢先版章节。我可能为那本书写了关于教育的章节。

<details><summary>Original English</summary>
>> Right. Like a substantial part of this is the psychological safety aspect of it. The other thing, which I think is natural for the AI labs, but hasn't been nearly as dominant for the rest of the industry yet, is you're learning as you go. And if you look at all of the research, you know, like Dora research on stuff or any research on productivity or team efficacy or any of those things, like at root it always boils down to culture, psychological safety, and the the permission to learn. All right, it's the permission to admit that I don't know something. It is the incentive to learn from each other. It is the incentive to share your mistakes so that the team only has to do that once. Your lint rules or SRE postmortem culture, every effective structure and organization in tech is actually about information flow and learning. And I think a really great perspective on that. Um I love Cat Hicks, uh the psychology researcher for tech. Like her book, The Psychology of Software Teams, is beautiful. And like she talks about, you know, these these things a lot, right? Um similarly, there's a platform engineering at Google book that some of my friends are putting out. This early release chapters on O'Reilly. I might have written the chapter on education for that.
</details>

>> 呃，并且——

<details><summary>Original English</summary>
>> Uh and
</details>

>> 所以——所以非常令人惊讶/不令人惊讶。

<details><summary>Original English</summary>
>> So so very surprisingly {slash} not surprisingly.
</details>

>> 确实。不过是的，像教育是强有力的根基，比如让我们将这个错误的发生次数降到最低。让我们将我们做过的事情条理化。让我们允许人们承认自己不懂并去成长，因为这不是一场一次性的博弈。这是一场重复博弈。

如果你的团队下次表现更好，随着时间的推移你会做得更好。

<details><summary>Original English</summary>
>> Right. But yeah, like education is the powerful root for like, let's make this mistake a minimum number of times. Let's codify what we've done. Let's give people permission to admit they don't know and to grow because it's not a one-off game. It's a iterated game. And you'll do better over time if your team is better next time.
</details>

>> 我想回到心理安全感上，因为大约在 5 到 10 年前，我们在工程领导力圈子里经常谈论它。这是相当普遍理解的，即，你知道，一支好的团队感觉是一支安全的团队。例如，如果你犯了错误，作为工程师导致了一次宕机，简直就是字面上的，你推送了一段代码，而那段代码导致了宕机。我们应该进行不追责的事后复盘，在复盘中我们不会说，嘿，Gergely 推送了这段代码，他造成了宕机，因为那样现在——我是说，我感觉糟透了，但是——但是让我们来谈谈，比如，我们如何在系统层面上避免这种情况？为什么测试没有触发？为什么当他是团队的新人或者她是团队的新人时，代码立即就被部署了——比如也许一些入职引导会有所帮助等等等等。你如何定义心理安全感，它为什么重要？特别是只是扮演魔鬼代言人的角色，比如当我们谈论懂得很多东西的聪明工程师时，这对我们来说真有那么重要吗？因为我们——我们——我们应该了解我们的专业，对吧？我只是像——我有点抛开我的情感——

<details><summary>Original English</summary>
>> I want to go back to psychological safety because back about 5-10 years ago, we kind of would talk so much about it in engineering leadership circles. This was pretty well understood that you know, a a good team feels a safe team. If you, for example, make a mistake, you cause an outage as an engineer, like literally, you push a code and that code causes outage. We should have a blameless postmortem where we don't say that, hey, Gergely pushed this code and he caused the outage cuz that's now, I mean, I feel terrible and but let's talk about, like for example, how could have we avoided this at a system level? Why did a test not fire? Why was it rolled out immediately when he was a new joiner on the team or she was a new joiner team like maybe some onboarding could have helped yada yada yada. What how how do you define psychological safety and why is it important? Especially just playing devil's advocate like when we're talking about smart engineers who know stuff like is it all that important to us cuz we we we should know our thing, right? I'm just like go I'm kind of removing my emotional
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。但在这里。是的。呃，我们应该懂我们的专业。当然。所以我想说，要把这项数据确立下来有点困难，但是通过与 DORA 的人交流，在那些研究中，有一点我非常喜欢的是，我们可以根据你在心理文化问题上的得分，解释你——你的团队是否能达成目标的 30% 差异，对吧？比如我们可以给你们一份 15 道题的对错题，或者可能是李克特量表，但就是一份针对团队的 15 道题的评估，就能预测你是否能实现你的无论什么目标的 30%。这太疯狂了。

明白吗？这比任何其他信号都更强大。

比如，好吧。所以你认为我们都是工程师，这都只是计算机和技术，与情感毫无关系。给我找出任何哪怕稍微有如此强大成功预测力的事情来。

这就是人的问题，毫无疑问，对吧？

回到，对吧？这——这不是单次博弈。这是一场重复博弈。我经常引用 Fred Brooks 在《人月神话》随笔集中的话，对吧？而在外科手术式团队中——外科手术式团队是我在那本书中最不喜欢的一章，因为它的结构就好像我们永远只会做一个项目一样。让最优秀的人来做这个，让其他所有人在他们之下构建工具并编写文档。这非常等级森严。对。而且非常类似于权力动态疯狂。是的。对。但如果你永远只做一个任务，这也许说得通。相反，我们玩的是博弈论意义上的游戏。这不是囚徒困境，这是重复囚徒困境。有一种不同的策略。这种策略是：找到能够有监督地完成这项工作的最资浅的人，这样他们就能学习和成长，而你仍然能得到一个不错的结果。

然后接下来，更高级别的人就可以去解决他们尚不知道如何去做、或者没有人能够应对的事情。

对吧？这是构建它的唯一方式，这样才能实现成长。

但为了让这种成长发生，人们必须愿意承认他们不懂某件事。

而这会直接把你带回心理安全感和学习文化，对吧？比如，如果这是一种突出信息共享、学习和成长的文化，你就会成功。

<details><summary>Original English</summary>
>> Yeah. But here. Yeah. Uh we should know our thing. Sure. So I would say and it's been a little hard to like root this uh stat, but from talking with people in Dora, the the research the one thing that I love was we can explain 30% of the variance in whether or not you your team will hit its goals based on how you score on psych culture questions, right? Like we could give you a 15 question true false or maybe Likert scale like but like a 15 question assessment for the team and predict 30% of whether or not you will hit whatever your goals are. That's insanity. All right? That is more powerful than any other signal. Like, okay. So you think that we're all engineers and this is all just computers and tech and emotions have nothing to do with it. Find me anything that's even remotely that powerful predictor of success. It's a people problem like period, right? And going back to, right? It's it's not a single shot game. It's an iterated game. I regularly cite Fred Brooks in the Mythical Man-Month essays, right? And in the surgical team like at the surgical team is my least favorite chapter in that book because it's structured as if we're only ever going to do one project. Get the best person to do this, get have everyone else build the tools and do the documentation under them. It's very hierarchical. Right. And it's very like power dynamics mad. Yeah. Right. But it might make sense if you're only ever going to do one task. Instead, we're playing like in a game theory sense. It's not prisoner's dilemma, it's iterated prisoner's dilemma. There's a different strategy. And the strategy is find the most junior person that can do it with supervision so that they learn and grow and you still get a decent outcome. And that next, like the higher level people can solve something that they don't know how to do yet or that like no one else can tackle. Right? This is the only way to like structure it so that growth happens. But in order for that growth to happen people have to be willing to admit that they don't know a thing. And like that brings you straight back to psychological safety and learning culture, right? Like if it is a culture that highlights information sharing, learning, and growth you will succeed.
</details>

>> 而且——而且你提到 AI 实验室已经采取

<details><summary>Original English</summary>
>> And and you mentioned that the AI labs already take
</details>

<!-- chunk 8/13 -->

这个想当然，而我准备……

<details><summary>Original English</summary>
this for granted and I'm going to
</details>

>> 因为他们不知道真实情况是什么样的。

<details><summary>Original English</summary>
>> Because they don't know what they're like
</details>

>> 好吧，我换个说法，比如AI实验室有几点优势。首先，业务蓬勃发展。他们正在增长。营收在增加。客户在增加。融资在增加。人员编制在增加。他们的团队只在不断扩张。他们处于超高速增长中。就像我们见过的处于超高速增长期的奈飞（Netflix）和优步（Uber）这类公司一样，这里的增速甚至更快。你的股权价值也在增加。所以你不需要去担心绩效考核之类的事，因为绩效考核通常关乎我能拿多少奖金、能拿多少等等。但是当你在一个像这样发展的公司，你的股权价值在上涨，你只要专注于帮助公司取得成功，无论你的头衔是什么，你的财务回报部分就都有了保障。其次，因为他们正在构建新技术，而且他们知道没有人懂，所以他们就直接说：好吧，我不知道，我正在向你学习。这是我学到的东西。所以这一切都很自然。相比之下，那些可能不会像这样增长的公司，他们可能也还在使用比如说AI，但现在说“我不知道”的动力就减少了，因为接下来会有绩效考核。你想表现得最聪明。你不想让大家觉得，嗯，这个人经常说不知道。你的奖金就会变少。你可能会被列入绩效改进计划（PIP），因为你现在所处的公司每年都会淘汰6%的人。

<details><summary>Original English</summary>
>> Well, I'm going to paraphrase it like with the AI labs have a few things going. First of all, business is booming. They are growing. Revenue goes up. Customers goes up. Funding goes up. Headcount goes up. Their teams are only ever expanding. They're in hypergrowth. Like we we've seen companies like Netflix and Uber in hypergrowth, this is even faster. Your equity also goes up. So you you don't need to worry about things like performance reviews because performance reviews are typically important where like how much bonus am I going to get, how much. But when you're at a place that goes like this and your equity goes up, your your financial part is taken care of just by focusing on helping the company succeed regardless of your titles. Second of all, because they're building new technology and they know no one knows, so they just tell okay, I don't know, I'm learning from you. Here's what I learned. So it's just all natural. Whereas compared to company that might not grow like this, they might still be using let's say AI, but now there's less of an incentive to say I don't know because there's a performance review coming up. You want to look like the smartest. You don't want people to say like well, this person says I don't know a lot. Your bonus will be lower. You might be put on a performance improvement plan because you're now at a company that every year let's go a 6% of people.
</details>

>> 对。

<details><summary>Original English</summary>
>> Right.
</details>

>> 你的目标突然就变成了：我只是不想垫底。我想保住这份工作，但这已经不是保不保得住的问题了。现在变成了……

<details><summary>Original English</summary>
>> And your goal is suddenly going from like I just don't want to be there. I want to hang on to this job, but it's not hanging on. It's now
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Uh-huh.
</details>

>> 而且你现在可能也会提防你的队友，因为现在有了内部竞争。你想霸占那个项目。

<details><summary>Original English</summary>
>> And you also you're now wary of maybe your teammates because now there's internal competition. You want to hog that project.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 所以这就是一个巨大的差异了。

<details><summary>Original English</summary>
>> And so this is a a huge difference then.
</details>

>> 是的，这太巨大了。比如如果你进入这样一种模式，认为团队成果才是决定你个人成功的关键，那么你就更容易意识到：好吧，我不一定非得拥有这一个亮眼的任务。团队会因为有人做了这件事而取得成功，下次可能就轮到我了。如果分解成那种个人主义，比如我不信任我对面那个人，或者你知道，就在我身边肩并肩的人，比如即使我们在同一个团队，我们也在苟延残喘，并且你知道，在争夺关注度和成功。那不是创新的秘诀，也不是增长的秘诀。那是停滞不前的温床，而且只会变得很糟糕。

<details><summary>Original English</summary>
>> Yeah, it's huge. Like if you get into the mode of believing that the team outcomes are what matter for your own success, then it is much easier for you to realize like okay, I don't have to have this one shiny task. Like the team will be successful by virtue of someone doing this and it might be my turn next. If when it breaks down into that like individualism and like I don't trust the guy across the way from me or you know, right shoulder to shoulder to me like even though we're on the same team, we're scraping by and like you know, fighting for attention and success. And that's not a recipe for innovation and growth. Like that is a recipe for stagnation and and just bad.
</details>

### 裁员对工程师与企业文化的冲击

>> 我认为你知道的一个显而易见的事，就是对心理成长没有好处，或者说极其不利的，就是裁员。

<details><summary>Original English</summary>
>> One of the obvious things that I I assume you know, is is is is does not do good for psychological growth or is terrible for it is layoffs.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 你能根据你的观察谈谈吗，我们都见过了，对吧？我们大家都经历过，在2022年、2023年发生了一连串的裁员。现在各大公司又在裁员了。当时那与利率有关，与零利率时期的过度招聘以及增长放缓有关。现在有些公司实际上公开声称是因为AI。有些公司没那么公开，但我们发现比如Meta想缩减团队规模，是因为他们认为AI能发挥作用。根据你在发生裁员的公司的观察，这如何改变了软件工程师的表现、工作和思考方式？请结合你自己的经历以及你交流过的人来谈谈。

<details><summary>Original English</summary>
>> Can you tell me based on your observation and then we've seen right? Like you we've all been part of it and in 2022 2023 there has been a series of layoffs. Right right now companies are doing it again. Back then it was to do with all all this interest rates and and over hiring during zero interest rates and and growth kind of going down. Now some companies are are actually openly saying that it's AI. Some are not as openly, but we find out that meta for example wanted to reduce team sizes because they thought that I will be there. From your observations at a company where a layoff happens, how does it change how software engineers show up, work, think? Speaking both about your experience and people you talk with.
</details>

>> 我是说，这压力很大。比如，我经历过所在领域发生裁员的情况，接下来的几周或几个月里，每次一对一交流开头都是：“那么，你怎么样？”比如，“你应对得如何？”就像，存在大量这种……是的，对绩效的负面影响，比如，“好吧，在我们实际回到工作之前，我们必须先在情感上相互支持。”

而且我非常怀疑在管理层针对这一切的核算中，他们是否考虑到了大量——你知道的——生产力损失和浪费的时间，比如，“是的，大家压力都很大。大家都在花时间打磨简历，以防自己成为下一个被裁的人。大家把一对一的时间花在心理疏导上，而不是做规划。”

这其中存在巨大的隐性成本。而且这真的很打击士气。它让人深刻体会到——它提醒了人们：好吧，这只是一种商业契约。这并不是一种生活方式选择。

而且如果我付出额外的努力并不能让我获得额外的安全感，那么意义何在呢，你懂吧？而且……它带来了很多文化上的包袱。这也是我实际上非常喜欢Adobe的一点：Adobe很长一段时间都是同一位CEO。他刚卸任，现在有了继任者。但他经历过大衰退危机。

他们在那个时期进行过一些裁员。他看到了那有多么打击士气、影响公司生产力以及其他一切……

他吸取了教训，比如，我们当时以为这在数字上讲得通，但这对公司的灵魂不利。那不是我们想成为的公司。

因此，Adobe在过去几年没有进行裁员。虽然随着事务优先级的重新调整，会有各个团队局部调整的情况，但并没有那种波及所有人的大范围裁员……

<details><summary>Original English</summary>
>> I mean, it's stressful. Like uh it I've had experiences of there being layoffs in the area and just it it'll be weeks or months of every one-on-one starts with, "So, how are you doing?" Like, "How are you coping?" Like, there's this huge amount of yeah, negative performance influence of like, "Okay, we got to like emotionally support each other first before we actually even get back to doing like the work."

And I am very skeptical that in the executive accounting on all of this that they're taking into consideration just the sheer amount of, you know, lost productivity and lost time from like, "Yeah, people are stressed. People are spending time brushing up their resume in case they're next on the chopping block. People are spending that one-on-one time like in therapy instead of in planning."

Uh it's it is a huge hidden cost to all of that. And it's really demotivating. It drives home like it is a reminder that okay, this is just a business obligation. This is not a lifestyle choice.

And if me putting in extra doesn't give me extra safety on this, then what's the point, you know? And like it there's a lot of cultural like baggage that happens for that. And it's one of the things that I actually really liked about Adobe was Adobe's had the same CEO for a long time. He just stepped down. He has a replacement now. But he was there for like the Great Recession crash.

And they did some layoffs at that era. And he saw how much it hurt morale and company productivity and all of the rest of that and and he learned like it we thought it made numeric sense at the time, but it was not good for the soul of the company. And that's not the company that we want to be.

And so Adobe didn't have the the layoffs in the last few years. Like there's group by group like local things as things get re-prioritized, but it's not the sweeping all that
</details>

>> 但我们看到大多数大型科技公司都经历了裁员，尤其是在2023年。

<details><summary>Original English</summary>
>> but we we've seen that at most of big tech has had it especially in 2023.
</details>

### 开发者生产力与衡量体系

>> 是的。说到Adobe，你几年前去了Adobe。你在Adobe专注于什么？

<details><summary>Original English</summary>
>> Yeah. And speaking of Adobe, so you've moved to Adobe a few years ago. What are you focused on at Adobe?
</details>

>> 在那里我是一名非常资深的IC，专注于开发者体验。

我常说这是一种委婉的说法。开发者体验其实就是关乎生产力的业务。我们只是足够清楚，不会宣称自己能量化生产力。它不是……

<details><summary>Original English</summary>
>> So, there I'm very senior IC focused on developer experience.

I happen to say this is a polite fiction. Developer experience is the business of productivity. We just know enough not to say that we can measure productivity. It is not given
</details>

>> 不像麦肯锡，我和Ken还就此产生过共鸣。

<details><summary>Original English</summary>
>> Unlike McKinsey who me and Ken have bonded over.
</details>

>> 是的。那个太糟糕了。

<details><summary>Original English</summary>
>> Yeah. That was that's horrible.
</details>

>> 我们会在下方的节目说明中放一个链接。

<details><summary>Original English</summary>
>> We'll put a link in the show notes below.
</details>

>> 是的。所以，这关乎我们需要什么工具、文化以及你知道的所有东西，来改善作为开发者的体验，并让你更具生产力和效率，因为大多数公司在工程薪酬上的支出比其他任何事情都多。

<details><summary>Original English</summary>
>> Yeah. So, it's it's what do we need for, you know, tools and culture and, you know, all of the things to improve the experience of being a developer and make you more productive and efficient because most companies spend more on engineering comp than anything else.
</details>

>> 那么，至今你一直专注于此，并在Adobe以及某种程度上在Google都从事这方面的工作。你目前对开发者生产力有哪些认识？这与AI、代码工具、产出、指标等等这些东西有什么关系？我们可以衡量什么？什么是值得衡量的？又有哪些事情是很难了解的？

<details><summary>Original English</summary>
>> So, today you've been focused on this thing about it and working on it for both at Adobe, but also to some extent at at Google. What do you know today about developer productivity? How does this relate to AI, coding tool, output, metrics, all of that things? What is it that we can measure? What is it worth measuring? And what are things that are hard to know?
</details>

>> 是的。我的意思是，我们已经公认衡量生产力即使不是不可能，也是非常困难的，因为它的度量单位到底是什么？不久前我有一个算得上聪明的想法。

我说这个词带有一点贬义。我当时想，如果我们不知道度量单位是什么，经济学在这方面是有现有方案的，对吧？你可以有一个指数指标，在其中衡量可能影响这一点的所有因素，并想出一种方法把它们有效地打包在一起。然后你就会得到一个无量纲的、但在方向上有用、且随时间推移具有参考价值的数字，你可以大致盯住它。

而我的理论曾是，衡量所有我们认为是事情进展好坏的正向或负向指标。对吧？发布次数、测试覆盖率、PR数量，对吧？比如所有东西，对吧？就是撒一张大网。我对这个的最初构想是，利用群体智慧的想法，对吧？比如没有人能估算出一个罐子里装了多少颗软糖，但你找来100个人，估算出的结果就会非常接近。所以，我们做一个类似于“行不行？”的选择题，比如你更倾向于哪一个？比如每周多一次发布，还是X个测试，对吧？你和那些相当有经验的工程师一起把这个游戏玩上几轮……

<details><summary>Original English</summary>
>> Yeah. I mean, we've taken it as axiomatic that it is hard if not impossible to measure productivity because what are the units even? I had a while back sort of clever idea.

Um and I use that as a loaded term. I had this idea that if we don't know what the units are, like economics has prior art for this, right? You have an index metric where you measure all of the things that might influence this and you come up with a way to effectively like basket those together. And then you have a unitless but like directionally useful and useful over time like number that you can sort of like pin to.

And my theory had been to measure all of the things that we think are positive or negative indicators of something is going well. Right? Releases, uh test coverage, number of PRs, right? Like everything, right? Just cast a wide net. My initial formulation on this was uh you know, the wisdom of the crowds idea, right? Like no individual can estimate how many jelly beans are in the jar, but you get 100 people and you'll get real close. So, we do a like am I hot or not? Of like which would you prefer? Like one release per week more or X tests, right? And you run a bunch of iterations of that game with your, you know, relatively experienced engineers
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> ……来理清所有这些……

<details><summary>Original English</summary>
>> to work out the linear trade-offs between all of those
</details>

>> 弄清楚

<details><summary>Original English</summary>
>> >> To figure
</details>

>> ……因素之间的线性权衡。
>> 哪个更重要。

<details><summary>Original English</summary>
>> factors.
>> out what matters more.
</details>

>> 对吧？去弄清楚那具体是什么。你可能想要对某些东西进行去重，因为它们只是换了个包装的同一项统计数据。对吧？但要找出那些具有非线性的指标。

然后把这一切融合在一起，对吧？现在你就有了某种综合指标，就像这就是我们的生产力数值。Adobe目前正在做一些类似的事情。

<details><summary>Original English</summary>
>> Right? To figure out like what that is. You probably want to dedupe some things cuz they're just going to be the same stat in a different package. Right? But find the ones that have some non-linearity.

Uh and then mush that all together, right? Now you have something that sort of gives you an aggregate, like this is kind of our productivity number. And Adobe is doing something along these lines.
</details>

<!-- chunk 9/13 -->

### 技术的四种影响力与传统生产力指标的局限

比我最初的构想要稍微聪明一些。但之后你就可以观察这个指标在特定人群中随时间推移上升或下降。我意识到的是，在这个后 AI 繁荣时期，它无法涵盖所有内容。我得出这一结论的原因是我最近发表的一篇论文——关于开发、部署、运维的那篇论文。其中的一个观点是，科技领域存在四种形式的影响力。第一种是产品成功，也就是每个人都在讨论、而且其他所有人都比我更擅长的那套东西。那不是我的工作。

<details><summary>Original English</summary>
Slightly smarter than my initial formulation. But like then you can watch that track up or down and, you know, over time for a given population. What I've realized is that won't capture everything in this post-AI boom. And the reason that I came to that was a paper that I put out, uh the develop deploy operate paper recently, where one of the points in there is there's four forms of impact in tech. There's product success, the stuff everyone talks about and everyone else is better at than I am. Like that's that's not my job.
</details>

>> 无论人们是否购买产品，或者是否使用产品，诸如此类。

<details><summary>Original English</summary>
>> Whether or not people buy a product or or use a product, whatever.
</details>

>> 还有净推荐值、收入，就像所有这些指标，对吧？然后是计算效率，对吧？比如你在 AWS 上挥霍了多少？

<details><summary>Original English</summary>
>> And net promoter score, revenue, like all of the stuff, right? There's compute efficiency, right? Like how much are blowing on AWS?
</details>

>> 对吧？或者如果你在交付传感器之类的东西，所以我对那套太清楚了。

<details><summary>Original English</summary>
>> Right? Or if you're shipping sensors and all that, so I know that all too well.
</details>

对。比如甚至像 Android 团队也有权衡取舍：如果你能将应用程序下载体积减少 1 兆字节——

<details><summary>Original English</summary>
Right. You know, or like even like the Android team has a trade-off for if you can reduce the size of a application download by a megabyte,
</details>

>> 它会对许多指标产生影响，是的。

<details><summary>Original English</summary>
>> it makes a difference for many metrics, yes.
</details>

>> 没错。你看，所有那些东西，那都是一种形式的影响力。然后是工程生产力，或者我们把它表述为工程产能。因为如果我们在生产力或产能上为你节省了 5% 的增益，你并不能把这笔收益花到别处。你只是拥有了更多的产能来做更多的工程工作。

<details><summary>Original English</summary>
>> Right. You know, and so like all of those things, like that is a form of impact. Then there's engineering productivity or we phrased it as engineering capacity because if we save you, you know, 5% productivity gains, capacity gains, you don't get to spend that somewhere else. You just have more capacity on doing more engineering.
</details>

>> 或者是拥有了用于创新或在发生状况时顶上去的空闲时间，诸如此类的事情。

<details><summary>Original English</summary>
>> Or having slack time for innovation or picking up when something happens, that kind of stuff.
</details>

>> 但它们并不能像美元那样同质互换，你不会在另一个账户里得到一笔钱。然后第四种形式的影响力——这又绕回到了 AI 这件事上。第四种形式的影响力是改变游戏规则，对吧？战略性创新。比如研究能让不可能的事情变成可能。

<details><summary>Original English</summary>
>> But they're not like dollar fungible, you don't get money in a different account. And then the fourth form of impact, and this ties back to the AI thing. Fourth form of impact is changing the game, right? Strategic innovation. Like research makes impossible things possible.
</details>

>> 哦，是的。

<details><summary>Original English</summary>
>> Oh, yeah.
</details>

>> 安全能让极其糟糕的事情变得不可能发生。对吧？但如果你改变了我们所做事情的本质、成本结构等等，那可就是完全不同的游戏了。

<details><summary>Original English</summary>
>> Security makes incredibly bad things impossible. Right? But if you change the nature of what is what we are doing, the cost structure, etc., then that's a different game.
</details>

我认为我们看到 AI 面临的问题是，即使采用巧妙的指标、指数指标方法试图捕捉生产力的全貌，如果你没有着眼于单次变更的价值存在实质性差异，那么你绝不可能在信号中捕捉到这一点。对吧？我们没有任何东西表明，这种规模变更的价值已经改变了。

<details><summary>Original English</summary>
And the problem that I think that we see with AI, even with a clever met, you know, index metric approach to trying to capture the gestalt of productivity, if you're not looking for the value of a given change is substantially different, then there's no way you'll ever be able to capture that in the signal. Right? We don't have anything that says the value of a change of this size has changed.
</details>

所以举个例子，在现阶段这完全是可能的：我也在安全圈子里混，做很多底层的 C++ 库之类的工作。你可以在几周内写出一个 JPEG 解析器。

<details><summary>Original English</summary>
So for instance, like it is entirely possible at this point, and I hang out in security spaces and do a lot of low-level, you know, C++ library stuff. You can write a JPEG parser in a couple weeks.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yep.
</details>

>> 对吧？带着你需要的任何额外特性。3 年前要是把那个词、那句话大声说出来，简直是疯了。

<details><summary>Original English</summary>
>> Right? With whatever additional features you need. That would be insane to say that word that sentence out loud 3 years ago.
</details>

### AI 改变游戏规则的实际案例

>> 好，所以你的意思是，没有任何测量能真正捕捉到那种可能性、那种影响力、以及做出巨大创新所需的努力——而眼下由于 AI 的存在，这正在发生。对，我也给你举一个例子，你告诉我这是否是你表达的意思：我有一个朋友，在一家工程公司担任 CTO，大概是一家中型工程公司。他们属于一个小众行业。这位 CTO 一直在关注发布频率等所有常规指标，与他们的工程团队沟通，询问他们开心还是不开心。当然，现在他们也在采用 AI。他们发现大家效率更高了。私下里这个人对我说：“听着，我几乎确信，我们大概可以用一半的人手完成相同的工作量，这样我们就能实现正向现金流了。但当然，这涉及士气问题。”他也喜欢手下的员工，所以他说：“我不知道自己是否想承担这种心理负担。但我们可以看到有些人上手更快，有些人更慢。我们当时差不多就聊到这里。”

<details><summary>Original English</summary>
>> Okay, so so what you're saying is what none of the measurements really capture is the possibility, the impact, the effort it is to do a massive innovation, which right now with AI is happening. And right and I'll I'll I'll give you also one example that I and tell me if if this is what you mean with it is there's a a friend who works at a a CTO at an engineering company about uh like a mid-size engineering company. They're they're a niche industry. And you know, like this the CTO they they have been looking at like release frequency, all the usual metrics, talk with their engineering team, are they happy, are they not? And of course now they're adopting AI as well. They're seeing that well, people are more efficient and just privately this this person was telling me like, "Look, like I kind of know that for a fact that we could probably do the same amount of work with like half the amount of people and then we could be cash flow positive. But of course there's a there's a morale thing." So he's like also like he likes the people. So he's like, "I I don't I'm not sure I want the emotional baggage on on me. But we can see some people are picking it up faster and some slower. And we kind of left it at that."
</details>

几周后我跟这个人聊天，对方说：“你肯定不敢相信，但我们可能要实现正向现金流了。”我说：“怎么做到的？难道你们推进裁员了吗？”他说：“没有。发生的事情是，我们的一位工程师来找我说：‘我们给这个组件付授权费。可以把它看作一个库，就像一个二进制文件。但那是该领域的一家供应商编写的，具有高性能表现，他们将其用在自己的软件中。这是软件的核心部分。他们有收入分成协议，要为这个组件支付比如大概 5%、10%、15% 的收入。它太重要了。这显然是受许可的闭源软件，但它真的非常重要，如果是让一个 5 人或 10 人的团队去写，需要耗费数年时间，而且还不一定能成。所以以前根本不值得去做。’

<details><summary>Original English</summary>
A few weeks later I'm talking with this person and says like, "You wouldn't believe, but we're probably going to be cash flow positive." I'm like, "How? Like did you go ahead with the cut?" He's like, "No. What happened is one of our engineers came to me and said like, "We license this component. Think of a library. Like it's a binary. But that was written by a vendor in the space that has a high performance thing that they use in their in their software. It's it's a core part of it. And they have a revenue share where they they pay like I don't know like 5, 10, 15% of their revenue for this component. It's so important. It's obviously licensed, closed source, but it's it's really important and it would take them years of a five-person or 10-person team to write it and it might or might not work. So it's not worth it."
</details>

那位工程师过来说：‘要是我们直接给出规格说明呢？’因为他们围绕这个东西有海量的测试，一套测试挽具。他们把它交给了 AI。AI 为他们写出了一个组件，比他们现有的组件更快、更好，而且没有任何先验领域知识。起初他们想，也许我们会把它开源，但后来他们告诉了供应商，供应商说这对他们来说是一笔巨大的业务。供应商付钱给他们，让他们不要开源，并把实现方案交给供应商，供应商可以重新对外授权。瞬间，游戏规则被彻底改变了。如果这个人推进了哪怕比如裁员，这位工程师可能就走了，而且可能没有人会知道游戏规则本可以因此改变。

<details><summary>Original English</summary>
The engineer came and said like, "What if what if we just gave the specs? Cuz they have all massive amounts of test around this thing, a test harness. They gave it to AI. AI wrote a component to them which is faster and better what they have, no prior domain knowledge. And at first they thought, well, maybe we'll open source it, but then they told the supplier and the supplier said like, it's a huge business for them. They're paying them to to not open source it and to give them the implementation. Which they can re-license. And suddenly, the game was completely changed. Like Like if if this person would have gone ahead with, let's say, the layoffs, this engineer might have just got a and no one would might have known that the game could be changed because of this
</details>

>> AI 有时能让疯狂的事情成为可能。

<details><summary>Original English</summary>
>> AI makes things crazy things sometimes possible.
</details>

>> 对，完全没错。

<details><summary>Original English</summary>
>> Right. Exactly.
</details>

### 从“提高产出速度”到“做更有价值的事”

>> 所以我认为这就是试图弥合差距的洞见所在——我还没见过有基于研究的数据表明 AI 之后的生产力提升超过 20% 或 30%。但随后每个人都在谈论这种 10 倍速的体验。我极度不认为它实际上达到了 10 倍，但是——

<details><summary>Original English</summary>
>> And so I think that this is the insight that tries to bridge the gap between I have not seen a research-based number that says productivity post AI is up more than like 20 or 30%. But then everyone talks about like these 10x sort of experiences. I super don't think it's actually 10x, but
</details>

>> 嗯，对。

<details><summary>Original English</summary>
>> Um yeah.
</details>

>> 但是，你该如何弥合这种差距？我认为症结恰恰在于：AI 的许多价值并不在于更快地做同样的事情，而是在于去做你甚至连想都不会去想的更难、更有价值的事情。而如果你的生产力衡量标准在逻辑上等同于去计算从工厂里生产出了多少个小构件，然后你开始生产极度豪华的镀金小构件，那是根本没有办法随时间去衡量或追踪这一点的，因为我们根本没有关于“这个组件或特性的价值是多少”的追踪机制。

<details><summary>Original English</summary>
>> But like, how do you bridge that gap? And I think it's exactly this thing of a lot of the value of AI is not in doing the same thing faster. It's doing a harder, more valuable thing that you wouldn't have even thought about. And if your productivity measures are the logical equivalent of counting how many widgets are coming out of the factory, and then you start producing super gold plated deluxe widgets, there's no way to measure that or track that over time because we just don't have the tracking of what's the value of this component or feature.
</details>

这也印证了，你知道，与资深工程师们的交流：他们说，是的，我们的代码量增加了 70%，系统故障增加了 30%，特性数量保持不变。而我们无法确知的是，那些特性的价值是否提升了？因为你怎么……你怎么去衡量那个？

<details><summary>Original English</summary>
And that also matches with, you know, talking with senior engineers that are like, yes, we're up 70% on amount of code, we're up 30% on outages, number of features is the same. The thing that we can't know for sure is are the value of those features up? Because what's how do you how do you do that?
</details>

### 对计算机科学教育现状的反思

>> AI 给应届毕业生进入就业市场带来的一个挑战是：现在似乎出现了这种预期。企业非常渴望招聘懂如何使用 AI、具备鉴赏力和判断力的资深工程师，我们到处都在抛出这些词汇。虽然并非有意为之，但每当我与 AI 实验室交谈时，他们总是越来越多地告诉我，他们寻找的是品味、判断力、能动性这类特质。让我们回到教育，回到计算机科学教育。结合我们所知行业正在发生的变化，你对当今计算机科学教育的运作方式有何看法？关于可能可以做出哪些改变，你有什么想法？

<details><summary>Original English</summary>
>> One challenge that AI is is giving uh is entering the market uh for for new graduates. Uh there's now there seems to be this ex- expectation. Companies are very eager to hire senior engineers who know how to use AI and they have taste and judgement, and we have these things thrown around. It's not deliberate, but whenever I talk to the AI labs, they always tell me increasingly that they look for taste, judgement, uh agency, these kind of things. Let's go back to to education. Uh to to computer science education. W- What are your views of how today's computer science education works, especially for how we know the industry is changing? And what are some of your ideas of what could what's uh possibly be changed?
</details>

>> 我想聊聊我在这方面的资质，以此来增加这番话的份量。在那本书之后，我被招募加入了 ACM、IEEE、AAAI 联合制订本科计算机科学学位课程要求的工作。这相当于专业学术机构在表态：“这些是我们必须要做的事情。”在该工作的指导委员会中——我是指导委员会成员——我是唯一一位目前在职的工程师。其他所有人都是学者。

<details><summary>Original English</summary>
>> I will riff a little on my bona fides there to like to to to add some weight to this. Uh So, after the book, I got recruited into the ACM IEEE AAAI work on setting the curriculum requirements for an undergraduate CS degree. So, this is like the the professional societies saying, "These are the things that we need to be doing." And for the steering committee for that work, I was on the steering committee, I was the only currently working engineer. Everyone else is academic.
</details>

>> 好的。

<details><summary>Original English</summary>
>> Okay.
</details>

>> 是的，在某种意义上，因为，你知道，这关乎我们能教什么。我主要负责软件工程要求部分。但这确实意味着我切实清楚这些要求到底是什么，并且已经在那个领域沉浸了多年。坦率地说——在 AI 出现之前的一次主题演讲中我就此做过分享——坦白地讲，大多数

<details><summary>Original English</summary>
>> Yeah, in some sense, cuz, you know, it's what can we teach? Uh and I managed mostly the software engineering requirements. But it does mean that I like I see exactly what the requirements are and have been living in that space for for years. And bluntly, uh and I gave a talk on this in a pre-AI keynote, uh bluntly, most
</details>

<!-- chunk 10/13 -->

### 计算机科学课程体系与实践脱节

计算机科学的课程设置自 2000 年左右，甚至更早以来，就没有发生过实质性的改变，对吧？课程里最普遍的内容，恰恰是 90 年代构建数据库或操作系统所必需的东西。

<details><summary>Original English</summary>
of the CS curriculum hasn't substantially changed since like 2000, maybe earlier. Right? The average thing in the curriculum is exactly what was needed to build a database or an operating system in the '90s.
</details>

>> 这听起来可不太妙，不是吗？

<details><summary>Original English</summary>
>> That doesn't sound good, does it?
</details>

>> 对于一个以创新为荣的领域来说，确实不妙，对吧？就像这里面所有的这些内容，我真的不得不去问：我们教这个，是因为它依然紧密相关且重要，还是仅仅因为它是传统？还有……或者是因为我们知道怎么去教它。

对，或者是因为我们懂得怎么教。但是因为，你看，软件工程或计算机科学系的历史，最早的计算机系距今也才不过 50、60、70 年而已，对吧？这个领域未免太年轻了，根本不应该出于传统去做事情。甚至在 AI 出现之前，我就觉得其中很多东西都需要彻底推倒重来，因为所有的课程要求、所有的教学基本上都是通过增生累积起来的。你知道，我们就是不断往里塞更多东西，然后把现有内容的深度削减那么一点点。

<details><summary>Original English</summary>
>> Not for a field that prides itself on innovation, right? And like there's all of these things where like I have to genuinely ask, like, are we teaching this because it is relevant and important, or are we teaching this because it is tradition? And the history of or we know how to teach it. Right. Or we know how to teach it. But cuz like the history of, you know, software engineering or CS departments, like we're only at 50, 60, 70 years for the earliest CS departments. Right? Like this is a field that is way, way too young to be doing stuff out of tradition. Even pre-AI, I was like, I think a lot of this needs to be burned down because all of the curriculum requirements, all of the teaching has mostly been through uh accretion. You know, like we just throw more stuff in there and cut the amount of depth on the existing stuff by epsilon.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 对吧？我认为那样行不通。甚至在 AI 出现之前我就一直在说，我真正希望的是你花更多时间去练习、去演练，真正成为一名熟练的程序员、算法思考者，而不是对上百万个不同话题都只拥有一点琐碎的常识性了解。

现在又有了 AI，对吧？我们可以保证，如果你把作业直接喂给 AI，你甚至可以完全不带思考地读完整个本科学位，因为它在所有那些程序和作业上的表现都绰绰有余。因此，我一直极力呼吁的很大一部分内容，就是我们必须从代码细节中抽身出来。我们必须进行大幅度的层级提升。比如，你需要能够阅读代码，作为一个系统思考者去思考，并在算法层面上理解其结构和执行，但没有人需要去实现链表。我们甚至可能根本不应该教链表。它太慢了，对吧？内存访问本来就很慢。我们越是能够重新聚焦于设计规范——比如准确表达你希望发生什么——然后是测试、验证与核实，比如确保 AI 确实完成了你需要它做的事情。对吧？如果我们能教这些东西，那么它对专业人员来说立刻就变得极为相关了。

我认为最大的疑问在于：这会由计算机科学系来承担，还是我们会看到计算机科学专业的招生人数暴跌，而软件工程项目却会激增？因为坦率地说，在 AI 时代真正重要、并且仍能让你找到工作的东西是团队合作、沟通、设计、规范、测试和验证，对吧？

<details><summary>Original English</summary>
>> Right? And like that I don't think that works. Even pre-AI, I was saying like the thing that I really want is like you spend more time practice and drill and actually become like a fluent programmer algorithmic thinker, not you have a trivia understanding of a million different topics. And now AI, right? Like Yeah. We guarantee like you can do all of an undergraduate degree without ever thinking uh if you can just feed it into an AI cuz it will do just fine on all of those programs and assignments. And so a lot of what I'm pushing for is we need to get out of the code. We need to up-level substantially. Like you need to be able to read code and think as a systems thinker and under- like algorithmically like understand the structure and execution, but no one needs to implement a linked list. And we probably shouldn't even teach linked lists. It's the way too slow. Right? Memory is a slow thing. The more that we can refocus on uh design specification, like precision in saying what you want to happen, and then testing, validation, verification, like making sure that the AI actually did the stuff that you needed to happen. Right? If we can teach those things, then it's suddenly perfectly relevant you know for professionals. And I think the big question is will that be CS or are we looking at CS enrollment is going to plummet but software engineering programs are going to kick up because let's be honest the stuff that's going to matter like in a AI era and still get a job is teamwork, communication, design, specification, testing, validation, right?
</details>

>> 噢，那全都是软件工程的内容。

<details><summary>Original English</summary>
>> Oh, that's a bunch of software engineering
</details>

### 项目经验与刻意练习

>> 而且还有构建生产级软件。尤其有了 AI 之后，就不再需要……我之前和 Cockroach Labs 的联合创始人 Peter Mattis 聊过，他告诉我，在大学期间他在课外构建了……

<details><summary>Original English</summary>
>> And also building production software especially with AI there's no like I was talking with Peter Mattis co-founder Cockroach DB Cockroach Labs and he was telling me that during his college on the side he built the
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 随后他获得了许多机会，之后他又构建了 GTK+。我当时就在想，等等，他是在攻读计算机科学学位的同时在课外完成了这些。你难道不想干脆抛开计算机科学吗？我也学过计算机科学，但对于软件工程学位来说，你难道不想从第一天就开始动手吗，特别是在有了 AI 之后？大家来到这里，在一门课上构建一个软件；在另一门课上与团队一起构建软件；在第三门课上扩展那个软件；到了第四门课……因为以我自己在计算机科学领域的经历来说，我们学了大量的理论。在四年里我最喜欢的一门课，就是那唯一一门以团队为基础、我们实际构建了软件的课程。四年里只有一门，仅有一门。

<details><summary>Original English</summary>
>> And he got a lot of opportunities afterwards and then he built GTK plus and I was thinking hang on like he did that on the side next to a CS degree. Would you not want just throw aside computer science? I I did computer science as well but for a software engineering degree would you not want to start on day one especially with AI? People come in here and you build on one class you build one software and the other build you build a software with a team. On the third one you extend the software. On the fourth one because my experience being in a computer science thing we we did a bunch of theory. My favorite class was the one team-based class where we actually built software in the four years. There was one only one.
</details>

>> 很普遍。

<details><summary>Original English</summary>
>> Normal.
</details>

>> 然后我又多选了一门课去实际学习 .NET。接着等我进入现实世界时，感觉自己完全是从零开始。我回想起所有那些当时没教但现在有教的内容，但实战练习确实缺失了。我有理论，但我绝对没有足够的演练次数。

<details><summary>Original English</summary>
>> And then I took an extra class for to actually learn dot net and then when I got into real world it felt I was starting from scratch. I was thinking of all of these things which were not taught at the time these days are but the practice was was missing. I I I had the theory but I I definitely did not have the reps.
</details>

>> 没错。我认为 LeetCode 面试之所以出现就是因为这个，因为好吧，你该如何找到证据证明某人确实做足了演练呢？对吧？那就是参加编程竞赛的学生，对吧？他们才是在任务上投入了足够时间的人。

<details><summary>Original English</summary>
>> Right. And I would argue that the lead code interview was because of this because okay, how do you find signal that someone has put in the reps? Right? It's the students that were playing in the programming contests, right? Those are the ones that had enough time on task.
</details>

>> 那曾是唯一……有点算是获取……

<details><summary>Original English</summary>
>> that was that was the only reps that were kind of a little bit get
</details>

>> 普遍的

<details><summary>Original English</summary>
>> common
</details>

>> ……向那些没有软件工程专业知识的工程师开放的途径。抱歉，呃，是对编程有兴趣、但没有软件工程专业知识的人。

<details><summary>Original English</summary>
>> that were open to engineers who didn't have software engineering expertise. Sorry. Uh yeah. People with affinity for programming who did not have software engineering expertise.
</details>

>> 完全正确，对吧？所以从这个角度来看，我们去问编程竞赛风格的 LeetCode 问题就完全合情合理了，这并不是因为我们需要去解决又一个广度优先搜索问题，或是反转链表之类的无稽之谈。而是明确地因为，它代表着你曾处于一个做足了演练的环境中。而在一般的学位中，实际用于编程任务上的时间是相当有限的。你知道，如果回头看马尔科姆·格拉德威尔提到的“一万小时定律”达到精通——我想是在格拉德威尔的书里。呃，就像是的，你从哪里获得那些时间呢？

<details><summary>Original English</summary>
>> Exactly, right? And so like it made perfect sense from that perspective for us to like ask the sort of leak code questions in the programming contest styles, not because we needed solutions to get another breadth-first search problem or reversing a linked list or any of that nonsense. But specifically because it was a proxy for you've been in an environment where you put in the reps. Whereas the amount of actual like programming time on task for an average degree is pretty modest. And you know, you go back to 10,000 hours to mastery in Malcolm Gladwell. I think that's in Gladwell. Uh and like yeah, like where are you getting the time?
</details>

### 训练营与带薪实习模式

>> 而且如果我回想一下从 2010 年代初开始兴起、在 2014 到 2017 年间开始变得非常强劲的那些训练营。他们的做法是，历时 3 个月、3 到 6 个月，有时是 12 个月，但通常是 3 到 6 个月，招收完全没有计算机科学或编程背景的人。他们从第一天就开始：“我们来构建一个应用”，通常包括前端和后端。他们教授基础知识，内容其实并不算多，但这三个月或六个月的高强度时间里，是在从零开始构建一个可以运行的 Web 应用。

<details><summary>Original English</summary>
>> And if if if I think back of the boot camps that have spun up in the from like early 2010s, they started to get really strong 2014 to 2017. What they did is that a 3-month 3 to 6 months sometimes 12 month, but usually 3 to 6 months, they took people who had no prior computer science or programming experience. They started day one, let's build an application which was typically a front end and a back end. They gave them the basics. It wasn't all that much, but that was a three intensive months or six intensive months of building a working web application from the ground up.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 当时对软件工程师的需求如此之大，以至于他们能以初级工程师、或者几乎是学徒的级别被录用。但比起计算机科学的毕业生，他们所掌握的包括：他们懂版本控制，懂 Git，懂 Pull Request，懂数据库，懂前端，懂 Chrome 开发者工具。因此，他们在短短 3 个月内就切实掌握了一批有价值的技能，而那些学了 4 年编程的人却可能掌握也可能没掌握，这更像是一种碰运气。

<details><summary>Original English</summary>
>> And there was such a huge demand for software engineers that they got hired as a junior engineer level or almost at an apprentice level, but what they knew uh compared to computer science uh science grads, they knew version control, they knew Git, they knew pull requests, they knew they they knew a database, they knew a front end, they knew new Chrome developer tools. So, they actually had a bunch of valuable skills in only 3 months that the people coming out from programming in 4 years might or might not have had. It was more of a a toss.
</details>

>> 是的，没错。我算过一笔账，一个计算机科学学位所包含的小时数，平均大约相当于 15 个月的全职工作时间。呃，而且这还涵盖了所有的理论知识，以及所有那些你知道的、其相关性存疑的内容。呃，并且它同样试图把你从毫无经验培养到可以在工业界或学术界就业。而这与为期 6 个月的训练营相比，对吧？差距并不是巨大悬殊。特别是其中一个高度聚焦于“这些都是立刻用得上的内容”，而另一个则是“这里有一些东西，希望能教会你如何思考这些问题，也许吧”，或者说得不那么客气一点，“这在我当年当学生时很有用”。

<details><summary>Original English</summary>
>> Yeah, exactly. Like I've done the math, the number of hours in a CS degree is roughly equivalent to like 15 months on average of full-time employment. Uh and that includes all of the theory stuff, all of the things that are you know like questionably relevant. Uh and is similarly trying to take you from no experience to employable in either an industry or academic direction. And like that is compared to a 6-month boot camp, right? Like that's that's not a huge gap. Especially when one of those is laser-focused on these are all things that are just immediately relevant. And one of them is here's some stuff that'll hopefully teach you how to think about these problems maybe or less charitably this was useful when I was a student.
</details>

>> 另外，我们能提一下那些最成功的学校当中，有些其实并不在美国吗？其中一所……当然，很多学校，大家都知道，像 MIT、斯坦福等常规名校都备受推崇。但加拿大的滑铁卢大学，我非常惊讶地发现，硅谷有一大批公司里都有大量的滑铁卢毕业生。我在社交媒体上问过这个问题：滑铁卢大学到底有什么特别之处？他们远在加拿大，为什么大家都要招他们？结果发现，滑铁卢大学有这样一个项目，是的，他们教授计算机科学或软件工程，我不确定是哪一个。但核心部分在于，每个……他们有专门的实习派遣安排。当一个人毕业时，他们已经在不同公司完成了四次定岗实习。而且因为他们拥有合作关系，这些公司往往是 Shopify、Meta 等等。所以你招到的工程师，你知道，3 个月乘以 4 次，相当于已经在这些公司内部工作了一年。

<details><summary>Original English</summary>
>> Also, can we just mention some of the most successful schools were actually outside of the US? One of them well, a lot of the schools are of course you know the the the usual suspects are are very highly regarded from the MITs, the the Stanfords and so on. But Waterloo in Canada, I was very surprised to see that all a bunch of Silicon Valley companies have a high number of Waterloo grads. And I asked this on social media, like what's what's up with Waterloo? They're up in Canada. Why is everyone hiring from there? So it turns out that Waterloo has this program where yeah, they they teach you computer science or software engineering, I'm not sure which one. But the main part is that every they have dedicated placements. By the time someone graduates, they will have had four placements/internships at different companies. And because they have the relationships, this will often be the Shopifys, the Metas, this. So you will get an engineer who you know 3 months times four, that's like a year working inside of these companies.
</details>

>> 是的，那才是价值所在。

<details><summary>Original English</summary>
>> Yeah. And that is the value.
</details>

>> 对，完全正确。

<details><summary>Original English</summary>
>> Yeah, exactly.
</details>

>> 比如，完全可以把那三个……不……

<details><summary>Original English</summary>
>> Like like it's it's not you can probably throw away the the three not
</details>

<!-- chunk 11/13 -->

### 实习与高校项目经验

不是丢掉，但如果要我说的话，从——顺便说一句，我并不想贬低理论的重要性。但从招聘经理的角度来看，比如，噢没错，我会录用那个人，因为他们能很快上手。哇，他们曾在不同的环境中工作过。他们甚至可能从第一天起就给我们带来一些想法。

<details><summary>Original English</summary>
not throw away, but but that is more valuable itself if you ask me from a I don't want to downplay the importance of theory by the way. But from a hiring manager point of view, like, oh yeah, I'll I'll take that cuz that person will be up to speed. Wow, they work in different environments. They might even bring some ideas from day one to us.
</details>

>> 是的。我非常羡慕——我觉得不仅仅是滑铁卢大学，很多加拿大高校都是——

<details><summary>Original English</summary>
>> Yeah. I'm incredibly jealous of I don't think it's just Waterloo, like a lot of the Canadian schools are
</details>

>> 顺便说一句，那只是其中一个例子。

<details><summary>Original English</summary>
>> just one of example, by the way.
</details>

>> 是的，但是嗯，很多加拿大高校的计算机科学专业在实习和协同培养（co-op）方面有实力强得多的项目，以至于现在其中很多学位都要读5年。但我认为这是一种强得多的教育体验，因为确实存在那样的一些教训——我完全承认，比如有些内容我们并没有放进软件工程的要求里，因为在学术环境中根本没办法做到那样，对吧？有些教训你必须以真实的方式去吸取，比如在实际领域中。即使你给出了比如做项目的例子。我希望我们能做更多的项目，但我对大多数学位里只有一门项目课程感到非常担忧，因为你知道团队从来都不可能是什么样子的吗？一群具有完全相同背景水平的人，对吧？这也让人对“这就是团队合作”产生了错误的理解。比如，嗯，比如我会接受它，这总比不做强，但是……是的。

<details><summary>Original English</summary>
>> Yeah, but uh yeah, a lot of the Canadian uh schools for CS have substantially stronger programs on internships and co-ops in a way that a lot of those degrees run 5 years now, but I think it is a much stronger educational experience because there are some of those lessons, like I will fully admit, like there's stuff we did not put into the software engineering requirements cuz there's just no way to do that in the academic setting, right? There's some lessons you're going to have to learn the real way, like in the field. Even though you gave the example of like doing a project. I want us to do more projects, but I'm really nervous about there being one project course in most degrees because you know what no team has ever looked like? A bunch of people with exactly the same level of background, right? Like it also gives the wrong taste about this is what teamwork is. Like, uh like I'll take it, it's better than not doing it, but there yeah.
</details>

### AI时代的基本功与新毕业生

>> 嗯，我们能用的就是现有的体系，而这个体系有望在像你这样的人以及其他人的努力下，有望开始转变，或者仅仅是顺应时代。但是，AI现在已经到来了，更有经验的工程师正在思考的一个大问题是：比如我们是在AI出现之前学会构建软件的。我们拥有一堆——我们知道基础原理，我们当中很多人都学过计算机科学，所以我们实际上有非常扎实的理论理解，其中某些部分我们可能会用，也可能不会用。但是，应届毕业生呢？现在他们进入职场，正好具备了我们所拥有的这些能力，你认为他们应该专注的基础原理是什么？他们应该直接依赖AI的事情又有哪些？总会有这样的问题：比如，你究竟是应该直接向AI寻求答案，还是应该去学习基础原理，对吧？

<details><summary>Original English</summary>
>> Well, we have what we have, and and this system will hopefully with with people like yourself and others will hopefully start to to also change or or just adapt to the times. But, AI is right now here, and one big question more experienced engineers are thinking about, like we we've learned to build software pre-AI. We have a bunch of we we know the fundamentals of many of us went through computer science, so we actually have a very strong theoretical understanding, which we might or might not use some parts of it. But, what about for for new grads? Now that they'll enter workforce of just today with just the capability that that we have, what do you think the fundamentals are that they should focus on, and what are the things that were they should just rely on AI? There's always the question of like, should you just ask AI for this or should you learn the the basics, right?
</details>

>> 是的。所以，我的意思是，我认为“学习基础”完全是一个预设立场的问题，因为没有人在什么是基础这一问题上达成一致。

<details><summary>Original English</summary>
>> Yeah. So, I mean I think the learn the basics is an entirely loaded question because nobody agrees on what the basics are.
</details>

>> 这话很客观。

<details><summary>Original English</summary>
>> And that's fair.
</details>

>> 几个月前我们上次聚在一起时，肯特·贝克（Kent Beck）说过类似这样的话：目前在工作的所有人，都是在一个存在标准玩法（playbook）的时代成长起来的。比如我们至少在理论上知道做这件事的正确途径。而现在没有任何标准玩法了。对吧？所以，我们都对不知道答案感到有点无所谓，而且我们肯定不知道关于什么依然属于基础的答案。我认为初级人员应该专注的事情：第一，具备避免仅仅把工单复制到AI提示词中然后试图提交该结果的韧性。对吧？比如如果你所做的一切仅此而已，你就可以被一个非常短的现成脚本所取代。那并不是你能留在团队中的防御性优势。我认为非常重要的一点是，利用AI来提升自己、拓宽你的输入，而不是立刻用它来产生你的所有输出。大约一年前在一个智库里，有一个我非常喜欢的隐喻。我们称之为“安德鲁的斧头”（Andrew's Axe）。

<details><summary>Original English</summary>
>> Kent Beck said a couple months ago when we were last together, uh something like everyone that's currently working uh has grown up in an era where there was a playbook. Like we know at least in theory the right way to do this. And there's no playbook right now. Right? So, we all get a little comfortable of not knowing the answer and we certainly don't know the answer on what is still the basics. The things that I think that the the juniors should be focusing on, one, uh the resilience to avoid just copying your ticket into AI prompts and then trying to check in that result. Right? Like if you're if that is all that you are doing, you can be replaced with a very short off-the-shelf script. Like that is not a defensible advantage for you being on staff. I think it's really important to use AI to better yourself and to widen your inputs, but not to immediately produce all of your outputs. There's a metaphor that I really liked from about a year ago at a think tank. Uh we called it Andrew's Axe.
</details>

那是关于：如果我拿着一把斧头去砍倒一棵树，我不会说是斧头砍倒了树。是我砍倒了树。AI尽管我们偶尔会将其拟人化，但它仍然是一个工具。1979年IBM的培训手册写道：计算机永远不会被追究责任，因此计算机不应该做出管理决策。AI至今仍然是不承担责任的。AI实验室不会因为这些东西产生的错误向我们做出赔偿。所以，对于在那些拉取请求（pull request）上署了你名字的任何内容，你必须能够为之担责。而这就需要严格得多的把关、不偷工减料，而且我认为那种对细节的专注确实是很难培养的。

<details><summary>Original English</summary>
And it's if if I go chop down a tree with an axe, I do not say that it was the axe that chopped down the tree. It's me that chopped down the tree. The AI, as much as we occasionally anthropomorphize it, right, is still a tool. And 1979 IBM training manual, a computer will never be held accountable, therefore a computer should not be making management decisions. The AI is still not accountable. The AI labs are not going to indemnify us for you know the mistakes that these things produce. So, you have to be able to stand up for whatever your name is on for those pull requests. And that requires a lot more rigor and not cutting those corners and like that attention to detail I think is is really hard to train.
</details>

### AI对学生群体的分化影响

嗯，回到本科教育这方面的情况，我从很多教授那里听到的可怕情况是：最优秀的学生，比如B、B+及以上的学生，比以往任何时候都更加优秀。

<details><summary>Original English</summary>
Um going back to the sort of the undergraduate version of this, the story the scary story that I've been hearing from a lot of profs is the best students, like the B B+ and above students, they are better than they ever have been.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 因为他们拥有——是的，因为他们不再依赖每周只提供几个小时答疑并且比他们高一两个年级的助教，他们随时拥有一位极有耐心、时刻在线、博览群书、偶尔会产生幻觉的导师，对吧？他们随时可以去学习、解释和弄清楚——

<details><summary>Original English</summary>
>> Because they have Yeah, because instead of relying on a TA that is available, you know, a couple hours a week and is one or two grades above them, they have an infinitely patient, always available, incredibly well-read, sometimes hallucinatory tutor right at the drop of a hat, right? They can always learn and explain and figure out
</details>

>> 而且他们实际上拥有使用它的自主性和动力。

<details><summary>Original English</summary>
>> And they actually have the autonomy and the drive to use this.
</details>

>> 没错。并且拥有元认知资源来避免变成“我就只管复制粘贴”，对吧？最差的学生稍微变好了一些，因为他们过去什么都做不出来，但现在他们能产出垃圾内容（slop）了。

<details><summary>Original English</summary>
>> Right. And the the and the metacognitive resources to avoid that like I'm just going to copy and paste, right? The very worst students are somewhat better because they used to not be able to do anything, but now they can produce slop.
</details>

>> 是的，他们就只是扔出一堆垃圾内容，对。

<details><summary>Original English</summary>
>> Yeah, they're just throwing slop, yeah.
</details>

>> 没错。这有点难检测，但我懂那是什么——

<details><summary>Original English</summary>
>> Right. Which is a bit hard to detect, but I I get what
</details>

>> 确实。

<details><summary>Original English</summary>
>> Right.
</details>

>> 但是处于中间层的所有人几乎都垮掉了。他们没有那种韧性。他们宁愿去参加聚会或打电子游戏也不愿意做作业。于是他们会想：好吧，就这一次，我就这样习惯性地处理一下。而那种滑坡只会越来越严重。对吧？所以很多来自不错学校的教授会表示：是啊，我不知道啊，伙计。比如我不确定中间庞大群体中像成绩在B以下的所有人，是否真的理解代码是如何运作的。整个体系根本就不是为了追踪这类事情而设立的。

<details><summary>Original English</summary>
Uh but everyone in the middle has kind of collapsed. They don't have that resilience. They would rather go to the party or play video games than do the homework. And so they like, well, just this one time I'll just get in the habit of doing this thing. And that slippery slope just gets worse. Right? And so like there are a lot of profs from decent schools that are like, yeah, I don't know, man. Like I'm not sure that anyone like below like the the vast middle, everyone below a B, might not understand how code works at all. Like the system is just not set up to be tracking that sort of thing.
</details>

>> 或者至少给予他们反馈，例如警示之类的事情，对。

<details><summary>Original English</summary>
>> Or at least giving them feedback, for example, alerting, those kind of things, yeah.
</details>

### 教育重塑与课程设计

>> 没错。所以最初很多讨论都集中在：我们如何阻止学生使用这些AI工具？我认为那是无稽之谈，因为这就像是历史的回响——比如我们有了高级语言，有了编译器。就像“但是现在你学不会怎么用汇编语言编程了”，对吧？反正整个行业都在使用它。

<details><summary>Original English</summary>
>> Right. And so a lot of the discourse initially was how do we prevent students from using these AI tools? And I think that that's nonsense because it's echoes of like we got high-level languages and there's compilers. Like But now you're not going to learn how to program in assembly, right? Like the industry is using it anyway.
</details>

>> 没错。他们将被要求去使用——当他们找到工作时，在某些地方他们甚至会被迫、被施压更重度地使用它。

<details><summary>Original English</summary>
>> Right. They're going to be asked to use They're going to be forced to pressure to use it harder in some places when they get a job.
</details>

>> 嗯，即便如此，如果有应届毕业生说“我没用过这些工具”，那绝对会是一个危险信号。比如得了吧。难道你没有——

<details><summary>Original English</summary>
>> Well, if that it might be it will for sure be a red flag if a new grad says like I've not used these tools. Like come on. Have you not
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 难道你不想在这个行业工作吗？我们正在做的事情是一个公开的秘密。我们在博客上到处都在公开发表它。

<details><summary>Original English</summary>
>> Do you not want to work in this industry? It's an open secret what we're doing. We're publishing it on blogs and everywhere.
</details>

>> 是的，确实如此，对吧？所以“我们永远不会允许你使用这些工具”的立场根本不可能守得住。嗯，本月我和一群学者在《美国计算机学会通讯》（Communications of the ACM）上共同发表了一篇文章。嗯，我认为那篇文章的开篇第一句话是：设想展望到2040年，我们坚守阵线，把所有使用AI的行为都视为作弊，但有一代AI学生——你知道，他们伴随着AI成长，就像互联网原住民伴随着网络成长一样。对吧？如果我们继续问他们这些传统的问题，比如“找出这个字符串中的回文”或者“测量这个图表中的降雨量”，对吧？他们能从传统的计算机科学学位中学到任何东西吗？我认为答案显然是否定的。

<details><summary>Original English</summary>
>> Yeah, exactly, right? And so the line of well, we're going to never let you use these tools cannot possibly hold. Um I co-published a piece in Communications of the ACM with a bunch of academics this month. Um the I think the opening line there is imagine forward to 2040. Uh and we hold the line treating all use of AI as cheating, but a generation of students AI you know, they've grown up with AI in the same way that the internet natives have grown up with the network. Right? If we keep continuing asking them these traditional questions about like find a palindrome in this string or measure the volume of rainfall in this graph, right? Like are they going to learn anything from a traditional CS degree? And I think the answer is obviously no.
</details>

所以如果我们知道我们不能停留在原地，而且有大量的事情需要修正。那就让我们推倒重来，去做一些有意义的事情，并弄清楚如何适当地利用它。而且我认为要找到一些方法，在假定他们正在使用AI的前提下进行思考：新的学习目标是什么？你如何让它在促使他们思考并以不同方式学习事物的维度上依然充满阻力（frictionful）——几乎可以肯定是在更高的层面上。对吧？但这实际上是本科教育、课程设计和评估的关键所在。

<details><summary>Original English</summary>
So like if we know that we cannot stay here and there's plenty of things that need fixing. Like let's burn it down and do something that matters and figure out how to use this appropriately. And I think finding ways to assume that they're using AI. And what are the new learning objectives? And how do you make that still frictionful in the ways that cause them to think and learn about different things like almost certainly at a higher level. Right? But like that's actually the key to undergraduate education and curriculum design and assessment.
</details>

>> 听起来不管是——教授们、助教们、设计这些课程的人，他们也需要投入大量的工作，因为没有人已经把这事彻底搞明白了。你必须去实验。你首先需要自己去使用这些工具。

<details><summary>Original English</summary>
>> Uh it sounds like whoever's uh so the the professors, the the the TAs, the people who are designing these course, they also need to put a bunch of work because no one has this figured out. You need to experiment. You need to first use these tools yourself.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yep.
</details>

<!-- chunk 12/13 -->

### 评估方式的转变与过程考核

>> 你需要构想出新颖的作业设计方式，也就是那种需要用 AI 去解决、但光靠 AI 本身又不够的作业。怎样获取反馈呢？你可能需要投入更多时间。比如说，事后和学生坐下来，让他们向你讲解。因为你看，面试形式也同样在发生变化。现在看来效果很好的面试形式之一就是结对编程：通过视频或者面对面，你可以使用 AI，但要一边做一边讲解你在做什么、怎么做的，对吧？因为这样你就不能完全靠伪造蒙混过关了。你没法找朋友代做，或者直接全丢给 Claude。你现在展示的是你的认知能力。面试官可以把你推向不适区，他们会借此评估你的专业程度，并一步步深入推进，等等。

<details><summary>Original English</summary>

>> You need to come up with novel ways of creating an assignment which you need to use AI to solve, but AI itself is not enough. How how do you get the feedback? You might need to put in more time. Let's say, like, sit down with someone afterwards and have them explain to you cuz, you know, again, like, interviews are also changing. And one of the interviews that seem to be working well is when you're pairing with someone, you're like, video or in person, you're using AI, but you're explaining what you're doing and how, right? Cuz now you you cannot just fully fake it and go away. You give it to a friend or or just have Claude do it. You're you're now showing your cognitive ability. The interviewer can push you into uncomfortable, you know, they'll they'll they'll they'll get a gauge of like how expert you are and and push you further and further and so on.

</details>

>> 没错，确实如此。在本科阶段，也出现了一些转向更多口试以及类似形式的趋势。

不过我也认为，一个非常简单的解决方案就是：别再只针对结果打分了。要关注过程，对吧？即使你不去出那些难得离奇的考核作业，也别再只评判他们交上来的代码了。相反，去评估：你用来得到这个结果的提示词是什么？另外，你提供了什么样的测试用例？比如，你是如何确保这东西确实在按照你的需求运行的？

当你开始关注促成结果的过程，而不仅仅是最终产物时——我认为不仅是计算机科学，大多数学科都是如此，对吧？比如，我们以前总是让学生去就《麦田里的守望者》写一篇新论文。可我们真的不需要又一篇关于《麦田里的守望者》的论文了。去写一个新的链表，我们也不需要又一个链表。我们一直把从中产出的制品，当成一种代表你投入了时间、经历了挣扎、面对了阻力，并因此推定你学到了东西的替代指标。或许更恰当的做法是直接关注：我们是否有证据表明你经历过挣扎并学到了东西？把整个过程打包交上来，对吧？

<details><summary>Original English</summary>

>> Yeah, exactly. And at the undergraduate level, like, there is some move towards more oral exams and those sorts of things.

But also, I think a really simple solution is stop grading just the outcome. Focus on the process. Right? Like, even if you don't come up with wildly harder assess assignments for assessment,

stop grading just the code that they turned in. Grade instead, what are the prompts that you used to get here? Also, what are the tests that you provided? Like, how did you make sure that this thing is actually doing what you need it to do?

And like, when you start focusing on like, the process that got you there instead of just the outcome,

like, I think not only CS, but most disciplines,

right? Like, we've been using go write a new essay on Catcher in the Rye. Like, we don't need another essay on Catcher in the Rye. Go write a new linked list. We don't need another linked list. We've been using the artifact that's produced from that as a proxy for you put in the time and the struggle and like, faced the friction that we assume that you now have learned something. It might be more appropriate to just focus on do we have evidence that you struggled and learned? Turn in the whole package. Right?

</details>

### 重构软件工程本科课程体系

>> 课程大纲通常是由委员会制定的，这自有其充分理由。但如果有这么一所“提图斯的软件工程学院”，你能亲自为一个比如说三到四年的本科项目制定大纲和研习课程，在当下它会是什么样子？我们探讨的前提是培养工程师——理想情况下是培养出能够直接在软件和工程公司上手工作、熟练运用 AI 工具、构建软件等等的工程师。

<details><summary>Original English</summary>

>> Curriculums are designed by committees, which is for a good reason, but if if you had Titus's software engineering school where you could yourself put together the curriculum and study course for an undergrad course of let's say 3 to 4 years,

how would it look like? Right now. And and we're talking about getting engineers

ideally having engineers who can hit the ground running at software and engineering companies obviously using AI tools, building software, that kind of stuff.

</details>

>> 是的。我认为第一门课，也就是第一学期，要在没有 AI 辅助的情况下开始。我们必须让你至少达到能看懂代码、对正在发生的事情有大致概念的水平，比如能理解控制流以及这类基本概念。我认为针对教学目的而设计良好支架与约束的 AI 存在一些非常有趣的切入点，也就是我们故意不直接给你答案；再结合如果你评估的是整个产出过程与创造过程，那么你就不必担心他们直接跑去问 ChatGPT 拿到完整答案，对吧？所以一部分问题就解决掉了。老实说，我其实不知道。没人知道，目前并没有现成的章法，但是……

<details><summary>Original English</summary>

>> Yeah. So, I think the first course, like the first semester, starts unaided by AI. Like we need to get you through at least the level that you can read code and have a vague idea of what's going on, like can understand control flow and those sorts of things. I think there's some really interesting things on well-scaffolded and harnessed AI for educational purposes of we're intentionally not just going to give you the answer and in conjunction with if you're assessing the whole package and process of creation, then you don't need to worry about them going to chat GPT and just getting the whole answer, right? So, like some of that's covered. I mean, I'll be honest, I don't know. Nobody knows. There is no playbook, but

</details>

>> 我想听听你的鲜明观点。我想听听你的鲜明观点。我……

<details><summary>Original English</summary>

>> I want to get opinionated. I I I I I want to get opinionated. I

</details>

>> 我有过的想法之一是，把 CS0——不论是对非专业还是专业学生——设为程序导论。具体来说，就是你如何描述接口的输入、输出、结构与设计？对吧？我们可以探讨复选框和单选按钮之间有什么区别；什么时候该用普通按钮，什么时候该用其他 UI 控件；对于非 UI 的东西，比如命令行参数、位置参数等。你如何将这些组件连接起来？具体来说，如果这是你上过的唯一一门课，至少你为自己的使用场景所生成的 AI 盲写代码水准，会拥有一套稍微更连贯、更合理的界面设计语言，也更能契合实际用途。

比如我住在纽约，我所在的公寓楼里有一个洗衣房 App。它快把我逼疯了，因为他们用的是菜单 UI 而不是按钮，对吧？它的设计语言完全是错的。先从这里开始。

然后逐渐过渡，大致沿着你刚才提到的思路推进，逐步走向项目、团队协作这类的实践。尝试激发他们内心想要解决更大问题的动力，从而需要一些背景知识，比如：“哦，原来 Web 是这样运作的。远程 API RPC 调用是这样进行的。”你无法给人们提供一种他们还没意识到自己遇到的问题的解决方案，对吧？在他们真正试图解决这些问题之前，我们在理论中呈现的那些解法都只是冷知识罢了。它们只是孤立的、学术层面的概念，没有任何现实关联。要先通过把他们置于需要该方案作为解答的情境中，来激发那种求知欲，然后你再去提供那层背景知识。

我也极其渴望加入更多项目，原因有两点。首先，我不希望作业存在唯一的标准答案，因为现实工业界不是那样运转的，科研大多也不是那样运转的。其次，我希望将评审他人纳入打分：成绩的一部分来自于对他人的评判。比如审视他们的产出，或者他们的代码，或者两者兼顾，对吧？并且能够给出诸如“这很棒，你有考虑过在这里尝试另一种做法吗？”之类的反馈。

然后，还要根据“你是否能在给出反馈的同时不显得刻薄无礼”来给他们评分。因为团队协作中的心理安全感很重要，对吧？所有这些听起来工作量极大，但你可以用 AI 来完成其中一部分分析，比如进行情绪分析：“刚才那番话显得粗鲁吗？”对吧，诸如此类的事情。我认为我们可以建立起一个更实用、更注重动手实践、而且有效得多的教育体系。

而我担心的是，这种体系未来可能只会出现在软件工程系，而不是计算机科学系。

<details><summary>Original English</summary>

>> So, one of the ideas that I've had is let's make CS zero, like non-majors and majors alike, uh intro to programs. Like specifically, how do you describe the inputs and outputs and structure and design of the interfaces? Right? So, we could talk about what's the difference between a checkbox and a radio button. When do you use a button versus some other UI widget? For non-UI things, like what command line flags, you know, positional parameters. How do you like interface these components? Specifically so that if that's the only class that you ever took, at least the the AI vibe-coded slop that you produce for your own use cases is going to have a like slightly more coherent, sensible design language and like be more fit for purpose.

Like, I live in New York. Uh the condo building I'm in has a, you know, there's an app for the laundry room. And drives me insane because like they use like menu UI instead of a button, right? And like the just the design language is completely wrong. Start with that. And then graduate kind of along the lines of what you were saying of like we want to move up into like projects and teamwork and things like that.

Try to motivate them into in themselves wanting to solve a bigger problem. And then needing some background on, "Oh, this is how the web works. This is how a web remote API RPC call works." You can't give people a solution to a problem they don't realize they have, right? And until they're trying to solve these problems, those solutions that we present in theory are all just trivia. They're just isolated, academic, not connected to anything. Like motivate that by like getting them into a situation where they need that as the answer first. And then you can provide that background.

I also desperately want more projects for two reasons. I don't want the assignments to be there is a correct answer because that's not how the industry works. Mostly not how it research works. And I want them to grade Part of your grade is critique of others. Like look at their outcomes or their code or both. Right? And be able to say like, "That was great. Did you think about doing a different thing here?"

And then also grade them on can you give feedback without being a jerk? Because psychological safety in teamwork, right? And all of this sounds like a lot of work, except you can use AI to like do some of that analysis. Like let's do the sentiment analysis. Was that rude? Right? Things like that. And like I think we could have a much more practical, hands-on, like and much more effective educational structure.

And And I worry that that's going to be software engineering departments and not CS departments.

</details>

### 给应届生的职业建议与领域深度

>> 作为结语，针对眼下的应届生，那些正坐在计算机科学专业、软件工程专业教室里的大学生，他们看到行业门槛竞争愈发激烈、工具正在改变，在策略、行动方案以及具体实践方面，你会给出什么建议，来最大化他们进入该行业并在其中脱颖而出的机会？

<details><summary>Original English</summary>

>> And as closing for for grads right now, college students sitting inside of CS programs, software engineering programs, who are seeing, okay, it's it's more competitive to get into the industry, tools are changing, what advice would you give in terms of tactics, strategies to activities to do to maximize your chances of getting into the industry and then doing well there.

</details>

>> 这或许听起来有些冒险，但我一生中的大部分成功，都来自于不做其他人都在做的事。

如果你只是听信什么是热门话题，盲目追逐跟所有人一模一样的时髦事物，你真的会极其难以脱颖而出。对吧？

所以我认为，关键是要忠于自己。找到你真正感兴趣的东西，并在你真正在意的事情上投入时间，尤其是当它比你周围人所做的事情更加标新立异的时候。因为这样一来，你在面试官面前就有了与众不同的故事可讲。在酒会交谈中你也会变得言之有物，从而让初创公司的创始人觉得：“对，我想在这个年轻人身上押一把注。”对吧？你投入在这些事情上的时间越多，你能带入其中的专业积累就越深，你的境遇就会越好。

我有一个担忧：在 AI 辅助工程的背景下，我们对纯粹工程技能的重视程度正在下降。你凭借浅得多的深度就能勉强应付。但能弥补这一点的唯一途径，就是你必须对所处的问题领域有深刻得多的理解。

而且我认为这实际上可能会导致行业内流动性的降低。不再是我是一名 C++ 工程师，或者我是一名后端工程师；而是我是一名深耕嵌入式音频的工程师，对吧？你必须在极深得多的层次上去理解那些问题领域，而那才是你真正的优势。

<details><summary>Original English</summary>

>> This might be risky, but most of my success in life has come from not doing the thing that everyone else is doing.

Like it is really incredibly hard to stand out if you are just listening to what is a hot topic and chasing the same shiny thing that literally everyone else is doing. Right?

And so I think it is to thine own self be true, right? Like find something that you are actually interested in and put in the time doing something that you care about, especially if it's weirder than what everyone else around you is doing. Because then you will have a novel story to tell your interviewer. You will be worth talking to at a cocktail party, so that the, you know, startup founder is like, yeah, I want to take a risk on this kid, right? Like and the more time that you put into these things, the more expertise that you can bring to it, like the better off you're going to be.

I have a worry that with AI-assisted engineering, our emphasis on raw engineering skill is dropping. Like you can get by with a lot less of that depth. But the only way to replace that is you need to understand the problem domain that you're operating into a much deeper level.

And I think that that might actually lead to less mobility in industry. Like, it's not I'm a C++ engineer or I'm a back-end engineer. It's a I'm an engineer in embedded audio. Right? Like, you have to understand those problem domains to a much deeper level, and that's your actual advantage.

</details>

>> 最后，除了你那本精彩的著作之外，你还会推荐哪本书，为什么？

<details><summary>Original English</summary>

>> As a closing, what's a book that you would recommend then why outside of your excellent book, of course?

</details>

>> 我前面提到过，但我还是坚持推荐它。凯特·希克斯（Cat Hicks）写的《软件团队心理学》（*Psychology of Software Teams*）。尤其是书中的那几个章节，如果我能把它们直接载入到周围每一位领导者的脑海里，我会感到无比欣慰。比如……

……的脑海里

<details><summary>Original English</summary>

>> I mentioned it earlier, but I'll stick with it. Uh Psychology of Software Teams by Cat Hicks. Especially, like, there are a couple chapters in that that if I could have that downloaded into the brains of every leader around, I would be so happy. Like,

the brains in

</details>

<!-- chunk 13/13 -->

罐子的比喻……嗯，令人难忘。所以，那个比喻真的很棒。

<details><summary>Original English</summary>
jars analogy is um haunting. So, that one's a really good one.
</details>

>> 好吧，Titus，非常感谢你参与这次对话。

<details><summary>Original English</summary>
>> Well, Titus, thank you so much for this conversation.
</details>

>> 非常感谢你邀请我。这真的非常有趣。

<details><summary>Original English</summary>
>> Thank you so much for having me. This has been a lot of fun.
</details>

### 对话回顾与总结

>> 我很高兴终于能和 Titus 坐下来聊聊，而且这次对话完全没有让人失望。首先，我知道 Google 的代码库很大，但我完全没想到单是 C++ 代码就有 2.5 亿行。而且这全都是在 AI 出现之前的事，所以我们讨论的并不是由 AI 生成的那种过度冗长的代码库。作为对比，早在 2016 年，Uber 的移动端应用的代码库大约有 100 到 200 万行 iOS 和 Android 代码，而 Uber 当时把大量的业务逻辑都塞进了那些应用里。Titus 和团队在不使用 AI 的情况下清理这些基础代码的方式也很有启发性。他们构建了确定性的代码生成工具来解析代码、匹配模式，然后生成修改。即使在今天，这种方法也可能比直接让非确定性的 AI 去重构代码库更可靠地起作用，尽管像 Titus 和团队那样在一个代码库上编写高级解析逻辑可以说要困难得多。

<details><summary>Original English</summary>
>> I'm glad I got to finally sit down with Titus, and this conversation did not disappoint. To start with, I knew that Google's code base was large, but I had no idea we're talking about 250 million lines of just C++ code. And this was all pre-AI, so we're not talking about over the verbose code bases generated by AI. As comparison, Uber's mobile apps had code bases of about 1 to 2 million lines of iOS and Android code back in 2016, and Uber crammed a lot of business logic into those apps. How Titus and the team cleaned up these foundations without using AI was also pretty educational. They built deterministic code generation tools to parse the code, match patterns, then generate edits. This is an approach that still could work more reliably even today than just asking a non-deterministic AI to refactor a code base, even though it is arguably more difficult to write advanced parsing logic on a code base like Titus and team did.
</details>

我也很赞赏 Titus 关于 AI 如今在哪些方面有用的看法。他提到了他从一位资深工程师那里听到的一句话：“我们的代码量增加了 70%，但我们的故障也增加了 30%。功能数量却是一样的。”嗯，那听起来可不太妙。那么 AI 的价值究竟在哪里呢？

<details><summary>Original English</summary>
I also appreciated Titus's view on where AI is helpful today. He mentioned this quote he heard from a senior engineer that said, "We are up 70% on the amount of code, but we're also up 30% on outages. The number of features is the same." Well, that doesn't sound all that good. Where's the value from AI then?
</details>

Titus 说，做我们在 AI 出现之前所做的同样的事情，只是做得更快，我们并不会从中获得多少价值。真正的价值在于变得更有抱负，去做我们在 AI 出现之前绝不会尝试的更难的事情。

<details><summary>Original English</summary>
Titus says that we won't get all that much value from doing the same stuff we did before AI, but faster. The value is to be more ambitious and do harder things that we would never attempted before AI.
</details>

最后，我听到很多关于科技行业应届生的担忧，担心他们能否找到工作，尤其是在 AI agent 如此普遍使用、但计算机科学（CS）项目却没有将它们纳入课程的情况下。Titus 是少数担任过 CS 课程指导委员会成员的工程师之一，他表示这个项目要么必须大幅改变并变得更加注重实践，要么 CS 的入学人数将会暴跌。Titus 还表示，最终建立一套专注于让学生获得更多使用这些现代工具构建软件的经验的软件工程课程，也许是合理的。

<details><summary>Original English</summary>
Finally, I hear a lot of worry for new grads in tech about how they'll get a job or not, especially when AI agents are so commonly used, but CS programs have not incorporated them into their program. Titus is one of the few engineers who has been part of the steering committee for the CS curriculum and says that this program needs to either change substantially and be more practice oriented or CS enrollment will plummet. Titus also says that it might make sense to finally have a software engineering curriculum that is focused on students getting far more experience building software with these modern tools.
</details>

我认为我们中没有人能给出什么样的做法会奏效的答案，但让更多来自业界的人更多地参与到革新 CS 软件工程课程中来，在我看来像是朝着正确方向迈出的一步。

<details><summary>Original English</summary>
I don't think any of us has an answer to what will work, but having more people from the industry get more involved in refreshing the CS software engineering curriculum sounds like a step in the right direction to me.
</details>

请查看节目备注中与 Pragmatic Engineer 深度探讨 Google 工程文化、衡量开发者生产力以及 AI 对软件工程的影响相关的内容。如果你喜欢这期播客，如果你能在上面留下评分或许还有评论，我将非常感激。非常感谢，我们下期再见。

<details><summary>Original English</summary>
Check out the show notes for related to the pragmatic engineer deep dives on Google's engineer culture, measuring developer productivity, and the impact of AI in software engineering. If you enjoyed this podcast, I'd greatly appreciate it if you left a rating on it and perhaps a review. Thanks a lot and see you in the next one.
</details>