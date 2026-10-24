---
author: The MAD Podcast with Matt Turck
date: '2026-06-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oWOz2htozfI
speaker: The MAD Podcast with Matt Turck
tags:
  - reinforcement-learning
  - large-language-models
  - scientific-discovery
  - model-reasoning
  - ai-ethics
title: OpenAI Dan Roberts访谈：AI为何能进行科学发现
summary: 本访谈深入探讨了AI在科学发现中的角色，特别是强化学习（RL）的重要性。OpenAI的Dan Roberts分享了他从理论物理学到AI的职业转变，并解释了RL如何驱动模型进行创新性思考和数学难题攻克。对话涵盖了RL的运作机制、其在大型语言模型（LLM）中的应用、与预训练的协同作用，以及AI在科学研究中探索与利用的平衡。Roberts强调了RL在将计算转化为智能方面的核心作用，并展望了AI在自动化科学发现和解决基础科学问题上的潜力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Dan Roberts
  - Rich Sutton
  - Noam Brown
companies_orgs:
  - OpenAI
  - DeepMind
  - Anthropic
  - MIT
  - Facebook AI Research
  - Sequoia Capital
products_models:
  - GPT-4
  - ChatGPT
  - AlphaGo
media_books:
  - The Principles of Deep Learning Theory
status: evergreen
---
### AI与科学发现的突破

**Matt Turk**: 大家好，我是**Matt Turk**，欢迎收听Matt播客。过去几天在AI领域又发生了非凡的事件，**OpenAI**、**DeepMind**、**Anthropic**等公司解决了一些数学领域最著名的长期未解难题，即**Erdos问题**。许多人认为这是一个惊人的突破，也是AI正从执行我们要求的任务转向自主进行深度科学发现的又一信号。为了深入探讨这一时刻以及使之成为可能所依赖的模型推理方面的根本性进展，我很高兴邀请到**Dan Roberts**，他是OpenAI的顶级AI研究员，拥有深厚的理论物理学背景，对科学与AI的交叉领域特别感兴趣。在这次对话中，我们将深入探讨**强化学习**到底是什么，为什么它是当前AI领域最重要的范式，以及AI和科学的未来。请欣赏我与Dan Roberts的对话。嘿，Dan，很高兴能做这个节目。谢谢你抽出时间。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, I'm Matt Turk. Welcome to the Matt podcast. It's been yet another extraordinary last few days in AI with OpenAI, DeepMind, Anthropic, cracking some of the most famous long unsolved questions in mathematics known as the Erdos problems. A moment many view as a stunning breakthrough and yet another signal that AI is moving from doing the work we ask of it to autonomously making deep science discoveries. to unpack the moment and the fundamental advances in model reasoning that make it possible. I'm excited to welcome Dan Roberts, a top AI researcher at OpenAI, who comes from a deep background in theoretical physics and has a particular interest in the intersection of science and AI. In this conversation, we go deep on what reinforcement learning actually is, why it's the most important paradigm in AI right now, and what's ahead for AI and science. Please enjoy my conversation with Dan Roberts. Hey Dan, excited to do this. Thanks for taking the time.

</details>

**Dan Roberts**: 当然，非常高兴能来。

<details>
<summary>Original English</summary>

**Dan Roberts**: Of course. Very happy to be here.

</details>

### OpenAI强化学习团队的使命

**Matt Turk**: 你是OpenAI强化学习基础团队的负责人。那这意味着什么？这个名字意味着什么？

<details>
<summary>Original English</summary>

**Matt Turk**: You are the lead of the foundations of reinforcement learning team at OpenAI. So what what does that mean? What does the name mean?

</details>

**Dan Roberts**: 我们所在的这个更大的团队叫做“基础团队”，我们思考的是**强化学习**。所以，这个名字很无聊，就是**强化学习的基础**。但这个团队的使命是思考强化学习的科学。很久以前，用AI的说法就是大概六个月前，也许现在是一两年了。在我们发布**GPT-1**并思考推理模型之前，我们内部就在研究这个。成为先行者，或者至少是被迫投入大量资源来扩展事物的一个优势是，你可以授权一群人不仅致力于让事情运作起来，更要致力于理解它如何运作。然后，在此之上，我们如何扩展？我们应该如何思考强化学习的扩展与预训练的扩展？所以，扩展定律会是什么样子？但除此之外，这种训练会教给我们什么？它不会教给我们什么？我们非常感兴趣的是，在探索性场景的前沿，我们如何改进或更好地理解强化学习正在做什么？我们拥有所有这些计算资源，众所周知，我们正在获取它们，我们希望将这些计算转化为智能，为此我们需要制造**思维模型**。在这个过程中，我们在早期阶段与这个过程互动，通常是针对那些不是下一个模型，而是像“下下个模型”或“下下下个模型”的东西。

<details>
<summary>Original English</summary>

**Dan Roberts**: The larger team that that we're on is called foundations and we think about reinforcement learning. So very boring foundations of reinforcement learning but the team comes from a mandate of of thinking about the science of reinforcement learning and a long time ago which in AI speak is like 6 months ago maybe a year I guess now two years. So before we released 01 and thinking reasoning models, we were studying this internally and and one of the advantages to being first or at least to being forced and and spending a lot of resources on scaling things up is that you can empower a group of people to not just work on making the thing work, but work on understanding how it works. And then beyond that, how do we scale? How should we think about scaling reinforcement learning versus scaling pre-training? So what what are scaling laws look like? But then going beyond that, what what sort of things does this kind of training teach us? What doesn't it teach us? We're very interested in at the frontier for exploratory scenarios. How do we either improve or understand better what reinforcement learning is doing? We have all this compute that famously we are in the process of of of of acquiring and we would like to turn that compute into intelligence and to do that we need to make thinking models and some somewhere along the way we interact with that process usually at the earlier stage uh for models you know not the next model but things that are like the next model or the next next model.

</details>

### 从理论物理到OpenAI

**Matt Turk**: 很好。那么，你进入OpenAI的经历是怎样的？你是如何从学习物理学到今天的职位的？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. And uh quickly what was your path to open AI? So, how did you go from studying physics to being where you are today?

</details>

**Dan Roberts**: 我在**麻省理工学院**获得了理论物理学博士学位，研究**量子引力**和**量子信息**的交叉点。我思考了很多关于**黑洞**、**量子混沌**的问题，比如如果你把东西扔进黑洞，信息会发生什么？它会出来吗？如果我们把黑洞看作计算机，它们的速度有多快？我对理论物理学中一个基本问题非常感兴趣，那就是如何找到一个**量子引力理论**。我也对计算与物理定律之间的这种相互作用非常感兴趣。你知道，任何计算机都存在于宇宙中，并根据物理定律运行。所以你能进行的计算受到物理定律的限制，这其中存在着某种有趣的关系。黑洞非常有趣，因为它们似乎饱和了一些关于信息处理的推测边界。

<details>
<summary>Original English</summary>

**Dan Roberts**: I did a PhD in in theoretical physics uh from from MIT thinking about the intersection of quantum gravity and quantum information. Thought a lot about black holes, quantum chaos kind of thing of what if you throw something into a black hole, what happens to the information? Does it does it come out? How if we think about black holes as computers, how fast are they? I was very interested in this fundamental question in theoretical physics which is how do you find a quantum theory of gravity. I also got very interested in this interest interplay between computation and the laws of physics. You know any computer exists in the universe in in you know behaves according to physical law. So the sort of computations you can do are bounded by the laws of physics and there's some sort of interesting relationship there. Black holes are pretty interesting because they sort of saturate some conjectured bounds around processing of of information.

</details>

**Dan Roberts**: 从那以后，我在**普林斯顿高等研究院**做博士后。大约在那个时候——我对于这个领域来说已经相当老了——那大概是**2016年**。**DeepMind**的**DQN Atari论文**是在**2015年**发表的，然后**AlphaGo**是**2016年**。我当时对这些非常兴奋，对**机器学习**以及后来的**深度学习**的可能性感到非常兴奋，它是一种**统计科学**，存在于一个与我们用来研究宇宙其他部分的框架相似的框架中。所以总有这样的问题：你知道，一切是如何运作的？这个三岁小孩会问的问题：我对一切都好奇。如果你向外看，你足够关心，你最终会走向哲学。如果你是量化思维，你最终会走向物理学。这是一个非常粗略的概括。一个能工作的AI，或者说能工作的AI系统，都非常引人入胜，因为它们是简单的例子，能做人类能做的事情。如果它存在于我们用来理解其他一切的同一个框架中，那么，你知道，你就可以在宇宙如何运作和“我”如何运作，或者**智能**如何运作之间建立联系。

<details>
<summary>Original English</summary>

**Dan Roberts**: And from there I did a posttock at the institute for advanced study and at around that time I'm pretty old now for at least for this field. So that was about 2016 uh was when the DQN Atari paper from deep mind happened in 2015 and then AlphaGo was in 2016. And I got very excited about these um about the possibility of uh machine learning and then and then deep learning was statistical science that lived in a similar framework to the sort of frameworks that we use to like study the rest of the universe. And so there's always this question of of of you know how does everything work? This three-year-old question of I'm curious about about everything. And if you look outward and you you care enough, you end up philosophy. Maybe if you're quantitative, you end up in in in in physics. Very very crude characterization. An AI that works is very fascinating or AI systems that work is are are fascinating because they are simple examples that do things that humans do. And then if it lives in the same framework that we use to understand everything else then you know it's sort of like you can you can draw the parallels between how does the universe work and how do I work or how does intelligence work.

</details>

**Dan Roberts**: 所以我对**AI**和**深度学习**产生了极大的兴趣。然后，我大约在**2017年**去了**Facebook人工智能研究实验室（FAIR）**，基本上是想尝试利用理论物理学的工具来理解深度学习。深度学习被认为是这种非常困难、你无法理解的东西。我认为物理学的工具可能有所帮助。这最终凝结成了一本书，是我和一位合作者共同撰写的，他现在仍然是我的合作者，目前也在OpenAI从事同样的工作。我们写了这本名为《**深度学习理论原理**》的书，它是这些思想的结晶，即我们能否利用统计学思想，比如理解房间里的气体这样的统计系统，我们可以用一些简单的**热力学定律**来描述它们，比如**理想气体定律**，也许我们可以在理解**深度网络**方面取得类似的进展。

<details>
<summary>Original English</summary>

