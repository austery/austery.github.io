---
author: AI Engineer
date: '2026-10-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DouK81O8R3o
speaker: AI Engineer
tags:
  - legacy-modernization
  - ai-agent
  - software-architecture
  - developer-productivity
title: 一天与1000美元Token：GEICO如何用AI作战室重构遗留代码
summary: GEICO资深参谋工程师Ford Prior分享了如何利用多智能体协作的“AI作战室”突破软件交付外循环瓶颈。通过结合Anthropic代码现代化插件与FleetKit框架，团队在一天内以1000美元Token预算对百万行遗留理赔系统完成端到端领域映射、发现生产缺陷并输出经全方位审批的迁移方案与API。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - GEICO
  - Anthropic
products_models:
  - Claude
media_books: []
status: evergreen
---
### 外循环瓶颈：当内循环提速后的全新挑战

在过去的几年里，感觉我们谈论的全部内容都是关于如何提高我们软件研发生命周期（SDLC）的速度。大家肯定都知道我在说什么。

具体来说，就是中间那个庞大的构建（build）环节，对吧？在那儿我们完成了大量的编码和脑力劳动。果不其然，至少在我工作的地方，那个步骤基本上已经被彻底抹去了，对吧？我们重新赢得了大量的时间。

但我认为——而且我也不是什么先知——完全能想象出这样一个未来：智能体在负责干活，而人类作为主管或高管在中间签字确认每个阶段的工作。

但是，我在 GEICO 工作，我们不是一家科技公司，而是一家风险管理公司。风险管理已经融入到了我们所做的一切之中，包括我们开发和交付软件的方式。因此，借用 Gene Kim 的概念，虽然我们看到这个“内循环”（inner loop）提速了，但我们发现自己似乎被困在了这个“外循环”（outer loop）的边界之内，也就是说，除了编码和构建之外发生的所有其他事情。

我们发现自己不禁在想，在一个外循环能够跟上内循环节奏的世界里，走出这道围墙之外的生活会是什么样子。所以，这就是一个关于我们如何“破局打破束缚”的故事，我今天演讲的目的就是为了给各位赋能，让你们也能做到同样的事情。

<details>
<summary>Original English</summary>

For the past couple years, feels like all we've been talking about is how to increase the velocity of our SDLC. Y'all know what I'm talking about.

And specifically this big fat build chunk in the middle, okay? Where we've been doing a lot of our coding and intellectual work. And sure enough, at least where I work, that step has basically been obliterated, right? And we've reclaimed a bunch of time.

But I think and I'm no prophet in imagining some future where agents are doing the work and humans are there in the middle as exec or as executives signing off on each stage.

But I work at Geico and we're not a tech company, we're a risk management company and risk management is baked into everything that we do, including the way we develop and deliver software. So while we've seen this inner loop speed up to use Gene Kim's concept, we find ourselves seemingly stuck within the bounds of this outer loop, which is to say everything else that happens other than the coding and the building.

>> [snorts]

>> And we find ourselves wondering what life might be like outside of these walls in a world where the outer loop keeps pace with the inner loop. So this is a story of how we broke free, as it were, and my intention with this talk is to power you guys to do the same.

</details>

### GEICO 理赔业务与重大重构的困境

当 GEICO 管理全美的汽车车队或其中的风险时，一旦路上发生了诸如事故之类的意外，我们就会产生所谓的“损失”（loss）。损失通常由我们的保单持有人报告，并演变成为一起“理赔”（claim）。理赔科技正是保单发挥效力的地方，让客户在受到最小干扰的情况下尽快重新上路，我们称之为“结案方案”（resolution）。

我是 Ford Prior，是 GEICO 理赔科技团队的资深参谋工程师兼技术布道师。我想我大概是伯克希尔·哈撒韦（Berkshire Hathaway）旗下唯一的技术布道师。但基本上这代表的意思是，在我们这个 300 人的工程师团队中，我们拥有大约 32 个过去常说的“双披萨团队”，每个团队都配有一名技术负责人以及对应的业务负责人。而我的职责就是在我们的 SDLC 中发掘并落地最佳实践。

我负责运营一个理赔创新实验室，我分享像今天这样的故事，是为了吸引世界上最优秀的工程师来到我们的问题空间。我们觉得这个领域非常有趣，更不用说它还是美国经济的重要组成部分。

