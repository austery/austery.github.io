---
author: AI Engineer
date: '2026-11-15'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Cyt3LU8TyNc
speaker: AI Engineer
tags:
  - artificial-intelligence
  - automation
  - software-engineering
  - large-language-model
title: Diogo Almeida：大模型为何难以实现自动化与软件工程的第四种逻辑门
summary: ChatGPT 与 RLHF 共同缔造者 Diogo Almeida 剖析了当前大语言模型在辅助场景表现优异却难以落地自动化的根源，指出追求极高确定性与可靠性才是关键。他呼吁重塑软件工程，将机器原生的智能作为除与、或、非之外的第四种语义逻辑门。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Diego Almeida
companies_orgs:
  - OpenAI
  - Anthropic
  - TypeSafe
products_models:
  - ChatGPT
  - InstructGPT
  - Jev
  - GPT-2
  - GPT-3
media_books: []
status: evergreen
---
### AI 的现状与自动化的缺位

我是 Diego Almeida，本次演讲的主题是《I Love You So Jev Much》。呃，这是在致敬 Glass Animals 乐队的梗，我们并不是什么怪人。正如我刚才所说，我是 Diego Almeida，大家通常称我为“Jev 专家”，有时也被叫做“粉衣 Jev 男”。我也是 ChatGPT、RLHF 以及 InstructGPT 的联合缔造者，不过我想台下的各位今天应该大多数都知道我是谁。

<details>
<summary>Original English</summary>
[music]

>> I'm Diego Almeida, and this talk is I Love You So Jev Much. Um, Glass Animals reference. We're not just weird. Um, like I said, I'm Diego Almeida. I'm known as the Jev guy, sometimes Jev pink man. Um, also co-created ChatGPT, RLHF, and InstructGPT, but I assume that for the crowd today, y'all know who I am, at least mostly.
</details>

我这里准备了一堆关于 AI 的具体内容想聊，不过我更喜欢先探讨我在 AI 领域最感兴趣的话题。首先就是：眼下到底他妈的发生了什么，所有的自动化又都去哪儿了？如果你以前听我说过这个，我很抱歉，但这确实是需要反复灌输给整个领域的一件大事，因为人们至今仍未理解，所以我必须不断大声疾呼，直到所有人都真正明白究竟是怎么回事。如果你身处 AI 行业，你就应当给出一个非常有力的解释：为什么 AI 能做到那么多极其惊艳的事情，却在另一大堆事情上依然毫无用处？

<details>
<summary>Original English</summary>
[snorts] Um, I have like a bunch of AI-specific stuff I want to get to, but I like going into my favorite topics in AI. First one is what the [ __ ] is actually going on and where is all the automation? If you've heard me say this before, I'm sorry, but it's such an important thing to beat into the field cuz people still do not get it, and I need to yell this until everyone really understands what the [ __ ] is going on. And if you're in AI, you should have a really good answer about why AI can do so many awesome things and yet still be so useless for a bunch of other ones.
</details>

我和 ChatGPT 的关系有些微妙，我是少数几个参与创造了 ChatGPT 却又去抨击它的人之一。先说清楚，我并不是讨厌 ChatGPT。我非常喜欢使用智能体，喜欢使用代码智能体，也喜欢聊天机器人。它们只是存在极大的局限性。具体来说，我认为它们把这个领域割裂成“过度承诺”与“交付不足”两种极端，这在某种程度上挺令人遗憾的。

<details>
<summary>Original English</summary>
My relationship to ChatGPT is somewhat unique, one of the few people who hates on ChatGPT, who made it. I don't hate ChatGPT, to be clear. I love using agents. I love using coding agents. I love chatbots. They're just quite limited. And in particular, I think it's a little tragic how much they've bifurcated the field into overpromise, underdeliver.
</details>

在我看来，这对全世界而言确实是非常糟糕的事情。我喜欢谈论 AI 领域的两个狂热教派，以及我们该如何化解这种认知失调——我认为只要没有特别完备解释的人，都应该正处于这种认知失调之中。

<details>
<summary>Original English</summary>
Really, really terrible stuff for the world in my opinion. And I like to talk about like the two cults in AI and how we can resolve the cognitive dissonance that everyone I think should be having unless they have a very good answer.
</details>

### AI 领域的两大派系与参差现状

第一个教派，就是大家所熟知的有效利他主义者（EA）群体。他们盯着所有的基准测试，然后断言：大语言模型不仅在几乎每一项基准测试上都超越了人类水平，而且这种超越已经持续了两年之久。过去两年来，我们一直在不断宣布 AGI 距离我们只有三个月了。

甚至可以追溯到 03 模型的时期。大家还记得那会儿吗？现在甚至已经没人关心那个模型了，但在当时，那可是 OpenAI 内部对 AGI 炒作的最狂热顶峰。

<details>
<summary>Original English</summary>
There's cult one, which is you know, the cult of like EAs. They look at all the benchmarks and they say like not only are LMs surpassing human level on basically every benchmark, they have been for two years. We've been announcing AGI three months away for two years now. Even since like the '03 days. Do people remember that? No one even care-cares about that model anymore and it it was that that was like peak internal to OpenAI AGI hype.
</details>

而在另一边，如果你去看基准测试之外的真实情况，去看看现实世界——特别是如果你走出旧金山去外面看看——就会发现整个世界的绝大部分其实完全没有改变，尽管 AI 确实他妈的很酷。我认为 AI 具有变革性。既认为 AI 酷炫且具备变革性，同时又觉得它目前在现实中表现平平，这其实是一种很罕见的视角。

<details>
<summary>Original English</summary>
And on the other hand, you look at the non-benchmarks and you look at the reality and you see the rest of the world, especially if you guys go outside and leave San Francisco, a lot of the world is like really unchanged despite AI being so [ __ ] cool. And I think AI is transformative. It's it's a rare point of view to actually think AI is cool and transformative and also like underwhelming the world right now.
</details>

最棘手的地方在于，这属于同一个领域，而且我们面对的都是完全相同的事实。那么，问题究竟出在哪里？为什么 AI 会表现得如此“参差不齐”？换句话说，为什么它在某些方面能做得这么好，而在另一些方面却又如此不行？对此，奥卡姆剃刀式的解释到底是什么？抱歉，我翻幻灯片的速度会比较快。或许我应该为拍照的人放慢一点节奏。不过我得提醒大家，节奏确实会很快。

<details>
<summary>Original English</summary>
And the tricky part is this is the same field and we are all seeing the same facts. So what gives? You know, why is AI jagged, so to speak? Like why can it be so good at some things and so not good at other things? And what is the Occam's razor explanation for that? Um I will be blasting through my slides fast. I'm sorry. Maybe I could slow down for people taking pictures. Um but uh I I'm noticing that uh this is going to go fast is all I'm saying.
</details>

我认为我们整个行业都应该具备一种奥卡姆剃刀式的解释：为什么有些任务它们不仅做得好，甚至好到不可思议、达到超人类水平，比如解决千禧年数学大奖难题；而另一方面，它们在某些事情上不仅表现很差，甚至毫无用处到连记账都碰不得？按理说记账听起来应该比千禧年数学难题容易得多吧？后者我能做，但前者我是绝对做不来的，而我以前还参加过数学竞赛。那么这里的症结何在？原因究竟是什么？我平时很喜欢把这里设计成互动环节，但这次我就直接告诉大家我的答案吧，抱歉打破了平等的互动。

<details>
<summary>Original English</summary>
So I think that we as a field should have an Occam's razor explanation for why are there some things that are just not just good, they are unbelievably good, superhuman, like millennium prize problems in math. But on the other hand, they're not just bad, they're so useless, they can't even be used to touch accounting. That sounds way easier than million prize problems in math, right? I could do the latter. I definitely could not do the former and I was a math athlete. So what gives here? What is the reason for this? And I normally love this as an interactive thing, but I will instead just tell you my answer. Sorry for the power dynamic.
</details>

### 人在回路与自动化的本质冲突

幻灯片左侧列出的所有东西，本质上全都是需要人在回路（human-in-the-loop）的任务。比如深度研究（Deep Research），我个人不可能比深度研究做得更好，模型在这方面真的太他妈强了。

但如果有人用枪指着我的头或者指着你的头，必须在我和深度研究之间选一个，并且要求答案必须准确无误、而不是文笔优美，你大概每次都会选择我。这就是优化方向的区别：针对自动化进行优化往往要简单得多、也纯粹得多，然而 AI 却屡屡在自动化上折戟。每年都会出现 AI 连汽车穿梭餐厅的点餐自动化都做不好的臭名昭著的失败案例。这本该让大家感到相当震惊。

<details>
<summary>Original English</summary>
Um everything on the left side is intrinsically a human in the loop task. Like deep research, I could not do better than deep research. The models are so [ __ ] good at that. But if gun to my head or gun to your head, you had to pick between me and deep research and the answer had to be correct, not well written, you'd probably pick me every time. And that's the distinction between like optimizing for automation, which tends to be a lot easier and a lot simpler, yet AI keeps failing at this. Every year there's like an infamous failure of AI failing to even automate drive-throughs. And that should be kind of shocking to people.
</details>

我的观点是，针对这类自动化任务，取悦人类和完成任务本身毫无关系。你真正需要做的，是在抽象层面上退后一步：做出决策之后，回到执行自动化的轨道上，而代码本身就是自动化的语言。因此，你必须与代码结合。虽然这里信息量很大，但我会再总结一次。我知道这听起来很讽刺，因为我也参与联合创立了 RLHF，但我确实认为 RLHF 本身就是问题的一部分。特别是，RLHF 正是导致当今所有 AI 都必须保留“人在回路”的原因——这里要打个星号，除非任务本身极易验证且可以独立运行，但即便如此，事后仍需要人在回路中进行校验。这是因为我们从一开始就硬生生把人塞了进去。这正是 RLHF 中“HF”（人类反馈）的含义。我的主张是，存在一条更好的路径。我对当前现状的概括是：当今 100% 的大语言模型都是针对“辅助”场景进行优化的。你可能会提到 RLVR（带可验证奖励的强化学习），但未经 RLHF 处理的 RLVR 模型，与之交互体验会极其糟糕。

<details>
<summary>Original English</summary>
And my claim is actually for these tasks pleasing a human is nothing to do with doing the task. What you want to do is basically be an abstraction away. You want the decision to be made and then you want to get back into doing automation and code is the language of automation. Therefore you need to integrate with code. This is a lot but I will summarize it again. I get the irony that uh you know I co-created RLHF and I do believe RLHF is part of the problem and RLHF in particular is why all AI today does require a human in the loop with an asterisk unless the task is like very trivially verifiable and can run on its own but still requires a human in the loop to verify it afterwards. It is because we literally put it in. That is what the HF is in RLHF and my claim is that there's a better way. You know my summary of the state is 100% of LMs today are optimized for assistance. You might talk about RLVR but the RLVR models are very bad to interact with if they've not been RLHFed.
</details>

这就导致大语言模型在辅助人类方面好得甚至有些不真实。它们简直强得离谱，以至于如果要向 ChatGPT 提问，你绝不应该选我而不选 ChatGPT。但如果是在后台实际执行认知工作，你根本不该信任大语言模型，因为它们从没有为此做过优化，这也是它们在自动化任务上如此差劲的原因。而且我认为，自动化比辅助要有价值得多，因为你可以借此完成更酷、更深层的事情。我稍后会展开讨论这一点，但我认为未来能做的事情还有极多，目前我们仅仅触及了皮毛。对我来说，这就是当前 AI 现状令人遗憾的地方。

