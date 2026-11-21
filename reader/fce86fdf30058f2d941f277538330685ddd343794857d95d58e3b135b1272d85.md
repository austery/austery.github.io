---
author: Latent Space
date: '2026-10-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kog7mwsDqnk
speaker: Latent Space
tags:
  - recursive-language-models
  - gpu-kernel-optimization
  - agent-scaling
  - research-methodology
  - post-training-scaling
title: Alex Jung访谈：RLM架构、GPU算子自动化与科研方法论
summary: 本文记录了Alex Jung关于递归语言模型（RLM）的讨论，强调通过局部分布内任务分解提升系统稳定性。同时回顾了GPU Mode社区及Kernel Bench在自动化GPU算子开发中的贡献，并探讨了在注意力稀缺时代，如何平衡工业应用与纯科学探索的研究策略。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Alex Jung
  - Mark Saroufim
  - Jeremy Howard
  - Tri Dao
companies_orgs:
  - Snapchat
  - MIT
  - Anthropic
  - OpenAI
  - PyTorch
products_models:
  - RLM
  - Claude Code
  - Codex
  - Kernel Bench
  - Mamba
media_books:
  - Infinite Attention
status: evergreen
---
<!-- chunk 1/13 -->

### 模型能力与规模化算力投入

**主持人**：哦，我就是太喜欢这些了。Claude Code、Codex，我都非常喜欢。还有 Pi，不，我是说我喜欢 Oh My Pi，还有 Prime。老实说，我认为它们都差不多。你知道的，如果你肯花心思去引导，模型其实能做到更多。所以这本质上是一个技术水平（Prompt 技巧与使用能力）的问题。

<details>
<summary>Original English</summary>

**Host**: Oh, I just love it. Claude Code. I love Codex. I love Pi. No, I am. I love Oh My Pi. I love Prime. Fair saying, I think that they are all the same. You know, your models actually capable of more if you make an effort. So it's a skills issue.

</details>

**Alex Jung**：是的，没错。大体上，我认为有一点是我特别想看到的。我很欣赏对智能本身的重点关注，因为这展现了一幅宏伟蓝图——如果我们真正给自己设定目标，我们就能做到这些。但我其实希望，也许学术界应该有人来做这件事：大家不妨坐下来认真想一想，即便拿最先进的现代模型来说，单凭它本身也不足以持续且保质保量地执行某项工作，比方说连续稳定运行一个月。如果投入 10,000 个 Agent 运行 88 个小时，那相当于大约 1,300 亿个公开 Token，按照公开 API 价格估算大约需要 4,000 万美元。也许你必须支付大约 4,000 万美元才能跑出最终结果。虽然听起来有些夸张，但这确实令人兴奋。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes. Yes. In the main, I think there is one thing, which I want to see. I appreciate what is great focus on intelligence, because it gives the big picture that we can do this to do if really let's set ourselves goal. But I would like to, and, maybe someone in academic circles should have done it. Really easy to sit down and think: if I took Astra, even modern advanced the model is not enough good to perform a certain work, let's say, during the month, consistently and qualitatively. That's, uh, 10,000 agents for 88 hours. Hmm, 130 billions of public tokens that estimated at approximately 40 million dollars at public prices. Maybe you will have to pay about 40 million dollars to get result. And this is kind of, well, but it's exciting.

</details>

**主持人**：我想说的是：我们如今拥有的能力已经非常惊人了。但问题在于，我们到底有没有可能真正调动 4,000 万美元直接用来解决某一个具体问题？

<details>
<summary>Original English</summary>

**Host**: I will say this: it is very It's amazing what we have. Is there a possibility at all direct 40 million dollars for problem solving.

</details>

**Alex Jung**：确实如此。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes.

</details>

### 播客频道订阅倡议

**主持人**：在正式进入今天的节目之前，我有一条简短的消息想对各位听众说。谢谢大家。如果没有你们，我们根本无法持续为大家带来关于 AI 工程、前沿科学与科技趣味的内容——我知道你们一直想参与进来。几乎每天都有赞助商找上门来，但幸运的是，你们有足够多的人订阅了我们，使我们能够在没有广告赞助的情况下保持独立与可持续发展，我们希望未来也能一直如此。但我只有一件事想拜托大家，这是你们能做的最有力、而且完全免费的一件事——点击“订阅”按钮。这是我唯一会向大家请求的事。这对我和我们每周辛苦制作这些内容的团队来说意味着一切。如果你们点击了订阅，我保证我们会不断努力，把节目做得越来越好。

<details>
<summary>Original English</summary>

**Host**: Before we move on until today episode, I have small message for listeners. Thank you. We could not offer you content about AI engineering, science and entertainment, which you are so I wish you would too haven't decided press and connect to our content. To us almost every day sponsors are applying. But, fortunately, enough of you subscribe to us, to do all this sustainable without advertising, and we want it to be so remained in the future. But I have one thing. A request to all of you. The most powerful and completely free thing you can do—this press the button "Sign up". It the only thing I ever... I'll ask you something. AND this means absolutely everything for me and mine team, which is works hard to bring every week these materials to you. If you do this, I promise that we will never we will not stop to work on, to make the show even better better.

</details>

### 嘉宾介绍与 GPU Mode 社区的起源

**主持人**：现在，让我们切入正题。今天来到演播室的嘉宾是 Alex Jung。你最为人所知的可能是因为 RLM，但你还有很多其他的背景。欢迎来到节目！

<details>
<summary>Original English</summary>

**Host**: Now, let's get down to business. So, we're here in the studio with Alex Jung. Uh-huh probably the most known thanks to RLM, e- uh, but you have more several other connections. Welcome to show.

</details>

**Alex Jung**：是的，非常感谢你的邀请。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes, thank you for that invited.

</details>

**主持人**：是的，大家认识你可能还因为 GPU Mode 社区。

<details>
<summary>Original English</summary>

**Host**: Yes, probably also GPU mode.

</details>

**Alex Jung**：没错，还有 GPU Mode。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes, GPU mode too.

</details>

**主持人**：是 Mark Saroufim 把你引荐到这里的，可不是每个人都能享受这种待遇。

<details>
<summary>Original English</summary>

**Host**: Well, I brought you here. Mark Sarafin. Not everyone gets one reception.

</details>

**Alex Jung**：是的，哈哈。我和 GPU Mode 里的大家都非常熟悉，所以我们经常在不同的角色中合作，甚至超出了 GPU Mode 社区本身的范畴。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes. Aha. Yes, I am very close to everyone people in GPU mode. So we we often work together in different roles, even outside the borders GPU mode itself. Therefore, yes.

</details>

**主持人**：我们能为那些不太了解的人解释一下吗？这是一个 Discord 服务器，最初专注于 CUDA mode，后来逐渐扩大了范围，是由 Mark 创建的。

<details>
<summary>Original English</summary>

**Host**: Can we explain this for those who doesn't know? This is Discord server. He used to was focused on CUDA mode, and then a little expanded. Its created by Mark.

</details>

**Alex Jung**：是的。在我看来，它就像是 PyTorch 团队的人才储备库，之后 Mark 离开了 PyTorch。是的，我想这个社区大约是在 2023 年我还在读大学时出现的，最早由 Mark Saroufim、Andreas 和 Jeremy Howard 发起。最初的设想是一个专门学习编写 GPU 算子/内核（Kernel）的 Discord 服务器，并在里面开办讲座。基本上起步就是这样。而我之所以对此产生兴趣，是因为我当时恰好在写 GPU 算子，那完全是一次偶然。我当时在 Snapchat 的推荐系统（Rexus）团队实习。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes. As to me, it's like personnel reserve for PyTorch commands, and then you left PyTorch. Yes. Yes. Yes. Yes. So, I think he appeared when I was in colleges, sometime in 2023 year. I think it's him started by Mark Andreas and Jeremy Howard. Primary the idea was that that it was a Discord server for training writing GPU cores, where gave lectures. This is it there was almost everything. And I interested in this because wrote GPU cores. It it happened cleanly accidentally. I was then an intern at Snapchat and Rexus.

</details>

**主持人**：是的。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

### 从无限注意力算子到 Popcorn 排行榜与 Kernel Bench

**Alex Jung**：我在推荐系统团队觉得挺枯燥的，刚好组里有个项目想做点东西。当时有一篇标题叫《Infinite Attention》（无限注意力）的论文，好像是 Google 发的。

<details>
<summary>Original English</summary>

**Alex Jung**: I was very bored with Rexus. So they have there was a project for which they wanted something write. It was article entitled "Infinite Attention". It seems this was an article from Google.

</details>

**主持人**：是的，我们还在论文俱乐部里讨论过那篇论文。

<details>
<summary>Original English</summary>

**Host**: Yes. We discussed her in our Paper Club.

</details>

**Alex Jung**：没错。所以当时我就在琢磨能不能在 Snapchat 为这个模型写定制化的 GPU 算子。虽然最终那个项目没做成，但我就是在那时候加入了 GPU Mode。当时它还叫 CUDA Mode，我想后来是因为法律和商标原因改了名字。在那里我结识了 Mark、Mate 以及许多对社区极度投入的人。接着 Mark 提出了一个叫 Popcorn 的想法，也就是现在大家所熟知的排行榜（Leaderboard）。大家当时都有一个直观的认知：编写 GPU 算子非常像竞技算法编程（ACM/Codeforces 这类竞赛）。我并不是说这种技能完全可以无缝迁移，但感觉很像在做 Code-golf 极限优化。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes. Yes. So me I was wondering if it was possible write for this specialized kernels on Snapchat. Nothing from this. It didn't work out, but I joined GPU mode in that time. He was called CUDA mode. I think from legal reasons they changed name, but I met Mark, Mate and many other people, which were very involved in the community. And then Mark proposed the idea called Popcorn, which now known as leaderboard. General the idea was that that we all had intuitive understanding: GPU programming very similar to sports programming if you were doing it. It not that I'm saying that this is quite transferable skills. You do a little coding-golf.

</details>

**主持人**：是的，没错。

<details>
<summary>Original English</summary>

**Host**: Yes. Yes. Yes.

</details>

**Alex Jung**：实际上，人们在底层算子中所使用的优化手段集是非常有限的，而大家真正需要优化的关键算子种类也并没有那么多。于是我们就在想：如果我们能有足够多的数据，就像 Codeforces 上有上百万道编程题那样，如果能把 GPU 代码也做成类似形式，我们是否就能规模化并自动化 GPU 算子的研发？这对研究人员来说将是巨大的一步。因为目前最大的痛点之一在于——比如以 Mamba 为例，作者在发表论文时必须连同底层算子一起开源，否则外界根本无法高效运行它，你能明白吗？而且并不是每个研究团队里都配有像 Tri Dao 这样顶尖的系统级专家。所以大家都觉得这非常有意义。Kernel Bench 正是从这些想法中诞生的：我们能否让大语言模型（LLM）自动化生成 GPU 算子代码？这项工作对我而言充满了乐趣。那段时间正好处在我本科毕业和攻读研究生之间，我在 GPU Mode 社区里做得很开心。现在我有空时偶尔会帮着做做讲座，虽然不像以前参与度那么高，也不像过去那样举办密集的比赛，但我依然和所有的核心成员保持着联系。

<details>
<summary>Original English</summary>

**Alex Jung**: AND actually exists surprisingly limited set of optimizations, which use people. And not really so many nuclei, what people want optimize. And we thought: what if we were enough data, similar to Codeforces, where there are millions tasks? If possible was to do it with code for GPU, you can would be to scale and automate development of GPU cores, and this for researchers a huge step. For, I think one of the biggest problems—for example, let's take Mamba: they publish article together with cores, because otherwise you you will not be able to effectively to use them, do you understand? And not in everyone on the team has Tri. So we are very interesting. Kernel Bench emerged from the same ideas: can we to force LLM automate code for GPU cores? I was very fun over this work. It was between college and postgraduate studies, and I with pleasure indeed was doing things in GPU Mode. Now I sometimes just helping with lectures. I'm not like that anymore involved, and I think that we are spending it wrong many competitions, like before, but I still I keep in touch with all participants.

</details>

### GPU 编程竞赛生态与行业过热现状

**主持人**：你们之间是否存在友好的竞争？因为在我看来，过去做这类基准评测的社区就像 MLPerf 那样……你们之间是良性竞争吗？这算是新一代的 MLPerf 还是正在发生什么变化？

<details>
<summary>Original English</summary>

**Host**: Or do you have a friendly competition? Because, as me, previous community that was doing this, on like MLPerf... Do you have friendly competition? This is just new MLPerf generation or what is happening?

</details>

**Alex Jung**：GPU Mode 最美妙的地方在于它是一个纯粹的学习型社区：大量的讲座门槛非常低，足以让初学者随时提问交流；那里的比赛并不是唯一的目的，你参赛更多是为了学习和提升。我认为像 MLPerf 这样的基准评测，大多只有正规的大型实验室或头部科技企业才会深度参与，至少在专业水准上是如此。至少据我了解是这样。或许我理解有偏差，但除了 GPU Mode 之外，令人非常激动的是最近涌现出了很多类似的平台，以及许多投身组织此类比赛的人。例如，现在出现了一个叫 LeetGPU 之类的网站，就类似于针对 GPU 算子题目的 LeetCode。我们在 GPU Mode 里也看到了其他类似平台的讨论。这非常令人兴奋，因为在过去，GPU 编程是一门极度小众和高度专业化的手艺。我之所以对这个领域产生兴趣，唯一的契机就是 Tri Dao 到普林斯顿做了一场报告（他当时在应聘教职，现在已经在普林斯顿任教了），我在 2023 年听了他关于 FlashAttention 的报告，心里直呼：“哇，这简直是世界上最酷的东西！”当时我也觉得这是每个人都必须深入研究的领域。后来 VLLM 等项目纷纷面世，大家都在喊“天呐，我们必须去手写算子”。但发展到现在，似乎人人都在写算子……在某种程度上，我认为这个领域甚至已经有些过度饱和了。

<details>
<summary>Original English</summary>

**Alex Jung**: The beauty of GPU Mode because it's a community: many lectures are enough available for beginners to bet questions, but competitions there—not that secondary, but you you can take them participation for the sake of teaching. I think so many benchmarks, such as MLPerf, mostly take only serious participants laboratories and companies, at least on a serious level. At least that's how I understood. Maybe I I'm wrong, but except for the GPU Mode, it is very exciting that what has just appeared much more sites and people who are engaged in organization of such competitions. For example, it seems there is this one. It seems there is such a site like LeetGPU or something like that, it's like LeetCode for GPU tasks. There is also others we have seen, they appeared, about they were talking in GPU Mode, and this is very exciting because earlier programming for GPU was something extremely highly specialized. The only reason why I am interested in this, is that Tri performed with report in Princeton, because he applied for teaching position—that is, now he is already teaches there, but I listened to him flash attention report in 2023 and thought: "Wow, this is the coolest thing in the world." Um, me too I thought that was it, over which everyone has work. It seems VLM and other things came out, and we're like, "Oh, we must write kernels", but now everyone they write kernels, it's... me I think that in a certain in a sense, this industry is almost oversaturated.

</details>

### AI 生成算子的突破与正确性验证隐患

**主持人**：对于那些现在想要进入这个领域的人，有什么值得注意的建议吗？最近最轰动的新闻之一是——GPT-5.6 编写出了更高效的算子，从而可能让 Terra 和 Luna 等模型的运行成本降低 80%。

<details>
<summary>Original English</summary>

**Host**: There are some interesting tips for those who want this to do? I think, one of the loudest news—GPT 5.6 wrote more efficient cores, therefore Terra and Luna can become 80% cheaper.

</details>

**Alex Jung**：是的。而且我们还看到在其他竞赛中，有人声称使用了一套自动科研迭代流程（Auto-research Loop）创下了性能纪录，即便这些人本身没有任何算子编写经验。

<details>
<summary>Original English</summary>

**Alex Jung**: Yes. And we also saw other competitions where people set records, claiming, what is used a certain cycle auto research, although these are people without experience writing kernels.

</details>

**主持人**：确实如此。

<details>
<summary>Original English</summary>

**Host**: Rightly.

</details>

**Alex Jung**：对。所以即使在 GPU Mode 的排行榜上，如果你翻看最近的许多挑战赛，几乎所有高分方案都是由 AI 生成的。然而，如果你仔细观察排行榜，会注意到有一位叫 Gorst 的选手，他是 GPU Mode 的老牌常驻参赛者。我们很久以前就知道他是一名极其出色的 GPU 算子开发者。我们发现了一件事：在这个排行榜里，他也确实借助了 AI 来辅助构思解决方案，但他主要是由人把控大方向并给出关键提示词线索。最后我们发现，在前十名的成绩中，几乎只有他的算子在真实的复杂系统中能够真正稳定、正确地运行。这就引出了一个核心问题：GPU 算子往往存在极其严重的正确性验证困难。大家似乎对此……

<details>
<summary>Original English</summary>

**Alex Jung**: Yes. So even in GPU mode leaderboards, if you look at many recent tasks, almost all solutions generated AI. However, you will notice in the leaderboard a guy named Gorst, who is very, very constant GPU mode participant. We have known for a long time that he extremely cool GPU core developer. We found out one thing: in this leaderboard he too used AI for help with solutions, but mostly he directed the work clues in a certain direction. We found that that its core was practically the only one in top 10, which is actually worked stably in real complex systems. This raises the question, because GPU cores have problem with verification. We are it as if they knew. It

</details>

<!-- chunk 2/13 -->

### 领域专长与 AI 时代的系统规划

**Speaker A**: 自从 KernelBench 发布以来，我们遇到了不少问题。那里发生了大量的系统投机取巧（system hacks）和奖励黑客行为。不过……你是否也注意到，代码行数变得大大减少了？这一点明显吗？还是说仅仅……

<details>
<summary>Original English</summary>

**Speaker A**: problem since kernel bench output. There a lot is happening system hacks rewards. But you... Yes. You too you notice that the lines code much, much Less. Is this noticeable? simply...

</details>

**Speaker B**: 是的，毫无疑问，这一点非常重要。而且我认为非常耐人寻味的是，在这个领域保持专业深耕，依然拥有巨大的优势。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. No, it is definitely very important. And I I think it's very interesting that there is still a big the advantage is that to be in this professional.

</details>

**Speaker A**: 当然存在优势。

<details>
<summary>Original English</summary>

**Speaker A**: Of course, there is.

</details>

**Speaker B**: 是的，我也这样认为。很多 AI 系统也是如此，哪怕最近在数学定理证明等任务上取得突破，但这并不意味着数学家就过时淘汰了。我的意思是，这些顶尖科技公司依然在招聘数学家，要么用于高质量数据标注，要么就是为模型在求解复杂难题时指明探索方向。因此，在这些领域拥有深厚的专业知识，依然是一项巨大的竞争壁垒。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. I I think so too concerns many AI systems too, even with the last ones mathematical proofs, etc., this not necessarily means that became mathematicians outdated. I have on meaning that these companies still hiring mathematicians, or for data markup, or even just for direction of models in solving problems, so in the deep knowledge in these areas there is still a big advantage.

</details>

**Speaker A**: 那么，这种优势仅仅在于行业知识本身，还是也关乎更好的规划能力？是否有某种全新的规划架构被证明更加高效？

<details>
<summary>Original English</summary>

**Speaker A**: Therefore, is it just knowledge or it is also about better planning, and is there any new one planning approach, what works more effective?

</details>

**Speaker B**: 我觉得这是两者的融合。或许这就是你所说的那种关于“如何拆解与解决问题”的直觉。例如，在写代码时，我总是会先绘制系统架构图。

<details>
<summary>Original English</summary>

**Speaker B**: I think that this combination, perhaps, this is what you have on under the intuition about how solve the problem. For example, I always I draw diagrams of my code.

</details>

**Speaker A**: 没错，确实如此。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. That's right.

</details>

**Speaker B**: 如果在架构图中有任何一部分是我没彻底搞明白的，我就会反复推敲研究，直到把它完全弄清楚为止，否则绝不能接受直接动手编码。

<details>
<summary>Original English</summary>

**Speaker B**: And if in this there is a part in the diagram that I don't understand, I'm working. over her, until I'll figure it out. Otherwise it is unacceptable.

</details>

**Speaker A**: 是的，完全赞同。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Yes.

</details>

**Speaker B**: 所以我认为这是多重能力的结合：懂得洞察问题本源并知道如何求解的人，同时也懂得如何将 AI 作为杠杆来辅助这个过程。如果你自身拥有硬核的专业领域知识、清楚正确目标是什么，你就能充当一个极高水准的验证者（verifier）。另外我认为，从当前涌现的所有智能体群（swarms of agents）以及类似研究中，我们学到的一点是：当你向一个问题倾注充足的算力时，确实可以充分探索解空间。但现实中经常出现的情况是，你可能花费了一千亿甚至一万亿个 Token 在无谓的穷举上；而如果引入一位真正吃透该问题的领域专家，他只需给模型稍作指点，就能避免耗费这上万亿 Token 的无用功。不过必须说明的是，这里的技术演进趋势究竟会走向何方，目前还不完全明朗。但可以肯定的是，我们眼下渴望解决的复杂问题实在太多了，根本不可能对每一个问题都不计成本地堆砌无限的计算资源。因此，在所有这些系统工程中，效率（efficiency）这一维度依然显得至关重要。

<details>
<summary>Original English</summary>

**Speaker B**: So, I think, it is a combination of these things: people who know how to watch to these problems and how to solve them to decide, also know how use AI for this, because you come across as very strong verifier, if you own knowledge or you know, What to do? And I too I think we found out from all these swarms agents and the like things, it's that when you direct enough computational capacities on problem, you can enough to explore ways to solve it. But it often happens that what can you do to spend a hundred billions or trillion tokens on something, but if you involve someone who understood on this problem, he can to suggest to the model that what will do unnecessary expense this trillion tokens. I have on mind you, not quite it is clear which ones There are trends here. But I I think that now there are so many problems that we we want to decide, and we we cannot allow just always to direct at them as much as possible computational resources. So the aspect effectiveness in all these things remains extremely important .

</details>

### GPU 算子性能、“光速评估”与能耗边界

**Speaker A**: 那么，是否存在某种基于基础物理定律可以直接推算出的理论极限指标，让我们能够朝着这一物理上限不断逼近？

<details>
<summary>Original English</summary>

**Speaker A**: Is there any theoretically correct the answer that can be just calculate based on physics, and then approach this physical limit?

</details>

**Speaker B**: 是的。不过对于具体的 GPU 算子（kernel）而言，根据任务本身的计算复杂度，精确量化往往并非易事。以最典型的矩阵乘法（GEMM）为例，计算其所谓的“光速”（Speed of Light，即硬件理论极限吞吐与执行上限评估）非常直接。然而这也取决于实际边界条件——比如你的输入数据最初是驻留在 CPU 主存中，还是已经存放在显卡的 DRAM（显存）里，诸如此类。这些硬件拓扑和数据搬运路径都会显著改变基准指标。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. For GPU cores this is not always actually easy to calculate, according to the complexity of the task. For example, for matrix multiplication very easy to calculate this "speed" assessment light", that is extremely possible kernel performance. And this also suggests, you know, maybe that all your data are initially located on the central processor, or, maybe they are in DRAM on video card, etc. It changes these a little indicators. data transfer and everything something else.

</details>

**Speaker A**: 确实是这样。

<details>
<summary>Original English</summary>

**Speaker A**: Yes.

</details>

**Speaker B**: 但我想指出的是，很多现实场景下，你究竟能否真正触及这个理论上限其实并不明确，你应该懂我的意思。理论上限假设了计算与数据传输能够实现完美重叠与隐藏，然而硬件中总会存在某些无法彻底消除的瓶颈。在现实工程中，我们手工或自动生成的许多 GPU 算子甚至远远无法贴近这一极限，二者之间往往存在极为显著的差距。

<details>
<summary>Original English</summary>

**Speaker B**: But I will say that no It is quite clear whether in many cases is it possible at all achieve this theoretical indicator if you You know what I mean. This suggests perfect overlap and data transmission, and, maybe there is some " bottleneck, which impossible to avoid, but often the cores that we we write, even not close approaching this indicator, so that it was somehow significantly.

</details>

**Speaker A**: 那么在优化时，大家真正关心的只有吞吐速度吗？还是说你同样非常在意内存访问——毕竟内存带宽直接决定了速度？另外，你会在乎能耗吗？在我们以往最精彩的一期播客中，Jeff Dean 曾分享过：“坦白讲，我平时一直在追踪微焦耳，或者纳焦耳、皮焦耳级别的能耗消耗。”皮焦耳在特定场景下也是重要考量，你平时会纠结能耗吗？

<details>
<summary>Original English</summary>

**Speaker A**: Yes. And does it matter? just speed? Or worries you too, of course, memory, which does it affect speed? Do you care about energy consumption? One of ours best podcasts was with Jeff for a year Dean, who said: " Actually, I just I am tracking microjoules or, maybe nanojoules, picojoules." Yes, pico, this is optional, pico. Are you concerned about this?

</details>

**Speaker B**: 我个人可能不会关注得这么细，我没有去精确测量过……在底层工程实践中，一切往往最终还是直接折算成执行速度，对吧？大家很少会直接拿着焦耳去算。不过这里存在一个非常关键的微妙区别：我认为必须区分单算子局部上下文中的速度，以及端到端模型任务整体上下文中的速度。正是因为这个考量，我们讨论所谓的“硬件理论极限速度（Speed of Light）”才变得如此关键。因为在评估单算子时，我们通常默认所有张量都已经就绪在 HBM 高带宽显存中；但如果你站在端到端全局视角来审视一个神经网络，为了避免在相邻两层之间产生显存搬运开销，你完全可能会宁愿牺牲第一层算子的绝对执行速度，换取将中间计算数据尽可能驻留在 SRAM 缓存中，以便直接供第二层操作流水消费。如果仅仅将单个算子割裂开来孤立观察，你是根本无法领悟并做出这种全局系统折衷的。

<details>
<summary>Original English</summary>

**Speaker B**: I probably don't, I don't so... But here it all boils down to to speed, right? Nobody counts joules. . However, there are caveats. : I believe that there is speed in in the context of a separate cores and speed in in the context of the broader tasks, for example, models "from A to Z". Because one thing is worth to take into account, and precisely therefore important to discuss what means "speed" light", consists in because for such we always have let's start with what everything is there, for example, in HBM, right? But you can to imagine a whole model "from A to Z". Maybe between the two in layers you want sacrifice speed of the first operations to leave data in cache for the second operation. And these are the things that impossible to fully to comprehend, considering only such nuclei in isolation.

</details>

### 算子融合、巨型算子与编译器的职责

**Speaker A**: 人们通常将这种技术挑战称为算子融合（operator fusion）问题。

<details>
<summary>Original English</summary>

**Speaker A**: And people call it that the problem of merger operations.

</details>

**Speaker B**: 没错，或者称之为构建“巨型算子（megakernels）”。通常情况下，这主要适用于显存带宽受限（memory-bandwidth-bound）的场景。但随之而来的问题是：随着这些神经网络模型不断演进，我们到底是否需要直接去手写构建这类庞大的巨型算子？这真的是我们想要的发展方向吗？嗯，你的看法是什么？

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Or " meganuclei." Usually this is only applies to cases when you limited by bandwidth memory ability. But the question arises: in as these models are improving, or we just need create such " meganuclear"? Is this what What do we want? Ahem. What is your opinion?

</details>

**Speaker A**: 我觉得这极其困难，因为要让模型做到这一点需要庞大的训练数据。而且在我看来，现实中我们至今还没真正见过模型在没有任何现成样例引导的前提下，能够凭空“冷启动”解决如此高难度复杂类别系统任务的成熟案例。

<details>
<summary>Original English</summary>

**Speaker A**: I I think that's very difficult because for This requires data. And it seems to me that I haven't seen it yet real conditions example of how we " loading » ability to decide very difficult class tasks without any examples.

</details>

**Speaker B**: 嗯，我也认为还有另一个原因可以解释为什么直接手写巨型算子可能并非长久之计：在单个独立算子的层面上，其控制流与计算逻辑相对没有那么繁复，而且你能在很大程度上确定算子内部的并行结构模式；然而在跨操作的巨型算子场景下，我更倾向于相信编译器才是更合适的解决方案。例如，面向高级计算图操作的专用深度学习编译器非常有价值，因为从宏观上看，巨型算子本就是由若干基础算子组件良好拼装而成的。尽管在某些特殊前沿领域，你可能会希望尝试一些极其激进乃至特异的算子融合技巧，但就通用情况而言，我认为这些调度工作正是编译器最擅长胜任的。据我了解，已经有专门的公司在这个方向上深耕，他们之前也在 GPU MODE 社区做过几次非常棒的技术分享。

<details>
<summary>Original English</summary>

**Speaker B**: Um, me too I think there is another reason, why can't it be so interesting, is in because at the level a separate nucleus: a) they not so complicated, and b) you to some extent sure that in one not so many cores structures. But in case with megacore i I would rather believe that would be better suited here compiler. For example, some compiler for high-level operations makes sense, because in general I I think meganuclear very good consist of individual parts— individual nuclei. There are certain areas where you, maybe you want make strange mergers and so on, but in general I I think these are cases, with which the compiler, will probably cope, and there is a company that this works, as far as I understand, and she also conducted several reports about GPU mode.

</details>

### GPU MODE 社区与基准评测的学术源流

**Speaker A**: 没错，我也正想把关于 GPU MODE 的话题在这里做个汇总，因为显然我们还有其他重要的技术部分需要展开讨论。我觉得应该向大家郑重推荐一下：你们团队产出了大量极其优秀的技术讲座，全都在 YouTube 上公开发布，大家都可以去跟进学习。而且其中相当一部分核心讲座都是由你亲自主持的。你现在依然……

<details>
<summary>Original English</summary>

**Speaker A**: Yes, I actually want to group all GPU mode discussion here, because, obviously, there is other parts to which we need to move. I think it's worth something. recommend. You spend a lot really good lectures. They are all on YouTube. People can follow. And you lead a significant part of them. You still enough

</details>

**Speaker B**: 我过去经常主持，呃，现在有时也还会参与主持。不过我认为目前主要是 Mark 在负责主持这些活动，Mate 有时也会分担。但无论如何，我强烈向所有人推荐 GPU MODE，这是一个非常宝贵的开源学习资源。里面有极多优秀的从业者毫无保留地分享干货知识，氛围真的不可思议。如果你身处 GPU 编程与底层优化这个圈子，你会发现那里全都是跟你志同道合的受众。

<details>
<summary>Original English</summary>

**Speaker B**: I used to, uh, sometimes I still do it. Uh, me I think it's mostly this. Mark. Mark is the one who usually them conducts. Mate sometimes also. But, uh, yes, I have them. I highly recommend it. It extremely good resource. I think this is just crazy like there are many people there share information . So yes, because if you are there, then you are very, very, you exactly the same audience, you know?

</details>

**Speaker A**: 没错，完全就是这样。这些底层知识并不会出现在普通大众的视野里，而且我们在社区里沉淀并发布了大量高质量的入门与进阶指导材料，在我看来对广大学习者极具实用价值。此外，去年发布的 KernelBench 也产生了极其广泛的影响力。回顾去年的工作，你还希望大家关注哪些目前正在推进的项目？毕竟你一直在这一领域的最前线深耕。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, exactly. This is not will reach the main one, and there there are also many introductory materials, which we have laid out, that, as for me, useful for people. Kernel Bench was quite influential. I just I want to see, well, you know, it was last year. Uh, about what other current Do you want a job? remember what people it is worth paying attention to, because you are obviously involved in this field.

</details>

**Speaker B**: 好的，我可以分享一下背后的背景渊源。我确实深度参与了许多 Benchmark 基准评测的构建工作，或者说在此之前——特别是在进入研究生阶段之前——我就一直在做这方面的事情。这一切始于我在普林斯顿大学的经历，当时我和 SWE-bench 团队共事，比如 Carlos 等人，整个团队都非常出色，我很喜欢与他们合作。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, I might. I will tell you. the background of what I really am involved in a lot benchmarks, or was before, perhaps before my graduate school. It it started because I was at Princeton, I worked there with by the Sweet Bench team. John Carlos is here. They everyone is wonderful. I them I love it.

</details>

**Speaker A**: 很多人可能根本没有意识到，开源社区里有那么多极具影响力的权威 Benchmark，其实全都出自同一个研究小组。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. There is basically this, I I think people don't understand how much benchmarks come from from the same group.

</details>

**Speaker B**: 确实。在普林斯顿，你认识 Shun 吗？

<details>
<summary>Original English</summary>

**Speaker B**: Yes. In Princeton Do you know Shun?

</details>

**Speaker A**: 认识，他之前就作为嘉宾上过我们的播客节目。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Aha. Yes. He was already with us on podcasts.

</details>

**Speaker B**: 他现在正在创办并管理 Cognition 公司。

<details>
<summary>Original English</summary>

**Speaker B**: Now he manages a company 10.

</details>

**Speaker A**: 没错，他如今在业界完全是明星级人物。

<details>
<summary>Original English</summary>

**Speaker A**: Aha. Now he a real star.

</details>

**Speaker B**: 我最初认识他的时候，他还是我导师 Michael Carbin 实验室里的研究员朋友，现在他在 Anthropic 工作，他们之间有很多深度的科研合作。当时在 Carbin 的实验室里最初就两名学生，后来陆陆续续有更多优秀的合作者加入进来。是的，Shun 真的非常卓越。在他毕业离开实验室之前，我甚至都没意识到他在业界会成为如此耀眼的明星。但确实，像你们这样出类拔萃的研究生真的凤毛麟角——可能每年我们才能有幸见到一位从博士论文开题一直到最终成果落地都做到如此严谨、扎实且无懈可击的学者，这样的人才真的并不多见。

<details>
<summary>Original English</summary>

**Speaker B**: I met him, when he was a scientist my boss Michael Tang's friend, who is currently working in Anthropic, they are many cooperated. We there were two students in Karik's laboratories. AND then later others joined in. But yeah, Shinu is awesome. I didn't know he was like that. star, until he left from there. But yes, I mean that there are very few of these graduate students like you, you next, once a year we see someone whose the dissertation was accurate from the start and to the end. There are not that

</details>

<!-- chunk 3/13 -->

### 学术品味、行业脱节与做冷门研究的价值

**嘉宾 (Guest)**: 他们中的许多人都是如此。Shil 是其中之一，还有 Jack Morris 也是。在写这篇文章之前，我们曾聊到过科研品味（research taste）。你知道，有些研究生在职业生涯中极其幸运，他们做的一切事情最终都被证明是高度相关且极其重要的；而另一些人则一无所获。我认为这种情况甚至也适用于工业界实验室的研究人员，只不过研究生往往更加显眼。所以你会看到，有些人确实是纯粹的幸运，还是说这是运气、极高的智商以及其他因素的结合体？

我认为就科研品味而言，它在很大程度上是借助机会培养出来的——至少就我个人的情况而言是这样。我非常庆幸自己在普林斯顿大学的工作经历，以及随后在麻省理工学院（MIT）遇到了我的导师 Omar。他是一位非常出色的导师。不过无论如何我都想说，最成功的研究生或学术界研究成果，往往出现在人们将精力聚焦在大部分工业界根本不予关注的问题上的时候。

<details>
<summary>Original English</summary>

**Guest**: many of them. Shil was one of them, and, you know, Jack Morris also. We talked. before writing about research taste, you know, some it's easy for graduate students incredibly lucky with career, they have everything it turns out, this relevant and important, and in others—nothing. I think this applies to even people in industrial laboratories. Simply graduate students are much more noticeable. Therefore you You see, there are people, who are truly lucky, or is it a mixture of luck, high intelligence and other things. I think regarding research taste, he develops thanks to opportunities, at least in mine case. I really like it. good luck with mine by: work in Princeton, and then meeting with mine scientific supervisor Omar at MIT. He fantastic adviser. I will say it anyway, which are the most successful research postgraduate students or in academic environment appear then, when people focus on problems that most of industry does not pay attention.

</details>

**嘉宾 (Guest)**: 我认为当前的问题在于，许多研究生所做的工作，都是那些看起来对工业界实验室极具吸引力的方向。例如，他们都在针对某个基准测试（benchmark）进行研究。现在这种做法非常流行。而在 2023 年，基准测试完全是另一回事。现在很多人都在研究评测系统、元系统（meta-systems）以及用于执行特定任务的专用工具。如果你仔细想想，某人之所以会投入精力做这些，是因为现有的模型已经具备了非常清晰的目标：大家都在说，“这就是我希望看到的东西”。

我拿关于 RLM（递归语言模型，Recursive Language Model）的论文作为一个例子，因为我认为它的核心想法其实极其简单。我想当它刚发布时，很多人看到之后都会质疑：“做这一切的终极目标到底是什么？这不就是搞几个简单的子智能体（subagents）之类的东西吗，对吧？”但我觉得这种反应反而是个好兆头，因为这恰恰表明人们尚未真正思考它的真实意图与根本目的。

<details>
<summary>Original English</summary>

**Guest**: I think the problem is that many graduate students are working on that looks attractive for industrial laboratories. For example, they are working on something benchmark. Now this very popular. I think , benchmarks in 2023 were completely different history than now. Many people are working on testing systems , meta-systems and specialized tools for performing certain tasks. And if it's good think, reason, why is someone over this works, consists of the presence of a clear goals around models, which we have today : they say, this is what I want see. I will show you how example article about RLM, that is, recursive language model, because I think it's her idea. extremely simple. I think when she came out, there were a lot people who, upon seeing something like that, asked: what the whole purpose of this all? Yes. Why, it's simple some subagents or something like that, right? And I I think that's it. reaction—it's even a good sign, because it becomes it is clear that people still don't think about the real purpose of this.

</details>

### SWE-bench 与具有叙事野心的范式探索

**嘉宾 (Guest)**: 我再举另一个例子——SWE-bench。当 SWE-bench 最初问世时——Omar 很喜欢讲这个故事——当时根本无人问津，根本没有人感兴趣。所有人当时的反应都是：这是一个不可能完成的任务。大家都在说：“我们凭什么要把这种东西当成一个基准测试来看待？”直到 Devin 问世之后，所有人这才恍然大悟般地惊呼：“哇，这才是我们梦寐以求想要攻克的方向！”

我认为事实确实如此，因为你经常会看到各种各样的想法。我最喜欢的例子是 Eric Zelikman 的工作——STaR 以及 Quiet-STaR。当你读那篇论文时，至少当我第一次读到它的时候，我的第一反应是：“这难道不是显而易见、极其自然的想法吗？”或许并不是，我也说不准。我当时心里想的是：“哦，这看起来太直截了当了”，或者就像思维链（Chain of Thought），又或者是 ReAct，大家都会觉得“理所当然本该如此”。但当你真正深思下去时，一个问题就会浮现出来：这些论文的真正价值究竟在哪里？

我认为其价值恰恰在于，它讲述了一个关于“你认为这个领域未来应当是什么模样”的完整叙事。而在学术界，要做到这一点是非常困难的。因为如果你回看所有这些论文——无论是 Quiet-STaR、ReAct、RLM 还是 SWE-bench——它们当中的任何一个都不是 GPT-6 级别的重磅发布，明白吗？它们并不是那种一经推出，所有人都会立刻趋之若鹜地说“天哪，我现在就要把它用起来，这是全世界最棒的东西”的项目。学术环境现在根本无法承担做出工业级工程产物的代价，至少目前是无法做到的。

<details>
<summary>Original English</summary>

**Guest**: I'll give you another one. example—Swe-bench. When Swe-bench appeared, and OIR likes to tell stories this story, nobody knows not interested. All they said that this an impossible task. Like, why are we we have at all to consider it as benchmark? And only after Devin came out, everyone like: "Wow, this is what why do we want to succeed." And I I think that's true, because you often see many ideas; my favorite example— Eric's work Zelikman, STaR and Quiet-STaR. When you read this article, at least when I first saw her read it, I thought: " Isn't it obvious? idea?" Or maybe not, I I don't know. I had on mind: "Oh, it seems very simple", or, let's say a chain thoughts, the same, or ReAct ; Well, of course, yes. But when are you really thinking, The question arises: in why the value of this articles? I think she is. is that she tells a certain story about how do you think it should be this area looks like. AND this is very difficult to do in academic circles, because if you look at all these articles—Quiet-STaR, ReAct, RLM, Swe-bench—none of them they are not a release GPT-6 level, you know? This is not the case, when everyone says: "Oh God, I will do it now. use". It the best thing in the world. similar, academic the environment just doesn't can do this allow, at least now.

</details>

### 学术界研究生的独特不对称优势：下大注

**嘉宾 (Guest)**: 我觉得这背后存在一整套原因，说明了为什么这种现状必须发生改变。但就我个人而言，如果你是一名研究生，你实际上处于一个非常独特的位置，因为在很大程度上你可以自由地去研究任何你想做的东西。如果你不去利用这一得天独厚的优势，反而去随波逐流做那些无人真正在意、或者大家认为显而易见和平庸琐碎的事情——比如有人会说“哦，我之前也考虑过这个，但我只是没做而已”——我认为这样研究最终绝不可能变得引人入胜。

如果你选择留在学术界，你就必须下大赌注（make big bets）。否则的话，我认为你大可以直接去工业界实验室，那里有充沛的算力资源和顶级的人才。何必把自己限制在一个资源匮乏、甚至身边同行寥寥无几的环境中呢？因此，我认为一切的关键都在于下大注。你必须勇敢地做出重大押注，而这其中很多尝试必然会以失败告终，你明白吗？这本身是非常自然、符合客观规律的事情。但我认为，对于研究生而言，这恰恰是你相较于其他工业实验室中任何人所拥有的最大优势——因为你完全不需要应付官僚主义和那些繁文缛节。

<details>
<summary>Original English</summary>

**Guest**: I mean, there are a whole bunch of reasons, why this should change , but, as far as I'm concerned, if you are a graduate student, you are you in unique a position where you can to work on something whatever, mostly. If you don't use this opportunity and working on things, who don't care about anyone are interested in, or which people think something trivial, on like, "Oh, I was thinking about this, but I don't I just I think that in result research never will not be like that interesting because you you have to do big things rates if stay in academy, because otherwise, I I think just go to industrial a laboratory where there is a lot of resources and talents. Why to limit oneself in industries where you have little resources and not even so many people around, and I think that it all comes down to big bets. Ahem, you just have to do big bets, and many of them will fail, Do you understand? It seems like this just...this...this naturally. But I think what is this, how about for graduate student, this is yours biggest advantage before anyone else in another laboratory, because you don't need to to deal with bureaucracy and everything to others.

</details>

**主持人 (Host)**: 确实如此。没错。我曾把这个问题抛给过许多人，他们通常只是敷衍应付、轻描淡写地一带而过。因此我非常赞赏你能够给出如此富有深度的思考与回答。他们说这不公平，但这其实就是你所拥有的“不公平优势”（unfair advantage），因为事实上除此以外的其他所有客观条件都在对你形成制约。

<details>
<summary>Original English</summary>

**Host**: Rightly. Yes. I asked this question. to many people, and usually they just are brushed aside. So I I appreciate what you give. so thoughtful The answer, they say, is no, This is your dishonesty. advantage, because everything another, in fact, opposed you.

</details>

### 从 JEV 看语言模型的范式突破与设计空间

**嘉宾 (Guest)**: 是的，完全正确。坦白讲，我想拿 JEV（JEB）作为一个案例，尽管它并不是一个纯学术性质的项目。之所以想提及它，是因为它所经历的舆论过程与 RLM 以及许多其他前沿研究如出一辙：当某些事物在某种程度上被过度追捧、引发了过度的炒作狂潮时，随后人们就会反过来苛责：“为什么这东西会被吹得神乎其神？这不就是显而易见的简单东西吗？根本毫无意义。”

在 JEV 发布时，我也看到了完全一样的现象。因为在我看来，那次发布……我明白其中的缘由，无论是学术界还是非学术团队，人们都不得不做品牌营销、不得不去推广自己的研究成果，这一点我很理解。但是，外界当时充斥着大量言论，声称“JEV 所做的事情不过是我们多年以前就已经掌握的知识”。我认为这种观点完全忽略了核心要点——忽略了为什么这样一个系统具有如此重大的启发性与研究价值。

它绝不是我们在机器学习入门课程里随手搭建的那种简单愚蠢的 MLP（多层感知机）分类器。我认为 JEV 真正引人入胜的核心在于，它打破了传统惯性思维并提出了根本性的质疑：现存的语言模型形态就一定是唯一正确的吗？在我们目前习以为常的表征形态下，除了“文本到文本”（text-to-text）的自回归范式之外，我们是否可以探索全新的设计空间（design space）？

<details>
<summary>Original English</summary>

**Guest**: Yes. Yes. That's right. AND so, honestly, I I'll give Jeb as an example, because it's not...it's not academic project. I I want to remember this, because this also happened with RLM and many others robots when things become overvalued , to a certain extent, something gets excessive hype and then people they say: "Why is this so?" overrated?" as if it trivial, this pointless. And I saw the same with Jev, because I it seems that the release was like this...I have to mind, there is this whole story about academics, or they not an academic group, but people have to engage in branding and somehow promote your research, so I understand. But I think that there was a lot talk about what Jev— this is something we know for years, and I believe that this misses the point, why is there such a system so interesting. Why is it not easy? some stupid MLP- the classifier that we did, you know, more in introductory courses with machine learning or something like that. I think What's interesting about Jev is that what he violates question: are they correct language models? In that in the form in which they exist, can we consider another design space , except for "text-to-text" "?

</details>

**嘉宾 (Guest)**: 他们的实际逻辑是：“我打算直接借用语言模型的基础底座；我深知这个预训练底座中蕴含着海量关于语言的深层知识，但我准备去彻底改变模型的输出空间（output space），以此来为你提供一种全新的权衡折中（trade-off）：如果你对当前任务拥有任何先验知识，那么我就可以实现极快速度的推理。”举个例子，假设我只需要完成一个二元分类任务，难道我还要去调用完整的语言模型做自回归生成，并为此多付出 400 倍的算力与经济成本吗？不，那样做简直荒谬透顶，对吧？

我认为在很长一段时间里，由于顶级实验室是唯一掌握主导权的存在，你永远只能接触和使用像 GPT、GPT-4 或者类似的最前沿基座模型。正是因为这种垄断与习惯，人们彻底固化了一种观念，认为所谓的“语言模型”本质上就必须是一个自回归解码器（autoregressive decoder），大家都无条件接受了这一定义。当我提出 RLM 时，面临的遭遇也是一模一样的。我收到的一个极其高频的批评就是：“这根本就不是语言模型”；或者“当我第一眼看到这个名字时，我以为你们发明了一种全新的网络架构，但仔细一看发现并不是”。

而我对这种质疑的回答是：语言模型的本质只是对语言进行建模与表征，它根本不必非得拘泥于 Transformer 解码器这一种固化形态，明白吗？而 JEV 之所以极其有趣，就在于它为我们提供了一个全新的调优参数维度：什么是它的源空间与输出空间，以及这种重塑如何从根本上影响推理延迟？我认为我们实际上可以开始尝试去灵活调用语言模型自身的各个不同组件与内部子结构。

这背后体现的是同一种思维脉络。尽管围绕它曾有过巨大的争议与批评，有人轻蔑地说“这想法太蠢了，到底谁会需要这种东西？”但事实上，这正是那种虽然构思直白简洁、却能撬动一整套崭新科学问题的绝佳思路！特别是如果你是一名研究生，这些问题正是你极度渴望去寻找答案的。因为关于 JEV，我们其实还有极其广泛的盲区未曾探明。比如，在循环 Transformer（recurrent / cyclical transformers）的脉络下，我们究竟能走多远？如果仅对模型的一部分结构进行循环调用，效果又会如何？再比如，如果我们通过路由器（router）将数据定向分流到模型的不同组件中，又会带来怎样的变化？我们是否能够复现在评估测试 Harness 中所做的那些事情？

<details>
<summary>Original English</summary>

**Guest**: They are actually they say: "I I will use this. the basis of language models; I know that it contains a lot information about the language, but I'm going change output model space to to offer you compromise: I will to perform very quick conclusion, if you have any specific a priori knowledge about this task." Let's say I need to do binary only classification, will I I ask for my language model to do this and pay 400 times more? No, that's it. It's ridiculous, right? And I I think that during for a long time, because laboratories are the only places, who have control, you will never be use nothing other than GPT, GP6 or Fable, because it is the best models. But because of this people are used to it to the idea that language model—it's simple autoregressive decoder. We are it accepted. And I think, when did RLM appear, it was the same. One of comments, very frequent criticism that I received, was like this : "This is not a language model" or "When I look on this, I thought it was new architecture, but "Actually, no." And mine The answer to this is: well, the language model is just modeling languages; she is not must be this transformer decoder, you know? And JEB is very interesting in that, that now we have a new one parameter for settings: what is it source space and how this affects delay in conclusion? AND I think we we can actually begin use different parts of itself language model. It similar idea, around which was a lot attention, they say, this a silly idea, Why would anyone need this? necessary? But this a simple idea that opens a whole series new questions to which, I think especially if you are a graduate student, you you want to answer, because I think that we, for example, many What we don't know about Jev. We don't know how. far we can come in with this, uh, for cyclical transformers. We we also don't know how far we can do it to start: what if cyclically use only part of the model? Hmm, what , if directed data, for example, through the router to different parts models? Is it possible? to reproduce what you do in a harness (

</details>

<!-- chunk 4/13 -->

### 非自回归架构与小模型的计算分发潜力

**Speaker A**: 无论是在评测框架（evaluation harness）层面，还是在模型内部，究竟什么是可能的？我们是否能在架构绑定与模型选择之间进行权衡和组合？在我看来，正是这类新型系统向我们揭示了这些问题，这实在令人着迷。

特别是当我看到 Jev 时，我立刻意识到：这对 RLM（强化学习模型 / 循环语言模型）而言极其有用。我认为这非常符合逻辑，因为在 RLM、智能体集群（swarms）或类似系统中，最大的瓶颈就在于高延迟（tardiness）。当你不断向大型语言模型发起高频调用时，你无法合理地分配计算负载。因为系统内部可能存在某些非常微小琐碎的子任务，你原本只想派发给一个极其轻量的简单模型，但你做不到——你现有的语言模型全都是那种庞大笨重的庞然大物。

因此我感到非常兴奋。我认为我们将开始看到除了常规、标准的前沿大模型之外，涌现出更多全新类型的架构与模型。而借助这些新型模型，我们可以做出更多折中与权衡，从而实现远超以往的各种应用场景。

<details>
<summary>Original English</summary>

**Speaker A**: ...harness), inside the models? What is possible? Can we combine between choices, bindings, and architecture model selection? These are all questions that, in my opinion, are opening up thanks to such systems. And this is actually very fascinating.

Jev, in particular—when I saw it, I thought: this is really, very useful for RLM. I think it's logical, because the biggest bottleneck in RLM, swarms, or similar systems is their latency and tardiness. When you are constantly making numerous calls to language models, you cannot properly distribute computation. There might be something trivial that you want to entrust to a simple model, but you can't, because your language model is just this bulky, monolithic thing, you know?

So I am very excited. I think we will begin to see the emergence of new types of models, alongside the ordinary standard frontier models. And with these new models, compromises can be made to achieve so many things.

</details>

**Speaker A**: 顺便我还想提一下 Thinky 以及他们的交互模型机制。

<details>
<summary>Original English</summary>

**Speaker A**: Ahem. I also want to note Thinky with their model interactions.

</details>

**Speaker B**: 对，没错，那确实是另一个绝佳的案例。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Yes. Another great example.

</details>

### 新兴实验室与前沿巨头的差异化生存策略

**Speaker A**: 是的。从本质上讲，这是一种跳出“序列到序列”（sequence-to-sequence）纯 Decoder 架构范式、去尝试全新路径的探索。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. So, essentially, an attempt to go beyond the paradigms of "sequence-in-sequence" decoder-only architectures and just do something else.

</details>

**Speaker B**: 确实。我的意思是，如果你试图正面竞争，没有任何人能与拥有海量算力资源、专攻自回归 Decoder 的顶尖实验室抗衡。即使是 Thinky 也做不到——虽然他们可能是极少数有潜力尝试的团队之一，但在这条老路上硬拼根本行不通。我对 Thinky 了解不算极深，也不想妄加断言，但如果他们的战略只是简单复制 OpenAI 或 Anthropic，那将是一场灾难。

因为从资源优势的角度来看，你必须思考：你的独特优势到底在哪里？如果你去走前沿巨头走过的老路——虽然我相信他们不会这么做——但如果你真选了那条路，你本质上就是在拼自己无法占据绝对优势的要素，也就是数据和算力规模。在这些维度上，小团队显然不可能赢过顶尖实验室。

所以，作为一家新兴实验室（neo-laboratory）——虽然我不知道大家是否把他们定义为新兴实验室，但我认为他们确实在榜单上，并且推出了 Inkling，因而备受关注——除了 OpenAI、Anthropic，以及 Meta 和 Google DeepMind 之外的任何团队，都必须另辟蹊径。虽然这是残酷的现实，但我认为这也是一件好事。我很高兴看到这种差异化探索正在发生，这些公司会继续推进下去，因为一旦他们挖掘出真正有趣的技术路线，就能为新玩家铺平道路。

而在前沿实验室内部，我严重怀疑这类非主流探索很难真正发生。因为他们何必去冒这个险呢？当旧的筹码和范式已经行之有效时，为什么要承担巨大风险、将宝贵的算力倾注在未经证实的新赌注上？正因如此，市场上才会孕育出这么多新兴实验室，不是吗？

在次级技术路线上，你拿不到那种天文数字的算力，于是你会说：“行，那我就走另一条路。”而潜在成功的典型代表就是像 Jev 这样的成果——成本直接降低了 100 倍。也许它不是传统意义上的通用语言模型，但在特定场景下，它带来了截然不同的可能性。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. I mean that if you try to compete directly, no one can compete with an advanced laboratory creating autoregressive decoders with that sheer amount of computing resources. Even Thinky can't—well, you know, maybe they are one of the few who could, but realistically you can't win in that regard.

I don't know too much about Thinky and I don't want to make assumptions, but if their strategy were simply copying OpenAI or Anthropic, that would be a terrible strategy. Because, well, they just don't have that scale. It's worth thinking about this from the perspective of advantage: Do you have any structural advantage? If you use the exact same approach—which I'm sure they won't, but if someone chooses that same path—you are essentially competing in areas you cannot control, namely data scale and compute, and in those areas they obviously cannot compete with frontier labs.

So yes, it makes total sense that if you are a neo-laboratory... although I don't know whether to classify them as a neo-laboratory, but they are certainly on the radar. They released Inkling, so they are taken into account. Anyone other than OpenAI, Anthropic, and possibly Meta and Google DeepMind simply has to do something different. It's a harsh reality, but I think it's healthy. I am very glad that this dynamic works, and these companies will continue doing this because it paves the way for new players if they find something genuinely interesting.

Because I have serious doubts that this kind of exploration is happening at Frontier Labs—why would they need to? Why take the risk and allocate massive compute to speculative bets when the established recipe is already paying off? And that dynamic is precisely what spawns so many neo-laboratories, right? If you are on a secondary bet and lack brute-force compute, you pivot: "Okay, I'll explore elsewhere." And your blueprint for potential success is something like Jev, which is 100 times cheaper. Maybe it's a different form factor than a standard language model, but in this domain, it represents something distinctly novel.

</details>

### Jev 的技术猜想、训练优化与置信度校准

**Speaker A**: 没错，完全同意。

那么关于 Jev 的本质究竟是什么，虽然目前还没有定论，但我有一些推测。我看到有些人讨论说：“噢，这看起来有点像扩散模型（diffusion）。”但在我看来，它更像是一种并行解码（parallel decoding）机制。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Yes. Yes. Yes. Um... So, no definitive assumptions yet about what Jev really is, but I think I have my guesses as to what it could be. I saw some people saying, "Oh, that's something like diffusion." Um, personally, I think it is parallel decoding.

</details>

**Speaker B**: 对，并行解码。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, parallel decoding.

</details>

**Speaker A**: 说实话，不管它的底层具体实现到底是什么——因为我也看到了社区对它的开源复现尝试——真正让我感到惊艳的，是我至今无法完全确定的两点：他们的优化目标到底是什么？以及他们究竟是如何完成模型训练的？

这也让我想到了 RLM。我们最初也认为：好吧，RLM 本身是一个非常直观简单的想法，一旦论文发表，所有人都能直接套用。但 RLM 的核心壁垒在于：你是否有能力正确地训练整个系统，以及能否围绕它构建出足够优秀的外围架构，使其输出真正达到极高质量。这正是目前我全力攻坚的方向。

而他们找到了一种成功训练该系统的方法，这绝非易事，是一项高度复杂的非平凡任务。实际上，我甚至完全不知道他们是怎么做到的。我看到网上有对比评测，有人声称他们使用了 Qwen 或者是对 Qwen 进行了重训练微调。但任何现成的开源 Qwen 表现都远逊于它，因为他们为训练专门设计的一整套机制，效果显然极为出色。这真的非常令人振奋。

另外还有一个关键要素是“模型校准”（calibration）。这是一个相当冷门、甚至在外界极少被深入讨论和理解的领域。我们之前曾与 Hugging Face 负责评测的前主管 Clémentine Fourrier 深入探讨过这个话题。核心问题在于：当前的语言模型被训练和调优的目标仅仅是输出“概率最高的下一个 Token”，但如果你直接反问模型：“你对这个答案究竟有多大把握？”，它往往会对你撒谎。因为它只会机械地吐出最可能的结果，而不会真正进行概率校准，告诉你：“不，我其实只有 50% 的把握，或者只有 20% 的把握。”

为了实现这种校准，我认为通过合成数据来训练是相对直观可行的：因为你能掌握真实标签（ground truth），你可以合成生成海量候选答案，让模型对其进行分类判定，然后将其置信度与真实数据进行比对。如果让我来做逆向工程，这会是我的切入点。因为我认为校准是一项被严重低估的能力——很多人仅仅把模型当成超高速分类器来使用，却完全没有利用其背后的概率分布和置信度校准分数。

很多人在这个认知上依然存在偏差：正如我强调的，当你直接询问一个未校准的模型它的确定程度时，它可能随口编造一个“43%”的数字；但这与经过严谨校准、在统计上具备实际置信意义的概率分类之间，存在着天壤之别。

<details>
<summary>Original English</summary>

**Speaker A**: Fair to say, regardless of what it really is under the hood—and I have seen open replications of it—what genuinely fascinates me about what they built is something I'm still not entirely certain of: What was their exact optimization objective, and how did they train it?

And I think this parallels RLM, where we also initially thought: okay, RLM is conceptually a very straightforward idea. Once the paper is out, anyone can use it. But the real value and moat of RLM is whether you can properly train the system, and whether you can build the surrounding architecture to make it consistently high quality. That is what I'm actively working on right now. But whatever method they found to train their system, it is clearly a non-trivial feat. Honestly, I don't even know how they achieved it.

I saw comparisons online where some claimed they just took Qwen or retrained it. But any vanilla open-source Qwen performs noticeably worse, which proves that whatever custom training pipeline they created works exceptionally well. And that is truly exciting.

There is also an element of calibration, which is quite a rare topic that, in my experience, many people don't fully understand or recognize. We discussed this with Clémentine Fourrier from Hugging Face, who previously led evaluation there. The issue is that modern models are tuned strictly to generate the most probable next token; but they will effectively lie to you if you ask them: "How confident are you?" They will simply output the most plausible-sounding answer rather than being genuinely calibrated—such as admitting: "No, I am only 50% sure, or 20% sure."

I would say it is fairly feasible to generate synthetic data for this, because you have ground-truth access: you can synthetically generate heaps of candidate answers, have the model classify them, and compare those calibration metrics against real ground truth. That would be my approach to reverse-engineering it. Calibration is vastly underrated; people currently just treat these models as ultra-fast classifiers without leveraging true probabilistic calibration scores.

People still misunderstand this: to reiterate, if you ask an uncalibrated model how confident it is, it might arbitrarily claim 43%. The crucial difference is having justified, well-calibrated probabilistic classification, right?

</details>

### 低延迟任务、游戏基准与极简控制接口

**Speaker B**: 没错，确实如此。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Yes.

</details>

**Speaker A**: 我非常期待社区接下来会用这类模型打造出什么应用。它能否包揽并解决所有问题？当然不可能。但它完美解决了一整类我们过往极难应对的问题——那就是对低延迟要求极高的“低风险容错任务”（low-stakes, latency-sensitive tasks）。

正因如此，我非常喜欢他们在游戏场景上的演示案例。

<details>
<summary>Original English</summary>

**Speaker A**: I am genuinely looking forward to what people will build with this model. Will it solve every single problem? Of course not. But I think it addresses a specific class of problems where we traditionally struggled—namely low-stakes, latency-critical tasks. That's why I really love the examples with games.

</details>

**Speaker B**: 对，比如运行《毁灭战士》（Doom）的那个示例，非常棒。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, the Doom example. That's great.

</details>

**Speaker A**: 我自己其实专门构建过一个让语言模型玩电子游戏的基准评测集（benchmark）。我一直对“能否构建出一个能自主游玩全新游戏及类似任务的通用智能系统”这个问题深深着迷。因此我觉得他们能够找到这样一种独特方式——将语言理解与极高推理速度融合在一个超快模型中——真的太酷了。

顺便借着这个话题，关于这个领域你还有什么特别想要强调的观察吗？

<details>
<summary>Original English</summary>

**Speaker A**: Exactly. I actually have a benchmark dedicated to language models playing video games. I've always been fascinated by whether we can create an intelligent system capable of playing new games and handling interactive environments like that. So I think it's remarkably cool that they found a unique way to combine language understanding in such an exceptionally fast model.

While we're on this topic, is there anything specific you want to highlight?

</details>

**Speaker B**: 噢，是的。其实无论如何，你已经为许多模型做过了这类基准评测。不过我觉得当时的那些评测数据现在已经有些过时了，如今不同模型之间的差距非常巨大。我看到社区里不少热心技术爱好者正在将最新的模型部署到这些游戏环境中运行，这非常酷。

我认为这个基准评测的核心出发点，本质上是在严格的实时延迟限制下，检验视觉语言模型（VLM）是否已经成熟到足以整合进动态游戏控制流程中。因为这一切实际上是在“Claude Plays Pokémon”（Claude 玩宝可梦）出现后立刻兴起的。虽然那是大约两年前的事了——以 AI 的演进速度来看，两年前简直就像古代一样遥远。但我认为这个测试集的设计非常出色的一点在于，它所涵盖的游戏类型非常丰富多样，而且其中绝大多数游戏都是大家耳熟能详或曾经见过的。

我也看到了那个在《毁灭战士》里操作的 Java/Jev 演示。老实说，我认为他们大概率只在一些非常基础的关卡上进行了跑通测试；坦白讲，大多数模型目前依然无法应付更复杂的关卡，我不认为现有模型能真正有意义地通关这些游戏。不过确实也有一些例外，比如我记得之前看到 Google Project Astra 能够玩通《星之卡比》（Kirby）。

而且针对这个基准评测，我们特意设计了一套极其极简的交互接口与控制外壳（headset / harness）。稍后我还会专门回到这个接口设计的话题，因为我认为深入探讨这样一套极简接口的价值非常值得：为什么我们需要为模型设计专门的外壳接口？

但总的来说，我非常期待很快能看到新一代模型打破现有的所有记录。回想当年老版的 Claude Plays Pokémon 还在艰难读取运行状态的情景，如今的发展确实令人感慨。

<details>
<summary>Original English</summary>

**Speaker B**: Oh, yes. I mean, you built that benchmark across many models anyway. Hmm, I think those earlier numbers are already quite outdated now. Different models behave very differently today. And I've seen enthusiasts running newer models across these games, which is really cool.

I think the overarching rationale behind this benchmark was to evaluate whether visual language models are sufficiently capable of being integrated into real-time games given strict latency constraints. Because this entire trend basically kicked off right after "Claude Plays Pokémon" emerged. Hmm, that was roughly two years ago, which in modern AI terms feels like ancient history. But within this task suite, what makes it really cool is the diversity of game genres. Moreover, most of these are titles that people recognize or have encountered before.

I saw the demo playing Doom. To be frank, I suspect they only tested on very basic levels; honestly speaking, most models still struggle, and I don't think any model can meaningfully beat these full games yet. Though there are isolated successes—I think I saw Astra successfully complete a Kirby game.

For this benchmark, we intentionally designed a very minimalist control headset and harness. I will circle back to this headset design theme later, because I think it's well worth discussing the architectural value of such an interface: Why is an interface harness even necessary for the model in the first place? But in general, I sincerely hope to see new models shattering all these benchmarks very soon. It's fascinating to remember how the old Claude Plays Pokémon setup originally read operational status...

</details>

<!-- chunk 5/13 -->

### 对话衔接与话题转换

**Speaker A**: ……记忆，并看到什么——你可以踩在哪些地砖上，哪些不能踩。我们很久以前和他们录过播客。

<details>
<summary>Original English</summary>

**Speaker A**: ...memory and saw what—you can walk on tiles, and which ones are not. We recorded with them podcast a long time ago.

</details>

**Speaker B**: 明白了，明白了。是的，这很类似。之前杰夫（Jeff）没有视觉能力，因此必须向他提交游戏状态，一切都截然不同。

<details>
<summary>Original English</summary>

**Speaker B**: Got it. Got it. Yes. Yes, it's similar. Before Jeff didn't have sight, therefore have to submit him the game state and everything is so different.

</details>

**Speaker A**: 让我们直接切入评测脚手架（harnesses）的主题，因为你的设想打破了常规：评测脚手架、语言模型、复合泛化（composite generalization）。这读起来挺晦涩的，能解释一下吗？

<details>
<summary>Original English</summary>

**Speaker A**: Let's go straight to headset [harness] themes, because you are here violated. Headsets [Harnesses], language models, composite generalization. It's hard to read, explain.

</details>

### 对现有脚手架同质化的反思

**Speaker B**: 好的，没问题。我对人们目前看待脚手架/框架（harnesses/frames）的方式感到有些不满。因为大家总在说：“噢，我喜欢 Claude Code，我喜欢 Codex，我喜欢 Pi，不，我更喜欢 Prime Agent。”坦白讲，我认为它们本质上全都是一回事。在这些框架的设计方案或者设计选型上，绝大多数都是完全相同的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. OK. OK. So, I'm a little dissatisfied with how people perceive headsets [harnesses]. Because they say, "Oh, I love Cloud Code [Claude Code], I love Codex, I love Pi, no, I love Prime Agent." Honestly, I think they all are the same. Majority design solutions, or, say, choice design regarding these frames [harnesses], identical.

</details>

**Speaker B**: 也许 Prime Agent 稍微有些不同，因为它本质上是 RLM（递归语言模型，Recursive Language Models），但总体而言，我认为我们在框架设计上本可以发挥大得多的创造力。我的意思是，如果你从框架究竟在为模型做什么这个视角来看——从根本上说，当你尝试解决问题并希望使用语言模型在困难任务上取得非常优异的性能时，我们发现：仅靠预测下一个词元（next-token prediction），对于完成许多此类任务而言是一种极其不便的形式。

<details>
<summary>Original English</summary>

**Speaker B**: Maybe Prime Agent is a little different because it is, essentially RLM, but overall, I think we can be much more creative with frames [harnesses]. Meaning that if look at this from prospects of what it is the frame that makes for the model, then, according to essentially, when you trying solve the problem and want to use language model for very good performance a difficult task. We found that prognostication next token—this is very, very inconvenient form for fulfillment of many such tasks.

</details>

**Speaker B**: 就比如以 SWE-bench 为例。当你在代码库中导航时，你能想象如何仅凭单次语言模型调用就能完成这一切吗？单纯对它说一句“修复这段代码”或者“在代码库中帮我解开这个查询”，这是根本不可能的。因此，我们必须依赖框架来帮助完成这些操作。

<details>
<summary>Original English</summary>

**Speaker B**: Here, for example, let's take Webbench [SWE-bench]. When you navigate by codebase, can you understand how to do all this with the help of one call language model? On kind of simple say "fix the code" or "untie my query in this codebase." No. Therefore we rely on frame [harness], which helps you do such things.

</details>

### 脚手架的本质与模型的训练范式

**Speaker B**: 在我看来，框架本质上是一套非常明确的程序规则，规定了你希望语言模型如何去适配并解决问题。我之所以想到这一点，是因为当我们思考框架的作用时，应该严肃审视：框架到底提供了哪些机制来让语言模型解决该问题？我们是否真的可以直接拥有一个自主完成这些行为的模型？

<details>
<summary>Original English</summary>

**Speaker B**: And, as for I wonder what frame [harness]—it's very categorical program about how you want the language model adapted to problem. I remember about this, because when we are thinking about what makes a frame, we should be taken seriously to think about it, what kind of elections [mechanisms/choices] are there frame allows language model to solve this problem, and can I really just have a model who does it herself?

</details>

**Speaker B**: 如果现在退一步看循环 Transformer（Recurrent/Cyclical Transformers）的出现，我认为最有意思的地方在于：你完全可以通过同样的方式让模型自身循环起来，从而模拟出使用框架的效果，对吧？你只需让模型构成闭环。有人可能会反驳说：“噢，但这并不是同一层面的解码机制”，因此存在细微差异；但总体上，出于某些原因，我们似乎永远被困在同一种固定的模型架构选择中，背后固然有很多理由。

<details>
<summary>Original English</summary>

**Speaker B**: Because the frame, if to think about now, when did they appear cyclical Transformers, I think, the most interesting thing about this what is possible to model cyclic transformer certain in the same way and for using a frame, truth? You just loop the model. Now you can say: "Oh, I don't decode," so this is a little different, but in general we, from some reasons, forever stuck on one and for the same choice architecture model, and there are many arguments why.

</details>

**Speaker B**: 但显而易见的是，我们现在训练模型时都是围绕着框架的部署流程展开的。这就带来了一种非常别扭的基于框架的训练路径：我们训练语言模型在特定框架内部行动；但如今面对长程、甚至是多智能体的部署，采用的都是极其繁琐、如同打补丁般的 hack 手段。

<details>
<summary>Original English</summary>

**Speaker B**: But, obviously, we are training now models around deployment of frameworks, and that's why there is this very inconvenient way learning based on frames, which is that we teach language model to act within frame; but now it is really long, perhaps, multi-agent deployment, and there are very inconvenient, "hacker-like" ways to do it.

</details>

**Speaker B**: 所以这篇博客文章探讨的核心，就是理解当前现状的一个视角：将框架视作辅助模型解决具体任务的脚手架。不同的设计方案能否承担起比单纯提供工具列表更繁重、更深入的职责？这关乎你如何审视自己的代码库基础。

<details>
<summary>Original English</summary>

**Speaker B**: So this blog tells about what one of the ways to understand what is here is happening, it is consider the frame as aid models in solution specific task. Can different design options obligation to do something a little heavier than just giving list of tools, which ones will help you? Here's how to view it your codebase.

</details>

### RLM 理念的萌芽与任务结构的一致性

**Speaker B**: 撰写这篇博客的想法最初是与 RLM 概念一同萌生的，只是我们当时还没有将其完全形式化。我认为这确实切中了本质。围绕 RLM 还有很多其他想法，我们后续会逐步公开，但它们从最开始就存在了。这一切都关乎架构设计决策。而在 RLM 的研发中，令我欣慰的是我们经历过大量抽象层次的迭代与版本演进，最终证明 RLM 是最合适的形式。这背后有诸多合理的原因，目前尚未全部公开，不过后续大家自然会看到。

<details>
<summary>Original English</summary>

**Speaker B**: So the idea of this blog arose together with the RLM concept. We just didn't formalize it that's right. And I think, what is it really truth. There are many other ideas regarding RLM, which we later let's imagine, but they were there from the very beginning. I mean, what is that all about design solutions, and I like it in RLM what was a lot iterations and versions various abstractions, which I wanted implement, and eventually RLM turned out to be the most appropriate. But there is many reasons why that's right, which are not yet are public. Well, I mean, you yourself will see.

</details>

**Speaker B**: 在这个示例中，我们在 RLM 中观察到的关键现象之一是：如果你充分卸载（offload）上下文负荷，并让模型在此上下文基础上去编写代码，就会展现出一种非常奇特却极其有用的特性——当模型在训练过程中掌握了如何解决某一类问题时，事实证明，对于许多表面看似截然不同的任务，其底层的求解逻辑其实是高度相似的。甚至在那些你直觉上根本看不出相似性的任务之间也是如此。

