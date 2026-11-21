---
author: Dwarkesh Patel
date: '2026-11-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1NHPDzpfR6Y
speaker: Dwarkesh Patel
tags:
  - artificial-general-intelligence
  - recursive-self-improvement
  - reinforcement-learning
  - machine-learning-research
title: 递归自我改进已经开启：AI研发自动化与超级智能加速
summary: 作者基于可验证领域及数学突破的进展，更新了关于超级智能到来时间的判断。文章探讨了AI自动化研发带来的速度、智力与规模提升，分析了软件奇点与火花情景，论证了RL环境泛化能力，并在附录中回应了持续学习、代理指标、数据与实验算力瓶颈等质疑。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Dario Amodei
  - Toby Ord
  - Sholto Douglas
  - Chris Olah
  - Ajeya Cotra
  - Mark Zuckerberg
  - Jerry Han
  - Noam Shazeer
  - Ilya Sutskever
companies_orgs:
  - METR
  - Anthropic
  - OpenAI
  - ByteDance
  - DeepSeek
  - Magic
  - Nvidia
  - Citadel
  - Jane Street
products_models:
  - Claude
  - Claude 7
  - Claude Code
  - Codex
  - GPT-2
  - GPT-3
  - GPT-3.5
  - GPT-4
  - GPT-6
  - GPT-6 Astra
  - GPT-7
  - DeepSeek V4 Pro
  - AlexNet
media_books:
  - East of Eden
status: evergreen
---
### 超级智能时间线的重大更新

>> 如果你在今年早些时候问我距离超级智能还有多远，我大概会说至少还要大半个十年。但过去三个月里，我的观点发生了翻天覆地的变化。无论在播客中还是私下里，我一直在与人们辩论这个问题；当然，我也一直在密切关注 AI 在可验证领域的进展，并思考这对 AI 研究本身意味着什么。
<details><summary>Original English</summary>
>> If you had asked me earlier this year how far away 
we are from superintelligence, I'd probably have  
said at least the better part of a decade.
But over the last three months,  
I've updated my views a ton.
I've been debating people both  
on and off the podcast about this question, and 
of course, I've been watching the progress of  
AI on verifiable domains and thinking about 
what that implies for AI research itself. 
</details>

>> 我现在认为，我们距离出现与最优秀人类水平相当的 AI 研究智能体只有两三年，甚至可能只有几个月的时间了。我也逐渐相信，AI 研发的自动化将在一年内压缩如此巨大的进展，以至于在此之后不久——大约在 2030 年之前，甚至可能最早在明年——我们就会拥有在各个领域至少能比肩最优秀人类专家的 AI。我知道这是一个极其惊人的断言，甚至在几个月前我自己都不会相信。让我来为你梳理一下我的思维转变过程。
<details><summary>Original English</summary>
>> And I've come to the view that we're only 
a couple of years away, and possibly only  
a couple of months away, from AIs that are 
as good as the best humans at AI research. 
And I've also come to believe that automating 
AI research will compress so much progress into  
a single year that soon thereafter, so by 
2030, and plausibly as early as next year,  
we'll have AIs that are at least as good 
as the best human experts in every field. 
I know this is a wild claim, and it's one that I 
myself didn't believe even a couple months ago. 
Let me walk you through how 
my thinking has changed. 
</details>

### 前沿研发中的 AI 加速现状

>> 在我们深入探讨关于未来走势的推测性论点之前，我想先指出：在前沿阵地上，AI 已经在极大地加速进一步的 AI 进展。例如，独立评估组织 METR 曾在 Anthropic 进行了为期三个月的实地调研，随后得出结论：Anthropic 在目标明确任务上的 AI 进展速度是一年前的两倍，并且“当前这种加速的大部分可能归因于 Anthropic 广泛使用 AI 进行研发”。
<details><summary>Original English</summary>
>> Before we get into the more speculative arguments 
about what will happen in the future, I want  
to point out that AI is already dramatically 
speeding up further AI progress at the frontier. 
For example, METR, which is an independent 
evaluation organization, spent three months  
embedded inside of Anthropic, and afterwards 
concluded that Anthropic's rate of AI progress  
on well-scoped tasks is 2x what it was a year ago, 
and that a, quote, majority of this acceleration  
today is likely attributable to Anthropic's 
extensive use of AI to do R&D, end quote. 
</details>

>> OpenAI 在九月份发表了一篇相关的博客文章，展示出在 OpenAI 研究人员中，使用 AI 程度最高的前 10% 用户，其内部编程智能体的使用成本从夏初的大约每天 1,000 美元激增至八月底的每天 7,000 美元以上。同样在九月，Anthropic 也发布了一篇关于自身 AI 提效的类似文章。他们报告称，Claude 现在主导了 Anthropic 26% 的 AI 研发工作，而在今年二月时这一比例还不足 1%。
<details><summary>Original English</summary>
>> OpenAI published a blog post about this in 
September, where they showed that the heaviest  
10% of AI users amongst OpenAI's researchers 
went from using about $1,000 a day of internal  
coding agents at the beginning of the summer 
to over $7,000 a day by the end of August. 
And also in September, Anthropic put 
out a similar post on its own AI uplift. 
They reported that Claude now leads 
26% of Anthropic's AI R&D work,  
up from under 1% as recently as February.
</details>

### 数学突破及其对机器学习研究的启示

>> 在思考让 AI 自动化 AI 研究会产生多大的影响、以及这会如何加快 AI 进展时，对我而言一个非常重要的认知更新，就是亲眼目睹了 AI 模型在数学领域能力的爆发式增长。现在的 AI 解决目标明确的数学问题，就像热刀切黄油一样轻松自如。仅仅两年前，我还曾问过 Dario，为什么大语言模型无法利用它们跨多个领域的庞大知识库把不同想法联结起来，从而做出新的发现。
<details><summary>Original English</summary>
>> In thinking about how big a deal it would 
be for AIs to automate AI research and 
how much that would speed up AI progress,  
a really important update for me has just been  
seeing how fast the capabilities of AI 
models in mathematics have exploded. 
Current AIs are slicing through well-scoped 
problems in math like a hot knife through butter. 
It was only two years ago that I asked 
Dario why LLMs aren't able to use their  
vast knowledge across so many different 
fields in order to connect together different  
ideas and make new discoveries.
</details>

>> 看吧，现实已经来到了眼前。在数学这样一个完全可验证的领域，AI 进行搜索和匹配式发现的规模如此之大，以至于世界顶尖数学家和计算机科学家苦思冥想数十年试图解决的数百个重要成果，现在被当成烘托未来模型发布的支线任务源源不断地产出。这一进展发生的速度实在惊人。就在 2023 年，这些模型还无法稳定地进行四位数加法。2024 年，它们在高中数学竞赛题面前几乎束手无策。到了 2025 年，它们已经能在国际数学奥林匹克竞赛中摘得金牌。再到今年早些时候，它们终于开始攻克一些小众的开放式未解问题；而就在一个月前，OpenAI 用 88 小时解决了一个千禧年大奖难题。
<details><summary>Original English</summary>
>> And lo and behold, here we are. 
In a wholly verifiable domain like mathematics, 
AIs are doing the search-and-match discovery to  
such a great extent that hundreds of important 
results, which the top mathematicians and computer  
scientists in the world had spent decades 
trying to resolve, are being churned out  
as side quests to hype up future model releases.
It's crazy how fast this progress has happened. 
As recently as 2023, these models 
couldn't reliably add four-digit numbers. 
In 2024, they could barely solve any 
problems in a high school math competition. 
In 2025, they could win a gold medal 
at the International Math Olympiad. 
To earlier this year, where they finally 
started to solve some niche open problems,  
to a month ago, where OpenAI solved a 
Millennium Prize problem in 88 hours. 
</details>

>> 这让我想起小说《伊甸之东》里的一句话：“诸神的陨落唯有一点可以笃定。他们绝非缓缓跌落，而是轰然崩塌、粉身碎骨。”诚然，目前的进展极大地偏向于数学中重在验证的部分，比如寻找反例，而不是提出全新的理论。Toby Ord 最近就此写了一篇非常出色的文章，他写道：“虽然当前的 AI 系统正开始实现数学证明的自动化，但目前极少有证据表明它们能够提出有力的问题，或者开辟深刻的全新数学探索领域。”然而，同一句话换一种方式表达其实就是：当前的 AI 系统在不具备提出有力问题或开辟深刻新探索领域的能力下，依然解决了一个千禧年大奖难题。
<details><summary>Original English</summary>
>> I'm reminded of a line from the novel East 
of Eden, quote, "And there is one sure  
thing about the fall of gods.
They do not fall a little. 
They crash and shatter." End quote. Now, it's 
true that progress has skewed disproportionately  
towards the verification-laden parts of 
mathematics, like finding counterexamples,  
rather than, say, coming up with new theory.
Toby Ord recently wrote a great essay about this. 
He writes, quote, "While current AI systems 
are starting to automate mathematical proof,  
there is currently very little evidence 
that they can ask powerful questions or  
find profound new fields of mathematical enquiry."
End quote. But another way to say that same exact  
sentence would be this: Current AI systems have 
solved a Millennium Prize problem, all without  
the ability to ask powerful questions or find 
profound new fields of mathematical inquiry. 
</details>

>> 这种解决界定清晰问题的能力，对机器学习研究的影响将远远大于对广义数学的影响。因为数学研究的目标不仅在于证明或推翻长串的猜想，而是在于拓展人类对数学概念的理解。提出拓扑学或群论的思想，甚至更早的笛卡尔坐标系，其意义远胜于准确知晓从 n 个点中能构成多少对距离为 1 的点对。我们之所以在意这些深奥问题，主要是因为它们可能催生新的数学理论。
<details><summary>Original English</summary>
>> And this ability to solve well-scoped 
problems is going to be an even bigger  
deal for machine learning research than it 
has been for mathematics broadly construed. 
That's because the goal of mathematics research 
is not just to prove or disprove long lists of  
conjectures, but rather to extend the human 
understanding of mathematical concepts. 
Coming up with the idea of topology or 
group theory, or going back even further,  
the Cartesian grid, matters far more than 
knowing exactly how many one-unit-apart  
pairs you can make from n dots.
We mainly care about such abstruse  
questions insofar as they might 
elicit new mathematical theory. 
</details>

>> 但在 AI 研究中，优先级完全颠倒了过来。AI 实验室最关心的，是任何新的算法配方在经验上能否让训练更高效，或者诱导出更聪明的模型。他们并不在乎为了理论本身的纯理论研究，而且过去十五年来我们在深度学习领域取得的所有进展，本来也没有需要多少新理论。那种仅仅去硬啃各类随机猜想的做法，在数学研究里或许价值有限，但在机器学习中却具有无比巨大的价值。
<details><summary>Original English</summary>
>> But in AI research, the 
priorities are exactly reversed. 
AI labs mainly care about how any new 
algorithmic recipe empirically makes  
training more efficient or elicits smarter models.
They don't care about theory for its own sake,  
and all the progress that we've made in 
deep learning over the last decade and a  
half has not required much new theory anyways.
The equivalent of just grinding through random  
conjectures would be enormously 
valuable in machine learning in  
a way that it just isn't for mathematics.
</details>

>> 实际上，AI 研究与当前 AI 格外擅长的这类数学进展惊人地相似，那就是：凭借难以置信的执着，加上联结众多邻近领域想法的超人类能力，收割海量的低垂果实。
<details><summary>Original English</summary>
>> AI research is actually surprisingly similar 
to the kind of mathematical progress which 
current AIs are disproportionately good at,  
which is unlocking a ton of low-hanging fruit by 
applying a combination of incredible persistence  
and a superhuman capacity to connect 
ideas from lots of adjacent domains. 
</details>

### 从 Transformer 的发明看拼图与实验能力

>> 例如，我们来谈谈 Transformer 架构。正是这项重大突破开启了现代大语言模型的时代。我的朋友 Sholto Douglas 本身就是一名 AI 研究员，他有一篇常年半成品的博客文章，解释了人们本可以在实际发明 Transformer 的两年前就把它创造出来。或许这个视频能促使他别再拖延，把文章写完。不过眼下，我先简要总结一下我和他探讨过的文章内容。
<details><summary>Original English</summary>
>> For example, let's talk about 
the transformer architecture. 
This is the big breakthrough 
that enabled modern LLMs. 
My friend Sholto Douglas, who is an AI 
researcher himself, has this perennially  
half-finished blog post where he explains 
how you could have invented the transformer  
two years earlier than people actually did.
And maybe this video will finally get him  
to quit stalling and complete his essay.
But in the meantime, I'll summarize a bit  
of the discussion I had with him 
about the contents of his essay. 
</details>

>> 在 2017 年 Transformer 论文发表之前，许多研究人员就已经确定将注意力机制作为更好地并行化训练并在更长序列间传递信息的方式。当时活跃的研究员 Chris Olah 曾说过：“在当时，我的感觉是 Transformer 架构是许多想法的自然融合，比如注意力机制和残差网络，它们原本各自都很有效，只是这次被推向了相当激进的极致。”换句话说，对于活跃在该领域的研究者而言，核心模块没有一个是出乎意料的。
<details><summary>Original English</summary>
>> Before the transformer paper was published 
in 2017, many researchers had already  
identified attention as a way to 
better parallelize training and  
communicate information across longer sequences.
Chris Olah, who was an active researcher at the  
time, has said, quote, "At that time, my sense is 
that the transformer architecture was a natural  
combination of many ideas like attention and 
residual networks, which had independently been  
effective, taken to quite aggressive lengths."
End quote. In other words, none of the  
core pieces were a surprise to 
researchers active in the field. 
</details>

>> 那么人们当时为什么没能早点发明出 Transformer 呢？原因之一在于，只有当你把半打额外的调整与微创新拼合在一起时，这种新架构才明显优于当时的最佳技术（SOTA）。尽管这些零散机制在文献中几乎都已经公开了数年，但没有人知道如何恰到好处地将这些拼图组合起来。要做到这一点，当然需要出色的研究品味，但它同样需要做海量细微的实验。
<details><summary>Original English</summary>
>> So then why didn't people 
invent the transformer sooner? 
One reason was that this new architecture 
was only obviously better than the state of  
the art at the time once you connected together 
half a dozen additional tweaks and innovations. 
And though almost all of them had been 
known in the literature for years,  
no one knew how to combine these puzzle 
pieces together in just the right way. 
Doing so required great research 
taste, of course, but it also required  
tons and tons of small experiments.
</details>

>> 而我上面所描述的——持之以恒且智能地在数十种不同想法组合中进行匹配——正是 AI 在数学贡献中所展现出的那种超常技能。总而言之，即便像 Transformer 这样自 2012 年 AlexNet 开启深度学习革命以来可称机器学习领域最大突破的成果，如果当年 Chris Olah 让 Claude 7 竭尽全力去把注意力机制做得更好用，它也是能被 Claude 7 发明出来的。
<details><summary>Original English</summary>
>> But what I've just described above, 
which is persistently and intelligently matching 
dozens of different combinations of ideas,  
is exactly the kind of capability that AIs 
have shown themselves disproportionately  
skilled at in their contributions in mathematics.
This is all to say that even the transformer,  
which is arguably the biggest breakthrough 
in ML since AlexNet kicked off the deep  
learning revolution in 2012, is the kind of 
thing that Claude 7 could have invented if  
Chris Olah asked it to try really hard to 
get this attention thing to work better. 
</details>

### 时间预测：2028 年中位数与起飞概率

>> 当然，我想澄清的是，AI 研究的某些部分在可验证性上确实不如数学。这就是为什么 OpenAI 即使手握显然能自主解决千禧年难题的模型，也并没有解雇所有的研究人员。但我认为，AI 研究的可验证性已经足够高，AI 很快就能在其中达到顶尖人类的水平。解释其中的原因需要深入探讨 AI 研究实际运作的技术细节；因为这些细节虽有趣但偏技术性，我把它们留到了结论之后。所以如果你感到好奇并想了解，可以一直看到视频结尾。
<details><summary>Original English</summary>
>> Now, I wanna clarify that some parts of AI 
research are, in fact, less verifiable than math. 
That's why OpenAI hasn't 
fired all of its researchers,  
despite having a model that can apparently 
autonomously solve Millennium Prize problems. 
But I think that AI research is 
verifiable enough that AIs will  
soon be as good at it as the best humans.
Now, explaining why requires getting into  
the nitty-gritty of how AI research 
actually works, and because those  
details are interesting but technical, 
I've saved them for after the conclusion. 
So if you're curious and you 
wanna hear them, you should just  
keep watching until the end of the video.
</details>

>> 不过现在，我先给出关于何时能出现此类 AI 的估计。如果要我选出自动化研究员在进行 AI 研究方面比肩最顶尖人类 AI 研究员的中位数年份，我猜是 2028 年——前提是各大 AI 实验室全速前进，没有自我有意放慢脚步，也没有受到政府的阻碍。
<details><summary>Original English</summary>
>> But in the meantime, I'm gonna give you my 
estimate of when we're gonna have such AIs.
If I had to pick my median year for when  
automated researchers will be as good as the very 
best human AI researchers at doing AI research,  
I'd guess 2028, and that's assuming that 
the AI labs go full steam ahead and don't  
slow themselves down intentionally or 
aren't slowed down by a government. 
</details>

>> 为什么我认为 AI 能在两年内达到这种水平？因为在每一个我们能够核验答案并让 AI 进行成千上万轮练习的领域——例如编程竞赛或界定清晰的未解数学题——它们都在短短几年内从弱于大多数人类飞跃为超越最顶尖人类。正如我将在结论之后论证的那样，AI 研究恰好具备完全相同的可验证属性。
<details><summary>Original English</summary>
>> Why do I think that AIs could 
get this good within two years? 
Well, in every domain where we can check answers 
and give AIs thousands of rounds of practice,  
for example, competitive programming 
contests or well-scoped open math problems,  
they've gone from worse than most humans to better 
than the best humans within just a few years. 
And as I'll argue after the 
conclusion, AI research has  
exactly the same verifiable properties.
</details>

>> 当然，顶尖人类 AI 研究员之所以能够表现优异，很大一部分能力是无法被直接验证的，例如他们提前数年押注正确研究方向的能力。但正如我们在数学领域已经看到的那样，模型所能泛化的范围远远超出了它们被直接训练的内容。OpenAI 的模型显然不是靠解决其他千禧年大奖难题训练出来的；它是靠训练大量野心较小、更易下手的数学题，然后从这些题目一路泛化，最终攻克了此前从未有人类解决过的难题。我认为在 AI 研究中也是同理：在可验证的研究任务上进行成千上万轮练习，加上新一代模型普遍比上一代更聪明的事实，两相结合将使模型即便在无法直接验证的 AI 研究环节中也变得出类拔萃。
<details><summary>Original English</summary>
>> Of course, a big part of what makes the 
top human AI researchers really good at 
their job can't be directly verified,  
for example, their ability to bet years in 
advance on the right research direction. 
But as we've already seen in 
mathematics, models generalize  
far beyond what they were directly trained on.
OpenAI's model was obviously not trained by  
solving other Millennium Prize problems.
It was trained on lots of less ambitious,  
more tractable math problems, and from those, 
it generalized all the way to solving a  
problem which no human had ever cracked before.
I'd expect the same in AI research, where the  
combination of thousands of rounds of practice on 
verifiable research tasks, plus the fact that each  
new generation of models is broadly smarter than 
the last, will make models excellent even at the  
parts of AI research that we can't directly check.
</details>

>> 这里我想明确一点：达到这一里程碑耗时更久的可能性相当大，因为 AI 研究的某些重要部分可能依然难以自动化。这种事情提前预测本就极为困难，我猜测至少有 25% 的概率要到 2032 年之后才会发生。但相反地，我也认为进展速度可能快得多，我们在 2027 年就能达到这一里程碑。
<details><summary>Original English</summary>
>> Now, I wanna be clear that there's a pretty decent 
chance that hitting this milestone takes 
longer because some important parts of AI 
research remain hard to automate.
This is just a very hard thing to  
try to predict in advance, and I'd guess 
that there's at least a 25% chance that  
it doesn't happen until after 2032.
But conversely, I also think that  
things could happen much faster, 
and we hit this milestone in 2027. 
</details>

>> 我认识的一些消息最灵通的研究者——他们在过去几年中的预测记录非常好——预计 AI 最早在明年就能在 AI 研究上击败最顶尖的人类。此外，如果把 METR 指出 Anthropic 的 AI 进展速度相比一年前翻倍的最新报告代入起飞模型，直接得出的推论也是 2027 年。正如往期嘉宾 Ajeya Cotra 在关于该报告的博客文章中所说：“如果我们按字面意义接受 AI 目前几乎使 AI 能力进展速度翻倍，并假设来自 AI 的加速是平滑的，这在朴素推演下意味着我们将在一年内达到极度超级智能。”因此，我的中位数年份之所以不是 2027 年，只是因为我无法确定这种直接建模到底有多准确。但对于明年就可能达成这一里程碑的世界，我们不应感到意外，并且应当做好准备。
<details><summary>Original English</summary>
>> Some of the most well-informed researchers 
I know, people who have a very good track  
record of making predictions over the 
last few years, expect AIs to beat the  
best humans at AI research as early as next year.
And 2027 is also the straightforward implication  
of putting the new report from METR that says 
that Anthropic's rate of AI progress has doubled  
from a year ago into a takeoff model.
As former guest Ajeya Cotra put it in  
a blog post about this report, quote, "If we 
take it at face value that AI is now nearly  
doubling the rate of AI capabilities progress 
and assume that acceleration from AI is smooth,  
this naively implies that we would reach extreme 
superintelligence within a year," end quote. 
So the reason my median year is not 2027 is just 
that I'm uncertain about how accurate this kind  
of straightforward modeling is.
But we should not be surprised,  
and we should be ready for a world in 
which we get to this milestone next year. 
</details>

### 加速三大支柱：速度、智力与规模

>> 一旦 AI 在 AI 研发上比肩顶尖人类，由于三个重要原因，算法进展将会大幅提速。其一，AI 的速度要快得多；其二，它们每一个都会非常聪明；其三，它们的数量将极其庞大。
<details><summary>Original English</summary>
>> Once AI is as good as the best humans at AI 
research, algorithmic progress will get a lot  
faster for three important reasons.
One, the AIs will be much faster. 
Two, each of them will be very smart.
And three, there will be a lot more of them. 
</details>

>> 我们先从“更快”谈起。今天的 AI 已经能以大约 10 倍于人类的速度工作，而且自动化研究员还将昼夜不停地运转，周末和节假日也不休息。结果就是，单个自动化研究员每个自然周所能塞进的工作量，大约是人类研究员的 50 倍。当然，这并不意味着 AI 的整体进展就会立刻加速 50 倍。这些自动化研究员仍然会受到实验算力的瓶颈限制，因为实验本身跑得并没有变快。因此，这里会出现边际收益递减。但即使存在极其陡峭的边际递减，单凭这一点也会让算法进展比目前快上许多倍。
<details><summary>Original English</summary>
>> Let's start with faster first.
Today's AIs already do work at  
about 10 times human speed, and automated 
researchers would also be working around  
the clock, nights and weekends included.
As a result, each individual automated researcher  
will be cramming roughly 50 times more work every 
calendar week than a human researcher can do. 
Of course, that doesn't mean that AI 
progress will immediately accelerate 50x. 
Those automated researchers would still be 
bottlenecked by compute for experiments,  
which aren't running any faster.
So there would be diminishing returns. 
But even with extremely steep diminishing returns, 
this alone would make algorithmic progress proceed  
many times faster than it currently does.
</details>

>> 这甚至还没把另一个事实考虑在内：在我所描述的情景中，每一个自动化研究员在 AI 研究和工程能力上，都将至少达到今天最优秀人类的水平。在我看来，前沿实验室大约 80% 的算法进展是由其顶尖的 50 名研究人员推动的。扎克伯格愿意豪掷数亿美元来招揽行业顶尖人才绝非无缘无故。因此，由于这家全自动化公司中的每一位工程师和研究员都处于当今前沿 AI 实验室中最优秀人类的水准，算法进展又将获得一轮巨大提速。
<details><summary>Original English</summary>
>> And this is before we account for the fact that 
in the scenario I'm talking about, every automated 
researcher will be at least as good at AI research  
and engineering as the very best humans today.
My sense is that around 80% of the algorithmic  
progress at a given frontier lab is 
driven by its 50 top researchers. 
It's not for nothing that Zuckerberg was willing 
to pay hundreds of millions of dollars to acquire  
the best talent in the industry.
And so you get another big speedup  
in algorithmic progress from the fact that 
every single engineer and researcher in this  
automated company will be at the level of the 
very best humans in today's frontier AI labs. 
</details>

>> 最后，自动化研究员的数量将多得多。诚然，单纯往一个问题上堆砌更多人力并不总是管用。例如，一个智能体集群写出一本绝妙小说的速度，大概不会比单个智能体快多少。但其他任务则要适合并行化得多。例如看看我展示的这个叠层动画，它展示了一群不同的 Claude 如何通力协作来形式化证明费马大定理。这项伟业包含成千上万个模块化子任务，每个子任务都能独立完成，且每个智能体都可以在本地检验自己的工作是否成功。
<details><summary>Original English</summary>
>> And finally, there will be a 
lot more automated researchers. 
Now, throwing more workers at 
a problem isn't always helpful. 
For example, a swarm of agents probably isn't 
gonna be able to write a great novel much  
faster than a single agent could.
But other tasks lend themselves  
much more to parallelization.
For example, look at this animation  
that I'm overlaying, which shows a 
bunch of different Claudes working  
together to formalize Fermat's Last Theorem.
This feat had thousands of modular subtasks,  
each of which could be completed independently 
and where each agent could locally check  
whether their work had succeeded.
</details>

>> AI 研究更接近于形式化一个定理，而不是写小说，因为其中有大量独立的模块化工作要做，并且存在可验证的进展代理指标。这意味着智能体集群可以尝试一千种不同的方法，看看哪种表现最好，而且他们可以针对流水线的每个不同部分独立进行尝试。AI 公司如今就已经由数十个不同的团队组成，各自独立研发模型开发的不同环节：例如一个团队改进预训练数据的过滤方式；另一个团队设计某种特定的合成强化学习环境；还有一个团队编写更好的注意力算子内核，等等。
<details><summary>Original English</summary>
>> AI research is closer to formalizing 
a theorem than it is to writing a novel, because 
there's a lot of independent modular work to do,  
and there are verifiable proxies for progress.
That means a swarm of agents can try out a  
thousand different approaches and see which one 
performs best, and they can do this independently  
for each different part of the pipeline.
AI companies are already made up of dozens  
of different teams working independently 
on different parts of model development. 
One team, for example, improves how 
the pretraining data is filtered. 
Another designs a particular 
kind of synthetic RL environment. 
Another writes a better 
attention kernel, and so on. 
</details>

>> 在这类工作流能够独立完成和验证的领域，投入大量持之以恒的爬山算法式智能体，往往会极大地加快进展。同样，仅仅增加更多并行的研究员也会面临极度陡峭的边际递减。任何有过团队合作经历的人都知道，拥有 10 万名协作者并不意味着你的速度会加快 10 万倍，甚至可能连 100 倍都达不到。但鉴于 AI 研究的特性，拥有数量级提升的自动化劳动力却不能让速度加快至少数倍，这是难以置信的。
<details><summary>Original English</summary>
>> In domains like this, where different streams 
of work can be done and checked independently,  
dumping in lots of persistent hill-climbing 
agents tends to speed up progress a lot. 
Again, there will be steeply diminishing returns 
just from adding more parallel researchers. 
Anybody who's ever worked on a team before 
knows that having 100,000 collaborators  
doesn't mean that you'll go 100,000 times 
faster, probably not even 100 times faster. 
But given the nature of AI research, it's 
implausible that you wouldn't be going at  
least a couple times faster from having 
orders of magnitude more automated labor. 
</details>

### 后续演进：“软件奇点”与“火花”情景

>> 因此，更快、更聪明且数量更多的自动化研究人员相结合，将极大地加速 AI 进展。但这种步伐能否持续下去？它是会变得更快，还是会放缓？这个问题甚至比初始速度本身更为重要。这里存在两种相互竞争的趋势，后续的进展速度取决于哪一种最终占据上风。
<details><summary>Original English</summary>
>> So the combination of faster, smarter, 
and more automated researchers will  
speed up AI progress a lot.
But will this pace continue? 
Will it get even faster, or will it slow down?
That question is even more important than  
what the initial pace actually is.
Two competing trends are relevant here,  
and the subsequent rate of progress will come 
down to which one ends up being more powerful. 
</details>

>> 一方面，由于递归自我改进（RSI），自动化研究员会不断变得更快、更聪明、数量更庞大；另一方面，随着所有容易的想法都被智能体集群收割殆尽，AI 研究的难度将变得越来越高。顺便提一句，想法越来越难找是一个已经发生的现象：AI 公司每年必须将研发算力翻两番、人员规模翻一番，才仅仅能够维持同样的进展速度。
<details><summary>Original English</summary>
>> On the one hand, because of RSI, automated 
researchers will continue getting faster,  
smarter, and more plentiful.
On the other hand, AI research  
will be getting harder and harder as all 
the easy ideas get eaten away by the swarm. 
By the way, ideas getting harder to 
find is a thing that already happens. 
AI companies have to quadruple their R&D compute 
and double their workforce every single year  
just to maintain the same rate of progress.
</details>

>> 因此，如果 AI 变聪明的速度快于想法枯竭变难的速度，我们就会迎来所谓的“纯软件奇点”。在这种情景下，即便不增加算力，AI 集群也能迅速造出越来越聪明的自身版本，直到在短短几个月内，我们最终得到一个逼近当前芯片物理极限的超级智能。但如果想法变难的速度快于 RSI 让 AI 更擅长研究的速度，我们就会迎来我称之为“火花”的情景：我们将在短短一个自然年内取得相当于当前速度三到六年的 AI 进展。随后一切会趋于平缓，直到我们建造出更多算力，因为哪怕是这些超级天才级的自动化研究人员，也需要运行更大的实验才能取得进一步的突破。
<details><summary>Original English</summary>
>> So if the rate at which AI gets smarter is 
faster than the rate at which ideas 
get harder to find, then we'd get 
something called the software-only singularity.
In this scenario, even without increasing compute,  
the AI swarm rapidly makes smarter 
and smarter versions of itself until,  
within a matter of months, we end up with 
a superintelligence that scrapes against  
the physical limits of our current chips.
But if ideas get harder to find faster than  
RSI makes AIs better at research, we'd end 
up with something which I'd call a spark. 
We'd get something like three 
to six years of AI progress  
at the current rate in a single calendar year.
And then things would simmer down until we build  
more compute, as even these super-genius automated 
researchers need to run bigger experiments before  
they can make further breakthroughs.
</details>

>> 至于到底会发生哪一种，我认为基本五五开。如果非要预测，我认为“火花”情景和“纯软件奇点”各占 50% 的可能性。但需要明确的是，即便在“火花”情景下——我们在自动化 AI 研究后的第一个自然年里实现大约四年的进展——一切感觉起来也依然会极其疯狂。那将是在短短 12 个月内实现如同从 GPT-3.5 到 GPT-6 Astra 的巨大跨越。
<details><summary>Original English</summary>
>> As to which one will actually happen, 
I think it's basically a coin toss.
If pressed, I'd give a 50% chance to  
the spark scenario and a 50% chance 
to the software-only singularity. 
But to be clear, even in the spark scenario, 
where we make something like four years of  
progress in the first calendar year after we 
automate AI research, things would feel insane. 
That's a jump as big as GPT-3.5 
to GPT-6 Astra in just 12 months. 
</details>

>> 提醒一下这种跃迁所压缩的进展规模：GPT-3.5 能够写出一首过得去的五行打油诗，能自动补全一个简单的 Python 函数，但除此以外，它基本上是一个毫无用处的玩具；而 Astra 则能从零开始构建完整的电子游戏，源源不断地产出足够获得菲尔兹奖的数学成果，多到让我们完全脱敏。在过去的四年里，我们见证了从学龄前儿童到博学实习生的跃升；如果再发生一次如此巨大的飞跃，而起点放在 2027 或 2028 年，你很可能会得到一个在哪怕稍微具备可验证性的领域里都全面碾压人类的心智。
<details><summary>Original English</summary>
>> To remind you of the scale of progress 
that this leap would compress,  
GPT-3.5 was able to write a passable limerick 
and autocomplete a trivial Python function,  
but otherwise, it was mostly a useless toy.
Whereas Astra can build whole video games  
from scratch and churns out so many Fields 
Medal-worthy mathematical contributions  
that we become totally desensitized.
In the last four years, we've gone from  
a preschooler to a savant intern.
If you made another jump that big,  
but starting in 2027 or 2028, you'd probably 
get a mind which would be vastly superhuman  
in domains that are even slightly verifiable.
</details>

>> 例如，它在构思下一代 AI 加速芯片方面会比英伟达更强；如果给予它平等的市场准入机会，它赚的钱将超过当前由人类构成的 Citadel 和 Jane Street；如果你给它远程访问材料科学实验室的权限，它在寻找室温超导体方面会比全人类都做得更好。
<details><summary>Original English</summary>
>> For example, it'd be better than Nvidia at coming 
up with the next generation of AI accelerators.
It would make more money than the current human  
versions of Citadel and Jane Street if 
it was given equal access to the market. 
If you give it remote access to a 
materials science experiment lab,  
it'd be better than the rest of humanity at 
finding a room-temperature superconductor. 
</details>

### 数据中心训练如何泛化至现实世界

>> 此时你可能会问：“即使是在数据中心训练出来的超级智能，又怎么可能在那些人类专长建立在多年现实世界经验之上的领域中击败人类专家呢？”我们目前让 AI 变聪明的方式，是在数据中心内部对那些易于自动评分的任务进行强化学习。例如，AI 新写的一百万行代码是否通过了所有单元测试？AI 是否攻克了更多未解数学题？但现实世界的大多数领域显然并非如此。我最近在文章中提出过这个问题：我们如何训练一个 AI 真正擅长从零开始创办一家企业？又如何训练它打赢官司、在金融市场实现盈利交易、或者帮助候选人赢得选举？这些实际展开都需要与真实世界交互，你无法仅在数据中心内重现它们。
<details><summary>Original English</summary>
>> Now, at this point, you might say, "How will 
even superintelligence, which is trained in 
a datacenter, beat human experts in domains 
where the basis of that human expertise is  
years and years of real-world experience?"
The way we're currently making AI smarter  
is by RLing them on tasks that are easy to 
automatically grade from within a datacenter. 
For example, do the million new lines of code 
that the AI wrote pass all the unit tests? 
Did the AI solve more open math problems?
But of course, most of the world is not like this. 
I made this point in a recent essay.
How do we train an AI to get really  
good at building a business from scratch?
How about winning court cases or having a  
profitable day of trading in the markets 
or helping a candidate win an election? 
The rollout here requires interacting with 
the real world, and you can't recreate it  
from just within the datacenter.
</details>

>> 那么超级智能将如何精通这些事情呢？让我澄清一点：我认为我们不可能将每一个现实世界问题的答案直接硬编码进权重中。我的观点是，扩大强化学习训练规模将赋予 AI 快速适应新情境所必需的能力，即便是在上述难以验证的领域亦然。要真正精通任何复杂任务都需要两样东西：一是特定领域的知识，二是一组更通用的技能——也就是有能力的人类所具备的那种技能，比如能够寻找相关信息、制定计划、在犯错和困难中推进该计划、记录所学心得，以及与其他人协作。
<details><summary>Original English</summary>
>> So how will superintelligence get 
good at this kind of stuff?
Well, let me be clear. 
I don't think we can just bake the answer to 
every real-world problem into the weights. 
Rather, my claim is that scaling up RL training 
will give AIs the abilities necessary to ramp up  
quickly in new contexts, even in hard-to-verify 
domains like the ones mentioned above. 
Getting really good at any 
complex task requires two things. 
One is domain-specific knowledge, and the 
other is a more general set of skills,  
the kind of capabilities that capable humans have, 
like being able to seek out relevant information,  
make a plan, push forward on that plan through 
mistakes and obstacles, keep track of what you've  
learned, and collaborate with other people.
</details>

>> 在 RSI 期间，自动化工程师所构建的强化学习环境数量将比我们目前拥有的多出数万倍，而且这些环境的规模更大、运行周期更长、质量更高、更具开放性，覆盖范围也比当今的环境宽广得多。AI 将学会在难以想象的海量虚拟世界中穿行探索，这些虚拟世界与当今电子游戏相比，就如同布加迪威龙之于单马马车。这些游戏将比以往任何为人类娱乐而制作的场景更加困难、庞杂、宏大和逼真，它们将要求 AI 与其他 AI 团队在漫长的时间周期内展开合作或竞争。例如，一个 AI 可能会被投放到由数百万其他 AI 组成的模拟经济体中，并被要求合伙创立一家成功的公司。AI 绝不会停留在仅仅思考理想的公司架构上；它将经历一段涵盖数个世纪商业竞争的演化过程，以摸索出最优的组织管理技巧。
<details><summary>Original English</summary>
>> During RSI, automated engineers will build tens 
of thousands of times more RL environments 
than we have currently, and these will be  
far larger and longer-running and higher 
quality and more open-ended and covering  
a much wider range than today's environments.
The AIs will learn to make their way through  
unfathomable amounts of virtual worlds 
that are each to today's video games  
what a Bugatti is to a horse and buggy.
These games will be far more difficult and  
messy and sprawling and realistic than anything 
that has ever been made for human entertainment. 
They will require AIs to cooperate or compete 
with teams of other AIs over long periods of time. 
For example, an AI might be dropped into a 
simulated economy of millions of other AIs  
and told to co-found a successful company.
And it's not like the AI will be stuck just  
thinking about the ideal corporate structure.
It'll go through an evolutionary process that  
involves centuries of corporate competition to 
figure out the optimal organizational techniques. 
</details>

>> AI 还会根据科学、技术、政治和文化历史上发生过的一切进行无休止的回溯测试训练，涵盖历史上所有的发现、发明、战争、选举和季度财报。例如有这样一个预测训练任务：如果给 AI 一个不包含 1700 年之后任何信息的训练语料库——这远早于人类有望发现广义相对论的时间——AI 能否推导出广义相对论？另一个任务可能是：在给出截至 1962 年的每一篇报纸文章的前提下，AI 能否预测古巴导弹危机将如何演变？
<details><summary>Original English</summary>
>> The AIs will also train themselves on endless 
backtests of everything in the history of  
science and tech and politics and culture, 
every discovery, invention, war, election, 
and quarterly earnings that has ever happened.
For example, here's one prediction training task:  
Can the AI figure out general relativity 
given a training corpus that includes no  
information beyond 1700, which is far earlier 
than any human was on track to discover GR? 
Another task might be, given every single 
newspaper article until 1962, can AI predict  
how the Cuban Missile Crisis is going to unfold?
</details>

>> 而且，这些自动化研究人员改进的不仅仅是训练数据。他们还将通过在线学习和样本效率方面的突破，从根本上极大地改进基础学习算法本身——正如我稍后将讨论的，这两者都具有可验证的代理指标。正如人类在从数据中学习的效率和效果上远胜于当前的大语言模型一样，未来的 AI 在学习效率上完全可能会远远超越人类。
<details><summary>Original English</summary>
>> And it's not just the training data that these 
automated researchers will be improving.
They will also radically improve the basic  
learning algorithms themselves through 
breakthroughs in online learning and  
sample efficiency, both of which have 
verifiable proxies, as I'll discuss later. 
In the same way that humans are much more 
efficient and effective at learning from  
data than current LLMs are, future AIs could be 
far beyond humans at their learning efficiency. 
</details>

### 从可验证任务到通用能力的迁移

>> 那么，我为什么认为我们会看到从可验证任务向这些更通用技能的大量能力迁移呢？一个原因在于，即便目前的强化学习训练规模只有未来智能爆炸期间的万分之一或百万分之一，我们已经看到了大量的泛化表现。如果你让 Claude Code 或 Codex 去处理一个它从未见过的项目，它知道如何熟悉环境、理清各个组件的关系，进而着手处理颇具挑战性的任务。当然，要想量化模型在那些不易直接验证的任务上提升了多少是极其困难的，因为如果我们能量化，那些任务就成了可验证任务。但你可以直接去和一个新模型对话，并将它与旧模型做对比。根据我的个人经验，AI 在那些与代码或数学几乎无关的事情上的表现已经大有长进，比如协助我调研在写这篇长文时需要解答的抽象问题。
<details><summary>Original English</summary>
>> Now, why do I think we'll see lots 
of transfer from verifiable tasks  
to these more general skills?
Well, one reason is that even  
at one ten-thousandth or a millionth of 
the scale of RL training that will be  
happening during the intelligence explosion, 
we're already seeing lots of generalization. 
If you point Claude Code or Codex at a project 
that it's never seen before, it knows how to  
orient itself and figure out how everything fits 
together and then tackle an ambitious assignment. 
Of course, it's hard to measure how 
much models have improved at tasks  
that are not easily verifiable because if 
we could, those tasks would be verifiable. 
But you can just go talk to a new 
model and compare it to an old one. 
In my experience, AIs have gotten 
much better at things that have  
very little to do with code or math.
For example, helping me research the  
abstract questions I needed to 
answer while writing this essay. 
</details>

>> 支持迁移现象的另一项重大证据来自人类进化。我们通用的心智架构是由进化塑造的，而进化是一个检验标准极其粗糙的优化过程：你的基因究竟有没有传递下去？在远古生存环境中，影响该结果的任务不过是打猎、抵御捕食者以及维持你在部落中的地位等。与当今人类所能应对的任务相比，这些不过是沧海一粟。进化并没有专门针对让我们写出普利策奖获奖传记、制造先进半导体、领导数百万人口的国家或开创全新数学分支来进行针对性优化。但在为了让我们在热带稀树草原上生存而进行优化的过程中，进化打造出了一个通用学习系统。
<details><summary>Original English</summary>
>> The other big piece of evidence 
for transfer is human evolution. 
Our general-purpose mental architecture was 
developed by evolution, and evolution is an  
optimization process with a really crude verifier.
Did your genes pass on or not? 
In the ancestral environment, the tasks 
which influenced that outcome were things  
like hunting and fending off predators 
and keeping your standing in your tribe. 
These are a tiny subset of the kinds of 
tasks that humans are able to tackle today. 
Evolution did not specifically optimize us 
to be able to write a Pulitzer Prize-winning  
biography or make advanced semiconductors 
or lead nations of millions of people or  
come up with a new branch of mathematics.
But in optimizing us for survival on the savanna,  
evolution built a general-purpose learner.
</details>

>> 在训练这些 AI 时，我们也在执行类似的过程，所不同的是我们在深思熟虑地进行，使用的任务与在当今世界取得成功所需的技能更加息息相关。而且与自然进化不同，AI 公司还在训练过程中主动尝试提升泛化迁移能力，比如确保模型在那些被扣留于训练集之外的难题上性能有所提升。如果连盲目笨拙的自然进化都能通过构建一个有效在草原上繁衍的大脑而带来如此强大的能力迁移，那么 AI 公司全力打造一种能够快速适应新情境的灵活通用智能体，其进展理应走得深远得多。
<details><summary>Original English</summary>
>> And in training these AIs, we're running a similar 
process, except we're doing so deliberately with 
tasks that are much more closely related to the  
ones that are needed for success in today's world.
And unlike evolution, AI companies are trying to  
improve transfer during training, for example, by 
making sure that performance improves on difficult  
tasks that were held out of training.
If even dumb, blind evolution can get  
this much transfer out of building a mind that is 
effective at propagating itself in the savanna,  
then the deliberate effort that AI companies 
are putting into building a flexible and  
general intelligence that can rapidly ramp up 
in new contexts should advance much further. 
</details>

>> 诚然，即便是超级智能学习系统也无法在数据中心内部搞懂一切，所以即使是这些 AI，也需要一定的现实世界经验才能击败顶尖人类。但我认为它们获取这些经验的速度会远远快于人们的预期，并且在部署后的几个月内就能超越顶尖人类专家。坦白说，引导我形成这种直觉的原因之一是：我身边有许多二十多岁的朋友，我亲眼见证了他们在涉足基本零经验的全新领域后，取得了不可思议的成就，建立起全球领先的企业和事业。历史长河中同样挤满了极度能干的年轻人，他们在所处的世界中横扫千军。拿破仑在 27 岁时，就已对欧洲其他列强规模远大于己的军队接连取得胜利；洛克菲勒 25 岁时，在他涉足石油行业仅两年后，就在掌管全球最大的炼油厂之一。
<details><summary>Original English</summary>
>> Now, even a superintelligent learner can't 
figure out everything from inside a datacenter,  
so even these AIs would need some real-world 
experience before they can beat the best humans. 
But I think they'll be able to get that 
experience much faster than people expect  
and that they'll be able to beat top human 
experts within months of being deployed. 
And honestly, one of the things that's 
guiding my intuition here is that I have  
a lot of 20-something-year-old friends 
who I've watched accomplish incredible  
things and build world-leading companies and 
ventures in domains that they entered into  
with basically zero years of experience.
History is full of super-competent young  
people who ran circles around the 
world that they found themselves in. 
By the age of 27, Napoleon had stacked 
victory after victory against far larger  
armies from the other great powers of Europe.
By 25, just two years after he got into the  
oil business, Rockefeller was running 
one of the world's largest refineries. 
</details>

>> 洛克菲勒和拿破仑确实需要经验，但仅仅需要几年而已，不需要数十年。而无论这些人大脑中运行着怎样的机制，AI 都应该能够复制甚至超越。没有任何理由认为人类在“从经验中快速学习”上已经触碰到了天花板。此外，与拿破仑或洛克菲勒不同，AI 将在短短几个自然日内积累相当于数年部署期的上下文。例如，假设你想让这些未来的 AI 比现任 CEO 更好地管理一家财富 500 强企业，AI 能多快掌握这项工作？如果你允许它影子跟岗那位 CEO，在上班的第一天上午，它就能读完该公司历史上产生过的每一封邮件、Slack 消息和文档；到第一天结束时，它的分身已经并行访谈了每一位员工和主要客户。
<details><summary>Original English</summary>
>> Rockefeller and Napoleon needed experience, yes, 
but only a couple years' worth, not decades. 
And whatever was going on 
inside these guys' brains,  
an AI should be able to replicate or even exceed.
There's no reason to think that humans are at the  
ceiling of learning quickly from experience.
Furthermore, unlike Napoleon or Rockefeller,  
AI's gonna accumulate years of deployed 
context in just a few days of calendar time. 
For example, imagine that you wanted 
these future AIs to run a Fortune  
500 company better than its current CEO.
How quickly could the AI ramp up at this job? 
Well, if you let it shadow 
that CEO, on its first morning,  
it could read every email and Slack message 
and document that the company's ever produced. 
By the end of its first day, copies 
of it have interviewed every employee  
and major client in parallel.
</details>

>> 显然，它们无法获取那些需要经历数月真实物理时间才能收到的反馈，比如下个季度的财报表现到底如何。但即便存在这类瓶颈，我们也应当预见到：在被开发出来后的几个月之内，这些经历“火花”情景洗礼后的未来 AI 就能在所有领域达到人类顶尖水平。在这一中位数情景下，时间点依然是 2028 或 2029 年。请记住，即便在“火花”情景中，所有这些也都发生在 AI 研发完全自动化后的短短一到两年之内。
<details><summary>Original English</summary>
>> Obviously, they wouldn't have 
access to feedback that arrives after 
many months of serial time, for example,  
how well they did on the next quarterly earnings.
But even given these kinds of bottlenecks,  
we should expect these future post-spark AIs 
to be able to get to top human performance  
in all domains within months of being developed.
That's still 2028 or 2029 in this median scenario. 
And remember, even in this spark scenario, 
all of this happens in just the first year  
or two after AI research is fully automated.
</details>

>> 事情不会就此止步，因为即使软件层面的进展逐渐放缓，AI 还会通过扩充越来越多的算力来继续添柴加火。哪怕没有 AI 的协助，过去五年里全球 AI 算力每年也以大约 3 倍的速度在增长；而经历“火花”之后诞生的 AI，将在协助我们进一步扩展算力方面表现出尖刺状的超人类能力。它们将极其擅长设计新的 AI 芯片并规划新晶圆厂的设计方案，甚至能远程操控机器人来协助建造晶圆厂和数据中心的部分设施。因此在“火花”情景下，AI 能力将继续提升；但由于进展受制于芯片、数据中心和机器人的实体建设，它将需要数年时间才能达成纯软件奇点几个月就能达到的终点——一个视我们如我们视黑猩猩般的超级智能。
<details><summary>Original English</summary>
>> Things don't just stop there because even if the 
software progress peters out, AIs will continue 
stoking the fire by adding more and more compute. 
Even without help from AIs, global 
AI compute has been growing roughly  
3x a year for the last half-decade.
And the AIs that come out of the spark  
will be jaggedly superhuman at helping 
us continue scaling up this compute. 
They'll be extremely good at designing new AI 
chips and laying out the designs of new fabs,  
even teleoperating robots to help 
build parts of fabs and datacenters. 
So in this spark scenario, AI capabilities 
continue to improve, but because their progress is  
driven by building more chips and datacenters and 
robots, it takes years to get to the same endpoint  
that the software-only singularity would have 
achieved in months, which is a superintelligence  
that is to us what we are to chimps.
</details>

### 附录：AI 研究的可验证性与三大核心环节

>> 附录。前面我曾承诺过要解释为什么我认为 AI 研究在很大程度上是可验证的，所以我就从这里谈起。之后，我将梳理针对我关于 RSI 论点的几大最强反驳。在最开头我想特别指出的一点是：因为预训练和后训练都是可验证的（我稍后会阐述原因），所以针对 AI 相比人类最令人恼火也是最重要的缺陷——即样本效率的低下——其改进同样是可验证的。
<details><summary>Original English</summary>
>> Appendix. So earlier, I promised to 
explain why I think AI research is largely 
verifiable, so that's where I'll start. 
After that, I'll go through what I think are the 
strongest objections to my arguments about RSI. 
Now, one thing I wanna call out at the very top 
is that because both pretraining and post-training  
are verifiable, and I'll make my argument for why 
later, so is progress on what is the most galling  
and important deficiency that AIs have against 
humans, namely their lack of sample efficiency. 
</details>

>> 如果你想让神经网络获得某种能力，你必须喂给它比人类学习完全相同内容所需多得多的数据。但各种维度的样本效率都是可衡量的。例如，你可以测量达到给定的预训练损失需要多少数据，或者在强化学习环境中达到特定分数需要多少任务，甚至可以测量在单个会话中仅通过上下文学习达到所需性能水平需要多少反馈和时间。样本效率与在线学习实际上是同一个问题的两面，即如何快速有效地从真实世界数据中学习。几十年来，人们一直认为这是机器学习中最深奥的未解问题，堪称 AI 领域的千禧年大奖难题。而数学已经向我们展示了：只要问题具有可验证性，哪怕极其困难，最终也难逃被攻克的命运。
<details><summary>Original English</summary>
>> If you want a neural network to gain 
some capability, you have to feed it  
far more data than it would take a 
human to learn the exact same thing. 
But every kind of sample efficiency is measurable.
For example, you can measure how much data it  
takes to reach a given pretraining loss or 
how many tasks it takes to reach a given  
score in an RL environment or even how 
much feedback and time within a single  
session it takes to reach a desired level of 
performance just from in-context learning. 
Sample efficiency and online learning 
are really two sides of the same problem,  
which is how to learn from real-world 
data quickly and efficiently. 
For decades, people have recognized this as 
the deepest open problem in machine learning,  
AI's equivalent of a Millennium Prize problem.
And mathematics has already shown us what happens  
to such problems, even when they are very 
difficult, as long as they are verifiable. 
</details>

>> 好，现在我们来看看为什么我认为 AI 进展在很大程度上是可验证的，为什么在样本效率、在线学习或机器学习其他问题上的进展都可以被可验证的代理指标所捕捉。AI 研发大致可划分为三大块：预训练、后训练以及推理效率。正如我将要解释的，每一块都有强大的、易于针对性训练的可验证代理指标。由于它们合在一起构成了算法进展的全部，这意味着 AI 进展总体上是易于针对性训练的——从某种意义上说这并不令人意外，因为凡是能在数据中心内部测试的事物我们都能让模型做得更好，而 AI 训练本身就切切实实地发生在数据中心之内。
<details><summary>Original English</summary>
>> Okay, now let's get to why I think 
that AI progress is largely verifiable,  
why progress on sample efficiency 
or online learning or the other  
problems in ML is captured by verifiable proxies.
There are roughly three broad buckets of AI R&D:  
pretraining, post-training, 
and inference efficiency. 
And as I'll explain, each has strong verifiable 
proxies that are easy to train against. 
And since together, these comprise all 
of algorithmic progress, that means that  
AI progress in general is easy to train against, 
which in some sense shouldn't be that surprising  
because we can make models better at things that 
can be tested inside a datacenter, and AI training  
is literally happening inside a datacenter.
</details>

>> 当我们探讨这些代理指标时，大家应当记住：可验证性的价值体现在两个层面。首先，它允许 AI 公司通过成千上万轮的练习，直接利用强化学习训练模型在 AI 研究的具体环节上变得更强。其次，这些代理指标允许每个智能体在合并自己的代码贡献之前，在经验上核验自己是否在排行榜上超越了某个分数，从而能够更加高效地并行协作。
<details><summary>Original English</summary>
>> As we talk about these proxies, you should 
keep in mind that verifiability 
is valuable for two reasons. 
So first, it allows AI companies to directly RL 
a model to get better at the specific parts of AI  
research through thousands of rounds of practice.
But the second reason verifiability is important  
is that these proxies allow each agent to 
empirically check whether they've beaten  
some score on a leaderboard before they 
merge their contributions, and so they can  
work much more effectively in parallel.
</details>

### 预训练验证与紧缩的迭代循环

>> 明确了这一点后，我们先从预训练谈起。在构建 GPT-7 的过程中，你可以对该模型进行强化学习，让它更擅长寻找预训练算力乘数。例如，你可以设定一个强化学习目标：要求 GPT-7 将训练一个 GPT-2 规模模型达到固定预训练损失所需的算力量降到最低。一旦 GPT-7 构建完成，你就可以部署这个模型或模型集群，去探索如何以尽可能低的困惑度训练一个 GPT-3 规模的模型。这是因为在保留测试集上的损失（这正是预训练研究的基础）极易验证。
<details><summary>Original English</summary>
>> Okay, so with that in mind, let's start 
by talking about pretraining.
So as you're building GPT-7,  
you can RL that model to get better at 
finding pretraining compute multipliers. 
For example, you can make an RL objective 
that GPT-7 has to minimize how much compute  
it uses to train a GPT-2-sized 
model to a fixed pretraining loss. 
And once GPT-7 is built, you can now deploy 
this model or a swarm of these models to  
figure out how to train a GPT-3-sized 
model to the lowest possible perplexity. 
And this is because loss on a held-out test 
set, which is the basis of pretraining research,  
is extremely easy to verify.
</details>

>> 当然，在小规模上有效的做法在大规模上未必奏效，需要有敏锐的品味才能预判哪些小规模的改进在组合进更大的模型时能够真正开花结果。但这种直觉同样是可以被训练出来的。例如你可以构建一个强化学习环境，要求 GPT-7 预测它在 1 亿参数规模下做出的某项算法改进，是否在 100 亿参数规模下依然成立。虽然在这样一个品味基准（taste-bench）环境中进行强化学习要比跑 nanoGPT 速通昂贵，但只要你拥有前沿实验室级别的算力，训练起来并没有那么困难。因此，即便是研究品味中的重要部分也是可验证的。
<details><summary>Original English</summary>
>> Of course, what works at small 
scale doesn't necessarily work at large scale, 
and it requires taste to anticipate exactly which  
small-scale improvements will actually bear fruit 
when they're composed together in a bigger model. 
But this kind of intuition is also trainable.
For example, you can make an RL environment  
where GPT-7 has to predict whether an 
algorithmic improvement that it made at  
the 100 million parameter scale will also 
hold at the 10 billion parameter scale. 
And while this taste-bench environment is more 
expensive to RL on than the nanoGPT speedrun,  
it's still not that difficult to train on 
if you have frontier-lab-scale compute. 
So even important parts of 
research taste are verifiable. 
</details>

>> 哪怕仅仅实现预训练的自动化，也会从根本上极大地加速 AI 进展。这有几个原因：首先，预训练能带来模型智力和能力上非常通用的提升。对此存在一个深刻的原理解释，即压缩与智能之间的内在联系。顺便说一句，如果你想深入了解这一点，我强烈推荐 3Blue1Brown 关于该主题的一期精彩视频，我会在文末附上链接。
<details><summary>Original English</summary>
>> And if you just automated pretraining, you'd 
already radically speed up AI progress. 
And there's a couple of reasons why.
First is that pretraining leads to  
very general improvements in the 
model's intelligence and capabilities. 
And there's a deep explanation for why 
this is true, which has to do with the  
link between compression and intelligence.
And if you wanna learn more about this, by the  
way, I highly recommend this excellent video by 
3Blue1Brown on the topic that I'll link to below. 
</details>

>> 第二个原因是：随着你不断改进预训练，你现在能够训练出越来越小的模型，其性能与先前更大的模型相当，但训练速度更快、成本更低。这不仅加快了预训练本身，也意味着基于这一基座模型进行的实验和强化学习展开会更加高效。既然你的自动化研究员本质上正是这个体积更小的模型的实例，你也就可以支持更大规模的研究员种群了。
<details><summary>Original English</summary>
>> And the second reason is that as 
you make pretraining improvements,  
you can now train a smaller and smaller model 
that is just as good as a previously larger  
model but which trains faster and more cheaply.
And this not only speeds up pretraining, but it  
also means that your experiments and RL rollouts 
atop this base model are now more efficient. 
And since your automated researchers are just 
instantiations of this now smaller model, you can  
now support larger researcher populations too.
</details>

>> 第三个原因在于：因为较小的模型训练速度更快，这实际上极大地紧缩了 RSI 循环本身。在 RSI 期间，实验室可能不会再去进行那些跨多个数据中心园区、耗时三个月的大规模预训练了。相反，庞大的自动化研究员队伍将极其快速地寻找算法创新，以至于当一个耗时巨大的训练运行结束时，它可能已经被一个仅在一周前才开始训练、尺寸小得多的模型淘汰了。这就像如果用当今的技术向半人马座阿尔法星发射一艘飞船，在航行途中它很可能会被一个世纪之后发射的飞船反超一样。此外，由于训练较小模型速度更快，且处于你每天可以运行数千次实验的规模下，你无需去押注小规模结果能否在大模型上维持——因为你已经在你最终将要训练的尺度上完成了测试。
<details><summary>Original English</summary>
>> And the third reason is that because smaller 
models train faster, this actually 
tightens the RSI loop itself. 
During RSI, labs probably won't be doing 
three-month-long pretraining runs that are  
spread out across multiple datacenter campuses.
Instead, the army of automated researchers will  
be finding algorithmic innovations so quickly that 
by the time that a giant run finished, it would  
already have been made obsolete by a much smaller 
model that first began training only a week ago. 
It's similar to how if you launch a spaceship 
to Alpha Centauri with today's technology,  
it would probably be overtaken in transit 
by one that was launched a century from now. 
Furthermore, since you're training smaller models 
faster and on a scale where you can run thousands  
of experiments daily, you won't have to bet that 
small-scale results will hold up in bigger models. 
You've already tested at the 
scale which you'll be training at. 
</details>

>> 那么即便保持在现今的参数规模下，基座模型还能提升多少？我认为可能还有极其巨大的潜力，我们远未触及预训练的极限。例如 AI 实验室 Magic 最近宣布，他们预训练出了一个足以媲美当今领先开源基座模型（如 DeepSeek V4 Pro）的模型，而其所消耗的算力仅为当年训练初代 GPT-3 的一半左右（按今天的价格换算大约相当于 50 万美元）。进一步实现几个数量级的提升似乎完全合情合理。
<details><summary>Original English</summary>
>> Now, how much better could base models 
get even at today's parameter sizes? 
I think there's probably a ton more potential.
We are far from the limits of pretraining. 
For example, the AI lab Magic recently 
announced that they pretrained a model that  
matches the leading open-source base models 
today like DeepSeek V4 Pro for just half of  
the compute that was used to train the original 
GPT-3, which would roughly cost $500,000 today. 
Orders of magnitude further 
improvements seem totally plausible. 
</details>

### 后训练与推理效率的验证代理

>> 现在我们来谈谈后训练。后训练存在三种不同类型的可验证代理指标。第一，自动化研究员可以尝试改进后训练算法，以便在针对新环境集合进行强化学习时消耗更少的算力、数据或时间，这三者都是极其容易测量的。第二，自动化研究员可以致力于提高模型当场即时学习的能力，而你能够轻松测量这方面的进展：例如测量当你将模型放入一个从未受训过的全新环境中时，它能多快弄清状况并获得高分；以及它在玩一款从未玩过的电子游戏时能多快变强。你也可以设计更多贴近现实世界的此类测试用例；如果你想了解这类任务的形式，可以看看字节跳动针对这类任务发布的优秀基准测试 EdgeBench。
<details><summary>Original English</summary>
>> Now let's talk about post-training.
There are three different kinds  
of verifiable proxies for post-training.
First, your automated researchers can try to  
improve your post-training algorithms such that 
if you want to RL on a new set of environments,  
it takes less compute or data or time, 
all three of which are easily measurable. 
Second, your automated researchers can work on 
making models better at learning on the fly,  
and you can easily measure progress on this.
For example, you can measure if you drop your  
model into an environment that it was never 
trained on, how quickly does it learn what's  
going on and figure out how to get a good score?
And how fast does it get better at a video game  
that it's never played before?
And you can have more  
real-world examples of this too.
If you wanna see what these could look like, check  
out this great benchmark that ByteDance released 
called EdgeBench for these kinds of tasks. 
</details>

>> 第三，你可以直接衡量 AI 的研发能力。例如 Anthropic 内部有一个名为 CoBench 的基准，其中包含他们的研究人员和工程师今年解决的大约 500 个实际工程问题。每个基准本身就是一个强化学习环境，像这样的强化学习环境可以让 Anthropic 的模型去练习重演人类过去三到六个月在前沿阵地上取得的进展。
<details><summary>Original English</summary>
>> And third, you can just measure 
AI R&D capability directly. 
Anthropic, for example, has this 
internal benchmark called CoBench,  
which contains around 500 real problems that their 
researchers and engineers have solved this year. 
And every benchmark is also an RL environment, 
and an RL environment like this would allow  
Anthropic to have their models practice 
redoing the last three to six months of  
human progress at the frontier.
</details>

>> AI 研究的第三大领域是推理效率。这涉及对模型及周边软件的设计，旨在从算力中榨取更多价值，而这一点尤其具有极高的可验证性。例如你可以轻松测量 GPU 利用率、每 Token 的 KV 缓存占用大小、前向传播中的总 FLOPs，或者延迟等等。
<details><summary>Original English</summary>
>> The third big area of AI 
research is inference efficiency.
What this involves is designing your model and  
the surrounding software to get more juice out of 
your compute, and this is especially verifiable. 
For example, you can easily measure GPU 
utilization or KV cache size per token or total  
FLOPs in a forward pass or latency and so on.
</details>

### 反驳之一：持续学习能力的缺失

>> 现在我想回应一下针对我关于 RSI 论点的几大最强反驳。我想表明的是，这些瓶颈确实很严重，它们确实压低了以最激进形态实现起飞的概率。这也是为什么我认为我们在 2028 年更有可能迎来一次相当于从 GPT-3.5 到 GPT-6 规模的跃升，而不是明天就开启某种不可思议的暴风骤雨般的一夜奇点。但我认为这些瓶颈不至于造成致命的瘫痪，这个瓶颈的瓶颈口实际上相当开阔。
<details><summary>Original English</summary>
>> Now I wanna deal with the strongest 
objections to my arguments about RSI.
I wanna be clear that these bottlenecks are  
serious, and they do tamp down the probability 
of the most aggressive possible takeoff. 
This is why I think we'll probably 
make something like a GPT-3.5 to  
GPT-6-sized jump in 2028 rather than some crazy 
overnight singularity that starts tomorrow. 
But I think these bottlenecks won't 
be especially crippling, and that  
the neck of the bottle is actually pretty wide.
</details>

>> 让我解释一下原因。第一个质疑点（这也是我直到最近都持有的异议）：我们会被持续学习能力的缺失所卡住。过去一年半的时间里我一直在主张：当今 AI 最缺乏的关键能力，就是从实际工作经验中学习的能力。每一次新的会话都是它们上班的第一天；而在每次会话中，它们只能保留几个小时的信息，因此根本无法积累那些需要在数周或数月时间里逐渐形成的高阶反馈和专有诀窍。
<details><summary>Original English</summary>
>> Let me explain why. Okay, so the first objection, 
and this is an objection that I had until 
recently, is that we'll be bottlenecked  
by continual learning or the lack thereof.
I've spent the past year and a half arguing  
that the main thing missing from today's AIs is 
this ability to learn from on-the-job experience. 
Every new session is their first day on the 
job, and in each session, they can only retain a  
couple hours' worth of information, so they don't 
accumulate the kind of feedback and know-how that  
arrives over the course of weeks or months.
</details>

>> 去年十二月，这也是我怀疑我们能否在短期内实现 AI 研究自动化的主要原因。正如我当时所写：在不具备小孩子所拥有的基础学习能力的情况下，这个自动化研究员不知怎的就要去找出实现 AGI 的算法——而这是人类长达半个世纪以来撞得头破血流的问题——这在我看来极其令人难以置信。但在这个问题上，我一定程度上改变了主意。以下是我认为这些模型当前缺乏持续学习能力并不会阻碍在 2028 年前实现顶尖 AI 研究员全面自动化的原因。
<details><summary>Original English</summary>
>> Last December, this was my main reason for 
doubting that we'd automate 
AI research anytime soon. 
As I wrote then, somehow this automated researcher 
is gonna figure out the algorithm for AGI,  
which is a problem that humans have been 
banging their head against for the better  
half of a century, while not having the basic 
learning capabilities that children have. 
I find this super implausible.
But I've somewhat changed my mind on this. 
Here's why I don't think that the current lack of 
continual learning in these models will stop full  
automation of the best AI researchers by 2028.
</details>

>> 首先，AI 公司到时候可能仅凭与现有架构非常相似的结构就解决了持续学习问题。此前我曾认为我们受制于某种不可思议的突破性架构，需要能够让模型在每次会话结束时自我更新权重；但现在我认为，扩大上下文学习（in-context learning）的规模就已经足够了。这样一来，你就能拥有在实际效果上长达数月的会话，从而允许单个实例在工作中切实有效地学习。人们已经发表了大量非常有前景的思路，能让实验室实现极其漫长的有效上下文窗口。
<details><summary>Original English</summary>
>> First, AI companies might just solve continual 
learning by then with architectures that 
are much like the ones they already have. 
Previously, I thought that we were 
bottlenecked by some crazy breakthroughs  
that would allow models to update their 
own weights at the end of every session. 
But now I think that scaling up 
in-context learning is enough,  
and so you'll have sessions that are effectively 
many months long, and this will allow a single  
instance to learn effectively on the job.
And people have published many, many  
promising ideas that would let the labs achieve 
dramatically longer effective context windows. 
</details>

>> 第二个原因在于：你未必需要一个具备持续学习能力的系统去攻克持续学习。正如我前面所解释的，在线学习本身就是一个拥有清晰、可验证代理指标的机器学习研究课题。如果在两年前问我 Navier-Stokes 方程和持续学习哪个更难解决，答案是 Navier-Stokes 对我而言绝非显而易见。现在看来，鉴于各大实验室尚未攻克持续学习，它确实更难一些。但我们真的有十足把握断定它就难到那种程度，以至于比当前解决千禧年难题的模型再聪明一两年的非在线学习模型即使像现有模型一样如同失忆症患者，也依然无法攻克它吗？
<details><summary>Original English</summary>
>> And the second reason is that you might not need 
a continual learner to solve continual learning. 
As I explained earlier, online learning is an ML 
research problem with clean, verifiable proxies. 
If you'd asked me two years ago, which would 
be harder to solve, Navier-Stokes or continual  
learning, it wouldn't have been obvious 
to me that the answer was Navier-Stokes. 
Now, of course, it turns out that continual 
learning did turn out to be harder, given the  
fact that the labs haven't cracked it yet.
But are we so confident that it's that  
much harder that the non-online learning 
models a year or two smarter than the ones  
that are currently solving Millennium Prize 
problems won't be able to crack it, even if  
they're amnesiacs like the current models are?
</details>

>> 这些模型目前在没有长期记忆、依然表现得像笨拙博学实习生的情况下，就已经在接连解决千禧年难题了。这就像看着一个人在跑道上一边翻着侧手翻，一边还能跟尤塞恩·博尔特并驾齐驱。如果真的允许他们放开奔跑，我相信他们肯定会跑得更快；但谁能说他们翻着侧手翻就绝对赢不下这场比赛呢？话虽如此，我认为我们未来几年无法解决持续学习、且模型无法通过其他优势来弥补这一缺陷的概率仍然不容忽视。这也是为什么我给出了 25% 的概率：在 2032 年之后，我们才能实现达到 Ilya 级别的顶尖人类研究员的自动化。
<details><summary>Original English</summary>
>> These models are out here solving Millennium 
Prize problems while still being these derpy 
savant interns that have no long-term memory. 
It's like watching somebody do cartwheels down 
the track and still keep pace with Usain Bolt. 
If they were actually allowed to run, 
I'm sure they could go even faster. 
But who's to say that they can't win 
this race while still cartwheeling? 
Now, all this being said, I think there is a 
serious chance that we don't solve continual  
learning within the next few years and that 
models are not able to compensate for this  
missing capability through their other advantages.
That's why I put a 25% probability that we won't  
automate Ilya-level top human 
researchers until after 2032. 
</details>

### 反驳之二：范式转变与研究品味

>> 人们提出的另一个重要质疑是：我们受制于寻找合适的可验证代理指标。他们会辩称：我上面列出的所有可验证代理指标都是以现有范式为前提的；然而在最初去搞清楚究竟该验证什么目标、决定让 GPT-7 去爬哪座山，这本身就是 AI 研究至关重要的一部分。这也就是人们所说的“研究品味”，你又如何针对这一点进行训练呢？在 2018 年之前，几乎没人会说将下一个 Token 的预测损失降到最低将是实现 AI 进展最可行的路径；因此当时没有人会费心去构建 nanoGPT 风格的速通环境，要求智能体集群以最短的时间达成某种预训练损失。难道从当前走到超级智能，我们不需要跨越多个全新范式吗？难道每个新范式不都需要某些我们在事后才能知道的关联代理指标吗？自动化研究员在 RSI 期间又如何能找到这些指标？
<details><summary>Original English</summary>
>> One important objection people 
have is that we'll be bottlenecked  
by finding the right verifiable proxies.
All the verifiable proxies that I've listed above  
assume the current paradigm, they would argue.
But figuring out what objective to verify in  
the first place, choosing which hill to have GPT-7 
climb, is itself an important part of AI research. 
This is what one might call research taste, 
and how are you gonna train for that? 
Before 2018, almost nobody was saying that 
minimizing loss on next-token prediction is gonna  
be the most tractable path to AI progress.
So nobody would have bothered to build  
nanoGPT-style speedrun environments where the 
agent swarm has to minimize how much time it  
takes to get to a certain pretraining loss.
Wouldn't there be multiple new paradigms  
that we have to cross to get 
from here to superintelligence? 
And won't each new paradigm require some 
associated proxy that we don't know ex ante? 
How will the automated 
researchers find these during RSI? 
</details>

>> 对这一质疑我有两点回应：首先，Transformer 在当时已有的翻译基准测试上是清晰可见的，事实上它就是为了刷爆现有的翻译基准而发明的。推理模型以及先前存在的代码与数学基准测试之间也呈现出完全相同的规律。在范式飞跃之前建立的代理指标，似乎完全能够捕捉到性能上的巨大阶跃变化。这是因为 AI 的学习算法具有很强的通用性。
<details><summary>Original English</summary>
>> I have two responses to this objection.
First, the transformer was visible on,  
in fact, invented to beat the 
existing translation benchmarks. 
A similar story is true for reasoning models 
and the pre-existing coding and math benchmarks. 
Proxies made before a paradigm leap seem 
perfectly capable of capturing large step  
changes in performance.
This is because AI  
learning algorithms are quite general.
</details>

>> 其次，提出与范式无关的外循环代理指标并不困难。例如你的新模型解决了多少个千禧年难题？如果你用 1905 年之前的数据训练你的模型，它需要多久能发现广义相对论？它掌握完全未见过的电子游戏速度有多快，等等。总体而言，我认为针对 RSI 影响的其他反驳要有力得多；如果这一条最终成了 RSI 未成大器的原因，我会感到非常意外。
<details><summary>Original English</summary>
>> And second, it's not that difficult to 
come up with paradigm-agnostic outer loop proxies.
For example, how many Millennium Prize problems  
does your new model solve?
And if you train your model on  
data before 1905, how long does it take 
before it discovers general relativity? 
How fast does it master totally 
unseen video games, and so on? 
All in all, I think the other objections 
to the impact of RSI are much stronger,  
and I'd be very surprised if this ended up 
being the reason that RSI was not a big deal. 
</details>

### 反驳之三：数据瓶颈与合成环境

>> 人们指出的另一个重大瓶颈是数据。数据难道不是 AI 进展的核心投入要素之一吗？如果数据不能以同样的速度扩张，RSI 又如何能够发生？我的回答是：数据在 RSI 期间将继续增长，但届时将是由 AI 来负责编译它们。无论为预训练还是后训练产出更优质的训练数据，这本身就是一个机器学习研究课题，而 AI 自己正在越来越擅长做这件事。
<details><summary>Original English</summary>
>> The other big bottleneck that 
people point out is data. 
Isn't data one of the main 
inputs into AI progress? 
How will RSI happen without that 
scaling up at the same rate? 
My answer is that data will 
continue growing during RSI,  
but the AIs will be the ones compiling it.
Producing better training data for both  
pretraining and post-training is itself an ML 
research problem, and AIs are getting increasingly  
better at doing it themselves.
</details>

>> 诚然，数据对于 AI 的进展是极其关键的投入。我和普林斯顿大学的学生 Jerry Han 实际上就此做过专门的研究：我们发现在过去的六年里，针对预训练而言，源自数据改进的算法进展是源自模型改进的 3 倍以上。然而我认为人们没有意识到，预训练中的这些数据改进工作与常规的 AI 研发工作高度契合：本质上就是去摸索哪些过滤现有数据或生成新合成数据的技术，在经验上能让模型在保留语料库上获得更低的损失。
<details><summary>Original English</summary>
>> Now, it is true that data is an 
extremely important input into AI progress.
Together with Jerry Han, who's a student at  
Princeton, I actually did some research into this.
We found that for pretraining, over the last six  
years, more than three times the 
algorithmic progress has come from  
data improvements than model improvements.
However, I don't think that people realize  
that these data improvements in pretraining are 
very much in line with normal AI research work. 
It's basically figuring out which techniques 
for filtering existing data or generating  
new synthetic data empirically lead 
to lower loss on a held-out corpus. 
</details>

>> 类似的情况在强化学习中似乎也越来越明显。DeepSeek 刚发表了一篇论文，阐述了他们是如何对新模型进行后训练的。他们表示，对基础强化学习算法的修改远没有那么重要，并且“合成数据与环境在规模、多样性和可验证性上的系统性提升，几乎贡献了观察到的全部收益”。而且，这类环境的构建方式本身也变得越来越自动化。他们写道：“我们对用于数据合成和环境构建的大规模自动化流水线进行了投资。利用难度和正确性作为奖励信号，我们迭代式地训练模型以构建出更优秀的任务。”
<details><summary>Original English</summary>
>> A similar thing seems to be 
increasingly true for RL. 
DeepSeek just published a paper where they talk 
about how they post-trained their new model. 
They say that changes to the basic RL algorithm 
have not mattered nearly as much, and that,  
quote, "Systematic improvements in the scale, 
diversity, and verifiability of synthesized data  
and environments account for essentially 
all of the observed gains," end quote. 
And the way in which these environments are 
made is itself getting more and more automated. 
They write, quote, "We invest in 
large-scale automated pipelines for  
data synthesis and environment construction.
Using difficulty and correctness as reward  
signals, we iteratively train the model 
to construct better tasks," end quote. 
</details>

### 反驳之四：实验算力瓶颈与小模型科学

>> 现在我想谈谈“AI 进展将受制于实验算力”这一观点。前面我把当前数学领域的加速与我们在 AI 研究中应当预期发生的事情做了一个长篇类比。但 AI 研究与数学之间存在一个巨大的差异：在数学中，你可以仅凭纸和笔推导构思出新发现；而在 AI 研究中，你必须运行真实的实验来验证你的想法，而这需要算力和时间。随着自动化研究员数量的增加，每个人分到的总实验算力蛋糕份额会变得越来越小。
<details><summary>Original English</summary>
>> Now I wanna talk about the idea that AI 
progress will be bottlenecked by experiments. 
So earlier, I made this extended analogy between 
the current acceleration in mathematics and what  
we should expect to happen in AI research.
But there is one big difference between  
AI research and mathematics.
In math, you can simply reason  
your way with pen and paper to new 
discoveries, whereas in AI research,  
you need to run actual experiments to validate 
your ideas, and these take compute and time. 
And as the number of automated researchers 
grows, each gets access to a smaller and  
smaller slice of the total experiment compute pie.
</details>

>> 对此我的回答是：基本上，每个智能体仍然会获得大量的算力支持。前沿实验室每年将算力翻两番以上，如果这一趋势持续下去，到 2027 年底，OpenAI 几乎可以给 10,000 个智能体（相当于解决千禧年难题所动用的智能体规模）每个智能体每天分配足够的算力来运行一次 GPT-3 规模的训练。别忘了，2017 年初代 Transformer 论文中训练的最终模型，仅在 8 块 P100 上跑了三天——这在今天花大约 50 美元就能租到，仅相当于 GPT-3 训练算力的万分之一左右。如果顶尖人类 AI 研究员（如 Noam Shazeer 和 Ilya Sutskever）每天都有足够的实验算力训练一个 GPT-3 规模的模型，他们的进展可能确实会比现在慢，但如果他们直接两手一摊、抱怨集群太小而彻底无法取得任何有意义的进展，那对我来说将是极其不可思议的。
<details><summary>Original English</summary>
>> My answer to this is that each agent will still 
get access to a ton of compute, basically.
Frontier labs have been more than quadrupling  
their compute every single year, and if this 
trend continues, then by the end of 2027,  
OpenAI could almost give 10,000 agents, so 
the amount that were involved in solving the  
Millennium Prize problem, each enough compute to 
run a GPT-3-sized training run every single day. 
Keep in mind that the final model trained in the 
original transformer paper in 2017 took three  
days on eight P100s, which would cost about 50 
bucks if you went to rent it today, or about one  
ten-thousandth of the training compute of GPT-3.
If the top human AI researchers, like Noam Shazeer  
and Ilya Sutskever, had enough experiment compute 
to train a GPT-3-sized model every single day,  
they might make slower progress than they 
currently do, but it would be extremely  
surprising to me if they failed to make meaningful 
progress altogether and just sat down and started  
complaining about how small their cluster was.
</details>

>> 那么，如果一家 AI 实验室拥有 10,000 名优秀的研究员，每人都拥有如此多的算力，且每人的思考速度都是原来的 10 倍，你认为这家实验室的生产力会有多高？难道你不想给这家新型实验室开支票吗？如今各大实验室的研究和实验模式反映出：相对于算力而言，研究员的时间极其稀缺。顶尖 AI 研究员个人的年薪高达数亿美元。因此，实验室今天使用算力的方式，根本无法说明如果关键瓶颈是算力而非研究员时间的话，他们能够将算力运用得多有效率。
<details><summary>Original English</summary>
>> Now, how productive do you think an AI lab 
would be if it had 10,000 great 
researchers, each with this much  
compute and each thinking 10 times as fast?
You wouldn't wanna write a check to this neolab? 
The nature of research and experimentation at 
the labs today reflects that researcher time  
is extremely scarce relative to compute.
Top AI researchers individually get paid  
hundreds of millions of dollars a year.
So the way labs use compute today tells  
us very little about how efficiently 
they could use it if compute rather  
than researcher time was the key bottleneck.
</details>

>> 在使用实验算力方面，RSI 智能体集群能比当今研究人员高效得多的主要方式有两点：首先，它们可以立刻以人力置换算力。为了节省宝贵的研究人员时间，如今的实验对算力往往非常浪费，而且理当如此。因此，今天的人类研究员可能不会去耗费心力建立并仔细监控大量小规模预训练实验，而是直接并行启动几次大规模的多智能体强化学习运行。但如果你受到了实验算力的制约，你完全可以多做前者。当这些自动化研究人员在进行强化学习运行时，它们可以阅读每一份展开记录，一旦发现某个任务出现故障，就能立即暂停并重建整个环境；它们还可以对模型进行海量的小规模消融实验，只为让它们好上那么一点点。当一个智能体团队决定把算力集中起来做一次更大规模的运行时，它们可以花上主观上的数十年时间去设计最具信息量的合并实验；一旦实验运行完毕，它们还可以花上主观上的数十年时间进行全方位的深入分析，然后再去设计新的实验。
<details><summary>Original English</summary>
>> There are two main ways in which the RSI agent 
swarm will use experiment compute much more 
efficiently than researchers today use it. 
First, immediately they can 
trade labor for compute. 
To save valuable researcher time, 
experiments today are, and should be,  
very wasteful with compute.
So instead of painstakingly  
setting up and carefully monitoring tons 
of small-scale pretraining experiments,  
a human researcher today might instead kick off 
a couple of huge multi-agent RL runs in parallel. 
But if you're bottlenecked by experiment 
compute, you can just do more of the former. 
And when those automated researchers are doing 
an RL run, they could read every single rollout  
transcript and immediately pause and rebuild 
a whole environment if some task is broken. 
They could be doing crazy amounts 
of small-scale ablations of their  
models to make them oh-so-slightly better.
And when a team of agents decides to combine their  
compute together in order to do a much bigger run, 
they could spend many subjective decades designing  
the most informative pooled experiment.
And once it's done running, they could  
spend further subjective decades comprehensively 
analyzing it before designing a new experiment. 
</details>

>> 庞大的智能体集群在单个副本分配算力减少的情况下依然能保持高效产出的另一大途径在于：这些自动化研究人员可以开创一套更好的“从小规模实验中学习”的科学体系。缩放定律（Scaling laws）本身就是极佳的例证：GPT-4 的论文中指出，他们能够利用少花费 10,000 倍算力训练出的模型来预测最终模型的最终损失。更聪明、更快速的自动化公司所能做的事情之一，就是尝试发现更多类似于 muP 的缩放现象——后者能让研究人员从缩小 100 倍的模型中预先推知更大规模运行的最佳超参数。像这样的相似发现还有多少？我记得曾与一位 AI 研究员交谈，他认为从极小规模的神经网络中学习可以带来极其巨大的信息量。他是这么说的：“天上的诸神，所遵循的想必是和地上的蝼蚁相同的法则。”
<details><summary>Original English</summary>
>> The other big way that this huge agent swarm 
could remain productive, despite the fact that  
each individual copy will have access to less 
compute, is that these automated researchers  
could come up with a better science for 
learning from small-scale experiments. 
Scaling laws themselves 
are a good example of this. 
The GPT-4 paper says that they were able 
to predict the model's final loss using  
models trained with 10,000x less compute.
One of the things that the smarter and faster  
automated company could be doing is trying 
to discover more scaling phenomena like muP,  
which lets researchers anticipate the 
optimal hyperparameters for a larger run  
from 100x smaller models.
How many more similar  
discoveries like this are there?
I remember chatting to an AI researcher  
who thought that learning from extremely small 
neural networks could be incredibly informative. 
He put it this way, "The gods above must work 
from the same principles as the ants below." 
</details>

>> 在撰写这篇长文的重要部分时，有几位朋友与我一起搭档，我想向他们表示感谢：Max Farrens、Gabe Fried 以及 Thomas Larsen。我们下一篇关于超级智能的长文再见；在此期间，如果你想在视频文章发布时收到通知，请在 YouTube 上订阅。好的，我们下次见。
<details><summary>Original English</summary>
>> I wanna thank my friends who paired with me 
through significant parts of writing this essay,  
Max Farrens, Gabe Fried, and Thomas Larsen.
I'll see you on the next essay about  
superintelligence, but in the meantime, if you 
wanna get notified when that video essay drops,  
please subscribe on YouTube.
All right, I'll see you next time.
</details>