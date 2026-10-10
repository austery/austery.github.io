---
author: AI Engineer
date: '2026-10-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=TyPpSRXGhbc
speaker: AI Engineer
tags:
  - reinforcement-learning
  - tool-use
  - financial-ai
  - domain-specialization
  - model-distillation
title: 500美元训出金融专家：4B小模型逆袭235B大模型的强化学习实践
summary: Snorkel AI与UC伯克利Sky Computing Lab合作，基于高质量领域数据与RL强化学习框架，用不到500美元的成本训练出4B金融专家模型。该模型在真实财报问答与多表推理任务中准确率达60%，超越了235B参数的通用大模型，揭示出垂直智能体任务中数据质量与工具调用规范远比盲目参数扩展更为关键。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Snorkel AI
  - UC Berkeley Sky Computing Lab
products_models:
  - Qwen 2.5
  - RLM
  - GPT-4o mini
media_books: []
status: evergreen
---
### 尺度定律的破局点：小模型专业化超越百亿参数通用模型

在企业级 AI 落地场景中，盲目依赖**扩展定律**（Scaling Law: 通过扩大参数规模与计算量单调提升模型能力）往往面临高昂的推理成本与不可控的延迟。在真实业务工作流中，**领域专业化**（Specialization: 针对垂直领域工具体系与上下文约束进行精准对齐）的价值能够彻底颠覆单纯的参数规模优势。

Snorkel AI 联合 UC 伯克利 **Sky Computing Lab**（加州大学伯克利分校云计算实验室），进行了一项极具对照意义的实验：在模拟金融环境与真实上市公司财报分析任务中，一个仅有 40 亿参数（4B）的量化小模型，实现了近 60% 的**首轮通过率**（Pass@1: 模型一次性推理生成正确答案的成功率），而 235 亿参数（235B）的通用基座模型同等条件下的准确率仅为 51%。

这一突破背后的核心在于高质量的领域数据构建与精准的针对性微调。通过构建高保真的领域资产与强化学习环境，小模型不仅能够在特定复杂任务中与前沿模型打平，更能将训练与推理成本降至通用大模型的极小零头。

<details>
<summary>Original English Source</summary>

everyone, thanks for joining. i'm charles, and i'm a research scientist at snckl ai. and today, i'm going to be talking about how we got a four billion priminter model to outsmart it's two hundred and thirty five billion priminter variant. and this is a specific result in a simulated financial environment. but i think there are general takeways that i want to make sure taken home. and the first is for enterprise AI worworkloment ment by ability and specialization uh can actually outweigh raw parameter scale. and this is possible with high quality data that actually represents the domain and tandistmodels that just targeting ting. uh, this can result in smaller models that can achieve parity with frentier models that just a fraction of the cost. so before i get to it, i'm going to a take this opportunity to introduce ourselves a little bit. this is our team where a frontier, ai data lab and our team. we have founders from labs at university washington was consenins stanford and in a teral team of really talented after e researchers, and we're in a fortunate position to play budatamine build and deploy data asatts and environments for frontier ai, and that's at the intersection of academian industry research, but also grounded in enterprised depointments. and this is all to say that we have a team that built to focus on building the best state, a possible dedefine in vvance ai. and the way we do this is three folk first is open research and benchmark. so we're constantly contributing to open source venchmarking. and the project i'll be talking about today actually follows under this pillar. um but i also want to acknowledge front tier labb data environments as well as enterprise dipointments are, are the things we work on and under open research and benchmarks. we support research to grants, and i'll talk about opportunities here at the end of this talks. so get ready for that and then go authoring with academic or industry partners um in leading independent research and publishing open artifacts. so what i'm talking about today is um a partnership with uc berkey sky computing lab, and we built like i said, a four billion primarter quent model, two, apperformance two and thirty five, five illion model, l very unfinancial tasks. we saw the four billion primarter model spoiled alerert achieve almost a sixty percent past at run, while the two thirty five billion model achieve fifty one percent. so exciting results. and this is all in collaboration with i'tta credit or credit to minnunroopa, susian town from the sky computing labs, as well as vvicia in chris place in myself from snarkle, and you can find all the assets, the training scripts, synthetic data on our githuub. so check those out, and this is all open source and available to you. so i'll cover today what um we see financial institution name from ai. this is from our enterprised appointments um arnings as well as the finua open source benchmark. this is expert validated financial question, answering data that we trained our in a diyeway to er a model on. and finally, the training process for the RLM fincua for b model.

