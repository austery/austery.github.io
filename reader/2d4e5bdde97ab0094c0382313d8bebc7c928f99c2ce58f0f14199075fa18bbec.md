---
author: AI Engineer
date: '2026-11-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=BT1Mo-fD-g0
speaker: AI Engineer
tags:
  - coding-agent
  - undo-mechanism
  - error-recovery
  - agent-evolution
title: UndoBench 与 Evo-Undo：解决编程智能体的故障恢复与撤销难题
summary: Tanmay 与 Dolly 介绍了评估编程智能体撤销与恢复能力的研究。UndoBench 发现智能体正常成功率达 84%，但在人为注入故障时仅 47% 能正确恢复，且盲目重试易引发重复副作用。Evo-Undo 提出捕获初始状态见证、扩充恢复语言和独立验证机制，将可准入的自进化改进显著提升。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Tanmay Sah
  - Dolly Sah
companies_orgs: []
products_models:
  - UndoBench
  - Evo-Undo
media_books: []
status: evergreen
---
### 编程智能体的“撤销”难题与 UndoBench 基准测试

**Tanmay**: 大家好。我是 Tanmei。今天我和 Dolly 一起，我们将介绍编程智能体所缺失的“取消”按钮。设想一个编程智能体正在代码仓库中处理一个问题。他应用了补丁，运行了测试，所有测试都成功通过。它甚至创建了一个发布标签，但随后底层集成却失败了。现在问题来了：智能体实际上能否将一切恢复到先前的状态？

<details><summary>Original English</summary>
**Tanmay**: Hello everyone. I am Tanmei. Today I'm with Dolly, and we're going to introduce the missing "cancel" button for programming agents. So, imagine a programming agent working on a problem in a repository. He applies the patch, runs the tests, and everything passes successfully. It even creates a release tag, but then the lower-level integration fails. Now the question arises. Can the agent actually return everything to its previous state?
</details>

**Tanmay**: Git 可以告诉我们仓库中发生了哪些变化，但 Git 之外的变化怎么办？比如外部 API 调用、运行时配置或通知？而且仅仅重试某项操作并不一定能撤销已经发生的事情。所以我们不仅想了解智能体是否能执行任务，还想知道当出现问题时它们能否恢复。这引出了我们的第一篇研究论文——Undo Bench。我们想探究智能体完成任务的能力是否也意味着它具有从失败中恢复的能力。我们在 2880 组配对试验中评估了智能体，对比了正常表现与人为制造故障时的表现。在正常条件下，智能体的成功率为 84%，但当我们引入故障时，原本成功的试验中只有 47% 能够正确恢复。注意这两个百分比的分母不同，但确实，即使智能体能够成功完成任务，恢复依然是一个严重的问题。

<details><summary>Original English</summary>
**Tanmay**: Git can tell us what has changed in the repository, but what about changes outside of Git, such as external API calls, runtime configurations, or notifications? And simply retrying an operation doesn't necessarily undo what has already happened. So we wanted to understand not only whether agents could perform tasks, but also whether they could recover when something went wrong. This brings us to our first research paper, Undo Bench. We wanted to investigate whether an agent's ability to complete a task also implies its ability to recover from failure. We evaluated agents on 2880 paired trials, comparing normal performance with performance during an artificially created failure. So, under normal conditions, the agent succeeded 84% of the time, but when we introduced failures, only 47% of normally successful trials recovered properly. Note that these two percentages have different denominators, but yes, even when an agent can successfully complete a task, recovery remains a serious problem.
</details>

**Tanmay**: 现在让我们来看一个具体的故障场景。设想一个编程智能体向外部系统发送请求以创建工单。请求已经发出，智能体正在等待响应。接下来，服务器收到了请求并成功创建了 781 号工单，但在返回给智能体的途中确认信息丢失了。从智能体的角度来看，请求超时了，但他并不知道工单实际上已经创建成功。超时意味着没有收到响应，并不意味着操作失败了。因此，智能体在没有检查第一次操作是否已完成的情况下重复发送了请求。现在我们有了两张工单，尽管智能体原本只想创建一张。因此，在 Undo Bench 中，盲目重试导致此类试验中有 54% 产生了重复效应。这就是为什么我们需要区分响应失败和操作失败。

<details><summary>Original English</summary>
**Tanmay**: Now let's look at a specific failure scenario. Imagine that a programming agent sends a request to an external system to create a ticket. The request has been sent and the agent is waiting for a response. Next, the server receives the request and successfully creates ticket number 781, but the confirmation is lost on the way to the agent. From the agent's perspective, the request timed out, but he doesn't know that the ticket has already been created. A timeout means that a response was not received, not that the operation failed. Therefore, the agent repeats the request without checking whether the first operation was completed. And now we have two tickets, even though the agent intended to create only one. So, in Undo Bench, naive retries resulted in duplicate effects in 54% of such trials. This is why we need to distinguish between a failed response and a failed operation.
</details>

**Tanmay**: 现在，故障所处的阶段也会改变响应。我的意思是，恢复也取决于故障何时发生。在发生变更（mutation）之前，重试通常是安全的，因为什么都没有改变。但在变更进行期间，系统可能已经被部分修改，所以我们需要检查其状态。而在变更发生之后，即便确认信息丢失，操作可能已经被记录下来。正如我们刚才所见，重试可能会产生重复。因此，根据故障阶段的不同，我们需要不同的恢复策略。

<details><summary>Original English</summary>
**Tanmay**: Now the failure phase also changes the response. I mean, recovery also depends on when the failure occurred. Before mutation, retrying is usually safe because nothing has changed. But during the mutation, the system could have been partially changed, so we need to check its state. And after the mutation, the operation could be recorded even if the confirmation was lost. As we just saw, retrying can create duplicates. So, we need different recovery strategies depending on the failure phase.
</details>

### Git Revert 的局限与 Evo-Undo 的状态见证机制

**Tanmay**: 那么，为什么我们不能直接使用 Git revert 呢？Git 可以回退对仓库的修改，但代码智能体还会改变它们的执行状态，包括工具注册表、中间件和配置。它们还可能引发外部效应，例如部署或数据库写入。因此，Git revert 无法撤销所有这些改变。恢复机制应当与智能体所产生的效应类型相匹配。当代码智能体开始改变它们自身的执行环境（也就是我们所说的智能体的“刚性/配置环境”）时，这一点变得尤为重要。这包括提示词、工具、中间件、事件监听器、资源和路由配置。此类更改可以提升智能体的性能，但也可能使恢复变得更加困难。换句话说，智能体可能会变得能力更强，但与此同时可恢复性却变差了。这就是为什么撤销一个操作需要的不仅仅是一条逆向命令。

<details><summary>Original English</summary>
**Tanmay**: Now, why can't we just use Git revert? Git can revert changes to the repository, but coding agents also change their execution state, including tool registries, middleware, and configurations. They can also cause external effects, such as deployments or database writes. Therefore, Git revert does not undo all these changes. The recovery mechanism should match the type of effect created by the agent. And this becomes especially important when coding agents start to change their own execution environment, or what we call the “rigidity” of the agent. This includes prompts, tools, middleware, event listeners, resources, and routing configurations. Such changes can improve agent performance, but they can also make recovery more difficult. In other words, an agent can become more capable, but at the same time less recoverable. And that's why undoing an action requires more than just a reverse command.
</details>

**Tanmay**: 如今，撤销一项更改并不总是像执行逆向命令那么简单。假设智能体将等待时间从 30 改为 60。要撤销此更改，它需要知道原始值是 30。这就是为什么 Evo undo 在应用变更之前会捕获先前状态的见证（witness）。该见证为恢复原始状态提供了信息，并用于进一步验证恢复是否真正奏效。

<details><summary>Original English</summary>
**Tanmay**: Now, undoing a change isn't always as simple as executing the reverse command. Suppose an agent changes the wait time from 30 to 60. To undo this change, it needs to know that the original value was 30. This is why Evo undo captures a witness of the previous state before applying the mutation. And this witness provides information for restoring the original state and further verifying that the restoration actually worked.
</details>

**Tanmay**: 现在问题来了：高级配置失败的频率有多高？在 Evo undo 中，我们评估了 600 个演进任务。其中 478 个任务实现了能力提升，但这些改进中有 197 个存在恢复缺陷。这大约占到了能力提升成功案例的 42%。因此，这里的核心启示在于，变更可以提高智能体的能力，但可能会使系统无法可靠恢复。

<details><summary>Original English</summary>
**Tanmay**: Now the question arises: how often do advanced configurations fail? So, in Evo undo we have evaluated 600 evolution tasks. Of these, 478 resulted in improved capabilities, but 197 of these improvements had recovery defects. This is about 42% of cases of successful improvement of capabilities. So, the key takeaway here is that a mutation can improve an agent's capabilities but leave the system incapable of reliable recovery.
</details>

### 恢复的两大瓶颈与扩充恢复语言的效果

**Tanmay**: 现在我们可以说说为什么“请撤销”这样的请求不起作用了。很自然地，我们想利用提示词对智能体说：“嘿，你能把所有这些恢复错误修好吗？”我们测试了四种验证器引导的修复策略，但在原本的恢复语言范围内，没有一种能修复这 197 个自然发生的故障。问题不一定出在智能体的推理能力上。在某些情况下，智能体缺乏关于初始状态的准确信息；在另一些情况下，恢复语言无法表达撤销该链条所需的操作。因此，我们分别对这两个局限性展开了调查。

<details><summary>Original English</summary>
**Tanmay**: Now we can say why the request "please undo" didn't work. So naturally, we wanted to use the prompts and tell the agent, "Hey, could you just fix all these recovery errors?" We tested four verifier-guided remediation strategies, but within the original recovery language, none of them fixed 197 natural failures. The problem wasn't necessarily the agent's reasoning. In some cases, the agent lacked accurate information about the initial state. In others, the recovery language could not express the operation required to undo the chain. Therefore, we investigated these two limitations separately.
</details>

**Tanmay**: 也就是两个“瓶颈”。第一个是状态条件的合理性依据，第二个是恢复的表达能力。当我们提供关于更改了什么以及在何处发生更改的精确信息时，恢复情况从 48 例中的 0 例提升到了 38 例。第二个是恢复工具的表达能力。当我们实现更丰富的撤销操作时，恢复情况大幅提升，从 143 例中的 0 例提升到了 142 例。这些结果来自两个不同的实验子集，但它们共同说明了为什么恢复既需要准确的状态信息，又需要执行必要撤销操作的能力。

<details><summary>Original English</summary>
**Tanmay**: So, two "bottlenecks". The first is the justification of the condition, and the second is the expressiveness of the recovery. When we provided precise information about what had changed and where, recovery improved from 0 to 38 out of 48 cases. The second is the expressiveness of the recovery tools. So, when we implemented richer undo operations, recovery improved significantly from 0 to 142 cases out of 143. These results are from two different experimental subsets, but together they show why recovery requires both accurate state information and the ability to perform the necessary undo operation.
</details>

**Tanmay**: 现在我们面临的问题是，更好的取消机制是否能够挽救失败的变更？那么，如果我们赋予智能体更强大的恢复能力，会发生什么呢？使用原有的恢复语言，我们无法恢复 197 个需要恢复的变更中的任何一个；但在扩充了这一语言之后，我们在 197 例中成功恢复了 180 例。这大约是 92%。结果，允许采纳的改进数量从 600 个任务中的 281 个增加到了 461 个。这带来了 30 个百分点的提升，这也引出了下一个问题：我们如何将这些恢复检查构建到智能体的演进过程中？现在我将发言权交给 Dolly，由她来讲解 Evo-Undo 算法。

<details><summary>Original English</summary>
**Tanmay**: Now we have the question of whether a better cancellation mechanism can rescue failed mutations. So what happens if we give the agent better recovery capabilities? With the original recovery language, we were unable to recover any of the 197 mutations that needed recovery, but after expanding this language, we successfully recovered 180 cases out of 197. That's about 92%. As a result, the number of allowable improvements increased from 281 to 461 out of 600 tasks. That's a 30 percentage point improvement, and that brings us to the next question. How do we build these recovery checks into the agent evolution process? Now I'll turn the floor over to Dolly to talk about the Evo-Undo algorithm.
</details>

### Evo-Undo 算法架构与执行流程

**Dolly**: 好的。谢谢你，Tanmay。那么，让我们来了解 Evo-Undo 究竟是如何工作的。首先我们从智能体开始，或者更确切地说，由智能体自行启动。智能体结合当前状态、效应契约以及恢复计划来处理变更。在应用变更之前，我们会捕获代表初始状态的状态见证。而在那之前，在测试环境中的测试阶段，智能体将应用该变更并执行恢复计划。独立的验证器也会检查原始状态是否已恢复。如果变更根据用户的标准提升了能力，并且通过了恢复检查，智能体就会接受这些更改。否则，智能体尝试纠正这种情况，或者验证器完全拒绝该变更。因此，弹性成为了准入决策的一部分，而不是我们在部署 AI 智能体之后才去进行战略规划的事情。

<details><summary>Original English</summary>
**Dolly**: OK. Thank you, Tanmay. Well, let's get to how Evo-Undo actually works. So, first we will start with the agent, or rather, the agent will start himself. The agent processes the mutation taking into account the current state, the effects contract, and the recovery plan. And before applying the mutation, we capture a state witness that represents the initial state. And even before that, during testing in the test environment, the agent will apply the mutation and execute the recovery plan. The independent verifier will also check whether the original state has been restored. If the mutation improves the capabilities according to the user's criteria and passes the recovery check, the agent accepts the changes. Otherwise, the agent tries to correct the situation or the verifier rejects the mutation completely. Thus, resiliency becomes part of the admission decision, rather than something we strategically plan for after the AI agent is deployed.
</details>

**Dolly**: 好的，谢谢。接下来我们将结合 Tanmay 之前解释的示例来进行说明。让我演示一下在实践中将计时器从 30 更改为 60 的示例会是怎样的。我们从初始状态开始，这是一个简单的示例，我们的智能体具有为 30 的时间值。在更改任何内容之前，Evo undo 首先读取初始值。然后它将其存储下来，将初始值作为状态见证捕获。我们确切地知道需要恢复什么，如果必须这样做，我们将确切知道什么状态是真实的，以便能够恢复到该状态。紧接着，智能体进行变更。现在智能体按照我们的要求将等待时间从 30 更改为 60。如果需要恢复，undo 会使用保存的见证将超时时间恢复为 60。现在，独立的验证器也会确认恢复后的值与原始值匹配。因此，恢复不单单因为执行了撤销命令就被视为成功，验证器还会检查接收到的状态，以确保我们确实恢复到了所需的状态。

<details><summary>Original English</summary>
**Dolly**: Okay, thank you. Next, we will go through how Tanmay already explained with an example. Let me demonstrate what that example would look like in practice with the timer changing from 30 to 60. So, let's start with the initial state, a simple example where our agent has a time value of 30. Before changing anything, Evo undo first reads the initial value. And then it stores, it captures the initial value as a state witness. We know exactly what needs to be restored, if we have to do it, we will know exactly what state is real so we can return to it. Now the agent, therefore, the mutation follows. Now the agent changes the wait time from 30 to 60, as we request. And if a restore is needed, undo uses the saved witness to restore the timeout to 60. Now an independent verifier will also confirm that the restored value matches the original. So, a restore is not considered successful simply because the undo command was executed, the verifier also checks the received state to make sure we are indeed performing a restore to the desired state.
</details>

### 恢复策略分类与总结

**Dolly**: 那么，现在出现了一个更重要的问题。我们武器库中有了这种恢复选项，我们是否应该不加区分地对所有故障都应用该恢复机制呢？当然不是。并非每个故障都能以同样的方式修复。如果什么都没有改变，如果系统中没有任何改变，我们只希望它能恢复，我们只希望它能安全地重试。我们希望智能体只需再次尝试，努力达到我们需要的状态。但是，如果我们有初始状态，我们可以将其恢复；但如果外部操作已经被记录下来，我们将需要一个补偿机制、一种补偿性操作来消除其影响。而如果我们无法恢复、无法验证恢复的安全性，或者验证器拒绝了恢复，那么智能体应当停下来并将其上报到更高层级。正确的响应绝对取决于实际发生了什么，以及哪些可以安全撤销，哪些不能。

<details><summary>Original English</summary>
**Dolly**: Well, now a more important question arises. So, we have this recovery option in our arsenal. Should we use it evenly and apply the recovery mechanism to all failures? Well, of course not. Not every failure can be fixed in the same way. If nothing has changed, then it's just, if nothing has changed in the system, we would just like it to recover, we would just like it to retry safely. We would like the agent to simply try again and try to reach the state we need. However, if we have an initial state, we can restore it, but if the external action has already been recorded, we will need a compensation mechanism, a compensatory action, to cancel its effect. And if we cannot restore, cannot verify the safety of the restoration, or the verifier rejected the restoration, then the agent should stop and pass it on to a higher level. The right response definitely depends on what actually happened and what can be safely undone and what cannot.
</details>

**Dolly**: 这几乎带我来到了最后一张幻灯片，在此我们总结关于两项研究工作的一切：UndoBench 和 EvoUndo。核心结论如下：第一，UndoBench 表明成功完成任务并不总能保证其能够成功恢复。第二，Evo undo 算法提供了一个结构化的流程：锁定初始状态、应用变更、对恢复进行独立验证以及实施还原。因此，Evo undo 算法完全按照我们的设想运行。第三，只有当功能性和可恢复性的要求同时得到满足时，我们才应允许自我演进式的更改。归根结底，在赋予智能体更多自主权的同时，我们也应当为它们提供更稳健的手段来从自身的操作中恢复。好的。最后，希望大家还记得开头提到的那个智能体。他当时正在寻找“取消”按钮。现在，他拥有了这个按钮。我们通过研究项目 Evo undo 开始构建这一能力。大家可以在 GitHub 上的代码仓库中查看它。您可以扫描屏幕上的二维码访问该页面。我们的目标是使恢复成为 AI 智能体的一项基础能力，让它们不仅能执行操作，还能在出现差错时进行恢复。非常感谢大家。

<details><summary>Original English</summary>
**Dolly**: This brings me almost to the last slide, where we summarize everything about our two works: UndoBench and EvoUndo. So, the key takeaways here are: first, UndoBench shows successful task completion. UndoBench shows that successfully completing a task does not always guarantee its successful recovery. Second, the Evo undo algorithm provides a structured process: fixing the initial state, applying the mutation, independent verification of the recovery, and restoration. So, the Evo undo algorithm works exactly as we intended. Third, we should allow self-evolutionary changes only when the requirements for both functionality and recoverability are met. Ultimately, by giving agents more autonomy, we should also provide them with more robust ways to recover from their actions. OK. And finally, I hope you remember the agent from the beginning. He was looking for the "cancel" button. Well, now he has it. We started building this capability through our research project Evo undo. You can check it out in the repository on GitHub. You can scan the QR code on the screen to go to the page. Our goal is to make recovery a fundamental capability of AI agents, so that they can not only perform an action, but also recover if something goes wrong. Thank you very much.
</details>