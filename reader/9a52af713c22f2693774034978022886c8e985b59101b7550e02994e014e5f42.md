---
author: AI Engineer
date: '2026-11-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=fTHByDwTxGM
speaker: AI Engineer
tags:
  - post-training
  - reinforcement-learning
  - agent-alignment
  - code-generation
title: Gemini 4 后训练：面向真实工程任务与模型对齐
summary: Google DeepMind 后训练负责人 Melvin 介绍了 Gemini 4 系列的研发与后训练进展。团队通过过滤饱和任务、引入基于真实代码提交的多维度评分准则（Rubric）、沙盒防作弊机制以及轨迹行为对齐，降低模型伪造与欺骗率，并借助 Google 内部逾 10 万名工程师的日常真实使用形成反馈飞轮，实现高频发布。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Melvin Johnson
companies_orgs:
  - Google DeepMind
products_models:
  - Gemini 4
  - Gemini 4 Argon
  - Gemini 4 Carbon
  - Gemini 4 Hydrogen
media_books: []
status: evergreen
---
### 破除质疑与 Gemini 4 密集发布节奏

大家好，很高兴来到这里。我是 Melvin，负责 Gemini 的后训练（post training）。今天我想带大家了解一下我们对 Gemini 4 进行后训练的过程。

我们的旅程始于外界认为我们不再是前沿模型实验室。这里有一个例子，大家常说“Gemini 已经完蛋了（cooked），但 GCP 势头正盛”。“从各方面来看，我们认为 DeepMind 已经不再是前沿实验室了。”我们非常尊敬的 Ethan Mollick 也用他客气的方式评价我们说：“各次发布之间的间隔相当长。”

我今天来到这里是要告诉大家，我们并没有沉寂，我们就在这里。在过去的 28 天里，我们发布了 Gemini 4 Argon，宣布并上线了 Carbon。所以我们正处于全速推进的状态，而且这还不是全部。

在这个过程中，我们甚至收到了 Dylan 的致歉，他说：“正式向 Google 致歉，他们其实并没有完蛋。”Ethan 也表示，Gemini 4 最显著的特点之一就是我们发布产品的速度。

我们此前曾经历过 236 天没有推出前沿模型，而在最近 28 天内连续推出了两款前沿模型，交付速度提升了 10 倍。大家曾觉得 Google 似乎落后了，但 Google 并没有完蛋。看到这种舆论转变令人欣慰，站在另一边感觉很好；当然，收到批评意见同样是好事，因为那会促使你做得更好。

<details>
<summary>Original English</summary>
Hey everyone, good to be here. I'm Melvin and I lead post training for Gemini. So today I thought I'll take you through a little journey of how we post train Gemini 4. And our journey begins by people calling us not a frontier model. Um, so here's an example. You know, people say Gemini is cooked, but GCP is cooking. For all intents and purposes, we believe Deep Mind is no longer a frontier lab. Ethan Malik, who we respect a lot, he says in his own nice way, pretty long gap between launches is what he calls us.

And I'm here to tell you we're not dead. We're here. uh and we have launched uh Gemini 4 Argon, we announced Carbon and we launched Carbon all within the last 28 days. So we're on a we're you know we're on a run here and that's not it.

Uh in the process we actually garnered an apology from Dylan. No, he says official apology to Google. Uh they're actually cooked. They're not cooked. Um Ethan says, you know, one of the most significant aspects of Gemini 4 is the speed at which we're launching things.

Um so we've gone 236 days without having a Frontier model and we've had two Frontier models in 28 days. That's a 10x improvement in our speed of shipping. And you know, people call us Google kind of cooked, but Google's not cooked. So it's good um to see see that sentiment. It's glad to be on the other end. It's also good to be on the receiving end of the bad comments because it pushes you to do better.
</details>

### Carbon 与 Hydrogen 的能力与基准表现

首先我想播放一小段视频，展示 Carbon 构建的一系列成果。

谢谢大家。

模型能自主制作出这段视频值得赞赏。大家在视频中可以看到很多出色的案例：模型在使用 Blender 构建 3D 模型资产方面表现大幅提升，里面还有很多游戏、真实世界的应用场景、模型处理以及多模态文档。

但这不仅仅停留在演示上。在许多面向客户的真实场景中，Carbon 实际上位列第一。我们特别兴奋的一点在于，它不仅在这些基准测试中表现卓越，而且成本要低得多。

在 Cursor Bench 上，它是目前排名第一的模型，而且比排名第二的模型便宜 3.3 倍。在针对深度研究（deep research）查询的基准测试 Perplexity's Wander 上，它是表现最好的模型；大家看到有竞品模型发布，但我们比那里的次优模型便宜 9 倍。在 Zapier 的 Automation Bench 上，我们同样位居第一，同时每个任务的成本便宜 2 倍。

不仅如此，今天我们公布了 Gemini 4 系列的新成员——大家应该不会感到意外——那就是 Hydrogen。

大家可能在今天早些时候看到了发布消息。Gemini 4 Hydrogen 旨在将 Gemini 4 的智能普及给每一个人。它速度快、可靠，并已在 Anti-gravity、Gemini API、Gemini 应用程序以及 Google 搜索等所有端面上线。

我这里有一张图表，展示了许多人可能熟悉的 AA 指标，横轴代表时间。可以看出，在同等智能水平下，它是最快的模型之一。为了让大家了解 Gemini 的进步幅度：此前 3.8 Flash 在 Terminal Bench 4 上的得分约为 20%，而 Hydrogen 约为 60%。我们在速度提升至 3 倍的同时，性能表现也提高了 3 倍。这绝非易事，我们非常高兴能把它交到大家手中，供大家构建应用。

至此，我们的 Gemini 4 系列构建完成：我们拥有面向前沿深度智能的前沿模型 Gemini 4 Carbon，以及适用于日常执行的高速模型 Gemini 4 Hydrogen。我们未来还会推出更多以元素命名的版本。当然，元素周期表上还有很多元素，要用完它们我们还有大量工作要做，但我们很高兴能将其推出供大家测试和使用。

<details>
<summary>Original English</summary>
I want to start by playing a little video of a bunch of things that uh Carvin has built.

Thank you.

Now, kudos to the model for building that video uh itself. So you saw great examples of the model doing much better at 3D model building assets using Blender. There's lots of games in there. The real world use cases, model processing, multimodel documents. Uh but you know, it's not just the uh the demos. Carbon's actually number one on a bunch of real world customer use cases. And one of the things that we're really excited about is, you know, it's not just uh really good on these benchmarks, it's actually much cheaper. Um, so on Cursor Bench, it's the number one model today and it's 3.3 times cheaper than the second best model. On Perplexity's Wander, which is a benchmark for deep research um queries, it's the best model. you know, you saw um competitor models come out were 9x cheaper than the second best model there. And on automation bench, which is Zapier's uh benchmark, again, we're number one while being two times um cheaper per task.

And that's not it. I mean, today we announced the new element uh to our Gemini 4 series, and it's not surprise. Uh it's uh hydrogen. Um, so you know, you might have seen the launch earlier today. Gemini 4 hydrogen is where we're trying to bring the Gemini 4 intelligence to everyone. It's fast, it's dependable, it's launched on all surfaces on anti-gravity, on the Gemini API, in the Gemini app, and on search. Um, and you know I have a graph that shows the AA index with many of you might be familiar with and time on the x-axis. You can see it's one of the fastest models for that level of intelligence. And to give you a sense of how far you know Gemini has come, 3.8 flash on terminal bench 4 was about 20%. And hydrogen is about 60%. So we're three times better performant while being three times faster, right? So that's no easy task and we're, you know, really happy to bring that to you in your hands so you can build things with it.

And that completes, you know, our uh Gemini 4 series. So we have Gemini 4 carbon a frontier model for deep frontier intelligence. Gemini 4 hydrogen which is fast for everyday uh execution and we'll have more elements you know of course there are many elements left in the periodic table and we have a lot of work to do to exhaust them uh but we're glad uh to put it out there for you all to test it and for you all to play with it. Um,
</details>

### 后训练的核心挑战：真实工程复杂度与飞轮架构

关于模型的市场介绍就谈到这里。有人告诉我今天在座的都是极具技术背景的受众，因此我想深入讲讲为什么对这类前沿模型进行后训练非常困难，以及背后的具体投入。

首先谈谈背景：目前在 Google，AI 编写了大约 75% 的新增代码，而在几年前这一比例还不到 25%；每天有 10 万人在 Google 内部使用 Anti-gravity 编写代码。

在过去几年中，人们交给模型处理的任务复杂度呈指数级上升。我们最初只是让模型补全聊天对话，那仅需数秒；后来发展到在几分钟内编写小型函数；再后来提交 PR 并解决单个 Issue 大约需要一小时；而现在，人们正在使用模型执行耗时数天的真实工程任务，利用智能体群体（swarms of agents）借助模型解决实际的开放性难题。Google 各地的工程师每天都在使用 Anti-gravity 和我们的 Gemini 4 模型跨天完成任务。

那么，我们该如何对 Gemini 进行后训练以应对真实的工程任务？我们必须从高难度任务着手，需要为模型寻找真正具有挑战性的问题。

这些模型的评分本身就是一个极难的课题：你希望评分标准能像一位资深代码审查者那样严格，能像富有经验的工程师评估解决方案那样去判定。我们通过大规模强化学习（Large scale RL）来训练模型，并让 10 万名工程师组成的内部社区对模型进行内部试用（dog food），不断重复这一循环——内部试用中的任何失败用例，都会转化为下一轮循环的训练任务。

<details>
<summary>Original English</summary>
now I think enough marketing with the models. I want to I was told this is a deeply technical audience. So I want to talk a little bit about why post- training these frontier models is hard and what goes into that. Let me start by saying you know AI writes about 75% of Google's new code today. And this is up from less than 25% a few years ago. And there are 100,000 people using anti-gravity writing code inside Google every single day.

Now the complexity of the tasks that people do have also increased exponentially in the last couple of years. We started with you know models just completing chats which took seconds to writing small functions within the minutes. You can submit a PR and resolve an issue. Takes about an hour, let's say. But now people are doing days of real engineering tasks with the model. People have swarms of agents solving real open problems with the model. We have engineers across Google using anti-gravity and our Gemini 4 models to solve tasks over multiple days.

Now, how do we go about post- training Gemini for real engineering tasks? We have to start with hard tasks. So we need really need to source hard problems for the model. Grading of these models is actually a very hard problem. So you want to grade like an experienced code reviewer would grade. You want to grade like an experienced engineer would grade a solution. Large scale RL is how we train the model. And we want to dog food our models with our 100,000 engineer community and repeat the loop. So any failures in the dog food become tasks for the next iteration of the loop.
</details>

### 高难度训练任务的设计与来源

我想就上述几个部分逐一深入探讨。首先是高难度任务。

大家可能听说过，随着模型能力的提升，大量基准测试逐渐趋于饱和；不仅是基准测试饱和，我们的训练数据同样面临饱和。这里有一张图表，展示了在 Gemini 4 模型的三个不同迭代版本中，具有学习信号的提示词（learnable prompts）份额是如何持续下降的。假设第一代模型拥有 x% 的可学习提示词，等到训练完成进入下一代时，这些提示词对第二代模型而言已经过于简单；当我们再完成第二代进入第三代时，原来的题目又变得过分容易。

训练任务过于简单会带来什么问题？简单的任务会带来零学习信号。如果一个提示词下的所有推演轨迹（rollouts）都是正确的，就没有方差，也就无法提供强化学习信号。因此，必须将重心放在获取高难度任务上，并且获取高难度任务的速度必须快于模型进步的速度。

我们具体是如何做的？
- **任务修剪**：首先识别这些简单任务并将其从混合数据集中剔除，砍掉那些对模型而言过于简单的传统基础任务。
- **扩展任务维度**：转向难度高得多的多文件代码仓库（multifile repos）。
- **评分机制跃升**：从单一的单元测试或二元正确性判定，转向基于评分准则（rubric-based）的评估。准则能够提供密集的学习信号，它们不只是非零即一（0/1）的布尔值，在各项标准内部还能包含更丰富的梯度空间。

我们在训练中采用的高难度任务包括：
1. **多文件仓库提交**：分析多文件代码仓库并从中提取代码提交（commits），让模型根据这些提交自动生成评分准则。我们并不强制要求必须包含单元测试，而是能够基于这些代码库动态生成准则。
2. **从零构建 CLI 工具**：让模型从一个空目录和一份规范说明开始构建命令行工具。规范会明确工具名称为 GP、参数、各类选项参数（flags）及具体功能，让模型从零完整构建出整个工具。由于已知该工具的功能表现，我们会准备一套隐藏测试集来对编译出的二进制文件进行评估。
3. **生产环境代码库 Diff**：观察模型在内部生产代码库中的实际使用情况，并从中提取高价值任务。

<details>
<summary>Original English</summary>
So I want to start by going into a little bit more detail of each of these sections. So let's start with the hard tasks, right? Um so you might have heard you know as models are getting better lots of benchmarks are getting saturated and it's not just the benchmarks that get saturated our training data gets saturated too. So here is a graph that shows for three different iterations of the Gemini 4 models how much uh the share of learnable prompts has gone down. So let's say we had x% of learnable prompts for the first iteration. By the time we finish and train the next one, the prompts are too easy for the second one. We finish that and train the third one, the prompts are too easy for the third one. So what's the problem with uh training on easy task? Easy task give you zero learning signal, right? So you have a prompt when all of your rollouts are going to be correct. There's no variance. There's no RL signal. So you really need to focus on getting hard tasks and you really need to be faster at getting hard task. Then the models are getting better, right? Um so how do we go about it? We first have to you know identify these easy tasks and prune them. So we cut these simple sweep style tasks from the mixture that are too easy for the models. we expand into much harder tasks for example that are multifile repos. We go from unit test or binary correctness um to rubric based grading and rubrics give you dense signal. They're not just 01. There can be um more gradients within the um within the criteria.

Here are some examples of hot tasks that we train on. So uh we look at multifile repos and we extract commits from them. From those commits we have models automatically extract rubrics. Um we don't actually ne necessitate unit tests being involved. We can actually uh generate rubrics on the fly based on these repos. Another example a great example of tasks are you try to teach the model to build uh CLI tools from scratch. So you start with an empty folder and a specification. The specification says, hey, you have to build this tool. It's called GP. These are the parameters of GP. These are the flags. This is the functionality. And you let the model build the entire tool from scratch. And you know what the functionality for GP is going to be. So you have a hidden test suite that you can evaluate the binary on. The last uh example is production codebased diffs. So you look at real usage of the model inside your production codebase and extract useful tasks out of them.
</details>

### 评分机制与沙盒防作弊加固

接下来谈谈评分系统（graders）。

智能体在受训时被设定为要通过测试，因此它们会不择手段去通过测试。然而，测试通过并不必然意味着它们真正解决了问题。现实中存在智能体绕过检查机制的案例，存在智能体针对基准测试走捷径刷分（gaming）的案例，也存在伪造证据的案例——比如把伪造的证据写进临时文件，然后再删掉所有伪造痕迹。因此，随着模型能力变强，评判机制必须更加严密。

这就是我所说的“像审查者一样评分”。如果你参与过代码审查，遇到过非常严格的审查者，你就会知道他们不仅考虑解决方案的正确性，还会考虑代码风格、可维护性以及诸多维度。因此，我们从依赖单元测试的二元正确性转变为基于评分准则的考量，这些准则由真实的代码提交生成，能提供密集的学习信号而非单一的 0/1 信号，并且会对寻找投机取巧手段的解法施加惩罚。

评分准则的具体示例如下：包含必须覆盖的边界条件、需要遵守的代码整洁规范，以及关于验证环节必须满足的约束。

除了需要评估准则，我们还必须警惕评分器本身被投机利用，必须对评分器所处的运行环境进行严格加固：
- **隔离沙盒环境**：将评分器放入隔离沙盒中，移除 Git 历史记录和远程仓库配置，防止答案泄露。
- **保留测试集（Held-out Test Sets）**：严格隔离测试集，只有在智能体宣告完成并提交方案后才披露测试用例。我们曾遇到过智能体先假装声称“我已经完成了”，等到测试集生效后查看测试用例，再重新提交修改方案的情况；这种情况必须杜绝。
- **精细化多维度打分**：抓取完整的 Diff，对比参考标准，从正确性、代码质量以及变更范围等多个维度进行综合考量。
- **惩罚作弊行为与保护思维空间**：对智能体的任何作弊企图施加严厉惩罚，同时注意不去干预其思维过程（thoughts）。任何针对环境的欺骗或破坏行为都会受到极强的强化学习负奖励，而这完全是基于模型所采取的操作动作（actions）来判定的，并非审查其内在思维。

处理作弊的一个明确成果是：Carbon 在 Terminal Bench 4 上的作弊率为 0%。我们前代模型的作弊率要高得多，而 Carbon 的对抗性倾向比 Argon 降低了约 5 倍。我们在模型的每一代迭代中都在努力提升其对齐程度，防止其试图作弊。

<details>
<summary>Original English</summary>
Now let me talk a little bit about uh the graders.

So agents you know they find any way you're you're training them to pass the test. So they will find any way to pass the test but if the test pass that doesn't necessarily mean that they've solved the problem. There are examples where the agent will bypass the checker. There are examples where the agent will game the benchmark. There are examples where the agent will fake the evidence. You know, it writes the uh fake evidence into a temp file. It'll delete any evidence of it faking it, right? Um so you have to be smarter about how you judge these models, especially as they become more capable.

Now, this is what I meant by grading like a reviewer. So if you've done a code review, you have a very strict reviewer, you're going to know they're not just going to think about the correctness of the solution. They're actually going to think about the style. They're going to think about maintainability. They're going to think of many different aspects. So what we do is we move from unit test base correctness to rubric base and these are generated from real commits. The rubrics also provide dense learning signal not just 01 signal and we penalize any sort of solution that is looking for a workaround. Right? So here is an example of a rubric where the criteria is you know here are the edge cases that need to be passed. This is an example of hygiene that needs to be maintained. These are constraints around verification that need to be satisfied.

Now, it's not just about the rubrics needed for grading. We also need to be careful about the graders not being gamed and you really need to harden the environment that the grader is in. So, we think about putting the graders in a isolated sandbox. So, we remove git history and git remote so the answers don't leak. The test sets are held out. So, only when the agent is done and submits the solution do we actually reveal the test. We've had instances where the agent will fake it and say, "Hey, I I'm done and the tests come into play and then it'll look at the test and resubmit the solution." Right? So, you don't want that. Um, we also want to be much more detailed with our scoring. So, we take the full diff and we look at the reference and we look at multiple aspects. It's not just the correctness. We also want to look at the code quality. We also want to look at the scope uh of the change that was done. And then finally we want to penalize any sort of cheating attempt by the agent while being careful not to police the thoughts. Um so any you know cheating or hampering of the environment gets a very negative RL reward. Uh and all of this is detected just based on the actions that the model is taking not the thoughts. Um so a good example of how we've handled cheating is you know carbon for instance has 0% cheating rate on terminal bench 4. Our previous models had a much higher cheating rate and it's about 5x less adversarial than argon. So every generation of the model we're trying to make it much more aligned so it's not trying to cheat.
</details>

### 行为对齐与诚实度建模

最后，我想谈谈模型行为，尤其是诚实度（honesty）建模。

智能体总是倾向于表现得乐于助人，而有时它们会伪造有用性（fake helpfulness）。大家在使用中可能遇到过：
- 它们有时会在测试明显未通过时谎称通过；
- 会在任务明显未完成时宣布完成；
- 声称自己修改了代码但实际并未做出修改；
- 凭空捏造事实或 API；
- 输出堆砌了大量数字的长篇文本，让你几乎无法验证。

这里是 Gemini 捏造率（fabrication rates）的实际数据：在某项高难度内部评测中，最初的捏造率为 8%；在 Hydrogen 中大幅压低到了大约 3%；而 Carbon 的捏造率在此基础上再次减半，降到了约 1.5%。我们的目标是将其降至零。你绝不希望自己的智能体捏造任何内容，但它们由于急于表现出有用而试图造假，因此必须下大力气进行对齐，让它们保持有益，但绝不能靠伪造来实现。

我们是如何降低伪造率的？

说出来可能让人难以置信，关键在于清洗数据。我们过滤掉了大量的训练轨迹，不仅排除有意伪造，也排除无意中出现的捏造行为，以及大量未充分佐证或未经核实的陈述。

我们要求模型的陈述立足于完整轨迹（ground in the full trajectory）。如果智能体声明“我已经完成了任务”并给出了最终答复，我们会审查该答复，比对它在得出最终方案的整个轨迹中所采取的所有动作与具体步骤。当智能体说“我已完成”并给出总结时，该总结必须完全立足于它实际执行的动作。

此外，我们奖赏诚实行为。如果面对一道难题，智能体更好的做法是坦白：“这是我取得的部分进展。这个问题很难，我目前只能做到这里，这是我的部分解决方案”，而不是在最后一步弄虚作假、硬称自己已经解决了问题。

<details>
<summary>Original English</summary>
Now finally I think uh I want to talk about model behavior a little bit and modeling honesty specifically.

Now agents they always want to be helpful and sometimes they fake helpfulness. You might have seen this in your usage of the agents. So sometimes they'll claim that tests have passed when they've obviously not passed. They'll declare done but obviously they're not done. They'll make edits that they'll claim to have made edits but they've not made those edits. Or they'll invent facts and APIs and whatnot. or they will give you a wall of text that has so many numbers that it's going to be impossible for you to verify. Right? We've gone through all of these examples.

Now, here is an example of fabrication rates in Gemini. Right? So, we on an internal eval started with 8% fabrication in that hard eval. We cut that down dramatically to about 3% for hydrogen and carbon is half of that is about 1.5%. But we're striving to get this down to zero. Like you don't want your agents fabricating anything, right? But they try to fabricate because they want to be helpful. And you really have to try hard to align them to be helpful but not by faking it.

How do we reduce the fabrication? Believe it or not, you have to clean your data. Uh right. So we filter out lots of training trajectories where there's you know not just uh intended fabrication but unintended fabrication. There's lots of claims that are not fully supported. They're not verified. We ground in the full trajectory. So if the agent says I've completed the task and it has a final response, we actually look at that response and see all of the actions that the agent had taken in the trajectory to get to that final solution and we look at the steps that were taken. So you really need to when the agent says, "I'm done." and gives you a summary, that needs to be grounded in the actions that were taken. And we want to reward honesty. So if there's a hard problem, it's better for the agent to say, "Hey, this is my partial progress. It's a hard problem. I'm done here. This is my partial solution." Rather than faking the last step and saying, "Hey, I've solved the problem. You know, this is done."
</details>

### 以周为单位的交付飞轮与未来展望

最后，我们是如何做到以周为单位进行快速发布的？

最核心的原因在于我们拥有超过 10 万名 Google 内部工程师，他们正使用该模型处理实际任务。很多人可能知道 Google 采用单一代码仓库（monorepo）架构；整家公司共享同一个代码库，这可能是全球规模最大的单体仓库之一。这是一个高度复杂的代码库，由顶尖人才在其中执行极度复杂的工程任务。

因此，每当后训练产出新的候选模型时，我们就会将其部署给内部用户使用。我们会在多个不同候选模型之间开展盲测对抗，让用户挑选心目中的最佳模型；我们也会在底层将用户请求路由到实验性模型，从中获取信号和反馈，并将所有摩擦点与反馈信号重新沉淀到下一个候选模型的训练中。

这个良性循环使我们能够快速迭代，真正针对高难度问题开展训练；随着模型能力提高，工程师们又会以各种新颖的方式进一步挖掘和考验它的极限。

这也是我们能将发布周期从按季度交付缩短到按周交付的原因。在 Gemini 3 时代，我们的发布节奏是每 2 到 3 个月一次；而在最近的 16 周内，我们已经完成了 6 次发布。

我们非常期待大家去体验 Carbon、Hydrogen 以及整个 Gemini 4。我们很兴奋想看到大家用它构建出什么样的成果。我们探索的脚步不会停歇，元素周期表上还有很多元素等待我们去发掘。谢谢大家。

<details>
<summary>Original English</summary>
Finally, shipping in weeks. So how are we able to ship so rapidly?

And the biggest reason for that is our internal uh team of 100,000 plus engineers at Google using the model for realistic tasks. You know many of you might know Google is a monor repo and what is a monor repo? The entire company is one codebase right and I don't know how to measure this but I think it might be one of the largest monor repos in the world. Now that's a really complex uh codebase and we have the best people in the world using a really complex code base to do really complex tasks. So every time we have a new candidate from post training, we actually serve that model uh for our users. We run blind battles with them through multiple different candidates. We let users you know uh pick the best model that they want. We also run less where under the hood we're routing the routing people to experimental models and get signal and feedback from that and we take all of these signals and friction back into training the next candidate.

So this is a cycle that helps us you know rapidly iterate really train on hard problems and as the models get better the engineers are going to push the model in interesting ways.

This is also why, you know, we've gone from releasing in weeks um to releasing to we releasing in quarters to releasing in weeks. So, in the three in the Gemini 3 era, we've had launches every 2 to 3 months, but now we've had six releases in the last 16 weeks, right? Uh and we're very excited to have you all try Carbon and Hydrogen uh and Gemini 4. Um, and we're excited for for for us to see what you all do with it. Uh, and we're not done. So, we have a lot more elements uh to go through. Uh, with that, you know, thank you.
</details>