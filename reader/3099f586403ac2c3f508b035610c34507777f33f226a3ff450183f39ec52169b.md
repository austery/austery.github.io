---
layout: post.njk
source: https://yage.ai/share/ai-coding-harness-comparison-20260630.html
speaker: yage.ai
title: |-
  鸭哥的观察：为什么现在的 AI 编码 Harness
  已经切换无感了？
date: '2026-06-30'
summary: 文章探讨了当前 AI 编码工具（如 Claude Code, Cursor, Codex, OpenCode）在日常开发任务中的高度同质化和可互换性，认为它们在底层智能与辅助功能上已趋于收敛。作者指出，Google Antigravity 在模型接口稳定性和软件工程成熟度方面存在明显掉队，导致其无法进入日常流的竞争。最终结论是，选择工具应基于个人对云端托管、本地交互或自主定制等工作流特征的侧重。
area: tech-engineering
category: ai-application
tags:
  - coding-assistant
  - model-convergence
  - software-development
  - agentic-workflow
people: []
companies_orgs:
  - Google
products_models:
  - Claude Code
  - Cursor
  - Codex
  - OpenCode
media_books: []
draft: true
status: evergreen
---

中文互联网上对于各种 AI 编码工具 (Coding Assistant)
的技术焦虑，表现得像潮汐一样，一波接一波。

一会儿，社交平台和公众号刷屏狂吹 Claude
Code，仿佛只要不把终端切换过去，你的开发效率就会落后于时代；一会儿，独立开发者圈子里又狂推
Codex；而隔一段时间，大家又会因为 Cursor
收费或者额度紧缩而产生集体焦虑，抱怨工具不给力了。

实际上，这种追赶风口的焦虑，大可不必。

对于 95% 以上的日常普通的增删改查开发任务，各大 AI 编码 Harness
在底层智能与辅助功能上已经高度重合收敛。在今天的日常项目下，它们完全是
interchangeable（可互换的）。

然而，Google 的 Antigravity
却成为了唯一的例外。它在模型接口稳定性和软件工程成熟度两个维度上，都出现了严重的掉队。

## 饱和同质化：日常开发下的可互换时代

当我们静下心来做横向对比时，会发现主流 AI
编码工具的发展正处于一个全面饱和的平台期。

### 1.
模型能力饱和：顶级任务略有差异，日常任务彻底拉平

在极少数超长上下文、超复杂架构重构的顶尖工程中，各家模型在推理深度上确实存在微小差异。但对于日常绝大多数的日常编码任务来说，模型的能力已经严重溢出。

甚至在实际开发中，开发者出于速度和价格的考虑，经常会故意放弃最顶级的模型（例如
Claude Opus 4.8 或 GPT 5.5），转而选择更便宜、更快速的模型。

在实际体感中，比如基于近期表现不俗的 GLM-5.2
运行日常代码修改，其响应速度非常快，且智能水平完全在够用线之上。虽然偶尔能察觉到它们与顶尖模型在极致长任务里的差距，但在
95%
场景下，它们的表现毫无破绽。底层大模型的同质化，抹平了工具在大脑智能层面的原生代差。

### 2. Feature
矩阵饱和：大家都有的标配

如果我们把各大 AI
编码助理的功能矩阵拉出来，会看到一个高度重合的图景。

下图展示了 2026 年 6 月全球几大主流编码 Harness 的功能矩阵对比：

AI 编码工具功能矩阵对比

从矩阵中可以看出，Sub-agent
拆分派发、云端托管工作区、背景定时/延时任务，各家在功能上都已齐备。

在客户端方面，Cursor 拥有官方的移动端 App；而 OpenCode 同样拥有支持
iPadOS/visionOS 和内嵌 SSH
隧道的移动客户端，这并非是官方商业软件，而是由鸭哥开发并完全开源的项目（iOS
版本：opencode_ios_client；Android
版本：opencode_android_client，克隆
Git
仓库的源码即可部署）。这证明在软件功能拼图上，开源生态和三方插件已经迅速填补了官方商业工具筑起的壁垒。

