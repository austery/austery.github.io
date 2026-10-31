---
layout: post.njk
source: https://baoyu.io/blog/2026-05-11/skill-next-codex
speaker: baoyu.io
title: Codex 的野心，MCP 和 Skill 的下一步 | 宝玉的分享
date: '2026-05-11'
summary: 本文分析了AI Agent界面布局演变，Codex欲通过插件生态实现全流程闭环编辑的野心，并提出“Agent App Store”模式。此举被视为Agent能力发展的关键，并为中小团队带来机遇。
area: tech-engineering
category: ai-application
tags:
  - ai-agents
  - plugin-ecosystem
  - product-strategy
  - user-interface
people: []
companies_orgs:
  - Codex
  - Cursor
  - Claude Code
  - Cowork
  - OpenAI
products_models:
  - Codex App
  - Cursor 3.0
  - Claude desktop version
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-05-11

# Codex 的野心，MCP 和 Skill 的下一步

作者：

宝玉

这段时间我在密集使用 Codex App、Cursor 等 Agent 应用，有件事越来越觉得有意思。

去年大家争的是谁家模型更强，今年争的好像变成了谁家窗口右侧更好用。

Codex、Claude 桌面版、Cursor 3.0、TRAE SOLO，这几家最顶尖的 Agent，在完全没有协商的情况下，几乎同时收敛到了同一个界面布局：左侧是项目和会话列表，中间是和 Agent 的对话，右侧是工作区，放着文件浏览、网页预览、文件变更审查这些功能。

肯定不是相互之间的抄袭，更像是当前 Agent 交互的最优解。

## 为什么是三栏

传统 Chatbot 只需要两栏，左边会话历史，右边对话窗口，你问它答，用完走人。

到了 Agent 时代，Agent 能自己写代码、改文件、调工具了。它做完之后，你得看看有没有做对——右侧工作区就是为这件事出现的。

但这只是第一阶段。

随着用户越来越多时间是在指挥 Agent，打开 VSCode 这类专业工具的时间自然越来越少。那个问题迟早会冒出来：Agent 帮你写完代码、做完 PPT，你想微调几个字，还要专门切出去打开另一个软件？

没有人愿意这样。用户的自然期待是：能不能直接在 Agent 里改？这也是目前 Codex App 呼声最高的功能之一（另一个呼声高的是手机版，马上要出了）。

于是各家开始悄悄升级右侧工作区，让它从只能看文件编辑记录，变成了一个多功能区。Codex 在 4 月 16 日的大版本更新里，右侧工作区的改动幅度是所有功能里最大的。

交互细节上各家略有差异。Codex 和 Cursor 用 Tab 切换，Claude 用浮动面板。我自己用下来觉得 Codex 最顺手，Claude 的浮动面板方案设计感有余、实用性不足，迟早要改。

## Codex 的真正野心

但如果只把这个变化读成“设计界面进化”，就低估 Codex 了。

Codex 4 月大版本发布时的口号是“Codex for (almost) everything”——几乎任何任务都能做。你可以把它理解成一句广告口号，但更像是一个产品方向的声明。

要兑现这句话，Codex 不能只是个擅长写代码的 Agent，它必须能处理各种文件格式，支持各领域的专业工作流，还要让用户能在它里面完成全程闭环，包括最后的人工微调。

目前 Codex 还做不到最后一步：生成之后无法编辑，代码、Markdown、PPTX 都不行。这可能是产品上有意为之的克制，可能是技术上还没跑通，也可能是在等一个统一的解决方案出现。

我猜是第三种。

## MCP 和 Skill 都只解决了一半

要理解 Codex 在等什么，得先想清楚 Agent 能力拼图里现在差哪一块。

MCP 解决了“连接”问题：Agent 通过统一规范接入各种工具，数据库、日历、代码仓库，都能打通。

Agent Skills 解决了“怎么做”的问题：Agent 学会了它没训练过的领域知识和最佳实践，比如怎么写特定风格的文章，怎么处理某类复杂任务。

这两件事做得都还不错。但有一块缺口始终没补上：用户的二次编辑。

你让 AI 写完一篇文章，最后还是要自己打开编辑器改几处，毕竟很多时候最后那 5% 的精准度，只有自己动手才能到位。就算将来 AI 再聪明，它也做不到百分百的懂你，还是少不了要手动去做修改。

于是最近 Markdown 编辑器又火了，各种 Vibe Coding 出来的 Markdown 产品满天飞。

但 Codex 不会自己做一个 Markdown 编辑器，因为每个人的偏好都不一样，做出来永远有人不满意；更何况它也不可能把每个垂直领域的专业编辑器都集成进来。

最合理的路，是插件机制。

## 下一步：Agent 版 App Store

把 Agent 做成平台，让社区来贡献插件，就像 VSCode 和 Chrome 那样。

Codex 只需要聚焦在 Agent 调度这一层，把文件预览、二次编辑、垂直领域的专业能力都交给插件来扩展。用户按需安装，做设计的装设计插件，写作者装写作插件。

插件机制还能顺手解决一个长期没有答案的问题：Skill 没办法商业化。

我自己的 baoyu-skills 快 2 万 Star 了，但从中赚到的钱是 $0。Skill 这东西几乎是透明的，对 Agent 透明，对人也透明，复刻成本极低，不管你写得再好，护城河都很浅。

插件不一样。App Store 和 Chrome 插件市场已经跑通了一套收费和版权保护机制，把它移植到 Agent 插件市场完全可行。好插件可以收费，开发者才有持续打磨的动力，生态才真正能转起来。

Codex 现在已经有了一个非常原始的插件市场。从这里到成熟的收费插件生态，还有很长的路，但方向是对的。

想做这件事的不止 Codex 一家。Cursor 我能看到类似的影子。唯独 Claude Code 和 Cowork，目前没看到这个方向的产品迹象——也许他们不屑于做，也许只是还没走到这一步。

## 留给中小团队的窗口

如果 Codex 真的跑通了插件生态，对中小团队意味着什么？

除了自己做一个垂直 Agent，还有另一条路：在 Codex 这样的平台上做插件。不用自己搭 Agent 调度层，不用解决 Token 接入，用户分发也靠平台。你只需要专注在那个“最后一公里”——帮用户把 Agent 生成的结果处理好、编辑好、用得顺手。

这个窗口不会开太久。先进去的能拿到冷启动红利，晚进去的只剩存量竞争。

时间点不会太远，也许就在这几个月。

Codex 的野心摆在那里，“几乎任何任务”这个口号要真正兑现，插件机制是绕不过去的一步。如果 OpenAI 在这件事上继续犹豫，那才是真的失误。

你觉得这个插件生态最后会是哪家先跑通？或者说你觉得有更适合 Agent 的产品表现形式？欢迎留言分享！

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme