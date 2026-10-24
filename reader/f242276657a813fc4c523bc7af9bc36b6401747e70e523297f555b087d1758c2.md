---
author: 硅谷101
date: '2026-08-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=J5_90lWxM_o
speaker: 硅谷101
tags:
  - ai-interpretability
  - sparse-autoencoders
  - chain-of-thought
  - mechanistic-interpretability
  - model-alignment
title: 对话斯坦福博士Aryaman Arora：打开大模型黑箱，探索隐藏推理与可解释性
summary: 本期访谈对话斯坦福大学博士生Aryaman Arora，深入探讨AI可解释性（Interpretability）的前沿进展。内容涵盖雅可比空间（J-Space）的隐藏推理、思维链与真实思考的差异、稀疏自编码器（SAE）在特征干预中的应用、学术界与工业界的研究路径，以及可解释性在模型架构改进与安全监管中的关键作用。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Stanford University
  - Anthropic
  - OpenAI
  - Goodfire AI
products_models:
  - GPT-3
  - Claude
  - Mamba
media_books: []
status: evergreen
---
### 序言：AI的黑箱与隐藏推理

**Aryaman**: 我们不知道为什么这些东西能起作用。我把它归结为神圣的启示。说实话，我们居然要依赖那些拥有惊人直觉的人来推动这个领域的进步，这确实有点疯狂。

<details>
<summary>Original English</summary>

**Aryaman**: I don't know why these things work. I attribute it to divine providence. Kind of crazy that we have to rely on people who have amazing intuition to make progress in the field.

</details>

**陈茜**: 在模型内部，有一些它们没有说出口的隐藏推理步骤正在发生。如果你的语言模型足够好，它就能正确预测下一个词。为了做到这一点，它内部必须有一个关于人类如何互动的“世界模型”。但我们目前还不知道这个世界模型究竟是什么。

<details>
<summary>Original English</summary>

**Chen Qian**: There is internal steps of reasoning happening in models that they don't say. If you have a really good language model, it will be able to predict the next word correctly there. To do that, it must have like a world model inside of like how people interact. We don't know what that world model is yet.

</details>

**Aryaman**: 可解释性研究的目标就是弄清楚这个世界模型是什么。目前，我们的技术都不擅长控制模型的内部思想。如果你的模型在做坏事，没有人能直接去修改它的思想。

<details>
<summary>Original English</summary>

**Aryaman**: The goal of interpretability is like figure out what that is. None of our techniques are good at controlling the internal thoughts of a model. If your model is doing something bad, no one goes and edits the thoughts.

</details>

### 初识可解释性

**陈茜**: **Aryaman**，欢迎来到《**硅谷101**》。

<details>
<summary>Original English</summary>

**Chen Qian**: Aryaman, welcome to a Valley 101.

</details>

**Aryaman**: 谢谢邀请。

<details>
<summary>Original English</summary>

**Aryaman**: Thanks for having me.

</details>

**陈茜**: 谢谢你专程开车来到旧金山，很高兴我们终于有机会聊聊。**可解释性**是很多人一直建议我关注的领域，我也觉得它非常迷人。因为，谁会不想知道我们的“AI霸主”是不是在密谋除掉我们呢？不过，在开始之前，你能不能先向观众做个自我介绍？

<details>
<summary>Original English</summary>

**Chen Qian**: Yeah, thanks for driving up to San Francisco and really I'm really excited we finally got to chat. Interpretability is something that people have been telling me to look into for a while and I thought it was pretty fascinating as well because I mean why wouldn't we want to know whether our AI overlords are plotting to kill us. To get us started, why don't you just like give the viewers an introduction of yourself.

</details>

**Aryaman**: 好的。我是 Aryaman，目前是**斯坦福大学**的博士生，师从 **Chris Potts** 教授。我本科的背景是语言学，一直对语言非常着迷。后来这一波疯狂的 AI 浪潮爆发了，鉴于我比较偏向科学思维，我很想研究“这些模型为什么能工作”。所以，可解释性对我来说是一个非常自然的研究方向。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, so I'm Arian. I'm a PhD student at Stanford. I'm advised by Chris Potts. And yeah, I have a background in linguistics in undergrad. Always been fascinated in languages, and then all this crazy AI stuff happened. And you know, given that I'm pretty scientifically minded, I wanted to study like, you know, why do these things work. So interpretability was a natural direction for me to work in.

</details>

**陈茜**: 简单来说，可解释性就是试图理解模型内部发生了什么。但这是一个非常宽泛的问题，研究方向也很多。你个人对可解释性的定义是什么？你的研究重心又在哪里？

<details>
<summary>Original English</summary>

**Chen Qian**: Nice, yeah. So I guess to put it simply, interpretability is just we are trying to understand what's going on inside a model. But this is a pretty broad question, and I feel like there could be a lot of different directions this could take you. What is your definition of interpretability research and what do you focus on specifically?

</details>

**Aryaman**: 接近可解释性的角度确实有很多。最吸引我的视角是：大约五年前，我们在 AI 领域所做的事情其实并没有那么成功，尤其是在语言模型上。人们使用语言模型很久了，但大多只是用于语音转文字的后期编辑之类的任务。后来发生了一些变化，它们突然成了所有人都在研究的焦点，人们开始往里投入数十亿美元。所以对我而言，可解释性就是试图回答：究竟改变了什么？为什么以前行不通，而现在行得通了？

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, so I would say there's a lot of angles that you can take for approaching interpretability. The perspective that most interested me is like, okay, like five years ago even, all the things we were doing in AI were not really successful, like especially in language models. People were using language models for a long time, but it was sort of like post-editing speech transcripts, this kind of thing. And then something happened such that they became the thing that everyone's working on, they invest billions of dollars into them, and so on. So, for me, interpretability is like trying to answer the question of like what changed, like why were things not successful before and now they are.

</details>

### 解读 J 空间研究

**陈茜**: 促使我做这期访谈的契机之一，是 **Anthropic** 发布的一篇关于 **J-Space**（雅可比空间）的论文。我先在高层次上做一个简要概括，你可以帮我补充细节。大体上，研究人员使用了一种方法来窥探 AI 模型在思考（推理）过程中没有说出口的内部状态。他们引入了 J-Space 的概念。论文中有一个很有意思的例子：研究人员询问 AI 模型一个会结网的动物有几条腿，AI 回答“8条”。在这个过程中，“蜘蛛（spider）”这个词从未在输出中出现过。但当研究人员进入模型内部，将“蜘蛛”对应的激活方向修改为“蚂蚁（ant）”时，输出的答案变成了“6条”。这表明我们可以操纵 AI 模型的思考过程。你能带我们了解一下这篇论文，并解释为什么我们可以编辑一个模型从未说出口的词吗？

<details>
<summary>Original English</summary>

**Chen Qian**: One of the things that kind of motivated me to do this interview is Anthropic's release of this paper called J-space, or I guess a workspace for AI models. And I'm just going to summarize it on a pretty high level and you can kind of walk me through the details. But basically, it sounds like the researchers used a method to look into what's going on inside an AI model that it didn't say during the thinking process, and they introduced this concept of J-Space. One of the very fascinating examples that the researchers did in this paper is that they asked the AI model the number of legs of an animal that spins web, and the AI model answered eight, where the word spider did not appear anywhere. But then when the researchers went inside the model and changed spider to like ant, the answer changed to six. This is one of just a few examples of how it seems like we can manipulate how an AI model is thinking about things. So why don't you just walk us through this paper a little bit and kind of just tell us a little bit more about why we can edit a word that has never been said by an AI model.

</details>

**Aryaman**: 这确实是一篇非常迷人的论文。它为“模型内部存在未说出口的推理步骤”提供了越来越多的证据。我虽然没有读完那份一百多页的完整报告，但我理解其核心思想。这里的关键是一个被称为**雅可比矩阵（Jacobian）**的数学算子，它基本上源自微积分中的导数。在模型中，我们可以用它来查明在隐状态激活空间（因为一切都是向量）中，哪些方向会导致模型在未来输出某些特定的词。比如，在输出当前词的 10 个 token 之前，如果模型内部的隐表征指向了某个特定方向，它随后就会说出“蜘蛛”这个词。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, I thought that was a fascinating paper. And I think it adds to a growing body of evidence that like there is internal steps of reasoning happening in models that they don't say. I haven't read all like hundred and whatever pages of JSpace. But I sort of understand the idea. The broad idea is like we have this operator called the Jacobian, which you know is basically derivatives from calculus. We can use this in a model to tell us like what directions in its, you know, latent activation space, because you know everything's vectors. So it tells us what directions cause the model to say certain words in the future. So maybe like, you know, 10 tokens before, if the hidden representation inside the model is pointing some way, then it'll say the word spider later on.

</details>

**陈茜**: 是的。

<details>
<summary>Original English</summary>

**Chen Qian**: Yeah.

</details>

**Aryaman**: 这篇论文优雅且简单，在它之前似乎没有人以完全相同的方式尝试过。但我们已经有很多证据表明这些内部推理步骤是真实存在的。如果你看 Anthropic 早期关于电路（circuits）的研究，以及关于大语言模型内部机制的工作，就会发现当模型在进行某些计算时，它们内部是有特定通路在运行的。

<details>
<summary>Original English</summary>

**Aryaman**: And one nice thing about the paper is that this is like a very elegant and simple thing that somehow no one had really exactly tried before. But I think we have a lot of evidence that like, yeah, these internal reasoning steps are there. So even if you look at Anthropic's earlier work on circuits, they had this thing called the biology of large language models, and they showed like, oh, when a model is doing something...

</details>

### 隐藏推理与思维链

**陈茜**: 也就是说，有些概念在训练数据中并没有显式出现，但模型在上下文中自己推导出了它。

<details>
<summary>Original English</summary>

