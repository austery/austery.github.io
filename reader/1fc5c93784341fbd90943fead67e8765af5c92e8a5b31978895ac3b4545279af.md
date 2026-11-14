---
author: AI Engineer
date: '2026-10-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Ve2bAarPA2I
speaker: AI Engineer
tags:
  - developer-productivity
  - engineering-management
  - software-metrics
  - empirical-software-engineering
title: 更好的模型救不了研发团队：影响工程产出的真正杠杆
summary: Jellyfish 的 AI 与研究负责人 Nicholas Arcolano 基于数万名工程师的遥测数据分析发现，AI 工具与底层模型对 PR 产出差异的解释力不足 1%，而工程技能运用、Token 消耗量、组织环境及工程师个人能力才是决定研发效能的核心杠杆。
insight: ''
draft: true
series: ''
category: software-development
area: tech-engineering
project: []
people: []
companies_orgs:
  - Jellyfish
products_models:
  - Cursor
  - Grok
  - Claude Code
media_books: []
status: evergreen
---
### 高尔夫球杆的启示：技术在进步，但问题出在挥杆者吗？

我是 Nicholas Arcolano，Jellyfish 的 AI 与研究负责人。很高兴再次回到 AI Engineer。今天我想聊聊，如果你使用 AI 没有得到预期的结果，很有可能问题其实不在于模型，而在于你自己。

既然我们身处领导力分论坛，而且切合这里的财务主题，我们先从一个高尔夫球的类比开始，这似乎很应景。现场有打高尔夫的吗？有球友吗？有谁打吗？

如果有的话，好吧。如果你不打高尔夫，请多包涵；如果你打高尔夫，我也表示同情，因为这是一项非常折磨人的运动。我很喜欢高尔夫，但我打得很烂。承认自己球技差算是这种文化的一部分，但我确实打得很烂。当你在球场上时，你只希望能摆脱那种痛苦。你脑子里冒出的一个念头往往是：天哪，我是不是换套更好的球杆就行了？那样打起来不就更容易了吗？然后你找了个教练，教练却说：不，问题出在你身上，你不需要更好的球杆，关键在于基本功。不过，我是一个搞数据的人，所以我想：这真的是真的吗？

从数据来看，球杆确实起到了作用，球杆确实变好了。你们现在看到的这张图表，是美巡赛（PGA Tour）从 1980 年至今的平均开球距离。在 1980 年——这让我很吃惊，我以前确实不知道——平均开球距离只有 257 码。我也能把球打出那么远，而正如我前面提到的，我是个非常糟糕的高尔夫球手。自 1980 年以来，这个距离增长了大约 20%。证明球杆确实起作用的一个证据是：在 2000 年左右进入实心球时代（solid core ball era），发生了一系列技术变革，开球距离几乎在那一瞬间就激增了大约 15 码。所以，职业球员并不是在那短短三年内奇迹般地变厉害了，那完全是技术驱动的结果。

这张图表让我想起了我们在模型前沿（model frontier）上看到的情景。我们目睹了模型持续不断地变得越来越强。这是来自 Artificial Analysis 的图表，我猜大家都看过其中的一张或很多张，并且每当新模型发布时都会去查阅。所以，模型确实变得越来越好。

我认为这是毫无争议的。我们现在能做到的事情，在一年前根本无法做到。所以，模型至关重要。对吧？是这样吗？

<details>
<summary>Original English</summary>

[music]

>> I'm I'm Nicholas Arcolano. I'm the head of AI and research at Jellyfish. It's great to be back here at AI Engineer. And today I want to talk about why if you're not getting the outcomes that you want with AI, uh chances are it's actually not the model, the the problem is you.

Um since we're here, uh you know, we're doing this this finance theme thing in the leadership track, we're going to start with a golf analogy. Seems appropriate.

Uh is anybody here a golfer? Any golfers? Anybody?

If you, okay. Um so yeah, I if you don't golf, bear with me. I apologize. If if you do golf, I also apologize. It's a very painful sport. Um I love golf. Uh I'm a bad golfer. Um it's part of the culture to say you're a bad golfer, but I I genuinely am a bad golfer. And when you're out there, you just want to make the pain go away. And one of the things you think of is like, oh, good should I just buy better clubs, right? That would make this easier. Uh and then you get an instructor and he's like, no, like you're the problem. You don't need better clubs, right? Uh it's about the fundamentals. But, you know, I'm a I'm a data guy, so I'm like, I don't I don't know. Is that really true?

Uh if you look at the data, like clubs matter. Clubs have gotten better. So, what you're looking at here, this is the average driving distance for the PGA tour uh from 1980 to the present. In 1980, I was shocked. I actually didn't know this. The average was 257 yd. Like I've hit the ball that far. And as I mentioned, I'm a terrible golfer. Uh so it's gone up about 20% since 1980. And you know, one bit of evidence that the clubs matter is uh this solid core ball era thing in the middle by uh 2000. A bunch of techno- technological changes happened, and there was like a 15-yard bump right at that time. So, people didn't magically get better over that 3-year span, like that was all technology-driven.

And this uh chart reminded me a lot of what we're seeing with the model frontier, right? We're seeing the steady advance of models getting better and better. This is a chart from artificial analysis. I assume everyone has seen one or many of these and checks them every time a new model comes out, right? So, the models have gotten better and better.

Um I think that's uncontroversial. We can do things that we just could not do a year ago, right? So, the models matter a lot.

Right? Yes?

</details>

---

### Grok 自然实验：模型切换并未带来产出变化

额，我不知道。这很有意思。我在一家叫 Jellyfish 的公司工作。我们将 AI 编程工具和 Agent 遥测数据与工程工作流数据、工程交付成果关联起来。我们拥有同类中规模最大的数据集，覆盖数十万名开发者和大约 1,300 家公司。我们一直在追踪他们在软件开发领域中使用 AI 所做的一切尝试。

我在我们的数据中注意到了一件事。这是大约在 SpaceX 宣布收购 Cursor 那段时间的数据，我们注意到 Grok 的使用量出现了激增，这是我们见过的规模最大的模型迁移，其转变速度远快于普通工程师根据个人偏好去为工作寻找最佳模型的自然过程。当我们深入探究时发现，当时 Cursor 在界面上做了很多调整，比如在 UI 中强推 Grok，并改变了自动模式（auto mode）的工作机制。因此，它的使用量迅速暴涨。作为数据科学家，令人兴奋的是这构成了一个所谓的“自然实验”（natural experiment）。存在这样一个外部冲击，那么一个很自然要问的问题就是：结果发生了什么？例如，产出改变了吗？

大家在图表上看到的，是每位工程师合并 PR 数量的变化情况。在我刚才展示的那段时间跨度内，这里的每一个点都代表一位工程师。X 轴代表他们的模型使用份额中从不使用 Grok 到使用 Grok 的比例，范围从 0 到 100%。Y 轴是他们相对于同公司同事的 PR 吞吐量相对变化。而这里得出的结论却是一个“非结论”（non-story）：数据散点完全聚集在零周围，不存在统计学上的相关性。产出并没有改变。把所有人都推向 Grok，实际上没有任何影响。

走出这个实验后我感到很困惑，我想弄清楚：模型到底有多重要？如果它并不那么重要，那么真正起决定作用的因素又是什么？

<details>
<summary>Original English</summary>

Well, I So, I don't know. The So, this is interesting, right? So, I work um I work at this company called Jellyfish. Uh we uh join AI coding tool and agent telemetry with engineering workflow data, engineering outcomes. Uh we have the largest data set of its kind, hundreds of thousands of developers, about 1,300 companies. And we're tracking sort of all the things they're doing with AI uh in the development space.

And one thing that I noticed in our data is um this is data from around the time when uh SpaceX announced its acquisition of Cursor, and we noticed uh a huge bump in Grok usage uh and the biggest model change that we've ever seen, far faster than just normal engineers sort of changing their preferences and trying to seek out the best model for the job. And when we dug into it, what happened was Cursor was doing a lot of things with the UI, sort of promoting Grok up in the uh up in the UI, changing how auto mode worked. And so, um you know, it it shot up very fast, and what was exciting about this as being a a data scientist is this is what we call uh kind of a natural experiment. There was this external shock, and a natural question to ask would be, well, what what happened? Right? Did output change, for instance?

So, what you're looking at here on this chart, this is change in merged PRs per engineer. And so, over that time span I showed you, every dot here is an engineer. And the x-axis is how much of their model share went from not using Grok to using Grok on a scale from 0 to 100%. The y-axis is the relative change in their PR throughput relative to their colleagues at the same company. And the story here is a non-story. There's the the cloud sort of center around zero. There's no statistical correlation. Output didn't change. Sort of shunting everyone to Grok didn't really matter.

So, I left this experiment confused and wanting to know how much does the model matter. And if it doesn't matter much, what are the other things that do actually matter?

</details>

---

### 解构研发吞吐量：影响因子的统计学地图

这就是我们在接下来的演讲中要探讨的内容。

我们接下来的做法是：继续聚焦于“每位工程师每周合并的 PR 数量”这一产出指标。我们将使用一个精选数据集，这是我们数据的子集，包含了完成该实验所需的全部维度：来自 447 家公司的约 50,000 名工程师，涵盖今年 Cursor 和 Claude Code 用户的行为数据。以下是相关的几个关键维度：

首先是**工具**。我们将测试框架（harness）和模型放在一起，因为它们紧密交织。这就像你的高尔夫球杆。

其次是你**使用它的熟练程度**。这里指的是 Skill 的使用、Cursor 规则（cursor rules）、框架定制，以及我们作为 AI 工程师为了更好地使用这些工具而摸索出的各种诀窍。在高尔夫球里的对应物，就是懂得如何把球从沙坑里打出来——这不是与生俱来的本能，而是你必须后天习得的技巧。

接着是你**使用了多少**。这与前面的因素独立开来，纯粹是 Token 的原始消耗量。对应高尔夫，就是你在球场上泡的时间。

然后是**外部环境因素**，即你在哪里工作。包括你的公司和你的团队，这就好比球场本身，作为高尔夫球手你是无法控制球场的。

最后是**工程师个人**，即作为个体所具备的一切特质。在控制了上述所有其他变量的前提下，这些个人特质依然让你显得与众不同。

这就是我们剩余演讲的路线图。将所有这些要素整合起来，进行一系列复杂的统计分析——我很乐意在此展开细节，但除了像我这样的统计学家之外，其他人都会觉得枯燥无味。不过，这就是全景图：

对于 PR 吞吐量变化的解释力，**工具**所起的作用不足 1%。

你**如何熟练地使用它**（即 Skill 的部分），贡献了约 3%。

你**使用了多少**，是工具影响力的近 10 倍，占 9%。

你**在哪里工作**占 12%。

而占比最大的部分，是**你这个个体**。

我们将逐一展开讨论，解释为什么数据会呈现出这种分布。

（回应听众）是的，这里没有包含质量指标，但质量是我们经常考量的一个维度。我很乐意稍后再深入讨论这个，但问得很好。

<details>
<summary>Original English</summary>

So, that's what we're going to spend the rest of the talk talking about. Uh

So, here's what we're going to do. We're going to continue to focus on this output metric of merged PRs per engineer per week. We're going to use a curated data set here. This is a subset of our data where we've got all the pieces we need to do this experiment. About 50,000 engineers at 447 companies. Data from this year for Cursor and Claude code users. And some of the stuff that matters.

So, you've got the tool. We're going to put the harness and the model together because they're very intertwined. This is like your clubs, okay?

There's how well you use it. By that, I mean things like your skill use, cursor rules, the the harness customization, the tricks of the trade that we're all learning as AI engineers to make the way that we use these tools better. Golf equivalent would be like this is knowing how to get out of a bunker, which is not like a natural thing. It's a thing you have to learn.

There's how much you use it. So, separate from these things, just raw amount of token spend. So, golf time on the course, right?

Uh and then there's factors like where you work, your environment. So, your company and your team, this is the course itself, something you don't have control over as a golfer. And then there's you, the individual, all the things that you carry with yourself as an engineer that, holding all these other factors constant, that make you still distinct.

>> [snorts]

>> So, this is the map for the rest of our talk. You put all this stuff together, you do a bunch of big statistical analyses, the details of which I would love to get into here, but would bore everyone except for statisticians like me. But, this is the map. You've got about uh less than 1% the in terms of how your how much your PR throughput changes is controlled, explained by the tool.

How well you use it, the skills part, that's about 3%. Uh how much you use it, that's like 10x uh the tool, that's 9%. Where you work is 12%. The biggest piece is you, the individual. We'll go through each of these and explain a little bit about why this looks like this.

Mhm. No, there's no quality metric here, but quality's a thing we look at a lot. I'm happy to talk more about that later, but good question.

>> [snorts]

</details>

---

### 工具与技能：模型差异影响微弱，技能熟练度带来 30% 提升

首先来看工具部分。

我们快速过一下这一块。正如大家从我的演讲标题所能猜到的，这是最无趣的部分。当工程师更换工具时会发生什么？我们刚才已经看到了当他们可以说是被“鼓励”更换工具时的情形。但工程师其实一直在自行更换所用的模型，他们也在更换测试框架。你可以借此观察每周合并 PR 数量的变化；你也可以拿工程师自身作前后对照，看看当他们全力投入使用 Opus 对比 Sonnet，或是转用 ChatGPT 时发生了什么。

如果他们从 Cursor 切换到 Claude Code 会发生什么？我们有很多关于做出这种迁移的用户数据。如果从完全的自动补全模式（autocomplete mode）切换到 Agent 模式（agentic mode），又会发生什么？情况基本上大同小异。从统计学上看，这基本上是个无关紧要的事件（nothingburger）。在解释 PR 吞吐量的任何实质性变化方面，工具所能提供的信息非常有限。

那么，你使用工具的熟练程度呢？这部分占到了 3%，在饼图中占据了更大的份额。我们来谈谈 Skill 的使用。这一点很有意思，因为 Skill 的占比理应更大。我们发现 Skill 实际上极其重要，而它在整体中所占比例没有更高的原因之一——这可能会让某些人感到意外——在于，在现实世界中，走出我们现在身处的 AI 工程师大会这一美妙天地之外，并没有那么多人高频使用 Skill。

这张图表展示了随着时间推移，工程师在各自然周内的 Skill 使用情况：即零使用或极低使用、低使用、中等使用和高使用水平的工程周比例。截至 9 月份，图中所显示的工程周里几乎有一半基本上完全没有使用 Skill；只有 12% 的使用水平达到了我认为现代 AI 工程实践所应具备的标准。

这之所以如此重要，是因为一旦高频使用 Skill，它对产出的推动作用将远远超过单纯的模型选择。这里我再次展示了之前快速闪现的更换模型家族的结果作为参考对比。但在图表底部展示的是 Skill 的使用水平，以及在保持其他变量不变的情况下，它对改变 PR 吞吐量所产生的实际效果。你可以看到，当达到每位工程师每周使用 Skill 超过 30 次以上时，仅凭这单一因素，在控制其他变量不变的情况下，就能带来 30% 的产出提升。所以这是一个非常显著的影响。

<details>
<summary>Original English</summary>

>> Uh so, let's do the tool first.

So, we'll kind of speed through this. This is the least interesting, as you might guess uh um from the title of my talk. But, what happens when engineers switch tools? We saw what happened when they were kind of encouraged, let's say, to switch tools, uh but engineers uh switch the models they use all the time, they switch harnesses. So, you can do things like look at change in the weekly merge PRs. You can compare an engineer to themselves and look at what happens when they go all in on Opus versus Sonnet, switch to Chat GPT. Um what happens if they switch from Cursor to Cloud Code, which we have a lot of data around people who've made that switch. What happens when uh you switch from working totally in an autocomplete mode to an agentic mode. The story's kind of the same. Statistically, it's kind of a nothingburger. There's not a lot here in terms of explaining any meaningful change in um the amount of PR throughput that you get.

What about how well you use it? This is 3%, so much bigger piece of the pie. Let's talk about skill use. This one's interesting because skills This should be bigger. Skills actually we find matter a lot. One of the reasons it doesn't matter more is and I don't This might surprise some folks. People who use skills that much like in the real world outside of like this this wonderful land of AI engineering conferences that that we're inhabiting. Uh this chart shows um you know, skill use engineer weeks over time. So, proportion of engineering weeks that have, you know, low zero skill use, a low level, a medium level, and a high level of skill use. And as of September, you know, almost half of the weeks here shown had essentially no skill use. Uh and only 12% had are using skills at a level that I think we would consider as like what you should be doing in terms of modern AI engineering.

And the reason that this is so important is because skill use when it's prevalent moves output way more than model choice. So, I'm showing here again those results I flashed from earlier about changing model family as as kind of a reference. But on the bottom here is level of skill use and the amount of effect it has in terms of changing the level of PR throughput holding these other factors constant. And you can see you get um you know, when you get up to 30 plus runs uh of using skills uh per engineer per week, that's a 30% bump just from that factor alone holding other things constant. So, it's a big effect.

>> [snorts]

</details>

---

### 使用量与组织环境：消耗更多 Token，以及企业文化的倍增效应

好的，接下来谈谈你使用了多少。这是消耗量，指的是 Token 数和活跃使用天数。

关于这一点，我完全可以做一场专门的演讲。实际上，我之前在 AI Engineer World's Fair 上就对此做过完整演讲。如果大家对这个感兴趣，我建议可以去看看那个分享。

不过我这里用一张幻灯片总结一下。大家现在看到的这些数据正是来自那次演讲，涵盖了大约 500,000 个开发者周的行为数据。每一个点代表按当周消耗水平划分的 2% 分位数人群，图表呈现的是他们的平均 Token 支出与每位开发者每周合并 PR 数量的关系。

基本结论是：消耗的 Token 越多，吞吐量越高。但它存在边际收益递减，呈现出一种饱和曲线。我在那次演讲中把它比作火箭方程，Token 就像火箭燃料。从数据来看，如果你对比前 10% 和中位数水平，中位数到前 10% 之间的产出基本可以翻倍；这大约需要消耗 10 倍的 Token。但无论如何，消耗更多 Token 确实意味着更高的产出。

现在我们进入到饼图中占比更大的部分，这些内容非常有意思。

首先是你在哪里工作、你的公司和你的团队。实际上，如果将这些因子拆解开来，大约三分之一归因于团队，三分之二归因于公司。这包括你的代码库、评审流程以及组织文化。那么，在固定了 Token 消耗量之后，这些因素依然重要吗？

观察这个问题的一种方式是：固定上述那些变量，仅观察其离散度，即在控制其他变量不变的情况下，各家公司相对于平均水平的分布跨度。这就是它呈现出来的形态。对这种分布的一种解读方式是：我刚才展示了那条 Token 曲线，你可以通过消耗 10 倍的 Token 从中位数爬升到前 10% 的分位数，从而使产出翻倍；而在这个分布中，即便保持你的 AI 消耗量完全固定，前 10% 的公司与后 10% 的公司之间也存在 2 倍的产出差距。换句话说，单单是你的文化、团队和公司环境，即便在固定的 AI 投入下，也会产生巨大的差异。

这一点至关重要，而且对身处领导力分论坛的各位来说非常值得关注，因为这正是管理者可以掌控的杠杆。这就是我们的职责所在，即便 CFO 可能会告诉我们不能再批更多的 Token 预算——当然，但愿他们不会这么说——我们依然可以去掌控和优化这些组织要素。

那么，占比最大的那个部分呢？你本身，即工程师个体。这占据了整个统计模型近四分之三的比重，因此它极其关键。

<details>
<summary>Original English</summary>

>> All right, let's talk about how much you use it. This is consumption. This is tokens. This is active use days. Uh this one I could do a whole talk about this. In fact, I did a whole talk about this at the AI Engineer World's Fair. So, I encourage you if you find this interesting to uh to take a look at that.

Um but I'll give you the one slide version. So, the data you're looking at here is from that talk. So, this is um about 500,000 developer weeks of behavior. Each dot is a two percentile bin of uh folks that use the same level of consumption in that week, and it's their average token span and their merged PRs per developer per week. And the basic story is more tokens, more throughput. And there's diminishing returns. So, there's sort of a saturating curve. I likened it to the rocket equation in that talk. It's like rocket fuel. And what you get is if you look at the top 10% versus the median, uh you can basically double your output between the median and the top 10%. It costs you about 10x the tokens. But more tokens mean more output.

Now we get to the bigger pieces of the pie. These are interesting. So, there's the factor of you know, where you work, your company, your team. Actually, if you tease out the factors, about a third of it's the team, two-thirds is the company. You know, your your code base, your review process, um your culture. So, once you sort of fix the amount of consumption, you know, do these other things still matter?

One way to look at this is, you know, if you fix these factors and just look at the variability, you look at the spread of companies relative to the average company holding these other things fixed. Um, this is what it looks like. And one way to interpret this is, I just showed you that token curve. So, you could spend 10x the tokens to move from the median up to the top 10 percentile and get double the output. There's also a 2x spread between the top 10% company and the bottom 10% company in this distribution holding your consumption fixed. So, in other words, your culture, your team, your company, there's a lot of variation just in those things even for fixed AI spend. This matters a lot and it's interesting for this group in the in the leadership track here because this is what leaders can control. Like, this is our our job is to control these things even if maybe our CFO tells us we can't have any more tokens than we have. Um, which hopefully they don't.

So, what about the biggest piece? You, the individual, right? This is this three quarters of this statistical model. So, it matters a lot.

>> [snorts]

</details>

---

### 工程师个体与结语：工艺依然重要，改变你所在的球场

思考这一点的维度之一，是很多人都在问的问题：AI 是否意味着你需要雇佣完全不同的一批工程师？我们是否需要换人？它是否在重塑工程师的排名？它是否改变了成为优秀工程师的定义？

大家刚才看到了我展示的公司分布。如果对工程师个体做同样的分布分析，其离散度甚至更宽。这意味着存在更大的个体差异，这也是为什么在我们为了解释各种可用杠杆而构建的统计全景图中，它占据了如此巨大的比重。它的分布更宽，在后 10% 和前 10% 之间存在 3.5 倍的差距，而不是公司层面的 2 倍差距。这里面有太多的细节需要剖析，要讲清楚究竟是哪些特质让一部分 AI 工程师比其他人更优秀，完全可以再讲上一整场。

但在我剩下的几分钟里，我们可以先回答一个问题：AI 是否改变了谁才是最高产的工程师这一格局？

观察这个问题的一种方法，是对 10,000 名工程师进行排名的纵向小型研究。我们拥有长期的追踪数据。Jellyfish 已经成立 10 年了，因此我们拥有海量关于工程师行为的历史数据。如果你去观察顶尖工程师在各个季度、每半年之间的排名表现，我们可以看看你的顶尖工程师在生产力方面的流动轮换情况——这里讨论的依然是 PR 吞吐量指标——即他们跌出前四分之一（top quartile）的比例。如果比较这个数据，在 AI 普及之前，大约有 44% 的人每半年会掉出前四分之一梯队。

如果对比 AI 出现前后的数据，这个流动其实还稍微收紧了一点，人员流动性反而略微降低了，变成了 41%。我们做过的其他类似研究也印证了这一点。我们并没有看到世界秩序的大洗牌。在 AI 时代到来之前最优秀的工程师，大体上现在依然是最优秀的工程师。因此，所谓“AI 抹平了竞争差距”的说法并不准确，工程技艺（craft）仍然极为重要，这也是为什么个体因素的比重会如此庞大的部分原因。

回到我一直在向大家展示的这幅全景图。将所有这些因素加总在一起，我希望大家能带走的认知是：图表左侧的那些东西，尤其是工具本身，固然非常吸睛，讨论起来非常令人兴奋。那是炫酷的新技术，几乎占尽了屋子里所有的关注，占尽了 Twitter 上的所有版面。那确实很吸引人，我也很喜欢那些东西。

但我们对底层技术并没有太多的控制权。我不在基础模型实验室工作，我无法直接把模型工具变得更强。而且随着成本收紧，我们购买心仪工具的自由度也许会越来越低。但作为团队领导者，我们能够掌控的杠杆都在方程的另一端：是人才，是组织。

再次回到我们最初的高尔夫球类比，最令人振奋的是：与高尔夫不同，在工作中你其实可以改造球场。你可以改变你的环境。你可以填平水障，或者去做那些如果你在真正高尔夫球场上干会被人破口大骂的事情。作为管理者，这些都是我们可以使用的手段。

所以在结束之际我想说：如果你没有得到预期的成果，我建议你认真想一想，也许问题并不在模型，问题也许就在于你自己。

谢谢大家，非常感谢。我就讲这么多。如果大家感兴趣，我们会发布包含所有这些数据及更多内容的月度基准报告，请访问 Jellyfish AI engineering trends。我们的许多研究也会发表在 Substack 上。谢谢大家。

<details>
<summary>Original English</summary>

>> Um, one way of thinking about this is this question that a lot of people have asked is, you know, does AI mean that you need different engineers? Do we need different people, right? Is it resorting the rankings? Is it changing what it means to be a good engineer?

So, uh, you saw that distribution I just showed you with companies. If you do the same sort of distribution for engineers, it's even wider. So, there's even more variability and that's why it's such a big factor in this this statistical map we've we've laid out for ourselves to explain the different levers available to us.

Uh, it's even wider. It's, you know, 3.5x spread between the bottom 10% and the top 10% uh instead of 2x as for companies. And there's a lot to unpack here. This will be a whole 'nother talk to unpack all the things that make different uh AI engineers uh better than others. One thing that we can answer a little bit in the few minutes I've got left is is AI changing who the most uh productive engineers are.

So, one way to look at this, here's a small study ranking 10,000 engineers. We have long uh you know, longitudinal data, long timeline. Jellyfish has been around 10 years. So, we have, you know, tons of history about how engineers behave. And if you look at, you know, how um top engineers rank uh you know, quarter over quarter, 6 months over 6 months, uh we can look at, you know, how much do your top engineers cycle in terms of productivity here. Um PR throughput we're still talking about. How much uh they cycle out of the top quartile. And if you compare that uh so, you know, about 44% cycle out of the top quartile uh every half year.

Uh if you look at before AI versus after, it actually tightens a little. People get a little less mobile. It's 41%. So, and we've done other studies like this. We're not seeing um you know, a big re-sorting of the world order. Your your best engineers before AI by and large are still your best engineers. So, the the sort of narrative that AI's leveling the the playing field uh there's craft still matters for a lot, and that's why part of why this factor is as big as it is.

So, you know, going back to this this picture that I've I've been showing you. When you add it all up, you know, what I want you to take away is is these things on the left, you know, the tool especially, are like really exciting to talk about. It's the cool new tech. It takes up kind of all the air in the room, all the air on on Twitter. And like that's exciting, and I love that stuff. Um but we don't have a lot of control over that. I don't work at a foundation lab. I can't make the tools better. Uh, and as cost tighten, we have um, less and less freedom maybe to buy the tools that we want. But as leaders, the things we can control are on the other side of the uh, the equation. It's it's the people, it's the organization. And I think what's, you know, going back to our golf analogy, what's really exciting about that is unlike golf, you can change the course. You can change your environment. So, you can like fill in water hazards or do things that they yell at you if you try to do on a golf course. But um, those are things as leaders that are available to us. So, in closing, um, you know, if you're not getting the outcomes that you want, I would encourage you to think, you know, maybe it's not the model, you know, maybe it's you.

So.

>> [applause]

>> Thank you. Appreciate that. That's all I've got. If you're interested, we publish monthly benchmarks with all of this data and more. Go to Jellyfish AI engineering trends. Uh, a lot of our research is published on our Substack. Uh, thank you.

</details>