<details>
<summary>Original English</summary>
The result is LMs become too good to be true at assistance. They are just so [ __ ] good like you should never pick me over ChatGPT for your ChatGPT queries. But for actually doing like you know run in the background cognitive work you should not trust LMs at all because they've not been optimized for that which is why they're so bad at the tasks of automation and I would also guess that automation is a lot more valuable than assistance because you can do way cooler deeper I'm going to get into this later but I think there's going to be so much stuff that we can do and we are just scratching the surface of that right now and that's the tragic thing about AI uh the state of AI for me.
</details>

### 最苦涩的教训：选对任务

让我们来谈谈 Jevolution。我不知道这样放合不合适，不过已经来不及改了。天啊，这张可千万别拍照。太好了，我看到有人比大拇指了，太棒了。因此，我们不能再继续搞 RLHF，而必须另辟蹊径。我们需要从第一性原理出发来思考：怎样才能面向“机器原生”（machine-native）的 AI 进行优化？希望大家已经了解 Jev 的交互界面，这正是我们正在做的事情。比优化其界面更重要的，是我们正在重新思考 AI 该如何构建，因为在过去开发 RLHF 时，我们走的也是这条路。

<details>
<summary>Original English</summary>
Let's talk about the Jevolution. Um I I can't tell if this is appropriate but it's too late. Um oh god don't take pictures of this one. Um cool. Oh I'm getting a thumbs up. Yeah excellent. So we're we instead of doing RLHF we just have to do something else. We need to think from first principles. How do we optimize for machine native AI? You guys hopefully know the interface of Jev and that is what we are doing. More important than optimizing for its interface, we are uh rethinking how AI should be done because this is what we did again for RLHF.
</details>

对于萨顿（Rich Sutton）的“苦涩的教训”（The Bitter Lesson），为了让我更容易表达观点，我用通俗的话来意译一下：算力和规模拓展的重要性超过算法。这就是为什么大家都被“规模化神教”洗脑了。但我认为还有一个比这更苦涩的教训，那就是：数据的重要性始终超过算力。如今行业里大家都在深刻体会这一点，但它其实自始至终都是显而易见的。到了该拍这张幻灯片的时候我会告诉大家。我认为，最苦涩的教训其实是：**选择正确的任务**。

对做机器学习的人来说，“选择正确的任务”是个很奇特的思考维度，因为他们热爱算法，只希望指标数值向下或者向上，朝着好的方向变动，而不想去思考现实世界。但这一直以来都是实现性能巨大飞跃的方式，重大突破正是这样诞生的，每一次都是源于此。对于经典的强化学习游戏来说也是如此。这就是为什么萨顿得出了他的苦涩教训——在进行 rollout 时，数据是由算力衍生出来的。在下国际象棋之类的任务中，你哪需要什么离线策略数据？而且规则本身就已经定义了什么是正确的任务，所以在做强化学习时，你甚至根本不需要去思考任务对不对。

<details>
<summary>Original English</summary>
For Sutton's bitter lesson, I'm going to loosely paraphrase to make my point easier to say, is that scaling um and compute matters more than algorithms. This is why people become like scaling pill geronimous and I would argue that there's an even bitterer lesson than that, which is data always matters more than compute. We are learning that quite a bit in the field now, but it has been obvious since the beginning of time. I'll tell you when the this is the one you should be photographing. I would argue that the the bitterest lesson is doing the right task. And doing the right task is like a weird thing to think about, especially for ML people, cuz they like algorithms. They want number goes down or up or whichever is good direction. They don't want to think about the real world. But this is always how you make gigantic gains in performance. This is how the big breakthroughs happen. 100% of the time it comes from this. And this is true for classical RL games. This is why Sutton had his bitter lesson, it which is data is derived by compute when you're doing rollouts. Like there's there's why would you need off policy data when playing chess or something like that? And doing the right task is defined by the rules. So actually when you're doing RL, you don't even need to think about the right task.
</details>

但在预训练方面，我们整个领域确实在“寻找正确任务”上进行了深入的探索。不知大家是否还记得 BERT 采用掩码语言模型的那个时期，行业花了很长时间，经历了很多迷茫，才最终发现下一个 token 预测其实非常厉害——这并不是因为它的掩码语言建模能力更强。目标函数本身并没有什么特别之处，重点在于你后续能用它来做什么。事实证明，下一个 token 预测在生成字符串方面效果惊人，而这恰好是这些预训练模型最擅长的地方。因此，任何程度的掩码语言模型，哪怕拥有今天的算力和算法，也无法做到像 GPT-3 那样有趣，因为两者所做的根本就不是同一个任务。而在数据方面，互联网显然已经成为一个巨大的瓶颈。我们现在为了获取更多数据，甚至到了近乎“焚书取字”的地步。但显而易见，数据的重要性远远超过算力，人们只是在不断重新发现和理解这一事实。

<details>
<summary>Original English</summary>
For pre-training, we actually as a field had to do a lot of thinking about the right task. I don't know if people remember the Bert days with um masked language modeling, but it took a while and it was very unclear to figure out that next pro token prediction was super [ __ ] cool, not because it was better at masked language modeling. You know, the objectives on their own aren't special. It's about what you can do with them afterwards. And it turns out next token prediction is incredible at generating strings, which is what these pre-trained models were so good at. So no level of masked language modeling, even if you had today's compute and algorithms, would make it as interesting as GPT-3 was because it was just doing a different task. And data, you know, the internet is obviously a giant bottleneck. Now we're like, you know, burning books or whatever in order to get more data, but data obviously matters a lot more than compute and people keep like rediscovering this and figuring this out.
</details>

### 从 RLHF 到机器原生智能

在让大语言模型变得实用这方面，这一规律就更是如此了。在 RLHF 出现之前，用于 RLHF 的数据根本就不存在，两者之间的差距可谓天壤之别。我给大家看下一张幻灯片，这大概是最相关的部分，也是当年 RLHF 论文里的研究成果。大体结论是：即便使用最笨拙的算法、采用 GPT-2 规模的模型，你也能获得相当于 GPT-9 级别的性能表现——我说的是真正的 GPT-9，而不是现在那种注水的 GPT 标号。过去那些版本号代表着预训练有效算力实现了百倍的规模增长，而现在他们已经放弃了这种命名方式，因为算力已经无法再这样扩展了。即便如此，如果单论遵循指令这项任务，仍然需要达到类似 GPT-7 到 9 的模型，才能比肩大约 2018 年那个仅有 GPT-2 大小的模型。这相当惊人，因为你通常会以为巨大的模型才是关键——它们确实很重要，但与“选择正确任务”所带来的巨大跃升相比，模型的体量并不是最重要的。剧透一下，这也正是我们在 Jev 上所做的事：我们在该领域实现了没人预料到的巨大飞跃，正是因为我们针对一项任务进行了优化，而业内很少有人会去思考什么是正确的任务。

<details>
<summary>Original English</summary>
It's extra true for making LLMs useful. Um, before RLHF even existed, the data for RLHF didn't exist and you could uh like it was night and day. I'll just show you the next slide. This is the probably the relevant part. This is what this was the work in the RLHF paper. And the high level was that even with the dumbest algorithms in the world, even with a GPT-2 sized model, you got something like GPT-9 level performance, like real GPT-9, not today's like fake GPT numbers. Like the numbers used to mean like a 100x scaling in effective compute for pre-training and they've given up on that because it just can't scale anymore. And still even with that it would take something like GPT-7 to 9 to match GPT-2, the model from like 2018 or whatever it was, at the task of instruction following. That is kind of wild because you think big LLMs are so important for this and they are, but that is not the most important thing compared to even the gigantic jump of doing the right task. And spoilers, this is what we did for Jev, right? Like we made this gigantic leap in the field that no one could realized could be coming because we were optimizing for a task and very few people think about the right task.
</details>

这就是为什么 Jev 拥有一种独特的妙处（je ne sais quoi）。我觉得这是个挺聪明的双关语。听到了一点敷衍的笑声，不过还是谢谢大家。你针对什么进行优化，就会得到什么。我一直在寻找一个比“可靠”（reliable）更好的词，如果大家有建议请告诉我。目前大语言模型最缺失的，正是这种智能上的确定可靠性。我常打比方说：你有 95% 的时间得到的是爱因斯坦，却有 5% 的时间得到的是憨豆先生。如果你分不清当前面对的是哪一个，那你他妈的怎么去实现自动化？与其将注意力放在偶发、之后还需要人类去验证的聪明表现上，为什么不专注于极致、狭窄且高度专一的可靠性，从而保证每一次都能获得那种智能？这在基准测试中是体现不出来的，也是大家喜欢 Jev 的原因。事后我也意识到，我们当时显然没有去筹备一个面向开发者的所谓“ChatGPT 时刻”，但它还是发生了，因为 AI 圈子里的人过度承诺、交付不足的情况实在太严重了，以至于出现一个真正不吹嘘的模型反而成了一大惊喜。它凭的不是速度、成本，甚至也不是交互界面。我的团队曾劝我不要把这些公之于众，好让我们保持长期的竞争优势，但我实在太在乎这件事了。核心就是可靠的智能。即使不用我们的模型，也拜托大家去做出真正厉害的模型来。

<details>
<summary>Original English</summary>
Um, this is why Jev has the je ne sais quoi. Um, that's a really smart pun I think. Um, that that little bit of a pity laugh, but thank you. Um, you get what you optimize for. I'm looking for a better word than reliable, so if you guys have suggestions let me know. But there's if there's this reliability of intelligence that's really missing in LLMs. I often call it you get Einstein 95% of the time, but Mr. Bean 5% of the time. And if you can't tell which is which, how the [ __ ] are you going to automate anything? And instead instead of like focusing on like sometimes occasional smarts that you can then verify, what if you focused on extreme extreme narrow focused reliability so you can get that smarts every time? And this doesn't show up on benchmarks. It is the reason why people love Jev. And this is also I realize in hindsight we obviously didn't prepare for a chat GPT moment for developers, but it happened because people in the AI space just overpromise, underdeliver so [ __ ] much that having a model that actually didn't do that was a surprise. And it is not the speed, cost, or even interface. This is something that, you know, my team tells me I shouldn't be telling people so that we can have a long-term advantage, and I just care too much. Like it's a reliable intelligence. Make sick models, please, even if we, you know, if it doesn't involve our models.
</details>

### 重塑软件工程与内循环智能

我们认为 Jev 是构建智能软件的基础。这部分我就直接跳过了，但我坚信软件必将强势回归。所谓的“SaaS 灭顶之灾”显然不可能发生，但我甚至觉得称之为“SaaS 危机”都有些低估了其影响，我稍后会细谈，在座的各位正是讨论这个话题最理想的听众。我对这一部分极其兴奋，因为这是我近期全新的思考。

我想对“智能软件”和“即时生成软件”（just-in-time software）做出区分。匪夷所思的是，AI 明明具有如此强大的变革性，但在过去十年里，除了编写成本变低之外，软件本身基本上毫无变化。这难道不奇怪吗？如果 AI 真的那么颠覆，难道我们在软件领域能做到的极致，仅仅是在旁边加一个聊天机器人，偶尔与软件交互一下，却连需要承担重大代价的决策都无法代为执行？如果 AI 真有那么强的变革力，这未免显得荒谬。我认为症结在于我们过度聚焦于编写代码的智能体，而没有花足够的心思将智能真正融入软件的内部核心循环（inner loop），这一点我稍后会详细解释。目前很多人已经在实践 Jev 式的模式，并取得了大量成功。我们不需要在这儿自夸，酷炫的成果已经非常多了，但我向 AI 工程师要透露的秘密是：整个行业在这条路上走得还远远不够深入。Swix 提到我可以给各位提一个独树一帜的倡议，希望我剩下的时间还够用。

<details>
<summary>Original English</summary>
Um we see that Jev is like a foundation for smart software. I'm going to skip all over this, but I think software is going to be so [ __ ] back. I think the narrative of SaaS apocalypse is obviously not going to happen, but I think that even calling it a SaaS apocalpyse is like an understatement, and I'll get into that a bit, and you guys ideally are the perfect crowd for this. I'm I'm so excited for this part because that's the part that's new to me. Um I want to make a distinction between smart software and just-in-time software. The the crazy part is AI is so transformative, and yet somehow despite AI being so awesome, software has essentially unchanged in the last decade except being cheaper to write. Isn't that what weird? Isn't the it weird that the best we can do in software is having a chatbot to the side that sometimes interacts with the software but cannot take expensive decisions for you? That is kind of like a weird thing if AI was really that transformative, and I think the problem is we're focusing too much on coding agents and not enough about putting the intelligence into the inner loop, which I'm going to get more into a bit. And people are jeving. There's been tons of successes. We don't need to flex this. There's so many cool things, but my AI E secret is going to be that the field isn't jeving hard enough. And this is what Swix said that I can make a call to action for you guys that's unique, and hopefully I have enough time for this.
</details>

我认为当今世界仍深陷于“大语言模型斯德哥尔摩综合征”之中。我们依然完全局限在大模型给定的思维定势里去思考，这真的挺让人遗憾的。软件行业有一句名言：“你使用的工具会改变你的思维方式。”我认为它对我们思维模式的改造已经有些过头了。我们没有像这个行业本该做的那样去真正重构软件。我们原本能做的事情远不止这些。希望在剩下的时间里，我能尽力让大家相信这一点。

<details>
<summary>Original English</summary>
I think the world still has LLM Stockholm syndrome. We are still thinking from a really LLM-filled place, which is I think tragic, you know? Like I I I love the software saying the tools you use change the way you think, and I think that it's changed the way we think way too much, and we're not really rethinking software like I think the field needs. I think that we could just just doing so much more. Hopefully I can try to do my best for my remaining time to convince you guys of that.
</details>

### 蓝光 LED 的启示与第四种逻辑门

那么，让我们展望一下未来。

请容许我使用一个我很喜欢的类比——关于发光二极管（LED）。在蓝光 LED 诞生之前，世界上只有红光和绿光 LED。它们的功能非常局限，只能用来做简单的指示灯，或者用在时钟这类设备上。而当蓝光 LED 被发明出来之后——其实计算机科学以外的事情我并不太懂，但当它出现后，它带来的应用场景绝不仅仅是原本预期的“颜色从两种增加到三种”那 50% 的提升，而是催生了无数全新的可能。现在 LED 可以用来发出白光，可以用作我们如今都在使用的各类显示屏，从而掀起了一场照明革命。仅仅是增加了一个能与旧原语组合搭配的新原语，LED 的应用潜力就迎来了难以想象的爆发式增长。大家或许已经猜到我接下来要说什么了。

<details>
<summary>Original English</summary>
Um, so let's jump to the future. Um, I an analogy I love, bear with me, is about LEDs. Before there was a blue LED, there was red and green LEDs. These were really limited in capability, and they were used for like simple indicators and you know like clocks and stuff like that. And when the blue LED was made discovered, I actually don't really know how things outside of computer science work. Um, but when it existed, I guess, um, it enabled not just like 50% more use cases, which what you'd expect about like changing colors from two to three, it enabled so many more. Like now LEDs could be used for white light. It could be used for like the displays that we all use right now, and it created a revolution in lighting. And it's it's it's unfathomable how much bigger the capabilities of LEDs were just you know adding a new primitive that composes together with the old primitives. You can see where I'm going here maybe.
</details>

我认为软件的发展也是类似的故事。软件本身太他妈不可思议了。先抛开过去五年的 AI 不谈，软件本身已经实现了大量极其惊艳的成就。我们做了很多探索。我真的很喜欢用 SaaS 吗？并不见得，但它解决问题了吗？绝对解决了他妈的问题。令人惊叹的是，我们仅仅依靠三种基础逻辑门，就构建出了如此庞大的世界。我们正是通过大于、小于、等于这些简单的二进制运算，才打造出这一切。仅凭如此简单的原语就能构建出整个软件生态，这简直匪夷所思。而我的主张是：我们如今借助 AI 所做的一切，也就是让智能具备机器原生特性，在概念上相当于加入了第四种“语义逻辑门”（semantic logic gate）。

如果我们能够直接利用常识、意图和人类的理解来进行编程呢？我们是否还需要写那些包含极其复杂规则的正则表达式，还是说我们可以直接声明：我们需要一个 Gmail 邮箱地址，或者一个看起来真实的邮箱？我们能做的事情太多了，为了达成这些目标，我们必须去拓宽便宜、智能、快速的边界。但不仅如此，就像蓝光 LED 一样，它的影响将远远超出将软件表征能力提升 33% 这么简单，因为它实际上相当于引入了一种全新的逻辑门。这种如同科幻小说般的未来，我认为是无法预测的。正如当年没人能预料到互联网会变得如此强大一样，因为它是更加草根、更加去中心化的，它需要赋予人们去创造不可思议事物的能力。