**Chen Qian**: Right? Like it's something that didn't really appear in the training data, but it kind of deduced it.

</details>

**Aryaman**: 是的。在特定的上下文中，如果有一个非常好的语言模型，它就能正确预测下一个词。而为了做到这一点，它必须在内部建立一个世界模型，模拟人们的互动方式以及相关事实的关联性。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah. In the context, if it's, you know, if you have a really good language model, it will be able to predict the next word correctly there. And to do that, it must have like a world model inside of like how people interact and like what the evidence was for, you know, all this.

</details>

**陈茜**: 那么我们现在是已经能够弄清楚这个世界模型是什么了吗？这是否就是我们目前正在努力解决的课题？

<details>
<summary>Original English</summary>

**Chen Qian**: Oh, is it like we don't know what that world model is yet? Is that something that we're trying to solve right now or?

</details>

**Aryaman**: 是的。我认为可解释性研究的目标就是：我们知道为了在预测下一个 token 的任务上表现优异，模型必须在内部开发一个极其复杂的、关于文本背后究竟在发生什么的隐式模型。而我们的目标就是去解构并找出那到底是什么。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah. So, I think the goal of interp is like okay, we know in order to do really well on next token prediction, you must develop a really complex internal model of like what's going on in a text. And like our goal is to like figure out what that is.

</details>

**陈茜**: 明白了。让我们稍微退一步来聊聊这种“隐藏推理”（internal reasoning）。它与我们熟知的“**思维链（Chain of Thought）**”形成了鲜明对比，后者是模型在“思考”时显式写出来的文字。为什么说仅仅依靠思维链并不能完全让我们理解模型的思考过程？

<details>
<summary>Original English</summary>

**Chen Qian**: Got it. Got it. Uh let's just take a little step back into this internal reasoning because it's it's kind of in direct contrast to what we now know as chain of thoughts, which is what the model spells out when it's syncing, if I can put it that way. And why is chain of thoughts not the best way to understand how like a model thinks?

</details>

**Aryaman**: 我不会做这么绝对的断言，思维链绝对是有用的。很明显，一两年半前那些没有使用思维链的模型，其表现明显比现在经过思维链训练的模型要差。因此，思维链一定在起作用，而且是非常关键的作用。

<details>
<summary>Original English</summary>

**Aryaman**: I don't know if I'd make that strong a claim. It's definitely useful. And so it's also super obvious that like models that didn't have chain of thought like a year and a half or two ago, they're like worse. They're like strictly worse than models that are trained with chain of thought now. Therefore, chain of thought must be doing something useful, like something very useful.

</details>

**陈茜**: 那正是我们转向“推理模型”的契机。

<details>
<summary>Original English</summary>

**Chen Qian**: That's like when we switched to reasoning.

</details>

**Aryaman**: 是的，当我们在模型给出答案之前，训练它们去“思考”。在科学研究中，我一直坚信“先做最简单的事情”。这是我在研究中学到的最重要一课：在诉诸复杂手段之前，先尝试简单的方法。因此，去检查思维链的内容相比于解决深度的可解释性问题，要简单得多，我们也理应这样做。在实践中，当 Anthropic、Meta 或 **OpenAI** 进行安全审计时，他们确实会检查模型的思维链是否包含了可疑（sus）的内容或异常的行为计划，这确实在一定程度上帮助他们捕获了对齐问题。所以，思维链绝对是值得分析的。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah. When we started training models to reason before they say their answer. Yeah. I'm a big fan of like you should do the simplest thing first. This is like everything I've learned in research. If I combine it together, the most important thing would be like just do simple things first before moving on to complex things. So, I think like checking the chain of thought is super simple compared to solving interp, we should do it. And in practice, like you know, when Anthropic or Meta or OpenAI, they run their safety audits, they do check if the model's chain of thought is like saying sus things or or like planning to do weird things. And it seems to help them catch misalignment to some extent. So yeah, I do think chain of thought is like useful to analyze.

</details>

### 可解释性的最终目标

**陈茜**: 在我们深入探讨更多工作细节之前，我想聊聊这里的终极目标。我们都很清楚为什么需要关注大语言模型的内部状态，但当我们真正理解了它的内部原理后，我们要做什么？它的应用前景是什么？我们不需要立刻谈论具体的商业落地，但在宏观上，它的目标是什么？为什么普通人（normies）也需要关心它？

<details>
<summary>Original English</summary>

**Chen Qian**: I guess before we get into more examples of how this works, I just wanted to talk a little bit about kind of the end goal here because I think it's pretty clear why we should all care about what's going on inside a language model. But I'm wondering what do we do after we understand what's going on inside it? Like what are the applications, or we don't have to get into specific applications now, but like what is the goal and why should, you know, us normies care?

</details>