<details>
<summary>Original English</summary>

**Speaker B**: So, in this example one of things that we see in RLM, is that if you are enough unload the context and ask for the model write code on based on this context, you will get a very strange, but useful property: when model during learning understands how solve the problem, it turns out that solution for many the tasks are very similar. For such tasks, where you don't even it is obvious that these the solutions are similar.

</details>

**Speaker B**: 例如，我们有一项搜索任务和一项聚合任务，它们的请求格式完全不同，任务类型也大相径庭。当你在两项任务上训练普通的语言模型时，它们的学习轨迹看起来差异极大。因此，当你依赖于 Pi 或 Claude Code 等现有方案时——这正是博客中探讨的现象，并且我们有明确的数据结果——你会发现这些常规脚手架把这两类问题区分得过于孤立，尽管两者的求解逻辑本质是一样的。

<details>
<summary>Original English</summary>

**Speaker B**: So, in this example we have there is a search task and aggregation tasks, and they have very different requests. Task types just completely different. And when you train ordinary language model on these two tasks, learning trajectories they look very different. So, when you rely on, let's say, on using pi or cloud code or something like that, what's wrong with this? blog, but we have these results. You will see that these straps [scaffolds/harnesses] are too tight distinguish these problems, although solution for them are the same.

</details>

### 子智能体分解与高维泛化能力

**Speaker B**: 我们在训练 RLM 时发现的一个事实是：模型会将这些不同问题视为同一类问题。之所以它能看透这种一致性，是因为具体的差异被下放给了子智能体（subagent）去处理——子智能体面对的是不同但更简单的局部子任务，只要保证子智能体具备足够的智能来应对即可；而在总体的基本策略层面上，两者的结构最终完全一致。因此，当你在左侧的任务上完成训练后，模型能够立刻泛化并直接解决右侧的任务。

<details>
<summary>Original English</summary>

**Speaker B**: So one the thing we discover when teaching RLM, is that the model sees these problems as the same. And the reason why she sees these problems as are the same, is because the subagent sees different problems, but the subagent decides easier subtask. So you are sure that he is enough smart, so that deal with it. But for basic overall strategy they eventually they look the same. So, when you training, for example, on the left task, the model can immediately resolve the right task.

</details>

**Speaker B**: 如果你查看我们的实验图表，就会注意到一个现象：当你仅仅用朴素方式在这些任务上训练 RLM 时，它自然而然就学会了泛化能力。例如泛化到更长步长或规模的任务上，因为底层策略根本未变，你所调整的仅仅是某个长度参数。而且这种泛化不仅限于不同长度的任务，在本质完全不同的领域间同样成立，比如数学任务与写作任务之间，其高层次的目标决策逻辑依然是同一套。当你在其中一个任务上训练 RLM，它就会将这一行为策略迁移并传播到另一个任务上，这里面没有任何玄学。

<details>
<summary>Original English</summary>

**Speaker B**: Therefore, if you look at our schedules [charts], then notice one thing: when you are just naive train your RLM on these tasks, she naturally is studying generalize, for example, for longer tasks, because strategy in basically the same. You just change a certain parameter length. And this actually too regarding tasks, which are different. And it's not just about differences in length. These are completely different tasks, for example, mathematical vs. writing tasks, but solution, that is, the goal decision level, there is the same. So when you train RLM on one of them, she propagates this behavior to another. And there is none here no magic.

</details>

**Speaker B**: 我想强调的重点就在这里。

**Speaker A**: 你会如何用语言来概括它们到底学到了什么？依你的意思，你们是在较短的任务上进行训练，而它们却能泛化到比训练任务长 8 到 30 倍的任务上。它们到底是在学习解决特定类型的问题，还是学到了某种更根本的东西？

<details>
<summary>Original English</summary>

**Speaker B**: I think maybe that's what why do I want emphasize:

**Speaker A**: How would you described in words that what are they learning? I think what you're saying here is, what do you train for short tasks. They generalize this for the task at 8:30 [8 to 30] times longer. They learn to solve these types of problems, or which is the main thing, what are they really are they studying?

</details>

### 递归归纳：从算法竞赛到 GPU 优化

**Speaker B**: 是的，它们学会在特定长度尺度上解决这些类型的问题，而事实证明，一旦你提取出它们所习得的策略，该策略可以直接迁移并泛化到大得多的规模上，就仿佛这原本就是同一套固定程序的自我延展。这令人极为振奋。这意味着，当面对训练模型所依赖的数据集或环境时：首先，你可以在数量较少的环境中开展训练，并泛化到远超现有模型通过朴素训练所能达到的广泛范围；其次，你依然可以充分利用手头拥有的全部数据。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, they are learning solve these types problems of a certain kind length, and it turns out that when you take this learned them strategy, it directly transferred to greater length. As if this is actually one and the same the program itself. And this very exciting, so what does this mean: when you have a data corpus or environments, on whom you train model, hope is that, according to first, you can to train on a smaller scale number of environments and generalize to a greater number than they can do it existing models through naive training. But, secondly, you all want the same thing use all the data you have.

</details>

**Speaker B**: 因此，当我们在这些任务上进行训练时，我们期待这种能力能推广到更广泛的问题类别。而在 RLM 或者任何递归调用的系统语境下，之所以更具吸引力，是因为这种论证具有归纳递推的性质（acts inductively）。

<details>
<summary>Original English</summary>

**Speaker B**: So when you train on these tasks, we hope so extends to a broader class of problems, and why is this even more so fascinating, at least in the context of RLM or any recursively caused by the system, is that this argument acts inductively.

</details>

**Speaker B**: 举个具体的例子：我之前提出过，算法竞赛编程（sports programming）与 GPU 性能优化需要大量高度相似的技能。模型潜在地——也许需要稍微给它一点提示或引导——能够理解：“好，我接下来用 GPU 编程解决这个问题的方法，与我之前学习算法竞赛时掌握的方法非常相似。因此，我先列出所有候选解集合，创建若干子智能体去检索并筛选有前景的方向，然后编写一个循环来遍历并校验这些方案，进一步完善它们并通过验证器（verifier）进行验证。”

<details>
<summary>Original English</summary>

**Speaker B**: For example, I will give example: I claimed that sports programming and GPU optimization require a lot similar skills. The model can potentially—possibly, you will have to give a little push—but she can understand: "Okay, the way I will be solve this task with GPU programming, very similar to what I learned for sports programming." Therefore, I will list the set solutions, create subagents for search for promising options, and then I will write a loop to walk and check these solution, perhaps develop them and check for with help verifier.

</details>

**Speaker B**: 尽管这两项具体任务看起来各具特色，各子智能体执行的具体工作也各有差异，但难道各个子智能体所求解的问题，其内在形态（shape）不正是相同的吗？这就像是一个递归论证。因此，我试图在这篇博文中表达的是：我们非常有必要重新审视脚手架的作用，因为合适的框架结构能够显著提升模型在高阶泛化与复杂处理层面的能力。

<details>
<summary>Original English</summary>

**Speaker B**: And although these two tasks they look the same, what they do subagents may be unique and something, well, to others. But isn't it? Maybe what they decide subagents, actually have the same shape? Because it's like recursive argument. So, I'm trying say this post in blog, what is it worth to us rethink the role harness, because frames can significantly increase your ability models up to generalization and processing.

</details>

<!-- chunk 6/13 -->

### 探索超越 RLM 的全新执行框架与归纳偏置

**Guest**: ……效率数据。这不仅适用于 RLM。我相信存在着一大类尚未被发掘的框架，它们能够提供类似的特性。顺着这个思路进一步推导，我认为可以得出这样一个结论：如果审视 RLM，RLM 的哪些组件实际上是必需的？我们是否真的可以直接训练模型来做到这一点？我能否训练模型在前向传播过程中隐式地像 RLM 那样运作？这是一个相当奇特的想法，因为大家可能会说：“啊，代码是不可微的”等等，但存在许多针对此类行为的近似方法，我们将逐步揭开它们的面纱。我认为我们将会超越简单的思路，比如“我要创建一个新的编码框架，利用某种特殊的压缩形式”。我认为在这个问题上我们可以更具创造力。

<details>
<summary>Original English</summary>

**Guest**: efficiency data. And this applies not only to RLM. I believe that there is wide class frames that have not yet been open and which can provide similar properties. AND developing this The argument goes further, I think, you can make from this conclusion: if I looking at RLM, which RLM components actually there is necessary? And whether Can I really? just teach model to do it directly? Can I teach the model to act as RLM implicitly during forward pass pass)? This is quite strange. thought, because you can say: "ah, code" undifferentiated" and so on, but there is many approximations such behavior, which we will start to open, and I think we will go beyond simple: "I will create new frame for encoding that

</details>

**Guest**: 我觉得我们在这些语言模型上能做很多事情，只是我们还没去付诸行动。这让我倍受鼓舞，因为我认为我们完全可以通过高度聚焦、高质量的框架设计来获得巨大的收益，而且这些设计能够更好地扩展。我的意思是，比如 RLM，它其实具有非常原始的归纳偏置（inductive bias）。它的设计没有什么非凡之处，除了一点：它与我们当前的做法截然不同。但这在利用我们现有的数据和环境方面，潜在地具有更好的可扩展性。人们可能会提出相反的疑问：现代框架在代码处理方面是非常通用的，大家看到它适用于很多领域——Claude Code 被用于设计、PPT 演示以及各种场景，还有 Cursor、Spark、Grok 等。这些都是非常简单、中立的框架，既擅长处理代码，又具备可扩展性。

<details>
<summary>Original English</summary>

**Guest**: uses special form compression. I think what can we be lot more creative in on this issue. We we can do with these language models yes a lot of things, I think we just we don't do it I am very inspired by this, because I think we can. to get substantial benefits due to very purposeful and high-quality design frames that are better scalable. I have on meaning that RLM, for example, there is a very primitive inductive displacement. In his there is nothing in the design extraordinary, except that he is very differs from of what we do now. But this potentially can to scale much better with those data and environments that we we have in at your disposal. Probably the opposite the question that people could put: modern frames are very universal regarding coding, and people see that it works for many areas. Cloud code used for design, presentations and everything else. Well, Muse, Spark, Grockbot. This is very simple, neutral frames that are good work with code and are also scalable.

</details>

### 运行时环境的同质化与模型能力的解耦

**Host**: 嗯，能举个例子说明我们该如何改进它们吗？

<details>
<summary>Original English</summary>

**Host**: Ahem , what an example of that, how can we get them improve?

</details>

**Guest**: 可以。让我想想，我想提一下最近刚发表的另一篇文章。那是一篇关于运行时环境税（tax on runtime environments）的文章，好像来自 LMSYS/Arena。我非常喜欢那篇文章，因为它验证了我之前的猜想，完全证实了我的假设。是的，大部分环境选择其实并不重要，因为它们本质上都是同质的。但我得说，比如 Grok，就我所知，它其实与其他环境的构建方式有很大不同。我喜欢这一点，真的非常喜欢。

<details>
<summary>Original English</summary>

**Guest**: Yes. Um, let me, let me to mention another one the article that came out very recently. It like an article about tax on runtime environments . It seems to be from Arena. I really like it. like this one article because it makes assumptions, which I had, and exactly what most she confirms assumption. Yes. Majority environmental elections are irrelevant because they are all the same. But I will say that Grockpot, for example, actually quite different , as far

</details>

**Guest**: 还有一点我觉得至少是明确的，我几乎可以肯定，Anthropic 或 OpenAI 完全是在他们自己的专属环境中进行训练的。他们大概率不会在竞品的环境中训练——我的意思是，我推测不会，因为我看不出他们有什么理由这么做。但是，在开源模型中我们看到了不同的情况，对吧？例如 Qwen，开源社区用得非常好。它们需要在特定环境中训练；而过去的 Gemma 在这方面曾因薄弱而闻名。模型本身是不错的，但需要置于环境中进行训练。我仍然认为，随着模型变得越来越聪明、越来越强大，这种差异将不再那么关键。我的意思是，如果你把先进模型（如 Claude / Astra）放入开源环境中，它并不会崩溃失效，因为在我看来它已经足够优秀了。我之所以这么说，是因为这些不同环境之间的唯一优势——主要就只是成本问题。

<details>
<summary>Original English</summary>

**Guest**: as I'm concerned, from the fact that how were they developed some others environment. And I like it. I really like it. Ahem, and I think that here at least it's clear, that I am almost certain, what is Anthropic or OpenAI train exclusively on their environments. They probably don't train on environments competitors, I have mind, I would assume, that no, because I don't know, Why would they do that? But, you know, that's what we see in the open models, right? For example, Quinn is very uses well open source. Them need to train in environments. Old Gema were known for their weakness in this. The models are good, but their need to train in environment. I still I think that to the extent that how models become

</details>

### “轨迹即提示词”的局限与新型后训练扩展

**Guest**: 我的意思是，如果你把这些模型接入 RLM，它们目前的表现都还算不上顶级，只能算尚可。我认为这主要是因为我们当前训练所依托的环境类型——就是这类环境范式。这种循环我称之为“轨迹即提示词”（trajectory as a prompt），它的含义很简单，就是你把整个执行轨迹都保留为基座模型使用的上下文。即使你使用子智能体（subagents），整个运行架构也依然是这种形态。我认为如果我们想探索新的环境，就应该有专门的团队投入进来，围绕扩展新环境进行有意义的实验，例如探索在不同环境设计下进行后训练的扩展规律（scaling after training）。我认为我们确实能从这类研究中获取非常可观的认知和收益，无论最终形式是 RLM 还是别的形态。

<details>
<summary>Original English</summary>

**Guest**: smarter or better, this the difference becomes not so important in that meaning that if you take Astra and put it in open source, it won't go crazy, because She, in my opinion, good enough. And I I say this because the only advantages between these different environments —it's mostly just cost. And I think, what do I mean by that if you connect these models to RLM, they are all not yet so good. They normal. And I think, this is mainly because the types environments in which we we are training—this is it class of environments. This cycle, I call it " trajectory as a prompt ", which simply means, that you keep all execution trajectory as a context that uses

</details>

**Guest**: 这令人兴奋，因为我认为，举例来说，如果你在特定环境上进行长期训练，比如 Fable 曾是针对 RLM 最好的模型，因为它们拥有动态工作进程（dynamic worker processes），显而易见这在某种程度上是一种后天习得的能力。即使模型本身略有瑕疵，在 RLM 环境中它的表现仍然远超其他模型。如今 Astra 在这些任务上的应对能力也相当不错。

<details>
<summary>Original English</summary>

**Guest**: your basic model. Even if you use subagents, that's all it looks like this . And I think that if we we want to explore new environments, there should be teams, who are engaged in conducting meaningful experiments on scaling new environments, for example, scaling after training on different environmental designs. I I think we really we can get very significant knowledge or benefits from things like that. Regardless of whether is it RLM or something else. And that's exciting, because I I think, for example, if you are long training on Fable, [] was the best model for RLM, because they had dynamic workers processes, and it was it is quite obvious that this is to some extent acquired ability. Even if the model was a little imperfect, in in the RLM environment it still worked much better than other models. Astra now also enough copes well with these tasks.

</details>

**Host**: 但我们目前的认知就仅限于此吗？我们看到 Fable 对 RLM 最适配，还有其他的吗？

<details>
<summary>Original English</summary>

**Host**: But is this where we are? we see that Fable best for RLM, is there any other?

</details>

**Guest**: 哦不，可能就这些了。这大多属于内部实验结果。是的，我现在手头有这些数据，但尚未公开。不过总体而言，我认为你很容易就能理解，我们目前的各种工作流其实根本还没有针对 RLM 进行深度优化。我认为如果我们能够训练出能够正确处理这一模式的模型，它们的效果也会显著提高。也就是说，你可以思考一下为什么会是这样，对吧？

<details>
<summary>Original English</summary>

**Guest**: Oh no, that's probably all. internal results . Yes, I have them now. not in the open accessible, but in general, I think you can you are very easy you will understand that we are still not optimized workflows for RLM. And I think if we we will obtain models that will do this right, they too will be significantly more effective. That is, you can just to consider why this is yes, right?

</details>

### 什么是 RLM：代码作为唯一工具与上下文解耦

**Host**: 我觉得现在正适合用 10 秒钟解释一下究竟什么是 RLM。因为虽然我们假定这里的很多听众具备相关背景知识，但你已经引入了特定的讨论语境。那么综合前面所讲的一切，我们能否得到一个清晰明确的定义？什么是 RLM？

<details>
<summary>Original English</summary>

**Host**: I think this is the moment when worth giving a 10-second explanation of what RLM is, because there are many here listeners who we assume having knowledge, but you have already asked a certain context, so whether can we get clear definition, taking everything into account said?

</details>

**Guest**: 是的，好的。我想回到那篇博文——关于组合式泛化器（composite generalizers）的博文，就是那篇。好，这最好能在原始论文中体现。RLM 本质上是一种环境设计，在这个环境中唯一的工具就是代码。它是一种基于代码的子智能体调用机制，智能体不仅能够将自身作为工具调用，还可以调用其他工具，但所有工具都表现为代码中的函数；而且智能体操作的上下文，始终保存在该编程环境的内存中，这也可以是一个文件系统。

<details>
<summary>Original English</summary>

**Guest**: RLM? Yes. Good. I want return to the blog, to the blog about composite generalizers, here this. OK. It best, I would like have it in original article. RLM is, in essence, such design of an environment where the only tool there is a code. This is software subagent call, where he has the opportunity to call oneself as tool, as well as has other tools, but they all are functions in the code, and the context with which it works, always stored in

</details>

**Guest**: 比如我给你举个例子：Prime Agent。对于 Prime Agent 而言，即便你在对执行轨迹上下文进行压缩或做类似处理，它的轨迹仍保存在磁盘上。因此模型始终能够调取自己最初的完整上下文，即便它被压缩了；而它的所有工具都在 Python REPL 或 Bash REPL 中执行。这是一种非常朴素的抽象。我想说，大多数智能体环境的区别在于，它们并没有实现上下文的解耦转储（unloading context）。我是说，如果你看一下 Prime Agent，顺便提一下，Prime Agent 会转储上下文，但并没有完全彻底。也就是说，它仍然保留了类似 Claude Code 的标准循环，即“轨迹作为提示词”被压缩带入，但它增加了一个特性——上下文可以转储到外部存储中。Prime Agent 的独特之处还在于它的唯一交互工具就是 IPython。所以某种意义上，它代表了围绕 RLM 的一种通用抽象。

<details>
<summary>Original English</summary>

**Guest**: in memory of this software environment. This can be a file system. For example, I will give you example: Prime Agent. Prime Agent Trajectory, even the context when you squeeze it and do all these things, stored on disk, so the model always can to turn to one's initial context, even if it is compressed, and all her tools are launched, say, in the Python REPL or bash REPL. This is very primitive abstraction, and I would said that most environments differ in that unloading context This is not happening. I mean, if take a look at Prime Agent, by the way, Prime Agent unloading context, but not fully. That is, he still keeps standard cycle Cloud Codex, where the trajectory is the hint you squeeze, but he has an additional feature- context is unloaded, and The uniqueness of Prime Agent is that his only one The tool is IPython. So it's kind of very general abstraction around RLM .

</details>

### RLM 旨在解决的核心问题：组合性与中央上下文

**Host**: 具体来说，RLM 试图解决的核心问题究竟是什么？

<details>
<summary>Original English</summary>

**Host**: Specifically. Wherein is the main thing the problem that are trying to solve RLM?

</details>

**Guest**: 在某种程度上，我认为当它们最初出现时，核心问题是上下文和……我先跳过这个问题。是的，最初的问题在于各种测试框架/测试平台（harnesses）很难处理超长上下文。通常它们仅用于特定场景，比如编程任务。正如大家所知，模型之所以能在你的代码库中运行，是因为它们在此类场景下受过专门训练。但现在的重点更在于我博文中所讨论的内容，那就是组合性（compositionality）。因为我认为我们希望构建的语言模型系统，必须对每一步执行的动作拥有更大的控制权。

<details>
<summary>Original English</summary>

**Guest**: To some extent, I I think when they just appeared, this there was a context and... I'll skip this question. Yes. So, the initial the problem was because the frames ( harnesses) very difficult to work with a long context. Usually they were used only for specific things, for example, for code. As you know, they could work with your codebase because they were there trained. But now it's more about, What is it about? this blog, namely—in compositionality, and in because I think we we want to have systems language models that have much more control over actions that they performed on each step. And by that I mean meaning that the challenges very tools limited because their need to call at

</details>

**Guest**: 我的意思是，传统的工具调用方式是非常受限的，因为每个轮次你都必须去单独调用工具。也就是说，你必须先调用工具 A，再调用工具 B，然后再调用工具 B，在这个过程中并不存在一个可以随时与之交互的中央上下文（central context）。而 RLM 恰恰是围绕组合性以及可用的中央上下文专门设计的，智能体可以随时从这个中央上下文中提取和回溯信息。这是一种围绕现有语言模型演进出来的统一上下文范式。另一个在设计上非常相似的例子是智能体集群（agent swarms），比如 Hugging Face 所做的相关实验。在这些智能体集群中，它们设有一个公共留言板（message board），通过这个看板学习交流沟通，而在某种意义上，这个看板就是它们共同共享的中央上下文……

<details>
<summary>Original English</summary>

**Guest**: every turn. That is, you need call the tool A, then tool B, then tool B, and there is no central context to which you can contact, while RLM specifically designed around compositions and availability central context from which you can always draw information. And this one context developed around existing language models. Yet one is very similar to design example—this agent swarms, for example, an incident with Hugging Face. Such agents the swarms have a board messages, through what they are learning communicate, and this board in a sense is common the context in which they

</details>

<!-- chunk 7/13 -->

### 代码作为通信媒介与 RLM 的局部同分布特性

**Speaker A**: 本质上，他们认为在这里最好的通信媒介是代码——也就是说，你通过编写代码来实现这一点。而这是因为这些模型非常擅长写代码，所以我们希望借此来利用这一点。再到这种组合式的结构，直到针对特定任务构建出自己的专属框架。

<details>
<summary>Original English</summary>

**Speaker A**: In essence, they say that the best way communication here is code, that is, you write code to do this realize. And this because these models so skilled at writing code that we we want to use hereby. And then for this one compositional thing, until the creation own frame, specific to specific task.

</details>

**Speaker B**: 没错，确实如此。我想我们可以从这里开始，看看……让我们来看这张图。好的。

<details>
<summary>Original English</summary>

**Speaker B**: That's right. That's right. I think we'll start this. to see if let's get to this drawing. OK.

</details>

**Speaker A**: 那么，我们正在讨论的是一种为框架提供局部同分布任务（locally in-distribution tasks）的思路。当我们思考语言模型时，这个概念与分布内任务（in-distribution tasks）相辅相成。分布范围之内的任务是指那种简单的任务——用户的请求是模型以前就已经见过的，或者见过某种变体。大多数现有的系统都是这样运作的：它们不断地将整个轨迹（trajectory）作为查询上下文附加进去。因此归根结底，如果你不是 Anthropic 或 OpenAI，并且你没有在这些自定义轨迹上进行过专门的训练，那么大多数这类任务在很大程度上都会超出模型的分布范围（out of distribution）。

<details>
<summary>Original English</summary>

**Speaker A**: So we are talking about an idea locally distributed tasks for the frame, and this is the idea, which complements distributed tasks (in-distribution tasks), when we thinking about language models. The task in within the boundaries of the distribution—this simple task where A request is something that the model has already seen before, or seen some version of it. Most systems work like that right: they constantly adding trajectory as a query. So ultimately, if you not Anthropic or OpenAI and not you study at such here are the custom ones trajectories, most of these things for the most part go beyond distribution.

</details>

**Speaker A**: 但是局部“分布之内”（locally in-distribution）——本质上是一种组合式的论证：如果 RLM 将其计算分解为某种元系统或程序，其中包括用于局部解决问题的子智能体（subagents），那么在执行该任务的过程中，对语言模型的每一次单独调用都保持在分布之内，即使整体任务作为一个宏观整体是超出分布的。在我看来，出于显而易见的原因，这是一个非常理想的特性。例如，如果每次对语言模型的独立调用所面临的任务都在“分布范围之内”，那么你大概率能够得到正确的回复。

<details>
<summary>Original English</summary>

**Speaker A**: But locally "within" distribution"—this is, according to essentially, composite argument: if RLM breaks his/hers calculation on a kind of meta-system or program, which includes subagents for local solution problems, then everyone separate call language model during doing this the task remains within the distribution, even if everything the task as a whole— outside of it. And this is very desirable property, in my opinion, with obvious reasons. For example, if each tasks for everyone separate call language model is "in within the limits of distribution", you, most likely, get the right one respond.

</details>

### RLM 训练、后训练扩展律与框架抽象的差异

**Speaker A**: 嗯，所以……我的意思是，RLM 的逻辑演进终点是 RLMS——在那里你不仅仅是在编写一个系统，而且还在训练你自己的模型、收集数据，这就好比在你的系统内部有一个完全自动化的 AI 研究员。是的，我们且看 RLM 训练未来会走向何方。作为一个研究学者，我坦率地说：我自己在麻省理工学院（MIT）并没有在这个规模上开展研究，至少没有做大规模训练，因为我承担不起这个成本。但是有一些公司正在做这件事。我认为 Prime 和 Select 很明显正在朝这个方向努力，这非常酷。我非常渴望看到，当你围绕一个“聪明”的框架去训练系统时，我们是否能观察到更好的后训练扩展（scaling after training）效果。也许我们甚至会见证基于这类原则运作得更好的更智能系统的出现。

<details>
<summary>Original English</summary>

**Speaker A**: Um, so...I I mean that the logical boundary of RLM is RLMS where you are not just write a system, and also teach your own model, collect data —it's like completely automated AI- researcher inside your system. Yes, we'll see where will move RLM training. I'll tell you how. scientist: I don't I'm working on this at MIT, at least in scale, because I don't I can afford this. to allow But there are companies that They are working on this. I think Prime and Select clearly are working on this, and this very cool I am very I want to see maybe we we will observe better results scaling after learning when you train the system around the "smart" frame. Maybe we we will even see the emergence of smarter systems that are better work on the basis of such principles.

</details>

**Speaker B**: 什么是“更聪明的系统”？这并没有具体的定义。你刚才还说它们全都大同小异。

<details>
<summary>Original English</summary>

**Speaker B**: What is "smarter" system"? It's nothing. does not mean. You just said that they all are the same.

</details>

**Speaker A**: 不，我的意思是像 Claude Code、Codex、Pi 等等——在某种意义上它们都是相同的，因为当你拆解它们的内部逻辑时，它们实际上是完全一样的。是的，无非就是循环里的两次调用，仅此而已。但是对于 RLM 和其他系统级抽象，情况看起来就截然不同了。正是在这一点上，我认为你确实能看出区别。这就像选择语言模型的架构一样：很多架构决策在进行扩展（scale）时最终都会趋于一致。或者说，这些差异最终会变得相当微不足道。我的意思是，对于实验室来说这或许不是小事，但是你知道，可能某一个模型的一致性比另一个稍微好那么一点点，真的只有一点点。但总的来说，比如预训练的扩展定律之所以适用，只是因为我们目前的架构选择相对稳定，对吧？但如果你彻底改变了架构，预训练的扩展极限可能就不起作用了，或者说，那种幂律（power law）看起来就会完全不同。

<details>
<summary>Original English</summary>

**Speaker A**: No, I mean that Claude Code, Codex, Pi, etc.— they are all the same in in the sense that when to disassemble their logic, they actually identical. Yes. Two calls in cycle, and that's it. But with RLM and others abstractions of systems this looks quite otherwise. And right here, on I think you really are. You see the difference. It just like with architecture choice language model: many architectural solutions eventually become similar when you scale them. Or, type, these differences turns out, well, quite insignificant. That is, I mean, for the laboratory it is not a trifle, but, you know, maybe one model coincides a little better than the other, absolutely a little. But in general, if, for example, the limits scaling previous training only applies because the choice architecture in our country somewhat stable, right? But if you were completely changed the architecture, zoom limits previous training, probably would not work, or this, say, power the law would look like completely different.

</details>

**Speaker A**: 框架（harnesses / straps）也是完全一样的道理。在我看来，我们目前拥有的所有绑定机制（bindings），大多数看起来都差不多。但也有某些例外，我认为它们已经开始显现了。实际上，我想说的是让我更感兴趣的事情之一——如果我们谈论那些冒着巨大风险的研究生们，那就是人们也在探索另一面：如果你改变了数据，预训练的扩展定律也会失效。现在的训练数据仅仅是无结构化的文本，也就是来自互联网的语料库数据。如果为了学习而拥有更好的数据表征，那会怎样？那么，是的，你的扩展定律也会随之改变。是的。所以，有架构，有数据，还有你能想到的所有其他方面。

<details>
<summary>Original English</summary>

**Speaker A**: And that exactly with straps ( harnesses). It seems to me, that all the bindings that we now have, mostly look approximately equally. But there are certain exceptions. I think that they are already appearing. Actually, I wanted to to say that one of things that make me more interested in— if we talk about postgraduate students who are going at great risk, it is that people also investigate another side: laws scaling previous training is not working, if you change the data. Now it's simple. unstructured text, well, body data from the Internet. What, if you had better data presentation for study? Then, yes, your law scaling too would change. Yes. So, there is architecture, there is data and, you know, everything anything else you can talk about to think, so I I just want to to come back to this,

</details>

### 与 Prime 的合作契机及学术激励反思

**Speaker B**: 这些都很有道理。我非常好奇你是如何在整个技术栈上下自如穿梭的，从非常宏观的概念性事物，一直到我们现在所处的具体层面。是的，你当然可以在高层和底层之间来回拓展。我很好奇你是怎么开始与 Prime 合作的？或者说 Prime 在这方面承担了更多的工作吗？这是他们对 Hermes 智能体的回应吗？你之前提到 Grockot 稍微有些不同。我只是想列出所有这些团队，并了解你对每个团队的看法。

<details>
<summary>Original English</summary>

**Speaker B**: This all makes sense. Very I wonder how you are, in fact, moving up and down the stack, from very conceptual things to, well, like, here Where are we now we are, but yes, of course you can scale up and Down, probably. Me I wonder how you started. work with Prime? Or takes on Prime more work on this? This is their response to Hermes agents? You mentioned that Grockot is a bit another. I just wanted to to list all these guys and to know your opinion about everyone.

</details>

**Speaker A**: 是的。我在 Prime 发布了一篇博客文章之后加入了他们——顺便提一句，那篇博文跟我完全没有关系，里面阐述了他们为什么认为 RLM 代表着某种未来。我有一位朋友在他们那里工作，是我在 GP Mode 认识的朋友，我们取得了联系。我认为我与那里的许多研究人员在很多观点上不谋而合，尤其是关于框架设计（harness design）的理念。我深受触动。我认为他们真正理解了关于 RLM 的论文的主旨——那篇论文的目的并不一定在于宣称“我们解决了长上下文问题”，而在于指出我们需要更专门化的框架设计。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Yes. I joined. to Prime after they published blog post, by the way , not related at all with me, about how they believed that RLM was a kind of future. And I had a friend, who worked there, my friend from GP Mode, we got in touch, and I I think I agreed. with many researchers there and from what they believed in regarding design strapping. I was very affected. I think that they understood the purpose articles about RLM, which is not necessarily in that, to say that we we solve problems with long context, and in that we need more specialized frame designs .

</details>

**Speaker B**: 是的，一篇论文总会有你选择去着重强调的表面成果。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. There is always the result of the article, which one do you choose to highlight.

</details>

**Speaker A**: 是的，与真正的核心本质形成鲜明对比。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. In contrast the real essence.

</details>

**Speaker B**: 我真的很想深入探讨学术界的激励机制，谈谈为什么这种机制是不完善的，以及其背后的所有问题，我们稍后会回到这个话题。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. I would really like to to talk about incentives in academic environment, about why is it something imperfect and about all problems, we are We'll come back to this.

</details>

### Prime Agent 的设计原则：最小化抽象与持续演进框架

**Speaker A**: 是的。撇开这些不谈，我非常喜欢 Prime 的这群伙伴。因此在我们决定携手合作之后，我们决定探索 RLM 的训练可行性，同时也去打造一种 RLM 框架，看看这能带来怎样的成果。Prime Agent 正是在这样的背景下诞生的。我认为 Prime Agent 的反响相当不错。我对 Prime Agent 唯一担心的一点是，至少在我们最初构建它的时候，没有一个模型能足够熟练地执行 RLM 任务。那是发生在 prefabs 和 astra 出现之前的事了。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. So, is that right? otherwise, I really like it the guys from Prime. So after we decided to work together, we decided to consider learning opportunity RLM, and also create a kind of RLM frame and to see what's up this will lead. Exactly so Prime Agent appeared. And I I think Prime Agent accepted enough good. The only thing that I was worried about Prime Agent, this is what none from models, at least by the time we got her created, was not quite skilled at performing RLM tasks. This was before the advent of prefabs. and astra.

</details>

**Speaker B**: 我觉得有必要往后退一步：你能解释一下什么是 Prime Agent 吗？它与传统的 Claude Code 有何不同？人们对这个框架应该抱有怎样的预期？

<details>
<summary>Original English</summary>

**Speaker B**: I think it's worth doing. step back, can you you explain what is Prime Agent, what is he? differs from traditional cloud code, what people expect from frame.

</details>

**Speaker A**: 好的。关于 Prime Agent，我想我稍早之前提到过它。是的，它本质上是一个构建在 pi 之上的框架，比如 pi mono——作为背景补充，pi 是一个极简主义的框架。我把 pi 作为衡量一切的基准，因为我认为所有其他框架实际上骨子里都只是 pi。但是对于 Prime Agent 而言，它也是 pi，只不过我们明确限制了 IPython 作为它唯一可用的交互工具。任何其他工具要么作为 Python 模块载入，要么作为它可以执行的 Bash 脚本载入。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. So, Prime Agent, I I think I remembered. about this a little earlier. Yes, it is. essentially a frame on top pi, such as pi mono, which for context is minimalist frame. I using pi as a standard for everything, because I think everyone other frames are actually just pi. But this is pi, except that we clearly restrict ipython as the only one available him a tool. Be -any other tool loaded as Python module or how bash script that it can run.

</details>

**Speaker A**: 因此，它在 pi 之上采用了 RLM 的核心抽象，并且它还拥有一个名为“持续框架”（continual harness）的东西。这是 Seth 的研究成果，他是另一位研究生。这就是他用来驱使语言模型框架去玩游戏所使用的机制。他与 Joel 合作了很多，Joel 就是那个让 Gemini 玩《宝可梦》的开发者。顺便提一句，这个持续框架也非常简单，我个人非常喜欢它。其本质上是一种设计原则：你允许框架自身去修改框架自身的哪些部分？在其中，存在着一些明确允许它去修改的特定元素，例如它自身所拥有的技能，或者它可调用的子智能体。对于模型而言，系统提示词（system prompt）和持续框架实际上就是 IPython 内核中的一种工具形式，这就是为什么 Prime Agent 是围绕这一理念构建的，正如 Prime Agent 中的其他部分一样标准。

<details>
<summary>Original English</summary>

**Speaker A**: Therefore, he uses the main abstraction of RLM on top of pi, and also has such a thing as a continual harness , this is Seth's development, he is another graduate student. This is what he used to to force frames language models play in games. He is a lot worked with Joel, which is the same the guy whose Gemini plays in Pokémon. And continual harness, to things, also very simple. He is mine. I quite like it. This is essentially the principle design, which is that which parts of the frame you allow yourself frame change? THERE ARE certain elements that you allow him modify, for example, own Are the skills available? him subagents. ee, system prompt for models and continual harness available virtually as tool inside IPython kernels, and that's why Prime Agent is developed around this, as well as everything else in Prime Agent. standard

</details>

**Speaker B**: 遵循标准设计，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Standard, right?

</details>

**Speaker A**: 是的，我很喜欢这一点。我们运气不错的是，许多新的先进模型在其中的实际运行表现非常出色，甚至很多开源模型的效果也很棒，至少某些较新的开源模型是这样的。关于 Prime Agent 还有一点非常值得着重指出，那就是我们非常独特的通信机制……

<details>
<summary>Original English</summary>

**Speaker A**: Yes, I really like this that, and we have a little lucky that many new advanced models actually they work very well inside, and even many models with open source they work great, at least some of new. And there is one more thing at Prime Agent, which is worth to highlight, it is ours very specific communication

</details>

<!-- chunk 8/13 -->

### 子智能体通信与长程运行机制

**研究员**：智能体之间需要一套系统，或者说一套通信框架，因为递归语言模型（RLM）天然倾向于创建大量子智能体。我们希望底层的子智能体能够与根智能体通信，或者彼此之间相互通信。因此，在系统设计上必须做出决策：哪些下级智能体被允许与谁通信，以及它们具体如何实现这种通信。这一切同样完全体现在代码中，模型会直接为这种类型的通信编写代码，在我看来这种机制非常强大。

<details>
<summary>Original English</summary>

**Researcher**: There is a system between agents, or let us say a framework, because RLMs have a tendency to create many sub-agents. We want the sub-agents to be able to communicate with the root agent or with each other. So there are certain design decisions on whether who under each agent is allowed to communicate and how it does. Again, yes, it is all in the code. So it writes code for this type of communication, which, in my opinion, is very, very steep.

</details>

**主持人**：而且看起来系统里还引入了持久化子智能体，这是新增的另一项特性。这些子智能体的存续时间可以超过原本父级智能体的标准工作周期。你可以直接找到这样的子智能体，向它输入更多提示词。也就是说，对于当前正在发生的事情，你拥有了更高的可见性与灵活性。这也正是我目前对 Codex 最主要的不满所在：它们的子智能体生命周期非常短暂，而且在处理长期运行的任务流程时往往直接拒绝调用。

<details>
<summary>Original English</summary>

**Host**: And yet, it seems there are permanent sub-agents, that is another thing that was added, that is sub-agents. They may exist longer than standard working hours of the original agent, and you can go to such a sub-agent, give him more prompts, that is, you have more visibility and flexibility regarding what is going on. This is my main problem with Codex now. Their sub-agents are very fleeting, and they actively refuse to use them for long-term processes.

</details>

**研究员**：没错，确实如此。

<details>
<summary>Original English</summary>

**Researcher**: Yes. Yes. Yes.

</details>

### 全面依托文件系统与代码生成

**主持人**：在我看来这完全讲得通。我的意思是，整套方案的核心秘密就在于把所有状态都沉淀到文件系统里，对吧？这就是整套设计的关键秘诀。

<details>
<summary>Original English</summary>

**Host**: What, how about me, makes sense. Yes. So I mean, the whole secret is that to take everything out to the file system, right? This is the whole thing, the secret. This is it, the main secret.

</details>

**研究员**：是的。而且还要强制所有操作都通过代码来运行。也就是说，你要信任一个能够编写代码的模型，相信它会自主为自己编写所有必需的工具。

<details>
<summary>Original English</summary>

**Researcher**: Yes. And also to force everything works through code, you know, trust a model that can write code, and it will write for herself all necessary tools.

</details>

**主持人**：那么，Prime 会参与进来，专门针对这个架构进行后续的模型定制微调与训练吗？这算不算是你们之间的一次性合作？

<details>
<summary>Original English</summary>

**Host**: So, is Prime coming to study, post-training custom models for this? Is this a one-time collaboration between you?

</details>

### 博士研究规划与 RLM 的外部探索

**研究员**：关于这一点，是的，他们内部确实在训练模型，而且我认为他们早在三月份就已经公开谈论过这件事了。显然，这是他们的商业业务范畴。

<details>
<summary>Original English</summary>

**Researcher**: That is all. As of yes, they teach model, internal, I think they spoke openly about this back in March. That is, obviously, this is their business, so...

</details>

**主持人**：明白。

<details>
<summary>Original English</summary>

**Host**: Yes.

</details>

**研究员**：是的，他们展示了有能力通过自己的训练技术栈来进行模型训练。但在具体的模型训练上，我并没有参与他们的这部分工作。最主要的原因在于，在我的博士研究课题中，我还有很多其他想做的事情。我认为除了仅局限于 RLM 本身之外，还有许多其他重大方向值得去投入押注。我现在能透露的可能有限，但总体而言，我认为读博最大的优势之一，就是你真的有机会去押注很多重大的设想。虽然其中的大部分可能最终一无所获，但这确实是一个极具吸引力的科研时期，尤其是因为该行业近期的大部分进展在我看来都有些索然无味。我并不是说研究结果本身无趣，而是落实这些成果的具体过程往往相当枯燥。因此这就引出了一个问题：我们究竟还想做些什么？不过这个话题我们可以稍后再聊。

<details>
<summary>Original English</summary>

**Researcher**: Well, yes, that is, they show that they can teach it on their own stack for teaching. But no, regarding model training, I am not involved with them in this. The main reason is because within the PhD I have other things to do which I want to work on. I think that there are many other big bets that are worth doing, except only RLM themselves. I do not know as much as I can tell now, but in general, I think that one of the advantages of studying in postgraduate studies is really a possibility to do a lot of big bets. Most of them probably will not bring anything. But this is really a very interesting time for research, especially because most of the progress in this industry, in my opinion, was somewhat boring. I am not saying that the result is boring, but the process of implementing these things is usually quite boring. And therefore the question arises: what do we want to do more of? But we can talk about it later.

</details>

### 业界案例与开源生态探索

**主持人**：好的。我想先总结一下你的这项研究，然后我们再聊别的，因为 RLM 发布之后引发了外界极大的关注与讨论。在第三方的工作中，有没有哪些是你特别想提及并推荐大家去关注的？

<details>
<summary>Original English</summary>

**Host**: Yes. OK. I want to sum up your research, and then we can move on to another, because after the release of RLM there was a lot of excitement around this. Are there any third-party works about which you want to remember, where people say, "you should look at this"?

</details>

**研究员**：哦，有的，确实有一些。比如法律 AI 公司 Harvey 在其官方博客上发布了一篇文章——他们和我们没有任何合作关系——但他们将 RLM 迁移到了自身的法律业务场景中。法律工作往往涉及大量的文档审查，以及检索各种非常具体的细节信息，而这类信息通常很难通过简单的传统搜索引擎提取出来。他们取得的成果非常出色，令人十分振奋。我当时感到非常震撼，因为他们是在我们完全不知情的情况下自主推进这项工作的。直到文章发布出来，我才惊叹道：“哇，这太棒了。”我觉得他们在那里的探索非常酷。另外还有一个与 Base10 的合作项目，好像是叫做 Headlong 还是什么？也就是 Lud 学院的工具，那是一个持续常驻运行的系统，非常酷。

<details>
<summary>Original English</summary>

**Researcher**: Oh, yes, yes, yes. Harvey, the legal AI company, published a post in their blog—they are not related to us—but they retrained RLM on their legal work, which often involves a lot of document review and searching diverse specific information that may not be so easy to extract with the help of simple search systems. And they really showed very good results. This is very fascinating. I mean, I was shocked that they worked on this. They did not tell me. So when this turned out, I thought: oh, this is great. So this is what I think is super cool, what they do there. Another thing seems to be also collaboration with Base 10. This is... Headlong, what is it? The Lud Institute instrument—it is their system that works constantly. It is very cool.

</details>

**主持人**：哦，他们改名了。他们之前叫别的名字，好像叫 Auto terminus 之类的。

<details>
<summary>Original English</summary>

**Host**: Oh, they renamed it. They used to call it differently. It was something like Auto terminus.

</details>

**研究员**：对，我知道，他们经历了更名。那是 Andy Kwinski 的一个大项目，超级厉害。我很欣赏 Andy。我绝无贬低他们工作的意思，虽然他们采用了 RLM 的抽象范式，但他们实际做出的东西远比单纯的 RLM 要强大得多。它就像是一个始终处于思考状态的系统，哪怕你当前没有发出任何请求，它也有一套机制去持续思考上下文中的问题。

<details>
<summary>Original English</summary>

**Researcher**: Yes, I know, they went through this. It is Andy Kwinski’s big project. This is super cool. I love Andy. I do not want to belittle what they do, because they use the RLM abstraction, but they are doing something much cooler than just RLM. Well, it is like they have a system which, so to speak, is constantly thinking. So even when you do not make a request, it has a way to think about problems which are in its context.

</details>

**主持人**：哦，这听起来像是一个永远保持开启的常驻系统？

<details>
<summary>Original English</summary>

**Host**: Oh, it is like an always-on system?

</details>

**研究员**：它就像一个持续运转的系统，但使用成本却并不高昂。他们对 Token 消耗成本做了严格控制，确保它不会耗尽你的全部额度，这非常厉害。我还在努力回想，实际上还有很多项目。如果你去 GitHub 上的 RLM 页面，我在下方链接中列出了一大批案例。很多人基于此做出了极其酷炫的成果。比如 Axe，这是另一个很棒的项目，似乎出自一位独立开发者之手，它结合了 DSPy 工具集与 RLM，现在 DSPy 本身也支持了 RLM。最后我还想提一下 ARC-AGI 3。在 Kaggle 举办的竞赛中，无论是在官方评测、私人探索还是公开基准评测里，出现了许多工具，它们都声称借鉴或引用了 RLM 的抽象（比如 Tufa），将其作为工具的核心设计灵感，这非常非常精彩。我认为这种环境恰恰展现了组合机制与代码调用的巨大优势，将神经符号系统与人工智能深度结合了起来。

<details>
<summary>Original English</summary>

**Researcher**: It is like something that always works, but not very expensive. They control costs in tokens to make sure that this does not burn all your credits. This is very steep. I am trying to remember, there are actually a lot. If you go to the GitHub RLM page, there is a bunch of things that I provided a link to below. There are many really cool things that people did. Axe is another very cool project, it seems from one developer. It is like DSP toolkit and RLM. DSPy also has RLM. Oh, the last thing what I want to mention is ARC-AGI 3. I think there were a lot of tools for their Kaggle competition—official, private, or what people used for evaluation. They all claim that they use, or refer to, for example, Tufa, some form or inspiration form of RLM abstraction in their tools, which is very, very cool. I think that is an environment where you would see a lot of benefits from composition and code usage, combining neurosymbolic systems with artificial intelligence and so on.

</details>

**主持人**：是的，太酷了。我们向来喜欢神经符号系统的结合。

<details>
<summary>Original English</summary>

**Host**: Yes, very, very cool. We love a good link to neurosymbolism.

</details>

### OpenAI 评测突破、智能体集群与调度控制

**主持人**：你刚才提到了 ARC-AGI 3。OpenAI 最近公布他们在该项基准测试中达到了 99.9% 的准确率。他们还声称直接把模型扔给 Navier-Stokes（纳维-斯托克斯）方程就完成了求解。关于这是否仅仅是一个简单的基础模型，外界还存在一些争议。你知道他们是否使用了 RLM 吗？

<details>
<summary>Original English</summary>

**Host**: Yes. You also mentioned ARC-AGI 3. OpenAI came out and said that they reached 99.9% in this. They also said that they solved the Navier-Stokes equations, just throwing a model at it. There is some debate about whether it is a simple model. Mhm. Do they use RLM? Do you know?

</details>

**研究员**：我个人推测大概率没有直接使用，除非……不过在这一点上我需要谨慎措辞，因为大家对于到底什么是 RLM、什么不是 RLM 一直存在争论。很显然，他们使用的是某种依托共享上下文（例如共享文件系统）的智能体集群（Swarm）。从理念上讲，这非常符合 RLM 的精神内核，但我认为他们在工程上做了很多更为复杂精妙的处理，而这些可能与 RLM 本身并无直接关联。我部分认同这样一种观点：对于他们所取得的成果而言，具体的工具框架并不是绝对必不可少的。用我的话来说，像 GPT-o1 这样的模型在技术上已经足够聪明，只要能为其提供恰当的信息，它完全有能力为这些极端复杂的问题找到证明。但真正的核心挑战在于：你究竟如何将这些关键信息发掘并呈现给模型？在他们的方案中，这大概率归结为在整个智能体集群或多个子系统中展开极其漫长深入的搜索，并且可能还有人类研究人员的直接参与——关于这一点我并不完全确定——人类研究人员在过程中注入关于哪些路径值得探索的直觉判断。最终，整个系统沉淀出了关键信息，某个智能体得以利用这些信息顺利完成了证明。因此从这个维度来看，那套底层的编排调度系统本身到底是不是决定性因素？其实并不是。我认为这恰恰说明，控制调度系统的具体实现细节并没有那么至关重要。这也正印证了关于“控制系统税”（调度税）的那篇文章的核心观点：除了面向用户的系统交互体验之外，真正关键的只有一点，那就是你如何以富有逻辑的方式将这些智能体组合起来，从而推导出最终答案。而这或许正是集群（Swarm）以及类似架构的本质所在。因此，至少从我的视角来看，当我们思考面向用户的真实应用场景时，我们到底希望从调度管理系统中获得什么？我们希望汲取其中的最佳实践——比如类似 Cursor 或 Codex 那样流畅的代码流式体验，那是用户喜闻乐见的；而在“引擎盖之下”，则可能运行着一个极其复杂、行为奇异的智能体集群，最终由它产出解答。普通用户自然不希望看到这些晦涩难懂的中间过程信息。所以你看，这本质上仍然延续了 RLM（递归语言模型）的内在精髓。“递归语言模型”听起来像是一个单一的模型名称，但它绝非传统的语言模型架构。正如我此前在博客中所写的那样，我相信我们未来将会逐渐目睹这一趋势：我们传统认知中与之交互的所谓“语言模型”，其实际载体很可能就是一个由多智能体协作构成的集群或框架系统。

<details>
<summary>Original English</summary>

**Researcher**: I mean, I would assume rather absolutely not, unless... let me be careful here, because people argue about what is RLM and what is not. Clearly, they used some kind of swarm of agents with a shared context, such as a file sharing system. And this is very much in the spirit of RLM, but I think a lot more cunning things have been done which may not be related to RLM itself. I partially agree with the idea that the toolkit is not so necessary for what they did. I would put it this way: in my opinion, a model like GPT-o1 is technically smart enough, given the appropriate information, to find proofs for these very, very complex tasks. But how to get this information—that is the big question. And in their case, it probably came down to a very long search among many such subsystems or agents in a swarm, and possibly with the participation of researchers—I am actually not sure about that part—adding their intuitions about what is worth investigating, and things like that. And in the end it worked out: certain information was produced that some agent was able to use to complete the proof. So in that sense, was the control system itself important? No. And I think that this indicates that the specific details of control systems actually do not have much value. And I think that is exactly what the article about the "orchestration tax" points to, namely: beyond the user experience of the system, really all that matters is how you combine these agents in a meaningful way to get to the final answer. And perhaps that is the whole point of swarms and everything like that. Therefore, at least from my point of view, if we start thinking about user-facing scenarios, what do we want from control systems and things like that? We want to take the best of it—cloud codes, Codex-type models, that stream which people love to see, but "under the hood" a very strange and complex swarm of agents can work, which ultimately yields the response. The user does not want to see this, of course, right? This is incomprehensible information. And therefore, you know, this was still one thing in the spirit of RLM, like "recursive language model". This sounds like a language model, but this is not a language model architecture. The reason is that, as I think we will start to see in the future, maybe one day—and I wrote about it on the blog—what we think of as a language model, the object to which we appeal, in reality can be a swarm or a framework.

</details>

<!-- chunk 9/13 -->

### 系统设计、扩展性与 Transformer 的本质边界

**Speaker A**: 某些奇特的系统设计与管理方式固然具备很好的扩展性，但用户本身往往感知不到这一点。归根结底，用户最终看到的一切，不过是这套系统对外呈现的某种交互界面罢了。是的，我认为至少从我们能看到的层面来说，这种假设是相当稳妥的。

<details>
<summary>Original English</summary>

**Speaker A**: Some strange system design management, which is good scalable, but user of this just doesn't see. Ultimately, everything that user sees—this is some kind of interface version of this system. And yes, I think that's it. Quite safe assumption, at least in terms of that we will see it.

</details>

**Speaker A**: 嗯，这或许又把我们带回到了 Transformer 的基础局限性上。显而易见，如果你只是拿一个最基础的 Transformer 模型，直接要求它去求解纳维-斯托克斯方程（Navier-Stokes）或类似的高深问题，它根本做不到。我们都很清楚这种事情不可能直接发生。但我认为更有趣的部分在于，关于所谓的“复杂度”究竟意味着什么，更相关的或许是：在不断累积上下文信息的驱动下，让模型或智能体沿着某个任意方向自主推进，这本身可能就足以解决非常复杂的问题了。对此我是相信的。

<details>
<summary>Original English</summary>

**Speaker A**: Hmm, and this is perhaps takes us back to basic limitations transformer. Well, you know, obviously, if you just take the basic one transformer and tell him solve the equation Navier-Stokes or something like that, he doesn't will do. Yes, we all are. We know that this is not will happen. But yes, I am I think it's possible. The more interesting part, and, maybe, statement about whether it has meaning complexity, more relevant that which is simply arbitrary direction models or agents on the rise context of information, maybe enough for solving very complex problems. Ahem, I can believe that.

</details>

### OpenAI 的庞大算力开销与多智能体组织架构

**Speaker B**: 尽管各种讨论很多，但我想说的是，OpenAI 实际消耗的资源其实属于半公开状态：在 88 小时内动用了 10,000 个智能体，消耗了 1300 亿输出 token。按公开标价折算，大约价值 4000 万美元。

<details>
<summary>Original English</summary>

**Speaker B**: Although there are many everything, I want to say that the amount that spent OpenAI, there is semi-public. This is 10 000 agents in 88 hours. 130 billion weekends tokens that estimated at approximately 40 million dollars at public prices.

</details>

**Speaker A**: 令人惊讶的是，这个数字其实比我预想的要少。

<details>
<summary>Original English</summary>

**Speaker A**: Surprisingly, actually less than I thought.

</details>

**Speaker B**: 是的，其实没那么多。这 1300 亿仅仅是生成最终结果的输出 token。但正如你所说，在上下文中传递的信息量极其庞大。如果只把智能体之间传递的全部消息总量算进去，这个数字直接翻了两倍不止。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, not really many. 130 billion for output for final result, but how do you said, a lot was passed on context. It more than twice more if you count only general number messages between agents.

</details>

**Speaker A**: 对，确实如此。我想提的一点是 Cursor 团队关于集群智能体系统（Swarm systems）的讨论。虽然这信息稍微有点过时了——那是今年二月份的事，在当下已经算很早以前了。但如果你翻到最后看他们最终构建的多智能体架构，它本质上就像一个常规软件开发团队的组织架构图。其中有一点让我印象深刻：系统里有一个必须在各个子智能体之间执行的“汇集全部”（gather all）操作，这实际上和 GPU 编程非常相似。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Yes. Yes. Yes. I think one thing, which I should mention, this is a Cursor, which refers to swarm issues systems. This is a bit older information, I mean February, that is already ancient. But if you scroll to until the very end final architecture multi-agent the system to which they belong arrived, it was actually organizational diagram of the usual development teams Software. One thing I'm talking about I think that's what's there. "Gather all" function, which you should to perform with subagents, and this actually very similar for programming for GPU.

</details>

**Speaker B**: 没错，正是这样。正因如此，它成了一个致命的性能瓶颈。你有一个核心主管去协调所有下属，然后下属执行完后再重新汇集、再次统筹。这种模式不仅极其缓慢，而且体验糟糕；一个真正意义上的集群架构应该由完全自治的个体组成。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Yes. Yes. And therefore it is a "narrow place. This is a "bottleneck". THERE ARE one main one, he coordinates everyone subordinates, then to them need again to gather, and then again to re-coordinate . This is slow, this is bad, a real swarm should consist of individuals.

</details>

### 集群冗余度、任务设计与商业化想象

**Speaker A**: 是的，我同意这一点。但我认为还有一个问题很值得探讨。打个比方：就像你什么时候会使用紧凑型存储，什么时候又会使用 RLM 模型一样。在很多场景下，RLM 能够解决比简单压缩更困难的任务，但大多数情况下你依然会优先选择压缩方案，因为它更便宜、更迅速。我认为在智能体集群（Agent Swarms）的语境下，类似的情况正在发生：我敢说整个集群里大约有 95% 的智能体几乎是完全无用的，它们所探索的方向不过是在白白燃烧 token，而在这套系统中未必非得如此。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, yes. Well, I agree with that, and still I think there is a question worth asking to discuss. Let me to give an analogy: when you use compact storage , and when is the RLM model? THERE ARE many situations where RLM can decide a more difficult task, than compaction, but you would you prefer compaction in in most cases, because it's cheaper and rather. And I think that in in the context of swarms agents is happening something like that, I pretty sure that about 95% of the swarm is absolutely useless, or what he investigates, is just burning tokens, while in this system may not Exactly.

</details>

**Speaker B**: 我不太确信。我的意思是，也许真实工作场景也是这么运转的：每个人都有自己的活干，Jira 看板上排满了任务。我认为在特定抽象层次上，问题的定义方式恰恰就是如此，对吧？也就是说，如果你面对一个搜索探索类任务，派出一大批子智能体去执行，过程里自然会充斥着大量的无用信息，对吧？最终你只会得到一个有效的搜索答案并以此为基准继续分支演化。但这本身就是有意为之的设计，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: I am not assured. I have on mean, maybe this this also applies case. Everyone has a job. THERE ARE board in Jira. I think that at a certain level, precisely are formulated like this problems, right? That is, if you have search task and you create a pile subagents for him implementation, there will be a lot of useless information, right? THERE ARE one answer search, which you receive and from which branch out. But this is deliberate understood, right?

</details>

**Speaker A**: 没错。但关键在于，针对什么样的问题才适合采用什么样的架构设计？理论上，OpenAI 完全可以把这种能力打包成一个名为“Swarms”的 API 接口开放出来，对你说：“把任何棘手问题扔给它，我们就能给你一个解答。”当然，它大概率会被命名为 Pro 版之类的。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. But there is question about what appropriate use for the solution of which problems, that is, which design? You know, in theory, OpenAI can package this into an API, call "Swarms", give to you and say: " Direct this to any what a problem, and we "We will give you a solution." But , perhaps it will be be called Pro.

</details>

**Speaker B**: 是的，也许为了拿到这个结果你得砸进去 4000 万美元，但这本身就极具吸引力。能有能力直接砸 4000 万美元去攻克难题，这太令人振奋了。但我们行业仍需在该领域投入大量研究，去弄清楚哪些是必需的、哪些是我们真正想要实现的。我们究竟需要怎样的架构设计？我们显然不希望所有场景都盲目套用集群，那么边界究竟该划在哪里？智能体自身是否具备自主设计架构、自行决断的能力？

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Maybe you will have to pay 40 million dollars for the result, but that's it fascinating. I will say that this is very exciting— to be able to throw 40 million dollars to solve problems. But still need to spend a lot research in this field industry to understand what is necessary and what we we want to do. Which Do we need design? We probably don't We want everything to be swarm, but where to spend border? Can the agent design it yourself whether to decide etc.

</details>

### 开放式探索（Open-endedness）与基础科研的本质

**Speaker A**: 对。顺便问一个快问快答：针对这一块你有什么看法吗？或者说，你们当中有多少人曾将“开放性”（open-endedness）作为一个通用问题类别进行过深入研究？所谓开放性，就是没有任何提示和外力引导，仅仅是任由其自主“向前演进”。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. And also, just quick questions, about anything case, do you have opinion on this. Or many of you investigated openness as general category problems? It means without tips, just " forward".

</details>

**Speaker B**: 我研究过一些。嗯，今年夏天我在 Sakana 待过一段时间，就在读博前后的那个阶段，他们在这方面投入了非常大的精力。而且我觉得很多人，包括 Recursive Superintelligence 那边的人也在做这个。

<details>
<summary>Original English</summary>

**Speaker B**: A little. Um, I was at Sakana during the summer, immediately after or, it seems right in front my graduate school, and they are very much on top of this are working. And I think, that many people even in Recursive Superintelligence.

</details>

**Speaker A**: 哦是的，没错。那是由 Richard 创办的公司……等等，也许它们其实是同一家公司？我有点记不清了。Tim Rocktäschel 也在那里吗？

<details>
<summary>Original English</summary>

**Speaker A**: Oh yes. Yes. Therefore, Richard's company, and then...but wait, maybe it's one and the same the company itself. I am not I remember. And Tim Rockell also? OK.

</details>

**Speaker B**: 对，他是主要联合创始人之一。他曾是 Google 开放式研究（open-endedness）部门的负责人。

<details>
<summary>Original English</summary>

**Speaker B**: He is the main one. Co-founder. He department head open-endedness on Google.

</details>

**Speaker A**: 明白了。

<details>
<summary>Original English</summary>

**Speaker A**: Yes.

</details>

**Speaker B**: 因此，我倾向于将开放性问题视作某种类似于未解数学难题的存在。这种措辞或许有些奇怪，但我认为人们在应对这两种问题时的许多方法其实是相通的。演化搜索（Evolutionary search）在本质上就非常类似于放出一大群智能体集群，寄希望于它们能碰撞出某些有趣的东西——就像一两年前的 AlphaEvolved 以及其他类似研究所做的那样。

但我总觉得……我不太确定你指的是不是这个意思，但在开放式搜索任务中有一点始终不够清晰：我们究竟是把它们全部塑造成极其困难的未解难题，还是塑造成目标本身已经明确的问题？如果连目标都不明确，我依然看不出它们的核心价值所在。也许你的观点有所不同，因为我对这块涉猎不深；但至少在 Sakana 工作的那段时间里，我个人的直觉是，我们归根结底还是希望以类似 OpenAI 攻克纳维-斯托克斯方程的方式去解决问题。我们仍然希望在特定方向上施加大量驱动力，以便推进到足以诞生有趣成果的临界点。

<details>
<summary>Original English</summary>

**Speaker B**: Therefore, I think the problems openness I I'm considering something. Similar to unresolved mathematical problems. Maybe this is strange. Way of wording, but I think that many methods of doing so how people approach them, similar. Evolutionary search very similar to launch swarms of agents in hope, what will they come up with something interesting is that made Alpha Evolved and some other works of the year or two ago. But I I think maybe not. Not at all...I don't sure, did you have this is meant, but not very clear in search tasks open type: or we formulate them all as unresolved, very a difficult problem, or as such, where the goal Got it? If it is not yes, I still don't know, in why theirs? Value. Maybe in you have a different opinion, because I I don't have much. Views on this, but at least for a while I have jobs at Sakcon the impression was that we are still in the end we want to approach things like, say , OpenAI approached Navier-Stokes. We we still want... We have a lot pushing in a certain direction, so that to reach that point when we get something interesting.

</details>

### 从目标驱动到无目标的自我发现

**Speaker A**: 我的理解是，这很像是基础科学与应用科学之间的分野。基础科学纯粹是“为了研究而研究”，你只是想更透彻地理解客观事物，甚至根本不知道它未来会不会有任何实际应用价值。而应用科学则完全不同——你有着极其明确的目标，你在千方百计地最小化损失函数。正因如此，对于人们下的那些巨额赌注，我常常会想：如果不给任何 prompt 会怎样？

你可以想象这样一个场景：你面对着整个庞大的智能体集群，只是随意地走过去打个招呼：“嘿，你们在捣鼓什么呢？”“我挺喜欢你们现在做的方向”，然后你再挑选出：“我看明白了，这是个有趣的问题。”然而，至少在我当时经历中，搞开放式探索的人面临的最大难题正是：你最终究竟该如何做出筛选决策？如何从浩如烟海的产出中精准提炼出真正有价值的东西？因为虽然智能体或许能自己构想出目标，但在许多类似案例中——比如他们搞出来的那个叫 Fugu 的东西，看起来就像是一种路由模型（router models），而它的初衷至少是：“让我们选择一个任务，并在其中找到最优解”，在这里就变成了“针对该任务选出最合适的模型”。

<details>
<summary>Original English</summary>

**Speaker A**: My version is because it is possible division between fundamental and applied science. Fundamental science—this is research for the sake of research. You just want better understand things. I I have no idea if it will be from this at all any application. But I I mean, what...? Applied—you have target. You are trying minimize losses somehow, you know? And because I I really think so. Regarding large bets that make people: what if there wasn't no prompt? I see, you know, you just choose. You just are you in this swarm of things and say: "Hey, what's up with you? Guys?" "Me?" I like what you work", and you you just decide: "I I see, this is interesting. Problem". The largest the problem that...and, maybe there is a clear the way to this, but at least when I was there, the biggest the problem we had people with openness, was: how in the end make a choice at the end? How to isolate interesting things? Because when no, well, maybe the agent invents a goal, but in many cases like theirs there is something called Fugu, It seems like this is...this something like router models, which was, at least, inspired by the idea: "Let's choose a task where we can find the best solution for something". In in this case it's like choose the best model for this tasks. Ahem.

</details>

**Speaker B**: 你可是第一个把路由模型和开放式目标联系在一起的人。

<details>
<summary>Original English</summary>

**Speaker B**: You are the first person who connects routing models with open purpose.

</details>

**Speaker A**: 哈哈，不不。不过我对这件事记忆犹新，因为在我看来，开放式探索的核心难点往往在于：如何在庞大冗余的废弃产出中进行过滤，找出真正的明珠？针对开放式目标的解决方案，难道就只是放任模型永无止境地运行下去，以极高的吞吐效率不断生成数据？如果提出这类设想，或许确实很酷。对我而言，这极其迷人的一点在于，它构成了与几乎所有主流机器学习范式的鲜明对抗——在传统机器学习中你永远都有一个明确的目标，而在这里，核心却是“缺乏目标”。

<details>
<summary>Original English</summary>

**Speaker A**: No, no. Yes. But I, I, I remember this, because I think that with open-ended the problem is usually in because among huge body waste filter and find the real ones pearls? And, like, solution for open-ended goal—this just allow models to work forever and, like, generate data from extremely high productivity. Asking things like, maybe that's cool. For me it is very interesting as a counterweight almost everything machine learning, where you have a goal, and here—lack of purpose.

</details>

**Speaker B**: 是的。或者说，更像是一种“未定义的目标”。也就是当你琢磨着：“嗯，这个目标怎么样？”然后你会觉得：“好吧，行得通。”随着你进一步深入探索，你发现这确实是个引人入胜的目标——因为正如你所言，能够自主发现并定义自身的目标函数，就像 Jeb 发现目标函数那样……

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Or, or maybe, undefined goal, when you think, "Well, "What about this goal?" And you're like, "Well, okay, "possible". And then you you explore more and you find that this interesting goal because I I think that finding own target functions—as you said, Jeb found objective

</details>

<!-- chunk 10/13 -->

### 学术界开放探索与工业界高薪现实：研究生的现实抉择

**嘉宾**：……函数，这非常有趣，而且此前没有人深入调查过。

<details>
<summary>Original English</summary>

**Guest**: ...function, which was interesting and what no one investigated.

</details>

**主持人**：我认为这很像你给研究生的建议：如果你想做目标开放的探索性研究，那就留在大学里；但如果你想最大化收益，比如避免沦为永久性的底层阶级，那就去工业界实验室，对吧？

<details>
<summary>Original English</summary>

**Host**: I think it looks like your message to graduate students: you stay in university, because do you want to do open purpose. If you want, you know, maximize profit and, like, avoid status permanent subclass, then you go to laboratory, yes.

</details>

**嘉宾**：是的，这很有意思。其实我平时并不常听到这种讨论。我的意思是，我来自美国东海岸，那里的氛围完全不同。但是当我来到这里（西海岸/硅谷）时，这始终是大家讨论的核心话题：“不这样做的话，你连房租都付不起；伙计们，物价飞涨正把大家逼走。”好吧，大概就是这样。

<details>
<summary>Original English</summary>

**Guest**: Yes. This is funny. Me I don't think I do often. I hear such discussions. I I mean, I'm from East Coast, it's completely different there atmosphere. But when I I'm coming here, this is always the main topic discussions. You will not be able to pay. for rent, without doing this. You are being pushed out because prices, guys. Okay. So, yeah, that's it. all.

</details>

### Ultra的自动化研究与“缺乏管理的天才”

**主持人**：嗯，我不知道你是否想继续……讨论到这里够了吗？是否需要聊聊你在博客里提到的那些“缺乏管理的天才”？

<details>
<summary>Original English</summary>

**Host**: Hmm, I don't know if Do you want to? this is enough it is important that to talk about " poorly managed "geniuses" that you are talking about remembered.

</details>

**嘉宾**：不，不，这只是你从我博客里看来的一个点，不过我可以稍微提一下这个话题。是的，他们在博客文章里写到了这一点，我也和他们交流过。Ultra最有趣的研究成果之一，在于他们赋予了系统自主开展数据研究的自由，只需要极少的人工干预，甚至完全不需要人工干预。它直接就能自行运转……

<details>
<summary>Original English</summary>

**Guest**: No, no, it's just one from your blogs, but I I'll touch on this topic. Yes. Yes. So, they did it in their blog post, I also talked to them about it. One of interesting results Ultra is that they actually gave he is free to automated data studies from minimal human intervention or without it at all . It just does

</details>

**主持人**：是的，这就是自动化研究（auto-study），它的开放程度更高一些，而且这种开放性存在不同的层级，我对此表示赞同。是的，这与设定具体明确目标的自动化研究截然不同，这里更像是在说——“尽管去探索一些东西吧”。不过你知道，这很酷，他们正在为对此感兴趣的人推进这项工作。既然我们已经聊到了这里，你对Sakana AI有什么看法？除了他们是“来自日本的团队”之外，他们到底在做什么？

<details>
<summary>Original English</summary>

**Host**: Yes. So this is auto-study, which there is a little more open, and there are different levels of this openness, I'm with this I agree. Yes. This is different. from auto research with a specific purpose, here—just do something . But you know, that's cool. They are working on it. for those who need it interesting. Since we are already talking about they talked about it, what What is your opinion about Sakana? What they do, except that they, well, "those" "You are from Japan?"

</details>

### Sakana AI：从DeepMind演化传统到日本本土化研究

**嘉宾**：是的，没错。实际上我非常喜欢在那里工作的人。我认为他们拥有一支规模很大且非常聪明的团队。这在逻辑上非常顺理成章：他们是从Google DeepMind（GDM）之前的团队中独立出来的，那个团队可能也一直在从事类似的、具有开放式结局的演化风格研究。根据我对他们的了解，我很欣赏的一点是他们也有过挫折——我不记得确切是什么时候了，但好像是关于科学家……不，是GPU集群核心的问题。是的，人们对此往往难以释怀。

<details>
<summary>Original English</summary>

**Guest**: Yes. Yes. Yes. Me actually very like people who They work there. I I think they have a lot of and very smart team. This is quite logically. They separated from of the previous team in GDM, which, probably, also was engaged in similar research in evolutionary style with open end. What I liked it in in my experience there, it's what they had and failure, no more I remember when, but I I think regarding scientists. No, it was the GPU core. Yes. People don't can they do this to forgive.

</details>

**嘉宾**：是的。至于他们的“AI Scientist”，外界存在一些批评声音，对于这些批评……因为我自己并没有亲自去做这个方向，所以对此不便发表意见。但总的来说，我为什么关注并喜欢他们呢？因为他们更像是一个纯粹的研究实验室。他们绝对没有跟OpenAI或Anthropic处在同一个竞争维度上，这一点毋庸置疑。我觉得很明显的是，至少在我在那里的时候，他们并没有去搞一个面向大众的庞大竞争模型。但在我看来，他们在某种程度上扮演着博士实验室（PhD-laboratory）的角色，这非常酷。

<details>
<summary>Original English</summary>

**Guest**: Yes. Yes. And regarding their AI scientist, there is some criticism with which I...because I don't I am doing it, I have there is no opinion from on this occasion; but In general, what do I care about them? I like it, that's it. that they are more similar to research laboratory. They definitely don't work in on the same plane as OpenAI or Anthropic, it is definitely. I think quite obvious, at least when I'm there was that they didn't have large model- competitor, which would use everyone. But to me it seems that they to some extent function as PhD- laboratory, and this steeply.

</details>

**嘉宾**：而且在我看来，David Ha确实非常通情达理且务实。我认为他非常清楚日本市场在AI领域有些与众不同，他们的目标受众也与我们这里习惯的受众略有不同。不过话说回来，我喜欢他们的尝试……当人们审视他们的研究时，可能会觉得有点特立独行，而我正喜欢这一点。我认为这个领域理应出现更多这种与众不同的奇思妙想。

