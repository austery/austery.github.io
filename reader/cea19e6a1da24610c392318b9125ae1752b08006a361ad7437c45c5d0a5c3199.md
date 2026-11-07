---
author: How I AI
date: '2026-10-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=HYb5w4PfPZM
speaker: How I AI
tags:
  - personal-agent
  - agent-architecture
  - human-ai-interaction
  - workflow-automation
title: 实测 Claude Duet：精美设计的个人 Agent 为何难敌 Grok 与 Muse？
summary: 本期深度评测 Anthropic 最新推出的个人 AI Agent 客户端 Claude Duet。尽管其具备无缝集成 Claude 产物（Artifacts）、类 Slack 频道化组织以及极其精致克制的 UI 设计，但因主动通知较弱、移动端局限、模型执行延迟高以及缺乏团队多人协作与本地 Skill 互通能力，在激烈竞争中难以彻底取代现有主力工作流。
insight: ''
draft: true
series: ''
category: ai-tooling
area: PAI
project: []
people: []
companies_orgs:
  - Anthropic
  - OpenAI
products_models:
  - Claude Duet
  - Codex
  - Grok
  - Muse
media_books: []
status: evergreen
---
### 破局者还是冗余项：个人 Agent 疲劳下的严苛审视

面对当前市场上层出不穷的 AI 助手，我们正处于一个充满矛盾的节点：一方面是 **Anthropic** 推出了设计极为精良的全新个人 Agent 产品 **Claude Duet**；另一方面，许多高频用户却正在经历严重的“个人 Agent 疲劳症”（Personal Agent Fatigue）。在日常工作流中已经充斥着各类自动化助手的今天，市场并不缺少平庸的产品。任何新工具若想争夺用户的注意力并成为首选的**核心个人代理**（Core Personal Agent: 日常最高频依赖、处理跨场景任务的专属 AI 助手），其表现就绝不能仅停留在“优秀”，而必须达到“卓越”。

从产品定位来看，Claude Duet 是一款原生支持 iOS 和 Android、且与网页端 Claude 账户深度同步的移动端个人代理。Anthropic 对其切入点的把控非常克制且精准：它既不像某些完全面向普通大众的生活消费级产品那样过于低龄或泛化，也没有走向纯代码向的重度极客路线，而是牢牢锁定在**企业业务人员、中小企业主、创业者、产品经理及高管**这一中坚群体。它旨在成为用户随身携带的智能外脑，承接那些原本可能在桌面端协同办公软件中处理的工作。

<details>
<summary>Original English</summary>

I have good news and I have bad news. The good news is Anthropic just released a new personal agent and it's really welldesigned. The bad news is I have personal agent fatigue. I am so tired of new personal agents. And while this one is super super well-designed and I'll go through what I love about it, I just don't need another one. And so to compete for my attention, to compete for being my number one personal agent, you have to be not good, not great. You have to be exceptional. And we're going to see in today's episode if Claude Duet, their new personal agent, is exceptional. Let's get to it.

Okay, before we go into my experience with Claude Duet, just a very, very quick overview of what this is. It is a phone, iPhone, Android based personal agent that is synced up with Claude. So, it is proactive, although I will go through how proactive it really is. It's proactive. It can use all the tools and plugins that your cloud has access to. And they really position this as being a personal agent for small business owners, for busy people, for professionals. So, none of this like your mom's going to use it with Muse and none of this like you have to be a developer. This is like solid middle of the road. Business user, SMB, entrepreneur, busy PM, busy CEO, um, agent. The things that you would reach for in co-work on your desktop, maybe you'll start reaching for on your phone.

</details>

### 精致克制的产品设计：无缝集成与频道化基元

