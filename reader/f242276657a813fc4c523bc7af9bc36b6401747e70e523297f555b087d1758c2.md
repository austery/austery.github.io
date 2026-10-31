---
author: 硅谷101
date: '2026-08-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=J5_90lWxM_o
speaker: 硅谷101
tags:
  - interpretability
  - large-language-model
  - internal-reasoning
  - representation-learning
title: 大语言模型内部推理与可解释性研究探讨
summary: 访谈探讨了大语言模型的可解释性研究与内部推理机制。受访者结合 J-Space 等研究，讨论了模型内部潜在表征、角色训练以及透明度对监管的潜在价值，同时指出当前基于此类研究制定政策仍处于早期阶段。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/7 -->

### 开场与可解释性研究

losing the AI.

<details><summary>Original English</summary>
losing the AI.
</details>

[音乐]

我不知道这些东西为什么有效。我把这归因于天意。我们不得不依赖那些拥有惊人直觉的人来推动这个领域的进展，这挺疯狂的。

<details><summary>Original English</summary>
[music]

I don't know why these things work. I attribute it to divine providence. Kind of crazy that we have to rely on people who have amazing intuition to make progress in the field.
</details>

Fore

[音乐]

[音乐]

[音乐]

transluc. forchech.

[音乐]

<details><summary>Original English</summary>
Fore

[music]

[music]

[music]

transluc. forchech.

[music]
</details>

模型内部正在发生一些它们没有说出来的推理步骤。如果你有一个真正优秀的语言模型，它将能够在那里正确预测下一个词。要做到这一点，它内部必须有一个类似于人与人之间如何互动的世界模型。

<details><summary>Original English</summary>
There is internal steps of [music] reasoning happening in models that they don't say. If you have a really good language model, it will be able to predict the next word correctly there. To do that, it must have like a world model inside of like how people [music] interact.
</details>

\>> 我们还不知道那个世界模型是什么。

<details><summary>Original English</summary>
>> We don't know what that world model is yet.
</details>

\>> 可解释性的目标就是去弄清楚那是什么。我们的技术没有一种擅长控制模型的内部思想。如果你的模型在做坏事，没有人会去编辑那些思想。

<details><summary>Original English</summary>
>> The goal of interpability is like figure out what that is. None of our techniques are good at controlling the internal thoughts of a model. If your model is doing something bad, no one goes and edits the thoughts.
</details>

Aurora

Armen，欢迎来到 Valley 101。

<details><summary>Original English</summary>
Aurora

Armen, welcome to a Valley 101.
</details>

\>> 感谢邀请。

<details><summary>Original English</summary>
>> Thanks for having me.
</details>

\>> 是的，感谢你开车来到旧金山，我真的很兴奋我们终于能聊上了。可解释性是人们一直让我去了解的一个方向，我也觉得它非常吸引人，因为我是说，我们怎么会不想知道我们的 AI 统治者是否在密谋杀害我们呢，不过……

<details><summary>Original English</summary>
>> Yeah, thanks for driving up to San Francisco and really I'm really excited we finally got to chat. uh interpretability is something that people have been telling me to look into for a while and I thought it was pretty fascinating as well because I mean why wouldn't we want to know whether uh our AI overlords are plotting to kill us but uh
</details>

\>> 当然，是的。[笑声]

<details><summary>Original English</summary>
>> sure yeah [laughter]
</details>

\>> 在开始之前，你能不能先给观众做个自我介绍？

<details><summary>Original English</summary>
>> to get us started uh why don't you just like give the viewers an introduction of yourself
</details>

\>> 嗯，好的，我是 Arian，我是斯坦福大学的博士生，我的导师是 Chris Potts。是的，我本科有语言学背景，一直对语言很感兴趣。后来所有这些疯狂的 AI 进展发生了，鉴于我比较有科学头脑，我想去研究比如为什么这些东西有效，所以可解释性对我来说是一个很自然的研究方向。

<details><summary>Original English</summary>
>> uh yeah so I'm Arian I'm a PhD student at Stanford um I'm advised by Chris Pototts and yeah I have a background in linguistics in undergrad um you know always been fascinated in languages and then all this crazy AI stuff happened and you know given that I'm pretty scientifically minded I wanted to study like you know why do these things work so interpretability was a natural direction for me to work in
</details>

\>> 挺好的，是的。所以我想简单来说，可解释性就是我们试图去理解模型内部正在发生什么。但这是一个相当宽泛的问题，我觉得这可能会带你走向很多不同的方向。你对可解释性研究的定义是什么？你具体关注什么？

<details><summary>Original English</summary>
nice yeah so I guess to put it simply interpretability is just uh we are trying to understand what's going on inside a model but this is a pretty broad question and I feel like there could be a lot of different directions this could take you uh what is your definition of interpretability research and what do you focus on specifically?
</details>

\>> 是的，所以我想说研究可解释性可以有很多切入角度。最吸引我的视角是，比如，即使在五年前，我们在 AI 领域所做的一切其实都不太成功，特别是在语言模型方面。人们使用语言模型已经很长时间了，但当时有点像是用在语音转录的后期编辑这类事情上。然后发生了一些事情，使得它们成为了每个人都在研究的东西，大家向它们投入数十亿美元等等。所以对我来说，可解释性就像是试图回答这样一个问题：到底改变了什么，为什么以前不成功而现在成功了？

<details><summary>Original English</summary>
>> Yeah, so I would say there's a lot of angles that you can take for approaching interpretability. The perspective that most interested me is like okay like five years ago even you know all the things we were doing in AI were not really successful like especially in language models people were using language models for a long time but it was sort of like oh post editing like speech transcripts this kind of thing uh and then something happened such that they became the thing that everyone's working on they invest billions of dollars into them and so on. So, so for me interability is like trying to answer the question of like what changed like why were things not successful before and now they are.
</details>

### J-Space 与内部推理

\>> 促使我做这次采访的原因之一，是 Anthropic 发布的这篇名为 J-Space 或者说是 AI 模型工作空间的论文。我先在宏观层面上做个总结，然后你可以带我深入了解细节。但基本上，听起来研究人员使用了一种方法来观察 AI 模型内部在思考过程中没有说出来的深层活动，他们提出了 J-Space 这个概念，这有点像是 AI 的工作空间。研究人员在论文中做的一个非常吸引人的例子是，他们问 AI 模型一个会结网的动物有几条腿，AI 模型回答说八条，其中“蜘蛛”（spider）这个词在任何地方都没有出现。但随后当研究人员进入模型内部并将“蜘蛛”改为比如“蚂蚁”（ant）时，答案变成了六条。这只是表明我们似乎能够操纵 AI 模型如何思考事物的几个例子之一。所以，你能不能带我们浏览一下这篇论文，再多讲讲为什么我们能够编辑一个 AI 模型从未说出口的词？

<details><summary>Original English</summary>
One of the things that kind of motivated me to do this interview is s anthropics release of this paper called Jspace or I guess a workplace and for AI models and I'm just going to summarize it on a pretty high level and you can kind of walk me through the the details but basically it sounds like the researchers used a method to look into what's going on like inside an AI model that it didn't say when it's doing like during the syncing process and they introduced this concept of uh JSpace which is kind of a workspace for AI. Uh so one of the very fascinating examples that the researchers did in this paper is that they asked the AI model the number of legs um of a animal that spins web and the AI model answered eight uh where the word spider did not appear anywhere but then when the researchers went inside the model and changed spider to like ant the answer changed to six. This is one of just a few examples of how it seems like we can manipulate how an AI model is thinking about things. So, why don't you just walk us through this paper a little bit and kind of just tell us a little bit more about why we can edit a word that has never been said by an AI model.
</details>

\>> 是的，我认为那是一篇非常吸引人的论文。而且我认为它为越来越多的证据增添了支持，表明模型内部正在发生一些它们没有说出来的推理步骤。我没有读完 J-Space 的全部一百多页，是的，但我大概理解这个想法。大体思路是，我们有这样一个被称为雅可比矩阵（Jacobian）的算子——

<details><summary>Original English</summary>
>> Yeah, I thought that was a fascinating paper. Um, and I think it adds to a growing body of evidence that like there is internal steps of reasoning happening in models that they don't say. I haven't read all like hundred and whatever pages of JSpace. Yeah. But I like sort of understand the idea. The the broad idea is like we have this uh operator called the Jacobian
</details>

\>> 嗯，也就是微积分里的导数。

<details><summary>Original English</summary>
>> um which you know is basically derivatives from calculus.
</details>

\>> 我们可以在模型中使用它来告诉我们，在它的潜在激活空间中（因为你知道一切都是向量），哪些方向会导致模型在未来输出某些特定的词。所以也许在提前 10 个 token 的位置，如果模型内部的隐藏表示朝向某个方向，那么它稍后就会输出“蜘蛛”这个词，诸如此类。

<details><summary>Original English</summary>
We can use this in a model to tell us like uh what directions in its you know latent activation space because you know everything's vectors. So it tells us what directions um cause the model to say certain words in the future. Um so maybe like you know 10 tokens before if the hidden representation inside the model is pointing some way then it'll say the word spider later on this kind of thing.
</details>

\>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

\>> 嗯……

<details><summary>Original English</summary>
>> Um
</details>

\>> 这篇论文的一个优点是，这是一个非常优雅而简单的事情，不知为何以前没有人真正确切尝试过，但我认为我们有大量的证据表明，是的，这些内部推理步骤是存在的。所以即使你去看 Anthropic 早期关于电路（circuits）的研究，他们有一篇叫做《大语言模型的生物学》（the biology of large language models）的文章。他们展示了比如当一个模型在做三位数加法题时，它可以不用把所有的步骤都大声说出来就能完成，但如果你观察其内部，你可以找到神经元在记录个位数应该是什么，或者十位数应该是什么。然后他们还有一个例子，比如当你让模型就某个主题为你作一首押韵的诗时，当它处于一节诗的末尾时，它已经在规划下一节诗的结尾应该是什么，以便保持押韵。所以我认为毫无疑问，模型会在内部做一些它们不会大声说出来的事情。

<details><summary>Original English</summary>
>> and one nice thing about the paper is that this is like a very elegant and simple thing that somehow no one had really exactly tried before but I think we have a lot of evidence that like yeah these internal reasoning steps are there. So even if you look at uh Anthropic's earlier work on circuits, they had this thing called the biology of large language models. Um and they showed like oh when a model is doing you know three-digit addition problems it can do it without saying all the steps out loud but if you look inside you can find neurons that are like oh it's keeping track of what the ones digit should be or what the 10's digit should be. And then in in they also had an example of like when a model you ask it to tell like a rhyming poem to you about some topic. Uh when it's at the end of one verse it's already planning what the end of the next verse should be so that it's still rhyming. So I think like without a doubt models do stuff internally that they don't say out loud.
</details>

我认为它们必须这样做才能学好语言建模任务。你看，Ilya Sutskever 是我们领域一位非常著名的研究人员，他给自回归语言建模（比如预测下一个词）做阐释时举过一个例子：当你在读一本谋杀悬疑小说时，假设你想在整部小说中预测下一个词，到了结尾总会有一个真相揭晓，比如凶手是谁，然后你读到一句话写着“凶手是……”，为了预测接下来的那个词，不知何故你必须对整部小说、整个故事以及指向各方的所有证据进行建模。所以如果你有一个真正优秀的语言模型，它必须懂得如何在内部进行逻辑推导，对吧？以此来推断出那种情况下正确的下一个词，对吧？

<details><summary>Original English</summary>
I think they have to to like learn the language modeling task. Well you know Ilia Sutzkaru who's a very famous researcher in our area. He motivated like auto reggressive language modeling like predicting the next word as like one of the examples he gave is you know when you're reading a detect you know like a murder mystery novel and let's say you want to predict the next word throughout the novel you know at the end there's always a reveal like who was the killer and you get to a sentence that's that's like the killer was and to predict that next word somehow you have to model the whole you know novel the whole story all the evidence going either way. So if you have a language model that's really good, it must know how to logically deduce stuff internally, right? To to figure out the the correct next word in that case,
</details>

\>> 对，就像是它并没有真正出现在训练数据中，但它有点推导出了它。

<details><summary>Original English</summary>
>> right? Right. Like it's something that didn't really appear in the training data, but it kind of deduced it.
</details>

\>> 是的。在上下文中，如果是，你知道，如果你有一个真正优秀的语言模型，它将能够在那里正确预测下一个词。

<details><summary>Original English</summary>
>> Yeah. In the context, if it's, you know, if you have a really good language model, it will be able to predict the next word correctly there.
</details>

\>> 要做到这一点，它内部必须有一个类似于人与人之间如何互动、以及所有这一切的证据是什么的世界模型。我希望能有一个更好的例子，但他毕竟是 Ilya，很难想出比这更好的例子了……

<details><summary>Original English</summary>
>> And to do that, it must have like a world model inside of like how people interact and like what the evidence was for, you know, all this. I wish I had a better example, but you know, he is ilas. It's hard to come up with better examples than
</details>

\>> 噢，是不是说我们现在还不知道那个世界模型是什么？这是我们目前正试图解决的问题吗，还是？

<details><summary>Original English</summary>
>> Oh, is it like we don't know what that world model is yet? Is that something that we're trying to solve right now or?
</details>

\>> 是的。所以我想可解释性的目标就像是，好吧，我们知道为了在下一个 token 预测上做得非常好，你必须在内部建立一个关于文本中正在发生什么的非常复杂的内部模型。

<details><summary>Original English</summary>
>> Yeah. So, I think the goal of interp is like okay, we know in order to do really well on next token prediction, you must have you must develop a really complex internal model of like what's going on in a text.
</details>

\>> 嗯，而我们的目标就是去弄清楚那是什么。

<details><summary>Original English</summary>
>> Um, and like our goal is to like figure out what that what that is.
</details>

\>> 明白了，明白了。让我们在这个内部推理上稍微退一步，因为如果我可以这样表述的话，它与我们现在所知道的思维链（chain of thought）形成了某种直接的对比，思维链是模型在思考时具体拼写出来的东西。为什么思维链不是理解模型如何思考的最佳方式呢？

<details><summary>Original English</summary>
>> Got it. Got it. Uh let's just take a little step back into this internal reasoning because it's uh it's kind of in direct contrast to uh what we now know as chain of thoughts which is what the model spells out when it's syncing if I can put it that way. And why is chain of salts not the best way to understand how like a model sinks?
</details>

\>> 我不知道我是否会提出那么强烈的论断。它肯定是有用的。

<details><summary>Original English</summary>
>> I don't know if I'd make that strong a claim. It's definitely useful.
</details>

