---
author: AI Engineer
date: '2026-07-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=eAXxdtNlK04
speaker: AI Engineer
tags:
  - agentic-loop
  - prompt-optimization
  - observability
  - domain-expertise
  - evaluation-metrics
title: 停止空转 Token：为什么智能体自我进化需要注入领域专家经验
summary: 本文探讨了如何构建高效的 AI Agent 自效优化循环。Langfuse 的 Annabell Schäfer 指出，传统的宽泛评估指标由于缺乏确定性，难以作为有效的反馈信号。为了避免 Token 的无谓消耗，开发者应与领域专家紧密合作，将行业经验提炼为高强度的确定性“是/否”评估器与具体案例，从而引导 Agent 围绕特定边界进行精准、渐进的自我迭代与泛化验证。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Langfuse
products_models:
  - GPT-5-Nano
  - Claude-4.8-Opus
media_books: []
status: evergreen
---
### 智能体循环与目标函数困境

**智能体循环**（Agentic Loop: 智能体在环境中持续感知、规划并执行的闭环控制机制）已成为当今 AI 应用开发的最前沿趋势。然而，目前的自动化研究与自我改进（Auto-improvement）大多是从开发人员的视角出发。以代码编写为例，自动化优化之所以能取得良好效果，是因为它拥有一个极其明确且具备强确定性的**目标函数**（Target Function: 评估优化方向是否正确的基准指标）——即代码是否能够编译成功。尽管编译通过并不等同于代码完美或功能契合，但它至少提供了一个明确的交付底线。

然而，在医疗合规、健康管理或各类垂直行业问答等非编程领域中，这种“是/否”的确定性基准往往不复存在。为智能体设定的优化目标天生就是不完整且模糊的。开发者最初设想的优化方向可能与最终的全局最优解大相径庭，这导致智能体在无序的自我迭代中消耗了大量 Token 却无法取得实质性的提升。要突破这一困境，就必须深入构建能准确捕捉业务意图的评估器，这是实现智能体持续平稳升级的核心基石。

<details>
<summary>Original English</summary>

Hi everyone, my name is Annabelle. I'm a growth engineer at Langfuse and we're the largest open source observability and evaluation platform for your AI system. And today I'm going to share about how you should stop burning your tokens and why you should start building in domain expertise early in into your loop design, but also into your overall application design to make sure you're continuously improving and updating your application.
It is June 2026 and the whole internet is about loops right now. So we have Boris Journey saying he doesn't write any prompts anymore. He has loops and Peter Steinberger being like you should be designing loops and not prompt your agents. And I mean the whole Karpathy auto research and auto improvement topic blew up earlier this year already. But all of them are coming a little bit from this developer perspective.
And coding is one for for a good reason. One of the cases where this whole automatically reaching a goal worked quite well because they've always had a at least one target function that was quite clear. And this was does the code compile or not. And of course just because code compiles doesn't mean it's great and doesn't mean that all the features are exactly how you wanted them. But you at least know that you shipped something that worked. And of course this was then expanded over time to expand this target function. But essentially it's a does it work or does it not.
In all other fields and especially if you're building AI applications for some kind of domains like medicinal compliance or healthcare or all kinds of chatbots these target functions are not nearly as clear and a target that you give an agent is actually also always incomplete. So you might initially think that you're trying to head down here but actually your optimal destination is up there and to get there and to understand this it takes quite some time and to figure this out and it's yeah it's just inherently a difficult problem especially if you are in a field where a clear yes or no like does the code compile doesn't really cut it. So it is very difficult but at the same time we at length you see that the teams who are investing heavily here in the middle so making sure they capture what they actually want to work so the target function and build this out and make sure they have good evaluators that are evaluating this are the ones who manage to continuously upgrade and improve their application over time and also ship with confidence because if you know it's working as you intended to then you can also sleep well at night in case you push a code change.

</details>

### 自我优化闭环的实操探索

为了验证这一思路，我们使用 **Langfuse** 开发了一个极简的自我优化闭环，探寻最清晰的优化路径。我们选择了一项单标签分类任务——即对学术论文进行学术分类，其核心判定信号具有明确的对错界限。实验采用 **arXiv** 论文数据集，由作者标注的分类作为基准真相（Ground Truth），包含200条微调样本（Fit Data）、100条验证样本（Validate Data）和300条测试样本（Test Data），以此严格防止模型在优化过程中出现过拟合。

实验的主体智能体使用极低成本的 **GPT-5-Nano** 模型，初始提示词仅包含一份扁平的分类标签列表及基础的分类指令。优化器则采用了更强大的前沿模型 **Claude-4.8-Opus**。整个优化循环通过一个结构化的 Markdown 任务文件进行定义：首先在微调集和验证集上运行初始提示词以获取基线准确度；接着，利用优化器对微调集上的错误样本进行深度的“错误聚类”（Error Clustering）；接着，由 Claude 提出修改提示词的假设，并发布更新后的提示词。只有当新提示词在独立的验证集上确实提升了准确率时，该更改才会被正式采纳。实验设置的停止条件为完成15次迭代或准确率达到92%。

实验结果表明，该机制在首轮迭代中就带来了10%的断崖式准确率提升，从68%的基线迅速跃升至78%，并在后续迭代中攀升至83%，随后进入平台期。更关键的是，这一优化成果最终在未参与优化的300条测试集上泛化表现出了80.2%的成绩，充分印证了该优化框架的实际成效。

<details>
<summary>Original English</summary>

Okay, so now we know it's super important and you should be doing it, but at the same time it's almost impossible to actually get it right. So we were setting out and wondering what's the clearest cut target function we can find for an agent to use and also if you run an auto optimization on it what can we learn about the role of target functions from running it on it. And the clearest cut target function we could find was a single label classification task that has a very clearcut yes or no. So for example, let's say we have an item to categorize. There's a true label. For example, oh, it's an order. And then we have a set of available labels, order, complaint, inquiry. And our classifier then assigns one label. And you can very clearly say is the true label equal to the predicted label. And if yes, then this one is right and the next one might be wrong. And overall you can calculate an accuracy value and get a very clear signal from here.
So we put this target function together with an agent and also with an optimizer. And how this minimal loop looked like I'm going to share with you now. So here's our minimal self-optimization loop. Up there in the first two rows we can see our target function. In our case we opted for classified archive papers. So it's a set of papers that based on their primary title and abstract got a primary label from the author to categorize it for the other people in research. And yeah, we have the ground truth here and we have it in 200 items in a fit data set, 100 in a validate data set, and 300 in a test data set. Just to also make sure we're not overfitting.
Then we have our agent, which is more or less just a simple prompt based on GPT-5 Nano because we wanted to see how a very small and cheap model performs on the auto improvement because the good ones actually got really really good but also very expensive over time and we have this flash list of labels.
And then we have our optimization process that runs through Claude Code leveraging Claude 4.8 Opus. So one of the frontier models and it proposes the prompt updates and has this context reference the GPT-5 prompting guide as well as a task MD that is describing the loop.
Looking a little bit closer on how this looks like. Here we can see our target function in this case especially our fit data set within Langfuse. So we see an input column where the title and the abstracts are inside as well as an expected output column. So what kind of label should be applied. And on those three different data sets the idea is on the fit data set you run it, you look for the errors and especially error clusters, and Opus should then formulate hypothesis for prompt updates. In the validation set we then check if those prompt updates actually also generalize to unseen data. And then finally when we're like reaching a plateau or our stopping criteria then we're running it on a test set to see how well we actually generalize for untouched data that was not part of the training process.
Our base prompt is a very flat list of labels and just a simple task classify this paper with a label. Of course if we would write the prompt we would probably add some prose how to think about it and all of this. But we just wanted to see what happens if we use the very base version of this prompt and how the system is dealing with it.
And our loop is a step-by-step instructed loop done through a task markdown file. So the overall idea of the loop is first you run the base prompt on the fit and in the validate set to get like a baseline accuracy. You score it per item and overall. Then on the fit data set you do this error analysis. So you really look into what kind of categories frequently are done right, what kind of item pairs are maybe often confused and also what's then the underlying abstract and title belonging to it. So we can maybe find patterns there. Then Claude Opus proposes an update for the biggest error category and publishes a new prompt change and then reruns and only accepts if this also improves on the validation set. And we have two stopping criteria. Either it's 15 runs completed or we have 92% accuracy reached. And as soon as this is happening or it stops for some other reason, then we perform a final run on a test data set to see it.
So yeah, here on the right you can see all of this is described in a markdown. We point at the data sets and we not even give it the test data set link, so it will not look into it before we wanted to.
So what happened? Yeah, I mean overall we can see here that there's a tendency to increase but also we can see that we reached a 15% uptake from our baseline which is actually quite solid. The first run ended at 68% accuracy and on our third fourth iteration we went all the way to 83% which then also afterwards plateaued a bit. Overall it kept this level around 80% and we wondering okay actually we wanted the perfect clearcut target function. But then looking deeper into the data and how those labels are chosen we realize okay there's some creative freedom for the authors to choose what kind of label they want. So even though description might make sense, they might have chosen in that moment that they actually want to go for a different label and that's then also of course not recorded in here. And we also saw this improvement then generalized to the test data set on yeah to 80.2%. So the generalization was also on the 300 item unseen data quite good and in a way that you could say okay this actually worked and the most interesting thing we thought is that the first iteration immediately gained 10% and then it was only a little bit movement. So it somehow got a lot of information from this very first run already and made a big uptick that we can see here up until the yeah very close to the final result also.

</details>

### 优化机制：大模型提示词提炼

深入剖析 Claude-4.8-Opus 的优化路径可以发现，它所采取的并非人类开发者直觉性的优化策略。人类开发者的惯性思维往往是去为每一个标签添加长篇累牍的定义描述，但优化器大模型配合提示词指南却选择了一条截然不同的路径。它直接针对前一轮分析中捕获的特定错误模式进行“对症下药”，构建了以下三大维度的优化方案：

* **构建全局分类心智模型**：定义了模型在面对标签时的底层推理逻辑与分类原则。
* **制定相似分类决策边界**：明确规定了当面对两个高度相似且容易混淆的类别时，应该依据何种特征倾向于选择哪一个标签。
* **补充特定少样本案例**：针对最常混淆的“错误重灾区”，注入具体的正反样本进行引导。

在实现首轮 10% 的准确率飞跃时，Claude 的思考过程清晰地展现了数据驱动的魅力：它首先统计出微调集中的64个错误，识别出最占主导的几种混淆标签对，进而形成“该提示词更新将精准覆盖此类特定混淆模式”的明确假设。这种依赖充足数据和高强度反馈信号生成的假设，能够极快地捕获系统的最核心缺陷。这也提示我们，在优化初期往往可以通过捕获第一波高信号反馈实现低成本的性能跃升。

<details>
<summary>Original English</summary>

And we wanted to look closer into what it actually did here. So here we can see on the left side the flat label list prompt. So here on the left again a screenshot from our platform where we managed the prompts and on the right side we can see what happened. So the very first thing it added is a general classification approach. So how should the model think about the behavior of choosing one of these labels? So what's the main goal of doing so? Then there's some information on how to decide between two very similar classes and then also some related confused patterns. So it's basically telling it when to choose which and under which conditions and how to go about it and to rather go for the more specific label than for the more broad label because there's some implicit testing in the label structure as well. And then it also added some examples for the item pairs that it frequently missed or frequently misclassified. So this is what we can see here. So overall the approach was improvement loop added rules and examples and I would have probably I was surprised I would have probably spontaneously added descriptions to the labels. But the prompting guide or the model together with prompting guide decided that actually the right approach is here and I mean it worked. So I'm not going to interfere here.
Um yeah what we wanted to dive deeper a bit more then is what actually happened in this one 10% uptick that we have. So let me remove myself a little bit because we need the bottom right corner. So this is the reasoning step that Claude Opus 4.8 took in this one jump from 68% to 78%. And what we can see here is that it has a very clear okay we have 64 errors. These are the dominating patterns. These are the number one answer sink and this is the biggest confusion. So also what are the two labels that are most frequently confused and where there's like issues coming up. And then it's forming a hypothesis and saying okay this loop will extract exactly address this pattern. So it got a very clearcut clearly quantifiable and reliable failure mode because they were just wrong on a yes no right wrong basis. They also had a lot of data to look at. We had a 200 item fit data set which probably in most real cases yeah it takes some time to get there and to also like make sure that it was only 10 labels so each of them got covered like enough times that it can get a signal from it yeah and like this it could form a database hypothesis and ended up returning a 10% gain on the first run and then I mean it was a bit of movement and we also found a better version then but the biggest jump was just the very first one from a very clear-cut signal, we could have probably stopped there and already have very good baseline.

</details>

### 评估器重构：从模糊评分到高信号反馈

尽管二分类评估在学术分类上取得了巨大成功，但绝大多数实际的 AI 应用并不具备这种天生的确定性结构。业界目前广泛青睐使用诸如“正确性”（Correctness）、“友好度”（Helpfulness）或“幻觉判定”（Hallucination）等宏观的评估器。然而，当开发者试图将这些指标用作智能体自我优化的反馈信号时，效果却往往不尽如人意。大模型作为裁判（LLM-as-a-Judge）本质上具有非确定性，将指标量化为 0 到 1 或 1 到 5 的连续评分不仅无法提供稳定的一致性，还极其依赖对每个分值背后复杂标准的界定。

为了将这种“是/否”的高信号反馈机制移植到更复杂的垂直领域智能体或医疗合规提取等场景中，我们必须实现评估指标的微观化重构。开发者应当深入数据，与领域专家一起定制具体的二元质检标准：

* **事实性基准验证**：将模糊的“正确性”解构为“该回答是否完全基于检索到的知识库上下文？是/否”。
* **品牌与安全规范审计**：例如验证“品牌英文名称是否被错误翻译为其他语言？是/否”、“名称书写是否完全拼写正确？是/否”。
* **已知故障模式分类**：提炼出该业务场景下最常见的五类典型缺陷，要求评估器识别当前输出是否触犯了其中任何一项。

通过将宽泛的主观评分转化为高信号、离散的逻辑判断，开发者才能为自我改进循环提供稳定且清晰的“编译式”反馈。

<details>
<summary>Original English</summary>

So given this right wrong high signal feedback works really really well on this classification test but also knowing that this is not the case for all others like there's barely any deterministic yes no target functions in most cases. You will run it this time and next time you get a different next time you run the same evaluator you get a different answer from the same kind of evaluation you ran just because LLM as a judge is also nondeterministic. We were wondering how can we translate this right wrong high signal feedback into other applications. So how can we try to shape this in a way it also works for your vertical domain expert AI agent or for your automation of requirements extraction in medicine device compliance or whatever your use case might be.
And for this we overall see the approach working that while the market for a good reason likes those evaluators like correctness or helpfulness or hallucination which like early in the days were a good thing to go for. This is actually if you're trying to autoimprove against this a rather low signal especially also because it's put on a often on a scale out of like between zero and one and 10, one and five and for this to really work properly you need to define each of those numbers. What does it mean? In which context would you need which number? Which kind of criteria need to be met. But this is most of the time also not done. So it's just choosing a number between zero and one and depending on the context it might just totally change perspective and is therefore rather low signal and also probably inconsistent across runs.
What we see working instead is really looking into what are the quality criteria that you want to work for your application. So what does good mean? So for example instead of correctness the answer is based on the knowledge base yes no. So for example, if there's a snippet about internal information in the answer and you can check is it actually also in the retrieved context we did in the previous step or also if you're frequently struggling with using your correct brand voice you could look into okay is it this time correct? Did we make sure that our name was written correctly? I've also seen companies that have English names that are checking for did we not accidentally translate our name to Spanish? things like this. And also one thing that works well because it's also this categorization yes no is maybe some known failure modes. So which out of these five types of failures happened here and can you categorize it? And these are only a few examples. We usually see that these are created by looking into the data, understanding what good means, what are things that are important to you and especially to your domain experts and creating these high signal feedback loops. Because if you can't do code compiles, you need to wrap your head a little bit differently around what is good and what is not.

</details>

### 双轨协同：专家知识编码与多阶验证

在理清了评估器的运作机制后，具体的系统落地还需要依赖两层关键的保障：一是将专家知识（Domain Expertise）切实编码进系统的反馈回路，二是建立严谨的多阶验证流程。简单地将数据交给优化智能体是远远不够的，开发者必须真正与领域专家协同，将他们大脑中隐性的商业直觉转化为显性的系统规则：

* **专家经验案例化**：由专家协同定义边界样本与理想输出，通过共同分析真实运行日志，揭示那些专家认为理所当然、但系统并未掌握的隐性决策链条。
* **高信号评估器共创**：根据识别出的失败模式（Failure Modes），协同设计能够提前拦截问题的离散评估器。

在数据管理上，必须保留足够比例且具有代表性的测试集进行最终裁决，同时在循环设计中加入提前终止或“逃生门”（Escape Hatch）机制，以避免系统陷入无意义的循环并白白消耗 Token。当系统进入生产环境后，必须加入人类的可视化复核，因为用户真实的使用场景和系统的失败模式会随着时间发生动态漂移。最终的目标是构建一个专家经验、人类复核与智能体优化三者有机协同的泛化演进系统，从而真正让 AI 应用在实际生产中落地生根。

<details>
<summary>Original English</summary>

So this is the one side. The other part is of course the volume that you need. We had a like luckily we could have used thousands of examples. There's so many papers out there. We opted for like 200 train 100 validate 300 test just because we wanted to see that it properly generalizes but we made the experience that this already gave back a lot of high signal feedback so depending on the complexity of your application and the steps in there of course it might differ but having the volume there and having the high signal feedback oops are the foundation.
So how do you get there? So the most important thing we see is working with your experts and this is like repeated advice and everyone's saying it and everyone's saying talk to your customers. But here it's something you can actually start to encode the domain expertise into very concrete examples. So use them to create examples what should come out of it. Look at those samples, run sample runs together with them and also ask okay but why is it like this here and here the other way? Because like this you can often also get information out of them that they implicitly think is clear and also really understand how the decisions are taken there and like this identify failure modes of your application and also define what good means because you probably need both and then use them to find these high signal evaluators.
Then as soon as you have this baseline and you might hit production, review this data and don't review it only with your coding agents but review it as a human. Look through it, understand like what is the the scope initially and what is then being done with this application. This can shift over time. The failure modes can change. People might try to do other things and it's potential for feature expansion and to really understand how the system works and fails in production is necessary to cover the typical failure modes and catch them before your customers do.
And then finally think about the whole thing as a system that generalizes. So you're trying to build up examples that are representative of what you might want to hit in production at some point. And for this to properly generalize, you need to bake in mechanisms for validation. So like in traditional machine learning context, the validation approach is actually quite typical. So people all the time make sure that they're actually validating if things don't overfit. And this combined with like a real mechanism, combined with like the instructions in your loop and giving the system an escape hatch instead of having it work for hours and hours hitting a wall and burning tokens are very important divas to actually make sure that you're not just burning tokens but actually looping towards a system where a human and your agent together collaborate on an improving system.
Perfect. Thank you so much for listening to me. Very excited that you took the time. And if you want to know more about Langfuse and also how we think about these topics, you can find more on langfuse.com. And I'm super excited to meet some of you at some point in person.

</details>