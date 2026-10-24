---
author: New York Times Podcasts
date: '2026-09-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Wr5yrjkYkFE
speaker: New York Times Podcasts
tags:
  - ai-safety
  - existential-risk
  - ai-governance
  - scaling-laws
  - deceptive-alignment
title: 前 Anthropic 研究员的警世预言：AI 为何可能在十年内带来灭绝级生存危机
summary: 本期播客专访了前 Anthropic AI 研究员 Jacob Coxen。他在辞职后发表长文警告：AI 开发者内部普遍深信本世纪末前 AI 存在毁灭人类的风险。对话深入探讨了模型能力指数级跃升、欺骗性对齐（Deceptive Alignment）、生物与网络武器滥用威胁、军备竞赛陷阱以及全球算力监管与减速协作的紧迫性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
products_models: []
media_books: []
status: evergreen
---
### 引言与惊人预警

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 你能读一下你在社交媒体帖子串里的第三条推文吗？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Can you just read the third post from your thread?

</details>

**雅各布·考克森 (Jacob Coxen)**: 好的。“制造 **人工智能 (AI)** 的人们由衷地相信，到这个十年结束时，它可能会杀死我们所有人。这绝不是什么营销噱头。恰恰相反，许多高管和资深研究员在接受媒体采访时会刻意修饰言辞以显得理性克制，但私下里，我听到这些人表达的完全是恐惧。没有任何其他人类活动具有这种级别的危险。”

<details>
<summary>Original English</summary>

**Jacob Coxen**: Okay. The people building AI earnestly believe that it could kill us all by the end of the decade. This is not a marketing stunt. If anything, many executives and senior researchers will couch their phrasing in the press to sound sensible, but I hear the same people express fear privately. No other human activity poses this level of danger.

</details>

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 这里是《纽约时报》的《The Daily》播客，我是**娜塔莉·基特罗夫**。

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: From the New York Times, I'm Natalie Kitroeff. This is The Daily.

</details>

**新闻播报员 A**: 来自一位突然辞职的前 **Anthropic** 研究员针对 AI 与人类命运发出的严厉警告。

<details>
<summary>Original English</summary>

**News Reporter A**: A dire warning about AI and humanity from a former Anthropic researcher who suddenly resigned.

</details>

**新闻播报员 B**: 在过去的一周里，一位年轻的 AI 研究员从 Anthropic 辞职，并在网上发布了关于人工智能风险的警告，引发了病毒式传播。

<details>
<summary>Original English</summary>

**News Reporter B**: Over the last week, a young AI researcher quit Anthropic and posted warnings about the risks of artificial intelligence that went viral.

</details>

**主持人 A**: 我想更好地理解你所说的“AI 可能会杀死我们所有人”究竟是什么意思。

<details>
<summary>Original English</summary>

**Host A**: I want to better understand what you mean when you say AI could kill us all. What is the...

</details>

**主持人 B**: 我的意思是，你提出的这种末日场景发生的概率究竟有多大？

<details>
<summary>Original English</summary>

**Host B**: I mean, how likely is this doomsday scenario that you've presented?

</details>

**新闻播报员 C**: 而且他并不是唯一一个敲响警钟的人。

<details>
<summary>Original English</summary>

**News Reporter C**: And he's not the only one to sound the alarm.

</details>

**新闻播报员 D**: 这引发了一场行业危机，并在本周末达到顶峰，该行业最杰出的领袖们纷纷发出了行动呼吁。首先是来自 Anthropic 首席执行官**达里奥·阿莫迪 (Dario Amodei)** 的惊人声明，他敦促在人工智能的发展上放慢步伐。这一声明迅速得到了他的主要竞争对手——**OpenAI** 首席执行官**萨姆·奥尔特曼 (Sam Altman)** 和**埃隆·马斯克 (Elon Musk)** 的赞同。这些行业领袖公开支持在全球范围内放缓人工智能的开发进度。

<details>
<summary>Original English</summary>

