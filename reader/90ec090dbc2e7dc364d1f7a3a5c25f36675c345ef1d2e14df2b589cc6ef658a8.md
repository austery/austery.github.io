---
author: AI Engineer
date: '2026-11-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=JNexz3Tbiu8
speaker: AI Engineer
tags:
  - coding-agent
  - software-engineering
  - agent-orchestration
  - workflow-automation
title: 在构建软件工厂之前，先打造工作室
summary: Armin Ronacher 分享使用编码 Agent 构建软件的经验，主张在追求全自动化软件工厂之前先建立高品质的工作室。他结合自身使用数据指出，虽然模型能力提升显著减少了人工修正并延长了 Agent 单次运行时间，但人类注意力仍是核心瓶颈；长期维护、协作与标准制定依然困难。他建议开发者保持工程技能与代码品味，克制无序膨胀，并探讨了持久化 Agent、弹性调度与结合轻量分类模型的代码编排工作流。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Armin Ronacher
companies_orgs:
  - Arendelle
  - Cloudflare
products_models:
  - Pi
  - Opus 4.6
  - Astra
  - Soul
  - PyAutoResearch
  - Jeff
  - Codex
media_books: []
status: evergreen
---
### 构建工作室，而非软件工厂

大家好，我叫 Armin Ronacher。今天想和大家分享一些我们在使用 Agent 构建软件过程中学到的经验。尤其是，我想极力主张：我们眼下更应该打造的是“工作室”（atelier / workshop），而不是急着去建造“软件工厂”。我打算结合我们自身实际使用的一些数据来说明这一点，但最核心的是，我想解释为什么在构建软件工厂之前，我们应当先建立好工作室。

<details>
<summary>Original English</summary>
[music]
>> Uh my name is Armin Ronacher and I want to share with you a little bit the lessons that we have learned from building software with agents and in particular I want to make a strong case for um not so much building the factory as building the atelier or workshop. And um I want to show some data with this from our own usage, but in particular I want to explain what I mean by building the atelier or the workshop prior to building the software factory.
</details>

我想在座的各位使用 Agent 都已经有一段时间了，大家大概也注意到了，我们在利用它们所能做的事情上，似乎正处于一条指数级增长的曲线上。但我在这里想打个比方：你可以成为一名出色的艺术家，使用从 CNC 机床、3D 打印机到各种极佳电动工具等最新最强的技术，而这些工具可以放大你对自己艺术创作抱有的抱负。我认为我们也可以在某种程度上这样看待软件——也就是说，重点不在于制造数量多得多的软件，而在于打造更具雄心、品质更高的软件。接下来我会向大家展示一下我这么说的具体含义。

<details>
<summary>Original English</summary>
And um I think everybody here is being used has been using agents for quite a while and you have probably noticed that uh it is we're sort of on an exponential curve in in what we can do with them. Um but the comparison that I want to give here is that you can be an amazing artist and use the greatest and latest technology from CNC machines to 3D printers to just very good power tools and it can increase the ambition of what you can do with your art. And I think we can also look at software a little bit in that sense. Uh so less about building much more software and just building way more ambitious and high quality software. Um so I'm going to show you a little bit of what I mean by that.
</details>

大家可能知道 Arendelle 正在开发 Pi 编码 Agent，所以在看待这个问题时，我们显然有自己的切身实践。不过我觉得相当有意思的一点是：Pi 编码 Agent 在核心 Harness 层面已经有一年没有真正变动过了。它今天所拥有的工具集，和去年 12 月时完全一样。我认为这很有启发性，因为它的能力大幅增强，纯粹是模型本身变得更强所带来的结果。因此，在没有对 Harness 核心功能进行任何变更的情况下，我今天用 Pi 能做的事情已经强大得多了。我认为反思这一点很有意义：这意味着即便我们不在做事的方法上引入重大改变，我们所有人也都在同时变得更强。

<details>
<summary>Original English</summary>
Um and um you might know that Arendelle is working on the PyCoding agent. So we have obviously a little bit of a horse in the race here of how we're looking at this. Um but I think what is probably quite interesting is that the PyCoding agent has not really changed in a year on the core harness. It still has the same tools today as it did uh in December last year. And I think this is interesting because it has become much more powerful purely as a effect of the models getting better. And so I'm much more capable today of what I can do with Py without any changes landing in the core functionality of what the harness is doing. And I think this is an interesting thing to reflect on it means that we're all simultaneously getting better even without landing any significant changes in how we're doing this.
</details>

在过去大约一年半的时间里，大家可能还记得曾涌现出许多关于如何更好编写 Prompt，或者如何在 Harness 上玩出新花样的想法。如今这些技巧中还在发挥作用的已经寥寥无几了。对我来说一个很好的例子是：我曾经非常喜欢 PyAutoResearch，它是一个插件，基本上能让 Agent 自主朝着某个目标前进，比如优化性能。但如果你使用当今最先进的模型，你会发现整个插件其实已经没有存在的必要了。所以，单单是模型本身发生的演进，就已经极大地改善了我们的工作方式。这些机器正在变得越来越厉害。

<details>
<summary>Original English</summary>
And um you might have remembered throughout the last year and a half maybe that there were a lot of ideas of how you can prompt the machines better or how you can do some interesting tricks with the harness. Very few of them are still necessary. For me a good example here is that I was in love with PyAutoResearch which was a plugin that basically allowed an agent to drive towards a goal like improving performance. But if you use a present day state of the art model you'll actually discover that the entire plugin is no longer necessary. So there's a lot that is just happening in the models that is dramatically improving how we're doing. So these machines are getting better.
</details>

### 数据体现的变化：人工介入减少与运行时长增加

我想通过几张图表来展示这一点，这些数据基本上来自我的 Pi 会话，且过滤为仅使用默认设置。我需要做的人工纠错总量——这里我使用了 chef 来做分析——伴随着每一个新模型的迭代提升，一直在不断下降。因此，与去年 12 月相比，面对最新模型时我提出的反对和纠正要少得多。在对其进行引导设置的频率上也是同样的情况。

<details>
<summary>Original English</summary>
Um and I just want to show this from a couple of graphs from basically my Py sessions where I filtered them out to be have nothing but the default set. And the total amount of corrections and I used chef to analyze this the total amount of corrections that I had to do uh got down and down and down with every single model that got better and better. So I'm I'm pushing back a lot less against the the the the the agent um with the latest model than I did uh in December last year. And the same thing with like how often I'm onboarding it.
</details>

对我而言，在分析会话中最有意思的一个维度，是 Agent 响应我给出的任务时的平均运行时长。这里看的是第 90 百分位数（P90）：去年 12 月使用 Opus 4.6 时，Agent 运行的 P90 时长大约是 2.5 分钟；而如今面对最新的模型，它们的 P90 运行时间已经达到了 14 分钟甚至更长。这确实改变了你与 Harness 协作的方式。但同样值得强调的是，Pi 本身并没有发生任何改动，可我使用它的行为模式却出现了这种显著变化。

<details>
<summary>Original English</summary>
Um and I think this to me was the most interesting way in which I sort of analyzed my sessions which is the average so this is the P90th percentile but the 90th percentile of how long an agent was running in response to a task that I gave it uh with Opus 4.6 in December last year was about two and a half minutes. And now with the latest models they are on the 90th percentile running for 14 minutes and more. And that does actually change something about how you want to work with a harness. But really again nothing in Py has changed and still I'm I'm seeing this sort of different behavior of of how I'm using this.
</details>

如果你一直使用 Agent 并且关注它的执行过程，大概也会以某种形式注意到这一点：现在的 Agent 相比提供的其他工具，要更加倾向于使用 Bash。但再次说明，我们在配置上没有做任何变动，纯粹是模型自身涌现出了更多的自主行为。这里图表中缺少了 Astra 和 Soul，在我的测试中它们其实和 Opus 表现非常相似，只是我的测试集中数据量不够，无法在此做很好的展示。大家会注意到这里有一小块紫色区域，最后我想谈谈这个，也就是“代码模式”（code mode）正在慢慢抬头。但其核心在于：即便你拥有一套现成且表现不错的基础设施，它依然会因为模型的进步而发生改变。

<details>
<summary>Original English</summary>
Um and this probably you have noticed in one form another if you're still using an agent we kind of see what it's doing you've probably noticed that the present day agents are much more likely to use Bash than any of the other tools that are being provided. But again nothing has changed in how we configure the It's just that there's a lot more emergent behavior coming from the models. What's missing here is Astra and Soul. They actually look very similar to Opus for my testing. I just didn't have enough data in my test set to show this nicely. You will notice that there's a little purple thing here. I want to talk about this in the end, which is sort of code mode is sort of slowly creeping up. But the core of this is even if you have a piece of infrastructure nowadays that is sort of there and is doing a good job, it's still changing as a result of the models.
</details>

### 人类注意力的瓶颈与维护挑战

过去一年里没有改变的——至少对我来说是这样，而且我认为对很多人也是如此——就是我们依然是人类，依然受限于我们最底层的生理与认知能力。随着我们的雄心越来越大、交给机器做的事情越来越多，我不想说我们成了“瓶颈”，但我们确实是把控它们产出节奏的决定因素。具体来说，对我而言人类的注意力就是那个制约因素。我在编码 Agent 部署到团队的过程中普遍注意到了这一点：我们可用于投入的注意力总量是非常恒定的。有了这些 Agent，启动一个新项目变得异常容易。尤其是在新模型发布时，我们都无比兴奋地想去尝试各种最新最强的功能，从 3D 游戏到各种新型自动化流程。但是，维护这些项目并没有真正变得更容易。

<details>
<summary>Original English</summary>
What has not changed in the last year, at least this is the case for me, and I think this is the case for a lot of people, is that we are still humans. We're still limited by our fundamental capabilities. And as we are being more ambitious and we're doing more of these machines, we're I'm not I don't want to say like we're the bottleneck, but we are the thing that paces what they can do. And in particular, human attention is for me at least the limiting factor and I'm noticing this with largely in how coding agents are deployed in teams, that this is so a stable amount of like attention that we have that we have to work with. And starting a new project is getting incredibly easy with these agents. And I think like particularly when a new model comes out, we're all super excited of trying the latest and greatest thing we can do from 3D games to new ways in which we automate things. But maintaining them has not really gotten easier.
</details>

此外，我们还在不断给许多外部系统施加沉重的负担，而这些系统在很多层面上原本是不该被卷入这场变革的。我想大家都清楚 GitHub 上被推送了多得多的 Commit 和代码仓库。但我还认识不少人，他们那些在互联网上运行良好的老牌网站被 Agent 赋予了“新生命”，而面对我们直接打过去的全新访问量，它们完全没有做好准备。所以我在这里想稍作提醒：当我们全力推进这些技术时，我们大家也在不经意间同步制造着一些冲击，而外界对 Agent 的这些行为其实并没有做好准备。

<details>
<summary>Original English</summary>
But we are also increasingly taxing a lot of external systems that actually in many ways are not supposed to be part of this revolution. I think we all know that GitHub has a lot more commits being pushed up there, a lot more repositories. But I know quite a few people who have well established all the websites on the internet that found a new life for agents and they are totally not ready for the new volume that's coming from from us kind of directly hitting them. So I just want to caution a little bit here in saying that when we are pushing things, we are also accidentally simultaneously all of us pushing things um, which we're not really ready for for what agents are doing.
</details>

对我来说，这张图表非常有意思：这一年中我主动发送的 Prompt 数量大致是平稳的。我知道某些月份会稍高一些，某些月份会稍低一些，但基本上是在每天 120 到 190 条左右交替。然而大家可以看到，Agent 为我工作处于活跃状态的时间，从最开始不到我单个工作日的时间，飙升到了我工作日时长的数倍。而且这个 11 月甚至还没过完，对吧？你可以看到这条曲线正呈现指数级上升趋势。

<details>
<summary>Original English</summary>
Um, and this to me, I think, is an interesting graph because uh the number of prompts that I'm actively pushing over the year is is sort of flat. I know that like in some months it's a little bit higher, in some months it's a little bit lower, but they're they're alternating between 120 190 something like this prompts uh that I'm pushing per day. Um, but you can see that the time that the agent was active for my use went from like less than my working day to many times my working day. Um, and this November is not even over, right? So you can see that this is taking an exponential curve up.
</details>

而这里显示的是项目数量，即我在过去一年里创建的 Git 仓库数量，显然呈累积上升趋势。我一共发起了 141 个不同的项目；但我保持稳定节奏提交代码的项目数量——也就是提交超过 5 天且后续还会回访的项目——几乎是一条平线，大约在 10 到 15 个之间。我也和一帮朋友做过非正式的调研交流，这似乎是一个普遍现象：长期规律性地维护项目其实非常棘手。

<details>
<summary>Original English</summary>
Um, and this here is the number of projects, this is Git repositories that I've created over the last year, and this is like obviously cumulatively going up. So I have 141 different projects that I started, but the number of projects I'm committing on a regular cadence too, um, which means like I'm committing for more than five days too and I'm I'm returning to them also, um, is is pretty much flat with with between 10 15 something like this. Um, and I have I have done this sort of an informal survey with a bunch of my friends as well, and this seems to be a common trend that actually maintaining something regularly is tricky.
</details>

围绕这张图表，我曾和一位朋友讨论过。他说：“其实我有一个开源项目现在已经完全自动化了：Issue 追踪器收到反馈，有配置好的 Agent 会自动做 Review、提交代码并回复。”这或许是一种扩展规模的方法，也就是把人从整个流程中剔除出去；但实际上他后来把这套机制关掉了，因为他最终对这个项目没那么在乎了，而且他希望能把 Token 额度留给其他事情。所以说，即使我们已经把开源项目完全自动化了，我们对其倾注的注意力依然至关重要。如果我们不再使用某样东西，我们往往就不会再去主动维护它。

<details>
<summary>Original English</summary>
And, um, I had this discussion with a friend of mine, uh, in sort of in relation to this graph and he said like, well actually I have an open source project that is now fully automated. So uh there's a issue tracker coming in, there's a there's an agent that's set up to auto review, commit and send it back. And that is maybe a way to scale up so you take the human out of the whole thing, but actually he also turned it off because eventually he didn't care about the project as much anymore and he wanted his token specs to use them for other things. Um, so our attention to an open source project matters even if maybe we have automated entirely. So if we stop using something where we have a tendency to no longer actually actively take care of it.
</details>

### 真实技能、认知掌控与防范无序膨胀

因此，如果我们主张首先搞清楚如何打造一个极佳的工作室来构建高品质软件，那么核心关键究竟是什么？我认为对我来说，最重要的有三点：

其一，是真正懂得何时对 Agent 的所作所为叫停并纠偏，明确告诉它这样行不通。我认为这是一项至关重要的技能，因为 Agent 获得的奖励仅仅来自于“完成目标”，而评判它是否达成这个目标非常容易。我们可以将其类比为强化学习环境在训练过程中对模型的奖励机制。但这并不意味着它最终交付出来的东西，在较长的时间跨度内是我们发自内心认可的。随着我们提交的 Commit 越来越多、软件规模越来越大，问题就会变得棘手。给软件堆砌出各种特性的“辛普森汽车”是轻而易举的；但要做出内在协调一致、内部复杂度不会爆炸式膨胀的系统，依然需要我们在它工作的过程中同步参与。

<details>
<summary>Original English</summary>
Um, so if we're pushing towards, and I would make this argument, first figuring out how to make a really good workshop to build really high quality software, there's a question of what matters. And I think for me, the three most important things to matter is on the one hand, to to really know when to push back against what an agent is doing, telling it that this is the wrong way of doing it. And I think that this is a crucial skill because an agent is really rewarded in just completing a goal. And it is very easy to look at if it has succeeded in this goal or not. Um and this we can sort of see it in the same way as the the RL environment maybe is rewarding the the model doing training. Um but it doesn't mean that what is being actually delivered is something that we are intrinsically happy with over a longer period of time. And this becomes tricky the more and more commits we're doing, the larger and larger the software is going. It is very easy to basically create the Simpson car of all the features in a software. Um but actually having something that intrinsically fits together where the internal complexity of a system does not is like um explode uh still requires us to um to to work with it as it's working.
</details>

我喜欢把这称为“真正的技能”与“Agent 技能”的差异。经验丰富的软件工程师在使用 Agent 时，与非专业工程师之间存在着非常明显的不同。对我来说最典型的写照是：我的儿子现在会给我们在合作的一个项目提交 Pull Request。因为他不是软件工程师，他提交的代码质量存在非常明显的差距；可我们用来给 Agent 发 Prompt 的是完全同一套系统，对吧？

我自己曾遇到过类似情况，但也常听许多其他人抱怨过：在至关重要的场合中，如果同处一室的其他人面对问题只是直接去问自己的 Agent，而不再对自身系统在做什么有深刻理解，或者无法真正弄明白他们正在解决的底层问题，这种体验其实是让人非常沮丧的。因此，始终透彻理解自己在做什么，依然具有极其重要的价值。

<details>
<summary>Original English</summary>
And I I like to call this like true skill versus agent skill. Um there is clearly a difference between someone who is an experienced software engineer working with an agent and someone who is not an experienced software engineer. And um I think for me the the truest form of this is that uh my son is now sending me pull requests on a project that we're doing together. And there's a very clear quality difference in what his contributions are because he is not a software engineer. Um but we're using the same system to prompt it, right? Um and I have I've noticed this myself in situations, but I've I've heard this also particularly from a lot of others. It is actually a very frustrating experience if you're in a situation that really matters and other people in the room are basically just going to their agent to answer a question and no longer have a really under good understanding of either what their system is doing or that the fundamental problem that they're working on they actually comprehend. Um so there is a lot of in still understanding what you're doing.
</details>

这也意味着你必须调节自己做事的节奏，使其始终保持在你的认知理解范围之内。随着我的 Commit 数量开始暴增，我采用的一种应对方式是：审视我每个会话的执行轨迹，看看能否在任务结束前切入某个环节，找到一种固定的方式来评估当前的进展。例如，我开始通过 Prompt 要求 Agent：在其进入验证阶段之前（通常在整个进度的 70% 左右），先为我生成一份精炼明了的高管摘要，并排版成漂亮的 HTML 页面，这样在它收尾的过程中我就能切实弄清楚它到底在做什么。尤其是借助更新的模型，输出的文本读起来不再那么痛苦了。这是我找到的一种平衡手段，因为在很多情况下我已经基本不再直接通读代码了。

<details>
<summary>Original English</summary>
Um, that also means that you kind of have to moderate the speed in which you're doing things to still work within your understanding. And one of the ways in which I started doing this as my commits started going through the roof basically was I I looked into how are my trajectories of sessions going and can I hook myself into a part before the end of it to find a consistent way for me to evaluate what's going on. And so for instance, I started um basically prompting the agent that before it's going towards the verification, which is typically around 70% of it, to start producing me a really nice short executive summaries and a nice typeset HTML page that can really understand what it's doing as it's finishing. Particularly with newer models, it's no longer quite as horrible to read the text that comes out of it. Um, but this is one way in which I found to balance out that I'm basically no longer reading the code in a lot of cases.
</details>

### 标准、协议与人际协作的重要性

另外一点对我来说日益重要：那就是在介入时要带有一定的导向，避免反复重写所有的软件。我向来极其推崇减少外部依赖、尽可能自己编写代码，因此从这个角度来看，我非常喜欢 Agent 带来的变革。但在德语中有一个词叫作 *Wildwuchs*，基本意思是“无序野生”或过度蔓延。原本应当协同工作的软件如果发生无序膨胀，会带来许多非常严重的负面后果。

大家最近可能看到过一篇流传很广的博文，讲的是一个经过特殊构造的 TAR 归档文件，不同的 TAR 实现读取它的方式截然不同。我认为这成了眼下的一个问题。为了让我们能够协同工作，我们极度需要标准，需要共同的规范和通用的文件格式。现在我们基本上能让 Agent 去实现任何我们想要的格式，但这些差异性必然会出现。而真正阻碍我们在标准上达成一致、阻碍我们共同协作完成某件事的，往往不是技术挑战，更多的是人们如何在“这个文件格式应该包含什么”、“应该如何实现”以及“应该如何解读”上达成一致的问题，因为对其可能会存在多种不同的解读。

<details>
<summary>Original English</summary>
Um, and this I think is something that increasingly is more important to me is to to to also show up with a little bit of a a guidance towards um not writing all the software over and over. Um, I'm a huge believer in using few dependencies and writing more code yourself. So I really like the agent revolution for for that element of it. Um, but in German we have this word called which basically means uncontrolled growth. And uncontrolled growth in software that is supposed to work together can have a lot of really negative consequences. Um, you might have seen a blog post that was going around recently about a tar archive that is has been crafted in a way that different tar implementations read it in different ways. And um I think this is a bit of a problem now. Um, we for us to work together we we really want to have standards. We want to have uh common specifications. We want to have common file formats. And we now can basically make an agent implement any format we want. But they're going to be these differences. And what really makes it hard for us to agree on standards and what what makes us work together on something often is not a technical challenge as much as it is a problem of how do people agree on what is supposed to be in this file format and how is it supposed to be implemented and how is it supposed to be interpreted because there can be multiple interpretations of it.
</details>

我坚信开放协议和通用文件格式是极为关键的一环。你可以想象这样一个未来：我们每个人都拥有属于自己的独立 Photoshop 复制品，但我们却再也无法互相传递文件，因为彼此之间的偏离已经太远了。这说到底还是归结为一点：人与人之间的协作难度依然一如既往。这在某种程度上拖慢了我们的步伐，对吧？

我认为有时很有必要抵制这种“直接甩给 Agent 解决”的诱惑，退后一步思考一下，这是否正是那种我们应当与其他人类共同协作来解决的问题。作为一个有开源背景的人，看到如今开源项目中人与人之间的协作变得如此之少，而产生海量 Fork 的项目却激增，这让我感触颇深——因为直接搞个 Fork 出来，比尝试把变更合并回上游要容易得多。

<details>
<summary>Original English</summary>
Um and I really think that these open protocols and file formats are really important aspect. Um you can imagine there is a future where we all have our own little Photoshop clones, but we'll no longer be able to send file formats to each other because we have diverged too much. Um and this really comes down to this part that collaboration between humans is as hard as it has ever been. And this is slowing us in a way down, right? Um and I think it's it's important to sometimes resist this temptation of just having the agent solve the problem and just taking a step back and figuring out if this is maybe one of those problems where we should be working together with other people. Um it is for me coming from an open source background fascinating to see how little actually human collaboration is happening in open source projects now and how many more projects end up with gazillions of forks because it's just easier to have a fork happen than to try to upstream changes.
</details>

所以我极力倡导：构建追求卓越的软件。我明白这很难。我想大家最近看到了形式化验证软件（verified software）的大爆发。很显然这本身难度极高，相关的技术栈目前也还没有完全成熟到开箱即用的地步；但我认为这确实是值得去发力推进的领域之一，看看它长远来看是否能帮助我们构建出更稳固的软件。

看到这么多人渴望构建在底层更轻快、内存利用率更高的软件，我真的非常欣慰，这是一个极好的趋势。多年以来我都深感沮丧：我的内存用量中，真正用在自认为有价值的事情上的比例竟是如此之低。而现在出现了一个明显的趋势，人们开始尝试用原生系统语言来重写软件，而不是单纯再做一个 Electron 壳。所有这些都是非常酷的发展，但在很多方面，它们依然是在我们之前时代所建立的技术成果之上添砖加瓦。我非常喜欢 Rust，也很高兴看到如今向构建内存安全软件靠拢的趋势。我想大家都见识过了优秀模型在挖掘安全隐患方面的表现，所以支持内存安全有着充分的理由。这也促使许多以前绝不会选择这门语言的人真正开始上手尝试，因为它带来的某些价值在当下近乎是“免费”获得的。

<details>
<summary>Original English</summary>
Um so I I want to make a very strong argument for uh building software that strives towards excellence. And I understand that this is hard. Um we have I think seen a pretty big explosion recently of verified software. Um it's also very clear that this is in itself hard. The the the technology stack is not right there yet where this works, but I think it is one of those areas where it's really worth pushing towards and seeing if this is maybe something that can help us over time creating more more stable software. Um I really I'm very happy with seeing so many people wanting to build fundamentally faster and more memory efficient software. I think it's a great development. Um for years I was very frustrated with um how little my RAM usage actually goes to things that I think are worthwhile. And now there's a significant trend of people trying to rebuild things in a native language rather than for instance just building another electron wrapper. So all of those things are really cool developments, um but they're in many ways still building up on technology that we have created before times. I really like Rust. I like that there is now a trend towards building memory safe software. I think you've probably all been exposed to what happens with yeah, good models finding security issues. So there's a strong argument towards that. Um and it it now has also led to people that would never have picked that language before to actually give it a try because it delivers some value that now can in quote come for free.
</details>

### Harness 架构演进：持久化、弹性调度与代码模式

在最后这部分，我想聊聊 Harness 能够发挥的作用。我这么说倒不是为了宣称“瞧，这就是我们选择的道路”，而是想给大家提供一些思路，探讨当我们推动任务向更长运行时间演进时，可能会遇到哪些挑战。

首先第一点：如果一个任务只需要运行两分钟，你是乐意守在旁边看着的。如果它崩溃了、提前退出了、没有执行完，或者你需要重启 Agent，你直接手动重启并让它继续跑就行了，对吧？在很长一段时间里，我们基本上都是在这样一种完全可以接受这种做法的环境中工作的。但如果你现在拥有自动化 Agent，需要在一夜之间处理成千上万个 Issue，你就希望 Agent 能够具备自我重启的能力。我们非常笃信“持久化 Agent”（durable agents）这一概念，同样也推崇持久化工作流——它们通过一种能够支持自主编排的方式来运行，你可以启动、停止、挂起并重新恢复它们。

这不仅是因为我们的任务运行周期变长了，更是因为我们现有的做法中存在大量低效环节。我们全都受限于算力，也都受限于推理成本；如果能在工作方式上更加智能一些，我认为会非常有价值，我也希望有更多人向这个方向努力。举例来说，如果你按原始 Token 计费，使用弹性调度（flex scheduling）可以获得相当可观的折扣。但这意味着可能整整几分钟内都不会有 Token 返回，对吧？所以在这种情况下，你会希望挂起你的 Agent，同时也挂起你的沙箱，避免白白浪费其他同样昂贵的资源。因此我认为，除了模型品质本身之外（毕竟现在的模型已经越来越强），我们可能需要重新思考一下如何更智能地利用这些计算资源。

<details>
<summary>Original English</summary>
Um on the last part I want to talk a little bit about maybe there is something by harness can do something and this is less so much for me to say hey here's the thing that a path that we are on as to give you some idea of maybe where some of the challenges are as we're pushing this task to be much more long running. Um the first one is if if if you have a task that only takes two minutes to run you're kind of willing to babysit it and if it breaks and it it ends early or it doesn't run to completion or you have to restart the agent to just restart it manually and tell it to continue. Right? So it's like we have we have largely been working in environment for quite a while where that was acceptable. If you now have automated agents running on thousands of issues overnight you want to have an agent actually be able to restart itself. Because we're pretty big believers on this concept of durable agents, also durable agents that create durable workflows when they orchestrate themselves in a way where you can start it, stop it, you can suspend it, you can bring it back. And this not just because we have this longer running tasks, but also because there's a lot of inefficiency in what we're doing and um we are all compute constrained, we are all constrained in terms of the cost of inference and being able to be a little bit more intelligent about how we're doing this. I think it's really interesting, and I wish more people would be pushing towards that. For instance, if you pay raw token costs, you get a pretty significant discount on flex scheduling. But that means that maybe for minutes no token is coming, right? And so then you want to suspend your agent, you want to suspend also your sandbox, and actually not waste the other resources that are also expensive. So this is one part where I do think beyond the quality of the models, because the models are getting so good now, we might want to rethink a little bit of how we are using these resources intelligently.
</details>

第二点：大家可能知道，在 Pi 刚推出的时候，核心理念很大程度上是“所有东西都可以通过 Bash 来运行”。直到现在，我们在很大程度上依然持有这一观点。但现在我们也观察到，人们涌现出编排 Sub-agent 的诉求，也渴望利用非大语言模型，例如决策模型或是像 Jeff 这样的分类模型。在这些场景下，你就必须开始组合工作流。我认为这种思路最初来源于 Cloudflare 的团队，也就是与其在代码上下文（Context）中强行塞入成千上万个工具，不如在 Bash 之外给 Agent 提供 JavaScript 的执行环境，让 Agent 原生要调用的所有工具调用都通过 JavaScript 来完成，从而实现更好的编排。

我认为在很多层面上，这已经从一开始的新奇探索，演变为了具有颠覆性实用价值的能力。这意味着 Harness 在很多情况下——这在 Codex 中已经明确实现，在 Pi 和目前的许多其他 Harness 中也都能做到——可以编排超大规模的工具调用，而无需经过低效的上下文窗口。这确实需要对现有的做法进行一番重新审视。同时，它也允许你使用分类模型。

<details>
<summary>Original English</summary>
And the second thing is um you probably know that when when when Pi came out, there was a pretty big motivation to say like bash is everything that you have to run. And this is still largely what we believe. But now we also see that there is an emergence of desire to orchestrate sub agents, a desire to use models which are not LLMs, like decision models or or classifier models like Jeff. And in those cases you need to start composing workflows. And this I think originally came from the folks from Cloudflare to say like in in instead of having thousands of tools being put into the code into the context, what if we just give the agent in addition to JavaScript in addition to bash JavaScript to run and have all the tool calls that the agent would natively do happen via JavaScript, and then you can orchestrate them better. And this has gone from a curiosity, I think in many ways, to something that is fundamentally shockingly useful. And this means that now the harness in many cases, and this is definitely the case already in Codex, you can do it in Pi and many other harnesses at this point, you can have the harness orchestrate very large invocations of tool calls without having to go through the inefficient context. And this does require a little bit of a rethinking of how you're doing things.
</details>

我认为这也是彻底改变我对某些技术拓展边界看法的另一大核心点：因为你不会因为缺少活跃的 KV Cache 而受到惩罚，而且这类分类模型既极其廉价，又非常迅速。对于某些以往因为成本过高或速度太慢而无法处理的特定问题，它们现在让你能够交给决策模型来解决。我认为各位可以这样来思考：当引入了代码模式，Harness 能够做的是创建一个轻量工作流，并在执行流程中设置决策分支点。比如，当你需要快速过筛 3000 条新涌入的客户支持工单，并在过程中做出一系列判定——比如是该派发给 Agent 来处理，还是需要向客户索取更多反馈——你可以让 Agent 动态生成一个按需定制的工作流，随后在其中的每一个 if 条件分支上，直接调用 Jeff 进行分类判断。这样一来，以往在编码 Agent 里需要耗费数小时才能处理的成千上万个 Issue，现在在极短的时间内就能一扫而空。

所以讲到这里，我想留给大家这样一个思考：现在我们有能力构建一切了，但也许我们不应该什么都做；相反，我认为我们应当真正去追求构建更加令人愉悦、并且在很多方面比以往更具雄心的软件。谢谢大家。

<details>
<summary>Original English</summary>
And it also allows you to to use classifier models. And I think this is the other big part that really changed how I was looking at how far I can push certain technology, because you're not being penalized for not having an active KV cache, um but they're also very cheap and very fast. And they allow you now to take certain problems that previously were just too expensive or too slow to do, to have a decision model do this. And the way I think you should be thinking on this is that when you have code mode, what the harness can do is it can create a little workflow that can have decision points along the way where if you for instance have to crunch through 3,000 incoming customer support requests and you have to make decisions along the way if this is being sent towards having an agent work on it, towards requiring more feedback from a customer, you can have the agent create basically an on demand workflow and then for every single if condition that it's doing, it's just going through Jeff. And then you can crunch through thousands of issues for very little time in no time in your coding agent that previously that would have taken you hours. Um so with this um I just want you to leave this idea. Now that we can build everything, maybe we should not, um but we should really I think push towards much more enjoyable and um in many ways much more ambitious software than we have been doing before. Thank you.
</details>