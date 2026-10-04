---
layout: post.njk
source: https://baoyu.io/blog/2026-04-17/claude-design
speaker: baoyu.io
title: 设计圈的 Claude Code 时刻来了 | 宝玉的分享
date: '2026-04-17'
summary: 本文介绍了 Anthropic 推出的 Claude Design，它标志着设计领域的范式转变，能从文本描述生成可交互的高保真原型，并输出可运行代码。这极大地提升了设计师的生产力，为产品经理等角色提供了新能力，并对 Figma 等传统设计工具构成重大挑战。
area: tech-engineering
category: ai-application
tags:
  - claude-design
  - generative-ai
  - ux-ui-design
  - design-workflow
  - ai-in-design
people:
  - 宝玉
  - Ryan Mather
  - flypig
companies_orgs:
  - Anthropic
  - Figma
  - Adobe
  - Canva
  - Datadog
products_models:
  - Claude Design
  - Claude Code
  - Claude Opus 4.7
  - React
  - Mac App
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-04-17

# 设计圈的 Claude Code 时刻来了

作者：

宝玉

Anthropic 今天发布了 Claude Design，第一时间体验了一下，震惊程度不亚于当年第一次用 Claude Code 写代码。借用 flypig 老师一句话：

> 刚才用了一下，这么说：Claude Design 让 Google 那个 Stitch 看起来像个笑话。

这就是设计领域的 Claude Code 时刻。 我不会说“设计已死”、“设计师要被替代了”之类哗众取宠的话，只是想说：

> 从想法到高保真交互原型的差距已基本消失，非设计师终于能独立产出可交付设计；设计师生产力指数级提升，但设计外包和传统设计工具要大幅缩水了。

今天 Figma 股价大跌也侧面印证了这一点。

## 先看我的实测案例

给大家看一个完整案例，这是我大约 3 轮交互做出来的一个设计作品，不是简单的一个静态图片或者网页，里面的链接大部分可以点击交互。

初始提示词很简陋：

> 帮我设计一个 writing agent 的 Mac App
> 支持多 workspace，可以看到 workspace 的文档（markdown、文本文档），可以对文档进行手动编辑，也可以调用 agent 编辑 markdown 文档
> 也可以在聊天对话中创建/编辑文档

主要是我还没想好做成个啥样，期待着它帮我想想，所以说得比较模糊。

然后它给了我一些问题让我选择，有单选有多选，还可以自己输入，或者让它自行决定。

过了一会去看，它给了我 3 个方案让我选择，就像一个专业的设计师，先跟你确认清楚需求，然后给几个不同方向让你挑。

每个结果都不是静态图片或者静态网页，都是可以点击交互的。

看完我觉得方案 2 和方案 3 都不错，但都有问题，需要综合一下。于是给了一些修改意见，还把 Codex 的截图发给它参考，让它把方案 2 和方案 3 综合一下，再结合 Codex 的一些设计。

它很快给了我一个新版本，基本上就是我想要但是描述不清楚的那种。 比如它把 Documents 和 Chat 用一个 Tab 分开，就是我喜欢的设计，比我预想的“一上一下”更好。

整体设计我挺满意，也提不出更好的要求，接下来就是抠细节。文档编辑历史它没实现，我就让它补这块。

提示词很简单：

> 帮我基于当前设计，设计 history 部分，希望用户能更方便的看文档编辑历史，对比差异

很快它就出了一版，但是打开一看，效果不行。

我正准备提示它改，结果发现它自己检测出了布局问题，自己修复了。

修复后的版本就很好看了，没有布局问题，甚至还能方便地选择任意两个版本比较变更。

从左边的消息历史看，它有自动纠错机制。

最终产出物是 React 代码和样式表。

整个过程让我很意外的几件事：它会主动问需求、它会给多方案、它能理解多图混合参考、它能自检自纠、它输出的是可运行代码而不是静态稿。这套协作模式，和之前任何一个设计工具都不一样。

## Claude Design 到底是个什么东西

先说基础信息。Claude Design 是 Anthropic Labs 今天发布的新产品，由 Claude Opus 4.7 驱动，Pro、Max、Team、Enterprise 订阅都能用（Enterprise 默认关，需要管理员开），直接去 claude.ai/design 就能进。

界面很简单：左边聊天，右边画布。 你描述想要什么，它在右边画出来；你用聊天、行内评论、直接编辑、或者它自动生成的调节滑杆去改；改完之后可以导出成 HTML、PDF、PPTX、ZIP，或者送进 Canva 继续编辑，或者直接打包给 Claude Code 去落地成产品代码。

看起来好像就是个 AI 版 Figma？并不是。

Ryan Mather 是 Anthropic 自己设计团队的人，一个人同时负责 7 个产品线。他今天发的推文里面说了一条很关键的话：

> 不要用对待画布工具的方式来用 Claude Design。它是另一种动物，有自己的超能力。老实说它更像 Claude Code，而不是像画布式的设计工具。
> https://x.com/Flomerboy/status/2045162328593670321

这句话是理解 Claude Design 的钥匙。

## 和 Figma、Canva 们的根本不同

过去一年，Figma 加了 AI、Adobe 加了 AI、Canva 也加了 AI。它们的逻辑都是一样的：在以人为主的画布工具上，加一层 AI 插件，帮你画得更快一点、写文案方便一点。

Claude Design 走的是另一条路：AI 是主要的生成者，人是主要的审阅者。整套工具的骨架就是围绕这个假设搭的。

这个区别听起来抽象，落到产品上有几个很具体的差异。

### 输出是可运行代码，不是静态设计稿

我上面那个 Mac App 案例，最终拿到的是 React + CSS，是一个能跑的东西，链接可以点、标签可以切、版本可以 diff。这和“生成一张漂亮的 UI 图”是两个物种。

### 组织级设计系统

你上传代码库、PPT、品牌资料之后，它会抽出颜色、字体、组件、布局规范，后面所有项目都自动套用。Brilliant 的设计师反馈说，以前在别的工具里需要 20 多轮提示才能搞定的复杂交互，在 Claude Design 里 2 轮就搞定，原因就是它已经“认识”你的设计语言。

### 理解你的代码库

不是把代码当截图看，是真的读组件结构、框架模式、文件组织。所以设计师做完之后点一下 handoff，工程师那边拿到的不是“这是一张图你去还原”，而是“这是一组可以直接接到你现有组件库里的实现草案”。

### 会做工具，不只是做设计

官方博客里提到一个能力：你可以让 Claude Design 临时给你生成一个专门的工具，比如一个针对你品牌色盘的拾色器、一个自定义的 spec 生成器、一个小的交互原型测试工具。产出不局限于“设计文件”，而是“任何帮你把问题想清楚的计算产物”。

Datadog 的反馈也有意思：以前需要一周、跨多轮 brief → mockup → review 才能完成的事，现在在一次会议里就能边聊边做出成型原型，甚至让工程师现场参与到设计对话里。

这不像“Figma 提速 30%”那种优化。更像另一种工作方式。

## 能拿来做什么

从官方博客和目前披露的使用场景看，Claude Design 至少能覆盖这几类工作：

产品原型和交互流程。 比如我的 Mac App 案例，或者 5 屏 onboarding 流程、带筛选和详情抽屉的搜索体验、审批工作流队列。这是它最强的一块。

演示文稿。 10 页 Q1 结果 Deck、15 页董事会 roadmap、客户会前材料、全员会 Deck。导出 PPTX 直接可用，也可以送去 Canva 继续编辑。

营销物料。 落地页、社媒图、活动视觉。

内部工具后台。 管理面板、内容审核队列、权限管理界面。这一类过去专门养一个前端岗来做，现在 PM 自己就能出可交付原型。

设计探索。 一次性出 3 到 5 个方向，让你挑。以前这是“我时间不够所以只能做两版给你看”，现在是“我出五版，你挑一版再精修”。

还有官方没重点讲但其实很重要的：视频 demo。Ryan Mather 提到它能直接生成视频形态的演示，不只是静态图。这对产品发布、用户测试、投资人沟通是新的能力位。

一句话概括使用边界：结构清晰、信息块明确、交互逻辑可描述的东西，它都做得不错；模糊情绪导向的纯艺术创作，它不是来抢这个饭碗的。

## 这事不止关于设计

Ryan Mather 一个人服务 7 个产品，这是一个信号。这事放在两个月之前是不可能的。

### 对设计师

生产力会指数级提升，但团队规模大概率会缩。过去一家公司需要 5 个设计师的活儿，现在 1 到 2 个就能做完，而且单人产出反而更多、更好。留下来的人会更值钱，因为他们做的是真正吃判断力的工作：品牌方向、关键插画、命名、战略级决策。剩下 80% 的执行工作，模型接走了。

### 同样的剧本，已经演过了

编程圈是 Claude Code，能用好 AI 的工程师产出翻几倍，跟不上的慢慢被挤出来；分析圈是各种 AI 辅助数据分析，分析师从“写 SQL 的”变成“和 AI 一起提问题的”。每一次轮到新的专业，走的都是同一条轨迹：人均产出飙升，头部的人拿得更多，尾部的人看着机会一点点消失。设计圈刚好走到这个拐点。

### 对 PM、创始人、营销人员

这是一个完全新的能力。以前你有想法，要么画个草图找设计师排队，要么忍着自己做个丑到抑郁的 PPT。现在你描述清楚想法，它给你一个可以直接拿去给工程师、给投资人、给客户的成品。

### 对 Figma、Adobe、Canva

这是警钟，但股价跌 10% 可能只反映了表层冲击。Ryan Mather 那条推里还有一层更深的信号：Anthropic 自己的设计团队已经把 Claude Design 当主力工具用，Figma 只是偶尔才会被提到。如果 Anthropic 的设计师已经不主要用 Figma，别的科技公司凭什么还主要用？再过 2 到 3 个季度，当企业年度预算开始重新整合设计工具开销，老牌工具的续费数字会比股价给出更直接的答案。

### 对公司决策层

有两件事要重新算账。一件是设计岗位的编制。Mather 一个人覆盖 7 个产品线，背后的参照线是原本需要 3 到 5 个设计师的工作量；放到年度预算表里，这个数字很难不被问到。另一件是工具订阅成本。当主力工作能在一个产品里基本完成，那些原本分散在 Figma、Sketch、Notion、Miro、Keynote 上的账号就会被拿出来重新评估。

### 对工程师

这是久违的好消息。设计到工程的交接一直是最痛苦的环节之一：设计师按视觉做，工程师按代码做，中间全靠 Figma 标注和来回 review。现在从 Claude Design 出来的东西本身就带着组件结构和实现草案，落地成本直接降一个量级。

## 其他

Claude Design 目前还是 research preview，有一些现实边界需要清楚：

它还没有审计日志和用量追踪，不支持数据驻留，上传的资产会被持久存储。如果你在一家对合规要求很严的公司，短期内最好不要把最高敏感度的设计素材直接放进去。

它目前只有网页界面，没有开放 API。你想把它嵌到自己产品里，目前还不行，只能基于 Claude API 和 Agent SDK 自建类似能力。但 Claude Design 能力这么强，最关键的是 Opus 4.7 模型在多模态能力上的增强，理论上来说你用 Opus 4.7 也能搭出来类似的产品。

但是和 Claude Code 一样，虽然同样用 Claude 的模型，但是 Claude Code 在很多方面就是能表现更好，毕竟 Anthropic 他们自家才知道怎么最大化的利用好新的模型，以及他们还能反过来，根据用户使用的设计数据和交互，去训练下一代的模型，形成数据飞轮。

这个优势短期内其他家比如 OpenAI 和 Gemini，还无法很快追上。

### 价格与额度

计划类型

官方定位

额度说明

超额方式

明确价格数字

Pro

轻量探索、一次性使用

每 7 天重置的 weekly allowance

可购买 extra usage

allowance 具体数值未说明

Max 5x

PM / 工程师较规律产出 mockup

每 7 天重置

可购买 extra usage

allowance 具体数值未说明

Max 20x

设计师、创意高频使用

每 7 天重置

可购买 extra usage

allowance 具体数值未说明

Team Standard

一次性探索

每个 provisioned user 各自拥有 weekly allowance

管理员可购 extra usage

allowance 具体数值未说明

Team Premium

设计/创意重度用户

每个 provisioned user 各自拥有 weekly allowance

管理员可购 extra usage

allowance 具体数值未说明

Enterprise 传统 seat-based Standard/Premium

PM / 工程师 / 设计重度用户

每用户独享 allowance

管理员可购 extra usage

allowance 具体数值未说明

Enterprise usage-based

走 API 合同计费

不走 seat allowance；按标准 API 费率计

直接计入组织 spend

有一次性 credit，约覆盖 20 个典型 prompts，2026-07-17 到期

这张表基于 Anthropic 官方 Claude Design 定价文档整理；官方没有公开 weekly allowance 的具体数值，所以这些格子必须标记为“未说明”。

我自己是 Claude Max@5x，就设计了一个 App 和生成了一个 Slides，一周的额度就没了。

### 模型、规格与多模态能力

Claude Design 当前唯一明确公开的底层模型是 Claude Opus 4.7。 官方没有说明用户是否可以在 Claude Design 中切换到 Sonnet 或 Haiku，因此这一项应视为未说明 / 大概率固定。与此同时，Anthropic 的模型总览页面给出了当前主力模型的对比，便于理解 Claude Design 选型背后的原因。

模型

Claude API ID

价格

上下文窗口

最大同步输出

视觉/多模态

速度

对 Claude Design 的关系

Opus 4.7

claude-opus-4-7

$5 / 输入 MTok；$25 / 输出 MTok

1M tokens

128k

文本 + 图像输入；高分辨率图像支持

Moderate

Claude Design 已确认采用

Sonnet 4.6

claude-sonnet-4-6

$3 / 输入 MTok；$15 / 输出 MTok

1M tokens

64k

文本 + 图像输入

Fast

可用于类 Claude Design 自建方案

Haiku 4.5

claude-haiku-4-5-20251001

$1 / 输入 MTok；$5 / 输出 MTok

200k tokens

64k

文本 + 图像输入

Fastest

适合轻量、低成本辅助任务

上表数据由 Anthropic 模型总览汇总；其中“Claude Design 采用关系”来自 Claude Design 官方博客。

在视觉规格上，Opus 4.7 是首个支持高分辨率图像的 Claude 模型，最大原生分辨率可达长边 2576 像素，单图最高约 4784 图像 token。这对 Claude Design 尤其重要，因为它大量依赖截图、网页捕获、原型对照和文档视觉语义。与此同时，Opus 4.7 使用新 tokenizer，处理相同文本时 token 可能比 Opus 4.6 高出约 1x–1.35x，这意味着在图像/代码/长上下文场景里，开发者必须重新估算 max_tokens、缓存与成本。

## 最后

Claude Design 带来的冲击，不只是设计圈的一次效率升级，更像一场深刻的范式转变。过去，设计师们习惯于在画布上精雕细琢、手动标注；现在，AI 已经可以直接从想法到可运行的高保真交互原型，让设计师的角色从纯粹的执行者向战略性的决策者转变。这种变化不只发生在设计领域，程序员、分析师、营销人员、产品经理，都已经或者即将经历类似的革命。

在这样一个时代里，真正被重新定义的不仅是我们的工作方式，还有我们对生产力和创造力的理解。AI 不会取代人类对美的判断、对品牌的洞察、对战略的规划，但它的到来却让每个人都有机会更加专注于这些最具价值的能力。

也许几年后，我们会回头看今天的 Claude Design，就像今天我们看待第一次使用 Claude Code 那样，发现历史的分水岭就在不经意间发生了——而我们刚刚走进了那个全新的未来。

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme