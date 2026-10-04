---
layout: post.njk
source: https://baoyu.io/blog/2026-02-25/coding-agent-sweet-spot
speaker: baoyu.io
title: Coding Agent 有个甜蜜点，多数人直接跳过了 | 宝玉的分享
date: '2026-02-25'
summary: 本文通过 Simon Willison 和 Cloudflare 的案例，深入探讨了 Coding Agent 的“甜蜜点”。文章总结出四个关键要素：明确的参照物、自动化验证、架构蓝图以及人来把控方向。遵循这些原则能极大提升 AI 编程的效率和质量。
area: tech-engineering
category: ai-application
tags:
  - coding-agents
  - ai-assisted-development
  - developer-workflow
  - prompt-engineering
people:
  - Simon Willison
  - 宝玉
companies_orgs:
  - Cloudflare
products_models:
  - Codex CLI
  - GPT-5.2
  - JustHTML
  - vinext
  - html5lib-tests
  - Vite
  - Next.js
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-02-25

# Coding Agent 有个甜蜜点，多数人直接跳过了

作者：

宝玉

有两个 Vibe Coding 项目让我印象很深。

一个是 Simon Willison（Django 框架的联合创始人），他一边陪家人装饰圣诞树、看电影，一边用 Codex CLI + GPT-5.2，把 Emil Stenström 的 JustHTML（一个纯 Python 的 HTML 解析库）迁移成了纯 JS、零依赖的版本，跑过了 9200 多个 html5lib-tests 用例，产出大约 9000 行代码、43 次提交。整个过程他自己只发了 8 条左右的提示词。

> 《I ported JustHTML from Python to JavaScript with Codex CLI and GPT-5.2 in 4.5 hours》https://simonwillison.net/2025/Dec/15/porting-justhtml/

另一个是 Cloudflare，一个工程经理带着 AI，用不到一周时间，在 Vite 上重新实现了 Next.js 的 API，做出了 vinext 这个项目。1700 多个单元测试、380 个端到端测试、覆盖 Next.js 94% 的 API，已经有客户跑在生产环境了。总花费大约 1100 美元的 Token。

> 《How we rebuilt Next.js with AI in one week》https://blog.cloudflare.com/vinext/

这两个项目的规模和复杂度都不低，但 Coding Agent 的完成质量出奇地好。为什么？

因为它们都精准命中了 Coding Agent 的舒适区——或者说甜蜜点。

## 有明确的参照物：让 Agent“翻译”而不是“创造”

大语言模型最擅长的事情之一是“翻译”，无论是自然语言还是编程语言。给它一个明确的参照物，它能做到又快又好。

Simon 的项目就是典型的翻译型任务。已经有一个写好的 Python 版 HTML 解析库，API 设计是现成的，代码逻辑是现成的，Agent 要做的就是把这些“翻译”成 JavaScript。不需要凭空设计架构，不需要做产品决策，照着画就行。

Cloudflare 的 vinext 项目看起来更复杂，但底层逻辑一样。Next.js 的 API 是公开的、文档极其完善，Stack Overflow 上积累了海量问答，这些内容早就进了大模型的训练数据。Cloudflare 团队不是让 AI 发明一个新框架，而是让它照着 Next.js 的规格说明书，在 Vite 上重新实现一遍。

第一个条件：给 Agent 一个明确的参照物。 不管是一个已有的开源项目、一份 API 文档、还是你之前写过的旧版本代码，都可以当参照物。让 Agent 做翻译而不是创造，成功率会高很多。

在你自己的工作中，动手之前先问一句：有没有现成的东西可以参考？一个开源实现、一段竞品代码、甚至一份伪代码，都能让 Agent 的表现跨一个台阶。

## 有自动化验证：让 Agent 能自己验证对不对

Coding Agent 和人类程序员一样，写完代码需要验证。区别在于：如果验证必须靠人工，效率就会断崖式下降；但如果 Agent 能自己跑测试、自己看结果、自己修 bug，它就能进入一个高速循环，不知疲倦地迭代下去。

Simon 的项目能成功，很大程度上因为 HTML5 标准有一套叫 html5lib-tests 的测试集，9200 多个用例，输入是 HTML，输出是正确的解析结构。Agent 不需要你告诉它哪里写错了，它跑一遍测试就知道。Simon 把 GitHub Actions 配好之后，Agent 就进入了这个循环，用了 140 多万个 Token，提交了 43 次，直到所有测试亮绿灯。

Simon 把这个过程叫做 “设计智能体闭环”（Designing the Agentic Loop），他认为这是释放 AI 编程潜力的关键技能。

Cloudflare 那边也一样。Next.js 仓库里有几千个端到端测试，团队直接把这些测试搬过来当验收标准。工作流程就是：定义任务，让 AI 写代码和测试，跑测试，过了就合并，没过就把报错扔回给 AI 让它改。几乎全自动的反馈闭环。

你可能会说：我的项目哪有这么完美的测试套件。确实，大多数项目没有。但你可以往这个方向靠：

先写测试再让 Agent 写实现（测试驱动开发和 Agent 是天然搭配）

配好 Lint 和类型检查

给它接上浏览器开发工具让它能看到运行结果

哪怕只是让 Agent 能自动跑一个 npm test，都比你自己肉眼审代码强得多

给 Agent 的自动验证工具越多，它能自我修复的能力就越强。

## 有架构蓝图：让 Agent”填空”而不是”作文”

Agent 受上下文窗口的限制，一次任务能处理的信息量是有上限的。你把一个复杂项目的整个代码库扔给它，它消化不了。你让它从头到尾一口气做完一个大功能，它做到后面就忘了前面。

所以架构设计特别重要。把大任务按架构拆成小任务，每个任务刚好在 Agent 的上下文窗口内能完成，这是高手和新手使用 Agent 最大的区别之一。

Simon 的做法很聪明。他的第一条提示词不是让 AI 写代码，而是让它读完 Python 项目后写一份 JavaScript 版本的设计文档（spec.md）。这份文档包含了 API 设计、实现步骤和验收标准。然后他让 Agent 从最简单的冒烟测试开始，一步步按计划推进。架构是现成的（参照 Python 版），路线图也规划好了，Agent 只需要按部就班地“填空”。

Cloudflare 团队的做法更系统。工程经理先花了几个小时和 Claude 反复讨论架构方案，定好整体蓝图，然后按模块拆任务。每个任务的边界清晰，AI 写完一个模块就能独立测试，不用等整个项目做完才能验证。

你不需要是架构大师才能做这件事。哪怕是花 10 到 30 分钟和 AI 聊一下你打算怎么做，让它帮你列个实现计划，再按计划分步执行，效果都会好很多。先设计再实现，这个道理对人类程序员适用，对 Agent 同样适用，甚至更适用。

## 有人把控方向：Agent 执行，人来决策

Cloudflare 的博客里有一句话：

> 给 AI 好的方向、好的上下文、好的护栏，它就能高产；但方向盘必须在人手里。

AI 有一个让人头疼的特点：它经常写出看起来完全正确、但实际行为不对的代码。语法没问题，逻辑看着也通顺，跑起来就是不对。识别这种“高置信度的错误”，目前还是需要人来做。

Simon 让 Agent“commit and push often”（频繁提交代码），这样他在手机上刷 GitHub 提交记录就能追踪进度。Cloudflare 团队把代码审查也交给了 AI Agent，但架构决策、优先级判断、识别 AI 走偏了，这些仍然由人来把控。

这两个项目的操作者都不是新手。Simon 是 Django 的联合创始人，Cloudflare 那位是工程经理。他们知道怎么把一个大问题拆成 AI 能消化的小问题，知道什么时候该介入，什么时候该放手。

你不需要是他们那样的高手，不需要盯着 Agent 写的每一行代码，但也需要在关键节点检查方向对不对。给 Agent 一个太大的任务然后自己走开，通常不会有好结果。小步快跑、阶段性验收，是目前最靠谱的协作方式。

这四个条件不是什么高深的理论，回头看都是常识：有参考、能自测、有规划、有人管。但正是因为它们太像常识，很多人在使用 Agent 时直接跳过了。

Cloudflare 团队自己说，几个月前这事还做不了，不完全是因为模型变强了多少，而是他们找到了正确的方法。

既然知道了 Coding Agent 的舒适区在哪，就可以有意识地把自己的项目往这个方向靠：

先看看有没有参考项目/代码再动手。 别急着让 Agent 从零开始写。看看有没有类似的开源实现、有没有现成的 API 规范、有没有可以参考的代码库。给 Agent 一个参照物，比给它一段需求描述有效得多。

给 Agent 配上自动验证的能力。 手动测试是 Agent 效率的最大瓶颈。尽量把验证环节自动化：单元测试、集成测试、Lint、类型检查，甚至浏览器自动化测试。让 Agent 能自己跑、自己看结果、自己改。Cloudflare 用了 agent-browser 来验证浏览器端的渲染和交互，这种思路很值得借鉴。

先设计后实现。 在让 Agent 动手之前，先把架构想清楚、任务拆好。每个任务的范围要小到 Agent 的上下文窗口能装下，大到足够产出一个有意义的模块。这个拆分能力本身就是高手和新手的分水岭。

建立反馈闭环。 Simon 的做法很典型：配好 CI，每次提交自动跑测试。Agent 写代码、提交、CI 报错、Agent 读日志、修复、再提交。人只需要在关键节点介入。这个闭环跑起来之后，Agent 的产出效率会远超你坐在那里一行行审代码。

知道什么时候 Agent 不行。 不是所有项目都在舒适区里。没有明确规范的探索性项目、需要大量领域知识的业务逻辑、涉及复杂人际沟通的需求梳理，这些 Agent 做不好。识别边界和利用优势同样重要。

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme