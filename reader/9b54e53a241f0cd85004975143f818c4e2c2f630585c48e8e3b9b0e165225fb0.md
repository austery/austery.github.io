---
author: The Pragmatic Engineer
date: '2026-03-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DfrAaDgFgjc
speaker: The Pragmatic Engineer
tags:
  - developer-experience
  - cognitive-load
  - feedback-loop
  - productivity-metrics
  - organizational-change
title: AI时代如何领导高效工程团队：Nicole Forsgren谈摩擦消除与未来
summary: Nicole Forsgren分享了AI如何加速软件开发但同时放大了交付瓶颈，特别是在代码审查和部署方面。她深入探讨了DevX框架中的认知负荷、心流状态和反馈循环，指出AI的快速反馈循环可能增加认知负荷。访谈强调了心理安全、项目所有权和技术决策自主权对心流状态的重要性。她还建议企业通过采用率和参与度来衡量AI工具的价值，并介绍了SPACCE框架（满意度、绩效、活动、沟通与协作、效率与流程）。面对不确定性，领导者应明确鼓励员工试验AI，建立安全空间，并强调建立“个人董事会”以寻求支持和避免职业倦怠的重要性。展望未来，她认为无摩擦组织将依赖数据洞察系统，并持续优化迭代循环。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Nicole Forsgren
companies_orgs:
  - Google
  - Etsy
  - HashiCorp
  - Sentry
  - Atlassian
products_models:
  - Frictionless
  - Dora
  - SPACE framework
  - DevX framework
  - Opus 4.5
  - Cloud Code
  - Jenkins
media_books:
  - Frictionless
status: evergreen
---
### AI时代软件开发与交付的摩擦

**Host**: Nicole，很高兴你能来到这里。上次我们进行长篇对话，以一种许多人会喜欢的方式，是在播客上。那时，**Frictionless**还没有发布。你当时在别的地方工作。现在，**Frictionless**已经发布了。恭喜你！你现在在**Google**从事着一份有趣而激动人心的工作。你能告诉我们你最近在忙些什么，以及什么让你夜不能寐吗？

<details>
<summary>Original English</summary>

**Host**: Nicole, it is so nice to have you here. Last time that you and I talked in more long form in a way that a lot of you could enjoy was on the podcast. And back then, Frictionless was not yet out. You were working somewhere else. Now, Frictionless is out. Congratulations. You're now doing a fun and exciting job at Google. Can you tell us a little bit of what you're up to these days and what keeps you up at night?

</details>

**Nicole**: 哦，天哪，我们有多少时间？嗯，工作非常相似，对吧？比如我们如何思考改进人们开发软件的方式？我们如何思考——我喜欢**Laura**今天早上提到的——如果我们不能称之为开发者体验，就称之为**agent experience**，那么一切都会顺利。思考如何让agent更智能、更好，以便我们能更好地与它们合作。我们如何衡量生产力这样非常困难的事情？因为**Martin**在上次会议中提到，衡量标准已经有点糟糕了，现在更是糟糕透顶。所以，我们如何找到方法？因为一方面，我们不喜欢生产力指标，因为它可能感觉像是一种攻击。但如果我们什么都没有，如果这只是凭感觉行事，我相信我们都曾在与总监或副总裁的会议中遇到过，他们只是凭直觉觉得“我们就应该这样做”。如果agent也只是凭直觉行事，他们似乎不会非常接受，所以拥有某种信号是很有帮助的。

<details>
<summary>Original English</summary>

**Nicole**: Oh my gosh, how much time do we have? Um, very similar work, right? Like how can we think about improving the way people build software? How can we think about I love that, you know, Laura mentioned this this morning. If if we can't call it developer experience, just call it agent experience and then it's all going to work. um thinking of ways that we can make agents smarter and better so that we can work with them better. Um how do we measure really hard things like productivity because you know Martin mentioned in the last session um the measurements were already like kind of bad and now they're like extra bad. So, so how can we find ways because like on the one hand we don't love a productivity metric because it can feel like an attack but if we have nothing right if this is just like vibes I'm sure we've all been in a meeting with a director or a VP or something where they like just have a gut feel this is just how we should go you know they don't seem to be super open to it if agents just go on gut feel so so having some kind of signal is helpful

</details>

**Host**: 你的书，无论是开头还是封底，都提到AI正在帮助我们比以往任何时候都更快地创建软件，但交付或发布仍然非常缓慢。这两件事是如何并存的？这其中发生了什么？

<details>
<summary>Original English</summary>

**Host**: One thing that struck me about your book, when the very either the very beginning or the back cover it says that AI is helping us create software faster than ever and yet delivery or like shipping is just still so slow. How do these things these two things go together? What what is happening in between?

</details>

**Nicole**: 我认为有几件事。首先，我们都开始关注**生成式AI**和编码，你知道，那个内循环，因为我们可以看到它，所有的多巴胺冲击都来自那里。那里一切都非常令人兴奋。然后当我们进行交付时，我们有一些系统，我们已经知道它们可能可以改进，但以前还算可以，对吧？可能有一些人在管理安全审查流程、发布流程或部署流程，或者有时审查有点慢，积压了。现在我们只是火上浇油，所以所有这些都成了问题。我们正在做的是，我喜欢**Tibo**今天早上提到的，我们正在追逐这些限制。我们正在追逐瓶颈，以一种比过去更加明显的方式。所以在短期内，是的，我们产出了更多，但现在我们的系统，无论是技术系统、人类系统还是流程，都真正地被压垮了。

<details>
<summary>Original English</summary>

**Nicole**: So I think there's a few things, right? One is that we all started focusing on Gen AI and the coding, you know, that interloop because we can see it and that's where like all of the dopamine hit comes. That's where it's all very exciting. And then as we go to ship, we've had systems that like we already knew they could probably be improved, but like it was fine, right? There were a handful of people probably managing a security review process or a launch process or a deployment process or, you know, sometimes reviews were a little slow and they got backed up. Well, now we just threw gas on the fire and so all of that is a problem. And so what we're doing I I liked how you know Tibo mentioned it this morning. Now we're kind of chasing those constraints. We're chasing the bottlenecks in a way that it's much more obvious than it was in the past. And so like in the immediate term, yeah, we were getting more out, but now our systems, whether technology systems or human systems or processes are really kind of getting overwhelmed.

</details>

**Host**: 你能举一些具体的例子吗？我们不需要点名具体的公司，但比如说，现在他们都在使用这些AI工具，但这些工具反而让他们慢下来了。

<details>
<summary>Original English</summary>

**Host**: Do you have some specific examples? We don't need to name specific companies but like a thing where like oh you know now they're using all these AI tools but these are things that are slowing them down.

</details>

**Nicole**: 有一些事情。嗯，这取决于他们在流程中的哪个阶段。**审查**最终会暴露出很多问题，对吧？因为我们投入了大量的工作。不仅如此，人类在审查过程中已经是一个瓶颈。现在情况可能更糟，因为一些公司对相当直接的变更进行了自动化审查，但如果**AI**参与其中，他们担心代码的可验证性或可靠性，所以现在审查的负担转移了。我也看到了不少——我仍然与一些公司保持联系——我们正在部署和发布过程中看到不少问题，对吧？对于许多不了解“香肠是如何制作的”的人来说，那是一个空的黑箱。但很多时候，这个过程一直由人类管理，因为你要选择正确的候选版本，并进行验证，你还要考虑，你知道，找出cherry picks，然后你重新打包，然后发送出去。这无法扩展。如果你有一两个或少数人试图做出集体决策并进行集体理解。

<details>
<summary>Original English</summary>

**Nicole**: There are a handful of things. So uh and it you know it kind of changes depending on where they are in the process. Review ends up surfacing quite a bit right because we're just we're putting so much work on it. And not only that but like humans were already a bit of a bottleneck in the review process. Now it can be worse because things that we fairly straightforward changes that some companies had automation around reviewing they've removed that reviewing because if AI is involved and they're worried about the verifiability or the reliability of the code and so now that review burden has shifted. I'm also seeing quite a bit uh I still talk to, you know, a handful of companies. We're we're seeing quite a bit in that deployment and release process, right? That's kind of empty black box for a lot of folks who like don't know how the sausage is made. But so many times that process has been managed by humans because you're selecting the right candidate build and you're verifying it and you're thinking, you know, you're figuring out cherry picks and then you like rebundle and then you send it out and that doesn't scale. if you have one or two or a handful of people trying to make group decisions and do group sensemaking

</details>

### 组织结构与AI对开发流程的影响

**Host**: 在你的书里——我知道这本书是在**Opus 4.5**之前出版的——它描述了这样一个场景：一个新员工加入公司，使用**AI**工具，但她的第一个贡献却在那里搁置了两到三周，因为代码审查没有标记出来，她也没有数据库访问权限。你能给我讲讲这些事情吗？我们很多人，以及坐在这里的一些人，实际上在初创公司工作，在那里，从部署到发布是非常常见的事情。这些事情有多常见？这些事情让人感到惊讶，比如“哦，这些东西被卡住了，人们只是闲着无所事事一段时间”。你认为这会持续下去吗？你认为**AI**的压力会促使我们消除和识别这些问题吗？你观察到哪些趋势？

<details>
<summary>Original English</summary>

**Host**: And in in in the book I I realize the book came out before Opus 4.5 but it described this scenario which seems like really alien but obviously it's based on a true story that there's a new hire joining a company uh using AI tools this person turns out her first contribution and then for I think two or 3 weeks it sits there because the the code review didn't flag it she didn't have access the database. Can you tell me a little bit about like some of these things? Like a lot of us, some people sitting here are actually working at startups where like it's just common thing to like go from like deployment to shipping pretty quickly. How common are are these things which are like just surprising people of like oh these things are being stuck. People are just fiddling in your thumb thumbs for a while and do you see this like being the same? Do you see because of AI pressure being on on removing these things and recognizing them? what what are trends that you're observing?

</details>

**Nicole**: 我认为我正在说的一件事可能不会让在座的很多人感到惊讶，那就是组织仍然会进行组织，对吧？所以，当你有一个审查流程，我们等待两周，或者只有一个人必须批准，但那个人可能很忙。所有这些我们围绕着结构化流程来努力使事情更统一的东西，往往正是减慢我们速度的原因。所以，虽然我们正在加快那个内循环，现在我们开始看到**agent**在审查和少数其他任务方面做得更多，但很多公司直到现在才开始思考如何将**AI**应用到非常人性化、非常业务流程的部分。所以，在我们找到解决办法之前，这会一直减慢我们的速度，对吧？很多时候，当我刚开始工作时，我获得了数据库访问权限，而两周没有数据库访问权限在历史上通常是没问题的。也许不太好，但90%的时间都是没问题的。然而现在，你可以在入职第一天就提交代码，而公司不一定为此做好了准备，对吧？比如**Etsy**就以你入职第一天就能提交代码而闻名，但他们知道这会发生。所有其他公司都不知道这会发生。我知道一两个实习生的案例，由于政策和一些供应链问题，他们两周都没有拿到笔记本电脑。所以，他们使用的是一台借用的电脑。他们在笔记本电脑到手之前就已经提交了很多代码，但系统中的没有人——他们正在处理一个特别安全的事情——无法弄清楚如何让它工作，因为它不符合源代码与他们认为的预期不符。所以，我认为我们现在真正看到的是，以前还算可以的事情受到了重视和关注，正是这些摩擦现在真正减慢了我们的速度。

<details>
<summary>Original English</summary>

**Nicole**: I think one thing I'm saying that probably won't surprise a bunch of folks here is organizations are still going to organize, right? So like when you've got like some review process and we wait two weeks or like someone the one person has to sign off on it but that person's like oof or like all of the the things that we have structured process around to try to make things more uniform are often the things that slow us down. So again, while we're kind of speeding up that interloop, and now we're starting to see agents do more around uh you know, reviewing and and a handful of other tasks, a lot of companies haven't started until now thinking about how we could apply AI to the very human very business process part of it. And so that will keep slowing us down until we find a way to to address it, right? And a lot of that comes with when I first start, you know, I get database access and not having database access for 2 weeks has like historically usually been fine. Maybe not great, but like you not like 90% of the time it was fine. Well, now when you can be committing code on your first day in ways that the company wasn't necessarily structured for, right? Like Etsy famously, you know, you you would commit code on your first day, but they knew that was coming. All of these other companies don't know that's coming. I knew of one or two cases with an intern where because of policies and a couple like uh supply chain snafoos, they didn't get their laptop for like two weeks. So, they were on a loner. They had committed a lot of code before their laptop showed up and like no one in the system. There was like one particularly secure thing they were working on. They couldn't figure out how to make that work because it didn't match the source didn't match where they thought it would. And so I think we're really seeing kind of an emphasis and a spotlight on the things that were kind of fine before and it's that friction that really slows us down now.

</details>

### DevX框架：认知负荷与AI的影响

**Host**: 你一直很擅长的一件事，我非常关注你的工作，我认为它影响了我自己和行业中许多其他人，那就是衡量这些非常难以衡量的事情。你经历了很多次迭代。我们有**Dora**、我们有**SPACE**、我们有**DevX框架**等等。在**DevX框架**中，这是在**AI**之前。我们能谈谈**DevX框架**是什么吗？然后，其中的一部分是**认知负荷**，它如何融入**AI**？

<details>
<summary>Original English</summary>

**Host**: When one thing you've been like so good at and I paid so much attention to your work and I think it's influenced myself and a lot of other people in the industry is is measuring how we can measure these very hard to measure things. And one of the the latest you you went through a lot of iterations. We have Dora, we have space, we have the DevX framework and and more. And in the DevX framework, this was pre AAI. Can we talk a little bit about what the DevX framework is? And then like one part of it is cognitive load, how that feeds into AI.

</details>

**Nicole**: 是的。所以，思考开发者体验有很多方法，但我发现一种很有用的是，它有三个相互关联的部分。它们是**心流状态**，**认知负荷**，还有——我怎么忘了最后一个了？**Laura**？

<details>
<summary>Original English</summary>

**Nicole**: Yes. So there are many ways to think about uh developer experience, but one that I find kind of useful is there there are three pieces that kind of fit together. So there's flow state, there's cognitive load, and there's why am I forgetting the last one? Laura,

</details>

**Host**: 反馈循环。

<details>
<summary>Original English</summary>

**Host**: feedback loop.

</details>

