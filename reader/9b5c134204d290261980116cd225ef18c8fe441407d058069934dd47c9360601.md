---
author: AI Engineer
date: '2026-10-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=F0TNSmbo5hE
speaker: AI Engineer
tags:
  - agentic-workflow
  - llm-evaluation
  - observability
  - automated-debugging
  - clustering
title: 闭环软件开发生命周期：从链路追踪到智能体自主纠错
summary: Arize AI 联合创始人 Laurie Voss 深入剖析了面向生产级 AI Agent 的工程范式演进。针对 Agent 的非确定性与海量追踪数据的分析瓶颈，提出结合聚类模式识别与自主纠错闭环的下一代观测体系，推动软件开发生命周期从人工审查走向模型自愈。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Laurie Voss
companies_orgs:
  - Arize AI
products_models:
  - Claude Code
media_books: []
status: evergreen
---
### 非确定性挑战：传统监控向智能体观测的演进

在构建传统软件系统时，工程师依赖明确的控制流与单元测试来验证系统行为；哪怕出现边缘情况，代码的确定性逻辑也保证了故障路径的可复现性。然而在**智能体应用**（Agentic Applications: 具备自主规划、多步决策与外部工具调用能力的 AI 系统）进入生产环境后，这一开发假设被彻底颠覆。智能体具有天然的**非确定性**（Non-determinism: 相同输入在不同运行中产生不同推理路径与输出），它们在执行任务时包含自主决策链条，即使针对完全相同的用户输入，不仅最终生成的结果可能截然不同，其中间调用的工具链路与推理轨迹也各不相同。

面对这种复杂系统，生产环境的调试无法再依赖离线复现，而是必须依赖**追踪分析**（Tracing: 完整记录智能体输入、Prompt、大模型响应及工具调用的调用链日志）。上午的基础课程（Session 101）展示了如何搭建观测平台、捕获单条链路追踪（Trace）并进行人工审查与单次评估。然而，当应用推向互联网规模的生产流量时，工程师立即遭遇了“追踪过载”危机。如果系统每天产生成千上万甚至数百万条执行链路，逐条检查单步执行不仅不具备可扩展性，更会让团队迷失在海量噪声中，无法辨别系统性的结构性失效。

<details>
<summary>Original English Source</summary>

OK. Hello everyone. Thank you for coming back. Who among you was at session 101 this morning? OK. So, I didn't scare everyone. Thank you very much. Uh, those instructions have been on the screen for the last 10 minutes. I really hope you've done them, because the Wi-Fi here is terrible, so cloning that repository takes a long time. Uh-huh. If not, uh, these instructions will appear on the screen again, and you will have another chance to follow them. Uh, but let's get started. This is "Vice Production 201". We're going to talk about how we automatically close the software development lifecycle loop. We are Arize AI. We are a leading platform for surveillance, oversight, monitoring and evaluation. Don't try to say both of these words at the same time. It doesn't turn out very well. Uh, this is the slide that everyone shows to say, "Hey, we're really big. We're really important. You should pay attention to us." That's right. We are very big. We are very important. Many people use us. This is great. Uh, and this is the last part of the advertising. You can use any monitoring platform for this. We hope you choose ours, but the goal of this class is to teach you where monitoring is headed. Well, and it moves towards continuous improvement. In Session 101 this morning, I covered the basics. I told you about manual operations. I told you how to do it on a small scale. Uh, how to get monitoring of your AI application, how to turn that into traces, how to turn those traces into assessments, and how to use those assessments to improve your application. Uh, and today in this session we're going to talk about how we do that in the new scale of the internet that we've found ourselves in. So, uh, I'm going to quickly, quickly review what we did this morning. If you were there, then this will be familiar to you. If you were not there, then you'll catch up. The whole reason this workshop exists is that agents are fundamentally different from traditional software engineering. When you were writing traditional code, you knew what that code was going to do. If it didn't do what you wanted it to do, you could write a test, you could run it locally, and you could reproduce it. And you could see what line of code caused it, and you could fix it. And that was fine. But even when you move to language models and simple LLM calls, you have some idea of what exactly that code will do. With agents, you have no idea. Agents are non-deterministic. Agents take several steps, make decisions, and even if they are given exactly the same input, they will not produce the same result. And even if they produce the same result, they won't necessarily follow the same path to it every time. This means that you can't test them beforehand. You have to monitor them in production. You have to observe them. You have to trace them. And then you have to evaluate those traces. So in Session 101, I showed you how to set up Arize or any tracing platform, how to instrument your application, how to get traces out of it. And then I showed you how you can look at individual traces, identify what went wrong, and then fix it. But that doesn't scale. That works when you have 10 users. It doesn't work when you have 10,000 users. Because you can't read 10,000 traces. You can't even read 100 traces. It's too much work.

</details>

---

### 从单点评估到聚类提炼：应对规模化追踪数据

为了突破人工单点检查的瓶颈，业界在过去探索的传统解决方案是引入**模型评估**（Evaluations / Evals: 利用代码或大语言模型作为裁判，自动化评估任务输出质量的方法）。通过定义明确的评估准则（如是否有幻觉、意图识别准确率、工具参数是否合法），让一个裁判模型对每一条 Trace 打出评分或布尔标签。然而，这一方案在规模化生产中迅速衍生出新的次生痛点：由于评估本身由大语言模型执行，输出的结果往往伴随着大量的自然语言定性评语，数据形态变得极其碎片化。

面对每天数以千计的评估结果与散乱评语，工程师依然被迫陷入“大海捞针”的人力筛选中。真正的解决路径在于引入高层抽象——通过对海量 Trace 的元数据、执行失败特征以及评估反馈进行**嵌入聚类**（Embedding Clustering: 将非结构化文本与调用特征映射到高维向量空间并识别聚集模式）。系统自动将孤立的错误聚合成具体的失败模式（Patterns），例如“在某些查询下向量搜索返回空结果”或“日期参数格式在跨时区调用时发生解析崩溃”。工程师不再逐一处理单条失败调用，而是直接审视聚类提炼出的高维信号，使问题诊断的颗粒度实现质的跃迁。

<details>
<summary>Original English Source</summary>

So the solution, the traditional solution, and by traditional I mean the 2025 solution, was evaluations. An evaluation is either code or, better yet, another language model that analyzes the agent's performance, examines all the traces, and determines whether they were good or bad according to your definition. The thing is that ratings come from language models, which means they are also text, and there are many of them. So now, instead of reading 10,000 traces, you're reading 10,000 evaluations. That is also not scalable. So what do you do? What you do is you cluster them. You aggregate them. You find patterns in the evaluations. You find out that, oh, 30% of my traces are failing because the model is hallucinating a tool that doesn't exist. Or 20% of my traces are failing because the user is asking in a language that the model doesn't understand. Or 10% of my traces are failing because the context window is too small. Once you have clustered the evaluations, you can start to prioritize what to fix. You don't have to fix every individual trace. You fix the pattern. You fix the root cause. And that's what we're going to talk about today: how do we go from traces to evaluations to patterns, and then—the exciting part—from patterns to automatic fixes. How do we take that pattern, give it to a coding agent, and have the coding agent write the code that fixes the problem, run the tests to make sure it fixes the problem, and then submit a pull request? That is closing the software development lifecycle loop. That is what we are here to do.

</details>

---

### 自动化闭环架构：重构代码审查与自愈信任链

在建立模式识别能力之后，完整的架构演进必然指向**闭环软件开发生命周期**（Closing the SDLC Loop: 自动化打通监控告警、问题归因、补丁生成及回归测试的全流程机制）。Arize 将这一模式产品化为 **Signal** 系统。其核心运作机制不是被动告警，而是将聚类识别出的错误模式与具体的负面调用链路打包，直接转化为**编程智能体**（Coding Agent: 能够理解代码库、修改源码并运行测试的自主 AI 辅助系统）的上下文 Prompt，驱动其自主定位代码缺陷并提交修复代码。