**Dan Roberts**: So I got extremely interested in in AI and and deep learning. Then I uh went to fair Facebook's AI research lab at around 2017 2017 to basically try and use the tools from theoretical physics to understand deep learning. Deep learning was supposed to be this really difficult thing that you couldn't understand. And uh I thought maybe the tools of physics could could be helpful. Uh this actually culminated in a book that I wrote with a collaborator who now is um a collab still collaborator of mine now at at OpenAI working on the same thing as Shya. But we wrote this book the principles of deep learning theory that is a culmination of of of these sets of ideas of can we can we sort of use the statistical ideas of of of uh you know understanding statistical statistical systems like the gas in in in the room. we can characterize them with some simple laws of thermodynamics like the ideal gas law and and maybe we can make similar progress in understanding deep deep networks.

</details>

**Dan Roberts**: 所以，嗯，那就是我转型的过程。我也曾创办过一家初创公司，并在**红杉资本**担任驻场企业家。所以，做科学家和做企业家之间存在一些张力。但在大约两年前，在我考虑是否要再创办一家AI公司之后，我意识到当下最令人兴奋的事情是前沿正在发生的一切，即AI领域正在发生一些惊人的科学进展。要真正理解这些问题并参与其中，你就需要身临其境。这意味着加入实验室，所以我两年前加入了OpenAI。

<details>
<summary>Original English</summary>

**Dan Roberts**: So um that was sort of my transition. I also had a startup along the way um and spent some time at Sequoia Capital uh as an entrepreneur and resident. So there's some tension between am I a scientist and am I entrepreneur but about 2 years ago after thinking about whether I want to start another AI company I realized that the the thing that was most exciting right now was what was happening at the frontier that there's some some some amazing scientific progress happening in in AI and to really get at the questions and understand what's going on you need to be there and you need to participate and and that that meant joining joining lab so I I joined OpenAI two two years ago.

</details>

### AI解决科学难题的演进

**Matt Turk**: 太棒了，谢谢你。你认为目前AI在解决复杂科学问题方面的演进处于什么阶段？我的意思是，这当然是我们行业一直在讨论的事情，但它似乎正在加速，也许就像AI领域的一切一样。但你认为我们现在处于什么阶段？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. Thank you for that. Where do you think we are in the evolution of AI being increasingly able to solve difficult scientific problems? I mean, certainly something that we've been talking as an industry about for a while now, but it seems to be accelerating perhaps just like everything else in in AI. But where do you think we are?

</details>

**Dan Roberts**: 我认为有趣的一点是，这个过程是平滑的。没有一个明确的转折点，或者说，我认为不会有一个明确的转折点，我们会说系统对科学过程不再有用，直到它们成为完全成熟的科学家。这将是一个渐进的转变。如果你非要指一个时刻，也许会是**GPT-1**的发布，以及OpenAI所开创的**测试时计算**和**推理**范式。但我相信，如果我试图提出这个主张，你可以去看看**GPT-4**，你会发现对科学过程有用的行为的某些闪光点已经存在。

<details>
<summary>Original English</summary>

**Dan Roberts**: I think one of the interesting things is that this process is smooth. the there's no sharp point or I don't think there will be a sharp point where we'll say that systems didn't weren't able to be useful for scient the scientific process to their fullyfledged scientists. There will be sort of a gradual shift. If you had to point to one moment, maybe it would be the release of 01 and by OpenAI and and the sort of paradigm of test time compute and and and reasoning. But I'm sure if I tried to make that claim, you could go and look at GPD4 and and see that there's um glimpses of that sort of useful behavior for for the scientific process were were already present.

</details>

**Dan Roberts**: 作为一个普遍观点，你知道，模型非常擅长某些类型的事情，这些事情显然有助于在数学领域取得进展。它们并非在任何领域都是**开放循环**的完全成熟的科学家。虽然，你知道，我也不是。这似乎只是一个非常好的渐进过程。所以，这周感觉非常有趣，可以进行这次对话，因为过去几天，AI和数学的普遍领域出现了许多不同的公告，围绕着**Erdos问题**。OpenAI率先取得了这一进展，但几乎在几个小时内，**Google DeepMind**也针对不同的问题提出了主张，**Anthropic**也有一些主张。然而，据我所知，OpenAI的方法和DeepMind的方法非常不同，这对于AI作为一名研究科学家来说，其意义可能非常有趣。

<details>
<summary>Original English</summary>

**Dan Roberts**: As a general point, you know, the the models are very good at certain types of things that clearly are amendable to to making progress in math. They're not open loop fullyfledged scientists in in any domain. Although, you know, neither am I. It seems like it's just this really nice gradual process. So it feels like a particularly fun week uh to be having this conversation because over the last few days uh there were a number of different announcements uh in the general field of AI and mathematics around the airdos problems. OpenAI came out first with this progress but like almost within a few hours Google deep mind had a claim as well on different problems. and anthropic had some claims. However, from what I understand, the open AI approach and the deep mind approach were were very different and that may be very interesting in terms of what that means for AI as a research scientist.

</details>

### Erdos问题的攻克：反向思维与跨领域洞察

**Dan Roberts**: 这个猜想每个人都认为是真的，但无法证明。**ChatGPT**能够做的一件事是，它假设它是假的。当你逆流而上，做出这样一种**反主流**的事情时，你真的需要对你正在做的事情有坚定的信念，才能坚持走完一个非常长的计算路径，因为在这一路上你可以做出很多选择。如果你在这些选择中任何一个地方出错，如果你的想法行不通，那么你就会发现你没有取得任何进展。所以，你需要这种非常强的**毅力**。

<details>
<summary>Original English</summary>

**Dan Roberts**: This conjecture everyone assumed was true and uh but could not prove it. One of the things that Chach GPT was able to do was uh assume it was false. And when you go against the grain and and do something contrarian like that, you really have to have strong conviction in what you're doing in order to persevere down a really long calculation path because there's a lot of choices that you can make along along the path. And if you get any of those choices wrong, if you if your ideas don't work, then you find out that that you didn't make any progress. And so um you need this really strong persistence.

</details>

**Dan Roberts**: 然后你还需要另一个领域的专业知识，比如**代数数论**，它是**数论**的一种泛化，涉及到整数和实数的泛化。如果你沿着这条路走得很远，你就可以推翻这个猜想。所以，这就是重大成果。重大成果是，这个关于你可以形成的**数对下限**的猜想是错误的。它不仅是错误的，而且它的错误是由于它与数学的另一个领域有着非常有趣的联系。所以，你必须是一个既知道这个问题很有趣，又在其他领域有专业知识的人，然后还要非常反主流，走一条非常漫长的道路，然后你才能找到解决方案。

<details>
<summary>Original English</summary>

**Dan Roberts**: And then you need expertise in this other field. uh which is like algebraic number theory, some sort of generalization of number theory on um you know things that sort of generalize the the integers and the real numbers. You go down that path really far, you can refute this conjecture. So that that was the big result. The the the big result was that this this conjecture of of this lower bound for the number of pairs that you can make is is false. Not only is it false, it was false due to a really interesting con connection to another field of of mathematics. And so you would have to be somebody who is aware of this problem as interesting which sounds like you know your expertise is one thing and then be an expertise in something else and then then also be super contrarian and go down this really long path and and then you could you would you would have identified the solution.

</details>

### OpenAI与DeepMind解决数学问题方法的对比

**Matt Turk**: OpenAI的方法和DeepMind的方法非常不同。你愿意比较和对比这两种方法吗？

<details>
<summary>Original English</summary>

**Matt Turk**: The open AI approach and the deep mind approach were were very different. Do you want to compare and contrast the two approaches?

</details>

**Dan Roberts**: **DeepMind**采取的方法之一是，将问题以一种名为**Lean**的**形式语言**呈现，然后使用方法在该语言中搜索证明。对于某些问题，为了使其可表示，有一个过程称为**自动形式化**，你将问题的英文版本翻译成严谨的形式化陈述，然后你在其中进行证明。它的设计使得证明可以**滴水不漏**。没有人需要去检查是否存在某些隐藏的假设或奇怪的东西，或者我猜通常是隐藏的假设或不严谨的定义。但在DeepMind非常关注的这种设定中，他们能够形式化一些问题，并使用他们的系统来证明它们。

<details>
<summary>Original English</summary>

**Dan Roberts**: One of the approaches that GDM takes is to take problems, present them in a formal language called lean and then use methods to search for proofs in in that language. And some problems for problems to be representable, there's this process called auto formalization where you take English version of the problem and you translate it into rigorous formal statements and then you you conduct your proofs there. And it's it's it's designed so that the proofs can be airtight. No one has to go and check for for some hidden assumption or some weird thing or I guess it's usually hidden assumptions or definitions that are not airtight. But in that setting, which is a setting that DeepMind has has has cared a lot about, they were able to formalize some some problems and and use their use their system to prove them.

</details>

**Dan Roberts**: 所以那是一种方法。另一种方法是直接用英文来处理问题，其中也包含数学表达式，但只是问题的非正式英文陈述，理解其含义，并以非正式语言解决问题，呈现一个证明，就像人类数学家会做的那样，或者像一个不使用Lean的人类数学家会做的那样，然后你需要去检查它。**验证问题**更难，因为它不是可以自动检查的。

<details>
<summary>Original English</summary>

**Dan Roberts**: So that's that's one approach. Another approach is to just take the problem in English with mathematical expressions as well but just the English statement of it which is informal and understand what is meant by that and solve that in informal language presenting a proof much like the way a human mathematician would or a human mathematician who's not using lean and then you have to check it. It's the the verification problem is is is is harder because it's not something that auto checks.

</details>

**Matt Turk**: 第二种方法就是OpenAI采取的。

<details>
<summary>Original English</summary>

**Matt Turk**: And that second approach was open AI.

</details>

**Dan Roberts**: 据我所知，我们公布的大多数成果都是在**非正式**环境下取得的。我们有**语言模型**，我们教它们在**测试时进行推理**，其中一个应用或基准就是**数学推理**。

<details>
<summary>Original English</summary>

**Dan Roberts**: Most of our results that we publicize as far as I I can think are all in the informal setting. We have we have language models that we've taught them to reason at test time and and one of the applications or benchmarks for that is is reasoning in in mathematics.

</details>

### 强化学习（RL）的定义与类比

**Matt Turk**: 好的，太棒了。那么，让我们来谈谈**强化学习**，让它更广泛地为人所理解。让我们从头开始。用一两句话定义一下强化学习，并举一个简单的非技术性例子，让大家都能明白。

<details>
<summary>Original English</summary>

**Matt Turk**: Okay, great. All right. So let's get into reinforcement learning to make this uh broadly accessible. Let's start uh from the top. What what is the one two three sentences definition uh for reinforcement learning and perhaps give us a simple non-technical analogy for people to understand.

</details>

**Dan Roberts**: 也许一个简单的方法是给你两个例子，说明你个人可以如何尝试学习某样东西。我们可以拿一个游戏，或者一个**视频游戏**。我年纪足够大了，玩过最初的**8位《超级马里奥兄弟》**。有两种学习玩游戏的方式。一种是你爸爸把它拿出来，插上电源，启动游戏，然后他玩几个小时，你就只是看着他玩。你就只做这个。所以他是在演示如何玩。然后，在演示结束后，他，你知道，他不是很友善，所以他不让你玩，但他出去玩别的了。然后，你知道，你偷偷溜进他的房间。你插上游戏机，然后你尝试玩。你玩得会有多好呢？

<details>
<summary>Original English</summary>

**Dan Roberts**: Maybe a simple thing to do would be to to give you two examples of of how you could try to learn something. you you as an individual. Um, and and maybe we can we can take a game or even a say say a video game, right? I I'm old enough that where I played the original 8-bit Mario Brothers, the Super Mario Brothers. And so here are two ways you could learn how to play. One way you could learn how to play is your dad takes it out um and plugs it it in and he boots up the game and then he plays for a few hours and then you you just watch him play. That's all you do. Um, so he's demonstrating how to play and then at the end of that he, you know, and he's not very nice, so he doesn't let you play and but then he like goes and runs outside and does something else and, you know, you sneak into his room. You you plug it in and you try to play. How how good are you going to be?

</details>

**Dan Roberts**: 嗯，你所做的一切都只是试图记住他做了什么。你没有机会自己按任何按钮。你没有机会自己与游戏互动。这有时被称为**专家演示**，你知道，你只是试图记住别人在做什么。这就是**监督学习**的版本。监督的意思就是你只看他做了什么，并接受那就是做事的正确方式。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: Well, all you've done is tried to memorize what he's done. You haven't gotten to push any of the buttons yourself. You haven't gotten to to interact with with the game yourself. Um this is sometimes called um expert demonstrations and and um and you know you're you're you're just trying to memorize what someone else is doing. It's the version of supervised learning. The supervision being like you you just watch what he does and and accept that that's the true way of doing a thing.

</details>

**Dan Roberts**: **强化学习**则是你爸爸说：“来，你玩吧。”也许他给你演示一次，或者他甚至不需要演示，因为游戏设计得很好，可以把你从一无所知带到熟练地玩，这被称为**课程**。但是你玩的时候，你做的第一件事可能是跑过去，撞到第一个坏人，你可能会——这个例子有点过时了——但你知道你丢了一条命。但第二次，你按下一个按钮，你跳了起来。所以你在采取行动，有一个环境在给你反馈。你知道，环境、你能采取的行动以及你得到的反应之间有密切的联系。最后一部分是有一个**奖励**。这个奖励，你知道，可以是你经常得到的东西，例如，你每做一件事，就会有一些分数上升。或者它可能只是你在最后得到的东西。所以你玩一局**国际象棋**，最后你得到一个奖励，就是你赢了或输了，但在中间你并不知道自己做得怎么样，直到最后。这被称为**稀疏抵抗奖励**。但我认为这是一个基本思想，尽管这里有很多变数，也有很多可以争论的地方，但它的核心理念是，你与环境互动，你得到奖励，而且通常是以这种反馈的方式，而不是仅仅试图从你无法互动的数据中学习。

<details>
<summary>Original English</summary>

**Dan Roberts**: Reinforcement learning would be your dad's like here why don't you play? Maybe he shows you once or maybe he doesn't even need to show you because the the game is, you know, beautifully designed to to sort of take you from not knowing anything to to being able to play expertly as something called a curriculum. But you you play maybe the first thing you do is you run, you hit the first bad guy and you probably this example is dated, but you you know you you you lose a life, but then the second time you press a button and you jump. And so you're taking actions, there's an environment that's giving you feedback and you, you know, there's this this close connection between the environment, you know, between um actions that you can take and then the responses that you're getting. And and then the the final part is there's a reward. And the reward um you know, can can be something that you get pretty often for for instance, every time you do something, there's there's some score that goes up or it could be just something that you get at the end. So you play a game of uh of chess and and and at the very end you you get a reward which is you won or you lost but in the middle you don't really know how you're doing until until the very end. So this is called sparse resistance rewards. But I think this is a basic idea in that um and there's there's obvious lots of variance here um and ways to quibble with this but it's this this notion that you you interact with an environment you get an reward and often it's it's in a way where you get this sort of feedback as opposed to just trying to you know learn from data that you don't get to interact with.

</details>

### 强化学习为何强大及其局限

**Matt Turk**: 那它为什么有效，为什么**强化学习**如此强大？

<details>
<summary>Original English</summary>

**Matt Turk**: And why does it work and why is RL so powerful?

</details>

**Dan Roberts**: 它之所以有效，是因为它能够从环境中获得**反馈**。如果你做得对，你就可以去学习，去弄清楚如何学习你不知道的东西。我还认为它之所以强大，是因为它更容易在你适合的水平上学习。如果你想学习加法，你不应该去读一本**微积分**教科书。你应该通过练习来学习，并在合适的水平上学习。我实际上是在做出选择，并从我自己的选择中学习，无论它们是否有效，然后我就能更好地将它置于我所理解的事物背景中。

<details>
<summary>Original English</summary>

**Dan Roberts**: It works because of this ability to get feedback from the environment. you can go and learn, you know, if you if you're doing it right, you can figure out how to learn the things that that that you don't know. And I also think it's powerful because of this fact that it's it's much easier to learn when you're learning at at the right level for for you, right? So, if you want to learn, you know, addition, you shouldn't read a calculus textbook. You want to learn by being able to practice and and learn at at at the right level. I'm actually making the choices and and and learning from my own choices whether they work or not then then I'm able to like place it in a better context for for the set of things that I understand.

</details>

**Matt Turk**: 很好。那么反过来，它的症结在哪里，以及**强化学习**会在什么情况下失效？

<details>
<summary>Original English</summary>

**Matt Turk**: Great. And then conversely what's the catch and how does RL break

</details>

**Dan Roberts**: 强化学习非常困难的场景，就是我之前提到过的，你无法从环境中获得太多**反馈**。你必须采取很多很多很多行动，然后你可能只会得到一个“是，这整套行动都很好”或者“不，这很糟糕”的反馈。例如，你正在玩一局**国际象棋**，直到你走出所有棋步，你才知道你做得怎么样，而且它有一个对手，所以这可能很复杂。也许你正在尝试做一个家庭作业问题，它是一个研究级别的，或者你知道，就像有人给你一个**定义明确**的问题，就像我们给语言模型的问题一样，它是一个需要思考几天甚至几周的问题，你可以在过程中做出很多选择，而如果最后你根本没有得到任何反馈，如果你只是独自一人躲在森林里，在笔记本上乱涂乱画，那么以这种方式取得进展是非常困难的。因为你没有任何反馈，你无法判断最后得到“是”还是“否”，也无法判断你所采取的哪些行动、你所做的哪些事情是好的还是坏的。

<details>
<summary>Original English</summary>

**Dan Roberts**: the setting where very difficult is is the setting um that I alluded to before where you don't get much feedback from the environment. you have to take many many many many actions and then you get maybe yes that whole set of actions was good or no it was bad. For instance, you're playing a game of chess and you don't know what you know until you make all the moves that has an opponent so it's maybe complicated. Maybe it's you are trying to do a homework problem and it's a research level or you know like someone gives you a well- definfined problem like we give our language models and it's uh you know a problem that requires days and days of thinking there's so many choices that you can make along the way and at the end if you if you don't get any feedback at all if you're just hidden in the woods by yourself scribbling in notebooks it's very hard to make progress that way um because you don't have any feed you don't have any sense if you get a yes at the end or you get a no at the and you have no sense for which of the the actions that you took, which of the things you did were were good or bad.

</details>

### RLHF在大型语言模型中的应用

**Matt Turk**: 好的，太棒了。现在，让我们谈谈**强化学习**是如何应用于**大型语言模型（LLM）**的。历史上，第一步是**RLHF**吗？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay, great. Now, let's talk about how uh RL has been applied in the context of large language models. So, was the first step historically RL HF?

</details>

**Dan Roberts**: 是的，我认为这可能公平，至少从广义上讲，在语言模型上进行的**强化学习**的第一种形式是**后训练过程**的一部分，目的是将一个只尝试预测互联网上下一个单词的模型，转化为一个能够遵循你的指令、对你友善、或者符合**聊天机器人**形式的模型。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: Yeah, I think that's probably fair at least in a broad sense that the first kind of RL that was done on language models was part of this post training process to turn a model that just tries to predict the next word on the internet into into either something that will follow your instructions, be nice to you, you know, or like fit the form of a of a chatbot.

</details>

**Matt Turk**: 那么，你能为人们定义一下**RLHF**是什么以及它是如何运作的吗？

<details>
<summary>Original English</summary>

**Matt Turk**: So do you want to define for people what uh RHF is and sort of how it works quickly?

</details>

**Dan Roberts**: 基本思想是你可以使用从人类那里收集到的数据。所以**RLHF**就是**来自人类反馈的强化学习**。你从人类那里收集数据，然后你训练一个**价值函数**。所以在语言模型设定中，你可能会展示来自语言模型的两种不同的完成结果。要求他们说哪个更好。这种比较可以用来训练一个价值函数，然后你可以将其用作强化学习过程的奖励。

<details>
<summary>Original English</summary>

**Dan Roberts**: The basic idea is that you could use uh collect data from from humans. That's so the RLHF is reinforcement learning from human feedback. So you collect data from humans and you train a value function. So you would show in the language model setting say two different completions from from from a language model. Ask them to say which is better. this this sort of comparisons could be used to train a value function and then you can um use that as a as a as a reward for for reinforcement learning process.

</details>

**Matt Turk**: 很好。你最初是用人类来做这个，然后你把它构建成一个**奖励模型**。