尽管市面上不乏强大的竞品（例如 OpenAI 的生态或 Codex 平台），但 Anthropic 在 **Claude Duet** 的外观打磨与交互细节上展现出了令人惊叹的设计功底。与某些充满毛刺、体验割裂的早期 Agent 相比，Duet 的整个应用界面干净流畅、毫无粗糙棱角，从引导流程（Onboarding）开始便展现出极强的品牌信任感。更为核心的是它在产品**交互基元**（Interaction Primitives: 构建软件用户心智模型的最基础交互架构）层面的几项精妙设计：

1. **连接器与插件的完全继承**：只要网页端已配置好 Gmail、Google Workspace 或 Figma，Duet 即可无缝调用，零迁移门槛。
2. **目标与任务清单可视化**（Task Lists）：引入清晰的任务跟踪列表，让用户随时掌握 Agent 正在进行的目标与后台排期，减少黑盒焦虑。
3. **原生级产物支持**（Artifacts: Claude 生成的独立交互卡片、代码、HTML 预览或演示文档）：Duet 将 Artifacts 视作一等公民。无论是在手机对话中实时生成的幻灯片，还是历史账户中积淀的产物，Duet 均能直接调取与交互。
4. **类 Slack 的频道化组织**（Channels）：不同于纯线程或单聊天框，Duet 借鉴了团队通讯工具的架构，允许用户围绕特定项目（如销售线索追踪）建立专属频道，理清了复杂多任务的上下文边界。
5. **抽象温和的视觉形象**：Duet 采用了一个极简且略带抽象感的拟人点状图标，既不唐突也不产生视觉压迫，恰到好处地平衡了专业与亲和力。

<details>
<summary>Original English</summary>

Now, you all know that I really love OpenAI products. I use codecs all day, every day. But I will say one thing that Anthropic did so so so well that OpenAI's Dots did so so so poorly is the polish of the agent design. This app is beautiful. It is welldesigned. There are no sharp edges. It is clearly incredibly well thought through from a design perspective. Everything from the very very early test flight versions that I got access to to the current beta that's out in research preview. From the second you onboard, they are really thoughtful about walking you through what to do. It looks really nice. It feels really trusted. I had zero problems getting up and running out the gate. It was a really nice onboarding. It was a little similar to my experience with Muse where it was very clear upfront what to do.

The product itself has some primitives again like Muse that I think you're going to see over time emerge as like core for agent design. Of course, it has plugins and connectors, so it inherits all your plugins from Claude. So, if you have your Gmail set up, your Google setup, your Figma setup, whatever you have set up in Claude, it's immediately available here in Duet. It also has task lists, which is something I really liked from Muse's agent design. I like the idea of keeping track of what goals and tasks I'm doing and what goals and tasks the agent is doing. So, I think the task list view is something that's really nice here and something that was really thoughtful.

And then what it has that again Muse has, but it does just a little bit more polished, is it treats artifacts as first class citizens. So if you're used to artifacts in claude code or in co-work if you're generating HTML artifacts designs slides anthropic has made those first class citizens in duet so that whenever you're generating stuff in your little chat with your little duet it's going to create those artifacts and it actually already can read the artifacts existing on your cloud account. So when I showed up here and looked at my clot account, it already had all those artifacts that I had generated over time in there and I had a really good sense of what I could do next.

Finally, the last thing I really love about Duet is the idea of channels. So we're all trying to decide what the primitives of are for agents. In Codeex, you have all these threads in chat. You have all these chats. In Claude, you have threads and chats and projects, all sorts of things. In Muse, you have your main chat and side chats. Everybody's trying to figure this out. And Anthropic borrowed a little bit from Slack, which I feel like is everybody's favorite tool to borrow UI designs from. So now you can kind of think of your duet as a main thread, a main chat, but but also side channels that you set up. Like here, I created a sales channel for working on sales projects.

And then I'll say my last little thing that I really like that I did give the anthropic team credit for, their little dot icon is really cute. It's abstract. It's definitely anthropic claude e. It's cute, but I have no problem with this little, dare I say it, dot. Um, it's just adorable, not offensive, not weird. I like it. Yes, of course. I love my personalized Muse consumer agent and that engenders a lot of joy with all the little characters. Of course, I love my little Grock bots and their little icons, but this is inoffensive and I think it's just fine. And as somebody who cares about design, I thought it was pretty good.

</details>

### 主动性的双刃剑：克制设计如何演变成注意力缺失

然而，在实际体验中，**Claude Duet** 在关键机制上暴露出明显软肋——其宣传的**主动交互能力**（Proactive Notification: AI 主动发起提示、推动用户决策或跟进进度的机制）在现实场景中过于孱弱。在初次完成初始任务后，该 Agent 几乎不再主动向用户推送任何信息。这引发了一个深层次的交互设计困境：设计上的克制与无干扰，在客观上反而降低了产品粘性。

从**用户留存与增长工程**（Growth Engineering: 借助机制激励促进持续活跃的系统化策略）的角度来看，如果一个 Agent 过于安静，它就极易被淹没在繁杂的多工具生态中。目前普遍采用的“每日晨报”（Morning Briefing）形式已难以激发兴奋感。对比在桌面端极具存在感且提醒及时的 Grok Bot 或 Muse，Duet 在缺乏桌面常驻入口的前提下，若在移动端保持静默，便会迅速失去用户的即时关注。要建立深度的协作依赖，个人 Agent 必须在“不过度骚扰”与“保持必要的存在感与声量”之间取得更具进取性的平衡。

<details>
<summary>Original English</summary>

Now, what are some things that I did not like about Duet? Well, I will tell you for a proactive agent, it just wasn't that proactive. I don't know if I forgot to turn on notifications or it's just not that annoying, but once I set up Duet a couple days ago and did a first couple tasks, it never pushed or bothered me to do anything ever again. It also doesn't show up in the desktop app. So, it's a really disconnected experience. And so, while I felt like the initial experience was pretty good, I ended up not using it a ton. one, because I have a million other personal agents, and two, it really didn't push me to come back.

I think one of the things that these agent designers are really going to have to figure out is what is a notification strategy that actually engages users. I get them from DOT all the time. They're not that exciting. I get them from now duet. They're not that exciting. Like, there's got to be something better than the morning briefing to engage agent users on why they would come back to the agent over time. And right now, I don't think any of these agents, except for maybe Grockbot and Muse, have really figured this out. So, it's not as proactive as I want. The notifications aren't noisy enough for me to remember it. You know, I've said it's elegant and well-designed and subtle and not annoying, and those are all positives in some ways, but from a growth hacking perspective, and the ability to get me to re-engage with your product, that doesn't work. I need you to be a little bit more annoying. I need you to be a little bit more proactive. I need you to be a little bit more noisy or I'm truly going to forget you in the ecosystem of all my agents.

</details>

### 推理延迟与闭环阻碍：多任务并发下的执行摩擦

在实际测试具体业务与生活任务时，交互深度与执行效率的短板进一步暴露。当要求 Duet 梳理跨邮箱和 Slack 的未读信息时，其虽然能够聚合信息，但在上下文权重判定与优先级排序上略显平庸。而在高频代购场景的评估中——例如委托其购买勇士队（Warriors）对阵步行者队的门票——系统性能的劣势暴露无遗。虽然底层调用的 **Claude Opus** 模型推理质量极高，但在个人 Agent 的快节奏互动中，过长的响应等待时间（Latency）严重破坏了人机协同体验。

AI Agent 的核心心理价值在于模拟一位“全天候待命且秒级响应的高效同事”。当用户在移动途中派发购票、生成 PPT、校对内容等并发任务时，Duet 虽能将其分流至独立线程，但动辄耗时超 10 分钟且中途缺乏有效的状态同步与权限请求打扰。这种无法**快速闭环**（Close the Loop: 迅速完成从指令发出、执行到确认返回的完整流程）的迟滞感，直接导致用户在等待中转移注意力，最终将此类长尾任务遗忘。在个人代理场景中，高延迟正成为压垮同步协作意愿的致命伤。

