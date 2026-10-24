---
author: How I AI
date: '2026-06-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=EJKwI4m0fZg
speaker: How I AI
tags:
  - vibe-coding
  - app-development
  - prompt-engineering
  - ai-video-generation
  - fitness-technology
title: Vibe Coding 实录：非技术人员如何将 AI 健身应用 Daily Hundreds 推向 App Store
summary: 本文详细记录了非技术背景的 Bryce 如何利用 Replit、Lovable 和 Claude 等工具，在短短几个月内完成健身应用从创意到上线 App Store 的全过程。她分享了“Vibe Coding”模式下的实战流程、通过 Gemini 与 Higsfield 生成定制化 AI 动物健身视频的技巧，以及在 AI 时代初学者心态如何重塑软件开发与职业竞争力的深度洞察。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Replit
  - Lovable
  - Railway
  - WorkOS
  - OpenAI
  - MetaView
products_models:
  - Daily Hundreds
  - Gemini
  - Claude
  - Claude Code
  - Higsfield
  - Kling
  - GPT-4o
media_books:
  - What Got You Here Won't Get You There
  - How Women Rise
  - A Whole New Mind
status: evergreen
---
### 创意起源：从人才招募到“Vibe Coding”的跨越

**Bryce Ratner Keithley** 过去大部分的职业生涯都沉浸在**人才与招聘**（Talent and People）领域。尽管长期与顶尖的技术领导者共事，但在她看来，自己与那些能够通过计算机科学改变世界的人之间存在着巨大的代沟和“抽象层”。然而，随着去年秋天 AI 工具的爆发，她感受到了一种直觉：也许她也可以尝试一些魔法，体验那种在电脑前敲敲打打（Beep Booping）就能让创意跃然屏上的快感。

这种渴望在疫情期间埋下了种子。当时 Bryce 每天在房间里待 20 个小时，几乎不动。她曾经尝试过每天 100 个俯卧撑的挑战，但很快就觉得枯燥乏味。她心想：“如果有人每天告诉我做点不同的运动，我肯定愿意完成那 100 个。”这个念头促使她同时打开了 **Lovable** 和 **Replit**（Replit: 一个云端协作代码编辑与部署平台），留下了最简单的提示词：**“帮我做个工具叫 Daily Hundreds，每天给我推一个不同的练习，让我记录 100 次重复。”** AI 工具极速生成的 **最小可行性产品**（Minimum Viable Product: 具备核心功能以验证市场假设的初步版本）令她感到不可思议。由于 Replit 有她熟悉的工程总监可以随时求助，她最终选择了在该平台上深入开发，并开启了这场从 0 到 1 的“**Vibe Coding**”（Vibe Coding: 强调直觉与愿景而非传统硬编码逻辑的开发模式）之旅。

<details>
<summary>Original English Source</summary>

I built an app called Daily Hundreds. I opened Lovable and Replet actually on the same day and left the simplest prompt. It was incredible to me that I could tell these AI tools, I want this. And it spit out a very basic minimum viable product of it.

Welcome back to How I AI. I'm Claraveo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have my friend Bryce Ratner Keithley who is decidedly not technical. She's actually spent her entire career in talent and people, but she has somehow beat me to the app store with a vibecoded fitness app.

Yes. So, most of my career has been in talent and recruiting, and I've had the privilege to work with really talented, incredible technical leaders throughout my career. And on one hand, through working with these folks, you come to see how talented they are with what they build. And on the other hand, do you come to see that they're living breathing humans as well? And without being a computer scientist myself, there was this massive gap and full abstraction between who they are and what they could do. And with these new tools that came out, even going back to last fall, I kind of got an inkling of like, well, maybe I can try something too and see what the magic is all about and see what the high is you get from be boopping into a computer and having what you build show up on the screen.

