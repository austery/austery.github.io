---
layout: post.njk
source: https://baoyu.io/blog/2026-04-06/how-openais-codex-team-builds-with-codex
speaker: baoyu.io
title: 访谈｜Codex 团队如何用自己的产品构建产品——整个 Spec 只有 10 个要点 | 宝玉的分享
date: '2026-04-06'
summary: 本文探讨了 OpenAI Codex 团队如何通过极简文档和 AI Agent（如 Codex 本身）高效开发产品。文章揭示了产品管理角色的转变、OpenAI 特有的规划哲学、Codex App 的诞生，以及“能动性”在招聘中的重要性，展现了 AI 时代下软件开发与组织模式的创新。
area: tech-engineering
category: ai-application
tags:
  - ai-development
  - product-management
  - developer-experience
  - workflow-automation
people:
  - Alexander Embiricos
  - Romain Huet
  - Peter Yang
  - Peter Steinberger
  - Scott Belsky
  - Thomas Ricouard
companies_orgs:
  - OpenAI
  - Stripe
  - Adobe
  - Anthropic
products_models:
  - Codex
  - GPT-5.2 Codex
  - Codex App
  - ChatGPT
  - Linear
  - OpenClaw
  - Imagen
  - Sora
  - Codex Monitor
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-04-06

# 访谈｜Codex 团队如何用自己的产品构建产品——整个 Spec 只有 10 个要点

作者：

宝玉

OpenAI Codex 团队的产品规格文档只有 10 个要点。不是说每个功能的文档只有 10 个要点，而是整个产品的 spec 就这么多。设计师写的代码量超过了六个月前工程师写的。50 到 100 人的团队，直到最近才有了第二个产品经理。

这些数字来自 OpenAI Codex 产品负责人 Alexander Embiricos 和开发者体验负责人 Romain Huet。两人在 Peter Yang 主持的 Behind the Craft 节目中，详细讲述了 Codex 团队如何用自己的产品构建产品，为什么中期路线图在 OpenAI 行不通，以及 PM 这个岗位可能正在从“领导者”变成“填空人”。

原始视频：https://www.youtube.com/watch?v=9qXc-THAvc0

> Alexander Embiricos（下文简称 Alex）是 Codex 的产品负责人，此前有五年结对编程产品创业经验。Romain Huet 是 OpenAI 开发者体验负责人，此前在 Stripe 担任开发者平台产品负责人。

要点速览：

Codex 团队几乎不写产品规格文档，只有涉及多人协调或重大决策时才写，而且往往只有 10 个要点的长度

OpenAI 内部的规划哲学是只做近期（8 周以内）或远期（方向感），永远不做中期产品路线图

GPT-5.2 Codex 在 2025 年 12 月发布是关键转折点，模型能力跨过了"可以可靠长时间独立工作"的门槛，直接催生了 Codex 桌面应用

Codex 团队刻意保持“海盗船”式运作，50-100 人的团队长期只有一个 PM，跨职能协调极少

Alex 认为 PM 不是领导岗位，而是”填补空缺”的岗位，在 AGI 时代最重要的人类品质是兴趣和能动性

## 10 个要点就够了

Peter Yang 开门见山：你们还写 spec 吗？

Alex 回答得很干脆：Codex 团队几乎不写产品规格文档。只有在问题复杂到一个人脑子装不下、需要多人协调的时候才会写。而且即使写了，也短得惊人。

> 我们在 Codex 团队写的 spec 非常非常少。就算写，也就十来个要点，就这样了。
> （“We write very, very few specs on the Codex team. We're talking like 10 bullets or something, and then that's it.”）

他解释了背后的逻辑：既然大部分编码工作已经可以委派给 AI Agent，一个人能处理的范围就大了很多。过去需要三个人协调的事情，现在一个人用 Codex 就能探索清楚。“让离金属最近的人做尽可能多的决策”是核心原则。

Romain 补充了一个更具体的例子。他在节目上直接演示了 Codex 的 plan mode（规划模式）：给 Codex 一个正在开发的 iOS 应用项目，不给任何具体指令，只说“我们下一步该做什么？”Codex 会自动分析代码库现状，提出几个方向让人类选择。

这个场景揭示了一种新的工作方式：产品规划不再是人类先想清楚再写文档，而是人和 AI Agent 一起在代码层面探索可能性。

## PM 用 AI 做”思维探索”，然后把思考分享给工程师

Alex 描述了自己作为 PM 使用 Codex 的三种模式。

简单改动直接上手，用 Codex 生成代码、测试、提交 PR（代码提交合并请求）。

> 对于一个小改动来说，直接提一个好的 PR，往往比找人沟通、让他们在一万件事情里把这件排上优先级要快得多。
> （“For a small change, it's often faster to send a PR than it is to communicate to someone and get them to prioritize that task when they have 10,000 other things to do.”）

中等复杂度的改动，他会让 Codex 先做一个实现计划。

最有意思的是第三种：他有时候有一个模糊的想法，甚至连具体功能都没想好，就直接在 Codex 里和模型对话，让它去代码库里探索、提问、生成方案。他经常不会真的使用这些方案，因为改动太复杂了，他不打算自己维护。但通过这个过程，他对问题有了更好的理解，然后把这份理解（而非计划本身）分享给工程师。

用 Alex 自己的话说：”我不是在写代码，我是在建立心智模型。”

谈到设计师角色，Alex 说：

> Codex 团队的设计师现在写的代码量，超过了六个月前一个工程师写的代码量。
> （“The designers on the Codex team write more code now than was written by an engineer six months ago.”）

他接着说，团队成员拿他提交的 PR 数量开玩笑。他没有透露具体数字，只说“确实应该更多”。但他认为这已经不是重点了。现在的关键问题不再是“你能不能生成代码”，而是“你选择做的事情对不对”以及“你怎么保证质量”。

他特别指出，虽然 Codex 团队绝大多数代码是由 AI Agent 生成的，但他们在系统思考和质量把控上投入了大量精力。凭感觉编程（vibe coding）可以用来说“整个 app 是 AI 写的”，但 Codex 团队不是这么运作的。

## 只做近期和远期规划，永远不做中期

Peter Yang 问：你们有年度路线图吗？

Alex 说两样都不是。他提到一个 OpenAI 内部研究员 Andre 给他的建议：

> 在 OpenAI，你要么做近期规划，要么做远期规划，但永远不要做中期规划。
> （“At OpenAI, you either plan near-term or long-term, but you never plan medium-term.”）

近期是 8 周以内，最多 8 周，而且要是一个具体的目标，团队能够围绕它集中发力。OpenAI 擅长的就是这种短周期的团队冲刺。

远期是一种“感觉”。比如：一年以后我们会有更聪明的模型，用户不会想把自己的电脑借给模型用（因为那样一次只能做一件事），会有无限多个模型同时独立工作、自己验证结果、甚至自己部署和监控代码，用户可能根本不需要主动输入提示词。

中间那段呢？产品路线图？基本不存在。他们有的是长期方向加上他们认为能朝那个方向推进的具体项目。

> 这种规划方法的前提是模型能力在快速变化。当你不确定三个月后模型能做什么，中期路线图就变成了猜测。但这个前提本身就值得追问：如果模型进展放缓了呢？

## Codex App 的诞生：从 18 个终端窗口到一个桌面应用

Alex 用 Codex App 的开发过程来说明这套规划方法怎么落地。

远期愿景：用户需要一个界面，让多 Agent 协作变得自然。不能绑定在某个特定的文件夹或 IDE 里（比如 VS Code 一次只能打开一个工作区），因为未来用户会同时委派多个任务给多个 Agent。

问题的出现：2025 年 12 月 GPT-5.2 Codex 发布后，模型能力跨过了一个关键门槛：可以接手更长、更复杂的任务，一次就做完。用户开始用 tmux（终端多路复用工具）同时运行大量 Codex 会话。社交媒体上出现了一张广为流传的照片：Peter Steinberger 在三块显示器上同时开了大约 18 个终端窗口运行 Codex。

> GPT-5.2 Codex 于 2025 年 12 月中旬发布，是当时 OpenAI 最强的编码模型，支持长时间独立工作和大规模代码变更。据 OpenAI 官方数据，发布后 Codex 整体使用量翻了一倍。

但 Alex 意识到，只有顶尖 1% 的工程师会用终端并行的方式工作。如何让这件事变得直觉化？

