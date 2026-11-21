---
author: How I AI
date: '2026-04-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kCMgUvnpzsM
speaker: How I AI
tags:
  - large-language-models
  - autonomous-agents
  - code-generation
  - data-migration
  - system-integration
title: GPT-5.5：破解复杂工程问题的高端推理模型
summary: 本期演讲深入探讨了OpenAI最新的GPT-5.5和5.5 Pro模型的实际应用。主讲人通过三个真实案例展示了该模型在安全问题修复、百万行数据迁移（6小时自主运行）以及逆向工程专有蓝牙设备等高难度技术工作中的卓越表现，揭示了高端推理能力对复杂问题的突破式改进。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
products_models:
  - GPT-5.5
  - GPT-5.5 Pro
  - Claude Code (Codex)
media_books: []
status: evergreen
---
### 智能优化 vs. 推理深度：重新定义模型价值

GPT-5.5 和 GPT-5.5 Pro 今日正式发布，但仅在 Codex（Claude Code）和 ChatGPT 中可用，API 接口尚未开放。根据 OpenAI 的官方说法，这两个模型具有更强的**复杂工作处理能力**和更高的**token 效率**——本质上是"更聪明、更快"的组合。定价方面，GPT-5.5 的输入 token 价格为每百万 5 美元，输出为 30 美元；而 GPT-5.5 Pro 则分别为 30 美元和 180 美元，确实成本不菲。但对于能够解决前所未有的技术问题的工具，付出"智力税"（Intelligence Tax）是值得的。

衡量 AI 工具价值时，最常见的指标是**速度 ROI**——能否更快完成现有任务。但 GPT-5.5 的真正突破在于**雄心 ROI**：它使我们能够尝试和完成过去根本无法完成的工作。其中，**自主性和上下文保持能力**尤为关键——由于模型更高效、响应更快，工程师可以同时启动多个并行任务，而不会丧失对工作的掌控。这种"烹饪"般的工作流（I am cooking）彻底改变了技术债的处理方式。

<details>
<summary>Original English</summary>

Today OpenAI is releasing GPT-5.5 and GPT-5.5 Pro into Codex and ChatGPT. Not available in the API quite yet. This model has a higher capacity for complex work and is more efficient, including being more token efficient getting that work done. The whole idea with this model is it's smarter and it's more efficient. So you're going to get more done. GPT-5.5 is $5 per million input tokens and $30 for output tokens. And GPT-5.5 Pro is 30 for a million input tokens and $180 for output tokens. This is a pricey one, but when I reflect on what I was able to achieve with this model in early testing, I'm going to pay the intelligence tax because I think what I was able to achieve is really important. Everything has an ROI and there can be an ROI in terms of speed. But where GPT-5.5 really helps me is ambition. It has been able to do things that literally I have not been able to do before for a couple reasons. One, just intelligence higher. The second thing I've experienced is because the efficiency is higher, I'm able to do more faster without losing context of what I'm working on because it's happening really quickly or it's being more autonomous so I don't have to babysit as much.

</details>

---

### 挡板思维与批量修复：安全债的系统化清算

在一个 ChatPRD 代码库中，首先尝试了 OpenAI 的 **Codex 安全产品**来执行威胁评估和安全扫描。结果表明代码库相对安全，但仍存在若干低优先级的问题。关键创新在于处理方式：而不是逐个修复问题，我**将全部问题导出为 CSV，上传到 Codex，要求它进行架构审视、归类相关问题，随后提议并实现修复**。这一方式的效果出乎预料——模型不仅完成了代码修改，而且质量在人工审核和代码评审中都得到了验证。最好的验证来自随后进行的**年度渗透测试**（Penetration Test），结果完全清洁。这表明 GPT-5.5 + Codex 特别擅长处理**技术债清单、安全问题分类、前端债务修复和不稳定测试**等成批量的关联但非单一项目的任务。

<details>
<summary>Original English</summary>

We used OpenAI's Codex security product to run a threat assessment and security scan on the codebase. It did come up with some low priority or low severity issues that we needed to remediate. Instead of taking those one by one, what I did is I downloaded the CSV of those issues, upload it to Codex and just said, can you please architecturally review these issues, group them if they're thematic, and then propose a change and then make those changes. It did it very well. We did human review on that. We did code review on that. And we were just really happy with the quality of execution. The real validation of the quality of that output came when we had very quickly after that our annual penetration test and our pen test came back super clean. If you have a list a triage list of technical debt, if you have a triage list of security issues, even maybe front-end debt, flaky tests, engineers, pay attention, you can throw that list at GPT-5.5 and it will get that list done.

</details>

---

### 百万行数据迁移：六小时自主运行的边界突破

最令人瞩目的案例源自 ChatPRD 的**长期积压数据债**。该系统存储了数百万条聊天记录，但这些记录被保存为各种遗留格式——因为 OpenAI 和 Anthropic 的 API 响应结构在三年间不断演变。这是一个**高度非结构化、充满边界情况（edge cases）的数据迁移问题**：这些 AI 调用可能包含附件、工具调用，也可能不包含，导致难以构建一个清洁、统一的回填和数据规范化方案。过去的做法是"打补丁"——每次修补都会发现新的边界情况，形成恶性循环。

直到决定**将整个问题交给 GPT-5.5 Pro in Codex**。通过提供技术文档和库引用，模型在**单次尝试（one-shot）中就构建了一个覆盖 98% 已知边界情况的解决方案**。随后，为了验证这个迁移，我要求 Codex 创建一套**可扩展的验证系统**：将生产级别的测试数据拉入测试环境，针对每一条记录调用 Anthropic 和 OpenAI API，通过 CLI 工具让任何工程师都能测试。关键指令是："**I trust you**"——让 GPT-5.5 自行决定如何生成子代理（sub-agent）、测试、修复问题。

这个过程运行了**5 小时 57 分钟**——完全自主，零提示、零后续指导。结果是：对 200 万行数据进行了压力测试，仅发现了**1 个遗漏的边界情况**，之后错误率在监控系统中直接跌至地板。这彻底改变了我对 AI 编码质量的看法——相比以前逐个打补丁导致漏洞百出，现在我们拥有了一个能够**自主、持续优化的系统化解决方案**，而且成本（即使 token 费用高昂）也比人工团队花费的时间更低廉。

<details>
<summary>Original English</summary>

We have millions of chats now for ChatPRD and we were storing those chats in various legacy formats as the model providers both OpenAI and Anthropic have changed the shape of their model responses over time. Every model in the world has changed a little bit about how they return data via API. Over the past 3 years, we have a bunch of data debt around that where we were storing legacy formats in our database. These legacy formats because they are AI calls, because they may or may not contain attachments, because they may or may not contain tools, very hard to build a clean cohesive backfill and sanitization of that data into our go forward data model. I have just been slapping fix after fix and patch after patch on this problem because every time we patch it, we find another edge case. I just finally was like you know GPT-5.5 take me away, gave the model that problem and it executed so well, it built functionally one shot a solution that covered 98% of the edge cases. I needed GPT-5.5 and Codex to validate that work. I asked Codex: I need you to make a scalable system for our team to do this programmatically, ideally through a CLI so that any agent can test any thread. I trust you to make a call, figure out how to spawn a sub agent to do this, test it, and identify any issues, repair them, and get this ready for production. This thing worked for 6 hours. It was actually 5 hours and 57 minutes. I did not have to— zero prompts, zero follow-ups, zero steering. It just went for 6 hours. This thing will do long-running autonomous tasks that require a loop to understand if it's doing well and moving things forward. After two million rows we had one edge case that was not caught. We saw our error rate just hit the floor in our monitoring. People say that AI coding is going to decrease quality because people are vi coding. That is just such an 18 months or 12 months ago narrative. I think quality is going to go up. Just being able to hand this to GPT-5.5 and Codex has changed my life.

</details>

---

### 逆向工程的终极考验：Doom Mini2 蓝牙通讯协议破解

这是 GPT-5.5 真正的"**个人高保真智能基准**"（Personal High-Tech Eval）。Doom Mini2 是一个复古风格的蓝牙音箱和微型屏幕设备，虽然附带了官方 iOS 应用，但我的目标是**以编程方式（通过终端）控制它**。这涉及**专有代码、中文文档、蓝牙硬件提供商资料**的深度挖掘。曾尝试用 Claude Code（Opus 版本）和 GPT-4 都失败了。

为了理解通讯协议，我采取了极端措施：**下载 iOS 蓝牙分析工具、使用数据包嗅探器捕获实时通讯，记录 app 发送给设备的确切 bit 流**。这份日志和所有信息被提供给 GPT-5.5，附带绝望但诚恳的提示："*This thing is connected by Bluetooth. Take what you know and please just do anything to figure out how to display on this... I believe in you.*"

结果是——**GPT-5.5 完成了它**。现在我拥有一个命令行工具，可以在终端中运行，实时将图像编码、发送到设备，并在屏幕上显示。更妙的是，该工具已集成到 Codex 的通知系统中——每当 Codex 完成任务时，设备就会发出提示音。这代表了**从复杂逆向工程到完整工作流集成**的飞跃，而过去数月的人工尝试都未能实现。

<details>
<summary>Original English</summary>

This is a Doom Mini2 retro PC style Bluetooth speaker and tiny screen. I have been hacking on this thing since January. My only goal is to be able to display funny stuff on this screen. It comes with an out-of-the-box iPhone app, but I don't want that. I live in the terminal. I want to be able to do this programmatically. This is like proprietary code loaded on this device. I was very deep in Chinese language repositories and documentation. I threw Cloud Code at this and said, "Can you figure this out?" Cloud Code could not figure it out even with Opus. I threw GPT-5.4 four at it. It could not figure it out. It connects to your phone via Bluetooth. It is interacting with this app on your phone through Bluetooth and in the app I can like draw something and click send and it will display here. But we could not figure out how to encode that message. I spent truly hours downloading a Bluetooth profiling profile on my phone for developer debugging. I then hooked it up to a packet sniffer so that when I was using the app here on my phone and it sent an image to this device, it would log and sniff the packets and tell me what Bluetooth was sending to this little guy. I threw these logs and all the information that I had at 5.5. I said, "This thing is connected by Bluetooth. Take what you know and please just do anything to figure out how to display on this. You have so much information. You should know how to do it. I believe in you." And guess what? This effing thing did it. It did it. I was able to build a command line tool where I can run it in terminal. Press enter. This is months, months, months of trying to hack into this stupid thing. It was encoding and decoding bitmap files. It was crawling the web trying to find if there was some secret SDK. Codex, you did the thing. And even better than that, it is now hooked up so that anytime I ask Codex to do a thing, it will alert me on this.

</details>

---

### 模型人格与工程价值的权衡

GPT-5.5 的一个特点是我所谓的**"烤土豆人格"**（Baked Potato Personality）——这是 Codex 平台的标志性风格，略显呆板。但 Codex 支持通过 `/personality` 命令调整这一点。在早期测试中，有人提到 Gen-Z 式的人格显得过度，但**我宁愿要一个年轻、有个性的模型，也不愿要一个生硬的纸袋版本**。对于**高级软件工程师和员工级工程师**而言，真正的价值在于能够**以最小的干预完成大规模、多层次的技术工作**，而非追求 UI 的友好程度。最终的建议是：将 GPT-5.5 Pro 投入到质量问题、bug 堆积、安全评估中——它在这些复杂问题上的表现已证明可以弥补自身的成本。

<details>
<summary>Original English</summary>

It has the baked potato personality that we've all come to know and love from Codex. It is a dull dull character, but I learned over the testing of this, if you do `/personality` in Codex, you're able to change that to something a little friendlier. And while some of my fellow early testers said it had too much of a Gen Z personality, I said, "I like to stay young. Give me that Gen Z GPT-5.5. I'll take it any day over the paper bag baked potato personality that you get out of the box." For senior software engineers and staff software engineers, I'm going to go blow through a bunch of technical work and I really love this model. Throw this thing at your quality issues. Throw this thing at your bug backlog. Throw this thing at a security assessment and close the quality gaps or performance gaps or security gaps in your app. It does really, really, really well.

</details>