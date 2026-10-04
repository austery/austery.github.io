---
author: AI Engineer
date: '2026-09-26'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=x4e5O9zN0TE
speaker: AI Engineer
tags:
  - multi-agent-system
  - long-horizon-agent
  - agent-evaluation
  - auto-research
title: 长周期多智能体系统的自动化研究：用闭环实验突破‘提示词微调’瓶颈
summary: 针对多智能体在长时间运行中出现的信源丢失、谣言硬化为事实等社会一致性退化问题，前微软与 Supercell 工程师提出结合 Auto-Research 的闭环实验架构。通过冻结测试框架、设计控制场景套件、引入多维平衡记分卡并约束微调策略面，实现智能体协议的自适应演进与长周期一致性。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Supercell
  - Microsoft
products_models: []
media_books: []
status: evergreen
---
### 状态架构：构建具备意图与记忆的游戏智能体

在游戏与虚拟世界中部署自主智能体时，核心技术挑战在于如何让智能体在长时间维度上持续保持状态与社会行为的一致性。前微软与 **Supercell** 工程师 Erina 在其 AI 创新实验室开发的 **Project Paradox** 探索了这一命题。该项目构建了一套模块化 AI 框架，使开发者能将具备自主性的智能体无缝接入游戏，让其与玩家或其他智能体展开互动、竞争与合作，成为动态共存的游戏伴侣。

为了使虚拟角色具备逼真的动态行为，智能体的行动必须基于明确的内部驱动力。智能体能够带着意图移动，其导航与决策受到自身记忆、情绪状态以及好奇心的共同引导。它们可以感知环境上下文，拾取或放置道具，并对周围发生的突发事件做出即时反应，事件的发生会动态修正其信念与情感。此外，智能体之间或智能体与玩家之间的对话互动会被持久化沉淀，成为后续决策的基础。

在底层架构设计上，系统采用了明确的**有状态架构**（Stateful Architecture: 持续保留历史上下文与内部状态的系统设计），其核心由四个关键支柱构成：
* **独立智能体记忆空间**（Per-Agent Memory: 基于独立的 **检索增强生成**（Retrieval-Augmented Generation: 结合检索与生成模型的上下文扩充技术）命名空间隔离各智能体记忆，防止上下文在智能体间发生数据穿透与污染）；
* **情绪向量追踪**（Emotion Tracking: 将情绪量化为低维向量，在交互后动态更新喜悦、悲伤、恐惧、愤怒、厌恶等情绪维度）；
* **信念与信任矩阵**（Belief & Trust Matrix: 维护智能体对其他角色与玩家的信任评分，每次交互后由大模型裁定信任分数的升降）；
* **记忆重要性评分**（Importance Scoring: 类比人类遗忘琐碎晚餐但会牢记重大谋杀案的机制，大模型会对事件进行重要性打分，跨越阈值的关键记忆会被写入独立的高速缓存以便后续高精度召回）。

在实际演示中，当玩家邀请角色 Blossom 一起野餐时，Blossom 会自主规划一系列动作序列——拿取糕点、前往野餐区域，并在后续对话中精准保持上下文一致性。

<details>
<summary>Original English Source</summary>

[Speaker 1]: hi, ron, i'm arena former engineer at microsoft and supercell. and today, i want to talk about autor research in a multi agent AI village. i ll use a video game like AI village as a running example here. but the broader question is one, i think many AI engineers are starting to run into. how do you evaluate an improve agents that carry state over long period of time?
[Speaker 0]: 嗯,
[Speaker 1]: before i get into the auter research layer, i want to talk a bit about project pardodox develop project paraddox at supercells ai innovation, love move. and my teammate natural money condedn, we built a modellar ai framework that allows any development to plug inteintelgent autonomous agents within a vdeo game that can intertract compete our corporate with other players, our agents as well and place them. and and them them dynnamic game companions. now to give examples of what these agents can do, the agents can move with intent. they can go to any location or person and theyguided by their own memories. emotion are curiosity. these agents can in tract with the world, they can pick up objects, drop them anywhere. and they're also aware about the context in their own environment, such as objects or other characters or agents as well. i would also like to note that game of a perst can also add new actions for these agents to accomplish within our framework as well. instead of just dropping ing or placing objects, agents can also extually react to what's happening around them. and these events that happen around them affect their own beliefs and emotions on the fly as well. and of course, it wouldn't be complete if agents start art conversation, right? agents can in this a scenario approach. other agents are even the player as well, and this makes the game feel more alive. and of course, these conversations are stored within their memory and is according to their own and affect their own emotions and believes our goals as well. and altogether, these agents make our multi agentic framework. um yeah, yeah. second. so the architecture was intentually statefall behind this. the first important part was per agent memory. each agent has its own memory name space ed by irag. so many we do not bleed between agents. second, we trapped emotion as a small vector. so after an event, our conversation the system could update values like joy, sadness, fear anger are discussed. third, agents had belief scores towards other agents and the player you can think of this as a trust matrix, basically like after the interaction happens, the elym basically decides whether the trust score should go up down or whether to and change at all. and fort, every memory receives an important score um to explain this very like, let's say, you had dinner few days ago, you probably wou't remember what you had for dindinner. but but if if one was was urdered a few days ago, you definitely remember that so the agent will evaluate or the lm will evalid uh an important score of an event. and if it crosses as thasuld, it will shore that specific memory uh in a separate cash, so that important context can be retrieved better later on. and here's an example of it just working. we 're going to ask one of the characters you're going to picnic with us here. um our character blossom um decides to pick up a pastry and go to the picnic yia because we asked her to do so. keep in mind during the conversation in the background, she plans all of these sequence of actions to accomplish. and when when we talk to her afterwards, she will also reply within context as well.

</details>

### 长周期衰减：社会一致性退化与信源断裂难题

然而，随着系统运行时间尺度的拉长，一个极具挑战性的工程难题浮出水面。尽管在短周期交互中，智能体能够顺畅地制定计划、移动、对话并精准响应即时上下文，但跨越**长周期交互范围**（Long Horizon: 跨越长时间线、多次迭代与复杂间隙的状态运行周期）时，系统的**社会一致性**（Social Consistency: 智能体群体在信息传递、信念维护与角色关系上的连贯与稳定程度）开始急剧退化。

以群体中传递信息的真实案例为例：某智能体针对“芒果打折”发起了一条传闻，并将该信息告知了第二位智能体；第二位智能体接收信息后，随后又转述给了第三位智能体。在经历了一系列无关事件后，当玩家直接向其中一位智能体询问芒果相关细节时，系统虽然仍能勉强记住“芒果”这个粗略主题，但却彻底丢失了关键的原始上下文。

这种退化具体表现为三种致命的系统性失效：
* **信源归属遗失**（Loss of Source Attribution: 智能体记住了信息内容，却丢失了信息由谁提供、从何而来的链路追踪）；
* **不确定性坍塌为确定事实**（Uncertainty Hardening: 原本属于“可能”、“推测”或“传闻”的模糊信息，在流转后被智能体当作无可置疑的客观事实进行转述与决策）；
* **知识与规划断层**（Knowledge-Planning Disconnect: 智能体内部虽然存储了某项事实，但在规划具体行动序列时未能有效激活与应用该记忆）。

面对这类长周期社会化行为的失效，传统依赖人工调试单一提示词或单次问答评估（Single-Turn Evaluation）的开发模式彻底失效，迫切需要一种能够在完整会话轮次与群体层面上持续评估与演进系统的全新工程范式。

<details>
<summary>Original English Source</summary>

