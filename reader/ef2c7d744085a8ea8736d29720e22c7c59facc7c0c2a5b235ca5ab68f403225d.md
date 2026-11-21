---
author: AI Engineer
date: '2026-11-11'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=0EnLxIbAvYk
speaker: AI Engineer
tags:
  - formal-methods
  - automated-reasoning
  - specification-analysis
  - coding-agent
  - smt-solver
title: Keto 规范分析器：在代码 Agent 编写代码前使用形式化方法消除规范歧义
summary: AWS 自动推理团队的 Rajat Kotyal 介绍了 Keto Specification Analyzer 项目。针对模糊提示导致 LLM 准确率下降及生成代码存在缺陷的问题，该工具结合形式化方法与 SMT 求解器，在规范移交 Agent 前检测单句歧义、跨句子冲突与遗漏，并聚类翻译结果供人工决策或弃权。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - AWS
products_models:
  - Keto Specification Analyzer
media_books: []
status: evergreen
---
### 介绍 Keto 规范分析器

大家好。我叫 Rajat Kotyal。我是 AWS 自动推理团队的一员。今天我将要谈论一个我最近参与的项目，名为 Keto 规范分析器（Keto Specification Analyzer）。

<details>
<summary>Original English</summary>
Hi everyone. My name is Rajat Kotyal. I'm part of the automated reasoning group at AWS. And today I'm going to talk about a project I worked on recently called Keto Specification Analyzer.
</details>

我们使用某些涉及形式化方法和自动推理的技术，在规范提供给你的编码 Agent 去写代码之前对其进行证明。

<details>
<summary>Original English</summary>
And we use certain techniques which involves formal methods and automated reasoning to prove specification that goes to your coding agent before it writes code.
</details>

### 规范冲突与歧义示例

那么我们来看一个特定的缺陷，对吧？这是一个规范片段，举例来说有两条规则。规则二指出，当一个订单被提交时——假设这是一个通用的电子商务网站。当一个订单被提交且库存不可用时，我们将订单置为延迟订购（back order），单独阅读这一条时是讲得通的。但在同一个你交给编码 Agent 的规范文件中，还有另一条规则指出：任何订单都不得置为延迟订购，而这是我们设定的一条规则。

<details>
<summary>Original English</summary>
So let's take a certain bug, right? This is a specification uh snippet and there are two rules for example and the rule two says when an order is submitted and this is for a a general e-commerce website, let's say. When an order is submitted and the inventory is unavailable, we place the order as a back order which makes sense when you read it individually. And there's also another rule in the same specification file which you hand to the coding agent which says no order shall be placed as a back order and this is a rule we'll set.
</details>

所以单独阅读这两行是讲得通的，对吧？但是当 LLM 一起阅读这两条规则时，两者无法同时成立。因此我们需要确保解决 LLM 所观察到的这种歧义。

<details>
<summary>Original English</summary>
So individually read these two lines make sense, right? But in when an LLM reads this, reads both the rules together, both cannot hold true at the same time. So we need to make sure the we resolve this ambiguity that the LLM is observing.
</details>

### 模糊提示词的影响

我们在这个项目中投入精力的范围和原因，是基于公开研究以及最近的研究：我们观察到模糊的提示词会导致 LLM 生成的准确率和代码准确率出现 **20% 到 40% 的下降**，对吧？并且在写出代码后，**60% 到 90% 的有效代码仍然存在错误**。此外，在那类情况下，我们观察到在部署该代码时，会出现 **2 倍以上的回归问题**。

<details>
<summary>Original English</summary>
And uh the scope and the reason we uh put an effort into this project is based on public research and recent research we've observed there's a 20 to 40% drop with unclear prompts on the accuracy the LLM generates and the code accuracy, right? And 60 to 90% of valid code is still wrong after it writes it. And also in that case we observed two times the more more regressions when we deploy that code.
</details>

### 形式化验证三步流程

那么这类缺陷隐藏在哪里呢？我们希望在它们进入代码库之前检测出来。唯一可行的方法类似于我们编写设计文档、类似于我们绘制图表和流程图，以确保在编写任何代码之前确定流程。我们希望在没有人类或任何人作为第一评审人阅读这些文件的情况下对其进行验证。

<details>
<summary>Original English</summary>
So where do bugs like these hide, right? We want to detect these bugs before they reach the code base and the way only way to do that it's similar to how we write design docs, similar to how we draw diagrams and flow charts to make sure the flow is set before we write any code. We want to verify that without a human or anyone reading these files as the first reviewer.
</details>

在单句内部，可能存在用词歧义和细节层次错误；而在跨句子之间，我们能观察到这些规范或规则中的冲突与空白，对吧？句子需要评审，彼此之间需要检索和歧义查找。

<details>
<summary>Original English</summary>
In one sentence let's say the ambiguity and wording wrong level of detail, but across sentences we can observe conflicts and gaps in these specification or rules, right? Sentences need review, such need search in between them and ambiguity searches.
</details>

因此我们设计了一个三步流程来完成这项工作：
1. **LLM 首先进行提炼**：它会尝试自行清理表述；如果成功了，那自然很好。
2. **形式化为 SMT 公式**：如果无法解决，我们随后将英语语言形式化为 SMT 公式。SMT-LIB 是一种特定类型的函数集合，我们将其传递给 SAT 求解器或可满足性检查器，它会输出一个布尔值，表明你给出的表达式是有效、真还是假（无效）。
3. **求解器反馈与迭代**：一旦求解器返回结果给我们，如果该表达式有效，我们就不采取任何操作；但如果检测到两句之间存在任何歧义，或者在单个句子内存在两种含义，我们就会检测出来并通知 LLM 重新检查该句子，它将对此进行重新迭代。

<details>
<summary>Original English</summary>
So we have a three-step process to do this where the LLM will first refine it. It will try to clean up the wording on its own and if it succeeds then well and good, but if it cannot we then formalize the English language into SMT formulas. So SMT lib is a certain set of type of function which we pass to a SAT solver or satisfiability checker where it's going to give out a Boolean saying this expression that you're giving me is valid, true or false, invalid. And then once the solver gets back to us if that expression is valid then we don't do anything, but if it detects any ambiguity between two sentences or within a sentence where there's two meanings to a sentence then we detect that and tell the LLM to recheck that sentence and it's going to re-iterate on that.
</details>

例如我们见过的那些规则：当订单提交且库存水平不可用时，我们应将订单置为延迟订购；在 SMT 格式中，它看起来大致像这样，就像一个数学公式，对吧？

<details>
<summary>Original English</summary>
For example, the rules we saw we've seen when order is submitted and inventory level unavailable we shall place the order as a back order and in SMT format it kind of looks like this, this like a math formula, right?
</details>

### 多次采样与逻辑等价聚类

进一步深入后，一旦我们检测到这一点，我们还会再次执行一个三步流程：反复对翻译进行采样。我们要求 LLM 进行 7 次或 10 次翻译，以了解该 LLM 表现出这种行为究竟是基于其固有能力，还是有什么因素影响了它产生这种行为。然后基于 LLM 给出的这 7 种或 10 种不同解释的逻辑等价性，我们按照逻辑等价性对其进行聚类，从而确定哪些条目归属于 LLM 自行做出的哪些假设。随后我们接受这些假设，或者要求用户澄清歧义，亦或放弃在代码库中实现该部分。

<details>
<summary>Original English</summary>
Once we go deeper, we once we detect this, we also do three-step process again where we sample the translations again and again. We ask the LLM to translate seven times or 10 times and to understand whether this LLM is behaving this way based on its its inherent capabilities or is something affecting it to behave this way. And then based on logical equivalence of these seven or 10 different set of interpretations by the LLM, we cluster them on logical equivalence which sets which entries came under which assumptions that their LLM made for itself. And then we accept or ask the user to clear out the ambiguity or abstain from implementing that in the codebase.
</details>

### 人工介入与冲突/遗漏判定

这是一个向人类询问针对可能存在矛盾的规则想要如何处理的例子。「删除记录」（Remove the record）是一个非常非常模糊的陈述。LLM 可以随意进行任何解释，但我们不应该允许这种情况发生。我们要么给出两个选项：
- 保持原样，直接删除该记录；
- 或者保留该记录，但对用户隐藏。

用户更倾向于哪一种？

<details>
<summary>Original English</summary>
This is an example of asking the human what you want to do with that rule that was perhaps contradicting. Remove the record is very very vague statement. The LLM cannot can interpret anything it wants, but we shouldn't allow that to happen. And we either give two options. We keep it as is. The record is deleted or we retain it and but hide it from the users. Which one does the user prefer?
</details>

冲突（conflict）是指我们在示例中看到的规则一与规则三发生矛盾。而遗漏（gap）则是指没有任何规则覆盖该示例中的闲置订单（idle order），在这里 LLM 检测到——抱歉，是流程或流水线检测到该规则缺少条目，存在遗漏项。

<details>
<summary>Original English</summary>
A conflict is when the examples example we saw rule one is conflicting with rule three. And a gap is where no rule covers an idle order in this example where the LLM detected an actual sorry the process or pipeline detected there's no entry for this rule where you are missing something.
</details>

### 总结与核心结论

归根结底，目前它还无法完成所有事情。我们希望确保除了用户之外，没有其他针对规范正确性的判定权威（oracle）。用户必须确保在将代码片段或规则手册发送给 LLM 之前，仔细检查其中的每一部分。而我们作为一个工具，只能提供协助。用户在这里更为重要，这是因为存在隐式领域知识。LLM 缺乏很多领域知识，且 LLM 无法提供任何保证。只有用户才能给出这一保证，对吧？目前关于形式化及其在 Agent 中如何应用的证据还很少。我们正处于这项技术的新兴阶段。

<details>
<summary>Original English</summary>
All in all, it cannot do a lot of things under the day. We want to make sure there is no oracle uh for for specification correctness other than the user. User needs to make sure to check every part of the snippet, part of the rule book before sending it to the LLM. And we as a tool only can help them. And the user is more important here because of implicit domain knowledge. The LLM doesn't know a lot of domain knowledge and there's no guarantee from an LLM. Only uh user can give that guarantee, right? And there's thin evidence right now for formalization and how it can be used in agents. We are emerging in this technology.
</details>

本次演讲的核心要点是什么？
- 在将规范向下传递给 Agent 之前，**务必先检查规范**。
- 对翻译进行聚类：我们的做法是**按逻辑等价性对翻译进行聚类**，以确定 LLM 的不同解释以及它到底在何处真正出错。
- **LLM 负责翻译，求解器负责检查，人类负责决策**。我们向人类提供选项；如果对此没有回应，我们则使用 LLM 作为评判者（judges）或放弃实现该部分代码。

<details>
<summary>Original English</summary>
What do we take back from this talk? Check the spec always before you pass it down to the agent. Cluster the translation we what we do is we cluster the translation by logical equivalence to determine the different LLM interpretations and where it's genuinely going wrong. The LLM translates, the solver checks and the human decides. We give to give the human options and if there's no answer to that, we use LLM judges or abstain from implementing that piece.
</details>

这里是参考资料，这项工作主要由我的团队贡献，大家可以查看他们的博客和提供的网站链接以深入了解。谢谢大家。

<details>
<summary>Original English</summary>
Here are the references and this work has been majorly contributed by my team you can check out their blog and the website link provided and delve deeper into this. Thank you.
</details>