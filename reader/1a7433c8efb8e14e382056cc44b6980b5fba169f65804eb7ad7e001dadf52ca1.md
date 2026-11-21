---
author: AI Engineer
date: '2026-04-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4fntwuOoedA
speaker: AI Engineer
tags:
  - personal-agent
  - life-os
  - local-first
  - human-computer-interaction
  - autonomous-agent
title: 应用的终结：从待办工具进化到自主代理的‘生命操作系统’
summary: Kitze 在演讲中回顾了他从 10 岁起对效率工具的痴迷，以及开发 Benji 等应用的心路历程。他深入探讨了 AI 代理（如 OpenClaw）带来的范式转移，分析了当前大模型在可靠性、UI 交互及‘麦片盒般枯燥人格’上的痛点。最终，他提出了‘逆向提示’与‘应用消亡’的愿景：未来的计算机将不再由用户主动寻找应用，而是由深度集成个人数据的本地 AI 代理主动管理生活，应用将仅作为专业工具存在，而大众用户将步入动态生成 UI 的新时代。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Kitze
companies_orgs:
  - OpenAI
  - Anthropic
  - Apple
products_models:
  - Benji
  - OpenClaw
  - Wolffer
  - Sizzy
  - GPT-4o
media_books: []
status: evergreen
---
### 效率工具的三十年：从待办清单到“生命操作系统”

演讲者 **Kitze**（Sizzy.co 创始人）在 34 岁生日当天分享了他对生产力工具的终极反思。他从 10 岁开始就对待办事项（To-do）应用表现出近乎偏执的狂热，早期曾使用文本文件配合 **Tasker** 实现基于地理围栏和 Wi-Fi 连接的自动化提醒。他逐渐意识到，用户真正需要的并不是另一个待办 App，而是一个**生命操作系统**（Life OS: 一个能够处理全维度个人数据、决策与执行的综合系统）。

这种愿景驱动他开发了多个产品：从 2017 年基于优先级算法的 **Toodo**，到旨在整合习惯、计划和事件的 **Better**，再到 2022 年启动的 **Benji**。然而，ADHD（注意缺陷多动障碍）带来的持续兴奋点切换，以及对“再加一个功能”的无止境追求，使得这些工具始终处于“开发中”状态。他指出，现代人被碎片化的 Web 端和移动端 App 撕裂，这种工具间的摩擦力正是提升生产力的最大阻碍。

<details>
<summary>Original English Source</summary>

Starting with my first to-do app was when I was 10 years old, which is crazy. I found an old note and a notebook and some scribbles that are like barely legible were like I need to eat my string juice today. I don't know what a 10-year-old does for a to-do list, but it clearly had checkboxes and I've been trying and wrestling to solve productivity since then... I got so fed up with like the to-doist and the other ones that I started using text files way before all these local markdown blah blah blah. And I used an Android app called Tasker to basically manage all of these text files. I got contextual reminders like whenever I connect to Wi-Fi, remind me about something or when I arrive at a destination or when I bike or blah blah blah. 

I realized that I never wanted a to-do app. I wanted like sort of like a life OS. So slowly I've been going to that direction. In 2017, I made something called toodo... Then of course ADHD hit and I switched to a bunch of other apps. And in 2022 I started making Benji. It's named after my dog... I wanted all of these features like mangled into one tool that can sort of fix my life. Has it? Absolutely not. But we're going towards that. My vision is to one day have like a Benji phone and a Benji OS.

</details>

### AI 代理的兴起：从“推土式”解析到龙虾文化

2023 年 ChatGPT 插件的出现曾让 Kitze 感到“App 时代已终结”，但早期的 LLM 调用充满挑战，开发者必须通过严厉的提示词（Prompting）来强制模型输出 **JSON** 格式。他在 Benji 中实验了语音实时触发 API 的功能，用户只需说话即可看到日历和任务动态更新，这在社交媒体上引发了轰动。

随后，社区出现了像 **OpenClaw** 这样的个人代理架构（即著名的“龙虾”社区，因其 Logo 和成员身穿龙虾服而得名）。Kitze 彻底转向了**本地优先**（Local-first）与**自我托管**（Self-hosting）的阵营。他认为，要让代理真正发挥作用，必须让它们拥有对个人数据（iCloud, NAS, Google Drive）的完全访问权。为了获得更高的系统权限，他甚至从 iOS 换回了 Android，以便代理能读取通知、清理未读信息乃至安装 App，打破“围墙花园”的限制。

<details>
<summary>Original English Source</summary>

We had the chat GPT moment... I called my wife and I was like honey it's over. It's over for all the apps for all SAS. Like GPD is going to eat the world... Like 2023 before the models could return JSON, you had to bully the models to return JSON. I don't know who remembers this. Like you had to be like, "Please don't write any markdown." It's like, "Sure, here's some JSON." You're like, "No." So you had to parse it, to cut it, to to like shape it into form to make some JSON. 

My brain caught on fire. I think we got like mass psychosis. It turned into a cult. Everyone wearing like lobster suits... I joined the Discord and it was like less than a hundred people who had their Cloudbot set up... I went full hipster mode like no more Gemini, no more chat GPT, no more cloud. I wanted to fully I I got the power of finally owning the assistant, owning the files, owning the memory... I started moving to local hosted like nextcloud image local markdown for everything that requires a lot of API calls or MCP... I went back to Android because I wanted my agent to be able to read my notifications, clear my notifications, install apps, uninstall apps.

</details>

### 代理的困局：不可靠性、人格平庸化与 UI 错位

尽管热度很高，但 Kitze 坦言目前的 AI 代理正处于一个尴尬的低谷期。核心痛点在于**不可靠性**：代理经常在下一轮对话中就忘记上下文，且复杂的定时任务（Cron jobs）和多代理协作经常崩溃。他幽默地形容现在的模型人格就像是“一盒麦片”（Box of oats: 形容极其枯燥、机械且缺乏灵性），只会不断重复确认“你准备好让我做这件事了吗？”却始终没有实质进展。

此外，使用 **Discord** 或 **Telegram** 作为生命操作系统的 UI 属于一种权宜之计（Cope），这些聊天软件本质上并不适合管理复杂的生活逻辑。这种挫败感导致了社区热情的减退，原本满员的周会现在变成了“匿名代理受害者互助会”。

<details>
<summary>Original English Source</summary>

The funny thing is like as I keep talking, keep in mind that my life is far from solved. It's never been more chaotic... It's a mess, but it's a performative mess, right? ... In the beginning it was an explosion of signups... and now if you enter a meetup now, it's like five people and it's slowly turning into like um open claw anonymous. Why is this happening? because it was and kind of is for me unreliable where it matters most which is like cron jobs multi-agents the agents talking to each other the agents forgetting... 

And finally, as I would like to call them, Benthropic, they ruin the charm of it. Like as soon as you pull the model, talking to GPT5 talks feels like talking to a box box of oats. Seriously, it has the personality of this. Try this. It's like, okay, did you do that? No, but I told you to do it. Okay, I'll do it. Did you do it? No. Every conversation with Open Claw looks like that in the last and it drives me nuts.

</details>

### Wolffer 实验：层级化上下文与确定性 UI

针对上述痛点，Kitze 正在开发一个名为 **Wolffer** 的实验性工具。该工具的核心逻辑是放弃对“魔法式记忆系统”的迷信，转而采用**嵌套主题**（Nested Topics）的结构。例如，在“Benji 客户支持”这一子主题下，系统会自动注入其所有父级（如“工作”、“Benji 项目”）的描述内容。这种**层级描述注入**确保了模型在无需检索（RAG）的情况下，就能精准理解当前任务的宏观背景。

Wolffer 还强调了 **UI 的确定性**：
1. **可视化工具调用**：所有的 API 调用、加载状态和结果都以可折叠的 UI 组件展示，而非纯文本。
2. **多代理编排**：支持在不同工作空间（Workspaces）间切换，并清晰显示当前对话代理的能力标签（Skills）。
3. **动态上下文挂载**：用户可以通过 `@` 符号直接挂载 Markdown 文档、技能或密码，为代理提供精确的输入数据。

<details>
<summary>Original English Source</summary>

I started making my own thing naturally... I call it wolffer. What I believe in here I have nested topics. So I have like work projects Benji Benji customer support. And when I'm talking to Benji customer support in the first prompt, it injects the description of all the parent prompts... It doesn't need to pull from memory or some magical place. It just looks at the topic, the parent topic... It takes all the descriptions together and it immediately knows what is my work, what is Benji... 

I hated that I couldn't see tool calls. I would like to see tool calls to collapse them, to uncolapse them, to see loading spinners. There's UI for managing agents... I can mention for example hey let's fix the landing page of Benji just like and then I would add the landing page of Tinker Club for example or I can add a knowledge base or a password or a skill so I can combine multiple ads so I give it the right exact context that it needs.

</details>

### 应用的终结：逆向提示与生成的操作系统

对于行业的未来，Kitze 提出了一个激进的观点：**逆向提示**（Inverse Prompting）。在当前的交互模式中，是人主动向 AI 发起提示；而在未来，由于 AI 代理深度 ingest（摄取）了用户的所有邮件、通知和计划，它应该在用户打开电脑时，主动给出下一步建议或请求决策。这种模式下，高效的人是那些将 99% 的事务委托给代理的人。

他预测，大部分消费级 App 将会消亡。对于普通用户（Normies）而言，**本地模型**（如整合了系统权限的 **Siri** 或 **Google Pixel** 的本地代理）将接管一切任务。用户不再需要寻找“用来做某事的 App”，而是直接通过对话描述目标，操作系统将根据需要**即时生成 UI**（UI on the fly）。应用软件将退缩为仅供专家（如调色师、音乐制作人）使用的专业工具，而大众将迎来一个无应用、由代理主导的新纪元。

<details>
<summary>Original English Source</summary>

I think the role of AI is going to inverse so the way we prompt the AI right now I think it's going to inverse and the fully productive people will be the one who delegate 99% of the stuff to the AI and then the AI prompts you. It's like, hey, you didn't send me a picture of your passport... I think where we're going, we're actually not going to need most consumer apps. No, your grandma, your mom or your friends are not going to VIP code, but they'll be able to sit in this new futuristic OS and they'll be able to do any task that they want to do. 

Either the UI is going to pop on the fly or whatever it needs, but they'll be doing task and they'll forget about I need an app to do a task. They'll just do it. A small set of apps will survive, but it will be software for like specialists... But normies will just chat to their computer and their computer will do things and the UI will generate on the fly. I also think it would be the funniest thing if Apple wins all of this because local models are getting insanely good... Siri getting tool capabilities from all of their locally installed apps, not wasting any credits.

</details>