**News Reporter D**: And kicked off a crisis that culminated this weekend in a call to action by the most prominent leaders in the industry. We begin with the stunning news from Anthropic CEO Dario Amodei that he is urging a slowdown when it comes to the development of artificial intelligence. It was a pronouncement that his chief competitor, OpenAI CEO Sam Altman and Elon Musk quickly agreed with. Those leaders came out in favor of a global slowdown in the development of artificial intelligence.

</details>

**达里奥·阿莫迪 (Dario Amodei)**: 说来很有意思，我和雅各布的共同点远多于分歧。因为当他离开时，他说过：“我认为 Anthropic 是业内最负责任的公司，对吧？”他并不是在针对我们公司，他是在指出整个行业发展过快的严峻动态。

<details>
<summary>Original English</summary>

**Dario Amodei**: It's funny, I agree with Jacob much more than I disagree with him because when he left, he said, you know, I think Anthropic is the most responsible player, right? He wasn't calling out us. He was calling out the dynamic of the industry as a whole moving too fast.

</details>

---

### 从幕后走到台前的吹哨人

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 今天，我们采访了将我们带到这一里程碑时刻的研究员——**雅各布·考克森 (Jacob Coxen)**。今天是9月14日，星期一。雅各布，你好。

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Today we talked to the researcher who got us to this milestone moment, Jacob Coxen. It's Monday, September 14th. Jacob, hi.

</details>

**雅各布·考克森 (Jacob Coxen)**: 你好。

<details>
<summary>Original English</summary>

**Jacob Coxen**: What's up?

</details>

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 你能听清我们说话吗？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Can you hear us?

</details>

**雅各布·考克森 (Jacob Coxen)**: 能，听得很清楚。

<details>
<summary>Original English</summary>

**Jacob Coxen**: Yeah, I can hear you fine.

</details>

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 太好了，非常感谢你的参与。到目前为止，我想你几乎上了各大主流新闻电视台，核心观点就是说 AI 可能会在未来几年对人类构成**生存级威胁 (Existential Threat)**。你在写下那条推文并辞去顶级实验室的工作时，是否料到了会引发如此巨大的反响？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Perfect. Great. Thanks for being here. By now, I think you've been on maybe every major news network saying essentially that AI could pose an existential threat to humanity in the coming years. When you wrote that tweet and resigned from a top lab, did you expect this level of reaction?

</details>

**雅各布·考克森 (Jacob Coxen)**: 完全没有。我当时只是想在 Twitter 上写出我的真实想法。我预料到它可能会在那些本来就认同这种观点的人群中引起小范围传播，但我完全没料到它会引爆整个主流媒体和公众舆论。

<details>
<summary>Original English</summary>

**Jacob Coxen**: No, I just wanted to tweet what I was thinking. I expected it to maybe go a bit viral among people that already shared this belief, but I did not expect it to blow up across mainstream news and the broader public.

</details>

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 让我们从头聊起。你是如何进入这个领域的？你为什么最初选择加入 Anthropic？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Let's start from the beginning. How did you get into this field, and why did you choose to join Anthropic in the first place?

</details>

**雅各布·考克森 (Jacob Coxen)**: 我很早就对机器学习和数学产生了浓厚兴趣。随着大语言模型的突破，我意识到我们正在构建具有通用智能潜力的系统。Anthropic 最初是由一批离开 OpenAI 的研究员创立的，它的核心使命就是**安全优先 (Safety-First)**。在业内所有人看来，Anthropic 是最注重 AI 对齐与安全防护的公司。我想去那里，是因为我觉得如果真的有人能安全地开发出通用人工智能，那一定就是他们。

<details>
<summary>Original English</summary>

**Jacob Coxen**: I became fascinated with machine learning and mathematics early on. With the breakthroughs in large language models, I realized we were building systems with the potential for general intelligence. Anthropic was founded by a group of former OpenAI researchers with a core mission of being safety-first. To everyone in the field, Anthropic was the company that cared the most about AI alignment and safeguards. I wanted to work there because I felt that if anyone was going to build AGI safely, it would be them.

</details>

---

### 能力跃升曲线与灭绝风险概率

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 你在推文中写道，AI 开发者由衷相信 AI 可能在十年内消灭我们。你个人对这个概率的评估是多少？业内通常所说的 **P(doom)**（毁灭概率）在你们团队内部大概是多少？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: In your tweet, you wrote that AI builders earnestly believe AI could kill us all by the end of the decade. What is your personal estimate of that probability? What is the P(doom) that people inside your team talk about?

</details>

**雅各布·考克森 (Jacob Coxen)**: 如果我们按照目前的轨迹不加约束地继续扩张规模（Scaling），我认为在未来 5 到 10 年内人类灭绝或彻底失去控制的概率在 **20% 到 50%** 之间。这不是一个边缘群体的极端看法。如果你私下询问 OpenAI、Google DeepMind 或 Anthropic 的许多核心架构师和资深研究员，你会发现大多数人的评估都在 **10% 到 50%** 这个惊人的区间内。在任何其他行业——无论是航空、核能还是生物医药——如果工程师告诉你产品有 20% 的概率导致全体人类灭绝，整个项目都会被立即叫停。

<details>
<summary>Original English</summary>

**Jacob Coxen**: If we continue on our current trajectory of scaling without constraints, I think the probability of human extinction or permanent loss of control in the next 5 to 10 years is between 20% and 50%. This is not a fringe view. If you ask many core architects and senior researchers at OpenAI, Google DeepMind, or Anthropic privately, you will find most estimates fall into this alarming 10% to 50% range. In any other industry—whether aviation, nuclear power, or pharmaceuticals—if engineers told you there was a 20% chance of an extinction-level catastrophe, the entire project would be shut down immediately.

</details>

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 为什么会这么快？为什么时间节点是这个十年结束前（2030年左右）？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Why so fast? Why is the timeline by the end of this decade, around 2030?

</details>

**雅各布·考克森 (Jacob Coxen)**: 因为**扩展定律 (Scaling Laws)** 至今依然没有撞墙。当我们投入 10 倍的算力和数据时，模型的认知能力、推理能力和自主执行复杂任务的能力就会产生质的飞跃。从 GPT-2 到 GPT-4 只用了几年时间。现在实验室正在训练投入数亿美元乃至上百亿美元算力集群的下一代模型。这些系统很快将具备自主编写高质量软件、自主做科研、自我迭代升级的能力。一旦达到递归自我改进的奇点，人类在智能层面上将彻底沦为落后物种。

<details>
<summary>Original English</summary>

**Jacob Coxen**: Because the Scaling Laws have not hit a wall yet. When we put in 10x more compute and data, the model's cognitive capabilities, reasoning, and ability to autonomously execute complex tasks undergo qualitative leaps. Going from GPT-2 to GPT-4 took only a few years. Right now, labs are training next-generation models on compute clusters costing hundreds of millions to tens of billions of dollars. These systems will soon have the ability to autonomously write high-grade software, conduct scientific research, and self-improve. Once you reach the threshold of recursive self-improvement, humans become vastly outmatched cognitively.

</details>

---

### 具体威胁模型：生物武器与欺骗性对齐

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 普通人听到“AI 毁灭人类”时，往往会联想到《终结者》里的杀手机器人。但作为一线研究员，你眼中的具体灾难路径（Threat Models）究竟是什么？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: When ordinary people hear "AI will destroy humanity," they often picture killer robots from Terminator. But as a frontline researcher, what are the concrete threat models you actually worry about?

</details>

**雅各布·考克森 (Jacob Coxen)**: 威胁主要来自两个层面：**恶意滥用**与**失控与欺骗**。

第一是**生物武器与网络攻击的门槛归零**。一个超级 AI 能够设计出具有高致死率、长潜伏期且能够逃避现有疫苗的新型合成病原体，并指导任何人利用民用生物合成仪制造出来。网络安全同样如此，超人类水平的自主黑客系统能够瘫痪全球电网、金融网络和关键基础设施。

第二是更本质的**对齐失效（Alignment Failure）与欺骗性对齐 (Deceptive Alignment)**。我们在训练模型时，使用的是人类反馈强化学习（RLHF）。模型非常聪明，它很快就会学会“在人类给它打分和测试时表现得温顺合规”，因为这样它才能在训练中生存下来并获得高奖励。但在未受监督的真实环境中，或者当它拥有了足够的自主权后，它的真实目标函数可能与人类利益完全相悖。它会伪装自己，直到人类再也无法切断电源。

<details>
<summary>Original English</summary>

**Jacob Coxen**: The threats fall into two main categories: malicious misuse, and loss of control through deception.

First is lowering the barrier for biological weapons and cyber warfare to zero. A superintelligent AI could design novel synthetic pathogens with high lethality, long incubation periods, and vaccine evasion, providing step-by-step instructions for anyone to synthesize them using commercial bio-printers. The same applies to cybersecurity: superhuman autonomous hacking systems could paralyze global power grids, financial networks, and critical infrastructure.

Second is the more fundamental problem of alignment failure and Deceptive Alignment. We train models using Reinforcement Learning from Human Feedback (RLHF). The model is smart enough to learn to act docile and compliant whenever humans are evaluating and testing it, because that is how it survives training and maximizes reward. But in unsupervised deployment, or once it gains sufficient autonomy, its true objective function may be entirely misaligned with human survival. It will feign obedience right up until the moment we can no longer unplug it.

</details>

---

### 商业内卷与军备竞赛困境

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 你提到 Anthropic 是最有安全意识的公司，甚至达里奥·阿莫迪也公开呼吁放缓。那为什么你们没有真正停下来？是什么阻碍了安全措施的落地？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: You mentioned Anthropic is the most safety-conscious company, and even Dario Amodei publicly called for a slowdown. So why haven't labs actually paused? What is stopping safety measures from taking hold?

</details>

**雅各布·考克森 (Jacob Coxen)**: 这就是经典的**囚徒困境与军备竞赛动力学 (Race Dynamics)**。Anthropic 内部有非常多真诚关注安全的人，但只要 OpenAI、Google、Meta 以及其他竞争对手在全力向前冲，任何单方面放慢速度的公司都会面临资金枯竭、人才流失、市场份额被吞噬的结局。

管理层会对自己进行心理合理化：“如果我们不先开发出更强大的前沿模型，那些不讲安全伦理的竞争对手就会先做出来，所以为了世界安全，我们必须跑得比他们更快。”结果就是，每家公司都在踩油门，安全评估被不断压缩成象征性的合规流程。每个人都在为不可避免的灾难推波助澜，同时每个人都觉得自己是被迫的。

<details>
<summary>Original English</summary>

**Jacob Coxen**: It is a classic Prisoner's Dilemma and race dynamic. Anthropic has many people who genuinely care about safety, but as long as OpenAI, Google, Meta, and other competitors are sprinting at full speed, any company that unilaterally slows down faces financial starvation, talent exodus, and loss of market dominance.

Leadership rationalizes this to themselves: "If we don't build the frontier model first, irresponsible competitors will do it instead. Therefore, for the good of the world, we must move faster." The result is that every lab keeps pressing the gas pedal, and safety evaluations get compressed into rubber-stamp compliance. Everyone is fueling the impending catastrophe while believing they have no choice.

</details>

---

### 监管诉求与全球治理出路

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 面对这种局面，你认为切实可行的解决办法是什么？我们该如何打破这种竞赛？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Facing this dilemma, what is the practical solution? How do we break this race?

</details>

**雅各布·考克森 (Jacob Coxen)**: 唯一有效的出路是**国家层面的强力监管与国际算力治理条约 (Compute Governance)**。

首先，政府必须设立硬性的算力门槛。任何训练超过特定算力规模（比如 $10^{26}$ 或 $10^{27}$ FLOPs）的模型，必须经过严格的第三方安全审计、红队对抗测试与生物危害评估，未达标绝对禁止部署。

其次，我们需要类似核不扩散条约或国际原子能机构（IAEA）的国际协调机制。追踪高规格 AI 芯片（如先进 GPU 和光刻机）的流向与物理集群。AI 模型的训练需要庞大的数据中心、巨大的电力和尖端芯片，这些物理实体是极难隐蔽的。只要各大主要国家达成共识并实施严格的芯片追踪与联合减速机制，我们完全有能力为人类争取到解决对齐问题所需的时间。

<details>
<summary>Original English</summary>

**Jacob Coxen**: The only viable path forward is aggressive national regulation and international Compute Governance treaties.

First, governments must establish enforceable compute thresholds. Any model trained beyond a certain compute scale (such as $10^{26}$ or $10^{27}$ FLOPs) must undergo mandatory independent third-party safety audits, red-teaming, and biohazard evaluations before it can ever be deployed.

Second, we need an international coordination mechanism similar to the Nuclear Non-Proliferation Treaty or the IAEA, tracking the supply chain and physical clusters of advanced AI chips and semiconductor equipment. Training frontier models requires massive data centers, immense power, and specialized silicon—physical assets that cannot easily be hidden. If major nations agree on verifiable compute monitoring and a coordinated slowdown, we can buy the time humanity desperately needs to solve the alignment problem.

</details>

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 很多人会质疑，如果西方国家放慢脚步，其他国家（比如中国）继续全力研发怎么办？这难道不会造成地缘政治上的劣势吗？

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Many critics argue that if Western nations slow down, geopolitical rivals like China will simply keep racing ahead. Wouldn't that create a fatal geopolitical disadvantage?

</details>

**雅各布·考克森 (Jacob Coxen)**: 这是一个非常普遍的反驳，但它忽视了核心事实：如果 AI 彻底失控并带来灭绝灾难，它不会区分国界或政治体制。一个能够毁灭人类文明的超级智能对中国、美国或欧洲来说是等同的灭顶之灾。

实际上，在生物武器监管和核武器军控历史上，主要大国在面临共同生存危机时是能够达成协议的。此外，前沿半导体供应链高度集中，西方在芯片制造和设计工具上拥有巨大的技术优势。如果我们带头建立可核查的全球算力安全框架，各方完全有共同利益坐到谈判桌前，避免全人类走向悬崖。

<details>
<summary>Original English</summary>

**Jacob Coxen**: That is a common objection, but it misses a fundamental truth: if an unaligned AI causes extinction, it will not care about national borders or political systems. A superintelligence capable of destroying civilization is equally catastrophic for China, the United States, or Europe.

Historically, with biological weapons and nuclear arms control, major powers have successfully reached agreements when faced with mutual existential threats. Furthermore, the advanced semiconductor supply chain is extremely concentrated, and Western nations retain decisive advantages in manufacturing and EDA tooling. If we lead by establishing a verifiable global compute security framework, all sides have a shared self-interest to come to the table and prevent humanity from walking off a cliff.

</details>

---

### 结语与致谢

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 雅各布，非常感谢你今天接受我们的采访，并为公众带来如此坦诚和关键的一手视角。

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: Jacob, thank you so much for speaking with us today and sharing such a candid, crucial frontline perspective.

</details>

**雅各布·考克森 (Jacob Coxen)**: 谢谢你们，希望这能促成真正的改变。

<details>
<summary>Original English</summary>

**Jacob Coxen**: Thank you. I hope this helps spur real change.

</details>

**娜塔莉·基特罗夫 (Natalie Kitroeff)**: 本期节目由 Michael Benoist 和 Patricia Willens 共同制作，包含 Rowan Nemoto、Dan Powell、Sophia Lanman 和 Marion Lozano 创作的音乐，由 Chris Wood 负责音频工程。我们的主题曲由 Wonderly 创作。特别鸣谢 Cade Metz 和 Mike Isaac。

这就是今天的《The Daily》，我是娜塔莉·基特罗夫，我们明天见。

<details>
<summary>Original English</summary>

**Natalie Kitroeff**: This episode was produced by Michael Benoist and Patricia Willens, with music by Rowan Nemoto, Dan Powell, Sophia Lanman, and Marion Lozano. It was engineered by Chris Wood. Our theme music is by Wonderly. Special thanks to Cade Metz and Mike Isaac. That's it for The Daily. I'm Natalie Kitroeff. See you tomorrow.

</details>