[Speaker 0]: yeah,
[Speaker 1]: but this is where an interesting problem actually started. as you saw in the last example, like for shark term, again, play this, our architecture work pretty well like a character could make a plan move around talk and remember the recent intraction and respond to us or other characters as well. but over longer, horizons, this is very notice the social consistency start to get weaker. so in this example, we have one agent spreading a rumor about a faile on bengals to another regent, and that agent receives that information and goes and tells another agent about it later on. after a number of events of her occurred in between when the player asked one of the agents about the mangoes, it doesn't exactly store that context that we were expecting. i doesn't give us the context that we kind of wanted to. and this is where things are trying to get messy, naturally like the system may rememred the rough topic, but lose the source of the topic. a rumor may become certain. instead of just a rumor like the agent might stated as a fact or um an dient might know a fact, but failed to fail to remembered while creating a plan for its actions. so the question here became harvely imve a mulltiagentic system over long running social behavior and not just over one response.

</details>

### 自主研究外循环：从单次问答评估跃迁至运行轨迹优化

受 Andrej Karpathy 近期提出的 **Auto-Research**（自动化研究: 驱动智能体自主执行假设生成、实验验证与代码策略更新的闭环框架）概念启发，团队尝试将多智能体框架转化为一个可自动实验的运行环境。与其人工微调单一提示词或沉迷于精心挑选的演示 Demo，不如构建一个能够对自身展开闭环实验的外部元系统。

在这种分层视角下，**Project Paradox** 本身演化为实验运行的沙盒环境（Lab Environment），而 Auto-Research 则构成环绕在外部的闭环迭代循环。需要强调的是，这一机制的目标不仅限于优化 RAG 的召回精度，而是全局优化**智能体交互协议**（Agent Protocol: 涵盖记忆读写、不确定性表达、信任迭代、资源竞争与动态重规划的通信规范）。

在系统拓扑中，Auto-Research 绝不是村庄内部的另一个村民智能体，而是独立于村庄之上的**元系统**（Meta-System: 拥有全局观测权限、监督整个多智能体集群演化的宏观调度系统）。村庄内的各个智能体受限于物理与认知边界，仅拥有**局部视角**（Local Perspective: 仅掌握自身所见、所听、记忆及推断的片面信息），信息只能依靠智能体间的有效交流而扩散；而 Auto-Research 层则具备上帝视角的全局追踪能力，其工作闭环包含五个严格阶段：
1. **定义可控场景**：设定具备基准真值（Ground Truth）的特定测试用例；
2. **运行多智能体仿真**：让系统全量运转并沉淀完整的结构化轨迹；
3. **采集多维轨迹数据**：全面记录智能体的观察序列、对话日志、记忆检索行为、信念矩阵变动等；
4. **群体行为评分**：对比仿真事实与真值，检验信息传递是否符合预期、信源是否留存、不确定性是否保留；
5. **小步长策略更新与回滚验证**：提出受限的策略微调，重新运行场景。若群体行为评分提高且安全护栏未被破坏，则保留变更；反之立即回滚。

这一演进的核心转折，在于评估目标从“评估单次问答输出的质量”彻底跃迁至“评估长周期运行中整个虚拟社会的群体行为演化”。

<details>
<summary>Original English Source</summary>

