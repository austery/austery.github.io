---
author: a16z
date: '2026-08-05'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Iy1W8vOxv5o
speaker: a16z
tags:
  - underwater-robotics
  - autonomous-systems
  - modular-design
  - asymmetric-warfare
  - ocean-infrastructure
title: 重构海洋基础设施：Ulysses 水下机器人与海洋新局势
summary: 本篇双语档案记录了水下机器人企业 Ulysses 的愿景与技术路径。面对AI超级周期带来的海底线缆、关键矿产与能源增量需求，以及地缘政治冲突下的不对称安全威胁，Ulysses 研发了高性价比且快速迭代的模块化水下机器人，旨在打造7x24小时全天候协同的海洋固定基础设施，成为海洋领域的 SpaceX。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - Ulysses
  - a16z
products_models: []
media_books: []
status: evergreen
---
### 战略转向：AI 超级周期与地缘政治下的海洋新局势

在当今地缘政治和科技发展的双重交织下，海洋正受到前所未有的关注。一方面，**AI 超级周期**（AI super cycle: AI技术爆发带来的算力和基础设施建设热潮）极大地拉动了对**海底光缆**（subsea cables）、**关键矿产**（critical minerals）及能源的需求，而海洋正是这些核心资源的主要来源地。另一方面，**地缘政治**（geopolitics）冲突使得海洋安全局势日益复杂，例如霍尔木兹海峡（Strait of Hormuz）的排雷难题、曼德海峡（Bab-el-Mandeb）的航道威胁，以及海底光缆窃听和输油管道爆炸等安全隐患。传统的昂贵军事装备在面对**非对称战争**（asymmetric warfare: 较低成本的武器摧毁高价值资产的战争形式）时已显得力不从心。因此，低成本、高可靠性、具备规模化部署能力的**自主无人系统**（unmanned systems）正在成为海洋探索与防御的核心力量。

<details>
<summary>Original English Source</summary>

To a surprising extent, the sea has remained a mystery. 10,000 fleets still sweep over it in vain. We know less of the oceans of our feet where we came from than we do of the sky above our head. It is time to change this, to use to the full our powerful new instruments of oceanic exploration to drive back the frontiers of the unknown in the waters which encircle our globe.

We started Ulyses 3 years ago in the effort to build underwater robots to solve a very specific problem. We wanted to massively scale up underwater ecosystem restoration. But in doing that and going after that problem, we realized that there is a lot more than underwater ecosystem restoration that needs to be scaled up. Work underwater being expensive or difficult was a limiting factor and not only applications in nature in offshore industry and in defense too.

AI super cycle is increasing demand for subc cables. It's increasing demand for critical minerals. It's increasing demand for energy. These are all things which the ocean is a primary resource for. There's going to be robots that operate in and manage every domain 10 to 15 years from now. You see it already happening on land with self-driving cars and in the air with delivery drones and things like that. We're the ones building the robots for the ocean.

We're already pretty much supply limited instead of demand limited, which is a good problem to have. The demand hasn't been constrained to one domain like defense or commercial crowd. Both sides honestly, people can't seem to get enough. There are so many people chomping at the bit to have vehicles that are reliable come in at a cost that's low enough that they can get them at a meaningful scale and capable enough to actually do the things that matter in the ocean.

All right. So this tenuous ceasefire in the Middle East negotiations have largely centered on that crucial shipping point, the straight of Hormuz. Today was an exercise in messaging whiplash about whether or not the straight was actually open. Is there any way to be sure those mines have been removed? Well, yes. According to an American technology company, the company is called Ulysus, and it says it's created drones that not only can detect these mines, but more importantly can disarm them.

There's so many things changing in the oceans a lot due to this new order of geopolitics that we're seeing coming out. Whether it's mines being placed in the straight of Hormuz and Iran being unable to find them again or threats on the Babel Manda or tapping of undersea cables or oil pipelines getting exploded. But this isn't anything new for people that have been working on the sea for years. The nature of warfare is fundamentally changing. It's becoming more distributed, more autonomous, less centralized. And the investments that the United States military has made in exquisite systems over the last 50 years, while they have been important, they are simply not sufficient to fight the conflicts of the future.

There's so many things that are happening in the ocean that often enough go unnoticed. But now, because they're, you know, raising oil prices, they're actually getting noticed in the news. The sea is starting to get its time in the sun, you could say. Warfare is trending increasingly asymmetric where small cheap things can be used to take out very high value assets. This is what we saw in Ukraine. This is going to happen in the ocean. You need to make things cheaper. You need drones. You need unmanned systems. The maritime domain is just becoming more and more important.
</details>

