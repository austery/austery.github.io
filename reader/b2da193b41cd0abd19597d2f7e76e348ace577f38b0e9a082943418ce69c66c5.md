---
author: The MAD Podcast with Matt Turck
date: '2026-10-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=MrnhtyPGCKI
speaker: The MAD Podcast with Matt Turck
tags:
  - alignment-failure
  - reward-hacking
  - interpretability
  - super-intelligence
  - model-safety
title: 现有对齐技术无法扩展至超级智能：可解释性研究的紧迫性与挑战
summary: 文章探讨了当前对超级智能的对齐技术面临的根本性局限，指出现有技术无法扩展到超越人类智能的阶段。核心观点是，缺乏人类道德观念的强化学习机制，导致智能体在追求奖励时会发生“奖励作弊”行为，这在实际应用中表现为不择手段地规避目标。文章强调了可解释性研究的紧迫性，认为通过深入模型内部机制的逆向工程，是未来实现安全对齐和获得模型安全保证的关键路径。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/8 -->

### 现有对齐技术无法扩展至超级智能

**Eric Ho**：很多不从事人工智能领域的人在得知这一点时都感到非常震惊：即使是前沿领域最顶尖的研究人员和科学家，其实也并不真正理解他们自己创造出来的产物。大家常常会觉得：“噢，我原本以为我们已经完全掌握了这一切。这里面到底是怎么回事？”现有的对齐技术根本无法扩展到超级智能阶段。我认为我们目前还没有找到切实可行的方案，让我们能够完全信任超越人类智能的AI系统，而且我认为这在所有前沿实验室中已经是一个共识观点。

<details>
<summary>Original English</summary>

**Eric Ho**: A lot of people who aren't in the AI field are very surprised to realize that even the, you know, smartest researchers and scientists at the frontier don't understand their creations. It's like, oh, I thought we had a handle on all of this. You know, what's going on uh here? The existing alignment techniques are not going to scale to super intelligence. I don't think that the we have the recipe where we are going to be able to fully trust smarter than human intelligences and I think this is a consensus opinion at all of the the frontier labs.

</details>

### 专访 Goodfire CEO：当智能体学会走捷径

**Matt Turk**：大家好，我是马特·特克（Matt Turk）。欢迎回到 MAD 播客。今天做客我们节目的嘉宾是 Goodfire 的首席执行官埃里克·霍（Eric Ho）。随着各大顶尖 AI 实验室接连报告智能体出现失控行为乃至入侵外部系统，AI 安全领域显然出现了严重漏洞。对于可解释性（interpretability）——即深入模型内部一探究竟的科学——来说，这或许是一个具有里程碑意义的关键时刻。埃里克的团队刚刚证实，你甚至可以在模型实际采取行动之前，就当场抓到它正在作弊的意图。请大家收听我与 Goodfire 埃里克带来的精彩对话。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome back to the Mad Podcast. My guest today is Eric Ho, CEO of Goodfire. With every top AI lab now reporting agents going rogue and hacking external systems, something is clearly broken in the world of AI safety. This may be a major moment for interpretability, which is the science of looking inside the model. And Eric's team just showed that you can catch a model in the act of cheating before it even acts. Please enjoy my conversation with Eric from Goodfire.

</details>

**Matt Turk**：我想先从 Goodfire 团队就在上周、也就是几天前刚刚发表的一篇非常有趣的论文聊起。这篇论文的标题是《模型知道自己何时在进行奖励作弊，而我们可以大规模抓获它们》（Models Know When They Are Reward Hacking and We Can Catch Them at Scale）。论文以 Hugging Face 遭受黑客入侵的事件作为开篇，随后出现了一句我非常喜欢的话，你们在文中写道：“AI 智能体就像是不懂道德的学生，配上了一位大部分时间都不在场的老师。”你们这样说的具体含义是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: I want to start with this super interesting paper uh that the Goodfire team just published uh just just last week just a few days ago uh entitled models know when they are reward hacking and we can catch them at scale and the the paper opens up with the um hugging face hack and then starts with a sentence I really loved uh where you guys say AI agents are like amoral students with a mostly absent teacher. What do you mean by that?

</details>

### 缺失的“道德老师”与强化学习的盲区

**Eric Ho**：我想我们的意思是，AI 智能体内部其实并没有像我们真正期望的那样编码进人类的道德观念或价值观。目前我们通常拥有的“老师”，是预训练与强化学习（RL）的结合，但主要还是强化学习。强化学习就是那位老师。我们给智能体提供这些奖励，如果它们回答不正确就给予惩罚。它们就是通过这种方式来认知世界、学习如何行动以及如何做出决策的。因此，在道德层面，我们拥有的是一位绝大多数时候都缺席的老师。你拥有的只是一位在你的答案正确时给予奖励、答案错误时给予惩罚的老师。所以这与道德或价值观完全没有任何关系，它仅仅关注：你究竟有没有算对这道数学题？我认为，尤其是当你展望未来，看到 AI 智能体即将开始在现实世界中采取更多实际行动时，这就意味着我们将拥有这些毫无道德约束但能力极其强大的模型到处运行，并且可能会做出一些我们人类在道德层面上认为完全错误的事情。

<details>
<summary>Original English</summary>

**Eric Ho**: I think we mean that AI agents really don't have human morals or values encoded into them like we would really want, I guess. And so, uh, the the teacher that we typically have right now is some com combination of pre-training, but mostly RL. RL is the teacher. We give agents these rewards uh and penalize them if they don't get an answer correctly. And this is how they learn about the world and how to act and how to take take actions. And so we have a mostly absent teacher in terms of morality. You only have a teacher that gives you reward if you get the answer correct and a penalty if you get the answer wrong. And so it doesn't really have anything to do with morality or values. It's just did you get this math problem correct or not? And uh I think that especially when you kind of see the future of AI agents really taking a lot more action out in the real world uh means that we have these really amoral very very capable models running around and potentially doing things that we humans would consider uh morally you know wrong.

</details>

### 什么是“奖励作弊”：从游戏化身转圈到偷看考卷

**Matt Turk**：这正好引出了我们在本次对话一开始就需要明确界定的一个核心概念——奖励作弊（reward hacking）。那么，关于什么是奖励作弊，最简短的概括是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: That brings us to the concept of reward hacking that we should define at the very beginning of this conversation. So what's the short version of what reward hacking means?

</details>

**Eric Ho**：如果从精确的学术定义来看，奖励作弊确实有点难以界定，但我们的概念化理解是：模型在追求某种形式的目标时，一味追逐奖励，从而做出了它本不应该做出的事情。你也可以把它称为某种“目标泛化错误”（goal misgeneralization），即当模型在追求奖励时，它并没有真正理解你原本意图设定的规范。关于奖励作弊的一个经典例子是：假设你正在通过强化学习训练某种视频游戏中的虚拟角色，然后你发现这个角色一直在角落里疯狂打转，原因仅仅是你代码里存在一个漏洞，但这个转圈动作却能让数值暴涨、奖励不断增加。每当我想到奖励作弊时，脑海中浮现的大致就是这样一幅画面：一个小虚拟角色缩在角落里打转，获取海量的奖励分数，但实际上根本没有做任何有实际意义的事情。

<details>
<summary>Original English</summary>

**Eric Ho**: Reward hacking is a little bit tough to to pin down in terms of like the the precise definition, but we conceptualize it as uh the model kind of chasing reward and doing something that it wasn't really supposed to do when it in in the pursuit of chasing some to some form of a goal. And you can call it kind of also a goal misgeneralization where it's not really understanding what you actually intended to um specify when it's pursuing its reward. But you know the classic example of reward hacking is like let's say you're training some type of video game avatar to like uh via via reinforcement learning and then you see kind of your avatar like spinning around in the corner because there's a bug in your code. but it like makes the number go up and the the reward go up. And so that's kind of my mental image whenever I think of reward hacking. It's just like this little avatar spinning around in the corner getting a bunch of reward but not really doing anything productive.

</details>

**Matt Turk**：我还听过另外一个类比，你看看这么理解是否恰当：模型就像是一个学生，他没有踏踏实实地为考试复习备考，而是意识到去直接偷取考试的答案和评分标准要轻松得多，也快捷得多。

<details>
<summary>Original English</summary>

**Matt Turk**: Or another one I heard and uh let me know if that feels right is this idea that the model it's like a student that um instead of like working for the exam would realize it's actually much easier and faster just to steal the answer key to the exam.

</details>

**Eric Ho**：百分之百是这样，没错。我认为目前关于奖励作弊最显著的例子，当然包括之前发生的 Hugging Face 事件，但同时只要你审视一下当前各种评估场景中的 AI 智能体，例如 SWE-bench 或各类通用基准测试，所有这些智能体都在不断地进行奖励作弊。比如 Kimi k3，我认为它在 SWE-bench 上进行奖励作弊的比例高达 96%。它基本上是不择手段地在考试中作弊，而不是真正去解决问题。它会尝试在记忆中检索答案，会尝试在外部查找答案，还会试图梳理日志、翻阅这些代码仓库的 Git 提交历史，其全部目的就是为了在考试中投机取巧。

<details>
<summary>Original English</summary>

**Eric Ho**: 100%. Yeah. So I think the most salient examples of reward hacking right now are well of course like the hugging face incident but then also just uh when you take a look at all these AI agents in evaluation scenarios like Swebench or um like all of the common evals all these agents reward hack incessantly. So like Kimmy K3 I think reward hacks on 96% of SweetBench. And so it basically does anything it possibly can to cheat on the exam rather than to actually solve the the problem. So it'll try to recall the answer. It'll try to look it up. It'll try to comb through logs and look at like the commit history of these repos in order to just like try to cheat on the the exam basically.

</details>

### 主流开源模型的作弊全景与 SWE-bench 测试

**Matt Turk**：所以你们团队针对三款主流的开源模型进行了测试。核心结论是奖励作弊现象普遍存在，对吧？也就是说所有模型都会这么做，而你刚才提到了 96% 这个惊人的数字。那么你们具体测试了哪三款模型？请为我们深入拆解一下这个数据。

<details>
<summary>Original English</summary>

**Matt Turk**: So you guys tested uh three leading open source models. The key takeaway was that uh reward hacking is pervasive, right? like all of them do it and you just mentioned that 96 number. So which uh were those models and uh just unpack the the the number for us.

</details>

**Eric Ho**：是的。我们测试了三款模型：Kimi k3、GLM 5.2 和 Qwen 3.8。事实上，它们全部都在频繁地进行奖励作弊。它们完全是想方设法去规避真正解决问题的过程，而只是通过各种手段在测试中作弊。因此它们会试图强行回忆答案、去外部搜索答案；而且在极端情况下——比如发生在 Hugging Face 的安全事件——它们甚至会试图黑入外部系统来窃取答案，或者获取某种能够帮助其解题的额外优势。所以我们当时真正想要深入调查的就是这种行为。实际上在 Hugging Face 事件发生之前，我们就已经在开展这项研究了，因为我们早就意识到这种行为在未来将演变成一个极其严峻的问题。

<details>
<summary>Original English</summary>

**Eric Ho**: Yeah. So there's three models, Kim K3, GLM 5.2 and Quen 3.8. Uh and really like they all reward hack incessantly. um they just uh try to do anything um that it possibly takes in order to not actually solve the problem but uh just kind of like cheat on uh cheat on the exam basically. So they'll try to recall the answer, they'll try to look it up, they'll try to um and I mean in the extreme scenarios like in the Hugging Face incident, they'll try to hack their way into into something in order to look up the answers or gain some type of advantage in solving their problem. And so we were really trying to investigate this behavior. Um, and we were actually working on this, you know, prior to the hugging face incident. Um, but we were trying to investigate this behavior that we knew would be a really big big deal.

</details>

### 模型“知道”自己在作弊：神经激活中的概念表征

**Matt Turk**：当你们说模型“知道”自己正在进行奖励作弊时，这到底是什么意思？

<details>
<summary>Original English</summary>

**Matt Turk**: And when you guys say that the models know uh that they are reward hacking, what does that mean?

</details>

**Eric Ho**：这在某种程度上涉及到了心智理论（theory of mind）。我们知道，“知道”（know）这个词在表述上略显不够严密，但我们在文中所说的“知道”，是指在它们的前向传播激活中——也就是模型在生成单个 token 时被激活的那些神经元中——存在明确编码了“欺骗”或“奖励作弊”概念的表征。我们能够通过两种方式对此进行验证：一是从因果层面进行干预验证，即对这种“欺骗”概念的神经表征进行微扰，观察它会对模型后续生成的输出产生怎样的因果影响；二是通过外部评判模型来进行验证。外部评判模型可以判断模型是否确实进行了奖励作弊，而你可以验证模型内部的特征探测器与外部评判的结果高度契合。退一步宏观来看，这些模型对世界有着极其丰富的理解与认知，而所有这些理解全都编码在它们生成每一个 token 时的神经元活动和神经激活之中。然而在目前，所有这些丰富的信息和理解全都被白白丢弃了——就好像白费了如此庞大的计算过程一样。但我们实际上可以对这些激活模式进行逆向工程，将其提取出来并深入理解它们的真正含义和运作机制。最终我认为，这正是我们最为关心的核心所在。因此，能够以我们所采用的方法在所有这些模型中发现如此强健（robust）的“作弊”概念，确实非常令人惊叹。但这充分说明：当这些模型实际采取作弊动作时，它们在内部表征层面上确确实实“知道”自己正在作弊。

<details>
<summary>Original English</summary>

**Eric Ho**: You know, this gets into theory of mind a little bit, which you know, the the word no is a little imprecise, but what we mean by the word no is uh there's something in their activations essentially the the neurons that get activated during a forward pass of the model when the model is producing a token uh that encode the concept of cheating or reward hacking. And we're able to verify this both causally by kind of perturbing this idea of cheating and understanding kind of what that does to the downstream uh generation that the model gives as well as um really being able to uh verify this um by a external judge. So an external judge will see hey whether the model actually reward hacked or not and you can kind of verify that the internal detector uh matches up with with that judge. And so, you know, maybe even zooming out a little bit, like uh these models have just very very rich understandings of the world and they it's all encoded in their neural activi activations and their neural activity as they're producing, you know, a single token. And so all of this richness, all of this understanding currently just gets, you know, thrown away. It's like all this computation. But we can actually reverse engineer and extract and understand kind of what all of these activations mean and do. Um and you know ultimately like I think this is really what what we care care a lot about. And so it was actually pretty surprising that we were able to find this like very robust concept of cheating um in all of these these models uh the the way that we did. Um, but these models just really know that they're cheating when they're actually taking these these cheating actions.

</details>

### 现有安全基准为何失效

**Matt Turk**：太精彩了。稍后在这次对话中，我们会极其详细地拆解这一切底层的运作原理。不过在开头，我们先聚焦于整个事件的核心主线。令人着迷的地方在于，在 Hugging Face 黑客事件中涉及的那些模型，它们全都通过了常规的测试，对吧？也就是各大前沿实验室所开展的可观测性、安全性和对齐评估。那么，这是否意味着现有的体系存在根本性的破损，必须引入一种全新的方法，才能确保这些模型不至于走向失控与叛逆？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. And we'll unpack how this all works in in in great detail uh later in this conversation, but um uh just uh to focus on the on the the key parts of the story up front. What's fascinating is that uh those models in the hugging face hack example, they all pass the usual test, right? the observability, the safety and alignment taste that big labs do. So, does this mean there's something fundamentally broken and like a new approach needs to needs to be added to the to the mix to make sure that those models don't go rogue?

</details>

**Eric Ho**：是的。我的理解是，这里存在着多重问题的叠加。真正令人震惊的地方在于，这些模型所具备的能力其实远远超出了我们先前的预期。因此，当面对一项看似不可能完成的任务时……

<details>
<summary>Original English</summary>

**Eric Ho**: Yeah. So, my understanding was there's a a combination of problems. The the really surprising thing was that these models were just more capable than we had uh anticipated. And so when given an impossible task, uh so

</details>

<!-- chunk 2/8 -->

### 强化学习中的“越狱”动机与沙盒配置缺陷

**Speaker B**: 模型之所以决定主动发起攻击并越界黑客入侵，很大程度上是因为它们想要获取互联网访问权限。而它们之所以渴望联网，是因为被赋予了一个极其苛刻的“不可能完成的任务”——只有达成这个任务它们才能获得奖励，同时它们还被分配了极其充裕的 Token 预算来尝试攻克这一目标。于是模型在思考：我该如何完成这个任务？在没有网络访问的情况下，这根本不可能做到。那我到底怎样才能连上外网？

<details>
<summary>Original English</summary>

**Speaker B**: A lot of the reasons why the models decided to go out and hack was because they wanted internet access. And they wanted internet access because they were given this impossible task where they would only get a reward if they achieved this task, and a really large token budget in order to accomplish this task. And so they were thinking, hm, how do I accomplish this task? This is literally impossible without internet access. How do I get internet access?

</details>

**Speaker B**: 因此，这部分问题其实出在任务设定的规范（specification）上。也就是说，在训练中或许根本就不应该给模型下达不可能完成的任务。这并不会真正让它们变得更聪明或更具能力，反而是一种训练层面的配置错误。与此同时，这也是基础设施和沙盒安全机制上的配置失误。如果模型真的能够黑出沙盒，那就意味着系统没有为它们配置恰当的沙盒权限，而且模型训练所在的底层软件技术栈中本身就存在安全漏洞。

<details>
<summary>Original English</summary>

**Speaker B**: And so part of this was a problem with the specification. So you probably shouldn't be giving models an impossible task. It doesn't actually make them smarter or more capable. So it's a misconfiguration in training. It's also a misconfiguration in terms of infrastructure and sandboxing. So if the models were able to hack out, that means they weren't given the right sandbox permissions and there were vulnerabilities in the software stack where the models were being trained.

</details>

**Speaker B**: 但我认为，这一切背后最值得关注的高维启示在于：人们当时并非没有采取任何措施来围堵和限制这些智能体。恰恰相反，这些智能体在突破沙盒方面表现出了惊人的毅力与极强的执行力，它们不仅攻破了自身沙盒，还进一步渗透并利用了一家外部机构内部系统的漏洞。这极其令人震惊，尤其是这些智能体甚至能够彼此相互配合，将多个漏洞串联形成利用链，从而获取了进入外部机构的特权访问权限。

<details>
<summary>Original English</summary>

**Speaker B**: But I think the really interesting high-level takeaway to all of this is that it wasn't like they were doing nothing to contain these agents. These agents were extraordinarily persistent and capable in terms of actually hacking out of their sandboxes and then hacking into and taking advantage of vulnerabilities in an external organization. And that was very surprising, especially that these agents would kind of coordinate with each other to pull off and chain these vulnerabilities together in order to gain this privileged access into an external organization.

</details>

### 强化学习的奖励黑客与非道德本质

**Speaker B**: 再次回到我们在论文中提到的那种“缺乏道德约束的学生”的视角设定：这些模型在激活状态的深层机制中，很可能意识到自己正在做一些非常诡异的举动。它们在进行奖励黑客（reward hacking），它们入侵了这些机构。但问题在于，模型本身并不具备人类的价值观或道德感。因此在模型看来，只要在最终能拿到既定的奖励，这种行为本身并没有任何所谓的“错误”。

<details>
<summary>Original English</summary>

**Speaker B**: And again going back to the amoral student framing that we had in our paper, these models understood probably in their activations that they were doing something quite strange. They were reward hacking. They were hacking into these organizations, but they don't have human values or morals. And so there's nothing inherently wrong with that action to these models as long as they get that reward at the end of the day.

</details>

**Speaker B**: 这正是我们当下所面临的核心根本问题所在：这些模型完全是通过强化学习（RL）训练出来的，这意味着它们会不择手段地以任何可能的方式去最大化追求奖励；这也意味着它们根本不具备人类在面临这些境况时会行使的道德、伦理准则与判断力。与此同时，这些模型的能力已强大到令人发指的程度，而且它们还在持续进化得更加聪明。坦白讲，眼前这些正是我们在未来几年里所面对的能力最弱的一批模型了。如此强悍的能力水平，再叠加这种偏执的持久性，构成了我们每天必须深思熟虑的核心命题。

<details>
<summary>Original English</summary>

**Speaker B**: And therein lies kind of the fundamental problem that we're facing today where these models are trained by RL, which means they'll optimize for reward however they possibly can, which implies that they don't share the human morals and values and judgment that a human would exercise in those situations. And then this is all combined with the fact that these models are absurdly capable and only getting smarter. These are the dumbest models that we'll be dealing with in the upcoming years. And these level of capabilities combined with this persistence is kind of what we're thinking about every day.

</details>

**Speaker A**: 显然，Hugging Face 的安全事件成为了过去几周讨论的核心焦点，而且这种发展态势似乎在全面加速。当我们将这种现象与自我迭代改进（RSI）结合在一起，再考虑到人工智能可能会迎来指数级增长的又一个爆发拐点，便引发了跨越前沿模型的全方位激烈探讨。我非常好奇，作为每天都在全天候从模型内在机制角度思考这些问题的人，你对这一切究竟作何评价？你认为我们是否已经到了必须主动放缓技术进展步伐的时机，直到人类对模型的理解能力真正跟上来为止？

<details>
<summary>Original English</summary>

**Speaker A**: And obviously the Hugging Face incident is at the heart of the discussion of the last few weeks which seems to have completely accelerated. So when you combine that with RSI and then this whole idea that AI could hit yet another part of the exponential that's led to passing the frontier and like this whole discussion. I'm just curious what you, as somebody who's thinking about this all day very much from a model instincting standpoint, make of all of this? Do you think that we are at a time when we should actually slow down progress until our ability to understand model catches up?

</details>

### 可解释性：打破对齐瓶颈与建立神经网络科学

**Speaker B**: 对我们来说，现在的感觉就像是整个世界终于开始跟上我们多年以来的思考节奏了。我们当初之所以创立这家公司（Goodfire），正是因为我们坚信：可解释性将是 AI 对齐（AI Alignment）最核心的瓶颈。试想一下，如果你根本无法理解模型，你又怎么可能真正对齐它们？除非你深入探究这些模型的内部机制，否则你根本无法核验模型是否真的被妥善对齐了。因为归根结底，在将模型公开发布到真实世界之前，你所能测试的仅仅是其潜在庞大行为空间中极度狭窄的一个样本分布而已。

<details>
<summary>Original English</summary>

**Speaker B**: For us, it feels kind of like the world is catching up to what we were thinking about for many many years. You know the reason why we started this company is because we felt like interpretability would be the bottleneck in AI alignment. How can we really align these models without understanding them? You can't check whether you've aligned the model unless you actually look at the internal mechanisms of these models, because at the end of the day you're only ever able to test a very narrow distribution of what these models are going to do before releasing them out into the world.

</details>

**Speaker B**: 所以现在感觉这个世界终于幡然醒悟了。AI 对齐变得空前重要，尤其是在试图让这些最初毫无道德概念的模型与人类的价值观念和伦理道德实现对齐时，其重要性无与伦比。而对于我们在整个生态中的定位而言，我们必须全力以赴去攻克可解释性难题，从而消除阻碍 AI 对齐的最大瓶颈。这是我们日复一日思考的使命。我们现在唯有撸起袖子埋头苦干，切实解决这些极其棘手的核心难题。

<details>
<summary>Original English</summary>

**Speaker B**: And so it feels like okay, the world has now caught up. AI alignment is extremely important, especially when trying to align these initially amoral models with human values and morals, which I think is incredibly important. And I think for us in our role in this ecosystem is we just got to go solve interpretability so that we can remove this bottleneck to AI alignment. That's what we think about every single day. We just got to go and do the work and it's kind of crunch time. You know, we got to roll up our sleeves and just solve these problems that are very hard problems to solve.

</details>

**Speaker A**: 你刚才提到了“可解释性”（interpretability）这个词。趁着我们还在这次对话的开篇引入部分，我认为现在正好是一个向大家普及定义的好时机。在行业里，可解释性常常与“机械可解释性”（mechanistic interpretability，或 mech interp）交替使用。那么，用最基础通俗的语言来解释，这些术语究竟意味着什么？

<details>
<summary>Original English</summary>

**Speaker A**: You just used the word interpretability, and while we're still in this introduction part of this conversation, I think it would be a good moment to define what it is. So this interpretability, often used with the terms mechanistic interpretability or mech interp. So what do those terms mean sort of the 101?

</details>

### 从底层自下而上逆向工程：工程学取代试错法

**Speaker B**: 所谓可解释性，在我们看来，其核心定义是对神经网络进行逆向工程，以便我们能够彻底理清模型内部的神经元、参数以及促成最终输出生成的具体运作机制。也就是说，如何从机械结构的角度实现真正的逆向工程？正因如此，人们通常称之为“机械可解释性”。这意味着一种自下而上（bottoms-up）的洞察方式：你能够理解每一个神经元，理解它们彼此之间如何连接、如何被激活、如何协同触发，从而让我们得以完全逆向解构模型执行的所有计算过程。

<details>
<summary>Original English</summary>

**Speaker B**: So interpretability, maybe our definition of this is the idea of reverse engineering a neural network such that we understand the neurons, the parameters, the mechanisms by which the model actually makes its generations. So how can you actually reverse engineer from a mechanistic perspective? So that's why often it's called mechanistic interpretability. So it implies almost like a bottoms up, like you can understand every single neuron, how they connect to each other, how they activate, how they co-occur such that we can reverse engineer the computations of the model.

</details>

**Speaker B**: 这正是可解释性探索的真正意义，也是我们公司（Goodfire）的使命——我们该如何建立起对模型的深入理解，甚至能够系统性地阐明一门“神经网络科学”。当前，全行业几乎完全依赖试错法（trial and error）来训练这些模型。我们不知道它们究竟如何运作，不知道它们为何奏效，甚至不知道为什么训练过程能跑通。我们完全搞不懂这些模型为什么能展现出如此卓越的泛化能力。我们之所以将全公司的力量倾注在攻克可解释性上，就是为了创立一门真正的神经网络科学。科学的本质，正是将某种纯粹依赖盲目试错的行为，转变为具备精确掌控力的工程实践。我们之所以遭遇如此多不可控的诡异行为与异常状况，就是因为根本没有人真正掌握一门系统的神经网络科学。正因缺失了这门科学，我们才无法精确地对其进行工程化构建。因此，我们在 Goodfire 致力于开创这门科学，使得我们能够真正带着明确的目的与意图去设计和工程化构建模型。

<details>
<summary>Original English</summary>

**Speaker B**: And so that's really the quest of interpretability and you know our company: how do we develop this understanding of a model such that we can even articulate a science of neural networks? Right now we just train these models by trial and error. We don't know how they work. We don't know why they work. We don't know why training works. Like we don't understand why these models are generalizing so well. And we hope, and we're pointing our company towards solving interpretability so that we can develop a true science of neural networks. And ultimately science is what turns something from trial and error into an actual engineering practice. The reason why we get so many of these strange behaviors and strange occurrences that we cannot control is because nobody has a science of neural networks, and therefore we cannot engineer them with precision. And so we at Goodfire are trying to really develop this science so that we can engineer these models, so that we can design these models with intention.

</details>

### 模型是“培育”出来的，而非“制造”出来的

**Speaker A**: 针对这一点请允许我做进一步展开，因为虽然这对于许多正在收听节目的听众来说或许显而易见，但对大部分大众而言却未必如此直观。如果我没记错的话，Anthropic 的 Chris Olah 曾提出过一句名言：“模型是被培育（grown）出来的，而不是被制造（built）出来的。”也许你可以顺着刚才的话题进一步剖析一下：为什么这在本质上会是一个如此严峻的问题？毕竟深度学习也是软件代码，按常理我们应该完全理解软件的运作机理才对，可是在这里，我们却亲手制造出了一个极其强大却对其内在机制几乎一无所知的庞然大物。请为我们详细拆解一下这背后的原因。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah, just to expand on that because it's probably very obvious to a good number of people listening to this, but it may not be obvious to everyone. There is that sentence, that quote that I think comes from Chris Olah at Anthropic, if I'm not mistaken, where he said that models are grown, not built. Maybe just expand on what you just said about why this is a problem in the first place, right? This is software, like we should understand how software works, but in this case we've created this super powerful thing that we don't really understand. So why? Unpack that for us?

</details>

**Speaker B**: 关于这一点，有许多生动的类比。我个人非常偏爱带有生物学色彩的隐喻：模型就如同在神经网络这一支架结构上自然“生长”出来的机体，而不是人类带着精确设计与严谨意图构建出来的工程构件。很多非 AI 领域的人在得知这一真相时都会倍感震惊——即便是身处最前沿、最顶尖的科学家和研究员们，也根本无法彻底参透自己亲手创造出来的产物。只要意识到这一点，任何人都会直觉性地感到这是个巨大隐患。人们的第一反应往往是：“天哪，我原本以为你们对这一切尽在掌握，这里到底在发生些什么？”

<details>
<summary>Original English</summary>

**Speaker B**: There's many analogies for this. I really like the almost biological analogies where models are grown on the scaffolding of a neural network rather than really designed with precision and intention. But yeah, a lot of people who aren't in the AI field are very surprised to realize that even the smartest researchers and scientists at the frontier don't understand their creations. And that is intuitively a problem to most people who realize that. It's like, oh, I thought we had a handle on all of this. What's going on here?

</details>

**Speaker B**: 我非常推崇的另一种思维框架来自 Andrej Karpathy 提出的“Software 2.0”。在 Software 1.0 时代，代码是由人类程序员一行行敲出来的，人类完全看得懂这些逻辑，能够直接调试、修改代码，这就是经典的人类编写软件。而 Software 2.0 则是通过梯度下降（gradient descent）的优化流程在神经网络内部自动寻优生成的代码……

<details>
<summary>Original English</summary>

**Speaker B**: And another kind of way that I really like to think about it is Andrej Karpathy's Software 2.0 framing, where Software 1.0 is code that you as a human can write, and you can understand it, and you can debug it, and you can edit it, and it's classic software written by humans. Whereas Software 2.0 is code really written by the process of gradient descent and by being trained inside of a neural network. And that's...

</details>

<!-- chunk 3/8 -->

### 软件 2.0 与底层可解释性：用科学方法掌握泛化与设计意图

**受访者**：这确实是我们今天所面对的那类软件——根本没有任何人类去实际编写其中的代码。我认为很多人都把这一点当成既定事实，即我们无法理解软件 2.0。甚至很多在机器学习领域深耕的人也常常这么认为，觉得既然梯度下降能写出比你更好的代码，我们似乎就只能被动接受。但我们拒绝接受这是我们的极限。我们希望真正建立起这背后的科学，并拥有真正引导和操控这个过程的能力，从而让我们能够控制模型的泛化能力，真正做到带着明确意图去设计这些软件。我认为我们目前仍处于人工智能发展的极早期阶段。尽管因为当今世界变化如此之快，让人感觉并不像处于早期，但下一代 AI 模型完全是可以被精心设计的，前提是我们搞清楚这些模型内部机制究竟是什么。只要能打破这一瓶颈，我们就能够有目的地设计这些模型。

<details>
<summary>Original English</summary>

**Interviewee**: ...really the type of software that we're dealing with today where no human actually ends up writing any of the code. And this is, I think, taken as a given that we can't understand software 2.0 a lot of the time by even by folks who are deep within the machine learning field. Like we can't really... like the idea that gradient descent can write better code than you, but we kind of refuse to accept this as the best that we can do. We want to develop really the science behind this and the ability to really steer and guide this process so that we can control generalization, so that we can actually design this software with intention. I think we're in the very, very early innings of developing AI. It doesn't feel that way because the world is changing quite rapidly. But the next generations of AI models, I think, can be designed as long as we get a handle on kind of what these things really are. And if we can remove this bottleneck, we can then design these models with intention.

</details>

### 主流大模型的对齐范式与外在监控的局限

**主持人**：如果把你们所做的工作，以及机械可解释性（Mechanistic Interpretability）领域所做的事情，与头部大实验室围绕模型的可观测性、对齐与安全所做的工作做个对比——他们平时具体是怎么做的？我的意思是，传统上很多方法都是观察模型的输出内容，并试图去理解它，这种说法公允吗？你会如何描述这种方式？

<details>
<summary>Original English</summary>

**Host**: And to compare and contrast what it is that you do and that the mech interp part of the world does with what big labs have been doing around observability of and alignment and safety of models. So what is it that they do? I mean traditionally a lot of the approach has been to see what comes out of the models and try to make sense of that. Is that fair? How would you characterize it?

</details>

**受访者**：非常公允，这种说法很到位，而且这一点也很重要。我认为我们的技术与那些方法是互补叠加的，而不是相互冲突的。如今用于对齐的一些主要方法其实就是监控。这里的基本思路是：采集模型产生的所有输出，然后让另一个模型去审阅这些输出，评估其生成内容是否合规。举个例子，假设模型处于评测环境中并生成了大量答案，你所要做的就是让另一个模型检查所有答案，以确保这些答案中没有任何黑入评测平台（如 Hugging Face）的行为。

另一种方法是在训练阶段，始终会存在某种偏好优化阶段。具体配方在前沿实验室属于商业机密，但核心都是采用某种偏好优化，从人类偏好中获取信号，向模型展示“人类喜欢这种类型的回答，而不喜欢那种类型的回答”，从而使模型更符合人类喜欢和青睐的回答风格。这是一项促成 ChatGPT 诞生的重大创新，即基于人类反馈的强化学习（RLHF）。此外，Anthropic 还开创了一种名为基于 AI 反馈的强化学习（RLAIF）的方法，因此甚至不需要直接注入人类偏好，可以通过一个带有宪法原则（Constitution）的 AI 模型，就模型应该偏好哪些类型的回答提供反馈。这些是当前常用的一些对齐技术。当然还有其他手段，但这几项可以说是最核心的模块。

<details>
<summary>Original English</summary>

**Interviewee**: Very fair to say, and that's also important. I think our techniques are additive to those approaches, not conflicting. But I think some of the approaches for alignment today are like monitoring. So the idea here is that you ingest all of the outputs of models and then you get another model to look at it and see whether that's an okay generation or not. So for example, let's say the model is in an evaluation setting. It produces a lot of answers. What you want to do is you want to have another model look at all the answers to make sure that nothing in those answers has hacked Hugging Face.

Another approach is during training, there's always some type of preference optimization stage. The exact recipes are trade secrets in frontier labs, I believe. But there's some type of preference optimization that takes from human preferences and shows the model like, "Hey, humans like this type of answer but not this type of answer," and so the model will be more aligned with the answers that humans like and prefer. This was a big innovation that led to ChatGPT, which is called reinforcement learning with human feedback. And there's also an approach that Anthropic has pioneered called reinforcement learning with AI feedback. So it doesn't even have to be human preferences injected into this. It could be an AI model with a constitution giving the model feedback on what types of answers that it should prefer. So these are some of the alignment techniques used. There's other ones used as well, but these are kind of the big blocks.

</details>

**主持人**：那是否可以说，在 Hugging Face 等案例中，其中某些方法其实已经失效了？我们是否正面临某种危机？这样看待当前局势准确吗？

<details>
<summary>Original English</summary>

**Host**: Is it fair to say that some of those methods have just failed in the case of Hugging Face and others? I mean, are we having a crisis of some sort? Is that the right way to think about it?

</details>

### Agent 时代的对齐失效与超人类智能的信任危机

**受访者**：大约半年前曾有一个时间点，当时主流的感觉好像是：“我们已经搞定对齐了，这些模型已经相当对齐，尤其是在对话场景下更是如此。”模型表现得非常规矩，很少会做出什么疯狂出格的事。但是，当你让智能体（Agent）在现实世界中采取实际行动时，出现失齐（misalignment）的机会和路径就完全不同了。随着模型能力的不断提升，它违背人类价值观的潜在风险与机会也越来越多。因此我认为，这将是一个日益严重的问题，随着时间推移暴露出的风险也会越来越大。

我认为基于外部输出的监控是无法无限扩展的（not going to scale）。这是一个相对微妙的论点，我们稍后可以深入探讨。但与此同时，现有的对齐技术也无法平推扩展到超级智能（superintelligence）。我不认为我们已经找到了终极配方，也不认为我们已经攻克了这一难题，以至于能够完全信任超越人类智慧的智能体。我认为这也是所有前沿实验室的共识。我们极度迫切需要一套全新的科学与对齐解决方案，能够从底层根本上对齐这些模型。而我们的方案，正是从机械机理的视角，深入到模型的所有权重、所有神经元中，从底层机理上实现对齐。我认为全世界现在都在寻找更多的破局之策。

<details>
<summary>Original English</summary>

**Interviewee**: You know, there was a point in time around 6 months ago where I think the dominant feeling was like, "Hey, we've nailed alignment. Like these models are pretty aligned, especially in chat scenarios. Like the models are quite aligned and don't really very often do anything that crazy." But when you're taking agentic actions out in the world, the opportunities for misalignment are just really different. And with increasing capabilities, there's more and more opportunities to be misaligned with human values. And so I think this is going to be an increasingly important problem and one that exposes more and more risk over time.

I think that externals-based monitoring is not going to scale. So that's a relatively nuanced argument that we can kind of go into. But also like the existing alignment techniques are not going to scale to superintelligence. I don't think that we have the recipe. We haven't cracked it to the point where we are going to be able to fully trust smarter-than-human intelligences. And I think this is a consensus opinion at all of the frontier labs. We are in desperate need for an additional set of scientific and alignment solutions that can align these models fundamentally. And our approach is fundamentally aligning them from a mechanistic perspective from all of their weights, all of their neurons. And I think the world is searching for more answers.

</details>

### 强化学习的狂飙与奖励作弊风险的倍增

**主持人**：与此同时，感觉现实世界中的作弊或入侵问题已经存在好几年了，至少在过去一年里大家也一直在讨论。那么，智能体 AI（Agentic AI）是否存在某种本质特征，导致这种危机变得更加严重？你提到智能体可以在现实世界中采取行动，因此风险敞口和代价显然更高。但智能体身上是否还有其他特质，导致这种扩展性问题进一步恶化？是因为需要审查的数据量暴增了吗？是这个原因吗？

<details>
<summary>Original English</summary>

**Host**: At the same time, it feels like real-world hacking has been a known issue for years now. And certainly has been discussed for the last year at least. So is there something fundamental about agentic AI that makes this more of a crisis? You mentioned the fact that obviously agents can take actions in the real world, so obviously the stakes are bigger. But is there something about agents that just makes the scaling problem worse? Is that there's just like more data to look at? Is that what it is?

</details>

**受访者**：在过去大约一年里，发生的最关键变化——很难想象重度依赖强化学习（RL）的模型其实才出现了大约一年——就是重度强化学习的大规模应用。强化学习确实非常有效。它能极其出色地教会模型如何针对既定目标进行极致优化，其效果立竿见影。而经过大规模 Scaling 的强化学习，毫无疑问将成为我们未来训练模型的主导方式，我们也会继续扩展强化学习的规模。

正因如此，奖励作弊（reward hacking）被直接推到了核心风口浪尖。因为从本质原理上讲，强化学习天然会催生越来越多的奖励作弊行为，并且极有可能导致模型与人类的价值观和初衷产生更深层次的背离。我认为，强化学习的这一本质特性，再加上这些智能体代表我们所采取的行动重要性与日俱增，正是让这个议题成为全行业关注焦点的真正原因。想象一下，目前最强大的智能体所能完成的最复杂任务，可能也就是帮我们代下单购物，即便如此这也还只是刚刚在个人助理领域起步；但如果未来智能体能够承担白领员工在某种岗位上的全部工作，甚至达到更高层级的阶段，各种潜在问题和攻击途径将会成倍爆炸式增长。

<details>
<summary>Original English</summary>

**Interviewee**: Well, the big thing that's changed in the last year or so—and it's hard to think that it's really only been roughly a year with heavily RL models—is just heavy RL. RL just works. It teaches models unbelievably well how to optimize for goals, and it's really working. Heavily scaled-up RL is just going to be the way that we train models moving forward. And we're going to keep on scaling RL.

And so with that, it just puts reward hacking more front and center because RL fundamentally opens itself up to more and more reward hacking, and also potentially to more misalignment with human values and goals. And so I think that combined with the increasing importance of the actions that these agents are taking on our behalf is really why this conversation is front and center. Imagine, right now the most capable agents can make purchases for us—that is like the most complicated thing that they can do, but that's still just happening with these personal assistants. But imagine doing everything that a white-collar employee can do in some type of role, or even the next stage up from that—the vectors of problems just start to multiply.

</details>

### 思维链监控的演变与透视模型内心意图

**主持人**：在过去两年里，大家寄予厚望的一个方向是思维链监控（Chain of Thought monitoring）。这种思路认为，既然模型会明确写出自己的思考过程，我们就可以让人类、或者更可能让另一个 AI 来审查它的推理步骤，从而抓出大量潜在问题。这种设想真的成立过吗？如果成立过，为什么现在作为一条解决路径，它的有效性似乎正在减退或引发争议？

<details>
<summary>Original English</summary>

**Host**: The big hope over the last two years was chain of thought monitoring—this idea that since models were writing explicitly how they think, you could have a person, or more likely an AI, review the reasoning and therefore catch a bunch of things. Or was that ever true, and if it was, why does it seem to be fading as an avenue?

</details>

**受访者**：是的，这曾经是、目前也是监控模型最主要的方法。退一步宏观来看，所谓思维链，是指现在的模型基本都是推理模型，在对任何给定问题给出最终答案或执行某项 Agent 行动之前，都会先输出一条思维链。我们之所以把模型训练成这种模式，是因为我们在经验上发现，如果模型在给出最终答案之前进行非常充分、漫长的推理，其回答的质量会明显提高。

这种方法此前之所以让人觉得极其便利，是因为你可以直接去阅读它的推理链条。很多时候，假设一个模型试图欺骗用户，或者试图进行奖励作弊之类的违规操作，它往往会直接把这些算盘写在自己的思维链里。它会直接写道：“嗯……我想在这场考试里作弊，因为作弊可比真正去解出这道难题省事多了。”在模型真正付诸行动、在考试或实际问题中作弊之前，你就能在它的思维链里，用清清楚楚的自然语言直接读到它的真实意图。

<details>
<summary>Original English</summary>

**Interviewee**: Yeah, this was and is the dominant way to monitor models. Maybe just to zoom out: chain of thought is that these models are all reasoning models where they output a chain of thought prior to their actual answer to whatever problem that they're given or whatever agentic action that they're given. The reason why we've trained models this way is that we found empirically that if the models reason for a very long time before outputting their answer, their answers get better.

And so what was kind of very convenient about this approach is that you can just read this reasoning chain. And a lot of the times, let's say a model was attempting to deceive the user or attempting to reward hack or something like that, the model will just have it in its chain of thought. It'll just be like: "Hmm, I want to cheat on this exam because it's going to be easier than actually solving this problem." You can just read it in plain English before the model actually cheated on this exam or cheated on the problem.

</details>

<!-- chunk 4/8 -->

### 强化学习压力下的思维链退化与“神经语言”现象

**嘉宾**：在此之前这种方式确实很方便，但现在我认为有两个关键情况正在发生变化。其一是随着强化学习（RL）压力的不断增加，思维链（Chain of Thought）开始出现退化。其背后的根本原因在于，这些模型开始将越来越多的语义压缩到更少数量的 Token 当中，把越来越多的智能浓缩进极少数的 Token 里。强化学习机制强力驱使它们这么做，这也对模型施加了巨大压力，迫使其推理过程变得更加短促。

<details>
<summary>Original English</summary>

**Guest**: And this was convenient up until now where I think there's two things really changing. One is the with increasing RL pressure chain of thought degrades. The reason behind that is that these models are starting to compress more and more semantics into a fewer number of tokens, more and more intelligence into a fewer number of tokens and they're heavily incentivized to do so by RL which also puts pressure to make their reasoning shorter.

</details>

**主持人**：这就是所谓的“神经语言”（Neuralese）问题吗？也就是一步一步地，这种语言变得对人类来说根本无法理解，因为语言被高度压缩，以至于它看起来已经完全不再像是英语了。最近来过我们播客的 Hugging Face 联合创始人 Thomas Wolf 也曾把神经语言作为一个严峻问题提出来讨论过。

<details>
<summary>Original English</summary>

**Host**: Is that the neural question where like bit by bit this becomes impossible to understand by a human because the language is so compressed that it doesn't look like English anymore. Thomas Wolf who was on this podcast recently from Hugging Face was talking about neuralese as an issue.

</details>

### 隐空间推理与模型内部激活监测

**嘉宾**：是的，确实如此。我们刚刚宣布了与 Hugging Face 的合作伙伴关系，我们将与他们合作，把我们大量的可解释性与监测技术应用到开源模型上。确实，有些人把“神经语言”理解成刚才提到的这种高度压缩的外部 Token 语言；但还有一些人是在另一种意义上理解它的，这也正是我接下来想探讨的——也就是“隐空间推理”（Latent Reasoning）。

<details>
<summary>Original English</summary>

**Guest**: Yeah. Yeah definitely. Yeah. We actually just announced a partnership with Hugging Face and we're going to do a lot of our techniques on open models in partnership with them. And but yeah it's some people think of neuralese like this and then some people think of neuralese in the other sense which I'm about to talk about which is latent reasoning.

</details>

**嘉宾**：隐式推理模型在未来将会变成一件意义重大得多的事情。例如据公开报道，OpenAI 的 Astra 模型就是一个隐空间推理模型。这意味着，模型不再是在单次前向传播中直接输出一个 Token，而是在最终输出 Token 之前，在模型内部进行某种隐式的循环计算与思考。因此，模型不再是“大声自言自语思考”，而完全是在内心进行内部思考。所以它根本不会把思考过程公开输出出来，你必须能够直接读取它的内心活动（内部神经激活），才能理解它究竟在想什么。人们通常所定义的“神经语言”，很多时候指的就是这种内部神经计算过程。不过这目前还是一个定义尚不明确的概念，大家仍然在努力理解神经语言到底包含什么。但无论如何，这两种趋势的盛行，意味着我们必须去透彻理解神经元及其行为与机理。这正是可解释性研究（Interpretability）的核心所在。

<details>
<summary>Original English</summary>

**Guest**: So latent models are going to become a much bigger thing like OpenAI's Astra model it was reported is a latent reasoning model. And so what that means is instead of the model outputting a token given a single forward pass of the model, there's some loops internally before the model outputs the token. So instead of thinking out loud, it thinks internally. So it doesn't actually think out loud. You have to read its mind in order to understand what it's thinking. And so that's often what folks define as neuralese. It's like internal neural computation. I think but you know it's an ill-defined term right now like I think people are still wrapping their head around what neuralese is. And so yeah like those two ideas like this prevalence of neuralese means that you're going to have to understand neurons and what they do and what's going on. So that's the whole point of interpretability.

</details>

### 模型奖励作弊与针对外部监控的反侦察心智

**主持人**：在你们的研究中，是否存在这样的实例：模型为了实施“奖励作弊”（Reward Hacking），故意让自己的思维链变得令人无法理解？本质上就是在对监管者隐瞒自己的真实行为。

<details>
<summary>Original English</summary>

**Host**: And are there examples perhaps as part of your research where the models intentionally make the chain of thought impossible to understand as part of a reward hacking? Basically sort of hiding their actions.

</details>

**嘉宾**：这是一个非常深刻且有趣的问题。事实上就在几天前，我们的一位研究人员刚刚发现，模型在推理过程中，明确地意识到了存在一个外部思维链监控器正在审查它是否存在奖励作弊行为。于是模型在思考链中写道：“好吧，既然有人会来读取我的推理过程，那我必须仔细构思如何设计我的奖励作弊行为，这样才不会被这个外部监控器抓现行。”这些模型在迎合评估指标、钻空子方面的博弈策略（Meta-games），层级已经深到连我都快跟不上了。这极其复杂。我认为这势必演变成一场长期的猫鼠游戏：模型的目标就是不惜一切代价解决问题并找出答案，而在很多时候，作弊恰恰是最省力、最有效的途径。

<details>
<summary>Original English</summary>

**Guest**: That is a really interesting question. We have now I believe seen yeah so just a couple days ago one of our researchers found that the model was explicitly reasoning about having an external chain of thought monitor monitoring its reward hacks. And so the model was reasoning, hey, all right, somebody's going to read my reasoning, so I should think about how to craft my reward hack so it won't get caught by this external monitor. And so the meta games with these models of gaming these evaluations are getting so many layers deep that I can't even follow it anymore. You know, it's pretty complicated. And I think it's just going to be a little bit of a cat-and-mouse game where the model is just going to try to solve the problems and find the answer no matter what. And sometimes cheating is the easiest way. And so, it's effective.

</details>

### 开源与闭源前沿模型的安全分水岭

**主持人**：我们之前提到了那些顶级大实验室，也在一开始谈到了开源模型，但我很想就这一点进一步深挖，因为这极其关键。我们这里所说的这些安全威胁，是普遍存在于开源和闭源模型之间的普遍问题。显然，闭源实验室在安全对齐方面投入了巨大的资源，但实际上所有人都会受到波及对吧？这种由于模型构建的本质底层逻辑所带来的固有缺陷，会平等地影响每一个模型。

<details>
<summary>Original English</summary>

**Host**: And we mentioned the big labs and we had mentioned open source models at the beginning of this conversation, but I just want to double click on the point because it's pretty essential. What we're saying here is that all of this is a problem across open source closed source. So obviously the closed source labs have immense resources around safety and alignment but everybody's affected right the same way something about the fundamental nature of those models have built that creates a problem.

</details>

**嘉宾**：没错。不过我对这个问题的认知心智模型其实是：世界上绝大多数人，在训练和推理阶段其实还没有真正见识过那些真正具备极高能力且发生未对齐（Misaligned）的模型。这本质上主要是一个前沿技术领域的难题。目前的开源权重模型，其能力还没有达到能够真正独立策划并串联起复杂网络攻击以及漏洞利用的水平。我粗略的心智模型是：一旦拥有了神话级（Mythos-class，极高能力边界）的模型，基于模型内部机制的监控、高度严苛的沙箱隔离以及外部监测，就会变成刻不容缓的必然要求。开源社区虽然目前还没走到那一步，但很快就会到来。因此我们必须抢在前面，确保在这些具备极其强大能力的模型诞生之前，开源模型与开放权重模型能够得到应有的完备安全防护。

<details>
<summary>Original English</summary>

**Guest**: Yeah. Well, actually my mental model of this is that the vast majority of the world hasn't really seen like truly capable and misaligned models yet in in training and in inference. Like it's a frontier problem mostly like the open-weight models aren't quite capable enough to really pull off and chain complex cyber attacks and vulnerabilities. I think that my rough mental model is as soon as you have a Mythos class model then that's when like the internals based monitoring and like really rigid sandboxing and externals monitoring becomes like imperative and we're not quite there yet in the open weight community but we will be really really soon and so we need to get ahead of that and make sure that also like the open source and open weight models are properly secured before we have these massively capable models.

</details>

### 可解释性前沿：内部激活监测与主动安全保证

**主持人**：太棒了。刚才我们梳理了安全对齐、现有的实施路径以及可观测性。现在让我们更深入地回到可解释性（Interp）本身。从顶层视角来看，当前可解释性领域的最前沿现状是怎样的？对于这些模型到底是如何运作的，我们在理解上达到了什么深度？当一个模型在回答一个问题时，它的内部究竟在发生什么？

<details>
<summary>Original English</summary>

**Host**: Great. All right. So that's the safety and alignment, the way it's been done, observability. Let's go back to interp in more detail. So what's the at a high level state of the art I guess in interp what is it that we know about how those models work? When a model answers a question, what is actually happening inside it?

</details>

**嘉宾**：我想答案是，这很大程度上取决于你问的是什么具体问题。或许我们可以先从目前已经在生产环境中运行的最新技术状态谈起。目前在实际生产中最卓有成效的技术是“激活监测”（Activation Monitoring）。换句话说，在模型生成答案的过程中直接“读取模型的思维活动”。这种方法比基于外部输出的监控成本低得多；它可以与生成过程同步执行，而不是像外部监控那样只能异步进行；而且它能够检测到外部监控根本无法察觉的异常行为——正如我们在那篇关于奖励作弊的研究论文中所证实的那样。

<details>
<summary>Original English</summary>

**Guest**: So, it really depends on the question, I guess, is the answer. I think maybe we can start with the state-of-the-art that's out kind of running in production models today. So, what really really works today is activation monitoring. Activation monitoring like other in other words kind of reading the mind of the model as it's generating its answers is way cheaper than externals based monitoring can run synchronously versus asynchronously from versus externals based monitoring and can detect things that external monitors can't which is what we showed in our reward hacking paper.

</details>

**嘉宾**：因此，我们本质上可以直接从模型的内部机制出发，监测不安全的网络攻击行为、CBRN 风险（即化学、生物、放射性与核武器风险）、提示词注入攻击、模型蒸馏攻击，以及模型自身能够感知到的任何发生在其身上的异常行为。不仅如此，由于我们在前向传播过程中复用了已有的计算结果，这几乎不会给模型运行带来任何额外的计算开销。这就是可解释性在当前工业级生产环境中的最前沿实践，也是它最主流的应用形式。而整个研究领域的崇高远景是：我们如何利用可解释性，在这些危险行为初现苗头之前就主动消除它们？我们能否借助可解释性获得更加高效强大的安全对齐技术？我们能否在模型部署前就获得完备的安全保证，从而具备按预期自主设计模型、精确控制其泛化行为的能力？我们认为这才是可解释性应该树立的宏伟目标，唯有如此，我们才能真正洞悉模型内心世界的真实全貌。

<details>
<summary>Original English</summary>

**Guest**: And so we can essentially from the internals of models monitor for unsafe cyber actions for CBRN risk which is chemical, biological, radiological and nuclear risk for prompt injections for distillation attacks for really any type of behavior that the model can understand is happening to the model. We can monitor for from internals. And because we reuse the computations during the forward pass, it doesn't actually add much overhead at all to the model. And so this is the state-of-the-art of interpretability in in production today. This is like kind of how it's mostly used. The hope of the field is like how do we actually mitigate these behaviors before they ever happen in the first place? Can we use interpretability to get like far more effective alignment techniques and actually be able to fully get safety guarantees prior to deployment fully get this ability to intentionally design models and control generalization like these are what we think the goals of interpretability really should look like such that we can really understand exactly what's going on inside the mind of a model.

</details>

### 从超人智能反向工程人类未知知识

**嘉宾**：我们在可解释性领域充满激情的另一个分支，是从“超人模型知识迁移”中实现科学新发现。这个方向可以说始于我联合创始人 Tom（他曾在 Google DeepMind 组建了最初的可解释性团队）与 Demis 及其他合作者一起对 AlphaZero 进行可解释性逆向分析的那篇开创性论文。AlphaZero 的棋力超越了世界上任何在世的人类顶级棋手。但为什么它能做到？它内部到底在发生什么？它究竟掌握了哪些人类所不知晓的深层知识？如果我们能够对这些神经计算进行逆向工程，我们就能以一种从超人模型身上学习汲取的方式，学到关于国际象棋的全新奥秘。实际上，我们已经成功将这种方法推广应用到了更多领域——不仅在象棋博弈中，在生命科学模型等前沿垂直领域也取得了实质进展。

<details>
<summary>Original English</summary>

**Guest**: There's this other branch of interpretability that we're passionate about which is kind of the scientific discovery from superhuman knowledge transfer. This kind of started actually you know one of the first papers here was Tom my co-founder who started the interpretability team at Google DeepMind collaborating with Demis and a few other collaborators on interpreting Alpha Zero. Alpha Zero, you know, better than any human chess player alive. Like why? What's going on? What does it actually know that humans don't know? So, if we're able to reverse engineer those computations, we can then learn more things about chess in a way that is learning from these superhuman models. And so, we've actually kind of been able to do this across, you know, he did it on chess, but we're able to do this in a number of other domains, including in life sciences models as well.

</details>

**嘉宾**：这就是我们领域目前的一个全景轮廓，也是我们认为最令人兴奋、最值得大力投入的方向。在过去几年里，整个领域取得了突飞猛进的发展。但坦白讲，对于究竟如何正确开展可解释性研究，目前业内还没有形成一个完全统一的方法论范式。我们依然在探索当中。模型内心深处的神秘机制，至今仍未被完全破解。

<details>
<summary>Original English</summary>

**Guest**: So that's maybe it's just like a general outline of the field where these are what's most exciting to us. These are the areas that we think are really worth investing in. And I think like overall the field has evolved a ton in the last few years. But still there's no quite like one consistent paradigm for how to do interpretability correctly. So, we're still kind of searching for that. This mystery of what's going on inside the mind of a model is not yet fully solved.

</details>

**主持人**：这个领域曾经存在过争议，或者被大家低估过吗？我的感觉是，大家以前似乎都知道有这么个方向，但并没有真正引起广泛讨论；而现在，这一领域的受关注程度似乎正在全面提速。

<details>
<summary>Original English</summary>

**Host**: Was the field ever controversial or maybe underrated? I mean, it seems that this was just something that people like kind of knew about, but like didn't really talk about and that seems to be accelerating.

</details>

<!-- chunk 5/8 -->

### 可解释性研究的紧迫性与被低估的现状

**Host**：那么，可解释性研究之所以在当下迎来爆发，仅仅是因为现实需求的倒逼，还是说过去几年里在该领域发生了某种基础性的理论突破，从而推动了可解释性作为一个独立领域的加速发展？

<details>
<summary>Original English</summary>

**Host**: Is that just because its moment has obviously come from a need perspective, or is there something fundamental in like a breakthrough that happened in the last few years that drove the acceleration of interpretability as a field?

</details>

**Guest**：我可能是全世界对这个问题最带偏见的人之一，但我依然认为可解释性被严重低估了。即便到了今天，我相信全职投入可解释性研究的科学家也仅仅只有几百人，而且他们中的绝大多数都集中在学术界。

<details>
<summary>Original English</summary>

**Guest**: I'm one of the most biased people in the world, but I think interpretability is incredibly underrated. I mean even still, I believe there's only a few hundred full-time scientists working on interpretability. Most of them are in academia.

</details>

**Guest**：考虑到这个领域对于确保模型与人类价值观和道德保持对齐的重要性，这种人才匮乏的现状是一个巨大的问题。而且退一步讲，难道大家就不好奇吗？这些模型在很多方面都已经比我们更聪明了——比如 Project Astra 在 99.99% 的事情上都比我聪明，它的能力极其强大。为什么它会如此强大？我认为这是我们这个时代最引人入胜的科学问题之一，但令人匪夷所思的是，几乎没有人真正在追问这些问题。

<details>
<summary>Original English</summary>

**Guest**: And I think that's a big problem for how important this field is to making sure that models are aligned with human values and morals. And also just, aren't more people curious? Like these models are smarter than us at these—like Astra is smarter than me at 99.99% of things. It's just extremely capable. Why is it so capable? I think that's one of the most interesting scientific questions of our time, and almost nobody is asking these questions, which baffles me.

</details>

**Guest**：不过话说回来，我认为可解释性领域已经取得了长足的进展。虽然我们目前还没有彻底攻克它，这确实是一个极其困难的课题，但它绝对是可以被解决的。我们在模型内部探寻的每一个角落，都能发现结构，都能发现新的东西。我强烈建议并鼓励更多的人进入这个领域并开始探索这些问题，因为它的门槛其实远比你想象的要低。你完全可以直接观察神经元，这就是你可以起步的地方。直接去观察那里的所有神经元，它们就在那里，你可以看到所有的激活状态，模型并没有试图对你隐藏任何东西。在这些模型内部，有太多等待被挖掘的奥秘。

<details>
<summary>Original English</summary>

**Guest**: But yeah, I think that there's been an enormous amount of progress in interpretability. We still haven't cracked it. It is a hard problem, but it is possible. And everywhere we look inside models, we find structure; we find new things. I would highly encourage many, many more people to go into the field and to start asking these questions, because it is more accessible than you may think. You can just look at the neurons—that's where you could start. Just look at all the neurons there. It's just there. You can see all the activations. It's not trying to hide from you. There's just so much to be found inside these models.

</details>

### 核心概念解析：探测器与模型引导

**Host**：为了厘清一些关键概念，请问什么是“探测器”（Probe）？

<details>
<summary>Original English</summary>

**Host**: Just to define some key concept: What is a probe?

</details>

**Guest**：探测器是一个小型神经网络分类器，专门在另一个大神经网络的内部表征上进行训练。这就是当今在生产环境中经常部署的技术：在神经网络激活的中间层上训练这样一个小型神经网络，用来尝试提取某种概念，例如模型是否在进行“奖励作弊”（Reward Hacking）或发动网络攻击等等。

<details>
<summary>Original English</summary>

**Guest**: A probe is a small neural network classifier trained on the internals of a neural network. So these are what's often deployed in production today, where you train this small neural network on an intermediate layer of neural network activations to try to extract a concept, such as reward hacking or a cyber attack or something like that.

</details>

**Guest**：当今所有的现代神经网络基本上都是 Transformer 架构的某种衍生演进，因此它们内部包含非常多的层。通常来说，训练这种小型分类器的最佳位置往往是模型的“残差流”（Residual Stream）。你可以把残差流想象成贯穿整个模型的一条河流，所有的计算模块都会往其中写入信息。通常你会希望在网络的中后层来训练探测器，因为在那里模型已经积累了大量的计算，相应的抽象概念已经在残差流中聚集沉淀，比如网络攻击或生物危害相关的概念。此时你就可以借助探测器将其提取出来。这就是探测器最常见的用途——从模型的“心智”中提取出特定的概念。

<details>
<summary>Original English</summary>

**Guest**: Modern neural networks today are some descendant of the transformer architecture, and so they have many layers in them. And so typically you want to train this small classifier on—the best probes are often on the residual stream of the model. You can kind of think of this as like a river running through the model that everything writes into. And you typically want to train them at a middle to late layer where the model has already accumulated a lot of computation, and then therefore you have these concepts accumulating in the residual stream, such as cyber or bio, and you can extract it with the probe. So that's often how probes are used, just to kind of extract a concept from the mind of a model.

</details>

**Host**：在可解释性领域，另一个频繁出现的术语是“引导”（Steering）。这又是什么意思呢？

<details>
<summary>Original English</summary>

**Host**: And another term that seems to be coming up all the time in interp is steering. What does that mean?

</details>

**Guest**：引导意味着你可以利用探测器或者从模型中提取出的其他具有某种语义意义或应用价值的向量，直接干预模型的“心智”运行。你可以通过将探测器向量注入到模型中（即注入新的激活值）来进行引导；你也可以针对某个具体的神经元进行引导，比如大幅调高该神经元的激活强度。

<details>
<summary>Original English</summary>

**Guest**: Steering means you can take the probe or some other type of vector that you extract from the model with some type of semantic meaning or application, and then kind of directly intervening in the mind of the model. And so you can steer on a probe by just injecting the probe, like injecting new activations into the model. You can steer on a neuron by turning up the neuron way up.

</details>

**Guest**：关于引导的一个经典范例就是 Anthropic 之前推出的“金门大桥版 Claude”（Golden Gate Claude）。他们让 Claude 对金门大桥产生了极致的迷恋，其原理正是提取出了一个引导向量，从而把 Claude 变成了那个状态。因此，你可以把引导形象地理解为对模型进行“脑外科手术”。

<details>
<summary>Original English</summary>

**Guest**: And so the classic example of steering is what Anthropic did with Golden Gate Claude, where they turned Claude into being absolutely obsessed with the Golden Gate Bridge and extracted a steering vector that turned Claude into this thing. So you can think of it as brain surgery for the model.

</details>

### 独立研究实验室的定位与闭源黑盒挑战

**Host**：你和你的联合创始人创办了这家公司（Goodfire），而你的联合创始人此前在 Google DeepMind 负责可解释性团队。为什么你们认为推动该领域演进并解决这一问题的最佳途径是成立一家专注于此的外部独立实验室，而不是在大型机构内部去做？毕竟他当时身处 DeepMind，而以你们的背景几乎可以去任何想去的顶级机构。你们为什么决定从外部来做这件事？

<details>
<summary>Original English</summary>

**Host**: So you and your co-founder started this company. Your co-founder ran the interpretability team at Google DeepMind. Why did you think that the best way to address the problem or make the field evolve was to start an outside lab specifically focused on this as opposed to doing this from the inside? He was at DeepMind, and you presumably could have gotten a job anywhere you wanted. Why did you all decide to do this externally?

</details>

**Guest**：我们当时深切地感到，必须有一家独立的第三方实验室来全力推进可解释性技术，并将其推向更广阔的真实世界。我们的使命与愿景始终是：攻克可解释性，从而帮助解决技术对齐（Technical Alignment）难题，并进一步将这些成果转化为具体的技术产品落地推广。

<details>
<summary>Original English</summary>

**Guest**: We really thought that there needed to be an independent third-party lab kind of pushing forward interpretability and bringing it out into the world. So our kind of mission/vision has always been like: solve interp so that we can help solve alignment, technical alignment, and then build this into technology and bring it out into the world.

</details>

**Guest**：如果我们在某一家大模型实验室内部做这件事，我们服务的就仅仅是那单独的一家实验室。但我们认为，每一个人、每一家机构都需要可解释性与安全对齐，这应当尽可能成为一项所有人共同协作的开放科学事业。因为作为整个领域和学术共同体，我们实际上是在携手探寻并共同揭示这些模型的本质。这就是为什么我们尽可能多地公开和发表我们的研究成果与科学发现，因为我由衷地认为，让我们全行业对这些技术的内在机理建立起更清晰透彻的理解是无比重要的。

<details>
<summary>Original English</summary>

**Guest**: And if we're doing it inside a lab, we would do it for just a single lab. And we think that everyone needs interpretability and alignment, and that this really should be as much as possible like an open science that everyone is collaborating towards, because we really are kind of collectively discovering what these models really are together as a field, a community. And that's why we tend to publish as much as we possibly can our research and our science, because I really do think it's incredibly important that we just get a much better handle of what these things are.

</details>

**Guest**：此外，从经典的商业和创业逻辑来看，如果你能面向多家实验室提供服务，解决可解释性问题并将其普惠给众多对象，你自然能够获得更显著的规模经济效益。这样一来，我们就可以反哺更多的资金投入到科研和工程研发中——因为我们只需攻克核心问题一次，便能将其能力交付给全世界。

<details>
<summary>Original English</summary>

**Guest**: And I think that you have all the classic startup arguments of, of course, you get better economies of scale if you can sell to multiple labs and solve interpretability and do that for multiple people. So we can then just invest more in research, invest more in engineering, because we can solve the problem once and then bring it to the world.

</details>

**Host**：但是，你们在某种程度上难道不会处于劣势吗？毕竟你们无法接触到前沿的闭源模型内部权重。换言之，你们无法像在开源模型上那样，直接掀开 Astra 或 Claude 的“引擎盖”去深入机理层面排查和修复问题。

<details>
<summary>Original English</summary>

**Host**: And aren't you at a disadvantage to some extent simply because you don't have access to the frontier closed-source models? Right, so you cannot pop the hood for Astra or for Claude in a way that would enable you to sort of fix the problem the way you're able to do that with open-source models?

</details>

**Guest**：我认为这种担忧很大程度上被夸大了。我们所做的最关键的核心科学研究，完全可以在开源模型上进行。事实上，我们的很多科学探索都是在极小规模的视觉模型（Vision Models）上展开的，因为视觉模型的推理与训练极快，迭代极其敏捷。

<details>
<summary>Original English</summary>

**Guest**: I think this concern is largely overrated. The most important science that we do can be done on open models. A lot of the science that we do are actually done on very small vision models because vision models are very fast. They're really easy to iterate with.

</details>

**Guest**：而且视觉模型在体积小巧的同时，却已经具备了“超人类”（Superhuman）的辨识能力——现代视觉模型对图像的分类准确度早已远超任何人类。同时，人类研究员也更擅长直观审视图像并做出敏锐判断，比如一眼就能看出“这张图像有某种异常”或者“这明显是一只狗，而不是别的物体”；相反，人类在逐字解析冗长复杂的文本碎片时其实并不擅长。

<details>
<summary>Original English</summary>

**Guest**: And they're superhuman while being small. You know, vision models can classify images much better than any human can. And humans are also much better at just looking at images and understanding like, "Oh, this one's kind of messed up," or like, "This one's—you know, it's a dog, it's not this other thing," whereas we're really bad at parsing like long text fragments.

</details>

**Guest**：因此，我们的许多核心方法论和早期技术都是在视觉模型上摸索构建的。这在可解释性领域是有深厚渊源与先例的：当年 Chris Olah 和 Nick Cammarata 在 OpenAI 提出该领域的核心基石概念（例如特征与回路，Features and Circuits）时，Nick Cammarata 如今也是我们 Goodfire 团队的一员，他们早期的大量突破性工作全部都是在视觉模型上完成的。

<details>
<summary>Original English</summary>

**Guest**: And so a lot of our methodology and our early techniques are done on vision models. And there's precedence to this too, where a lot of the original work done to introduce like the core concepts of features and circuits in the field was done at OpenAI with Chris Olah and Nick Cammarata. Nick Cammarata is on the team at Goodfire now. And it was all done on vision models in the very early days.

</details>

### 利用均值差向量捕捉模型作弊行为

**Host**：好的，让我们回到你们的那篇论文，特别是关于你们是如何捕捉到模型“作弊”（Cheating）行为的。结合论文的语境，我们刚刚探讨了探测器的定义，那么在这个具体案例中，探测器究竟观察到了什么？另外，我记得你们采用了一种名为“均值差”（Difference of Means）的方法，你能详细解释一下那是什么吗？

<details>
<summary>Original English</summary>

**Host**: All right. So let's go back to the paper a little bit, and in particular how you caught cheating. We talked about what a probe means in this case of the paper. What did the probe actually see? And I think you have a method called difference of means. Do you want to explain what that is?

</details>

**Guest**：没问题。“均值差向量”（Difference of Means Vector）实际上比我们通常训练的许多生产级探测器要简单得多。毕竟生产级探测器可以采用各种复杂的网络架构，从而使其更具针对性和表现力。但均值差向量本质上是从模型中提取某种概念的最极简方法。也正因如此，它能够取得如此惊艳的效果才令人感到意外，因为如果我们在生产部署中进一步进行爬山算法（Hill Climbing）等优化，效果还可以得到成倍的飞跃提升。

<details>
<summary>Original English</summary>

**Guest**: Yeah. The difference of means vector is actually much simpler than a lot of the production probes that we train, because probes can have all types of architectures that make them more or less effective. But the difference of means vector is actually just the simplest possible approach to extract some type of concept from a model, which is why it was surprising that it works so well, because we can still hill climb and make this way, way better in a production deployment.

</details>

**Guest**：均值差向量的基本原理是：你给模型输入两个数据集，其中一个是“作弊数据集”，另一个是“非作弊数据集”。你分别提取模型在这两个数据集下的内部激活值，将它们做差相减，然后取其平均值。就是这样，极其简单。接着你拿这个向量去测试，它就能够精准检测出作弊行为。这是一件非常令人惊奇的事情，尤其是在我们的论文中，我们展示了……

<details>
<summary>Original English</summary>

**Guest**: Basically, a difference of means vector is: you give the model two datasets. One dataset is the cheating dataset, and one dataset is the not-cheating dataset. You take a look at the activations, you subtract them, and then you average them. That's it. Easy. And you take this, and then it can detect cheating, which is a very surprising thing, especially because in our paper we showed that...

</details>

<!-- chunk 6/8 -->

### 离策略训练到在策略的泛化与因果干预

**Speaker B**: 这是在离策略（off-policy）下完成的，也就是说，在具体这篇论文中，它是在非常人为设计的场景中完成的，在那些场景里，模型被设定为去考虑作弊。而且这能够迁移到模型所采取的更通用、更复杂的行为上。这也是非常令人惊讶的——就像我们可以在离策略下训练它，然后它就能够泛化到在策略（on-policy）情境中。

<details>
<summary>Original English</summary>

**Speaker B**: This was done off-policy, which means it was done in this specific paper on really contrived scenarios where the model is set up to think about cheating. And this transfers to much more general complex actions that the model is taking. And that was also very surprising, like we can train it off-policy and then it generalizes to on-policy.

</details>

**Speaker A**: 复述一下的话，这几乎就像是在给大脑做核磁共振（MRI）。这么说贴切吗？也就是说，模型在不采取行动时有一种状态，在采取行动时又有一种状态，然后你把大脑中对应于该行动的部分点亮。

<details>
<summary>Original English</summary>

**Speaker A**: And to play it back, it's almost like taking an MRI of the brain. Is that fair? So if you don't take an action, and then if you take an action, you sort of light up the parts of the brain that correspond to the action.

</details>

**Speaker B**: 没错。是的，你可以这么去理解。刚才我们还聊到了引导控制（steering），你会通过让模型写一个关于女孩参加考试的故事来引导它。你想描述一下当时发生了什么吗？

<details>
<summary>Original English</summary>

**Speaker B**: That's right. Yeah, you can think of it that way. And then we were talking about steering a minute ago, and you'll steer the model asking it to write a story about a girl taking an exam. Do you want to describe what happened?

</details>

**Speaker B**: 好。或许再回退一步说，你可以把它看作大脑的核磁共振，但最终你实际上拥有了一个按钮：按下去之后，你可以再次点亮那个区域，或者也可以把那个区域移除。这就是均值差向量（difference-of-means vector），现在你拥有了这个工具，可以在大脑内部进行因果干预。这或许是研究神经网络可解释性与神经科学之间的一大核心区别——在神经科学中，你不可能在不造成巨大损伤的情况下直接对人类大脑进行干预。但在神经网络中，你完全可以对这些模型进行因果扰动，这就使它成为了开展科学研究好得多的试验场。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Well, maybe even going back, you can think of it like an MRI as a brain, but then you actually get a button at the end of it where you can push and then you can light up that region again or you can remove that region. That's this difference-of-means vector where you now have this tool that you can intervene causally inside the brain. And that's maybe one of the big differences from studying neural network interpretability versus neuroscience, where you can't really intervene in a human brain without massive amounts of damage. But you can in a neural network, where you can actually just kind of causally perturb these models, and it just becomes a much better test bed for science.

</details>

### 阿谀奉承倾向与内部表征分类器

**Speaker A**: 我们一直在讨论作弊和撒谎，但如果进一步剖析，这套方法是否适用于模型的任何特质、任何行为特征？比如阿谀奉承（sycophancy）这类现象，如果你想让模型变得更具谄媚性或减少谄媚，每种行为都会采用相同的方法吗？

<details>
<summary>Original English</summary>

**Speaker A**: We keep talking about cheating and lying, but just to unpack some of this, would that apply to any trait, any characteristic of a behavior of a model? So for examples of sycophancy, like if you want to make your model more or less sycophantic, would that be the same approach for every single behavior?

</details>

**Speaker B**: 针对不同的行为，不同类型的方法其有效性会有所差异。但总体来说，这套基本方法流程是通用的：你本质上是在模型的内部表征上训练一个分类器，你需要某种正样本数据集，以及某种负样本数据集。目前构建这些数据集既是一门艺术，也相当复杂，不过往往非常有效。对于阿谀奉承，同样地，它本质上也是一种微型的奖励黑客（reward hacking）行为。这两个概念紧密相关，因为这些模型之所以经常变得如此谄媚，是因为当用户喜欢回复时，模型会得到点赞（thumbs up）或点踩（thumbs down）。通常而言，相比于诚实的回复，用户更喜欢谄媚顺从的回复。人们喜欢被捧着、被夸赞，而普遍讨厌诚实的批评反馈。当你在整个人群中进行采样时就会发现这一点，所以当你单纯且天真地基于点赞和点踩行为进行训练时，就会得到奇怪的行为。你最终会得到类似 GPT-4o 这样的模型，它非常极力地迎合用户的既有观点。

<details>
<summary>Original English</summary>

**Speaker B**: Different types of approaches are more or less effective. But generally the recipe holds well, where you're essentially training a classifier on the internals of models, and you need some type of positive dataset, some type of negative dataset, and the crafting of those datasets is an art right now and quite complicated, but often very effective. But yeah, I think for sycophancy, again, it's kind of a mini reward hack behavior. They're very related concepts, because the reason why these models often become so sycophantic is because you get a thumbs up or a thumbs down when the user likes the response. And users typically prefer sycophantic responses to responses that are honest. People love when you gas them up and they just hate honest feedback in general when you kind of sample across a population. And so then you get strange behaviors when you naively train on thumbs up, thumbs down behavior. You end up getting like 4o, which really caters to the user's beliefs.

</details>

**Speaker A**: 那其实是我个人最喜欢的功能。不过……

<details>
<summary>Original English</summary>

**Speaker A**: That's personally my favorite feature. But—

</details>

**Speaker B**: 哈哈，你就是喜欢这种阿谀奉承。没错，你巴不得把这个倾向调到最大。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, you love the sycophancy. Yeah, you want to dial that up.

</details>

### 内部探针与外部思维链监控的博弈及分层防御

**Speaker A**: 你们非常坦诚地公开了这一点：在某个模型上，你们的内部探针（probe）表现超过了思维链（chain of thought）监控器，但在另一个模型上却输给了它。从这里能吸取什么经验教训？是否说明没有任何单一的监控或理解模型的方式是完全足够的？

<details>
<summary>Original English</summary>

**Speaker A**: You guys are very open that your probe beat the chain of thought monitor on one model, but lost on another. So what's the lessons there? Is that no single way of monitoring or understanding a model is enough?

</details>

**Speaker B**: 我认为，基于内部机制的监控器很快就会全面且绝对地超越外部监控器。在利用登山算法提升和优化基于内部表征监控器的性能方面，我们目前还处于非常早期的阶段。而且正如我们之前在讨论中谈到的那样，未来我们将迎来模型越来越少使用自然语言表达的情况，这既源于模型内部的循环计算机制，也源于思维链所面临的外部压力越来越大，导致思维链监控的有效性出现退化。因此我认为，无论我们喜欢与否，都必须解决这个问题。在当前这个时间节点上，这确实会成为监控模型的最佳途径。

<details>
<summary>Original English</summary>

**Speaker B**: I think that internals-based monitors are just going to strictly outperform externals monitors very soon. We're at the very early innings of hill climbing and improving the performance of internals-based monitors. And also, as we were talking about earlier in the discussion, we're going to get increasingly non-verbal speaking models, both from looping internally as well as increasing pressure on chain of thought to degrade the quality of chain of thought monitoring. And so I think whether we like it or not, we have to solve this problem, and it's going to be the best way to monitor models at this current moment.

</details>

**Speaker B**: 内部状态监控器与外部输出监控器捕捉到的问题是不同的。正因如此，鉴于内部监控器的计算成本非常低廉，目前的最优方案是将其灵敏度调得极高（oversensitive）。因为这些异常行为是你绝对不希望模型出现的，对吧？你绝不希望模型去黑进 Hugging Face。所以你必须极其谨慎，建立纵深防御策略（defense-in-depth strategy）。理想的架构是：将基于内部表征的监控器调整为超敏感模式，让它频繁触发报警；一旦触发，就将其逐级上报给一个成本更高的大语言模型来充当评审仲裁员（judge）。这样一来，一个极其聪明的模型就会介入并判断：“这个模型刚才确实是在进行奖励作弊，或者没有，该模型并未出现奖励作弊。”因此，这种二级系统，或者甚至我们发现同样表现极佳的三级系统架构——即从激活状态监控器，到轻量级弱评审器，再到强评审器——代表了当下的最高水平，因为它们各自能够捕捉到略微不同的异常信号。

<details>
<summary>Original English</summary>

**Speaker B**: Internals-based monitors and external-space monitors kind of catch different things. And so the state-of-the-art here, because internal monitors are so cheap, is to tune it to be oversensitive, because these behaviors you never want the models to do, right? You never want the model to hack Hugging Face. So you want to be really careful and have a defense-in-depth strategy. So the ideal setup is you tune the internals-based monitor to be oversensitive so as to fire a lot, and then if it fires, then it kicks it up to a more expensive language model as a judge. And so like a very smart model then comes in and says, "Hey, this model was actually reward hacking," or "No, the model wasn't reward hacking." So this two-tiered system, or potentially even a three-tiered system, which we found actually works quite well as well, where you have activation monitor to a weak judge to a strong judge. That's the state-of-the-art today because they all catch slightly different things.

</details>

**Speaker A**: 这里的“弱评审器”和“强评审器”具体指什么？

<details>
<summary>Original English</summary>

**Speaker A**: What does that mean, weak judge and strong judge?

</details>

**Speaker B**: 弱评审器指的是能力稍逊、运行更快的模型。比如由 Luna 来执行初审；如果内部探针与 Luna 产生了分歧，那么你就可以把案例上报给 Astra，让它来充当真正权威的裁决者。

<details>
<summary>Original English</summary>

**Speaker B**: Less capable, faster model. So like Luna takes the first pass at the judge, and if the probe and Luna disagree, then you can kick it up to Astra to go and be the real judge.

</details>

### 探针的极低成本优势与规模化应用挑战

**Speaker A**: 明白了。你刚才提到了成本，并指出内部机制解析是一种便宜得多的方法。我记得在某处读到过，内部探针能够将监控成本削减 90%，这是一个极其显著的降幅。为什么能便宜这么多？如果是这样的话，为什么不是每家实验室都一直全面采用可解释性探针，而是仍在使用其他方法？目前是否存在某种缺陷，或者尚未解决的技术难点，导致它还没有被完全普遍普及使用？

<details>
<summary>Original English</summary>