<details>
<summary>Original English</summary>
And I think it's a similar story for software. Software is so [ __ ] incredible. Ignore AI for the last you know half decade, but software's done so many insanely cool things. We've done a lot of stuff you know like do I love using SAS? Not really, but does it solve problems? Abso [ __ ] lutely. And it's incredible how much we've done with three [clears throat] fundamental logic gates. You know like we are doing this with like simple binary operations that can do things like greater than, less than, equal. It's kind of nuts how much software has been built from such simple primitives. And my claim is that what we are doing with AI now and we're making it our intelligence machine native, this is kind of conceptually adding a fourth semantic logic gate. What if we can program with common sense, with intention, with human understanding? Like do we still need regexes with like crazy things or can we just say like we want a Gmail email address or a real looking one? There's so much that we can do that we are going to need to push the you know push the frontiers of cheap, smart, fast in order to get done. But I think there's going to be like so many things here, And I think just like the blue LED, it's going to be way bigger than just increasing the representational ability of software by 33 % cuz it's adding effectively another kind of sort of logic gate. And this sci-fi is the stuff that I think will be impossible to predict. Just like who could predict how powerful the internet would have been because it requires it's like much more grassroots and decentralized and it requires people to be empowered to do insane stuff.
</details>

### 提倡“软件研究”与摆脱模型束缚

我把这称为“软件研究”（software research）。我不是在开玩笑。我认为未来软件的能力将迎来一场大爆发，我们应当鼓励人们去探索软件的全新边界——不一定是因为这有多大商业价值，而是因为大家拥有了这种能力，我们有了可供探索的新疆界。早期的互联网就是这个样子。当年的那些网站真的都有存在的必要吗？大概没有，但那确实很酷，而且我们从中发掘出了很多极其出色的东西。我认为我们迎来了另一次重现这种探索的机遇。所以我们不应该继续活在狭小的鱼缸里，任由 OpenAI 和 Anthropic 发布什么就只能接受什么，被动地充当大模型套壳应用（LLM wrappers）。因此，我在这里极力倡导“软件研究”这个方向。

这里的核心主题是货真价实的软件工程，而不仅仅是凭感觉的“氛围编程”（vibe coding）。这需要运用每一位资深软件工程师都熟知的那些工程方法：任务解构与拆分。我们需要思考执行阶段，最好是每个阶段都具备可验证性，从而实现真正的封装。我们必须切实做好状态管理，而不是想当然地把所有东西都当成 KV 缓存里的全局状态。核心就在于由极度在乎最终成果的人去践行扎扎实实的硬核工程。它不一定非要具有商业变现价值，但最好能酷到极致。我们应该去不断突破极限。

<details>
<summary>Original English</summary>
Um I call this software research. Um that's not a joke. Um but uh I I think that there's going to be like an explosion of what software can do and we will want people to be exploring those boundaries of software, not necessarily because it's valuable, but because they can, because we have like new frontiers to explore. And this is what the early internet was like. Should all of those websites existed? Probably not, but like it was very cool and we found a lot of awesome stuff from that and I think we we you know we have another opportunity for that. So we should not just keep living in this little you know fish tank that we are the victims of open AI and Anthropic on whatever they ship and we just have to be like LLM rappers. So I'm going to pitch software research as a direction here. The theme is going to be real software engineering, not just vibe coding. There's it's going to be like the kind of stuff that everyone has known if you've been a software engineer. Decomposition, breaking tasks down. We need to think about stages, ideally ones that can be verified so we have real encapsulation. And we all need to actually do state management instead of assuming everything is global state within a KV cache. And the theme is just going to be like real [ __ ] engineering by people who care a lot about the end result. It doesn't have to be valuable. Ideally it's sick as [ __ ] Um and you know we should be pushing the limits.
</details>

接下来我想分享几个我自己非常喜欢的想法，我很想探讨如何在现实世界中推动这些方向的发展。这算是我迈出的第一步，今天先在这里聊聊。我们已经筹集了一大笔资金，所以很希望能找到资助这些方向的途径，只是目前我们还缺乏运营支持来实现这一点。不过这里可以先抛出几个想法。

我认为现在的智能体确实很酷，但由于受制于 KV 缓存的束缚，它们在架构设计上极其僵化死板。如果计时器显示的时间没错的话，我没有充足的时间展开细讲了，但请相信我：过去大家尝试过的很多方案之所以失败，就是因为最终都在与 KV 缓存机制对抗，导致效率极低。但我认为能做的事情还有很多。

为什么记忆检索的复杂度非得是 O(N)？为什么不能把我们与代码智能体交互的历史记录全部带入每一次新的调用中？持续学习本就该是这个工作原理。我们本就具备足够的存储容量，只是缺乏足够的智能去对这些记忆执行 map-reduce 操作，以甄别哪些内容应该记住、哪些不该记住。

我认为在实现日志记录或更优检索方面还有很多方式。此外，当同时构建多个智能体时，为什么它们之间不能共享状态？为什么每个智能体都必须反复、从头去重新理解同一个代码库的模式？为什么针对子智能体的非朴素路由无法奏效？事实上连朴素路由都跑不通。可为什么我们做不到这些？为什么那些头部大实验室在“子智能体到底行不行得通”这个问题上总是反复横跳？从工程角度来看，这种架构确实具备优雅性，但它们都在与 KV 缓存对抗。我认为，如果我们能围绕这一点来专门设计智能体，我们所能实现的成就将远超现在。

<details>
<summary>Original English</summary>
I'm going to go into a couple of like my favorite ideas and I want to figure out how to encourage these in the world. So this is my first step at this. I'm just going to talk about it. We have raised a bunch of money so I would like to figure out how to fund this, but we don't have the operations help to do that. But here are just some ideas out there. Um I think agents are they're cool, but like they're they're so inflexible in their design because of the tyranny of the KV cache. I don't have the time for this if this timer is to be believed, but believe me that there's so much that people have tried to do but failed at because it ends up becoming inefficient because it fights against the KV cache. But I think there's a lot more to do. Why is memory O of N, right? Like why can't we have all of our history of coding agents always included in every new call? That is how continual learning works, right? And we have the memory available. It's just that we don't have the smarts to map reduce over the memory to find out like what you should what you should remember, what should you shouldn't. Um I think there's many ways to do login or even better lookups. Why when you're making many agents at once, why can't they not share state? Why do they need to rediscover the same patterns of the codebase over and over and over again? And why can't non-naive routing in sub agents work? Like even naive routing doesn't work. But like why can't we do these things? And why just like the you know the the big labs keep going back and forth on whether or not sub agents work? Um I think that like from an engineering perspective, there's elegance to it, but they fight against the KV cache. And I think that if we design agents around that, we could do so much more.
</details>

### 编码精神内核、实时安全与根除垃圾内容

这一个方向可能是我提出的所有想法里最抽象的，但我对它深信不疑。现实世界中充斥着委托代理问题（principal-agent problems）。这种情况发生在不同主体之间存在利益冲突或隐秘动机时——这里指的不是代码智能体，而是任何广义上的代理人。最典型的例子就是公民与民选官员之间的关系。我不想在这里发表过于政治化的言论，但社会各阶层确实都存在利益不对齐的现象。这导致了浪费、欺诈等各种负面结果；对于一个追求公平的社会来说，这就迫使人们过度恪守字面规定而非实质精神，进而导致了漏洞滋生和花钱买通规则的现象。我认为这个问题的根源在于我们无法把“精神实质”编码化。就像软件开发一样，我们受限只能编码具体的比特位，而无法把特定情境下的真实意图给编码进去。我认为，如果能在各个层面真正将实质精神编码化，很多组织乃至整个社会都将迎来巨变。

还有实时智能安全：我们能否防止类似 OpenAI Hugging Face 沙箱被攻破这类事件？他们当初为什么没能防住？并不是因为他们缺乏足够的智能。我认为，识破攻击者的不轨企图，其实比真正实施攻击要容易得多。根本原因在于现有的检测方案在速度、成本和可靠性上达不到要求，无法真正做到实时运行。如果每家企业都能拥有自己专属且真正聪明的实时安全防护，这该有多帅？

关于生成式 UI（Generative UIs），因为后面有人会专门做分享，我就不多讲了，免得抢了别人的风头，但相信我，那真的超级他妈酷。

还有语义依赖类型（semantic dependent typing）。为什么我们就不能拥有一套真正基于语义的类型系统呢？为什么我们不能直接声明我们需要的局部属性，从而不必顺着依赖链一层层往下阅读底层代码？这些理应全都可以实现。试想一下，如果你能在代码静态检查器中运行一个类似 Jev 的模型，用来检查类型是否绝对安全，并确保所有的语义属性都得到遵循，那该有多棒。

<details>
<summary>Original English</summary>
This one's the probably the most vague of my directions, but I feel very strongly about it. Um the world is full of principal agent problems. This is when you have like you know ulterior motives between this is not a coding agent, but like any agent. The the classic example is citizens versus elected officials. And I don't want to make a too political claim here, but like there's misalignment in all levels of society. And this results in like waste, fraud, bad things, and it it results in for a society that wants fairness, you need to over emphasize the letter over the spirit, which then results in loopholes and pay pay to win dynamics in the world. And I think the root of that problem is we can't encode the spirit. Just like with software, we're constrained to encoding bits instead of what we actually meant in that situation. And I think so many organizations, society could be transformed by really encoding the spirit all over the place. Obviously real-time intelligence security, can we prevent the OpenAI hugging face sandbox, blah blah blah? Um, why did why couldn't they prevent it? It is not because they didn't have the intelligence. I would argue it's a lot easier to figure out they're doing a naughty thing than to actually do the naughty thing. It is because it was not fast, cheap, and reliable enough to actually run real-time. And what happens when every corporation has their own real-time security that's actually smart? How cool would that [ __ ] be? I can't talk about generative UIs because people are going to be talking about it afterwards. I don't want to steal their thunder, but it's cool as [ __ ] trust me. Um, like semantic dependent typing. Why can't the we have like a type system that actually is semantic, right? Like why can't we like declare what local properties we want so we don't have to read a chain of dependencies deep down? These all should be possible. And imagine if you could like run a JEP-like model in your lint checker to check if your it's all type-safe and it could you know uphold semantic properties. It would be so [ __ ] cool.
</details>

推特上之前有一个关于语音交互界面的精彩视频。总的来说，我认为全新的人机界面极其令人兴奋。对我而言，这标志着“智能软件依意图行事”（do what I mean）的回归。过去这种理念曾流行过一阵，但从未真正行得通，因为单靠硬编码规则根本不可能完全理解人的真实意图。

另外，“停止制造垃圾内容”（stopping slop）显然也是这里的一大主题，我们对这一点深信不疑。这是我的道具——我们准备了一个用于保障类型安全、写着“停止生成式 AI 垃圾”的棒球棒，非常酷。我想谈谈这种垃圾内容的根源。

垃圾内容的根源在于 AI 的不可靠性。因此，作为一家企业或者作为具体干事的人，你无法用它来做那些需要你承担成本的决策。但把这些成本转嫁给其他人却完全行得通，这种将成本外部化的做法极其恶劣，最终产生的就全都是垃圾内容。

如果大家真的会去阅读、筛选并真正在意输出质量，那就不会变成垃圾内容。但如今世界上到处充斥着这些，因为那些不负责任的劣质从业者享有不对称的优势。因此，我认为我们至少能够把世界从无休止的低质骚扰地狱中拯救出来，这将会非常棒。

