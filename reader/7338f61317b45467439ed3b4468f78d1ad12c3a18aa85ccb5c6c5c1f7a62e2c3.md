---
author: The Pragmatic Engineer
date: '2026-03-29'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=5nMa3p3qw1w
speaker: The Pragmatic Engineer
tags:
  - software-replication
  - long-tail-problems
  - human-ai-interaction
  - cultural-nuances
  - builder-motivation
title: 当一切皆可被复制：AI 时代的构建者存亡录
summary: Chip Huyen 在演讲中探讨了 AI 彻底降低构建门槛后，开发者面临的动力危机。她指出，当软件能被 AI 瞬间克隆，传统的“数据护城河”已然失效。然而，通过分析长尾问题、文化颗粒度以及人机协作的范式转移，她提出构建者的核心价值正从“如何构建”转向“构建什么”，并呼吁回归创造的本真喜悦。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - GitHub
products_models:
  - GPT-5
  - Claude
  - PostgreSQL
media_books: []
status: evergreen
---
### 复制陷阱：当软件遭遇“吉卜力时刻”

在 AI 飞速进化的当下，构建者正面临前所未有的心理震荡。这种震荡源于一个残酷的现实：**软件的复制成本正趋向于零**。当一个侧边项目仅凭一周时间就能获得 30 万次曝光，却在次日被他人利用 AI 工具瞬间克隆时，传统的构建动力结构彻底瓦解。我们正处于一种“兴奋与绝望”的往复循环中——虽然每个人都拥有了构建一切的能力，但也意味着你所构建的任何东西都不再具备排他性。

这种现象预示着**软件即服务**（SaaS: Software as a Service）中那些仅解决微小痛点的“轻量级 SaaS”将走向消亡。如果用户能用 AI 轻易复刻你的核心功能，每月 50 美元的订阅费便失去了合理性。更深层的危机在于，传统的**数据护城河**（Data Moat）正在失效。数据不再是天然的防御墙，而仅仅变成了“昂贵的资源”；只要有足够的资金投入，任何领先的模型（如 GPT-5）或数据集都能被快速复制。软件行业正迎来其“**吉卜力时刻**”：就像 AI 可以通过描述生成吉卜力风格的图像一样，现在只要你能清晰地描述软件，AI 就能为你构建它。当想象力被直接转化为生产力，我们必须重新审视：如果一切皆可复制，持续构建的意义究竟何在？

<details>
<summary>Original English Source</summary>

Who here thinks that the job won't be automated by AI in the next five years? Wow. What do you do? How do I get a job? So, who here thinks that your job will be automated in the next five years? Okay. So, I just did this question yesterday. It was just curious like what people online would think and it seems like a lot of people think that the jobs are going to be automated. 

Recently I launched something as a side project. It's small. It got like 300,000 views. And within a day, I got an email from someone saying like, "Hey, I love what you built. So I use Clico to recreate exactly that and here's a link." And I'm just like, I'm flattered, but also like what? So it made me realize that whatever exists can be replicated. I just fluctuate between excitement and despair because on one hand, I feel like now I can build anything I want but at the same time anyone can build anything I want. So what is the incentive structure for me to do anything? 

I have stopped using a lot of what I call like SAS light. I feel like it solves a very small problem and charge me like $50 per seat per month. Why should I keep paying for you when I could just recreate exactly that with AI? People tell me data is a mode but it turns out that data is not a mode, it's just like expensive. It's not really a mode if somebody can just throw money at it and acquire data and build it. I call it like the Ghibli moment of software. If you can describe a style, AI can generate it. If you can describe a software, then AI can build it for you. You remove the need for imagination.

</details>

### 长尾护城河：文化差异与人类偏好的复杂性

尽管标准化功能的构建已变得廉价，但**长尾分布**（Long-tail Distribution: 描述极少数头部问题被解决，而大量稀疏、个性化的边缘案例被忽略的现象）中蕴含的问题依然是人类构建者的自留地。AI 虽然擅长处理海量的共性数据，但在面对极其私人化、具备地理文化特异性以及年龄跨度带来的复杂需求时，往往显得力不从心。

以越南市场的**语音机器人**（Voice Bot）开发为例。在西方，企业倾向于优先部署文本机器人，因为文本处理比语音转文字、模型推理、再到语音合成的链路更简单。但在越南，由于摩托车出行的普及，用户极其厌恶在移动中打字，这迫使当地企业必须先攻克语音交互。更微妙的差异在于**响应延迟**（Latency: 系统响应的时间差）。在美国，社交习惯要求响应几乎即时（约 80 毫秒），否则就会产生社交尴尬；而在许多亚洲文化中，出于尊重，人们习惯等待 200 到 300 毫秒以确保对方发言结束。这种对“尴尬感”的不同定义，是单纯靠模型训练难以精准捕捉的文化底色。只有深入特定的人群画像和使用场景，构建者才能发现那些 AI 尚未覆盖的边缘案例。

<details>
<summary>Original English Source</summary>

I built because I want to solve a problem. One thing I do believe is that there would always be problems to solve. Problems follow a long-tail distribution. AI would get really good at common issues, and over time it would cover more and more edge cases, but the edge cases would never go away. 

Human preference is one thing I don't think that human preference is just an equations that people can just package nicely. It's very personal, very culturally dependent, geographically dependent, age dependent. I'm from Vietnam. Here, companies deploy customer support chatbot usually go the text route first. But in Vietnam, people are on the motorbike all the time, so they actually really don't like typing. So companies in Vietnam actually deploy voice bots before they do chatbot. 

There are a lot of cultural nuances. For example, the response time. In the US, people expect you to respond instantly, like 80 milliseconds. Whereas in Asian culture, we actually wait a lot longer, more like 200 or 300 milliseconds to make sure the person finish. Voice bot you want to balance latency and also humanness. You have to understand all these nuances. Only when we go into specific use cases and specific demographics we're targeting that we can understand.

</details>

### 范式重构：从行级评审到可逆环境的治理

随着 AI 深入开发工作流，传统的**人机交互**（Human-AI Interaction）和团队协作模式正面临剧烈的重塑。目前的工具往往只是在旧瓶装新酒，例如在终端和 IDE 之间设置隔离。但从本质上讲，无论是**终端**（Terminal: 基于文本命令的交互环境）还是 **集成开发环境**（IDE: 提供代码编辑、调试等功能的综合软件），它们的目标都是将指令转化为产品，这种边界在 AI 时代应当变得模糊。

在协作层面，**代码评审**（Code Review）流程正变得极度低效。资深工程师仍习惯于对 AI 生成的代码进行逐行审查，试图以此辅导初级员工。然而，这种反馈往往是“不可执行”的，因为初级员工并非代码的直接撰写者。真正的指导应当从“如何写代码”转向“如何给 AI 发送更优的指令”。

此外，随着 AI 智能体获得更多环境访问权限，**可逆性**（Reversibility）成为了安全治理的关键分水岭。在代码或数据库环境中，错误往往是可撤销或有备份的；但在现实世界或跨平台的表单提交中，行为一旦触发便无法回滚。建立针对不可逆行为的防范机制，是防止 AI 造成灾难性后果的关键。

<details>
<summary>Original English Source</summary>

Humans interact with AI. People are trying to retrofit whatever exist to fit what they think is a new workflow. What's a fundamentally difference between a terminal and an IDE? A lot of that is still ongoing questions. Human to human collaboration is actually very complicated. Who here is still review every single PR line by line? 

I talked to a team recently. The senior person reviews team members' AI generated code line by line for education. But junior members were like, I'm not writing the code, how do I give that feedback to my AI? The whole workflow of reviewing code is very outdated. Senior members should be giving feedback on how you give instruction to AI to produce better. 

AI interaction with the environment is another thing. Terminal is already getting a bit more dangerous. Recently Claude just wipe out my Postgres locally because it was trying to create a new app and that port was taken. A lot of environments that AI currently operate in are reversible. You can revert back to the last commit or previous backup. But there are a lot of environments where the action cannot be reversible. If an agent fill a form and click submit, we cannot reverse that. Or in the real world, a car runs over a pedestrian, you cannot reverse that. We need to build out the guard rails for the non-reversible actions.

</details>

### 结语：迈向“匠人软件”的喜悦

未来的世界需要变得更“智能体就绪”（Agent-ready）。目前的数字世界仍充斥着人类中心的设计，如过时的**速率限制**（Rate Limit: 限制在特定时间内请求次数的机制）和低效的网页搜索模式。当 AI 搜索网页时，往往机械地模仿人类点击 URL、提取引用的行为，造成了巨大的信誉点额浪费。

真正的变革不在于“如何构建”，而在于“构建什么”。当 AI 接管了生产力，构建者将从繁重的商业逻辑中解放出来，回归到构建的原始驱动力：**喜悦**。软件将呈现出一种“匠人化”趋势，我们不再仅仅为了规模化而生产软件，而是像制作手工礼品一样，为朋友的一个小爱好（如茶叶追踪）去打造专属应用。构建，最终将从一种生存手段进化为一种纯粹的创造性表达。

<details>
<summary>Original English Source</summary>

Who is making the world more agent ready? Websites, rate limits... the whole concept of rate limit is quite irrelevant to AI. I did a benchmark on how AI do web search. It visited a thousand URLs but only 20 were unique. It's a very human way of doing search. There must be a more efficient way that are less human-centric and more AI-centric. 

The question nowadays is usually less about how to build. The question is what you build. Who is going to build the things that don't exist yet? Who should be imagining it? Fundamentally I enjoy building, it just bring me joy. I hope we can normalize building things for fun. Before we had mass manufacturer clothes, now people want something custom made. I'm not sure if we'll have a future where there's "artisan software", but for now, I enjoy building apps as a gift for my friends. AI does make my life for now happier.

</details>