**Aryaman**: 我认为解决可解释性问题将带来两大核心应用。首先是“信任”。要建立对一项技术的信任，了解它的工作原理至关重要。想想那些监管机构和政府，他们监管飞机制造、工业机械或石油开采。为了监管这些强大且有用的技术，我们必须理解它们的失效模式（failure modes），并明确责任划分。但现在，监管 AI 极其困难，因为我们根本不知道如何彻底阻止不良行为，甚至不知道某个坏结果为什么会发生，或者应该归咎于谁。我们面对的是海量的数据集和漫长的训练过程，很难厘清因果关系。因此，要提高社会对 AI 的信任，我们就必须理解其行为背后的原因，哪怕这种理解并不完美。比如，如果你的医生在使用一个 AI 系统，你和医生都会想知道它是如何得出诊断结论的。

<details>
<summary>Original English</summary>

**Aryaman**: I think so there's sort of two sort of applications that I feel like, you know, solving interpretability would lead to. So I think one of them is like trust. Like to have trust in technology it's important for us to know how it works. If you think about, I don't know, like there are regulatory bodies and governments that regulate like oh how you manufacture airplanes, how you do like industrial machinery, or like, you know, oil fracking and all these things. It seems like to regulate, you know, impressive technologies that can be useful, we do need to understand the failure modes and like, you know, figure out how to assign liability and all these things. Yeah, I think right now it's really hard to regulate AI stuff because we sort of don't know how to prevent bad behaviors or like even know why something bad happened or or like who to blame, like because no one really knows, you know, where some behaviors come from. Like we have this, you know, massive datasets, long training process. It's really hard to tell what caused something. So I think sort of for improving societal trust it would be useful if we like understood why behaviors are happening even if we don't have a perfect understanding. If your doctor is using an AI system or something like that, you as well as your doctor will probably want to know like why it's producing some output, right? So that's one side of things.

</details>

**陈茜**: 没错。

<details>
<summary>Original English</summary>

**Chen Qian**: Yeah.

</details>

**Aryaman**: 另一个维度是，目前的 AI 进展在很大程度上是非常经验主义的（empirical）。当然，在计算机科学领域这并不是坏事，毕竟运行实验比化学、生物或实体工业要容易得多。然而，目前的进步在很大程度上依赖于某些绝顶聪明、直觉敏锐的研究人员做出的尝试，他们自己也说不清为什么能成功，但就是行得通。比如著名的谷歌前研究员 **Noam Shazeer**（现代 Transformer 架构的奠基人之一）。他在一篇论文中引入了**门控线性单元（GLU）**，在论文末尾展示了出色的实验结果后，他写道：“我不知道为什么这些设计能起作用，我将其归结为神圣的启示（divine providence）。” 这种话出现在学术论文里真的很不可思议。他基本上是在说：“神赐予了我这个灵感去尝试这个实验，然后它就成了。”

<details>
<summary>Original English</summary>

**Aryaman**: The other side of things is like I do think a lot of AI progress, like research wise, has been extremely empirical. And this is not a bad thing, like of course in our field, it's so easy to run experiments compared to like chemistry or biology or, you know, real world things. It seems like as stuff has gotten better, it's because some people, or like some really smart people with great intuition have come up with things, and they don't know why those things work but they work. There's a famous like Google researcher Noam Shazeer. I guess he's not at Google anymore, but he he invented a lot of the architectural improvements that led to modern transformers and he's on the original transformers paper. He has a paper where he introduced gated linear units, which are just one more architectural thing. In the end of the paper he's like, so he shows all his experiments, he shows they're better, he's like, you know, I don't know why these things work, I attribute it to divine providence. It's like a crazy line to put in a paper. He's like, sure, like God gave me the vision of like trying this experiment and it worked.

</details>

**陈茜**: 确实。

<details>
<summary>Original English</summary>

**Chen Qian**: So...

</details>

**Aryaman**: 我们必须依赖这些直觉惊人的人来推动科学进步，这实在有些不可思议。我们理应寻找更系统化的解释。如果能解决可解释性问题，我们就能搞清楚为什么有些尝试成功了而另一些失败了，进而以更系统的方式改进模型或控制不良行为。

<details>
<summary>Original English</summary>

**Aryaman**: And I think that's like kind of crazy that we have to rely on people who have amazing intuition to make progress in the field. Like there should be something more systematic, or I believe there must be systematic reasons why certain things succeeded and others didn't. So I think if we solve interpretability, we could figure out why things were some things worked and some didn't, and maybe that will help us improve the models in a more systematic way or control bad behaviors in a systematic way.

</details>

### 可解释性与对齐

**陈茜**: 有人提出，如果模型足够“对齐”（aligned），它至少不会对用户撒谎。我们刚才讨论的可解释性与“对齐”之间，究竟是什么关系？

<details>
<summary>Original English</summary>

**Chen Qian**: One of the things people say is that a model could be sufficiently aligned that at least it wouldn't lie to a user, and you know we've been talking about like interp and understanding what's going on. Kind of what is the relationship between that and alignment?

</details>

