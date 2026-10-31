---
author: AI Engineer
date: '2026-07-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UcYoMg-8-L8
speaker: AI Engineer
tags:
  - ai-assisted-development
  - design-engineering
  - collaborative-workflow
  - rapid-prototyping
title: 在 Automattic 亲历的30天“极端速度月”：AI 时代下设计师向设计工程师的蜕变
summary: 本文记录了 Automattic 开展的为期一月的“极端速度月”实验。作者 Sanja Grbic 作为一名非技术背景的产品设计师，在双人团队中利用 AI 协作和公司的基础设施支持，在30天内连续交付了桌游管理应用、开源设计系统状态追踪器以及 WooCommerce 移动端商户实时 AI 客服聊天系统。展示了 AI 时代下研发团队中工程师作为“赋能者”的新角色定位，以及设计师转向“设计工程师”的全流程掌控模式。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Automattic
products_models:
  - WordPress
  - Storybook
  - Figma
media_books: []
status: evergreen
---
### 实验前奏：构建分布式的 AI 学习底座

在进入这次速度实验之前，有必要先了解 **Automattic** 内部使用人工智能（Artificial Intelligence: 模拟人类智能的计算机系统）的背景积累。作为 wordpress.com、Jetpack、WooCommerce、Tumblr 和 Beeper 等产品背后的母公司，我们拥有约 1400 名员工，并且实行完全的分布式和异步工作机制。这种长期的分布式协作文化让我们积累了数十年的详尽文档和知识库。

在 AI 浪潮来临时，公司不仅鼓励我们去学习和尝试，还启动了全员浸润式的“AI 赋能计划”（AI Enablement: 针对各岗位定制的 AI 实操培训）。每位员工都会参与为期两周的专属课程，包含了针对具体职能方向的理论和高强度上手实践。随着 AI 编程工具的发展，非技术人员也被积极鼓励直接参与到代码库的贡献中。得益于系统运维团队建立的安全环境、规范流程以及极其清晰的本地开发部署文档，即使是像我这样没有工程背景的产品设计师，也能够轻松在本地运行起工作开发环境。而在日常的调研与规划中，我高频使用 **Context AC**（一款专为 AI 助手提供企业内部历史知识与文档访问权限的 MCP 服务端），以充分发挥我们数十年积累下的文档资产优势。

<details>
<summary>Original English Source</summary>
I'll tell you a little bit about Automattic first. We're the company behind several products in the WordPress ecosystem such as wordpress.com, Jetpack, WooCommerce, as well as many other brands like Tumblr, Beeper, and many more. We are around 1,400 people and we're fully distributed which is pretty interesting for also what what I'm about to show you. We're fully distributed distributed and asynchronous which means that most of our work, our thoughts, our concepts from the past couple of decades are very well documented. I'm a product designer and I've spent over a decade building software and watching how teams build software. I've worked for I've been at Automattic for 5 years now on the Jetpack design team and in the past I worked for several companies of different sizes, different types of products, and different team organiza- configurations. So after all these years I've not only accumulated experience in designing products, I also have a lot of insight into team dynamics and organizational structures within product teams. Over the years the the designer role has morphed and evolved a lot. We we had We still have all of these different types of of roles like web designers or UX designers or interaction or product designers. We've also used many different tools from the Adobe suite to Sketch to Figma and many many others in addition to those. And AI is a new tool. It is definitely not built just for designers. It's versatile so it can be used by many other um many different roles, but the expectation is is the same for everyone. It's that it will bring a speed. And of course, this is why companies are rushing to put it to use. But no matter what role uses AI, um this velocity is going to look very different in small teams like one to three people that are building new products. Let's say a zero to one product versus large organizations that might have built entire entire product ecosystems, that have software that's anywhere between 5 and 20 years old and that have uh more than a thousand or even thousands of people. Before I dive into the experiment, I will tell you a little bit about what preceded it in terms of how we use AI at Automattic. We were encouraged to use it, to learn it, and to experiment with AI from the very beginning. At first, we had access to tools and courses. Then the AI enablement was initiated where every single employee goes through a two-week course designed specifically for their role. This is completely immersive with lectures and and focused hands-on time. Very very helpful. And over time as AI coding tools got better, everyone was encouraged to get comfortable with contributing in code. And we can thank our systems and operations team for setting up fantastic security and processes as well as documentation that's good enough that a non-engineer such as myself can spin up a working development environment. And last but not least, an incredibly helpful tool that I that I use every day for research and planning is context AC. It's an MCP server that gives AI tools access to all of the knowledge and data that we have documented over the years that I previously mentioned.
</details>