I built an app called Daily Hundreds for consumer number one. The story dates back to the pandemic where I spent 20 hours per day every day in this literal room and wasn't moving and had two young kids at home and I craved exercise and there was this very short-lived 100 push-up a day challenge that I started doing but felt like it was boring and monotonous doing push-ups every day. And I kind of thought, I wish someone could just tell me something different to do every day. I would happily do a hundred of them. And it kind of came back to mind. I've been doing it intermittently throughout of just jumping jacks or squats here and there between meetings. And I was like, that seems like a lightweight thing that I can try. And so I opened lovable and replet actually on the same day and left the simplest prompt of, hey, build me a tool called daily hundred that pushes a different exercise to me to log a 100 reps. And it ended up building something remarkably fast. It's not what you'll see today, but it was incredible to me that I could tell these AI tools, I want this. And it spit out a very basic, minimum viable product of it. I ended up sticking with Replet because I could phone a friend. I have a friend who's a director of engineering there and I figured at a worst case he could unblock me. But that was really how it started. And I built this starting in October and I got it into the app store earlier this month.

</details>

### 利用初学者心态与计划模式进行协作

对于非技术背景的创作者，Bryce 认为“**初学者心态**”（Beginner's Mindset）实际上是一种优势，因为她完全不知道边界在哪里。在开发过程中，一个关键的突破点是利用 Replit 的“**计划模式**”（Plan Mode: 开发工具中用于先行规划架构而非直接生成代码的功能）。

早期她直接要求 AI 修改进度条，结果往往会产生莫名其妙的混乱（Bananas）。学会使用计划功能后，她会先与 AI 沟通宏观蓝图：“**机器人，这是你的非技术朋友想做的事，我们如何为新点子进行协作？**” 配合 Replit 的预览面板（Preview Panel），她能迅速判断开发路径是否正确。尽管过程中经历过无数次偏离轨道，但这种一体化的工作流让小规模开发变得极其简单。更有趣的是，作为一名“Vibe Coder”，她甚至在不完全理解 **Railway**（Railway: 一个现代化的云托管平台）底层架构的情况下，就将其作为了自己的应用基础设施。这种“**信任机器人神明**”（Trusting the beep boop robot gods）的态度，反而让她发现并突破了原本可能被技术常识锁死的界限。

<details>
<summary>Original English Source</summary>

I tend to think that a beginner's mindset can be used to your advantage here because I truly don't know what I don't know. A big unlock somewhat from your pod is that there's a plan mode. I would sometimes get myself in trouble by asking Replet, you know, how can we change the progress bar? The progress bar is like, you're adding some reps and now it's in a circle, but it started as a line. And initially, I would say, let's change the progress bar to a circle. And it would just do something bananas. And I would have to quickly like undo that. We don't like that. And coming to see they have a plan function was really helpful and profoundly changed how I would approach things and tend to start really big picture of like, okay, robot, here's what your non-technical friend wants to do. How can we collaborate on our new idea? It has a preview panel that y'all can see right here, which makes it really easy to see if you're on the right track or the wrong track. Sometimes it magically happens on the right track right away. Other times it goes on the wrong track many, many times over. But it's really all in in one and made things very simple to at least work at at a small at a small scale.

I got really good at copying and pasting, but I think I knew how to do that beforehand. I got way better at labeling things so I could find things on my computer. I still don't think I know candidly any more about software than I did when I started to the extent that like when I learned that heaven forbid I had to take my app from my precious replet and move it to somewhere else before it can be an app, I moved it to Railway. I don't actually really know what Railway does and yet it's there now.

The fact that you, a very non-technical person, are buying or acquiring railway as your infrastructure without really knowing what it is kind of amazing from a go to market perspective for these AI tools. And I'm sure saying what you don't know and then trusting the beep boop robot gods also helps you discover and push further than you would if you knew the boundaries of things.

</details>

### AI 动物健身教练：精准提示词下的高保真视频生成

**Daily Hundreds** 的核心亮点是其内置的**拟人化动物**（Anthropomorphic Animal）演示视频。为了解决用户关于“超人式练习怎么做”或“反向箭步蹲是什么”的疑问，Bryce 决定让动物来做示范，而不是自己亲自上阵。

她的生成流程是一个多工具协作的系统闭环：
1.  **静态形象设计**: 在 **Gemini**（Google 开发的大型语言模型）中生成身穿运动装备、处于特定起始姿势的拟人化动物图像。她强调“**起始位置**”是成功的关键。
2.  **动作捕捉拍摄**: 亲自拍摄自己做标准动作的视频。
3.  **视频合成**: 利用 **Higsfield** 平台中的 **Kling 3.0**（Kling: 一种高效的视频生成模型）模型，将静态图像与她的动作视频进行融合（Mash-up），让静态动物精准还原她的健身动作。