</details>

### 通用通才还是垂直专家：金融智能体的三重致命失效模式

当金融机构评估**智能体推理能力**（Agentic Reasoning: 结合环境观察、工具调用与多步反思的动态决策机制）时，核心诉求并不是写诗或通用闲聊，而是：它能否接入企业内部充斥着陈旧 API、杂乱 Schema 与历史技术债的遗留技术栈？它在面对多步长流程任务时，能否遏制错误级联扩散？其执行轨迹是否具备严格的**可审计性**（Auditability: 遵循金融合规要求、每步调用均有据可查并复现）？

现实中，企业级任务并不需要懂天体物理的“通才”；当面临专业财报与税务审计时，企业需要的是精通报表规则、工具指令与行业准则的“专才”。在基准测试中，即使是参数量庞大的通用前沿大模型，在金融数据处理场景下也暴露出三大系统性失效模式：

* **模式幻觉（Schema Hallucination）**：模型在预训练记忆的干扰下，凭空臆造并不存在的数据库表名和字段名称。
* **上下文洪泛（Context Flooding）**：模型盲目发出低效的全局查询（如无过滤条件的 `SELECT *`），将大量无意义的原始行直接倾倒进输入窗口，迅速击穿注意力与上下文容量上限。
* **错误恢复瘫痪（Poor Error Recovery）**：当工具或 SQL 执行报错时，大模型往往忽略系统的错误日志与反馈，盲目机械地重复原先失败的指令。

这些痛点不仅存在于二级市场财报分析，在保险核保等复杂金融流程中同样反复上演。

<details>
<summary>Original English Source</summary>

so let's can start it. this is the one in only side with the charle's dick and reference. i promise, but this is a tale of two models. i'd say, first, the large ge gennalist versus small specialist. and the point is here, when financial institutions ask us, how old does the model are, the agent reason what they typically mean is kind of operate in my stack of complex schemers, legacy api and techch debt. and can we trust it in realistic in long workclothes without compounding areand? and can we reliably audit the agent that's important in financial legal domains, for example, which brings us to question tion is how can we evaluate and improve the agents to make them reliable in these real world environments? so um the reflex may be to scale. we've all seen scaling law results. but today, i'm going argue that specialized workclothes don't actually need generalists. we don't need polymass you to when it call terntotaw for a tax on it. if you're lulucky enough to have him in your contacts, you call the specialist, that knows the forms, the tools in the rules. so that's why we built. thank you. ate, this is expert, validated financial question, answering data, and i walk through the multii stage pipeline of how we built this benchmark and training data.

</details>

### 数据合成与三重校验：构建高可信金融基准 FinQA

为根除大模型的工具幻觉与推理脆弱性，研发团队开发了经过专家严格校验的金融问答基准与训练数据集 **FinQA**。该流程直接锚定美国证券交易委员会 **SEC**（Securities and Exchange Commission）EDGAR 系统中公开的 **10-K 年报**（10-K Annual Report: 美股上市公司法定披露的全年综合业绩报告，包含大量结构化财务报表与业务附注）。

数据流水线采用严密的多阶段合成与过滤闭环：
1. **模式与表格抽取**：从 EDGAR 系统解析 10-K 原文，利用 235B 模型将半结构化财报转化为约 6,900 张标准化 SQL 关系表。
2. **专家引导的问答生成**：基于金融分析师制定的分类学模板（Question Taxonomy），要求模型为每张表格生成对应的深度问答对，并强制附带数据血缘与元数据追踪标签。
3. **三层校验防线（Three-layer Verification）**：
   - 第一层：**程序化一致性校验**（检查 SQL 语法、表名与列名字段存在性，确保 100% 杜绝模式幻觉）；
   - 第二层：**独立智能体交叉审查**（由独立 Agent 自动模拟执行并校验答案唯一性）；
   - 第三层：**金融专家人工审计**（验证业务逻辑真实性与问题专业度）。

最终从约 7,000 张表格中严格提炼出 4,000 条训练样本、500 条验证样本，以及 290 条严格按企业隔离（不同集合之间完全无公司重叠）的评测基准，且所有样本均对应确定、可单值验证的最终财务结果。

<details>
<summary>Original English Source</summary>

so first is schema and data extraction. this is coming from ten k reports. these are annual reports required by the escc for all public companies, and they're used by analysts for identifying risks and informing investment decisions. we pull this from the egar system and use the twenty three thirty billion model to produce tables, sql tables, approximately six thousand nine hundred of those, and we use each table to generate a single question, answer pair. and this is um produced, along with the question taxonomy that was developed with financial experts that work with these documents. and these are using as tetets for the model to generate a question ansspirir, along with meda data that will see uh what that's used for later. and finally, the third step is verification. and this is a three layer verification process. first is programmatic consistency checks. that's wewe reuse the mea data, which includes liniage and table names and columns and make sure we're not elulutionating those. the second is automated reviews from independent agents. and finally, expert manual reviews are humans actually going through these and making sure the questions and answers are realistic and verified, and the outcome is sarcles vinuate data. and this is our first pasass at this real less sequeries requiring planning, two use tool calling and reasoning and um answers are single, verifiable final answers. and from this um we get from the original set of roughly seven thousand tables, four thousand and train five hundred and vell, and two and ninety, and the held out benchmark and the data is split so that no company in the benchmark overlapse in any split. and on this data, we identified um even with frontier models, reoccurring, discipline, gaps, failure, modes, and the first is scheme of hallucination. so a model will actually assume that tables exist, calling names exist. and um this can be an artiffecof pretraining data, something it seem in pbest. the next is context flooting. so actually flooting its own context with with orly playing ququriies for examples, just calling select star um and this could overone with context, limits successful and finally, poor recovery from erabs. so twenty three, two, thirty five would actually repeat the same failld strategy. um insaid of considering the err messages in adapting and these failure modes are not actually just seen in the financial environment that i'm talking about today, but also what we saw an insurance underwriting. and this is a work that i'm calling out that was presented that the CAIS conference few weeks ago.

</details>

### 强化学习与极致成本：用不到500美元实现端到端智能体训练

在训练基础设施上，项目采用了由 UC 伯克利 Sky Computing Lab 主导开发的 **RLM**（Reinforcement Learning for Models: 面向智能体优化的轻量级强化学习框架）。该框架原生兼容任意 Agent 框架，只需极少代码甚至仅靠装饰器即可无缝嵌入，同时支持 **GRPO**（Group Relative Policy Optimization: 群组相对策略优化算法）、PPO 等主流算法后端。

训练环境被形式化为一个标准的 **ReAct 循环**（Reasoning and Acting: 协同思考、工具调用与环境观察的迭代循环）。模型面对近 7,000 张 SQL 表格环境，自主调用查询工具以寻找目标数据。核心工程架构与训练配置如下：
* **基座模型**：以 **Qwen 2.5 4B** 作为参数基座；
* **优化目标**：采用 GRPO 算法与二元奖励函数（Binary Reward: 仅评估最终财务数字是否完全一致）；
* **评判裁判**：使用轻量级语言模型进行基于真实事实的评判；
* **并行吞吐**：在 8 张 A100 GPU 上并发启动约 1,000 个环境实例采集交互轨迹（Trajectory）。

整套训练流程在不到 500 美元的总成本内完成（其中硬件算力约 420 美元，Judge API 调用仅约 40 美元）。在严格保留的 290 个专家验证金融测试集上，Qwen 4B 模型的准确率直接翻倍，成功逆袭 235B 通用大模型，证明了在垂直工具场景下低成本高精度的可行性。

<details>
<summary>Original English Source</summary>

