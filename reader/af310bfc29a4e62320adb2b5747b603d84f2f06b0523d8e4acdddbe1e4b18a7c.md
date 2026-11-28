---
author: Internet of Bugs
date: '2026-11-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pyRG_5dCrfg
speaker: Internet of Bugs
tags:
  - conflict-of-interest
  - capability-evaluation
  - initial-public-offering
  - benchmark-manipulation
title: 质疑 80,000 Hours 与 METR 夸大 Anthropic 的 AI 进展及潜在利益冲突
summary: 作者质疑 80,000 Hours 在 Anthropic 即将上市之际发布视频宣传其实现“两倍提速”里程碑的真实性，指出评估机构 METR、Epoch 与 Anthropic 早期投资者之间存在重大利益关联，并批评其能力指数在校准、模型筛选及访谈证据上存在操纵。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Daniela Amodei
  - Dustin Moskovich
  - Jaan Tallinn
  - Eric Schmidt
  - Holden Karnofsky
companies_orgs:
  - 80,000 Hours
  - Anthropic
  - METR
  - Epoch AI
  - Schmidt Sciences
  - Coefficient Giving
products_models: []
media_books: []
status: evergreen
---
### 80,000 Hours 视频背后的利益冲突与背景

80,000 Hours 制作了一期新视频，称 Anthropic 据说已经达成了一个超级 AI 毁灭里程碑，并且他们在 Anthropic 首次公开募股（IPO）前一周发布了该视频，其依据是前一周刚发布的一份报告。正如这类内容的一贯做法，里面充斥着半真半假的说辞，以及大量令人怀疑甚至与视频内容相矛盾的遗漏。我将为大家拆解这一切，首先从他们隐瞒的利益冲突讲起。

<details>
<summary>Original English</summary>
So, 80,000 hours has made a new video about how Anthropic supposedly has reached a super AI Doom milestone, and they put it out a week before Anthropic's IPO, based on a report that came out a week before that. And as usual with this stuff, it's full of half-truths, lots of omissions that cast doubt on, or even contradict what the video says. I'm going to break it down before you starting with the conflicts of interest that they're hiding.
</details>

不过要做到这一点，我必须提及一些人的名字，有些名字我可能会念错，我也不打算去查证发音，因为我想赶在即将到来的 IPO 之前发布这个视频，坦率地说，也因为我不在乎。因为我今天要提及的大多数人全都是亿万富翁，或者即将成为亿万富翁。如果我伤了他们的感情，他们大可以去给自己买艘游艇或私人飞机来抚慰心情，或者干脆花钱把我做掉。

<details>
<summary>Original English</summary>
To do that though, I'm going to have to be giving you some names, and I'm probably going to mispronounce some of them, and I'm not going to look them up because I'm trying to get this video out before the upcoming IPO, and frankly, because I don't care, because the people I'm mostly going to be naming today are all billionaires, or soon to be billionaires, and if I hurt their feelings, they can go buy themselves a yacht or a private jet to make themselves feel better. That or they can just pay to have me ki---------------d.
</details>

这里是 InternetOfBugs。我叫 Carl。自 1980 年代末以来我一直是一名软件专业人士，我正尽自己的一份力量让互联网变得更安全、更少 Bug。你可以在 InternetofBugs.com 了解更多关于我和我工作的信息。你可以在我免费的 Internet of Bugs Substack 上阅读我关于 AI 软件的文章；如果你愿意支持我在这里做的事情，并获取独家锐评视频以及每周问答视频通话的权限，下方也附有我的 Patreon 链接。

<details>
<summary>Original English</summary>
This is the InternetOfBugs. My name is Carl. I've been a software professional since the late 1980s, and I'm trying to do my part to make the Internet a safer, less buggy place. You can find out more about me and my work at InternetofBugs.com. You could read my essays about AI software on my free Internet of Bugs substack, and if you would consider supporting what I do here and getting access to exclusive hot-take videos and weekly question and answer video calls, links to my Patreon are below as well.
</details>

我们今天的故事始于 80,000 Hours 的这期视频，内容是关于 Anthropic 据称达成了一项名为“递归自我改进”（Recursive Self Improvement）的里程碑。我以前谈过这个。根据 METR 基于 Epoch 定义的指标撰写的一份报告，这一说法并不属实，我们稍后会讲到。但在我开始驳斥这个视频之前，我想先向你们介绍其中的几位参与者。参与者还有很多，但我只挑几位来讲，我想让你们看看他们不会告诉你们的内容，而我将要告诉你们的一切，都有我下方附带的一系列链接作为支撑。这个视频有大量的消息来源。

<details>
<summary>Original English</summary>
Our story today starts with this video by 80,000 hours about how Anthropic has supposedly reached a milestone called "Recursive Self Improvement." I've talked about that before. According to a report written by METR based on metrics defined by Epoch. This claim is not true, and we'll get to that in a while. But before I start debunking this video, I want to introduce you to just a few of the players here. There are a lot more, but I'm going to talk about just a few, and I want to show you what they won't tell you, and everything I'm going to tell you is backed up by a bunch of links I've included below. This video has lots of sources.
</details>

80,000 Hours 是一家非营利组织，声称帮助人们寻找有意义的职业。他们也制作了大量关于 AI 有多么可怕的内容。Anthropic 是一家将在本周晚些时候进行首次公开募股的公司。他们就是那家据说达成了该里程碑的公司，我稍后会谈及。METR（M-E-T-R）是另一家自称独立的非营利机构，它获得了访问 Anthropic 数据的权限，并得出结论认为 Anthropic 已经达成了该里程碑。而 Epoch AI 则是另一家设立基准和衡量标准等的非营利机构，AI 公司可以用其来展示自家 AI 变得多么强大。

<details>
<summary>Original English</summary>
So 80,000 hours is a non-profit that says that it helps people find meaningful careers. They also make lots of content about how scary AI is. Anthropic is a company that's going to an initial public offering later this week. They are a company that supposedly reached the milestone. I'll talk about that later. METR - M-E-T-R is another non-profit that claims to be independent who was given access to Anthropic's data and concluded that Anthropic has reached the milestone. An Epoch AI is another non-profit who sets up benchmarks and measurements and such that AI companies can use to show how great their AIs are becoming.
</details>

总结一下：根据 Epoch 设立的衡量标准，经 METR 解读和报告，Anthropic 据称完成了一件事，然后被 80,000 Hours 制作成了视频形式，希望你们在 IPO 之前看到。明白了吗？好，让我把这些挪动一下，腾出点空间。

<details>
<summary>Original English</summary>
So in summary, Anthropic supposedly did a thing according to measurements set up by Epoch as interpreted and reported on by METR that was put into a video form by 80,000 hours that they want you to see before the IPO. Got that? Okay. Let me move these around to make some room.
</details>

### 核心人物与资金链关联

好的，现在我需要加入另外两个组织：Schmidt Sciences 和 Coefficient Giving。它们都是 METR、Epoch 以及 80,000 Hours 的主要资金来源。

<details>
<summary>Original English</summary>
Okay. Now I need to put in two more organizations, Schmidt Sciences and Coefficient Giving. These are both major funding sources for METR, Epoch and 80,000 hours.
</details>

好了，现在我需要引入五个人。本来可以列出更多，但我用五个人就能说明观点，所以尽量保持画面不那么杂乱。首先是 Daniela Amodei，Anthropic 的总裁，也是 Anthropic 首席执行官 Dario Amodei 的妹妹，不过 Dario 甚至都没进我的名单。但由于包括我在内的大多数人一听到 Amodei 这个姓就会联想到 Dario，所以在本视频余下部分我将称呼她为 Daniela。我绝无不尊重她性别等方面的意思，纯粹是因为在当前语境下她的姓氏存在歧义，所以我用名字来称呼她，这样能确保清楚我在说谁。

<details>
<summary>Original English</summary>
Okay, now I need to bring in five people. Could have been a lot more, but I can make my point in just five, so I'm trying to keep things as then clutter as I can. First we have Daniela Amodei, the president of Anthropic and the sister to Dario Amodei, the CEO of Anthropic, but he didn't even make my list. But because most people, including me, associate the name Amodei with Dario, I'm going to be referring to her as Daniela for the rest of this video. I don't mean any disrespect for her gender or anything. It's simply because her last name is ambiguous in the context, so I'm going to use her first name. So that way, I'm sure who I'm talking about.
</details>

好的，现在我们有了 Facebook 联合创始人 Dustin Moskovich、Skype 联合创始人 Jaan Tallinn、Google 前首席执行官 Eric Schmidt，以及 Coefficient Giving（在其从 Open Philanthropy 改名之前）的创始人兼前首席执行官 Holden Karnofsky。现在，我要把 Karnofsky 挪到 Daniela 旁边，因为他们两人是夫妻。

<details>
<summary>Original English</summary>
Okay. So now we've got Dustin Moskovich, the co-founder of Facebook. Jaan Tallinn, the co-founder of Skype, Eric Schmidt, the ex CEO of Google and Holden Karnofsky, the founder and ex CEO of Coefficient Giving back before it changed its name from Open Philanthropy. Now, I'm going to move Karnofsky over here next to Daniela because they're married to each other.
</details>

Moskovich、Tallinn 和 Schmidt 都是 Anthropic 非常早期的 A 轮投资者。因此，如果 Anthropic 的 IPO 估值很高并且他们能够出售所有股份，他们都将赚取数十亿美元。Daniela 是 Anthropic 的总裁，显然也能赚大钱。而她的丈夫 Karnofsky 也在 Anthropic 工作。目前为止都跟得上吗？

<details>
<summary>Original English</summary>
Okay. So Moskovich, Tallinn, and Schmidt were all very early Series A investors in Anthropic. So they all stand to make billions of dollars if Anthropic has a high IPO valuation and they can sell all their shares. And Daniela is the president of Anthropic, and so also stands to reason she'll make a ton of money. And her husband Karnofsky also works in Anthropic. With me so far?
</details>

好的，Schmidt Sciences 是 Eric Schmidt 的慈善载体。基本上，这是他和妻子设立的一家非营利机构，用来向其他组织捐款。Coefficient Giving 由 Moskovich 和 Karnofsky 创立，Karnofsky 曾担任过一段时间的首席执行官，尽管他现在在 Anthropic 工作。Schmidt Sciences 同时资助 Epoch AI 和 METR；Coefficient Giving 资助 Epoch AI 和 80,000 Hours；而 Tallinn 则以个人名义同时资助这三家机构。

<details>
<summary>Original English</summary>
Okay. So Schmidt Sciences is the philAnthropic vehicle for Eric Schmidt. Basically, it's a nonprofit that he and his wife set up to use to give money to other organizations. Coefficient Giving was founded by Moskovich and Karnofsky, and Karnofsky was their CEO for a while, although now he works in Anthropic. Now Schmidt Sciences funds both Epoch AI and METR, Coefficient Giving funds Epoch AI and 80,000 hours, and Tallinn funds all three of them personally.
</details>

### 所谓的“独立评估”漏洞

而这些只是我在赶制这个视频时能追踪到的最直接的关联，因为我想在 IPO 之前把视频发出来，任何准备投资 Anthropic 的人都应该被告知这一切。这些都不是秘密，但追踪所有这些关联肯定非常耗时，因为它们全都被埋在财务文件的最底层。

<details>
<summary>Original English</summary>
And those are just the most direct connections that I could trace while making this video in a hurry because I wanted to get the video out before the IPO, because anyone who's going to be investing in Anthropic should be told about all of this. None of this is secret, but it's certainly time consuming to track down all these connections because they're all like buried in the bottom of financial documents.
</details>

如果 80,000 Hours 在他们的视频中清楚说明，包括 80,000 Hours 在内的所有这些组织的资助者，在视频说服人们相信 Anthropic 达成了这一里程碑并促使人们投资 IPO 的情况下，都能赚取数十亿美元，那么这本身并没有什么问题。如果 METR 在撰写该视频所依据的报告时披露，他们直接或间接地从 Anthropic 的极早期投资者（这些人将在 IPO 中赚取数十亿）那里获得了大量资助，那本身也没有问题。但相反，METR 称自己是独立的。

<details>
<summary>Original English</summary>
And there would be nothing inherently wrong with this if 80,000 hours clearly explained in their video that the funders of all of these organizations, including 80,000 hours, stood to make billions of dollars if their video convinces people to believe that Anthropic hit this milestone and that causes people to invest in the IPO. And there would be nothing inherently wrong with METR writing the report this video was based on if they disclosed that they received major funding from individuals either directly or indirectly who were very early investors in Anthropic and stand to make billions in the IPO. But instead METR calls themselves independent.
</details>

他们甚至有一份清单（该清单是由他们共同创立的标准组织制定的），试图以此证明自己是独立的。看看你能不能发现漏了什么，引用如下：“评估机构的重要资金份额是否来自系统提供商、其员工或其直接竞争对手？”引用结束。好吧，并不来自他们。评估机构的重要资金份额是来自系统提供商的早期个人投资者和股权持有者。有意思的是，这一点竟然没被列入清单。

<details>
<summary>Original English</summary>
And they even have a checklist (and the checklist was created by a standards organization that they co-founded) to try to prove that they're independent. So see if you can spot what's missing: Quote: "Does a meaningful fraction of the evaluators funding come from the system provider, its employees or its direct competitors?" Unquote. Well, no. A meaningful fraction of the evaluators funding comes from the system providers early individual investors and equity holders. Funny how that got left off the checklist.
</details>

我现在无法证实 Anthropic 的投资者资助 METR 这一事实影响了他们的调查结果，但我可以证明，他们关于自身独立的说法是在撒谎，至少在大多数人对独立的定义上是如此，按我的定义肯定也是如此。我也无法证明 80,000 Hours 的资助者影响了他们的视频内容，但我可以证明他们没有进行充分披露。这让我感到怀疑，也应该让你感到怀疑。我想说明的是，对于这些参与者之间错综复杂的关系网，我仅仅是触及了冰山一角。我并不是唯一这样做的人，我在下方留下了 Twitter 上 Kevin Bass 工作的链接，他在追踪这些事情上做了大量工作。我是说，看看他画的这张图，简直太疯狂了。

<details>
<summary>Original English</summary>
Now I can't prove that the fact that Anthropic's investors are funding METR influence their findings, but I can show that they're lying about being independent, at least in the way that I think that most people would define independent, certainly the way I do. And I can't prove that 80,000 hours funders influence their video content, but I can show that they didn't adequately disclose it. And that makes me suspicious and that should make you suspicious too. And I want to make it clear that I'm only scratching the surface of the iceberg that is all the tangled web of connections between these players and I'm not the only one to do so, I've left links below to the work of Kevin Bass on Twitter who's done a lot of work tracing down this stuff. I mean, look at this graph of his. It's crazy.
</details>

### 拆解“AI 进步提速两倍”的评估数据

好了，现在让我们来看看视频中的实际论断。在 80,000 Hours 的视频播放到 5 秒时，我们被告知，引用如下：“METR 是一个独立组织。”引用结束。正如我们在过去几分钟所看到的，他们并不是。所以这不是一个好的开端。播放到 13 秒时，我们被告知“Anthropic 现在改进其 AI 的速度比一年前快了两倍”。嗯。接着是一堆关于递归自我改进的废话，然后又是那句“快了两倍”，再然后是一堆关于 COVID 和 AI2027 的恐慌炒作……你们懂的。

<details>
<summary>Original English</summary>
Okay. So now let's deal with the actual claims in the video. So five seconds into the 80,000 hour video, we're told, quote, "METR is an independent group." Unquote. Now, as we've just seen in the last few minutes, they're not. So this isn't a good start. 13 seconds in and we're told "Anthropic is now improving its AI twice as fast as it was a year ago." Hmm. Then we get a bunch of crap about Recursive Self Improvement, then we get the "twice as fast" line again, then we get a bunch of scaremongering about COVID and AI2027... You get the idea.
</details>

在视频的前半部分，我们被一遍又一遍地告知 METR 发现了 2 倍的提速。终于，在视频进行了大约 7 分半钟时，他们提出了本该一开始就问的问题，随后立即给出了一个谎言。问题是，引用如下：“所有这些都建立在 METR 是正确的基础之上。那么，他们关于 Anthropic 目前取得进展的速度是原来两倍的发现究竟有多可靠呢？”引用结束。他们的回答是，引用如下：“METR 用不同的统计方法以多种方式进行了分析，改变了他们使用的基准并剔除了某些模型，几乎每一个版本仍然显示进展发生的速度大约是原来的两倍。”引用结束。这就是个谎言。

<details>
<summary>Original English</summary>
For the first half of the video, we're told over and over again that METR found a 2x speed up, then finally, about seven and a half minutes into the video, they asked the question they should have started with and then they immediately answer it with a lie. The question is, quote, "All of this rests on METR being right. So how solid is their finding that Anthropic is now making progress twice as fast?" Unquote. Their answer, quote, "METR read the analysis lots of ways with different statistical methods, changing which benchmarks they use and leaving out certain models, almost every version still showed progress happening around twice as fast" unquote. This is a lie.
</details>

这是报告中的一张图表，展示了 METR 进行分析解读的部分方式。你会注意到，这期视频解读为“大约快两倍”的 1.90 这个数字，是图表左上方最高的数值；而对于其他校准（稍后会详细讨论校准），这一加速实际上可能是 1% 的放缓。这就引出了另一个重要问题：这些人到底使用的是什么鬼方法，竟然校准上的一个变动就能在增加 90% 与减少 1% 之间波动？

<details>
<summary>Original English</summary>
So here's one figure from the report showing some of the ways that METR read their analysis. You'll notice that the 1.90 number that this video is interpreting as "around twice as fast" is the highest number on this chart up in the upper left and for other calibrations, (more on calibrations in a minute), the speed up could actually be a 1% slowdown. And that leads to another important question, what the hell kind of methodology are these folks using where a change in calibration can vary between 90% increase and a 1% decrease?
</details>

在这整个视频中，他们仅使用了一种度量标准来判定取得了什么样的进展（此外还有我们稍后会讲到的另一部分）。这种度量被称为“能力指数”（capabilities index），它是一种将一堆不同的基准结合起来、用非常复杂的统计数学进行处理，然后输出一个单一数字的方法。最初的“能力指数”是由 Epoch 创建的，也就是我们之前谈到的受 Anthropic 投资者资助的机构之一，所以这里存在明显的利益冲突。然后 Anthropic 又创建了他们自己的专有版本，并在 METR 对 Anthropic 模型的评估中大量使用。我相信他们会说“相信我吧兄弟，没问题的”。

<details>
<summary>Original English</summary>
Well, they're using only one kind of measurement in this entire video to decide what kind of progress is getting made (as well as another section will get to in a minute). That measurement is called a "capabilities index", and it's a methodology for taking a bunch of different benchmarks, combining them all with very complicated statistical math and then spitting out a single number. The original "capabilities index" was created by Epoch, one of those groups that's funded by Anthropic investors that we talked about earlier, so there's a clear conflict of interest. And then Anthropic created their own proprietary version of it that was largely used in METR's evaluation of Anthropic's models. I'm sure they'd say "Trust me, Bro, it's fine."
</details>

### 刻意筛选模型与主观划分数据

而且众所周知，这些能力指数度量很容易让所有的分数随着时间的推移向上漂移。一些批评者甚至表示，这些能力指数，引用如下：“没有良好的 y 轴”，引用结束。除了解释随着时间推移的增长却使用了一个随时间向上漂移的指数之外，他们还在哪些模型算入或不算入度量中进行了极其严重的挑拣（cherry picked）。

<details>
<summary>Original English</summary>
And these capability index measurements are notoriously bad at allowing all of the scores to drift upwards over time. Some critics have even said that these capability indexes have, quote, "No good y-axis," unquote. And then, on top of the fact that they're using an index that drifts up over time to measure an increase over time, they cherry picked a hell out of which models do or don't count towards their measurements.
</details>

这是他们论文中的图表。对于 Opus 4.7、4.8、5 和 5.5，哦，还有 Mythos 5.1，那些白色圆圈里的每一个……是的，他们认定那些都不算。为什么？因为它们“不是前沿模型”（not frontier）。所以 Mythos 5 算作前沿，但 5.1 就不算。还要注意，在他们确实算作前沿的 7 个内部模型中，有 4 个要么是“早期”（early）要么是“准早期”（pre-early）模型。他们不算 2024 年或 2025 年模型的早期或准早期内部版本，只算 2026 年新模型里的。这是为什么呢？这么说吧，这改变了线条的走势。我们稍后会回到这一点。

<details>
<summary>Original English</summary>
So here's the graph in their paper. Each of those white circles for opus 4.7, 4.8, 5, and 5.5, oh, and Mythos 5.1... Yeah, they decided those don't count. Why? Because they're "not frontier." So mythos 5 counts as frontier, but not 5.1. Also note that four of the seven internal models that they DO count towards the frontier are either "early" or "pre-early" models. They don't count early or pre-early internal versions of models from back in 2024 or 2025, only from the new ones in 2026. Now why is that? Well, let's just say it changes the shape of the line. We'll get back to that a second.
</details>

如果这还不够作弊的话，他们还武断地将数据集分成两组：右边一组，左边一组。每一组都被赋予了一条自己的趋势线，然后他们画上一个黄色圆圈，试图让这看起来像是有什么依据似的。武断地选定某一点并声称“右边的一切都与左边的一切不同”，根据你划分位置的不同，你会得到很多不同的答案。

<details>
<summary>Original English</summary>
And if that wasn't enough cheating, they just arbitrarily divide the data set into two different groups. One group on the right, and one group on the left. Each are given their own trade line, and then they draw a yellow circle in to make it look like there was some reason for it. Arbitrarily picking some point and saying "everything on the right counts as different than everything on the left," you get a lot of different answers depending on where you put the division.
</details>

这是我在下方附上链接的一份电子表格，是我复现他们数据所制作的。我加入了从 Epoch AI 下载并合并的数据集，涵盖了已测定但 METR 选择不包含在其图表中的所有其他 Anthropic 模型。看到左边所有的复选框了吗？其中每一个都是 METR 和公众拥有数据、但 METR 选择不在报告中包含的 Anthropic 模型。

<details>
<summary>Original English</summary>
So here's a spreadsheet linked down below that I put together with a reproduction of their data. And I included a downloaded and merged data set from Epoch AI for all of the other Anthropic models that have been measured that METR chose not to include in their graph. See all those check boxes on the left there? Every one of those is an Anthropic model that METR and the public have data for, but that METR chose not to include in their report.
</details>

因此出于报告的目的，METR 认定：Haiku 模型不算，Fable 模型不算；Sonnet 3.7 和 4.5 算，但 4、4.6 和 5 不算；Opus 3、4、4.5 和 4.6 算，但 4.1 不算，4.7 及更高版本也都不算；Mythos Pre、Mythos Pre-Early 和 Mythos 5 算，但 Mythos 5.1 不算。这对你来说听起来诚实吗？因为对我来说这听起来极其可疑。

<details>
<summary>Original English</summary>
So for the purposes of their report, METR decides that Haiku models don't count, Fable models don't count, Sonnet, 3.7 and 4.5 count, but 4, 4.6 and 5 do not. Opus 3, 4, 4.5 and 4.6 count, but 4.1 doesn't count and neither does 4.7 or higher. Mythos Pre, Mythos Pre-Early, and Mythos 5 count, but mythos 5.1 doesn't. Does that sound honest to you? Because it sounds really shady to me.
</details>

如果你把这些模型包含在报告中，左右两侧之间的巨大差异就会突然不复存在。通过选择哪些模型计入或不计入，你几乎可以把那些线条画成你想要的任何样子；而通过剔除不同的模型，我甚至可以让它看起来像是进展随时间推移放缓了。

<details>
<summary>Original English</summary>
And if you do include those in the report, you suddenly no longer get a huge difference between the left side and the right side. By choosing which models do or don't count, you can make those lines look like almost anything you want, and by throwing out different models, I can even make it look like progress has slowed down over time.
</details>

### 缺乏科学依据的员工访谈与结语

你肯定会认为，证明加速的证据理应不仅限于基于挑拣出的模型集合所做的一项计算。在这份文件中确实有一个“AI 提速的证据”（Evidence of AI Speed Up）章节。问题在于，它只是一堆轶事以及对 Anthropic 员工的访谈集合，而如果 IPO 表现良好，这些员工都能大赚一笔。看看这个糟糕的小标题，引用如下：“访谈广泛支持 AI 增长率翻倍”，引用结束。

<details>
<summary>Original English</summary>
Surely you would think there would be more evidence of acceleration than just one calculation done on a collection of cherry pick models. And there is an "Evidence of AI Speed Up" section of this document. Problem is, it's just a collection of anecdotes and interviews with employees of Anthropic who all stand to make a lot of money at the IPO does well. Look at this crap subsection title: Quote, "Interviews Broadly Support AI Doubling The Rate of Growth," unquote.
</details>

接着他们给出了 11 位研究人员访谈的情感倾向。我可不是凭空捏造的，你们在屏幕上就能看到。其中有两人说：“是的，我认为相对于没有 AI 的工作，我的工作获得了 2 倍或更多的加速。”同样有两人回答“不”。有四人处于边界状态，而有三人根据 Claude AI 自己的判断“倾向于支持”。所以你的意思是，当赞成和反对的人数一样多，有三人“有点赞同，至少根据 AI 的看法是这样”，且回答“可能”的人数比其他任何回答都多时——在 AI 研究界这就叫作“广泛支持”？你在开玩笑吗？

<details>
<summary>Original English</summary>
Then they give the sentiment from 11 researcher interviews. I am not making this up. You can see it on the screen. Two of them say "Yes, I support a 2x or more acceleration in my work relative to working without AI." And two - the same number - say "NO". Four are borderline and three, according to Claude AI's own judgment, "lean yes". So you're telling me that when you get equal numbers of yes and no, three "kind of yes, at least according to what the AI thinks". And more "maybe" answers than any other - That counts as "Broad Support" in the AI research world? Are you kidding me?
</details>

这就是题为“AI 提速的证据”这一节中提供的证据。真的吗？就这些？听着各位，你们爱信什么见鬼的就信什么，但这绝不是科学。严谨的研究绝不是这么做的。坦白说，这让我感到恶心。我不是来给你们提供投资建议的。如果你想把钱投进这个 IPO，那是你的选择。但我至少希望你们能擦亮眼睛做出决定。我真是受够这些了。感谢观看。大家在外面都要多加小心。

<details>
<summary>Original English</summary>
And that's the evidence provided in the section titled "Evidence of AI Speed Up". Really? That's it? Look, folks, believe whatever the hell you want to believe, but this is not science. This is not the way valid research is done. It makes me sick, honestly. I'm not here to give you investment advice. If you want to put your money into this IPO, then that's your choice. But at least I hope you will make it with your eyes open. I'm just done with this. Thanks for watching. Let's be careful out there.
</details>

……在大家离开之前，在结束本视频前说两句简短的说明。通常情况下，像这种包含如此多技术细节的视频，我会再花几天时间来制作。我只是觉得在 IPO 之前发布这个视频很重要，这样人们在决定投资与否之前就有机会看到它。所以很抱歉这比我预期的要粗糙一些。希望这不至于太难理解，也希望我没有遗漏任何如果我有充足时间深入研究所能发现并涵盖的内容。感谢各位坚持看到最后。希望你们以后能再来看我有更充裕时间打磨的视频。大家在外面都要多加小心。

<details>
<summary>Original English</summary>
...Before you go, quick couple of notes before I end the video. Normally, I would have spent another few days on this video - on any video with this much technical detail. I just thought it was important to get this video out before the IPO so people had a chance to watch it before deciding to invest or not. So, sorry this was sloppier than I would have preferred it to be. Hopefully it wasn't too hard to follow, and I didn't leave anything out that I would have found and included if I'd taken the amount of time the subject really deserved. Thanks for sticking out to the end. I hope you come back for some future video that I had more time to work on. Let's be careful out there.
</details>