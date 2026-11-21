---
author: AI Engineer
date: '2025-12-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=pP_dSNz_EdQ
speaker: AI Engineer
tags:
  - prompt-learning
  - coding-agent
  - eval-engineering
  - llm-as-a-judge
  - system-prompt-optimization
title: 系统提示词学习：重构 AI 编码智能体的核心进化引擎
summary: 本文探讨了由 Andrej Karpathy 提出的“系统提示词学习”范式，对比了强化学习（RL）在数据效率上的局限性，提出利用 LLM-as-a-Judge 生成的自然语言反馈来驱动提示词迭代。通过在 SWE-bench 基准测试上对 Claude Code 和 Cline 进行实测，证明了该方法仅需少量样本即可显著提升智能体的工程问题解决能力。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Aparna Dhinakaran
  - Andrej Karpathy
companies_orgs:
  - Arize AI
  - Anthropic
  - OpenAI
products_models:
  - Claude Code
  - Cline
  - SWE-bench
  - GPT-4o
  - DSPy
media_books: []
status: evergreen
---
### 动态演进：系统提示词在编码智能体中的核心地位

在当前的 AI 领域，人们对前沿编码模型的关注度极高，但有一个关键点往往被忽视：构建这些编码智能体（Coding Agents）的工程师在**系统提示词**（System Prompts: 定义模型行为、约束和工具使用的一段核心指令）上投入了海量时间。最近在社交媒体上引发热议的 **Claude** 系统提示词泄露事件清晰地展示了这一点。无论是 Cursor 还是最近流行的编码智能体，其系统提示词的长度和复杂度都令人惊叹。更重要的是，这些提示词并非一成不变的静态文本，而是处于不断的迭代之中。这种持续的迭代正是让这些智能体在复杂的工程任务中脱颖而出的核心背景信息。

**安德烈·卡帕斯**（Andrej Karpathy: 前特斯拉 AI 主管，OpenAI 创始成员）曾将这种范式称为**系统提示词学习**（System Prompt Learning）。他认为这极像人类的学习过程：智能体获取英文形式的反馈，并利用这些反馈来调整下一次的行为。他甚至用电影《记忆碎片》（Memento）来做类比——主角会忘记学到的东西，于是他把信息记录下来，并用这些记录来指导第二天的行动。系统提示词学习的本质，就是为原本“健忘”的模型建立一套持续进化的知识与规则库。

<details>
<summary>Original English Source</summary>
Hi everyone. Thanks so much for coming. Um, well, today I'm excited. We're going to talk a little bit about prompt learning and how to use that with eval. uh if any of you guys um are spending a lot of time thinking about the frontier coding models, I think there's so much attention on on them. But just what's not so obvious is how much time is actually spent uh on the system prompts uh for those building these coding agents. So here's actually a look um this is a tweet that went viral about the whole system prompt uh of Claude that's been leaked. I'm sure you know they've changed it since then. Um, but you can actually see that Claude, there's cursor, there's Clyde. Um, and just the length of the actual system prompt um, for each one of these. And I think what's not as obvious is these actually aren't just static. They are repeatedly iterated on. And it's such an important piece of context that actually goes into making these coding agents the most successful agents out there. Um, it's not just us talking about it. Karpathi talks about it a lot. Um, and this was a viral tweet that that he posted, which was there's this paradigm around iterating on these prompts that he he's kind of coined it system prompt learning. And what he said is that it almost feels like humans learning because they take back English feedback uh and use that to actually iterate on what they should do differently the next time. And I think he wrote something like it's almost like that movie momento where the guy forgets uh what you know what he learns and then he starts writing it down and then uses that to actually kind of go through his next day. And so this is a little bit of the concept behind system prompt learning.
</details>

### 范式飞跃：从强化学习到自然语言反馈的进化

为了理解提示词学习的优势，我们可以将其与**强化学习**（Reinforcement Learning: 通过奖励机制优化决策的机器学习方法）进行对比。以学生备考为例，在强化学习模式下，学生参加考试后只得到一个标量分数（Scalar Reward: 如 70 分或 80 分）。学生必须在没有具体解析的情况下，盲目地摸索如何提高下次考试的分数。虽然强化学习在很多领域非常成功，但它存在严重的**样本效率低下**（Sample Inefficient: 需要海量数据才能达到预期效果）问题。它耗时极长、极度渴求数据，且通常需要一整个数据科学团队来维护，对于快速构建智能体的团队来说往往显得过于繁重。

相比之下，**提示词学习**提供了一个更具吸引力的范式。同样是考试，学生不仅能得到分数，还能得到具体的**英文反馈**。这份反馈会告知学生哪道题做对了、哪里出错了、错在了哪些概念上，以及下一步该复习什么。这种基于语义的反馈极大地缩短了学习路径。我们将这一概念应用于编码智能体的优化中，针对 **Claude Code** 和 **Cline** 进行了测试。这两个智能体都有允许用户添加自定义规则的机制（如 `CLAUDE.md` 或 `rules` 文件）。我们最初让这些规则文件保持空白，作为基准测试的起点。

<details>
<summary>Original English Source</summary>
And what we wanted to do was show you guys a little bit of how that works and then put that to test on two of the most popular coding agents uh Claude and Klein today. So first off, how does prompt learning actually work? So for those of you who are familiar with RL, what I thought we'd do is just do a little analogy compare how does RL work versus system prompt learning. For RL, you know, if we just took an analogy of a student who's trying to improve their exam scores. They take an exam, you know, somebody grades the exam, you have a scalar reward, which is like, you know, they got a 70%, an 80%, 90%, and then they have to figure out almost blindly just with that score how to actually improve their score on the next exam. And I think this is actually one of the flaws of I mean RL works, don't get me wrong, amazing in so many concepts and domains, but it can be, you know, a long path to actually figure out what the right solution is. And I think some of the things that we've noticed is that it can be sample inefficient. It takes a lot of data to get what you want. It's time inensive. It's data hungry. You need to have a whole data science team to do this. and it just might be overkill for teams who are trying to build agents because LLMs are already so good. So if you're a team who's actually trying to build an agent, maybe prompt learning is actually slightly might be slightly more of an interesting paradigm for you. So in this scenario, same same analogy. You have a student who's taking an exam, there's some exam score, except in this case, what actually gets outputed isn't just the score. They got a 70, they got an 80, but you also get back some kind of English feedback. Why did they get this answer right? What did they mess up on? Here's concepts that they missed on, what do they need to go study? And then they use this information to actually go and and prepare on what to do next um to to get a better score. This is basically the the concept that we applied to coding agents.
</details>

### 闭环实验：利用 LLM-as-a-Judge 驱动提示词自动迭代

我们在 **SWE-bench**（一个衡量 AI 解决真实 GitHub 问题的基准测试）上对这一范式进行了实证。在没有任何自定义规则的初始状态下，Claude Code 的解决率约为 40%，Cline（基于 Claude 3.5 Sonnet）的解决率约为 30%。我们的目标是：能否在不进行**微调**（Fine-tuning: 调整模型权重）、不更换模型的情况下，仅通过优化系统提示词来提升分数？

优化的核心流程如下：首先，让编码智能体尝试解决 SWE-bench 中的问题并生成补丁；其次，运行单元测试；最关键的一步是，将问题描述、智能体的代码实现和测试结果提交给一个 **LLM-as-a-Judge**（LLM 评委: 使用大模型作为评估器来判断任务质量）。这个“评委”不仅给出成功或失败的判断，更重要的是生成深度的**失败解释**——例如是特定的库解析错误，还是没有处理某种边界情况。最后，这些解释被输入到一个庞大的 **Meta-prompt**（元提示词: 用于生成或优化其他提示词的高阶指令）中，该指令会对原始的系统规则进行“差异对比”（Diff），生成全新的、包含学到教训的提示词规则。

<details>
<summary>Original English Source</summary>
And we ran this kind of test on both Claude as well as Klein. Um, both of these, as you know, start off with some kind of uh system prompt, which in cloud code, this is kind of a snippet of it. And they both kind of come with something that you can append rules to. So, client has rules, cloud MD has the cloud MD file, and it starts off empty. You can go in and add whatever is important for your repo. So, what we did was actually took, you know, just benchmark both client and cloud code on Swebench. I'm going to kind of run through theam uh this entire example at Sweetbench, but this entire thing we also ran on BBH and a ton of other uh software engineering data sets, but you can see here just on vanilla client vanilla cloud code um nothing added to the cloud MD or the client rules. Um they had you know about I think with client somewhere on you know cloud sonnet 45 it was about 30% of the github issues actually resolved uh cloud code it was about 40% of the github issues resolved. So we took this as kind of our starting benchmark and the thesis is is could we actually use prompt learning to see if we can improve the system prompt and see if um it was able to with the new system prompt actually you know give us a better uh score on these benchmarks. We didn't do anything on fine-tuning. We didn't change the models anything like that. It was just focused on the system prompt. Um this is the process that we went through. We took the coding agent. Uh we had it actually write some code. Um we ran unit tests and then um we then passed that through to some kind of um model that was doing the LLM as a judge evals. And I'll show you guys what that looks like. But the LLM as a judge eval actually gave back why did it fail? Did it fail because of this? Uh can you give some examples of you know what were common scenarios that it didn't do good on? and then it actually use those kind of evals to then go back and add it to a meta prompt to come back with kind of the the system prompt rules that we're going to append to.
</details>

### 实测效能：工程实践中的显著增长与评估工程的重要性

实验结果令人振奋：在仅使用了 150 个样本作为训练数据的情况下，**Claude Code** 的 GitHub 问题解决率提升了 5%，而 **Cline** 更是提升了 15%。这充分证明了在顶级编码智能体之上，系统提示词学习具有巨大的潜力。

很多人可能会问，这与 DSPy 中的 **GEA**（Gradient-based Evolver: 一种提示词优化器）有何不同？GEA 的基本思路也是利用自然语言反馈进行优化。然而，通过对比测试，我们发现 GEA 通常需要经历极多次的循环和展开（Rollouts）才能收敛。而我们的方法效率更高，其核心差异在于我们投入了大量精力进行 **评估工程**（Eval Engineering）。撰写高质量的“评委”提示词至关重要，因为只有评估器能返回精准、深刻的失败解释，Meta-prompt 才能据此生成真正有效的规则。因此，要让系统提示词学习发挥作用，构建一套能够提供深度见解的评估系统是最为关键的底层支撑。

<details>
<summary>Original English Source</summary>
So let's talk through kind of the process. So first we had kind of the SWEBench data set. Uh SWEBench in this scenario is just 150 examples. Uh we did this for both client and cloud code where we took the original prompt which had no rules. We gave it kind of the software engineering problem and then it generated some kind of patch to actually solve that and then we ran the generated solution through the unit test. Then whatever the unit test came back with whether it was right or wrong, we then passed this into an LLM as a judge eval. And this is kind of the most important part because this actually generated the explanation for us. So we passed in the problem statement. We passed in what the coding agent solution was, the unit tests, and then the actual solution that it came up with. Uh, pass that in. And this that you're looking at in the center here is actually the LLM as a judge eval. And these evalu engineering is a whole kind of concept that, you know, we spend a lot of time on. And writing really good evals is I think um how you get the best kind of insight into what you could do to improve your agents. So in this scenario, what we did was we wrote a good LM as a judge eval prompt. It outputed whether it failed or passed. And then this is the key part. We actually asked for an explanation. Why did it actually mess up? um you know for specific libraries in the Sweetbench light test um you know it was parsing errors or it was not handling um there there's all sorts of actually different categories of errors but we went through and we we kind of looked at the explanation of what went wrong in each scenario. We then passed into a huge meta prompt. So this is actually what's helping us iterate on our system prompt. We passed in the original claude or client system prompt. We passed in the original rules which for us started off empty. Um and then we passed in here was the input, here was the LM is a judge eval, and then here was the actual explanation from that eval. Passed that all into the meta prompt and then we did kind of a diff comparing you know the old world. So just for you just to remember the old world had the original clawed system prompt no rules kind of added or appended to it. And then the new world where it generated this entire rules of what to avoid or what to um what it had learned essentially from all those mistakes it had actually made. And then we ran this basically on the entire Sweetbench light again. Um and what we saw was that you know on 150 examples we were able to get cloud code up by 5% more GitHub issues resolved client um you know 15% and this was literally on I think the key thing is like 150 examples of just training data that was used um on the most kind of powerful coding agents that are out there. Um, and so just think about kind of the impact that could have for your agents. Many of you guys in this room might be thinking, okay, well, prompt learning is cool, but how does that compare to GEA? If you're familiar with DSPI and you've kind of seen, I don't know if it's GEA or Jeepa. I've heard both. Um, but you know, you guys might be asking, well, how is this different? Um, so GEA, just just in case you guys aren't familiar, it's a prompt optimizer from DSPI that is essentially very very similar to what we're talking about, which is taking English feedback using that English feedback inside of the actual prompt. Um, and what we did was actually run a sidebyside benchmark against GEA where we compared kind of our prompt learning against GEA. And um I think what we saw was that GEA required many many loops and rollouts compared to um kind of a a fraction of that which was our approach. And I think the key difference here, I mean the underlying approach around using English feedback is the same, but I think the key thing that was really different here was we spent a lot of time actually developing and iterating on the evals and the eval prompts really mattered to making sure that you gave really good explanations back to the agent. Um, and so eval. This was super critical for us to be able to get this to work.
</details>