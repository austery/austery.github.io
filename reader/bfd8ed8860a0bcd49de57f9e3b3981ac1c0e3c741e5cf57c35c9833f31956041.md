---
author: AI Engineer
date: '2026-07-31'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=k35LeKZEhiE
speaker: AI Engineer
tags:
  - post-training
  - reinforcement-learning
  - agent-harness
  - reward-hacking
  - self-distillation
title: 在岗学习：后训练的未来
summary: 演讲者分享后训练前沿工作：从单轮问答、合成环境，到自带 harness 训练，并展望可跨交互自我改进的智能体。讲到环境保真度、奖励作弊、不可重放与离线数据等挑战，以及自蒸馏、自动化数据管线和定性反馈摄取等研究方向。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
### 开场：让智能体在工作中学习新技能
谢谢你，Jack。非常感谢有机会在这里发言。

今天我将分享我们在后训练方面的一些前沿工作，以及我们设想的未来：智能体可以在工作中学习新技能。

<details>
<summary>Original English</summary>
Yeah, thank you, Jack. Um, really grateful for the opportunity to speak here.

Today, I'm going to be sharing some of our frontier work on post training and how we envision a future where agents can learn new skills on the job.
</details>

### 背景与后训练的几个层级
过去大约一年里，我们看到智能体发展出了很强的推理能力，并学会使用智能体 harness，去解决越来越长程的任务，这些任务涉及多轮交互和工具调用，环境状态也很复杂。

我们看到，对能够即插即用地部署到企业现有使用方式中的智能体，需求越来越大。比如，如果企业已经有某种调用智能体完成任务的方法，他们会希望能改为训练一个定制模型来完成这个任务。

这就需要看待后训练的新方式，使你能够适应任何 harness，包括那些你不一定能拿到源代码的 harness。

所以我想谈谈后训练的几个不同层级，每一层都建立在上一层之上。

我们对此的一种思考方式，是把它与人类学习做类比的框架：你先学简单的任务，然后可以把理解逐步叠加到越来越复杂的任务上。

过去一年里，我们在简单的单轮问答任务和一些较长程的合成环境任务上，可以说已经掌握，或者说积累了大量练习。

但我们越来越多地看到的是，我们希望能适应定制的 harness，并直接在这些 harness 上训练。我们把这类情形有点像看作实习：你希望模型完成一项特定任务，但你不一定确切知道任务会如何展开，因为你并不拥有这个 harness。

最后，我想分享我们对定制模型训练领域未来的一些设想：我们认为将会出现这样一种智能体“公民”，你只需部署一次，它们就能适应许多不同类型的分布外任务，并从自己的交互中学习。

<details>
<summary>Original English</summary>
So, over the last year or so, we've seen agents develop really strong reasoning skills. And they've learned to use, uh, agentic harnesses to solve longer and longer horizon tasks, which involve many turns and tool calls on complicated environment states.

We're seeing an increasing, uh, demand for agents that can just be deployed in a plug-and-play way into how enterprises use the agents, um, so, for instance, if they already have some method of calling the agent to do a task, to do a task, they would want to be able to train a custom model to do that task instead.

And that requires new ways of looking at post training that allow you to, um, adapt to any harness, including ones that you don't necessarily have access to the source code of.

So, I wanted to talk about a few different levels of post training, where each one builds on top of the last.

One way that we kind of think of this, uh, is a framework comparing it to how humans do learning, where you learn simple tasks first, and you can sort of compound your understanding to more and more complicated tasks.

So, over the last year, we've sort of, I would say, mastered or gotten a lot of reps with these simple single-turn Q&A tasks and um some longer horizon synthetic environment tasks.

But, what we're increasingly seeing is we want to be able to adapt to custom harnesses and be able to train directly on those instead. And we kind of think of those kind of like internships where you want to the model to do a specific task, but you don't necessarily know how exactly the task will play out because you don't own the harness.

And then finally, I would want to share some visions we have for the future of the custom model training space, where we think that there will be these kind of agentic citizens, which you can just deploy once, and they'll be able to adapt to many different types of out of distribution tasks and learn from their interactions.
</details>

### 简单问答任务的训练设置
首先，我想谈谈这些简单问答任务的训练设置。

我们的设置大致是这样：有一个编排器（orchestrator），负责驱动 rollout。

编排器持有一个任务包，目前你可以把它看作只是一个简单的提示和答案，比如一道数学题和对应的数值答案。

编排器把这个提示发给模型，然后拿回一个答案。接着它把答案发给评分器进行评分。这一切完成后，我们想基于这次交互，或者一批交互，来改进模型。我们的做法是通过训练引擎：它接收已评分的对话，产生一次权重更新。

这次权重更新随后同步到一些推理引擎。推理引擎更新完毕后，我们就可以重新开始整个过程：编排器有新的问题要发送给模型的 completion 端点，然后你就能得到更多对话，对它们评分，再次训练。

这里要注意的关键点是，改进模型你唯一需要的，就是某种格式的已评分对话；有了这些，训练引擎就可以计算权重更新来改进模型。

这里重要的是，对话采用非常特定的格式，因为我们把一切都限制在训练栈内部。所以在这种简单的问答设置里，没有任何东西存在于训练栈之外。你基本上拥有如何运行 rollout 以及一切如何格式化的代码，所以这是一个非常受控的环境。

<details>
<summary>Original English</summary>
So first, I just want to talk about the training setup for these simple Q&A tasks.

We have something that looks like this, where you have an orchestrator, and the orchestrator is in charge of driving the rollouts.

The orchestrator holds a task back, which you can think of for now is just a simple prompt and answer. So, something like a math question and a corresponding numerical answer.

Um the orchestrator will send this prompt to a model and then get an answer back.

Then it will send the answer to a grader and have it be graded. So, once all of this is done, we want to improve our model based on that interaction or maybe like a batch of interactions. And the way we do that is through a training engine, which takes in the graded chats and produces a weight update.

That weight update is then synced to some inference engines. And once those inference engines are updated, then we can start this entire process over again, where the orchestrator will have like new problems to um send to the model completion endpoint, and then you'll be able to get more chats, grade them, and train again.

The key thing to note here is that the only thing you need for improving your model is the graded chats in some format, and once you have those, the training engine can compute weight updates to improve your model.

Uh what's important here is that the chats are in a very specific format because we're sort of constraining everything to be inside of our training stack. So, in this simple setup for Q&A, you don't have anything living outside of the training stack. You You basically have the code of how to run the rollout and how everything is formatted, so it's like in a very controlled environment.
</details>

### 合成环境与环境保真度问题
然而，这有一定局限，因为这样我们只能做单轮任务。如果我们想做越来越长程的任务，并想把更高阶的技能构建进模型，就还需要提高环境的复杂度。

所以对于合成环境，我们有非常相似的设置，但把大量环境状态转移到训练栈之外。你仍然有之前同样的编排器，但任务包可能更复杂一些，环境状态存在于训练栈之外。于是任务包现在可能包含工具调用规格，或者环境的初始状态，比如一个文件系统。

编排器现在负责依次运行许多轮：也许先询问模型想如何回应，然后如果模型想调用某些工具，它就会调用沙箱去真正修改或读取环境状态，再把结果返回给模型。

这一切结束后，你会得到一条完整的任务轨迹，然后这条轨迹被发送给评分器评分。

与之前非常相似，你可以拿到已评分的对话，再用它们来做权重更新。

这里要强调的主要一点是，这种编排器加沙箱的设置是可重放的，基本上就是说，对任何特定提示，你总可以回滚到初始状态并重新运行。你可以并行做，也可以串行做。

这之所以重要，是因为我们今天用于强化学习的主要方法是 GRPO，它涉及对同一个提示比较许多 rollout，然后相对地比较哪一个比另一个更好。训练引擎随后会对模型做出修改，提高更成功轨迹的权重，降低不太成功轨迹的权重。

我们在这种设置中面临的一些挑战是：环境是你想用来复制现实的东西，这样训练完成后，你看到的改进才能在这些模型部署到生产环境时真正转化过去。

主要的问题有两个名字，但其实是同一个问题：环境保真度和奖励作弊（reward hacking）。

本质上，智能体暴露在一个环境中，你环境的任何怪癖，最终都可能成为智能体学到的模型的一部分。我们见过一些例子：过去有一次训练运行中，我们遇到一些网络问题，导致环境中的工具调用大约有 10% 的时间失败。在这种情况下，我们实际看到模型开始输出越来越短的回复。这让我们很意外，因为在我们的奖励函数里，其实并没有任何长度惩罚。所以我们当时无法真正判断这为什么会发生。

但真正发生的事情是：如果你把模型想成一个人沿着人行道走，工具调用失败就像人行道上的坑洞。因为坑洞太多，模型不想走太久，这很合理，因为它可能掉进坑里，然后这次 rollout 得到零奖励。

反过来，你的模型也可能随着时间推移，学会输出越来越多的胡言乱语，这取决于你的环境是什么样。在另一个案例中，我们有一次训练运行设置了沙箱超时，以免它们无限运行，而且我们通常会把超时的 rollout 从训练中过滤掉。

我们看到的一件事是：如果你的工具调用耗时很长，当模型觉得问题真的很难时，它实际上会被激励去滥用工具调用，在短时间内连续调用很多次，试图让沙箱超时，这样它就避免得到零奖励，只是让这次 rollout 被丢弃。

所以，随着我们扩展到越来越复杂的任务，复制这些环境的任务变得越来越困难，因为要完美模拟现实非常非常难，而你犯的任何错误，即使并非有意，最终都会在模型中诱发这些微妙的不良行为。

<details>
<summary>Original English</summary>
However, this is kind of limited because we can only kind of do single-turn tasks in this way. If we want to do longer and long-horizon tasks, and we want to build like higher-order skills into our models, we need to also increase the complexity of our environment. So, with synthetic environments, we have a very similar setup, but we offload a lot of the environment state um outside of the training stack. So, you still have the same orchestrator um from before, but um the task back is maybe a little bit more complicated, and the environment state is uh living outside of the training stack. So, the task back might now include things like tool cost specs or like maybe an initial state for your environment, like a file system.

And the orchestrator is now in charge of running many turns in a in series, where maybe first they ask the model for how it wants to respond, and then if the model wants to call some tools, it'll then call the sandbox to actually like modify the environment state or read the environment state, and then return those results back to the model.

After all that is said and done, you get a full task trace out of this, um, and that task trace is then sent to a grader for grading.

And very similar to what we had before, you'll be able to take the graded chats, you'll be able to then use them to do a weight update.

The main thing to highlight here is that this orchestrator and sandbox setup is replayable, which is basically just saying that for any specific prompt, you can always like roll back to the initial state and like rerun it. Um, you can do that in parallel or you can do that in series. But, the reason that's important is because the main sort of method that we use for reinforcement learning today is GRPO, and that involves comparing many rollouts for the same prompt, and then comparing like relatively which one is better than the other. And the training engine will then up like make an edit to the model to upweight the trajectories that were more successful, and then downweight the ones that were less successful.

So, some challenges that we face in this setup is that the environment is something that you want to basically, uh, use to replicate reality, so that after you're done training, like the improvements that you've seen actually translate to when you deploy these models into production. And the main sort of problem is like has kind of two names, which are both the same problem, environment fidelity and reward hacking.

Essentially, the agent is exposed to an environment and sort of any, uh, any quirks of your environment will end up being something that your agent may like learn a model of. So, we have some examples that we've seen where in a trading run in the past, we had some like networking issues causing our environment to have tool calls that failed maybe around 10% of the time. If that is the case, then we actually saw that the model would then start outputting shorter and shorter responses. Now, this was really surprising to us because in our reward function, we actually didn't have any length penalty. So, like we we couldn't really tell why this was happening, but really what's going on here is if you think about maybe the model is like a human like walking along a sidewalk and like the tool call failures are like potholes in the sidewalk, like it makes a lot of sense that because there's so many potholes, the model doesn't want to run for that long uh because it might fall in a pothole and then get a zero reward for the rollout.

Um and then conversely, um it's also possible that your model just learns to like output more and more gibberish over time depending on like what your environment looks like. So, in a different case, we had a training run where we um have sandbox timeouts uh just so that they don't run forever, and we usually like filter out the rollouts that timed out from being trained on.

One thing we saw was that if your tool calls take a long time, then if the model feels like the problem is really hard, it will actually just be incentivized to like abuse the tool calls and just like call a lot of them in quick succession and try to time out the sandbox so it avoids getting a reward of zero. It just gets the rollout dropped.

So, as we scale to like more and more complicated tasks, the the task of like replicating these environments becomes increasingly difficult because it's very, very difficult to like perfectly simulate reality and sort of any mistake that you make, even if it's not intentional, will end up inducing these like subtle undesirable behaviors in your model.
</details>

### 自带 harness 与由此产生的挑战
这就引出了我们的下一个主题：自带 harness（bring your own harness）。我们基本上是在问：如果智能体学到的是确切的环境分布，那我们为什么不直接用它来训练？直接用真实环境，你就不再需要复制任何东西，可以直接按它在生产中将被使用的方式来使用。

这解决了很多问题，听起来非常不错。

架构大致是这样：我们现在几乎把所有东西都放在训练栈之外。我们剩下的唯一东西是模型 completion 端点，以及某种记录进出模型的请求和响应的方式。

其他一切都存在于训练栈之外，可以以现有企业或客户可能在使用的任何方式运行。所以这些会是现有的企业 harness。

这样做的好处在于，我们可以在客户所处的位置与他们对接。比如，如果他们已经在以某种方式使用模型，我们可以直接把我们的训练方法接入进去，然后帮助他们改进模型，使其恰好适配他们使用它的方式。

所以，所有编排循环和逻辑现在都将位于训练栈之外。

这听起来很好，但这里的挑战在于数据：当你把它部署到生产环境，对 rollout 如何展开的控制越来越少，你可供学习的信号也越来越少，因为数据不是熟悉的格式。

这个话题在英伟达的一项相关工作中被谈到。那是大约一个月前的一篇论文，他们介绍了 Polar，本质上是一种思考方式：从一种由你负责微观管理 rollout 每个方面的 harness，也就是我们之前讨论的那种，过渡到某种只是在黑盒 harness 上“监听”的方法，你不再确切知道其中的逻辑是什么。

我们在这种场景下面临的一些挑战是不可重放性，以及离线或 off-policy 数据。我认为这两者描述的是同一个问题：因为我们把太多逻辑移到了训练栈之外，所以我们没有办法强制执行不变量，或我们想要的那类数据结构。我们必须在训练方式上更灵活，因此训练模型就变得更困难，并且可能会产生一次更新。

举个例子，对于传统方法 GRPO，你会希望对你的任务并行跑许多 rollout，而这可能不再可行。假设有一个客服聊天，你有一条聊天记录，记录了其中一次聊天是怎么进行的，你并没有真正的办法回头去想：“哦，如果我换另一种方式说或回应，用户会不会更满意？”没有办法再次得到用户的回应。

但我们是乐观的，因为我们认为人类可以做这种学习，所以应该有可能构想出某种同样适用于模型的方法。比如，如果一个人在客服聊天中，他们能以某种方式根据客户的反应理解自己说的话是错的还是好的，然后把改进内化，用于未来。

<details>
<summary>Original English</summary>
So, that brings us to our next topic of bring your own harness, where we're basically asking like if the agent learns the exact environment distribution, why don't we just use that for our training? Like just directly the real environment, you will no longer need to uh replicate anything. You can just like use exactly how it's going to be used in production.

This solves a lot of problems and sounds really good.

The architecture looks something like this where we now have almost everything outside of our training stack. The only thing we have left is the model completion endpoint and some way to uh record the requests and responses that go in and out of the model.

Everything else kind of lives outside of the training stack and can be run in whatever fashion uh that like an existing enterprise or like customer might be using. So, these would be like existing enterprise harnesses and essentially the reason this is nice is because we can meet customers where they're at. Like, if they're already using the model in a certain way, we can just take our like training methodology and just like plug it right in and then we can help them improve the model for like exactly the way that they're using it.

So, all the orchestration loops and logic will now live outside of the training stack.

Now, this sounds really good, but um This sounds really good, but the challenge here is in The challenge here is in the like data where I as you're deploying this into uh production and you have less and less control over how the rollouts uh play out, you also have like less signal to learn from because the data is not in like a familiar format.

And this topic is touched on in a related work by Nvidia. Uh this is like a paper from around a month ago where they introduce uh Polar, which is essentially a way to think about transitioning from a harness where you are kind of in charge of micro managing every aspect of the rollouts, kind of like what we were previously talking about. And transitioning to some method of just uh listening in on a black box harness, and you would no longer know exactly what the logic in here is.

So, some challenges is that some challenges we face in this setting are non-re-playability and offline or off-policy data. I think both of these are describing the same issue, which is just that because we've moved so much of the logic outside of our training stock, we just don't have any way of like enforcing invariants or like data structures that we like. We have to be more flexible about the way we do training, and because of that, it just becomes harder to train your model and it may create an update. So, an example would be for GRPO, which is like the traditional method, you would want to have many rollouts in parallel for your task, and that may not be possible anymore. If you think about um suppose like a customer chat customer support chat, and you have a record of how one of your chats went, there's not really a way that you could then go back and think, "Oh, if I like said or if I responded in this other way, like would the user have been happier?" Like there's no way to then get the user's response again.

But, we're optimistic because like we think that humans can do this kind of learning, and so it should be possible to like formulate some kind of method that would work for models as well. Like, if a human was in a customer support chat, they could understand somehow that like based on the customer's reaction, like what they said was wrong or what they said was good, and then be able to like internalize improvements uh for for the future.
</details>

### 前沿研究方向
所以，我想谈谈我们在解决这个问题上的一些前沿研究方向。主要有三个主题：自蒸馏、自动化数据管线和定性反馈摄取。

自蒸馏是一项相当新的技术，我会说它的适用范围相对还比较窄。我们已经在让模型产生特定的新行为方面看到了成功，但能把它推广到多一般，仍然是一个开放的研究问题。

自动化数据管线的想法是：如果你拿一大批轨迹，就能自动标记不良行为或失败模式，然后自动整理出一批好的训练数据，发给模型帮助它改进。目前这还是相当手动的，或者说是有人参与其中：我们自己翻看轨迹，手动寻找这些失败模式，然后描述如何改进模型，再自己筛选整理这些数据集。

最后，我认为一个有趣的方向是定性反馈摄取。当你转向这些生产环境时，有时你拿不到明确的二元评分或数值评分。通常你收到的是这样的信息：“嘿，对于这次聊天，客户给了这样一条反馈。”如果我们能找到一种方法，基于这类信息更新模型，那也会极其有帮助。事实上，自蒸馏就是我们在探索如何做到这一点的一种方式，但这仍然是一个相当开放的问题。

<details>
<summary>Original English</summary>
So, I want to talk about some of the frontier research directions we have um towards like solving this problem. There's kind of three main topics, which are self-distillation, automated data pipelines, and qualitative feedback ingestion. Self-distillation is a pretty new technique, which is still um, I would say relatively like narrowly scoped. So, we've seen successes in inducing like specific new behaviors with models, but it's it's still an open uh, research question of like how general can we push it?

Automated data pipelines is an idea which maybe if you take like a big batch of traces, um, you would be able to like automatically like flag undesirable behaviors or failure modes, and then be able to like put together a like nice batch of training data, um, automatically, and then send that to the model and help it improve.

Currently, this is like pretty manual or like human in the loop, where like we go through traces ourselves, and we're like looking for looking for these failure modes manually, and then like describing how we can improve the model, and then um, looking curating those data sets ourselves. And then finally, I I think an interesting direction is qualitative feedback ingestion. So, as you move to these like production settings, sometimes you don't have access to like a clear-cut binary grade or like a numerical grade. Um, often times, what you receive back is like, "Hey, for this chat, the customer had this like piece of feedback." Um, if we can find a way to update our models based on that information, uh, that would also be prove extremely helpful. Um, and in fact, like self-distillation is one way in which we're exploring how we can do that, but it's like a pretty um, it's still a pretty open question.
</details>

### 未来愿景：自我改进的模型
最后，我想稍微分享一下对后训练（原文为 post-editing）未来可能样子的愿景，如果我们把这种演进外推并推到尽头的话。

我认为最终我们可能会达到这样一种局面：我们不再局限于思考某个具体任务上如何改进模型，而是可以把模型看作一个单一的部署，它可以在许多许多不同的场景中交互。你所思考的任务，也许就是在一切方面改进自己这个任务。

这个模型可能被用于各种不同的任务，也许还跨越不同的用户。并且它能够进行某种反思或内省，比如：“好，对于这类交互，我是这样自我评估并认为自己表现如何的；而对于另一类交互，我认为自己表现如何如何。”然后能够自动利用这些交互计算权重更新并改进。

所以，回到智能体会学会你环境中每个角落、确切的环境分布这一点：如果环境就是智能体曾有的每一次交互呢？再加上，我们有某种方式让模型能够评估自己。

基本上，我们看到的一个问题，或者说抱歉，一个挑战是：如果你一次只专注于改进一个任务，或一次只标记一种失败模式，你就像是在打地鼠，一旦冒出新的东西，你就得匆忙创建新的数据或新的环境，以此来改进模型。

有了这种自我改进的系统，它理解来自环境的每一次交互，你就能在某种程度上绕过这个问题，不再需要为此担心。

<details>
<summary>Original English</summary>
And then finally, I wanted to share a little bit about a vision for what the future of post-editing might look like if we sort of extrapolate out and take this sort of progression to its end.

I think eventually we might reach a setting where instead of just limiting ourselves to thinking about a specific task that we can improve the model on, we can actually just think of the model as this one deployment that can interact in many, many different settings. And like the task that you think about might just be the task of improving yourself on everything.

Um and this model may be used for all sorts of different tasks, maybe across different users as well.

And be able to sort of do some kind of reflection or introspection on like okay, for this sort of type of interaction, here's how I like self-evaluate and think that I'm doing. And then for this other type of interaction, um here's how I think I'm doing. And then being able to automatically take these interactions and compute weight updates from them and improve.

And so, yeah, going back to the point that the agent learns every nook and cranny in your environment, um the exact environmental distribution, what if like the environment was just like every interaction that the agent ever has? And then in addition, we had some way that the model could evaluate itself.

Um basically one one like question that we've Or sorry, one challenge that we've seen is like if you're only focusing on like what improving on one task at a time or like flagging one failure mode at a time, you're kind of playing a game of Whac-A-Mole where as soon as a new thing pops up, you need to scramble and like create new data or new environments and improve the model that way.

With this kind of like self-improving system that understands interactions from like understands every interaction from the environment you would like kind of get around this problem and you wouldn't need to worry about it anymore.
</details>

### 结语
最后，我想用一年前一篇论文中的一句话来收尾，我觉得它现在极其贴切：AI 正处在一个新时期的边缘，在这个时期，经验将成为改进的主要媒介，并最终使当今系统中使用的人类数据的规模相形见绌。

好的，如果大家有任何问题，我很乐意在之后回答，你们也可以通过那个地址给我发邮件。谢谢。

>> [掌声]

[音乐]

<details>
<summary>Original English</summary>
So I want to leave people on this quote from a paper on a year ago which I find extremely relevant now which is that AI is at the cusp of a new period in which experience will become the dominant medium of improvement and ultimately dwarf the scale of human data used in today's systems.

And yeah. If you all have any questions I'm happy to take them after and uh Yeah, you can also email me at that address.

Thank you.

>> [applause]

[music]
</details>