<details>
<summary>Original English</summary>

So, what were some things that I asked it to do and how well did it do it? Well, the first thing I asked it to do was just this like basic kind of like go through my email, go through my Slack, figure out what's going on. I would say it didn't do an exceptional job at that. It did okay. It came up with a couple things, but the priority didn't seem right. The context didn't seem right. So, I do think there's a little work on the quality of the interaction.

I asked it to find me good Warriors tickets. You know, go Dubs. I want to go see the Warriors when they play the Pacers. It's a noon game. I can actually take my kids. And so, I've had all my agents try to shop for tickets for me, shop for shoes for me. I thought this was a good eval. I had it go shop for me. And this is the second thing that I think is bad about it. So, the first thing that I didn't love about Duet is that it is not that proactive. The second thing that I don't love about it, and this has been my experience with Claude generally, is it's slow, man. And I get so disengaged waiting for the models to finish. The killer feature of Muse Meta is that it is fast. In fact, Codex with their GPT ultraast models, it just keeps me engaged because I am always moving to the next step, always getting something done. And so even though I really love Opus 55 as a model and even though it does really good work, the performance is so slow and you really feel that in a personal agent and it degrades my desire to work synchronously with an agent. You know, one of the benefits I think of an AI agent is that it is like a colleague, but a colleague who's up 24 hours a day and responds to immediately. But if that colleague is slow, if that colleague goes to a meeting to get work done, like you kind of forget and don't want to go to that colleague over your more responsive ones, even if the more responsive ones do like 10% worse of a job.

And so it was shopping for these warrior tickets for me as I was like passenger princess and driving to dinner. And like I kind of forgot that it did it cuz it took so long. It didn't close the loop. And then by the time that I came back, I was off to something else. And so even though it tracked it in this, you know, checklist of things that it was doing, the performance was really frustrating. And I think this adds up, especially if you use a single chat, single agent, where you're firing off a bunch of tasks. Like you're saying, "Okay, check my email and I need you to make a deck and I need you to make edits on this thing, and let's figure out what we do for social." And in Claw Duet, it those all kicked off individual threads, but then they took so long and I'm telling like 10 plus minutes to finish those threads or come back to me or ask for permissions. And because it wasn't noisy, because it wasn't, you know, like in my face, I actually forgot about all those threads. And so while like foundationally it's really welldesigned, the models are very good, the intelligence is there, and like I can't knock anything specific about the user experience. The reality is like the latency and the inability to close loops meant that this particular agent product just really fell to the bottom of my use list.

</details>

### 生态割裂与单人局限：通往生产级工具的必修课

除了推理性能与通知机制外，Claude Duet 迈向成熟生产力工具还需跨越三道核心屏障：

* **桌面端原生形态的缺失**：在日间工作与频繁会议中，依赖手机操作会产生严重的注意力摩擦。竞品如 Grok Bot 之所以能占据心智，关键在于其桌面客户端始终驻留在屏幕一角，以极低切换成本参与实时工作流。
* **本地能力与技能孤岛**（Local Skills: 开发者或重度用户在本地配置的定制化提示词模板与脚本环境）：Duet 无法直接继承桌面端 Claude 的本地定制技能（如基于 Chat PRD 自动化生成产品发布视频的流水线），在不同设备载体间造成了明显的体验与上下文断层。
* **团队多人协同机制的真空**（Multiplayer Mode: 多个团队成员共享、协同调度与观察同一个 Agent 实例的协作架构）：目前 Duet 依然是典型的“单人单机”（Single-player）工具。即便引入了频道形式，依然缺乏轻量级团队共享通道。对于拥有小型团队的管理者而言，无法将配置好的 Agent 便捷分发给协同成员，极大制约了其在组织层面的推广可能。

总体而言，Claude Duet 是一次极具工匠精神的尝试，其产品精致度远超同代竞品的初始版本，为 Agent 界面的基元设计树立了极高标杆。但在解决端侧常驻、推理提速、上下文互通与团队协作等深水区挑战之前，它尚不足以颠覆由 Grok Bot 与桌面 Agent 构建的成熟生产力壁垒。

<details>
<summary>Original English</summary>

I think the other thing that they are going to have to solve ASAP. And again, this is in research preview. So, it's an early access list. It's in beta. I'm sure they will get there is a desktop app. The reality is I do not want to be on my phone during the day when I'm doing work and sitting on meetings. I need a desktop app to engage with my agents. I think that's why like Grockbot does so well is there's a desktop agent. It's cute little icon. It's sitting there staring me in the face. I'm always chatting with it like it's Slack. Same with Muse. You know, I started using it as a mobile app, but very quickly download the desktop app. And then even same with Dots from Codeex, which I don't even use, but at least it's in the desktop app. Like at least my dot bay is staring me at the face in Codeex like with a little icon at the bottom.

And so what I would say about Duet is like it's got all the makings of a great agent, but it needs to show up. Maybe that's intentional. Maybe the design is to be calm and soothing and helpful but in the background. But I do think to compete for attention right now, it is not enough to have beautiful design. It is not enough to have these artifacts which is actually really awesome and one of the best parts of the Claude ecosystem. The agent itself has to be super proactive. The agent itself has to be super fast and it has to get stuff done quickly enough so that I don't disengage with it.

Okay, so that was a very long aside for buying Warriors tickets. A couple other things that I had it do, good, bad, left, right, you know, standard evals. I had it look at my sales pipeline. Nice things there. It was already connected to Slack. It was already connected to my email. It was already connected to our CRM. So, it was able to pull in that data pretty quickly. Um, I had it create a deck in Google Docs. I have a really high bar for design and so I was disappointed that it didn't use pitch or gamma or whatever, but it worked. It was created in Google Docs and it was kicked off from my phone. I think for like the kind of everyday business person who maybe is not as particular as I am about design, having an agent kick off a deck on your phone on the go with Duet. So, I think that was like good, not great, but I have a really high bar for that stuff.

And then one other point of like friction and disappointment, again, this is a minor thing, but I think for heavy users this matters. I've been making all these launch videos in Claude. I've been spending a whole bunch of time doing like chat PRD launch videos in Claude. They're super cool. Um, and I wanted to see if I could create those in Duet on my phone. The reality is unfortunately duet does not ingest all your local skills. Um so I probably need to push these skills as plugins to claude and then it can ingest them into Duet. But again I think with all these product surface areas and this is not just an anthropic problem. This is an open a problem. um is like the shared context, the shared experience, what ports over elegantly, what does not port over elegantly, I think is going to be an open question for folks who want to really migrate to Claude Duet.

I'd say the final thing that's really missing is look, we don't work alone and Duet right now is clearly a agent for single player use. In fact, like most of the Claude projects feel like very good products for single player use. I just don't think even with claude tag claude and slack all these things I don't think they've quite cracked multiplayer and I've been moving more of my grobbot usage to team agents and deploying those in Slack. So while Claude Duet with these channels might feel like Slack, it doesn't have a multi-player capability. Like I'm not running a team of 500 anymore. I do not need like the full enterprise deployment, but I am a small business owner. The problem is I have a small team, so you know, I have like five humans that I interact with on a daily basis. If I don't have a way to share my agents with them, I'm not sure if it's going to fit into my stack.

So, that is my very quick preview, early review, early thoughts on Claude Duet, the new personal agent from Anthropic. I would definitely give it a try. Again, I maybe have different use cases, different preferences, different desires than other folks. I think it is approximately 100 times more polished than Dots was when it came out. So, I think that's really nice. I think it is quite elegant. It does the job well. I would just say there's like fit and finish things that they really need to work on. So, give it a try. Sign up for early access if you can. Let me know what you think and let me know if Claude Duet becomes part of your stack because I'm just not sure it's going to become part of mine. Thanks for joining How I AI. Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube or even better, leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.

</details>