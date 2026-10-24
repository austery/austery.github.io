---
author: AI Engineer
date: '2026-10-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UGjk3Uk0MxM
speaker: AI Engineer
tags:
  - model-evaluation
  - agent-architecture
  - tool-calling
  - prompt-optimization
  - synthetic-data
title: 大模型横向评测与 Agent 架构实战：从模型替换到 DSPy 自动优化
summary: 微软云专家 Pamela Fox 围绕多模型（GPT、Mistral、DeepSeek、Kimi 等）替换实战，系统剖析了单轮调用、多模态视觉、工具调用（单轮与循环）、并行规划效率以及代码断言与 LLM-as-a-Judge 评估体系，并演示了利用 DSPy 与遗传算法进行 Prompt 自动优化的全链路落地指南。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Microsoft
products_models:
  - GPT-4o
  - Mistral
  - DeepSeek
  - DSPy
media_books: []
status: evergreen
---
### 实战工作坊环境构建与多模型云端资源分配

在开展多模型替换与基准评估前，首要任务是搭建稳定且可复现的实验环境。本次实战依托 **Microsoft Foundry** 部署了一系列主流大语言模型，通过统一的环境变量与预置端点向开发者开放访问。由于实验涉及高频次的批量并发调用，极易触发服务商的 **速率限制**（Rate Limit: 429 错误状态码，表示请求速率超出分配配额），因此在环境变量配置文件中预备了多套备用端点以备动态切换。

为了抹平开发者的本地运行环境差异，工作坊提供了两种运行路径：对于本地开发环境，推荐使用现代 Python 包管理器 **UV**（UV: 基于 Rust 构建的高性能 Python 包与环境管理工具）快速执行环境同步与依赖锁定；对于希望免配置即开即用的开发者，则可以直接拉取预配置好的 **GitHub Codespaces** 云端容器化环境。在实际工程落地中，面对多模型横向对比测试，建立这种容器化、多端点热备的基础设施是保障评估流程不被网络抖动或配额耗尽中断的关键防线。

<details>
<summary>Original English Source</summary>

All right. Uh since it's already like 11:12, I want to start talking about the workshop. Um so, I'm going to do this as a guided workshop, so I'll go through all the examples up here on screen, um but you can also uh try and follow along. So, the repo is there, the environment variables are there. Uh so, the environment variables give you access to a bunch of Foundry models that I've deployed on uh Microsoft Foundry project. Um and they have a certain amount of token capacity. It is possible that we are going to go over the token capacity um in you know, in this session. Um I only got found out very recently that this workshop was accepted, so I tried to get as much resources as I could in the small period of time. Um so, in that EMB file, there is actually uh multiple different possible environment variables that you can comment in or comment out. If we do start getting 429s, um you know, uh rate limit exceeded errors. Uh so, yeah. So, I'm hoping that there's enough capacity for all of you to be able to try out those models, and uh we will see. Uh I also have my colleague Cedric here. Uh so, Cedric is going to be wandering around while I'm talking, so he might be able to help uh with with issues as well. Uh if you In terms of setting up the code, if you already have Python and UV on your machine, then you can do a get clone of the repo and run UV sync, and that should have everything you need to run the examples uh once you have that .env. Uh otherwise, you can make a GitHub code space. That's uh basically a VS code in the browser that has everything set up for you. Uh who here uses UV? Cedric wants to know. Okay. So, it's not number one yet. But, the other question here, who uses Python? All right, then more people. Okay. >> Pretty much everyone uses Python here. >> Yeah. Oh, did you count the overlap? All right. Okay. All right, so if you didn't take a picture of that screen yet, just take a picture of it now.

</details>

### 单一文本调用基准：参数化模型替换与知识幻觉差异

在进入复杂的 Agent 架构之前，评测体系必须从最基础的单一文本提示词调用（Single LLM Call）切入。通过将调用代码中的模型标识符参数化，系统可以低成本地无缝切换不同厂商的模型（如 OpenAI 的 GPT 序列、Mistral、DeepSeek 等）。在此基准场景下，核心考察点在于模型在脱离外部检索（**检索增强生成**，Retrieval-Augmented Generation / RAG: 通过检索外部私域知识库辅助大模型生成准确答案的架构）时，仅依赖自身预训练权重进行事实性回答的表现。

实验对比清晰地展示了不同模型在事实记忆与知识边界上的本质差异。例如，面对针对特定事实细节的提问，某些模型能够准确提取出事实，而另一些模型则因预训练语料的时间截断（Knowledge Cutoff）或对特定领域知识的覆盖不足，产生严重的 **事实幻觉**（Hallucination: 大语言模型生成看似合理但与事实完全相悖的内容）。这凸显了在设计生产级 RAG 架构时，首先必须对候选基础模型本身的固有知识底色与置信度阈值进行基线量化，否则外部检索注入的信息极易被模型的固有偏见或虚假记忆所污染。

<details>
<summary>Original English Source</summary>

in this repo here is a ton of different scenarios, and we can try out these models for each of them. So, we're going to start really really basic, all right? So, just a single LLM call that asks the LLM to do something. So, what you see for each of these files is that they all start off with the model variable and they default to GPT-3.5. That's kind of our baseline. It's obviously it's a very good baseline. And then, we can swap in other models. And so, what I've done here is I've deployed GPT-4o, GPT-4o mini, Mistral Large, DeepSeek, and so on. So, in the code, you'll see that you can just change this model string. And when we run this basic prompt, we're asking it a question that requires some specific factual knowledge. We want to see what does the model know out of the box, without RAG, right? Before we add RAG into the mix, we want to know what is baked into the model weights. And what you find when you swap between these models is that some of them actually answer correctly from their weights, and some of them completely hallucinate. And now let's go to Mistral. Uh, Mistral, sorry. Cedric, how do we say Mistral? It's French, right? French company? >> Mistral. >> Mistral. Cedric's going to be my French translator. Every time I need to say it, you're just going to say it. Now, Mistral. Mhm? Yeah, okay. Mistral. Um, so Mis- Mis- With Mistral >> [laughter] >> Um, we do see that Mistral actually answered uh, from its weights, but it answered differently than GPT. Uh so, it's it's something you want to evaluate when you're looking at models to use with rag is are the models already good at answering this kind of question, or do they completely fall down without external context?

</details>

### 多模态视觉理解的细粒度辨识与跨语言偏见

将模型从单一文本扩展到 **多模态**（Multimodal: 能够同时处理并关联文本、图像等多模态输入表征的模型架构）后，评估维度迅速转向对图像细节的细粒度空间与分类辨识。在展示的生物视觉分类测试中，向模型输入短吻鳄与凯门鳄（Caimans vs Crocodiles）的对比图片并要求辨别，直接暴露了视觉编码器与语义对齐模块的真实能力。许多模型仅能粗略给出笼统结论，而无法准确依据吻部弧度或牙齿排列特征进行严谨归纳。

更为深刻的系统发现来自于提示词语言引发的跨语言性能偏差。由于全球主流大模型在多模态对齐阶段重度偏向英文预训练语料，当将 Prompt 切换为西语（例如询问是 `caimanes` 还是 `cocodrilos`）时，模型的分类置信度与推理逻辑链条出现了显著漂移。这证明多模态能力绝非语言无关的抽象视觉算力；在落地非英语或全球化业务时，对特定多模态模型的评测必须将目标语言作为核心变量置于多维矩阵中进行综合验证。

<details>
<summary>Original English Source</summary>

Now, what's interesting with the multimodal, too, is that a lot of these also depend on the language, right? Here I'm using English. Remember, all these models are super English-centric, but if you switch to a different language, like if I ask in Spanish if they're caimanes or cocodrilos, it actually changes the results quite a bit. It's all figuring out what is the task you want to do and is the model going to do a good job at it? So here we pass an image of reptiles and we ask it to distinguish between them. With the vision models, some of them are able to pick out the subtle differences in the snout shape or the teeth visibility, while others just give you a generic answer like "these are reptiles" or guess wrong. And when you switch to Spanish, suddenly the model that was getting it right in English starts confusing the terms, because its multi-modal visual alignment in Spanish isn't as strong as in English. So that's a huge lesson for multimodal evaluations: you cannot assume that image understanding is language-agnostic. You have to test with the actual language and cultural context your users are using.

