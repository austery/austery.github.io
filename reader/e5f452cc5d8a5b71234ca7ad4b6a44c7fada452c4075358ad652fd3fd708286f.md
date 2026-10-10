---
author: AI Engineer
date: '2026-07-25'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Ib5t2RLtxvM
speaker: AI Engineer
tags:
  - agent-evaluation
  - simulation-environment
  - benchmark-framework
  - observability
title: 从轨迹到模拟：智能体评估与优化的新范式
summary: Snorkel AI 平台团队负责人 Rustem Feyzkhanov 探讨了将生产环境中的智能体轨迹（Traces）转化为离线模拟（Simulations）的工程实践。通过构建贴近真实业务的私有基准测试，团队能够引入成本、延迟等多维指标，建立可靠的发布门禁与持续优化闭环。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Snorkel AI
  - GitHub
  - Arize
products_models: []
media_books: []
status: evergreen
---
### 生产级基准测试的必要性与局限性

在当今的 AI 应用开发中，每个企业都需要建立专属的基准测试，这是可靠地评估、发布和改进**智能体**（AI Agent: 能够自主规划并使用工具执行复杂任务的 AI 系统）的唯一途径。基准测试必须尽可能贴近生产环境，模拟真实的工具、API 服务、企业策略和工作流。此外，基准测试不能是静态的，而应当是利用生产环境中的**运行轨迹**（Traces: 记录 Agent 输入、中间动作、工具调用及输出的完整日志）不断进行动态填充的数据集。传统的运行轨迹虽然在定位生产环境中的单点失败时非常有用，但却难以用于测试不同的 Agent 变体。这是因为生产环境中的数据库状态、API 响应和工具版本都在不断变化，使得 A/B 测试难以保证实验的可重复性，无法进行“苹果与苹果”的公平对比。

为了解决这一问题，我们将运行轨迹转化为离线模拟。**离线模拟**（Offline Simulation: 在受控的沙盒环境中复现并重跑 Agent 执行过程的技术）将不确定的生产运行记录转变为可重复的科学实验。我们可以离线运行不同的 Agent 配置，并在并行环境中对比成功率之外的多维指标，如调用成本、延迟和重试次数。这正是 Snorkel AI 作为一家数据服务公司所擅长的工作，我们每月运行数百万次模拟，将基准测试的构建提升为一种系统工程。

虽然市面上存在诸如 **SweepBench**（专注于自动解决 GitHub 问题）、**TerminalBench**（专注于终端命令行环境）或 **Co-Bench**（专注于计算机使用 Agent）等公共基准测试，但它们大多仅局限于特定领域。企业需要关注的是自身的特定业务域、所用工具和内部合规策略。正如行业共识所言，公共基准测试用于建立先验认知和技术方向，而私有基准测试则是决定产品能否上线的最终依据。

<details>
<summary>Original English Source</summary>

>> Okay. Oh, yeah. Thanks everyone for coming. And I know this is the last session before lunch. So, thanks for staying here. Let's make it smooth and with good vibes. Just as that said. And thanks that for introduction. And for inviting me. So, yeah. My name is Rustam. I'm leading AI platform team uh at Snorkel. And uh today I want to tell you how to turn agent traces into agent simulations and why this uh becomes the next stage for agent evaluations.

So, three main things that I want you to take away from my talk is uh every company needs a benchmark. It's the only way to reliably evaluate, release, and improve your agents. It has to be as close to production as possible. Uh it has to mimic your real tools, real API services, policies, and workflows. And finally, it has to be part of your agentic life cycle. It's not a static benchmark. It's a constantly populated data set from your production traces.

So, why is Snorkel AI giving this talk? We are uh data as a service company and we uh basically selling uh benchmarks. And we're producing benchmarks at scale. And for us, benchmark construction is an engineering discipline. We run millions of agent simulations per month. And uh we learned how to do like uh environment built at scale. Working using both agents uh and subject matter experts to build reliable benchmarks that are close to production and uh specific domains.

So, a lot of the time when people say about agent evaluation, they're focused on traces. And traces are very useful. The usual traces like you can see an example on the screen. It basically shows, "Okay, here is the input prompt. Here are the actions that agent took, and here is the agent output." And then relation can analyze it and and say, "Okay, was agent successful or not? Was there any edge case?" Uh so, it is useful to find failures in production, but it's hard to test different variants. You can run AB testing, and that's one way of checking different agent configurations, but it's hard to make sure that everything is repeatable because you will get different database state, different tool versions, and so on. So, never fully compare apples to apples.

Offline simulation turns traces into repeatable experiments. Now you take production traces, you construct tasks, and then you can run simulation benchmark um with different agent configuration offline. And you can compare agents using different metrics, not just success rate, but cost, latency, and retries. And you can run those in parallel.

But you can ask, "Okay, but why do we need it? Like we already have public benchmarks." The challenge with public benchmarks is that usually they are focused on a very specific domains. For example, SweepBench is focused on like uh fixing GitHub issues, TerminalBench will focus on agent running in terminal, and Co-Bench will focus on computer use agent. In your case, you want your benchmark to be focused on your company's domain both from perspective of use cases and in terms of tooling that your agent has, whether it follows the policies that your company uses, and whether you get full production environment. Basically, public benchmark is useful to orient and build your prior, but your private benchmark is useful to ship. And a lot of the time public benchmarks they're specifically focused on pass rate. Every time you see new model release, you see performance like pass rate on different benchmarks. Which makes sense because it tells us like about the frontier of how good is the like new model. But when you release agent to production, you also care about more metrics. You care about cost for solving the task. You care about latency. You care about number of retries. And by running evaluation offline with in simulations, you can effectively compare apples to apples and and iterate on agent.

</details>

### 离线模拟的架构设计与环境构建

在构建私有基准测试时，我们需要评估整个智能体系统的完整栈（不仅仅是底层的模型性能，还包括 Prompt、技能、工具等）。因此，模拟环境需要通过解耦评估器和外部环境来确保多次运行的一致性。从基准测试的生命周期来看，它通常有三个阶段：首先是**确保可行性**（Make it work：通过 Trace 调试、处理边界情况、选择最优模型）；其次是**确保正确性**（Make it right：将其作为发布门禁，防止迭代引入退化）；最后是**优化性能**（Optimize it：降低成本和延迟，甚至微调小模型以匹配大模型的表现）。

在具体实现上，目前业界流行使用 **Harbor 格式**（由 TerminalBench 团队开发的基准测试数据格式）来组织任务，主要包含三个核心文件集合：
* `instruction.md`：Agent 可见的任务指令；
* 环境配置文件：定义运行环境的 Dockerfile 或 Docker Compose 文件；
* Oracle 解决方案与验证器：Agent 不可见的参考方案和评估脚本。

其中，**验证源**（Oracle: 用于验证任务本身是否可解的标准参考路径或黄金答案）在任务构建中至关重要，如果 Oracle 无法成功执行，说明任务本身设计有误。为了让 Agent 确信自己是在真实生产环境中运行，模拟环境应当是一个“微缩版生产环境”。这意味着我们不能在模拟中接入真实用户，而是必须使用 LLM 并赋予其特定的提示词与上下文来**模拟用户行为**（Simulated Users）。此外，类似于微服务中的 **边车模式**（Sidecar Pattern: 将辅助功能与主应用容器分离部署的设计模式），我们可以将真实的 API 服务、数据库和 MCP 工具部署在边车容器中，仅为 Agent 提供一个轻量级主运行环境。针对耗时数小时的**长流程任务**（Long Horizon Tasks），则需要将任务分解为包含独立 Prompt 与验证器的多个中间步骤，并在 Agent 早期失败时及时终止模拟，从而大幅节省评估成本。

在验证环节，传统的测试仅仅验证最终输出。但在复杂的 Agent 模拟中，**验证器**（Verifiers）需要对环境的最终状态、API 调用轨迹以及生成的制品进行综合分析。常用的验证方式包括**确定性校验**（Deterministic Checks: 针对输出文件或接口调用进行精确比对）和 **LLM 裁判**（LLM-as-a-Judge: 利用大语言模型评估复杂交互轨迹与规划合理性）。此外，在自动化验证存在分歧的边缘案例中，引入**领域专家**（Subject Matter Expert）进行人工复核，对于微调负责评审的 Agent 具有不可替代的价值。

<details>
<summary>Original English Source</summary>

In this case, you can test the full stack of your agent. You're not just checking, okay, is model one is one model performs better than the other model. You check even like thinking talk like thinking level. You can change the prompt. You can tune the full hardness and skills tools available to agent because in your production, you don't care about the model, you care about the full system. And here you can configure and test the full system while keeping environment and evaluators the same between runs.

And that raise the point about like what benchmark is in this case. Because first of all, you can use it to first release the agent. You can make sure that it works. You can handle edge cases well. You can select the optimal model, and you can debug the traces. That's how you make sure that it works. Next, you can make it right. You can put it as a release gate for your agent and verify that any change to agent stack in didn't reduce regression suddenly. And iterate on hardness. And finally, you can optimize it. You can tune it for better cost or latency. Or you can use the traces to even do error training. Uh later I will say I will share link to our website where we have example how we used simulation environments to fine-tune small plan model to match performance of large plan model for specific tasks. Here effectively, that becomes like trifecta of use cases. Like for you, benchmark becomes part part of agent evaluation, becomes part of integration test for agent for release, and it becomes also training set for agent to improve it.

So, I hope I explained why you need benchmark. So, now let's take a look like how can you actually construct it at scale for your company? Like what is the anatomy of the benchmark task? If you take a step back, like what is the sequence of running the benchmark? It's straightforward. Agent gets input prompt, it interacts with environment trying to solve the task with APIs, MCP tools, database, files. Then it produces the output, trace, final state of the environment, and artifacts, basically output files. Then we run verifiers, and we can produce the metrics how was agent able to solve the task, how well did it do, and so on.

The important second part of the task is Oracle. When Oracle solution runs, it runs through the whole sequence, but just instead of running the real agent, it runs Oracle, and it and when we construct Oracle ourselves to make sure that task is solvable in the first place. Because if it's not solvable, agent won't be able to solve it. So, Oracle is important part of the task.

If we look at the anatomy of the like of the benchmark task, how it looks in terms of files, we can look at one of the most popular formats nowadays, Harbor format, which was done by the same team who uh maintains Terminal Bench. In this case, basically, it's just three set of files. So, basically, what agent sees and interacts with, instruction.md, classic markdown file, environment, which you can see Dockerfile, could be Docker Compose in case you have multiple Docker containers. You have something that agent doesn't see, which are which is Oracle solution and verifiers. And finally, you have some metadata. It may uh look very straightforward. Yeah, I'm saying like, "Okay, simulation environment is just Dockerfile and a bunch of stuff." But, it is useful because now you have repeatable way of running experiments in agent simulation.

So, now let's dive deeper into main parts of benchmark. First is environment. The main challenge with the environment is that effectively it has to be mini production, but you don't want to run full production for every experiment. So, you want to make sure that uh your database, API service, tools, and files match production, just as like previous speaker mentioned like that you don't want your agent to know that it's running within simulation. So, it has to be real. One thing, though, you cannot put real user in your simulation task. So, you can simulate the user. In this case, that becomes effectively LLM with its own prompt, which with additional context that can mimic human behavior and interaction with your system. So, in the port system that all these things exist in the environment, and verifiers just interact with the environment afterwards.

There are certain patterns to make sure that you can organize environment this way. And think about it as like how you construct integration tests. Basically, how you give effectively diff environment to your agent. You don't run the full production database. You have a certain snapshot. You can run side containers sidecars in this case. So, your uh agent runs in one main uh environment, but there are other containers which contain API services, databases, MCP tools, and so on, available to your agent. You don't need to have like full production API services, you can mock them. I already mentioned simulated users. Uh and uh one important piece here is multi-step to handle long horizon task, if your agent needs to handle task that span hours. You want to ensure that you have intermediate like steps, and for each step you have separate prompt, separate verifiers, and uh you can uh finish simulation early if you see agent failing. And basically that enables you to simulate long-running horizon tasks.

So, next part is verifiers. Like in traditional sense, usually when people speak about verifiers, you just verify the output. You get agent output, you verify it, that's it. That's why, let's say, how coding works. It's like we just verify the output code. We test, and so on. Here it's more complex. The way agent interacts with the simulation, we get a lot of different data. We get the world, basically how environment changed in the final environment state. What is your database state? What are the API responses? What were user replies? And so on. And your verifier analyzes final state, trace, and artifacts.

So, how can you analyze it? Effectively, there are multiple ways to do it. You can have deterministic checks. Basically, uh and that can work really well for things like final output or tool calls, where like it's very easy to check whether it was correct or not. It Sometimes you can use LLM as a judge, or even harness as a judge, or agent as a judge to evaluate basically whether the uh trace quality was successful, whether um planning of the agent was correct, and so on. In this case, it really depends on the use case. So, you can use one or another or both depending on what's what works better. And finally, it's important to keep in mind that you can use sub- uh subject matter expert to review some of the traces, some of the outputs. Not for everything, but for cases where you see discrepancy in agent behavior and where you want human involvement.

</details>

### 智能体发布流程与持续优化的双环回路

在实际运行中，模拟基准测试的开发本身就是一门工程艺术，必须防范诸如 **奖励黑客行为**（Reward Hacking: Agent 发现并利用模拟环境或评测指标的漏洞来获取高分，而非真正解决目标问题）等副作用。为了保障基准测试的稳定性，应当像对待生产代码一样对待基准测试，为其建立独立的 CI 流程（验证依赖锁定、基础镜像一致性，并定期自动运行 Oracle 以确保任务依然可解）。

在修复 Agent 缺陷时，业界存在一个普遍的**反面模式**（Anti-Pattern），即过度依赖在 Prompt 中堆砌规约（例如频繁加入“绝对不要做某事”或“只能做某事”的指令）。这种做法会导致 **提示词过载**（Prompt Overload: Prompt 承载过多规则导致模型处理核心业务的能力下降），增加模型上下文负担并降低其泛化能力。在模拟体系的支撑下，开发者能够准确定位问题，并将修复策略沉淀到更合理的组件中：例如将缺失的业务流程封装为独立的**技能**（Skills），或者通过**结构化输出**（Structured Output）固化输出格式。

当 Agent 上线后，系统将围绕两个闭环进行演进：
1. **基准测试扩容环**：通过诸如 **Arize**（一款机器学习可观测性平台）等工具收集生产环境中的失败轨迹，并将其提炼为新的基准测试案例。
2. **模拟运行网关环**：在发布新版本或新配置时，运行完整的离线模拟测试，达到指标阈值后方能获准发布。

在问答环节中，Rustem Feyzkhanov 针对测试数据集的划分给出了建议。类似于传统机器学习，建议对任务数据集进行 80% 训练集与 20% 验证集的划分，确保评估用例对 Agent 保持盲测状态。在用例覆盖度上，基准测试应当包含“常规任务”（Happy Path）与各类“边界用例”（Edge Cases），如模拟外部数据库宕机或第三方 API 响应失败，以此检验 Agent 在异常环境下的鲁棒性。针对自动验证与人工评审的分歧，通过专家反馈微调评审 Agent，可以进一步提升基准测试本身的评测效能。

<details>
<summary>Original English Source</summary>

So, final piece, how can we kind of organize everything together as part of agent release and agent improvement process? So, can we just start? Not just yet. Can something go wrong with benchmark task? 100%. Agent can try to reward hack simulation environment because it can understand that it's in simulation and it can hack it. Task could be too simple and like our verifiers could be too broad and in this case agent will always pass even if it does something incorrectly. It could be that agent always fail because verifiers are incorrect. Or it could be that agents not perform in a stable way and like you have high variation of agent success.

So, all of these are effectively edge cases that you need to catch during your benchmark development because benchmark development is an art on its own. We saw already like hundreds of benchmarks appear over the course of last years, but this is something that the card culture and engineering discipline that needs to be built in each uh engineering team that needs to ship AI agents to production. Because as you saw, effectively benchmark is software. It's code. It's files. You need to treat it as such. You need to have a separate CI pipeline for it. E- And you can check pretty obvious things like for example, making sure that all dependencies are pinned or like your base image is correct or you don't have any missing fixtures, then you can run Oracle uh solution and make sure that it passes. Or like if you don't run Oracle that verifies fail, you can run several agent runs uh on the task and verify that okay, it is solvable and it is hard for agent. You can tag the task whether it's simple, medium, or hard depending on how much time how many times the agent is successful. And finally, you can approve it to make it part of your benchmark.

In this case, the process for improving agent becomes straightforward. You establish baseline in like on your benchmark, you run evaluation data set, you see the failures where it doesn't perform well, you change one thing, you rerun experiment and where you can use something like Arize to record your experiments. And then once you fix it, you rerun the full experimentation again. And then you can finally release to production.

What it unlocks is to make sure that you fix issues correctly. There is a bit of an anti-pattern in the industry where like folks try to fix things in the prompt. And they populate the prompt with things like, "Never do this or only do that. Never output this critical that." Which is one way of handling it for sure, but with simulation, you control the full stack. You can evaluate the full stack. And you can make sure that fix lives in the correct place. You don't push everything to the prompt. You fix hardness if you want if you have context overload. Or you can if there is a missing procedure, you put it into skill. Or like if you need to have specific output schema, you put it as part of structured output.

So, once agent is in production, effectively, you will have two loops. One loop for benchmark expansion. You take uh, observability traces uh, traces from observability basically using something like a rise. You record failures and use failures to build your benchmark further. Then you have simulation runner that will run experiments on your on extended benchmark on a new or on new agent config. Uh, we'll record these experiments. Then you can use it for as a release gate whether, uh, agent performs significantly well and finally release it to production. Uh, in this case it's important that you have system like it's important to under- to make sure that your observability piece and experimentation piece are connected. Because they're part they're two sides of the same coin.

Um, so yeah, to summarize my talk, everyone needs every company needs a benchmark. Traces are useful for like the finding edge cases in production, but simulation helps to, uh, test what would happen. And finally, uh, you want, uh, your, um, benchmark to be be part of your, uh, agent ops, uh, loop. Thank you very much for for your time and, uh, I think maybe I will have answer for one question, but will be happy to answer any questions outside and please check our booth, uh, if you have any questions about benchmarks.

>> [applause]

>> All right. A couple questions. All right.

>> A great talk. I have a question about structuring the benchmark. How many examples you should include ideally? And do you split them into, uh, like a train test split? If so, like how do you recommend structuring examples, um, across those two splits?

>> Great question. So, uh, the question was basically how can we structure to for training and validation? And just as previous speakers uh shared, basically they also had a pattern of like having train validation split. This is very close to traditional machine learning where we want to have standalone data set that agent didn't see. But basically where we can verify agent config. I think the classic approach applies when like you want to have 80/20%. Always depends on the use case. But uh you do want to have a standout data set that agent didn't see through the experimentation process.

>> Awesome. Next question.

>> Um so when you create the benchmarks, um what data do you include in the benchmark? Do you include production runs that you've handpicked into the benchmark? Or if your agent is not yet in production, do you create uh data sets or problems to solve for the agent in the benchmark? And if you're if you're like handpicking problems for the agent to solve, um how do you make sure you have like enough coverage uh similar to what you'd see in production?

>> Great question. So the question is how to ensure coverage and distribution of benchmark is a very important piece. So effectively you want to keep keep make sure like you have both. You have bread and butter use cases, basically covering all main use cases that work, but also making sure you have edge cases. Basically how you can make sure like your agent can handle edge case when tools fail or if like there is problem with database and so on. So you want to have both uh it basically think about it as integration test. You you have happy path, but you also have edge cases.

>> Would you simulate agent with LLMs or would you create hand-crafted business?

>> Yeah, uh great question. Basically similar to us handcrafting, uh I think basically I mean people use agents to write code. So a lot of things here can be automated. So the what is handcrafted kind of changes. Like the the most important piece that you can provide is like the build environment once and then build the context uh for basically that mimics your production.

>> Um you mentioned sometimes you use LLM or sometimes use human expert to build verifiers. Can you elaborate on that? What's the best practice over there?

>> Great question. So, in our case basically, we have a lot of subject matter experts, so we do things at scale. So, the important piece here is to you don't need subject matter experts to review everything, but you specifically want to find cases where there's disagreement between agent and different verifiers. If you you think that basically task was supposed to be solved, but agent somehow marks it as like not solved correctly or like it marks that trace wasn't optimal enough. And this is where you want to have subject matter expert that can basically tune the agent that does the review.

</details>