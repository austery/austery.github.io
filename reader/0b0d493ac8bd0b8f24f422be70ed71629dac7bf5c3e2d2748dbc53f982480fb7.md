---
author: Dwarkesh Patel
date: '2024-05-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=1fmcdz2EO_c
speaker: Dwarkesh Patel
tags:
  - ai-collaboration
  - long-horizon-tasks
  - ai-training
  - programming-assistants
title: AI 协作新纪元：从单步指令到项目伙伴
summary: 本文探讨了未来AI模型将如何从执行单一指令的工具转变为能够独立完成复杂项目（如编码项目）的协作伙伴。通过长时程强化学习训练，AI将能进行更连贯、主动的交互，并具备更强的错误恢复和泛化能力，重塑人机协作模式。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models: []
media_books: []
status: evergreen
---
### AI 协作新纪元：从单步指令到项目伙伴

一到两年内，我们将发现AI模型能够处理比现在更加深入和复杂的任务。例如，我们可以设想模型能够独立完成一个完整的编码项目，而不仅仅是提供编写函数的单一建议。想象一下，你只需向模型给出高层指令，它便能去编写许多文件，进行测试，审视输出，并进行迭代优化，执行远比当前复杂得多的任务。这将使AI的使用方式从一次性的查询，从类似“智能搜索引擎”的工具，转变为与模型进行真正的项目协作。在这种协作模式下，AI能了解你过去的工作，主动提出建议，甚至在后台默默执行任务。而其关键突破在于，模型能够具备足够的“连贯性”，足以完成涉及编写多个文件的复杂编码任务。

当前大部分训练数据侧重于单步操作，与现在相比，未来的模型需要进行更多专门针对长时程项目的训练，例如通过强化学习（RL）来教会模型执行这类任务，无论这种训练是监督最终结果还是监督每一步骤。我相信这种长项目执行训练将显著提升模型能力，鉴于这个领域尚属新兴，进行此类训练存在大量机会和潜在收益。

此外，随着模型能力的提升，它们在错误恢复和处理边缘情况方面将表现得更好。模型将能更智能地应对错误，而不是像现在这样卡住。这意味着模型将更具“样本效率”，仅需少量数据或通过泛化能力就能学会如何纠正错误并重回正轨，而当前模型则可能因此卡顿停滞。模型通过泛化能力可以从其他领域或预训练中学到的经验中推断并应用到当前情况，即使只有少量正面示例，也能有效地纠正方向。虽然弱模型可能需要大量特定数据才能掌握某个领域，但强大的模型凭借其泛化能力，或许无需额外训练就能展现出色的表现。

目前，尽管模型在“每 token”层面上可能已具备堪比最聪明人类的智能，但其应用价值受到“短期记忆”的极大限制——它们可能很快忘记之前的上下文，无法进行长时程的连贯性工作，从而阻碍其在代码编写及项目目标对齐方面发挥最大作用。一旦开始“长地平线 RL 训练机制”，AI将能实现更长时间的连贯性，从而解锁处理复杂项目的能力。这是否意味着AI能迅速达到人类水平的协作能力？还是说，即使解锁了长时程规划和执行能力，仍有其他瓶颈需要克服？

我并不认为仅凭这一项改进就能立即解决所有问题。AI可能仍会存在各种“杂项缺陷”（miscellaneous deficits），导致它们遇到困境、进展缓慢，甚至做出不如人类的决策。因此，尽管提升长时程任务能力是关键一步，它并非通往通用人工智能（AGI）的唯一路径。AI要成为真正“功能齐全的同事”，还需要克服其他关键性的挑战，而这些挑战的具体形式仍不明确。

<details>
<summary>Original English</summary>

in one or two years we'll find that you can use them for a lot of um more like involved tasks than they can do now so you could um you could imagine having the models do carry out a whole coding project instead of maybe giving you one suggestion on how to write a function so uh you could imagine the model like you giving it sort of high level instructions on what to what to code up and it'll go and write uh many files and test it look at the output iterate on that a bit so just much more complex Tas moving away from sort of oneoff queries uh like using the model kind of like a search engine a smarter search engine and more towards uh like having a whole project that um I'm like doing in collaboration with the model yeah and it knows everything I've done it's proactively uh like um suggesting things for me to try or it's going and doing work in the background and fundamentally the unlock is that it can act coherently for long enough to write multiple files of code or what what has changed between now and then um most of the uh training data is more like doing single steps at a time and I would expect us to do more uh for training the models to uh carry out these longer projects um so I'd say any any kind of training uh any like doing RL uh to learn how to do these tasks uh however you do it whether it's whether you're supervising the final output or supervising it like each step um I think any kind of training at uh carrying out these long projects is going to make them a lot better and uh since uh the the whole um area is pretty new I'd say there's just a lot of lowhigh fruit interesting in doing this kind of training so i' say that's one thing um also I would expect that as the models get better they're just um better at recovering uh from errors or they have um just uh they're better at um dealing with um dealing with edge cases or when things go wrong they know how to recover from it so uh the models will be more sample efficient so you don't have to collect a ton of data to uh teach them how to get back on track just a little bit of data or or just their like generalization from uh from other um abilities will allow them to get back on the track on track whereas current models might just get stuck and get lost I'm not sure I'm not sure actually how uh understand more supposedly how the generalization helps you get back on track yeah if you collect a divers data set um you're going to get a little bit of everything in it and uh and if you have models that generalize really well uh even if there's just a couple examples of getting back on track or even um like maybe in the pre-training there's examples of getting back on track then like the model will be able to generalize from uh those other things it's seen to the current situation so I think uh like uh if you have models that are weaker you might be able to get them to do almost anything with enough data but you might have to put a lot of effort into um a particular uh domain or skill whereas for a stronger model it might just do the right thing without any training data or any effort right now we have models that are on a per token basis pretty smart like they might be as smart as humans on a per token basis the smartest humans and the the thing that prevents them from being as useful as they could be is that five minutes from now they're not going to be so writing your code in a way that's coherent and aligns with the broader goals you have your project or something if it's the case that once you start this long Horizon RL training regime it immediately unlocks your ability to be coherent for longer periods of time should we be predicting something that is human level as soon as that regime is unlocked or and if not then what what is remaining after you can plan for a year and execute projects that take that long I wouldn't expect everything to be immediately solved by doing any training like this I would think uh there will be other um like miscellaneous deficits that the models have that um cause them to get stuck or not make progress or make um worse decisions than humans so uh I I wouldn't say I expect that this one little thing will unlock every all capabilities but I um yeah it's not clear uh but it might like some improvement in the ability to do long Horizon tasks might go quite far does that imply that unless there are these other bottlenecks which they may or may not be by next year you could have models that are potentially like human level in terms of acting like like you're interacting with this as a colleague and it's like it's like as good as an interacting with the human colleague you can tell them to go do stuff and they go get it done uh what seems wrong with that picture of this is the capabilities you think might be possible yeah it's hard to say exactly what will be the deficit I mean I would say that uh when you talk to the models today they have various um uh weaknesses besides uh long-term coherence in terms of also like um like really uh thinking hard about things or paying attention to the way you ask them uh so um I would say um I wouldn't expect um like just improving the uh coherence a little bit to like um to be all it takes to get to AGI but um I guess I wouldn't be able to articulate exactly what the main weakness is that'll stop them from uh like being a fully functional colleague

</details>