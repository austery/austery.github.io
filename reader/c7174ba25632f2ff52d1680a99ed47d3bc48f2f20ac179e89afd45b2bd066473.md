---
author: 人民公园说AI
date: '2026-05-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=eHIpMclCtbo
speaker: 人民公园说AI
tags:
  - agentic-workflow
  - multi-modal-learning
  - dev-productivity
  - ecosystem-integration
  - low-code-ai
title: 深度解读Google I/O 2026：Gemini 3.5 Flash与Antigravity 2.0的Agent时代
summary: 本期访谈深度解析了Google I/O 2026大会，重点讨论了Gemini 3.5 Flash模型在智能与执行力间的平衡，以及Antigravity 2.0在Agent开发、多端应用转制和生态整合上的重大突破。访谈强调了Google凭借家底厚实的生态系统和对环境的深度整合，有望在Agent应用开发领域构建起极具竞争力的“一条龙”式开发体验。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google
  - OpenAI
products_models:
  - Gemini 3.5 Flash
  - Gemini Omni
  - Antigravity 2.0
  - Codex
media_books: []
status: evergreen
---
### Google I/O 2026现场印象

**人民公园说AI**: 今天特别感谢抖音、前沿科技和**Google**邀请我们到 Google 2026 I/O 大会的现场。今天我就是在现场给大家做一场直播，有好多体会。闲哥，你讲讲今天听下来最直观的感受，可不可以跟我们分享一下？

**闲哥**: 我觉得就两点。第一点就是财大气粗。我更觉得是说 **Google** 真是家底厚，延续了 2025 年的风格，把整个家底 showcase 一遍，有点像冬天晒被子，把所有家里好东西都拿出来晾一晾。今天什么都聊到，什么 **TPU**、**Antigravity**、多模态等等，这些东西都有。

第二点是关于 coding 这块，大家知道大会之前就很关注 **Gemini** 在 coding 这方面的动作，毕竟其他的“御三家”都很激进。但是我今天的感觉反倒是，在 coding 方面，Google 是把自己多模态这块的优势发挥到极致，这是我最直观的两个感受。

**人民公园说AI**: 我看今天发的这个 **Gemini 3.5 Flash**，能力上据说超过了 3.1 的 Pro，价格更低，且 agent 做事情的能力提升了。有人说这是牺牲了一些主动的智能能力，去换取了更强的 agent 执行能力。这点你在现场看的感觉是什么呢？

**闲哥**: 现场有一个地方确实让我很惊艳，就是 **Mac** 版桌面端的这个 Gemini。当时应该是 **Josh** 的演示，他讲家里两条狗参加活动需要做准备工作，他就是用 Mac 版直接实现的。过程中没做任何作业，直接通过语音输入下达任务，一会功夫就在他的 **Gmail** 里面把东西都安排好了，邮件都已经一发待发。现场坐在我身边的朋友都觉得哇，很惊艳。我自己因为用了桌面端，确实又回归到 Gemini 的使用中了。

### Gemini与Agent入口

**人民公园说AI**: 你讲的这应该是 Gemini 的 **Gemini Spark** 吧，它会在 Chat 旁边单独出一个 Gemini Spark 的 Tab 作为 agent 的入口。我觉得这个应该要连起来看，我看到了这次还发布了 Antigravity 2.0 版本，有人吐槽它又向 **Codex** 致敬了，把 **IDE** 给干掉了。但很多人漏了重要信息，就是 Antigravity 2.0 同时发布了 Antigravity 的 **CLI** 和 **SDK**。

过往 Google 在纠结到底要做一个 AI 编程的 IDE，还是要做成像 Codex 这样子，或者做一个 Gemini CLI，今天就没有这个讨论了。我觉得未来 Gemini 的 Mac 版会跟 Antigravity CLI 结合，Mac 的 Gemini 来理解指令，Antigravity CLI 来执行指令或编程。这一步，Google 可能做得比 **OpenAI** 还要快。

**闲哥**: Codex 已经有 500 万的活跃开发者，从 OpenAI 的角度来讲，Codex 应该是要做主战场。但对谷歌的话，Gemini 的用户基数肯定比 Antigravity 大几个数量级。Antigravity 是收购 **Windsurf** 改的，本来 OpenAI 想收购，被谷歌截胡了。

OpenAI 的路线是 Codex 是关键的救命稻草，如果 Codex 突破不了，故事就垮掉了。但 Google 这边，Gemini 会更像基石，因为 Gemini App 的用户基数和装机率要高很多。我个人的想象中，未来 Gemini 的 Mac 版会跟 Antigravity CLI 结合，本质上还是 Google 把自己所有的服务都 CLI 化了，串成一个通用型的产品给你去用。

### Antigravity的Agent表现

**人民公园说AI**: 刚才提到财大气粗，生态我们聊了很多。关于多模态这块，现场令我印象最深的是新的 **Gemini Omni** 模型，它简直是视频版的 **Nano Banana**。现场展示无论是一致性还是场景切换，如果真的能到演示的地步，无论自媒体创作还是商业盈利，店主都可以自行完成，不再需要技术去拼这些。比如现场提到的韩国女士餐厅案例，非常震撼。

Antigravity 现场演示也很震撼，应该是一个用于 **Doom** 的操作系统，花了九十几个 agent 协作 12 个小时，大概只花了 1,000 美金。如果这笔账是真实的，非常牛逼，以前做 MVP 烧 Token 成本远不止这些。而且现场演示 Doom 的时候，开始键盘出不来，Antigravity 现场写了一个键盘驱动给修好了，这最考验一个 agent-first 平台的理解和执行能力。

**闲哥**: 从外行看热闹角度，有几个点我是听懂了。第一，我可以自己做个 App 了，不仅是做个网页。现场演示说技术上 ready 了。第二，它能把一个已有的 iOS 版本的 App 直接转制成一个 Google Play 上的 App，做成了集成化，这简直是巨大福音，以前做跨平台太复杂了，需要养不同的工程师团队。

### 生态整合与开发效率

**人民公园说AI**: 我觉得整个 Google 的策略还是放在前端偏多，因为它解决一个问题很明确，很多后端大家都用 Codex 或者 **Claude** 去做，但我们还是会需要很多前端来做 iOS。大家别忘了，跨平台的 **Flutter** 就是 Google 的，Antigravity 这次应该是跟 Flutter 整合了。

尤其是前端开发，Antigravity 补课 CLI 和 SDK，再加上本地浏览器跟 Antigravity 做即时的联调，效率完全不一样。这是 agent-first 的 environment 的必备环境。如果没有即时的、本地的、完全联通的环境给到 agent，它是没有办法高效调 UI 的，因为很多东西需要浏览器截图做验证。

**闲哥**: 今天在卷 IDE、编程这些东西，有奶便是娘。今天 Claude 不行了就用 Codex，Codex 不行了又用 Claude。但什么能留住人？我觉得 Google 给我很大启发，还是生态或者一条龙的环境整合。如果我能从 Antigravity 一路到 Google Play 发布，用 Google 的全家桶一整套解决了，我觉得这是一个很顺的流程，利好编程要求没那么高的开发者。Google 还是花了非常多的力气在整合自己的生态，因为生态才能留住人。我真正希望的，是 Google 大善人赶紧回来。