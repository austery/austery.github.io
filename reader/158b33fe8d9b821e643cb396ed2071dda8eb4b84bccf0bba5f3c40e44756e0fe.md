---
author: AI Engineer
date: '2026-10-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=c_SPW__jF9w
speaker: AI Engineer
tags:
  - agent-evaluation
  - synthetic-data
  - contract-analysis
  - llm-as-a-judge
  - rag-evaluation
title: 无基准测试集时如何评估AI Agent：加拿大航空的逆向生成实践
summary: 加拿大航空数据科学团队面对垂直业务场景缺乏公开基准且专家资源稀缺的难题，提出了“答案先行、逆向构造测试集”的核心方法。通过基于规则合成合同、破坏已有合规合同、参数模板排列组合以及不变性测试等五种技术，用确定性代码替代高噪的LLM-as-a-judge，实现Agent评估的快速闭环。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Air Canada
products_models: []
media_books: []
status: evergreen
---
### 戒掉“无评估交付”的执念

感谢大家参加这一场分享。这稍微带有一点个人情感色彩。我叫 Nathaniel，我曾是一个“不设评估者”。我已经有很长一段时间不再交付任何未经评估的 agent 了。今天我想向大家讲述我如何戒掉这种“不带任何评估就交付 agent”的瘾。

我在加拿大航空（Air Canada）工作。所以与前面的演讲相比，这更聚焦于具体的业务场景。我是在今年六月加入加拿大航空的。加拿大航空是一家庞大的公司，我们的业务涵盖运营、企业后台、商业以及常旅客忠诚度计划，每个板块都有各自独特的挑战。

<details>
<summary>Original English</summary>

[music]

>> Thank you for joining this station. It's a bit of an emotional one. My name is Nathaniel. And I'm a non-evaluator. It's been a lot of time since the last agent I've been shipping without any evaluation. And today I want to tell you the story how I quit this addiction of shipping an agent without any evaluation.

So, I'm working at Air Canada. So, compared to the previous talk, it's more like focus on specific business. I joined Air Canada in June of this year. And Air Canada is a huge company. We work in operation, corporate, commercial, and loyalty. Each of those segments have their own challenges.

</details>

我的团队负责为所有这些板块交付 AI 解决方案。而当我们处理具体任务、为极其特定的任务构建 agent 时，面临的难题是没有可依赖的公开基准（public benchmark）。这正是我在本次演讲中试图探讨的核心问题。

更关键的是，不仅是没有基准，还在于我们是可以构建 agent 的数据科学家或 AI 工程师，但我们不是领域专家。而那些领域专家分布在不同的业务部门，他们忙于自己的日常工作，我们能接触到他们的机会非常有限。这两种情况交织在一起，导致我们极难为自己的任务构建任何评估流程或基准。

<details>
<summary>Original English</summary>

So, my team is in charge of delivering AI solution for all of those. And the problem when we tackle task we create an agent for a task that is so specific, we don't have any public benchmark we can rely on. And that's the main main problem we I'm trying to address in this presentation.

More importantly, it's not that we don't have a benchmark, is we are data scientists that can build agents or AI engineers that can build agents, but we are not domain experts. And those domain experts sit in different business units. And they are very busy in their own task. And we have a limited access to that. So, both of those things went together in a situation where it's very hard for us to build any evaluation or any any benchmark for our task.

</details>

### 从电信 RAG 项目中汲取的教训：逆向生成问题

在加入加拿大航空之前，我在另一家公司工作。当时的任务是为电信工程师构建一个问答助手。不知道大家对这个领域是否熟悉，电信是一个庞大的领域，大约有一万份文档，此外还有大量的供应商文档。要找到哪份文档才能回答问题，其背后有一整套逻辑，因此这是一项相当复杂的任务。

到了 2024 年，每个人都想做 RAG。于是我们也开始做。在 LinkedIn 上看着好像超级简单，但实际根本不是。问题在于当我们推进这个项目时，遇到了和加拿大航空完全一样的困境：我们缺乏接触专家的途径，对专家的访问很受限，而且我们自己无法给模型生成的答案打分。这就是我今天想聊的问题。

<details>
<summary>Original English</summary>

So, before going to Air Canada, I was working for a different company. It was a company that and the task was to build a a Q&A assistant for telecommunication engineer.