那么，再多介绍一点关于我们如何开发软件的背景。就像许多组织一样，我们从语义化版本控制（semantic versioning）的角度来构想我们的工作。

大约 6 个月前，我们查看了手头的积压工作（backlogs），发现我们的工程师在完成最新的补丁修复或跟进最新的次要版本升级后，状态好时也只有 25% 甚至更少的带宽，能够投入到能让我们保持竞争力、领先竞争对手一步的重大变更（major changes）上。也就是从 V1 到 V2、再到 V3 的那种大版本工作。

因此，我们开始战略性地投资由 GEICO 管理的 AI 智能体，运行在各种框架（harnesses）上并调用各种模型，从而把从规格制定到部署的补丁及次要工作全部卸载出去。目标就是将这些工作重定向或转移开，让我们那些聪明的工程师能够专注于真正重要且让他们感到最有乐趣的事情上，也就是去推进重大版本工作。正如我刚才提到的，这正是我们保持竞争优势的关键所在。

<details>
<summary>Original English</summary>

Now when Geico manages America's fleet of automobiles or the risk therein and something happens on the road like an accident, we incur what we call loss, which is typically reported by one of our policy holders and it becomes a claim and claims technology is where the policy comes to life and gets the customer back on the road as quickly as possible with minimal disruption, which we call a resolution.

And I'm I'm [snorts] Ford Prior. I'm a senior staff engineer and tech evangelist embedded in the claims tech group at Geico. And I think I'm the only tech evangelist at Berkshire Hathaway, but basically what that means is within our 300 engineer group, we have like 32 pizza teams as we used to call them with a tech lead and counterpart for each business counterpart for each. And my job is to find and implement best practices in our SDLC.

I run a claims innovation lab, and I share stories like this one to attract the best engineers in the world to our problem space, which we find very interesting, not to mention important part of the American economy. So, a little bit more context in how we develop software. Um as many organizations do, we conceive of our work in terms of semantic versioning.

And about 6 months ago, we looked at our backlogs and found that our engineers, after they finished their latest patch or chased down the latest minor upgrade, had only 25% on a good day or less of their bandwidth to dedicate towards the major changes that keep us competitive, step ahead of the competition. That's like V1 to V2 to V3.

So, we began strategically investing in Geico managed AI agents on a variety of harnesses using a variety of models to offload that work all the way from spec to deployment for our patches and minor work. Um with the goal of redirecting or rerouting that work so that our engineers can stay our our brilliant engineers can stay focused on the stuff that matters and that they find most joyful, which is to do the major work. Which again, as I mentioned, is key to our competitive edge.

</details>

### 破局之道：多人 AI 原生作战室

好，这是目前的现状。但是当我们审视这项重大版本工作时，发现自己受制于协同能力——也就是能否将合适的人在合适的时间召集到同一间屋子里，在将重大工作推向生产环境所需的整个生命周期各阶段节点上做出正确决策的能力。

而且我们不仅缺乏这种协作能力，还缺少这种智能——这种随着我们了解并加深对问题空间的理解，将与问题空间相关的所有变量交织在一起的能力，包括事实核查、代码解析处理，基本上就是所有需要在决策出现时迅速提供洞见的工作。

而这才是最终赋予我们将这些重大变更推向市场的信心所在。所以说，这是协作与智能两方面的缺失。在面对重大变更的规模时，这两点我们全都不具备。

因此，为了解决这个问题，我们创建了一个**多人协作的 AI 原生作战室**（multiplayer AI-native war room）。

它由以下几部分组成：一份与该主题相关的核心决策者和领域专家（SME）花名册；一个负责操作驾驭这些昂贵 AI 工具的“驾驶员”（driver）；以及一套 AI 原生生产力套件——其中包括用于日常沟通讨论的通讯渠道、一个交互式设计工作台（我不能透露供应商名称，但大家完全可以大胆猜一猜）用于所有协同要素，然后显然还有我们的代码仓库。

所有这些都被接入到一个由工作流、智能体技能（agent skills）、MCP、企业级 MCP 以及负责承担繁重任务、事实核查与信息综合的智能体集群所组成的强大组合中。

<details>
<summary>Original English</summary>

Okay, so this is current state. But as we look at this major work, we find ourselves rate-limited by our ability to collaborate in rooms full of the right individuals summoned at the right time to make the right decisions at every interval in whatever life cycle would need to happen in order to get get get the major work to prod.

And not only are we missing the ability to collaborate, but we're also missing this intelligence, this ability to weave together all the variables relevant to the problem space as we learn it and deepen our understanding of it, including the fact checking, the code crunching, basically everything that needs to happen to serve up the insights as quickly as the decisions come up.

And that's what ultimately gives us the confidence to bring those major changes to market. Okay, so it's collaboration and intelligence. We're missing both of those at the major change scale.

So to solve for this, we created a multiplayer AI-native war room.

And it consists of a roster of key decision makers and subject matter experts relevant to the topic, a driver to wield these expensive AI tools, and an AI-native productivity suite, um which includes our comms channels for all the chatter, an interactive design studio. I can't mention the vendor name, but y'all can take a wild guess. Um to uh for all of our our collaborative elements, and then obviously we have our code repositories.

And all of these are wired into a powerful combination of workflows, agent skills, MCPs, enterprise MCPs, um and these agent fleets to do the heavy lifting, back checking, synthesis, etc.

</details>

### 一天与 1000 美元 Token 的现代化实验

当时我提出的问题是：我们如何才能加快为我们的遗留核心功能交付可供智能体调用的 API（agent-callable APIs）？

补充一些背景信息：我们的遗留理赔系统包含数百万行代码，明白吧？我们在构建这种深度上下文时，只需构建一次便能反复复用。这是额外的背景。而我当时下的注是：手握 1000 美元的 AI Token，我们可以在一天之内将一个领域端到端地梳理映射完毕，包括业务拓扑的图谱表示、我们遗留系统中所有复杂的代码以及介于两者之间的所有内容。

同时，我们能让智能体发现并提出一项严肃的变更——在我们的案例中，我们将其范围限定为针对遗留理赔系统提供一个可供智能体调用的 API。

并且还要将整个成果部署到我们的技能智能体平台上，并在下午 4:00 准时向我的老板进行运行演示。

于是我给自己施加了很大压力。我们在三个不同的代码现代化任务中，将这个实验运行了三次。这里用到的分类法——提升（uplift）、改造（transform）、重构再造（reimagine）——来自 Anthropic 的代码现代化插件，我稍后会具体讲到。

我们经历的故事是：首先，我们把目光投向了租车业务领域（rentals domain），这是一个非常简单的领域，涵盖了当各位的主力用车发生事故时为你们提供代步租车背后的所有技术。我们针对同一套技术实现了一个较新的版本，这也就是所谓的“提升”，并且拓展了现有的 API。

在这一案例中有一个非常有趣的故事：智能体采用了一些非常巧妙的数据查找与提炼流程，推算出如果我们把几个数据点关联起来，通过向客户提供最新的租车信息，每月就能为我们自己节省 8500 次呼叫。

这是我们运行的第一个实验。第二个实验是对定损领域（damages domain）的“改造”。

定损可以说是我们最复杂的——不，抱歉，我看下笔记。定损领域是指我们如何为上报的损失标上具体的美元金额。

所以在这种情况下，我们构建了一组新的可供智能体调用的 API，从而解锁了一个需要定损数据的更大规模工作流。

最后，我们对全损报废领域（salvage domain）进行了“重构再造”，这可以说是三者中最复杂的。它基本上涵盖了车辆被判定全损（totaled）后发生的所有流程。

在这个案例中，我们产出了一份经过全面审查的迁移计划，包含 API 规范和设计原型图，并且——这是最关键的部分——得到了产品和技术各层级团队的正式核准与开绿灯批准。这完全就是一份经过全面审查、可直接落地执行的项目方案；各位都知道，能让所有人达成共识（包括技术细节）本身就是一座里程碑。

坦白讲，在这一案例中，智能体对业务领域的理解极其透彻。而且在全损报废的工作中发生了一个故事：它甚至发现了一个生产环境缺陷（prod bug）。具体的我不能再多透露了。

<details>
<summary>Original English</summary>

So my question was, how might we accelerate the delivery of agent-callable APIs for our legacy core capabilities?

>> [snorts]

>> And for context, our legacy claim systems is like millions of lines of code, okay? So um and the deep context that we're trying to build here um gets built once and then can be reused. So that's just some additional context, but my bet was that with a thousand dollars in hand of AI tokens in one day we could map out one domain end-to-end including like graph representations of the business topology, all of the complex code um in our legacy systems and everything in between.

And we can have the agent find and propose one serious change um which in our case we scoped down to an agent callable API into our legacy claim systems.

And have the whole thing deployed to our skills agent platform and running for an a a a demo to my boss at 4:00 p.m.

So, I put the pressure on myself um but we ran this experiment three different times across three different code modernization missions. Um and this little taxonomy here uplift, transform, reimagine is from the Anthropic code modernization plugin which I'll touch on in a minute. Um but the story is um that we first we looked at our rentals domain which is a really simple one um that is like all the tech behind getting you guys your rental cars when your primary car gets in an accident. And we implemented a newer version of the same tech which is again the definition of uplift and we extended an existing API.

And in this case it was an interesting story because the agent used some uh interesting um uh process to find and distill data to figure out that we could connect a couple dots and save ourselves eight and a half thousand calls per month by giving the customer up-to-date rental information.

Um so that was the first experiment that we ran um and then the second one was transformation of our damages domain.

And damages is like arguably our most complex No, sorry. Damages I'm meaning from notes here. Damage domain is how we put dollar signs on a reported loss.

And so for this case we built in a set of new agent callable APIs to unlock a larger workflow that needed damages data.

>> [snorts]

>> And then lastly, we reimagined our salvage domain, which is arguably the most complex of the three.

Um it's basically everything that happens when your car's totaled.

Um and in this case, we produced a fully vetted migration plan with API specs and design mock-ups, ratified, and this is the most important part, green-lit by product and tech at every level. Okay, so it's like a fully vetted project plan that's ready to be implemented, which is like as you guys know is like that's like a a milestone unto itself, getting everybody on the same page.

Um including the technical details.

Um and honestly, like in this case, it understood the domains really well. And um in this and the the story with the salvage work was that it found a prod bug. I can't talk about more, but it was

</details>

### 系统架构：FleetKit 与代码现代化插件

大家可能对这套系统究竟是如何运作的细节感到好奇。其实，主要是由 Anthropic 的朋友们提供了一堆东西，然后我们这边也提供了一大批东西。

在左边，我们有运行框架、模型、一个叫做 FleetKit 的东西（我稍后会解释），以及执行代码现代化任务的插件。这就是左边由供应商带来的部分。顺便说一句，我们完全可以用另一家供应商、另一个模型或另一个框架来替换掉其中的任何一部分。而在右侧，则是我们无法替换的部分。

这就是 GEICO 的全部家当，而且我们需要大量的输入。我们在知识库中准备了上下文，包括软件规范标准以及我们不得不进行的所有历史决策“考古”；列出了智能体可以在我机器上访问的工具清单，以及针对智能体如何使用这些工具的指令。

我们还有“方法”（methods）——我这里讲的顺序有点乱——但我们有各种方法，本质上代表了我们所有的技能，以及我们开发软件时那种独特的、高度优化的特定领域方式，很可能与各位的做法有所不同。最后是“裁决”（judgment），也就是谁有权在哪个质量门禁（gate）做出何种决定，对吧？这既涵盖领域专家的视角，也涵盖决策领导层的视角。

我们把它们归纳在两个代码仓库中。这使得智能体能够对其进行补充和修正，人类同样也可以参与其中。

但是 AI 大规模运行起来是极其昂贵的。所以我们需要一个集群管理器（fleet manager），一个相当于拥有博士水平的舰队管理者。

这是我们与 Anthropic 的一次合作成果。目前它还没有开源，但我今天可以分享它的工作原理，希望大家能搭建出自己的版本，因为这并不是什么高不可攀的尖端科技。

FleetKit 是一套紧凑、结构化的规则、协议和指令集，全部用 Markdown 编写。它针对 Claude 框架（特别是 Fable）进行了优化，并围绕架构改造的核心任务进行设计。

正如大家所猜到的，这种机制在以前的一些模型迭代版本中根本无法跑通。我猜大概需要像 Opus 48 及以后的模型才能够应对这种级别的操控引导。因为这相当于在系统提示词之上又拔高了一层，对吧？这是智能体必须严格遵守的规则。

它的运作非常简单：接收一个目标，将其分解拆割，派出主导智能体（leaders）去进行所有的前期调研并确定技术方案。

然后它会把所有内容放入这样一个“有人在回路中”（human-in-the-loop）的队列中。比如你可以使用 GitHub issues，让人类能够在上面发表评论和审批，其他智能体也可以在其中补充更多上下文。

当从审批角度看一切都准备就绪时，它就会派遣构建智能体（builders）去完成剩下的工作。

在这个过程中，我们使用了 beads。我不确定各位是否了解 beads，但 beads 能够帮助智能体在各自的智能体空间内对所有事物保持追踪。

最终的目标是产出我们所谓的“实质性变更”（material change），也就是向我们的系统提交一个变更请求，或者向代码仓库提交代码修改。

其核心理念在于：开发软件的形态开始变得不再像是在画布上随意涂抹，而更像是在工厂流水线中规范作业。

<details>
<summary>Original English</summary>

Um so anyways, uh you may be curious about kind of what like a little bit more detail into how this all worked. Um really like we had our friends at Anthropic who provided a bunch of stuff, and then we had us that provided a lot of stuff. So on the left here, we have um [snorts] the harness, the model, this thing called FleetKit, which I'll explain in just a moment, and this plug-in that did code modernization tasks. That's on the left, brought by the vendor. Okay, we could replace any of that, by the way, with another vendor, another model, another framework, etc. And on the right was the stuff that we can't replace.

This is everything GEICO, and we need a ton of it. We had context in our knowledge base, including software standards and all of this past decision archaeology we had to do, list of tools that the agent could access on my machine, and instructions for the agents on how to use it. We had the methods. I'm doing these out of order here, but we had methods, which is essentially like all of our skills and all of the the the kind of the quirky domain-specific, highly optimized way that we develop software, probably different from the way you guys do it. Um and um and lastly, judgment, which is like who can decide what and at what gate, right? So both from the subject matter expert point of view and from the um the uh decision-maker leadership point of view.

Um and um we grouped them into two repos. and why in a minute, but that allowed us to ver- allows us to have the agents add to it and correct it um and also humans to do the same.

Um but that AI, and this is kind of one of the interesting parts, uh is is expensive, right, to run at scale. And so, we needed a fleet manager, like a PhD-level fleet manager.

And this was a bit of a collaboration with uh with Anthropic, and it isn't open source yet, but I can share how it works today and hopes that you guys can construct your own version cuz it's not rocket science.

So, FleetKit is this tight structured collection of rules, protocols, and instructions all written in markdown. Optimized for the Claude harness, specifically Fable, and designed around the core task of architecture transformation.

Um and as you guys can kind of guess, like this type of thing doesn't really work with some of the previous iterations of models. I think like Opus 48 and beyond I I I would I would guess is like something that could handle this type of like uh steering. Um cuz it's like one level above um the actual system prompting, right? This is like rules that it has to follow, the agent has to follow.

Um and um it's pretty simple. Takes a goal, breaks it down, dispatches leaders to do all the research, and decide about the approach.

It puts everything into this like human-in-the-loop queue. You could use GitHub issues, for example, something that the humans can comment on and approve or that other agents can add more context to.

And then when everything looks tight from a approval standpoint, it dispatches builders to do the rest.

And in this case, we use beads. I'm not sure if y'all know about beads, but beads kind of helps the agents keep track everything um within their own agent space.

Um and um ultimately, the goal is to produce what we call a material change, which is like a a change request into our systems or code change into our code repositories.

And the ultimate like idea with this though is that like developing software looks less like playing in a canvas and more like working in a factory.

</details>

### 作战室工作流程与人机协同产物

我得加快速度了。最终在左边大家可以看到这三个代码仓库。它们包含了 FleetKit 运行所需的全部内容，包括 FleetKit 自身的源代码。

顺便提一句，所有这些幻灯片都可以在一篇博文中找到，我会在最后附上链接。现场灯光太刺眼，我看不清是谁在拍照，但我想告诉大家，如果你想查看我这里展示的图表可视化，它们全都在今天发布的博文里，我在幻灯片末尾附上了链接。

总之，所有这些启动后，都会被拉入一个带有插件的 Cloud Code 会话中，插件被调用，你赋予它一项使命。它会在我们的通讯平台上认领或创建一个 Slack 频道。这个使命频道就是大家交流的地方。所有作战室成员，即与该项目决策相关的人员，都会被邀请进来。

每当智能体按照其九步流程达成一个里程碑时，就会生成两类产物之一。右边标有“作战室”的地方，就是它能够根据花名册直接 @ 呼叫具体人员的位置。例如，如果它缺少某些产品细节，它会查出产品端由谁负责，并在频道中直接提及该负责人。

除此之外，它还会创建一些非常出色的 HTML 工作表（通过 Claude Artifacts 生成）。人们可以在里面填报信息，内容会自动保存，以此来填补信息空白。它还会创建设计文档，包括此前根本不存在的复杂架构可视化图表。团队收到这些图表后非常兴奋，因为事后可以一直保留使用。我们随后可以进行编辑，然后智能体可以重新读取我们编辑过的设计文档（比如 draw.io 或 Figma 文件），所有这些内容又会被重新吸收到会话之中。

今年夏天，如果你偶然走进我们位于弗吉尼亚州里士满的作战室（我就来自那里），你就会看到要么是一块巨大的 Cloud Code 屏幕，周围围了一群人；要么就是眼前的这两块屏幕之一。左边是我们需要填写的需求工作表；右边则是我们的图表绘制工具之一。

整套方案的核心精髓、也是最令我惊喜的地方在于：这些产物的质量极其高。所以大家从来不会去质疑“为什么智能体总问一些愚蠢的问题？”反而会惊叹：“哇，这真是一个绝妙的问题，我们以前从未想过去识别业务或技术层面的这个边界用例。”

正如我所说，团队在项目结束后能够继续保留这些设计资产，很多时候智能体梳理出来的架构图，正是过去大家根本没时间去画的，因为各位都知道，并不是每位工程师都喜欢画架构图。

<details>
<summary>Original English</summary>

Um Okay, I need to go faster. Uh so ultimately on the left here you see these three repositories. They contain everything that Fleet Kit needs to run including the Fleet Kit source.

Um and by the way, all of these slides are available on the blog post that I'll link at the very end. I can't tell with these lights who's taking pictures, but I just want to let you all know that if you want to look at the uh the the visualizations that I'm showing here, they're all in a blog post that was released today and I link it at the end of the slides. So anyway, um so anyway, all this boots up, gets pulled into a cloud cloud code session with a plugin, gets invoked, and you give it a mission. It adopts or creates a Slack channel um or a in our comms platform. And um and then that's that that that mission channel is where everyone communicates. All the war room members, the people who are relevant to the decisions in the project are invited. And um every time the agent reaches a milestone um as it follows its nine-step process, it creates one of two artifacts. Um and by the way, on the right there where it says war room, that's where it like it can ping individual people based on the roster. So for example, if it's missing missing some product details, it'll figure out who owns that from a product perspective and mention that individual person. Um but other than that, it creates these worksheets that are like actually really well-done HTML using cloud artifacts. People can fill them out. They're automatically saved. Um and that's to fill the gaps. And then also creates design documents including like these like complex visualizations of our architecture that didn't exist before um that teams were delighted to get cuz they kept them afterwards um that we can then edit and then the agent can then reread our edited like uh design document like a draw.io or Figma, and then all that gets that all that gets slurped back up into the the um the session.

Okay. Um and if you had stumbled into our war room in Richmond, [snorts] Virginia, which is where I'm from, um uh this summer you would have seen either a big cloud code screen um with a bunch of people huddled around it or one of these two screens here. On the left is like a product worksheet that we had to fill out. And then on the right um there it's like one of our our diagramming tools. And so like the big gist with this and the thing that was so delightful for me is that these were really high-quality artifacts. So, there wasn't like ever a question of like why is the agent asking me dumb questions? It was like, "Wow, that's actually a great question that we've never thought about identifying an edge case either in the business or with the technology."

Um and then the design artifacts, like I said, the teams could keep them afterwards and oftentimes they were mapping stuff that just no one had taken the time to do cuz as you all as you all know not every engineer loves doing diagrams.

</details>

### 云端与本地双轨智能体及九步现代化流程

好，我跳过一些内容继续讲，因为我只剩大概 3 分钟了。这些作战室工具简单来说包含两类智能体：

一类是我们所谓的“代码深潜”（code dives）智能体，它在云端运行，负责大量的代码分析解析，并在我们遗留的领域特定语言（DSL）之上构建图谱。

另一类是在本地运行的本地智能体，它可以访问我笔记本电脑上的所有 MCP 服务。其中很多还没有上生产环境，是高度针对我们的企业业务场景优化的，能够呈现出极具价值的数据，包括被深潜分析的代码库的代码块版本。

我向智能体提供了一个绑定文件（bindings file），用以描述我机器上装了什么、如何运作以及如何将其映射到 FleetKit 的工作中。大家可以看到内置的各种 MCP 服务器。

快速提一下这个代码现代化插件，它是整个系统的核心。里面的内容我认为各位会觉得很有趣，我鼓励大家在演讲结束后深入了解以获取更多信息。

最后，驱动者的笔记本电脑（也就是我的笔记本）就是运行环境。我需要执行九个步骤：从引导（booting）步骤开始，之后紧跟八个步骤。

我希望大家能从这张信息量极大的幻灯片中了解的是：左侧全部是从代码现代化插件中分叉（fork）出来的步骤。我们根据自身需求对其进行了改造适配，我也鼓励所有人根据实际情况这么做。右边那些橙色的元素则是生成的各种工作表，这些都是需要人工审批的。

因此，在我们推进代码现代化的过程中，你可以清楚地看到前期有大量的人工输入，到了后期则越来越少，而核心支撑正是这个代码现代化插件。

还有一个很有意思的细节，这也是代码现代化插件具备的功能：它会执行确定性分析（deterministic analysis），核查前一步骤是否成功创建了所需的产物（包括具体的文件）。

<details>
<summary>Original English</summary>

Okay, I'm skipping stuff here, but we're going to keep moving cuz I got like 3 minutes. Um these war room tools um just really simply uh basically there's two types of agents, the code dives that we called them um where it did lots of code crunching and graphing over of our legacy legacy domain-specific languages. Um that happened in the cloud and then we had local agents running that had access to all of my laptop all the MCPs on my laptop, uh many of which were not in production yet, and enterprise-specific, highly optimized for our problem space um and that could surface really viable data including like chunked versions of the code bases that were being dived. So, um there's there's a bindings file that I gave the agent to basically describe what's on my machine, how it works, and how to map it to the fleet kit work. Um and you can see the built-ins, MCP servers. The really quick, the code monetization plugin um this is at the heart of the whole thing. And what's inside of it uh I think uh you guys will find somewhat interesting um and I would encourage you to to look into it after the fact after this presentation to get more information. Um and I'm going to I'm going to keep moving here. Um ultimately, the driver's laptop, my laptop, was the runtime, okay? So, I had to run nine steps that are that are um started with the booting step, so eight steps after that.

And what I want you all to take from this super busy slide is that on the left here, those were all steps forked from the code mod plugin. Okay, so we adapted it to our needs as I would would encourage anyone to do. And on the right, those orange colored elements are worksheets that were created. So that was going to require human approval. And so as we did this like modernization journey, you can see how there's a lot of human input in the beginning, less than on the on the end, and how the core of it was this code modernization plugin.

And uh just an interesting detail, and this is something that the code modernization plugin does is it does like a deterministic analysis of like did the previous step create the artifacts that it needed to, including a file.

</details>

### 实战经验与未来展望：让人类选择下一座山头

总结一些有趣的经验教训。首先，我显然消耗了海量的 Token。

别让运行在 Fable 上的 Claude 去设置定时任务（crons）来检查进度，因为它每次都会直接唤起一个全新的 Fable 会话，瞬间就把你的预算烧个精光。

另外一些值得注意的收获与 Prompt 缓存有关，其利用率和收益远超我的预期。此外还有一些子智能体的奇怪行为。

但最有趣的事情之一是：在我们完成了所有上下文构建、并将这些智能体派发出去编写我们复杂的遗留代码之后，我们拿最近编写的现有代码作为黄金参考标准（golden data）进行了基准评测，结果发现 Sonnet 3.5 写出来的代码和 Fable 一样好，甚至可能更好。所以说，模型选型至关重要。

展望未来，在我看来，强化质量门禁的强制执行（enhanced gate enforcement）将是我们最大的收益点。我们在框架内部的决策模型以及模型选择框架方面也有一些令人兴奋的更新要做。

此外，我们当时的上下文基本全都是 Markdown 文件。我们并没有什么复杂的图谱化手段，没有用上诸如 Graphify 或 Obsidian 之类的高级工具。如果大家在会后找到我，我非常渴望听取各位在这方面的建议——怎样才能有更优化的方式去检索和审视用于为作战室提供输入的海量上下文。

最后一点，是将音频作为数据源。我非常希望只要打开录音设备，就能将我们开会时的讨论自动转录下来；但在实际操作中，我只能坐在那里疯狂地手动记录会议期间发生的所有内容。这相当让人分心，而且我敢肯定自己遗漏了大量细节。我们需要一种更低损耗的方式来吸纳作战室中的输入。

最后，如何将这套模式在整个组织中推广普及？各位不妨在自己的组织中找一个不知道该如何做决策的团队，把这套方案部署进去、亲自驾驭它、控制好成本，让它变成你们自己的工具。

在 GEICO，随着这些智能体不断向上爬坡寻优（hill climbing）、寻找更好的做事方式，我们正在探索究竟该把人类放在流程的哪个环节。我们怎样才能让我们最优秀的顶尖工程师获得如同神启般的灵感，并在智能体攻克第一座山头的同时，由人类来为它们挑选下一座要去征服的山头。

好的，我的分享就到这里。我们已经成功突破了外循环的束缚，现在轮到各位了。

这是博客的链接，欢迎大家拍照。感谢各位的时间。

<details>
<summary>Original English</summary>

So, some interesting lessons. Um obviously I burned a lot of uh burned a lot of tokens.

>> [laughter]

>> Um and um one of just as a little takeaway, do not let uh Claude running Fable set up crons to check on work uh because you'll it'll just launch a Claude uh a Fable session each time and burn your budget immediately. Um but um some other interesting takeaways we had were relevant to prompt caching, um which was way higher than I thought it would be. And then some quirky subagent behavior. But one of the interesting things was is like after we did all the context building and how these agents dispatched to like write our complex legacy code, we ran benchmarks um against like using our existing code recently written as the golden data and found out that Fable or uh Sonnet 5.5 wrote it just as good as if not better than Fable. So, um model selection for the win. Um and then looking forward, um I think you know, uh enhanced gate enforcement is going to be the biggest win that we have um in my mind at least.

Um we also have some interesting updates to make with decision models within our harness um and within the our model selection harness framework. And then um our our like to our context was just like markdown files, y'all. Like we didn't really have any complex way to graph things out. Like we weren't using anything fancy with a um like um like graphify or um obsidian. I mean any of these I mean honestly if you guys find me afterwards, I love your input on this, but like a more optimized way to do search and uh and look at all that context that we're using to inform this war room. Um and then lastly um audio as a data source. Like I want to turn a recorder on and have these conversations we have like automatically transcribed, but I had to like instead sit there and furiously write down all the notes that were happening during these meetings. Um and so that was kind of like a distracting thing that I think and I'm sure I lost a bunch.

Um so a less lossy way to incorporate the um inputs from the war room. And then lastly, how can we deploy this thing across the organization?

Um y'all find some group in your organization that doesn't know how to make decisions, deploy this, drive it, control the cost, make it yours.

And at GEICO, we're like trying to figure out how as these agents are hill climbing and figuring out better ways to do things, where can we put humans in the loop? And right, how can we like put our best brightest engineers who are receiving genius divine intervention as it were and have them pick the next hill as the agents climb the first one.

All right, and that is it. Um we broke free of our outer loop. Now it's your turn.

>> [laughter]

>> Uh and that's the blog that you guys can take a picture of um if you'd like. All right, thanks for your time.

>> [applause]

</details>