---
author: Dwarkesh Patel
date: '2026-08-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=iewm45atodE
speaker: Dwarkesh Patel
tags:
  - continual-learning
  - ai-regulation
  - technical-alignment
  - inference-economics
title: 持续学习时代的8个预言：AI范式的根本性重构
summary: 探讨AI持续学习（Continual Learning）实现后将带来的八大变革。作者指出，持续学习不仅会颠覆现有的AI监管模式与对齐技术，还将重塑商业竞争壁垒、推动AI思维的多样化发展，并赋予大型组织在推理成本上的巨大经济优势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
products_models:
  - Mythos
  - DeepSeek-V3
media_books: []
status: evergreen
---
### 持续学习的必要性与萨克斯隐喻

在探讨人工智能的演进时，作者指出真正的**持续学习**（Continual Learning: AI系统在部署后持续吸收新经验并更新权重能力）对于让AI像人类一样胜任整份工作是必不可少的。目前的AI系统被迫在不同会话之间仅通过编写Markdown文件来传递信息。为了形象地说明这一局限性，作者使用了一个**萨克斯学习隐喻**：想象一个从没吹过萨克斯的学生进入音乐厅尝试演奏，首次尝试必然失败。他写下一堆关于失误的笔记。排在门外的下一个学生进来阅读这些笔记，但因为他也没吹过，同样会搞砸并继续累加笔记。如此循环往复，门外有无数个学生通过笔记向后人传递经验。显而易见，没有任何文本序列能让后续的学生仅凭阅读就在首次尝试中完美演奏萨克斯。要在某项技能上真正取得突破，大脑必须在某个时刻**实际积累相关经验**。对于我们希望AI在各种部署现场真正积累的许多技能而言，情况完全相同。

<details>
<summary>Original English</summary>
I've explained elsewhere why I think actual continual learning is needed. I don't think you can have AIs that perform whole jobs as competently as humans if they are forced to just write markdown files from session to session. Just to give an illustrative example, imagine if this is the way that students learn to play the saxophone. You have one student, he's never played the saxophone before. He goes into the music hall, he tries to play it. Of course, this is his first time, so he fails, and he writes down a bunch of notes about what went wrong. And there's a next student who's waiting outside the music hall. He comes in, he reads all these notes. He's also never played, so of course he messes up, and he continues to add on to these notes. And you have an infinity of students outside the music hall who keep writing notes to the next person. I don't think there's any sequence of text they could write to each other that would allow the subsequent student to just nail the saxophone from the first try. At some point, you actually have to accumulate the relevant experience into your brain. I think the same thing will be true for a lot of skills that we want AIs to actually accumulate from all the different workplaces in which they're deployed.
</details>

### 重构安全监管与技术对齐的范式

当真正的持续学习成为现实后，现有的AI监管和技术对齐范式将被彻底颠覆。当前的许多**AI监管提案**（AI Regulation Proposals: 针对人工智能开发和部署制定的政策与法律规范）都建立在“先训练模型再进行部署”的静态假设之上，认为只要在部署前进行一系列安全检查，就能防范网络攻击等潜在威胁。然而，如果模型在部署后基于每天数百万次的工作会话不断进行自我更新和提升，这种静态的检查方法将彻底失效，甚至可能将监管锁定在过时且适得其反的框架中。因此，政府应将安全评估调整为月度或季度的**风险检查**（Risk Inspection: 对运行中AI系统进行的高频定期安全审计），而不是试图寻找一个“训练完成与部署开始之间”的特殊节点，因为在未来这种界限将不复存在。

与监管变革相呼应，AI实验室的**技术对齐**（Technical Alignment: 确保AI系统行为符合人类意图和伦理标准的工程技术）方法也必须进行根本性重构。目前的大多数研究聚焦于如何让一组静态权重在部署期间保持良好行为，但鲜有研究探讨在权重持续更新的情况下，如何确保AI系统不会被恶意**提示词劫持**（Jailbreak: 绕过安全机制使AI输出违规内容的攻击手段）或转化为具有欺骗性的邪恶人格。此外，当AI在不同用户之间整合学习经验时，如何防范恶意用户向基础模型注入后门或不良倾向，也是一个亟待解决的挑战。这在某种程度上与**人类对齐问题**（Human Alignment Problem: 引导人类个体在成长中形成健康社会化价值观的过程）高度一致：父母即使希望给予孩子足够的常识和基本价值观，让他们能够自我引导成长，也无法完全避免他们在外出接触新事物时可能被偏激意识形态影响或误入歧途。

<details>
<summary>Original English</summary>
Okay, so what changes once we have actual continual learning? One, I think that a lot of proposals that have been put forward about regulating AI assume that you train a model and then you deploy it. And therefore, if you run a bunch of checks on the model before it is deployed, we can make sure that it's not going to aid in cyber attacks or do something crazy. I don't think this assumption necessarily makes sense in the future, and this is one of the many reasons I'm worried about locking in some kind of safety regulatory regime right now — because we don't know what kind of technology we're going to be dealing with even within a year, let alone within five or ten years. What if the model is improving every single day based on the millions of sessions of work it does in that day? If that happens, we could potentially be locking in an archaic and potentially counterproductive approach to dealing with the threats from AI. To the extent the government wants some way to do safety evaluation on model providers, I think it would make more sense to do monthly or quarterly risk inspections rather than trying to single out some special moment that occurs after training is done but before deployment begins, because that will not be a meaningfully distinct category in the future. Two, how the labs do technical alignment would probably totally need to change. Right now, a lot of research is focused on the question of how we make sure that a frozen set of weights behaves well during deployment. But I'm not aware of much research on the question of how we make it so that even with constant weight updates, the AI system never falls prey to jailbreaks or changes into a deceptive or evil persona. And if AIs are consolidating learnings between users as well, how do we prevent users from injecting backdoors or some kind of malicious inclination into the base model? In some sense, this is what the human alignment problem is, right? Humans improve in a self-directed way. If you have kids — I don't have kids, but I imagine this is what happens — they go out, they learn new things. Sometimes they go crazy. They get one-shotted by crazy ideologies, they take the wrong drug, they become super weird. But you hope that you've given them enough common sense and basic values that they improve as people in a self-directed way without ending up with some super weird beliefs or misanthropic ideas.
</details>

### AI心智多样化与竞争飞轮的加速

随着部署过程深度融入训练，AI生态的竞争动态将发生剧烈变化。首先，**AI心智多样性**将显著提升。当前全球仅有少数几个主流AI心智（即服务于数亿用户的几个核心基础模型），并且由于训练数据高度重合，它们的表现极为相似，呈现出某种**模式崩塌**（Mode Collapse: 模型生成样本单一、缺乏多样性的现象）。然而，一旦AI能够从不同的部署经验中学习，不仅不同厂商的模型会分化，即使是同一模型的不同实例也会演化出独特的特性。这种多元化的AI生态将远比目前的单一单调世界更有趣。

与此同时，这种机制将导致**先发优势**（First-mover Advantage）急剧放大，形成难以逾越的竞争飞轮：拥有最强模型的实验室将吸引更多用户处理复杂、有价值的工作，这会产生海量的真实反馈，并被模型在会话窗口之外持续吸收，使其变得更加聪明。这也将迫使实验室不得不提前发布其最先进的模型。以 **Anthropic** 为例，据报道其在内部使用 **Mythos** 模型长达数月才向公众发布，而在持续学习的时代，这种长达数月的内外部署差距将不复存在。因为如果不能及时将模型推向市场以获取真实世界的经验，即使初始性能稍逊的竞争对手也会在短时间内通过实战学习反超，这在商业竞争中是致命的。

<details>
<summary>Original English</summary>
Three, the diversity of AI minds will increase. Right now, there are less than five prominent AI minds, by which I mean the base models which are served to millions or hundreds of millions or billions of users at once. And they're all quite similar to each other, by the way, because they've all been trained on roughly the same data. But if AIs are learning from experience, and that experience is different between not only different AI companies but also between different instances of the same AI model, we could see a lot of diversity come out the other end in this world. And this would be, I think, a net good outcome. One of the things to worry about in the future is having this monolithic singleton that's quite boring. A world where we have continual learning would hopefully be more interesting than the mode collapse of different models we see in the world right now. Four, when deployment becomes part of training, the returns to being ahead in the AI race accelerate. If you have the best model and more people are using your AI for more complicated and useful work, and as a result they're giving it lots of feedback that it can integrate beyond the session window, then your model will become even smarter. Five, if the model learns mainly from deployment, then labs will feel a lot of pressure to deploy their smartest models earlier. Anthropic has reportedly been using Mythos internally since February, but it only shipped the model to the public in June. In the regime with actual continual learning, this kind of thing would just not be possible. You could not keep a four-month gap between internal and external deployment and still be competitive, because a competitor who ships a worse model on release date will have a smarter model based on actual real-world experience.
</details>

### 商业护城河与大型组织的推理经济学

在商业维度上，持续学习为AI实验室创造了目前极其欠缺的**商业护城河**（Business Moat: 企业抵御竞争对手、维持长期盈利能力的结构性优势）。当前，用户在不同工具之间的迁移成本几乎为零。然而，一旦引入持续学习，模型能够随着时间推移在会话间不断积累特定用户的上下文。此时，更换AI供应商的代价相当于“解雇一个已经积累了数月组织上下文的老员工，换来一个必须从头培训的零经验实习生”。这种巨大的**迁移成本**（Switching Cost: 客户从一个供应商转向另一个供应商时所面临的一次性成本）使模型提供商能够索取极高的利润率。

尽管企业会极力避免这种锁定，但他们可能不得不面对“接受供应商锁定”或“放弃持续学习功能”的二选一局面。为了获取宝贵的会话数据，AI实验室甚至会采取“胡萝卜加大棒”的策略：向愿意提供会话数据进行训练的用户提供高额补贴（类似于谷歌免费提供搜索的逻辑），并对拒绝提供数据的企业限制访问最先进的模型。

此外，这种个性化权重的升级也深刻影响着**推理经济学**（Inference Economics: 运行人工智能模型生成输出时的成本与计算效率关系）。由于不同公司的权重分叉需要进行完整的权重更新，而非仅使用低秩适配器，此时通过**批处理**（Batching: 将多个计算请求合并为一组共同处理以提高硬件利用率的技术）来分摊算力开销将带来巨大的成本优势。粗略计算表明，对于像 **DeepSeek-V3** 这样的稀疏模型，最优的推理批处理大小需要达到2400个并发序列。在这种经济规律下，拥有大量员工和代理进行高并发操作的大型组织可以非常高效地运行其专属的权重分叉，而单序列运行的个人用户在算力效率上可能会面临两个数量级以上的劣势。因此，持续学习时代的推理经济将极大地偏向大型机构。

<details>
<summary>Original English</summary>
Six, continual learning will create a clear moat for the leading AI labs that they currently lack. Many people have been asking, "How will the AI labs actually make money?" I have been asking this. When I had Dario on the podcast, I asked him this question, and he made the analogy to cloud providers. He made the point: look, the cloud providers are offering many undifferentiated services, but they're earning high profit margins nonetheless. You will have noticed this if you look at Amazon or Google's quarterly earnings — they're doing just fine. But the reason that the cloud margins are so high is that it's really time-consuming and expensive to switch from one cloud to another. Currently, there's nothing stopping me from starting a software repository with Codex, then doing more work on it with Cursor, and then finishing it up with Claude Code. But once we have actual continual learning, and the model you're working with is actually getting better as it interacts with you from session to session, then there are pretty significant switching costs. If you want to change the AI that you're using, you basically have to fire an employee that has accumulated months of context on your organization, and replace them with a very fresh, very unexperienced new intern that you've got to retrain from scratch. And once you have this kind of lock-in, model providers can demand pretty hefty margins. Sorry. Really emphasis on the fresh intern. Seven, of course, enterprises will be wise to this kind of dynamic. They will try to avoid this kind of lock-in. But what if the choice is that you either get locked into a model provider or you lose out on this super valuable feature where your model improves for you from session to session? If real usage ends up being the main way the models improve, then the AI labs may subsidize users and enterprises which allow the model to train on their sessions. This is already happening if you look at the kinds of deals that are offered to new users of coding products. This is very similar to why Google gives away search. And conversely, the labs may say that any enterprise that refuses to let them train on the sessions can't have access to the very best models. With both carrots and sticks, the labs can do a lot to get users to allow AIs to learn from experience. Now, of course, I'm glossing over the fact that there's a difference between updating one user's set of weights and pooling all these different weight forks back into the main model, and the latter may be more technically challenging. But in due time, this too will be solved. Eight, AI training already has large economies of scale. You get to amortize all this expensive training across more users, and you see the evidence for this in the fact that the lab revenues are increasing far faster than their compute. But continual learning may also lead to economies of scale in inference for end users, namely from batching. You might have seen my episode with Reiner Pope where we discussed this in detail. But if per-company information require full weight updates rather than living in low-rank adapters, there are huge advantages from batching. Back-of-the-envelope math suggests that the optimal inference batch size for a sparse model like, say, DeepSeek v3 is more than 2400 concurrent sequences being generated at once. If you don't do this, then you're underutilizing your compute. And if you want to understand why, again, I highly recommend that episode with Reiner on inference economics. But anyways, the point here is that a given set of weights is only served efficiently when thousands of sequences are being decoded against it all at once. A large company with lots of employees and agents who are doing lots of different kinds of things can very efficiently serve their weight fork, whereas an individual user who's only running a batch size of one may suffer more than two orders of magnitude worse efficiency on their compute. So the economics of serving personalized weights strongly favor big organizations. Obviously, plenty more will have changed by the time that continual learning actually works, and the most important changes are probably the ones that are hardest to anticipate in advance. But the ones above seem clear even now. This was a narration of a blog that I also published on my website. Go check it out at dwarkesh.com. Otherwise, I will see you on the next podcast.
</details>