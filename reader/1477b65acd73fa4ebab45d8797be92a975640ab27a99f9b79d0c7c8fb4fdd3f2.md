---
layout: post.njk
source: https://yage.ai/share/ai-scaffolding-commodity-runtime-20260505.html
speaker: yage.ai
title: AI 脚手架正在商品化，人的工作变成判断边界
date: '2026-05-05'
summary: 文章指出，随着AI模型和代理运行时发展，软件工程重心从提示词工程和定制化代理循环转向更高层次的判断和边界定义。任务正被商品化，工程师角色转向决策和标准设定。
area: tech-engineering
category: ai-application
tags:
  - agentic-runtime
  - prompt-engineering
  - harness-engineering
  - ai-in-software-development
people:
  - Garry Tan
companies_orgs:
  - OpenAI
  - Anthropic
products_models:
  - ChatGPT
  - GPT-4
  - GPT-5
  - GPT-5.5
  - Claude Code
  - Codex
  - Cursor
  - OpenCode
  - SWE-bench
  - SWE-Agent
media_books: []
draft: true
status: evergreen
---

过去几年，用 AI 的门槛一直在下降。早期 ChatGPT
用户会认真研究提示词句式，试
take a deep breath，试角色扮演，试 few-shot 模板。到了
GPT-4 以后，只要把意思说清楚，模型通常就能理解。再往后，Claude
Code、Codex、Cursor、OpenCode
把读文件、写文件、跑命令、看报错、循环修改这些动作接进一个现成的 agentic
runtime 里，用户不再需要自己写一套 agent loop，才能让模型持续做事。

这件事容易概括成一句话：AI 越强，越不需要
hand-holding。这个判断方向对，但说得太粗。更准确的说法是：一部分脚手架被模型能力吸收，一部分脚手架被产品
runtime 商品化，剩下的脚手架变得更像团队自己的判断资产。

所以真正的问题已经变成：哪些脚手架已经可以交给商品化
runtime，哪些仍然必须自己设计。这才是技术人接下来要面对的边界判断。

## 退潮的是补模型短板的脚手架

最先退潮的是提示词技巧。GPT-3.5 时代，很多 prompt engineering
确实像民间偏方：写特定句式，给角色设定，要求一步一步想，用示例逼出格式。这些技巧在当时有用，因为模型的指令遵循、格式控制和长上下文稳定性都弱。

OpenAI 自己的文档演化很能说明这件事。GPT-4.1 的 prompting
guide 还在强调 agent prompt 里要写
persistence、tool-calling、planning 三类 reminder，并说这三条让内部
SWE-bench Verified 分数提升接近 20%。到了 o-series 的 reasoning
best practices，官方反过来提醒用户不要再对 reasoning model 写
think step by step，因为这类模型已经内置推理过程，旧技巧可能没有帮助，甚至会妨碍表现。

GPT-5 和 GPT-5.5 的 guidance 更进一步。GPT-5 guide 里记录了 Cursor
的一个案例：旧模型需要 prompt 鼓励它充分分析上下文，但同样的 prompt 放到
GPT-5 上会导致过度搜索，因为 GPT-5 已经更主动地收集上下文。OpenAI 的 GPT-5.5
prompt guidance 直接建议用户写更短、更结果导向的
prompt，定义目标、约束、证据和最终产物，把实现路径留给模型自己选择。

Anthropic 的路径也类似。早期 Claude guidance 重点放在 XML
tags、few-shot examples 和 role prompting。到 Claude Opus 4.7 的 prompting
best practices，官方已经开始提醒用户移除
over-prompting。以前为了让工具触发而写的绝对指令，在新模型上会造成过度触发。Anthropic
还在 Effective
context engineering for AI agents
里概括了这层变化：构建语言模型应用，重点正在从寻找正确措辞，转向回答“什么样的上下文配置最可能让模型产生期望行为”。

Prompt
仍然重要，只是从话术变成了工作契约：目标是什么，约束是什么，什么证据可用，什么时候应该停止。退潮的是补模型短板的低层技巧，表达意图这件事本身仍在。

## 中间层正在变成商品化 runtime

第二层变化更重要：过去要自己写的 agent
harness，正在变成标准运行时。

如果直接调
API，很多脏活都要自己处理：状态怎么保存，长文本怎么压缩，工具调用失败怎么恢复，输出格式错了怎么重试，命令执行在哪里跑，权限怎么限制，测试失败后怎么把报错送回模型。很多团队以为自己在做
AI 产品，实际大量时间花在给模型收拾长尾错误。

Claude Code、Codex、Cursor、OpenCode
这类工具把这些通用能力封装了起来。它们的产品差异当然存在，但从用户的工作边界看，核心能力正在收敛：文件系统访问、shell
执行、工具调用、上下文压缩、diff、lint、test
feedback、重试循环、权限确认、会话状态。它们越来越像一类标准 agentic
runtime。

这层东西可以叫 commodity runtime。这里的 commodity
指的是足够通用、足够便宜、足够可替代，以至于大多数团队没有必要自己实现。如果你自建
harness
的结果只是模型能读文件、改文件、跑测试、看报错、继续修，那这部分已经不值得自建。

OpenAI 的 Harness
engineering 文章把这个趋势讲得很直接。Codex
看不到的东西等于不存在，所以文档、架构约束、lint、eval harness、review
loop 都要放进 agent 可访问的环境里。随后 OpenAI 又把 skills、hosted
shell、server-side compaction 做成 agentic
primitives。换句话说，一部分原来属于团队自建 harness
的能力，正在被模型提供商做成平台能力。

Anthropic 的 harness 文章也显示出同样方向。Harness
design for long-running application development
记录了一个重要案例：早期长程应用开发需要 sprint construct 和 context
reset，到了 Opus 4.6，作者发现模型已经能连续工作更长时间，于是移除了
sprint construct。Anthropic 的原话是：每个 harness
组件都编码了一个“模型自己做不到什么”的假设，而这些假设需要被压力测试，因为模型进步后它们会过期。

这里的结论是通用 harness 的中间层正在空心化。轻量自研 while
loop、手写 tool parser、格式重试、简单上下文压缩，这些东西会被标准
runtime 持续吞掉。自建的门槛反而提高了：你要么直接使用商品化
runtime，要么为少数非标准任务写更重、更领域化的脚手架。

## 交给 runtime，还是自己搭

什么时候 delegate 给商品化
runtime，什么时候必须自己搭脚手架，可以先用一个粗规则：通用执行交给
runtime，专属判断写成 scaffolding。

如果任务反馈清晰，比如 test、lint、build、preview、diff
能直接判断结果，那就优先交给 commodity runtime。修一个
bug、重构一个局部模块、补测试、改文档、整理一个 repo
里的重复模式，这些任务的执行层已经没有必要自己造轮子。让 Claude
Code、Codex、Cursor 或 OpenCode
去读文件、跑命令、看报错，比你写一套自己的 agent loop 更划算。

如果任务依赖领域判断，情况就变了。什么算好设计，什么风险可以接受，哪个指标比另一个指标重要，哪些内部
API 不能碰，哪些历史决策不能推翻，哪些用户场景优先级最高，这些不是
runtime
知道的东西。它们必须进入项目文档、skills、AGENTS.md、eval、review
rubric、domain context，甚至进入团队长期沉淀的判断原则。

再具体一点，适合 delegate
的是文件读写、命令执行、常规工具编排、基础错误恢复、常见代码修改、已有测试覆盖下的迭代。适合自建
scaffolding 的是 domain-specific
eval、内部系统集成、合规和权限边界、多步骤任务的状态机、高风险外部动作、长程异步协作、团队特有的质量标准。

外部 benchmark 也在支持这个边界。SWE-bench 说明真实 repo
issue 往往需要跨函数、跨类、跨文件协调修改；SWE-bench Pro
直接用 SWE-Agent scaffold 复现实验结果；Terminal-Bench
把任务放进真实命令行环境，并配套 execution harness 和测试。SWE-agent 的
Agent
Computer Interface 文档也明确说，好的 ACI 设计会显著改善 agent
表现。

这些证据指向同一个事实：当任务变成长链路执行时，可靠性不来自“模型单次回答更聪明”，而来自
runtime、工具接口、测试、eval、checkpoint、guardrail
和观测机制。差别在于，通用部分可以购买，领域部分仍要自己设计。

## 商品化 runtime 的隐性成本

把执行交给 commodity runtime
仍然有成本。控制权被换走了才是真正的代价。

第一，你接受了 runtime
的上下文管理策略。它如何压缩历史，如何判断哪个文件重要，如何决定什么时候搜索，如何处理长会话中的旧信息，这些通常不透明。标准软件工程任务里，这些默认策略是效率；非标准任务里，它们可能把关键上下文压掉，让你很难判断失败来自模型本身、prompt、工具，还是
runtime 的上下文选择。

第二，你接受了 runtime 的默认行动方式。Claude
Code、Codex、Cursor、OpenCode 都在塑造一种默认
agency：什么时候问用户，什么时候继续试，什么时候运行测试，什么时候认为任务完成。默认行动力很有价值，因为它让大多数普通任务不需要人工编排。但只要你的任务有特殊停机条件、特殊风险边界、特殊验收标准，默认
agency 就可能不够。

第三，自建脚手架有逆水行舟成本。模型和工具提供商会持续优化主流
runtime 的使用分布。模型越来越适应标准 tool schema、标准 shell
环境、标准 code edit
workflow。如果你自建一套非主流接口，就不只是在维护代码，也是在对抗模型默认训练分布。除非你的自建脚手架能带来明显收益，否则它会被下一轮模型和
runtime 升级抹平。

所以更实用的策略是把控制权放在最值得放的位置。文件系统、shell、上下文压缩、基础重试交给
runtime；成功标准、领域知识、权限边界、评估方法、长期记忆留在自己手里。

## Harness Engineering
是边界管理，不是固定框架

Harness Engineering
现在受到广泛关注，但它未必会以今天的形态长期存在。

LangChain
的历史已经提供了一个参照。早期多模型编排、chain、memory、agent executor
都像是必须由框架管理的复杂问题。那时模型弱，工具调用能力弱，产品接口也不成熟，把这些东西包装成框架确实有价值。但几年后再看，很多早期框架承担的工作已经被模型、API
和 coding agent runtime 吸收。你不一定要写一个
chain，也不一定要搭一套多模型编排框架。很多时候，把目标、上下文和验收标准说清楚，让现成
agentic runtime 自己查、自己跑、自己修，效果已经足够好。

Harness Engineering
可能正在经历同样的过程。今天它针对的是长任务、并行
agent、异步执行、可观测性、权限和评估这些模型与 runtime
还没有完全覆盖的边界。OpenAI 讨论的是环境设计，Cursor 讨论的是大规模
agent 编排，Anthropic 讨论的是一个 agent
连续跑几小时的时间扩展。三家都叫 harness
engineering，但它们实际解决的是不同边界。

因此，学习 Harness Engineering
的重点在于训练边界判断：这个脚手架是在补模型短板、补 runtime
缺口、补领域知识，还是补评估标准？如果它只是补模型短板，模型升级后要优先删除。如果它只是补通用
runtime
缺口，平台很可能很快吸收。如果它编码的是你的领域知识、风险边界和质量标准，它才值得长期维护。

好的 harness 也会留下副产品：失败样本、eval、review
记录、错误分类和上下文资产。这些东西可能反过来推动模型和产品 runtime
改进。但这只是辅助机制。主线仍然是边界迁移：今天值得自建的脚手架，明天可能变成商品化
runtime
的默认能力；而模型变强以后，人类又会把更长、更模糊、更高风险的任务交给它，新的边界继续出现。

## 真正上移的是人的工作

人的工作确实在上移。迁移方向是从执行到判断，从 coding 到 prompting
只是提示词层面的一个侧面。

底层会继续收敛到简单、确定性的接口：命令行、JSON、exit
code、文件系统、AGENTS.md、测试脚本、lint 规则。中间的 runtime
层会继续产品化，Claude Code、Codex、Cursor、OpenCode
会越来越像标准工作环境。真正拉开差距的是更上层的东西：context、skills、evals、contracts、domain
memory、cognitive framework。

Garry Tan 的 Thin
Harness, Fat Skills 也指向这条路：harness
只负责循环调用模型、读写文件、管理上下文和安全策略；真正的能力沉淀在
skill files 里。我们的实践也更接近这个判断：runtime 可以外包给 Claude
Code 或 OpenCode，skills、axioms、workspace routing、research
workflow、验收标准要自己维护。

这也是 cognitive framework
重要性上升的原因。模型越能执行，人类越需要负责定义问题、选择边界、建立验收、判断取舍。过去你要把过程写清楚：遇到
A 做 B，遇到 C 做
D。现在更有效的方式常常是定义结果：最终产物必须满足哪些条件，怎么验证，失败以后如何继续。过程交给
agent 探索，验收标准由人设定。

同样的模型、同样的
runtime、同样的工具，只要背后的认知上下文不同，产出可能从行动清单变成判断。Context
infrastructure 的对照实验正好说明了这一点：缺少个人判断框架的 AI
会输出正确但平庸的建议；接入长期沉淀的判断原则后，它开始能做非共识的分析。

AI
的进步没有让框架世界消失。它把低层补丁吸收到模型里，把通用执行吸收到商品化
runtime
里，也把真正难的部分推回给人：哪些能力该买，哪些能力该自建，什么标准定义完成，以及你凭什么相信它做对了。

## 鸭哥每日手记

日更的深度AI新闻和分析

订阅

Built with Kit

🔊

Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a>