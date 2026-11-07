---
author: Dwarkesh Patel
date: '2026-06-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=20p5-kQXF_Q
speaker: Dwarkesh Patel
tags:
  - reinforcement-learning
  - sample-efficiency
  - continual-learning
  - in-context-learning
  - on-policy-self-distillation
title: AI 的下一个训练范式：从 RLVR 到持续学习与梦境模拟
summary: 本文深入探讨了当前 AI 训练范式的核心赌注——通过 RLVR 在可验证任务上训练通用智能体，并批判性地分析了其样本效率低下和缺乏持续学习能力的根本缺陷。文章提出了两种突破路径：在线策略自蒸馏（OPSD）和梦境模拟，并展望了到 2027-2028 年，AI 通过大规模部署实现持续学习、不断自我进化的未来图景。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - DeepMind
products_models:
  - EfficientZero
media_books: []
status: evergreen
---
### 核心赌注：RLVR 能否通向 AGI？

当前所有 AI 实验室都在押注一个巨大的研究方向：他们认为，如果我们训练 AI 在数千个不同的强化学习（RL）环境中完成数百万个可验证的任务，那么我们就基本上构建了通用人工智能（AGI）。因为这种训练将创造一种能够解决问题的智能体——一种可以在数周内，面对错误、失误和模糊性，持续在开放式任务上取得进展的实体。

对这一愿景持乐观态度的人会辩称，我们当前训练范式的所有根本性缺陷——例如模型的数据效率低下，或者它们缺乏持续学习能力——都可以通过进一步扩大训练规模来碾压。就像自然语言处理中的所有基础研究问题，在向大语言模型（LLM）投入足够多的算力后都迎刃而解一样。

在之前的文章中，我提到这些模型的样本效率只有人类的百万分之一。而支持当前训练范式的人会说：“没错，这可能成立，但这只是在训练阶段。训练是一次性成本，可以分摊到模型将经历的数十亿次会话中。真正重要的是模型在单次会话中的智能程度、通用性和样本效率，而这随着我们进行更多的 RL 训练，显然在不断提升。AI 智能体能够解决越来越复杂的问题，时间跨度也越来越长。任何用这些模型写过代码的人都知道这一点。”

同样，他们也会说，我一直在强调的持续学习能力——即模型根据部署中学习到的内容更新其权重——可能根本就不是必需的。因为如果上下文学习（in-context learning）在越来越长的时间跨度内变得足够好，那么你就不需要将模型在工作中学习到的一切都蒸馏回权重里。人们常说，新员工通常需要六个月或更长时间才能产生净生产力。显然，在线学习对于胜任工作是必要的。但是，如果你能把那六个月的经历都塞进上下文窗口呢？已经有大量的架构创新极大地增加了 Transformer 可以存储的信息量或上下文量。为什么不能认为，再经过几年的进步，我们就能拥有近乎无限大的上下文窗口呢？

<details>
<summary>Original English</summary>

So here's a big research bet
that all the labs are making.
They think that if we train AIs to
accomplish millions of verifiable
tasks across thousands of diverse
RL environments, then we will have
basically built AGI, because this kind
of training will have created a kind of
problem-solving agent: the kind of thing
that can make progress on open-ended
tasks for weeks on end in the face
of errors and mistakes and ambiguity.
And the people who are optimistic
about this vision will say that all
these things we talk about as the
fundamental deficits in the current
training paradigm — for example, the
data inefficiency of these models,
or the fact that they lack continual
learning — can just be steamrolled if we
scale training more, in the same way that
all the fundamental research problems
in natural language processing collapsed
when we threw enough compute into LLMs.
So in the previous essay, I talked
about how these models are one
one-millionth as sample-efficient as
humans, and the people who are in favor
of the current training paradigm will
say, "Look, that might be true, but
this is only true during training."
Training is this one-time cost that
is amortized across billions of
sessions that a model will experience.
What really matters is how smart
and general and sample-efficient
the model is during a session, and
this has clearly been improving as
we've been doing more RL training.
AI agents are able to solve more
and more ambitious problems over
longer and longer time spans.
Anybody who has used these
models for coding knows that.
Similarly, people would say, look,
continual learning — this capability
I keep harping about, where the
model's weights get updated based on
what it's learning from deployment
— may simply not be necessary.
Because if in-context learning gets
so good across longer and longer
time horizons, then you don't need to
distill everything the model is learning
on the job back into the weights.
People often say that their
employees are not net productive
until six months or more on the job.
So clearly, online learning
is necessary for competence.
But what if you could just fit those
six months into the context window?
There have been tons of architectural
innovations that dramatically increase
the amount of information, or the amount
of context, that a transformer can store.
And why not think that, with a
couple more years of progress,
we might have what feels like
infinitely large context windows?