对于延时执行任务（例如起一个 timer 像 reminder
一样在后台回看），Claude Code 通过本地 Desktop Routines 交互式支持；而
OpenCode 更是拥有本地通用的 Process Launcher 进程管理器，支持 SQLite
级别的延迟任务持久化和漏跑任务自动补偿。各大工具在功能版图上已经没有任何本质的代差。

### 3. Claude
Code：高阶功能被体验问题折损拉平

Claude Code 独占的 Agent Teams (通过 13 个
Peer-to-peer 操作 API 进行团队协作) 和 Dynamic
Workflows (动态生成 JS 编排脚本处理大规模 sub-agent)
在发布时吸引了大量关注。然而在实际工程环境中，这些机制仍处于早期阶段，并且其实际体验被以下几处问题严重折损：

经常断连的 Remote 遥控连接：Claude Code 提供了 “Remote” 遥控功能，允许手机 App 连回电脑进程以监控终端会话。但在实际使用中，它的连接管道非常脆弱，极易无故断开；而在 Cursor 或是 OpenCode 已经提供平稳顺畅的端到端遥控体验时，这种频繁的中断给离线监管带来了极大的不便。

严厉的风控与误伤机制：Anthropic 对生化/武器安全、网络对抗以及模型蒸馏三个核心领域执行了严格的安全策略（具体细节见先前发表的深度解析：Fable 5 的暗中破坏机制 以及 Claude Code 八层纵深防御体系）。一旦开发者的代码片段或查询词无意中触发了生化、安全对抗或者是模型蒸馏（如本地上下文自整理逻辑被误判为模型蒸馏企图）的风控边界，其账号就会面临风控封禁，或者导致整个会话降级。

服务端机制与 Bug 导致的“暗中降智”：许多开发者常遇到模型生成质量明显下降，其根源往往不在本地，而在服务端的降级与防御策略。根据核实的事实，在高负载时，Anthropic 调度系统会把请求透明地转给老旧版本的模型；同时，一旦网关检测到与前沿模型开发相关的提示，系统会启动 Steering Vectors (方向向量干扰) 或 Stealth 提示词改写，暗中直接降低模型的响应质量且不予通知，折损了实际的编程表现力（详细逻辑见：Fable 5 的暗中破坏机制）。

这几项工程痛点，直接抵消了上述高阶功能的优势，使 Claude Code
的日常综合表现回落到与 Cursor、Codex、OpenCode 相同的水平线。

这得出了一个显而易见的结论：在日常开发中，各大 AI 编码 Harness
具有极高的可互换性（interchangeable）。如果开发者一时间无法感知到它们之间的差别，选择哪一款都不会影响工作效率；而一旦开发任务复杂到能显式暴露各家底座性能的微细鸿沟时，开发者自然会建立明确的偏好，也就不再需要四处搜寻对比指南了。

## 掉队的例外：难以走进日常流的
Google Antigravity

既然主流工具都相差无几，为什么我们却唯独把 Google 的 Antigravity
排除在外？

因为它在智能 API
稳定性与软件成熟度两个维度上，都出现了严重的掉队。

### 1.
智能掉队：Thinking Token 冲突导致的 length 截断

底层的 Gemini 3.5 Flash
模型响应迅速，虽然偶尔会出现逻辑瑕疵，但基本能与 GLM
划在同一档次。然而真正影响开发流程的，是 Gemini API
本身的内生计算机制。

在开发中，如果我们使用非官方的编码 Harness（比如通过 LiteLLM 或
OpenCode 接入 Gemini
API）来执行长输出任务，常常会遇到模型输出到一半就突然异常中断的现象。

通过技术调试，我们发现了藏在背后的 API 逻辑缺陷：