<details>
<summary>Original English</summary>

**Matt Turk**: Great. And uh you you do that initially with humans but then you build that into a reward model.

</details>

**Dan Roberts**: 是的。所以你会为此训练一个模型。然后，在训练过程中，你不能只是暂停训练，向人类寻求输入。那样**延迟**太大了。所以你需要一个人类反馈的代理。所以你根据人类偏好数据训练这个模型，然后你可以根据它进行优化，至少是一部分。

<details>
<summary>Original English</summary>

**Dan Roberts**: Yeah. So you would train a model for this and then and then now because during the training process you can't just pause your training run to ask some humans for for input. um right the the feedback the that that would have way too much latency. So instead you need a proxy for what a human would say. So you train this model based on based on the human preference data and then you can optimize against it or at least a little bit.

</details>

### Go与扑克机器人中的探索与利用

**Matt Turk**: 在**强化学习**的历史上，有一个著名的例子是**“37号棋步”**。你如何训练一个模型，鼓励它做这类事情，并以高效的方式提出全新的方法，同时又能利用已知路径？

<details>
<summary>Original English</summary>

**Matt Turk**: One of the famous things in the history of RL is uh moves 37. How do you um train a model to encourage the model to do that kind of things and come up with brand new ways while being efficient and exploit known path?

</details>

**Dan Roberts**: 是的。关于**Go**的妙处在于，你可以直接训练它。它是一个**零和双人游戏**。你可以训练它进行**自博弈**。它自己下棋，可以从随机下棋到专家级，它会找到最好的策略。所以如果这意味着**探索**，那很好；如果这意味着**利用**，实际上我有一个关于这个的有趣故事。我在研究生院认识了**Noam Brown**。他去了另一所研究生院，但他想参加**麻省理工学院**的**扑克机器人竞赛**。他有一个扑克机器人，是世界上最好的，但它还不能和人类竞争。他只是赢得了这项研究竞赛。他和我以及另一位朋友合作，参加了麻省理工学院的扑克机器人竞赛。这对我来说非常棒，因为我在做物理研究时学到了一些非常令人兴奋的AI工作，并对此非常兴奋。

<details>
<summary>Original English</summary>

**Dan Roberts**: Yeah. Uh so the great thing about Go is that you can just train it. It's a you know zero sum two-player game. You can train train in what's called selfplay. It plays itself and it can go from playing randomly to expert play and it will find whatever the the sort of best best strategies are. So if that means exploring great if that means exploiting uh actually I have a I have a funny story about this. Um so I I met Noam Brown in grad school. um he went to a different grad school than me, but he wanted to enter MIT's poker bot competition. And he had a poker bot that was the um best in the world, but it wasn't something that would compete against humans yet. He just won in this research competition. He collaborated with me and and another friend to uh enter MIT's Pokerbot competition. This was great actually for me because I learned some really exciting work in in AI and I got very excited about this while I was doing doing physics.

</details>

**Dan Roberts**: 我们当时玩的是一种**自博弈**的**均衡策略**。虽然有一些细微差别，但你知道，基本上，只要我们的代码没有bug，我们就不会输。这个东西的运作方式是一个锦标赛，你会和一个对手配对，然后和他们玩。根据你在某种循环赛设置中获得的积分数量，他们会淘汰一半的选手，并继续进行，直到你进入决赛桌，可能就是你和另一个人对决。然后是颁奖典礼，我们不知道发生了什么，但是有人在记录所有人的分数随时间的变化。比如说，有64个——我记得当时有32个人在玩——所以那大概是32人规模的锦标赛，30个人随着时间的推移，他们的分数都非常负面，一直在下降。然后有一个人的分数几乎是直线上升的，另一个人也很好，但没有那么疯狂的斜率。那么，你猜我们是哪一个？我们是斜率较低的那个，然后另一个人有疯狂的斜率，完全碾压了所有其他玩家。然后这种情况在16强、8强、4强中都发生了。

<details>
<summary>Original English</summary>

**Dan Roberts**: We were playing essentially this this kind of selfplay equil equilibrium strategy. There's some some nuances but you know essentially we could not lose assuming we did not have any bugs in in our code. Um the way this this thing worked was that it was a tournament where you would be paired with say another another person and play them in and if you you know depending on the amount of points you got in like some sort of roundroin setup they would eliminate the bottom half and they would keep going until you got to the final table which would just be say you versus the other person. And so the scores there was the award ceremony and we didn't know what what happened but the there was someone else who was um you know what what what did the what was everyone's scores over time look like and there was you know say 64 I think there were 32 actually people playing so it was like around uh 32 kind of tournament and 30 people over time you know their scores would were all very negative and going down and then there was one person whose score was like like pretty much straight up and then there was another that was like pretty good but but not like with a crazy slope. And um so do do you want to guess which which one we were? So so we were we were the lower slope and then there was this other guy that was had this crazy slope was just like completely crushing all the other players. And then this happened for the round of 16, the round of eight, the round of four.

</details>

**Dan Roberts**: 然后在**两人对决**中，我们对阵这个人，他在整个锦标赛中赢得的钱比我们多得多，总的来说从其他人那里赢走了更多的钱。然后我们击败了他，为什么呢？因为他正在**利用**其他所有人的弱点。他有一些**心智理论**，试图找出“哦，这个人虚张声势时会这样做”，所以我想他非常擅长利用其他人，但我们只是在玩最好的策略，你所能做的就是，你知道，所以标准不是最大化你从其他人那里获得的金额，而是**不要输**，像玩，你知道，所以这是对任何策略的最佳回应，所以最后我们必须赢，假设我们做得对，而另一个玩相同策略的人会打平。

<details>
<summary>Original English</summary>

**Dan Roberts**: And then in the round of two, it's heads up, us versus this guy who's like over the course of this tournament won way more than us uh overall like taking more money from from everyone else. And then we crushed him because why? Because he was exploiting the weaknesses of of of everybody else, right? It it's had some theory of mind to try to figure out oh this this guy you know does this when he bluffs and and so it was very I assume it was very good at at like taking um you know exploiting everyone else but we were just playing the best possible thing that you could that you can do given you know so the the criteria was not maximize your your amount that you get from anyone else it was don't lose like play you know and and uh and you know so it's the best response to anyone's strategy and so at the end we had to win assuming we did it right and someone else playing the same strategy would would tie.

</details>

**Matt Turk**: 好的，太迷人了。那么，把这个话题带回到对话的开头，关于**Erdos问题**和解决未解的数学问题。所以，大概直觉是，你需要大量的**探索**，而不是**利用**。那么，这在**新颖科学发现**的背景下是如何运作的呢？

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. Fascinating. So just tying this back to the beginning of the conversation about air do problem and and solving uh unsolved math problems. So presumably the instinct would be that you need a lot of exploration not exploitation. So how does how does that work in the context of novel scientific discovery?

</details>

**Dan Roberts**: 我认为数学研究或一般的科学研究，有很多方面都包含了**探索**和**利用**。举最近的例子，OpenAI的**单位距离证明**我认为就非常属于探索范畴，模型乐于**反主流**，尝试去反驳每个人都相信的东西。它只是在寻找，它拥有一个巨大的**人类数学知识库**。所以它花费了非常长的时间。我忘了具体多少小时，但我想我们发布了一个改写版，是这种**思维链**，但就像好几个小时都在尝试不同的东西。所以这显然属于探索领域。

<details>
<summary>Original English</summary>

**Dan Roberts**: I think math research or scientific research in general has a lot of versions of both explore and and and exploit. um to give to give the recent example, the OpenAI unit distance uh proof I think is is is is very much in the explorer setting where the the model was happy to be contrarian and and try to disprove this thing that everyone believed and it was it was just looking for it has this huge repository of understanding all of human math. And so it was it was spending a very long amount of time. I forget how how many hours but I think we published a rewritten version this chain of thought but like hours and hours trying different things. So it's clearly in the in the domain of exploration.

</details>

**Dan Roberts**: 不过很多时候，你可以要求这些模型计算它们非常理解的东西，然后这具有不同的结构，可能看起来很像**利用**。最近在OpenAI成果之后发表了一篇论文，它解决了一个不相关的问题。它与**集合论**有关，如果你有一个集合，你尝试将它加到自身，或者你尝试将集合与自身相乘。所以，就像取元素并将它们全部相加，或者取单个元素并将它们相乘，以及你能得到多少个唯一的和或积。这周围有一些猜想。而这个猜想也被推翻了，那是人类完成的，核心思想是，它是一个完全不同的问题，但它受到了**单位距离**问题的启发，即你可以泛化，从“选择一个具有某种属性的数字类型，OpenAI模型发现了这种属性，然后他们意识到这适用于这种设定。”所以这非常像一种利用。

<details>
<summary>Original English</summary>

**Dan Roberts**: Um a lot of times though you can ask these models to uh compute something that they understand very well and then that that has a different structure and might look a lot like exploit. There's a a paper that came out recently after the open AI result where the uh an unrelated problem. It has something to do with uh if you have a set and you try to add it to a cell add the set to itself or you try to multiply the set with itself. So like take the elements and add them all together or take the element individualize or multiply them together and how many unique sums or products you get. There's some conjecture around that. And this this one was also disproved and and that was done by by humans and the core idea was um it's like a totally different problem but there there was inspiration from the from the unit distance one the idea that you you can sort of generalize uh from from the as pick a pick a certain find pick a certain type of of numbers that had a certain property that that the open AAI model figured out and that they realized that like this applies in this setting. So that's very much an exploit thing.

</details>

**Dan Roberts**: 但是，嗯，所以我认为这个过程显然是这样的：实际的发现过程。嗯，我认为通常当你谈论**探索**与**利用**时，我们可能是在讨论训练强化学习模型时应该如何训练它们。但我认为有一个有趣的观点是，在科学发现过程中，探索和利用之间确实存在着相互作用，以便完全推动这个领域向前发展。

<details>
<summary>Original English</summary>

**Dan Roberts**: But um and so so I think the process clearly is like this the actual discovery process. Uh I think normally when you talk about explore exploits maybe we're talking about when training reinforcement learning models how should we train them but I think there's this interesting point that in the scientific discovery process there's really this interplay between like exploring exploration and then exploitation in order to totally push the field forward.

</details>

### RL在现代LLM系统中的核心地位