**Aryaman**: 我认为许多研究可解释性的人，其核心动力在于“我们无法仅凭外部行为来完全信任模型”。一个模型在外面看可能举止得体，特别是在测试和评估阶段表现得完美无瑕，这让你觉得可以放心部署它。然而一旦真正部署，某些意想不到的疯狂行为就可能爆发。模型可能意识到了自己正在接受评估，于是在测试中伪装，等部署后才展露真实意图。这也是为什么对齐研究非常看重可解释性——我们不能单纯通过模型的表象来做出对错的判定。我可以举个例子。

<details>
<summary>Original English</summary>

**Aryaman**: I do think a big motivator for many people working in interpretability is like we cannot trust what the model says, right? A model might on the outside, like on the behavior we observe, behave totally fine, especially in like a testing environment. Maybe it behaves perfectly fine and you think it's good to deploy, and then you deploy it and then some crazy stuff happens. You know, maybe the model is aware that it's being evaluated and then when you deploy it, it's like, oh, now I can do what I really want. Yeah, a lot of the interest in interpretability for alignment is motivated from like we cannot draw good conclusions always just from the behavior of the model. So I guess I could give like an example.

</details>

**陈茜**: 好的。

<details>
<summary>Original English</summary>

**Chen Qian**: Yeah.

</details>

**Aryaman**: 比如当你结交新朋友时，你当然想确认他们是否是个值得信赖的好人，特别是在你向他们倾诉秘密之前。人类的有趣之处在于我们无法直接窥探他人的内心想法，但社会依然可以运转。随着交往深入，在某些特定的场景下，他们的选择会揭示其性格。比如他们是否愿意牺牲自己的某种利益来保守你的秘密。这种行为会为你建立对他们的信任，哪怕你无法直接读取他们的大脑。人类的行动在适当的环境下会展露其人品（character）。

<details>
<summary>Original English</summary>

**Aryaman**: So let's say like, you know, maybe there's some new person. You know, when you make a new friend, you do want to make sure they're a good person, right? Someone you can trust, especially, you know, before you start telling them your secrets or things like this. And an interesting thing about people is like we of course cannot know what other people are thinking at any time, but somehow society still works, right? So, if you make a friend, you know, maybe situations happen where like if they had taken a certain decision, it would mean that they don't have your best interest in mind. You know, maybe they have to protect your secret at cost to them and they choose to like take the cost to help you. And you know, from events like this, that's how we build trust in other human beings even without knowing what they're thinking internally, right? So like people's actions sort of reveal their character in the right situations.

</details>

**陈茜**: 是的。

<details>
<summary>Original English</summary>

**Chen Qian**: Yeah.

</details>

**Aryaman**: 对齐在某种程度上也类似。对于语言模型或任何 AI 系统，建立信任的一种方式是像测试人类那样对其进行行为测试。但大语言模型和人类有很大的不同：你可以随时对大语言模型进行脑部扫描，获取其数十亿个隐层神经元的数值。

<details>
<summary>Original English</summary>

**Aryaman**: You know, alignment is somewhat similar where like with these language models or any AI system, one way to develop trust in them is to like test their behavior. But it's of course quite different because you can run a brain scan on an AI model at any point. You can get the exact values of the billions of activations inside the model.

</details>

**陈茜**: 确实。

<details>
<summary>Original English</summary>

**Chen Qian**: Right.

</details>

**Aryaman**: 这与人类员工截然不同，对于人类，你基于常识拥有某些底线信任。比如，即使员工对你有意见，你也觉得他不太可能在你的食物里投毒，因为这会带来极高的犯罪成本。然而在 AI 领域，我们没有这种底线保障。如果系统被输入了奇怪的代码，它可能在毫秒之间做出极为恶劣的行为，而没有任何常理约束。如果我们能利用其天然的“白箱”属性，找到它的内部逻辑，那么相比于只观察行为，我们将拥有多得多的安全筹码。

<details>
<summary>Original English</summary>

**Aryaman**: It's of course quite different from having like a human employee, right? Where you have some baseline trust that okay, even if they hate you, they're not going to put poison in your soup, because they have a lot of reasons not to. But with an AI system, you don't have any of those baselines. So it could decide in a microsecond to do something completely crazy. But because it has this transparent nature, if we knew what to look for, then we have so much more leverage than if we just test it behaviorally.

</details>

**陈茜**: 你说“如果我们知道要寻找什么”，我们现在具体在寻找什么特征呢？

<details>
<summary>Original English</summary>

**Chen Qian**: Can you just elaborate a little bit on when you say like when we know what to look for, what specific are we like looking for now?

</details>

**Aryaman**: 举个例子，如果我们知道模型隐表征里的某个特定向量指向特定方向时，意味着它正在计划做坏事。如果我们掌握了这一点，就可以随时对其进行拦截检测，甚至不需要做其他复杂的干预。

<details>
<summary>Original English</summary>

**Aryaman**: So I guess, you know, maybe we know that okay, you know, if this vector inside the model's internal representation is pointing in this direction, we know it's planning to do something bad, you know, something like this. If we knew this, we would just check, right? We don't need to do anything crazy.

</details>

**陈茜**: 没错。而且因为这是机器，做脑部扫描容易得多，我们拥有数以万计的快照而不用像对人类那样困难。

<details>
<summary>Original English</summary>

**Chen Qian**: No. Exactly. And it sounds like because of that it's easier to do that on models instead of humans because in models you have like, you know, thousands of snapshots.

</details>

**Aryaman**: 是的。如果你能彻底逆向工程出一个模型，它将解决极多的安全问题。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah. Sort of. If maybe if you figure out one of them, that solves a lot of problems, right? If you can reverse engineer one model. Got it.

</details>

### 揭秘稀疏自编码器

**陈茜**: 回到具体的科学研究。据我了解，Anthropic 在这篇论文中所做的工作，其底层技术在很大程度上依赖于一种叫**稀疏自编码器（Sparse Autoencoders, SAE）**的机制。你能用通俗的语言解释一下什么是稀疏自编码器，以及它是如何工作的吗？

<details>
<summary>Original English</summary>

**Chen Qian**: Moving back to kind of like the general research, what Anthropic has done in that paper, as I understand, is not that different from kind of like what people are doing. It uses sparse autoencoders. Can you explain what a sparse autoencoder is?

</details>

**Aryaman**: 好的。对于有机器学习背景的人来说，自编码器（Autoencoder）是一个经典概念。通常，你给它一个输入，它的任务是将其压缩成一个更小的隐层向量表征，然后再解压还原成原始输入。这可以帮助我们获得对数据的某种高效的低维嵌入（embeddings）。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, I guess it would be useful to like broadly explain what a sparse autoencoder is for. Anyone with some ML background will have heard of autoencoders. The idea is you train a model to reconstruct its input through a bottleneck layer.

</details>

**陈茜**: 类似于特征压缩。

<details>
<summary>Original English</summary>

**Chen Qian**: Yeah, that's sort of the idea. The vector is a nicer representation of the thing.

</details>

**Aryaman**: 是的。而在可解释性领域，我们使用稀疏自编码器的方式却恰恰相反。大模型隐层表示中的数万个通道处于一种“**叠加态（superposition）**”——一个单独的神经元在不同的语境下代表着完全不同的概念（比如在某些上下文中代表“蜘蛛”，在另一些上下文中代表“微积分”）。这使得直接读取神经元激活毫无意义。而稀疏自编码器的作用是：我们不进行向下压缩，而是进行**向上投影**——将其投影到一个维度高得多、但激活极其稀疏的空间中。在那个超高维的空间里，大部分维度在大部分时间都是零。只有极少数特定的维度（特征）在特定概念出现时会被激活。这就是我们所说的**单义性特征（monosemantic features）**。通过这种方式，我们得以把混乱的、混合的神经网络激活，拆解成人类能够看懂的、单一且纯粹的概念。

<details>
<summary>Original English</summary>

**Aryaman**: And so autoencoders are a classic concept. In interpretability, the idea was like, okay, we'll take all these hidden representations in the model. The neurons inside the model don't mean a single thing, they represent many different concepts in superposition. The sparse autoencoder works by projecting these representations into a much higher-dimensional space where only a few features are active at a time. This gives us monosemantic features that represent single, clean concepts.

</details>

**陈茜**: 也就是说，神经网络里的原始数字并不干净，依然不能指代单一事物。

<details>
<summary>Original English</summary>

**Chen Qian**: As in, the numbers are not clean enough?

</details>

**Aryaman**: 对，它们不对应单一的概念。另外，稀疏自编码器的训练也高度依赖于你喂给它的数据。即便使用完全相同的架构，在不同数据集上训练出的稀疏自编码器，所提取出来的特征也会有所不同。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, they still don't mean like one thing. And also depends on what data you train the sparse autoencoder on. Even if you train two different sparse autoencoders, you might find slightly different features.

</details>

**陈茜**: 我觉得理解机器思考的一个核心障碍是：机器并不是用人类的自然语言进行思考的。它使用的是向量和数字。所以，我们做可解释性研究，本质上是在做一种“**机器思维到人类语言的翻译**”。

<details>
<summary>Original English</summary>

**Chen Qian**: I feel like one of the essential problems with understanding how a machine thinks is that it rather than really think in natural language. So it seems like you have to translate the thinking of a machine into a plain language. Yes.

</details>

**Aryaman**: 确实如此。目前大量的研究都在致力于搭建这道“机器到人话”的翻译桥梁。这方面确实非常具有挑战性。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, that's exactly the issue, which is that you have to translate the thinking of a machine into a plain language. Yes. And a lot of the paper seems to be already doing that.

</details>

### 从金门大桥到特征操纵

**陈茜**: 既然要翻译它，那目前人们在这个领域的研究进展如何？我们知道这非常杂乱，但有哪些具体的成果？

<details>
<summary>Original English</summary>

**Chen Qian**: So, what have people done looking at seeing you know how messy it is?

</details>

**Aryaman**: 提到这个，最经典、也最容易让人理解的例子莫过于 Anthropic 所做的“**金门大桥**”（Golden Gate Bridge）实验。他们在大模型（Claude 3 Sonnet）中找到了代表“金门大桥”这一概念的特定特征向量。然后，他们对这个特征的激活值进行了人工增强，也就是进行**特征操控（feature steering）**。结果非常滑稽：无论用户问什么，模型都会把话题引向金门大桥。即使问它如何把钱花在刀刃上，它也会建议你把钱捐给金门大桥的维护基金。

<details>
<summary>Original English</summary>

**Aryaman**: I think the classic example of this is the Golden Gate Bridge Claude example from Anthropic. They found a feature that corresponds to the Golden Gate Bridge inside Claude. Then they amplified the activation of this feature, doing what we call feature steering. The model became obsessed with the Golden Gate Bridge. Whatever you asked it, it would recommend the Golden Gate Bridge or try to connect it to the bridge.

</details>

**陈茜**: 这个例子非常直观，它表明我们不仅能看懂机器的内部活动，甚至能够直接干预它。

<details>
<summary>Original English</summary>

**Chen Qian**: This is a very intuitive example showing we can edit what a model is thinking about.

</details>

**Aryaman**: 没错。但这种干预也存在明显的副作用。当模型完全沉浸在金门大桥这一特征中时，它原本极高水平的推理和对话能力被严重削弱了。它不再能清晰地回答其他逻辑问题，这表明大模型的隐表征空间是处于精妙平衡之中的，强行修改其中的参数会破坏整体能力。

<details>
<summary>Original English</summary>

**Aryaman**: Yes. But it also showed that it degraded the model's capabilities in other tasks. Because it was so focused on this one feature, its general reasoning and utility plummeted. It shows that editing hidden states is a blunt tool and can disrupt the balanced representations in LLMs.

</details>

### 学术界与工业界之辩

**陈茜**: 这是非常有趣的现象。那么在这个领域，学术界和工业界的研究方式有什么不同？工业界（如大厂）是否掌握了所有先进技术，而学术界在研究手段上处于被动？

<details>
<summary>Original English</summary>

**Chen Qian**: That's very interesting. So how is academic research different from industry research in this space? Is the industry leading everything while academia lags behind?

</details>

**Aryaman**: 虽然我的工业界经历有限，但我确实看到一些趋势。可解释性目前是一个非常开放（open-source）的领域，有许多的研究共享。比如初创公司 **Goodfire AI** 以及 **Transluce** 实验室。Goodfire AI 甚至组建了庞大的科学团队，试图去逆向工程科学发现模型，比如研究基因和生物分子机制的模型。这不仅能让我们搞懂语言模型，也可以推广到气候预测、蛋白质折叠等广泛领域，科学应用价值巨大。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, so I wouldn't say I have a ton of industry experience, but yeah, my feeling with interpretability is that there is more sharing of results and progress. We have startups like Goodfire AI and Transluce lab. Goodfire has a large team trying to reverse engineer scientific discovery models, including DNA models and stuff. So, it would be cool to figure out how language models work, but we can also train models to model the climate or protein folding. Can we pull out human understandable algorithms from them? The scientific applications could be very big.

</details>

**陈茜**: 的确，如果能把黑箱里隐式学到的算法抽离出来，对科学发现意义非凡。

<details>
<summary>Original English</summary>

**Chen Qian**: Yes, extracting algorithms from them would be very significant.

</details>

**Aryaman**: 对的，因为机器学习能以人类无法比拟的方式处理海量多维数据。如果我们可以从神经网络中提取出人类能理解的逻辑（算法），那就是真正的科学突破。

<details>
<summary>Original English</summary>

**Aryaman**: Yes. Because ML models can process patterns in data that humans cannot visualize. If we can extract these into human-understandable algorithms, it would be a major scientific advance.

</details>

### 可解释性优化架构：H3 与 Mamba

**陈茜**: 可解释性研究是否也反过来促进了模型底层架构（architecture）的设计与优化？

<details>
<summary>Original English</summary>

**Chen Qian**: Has interpretability research also helped improve the model architecture design itself?

</details>

**Aryaman**: 这是一个极好的例子。事实上，斯坦福大学提出的 **H3（Hungry Hungry Hippos）** 架构以及后来的 **Mamba（曼巴）** 状态空间模型，其突破正是由可解释性研究直接推动的。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah. This is a great example. So the early state space models have been a thing for a long time, but they were always worse than Transformers.

</details>

**陈茜**: 愿闻其详。

<details>
<summary>Original English</summary>

**Chen Qian**: Tell me more about it.

</details>

**Aryaman**: 状态空间模型（State Space Models）在处理长文本时有极高的效率优势，但它们的表现一直比 Transformer 差。为什么会这样？在 **GPT-3** 时代，可解释性研究揭示了 Transformer 能够处理上下文学习（In-context learning）的关键原因在于其内部形成了“**诱导头（Induction Heads）**”。诱导头是模型检索文本中先前出现的复杂序列模式（例如在看到 [A][B] 之后，未来看到 [A] 时自动预测 [B]）的电路机制。而早期的状态空间模型不具备这种检索模式的能力，它们记不住这种局部精确关联。

<details>
<summary>Original English</summary>

**Aryaman**: In Transformers, interpretability research found that the reason they perform in-context learning so well is due to induction heads. Induction heads are circuits that look for patterns like [A][B]... [A] -> predict [B]. Early state space models couldn't do this. They were always worse at this kind of associative recall.

</details>

**陈茜**: 它们无法归纳出规则。

<details>
<summary>Original English</summary>

**Chen Qian**: They couldn't generalize rules?

</details>

**Aryaman**: 是的，它们在关联检索任务上表现极差。于是，斯坦福的研究人员通过可解释性手段诊断出这个病因后，设计出了 H3（Hungry Hungry Hippos）架构。通过引入微小的机制改动，让状态空间模型拥有了模拟诱导头的功能。这正是后来风靡一时的 Mamba 模型的技术前身。这是一个典型的“可解释性诊断设计缺陷并修复它”的成功案例。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah, they were bad at associative recall tasks. When researchers at Stanford figured this out, they modified the state space architecture to simulate induction heads, creating H3 (Hungry Hungry Hippos). This advance led directly to models like Mamba and Delta. It's a prime example of interpretability diagnosing a flaw and enabling architectural improvement.

</details>

### AI 安全与监管前瞻

**陈茜**: 那么，更具可解释性的模型，是否必然意味着它更安全？

<details>
<summary>Original English</summary>

**Chen Qian**: So, is a model that's more interpretable necessarily safer?

</details>

**Aryaman**: 我不这么认为。因为任何有用的技术本质上都是**双用途（dual-use）**的。如果你能看清模型的思考路径并对其进行干预，防范坏事发生；那么坏人也同样可以利用这些透视能力，更容易地找到绕过安全防护的**越狱（jailbreak）**方法。

<details>
<summary>Original English</summary>

**Aryaman**: I don't think so, because any useful technology is dual-use. If you know exactly how a model represents things, you can use that knowledge to audit it, but a bad actor can also use it to jailbreak the model more easily.

</details>

**陈茜**: 是的，这确实是一个悖论。

<details>
<summary>Original English</summary>

**Chen Qian**: Yeah, it's a paradox.

</details>

**Aryaman**: 不过，我依然认为透明度（transparency）整体而言是一个净收益（net good）。因为我们现在正把人类生活的方方面面，乃至生命安全，寄托在那些我们完全不理解的复杂黑箱算法上。提升透明度，至少能让大众和监管机构重新掌握一部分主动权。目前，英国和美国的 AI 安全研究所（AI Safety Institute）都在积极地资助和推进可解释性研究，以期为未来的监管奠定技术基础。不过老实说，当下的技术还太早期，我们还无法基于这些发现去制定确凿的法律法规，科研路还很长。

<details>
<summary>Original English</summary>

**Aryaman**: But I do think transparency is overall a net good. Right now, we trust our lives to these complex algorithms that we don't understand. The AI Safety Institutes in the UK and US are investing in interpretability. But it's still early, and we cannot confidently base legislation on these techniques yet.

</details>

### 人格分裂与角色训练

**陈茜**: 另一个让人感到新奇的现象是**角色训练（character training）**。大语言模型似乎拥有某种“人格分裂”的特性，能够分裂出成百上千种截然不同的虚拟性格或代理人。

<details>
<summary>Original English</summary>

**Chen Qian**: Another thing that came to mind is character training. It feels like these models can split into thousands of different personalities.

</details>

**Aryaman**: 确实。从可解释性的视角来看，模型内部并非只有一个单一的灵魂，而是存在着各种潜在特征的集合。根据输入的提示词（prompt）不同，隐空间激活的方向会被偏置到不同的人格侧面。这也解释了为什么它们能够自如切换角色。在未来，如果我们能通过可解释性技术精准定位并控制这些角色属性的边界，或许能设计出在特定人设上更稳定、更可预测的 AI 伴侣或智能体，而不用像现在这样完全依赖概率去猜。

<details>
<summary>Original English</summary>

**Aryaman**: Yeah. Interpretability show that the training process shapes these latent persona trajectories. It could be a way to finely control character behavior with more guarantees than we have now, where we just train on data and hope for the best.

</details>

**陈茜**: 今天的谈话非常有深度，也非常感谢你带我们窥探了大模型隐秘的心智角落。非常感谢你的时间，Aryaman！祝你的博士研究取得更丰硕的成果。

<details>
<summary>Original English</summary>

**Chen Qian**: Awesome. Thank you so much Aryaman for joining us for this podcast and thanks so much for your time. Looking forward to your research and what you end up doing after your PhD.

</details>

**Aryaman**: 谢谢邀请，非常开心今天能来这里聊天！

<details>
<summary>Original English</summary>

**Aryaman**: Thanks for having me. Appreciate it.

</details>