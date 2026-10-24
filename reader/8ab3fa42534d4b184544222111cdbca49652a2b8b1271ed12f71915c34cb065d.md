---
author: Machine Learning Street Talk
date: '2026-03-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=dHBEQ-Ryo24
speaker: Machine Learning Street Talk
tags:
  - ai-coding
  - software-development
  - knowledge-erosion
  - model-fine-tuning
  - human-ai-collaboration
title: AI编程的危险幻觉：能力提升与知识侵蚀
summary: 本次访谈探讨了AI辅助编程的深层影响。嘉宾 **Jeremy Howard** 认为，过度依赖AI可能导致开发者对底层技术理解的退化，形成“控制幻觉”，甚至侵蚀组织内部知识。对话深入讨论了AI在代码生成、模型微调、创造力边界等方面的能力，并对AI在软件工程领域带来的风险与机遇进行了批判性分析。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Jeremy Howard
  - Rachel Thomas
  - Jacon You
  - Steven Merity
  - Yann LeCun
  - Margaret Boden
  - Peter Norvig
  - Chris Lattner
  - Fred Brooks
  - Daniel Dennett
  - Stephen Wolfram
  - Bret Victor
  - Geoffrey Hinton
  - Demis Hassabis
  - Eliza Yudkowsky
companies_orgs:
  - Fast.ai
  - Microsoft
  - OpenAI
  - Anthropic
  - Google
  - Nvidia
  - DeepLytic
products_models:
  - LLVM
  - GPT-4o
  - DGX Station
  - Mac Mini
  - MacBook Pro
  - ChatGPT
  - Codex
  - Supermemo
  - Anki
  - Jupyter Notebook
  - NBDEV
  - Wolfram Mathematica
media_books:
  - No Silver Bullet
  - Consciousness Explained
  - The Laws of Knowledge
  - DINO paper
status: evergreen
---
### AI编程的幻觉与软件质量

**Speaker 0**: 是的，这让我感到厌恶，我真的觉得这不人道。我的使命和过去二十年一样，就是要阻止人们这样工作。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, it litererdiscussts me like i literally think it's in humane. my mission remains the same as it has been for, like twenty years, which is to stop people working like this jeremy howard,

</details>

**Speaker 1**: **Jeremy Howard**是一位深度学习先驱，也是 **Kaggle** 大师。他强烈主张通过互动循环、笔记本和REPL来理解我们正在构建的东西，不断尝试解决问题直到它反弹回来。他认为这才是真正洞察力产生的地方。

<details>
<summary>Original English</summary>

**Speaker 1**: a deep learning pioneer. er a cangle grandmaster. he is a huge advocates for actually understanding what we are building through an interactive loop, a notebook, a repple the acts of poking at a problem until it pushes back back. he argues this is where real ininght happens,

</details>

**Speaker 0**: 这很有趣，他们都说得对。**LLM**s（大型语言模型）扮演着理解的角色，它们假装理解事物。没有人真正能比以前交付更多高质量的软件。我们实际上对此进行了一项研究，结果显示人们实际交付的东西只有微小的提升，非常微小的提升。关于基于 **AI** 的编程，它就像一台老虎机，你有一种控制的幻觉。你知道，你可以精心设计你的提示、你的宏指令列表、你的技能等等。但最终，你拉动杠杆，对吧？这里有一段代码，它能够理解。我是否会把公司的产品押注在这上面？答案是“我不知道”，因为我不知道现在该怎么做，因为没有人经历过这种情况，它们真的很糟糕。这是软件工程。而且我认为这可能永远都是真的。人类在使用计算机时可以做得更多，当人类能够实时操作计算机内部的对象，研究它们，移动它们，并将它们组合在一起时。无论你听谁说，我们都知道他们如何移动它们，或者是什么，如果你总是从伟大的科学家那里听到他们如何通过建立心理模型来建立更深的直觉，这些心理模型是他们通过与正在学习的事物互动而获得的。一台机器通过查看大量文本的统计相关性来建立关于世界以及它是如何工作的有效层次结构，这是我的前提。

<details>
<summary>Original English</summary>

**Speaker 0**: and this hunny thing they're both right right LM cospplay understanding things like they pretend to understand things, no one's actually creating shift times more high quality software than they were before. so we've actually just stone a study of this, and there's a tiny uptic, tiny uptic and what people are actually shipping. they thing about AI based coding is that it's like a slot machine and that you you have an illusion of control. you know, you can get the craft you're prompt and your list of mc pys and your skills and whatever. and then, but in the indiof, a pull l lvor, right, here's a piece of code that, that would understands. and am i going to bet my company's product on it? and i the answers i don't know because like II don't like like i don't know what to do now because no one's like being in in this situthat, they're really bad. it's software engineering uh. and then i think that's possibly always going to be true. they the idea that a human can do a lot more with a computer when the human can like manipulate the objects in inside that computer in real time, study them, move them around and combine them together. whoever you listen to. we know whether they move them or whatever like is, if you always always here from the great scientists, how they build deeper intuition by by building mental models, which they get overtime by interacting with the things that they're learning about a machine called kind kind of build at effective hiereracio distractions, about what the world isn't, how it works entirely through looking at the statisticcorrelations of a huge coppus of text using a declloning model that was my premise.

</details>

**Speaker 1**: 本视频由 **Nvidia GTC** 赞助。大会将于3月16日至19日举行，并免费在线直播。今年的主要议题包括：代理 **AI** 和推理、高性能推理和训练、开放模型以及物理 **AI** 和机器人技术。我对 **DGX Station** 感到非常兴奋，我已经等待了一年多。它是一款个人超级计算机，大小和 **Mac Mini** 差不多，是 **MacBook Pro** 的完美补充。你可以用它来微调一个700亿参数的语言模型。我将免费送出一台。你所要做的就是注册参加会议并使用描述中的链接参加其中一场会议。至于我想参加的会议，我对 **Aman Sang** 的演讲很感兴趣。他是 **Azure** 的首席技术官，他的会议主题是“用上下文编码：构建能真正理解你代码库的代理 **AI**”。现在，显然，**Jensen** 的主题演讲在3月16日。他说他将发布一款将震惊世界的新芯片。所以，他们的 **Blackwell** 架构已经全面投产。有人猜测我们甚至可能提前看到他们新的 **Blackwell** 架构。如果你不专注于此，链接就在描述中。如果你是虚拟参会，它是完全免费的。千万不要错过。欢迎收看 **MLST**。

<details>
<summary>Original English</summary>

**Speaker 1**: this video is brought to you by envideo GTC. it's running much the sixteen until the nineteen teen ince and hoza and streaming free online. the key topics this year are agentic, AI and reasoning, high performance, inference and training, open models and physical AI and robot tics. i'm so excited about the DGX spari've been on the waiting list for over a year. now it's a personal supercomputer that is about the size of a mac mini. so the perfect aornment to a macbook pro by the way, and you can find tune a seventy billion parameter language model with one of these things. and i'm giving one away for free. well, you have to do is sign n to the the conference and attend one of the sessions using the link in the description. as for the sessions, i'm interested in attending amen, sang 's talk. so he's the cto of as and a session is code with context, build and ergentic tic d. the truly understandand your code base. now, obviously, jenson's kino is on mars to sixteen. he said he's going to unvy LA new ship that will surprise the world. so their gengenerararchitecture very a rubin is already in full producture theyre's speculation. we might even get an early glimpse of their new finineman architecture. if you don't forget focused, the link is in the description. if you're attending virtually, it's completely free. don't miss it. join me how to welcome to MLSTI.

</details>

**Speaker 0**: 意思是，欢迎来到我的家。感谢你的到来。

<details>
<summary>Original English</summary>

**Speaker 0**: mean, welcome to my home. thanks are coming. yeah,

</details>

**Speaker 1**: 我们现在在哪里？

<details>
<summary>Original English</summary>

**Speaker 1**: where where where are we now?

</details>

**Speaker 0**: 我们在昆士兰东南部美丽的 **Moreton Bay**。我们在海边，在我家后院。

<details>
<summary>Original English</summary>

**Speaker 0**: we are in beautiful motin bay in southeast queensland. we are by the sea in my backyard,

</details>

**Speaker 1**: 天气没有让人失望，我当然没有失望。

<details>
<summary>Original English</summary>

**Speaker 1**: whether didn't disappoint II certainly didn't.

</details>

**Speaker 0**: 它不常令人失望。但如果你昨天在这里，那会非常不同。

<details>
<summary>Original English</summary>

**Speaker 0**: it doesn't often. but if you were here yesterday would have been very different.

</details>

### ULMFit的开创性工作与微调方法

**Speaker 1**: 我不知道从何说起。我一直是你的忠实粉丝，可能从2017或2018年开始。当然，你发表了著名的 **ULMFit** 论文。当我在 **Microsoft** 工作时，我记得做过一个关于它的演示，因为它实际上，我的意思是，现在我们认为在大量文本上微调语言模型是理所当然的，然后我们继续训练它们并使其专业化，但显然这在当时并非公认的智慧。

<details>
<summary>Original English</summary>

**Speaker 1**: well, i don't know way to start i'i've ve been a huge fan, probably since about two thousand and seventy eighty. and of course, you had the famous you were in fit paper. and when i was at microsoft, i member doing a presentation about that because it is actually, i mean, now we take it for granted that we find tune language models on a copies of text. and then we kind of like continue to join them. and and specialize them, but apparently this was not received wisdom.

</details>

**Speaker 0**: 这是第一次发生。是的，算是第一次或第二次。所以 **Collobert** 和 **Andrew Dai** 几年前做过一些事情，但他们错过了关键点，那就是你预训练的内容必须是通用语料库。所以没有人真正意识到这个关键点。也许我在这里有点幸运，我的背景是哲学和科学认识论。所以我花了几十年思考这个问题。

<details>
<summary>Original English</summary>

**Speaker 0**: now this was the first time it happened. yeah, kind of the first old second. so cockly and andrew die had done something a few years ago, but admissed the key point, which is the thing you pray train on has to be a general purpose coppus. so no one quite rezze this key thing. and maybe i had a bit of fortune here that my background was in philosophy. and cocology of science. and so i spbeen some decades thinking about this,

</details>

**Speaker 1**: **ULMFiT** 的技术架构。

<details>
<summary>Original English</summary>

**Speaker 1**: the technical architecture of of ULM it. it just ckechch that up.

</details>

**Speaker 0**: 我是正则化的忠实拥护者。我非常喜欢采用一个极其灵活的模型，然后通过添加正则化而不是减小架构规模来使其更受约束。所以即使在当时，这都是极具争议的，但这绝非我们独有的见解。**Steven Merity** 所做的是，他利用了 **LSTM** 的极端灵活性，这是一种经典的带状态循环神经网络，现在事物正在逐渐回归这种方式。他添加了五种不同类型的正则化。他添加了你能想象到的所有类型的正则化。然后这就是我的起点，我说：“好吧，我有一个极其灵活的深度学习模型，它可以随心所欲地强大，也可以随心所欲地受约束。”然后我需要一个真正庞大的文本语料库。这也发生在 **Common Crawl**。我想他帮助或制作了 **Wikipedia** 数据集。然后我意识到 **Wikipedia** 数据集做了很多假设。它有所有这些关于未知单词的“unk”标记，因为它有所有这些手工调整的传统 **NLP** 方法。所以我阅读了所有内容，创建了一个新的 **Wikipedia** 数据集。现在它是我的通用语料库，然后我使用了 **AWD-LSTM** 进行了训练。它实际上是通宵训练的。在游戏 **GPU** 上训练了八个小时，你知道，因为在几年前的大学里，我们没有那么多资源，我猜可能是 **2080 Ti** 左右。然后第二天早上，当我醒来时，它就是我们今天使用的三阶段架构：预训练、训练、后训练。所以那时我明白了：“好吧，既然我已经训练了一个模型来预测 **Wikipedia** 的下一个单词，那么它肯定对世界了解很多。”然后我想到，如果我将其在一个特定语料库上进行微调，我们可以称之为监督式微调数据集，在这种情况下是电影评论数据集，那么它将特别擅长预测这些单词的下一个单词。所以我花了一个小时左右了解电影，然后花了大约几分钟的时间进行微调，使用降采样分类器，这是一个经典的学术数据集，被认为是“最难”的一个，它需要对五千字的电影评论进行分类，以判断情感是积极还是消极。今天这被认为是容易的，但在那时，你知道，其他做得很好的方法是高度专业化的模型，人们为此写了整个博士论文，而我击败了他们所有的结果。你知道，五分钟后，它证明了那个模型是多么的惊人。

<details>
<summary>Original English</summary>

**Speaker 0**: i'm a huge fan of regusization. i'm a huge fan of taking a model that's incredibly flexible and then making it more more constrrained, not by decreasing the size of the architecture by bbby adding regularization. so even that at the time was extremely controversial, but that was by no mains a unique inside of of hours. so what's steven marity had done as you taken the extreme flexibility of an LSM kind of the classic stateful recurrent 're own it towards switch. things are kind of gradually heading back towards now. it is added five different types of regularizzation. he added every type of regularization you can imagine. and then that was the my starting point. this is say, okay, II have mmassively ly lelexible deep mining model that can be as powerful as i wanted to be. and it could also be as constrained as i neeit to be. and then i needed a really big corpposive text from enough. this is also even he had been a common crawl. and i think he helped or made the wikipedia data set you, then i realized actually the wikipedia data set made lots of assumptions. it had all these like ank for unknown words, because it all is huuned plastic NLP approaches. so i read the whole thing created a new weicoppedia data set. et now it's my general corpus, and then i used AWDLTM trained of. so it's actually overnight. so for eight hours on a gaming gpu, you know, because at the university of sentences ago, we didn't have hapes of resources, probably like a twenty IDTI or something i suspect. and then next morning, when i woke up, then it's the same three stage architecture that we do today. you know, pretraining the training post training. so then i figured it okay. now that i've trained something to predict the next way of wikipedia, let must know a lot about the world. i then figured, if i then fine tunit on a corpa specifics of what we could alcohol to pervised fine toting dataset, which, in this case was the dataset of movie reviews. it would become especially good at predicting the next word of those. so i'd learned a lot about movies did that for like an hour. and then like a few minutes of fine trauning, the downduring classifier, which was a classic academic data stets kind of considered the the ghdest one, which was to take like five thousand word movie reviews. and to say, like was a positive tive negative sentiment today is considered easy it at that time. you know, the other things that did it quite well, were highly specialized models that people wrote the whole phds on that. i beate all of their results. you know, five minutes later, what it five shooing that that model was amazing.

</details>

**Speaker 1**: 另一个有趣的事情是关于你进行微调的方法。

<details>
<summary>Original English</summary>

**Speaker 1**: and the other interesting thing is this kind of methodology around how you do the fine tuning air.

</details>

**Speaker 0**: 我们在 **Fast.ai** 开发了微调方法。所以这算是 **Fast.ai** 的一个成果。那时还处于早期阶段。我们做的非常有争议的事情之一是，我们认为应该专注于微调现有模型，因为我们认为微调很重要。当时也有其他人在做类似的工作。所以 **Jacon You** 的研究真的很棒。我认为这是他读博士期间的研究，关于如何微调模型以及它们能有多好，还有计算机视觉领域的其他一些人。我们是第一批真正投入微调的人。所以我们认为，使用单一学习率一次性微调整个模型是没有意义的，因为不同层有不同的行为。这也是 **Jacon You** 的研究表明的。我们发展了这样一个想法：如果你只训练最后一层，速度会快得多，对吧？因为它确实必须反向传播到最后一层。然后，一旦效果不错，就反向传播到倒数两层，再到倒数三层。然后我们使用了一种叫做判别性学习率的方法。所以对于不同的层，我们会给予不同的学习率。然后另一个关键的见解是，多年来没有人意识到，即使我们告诉了所有人，那就是你实际上必须微调每一个 **batch norm**。所以你做的所有归一化都必须微调，因为它会整体地上下移动。不，它改变了它的尺度。所以，是的，当你这样做的时候，你通常只需要微调最后一两层，我们发现，虽然我们最终解冻了所有层，但实际上只有最后两层才能达到接近最先进的结果。其他的只需几秒钟。

<details>
<summary>Original English</summary>

**Speaker 0**: so the how would we do? the finine ununing was something we dedeveloed at fast day. i so this is kind of yeah one of fast day eyes. so it's still still an every early days. and one of the extremely controversial things we did was, we felt that we should focus on fine tuning existing models because we thought fine tuning was important. uh some other folks were doing good contemporonouously that. so um jason is since keid, it's really, really great. um research, i thing it's during his phd, um how to find tratrade models and how good they can be in sather folks in the in the computer vision world. we were, you know, amongst first, there's a bunch of us kind of really investing in fine shooting. and so yeah, we felt that using a single learning rate to find true in the whole thing, all at once made no sense, because the different layers have different behaviors. and this is one of the things jacon you since kess research are so showed we developed this idea of like all. it's also way faster if you just train the last layer, right? because it really has to backproup the last layer. and then once that's pretty good backrop the next the last two. and then the last three and then we use something called discriminative learning rates. so different layers, we would give different learning rates too. and then another critical inside that no one realized for years, even though we'd told everybody was that you actually have to find tune every batch norm. so all the normalization is, you do actually have to find tune because that's moving the whole thing up and down. no, changing it scale. so yeah, when you do that, you can often just find you in the last layer or two, and we found that actually with you AM fit, although we did end up and freezing all the layers, only the last two were really needed to get the close to stay ad. the other result took like took like seconds.

</details>

**Speaker 1**: 是的，因为判别性学习率这个事情很有趣，因为我认为当时普遍的观点是，当你微调一个模型时，如果学习率太高，你会损害其表征。所以我想，当时的普遍观点是，如果你没有一个非常低的学习率，你就会破坏表征。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, because the discriminaof learning rate thing is interesting because i think the received wisdom at the time was when you find una model. if the learning rate is too high, you kind of blow out the representations tions. so i guess the wisdom was, if if you don't have a really low learning rate, you're just destroy the representations.

</details>

**Speaker 0**: 我知道当时没有所谓的“普遍观点”，因为没有人谈论它。没有人关心。我的意思是，当时根本没有人关心迁移学习。**Rachel Thomas** 和我感觉它比任何事物都更重要，你知道，因为只需要一个人训练一个非常大的模型一次，然后我们其他人就可以在此基础上进行微调。所以我想我们只是学会了如何做得非常好。我们花了很多时间尝试很多事情。但最终，直觉是相当直接的。直觉上认为它应该有效的事情，基本上总是有效。这也是当今人们进行机器学习研究方式的一个巨大差异，因为我认为这都是关于消融实验的，你不能做任何假设或猜测。这完全不正确。我发现我尝试做的几乎所有事情，第一次就能成功，因为我花了很多时间建立这些直觉，那种对梯度如何行为的理解。

<details>
<summary>Original English</summary>

**Speaker 0**: i know there was no received wisdom, because nobody talked about it. no one caare. i mean, there just no tight like on not nearly no one care. transfer learning was just not something anybody thought about. and racheland, i felt like it matters more than anything, you know, because only one purs and has to train a really big model once. and then the rest of us cannot plangunit. so i think we just to learn how to do that really well. so we spend a lot of time, just trying lots of things. but in the end, the intuition was pretty straightforward. and what intuitively saying like it all to work, basically always did work, which has another big difference between how people still today tend to do mail research, as i think it's all about abolations, and you can't make any assumptions or guesses. it's not at all true. i find nearly everything that i ct to work almost always works first time because i spent a lot of time building up. there's intuitions that kind of understanding of hell, gradients, behave.

</details>

**Speaker 1**: 我认为在持续学习和微调模型以完成特定任务之间存在差异。持续学习是为了在继续训练的同时保持模型的泛化能力，而微调是为了使模型专注于特定任务。一直以来，人们认为你可以使模型特定化，使其按你的意愿工作，但你会失去泛化能力并降低表征的质量。告诉我你的看法。

<details>
<summary>Original English</summary>

**Speaker 1**: i think there's a diiccosto me though, between continual learning, which is when we want to keep training the thing, but maintain generality versus find ine uning a thing to do something specifis that there's always been this idea that, yes, you can make a model specific, you can bend it to your will, but you lose generality and you kind of degrade the representation. so tell me about that.

</details>

**Speaker 0**: 是的，这有一些道理，尽管没有你想象的那么多。最大的问题是人们实际上不看他们的激活值，也不看他们的梯度。所以在我们的软件中，现在 **Fast.ai** 的软件中，我们内置了这种能力，可以一目了然地看到你的整个网络是什么样子。一旦你做过几次，只需几个小时就能学会，你就可以立即看到。哦，我看到了这个过度训练或训练不足，或者这个层出了问题。这不是一个谜。基本上发生的事情是，例如，你最终会得到“死神经元”，它们达到一个点，无论你做什么，它们的梯度都为零，这通常发生在它们走向无穷大的时候。你总能修复它。所以，是的，这并没有人们想象的那么糟糕。通过适当的连续学习训练良好的东西，也可以很好地用于训练特定任务。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, there's some truth in that, although not as much as you might think think the whole, the big problem is that people don't actually look at their activations and don't actually look at their gradients. so something we do and our software and now fast day are software. we have built into what this ability as to seeing in a glance, what your entire network looks like. ononce, you've done a few times. it just takes a couple of hours to learn. you can immediately see. oh, i see this over tratraor under trained or this layer that something went wrong. it's not a mystery. it also basically what happens is, for example, you end up with dead ad urons that go to a point, whether they've got zero gradient regardless of what you do with that often happens if they get of head off towards infinity, you cannot always fix that. so yeah, it's not as bad as people think by any means something that trains well for continuous learning when done properly can also be done well to train well for a particular task.

</details>

**Speaker 1**: 如果你小心的话，从某种意义上说，你确实希望神经元死亡，让我解释一下我的意思。我们希望通过引入隐式约束来改变模型的行为。因为，没有约束就没有创造力。没有约束就没有推理。所以，从某种意义上说，你实际上希望它说：“不要那样做。”你希望它做其他事情。

<details>
<summary>Original English</summary>

**Speaker 1**: if you're careful in a sense, you do want the neurons to dial and and explain why what i mean by this, like we want to bend the behavior of models to introduce implicit constrainths. because, without constraints, there is no creativity. there is no reasoning, and so not so possiso. so in a sense, you actually wanted to say, don't do that. you wanted to do something else.

</details>

**Speaker 0**: 我不那样认为。在我看来，在思考 **AI** 时，人类非常有帮助。我发现它们的行为相似多于不同。我对它们每个的直觉都相当有效。你知道，当人类学习新事物时，这不是关于“忘记”其他事物。我总是发现，当我让模型尝试学习做一些相似的任务时，它们几乎总是同时在这两个任务上做得更好，而不是只学习其中一个。

<details>
<summary>Original English</summary>

**Speaker 0**: i don't think of it that way like to be. it's more like i find thinyou humans extremely helpful when it comes to think about ai. i find they behave more similarly than differently. and my intriition about each tends to work quite well, you know, with a human when you learn something new. it's not about unlearning something else. and so something i always found is when i got models to try to learn to do to somewhat similar tasks, they almost always got better at both of them. that one that, that only learned one of them.

</details>

### 预训练模型与泛化能力

**Speaker 1**: 这让我想起了 **Yann LeCun** 的 **DINO** 论文。这种自监督学习的范式，这意味着，那是一个视觉模型，所以其理念是，我们在进行预训练，我们希望尽可能多地保持多样性和保真度。这样，当我们执行下游任务时，我们就能有更多的东西可以利用。

<details>
<summary>Original English</summary>

**Speaker 1**: i was reminded a little bit of, you know, where the dino paper from lecoon. and so this whole kind of regime of selsusupervised learning with with mean that, that was that, that was a vision model so that the idea was tracase. we're doing pretraining, and we want to maintain as much diversity and fidelity as possible. so that when we do the downstream task, we can kind of we got more things that we can latch on.

</details>

**Speaker 0**: 是的，是的。但是，嗯，你知道，半监督学习和自监督学习是一个被低估的领域。是的，**Yann LeCun** 绝对是其中一个也在研究它的人。是的，我实际上发了一个帖子，因为我对人们不关心半监督学习感到非常恼火。我多年前就写了一整篇关于它的帖子。**Yann LeCun** 也帮我看了，你知道，还提出了一些我遗漏的其他工作。但我有点惊讶，它到底有多么有用，基本上可以这样说，你看，当你完成预设任务时，对吧？所以在 **ULMFiT** 之前，我们已经在视觉领域做过这个。所以就像在医学图像中，他会拿一张组织学切片并预测，你知道，遮住几个方块并预测那里会是什么。所以我的 **USFI** 的一些学生正在做类似的事情，这基本上完全采用了 **Way** 和其他人在视觉领域已经完成的工作。是的，就像这种遮蔽方块的想法，我们没有发明它，它遮蔽了单词。但是显而易见的事情，你知道，渐进解冻层，我们以前在计算机视觉中做过。从预训练的通用模型开始的整个想法在计算机视觉中已经存在。实际上，在2015年左右，计算机视觉领域有一篇非常经典的论文，完全是一篇奇迹论文，说：“看，当我们采用一个预训练的 **ImageNet** 模型，预测哪个雕塑家创作了这个雕塑，或者预测这是什么建筑风格时，会发生什么？”在每个任务中都取得了最先进的结果。这真的让我惊讶，人们没有看到这一点并思考，我敢打赌这在其他所有领域也会有效，无论是基因组序列还是语言或其他什么。但是人们缺乏想象力。我发现他们倾向于假设事物只在一个特定领域有效。这确实是真的。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, yeah, but um, you know, sei, supervised and self supervised learning was such an unappreciated area. and yeah, young lukon was absolute in one of the guys who was also working on it. yeah, actually did a post because i was so annoyed healthy people. people cared about semi supervised learning. i did a whole post about it years ago. younlekcorn looked it for me as well, and you know suggested a few other pieces of work that i i'd missed. and but i was kind of surprised that how you know how incredibly suits useful it is to basically say, look, as you come come of the pretext task, right? so in i we did this envision before, you will them fit. so it's like in medical imaging, he ttake a histology slide and predict, you know, mask ked, a few squares and predict what is to be there. so some of my students USFI had doing stuff with that, it was basically entirely taking stuff the way and others had already done in vision. yes, ah, like this idea of masking out squares, we didn't invent it asking out words. but the obvivithing, you know know in ideidea, um gradually unfreezing layers. we had done before in computer vision. the whole idea of starting with a pretrained model that was general purpose have been in computer vision. there's a really classic paper actually in computer vision in i've been around twenty fifteen was entirely and miracle paper saying, look what it happens when we take a pretrained image net model, predicting what sculptor created this sculpture or predicting what architecture style this is. and like an an every task get got the state of yet result. and it really surprised me, people didn't look at that and think like i bet that ought to work in every other area as well, whether it be genome sequences or a language or whatever. but people have that of a lack of imation imagination. i find they tend to assume things only work in one particular field. that's really true.

</details>

**Speaker 1**: 是的，我想有两件事。我的意思是，首先，我们有点暗示了“古德哈特定律”或“肖特法则”的概念，即你优化了什么，就得到什么，代价是其他一切。但似乎并非如此，因为我们可以，你知道，在语言模型中优化困惑度。实际上，似乎发生的事情是，我们正在进入一点点分布假说。所以你知道，你，你知道，**Kekeps** 公司的“词”这个词。所以当我们有大量的关联数据时，它可能是通过预测或其他类似的事情来掌握的。模型似乎构建了一些我们可以称之为理解的东西。

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, i guess ss, there's two things. i mean, festival. we were kind of hinting at this notion of almost good hearts law or the short that rule that you get exactly where you optimised for the cost of everything else. but that doesn't seem to be the case because we can, you know, optimize for perplexity in the case of language models. and actually say, what seems to happen is we're getting into the distributional hypothessary a little bit. so you know, you, you know, the word by the company kekeps. so when we have an incredible amounts of associtive data, it might be master red to prediction, or any of these things like that. the model seems to build some thing that we might cool. and understanding II foralways thought of it as a higher acacof of strstractions.

</details>

**Speaker 0**: 我一直认为它是一个抽象的层次结构。如果它必须预测，你知道，如果文档中写着 **Bobby Fischer** 在国际象棋棋谱中使用的开局，那么它需要知道一些国际象棋棋谱，至少是开局。如果它写着“这是1956年美国总统说的”，那么你需要知道，你不仅需要知道总统是谁，还需要知道有总统这个概念，他们是领导者，他们领导着一群人，这些人群有等级制度。因此，存在着人，存在着物体。如果不知道所有这些，就无法很好地预测句子的下一个词。所以我的假设，我创建 **ULMFiT** 的初衷是，它会尽可能地压缩这些知识，为了获得这些知识，它必须在模型深处创建这些抽象和等级结构。否则，它怎么可能很好地预测下一个词呢？你不希望深度学习模型成为通用的学习机器。你知道，我们有一种通用的训练它们的方法。我认为，如果我们正确处理数据，如果提示足够好，那么理论上我们应该能够构建那个预测下一个词的机器，它应该隐含地构建一个层次结构，理解文本中描述的事物。

<details>
<summary>Original English</summary>

**Speaker 0**: if it's it's got a predict, you know, if the document is here was the little little opening that it old that bubby fisher used and has chest notation to predict the next thing it needs to know something about chest notation at least openings. if it's like, uh know know this. this was totoed by the nineteen and fifty six US president comma. you need to know like you don't even did, don't just need to know who the president was. but the idea that there are presidents and they folght the idea that there are leaders and theyfoll the idea that there are groups of people who have hieracy es, and they thoufore that there are people, and they thought that there are objects. and you can't predict the next way of a sentence well, without knowing all of these things. so that knowing my hypothesis for where i created you will enfit was to say it would end to to comppress that as well as possible to get that knowledge. it would have to create these abstractions these hierarchh's obstractions somewhere deep inside its model. otherwise, how could it possibly do a good job of predict an expert? you don't want because deep leadning models are universal learning machines, you know, and we had a universal way to train them. i think it, if if we get the data right tion, if the pt was good enough than in theory, we ought to be able to build that next word predicting machine, which ought to implicitly build a hiarchical structural understanding of the things that have being described by the text that it is learning to predict.

</details>

### AI的创造力边界与约束

**Speaker 1**: 我认为它们在某种程度上理解，但只是以一种相当肤浅的方式理解。所以存在着无数的表面统计关系，它们泛化能力非常强。好吧，这并非奇迹。但关键是我想把这与你之前关于创造力的评论进行对比。我认为知识是关于约束的，我认为创造力是关于尊重这些约束的知识演变。因此，**AI** 没有创造力。你也说过同样的话，你说 **AI** 没有创造力。那么，一方面，你怎么能说它们理解，却又不认为它们有创造力呢？

<details>
<summary>Original English</summary>

**Speaker 1**: i think that they can know in quite they they know in quite a superficial way. so there's a myriad of surface statistical relationships and they generalize extrorordinary. well, it's no exmiraculous is, but the thing thing is want want to conrost this with other comments you've made about creativities. and i think knowledge is about constraints, and i think creativity is about evolutionship of knowledge respecting those constraints. therefore, AI is not creative. and and you've said the same thing, you've said, AI isn't creative. so like on the one hand, how can you say that they know and not think that they can be created?

</details>

**Speaker 0**: 我的意思是，我想我用过那个确切的表达。你知道，我确实记得和 **Peter Norvig** 在镜头前聊天，我们俩都说：“好吧，实际上，它们确实有点创造力。”所以我们只是要非常小心措辞。我想，嗯，你知道，**Piotr Wozniak** 是一个我非常非常尊重的人，他重新发现了间隔重复学习，建立了 **SuperMemo** 系统，并且是现代记忆大师。他将一生奉献给记忆，原因是他相信创造力来自于记住大量事物，也就是说，以有趣的方式将你记住的事物组合在一起是创造力的绝佳方式。**LLM**s 在这方面实际上相当擅长，但有一种创造力它们完全不擅长，那就是，你知道，超越分布。所以这也就是我认为你的问题所指向的地方。嗯，但我只是想用这种方式来表达，你必须对这些事情非常谨慎，因为如果你说它们没有创造力，这可能会给你错误的印象，因为它们可以做很多看起来很有创造力的事情。但如果问题是：“它们真的能外推到训练分布之外吗？”是的，它们不能。但是训练数据的分布如此之大，它们之间进行解释的方式如此之广阔。我们还不知道它的局限性是什么，但我每天都看到它，你知道，因为我的工作就是如此。我一直在训练数据的边缘和之外，我正在做以前从未做过的事情，这很奇怪。我不知道你以前是否见过，但我每天都会看到好几次，**LLM** 从极其聪明变得比愚蠢还糟糕，就像完全不理解世界最基本的运作原理。是的，就像：“哦，糟糕，我超出了训练数据分布。”它变得迟钝了。然后就像，我跟你家人争论是没有意义的。是的，是的，你知道，你知道，那时已经没用了。

<details>
<summary>Original English</summary>

**Speaker 0**: i mean, i think think have fused that exact expression. you know, i have actually remember chatting with peter norvada on camera, and both of us said, well, actually, they kind of are creative like. so we just could be a good careful about that choices of words. i guess, so um know, pilter wasn't yet who's a guy. i really really respect who could of rediscovered space prepeative learning, built the supermemo system and is the modern day greuru of memory. the entire reason he's based his life around remembering things is because he believes the creativity comes from having a lot of stuff remembered, which is to say, putting together stuff you've remembered in interesting ways. it's is a great way to be creative. lms are actually quite good at that, but there's a kind of creativity. they're not at all good at, which is you know, moving outside the distribution. so which i think is where you're heading with your question. um but i just kind of i'm framing it this way to say you have to be so you once about this stuff, because if you say like they're not creative, i gives you the can give you the wrong idea, because they can do very creative saming things. but if it's like well, can they really extrapoulate outside the trading distribution? yes, there's no they can't. but the training english speciation is so big and the number of ways to interpreate between them is so vast. we don't really know yet what the limitations of that is, but i see it every day, you know, because i my my work is irond. i'm constantly on the edge of and outside the training data. i'm doing things that haven't been done before, and this is weird thing. i don't know you''ve ever seen it before. i see, but i see it moderal times every day, where the l en goes from being incredibly clever to like worse than stupid, like like not understanding the most basic fundamental premises about how the world works. yeah and is like, oh, worps. i feel outside the training data distribution. it's gone dumb, and then like it's no point 我是你家人 having that discussionary faith. yes, yes, know know ''ve asted at that point.

</details>

**Speaker 1**: 是的，我的意思是，我喜欢 **Margaret Boden**。她有这种创造力的层次结构，分为组合式、探索式和变革式。但模型肯定可以进行组合式创造。但对我来说，关键是约束。但是，**Boden** 说过，你也提到过，她说创造力是关于约束的。你也说过，我们谈论对话式工程。但当我们谈论语言模型时，它是一个规范获取问题。所以我们经常来回沟通。实际上，当我们认为智能的过程是关于在我们的头脑中构建这个想象中的乐高积木并尊重这些约束时。当你尊重这些约束并不断演变时，那么这些事物就被认为是具有创造力的。所以语言模型，当你给它们添加约束时。这可以通过监督，通过验证的策略来实现，那么它们就具有创造力，并且我们一直在演变。我们看到了很多这样的例子，但幻觉在于它们自身的约束。显然，它们有我们谈论的这种行为塑造机制，但没有硬性约束，这就是为什么它们无法超出其分布。

<details>
<summary>Original English</summary>

**Speaker 1**: yes. i mean, i love the margagat bobodens. she had this kind of iarqi of creativities. there's like combatorial exploratory and and transformative, but what models can certainly do commondatorial creativity. but for me, it's what about constraints. but that mean, it's is about bodendensaid and you've anido diventiy, he said the creativities, what about constraints and and you've spoken. and and we talk about this dialogue engineering. but what happens is when we we talk about language models, it's a specification acquisition problem. so we go back and for often, actually, when we think the process of intelligence is about building this imaginary lego block in our mind and respecting vous constraints. and when you respect those constraints and you just continue to evolve, then those things are said to be creative. so language models, when you add constraints to them. so this could be via supervision via tictics for a verifies, then they are creative, and we alpha evolve. we see many examples of this, but the illusion sion is on their own constraints. obviously, ly, they have this behavioral shaping stuff that we're talking lob that don't have hard constraints, and that's why they can't go outside their distribution.

</details>

**Speaker 0**: 我的意思是，我认为它们无法超出其分布，仅仅因为这种数学模型无法做到。你知道，我的意思是，它能做到，但它会想知道。嗯，你知道，当你看到二维情况下将曲线拟合到数据时，一旦你超出数据覆盖的区域，曲线就会以疯狂的方向消失在太空中，你知道，我们正在做的事情就是这样。我们正在多个维度上做。你认为 **Boden** 可能会对组合式创造力感到非常震惊，当你能组合整个人类知识语料库时。我认为这就是人们经常感到困惑的地方，因为，正如我所说，例如，我昨天和 **Chris Lattner** 谈论过 **Anthropic** 如何让 **LLaMA** 写出 **Swift** 编译器。他们说：“哦，这是一个干净的房间的 **Swift** 编译器。你可以。它是干净的房间，因为它是在 **Rust** 中创建的。”你知道。这是 **Chris** 的功劳，这种，你知道，我想它可能是使用最广泛的 C++ 编译器之一。它在 **LLVM** 之上运行，**LLVM** 是编译器最广泛使用的基础。所以我想 **Chris** 并没有创造这个，你知道。我们没有给它访问他编译器源代码的权限。这是一个干净的房间实现。但这误解了 **LLM**s 的工作方式，对吧？也就是说，**Chris** 的所有工作都在训练数据中出现了多次。**LLVM** 被广泛使用，并且很多很多东西都是建立在其之上的，创建了许多 C 和 C++ 编译器。将这些转换并不是训练数据不同部分之间的插值。你知道，它是一个风格迁移问题。嗯，所以它充其量只是组合式创造力，如果你能称之为创造力的话。当你查看它创建的 **REPL** 时，你实际上会看到它复制了 **LLVM** 代码的一部分，而今天 **Chris** 说：“哦，我犯了一个错误。我不应该那样做。其他人都不那样做。”你知道，“哦，好吧，看，他们是唯一那样做的人。”这并非偶然发生，这发生是因为你实际上并没有创造力。你实际上只是在训练数据中找到了一种非线性平均点，介于构建和编译事物之间。

<details>
<summary>Original English</summary>

**Speaker 0**: i mean, i think they can't go outside their distribution because it's just something that uum that type of mathebetical model can't do. you know? i mean, it can do it, but it wonder it. well, you know, when you look at the kind of two d case of of fitting a curve to data, once you go outside the area that the data covers the curves disappear off into space in wild directions, you know, and that's what we're doing that. we're doing it in multiple dimensions yethink. i boboden might be pretty shocked at alfa. compositional. creativity can go when you can compose the entirety of the human knowledge corpus. and i think this is where people often get confused, because, as i so, for example, as talking to chris latner yesterday about have clad anthroropic ito, had had got lalad d write the sick compililer. and they were like, oh, this is a clean room sakon pilot. you can. it's it's clean room because it was creit in rest, you know. and that's a chris credit that kind of you know, i guess it's probably the top most widely used to say, say, plus class compiled out, it is playing on top of LLVM, which is the most widely used kind of foundation for compilers. though i go. chris didn't is rest this, you know, and we didn't give it access to what he compile a source code. it's a clean room implementation, but that misunderstands how LMS work, right, which is all of chris 's work, wasn't the training data. many, many times. LLVM is used widely and lots and lots of things are built on it, creating lots of sea and c plus plus compilers, converting a terruisn't, an interpulation between parts of the training data. you know, it's a style transfer problem. um so it's definitely compositional creativity at most, if you can call it creative at all. and you actually see it when you look at the the repole that it created, it's copied parts of the ellaa vencode, which today, chris says, like, oh, i made a mistake. i shouldn't have done it that way. nobody else does it that way. you know, oh, well, look, they're the only other one that did it that way you that doesn't happen accidentally that happens because you're not actually being creative. you're actually just finding the kind of non linear average point in your training data between like finding the building and compilor things.

</details>

**Speaker 1**: 好的，所有这些都是真的。首先，我认为我们不应该低估这种组合式创造力有多么强大。所以所有这些都是真的。代码在互联网上，但他们也有大量的测试，这些测试是脚手架式的，这意味着每次提交代码时，他们都可以运行测试，他们基本上有一个评审员，然后他们可以进行这种自主的反馈循环。所以从某种意义上说，这与 **OpenAI** 和 **Google** 最近的研究非常相似。你在尝试解决一个数学问题，并且你已经有了一个评估函数。在 **AlphaGo** 上也是一样，对吧？你有一个评估函数，人们所忽视的是，即使是了解评估函数是什么，也是对问题的部分了解。所以你就可以进行暴力搜索，你可以使用统计模式匹配，并使用验证作为约束，你实际上可以。

<details>
<summary>Original English</summary>

**Speaker 1**: 好的 all of that as tram mean, first stivlife. i think we shouldn't underestimate these size of how big this combinatorial creativity is. so all of that is true. so the code is on the internet, but also they had a whole bunch of sts, which was scacuffolded, which meant that every single time some code was was committed. they could run the test and and they basically had a critic, and they could then do this autonomous ous feedback loop. so in ina sense, it's very similar to the recent research by open ai and geerine. i you, you're trying to solve a problem in math, and you already have an evaluation function. the same on the ok, ze, right? you have an evaluation function, and what people discount is, even knowledge of what the evaluation function is, is partial knowledge of the problem. so you can then brute for search, you can use the statisticpattern match and use the verifiy as a constraint, and you can actually,

</details>

**Speaker 0**: 他们甚至不需要那样做，对吧？就像你已经知道如何通过这些测试一样，因为有很多软件已经做到了。所以它只是使用那个并将其翻译给我们。我想它就是这样做的，嗯，这令人印象深刻。如果我对数学的了解比对计算机科学的了解少得多，但据我与数学家的交谈，他们告诉我，这也发生在像 **Abbott** 的问题等等方面。其中一些是新解决的。

<details>
<summary>Original English</summary>

**Speaker 0**: and they don't even need to do that, right? like you literally already know how to pass those tests because it's lots of software ether already does it. so it just uses that and translates them to us. i guess that's all it did um which is impressive um and if i'm much less similar with math than i am computer science, but from talking to mathematicians, they tell me that that's also what's happening with like adults, problems and stuff. it's some of them are newly solved.

</details>

**Speaker 2**: 是的。

<details>
<summary>Original English</summary>

**Speaker 2**: yeah,

</details>

**Speaker 0**: 但它们不是洞察力的火花。你知道，它们解决的是可以通过将非常密切相关的事物组合起来解决的问题。所以人类已经解决了。

<details>
<summary>Original English</summary>

**Speaker 0**: but they are not sparks of insight. you know, theare solving ones that you can solve by mesing up together very close regulated things. so humans already figured out so on the subject of claud code.

</details>

### AI编程对生产力的影响与能力退化

**Speaker 1**: 好的，关于 **Claude Code**。我知道你广泛讨论了 **AI** 编程。实际上 **Rachel** 做了一些有趣的工作。我的意思是，她引用了 **Meta** 的研究，该研究表明人们在使用 **AI** 编程时生产力实际上下降了。但我想，当时我认为这是 **Anthropic** 的研究。也许我们应该重新思考一下。我记得几天前 **Dario** 写了一篇文章，我想叫做“技术的青春期”之类的。他基本上说：“看，你知道，我们有所有这些令人惊叹的软件工程师和 **Anthropic**，他们效率极高。”他正在推断普通软件工程师的情况。所以很快就会出现大规模失业，因为我们将能够自动化所有这些工作。我的意思是，

<details>
<summary>Original English</summary>

**Speaker 1**: now i know you spoke an extensively about five coding. i'd actually rachel had some interesting workout. i mean, she quoted the the meter study, which showed that productivity actually went down when people were vipe coding. but i think and i thought that they went when i wwand and think was there was the anthrotics study mean. and maybe we should rewonder of that mendario had the SA out the other day, i think, was called the athlesence of technology gy something like that. and he was basically saying, look, you know, and we have all these amazing suffreiengineers and ropic, and they are just so productive, and he was extrapulating to the average sofreengineers. so there's going to be mass unemployment because soon we're going to be to automate all of this where they are. i mean,

</details>

**Speaker 0**: 这没有任何意义。嗯，**Elon Musk** 几天前也说过类似的话，他说：“哦，**LLM**s 会直接吐出机器代码。我们不需要库、编程语言。”是的，是的。看，问题是这些家伙最近都没有做过软件工程师。我不确定 **Dario** 是否做过软件工程师。软件工程是一门不寻常的学科，很多人都把它误解为在 **IDE** 中敲代码。编程是另一种风格迁移问题。你接受一个要解决的问题的规范，然后你可以利用你的组合式创造力，从训练数据中找出那些经过插值解决问题并将之翻译成目标语言语法的片段。然后你就得到了代码。**Fred Brooks** 几十年前写过一篇非常著名的文章《人月神话》，其中提到“没有银弹”，听起来他几乎是在谈论今天。他特别说了一些非常相似的话，那就是在那些日子里，人们都在说：“啊，这些新的第四代语言等等呢？”你知道，“我们再也不需要编码员了，再也不需要软件工程师了，因为软件现在太容易写了，任何人都可以写。”嗯，他说：“好吧，我猜你最多可以提高30%。”他明确地说在未来十年内提高30%。但我不认为他需要限制那么多，因为软件工程中绝大多数工作不是敲代码。嗯，所以从某种意义上说，**Dario** 说的一些话是正确的，就像对很多人来说一样。现在他们的大部分代码都是由语言模型编写的。对我来说也是如此，也许90%的代码是这样，但这并没有让我提高多少生产力，因为那从来都不是瓶颈。它也帮助我进行研究，弄清楚要修改哪些文件。但每当我试图让 **LLM** 设计一个以前从未设计过很多次的解决方案时，结果都非常糟糕，因为它每次给我的设计都只是表面上有点相似的东西。而通常这会是一场绝对的灾难，因为表面上相似的东西，而我实际上正试图创造新东西来摆脱相似的东西。这非常具有误导性。

<details>
<summary>Original English</summary>

**Speaker 0**: it doesn't make any sense. um elon musquks said something a bit similar few days ago, saying like, oh, hellems have just spit out the machine code directly. we want need libraries, programming languages, yeah yeah. look, the thing is none of these guys have have been ssofare engineinerecently. i'm not sure sharrias have have been a software engineer at all software engineering as a unusual discipline, and a lot of people mimike it for being the same as typing code into an ie coding is another one of these style transfer problems. you take a specification of the problem to solve, and you can use your compositional creativity to find out the parts of the training data, which interpulated between them, solve that problem and interprelate that with syin tax of the target language. and you have get cold. there's a very famous sa o pread brooks written ten many decades ago, no silver bullet, and which it almost sounded like he was talking about today. he was specifically saying something he was just putting saying very similar, which is those days as all like ah, what about all these new fourth generation languages and stuff like that? you know, we're not going to need any need coatas anymore any software engineers anymore because softwis now so easy to write anybody can write it um. and he said, well, i guess you could could at maximum m thirty percent ent improvement. specispecifically said a thirty percent improvement in the next decade. but i don't think he needed to limit that much because the vast majority of work in software engineering isn't typing in the code. um so in some sense, parts of watdariia said, we're right just like for quite a few people. now most of their code is being typed by a language model. that's true for me, say, like maybe ninety percent, but it doesn't make me that much more productive because that was never the slow bit. it's also helped me with kind of the research charge and figuring out, you know which files are going to be touched. but any time i've made any attempt getting an an lemonto lake design, a solution to something that hasn't been designed lots of times before. it's it's horrible because what it actually every time gives me is the design of something that looks on its surface a bit similar. and often, that's gta be an absolute disaster because things that look on this surface bit similar. and like i'm literally trying to create something new to get away from the similar thing. it's very misleading.

</details>

**Speaker 1**: 首先，我对那些科技界的兄弟们误解认知科学和哲学的倾向感到筋疲力尽。我们俩都讨论过很多真正有趣的人，比如 **Sai Suddhego**，他写了《知识法则》，还有神经科学哲学家 **Anil Seth**，她谈论的是知识基本上是蛋白质。所以，是的，我认为知识是透视的。我不认为知识可以是这种抽象的、没有透视的东西，可以存在于 **Wikipedia** 上。我还认为知识是进化的，它是活的。它是存在于我们内部的东西。一个组织的目的就是保存和发展知识。所以当你开始将认知任务委托给语言模型时，你实际上会产生一种奇怪的悖论效应，即你侵蚀了组织内部的知识。

<details>
<summary>Original English</summary>

**Speaker 1**: first of all, i'm i'm exhauerated by what i see as the tech bro prede election to misunderstand coglesitive signs and philosophand. i'm on us because we've we spoken to so many really interesting people on emolesty, like, for example, says a hiddewgo, he wrote to mispoook the laws of knowledge and and even a movii to erimmoter. she's a philosopopher of neuroscience. and she was talking all about, you know, lithe ficicting. it basically that knowledge is protein. so yeah, i think that that knowledge is perspect divial. i don't think that knowledge can be this abstract perspective free thing that can exist on wikipepediand. and i also think that knowledge is evoldiand. it's alive. it's it's something that exists in in us. and the purpose of an organization is to preserve and evolve knowledge. so when you start delegaate eighating cognitive task to language models, you actually have this weird paradoxicical effect that you erode the knowledge inside the organization.

</details>

**Speaker 0**: 是的，这既真实又可怕。网上经常有这样的争论：有人说 **LLM**s 什么都不懂，只是假装懂；另一些人则说：“别傻了，看看这个 **LLM** 为我做了什么！”对吧？有趣的是，他们都说得对。**LLM**s 扮演着理解的角色，它们假装理解事物。这让我想起了早期关于大众科学作品，比如 **Daniel Dennett** 的作品。这基本上就是中文房间实验：房间里有一个完全不懂中文的人，但他看起来好像懂，因为你可以给他输入问题，他会给你输出答案。但他所做的只是在一大堆书或机器中查找。假装智能和真正智能之间的区别完全不重要，只要你处于这种假装实际上有效的区域。你知道，所以对于很多任务来说，**LLM**s 假装智能是完全可以的，因为在所有意图和目的上，它根本不重要，直到你到达它无法再假装的地步。然后你意识到：“哦，天哪，这个东西太蠢了。”

<details>
<summary>Original English</summary>

**Speaker 0**: well, that's true and that's terrifying. it's often these these arguments online between people who are like ellams don't understand anything. they're just pretending to understand. and then other people were like you don't be ridiculous. look, what this LE mm is did for me, right? and it's one thing is theyy're both right. l lms cos play understanding things, they pretend to understand things. and this is the interesting thing about the early kind of work with, like popular science ence work with, like daniel dinner. um that's basically what the chinese room experiment is is you've got a guy in a room who can't speak chinese at all, but he sure looks like he does, because you can fading questions, and he gives you back answers. but all he's actually doing is looking up things in a huge array of books or machines, or whatever the difference between pretending to being intelligent and actually being intelligent is entirely unimportant, as long as you're in the region in which the pretense is actually effective, you know. so so it's actually fine for great many tasks that ellenms only pretend to be intelligent, because for all intense and purposes, it just doesn't matter until you get to the point where i can't pretend anymore. and then he realize like, oh, my god, this thing so stupid.

</details>

**Speaker 1**: 我是他的粉丝。顺便说一句。你知道，他说理解在概念上是可还原的，但在本体论上是不可还原的。他说有一种现象学的组成部分可以理解。我们甚至不需要讨论到那种程度。关于知识是蛋白质的有趣之处在于这个想法，你知道，基本上，这个康德式的想法，世界是一个复杂的事物。没有人能完全理解。它就像盲人摸象。我们都通过一个复杂的事物有不同的视角。所以我们都做这种建模。但有趣的是，语言模型有时它们似乎理解，而且它们理解，因为监督者将它们置于一个框架中。所以在这个框架内部。所以当你有了大象的视角时，它们实际上惊人地连贯。但我们忽视了监督者将模型置于那个框架中。

<details>
<summary>Original English</summary>

**Speaker 1**: i'm a fan of. so by the way. so you know, he said that i'm understanding is cosely reduceable, but ontologically irreduceable, and he was saying there was a phenomenal components underunderstand. we don't even need to go that like the interesting thing about knowledge being protein. is this idea that, you know, spbasically, this cantian idea, the world is a complex thing. none of the understanding. it's like the blind men in the elephant. we all have different perspectives through a complex thing. and so we all we all do this kind of modeling ling. but the interesting thing is that the language model sscitimes, they seem to understand and they understand, because the supervisor places them in a frame. so inside that frame. so when you have that perspective of the elephants, they're actually surprisingly coherent, but we discount the supervisor, placing the models in that frame.

</details>

**Speaker 0**: 是的，是的。所以，**Cellvis** 是新的，或者 **Verscell**。但当我读本科哲学时，每个人都在谈论的，那时 **Consciousness Explained** 大概就是那时出版的，中文房间实验可能还要早一点。这很有趣，因为我们现在讨论的正是当时讨论的相同问题，但它们已经从抽象讨论变成了实际讨论。如果人们回到抽象讨论会很有帮助，因为这有助于你摆脱你的，你知道，目前看着一个如此完美地扮演智能的东西，然后回到基本问题，这非常分散注意力。嗯，无论如何，我只是想提一下，我们现在处于一个有趣的境地，很容易对 **AI** 能做什么产生错误的认识，特别是当你分不清编程和软件工程的区别时。是的，然后就涉及到，你的问题是关于这对组织的影响？是的，你知道，很多组织基本上都在基于一个推测性的前提来押注他们的未来，那就是 **AI** 将能够比人类更好地完成所有事情。至少在编码方面比人类做得更好。我担心 **AI**，既担心组织，也担心人类。你知道，对于人类来说，当你不再积极使用你的设计、工程和编码“肌肉”时，你就不会成长，你甚至可能会萎缩，但至少你不会成长。你知道，谈到一家海洋初创公司的首席执行官。你知道，如果我的员工不成长，我们就会失败。你知道，我们不能让这种情况发生。而精通当前这一代 **AI** 框架的特定提示技能，并不是成长。你知道，这就像，这就像了解某个 **AWS API** 的细节一样，当你不想了解互联网是如何工作的时，这并没有帮助。你知道，它不是可重用的知识。它是短暂的知识。所以，如果你愿意，你实际上可以把它作为学习的超能力，但它也可能做相反的事情。它知道一个自然而然会发生的事情，那就是随着时间的推移削弱你的能力。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, yes. so so cell vis is neor or vers cell. and then it but what everybody was talking about when i back when i was doing my undergrade in phosophy y does. so inconsciousness explained came out about then probably chinese room little bit before that's interesting because the discussions were the same discussions were having now, but they've gone from being abstract discussions to being real discussions. it's helpfully people go back to the abstract discussions because it's it helps you get out of your, you know, it's very distracting at the moment to look at something that's cause playing intelligence so well and go back to the fundamental question. um anyway, i just want to mention that kind of this. this is interesting situation were now in where it's very easy to really get the wrong idea about what i can do, particularly when you don't understand the difference between coding and and soft engineering. yeah, then takes video point point. are your question about about the implications of that for organizyes? you know, a lot of organizations basbasally batting their featachres on a culative premise, which is AI, is gotta be able to do everything better than humans. ah, h least everything encoding better than humans. II worry about AA, both both the organanizations and for the humans, you know, for the humans when you're not actively using your design and engineering and coding muscles, you don't grow, you might even wither, but you at least don't grow and youyou. know speaking of the CEO of an marane start up. you know, if my stuff aren't growing and we gotta fail. you know, we can't let that happen and getting better at the particular prompting skills, whatever details with the current generation of AICI frameworks isn't growing. you know, that's that's like that's as helpful as learning about the details of some AWS api when you don't not want to understand how the internet works. you know, it's not. it's not reusable knowledge. it's a femoral knowledge. so like if you wanted to, you can actually use it as learning superpower, but also it can do the opposite. it know a natural thing. it's going to do with remove your competence over time.

</details>

**Speaker 1**: 我同意那是自然而然的事情。所以，这尤其是我个人的观点，因为你的职业生涯一直围绕着，基本上是教育人们忘记，你知道，技术和 **AI** 素养。所以这种深层行为与自动驾驶汽车非常相似，你知道，有一个临界点，在某个时刻，你不再投入，你不再关注，你获得了能力的下放，你得到了理解的消亡。这就是深层潜力。所以 **Anthropic** 几周前的研究完全与 **Dario** 相悖，因为它甚至说：“是的，研究中有几个人在问概念性问题，他们实际上在关注事物。”他们有学习的梯度，但大多数人没有。我的假设是，你知道，**AI** 编程的理想情况是，像我们这样，我们已经编写了几十年的软件。我们已经有了这种抽象的理解。我们正在将其应用于我们熟知的领域，我们可以进行规范。我们可以消除大量的歧义。我们可以跟踪，我们可以来回沟通，我们可以掌握整个过程。但发生的情况是，默认情况下，人们会进入自动驾驶模式，他们不知道发生了什么。这实际上让他们变得更笨。

<details>
<summary>Original English</summary>

**Speaker 1**: i agree that that's the natural thing. so and this, this is especially personal view, because your career has been around, basically educating people to forget, you know, technology in AI literacy. so the deep behavior is very similar to a self driving car that you know, there's this tipping point where, at some point, you're not engaged anymore, you're not paying attention and you get this delegation of competence, and you get understanding dead. that's the deep potention. so the study from anthropic couple of weeks ago. so contradicted diario completely because it even said, yeah, there were a few people in the study that were asking conceptual questions that are actually kind of keeping on top of things. and they have a gradient of learning, but most people didn't. and my hypothesis about that is, you know, the ideal situation for jn AI coding. is that like us, we've been writing ssoftware for decades. we already have this abstract understanding. we're using it in demands that we know well, and we can specify. we can remove loads of ambiguity. we can track and we can go back and forth, and we can we can stay in touch of the process. but what happens is that, that the default the track is for people to just go into this autopilot mode, and they got no idea what happening. and it's actually making them dummmi.

</details>

### AI与人类能力的平衡

**Speaker 0**: 我创建了第一家用于医学深度学习的公司，叫做 **DeepLytic**。那是在2014年左右，我们最初的重点是放射学。很多人担心这会导致放射科医生效率降低，或者放射学。我强烈反对这种看法，我对此做了很多研究，比如当飞机有了线控飞行，或者汽车有了防抱死刹车等等，会发生什么。如果你能成功自动化任务中真正可以自动化的部分，你就可以让专家专注于他们需要关注的事情。我们发现，在放射学中，如果我们能够自动识别长 **CT** 扫描中可能的结节，我们实际上做得很好，我们也确实做到了。然后，放射科医生就可以专注于观察这些结节，并决定它们是否恶性，或者如何处理它们。所以，这又是这些微妙的事情之一。所以，如果有些事情你可以有效地完全自动化，以一种你可以消除人类认知负担的方式，让他们可以专注于他们需要关注的事情，那可以是好事。你知道，我不知道我们在软件开发中的位置，因为我编码已经将近四十年了。所以我写了很多代码，我可以瞥一眼代码屏幕，然后，如果它不是很复杂的话，我就可以立即告诉你它做了什么，它是否有效。无论如何，我能够直观地看到可以改进的地方，你知道，需要注意的潜在问题。我不确定如果我没有写过大量代码，我是否能达到那个水平。所以，我现在发现真正能从 **AI** 中受益的人，要么是完全不会编程的初级人员，他们现在可以编写一些应用程序。只要他们能合理快速地利用当前的 **AI** 能力，他们就会很高兴。然后是像我或 **Chris Lattner** 这样经验丰富的人，因为我们基本上可以有一部分打字工作由 **AI** 代劳，你知道。还有一部分研究工作。而中间的人，也就是大多数人，大多数时候，这让我非常担心，因为你如何从 A 点到 B 点呢？是的，不敲代码。这可能吗？但我们没有这方面的经验。我们不知道这是否可能。你如何做到呢？就像回到学校一样吗？我们小学时不让孩子用计算器，这样他们可以锻炼他们的数学能力。作为开发人员，我们是否需要在头五年里自己写所有的代码？我不知道，但如果我不是一个有20年经验的开发人员，我就会经常问自己这个问题，因为否则你可能会在这个过程中让自己变得过时。

<details>
<summary>Original English</summary>

**Speaker 0**: i created a, the, the first deep learning for medicine company called dealytic. c acking was elect twenty fourteen, and our initial focus was on ideology, and a lot of people were worried. this would caused radiologists to become less effective or radiology. and i strongly felt the opposite, which is that i did quite a bit of research into this, like what what happens when re's like, fly by wire in eraplanes or antiop breaks in cars, whatever, if you can successfully automate parts of a task that really are automable, you can allow the the expert to focus on the things that they need to focus on. and we WW happhapps so radiology we found if we could automate identifying the possible nojeells in a long CT skcan. we were actually go at it, which we were. and then we've that the radiologist thing can focus on looking at the nodules and try to decide if they're malignant are what to do about it. so again, it's one of these sebtle things. so if it's things which you can fully automate effectively in a way that you can remove that cocktatative burden from a human so that they can focus on things that they need to focus on that can be good. you know, i don't know where we sit in software development because i've been coding for for forty bish years. so ve written a lot of code, and i can plance at a screen of code, and then don't don't less, it's something quite. we're not specisticated. i can immediately tell you what it does and whether it works. and whatever i can kind of see intuitively things that could be improved, you know, possible things to be careful love, and not sure i could have got to that point if i hadn't have written a lot of code. so the people i'm finding who can really benefit from AI right now, either really junior people who can't code it all who can now write some apps. they haven't 't hidden. it's long as they work reasonably quickly with the current i capabilities, then they happy. and then really experiences people people like me or like chris latina, because we can basically have a dosome of a typing for us, you know. and some of our research for us, people in the middle, which is most people, most of the time. it really worries me because how do you get from point eight of point b, yes, without typing code, it might be possible. but we don't have a we have no experience with that. we don't is it possible. how would you do it like? is it kind of like going back to school? we're a primary school. we don't let kids use calculators so that they develop their number muscle. do we need to do that for like first five years as a developer, you have to write all the coach yourself. i don't know, but if i wasn't it, the seen like two and twenty years of experience developer, i'll be asking that question of myself a lot, because otherwise you might be in the procesve, making yourself obsolete.

</details>

**Speaker 1**: 是的。好吧，这是关于知识的另一件事，这位 **Sai Suddhego** 先生说过。他说知识是不可替代的，这意味着它不能被交换。所以他的意思是，学习的过程在某种重要的意义上是不可还原的，对吧？所以你必须有经验，经验必须有摩擦。当我们建立世界模型时，我们真正学习，你，你。有一个短语叫做“现实的反击”。所以我们犯了很多错误，我们更新了我们的模型。我们只是在我们的模型中放置了这些连贯性约束，这就是我们学习使用核心代码的方式。这个过程中几乎没有摩擦，这正是 **Anthropic** 研究的发现，它说摩擦太少了。他们什么都没学到，对吧？

<details>
<summary>Original English</summary>

**Speaker 1**: yeah. well, this is another thing about knowledge that this sessor hadoggo guys said. so he said that knowledge is not fununible, and that which means they can't be exchanged. so what what he means by that is, the process of learning is in some important sense, not reducable, right? so you have to have the experience of the experience has to have friction. and when we build models of the world, and we actually learn you, you. there's this phrase reality pushes back. so we make lots of mistakes, and we update on models wewe're just placing these coherence constraints in in our in our model, and that's how we come to learn to use core code. and there's so little friction in the process that's exactly what they stustudy from. anthropics said is said there is so little friction. they didn't learn anything, right?

</details>

**Speaker 0**: 是的，没错。嗯，期望的难度是教育中出现的一个概念。但即使追溯到 **Ebbinghaus** 的工作，他是19世纪最初的间隔重复学习研究者，然后最近的 **Piotr Wozniak**。我们发现，记忆的形成需要艰苦的工作。所以，你知道，这就是为什么你会得到一些令人惊讶的结果，即过度复习通常是个坏主意，因为它很快就会浮现在脑海中。因此，在间隔重复学习中，像 **Anki** 和 **SuperMemo** 这样的算法会尝试在你要忘记之前安排抽认卡。这样，学习就很辛苦了。所以我为了尝试了解学习本身，学了十年的中文。我确实注意到了这一点，我用了 **Anki**。因为它总是安排我的卡片，就在我要忘记它们之前，所以复习总是非常辛苦。你知道，因为几乎所有卡片都处于即将忘记的边缘，这让我筋疲力尽，但天哪，它非常有效。我现在，十多年来没有学习，但仍然记得我的中文。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah. now exactly um desirable difficulty is the concept that kind of comes up in education. but even going back to the work of uebing house, who was the original respect, repeatea space learning guy in the one nine hundred and century. and then peta wasn't near more recently, it we find the same. we we know that memories don't get formed unless it is hard work to form them ah. so you know, that's way you kind of get this somewhat surprising result that is revising true often is a bad idea because it comes to mind too quickly. and so with repetitedly space learning with stuff like anki and supermemo, the algorithm tries to schedule the flashcards at a just before the moment you're about to forget. so then it's hard work. so II studied chinese for ten years um in order to try to learn about learning myself, and i really noticed this that i is dankiy. and because it was always scheduling my cards s. just before i was about to forget them, it was always incredibly hard work, you know, to do reviews because almost all the cards through once. so this on the verge of forgetting, i was absolutely exhausting, but my god, it worked well here i am. i don't really haven't done any study for, fifteen in plus years, and that's still all remember my chinese.

</details>

**Speaker 1**: 我知道。我可能会回到你的放射学例子。嗯，人们举的一个例子是呼叫中心。所以你知道，我们有这样一种观念，即一个组织中，我们有高智能角色和低智能角色。对我来说，智能就是知识的适应性获取和综合。所以我们假设，你知道，低智能角色是低智能角色。它不会适应，这意味着我们可以有一些组织的工作不会改变。所以我们可以自动化，我们不需要更新知识。我认为这实际上低估了，也许对于放射学例子来说，拥有这种整体知识，就像你知道的，在一个呼叫中心，有那么多奇怪的案例出现，有那么多奇怪的事情发生，然后这些信息会上报到组织中，我们会随着时间的推移进行适应。所以当你开始自动化事物时，你实际上失去了创造过程的能力，创造了最初的事物。你失去了组织中知识的进化能力。你实际上是在自断双臂。

<details>
<summary>Original English</summary>

**Speaker 1**: i know i may also me coming back to your radiology example. um like one example, people give is cool centres. so you know, we have this notion that an organization. we have high intelligence roles and low intelligence roles. and for me, intelligence is just the adapted acquliztion and synthesis of knowledge. so we assume that, that know the low intelligence roles and low intelligence roff. and it doesn't adapt, which means we can there are cercertain that that an organization does that do not change. so we could automate, and we don't need to update on knowledge. and i think that discounts actually may be with the radiology example that having this holistic knowledge, like you know, in a core centre, there are so many weird educaes that comin so many weird things happen, and that filt is up in the organization, and we adapt over time. so when you start to automate things and you actually lose the competence to create the process, which created the thing in the in the first place. and you lose the evolizility of that knowledge in your organization. you're actually kind of cutting your legs off.

</details>

**Speaker 0**: 是的，绝对是。嗯，所以在我的公司里，我总是告诉我们的员工，我几乎只关心你们个人能力的成长。你知道，我并不真正关心你们做了多少 **PR**，做了多少功能。就像 **John Ousterhout** 在最近发布的斯坦福周五讲座中有一个很好的例子，叫做“一点点斜率胜过很多截距”。这基本上就是说，你知道，在你的生活中，如果你能专注于做那些让你成长更快的事情，那比专注于你已经擅长的事情要好得多。你知道，那有那个截距。所以，我真正关心的，我认为也是对我公司唯一重要的事情，就是我的团队专注于他们的“斜率”。如果你只专注于在当前 **AI** 能力的极限下产出结果，你只关心“截距”。你知道。所以我认为这基本上是通过公司及其员工走向淘汰的道路。我真的很惊讶，现在这么多大公司的高管都在推动这个，因为感觉如果他们错了，他们很可能错了，而且他们无法判断自己是否错了，因为这是他们完全不熟悉的领域。他们从来没有在 **MBA** 课程中学过这些。他们基本上是在将自己的公司置于毁灭之中，我真的很惊讶，你知道，股东会让他们这样做。你会做出如此投机的举动。是的，我们现在就是这样，感觉很多公司会因为这种大规模技术而失败，这种技术导致他们无法再维护或构建他们的产品。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, absolutely. and um so i know know i know was in in my company. i just i tell our stuff all the time. almost the only thing i care about is how much your your personal human capabilities are growing. you know, i don't actually care how many PS you're doing everyfeatfeatres you're doing like there's that nice yeah johnose to help the tc yoga brrecently released some of his, his stanford friday take away lextures. and he has his nice one called a little bit of slope, makes up for a lot of intercept. just basically the idea that, that you know, in your life, if you can focus on doing things that caused you to grow faster, it's way better than focusing on focusing on the things that you 're already good at. you know, that has that i intercepcept. so the only thing i really care about, and i think, is the only thing that matters for my company is that my team i'm focusing on their slope. if you focus on just driving out results at the limit of whatever AI can do right now, you're only caring about the intercept, you know. so i think it's basically a pass to obsolessons through out the company and the people who in it. it's i've really surprise how many executives of big companies are pushing this now because it feels like if they're wrong, which they probably are, and they have nowhere to tell if they are, because this is an area they're not at all familiar with. they ever learned ted their mba thethey're basically setting up their companies to be destroyed and really surprised that you know, shareholders would let them do that. you'll set up such an incredibly speculative action. yeah, here we ah feels like a lot of companies you're gonna fail as a result of the amass tech that that causes them to not be able to maintain or build their products anymore there there.

</details>

**Speaker 1**: 很多人就像 **Francois Chollet** 一样。他真的，真的理解这一点。他理解这一点？你知道，他一直说这是关于领域认知模型和我们如何共同完善它的“模仿性分享”。关于分享，这是 **Generative AI** 编程的另一个大问题。所以理想的情况是我已经做了这个，我非常了解这个领域，我可以精确地指定，我告诉 **Claude Code** 去做这件事。我脑海中的模型并不重要。然后你进入一个组织，现在我需要分享我对所有其他代码的知识。我相信你的公司也有这种感觉，你需要知道。这种知识获取的瓶颈在组织中是一个非常严重的问题。所以，当只有我一个人的时候，我认为使用 **Claude Code** 可能会让我的生产力提高10倍左右。它绝对是魔法。我能理解为什么人们对此如此兴奋。但人们似乎理解这个瓶颈，以及它如何无法真正转化为许多现实世界的组织。

<details>
<summary>Original English</summary>

**Speaker 1**: lolos of folks out that are like france was relallike. he really, really gethis it. is he understand this? and you know, so he's always said that it's it's about kind kind of mmetic sharing of cognitive models about the domain and how we refine it together on the sharing thing. this is another big scaling problem with gena. i coding this. so the the ideal case i've done this, i know ddeain really well, and i can specify with exquisite detail, and i told cloud code gogoing 't do this thing. and the models in my mind doesn't matter um and then you go into an organization, and now i need to share like my knowledge of all of the other code. and i'm sure you have this sennual companwell like you need to that. this knowledge acquisition. bottneck is a real serious problem in an organizations. so when it's just me, i think i'm probably about of times more productive using clawd code. it's absolutely magic. and i can see why people are so excited about it. but people, i you seem to understand the bottonic and and how that doesn't really translate to many real world organization.

</details>

**Speaker 0**: 没有人实际创造出比以前多50倍的高质量软件。所以我们实际上对这个进行了研究。在人们实际交付的东西上，只有微小的提升，微小的提升。这是事实。显然，我是 **AI** 及其能力的热情支持者。但我的妻子最近也指出了一篇文章，所有让赌博上瘾的因素都存在于其中。是的，**Dogflow**。

<details>
<summary>Original English</summary>

**Speaker 0**: no one's actually creating fifty ty more high quality ality software than they were before. so we've actually stand to study of this. and there's a tiny up, tick, tiny upck and what people are actually shipping. that's the fact, obviously, i ve an enthusiasst of AI and what it can do. but also, my wife, actual recently pointed out an article, all of the pieces that make gambling addictive are present in. yeah, dog flow.

</details>

**Speaker 1**: 是的。是关于投票的吗？

<details>
<summary>Original English</summary>

**Speaker 1**: yeah, i was. it's it about voting.

</details>

**Speaker 0**: 是的。这是一种非常尴尬的局面，非常尴尬。你知道，最近几个月对 **AI** 驱动编程充满热情的人，当他们最终回头看看那些日子里我构建了多少需要热情的东西，我今天在使用吗？我的客户今天在使用吗？我今天从中赚钱了吗？几乎所有的钱都由影响者赚走，你知道，或者由生产这些代币的公司赚走。关于基于 **AI** 的编程，它就像一台老虎机，你有一种控制的幻觉。你知道，你可以精心设计你的提示、你的宏指令列表、你的技能等等。但最终，你拉动杠杆，对吧？你输入提示，然后会得到一些回复。就像“樱桃樱桃”，就像“哦，下次我会稍微改变一下我的提示。我会再多一些上下文。”再拉一次杠杆，再拉一次杠杆。这是一种巨大的事情。你偶尔会赢一次，就像“哦，我赢了。我得到了一个功能。”所以它拥有所有这些伪装成胜利的损失，一种略带讽刺意味的控制感，所有这些都是博彩公司试图在他们的游戏室里设计的。这并不意味着 **AI** 没用，但天哪，这很难说。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah. it's this really awkward situation where it's very awkwding know. it's very, very thuusitic about eepowered coding in recent months have totally changed their mind about it when they finally went back and looked it like how much stuff that i built during those days recquired enthusiasm, am am i using today? my customers using today? am i making money from today? almost all the money is being made by influences, you know, or by the companies that produce the tokens. they think about AI based coding is that it's like a slot machine and that you, you have an illusion of control. you know, you can get the craft you're prompt in your list of mc pays and your skills and whatever. and then but in the end, your ll vlavor, right you put in the prompt and something comes back. and it's like cherry cherry, as like oh, next time i'll changed my prompt a bit. i'd a bit more context, pull the lave or again pull the lavor. again, it's this darastic thing. you get the occasional win. that's like, oh, i won. i got a feature, so it's got. it's got all these horacks of like lost disguised as a wind of somewhat sarcastic feeling of control, all the stuff that gaming companies try to engineer into their gaming rooms. another, that means that AI is not useful, but gosh 's had to tell.

</details>

**Speaker 1**: 我知道。**Rachel** 只是，只是想澄清一下。她还说过，赌博的一个特点是你会自欺欺人地认为你对发生的事情有所了解。但实际上你没有。但让我们来看看乐观的情况。所以，我认为在受限的情况下，它非常有用。这些情况是我们理解的，并且我们可以施加特定的约束。但即使在这些情况下，你也可以争辩说，一方面，我们不会很快失业，因为你只是在戒瘾方面做更多的工作。我注意到了这一点。所以我曾进行过长达40小时的 **Claude Code** 马拉松会话。我确实感觉对它上瘾了，就像老虎机一样。你知道，它真的。

<details>
<summary>Original English</summary>

**Speaker 1**: i know, and rachel just just just to be close. sure. she also said that one of the hormarks of gambling is that you kind of delude yourself that you have some awareness. so what's going on? but it, but actually you don't, but let's do the bull case a little bit. so on the i do think in restricted cases it it is it is very useful. and these are cases where we understand. and and we can place constraints specificficbut. but even in those cases, you could argue on the one hand that we're not. we're not going to be unemployed anytime soon because you just just do more work on the addiction thing. i've noticed that. so i've had forty hour clawd code marathon sessions. and and i actually feel addicted to it like a spot machine. you know it, it really is,

</details>

**Speaker 0**: 而且你也很清楚。

<details>
<summary>Original English</summary>

**Speaker 0**: and they too absolutely yeah.

</details>

**Speaker 1**: 我从来没有感觉到在写作时如此疲惫，我实际上需要休息几天，因为它完全。

<details>
<summary>Original English</summary>

**Speaker 1**: i know it's and just i've never felt more drained writing, and i actually need to take a rest after it's like a few days rest, because it it completely.

</details>

**Speaker 0**: 我很糟糕，你知道，是的，当然。我取得了一些成功，对吧？实际上，我们过去几年一直在围绕我们认为会成功的领域构建整个产品，那就是当你处理相对较小的部分时，你可以完全理解并设计它们，并且你可以通过抽象来构建比你正在构建的更大规模的东西。我最近遇到一个非常有趣的情况，我只是在进行一种实验，基本上就是我们非常依赖一种叫做 **IPython Kernel** 的东西，它为 **Jupyter Notebook** 提供支持。**IPython Kernel** 从版本6升级到版本7，然后它就不工作了。它不工作了。我们尝试使用的两个产品，一个是现在叫做 **ND Classic** 的原始 **Jupyter Notebook**，另一个是我们自己的产品 **Solve**。它们会随机崩溃。**IPython Kernel** 有超过五千行代码。它是非常复杂的代码，有多个线程、事件、锁、与 **IPython** 的接口，你知道，与 **ZeroMQ** 的接口，你知道，各种不同的部分，调试器。我无法理解它，我不知道它在哪里崩溃，所有的测试都通过了。我想知道 **AI** 能否解决这个问题，比如我总是对 **AI** 现在能独自处理多大的任务块感兴趣。结果证明答案是肯定的。我认为它可以做到，就像，我花了几个星期，我对 **IPython** 的实际工作原理没有太多理解，但我确实。这就像一个艰巨的任务，需要抽出单独的注释。所以答案是，在两个小时内，**Codex** 5点。我想那时是 **Copilot** 2，或者也许是3，刚刚发布，做不到。然后我花了200美元一个月购买了 **GPT-3.5 Pro** 来解决问题。所以通过在这两款软件和这两个模型之间来回切换，我在几周内解决了问题，而且很幸运，可以说，这根本不令人满意，感觉很累，而且有压力，因为我无法真正控制它。但有趣的是，我现在处于这样一个境地：我拥有唯一一个能够正确运行 **Python Jupyter Kernel** 的实现，据我所知，它使用了新的版本7协议改进。现在，这很令人着迷，因为我们没有一种关于如何处理的软件工程理论。现在，比如说，这是一段 **AI** 理解的代码。我是否要将我公司的产品押注在这上面？答案是：我不知道，因为我不知道该怎么做，没有人经历过这种情况。比如说，它会有内存泄漏吗？如果 **Mind** 改变协议，它一年后还会工作吗？会有一些奇怪的边缘情况会毁掉一切吗？没有人知道，因为没有人理解这段代码。这是一个非常奇怪的情况。

<details>
<summary>Original English</summary>

**Speaker 0**: and i re's crap, you know, yeah, definitely. i had some successes, right? and so in fact, we've spent the last couple of years building a whole product based around where we know the successes are going to a be, which is when you're working on recently, small pieces that you can fully understand and that you can design, and you can build up your only only as abstraction to create things that are bigger than the patthat. you're building out of had a very interesting situation recently where i just kind kind of experiment, basically, which is we we rely very heavily on something called ipe kernel, which is the thing that's powers, stupid and nobooks. and they're been a major version release of vii pacanal from six to seven, and it stopped working. and it stopped working. and both of the products that we were try to use it with. one was whowas called today ND classic, which is see original jupiter dotebook, and then our own product called solve it. it were just ranomly crash um and ipad canandls over five thousand lines of code. it's very complex code multiple threads events, locks interfaces with i python, you know, with with said MQ, you know, all kinds of different pieces, debag pie. and i couldn't get my head around it, and i couldn't see where it was crashing the test to all passing. i wonder if AIE consolve this get us like i'm always interested the question of like how bigger chunk today. i handle on its own right now. the answer turned out to be. yes. i think it can just it was like, so it's been a couple of weeks. i didn't develop a lot of understanding about how ipad phone or really work in the process, but i did. it's been quite a child kind of pulling out separate comment like, so the answer was in two hours codex five point. i think it was popwite two at that time or maybe three year, just come out, couldn't do it. then if i got the two hundred dollar a month, GPT five point three pro to fix the problems equal. and so by rolling back between those two pieces of software and those too much models, i could get things working uh over a couple of week's period and luck. y say, wasn't at all, thought it very tiring, and it felt stressed because it wasn't really in control. but the interesting thing is, i now am in a situation where i have the only implementation of an of a python jupparkernel that actually works correctly as fas. i can tell with these new version, seven protocoal improveonments. and now like this is fascinating because we don't have a kind of a software engineering theory of what to do. now, like here's a piece of code that, that would understands. am i going to bet my company's product on it? and i the answers, i don't know because like II don't like II don't know to do do now, no one's like been in this situation. and like, will it does it have memory leagues? will it still work a years time if this mind to change the protocol? is there some weird edge case that's going to destroy everything? no one knows because no one understands his code. it's a really curious situation.

</details>

### 软件工程的挑战与AI的局限性

**Speaker 1**: 我的意思是，首先，我们应该承认控制的恶意侵蚀。所以在一开始，你只有10%的 **AI** 生成代码，然后你就可以看到它如何逐渐增加。然后在某个时候，六个月后，一个 **PR** 进来，现在你知道，60%的代码是 **AI** 生成的。然后你会看到发生了什么，你看到自己慢慢变得脱节。但对于这种情况，你知道，在 **AI** 中有一个叫做功能主义的观点，我们不在乎智能的东西是由什么组成的，只要它能做所有正确的事情。那么我们就会知道，你知道，我们会说那是 **AI**。软件也是一样。所以乐观的情况是，我理解需求，我不需要编写，不需要知道如何编写快速排序算法。我只需要。我只需要理解它。然后，你知道，我只需要有所有这些测试，它需要投入部署。这些事情需要发生。在那个时候，你知道，我并不真正关心。我也可以。

<details>
<summary>Original English</summary>

**Speaker 1**: it mean festival, we should acknowledge the peninicious erosion of control. so at the very beginning, you have ten percent AI generated code, and then you can just see how it creeps up and up. and then at some point, six months down the line PR comes in. and now you know, sixty percent of the code is i generated. and and and you see what you see what happens you, you see slowly become disconnected. but the bullcase for this, you know, in AOI, there is an idea called functionalism that we don't care what the intelligent thing is made out of as long as it and does all of the right things. then we know, you know, we would say it's AI, and it's the same thing of software. so the bull cases II understand the demand, i don't need to rights and don't need to know how to write the quick sore alaloriththm. i just need to. i just need to understand it. and then and then you know, so i just need to have all of these tests, and it needs to go into deployment. and these things need to happen. and at that point, you know, i don't actually care. and i could also,

</details>

**Speaker 0**: 我很喜欢这个说法，我很喜欢这个说法，但你的说法实际上是，软件工程当然很重要。因为软件工程就是关于找到这些组件是什么以及它们应该如何行为，然后如何将它们组合起来创建一个更大的组件。然后如何将它们组合起来创建一个更大的组件。如果我们做得好，十年后，我们可能会拥有比我们今天所能想象的强大得多的软件。但你真的需要非常出色的软件工程。是的，你需要小心。我认为最终，就像 **IPython Kernel**，我发现，例如，它只是一个更大的项目，对吧？因为最终，原始 **IPython Kernel** 的创建者无法创建一组能够正确测试它的测试。因此，现实世界的下游项目，包括原始的 **ND Classic**，你知道，也就是 **IPython** 的起源，也无法再运行。所以，这就是我们现在在开发方面的重点。它是找到合适大小的组件，并确保它们是正确的组件，知道如何识别这些组件是什么以及如何设计它们，如何将它们组合起来，这实际上通常需要几十年的经验才能真正擅长。嗯，对我来说也是如此。我在大约二十年的经验后才在这方面变得相当擅长。是的，大问题是，如何建立软件工程能力，这现在比以往任何时候都更加重要？它们是编写计算机软件的人和不擅长编写计算机软件的人之间的区别，这感觉是一个具有挑战性的问题。

<details>
<summary>Original English</summary>

**Speaker 0**: i quite that i quite that be clear. i quite like that framing, but you're what that actually does says, well, software engineering sure is important. then because after engineering is all about finding what those pieces are and how they should behave, and then power, you can put them together to create a bigger piece. and then how you can put them together to create a bigger piece. and if we do that well that in tenious time, we could have software that it's far more capable than anything we could even imagine today. but you're really gonna get that we're really great sofoftware engineering. yeah, you want to be careful. i think in the end, like i pad coranel, i'm finding, for example, it's just two bigger pace, right? because in the end, the time that made the original ipc ernewe're not able to create a set of tests that correctly exercised it. and therefore, real world downraam projects, including the original NA classic hknow, which is what ipc cha was exjected from, didn't work anymore. so this, this is kind of where our focuses are now on the development side at that answer. i it's finding the right size pieces and making sure they are the right pieces lowing how to recognize what those pieces are and how to design them, how to put them together is actually something that normally requires some decades of experience before you really good at it um saying it's true for me. and where can i got pretty good at it after maybe twenty years of experience? yeah, the big question is, like, how do you build the software engineering chops, which are now even more important than theyever been before? they're the difference between somebody who's good at writing computer software. and somebody who's not that feels like a challenging question.

</details>

**Speaker 1**: 我知道还有这样一种观念，即有许多不同的方法来抽象和表示事物。你知道，世界是一个非常复杂的地方。也许我们抽象和表示软件的方式，大多反映了我们自身的认知局限性，对吧？即使在科学领域，在物理学中，你往往有很多相当还原论的世界建模方法。然后你有了复杂性科学，它只是拥抱事物建构性、解构性的、你知道的、非线性的本质。我认为今天的许多软件，我们并不理解，对吧？所以，例如，有许多使用 **Actor** 模式的全球分布式软件应用程序。这基本上就像一个复杂系统，对吧？我们理解它的唯一方法就是通过模拟和测试，因为没有人真正知道这些东西是如何组合在一起的。所以你可以争辩说，我想，作为一个乐观的观点，也许我们已经在软件工程的顶端做到了这一点，而这正是我们最终想要做的。

<details>
<summary>Original English</summary>

**Speaker 1**: i know there's also this notion that there are so many different ways to abstract and represent something. you know, the world is a very complex place. and maybe the way we've been abstracting representing software is mostly a reflection of our own cognitive limitations, right? and even in the sciences in in physics, you tend to have a lot of quite reductive methods of modeling the world. and then you've got complexity science, which is just embracing the constructive disability tive, you know, narly nature, tive of things. and i think a lot of software today, we don't underunderand right. so for exexple ple there, many globally distributed software applications that use the actor pattern 你的. and this is just this is it's basically like a complex system, right? and the only way we can understand it is by doing simulations and tests, because no one actually knows how one of these things fit together. so you could argue, i guess, as a bullcase that maybe we already are doing this at the top of the suffiengineering, and that is what we want to do. eventually anyway,

</details>

**Speaker 0**: 是的，我可能会说不是。你看到像 **Instagram** 这样的公司，以及 **SAP** 如何主导他们的领域，拥有十名员工，却在摧毁像 **Google** 和 **Microsoft** 这样的大公司。我会说这种在大型公司中构建软件的方式实际上正在失败。我认为我们正在看到许多这样的大公司变得越来越绝望。你知道，例如，**Microsoft Windows** 和 **Microsoft Office** 的质量在过去五到十年中明显严重恶化。当你回到 **Dave Cutler** 检查 **NT** 内核每一行代码并确保它完美无缺的时候，它是一段优雅而卓越的软件。你知道，我不认为世界上有人会说 **Windows 11** 是一段优雅而卓越的软件。所以实际上，我认为我们确实需要找到这些我们完全理解的小组件。我们确实需要构建它们。问题来了，嗯，**AI** 在这方面做得不好。所以我经验性地认为它们在软件工程方面真的很糟糕。我认为这可能永远都是真的，因为你知道，我们经常要求它们处理超出其训练数据范围的事情。你知道，如果我们试图构建以前从未构建过的东西，并且以比以前更好的方式构建。我们正在说：“不要只是复制训练数据中的内容。”所以，嗯，这又是很多人感到困惑的地方，因为他们看到 **AI** 在编程方面做得很好。然后你就会想：“哦，那也是软件工程。”是的，它一定擅长软件工程。但它们是不同的任务。它们之间没有太多重叠，也没有任何当前的经验数据表明 **LLM**s 在软件工程方面正在获得任何能力。每次你看到它们完成的软件工程作品时，比如 **Mozilla Firefox**，或者 **Anthropic** 创建的 **Swift** 编译器，我读过很多这些东西的源代码。嗯，**Chris Lattner** 对编译器示例更熟悉。嗯，但它们是非常非常明显地复制了已经存在的东西。所以这是一个挑战。你知道，如果你想构建一些不仅仅是复制品的东西，那么你不能把它外包给 **LLM**。没有理论依据相信你永远能够做到。也没有经验数据表明你永远无法做到。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, i'd say probably not you see companies like instagram and what's sap dominate their sectors, wealth having ten stuff and beiding companies like google and microsoft in the process. i would argue this way of building software in very large companies is actually failing. and i think we're seeing a lot of these very large companies becoming, you know, increasingly desperate. and you know, for example, the quality of microsoft windows and microo s has very obviously deteriorated greatly in the last five to ten years. you'll back when dave katler was looking at every line of the NT kernel and making sure it was beautiful it. it was a elegant and marvelous pece of software. you know, i don't think as anybody in the world, he's going to say that windows eleven is an elegant and marvelous pece of software. so actually think we do need to find these smaller components that we do fully understand. and that we need to build them up. and here's the problem. um AI is no good at that. so and so i say that imirically they're really bad. it's software engineering. then i think that's possibly always going to be true, because you know, we're we're asking them to often outside outof their training data. you know, if we trying to build something that literally hasn't been built before and it in a better way and has been done before. we're saying, like, don't just copy what was in the training data. so um and again, this is a confusing point for lot of people because they see AI been very good coding. and then you think like all that's software engineering. yeah, it's was god must be good a software engineering, but it's they're different tasks. there's not a huge ament of overlap between them, and there's no current empical data to suggest that LM ms are gaining any compedency at software engineering. every time you look at a piece of soft engineering. they've done like the browser for examwhich, um curse a created or the sea compiler, which um antropic can created, like i've read the source code of those things quite a bit. um chris lton is much more than ly with the compiled. examples may. um but there are their very, very obvious copies of things that already exist. so that's a challenge. you know, is if you want to build something that's not just a copy, then you can't outsource that to an LM. there's no theoretical to reason to believe that you'll ever be able to. and there's no empical data to suggest that you'll never be able to.

</details>

**Speaker 1**: 是的。我认为这次对话的重点是，我相信你也会同意，我们需要 **AI** 和人类共同合作，对吧？因为人类提供理解，以及我们之前说的所有关于知识的东西。但我们仍然可以将 **AI** 作为工具来使用。但我们需要，我们需要设计操作模型或工作方式，使我们不至于削弱我们的能力和理解，对吧？所以这是一个非常，非常重要的观点。

<details>
<summary>Original English</summary>

**Speaker 1**: yes. i think the punch line of this conversation is, and i'm i'm sure you degree with this that we need to have the combination of AI and humans working together, right? because the huhus s provithe, the understanding and all of the stuff we were saying about knowledge, but we can still use AI as a tool, but we need to we need to design operating models or ways of working that make that we say we we don't want to diminish our competence and understanding, right? it's so it's a very, very ine light.

</details>

### 交互式开发环境的重要性

**Speaker 0**: 这正是我们的重点，我们都专注于教学和我们内部开发。我二十年来一直在研究的东西，最终证明了它是这一切的关键。**Stephen Wolfram** 应该得到这个荣誉，他是创建笔记本界面的人，尽管很多想法也可以追溯到 **Smalltalk**、**Lisp** 和 **APL**。基本上，这个想法是，当人类能够实时操作计算机内部的对象，研究它们，移动它们，并将它们组合在一起时，人类可以使用计算机做更多的事情。是的，**Smalltalk** 就是关于这个的，你知道，关于对象，**APL** 也是关于数组的。**Mathematica** 基本上是一个超级强大的 **Lisp**，它还添加了这个非常优雅的笔记本界面，允许你将所有这些构建成一个活文档。嗯，所以几年前我构建了这个叫做 **NBDEV** 的东西，它是一种在这些笔记本界面、这些丰富的动态环境中创建生产软件的方法。我发现这极大地提高了我的编程效率，即使我从未全职从事编程工作。当你查看我的 **GitHub** 贡献时，我认为 **GitHub** 会提供一些统计数据。我感觉自己是澳大利亚效率最高的程序员之一，你知道，它正在发挥作用。我构建的很多东西都有很多人在使用，因为它是一种如此丰富、强大的构建方式。所以事实证明，我们发现如果你将 **AI** 和人类放在同一个环境中，一个丰富的交互式环境中，**AI** 也会表现得更好，这也许并不令人震惊。但正常情况下，比如你使用 **Claude Code**，我知道你用。它是一款非常好的软件。但我们给 **Claude Code** 提供的环境非常类似于人们四十年前拥有的环境。你知道，它是一个基于行的终端界面。你知道，我可以使用 **Midnight Commander**。你知道，大多数时候。现在它只是使用 **Bash** 工具，这再次非常强大。我一直使用 **Bash** 工具，**CI** 工具，但它仍然只是将文本文件作为与世界的接口。它真的很糟糕。所以我们把人类和 **AI** 放在一个 **Python** 解释器中。嗯，现在突然之间，你拥有了完全的力量，非常非常优雅、富有表现力的编程语言，人类可以用它来与 **AI** 交流。**AI** 可以与计算机交流，人类可以与计算机交流。计算机可以与 **AI** 交流。就像你拥有了如此丰富的东西。然后我们让人类和 **AI** 实时构建彼此可以使用的工具。对我来说，这就是重点，对吧？这就像创造一个环境，让人类可以成长、参与和分享。对我来说，当我使用 **Solve** 时，它与你描述的 **Claude Code** 体验完全相反。几个小时后，我感到精力充沛，快乐和满足。

<details>
<summary>Original English</summary>

**Speaker 0**: that's that's paying our focus, and we both focus on that for teaching and for own internal development. the stuff i've been working on for twenty years has turned out to be the thing that makes this all work. stephen wolfm should get credit for this. who was the guy that created the notebook into face, although also lots of ideas, kind of go back to smsmall talk and lisp and APO the basically the idea that human can do a lot more with a computer when the human can like manipulate the objects in inside that computer in real time, study them move them around and combine them together. yeah, that's what small talk was all about, you know, with objects and APO with a same with a raise thethebetica. basically is a superpowered list, which they're also added on this very elegant notebook interface that allowed you to construct is a living document out of all this. um. so i build this thing called NBDFA few years ago, which is a way of creating production software inside these notebook interfaces inside these rich dynamic environments. and i found that made me dramatically more um productive as a programmer ing like even even though i've never been a full time. programmer is my job when you look at my kind of get have breail up, what i think get have producsome statistics about it. and i was like just about the most productive programmer er in australia, you know, like it's working. and a lot of the stuff i build has lots and lots of people use it because it's such a rich, powerful way to build things. and so it turns out weve ve discovered that if you put ai in the same environment with a human i get in AA, rich interactive environment, AI is much better as well, which perhaps isn't shocking to hear. but that the normal, like if you use cloud code, i know you do. and it's a very good piece of software. but the environment we give cloud code is very similar. the environment that people had forty years ago. you know, it's it's a line based terminal interface. you know, i can use MCP. you know, have most of the times. it's just nowadays uses bash tools, which again, very powerful. i love bash tools. i use them all the detail CI tools all the time, but it's still just it's using text files. you know, as it's as it's interface to the world, it's it's it's really mega. so so we put the human in the AI inside a python interpreter. um and now suddenly you've got the full power power, very, very elegant, expressive programming language that the human can used to top the ii. the ii can top the computer, the human can tok to the computer. the computer can top the ii like you have this really rich thing. and then we let the human and the II in real time build tools that each other can use. and that's what it's about to me, right? it's about like creating an environment where humans can grow and engage and share. it's like for me when i use sovet. it's the opposite of that experience. you describe with cloud code after a couple of hours. i feel energized and happy and fulfilled.

</details>

**Speaker 1**: 我给你我的观点。我认为你在这里指出的是，拥有一个交互式、有状态、能给你反馈的环境是神奇的。那是因为我们的大脑可以做一定量的，你知道，工作。所以我们实际上通过与现实的精炼和测试来思考，这就是为什么我攻读博士学位时使用 **Mathematica** 和 **MATLAB**。我同意。所以如果我们有了这个封装环境，你知道，这是 **MATLAB**，做一个图像绘制，你知道，做一个改变。现在看起来就是这样。这实际上是一种很好的方式，可以完善我对某个事物的心理模型。但是 **Claude Code** 做了很多这样的事情。我认为这主要是一个技能问题。我认为那些有效使用 **Claude Code** 的人会这样做。我写了一个叫做 **LeadScript** 的联系人管理系统。当我制作纪录片时，它可以通过，它可以通过拉取字幕，然后我就可以验证这些说法。你知道，识字的一部分就是理解语言模型的不对称性，对吧？所以当你给它们一个鉴别任务时，它们实际上做得很好。所以如果我告诉一个子代理去验证每一个独立的说法，它会更准确。验证是在生成模式下进行的。我生成了一堆说法，然后是这种有状态的反馈机制。再说一次，你知道，我可以在旁边有一个图式化的 **Excel** 导出，我可以在旁边有一个应用程序，它可以进行可视化，这是一个反馈循环。对我来说，这是一种 **AI** 素养。那些优秀的 **AI** 人员已经在做这些了。

<details>
<summary>Original English</summary>

**Speaker 1**: i give you give you my site. i think that the thing that you're pointing to here is there's something magic about having an interactive stateful environment that gives you feedback. and that is because our brains kind of they they can do a certain, you know, unit of work. so so we actually think through refining and testing with reality, and that's why i'm i'd doing my PHDI use mathemagic and mat lalab. and i agree. so if we got this rapper environment and you know, here's the matrio, do an image plot, you know, do a change. this is what it looks like now. and it's actually a wonderful way to kind of just just refine my mental model about something. and but but claud code does a lot of this stuff. II think it's mostly a sill issue. i think the people that use cloud code effectively do this. i've wrwrten a contcontact management possipossible it possipossible possipossible so you i've writa contact management system called led script. and when i'm putting together a documentary video, it can go, it can it can pull transcripts, and then i can verify the claims. and you know, part of the illiteracy is just understanding the a symmetry of language models, right? so when you give them a sort of discriminative task, they're actually quite good. so if i tell it in a subbagent to go and verify every individual claim, it's much more accurate. vify was in genereration mode. i was generated a bunch of claims and the stateful feedback thing. again, you know, i can have some kind of like schematized examell dump. and i can have like a an application here on the side, which is visualizing, and it's like a feedback loop. and for me, this is an AI literacy thing. the the good people AI are already doing this.

</details>

**Speaker 0**: 是的。我完全同意你的观点。我同意你可以在 **Claude Code** 中做到这一点。我同意这是一种 **AI** 素养，至于你是否能做到。但 **Claude Code** 并不是为此设计的。它在这方面做得不好。它也没有使其成为自然的工作方式。我不想说这是一个 **AI** 素养问题，因为这就像说：“哦，这是你的问题。”对我来说，如果一个工具没有让一个人自然而然地变得更博学，更快乐，更深入地理解和连接他们正在做的事情，那么这就是一个“谁的问题”。工具的设计应该如此。所以很多模型和工具都被明确地评估为：“我能否给它一个完整的工作，让它自行完成所有事情？”这在我看来是一个巨大的错误。这应该是：“你有没有评估过人类是否因此对一个主题有了更深的理解？”你知道，这样他们将来可以很容易地构建东西。

<details>
<summary>Original English</summary>

**Speaker 0**: yes. so i thought fully agree with you. i agree. you can do it in cloud coand. i agree, it is AA literacy thing as to whether you can, but also cloud code was not designed to do this. it's not very good at it it, and it doesn't make it the natural way of working with it. i don't want to say it's an a literacy problem because that's like saying, like, oh, it's a you problem to me, if at all, is not making it the natural way for a human to become more knowledgeable, more happy, more connected with a deeper understanding and a deeper connection to what they're working on. that's a whoproblem that, that should be how tools are designed to work. so so many models and tools expressely are being evaluated on. can i give it a complete piece of work and have it to go away and do the whole thing, which feels like a huge mistake to me. this is, have you evaluated whether a human comes out the other end with a deep understanding of a topic, you know, so that they can really easily build things in the future.

</details>

**Speaker 1**: 我同意所有这些，但还有另一个有趣的角度，那就是 **Joe Gruce** 有一个著名的演讲。我们讨论过这个。他说笔记本很糟糕。从软件工程的角度来看，它们真的很糟糕。在当时，也许在某种程度上现在仍然是，我同意他的观点，因为我，嗯，你知道，我做过很多开发工作，我曾在大型组织工作过，试图弄清楚我们如何弥合数据科学和软件工程之间的鸿沟，而 **Claude Code** 已经更倾向于软件工程方面。这意味着它创建了独立、无状态、可重复的工件，对吧？所以正如你所说，从教学的角度来看，因为我很高兴有这种有状态的反馈，因为我理解正在发生的事情。但我需要将其转化为可部署的东西。你能告诉我们你回应 **Joe Gruce** 的故事吗？那有点像一场灾难，不是吗？但请告诉我们那个故事。

<details>
<summary>Original English</summary>

**Speaker 1**: i agree with all of that, but then is the other interesting angle, which is that there there is famfamous talk by joe grooce. and we've talk about this, and he said that notebooks are terrible. they're really bad from a sufreiengineering point tity. and and at the time, and maybe still one out of certain extent, i agree with him, because 我 um you know, i've i've done m dedevelos i'worworin larlarge organzzations know trying to figure out how do we bridge like data science and softwer engineering and claud code is already more towards a sffer engineering side. and what that means is it creates eyedepopoant at stateless repeatteable artifacts right? so as you say from a pedogogical point of view, because i good having this stateful feedback, because because i understand what's t's going on, but then i need to translate that into something which is deployable. and can you tell us the story of you responded to john gruce in new? and it was a bit of a fiasco, wasn't it? but just just tell us about that story,

</details>

**Speaker 0**: 他做了一个非常好的视频，叫做《我不喜欢笔记本》。嗯，那很搞笑。它做得非常好。是的，它完全是错误的。他说的所有笔记本做不到的事情，它们都能做到。他说的所有你不能用笔记本做的事情，我一直都在用笔记本做。所以那是一场非常好的，非常，非常不正确的演讲。所以我做了一个它的模仿作品，叫做《我喜欢笔记本》，其中我基本上复制了，并注明了出处，他大部分的幻灯片，并展示了它们是如何完全错误的。但我确实认为你的观点触及了核心，那就是软件工程的通常做法与科学研究和类似事情的通常做法之间的区别。而且我认为，我同意，这里存在着二分法。我认为这种二分法是一种耻辱，因为我认为软件开发做得不对。它以这种方式进行，即你大谈特谈可重复性。以及这些死气沉沉的页面。你知道，所有都是死代码、死文件。我永远无法像 **Bret Victor** 在他的作品中那样清晰地表达这一点。所以我鼓励那些没有看过 **Bret Victor** 作品的人去看。但是，他一次又一次地展示了，你所做的事情之间的直接联系，你知道，直接的视觉联系，就是它所代表的一切。你知道，他的使命就是确保人们拥有这种联系。这基本上也是我的使命。所以对我来说，传统的软件工程离这尽可能地远。我认为这很糟糕。我觉得这令人作呕，我觉得人们被迫以这种方式工作很悲哀，我觉得这不人道。我只是不认为它工作得很好。我的意思是，从经验上讲，它工作得不好，而且它对 **AI** 和人类来说都更差。以前并非如此，你知道，有了 **Alan Kay** 和 **Smalltalk**，还有 **Iverson**，以及 **APL**，你知道，还有 **Mathematica** 的 **Lisp**。对我来说，那是黄金时代，那时人们专注于如何让人类尽可能紧密地与计算机合作？你知道，这就是鼠标的来源，例如，你可以拖动和可视化计算机中的实体，事物可以移动。所以我感觉我们已经失去了这一点。我认为这真的很悲哀。是的，使用 **Claude Code** 等等，与它们合作的默认方式是深入研究它。就像：“好吧，有一个完整的文件夹文件。”你永远不会看它们。你与它的整个互动都是通过一个提示。这真的让我感到厌恶，就像我真的认为这不人道，我的使命和过去二十年一样，就是要阻止人们这样工作。

<details>
<summary>Original English</summary>

**Speaker 0**: you did a really good video called. i don't like noteooks. um it was hilarias. it it really well ddone. and yeah, it's totally wrong. and all the things he said, notebooks can't do they can. and all the things they said, you can't do with no books. i do with no books all the time. so it was a very good, very, very uuum incorrect talk. so then i did the kind of a parody of it called um i like notebooks um in which i basically copied with credit, most of his slides and and chold how every one of them was totally incorrect. but like i actually think you're coming about, it does come down to the heart of it, which is this difference between, like how software engineering is normally done. this is how scientific research and similar things is normally done. and i think and i agree, there is a dichoomy there. and i think that economy is a real shame, because i think software development is being done wrong. it's being done in this way, which is yell about reproduceability. and these like dead these dead paces. you know, it's all dead code dead files. i will never be able to express his one million of his clearly, as as bread victor has in his work. so i'd encourage people who haven't watch bread victor to to watch him, but know, know he, he shows again and again, how a direct connection, you know, a direct vistival connection with the thing you're doing is, is all that medits, you know, and that's his mission is to make sure people have that connection. and that's basically my mission as well. so for me, traditional software engineering is as far from that as it is possible to get. i think it's i think it's gross th. i find it disgusting, and i find it sad that people are being forced to work like that like i think it's humane. and i just didn't think it works very well. i mean, empirically it doesn't worfor very well, and it's much less good for AI as well as it's much less good for humans. it hasn't always been that way like it know with with alan, an k and small talk can ivson, and and app l, you know, lispible from with mathematica. to me, these was a golden days when when people were focused on the question of how do we get the human into the computer to work as closely with it as possible? you know, that's whether the mouse came from example, like you got like, like can drag and visualize entities in your computers, things things can move around. so i feel like we've lost that. i think it's really sad, yeah, with cloud code and stuff the the default way of working with them is go super deep into it. it's like okay. there's a whole folder follow files. she'd ever look at them your entire interaction with it is through a prompt. i literally discussed me like, i literally think it's it's inhumane, and it's my mission remains the same as it has been for, like twenty years, which is to stop people working like this.

</details>

**Speaker 1**: 我知道。但当我回顾过去时，我曾经和数据科学家一起工作。他们使用 **Jupyter Notebook**。我通常发现，我的意思是，如果你把它们提交到 **Git**，它看起来不会很好。大多数数据科学家不知道如何使用它。他们会乱序运行单元格，这意味着它无法重现。但问题是，我同意你可以在这个工作流程中使用它们，但这又回到了我之前说的。你知道，我们正在谈论核心传感器，它就像一个低智能的工作。你知道，那里的数据科学家，他们正在做智能工作的方式是，他们实际上正在创造一些不存在的东西。他们正在找出问题的控制点。他们实际上在一个知之甚少领域工作。但你现在可以争辩说，乐观的情况是，当数据科学家能够简洁地描述问题的控制点时，也许我们可以转向 **Claude Code**，我们可以正确地实现它。如何弥合这两个世界之间的鸿沟，那是一个关键的想法。

<details>
<summary>Original English</summary>

**Speaker 1**: i know, but but so costing my mind back, i used to work of data scientists. they were using jokes to notebook ks. what i found found. i typically, i mean, then then you couldn't if you check them into get, it wouldn't look very good. most of these daof scientists didn't know how to use it. they would run the cells out of border, which means it wouldn't be reproduced. but it what t's the things like that. the thing is, i agree with you that you can use them in this in this workflow, but it comes back to what i was same before about. you know, we 're talking about the core censor, and it being like a low intelligence job. you know, the data scientists out the reasway that they they are doing intelligent work is they are actually creating something that doesn't exist. they are figuring out the the contcontls of of problem. they're actually working in a domain that is poorly understood. but you could argue now the bull case is when the data scientists can sucsinically describe the controls of the problem. maybe we could go to cloud code, and we could implement the properly that how do bridge dge between those two world be be driterririidea ah,

</details>

**Speaker 0**: 就像，你知道，把人们从他们的探索环境中移除。你知道，研究和科学是通过人们建立洞察力而发展的。你知道，无论你听谁说，我们都知道无论是 **Anmman** 还是其他什么，你总是会听到伟大的科学家们如何通过建立心理模型来建立更深层次的直觉，这些直觉是他们通过与他们正在学习的事物互动而获得的。就像在 **Feynman** 的案例中，因为他是理论物理学家，他无法真正拿起一个旋转的时钟，但他确实研究了旋转的盘子。你知道，你必须找到方法来深入地与你正在研究的东西互动。我见过七次数据科学团队，因为你说得对，数据科学团队。我非常熟悉 **Git**，也非常熟悉他们不需要理解的东西。嗯，所以通常情况下，我见过软件工程师成为他们的经理，他们的解决方案就是告诉他们都停止使用 **Jupyter Notebook**。现在他们必须使用所有这些可重现的巴拉巴拉，你知道，虚拟的巴拉巴拉。他们一次又一次地摧毁这些团队。我见过这种情况一直在发生，因为解决方案不是制造更多的纪律和官僚主义，而是解决实际问题。所以，例如，我们构建了一个叫做 **NB Diff Merge** 驱动的东西，很多人没有意识到这一点。但实际上，嗯，笔记本非常友好 **Git**。只是 **Git** 没有附带一个用于它们的合并驱动。所以 **Git** 只附带了一个用于基于行的文本文件的合并驱动，但它是完全可插拔的。所以你可以很容易地插入一个用于 **JSON** 文件的合并驱动。所以我们写了一个。所以你可以比较，你知道，当你使用我们的合并驱动进行 **Git Diff** 时，你会看到单元格级别的差异。如果你遇到合并冲突，你会得到单元格级别的合并冲突，笔记本始终可以在 **Jupyter** 中打开。嗯，**Andy Dime** 也独立实现了同样的功能。所以是的，有一些问题需要解决，你知道，但解决方案不是抛弃 **Bret Victor** 的想法，让人们远离他们的探索工具，而是修复探索工具。我认为所有软件开发人员都应该使用基于探索的编程来加深他们对正在处理的事物的理解，这样他们就能对他们正在构建的系统有一个非常强大的心理模型。然后他们就能想出更好的解决方案，以更增量的方式，而不是经过测试。我基本上从来不需要使用调试器，因为我基本上从来没有 bug，这不是因为我是一个特别优秀的程序员。而是因为我建立了一步一步的小步骤，每个步骤都有效，我可以看到它有效。我可以与它互动。所以没有 bug 的空间。

<details>
<summary>Original English</summary>

**Speaker 0**: like, you know what to remove people from their explororatory environment. you know, research and science is developed by people building insight. you know, whoever you listen to, we know whether be a anmman or whatever like this is if you always here from the great scientists, how they build deeper intuition by by building mental models, which they get overtime by interacting with the things that they're learning about that, like in fineman's case, because it's theoretical physics, he couldn't actually pick up speeding clock, but he did literally study speding plates. you know, you gota a find ways to deeply interact with with what you're working with. like seven times, i've seen data science teams because you right, data science teams. i'm very familiar with kit, and i'm very familiar with things that they don't need to understand. um so often, i've seen a software engineer will become their manager, and their fixed to this will be id to tell them all to stop using jupiter notebooks. and now they have to use all these reproducable blaablavivirtubut. you know, virtual end of blablah. they destroy these teams over over again. i've seen this keep happening because the solution is not create more discipline and bureaucracy. it's solve the actual problem. so for example, we we built a the thing called an ND merge driver, which a lot of people that realize this. but actually, uh, no books extremely get friendly. it's just that get doesn't ship with a merge driver for them. so get only ships with a merge driver for a line based text files, but it's fully plugble. and so you can easily plug in in one for jason files instead. and so we wrote one. and so you can diff, you know, when you get to get diff withour merge driver, you see sell level difts. if you get a merge conflict, you get surge level lelevel merge conflicts that the notebook is always openable in jupiter. um andy dime did the same things of to independent implementations of this. so yeah, there were problems to solve, you know, but the solution to it was not throw away brebrevicicor's ideas and make people further away from from their exploratory tools, but to fix the expliratory tools. and i think all software developers should be using explloitatory based programming to deep en, their understanding of what they're working with so that they end up with a really strong mental model of the system that they're building. and that working with and then they can come up with better solutions more incrementally than are tested. i basically ever have to use a debegga because i basically never have bugs, and it's not because i'm a particularly good programmr. it's because i build up small little steps and each step works, and i can see it working. and i can interact with it. so there's no room for bags,

</details>

**Speaker 1**: 你知道，你知道，我对此很纠结，因为我同意你的观点，而且我也对那些声称组织会趋同于某种做事方式，不再需要进化的人持怀疑态度。他们不再需要适应。你知道，创新就是适应性，我们应该尽可能地增加适应性的表面积。我们需要不断尝试新想法，找到这些约束的人。但同时，我们需要使用云，我们需要使用 **CI/CD**。我们需要将这些东西投入生产。

<details>
<summary>Original English</summary>

**Speaker 1**: you know, you know, i'm so torn on this, because i agree with you, and i'm also scheduical of people who say that organizations that they they converge on to ways of doing things, and they no longer need to evolve. they no longer and need to adapt. you know, innovation is adaptivity, and we should should rease the surface area of adaptivity as much as we possibly know cancer. we need people that are constantly testing new ideas, finding these constraints. but by the same token, we need to use the cloud, we need to use CRCD. we need to get this stuff into production.

</details>

**Speaker 0**: 是的，这样做绝对没问题，就像绝对没有问题一样。所以 **BDF** 开箱即用支持 **CI** 集成，而且测试就在那里，因为源代码和笔记本的整个探索过程，比如 **API** 如何工作，你知道，调用函数时会是什么样子，函数的实现，文档示例，通常测试都在一个地方。所以在这个环境中做一名优秀的软件工程师要容易得多。嗯，所以，就像两者兼顾，你知道。

<details>
<summary>Original English</summary>

**Speaker 0**: yeah, so do theit's absolutely like there's absolutely know like it. so BDF chips with out of the box CI integration and the the tests are literally there like, because the sources and notebook the entire exploration of like hatsses API work, you know, what does it look like when you call it the implementation of the functions, the examples of the documentation, often the test of them are in one place. so it's much easier to be a good software engineer in this environment. um so yet like to do do both, you know.

</details>

### AI存在的真正风险

**Speaker 1**: 所以我记得，当时有一个关于“生存风险应该是一个紧急优先事项”的声明，签名人包括 **Hinton** 和 **Demis Hassabis** 等人。你当时基本上是反驳了这份声明。那是和 **Aravan** 一起，你知道，那位关于蛇和鹰的家伙。告诉我那是怎么回事。你真的认为我们应该担心 **AI** 的生存风险吗？

<details>
<summary>Original English</summary>

**Speaker 1**: so remember, there was there was that existential risk should be an urgent priority, and it was signed by fix like hinton and and demiscs sobis. and you responded um basically with a rebuttle. and that was with aravan. you know, the snake oal guy tell me about that. you do think we should be worried about AI exexistentirisst.

</details>

**Speaker 0**: 我的意思是，那是在特定时期，不是吗？我觉得事情有点变化了，天哪。我觉得我们没有和 **Aravan** 讨论，但总的来说，你所属的那个群体可能赢了。现在我们有其他问题要担心。但你知道，基本上，在那个时候，主流叙事是 **AI** 即将变得自主，现在可能变得自主，并摧毁世界。这在很大程度上源于 **Eliza Yudkowsky** 的工作，我认为这在很多层面已经被证明是错误的。

<details>
<summary>Original English</summary>

**Speaker 0**: i mean, that was a certain time wasn't. and i feel like things have changed a bit god. i feel like we we not spend an avvan, but broadly aaking community of which you're part kind of probably won that. now we have other problems to worry about. but you know, basically, at that point, the prevailing narrative was AI is about to become autonomous st, could become autonomouous at the moment, and great destroy the world. so very much comes from. you know, eliza you kcaskiis work, which i think clearly, it's been shown to be wrong that many levels this point that they would review that,

</details>

**Speaker 1**: 显然。

<details>
<summary>Original English</summary>

**Speaker 1**: obviously,

</details>

**Speaker 0**: 嗯，他们会的。是的，这是那种他们总是可以拒绝的事情，就像任何事情都是邪教一样，除非你给它一个日期，然后日期过去了。

<details>
<summary>Original English</summary>

**Speaker 0**: well, they would. yeah, it's one of those things that they can always refuse, just like any doing stay cult unless less you give it a date and the date passes.

</details>

**Speaker 1**: 所以即使我也稍微更新了一点，从某种意义上说，我如今会说，这些模型可以在受限领域被认为是智能的，**Archallens** 证明了这一点。所以如果你给问题设置约束，你就可以更快地走向知识，甚至代理。你，你可以给它一个规划者。如果你知道你要去哪里，你就可以更快地到达那里。但这并没有帮助你，你可以拥有世界上所有的智能和代理，但如果你没有知识和约束，那么你就会更快地走向错误的方向。我认为他们似乎没有意识到这些模型并不真正了解世界。

<details>
<summary>Original English</summary>

**Speaker 1**: so even i update a little little bit in the sense that i now think i would now say that these models can be said to be intelligent and restraicted demains the archchallenshowed that. so if you place constraints into the problem, you can, you can go faster towards an knogo even agency. you, you can put a planner on that. and you can go if you, if you know where you're go, you can go there faster, but that doesn't help you that you can have all the intelligence and agency in the world, but you don't have the knowledge in the constraints, then you're going in the wrong direction, faster. and i think they don't seem to appreciate that these models don't actually know the world like that of that,

</details>

**Speaker 0**: 这甚至与我的观点相关。我的观点是，它误解了真正的危险所在，那就是当一项更强大的技术进入世界时，它会让一些人变得更强大，那些热爱权力的人会寻求垄断技术。技术越强大，那些渴望权力的人的这种冲动就越强烈。所以，忽视那些说“问题在这里”的人，如果你说：“我不关心那些。”我只关心自主 **AI** 的崛起，你说的奇点、回形针、随便什么。对此最明显的解决方案是：“哦，让我们将权力去中心化。”这正是我们当时一直在说的，特别是在当时，将所有这些权力交给非常富有的科技公司或政府，或者两者兼有，并确保其他人没有这种权力。在威胁模型中，这是你能做的最糟糕的事情，因为你将控制能力集中在一个地方。因此，这些渴望权力的人只需要接管这个东西。

<details>
<summary>Original English</summary>

**Speaker 0**: that even relevant to, even in my point, which was it is that it's misunderstanding where the actual danger is, which is that when you have a dramatically more powerful technology entering the world that can make some draramatically more powful people, people who in love with power, we'll seek to monopolized technology. and the more powerful it is the more strong that urge from those power. hungry people will be so to ignore people who say here's the problem. if you're like, i don't care about a new of that. all i care about is autonomous AI taking off you singsinglarity paper clip, let no good. whatever the obvious solution to that is, oh, let's set tualize power wer, which which is what we kept saying, particularly at time lelegive, um either very rich technology companies or the government, or both all of this power and make sure nobody else has it in in ththreat model. that's the worst possible thing you can do because you've centralized the ability to control in one place. and therefore, these people who are desperate for power just have to take over that thing.

</details>

**Speaker 1**: 我们能否区分一下你所说的权力是什么意思？因为我们刚刚讨论过，它实际上没有人们想象的那么强大。

<details>
<summary>Original English</summary>

**Speaker 1**: could we didistinguish though what you mean by power because we we just spend some of this conversation talking about how it's not actually as powerful as people think it is,

</details>

**Speaker 0**: 但我甚至不是，但那甚至不是事实。所以我就说，即使它最终证明非常强大，对吧？就像我不想争论它是否会强大，因为那是推测性的。即使它会非常强大，你仍然不应该将所有权力集中在一两家公司或政府手中。因为如果你这样做，所有这些权力都将被渴望权力的人垄断，并用来摧毁文明。基本上，你最终会到达一个所有财富和权力都将集中在那些我们不希望权力集中在他们手中的人手中的地方。所以，就像社会几百年来一次又一次地面对这种情况一样，你知道。所以当写作曾经只是最少数人才能接触到的东西时，人们对写作的了解。人们提出了同样的论点。如果你让每个人都写作，他们就会写出我们不希望他们写的东西。那会非常糟糕。你知道，印刷术呢？我用投票权也是一样。社会必须一次又一次地与那些拥有现状权力的人的这种自然倾向作斗争，他们会说：“不，这是一种威胁。”所以当我们说：“好吧，如果 **AI** 变得极其强大怎么办？”是让它掌握在少数人手中，还是分散到整个社会中，哪种对社会更好？我的论点是后者。不，还有一种论点是：“别担心。它们不会那么强大。”无论如何，我只是不想去讨论这个问题，因为它不是。而且我发现那很容易赢得争论，因为你无法真正说出将会发生什么。我们都在猜测。但我可以清楚地说，如果它发生了，只让 **Elon Musk** 拥有它会是个好主意吗？只让 **Donald Trump** 拥有它会是个好主意吗？**Hendrik** 谈到过这种攻防不对称。

<details>
<summary>Original English</summary>

**Speaker 0**: but i'm not even but that man isn't even if thing right. so II just say, even if it turns out to be incredibly powerful, right, like i don't, i don't even want to argue about whether it's going to be powerful, cause that's speculative. even if it's going to be incredibly powerful, you still shouldn't centralize all of that power in the hands of one company or the government. because if you do all of that power is going to be monopolized by power hungry people and used to destroy civilization. basically, you'll i'll end up with the place where all of that wealthy power will be centralized with the kinds of people who we wanted centralized. so like society for hundreds of years have faced this again and again and again, pitknow. so when it's like the writing used to be something that only the most exclusive people had access knowing about writing, and the same arguments were made. if you let everybody write, they're gona use it to write things that we don't want them to write. and it's going to be really bad. you know, did know with printing, did i with the vote like the and again, it again, society has to fight against this natural predalition of the people that have the statscore power to be like. no, this is a threat. so when we saying like, okay, what if AI turned to be incredibly powerful, would it be better of a society to be that to be kept in the hands of a few or spread out across society? my argument was the letter. no, there's also an argument which is like i don't worry about it. thenot going to be that powerful. anyway, i just didn't wanna go there because it's not. and i commate that easy to win, because you can't really say what's going to happen. we're all just guessing, but i can cleclearly say, what if it happens, would it? it be a really good idea to only let elline nust kevt would it going to be a good idea to only let andred tramp hait it dhendrok spoke about this offence defence a symmetrium.

</details>

**Speaker 1**: 所以我们拥有对抗性防御非常重要。但让我们暂时将其视为既定事实，因为显然，当我们审视像 **Meta** 和 **Facebook** 这样的公司时，力量不平衡非常明显。你知道，他们控制着我们所有的数据，他们知道我们在做什么。所以像 **OpenAI** 和 **Claude** 这样的公司，它们并没有我们想象的那么好，因为实际上人类仍然需要参与。例如，他们拥有我们所有的数据，对吧？你可能正在开发一些新的创新技术，你正在使用 **Claude**，你将所有信息都发送到那里，他们现在可以复制你。我的意思是，你谈论的是什么样的风险，请具体一点？

<details>
<summary>Original English</summary>

**Speaker 1**: so it's actually very important for us to have to have counterviling in a defences. but let's just take that as a given from minute because obvisly, when we look at something like meter and facebook it, it's quite clear what the power and balances, you know, there's they they control all of our data, they they know what 're doing. so it's something like open they are in claued. so it's it's not as good as we thought it was because actually humans only to be involved, for example, they have all of our data right? and you might be working on some new innovative technology and you're using clad and you're sending all of your information up there and they can now copy you. i mean, what what ms of risks are you talking about to be more concrete?

</details>

**Speaker 0**: 是的，我的意思是，那时我没有谈论所有这些事情。我当时谈论的是这个投机性问题：如果 **AI** 变得极其强大怎么办？

<details>
<summary>Original English</summary>

**Speaker 0**: yeah now. i mean, so i was not talking about any of those things that's at the time. i was talking about this speculative question of what if i get incredibly powerbut.

</details>

**Speaker 1**: 我的意思是，我现在，例如，他们说这是新的生产资料。这对我来说似乎完全是夸大其词。但根据你的最佳估计，现在，如果当前技术存在风险，

<details>
<summary>Original English</summary>

**Speaker 1**: i mean, i now, for example, they they say that this is the new means of production. and and that seems completely hyperbullets to me. but like in your best estimation, now, if there are risks,

</details>

**Speaker 0**: 如果当前技术存在风险，那是什么？我认为其中一些是我们已经讨论过的，那就是人们通过基本上失去随着时间变得更有能力的能力而削弱自己。这是我最担心的大风险。隐私风险是存在的。但我不确定它是否比之前对 **Google** 和 **Microsoft** 的风险大得多。你知道，你以前在 **Microsoft** 工作，你知道他们拥有关于普通 **Outlook** 用户的多少数据，或者 **Google**，你知道，普通 **Google Workspace** 或 **Gmail** 用户的数据。嗯，这些隐私问题是真实存在的。尽管我认为这些公司存在更大的隐私问题，政府可以将国家选举工具外包给它们。所以在过去，有一些像 **ChoicePoint** 和 **Acxiom** 这样的公司。现在，可能更多是像 **Palantir** 这样的公司。美国政府实际上被禁止建立关于美国公民的大型数据库，例如。但公司没有被禁止这样做，政府也没有被禁止将这些事务外包给这些公司。所以我的意思是，这是一个巨大的担忧，但我不认为这是一个 **AI** 独特造成的问题。这当然，就像你在英国一样。如你所知，在英国，监控已经普遍存在了一段时间。现在它肯定让使用这种监控变得更容易，但一个拥有足够资源的组织可以通过投入大量人力来解决这个问题。所以，是的，我不确定这些是否是由于隐私问题，也许是比我以前更常见的问题。**Jeremy**。

<details>
<summary>Original English</summary>

**Speaker 0**: what are that if there are risks with a current state of technology, i think i think some of them of the ones we've discussed, which is people and febling themselves by basically losing their ability to be to become more competent over time. that's the big risk. i worry about the most the privacy risk, it's there. but i'm not sure it's much more there than it was for google and microsoft. before you know, you used to work at microsoft, you know how much data they have about the average outlook offers six etera user did of a google, you know, the average google worspace or gmail user. um those privacy issues are real. although i think there are bigger privacy issues around these companies, which the government can outsource state election tools. so back in the day is to be companies like choice point in axim. nowadays, it's probably more companies like pentia. the US government is um actually prohibited from building large databases about US citizens, for example, but it's not prohibited companies are not prohibited from doing so in the governis, not prohibited from contracting things to those companies. so i mean, that's a huge worry, but i don't think it's one that II is uniquicly creating. it's tatainly like you're in the UK. as you know, in the UK surveillance has been universal for quite a while. now it certainly makes it easier to use that surveillance, but a sufficiently well resource organization could just through one thousand bodies at the problem. so yeah, not sure these are due privacy problems as maybe more common ones than i used to be jeremy.

</details>

**Speaker 1**: 我刚注意到时间，我得去机场了。好吧，这次对话太棒了。

<details>
<summary>Original English</summary>

**Speaker 1**: i have just noticed the time i need to get to the airport. Alright, this has been amazing.

</details>

**Speaker 0**: 谢谢你。感谢你的到来。是的。希望你旅途愉快。非常感谢。

<details>
<summary>Original English</summary>

**Speaker 0**: thank you. so thank you for coming. yeah. hope you had a nice trip. thank you so much.

</details>