</details>

### 可验证 ≠ 可磨炼：计算机使用的困境

在进一步讨论这个研究赌注之前，我想先退一步，问一个看似不相关但非常有趣且令人困惑的问题：为什么计算机使用（computer use）领域的进步比其他领域慢得多？计算机使用显然是可验证的。你可以问这样的问题：我订购的 Etsy 商品送到了吗？我试图组织的活动场地预订了吗？我的税报了吗？那么，计算机使用的进展比编码、数学和其他可验证领域慢得多，这难道不奇怪吗？

原因有很多，其中之一当然是模型在预训练期间接触的高质量多模态数据要少得多。但我认为有一个被严重低估的原因，它揭示了 AI 进步这条河流将缓慢冲刷的峡谷壁垒：一个领域仅仅可验证是不够的。它还必须非常“可磨炼”（grindable），也就是说，你必须能够针对一个确定且可重放的模拟器运行大量并行回滚（parallel rollouts），并且这些回滚必须从相同的起点开始。

如果你想让模型在编码方面变得更好，你可以定义一个容器，里面有一个缺少某些功能的软件仓库，你让 AI 去创建这些功能。然后你可以让一千个并行的智能体去解决这个问题，每个智能体都拥有该容器的相同副本。但这在计算机使用上行不通，至少不是那么容易。你不能让一千个智能体去尝试亚马逊上的同一个结账流程来提高使用网站的能力，因为安迪·贾西（Andy Jassy）会发现你的机器人并封杀你。你可以通过克隆 Slack、Gmail 以及其他所有常见的应用程序和网站来解决这个问题。但至少目前，这是一种非常劳动密集且不可扩展的环境构建方式。当然，一旦 AI 自身的编码能力足够强，能够以极高的保真度构建这些克隆，那么我相信计算机使用的进步会比现在快得多。而且，这个过程还能一石二鸟，因为让 AI 从头重建整个应用程序本身也是一个很好的编码 RL 目标。

因此，尽管计算机使用本身可能很快就会被解决，但它目前的缓慢进展告诉我们：除非你能为一个领域构建一个非常可重放的训练目标，否则模型将难以取得太大进展。原因当然是模型在训练期间的样本效率极低。这就是我在上一个视频文章中提出的观点。所以对于计算机使用，我们或许可以通过构建这些可耕种的确定性模拟器来弥补样本效率的不足。但对于我们需要的许多其他类型的 AI 技能，我们根本无法做到这一点。

<details>
<summary>Original English</summary>

Okay, so before we discuss this research
bet a bit further, I want to step
back and ask a completely tangential
question, which I find actually
very interesting and confusing about
the nature of current AI progress.
Why has progress on computer use been
so much slower than other domains?
Computer use is so clearly verifiable.
You could ask a question like: did the
desired Etsy item I ordered get delivered?
Is the venue for an event I'm
trying to organize booked?
Have my taxes been submitted?
So isn't it weird that computer
use has been making so much slower
progress than coding and math and
these other verifiable domains?
I'm sure there are many reasons for
this, and one of them, of course,
is the fact that the models are
exposed to far less high-quality
multimodal data during pretraining.
But one reason that I think is actually
quite underrated by people, and which I
think reveals the canyon walls against
which this river of AI progress will
only slowly chip away, is that it is not
enough for a domain to be verifiable.
It also has to be very grindable, in
the sense that you have to be able
to run lots of parallel rollouts
against a deterministic and replayable
simulator, and you have to run those
rollouts from the same starting point.
If you're trying to make a model
better at coding, you can define some
container that has a software repo
with some missing feature that you
have tasked the AIs with creating.
And then you have a thousand parallel
agents go at the problem, each of which
has an identical copy of the container.
But this doesn't work with computer
use, at least not trivially.
You can't just have a thousand
agents go try the same checkout flow
on Amazon to get better at using
websites, because Andy Jassy will
find your bots and shut your ass down.
You can solve this by making clones
of Slack and Gmail and all the other
common applications and websites.
But at least currently, this is a
very labor-intensive and unscalable
way to build environments.
Of course, once AIs get good enough
at coding themselves to build these
clones with extremely high fidelity,
then I'm sure computer use will make
quicker progress than it is right now.
And you're also killing two birds with
one stone with this kind of procedure,
because getting AIs to rebuild whole
applications from scratch is also
a great RL objective for coding.
So while computer use itself may
soon be solved, its current lethargy
is telling us the following: that
unless you can build a very replayable
training target for a domain, the models
will struggle to make much progress.
And the reason this is true, of course,
is that the models are incredibly
sample-inefficient during training.
This is the point I was
making in my last video essay.
So for computer use, we might be able
to make up for the sample-efficiency
deficit by building these
farmable deterministic simulators.
But for so many other different
kinds of skills that we need AIs
to have, we simply can't do this.

</details>

### 样本效率：通往通用智能的瓶颈

我们如何训练 AI 真正擅长从零开始建立一家企业？如何让它擅长打赢官司、在市场上实现盈利的一天交易，或帮助候选人赢得选举？这些任务的执行需要与现实世界互动，你无法仅在一个数据中心内重现它。这里的外循环验证可能需要数月甚至数年的真实世界行动才能触发，你无法通过轻微扰动模型在数千次并行回滚中的行动，来精确隔离出模型到底做了什么有效的事情。

处理这种无重置、非平稳的环境是 RL 中一个已知的开放问题。我并不是在提出什么新东西。但我确实想强调，由于世界上大多数领域的数据都具有特殊性和稀疏性，你需要样本效率才能变得熟练。如果 AI 要发展人类拥有的所有技能，甚至人类没有的技能，那么它们就需要能够从非结构化、不可验证、模糊的信息中，通过稀缺的真实世界互动来学习。因为在许多领域，相关的训练信息根本不存在于其他任何形式中。什么是让 AI 像林登·约翰逊（Lyndon Johnson）一样擅长政治，或像埃隆·马斯克（Elon Musk）一样擅长建立太空发射业务的 RL 环境？

实验室们押注的是 RLVR（基于可验证奖励的强化学习）能够泛化。也就是说，如果你在足够多的容器化、可复现的环境上进行训练，你将开发出一个非常通用的智能体，它可以在单次会话中制定和执行计划、从新信息中快速学习，甚至掌握新技能。如果你把这个经过无尽 RLVR 训练的 AI 扔进 1948 年的德克萨斯州政坛，它可能会在赢得参议院席位方面给出比 LBJ 更好的建议。如果你在 2002 年给它一亿美元并让它放手去做，它可能会为你打造出 SpaceX。

现在，RLVR 能否如此完美地泛化是一个实证问题。如果实验室从在 RL 环境上花费数十亿美元增加到一万亿美元，你能否得到那种在上下文窗口内完全像人类一样的通用智能？Dario（Anthropic CEO）在我们一起做播客时给出了一个很有启发性的引述，我认为这暗示了 RLVR 的泛化能力并非无限强大。当他在解释为什么模型在长上下文下性能会下降时，他说：“有两件事。有训练时的上下文长度，还有服务时的上下文长度。如果你在短上下文长度下训练，然后试图在长上下文长度下服务，你可能会遇到这些退化。” 也许我过度解读了，但他似乎是在说，短视界的 RL 训练不一定能泛化到长视界的 RL 性能。如果你不能从短视界泛化到长视界，那么智能体又如何能从在一堆白领任务上训练，泛化到被扔进现实世界并像山姆·沃尔顿（Sam Walton）一样从零开始建立企业呢？

即使经过足够的上下文内体验，AI 可以变得像亨利·福特（Henry Ford）或阿尔伯特·爱因斯坦（Albert Einstein）一样，但如果不能将这些学到的知识回传至权重，那么这一切都将是短暂且被浪费的。大约 30% 到 50% 的实验室算力用于推理，而这些算力目前并没有在帮助改进模型方面发挥任何生产性作用。这似乎是一个巨大的浪费。而且情况比听起来更糟，因为只有在部署过程中，模型可以学习到的最有价值的信息才会真正显现出来：在我被使用的组织中到底发生了什么？他们用我来做什么？我在现实世界中倾向于犯哪种错误？