<details>
<summary>Original English</summary>

**Guest**: And David Ha, as to me, really very reasonable. I think he understands well that Japan market somewhat differs in in terms of AI, and their target audience a little different than the one before which we are used to here. But yes, I I like that they take...their research a little strange to me, when people are on them watching, you know, and I like it. I think this is there should be more eccentricities.

</details>

**主持人**：是的，完全正确。你提到“另一个市场”，是指类似于企业端（ToB）的细分领域吗？

<details>
<summary>Original English</summary>

**Host**: Yes. That's right. That's right. Uh, and you say "another" market", it's something on kind of corporate segment?

</details>

**嘉宾**：那里的整个运作方式稍有不同：商业交易如何达成等等。他们有……也就是说，我认为他们的主页首先是日语的，而且他们拥有专门针对日语优化的专业模型。你以前不知道吗？

<details>
<summary>Original English</summary>

**Guest**: The way everything works there, is slightly different: how deals are made and so on. They have... that is, I think that this page first in Japanese, but they have model, specialized for Japanese language. Didn't you know that?

</details>

**主持人**：我不知道你知道这个。我在那个团队里也有私交很好的朋友，所以我了解这一点。

<details>
<summary>Original English</summary>

**Host**: I didn't know what you knew. I also have personal friends in this team, and I know it.

</details>

**嘉宾**：所以就是这样。甚至从文化沟通的角度来看，回答也是专门为此调优的。这绝不仅仅是在跑分基准（benchmarks）上表现先进那么简单，而是一个在文化上深度适配的模型，他们有配套的聊天界面和其他所有功能。

<details>
<summary>Original English</summary>

**Guest**: So there it is. even from the point of view how you communicate culturally, uh, you know , answers are tuned specifically to it. It's not easy. something advanced than benchmarks. It culturally adapted a model for them, and they they have chat and everything else.

</details>

### Kimi的架构创新与中国AI实验室的崛起

**主持人**：不过，顺着你的观点，这其实也关系到教育模式应该是什么样的问题，有人就想以这种方式工作。他们非常契合“博士式实验室”的运作范式：“做你想做的事，为什么不呢？我们有资金，去做你的探索研究吧。”另外，听说Kimi的发展也相当不错，这很棒，真为他们感到高兴。

<details>
<summary>Original English</summary>

**Host**: But, uh, supporting your opinion, you know, there is also the question of how what education should look like, and someone wants to do this to work, and they very similar to PhD- "format laboratory" Do your thing, why not? ". We have money, do your job research. Oh, they say it's Kimmy fine, also. That's not bad. Oh, that's it. Glad for them.

</details>

**嘉宾**：嗯，是的。提到Kimi，就好像是另一个例子——你知道，一个研究生独立出来，然后说：“我有这个Kimi Delta Attention架构想要攻坚。”然后不知怎么搞的，居然一举做成了单次推理/一步到位（one-shot）。我至今仍觉得这不可思议。

<details>
<summary>Original English</summary>

**Guest**: Um, yes, I mean , and you know, speaking of Kimmy, yeah, like another one, uh- uh, you know, just a graduate student who separated and this one: "I have this Kimmy Delta attention, over which I want work". Uh, and somehow managed to make a one-shot. I still don't understand this. .

</details>

**主持人**：是的，没错，他确实极其出色。至少据我了解是这样。我认为总的来说，很多中国实验室都做出了非常非常出色的成果。

<details>
<summary>Original English</summary>

**Host**: Yes. Yes. Well, he incredibly cool. Ahem at least as far as I understand. I think that in general many Chinese laboratories have done really very cool work.

</details>

**主持人**：那么，你对智能体群（Agent Swarms）——比如Kimi的智能体集群怎么看？

<details>
<summary>Original English</summary>

**Host**: Yes. Like this What are your thoughts on swarms? Kimmy agents?

</details>

### 多智能体集群的系统设计难题与动态工作流的局限

**嘉宾**：好的。我想说的一点是，OpenAI此前并没有直接押注智能体群路线，这显然是一条正确的思路。我们需要冷静思考：如果没有非常、非常精妙的顶层架构设计，单凭智能体本身根本做不出什么名堂，而这种系统设计能力我认为目前还没有谁真正掌握。有些成果并非理所当然、唾手可得的。例如，智能体群的设计决不能被视为理所当然的事情。并不是说GPT-6 Astra只要超级聪明，然后智能体集群就能自然而然运转起来。它们显然是需要专门训练的……请注意，之前Hugging Face的事件正是他们在训练系统以形成类似集群的协作行为。好吧，我认为如果能够投入4000万美元去攻克一个尚未解决的难题，那确实很了不起。而关于Kimi的多智能体群，至少从我读到的资料来看，它看起来很有趣，但我不知道它是否真的能够解决全新的问题。

<details>
<summary>Original English</summary>

**Guest**: Yes. Um, one thing I I would say this is what OpenAI would didn't do anything with mine a swarm of agents, it's clear the right way. We need to think about this. yes: nothing in particular without very, very smart design frame, which I don't I think someone has What is given is not given like that. easy and free. For example, the design of the swarm agents—this is not what can be perceived as due. It's not like that. GPT-6 Astra simply super smart, and then she just has swarms have started agents. They are clearly trained...I have Mind you, the Hugging incident Face was theirs training the system, so that it is like a swarm. Well, I think they clearly did something very Okay, if possible spend 40 millions of dollars and to resolve an unresolved issue problem. And I think, What's with this thing about swarms of agents from Kimmy, at least from what I read, it looks like interesting, but I don't know, can this be solved? something new.

</details>

**主持人**：是的。他们对外宣称这能生成电子表格。他们只是简单地说：“看，这里有一个集群在做事情，这很酷。”

<details>
<summary>Original English</summary>

**Host**: Yes. They just they said that it creates electronic tables. They simply said: "Here is a swarm, which does something, and that steeply".

</details>

**嘉宾**：但我具体想谈谈动态工作流（dynamic workflows）。事实上，我认为动态工作流的发布在某种意义上是失败的。我不知道你怎么看，但在我看来，据我所知，人们往往在使用方式上存在偏差，或者说它的成本实在太昂贵了。

<details>
<summary>Original English</summary>

**Guest**: But I will say this. namely about dynamic workflows. Actually, I think that release of dynamic workflows was a kind of failure. I don't know what you mean by that. you think, but how me, as far as I am I understand, by him are using it wrong often, or it's just too expensive .

</details>

**主持人**：成本确实太高了，这简直就是极端写代码（ultracode）。它实际上就像是在说“接管我的银行账户控制权”。它根本行不通。我亲自尝试过，根本不是那么回事——再次重申，我并不是OpenAI的狂热拥趸，但我认为他们的成果确实令人印象深刻。他们不知用了什么方法，硬是让这群智能体朝着既定目标协同推进，这确实极其困难。

<details>
<summary>Original English</summary>

**Host**: This is too expensive. This is ultracode. It actually like "take my bank under control ". It doesn't work. I tried it, and it doesn't work like— again, I don't OpenAI's biggest fan, but I think that what they did, very impressive. They somehow somehow managed to force this swarm move towards goals, and yes, it's very difficult.

</details>

**嘉宾**：当然。因此多智能体集群的效率正是这里的核心目标函数，对吧？这里面到底产生了多少无用功？一大堆废话和垃圾信息。

<details>
<summary>Original English</summary>

**Guest**: Of course. So efficiency multi-agent swarm -it the objective function here, Yes? How many here? useless work, right? A bunch of junk.

</details>

**主持人**：是的，我也这么认为。我们总觉得智能体群自然而然就该得出确定的答案，但这种能力绝不是理所当然就有的。

<details>
<summary>Original English</summary>

**Host**: Yes, I am. I think so too. I think we perceive as it is proper that means for the swarm to come to a certain answers. This is not that. what can be perceived as due.

</details>

**嘉宾**：是的，确实如此。

<details>
<summary>Original English</summary>

**Guest**: Yes. Yes.

</details>

### 合作型智能体范式转移与对Gemini、AlphaGeometry的客观评价

**主持人**：我们之前和Noam Brown录制过一期播客，他的核心理念可以总结为：过去我们研究的是大量相互博弈竞争的智能体（competitive agents）；而现在，我们转向研究协同合作的智能体（joint/cooperative agents），这就是现在所谓的智能体集群（swarm）。对了，我还想顺便问一下：你对Gemini怎么看？我认为他们过去也是黄金标杆。曾经有一段时间，他们让智能体进行超长时间的深度推理。现在谈论并思考这些，是不是已经过时了？

<details>
<summary>Original English</summary>

**Host**: We recorded a podcast with Noam Brown, and all his concept came down to the fact that we worked on many competitive agents. Now we working on joint agents, and this is now called swarm. Yes. I would like to quickly to ask. What are you Thinking about Gemini? On I think they are too were golden standard. There was a time, when they forced agents to reason a long time, and yes, I mean, Is this too much? long time ago, to talk about this think?

</details>

**嘉宾**：不，不，不。我认为Gemini在某种程度上被略微高估了。当然，我必须声明，我并未在这些公司中的任何一家工作过，所以大家不妨持怀疑态度来看待我的观点，好吗？我的意思是，关于智能体系统你完全可以有自己的见解……不过，请允许我先说明：那项工作确实令人印象深刻。我认为他们证明了，在模型本身精度还不算太高的时期，需要通过耗费时间来进行推理。他们非常明智地利用了这套工具集。我至少还记得AlphaGeometry——它似乎比那还要早一年推出，但它极其出色，令人惊叹。他们榨干了这套系统的极限潜力并加以开发……老实说，这给我留下了极其深刻的印象：奥林匹克数学竞赛级别的成就。

<details>
<summary>Original English</summary>

**Guest**: No, no, no. I think that Gemini a little overestimated, again Yes, I must point out, who did not work in none of these companies , so accept this skeptical, okay? I mean, you have own opinion about agent systems, and you you know, it was But, um, let me tell me first that. This work was truly impressive. I think they showed, that took time when the models were not yet so accurate. Yes. And they managed to do very to approach wisely what this one does toolkit. I I remember at least so, for example, AlphaGeometry. It seems that this It was a year before that. But it was very steeply. They took, um, they squeezed out of this is the maximum and developed, well, I don't know . To be honest, I don't I am very impressed. Olympic mathematics.

</details>

**主持人**：在我看来，Google DeepMind（GDM）似乎显得有些落寞失意。每一个和我聊起GDM的人……

<details>
<summary>Original English</summary>

**Host**: Me It seems that GDM is a bit sad. Everyone, from who I was talking about GDM,

</details>

<!-- chunk 11/13 -->

### 大公司的官僚主义与工具生态

**Speaker A**: 大家基本上都持差不多的观点：那里的官僚主义实在太严重了。就算他们拥有顶尖的人才和充足的资源，几乎能做出任何东西，但在那样的环境下，我也不知道……当他们身处其中时是无法想明白的。我倒不是对它有什么偏见，比如像 Antigravity，但我身边根本没有人在用。我自己尝试过一次，完全看不到有什么理由非要切换过去。而且我认为，他们为此内耗斗争正是其中的部分原因。

<details>
<summary>Original English</summary>

**Speaker A**: ...have approximately the same opinion: there's too much bureaucracy. Let there be, like, they have talents and resources to make almost everything, but I don't know, while they're at it, won't understand... I have nothing against it. Antigravity, for example, but I don't—I don't know anyone who would use it. I tried once and I don't see any reason to move on to it, and, I think, from some of the reasons they have for this are fighting. So yes.

</details>

**Speaker B**: 确实。你看，很多人曾经长篇累牍地批评 Meta，直到他们真正开始拿出硬核产品。我认为 Google 现在经历的恰恰也是这个阶段。

<details>
<summary>Original English</summary>

**Speaker B**: Well, you know, many people criticized Meta for a long time, until they started to produce products, and I think Google now is experiencing exactly this phase.

</details>

**Speaker A**: 没错，为了生存，你总得保持竞争力、维持运转……

<details>
<summary>Original English</summary>

**Speaker A**: Yes. And, you know, you need to stay afloat, and...

</details>

### 投机性预执行与“失控环境中的天才”

**Speaker B**: 我想把话题转回到你整体的想法上。我们可以聊聊投机性 PTC（Speculative Programmatic Tool Calling / PCC），也可以聊聊“失控环境中的天才”（geniuses in uncontrollable environment），或者把这些都抛开，随便聊点别的也行。

<details>
<summary>Original English</summary>

**Speaker B**: I want to go back to your thoughts in general. We can talk about speculative PCC, about "geniuses in uncontrollable environment", or just throw everything away and talk about anything else.

</details>

**Speaker A**: 行，那我们稍微聊聊“失控环境中的天才”吧。关于投机性 PTC，我只简单评论一句：这是一个极其简单的想法。几乎显而易见就应该这么做，本身没有什么特别好深入讨论的。我认为它完全值得直接用在代码生成上，用在任何软件智能体调用的场景中——比如 RLM 或者 CodeAct——这完全就是不假思索就能想到的显然之举。

<details>
<summary>Original English</summary>

**Speaker A**: Okay, let's talk a little—let's talk about "geniuses in uncontrollable environment". Only comment on speculative PTC: this is a very simple idea. It is almost obvious that this had to be done, and there is nothing here especially to discuss. I think that it's just worth using for encoding, for any software agent calls, like—so RLM or CodeAct—it's like a "no-brainer", the obvious thing.

</details>

**Speaker B**: 对那些还没读过这篇内容的人来说，能不能用一句话概括它的核心要点？

<details>
<summary>Original English</summary>

**Speaker B**: Which, you know, is for those who haven't read, what's the point in one sentence?

</details>

**Speaker A**: 道理其实很简单：当模型在编写代码时，甚至在写完之后，很多工具往往是按部就班地串行执行，模型必须在原地等待它们返回。因此你完全可以提前把它们预先启动：如果你能编译这段代码，即便有未定变量或类似情况，你大概率也能提前预测……通过静态分析假设来做投机执行。

<details>
<summary>Original English</summary>

**Speaker A**: All simple: while the model writes code, or even after it finished it, a lot of tools work sequentially, or one has to wait on them. So you need to launch them in advance: if you can compile this code, you probably can understand, even despite the variables and such else, you can find out how to statically analyze the assumption.

</details>

**Speaker B**: 没错。有人曾经向我指出，学术界尤其是编程语言领域的专家们，其实有一套非常精妙的做法来实现这一点。所以说不定哪天我也会在这方面花点心思深入研究。不过很多时候可能需要更换编程语言，因为在 JavaScript 或 Python 里你很难直接做到这一点。

<details>
<summary>Original English</summary>

**Speaker B**: Yes. There is this—well, someone pointed out to me that actually scientists, especially experts in programming languages, have very cool ways to do it, so, you know, once upon a time, maybe I'll work on this. Mostly it is necessary to change the language, so that in JavaScript or Python you can't do this.

</details>

**Speaker A**: 对，对，对。比如像 Haskell……还有什么来着，不是 Lisp 的那种常规函数式语言。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, yes, yes. Well, for example, Haskell, yes, um, what is this, which is normal, which is not Lisp.

</details>

**Speaker B**: 是 Lisp，还是 OCaml？

<details>
<summary>Original English</summary>

**Speaker B**: Um, Lisp, or OCaml.

</details>

**Speaker A**: OCaml，或者任何能够将计算过程管道化、流水线化的函数式语言。如果你想在 TypeScript 里做这个，也可以用 Effect-TS。

<details>
<summary>Original English</summary>

**Speaker A**: OCaml, any functional language where you can pipeline this, therefore Effect-TS if you want to work with TypeScript.

</details>

### 模型能力的锯齿状特征与工程瓶颈

**Speaker B**: 好，那我们可以切入图表了。本质上，你的核心论点是什么？在我看来，如果做个转述的话——也许我漏掉了一些细节——大概意思是：去打造更好的工具；或者说，如果肯下功夫做工程，现有的模型其实能爆发出远超现状的能力，所以这本质上是个技巧和工具链的问题。

<details>
<summary>Original English</summary>

**Speaker B**: Okay, we can move on to the diagram. What is, in essence, your common thesis? That is, um, it looks like this to me, of a kind, paraphrasing, but maybe I skip something, like: work on better tools, or, you know, your models are actually capable of more if you make an effort, so this is a skill problem.

</details>

**Speaker A**: 没错，确实是这样。实际上，我想要看到的是另外一件事。我很认同大家高度关注所谓的“锯齿状智能”（jagged intelligence），因为这描绘了一幅广阔的图景，展示了如果我们真正集中精力能做到什么。但我更希望——也许学术界有人能做这件事——大家能真正坐下来认真思考：哪怕是用当前最顶尖的模型 Astra，让它在整整一个月内持续、稳定、高质量地执行某项工作，它依然做不好。

而在我看来，这是一个很蠢的问题。我发自内心地相信我们完全有能力解决它。你根本不需要成为什么顶尖前沿实验室，也不需要为了公司 IPO 去搞那些花哨博眼球的名堂。我认为这些模型已经足够聪明了，就算用最笨的方法，这也纯粹是一个工程技巧的问题：你完全可以让模型表现得像一个正在干活的 18 岁高中生一样出色。我觉得我们现在做不到这一点简直荒谬。

其中一部分原因在于，语言模型当下的交互形式并不适应这种长程工作流。但我认为完全可以在模型外围构建工具来达成。撇开 RLM 以及关于该用何种抽象的种种争论不谈，我坚信有人能做出这样的工具来实现它。也就是说，你问该怎么做？那就是去执行漫长而简单、但要求极高可靠性的任务，并稳定地交付。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, exactly. Actually, I mean, there is one thing which I want to see. I appreciate the great focus on the "uneven" jagged intelligence, because it draws a wide picture of what we can do if we indeed focus, but I would want—and maybe someone in academia would do it—really, just sit down and think: even taking current leading models like Astra, they are not good enough at, let's say, executing some work during the month consistently and qualitatively.

And I think that this is a silly problem. I sincerely believe that we can solve this. You don't have to be an advanced laboratory and do all these quirky things for your IPO. I think these models are so smart that even if it is a silly way, I think it's truly a skills question: you can force the model to work just as well as, let's say, some 18-year-old schoolboy performing work. I believe it's absurd that we can't make this happen.

And partly the reason is that the language model format is not very adapted to this. But I think tools can be built around this to do it. And ignoring RLM and all sorts of questions about what abstractions we ought to use—I just think that someone can create a tool that will do it. That is, you ask what to do? Perform long, but simple tasks, and do it reliably. This is an example.

</details>

**Speaker B**: 这和你最喜欢的公司 Harvey（利用大语言模型做法律业务）有什么区别吗？核心差异在哪里？

<details>
<summary>Original English</summary>

**Speaker B**: Therefore, is this different from, you know, we'll take your favorite company, Harvey, for example, that uses LLM for legal work, or what's the difference?

</details>

**Speaker A**: 我觉得大体方向是一致的，只不过瓶颈并不在于具体的垂直领域法律知识之类的，老实说我也说不准。这么说吧，现有的典型模式通常是人们拿到模型后，自己搭建流水线或定制系统，强行让智能体去持续完成他们指定的某些任务，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: Well, I think that it's something like this, except the bottleneck was not certain legal knowledge or something like that—honestly speaking, I don't know. Let's say this. Apparently, examples are because people can take models, build conveyors or anything and force an agent to constantly perform any tasks they want, right?

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

### 通用辅助系统的形态与泛化能力迁移

**Speaker A**: 举个例子，如果我想要一个通用的系统，我希望和它的交互就像和一个实习生交流一样，随口让它去调查某件琐碎的小事。比如做一些相对简单的自动化调研，并不需要它去发现什么颠覆性的崭新解法，但至少能把任何问题中较为轻量、繁琐的环节自动化优化掉。然而现在的方案往往过度面向机器学习或者垂直场景本身。

可能我表达得不够清晰，但在很多人的日常工作流程中，往往存在不少只需写一小段代码就能快速自动化某个工具的场景，比如检索科研论文之类的。但现在人们通常要么专门做一个垂直特化的智能体，要么仓促写一段脚本挂成 Slack 机器人。但在我看来，应该存在一种标准形态的工具，你只需把它接入进来——它不需要专门为了搜论文而定制开发，你只要告诉它“帮我把这个找出来”，然后把它连入正确的环境即可。

我真正想表达的是：现存大量简单的事情都可以被自动化。关于“能力过剩”的假说或论点在于，即便基础模型研究现在暂停，现有的模型依然具有巨大的潜在影响力。从某种意义上说是这样，但我呈现的核心观点在于：既然模型的能力存在明显的锯齿分布，比如它们在编程和数学方面的能力极其突出、不成比例地强大，这意味着我们完全可以把这些卓越的能力迁移并应用到许多其他领域。

这就好比我们找来一个在国际数学奥林匹克竞赛中拿到金牌的人，把他们的解决问题能力应用到各种不同行业的难题上，他们完全有能力把事情理清楚。但我不敢确定这是否同样适用于大模型。例如在 GPU 代码优化中，有一个非常有趣的问题：如果你把模型中关于 GPU 编程的所有训练数据彻底抹去，但它依然保持像现在 Astra 一样的强大通用推理能力，它还能很好地优化 GPU 内核吗？它能否仅凭上下文学习掌握所需的知识，然后构建出某种流水线或方案来完成优化任务？

我认为这里存在一道鸿沟：如果把一个智力水平和 Astra 相当的人类拿来对比，人类能做到的事情与 Astra 能做到的事情之间存在差距，而这种差距很大程度上是由工具支持决定的。我认为通过工程和工具，我们其实能让模型极大程度地逼近人类的这种能力。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. So, for example, if I wanted a general system with which I could communicate as with an intern, and just ask her to investigate some little thing. Perhaps an example: these are pretty simple automated research, not having to search for some extremely new solutions, but at least optimizing all the easy parts of whatever problem. They often appear too oriented towards machine learning and things like that.

But yes, I don't know. Maybe this is not very clear, but in workflows of many people there are moments when it would be easy to quickly write code for a specific tool to automate this. Some examples are: search automation for scientific articles and something like that. But usually people create a specialized agent to help them with this, or they write in a hurry tool code and run it as a Slack bot or something. But it seems to me that there is some standard format, such a tool where you just connect it—it doesn't need to be developed just for searching articles, you just tell it: "find this for me", and connect it to the right environment.

What I'm getting at is that, in my opinion, there are many simple things that can be automated. And is this a hypothesis or argument about an excess of capabilities, that even if we took a break, current models would still have a huge impact? In a sense, yes. I think what I present in its simplest form is this: it indicates that we have uneven, jagged intelligence in many things; for example, models are disproportionately best in programming and mathematics. It means that we can transfer these abilities to many other areas.

Therefore, for example, if we take someone who has received gold at the International Mathematical Olympiad, and apply their abilities to problem-solving across various industries, they can figure everything out. I don't really know if this applies equally to models. For example, in GPU code optimization, there's a very interesting question: if you removed all data about GPU programming from the model, but it remained just as good as Astra is now, would it be able to optimize GPU kernels? Could it study in context what it needs, and then set up a pipeline or come up with a solution for performing optimization tasks?

And I think there is a discrepancy: if you take a person who was as smart as Astra, there is a gap between what that human can do and what Astra can do, perhaps regarding tools. And I think that we can actually get much closer to human abilities.

</details>

### 概念抽象与范畴论式的思考方式

**Speaker B**: 在我听来，这听起来非常像持续学习（continuous learning）的问题。你指的是这个意思吗？

<details>
<summary>Original English</summary>

**Speaker B**: To me it sounds very similar to the problem of continuous learning. Is that what you mean?

</details>

**Speaker A**: 这是最好的类比，没错。

<details>
<summary>Original English</summary>

**Speaker A**: This is the best example, yes.

</details>

**Speaker B**: 那你刚才为什么不直接这么说呢？

<details>
<summary>Original English</summary>

**Speaker B**: Why didn't you just say this?

</details>

**Speaker A**: 对，我想……我只是在想能不能直接用某些词，我平时一直在努力表达得严谨谨慎一些。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. I guess I... I was wondering if I could just blurt out some words; I try to be careful.

</details>

**Speaker B**: 但你的思维方式……可能我有点冒犯，不过我知道你本科是在哪里读的。你是学数学出身的吧？

<details>
<summary>Original English</summary>

**Speaker B**: But yes... you have a very—maybe a little—I think you are very... I actually know where you studied at undergraduate. You're a mathematician?

</details>

**Speaker A**: 没错，正是如此。学过数学。至少我以前确实想往这个方向发展。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Exactly, yes. Studied mathematics. Yes. At least I wanted to do it.

</details>

**Speaker B**: 难怪。这就像类型抽象和范畴论（Category Theory）：你总是在最高的范畴层面上思考，然后才被迫降落到具体的细节实例上，但内心深处其实更在乎范畴本身。而在沟通中这往往容易造成偏差，因为大家都在等着听具体的实物与细节，而你却总是试图……

<details>
<summary>Original English</summary>

**Speaker B**: As in type abstraction, category theory, where you think in categories, and then must go down to the specifics, while actually caring more about the category itself. And this is a mistake in communication, because everyone is waiting to hear about something specific, and you are actually too busy trying to...

</details>

<!-- chunk 12/13 -->

### 认识论的速记符号与思考媒介

**提问者**：……去普遍地传达。是的，这确实相当困难。我真不知道该怎么处理。也许可以使用某种简写记录，比如“我现在处于第二层”，然后“我正在进入第三层”，接着“我又回到了第二层”。

<details>
<summary>Original English</summary>

**Speaker A**: convey general. Yes. Which is quite difficult. I really don't know. there are you you can possibly to use some abbreviated record, like "I'm on the second" equal", then " I'm moving on to the third one. level" and " I'm going back to the second one. »

</details>

**受访者**：对于这类过程，我们应该有一套认识论意义上的速记符号。因为这确实不容易，当你在词语序列中压缩大量富有条理的内容时……嗯，我们是否应该转向某种“神经代码”（neurocode）呢？你觉得是否存在某种比英语、Python 或 JavaScript 更适合导出数据的方式？

<details>
<summary>Original English</summary>

**Speaker B**: we should have some epistemological shorthand for like this, because it's difficult, when you squeeze makes a lot of sense in sequence of words hmm, should we to switch to neurocode, do you know if there is some best way to exit data than English , or Python, or JavaScript?

</details>

**提问者**：据我所知还没有。这听起来有点类似之前的讨论。开个玩笑，但人们确实一直在思考模型的母语究竟应该是什么，模型本身究竟倾向于输出什么样的结果。有人甚至认为是二进制代码。

<details>
<summary>Original English</summary>

**Speaker A**: Not I know. This is a bit similar. just kidding, but people were thinking about what the native language is, what model do they want to give a result. Some say that binary code.

</details>

**受访者**：这是马克（Mark）和杰森（Jason）聊过的话题。我不太确定。是的，也许是 PTX，或者假定是英语与 Python 的混合体。我之所以这么说，是因为模型的能力在某种程度上正是我们用来训练它的那些材料的映射。所以我们其实依然希望……其实我并不是真的信服关于二进制代码的那个观点。

<details>
<summary>Original English</summary>

**Speaker B**: This is a topic Mark and Jason. I don't know. Yes. PTX. Suppose a mixture English and Python. I only say this because what are the capabilities of the model to some extent there is a reflection of that, what are we doing them on we teach. So we all we still want...i don't I really believe in the argument. about binary code.

</details>

**提问者**：我想我明白你的意思，但那感觉就像是……没错，你总是想用某种特定方式去给世界建模。

<details>
<summary>Original English</summary>

**Speaker A**: I think I understand, but it's like... yes, you want to model the world in a certain way.

</details>

### 萨丕尔-沃尔夫假说：语言对思维边界的塑造

**受访者**：在做这类交流时，我脑海中总是会浮现出一件事，那就是萨丕尔-沃尔夫假说（Sapir-Whorf hypothesis）。如果你选择英语，你就会受到它存在时长的局限——比方说大约五百年，其实并不算很长。事实上，你所使用的语言会限制你的思维方式；而如果你去学习另一门语言，例如汉语，不知道你是否……

<details>
<summary>Original English</summary>

**Speaker B**: I think I always remember about one thing I always I do it in such a way conversations, it is Sapir's hypothesis Worf: if you choose English, you are limited by time , how long it exists, let's say 500 years, and that's not so much. In fact, the language in which you are talking, limits your thinking, and if you learn another language, for example, in no Chinese times, I don't know if you...

</details>

**提问者**：我其实对这个不是很了解。

<details>
<summary>Original English</summary>

**Speaker A**: I don't really do that. knew.

</details>

**受访者**：而我平时讲中文。

<details>
<summary>Original English</summary>

**Speaker B**: And I am talking. in Chinese.

</details>

**提问者**：噢，我知道这个假说，只是我的中文说得不是很好。确实如此。

<details>
<summary>Original English</summary>

**Speaker A**: Oh, I knew about that, but My Chinese is not very good. good. Yes. Yes.

</details>

**受访者**：再比如在日语中，或者我记不清具体是哪种语言了——比如韩语中，当你与某人交谈时，你必须时刻考量社会地位与敬语层级，而这是一个独立于性别的全新维度。

<details>
<summary>Original English</summary>

**Speaker B**: Or, let's say, in Japanese, or, I I forgot what language it is, for example, in Korean when you are with Are you talking to someone? you must consider social status, and this is a different dimension than sex.

</details>

**提问者**：完全正确，它直接影响着你所表达的一切。当年我学语言学时，非洲好像有某种语言，它的语法范畴里甚至存在专门针对“植物”的词性与语法性。

<details>
<summary>Original English</summary>

**Speaker A**: Exactly, it's simple. affects everything you do do. When I studied linguistics, It seems there is some language in Africa, where there is a "vegetable" grammatical gender

</details>

**受访者**：没错，正如你所说，或者就像某些语言里缺乏表示“雪”的独立词汇等等。因此，你所选择的语言会塑造你的思考方式；如果你选择用英语来导出思维链条，你就必然把关注点转移到了英语预设决定的方向上。我不知道英语本身暗含着哪些先验假设。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, exactly as you say, or as the absence words for "snow" or something like that, after all. So the language you you choose, affects your thinking, and if you choose to withdraw the train of one's thoughts in English, you shift the focus to what decides English. I don't know what they are. a priori assumptions English language.

</details>

**提问者**：这非常有意思，我以前从未从这个角度思考过。我的意思是，在某种程度上这确实极其引人入胜，对吧？

<details>
<summary>Original English</summary>

**Speaker A**: This is interesting. I didn't think so. about it this way. I mean, on to some extent it is Interesting, right?

</details>

### 自回归与扩散：从语言生成机制看思维表达

**受访者**：你说得对。在许多模型中，思维链的具体表现形式也会因所使用的语言而有所不同。最明显的例子是：即使是用英语交流的中文大模型，其底层依然可能会用中文进行思考。但在相同的能力水平上，绝大多数模型都具备极强的多语言能力；我们可以看到，向模型中引入新语言并不需要付出巨大代价去彻底重学整套语言知识，它们在不同语言之间的思考几乎是可以无缝互换的。

<details>
<summary>Original English</summary>

**Speaker B**: You you are right, in many models a chain of thought too varies depending from the language. Obvious example: Chinese models that are talking in English, can still thinking in Chinese. But on at the same level most models very capable in multilingualism, and we we see what is possible add languages, no making great efforts efforts to study of the whole language, they are all will be the same think interchangeably.

</details>

**提问者**：没错，归根结底我们都是自回归式的。我的意思是，拿德语来说，主语和状语的搭配、动词必须置于句末——这实在让人抓狂，但这本身就是一个众所周知的事实，对吧？在你把句末那一堆名词和最终的动词呈现出来之前，听众根本无法预知你究竟要表达什么。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, we all, all of us autoregressive. I we mean, take, for example, German; you know, agreement of subject and adverb, verb must be put at the end , which is very annoying, is It's a known fact, right? You you don't know what you're talking about until at the end this pile will appear nouns, and then verb.

</details>

**受访者**：很多人都听过的一个最经典的例子就是电影《降临》（Arrival）。在那部电影里，七肢桶（Heptapods）对时间的感知是扁平、非线性的，因此它们在思考和表达时能够瞬间给出完整的句子。这与自回归生成和扩散生成之间的差异极为相似。我们人类是通过自回归的方式来交流的；但如果我们可以通过“扩散”（diffusion）的方式进行交流呢？在扩散过程中，整体信息会随着时间推移逐步清晰显现。

<details>
<summary>Original English</summary>

**Speaker B**: Well, the most classic example of which many have heard—this the film "Arrival", where heptapods perceive while something is flat. Therefore, they think and utter complete sentences at once. This is very similar to the difference between autoregression and diffusion. We we are talking about with help autoregression. What about if we could to speak for by diffusion? Where everything is gradual clears up over time.

</details>

**提问者**：我明白了，但整个核心概念在最初是一瞬间成型的。

<details>
<summary>Original English</summary>

**Speaker A**: I understand. I understand. But the whole idea arises immediately.

</details>

**受访者**：是的，我懂你的意思。所以说，这是一种彻底迥异的语言范式，但它依然是一种语言。

<details>
<summary>Original English</summary>

**Speaker B**: A. I understand. So, this is a radically different language, but it's still a language .

</details>

**提问者**：我完全明白了。噢，这确实非常、非常引人入胜。机器完全可以用这样一种语言来进行交互交流，虽然我们人类可能永远做不到，但机器根本不在乎这些限制。这或许有点跑题了，但世上是否存在一些本质上就是自回归的思考链条？

<details>
<summary>Original English</summary>

**Speaker A**: I understand. Oh, it really is. interesting. This is very, very interesting. In this language they can talking machines, which we probably we will never, but Cars don't care. Maybe this is a big one indentation, but is there any things that are in their own right are essentially chains considerations that are autoregressive?

</details>

**受访者**：有时候确实是这样，或者说大致如此。首先发生了一件事，紧接着才会引发另一件事，在某种意义上确实是线性的。

<details>
<summary>Original English</summary>

**Speaker B**: Sometimes, yes. Or so. Yes. Yes. Yes. First something happens, and then something else. Sort of, yes.

</details>

**提问者**：比如在代码中，一切逻辑通常都必须具备清晰的因果链条，至少大多数情况下是这样。

<details>
<summary>Original English</summary>

**Speaker A**: Any- that in the code, for example, must be causal- consequential, at least usually must be.

</details>

**受访者**：嗯，那倒不一定。如果你这么想，说明你对函数式编程语言的理论研究还不够深入。在纯函数式和关系型范式中，一切都是纯粹的逻辑映射，你仿佛彻底脱离了底层求解器（solver），由求解器去将这些永恒的关系与真理转化为机器代码。所以我觉得，探讨这个可能稍微超出了我的核心专长范围。但我非常热爱语言，无论是编程语言还是人类自然语言都是如此。我常常思考语言如何塑造我们的思维以及它如何划定我们认知能力的边界。不过我认为自己没必要在这个话题上继续深究了。不知道你是否还有其他想法？

<details>
<summary>Original English</summary>

**Speaker B**: Ahem. Well no, then you you don't study enough theory functional languages programming, where everything is clean functional and fully relational, and you seem to abstract from solver, which transforms these eternal truth to code. So I, yes, I feel that this, maybe a little out of place my competence. But I love languages, right? then languages programming, or human, and I have a lot I think about how it is. affects thinking and the boundaries of our opportunities. I don't think so. what is worth to me delve into this more. I don't know if there is Do you have any other thoughts?

</details>

### 从 GPU 底层到模型层：研究方向的演进与动因

**提问者**：我的最后一个问题关于你的研究方向规划。你涉足了这么多不同的研究领域，你经历过 GPU 算子优化的阶段，也做过 RLM（递归语言模型）阶段。你未来想必还有其他规划，而不会仅仅局限于某一个特定方向。顺便提一句，我注意到一个很有趣的演进路径：你是从底层的 GPU 优化起步，随后逐步转向了 Shena 所说的“零梯度”（zero gradient）领域。相比于深耕 GPU 底层，转向这一层会不会让人觉得显得没那么“硬核”或严肃？

<details>
<summary>Original English</summary>

**Speaker A**: AND, my final the question was about that you have all these research the directions you take Do you want to work? You you know, you had a phase GPU mode, there was the RLM stage. You probably have something is planned different, so you don't focus only on this. By the way, I noticed that it was interesting how you start from the GPU side , and then move on to "zero" gradient", as it called Shena. Not it seems less more serious than work with GPU?

</details>

**受访者**：是的，可能确实如你所提及的那种感觉。我个人很喜欢从数学视角去推导和审视问题，而有时候在胶水层（straps/scaffolding）和智能体（agents）架构上工作会让人感到相当别扭，因为放眼望去，好像所有人写的胶水绑定代码都大同小异，这类外围脚手架里缺乏真正的新颖思想。

<details>
<summary>Original English</summary>

**Speaker B**: Yes, probably in in the sense that you mentioned: I love to think about things with mathematical point vision, and sometimes very uncomfortable to work on straps and agents, because it's... because it seems that everyone the bindings are the same, few new ideas in straps.

</details>

**提问者**：确实是这样。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. This...this...

</details>

**受访者**：而且仅从实证角度来看，凭借我们现有的计算资源，要去验证海量的结论本身也是极其困难的。但我之所以转向这其中的许多问题，核心原因在于，依我看创新往往正是在这个交汇处不断涌现。GPU 层面的掌握，本质上是探索更广阔技术构想的工具与基石。比如你想写出极佳的高性能算子，甚至去自动化算子生成，这都是为了一个更宏大的目标：“我渴望在不被系统调用和底层硬件壁垒束缚的前提下，自由地探索算法构想。”从这个维度来看，虽然很多现有工作是在写胶水层代码，但我真正关注的依然是模型本层的问题。不过这个话题我就先谈到这里。

<details>
<summary>Original English</summary>

**Speaker B**: It's also simple. empirically difficult check a lot conclusions, at least with those computational resources that we we have. But the reason, why did I switch to many of these problems, is to because, in my opinion, right here it still has most of the time innovations. GPU level— it is a tool for learning other ideas. Do you want to for example, good write kernels or even automate them writing for the sake of broader goal: "I want explore ideas where I am not restricted. system calls." IN in this sense, you know, I I think that a lot of things from what is there written, concerning strapping, but I also I am interested in things on levels of models. But I I'll stop there.

</details>

### 合作意愿与探讨标准：寻找有独立见解的同行者

**提问者**：好的，这是一个非常好的注脚。如果人们希望与你取得联系，你具体在寻找什么样的合作？你希望与谁携手同行？有什么明确的行动倡议（call to action）吗？

<details>
<summary>Original English</summary>

**Speaker A**: Okay, that's good. hint. If people will want to apply to you, what exactly are you Looking for help? WITH who do you want cooperate? Some calls to action?

</details>

**受访者**：其实并没有什么强烈的特定诉求，让我觉得非得去寻求某个人合作不可——除了可能需要联系能够提供算力资源的公司，或者单纯想与同行探讨交流构想之外。不过我想说的是，我从来不排斥与其他志同道合的人一起碰撞思想。经常有学生来找我，或者其他学者……

<details>
<summary>Original English</summary>

**Speaker B**: Yes. Well, probably not. nothing like that, where am I would feel the need to work with someone, except with company for computational capacities or just so discuss this with others. But I will say that I never mind. to work on ideas with others people. Come to me often students apply , or even other students .

</details>

**提问者**：还有播客主播。

<details>
<summary>Original English</summary>

**Speaker A**: Podcasters.

</details>

**受访者**：播客主播也是。通常我收到的邮件往往是这种调调：“我非常喜欢 RLM，希望能一起合作。”我觉得这种沟通方式并不理想。最糟糕的说辞莫过于：“能否借助你的知识？”我的反应通常是：为什么要这么做？兄弟，你先去把我的论文读一遍吧。他们会说：“我‘读过’你的论文，关于递归语言模型，或者关于具备自我改进机制的专业智能体——比如 RLM 工具包。”诸如此类。

<details>
<summary>Original English</summary>

**Speaker B**: Podcasters. Um, and usually me comes email to styles: "I really like RLM, I want work together." Uh, and I feel that I Yes, this is unfortunate. approach, right? The worst thing is "it's possible" to use yours knowledge?" I am like this: in Why exactly? Like, read my article, dude. Type they will say: "I I read your article, in quotes, about recursive language models or about the pro- agent, such as RLM toolkit, which self-improvement ", or something like that.

</details>

**受访者**：我真正欣赏的是那些拥有自己独立见解的人，哪怕我们的观点截然不同也完全没有关系。我认为，如果你拥有坚定扎实的信念，并且能够清晰阐明你为什么会认为这些想法是正确的——虽然在实际中要严密证明这一点往往非常困难——但只要你对某些问题拥有稳定成体系的视角，我始终非常乐意深入交流，甚至一同开展合作研究。我在合作对象或者研究方向上没有任何预设的条条框框，完全是开放的。

<details>
<summary>Original English</summary>

**Speaker B**: Uh, and it's kind of like that I really like people who have their own opinion, even if we don't agree. I think if you are solid beliefs and you able to think, why do you think these Are the thoughts correct? no, because it's usually difficult actually say, but if you have stable views on some problems, I always happy to chat and, maybe even to work together. IN I have no restrictions. about who or what what I would like to do work. So, um without restrictions.

</details>

**提问者**：确实是这样。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Yes. Yes.

</details>

**受访者**：你知道的，在智能体时代，人们的吞吐量和处理带宽大幅提升，能做的事情比以往多得多。所以我认为，总的来说我并不是一个难以打动的人，但这确实需要你带着深思熟虑的见解而来。

<details>
<summary>Original English</summary>

**Speaker B**: I, you know, in the era agents, I think, can be done much more work, you know, about bandwidth , so I, yes, I think, In general, I don't It's hard to impress, but I I think it is necessary.

</details>

<!-- chunk 13/13 -->

### 注意力稀缺与科研选题的权衡

**提问者**：……只需要花一点点努力，去弄清楚你到底想要什么。这其实非常清楚。我的意思是，当你看到某个新颖的事物出现，做得很好、想法很漂亮简单，它就会立刻吸引你的注意力，对吧？其实要吸引各大前沿实验室所有年轻人的注意并没有那么困难，因为他们本身也在寻找你。你只需要展现出自己的成果，对吧？

<details>
<summary>Original English</summary>

**Interviewer**: ...a little effort to, you know, know what you want. This is very clear. I mean, when you see that something new appears, well done, nice simple idea, then it immediately attracts your attention, truth? This is actually not that difficult to attract attention all the boys from advanced laboratories, because they are looking for you. You just need to declare oneself, truth?

</details>

**受访者**：确实是这样，没错。但这确实是个事实。我想说的是，人类的注意力在当下是非常重要且极其稀缺的资源。我真的在自己负责的众多项目之间苦苦权衡，有时我甚至不知道该如何去应付这一切。并不是说智能体（agents）大体上没有帮助，只是我觉得我往往创建了一个 prompt、搭建起了一个东西，然后就再也没去盯着它了。

<details>
<summary>Original English</summary>

**Interviewee**: That's right. Yes. But yes, it's true. I will say that human attention is very important now, scarce, and I really struggle with number of projects which I lead and, I don't know how to cope with this. Not I think the agents generally helpful. I guess I just create a prompt, I create a thing, and then never on it I'm watching.

</details>

**提问者**：是的，这种情况非常普遍。

<details>
<summary>Original English</summary>

**Interviewer**: Yes. What is very common.

</details>

**受访者**：没错，这种情况确实很糟糕。或许其中一个微小的区别在于——请注意，也许他们专注于研究本身，我不太确定。但至少对我而言，我脑海中可能同时盘算着大约 10 到 15 个不同的想法想要去落地实现，可问题在于其中绝大多数都是不成功的。

<details>
<summary>Original English</summary>

**Interviewee**: Yes. Yes. And that sucks. Probably one of small differences are in that, mind you, maybe were engaged in research. I am not assured. But for me at least, I might be around 10 or 15 different ideas that I want to implement, but the thing is that most of them unsuccessful.

</details>

**提问者**：是的。

<details>
<summary>Original English</summary>

**Interviewer**: Yes.

</details>

### 研究中的灵感沉淀与专注投入

**受访者**：对于那些向我寻求指导或合作的人来说，情况可能也是这样。也许某个想法最终并不成功，但只要对方对此抱有执着与热情，我就会很感兴趣。因此，我们可以花一点时间去调研评估。如果我们能感觉到这里面确实存在某些价值，那就值得在接下来的几周里全身心投入，认真去做些扎实的探索。

你知道，这就是我的做事风格。顺便提一句，这也是为什么我非常热爱研究生阶段的学习与研究。因为总有这样的时刻：我只是在思考问题，比如在慢跑、打网球或者做其他事情的时候，看起来我好像完全没有在工作，但那些时刻反而是最充满趣味的。

而紧接着，当我真正对某件事情着迷时，我很确定自己会放下手头的一切工作，全盘接手并扑上去；我会把全部时间都用来反思推敲并解决这个难题。而当你推进到某个阶段，能够直接顺畅地开展实验时，后续的一切就会变得非常轻松自然，运转得像钟表一样顺理成章。

<details>
<summary>Original English</summary>

**Interviewee**: And this could also be true even for someone who turns to me. Maybe an idea actually unsuccessful, but she gives up I'm interested. So we can spend a little time for study, and if we feel that in this if there is something, it is worth it. Dedicate the following a few weeks ago, to take it seriously to do something.

And, you know, this is my style. That's why I love studying in postgraduate studies, by the way, because there are moments when I just thinking about tasks, for example, during jogging or playing tennis, or something else. It's like I'm not working. But these are the most interesting moments.

And then, when I am really into something, I'm sure I just drop everything and take on it; I spend all time for reflection and work on this problem. And when you reach a stage where you can just conduct experiments, then everything becomes quite easy and it goes like clockwork.

</details>

### 工业应用与纯科学探索的边界

**提问者**：对，抱歉打断一下，这引出了我们倒数第二个问题：现在许多人将科学视为下一个重要的里程碑，例如物理科学、生物学甚至是数学。你如何在选择适用于工业界的落地项目，与选择纯粹的科学探索项目之间进行权衡与区分呢？

<details>
<summary>Original English</summary>

**Interviewer**: So yes, sorry, that's it penultimate question about what many people now view science as the next milestone, for example, physical science, biology or even mathematics. How do you differentiate, let's say, choice projects that applicable in industries, and choice projects that are purely scientific?

</details>

**受访者**：实际上，甚至在读研之前，我就已经在从事人工智能在生物学领域的交叉研究了。不得不说，从那时起，这个领域发生了翻天覆地的变化。以前它纯粹是理论性的，就好像大家都抱着这样的想法：“当然，你懂的，我就走这一条路，我选了它。”

但如今，越来越多的人涌入了这个领域。因此我们专门成立了一个科学研究部门来覆盖这些课题，因为有许多工程师会说：“事实上，这里存在很多可解的问题（solvable problems）。”

你知道，我首先想说的是，我对其中很多课题的理解或许是相对有限的。但我认为，如果我了解到某个问题——无论是有相关的人联系我，还是我自己碰巧发现了这个问题——我会去思考：“嘿，我们正在使用、或者我们目前正在琢磨的某些架构设计原则，实际上是否非常适合用来解决这个特定任务？”

我自己对这些科学探索也非常钦佩和着迷，但我认为它的难度要大得多。我……我不知道该怎么说，我认为科学研究，尤其是经验科学或偏应用的科学，它的反馈周期往往极其漫长。

<details>
<summary>Original English</summary>

**Interviewee**: I was actually working over artificial intelligence in biology even before beginning of postgraduate studies. Since then, this area has changed a lot, I have to say. Previously it was purely theoretically, like: "Of course, you have mind? Here I have one path, and I chose it."

But now many people are moving into this sphere, so we created a scientific department to cover these topics, because there are many engineers say: "Actually there is solvable problems."

You know, I'll start with that. That my understanding many of these topics, probably enough limited, but I think if I find out about something—or someone will contact me, will I see it myself? problem—and I'll think: "Hey, some principles design, which we use or over which now we are thinking, actually good suitable for this tasks."

Me too I admire these things, but I think it's more difficult. I... I don't know. I think that science, especially empirical whether it is applicable, has very long cycles feedback.

</details>

**提问者**：嗯，确实如此。

<details>
<summary>Original English</summary>

**Interviewer**: Ahem. Yes, it is.

</details>