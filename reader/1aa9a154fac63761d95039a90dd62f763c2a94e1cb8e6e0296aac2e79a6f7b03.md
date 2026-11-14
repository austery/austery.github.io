---
author: AI Engineer
date: '2026-05-30'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=phchDt63qAA
speaker: AI Engineer
tags:
  - edit-prediction
  - model-training
  - distillation
  - production-data
  - code-intelligence
title: Zed 2 模型训练：生产环境下的编辑预测模型构建详解
summary: 本文详细介绍了 Zed 公司如何构建其编辑预测模型 Zed 2。内容涵盖了从生产环境数据收集、使用‘教师模型’进行蒸馏训练，到‘已定数据’概念的引入及其过滤方法。同时，文章还阐述了模型评估、优化训练数据以及在生产环境中进行实验部署的策略，旨在提升代码编辑的智能化体验。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Zed
products_models:
  - Zed 2
media_books: []
status: evergreen
---
### 编辑预测模型的核心概念与数据管道

**编辑预测**（Edit Prediction）的核心在于，为模型提供光标周围的代码区域，并要求其预测用户即将进行的下一次编辑。为了实现这一目标，模型会接收多种输入数据，包括用户最近的编辑历史、光标位置、类型定义、变量定义以及光标附近的诊断信息（如错误提示）。由于此功能需要在每一次按键时快速响应，因此它非常适合使用一个小型、专业化且经过微调的模型，该模型专注于执行此特定任务。Zed 公司近期发布的 **Zed 2** 模型便是基于这一理念构建的。

其训练流程的起点是收集用户选择加入的生产环境数据。这种方法之所以有效，是因为它能捕获代码编辑过程中的快照，完整地记录下所有相关数据，包括类型定义等上下文信息，并将其转化为可用于训练的数据。

<details><summary>Original English</summary>
I'm Ben Kunkel. I'm the edit predictions lead at Zed. Um, we recently announced our model Zed 2 and this is how we trained it. I'm going to go through a lot. This is obviously a pretty short talk. So, I'm going to try and leave enough time for questions at the end, but it's if you're not familiar with training models, uh, it's going to be a bit of a whirlwind tour. So, if you're not familiar with edit prediction, it's essentially giving the model a region of code around the cursor, asking them to predict the next edit that you're going to make. We give it various data in such as your recent edits, your cursor position, the type definitions and variable definitions or of things around your cursor, as well as diagnostics, errors, etc. It obviously needs to be very fast cuz it runs on every keystroke. And so, it's ideal for a small specialized model, fine-tuned. It can do this task and this task only. Um, so that's what we've we've done. So, the pipeline in essence is taking these opt-in production data. Uh, this works really well cuz it's snapshots. So, all of that data that we have collected, related like related types and definitions and etc., all of that gets captured and then we're able to turn that into training data.
</details>

### 蒸馏训练与数据精炼策略

为了将收集到的生产数据转化为训练数据，Zed 采用了**蒸馏**（Distillation）过程。该过程涉及使用一个**前沿模型**（Frontier Model），也称为“教师模型”，输入所有收集到的上下文信息，并要求它预测用户的下一个编辑操作。然而，这一过程并非易事。即使是强大的前沿模型，在面对海量输入时也可能产生不确定或多样的预测结果（例如，100,000次请求可能产生100,001种答案）。因此，需要对输入给前沿模型的提示（prompt）进行精细调整，以获得高质量的预测输出。

为了进一步提升预测质量，Zed 团队会进行离线或静态评估。这些评估包含一些启发式规则，用于判断模型是否仅仅撤销了用户刚输入的内容，或者是否忽略了指定的**可编辑区域**（editable region）边界。如果模型表现不佳，这些不理想的预测会被发送给另一个类似的前沿模型，并附带一个“修复”提示，要求其修正错误。这个过程被称为“修复步骤”（repair step）。

一旦不良预测得到修复，教师模型生成的“正确”输出就可以作为**学生模型**（Student Model），即 Zed 2 的预期输出，用于训练。在这一点之前的所有数据处理步骤都是可复用的，可以被缓存并用于训练多个实验。通过将前沿模型预测的结果转换为实验所需的特定格式，可以进行进一步的实验。这种**提示格式化**（prompt formatting）是实验特定的，它决定了是否包含诊断信息、编辑历史的多少等。最终，教师模型提供的结果被转化为用于蒸馏和训练学生模型的提示。

<details><summary>Original English</summary>
In order to do that, we use a process called distillation where we take a frontier model, we give it all of that input, and we say, "What prediction would you make?" This is a pretty difficult process as it turns out, even though the frontier models are pretty smart. If you ask them 100,000 times, they're going to give you 100,001 answers, right? And so, there's a bunch of problems there that we've had to like finely tune the prompt that we're giving that frontier model in order to get good things out. One of the things we've done to try and get better, um, predictions to train off of is we run some offline or static evaluations. So, uh, we have some heuristics for, you know, is it just undoing what you just typed? Is it ignoring that editable region boundary that we've given it, etc. And if it does, then we send it to another frontier model with a similar prompt like, "Hey, it failed in this way. Can you fix it?" And so, that we call that the repair step. And then, once we've repaired the bad predictions, then we can essentially turn what the teacher made into the expected output of the student model or Zed 2. Um, up until that point is reusable across experiments. So, this is stuff that we can cache. We can train multiple experiments on top of that by turning what the, uh, frontier model predicted into the format that we want the experiment to output. And so, that's the next piece is this prompt formatting. This is experiment specific. I.e., are we including diagnostics this time? Are we not? How much of the edit history are we including? Those are the kinds of experiments we're running. And so, we'll turn what the teacher gave us into the prompt to, uh, distill and train our student model. And then we'll we'll do our uh, final set of offline evaluations.
</details>

### “已定数据”概念及其在训练中的应用

一个特别的训练方法是利用所谓的“**已定数据**”（Settled Data）。其核心思想是，当用户请求模型进行预测时，最终用户会自己完成代码的编写。模型可以等待用户停止编辑指定的**可编辑区域**，然后将其快照保存下来，作为训练数据。然而，这种方法存在固有的“**噪声**”（noisy）问题。因为在等待用户完成编辑的过程中，用户可能会改变主意，或者有其他代理（agent）介入完全重写代码，导致最终状态与模型做出预测时的状态截然不同，使得原先合理的预测变得不再合理。

为了过滤掉这些噪声数据，一种方法是让教师模型生成10个预测，然后使用如 **Levenshtein 距离**（Levenshtein's distance）之类的度量方法，检查其中是否有任何一个预测结果与最终的“已定状态”足够接近。如果接近，则表明该预测是可信的，并且不是由于用户彻底改变想法或输入完全不同而产生的噪声。然而，这种方法成本高昂：对于100,000个样本，可能需要进行数百万次前沿模型请求，这在计算上是难以承受的。

幸运的是，随着学生模型（如 Zed 2）的质量不断提升，它们在预测能力上已接近教师模型。因此，Zed 团队现在可以使用学生模型进行多次（例如50次）预测，这几乎不产生额外成本。通过比较这些学生模型的预测与已定状态的 Levenshtein 距离，同样可以判断预测的有效性。

<details><summary>Original English</summary>
Um, the nice part about this whole process, we've designed it in such a way that it's all JSONL or a single line is a giant JSON object. These files get huge. Um, but each stage just adds some more fields to it or moves some fields around. So, it's a very like, uh, fluid and dynamic process. Um, we're generally doing 100,000 examples to train a model. Like, that's our peak. For these smaller experiments, we'll cut it down lower to 10 to 50k range. Um, one interesting thing that we're trying right now is to use what we call settled data, which is the idea that eventually the user writes the answer, right? When you request a prediction as you're typing, eventually you're going to like write the code in the way that you wanted it. And so, we can wait given that we're the editor, we can just wait until you stop editing that editable region that we gave the model, snapshot it, and save it. Um, and then use that to inform our training. Uh, this is actually this is very noisy because by waiting on the edit region to settle, you could change your mind, you could have an agent come in and rewrite it completely. It could be completely different from what it looked like when the prediction was made. So, what was maybe a reasonable prediction, it no longer looks reasonable. So, we need some way to filter that out. One way that we can do that is by having generating 10 of the teacher predictions and seeing if any of them are close using like Levenshtein's distance type of thing. See if any of those are close to the settled state. And if they are, we know a couple of things. We know it's predictable and that it's not noisy and, you know, completely different than what the input was, right? Cuz we're giving the same input that we gave for the original prediction for this new prediction. Um, that turns out to be quite expensive. For 100,000 examples, you're then doing, you know, a million frontier model requests. That is prohibitively expensive. Fortunately, given that we've now trained models using the original teacher predictions, uh, our student models or Zed 2 is approaching the teacher in terms of quality of prediction. So, instead of running the teacher, we can run our student checkpoint or something 50 times. That costs us basically nothing. And we can see do the same process, see if any of them are close to the settled region using Levenshtein or something similar.
</details>

### 理想训练样本的识别与评估指标

通过分析预测结果与“已定状态”之间的距离范围，可以识别出理想的训练样本。距离非常远的样本可以被视为噪声，而距离非常近的样本则代表显而易见的预测（例如，输入“function add A plus”，模型预测“B”）。真正有价值的训练数据位于两者之间的“中间区域”，特别是那些超出了学生模型训练数据截止日期的新函数或新概念，这些是用户真正期望模型能够处理的。Zed 通常不直接使用“已定状态”本身作为训练数据，因为其固有的噪声问题，而是使用最接近已定状态的预测结果进行训练。

在进行离线评估（offline evaluations）时，Zed 使用一个**留出测试集**（held out test set）来确保模型不会在测试数据上进行训练。评估指标包括：**Delta Car F**（一种基于 n-gram 比较的 Levenshtein 距离变体），用于衡量预测与实际结果的相似度；**反转率**（reversal ratio），即模型撤销用户刚刚输入内容的比例；以及在生产环境中的**保留率**（kept rate）。在评估过程中，通常会运行三个教师模型的预测，因为许多编辑场景没有唯一的正确答案。如果模型预测结果接近这三个教师预测中的任何一个，则可以认为该预测质量较高。

<details><summary>Original English</summary>
Um, this gives ideal training examples, right? Cuz there's a by looking at the range of distance to the settled state, there's a region that are super far away, we can be confident that that's just noise. There's a con- there's a region that's super close, that's like it's super obvious what you're going to be doing, right? You you typed function add A plus, it's obviously B, right? Uh, but then there's this interesting section in the middle where it's almost. That's like the ideal what we want in our training examples. For example, the stuff that's past the training data cutoff of our student model. So, new functions etc. that it's never seen before that you actually wanted. And that's going to show up in these new training examples that we can then, um, train off of. We generally don't train off of the actual settled state just because it's still noisy, but we can train off of, you know, what was closest to the settled state. So, to run those offline evals, we're running on a held out test set. Um, just making sure we're not training the model on the same stuff we're testing it on. Um, delta car f is our Levenshtein. Essentially, it does a like n-gram comparison of various sizes of n. Um, and then we're tracking this reversal ratio, reversals being it's undoing exactly what you just typed. Um, and we can also look at the kept rate in production. Uh, we're gener- when we're evaling, we're generally running against three teacher predictions cuz a lot of these have no one right answer. And so, by generating three distinct answers that were all generated by a frontier model, we can be pretty sure that if it's close to one of those, it's a pretty good prediction.
</details>

### 生产环境部署与质量监控

在完成离线评估后，模型需要进入生产环境进行部署和实验。Zed 建立了一个实验页面，用于管理模型在生产环境中的 A/B 测试。例如，可以将一个新模型采样到 15% 的流量，其余流量则由现有模型处理。通过一个内部仪表板（dashboard），可以监控这些实验的关键指标，如**接受率**（acceptance rate）、**延迟**（latency）等。这个页面使得团队能够逐步推广模型，例如先设置为 15% 的流量，然后增加到 20%，最终使其成为主要的运行模型。

对于**诊断错误计数**（diagnostic error counts），其监控方式与预期基本一致：记录模型做出预测前后的错误数量，并以此来评估模型的质量。在问答环节中，当被问及如何确定“已定状态”时，Ben Kunkel 解释说，他们目前采用一个简单的启发式方法：如果用户在指定的可编辑区域停止编辑10秒钟，就将其视为已定状态。只有当用户持续编辑而没有超过10秒的停顿，才不会对其进行快照。这种方法虽然简单，但在实践中被证明是足够有效的。

<details><summary>Original English</summary>
So, for our experiments, um, this is the training and production part of it. Uh, those evals that we um, don't necessarily correlate to what users actually want in their editor. And so, we have this page set up of our experiments. These are the two that are live right now. You can see over here, we've got this one being sampled at 15% and that's going to get the rest of production traffic. And so, we have a dashboard that I can't show you of the acceptance rate, latency, all of that kind of stuff for these experiments. But this is a page that we created so that we can, you know, once we've deployed it, set it to 15% of traffic, set it to 20, make it our our live running model. Um, so this V 0211 seed coder, this is what we released as Zed Um, for diagnostic error counts, it's pretty much exactly what you'd think. We snapshot how many errors there are before the prediction, how many there are after. And then we're and try and use that to judge the quality of the model. So, that's it. I There was a lot. Happy to answer, uh, questions. I think we have five or eight minutes left. So, yeah. Uh, you said it's very noisy to determine like the settled state. Are there any signals that you can share that you use like like git commit, for example, or Sorry, what was the algorithm? Uh, so you said that uh, determining the settled state like when the user has is satisfied with that block of code, for example, is very noisy. Are there any particular signals that you can use already that are useful like, for example, they get committed something. Sure, yeah. Um so we don't look at the get commit, we could. But uh right now we just do like you stop editing that area for 10 seconds. And that that serves as a rough enough heuristic that um so it's only in the cases where you are like consistently editing that location for longer um without pausing for 10 seconds that we wouldn't snapshot it. Um any other questions? All right, I guess you guys get your time back. Thank you for coming. >> [applause]
</details>