我们有一个天才的研究生，却从不允许它去参加真正的实习，我们只是不断地以 RL 环境训练的形式给它提供越来越多的课堂案例研究。这太奇怪了，我们已经有了广泛部署在经济中的 AI，它们参与了如此多不同类型的任务，接触了如此多领域和组织特有的隐性知识，但它们却无法利用这些知识。但这种持续学习需要回到权重上。AI 不能随着从更多用户那里学习而不断构建越来越大的 KV 缓存。这不可扩展，也不是人类的方式。我们的大脑中，参数和激活之间没有清晰的界限，也不会像你的头骨随着你一生中学习更多东西而不断扩张。当我们学习东西时，显然存在某种压缩，这有助于我们的泛化和顿悟（grokking）。事实上，有些人类拥有类似自闭症学者的能力，可以在多年后回忆起随机的数字表或无意义的音节——基本上就是模型在上下文中拥有的那种信息保真度。而这种巨大的信息量会削弱这些人类理解抽象和隐喻的能力。人类的持续学习，与其说是将所有观察结果都放在嘴边，不如说是将正确的直觉和大局观知识凿刻回权重中。

<details>
<summary>Original English</summary>

How do we train an AI to get really good
at building a business from scratch?
How about winning court cases, or having a
profitable day of trading in the markets,
or helping a candidate win an election?
The rollout here requires interacting
with the real world, and you can't
recreate it from just within a datacenter.
The outer-loop verification here
may take months or even years of
real-world actions to elicit, and you
can't re-observe it by perturbing the
model's actions slightly in thousands
of parallel rollouts to isolate exactly
what the model did that actually worked.
Now, dealing with such reset-free,
non-stationary environments
is a known open problem in RL.
I'm not pointing out anything new.
But I really do want to emphasize
that because of the idiosyncratic
and sparse nature of data in most
domains in the world, you need sample
efficiency in order to get proficient.
If AIs are to develop all the skills
that humans have, and even skills
that humans don't have, then they need
to be able to learn from information
revealed in unstructured, unverifiable,
and ambiguous ways from scarce
amounts of real-world interaction.
Because in many domains, the
relevant training information simply
doesn't exist in any other way.
What is the RL environment to make an
AI that is as good at politics as
Lyndon Johnson, or as good at building
a space-launch business as Elon Musk?
The labs are betting that
RLVR will generalize.
That is, that if you train on
enough containerized, reproducible
environments, you will develop a
very general agent that can make and
execute plans and learn rapidly from
new information, and even pick up new
skills, all within a single session.
If you drop this endlessly RLVR'd
AI into Texas politics in 1948, it
could give you better advice than
LBJ about winning the Senate seat.
And if you gave it a hundred million
dollars in 2002 and let it cook,
it would build SpaceX for you.
Now, whether RLVR can generalize
this well is an empirical question.
If the labs went from spending billions of
dollars on RL environments to a trillion
dollars, would you get the kind of
thing that is a fully human-like general
intelligence within the context window?
Dario gave a telling quote during
our podcast together, which I think
hints that RLVR generalization
is not infinitely strong.
When he was explaining why model
performance tends to degrade at long
context, he said: "There's two things.
There's the context length you
train at, and there's a context
length that you serve at.
If you train at a small context length
and then try to serve at a long context
length, maybe you get these degradations."
Now, maybe I'm reading too much
into this, but it seems like he's
saying that short-horizon RL training
doesn't necessarily generalize
to long-horizon RL performance.
And if you can't generalize from short
horizon to long horizon, then how are
agents supposed to generalize from getting
trained at a bunch of white-collar tasks
to, say, having the ability to be dropped
in the real world and build a business
from scratch as well as Sam Walton?
And even if, after enough in-context
experience, the AIs could become
like Henry Ford or Albert Einstein,
all that would be ephemeral and
wasted if you couldn't get those
learnings back into the weights.
Around 30 to 50 percent of a lab's compute
goes to inference, and that compute is
currently not playing any productive
role in helping improve the model.
This seems like a huge waste.
And it's even worse than it sounds,
because it is only in deployment
that the most valuable bits of
information which your model could
learn from are actually revealed.
What's actually happening in the
organizations where I'm being used?
What are they using me for?
And what kinds of mistakes do I
tend to make in the real world?
We've got some genius grad student
who's never been allowed to take a real
internship, and we keep giving it more
and more classroom case studies in the
form of RL training on environments.
It's so bizarre that we have AIs
that are broadly deployed through the
economy already, and are participating
in so many different kinds of tasks,
and are privy to so much domain- and
organization-specific tacit knowledge,
and they're not able to make use of it.
But this kind of continual learning
requires going back to the weights.
AIs can't just keep building up a
bigger and bigger KV cache as they
learn from more and more users.
That's just not scalable, and
that's also not how humans do it.
There's no clean separation in our brain
between parameters and activations,
and it's not like some part of your
skull keeps expanding as you learn
more things throughout your lifetime.
When we learn stuff, there's clearly
some kind of compression, and this
aids our generalization and grokking.
There are, in fact, some humans who
have this autistic-savant-type ability
to recall random tables of numbers
or nonsense syllables years later
— basically the kind of fidelity of
information that models have in context.
And such sheer volume cripples
these humans' ability to understand
abstractions and metaphors.
Human continual learning is less about
having all your observations at the tip
of your tongue and more about chiseling
the right intuitions and big-picture
knowledge back into the weights.