so now we'll get into actually training the RLM finua four billion model. um for this, we used the RLM uh framework. and this is developed by the are sky computing, lab collaborators. and if you haven't used this yet, um this is a really user friendly tool in a few core features. um i want to call out is it really works with any agent and framework requires near zero code changes, just using a decorator pattern sea life, first workflow battle tested result. so we've seen our al m actually improved, not just on this finance um case study, but also in math reasoning, for example, multiple our algorithms are pill, ten GRPO reinforce oral. oh, for example, and you can customize those and then supports multiple training back ins, all right now for our training environment. um this is the training environment we use for our model. the agent runs in a react loop, and it has access to tools to interact with the tables we generated. the environment includes the roughly seven thousand tables we created. and finally, rereard ard as binary corretness ss determined by a language models judge. in this case, GPT five nano using reference based evaluation 没有没有 training details are listed here. this is, i guess would be interesting. the folks we have the quent three four billion model is our base model, jorpo and binariary reward for opoptizzation, the oil and framework. um we ran roughly a thousand concurrent environments to generate trajectories ies. this all was was a cost under five hundred dollars to get the results that we saw um broken down between compute roughly fourhundred and twenty and forty dollars for a judge. the judge API. and this is on eight one hundreds. the first result is the central question kind of four billion model on to to specialized tools and training actually compete with its larger variant. and the answer is, yes. so what we saw was actually debasase models accuracy more than doubled, and it our performs its larger variant the two thirty five primary model, and this is despite being a faction of the size, and we eiwait all model shown here on the exprecuated held ld out into ninety samples.

</details>

### 泛化性与消融实验：简单二元奖励与基础工具规训的胜利

针对该垂直训练是否仅是“死记硬背”单表题目的质疑，团队在两类外推数据集上开展了全面验证：
1. **多表复杂时序推理（FinQA Reasoning）**：引入需要跨 2 到 5 张财务报表进行级联决策与序列规划的评测集。结果显示，**工具使用纪律（Tool Discipline）能够零样本泛化**——仅在单表基础数据上训练的模型，在多表任务上自动展现出准确率跃升，无需复杂的多表微调。
2. **跨领域工具通用评测（BFCL 基准）**：在测量通用函数调用能力的 **Berkeley Function-Calling Leaderboard** 上，模型表现不仅未发生灾难性遗忘，在多轮对话与长上下文记忆能力上反而有微小提升，证实了垂直 RL 训练不会损伤通用工具调用素养。

数据配比与奖励工程的**消融实验**（Ablation Study: 通过剔除特定模块探究系统性能贡献归因）进一步得出了两个反直觉的核心结论：
* **课程学习适得其反**：对比“仅单表训练”、“单多表混合训练”与“由浅入深课程学习”，最精简的纯单表训练效果最为突出。这表明系统核心瓶颈从来不是深层推理链路，而是**工具调用的稳健度与基本功**。
* **二元奖励优于细粒度奖励打分表**：团队曾联合金融专家设计了对中间推理步骤、表访问准确性、查询完备性进行加权赋分的精细**打分细则**（Rubric Scoring: 针对复杂认知行为设计的结构化评分标尺），但实验证明，最简单的最终结果二元奖励反倒促成了最高的性能收益。过度人工干预的奖励工程容易诱导模型过拟合，而端到端的二元成败反馈更利于策略探索。

<details>
<summary>Original English Source</summary>