Gemini 3.0+ 引入了内生思考预算 (Thinking Budget)
机制。在处理复杂编码逻辑时，如果开启了 adaptive thinking
(自适应思考模式)，模型内部的思考链 (Reasoning Trace)
同样会消耗并扣减 API 允许输出的最大字符数
(max_output_tokens)。

这就引发了机制上的冲突：即便将最大输出长度设得很宽，当 Gemini API
面对复杂编码任务时，其内生思考机制会生成极长的推理轨迹，在尚未输出实质代码前便将
max_output_tokens
消耗殆尽。这最终导致正文在生成中途因为触发 length
限制而被截断。同时，由于这种自适应思考通常缺少及时的流式返回，使得网络连接容易被客户端判定为超时并强制挂断。

虽然在官方原生的 antigravity 客户端里，Google
团队做了一些针对性的改进，稳定度有所回升，但底层 API
的固有机制依然让开发面临着代码中断的隐患。

### 2.
软件成熟度掉队：大公司割裂的产品线与迭代滞后

除了接口设计外，antigravity 的软件成熟度同样存在明显的工程局限。

客户端运行 bug 频发：antigravity 桌面端与 IDE 插件经常出现无响应和死锁。在连续使用时，系统容易陷入僵死状态，需要开发者在活动监视器中强行结束进程（kill）并重启。

产品线分割与认知灾难：与其他 Harness 精简清晰的单一产品线相比，Google 展现了典型的大公司架构割裂。

远程 SSH 迭代停滞：一年前 antigravity 官方声称“SSH 远程连接只支持 Linux 主机，不支持 macOS Host”。一年过去了，直到 2026 年的今天，这个限制依然没有任何改进。这直接导致苹果环境的本地 Context 基础设施无法跨机器复用，失去了异地协同的价值。

下图展示了 Google Antigravity 割裂的产品架构：

Google Antigravity
割裂的产品架构

Google 将其分割成了 5 个独立的组件（Antigravity 2.0
桌面端、Antigravity IDE 编辑器、Antigravity CLI 终端、SDK、云
API），并在 6 月 18 日暴力下线了 Gemini CLI
强迫用户重新配置迁移。这种大厂赛马冗余的产品设计，制造了不必要的认知混乱。

## 结语：可互换时代的选型指引

剥离了被过度营销的噱头后，最真实的结论是：除去掉队的
Antigravity，Cursor、Codex、Claude Code 和 OpenCode
四家在日常开发任务中并没有拉开体验代差。在同质化收敛的趋势下，它们早已到了可以无缝无感切换的互换时代。

因此，如今选择哪款工具，并不是要在智能层面分出高下，而是取决于个人对以下工作流特征的侧重：

侧重云端托管与移动闭环：如果需要离开电脑后依然能通过手机 App 实时查看 Always-On 离线编译与大工程追踪，Cursor 的官方移动 App 与云端 Sandbox 闭环是较为完备的方案。

侧重本地交互与经典稳健：如果习惯经典的 API 调用模式，看重连贯的本地交互，避开花哨的测试期功能，Codex 依旧是极度稳健和高连贯的选择。

侧重本地大修与任务编排：如果经常面临复杂系统重构，并且能够忍受极不稳定的 Remote 遥控掉线率以及严苛的生化/蒸馏分类器风控判定，Claude Code 凭借 Agent Teams 和 Dynamic Workflows 在复杂本地编排中仍占有一席之地。

侧重自主定制与开源可控：如果看重隐私和绝对掌控权，希望随手定制移动遥控端和延时调度逻辑，那么由个人开源维护的 OpenCode 移动端及其 Process Launcher 本地网关留出了最大的腾挪余地。

而在大模型能力迅速弥合的浪潮下，Google 的 Antigravity
彻底掉队了。它在智能 API 层面由于内生 Thinking Token
的冲突截断导致长代码随时腰斩，在软件工程上陷入了死锁卡死与五组件命名分裂的境地。在消除了“Google
制造”的光环后，它在这一波切换无感的可互换大潮中，已经丧失了与主流并列对比的资格。