</details>

### 在线学习的局限与持续学习的真正挑战

但一旦你转向权重，你就必须放弃上下文学习的样本效率。因为梯度更新的样本效率极低，所有成功上线的在线学习模型都必须在数百万用户身上学习完全相同的东西。例如，Cursor Tab 模型通过每天预测超过 4 亿次请求的完全相同目标来进行在线学习。这里的目标是哪些编辑最终被用户接受了。至少到目前为止，我们还没有看到模型为不同用户在线学习不同类型的东西，因为虽然单次会话产生的数据足以让人类学习，但不足以训练一个更强大的 AI。当前的在线学习只能用于非常有限的用例。

但持续学习的全部意义在于，世界非常复杂，每份工作、每个公司、每个问题都不同，你需要你的智能能够学习与特定部署相关的具体信息，而这些信息根本无法塞进某个共享的训练运行中。这就是我们在谈论在职学习时所讨论的一切：你的组织中的一切是如何运作和配合的，如何与你周围的基础设施和其他人合作以在更大的项目上取得进展，常见的失败模式是什么，以及许多其他类似的事情。

随着播客的发展，我不得不处理越来越多的运营开销。以支付账单为例。过去，承包商只是通过电子邮件给我发发票。每隔几周，我就会翻遍收件箱，创建一个包含所有账单的文件夹，然后手动支付每一笔。但现在，我只需给每个人一个直接发送到我的银行平台 Mercury 的电子邮件地址。每当有人向该地址发送发票时，Mercury 会自动下载、扫描并提取所有相关信息——比如承包商姓名、地址、付款金额、发票编号和到期日——然后利用所有这些信息创建付款草稿。Mercury 会存储这些草稿列表供我审核。我只需浏览列表并仔细检查它们是否正确构建。我不需要自己跟踪任何东西或输入任何信息。Mercury 为你的企业出色地完成了所有基础工作，并将它们集中在一个地方。

这样看来，样本效率和持续学习实际上是深度关联的问题。模型在工作中可用的数据相对较少。要从这些数据中学习需要样本效率，模型可以在上下文中做到这一点，但使用由注意力机制即时构建的快速权重（fast weights），虽然实现了样本效率，但在内存方面扩展性很差。因此，我们需要允许某种中间表示的架构创新。我之前谈到过，我们已经有很多不同的工作思路，从稀疏注意力到 KV 缓存压缩。每周都有人发布新论文，提出某种其他的架构优化。在我看来，架构并不是从根本上限制持续学习的瓶颈。

那么，瓶颈可能在于损失函数。我们如何根据从某个特定会话中学到的信息来更新权重，也就是如何改进模型本身？即使在这里，天真地看，似乎也有很多应该可行的想法。最近很多人都在讨论一种叫做**在线策略自蒸馏**（On-Policy Self-Distillation, OPSD）的技术。如果你想了解更多，几周前我和 Sasha Rush 在我的 iPhone 上录制了一个即兴的黑板讲座，链接在描述中。简而言之，这个想法是鼓励基础模型在尝试解决某个现实世界问题时，做出与积累了长会话上下文后的模型相同的预测。这个过程的全部意义在于将会话中学到的知识蒸馏回权重本身。

这比 RLVR 更好，原因有二。第一，OPSD 不需要我们拥有某种外循环可验证的奖励。我们只需要一个能够在上下文窗口内学习正确事物的模型。只要我们有这个，我们就可以训练基础模型去匹配我们的“资深教师”模型，后者在会话中积累了所有这些经验。第二，OPSD 提供了比朴素 RL 更密集的监督信号。它不是将单个奖励投射到整个轨迹上，而是可以训练教师和学生之间每个 token 的概率差异。

对于持续学习，OPSD 也优于监督微调（SFT）。你能想象到的最朴素的 SFT 版本就是训练基础模型去预测会话中观察到的所有 token。但如果你把它当作一个学习目标来思考，这是没有意义的。你提高工作水平的方式，不是完美地回忆每天发生的每一件事的记录。而是整合那些与你提高工作水平真正相关的少数见解和知识。RL 训练不会遭受这种失败模式。RL 擅长将更新集中在与获得正确结果相关的内容上。这就是为什么 RL 的更新非常稀疏。这对于持续学习来说是一个非常重要的特性，因为当你在职学习时，你不想覆盖和忘记基础模型知道的所有其他东西。

我几个月前写过一篇文章，认为 RL 每个样本学习的信息比监督学习少得多。但这可能是一件好事而不是坏事。你只改变模型达到结果所绝对必要的程度，仅此而已。OPSD 保留了 RL 的这一特性，它不是像监督学习那样让你弹射式地接近教师分布，而是只提取在真实世界任务上达到与教师相同结果所必需的知识。

<details>
<summary>Original English</summary>

But the moment you move into the
weights, you have to give up on
in-context learning's sample efficiency.
Because gradient updates are super
sample-inefficient, all of the
successfully shipped online-learning
models have had to learn the exact
same thing across millions of users.
For example, the Cursor Tab model
online-learns by predicting the
same exact objective for over
400 million requests a day.
The objective here is which edits
actually got accepted by the user.
At least so far, we haven't seen models
online-learn different kinds of things for
different users, because while a single
session may generate more than enough
data for a human to learn from, it's
not enough to train a more capable AI.
Current online learning can work for
a very limited number of use cases.
But the whole point of continual
learning is that the world is very
complicated, and each job and company
and problem is different, and you need
your intelligence to be able to learn
the specific information related to a
particular deployment, which simply can't
be stuffed into some shared training run.
These are all the things we're talking
about when we talk about on-the-job
learning: things like how everything
in your organization works and fits
together, how to cooperate with all
the infrastructure and the other people
around you to make progress on some larger
project, what the common failure modes
are, and many other things like this.
As the podcast has grown, I've had to deal
with more and more operational overhead.
Take paying bills.
In the past, contractors would
just email me their invoices.
Every few weeks, I'd dig through my
inbox, create a folder with all the
bills, and manually pay each one.
At this point, though, I just
give everybody an email address
that goes straight to Mercury,
which is my banking platform.
Whenever anybody sends an invoice to
that address, Mercury automatically
downloads it, scans it, and extracts
all the relevant information — things
like the contractor name, address,
payment amount, invoice number,
and due date — and then uses all
of this to create a draft payment.
Mercury then stores a list of
these drafts for me to review.
I just go through the
list and double-check that
they've been built correctly.
I don't have to track anything
or enter any information myself.
Mercury does all the fundamental things
for your business extremely well,
and it puts them all in one place.
If you want to learn
more, go to mercury.com.
Mercury is a fintech company,
not an FDIC-insured bank.
Banking services provided
through Choice Financial Group
and Column N.A., Members FDIC.
In this way, sample efficiency and
continual learning are actually
deeply connected problems.
Relatively little data is
available to the model on the job.
Now, to learn from this data requires
sample efficiency, and models can do that
in context, but using the fast weights
that are built on the fly by attention,
which allow for this sample efficiency,
scales very poorly in terms of memory.
So we need architectural innovations
that allow for some kind of
intermediate representation.
I talked before about how we already
have many different working ideas
for this kind of thing, from sparse
attention to KV cache compaction.
And every week, somebody releases
a new paper suggesting some kind of
other architectural optimization.
It doesn't seem to me that
architecture is fundamentally what
is bottlenecking continual learning.
So perhaps the bottleneck
is the loss function.
How do we update the weights, AKA
how do we improve the model itself,
based on information that was
learned from one particular session?
Even here, naively, it seems like there
are many ideas that ought to work.
A lot of people are talking about
this technique called on-policy
self-distillation recently.
If you want to learn more about
it, I recorded a little impromptu
blackboard lecture on my iPhone with
Sasha Rush a couple weeks ago, and
it's in the link in the description.
But to summarize the explanation, the
idea is that we encourage the base model
to make the same predictions when trying
to solve some real-world problem as the
model with all the context accumulated
after a long session would have made.
The whole point of this procedure is
to distill what the model learned in a
session back into the weights themselves.
This is better than RLVR for two reasons.
One, OPSD doesn't require us to have
some outer-loop verifiable reward.
We just need a model that can learn the
right things within the context window.
And as long as we have that, we can
train the base model to match our veteran
teacher model, which has built up all
this experience during the session.
And two, OPSD provides a much denser
supervision signal than naive RL.
Instead of projecting a single
reward through the whole
trajectory, you can train on the
per-token probability discrepancy
between the teacher and student.
For continual learning, OPSD is also
superior to supervised fine-tuning.
The most naive version of SFT
for this application that you can
imagine is just to train the base
model to predict all the tokens that
are observed during the session.
But this makes no sense if you
think about it as a learning target.
The way you get better at your job
is not by recalling the transcript
of every single thing that happened
every day with perfect fidelity.
Rather, it's by consolidating the
handful of insights and pieces of
knowledge that are actually relevant
to you getting better at your job.
RL training doesn't suffer
from this failure mode.
RL is great at concentrating the
update to only what is relevant
to getting the outcome right.
That's why
the updates from RL are incredibly sparse.
And this is a very important property
for continual learning, because as
you're learning on the job, you don't
want to overwrite and forget all the
other things that the base model knows.
I wrote a post a few months
earlier arguing that RL learns
much less information per
sample than supervised learning.
But this may be a good thing
rather than a bad thing.
You only change the model as much
as is absolutely necessary to
achieve the outcome, and no more.
OPSD preserves this property of RL,
where instead of slingshotting towards
the teacher distribution as supervised
learning would have you do, you only
extract the knowledge that is necessary
to achieve the same results as the
teacher on actual real-world tasks.

</details>

### 梦境模拟：第四维度的扩展

OPSD 是解决样本效率问题的一种方法。你获取这些稀缺的现实世界经验，并将所有信号压缩成一个微小、精准的更新。但还有另一个更具推测性的想法。我们称之为“梦境模拟”（dreaming）。如果 AI 能够构建一个良好的现实模拟器，用来演练新技能、尝试替代策略并强化有效的方法，那么 AI 就可以在相同的挂钟时间内体验数量级更多的模拟样本。

让我们回顾一下历史。DeepMind 发布 AlphaZero 几年后，一组研究人员训练了一个名为 EfficientZero 的模型，其全部目标就是实现极高的数据效率。因此，如果这个模型和一个人都有两个小时的时间来对抗一个他们从未见过的 Atari 游戏模拟器，这个模型很可能会击败新手人类。这是否意味着该模型比人类更高效？嗯，那是训练的目标，但这取决于你如何衡量样本效率。因为在真实游戏的每一步中，EfficientZero 都在其脑海中模拟了数十场游戏。类似地，未来的 LLM 或许能够消耗更少的现实世界数据，同时在自己构建的环境中无休止地练习。当然，最大的区别在于，构建整个世界的模拟器比模拟围棋游戏要困难得多。这就是为什么我说这是一个更具推测性的想法。

如果它成功了，它将成为一个与预训练、RL 和推理时计算并列的第四扩展轴。你可以称之为测试时训练（test-time training）或梦境模拟。模型花费算力来编写 RL 环境，然后针对它们进行训练，并演练将在生产中为特定用户实际使用的所有技能。因此，不是在 Codex、Cursor 或 Claude 中按下 `/compact`（这会消耗少量算力来生成摘要，给你一种持续学习的假象），而是按下 `/dream`。这会消耗大量算力来构建并训练一个视频游戏版本的模型在现实世界中观察到的东西。

<details>
<summary>Original English</summary>

OPSD is one way to attack the
sample-efficiency problem.
You take this scarce real-world
experience, and you squeeze all the
signal into a tiny, well-targeted update.
But there's also another
much more speculative idea.
Let's call it dreaming.
If the AI can build a good simulation
of reality against which to rehearse
new skills, or try alternative
strategies and reinforce what actually
works, then AIs could experience
orders of magnitude more simulated
samples in the same wall-clock time.
Let's go back into history a bit.
A couple years after DeepMind released
AlphaZero, a group of researchers
trained a model called EfficientZero,
and the whole point of this model
is to be very efficient with data.
So if this model and a human both got
two hours to play against a simulator
of an Atari game that they hadn't
seen before, this model would actually
probably beat the novice human.
Does this mean that the model was
more sample-efficient than the humans?
Well, that was the goal of the
training, but it depends on how
you measure sample efficiency.
Because for each step in the real
game, EfficientZero is playing dozens
of simulated games in its head.
In a similar way, future LLMs
might be able to consume far less
real-world data while practicing
endlessly against environments
that they build for themselves.
The big difference, of course, is
that it will be much harder to build
a simulation of the whole world than
it is to emulate the game of Go.
That's why I said this is a
much more speculative idea.
If it works, it would become a fourth
axis of scaling alongside pretraining,
RL, and inference-time compute.
You could call it test-time
training or dreaming.
The model spends compute writing up
RL environments and then training
against them, and it's rehearsing all
the skills that will actually be used
in production for a specific user.
So instead of hitting /compact in Codex
or Cursor or Claude, which kindles a small
amount of compute to write up a summary,
and which gives you the simulacrum of
continual learning, you hit /dream.
And this incinerates huge amounts of
compute to build and train against a
video-game version of what the model
is witnessing in the real world.

</details>

### 2027-2028 的持续学习愿景

那么，到 2027 或 2028 年，持续学习会是什么样子？我们如何实现它？以下是一个场景。

所有这些 RLVR 训练正在产生一个智能体，当它被扔到一个不熟悉的问题上时，能够迅速定位，尝试不同的策略，并在遇到障碍时进行迭代。这是 RLVR 给你的关键东西：一个至少足够胜任、可以开始获取一些现实世界经验的 AI——如果它能从中学习的话。一旦你有了这个，你就把它送到现实世界去做真正的工作，即使是那些偏离训练分布的项目。

假设此时，有效的上下文长度已经扩展到 AI 可以与你一起协作整整一周的挂钟时间。在一周结束时，你给它一个“赞”或“踩”，你给它一份工作评估。如果你给了“赞”，基础模型就会蒸馏 AI 在会话中学到的一切，它可能会使用 OPSD，可能会使用梦境模拟，可能会使用我们甚至不知道的其他技术，或者会结合使用以上所有方法。AI 可以在与它之前通过 RLVR 明确训练的领域相邻的领域变得更好。在下一轮中，它会在与之前在线学习的内容相邻的领域变得更好。

通过这种方式，AI 技能、知识和能力的范围可以远远超出模型在部署前最初训练时所依据的可验证领域。正如预训练创造了一个足够智能的基础智能，通过在其上进行足够的 RLVR 可以成为一个称职的智能体一样，RLVR 也创造了一个足够称职的智能体，可以真正被广泛部署到世界中，并且一旦持续学习的训练配方真正到来，就能从这种广泛部署中在职学习。

到那时，AI 变得更好的主要方式，将不再是它们在发布给公众之前所接受的训练。而是来自于它们被广泛部署在经济中、参与如此多不同类型任务所积累的所有经验。每次你与 AI 互动时，它都会变得更聪明，不仅因为它从你之前的会话中学习，还因为它从与世界上所有其他用户的互动中学习。这非常令人恐惧、兴奋，并且与当前 AI 改进的方式截然不同。

<details>
<summary>Original English</summary>

So what might continual learning
look like by 2027 or 2028?
And how do we get there?
Here's one scenario.
All of this RLVR training is producing
an agent that can get its bearings when
it's thrown at an unfamiliar problem,
and it can try different strategies, and
it can iterate when it hits a roadblock.
This is the crucial thing that
RLVR has given you: an AI that
is at least competent enough to
start getting some real-world
experience, if it could learn from it.
And once you have that, you send
it out into the world to do real
work, even on projects that are
off the training distribution.
Now let's say at this point, the
effective context lengths have expanded
such that AIs can jam and co-work with
you for a full week of wall-clock time.
At the end of a week, you give
it a thumbs up or a thumbs
down, you give it a work review.
And if you give it a thumbs up, the
base model distills everything that
the AI learned during the session, and
it may use OPSD, it may use dreaming,
it may use some other technique that
we aren't even aware of, or it'll use
a combination of all of the above.
And AI can get better at domains that
are adjacent to what it was explicitly
trained for beforehand with RLVR.
And in the next round it gets better
at the thing adjacent to what it
was previously online learned.
In this way, the gamut of AI skills
and knowledge and capabilities can
expand far beyond the verifiable
domains that the model was originally
trained against before it was deployed.
Just as pretraining created a base
intelligence that was smart enough to
become a competent agent with enough
RLVR on top, so RLVR has created an agent
that is competent enough to actually
be broadly deployed in the world, and
from this broad deployment to learn on
the job once the training recipe for
continual learning actually arrives.
By this point, the main way that
AIs get better is not from the
training they have received before
they are released to the public.
Rather, it's from all this experience that
they'll be accumulating from being broadly
deployed in the economy and engaging
in so many different kinds of tasks.
Every time that you interact with an
AI, it'll be smarter, not only because
it's been learning from your previous
sessions, but also because it's been
learning from all its interactions
with all the other users in the world.
And that's very scary and
exciting and different from the
way that AI improves right now.
This was a narration of a blog
post that I also released on
my website at dwarkesh.com.
Go there if you want to read all
the footnotes, or if you want to
sign up so you can find out when
I release the next blog post.
Otherwise, I'll see you
on the next episode.

</details>