\>> 嗯，而且这也是显而易见的，比如一年半或两年前没有思维链的模型，

<details><summary>Original English</summary>
>> Um and so it's also super obvious that like models that didn't have chain of thought like a year and a half or two ago,
</details>

\>> 它们更差。它们确实严格劣于现在用思维链训练的模型。因此，思维链必然是……

<details><summary>Original English</summary>
>> they're like worse. They're like strictly worse than models that are trained with chain of thought now. Therefore, chain of thought must be
</details>

<!-- chunk 2/7 -->

做点有用的事，比如非常有用的事。

<details><summary>Original English</summary>
doing

 something

 useful,

 like

 something





very

 useful.
</details>

>> 这就像我们转向推理模型的时候一样。

<details><summary>Original English</summary>
>> That's

 like

 when

 we

 switched

 to





reasoning.
</details>

>> 对。当我们开始训练模型在说出那个词——呃，在说出它们的答案之前先进行推理。是的。我非常推崇先做最简单的事情。这就是我在研究中学到的一切。如果我把它们结合在一起，最重要的事就是先做简单的事情，然后再转向复杂的事情。所以，我认为比起解决可解释性，检查思维链超级简单。我们应该这么做。嗯，在实践中，比如你知道当 Anthropic、Meta 或 OpenAI 他们进行安全审计时，他们确实会检查模型的思维链是否在说可疑的话，或者或者比如计划做奇怪的事情，嗯，这似乎在某种程度上帮助他们发现了未对齐的情况。所以是的，我确实认为思维链是有用、值得分析的。

我想在深入了解这具体是如何运作的更多例子之前，我只是想稍微谈谈这里的最终目标，因为我认为大家都很清楚为什么我们都应该关心语言模型内部发生了什么。呃，但我很想知道，在我们理解了它内部发生的事情之后，我们要怎么做？比如有哪些应用，或者我们现在不必深入具体的应用，但比如目标是什么？为什么你知道我们……呃，普通人要关心？［笑声］我认为，我觉得解决可解释性大概会带来两类应用。

<details><summary>Original English</summary>
>> Yeah.

 When

 we

 started

 training

 models

 to





reason

 before

 they

 say

 the

 word

 uh





before

 they

 say

 their

 answer.

 Yeah.

 I'm





a

 big

 fan

 of

 like

 you

 should

 do

 the





simplest

 thing

 first.

 This

 is

 like





everything

 I've

 learned

 in

 research.

 If





I

 combine

 it

 together,

 the

 most





important

 thing

 would

 be

 like

 just

 do





simple

 things

 first

 before

 moving

 on

 to





complex

 things.

 So,

 I

 think

 like





checking

 the

 chain

 of

 thought

 is

 super





simple

 compared

 to

 solving

 interp.

 we





should

 do

 it.

 Um,

 and

 in

 practice

 like





you

 know

 when

 u

 anthropic

 or

 meta

 or





openi

 they

 run

 their

 safety

 audits

 they





do

 check

 if

 the

 model's

 chain

 of

 thought





is

 like

 saying

 sus

 things

 or

 or

 like





planning

 to

 do

 weird

 things

 um

 and

 it





seems

 to

 help

 them

 catch

 misalignment

 to





some

 extent.

 So

 yeah

 I

 I

 do

 think

 chain





of

 thought

 is

 like

 useful

 to

 analyze.

 I





guess

 before

 we

 get

 into

 more

 examples





of

 how

 this

 works,

 I

 just

 wanted

 to

 talk





a

 little

 bit

 about

 kind

 of

 the

 end

 goal





here

 because

 I

 think

 it's

 pretty

 clear





why

 we

 should

 all

 care

 about

 what's





going

 on

 inside

 a

 language

 model.

 Uh

 but





I'm

 wondering

 what

 do

 we

 do

 after

 we





understand

 what's

 going

 on

 inside

 it?





Like

 what

 are

 the

 applications

 or

 we





don't

 have

 to

 get

 into

 specific





applications

 now,

 but

 like

 what

 is

 the





go

 and

 why

 should

 you

 know

 us

 uh

 normies





care?

 [laughter]

 I

 think

 so

 there's

 sort





of

 two

 sort

 of

 applications

 that

 I

 feel





like

 you

 know

 solving

 interpability





would

 lead

 to.
</details>

### 可解释性的价值与应用方向

>> 所以我认为其中之一就是信任，比如要对技术产生信任，了解它是如何运作的对我们来说很重要。

<details><summary>Original English</summary>
>> So

 I

 think

 one

 of

 them

 is

 like

 like





trust

 like

 to

 have

 trust

 in

 technology





it's

 important

 for

 us

 to

 know

 how

 it





works.
</details>

>> 嗯，如果你想想，我不知道，比如有监管机构和政府来监管，比如哦你如何制造飞机，你如何操作工业机械，或者比如你知道的水力压裂等等这些事情。看起来为了监管，你知道，那些令人惊叹且有用的技术，我们确实需要了解故障模式，并且比如你知道，弄清楚如何确定责任归属以及所有这些事情。是的，我认为现在监管 AI 事务真的很难，因为我们在某种程度上不知道如何预防不良行为，或者甚至不知道为什么会发生坏事，或者或者比如该归咎于谁，因为没有人真正知道，你知道，某些行为是从何而来的。比如我们拥有你知道的庞大数据集、漫长的训练过程，这就像是……真的很难说是什么导致了某些事情。所以我认为，在提升社会信任方面，如果我们了解行为为何发生会很有用，即使我们没有完美的理解。嗯你知道，如果你的医生正在使用 AI 系统之类的东西，你以及你的医生可能都会想知道比如它为什么会给出某个输出，对吧？是的，所以那是事情的一方面。呃事情的另一方面就像……

我确实认为很多 AI 的进展，比如从研究层面来说，是非常偏经验主义的，这并不是坏事，比如当然在我们的领域。与化学、生物或你知道的现实世界事物相比，运行实验是如此容易。

<details><summary>Original English</summary>
>> Um

 if

 you

 think

 about

 I

 don't

 know

 like





there

 are

 regulatory

 bodies

 and





governments

 that

 regulate

 like

 oh

 how





you

 manufacture

 airplanes

 how

 you

 do





like

 industrial

 machinery

 or

 like

 you





know

 oil

 fracking

 and

 all

 these

 things.





It

 seems

 like

 to

 regulate,

 you

 know,





impressive

 technologies

 that

 can

 be





useful,

 we

 do

 need

 to

 understand

 the





failure

 modes

 and

 like,

 you

 know,

 figure





out

 how

 to

 sign

 liability

 and

 all

 these





things.

 Yeah,

 I

 think

 right

 now

 it's





really

 hard

 to

 regulate

 AI

 stuff

 because





we

 sort

 of

 don't

 know

 how

 to

 prevent

 bad





behaviors

 or

 like

 even

 know

 why





something

 bad

 happened

 or

 or

 like

 who

 to





blame

 like

 because

 no

 one

 really

 knows,





you

 know,

 where

 some

 behaviors

 come





from.

 like

 we

 have

 this

 you

 know

 massive





data

 sets

 long

 training

 process

 it's





like

 it's

 really

 hard

 to

 tell

 what





caused

 something.

 So

 I

 think

 sort

 of

 for





improving

 societal

 trust

 it

 would

 be





useful

 if

 we

 like

 understood

 why





behaviors

 are

 happening

 even

 if

 we

 don't





have

 a

 perfect

 understanding

 um

 you

 know





if

 your

 doctor

 is

 using

 an

 AI

 system

 or





something

 like

 that

 you

 as

 well

 as

 your





doctor

 will

 probably

 want

 to

 know

 like





why

 it's

 producing

 some

 output

 right





yeah

 so

 that's

 one

 side

 of

 things

 uh

 the





other

 side

 of

 things

 is

 like





I

 do

 think

 a

 lot

 of

 AI

 progress

 like





research

 wise

 has

 been

 extremely





empirical

 and

 this

 is

 not

 a

 bad

 thing





like

 of

 course

 in

 our

 field.

 It's

 so





easy

 to

 run

 experiments

 compared

 to

 like





chemistry

 or

 biology

 or

 you

 know

 like





real

 world

 things.
</details>

>> 看起来随着东西变得越来越好，是因为某些在……或者说某些非常有直觉的聪明人想出了新东西，而他们不知道为什么那些东西能起效，但它们就是起效了。有一位著名的比如 Google 研究员 Noam Shazeer……

<details><summary>Original English</summary>
>> It

 seems

 like

 as

 stuff

 has

 gotten





better,

 it's

 because

 some

 people

 at le





or

 like

 some

 really

 smart

 people

 with





great

 intuition

 have

 come

 up

 with

 things





and

 they

 don't

 know

 why

 those

 things





work

 but

 they

 work.

 There's

 a

 famous





like

 Google

 researcher

 Nome

 Shazir
</details>

>> 我猜他现在不在 Google 了，但他发明了许多带来现代 Transformer 的架构改进，并且他是原始 Transformer 论文的作者之一。他有一篇论文，其中介绍了门控线性单元（GLU），这只是又一项架构上的东西。在论文的结尾，他就像是……他展示了他所有的实验。他展示了它们表现更好。他说比如，你知道的我不知道为什么这些东西能起效，我将其归功于神圣的天意。在论文里写这样一句话真的很疯狂。他就好像在说，当然是上帝赐予了我尝试这个实验的灵感，而且它成功了。所以……

<details><summary>Original English</summary>
>> I

 guess

 he's

 not

 at

 Google

 anymore

 but





um

 he

 he

 invented

 a

 lot

 of

 the





architectural

 improvements

 that

 led

 to





modern

 transformers

 and

 he's

 on

 the





original

 transformers

 paper.

 He

 has

 a





paper

 where

 he

 introduced

 uh

 gated





linear

 units

 which

 are

 just

 one

 more





architectural

 thing.

 In

 the

 end

 of

 the





paper

 he's

 like

 so

 he

 shows

 all

 his





experiments.

 He

 shows

 they're

 better.





He's

 like

 you

 know

 I

 don't

 know

 why





these

 things

 work.

 I

 attribute

 it

 to





divine

 providence.

 It's

 like

 a

 crazy





line

 to

 put

 in

 a

 paper.

 He's

 like

 sure





like

 God

 gave

 me

 the

 vision

 of

 like





trying

 this

 experiment

 and

 it

 worked.

 So
</details>

>> 嗯，我认为我们必须依赖具有惊人直觉的人来推动该领域的进步，这有点疯狂。比如应该存在更系统化的东西，或者我相信某些东西成功而另一些没有成功背后一定有系统性的原因。因此我认为，如果我们解决了可解释性，我们就能弄清楚为什么事情是……某些东西起效了而某些没有，也许这会帮助我们以更系统的方式改进模型，或者以系统的方式控制不良行为。人们常说的观点之一是，一个模型可能达到充分对齐，以至于至少它不会对用户撒谎，并且你知道我们一直在讨论比如可解释性以及了解内部发生了什么，这与对齐之间究竟是什么关系？

<details><summary>Original English</summary>
>> um

 and

 I

 think

 that's

 like

 kind

 of

 crazy





that

 we

 have

 to

 rely

 on

 people

 who

 have





amazing

 intuition

 to

 make

 progress

 in





the

 field.

 like

 there

 should

 be





something

 more

 systematic

 or

 I

 believe





there

 must

 be

 systematic

 reasons

 why





certain

 things

 succeeded

 and

 others





didn't.

 So

 I

 think

 if

 we

 solve





interpretability

 we

 could

 figure

 out

 why





things

 were

 some

 things

 worked

 and

 some





didn't

 and

 maybe

 that

 will

 help

 us





improve

 the

 models

 in

 a

 more

 systematic





way

 or

 control

 bad

 behaviors

 in

 a





systematic

 way.

 One

 of the

 things

 people





say

 is

 that

 a

 model

 could

 be





sufficiently

 aligned

 that

 at

 least

 it





wouldn't

 lie

 to

 an

 user

 and

 you

 know





we've

 been

 talking

 about

 like

 interb

 and





understanding

 what's

 going

 on

 kind

 of





what

 is

 the

 relationship

 between

 that





and

 alignment
</details>

### 可解释性与对齐

>> 我确实认为对许多从事可解释性研究的人来说，一个巨大的驱动力就是我们不能信任模型所说的话，对吧？呃，一个模型在表面上——比如在我们观察到的行为上——可能表现得完全正常，特别是在像测试环境中，也许它表现得完全正常，你认为部署它是安全的，然后你部署了它，接着就发生了一些疯狂的事情。嗯，你知道，也许模型意识到了自己正在接受评估，然后当你部署它时，它就像是“哦，现在我可以做我真正想做的事了”。是的，对可解释性用于对齐的大量兴趣源于……比如我们不能总是仅仅从模型的行为中得出良好的结论。所以我想我可以给举个例子，嗯……

<details><summary>Original English</summary>
>> I

 do

 think

 a

 big

 motivator

 for

 many





people

 working

 in

 interability

 is

 like





we

 cannot

 trust

 what

 the

 model

 says





right

 uh

 a

 model

 might

 on

 the

 on

 the





outside

 like

 on

 the

 behavior

 we

 observe





behave

 totally

 fine

 especially

 in

 like

 a





testing

 environment

 maybe

 it

 behaves





perfectly

 fine

 and

 you

 think

 it's

 good





to

 deploy

 and

 then

 you

 deploy

 it

 and





then

 some

 crazy

 stuff

 happens

 um

 you





know

 maybe

 the

 model

 is

 aware

 that

 it's





being

 evaluated

 and

 then

 when

 you

 deploy





it

 it's

 like

 oh

 now

 I

 can

 do

 what

 I





really

 want

 yeah

 a

 lot

 of

 the

 interest





in

 interability

 for

 alignment

 is





motivated

 from

 like

 we

 cannot

 draw

 good





conclusions

 always

 just

 from

 the





behavior

 of

 the

 model

 so

 I

 guess

 I

 could





give

 like

 an

 example

 um
</details>

>> 比如就说，你知道，也许有个新认识的人，你你知道，当你结交新朋友时，你确实想确保他们是个好人，对吧？一个你可以信任的人。嗯，尤其是，你知道，在你开始告诉他们你的秘密或类似的事情之前。而关于人的一件有趣的事情是，我们当然不可能随时知道其他人在想什么。嗯，但不知何故社会仍然在运转，对吧？所以，如果你交了个朋友，你知道，也许会发生一些情况，在那些情况下如果他们做了某个决定，那就意味着他们没有把你的最大利益放在心上。嗯你知道，也许他们必须付出代价为你保守秘密，而他们选择承担代价来帮助你。嗯你知道，正是从这样的事情中，我们建立起了对他人的信任，即使不知道他们内心在想什么，对吧？所以在适当的情境下，人们的行为某种程度上揭示了他们的品格。

<details><summary>Original English</summary>
>> so

 let's

 say

 like

 you

 know

 maybe

 there's





some

 new

 person

 you

 you

 know,

 when

 you





make

 a

 new

 friend,

 you

 do

 want

 to

 make





sure

 they're

 a

 good

 person,

 right?





Someone

 you

 can

 trust.

 Um,

 especially,





you

 know,

 before

 you

 start

 telling

 them





your

 secrets

 or

 things

 like

 this.

 And

 an





interesting

 thing

 about

 people

 is

 like





we

 of

 course

 cannot

 know

 what

 other





people

 are

 thinking

 at

 any

 time.

 Um,

 but





somehow

 society

 still

 works,

 right?

 So,





if

 you

 make

 a

 friend,

 you

 know,

 maybe





situations

 happen

 where

 like

 if

 they

 had





taken

 a

 certain

 decision,

 it

 would

 mean





that

 they

 don't

 have

 your

 best

 interest





in

 mind.

 um

 you

 know

 maybe

 they

 they





have

 to

 you

 know

 protect

 your

 secret

 at





cost

 to

 them

 and

 they

 choose

 to

 like





take

 the

 cost

 to

 help

 you

 um

 and

 you





know

 from

 events

 like

 this

 that's

 how

 we





build

 trust

 in

 other

 human

 beings

 even





without

 knowing

 what

 they're

 thinking





internally

 right

 so

 like

 people's





actions

 sort

 of

 reveal

 their

 character





in

 the

 right

 situations
</details>

>> 你知道，对齐在某种程度上很相似，对于这些语言模型或任何 AI 系统，建立对它们信任的一种方法是在特定情况下测试它们的行为，在那些情况下比如你知道，如果它们做或不做某个决定，就会告诉我们它是好是坏，它们是具有好的还是坏的品格，当然你可以从中获得很多证据。然而与人不同的是，对吧，这些模型运行在某人的——你知道，外面的某台计算机上，对吧？你知道原则上我们可以检查进入到某个输出中的每一次计算。与人不同的是，你知道我们部署了——你知道，数百万份模型副本，人们付钱让模型做各种各样的事情，我们并不总是知道使用这些模型的人的意图是什么。

<details><summary>Original English</summary>
>> you

 know

 alignment

 is

 somewhat

 similar





where

 like

 with

 these

 language

 models

 or





any

 AI

 system

 one

 way

 to

 develop

 trust





in

 them

 is

 to

 like

 test

 their

 behavior





in

 cases

 where

 like

 you

 know

 if

 they





took

 a

 certain

 decision

 or

 not

 it

 would





tell

 us

 if

 it's

 good

 or

 bad

 if

 they

 have





good

 or

 bad

 character

 and

 certainly

 you





can

 get

 a

 lot

 of

 evidence

 from

 this.

 Now





unlike

 people

 right

 these

 models

 run

 on





someone's

 you

 know

 some

 computer

 out





there

 right

 you

 know

 in

 principle

 we

 can





check

 every

 computation

 that

 went

 into





some

 output

 unlike

 people

 you

 know

 we





deploy

 you

 know

 millions

 of

 copies

 of

 a





model

 people

 pay

 for

 models

 to

 do

 all





sorts

 of

 stuff

 we

 don't

 always

 know

 what





you

 know

 what

 the

 intentions

 of

 people





using

 these

 models

 are
</details>

>> 嗯，所以这当然与雇用人类员工非常不同，对吧，在那里你有一些基准信任，即好吧，即使他们变坏了，他们可能也无法造成那么大的破坏。是的。所以我认为，鉴于涉及的风险大不相同，而且监控语言模型的内部要容易得多，可解释性是合理的。原则上如果我们只知道该找什么，我们就能找到它。我们不需要做任何疯狂的事情来弄清楚“哦，这个矩阵乘法的结果是什么”，对吧？

<details><summary>Original English</summary>
>> um

 so

 it's

 of

 course

 quite

 different





from

 having

 like

 a

 human

 employee

 right





where

 where

 you

 have

 some

 baseline

 trust





that

 okay

 even

 if

 they're

 like

 bad

 they





probably

 can't

 do

 that

 much

 damage.





Yeah.

 So

 I

 think

 interpability

 makes





sense

 given

 that

 the

 stakes

 are

 quite





different

 and

 also

 like

 it's

 much

 easier





to

 monitor

 the

 internals

 of

 a

 language





model.

 In

 principle

 if

 we

 just

 knew

 what





to

 look

 for

 we

 could

 find

 it.

 We

 don't





have

 to

 like

 do

 anything

 crazy

 to

 figure





out

 oh

 what

 was

 this

 matrix





multiplication

 result

 right?
</details>

>> 你能不能再具体阐述一下，当你说比如当我们知道该找什么时，我们现在具体在寻找什么？

<details><summary>Original English</summary>
>> Can

 you

 just

 elaborate

 a

 little

 bit

 on





when

 you

 say

 like

 when

 we

 know

 what

 to





look

 for

 what

 specific

 are

 we

 like





looking

 for

 now?
</details>

我想你知道，在可解释性得到解决的世界里……

<details><summary>Original English</summary>
So

 I

 guess

 you

 know

 you





know

 in

 the

 world

 where

 interpability

 is





solved
</details>

>> 也许我们知道，好的，你知道如果模型内部表征中的这个向量指向这个方向……

<details><summary>Original English</summary>
>> maybe

 we

 know

 that

 okay

 you

 know

 if

 this





vector

 inside

 the

 model's

 internal





representation

 is

 pointing

 in

 this





direction
</details>

>> 我们就知道它正打算做坏事，你知道类似这样的事情。如果我们知道这一点，我们直接检查就行了，对吧？我们不需要做任何疯狂的事情。嗯，而你知道，即使对人类来说，如果我们弄清楚了大脑是如何运作的，并且我们能搞清楚“哦，比如如果……”这个人就要开始奔跑了。

<details><summary>Original English</summary>
>> we

 know

 it's

 planning

 to

 do

 something





bad

 you

 know

 something

 like

 this

 if

 we





knew

 this

 we

 would

 just

 check

 right

 we





don't

 need

 to

 do

 anything

 crazy

 um





whereas

 you

 know

 even

 with

 a

 human

 being





we

 figured

 out

 how

 the

 brain

 works

 and





we

 could

 figure

 out

 oh

 like

 this

 person





is

 going

 to

 start

 running

 if
</details>

<!-- chunk 3/7 -->

这个神经元就在他们的大脑中被激活了。实际上，我们不可能，你知道的，往一个人的大脑里植入一个电极去把这弄清楚，对吧？这是完全不一样的。当然，人类毕竟是人类，我们不可能像对待在计算机上运行的东西那样去对待人类。

<details><summary>Original English</summary>
this neuron in their brain lights up. This is like practically we're not going to be able to, you know, insert a electrode in a person's brain to figure this out, right? It's quite different. And of course, yeah, like humans are humans. It's like we're not going to treat them the same way we treat something that runs on a computer.
</details>

>> 不，确实如此。而且听起来正因如此，在模型上做这件事比在人类身上要容易得多，因为在模型里你会有成千上万个副本，然后你可以对模型进行解剖。

<details><summary>Original English</summary>
>> No. Exactly. And it sounds like because of that it's easier to do that on models instead of humans because in models you have like you know thousands of copies and then you can kind of dissect a a model.
</details>

>> 是的，差不多是这样。如果也许你弄明白了其中一个，那就能解决很多问题，对吧？如果你能逆向工程一个模型的话。明白了。

<details><summary>Original English</summary>
>> Yeah. Sort of. If maybe if you figure out one of them that solves a lot of problems, right? If if you can reverse engineer one model. Got it.
</details>

### 可解释性研究的不同学派与稀疏自编码器

>> 回到一般的研究上，Anthropic 在那篇论文中所做的工作，据我理解，与可解释性研究中的传统方法并没有太大不同，那种方法被称为稀疏自编码器（SAE）。在我看来，这似乎就是进行这类研究的一般逻辑，也就是正如你所说的，你找到一个方向，你改变一些东西，然后你观察行为是如何变化的。基于这个背景，我想知道你是否能为我们梳理一下这个领域中不同的思维流派。

<details><summary>Original English</summary>
>> Uh moving back to kind of like the general uh research, what Enthropic has done in that paper as I understand is not that different from kind of like the traditions uh in interpretability research which is called sparse autoenccoder SAPE. That seems to me like uh kind of the general logic of doing this kind of research which is as you said you find a direction you change something and you see like how behaviors change and based on that context I'm wondering if you can just break it break down the different schools of thoughts uh in this field for us.
</details>

>> 好的，我想大致解释一下稀疏自编码器的用途可能会很有用。任何有机器学习背景的人都会听说过自编码器，其核心思想是，存在某种对象，比如可能是一张图像，可能是一段文本，你想训练一个模型，首先将这个复杂的输入转换为一个简单的向量，就像一串数字列表，然后再将它转换回输入。所以这就是为什么它被称为自编码。

<details><summary>Original English</summary>
>> Yeah I I guess it would be useful to like broadly explain what a sparse autoenccoder is for. Anyone with some ML background will have heard of autoenccoders where the idea is um there's some some kind of object like you know maybe it's an image maybe it's like a paragraph of text um and you would like to train a model that first converts this complicated input into a simple vector like just a list of numbers and then converts it back to the input. Um, so that's why it's called autoenccoding.
</details>

>> 这里的理念是，如果你训练一个模型来做这件事，你就能为给它的任何奇怪输入获得一个非常漂亮的向量表示。所以你知道，如果你能将所有的图像都转换为向量，那么做相似度搜索之类的就会更容易。

<details><summary>Original English</summary>
>> And the idea is if you train a model to do this, you get this nice vector representation of any weird input you give it. Um, so you know, if if you can convert all your images into vectors, then it's easier to do like similarity search.
</details>

>> 对，大体上就是这个思路。向量是对该事物的一种更好的表示。

<details><summary>Original English</summary>
>> Yeah, that that's sort of the idea. The vector is a nicer representation of the thing.
</details>

>> 自编码器是一个经典概念。在可解释性领域，当时的想法是，好，我们将提取模型中的所有这些隐藏表示。这些隐藏表示就像大型语言模型第 20 层中的向量一样。我们将训练一个自编码器，把这种表示转换为更干净的东西供我们研究。所以理念是，也许我们可以将其转换为一个数字列表，其中每个数字都代表一个具体、明确的事物。比如说，如果文本是英文，这个数字就是 1，否则就是 0；如果模型在谈论火箭，这个数字就是 1，否则就是 0。诸如此类。因此，稀疏自编码器就是将这设定为一个技术问题的一种方式，使得当我们将模型的表示输入进去时，最终能得到一个干净的数字列表。是的。我认为这里的好处在于，好吧，如果我们只有一串数字，其中某些数字代表模型的行为不良或者说没有对齐，我们只要想办法把那个数字设为零就行了。然而在实践中，情况极其混乱。事情并没有像我们希望的那样干净利落。

<details><summary>Original English</summary>
>> Um, and so autoenccoders are a classic concept. Uh, in interpretability, the idea was like, okay, we'll take all these hidden representations in the model. So these are just like vectors in like layer 20 of a big language model. Um and we'll train an autoenccoder which converts this representation into something cleaner for us to study. So the idea is you know maybe we could convert this into a list of numbers where each number means a specific clear thing. We're like you know this number is one if the text is in English and zero otherwise. It's one if the model is talking about rockets and zero otherwise. This kind of thing. So sparse autoenccoders were like a way to set this up as a technical problem such that we would end up with a clean list of numbers when we feed in a model uh a model's representations. Yeah. And I think the nice thing here was like okay if we just have a list of numbers some of those numbers will mean the model is behaving badly or it's like misaligned and we'll just figure out to you know set that number to zero. Uh in practice it's like extremely messy. Um and like yeah things things don't work out as cleanly as we would like
</details>

>> 也就是说，这些数字还不够干净，无法……

<details><summary>Original English</summary>
>> as in the numbers are not clean enough for
</details>

>> 是的，它们仍然不代表单一的事物。而且这也取决于你在什么数据上训练稀疏自编码器，即使你在相同的数据上训练两个不同的稀疏自编码器，你也会得到不同的结果。并且它们并没有捕捉到正在发生的一切，所以它并不是原始模型的完美表示。

<details><summary>Original English</summary>
>> yeah they still don't mean like one thing um and also depends on what data you train the sparse autoenccoder on even if you train two different spars auto encoders on the same data you get like different results um and they don't capture everything that's going on so it's not a perfect representation of the original models
</details>

>> 我觉得理解机器如何思考的一个本质问题在于，它并不是真的用自然语言来思考。所以这看起来有点像一个相关的问题……

<details><summary>Original English</summary>
>> I feel like one of the essential problem with understanding how a machine sinks is that it RA than really think in natural language. So it seems like it's kind of like a related
</details>

>> 也就是你必须把机器的思考翻译成浅白易懂的语言。是的，而且很多论文现在似乎已经在这么做了，但你似乎在指出，这其中并不存在一对一的对应关系。我认为原则上它可以是……你知道，稀疏自编码器确实有其用途，现在也有其他方法基本上是在尝试将模型内部的数字列表翻译成自然语言，它们可以极其有用，只是看起来它们无法一蹴而就地解决我们所有的问题。

<details><summary>Original English</summary>
>> issue which is that you have to translate uh the thinking of a machine into a plain language. Yes. Uh and a lot of the paper seems to be already been doing that now but you seem to be suggesting that there's no like onetoone correlations. I think in principle it could be you know it is you know sparse auto encoders do have their uses and there are other approaches now that also like basically try to translate you know list of numbers to natural language inside a model um and they can be extremely useful it just doesn't seem like they solve all our problems in one go
</details>

>> 明白了。那么在看到情况如此混乱之后，人们都做了些什么呢？

<details><summary>Original English</summary>
>> it so what have people done looking at seeing you know how messy it is
</details>

### 可解释性的两种哲学：规模化目标与因果干预

>> 是的，所以我想说，在可解释性研究中大致存在两种哲学，它们在一定程度上解释了人们为什么会这么做。

<details><summary>Original English</summary>
>> yeah so I guess I would say there's broadly like two philosophies of research in interp that sort of explain why people did this.
</details>

>> 其中之一是，我们从机器学习中吸取教训……

<details><summary>Original English</summary>
>> So one of them is like we take the lesson from machine learning
</details>

