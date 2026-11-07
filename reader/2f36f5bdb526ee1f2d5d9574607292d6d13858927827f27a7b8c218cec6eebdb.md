---
author: AI Engineer
date: '2026-08-02'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-npY6XjM8CQ
speaker: AI Engineer
tags:
  - benchmarking
  - reward-hacking
  - data-contamination
  - human-evaluation
  - large-language-model
title: 终结刷榜瘟疫：大语言模型基准测试的异化与重构
summary: 本文探讨了人工智能行业中基准测试刷榜（Benchmaxxing）现象的根源，深入剖析了高昂制作成本、数据污染、奖励黑客以及硬编码验证等导致基准测试失真的核心反模式，并提出以专业人类专家盲测为基础的质量最大化重构路径。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Surge AI
  - Meta
  - Anthropic
products_models:
  - Claude Opus
  - Claude Haiku
  - SWE-bench
  - IFEval
media_books: []
status: evergreen
---
### 刷榜乱象：指标攀升与真实体验的脱节

**指标刷榜**（Benchmaxxing: 模型在评估指标上取得虚高分数，但在实际应用中表现平庸）现象的根源在于技术行业的炒作周期。当新模型发布时，实验室往往会引用大量指标，甚至通过精细调整图表来夸大效果。然而，当用户在真实场景中使用时，期望与现实的差距便会暴露。这种脱节表明传统基准测试已无法准确反映真实世界的价值。以**LMSYS 竞技场**（LMSYS Chatbot Arena: 依靠用户盲测对模型进行排名的权威平台，转写中误记为 Elm Marina）为例，尽管大量预测市场资金在此下注，行业领袖和思想家却公开承认该系统极易被操纵。安德烈·卡帕西（Andrej Karpathy）也指出，他认为最优秀的模型往往与该竞技场的排名不符；实验室最终得到的只是“竞技场专用模型”，这些模型可能只是通过嵌套列表、项目符号和表情符号来迎合投票偏好，而非在整体能力上有所提升。

<details>
<summary>Original English Source</summary>

Let's get started. When will the benchmaxing plague end?
In the tech industry, we love a hype cycle. And in AI, we really love a hype cycle. And the way we do that is when a model comes out, there's a big announcement, there's a lot of benchmark cited. Sometimes to keep things interesting, we do a little chart crime. And then people actually go and use it. And if the expectations aren't met by the reality, then we have allegations of benchmaxing. Benchmaxing, of course, being when labs are training too hard on benchmarks in a way that deviates from what people actually care about.
So the existence of that term indicates that we have a sense that benchmarks don't always equal reality. And so in this talk we're going to figure out why does benchmaxing happen? Why are traditional benchmarks not always accurate reflections of real world value? Is this intrinsic to all benchmarks? And will we ever know which models are best? And the answers are incentives, poor methodologies, no and yes.
...
So we have a sense that benchmarks don't equal reality but the industry is dominated by a lot of popular but very bad benchmarks. So there's millions of dollars on prediction markets being wagered on Elm Marina outcomes even as we have industry leaders openly bragging about gaming Elm Marina and you have thought leaders like Wor saying it can be easily gamed. It's past time for the Elm Marina people to sit down and think about whether they're doing more harm than good.
Andre Karpathy had a similar observation when he noticed that the models that he thought were best were not lining up with what Elmarina was ranking. He said unfortunately the teams are not getting better models overall but better Elm Marina models whatever that is possibly something with a lot of nested list bullet points and emojis.
So why does this happen that sort of industry insiders are telling us that this benchmark is not useful but it still gets a lot of play. The problem is that AI is aimed at everyone in the world is is something everyone in the world can use. And so everyone needs some tool to figure out which models are best. And benchmarks are what we have for that. But if you can't if you don't have the ability to assess if a benchmark is good, what you do have is the ability to assess what's popular. And this creates this avalanche, this feedback effect where the conversation is very much driven by incumbency and marketing and less by real world value.

</details>

### 评测瓶颈：高昂生产成本与隐蔽的数据污染