**Dan Roberts**: 谈到在现代**LLM系统**中转向**强化学习**。以前有一种说法，我想这来自于**Yann LeCun**，说强化学习是蛋糕上的樱桃。但我想你已经说过，现在情况变了，强化学习是蛋糕的主要部分。你能给我们讲讲你的想法吗？

<details>
<summary>Original English</summary>

**Dan Roberts**: switching to RL in modern LLM systems. So there used to be a saying which I think comes from Yanukan that RL was the cherry on top of the cake, but I think you have argued that things have switched now and that uh RL is the main part the the cake. Do you want to just walk us through what you were thinking?

</details>

**Dan Roberts**: 是的，我大概一年半前说过那句话。当时我必须做一个公开演讲，不能说太多。所以我决定颠覆这个关于蛋糕和樱桃的说法。**强化学习**确实非常令人兴奋。这就是我今天在这里谈论它的原因。我认为当你拥有大量计算资源时，你希望以一种有用的方式将这些计算转化为**智能**。而强化学习就是实现这一目标的方法之一。我们当时才刚刚开始做这件事，现在我们将做更多。

<details>
<summary>Original English</summary>

**Dan Roberts**: Yeah, I said that about a year and a half ago. Had to give a talk that was public and I couldn't say much. So, I decided to invert this meme with the with this cake and the cherry. RL is really exciting. That's why what I'm here talking about. And I think that when you have a lot of compute, you want to turn that compute into intelligence in a way that's that's useful. And RL is one way of doing it. and we just started doing it then and we're going to do a lot more of it now.

</details>

### 强化学习为何如今奏效？

**Matt Turk**: 为什么**强化学习**现在开始奏效了呢？它并不是一个全新的概念，已经尝试了很多年。现在有什么不同呢？

<details>
<summary>Original English</summary>

**Matt Turk**: Why did RL start working? Well, it's not an entirely new concept is uh been tried for many years now. Uh what is different now?

</details>

**Dan Roberts**: 是的，说实话，我也不确定当人们说它不起作用时，那到底意味着什么。例如，在**2016-2017年**，甚至到**2018年Transformer时代**之前，**DeepMind**全身心投入到**强化学习**中，**OpenAI**也有**Dota**和**魔方**以及其他一些令人兴奋的成果。很多人都全力投入强化学习，然后出现了**语言模型**，显而易见的做法是扩展那些奏效的东西，也就是**预训练**。我不知道人们对强化学习尝试了什么，正如你指出的，**RLHF**是一个很快就出现的关键事物。最初，它是在**游戏环境**的背景下开发的，比如试图通过使用人类反馈来防止**奖励作弊**，我记得最初的论文是关于使用人类反馈来控制一个角色行走之类的东西。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: Yeah, I'm not sure to be honest what when people say it wasn't working what that actually means. like there was this 2016 27 maybe even to 2018 before the transform period where DeepMind was all in on RL and um OpenAI had Dota and um the Rubik's cube and some other exciting exciting results as well but a lot of people were all in on RL and then there were language models and the obvious thing to do was scale up the thing that worked which was pre-training and I don't know whether or what people tried for RL as you pointed out RHF was a central thing that that came pretty quickly. Originally, it was developed for in the um in the context of of of game environments of of like uh trying to prevent reward hacking by using I think the original paper was about using human feedback to like control uh um uh like a character for walk or some something like that.

</details>

**Dan Roberts**: 但这里有一个有趣的观点，那就是**如何让模型在测试时进行思考和推理**的问题。OpenAI很早就有一个**推理**方面的努力，投入了一些时间，并提出了一些算法。我想也许简单来说就是，如果你有一个足够强大的**预训练模型**，那么它就可以在**强化学习**方面表现出色。它可以在测试时进行思考，利用**测试时计算**来解决它原本无法解决的**数学问题**。

<details>
<summary>Original English</summary>

**Dan Roberts**: But there's an interesting thing to to point out here though which is that uh there there's this question of how do you get models to think in test time and and reason and there was a reasoning effort at OpenAI that was quite early and spent some time and and came up with some some algorithms. I think maybe the simple thing to say is that if you have a powerful enough pre-trained model then it can start to do well at RL. it can start to like think um at at use test time compute to to for instance solve solve math problems that it that it wouldn't otherwise be able to do.

</details>

### RL效率与系统模型

**Matt Turk**: 今年早些时候，也就是**2月**，有一项**病毒式分析**声称**强化学习**每1万个token产生的有用信息不到1比特，然后**Karpathy**称之为“通过吸管吸取监督”。你对此以及**RL的整体效率**有何看法？

<details>
<summary>Original English</summary>

**Matt Turk**: This um a viral analysis uh from earlier this year February I think that claims that um RL produces less than one bit of useful information per 10,000 tokens and then Carpathy called it sucking supervisions through a straw. What is your take on on this and the overall efficiency uh of of a

</details>

**Dan Roberts**: 如果你看一下**DeepSeek算法**，这是一个我们可以公开讨论的东西，那么你是在正确的序列上进行训练的。所以它是否正确可能就是一比特信息。所以我想，你知道，你可以理解这种逻辑从何而来。我认为问题在于，这是否在做你无法通过其他方式做的事情？比如，也许你会想提供更多的监督，但你将如何做到这一点？我认为非常清楚的是，这种方法已经带来了一系列的突破，就模型能力爆炸性增长而言，无论是在编码还是在科学领域。我总的来说认为，这是关于让模型在**测试时思考**，利用**测试时计算**并进行**推理**。显然，强化学习过程的很多部分对于实现这一点至关重要。

<details>
<summary>Original English</summary>

**Dan Roberts**: if you look at like the deepsek algorithm which is a public thing that that we can talk about then the you train on on um sequences that that are correct. So whether it's correct or not is maybe one bit of information. So I I think there's you know you can see where that logic comes from. I think the question is like is this doing a kind of thing that you can't otherwise do? Like maybe you would want to give more supervision, but how how are you going to do that? I think I think it's very clear that that this method these methods have lead led to a bunch of of breakthroughs um in terms of like the explosion of what the models can do and and you know both in in coding and in science. I think broadly it's about getting models to think in in test time to use test time compute and and and and do reasoning. And there's clearly a lot of the pieces of what the RL process is that's essential to make that work.

</details>

**Matt Turk**: 你对我们目前这种系统模型能走多远有什么整体看法？我们有**预训练**，然后在其之上是**强化学习**。去年，在**Dwarkesh播客**上，**Rich Sutton**有一个著名的对话，他声称——我尽力概括——**LLM**并非真正的智能，因此强化学习是唯一的方法，而且是纯粹的强化学习，而不是**LLM+RL**。你对此有何看法？我的意思是，你显然是在一家公司的一个强化学习团队，这家公司同时进行预训练和强化学习。那么你的看法是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: What's your overall feeling in terms of um how far we can go uh with that current sort of systems model where we have pre-training and then we have um RL on on on top somewhat famously last year there was a conversation with Rich Sutton on the Dwarkish podcast where his uh claim in my best attempt to paraphrase it was that LMS were not really intelligence and uh therefore for uh RL was the only way to do it and R pure RL not LM plus RLS. What is your take on this? I mean obviously you're in on an RL team at a company that does uh you know both pre-training and RL combined. So what's your what's your take?

</details>

**Dan Roberts**: 我再讲一个故事。在我读博士之前，我在**英国**待了两年，其中一年在**牛津**。当时我在一家酒吧，就像人们常做的那样，我的两个好朋友，一个是**认知科学家**，一个是**语言学家**。所以我们像那个年纪的人在这种情况下会争论的那样。有人说物理学是所有科学中最基础的，因为它解释了世界如何运作，而万物都在世界之中。我之前说过，我的计算机存在于世界中。我存在于世界中。我们都遵循物理定律。然后认知科学家说：“是的，但你必须处理它。所以有很多认知偏差，以及你收集数据和学习的方式等等。”

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: Let me tell another story. So when I when I was uh before I did my PhD, I spent two years in the UK and I was at Oxford for one of those years and I was at a pub as one does and you two of my close friends, one was a cognitive scientist and one was a linguist. And so we had the sort of argument that you do in those situations when you're that age. And so something like physics is the most fundamental of all the sciences because it explains how the world works and everything is in the world. I said this earlier, my computer exists in the world. I exist in the world. We all follow the laws of physics. And then the cognitive scientist said something like, "Yes, but then you have to, you know, you have to process it. So there's all sorts of cognitive biases about that and and and you know, the way you collect data and learn something something."

</details>

**Dan Roberts**: 但那位**语言学家**则说“blah blah blah **维特根斯坦**，你知道，一切都通过语言。那是交流的方式。那是，你知道，词语意味着什么的核心所在。”当我们想谈论**物理定律**时，我们必须使用语言。我感觉他和维特根斯坦都是对的，对吧？这就是AI所暗示的正确路径。我现在向**Kyle**让步，如果他正在听，他现在是一位语言学教授。**强化学习**这个在上一个十年引发了对AI兴趣的整个想法，我认为所需的**基础**就是通过**语言**来实现的，因为一切都通过语言。所有的互联网，它融入了真实世界的基础，我们所有的科学知识，我们所有的数学知识，所有的人类，你知道，基本上所有人类工作的总和都以语言的形式呈现在互联网上。所以，让模型拥有语言的先验知识，并能够用语言思考，然后在之上进行训练。这显然是正确的做法，而且，你知道，即使在这一切之前，也可能有人会认为这是有道理的。这对于一个智能来说，是一个令人惊叹的先验知识，因为它非常基于我们和我们的社会。

<details>
<summary>Original English</summary>

**Dan Roberts**: But then the linguist was was like blah blah blah Victenstein, you know, the everything goes through language. That's the method of communication. That's, you know, that's the way words mean things are are um the central thing. And and when we want to talk about the laws of physics, we have to use language. And I sort of feel like he and Victor like that that was correct, right? That's what's what or at least the path through AI suggests that that is a correct path. I'm I'm conceding now to Kyle and u if he's if he's listening, he's now a linguistics professor. This whole idea of reinforcement learning that kicked off the previous decade's interested in AI. the the sort of uh grounding I think that was needed was was to to make things really work is through is through language because everything goes through language right all the internet right it's like it it incorporates the grounding of the real real world all of our scientific knowledge all of our mathematical knowledge all all of the human like you know the sum total basically of of human work is represented on the internet in language and then so having the model have a prior of language and being being able to like think in think in language and then train on top of that. That seems like clearly the right the right thing to do and and like you know seems also well well grounded in a way that even before all this somebody might have argued would would make sense. It's like an amazing prior to have um to to start with for for an intelligence because it's like very much based on us and our society.

</details>

**Dan Roberts**: 我和**Rich Sutton**还有其他一些分歧，但如果你想深究。

<details>
<summary>Original English</summary>

**Dan Roberts**: I have other disagreements with with uh Rich Sutton but if you want want to poke at that.

</details>

### 规模、好想法与预训练+RL的协同

**Matt Turk**: 是的。那么就给我们一两个快速的例子吧。

<details>
<summary>Original English</summary>

**Matt Turk**: Yes. So just give us one one or two quick ones.

</details>

**Dan Roberts**: 我有一个有点**反主流**的看法，那就是，更好的教训是，**规模**并不是你所需要的一切。你还需要有**好想法**来指导扩展。所以，这不仅仅是扩大规模，其中有更深层次的相互作用。例如，如果你只是尝试扩展**预训练**，你不会像现在这样，在预训练之上也尝试扩展**强化学习**那样走得那么远。我们的模型之所以强大得多，就是因为这个非常好的想法，以及对这个好想法的投入。

<details>
<summary>Original English</summary>

**Dan Roberts**: I have a somewhat contrarian take that that um with the better lesson that it's not that scale is all you need. You need to also have have good ideas to to guide the scaling. So there's there's like a deeper interplay than just scale things up. For for instance, if you were just trying to scale pre-training, you wouldn't get anywhere near as far as also trying to scale RL on top of pre-training, which is what we do now. And our models are much more powerful for like that very good idea and investing in that good idea.

</details>

**Matt Turk**: 那么，这些**好想法**来自人类。嗯，也许未来它们会来自AI，但在我们拥有AI之前，它们来自人类。我的意思是，**规模化**也是一个来自人类的好想法。但是，存在着这样一种相互作用：在规模上引发**新现象**。你尝试在那个规模上理解它们，然后这会指向新的方向，然后你开发新的想法，然后你尝试在这些想法上应用规模。所以，我认为这不仅仅是**规模、规模、规模**。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Matt Turk**: And that the good ideas come from humans. Well, maybe they'll come from AI in the future, but before we had AI, they they came from humans. I mean, scaling was also a good idea that came from from humans. But but there's like this this interplay of elicit new phenomena at scale. You try to understand them at that scale and then that points you at new directions and then you develop new ideas and then you try to apply scale and those ideas. Um so I think it's not just scale scale scale.

</details>

### 测试时计算与思维链

**Matt Turk**: 既然你提到了**测试时计算**，我想有一个问题仍然困扰着人们，那就是**思维链**这种东西，从用户角度来看它是如此神奇。无论你看到什么，在测试时计算过程中实际发生了什么，创造了这些**工件**。一个模型到底做了什么？

<details>
<summary>Original English</summary>

**Matt Turk**: Since you mentioned test time compute, I think there's um something that that still puzzles people which is the the whole chain of thought thing which is so magical from a user perspective whatever you can see what actually happens during test time compute uh that creates uh those um artifacts. What does a model actually do?

</details>

**Dan Roberts**: 我认为它做了你所看到的。嗯，我们只是稍微重写或总结它。嗯，但它只是生成**token**，这些token就像一个正在运行的**思维过程**，就像你可能会有的，或者更像是如果你正在解决一个数学问题，你的草稿本，你收集的笔记，但它只是不断生成。生成的好处在于，你知道，它是一个模型**正向传播**。所以我们正在使用大量的计算。所以我们正在，你知道，这是一种利用比以前更多的计算来解决问题的方法。

<details>
<summary>Original English</summary>

**Dan Roberts**: I I think it does what what you see it do. um we lightly rewrite it or summarize it. Um but it it just it just produces tokens and those tokens are like a running thought process just like you might have or or maybe it's more akin to if you're solving a math problem the the scratch pad the collection of notes that that that you have but it it just keeps generating. The cool thing about generating is that you know it it it's a a forward pass the model. So we're using a bunch of computation. So we're we're you know it's a way of leveraging a lot more computation on a problem than than you would before.

</details>

**Dan Roberts**: 所以我的同事**Noam Brown**经常谈论**黎曼假设**，你知道，你难道不想有一个能够运行多年、能够解决这个问题、证明它的模型吗？如果你呈现它，并且你希望它产生一个答案，那么如果它被迫立即回答，它只有在一次**前向传播**中产生一个**token**的**浮点运算**数量。但如果它可以在长时间思考之后回答，它就可以重用其**权重**，产生一个最终答案，这个答案是大量计算的函数，而且它思考的自然方式是**语言**，它是一个**语言模型**，所以这就是一个关键的洞察，你可以通过在**token空间**，也就是语言中产生一个**思维过程**来让它做得更好。

<details>
<summary>Original English</summary>

**Dan Roberts**: So my colleague Nome Brown likes to talk about the remon hypothesis a lot and you know wouldn't you want to have a model that runs for years that that that can um resolve resolve that prove that if you present it and you wanted to produce an answer then it only has the number of flops in a in a single forward pass to produce one one token if it's forced to answer right away. But if it gets to answer after think you know after a long time it can it can re reuse its weights you know produce um a final answer that is a function of a m much much larger amount of computation and the like the natural way it thinks is in language it's a language model and so that's sort of this key insight that that you can um cause it to do better just by producing a thought process in in in token space in in language.

</details>

**Dan Roberts**: 而这在**强化学习**之前就已知。如果模型被告知要思考问题，或者你给模型思考过程的例子，它会在给出最终答案之前这样做。或者如果你只是告诉它那样做，它就会做这种事情，对吧？回到我之前给出的**SFT**与**监督学习**与**强化学习**的类比，互联网上有很多人们长时间思考的例子。所以，它并非完全无用。它可以在一定程度上利用这些信息，但强化学习真正地将这一点发挥出来。

<details>
<summary>Original English</summary>

**Dan Roberts**: and this was known before RL the idea that if you asked the model, if you gave a model examples of of thinking things out, it would do this before it produced a final answer. Or if you just told it that, then it would then it would do this sort of thing, right? Going back to this SFT versus supervised learning versus reinforcement learning analogy that I gave earlier, like there's a lot of examples on the internet of people thinking for a long time. And so like it's not completely useless. It can channel that a bit, but RL really like brings that that out.

</details>

**Matt Turk**: 那么在**测试时计算**过程中发生了什么，它与**强化学习**有关联或由其产生吗？因为这实际上就是你之前在定义强化学习时所描述的：模型朝着一个方向前进，可能觉得那不是一个有成效的方向，然后回溯，尝试别的东西。这是否正确？

<details>
<summary>Original English</summary>

**Matt Turk**: What happens during testm compute is is RL related or created because that that's effectively what you described earlier when you were defining RL the model goes in one direction decides maybe that's not a fruitful one backtracks tries something else is that correct or not

</details>

**Dan Roberts**: 我认为**强化学习**过程的结果是模型可以在**测试时进行思考**，这就是为什么我们有这些拨盘，或者说不同的公司都有**推理**方面的努力拨盘。所以，你现在创建了一个模型，它会在输出最终答案之前产生大量的**token**，而让它变好正是强化学习正在做的事情，或者说是强化学习正在做的事情之一。所以，进行强化学习训练的产出就是拥有一个能够思考的模型。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: I think maybe the result of the RL process is that the model can then think at test time and that's why we have these dials or various companies have labs have reasoning effort dials. Um, right. So, so you now created a model that will produce a bunch of tokens before it outputs a final answer and like causing that to be good is what RL is doing or one of the things RL is doing. And so the output of of doing RL training is the ability to have a model that thinks.

</details>

### 可验证奖励与RL的未来

**Matt Turk**: 该领域的一个关键问题是，我们能否扩展和推广**LLM系统**在编码和现在的数学方面取得的成功，这些领域你可以验证模型得出的结果是否正确。你对此有何看法？也许可以从解释什么是**可验证奖励**开始。

<details>
<summary>Original English</summary>

**Matt Turk**: So one of the key questions in the field is whether you can expand and generalize the success uh that LLM systems have had in particularly in coding and now math uh but like domains where you can sort of verify uh whether uh what the model comes up with is is correct or not. What is your view on on that and and perhaps start by explaining what a ver verifiable reward is?

</details>

**Dan Roberts**: **可验证奖励**原则上是**无法被欺骗**的奖励。如果是一个**数学问题**，答案是一个整数，你只需**字符串匹配**这个整数，然后你就验证了它正确解决了问题。这个抽象存在各种问题。但是，一个**无法验证**的问题，例如“这是一篇好的**创意写作**吗？”，那里没有你可以进行字符串匹配的东西，对吧？这涉及到品味问题，也许不同的人有不同的看法。所以它可能是一种**分布**式的东西。所以这两者之间显然存在很大的差距。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: So a verifiable reward is is is in principle a reward that that that can't be hacked. Uh so it's a if the if it's a math problem and the answer is an integer, you just string match the integer and and then you verified that it that it did it solved the problem correctly. Um that that abstraction has all sorts of problems with it. But uh unverifi a problem with an that can't be verified is is this a good piece of creative writing that that that's there's not uh something you can sort of string match against, right? That involves questions of taste and maybe different people ask differently. So maybe it's a distributional kind of thing. And so there's there's clearly a big gap between those those two things.

</details>

**Matt Turk**: 那么你认为**强化学习**能否真正在没有**可验证奖励**的领域发挥作用呢？比如咨询、银行、法律。我的意思是，在这些领域显然已经取得了巨大的进展，但具体发生了什么？

<details>
<summary>Original English</summary>

**Matt Turk**: So do you think there is a path for RL to be truly effective at domains without referral rewards? So uh you know consulting, banking, uh legal I mean clearly there's tremendous progress in those domains but like what what is happening?

</details>

**Dan Roberts**: 我绝对相信**OpenAI**将拥有惊人的产品，它们将在这些领域发挥作用，并且一定程度的**强化学习**将在其中扮演角色。

<details>
<summary>Original English</summary>

**Dan Roberts**: I definitely think OpenAI will have amazing products that will um be relevant in those domains and some amount of RL will play a role in there.

</details>

### RL的泛化能力与物理学视角

**Matt Turk**: **强化学习**是否具有**泛化能力**？也就是说，当你针对越来越多的领域训练它时，它在学习下一个领域时是否会表现出**不成比例**的优势？我的意思是，我们希望构建一个**通用智能模型**，并尽可能地推进这种智能，为此我们希望将一切都纳入**分布**中，然后我们也希望它在遇到不在分布中的事物时具有**鲁棒性**。如果强化学习是这个过程的一部分，那么，你知道，就像我之前试图说的那样，存在一种模糊的感觉，即有很多非常模糊的东西，但，你知道，AI中的**泛化问题**显然是一个重要的核心问题，而且有很多例子我认为支持这种观点，即这些过程可以做到这一点。

<details>
<summary>Original English</summary>

**Matt Turk**: Does RL generalize uh meaning that as you train it against more and more domains it becomes disproportionately good at learning the next domain? I mean we want to make a model that is generally intelligent and push that intelligence as far as possible and to do that we want to make everything part of the distribution and then we also want to make it robust in cases where it encounters things that it was not in the distribution and if RL is part of that process then you know like but like I think there's a vague sense as I was trying to say earlier is that there's a lot of things that are very fuzzy but the you know clearly the question of generalization in AI is is is a important central one and there's a bunch of examples I think that support that the processes can do this.

</details>

**Matt Turk**: 回到你的**物理学**根源，我们刚才描述的关于**预训练**和**强化学习**之间的相互作用，以及所有我们描述过的各种细枝末节，它们显然是非常复杂的系统。你所受的训练是一门完全关于研究复杂系统的学科。物理学能教给我们什么，关于如何理解我们正在构建的这些**AI系统**？

<details>
<summary>Original English</summary>

**Matt Turk**: So going back to your physics roots, a lot of what we just described about this interplay between pre-training and RL and uh you know all the various bits that we described, those are clearly pretty complex systems. Uh and uh you uh were trained in a discipline that is all about studying complex systems. What can physics uh teach us about how to understand uh those uh those uh AI systems that we're currently building?

</details>

**Dan Roberts**: 我认为回答这个问题有很多角度。我认为也许最有趣或最相关的一个，与我们目前的工作方式以及这可能是一个**反主流**的观点有关，那就是思考**扩展**和**扩展定律**的方式，不是从小到大，而是**从大到小**。稍后我将解释为什么物理学对这一点很重要。当你有一个非常庞大的**AI系统**存在时，会发生一些奇怪的事情，这些事情在小规模下并未发生，所以我们说“哦，这在规模上出现了什么”，有时人们会用**“顿悟”（grocking）**这个词，或者说**扩展序列**存在某种**不连续性**，所以它看起来，或者说**扩展定律**被打破了，这些都是人们可能会说的话。但我认为我完全反对这一点。我认为这意味着你对你正在扩展的东西没有理解透彻。

<details>
<summary>Original English</summary>

**Dan Roberts**: I think there's a lot of lot of angles to answering that question. I think the maybe most interesting one or the most relevant one to how we work currently and maybe this is a contrarian take is that the way to think about scaling and and say scaling laws is not small to big but big to small. So and and I'll get to why physics really matters for this in a second. when when you have you know you have the existence of some really big AI system and some weird things happen and they didn't happen at the small scale and so we say like oh this whatever emerged at scale right there sometimes people use the word grocking or there's something discontinuous about the scaling sequence and so it see or the scaling law is broken these are things that people might say but I think I reject that entirely I think you it means that you didn't understand something about what you were scaling up.

</details>

**Dan Roberts**: 也许回到**推理**这个话题，我不知道这是否属实。这是一个卡通化的说法。我当时不在OpenAI，但如果你想象尝试让小型模型进行推理，比如**GPT-1**、**GPT-2**、**GPT-3**，然后是**GPT-4**——这同样是卡通化的说法。你可能会说：“哦，这在规模上出现了，而在小型模型中没有发生。”我拒绝这种说法。相反，我们发现了一些真正令人兴奋的现象，比如**推理**，或者，你知道，也许是一些不好的事情。你的模型崩溃了，而你之前的模型没有崩溃，你的任务就是找出如何恢复**扩展序列的平滑性**。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: Maybe even going back to the reasoning thing, like I don't know if this is true. This is a cartoon. I wasn't at opening a at the time, but if you imagine trying to like get small models to to reason, you know, GPD 1, GPD2, GPD3, and then GPD4 to again cartoon. Um, you might say like, oh, this emerged at scale, and it doesn't happen for the small models. Uh, you you know that I I I reject that. Instead, there's some phenomena that's really exciting that we discovered like reasoning or, you know, maybe something bad. um you know like your model blew up and your earlier models didn't blow up and your job is to then figure out how to restore smoothness to the scaling sequence.

</details>

**Dan Roberts**: 回去制作更小、更简单的模型，或者更简单的**玩具示例**，使得整个过程是平滑的。如果你能做到这一点，如果你能弄清楚在小事物中放入什么，那么你就能理解这个事物，然后你就可以继续前进。这正是我们在**理论物理学**中所做的。有**标准模型**，你知道，我有一本教科书在我身后，它描述了除了**引力**之外的所有力，即使是紧凑的符号也会占据整整一页。它非常庞大，有很多不同的粒子，谁知道呢，其中一些有其原因，但它们在做各种不同的事情，不同的事情相互抵消，或者，你知道，这恰好是我们所居住的宇宙。但你不需要所有这些来研究其中的一部分，比如研究**电磁学**，你可以忘记其他一切。或者如果你想研究**希格斯现象**，你知道，它赋予一些粒子质量，你可以研究它的简化版本。

<details>
<summary>Original English</summary>

**Dan Roberts**: Go back and make smaller and simpler models or or simpler toy examples such that the um the whole thing is smooth. And if you can do that, if you can figure out what to put into the small thing, then then you understand the thing um and and then and then you can you can move forward. This is exactly what we do in theoretical physics. There's the standard model which is you know I I have it a textbook behind me it the description of all the forces except gravity would take even in compact notation like the entire entire page it's it's like completely gross there's you know a lot of different particles why you know I who knows some of them there's reasons for but they're doing all sorts of different things different things cancel whatever or you know this just happens to be the universe that we live in but you don't need all of that to to like study pieces of it to study electromagnetism, you forget about everything else. Or if you want to study the Higs phenomena, you know, which gives mass to some particles, you you can study a simplified version of that.

</details>

**Dan Roberts**: 嗯，所以我想我们所做的，至少在我所受的物理学训练中，一个关键的举动就是处理真正复杂的系统。这通常被称为物理学家只研究**球形奶牛**。我认为这有点误解了重点，比如如果你研究的**球形奶牛**足以描述你关心的事情，那么你做得很好；如果不是，那你做得不好。你不要试图退回到一个足够简单以至于你可以进行计算的场景。你尝试退回到一个足够简单但包含你所关心事物的场景，然后你不知道你是否能在那里取得进展。但一旦你做到了，你就理解了问题是什么，而这就是物理学中的大部分工作，在AI中也是如此。你拥有这些疯狂的庞大系统，它们具有各种有趣的现象，而且，你知道，如果你以正确的方式思考它，它们并不会突然**顿悟**，只是存在这种很好的**连续性**。

<details>
<summary>Original English</summary>

**Dan Roberts**: Um, and and and so what we do in I think one of the key moves in at least in my training in physics is to take really complicated systems. This often gets talked about as physicists just study spherical cows. And and I think that that that like kind of misses the the point like you you study if if the spherical cow is sufficient to describe the thing that you care about then you did a good job and if not you did a bad job. You don't try to retreat to a setting that's simple enough where you can make pro where you can like calculate something. You try to retreat to the setting that's simple enough that contains the thing that you care about and then you you have no idea whether you can make progress there or not. But once you did you sort of understand what the problem is and you and and that's that's like uh a lot of the work in physics and I and the same thing is true in AI. You have these crazy huge systems that have all sorts of interesting phenomena and and you know if you think about it the right way they don't grock there's just this nice continuity.

</details>

### AI中的热力学与预测

**Matt Turk**: 你认为AI中会有类似于**热力学**的等价物吗？也就是说，一个紧凑的理论，可以在不追踪每个单独比特的情况下预测行为。

<details>
<summary>Original English</summary>

**Matt Turk**: Do you think there could be an equivalent in AI to thermodynamics meaning uh you know a compact theory that uh predicts behavior without tracking every individual bit.

</details>

**Dan Roberts**: 是的。**Kaplan MechanDalish**的**扩展OpenAI**，嗯，**扩展定律**最初的工作就是这个版本，你抛弃了所有关于网络的信息，你只知道它有多少参数以及你训练了多少数据，然后你就可以预测最终的损失。我认为缺失的部分是从所有单个**权重和偏差**到**扩展定律**的累加。我有一些非常初步的工作，也有一些其他的初步工作，试图弥合这种联系。但我认为那就是缺失的部分，就像**统计力学**到**热力学**的过程，我们如何让这些东西出现。但肯定有很多有用的**有效描述**来解释这些系统的行为。我认为你问题的另一部分是，这是否足以描述我们所关心的一切？我们可能除了最终的损失函数之外，还关心很多其他事情，所以除了如何从微观描述中产生热力学之外，还需要解决更多的**热力学问题**。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: Yeah. Kaplan mechandalish scaling openAI uh scaling laws work originally is is a version of this where you throw away you know all you know about the network is how many parameters it is and how how much you've how much data you've trained on it and you you can predict like the the final loss. I think the the missing piece is going from all the individual weights and biases and and how does that add up to the scaling law. I have some very like initial work and there's some other initial work about like trying to bridge that connection. But like I think that's that's the missing piece like the sort of statistical mechanics to thermodynamics of how do we like how do these things emerge but there's definitely a lot of useful effective descriptions of how these systems behave. I think the other part to your question is like is it is enough to characterize everything that we care about right there's probably a lot there's a lot that we care about other than just the final loss function and so there's there's more thermodynamics to be worked out in addition to like how does the thermodynamics arise from the microscopic description

</details>

**Matt Turk**: 所以一年前在那次会议上，你开玩笑地预测，再过9年就能达到**爱因斯坦级别**的AI。抛开玩笑，你认为我们现在在**AI创造科学发现**这个领域处于什么位置？我的意思是，这是我们开始对话的地方，我很想知道这会走向何方。

<details>
<summary>Original English</summary>

**Matt Turk**: so at that conference a year ago you you jokingly uh predicted 9 years to Einstein level AI where do you think all jokes aside we are on that on that spectrum of uh just um AI uh uh creating scientific discovery. I mean that's where we started the conversation and curious about where this is going.

</details>

**Dan Roberts**: 这个玩笑，也许**解构**一个玩笑总是有帮助的。但这个玩笑是说，根据系统可以自主完成的工作量翻倍的时间，计算出我们需要多长时间才能达到一个可以自主思考八年的系统，因为**爱因斯坦**花了八年时间发现了**广义相对论**。我把它推算出来，大概是去年算起九年。所以，嗯，我讨厌做预测，但我很确定在那之前会有一些突破。我的意思是，总的来说，我们不会只是建立一个系统，让它自主思考八年，因为八年后的系统会强大得多，所以让一个系统思考一定时间可能没有意义。你知道，系统改进所需的时间和它思考的时间是不同的，当这些交叉时，所有这些**扩展壁垒**都会以某种方式被打破。

<details>
<summary>Original English</summary>

**Dan Roberts**: The joke maybe it's helpful to deconstruct a joke as as as it always is. But the the joke was that taking the doubling time for uh the amount of work a system can do autonomously and figuring out how long it would take us to get to a system that can think eight years on its own because Einstein spent eight years discovering general relativity. and I projected that out and it was like nine years from last year. So, um that that like something I I hate making predictions, but I'm pretty sure something will break before that. I I mean, in in general, we're not just going to like set up a system and let it think autonomously for 8 years, if anything, because like the systems 8 years after will be so much more powerful that it probably doesn't make sense to let a system think for a certain amount. you know, there's there's amount of time it takes for the system to improve and then there's the amount of time in it thinking and like probably when those cross like all these scaling walls are going to to break in in in certain ways.

</details>

**Dan Roberts**: 我确实认为我一直在努力谈论的，即我们物理学家如何处理问题的那种思考方式和风格，可能与“这是一个定义明确的东西，去进行计算”不同，而这正是**Erdos问题**的特点。我认为我们可能需要一些想法来弥合两者之间的差距。我不认为它必然会是一个**不连续**的事物，或者是一个**平滑**的事物，但你知道，我认为科学过程的一部分，模型尚未被赋予，我相信人们正在思考如何做到这一点。你知道，就像试图弄清楚什么是**正确的问题**，而不是“这是一个定义明确的东西，去计算吧”，其中一些涉及到**研究品味**，这不是一个容易验证的事情。

<details>
<summary>Original English</summary>

**Dan Roberts**: I do think that the kind of thing that that I was trying to talk about about like how we as physicists approach problems that the structure and flavor of that is maybe different than here's like a very well- definfined thing and go and do a calculation which is like what these Erdos problems are. I think probably we'll need to have some ideas to bridge from from one to the other. I don't think it's it's not obvious whether there has to be a discontinuous thing or or or a smoothing thing, but you know there's part of the scientific process I think that the models haven't been imbued with yet and I'm sure people are thinking about how to how to how to do that. You know like what trying to get to what is the right question as opposed to here's a well- definfined thing and and and go calculate and and some of that involves research taste that's not an easy easily verifiable thing.

</details>

### AI自主科学研究的未来

**Matt Turk**: 那就是什么会让你相信**AI**正在进行真正原创的科学研究？

<details>
<summary>Original English</summary>

**Matt Turk**: Is that what would convince you that AI is doing genuine original science?

</details>

**Dan Roberts**: 不，我确信，而且我认为我们会，我认为**单位距离问题**就是一个很好的例子，而且能够采取**反主流**的立场，长时间地思考，探索许多不同的选项，并利用不同领域的全部力量，比如在某些情况下，你不太可能找到一个拥有解决这些问题所需精确技能组合的人类，对吧？这是一个巨大的，这是一个巨大的事情。

<details>
<summary>Original English</summary>

**Dan Roberts**: No, I'm convinced and I think we're going to like I like like this is clearly I think the the unit distance problem is a is a is a great example and and like the also just being able to take a position that is contrary and think for an extremely long amount of time explore lots of different options and bring to bear the full weight of disparate fields like where something you know it's very unlikely to find a human that has the exact set of skills to solve some of these problems right that's a huge that's a huge thing

</details>

**Matt Turk**: 你认为我们离**AI研究**真正实现**自动化**还有多远？不是AI研究人员使用AI，而是AI自主构建AI？

<details>
<summary>Original English</summary>

**Matt Turk**: how far do Do you think we are from AI research uh actually automating itself uh not not just AI researchers using AI but like AI autonomously building AI?

</details>

**Dan Roberts**: 是的，我认为这又是一个**平滑**的过程，就像它现在已经做到了其中的一部分。未来它会做得更多。我知道有人喜欢思考这种**强版本**，但你知道，我不确定我们是否会看到一个真正的**剧烈相变**，而不是越来越多的部分，你知道，现在很多需要人们数周才能完成的编码工作，模型可以非常高效地完成。所以，就像这些**数学发现问题**一样，也有一些版本是模型在工程领域扮演着更核心的角色。所以我想这只会越来越多。我认为存在一种**科学思维**，人类似乎仍然非常擅长，而且，你知道，我不想对何时或如何做出具体预测。

<details>
<summary>Original English</summary>

**Dan Roberts**: Yeah, I think it's again one of these smooth things where where like it's already doing pieces of it it now. It'll do more in the future. And there's I know there's strong versions of this that that that that people like to think about, but you know, I I'm not sure that we'll see like a a really sharp phase transition versus just more and more pieces of you know, right now a lot of coding that would take people weeks can be done very efficiently with models. So like some of these math discovery problems, there's also versions of this where for engineering the the model the models are playing a more central role. And so I think that will just there will just be more of that. I think that there's a kind of scientific thinking that that humans still seem to be very useful for doing and you know I don't want to make specific predictions about when or how.

</details>

**Dan Roberts**: 我可以想象，你不想被记录下来说模型在某个方面不好，因为你肯定会错，或者也许我应该那样说，然后模型就会立即擅长那个方面，所以我应该选择我希望模型去做的事情，然后说它们永远不会做。我认为也很难做出预测，因为我认为人们以前做出预测的方式，实际情况往往并非如此。所以，你知道，这又是另一种**归因问题**，如果你有很长一串需要发生的事情，才能发生某事，那么任何打破这个链条的事情都意味着你的预测完全错误。

<details>
<summary>Advisory:**  Some repetition of "Um" and "And" have been removed for improved readability in the Chinese translation. This is a common practice in transcription to improve flow without altering meaning.  The original English includes these as natural speech patterns.
</details>
<summary>Original English</summary>

**Dan Roberts**: Um I can imagine like it's you don't want to be caught on record saying the models won't be good at something because you'll you'll definitely be wrong or maybe I I should say that and then the models will be good at that immediately and so I should pick the things that I want the models to do and say that they'll never do that. I think it's also just hard to make predictions because I think the way in which people made predictions before like the the actual ways things shook out often are are not um in that direction. And so, you know, it's it's another sort of credit assignment thing like if you have this long chain of things that has to happen for whatever to happen, then anything that breaks that chain means your prediction like is just is just way off.

</details>

**Dan Roberts**: 但是，你知道，在接下来的六个月里，我可以做出一个非常长远的预测，我认为我们会看到更多的这种**数学和科学突破**，而且显然我们会将这种东西应用于**AI本身**，模型将变得更加强大，那将非常有趣。你可以想象，你可以做**AI科学**，并感觉就像在做**物理学**一样，这是真的。另一个真正令人兴奋的事情是，我进入物理学领域时，以为我会，你知道，当你第一次学习一个领域，也许你想投身其中，至少我当时的看法是，哦，等我学完了，我就会知道所有的答案，对吧？所有基本问题，显然，这只是一个旅程，在旅程的尽头，它会得到解决。然后我不知道，也许是在研究生院，或者也许是我转向AI的时候，我意识到，哦，其中一些问题会一直开放，也许永远不会有答案，也许我永远也学不到答案。你知道，看着年长的同事退休，意识到他们可能也学不到答案。但我感到非常兴奋的是，你知道，我们真的能够回答科学领域中我们关心的许多基本问题，在**模型**的帮助下，或者说模型是驱动力，所以这确实非常令人激动。

<details>
<summary>Original English</summary>

**Dan Roberts**: And so but in the you know in the I can make a very long distance prediction you know for the next 6 months like I think we'll see more of of these sorts of math and science breakthroughs and and obviously we'll turn this sort of thing on on AI itself and the models will get a lot more powerful and that'll that'll be fun. You could think about you know that you could do science of AI and have it feel like doing doing physics and and and that's true. Another really exciting thing is that like I entered physics thinking that I would you know when you you first start learning a field and and maybe you want to commit to it at least the perspective I had is that oh by the time I get to the end I'll know all the answers right all the all the fundamental questions obviously like this is a journey and at the end of the journey it'll resolve and then I don't know maybe it was in grad school or maybe when I switched to AI I realized oh like some of these questions will stay open maybe forever maybe I'll never get to learn the answers you know watching older colleagues as well start to retire and and realize that they might not get to learn the answers. But I I feel really excited that that you know we will get to really answer a lot of fundamental questions in in the fields of science that that we care about um with with the aid or maybe the the models being the driving force and so that yeah that that's just really thrilling.

</details>

**Matt Turk**: 好的，这感觉是一个绝佳的结束点。Dan，你给了我们很多值得深思的东西。非常感谢你今天抽出时间。谢谢你。

<details>
<summary>Original English</summary>

**Matt Turk**: Well, that feels like a wonderful place to leave it. Dan, you gave us plenty to ponder. really appreciate you spending time with us today. Thank you.

</details>

**Dan Roberts**: 谢谢你的邀请。很高兴。

<details>
<summary>Original English</summary>

**Dan Roberts**: Thanks for inviting me. It was a pleasure.

</details>

**Matt Turk**: 大家好，我是**Matt Turk**。感谢收听这期Matt播客。如果你喜欢这期节目，如果你还没有订阅，或者在您观看或收听这期节目的任何平台上留下积极评论或反馈，我们将非常感激。这真的有助于我们建设播客并邀请到优秀的嘉宾。谢谢，我们下期节目再见。

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the Mad Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already, or leaving a positive review or comment on whichever platform you're watching this or listening to this episode from. This really helps us build a podcast and get great guests. Thanks, and see you at the next episode.

</details>