### 项目一：在共同协作中重塑工程师角色

大约两个月前，公司正式开启了**极端速度月**（Radical Speed Month: 暂停日常路线图规划 30 天，由两人结对，全权自主构建并交付真实可用项目的倡议）的探索。全公司约有三分之一的员工（近 500 人）首批参与，在 30 天内启动了 794 个不同的项目。此时刚好也是我参加两周线下 AI 赋能课程的期间，因此 AI 工具在我的交付中扮演了至关重要的角色。

在第一个项目里，我们组成了包含两名设计师、一名产品经理和一名开发工程师的四人临时小组。为了给当晚的团建做准备，我们决定在短短两小时内用代码实现一个**桌游局管理工具**。该工具能够创建、加入和管理桌游场次，实时查看可选游戏和空余席位，甚至集成了即时聊天功能，并搭配了颇具趣味性的 16 位像素风办公室插画。

在这个项目中，最大的收获并非我们做出了什么，而是团队协同模式的转变。团队中强力的开发工程师在 GitHub 上初始化了项目，并辅导我们掌握了基本的 **Git**（Git: 用于追踪文件修改历史的分布式版本控制系统）指令与工作流。这种脱离核心业务、无风险且强调学习的环境，让我们的注意力完全聚焦于跨界尝试。这带来了一个重要的行业启示：在 AI 辅助开发的今天，资深工程技术人员的价值不仅在于自己写了多少代码，更在于他们能够成为团队中的**赋能者**（Enablers）和**导师**（Teachers），带领其他跨职能角色通过 AI 探索代码世界。

<details>
<summary>Original English Source</summary>
So back to the experiment. About 2 months ago, we kicked off this project. The instructions were to pause the roadmap work for 30 days, pair with a partner, and ship something real. We were welcome to use AI, though it wasn't a requirement. And of course, um we couldn't all do this at once. We had to do this in in stages, and we had about a third of the company participating in the first round. That's around 500 people that started around 794 projects in these 30 days. One lucky circumstance for me was that during this month, I was also participating in this 2-week in-person AI enablement course. So AI tools played a huge role in what I was able to deliver. Um and that's why I was building not one but three different projects. And when Radico Speedman started, uh I I had some knowledge of GitHub. I would review PRs. I had played around with cloud code. But I had never until then actually built and shipped something in code. And I mean at work. Like I've done a small hobby project here and there, but that's completely that was a completely different experience. Uh I'm going to share my personal journey of how my skills and process and collaboration style shifted over the over the course of the 30 days. And this will also give us insights into how this change can be promoted and implemented at the organizational level for large companies. So this is the story of the first project I worked on and my first contributions in code. As I mentioned at the time uh Radical Speed Month was starting, I was at the in-person A&E enablement training. And over there we did an as as part of the program we did an exercise where as a group of four we had uh 2 hours to build something together. We were two designers that aren't super comfortable in code, an engineer, and a product lead. And we decided to build this board game session manager. We had a board game evening planned that night. Uh so we wanted to create an app that's that's used to create, view, and join, and manage board game event sessions. Um you can see what that looked like. This is what we built in in 2 hours. We built an app um where people can start and stop uh uh a session, uh see what games and spots are available, and even chat with each other. And on top of that we chose this 16-bit style um illustration of our actual office that uh people found especially appealing. The most interesting thing about this project isn't what we built. It was how we worked together and leveled up together. Uh at the very beginning we agreed that we all want to uh contribute, and we were very lucky that the engineer that was uh in our group was really really great at setting us up for success. So she set up the project in GitHub, helped us grap grasp some basic commands, and helped us understand how Git works. I worked with versioning in the past um for you know, in different situations, but and I thought I understood Git, but actually I didn't. I really needed someone to to tell me how it works and and what what are the best ways to to to set up a project. We were sitting together, we were testing out the app, and we were building it um together and dividing the work among us. So, we were committing code to this project. And since this wasn't this this this app that we were building, it's not related to any of of our existing products, so there were no risks involved, and our focus was on learning, which was really really really great. We only used Cloud Code for this purpose, and outside of that, I think the only visual tool used was Nano Banana to to create um uh to create the office illustration. And the biggest insight, I think, for me from this project was that if you're an engineer, the impact that you have when you enable others may be far greater than the impact of doing more engineering yourself. And for any this this is a great learning for any role. It can be the same for engineering or design or product. Keep in mind that when you're working on a team with mixed abilities, and if you're stronger in a specific skill, make sure that you're helping and enabling each other up, because now with AI, we can all do a little bit um of the work that's outside of our domain. And this was the biggest learning for me, uh that engineers will need to become enablers and teachers.
</details>

### 项目二：从产品设计师蜕变为设计工程师

在首个小项目的鼓励下，我开始独立探索速度月的第二个项目，这也成为了我之后两周半时间的主力重心。在该项目中，我与一名研发人员和一名设计运维人员合作，试图解决一个宏大的痛点：**如何在不断演进的开源设计系统中，向团队和 AI 助理高时效地呈现最新的状态和组件库数据**。

由于工程性能和长期维护成本的不确定性，最初提出这个设计系统追踪方案时，合作的工程师有所顾虑。但我决定在没有包袱的情况下独立发起概念验证（Proof of Concept: 快速验证方案可行性的原型开发）。在此阶段，我作为唯一的设计与编码实施者，花了两周半时间写出了这个应用。这个被称为 **Design System Tracker** 的工具效果超出预期：它能够直接抓取 GitHub 仓库、Storybook 和 Figma 的链接，对数据进行状态自动分类和归档，生成实时组件渲染预览，并且保证了极佳的搜索性能。

在流程上，我们打破了“先在 Figma 中做高保真视觉再交接给研发开发”的传统交接链路，转而由我直接在生产代码上进行快速原型修改，最终仅在细微视觉调整和 Moodboard 阶段返回 Figma 协作。这一探索标志着我完成了从**产品设计师**到**设计工程师**（Design Engineer: 兼具界面设计与前端系统编码实现能力的复合型研发角色）的转变。在缺乏条框限制的探索空间中，独立做出决策并拥有全栈实现的“完整掌控感”，使效率呈数量级攀升。

<details>
<summary>Original English Source</summary>
Moving on to the second project I worked on, this was my main focus for the radical speed month. I paired with an engineer and um a design operations person. And our goal, our main goal, we we worked on some design system projects together in the past. And here our main goal was to surface relevant and up-to-date design system information to humans and AI tools. And this um problem space is huge. Our design system uh that we use for our WordPress ecosystem products is open source. It serves many products internally and externally and is always in flux. So, the problem space was big. Uh we saw a lot of opportunities. So, we decided to divide and each person took on a problem to tackle. And what I proposed this design system status track tracker um the solution that I proposed raised questions with the engineer around performance, around maintenance, and if we would be able to to build it in the first place. But I was kind of empowered by the previous exercise. I was allowed to experiment, so I decided to build the full idea as a proof of concept on my own. So, um the discovery portion was three people, but the design and build was just myself. And it took around 2 and 1/2 weeks to build this. And as I worked on it piece by piece, especially uh when I reached the point where I had actual live component previews working, I was really mind-blown at what I was able to achieve. I moved through the project without any um without any restrictions in mind. Um I was just trying to push the limits. And um the tracker was picking up links from the GitHub repo, from Storybook, from Figma, sorting them according to status, tagging them with the correct library names. Search worked perfectly, and I was really excited about this product, and I shared it with fellow designers. I iterated a little bit based on the feedback, but everyone was pretty excited. I built the prototype initially as a start, and then I used Figma only later in the process for some visual fine-tuning. Some things that I just couldn't explain to claw to claw code, I I wanted to deliver an image, and that worked. But the live project was was I was what I was iterating on directly. And the prototype was built within a week, and then it took another week and a half to rebuild it for some fixes, to set up a hosting, and deploy it in our internal platform as an internal tool, as well as on an external public-facing site with that that had a little bit of a curated um data and information. And delivering this this product was a defining moment for me, where I moved from a designer to a design engineer. This is of course enabled by AI, but most of all, it was enabled by the fact that I could own the entire process. We were within the radical speed month, I was allowed to experiment. I I I had the agency and made all of the necessary decisions. In large organizations, this is very hard to do, but here I could just build whatever I thought was um was needed, and I didn't have to spend a lot of time in negotiations and handover.
</details>

### 项目三：极致极速下的全天候双人协同

在极端速度月的最后一周，我与另一位设计师结对，在短短 **6 天** 内从零交付了第三个项目：一款面向 WooCommerce 商户的 iOS 移动端实时客服应用。

虽然时间极短，但该项目完成了完整的功能闭环。它集成了 wordpress.com 的 OAuth 统一身份验证与 Jetpack 的连接系统，允许商家直接在手机上接收顾客咨询。更有价值的是，它包含了一个高度定制的 **AI 助理客服**（AI Agent: 能自主分析上下文信息并执行任务的 AI 实体），该助理能自动扫描网站的相关文档信息，在线解答买家疑问，并智能判断何种复杂情况该交由人类接管，何种情况可由其自动答复。

如此高速度的产出，得益于我们将设计理念和方案的碰头，直接记录到了一个与代码工程并行的云文件系统中。由于大家已经对 AI 协同开发工具有了高度默契和技能沉淀，我们不需要进行耗时的需求文档对齐。设计师和工程师能够以极其统一的敏捷节奏直接在代码和可用原型层面对齐，从而实现了小团队的高效爆发。

<details>
<summary>Original English Source</summary>
And then that was 2 and 1/2 weeks, so I kind of had 1 week left Um a radical speed month, so I paired with a fellow designer and here you'll be able to see the incredible shift and speed and process that happened. In only 6 days, we went from zero to uh through the entire process to building an iOS chat for WooCommerce merchants that um allows them to answer shoppers in real time, reply from their phone, or even set up AI to answer the uh questions for them. And this is a fully working proof of concept that includes authentication through wordpress.com, includes a Jetpack connection. If If you use WordPress, you might know what that is. Um we also built a widget that inherits the site theming where the site visitors can actually ask the questions, as well as the the fully capable AI agent that scans the site for information and answers visitors' questions in real time, and also discerns whether it can answer a question or or not. What was important here was that the the alignment and the the ideation part was fairly easy. It was fairly easy for us two designers to align and shape the features with because we always have the users in mind. And on the process side, um what was interesting is that we started the exploration as a cloud code project folder where all of the chats and ideas were recorded into a file system. And I noticed that that um significantly uh sped up collaboration, as well as build later. And we've uh continued I've continued this practice in my in my daily work. Um the main artifact we worked on here as well was the prototype. And that's the biggest shift for our process because normally we would start in Figma and we would work in Figma until we reach very high fidelity. But here uh, we had uh, very good plan. Then we um, built the the the the prototype or the product and then we went back into Figma to just come back to it in a visual sense to build a mood board and for some UI fine-tuning.
</details>

### 总结：大型组织的效率革新建议

回顾这 30 天，长久以来固化的软件研发模式在 AI 的冲击下被迅速打破：
* 工程师正从“纯粹的代码编写者”转变为跨职能成员的**赋能导师**；
* 设计师逐步将工作重心前移至真实的生产代码中，成为能够独立交付成品的**设计工程师**；
* 高度的**自主决策权**和**无干预实验空间**是激发组织效率的动力源泉。

正如本次实验所证实的，如果想在大型组织中解锁被 AI 赋能的潜在生产力，即便无法推行全员改革，也可以在团队局部尝试这种结对极速交付模式。通过为团队成员扫清安全和本地部署的技术障碍、找到技术赋能的布道者并给予充分的原型试错空间，任何团队都能突破陈旧习惯，让 AI 工具真正释放出颠覆性的研发速度。

<details>
<summary>Original English Source</summary>
And in only 30 days, my process that has been similar for years has completely shifted. And that was true for many other people. The first project showed me how the engineer's role can be elevated from a builder to an enabler. And this is a skill that I believe will be crucial as more and more um, people in other roles start working in code. The second one moved me from a designer to a design engineer. Um, and here I'm talking about being able to push code to production in a well-established large system that requires serious onboarding and security practices. All of the company initiatives that I described together gave me the space I needed to experiment and find my own process that works within what we already have established in the company. And and the third project that I shared was just proof that we've unlocked speeds because I already had adjusted my process a little bit, but then we both leveled up together and had a shared understanding on how we can apply the tools so we could also easily meet each other. If you're in a large organization, try to implement this um even just at your team level. Uh changing processes or tools in large organizations requires shifting the human behavior behind them. So, provide your people with the access to the new tools, find your enablers and champions, create space for experimentation, and and give them agency so that they can break out of their habits and unlock the speed that AI tools can bring. Thank you.
</details>