[Speaker 1]: and this is where we wanted to bring an artter research. as you all know, uh, few months ago, karpari posted out utter research. and this this made us immediately racuous. um perhaps we can make the system run experiments on itself. and can we use this for our system as well. so what we understood it is instead of manually tuning a prompt or watching one nice demo, we could define a scenario suit, run the agents, collect traces, scored the behavior and chanined a small policy surface, and only keep the changes that actually improved the score. and this is where we're trying to bridge project paraddogs with auto research. so at this point, basically our multigentic fammer project paraddogs is more like a labinent and auterreseararbecomes the experimental loop around it. and importantly, this is not only about improving grag tritrival. the broorder framing is optimizing the agent protocol. like how do agents write memories, retrieve them, communicate uncertainty, a bit trust, active resources and repplant around new facts. basically, um yeah, in this context are yeah. 好, yeah. in this context, art research is a not another agent in the village. like i said, it's a meda system outside the village. the villagers have local perspectives. of course, they only know what they saw heard remembered are infered, because there isn't the common memory database in between them, information only travelles. once ce other agents communice than properly the art research layer has has different job b here. it reads the full traces of a run, compares what happens against the scenario ground trooth um scores the behavior and proposes a constrained tees to the agent protocol are coordintive policy, then agreed runs to scenario and ask society level behavior like, did society level behavior get better。 this is the key shift we are trying to look for. so we were no longer evaluating one answer. we were evaluating an entire run. and this is what one of the loops would look like. like first, we define a controlled scenario, which all elaborate a bit more about later. for example, one agent learns a public fact or one agent, hears a rumor um that could be a controlled scenario. then we run the simulation during the run. we collect structure, traces observations, conversations, memorites ts retrievbeliebelief objects, whatever is relevant to us. in that case, we collect, then we score this behavior did the information spread as we expected to did the source attribution survive, such as does the agent. remember who started the rumor? did uncertainly stay uncertain? did agents act on what they actually knew? and then the auteror sesearch yer here proposes a small policy change. and this is important, it should not rewrite the whole application. of course, it should only edit a controlled policy surface. and then rerun, if the score improves and the guardials hold, we keep the improvement. and if not, we simply just revert back and talking about controlled scenaris.

</details>

### 控制场景与平衡记分卡：防范度量作弊的系统工程

为了让实验框架具有可重复性与判定效力，必须消除自然漫游带来的评估模糊性。如果仅仅让智能体在虚拟环境中自由游荡，表面上或许能产生有趣的互动，但工程上根本无法断定系统是一致性增强还是发生了退化。因此，构建成套的**可控场景套件**（Controlled Scenario Suite: 具有明确输入、预期扩散路径与因果链条的测试用例集）是长周期评估的前提。

典型的控制场景包括：
* **公共事实扩散测试**：智能体 A 得知“面包店明日闭店”的事实，评估该事实是否准确传递给目标智能体、接收者能否准确复述信源，以及相关智能体是否据此调整自身次日行程规划；
* **谣言不确定性保留测试**：智能体得知“某智能体‘可能’要离开村庄”，检验该传闻在多跳传播过程中，“可能离开”是始终保持传闻定性，还是被错误硬化为“确定离开”的事实；
* **动态重规划测试**：团队原本制定了协同行动计划，当某智能体发现既定路线被阻断时，检验其能否将新事实同步至群体并触发重新规划，避免执行无效或失效动作。

与场景设计同等重要的是严谨的**平衡记分卡**（Balanced Scorecard: 兼顾多维约束以防止单一指标被过度优化的综合度量体系）。单一度量指标（如笼统的“智能体质量评分”）会掩盖所有致命的边缘失效。设计记分卡时必须形成多维约束对抗：
* **传播覆盖与信源溯源的对抗**：不仅测量信息覆盖度（Reach: 若干步长后知晓事实的智能体数量），更测量信源留存率（Provenance: 知晓者中能准确指认信息源头的比例），避免智能体通过无脑刷屏达成高覆盖；
* **传闻保真度与假性确定性的对抗**：同时测量不确定性保留率与错误确定性转化率（False Certainty Rate）；
* **规划一致性与响应时延的对抗**：量化行动一致性（Action Consistency）与触发重规划所需的时间窗口；
* **私密性围堵**：增加信息遏制率（Containment）以防止信息向未授权角色扩散。

这种平衡机制切断了智能体利用算法漏洞刷分的空间，防止优化扩散导致“过度倾销隐私”，或优化召回导致“记忆垃圾过载”。

<details>
<summary>Original English Source</summary>

[Speaker 1]: the reason why uh scenario design matchers is that social behavior is otherwise a bit fuzzy y in general. in the sense, if you just let the agents in our environment wonder around, it might look cool and you might get nice interactions, but it's actually very hearkey valid on whether the system actually improved. so this is why we believe you need controlled scenaris. for example, one scenario could test a public fact division, let's say, agent a learns. um the bakery will close tomorrow, do the right agents learn it. do they remember who said, what do they do? they change their plans based on this fact. another scenocould test rumor uncertainy agent, let's say agent here that agency might leave the village. when this rumors threads does might leave suddenly become is leaving? or does it stay as might leave like does it become a fact? or does it still say, as AA rumor, another scenario could test replanning, the group has a plan, but one agent learns, let's say the roroup they wanted to take is blocked. do edents update this and communicate this with each other to avoid um improper plan or steal actions. the point is not that these exact scenaris are universal here. the point we are trying to make is that long horizon agent behavior need scenario suits and talking about our mango example, again, after running one of our archy research loops this time after uh, a long period of time when the player finds. he asked one of the agents about the salilon mangoes. we did find that the agent was able to respond within context this time like compared to last time, yeah. and for this talk, the the exact formula, we believe is less important than the shape of the score card. uh you do not want a single vae e tritric like asent quality. this will hide all the interesting failures. instead, you want a balanced score card for difusion. you might measure reach like how many agents know the fact after end steps for a provenenence, you measure source attention among agents who know it, how many remember it where it came from exeta for rumors, you can measure uncertainy preservation and false certainy rate for planning. you can measure action consistency and time to replan and for privacy. you can measure containment this matters because optimizing only one metric can create bad behavior, because let's say, if you only optimize for a diffusion, the agents may learn to overshare everything. and let's say, if you only optimize for memory ealds, you might create noise, you are still like memories. so this score card is what keeps the system honest and prevents the auto research agent from gamifying the system to just increase one specific score.

</details>

### 受限策略面与通用范式：超越游戏的长周期智能体工程

在具体工程落地中，另一个关键经验是**严格限制可编辑策略面**（Constrained Policy Surface: 仅向自动搜索算法暴露的受限参数与逻辑切面）。严禁赋予 Auto-Research 随意修改系统全量代码的权力。工程上必须彻底冻结基准测试框架、控制场景以及评估指标体系，仅暴露特定的策略接口供优化器进行小步长搜索：
* **记忆写入与检索策略**（如在记忆写入和摘要提炼时强制追加信源元数据）；
* **不确定性表达规范**（如要求区分直接见闻与第二手传闻，并在转述未证实主张时强制使用限定词语）；
* **事实传播触发器**（如将关键公共事实分类标记，主动驱动智能体共享关键证据）；
* **信任更新法则与重规划触发阈值**。

这种收敛设计构成了“大语言模型随意打补丁”与“大语言模型在受限策略空间内严密搜索”的本质分水岭。

从这项实践中提炼出的核心启示在于：**仅为智能体赋予存储空间是远远不够的**。向智能体盲目堆砌 RAG 或向量数据库，无法直接换来可靠的长周期行为；系统必须显式维护信源出处、保留证据层级（一手记录与二手转述）、隔离原生情境记忆与当前信念状态，并通过严格的控制场景进行压力测试。此外，**自动回滚机制是绝对刚需**，因为优化社会化行为天然具备负外部性——提升公共信息扩散速度的策略，极有可能同时导致私人信息泄漏；提高记忆召回率的策略，可能引发陈旧记忆冗余。

这一套工程范式绝非仅适用于虚拟游戏，所有需要维护跨时间状态并根据状态指导行动的长周期智能体系统，都面临完全一致的底层困境：
* **客户支持智能体**（Customer Support Agents: 必须明确政策更新的具体出处，知晓新规定何时取代旧口径）；
* **个人助理智能体**（Personal Assistants: 必须长久记住历史承诺并在用户偏好改变时精准修正）；
* **深度研究智能体**（Research Agents: 必须严密保持引用溯源、妥善处理事实冲突与假设迭代）；
* **代码辅助智能体**（Coding Agents: 必须在长期跨 Issue 协作、人员轮换与需求漂移中维系完整上下文）；
* **企业工作流智能体**（Workflow Agents: 必须在环境变化时执行精准的访问控制、任务交接与自适应重规划）。

总结而言，构建长周期智能体的核心工程法则可概括为：**冻结测试基准框架，定义控制场景套件，沉淀结构化运行轨迹，使用平衡记分卡打分，仅暴露受限策略面供搜索，并仅保留能够通过度量检验的有效变更**。长周期自主智能体的发展已跨越单纯依赖提示词工程的初级阶段，全面迈入依赖系统化闭环实验的全新工程纪元。

<details>
<summary>Original English Source</summary>

[Speaker 1]: the other import enering lesson that we learned over this project is that um it's imppart to keep the editable surface really small. the arto sesearch's alyer should not have permission to romly rewrite the whole code base. instead, it's really imppoint to freeze the harness, the scenos and metrrix. so we're only exposing the part of the system that we actually want to optimize here in project products for us. that meant tings like memory, writing policy, retrieval policy communication prompt, believe trust rules, source attribution, replanning, triggers eetra. this gives the search proprocess room to improve behavior, but it also prevents it from gaming the evaluation directly as we mentioned before. and this is the difference between the elam writing lurandum patches versus the MM actually searching within a controlled policy space. and here here, examples of the kind of changes, i want this kind of loop to search over, if if source attribution disappears, the policy change might be preserve source in memory and uright memory rights and summaries. if rumors harder into facts, the policy change might be stored confidence. mark first hand versus second hand and require heading when retailing uncertain claims. if if facts, if public facts stay local, the policy change might be classify useful, public facts differently and make edens practively share important source evidence. the key is that these are small changes to the agent protocol, but they can have larger effects on a society level behavior from monthly agentic systems. this is also where i kind of want to be careful about our claims here because we believe, without repeated to current loop results, like i won't say the system this generally improved. we're trying to say this is the right kind of surface to expose to an autorresearch layer. uh p. because it is small enough contcontrol, but still written enough to change the social behavior, to some extent, at least. and the biggest lesson for me, perhaps, was that memory is not enough here. you can add a add memory to an agent and still not get the current long term, her horizon behavior that you are looking for um because agents need to sometimes know where that information came for came from. you need to preserve whether it was first time, second hand, raified or uncern. sometimes you need to separate draw pacodic memories from what the agent and currently believes to, and you need to test behavior through scenario, not not through vives. so the other lesson is that um rollback also is not optional when you opto my social behavior, a change can improve one thing and damage another. so policy that spreads public facts um faster might also leak private information, a policy that increases recall might increase scale memory usage. so the loop should basically be like a ratred try a team score. it keep it only if the score card improves and gardielseful. and we we definitely believe this is not only relevant ant a game agents. because, although i gave an example of using a game village, we believe, like, let's say, for example, support agents support agenciy to know which policy of date comes from wewereed. and whether it's supreceds and older answer personlistence, for example, need to remember commitments that the prevacy made and make corrections, if if the user wants to change those personal commitments, research agents, proprevenence cctations, contraction handling and hypertests updates coding agents need long running context across issues, fres teammates and changing requirements. birfflu eens need access controls, handdofs and replanning. when the world changes, all of these systems have the same underlying problem, they maintain state over time, and that state affects affeacaction. so they control sceniors and behavioror score cards is what we are proposing. so again, in brief a recipe for long horizon agents. if there is one practical recipe, i want you to take away freeze. the harness defines senials log traces a score behavior and expose only a small policy surface search over these changes. keep only changes that survive your measurement, and this is an engineing pattern that we believe would make sense for long running agents. the real question we believe, is across control runs. does the system behave better to close project padct start as an attempt to make game, even n't feel alive in a trady world, but the deeper engining problem was not animation or dialogue for us. it was the state, such as which agent knows what which agent told whom what is true, uncertain are outdated and do agents act on what they remember. alter research, alter research gave us a way to approach this a bit more systematically, not by trusting one demo or not by endlessly handtuning proms, but by running control experiments and keeping only the changes that survived our measurement, long horizon, agencts need experiments and not just prompt. and i hope that's to take away that you get from this talk. and yes, please do connect with us. we'd love to talk if you have any questions. thank you so much for listening. yes.

</details>