**Nicole**: **反馈循环**。我看看**Laura**。别担心。谢谢**Laura**。嗯，它们都相互支持，对吧？因为当我在心流中时，反馈循环非常重要。如果我不得不等待20分钟，如果我不得不等待一周才能得到答案，或者得到审查反馈，那么我就会打破我的心流。嗯，这也会增加认知负荷。所以，认知负荷基本上就是我们大脑需要做的工作。我们所做的事情中存在一定程度的固有认知负荷，对吧？所以困难的事情会消耗更多的脑力，但简单的事情不应该消耗脑力。但有时，当我们有一段时间没有接触一个代码库时，重新熟悉它会带来更高的认知负荷。所以如果我已经进入心流状态，我就可以免费完成很多工作。或者，任何时候我必须处理一个非常神秘的流程，并经历一百个步骤，这很容易，因为它很直接，但它需要大量的工作，对吧？这就是，你知道，我认为思考人本身会非常有帮助，因为，你知道，在早些时候的几次演讲中都提到了，对人有益的，对系统也有益。如果我有结构良好的代码，如果我有结构良好的文档，如果我有清晰定义的API，并且我知道这些接口是什么样的，那会非常有帮助。然后我要说的是，我们现在需要重新审视这个问题：我们如何思考认知负荷？因为我想说**Gloria Mark**在专注方面做了一些非常出色的工作，人类每天进行真正非常深入的专注工作最多只能达到三到四个小时。嗯，这总是让我发笑，当高管们说“我们需要八小时的密集工作”时，我就想“不，人类做不到，我们的大脑不是那样运作的”。所以现在，当我们有这三到四个小时时，我们如何最好地利用它们？当我们与**AI**和**agent**合作时，这意味着什么？因为对我们中的一些人来说，深入的工作意味着我 bloquear 我的日程表，我可以真正投入其中，我可以做一件事，我可以非常深入地思考。而现在很多模型都非常具有中断性，对吧？我一直收到提醒。所以，我如何改变我的工作方式，或者我如何思考管理我自己的认知负荷？我们如何更广泛地在组织中思考它，知道我们所做的工作的性质在很多时候确实发生了变化？

<details>
<summary>Original English</summary>

**Nicole**: Feedback loops. I'll look at Laura. Don't worry about Thanks, Laura. Um, and they all kind of support each other, right? Because when I'm in the flow, the feedback loops are really important. If I have to wait 20 minutes, if I have to wait a week to get something an answer, uh, a question answered or a review back, then I break my flow. Um, that makes it harder for cognitive load as well. So, cognitive load is basically like the work that our brain needs to do. And there is some inherent level of cognitive load in something we do, right? So something that's difficult is going to take more brain power, but things that are easy easy should not take brain power. But like sometimes reampramping into a codebase when we haven't been into it for a while, that's higher cognitive load. And so if I'm already there, I can get a bunch of that work for free. Or anytime I have to deal with like a really arcane process and go through a hundred steps, it's easy because it's straightforward, but it takes a lot of work, right? And that's where you know I thinking about the human can be really helpful because you know it was called out in a couple talks earlier what's good for humans is good for systems. If I have well structured code if I have well structured documentation if I have uh APIs that are like cleanly defined and I I know what those interfaces look like it can be really helpful. And then I will say it's it's kind of revisiting this question of now of how do we want to think about cognitive load because I want to say Gloria Mark has done some really incredible work on focus and humans max out at about like 3 to four hours a day like really really hard deep work right um which always makes me laugh when exact like we need eight hours of intense work and I'm like not with humans that's our brains don't do that and so now when we have these three or four hours how can we use them best. And what does it mean when we're working with AI and with agents? Because for some of us, um, good deep work means I block my calendar and I can get really embedded and I can do one thing and I can think really hard. And now a lot of the models are very interruptive, right? I'm getting pinged all the time. And so, how can I change the way I work or how can I think about managing my own cognitive load? How can we think about it more broadly in organizations knowing that the nature of the work that we're doing in many times has really changed?

</details>

**Host**: 我在**agent**身上看到一个有趣的现象，你们都会看到，那就是**反馈循环**更快了，对吧？你告诉它“做这个”，它很快就回来了，尤其是一些像**Cloud Code**这样的模型在这方面非常擅长。然后你就开始感到非常疲惫，因为用你的术语来说，认知负荷因为更快的反馈循环而增加了，这似乎是如此反直觉。因为在**AI**出现之前，我们总是追求迭代、快速反馈循环。我们从未如此接近过拥有如此快的反馈循环。那么，到底发生了什么？这到底是好事还是坏事？拥有更快的反馈循环是好事，但拥有更多的认知负荷是坏事吗？或者说，这感觉像是一个矛盾。

<details>
<summary>Original English</summary>

**Host**: And one interesting thing I see with with agents and all of you will be seeing it is the feedback loop is faster right you tell it do this and it comes back especially some models like cloud code are very good at doing that and then you start to get really tired because in using your terminology like the cognitive load increases by faster feedback loops and it seems so counterintuitive Because until before AI, we're always we're all about iteration, fast feedback loops. We we we were never ever close to having these fast feedback loops. So what what what is happening? Is this a net good? Is this a net bad? Is it it's is it good that we're having faster feedback loops, but is it bad that we're having more cognitive load or how are like it it feels like such a contradiction.

</details>

**Nicole**: 我认为这只是不同了，对吧？所以，以前快速反馈循环是好的，因为如果我，举个例子，对一个库有疑问，有人能回复我，那么我就可以继续工作，对吧？虽然会有一点暂停，但我会继续。而现在，我收到反馈的速度如此之快，以至于我有时不得不在大约30分钟内重建我的心智模型几十次。所以，这不仅仅是，快速反馈是好的，但如果它比我能跟上的速度还快，或者如果它具有中断性，因为，你知道，有时当我不准备好它们完成时，它们只是想注入文本。所以，你知道，我认为其中一些是，你知道，有时我就是会把它关掉，因为我只是需要写一会，然后我再让它审查。所以，我要说的是，现在很多都是一个开放性问题。PE（绩效工程）的人正在开始研究它，但六个月前的环境与现在的环境已经非常不同。所以，这是一种不断演变的情况。你提到你把它关掉很有趣，因为我大约一周前和**HashiCorp**的创始人**Michel Hashimoto**交谈，他告诉我他的工作流程是：他有一个**agent**总是在旁边运行，但所有的通知都关掉了，因为他只在他准备好的时候才去处理，他启动它后就不管它什么时候完成。我感觉我们可能正在开始发现自己的工作风格，什么有效，什么无效。但是说到心流状态，你知道，处于心流中，作为一名工程师曾经是很棒的，我以前在心流中工作效率很高，而现在有了**AI**，你也可以更容易地进入心流。在你的书里，你确实提到了一个有趣的事情，这与工具有关，但你说**心流状态**不仅取决于工具。你特别提到了心理安全、项目所有权、技术决策的自主权等等。你如何看待这种变化？当工具似乎非常擅长让人进入心流时，我们是否会看到人们仍然因为缺乏很多这些东西而难以进入心流？

<details>
<summary>Original English</summary>

