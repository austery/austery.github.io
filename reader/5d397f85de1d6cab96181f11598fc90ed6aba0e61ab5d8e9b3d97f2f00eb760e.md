---
author: AI Engineer
date: '2026-05-04'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2TLXsxkz0zI
speaker: AI Engineer
tags:
  - ralph-loop
  - agentic-workflow
  - software-development-automation
  - claude-code
  - theory-of-constraints
title: Ralph Loops：构建简单、迭代且自动化的 AI 交付闭环
summary: Chris Parsons 深入探讨了 Ralph Loops 的核心理念：通过简单的迭代循环而非复杂的编排工作流来释放 AI 的生产力。文章涵盖了从基础的重复提示词到复杂的任务队列自动化、代理团队协作、安全性沙箱以及如何识别系统瓶颈等进阶课题，旨在重新定义 AI 时代的软件工程模式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Chris Parsons
companies_orgs:
  - Anthropic
  - OpenAI
products_models:
  - Claude Code
  - Claude Opus
  - GPT-5
  - n8n
  - Cursor
media_books:
  - The Goal
status: evergreen
---
### 范式转移：从脆弱的复杂工作流走向简洁的 AI 技能循环

Chris Parsons 作为一名拥有 30 年经验的 CTO 和创业者，分享了他对 AI 自动化认知演进的过程。在早期，他倾向于使用如 **n8n** 这样的低代码编排工具来构建复杂的 **端到端工作流**（End-to-End Workflow: 涵盖数据读取、总结、发布等多个环节的线性链条）。然而，这类系统极其脆弱且难以维护，往往在关键时刻因 API 或数据变动而崩溃。

随着 **Claude Code** 等工具的出现，他意识到未来的自动化不再是死板的编排，而是 **基于技能的循环**（Skill-based Loops）。他将曾经复杂的 n8n 逻辑直接转化为 Claude Code 的指令集，让 AI 根据目标自主决策下一步。这种转变的核心在于：不再试图控制每一个细节，而是给 AI 提供环境、工具和反馈。

<details>
<summary>Original English Source</summary>

Welcome. So, this workshop is on Ralph loops. Uh, hands up here who knows what a Ralph loop is. That's almost everyone... What we're going to do today... we're actually going to build Ralph Loops together... Hopefully the idea is that you'll be able to use this on your real work when we get done. 

Who is using Claude code or codeex specifically to write code? Hands up... Who is no longer writing any code? That's quite a lot of people. Look around for a minute. That that is a huge change... My name is Chris Parsons. Um, these days I spend most of my time trying to help, uh, teams... figure out what on earth to do with AI mostly. So, uh, I'm a CTO by background... I have about 30 years or so of building software professionally... and funnily enough all of those uh principles and practices that we taught for years [Agile]... are still very much applicable um to AI.

This is how I used to work with AI until quite recently... This is an n8n workflow uh that I used in order to create my weekly newsletter. It took me uh probably a week to write let alone actually test and debug... it was so brittle to use at this kind of level of complexity... And I thought that this was the future of automation, but it isn't really the future of automation. The future of automation is a lot more like something like this uh running in Claude code... I have now in Claude code a skill that writes newsletters for me and it has all of those instructions. In fact, I copied and pasted the n8n JSON code from there into Claude code and said, "Write a skill based on this flow, and it did a great job."

</details>

### Ralph Loop 的起源：迭代式自我修正的力量

**Ralph Loop** 的概念最早由 Jeffrey Huntley 提出，名字来源于《辛普森一家》中的角色 Ralph Wiggum，寓意是“不断尝试同一件事直到成功”。在 AI 语境下，这是一种极简而强大的范式：当你让 AI 完成一项任务后，不论结果如何，紧接着再次输入相同的指令。

这种做法在早期模型中尤为有效，因为 AI 往往在第一轮输出时会遗漏细节。通过 **递归式提示**（Recursive Prompting: 重复同一指令以触发 AI 的自我审查机制），AI 会在第二轮或第三轮中意识到代码中的缺失或逻辑漏洞，从而实现自动补全。在现代的高级模型（如 **Claude Sonnet 4.6** 或 **GPT-5** 级别）中，模型本身的完整性已大幅提升，但循环的理念已演变为更高级的形式：不再只是重复指令，而是让 AI 在循环中不断扫描任务队列、执行变更并自我验证。

<details>
<summary>Original English Source</summary>

Ralph loops Fundamentally is running on a loop, isn't it? It just reads the skill, calls a tool, goes back to the beginning, reads the skill again... at some point it figures out that it's done and it stops... The first idea came from Jeffrey Huntley uh a little while ago... ancient times in AI which means probably about last June and he said basically what we should do is whenever we finish using an AI to do anything we should just try the thing again... give it exactly the same prompt and see what happens... 

It's called a Ralph loop because of Ralph Wigum, which is a Simpsons character who basically says um the uh he just tries the same thing over and over and over again and eventually it works... All that a Ralph loop is is uh build this thing or do this thing inside a prompt. Then the AI goes away and does the thing... and then you give it another prompt again say go away and build the feature... oh yeah there was actually this tiny thing that I should have done I really am now finished and so on and so on... Where you just build the feature and just then ask it to build the feature and then you ask it to build the feature.

</details>

### 任务驱动的自动化：将循环引入积压工作管理

当 Ralph Loop 被应用到 **任务积压队列**（Backlog: 待处理的任务清单）时，其威力会呈指数级增长。Chris 演示了如何通过简单的本地文件（如 `doc/tickets`）构建一套自动化系统。他不再手动指定依赖关系或优先级，而是直接告诉 AI：“根据 **测试驱动开发**（TDD: Test-Driven Development）原则，从 tickets 文件夹中选择下一个最重要的任务进行实现，完成后提交代码。”

AI 展现出了惊人的自主性：它能够读取所有 Ticket，分析当前代码库状态，识别出下一步的最佳行动，并自动编写测试用例来验证实现。这种 **动态依赖解析**（Dynamic Dependency Resolution: AI 在运行过程中实时判断任务间的依赖关系）规避了人类在进行大项目规划时常犯的“瀑布式”错误。只要环境提供足够的反馈（如测试结果、编译报错），AI 就能在循环中不知疲倦地处理掉整个积压队列。

<details>
<summary>Original English Source</summary>

The really interesting thing is not how do I make sure Claude has finished this one thing. It's what happens if I point this kind of loop at a whole pile of things to do, right? What happens when we point at a whole list of things?... what I'd done effectively was recreate the waterfall processes... where the entire project was specified up front... No wonder it didn't work. If humans can't do that, how is AI supposed to do any better? 

However, if instead of saying with all of your tickets... you can just run a loop where you say something like, "Hey, just pick the next most important ticket." It's as simple as that... the AI is quite capable of looking at all of them, figuring out the dependencies on the fly based on what's just been done... let's forget parallelism just for a minute and just start with a loop... If I go back to Claude... and say implement the next most important ticket using uh TDD principles from doc tickets. um commit when done.

</details>

### 进阶架构：从单线程循环到代理团队协作

为了进一步提升交付能力，Chris 引入了更复杂的循环机制，例如 **agent-teams**（代理团队：多个 AI 协作执行任务）。在这种模式下，AI 不再是一个孤立的执行者，而是可以调用 **子代理**（Sub-agents）来执行特定任务，如专门的验证代理或评审代理。

他分享了一个极具野心的实验——“Startup”技能。这套系统的目标是引导 AI 跑通整个创业框架：从寻找市场痛点、撰写投资备忘录到自动化开发。虽然目前仍处于实验阶段，但它揭示了一个未来方向：**嵌套式循环**（Nested Loops）。一个大的外部循环监控业务目标，内部循环不断执行具体任务。此外，通过 **Loop 指令**（如 `loop every 1 minute`），AI 可以变成一个 7x24 小时在线的数字化员工，持续监控 Bug 报告或日历变更。

<details>
<summary>Original English Source</summary>

I can just simply go into Claude and say implement the next most important ticket... now the interesting thing now is that once this is finishes, now it's using TDD, so it read the test first... You could have a loop that does something like this: loop every one hour check linear for new bug reports from test... I have a skill that I'm working on... which is called startup... the idea is that it should um basically guide a product through an entire startup framework... it is meant to be run as a loop.

The reason for showing that is more to kind of point out that that AI can do a heck of a lot... I have a morning loop where every morning at at 6:00 a.m. it comes up with a full briefing of my day... I have a worker loop... It's got a decision trail of things that it's done and why it's done them... My basic rule is: is this reversible without embarrassment to me? And um if the answer is no, don't do it.

</details>

### 安全、瓶颈与人类价值的再定位

在将权限交给 AI 循环时，**安全性沙箱**（Sandboxing）至关重要。Chris 强调了 **致命三要素**（Lethal Trifecta: 不受信任的 Token、互联网访问、核心机密数据）。他建议在隔离的 VPS 或 **Docker Sandbox** 环境中运行 AI，且严格遵循“可逆性原则”——凡是不可逆或可能造成尴尬的操作（如发送正式邮件、发布到生产环境），AI 仅能生成草稿，由人类做最后审计。

最后，Chris 引用了 **约束理论**（Theory of Constraints）来警示：AI 的加入会将系统的瓶颈从“编码速度”转移到“评审与发布”。如果一个团队每秒产出 200 个 PR 但每月只发布一次，AI 的加入反而会拖慢进度。真正的转型需要领导者为这些“混乱的实验”提供 **空中遮蔽**（Air Cover: 容许失败的保护性环境），并在不断的 **回顾会议**（Retrospectives）中，人类需要思考一个存在主义命题：当 AI 能够处理掉所有的“垃圾工作”时，我们真正想做、且唯一能做好的那部分核心价值是什么？

<details>
<summary>Original English Source</summary>

There's a thing called the lethal trifecta... Simon Wilson coined it. um an idea that if you have untrusted tokens, uh internet access and access to secret important data you don't want to lose, you're going to lose that data... I use a combination of uh positioning the code physically away from the machine on a VPS... I use Claude permissions... Use sub agents here now for the validation step, it started finding things... 

I'm always a bottleneck. I have 30 different things that I need to now review... The only reason that it's given it to me is because I can't trust the AI with it... Within any team in any system there is always a bottleneck... This is why some teams when using AI tools actually go slower... because they're not working on the constraint... Always fix the thing that is the biggest bottleneck first... If you want to transform your team, you are going to have to sponsor these kind of experiments and be okay with failure... give um your team space to try a whole bunch of different things. So give them air cover.

</details>