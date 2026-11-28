---
author: AI Engineer
date: '2026-10-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=YvQ4BVTWfHI
speaker: AI Engineer
tags:
  - llm-inference
  - quantization
  - sparse-attention
  - speculative-decoding
  - workflow-optimization
title: 更快的模型真的更快吗？从完整工作流视角评估大模型效率与隐性成本
summary: MiniMax 研发团队探讨了更快的 AI 模型在实际业务落地中的隐性成本。针对金融研报等长上下文、严谨推理任务，单纯追求吞吐量或首字延迟并不等于提效；模型在稀疏注意力、KV 缓存与专家量化（MoE 4-bit）、推测解码及不同推理预算（Thinking Budget）下的优化，必须回归到端到端业务交付质量、人工修正成本与系统并发延迟的全局检验。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - MiniMax
products_models:
  - M3.1 Flash
media_books: []
status: evergreen
---
### 速度的假象：完整任务闭环才是衡量效率的唯一标准

在将 AI 引入生产工作流时，面对推理速度更快的新模型，团队最常面临的决策难题是：**“我们是否应该切换到这个更快的模型？”**。如果一个更轻更快的模型生成一份行业调研报告仅需几秒钟，但其中遗漏了一处核心信源，人类分析师就必须手动核查、补充原始文档并修正数据。这种反复打补丁的人工成本，往往直接抵消了模型推理节省的毫秒级时间。因此，单次生成的 token 吞吐量并不能代表工作流的真实效率，衡量模型价值的真正尺度，是交付一份无需返工、可验证的**完整交付成果**（Finished Job）所需的时间与总成本。

为了具体量化这一问题，我们以真实的金融研报分析为基准场景：面对“随着 AI 服务器需求爆发，上游印刷电路板（PCB，Printed Circuit Board）供应链企业是否成功将营收转化为自由现金流”的专业问题，模型需要跨越 14 家上市公司的财报与研报展开对比。它不仅要对齐财报周期、区分不同业务板块，更要精准解释财务数字背后的含义——例如利润增长但经营性现金流为负时，指出客户应收账款积压或原材料存货增加的附注披露。合格交付的标准，在于分析师能否顺畅点击引用的信源核验每项主张、复核计算公式，并评估反方证据。围绕这一标准，MiniMax 在最新推出的大语言模型 **M3.1 Flash** 中，从长上下文注意力、量化存储、推理架构到并发服务展开了底层改造，而每一项底层算力优化都必须经过业务闭环的严格审视。

<details>
<summary>Original English Source</summary>

Uh I'm Morgan from Minimax. Uh how many of you knows Minax before? Oh wow. I like that. Yeah. Because uh I joined this M uh company for three almost three years. But when we first like step into the American market like uh almost no one knows us. But at that time we have the first video generation model. So I will show you something of that at the end of this speech. But first I will show you like about our the latest language model which will be released next week. So uh today um I would like to my topic is the hidden cost of a faster model.

So when people thinking about like if you have a AI application your product built in in your own pro workflow. So when a new model arrives when I say oh please we have a new model do you want to try it? It can generate a task faster but your I think your question is should I switch to that model? So you try a research task and the report just comes back very soon and but it misses a very important source. So someone has to find that source and fix that report. I think this is the thing we did every every day. So did the job really get faster with this faster model.

Today we will look at how we reduce the model computation and then we will ask how to test the value of those changes of this model. So let me show you the job that we will use to answer this question. So at minimax we build different multimodel models and pro products that people use and a quick chat reply and research report actually have different needs. So the task tells us what good performance means. Today I will focus on our latest uh large language model M3.1 flash and one research job.

So here's the analyst question as AI server demand is growing are the companies supplying the circuit boards turning this growth into cash? The PCB there means printed circuit board. I think you guys know that. and unc it connects electronic components that inside devices that such as the AI servers. So our research case looks like companies in this supply chain. The internal review describes work across 14 company reports and the model has several jobs. It must find the right reports. It must compile the same reporting periods and it must keep different businesses separate. Then it must explain what the numbers mean.

Think about the analyst who receives the report. They need to open the source behind an important claim and they need to check a calculation. They need to see what evidence could change the conclusion. So a useful report gives the analyst something that they can check and that is our standard for a finished research job. So when funding shows why those checks matter. This internal review highlighted a very useful distinction. So profit can grow but cash flow tells a different story. A company sells more so is reported pro profit rises but customers have not paid yet or it has uh bought materials that are still in storage. So the anal the analyst needs to know why the model should point to the cash flow statement and the relevant is disclosures. So a report earns trust when it claims can be checked and the internal review here describes the research output. So we still need to verify it sources and calculations and also we also need to measure the time and cost on this same job. But the technical task a heart use separate tasks. So they help us to understand specific trade-offs.

</details>

### 长上下文与稀疏注意力的权衡：大海捞针与位置敏感性

在深入模型内部结构时，开发团队往往面临四个核心技术抉择：如何削减注意力机制计算量、如何在存储与数据搬运中节省带宽、高并发部署如何影响终端排队延迟，以及如何灵活配置思考算力预算。面对行业普遍宣传的 100 万 token 超长上下文窗口，真正的技术考验并非“能否塞入数据”，而是在巨量信息中能否快速且无差错地定位关键细节。在数十页的财报中，不同段落对于特定分析目标的信息权重天差地别，这正是引入**稀疏注意力**（Sparse Attention: 一种仅对筛选出的相关上下文计算全量注意力权重的优化算法）的底层动力。

在 M3.1 Flash 的设计中，注意力机制被重组为一个两阶段计算流：首先执行极轻量的预选步骤，动态对全量文本块进行相关性打分并选取高分块；随后全量注意力层仅聚焦于被选中的核心块，同时保留邻近上下文窗口。由于筛选过程完全随分析师的 Prompt 查询动态变化，不同问题会激活不同的上下文片段。为验证这一机制是否造成信息丢失，必须进行高强度的“大海捞针”（Needle In A Haystack）压力测试。在多达 39 项极限测试、输入长度达到约 83 万 token 的评估中，模型保持了全部通过。而在实际的金融任务中，这种验证更加严苛：团队将关键的现金流附注、财务冲突披露放置在输入文档的不同深度位置进行重复测试，确保稀疏化修剪不会因文本位置变化而漏掉致命证据。

<details>
<summary>Original English Source</summary>

With this job clear, so let's look at what changes inside M3.1 flash. This table shows the main changes inside M3.1 flash. So I will connect them to a few simple questions. First, where can we reduce the attention work? And second, where can we store and move data? And third, how does the serving setup affect the time a user waits? And fourth, we also control how much reasoning the model does. These choices affect different parts of the job and each knows a check against the result we want. So every optimization has to help the finished job.

And let's begin with how the model uses a long input. So nowadays I think every model says oh I have a very big context window like we said we have 1 million. So among this one million how it can help you to find the output find your result quickly faster and correct. So some passenger passages like in this report like miter just much more than others for this question. So sparse attention itself means like we uses a very small selection step first like the blue uh box there. So it scores the blocks of the tax and the main attention then calculation calculate the uses of the selected blocks and the model also keeps the nearby tax in view and this selection actually they can change with the query and different questions can also needs different passengers of the the context and the number on at the bottom show how much text is published examples lacks and the full input can be much longer.

For our research job, the places at different OP positions in long inputs. So in v run the model passes all 39 requests and the longest inputs were about uh 830k uh tokens. So the result covers the cases in this test and for our research job we need with real reports. Can the model find a cash flow footnote? Does it use the right reporting period? And can it spot a conflict between different documents? So move this important passage to different places in the input and then ask the same question again. A long input is useful when the model can find a key fact. So finding the evidence is one track too.

</details>

### 低精度量化陷阱：平均分表象下的特定能力坍塌

解决上下文计算开销后，数据在芯片与显存之间的搬运成为了另一个主要瓶颈。在自回归生成过程中，模型依赖保存前序上下文中间计算状态的**KV 缓存**（KV Cache: Key-Value 缓存，用于加速 Transformer 文本生成的中间注意力矩阵），M3.1 Flash 将其中键（Key）和值（Value）的表示从标准的 8-bit 量化压缩至 4-bit，同时保持查询向量（Query）在 8-bit 精度，大幅削减了显存占用与传输能耗。然而，评测基准展示了量化带来的潜在代偿：在整体评测集上，4-bit KV 缓存的综合平均得分与全精度几乎持平，但在特定的科学与符号推理（Science）得分上却出现了 6.6% 的断崖式下跌。这证明**宏观平均分极易掩盖关键维度的致命缺陷**，如果用户的核心业务恰好依赖受损的能力项，轻率采用压缩模型就会直接破坏最终交付物的准确性。

同样的量化权衡被应用到了混合专家架构（**MoE**架构: Mixture of Experts）的专家层中。在 M3.1 Flash 中，被路由激活的特定专家采用 4-bit 权重与激活值（Weights & Activations），而共享专家则维持原精度以保障基础表征。虽然低精度大幅加快了计算并降低了访存带宽，但整个定点运算流程涉及数值缩放（Scale）、定点计算、以及恢复标度（Restore Scale）的精密流水线。标度恢复阶段在流水线中的先后顺序直接决定了数值误差的放大倍数。因此，硬件加速数学运算的每一步调整，都必须重新带入金融研报问答中进行端到端重算：验证引用的原始信源是否偏移、多期财报数据计算是否出现舍入漂移，以及生成的结论是否仍被底层证据严格支撑。

<details>
<summary>Original English Source</summary>

Next we look at the numbers we used inside this model. So the model keeps the internal information from earlier text which we call this KV cache. And M3.1 flash changes its keys and values from eight bits to four bits, but the query still stays at eight bits. And this can reduce the data we store and move. It also changes the position of that internal information. Look at that table. So the average scores actually is almost the same but the sign score there it drops like 6.6 percentage. So some but some other scores rises. So the average score actually can hide a mistake we your user cares about. This compares that two full setups but it does not tell us which changes caused each score. So for our research job we should check the output out output again. Are the sources right? Are the calculations right? And does the explanation match the evidence?

The same ideas applies to another part of the model is experts. Uh our model is the MO ine architecture. So it has the computing parts that we called experts which is the uh M of E experts. So it selects some of them for each token in M3.1 flash. These selected experts use four bit ways and act activations. The shared expert is outside this change and ways of stored model uh values and activations are values the model calculates and lower precision can reduce data movement and support more efficient computation. But the full calculation has several steps. So we scale the numbers, we run the calculation and restore the scale. The position of these steps really matters and the table shows like where scale restore happens and getting that order right is the part of getting the answer right. So fast math still has to be corrected. And when we check the complete result, we we measure the complete imp uh implementation. And for this research job, we run the same questions again. We inspect why the answers still miss our checks.

</details>

### 推测解码与服务排队：吞吐量繁荣下的长尾延迟刺客

在模型内部计算压缩之外，工程端常采用**推测解码**（Speculative Decoding: 一种利用小型草稿模型预先生成候选 token，再由目标大模型并行验证的加速机制）来降低生成延迟。理论上，目标大模型一次前向传播可以验证并接受多个 token，从而显著提升解码吞吐。但在系统工程层面，草稿生成需要耗时、目标验证需要耗时，而一旦候选 token 被大模型拒绝，回退重算的惩罚同样消耗算力。因此，推测解码节省的并不是绝对时间，必须连同验证失败与回滚的耗时一并计入系统开销；若落到金融研报这类事实性极强、容错率极低的工作流中，外层的向量检索、工具调用（Tool Calls）以及格式校验失败的重试代价，同样构成了总时延的一部分。

更具隐蔽性的是高并发场景下的服务排队效应。在实际集群压力测试中，当并发请求量从 32 提升至 64 时，整体系统吐字吞吐量（Tokens per Second）提升了约 1.9 倍（超过每秒 300 token），中位数等待时间依然在可接受范围内。然而，**P95 首字生成延迟**（P95 Time to First Token）却从 1.5 秒急剧恶化至 11.6 秒，飙升了近 8 倍。这意味着近 5% 的真实请求在开始输出第一个字符前就需要等待超过 10 秒。更致命的是，首字吐出往往只代表思考链的启动，并不等于可用结果的就绪。如果为了追求纸面吞吐而忽视 P95 交付红线，系统在生产环境就会产生不可承受的阻塞体验。

<details>
<summary>Original English Source</summary>

And now we look at insight. We have already look at inside the model. And now we can look at how it generates an answer for you. So a serving method called speculative decoding works in two stages. A faster draft process. It can help you to propose a short sequence of tokens and the then the targeting model can tracks it and the system keeps this first part that the target accepts and makes a correction when it's needed and then continues this whole process. And sometimes it keeps several proposed tokens and sometimes the draft does work what it cannot keep. So the opportunity here is to get several tokens from one target check and but drafting takes time checking takes time. Rejecting this tokens also takes time. So count the time spent checking the draft too. These checks propose tokens and but financial claims and sources need their own checks. So for our research job we should also include the source retrieval the tool calls and retries. The final measure is the time to a report that an analyst can really use in their home own work.

So even when one request runs well many users can change this diff experience. Here's an separate serving test. So it's uses the storage generation with low reasoning effort but the concurrence requests now like we rise from the 32s to 64. So the total output per second grows about 1.9 times but look at the weight time actually it the P95 weight for the first token rises. It goes from about 1.5 seconds to 11.3 seconds uh6 seconds. So for 95% of this request the first token arrives by this time and the weight now is becomes like eight times longer. So the medium stay as uh the the time that we can satisfy it. But we we cannot only look at the median time. So it changed everything that if we only like look at that one. So the users feel the weight and even when the throughput you see like oh we have through like more than 300 per second but still you need to care about the final weight time. So the first token may be reasoning and we will still need to measure when the usable report arrives. So set a dial line for that report. we choose a low that miss it

</details>

### 推理预算调优与上线核验协议：构建可持续落地的交付飞轮

除了硬件与架构优化，**思考算力控制**（Reasoning Effort / Thinking Budget: 控制推理模型内部思维链 token 生成上限的参数）是影响交付质量与延迟的另一个核心控制开关。在 M3.1 Flash 中，若不指定参数，默认会开启全量思考（Max Effort）。在代码生成基准测试中，将推理努力从最高档（Max）下调至高档（High）虽然节约了输出 token 并加快了生成，但任务准确率却直接从 80% 跌落至 68%。这表明压缩思考步数在复杂逻辑场景下存在明确的准确率惩罚。在长文本研报流中，粗筛和终稿阶段需要分配完全不同的思考预算：初版快速扫描可采用低推理预算，而最终用于决策的复核稿件必须赋予充足的思考空间以支撑复杂因果推导。

为了将包含上述全栈更新的模型安全推向生产，工程团队必须建立严格的**上线核验三步法**：
1. **真实可信核验**: 冻结基础资料库与知识截止期，确保对比基准完全一致。检查业务人员能否调出每一条核心论据的原始出处、验证跨期财务对比的口径，并复核结论所依赖的推导链路。
2. **端到端综合成本结算**: 放弃以每千 token 价格为单一计费指标的评估模式，统计涵盖向量检索、Agent 工具调用、超时重试以及人工二次修正工时在内的**单个合格研报综合成本**。在预期的并发规模下施加压力，验证交付耗时是否落在承诺服务等级协议（SLA）范围内。
3. **确定性复现与渐进式回滚**: 固化模型权重版本、运行时环境依赖、Prompt 参数与信源切片。留存所有边界失败用例，通过小流量灰度逐步放量，并始终保留能够平滑切回上一代稳定架构的双轨机制。

最终，模型速度的革新固然令人兴奋（正如 MiniMax 随后展示的使用旗下 **Hailuo 01 / A3** 视频模型自动生成的演讲总结），但在产业落地中，算力消耗的重构唯有转化为用户侧确定、按时且可信赖的端到端产出，更快的模型才具有真正的技术与商业意义。

<details>
<summary>Original English Source</summary>

and there's a one more setting that change the work we ask the model to do. So this is the first time we uh just use this different uh reasoning uh uh control. So uh from this part uh so this is the default max changes that we use in the request and it can controls how many tokens we use for this model thinking. So in the document setup here so thinking stays on but if we leave the effort blank the default is max. So a default can change the amount of work we request and one coding test there shows the tradeoff. So high reasoning and max reasoning. So the high uses fewer up output tokens than the max but the accuracy actually fell from 80% to 68%. So the fewer tokens came with lower accuracy on those task items. So give this task the thinking budget it really needs. So for our research job compare these settings on the same reports and check whether each setting finds the evidence and supports the calculations and the quick first pass on the report ready for review may need different budgets. So we need to record this setting or which reasoning control we need to put and then used in our later work.

Okay. Then when we ship this research workflow with all these um new updates we have with this model. First we can fix this question on the source reports and use the same information cutoff and agree on what makes a report acceptable before running this comparison and then we can check three things.

The first is can the analysts trust the report and open the resources behind the important claims and check the reporting periods recalculate the financial financial numbers and look for the evidence that could change the conclusion.

And second, what did the finished job cost? How long did they take? And include retrieval tool costs and retries. So if a person must fix the report before use, count that work too. So include all the failed attempts in the cost of producing uh of producing this acceptable reports. So test are the number of these users you expect and check whether reports arrive within the promised time and measure the cost of report you can actually use.

And the third one is can we repeat this result save this model and runtime versions and also save the prompt settings and sources. So keep these examples of failures and we can start with a small roll out and keep a way to switch back.

So before we finish, here's a short recap of today's talk. It's created with Miniax A3, our AI video model, and you can check here. Okay. So uh this is another model that we are working on and it's opened way. So everyone that who wants to build this actually it's only a one problem with the text to video.

Okay. So let's return to this uh our opening question today. Should we switch to a faster model and look at this finish job that we talking about for the last 18 minutes. So for our analyst that means a report with resources they can open and it has numbers they can check it must arrive when they need it and for uh this M3.1 flash changes how we spend computation and the complete task uh shows that those changes means for the user so measure what we cost to finish job and on time. So faster models uh I think like faster mo models really matter but what matter most is what we can do with them. Thank you guys.

</details>