so a natural concern is whether this actually transfers to harder problem. so this is just single question, answer pairs on a single table um and do investigate this. we uh looked at our thanua reasoning data. so this is a development on the thanua um data presented earlier. and the difference here is not now we're having a dependencies on multiple tables, two to file tables. and requires sequential decision making and planning, and we evaluated on this dataset. you can see the breakdown um as well. we have roughly thousand and train hundred twenty and validation eight in benchmarked. um and what we see is the toilous discipline actually generalized directly from training on the simple data, and no explicit training on multitable. examples was needed actually to see lift. and uh this mutitable um um vary of the dataset and will investigate why with abablish studies. uh. but the next concern we had was whether this result will generalized to more general use cases. so for this, we use the bf CL benchmark and um this measures general two calling capability. and um all accuracy y um um actually slightly improved and and um we had also minor gains and multii turn and memory. so specialization didn't actually erode the models brouadter two use competence when we did our al fine tining for this model. so to isolate would drow this performance. we ran a blation study on data mexures. so different ways, we can um combine the training data we had. the first is just training on vinuate data and the second single and more tile set and finding a curriculum where we start with single then moved to more diet. and surprisingly, just training on the simpler set um resulted in the most left. um and this parture that explains why um the genereralization result we saw earlier the bottleneck was never reasoning debt. it was just two use, meaning the motorwhere. it was actually failing and improving the reliability of that. and once you master with the fundamentals, it could compose those skills. yeah. so oooes. can you go back? um the next national question is whether more informed of reward signals, for example, rewarding intermediate steps table acaccess query completness things like that could actually accelerate learning. um so this is different from curricum, for example, and the most sophisticacavariariant came came up with was a rubrick. and this uses find green scoring with um multiple waited components. and this has actually coming came up with with experts. um and despite this investment in reward engineering, we actually again, saw simpler was better. a single binary reward signal was what god us the most lift on this data, which led us to a blueprint uh that we've been developing for enterprise agts.

</details>

### 企业级智能体蓝图：迈向动态环境与开放评测生态

结合金融与保险场景的落地经验，企业构建生产级智能体必须围绕三维能力坐标系展开规划：
1. **环境复杂度（Environment Complexity）**：智能体所处的环境是静态文本还是动态演进的复杂系统？必须在包含脏数据、异构模式和状态突变的环境中打磨决策能力。
2. **自主时界（Autonomy Horizon: 智能体在无需人工介入下持续执行多步推理与操作的时间或步骤跨度）**：测试不应局限于单次问答，而要衡量智能体在超长链路中维持自我判断、纠错回溯与独立决策的耐受力。
3. **输出复杂度（Output Complexity）**：从单一的纯文本和数字，拓展至能够生成审计报表、操作日志乃至完整业务交付物的多维表达形态。

为推动行业生态走出仅靠文本困惑度或简单问答评测的局限，Snorkel AI 设立了 100 万美元的开放基准研究基金（Open Benchmark Grants），先后支持了 **Agent Last Exam** 与 **Judgment Bench** 等评测项目，并将本次研究的全部资产——包括 RLM 训练脚本、FinQA 数据集与模型权重——全量开源。

<details>
<summary>Original English Source</summary>

and generally, i'd say this study showed us that small models can successfuly be trained uh with oriil. um when you have quality data to represent the target um outcomes in tasks, and this can result in better deployment economics for specialized tasks and domains. and um we've seen this and repeated this result in other areas, including health care law ensurance, which i pointed to earlier. so check that out um and our point of view, as far as building acxities for evaluating agents is this is environment. complexity is um one of the most important accities. how complex, how realistic and dynamic other the environments um the agents operating in the next is is atommy horizon. um our agents being tested and evaluated at the links and the horizon lanks in the way people actually, when to use agents. um are they making saving good decisions by themselves? and can they actually improve their judgment as a copoot time in finally, output complexity, we want to capture the wide range of outputs in our data daywork. and i would say that this is currently under explored um new benchmarks are coming up in this direction. but um still i see a big um primary focus on um tex artifacts and creating more rigorous evaluations. and um these settings is uh a big opportunity in uh progresses being made here. so on that note, um when advertise are open benchmark strands, which funded this project, and this is a what time million dolar commitment to producing open mentworks like this. uh we've had a lot of success agent last exam um judgment bench um others are coming out. and this is um really accelerating our ability to measure the frontier and shape the frontier. so to apply. uh check out our website. um you'll go through a submission um selection, review process develop and then finally publication launch um and promotion and also wwant to call out that we're hiring in fessional research. um you name and engineers, and um yeah check that out. you can h check out our website. and finally, thank you so much for attending. um you can use this QR code to see the blog as well as pointers to all the artifacts that released get home hugging face. yeah, thank you all the.

</details>