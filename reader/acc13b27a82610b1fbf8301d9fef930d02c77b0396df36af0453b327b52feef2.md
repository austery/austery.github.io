---
author: Dwarkesh Patel
date: '2024-05-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ERpNuLzKmJY
speaker: Dwarkesh Patel
tags:
  - llm-development
  - prompt-engineering
  - conversational-ai
  - instruction-following-models
title: ChatGPT的诞生：从基础模型到对话助手的演进之路
summary: 本期内容深入探讨了ChatGPT的诞生历程，揭示了从早期基础模型到指令遵循模型，再到最终实现对话助手的关键技术演进。演讲者分享了OpenAI在模型开发中的探索，包括如何通过指令遵循和对话数据优化模型，以及GPT-3.5和GPT-4在这一过程中的作用。对话还触及了Google在聊天机器人领域的早期研究，并阐述了为何对话式AI比指令式AI在用户交互和模型行为上更具优势，以及自研ChatGPT的非易事性，特别是多轮微调和RLHF的重要性。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Google
products_models:
  - ChatGPT
  - GPT-3.5
  - GPT-4
  - Lambda
  - Mina
  - Web GPT
media_books: []
status: evergreen
---
### ChatGPT的演进之路

**John Schulman**: 在ChatGPT之前，OpenAI拥有**指令遵循模型**。而当时的想法是，我们有**基础模型**，人们可以以复杂的方式提示它们，但提示它们很困难，因为它们本质上是自动补全，所以你需要用一些例子设置一个非常好的提示。因此，OpenAI的人们正在努力，只是拿来基础模型并让它们更容易被提示，这样如果你只写一个问题，它就会回答问题，而不是给你更多问题。我们有了这些指令遵循模型，它们就像基础模型，但更容易使用。这些是在API中部署的原始模型，GPT-3之后，它们是下一代模型。

<details>
<summary>Original English</summary>

**John Schulman**: Before ChatGPT, OpenAI had these **instruction-following models**. And, uh, that was, B, the idea. There was, um, we had **base models** and people can, um, prompt them in elaborate ways, um, but, uh, they're also kind of hard to prompt. You had to, uh, they basically do autocomplete, so you have to set up a very good prompt with some examples. So, uh, people at **OpenAI**, uh, were working on, um, just taking the base models and making them easier to prompt, so that if you just wrote a question, it would answer the question instead of giving you more questions or something. Uh, so we had these instruction-following models which were kind of like base models but a little easier to use. Um, and those were the original ones deployed in the API, uh, after, um, **GPT-3**. Those were the next, uh, generation of models.

</details>

**John Schulman**: 同时，也有很多人在思考**聊天**。比如，**Google**发布了一些论文，像是有**Lambda**和更早的**Mina**。它们有这些聊天机器人，更像是一个专门用于聊天任务的基础模型，非常擅长聊天。根据论文的例子，它们更多地用于有趣的应用程序，比如模型会扮演某个角色。它不像“帮我重构代码”那样功能化。所以，是的，确实有人在思考聊天。我之前在一个名为**Web GPT**的项目上工作过，它更多地是通过网络浏览和检索来进行问答。当你进行问答时，它确实想进入聊天状态，因为你总是想问后续问题，或者有时需要澄清，模型应该问一个澄清问题，因为问题本身含糊不清。所以，在我们完成了第一个版本后，很明显下一版本应该是对话式的。

<details>
<summary>Original English</summary>

**John Schulman**: Um, then at the same time, there were definitely a lot of people thinking about, um, chat. So, uh, so **Google** had some papers, uh, like they had, uh, **Lambda** and, um, earlier **Mina**. So they had these chat bots, and it was more like, um, uh, like you had a, it was more like a base model that was really specialized to, um, the task of chat, really good at chat. And, uh, like, I think, at least looking at the examples from the paper, it was more, uh, used for sort of fun applications, like, um, where the model would, would, uh, like take on some persona and pretend to be that persona. It was not so functional, like, um, like, help me refactor my code. Um, so, yeah, there are definitely people thinking about chat. I had worked on a project before, uh, looking at chat called, uh, **Web GPT**, which was more about doing question answering with the help of web browsing and retrieval. And, well, when you do question answering, uh, it really wants to be in a chat because, um, you always want to ask follow-up questions, or sometimes you need a clar, the, the model should ask a clarifying question because the question is ambiguous. So it was kind of clear after we did the first version of that that we should, the next version should be conversational.

</details>

**John Schulman**: 因此，我们开始着手开发一个**对话式聊天助手**。这个助手是基于**GPT-3.5**构建的，它在2022年初完成了训练。那个模型在语言和代码方面都相当不错，所以我们很快意识到它在**编码辅助**方面actually相当出色，这是我们感到兴奋的一点。所以，我们花了将近一年的时间来研究它，我们还加入了浏览功能。但后来我们逐渐淡化了它，因为模型的内部知识已经足够好，浏览功能并不是最吸引人的部分。

<details>
<summary>Original English</summary>

**John Schulman**: So anyway, we started working on, uh, like a conversational chat assistant. Um, and, uh, we, uh, this was built on top of **GPT-3.5**, which was done training at the beginning of '22. And, uh, that model was quite good at language and code. So we quickly realized that it was actually, uh, quite good at **coding help**, and that was one of the things we were excited about. So, yeah, we worked on that. Uh, we worked on that for, for most of the year. And we had, we had browsing, um, as another feature, and it, though we ended up, uh, like deemphasizing that later on because the, like, the model's internal knowledge was so good that we didn't, that the browsing, um, wasn't the most interesting thing about it.

</details>

**John Schulman**: 接着，我们在2022年8月，**GPT-4**完成了训练。当时，OpenAI的主要**RL（强化学习）**工作是指令遵循模型，因为这些模型将被部署到生产环境。因此，GPT-4的第一个微调版本使用了那整套技术栈。这些模型非常好，大家看到它们后都很兴奋。但它们有时会提供惊人的输出，但模型明显不太可靠，经常会产生幻觉，有时会给出相当离谱的输出，显然还没有准备好。

<details>
<summary>Original English</summary>

**John Schulman**: Um, and then, uh, we were thinking about, we had it out for beta testing or to friends and family for a while, and we were thinking about doing a public release. Um, but, um, at that time, uh, actually **GPT-4** finished training in August, or, um, yeah, in August that year. And, um, actually, the, um, like the flagship **RL** effort at OpenAI was the instruction-following effort because that was the models that were being deployed into production. So, um, like the first fine-tunes of GPT-4 used that, um, that whole stack, and that was, um, yeah, those models were really good, and everyone got really excited about that after seeing the, uh, like, instru, fine-tune GPT-4s. Uh, but so they were really, really good. They would occasionally give you amazing outputs, but they were also, like, a little bit, the model was clearly, like, pretty unreliable. Like, it would sometimes hallucinate it a lot, and it was like pretty, it would sometimes give you pretty unhinged outputs. So it was clearly not quite ready for prime time, but it was, like, obviously very good.

</details>

**John Schulman**: 然后，大家在一段时间内似乎忘记了聊天。但我们继续推进，将**指令**和**聊天**的数据集混合在一起，试图获得两者的最佳结合。聊天模型显然更易于使用，行为更合理，能意识到自身的局限性。另一个关于聊天的方面是，对于指令模型，像“以友好的方式或有帮助的方式完成这段文字”这样的任务定义非常模糊，对模型和人工标注者都很困惑。而对于聊天，人们对“有帮助的机器人”应该是什么样子有更直观的理解。因此，更容易让人们理解模型的预期功能。结果是，模型拥有更连贯的个性，并且具有更稳健、合理的行为。

<details>
<summary>Original English</summary>

**John Schulman**: Um, and, uh, yeah, so I guess that, um, people forgot about chat for a little while after that. C, about this, like, alternative branch. Uh, but then we, we ended up, um, we pushed it further, and we ended up, like, mixing together all the datasets, like the instruct and the chat data, and to try to get something that was the best of both worlds. And, uh, I think the, yeah, the models we, the chat models were like, uh, were clearly more, um, like, it was an easy, easier to use. It was sort of more, um, it sort of, uh, like, automatically had much more sensible behavior in terms of, like, the model knowing its own limitations. The other thing about chat was that when we had these instruct models, uh, like the task of, uh, complete this text, but in a nice way, or in a helpful way, that's like a pretty poorly defined task. So I think, uh, like, I think that task is like both confusing for the model and for the human who's supposed to do the data labeling. Whereas for chat, um, I think people had an intuitive sense of, uh, like, what a helpful robot should be like. So I think it was, uh, just much easier to tell people, uh, like, uh, to, to get, for people to get the idea of what, what the model was supposed to do. Yeah.

</details>

**John Schulman**: 那么，任何人是否都能使用你们公开的微调API来制作ChatGPT？不完全是。假设当时我们有3.5可供微调，你可以做出相当接近的东西。但我不确定你是否能只通过一次**微调**就能做到，即只用人工编写的数据进行微调。我认为你需要进行多次迭代。如果你不进行RL（强化学习），而我们确实做了，那么你需要进行某种**迭代式监督微调**，即让人类编辑模型生成的输出来进行微调。因为如果只用人类生成的数据训练，即使质量很高，模型也难以完美拟合，因为它可能无法输出这样的内容。所以你需要进行一些更接近RL的迭代。那样可以得到非常接近的结果，但这并不简单。

<details>
<summary>Original English</summary>

**John Schulman**: Um, and, uh, so that, so as a result, I think the, um, like the model had a much more coherent personality and, uh, like it was much, like, easier to get, um, like, robust, like, sensible behavior. Robustly. Is it the case that anybody could have made ChatGPT using your publicly available fine-tuning API? Not exactly. I mean, uh, they could have, um, I don't remember the status of which models were available for fine-tuning. Uh, you, assuming we had 3.5 available for fine-tuning at the time, you could have made something pretty decently close. But I'm not sure you would have, um, I don't think you would have been able to do just one iteration of fine-tuning where you have like, purely human-written data, and you fine-tune on that. I think you would want, like, you'd want to do several iterations. Like if you're not going to do RL, um, which, which we did, um, you'd want to do some kind of **iterative supervised fine-tuning** where you have like, humans edit the model-generated outputs. Because it's really hard to get people to, like, if you train on human-generated data, even if it's really high quality, it's just hard for a model to fit that data perfectly because it might not be, like, it might not be something a model is capable of outputting. Uh, so you need to do something iterative that looks a little bit more like RL.

</details>

**John Schulman**: 但是，我们也有一个在ChatGPT之前发布的、用RL训练的指令遵循模型。所以，如果你给它加上一个聊天的包装器，你就能得到一个相当接近的东西。但那个模型，如果你只是用聊天方式提示它，它在某些方面就有差异，比如它很擅长写作和诗歌，但不太擅长认识到自己的局限性以及事实准确性等方面。

<details>
<summary>Original English</summary>

**John Schulman**: Uh, so I think if you had done that, you could have gotten something pretty close. But, um, that would have been kind of non-trivial. Um, but we also had another, uh, like instruction-following model trained with RL that was released a little before ChatGPT. So I think if you put a chat, like wrapper on that, you would get something decently close. Uh, but it, like, that model, um, like if you just prompted it with chat, um, so, but that model had some, uh, differences in, uh, strengths. Like, it was like that model was pretty good at writing and poetry and so forth, but it wasn't, uh, it sort of, it wasn't as good at knowing its limitations and, uh, at factuality and so forth.

</details>