**Nicole**: I think it's just different, right? So fast feedback loops were good before because if I for example, if I had a question about a library and someone could get back to me, then then I could continue on, right? like there was a bit of a a pause, but I kept going. Well, now I'm getting feedback so quickly that I'm having to sometimes rebuild my mental model dozens of times in like a 30-minute period. And so it's not just it getting fast feedback is good, but if it's faster than I know how to keep up with or if it's interrupting because, you know, sometimes they just want to inject text when I am not ready for them to do that completion. And so, you know, I think some of that is, you know, sometimes I'll just turn it off because I just like need to write for a second and then I'll let it review. So, it's I will say right now like a lot of this is kind of an open question. PE people are starting to look at it, but also what the environments were like 6 months ago is very different than what they were like now. So, this is kind of evolving. It's interesting when you said like you turn it off because I was talking with Michel Hashimoto uh founder of of Hashi Corp about a week ago and he was telling me that his workflow is he has an agent always side by on the side that usually runs but he turned off all notifications because he only wants to go when he is ready and he kicks it off with something and he doesn't care when it finishes and I feel we might be like people might be starting to discover their working style on on what works and what doesn't. But speaking of flow state in in you know like being in the flow it it used to be amazing as an engineer I I used to be really efficient in the flow and now with with AI you can also kind of get into flow maybe a little bit easier. In your book you did mention something interesting and this is about the tooling but you said flow state does not only depend on tooling. You specifically said how things like psychological safety project ownership uh how technical decisions how how much autonomy you have all those depend. How do you see this changing with AI where like the tooling seems to be really good at getting in the flow? But could could we see that people are actually still struggling to get into the flow because they're lacking a lot of those things?

</details>

**Nicole**: 嗯，技术很简单，人很难。所以，你知道，有时进入心流状态确实是关于理解我在做什么，有非常清晰的方向和目标，并且知道我的工作在做什么，所以它的范围是明确的，但我不仅仅有一个范围明确的功能或任务，我还要知道它的目的是什么，这样我才能做出明智的决定。其中一部分是拥有**心理安全**，这样我才知道我可以冒险做某事，或者我可以向团队中的某人提问。你知道，**Kent**提到，当我们称**AI**为**genies**（精灵）时。当我们与精灵合作时，这并不是一回事。我们可能有一些精灵，但这与拥有一些朋友不同，对吧？部分原因在于能量不同。对话也不同。而且，它们总是同意我们。我总是觉得自己很聪明，我就想，我知道那很蠢，我知道那非常蠢。所以，我要说的是，我做得最好的工作。比如，我想不出任何一篇论文或一本书是我独自完成的，因为很多时候我开始写，我会写大部分，然后我就会想，我真的需要有人告诉我哪里有问题，我哪里愚蠢了，我遗漏了什么，在我脑海中完全合理的事情，当我说出来时，对他们来说是否合理？我们的**AI**工具和**agent**还没有达到那个水平。有时它们猜得很好，有时它们猜的方向完全是正交的。但是关于那一点，你想讲一个关于**Frictionless**这本书的故事吗？当你开始写它，然后你又回去，我想你删除了很大一部分，对吧？

<details>
<summary>Original English</summary>

**Nicole**: Uh well, tech is easy, people are hard. And so, you know, sometimes getting the flow really is about understanding what I'm doing, having very clear direction and goals and and knowing what my what my work is doing so it's well scoped, but I also not just have a well scoped feature or something, but I I know what the purpose of it is so that I can make informed decisions. Some of it is having that psychological safety so that I know that I can take a risk on something or I can ask someone on my team. And you know, Kent mentioned when we he was calling AI the genies. When we're working with the genie, that's not the same thing. We might have a handful of genies, but that's different from having a handful of friends, right? In part because the energy is different. The conversations are different. Also, they just agree with us constantly. I'm always so smart and I'm like, I know that was dumb. I know that was very dumb. And so, and I will say I do my best work. Like, I I can't think of any paper as one example. paper or book I've written on my own because many times I get them started and I'll write most of it and then I'm like I really need someone to tell me like where a hole is, where am I dumb, what am I missing, what makes perfect sense in my head, but does that make sense to them when I say it? And like our our AI tools and agents just aren't there yet. Sometimes they guess really well and sometimes they guess in a completely orthogonal direction. But on on that one, do you want to tell a story about the frictionless the book when you started writing it and then you you went back and I think you deleted a good part of it, right?

</details>

**Nicole**: 听着，我当了多年的软件工程师，然后是一名研究员，我写了很多东西。研究员写作的方式非常独特。有很多细节。有很多背景，直到第105页你才切入正题。所以我当时已经开始了。我可能和某人合作，我们聊了聊，但我读完了整本书的这一部分，我意识到我创建了几个章节，基本上是关于如何在不是研究员的情况下进行研究，比如如何写出好的调查问题，如何与人交谈以理解，它非常详细且易于理解，有100页，但没有人需要读，没有人会读这个。所以我只是把它扔掉了，然后联系了**Abby**，我说：“你想写这本书吗？我想我大概知道方向了。另外，如果我陷入死胡同，请告诉我。”因为它很有意义，而且是正确的。另外，没有人会，没有人想读那个。我们最终把它变成了书后的练习册，这很棒，因为那时它就像填写表格，检查东西，让它真正有用和可操作。所以我不太擅长这一点，这就是我**心流状态**的问题所在：我进入心流状态，但我会为错误的受众写作，或者以错误的视角写作，或者以错误的具体程度编码，尤其是在与**agent**合作时，对吧？有时我只是给它一个宽泛的指令，我就想，那本来应该更详细，但等我发现时，已经过了一个小时了。

<details>
<summary>Original English</summary>

**Nicole**: Listen, I was a software engineer for years and then I was a researcher and I was writing a bunch. Researchers write a very particular way. There's a lot of detail. There's a lot of background and on page like 105 you get to the point. And so I had started it. I was maybe working with someone like we kind of chatted about it but I get through this whole section of the book and I realize there's I've created several chapters of basically like how to do research when you're not a researcher like how to write good survey questions how to talk to people so you understand it was incredibly like detailed and easy to understand and 100 pages that no one needs to read ever no one is going to read this and so I just like tossed it and reached out to Abby and I was like do you want to write this book I think I have an idea of the direction I'm going. Also, tell me if I get in a rabbit hole cuz it made sense and it was right. Also, no one's going to no one wants to read that. And we ended up turning it into workbooks in the back, which were great because then it's like fill in the table, check the thing, make it really useful and actionable. So that I I'm not great at I'll that's my problem with flow state is I'll get in a flow and I'll write for the wrong audience or I'll write at the wrong altitude or I'll code at the wrong like level of specificity especially with agents right sometimes I'll just give it something broad I'm like that really should have been more detailed but by the time I find that out we're an hour in and

</details>

**Host**: 但我我想知道，如果一个收获可能是：努力并没有白费，对吧？你花了大量时间在**心流状态**下写作，姑且说是写错了，但你也在学习，然后最终的结果是某种特别的东西，如果不是你所说的“一击即中”，那它就不会发生。我们谈论了那么多“一击即中”的事情。你认为我们可能不得不真正重新学习，即使作为一个人，当**agent**可以无限次地做这些事情时，努力和浪费的精力可能对我们有帮助吗？

<details>
<summary>Original English</summary>