So, I don't know if you're familiar with the domain. The telecommunication is a huge domain. There is about 10,000 documents. A lot of vendor documents on top of that. There's a logic to know which document you should you should find in order to answer the question. So, it's it's a bit of a complex task.

And then 2024, everybody wanted to build RAGs. So, we started to do that. Yeah, on LinkedIn it's super easy. It's not. So, the thing is when we tackle this project, the same problem as at Air Canada, we don't have access to expert. We have the limited access to experts. And we we could not actually grade the answer ourselves. So, that's the the problem I I want to talk today.

</details>

有趣的是，我们当时还面临着与其他团队的竞争——两个外部团队，一个内部团队。并非完全并行，而是分阶段推进。最终我们的方案切实起效了。“起效”的意思是真正交付了价值，人们喜欢这个解决方案并且切实去使用了它。但坦白讲，与其他团队相比，我并不完全清楚我们到底凭什么做成功了。今天我就来展示我和团队到底做了什么才让它运转起来。所有团队面对的都是同样的文档、相同的任务、一切背景都一样，但我们的方案莫名就奏效了。

熟悉 RAG 的人都知道，其原理非常基础：向系统提问，系统检索相关文档，并基于这些相关文档组织答案。这已经存在很长时间了。实际尝试过的人都会发现，只要找到了正确的页面或文档，90% 的情况下都能得到正确的回答。所以挑战其实在于找到正确的文档，至少在这个任务里是如此。

<details>
<summary>Original English</summary>

Funny enough, we were in competition with other teams. Two external, one internal. It's not like in parallel, but in segments. And our solution actually worked. What mean worked is actually delivering the value. The people liked the solution, actually used it. But to be honest, I don't know why we actually made it work compared to the other the other team. So, today I'm just going to show what I actually did or my team actually did to make it work. So the the all have the same document, same task, everything is the same, but our solution somehow worked.

So, for those that are familiar with RAGs, the principle is very is is to ask a question to the system, the system found the the relevant documents, based on this relevant document, formulate an answer. It's something that exists for a long time now. And for those that actually tried it, if you found the right page or the right documents, 19 90% of the time you have actually the right answer. So, the challenge to find the right documents, at least in this task.

</details>

### 复杂度的陷阱与自动化评测转化

于是我们搭建了一个非常复杂的流水线，随着时间推移变得越来越复杂。如果你翻看当时发表的论文，每个人都提出过非常惊艳的技术来优化方案。我们去尝试了，但实际上并没有带来提升。在论文的实验环境里它们或许有效，但在我们这儿没起什么作用。

更要命的是，当我们增加复杂度时，往往会改坏现有的东西——原本能正常工作的部分突然失效了。这才是真正的问题。我们可以不断堆叠想法去解决不同的个案问题，但系统却在反复崩溃。所以复杂度并不总是管用。

另一个问题是评估周期。我们几分钟内就能修改一个 agent，加一层 query 重写或是某种推理步骤。但为了给它打分，我们每周都要和专家开一次令人发疯的会议。我们摆出一面巨大的屏幕，同时展示五个不同的聊天机器人，向它们提出同一个问题，然后让专家来评定：“我更喜欢这个，我更喜欢那个。” 有趣的是，他们内部的意见也经常不一致。把专家聚在一个房间里，常常会得到三种不同的看法。这就是我们面临的瓶颈：我们的预算只够每周做一次测试，这完全不足以支撑快速迭代。

<details>
<summary>Original English</summary>

So, we created a very complex pipeline that get complexified over time if you publication if you found publication back in the time this everybody has an amazing technique to improve the the solution. We try them. It's actually didn't improve the solution. So, on paper it worked for them for the publication but for us it didn't really help. And more importantly when we add complexity, we found that like we break something else. So, something that used to work now is not working anymore. And that's actually the the real problem. So, we can add and more we can get more ideas on into solving the different problems but we we keep continue we keep breaking things over and over. So, complexity doesn't always help.

And the other problem is this one. We can change an agent in few minutes, add a certain layer of query writing or whatever reasoning step. But to grade that, we had those crazy meeting once a week with experts. We put a giant giant screen with five different chatbot, ask the same question to all of them and ask the the expert to grade them. I prefer this one, I prefer this one. And funny enough they're not always agreeing. It's very hard when you when you put expert to explain the room you get three opinions. So, that's the the the problem we were facing. And so, our budget was we can try one solution a week and this was not enough to go fast.

</details>

在进一步深入前，当时的流程大致是这样的：我们提问，agent 回答，然后让专家去读；有时候专家自己也不知道答案，还得去查阅资料，消耗大量时间。我们每周只有一次试错预算。

这里其实没有什么全新理论，我们做的是一个广为人知的转变：将问题反转过来。我们从具体的页面出发，让 LLM 针对这个页面生成一个问题——这是一项很简单的任务。然后让 agent 去检索这个问题的答案，并将 agent 检索到的页面与最初用来生成问题的原始页面进行比对。这样一来，我们完全可以用代码来打分，不再依赖主观意见，也不受其他因素干扰，彻底实现了自动化评估。这让我们迭代的速度大幅提升。

<details>
<summary>Original English</summary>

So, the before going further so, the the the the process was the following. We ask we ask a question the agent answer. We ask the expert to read. Sometimes they don't know the answer. They have to look up. It takes a lot of time. And we had the budget of one trial a week.

So there is nothing new here. This abiding that is well known is we reverse the problem. So we start with a page. We ask an LLM to write a question about this page, which is an easy task. We ask the agent to search for this answer and compare to what the agent found, compared to the to the page that has been used for to generate the question. We can actually use code to grade that. And no longer opinions, no longer anything. We can automate this task. And that allow us to go much much faster.

</details>

在做 RAG 的圈子里，这种做法有很多具体的实现，并非我所发明。我只是觉得这个思路非常巧妙，并且深深刻在我的脑海中：为什么这个原则不能应用到其他任务上呢？

这样做的效果立竿见影：我们从每周只能评估一次，变成了每天可以评估几十次。我们开始看到专家打分的准确率一路走高。事实证明，移除大量复杂度非常有帮助，很多花哨的步骤根本不需要。集中精力选对 Embedding 模型、做好分块（chunking）、调好 BM25 中的 alpha 参数，才是正确的方向。随着数周的推进，我们眼看着准确率稳步上升。

我不知道我们最终胜出的全部原因，但我敢肯定其他团队没有任何测试集。他们依赖的是那种漫长的专家评审循环，尽管他们接触专家的权限可能比我们多得多。但我们拥有这个测试集。2024 年我学到的一点是：如果你无法评估 agent，你就无法改进它。这个认知伴随了我两年，直到今天。

<details>
<summary>Original English</summary>

So for those that work in rags, there is plenty of implementation of this thing. I didn't invented it. I just found it very very very smart. And it stick to me. Like why this principle cannot be applied to other task?

So the impact of that is we went from one evaluation a week to dozens a day. And we start to see the the accuracy of the the the grading from the expert going up and up. And actually removing a lot of complexity help. Like we didn't need a lot of those. And focusing on the right embedding model, the right chunking, the right alpha in the BM25 is the right thing to do. And we we saw the we saw the the accuracy increasing over over weeks.

>> [snorts]

>> So I don't know why we succeeded, but I'm pretty sure the other team didn't had any test set. So they were using this kind of long loop with expert maybe a much more expert than we had access to. But we had it we had this test set. And my learning from this back in 2024 is if you cannot grade the agent, you can't make it better. So that stick to me until this day has been 2 years now.

</details>

### 加拿大航空的新挑战：供应商合同分析

现在我想把话题转回加拿大航空。我们面临着一个全新的项目。到了 2026 年，这个项目旨在分析供应商合同。大家可以想象，加拿大航空有大量的供应商，我们会收到源源不断的合同。法务和领域专家必须逐字逐句审核合同中的每一项条款，进行分析并给出反馈：例如“这一条款不合规”、“这一条款需要重写”等等，这中间有大量繁重的审阅工作。

这是一项极为耗时且成本高昂的任务。如果业务上急需某个供应商即刻交货，而合同卡在审核中，就会给整个供应链造成严重延误；而如果遗漏了某个风险条款，代价同样极其高昂，因为最终可能会反噬到公司身上。所以这是一个非常棘手的难题。

于是业务方找到了我们数据科学团队，希望能构建一个能替他们完成这项工作的 agent：我们能否将这项任务自动化？

<details>
<summary>Original English</summary>

And I want to go back to Air Canada now. Where we have a different project. So in 2026 the project is about analyzing supplier contract. So you can imagine Air Canada has a lot of suppliers. We get a lot of those contract. There's expert looking at them one by one. Checking each of those clauses. And they have to analyze it and provide a feedback. Like this clause is not compliant. This clause needs to be rewritten. Like there's a lot of work to do that.

It's a very long task and very costly because if we need the if we need some supplier to deliver right now and we don't, then it cause a lot of delay in the in the chain. And if we miss a clause, it's also very costly because at at the end of the day it can backfire to us. So it's a tricky problem.

Um and they came to me I mean to the to the data science team to build an agent that can actually do that for them. So can we automatize this task?

</details>

显然，在做合同分析时，有海量的文档、规则和各类约束需要考量。专家们极其繁忙，大家完全可以想象律师按小时计费的成本。而且外界根本没有现成的基准可供参考，我们无法直接去网上搜索文档或套用已有的 benchmark。

于是我又回到了 2024 年面临的同样困境：迭代周期极慢。但我们清楚，必须让自己处于一种能够快速尝试、反复验证的状态。我知道只要进入这种正向循环，我们就能在准确率上走出一条更好的增长轨迹。

这个项目的挑战究竟在哪里？在 RAG 场景中，从文档中生成回答已经是一个定义明确且成熟的问题；但对于这个特定项目，世界上没有任何人能告诉你：“嘿，你应该用这种技术，或者那种技术。”

因此我们开始思考，如何将之前在 RAG 上学到的机制重新应用到这个具体项目中。加拿大航空有许多此类项目，我们沿用的都是同一个核心理念：**先掌握答案，再让 agent 去反向推导寻找答案**。

<details>
<summary>Original English</summary>

And obviously there's a lot of documents, a lot of rules, a lot of things to consider when you do that. Expert are super busy. You can imagine the price of of a lawyer by hour. And there's no benchmark for that. We cannot go on the web and found documents I found an existing benchmark we can apply.

So go back to the same problem as I was in 2024. Cycle were super slow and we knew that we want to be there in a in a in in a in a shape where we can go fast and try and try and try. And I knew that if we if we learn to this situation, we can have a better trajectory in term of accuracy.

And that What the challenge for this for this project? So, the the problem is creating the answer from documents is a well-known and defined thing in the rags, but for this specific project, there's no guy in the world that say, "Hey, you should use this technique. You should use this technique." So, we try to think how we can reapply the same mechanism from what I learned on rag to this specific project. And we have plenty of project at Air Canada. So, we're using the same concept of getting the answer first and then try the agent to find it back.

</details>

### 合同分析 Agent 的架构与五种测试构建技术

具体展开来看，虽然做了些简化，但实际上这个 agent 包含四个主要步骤：
1. 识别并定位合同中的特定条款（spot）；
2. 检索支撑修改该条款的相关依据文档；
3. 撰写修订建议（amendment）；
4. 最后通过分类系统判定是否保留这条修订建议。

比如第一步“定位”，涉及将合同的所有章节划分到特定的领域中，然后判断该章节是否存在缺陷或需要修改的地方。借助之前在 RAG 中积累的技巧，我们知道如何检索依据文档，这一块是有底气的；但对于 agent 的其余模块，我们此前毫无积累。

接下来我将介绍我们在该项目中实际使用或尝试过的五种技术，它们旨在攻克这一评估难题。我的目的不是为了炫耀，而是希望启发大家如何将这些技术迁移到各自的业务挑战中。

1. **利用历史决策与答复**：调取历史合同，与变更后的版本进行比对；
2. **基于规则反向合成**：选定想检测的目标特征，反向编写或生成围绕它的合同文本；
3. **破坏合规合同**：拿一份已签署的高质量合同，故意破坏或剔除部分条款；
4. **不变性测试**：改变一些理论上不应影响结果的变量，确保标记数量保持不变；
5. **基于模板的组合扩增**：这是最强大但也最具挑战的方法，利用模版概念将单个案例裂变为海量测试用例。

<details>
<summary>Original English</summary>

So, going into the details, it's a bit simplified, but actually the the agent has four steps. We need to spot the clause in the contract. We need to find the relevant documents to support an amendment. We need to write the the amendment. And then at the end, there's a classification system that tells you should we keep it or not this amendment. So, the first step, for example, spot is classifying all the section of the contract into specific domain domains. And then found if there's a defect or there's a change to be to be done in this section.

So, we did have this trick from the rag. So, we know how to find the documents. So, this is covered. But for the other other section of the of the agent, we didn't have anything.

So, I going to present five different techniques that we use in this project or we try to use in this project. That is trying to address this specific problem. My goal is not to show off. My goal is to get you inspired in how to reapply those techniques in your own challenges.

So, the first one is to use past decision and answer. So, we you can retrieve past contract, compare with the one that has been changed. The second one is to choose something you're looking for, write the contract around or generate the contract. The third one is take a good contract that has been signed and break it. The fourth one is about things that should not change no matter what you do, you should not get more flags. And the fifth one is actually the most powerful. It's very hard. It's to turn an example into many using the concept of templates.

</details>

我们最开始直接尝试了第一种方法。我们向专家要来原始合同以及最终签署生效的合同，打算像在代码里跑 diff 一样比对改动内容，理论上 agent 应该能报出完全相同的修改标记（flags）。这本该是最完美的方案。

然而出于现实中的种种原因，业务团队并没有完整保存所有合同的历史版本：他们不保留原始送审稿，只留存最终版；而且合同在谈判过程中版本繁多、流程复杂。我们根本无法拿到成对的新旧合同。因此，第一条路走不通。

于是进入第二种方法：以规则为起点。我们稍稍调整了思路，不再从“构建能打标记的 agent”入手，而是直接从“规则”出发。比如有一条规则是“交易额上限不得超过 100 万美元”，这是加拿大航空在特定领域所有合同都必须遵守的准则。既然明确了规则，我们就可以故意生成一条违背该规则的条款，并在其周围合成出一整份合同。这样我们就能预先确切知道 agent 应当捕获该违规标记。这种方式非常简单，不需要大量人工，很多内容可以直接生成。唯一的要求是你必须清晰知晓具体的业务规则。

幸运的是，我们能够从专家或现有文档中整理出一部分明确的规则，尽管无法保证覆盖全部细节。结合我们自己梳理的规则，我们最终生成了 275 个确定知晓标准答案的测试用例。与 RAG 的思路类似，我们反转了问题：预先把“缺陷”埋进去，再去测试模型能否把它找出来。

<details>
<summary>Original English</summary>

So, immediately we jump into this approach. We ask the expert to provide us the original contract, the one that has been signed. We're going to take that, do a diff like you do in the code, compare what has been changed, and the agent should should provide the same exact flags. That would be perfect. However, for many reason, our our team do not keep all the contract. They don't keep the original one, they just keep the last one, they don't have all the version of the contracts. It sometimes goes into negotiation, there is a lot of things. So, we could not have any of those pairs of contracts, so this thing doesn't work.

Okay, second one. We took a rule. And so, that's changing a bit the topic. Instead of creating flags or creating an agent that can provide flags, we start from rules. And the rule is, for example, we have the the cap above $1 million. So, that's every contract that Arcada should follow this rule or many of those in specific domains. So, you know the rule, you create a clause without breaking this rule and generate the contract around, and you should found the rule back the the flag, which is breaking the rule. So, that's simple. It doesn't require a lot of of work. A of things can be generated. The problem is you need to know the rules.

So, luckily enough, we could actually get some of those from either the expert or the documentation they had, but cannot guarantee the coverage of everything. So, we came up we also with our own rules, etc. So, we generate at the end 275 tests that we know can run and we know the answer. So, similar to the rug, we inverse it we inverted the problem, we planted the problem, and we try to find it back.

</details>

第三种方法难度很大：我们取出一份已经正式签署的合规合同样本，故意删掉其中的某一关键条款，此时 agent 应当主动警示：“嘿，这里缺少了某项条款。”

这项任务之所以非常困难，是因为不同供应商使用的合同模版各异，内容编排千差万别。要判断某类合同中必须包含什么条款，需要相当深度的业务理解。我们将这些被删减条款的合同样本，与本就不该报错的正常完整合同混合在一起进行测试。这是我们目前使用的最有效的方法。借助这种方式，我们可以大批量生成合同样本。最终测试发现，我们的 agent 漏掉了绝大多数被人工故意移除的条款——这立刻构成了一个极具参考价值的高强度基准测试。

第四种技术是不变性测试：修改那些理应不会对 agent 结果产生任何实质影响的无关变量。例如修改供应商的名称、地址，这些信息的变动绝不应该导致风险标记数量发生变化。此外还可以打乱条款的先后顺序，引入一定的随机性，理论上也应输出完全相同的结果；或者对同一份合同进行多次重复运行。所有这些手段都是为了检验系统输出的一致性与稳定性。

在这类测试中，所有的结果都可以完全通过代码进行硬性校验，根本无需引入 LLM 作为裁判（LLM-as-a-judge）。正如前一位讲者提到的，LLM 裁判本身就是一项极难驾驭的任务，因此我们尽可能远离 LLM-as-a-judge。

<details>
<summary>Original English</summary>

Another one which is a very hard, actually, we took an example of a contract that has been signed, we remove a clause, and the agent is supposed to say, "Hey, there's something missing here." It's a very hard task because some supplier has different templates, have different kind of content. Knowing what should be in what contract require a bit of thinking. And we mix those with existing contract that should not show any flag. So, that's the most powerful approach what that we had today. Using this approach, we can generate a lot of contract, and at the end of the day, we found that our agents are missing most of the clause that has been removed. So, that's a very very strong benchmark.

Okay. Fourth technique, you don't change you change something that should not affect the agent or should should not change anything in the result. For example, the name of the supplier, the address of the supplier, something that should not have any impact on the number of flags. You can reorder the clause, so some randomness should also lead to the same results. And you can run the same contract again and again. All of those are things that we check to make sure that the the output is consistent over all of those.

In this example two, everything can be checked using code. You don't need to do any LLM as a judge. The previous speaker showed like it's very hard task. So, we stay away from LLM as a judge as much as possible.

</details>

第五种技术是利用模板概念。法务专家手头通常备有各种留有空白的模板——如果大家写过合同应该很熟悉，这些空格是留给业务方或专家填写的。我们不再尝试人工填写，而是为每一个待填空格生成一组候选值数组。

这使我们能够排列组合衍生出海量的合同用例。在这些组合元组中，哪些组合违反了规则、哪些没有违反，我们预先完全掌握。因此我们确切知晓系统应当报出哪些违规标记。同样地，这也是纯代码级别的判断，全程不需要任何 LLM 介入评判。这种做法的好处在于专家平时就习惯使用模板，我们可以直接复用现成资产来生成测试合同。以往需要等待 4 周才能从业务端拿到一轮人工反馈，而现在我们只需运行一段脚本，5 分钟内就能拿到完整的评估结果。

<details>
<summary>Original English</summary>

The fifth one, it's the concept of template. Our expert have different kind of templates with blank. So, I don't know if you ever write a contract. Those blanks should be filled by the expert. And instead of trying to fill them, we generate an array for each of those blanks to be filled with.

So, that's allow us to generate plenty of contracts. Some tuples break some rules, some tuples doesn't. We know that. And so, we know what actually should be flagged as a as a as a breach or not. Again, this is a code check. We don't need to have any LLM involved.

What The good thing is with this one is our expert already use templates, so we can reuse them to generate some contracts. So, the cycle was a bit slower in this case, so 4 weeks to get a a feedback, and we can get a script to run and get the the evaluation back in 5 minutes.

</details>

### 避开 LLM-as-a-Judge 的噪音陷阱

我想强调的一点是，我们在评估金字塔底部探索了所有这些评测类别。精确匹配（Exact match）或纯代码检查的执行速度极快。一旦涉足 LLM-as-a-judge，它看起来可能非常酷炫高级，有时也确实有用，但实在太痛苦了。相比于我们正在构建的 agent 自身的噪音，LLM-as-a-judge 引入的噪音甚至大得多。

解决评测模型本身的可靠性问题，其难度几乎不亚于去解决业务核心问题本身。要为 LLM 裁判找到合适的 prompt、搭建合适的基础框架（harness），是一项极度艰巨的工程。你固然可以做很多防护手段、做事实核查等等，但它需要消耗海量的精力，在这个项目中我们始终没能为它找到最恰当的落地方案。

当然还有很多其他技术，我无法在此逐一列举。比如轨迹评估（trajectory）：我们在另一个项目中要求 agent 命中某些特定的断点/终点（endpoints），既然已知终点按某种顺序出现，就可以围绕它生成一个业务故事，让 LLM 驱动 agent 运行并观察调用链路追踪（trace），以此验证执行轨迹是否正确。还有大家可能已经熟知的 Text-to-SQL 评测。

无论你开发的是什么 agent，只要你清楚如何圈定标准答案、只要你知道自己想要找什么——正如我刚才展示的几个例子——那就把输入反向生成出来，再去测试 agent 能否把它找回来。这套方法并不适用于所有场景。甚至有时候我们不得不反向重构原有的解决方案，哪怕这会稍稍偏离最初的产品架构设计，因为按照最初的设计我们根本无法对其进行评估；正是为了让系统具备可评估性，我们转向了能被评测的架构。

<details>
<summary>Original English</summary>

So, I just want to highlight one point, and we went through all of those kind of categories of grading at the at the bottom. Exact match or code that are very fast. As soon as we step into LLM as a judge, it's can be very fancy, it can be very useful. It's so hard. Like, we got so much noise from the LLM as a judge compared to the noise with the with the agent that we building.

Solving this problem is actually almost as hard as solving the the the right problem. So, finding the right prompt of the right harness for the LLM as a judge is a very hard task. There's some padding you can do. task. You can do fact checking. You can do a bunch of stuff, but actually it require so much work and we could not found the right one for this project.

There's plenty of other techniques. I won't go over all of them. For example, trajectory. We have another project that require the agent to eat some hand points. So, trajectory you can you you know what the end point should be in some order. You generate a story about it. You ask the LM to fill to use the agent and look at the trace to to see if the the trajectory is correct. Test to SQL, you might already know it.

Doesn't matter what your agent is. If you know how to pick the answer, if you know what you're looking for, and I showed a couple of examples. Generate the input and then try try to find it. Doesn't apply to everything. And sometime we had to re-engineer our solution to fit this paradigm, even if we move away slightly from the original design of the solution. We could with the original design we could not evaluate it. We switched to something that we can actually evaluate because of that.

</details>

需要提醒大家的是，测试的生成绝非终点。你生成了测试集，优化了 agent，随后会拿到真实的业务反馈。专家们会提供反馈意见，但我们并不会直接拿着这些零散反馈去临时缝补 agent，而是用这些反馈去生成更好的测试用例、提炼更好的 prompt、构思更精妙的剔除条款思路等等，实现一轮又一轮的闭环迭代。这套流程可以通过很多现成工具来支撑。非常感谢主办方的邀请。

这就是我的总结页：为什么一定要“答案先行”？我想我已经解释清楚了。当你生成了这些测试集，它依然不足以直接证明产品是否可以上线发布，这只是一个起点，是一个帮助开发者做前置预测的工具，它本身并不是解决方案上线的唯一准入裁决（go / no-go）。希望大家喜欢这场演讲。我知道走出“24小时无评估快速上线”的习惯是最艰难的一步。如果你也想戒掉“不加评估就交付 agent”的瘾，我很乐意提供支持并交流经验。非常感谢大家！

<details>
<summary>Original English</summary>

One thing to highlight is not the end of the day. You generate the test. You get a better agent. You get some real feedback. So, expert can provide some feedback and we don't use this feedback to fix the agent. We use this feedback to generate better test. Better prompt. Better ideas how to remove clauses, etc. etc. And one loop at a time.

That can be done by Rise. There's a lot of tools there. Thanks for the invitation.

>> [snorts]

>> Um and that's my conclusion slide. Why the answer first? I think I I explained that. When you generate those tests, it's not enough to know if you can ship the product. Just a starting point. It's a tool to help anticipate the developer. It's not the go no go for the for the solution.

So I hope you like this this presentation. I know that the 24 hour chip is the hardest one. If you want to quit releasing agent without evaluation and I would be happy to support you and have your own feedback. Thank you very much.

</details>