</details>

### 单轮工具调用基石：函数签名解析与 Schema 遵从度

所有自主智能体系统的核心基石，无一例外地建立在 **工具调用**（Tool Calling / Function Calling: 模型解析外部函数结构定义并精准输出符合规范的调用参数的能力）之上。在最底层的通信协议中，开发者向模型提供包含名称、描述与 JSON Schema 参数规范的函数签名。模型并非直接执行代码，而是根据用户意图进行语法级决策，返回结构化的函数调用请求。

在单轮工具调用（Single-turn Tool Calling）评测中，核心考量在于模型对参数类型的约束遵从度与隐式参数提取精度。例如在天气查询或简单运算工具中，模型必须准确把自然语言中的实体（如地点、日期跨度）精确映射至结构化字段。实验表明，顶级专有模型在标准 Schema 遵从上高度稳定，但在替换为轻量级或开源微调模型时，容易出现参数漏填、字段类型不匹配或输出无效 JSON 的现象。在构建更复杂的上层调用之前，对候选模型的基础 Schema 遵从率进行单元测试（Unit Testing）是不可逾越的质量底线。

<details>
<summary>Original English Source</summary>

All right. So, tool calling, also known as function calling. So, tool calling is in fact the basis of like all agents. All agents are based off of tool calling. And this is a a capability that the LLMs are trained with where you give them a list of tool definitions, like here is a weather tool or a calculator tool, with their parameters defined using JSON schema. And the model responds back not with natural language, but with a structured payload: here is the name of the tool to call, and here are the arguments as a JSON object. So in and this is like really low-level tool calling here. Uh once we build an agent, we're going to abstract on top of this, but I wanted to start with the most low-level tool calling we can do. And the LM just responds back with here's the name, here's the arguments. What we want to see like when we're doing tool calling, we want to see is it calling the right tool? So it is in fact picking the appropriate function from the list? And is it adhering to the schema, passing the right data types, not omitting required arguments? Some models are fantastic at this, and other models, especially smaller ones, might hallucinate arguments or return malformed JSON. So you always want to start your model evaluation with basic single-turn tool calling tests.

</details>

### 循环调用与多步 Agent 协同：状态流转与死循环控制

在掌握单轮工具调用的基础上，系统演进的下一步是构建能够持续感知与决策的循环执行器，即 **Agent 执行回路**（Agent Loop / Harness: 驱动模型在多轮交互中反复观察工具输出、更新内部状态直至达成终止条件的运行时框架）。以一个简单的数学计算代理为例，复杂的四则混合运算无法一步到位，Agent 必须将任务拆解为多道中间步骤，依次调用运算工具并将上一轮工具的返回值写回上下文消息历史。

在这一场景下，不同模型的工程化差距被急剧放大。高效的模型能够保持清晰的上下文追踪，在达到最终求解目标后主动发出终止信号；而推理能力较弱的模型则极易陷入两类经典失效模式：其一是 **无效冗余调用**，反复以相似参数发起无效查询；其二是 **死循环**（Infinite Loop: Agent 无法满足终止判定，在工具调用与错误状态之间无休止空转）。因此，在多模型替换评估中，不能仅统计最终回答的准确率，必须将平均调用轮数、无效重试率以及系统必须设置的最大轮数硬性阈值（Max Iterations Guardrail）纳入关键考量。

<details>
<summary>Original English Source</summary>

The next thing we want to do, we're building up to agents here. The next thing is to do tool calling in a loop, right? So when we have an agent, it's calling tools in a loop until it reaches a goal. Um so, we're going to demonstrate using this just a function calculate. So, this calculate takes a mathematical expression and returns back the output, right? And we have, you know, basic support for uh evaluating these uh mathematical expressions. So, we're giving it basic tools, and we're seeing can it take a multi-step math problem, break it down, call the calculate tool for step one, get the result back in the context, and then call calculate for step two? And so, you know, when we're evaluating two two models, we want to both look at the final answer, but we also want to look at the trace. How many turns did it take? Did it get stuck in an infinite loop? A lot of times once you have tool calling in a loop, the differences between the models is their efficiency and their termination logic. A really good model knows when it has enough information to stop and give the final answer. A weaker model might keep calling tools over and over again, or keep making the same mistake because it can't recover from an unexpected tool output. So you need guardrails like max iterations, but you also need to benchmark this loop behavior.

</details>

### 并行工具调用机制：复杂规划中的吞吐与容错差异

当面对复杂的复合型业务诉求（例如多城市旅行规划或跨数据库联合查询）时，**并行工具调用**（Parallel Tool Calling: 模型在单次推理轮次中同时发射多个独立的工具调用请求）成为衡量模型高阶规划能力的分水岭。在旅行规划场景中，若要查询某地多天的景点天气与酒店库存，顶尖模型（如 GPT 序列）能够在 Turn 1 瞬间并发分发 5-10 个独立的查询指令，从而极大压缩整体执行时延。

评测显示，各家模型对并行调用的支持与策略存在本质分化：
* **原生高并发决策型**: 能够在首轮自主并发生成全量检索参数，将时序调用大幅扁平化；
* **单步保守序列型**: 如部分轻量级模型或某些未深度优化并行 Schema 的模型（包括部分国产模型端点），即使底层支持并发，仍倾向于每次仅发射单条工具请求，导致交互轮次线性膨胀；
* **部分不支持或退化型**: 在要求并发时出现参数串扰甚至直接退化为纯文本描述。

这意味着在评估 Agent 架构的系统吞吐量与成本时，模型是否具备稳定的并行调用能力直接决定了端到端的用户感知延迟与 Token 消耗曲线。

<details>
<summary>Original English Source</summary>

Turn one, it says is parallel. So, one thing is you can do with LLMs is uh is like many LLMs support parallel tool calling where if you give them a bunch of tool definitions, they can suggest a multiple tools that can be called at the same time in the same turn. And this is huge for travel planning or research agents where you need to fetch weather for three cities, look up flight options, and check hotel bookings all at once. We're starting off with GPT here, and what you see is that in turn one, it generates five tool calls simultaneously. That saves massive amounts of time because you can run those external HTTP requests concurrently in Python with asyncio. But then when we swap over to other models—like Mistral, or Kimi, or DeepSeek—we see very different behaviors. Some models don't support parallel tool calling at all, or they just choose not to in this case. So instead of doing everything in parallel in turn one, it takes turn one, turn two, turn three, turn four, doing them one by one sequentially. Every framework has a slightly different tool calling loop, also called the harness. So you have to be aware of whether the model supports parallel tool calling, because if it doesn't, your agent's latency will skyrocket.

</details>

### 确定性代码评估：硬断言与测试用例驱动的基准构建

评测自主智能体的首要原则，是能够通过程序化代码进行硬性校验的地方，绝不引入不确定性。对于单轮或轻度多轮的任务，最可靠的评估手段是基于 **确定性代码断言**（Code-based Assertion: 使用确定性逻辑校验输出参数类型、枚举范围及严格匹配的测试方式）。例如，当测试系统是否推荐虚拟会议或线下参会时，只需直接断言返回的参数枚举值是否等于预期常量。

在构建工程化评估流水线时，关键步骤包括：
1. **构建覆盖边界的测试集**: 积累包含各种边缘情况（如闰年日期、跨时区、异常输入）的基准测试样本库；
2. **分离工具决策与工具执行**: 在评估 Agent 意图识别时，通常使用 Mock 数据拦截实际工具执行，直接测试模型生成的工具名（Tool Name）与参数载荷（Payload）；
3. **监控行为漂移**: 当后端模型版本微调或发生供应商切换时，运行全套单元回归测试集，以分钟级速度捕捉模型的行为衰减。

这种确定性测试的优势在于零外部开销、毫秒级响应以及 100% 的可复现性，构成了企业级 AI 工程流水线的第一道防线。

<details>
<summary>Original English Source</summary>

So, now we can talk about evaluations, right? So, we've been doing everything just, you know, running it manually on the command line. But in real life, you want to actually have bulk automated evaluations that you can reliably run and compare results, right? Cuz everybody asked me like, "How do you evaluate agents?" Agents are the hardest to evaluate because there's so much going on. There's so many different dimensions. But you always want to start with code-based evaluations where possible. So in this example, we can actually just do a straight string comparison say, "Hey, did it give back virtual, right? We wanted virtual for this, did it give back virtual?" So, when you're testing a single tool call, you can just check to see, did it call the right tool and did it use the right arguments? So, that's what we're going to do in this one. Um and we set up a bunch of test cases, right? Cuz when you're building an app, you want to have a bunch of test cases of user input to your evaluations to make sure that you don't drift, right? This is called regression testing. You want to make sure your model swap didn't break things that used to work. And code asserts are fast, cheap, and completely reproducible. Especially with things like date handling on leap years—evaluating an LLM on a leap year was hard! So having a test suite of explicit assertions is foundational.

</details>

### 基于 LLM-as-a-Judge 的高维评判与执行轨迹上下文注入

当任务涉及开放式生成、复杂推理逻辑或长文本摘要时，传统的字符串匹配或正则表达式无法有效衡量语义质量，此时必须引入 **LLM 作为裁判**（LLM-as-a-Judge: 使用能力更强的大模型依据详尽的评审准则对目标模型的输出进行评分与校验）。然而，粗糙地将最终生成结果直接抛给裁判模型往往会导致高误判率，因为智能体的很多致命失误隐藏在中间过程中。

正如评估方法论专家 Hamel Husain 所倡导的最佳实践，构建高质量的 Judge 体系必须遵循以下系统原则：
* **全轨迹可见性（Full Trace Visibility）**: 评估模型时不仅需要提供最终产出，还必须连同所有工具定义规范、调用的参数及工具返回的中间数据一并输入裁判提示词；
* **独立上下文冻结**: 预先跑完测试流程并固定执行轨迹（Trace Logs），将评估逻辑与应用运行解耦，避免在调试裁判标准时重复触发被测 Agent 的开销；
* **裁判本身的元评估（Meta-Evaluation）**: 在将裁判投入自动化管线前，工程师必须人工抽检裁判模型的打分准确率，防止“盲人给盲人引路”。

<details>
<summary>Original English Source</summary>

Sometimes in order to really evaluate, you do need access to more information. So like tool calls, if you're trying to evaluate whether it was an efficient user of tool calls, you can't you have to give it everything. You have to give it the tool call definitions. You have to give it the traces of the tool calls it made, right? So to build really good evaluators, a lot of times you're you're not just giving it the input and output, you're giving it the whole execution trace. So that's when we start to bring in LLM as a judge. You put an LLM in judge mode and say, "Okay, you are an evaluator. This is what you're evaluating and you need to either say does it pass or does it fail?" But as you see, it is hard to build judge evaluators! A lot of times what you realize is that your evaluator is incorrect, right? Like that you haven't written good evaluator. I should recommend if you're interested in evaluation, Hamel.dev. Hamel Husain writes a lot about this. You have to evaluate your evaluators! And the best practice is: run your agent, get all your context and traces recorded beforehand, and save that. Then you can change and iterate on your evaluator independently from running your expensive app over and over.

</details>

### 合成数据多维分层扩增与智能体专用评估套件

在工程实践中，启动模型评估面临的最大瓶颈通常是缺乏真实业务数据（Cold Start）。为了在系统上线前建立具备统计学意义的测试基准，可以借助大模型执行 **合成数据生成**（Synthetic Data Generation: 利用模型生成具备特定边界分布的大规模模拟测试用例）。为了防止生成的数据集同质化，必须引入 **分层抽样设计**（Stratification: 按照预设的多个正交业务维度对生成样本进行特征空间分割）。

在旅行规划智能体的评估案例中，分层策略具体体现为沿不同维度施加压力：
* **预算约束维度**: 充裕预算（Ample Budget）、极度紧张预算（Tight Budget）与隐式未知预算；
* **用户画像偏好**: 商务极简型、亲子休闲型、文化深度型；
* **环境异常输入**: 恶劣天气扰动、公共假期闭馆冲突等。

利用微软推出的 **Agent Evaluation SDK**，开发者可以基于上述分层矩阵一键生成数百条覆盖边缘场景的合成数据集。针对每条样本，SDK 会自动化跑出完整调用链，并结合定制的无参考依据（Groundness）与语义相关性评判器，快速构建起从冷启动到量产上线的质量护城河。

<details>
<summary>Original English Source</summary>

we can we can give it more information if we know, like, "Oh, we care about ample budget, tight budget, invisible." Um you know, so, you can you can stratify it. This is called stratification. You can you can pre-stratify if you want, uh or you can just have it come up with the synthetic data. And then we have the actual thing that's evaluating. This is the LangChain travel planner that we saw before. And it's interesting cuz it's saying, "When you are doing evaluations, you do want to see every single tool call so that you can really properly do these evaluations." All right. So, then it runs it all, and then we can see the results. It's really hard to bootstrap your evaluation before you go into production, but you want to have evaluations before going to production. So synthetic test generation helps you bootstrap that test set following best practices. Most of the times the built-in evaluators—like basic generic groundness or relevance—are not what you want. You want to build custom evaluators tailored to your domain. And that's what this Agent Evaluation SDK helps you with: bootstrapping custom test cases across stratified dimensions so you have real coverage.

</details>

### 基于 DSPy 与遗传算法的系统级 Prompt 自动搜索与优化

评估体系的终极目标并非仅仅给出静态分数，而是反哺系统工程，实现提示词与推理管线的自动化优化。传统的手工“调提示词”（Vibe Tuning）在面对跨模型迁移时极其脆弱。**DSPy**（DSPy: 斯坦福大学开源的声明式大模型编程框架，通过编译器思想将提示词与权重优化转化为代码逻辑）彻底改变了这一范式：开发者只需编写声明式的输入输出契约与指标评测函数，Prompt 则被完全视作由编译器生成的“汇编副产物”。

更具突破性的是结合 **GEPA 遗传帕累托算法**（GEPA / Genetic Pareto Algorithms: 模拟自然选择与变异机制在多目标约束空间中搜索最优解的高阶优化算法）：
1. **参数化编译**: DSPy 以评估得分作为反馈信号，通过类似“爬山法”（Hill Climbing）的遗传迭代循环，自动变异并生成候选提示词；
2. **约束自适应求解**: 针对新模型的固有特性，算法自主寻找能够满足测试断言的最优 Prompt 结构；
3. **降本增效突破**: 产业界案例（如 Dropbox 与 Shopify）证明，通过 DSPy + GEPA 自动调优，团队能够成功将原本依赖顶级昂贵大模型的复杂任务迁移至体积更小、单价更低的小型开源模型上，同时在严苛评估集上保持甚至反超原有的准确率基准。

<details>
<summary>Original English Source</summary>

Now, the last thing I want to show is DSPy. Has anyone used DSPy here? Cool, a couple people. So DSPy, the idea of DSPy is that you declare your program like you say, "Hey, I'm making a pipeline that takes these inputs and produces these outputs," and you specify your metric or evaluation. You check the constraints of your program and then DSPy is going to figure out the prompt that adheres to those constraints. So, DSPy is going to write your prompt. You're basically checking your spec in and then having DSPy write the prompts based off of doing evaluations and seeing, "Hey, what prompt is going to satisfy those constraints?" And it actually uses this cool algorithm called Jeppa (GEPA), genetic algorithms. It can use these genetic algorithms in order to come up with the next best prompt to try, which is really really cool to watch it do that. The prompt is an output from this DSPy process, right? And that way DSPy can keep iterating, hill climbing, right? Basically hill climbing on your evaluation metric until it finds a prompt that satisfies your criteria. There are great case studies from Dropbox and Shopify about how they've used DSPy plus GEPA so that they can move off the larger expensive models and onto smaller, cheaper models without sacrificing quality. Once you have a rock-solid evaluation harness, DSPy can do the optimization for you automatically.

</details>