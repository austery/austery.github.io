---
author: Dwarkesh Patel
date: '2024-04-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=AOt0GwY8IvU
speaker: Dwarkesh Patel
tags:
  - long-context-windows
  - ai-agents
  - model-reliability
  - future-of-ai
  - fine-tuning
title: AI模型的未来：长上下文、微调的消亡与智能体的挑战
summary: 本次讨论探讨了AI模型发展的未来趋势，包括小型与大型模型界限的模糊、长上下文窗口可能带来的微调（fine-tuning）的式微。核心议题围绕AI智能体（agents）的局限性展开，指出其发展瓶颈在于可靠性而非长任务处理能力。同时，也展望了AI公司未来的形态，可能是单一的端到端训练模型，也可能是相互协作的智能体网络，并强调了在RL（强化学习）中，明确的信号和人类的细致指导对于模型进步的关键作用。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
products_models:
  - GPT-4
media_books: []
status: evergreen
---
### AI 模型发展的未来趋势与智能体的挑战

**Unknown Speaker**: 设想一下，在不久的未来，小型模型和大型模型之间的界限将某种程度上消失。同时，随着**长上下文窗口**（long context windows）的发展，**微调**（fine-tuning）的必要性也可能大大降低。

<details>
<summary>Original English</summary>

**Unknown Speaker**: there's a future where like the distinction between small and uh large models like disappears to some degree um and with long context there's also a degree to which fine tuning might disappear to be honest um

</details>

**Unknown Speaker**: 当前的模型格局中，我们有不同层级、不同大小的模型，也有各种各样的微调模型。但在未来，你可能会有一个动态的计算资源集合，以及无限的上下文，能够根据不同需求专门化你的模型。AI 进展中的一个瓶颈，许多人认为，是模型在**长时程任务**（Long Horizons）上的表现不足，这意味着任务需要持续数小时、数周甚至数月。而 AI 智能体（AI agents）在这方面尚未取得突破，据我理解，原因就在于此。那么，长上下文窗口的能力与在长时程任务上的表现能力，这两者关联有多大？它们是独立的吗？

<details>
<summary>Original English</summary>

**Unknown Speaker**: like the these two things that are very important today like today's landscape of models we have like whole different tiers of model sizes and we have fine sh models of different things you can imagine a future where you just actually have a dynamic bundle of compute and uh like infinite context um and the that specializes your model to to different things one of the bottleneck for AI progress that many people identify is the inability of these models to perform tasks on Long Horizons which means engaging with the task for many hours or even many weeks or months where like if I have I don't know an assistant or an employe or something they can just do a thing I tell them for a while um and AI agents haven't taken off for this reason from what I understand so how linked are long context windows and the ability to perform well on them and the ability to do these kinds of long Horizon tasks that require you to engage with uh an assignment for many hours or are these unrelated Concepts

</details>

**Unknown Speaker**: 我倒不完全认同将此归咎于智能体未能普及的原因。我更倾向于认为，这更多地关乎**可靠性**（reliability），即模型能否真正成功地完成任务。如果任务无法以足够高的概率连续地串联起来，就无法形成一个真正意义上的智能体。这或许解释了为什么智能体的发展更像是**阶梯式**（step function）的进步，就像 GPT-4 级别（Gbd4 class models）或 Ultra 级别的模型，它们还不够完美。但也许下一代模型规模的提升，能带来那额外的“可靠性百分点”，即使损失（loss）函数下降不那么显著。当然，要完成长时程任务，确实需要一定程度的上下文，但我认为这并非迄今为止的限制因素。

<details>
<summary>Original English</summary>

**Unknown Speaker**: I mean I would actually take issue with the that being the reason that agents haven't taken off um where I think that's more about like nines of reliability and the model actually successfully doing things and if you just can't chain tasks successively with high enough probability then you won't get something that looks like an agent that's why something like an agent might follow more of a step function like gbd4 class models G Ultra class models they're not enough um but maybe like the next incr model scale means that you get that extra nine even even though like the loss isn't going down that dramatically that like small amount of extra ability gives you the extra and like yeah obviously you need some amount of context to fit long Horizon tasks but I don't think that's been the limiting factor up till now

</details>

**Unknown Speaker**: 你认为未来会是多个模型相互对话，还是仅仅依靠一个强大的计算系统，在需要时调用更多资源来完成一个大型企业级的任务？我之所以这样问，是因为有两点让我思考智能体是否是未来的正确方向。第一，随着上下文窗口越来越长，模型能够处理和考虑的信息量已远超人类的能力。这意味着我们可能不再需要一个前端工程师和一个后端工程师，而是一个模型就能理解整体。这使得**专业化**（specialization）的“柯克内问题”（keken problem）消失了。第二，现在的模型非常**通用**（general）。你不会使用不同类型的 GPT-4 来做不同事情，你使用的是完全相同的模型。这让我思考，未来一个 AI 公司是否就像一个单一模型，而不是一堆相互连接的 AI 智能体？

<details>
<summary>Original English</summary>

**Unknown Speaker**: do you expect that it will be multiple copies of models talking to each other or will it be just uh a adap a computer solve then the thing just like runs bigger uh like more compute when it needs to do a kind of thing that a whole firm needs to do and I asked this because there's two things that make me wonder about like whether agents is the right way to think about what will happen in the future one is with longer context these models are able to ingest and consider the information that no human can and therefore we need like one engineer who's thinking about the front end code and one engineer is thinking about the back end code where this thing can just ingest the whole thing the sort of like keken problem of specialization uh goes away second these models are just like very general um of you're like not using different types of gp4 to do different kinds of things you're using the exact same model right so I wonder if what that implies is in the future like an AI firm is just like a model instead of bunch of AI agents hooked together

</details>

**Unknown Speaker**: 这是一个很棒的问题。我认为，尤其是在近期，AI 的形态会更像是由多个智能体组成的。之所以这样说，是因为作为人类，我们希望拥有这些独立、可靠且可信赖的组件。所以，如果你的观点是 AI 智能体之所以未能普及是因为可靠性而非长时程任务表现，那么，当一个任务建立在另一个任务之上，再建立在另一个任务之上时，这种**不可靠性**（lack of reliability）难道不正是长时程任务的困难所在吗？也就是说，你必须连续完成 10 件事，甚至 100 件事，其中任何一件事的可靠性下降，或者说概率从 99.99% 降到 99.9%，都会导致整个事情的成功率成倍降低。

<details>
<summary>Original English</summary>

**Unknown Speaker**: that's a great question um I think especially in the near term uh it will look much more like agents look together and I say that like purely because as humans we're going to want to have these like isolated reliable and uh like like like components that we can trust so if you're claiming is that the AI agents haven't taken off because of reliability rather than long Horizon task performance isn't the lack of reliability when a task is changed on top of another task on top of another task isn't that exactly the difficulty with long Horizon tasks is that like you have to do 10 things in a row or 100 things in a row and diminishing the reliability of any one of them uh or yeah the probability goes down from 99.99 to 99 .9 then like the whole thing gets multiplied together and the whole thing becomes much less likely to happen

</details>

**Unknown Speaker**: 未来非常重要的一件事是，我们需要更好地理解，在长时程任务中，成功率到底意味着什么。我认为，这对于理解这些模型可能产生的**经济影响**（economic impact）也至关重要。我们需要通过将我们所做的工作、输入的输出量缩减到几分钟、几小时或几天，来真正地评估模型能力的增长，并观察其在不同时间尺度下的连续训练和任务完成能力。这能告诉你，一个工作家族或任务家族在多大程度上是可自动化的。这与 MMO 游戏玩家的学习方式有所不同。

<details>
<summary>Original English</summary>

**Unknown Speaker**: one of the things that will be really important to do over the next however long is understand better what does success rate over long Horizon task look like um and I think that's even important to understand what the economic impact of these models might be and like actually properly judge increasing capabilities right by like cutting down the tasks that we do and the inputs and outputs involved into minutes or hours or or days and seeing how good it is successively training and completing Tas those different resolutions of time because then that tells you like how automatable a job family or task family is um in a way that like MMO you schooles don't

</details>

**Unknown Speaker**: 不到一年前，我们还引入了 10 万（100K）的上下文窗口，我想这让很多人感到惊讶。当时，大家普遍认为“二次方注意力成本”（quadratic attention costs）导致我们无法拥有长上下文窗口。然而，事实是我们已经做到了。所以，是的，**基准测试**（benchmarks）正在不断被刷新。

<details>
<summary>Original English</summary>

**Unknown Speaker**: I mean it was less than a year ago that we introduced 100K context windows and I think everyone was pretty surprised by that so yeah everyone would just kind of had this sound bite of quadratic attention costs and we can't have long context windows and uh here we are so yeah like the benchmarks are being actively made

</details>

**Unknown Speaker**: 设想一家 AI 公司，整个系统是端到端训练的，其信号就是“我是否盈利了？”。或者，如果这个目标太模糊，设想一家**建筑设计公司**，他们的信号是客户是否喜欢蓝图。在这种情况下，中间可以想象有负责销售的智能体、负责设计的智能体、负责编辑的智能体等等。这种信号机制能否在这样的端到端系统中奏效？

<details>
<summary>Original English</summary>

**Unknown Speaker**: one thing you can imagine is you have an AI firm or something and the whole thing is like end to end trained on the signal of like did I make profits or like if if that's like too ambiguous if it's if it's an Architecture Firm and they're making blueprints did did my client like the blueprints and in the middle you can imagine agents who are sales people and agents who are like doing the designing agents who like do the editing whatever um uh would that kind of signal work on an end toin system like that

</details>

**Unknown Speaker**: 是的，在极限情况下，这正是**强化学习**（reinforcement learning）的梦想。你只需要提供一个极其稀疏的信号，然后通过足够的训练，模型就能自行学习。但我不认为这是会首先实现的那种方式。我认为这需要人类在这些机器周围付出极大的**关注和勤奋**（care and diligence），确保它们做exactly你想要的事情，并给予它们正确的信号来改进。

<details>
<summary>Original English</summary>

**Unknown Speaker**: yeah in the limit yes that's the dream of reinforcement L right it's like all you need to do is provide this extremely Spar signal and then over enough it already you sort create the information that allows you to learn from that signal um but I don't expect that to be the thing that works first I think this is going to require an incredible amount of care um and like diligence on the behalf of humans surrounding these uh machines um and making sure they do exactly the right thing and exactly what you want and giving them right signals to improve in the ways that you want yeah

</details>

**Unknown Speaker**: 如果模型无法产生任何奖励，你就无法基于 RL 奖励进行训练。

<details>
<summary>Original English</summary>

**Unknown Speaker**: you can't train on the RL reward unless the model generates some reward yeah

</details>

**Unknown Speaker**: 对，没错。你正处于一种 RL 的循环中：如果客户从不喜欢你的产出，你就得不到任何奖励，这很糟糕。但未来，模型将足够强大，能够获得一些奖励。这就是我们之前谈到的**可靠性**（nines of reliability）。

<details>
<summary>Original English</summary>

**Unknown Speaker**: yeah yeah exactly you're in like you're in this like RL world where like if it never the client never likes what you produce then like you don't get any reward at all and like it's kind of bad but in the future these models will be good enough to get the reward some of the time right this is the nines of reliability that was talking about yeah

</details>