**Host**: But I I I wonder if if one takeaway might be that effort is not gone wasted right you spent a lot of time in flow state writing let's say the wrong and and learning and then the end result was something special something that would have not happened if you would have so-called oneshotted it we talk about so much of oneshotting things do you think like we might have to really relearn that effort and and wasted energy even as a human when agents can do infinite of these things it might be helpful for us

</details>

**Nicole**: 哦，我同意。你知道，一是能够清晰地阐明问题、论点或想法，而不是试图达到那个目标，对吧？嗯，很多事情都是如此，我认为这既包括学习事物并掌握它们。但一个对我来说非常有趣的开放性问题是，当我以前更多地编写代码时，我对系统有一种感觉，因为我一直在编写它。我了解这个系统吗？不，它太庞大了，对吧？但我知道我可以合理地在白板上画出我的那种感觉。而现在我们正在编写代码，并且事物变化如此迅速。我认为有一个非常有趣的开放性问题，那就是我们如何帮助支持和构建这些**心智模型**，不仅仅是为了减少**认知负荷**或改善**心流状态**，而是帮助我们理解我们的系统。无论是像我这样喜欢视觉化的人，多年前它刚出现时，我总是要求它生成**Mermaid图**，对吧？我需要看到它是什么样的，我需要它和我一起在白板上画图。我认为这对于其他人来说会是不同的，但如果不花时间，我们的大脑就是以那种方式运作的，对吧？我们的大脑就是以那种方式运作得更好。

<details>
<summary>Original English</summary>

**Nicole**: Oh I agree you know one is being able to clearly articulate the problem or the thesis or the idea without trying I don't get there right um and that's true of so many things I think It's both in terms of like learning things and kind of getting your hands around them. But one open question that I think is really interesting to me is back when I was doing more coding. I kind of had a feel for the system because I was coding it all the time. Did I know the system? No, it was huge, right? But I knew my kind of I could whiteboard it reasonably well and now we're coding and things are changing so rapidly. I think there's a really interesting open question around how can we help support and build these mental models not just in a way that reduce cognitive load or improve flow but help us understand our systems whether it's like for me I'm a visual person so I years ago when it was first coming out I was asking it for mermaid diagrams all the time right like I I needed to see what it kind of I needed my I needed it to whiteboard with me and I think that'll be different for for everyone else but without taking that time like we b our brains just work that way right our brains just work that that way better.

</details>

### 衡量AI时代的生产力：SPACCE框架

**Host**: 所以，我们谈论花时间，我们想了解这是一个漫长而巨大的变化，但这是一个向所有工程领导层提出的问题，他们正被他们的CEO和董事会以及所有这些事情所困扰，说：“好吧，我们为这些东西付了很多钱，我已经看到了，不是说我们如何衡量它，他们会问你，就像你们都参与了与**Nicole**的精彩对话，**Nicole**说了什么？我们应该衡量哪些指标？我们能诚实地谈谈我们目前所处的位置，什么可行，以及你对此有何看法吗？你肯定经常遇到这种情况。

<details>
<summary>Original English</summary>

**Host**: So, we talk about taking the time and we want to understand it's a long large change, but this one's a question for everyone in engineering leadership position who is being hammered by their CEO and board and all of these things saying all right we're paying a bunch of money for this stuff and I already see that not not how do we measure it and they're going to ask you like you all been with this excellent conversation with Nicole and what did Nicole say what metrics should we measure and like can we actually talk about honestly of of like where we are what what can work and how you think about this and you must get this so much.

</details>

**Nicole**: 这是我的工作。嗯，这取决于情况。总是“这取决于情况”。嗯，我们现在都可以去做咨询了，然后赚大钱。嗯，但确实如此。这取决于你试图提出的问题是什么，对吧？所以当有人说“我是否更有生产力？”时，我会说，“你所说的生产力是什么意思？”我看到了就知道。它呈现出什么形态？对吧？就像**代码异味**（code smells）一样，**生产力异味**（productivity smells）也有它的特点，对吧？有时是代码行数或PR（Pull Request）数量之类的。我就想，好吧，你从中学到了什么？对吧？那有助于你更快地向客户发布功能吗？有时他们会说，嗯，是的。我就想，好吧，那是正确的功能吗？我们知道它是正确的功能吗？我们正在放大端到端流程中的哪一部分？你还想要更多的想法、更多的代码行、更多的审查以及更多的一切吗？他们会说，嗯，不。我就想，我只是在提问，对吧？所以我认为这会有帮助。现在我们用什么来衡量生产力？我要说它正在演变，对吧？所以**SPACE框架**最终非常有帮助。所以**SPACE**是：

*   **S**atisfaction (满意度)：你对事物有多满意。
*   **P**erformance (绩效)：成果是什么，无论是质量还是其他。
*   **A**ctivity (活动)：这是你可以计算的任何东西。
*   **C**ollaboration and **C**ommunication (协作与沟通)：这可以是人与人之间，我们正在看到它的演变，也可以是系统之间。
*   **E**fficiency and **F**low (效率与流程)：这可以是当我们处于心流状态时，也可以是完成系统所需的时间，对吧？

我知道这里有几个人说，你知道，每个人都在谈论速度，他们希望事情更快，他们关心速度。我就想，我听到了。是的，那可能是好的。但你想设置什么**护栏**（guardrails）？对吧？我们想如何思考质量？我们想如何思考满意度？我们想如何思考其他什么？因为如果我们只是蛮力行事，就会出问题，对吧？而且，我们有办法做出明智的决定。我曾与一些团队合作过，我要说，在其他会议中有一个问题是关于为了速度牺牲质量。有些团队可以这样做，但当他们这样做时，他们是非常非常刻意地这样做。他们不会说他们在牺牲质量。他们会说他们在做**基于风险的决策**。这是公平的，他们正在进行快速实验。他们希望非常非常快速地获得信号，如果他们能在几个小时内完成一个实验，并且可以在非常小的百分比上运行它，那么他们愿意承担较低延迟或崩溃的风险，针对那非常小的百分比，然后他们将其撤回，然后得到一个答案。所以，我认为有了正确的**指标**，它确实可以帮助我们做出那些基于风险的决策，而不是要么全速前进，要么全速放缓。我仍然看到一些团队是全速放缓的，因为他们只是想踩刹车。你知道，安全领域的一些人，这是可以理解的，但他们现在有点“火烧眉毛”了，因为有太多事情要做。哦，是的，尤其是在其余的访问结束后。我们昨天举行了一个小型活动，我们谈到**Sentry**的**David Kramer**如何谈论许多非开发人员正在接触**Cloud Code**，他们非常喜欢它，他们非常高效，哦，这可能是一个来自一家大型上市公司的人，我不会点名他们，但其中一位业务开发人员创建了一个很棒的工具，我想是用来查看销售代理和所有这些的，然后意外地让全世界都能使用它，他们及时发现了。但现在有很多人都是这样。所以，我想**Sentry**的**David Kramer**说：“是的，我们有这种年度培训，开发人员会去参加，他们觉得有点无聊，但我们需要让它更具互动性和吸引力，而且业务中的每个人都必须参加。”所以，这将是一个有趣的挑战。所以现在听起来，现在是从事安全工作的好时机。

<details>
<summary>Original English</summary>

**Nicole**: That is my job. Um, it depends. It is always it depends. Uh, we can all go into consulting now and just make a ton of money like the check. Um, it it really does though. It depends on what question it is you're trying to ask, right? So, when someone says, "Am I being more productive?" Then I will say, "What do you mean by productive?" I know it when I see it. What what shape does it take? Right? like code smells have a thing, productivity smells have a thing, right? And sometimes it's lines of code or like PRs or something. And I'm like, okay, so what does that what do you learn from that, right? Does that help you get a feature out to a customer faster? And sometimes they're like, well, yeah. And I'm like, okay, is it the right feature? Do we know it's the right feature? And and what kind of part of that endto-end process are we amplifying? do you also want more ideas and more lines of code and more reviews and more more all everything and they're like well no I'm like I I'm just asking questions right and so I think that that can help now what are we using to measure productivity now I will say it's evolving right so uh space framework ends up being really helpful so space is satisfaction uh how satisfied you are with the thing uh performance right what's an outcome whether it's quality or something. Uh activity is account that's the anything you can count. Uh C is collaboration and communication which can be between people which we're seeing evolving. Um or between systems. Uh and then E is efficiency and flow. So that can be like if we're in a flow or it can be the time just the time it takes to get through the system, right? And I know I've heard a couple of people say here that, you know, everyone's talking about velocity and they want things to be faster and they care about velocity. And I'm like, I hear you. Yes, that can be good. What are the guardrails that you want to put in place? Right? How do we want to think about quality? How do we want to think about satisfaction? How do we want to think about whatever? Because if we just brute force it, something's going to break, right? and and there are ways where we can make informed decisions. So I've worked with teams who I will say there uh there was a question in one of the other sessions about sacrificing quality for speed. Some teams can and but when they do it they're doing it very very intentionally. They don't say they're sacrificing quality. They say they're making a riskbased decision. What this is fair though they're running a rapid experiment. They want signal really really quickly and if they can get an experiment out in an hour and they can run it against some very small percentage then they're willing to take the risk of lower latency or a crash or something for that very small percentage and then they back it out and then they get an answer. So like I think with the right metrics in place it really helps us make those risk based decisions versus all fast or all slow. And I do still see some teams that are like all slow because they they just want to pump the brakes. I you know some some folks in like security which is understandable but it's like now they're kind of on fire right their feet are on fire because there's just so much to do. Oh yeah, especially when the rest of the visits out. We we talked about yesterday we had a small event and we talked about how David Kramer from Sentry was talking about how a lot of non-developers are getting access to cloud code and they're loving it and they're so productive and oh this might have been actually someone from a larger publicly traded company which is I I won't name them but one of the business developers like created this like awesome tool to I think look at sales proxies and all that and then accidentally made it available to the whole world and they caught it in time but now now there's a lot of those folks so and and I think David Kramer from Centry was saying like, "Yeah, like we we have this like annual training where developers go and they go kind of a yawn, but we will need to make this a lot more interactive and engaging and everyone in the business will have to go." So like there's going to be this fun challenge. So now sounds like it's a good time to be in security.

</details>

**Host**: 的确如此。

<details>
<summary>Original English</summary>

**Host**: It really is.

</details>

**Nicole**: 嗯，因为现在安全也有了不断演变的定义，对吧？有些东西有点安全，有点不安全，但我们正在寻找什么信号？哪些安全级别很重要？甚至有一些很好的问题是关于，你知道，根据某些国家的法规，代码在部署之前必须至少由两人审查。这意味着什么，对吧？现在我们能否重新审视其中的一些规定？在过去十年或二十年中，有一些改进，如果通过了一系列自动化检查和测试，那么就可以算作一个人，对吧？现在是两个人。那么，现在有了**agent**会发生什么呢？对吧？所以我认为其中一些对我们来说很重要，我们要去发现并思考真正有创意的方法来解决问题，以一种有意义的、一致的方式，并且还要教育不仅是行业，还有监管领域。

<details>
<summary>Original English</summary>

**Nicole**: Well, and because now there's also kind of evolving I don't say evolving definitions of security, right? Like something's kind of secure kind of not, but what are the signals that we're looking for? What are the levels of security that are important? There are even some good questions around, you know, with some of the regulations in certain countries, you had to have at least two people review the code before it can deploy. What does that mean, right? Are there ways that we can revisit some of that now? And there were some improvements made over the last changes, improvements um over the last decade or two so that if you passed a set of automated checks and tests, then that would count as one person, right? Well, now it's two. Well, what if what happens when we have agents now, right? And so I think some of this will be important for us to kind of discover and think about really creative ways to solve the problem in ways that are meaningfully consistent and also educate the rest of not just the industry but regulatory fields right

</details>

**Host**: 今天，如果你是一名工程副总裁，坐在这个小组里，你正在推广所有这些**AI agent**，无论是来自**Cloud Code**，还是**CodeX**，抑或是其他供应商。我们提到了衡量事物的重要性。你有什么建议吗？你现在可以在战术层面衡量哪些具体且可能无害，甚至可能有所帮助的事情？你如何确保你拥有正确的数据？你正在考虑如何不侵犯开发者隐私，也不收集垃圾数据？

<details>
<summary>Original English</summary>

**Host**: today if you're a VP engineering sitting in this this group and you are in the process of rolling out all these AI agent from cloud code it might be codeex it might be other vendors we we mentioned the importance of measuring measuring things. What would your suggestion be? Specific things that you can and probably it's not harmful. It's probably helpful to measure already at a tactical level. And how would you come ac you have the right data? You're you're not you're thinking about like not necessarily invading too much of developer privacy and not collecting junk data.

</details>

**Nicole**: 这取决于情况。嗯，很多时候，我倾向于从**采用率**开始。我不喜欢采用率这个指标。我不是它的粉丝。但开发人员也是一群光荣而脾气古怪的人。我们不会使用糟糕的工具，除非我们别无选择。几乎没有其他选择时才会使用。我说这个可能会显得老套，但有一次一家公司告诉我，“哦，他们必须使用那个**CI/CD系统**。”我说：“20块钱。他们只是在启动**Jenkins**。”他们是对的。所以，我认为采用率可以给我们一些早期信号，部分原因在于满意度。因为如果一个工具很糟糕，他们就不会使用它。如果我们不与工具互动，那么我们就无法理解，对吧？就像我们不知道它的功能是什么。我们不知道如何发挥它的作用。你知道，我们可能立刻爱上它，觉得它很棒，然后后来才发现它的弱点是什么。我们可能会讨厌它，再也不回头。但我认为这会有帮助。**参与度**是另一个指标，即人们使用它的频率以及用于什么类型的任务。有一些工具——我知道早期的研究发现，对于相当直接的工作，它经常被使用，对吧？所以我们也可以观察人们如何使用它。现在我要回到“这取决于情况”，对吧？作为一名假想的副总裁，你的目标是什么？你希望人们使用它吗？你希望他们更快吗？因为每个人都谈论更快，对吧？那么你所说的更快是什么意思？是内循环编码部分吗？是端到端的功能吗？因为那样你就需要更全面地看待整个系统。嗯，特别是如果我们谈论一些神奇的、**agentic**的未来，它们都是自动驾驶的。但那是另一个**metrics**的抱怨了。除了衡量之外，我听到的一个有趣的方法是给予明确的许可。**Atlassian**的**CCO Rajiv Rojan**，他将是我们下一位演讲者。他发送了一条消息，告诉所有人：“你们有我明确的许可，可以用10%的时间试验这些系统，看看它们是如何运作的。”你如何看待这种方法？它感觉有点自上而下，但我想它也创造了一个更安全的空间。你认为这对于新技术，或者特别是现在，普遍有用吗？

<details>
<summary>Original English</summary>

**Nicole**: It depends. Um a lot of it kind of so I I will say I tend to start with adoption. I am not a fan of an adoption metric. I don't like it. But also devs are like a gloriously cranky bunch. We are not going to use tools that are awful unless we absolutely like if it's the only option. There's almost no other option. I'm going to sound old when I say this, but like I one time had a company tell me, oh well they have to use that CI/CD system. I'm like 20 bucks. They're just spinning up Jenkins. And they were right. And so I think adoption can give us some early signals in part to satisfaction because if a tool is awful then they won't use it. And if we aren't engaging with a tool so then we can look at engagement. If we're not engaging with it then we can't understand right like we don't know what the capabilities are. We don't know what like how to kick the sides. Um you know we might love it immediately and decide it's amazing and then later find out it's what its weaknesses are. We might hate it and never go back. But I think that can help. Engagement is another one which is how much are people using it and for what kind of tasks and so there's some tooling that uh and I know earlier studies found that you know for fairly straightforward work it gets used quite often right and so we can also watch how people are kind of using that now I'll come back to it depends right what is it that you're going for as a hypothetical VP of right do you want people using it do you want them to get faster because everyone talks about faster right and then what do you mean by faster is it the interloop coding part is it features end to end because then you have to take a much more holistic look at the whole system. Um especially if we're talking about some like magical agentic future where they're all self-driving. But that's that's another metrics rant. And outside of just measuring, one thing that I heard is an interesting approach is giving explicit permission. Uh Rajiv Rojan Atlashian CCO who will be our our speaker in the next one. He at last and he sends a message telling to everyone for 10% of your time you have my explicit permission to experiment with these systems and just see how they work. How do you see these kind of approaches which feels a little bit top down but it also I guess creates a bit more safe space. Do you see this being useful in general for new technology or especially right now?

</details>

**Nicole**: 我认为这在总体上很重要，对吧？它基本上就像沟通和**变革管理**。这就像非常老派的东西。但我认为现在它尤其重要，因为使用**AI**工具存在如此多的恐惧、风险和未知。我会因为使用它们而被解雇吗？如果我因为使用它们而出错怎么办？所以，嗯，我看到至少有几家公司，明确的**高管赞助**在不仅仅是使用它们，而且尝试新事物并在一定**护栏**内感到安全地失败方面产生了巨大影响。我知道，你知道，多年来一直有一些地方，如果你搞垮了整个系统，你会得到某种奖励。在不将其推向极端的情况下，这也会有所帮助，因为它们正在帮助**压力测试**我们现在工作的系统。

<details>
<summary>Original English</summary>

**Nicole**: It's I think it's important in general right it's basically like comms and change management. It's like the really old school stuff. I think it's especially important now though because there's so much fear and risk and unknown around using AI tools. Will I be fired for using them? What if I make a mistake by using them? And so, um, I'm seeing across at least a handful of companies that explicit exec sponsorship makes a huge difference in not just using them, but trying new things and feeling safe to fail within, you know, kind of guard rails. And I know, you know, for years there have been places where like if you take down all abroad, you get some kind of prize. Without taking that to its extreme, that can also be helpful because they're helping pressure test the systems that we work in right now.

</details>

### 自我支持：应对变革时代的挑战

**Host**: 在你的书里，这本书是关于消除摩擦，关于如何更好地、更快地行动等等。在书的结尾，有一整章是关于**自我支持**的，这一章叫做“通过挑战性工作支持你自己”。你能告诉我们你为什么要专门写这部分内容，以及对于大家如何支持自己，你有什么建议？你如何看待你自己的自我支持，或者你如何看待同伴们度过这个非常紧张的时期？

<details>
<summary>Original English</summary>

**Host**: In your book, which is about again removing friction, h having ways to like move better, faster, etc. in the in towards the end there's a whole chapter on um on self-support on the chapter is called support yourself through challenging work can you talk us tell us about why you wrote a whole section on it and just advice on how folks can support themselves how you see either your supporting yourself or how you see peers getting through this like pretty intense time.

</details>

**Nicole**: 是的。所以最后一节的背景是，嗯，支持组织度过变革，支持你的团队度过变革，以及支持你自己。这很有趣，因为当我采访一些工程领导者时，我们谈到了这些以及更多，其中不止几位说，对他们来说，不仅仅是支持他们的团队，你知道，为使用新工具和系统提供高管的正式支持，而且还要支持他们自己，这非常重要。因为任何时候你经历任何形式的变革，无论是你，你知道，启动一个新的**DevX**倡议，还是你正在推广**AI**，尤其是在现在一切都如此——那里有很多未知。这些都是非常困难的问题，对吧？所以有几个人可以交谈，你自己的——我想说**Rose Whitley**说过，你应该有你自己的**董事会**（board of directors），因为这样我们就可以向人们征求意见。我们可以安全地说，发生了什么。我必须去参加一个高管评审，我需要有一个意见，而且我只理解其中一半，你能和我一起讨论一下吗？我认为这也有助于避免**倦怠**，对吧？因为我们知道，**Christine Maslac**做了一些非常出色的工作，其中，嗯，倦怠是多种因素的结合，它工作过度，对吧？但这实际上并不是倦怠，那只是感到疲惫。另一个对倦怠至关重要的部分是你的价值观不一致。所以有时我发现，与人交谈，以及其他人告诉我同样的，是了解你的价值观在哪里，你的价值观是否一致，然后如果不一致怎么办。很多时候他们发现他们的价值观确实一致，这在某种程度上减轻了他们所承受的一些压力。

<details>
<summary>Original English</summary>

**Nicole**: Yeah. So the context of that last section was uh supporting organizations through change, supporting your teams through change and supporting yourself. And it was interesting because when I had been I interviewed like a handful of many several handfuls of engineering leaders as we were talking about some of this and more than a few of them said it was really important for them to not just support their teams you know provide executive formal support for using new tools and systems but also themselves because anytime you're going through any kind of change whether you're you know kicking off a brand new DevX initiative or you're rolling out AI especially now when everything is so there's a lot that's unknown there. These are really hard problems, right? And so having a couple folks that you can talk to, your own uh I want to say Rose Whitley said uh you should have your own board of directors because then we can bounce ideas past people. We can safely say what is happening. I have to go I have to go to an exec review and I need to have an opinion and like I understand half of this like can you talk this this through with me and I think that also helps with burnout right because burnout we know you know Christine Maslac has done some some really great work where um burnout is a combination of things it's working too hard right but that actually isn't burnout that's just like getting tired another piece that's super critical to burnout is not having your values aligned And so sometimes I have found that talking through people and others who told me the same is kind of understanding where your values are, if your values align and then if they don't. And many times they found that they did align and it sort of like relieved some of that pressure that they were under.

</details>

### 无摩擦组织的未来与行动建议

**Host**: 最后，展望未来，在两到三年后，你如何设想一个或多或少无摩擦的组织运作？一家真正认真对待此事的公司，他们正在采用**AI**工具，他们会说：“好吧，让我们消除摩擦点。”那会是什么样子？如果你今天坐在这个房间里，你想离开并本周就开始做一些事情，你会从哪里开始，当然除了获取并阅读这本书之外？

<details>
<summary>Original English</summary>

**Host**: And finally looking ahead um in two to three years time how would you envision a more or less frictionless organization operating a company where like takes this really seriously? they are adopting AI tools. They're like, "All right, let's remove the friction points." How how would that look like? And if you're sitting in this room today and you're you want to walk away and you want to start doing something this week, where would you start on top of course getting the book and reading it?

</details>

**Nicole**: 嗯，练习册也可以免费在线获取。你可以去找找。嗯，所以对于这种**无摩擦的未来**，有几件事。我是一个**指标**（metrics）人，所以我的答案会是关于数据的。嗯，但我认为，你知道，我几个月来一直在与人们交流，如果我们认为存在这样一个未来的世界，**agent**可以**自动驾驶**（self-drive）和**自我改进**（self-improve），它们可以做所有的事情，我们的组织运行得更好。要实现这一点，对吧？所以，那将是真的。也许是，也许不是，但这有点牵强。要实现这一点，**agent**需要能够看到和理解系统，**agent**需要能够改进需要修复的地方。要实现这一点，人类需要能够看到和理解系统，然后采取行动来修复它。嗯，要实现这一点，我们必须看到系统，对吧？特别是在我们快速行动的时候。现在，人类是一个**权宜之计**（stop gap），对吧？我们会和人交谈，我们理解系统。我只是知道，当这里有问题时，通常是关于构建，对吧？**Agent**无法做到这一点。或者如果它们能做到，我们可能也不希望那样。所以我们如何思考方法，以简单廉价的方式呈现一些信号，帮助我们做出决策？它不必是超级重量级的。虽然**agent**可能也可以帮助我们构建一些相当不错的**工具化**（instrumentation），对吧？所以我们如何思考方法，首先识别我们关心的**触点**（touch points）是什么？我们想要看到什么**信号**（signals）？我们如何让获取这些信号变得廉价和容易？然后我们如何围绕它们进行**意义建构**（sense make），并意识到这将会改变，对吧？就像编写软件有几个阶段。有想法并提出设计，然后编码。现在整个前端都变得有点模糊了，因为很多时候我们都可以非常快速地**原型化**（prototype），并固化我们在想法和编码方面的一些思考。所以我完全期望外部循环也会崩溃，对吧？因为我们会找到更有效的方法来做到这一点。但如果在此期间，我们知道一些**触点**在哪里，那将会很有帮助，对吧？比如我们在寻找什么？**质量门**（quality gates）是什么？哪些信号表明事物运作良好或不佳？然后如果我们崩溃了，这些信号会转移到哪里，或者它们会消失吗？

<details>
<summary>Original English</summary>

**Nicole**: Uh workbooks are also free online. You can go find those. Um so a couple of things for the kind of frictionless future. I'm I'm a metrics person, so my answer is going to be about data. Um, but I think, you know, I've I've been having conversations with folks for a handful of months now around if we think there's this future world where agents can self-drive and self-improve and they can do all the things and our organizations run better. For that to be true, right? So, that's going to be true. Maybe, maybe not, but it's a stretch. For that to be true, agents need to be able to see and understand the system and agents need to be able to improve the things that need fixed. For that to be true, humans need to be able to see and understand the system and then take action to fix it. Uh and for that to be true, we got to see the system, right? Particularly when when we're moving really really quickly. Right now, humans are a stop gap, right? We'll talk to people, we understand the system. I I just know that when there's a problem over here, it's like usually about the build, right? Agents aren't going to be able to do that. Or if they are, like we probably don't want that. And so how can we think about ways to easily and cheaply surface some of the signals that can help us make decisions? And it doesn't have to be super heavyweight. Although like agents can also probably help us build some instrumentation that's pretty good, right? So how can we how can we think about ways to first of all identify what are the touch points that we care about? Where are the signals that we want to see? How can we make it cheap and easy to get a hold of those? And then how can we kind of sense make around them and and realize that's going to change, right? Like there's several phases in like writing software. There's like having the idea and coming up with the design and then coding it. And then right now that whole front end's been like kind of smooshed because many times we can just like prototype really really rapidly and kind of solidify some of what we're thinking in terms of like ideas and coding. So I fully expect that part of the outer loop is just going to be collapsed as well, right? Because we'll find more efficient ways to do that. But it's going to be helpful if in the interim we know where some of those touch points are, right? Like what are we looking for? What are the quality gates? What are the signals that show us something is working well or not? And then if we collapse then where do those signals shift to or do they get to disappear?

</details>

**Host**: 是的。我觉得随着如此多的变化到来，对我来说非常重要的一点，书中也提到了，我们刚才也谈到了，那就是拥有一个**个人董事会**（personal board of directors），寻找理想情况下在不同公司工作的同行。你可能会在这里遇到一些人。你可能已经认识他们了。联系他们。听起来现在是一个每个人都乐意聚在一起喝咖啡的时候。创建一个**WhatsApp群**或者一个群组消息群，里面有几个人，你们可以交流：“我正在做这个。我看到了这个。我正在做这个。我看到了这个。”因为似乎唯一确定的事情就是它会改变，并且什么对你有效取决于具体情况。所以如果你找到志同道合的人，在相似的行业中，那么“这取决于情况”可能会更相似，对你们很多人来说，对吧？

<details>
<summary>Original English</summary>

**Host**: Yeah. And it feels to me that with so much change coming, one thing that feels really important to me that again it was in the book and we just talked about is having this personal board of directors, finding peers who ideally work at different companies. You might meet some people here. You might already know them. Reach out to them. And it sounds like it's a time where everyone will be happy to get together to have coffee. Create a WhatsApp group or or just just a group messaging group with a few of you and you talk. I'm doing this. I'm seeing this. I'm doing this. I'm seeing this because it seems like the only certain thing is it will change and it will depend what works for you. So if you get like-minded people in similar industries, the it depends will probably more similar to a lot of you, right?

</details>

**Nicole**: 是的。嗯，我发现那对我来说是最有帮助和最有益的，你知道，我能否向某人征求意见？我解释的方式是否有道理？嗯，我看到的事情和你看到的事情相似吗？如果是，那可能意味着什么？如果不是，那真的是不同吗？还是我们只是用了不同的词？对吧？所以我想，特别是在这样一个变革时期，但尤其是这种快速变革时期，这非常有帮助。而且我只是保留着，我有一个**后方通道**（back channel），对吧？所以有时是和某人交谈，有时只是向你认识和尊重并感到安全的几个人在**后方通道**里提问。
<details>
<summary>Original English</summary>

**Nicole**: Yeah. Um, and I found that to be some of the most helpful and the most beneficial for me is, you know, can I bounce an idea off someone? Is the way I'm explaining it making sense? Uh, are the things that I'm seeing similar to the things that you're saying? And if yes, what could that mean? And if no, is it actually different? Or are we just using different words? Right? And so that I think especially when we're in a time of change at all, but especially this rapid, it's super super helpful. And I also just keep I've got like the back channel, right? So sometimes it's talking to someone and sometimes it's just like popping a question at a back channel with a handful of folks that you know and respect and you feel safe with.

</details>