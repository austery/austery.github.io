---
layout: post.njk
source: https://baoyu.io/blog/coding-agent-em-shift
speaker: baoyu.io
title: 从 TL 到 EM：我终于不再盯着 AI 写代码了 | 宝玉的分享
date: '2026-07-29'
summary: 文章探讨了从技术负责人（TL）到工程经理（EM）的角色转变对使用 AI 辅助编程的影响。作者分享了如何通过信任 AI 的代码生成能力，将工作重心从代码层面的细致审查转移到全局的项目决策和结果验收上，从而极大地释放了 Agent 的生产力，并展示了在技术选型上的思维方式转变。
area: tech-engineering
category: ai-application
tags:
  - role-shift
  - agentic-workflow
  - technical-selection
  - code-review
people: []
companies_orgs: []
products_models:
  - Coding Agent
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-07-29

# 从 TL 到 EM：我终于不再盯着 AI 写代码了

作者：

宝玉

今年以来，我在使用 Coding Agent 方面有一个很大的变化，就是从 TL（Tech Lead）的角色变成了 EM（Engineering Manager）的角色。

这两个角色主要差别在技术参与深度多少。

## 以前：AI 写代码，我必须盯到代码层

之前我更像一个 TL，虽然不是说事必躬亲，但是系统设计、代码审查什么的肯定是少不了的，说到底还是对 AI 写的代码不放心。

这样虽然质量更有保障，但是人会成为 Agent 的瓶颈，很多事情需要人去决策，细节需要人去掌握。

## 转折点：Fable 5 之后，我开始相信结果

转折点在 Fable 5 前后，我发现 AI 写的代码质量已经相当可以了，只要稍加验证就不会有太大偏离，所以我越来越少的去干预 AI 写代码，而是会更站在全局去看一个项目：

决定项目怎么做，去验收好结果。

这极大的释放了 Agent 的生产力，大部分时候我想好要做什么功能，先和 Agent 一起做一个技术方案，然后确认方案没问题后，用 /goal 加上方案，让 Agent 去执行，写代码和自动化测试，等做好再去验收下功能，代码不怎么细看。

有 Bug 了就是把 Bug 描述给 Agent 让它自己去重现解决，并且让 Agent 补上相关测试覆盖，修复了后人再去验证一下。

## 技术选型，也终于不再围着自己的技能树转

这样还有一个好处，就是在技术选型时，不会局限于你自己的喜好和擅长。

当你是 TL 的角色是，还是会有点过度关注技术实现，包括技术选型会偏向你自己熟悉的喜欢的，而不一定是最适合的。

当你是 EM 的角色做技术选型，就不再关注自己擅长什么，而是什么技术最适合项目。

我因为前端熟悉，所以最开始开发字幕翻译 App 时，就优先考虑 Electron 这样的技术栈，因为自己熟悉，有问题能解决也能写的出来。

后来发现 Electron 性能很难满意，就换成了 Swift + AppKit 原生技术栈，本来我 Swift 是不熟悉的，但有 AI 辅助，整个过程毫无压力。

现在在设计 BaoCut 下一个大版本的时候，要考虑跨平台方案，首选是 Rust，哪怕我从来没写过一行 Rust 代码，但我知道这是一个很好的跨平台选择。

目前基于 Rust 的第一个版本已经写完了，整个过程几乎没有任何语言上的障碍。

## 真正的瓶颈，从写代码变成了想清楚

通过这样的模式我在开发 BaoCut 的时候，基本上可以每天一个小版本迭代。https://baocut.app/releases/

这两天速度慢下来了，是因为需要构思新的大版本，这时候人就又成了瓶颈了：如果人没想清楚该做什么，Agent 再厉害也帮不上。

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme