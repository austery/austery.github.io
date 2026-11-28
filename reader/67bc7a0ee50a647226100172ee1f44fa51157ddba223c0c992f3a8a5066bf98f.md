---
author: AI Engineer
date: '2026-11-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=DQwcuXgAIA0
speaker: AI Engineer
tags:
  - agentic-workflow
  - llm-as-judge
  - evaluation-metrics
  - multi-agent-systems
title: ZoomInfo 工程师分享如何通过结构化小问题和 Jev 模型解决 LLM 评判者在智能体工作流中的失灵问题
summary: ZoomInfo 工程师 Brian Kennedy 分享了在多智能体编排中，LLM 评判者因过度信任智能体生成的“故事”而导致虚假操作通过的案例。通过离线评估发现评判者准确率仅为 65%，团队随后将宽泛的评估改为由 Jev 模型执行的结构化“是或否”问题，并采用影子模式进行验证，显著提升了拦截错误的效率和成本效益。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - ZoomInfo
  - Jev
media_books: []
status: evergreen
---
## 开场与真实失败案例

>> 各位下午好。我是 Brian Kennedy，ZoomInfo 智能体平台（agentic platform）的一名工程师。现在，我想先向大家展示一段我们某个智能体（agent）写的内容。这是我们产品的真实输出。该智能体的任务是为客户安排发送一封电子邮件。以下是它汇报的结果。它说它已经安排好了邮件，已将其加入队列，并将在周二发出。不过，我们并不只是盲目信任智能体。第二个模型会检查智能体的工作。我把这个模型称为评判者（judge）。评判者读了这份汇报并接受了它。很好。

<details><summary>Original English</summary>

[music]
>> Good afternoon, everybody. I am Brian Kennedy. I'm an engineer on ZoomInfo's agentic platform. Now, I want to start with showing you something one of our agents wrote. This is a real output from our product. The agent's job was to schedule an email for a customer. And this is what it reported back. [clears throat] It said it scheduled the email, it queued it up, and that it was going to go out on Tuesday. We don't just trust the agent, though. A second model checks the agent's work. I'm going to call this one the judge. The judge read this and it accepted it. Great.

</details>

现在，问题来了。以下是实际发生的情况。这些是工具结果，即智能体调用工具时实际运行情况的记录。我把这些称为凭证（receipts）。智能体尝试在 Salesforce 中创建一条记录，但失败了。返回的错误信息显示记录未被创建，并告诉智能体不要汇报成功，也不要捏造记录。这条信息正是我们自己针对这种情况编写的。智能体再次尝试。它创建了一个任务（task），也就是一个待办事项。实际上从未安排过任何邮件。该智能体甚至没有可以发送邮件的工具。智能体捏造了这件事，而评判者批准了它。这就是两个失败。智能体捏造了一次发送，而评判者草率地盖章通过，批准了一个从未真正核实过的声明。所以，如果你也在构建智能体，你可能遇到过这种情况，也可能有一个这样的评判者。它可能是一个代码审查员、评估（evals）的评分员，或者循环中的监督者。每当一个模型决定另一个模型的工作是否合格时，这种情况都可能发生。在接下来的大约 10 分钟里，我将向大家展示我们是如何发现这个问题并采取应对措施的。

<details><summary>Original English</summary>

Now, here's the problem. And this is what it actually happened. Their uh these are the tool results, the record of what actually ran when the agent called the tools. I'm going to call these the receipts. The agent tried to create a record in Salesforce and it failed. The error message that came back says the record was not created and it tells the agent not to report a success or even make up a record. We wrote this message ourselves for exactly this situation. The agent tried again. It created a task, which is a to-do. No email was ever scheduled. The agent doesn't even have a tool that can send an email. The agent made it up and the judge approved it. So that's two failures. The agent fabricated a send and the judge rubber stamped it, approved uh a claim that never actually checked. So if you build agents, you probably have run into this and you probably have a judge like this. It might be a code reviewer or a grader of your evals or a supervisor in your loop. Anytime a model decides whether another model's work is good, this can happen. About for the next 10 minutes, I'll show you how we caught this and we did about it.

</details>

## 背景：Agent Teams 与 LLM 评判者

首先，简单介绍一下背景。我在 Zoom Info 的团队叫做 Agent Teams。我们上周发布了这个项目。它是一个多智能体编排层，位于 Zoom Info 的 GTM Studio 中。它协调公司系统中的一组专业智能体来运行 GTM 工作流。例如，寻找公司、研究它们、撰写电子邮件、将其记录到 CRM 中。每个智能体都有自己的角色和指令，以及诸如 Salesforce、HubSpot、Slack 等工具。这些智能体在客户的系统中做出真实决策并采取真实行动。它们写入记录并发送消息。每个团队和每个智能体完成一个步骤后，第二个模型会检查其工作。这就是评判者，它有三个选项：继续推进、重做该步骤，或完全停止任务。你可能听说过这被称为“LLM 作为评判者”（LLM as a judge）。这与代码审查员或评估评分员是同样的思路。

<details><summary>Original English</summary>

First, some quick background. My team at Zoom Info is called Agent Teams. We announced this last week. It's a multi-agent orchestration layer that lives in Zoom Info's GTM Studio. It coordinates a team of specialized agents across the company's systems to run GTM workflows. For example, find companies, research them, write an email, log it into their CRM. Each agent has its own roles and instructions like and tools like Salesforce, HubSpot, Slack. These agents make real decisions and take real actions in the customer's systems. They write records and they send messages. Every team and every agent finishes a step. A second model checks its work. That's the judge and it has three options to move on, to redo the step or to stop the job altogether. You probably heard this called LLM as a judge. It's the same idea as a code reviewer or an eval grader.

</details>

对我们来说，困难的部分在于它只有一个模型，却必须对我们运行的每一种智能体进行评分。我们的客户使用任何智能体、任何工具、以任何顺序构建他们自己的工作流。因此排列组合几乎是无穷无尽的。评判者的任务列表也必须随之增长。评判者能判断工作看起来是否完成，但它无法判断工作是否正确，因为“正确”的含义取决于每项具体任务，而我们对所有任务问的都是同一个问题。接下来是我们的分享内容。首先，我将谈谈我们在检查评判者时发现了什么。然后是我们转而选择的方案，以及你今天就可以用自己的智能体做些什么。

<details><summary>Original English</summary>

Now, the hard part for us is that it's one model and it has to grade every kind of agent that we're running through it. Our customers build their own workflows with any agent and any tool in any order. So the permutations are almost infinite. So the list of jobs for the judge has to grow with it. The judge can tell whether the work looks finished, but what it can't tell is whether the work was right because that depends on what right means for each job and we're asking it the same question for all of them. So here's where we're going. First, I'll talk about what we found when we checked the judge. Then what we chose instead and what you can do today with your own agents.

</details>

## 离线评估与评判者失灵的原因

首先，我们运行了离线评估（offline evals）。我们从生产环境中抽取了 500 个真实步骤，每个步骤都带有评判者做出的决定。然后，我们用一个更大的前沿模型（frontier model）对每一个步骤重新评分，给出“接受”或“退回”的结果。接着我们人工核查了每一个样本并检查了评分。在我们与模型意见不一致的地方，我们采纳了自己的判断。这为我们提供了所有 500 个步骤的参考标签。结果发现，评判者只有 65% 的时间是正确的，差不多跟抛硬币一样。它接受了 118 个本应退回的步骤。这占了它所接受的全部内容中的四分之一以上。相当糟糕。当我们通读这些案例时，最常见的问题与开头的邮件案例类似：智能体汇报说它做了某事（比如发送了一条消息），但实际上没有任何工具调用执行过该操作。

<details><summary>Original English</summary>

To start, we ran offline evals. We took 500 real steps from production, each with a decision that the judge had made. Then we took a larger frontier model and regraded every one of those to come back with an accept or send back. Then we hand checked each of those samples and we checked the grades. Where we disagreed with the model, we went with our call. This gave us a reference label for all 500 steps. And it turned out the judge was right 65% of the time, so more or less a coin flip. It accepted 118 steps that it should have sent back. That's more than one in four of everything that it accepted. Pretty bad. And when we read through those, the most common problem was that similar to the email at the start, the agent reported that it did something like send a message and no tool call had ever done that.

</details>

为了弄清楚评判者为什么会接受它，让我们回到邮件的例子，看看评判者收到了什么信息。左边是智能体自己的总结，你可以把它看作是一个故事。它很自信，写得也很好，说邮件已经安排好了。现在看右边，这是凭证，也就是实际的工具结果。里面有错误，创建失败，并有信息告诉智能体不要捏造记录。评判者同时拿到了这两份信息，结果它采信了那个故事。工作从表面上看不错，所以它就接受了。这不只是我们评判者的问题。你可以想象一个代码审查智能体，它在看代码差异（diff）之前先读了 PR 描述。这是类似的问题。如果描述写着“我修复了 bug，添加了测试”，智能体在阅读代码时就会偏向于相信这个说法。

<details><summary>Original English</summary>

So to see why the judge had accepted it, let's go back to the email example and look at what the judge was given. On the left, you have what the agent's own summary Think of it as like a story. It's confident, it's well written. It says the email was scheduled. Now on the right, you have the receipts. This is the actual tool results. There are errors, failed to create messages telling the agent not to make up the record. Now the judge had both of these and it went with the story. The work looked fine on the surface, so it accepted it. Now this isn't only our judge. You can think of a code review agent that reads the PR description before it looks at the diff. It's a similar kind of problem. If the description says I fixed the bug, added tests, the agent is going to lean on that when it reads the code.

</details>

因此，一开始最显而易见的解决办法是调优评判者并写出更好的提示词（prompt）。对我们来说，这将是一项非常庞大的工作。我们的智能体要撰写销售邮件、更新 CRM、做研究，为了对每一种工作都做出准确评判，我们必须弄清楚用户到底在要求什么。为每一种工作制定正确的规则，并让所有规则保持最新。这基本上等于为每个用例都定制一个评判者。

<details><summary>Original English</summary>

So the obvious fix at the start was to tune the judge and write a better prompt. For us, that was going to be a significant amount of work. Our agents write sales emails, update CRMs, do research, and to judge each of these well, we'd have to figure out what it was that the user was asking. Give the judge the right rules for every kind of work and keep it all up to date. That's basically a custom judge for every use case.

</details>

## 转向结构化小问题与 Jev

我们选择了另一条路。我们不再问一个宽泛的大问题“这好不好？”，而是开始问一小组简短的“是或否”问题。每个步骤问的都是相同的问题，而且每一个问题都足够小，只需查看凭证就能回答。第一种方案基本上是一个永无止境的提示词调优项目，而第二种方案只是一小撮简单的检查。

<details><summary>Original English</summary>

What we went with, we went a different direction. We stopped asking one big general question, is this good? And we started asking a short list of small yes or no questions. They're the same questions for every step and each one is small enough to answer by looking at the receipts. The first option here is basically a prompt tuning project that never ends, whereas the second one is a small handful of small checks.

</details>

为了回答这些问题，我们使用了 Jev。大家今天已经听了很多关于 Jev 的介绍，所以我就不赘述了。它是一个类型决策模型（type decision model），而不是生成式模型。对于在家观看的妈妈来说，去问 Claude 就好了。我们会向它发送关于该步骤的结构化事实，并列出一种类型的问题。类型问题指的是“是或否”问题，或者从固定选项列表中进行选择的问题。它会为每个答案返回一个概率，并在一次调用中回答所有问题。我们给它提供四样东西：指令、输入、凭证（即每一次工具调用及其成功或失败的状态），以及智能体的报告。然后我们要求它做出一个选择：接受、重做或停止。这个选择决定了最终结果。但同时我们也问了七个“是或否”的问题。这七个问题告诉我们原因。它们决定了是“重做”还是“停止”，并且会进入智能体在真正需要重做某一步时收到的反馈中。

<details><summary>Original English</summary>

Now to answer those questions, we used Jev. You've heard a lot about Jev today, so I'll skip that and keep that short. It's a type decision model, not a generative model. Uh for mom at home watching, just ask Claude. And we'll send it structured facts, you know, about the step and listed a type of questions. A type question is a yes or no question or a choice with from a fixed list of options. It sends back a probability for each answer and it answers all the questions in one call. We gave it four things, the instructions, the uh input, the receipts, uh meaning every tool call, and whether it was successful or failed, and the agent's report. Then we asked for one choice, which was accept, redo, or stop. And that choice makes the decision. But then we also asked seven yes or no questions. Those seven questions tell us the why. They decide between a redo and a stop. And they go into the feedback that the agent gets when it actually has to redo a step.

</details>

现在回到邮件的例子。LLM 评判者接受了它，并且耗时大约两秒半。Jev 为每个选项给出了概率。对于这一步，它给出的“接受”概率是 0%，“重做”是 97%，“停止”是 3%。而且它只花了大约五分之一秒。我们根据“接受”的概率来做决定。达到 30% 或更高，我们就接受；达到 5% 或更低，我们就重做或停止。介于两者之间的任何情况都意味着 Jev 不确定，所以我们会把它交给 LLM 评判者。我们是通过测试一开始的 500 个标签来选定这些阈值的。

<details><summary>Original English</summary>

Now back to the email. The LLM judge accepted it and it took about two and a half seconds. Jev gave us a probability for each option. For this step, it accepted 0%, redo 97% and stop at 3%. And it took about a fifth of a second. We make the decision from the probability of accept. At 30% or higher, we accept that. At 5% or lower, we redo or stop. And anything in between means Jev isn't sure, so we kick it to an LLM judge. We pick those cutoffs from testing the 500 labels that we had at the beginning.

</details>

## 验证效果：离线评估与影子模式

现在，为了测试这样做是否效果更好，我们采取了两条不同的路径。第一项测试使用了离线评估中同样的 500 个生产步骤。Jev 对其中大约十分之七的步骤都足够自信。在这些步骤中，LLM 评判者接受了 82 个本应退回的步骤。这里的每一个红色方块都代表其中之一。Jev 成功拦截了其中的 74 个。蓝色方块则是 Jev 会退回的步骤。

<details><summary>Original English</summary>

Now, to test whether what whether or not this works better, we took two different routes. The first test used the same 500 production steps from the offline eval. Jev was confident enough in about seven out of 10 of them. One of those steps, uh the LLM judge had accepted 82 that should have been sent back. Each red square here is one of those. Jev successfully caught 74 of those. The blue squares are the ones that Jev would have sent back.

</details>

第二项测试是我们所说的影子模式（shadow mode）。两个评判者都会查看每一步，但只有 LLM 评判者的决定算数。所以我们保存了 Jev 本会做出的决定，但不让它影响实际运行。这为我们提供了 37,000 个决策供我们挖掘洞察。在那段时间里，有 728 个步骤出现了工具明显失败的情况。LLM 捕获了其中的 294 个。Jev 捕获了 623 个。而开头那个伪造邮件的案例，也并不是个例。同一个步骤运行了 1,081 次，几乎每次智能体都说自己安排了邮件，而 LLM 评判者只捕获了 1 次。Jev 捕获了 876 次。当你有一个评判者时，每一步都要等待。Jev 的速度快了 10 倍，成本低了 40 倍。在这个规模下，这种提升是巨大的。

<details><summary>Original English</summary>

Now, the second test is what we called shadow mode. Both judges look at every step, but only the LLM judge uh that decision counts. So we saved Jev what would have done, and we don't let it affect the actual run. That gave us 37,000 decisions to mine for insights. And in that time, there were 728 steps where a tool had clearly failed. The LLM caught 294 of them. Jev caught 623. And the fake email from the beginning, it wasn't a one-off thing either. The same step ran 1,081 times, and almost every time the agent said it had scheduled an email, the LLM judge only caught it once. Jev caught that 876 times. And when you have a judge, every step waits. Jev was 10 times faster and 40 times cheaper. At this scale, it is massive.

</details>

## 下一步计划与行动建议

那么接下来是什么？目前，每个步骤都使用相同的七个问题。它们连同事实一起输入 Jev，Jev 给出接受、重做或停止的结果。但接下来，我们正在添加后置条件检查（post-condition checks），这些问题取决于该步骤中调用了哪个工具。这样我们就不用猜测。我们预先就知道这一步，因为工具会告诉我们。如果某个步骤调用了比如说发送工具，我们还会询问消息是否已送达。如果它写入了一条记录，我们会询问该记录是否存在。这些问题会和那七个问题一起，在同一次调用中进入 Jev。

<details><summary>Original English</summary>

[snorts] So what's next? Right now, every step goes with the same seven questions. They go into Jev along with the facts, and Jev gives us an accept, redo, or stop. But next, we're adding post-condition checks, which are questions that depend on which tool called uh was within the step. So we don't have to guess. Uh we know the step upfront because the tool tells us. If a step called let's say a send tool, we also ask whether the message was delivered. If it wrote a record, we ask whether the record exists. And those go into Jev with the same seven questions in the same call.

</details>

那么，你今天可以用自己的智能体做些什么呢？首先，挑选一个判断环节。在你的系统中的某个地方，一定有一个 LLM 在决定某件事是否合格。它可能在审查代码，或者在给评估评分。挑选其中一个，把它改写成几个可以根据证据回答的简单“是或否”问题。第二是构建它。老实说，这是最简单的部分。我们用了 Jev，我们的方案是七个问题。第三，以影子模式发布它。让它在你现有的系统旁边运行，但先不要让它做决定。只需把结果保存下来，之后再进行分析。然后阅读这些案例，看看两者在哪里意见不一致。不要想太多，从小处着手即可。在衡量之前，我们一直信任我们的评判者。去衡量你的评判者吧。运行第二道检查。在影子模式下运行它，看看它在哪里出现分歧。你可能会对自己的发现感到惊讶。谢谢大家。

<details><summary>Original English</summary>

Now what can you do today with your agents? First, pick one judgment. Somewhere in your systems there is an LLM deciding whether or not something is good. It might be reviewing code, grading an eval. Pick one of those and rewrite it as a few simple yes or no questions that can be answered from the evidence. Second is build it. This is the easy part honestly. We used Jev and ours was seven questions. Then the third, ship it in shadow mode. Run it next to what you already have, but don't let it make the decisions yet. Just save it uh and then you can analyze it later. Then read the cases and see where the two disagree. And don't overthink it, just start small. We had trusted our judge until we measured it. Measure yours. Run a second check. Run it in shadow mode and see where it disagrees. You may be surprised with what you find. Thank you.

</details>