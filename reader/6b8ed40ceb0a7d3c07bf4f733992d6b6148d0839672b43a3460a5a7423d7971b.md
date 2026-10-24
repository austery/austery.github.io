---
layout: post.njk
source: https://yage.ai/share/harness-demand-side-analysis-20260420.html
speaker: yage.ai
title: |-
  Everybody Talks About It, Nobody Knows What It Is —
  Harness Engineering 到底是什么
date: '2026-04-20'
summary: 文章探讨了近期流行的“Harness Engineering”概念，指出其核心是将管理学中处理自主智能体（如AI Agent）的原则，重新应用于新的技术环境中。它解释了Harness Engineering为何能解决AI Agent在生产部署中遇到的如组合错误、输出不可度量、Context Anxiety、测试失效及治理困难等“五面墙”问题。该概念通过精确的“马具”隐喻和“工程学”的定位，成功打包并传播了应对AI Agent可靠性挑战的实践方法，使其成为一个热门但定义不一的技术领域。
area: tech-engineering
category: tech-trends
tags:
  - harness-engineering
  - ai-agents
  - reliability
  - management-science
  - engineering-practices
people:
  - Mitchell Hashimoto
  - Garry Tan
  - Karpathy
  - Ethan Mollick
  - Simon Willison
companies_orgs:
  - OpenAI
  - Cursor
  - Anthropic
  - McKinsey
  - IDC
products_models:
  - GPT-5.4
  - Claude Opus 4.6
  - Gemini 3 Pro
media_books: []
draft: true
status: evergreen
---

> 日期：2026-04-20

## 一个没人定义得了的词，凭什么火三个月

Dan Ariely 说大数据像 teenage sex：everybody talks about it, nobody
really knows how to do it, everyone thinks everyone else is doing it, so
everyone claims they’re doing it. Harness engineering
现在就是这个状态。

AI
领域每隔几周就有一个新概念被推上风口，热闹一阵，然后被下一个概念取代。RAG
是这样，LangChain 是这样，Context Engineering 也是这样。

Harness Engineering 不太一样。从 2026 年 2 月 Mitchell
Hashimoto 首次提出，到 OpenAI
正式采用，到 Garry Tan 的 Thin Harness
Fat Skills 拿下 140
万阅读，这个概念已经持续了近三个月，热度没有明显衰减。而这三个月里，几乎没有人能给出一个让大家都满意的定义。

OpenAI 写了一篇好文章，Garry Tan
有影响力，三大公司同时发文形成共振。这些可以解释第一周的热度，但解释不了第三个月的热度。三个月的持续需要需求侧的真实共鸣：一群人在自己的实践中撞上了同一组问题，然后发现
harness 这个词恰好描述了它。

这组问题是什么？2025 年底到 2026 年初，GPT-5.4、Claude Opus
4.6、Gemini 3 Pro 先后发布，agent
从概念验证进入了生产部署。大量团队在这个过程中同时撞上了五面墙。

## Agent 撞了哪些墙

第一面墙：错误的组合爆炸。 单个 agent
的错误模式是可管理的，你可以给它加 guard。但两个 agent
串联起来，失败模式不是两个的叠加，而是两个的组合。一个医疗场景的案例能说明这种组合爆炸：三个
agent 各自准确率 95%，Agent A 生成了一个不存在的药物名称，Agent B
基于它检测出虚构的药物相互作用，Agent C 据此向医生发出了紧急警报。每个
agent 的 guard
都通过了（各自的输出格式正确、逻辑自洽），但组合在一起产出了一份完全虚构的高置信度医疗告警。根源在于：传统的逐组件防错机制建立在错误模式可穷举的假设上，agent
的概率性输出让这个假设不再成立。

第二面墙：自然语言产出无法度量。 传统的
observability 度量的是结构化数据：HTTP status code、latency、error
rate。你可以对数值设阈值、配告警。但 agent
的核心产出是自然语言。一封催款邮件写得是否精准、细节是否充分、语气是否得当，没有现成的度量手段。一个金融领域的案例：agent
初期生成的催款邮件非常精准，随着处理的边界情况增多，输出逐渐退化为泛泛的模板。模型对
prompt 的理解发生了漂移，而团队完全没有手段在漂移发生时捕捉到它。Mezmo
的 AURA 项目负责人一句话说到了点上：“agents fail silently. They
hallucinate, loop, and make confident but incorrect decisions based on
incomplete context. Traditional observability stacks offer no visibility
into these failures.”
根源在于：传统的观测体系建立在被观测对象是结构化数据的假设上，agent
的自然语言产出让这个假设不再成立。

第三面墙：被管理的对象会感知环境并改变行为。
传统软件的状态由程序员定义，边界清晰。Agent 的 context
完全不同：动态、非结构化、有容量限制，而且 agent
对这个限制有感知，并会据此改变行为。Cognition（Devin 团队）在重建产品时发现了
context anxiety：agent 提前感知到 context window
的限制，开始走捷径、提前收尾任务。他们的解决方案完全是环境层面的：开启
1M token context，实际限制使用量在
200K，让模型认为自己还有大量余量。模型没变，环境变了，问题消失了。根源在于：传统的状态管理建立在被管理的对象不会感知资源约束的假设上，agent
对 context 的主动感知让这个假设不再成立。

第四面墙：输出不可复现，传统测试失效。
传统的测试手段（单元测试、集成测试、回归测试）建立在一个前提上：同样的输入产生同样的输出。跑一次
pass 了，就代表以后也会 pass。Agent 的输出每次都不一样，今天 pass 的
case 明天可能 fail。传统的 pass/fail
判定方式不够用，需要的是基于评判标准的持续评估：定义什么样的输出算合格，然后用统计方法判断整体质量是否在可接受范围内。根源在于：传统的验证体系建立在行为可复现的假设上，agent
的概率性输出让这个假设不再成立。

第五面墙：治理框架管不住概率性行为。 McKinsey
的数据显示超过 70% 的企业在试点 AI，但只有不到 20% 成功规模化。IDC
的调研更尖锐：只有 2.9% 的组织在跨部门规模化 agent
应用。具体症状包括 agent 跨系统重复处理数据、API 变更导致 agent
静默失败、管理不善的 agent 产生的 support ticket
比带来的生产力提升更多。企业原有的 IT governance
体系（权限管理、变更控制、审计追踪）假设一个系统被授权做某件事，它就只做那件事，每次都以同样的方式做。Agent
的概率性行为让这个假设不再成立：同样的权限、同样的输入，agent
可能做出授权范围之外的操作。根源在于：传统的治理框架建立在系统行为确定的假设上。

回过头来看这五面墙，它们有一个统一的模式。每一面墙对应的都是传统软件可靠性保障链条上的一个环节：防错、观测、状态管理、验证、治理。这五个环节合在一起，覆盖了一个软件从运行到交付的完整生命周期。而每个环节失效的原因也是同一个：它的底层假设建立在确定性系统上，agent
的概率性行为打破了这个假设。

换句话说，agent
不是在某一个点上出了问题，而是让整条可靠性保障链条同时失效了。这些问题不属于模型能力的范畴（你不能等下一代模型来修复它们），也不属于
prompt 或 context engineering
的范畴（后两者关注的是模型的输入质量）。它们是 infrastructure
的问题：agent 的能力跑在了 infrastructure 前面。

但这些 infrastructure 缺口真的是全新的吗？

## 太阳下面没有新鲜事

把上面五面墙放到管理学的语境下看，每一面都有现成的对应物。我们在《管理
AI》系列中用大量案例论证过这一点：AI
落地中遇到的大多数障碍，在管理人类团队时早就出现过，也早就有成熟的解法。

错误的组合爆炸，对应的是跨部门协作中的组合性风险。每个部门自己的质量管理可能都过关了，但部门之间的交接点会产生谁都没预见到的新问题。组织管理中的应对是端到端的流程审计、跨部门的
independent review、在关键交接点设置
checkpoint。单独检查每个部门永远不够，你必须检查它们组合在一起的效果。

自然语言产出无法度量，对应的是考核指标失效。当团队的产出从可量化的（代码行数、工单数、达标率）变成难以量化的（方案质量、沟通效果、判断力），原来的
KPI
体系就不够用了。管理学中的应对是引入定性评估：同行评审、案例复盘、基于
rubric
的多维评分。核心挑战是同一个：你需要为非结构化的产出建立新的度量体系。

Context
anxiety，对应的是员工感知到资源压力后降低标准。人类员工在觉得时间不够或者任务超出能力边界的时候，也会提前收尾、走捷径。管理者的应对方式是合理分配工作量、明确优先级、让员工对资源约束有正确的预期，而不是等到产出质量下降了才去追究。

测试失效，对应的是产出波动大的团队成员。有些下属的表现时好时差，你不能只看一次交付就下结论，需要持续跟踪多次产出来判断整体水准。管理学中的做法是建立持续的绩效追踪机制，用多次采样来替代单次考核。

治理框架失效，对应的是组织扩张中的管控失灵。当组织从一个团队扩展到十个团队，原来有效的管理方式开始失效，需要引入层级结构、标准化流程、跨团队协调机制。而且当团队成员的行为不完全可预测时（比如新人、外包团队），你需要更强的审计和权限管理。

每一面墙在管理学中都有对应的问题和成熟的解法。

## 既然是管理学，为什么之前没火

用 AI 就是在做管理，这个观察并不新鲜。

2023 年，Karpathy 提出
Software 3.0，说开发者的角色从写代码变成了用自然语言指挥和验证 AI
的产出。2024 年，Ethan
Mollick 在 Co-Intelligence 中明确写道 “great AI management,
not great models, creates competitive
advantage”，并给出了完整的委派-监督-评估框架。同年 Simon
Willison 把 agent 定义为 “an LLM that runs tools in a
loop”，开发者的角色是提供约束和验证。2025 年 Karpathy 的 vibe coding
走红之后，他自己也承认实际工作需要 “more oversight and
scrutiny”。我们自己从 2025 年初开始写《管理
AI》系列，核心论点也是同一个：AI
落地中遇到的障碍，在管理人类团队时早就出现过。

这些观点都对，传播也不差，但没有一个形成持续的热度。为什么？

因为「管理 AI」这个说法有两个问题。

第一，它唤起的联想是错的。一说管理学，技术社区的第一反应是：供应链管理、财务管理、人力资源管理，跟我写代码有什么关系？更具体地说，人类管理学里大量精力花在了解你的下属、知道怎么
motivate 他、处理人际关系和政治上。这些对 AI 完全不适用，AI
天生就是被训练成 helpful assistant
的，你不需要花精力去激励它或者处理它的情绪。所以 AI
的管理和人类的管理虽然原则相通，但侧重点完全不同：人类管理的难点在意愿（willingness），AI
管理的难点在可靠性（reliability）。叫管理学，大家想到的是意愿那一半，而
agent 真正需要解决的是可靠性那一半。

第二，它听起来是软技能。Yuzheng 在「名词
vs
动词」里点明了这个问题的根源：市场只给名词定价，不给动词定价。Debug
一个 multi-agent 系统的级联错误是动词，设计验证循环是动词，管理 agent 的
context 生命周期是动词。这些动词没有 GitHub 仓库，不能 pip
install，不能写进简历的技能栏。叫管理学，它就留在软性认知的货架上。

Harness engineering 解决了这两个问题。

## 一个起得好的名字

Harness
的原始含义是马具。马是有自主能动性的生物，它能自己判断路况、绕开障碍、在骑手醉酒的时候不撞墙。但骑手需要控制方向，需要用
5% 的力气决定 95% 的行进路线。这个隐喻精确地映射了 agent
的特性：有能动性、有判断力，但需要 high-leverage 的引导。

这和汽车的隐喻完全不同。汽车没有能动性，方向盘往左它就往左，踩刹车它就停。驾驶汽车的心理模型是过程确定性：你控制每一步操作。骑马的心理模型是结果确定性：你给出方向和意图，马自己决定具体怎么走。我们在《从过程确定性到结果确定性》和《管理
AI：你职业生涯中最重要的一次晋升》中都用过类似的类比：过去用 API
调用 AI 就像开汽车，你控制每一步操作；现在用 agent
就像骑马，你管方向，它管执行。从 micromanage 到 management
的转变，从过程确定性到结果确定性的转变，说的是同一件事。

Harness
这个词天然锁定在「引导有自主能力的智能体」这个特定场景上，比管理学的范围窄得多，心理锚点也准确得多。当然，这里面也有
hype 的成分。Harness engineering 听起来比 AI 管理学新、比 AI
管理学酷，这种新鲜感本身就是传播力的一部分。AI
管理学一听就是几十年的老东西，即使内容完全一样，也很难让技术社区兴奋起来。但
hype
只能解释短期传播，三个月的持续热度说明名字之下确实有实质。而这个实质就是：harness
engineering 比 agent management
多了一个关键信号：engineering。它宣称这是一个工程学科，有可编码、可传授、可度量的工程实践。当你把一组动词打包成
harness engineering
这个名词，它就从软性认知的货架搬到了硬核技术的货架上，可以被讨论、被学习、被定价了。

但好名字只解决了认知分类的问题，没有解决内容的问题。名字之下，harness
engineering 到底在做什么？

它在做的事情是：把管理学的旧原则在 agent runtime
这个新环境中重新实现。原则是同一套，工程实践是两套。

一个更精确的类比是
DevOps。运维的原则几十年没变：监控、告警、容量规划、故障恢复。传统数据中心时代，这些原则的实现工具是
Nagios 做监控、手动 SSH 上服务器查日志、运维团队 oncall
轮值处理故障。Cloud-native
时代，同样的原则有了完全不同的实现：Prometheus + Grafana
做监控、Kubernetes 自动编排容器、Terraform 把基础设施写成代码、GitHub
Actions 做 CI/CD 自动化部署。原则没变，但 cloud-native
环境（实例随时创建销毁、状态分布在多个节点、基础设施本身需要版本管理）要求一套全新的工具和实践。DevOps
不是发明了新的运维原则，而是在新的执行环境中重新实现了旧原则。

Harness engineering 和管理学的关系也是如此。管理人你用
1-on-1、绩效考核、文化建设。管理 agent 你用 checkpoint
设计、验证循环、context 生命周期策略、可观测性 stack。Agent runtime
有自己特有的约束（概率性输出、context window
限制、工具调用的不确定性、多 agent
状态同步），这些约束要求一套新的工程实践来实现管理学中那些老原则。

2026 年 Q1
的三篇奠基文章，从这个角度看就清晰了。它们各自解决的是管理学原则在 agent
runtime 不同维度上的工程实现。OpenAI 的 harness
engineering 解决的是交互维度：人如何用最少的介入来 steer 大量 agent
工作，对应管理学中的 span of control 和 delegation。Cursor 的 self-driving
codebases 解决的是空间维度：几百个 agent
并行如何不踩脚，对应跨团队协调。Anthropic 的 harness
design for long-running apps 解决的是时间维度：一个 agent
连续跑几小时如何不走偏，对应长周期项目的 milestone management。

三篇文章的读者群高度重叠，用的术语高度一致，但各自回答的工程问题截然不同。这也是为什么大家对
harness
的定义始终无法收敛：每个人都在往这个词里装自己正在解决的那个特定维度的管理问题。

## Harness engineering 为什么火

回到一开始的问题。三大公司同时发文形成共振，这解释了第一周的热度。但三个月的持续需要需求侧的支撑。

需求侧发生了什么：agent
进入生产环境之后，整条软件可靠性保障链条同时失效了。防错、观测、状态管理、验证、治理，五个环节的底层假设全部建立在确定性系统上，agent
的概率性行为把这些假设逐一打破。实践者在日常工作中撞上了这些问题，然后发现解法并不陌生：管理学里早就有对应的原则和工具。

原则是旧的，但之前的几次命名尝试都没能让它流行起来。管理 AI
这个说法让人想到意愿和政治，而 agent 的核心挑战在可靠性。Harness
engineering 解决了这个命名问题：harness
锁定了「引导有自主能力的智能体」这个特定场景，engineering
声明了这是可编码、可传授的工程学科，两个词合在一起把一组散落的动词打包成了一个可以被讨论和定价的名词。

所以 harness engineering 的持续热度来自两件事的叠加：一个真实存在的
infrastructure 缺口，和一个终于对上了这个缺口的名字。

对于实践者来说，这意味着一个好消息和一个坏消息。

好消息是你不需要从零学一门全新的学科。管过人、管过项目、管过团队，你已经具备了
harness engineering 的原则基础。

坏消息是原则相通不等于可以直接搬。Agent runtime
有自己特有的约束和机会，需要专门学习的新实践。举几个例子。管理人的时候，团队有
tribal knowledge，很多事情不用写下来大家也知道。Agent 没有 tribal
knowledge，所有上下文必须显式写成文档，document first
不是锦上添花而是基本前提。管理人的时候，你不需要担心下属在任务进行到 80%
的时候突然开始偷工减料。Agent 会：当 context window
接近容量上限时，它会感知到压力并开始走捷径（前面讲的 context
anxiety）。你需要主动管理 context 的生命周期，在它接近阈值之前做 divide
and
conquer。管理人的时候，让十个人同时做同一件事然后赛马，成本高、伦理上也说不通。管理
agent 的时候，你可以让十个 agent
并行跑同一个任务，取最优结果，这在统计学里叫
bootstrapping，成本几乎为零，效果显著。

这些实践在管理人的语境下要么不可能，要么不经济，但在 agent runtime
中是基本操作。Harness engineering
的原则来自管理学，但它的工程实践必须针对 agent
的特性重新设计。这也是为什么它值得有自己的名字。