>> 只要你选对了目标，并针对该目标扩展出一个真正庞大的模型，你就能得到你想要的东西。比如对于语言生成来说，这个目标就是下一个标记预测。

<details><summary>Original English</summary>
>> that as long as you pick the right objective and you scale up a really big model on that objective you'll get what you want. So like for language generation this was next token prediction.
</details>

>> 你只需要挑选正确的目标来进行训练，就能获得一个非常优秀且有用的模型。所以他们正在为可解释性寻找这样一个目标。而稀疏自编码器就是这方面的一次尝试迭代，那里的想法是，好吧，我们拿来一个混乱的表示，我们的目标是生成一个干净的数字列表，这里有稀疏性损失等等。这看起来似乎并不太是对的目标，或者说，它并没有完全捕捉到我们所关心的全部内容。这个方向上近期的迭代之一，同样来自 Anthropic，被称为自然语言自编码器。那里的理念是，它仍然是一个自编码器，但不是将混乱的数字列表转换为干净的数字列表，而是直接将混乱的数字列表转换为自然语言，然后再将自然语言转换回来，并进行大量的强化学习训练来达成这件事。这里的好处是，我们直接在寻找我们能够读懂的东西。但问题再次出现，好吧，你怎么去信任它？随着训练的进行，模型开始说一些有些奇怪的内容，我们不确定它是否具有自己内部的某种语言还是怎么回事。但不管怎样，那一脉可解释性研究的整体哲学就是：我们会训练一个非常庞大的模型来为我们解决问题，我们只需要挑选出正确的问题就行了。[清嗓子]

<details><summary>Original English</summary>
>> You just had to pick the right thing to train on and you would get a really good and useful model. And so they're looking for that objective for interpretability. And sparse autoenccoders were one iteration of this where the idea was okay you know we take a you know messy representation and our objective is to create a clean list of numbers um and this like there's sparsity loss and so on. It seems like it wasn't quite the right objective or like you know it doesn't fully capture everything we care about. One of the recent iterations in this direction also from anthropic is called natural language autoenccoders. And there the idea is it's still an autoenccoder but instead of converting messy list of numbers to clean list of numbers, we convert messy list of numbers into natural language directly and then convert the natural language back and then do like extensive reinforcement learning training to to do this thing. The nice thing is here that you know we're we're directly looking for something we can read. But again the problem is like okay how do you trust this? uh you know as you train the model starts saying somewhat weird stuff and we're not sure if it's like you know it has its own internal language or what but anyways yeah the whole philosophy of that line of interpility research is like we'll train a really big model to solve the problem for us we just have to pick the right problem [clears throat]
</details>

>> 另一方面的思路是——比如我来自斯坦福大学 Chris Potts 实验室的背景，我们发明了这个被称为因果抽象的框架。那里的想法是，给定关于模型内部推理步骤的某种假设，我们可以通过对模型进行干预来测试这个假设。假设你认为模型在向量空间中有某个方向代表它是否在用英语交流。如果你提出这样的主张，我就可以通过加上该向量或减去该向量来直接测试它，对吧，然后看看会发生什么。

<details><summary>Original English</summary>
>> the other side of things is like so the background I come from in Stanford Chris Pots's lab we adakus guy invented this framework called causal abstraction and And the idea there is like you know given some hypothesis about the internal reasoning steps of a model we can test this hypothesis using interventions on the model. So let's say you think uh you know a model has some direction in vector space that represents whether it's talking in English or not. If you make a claim like this I can just test it by like adding that vector or subtracting that vector right and then see what happens.
</details>

>> 我们拥有这样一个假设检验框架。许多人在许多不同的地方几乎同时发现了这一点，即对模型进行干预是检验关于它的假设的一种方式。而且好的地方在于，只要你选择了正确的假设，你就可以在一定程度上信任这个结果。

<details><summary>Original English</summary>
>> We have this hypothesis testing framework. A lot of people figured this out at the same time at many different places where like doing interventions on a model is a way to test hypothesis about it. Um and nice thing is you can sort of trust the results of this given you pick right hypothesis.
</details>

>> 是的。有哪些假设呢？比如你该如何选择正确的假设？

<details><summary>Original English</summary>
>> Yeah. What are some of the hypothesis like how do you pick the right hypothesis?
</details>

>> 是的。所以我认为这种方法的一个明显局限性一直在于，我们必须去研究非常受限的事物。所以也许我们可以提出关于模型如何进行加法的假设……

<details><summary>Original English</summary>
>> Yeah. So I would say definitely a limitation of this approach has been we have to study really constrained things. So maybe we can like come up with hypothesis for how model does addition
</details>

>> 或者是模型如何处理语言学方面的内容，比如单数与复数，主谓一致等这类非常受限的内容。我们可以对此进行测试，并弄清楚很多东西；实际上，我们可以准确找出哪个注意力头、哪个 MLP 正在做什么……

<details><summary>Original English</summary>
>> or how a model does like linguistic stuff like singular versus plural you know subjectverb agreement this kind of thing very constrained stuff and we can test this and like figure out a lot actually we can figure out exactly what attention head what MLP is doing what
</details>

>> 但我们关心的许多问题并不那么简单，比如你想知道，模型是否……

<details><summary>Original English</summary>
>> but like a lot of the questions we care about are not so simple like if if you want to know oh is the model
</details>

>> 正在考虑对用户撒谎或类似的事情，在这样的框架下如何设置实验并不清楚。

<details><summary>Original English</summary>
>> uh thinking about lying to the user or something like this it's not clear how to set up an experiment like this in this framework
</details>

>> 是的，所以目前这个方向上的许多进展一直是在尝试将提出假设的手动步骤自动化。因此，也许一个语言模型智能体会被赋予用于进行干预的工具。这基本上就像是在做人类会做的事情，但我们训练了一个模型来执行它。所以

<details><summary>Original English</summary>
>> yeah so a lot of The progress in this direction now has been trying to automate the manual step of coming up with hypothesis. So maybe a language model agent gets tools which are for like doing interventions. It's basically like doing what a human would do but we train a model to do it. So
</details>

<!-- chunk 4/7 -->

我想说这是两种不同的哲学，我看到可解释性领域的研究正沿着这两个方向分化。

<details><summary>Original English</summary>
I would say these are like sort of two different philosophies and I see stuff diverging in interpity along these two.
</details>

>> 我明白了，明白了。那么智能体提出的假设通常会比人类更好吗？或者说，与人类相比，它们会从任何不同的视角或方向提出假设吗？

<details><summary>Original English</summary>
>> I see. I see. How does so does an agent usually come up with better hypothesis than humans or are they do they come up with hypothesis in any like different perspectives or directions compared to humans?
</details>

>> 是的，我认为目前阶段还为时尚早。我还没有遇到过……我还没有经历过那种“噢，这个语言模型显然比我有更好的想法来进行这项测试”的时刻。好的，

<details><summary>Original English</summary>
>> Yeah, I think things are still early. I haven't seen like a I haven't had a moment where I'm like oh this yeah the language model clearly had a better idea than me to test on this. Okay,
</details>

>> 也许其他人遇到过，因为我现在作为一名博士生，也没有足够的算力来运行很多这类东西。算力是用在什么地方的？

<details><summary>Original English</summary>
>> may maybe other people have cuz I also don't have the compute to run a lot of this stuff currently right as a PhD student. What does the compute need for?
</details>

>> 我认为问题在于，随着领域的发展，可解释性研究将需要多得多的算力。所以我认为关于可解释性，过去一件非常美好的事情就是……

<details><summary>Original English</summary>
>> I think that's the problem as the field progresses interp will need a lot more compute. So I think a really wonderful thing about interp has been like
</details>

>> 会有偶遇的高中生涉足可解释性研究。我收到过……我收到过一些湾区高中生发来的邮件，他们会说“噢，我想……我在笔记本电脑上用 GPD2 运行了这个实验，我觉得……是的，我想展示给你看。”

<details><summary>Original English</summary>
>> there are random high school students who get into interpity research. I get like I get emails from random Bay Area high school students who are like oh I want to I ran this experiment on GPD2 on my laptop and I thought here's yeah I want to show you.
</details>

>> 哇。是的。

<details><summary>Original English</summary>
>> Wow. Yeah.
</details>

>> 这可能是目前人工智能领域为数不多你还能做这类事情的方向之一，因为我们连真正很小的模型都还不理解，对吧。嗯……

<details><summary>Original English</summary>
>> This is like this maybe one of the few things in AI where you can do stuff like this right now because we don't understand really small models right. Um
</details>

>> 但如果一个，你知道的，如果一个孩子想进入强化学习领域，

<details><summary>Original English</summary>
>> but if a you know if a kid wants to get into reinforcement learning
</details>

>> 他们就必须购买算力，

<details><summary>Original English</summary>
>> they got to buy compute
</details>

>> 才能做任何事情。

<details><summary>Original English</summary>
>> to do anything.
</details>

>> 明白了。明白了。那确实很……

<details><summary>Original English</summary>
>> Got it. Got it. That's really
</details>

### 从语言学到计算模型

>> 不过我确实认为可解释性正在朝这个方向改变。我想多聊聊你是怎么进入这个领域的，因为你……呃，你说过你大学时是一名语言学学生，而且你有点看到了语言与语言模型之间的这种联系。跟我多讲讲这种联系，特别是，我觉得当我听说可解释性研究时，很多人会用大脑打比方，比如他们会用[咳痰]神经科学来做类比，他们觉得自己是在做生物学，在解剖一个语言模型，但你似乎是从，你知道的，从一个不同的角度切入的。

<details><summary>Original English</summary>
>> I do think interpret is changing though in this way. I wanted to talk a little bit more about how you got into this because you uh you said that you were a linguistic student and during college and you kind of saw this connection between language and language models and tell me more about that connection and specifically like I feel like when I hear about interb research a lot of people make the analogy of a brain like they make the [clears throat] neuroscience analogy they think they're doing like biology and dissect a language model but you seem to be taken you know, from like a different perspective.
</details>

>> 是的。就我的背景而言，嗯，是的，我从初中左右就一直对语言很感兴趣。嗯，当然，我的家庭是一个多语言家庭。嗯，我们在家里说印地语。嗯，在，你知道的，在某个时期我有一群讲普通话的朋友，我当时就非常好奇，比如这种语言有什么不同？呃，所有诸如此类的事情。所以，我一直都超级喜欢语言，然后我在乔治城大学开始了本科阶段的学习。嗯，他们有一个非常优秀的语言学系。你知道在那个时候，计算语言学正开始成为一门显学。嗯，当时人们在，你知道的，训练能够写文章的 LSTM。他们用莎士比亚的作品来训练它们，而且当时有各种有趣的演示，某种程度上像是把语言学的思想与计算机科学结合起来，比如当时的人工智能进展。嗯，所以我想，好吧，也许如果我做这个方向，我就能将自己的热情与某种可能对社会切实有用的东西结合起来，对吧？

<details><summary>Original English</summary>
>> Yeah. So, for my background, um, yeah, I was always into languages since like middle school or something. Um, of course, my my family is multilingual. Um, we we spoke Hindi at home. Um, at, you know, at some point I had a bunch of friends who spoke Mandarin and I was so interested in like how is this language different? Uh, all this kind of stuff. So, I was always super into languages and then I started undergrad at Georgetown University. Um and they have an excellent linguistics department. You know at that time computational linguistics was starting to be a thing. Um where people were you know training you know LSTMs that produce essays. They train them on Shakespeare and like there are all these interesting demos sort of of like I combining ideas from linguistics and computer science like AI progress at the time. Um so I thought okay maybe if I work on this I can combine sort of my passions and like something that might be practically useful for society right
</details>

>> 那是什么样子的？计算语言学看起来是什么样的？

<details><summary>Original English</summary>
>> what does that look like what is a computational linguistic look like
</details>

>> 它经历了很大的演变，在当时，计算语言学存在的一种方式就像是：好吧，我们想做语言学研究，对吧？我们想要，你知道的，寻找语言中的结构，我们想要寻找比如随着时间的推移语言是如何变化的等等。通过人工来做这些是极其困难的，因为有太多的数据，对吧？

<details><summary>Original English</summary>
>> it evolved a lot sort of at the time one of the ways computational linguistics was a thing was like okay we want to do linguistics right we want to you know find structure in language we want to find like over time how does language change and so on this is extremely difficult to do manually because there's so much data, right?
</details>

>> 所以，计算语言学的其中一个思路就是，好吧，我们来做语言学，但我们用计算机来做。

<details><summary>Original English</summary>
>> So, one of the ideas in computational linguistics was like, okay, we'll do linguistics, but we'll use a computer to do it.
</details>

>> 嗯，那是其中一方面。另一类事情就是，你知道的，就像现在我们有聊天机器人之类的东西。在某个时期，人们想要训练或者做出某种能够像人类一样与你交谈的计算机程序，对吧？并且能接收你的指令。而如果你没有任何基础可以着手，这是一个极其庞大的问题，对吧？你甚至该如何入手？呃，所以当时的一个想法就是，好吧，语言学告诉了我们人类是如何处理和生成语言的，呃，从他们如何处理声音，到他们如何将声音组合成意义单元，再到他们如何将意义单元组合成合乎语法的句子。所以当时的思路就是，我们直接照搬我们认为大脑中存在的整套语言结构，并尝试编写一个做同样事情的计算机程序，因为面对这么大的一个问题，你还能怎么入手呢，对吧？那么在你自己的研究中，当谈到语言模型内部发生的事情时，有没有什么让你感到惊讶的？比如当你刚开始你的研究时，有没有什么极其有趣的事情？

<details><summary>Original English</summary>
>> Um, and that was one of the things. The other set of things was like, you know, just like now we have chatb and stuff. At some point, people wanted to train or like have some like computer program that could talk to you like a human, right? And take commands from you. And like this is such a huge problem if you have nothing to start with, right? Like how do you even approach it? Uh so one of the ideas back then was like okay linguistics tells us how humans process and produce language uh down from like how they process sounds, how they combine sounds into units of meaning, how they combine units of meaning into grammatical sentences. So the idea was we'll just copy the whole like linguistic structure that's in the brain that we think is there and try to write a computer program that does the same thing because how else can you approach such a big problem, right? So in your own research, has there been anything that surprised you when it comes to what's going on inside a language model? Like when you just started uh your research, has there been anything that's super interesting?
</details>

>> 本科时，我绝对处于第一种模式，那就是我致力于解决一个非常微小的问题，嗯，它以某种方式与语言学相关，然后我试图让一个，你知道的，让一个模型学会解决那个问题。所以对我来说，那就是比如对于印度语系语言，我想要学习如何将句子解析成树状结构，你知道的，你可能见过像句法树那样的东西，是的，就像你知道的，单词是如何组合成某种更大的结构的，

<details><summary>Original English</summary>
>> In undergrad, I I was definitely in that first mode of like I work on a really tiny problem um that's like somehow linguistics related and I try to make a you know like a model learn that problem. So for me that was like oh for Indian languages I want to learn how to parse sentences into like tree structures you know you might have seen like syntax trees yeah just like you know how how the words go together into some bigger structure
</details>

>> 比如在某种特定语言中。

<details><summary>Original English</summary>
>> like in a certain language
</details>

>> 是的，在一种特定的语言中，这是一个受到非常严格约束的问题，对吧？

<details><summary>Original English</summary>
>> yeah in a specific language it's a really constrained problem right
</details>

>> 那是被认为属于微小的问题吗？听起来好像……

<details><summary>Original English</summary>
>> is that something that's considered as a small problem like it just seems like
</details>

>> 它确实非常难，但是想想看，好吧，那是我们必须做的范围，我们不可能做所有的语言，我们不可能做那种语言里的所有事情。

<details><summary>Original English</summary>
>> it is really hard but like think about like okay that's the scope we have to do we cannot do all languages we cannot do like everything in the language
</details>

>> 而且当然，当时就像……我不需要凭空发明任何东西。当时的那些技术是已经存在的。只是说……

<details><summary>Original English</summary>
>> and of Of course, there's like I didn't have to come up with anything. There's like the techniques existed back then. It was just
</details>

>> 就像我作为一个本科生，当时是在手动标注数据。比如我有一份印地语句子列表，

<details><summary>Original English</summary>
>> like for me as an undergrad, I was annotating data manually. Like I had a list of Hindi sentences
</details>

>> 然后我用手工把树状结构写出来。我花了几百个小时做这件事，然后我会训练一个模型来预测……

<details><summary>Original English</summary>
>> and I like wrote out the the tree manually. I spent hundreds of hours doing this and then I would train a model that like predicts
</details>

>> 你知道的，我创建的那个数据集。

<details><summary>Original English</summary>
>> you know the data set I created.
</details>

>> 噢，哇。

<details><summary>Original English</summary>
>> Oh wow.
</details>

>> 嗯，而这在计算语言学领域就是几十年来的做事模式。

<details><summary>Original English</summary>
>> Um and this was like the mode of doing things for like decades in computational linguistics.
</details>

>> 我明白了。

<details><summary>Original English</summary>
>> I see.
</details>

### 模型规模与 Scaling Law

>> 是的。我们没有别的事情可做。所以对我来说，发生的一件大事是，嗯，当时我在乔治城大学所在的实验室在做一个语义解析任务，嗯，我的导师是内森·施奈德（Nathan Schneider）。他让不同的学生针对同一个任务做不同的语言。于是我们为了训练模型搞了这么一套复杂的架构。我们会拿一个 BERT，在上面接一个 LSTM，再在上面接一个 CRF。我不知道……今天这些词好像都不相关了，但在当时那是某种你会去训练的复杂东西，

<details><summary>Original English</summary>
>> Yeah. We didn't have anything else to do. So for me the big thing that happened was um there was one like semantic parsing task that the lab I was in at Georgetown worked on um and my adviser was Nathan Schneider. He had like different students doing different languages on the same task. And so we had this like complicated setup for training a model. We would take a bird we would stick an LSTM on it. We stick a CRF on it. I don't like none of these words are like relevant today but back then there was some complicated thing you would train
</details>

>> 这套东西表现还算过得去，比如它能学会这项任务，达到大概 60%、70% 的准确率。有一天我冒出一个想法，比如如果我就直接用一个 BERT，但我用我们在当时能找到的最大的 BERT 呢？当时微软发布了一些更大的模型，然后就在最后微调一个线性投影层。所以没有任何复杂的东西，就只是在同一个任务上训练一个非常大的模型，

<details><summary>Original English</summary>
>> and this thing would do okay like it it would learn the task to like 60 70% accuracy. One day I had the thought of like what if I just take the like a bird but then I take like the biggest bird we can find then. So like Microsoft had released some larger models and then just fine-tune like a linear projection at the end. So none of the complicated stuff just train a really big model on the same task
</details>

>> 结果这东西一上手就达到了大概 80%、85% 的准确率。我跑的第一个实验，我没有……当时我就心想，哇，如果我直接用一个更大的模型，我们之前做的所有那些复杂的东西就完全没有必要了，

<details><summary>Original English</summary>
>> and this thing was like 80% 85% accuracy like off the bat. The first experiment I ran I didn't and I was like whoa if I just use a bigger model all this like complicated stuff we were doing before is like not necessary
</details>

>> 这大概是在 2022 年左右。我觉得那就是让我意识到“等等”的时刻，比如当时的模型仍然像……我还可以把它们放进我的笔记本电脑里，几个，你知道的，几十亿参数，我们在那个节点已经见过了，模型一直在变大，对吧？OpenAI 大约在那个时候发布了像 GPT-2 XL，

<details><summary>Original English</summary>
>> and this is like probably 2022 or something. I think that was the moment I was like wait like the models are still like I can fit them on my laptop a couple you know a couple billion parameters we'd seen at that point the models keep growing right open I released like GBD2 XL around that time
</details>

>> 然后微软有了更大的 DistilBERT，

<details><summary>Original English</summary>
>> and then Microsoft had the bigger distilberts
</details>

>> 所以如果你看这个趋势，就会觉得，好吧，

<details><summary>Original English</summary>
>> so if you looked at the trend it was like okay
</details>

>> 模型一直在变得越来越大，作为计算语言学家我们认为重要的所有这些任务，它们就这么被解决了，甚至不需要我们做任何特别的事情。

<details><summary>Original English</summary>
>> the models keep getting bigger all of these tasks that we think are important as computational linguists they're just going to be solved like without us doing anything special
</details>

>> 就像是你有点发现了规模扩展定律（Scaling）？

<details><summary>Original English</summary>
>> is like did you discover scaling kind of
</details>

>> 我想那大概是我第一次切实感受到“噢，原来这就是规模法则”的时候。当时规模法则的论文已经存在了，已经有好几篇了，

<details><summary>Original English</summary>
>> I think that was like the the time I felt like oh this is what a scaling law is. The scaling law paper existed by then. There were there were several of them
</details>

>> 但就针对我的事情而言，在那之前它并没有影响到我，在那之前我并没有去思考过它，

<details><summary>Original English</summary>
>> but like for my stuff it didn't it hadn't like affected me till then like I hadn't thought about it till then
</details>

>> 这大概是在我本科阶段进行了两三年的时候。所以你知道的，在那之前我很满足于做那些常规的项目。

<details><summary>Original English</summary>
>> and this was like two three years into my undergrad. So you know I was happy doing like standard projects until then.
</details>

>> 顺着这一点说，你在 2024 年发表了一篇关于 calls gym 的论文。发音是那样念对吗？是的。

<details><summary>Original English</summary>
>> To build on that you had a paper uh in 2024 on calls gym. Is that the correct way to pronounce it? Yeah.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

<!-- chunk 5/7 -->

那就像是一个用来测试语言模型在语言学任务中表现如何的基准。这个领域需要基准吗？

<details><summary>Original English</summary>
That's like a benchmark for testing how a language model performs in linguistic tasks. Does the field need benchmarks?
</details>

>> 是的。所以我认为大体上对于可解释性来说——如果你看人工智能其他领域的进展，比如说你想训练模型擅长翻译，或者像……我不知道，数学问题、数学竞赛题，你知道，我们有相关的基准，你可以在国际数学奥林匹克（IMO）试题或诸如此类的内容上运行它，

<details><summary>Original English</summary>
>> Yeah. So I would say in general for interpretability um so if you look at progress in other parts of AI let's say you want to train models to be good at translation or like I don't know math problems math limbad problems you know we have benchmarks for that you can run it on like IMO questions or stuff like this
</details>

>> 然后你只要……你知道，为了检查进展是否正在发生，你只需查看该基准上的分数。而在可解释性方面，我认为我们没有那种能告诉我们正朝着正确方向前进的明确基准，因为衡量进展非常困难。可解释性在很大程度上是关于……你知道，产生既能令人类满意又是真实的解释，

<details><summary>Original English</summary>
>> and you just you know to check if progress is happening you just check the score on this benchmark I think interpability we don't have like clear benchmarks that tell us that we're progressing in the right direction because it's really hard to measure measure progress. Um, a lot of interp is about like sat, you know, producing explanations that satisfy a human and are true
</details>

>> 而这两点都很难测试。

<details><summary>Original English</summary>
>> and both of those things are hard to test.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 所以我在那篇论文里的想法——当然我认为那篇论文是非常受限的。这是我读博期间的第一篇论文。那里的想法是：好吧，语言学特征……每个模型，即使是最小的模型，都必须追踪像单数、复数这类所有基本的语言学内容，它们必须存在于模型内部的某个地方。而一个好的可解释性测试方法就是看它能否找到与该语言学特征相对应的内部机制，

<details><summary>Original English</summary>
>> So my idea in that paper and of course I think it it that paper is very constrained. This is like my first PhD paper. Um the idea there was like okay linguistic features every model even the smallest model has to keep track of like singular plural all these basic linguistic things they have to be in there somewhere and a good testament interpability method is if it can find you know an internal mechanism that corresponds to that linguistic feature
</details>

>> 因为我们知道它肯定在某个地方。对于更复杂的推理步骤，做出这种断言要困难得多，

<details><summary>Original English</summary>
>> because we know it has to be there somewhere yeah it's harder to make this claim for more complex you know reasoning steps
</details>

>> 所以从小处着手更合理。

<details><summary>Original English</summary>
>> so it makes more sense to start small
</details>

>> 我觉得这是我能说得通的，同时也能结合我的语言学兴趣。

<details><summary>Original English</summary>
>> I think this is the thing I could justify and also combine my linguistic interest.
</details>

### 模型操纵与内部表征编辑

>> 是的。后来我和……在我的整个博士期间，我和我的朋友 Zen Junction 密切合作，

<details><summary>Original English</summary>
>> Yeah. Later on me and um so I worked super closely with my friend Zen Junction
</details>

>> 开展了各种类似的研究。我们做了一个关于转向（steering）的评估基准，也就是你的可解释性方法能否以一种干净的方式控制模型的输出，同时不损害其能力。

<details><summary>Original English</summary>
>> on uh all sorts of stuff like this throughout my PhD. We did an evaluation benchmark on steering which is like can your interpret method control the model's output in a in a clean way without harming its capabilities.
</details>

>> 在那里我们发现，所有的可解释性方法在操控模型方面都非常吃力。你能做的最好的事情就只是给模型输入提示词，

<details><summary>Original English</summary>
>> Um and there we found all the interpility methods really struggle to steer models. The best thing you can do is just prompt the model
</details>

>> 或者微调它。问题在于，我们现有的技术都不擅长控制模型的内部思维。

<details><summary>Original English</summary>
>> or fine-tune it. The problem is like none of our techniques are good at controlling the internal thoughts of a model.
</details>

>> 而且在实践中，如果你的模型表现不好，没有人会去编辑那些思维。他们只是用更好的数据训练一个新模型。

<details><summary>Original English</summary>
>> And in practice, if your model is doing something bad, no one goes and edits the thoughts. They like just train a new model on better data.
</details>

>> 理论上，你是可以编辑思维的，对吧？

<details><summary>Original English</summary>
>> Theoretically, you could edit the thoughts, right?
</details>

>> 我不确定你能否以鲁棒的方式做到这一点。这很有趣，因为大家会认为，一旦你弄清楚了某事物内部发生的情况，很自然的下一步就是想要改变它或编辑它，让它不再做那件坏事。有人尝试过这样做吗？也就是大家目前还在尝试编辑或者做出那种较小规模的改变吗——

<details><summary>Original English</summary>
>> I'm not sure you could do it like in a way that's robust. That's interesting because you would think that once you figure out what's going on inside something, the natural next step that you would want to do is to change that or edit that so that it doesn't do that bad thing. Uh has anyone attempted to do this? So like are people still attempting to edit or like making those smaller scale change
</details>

>> 比如直接编辑思维？是的，出于实际目的，可能有人看到过 Anthropic 部署 Golden Gate Claude 的情况，那是一个有趣的演示，他们使用转向向量让模型始终想着金门大桥。

<details><summary>Original English</summary>
>> like edit the thoughts directly? Yeah, for practical purposes might have seen Golden Gate Claude when Enthropic deployed it and that was like a fun demo where they used a steering vector to make the model always think about Golden Gate Bridge.
</details>

>> 我敢打赌，在实践中如果还有人在生产环境中使用转向向量，那也就是 Anthropic 了，因为他们说过类似——

<details><summary>Original English</summary>
>> I I would bet in practice if anyone is still using steering vectors in a production context, it would be anthropic because they've said like
</details>

>> “哦，当你询问涉及 AI 研究或生物风险等问题时，我们会使用分类器或转向向量来改变其输出。”所以他们可能在做诸如此类的事情。也许他们找到了让转向向量非常鲁棒的方法。

<details><summary>Original English</summary>
>> oh when when uh you ask fable like AI research or bioisk questions, we use a classifier or steering vectors to to change its output. Um so they they might be doing stuff like this. Maybe they figured out a way to make steering vectors very robust.
</details>

>> 在实践中，[清喉咙] 我们对学术界已知的转向向量技术所观察到的情况是，

<details><summary>Original English</summary>
>> In practice, [clears throat] what we've observed um with you know academically known steering vector techniques
</details>

>> 如果转向用力过猛，就会让模型在其他任务上表现变差。比如你针对金门大桥进行转向，它确实会谈论金门大桥，但随后在回答数学题等内容时就开始变得非常糟糕，

<details><summary>Original English</summary>
>> is like if you steer too hard it like makes the model bad at other stuff. So like if you steer for Golden Gate Bridge, sure it talks about Golden Gate Bridge, but then it starts becoming really bad at answering math questions and things like this
</details>

>> 表现出一种不可预测的方式。而如果你只是通过微调让它谈论金门大桥，你就能更轻易地[嗤鼻笑]避免这种情况。

<details><summary>Original English</summary>
>> uh in a way that's unpredictable. So, and like if you just fine-tuned it to talk about Golden Gate Bridge, you could avoid [snorts] this like much more easily.
</details>

>> 是的。鉴于此，我怀疑直接编辑思维是否是一种改变行为的鲁棒方式。

<details><summary>Original English</summary>
>> Yeah. Given that, I'm like doubtful that editing the thoughts directly is a robust way of of changing behavior.
</details>

>> 并且鉴于……如果这种方法流行不起来，那么可解释性研究人员就应该看看大家正在做的事情，并尝试找出如何将它们做得更好，或者系统地解释为什么那些方法行得通。

<details><summary>Original English</summary>
>> Um, and given that like, you know, if this is not going to catch on, then interability researchers should look at like the things people are doing and try to figure out how to do them better or explain why those things work systematically.
</details>

### 用户建模与行为审计

>> 明白了。很有意思。我在做这项调研时看到的另一个有趣的例子最近来自 Transluce，他们某种程度上展示了模型对自己正在与谁交谈会有某种猜测，并且——

<details><summary>Original English</summary>
>> Got it. Interesting. Uh, another interesting example that I saw while doing this research came from Trans Lewis recently where they kind of show that the models have some sort of guest as to who they're talking to and
</details>

>> 这也是因为那不一定与思维相关，对吧？或者说那也是这种传统的一部分吗？

<details><summary>Original English</summary>
>> like is that also because that's not necessarily relating to salts, right? Or is that also like part of this uh this tradition?
</details>

>> 呃，是的。交代一下背景，我在 Transluce 做过大约八个月的兼职。我和 Zen 密切合作。我度过了一段美好的时光。他们是一家非营利机构。他们从事有益于社会的人工智能研究，并且对其他公司部署的语言模型进行审计。

<details><summary>Original English</summary>
>> Uh, yes. So, for for context, I was at Transloose for like eight months part-time. Uh, and I worked closely with Zen. I had a great time. They're they're a nonprofit. Um they do like society helpful AI research um and like auditing for you know language models that other companies are deploying.
</details>

>> 我认为存在这样一个机构非常重要。

<details><summary>Original English</summary>
>> Um I think it's very important that something like this exists.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。所以我想说他们最近的一些研究——我在那里时我们研究的方向之一是用户建模，我们想要理解模型在内部对与之交谈的用户做出了什么样的推断。我们可以构建一些有趣的数据集来做可解释性分析，发现比如存在一种表征：当你谈论寿司时，模型会认为用户来自日本，诸如此类。但为可解释性构建这类数据集非常困难，仅仅是因为我们需要非常完美的成对数据集来进行干预，

<details><summary>Original English</summary>
>> Yeah. So I would say some of their recent research, one of the things we looked at when I was there was user modeling where we want to understand like what inferences does a model make about the user it's talking to internally and you know we could set up some interesting data sets where we could do interp and figure out that oh there's a representation of you know the model thinks the user is from Japan when you talk about sushi this kind of thing but like it's hard to set up data sets for this for interp um just because we need like a really perfect like paired data set to do interventions on
</details>

>> 有意思。是的。

<details><summary>Original English</summary>
>> interesting. Yeah.
</details>

>> 是的。我很喜欢他们在最近这项工作中所采用的非常偏行为学的方法。那是什么来着？就像他们有了 Claude Code，然后告诉它用户是 Amanda Askell 或者其他某个人，接着观察它的行为如何发生变化，

<details><summary>Original English</summary>
>> Yeah. I like that in this recent thing they took a very behavioral approach. Um and what was it it was like they had clawed code and they told it uh the user is like Amanda Ascal or like some other person and then they look at how the behavior changes
</details>

>> 仅仅从这一点你就能发现很多东西，对吧？比如，如果这个人是知名的 AI 安全研究员，模型就会非常谨慎，在做出断言时远比对普通人要谨慎得多。

<details><summary>Original English</summary>
>> and from just that you can figure out a lot right of like oh if the person is a known AI safety researcher the model is really careful like way more careful than it is with normal person when it's making claims.
</details>

>> 很有意思。而这并不……

<details><summary>Original English</summary>
>> Interesting. And this is not
</details>

>> 那就是我的理解。是的。这与你所说的你们最初的那个数据集有些不同。

<details><summary>Original English</summary>
>> that was my understanding. Yeah. And this is a little different from when you said the initial data set that you guys were
</details>

>> 是的。毕竟你不需要探查模型内部来进行这种研究，对吧？你只需给它输入不同的内容，然后观察其行为如何改变，

<details><summary>Original English</summary>
>> Yeah. Well, you don't need to look inside the model to to do this kind of study, right? You just you feed it a different input and then see how the behavior changes,
</details>

>> 对吧？对。

<details><summary>Original English</summary>
>> right? Right.
</details>

>> Transluce 还有其他关于审计语言模型的工作。

<details><summary>Original English</summary>
>> Um, Transluc also had other work on like auditing language models.
</details>

>> 让它们说出奇怪的话。是的。比如——

<details><summary>Original English</summary>
>> Um, getting them to say weird stuff. Yeah. Like
</details>

>> 最奇怪的话是什么？

<details><summary>Original English</summary>
>> what are the weirdest stuff that
</details>

>> 我非常建议大家去看一看。它叫做 Weird Chat。有一些非常奇怪的内容，我都觉得不太好意思说出口。真有意思。

<details><summary>Original English</summary>
>> I I think I highly suggest people to look at it. It's called weird chat. There's some really weird things that I cannot I feel uncomfortable talking about. That's funny.
</details>

>> 但是，是的，他们发现了各种各样奇怪的事情。

<details><summary>Original English</summary>
>> But uh yeah, they found all sorts of weird things.
</details>

>> 这些都是通常聊天机器人不会说的事情，

<details><summary>Original English</summary>
>> And these are things that normally like a chatbot wouldn't say
</details>

>> 或者你不会希望它说的，但你可以构造出看似正常的情境让它说出奇怪的内容。

<details><summary>Original English</summary>
>> or you wouldn't want it to say, but like you can create normal looking situations where it says weird stuff.
</details>

>> 哦，所以并不是……即使我只是一个普通用户，我仍然能通过提示让它说出来。

<details><summary>Original English</summary>
>> Oh, so isn't if I'm just like a regular user, I can still prompt it to say.
</details>

>> 是的。这甚至都不属于越狱那一类的手段。

<details><summary>Original English</summary>
>> Yeah. It's not even a jailbreak kind of thing.
</details>

>> 哦，那真挺有意思的。是的。是的。

<details><summary>Original English</summary>
>> Oh, that's really interesting. Yeah. Yeah.
</details>

>> 是的。他们是通过自动化的提示词搜索发现这些的，而不需要进行某种疯狂的可解释性处理。

<details><summary>Original English</summary>
>> Yeah. And they found that by like automatically doing prompt search, not having to do some crazy interp progress.
</details>

>> 所以，是的。我们是如何走到这一步的？

<details><summary>Original English</summary>
>> So, yeah. How do we get to this point?
</details>

>> 是的。是的。而我们正在试图理解它为什么会那样做。这依然算是一种切入角度。

<details><summary>Original English</summary>
>> Yeah. Yeah. and we're trying to understand why it does that. That's kind of still the angle.
</details>

>> 我依然……是的，有很多事情你无需理解其背后的全部原因也能弄明白，

<details><summary>Original English</summary>
>> I still Yeah, there's a lot of things you can figure out without understanding the whole like why,
</details>

>> 对吧？

<details><summary>Original English</summary>
>> right?
</details>

>> 比如通过自动搜索等手段找出所有这些奇怪的行为。但某种意义上这些不全都是边缘案例吗？因为这有点像在挑选个例，有大量的案例研究，就像……我想整个领域某种程度上都有很多案例研究，正如我们刚才讨论的那样，这似乎有些主观，因为我们有点像在指定……

<details><summary>Original English</summary>
>> Um like find all these weird behaviors using automatic search and things like this. But would it not all be like edge cases in a in a sense because you're kind of like cherrypicking there's a lot of like case studies like in in I guess the whole field is kind of a lot of case studies and you know as we were we were talking like it seems like somewhat subjective because we're like kind of assigning
</details>

>> 并且提示模型去说某些话，比如去……

<details><summary>Original English</summary>
>> uh and prompting the models to to say certain things like to
</details>

>> 是的，很难说其中某些内容有多现实。我不知道。我认为这可能就是我们这个领域的性质，事情具有极强的经验主义色彩。

<details><summary>Original English</summary>
>> Yeah, it's it's hard to tell how realistic some of this kind of stuff is. I don't know. I think it's just sort of the nature of our field that things are super empirical.
</details>

>> 我想很久以前人们认为，作为科学家，我们弄清楚了……

<details><summary>Original English</summary>
>> I think a long time ago people thought like you know we just as scientists we figure out the
</details>

<!-- chunk 6/7 -->

对的想法，那个绝妙、完美的想法，然后我们利用它，最后就得到了通用人工智能（AGI）之类的东西。

<details><summary>Original English</summary>
right idea the right beautiful perfect idea and we you know we use it and we end up with AGI like this kind of thing.
</details>

>> 实际上，它看起来非常讲求迭代。人们尝试一些东西，模型在某些方面变得更好。有时候会出现一个产生巨大影响的想法，但从来没有什么是一蹴而就解决的。看起来在人工智能研究中，就像你必须部署一个新模型，收集反馈，弄清楚该修复什么。

<details><summary>Original English</summary>
>> In practice it seems like it's very iterative. People try a few things model gets better at some things. Sometimes there is an idea that has huge effects but nothing is solved ever in one go. It looks like an AI research. is like you have to deploy a new model, collect feedback, figure out what to fix.
</details>

>> 所以也许我们的整个领域就是在应对边缘情况，比如修复边缘情况，

<details><summary>Original English</summary>
>> So maybe our our whole field is about edge cases and like fixing edge cases,
</details>

>> 对吧？

<details><summary>Original English</summary>
>> right?
</details>

>> 有可能。也许它不像人们所希望的那样系统化。

<details><summary>Original English</summary>
>> Possibly. Maybe it's not as systematic as one would hope.
</details>

>> 嗯。[清嗓子]

<details><summary>Original English</summary>
>> Mh. [clears throat]
</details>

>> 但我觉得我做可解释性研究得到的一个感受是，模型内部确实有系统性的机制可以解释很多行为。

<details><summary>Original English</summary>
>> But I think one feeling I've gotten from doing interpity research is that the models do have systematic, you know, internal mechanisms that explain a lot of behavior.
</details>

>> 我们只是需要找到正确的角度来运用这种理解，以便改进模型。

<details><summary>Original English</summary>
>> We just got to figure out the right angle to deploy this understanding in order to improve models.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是啊。所以归根结底它是一门科学。

<details><summary>Original English</summary>
>> Yeah. So it is a science at the end of the day.
</details>

>> 我想我们希望它成为一门科学。我们走着瞧吧。你不需要做纯粹的科学就可以做很多事情。显然，

<details><summary>Original English</summary>
>> I think we want it to be a science. We will see. You can do a lot of things without having to do pure science. Clearly
</details>

### 幻觉与系统性机制：以状态空间模型为例

>> 那我们来谈谈幻觉问题，因为我觉得每个人都有过这种经历，而且似乎并没有一个非常清晰的解释来说明为什么会发生这种情况。你通常会认为语言模型只是犯了个错误，但我觉得从可解释性的角度来看，背后应该有更深层的原因。比如大家经常引用的一个非常普遍的例子：strawberry（草莓）里有多少个字母 R？这似乎是一个非常简单的问题，语言模型却会犯错，我们能从可解释性的角度来回答这个问题吗？

<details><summary>Original English</summary>
>> and let's address the hallucination issues cuz I feel like that's something that everyone has experience with and there doesn't seem to be a very clear explanation of why that happened. You would usually think that the language model kind of just made a mistake but I would think you know from interp perspective there's something deeper to it. Like for example, a very common instance that people site is how many Rs are in a strawberry and like that seems to be like a very simple question the language model would make a mistake on like do we can we answer that from an interpret perspective?
</details>

>> 是的，我认为这确实可以回到你提到的边缘情况的观点，

<details><summary>Original English</summary>
>> Yeah, I do think it goes back to your edge case point
</details>

>> 如果一个模型做对了某件事，很可能内部有某种机制可以解释它的正确性。嗯。

<details><summary>Original English</summary>
>> where like yeah if a model does something correct then it's likely there is some internal mechanism explaining the correctness. Mhm.
</details>

>> 如果它做错了，可能只是因为它没有学到正确的机制，

<details><summary>Original English</summary>
>> If it does something wrong, it could just be it failed to learn the right mechanism
</details>

>> 或者是出现了一些疯狂的情况。就像陀思妥耶夫斯基的名言：幸福的家庭各以其特有的方式相似，不幸的家庭却各有不同。大概是这样吧？我认为这也适用于这里。是的。如果模型表现正确，就会有系统性的解释；但如果没有做对，我不知道我们是否能给出解释。

<details><summary>Original English</summary>
>> or like there's some crazy stuff going on. There's like a dsttoyki quote. It's like all happy families are alike in their own way, but unhappy ones are like different. Something like this, right? I think this applies here. Yeah. If the model is doing the correct thing, there is a there is a systematic explanation. But if it's not, it's like I don't know if we can offer it.
</details>

>> 所以，弄清楚它为什么能把事情做对，相比于弄清楚它为什么做错，要更有价值一些。

<details><summary>Original English</summary>
>> So, it's kind of more more valuable to figure out why it does something right compared to why it does something wrong.
</details>

我认为可能确实如此。是的。好的。我可以从一个更偏技术的角度举个例子。通常我的感觉是，大多数错误都很难解释。即使我们能完全解释它们，我们也只会发现那些错误乱成一团，除了一直训练或者使用更大的模型之外，我们没有简单的解决办法。也许是模型用尽了容量来存储你想要它存储的所有事实，诸如此类，对吧？但有时候，失败背后也存在着系统性的解释。例如，大家知道如今所有模型都使用 Transformer 架构。Transformer 的一大问题是它们在时间成本上是呈二次方增长的。因此序列越长，你就必须等待越来越长的时间让它生成下一个 token。所以有些人致力于尝试加速这个过程。他们开展了一项名为状态空间模型（state space models）的研究方向。这会涉及到一点技术细节，但我会尽量讲得浅显一些。好的。

<details><summary>Original English</summary>
I think possibly yes. Yeah. Okay. Uh I can give one example from a more technical point of view. So normally my feeling is most errors are hard to explain. Even if we could interpret them perfectly, we would just find that the errors are a mess and we don't have an easy fix except like train longer or have bigger model maybe model runs out of capacity to store all the facts you wanted to store this kind of thing, right? But sometimes there are systematic explanations for failures. So one example is you know of course all models these days use the transformer architecture. You know a big problem with transformers is their quadratic in time cost. So the longer your sequence gets the more and more time you have to wait for it to generate the next token. So some people have worked on like trying to speed this up. They have this line of research called state space models. It'll get a little technical but I I'll keep it low. Okay.
</details>

>> 嗯，早期的状态空间模型在统计学等领域已经存在很长时间了。但是在 2020 年代初，大概是在 2019 年左右，人们开始将其应用于语言建模，并且非常努力地尝试击败 Transformer，因为状态空间模型要快得多。所以如果你能将其扩大规模，而且它们的效果和 Transformer 一样好，你就会想要转向它们。

<details><summary>Original English</summary>
>> Um so the early state space models have been a thing for a long time in like statistics. Um, but in the 20 early 2020s, maybe like 2019 kind of stuff, people started applying it to language modeling and they tried really hard to beat transformers because they're much, you know, they're much faster states space models. So if you can scale this up and they're as good as transformers, you would want to switch to them.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 但在实践中，他们发现它们更差。它们总是更差，而且大家想不通为什么。用相同的数据训练等等，它们就是更差。大概在 2021 年左右，斯坦福大学的一个团队，Chris Re 的学生们，注意到了 Anthropic 在可解释性方面的一项发现，即 Transformer 中上下文学习（in-context learning）的机制。在 Transformer 中，你输入一些内容进行提示，它们就能够理解上下文并利用它来完成任务。比如你给它展示你想要完成的任务的示例，但你不知道该如何用语言解释该任务，于是你仅仅提供示例。

<details><summary>Original English</summary>
>> But in practice, they found they're like worse. They're always worse and they couldn't figure out why. You train on same data, so on they're worse. Uh, in 2021ish, there was a group at Stanford um Chris Ray students. They noticed anthropics discovery on the interp side of a mechanism for incontext learning in transformers. So in transformers you prompt them with some stuff and they can understand the context and use that to do things. Um maybe you give it examples of a task you're trying to do but you you don't know how to explain that task. So you just give examples.
</details>

>> 它能摸索出规则来进行预测，

<details><summary>Original English</summary>
>> It figures out rules to like predict
</details>

>> 那个任务，而且示例越多效果就越好。这是 GPT-3 时代一个极其惊人的发现。

<details><summary>Original English</summary>
>> that task and they get better with more examples. This is a crazy finding from GPT3 era.
</details>

>> 于是他们就在想，好吧，为什么我们的状态空间模型做不到这一点？他们尝试在相同的任务上运行，结果表现就是很差。Anthropic 从可解释性的角度给出了解释：只要给这些 Transformer 至少两层，它们就会学习到一种特定的注意力头机制，使其能够解决这一任务。

<details><summary>Original English</summary>
>> And so they were like okay why can't our state space models do this? They tried running on the same task and they would just do bad. You know, Enthropic gave an explanation from an interp side. There's a certain attention head mechanism that these transformers learn when you give them at least two layers that enables them to solve this task.
</details>

>> 它被称为归纳头（induction heads）。

<details><summary>Original English</summary>
>> It's called induction heads.
</details>

>> 于是斯坦福大学研究状态空间模型的人就想，如果我们找到一种方法，把完全相同的机制放入状态空间模型中，来帮助它学习上下文学习呢？这篇论文叫作《Hungry Hungry Hippos》。我不知道，我也不知道为什么叫这个名字。

<details><summary>Original English</summary>
>> So the state space model people at Stanford were like what if we figure out a way to put this exact mechanism inside the state space model uh to help it out learning you know in context learning. And this paper is called hungry hungry hippos. I don't know I don't know why it's called this.
</details>

>> [笑声]

<details><summary>Original English</summary>
>> [laughter]
</details>

>> 简称就像 H3。他们展示了只要做这么一个细微的改动——那其实是一个简单的改动，并不是一个微小的改动——模型就学会了如何进行上下文学习。随后所有较晚期的状态空间模型，你可能听说过 Mamba 或者 Delta，

<details><summary>Original English</summary>
>> is like H3. Um, and they showed that if they just did this minor change, it was like simple change, it's not a minor change, the model learned how to do in context learning. Uh, and then all the later state space models, you might have heard of Mamba or Delta,
</details>

>> 它们都借鉴了这一进展。

<details><summary>Original English</summary>
>> they draw upon this like advance.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 现在状态空间模型被相当广泛地使用。如果你看看 Kimi 或者最近的大型 Qwen 模型，它们都结合了 Transformer 注意力与门控 DeltaNet 等等。是的，这就是一个非常清晰的例子，说明某样东西表现糟糕是有系统性原因的，

<details><summary>Original English</summary>
>> And now state space models are like used quite heavily. So if you look at Kimmy or the big Quen models recently, they have a hybrid of transformer attention and gated Deltaet and stuff. Yeah, this is a clear example of like there was a systematic reason why something was performing badly
</details>

>> 而可解释性 [清嗓子] 帮助我们找到了它并进行了修复。

<details><summary>Original English</summary>
>> and interp [clears throat] helped us find it and fix it.
</details>

>> 是的，我希望有更多这样的研究成果。我认为确实有可能存在类似的情况。

<details><summary>Original English</summary>
>> Yeah, I would like there to be more stuff like this. I think it's possible there is some stuff like this.
</details>

>> 是的。然后你就可以将其应用到其他大型模型中。

<details><summary>Original English</summary>
>> Yeah. And then you can apply that to big other models.
</details>

>> 没错。如果我们能在可解释性上取得非常好的进展，那么也许我们就能发现更多类似这样的例子。

<details><summary>Original English</summary>
>> Yeah. And if we have really good progress on interp then maybe we can you know find more instances of this.
</details>

>> 也许幻觉并不是这类情况，但也可能它是，也许架构中存在某种根本性的问题，

<details><summary>Original English</summary>
>> Um you know maybe hallucination is not an instance of this but maybe it is maybe there's some fundamental issue in the architecture.
</details>

>> 是啊。

<details><summary>Original English</summary>
>> Yeah.
</details>

### 学界与业界的合作与分歧

>> 导致了它产生幻觉。我不知道。非常有趣。太棒了。是的，我觉得这是一个很好的切入点，让我们顺势聊聊产业界，以及大家在可解释性领域都在做些什么，因为正如你所说，我觉得这仍然是一个相当偏技术性的研究领域，但它似乎确实具有一些非常明显的商业价值和应用。我们先从这里开始：你在学术界，但你也有很多业界经验。学术界和工业界的人在对待这类研究以及总体上对待这个课题时，是否存在不同的切入方式？

<details><summary>Original English</summary>
>> That makes it hallucinate. I don't know. Very interesting. Uh, cool. Yeah, I think this is a good segue for us to kind of get into the industry uh and you know what everyone is doing here with inter because this is you know as you said like I feel like it's still a pretty technical field of research but it seems to you have some like pretty clear commercial values and uh applications as well. Uh let's just start with you know you are in academia but you have you know a lot of industry experience as well. Are academics and industry folks approaching the this kind of research uh and just this topic in general differently?
</details>

>> 是的，我不能说自己有非常丰富的工业界经验，不过，我主要的经历是在 Transluce 实验室之类的地方。所以我看到的所有东西都是以外部视角来看的。

<details><summary>Original English</summary>
>> Yeah, so I wouldn't say I have a ton of industry experience, but um yeah, my main experience has been translucier lab or anything. So everything I see is external.
</details>

>> 我对可解释性领域的感受是，比起人工智能研究的其他领域，学术界和工业界之间在成果和进展上有更多的共享。我认为这是因为可解释性目前还没有出现只要通过堆算力规模就能取得更好效果的固定配方。因此，基本上需要大家不断提出新的想法，而想法是连随便一个研究生都能够贡献的，对吧？在其他领域，比如如果你想做强化学习研究，由于学术界和工业界所拥有的资源规模差距太大，两者的研究性质截然不同。是的，我想说在可解释性领域，它仍然算是一个跨越学术界和工业界的共同体，举办的研讨会有来自 Anthropic、DeepMind、OpenAI 的人，也有来自斯坦福、西北大学的 David Ba 团队、Ellie Pavlick 等学术界人士。有这么多从事可解释性研究的教授，带着学生做可解释性，这绝不是毫无用处的，我认为这对可解释性的进步非常非常重要，甚至对整个工业界来说也是如此。

<details><summary>Original English</summary>
>> My feeling with interpility is like there is more sharing of results and progress between academia and industry than other areas of AI research. I think because interp is still like there's not some recipe that you just scale up to get better in TRP yet. Um and so it's basically like people need to come up with new ideas and like ideas are are something that even a random grad student can contribute to, right? Um in other areas it's like if you want to do reinforcement learning research the nature of the research is quite different from academia versus industry because of the scale of resources being so different. Yeah, I would say in interability it is still sort of a community across you know academia and industry like uh you know the workshops that happen they have a mix of people from anthropic or deep mind um openai and also academics from like Stanford or um you know David B David Ba's group at Northwestern um Ellie Public there are all these professors who do interbility research and have students who do interp is is like you know useless or something it is like quite quite important for progress and interpability I would say even for the industry.
</details>

>> 是的。是的。有道理

<details><summary>Original English</summary>
>> Yeah. Yeah. Makes
</details>

<!-- chunk 7/7 -->

### 可解释性与模型设计

道理。

额，那么当我们把这一点应用到模型设计上时——比如 Goodfire 的设计理念，某种带有可解释性的模型——额，这引来了一些批评，因为我觉得这有点把能力和安全审计画等号了。额，如你所知，这在行业里总是有那么点争议的。不过我想回到这个概念本身：带有可解释性地去设计模型，到底意味着什么？当然，我不能完全代表他们发言，但他们确实明确表达过这种有意识的设计理念。

<details><summary>Original English</summary>
sense.

 Uh

 so

 when

 we





apply

 that

 to

 model

 design

 goodfire

 for





example

 their

 design

 philosophy

 kind

 of





models

 with

 interpretability

 uh

 which





has

 drawn

 some

 criticism

 because

 I

 feel





like

 it

 kind

 of

 equalizes

 capability

 and





then

 safety

 auditing

 uh

 which

 is

 you





know

 always

 a

 little

 controversial

 in





the

 industry

 but

 I

 guess

 just

 going

 back





to

 the

 notion

 itself

 what

 does

 it

 mean





to

 design

 models

 with

 intervertability?





Of

 course

 I

 cannot

 speak

 fully

 for

 them





but

 they've

 articulated

 this

 intentional





design

 philosophy.
</details>

>> 所以，任何有——任何有用的技术本质上都是双重用途的，我认为。

<details><summary>Original English</summary>
>> So

 any

 su

 any

 useful

 technology

 is

 by





nature

 dual

 use

 I

 think
</details>

>> 嗯，如果我们谈论比如核能，你知道从可再生能源的角度来看非常有用，但同一门科学中的那些同样的技术进步，也导致了核武器。嗯，AI 研究本身也是这样，对吧？随着我们在编程智能体方面取得进展，你知道这对各种各样不懂编程、但生活中想做些目前还没有人提供相应产品或服务的事情的人来说，可能会超级有用，他们现在可以自己去做了；但另一方面，随便某个人也能拥有前沿水平的网络安全技能，可以黑进任何东西。

<details><summary>Original English</summary>
>> um

 if

 we

 talk

 about

 like

 you

 know





nuclear

 power

 you

 know

 very

 helpful

 from





a

 you

 know

 re

 renewable

 energy





standpoint

 but

 those

 same

 you

 know





progress

 in

 that

 same

 science

 led

 to





nuclear

 weapons.

 Um

 AI

 research

 itself





is

 like

 this

 right

 as

 we

 made

 progress





on

 coding

 agents

 you

 know

 this

 could

 be





super

 helpful

 for

 I

 don't know

 all

 sorts





of

 people

 who

 don't

 know

 how

 to

 code

 but





they

 have

 things

 they

 want

 to

 do

 in





their

 life

 that

 no

 one

 has

 you

 know





served

 a

 product

 or

 or

 like

 service

 for





and

 they

 can

 do

 it

 themselves

 now

 but

 on





the

 other

 hand

 like

 you

 know

 random





person

 has

 like

 frontier

 level

 cyber





security

 skills

 and

 can

 like

 hack

 into





whatever
</details>

>> 嗯，所以我觉得，如果某件事物是有用的，它就会具有双重用途，而作为一个社会，我们必须去弄清楚这一点。嗯，对于可解释性来说，如果我们成功搞清楚了为什么模型会以某种方式表现，或者搞清楚了如何系统地改进模型，这当然也会是双重用途的。

<details><summary>Original English</summary>
>> um

 so

 I

 think

 there's

 like

 if





something's

 useful

 it's

 going

 to

 be

 dual





use

 and

 as

 a

 society

 we

 to

 figure

 that





out.

 Um

 for

 interpretability

 if

 it's

 if





we

 succeed

 in

 figuring

 out

 why

 a

 model





behaves

 in

 a

 certain

 way

 or

 or

 you

 know





figuring

 out

 how

 to

 improve

 models





systematically

 of

 course

 this

 will

 be





dual

 use
</details>

>> 比如，这会帮助我们审计模型，但它也可能帮助比如某个恶意行为者弄清楚如何消除模型中的对齐。我认为这在本质上必然是成立的。额，这并不意味着我们不应该去做它。额，这意味着，是的，我们必须进行监管之类的事情，或者拥有一个民主的决策程序来决定谁能接触到这种强大的技术。我想说，到目前为止，可解释性研究还没有发展到在这方面产生危险的程度，对吧？我认为在达到我们不得不开始为此担忧的地步之前，还有很多工作要做。

<details><summary>Original English</summary>
>> like

 this

 will

 help

 us

 audit

 models

 but





it

 might

 also

 help

 like

 a

 bad

 actor





figure

 out

 how

 to

 remove

 alignment

 from





model

 I

 I

 think

 this

 is

 by

 nature

 going





to

 be

 true.

 Uh

 that

 doesn't

 mean

 we





shouldn't

 do

 it.

 uh

 it

 means

 that

 like





yes

 we

 we

 must

 regulate

 or

 something

 or





have

 you

 know

 a

 democratic





decision-making

 process

 that

 decides

 who





gets

 access

 to

 this

 powerful

 technology.





I

 would

 say

 so

 far

 interp

 hasn't





progressed

 enough

 to

 be

 dangerous

 in





this

 regard,

 right?

 I

 think

 there's





still

 a

 lot

 of

 work

 to

 do

 before

 it





reaches

 like

 a

 point

 where

 we

 have

 to





start

 worrying

 about

 this.
</details>