团队内部其实对此有争论：IDE 扩展已经很受欢迎了，要不要就专注做好那个？CLI 也很有需求。真的需要一个独立的桌面应用吗？

最后推动项目启动的不是一份 spec，而是一份说明“为什么我们认为做一个 app 是好主意”的文档。app 的具体形态是在构建过程中逐渐成形的。

Romain 补充了一个关键的技术细节：Codex App、IDE 扩展和 CLI 底层共用同一套开源的 Rust 核心（Codex harness），这让三个产品形态能够共享代码和能力。

> Codex App 于 2026 年 2 月正式发布，首先支持 macOS，后扩展到 Windows。据 OpenAI 数据，发布当月有超过 100 万开发者使用了 Codex。截至 2026 年 3 月，Codex 周活跃用户超过 200 万。

## 让最前沿的用户拉你进未来

Alex 谈到了 Codex 产品设计的一个核心原则：先为 power user 做可配置性，再为普通用户做简化。

因为 Codex 核心是开源的，用户会直接去改源码。Alex 说了一件让他很高兴的事：团队还没把某个功能上线到生产环境，推特上就有人在抱怨这个功能不好用了。用户直接 fork 了源码，自己启用了未发布的功能。

他把这视为产品优势：最前沿的用户在和团队一起探索未来。他们的实际使用方式就是产品方向的信号。比如子 Agent（sub-agents）这个概念，Codex 已经在底层支持了，用户可以自己启用、实验，但产品层面还没有主动触发它。团队在观察用户怎么用，再决定怎么简化。

> 我们最前沿的用户和我们一起住在未来，还把我们往未来拽。
> （“The cutting edge of your users are just absolutely living in the future with us and pulling us into that future.”）

但 Alex 也承认，如果只为这类用户构建，产品会变得非常难理解。所以他们的设计哲学是：核心交互要做到极简，用他的话说就是“让产品几乎隐形，让模型的能力自然显现”，然后通过分层让 power user 自己去发现更深的功能。他用了一个比喻：用 Codex App 就像打游戏，一层层解锁功能。

## 50-100 人团队的“海盗船”式运作

Peter Yang 问：你是 Codex 唯一的 PM，团队有 50 到 100 人，你每天怎么过？

Alex 说他不知道怎么回答这个问题，想了想发现自己有几种不同的“模式”。

执行模式：在产品发布前，他大量使用 Codex，用它来了解 Slack 上的反馈、让 Codex 总结反馈并发到 Linear（项目管理工具）、用 Codex 理解代码库状态、直接用 Codex 提交代码改动。他说判断自己是不是在执行模式的标志之一是他在推特上发了多少东西。发得多 = 在发布节奏里。

协调模式：在规划新方向的时候，他花更多时间思考和沟通，用 Codex 更多是做文字工作而非写代码。

团队刻意保持低摩擦运作。Alex 说他们”有意识地像一支海盗船”，跨职能协调极少。直到最近才有了第二个 PM。大部分人都是工程师，汇报结构极简。

但他也提到一个正在出现的挑战：越来越多 OpenAI 内部的非技术团队也在用 Codex App 做非编码工作。这意味着 Codex 的定位正在从“开发者工具”向更通用的方向扩展，而这需要和 ChatGPT 团队做更多跨职能协调。

> 2026 年 4 月，据路透社报道，Anthropic 的 Claude Code 对 OpenAI 构成的竞争压力促使 OpenAI 将更多资源转向 Codex 和企业工具。Codex 产品负责人 Alex 近期接受 Sources 采访时表示，最终目标是把 Codex Agent 带给 ChatGPT 的 9 亿用户。

## 开发者体验：Codex 成为所有开发者平台的入口

Romain 从开发者体验的角度补充了另一个观察。他的团队现在把 Codex 定位为 OpenAI 整个开发者平台的入口，不只是编码。

一年前，当 OpenAI 推出 GPT-5 时，他们需要手动撰写大量指南来教开发者怎么使用新模型的推理能力。现在，他们的策略变了：直接教开发者用 Codex 加上对应的 Skill（技能插件）来完成集成。不管你是要接 Imagen（图像生成）、Sora（视频生成）还是 Speech-to-Speech（语音对话），Codex 都可以是起点。

他还提到一个例子：一个朋友用 Codex 的 Linear Skill 把一堆产品想法自动写成 Linear 任务，然后睡觉前告诉 Codex：“去把这些任务全部实现。”第二天早上醒来，全部完成了。

社区建设方面，他们已经在多个城市和国家建立了 Codex 大使网络，由本地开发者自发组织活动和教学。Alex 补充说，Codex 团队最好的部分就是这个社区。因为开源，团队变得对外非常透明，社区也以积极参与来回报。

## Peter Steinberger：从“永远不用”到主力工具

谈到 Peter Steinberger 加入 OpenAI，Alex 分享了一个故事。2025 年 10 月，他和 Peter 在旧金山的 Fort Mason 散步。他没有直接说团队在考虑做一个独立 app，但开始试探性地聊“某种让委派变得自然的新界面”。Peter 当时的反应是：他永远不会用这种东西。最近，Peter 在推特上发帖说这个 app“还不错”。

> Peter Steinberger 是奥地利开发者，OpenClaw（原名 Clawdbot、Moltbot）的创建者。OpenClaw 是一个开源个人 AI 助手，可以自主操作应用、浏览器和日历等。Steinberger 于 2026 年 2 月加入 OpenAI，负责推动“下一代个人 Agent”的开发。OpenClaw 项目转移到一个独立基金会，保持开源。

Romain 补充了一个更深层的观察。Peter 在 2025 年全年构建了超过 40 个开源项目，每一个都围绕同一个愿景：为日常工具（日历、推特、Gmail）构建命令行接口。这些项目看起来零散，但其实共同指向了一个方向：让编码 Agent 不只是写代码，而是成为操控一切数字工具的通用个人 Agent。

Alex 对 Peter 在 OpenAI 的具体工作没有透露太多，只说他正在帮助构建“下一代个人 Agent，整合到 ChatGPT 中”。

## PM 不是领导岗位，是填空岗位

这是全场最有争议的部分。Peter Yang 直接问：我们还需要 PM 吗？

Romain 先回答，给出了一个更温和的框架：所有角色的边界都在模糊化。工程师、设计师、PM 之间的传统分工正在失去意义。设计师能写代码了，PM 能做原型了，工程师能直接和用户对话了。

Alex 更直接。

> 我其实不认为 PM 是一个好的领导岗位。我觉得它是一个填补空缺的岗位。
> （“I don't actually view PM as a good leadership position. I view it as a fill-in-the-gaps position.”）

他承认自己可能在某个地方说过“一个创业公司如果在 20 个工程师以下就有 PM，那是红旗信号”。

他的推理链条是这样的：AI 工具让每个人都能做一部分别人的工作。工程师以前没时间做任务分类和项目管理，是因为他们需要集中精力写代码。现在写代码这件事可以委派给 Agent 了，工程师有了更多时间。Scott Belsky（Adobe 首席战略官）提出的“人才栈压缩”（collapsing the talent stack）正在发生。

> 做任何事情所需的人越少，那件事就做得越好。每个决策都更纯粹。
> （“I think the fewer people you need in a room to do anything, just the better that thing goes. The more pure every decision is.”）

> Scott Belsky 是 Adobe 首席战略官兼设计与新兴产品副总裁，也是 Behance 创始人。“人才栈压缩”是他在 2023 年提出的概念，核心观点是：让一个人覆盖多个角色的职能（比如首席设计师同时做产品决策），比增加协调人员更有效。

但 Alex 随即做了一个细分。他认为有些 PM 应该直接转行：如果你一直想做工程师，只是因为管理能力不错才做了 PM，那现在有了编码 Agent，你可以直接“把自己从 PM 岗位上删掉”，转做工程师。同理，如果你更喜欢设计，那就去做设计。

但如果你真正感兴趣的是花大量时间和用户在一起、理解市场走向，而且你所在的团队足够大，那 PM 可能还有存在的空间。

他最后补了一句：每个问题都需要一个负责的人，但这个人不一定得是 PM。

Romain 提供了一个对照：Stripe 在没有任何 AI 工具的情况下做到了 250 名员工零 PM。原因很简单，他们全都是工程师，他们在构建自己一直想要的那种 API，每个人都知道一个优雅的 API 长什么样。

这个例子说明了一个前提条件：PM 需求的大小和你离用户的距离有关。如果你就是自己产品的用户，PM 的价值就会下降。Codex 团队恰好处在这个位置。

## “给我看你做了什么”

最后一个话题是招聘。Alex 的标准可以用一个词概括：能动性（agency）。

他描述了 Codex 团队的入职体验：没有递增难度的任务列表，就是一句“欢迎”，然后自己找事做。他要的是那种会主动发现问题、不介意推翻现有决策、愿意接手任何未知领域的人。

看求职信息时，他优先看对方发来的链接和想法。如果有人写了一堆自我介绍和简历，他大概率不会读完。他说他完全不知道团队成员是什么学校毕业的。

> 我很高兴我们生活在一个那些愚蠢的证书不再重要的世界里。管它什么学校呢。给我看你做了什么。
> （“I'm so glad we live in a world where all these stupid credentials don't matter anymore. Who cares? Show me what you built.”）

Romain 补充了开发者体验团队的招聘标准：技术强、工具熟练、同时热爱和开发者社区在一起、喜欢教别人。他提到他们刚宣布 Thomas（Codex Monitor 开源项目的创建者）将加入他的团队。

> Thomas 即 Thomas Ricouard（@Dimillian），知名开源开发者，构建了 Codex Monitor，一个用 Codex 为 Codex 开发的开源监控应用。Romain 在推特上确认了这一加入。

Alex 用一句话总结了 DevX 团队的岗位描述：“很会写代码，同时很会用推特。”Romain 笑着加了一个限定条件：在欧洲和其他地区，开发者可能更活跃在 LinkedIn 或其他平台上，所以更准确的说法是“在社交媒体上表现出色”。

## 写在最后

这次访谈最有价值的信息不是 Codex 的产品功能，而是它暴露的一个结构性前提：Codex 团队的极简管理方式，几乎不写 spec、50 人团队一个 PM、海盗船式运作，建立在一个特殊条件上。Alex 和 Romain 都明确承认了这一点：他们是自己产品的用户，他们的用户也是开发者，他们有一个极度活跃的开源社区提供持续反馈。Romain 举的 Stripe 例子同样如此。

当 Codex 的野心是“把编码 Agent 带给 ChatGPT 的 9 亿用户”时，这套方法还能继续有效吗？Alex 自己也提到，当产品面向不熟悉的用户群体时，可能需要更多 PM 的工作。但他随即用“PM 只是一个标签”把这个问题化解了。

另一个值得持续关注的张力是 Codex 向通用 Agent 方向的演变。Alex 提到 OpenAI 内部非技术团队已经在用 Codex App 做非编码工作，Romain 把 Codex 定位为“所有开发者平台的入口”。2026 年 4 月的报道显示，OpenAI 正在将 Codex 作为统一桌面“超级应用”的基础，整合 ChatGPT 和 Atlas 浏览器。当一个编码 Agent 产品的用户从“写代码的人”扩展到“所有人”，产品决策的复杂度会发生质变。“让离金属最近的人做决策”的原则在那个世界里还适用吗？

Alex 说他最看重兴趣和能动性。这两个品质在 AI 时代确实变得更重要了。但“PM 是填空岗位”这个判断，可能本身就是一个只有在特定条件下成立的结论，而 Codex 团队恰好处在让这个结论看起来最正确的那个位置上。

原始视频：https://www.youtube.com/watch?v=9qXc-THAvc0

## Q&A

问：Codex 团队用什么方式代替产品规格文档？
答：让工程师直接在代码层面做决策，用 Codex 的 plan mode 和模型对话来探索方案，只有涉及多人协调的复杂问题才写极简文档。

问：OpenAI 内部怎么做产品规划？
答：8 周以内的具体冲刺目标，加上一年以上的方向性判断（“vibes”），中间不做路线图。

问：PM 还有存在的必要吗？
答：Alex 认为取决于你的团队是否是自己产品的用户。如果是，PM 的传统职能可以被工程师和设计师吸收。如果不是，可能还需要有人专门投入时间去理解用户。但那个人不一定要叫 PM。

问：Codex 团队怎么招人？
答：看作品不看简历，看能动性不看资历。入职没有递增难度的任务列表，就是“欢迎，自己找事做”。

问：Peter Steinberger 在 OpenAI 做什么？
答：帮助构建下一代个人 Agent 产品，将其整合到 ChatGPT 中。具体细节尚未公开。

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme