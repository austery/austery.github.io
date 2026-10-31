---
author: All-In Podcast
date: '2026-05-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=HGbA6ze0_3M
speaker: All-In Podcast
tags:
  - recursive-self-improvement
  - ai-infrastructure
  - space-economy
  - macro-economics
  - geopolitics
title: 'All-In 274: SpaceX 估值 2 万亿，AI 舆论危机与英伟达的‘印钞机’时代'
summary: 本期讨论了 Andre Karpathy 加入 Anthropic 推动 AI 递归自我改进；分析了 AI 行业面临的公关危机，特别是科技巨头裁员与‘录屏训练’引发的恐慌。重点拆解了 SpaceX 以 1.75 万亿美元估值 IPO 的财务逻辑，探讨了‘埃隆云服务’（EWS）和太空计算的未来。此外，还涵盖了英伟达惊人的财报表现及宏观经济中的通胀风险。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - SpaceX
  - Anthropic
  - Nvidia
  - OpenAI
  - Meta
  - Cloudflare
  - Google
products_models:
  - Claude
  - Starlink
  - Colossus
  - Grok
  - H100
media_books: []
status: evergreen
---
### Andre Karpathy 加入 Anthropic 与递归自我改进

**Jason**: 大家好，欢迎回到世界第一的播客。这是《All-In》第 274 期。今天 Sachs 不在，但我们很幸运请到了 **Gavin Baker** 参加。本周科技界大事不断：**SpaceX** 和 **OpenAI** 的 IPO、**Andre Karpathy** 加入 **Anthropic**、**英伟达 (Nvidia)** 业绩爆表。我们先从 Karpathy 说起。他才 39 岁，就已经是科技界的传奇。他曾是 OpenAI 的创始成员，主导过特斯拉的自动驾驶团队。他最近搞的开源训练工具 Auto-Research，通过 5 分钟的实验让模型自我改进，在 GitHub 上拿了 8.2 万颗星。现在他要在 Anthropic 负责一个新的预训练团队，核心重点是**递归自我改进 (Recursive Self-Improvement)**。简单说，就是让 Claude 自己改进自己。在 2026 年，这是否具有超级重要性？

<details>
<summary>Original English</summary>

**Jason**: All right, everybody. Welcome back to the number one podcast in the world. It's the All-In podcast, episode 274. Sachs is out today, but we're very lucky to have Gavin Baker from Atreides Management joining us. It's been a huge week in tech. We can start with the SpaceX and OpenAI IPOs. We've got Andre Karpathy joining Anthropic. Nvidia crushing it. Karpathy is only 39 years old. He's already a legend in the tech industry. He recently built auto-research, an open-source training tool that helps AI models improve themselves by running five-minute experiments. That got over 82,000 stars on GitHub. He's going to be in charge of a new pre-training team at Anthropic. The focus obviously being recursive self-improvement. In other words, they're going to have Claude improve itself. Is this super important in 2026?

</details>

**Chamath**: 有趣的是，如果你回看谷歌的文化，他们会将顶尖技术人才称为“谷歌院士 (Google Fellows)”，比如 Jeff Dean。这些人总是处在浪潮的最前沿。Andre 也是如此，他经历了 AI 的一波又一波浪潮。他在特斯拉负责 FSD 时，可能是第一个将 Richard Sutton 的《苦涩的教训 (Bitter Lesson)》商业化的人，即依靠蛮力计算。他曾告诉我，他花了四分之一的时间在**手动标注数据**——你能想象在 2016 年手标特斯拉的视频数据吗？他是个极其聪明且充满好奇心的人。我认为“递归自我学习”会让模型进入超速自动驾驶状态。如果这能实现，我们可能会看到模型质量每年呈数量级提升，这就像一种新形式的**摩尔定律**，模型质量会呈抛物线式增长。

<details>
<summary>Original English</summary>

**Chamath**: You know what's interesting if you go back to like Google, the culture of Google which they got right was the singular technical talents there, they were called Google Fellows. What's interesting about Andre is he's been at the wave upon wave of AI. He was probably the first person that really commercialized the Richard Sutton bitter lesson essay when he was leading FSD at Tesla, which was really about the brute force computation. I remember him telling me he spent a quarter of his time labeling data—could you imagine like 2016-17 like hand-labeling video data from Teslas? This idea of recursive self-learning puts these models on a combination of overdrive and autopilot. The model quality just goes absolutely parabolically just like this straight up.

</details>

**Gavin**: Anthropic 的成功是不可否认的。《华尔街日报》报道他们最近一个季度 **EBIT (息税前利润) 已经转正**，这对整个 AI 叙事至关重要。如果 OpenAI 和 Anthropic 的 ARR (年度经常性收入) 达到 1000 亿美元，且推理毛利率在 80% 左右，那么回报是实实在在的。算上 Gemini、Cursor、xAI 和开源模型，今年底全行业 ARR 达到 2000 亿到 4000 亿并不难。我认为 Karpathy 研究的递归自我改进和**持续学习 (Continual Learning)** 是 AI 的最后两个前沿。模型在训练过程中通过前向传递对自身训练产生输入，或者模型学习经验像人类一样，这会真实地把未来拉近。

<details>
<summary>Original English</summary>

**Gavin**: The success is extraordinary. It's undeniable. I think the fact that they were EBIT positive per the Wall Street Journal in the most recent quarter is a really important fact for kind of the whole AI narrative because now there's ROI. If OpenAI and Anthropic are at call it a hundred billion dollars of ARR now with 80%ish gross margins on inference, the returns are there. It's not hard to see 200, 300, 400 billion of ARR at the end of this year across all language models. I do think what Karpathy is working on recursive self-improvement is really important. Maybe the two final frontiers for AI are that and continual learning, where the model learns from experiences the way humans do.

</details>

### AI 的公关危机：裁员、监控与“测量员”

**Jason**: 现在 Anthropic 领先一步，可能领先开源模型 6 到 12 个月。但在某个时点，AI 改进模型的能力会超过人类。Friedberg，你对目前的 **AI 公关危机**怎么看？我们看到三场毕业典礼上的演讲被嘘，包括 Eric Schmidt。年轻人为什么如此强烈地抵制 AI？

<details>
<summary>Original English</summary>

**Jason**: Anthropic has a decent lead on everybody else. But at what point do we think this super recursiveness occurs? Friedberg, what's your take here on the AI PR crisis? We had three different commencement speeches that were booed. Eric Schmidt being one of them. Why are young people booing AI vociferously?

</details>

**Friedberg**: 这是一个很长的问题。根本观点是，技术为少数人创造了**杠杆**，从而导致权力失衡，而 AI 是这种失衡的终极代表。少数控制并获益于 AI 的人将获得远超大众的回报。人们不明白 AI 如何运作，只看到少数人赚了几万亿。其次，存在外部力量在资助美国的反技术情绪。就像冷战时期的 KGB 一样，外国势力有动机削弱竞争对手的技术进步。最后，这是一种心理冲击。哥白尼革命挑战了人类中心论，AI 也在挑战人类的自我（Ego），它带有一种**反人文主义**的色彩，这让很多人深感不安。

<details>
<summary>Original English</summary>

**Friedberg**: I think that there's an underlying view that technology creates leverage for a small group of people which creates power imbalances, and nothing represents that more than AI. The economic benefit that's accruing to the few today becomes the narrative. Secondly, I think that there's a deep amount of external energy that's fueling this anti-technology sentiment in the United States. I think this goes all the way back to KGB design during the Cold War. Thirdly, AI shifts and messes with the ego of the human. It's almost anti-humanist, and I think that's a deep psychological current in a lot of people's disdain for this technology.

</details>

**Jason**: 现在的裁员不仅仅是因为“机构臃肿”了。Cloudflare 的 CEO **Matthew Prince** 两周前裁掉了 20% 的员工，他说他要裁掉的是“测量员 (Measurers)”——即管理人员和测量数据的人，因为 AI 可以做这些。与此同时，**扎克伯格 (Zuckerberg)** 又进行了一轮裁员，同时他要求在所有员工电脑上安装**记录软件**，研究员工如何工作以训练模型。这让人们感到恐慌：你不仅要丢掉工作，你还在丢掉工作前被要求训练你的替代者。

<details>
<summary>Original English</summary>

**Jason**: I think we have to recognize that the layoffs are not just the bloating issue anymore. Matthew Prince, CEO of Cloudflare, laid off more than 20% of his workforce. He says he's getting rid of "measurers"—people who manage people and measure data—because they are unnecessary because of AI. At the same time, Zuckerberg did another round of layoffs and he told everybody we're putting recording software on every single person in the company's computers to study and train our model. This is scaring the be-Jesus out of people.

</details>

**Chamath**: Matthew Prince 的那封备忘录简直是公关灾难的典范。你把活生生的人简化为一个叫“测量员”的标签，然后说你要裁掉所有“测量员”。这给这些人贴上了“红字”，让他们以后找工作都难。这些技术 CEO 也许在某一方面很天才，但在公关上简直烂透了。我想对他们说：闭上臭嘴，回到键盘后面，做你的工作，别再写这些烂备忘录了。你们在这方面真的烂透了。

<details>
<summary>Original English</summary>

**Chamath**: I thought the Matthew Prince note was horrible. This was like from the PR school of retards. You reduce humans to a label called the "measurer" and then you're like, I'm going to lay off all the measurers. It puts a scarlet letter on their back. I would say shut the f**k up, get behind the keyboard, just do your job. Don't write these missives. You're all terrible at it.

</details>

### SpaceX IPO：2 万亿美元估值的逻辑

**Jason**: 话题二，SpaceX 周三提交了 **S1 文件**。他们计划融资 750 亿美元，估值达到 **1.75 万亿美元**。这将是历史上规模最大的 IPO。核心业务中，**Starlink** 是印钞机，去年营收 114 亿美元，增长 50%。AI 业务营收 32 亿美元，但运营亏损 64 亿。最惊人的是 **EWS (Elon Web Services)**，Anthropic 每月支付 SpaceX 12.5 亿美元来租用 **Colossus (巨像)** 超算集群，这是一份 3 年 450 亿美元的合同。Gavin，你怎么看这份 S1 和“埃隆云服务”？

<details>
<summary>Original English</summary>

**Jason**: Topic two, SpaceX just filed their S1 on Wednesday. They are aiming to raise 75 billion at a 1.75 trillion valuation. This will be the largest IPO ever. Starlink is the money printer right now, 11.4 billion in revenue. AI did 3.2 billion in revenue but had 6.4 billion in operating losses. But here's the big one: EWS, Elon Web Services. Anthropic is paying SpaceX 1.25 billion a month to rent out Colossus 1 and parts of Colossus 2. It's a $45 billion deal over three years.

</details>

**Gavin**: “埃隆云服务”这个名字让我发笑，但这意味其 AI 业务将翻四倍。SpaceX 建造数据中心的速度比任何人都快——第一个花了 122 天，第二个 91 天，第三个才 66 天。只要有算力分配，他们就能迅速把电子转化为 Token。此外，**Cursor** 的 Composer 2.5 模型本周发布，它在 Colossus 2 上进行了几周的强化学习，表现已经超出了**帕累托前沿 (Pareto Frontier)**。这证明了算力集群的强大。我预测 2028 年到 2030 年间，**轨道计算 (Orbital Compute)** 也就是太空数据中心将成为现实。

<details>
<summary>Original English</summary>

**Gavin**: Elon Web Services makes me laugh, but it means the AI business is going to quadruple. They build data centers dramatically faster than anyone else—the first one was 122 days, the second 91 days, the third 66 days. Cursor's Composer 2.5 model came out this week and it is Pareto dominant after doing reinforcement learning on Colossus 2. As far as when will orbital compute be a reality, I would say second half of '28 to first half of 2030.

</details>

**Chamath**: 如果你问我如何为 2 万亿估值的 SpaceX 承销？我会看它的三层逻辑：1. 互联网基础设施（Starlink），这是自互联网诞生以来最重要的项目；2. 交付基础设施（火箭发射）；3. AI 业务，不仅是应用层，更是底层的算力能力。SpaceX 是唯一能交付**吉瓦级 (Gigawatt)** 数据中心的公司。马斯克正在创造一种资本护城河，进而加速技术护城河。当特斯拉最终并入这个实体时，它将拥有海量的物理数据语料库。过几年看，这个价格也许会显得非常便宜。

<details>
<summary>Original English</summary>

**Chamath**: How do I underwrite SpaceX at 2 trillion? I'm buying the most important internet infrastructure project (Starlink). I'm buying a delivery infrastructure. And I'm buying an AI business. They are the closest to delivering a gigawatt data center. What he creates is a capital moat that then accelerates a technology moat. That thing will look very cheap, I think, in a few years.

</details>

### 英伟达的统治与宏观经济风险

**Jason**: 英伟达再次引爆财报，第一季度营收 816 亿美元，增长 85%，利润 580 亿，毛利率 75%。它是目前全球市值最高的公司（5.3 万亿）。他们还宣布了 800 亿的股票回购，并将季度股息提高了 25 倍。

<details>
<summary>Original English</summary>

**Jason**: Nvidia blew out its earnings again. 81.6 billion in revenue, up 85% year-over-year. 58 billion of net income with 75% gross margins. They've announced another 80 billion in additional buybacks and raised the quarterly dividend 25x.

</details>

**Gavin**: 我认为目前 AI 市场在横向估值上是不合理的。如果你看电力、冷却、光学设备公司的倍数，它们和英伟达的逻辑是冲突的。英伟达本季报最惊人的一点是，他们的 **CPU 业务**今年将达到 200 亿美元。一夜之间，他们成了全球最大的 CPU 制造商之一。此外，英伟达通过与每一家实验室的“协同设计”，正在内部演化出**领域特定架构 (DSA)**。这简直疯了。

<details>
<summary>Original English</summary>

**Gavin**: The AI market is cross-sectionally inefficient right now. I think there was one other really important thing in the Nvidia quarter: they said their CPU business was going to be $20 billion this year. It means overnight they're one of the world's largest CPU manufacturers. The DSA (Domain Specific Architecture) market evolution is actually happening inside of Nvidia.

</details>

**Friedberg**: 宏观方面，我并不乐观。全球债务占 GDP 的比例已经达到 310%。通胀正在卷土重来，May CPI 预计在 4.2% 以上，甚至有人预测会达到 6%。这意味着美联储不仅不会降息，反而可能加息。日本 30 年期国债收益率创历史新高，英国和德国的收益率也在飙升。这就好比水正在从桶里漏出来。我们正处在过山车顶端开始俯冲的时刻，引力是不可避免的。

<details>
<summary>Original English</summary>

**Friedberg**: Global debt to GDP is 310%. The spending problem ultimately creates a cascading effect. As it starts to break, you have massive inflation. 30-year Treasury is at 5.2%. This Japanese yield might be a catalyst for a credit crisis. This is water leaking out of the bucket.

</details>

**Chamath**: 我同意这是危险信号。我的建议是不要投机。我老了，不想再经历那种情绪波动。我只持有极少数（5 个以内）我真正相信的公司。

<details>
<summary>Original English</summary>

**Chamath**: There are signals that are flashing. Generally everything else, I think you should not speculate. I have a few companies that I really believe in. Five or less.

</details>

### 中美关系：地缘政治的博弈

**Jason**: 本周多位科技 CEO 随同总统会见了中方领导人。虽然有一些飞机和黄豆的订单，但并没有达成预期的重大突破。

<details>
<summary>Original English</summary>

**Jason**: We had a 48 hour jaunt by a bunch of tech CEOs and the president to hang out with Xi. Other than a little business development, was it just performative?

</details>

**Friedberg**: 我认为并没有达成那种能缓解紧张局势的“大交易”。普京紧接着访问中国也说明了故事还在继续。地缘政治的博弈依然处于剧烈波动中。

<details>
<summary>Original English</summary>

**Friedberg**: The grand deal that de-escalates tension probably didn't manifest as some had hoped it would. And it's no surprise that Putin is with Xi today. The story continues.

</details>

**Gavin**: 我支持向中国出售性能较低的英伟达 GPU。这降低了他们开发自己生态系统的动力。这是一种稳定世界的手段，也是让美国在 AI 领域保持领先并保留控制权的概率最高的路径。

<details>
<summary>Original English</summary>

**Gavin**: I think selling deprecated Nvidia GPUs to China lowers the odds of them developing their own alternative ecosystem. I think there's sound arguments that this is stabilizing for the world.

</details>

**Jason**: 好了，本期结束。Sachs 快回来吧。谢谢 Gavin Baker，谢谢大家。让赢家继续跑！

<details>
<summary>Original English</summary>

**Jason**: All right. Let your winners ride. See you next time.

</details>