此外，我还觉得“诅咒软件”（cursed software）特别有意思。不知大家有没有逛过 Reddit 上的 bad UI battles 板块？哪怕他们做出的界面极其糟糕，也依然他妈的酷炫至极——比如把“确认删除账号”做成一个完全随机的碰运气游戏。我其实认为，“仅仅因为我们能做到就去动手实现”正是软件工程的精髓所在，因为谁知道呢，说不定这些点子里有 1% 真的能孕育出极其惊艳的成果。真正去包容哪怕是糟糕的创意，正是作为一个充满玩心的黑客的真谛所在。

<details>
<summary>Original English</summary>
There's there was a great Twitter video on um like a voice interface. In general, I think new interfaces are so exciting. This is to me the return of like this is going to show by agent software like do what I mean. This used to be like a popular thing, but it never really worked because you it was it was too many hard-coded rules to really figure out what I mean. Um, the stopping slop obviously a big theme of here, but like we definitely believe this. This is my props I have to We have a stop Gen AI baseball bat for type-safe. It is very very awesome. I want to talk about the root of slop. Um, the the root of slop is that AI is unreliable. Therefore, you as a company or you as you know like someone who's doing stuff, it can't be used for decisions that costs you stuff. But it's actually totally fine to push the costs into other people, which is horrible, you know externalized costs. And then this is what ends up becoming slop. You know if people actually read this stuff and filter it and like care about the quality, it becomes not slop. But now the world is full of this because there's an asymmetric advantage for people who are like bad actors and don't give a [ __ ] So, I think that we can save the world from at least inbound hell among many other things and that would be very cool. Um, and even something I think is super sick is cursed software. Like why? If you guys ever seen the subreddit bad UI battles, it is so [ __ ] cool even though they make the horrible interfaces like this whole game of like would you like to delete your account becomes, you know, a a random thing. And I actually think doing things because we can is what software engineering is about cuz who knows maybe 1% of these ideas actually lead to something super awesome. And I think like really cultivating even bad ideas is kind of what being like this, you know, playful hacker is all about.
</details>

### 未来的无限可能与致谢

总的来说就是实现万物的完全自动化。接下来的演讲大多会围绕这个展开。这是一张翻车了的图片，我们的 Logo 渲染得有点不太对，不过别太在意，看着确实有点怪。后续的很多分享都会聚焦在自动化上，谢谢大家。

如果你是一名软件工程师，你几乎必然是在由比特构成的世界里思考的。只要你懂一点软件、接触过软件，就会清楚地知道哪些事情软件做得到，哪些做不到，因为那是明摆着的限制。你清楚地知道有些事情必须由人去做，因为它们与传统的软件逻辑不兼容。但如果这些限制不复存在了呢？也许不是今天，但可能在未来的 6 个月或 1 年之后，还有什么是我们无法实现自动化的？

这就是我想留给大家思考的核心命题。因为我认为未来极有可能会变成这样：问题不再是我们能不能实现某件事的自动化，而仅仅在于实现它需要投入多少工作量——就像现今面对那些本就可以自动化的任务一样。那真的会酷到极致。

必须如此，非常感谢大家。

<details>
<summary>Original English</summary>
And generally just automating everything, this is what the follow-up this is this is a flop image but uh so our logo's a little bit wrong but don't stare at that that's a little weird. Um, this is what a lot of the follow-up talks are going to be about. Thank you. Um, and and if you're a software engineer, you almost certainly think in the world of bits. If you know anything about software uh and you've interacted with software, you know that there are things software can do and software cannot do because that is just only obvious, right? Like there's some things that you know you need to do because that is not compatible with software. But what if those constraints were no longer true? Maybe not today but maybe in like 6 months or a year, what couldn't we automate? And that's kind of where I want to leave this whole thing because I think there is very likely to be a future where it's not a question of whether or not we can automate something, it's going to be a question of like how much work is it which is how it is right now for the stuff that can be automated and that would be cool as [ __ ] So, hell yeah. Thank you.
</details>

虽然严重超时了，但我还是要由衷感谢最初就相信我们的支持者。我们当初完全没想到会有这么多人产生共鸣。我们原本以为自己才是疯了的那群人，但事实证明，世界上大多数人都意识到了 AI 本该拥有远超于此的能力。

感谢那些对可靠性保持务实态度的人。大家都知道我讨厌基准测试，现在很多其他人也都在大声疾呼基准测试有多糟糕。它伤害最深的反而是那些除了跑基准测试之外毫无闲暇顾及其他的人，这很可悲。

对于那些正在不断拓宽软件极限的人们，你们太棒了。我们希望能与大家站在一起，助力各位前行。致所有的梦想家，以及那些不愿被过往既定规则所束缚的人们，我们真心想为你们而战。我们希望让机器原生智能变得如同第四种逻辑门一样坚实可靠。这是一个极高的标准，我们前方的路还有很长。再次谢谢，谢谢大家！

<details>
<summary>Original English</summary>
Um, I'm super overtime but thank you to the early believers. You know, we had no idea so many people would resonate with this. We thought we were the insane ones but it turns out like we were actually the majority of the world who realized AI could be so much more. Thank you to like the people who are like realistic about reliability. Everyone knows I hate benchmarks and a lot of other people are really screaming out like benchmarks [ __ ] suck. They're actually they hurt the people who do not have time for anything other than benchmarks most. It's tragic. And for the people who are pushing the limits of software, like [ __ ] yes. And we want to be there with you helping you all do that. The the dreamers and the people who don't want to be limited by everything that has happened so far, we want to really fight for you and we want this to be as reliable as a fourth logic gate. And that is a very high bar and we have like a lot of work to do. So thank you, thank you.
</details>