---
layout: post.njk
source: https://yage.ai/share/claudeforce-pipes-not-products-20260901.html
speaker: yage.ai
title: |-
  管道不是产品：Salesforce
  把同一套接口发了两次，只有一次有人理
date: '2026-09-01'
summary: 文章探讨了软件厂商在为 AI agent 时代提供接口时，从最初的裸露接口（如 Salesforce 的 Headless 360）到最终封装成完整产品（如 Salesforce in Claude）的演进过程。核心观点是，真正促成企业采用的关键不在于底层接口本身，而在于对业务语义的深度封装、管理运维的整装打包以及终端分发的深度绑定，这三层能力构成了 agent 时代软件落地的最小采用单元。
area: tech-engineering
category: ai-application
tags:
  - agent-workflow
  - software-development
  - ai-application
  - ai-tooling
  - workflow-tools
people:
  - Marc Benioff
  - Patrick Stokes
companies_orgs:
  - Salesforce
  - Anthropic
products_models:
  - Claudeforce
  - Headless 360
media_books: []
draft: true
status: evergreen
---

2026 年 8 月 26 日，Salesforce 与 Anthropic 联合发布了
Claudeforce。主流财经媒体几乎在同一时间密集报道，第二天 Salesforce
股价大涨
23%，创下 2020 年以来最好的单日涨幅。往前数四个月，同一家公司其实在
2026 年 4 月 15 日的 TDX 大会上也做过一场发布，宣布推出 Headless
360，要把整个平台完整开放给 AI
agent。官方当时给出的原话是：「Everything on Salesforce is now an API,
MCP tool, or CLI command, and agents can use all of
it」。但在那天，主流财经媒体几乎没有给它版面。

这两场发布并非各自独立。Marc Benioff 在 Claudeforce
官宣当天明确提到，Claudeforce 正是运行在 Headless 360
之上，原话是「running directly on top of Salesforce via our new AIforce
UI harness, Headless 360, Data 360, Tableau, and
Slack」。也就是说，完全相同的底层能力，Salesforce 在四个月里推了两次。4
月推出的是一条裸露的连接管道，8 月推出的则是打包完整的应用产品。4
月推出的连接管道少有人用，8 月打包好的产品却引起了广泛关注。

顺着这个反差往下追，问题开始变得具体。眼下几乎所有软件公司都在解答同一个命题：自家的软件不仅要给人类操作，还要给各种
agent 调用。大家在形态上几乎一致转向了 MCP server。但 Salesforce
展现出的这四个月，更像一场对照清晰的自然实验。接口早早摆在那里，光靠接口什么都不会发生。真正促成采用的关键条件，全藏在接口之上的那几层。

## 四月那次，卡在哪

把 4 月的那场发布放回当时的语境来看。Headless 360 当时最核心的组件是
Salesforce Hosted MCP Servers，在 4 月 15
日当天同步进入通用可用（GA）阶段。MCP 作为 Anthropic 在 2024
年底开源的通信协议，当时已经成为 agent 连接外部系统的事实标准，像
GitHub、Slack、Notion 都已经推出了官方 MCP server。Salesforce
走出的这一步，按理说把 CRM
内部的数据资产、业务流转逻辑和权限管控全部通过 MCP
接口暴露了出来，理论上任何 agent 客户端都可以直接接入。

在行业声量层面，4 月的发布其实不能算失败。VentureBeat
当时刊发了深度分析，Salesforce
自身的开发者生态媒体也跟进得非常紧密。但如果把视角切到真实的采用层，在随后的四个月里，全网能查到的有效痕迹几乎只有教程，大约有
8 到 12
篇第三方的实操文章与演示视频，反复讲解管理员该怎么配参数、用户该怎么连进
Claude。但在公开渠道中，找不出哪怕一家企业把这套官方管道真正放进生产环境去跑实际业务。

去翻 Reddit
上的开发者讨论，一线工程师的真实反馈分成了清晰的两派。第一派尝试走官方路径，但在实操中遇到了不少阻碍。有个热帖列出了十个具体问题，其中最典型的一个是：明明
OAuth
流程显示授权成功，系统却依旧报错拒绝访问，排查到最后才发现是官方文档里的服务器
URL 漏写了一个路径分段。第二派开发者则直接绕开官方提供的
hosted MCP，自己用 Python 写了一层网关去封装旧的底层
API，给出的理由是：官方的 hosted MCP 在当时「totally
useless」。资本市场的独立调研也印证了这个冷清局面：TD Cowen 在
Claudeforce 发布前五天对生态合作伙伴做了一轮摸底，没有一位受访者说
Agentforce 是近期订单的驱动因素。

最有说服力的证据其实来自 Salesforce 管理层自己的复盘。据 Apex Hours
转述，Salesforce 应用与市场总裁 Patrick Stokes 后来坦承，TDX
大会之后确实有许多开发者开始对着 MCP server 搭建各种 agent
界面，但随后「immediately hit a
wall：管理认证、给一百多个用户执行权限……每个团队都在用糟糕的方式解决同一个管道问题，一次一个用户」。

把这些摩擦放在一起看，阻碍落地的原因主要在两个具体层面，与协议本身关联不大。第一道关卡落在管理运维面。要让官方管道正常跑起来，企业管理员必须手动走完七步配置：从激活
server、创建外部应用、精确配置回调 URL、设置 OAuth
策略，再到把生成的密钥手动复制给 Claude 客户端。而且认证 token
全都绑定在每个登录用户的个人账号上，一个团队有一百个员工，管理员就要重复做一百次认证分发。第二道关卡落在业务场景面。裸管道提供给
agent 的只是一堆原子
API，至于销售晨会怎么准备、商机健康度怎么评估，底层接口并不包含这些业务逻辑，需要
agent 自行拼装组合。教程讨论虽多，企业实际采用却几乎为零，这种断层构成了
4 月到 7 月之间的真实图景。

## 八月这次，多包了什么

到了 8 月，这款产品的正式名称定为 Salesforce in Claude，以一个内置了
37 个销售专用 skills 的插件形态重新亮相。对照 4
月的那张摩擦清单，这次发布多出来的增量恰好覆盖了三个层面。

第一个层面是管理面的整装打包。产品主页给出的核心承诺是：「An
admin connects Salesforce in Claude once, and it works for the whole
team from day
one」。企业权限管理不再需要一次配置一个用户，员工直接带着自己在
Salesforce
原生系统中的角色与权限接入，权限自动继承。官方甚至直接把这句话当成了核心卖点：「There’s
nothing new to stand up, nothing to re-audit.」

第二个层面是业务语义的深度封装。内置的 37 个 skills
全是任务导向的，比如 daily-briefing、pipeline-review、stakeholder-map
以及 close-plan 这些具体命名。每一个 skill
对应一线销售人员的一个真实工作流，把诸如哪个字段权重最高、商机健康度如何计算这些业务认知直接写入了执行逻辑。这层语义与底层的
MCP 截然不同：MCP 递给 agent 的是一张功能清单，而 skills 交付给 agent
的是一套做事的方法论。这里有一个细节：在官方产品页的宣传示意图里，公开展示的
15 个 skills 都围绕着一个代表 skill.md 文件的图标展开。按照 Claude
插件体系的底层规范，skills 本质上就是包含 SKILL.md
文件的特定目录，而这套标准正是 Anthropic 在 2025 年推向行业的开放 Agent Skills 规范，OpenAI
随后也在自身产品中悄悄采纳。换句话说，一家头部
SaaS
正在直接使用大模型厂商制定的开放文件格式来封装自身的业务任务。需要说明的是，官方目前并没有对这个实现细节给出明确声明，这
37
个文件本体也尚未对外公开，但综合插件运行机制和产品页的物料佐证，技术路径的走向已经相当明朗。

第三个层面是终端分发的深度绑定。如果说管理面和语义层解决了功能能不能用好的问题，分发层解决的则是用户究竟在哪里使用。这个插件直接内置在
Claude
界面中，而销售人员日常沟通与办公原本就在这个环境里。官方宣传页上有一句自我总结：「A
plugin you install instead of a stack you assemble by hand.」

不过，在看清增量的同时，也需要客观记录下这次发布尚未解决的问题。产品在官宣当天仅面向受限的
pilot 客户开放测试，真正的公开 beta 要等到 9
月才会上线。定价方案至今没有对外公布，企业在采购时还需要分别与
Salesforce 和 Anthropic 签订两份独立合同。Stokes 在接受采访时也提到：「You
can’t buy this on one piece of paper at the
moment」，暂时没法用一份合同完成这笔采购。在客户背书方面，官方没有给出任何一家具名的外部企业客户，唯一的证言来自
Salesforce 内部的销售主管。此外还有股价问题：8 月 26 日当天恰逢
Salesforce 发布财报，次日单日 23%
的股价拉升主要得益于超出市场预期的财务业绩以及做空 SaaS
资金的集中平仓，其每股收益里还包含着来自 Anthropic 股权投资所确认的 26
亿美元收益。Claudeforce 在其中扮演的角色，更像是一个叙事放大器，推动
Benioff 与 Dario Amodei 一起走上 CNBC 的直播演播室。但在开发者集聚的
Hacker News 上，关于 Claudeforce 的讨论帖最终只有
9 分。8
月的发布赢得了叙事层面的关注，而软件在真实业务场景里的采用深度，依然要等待
9 月公开 beta
后的实际数据给出检验。两次发布各占了一个不同的切面，这种对照恰恰说明了问题所在。

## 整个行业押了什么形态

跳出 Salesforce 单家公司来看，整个软件行业围绕 agent
形态形成共识的速度比预想的要快得多。Satya Nadella 在 2024 年底的 BG2
播客里说，业务应用这个概念本身，大概就会在 agent 时代坍缩，原话是「I
think the notion that business applications exist, that’s probably where
they’ll all collapse, right in the agent era」。Vercel 创始人 Guillermo
Rauch 在 2025 年 10 月写得更直白：工具开发者的工作「不再只是服务开发者，还要服务他们的
agent」，昨天的入门示例是一个交互网页，今天的入门示例则是一个能够行动的
agent。而在底层的协议演进上，OpenAI 于 2025 年 3 月采纳了 MCP，Google
随后在 4 月跟进支持，Anthropic 也在 12 月把 MCP 正式捐赠给了
Linux 基金会新设立的 Agentic AI Foundation。到了 2026 年 8 月，Google
原本主导的 A2A
协议也并入该基金会。伴随这一连串标准化动作，接口层迅速走向了商品化：各大公共资源库里收录的各类
MCP server 已经接近一万个，The New Stack
对此评价道「seemingly every SaaS service exposing an MCP server
now」。当市面上出现了一万套通用供水系统，单单接上一根水管就已经不再构成竞争壁垒。

在系统架构上，行业正在形成的共识是多层能力的复合堆叠，厂商无需做非此即彼的单选。Salesforce
官方在插件技术文档中给出了清晰的三层解析顺序：「skills first, then
the Salesforce CLI, then Salesforce MCP」。各层职责分工明确：skills
负责组织业务方法论与工作流程，CLI 负责提供确定性的本地指令执行，MCP
则负责底层安全连接与数据调取。不同的分层各司其职，没有厂商会在接口与技能之间做二选一。

与此同时，行业内部也始终保留着审慎与质疑的声音。LangChain 创始人
Harrison Chase 曾公开表示，当前的
MCP-1 很像当年的
USB-1，未来会出现设计更成熟的新协议。安全领域的数据也提供了佐证：GitGuardian
在公开的 GitHub 仓库中扫描出两万多个与
MCP 配置文件直接关联的泄露密钥；也有用户自述在单一开发环境中挂载了 58 个
server、汇集了 680 多个工具。在 MCP
Dev Summit 2026 上，行业自己给出的诊断是 MCP
已经进入承重状态，开放问题全在运营层：会话、蔓延、身份、审计。其中身份、会话、审计这几样，正是协议早年为保持简单而绕开的部分，如今一项项补回来，协议也随之变厚。这些批评并没有削弱
MCP
的行业地位，却指向了同一个事实：通信协议本身正在快速收敛，剩下的问题全在协议之上的层次。

## 怎么判断下一个

这场实验留下的框架可以复用。未来看到任何 SaaS 厂商宣布支持
agent，顺着四个层级逐一审视，多数新闻在第一层就露了底。

第一层看接口：厂商提供的是原生 MCP
还是第三方包装，底层的读写颗粒度究竟如何。接口层属于基础条件，在人人都有接口的今天，光有这一层不足以促成实际采用。第二层看语义：厂商有没有把业务规则沉淀为任务级别的执行单元，例如结构化的
skills、自动化 workflow 或者标准 playbook，还是仅仅提供原始
API。第三层看治理：agent
的操作能否继承企业既有的权限体系与审计日志，管理员是一次完成全局配置还是需要每个员工逐一授权，写操作的确认机制是强制拦截还是能够按需调整。第四层看分发：这些封装好的能力最终嵌入在哪个高频交互的客户端当中，厂商与模型生态之间建立了怎样的绑定关系。Claudeforce
在 8 月能够立住叙事，原因在于它补齐了第二、三、四层；而 4
月那次发布之所以少有人用，正是因为它只提供了第一层。

对于 Claudeforce 本身而言，接下来的真实走向取决于即将在 9
月到来的三个验证点。第一，伴随公开 beta 的启动，这 37 个内置 skills
的详细清单与读写权限粒度究竟会不会完全公开。第二，针对关键业务数据的写操作，系统的默认确认逻辑究竟如何设定。第三，市场上何时会出现第一家公开具名的外部企业客户。这三个来自一线的反馈信号，比任何发布会演讲都更诚实。

这场历时四个月的自然实验，留下了一条清晰的判断线索：给 agent
调用的接口如今已经不再稀缺，真正具备商业价值的，是将接口封装成完整产品的工程能力。业务语义的封装、组织治理的继承以及分发渠道的嵌入，这三层能力才是
agent
时代企业软件走向落地的最小采用单元。把管道接通只是第一步，把水装进容器里，才会有买家愿意买单。