Bryce 此前教授 **Barre** 课程的职业背景在这一环节发挥了奇效。她能够写出极其专业的**运动引导词**（Exercise Queuing）：“双膝位于臀部上方，肩宽距离，双手置于脑后”。这种对身体姿态的精准掌控能力转化成了极高质量的提示词。当 AI 生成出错时（例如让动物一直悬空或多出一只脚），她会采取“**极致字面化**”（Hyper-literal）的沟通策略，甚至通过截图标注来消除任何解释空间，最终生成了动作自然、连镜子反射都高度真实的动物健身视频。

<details>
<summary>Original English Source</summary>

We have anthropomorphic animal demos. Yeah. So, it turns out that micro workouts, like exercise snacks, are really good for you. I did start sharing it with my network, even when it was small and just on Replet. And I would get text messages of like, what's a superman? How do I do a reverse lunge? What's a reverse push-up? And I was like, I've got to like not be the single point of failure here. But then I got kind of stuck in the what person do I make? Is it all of me? I really didn't like that idea. And I thought we all have animals. And so I've created anthropomorphic animal videos. they are all obviously AI generated and I've really kind of gone ham on these.

Creating the animals in Gemini. I came to learn that the starting position for the animals was really key. Gemini wasn't doing the videos, but I was making the animals there. And my husband introduced me to Higsfield. And so there's a ton of models in Higsfield and one of their capabilities is to merge mesh intertwine a still image with a motion video to have what's in the image doing what's in the video. I found that clling is the model that works best for these videos. I make the animal in Gemini. I film myself doing the exercises and then I mash up the anthropomorphic animal with Bryce exercising to create the videos.

Create an anthropomorphic leopard in a gym setting wearing exercise gear. Its hands behind its head. Elbows out to the side. Head resting down on the mat. The head should be to the left. And the feet should be to the right. The knees should be positioned above hips. And the feet forward in a tabletop position. I have to call out that she has a secret power here which is she used to teach bar and so being able to prompt somebody knees over hips shoulder width apart hands behind your head. Who knew that all those skills would work into prompting an AI image genen model to make a leopard doing crutches?

It's really true. As I often tell people, like you never know what lateral moves in your career are going to end up being tools that pay off in dividends later. And I am quite good at physical exercise queuing and now I use it a lot. I'll often ask myself, can I be any more literal in what I'm describing?

You put these two image and video side by side. They're roughly the same shape of character. You're using this Cling 3.0 motion control model and then you're saying the image is what's going to control the scene versus the video is what's going to control the scene because you don't want the videos in your living room. You want the videos in 24-hour fitness animal edition.

</details>

### 打通 App Store 上线的“最后里长”

从一个 Web 端的实验项目到正式上线 **App Store**（App Store: 苹果公司的移动应用发行平台），是许多开发者面临的巨大挑战。Bryce 起初得到的反馈是：“你最终必须雇佣技术人员来帮你通关。”但在 2026 年初更强大的模型发布后，她决定靠自己。

她的**双层 Claude 协作流**极具启发性：
*   **规划层 (OG Claude)**: 她告诉原生 Claude：“我不是技术人员，请给我一个从 Replit 迁移到 App Store 的详细步骤计划。”将 Claude 作为她的“副驾驶”和“技术架构师”。
*   **执行层 (Claude Code)**: 根据计划，她调用 **Claude Code**（Claude Code: 具备代码库操作权限的 AI 代理工具）来编写具体代码。
*   **交互层 (Terminal)**: 最终在 AI 的指导下，她勇敢地踏入了曾经让她感到恐惧的终端（Terminal）执行具体指令。

在一个周末高强度的 25-30 小时劳作后，她在第二次尝试时就成功通过了苹果的审核。她总结道，面对 Apple 的拒绝反馈，最简单的办法就是**原封不动地复制粘贴**给 Claude。无论是处理隐私设置的错误选项，还是紧急添加“使用 Apple 登录”或“删除账户”按钮，AI 都能给出精准的修复路径。

<details>
<summary>Original English Source</summary>

I started building this in October and once I realized that I wanted to keep using it every day and to your point not only do people not want this as a web app. You certainly don't want it to be dailyund00.replet.app because nobody's going to go there. it was like okay well the holy grail is getting this to being a published app in the app store.

Beginner's mindset went into claude and was basically how do I prepare a replet app for app store submission and kept it really broad and gave it the context that I am not technical. I can use cloud code, what do we do next? And it gave me, I think it was like five pretty meaty items that we were going to have to go through. And so what I would do is I would use Claude, original Claude as like my friend in the cockpit of like what are we doing? How are we going to approach this? And it would tell me when to go into Claude code. Claude code would write me code. I would bring that back into claude and say this is what you told me to have it do. Here's what it did. it would confirm or give me thoughts on it and then it would tell me to put it into the terminal directly which was a fascinating and at first terrifying experience but that was ultimately what I would do. I'd bought between claude, claude code, claude and terminal and really continue. I took about 25 or 30 hours in one weekend and just cranked through it but ultimately got it into the app store on the second try.

Yes. So, there were three things. I just took it all. I copied it and pasted it from Apple's feedback into Claude and was like, "We did not achieve full publishing. Here's what it said." One was like checking the wrong box on parental child proofing. The second one was I needed to add signin with Apple, which I had done, but I never tested it. And then you need to have a way to delete your account. She truly beat me. I am a competitive vibe coder. This is super impressive. People are unconstrained by execution and they can take a good idea and make it production ready.

</details>

### AI 时代的职业价值观：从执行者到决策者的演变

这次跨界开发不仅让 Bryce 获得了一个应用，更重塑了她对**职业竞争力**的思考。作为一名人才招聘专家，她意识到：在这个时代，**“最佳创意获胜”**已成为现实，而不是特定的职能部门。

她提出了几个关键洞察：
1.  **交叉授粉 (Cross-pollination)**: 拥有跨学科的谦逊与好奇心是基本盘。拒绝接受新技术、坚持固有工作模式的人将面临淘汰。
2.  **人类角色的转变**: 在技术面试中，如果工程师只关注“最快找到工作方案”，那就偏离了重点，因为机器人永远更快。人类的角色已从单纯的“执行方案”转变为“**全局工具链的管理者**”。
3.  **右脑思维的价值**: 她引用了 Dan Pink 的《全新思维》（A Whole New Mind），强调随着电脑接管更多的左脑逻辑，**共情力、全局观和人文关怀**等右脑特质将成为人类保留影响力的关键。

Bryce 的故事向所有非技术人员证明：**如果你相信自己并愿意缩放思考的高度，AI 就能抹平执行力的鸿沟。** 那些曾经让你获得成功的技能（What Got You Here）可能无法带你走向未来，但那种对结果保持开放、不拘泥于过去的适应能力，将是通往新高度的入场券。

<details>
<summary>Original English Source</summary>

I've personally always gravitated towards environments where the best idea wins, right? It's not only certain people have the best ideas, but I think in this day and age, it's table stakes to cross-pollinate and have both like the humility and the curiosity to work with others in ways that you haven't before. I think people that get territorial or constrained by what they used to do are going to struggle with relevance.

If an engineer come in to a technical interview and focus only on finding a working solution fastest, it misses the point because the robots can find a working solution faster than they can. And if they're not recognizing, hey, in this equation, the human role has shifted. I need to step back and consider my role as well as the full suite of tools and understand that my role as a technical expert is broader and different than it was 6 months ago.

If you haven't read What Got You Here Won't Get You There or How Women Rise, it's a good reminder. definition of insanity is doing the same thing and expecting different results. I did listen to a whole new mind by Dan Pink. Especially as computers can do more leftrain thinking, there's an opportunity and a lot of inspiration for seizing and maximizing humanity with right brain thinking.

Dale Carnegie enthusiast. I do try and be more measured and decent and prepare myself for continued robot evolution. So I try to be decent and firm when needed and also keep my position of power polit. Hyper literal and the screenshot is your friend. Reset. refresh or rewrite if I need to and then try something new.

</details>