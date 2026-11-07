---
author: AI Engineer
date: '2026-08-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=qqrk7CtkuIw
speaker: AI Engineer
tags:
  - ai-assisted-engineering
  - product-development
  - team-structure
  - software-development
title: 迈克·克里格谈 Anthropic 的 AI 研发秘密与团队方法论
summary: Instagram 联合创始人、Anthropic 技术成员迈克·克里格分享了他从首席产品官（CPO）转型为独立贡献者（IC）的经历。他深入探讨了 Anthropic 内部如何利用 Claude Code、Slack 标签和 Artifacts 实现“人机协同多人协作”，并阐述了“小赌注”敏捷管理机制（Persevere or Pivot）以及在高强度 AI 竞争中保持心理健康的独特见解。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - Instagram
products_models:
  - Claude Code
  - Claude Artifacts
  - Claude Design
media_books:
  - The Hard Thing About Hard Things
status: evergreen
---
### 欢迎新成员加入

**主持人**: 今天加入我们舞台的是 **Instagram** 的联合创始人，同时也是 **Anthropic** 技术团队的成员——**迈克·克里格（Mike Krieger）**。

<details>
<summary>Original English</summary>

**Host**: Joining us on stage is the co-founder of Instagram and a member of technical staff at Anthropic, Mike Krieger.

</details>

**迈克·克里格**: 大家好吗？我是说，大家早上好。非常高兴能来到这里。

<details>
<summary>Original English</summary>

**Mike Krieger**: How's everybody doing? I mean, good morning. Nice. Um.

</details>

**主持人**: 麦克，非常感谢你们刚好及时为我们发布了新产品，这配合简直完美。

<details>
<summary>Original English</summary>

**Host**: Mike, thank you for releasing Fable just in time for us.

</details>

**迈克·克里格**: 没错，就是为了这次大会。我们特意计算好了时间。

<details>
<summary>Original English</summary>

**Mike Krieger**: Exactly for the conference. We timed it.

</details>

**主持人**: （笑）我们真的太高兴能邀请到你了。你不仅是最杰出的系统构建者之一，还在 Anthropic 带领着前沿的实验室工作。随着模型在内部的成长，你自己使用模型的方式发生了怎样的变化？

<details>
<summary>Original English</summary>

**Host**: [laughter] Um we're we're so glad to have you. Uh you're uh one of the preeminent builders and you're a leading labs at Anthropic. Um how has your model usage changed as as you've, you know, seen models internally grow?

</details>

### 从管理者到IC

**迈克·克里格**: 是的，对我来说，这不仅是模型的转变，也是我自己角色的转变。在我加入 Anthropic 的前两年里，我担任的是**首席产品官（CPO）**。在那个岗位上，我总是看到大家在用模型构建各种酷炫的东西，我的“错失恐惧症”（FOMO）就一天比一天严重，因为我虽然也在尽一切可能频繁地使用模型，但场景不一样。比如在制定产品策略时，我会写一份策略文档，然后让 **Claude** 对它进行批判性评估。这虽然也是一种工作流，但它跟那种纯粹的、动手编写代码的构建方式完全不是一回事。

我当时把所有的周末时间都花在尝试用模型写代码上，最后我意识到：“好吧，我其实只需要彻底转变我的角色。现在的时代太有趣了，不能只当个旁观者。” 实际上，我现在看到了一个很有意思的趋势，好几个在其他地方担任首席技术官（CTO）的人，现在也纷纷加入 Anthropic 或其他地方做**独立贡献者（IC）**。

就在我做出角色转变的时候，恰好也是我们开始在内部拿到那些后来演变成 Mythos 和 Fable 的模型快照的时期。观察这种转变非常有趣：以前我的模式是“我有一个想法，然后我要在脑海里像往常做工程设计那样把步骤拆解得很细，再一步步迭代去实现”；而现在，它变得更像是一种全新的范式——“我只需要描述最终的目标，让模型自己去摸索和处理，然后我们一路上针对它抛出的一些权衡和问题进行交流，最终看它产出的结果，再从那个基础继续往前推进”。

我发现这挺难的。我不知道大家有没有这种体验：有时候模型明显比我聪明得多。所以有时它完成工作后说：“这是我做出的折中方案。” 我就会跟它说：“你能像解释给一个比你笨一点的人听那样，给我解释一遍吗？因为我需要你帮我把这部分逻辑拆解开来。” 但这确实是一个巨大的改变，也就是从具体的任务指派，转变为直接表达最终的状态，然后让模型去“烹饪”和实现它。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah, I mean, for me it's been like both the model shift and then my role shift. So, I for like the first 2 years I was at Anthropic, I was chief product officer. And then I kept seeing people build with the models and the FOMO just kept increasing because I was you know, use the models as much as possible. But for example, on product strategy I would write a strategy doc and then have Claude critique it and maybe you can use a workflow, but it's not quite the same as like building in that pure way. And I was like spending all my weekends trying to build with it and I realized, "Okay, I actually just need to shift. It's like way too interesting a time." And it's actually an interesting trend I've seen now like several people that were CTOs at other places are like now joining as ICs at Anthropic and other places. But I made a role shift and it was actually right around the time where we started getting sort of internal snapshots of what became Mythos and Fable. And what was really interesting watching that sort of shift was um that kind of change between I have an idea, I'm going to like sort of break it down in my head much more how I would do engineering normally, and then kind of iterate through these different steps to moving to much more of the paradigm of I'm going to describe the goal, like go off and work on it, and then like we can talk about what trade-offs you you know, surface some questions along the way, but then figure out what where you landed and where we can go from there. I find it's hard. I don't know if people have this experience where people's only been re-enabled for a couple of days. People's definitely way way smarter than me. So, sometimes it'll finish work and be like, here's the trade-offs I made. I'm like, can you explain it to me like I'm a little dumber than you are because I need you to like sort of break this down for me. But, that's been one sort of big change is sort of moving from that task delegation to like express the end state and then have it go and and cook on it.

</details>

### 用不合理的方式提问

**主持人**: 是的，我们都在学习如何更好地进行授权和委托。塔里克（Tariq）昨天帮了我们大忙。你会在报纸上读到相关的报道吗？你知道的，我们现在在第二天的报纸上就会有关于这些讲座的报道。

<details>
<summary>Original English</summary>

**Host**: Yeah, we're all learning how to delegate better. Tariq did us a huge favor yesterday. We Did you want to read it in the newspaper? You know, that we have we have write-ups of talks now in in like the next day's newspaper.

</details>

**迈克·克里格**: 他说，要提出“不合理”的要求。

<details>
<summary>Original English</summary>

**Mike Krieger**: He said, be unreasonable.

</details>

**主持人**: 在哪些方面你变得更加野心勃勃了？我是说你给模型写的提示词。

<details>
<summary>Original English</summary>

**Host**: In what ways you know, you know, have you been more ambitious? Yeah, you're prompting.

</details>

**迈克·克里格**: 我很喜欢这个提法，这种框架非常棒。今天我就刚好遇到了这样的事情。作为实验室的项目之一，我负责内部产品的开发。今天有人来跟我说：“嘿，这个功能的运行方式不是我想要的，你能不能做些修改？” 我突然意识到：“哦，我直接去让 Claude 来改就好了。你为什么不直接问 Claude 呢？” 而提问的这个人实际上是一个非技术人员。

所以我认为，作为整个行业，甚至是作为一个产品团队，我们必须教会人们在使用模型时表现得更加“不合理”。这在以前是很难想象的。如果我可以稍微偏离一下主题，谈谈产品设计的话：我觉得目前第一代的 AI 产品，我们把它们限制得太死了，放在了一个太小的盒子里。限制了它们对工具的访问权限，限制了它们的自由度，这意味着用户在以前很难提出什么“不合理”的要求。比如你让它“帮我做这件事”，它会很为难地回答：“我做不到。我顶多能帮你写写代码，但我没法真正运行它；我虽然可以审视我所处的环境，但也仅仅是一点点而已。”

但如果你看看我们自己的产品演进，比如 **Claude Code** 这样的项目，它会让你思考：是不是每一个知识工作者都需要一个能够编写 Bash 命令的虚拟机？从表面上看，似乎不需要；但是当你意识到——比如昨天我就碰到了这个问题——我试图用我们内置的 PDF 解析器去解析一个 PDF，但失败了。如果模型有这个能力，它就会说：“啊，我没法用这种方式解析它。不过没关系，我大概可以自己写个脚本来搞定这件事。”

不过，我做过的最“不合理”的事情，是把我用 Python 写的一个实验室项目做迁移。Python 是我最热爱、最亲近的语言，整个 Instagram 的后端以前都是用 Python 写的。虽然听说他们现在因为有了更好的 LLM 翻译模型，终于开始把它转换成 PHP 了，我知道，这都是为了 Token 成本。（笑）

当时对于部署，我意识到 Claude Code 已经结合 **Bun** 摸索出了一套更好的部署方案。于是我说：“好吧，我需要把这整个项目从 Python 移植到 TypeScript。” 如果我戴上 2010 年代甚至 2020 年代初的工程师帽子，这绝对是一个极度愚蠢的想法。谁会在那个时候把一个几十万行代码的库进行重构移植啊？

但我当时觉得，现在这已经是可以实现的了。我建立了一个动态的工作流配置，然后在周末让模型去执行整个迁移工作，让它去验证、双重检查，然后对比两边的代码，像这样不断地循环往复、反复打磨。等周一我回来的时候，展现在我面前的就是一个已经完全移植到 TypeScript 并且完全可运行的工作流。这绝对算得上是我做过的比较“不合理”的事情之一了。直接对模型说：“来，把这个完整的 Python 代码库移植到 TypeScript，让它跑起来，并且在周末结束前达到可以部署的状态。”

<details>
<summary>Original English</summary>

**Mike Krieger**: I love that I I mean, I love that framing. We actually just hit this today. I'm one of the labs initiatives I have is internal product, and somebody was like, hey, it doesn't work the way I want it to, and can you make some changes? And I realized, oh, I'm just going to go ask Claude to do this. Like, why don't you ask Claude? And this was a non-technical person. So, I actually think as an industry or even as a product team, we have to teach people to be more unreasonable in their usage, and it's sort of hard to imagine. I think that that if I can digress for a second on product design, I think right now the like kind of first generation of AI products, we put them too much in a box and constrain their their sort of access to tools or kind of degrees of freedom, which means it was much harder to be unreasonable, right? When you say, do this thing for me, and then it would be like, well, I can't. I can barely like I can write code, but I can't really run it, or I can kind of introspect my environment, but not really. Um and I think as you see our own like product progression even with things like co-work where like, you know, does every single like knowledge worker need a virtual machine that can write bash? Like, on the face of it, no, but then when you realize, oh, actually, that way it can remediate an issue where, oh, I tried to parse a PDF using our built-in PDF parser. I hit this yesterday and it was like, ah, I can't parse it this way. Well, okay, well, I can probably write a script that can do this as well. Um so, I think that's it. My most unreasonable thing though was uh one of our labs projects I wrote in Python like near and dear to my heart. All of Instagram was in Python. But I think they're finally converting it to PHP now that they have um like models that can do it. I know. [laughter] Tokens. Um and uh for deployment I realized that Cloud Code had like figured out a better deployment story with Bun. And I was like, okay, I need to port this whole thing from Python to TypeScript. Like, as a, you know, if I put on my like 2010s engineering hat or even my early 20 20s, like, that's a dumb idea. Like, who would ever port like, at that point, you know, a couple hundred thousands of lines of code. Um but I was like, I think this is doable now and I basically created this dynamic workflow setup and over the weekend had it port the whole thing, like, verify it, double-check it, then read both code like this basically churn and churn and churn and then came back Monday to a completed workflow that was a ported version of that thing. So, that probably ranks on like the more unreasonable things. Like, yeah, just port this entire Python code base to TypeScript, get it working, get it deployable in, you know, a weekend.

</details>

### 利用生产数据辅助跨语言编译

**主持人**: 是的，很多人的确都在讨论那个把 Bun 从 Zig 语言移植到 Rust 语言的版本。对于编译器或运行时来说，它有大量的测试，所以大家觉得移植起来相对简单。但是如果像你刚才提到的那样，把像 Instagram 这样包含复杂产品逻辑的系统移植到 PHP 呢？这涉及到很多具体的产品业务边界。

<details>
<summary>Original English</summary>

**Host**: Yeah, I mean, a lot of people are talking about the the Bun Zig to Rust version. I think a lot of people are also like, well, it's a compiler, it's a it's a runtime, it's got lots of tests, easy to do. Can you port Instagram, which you would know very well, to PHP like that? Like a like a product.

</details>

**迈克·克里格**: 确实，产品端的移植可能更难，也可能更简单，这取决于你怎么看。我们在 Instagram 做过的一件事，是在 Python 3 刚发布的时候。那时我们第一次能够引入类型提示（Type Hints），当时内部有很多讨论：“我们会在 Python 这条路上走到尽头、失去动力吗？” 我的观点一直是，我觉得我们能走得比想象中远得多，但类型系统能帮我们理清思路，不至于自己绊倒自己。

所以我们构建了一个叫 **MonkeyType** 的工具，它核心做的事情就是捕获生产环境中的运行时的真实类型数据，然后再把这些真实的运行时类型映射回我们的代码库中。我觉得这种模式在当前利用 LLM 进行代码转换或交叉编译时非常值得借鉴——你可以极大地依赖真实的生产环境数据，或者运行分段测试（Segmented Tests）。在这些方面有很多非常有意思的尝试。

但不管怎么说，天空才是唯一的极限。我觉得这里面最难的部分，始终是找到一个清晰的边界，让你能够以渐进的方式（Incrementally）去推进，而不是试图在一夜之间“把整个海洋煮沸”，一步到位地把所有东西都换掉。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah, I mean, I think the product side of it it's even I don't know if it's easier or harder. One of the things we did at Instagram, this is when Python 3 came out and we were able to add type hints for the first time and it was people had a lot of internal conversations like, are we going to run out of steam on Python? And my perspective was always like, I think we can take this way further than we think we can, uh, but I think types are going to help us not sort of be in our own way. And we built this thing called Monkey Type where we basically like captured runtime type like basically the types that were actually getting used in production and then map those back to to the types in the code base. And I think because of that sort of pattern, I think there's really interesting ways in which if you're doing sort of conversion or sort of cross compiling using LLMs, you can also lean on production data a lot more or run sort of like segmented tests. I think that like there's a lot of, uh, things you can do there. But yeah, I think it's, I mean, the sky's the limit there as well. I think the hardest part is always finding the boundary around where you can start doing it incrementally without trying to boil the whole ocean and like swap it overnight.

</details>

### 灰度发布与配置开关

**主持人**: 没错，用户最终是你的测试者。我也在报纸上读到过另一篇文章，讲的是你如何直接利用功能发布灰度控制（Rollouts），有时候你可能并不确切知道自己会为了什么去使用它，但一旦这些灰度发布和实验的基础设施搭建好了，它就能释放出巨大的能量。

<details>
<summary>Original English</summary>

**Host**: Yeah, I mean, your users are your test ultimately and, um, you know, I we I also read another article in the newspaper about how you could just use rollouts and sometimes you don't really know, uh, what you're going to need it for, but when that infrastructure exists for your experiments and to roll things out, it's enabled so much.

</details>

**迈克·克里格**: 对，这是我们很早就得到的一个忠告。我们刚推出 Instagram 的第一周，后台的一切几乎都融化、崩溃了，因为我们当时根本不知道怎么做后端扩展。碰巧在那一周，我们的一位投资人为我们安排了一个午餐会——甚至都不是专门为我们准备的，而是一个基础架构主题的午餐。结果我们完全“霸占”了那场对话，因为在场的每个人都对我们如何解决扩展性问题有着自己的看法。

在那里我得到了两条终生难忘的建议。第一条是：**对你觉得可能会用到的所有指标进行预先测量（Pre-measure）**。因为在遇到宕机故障时，最糟糕的事情莫过于看着一个数字，却不知道这个数字到底是处于正常水平还是异常高点，而你之所以不知道，是因为你直到刚刚才临时把这个监控指标加进去。

第二条建议是：**对控制旋钮和功能开关（Knobs & Feature Flags）保持高度的敬畏和思考**。即便是在早期的 Instagram，我们也有一套非常简单但极其有效的灰度发布和动态配置系统（Dynamic Config）。许多运行时配置必须在几秒钟内完成修改，这样我们才能应对突然暴涨的流量。这种将动态配置作为一等公民对待的做法至关重要。我们在如今的 AI 研发中也看到了同样的模式，因为我们总是在做各种不同的权衡，而拥有这种运行时配置的能力是超级关键的。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah, I mean, I always found this was advice we got. It's like we launched Instagram and the happened to be the first week everything melted cuz we didn't really know what we were doing on the back end side of things. And, uh, coincidentally that week there was like a lunch that one of our investors just scheduled like not even for us. It was just a infrastructure lunch. And we ended up spending we totally like monopolized that conversation cuz everybody had their own opinion about how we could fix our scaling. Um, and like the two pieces of advice I got there is like 2010 that I like will forever retain is like, um, like basically like pre-measure everything that you think you might even remotely need because the worst thing is an outage where you're like, well, is this like number normal or is it high? And like, oh, I don't know because I don't have data until I just added this metric. And the other one is being like really thoughtful about knobs and feature flags. So even, you know, early Instagram we had like a very, uh, simple but really effective like way in which you could do like ramp outs and rollouts. And dynamic config too where, you know, a lot of our runtime configurations had to be changed, you know, in a matter of seconds so that we could handle load and being able to like do that in a first class way was was really important. I'm seeing that definitely in in AI as well where, you know, we're making all sorts of different trade-offs and having that kind of runtime configuration is super key.

</details>

**主持人**: 顺便说一句，我最喜欢的关于 Instagram 扩容的故事是，在上线首日，你们用那封欢迎邮件对自己发起了 DDoS 攻击。

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh my my favorite scaling story of Instagram by the way, I think it's like your launch day when you you DDoS yourself with the email.

</details>

**迈克·克里格**: （笑）是的。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yes.

</details>

**主持人**: 如果有人还没听过这个故事，大家应该去搜一下。现在我想聊聊 **Slack 标签（Tags）**。这是一个非常重大的工作流转变。如今你们有 60% 以上的代码是通过这种方式编写的。

<details>
<summary>Original English</summary>

**Host**: Which I people should look up that story if uh if you haven't seen it. Um I wanted to go into tags. Uh very very major shift. Uh it's it's how 60 something percent of your code is written today.

</details>

**迈克·克里格**: 没错。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah.

</details>

**主持人**: 你如何将这种做法与你刚才说的动态性结合起来？这感觉就像是你并不是在交付一个单一的应用，而是在交付一个带着 3000 个功能开关的应用。

<details>
<summary>Original English</summary>

**Host**: Um how do you square that with everything you just said where it's like very dynamic? Like you don't actually ship one app, you ship one app with 3,000 flags.

</details>

### 用 Slack 标签重构开发模式

**迈克·克里格**: 是的。我之前和 Swix（大会组织者）聊过，我非常兴奋我们把“标签（Tags）”这种模式向外公开了，因为这是我们在 Anthropic 内部已经使用了相当长一段时间的工作方式。以前我站在演讲台上，大家总会问我：“你们在 Anthropic 内部是怎么写代码的？” 我就会说：“哦，我们用一些跟 Claude Code 不完全一样但很类似的东西。” 但那时候很难向外界描述清楚。

如果你有机会一窥 Anthropic 内部的代码编写过程，你当然会看到人们在进行高带宽的实时交互时会使用交互式的命令行工具；但实际上，绝大多数的代码编写和任务委派是通过**在 Slack 里打标签（Tagging）**来异步完成的。

这种模式之所以极其有趣，是因为它的“多人游戏”（Multiplayer）属性。它让我想起了 Midjourney 的运作方式：所有人都待在 Discord 频道里，看着别人是如何使用提示词和工具的。这极大拓宽了大家的野心。

比如当你第一次在频道里看到有人 @Claude 并写道：“嘿，不仅要修复这个 Bug，从现在开始你还要负责这整个代码库的这部分模块。我需要你监听这个反馈渠道，主动认领任务并修复它们。另外，如果这个 API 发生变化，也请同步去更新。” 当我看到别人这样做时，我直接惊呆了：“等等，我之前完全没有发挥出这个工具的潜力，我只是把它当成了一个高配版的 Slack 机器人来用。”

所以，这是一种完全崭新的开发范式。更高级的版本是，你需要把 AI 真正看作是一个能够持有上下文、拥有记忆并能够主动采取行动的**队友**。这彻底改变了我们内部的运营方式。相比于传统的个人单机 CLI 终端，它更像是一种多人、异步且主动的协同网络。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah. Yeah, I mean, I think there's a bunch of things. So, like with I was really excited. I was talking to Swix earlier like, I'm really excited that we have tag out there because it is uh how we've been working for a while and I would get up on stages and people like, "How do you work at Anthropic?" And I'd be like, "Oh, yeah, we use these things like that are not quite Claude code, but you know, uh but it's hard to describe it, but I mean, if you like got to poke into Anthropic, like you would see uh of course Claude code usage for things that are like more interactive or if you're kind of iterating on a particular uh sort of sort of specific thing where you want a lot of like a high sort of bandwidth back and forth, but most usage is actually much more delegating uh via tagging and via tag. And you can say like, "Here's the And the reason it's really interesting is how multiplayer it is." And it reminds me sort of of like um actually like Midjourney, like the fact that everyone was on Discord seeing how other people were using it. I think it actually to your earlier question really helps with that unreasonableness or ambition where the first time you see somebody tag Claude and be like, "Hey, you know, don't just fix this bug, but like now you are responsible for this part of the code base and I want you to monitor this feedback channel and proactively take on tasks and then fix them and then also take like, you know, if this API changes, do that." Like I saw somebody do that. I was like, "Oh, wait, I've I've totally underutilizing this thing. I've just been using it as like a glorified Claude code and slack. Like that's definitely a totally like sort of new version of it, right? And then more advanced version is really trying to start thinking of it as a teammate that is actually sort of holds context, has memory, and can be proactive. And that's just really changed how we operate internally. It's much more like this multiplayer async proactive way than it is a you know, most people often their own CLIs.

</details>

### 代码审查的瓶颈与意图共享

**主持人**: 那你们在代码合并和 Git 流程上会遇到代码审查（Code Review）的瓶颈吗？显然我们依然有代码审查，通常还是得有人去看一眼。在你们的想象中，会不会存在一个直接由 AI 自动合并代码的世界？

<details>
<summary>Original English</summary>

**Host**: Are you bottlenecked by code review and get? Obviously, there is code review, but someone usually still looks at it. Is there a world in which you just merge it in?

</details>

**迈克·克里格**: 问得非常深刻。我们目前在代码审查上确实依然存在瓶颈，特别是当改动涉及到核心架构的时候。但这个瓶颈比纯粹的“审查速度慢”要微妙得多。它其实是**人类对代码改动的认知能力和理解能力的瓶颈**。

这也是为什么我们几周前推出了 **Claude Artifacts** 的原因之一。以往你给同事发一个 Pull Request，对方看了一眼说：“我看不大懂，哥们，这里面有 2000 行改动，它们看起来确实是代码。” 

而我们现在更倾向于做的是分享一个 Artifact 页面，里面包含了对这 2000 行代码的解释、这次修改的根本意图、以及在不同实现方案之间做出的权衡。我认为未来的趋势是，我们通过交流“意图与权衡”来沟通，而代码本身的正确性可以通过各种自动化测试工具来验证。

当我现在收到一个 PR 时，我不敢说我逐行审查了每一行代码。我其实并不需要这么做。我会把代码塞给 Claude，问它：“这些是我的疑问和担忧，你能不能去帮我做个深入调查？” 所以，这是一种由 **Claude 驱动的代码审查**，但背后依然由人类的意图来主导。而对于那些纯视觉或样式上的修改，我们往往就采取“快速合并，如有问题后续修补”（Fix Forward）的策略了。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah, we're it's a really good question. We are definitely still bottlenecked on reviews, especially for things that are like touching some architecture pieces. And it's actually more subtle than just being bottlenecked on review, cuz that's you know, okay, we can carve out time differently. It's like bottlenecked on human ability to even like fully conceptualize what we're doing. So, one of the reasons we built Claude code artifacts that we shipped a couple weeks ago was partially for that, which is you would send somebody a PR, and then they'd be like, I don't know, man. This is like 2,000 lines of code. Like, it looks like code to me. And what we started doing instead is sharing much more like, here's a Claude code artifact. Like, here's the explanation. Here's the intention of the the change. Here's the trade-offs that were made. And like, I think that's going to be much more be the trend by which we communicate, which is the code is ultimately, you know, verifiable using some things, but actually like discussing intent and trade-offs, and then measuring in production I think that at least the direction of travel we've we've gone. And I don't review when I get a pull request, I wish I could say I reviewed every line of code. I definitely do not. I like actually talk to Claude about the the code and say, all right, like, these are the questions that I would have. Can you go investigate it? So, it is kind of Claude-powered code review, but still human-driven. And and for the really important ones. And for the ones that are like cosmetic visual changes, it's much more like look like we'll fix forward if we need to fix forward, you know.

</details>

### “小赌注”机制与敏捷项目管理

**主持人**: 完全理解。我想这大概是现场很多团队也在苦苦思索的问题。我还想聊聊 **Anthropic Labs** 本身。Nilay Patel（The Verge 总编辑）非常喜欢问一个问题：“请画出你们的组织架构图。” 很多人说，你交付的产品实际上就是你组织架构的映射。大家现在都知道 Claude Code，现在又有了 Tags。你如何去构建 Labs 这个组织？

<details>
<summary>Original English</summary>

**Host**: Yeah, totally. I think a lot of people are here are trying to figure that out, too. I wanted to talk also a little bit about Anthropic Labs in general. Nilay Patel, who you've probably met before, loves to ask ask the question like draw the org chart. Like how like people, you know, you ship your org chart. Like I think it's important like everyone knows cloud code. Now you've got tags. Um How are you structuring the labs?

</details>

**迈克·克里格**: 这是个好问题。因为我们之前一直努力克服的一个问题是，在强调敏捷开发的同时，你依然需要让员工获得管理层面的支持。我认为“工程经理（Engineering Manager）这一职能即将消亡”的说法被大大夸大了。在团队中，人际沟通、职业成长指导和个人能力发展依然是不可或缺的。

但是在 Labs 团队，我们的运作节奏是**两周一次的评审循环**。在这两周的周期里，每一个项目都面临两个选择：“坚持（Persevere）”还是“转向（Pivot）”。也就是说，如果一个原型项目在两周内没能证明自己的生命力，它就会被重组或者干直接关掉。在每一个评审周期里，我们都确实在关掉一些项目。

当你把这种淘汰机制常态化以后，大家就不会觉得“哦天呐，我的项目被砍掉了，我是个失败者”。这正是 Labs 的设计初衷：快速做原型，快速在内部发布，甚至拿到早期测试版中去验证，如果它不行，就快速体面地收尾。

但这种高频重组的节奏也带来了一个挑战：如果你把汇报线（Org Chart）和具体的项目绑定得太死，你可能每两周就得做一次公司架构调整，这会是一场灾难。

因此，我们采用了一种非常灵活的矩阵式架构。当我们在 Labs 内部确定了一个**“下注项目”（Bet）**，我们会从产品团队、工程团队等不同方向抽调人手组成一个小队（Pod）。如果这个产品是我个人特别感兴趣的，我也会亲自跳进去和大家一起写代码。在这个项目存续期间，这个小队就是基本的战斗单元。

这里有“项目负责人（Bet Lead）”或者“直接责任人（DRI）”的概念，但关键是：他们通常并不在行政汇报线上管理小队里的其他人。这打破了传统的层级观念，但它让我们在项目要被砍掉或重组时变得极其轻巧和灵活。

而工程经理（EM）的角色，则更多地回归到“确保每个人都被分配到他们最感兴趣的事情上，并以最舒服的状态去工作”。如果某个产品证明了它能跑通——比如 Claude Design，它最初只是 Labs 内部几个人的一个小实验，但当我们把它发布出去并获得了巨大的用户反响后，我们就会正式为这个项目组招聘专属的团队，它才开始固化成一个更有结构的常规团队。在 Labs 里，项目在证明自己之前，永远是流动和松散的。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah, it's a good question. Because what we were trying to wrestle with was you want sort of people to be supported like, you know, I think the death of the engineering manager discipline has been greatly exaggerated. Like I think there's still a lot of coaching and interpersonal pieces and personal development that I think is still really, really important. But especially in a labs type group where like our whole cadence is two-week reviews where every project goes up for we call it persevere or pivot. So basically every project is up for review and either it's time to, you know, keep going, persevering, or you know, it's time to pivot it or even shut down. And, you know, we've shut down projects basically every single one of those cycles and it's like the more you do it, the less it's just like, "Oh no, my project is shut down. I failed." It's like, "No, that is definitely the intention of the labs team is to prototype quickly, try to ship internally, maybe get it to early access, and if it doesn't work, wind it down." But because of that kind of like rapid iteration, it means that if you align the org chart too much to the individual projects, you're going to end up like re-orging every two weeks, which would be a total nightmare. And so we've actually ended up with this interesting setup where like the the pod or the team that is working on a given we call them bets within labs, definitely just draws upon like all right, somebody from product, somebody from the eng team, you know, I'll jump in when it's a product I'm particularly interested in. I'll come in and work together with the team on it. And that's the unit for that time. And there is the concept of a bet lead or a directly responsible individual. But the interesting thing is that they don't manage usually any of the other people, which kind of breaks the that kind of previous way in which a lot of these things were done. But I think it leaves it leaves us to be really flexible when you say, "Okay, actually this project is not going to work out. Let's disband and keep going and it's not a big deal." And the engine manager is much more playing the like make sure every individual is assigned to the thing that they're most excited about and that they're working in the best way possible. Now, what we do sort of solidify is when there's a product that has like legs. Like Cloud Design for example, started in this sort of ad hoc sort of grouped way and then now that like we've shipped it, it's gotten traction, we've done like a big second release in June. Like it's becoming like we've hired people for that specific team and it has more of a of a structure. So, it's like loose until it gets solidified down the line.

</details>

### Claude Design 与应用边界的模糊

**主持人**: Claude Design 的未来会怎样？这是你们今年最重磅的发布之一，很多人都对它接下来的走向非常感兴趣。

<details>
<summary>Original English</summary>

**Host**: What's the future of Cloud Design? I think a lot of people are very interested in It's one of your biggest launches this year. Where does this go?

</details>

**迈克·克里格**: 对我来说，制约 Claude Design 变得更强大的一个关键瓶颈，是它与我们其他交互界面的协同。比如我前几天在用 Claude Code 写东西，我希望在设计界面（Design UI）和代码编辑器（Code Editor）之间能有一个完全无缝的流转。

总的来说，这又回到了“为 Claude 解绑”的思路上。如果我们的各个交互表面（Surfaces）之间不能顺畅地对话，就会扼杀掉很多有意思的创意。这是我们目前正在重点攻坚的领域。

另一个趋势是，**原型设计（Design）和真实应用程序（App）之间的界限正变得越来越模糊**。我们看到有很多人用 Claude Design 拼装出了完全可运行的小游戏——虽然我们设计这个功能的初衷绝不是为了让人去写游戏，但它确实可以做到，因为它底层就是 HTML 和 JavaScript。

随着这种边界的进一步消融，我们开始思考：从一个看起来很精美的 UI 原型，到真正能够持久化存储数据、分享给他人使用、并基于此不断构建的生产级应用，这中间的路径该如何演进？这其中的想象空间非常大。

<details>
<summary>Original English</summary>

**Mike Krieger**: I think for me, I mean the things that are holding back Cloud Design from being even better is better interaction with our other surfaces. So, you know, I was designing something or I was talking to to Cloud Code the other day. I'm like, I want a really much more seamless like what I'm talking about the design for it, you know, and then after design back to that. I think in general it's I mean this goes back again to kind of unconstraining Cloud. Like the fact that our surfaces don't talk to each other as well as they could. I think really holds back a lot of interesting ideas around what we could do. So, I think that's one like kind of major area that we're looking at. And then the other one is people like the lines between a Cloud Design and an app get blurry and blurrier over time. Like I've seen people Of course there's no like persistence but build like fully functional like even games which is definitely not what we designed Cloud Design for but you can do it. It's just HTML and JavaScript. So, blurring those lines even further and thinking through like what is the path from a like fully featured design that looks really well to really good to something that is maybe more like a artifact where you're actually able to go and you know, persist data and share it with others and build from there. So, I think that those lines get really interesting over time, too.

</details>

**主持人**: 没错。产品设计的很大一部分在于品味。我试着用 Fable 问了它自己一个想问你的问题，它是这么写的：“你当年为了做 Instagram，几乎砍掉了 Bourbon（Instagram 的前身）里的所有复杂功能。那么在今天的 AI 领域，或者更具针对性地在 Claude 里，你会选择‘砍掉’或‘下线’什么功能？”

<details>
<summary>Original English</summary>

**Host**: Yeah. A big part of design is having taste. I actually asked Fable what Fable wants to ask you and this this this is what Fable came up with. You deleted almost all of Bourbon to get to Instagram which is like you had a whole you know solo mode whatever thing and you went to Instagram. What would you delete in AI or more spicy what would you delete in Claude?

</details>

**迈克·克里格**: 哈哈，我喜欢这个尖锐的问题。

我们在 Slack 里有一个叫 `#project-unship` 的频道，专门用来讨论：“有哪些功能是目前堆在产品里，但我们应该砍掉的？” 当年我们在 Instagram 时也面临过这种取舍。你可能会发现有些功能的日常使用率只有 4% 到 5%，你觉得这微不足道；但当你堆积了 20 个这样的功能时，你就陷入了经典的“微软 Word 困境”——每个用户都只使用其中一个互不相交的功能子集，导致产品变得无比臃肿。

因为我们的产品还很年轻，所以这种历史包袱相对少一些。比如我们最近下线了“样式设计”（Styles）这个功能，因为它不仅使用的人很少，而且从实现 AGI 的长远角度来看，这种非常生硬、规定死的使用方式是不对的，用“技能”（Skills）这种形式去实现要好得多。你必须有勇气去砍掉上一代 AI 交互的产物。

我目前在 Labs 之外花了一些时间思考的问题是：我们让用户去区分“写代码模式”（Code）、“协同模式”（Co-work）和“日常聊天模式”（Chat），但这些模式之间不能很好地互操作，不能互相委派任务。而对于一个刚从街上走过来的普通用户来说，你根本没法跟他们解释清楚这三个功能为什么是彼此独立的。

所以，**砍掉我们不同产品模式之间的复杂度**，把底层打通，这会让 Claude 表现得更好。没有什么比下面这种体验更让人沮丧的了：你在 Co-work 界面里跟模型理清了你想要构建的所有产品细节，最后你却不得不跟它说：“请帮我把这些梳理成一段话，这样我好把它复制粘贴到 Claude Code 里面去。” 这种体验太像是 2020 年代的旧工作流了，在今天它根本不应该存在。

<details>
<summary>Original English</summary>

**Mike Krieger**: Oh, I like the spice. I think I mean we have it's interesting we have a one of our slack channels is like project unship which is like what is in the product right now. It's I mean this is hard at Instagram. The Instagram we what things that had like four to five percent usage you're like oh that's really not very many but then you have like 20 features that each have four to five percent usage is like the classic Microsoft Word problem of like everybody uses some disjoint subset of the of the functionality. So that that's always the challenge. Now I think we're younger product so hopefully we have less of those things. Like we unship styles I think recently where it was like used by a small percentage of people and was not really AGI filled in a lot of ways it was like very sort of prescriptive in the way that it worked and skills very much better applications and then like that. So I think you have to be willing to take the primitives of like one generation of AI and like unship them or at least like supplement them or supplant them with the next one as well. I think the biggest thing is I look at it and I've been spending some time like outside labs on some of this is like man like we're asking people to make like code versus co-work versus like chat distinctions and like one they don't interoperate well and they can't delegate to each other and two I think the average person off the street could not explain to you why those are all different. So I think deleting some of the product complexity within our our code or our product I think is a a thing that would would serve well. Also because then Claude can do what it needs to do and and do well. Like there's nothing more frustrating than having a co-work session where you're like great I've mapped out exactly what I want you to build and then be like can you please like create a paragraph that I can paste into Claude code? Like that is some 2020 you know kind of workflow there that really shouldn't exist anymore.

</details>

### 初创公司的核心壁垒

**主持人**: 的确。明确不做什么是很难的。今天也是我们的“初创公司日”（Startups Day），我们在座的很多人对初创公司都非常有共鸣。但现场也弥漫着一些焦虑：大家觉得，万一明天 Anthropic 醒来发布了几个 Markdown 文件，就把我所在的整个细分行业彻底给颠覆了呢？

<details>
<summary>Original English</summary>

**Host**: Yeah. Um I think drawing lines on what you don't want to do and also sort of leaving room for others is interesting. Um a lot of people today is like the startups day for AI E or obviously very sympathetically aligned to startups. Uh but there's some anxiety in the room because tomorrow's Anthropic could wake up and publish some markdown files that destroy my industry. Um so

</details>

**迈克·克里格**: （笑）

<details>
<summary>Original English</summary>

**Mike Krieger**: [laughter]

</details>

**主持人**: 那我们为什么不直接放弃，全部加入 Anthropic 算了？我们为什么还要折腾去创办别的公司呢？

<details>
<summary>Original English</summary>

**Host**: uh why should we not all just give up and join Anthropic? Like why bother starting any other company?

</details>

**迈克·克里格**: 我加入 Anthropic 的核心原因之一，是因为我看到了即使在早些时候模型编程能力还没那么强的时候，它一旦爆发，将会为下一代的**垂直初创公司**释放多么巨大的想象空间。这并不是因为模型能代替你的直觉、创意或品味，而是因为它把试错和实验的物理成本降到了极低，让初创小团队能以极快的速度狂奔。我至今深信这一点。

我们当年在做 Instagram 的时候也面临同样的拷问。投资人经常问我们：“如果 Google 推出一款竞品照片工具，你们该怎么办？” 事实上，Google 确实会推出一款非常有“Google 味”的相册产品，但那款产品不可避免地会被绑定在他们既有的庞大生态和利益纠葛中。

我们虽然是一家底座平台公司（Platform），但平台是不可能在每一个垂直细分领域都做到极致专注的。如果你能对自己所在的细分行业、垂直品类或者特定用户群体的真实痛点保持**激光般聚焦的痴迷（Laser Obsessed）**，底座大模型厂商是永远无法在这个深度上与你竞争的。这种专注会带给你独特的用户热爱和粘性。

诚然，在今天这个模型能力强大的时代，创办一家初创公司确实变难了，很多轻量级的功能点直接被大模型的能力覆盖了。但那些真正硬核的痛点依然存在：**去深入理解用户的需求，去理清你的获客路径，去倾听用户的反馈并以最快的速度迭代**。一个四五个人、对某个痛点近乎偏执般痴迷的敏捷小团队，其奔跑速度永远会超过大厂里被繁文缛节和利益协调所拖累的庞大团队。

所以我对初创公司的未来依然持非常乐观的悲观主义态度（Bullish on Startups）。写代码从来都不是初创公司生死存亡的唯一决定性瓶颈，真正的核心，永远在于你对特定业务场景（Domain Knowledge）和用户痛点的独特理解。

<details>
<summary>Original English</summary>

**Mike Krieger**: Um I I mean actually joined one of the main reasons I joined Anthropic was because I saw how much this was like, you know, the models weren't that good at coding up but they were getting there. Like how much it would unlock like whole like next generation of startups. Not because it was going to solve their ideation or their taste, but because like it would make experimentation way simpler and would get you to move faster. And I still like really believe that. And I mean it's the reality of, you know, uh And we saw this with like Instagram. Like we would get questions from investors like, well, what happens when Google launches a photos product? It's like Google's going to launch a very googly photos product and it's going to have to be bound by the integrations that they already have and it's going to be like it's going to play to their strengths. And I think that is going to be true. And I'm not like giving advice on how to compete with Anthropic, I guess in a way, but like it's actually not because we're also a platform which is like there's so much I think room to be like laser obsessed with your particular vertical or your industry or group of people that you know really well in a way that like none of the labs are ever going to get to that level of uh of understanding and like therefore get that kind of adoption and user love and and build that out. Now, it's definitely harder in the age where like the models can just do a lot and so there's, you know, some of these things can be like skillified and like maybe don't need their own dedicated product. But I think it's like the hard stuff is still hard. It's like understanding the needs of people, like figuring out how you're going to reach them, uh listening to them and iterating on them really quickly. Like it is still the case that like a group of four or five people obsessed with a problem is going to move faster than those same people at any other kind of organization that are like, you know, subject just to the complexity. I just mentioned the like the fact that we have, you know, a lot of different products that kind of interoperate. Like that's a interesting constraint that we have to work through. It's an advantage in other ways, right? So, yeah, I'm still like very long and bullish on startups and um it's just it tapers over the fact that like writing code was never the like the limiting part. You know, maybe it was on the timeline perspective, but it was never like the thing that was going to like make or break a startup. It's really that space and user understanding.

</details>

**主持人**: 没错，行业专有知识（Domain Knowledge）。

<details>
<summary>Original English</summary>

**Host**: Yeah. Uh domain knowledge.

</details>

**迈克·克里格**: 是的。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah.

</details>

**主持人**: 今天也是我们的“垂直 AI 日”（Vertical AI Day）。我们的一位常驻嘉宾 Chris Lovejoy，经常和我们探讨医疗 AI 领域。他最近刚刚被你们招致麾下，去领导 Anthropic 的医疗健康团队。此外，我们下一个核心讨论板块是金融。你们最近刚刚在纽约举办了一场盛大的金融峰会。在这两个垂直领域，你看到了哪些机会？特别是针对 Claude。显然，这些行业里充斥着大量的 Excel 表格。

<details>
<summary>Original English</summary>

**Host**: Uh today is also our day for vertical AI. Uh one of our uh returning speakers and top speakers, Chris Lovejoy, uh was always talking about vertical AI. He was in from interior in the healthcare space. And then recently I was I invited him back and turned out he you guys just hired him for your uh healthcare efforts. Um we also our next big one is also finance. You know, we have a yeah, a finance track. You guys just had a huge finance event in New York City. Um and where our next uh AI is is sort of finance focused. What are you seeing there? Any you know, any potential uh for Claude? Obviously a lot of Excel Excel spreadsheets.

</details>

### 金融与医疗的垂直化探索

**迈克·克里格**: 没错。这是一个每一代新模型在能力上都会有阶跃式提升的领域。目前许多优秀的垂直金融初创公司做出了非常多有价值的评测基准（Evals），看着这些基准数据不断刷新非常令人振奋。

在这些垂直行业中，一个非常有趣的趋势是**“即时性分析”（Just-in-Time Analyses）与“强验证数据”的结合**。如果一个应用完全是自由格式的（Free Form），没有任何确定性的数据限制，这对于金融这种需要极度精确性的行业来说绝对是一场灾难。

因此，如何找到那条分界线——一方面保持模型生成应用、分析看板和工作流的极大灵活性，另一方面又在底层提供坚实的**可验证性、审计日志（Audit Logging）和数据溯源（Data Provenance）**。我觉得这就是垂直 AI 应用的“工程艺术”所在。

如果这件事情做好了，你就能同时拥有两个世界的优势。而难点在于，现存的许多保证合规和可审计的旧系统，其底层设计在天然上是排斥这种高灵活性的 Agent 工作负载的。这就是为什么说，在技术栈的底座端和应用端，目前都孕育着巨大的创业机会。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah. No, I think that there's there's a lot in there, too. And that's like an area where uh you could see the model get clearly better at it like sort of generation to generation. And there's, you know, there's some good sort of vertical specific uh uh finance startups that have like done their own um evals, which has also been interesting to to track. And it's not like we're like sort of playing to the eval, but it is a useful sort of barometer around like is this actually getting better um at these finance use cases. I think the interesting blend that's going to happen um is this mix of, again, the model having the flexibility to like dive in and create just-in-time analyses or dashboards or workflows with like some sense of like what is the not immutable, but at least like verified sort of set of data. And so like uh set having all of that be totally free form, I think is a recipe for confusion and is like not what most companies in the financial services space want. So, finding that right uh sort of cut line where you have verifiability and audit logging and and sort of data provenance here, but not in a way that constrains the kinds of applications that you can build on top, I think is a lot of the art that we're seeing in that space as well. Um and I think, you know, if you solve it well, you can you can get the best of both worlds. The hard part is a lot of the systems that were built to do the verifiability audibility like are kind of almost by design not super flexible in terms of agentic workloads on top. So, I think there's opportunity at both sides of the stack there.

</details>

**主持人**: 没错。我们也将在接下来的纽约活动中深入探讨这个话题。最后，我想以一个关于**心理健康**的话题来收尾。这在很多技术大会上往往被讨论得太少了。在如此狂热的 AI 竞赛中，大家都在没日没夜地加班（996），拼命地刷新推特和各种发布会时间线，这极其令人精疲力竭。对于那些处在风暴中心的从业者，你有什么建议来帮他们避免倦怠（Burnout）？

<details>
<summary>Original English</summary>

**Host**: Yeah. Um I think I I also agree we'll be exploring that in in New York. Um the last thing I want to end on is on mental health, which we don't talk about enough in technical conference conferences. Um you've seen a lot of hyper growth. People are just always refreshing their timelines and it's exhausting. Um how do you advise people who are working 996 to avoid burnout?

</details>

### AI 竞速中的心理健康与长期博弈

**迈克·克里格**: 这是个非常沉重且真实的话题。身处这个行业的每个人应该都在切身经历着这种高压。现在的竞争烈度比当年 Instagram 的时期要高出好几个数量级，事情发生的速度太快了。

当年在 Instagram，我们一年中最紧张的时刻，顶多就是看苹果在 WWDC 大会上会宣布什么新功能，看看它是会帮到我们还是击碎我们，但这也就是一年一次的频率；或者某个竞争对手每隔三四个月推出一次更新。

而现在完全不是这样。在 Anthropic，我们每周三会举行全员大会（All Hands），里面有一张例行幻灯片叫“本周 AI 大事记”，而每一次到了周三，上面就已经写满了——这周又有哪家竞品发布了新模型，又诞生了什么新产品，或者监管层又有了什么新动向。所有事情都在以疯狂的速度推进。

我个人保持相对清醒和健康的方式，第一点是**强制划定离线时间（Carving Time Off）**。我们团队的创始人们在这方面做了一个很好的示范：他们总是强调，一旦你彻底倦怠、燃尽了，你的职业生涯基本上就宣告结束了。我亲眼看到过这种不幸发生在我身边非常亲近的朋友身上，而要从彻底的 Burnout 中恢复过来，需要极其漫长的时间。

因此，你必须鼓励员工：这个世界上没有任何工作是重要到你不能离线休假几天的。如果你的系统离了你运转个几天就会瘫痪，那说明你们的团队架构本身就出了问题，你需要去找一个导师去聊聊如何解耦这个瓶颈。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah. I mean, I think this is a hard one. I mean, and it is, I'm sure you are experiencing this cuz you're all working in this industry like it is you know, multiples more intense and things move much more quickly at an Instagram like our the two things that we were thinking about was like, what is Apple going to announce at WWDC and is it going to like totally mess us up or boost us, right? So, that's like once a year. Um or, you know, maybe a competitor launches every three or four months, right? And uh it is definitely not that. It's a topic we we do a when we do do our weekly all hands. Usually on Wednesdays and we have a slide that's like the week in AI at Pinterest is and it's only Wednesday and like and inevitably like some competitor has shipped a new model and like there's been a like new product and maybe there's some interesting thing happening um uh on the regulation side. Like if things are moving really, really quickly. I think the way I try to stay at least relatively sane, um one is like actually carving time off and I think the topic co-founders do a good job of like saying like, look, like burnout if you you out, like you're kind of done. I've seen it happen unfortunately to people I'm really close to and then it takes a long time to recover from that. Um so actually encouraging people like there's no job that is so important that you can't be offline for a couple of days. Um so I think that's like a big key like piece in there. So like let's

</details>

**主持人**: （掌声）

<details>
<summary>Original English</summary>

**Host**: [applause]

</details>

**迈克·克里格**: 谢谢。这也是我强烈笃信的理念。

第二点，我非常喜欢体育，体育运动里有一个很经典的信条：**“你永远没有你打得最好的一场比赛那么神，也永远没有你打得最烂的一场比赛那么糟。”** 

这句话放在今天的 AI 浪潮中再贴切不过了。今天推特上还充斥着“AI 已经结束了、泡沫要破了”（It's Over），明天就变成了“我们又活过来了、AGI 要降临了”（We're Back）。如果你把自己的个人价值和这种舆论起伏深度绑定，你迟早会被折腾疯的。

本·霍罗威茨（Ben Horowitz）在《创业维艰》里有一章专门写“我们完蛋了”（We're Effed）。每一个身处初创公司的人都必然经历过这种瞬间：“哦天呐，这件事情砸了，我们绝对无法挺过去，死定了。” 我们在 Instagram 也经历过好几次这样的至暗时刻。

但真正的考验在于，你和你的团队如何一步步穿过这些风暴。这才是最终定义一家公司的东西。我总是提醒我自己和 Anthropic 的团队：这是一场极其漫长的长跑（Long Game）。模型的发布起伏、一时的舆论反应、今天的竞品发布，在长期的尺度下都是微不足道的噪音。你只需要专注于去打造一个健康的团队和文化，去信任彼此，保持定力。

当你感到极度焦虑或者遭遇挫折时，**公开表达你的脆弱（Vulnerability）**是非常有力量的。这是我从我的个人教练（Coach）那里得到的极好的建议。当你在团队里感到痛苦或沮丧时，大方地把它说出来。

几个月前，我们经历了一个我们付出了极大心血的 Labs 项目被决定砍掉的瞬间。在团队会议上，我直接作为主持人说：“说实话，我今天真的非常难过和沮丧，我多么希望我们努力了这么久的东西能够成功。”

当作为领导者的我把这种情绪和脆弱表达出来后，它为在场的其他人撑开了一个安全的空间。大家开始纷纷表达：“是的，我也很愤怒”、“我也觉得非常难过”。只有当大家把这些情绪宣泄并对齐之后，我们才能坦然地放下，进入下一个阶段，去商量：“好吧，那接下来我们该怎么做？” 这比把负面情绪憋在心里要好得多。

<details>
<summary>Original English</summary>

**Mike Krieger**: strongly believe. Um And if it is you're probably doing something wrong and you talk to somebody who could be a mentor to figure out how you can unblock that. Um and then I think the other one as well is like I love sports and like uh this is the notion of like you're never as good as like your best game and you're never as bad as your worst game. I think that's also really true. Like I know like in AI there's like the you know it's so over we're so back thing. Like that like if you internalize that that cycle is always going to be at play in some way, you realize like it's never that bad. Like Ben Horowitz's book the hard thing about hard things has this chapter on like we're effed it's over and like that feeling as a startup that probably many of you have had at startups where you're like oh I can't believe this thing happened like we're never going to like recover from this. I definitely we definitely had an Instagram a couple of times. And then you get through it and like it's that like def like defines the company when you can actually go through that. I try to remind myself and the team here even with an Entropic which is like like this is a is a fast-moving but is also a long game. And it's like we're never it's never just about today's model launch and reaction or this product launch and everything else. Like you're playing and you're building and you just have to trust that you're building like the team and culture that is going to get through those things and have that sense of perspective even if perspective is saying like look 3 months ago we were in a similar position. Maybe it's not a year it's just a matter of months but it's still like zooming out and not taking things not letting your internal sort of like sense of self and success be so driven by the day-to-day. Yeah. It has anyone any coach or mentor said something to you that you repeat to yourself that gets you through the hard tough times? Um I think the biggest one was this like sense of like if you're feeling something it's really often the case that other people on the team are feeling it too. So this is like advice I got from my my coach around just being like like just verbalizing emotions like even saying like hey I'm feeling really stressed out about this or yeah I'm really sad that we are shutting down this labs initiative. I literally had this meeting a couple months ago where I was working really hard on something and I kicked off the meeting like I'll kick it off like I'm really sad like I'm frustrated like I wish this thing had worked out and I think that holds the space for other people to be like yeah I'm pissed off too or like I'm sad too and like I think giving that advice around like not I think if you can get yourself to be open and vulnerable it often like lets other people verbalize that and then you can from there you can be like great what are we going to do about it like you know it's much easier to start from that place.

</details>

**主持人**: 太棒了。我们昨天的会议就是以 Stanford 著名的“Touchy Feely”人际动力学课程导师 Carol Robbins 的演讲开场的。我想没有比鼓励大家表达真实感受、管理心理健康并保持专注构建更好的收尾方式了。非常感谢迈克。

<details>
<summary>Original English</summary>

**Host**: Yeah we actually kicked off AIE with a session from Carol Robbins who runs touchy feely at Stanford and I can't think of a better way to end than encouraging people to talk about their feelings manage their mental health and keep shipping.

</details>

**迈克·克里格**: 感谢你的邀请。

<details>
<summary>Original English</summary>

**Mike Krieger**: Yeah. Thanks so much Mike. Thanks for having me.

</details>