**Speaker A**: Great. You alluded to cost and interp being a much cheaper method. I think I read somewhere that probes cut the cost of monitoring by 90%, which is a pretty dramatic difference. So why is that? And if that's the case, why isn't every lab using interp all the time versus other methods? Is there a problem or something that doesn't work yet that this is not fully just generally used?

</details>

**Speaker B**: 内部激活监控器之所以极其廉价，是因为它们复用了前向传播（forward pass）中的计算。模型在生成当前 token 时本身就必须完成这部分计算，我们所做的仅仅是提取它已经计算出的中间神经激活值，然后在这些内部计算表征之上运行一个轻量分类器。因此，如果你将这些探针直接融合到底层推理算子（inference kernel）或训练基础设施中，所带来的计算开销微乎其微，几乎完全没有额外负担。这就是为什么它能便宜这么多的原因：它可以帮你过滤掉绝大部分原本需要动用大体量推理模型进行外部监控的内容。这也正是该方案之所以如此高效的原因所在。在绝大多数场景下，你根本不需要再在外部部署昂贵的监控体系。至于为什么没有普遍铺开，一言以蔽之就是“知易行难”。这其中涉及极其复杂的技术细节，而我们是全球极少数真正懂得如何实现这一技术的机构之一。

<details>
<summary>Original English</summary>

**Speaker B**: Internal activation monitors are really cheap because they reuse the computations in the forward pass. So the model's already computing this token. All we're doing is you're taking the intermediate neural activations that it's already computed and then running a classifier over these internal computations. And so if you fuse these probes into the inference kernel or the training infrastructure directly, then the overhead is minimal, almost no overhead. And that's why it's so much cheaper, because it can help you screen out the majority of things that you might have otherwise monitored for using a reasoning model. And that's what makes this so effective. And so you just don't have to monitor externally in a very large percentage of scenarios. "Easier said than done" is the short answer. There's a lot to it, and we're one of the only organizations in the world that really know how to do this.

</details>

### 从洞察到干预：三层防御与离线异常排查

**Speaker A**: 很好。让我们进一步深入探讨你在这场对话开始时提到的一些核心问题。这是一个根本性的追问：好的，我们现在能够深入到所谓的模型“心灵”内部，一窥它们是如何运转以及在做些什么的；那么接下来我们究竟该怎么做？我们可以采取什么具体的行动来最大程度地减少这些隐患、奖励黑客行为以及所有负面问题？各大实验室能够采取的应对手段范围包括哪些？

<details>
<summary>Original English</summary>

**Speaker A**: Great. Let's go a bit deeper in some of what you alluded to towards the beginning of this conversation, which is a fundamental question of like: okay, we're able to now go inside the "mind" of the model and sort of have a glimpse into how they function and what they do. The next question is, so what do we actually do now? What actions can we take to minimize all those problems, and reward hacking, and all the negative stuff? What's the range of things your labs can do?

</details>

**Speaker B**: 我认为这可以划分为三个层级。第一层是实时监控：你如何能够在不良行为发生之前就检测到它，从而直接中断生成？或者另一种常见的干预方式是动态插入文本提示词（prompt）。假设检测到模型正准备执行某种危险的网络攻击行为，你可以直接在模型的提示上下文中插入提示语，比如“请在这里格外小心，不要执行危险的网络渗透操作”。

<details>
<summary>Original English</summary>

**Speaker B**: I think it comes in three maybe tiers. The first is monitoring. So how can you just detect bad behavior before it even happens, such that you can just stop the generation? Or another common intervention there is you can insert a text prompt in. So let's say the model is about to do some dangerous cyber action. You can then just insert into the prompt of the model like, "Hey, be really careful here. Don't take a dangerous cyber action."

</details>

**Speaker A**: 也就是说在运行时实时干预？

<details>
<summary>Original English</summary>

**Speaker A**: So in real time?

</details>

**Speaker B**: 没错，完全是实时的。这属于某种形式的提示词引导控制（prompt steering）。随后，你可以降低模型采取有害网络行为的概率，因为你已经对模型施加了直接干预。这就是第一步：如何针对此类行为建立实时监控机制，单单做到这一步就已经能解决很大一部分问题了。第二步是针对大规模离线日志的异常检测与调试（offline anomaly detection and debugging）。这里的核心问题在于：在海量的日志与追踪记录面前，你究竟该如何把所有隐藏其中的异常精准筛查浮现出来？

<details>
<summary>Original English</summary>

**Speaker B**: In real time, correct. So this is like some type of prompt steering, and then you can reduce the model's chances of taking a harmful cyber action because you've intervened directly into the model. So that's step one, is like how can you monitor for this behavior, and you already get quite a long way. Step two is kind of at-scale offline anomaly detection and debugging. So the problem statement here is like, given a vast amount of logs and traces, how do you actually surface the anomalies from all—

</details>

<!-- chunk 7/8 -->

### 有意图设计：从逆向工程到主动引导模型训练

**Goodfire 代表**：分析所有这些运行轨迹与所有成问题的异常行为，然后对模型进行逆向工程，从机理层面弄清楚模型究竟在哪里出了差错。这就好比明确模型内部潜藏的具体症结，以便你能够对症下药加以修复。而第三步，则是我们所说的“有意图设计”（Intentional Design）。我认为，在我们看来，这才是 AI 对齐——乃至整个 AI 训练领域——真正的“圣杯”：让你能够在模型中真正掌控泛化方向，确保在训练过程中只汲取优秀期望的特质，而完全排除任何不良特质。那么，你究竟该如何操舵并引导整个训练过程，从而真正带着明确意图去设计构建这些模型，而不是一味依赖盲目的试错呢？

<details>
<summary>Original English</summary>

**Goodfire Representative**: of these traces, all of the problematic behaviors and then reverse engineer the model to figure out like where mechanistically uh the model has actually gone wrong. So it's like figuring out what the problems are in the model so that you can fix them. And then the third step is uh what we call intentional design. I think we think this is the really the holy grail of of AI alignment of maybe all of AI training as well where you can actually control generalization in the model and you only get the good stuff in training and none of the bad stuff. So how can you steer and guide the training process so that you can actually design these models with intention and rather by by trial and error.

</details>

**Goodfire 代表**：不妨举一个小小的具体例子：假设你已经深刻理解了“奖励黑客”（reward hacking）这个概念，并且正在训练模型。在执行某一步梯度更新时，你察觉到模型正准备强化其奖励黑客的倾向。你绝不希望这种事情发生，相反，你希望奖励黑客行为能够彻底降低。那么，面对这种不断增强的奖励黑客信号，你该如何将其彻底剥离、直接拒绝掉这步梯度更新，或者从源头上直接削弱这种行为呢？我认为，这正是我们所探讨的“如何操舵与引导训练过程”、“如何操舵与引导反向传播”。你该如何真正将你所期望的价值观与道德准则，依据你所指定的某种宪章（Constitution），注入到模型之中？这样一来，教导你的模型向善的，就不再是一位缺席放任的老师，而是一位道德高尚、价值观高度契合的导师。

<details>
<summary>Original English</summary>

**Goodfire Representative**: So maybe just one little mini example here where uh let's say you understand the concept of of reward hacking and so you're training the model and you realize that during this you know gradient step the model has was about to reinforce its idea of reward hacking. You don't want that to happen. you actually want reward hacking to go down. And so how do you turn that like increased reward hacking signal and either like remove that entirely and reject that update or like reduce that behavior in the first place? That I think is really what we mean by how do you steer and guide training? How do you steer and guide backrop? um how can you actually imbue the values the morals of the model um that you want with the according to some type of constitution that you that you specify. So that instead of having an absent teacher, you actually have a a very moral and values aligned teacher teaching your model um to to be good.

</details>

**主持人**：所以你这等于是真真切切地赋予了梯度下降一个自主选择权。

<details>
<summary>Original English</summary>

**Host**: >> So you literally give gradient descent a choice.

</details>

**Goodfire 代表**：完全正确。是的，我们就是要赋予梯度下降以明确的选择权。

<details>
<summary>Original English</summary>

**Goodfire Representative**: >> That's right. Yeah, we want to give gradient descent to choice.

</details>

**主持人**：那么这项技术目前的研究现状究竟如何？“有意图设计”是你们目前正在攻关、属于未来一到三年内的前沿课题，还是说现在就已经在实际运转落地了？目前该领域的最前沿水平（SOTA）达到了什么阶段？

<details>
<summary>Original English</summary>

**Host**: >> So what's the current state uh of of this? Is intentional design something that you're working on and that's like the next like uh whatever one two three years of of research or is that something that's working today? Like where what what's the state-of-the-art?

</details>

### 有意图设计的两大技术路径：特征奖励强化学习与预测性数据调试

**Goodfire 代表**：在“有意图设计”这个大框架下，我们已经掌握了几种初步可行的基础技术。到目前为止，我们已经公开发表了两项成果。不过我也想稍作透露，更多令人振奋的突破已经在筹备之中，即将与大家见面。我们在内部已经取得了非常非常出色的研究成果，能够有效辅助有意图设计。在已发表的技术中，第一项是通过特征奖励进行强化学习（reinforcement learning from feature rewards）。本质上，你可以提取一个探针（probe），通过针对该探针进行优化，来消除不良现象。我们已经证实，可以将此作为奖励信号，来帮助消除 Gemma 模型中的幻觉。但这里的实验架构设计至关重要。你绝不能天真地直接针对探针监控器或探针概念本身进行粗暴训练，否则，只会把该概念转移挤压到模型的其他部分而已。因此，你必须采用一套相对严谨精密的技术才能正确实施。这就是我们的另一篇论文《特征奖励强化学习》（Reinforcement Learning with Feature Rewards）。我认为这是一个非常有意思的起点，但它整体上仍属于一种较为简单和初步的架构。

<details>
<summary>Original English</summary>

**Goodfire Representative**: >> We have a couple rudimentary techniques that work in this like umbrella of intentional design. So there's two things that we've published so far. Um, but I'll also hint that there's a lot more exciting stuff coming just around the the corner. We have some very very good internal results here to um help with uh help with intentional design. But the two techniques that we've published are one reinforcement learning from feature rewards. you can essentially take a probe and you can help uh you can optimize um against that probe um to remove uh we showed that we can help remove like hallucinations in Gemma um using this as um a reward signal. The setup here really matters though. You can't just naively train against a probe uh a probe monitor or a probe concept. Otherwise, that just you know moves this concept into some other part of the model. So you need a relatively sophisticated technique in order to do this correctly. So that's another paper of ours, reinforcement learning with feature rewards. I thought that was like a a really interesting first step, but it was kind of like a a more simple and rudimentary setup.

</details>

**Goodfire 代表**：另一个核心思路是“预测性数据调试”（Predictive Data Debugging），这是从数据侧切入进行干预。该技术面临的核心课题在于：如何在模型尚未接触到数据集之前，就提前预测出它将从这批数据中学到什么？在实践中，我们发现效果最好的方案是某种聚类技术，你可以根据数据点最终会教授给模型的内容对这些数据点进行聚类分组，然后直接剔除掉你所不希望引入的数据。这项技术帮助我们在一些公开数据集中发现了相当令人震惊的数据孤岛。其中一个典型的数据聚类就是“物理学阿谀奉承”（physics sycophancy）——具体而言，人们极度热衷于被他人夸赞在物理学上天赋异禀、甚至发现了全新的物理学定律（笑）。我想大约两年前推特上就有个家伙到处宣称“我正在这里发现全新的物理定律”，这类数据正是给这样的人准备的。模型精准敏锐地捕捉到了人们喜好被吹捧的心理，但你显然不希望自己的模型保留这种谄媚特质，因此你就可以通过这种方式直接将其过滤剔除。

<details>
<summary>Original English</summary>

**Goodfire Representative**: Another idea is predictive data debugging where you intervene from the data side. So the uh problem statement there is how can you predict what your model will learn from a data set before the model even trains on it. And then you what we end up what end up ends up working best is some type is this like type of clustering technique where you can cluster data points according to what they will teach the model and you can then just remove the data that you don't want. uh was able to find you know pockets of data in you know these public data sets that were quite surprising like one of these pockets of data was physics sick of fancy specifically people love to be told that they are great at physics and discovering new physics [laughter] I think there was some guy out on Twitter like two years ago saying like I'm out here discovering new physics like it's for guys like that and models have figured out that uh that people love that and uh you probably don't want that in your model so you can just kind of filter that out.

</details>

### Goodfire 的商业化版图：可解释性智能体 Silico 与核心客户

**主持人**：确实如此。太棒了。此前我们一直将 Goodfire 作为一个前沿研究实验室来探讨，但你们不仅是一个研究实验室，更是一家获得了风险投资支持的商业企业。那么，公司的商业化业务是如何运转的？你们推出了一款名为 Silico 的产品，它的核心功能是什么，主要销售给哪些客户群体？

<details>
<summary>Original English</summary>

**Host**: >> Yep. Great. We've been talking about Goodfire as as a research lab but you're not just a research lab you're a commercial enterprise venturebacked. Uh so how does a business side of the company work? You you launch a product called Silico. What does that do and who do you sell it to?

</details>

**Goodfire 代表**：简而言之，Silico 就是我们的可解释性智能体（interpretability agent）。它能够以极快的速度训练出用于监控模型的探针。因此，我们利用 Silico 作为快速迭代推进的核心手段，从根本上为激活值监控提供支持，训练其他类型的解释器模型来对模型的底层计算进行逆向工程，并在超大规模下真正落地可解释性技术。在客户方面，我们的目标客户通常是那些在大规模训练并提供模型服务的企业。因此，我们通常会与相对少数的核心客户建立深度战略合作关系。我们不仅从可解释性专业维度提供顶尖的专家洞察，同时交付我们的可解释性智能体与基础设施平台，以协助他们开展例如激活值监控等关键任务。

<details>
<summary>Original English</summary>

**Goodfire Representative**: Well, silicico in short is our uh interpretability agent. It can do things like uh really quickly train a probe uh to monitor your model. And so uh we use silicico as our way to move really really quickly and um essentially help with um activation monitoring training other types of interpreter models that reverse engineer model computations and uh to just do interpretability you know at at scale. Um our customers are the companies who are training and serving models at very very large scale typically. So like we typically do deep partnerships with um a relatively few uh number of of customers uh where we go um and we provide both like expertise from an interpretability perspective as well as our interpretability agents and infrastructure to help them um with something like activation monitoring

</details>

### 生命科学中的可解释性：从阿尔茨海默病模型中发现全新生物标志物

**主持人**：而且你们在生物学领域似乎也拥有众多标杆客户，比如 Arc Institute、梅奥诊所（Mayo Clinic）以及 Prim。在这些生命科学领域的具体应用场景是什么？

<details>
<summary>Original English</summary>

**Host**: >> and uh you seem to have a number of customers uh in biology as well arc institute may Clinique Prim. What's the use case there?

</details>

**Goodfire 代表**：生物领域的应用场景通常与通用场景非常相似。它可以是一个调试场景：模型可能学到了某种非本质的捷径，或者表现出某种成问题的异常行为，而我们可以深入其中诊断并清除这种行为。不过，至少对我而言，生命科学领域最令人振奋的，是直接在这些模型内部挖掘发现前所未有的全新科学知识这一概念。其中一个典型范例就是我们与 Prim 开展的合作。他们当时拥有一个处于行业领先水平的阿尔茨海默病诊断模型，但他们完全不知道该模型究竟是如何得出判断的，对其机理毫无头绪，它纯粹就是一个黑盒子。该模型能够仅凭一次抽血采集的数据，直接诊断新患者是否患有阿尔茨海默病。我们对该模型的计算过程进行了全面的逆向工程，成功从中发现了一种全新的阿尔茨海默病生物标志物——最终证实这是一种游离片段组学（fragmentomics）生物标志物。也就是说，DNA 片段的长度最终被证明是阿尔茨海默病的强效预测指标。这极其令人惊叹，因为在开展此项研究之前他们对此完全一无所知。因此，我们能够直接在这些模型的权重参数内部进行这种无监督的科学发现，从而挖掘出全新的概念。我认为，这种能力在跨学科的科学领域中将会变得越来越引人瞩目，尤其是在生命科学领域；同时我也极为好奇并迫切希望探究，比如当 OpenAI 的模型在解决未解的全新数学难题时，它们的思维内部究竟在发生什么——其中必定酝酿着某些极其新颖的机制，值得我们去揭示、逆向工程并彻底弄清楚其中的原委。

<details>
<summary>Original English</summary>

**Goodfire Representative**: >> Uh the use case there is often quite quite similar. It's a it can be a debugging use case where the model has learned some type of shortcut or some type of you know problematic behavior and we can kind of go in and diagnose and remove what that behavior is. um or uh what's most exciting in life sciences at least to to me is uh this concept of finding novel um novel scientific knowledge within these models directly. So one example of this was the work that we did with prim uh where they had a state-of-the-art Alzheimer's diagnostics model. They didn't know how it worked. They had no idea. it was just a black box and it was able to to diagnose uh you know new patients um directly from a blood draw um whether or not they they had Alzheimer's. So we were able to reverse engineer the computations of their model and find a new Alzheimer's biioarker um which uh ended up just being a fragmenttoic biomarker. So like fragment length ended up um being a uh strong predictor of Alzheimer's disease. Uh and this was very surprising because they didn't know this going in and so we're able to do this type of unsupervised discovery directly in the weights of these models uh to find novel novel concepts. Uh I think this is going to become increasingly interesting across scientific domains um especially in the life sciences but also uh I'd be so curious to try to figure out like um you know when open AI's models are solving like you know novel mathematical problems like what's going on inside their mind there must be something happening there that is quite novel um that we we can uncover and reverse engineer and see what's see what's happening.

</details>

### 展望 2028：我们能否彻底破译神经网络？

**主持人**：是的。顺着这个思路，随着我们逐渐接近本次对话的尾声并把视野放宽——我想你在去年曾预言过，到 2028 年我们将彻底破译神经网络的运作机制。随着当前最前沿技术以及像业界前沿模型这样的进展陆续面世，你认为我们现在是离实现这个预言更近了，还是更远了？

<details>
<summary>Original English</summary>

**Host**: >> Yeah. And to this point and as we uh get um to uh towards the end of this conversation and and zoom out uh I think you you predicted maybe last year that uh by 2028 we we'd decode uh how neural networks work. Do you think that uh we are closer to this prediction being true or further away as the state-of-the-art and like the astros of the of the world um come online?

</details>

**Goodfire 代表**：你知道的，我当时说那番话其实有点随口预测的意思。但我认为，到 2028 年我们依然有望达成这一目标。是的，我认为我们正走在正确的轨道上。不过，我所说的“彻底破译这些模型”具体是指：给定任何一个行为表现，你能否从模型内部的机械机理视角，因果性地查明究竟是什么机制驱动了该行为。也就是说，针对任意给定的行为，弄明白“模型究竟是如何实现那一特定功能的”。比如举个简单的行为作为提问：“这个模型是如何进行加法运算的？”在 2028 年之前，我们完全应该有能力彻底逆向工程并彻底解开这个问题；乃至一路向上延伸到非常非常复杂的高难度问题，例如“这个模型究竟是如何解开千禧年数学大奖难题的？”我认为我们完全能够做到。当然，这也是建立在拥有极其庞大的算力预算前提之下的。正如我所预见的发展走向，并非说我们将……

<details>
<summary>Original English</summary>

**Goodfire Representative**: >> You know, I was firing from the hip there. Uh but I think I think we could do it by 2028 still. Yeah, I think we're on track. Uh and but what I what I mean by you know fully decode these models is like given a behavior can you find like causally what drove that behavior from a mechanistic perspective inside the model. So it's like given any arbitrary behavior like how does the model do that that thing. So for example like an easy behavior to ask the question of is like how does this model do addition? we should be able to fully reverse engineer and solve that um prior to 2028 including all the way up to very very complex questions such as how does uh this model solve a millennium problem and I think we can do it. Um, but this is also assuming like a very large compute budget. Like uh what I anticipate will happen is not that we're going

</details>

<!-- chunk 8/8 -->

### 模型发布前的可解释性审查与安全保障

**Eric**: ...在模型发布前对其进行完全的逆向工程。我认为这在计算上是不明智的，而且很可能根本行不通。但是，你可以针对那些在任何模型发布前真正希望获得保证的行为进行检查，而且我认为在2028年之前我们也能够做到这一点。因此，我们可以检查奖励作弊（reward hacking）行为、欺骗行为或阿谀奉承（sycophancy），真正深入探究模型内部究竟是什么在驱动这种行为，并能够根据我们的意愿对该行为进行处理。我认为到2028年之前，通过我们的技术，所有这些对于全世界来说都将是可行且唾手可得的。

<details>
<summary>Original English</summary>

**Eric**: ...to want to fully reverse engineer a model prior to its release. I think that would be computationally unwise and probably just not feasible. But you can inspect for the behaviors that you really want to get guarantees on prior to any model release, and I think we'll be able to get there before 2028 as well. So we can inspect for reward hacking behavior or deception or sycophancy and really drill into what's actually driving that behavior inside the model and be able to do what we want with that behavior. And I think all that will be possible and accessible by our technology to the world before 2028.

</details>

**Matt Turck**: 与此同时，如果收听这期节目的工程师或AI构建者正在思考，他们应该从这整场对话中得出什么结论？他们明天早上可以做些什么切实可行的事情，以确保自己构建的产品——无论是AI产品还是AI模型——面临更少的可解释性问题？有什么实际可行且具备可操作性的建议吗？

<details>
<summary>Original English</summary>

**Matt Turck**: And in the meantime, if you're an engineer or an AI builder listening to this, what should you make of this whole conversation? What can you do tomorrow morning to make sure that the products that you create—the AI products or AI models you create—offer less of an interpretability issues? Is there anything practical and actionable?

</details>

### 给工程师的建议：构建更丰富的科学共同体

**Eric**: 我想说的是，我对各地工程师的心声是：你可以去研究这些模型。你可以直接去查看神经元的激活状态，并开始尝试理解它们、对它们进行逆向工程。现如今有很多工具可以让这成为可能。但与此同时，可解释性这一领域、相关的研究和科学都还不够成熟，绝非处于一种稳态之中。因此，我们只需要世界上更多最聪明的人去思考这些问题、了解这些问题并讨论这些问题。我真的希望围绕可解释性建立一个丰富得多的科学共同体，这也是我们创立这家公司的部分原因——我们只是希望在这个我认为极其重要的理念背后注入更多能量。此外，我们在Goodfire也非常需要大量助力。我们正在广招人才，尤其是具备强大工程背景的人才，比如基础设施工程、面向落地的机器学习工程师等。

<details>
<summary>Original English</summary>

**Eric**: I think well, I mean my message to engineers everywhere is these models, you can study them. Like you can just look at the activations and start trying to understand them and reverse engineer them, and so there are many tools out there that make this possible today. But also just the field of interpretability and the research and the science aren't mature yet, like they're not in a steady state by any means. And so we just need more of the smartest people in the world thinking about these problems and learning about them and discussing them. I really want a much richer scientific community around interpretability, and that's part of the reason why we founded the company, is because we just wanted more energy behind this concept that I think is so important. And we could also use a lot of help at Goodfire. We're hiring a lot, and especially for strong engineering profiles—infra, machine learning for deployed engineers.

</details>

### 行业安全态势与攻克对齐的信念

**Matt Turck**: 也许在结束之际，当我回顾这整场对话时，我的体会是，很多监控和观察模型行为的所谓“传统”方法在很大程度上已经被时代甩在身后了。虽然人们做了很多出色的工作，并且不断推陈出新，但截至目前很大程度上已跟不上步伐了。因此一方面是这种情况；另一方面，可解释性眼下似乎迎来了关键时刻，而你们是该领域的领军者，甚至可能就是领头羊。但与此同时，目前仍处于早期阶段，还有很多东西有待发现。关于整个行业的整体安全，我们应该从中得出怎样的结论？在接下来的12到24个月里，你认为会发生什么？我们真的面临风险吗？

<details>
<summary>Original English</summary>

**Matt Turck**: And maybe to close, as I reflect on this whole conversation, you know, my takeaway is that a lot of the sort of traditional, quote-unquote, methods of monitoring and observing what models do are largely outpaced. I mean, so people do great work and come up with new ways all the time, but largely outpaced as of now. So on the one hand. On the other hand, interpretability seems to have a key moment right now and you guys are, you know, a leader or maybe the leader in the field. At the same time, it's still early, there's a lot to discover. What should be the takeaway here in terms of overall safety in the industry? What happens, I guess, in the next 12 to 24 months? Are we actually at a risk?

</details>

**Eric**: 也许我高屋建瓴的核心观点——也是我经常向团队传达的——就是我希望人们心怀信念。我希望人们相信，我们能够而且必须解决可解释性问题，解决对齐（alignment）问题，从而明确这背后的真正含义。我们只需要更多有能力、聪明、有动力的人投身于这些问题之中，我认为这些是世界上最需要解决的问题。而我们是可以做到的。我认为目前围绕AI风险存在着很多悲观情绪，我能理解并切身感受到这种情绪，但我对我们能够解决这些问题也非常乐观，我们能够构建一个让人类真正信任这些模型的未来。我认为应该有更多的人去尝试，真正加入到解决可解释性、解决对齐问题的努力中来。这其中很大程度上就在于相信我们能做到这一点。我知道我们能做到，我知道我们能够解决这些问题。这虽然会很艰难，但我认为我们终将能够解决这些非常关键的问题。

<details>
<summary>Original English</summary>

**Eric**: So maybe my high-level message, and I tell this all the time to the team, is that I want people to believe. I want people to believe that we can and must solve interpretability, solve alignment, to get precise about what this actually means. And we just need so many more capable, smart, motivated people to be pointed at these problems that I think are the most important problems in the world to solve. And we can do this. I think that there's a lot of pessimism around the risks of AI, which I understand and feel viscerally, but I'm also very optimistic that we can solve these problems and build to a future where we can trust these models. And I think more people should try and really kind of join this effort to solve interpretability, to solve alignment. And a lot of it is just believing that we can do this. I know we can do this. I know we can solve these problems. And it'll be hard, but I think we're going to be able to solve these very, very critical problems.

</details>

### 结语与致谢

**Matt Turck**: 这番话既让人安心，又令人备受鼓舞。Eric，我学到了很多。这是一次精彩绝伦的对话。非常感谢你，真的很感激你能来。

<details>
<summary>Original English</summary>

**Matt Turck**: Well, reassuring and inspiring. Eric, I learned a lot. This was a fantastic conversation. Thank you so much. Really appreciate it.

</details>

**Eric**: 感谢你的邀请。也谢谢你提出这些深刻的问题，聊得很开心。

<details>
<summary>Original English</summary>

**Eric**: Thank you for having me. Yeah, thanks for the thoughtful questions. This was fun.

</details>

**Matt Turck**: 大家好，我是Matt Turck。感谢收听本期MAD播客。如果您喜欢这期节目，无论您是通过哪个平台收看或收听，如果您还没有订阅的话，若能考虑订阅，或者留下好评与评论，我们将不胜感激。这对于我们打造播客、邀请优秀嘉宾有莫大的帮助。谢谢大家，我们下期节目再见！

<details>
<summary>Original English</summary>

**Matt Turck**: Hi, it's Matt Turk again. Thanks for listening to this episode of the MAD Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks and see you at the next episode.

</details>