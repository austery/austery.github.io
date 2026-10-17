---
author: AI Engineer
date: '2026-09-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5Cxe5dv2Xlw
speaker: AI Engineer
tags:
  - sparse-attention
  - long-context
  - multimodal-learning
  - agentic-workflow
  - open-source-model
title: MiniMax与百万上下文Agent：原生多模态与稀疏注意力架构解析
summary: Hugging Face联合创始人Thomas Wolf对话MiniMax研究员Olive Song，深度拆解MiniMax开源模型M3的技术内核。对话深入探讨了100万至千万级超长上下文在复杂多轮Agent交互中的必要性、MSA稀疏注意力机制的架构设计与算力优化、从预训练初始阶段即引入图像与视频的原生多模态训练方法，以及内部自研Research Harness推动AI自我迭代的工程实践。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - MiniMax
  - Hugging Face
products_models:
  - MiniMax-M3
  - MSA
media_books: []
status: evergreen
---
### 嘉宾开场与背景介绍

**主持人**: 接下来登台的是 **Hugging Face** 联合创始人兼首席科学官 **Thomas Wolf**。

<details>
<summary>Original English</summary>

**Host**: Joining us on stage is the co-founder and chief science officer at Hugging Face, Thomas Wolf.

</details>

**Thomas Wolf**: 大家好。你好，**Olive**，非常高兴能邀请你来到舞台上。

<details>
<summary>Original English</summary>

**Thomas Wolf**: Hello everyone. Hello Olive, nice to have you on stage.

</details>

**Olive Song**: 嗨，很高兴见到你。非常感谢邀请我来参加。

<details>
<summary>Original English</summary>

**Olive Song**: Hi, nice to meet you. Thanks for having me, yeah.

</details>

**Thomas Wolf**: 我想大家今天一定会大饱眼福，因为你们刚刚见证了 **GLM** 的分享，它目前在人工智能排行榜上名列第二——我把 Fable 排除在外了，因为根本没人能用得上它。而现在我们迎来了第四名。所以基本上，大家一口气连续看到了所有顶尖的模型，至少是全部顶级的**开源大模型**。

我们非常幸运能邀请到 Olive，她的人生履历相当精彩。她来到美国宾夕法尼亚州求学，后来在纽约大学（NYU）师从 **Yann LeCun** 的实验室攻读博士学位，主攻 **JEPA**（联合嵌入预测架构）方向。不过我们之前商量好了，今天就不展开聊 JEPA 了对吧？那个话题留到以后再说。

后来，她没有选择加入当时同样位于纽约的 Hugging Face，而是决定加入 **MiniMax**。对于那些可能不太了解全球所有新兴 AI 实验室的朋友们来说——这完全可以理解，因为据我所知目前大概有 64 家新兴实验室——MiniMax 是被誉为中国“**AI四小龙**”之一的顶尖团队。如今大家都很熟悉 **DeepSeek**，还有打造了 Kimi 的 **Moonshot**（月之暗面），以及大家刚刚看到的 GLM（智谱AI），现在则是 MiniMax。他们都极其优秀，也都在全力以赴争夺第一梯队的位置。

MiniMax 最新的成果是在今年 6 月初发布的 **M3** 模型，它在当时是首屈一指的开源模型，表现非常惊艳。这个模型身上有很多非常值得探讨的亮点，所以我们马上会深入拆解，接着也会聊聊 MiniMax 这家公司的独特之处与精彩之处。

那么 Olive，或许我们可以先从这里开始：你能向大家谈谈你对 M3 的看法吗？你最喜欢这个模型的哪些特性？当时的发布情况如何？

<details>
<summary>Original English</summary>

**Thomas Wolf**: So I think you're in for a treat today because you just saw GLM, which is current number two on the artificial intelligence leaderboard. I take Fable out because nobody can use it. And now we have number four. So basically you will have all the top models, at least the top open source models in a row. And we're very lucky to have Olive who has a pretty amazing path in life.

She came to the US, Pennsylvania. She was studying, doing a PhD at NYU in the lab of Yann LeCun working on JEPA, but we decided we won't talk about JEPA today, right? Something for another day. And then instead of joining Hugging Face, which was in New York also at that time, she decided to go join MiniMax.

So for those who maybe don't know all the neo labs around the world—and you're forgiven because I think there's like 64 neo labs right now—MiniMax is one of the top of what we call the AI dragons in China. So these are the new—there's DeepSeek which is very well known now, Moonshot who does Kimi, and GLM that you just saw, and now we have MiniMax. They're all extremely good, fighting for the first spot.

The latest release of MiniMax was M3 just earlier in June, which was the top model at the time, top open-source model. Very impressive. There's a lot of very interesting things about this model, so we'll quickly dive into them, and then talk a little bit about what's specific about MiniMax, what's great there.

So maybe Olive to start a little bit: can you give us your view of M3, what you like about this model, and how was the release?

</details>

### M3模型特性与参数规模

**Olive Song**: 嗯，好的。我们在本月初发布了 M3，它是一个参数规模相对紧凑的模型，总参数量约为 **4000 亿**（400B），而**激活参数仅为 200 亿**（20B）。

尽管激活参数很小，但它在代码生成性能以及视觉理解能力方面都极为出色。这是通常开源模型所不具备的特质——传统开源模型往往只能处理纯代码或文本任务，而 M3 不仅精通编程，还能够理解图像与视频。并且依托我们自研的全新架构 **MSA**（**MiniMax Sparse Attention**，稀疏注意力机制），它具备高达 **100 万 token** 的超长上下文窗口。

我们之所以将这三项关键能力融合在一个模型中，是因为我们深知它们在未来的 AI 应用中将至关重要：卓越的代码生成能力、智能体（Agentic）协作能力、超长上下文处理能力以及多模态理解能力。我认为这正是该模型最引人瞩目的核心所在。

<details>
<summary>Original English</summary>

**Olive Song**: Mhm. Yeah, we released M3 earlier this month, and it is a smaller model with around 400 billion total parameters and 20 billion activated.

Um, but it is very capable in terms of both coding performances, and also it understands vision. So that's what open-source models don't usually have. It's not just that the model can deal with coding, but it can also understand videos, images, and it has a super long context of 1 million tokens with our new architecture called MSA, MiniMax Sparse Attention.

So we really put these three things together because we know that they will be very important in future AI applications: coding capabilities, agentic capabilities, longer context, and multimodal understanding. Yeah, I think that's what is very interesting about the model.

</details>

### 百万上下文与稀疏注意力

**Thomas Wolf**: 确实，这个模型包含了太多值得深度剖析的技术细节。而且据我所知，它至今依然是排名前五的开源大模型中唯一真正具备原生多模态能力的模型，我们稍后必须好好聊聊这一点。

不过我们也许应该先聚焦在**长上下文**上，因为 M3 是首个真正实现并落地了功能完备、切实可用的 100 万 token 长上下文的开源模型。而且你们团队还提出了 MiniMax Sparse Attention（MSA）技术，并且发表了详细论文向全社区进行了深度分享，以此来大幅提升长序列计算的效率。你能为我们详细讲讲这个项目吗？比如从最初的注意力机制探索，到最终成功实现这种超长上下文，整个研发历程是怎样的？

<details>
<summary>Original English</summary>

**Thomas Wolf**: Yeah, so there's a lot to unpack in this model, and it's still, I think, the only top five open-source model that is actually multimodal, so we need to talk about that.

But maybe first about the long context, because that was also the first one that really had this real 1 million token long context that is actually functional. And you guys had also the MiniMax Sparse Attention, which is this one technique to make that efficient that you also published and share extensively. So can you talk a little bit about this? Maybe how the project went from the attention mechanism to how to make this long context?

</details>

**Olive Song**: 好的。其实我们对于长上下文的探索历史，甚至可以追溯到早期的 **MiniMax M1** 和 **MiniMax-01** 时代。在那个阶段，模型其实就已经能够处理 **1000 万 token** 级别的超长上下文任务了。

<details>
<summary>Original English</summary>

**Olive Song**: Yeah, I would say the story about long context went back to even MiniMax M1 and MiniMax 01, where the model was actually able to perform tasks of 10 million token context.

</details>

**Thomas Wolf**: 1000 万 token？

<details>
<summary>Original English</summary>

**Thomas Wolf**: 10 million?

</details>

**Olive Song**: 没错，是 1000 万 token。但当时的模型还不是一个具备 Agent 属性的智能体模型，对吧？它当时主要用于诸如你直接丢进去一整套大部头书籍，它能快速生成书评和内容总结之类的任务。

但随着研发深入，我们敏锐地意识到：更长的上下文实际上能够解锁大量深层能力，尤其是在与人类用户交互，以及当前 Agent 需要与外部复杂环境进行深度交互时。智能体在执行任务时需要接收大量工具调用（Tool Call）的返回结果，经历多轮连续对话与环境反馈。如果上下文窗口较短，根本无法胜任这种高复杂度的端到端任务。因此在打造 M3 这个版本时，我们明确决定：“我们必须把强大的长上下文能力全面带回来。”

为了实现这一目标，我们全力研发了 **MiniMax Sparse Attention**（MSA 架构）。这一架构具备极高的可扩展性，且整体设计非常优雅轻量。

从高层架构逻辑来看，它主要包含两大核心分支：首先是一个**索引分支**（Index Branch），它站在全局宏观视角，从海量上下文中筛选出真正关键、高价值的上下文信息块；随后是一个**稀疏注意力分支**（Sparse Attention Branch），它仅针对被选中的重点信息块执行高精度的注意力矩阵计算，从而高质量完成推理任务。

通过这样简洁高效的设计，我们构建出了一个兼顾计算效率与表现力的架构，使得我们未来不仅能够进一步扩展上下文序列的长度，同时也能轻松扩展更大规模的模型参数量。

<details>
<summary>Original English</summary>

**Olive Song**: 10 million, yes. But then it was not an agentic model, right? It was just, for example, you dump in a book, it would be able to give reviews on it and stuff like that.

So what we realized was that longer context actually unlocks a lot of capabilities, especially when interacting with users and now when the agent is interacting with the whole environment and getting all the tool responses, getting multi rounds—the shorter context wouldn't be enough to perform the complex task. So for this version we said, "Oh, we have to have our longer context back."

So what we pursued was with our MiniMax Sparse Attention, which you know, was the architecture that was scalable and had a simple design. So I would say from a higher level, right? It has an index branch that selects on a higher level what matters more in the context, and then we have a sparse attention branch that performs the calculation on the selected blocks to actually perform the task.

And so yeah, like that we really designed an elegant architecture so that we can scale the length and then scale the model size in the future with that.

</details>

### 算力效率与研究创新

**Thomas Wolf**: 这个设计太漂亮了。对于在这个领域深耕了较长时间的人来说，大家肯定记得我们以前在注意力机制上做过海量的研究工作，对吧？为了解决 $O(N^2)$ 的复杂度问题，学术界曾涌现过大量的**线性注意力**（Linear Attention）方案。但后来当 **FlashAttention** 横空出世后，这些研究在某种程度上几乎一夜之间全都淡出了视野——大家发现原来我们只需要更高效的底层硬件算子就行了。

而现在，我非常欣喜地看到大家又重新回归到第一性原理去深度思考：究竟什么是注意力？我们怎样才能从本质上让它变得更加高效？

毕竟 100 万 token 已经非常惊人了。想当年 **GPT-2** 只有 1024 个 token，当时所有人都惊呼：“天啊，这已经足够庞大了，我们以后绝对用不着更多的上下文了。”在你看来，未来的技术演进路线会走向何方？前几天 **Jeff Dean** 还向我畅想过**一万亿 token**（Trillion-token）的超长注意力机制。你认为我们真的应该向万亿 token 注意力进军吗？

<details>
<summary>Original English</summary>

**Thomas Wolf**: That's beautiful. I like how for those who've been in the field for quite some time, we had a lot of work on attention, right? This N square and there was a lot of linear attention. And then somehow all of these disappeared at some point when FlashAttention came around. We discovered we just needed more efficient compute kernels.

Now, I like how we come back to thinking, you know, first principle: what is attention? How can we make that more efficient? So 1 million token is crazy, right? GPT-2 was 1,024 and everyone was like, "Oh, that's really big. We never need more."

Where do you see this going in the future? Like, Jeff Dean was pitching me the other day a trillion-token attention. You think we should go to a trillion-token attention?

</details>

**Olive Song**: 走向超长极限上下文绝对是我们完全可以积极探索的发展方向，对吧？这种极端维度的上下文长度确实是一个令人无比兴奋的探索领域。当然，这需要顶层模型架构设计与底层硬件系统深度协同，需要投入大量的专项科研攻关。

<details>
<summary>Original English</summary>

**Olive Song**: So, that's definitely something we can explore towards, right? Ultra lengths of the context. Definitely, it's something that's very exciting to explore with. And something that architecture design along with hardware would require a lot of research onto that. Yeah.

</details>

**Thomas Wolf**: 你认为在注意力与推理优化领域，是否依然存在许多“容易摘到的果子”（Low-hanging fruit）？比如我们今天看到 **OpenAI** 大幅削减了他们一半的推理账单成本，这背后很可能就是通过对各类注意力机制进行了某种更高效的优化处理。你觉得在探索如何更高效地处理注意力计算方面，是否依然有巨大的红利空间？

M3 之所以引起广泛关注，另一个非常关键的原因在于它的**推理成本极其低廉**——这一方面得益于其精妙的稀疏注意力机制，另一方面也得益于它极小的激活参数量，两者共同带来了极致的推理效率。你觉得我们还能在这条路上走得更远吗？另外我也很好奇，你们团队当初是如何发明出 MiniMax Sparse Attention 的？这个灵感是由内部的某个自动化智能体想出来的，还是依然由人类研究员提出的？能为我们透露一些幕后故事吗？

<details>
<summary>Original English</summary>

**Thomas Wolf**: You think there's still a lot of low-hanging fruits? So, typically today we saw OpenAI really reducing—I mean, we don't know how as a firm, but reducing their inference bill by half, by probably having some more efficient processing around attentions of any type. You think there's still a lot of low-hanging fruit that can be gotten in how we can process that?

So one thing we're still very interested about M3 is how cheap it is, in particular because of this sparse attention and partly because of its small activated parameters, but it's also very efficient. You think we can go even way further?

And maybe how did you guys invent MiniMax Sparse Attention? Was it an agent coming up with the idea? Was it a human still coming up with the idea? Tell us a little bit about that.

</details>

**Olive Song**: 是的。我们坚信在模型架构与推理优化层面，仍然有极大的探索空间和提升潜力可以让模型变得更加高效。特别是针对那些对**延迟极其敏感**、但同时又要求模型具备极高任务能力的复杂场景，我们非常迫切地需要模型在保持高智能的同时具备超高效率。

至于这项技术的发明者——其实这项稀疏注意力架构最初是由我们团队的**一名实习生**研发出来的。是的，你没听错，确实是一位实习生完成的。

这种情况在很多传统 AI 实验室中并不多见，因为在不少实验室里，实习生通常很难直接获取核心数据集、代码工程权限和顶级算力资源。但在 MiniMax，我们对任何渴望为模型做出突破性贡献的人都保持完全开放。因此，这项核心架构的最初设计确实诞生自一位才华横溢的实习生之手。

<details>
<summary>Original English</summary>

**Olive Song**: Yeah. Um, so we do think there's still a lot of work that can get into architecture and inference optimization so that the model can be more efficient, especially if there are tasks that are very latency-sensitive but require very strong capabilities, right? And for those kind of tasks we really want the model to be efficient.

Um, and who came up with this part? Actually I think an intern from our team worked on that. Yeah, an intern. That doesn't usually happen in a lot of labs because I think in some labs interns don't have access to the data, the code, and stuff. But yeah, we are open to anyone who would like to contribute to our models. So, the architecture was actually designed by an intern.

</details>

### 研发组织与项目机制

**Thomas Wolf**: 这太棒了，看来实习生依然大有可为，真是一个振奋人心的好消息！这也恰好引出了我对 MiniMax 内部运作机制的好奇。在上台之前我们交流时你就提到过，在你们公司，任何人都可以主动发起并提议一个研发项目。你能向大家详细介绍一下你们的团队组织架构以及日常的研究工作流是怎样运转的吗？

<details>
<summary>Original English</summary>

**Thomas Wolf**: It's very good. Still some work for interns here. Good news. Um that's also a good segue to also how MiniMax is working internally. So we were discussing before coming on stage, I was saying everyone can propose a project. Can you tell us a little bit about how you are organized, how you do your research?

</details>

**Olive Song**: 好的。我觉得 MiniMax 的研发机制与传统高校实验室、甚至与早期的传统科技大厂都截然不同。

我们内部最核心的做法是：确保搭建好坚实强大的**底层技术底座**与**基础设施**，让团队里的每一个人都能随时去体验、把玩最新的模型，并自主思考模型还有哪些可以提升的方向。

每当一个新模型版本发布上线后，大家在相对自由的探索期里，可以自由测试模型、设计专属的评测基准，主动挖掘当前模型的缺陷与弱点，进而针对性地提出他们希望攻克的改进项目。此时，内部其他对这个方向感兴趣的同事就会主动申请加入该项目组，大家紧密协作攻坚几周甚至几个月。一旦取得突破性验证成果，这项技术就会被直接合并并应用到下一代模型的最终预训练管线中，最终作为核心能力交付给广大用户。

<details>
<summary>Original English</summary>

**Olive Song**: Mhm. Mhm. I think that is very different from school or even in earlier tech companies, it is pretty different.

It's that what we make sure is that we have good foundation and good infrastructure so that anyone can play with the model and can think of what they can improve with the model. And then after model releases when they are free, right? They can play with the model. They can think of their own evaluations. They can find their own weaknesses and propose a thing that they want to improve on the model.

And then other people who are interested in that would, you know, propose to join the project and they will work on it for a couple of weeks or even a couple of months. And when they work out, the final thing is shipped to our model. We use that in our final training and it's shipped out to the audience.

</details>

**Thomas Wolf**: 这种模式非常有意思。也就是说，研究人员可以围绕一个方向沉浸探索很长时间。当你提到“几个月”时，意味着这通常是一次非常深度、扎实的硬核探索。

<details>
<summary>Original English</summary>

**Thomas Wolf**: Interesting. So, you can have people working for a really long time on a project. When you say a couple of months, it can be like really deep exploration.

</details>

**Olive Song**: 确实如此。比如在模型基础架构的创新上，往往需要经历极其漫长的调研论证、算法研究、大量消融实验，甚至需要彻底推倒并重构整个预训练阶段的评测体系。因此，这类底层核心项目确实需要投入更长的研发周期。

<details>
<summary>Original English</summary>

**Olive Song**: Yes. Yes. I would say, for example, architecture might require longer time of investigation, research, experiments, even redoing the evaluations for pre-training. Yes, so it might require longer time.

</details>

### 原生多模态训练策略

**Thomas Wolf**: 非常棒。我知道你们在模型评测上也倾注了极大的心血，我对此深表赞同，我们后续可以深入交流。

不过与此紧密相关的另一个独特亮点，是 M3 以及你们团队在**多模态能力**上的独树一帜。M3 不仅能够处理纯文本，还能深度理解图像与视频。而且据我了解——如果有不对的地方请指正——在 Hugging Face 上的 Model Card 文档中明确提到：该模型从**预训练的第一步起就是作为原生多模态模型进行联合训练的**，而不是像业内普遍做法那样，在纯文本模型训练完成后再去外挂 Adapter（适配器）。你能为我们深入讲解一下背后的技术考量吗？为什么你们认为这一点如此关键？为什么坚持从第一天起就进行多模态端到端联合训练？

<details>
<summary>Original English</summary>

**Thomas Wolf**: Very nice, yeah. And I know you're also very big on evaluation. I agree. We could talk about that.

I think one thing probably related to that is this unique specificity that M3 and your team has around multimodality. So, not just text, but the model can also understand image and video. And as I understand—but please explain better—when you read the model card on Hugging Face, it says the model was trained from the first step as a multimodal, not just have a like adapter after thought, right?

Can you tell us a little bit more about that and why you think it's important, and why starting from the first step on multimodal training and not just training text first?

</details>

**Olive Song**: 我们把这种范式称为**原生多模态**（Native Multimodality）。

在业界目前的很多主流大模型实验室中，一种标准做法是先完成纯文本预训练，随后在外层拼接视觉适配器（Adapter），再去微调训练视觉理解等模态能力。但我们在实验中明确发现：这种后期拼接适配器的做法，实际上会**严重损伤模型原有的纯文本能力**。同时，视觉理解性能的收敛效果也远谈不上理想，因为模型早期的特征表征空间已经被强行收敛固定在了纯文本分布上。这种割裂的流程既不是最优解，从长远来看也缺乏良好的可扩展性——毕竟我们的目标是持续大幅扩充跨模态数据规模。

此外，也有些实验室尝试在预训练进行到一半时（例如通过持续预训练 Continued Pre-training）中途引入多模态能力。但我们的研究表明，这种方法对训练配方（Recipe）极度敏感。针对不同的网络架构、不同的数据混合配比、不同的学习率调度策略，其中途介入的最佳配方完全不同。它极难精准掌控，更致命的是，你根本无法将小模型上的实验结论与超参数直接扩展（Scale）到更大规模的模型上。

因此我们团队反思：既然如此，为什么不干脆**从第一步开始就直接进行原生多模态联合训练**呢？这显然是最自然、最符合第一性原理的路径。

当然我们也清楚，很多实验室在尝试这一路径时都遭遇了灾难性的模型崩溃（Model Collapse）——在联合训练文本与视觉几个 Step 之后损失函数就直接发散爆炸。但我们成功攻克了这一世界级难题。我们在 **ViT**（Vision Transformer）架构优化以及底层训练数据构建上做了极其扎实且深度的工程创新。

例如，我们采用了真正意义上的**交错多模态数据**（Interleaved Data）。这些都是高度自然的图文混合数据，但我们绝不把其中的图像和视频特征强行 Mask 掉，而是完整予以保留；与此同时，我们配合了极其精细严格的数据清洗、特征掩码与高质量的**奖励建模**（Reward Modeling）。这套体系使得我们能够从预训练的最早起点直接启动多模态端到端训练，不仅在大规模扩展时性能持续飙升，而且全程保持极高的数值稳定性，绝不发生训练崩溃。

<details>
<summary>Original English</summary>

**Olive Song**: Um so, we call it native multimodality. And so, it is somehow typical for model labs to train the multimodal, let's say, vision understanding capabilities after the text pre-training is done. They put adapters and then train that part.

But what we found out was that that would actually harm the text performance. And the vision understanding performance wouldn't converge that well because the model is kind of converged towards the text understanding. Um and it's just not the most optimal. And also not the most scalable, if you think about it. We want to scale the data, right?

And also, some labs train this capability from halfway through the pre-training. For example, continued pre-training. But what we found that this would be very, you know, recipe sensitive. It is different for—the recipe would be different for different architectures, different, you know, data mixtures, different learning rates. It's hard to control, hard to, you know, scale your experiment results and conclusions to a larger model.

And so you know, what we thought was why not just training from the very first step? That comes to the most natural. We know that a lot of labs run into problems doing that. The model would collapse after a couple of steps of training, you know, both text and vision understanding, but we managed to solve that problem.

We did a lot of work on ViT and we did a lot of work on the data that we actually training. For example, we do interleave the data, what we call interleave the data. It's actually natural data, but we keep the images and videos in instead of masking it out and we do some pretty good cleaning and masking on the data and we do very good reward modeling so that we train it from the first step and it scales up a lot. Yeah, it does not collapse.

</details>

### 规模扩展与未来算力

**Thomas Wolf**: 这确实是一项令人赞叹的工程与算法突破。那么我们未来是否可以期待看到参数规模更庞大的旗舰模型？毕竟 M3 当前的体量依然算相对小巧轻量，对吧？

<details>
<summary>Original English</summary>

**Thomas Wolf**: That's really impressive. Should we expect much larger model in the future? So this one is still fairly small, right?

</details>

**Olive Song**: 目前 M3 的总参数量是 4280 亿（428B），每次推理激活的参数量为 230 亿（23B）。

<details>
<summary>Original English</summary>

**Olive Song**: It's 428 billion parameters, 23 active billion.

</details>

**Thomas Wolf**: 那么，你们未来有计划迈过**万亿参数**（Trillion Parameter）的大关吗？

<details>
<summary>Original English</summary>

**Thomas Wolf**: Well, do you think you will go past the trillion?

</details>

**Olive Song**: 毫无疑问，未来一定会。因为现实中存在大量极其艰深的复杂任务，参数规模过小的模型在泛化与推理极限上始终存在物理天花板。我们在未来的模型规模演进上绝对有着远超于此的宏大抱负。

<details>
<summary>Original English</summary>

**Olive Song**: Definitely. Yeah, definitely in the future. There are many tasks that wouldn't be able to—the smaller parameter model wouldn't be able to perform very good at. We are definitely going more ambitious than this.

</details>

### 商业生态与开源社区

**Thomas Wolf**: 太棒了，我们由衷期待着。

关于 MiniMax，另一个始终让我非常着迷的地方在于：你们不仅拥有顶尖的基础模型研究，同时还打造了涵盖多品类的**丰富 C 端应用与产品矩阵**。我清楚地记得，MiniMax 最早在 Hugging Face 平台上开源模型是在去年 1 月份，也就是大约 18 个月前。当时我们与你们团队深入交流，想了解你们正在开展的工作，我惊讶地发现你们旗下的几款产品就已经拥有了极为庞大的用户调用量。

你能向大家讲讲这段创业历程是如何展开的吗？最初究竟是你们先做了一批爆款应用、沉淀了海量真实数据后决定自研大模型并组建研究团队，还是有着其他的演进路径？

<details>
<summary>Original English</summary>

**Thomas Wolf**: It's great. Looking forward. Um another interesting thing I always find fascinating about MiniMax is how you also have this whole range of apps and product, right?

So, I remember already—so MiniMax started to open source things on the Hugging Face platform in January last year. So that's 18 months ago, and we were chatting a little bit about the team to understand what you were doing, and I remember you were already having a huge usage on some of these apps.

Can you tell us a little bit how this started, right? Was it basically you had a lot of apps and then you thought "we have all this data, why not training a model" and then build up research team? How is the story there?

</details>

**Olive Song**: 我们的故事自始至终都是**以模型为绝对核心**（Model-first）从第一天演进至今的。

打造一个能够深度理解全模态视觉输入、并能自由生成全模态内容的原生多模态通用底座模型，是我们 CEO 在公司正式创立的第一天、甚至在公司正式注册成立之前就已经确立的初心与顶层规划。那是通向 AGI 的终极梦想。我认为这个战略愿景确立得非常早，甚至远远早于 **ChatGPT** 的横空出世。

至于丰富的产品矩阵，则是随着底层模型能力的不断突破而自然孵化衍生的。因为当你拥有了强大的模型能力后，你必须让普通大众能够极佳地体验到这种智能。毕竟世界上能够直接调用 API 进行开发的工程师是极少数，我们绝不能指望全球每一个人都通过 API 终端去感受 AI 的魅力。因此，我们需要打造极其友好的交互界面、设计精良的 App 以及匹配贴合的具体业务场景，让普通用户能够沉浸式地体验模型的强大。

截至目前，我们旗下的产品矩阵已经覆盖了全球超过 **200 个国家和地区的 3 亿多用户**，同时也在为全球超过 **100 万家企业客户**提供服务。

<details>
<summary>Original English</summary>

**Olive Song**: Um our story is model from the first day. So, I believe that a multimodal model that can understand all visions and outputs all modalities was the first thing that our CEO planned on the first day even before the company even started. So, that was the dream of AGI. I think that was very early, even before ChatGPT came out.

And then apps were something that comes along because you have some model capabilities, you want people to experience it well. Not many people can use it with API, right? We can't expect everyone to experience with API. So, we need good user interaction interfaces, good apps, good scenarios that people can experience model with.

I think actually those apps covered more than 300 million people around 200 countries globally. And I think over a million companies as well.

</details>

**Thomas Wolf**: 是的，当初我第一次得知这一庞大体量时真的深感震撼，外界往往很难想象到你们的产品在全球范围内已经积累了如此巨大的使用规模。

这也引出了一个关于**开源商业模式**的经典讨论：在当下的商业环境下，开源模型固然能够回馈社区，但企业自身也必须建立清晰健康的商业变现与收入造血能力。比如像 M3 这样强大的模型，你们最终决定完全免费开源，这对全球 AI 开发者社区来说无疑是一件功德无量的善举。

你如何看待开源与商业化的平衡？你们在内部自研应用中是否会部署更专门的专属模型？你认为在未来的发展中，MiniMax 会长期坚持开源战略吗？你们团队内部目前对开源抱有怎样的文化与心态？

<details>
<summary>Original English</summary>

**Thomas Wolf**: Yeah, this was mind-blowing when I heard about the size, and we don't often realize the size of this type of usage already.

And that kind of brings me to the question around open source business model and all of that, which is the always existing question, which is right now it's nice to open source model, but you also need to have some revenue stream, right? So, I guess M3 is something you decided, for instance, to be for free, and I think it's great for the world.

How do you see this? Do you also have some specific models you use for the app? Do you think in the future you'll keep open sourcing models? How is the culture around open sourcing right now?

</details>

**Olive Song**: 就我个人立场、以及整个基础模型研究团队而言，我们始终发自内心地渴望能够持续开源我们的前沿模型，这始终是我们坚定的既定路线。

因为我们真真切切地见证了**开源社区的集体智慧**是如何合力帮助模型实现快速进化与迭代的。举例来说，每次模型开源后，我们都能从全球优秀的开发者社区中收到极其海量且宝贵的模型性能实测反馈，甚至直接在开源仓库中收到针对各种边角缺陷的 Pull Request（PR）。这些来自一线开发者的贡献极其珍贵，它们被源源不断地沉淀并吸纳到了我们后续迭代的全新模型版本中。因此，持续拥抱开源绝对是一件无比美妙且共赢的事。

<details>
<summary>Original English</summary>

**Olive Song**: Personally, and also for the model research team, we always hope to open source the models. That is our plan.

Because we really see how the open source community together can help the model build better. For example, we receive a lot of feedbacks on the model performance from the great community, and we receive PRs on whatever we open source. And those are very, very valuable and comes to our later versions. So, definitely open sourcing is great.

</details>

### 多模态Agent与自动化研究

**Thomas Wolf**: 确实如此。那么在今天现场，面对台下以及全球正在使用 M3 和 MiniMax 技术的广大开发者与用户，你有什么特别想向大家征集的吗？比如你们最希望社区把哪些维度的反馈传达给你们？当看到开发者魔改模型或进行各种微调实验时，你们会主动跟进研究吗？你们认为目前从开源社区汲取哪些输入，对塑造未来下一代模型最有帮助？

<details>
<summary>Original English</summary>

**Thomas Wolf**: That's great. And actually, do you have some ask for the audience, people who are using M3 or MiniMax? Is there something you would love them to send back to you as feedback? Do you read when people try to modify the models or play around, you know, tweaks? Or what is the best thing you think you can take from the community for future models, for instance?

</details>

**Olive Song**: 嗯，我认为最关键的是大家在实际落地中踩到的所有真实坑点和问题，尤其是涉及**多模态融合**的复杂边缘场景。

毕竟，这是业界首次将如此深度的原生多模态与超长上下文技术在一个模型中融合落地，我们在未来的技术演进上必然会更加激进与宏大。虽然当前版本在某些特定极端场景下可能依然存在些许瑕疵，但我们正在争分夺秒地快速改进。因此，任何关于“模型在哪些具体任务上表现不够理想”的真实反馈，我们都将毫无保留地作为核心优化目标，在未来的下一代版本中彻底攻克。

此外，还有社区用户迫切期盼的任何全新特性。比如前段时间呼声极高的“**思考预算/深度推理耗时**”（Thinking Effort / Reasoning Effort）机制——只要大家把需求明确提出来，我们就会竭尽全力在未来的模型架构中将其研发落地。

<details>
<summary>Original English</summary>

**Olive Song**: Mhm. I would say whatever issues that people are running into, especially with multimodality, right? This is the first time that we're combining it together. We are definitely going more ambitious on that in the future. It might have some flaws right now, but we are improving on that. So, whatever that's feedback that model is not doing that great, we will definitely improve that in future versions.

And also, whatever features that people want. Say, you know, for example, thinking effort. Right? Some people ask for that. Like everyone can ask, and we will try to accomplish that in the future models.

</details>

**Thomas Wolf**: 明白。关于多模态在**编程智能体**（Coding Agent）领域的应用，你目前是否观察到了大规模的落地爆发？我个人总感觉多模态在辅助编程这一块似乎依然处于未被充分挖掘的蓝海状态。

<details>
<summary>Original English</summary>

**Thomas Wolf**: Yeah. Do you see a lot of usage right now already in multimodality in terms of coding agents? I feel like it's a little bit underexplored.

</details>

**Olive Song**: 确实，目前整个行业对多模态 Agent 的挖掘才刚刚起步。但它实际上蕴藏着极其巨大的潜力，能够解锁前所未有的智能体应用场景。

设想一下：在实际业务中，你希望智能体去阅读一份复杂的 PowerPoint 幻灯片，或者解析排版混乱、极度非结构化的视觉行业研报；或者你直接向智能体输入一段长达数小时的操作演示视频，要求模型在完全理解视频时空逻辑后，自主调用各种外部开发工具去执行复杂的一整套下游操作任务。这种原生多模态能力的就位，将彻底引爆极为广阔的端到端 Agent 商业新范式。

<details>
<summary>Original English</summary>

**Olive Song**: It is, but it can actually unlocks a lot of capabilities and a lot of agent applications.

Say that for example, you want a model to read a PowerPoint, or to read some report that is not very structured. And you want it to understand a very long video—say that you dump in a long-playing video, and then you want the model to act using some tools after understanding it. And it unlocks a wide variety of agent use cases.

</details>

**Thomas Wolf**: 也就是说，未来的智能体终于可以直接完整观看我在 YouTube 上发布的教程视频，并彻底看懂我视频里演示的编程工具具体该如何配置和使用了？大概就是这种美妙的体验对吧？智能体终于具备了从 YouTube 教学视频中直接自学硬核技能的能力？

<details>
<summary>Original English</summary>

**Thomas Wolf**: So, like the agent could finally watch my YouTube tutorial and understand how to use my coding tools, how I described it? Is it something like that? Could the agent finally watch YouTube tutorials and understand things from them?

</details>

**Olive Song**: 没错，完全是这样！这在技术上是完全可以实现的。

<details>
<summary>Original English</summary>

**Olive Song**: Yeah, yeah, yeah. I think so.

</details>

**Thomas Wolf**: 那么在你们团队内部，你们自身是否已经在深度重度依赖各种编程智能体工具了？在基础代码编写之外，你们的**日常科研工作流**是否也已经实现了高度的自动化运转？你们内部的实际协作机制是怎样的？

<details>
<summary>Original English</summary>

**Thomas Wolf**: Do you use a lot of agent coding tools internally? Is it like—I mean, coding for sure, but like is it also already in terms of research? Is it automated part or not? How does this work?

</details>

**Olive Song**: 是的。我们内部深度自研了一整套专属的**科研评估与实验驱动框架**（Research Harnesses），用来对我们内部的端到端研发工作流进行全面自动化。可以毫不夸张地说，我们日常非常大比例的科研流程都已经交由智能体全自动执行了。

大家可以看到，当前全球最顶尖的前沿基准模型，无一例外都在追求极高阶的底层自动化能力——比如让模型自主进行 GPU 底层算子（Kernel）优化、让模型自主完成针对下一代模型的后训练（Post-training）、让模型全自动合成与提纯高质量训练数据等等。

目前越来越多的前沿模型开始展现出胜任这些复杂任务的能力，这其中就包括 M3。事实上，M3 在超长决策周期（Longer Horizons）规划以及底层算子自动优化等极端复杂场景下表现得极为出色。因此，我们能够充分将 M3 的这种核心模型能力进行系统化封装编排，让它全天候深度赋能我们的日常科研循环，从而使得我们内部的技术迭代与演进速度呈指数级加快。

<details>
<summary>Original English</summary>

**Olive Song**: Yes. We have our own research harnesses. We build our own research harnesses that automate our workflows. I would say a lot of our workflows are automated.

You can see how the latest frontier models all pursues capability like kernel optimization, right? Like let the model post-train other models, let the model build data, auto data, stuff like that. You can see how more and more models are capable of doing those, including M3.

Actually, we were very good at those cases—longer horizons and kernel optimizations. And so we can use that model capability, harness it together, and help with our daily routine, and make our iterations even faster.

</details>

**Thomas Wolf**: 所以说，现在的 M3 已经在全自动训练构建 **M4** 了吗？

<details>
<summary>Original English</summary>

**Thomas Wolf**: Is M3 building M4 already?

</details>

**Olive Song**: 哈哈，它目前正在全力构建 **M3.1**！

<details>
<summary>Original English</summary>

**Olive Song**: Um building M3.1.

</details>

**Thomas Wolf**: 已经开始做 M3.1 了，太棒了！（笑）看来我们得赶紧加把劲去健身房锻炼身体跟上节奏了。

<details>
<summary>Original English</summary>

**Thomas Wolf**: M3.1, okay. [laughter] Let's hit the gym.

</details>

**Olive Song**: 已经在火力全开了！

<details>
<summary>Original English</summary>

**Olive Song**: Already.

</details>

### 多智能体协作与未来展望

**Thomas Wolf**: 在对话的尾声，我很想听听在接下来的几个月乃至更长的时间里，最让你感到兴奋的技术趋势是什么？无论是具体的产品功能演进，还是你期待在整个 AI 行业发生的宏观范式变革，只要是你脑海中最魂牵梦绕、且你确信即将成为现实的方向，都可以和我们分享一下。

<details>
<summary>Original English</summary>

**Thomas Wolf**: Um I would love to finish on what you find exciting in the coming month. What do you think it can be in terms of feature or things you want to see happening in AI, or more generally in terms of whatever really is top of your mind and it's going to happen?

</details>

**Olive Song**: 令人心潮澎湃的新技术实在是太多了。但如果要选一个我近期认为最令人兴奋的方向，那绝对是**多智能体系统**（Multi-Agent Systems）。

目前越来越多的前沿 AI 应用开始深度落地这一范式，包括**模型动态路由**（Model Routing）与多智能体分工协同网络。这一体系不仅能够大幅拓展系统整体的能力边界、攻克单体模型无法企及的高难度复杂工程任务，同时它也像一面清晰的镜子，能精准映射出每一个底层模型各自擅长什么、在哪些维度存在短板与盲区。开发者可以依托多智能体网络释放出无穷无尽的创造力与可能性，这真的是一个极其令人振奋的发展方向。

<details>
<summary>Original English</summary>

**Olive Song**: A lot of things are very exciting. But what I recently find the most exciting would be a multi-agents that I think a lot of AI applications are using, model routing, multi-agents that allows even more capabilities, even more complex tasks, and also it tells us what the models are capable and not capable of, and you can, you know, do a lot of things with that. It's pretty exciting.

</details>

**Thomas Wolf**: 非常感谢你，Olive。非常荣幸能邀请你来到现场与大家深度交流！

<details>
<summary>Original English</summary>

**Thomas Wolf**: Thanks a lot, Olive. Pleasure to have you.

</details>

**Olive Song**: 非常感谢你的邀请！

<details>
<summary>Original English</summary>

**Olive Song**: Thanks for having me.

</details>

**Thomas Wolf**: 谢谢现场的每一位朋友！（掌声）

<details>
<summary>Original English</summary>

**Thomas Wolf**: Thanks, everyone.

</details>