### 逆向开发与标准化：Ulysses 的模块化机器人架构

面对海洋环境中高盐度、高腐蚀性等天然的恶劣条件，Ulysses 团队放弃了昂贵且不可行的一体化商业水下载具，转向了**模块化设计**（modular design: 将系统划分为可独立装配和更换的模块）。创始团队通过将**内部机加工**（in-house machining）引入研发流程，实现了“今天设计，明天测试”的极速迭代。其核心技术亮点在于**标准化接口**（standardized interface），每个模块均配有统一的电源引脚与数据连接器，整车载具均能共享电池电压及高速数据通信。用户只需在现场花费20分钟，即可通过挂载多波束回声测深仪、声纳等不同传感器，或增加额外的推进器与电池，完成针对特定任务的硬件配置。

<details>
<summary>Original English Source</summary>

Jamie was walking with one of his friends who was doing seagrass restoration and this was off the coast of Scotland. So you can imagine stormy weather, horrible rain, everything. And essentially the process for doing seagrass restoration is you pick up a handful of seeds and chuck them off the side of a boat. The initial kind of nugget of a thought there was that we could mechanize this. So we started out the company by building these attachments that were meant to go down and plant seagrass. We looked at the price of these vehicles online and it was just ridiculous compared to the cost of the stuff that we were making. It was multiple orders of magnitude higher and it just wasn't feasible for us to use an off-the-shelf unmanned underwater vehicle. So that's when Jamie and his drone background came in.

Testing in the water is a challenging environment for robots, specifically seawater. It wants to destroy anything robotic and it's corrosive. We immediately discovered that operating in the ocean works very very differently. The ocean is always trying to kill you and flood whatever you put inside it. On the mechanical side of the house, we've brought machining inhouse specifically so that we can design something, make it the next day and see if it works.

We have had a lot of customer input that the modularity is important to them and what it enables is that they can add the sensors they want. They can configure in the field to add more battery or more skewability with extra thrusters etc. Each one of our modules has a standardized interface. We have two power pins here and a data connector here. Every single module has that load out so they can all connect together. They're all getting full battery voltage and full data connection across the entire vehicle. every single connection is standardized. If we want to go down and survey something um with the multi-beam echo sender or sonar systems, uh we can just strap those to the front of it and have that capability within 20 minutes. That's the beauty of the modular system.
</details>

### 蓝色版图：构建 24/7 全天候海洋基础设施

真实的海洋物理数据比任何模拟器都要精准。通过高频度的真实水域测试，Ulysses 积累了宝贵的迭代数据。他们的最终愿景是建立一个由水面及水下载具交织而成的**全天候协同网络**（24/7 collaborative network），使机器人成为类似于人造卫星的海洋固定基础设施。Ulysses 致力于重新定义人类与海洋的互动方式，不仅要从海洋中获取资源，更要通过大规模水下生态修复回馈海洋，成为在海洋领域具有垄断性技术代表力的“**海洋公司**”（The Ocean Company），正如 SpaceX 在航天领域的地位一般。

<details>
<summary>Original English Source</summary>

Real world data is always better and always more accurate than any sort of simulation you can do. When going into space, it's a lot harder to access space and just go up to test and get your real world space data. It's not the case with the ocean. You know, most of the planet is covered with it. So, we have this advantage where if we can get something that's ready to go in the water, we can get the best possible feedback to iterate on. We want to actually fundamentally change how things are done in the ocean. And that requires us to look at the underwater ecosystem an entirely different way.

The broader vision of what we're doing is that you have a network of surface and undersea vehicles and they're operating 24/7 to solve these critical tasks all around the ocean. They become fixed infrastructure in the ocean in the same way we've just accepted that there is satellites above our heads. And that's where we want to push the ocean towards.

really don't know why it is that all of us are so committed to the sea except I think it's because we all came from the sea. And it is an interesting biological fact that all of us have in our veins the exact same percentage of salt in our blood that exists in the ocean.

By and large, our ocean is still a mystery. If Ulyses is successful, we explore, understand, and protect this last great frontier.

Future of maritime is fleets. fleets that are operating everywhere all at once.

We like to use the moniker the ocean company sometimes because where we want to be in 5 10 years is a company that is synonymous with the ocean in the way that SpaceX is synonymous with space. We want to be the technology company that fulfilling its vision completely rethinks how we can act with the ocean and enables humanity to get a lot more out of this resource and to give a lot more back to it.
</details>