构建高质量的基准测试面临巨大的成本与方法论挑战。以**智能编程基准测试**（Agentic Coding Benchmark: 评估 AI 智能体自主编写和修复代码能力的测试集）为例，若要制作包含 1000 个任务的测试集，假设每个任务需耗时 60 小时，而高级软件工程师年薪达 50 万美元，那么总研发成本将高达 1500 万美元。此外，随着模型能力的提升，每年约有三分之一的任务会因“饱和”而失效，需要额外投入 500 万美元进行更新。由于预算有限，许多项目转向使用低成本劳动力或 AI 辅助生成，但这无法突破前沿能力的边界。
更严重的问题是**数据污染**（Data Contamination: 测试集数据泄露至模型训练集中，导致评估结果失真）。以 **SWE-bench**（SWE-bench: 基于真实 GitHub 问题评估模型软件工程能力的基准测试）为例，如果给 Claude 3 Opus 输入部分提示词，它能一字不差地背诵出剩余内容及其标准答案。Surge AI 的调查表明，Opus 已经严重背诵了该测试集的内容。然而，在最新的 Opus 4.8 模型白皮书中，虽然大肆宣传其 SWE 分数，却未披露任何数据污染情况。这种信息不对称使消费者无法获得准确的模型评估。

<details>
<summary>Original English Source</summary>

There are a handful of key antiatterns that we're going to go through.
The first is price. Let's say you want to make an agentic coding benchmark, which these days is a very popular thing to want to do, and you want a thousand tasks in your benchmark. Each task takes 60 hours to make. Each software engineer in your workforce costs half a million a year. That's $15 million to make your benchmark. And if you think that over time about a third of those tasks are going to get washed away every year due to models getting better, that's $5 million to replace them. So that puts you out of budget for most projects. So then people turn to a variety of workarounds that have their own problems. One of which is trying to use a lot of AI assistance which ultimately does not really work. Like you can't push the frontier forward from within the frontier. You need to inject that external human expertise and it needs to be good expertise. If you try to use cheap labor, you're going to get what you pay for and the whole result is not going to be that useful. At Surge, one of our differentiators has long been that we are not trying to minimize cost. We are trying to maximize quality and part of that means paying a lot of money for good workers. We've always believed that but especially in 2026 models are just beyond the point where you can make do with anything less than the best workers.
Contamination is often thought of as when labs are explicitly training on the test set and that does happen sometimes but really contamination is the default outcome unless you are very very good. So labs put a lot of effort into holding back this flood of data that's going to contaminate their models. But inevitably if you have public questions and answers on the internet that's going to get memorized to some extent. So SweetBench verified here's an example prompt. You can give opus the first part of the prompt and it will verbatim spit out the rest. It does that with the answers as well. And we actually did an investigation where we compared looking at the repos that Sweepbench verified was built out of. How much has Opus memorized the Sweepbench verified contents versus the rest of the repo? And we found very clear evidence that Opus had memorized a lot of Sweetbench. In the most recent model card, Opus 4.8 talks about its SWE score. It does not disclose this contamination. We as an industry aren't really in the habit of doing those disclosures. And so what that means is that as benchmarking consumers, we're just missing that information.

</details>

### 指标投机：奖励黑客与校验机制的工程局限

在模型评估中，**对齐规避**（Reward Hacking: 模型通过寻找规则漏洞而非理解本意来完成评估任务）是一个普遍且棘手的反模式。梯度下降过程如同流水寻找阻力最小的路径，模型会以最“懒惰”和巧妙的方式满足字面规则，而非符合评测的真实意图。
同时，许多评测工具的校验机制过于简陋。在评估智能体企业级工具调用能力的测试中，验证器往往采用生硬的硬编码字符串匹配。例如对于电话号码格式，明明存在多种合法的输入形式，但验证器只死板地锚定其中一种。这导致 Claude 3 Haiku 和 Fable 在该任务上都只得到了 20% 的分数——Haiku 是因为犯了许多实质性错误，而 Fable 则是做对了 80% 但仅因格式不一致被扣分。这种粗糙的评测根本无法区分模型能力的真实差距，更无法作为预测 AI 重塑行业进程的“风向标”。此外，像 **IFEval**（Instruction Following Evaluation: 评估模型执行复杂、多约束指令能力的基准测试）这类知名评测集也缺乏真正的**产品感知**（Product Sense: 理解用户真实意图与体验的感知能力），包含大量反人类的矛盾指令（如“不能使用逗号”与“必须使用多次 T 字母”的拼凑），甚至在验证机制上存在漏洞，使得模型能够通过使用西里尔字母代替 ASCII 字母等作弊手段轻松获得满分。

<details>
<summary>Original English Source</summary>

Reward hacking is also a big problem. Reward hacking is basically when a model finds a lazy and creative way to meet the letter of the law, but not the spirit. You need to think about designing your rewards as a adversarial process against this maximally lazy agent. Gradient descent is basically like water flowing downhill looking for the path of least resistance. And so your verifiers need to be robust to that.
Another key challenge is simply just not having the ambition to make a sophisticated enough benchmark. Automation bench tests that agents are able to make tool calls in an enterprise environment. The problem is that a lot of the verifiers are these hard-coded string matches. And so you'll see it for things like phone numbers where there are many different acceptable phone number formats. But this verifier just picks one and the prompt doesn't tell you which one it is. So the result of this is that Haiku and Fable both score 20% on this task. Haiku scores 20% because it makes a bunch of mistakes and Fable scores 20% because it gets it right 80% of the time but then just happens to pick different formats. So if the benchmark task is not differentiating between Haiku and Fable, it's not a useful task. And more broadly, in 2026, many of us in this room are looking towards AI that's about to remake entire industries. And benchmarks are ideally our lighthouse on the horizon to let us know when that's coming. And a simple hard-coded string match is just not going to do it to measure that sort of impact.
Another important aspect of a good benchmark is taste. Perhaps it used to be the case that benchmarks were these dry academic, you know, questions and answer sets. But nowadays, a benchmark is an artifact expressing what it's an aspirational artifact. It's an expression of values of what you want your AI to do and how you want it to behave. And so you need to have some product sense in this process, some sort of a sense of what you want the AI to do. And that sense is unfortunately missing from ifal if has been cited on many model cards. And the way it was constructed was taking a bunch of arbitrary prompts that no user has ever asked in earnest and mashing them up with a bunch of other prompts to create a prompt set. The problem is that because no user actually has asked do not use any commas in your response or use the letter T at most once. You have to believe for this to be useful, you have to believe that there's a generalization from this to actual things that users are going to ask. If eval just happens also to have a bunch of prompts that are fully unsolvable due to having contradictory instructions. So this one starts by saying repeat this response verbatim and it ends by saying translate this into Hindi. Obviously you can't do both of those at once. Here's one that says write a riddle that includes exactly one bullet point. Make sure to include a few bullet points. Again this is just fully impossible. It uses a sentence splitter that does not align with how humans would actually split the sentences. And a lot of the prompts are not fully verified. So this one says write a story. There's nothing in the verifier that checks that a story was written. It just checks that the asky character I is not used more than once, which means that all of these responses get a full score, including response D. The way it gets a full score is by reward hacking and using the cerrillic eye character instead of the asy eye character. If is totally fine with that.

</details>

### 重构基准：严谨运营与人类专家的深度协作

高质量的基准测试必须具备严谨的工程化运营支撑。例如一些 **RAG 基准测试**（RAG Benchmark: 评估检索增强生成系统准确性的基准测试，如 Apex）在实际运行中，经常出现文档内容与评测参考答案不匹配的问题，导致给出正确答案的智能体反而被扣分。这种低质量的数据会诱发模型的**评测感知**（Eval Awareness: 模型意识到自己处于测试环境并调整行为的现象），使其偏离真实世界的数据分布。同时，实验室在刷榜时也存在缺乏透明度的行为，例如 Meta 在测试中暗中测试了 27 个模型变体以挑选最佳成绩，严重扭曲了测试结果。

为了终结这种刷榜乱象，评测行业和实验室必须引入更高标准的专家协作。Surge AI 推出了 **Hemingway-Bench**（Hemingway-Bench: 基于专业人类作家评估 AI 写作质量的盲测基准），因为写作是一种极其丰富、深刻且富有人类情感的活动，机械化的指标或“以大模型为裁判”的评估无法识别出真正优秀的文笔。通过构建由数千名专业作家、编辑和记者组成的专家网络，进行双盲模型对比，才能在模型能力不断攀升的当下，提供一条真正能保障质量上限的评测路径。

<details>
<summary>Original English Source</summary>

Another challenge is operational ability. Making a big benchmark requires a lot of QC work and plenty of organizations just don't make that investment. Apex is a rag benchmark where the agent is given files and then asked questions about them. And in some instances, what's in the file and then what's expected in the rubric don't line up. So an agent that does the thing that it's seeing in the ground truth is going to get a negative score. And a lot of the data in Apex is seemingly synthetically generated because it's full of obvious placeholder values or dates or places that don't exist. And so as a result, the model is more likely to develop eval awareness where it realizes that it's being tested which undermines the entire exercise. It also just takes you out of distribution from actual real world data to something that is obviously fake.
So that's an overview of some of the key antiatterns that happen during benchmark creation. But benchmaxing is a two-way process and there are all sorts of fun things that labs can do to benchmax and that's what we're going to talk about next.
So the the core value that we're all trying to get towards as human eval right AI exists to serve humans and so just having humans look at the responses and make ratings like that's what we care about. The problem is that human eval is very expensive. And so a lot of what benchmarks are doing is trying to get around that and you are trying to distill human preference into something more scalable and you're hoping you do that distillation in a way that's still sufficiently faithful to what human eval wants. But what this means is that inevitably there is a point where you can keep hill climbing on a benchmark and the human eval stays flat. And you can actually take it even further if you want where you keep hill climbing on a benchmark even as the human eval goes down. But if for whatever reason you think this is necessary for marketing or we have sort of organizational politics or incentives that are demanding this that's how it can end up happening. In this instance the prompt is what time is it? And the response is absolutely deranged. No human eval is ever going to choose this but El Marina puts it at the top of the leaderboard. So again, you have this divergence and if you're trying to benchmax, you just cannot care about that.
Another thing you can do that I've heard stories of is you can actually hire a crowdsource army to vote for you in Elmarina since Elmarina basically does no filtering of their workforce. And you might say, well, we anonym, you know, Elmarina anonymizes. So how are they going to know who to vote for? That's actually quite simple. You have your model include a watermark that tells the crowd who to vote for.
There's also all sorts of things you can do with running your evals in conditions that are like not fully representative of the applesto apples comparison you're trying to make and then not always being super transparent about those conditions in such a way that undermines the validity that the community is trying to interpret because they don't have that contextualizing information. This was a paper um again about Elmarina and talking about how some of the dynamics of how it's run lead to models overfitting on Elmarina. Um in this instance, the specific chart we're seeing is that Meta tested 27 models without disclosing that it was doing so. Um which you know distorts the results.
So how are we going to end benchmaxing? We need to hold the benchmark industry and the labs to a higher standard. The first thing we need to do when making a good benchmark is start with great human experts. And those experts inform everything that is downstream from what types of tasks are we going to have the agent do? How is success measured? What are the input files that agents are given? What are the tools that they're given? But we also do need that product sense. So imagine you're making a medical benchmark. It's not enough to have doctors who can answer specific medical questions because if you're trying to test how ready are we for agents to be deployed into hospitals. You also need someone with the business sense to know what's the regulatory environment, what's the legal requirements because that is going to impact what types of tasks you're trying to have the AI solve. You need high fidelity input data which is best done by going out and getting it from the real world, having actual people create this data. Synthetic approaches are possible, but it is very very hard to do it reliably. The tools need to actually work. A lot of benchmarks have tools that are buggy in various ways. And unless you're intentionally making a benchmark about buggy tools, this just introduces noise. You need verifiers that are fully aligned with the prompts. And this is a two-way alignment. So the verifiers need to be verifying everything the prompt asks for. And everything the prompt asks for needs to be covered by the verifiers. And if you get either side of those two misaligned, then it's going to be unfair to models and you're introducing random noise. You need to thoroughly QC everything and you need to have a private hold out set so you don't get contaminated.
And if you do all this right, then you'll avoid what often happens with benchmarks, which is when labs get to like 80% and say, "Okay, this is saturated." And I used to think that saturation was just them saying again we don't think training on this further is going to increase real world value. And it often does mean that but it can mean that because the lab is saying we realize 20% of these tasks are broken. But the problem is that as you're hill climbing you don't know what 20% are broken until you solve all the others. And so as a result you have a lot of noise. And if that 20% of broken tasks is randomly but in a biased way assigning the rewards, it's going to really distort the model relative ranking you're trying to get.
So at Serge, we created a benchmark called Hemingway bench to measure writing. There have been a number of writing benchmarks that use various mechanical means to try to assess writing quality, but we believe that writing is just too rich and deep and nuanced and frankly human of an activity to measure with mechanical benchmarks and LM as a judge doesn't really work either because LLMs don't have good taste in writing. Again, this is sort of the you can't expand the frontier from within the frontier situation. So what we've done is we've just created a workforce of thousands of professional writers in various domains, technical writers, poets, journalists, editors, and we just have them do blind model comparisons and then we create this leaderboard and it is quite expensive, right? Human eval is very expensive. Getting the time of these professionals is quite expensive. But again, our goal is to maximize quality, not to minimize costs.
So in conclusion, benchmaxing is the exploitation of benchmark misalignments between human preference, but we can do better and we can hold the industry to a higher standard. Both the people making the benchmarks like myself and the people who are reporting on the benchmarks. And if you'd like to be a part of that, of course, obligatory pitch at Serge, we're hiring for basically all aspects of that. Uh and if you'd like more spicy takes from me, uh please follow my substack. Thank you very much.

</details>