现场听众随即提出了一个关键的工程信任问题：“如果由智能体编写代码来修复智能体，同时还由智能体编写测试来验证测试，我们如何信任这一闭环？” 这直指软件工程的核心议题——“代码审查的消亡”。在确定性软件时代，人类通过逐行检查代码来建立安全感；但在复杂的智能体生态中，人工审查往往只能捕获语法或表面逻辑漏洞，对非确定性边界极其无能为力。真正的信任来源是**端到端评估测试套件**（End-to-End Evaluation Suites: 针对智能体行为的多维基准测试集合）：我们不应过度关注智能体内部编写了什么代码，而是通过独立的、隔离的黄金评估集（Golden Dataset）来施加确定性的验收边界。当新生成的代码能通过所有基准测试且未引发回归时，闭环自治便具备了统计学意义上的生产安全性。

<details>
<summary>Original English Source</summary>

At Arize, we built this into a product called Signal, which I'll talk about at the end. But this is not advertising. This is a demonstration of what can be done by moving to this new level of abstraction. When you go from reading traces one by one to having patterns surfaced for you, you can hand those patterns directly to an AI that knows how to write code. And that's what we're going to do in the hands-on part of this workshop. We're going to use Claude Code, Anthropic's new agentic coding tool, and we're going to give it a set of traces that show a bug in our application, and we're going to say, "Hey, Claude Code, fix this bug." And Claude Code is going to look at the traces, look at the code, figure out what's wrong, write the fix, run the tests, and show you that it works. Now, before we jump into the hands-on, I want to address a question that someone asked during the break. I can't believe you're asking this question, because it's a great question for me, because I'm giving a talk on Wednesday called "The Death of Code Review," which is the answer to your question. So I highly recommend you come to this talk. The question is, how can you trust the code written by agents who are testing your agents, and then writing code to fix your agents? How do you not end up in an infinite loop of garbage in, garbage out? And the answer is evaluations! Because the evaluation is not written by the agent that wrote the code. The evaluation is a separate standard. It is a set of tests. It is ground truth. Just like in traditional software engineering, you don't trust the developer's code just because they said it works; you run CI/CD, you run automated tests, you have linters. In the agentic world, evaluations are your CI/CD. The agent can write whatever code it wants, as long as it passes the evaluation suite. And if the evaluation suite is robust, and if it tests for hallucinations, if it tests for tool use accuracy, if it tests for latency, if it tests for user satisfaction, and the agent's code passes all of those tests, then you don't need a human to read every line of code. You can trust the result because you trust the evaluation. That is the shift from line-by-line code review to evaluation-driven development.

</details>

---

### 实战工作坊搭建：为 Claude Code 注入领域感知能力

进入实操环节，工作坊演示了如何在本地环境中运行这一闭环流水线。示例应用是一个电商客服智能体，其依赖本地工具库进行商品价格查询与类别检索。代码库中已经配置了专用的 **Agent Skills**（智能体技能扩展: 为编程工具注入针对特定项目架构、测试命令及调试规则的外部规范文件）。对于通用的开箱即用编程模型，由于不具备当前业务系统的隐式上下文，往往难以精准定位工具层与模型 Prompt 层之间的职责划分；而通过在根目录下预置规范定义，**Claude Code** 可以瞬间获知如何在隔离环境中启动沙箱、读取失败 Trace 结构，以及调用评测指令。

现场网络环境的延迟与依赖克隆问题，也生动体现了真实工程部署中的阻碍。现场演练演示了如何在终端中调起 `claude` 命令，并传递结构化的追踪报告。系统向智能体喂入了一批带有错误标记的执行追踪文件，要求模型不仅审查应用代码（如基于 OpenAI 架构的智能体调用逻辑），更要跨越到底层工具库寻找端倪。这一环境搭建的核心启发在于：智能体辅助开发不仅仅是打开一个交互式聊天窗口，而是必须建立标准化的代码-追踪交互接口，使外部观测数据能够无缝沉淀为智能体的执行上下文。

<details>
<summary>Original English Source</summary>

The repository already has the skills installed, so Oh, it's in the top-level readme file. The one you need is called Open AI agents pi. Open AI agent There is also a second folder—Open AI agents. Make sure you're in the right one. Okay, let me walk you through what's in this repo. You've got an agent built using OpenAI's Swarm or standard agent framework. It has tools: a search tool, a pricing tool, an inventory tool. It's an e-commerce assistant. And it has a set of tests. And it also has a Claude Code configuration. How many people here have used Claude Code before? Okay, a handful of you. Claude Code is a CLI tool from Anthropic. It runs in your terminal. It has access to your file system, it can run commands, it can edit files, it can read git history. It is essentially a junior engineer sitting in your terminal. But out of the box, it doesn't know anything about your specific codebase. It doesn't know how you run tests, it doesn't know your coding style, it doesn't know what libraries you use. That's why we use skills. A skill is a markdown file that gives Claude Code instructions on how to interact with a specific repository or a specific problem domain. In our repo, we've provided skills that tell Claude Code how to read Arize traces, how to interpret evaluation results, and how to run our specific evaluation suite. So when you ask Claude Code to fix a bug based on a trace, it doesn't just guess; it follows the protocol laid out in the skill. So let's run it. Open your terminal, navigate to the repo directory, make sure your virtual environment is activated, and run the command that's in the readme. If you run into issues with the Wi-Fi or API keys, raise your hand and one of our TAs will come help you. What you should see is Claude Code reading the prompt, exploring the codebase, reading the trace files that we provided in the `traces/` directory, and then starting to form a hypothesis about why the agent failed. So, a standard ready-made agent for writing code will not know this. However, when you install a repository, you install a whole set of skills. Uh, so he should know from these skills, uh, where to do it. Besides the fact that I'm in Oh, yeah. Oh, it works. Okay, that's it. Steeply. Uh This is the moment where we watch the terminal scroll and hope that the demo gods are smiling upon us.

</details>

---

### 缺陷归因与工具层修复：定位向量检索与过滤逻辑冲突

当编程智能体解析提供的 Trace 日志时，一个极其典型的 AI 应用缺陷浮出水面：用户在搜索特定价格区间的某类商品时，智能体直接反馈“未找到商品”或报错商品不存在。初级排查往往误以为是主模型产生了幻觉或 Prompt 编写不当，但深入调用栈后发现，真正的问题存在于**工具层**（Tool Layer: 提供给智能体调用的外部 API 与检索函数）的组合逻辑中。

该系统在检索商品时，同时结合了**向量搜索**（Vector Search: 基于语义相似度嵌入的非结构化检索）与**关键词分类过滤**（Keyword Category Filtering: 基于元数据的精确字段过滤）。当模型从用户自然语言中提取出价格与类别参数并传给工具时，底层的检索过滤器由于实现过于严苛或字段不匹配，导致两者的交集返回了空列表。模型由于拿不到任何检索结果，只能如实回答“没有找到该商品”。Claude Code 通过审查 Trace 中的参数传递与工具内部源码，准确识别出错误根源并不在 Prompt，而在于工具内部的过滤逻辑。随后，智能体自主编写针对性补丁，放宽过滤边界、修正类型转换，并自动重新触发评估测试，验证了该类搜索请求的成功率恢复至 100%。

<details>
<summary>Original English Source</summary>

When I tried this this morning, I only had one trace, and that trace indicated that the price was not found. So, is there a problem with the model, or is there a problem with the tool? Look at what Claude Code is doing right now. It's analyzing the trace, and it's looking at the tool definition. Here is the finding: is the product search filtering logic. Vector search and keyword category filters often return empty results when the model provides data. The correction should be on the side of the tool. Em. Exactly! The model was doing what it was supposed to do. It parsed the user's intent, extracted the query "red running shoes under $50", and called the `search_products` tool with category="shoes", color="red", max_price=50. But inside the tool, whoever wrote the search function implemented a hard boolean AND between the vector similarity search results and the metadata filters. If the vector search returned 10 items, but none of those 10 items had the exact metadata match for both "shoes" and "red" and price < 50, the result set was completely empty! Even though there were items in the database that matched. The model wasn't hallucinating; the tool was failing silently. And this is a super common failure mode in agentic systems. We blame the LLM for being dumb or hallucinating, when in reality, the tools we gave the LLM are brittle, poorly documented, or buggy. Claude Code identified that the fix shouldn't be to change the prompt. You don't fix this by telling the LLM "please try harder to search." You fix the Python code inside `tools/search.py`. And look at what Claude Code just did: it modified the filter logic to do hybrid search properly—it filters first in SQL/Elasticsearch, and then runs semantic ranking over the filtered set, or falls back gracefully if the intersection is empty. Then it ran the regression tests in `tests/test_search.py`, and they all passed.

</details>

---

### 自愈系统的生产实践：构建自治的持续集成循环

在实操演示的最后阶段，Laurie Voss 将这一工作流程扩展到宏观的企业生产环境。在真实的大规模系统中，工程师不需要手动将 Trace 喂给终端里的 Claude Code；在 Arize 的生产观测流水线中，这一流程是在后台常驻且完全自治运行的。系统在生产中以无感方式持续收集数万条 Trace，通过自动化评估器不断打标，后台的聚类引擎实时捕捉新出现的失败模式聚类。

一旦某个模式的失败样本数突破预设阈值（例如聚类识别出 100 到 1000 条相似调用由于某种边界条件崩塌），系统会自动打包该模式的失败上下文与黄金测试集，在后台沙箱中唤起编程 Agent 编写修复代码，并在隔离环境中运行回归套件。确认无误后，系统直接向代码仓库提交一个附带完整 Trace 证据、根本原因分析及测试对比报告的 Pull Request。人类工程师的角色随之发生根本性转变：从救火式的“排查追踪日志、手工编写补丁”，转变为在高维度上“审查评估准则、审批合并自愈 PR”。这种范式彻底闭环了现代软件生命周期，为构建具备自愈能力的高韧性生产级智能体应用确立了前沿标准。

<details>
<summary>Original English Source</summary>

Cloud Code, but it does it automatically inside AX all the time. It reads your traces, looks for patterns, finds errors, and suggests fixes. So luckily I created this thing over 6 hours ago, so it's already up and running. Uh, and she found, uh, a bunch of problems in the previous versions of this program that I didn't even notice. In a real production deployment, you don't do this manually with a single trace on your laptop. You don't wait for a customer to complain, pull up a trace, open your terminal, and run Claude Code by hand. What happens in production is that you have a continuous stream of traces. Arize or your observability platform ingests millions of spans. Evaluators run in the background, scoring each interaction asynchronously. Then the pattern clustering engine groups the failures. It doesn't trigger on a single isolated glitch. It triggers when it sees a statistically significant pattern: "Here are 500 traces where the agent failed on currency conversion," or "Here are 1,200 traces where the inventory lookup timed out." When that threshold is reached, the system automatically spins up an autonomous coding agent in a container. It gives the agent the repo, the clustered traces, the failing evaluation criteria, and says, "Fix this." The agent branches the repo, modifies the code or prompt, runs the evaluation suite against the historical failing dataset, verifies that the fix resolves the failures without degrading other metrics, and opens a Pull Request on GitHub with a comprehensive explanation of the bug, the root cause, the fix, and the before/after evaluation metrics. That is what we mean by closing the software development lifecycle loop. You, the human engineer, wake up in the morning, look at GitHub, review the PR, look at the evaluation delta, and click merge. You're no longer the manual debugger. You are the architect and the evaluator. How do you know that, excuse me? M-hm. Oh, yes. Um, so the solution here is evaluations (evals), you'll be surprised to know this. A production system must have rigorous evals. If your evals are weak, your automated fixes will be dangerous. But if your evals are solid, you have created a self-healing software system. That is the future of agentic engineering, and that is where the industry is going. I think I'll stop there. Thank you all for your time and attention. Ugh.

</details>