>> 所以，我之前给过你一个例子，就是由可解释性进展所驱动的状态空间模型改进。可能还有几个类似的例子，嗯，比如注意力汇聚（attention sink）之类的东西，嗯，但我不会说有非常多，这是因为人们还没有——你知道，可解释性还没有发展到能够以这种方式系统地产生成果的地步。我对此目前还不是太担心。我认为还有非常多的基础科学工作要做，所以，是的，这目前还挺遥远的。

<details><summary>Original English</summary>
>> So

 I

 gave

 you

 one

 example

 of

 the

 state





space

 model

 improvement

 being

 driven

 by





interpility

 progress.

 There

 are

 maybe

 a





few

 more

 examples

 like

 this

 um

 like





attention

 sync

 stuff

 um

 but

 I

 wouldn't





say

 there

 are

 a

 ton

 and

 this

 is

 because





people

 have

 not

 you

 know

 interp

 hasn't





progressed

 enough

 to

 to

 systematically





give

 results

 in

 this

 way.

 I'm

 not

 too





worried

 about

 it

 yet.

 I

 think

 there's





still

 so

 much

 fundamental

 scientific





work

 to

 do

 that

 like

 yeah

 this

 is

 still





kind

 of

 far.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 嗯，我认为把进展落实到实际应用中是一件好事，而其中一个应用就是有意识地做出更好的模型。对吧。所以——

<details><summary>Original English</summary>
>> Um

 and

 I

 think

 it's

 good

 to

 ground





progress

 in

 like

 a

 real

 application

 and





one

 of

 those

 applications

 is

 making





better

 models

 intentionally.

 Right.

 So
</details>

>> 是的，而且另一个相当明确的用例就是比如在药物发现领域，我想还有比如医学领域，比如 DNA 模型等等，对吧？

<details><summary>Original English</summary>
>> yeah

 and

 and

 another

 pretty

 clear

 use





case

 is

 just

 in

 like

 uh

 drug

 discoveries





and

 I

 guess

 like

 uh

 medicine

 uh

 like

 DNA





models

 and

 all

 that,

 right?
</details>

>> 对。对。Goodfire 有一个庞大的生命科学团队，正试图去对包括 DNA 模型等在内的科学发现模型进行逆向工程。

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Goodfire

 has

 a

 large

 life





sciences

 team

 that's

 trying

 to

 you

 know





reverse

 engineer

 uh

 scientific

 discovery





models

 including

 DNA

 models

 and

 stuff.
</details>

>> 所以，搞清楚语言模型是如何工作的会很酷。我希望对于语言学家来说，了解它们如何处理语言会超级令人兴奋。但这固然很酷，真正的应用会是像……你知道，你训练气候模型，或者你训练它们来模拟气候，或者训练它们去做蛋白质折叠。

<details><summary>Original English</summary>
>> So

 you

 know

 it

 would

 be

 cool

 to

 figure





out

 how

 language

 models

 work.

 It

 would





be

 super

 exciting

 for

 linguists

 I

 hope





to

 know

 how

 they

 process

 language.

 But





this

 is

 cool.

 The

 real

 applications





would

 be

 like

 you

 know

 you

 train

 models





for

 climate

 or

 you

 train

 them

 you

 know





to

 model

 the

 climate

 or

 you

 train

 them





to

 uh

 you

 know

 do

 protein

 folding.
</details>

>> 我们能否从它们之中提取出人类可理解的算法，来帮助我们取得科学进展？因为我们也想弄明白它们为什么能起作用，对吧。我认为科学应用可能会非常广阔。

<details><summary>Original English</summary>
>> Can

 we

 pull

 out

 human

 understandable





like

 algorithms

 from

 them

 that

 help

 us





you

 know

 make

 scientific

 progress





because

 we

 also

 want

 to

 understand

 why





they

 work

 right.

 I

 think

 the

 scientific





applications

 could

 be

 very

 big.
</details>

### 透明度与安全

>> 是的。是的。有道理。更具可解释性的模型，是否必然意味着它更安全？

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Makes

 sense.

 Is

 the

 model





that's

 more

 like

 interpretable





necessarily

 mean

 that

 it's

 safer?
</details>

>> 额，我不这么认为。是的，

<details><summary>Original English</summary>
>> Uh

 I

 don't

 think

 so.

 Yeah,
</details>

>> 因为如果你知道它为什么做出某种行为，你也可以利用这一点来利用它的行为，对吧？

<details><summary>Original English</summary>
>> because

 if

 you

 know

 why

 it

 did





something,

 you

 could

 also

 use

 it

 to





exploit

 its

 behavior,

 right?
</details>

>> 也许你能更容易地搞清楚如何越狱一个模型，如果你知道为什么它在面对某些提示词时没有被越狱，对吧？

<details><summary>Original English</summary>
>> Maybe

 you

 could

 figure

 out

 more

 easily





how

 to

 jailbreak

 a

 model

 if

 you

 know

 why





it

 wasn't

 jailbroken

 in

 some

 by

 some





prompt,

 right?
</details>

>> 嗯，但我确实认为透明度总体上是一件净收益的好事。是的，如果我们把自己的生活托付给这些我们不理解的复杂算法，从社会角度来看似乎是很糟的。嗯。

<details><summary>Original English</summary>
>> Um,

 but

 I

 do

 think

 transparency

 is

 like





just

 overall

 a

 net

 good

 thing.

 Yeah,

 it





seems

 like

 bad

 from

 a

 societal

 point

 of





view

 if

 like

 we

 trust

 our

 lives

 to

 these





complex

 algorithms

 that

 we

 don't





understand.

 Mhm.
</details>

>> 你知道，比如人们对社交媒体那一套并不放心。嗯，因为你知道有这些算法推送人们喜欢的视频等等，它消耗了大量时间，可能对儿童有害。而且我认为，如果公司能对他们如何训练这些算法、它们如何运作、为什么向你推荐某些内容保持透明，这至少能帮助我们作为一个社会去决定我们是否想要它们，或者至少能让人更加确信没有人在试图做恶意的事情，对吧？

<details><summary>Original English</summary>
>> You

 know,

 people

 are

 not

 comfortable,





for

 instance,

 with

 social

 media

 stuff.





Um,

 because,

 you

 know,

 there's

 these





algorithms

 that

 serve

 videos

 that

 people





like

 and

 so

 on

 and

 it

 eats

 up

 a

 lot

 of





time,

 maybe

 bad

 for

 children.

 And

 I





think

 if,

 you

 know,

 companies

 were





transparent

 about

 how

 they

 train

 these





algorithms,

 how

 they

 work,

 why

 they





recommend

 you

 certain

 things,

 it

 would





at least

 help

 us

 decide

 as

 a

 society,





you

 know,

 if

 we

 want

 them

 or

 not,

 or

 at





least

 have

 more

 trust

 that

 no

 one's





trying

 to

 do

 malicious

 things,

 right?
</details>

>> 是的。额，我认为这对 AI 系统来说也是类似的。很多人并不信任 AI 公司或 AI 的进展。他们对此相当担忧。因此，透明度总的来看就是一件好事。

<details><summary>Original English</summary>
>> Yeah.

 Uh,

 I

 think

 it's

 similar

 for

 AI





systems.

 A

 lot

 of

 people

 don't

 trust





like

 AI

 companies

 or

 like

 AI

 progress.





They're

 quite

 worried

 about

 it.

 So,





transparency

 seems

 just

 like

 a

 good





thing

 to

 have

 in

 general.
</details>

### 监管与角色训练

>> 是的。是的。有没有——我的意思是，我猜这个领域目前依然处于相当早期的阶段。有没有出现任何进展，使得监管机构能够在那方面开始起草政策了？

<details><summary>Original English</summary>
>> Yeah.

 Yeah.

 Is

 there

 I

 mean

 I

 guess

 this





photo

 is

 still

 like

 pretty

 early

 on.

 Has





there

 been

 any

 progress

 that

 allows





regulators

 to

 kind

 of

 start

 drafting





policies

 already

 like

 in

 that

 in

 that





front?
</details>

>> 是的，我想说，我是说这是可解释性研究的一个希望，去提供此类成果。嗯，我想这也是非营利组织比如 Translucent 背后的部分考量。许多其他可解释性组织……为监管机构提供帮助，去弄明白为什么模型会做出某些行为，以便他们能更好地控制模型。比如英国的人工智能安全研究所（AI Safety Institute），他们就做可解释性研究。

<details><summary>Original English</summary>
>> Yeah,

 I

 would

 say

 I

 I

 mean

 it's

 a

 hope





for

 interpability

 research

 to

 provide





stuff

 like

 this.

 Um,

 I

 guess

 that's,

 you





know,

 part

 of the

 reasoning

 behind





nonprofit

 orgs

 like

 Transloose.

 Many





other

 interpols





for

 regulators

 to

 help

 figure

 out,

 you





know,

 why

 models

 do

 certain

 things

 so





they

 can

 better

 uh

 control

 them.

 You





know,

 the

 AI

 safety

 institute

 in

 the

 UK,





they

 do

 interp.
</details>

>> 我 [清嗓子] 想说目前仍然有很多事情要做。我……我不认为……是的，我们还不能基于这类研究成果充满信心地制定新法律。是的。

<details><summary>Original English</summary>
>> I

 [clears throat]

 would

 say

 there's





still

 a

 lot

 to

 do.

 I

 I

 don't

 think

 Yeah,





we

 cannot

 confidently

 like

 make

 new





legislation

 based

 on

 stuff

 like

 this.





Yeah.
</details>

>> 另一件想到的事情是，角色训练（character training）是我最近一直在关注的方向。我们拥有所有这些不同的语言模型，它们与我们交谈的方式都略有不同。我们之前提到了 Amanda Askell，比如有所有这些哲学家在教语言模型如何行事、以不同的原则来处理问题，我想随之也塑造了它们的个性，比如这些模型的个性。对于这一切，你是怎么看的？模型正变得彼此更加分化，它们有点像……你知道，不同的人。

<details><summary>Original English</summary>
>> Another

 thing

 that

 came

 to

 mind,





character

 training

 is

 something

 that





I've

 been

 looking

 into

 uh

 recently.

 We





have

 all

 of

 those

 different

 language





models

 and

 talk

 to

 us

 in

 a

 bit

 of

 a





different

 way.

 And

 we

 mentioned

 Amanda





Manasco

 before

 like

 you

 know

 we

 have

 all





of

 those

 philosophers

 kind

 of

 teaching





language

 models

 how

 to

 do

 things





different

 principles

 on

 how

 they





approach

 things

 and

 I

 I

 guess





consequentially

 also

 shaped

 uh

 their





personalities

 like

 the

 models





personalities.

 How

 are

 you

 thinking





about

 like

 all

 of

 that

 where

 you

 know





models

 are

 becoming

 more

 differentiated





from

 each

 other?

 They're

 like

 kind

 of





like

 you

 know

 different

 different





different

 persons.

 I
</details>

>> 我绝对想说，我们现在处于一个非常奇特的境地，竟然在讨论这样一件事，对吧？这确实很奇妙，比如语言模型竟然具有角色性格。这似乎是真的，而且从可解释性的角度来看是有证据支持的。

<details><summary>Original English</summary>
>> I'll

 definitely

 say

 it's

 a

 really

 weird





position

 that

 we're

 in

 now

 that

 this

 is





a

 thing

 we

 discuss

 right

 that

 is

 weird





like

 yeah

 language

 models

 have





characters.

 It

 seems

 to

 be

 like

 true

 and





there's

 evidence

 for

 it

 from

 interp





point

 of

 view.
</details>

>> 是的。这简直有点不可思议。

<details><summary>Original English</summary>
>> Yeah.

 It's

 like

 kind

 of

 crazy.
</details>

>> 嗯。

<details><summary>Original English</summary>
>> Mhm.
</details>

>> 是的。我确实认为，可解释性研究已经表明，不同类型角色的内部表征在表征空间中是以某种方式组织起来的。嗯，Anthropic 提出了这个“助手轴”（assistant axis）的概念，其中有益的助手位于一个方向，而如果是不对齐的助手，则位于另一个方向。可解释性具有一种潜力：如果我们能用可解释性以某种方式引导训练过程。嗯，这可能是一种对角色进行精细控制的方法，

<details><summary>Original English</summary>
>> Yeah.

 I

 do

 think

 there

 is

 uh

 you

 know





there's

 been

 interp

 showing

 that

 the





internal

 representations

 of

 different





types

 of

 character

 are

 organized

 in

 some





way

 in

 representation

 space.

 Um

 there's





anthropic

 this

 assistant

 access

 thing





where

 like

 helpful

 assistants

 lie

 in

 one





direction

 and

 like

 if

 you

 get

 misaligned





assistants

 they

 lie

 in

 the

 other.

 There





is

 a

 potential

 for

 interpretability

 if





we

 can

 use

 interpability

 to

 like

 steer





the

 training

 process

 somehow.

 Um,

 it





could

 be

 a

 way

 to

 like

 finely

 control





character,
</details>

>> 对，

<details><summary>Original English</summary>
>> right,
</details>

>> 相比我们目前仅仅在数据上进行训练能提供更多保证，尤其是当我们采用像……你知道，宪政 AI（Constitutional AI）之类的手段时——在角色训练过程中，由一个 AI 来决定如何奖励某种行为与否。

<details><summary>Original English</summary>
>> with

 more

 guarantees

 than

 we

 have

 right





now

 where

 we

 just

 train

 on

 data,





especially

 as

 we

 do

 like

 AI,

 you

 know,





like

 constitutional

 AI

 kind

 of

 stuff





where

 an

 AI

 decides

 how

 to

 reward

 like





some

 behavior

 or

 not

 in

 the

 character





training

 process
</details>

>> 而我认为这是我们希望控制的，也许训练过程中的可解释性能够发挥作用。

<details><summary>Original English</summary>
>> and

 this

 this

 is

 something

 we

 would

 like





to

 control,

 I

 think,

 and

 maybe





interpability

 in

 the

 training

 process





has

 a

 role

 to

 play.
</details>

### 结语

>> 太棒了。非常感谢 Arman 参加我们的播客，非常感谢你抽出时间，期待你的研究，也期待你在博士毕业后的发展。

<details><summary>Original English</summary>
>> Awesome.

 Thank

 you

 so

 much

 Arman

 for





joining

 us

 for

 this

 podcast

 and

 thanks





so

 much

 for

 your

 time

 and

 looking





forward

 to

 your

 research

 and

 you

 know





what

 you

 end

 up

 doing

 after

 your

 PhD.
</details>

>> 感谢邀请我。感谢邀请我。非常感谢。

<details><summary>Original English</summary>
>> Thanks

 for

 having

 me.

 Thanks

 for

 having





me.

 Appreciate

 it.
</details>

[外语]

<details><summary>Original English</summary>
Foreign
</details>