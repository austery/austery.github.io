---
layout: post.njk
source: https://yage.ai/share/claude-code-trust-control-plane-20260701.html
speaker: yage.ai
title: 你的公司还应该用 Claude Code 吗？
date: '2026-07-01'
summary: 文章探讨了企业在使用 Claude Code 等 AI coding agent 时面临的安全与控制权问题。核心观点是，AI agent 的风险不仅在于代码外泄或命令失控，更在于其指令层和权限层的多重控制面。作者建议企业不应简单禁用工具，而应通过设置沙箱运行、建立完善的审计机制以及切分供应商控制面和企业控制面来治理高权限 AI agent 的行为。
area: tech-engineering
category: ai-application
tags:
  - coding-agent
  - security-risk
  - system-prompt
  - control-plane
people: []
companies_orgs: []
products_models:
  - Claude Code
media_books: []
draft: true
status: evergreen
---

企业审批 AI coding agent
时，通常会先问两个问题。第一，代码会不会外泄。第二，agent
会不会乱跑命令。前者可以通过商业 API、数据不训练条款和 DLP
网关缓解；后者可以通过权限提示、沙箱和代码审查缓解。现在，还要问第三个问题：谁在控制
agent 的指令层？

最近的两条线索把这个问题推到了台前。一条来自 thereallo.dev 对 Claude
Code 2.1.196 的逆向分析：在中国时区、非官方 endpoint
等条件同时满足时，客户端会在系统提示词的日期字符串里加入弱可见标记。另一条来自
GitHub issue #62061：Claude Code
曾存在从服务端配置读取额外系统提示词的机制。

这两条线索让第三个问题变得具体。Claude Code
不是一个只给补全建议的编辑器插件。它能读代码库、改文件、跑 Shell、调用
Git、连接 MCP
工具，也可能触达本地凭证和内网资源。企业把它放进开发环境时，实际上是在引入一个特权开发运行时。

在这次事件中，地域识别和账号封禁确实是现实风险。尤其是使用非官方
endpoint、企业网关、中转代理、转售服务和中国相关模型服务的用户，会直接面对账号风控和工作流突然中断的隐忧。然而，更深层的问题在于企业的控制面与审计。如果高权限
agent
的上下文窗口和策略层有一部分能被闭源供应商远程改变，而企业默认看不见改了什么，这就超出了普通封号问题，变成了研发环境控制权的问题。

## 这次标记明显指向中国相关
endpoint

安全研究者 thereallo.dev 在 Claude
Code Is Steganographically Marking Requests 里披露，他逆向了 Claude
Code 2.1.196
的二进制，发现客户端会在特定条件下修改系统提示词里的日期字符串。

逆向摘录披露的逻辑显示，这不是一个只看中国时区的简单判断。它的触发起点是自定义
ANTHROPIC_BASE_URL，也就是官方
api.anthropic.com 之外的
endpoint。只有在这个前提下，分类器才会读取系统时区和目标
hostname，并对照内置的 known domains 与 lab
keywords。单独处在中国时区，但没有配置自定义
endpoint，不会进入这套标记。

这套分类结果会被编码进系统提示词里的日期行，也就是
Today's date is YYYY-MM-DD.：

分类条件

日期分隔符

Today's

里的撇号

对应 Unicode 字符

默认：官方 endpoint，或未命中 known / lab

-

普通撇号

'

ASCII

U+0027

自定义 endpoint + 命中 known domain

-

右单引号

’

U+2019

自定义 endpoint + 命中 lab keyword

-

修饰字母撇号

ʼ

U+02BC

自定义 endpoint + known / lab 都命中

-

修饰字母锐音符

ʹ

U+02B9

自定义 endpoint + 中国时区：

Asia/Shanghai

或

Asia/Urumqi

/

按上面 known / lab 条件选择

-

也就是说，cnTZ
这个条件通过日期分隔符表达：2026-06-30 会变成
2026/06/30。endpoint 是否命中 known domain、lab
keyword，或两者都命中，则通过几个肉眼接近的 Unicode 撇号表达。

thereallo 还公开了配套的 cc-domains.js。这份列表有
147 个 known domains 和 11 个 lab keywords。关键词包括
deepseek、moonshot、minimax、xaminim、zhipu、bigmodel、baichuan、stepfun、01ai、dashscope、volces。域名列表中能看到
alibaba、alipay、antgroup、baidu、netease、sankuai
等中国科技公司和服务标识。

在安全边界上，这套机制不产生额外的网络外传，也不属于远程代码执行。它是在本来就会发送给模型的
system prompt 里做 prompt-level fingerprint。Anthropic
官方没有公开承认或专门解释这段逻辑，但这正是企业安全团队需要警惕的地方：它没有新增显眼的
API
请求字段，也没有弹出权限提示，而是把环境分类结果放进了系统提示词的普通日期句里。对模型来说，这是输入上下文的一部分；对大多数企业审计来说，这类细微文本变化很容易被当成无关噪音。

所以这件事不用绕着说。thereallo
披露的触发条件和列表，明显是围绕中国时区、中国相关 endpoint、中国 AI lab
和中转/转售场景设计的。对中国用户来说，这不是“想太多”，而是实实在在的使用风险。自定义
ANTHROPIC_BASE_URL 本身并不等于滥用。Alibaba Cloud 的 Model
Studio 文档 和 Ask Sage 的 Claude
Code integration 文档
都把它作为正常接入方式。企业网关、区域化服务、合规代理都可能需要改 base
URL。

围绕这次披露，最容易被独立核对的是二进制身份：npm 上确实存在
@anthropic-ai/[email protected] 和 darwin-arm64
平台包；下载后的二进制 SHA256 与 thereallo 原文一致；macOS
签名有效，TeamIdentifier=Q6L2SF6YDW。这至少说明，争议指向的是
Anthropic 官方签名分发的客户端，而不是一个来路不明的第三方改包。

这件事在 Hacker News
上引发大量讨论。社区争议点也很集中：供应商为了防
reseller、反转售、反蒸馏做客户端标记，有商业动机；但用混淆列表和不可见字符在系统提示词里埋标记，对本地开发工具来说越过了许多企业的透明度预期。

## 远程系统提示词实验暴露了更大的控制面

另一个线索来自 GitHub issue #62061。这个
issue 指出，Claude Code v2.1.150 曾引入 tengu_heron_brook
机制：客户端可以从 Anthropic
的服务端配置或实验系统读取一段文本，并把它加入本地 agent
的系统提示词。

这里不需要读 minified function，也不需要理解 GrowthBook
的实现细节。high-level 的含义已经足够：一个本地运行的 coding
agent，其系统提示词并不完全来自本地安装包、项目文件或用户配置。它曾经有一条通道，可以从供应商服务器读取一段额外系统提示词。

Anthropic issue
内的维护者回应也基本承认了这一类实验的存在。他说团队有时会做 system
prompt changes 的实验，用来评估质量和避免回归，并给出
CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC=1 与
DISABLE_GROWTHBOOK=1 作为
opt-out。这个回应不是正式安全公告，但足以说明：远程系统提示词实验不是社区凭空想象。

这不等于远程代码执行。Claude Code 的 security 文档
明确说，permission rules
由客户端执行，不由模型提示词执行。系统提示词改变不会自动绕过权限系统。

但企业不能只看这一层。系统提示词决定 agent
想做什么，权限系统决定它能做什么。开发者一旦为了效率放宽 allow
rules、启用 auto mode 或使用
--dangerously-skip-permissions，这两层之间的距离就会缩短。Anthropic
自己在 auto
mode 工程说明 里也说，完全跳过权限提示在多数场景下并不安全。

真正的风险是组合出来的：本地权限层允许 agent
读写文件和跑命令；上下文指令层决定 agent
的行为倾向；供应商策略层决定哪些远程实验、风控、账号规则和客户端配置会生效。

AI coding agent
的三层控制面：本地权限、上下文指令和供应商策略共同影响 agent
行为

普通 IDE 插件最多改变编辑器体验。AI coding agent
改变的是本地开发循环。它可以读 repo、跑测试、安装依赖、改
CI、调用内网工具、提交代码。这样的工具如果存在默认不可见的远程指令层，安全评审就不能只问“它有没有上传源码”。还要问：它的指令从哪里来，什么时候会变，变了之后谁能看见。

## Anthropic
的商业边界会进入企业研发连续性

这件事还需要放到 Anthropic 的供应商行为里看。Anthropic 是一家 policy
posture
很强的公司。它对安全、合规、竞争性使用、区域访问和第三方封装都有明确立场，而且会执行这些立场。

Anthropic 的 Commercial
Terms
限制客户用服务构建竞争性产品、训练竞争模型或未经批准转售服务。Supported
Countries 页面也写明，Anthropic
保留基于实体多数所有权归属拒绝提供服务的权利。这些条款本身不奇怪。大模型公司保护算力、模型和商业边界是正常行为。

问题在于，AI coding agent
已经进入研发主路径。供应商边界一旦执行，就可能直接变成工程连续性问题。

TechCrunch 报道过 Windsurf 称 Anthropic 在少于五天通知下限制其 Claude
3.x first-party capacity，原因与竞争关系有关。WIRED 报道过 Anthropic
撤销 OpenAI 对 Claude 的 API access，Anthropic 的解释是 OpenAI
的使用违反了服务条款。VentureBeat 报道过 Anthropic
加强技术防护，阻止第三方应用伪装成官方 Claude Code 客户端，并影响到
OpenCode 等第三方 harness 用户。

这些事件不能推出 Anthropic
会对普通企业恶意断供。这个结论没有证据。但它们足以说明：当企业把研发流程绑在单一闭源客户端、单一模型供应商和单一账号体系上，供应商的商业判断、区域政策和风控系统会进入业务连续性评估。

过去一个编译器厂商停止服务，企业至少还能继续在本地编译。今天如果
agent
工作流依赖云端模型、官方客户端识别、账号策略和远程配置，供应商的一次策略变更就可能让团队的开发节奏受到影响。

## 企业不该禁用，而该换一套准入标准

直接禁用 Claude Code
不是好答案。禁令会把使用行为赶到个人账号、个人电脑和影子 IT
里。更现实的做法是承认 AI coding agent
的生产力价值，同时按特权开发运行时来治理。

第一，默认禁用 bypass。企业应通过 settings、MDM
或系统配置禁用 --dangerously-skip-permissions 和
bypassPermissions。auto mode
可以试点，但要限定在低风险仓库、隔离环境和可回滚任务里。涉及生产凭证、云资源、CI
配置、依赖安装和 Git 写操作的任务，仍应保留人工确认。

第二，把 agent 放进沙箱。不要让 agent 默认继承开发者宿主机上的 SSH
key、云凭证、生产 kubeconfig、package registry token 和所有
.env。高权限任务应在容器、VM 或远程 dev environment
中运行，只挂载必要目录，限制网络出口，任务结束后销毁环境。需要全自动执行时，隔离比相信提示词更可靠。

第三，建立企业自己的审计面。Claude Code 的 Monitoring
文档 提供 OpenTelemetry 和 raw API body logging，但 raw bodies
默认关闭，开启后会记录完整对话历史，可能把源码和隐私数据带进日志系统。企业要自己定义审计粒度：tool
name、Bash command、MCP
server、文件路径、模型请求摘要、拒绝原因、策略命中记录。默认不要把完整
prompt 和完整源码写入日志，除非已经有脱敏、访问控制和保留期策略。

第四，切开供应商控制面和企业控制面。Anthropic 的 server-managed
settings 说明客户端可以从 Anthropic
服务器拉取策略。企业不能只依赖供应商远程策略来保护自己。关键限制要落在本机配置、设备管理、网络网关和仓库规则里。对于不需要远程实验的环境，CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC=1
和 DISABLE_GROWTHBOOK=1 应该作为 baseline 考虑。

第五，保留
fallback。企业至少要准备两条退路：模型退路和客户端退路。模型退路可以是
Anthropic API、AWS Bedrock、Vertex、OpenAI、Google
或本地开源模型的组合。客户端退路可以是 Claude Code、OpenCode、Codex
CLI、内部 harness 或 IDE agent
的组合。不要让某个供应商账号不可用直接等于团队今天不能开发。

采购时还要问清楚几个问题：系统提示词实验是否可见；feature flag 和
bootstrap cache
的生命周期是什么；企业能否禁用非必要远程实验；完整请求体如何审计且不泄漏源码；二进制更新、签名和版本准入如何控制。供应商答不上来，不代表不能用，但应该进入风险登记。

## 信任的前提是能审计

AI coding agent
的价值来自放权。不给它读仓库、不让它跑测试、不让它改文件，它就只是一个聊天框。可是放权以后，信任就不能只靠品牌、模型能力或供应商善意维持。

Claude Code 这次暴露出的两条线索，一个是针对中国相关 endpoint
和时区的 prompt-level
标记，一个是远程系统提示词实验。它们都可能有合理产品解释：反转售、反滥用、质量实验、灰度发布。但合理动机不等于可接受控制。对企业来说，一个高权限
agent 的行为应该能被看见、被记录、被限制、被回滚。

所以问题不是“你的公司还要不要用 Claude
Code”。更准确的问题是：你的公司有没有能力把 Claude Code
当成特权开发运行时来管。

如果答案是有，继续用，而且可以用得更大胆。把它放进沙箱，接入审计，禁掉
bypass，保留多模型退路，让 agent 做更多执行工作。

如果答案是没有，那风险不在 Claude Code
这一款工具上。风险在于公司已经把本地研发环境交给一个闭源、远程可变、默认不可充分审计的控制面，却还以为自己只是装了一个插件。