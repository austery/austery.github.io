---
author: AI Engineer
date: '2026-10-06'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=uKUA1a0Kdfc
speaker: AI Engineer
tags:
  - database-sharding
  - high-availability
  - backpressure
  - schema-migration
  - fault-tolerance
title: 在 AI 时代既要快速迭代又要保持稳定：PlanetScale 数据库高可用架构与 Agent 演进实践
summary: PlanetScale 探讨了在 AI 时代如何平衡快速迭代与数据库高可用性。通过控制平面隔离、全链路冗余、Vitess 水平分片、背压限流以及 Git 风格零停机模式变更，构建让 AI Agent 安全参与数据库治理的可靠基础设施。
insight: ''
draft: true
series: ''
category: data-engineering
area: tech-engineering
project: []
people: []
companies_orgs:
  - PlanetScale
products_models:
  - Vitess
media_books: []
status: evergreen
---
### 平衡速度与稳定：重构 AI 扩展架构

在传统软件工程文化中，“快速行动，打破常规”（Move fast and break everything）曾是早期 **Facebook** 奠定其技术优势的核心信条。在 20 年前，这一理念的底层逻辑十分明确：快速向市场交付产品和验证价值具有压倒性优先级，团队宁可承受数据库崩溃或功能故障的代价，也不愿被繁重的稳定性负担拖慢节奏。然而，随着能够自主编写代码、测试并部署系统的 **AI Agent**（人工智能代理）全面接管研发流程，软件迭代的频率与规模呈现出指数级增长。面对前所未有的工程密度，我们既不能因噎废食而放慢创新步伐，也无法再容忍基础设施的意外中断，追求“快速交付且不损坏任何系统”（Move fast without breaking anything）已成为当前系统设计的刚性需求。

现实情况是，在过去半年到两年间，整个行业普遍遭受了严重的系统扩展瓶颈。这并非单一企业的特例，而是伴随 AI Agent 驱动的爆发性需求，大量平台的日活跃用户数（DAU）在短时间内实现了 2 倍、3 倍、10 倍甚至 100 倍的激增。当海量并发涌入时，原有的数据库、应用服务器与基础设施往往无法承受重负而频繁报错。构建一个能够支撑数千万乃至数亿用户规模、并维持 3 个 9、4 个 9 乃至 5 个 9（99.999%）可用性的系统本身就是一项极其艰巨的挑战。本次演讲跳出常规关于大模型推理或提示词编写的讨论范畴，专注于**底层基础设施**（Infrastructure）的加固策略：如何在保持高速创新的同时构建稳固的数据库架构，并最终将 AI Agent 安全引入数据库治理闭环。

<details>
<summary>Original English Source</summary>

Hello everyone, how are you? I hope you are having a great last day of the AI ​​ Engineer conference. Today I'm going to talk about how to move fast without breaking anything. So, the phrase "move fast and break everything," you've probably heard it before. This is a saying from the formative years of the engineering culture of early Facebook, right? The idea was to move and release products quickly, without being limited by database crashes or broken features, because the high value of a quick release was a priority. That was 20 years ago, right? Even before AI agents appeared that wrote code for us, released and deployed solutions for us. So, more than ever before, this idea is becoming relevant.

But I think we can actually achieve both goals, right? I want to release products quickly, build great features, deliver them to customers, but at the same time not break the databases, infrastructure, and application servers that power my work. We've all probably seen something similar to this, and I'm not pointing to any specific company. There are many such companies, right? Which, due to the crazy scale that we have been observing for the last six months, a year or two, have encountered problems. Where the number of daily active users has doubled, tripled, 10 or 100 times. This is largely driven by the demand for AI agents. The infrastructure simply cannot keep up with this development.

Part of that is because it's a very difficult task, right? This is not an attempt to single out or blame anyone. It is difficult to scale systems to tens or hundreds of millions of users. But we want to have great products that scale well for many users, and for our status pages to look something like this, right? Three or four nines of availability. Maybe five-ninths of availability, where our databases are up and running, our applications are working, and our users are ultimately happy. This is the main idea of my talk, which is a little different from most of the speeches you have attended. Many of the talks are devoted to inference or specific ways of working with agents, prompting, and other things. This is more of a report on infrastructure: how to work quickly, taking into account the architecture and systems we run, which power the work of these applications. And we provide support for their databases. So this is something we as a company take very seriously. How do we scale and support companies that have millions of users on their platforms? Part of what I'm talking about is taken from an article we published last year about our database philosophy. I would advise you to find it on Google and read it.

</details>

### 高可用架构底座：控制面隔离与冗余设计

在构建弹性系统的过程中，最为核心的底层防御机制是**系统隔离**（Insulation）。基础设施的设计必须保证单点组件的故障具有严格的爆炸半径，绝不能引发全链路击穿。在典型的系统架构中，可以清晰地划分为两大核心层级：
* **数据平面**（Data Plane: 系统中负责承载与处理核心业务数据的底层存储与运行环境）：这里存放着所有支撑用户登录、交易和实时交互的最核心数据，是整个业务运行的生命线。
* **控制平面**（Control Plane: 负责系统治理、策略配置与集群管理的管控中枢）：包含系统的治理逻辑、监管闭环、分析框架、应用程序乃至新兴的 MCP（Model Context Protocol）组件。

在实际生产运维中，成熟的底层数据库本身具备极高的稳定性，极少主动崩溃；相反，上层的治理模块、应用逻辑和业务控制层因频繁变更和快速迭代，其故障发生概率要高出数个数量级。因此，架构设计的关键在于建立严格的解耦屏障：即使管理层或治理层在版本升级中发生崩溃，数据平面仍能独立维持正常运作，确保终态用户依然能够不受干扰地访问底层数据。

在隔离机制之外，保障可用性的另一支柱是全链路的**系统冗余**（Redundancy）。对于应用服务器而言，依托于**无状态架构**（Stateless Architecture: 服务端不持久化客户端会话状态、可任意弹性伸缩的系统设计），现代平台借助如 **Cloudflare Workers**、**Vercel** 无服务器函数或 **AWS Lambda** 等自动化伸缩工具，可以相对轻松地实现水平扩展与冗余容灾。然而，对于承担持久化职责的有状态数据库，系统无法容忍任何单字节数据的丢失。行业标准且经过验证的高可用范式是构建**主从复制**（Primary-Replica Replication: 主库处理写请求并向从库同步数据以保障冗余与读扩展的高可用架构）：系统部署单一的主写节点（Primary）与多个只读副本节点（Replicas）。所有写操作由主节点承接并同步至副本，读请求则分散至副本处理。一旦主节点发生硬件或网络故障，高可用管控机制能立刻将流量平滑转移至存活副本并完成角色提拔。即便是一个只有 100 名用户的早期系统，虽然单机或许能勉强承受每天 10 万到 100 万次请求，但若要迈向真正可靠的规模化扩展，建立这种完备的冗余体系依然是不可逾越的先决条件。

<details>
<summary>Original English Source</summary>

But let's look at a few of these principles. So, the first and one of the most important is insulation, right? When you manage infrastructure, it is important to make sure that you have configured the system so that a failure in one thing does not "bring down" the entire system, that is, each component must be isolated. So what I'm showing here is the data plane. This effectively means: where are your databases located? Where does your most important data live, which is needed for users to log in and interact with your app? But there are many other components, right? There are your layers of governance, your oversight loops, perhaps your analytics frameworks, your applications, your MCPs, and all of these components can potentially fail. In fact, if you use a good database platform, the database is unlikely to fail, but you update these other things more often, so they are more likely to fail. So we want to make sure that we design everything so that if the management layer fails to update, it doesn't affect the rest of the system and users can still access the database, right? And to everything at the data level. So, this is one of those basic principles that we take very seriously.

And another point is redundancy. And if any of you have worked with databases before, you've probably seen a diagram that looks something like this. Although in the case of application servers, redundancy is usually a little easier. There are many autoscaling tools, such as Cloudflare Workers, Vercel functions, and AWS Lambda, which are very easy to scale and easily provide redundancy because they are stateless. But in the database world, state needs to be stored reliably, you can't lose a single byte of data, so how do you do that? A very common approach, which is more expensive and complex, but which can scale reliably, is to have a primary node and multiple replicas. So, in the case of a database, you write to the primary node, you can write all of your data to the primary node, and then it is replicated to each replica. That way, if a server crashes, and you see that red "X" next to the primary node, the system can automatically promote one of the replicas to primary and your users can continue reading and writing data without any problems. And this is a very standard way to scale databases. It's not the cheapest, it's not the easiest, but it's a very standard way. And I would say that even if you don't have thousands or tens of thousands of users. You might have 100 users, and in that case it's still worth having redundancy, if you're serious about your business, right? You can usually easily get through 100,000 requests per day, maybe even a million requests per day. But there comes a point when other technologies have to be implemented for effective and efficient scaling.

</details>

### 系统韧性双引擎：Vitess 分片与背压机制

当业务规模跨越单机性能上限时，系统必须从垂直扩展转向更为彻底的水平拆分与自我保护设计。单节点架构在数据量处于 10GB 级别时往往游刃有余，但一旦数据膨胀至 10TB、100TB 乃至 PB 级别，单一物理服务器的存储与 I/O 承载能力将彻底失效。此时必须引入**数据库分片**（Database Sharding: 将海量数据与并发查询水平切分至多个独立物理节点的扩展机制）。在分片架构中，整套数据库被水平切分为多个独立的底层分片（Shards），并通过前端部署的智能路由代理 **VTGate**，对上层传入的 SQL 查询进行语法解析与分片键计算，将流量精准分发至对应的物理节点。在 **PlanetScale** 的生产实践中，针对 MySQL 生态依托开源分布式引擎 **Vitess**，针对 PostgreSQL 生态则采用对应的专用扩展层，将海量查询和数据均匀分散至由众多计算节点与磁盘组成的分布式集群中。

然而，分片绝非能够孤立运作的银弹，它必须与高可用冗余深度融合。在生产环境中，每一个独立的分片模块（如 Shard A）自身都必须内嵌完整的主备架构，配置一个主写入节点（Master）与多个只读副本（Replicas）。一旦该分片的主节点出现宕机，分片内部能够实现快速的局部故障切换与自我修复，而绝不会波及其他分片及全局系统的连续性。

除了在存储层实现数据分散外，保障数据库在高并发冲击下生存的另一项决定性能力是**背压**（Backpressure: 系统在过载时主动抵抗并向调用方反馈阻力以防崩溃的自我保护机制）。业界广泛使用的传统数据库系统（包括 **MySQL**、**PostgreSQL** 以及 **SQLite**）在底层机制上天生缺乏针对极端超载的自我防御能力。当海量并发连接瞬间涌入时，传统数据库往往因计算资源耗尽或连接池被打满而瞬间锁死崩溃。背压机制的核心设计哲学是赋予系统“主动抵抗与反向施压”的能力：当系统监测到处理能力逼近红线时，不再盲目接收无休止的外部请求，而是主动向调用客户端发出阻断与节流信号，明确告知系统已过载并要求客户端降低请求速率。通过分片实现负载分散，通过背压建立自卫防线，系统才能在不可预知的业务峰值中构筑起坚不可摧的韧性屏障。

<details>
<summary>Original English Source</summary>

So let's take a few minutes to talk about how we scale these systems, and probably what you're most interested in— AI agents, which we'll get to at the end. So one of the key things, and this is something we do a lot at Planet Scale, is sharding. Oh, I just realized my mouse cursor is on the screen. Let me remove it from the screen. Let's see if it disappears later.

So, database sharding, what is it? Instead of relying on a single node that works well when you have 10GB of data, but not so well when you have 10TB, 100TB, or a petabyte of data. So what should you start doing? You need to distribute your data and queries across many servers, which is what all those shards below are for. Usually you set up a proxy, and we'll talk about what VTGate is, which intelligently distributes all user requests or database queries between all these servers. And that's exactly what we often do for some of our larger clients at Planet Scale. We perform sharding through Vitess for MySQL and Nicky for Postgres. This is a very fundamental way of sharding, but the thing is, you don't use sharding as a stand-alone solution. If we look here and see, for example, shard A in this block, you actually need a backup system. So, you should have one master server and multiple replicas. Then, if one of the servers fails, that individual shard will be able to recover on its own and get back up and running very quickly in the event of a problem. This is one way we see it, and probably the most common and efficient way to scale databases, but the principle of “distributing queries and data across many servers, nodes, and disks” is applicable to many other parts of your stack.

Back pressure. This is another aspect that is a combination of scalability and reliability. We mean that there are many systems, like MySQL, Postgres, and SQLite. These are very popular databases that people use, but they don't handle overload situations well. So if you send a lot of queries to them, their performance can degrade quickly, and they can basically crash. And that's usually where people's applications start having problems. So you want to design a system with the concept of backpressure. Back pressure is the design of a system with the ability to resist; when I find that too many requests are coming in, I want to be able to tell the client, "Hey, you are sending too many requests, slow down, stop doing that, reduce the number of requests." This is a very, very common and very important principle for scaling systems.

Now let's move on to the next one: compute partitioning. So we've talked about data partitioning, right? But what about compute? There's this idea that you have a single node running your app, but with compute partitioning, you break down different parts of your application and deploy them to different servers so that no one has to deal with the struggle for resources. So if you suddenly have a spike in job queues and you need to scale the queues, but nothing else needs to be scaled, it wouldn't be a bad idea to independently scale the compute resources for each part of our backend that powers your favorite application. So that's the idea of ​​compute partitioning.

And finally, something that's really, really, really important, and something that we think a lot about at Planet Scale, is schema changes. And that's something we'll talk about. So this is not a complete list. What have we already covered? We discussed sharding, backpressure, and now we're talking about partitioning.

</details>

### 声明式分片建模：赋予 Agent 架构设计力

在分布式系统的扩展图谱中，除了数据存储层面的切分外，**计算资源分区**（Compute Partitioning）同样是解耦系统压力的核心手段。若将整个后端应用捆绑在单一节点上，各个业务模块将陷入无休止的硬件资源争夺。通过将不同功能模块拆分并独立部署在专属计算实例上，团队能够实现按需弹性扩展。例如，当后台异步作业队列遭遇突发流量洪峰时，系统可以独立对队列处理算力进行横向扩容，而完全不会侵占其他核心服务的 CPU 与内存资源，从而在计算层彻底切断了资源争夺引发的雪崩隐患。

然而，在建立高可用和强扩展架构的演进道路上，最大的工程风险在于**数据库模式变更**（Schema Changes）。当前由 AI 辅助乃至完全由 AI Agent 编写、测试代码已经成为行业新常态，许多开发者甚至不再亲手撰写业务代码，而是转为调度 Agent 达成目标。但如果直接将权限扩大，允许 Agent 自主执行数据库配置修改、底层分片或 DDL 结构变更，其潜在风险将是毁灭性的。在应用代码层犯错尚可通过快速版本回滚来挽回，但在底层数据库中，一次灾难性的模式变更错误往往无法通过简单的“撤销键”瞬间复原，它会立即导致整库锁死或数据损坏，引发全站服务不可用并波及所有终端用户。

为了化解这一矛盾，系统必须向开发者与 AI Agent 暴露具备强容错性的抽象原语。借助底层强大的开源分布式数据库项目 **Vitess**，PlanetScale 实现了对大规模 MySQL 分片集群的高度托管，其核心组件 **VTGate** 作为智能代理层，能够高精细度地解析 SQL 请求并无缝路由至对应的物理分片。尽管底层分布式运维极其复杂，但上层暴露给开发者的配置界面却被精简到了极致——即 **VSchema**（Vitess Schema: 以 JSON 格式声明分片键、路由策略与表分布的模式配置文件）。
* **JSON 声明式配置**: 开发者或 Agent 只需在一个标准的 JSON 文件中明确指定：“当前数据表以哪一列作为分片键（Sharding Key），采用何种哈希路由算法，以及哪些表应当分布在特定分片上”。
* **Agent 原型设计闭环**: AI Agent 天生极度擅长解析与生成结构化的文本及 JSON 配置文件。团队可以直接向 Agent 提供现有表结构上下文并下发任务：“当前数据库遇到了扩展瓶颈，请根据数据模式为我设计一套优雅的 VSchema 分片原型”。
* **API/CLI 一键下发生效**: 经过推演验证后的 VSchema 配置，能够直接通过 PlanetScale 的开放 API 或 CLI 命令行工具推送到平台。底层复杂的 Vitess 基础设施将自动接管后续所有分片系统的创建与调度，将极其晦涩高深的分布式数据库架构转化为任何工程师与 AI 都能轻松驾驭的标准化工具。

<details>
<summary>Original English Source</summary>

There are many other aspects of scalability, and again, you can spend your entire career becoming an expert in this area. We work reliably, providing fault tolerance and high scalability, but today in my talk I wanted to focus on how we can combine this with AI agents, right? Because they are the ones writing code for us, but at the same time they are interacting with the lowest levels of our infrastructure. Databases, queues, things that power every other level of your stack. And that can be a little scary, because it's practically become the standard these days, right? Write code using AI. In some cases, people don't even write a single line of code themselves anymore, right? The AI ​​actually writes all your code, tests it, and you just direct these agents to perform tasks. But it’s a completely different thing to say, “Now I’m also going to give my agents the ability to deploy changes to the database, change its configuration, or perform sharding, right?” Because if you make a mistake here, it's usually impossible to just hit the undo button, right? This will disable your entire application, and every user will notice it. So we want to do it efficiently and safely. So I'll go back to a few concepts I talked about earlier and consider how to use agents to solve this problem.

So, let's get back to sharding. I will tell you more about Vitess— it is an open source project. We manage Vitess databases for our clients, and it works with MySQL to implement sharding. So, as you can see here, all these shards down there are MySQL databases, and VTGate is a proxy, an intelligent proxy, that takes MySQL requests, parses them, determines which shard they should go to, and routes all these requests in a very sophisticated way. The software is quite complex, but the interface we provide for defining how you want all your queries and data to be distributed across shards is actually quite simple. This is what we call a VSchema, and it's literally a JSON file where you specify, "Here's the column I want to shard by, and here's the way I want to do it." And you can specify which tables should be placed on which shards, having full control over where and how everything is configured. And the great thing is, as we all know, AI agents work great with things like text files and JSON files. So you can give your agent a task and say, "Hey, I'm having problems with the scalability of my database. Here's my schema. I want you to help me prototype a good schema, okay?" And once you've designed and engineered something, thought through and decided on the most efficient ways to shard on a platform like PlanetScale, you literally plug it in, deploy it, and we'll give you an interface to create new sharded systems and scale your database. A lot of this can happen either through AI or by allowing AI to take control of these processes through our API and the command line interface that we run. So, this is one of those things, right? There's actually a very complex infrastructure under the hood that scales your systems, but you provide the right interfaces for it, like simple configuration files, and these things become much more accessible to any company trying to scale.

</details>

### 流量治理与预算：抵御 Agent 并发洪峰

在 AI 驱动的技术生态中，系统面临的最直接挑战往往是调用端流量的骤然失控。以开发领域的代表性平台 **GitHub** 为例，其官方公开透露，在原先已然极其庞大的访问基线上，系统流量再度激增了 2 倍、3 倍乃至 4 倍，且新增负载几乎全由高频并发的 AI Agent 调用所驱动。面对在节假日或深夜依然持续冲刷系统的自动化流量洪峰，即便是全球顶级的工程架构也随时面临被推向过载边缘的严峻考验。

为了将此前阐述的“背压”理论落地为可执行的工程实践，PlanetScale 提出了系统级的**流量治理方案**：
1. **流量打标与分类识别**：通过**流量控制**（Traffic Control: 对流入数据库的所有查询流量进行打标签、分类识别与分流的治理系统），平台对流入数据库的每一笔 SQL 请求进行特征解析与标签注入，清晰区分人机交互流量、后台分析任务与各类型 Agent 自动化任务。
2. **多维度资源预算调度**：建立精细化的**资源预算**（Resource Budget: 针对特定流量切片限制其 CPU 占用或进程资源上限的配额计划），针对被标记的特定流量切片设定绝对消耗红线。例如明确规定：“该特定 Agent 流量分组在任何运行周期内，所占用的 CPU 算力或服务器进程资源严禁超出指定限额”。
3. **阶梯式降级与主动熔断**：监控引擎会动态捕获超出预算的请求轨迹。当流量初现超标苗头时，系统首先实施平滑性能抑制，向调用客户端主动抛出明确的过载告警（例如：“系统当前已进入超载状态，调用方必须主动降速降频”）；若客户端未能及时收敛流量且系统整体健康度受到实质性威胁，底层背压防线将触发最为严格的熔断策略——直接主动终止（Kill）并拒绝正在执行的超限请求。

在系统治理的设计哲学中，主动拒绝请求或强行杀掉查询固然不是最理想的用户体验，但相比于坐视整个数据库集群被流量洪峰彻底击垮并导致全量业务瘫痪，果断实施主动熔断与局部降级是守护全局稳定性的必然选择。

<details>
<summary>Original English Source</summary>

Um, one more thing, this relates to the back pressure concept we talked about earlier, right? So when the database is overloaded, and as you can imagine, this probably happens all the time at some of these companies, right? I think there was a tweet from GitHub a few months ago that said their traffic had increased two, three, or four times from what was already an extremely high load, and almost all of that was driven by AI agents, right? So, they already had a gigantic infrastructure because they are the most popular place in the world to develop, and then they got a multi-fold increase in traffic, especially during the holidays, right? Because of these overloaded systems.

So, how do we deal with this? One of our solutions, and the way we like to think about it, is that we provide users with a system called "traffic control" that allows you to essentially classify and label all the traffic coming into your database, and then you create resource budgets to say, "Hey, this segment of my traffic can't exceed this amount of CPU or server process resource usage." And again, we perform a smooth performance reduction when this happens. So what I'm showing here is a budget schedule that I've set up to say, "Don't exceed these resource amounts and warn me if I start to exceed these resources." So it shows me the number of requests that exceed your budget over time. And we, we, we send a warning to the client, like, “Hey, I’m overloaded. You need to slow down." And we can make it even stricter, where we actually kill those queries that are running, right? And this is one of those things where, well, it's not ideal to reject requests, but it's much better than having your entire application crash and become inaccessible to all your users.

</details>

### 零停机模式迁移：Agent 数据库交付闭环

现代软件研发的标准范式早已建立在以 Git 为代表的版本控制流程之上：开发者从主分支切出特性分支、在本地或隔离环境完成代码编写与测试、发起合并请求（Merge Request），最终动态部署至生产应用。在当前 AI 深度渗透的工程体系中，Agent 同样是沿着这套成熟的心智模型推进代码生成的。然而，软件开发从来不仅仅关乎代码本身，应用层每次新增业务特性，几乎都不可避免地伴随着底层数据库模式（Schema）的同步演进——包括新增数据表、添加或删除字段、创建特定查询索引等。长期以来，传统的数据库 DDL 变更始终是生产运维中最危险的阿喀琉斯之踵，极易引发长时间锁表、复制延迟乃至生产事故。

为了彻底消除这一系统断层，PlanetScale 将 Git 级别的开发体验完整映射至数据库管理中：
* **数据库分支**（Database Branching: 基于隔离副本进行模式修改与验证的独立数据库环境）：依托 Vitess 的底层虚拟化与路由能力，开发者或 Agent 能够像切 Git 分支一样为生产数据库秒级创建独立分支，在完全隔离的环境下安全验证模式修改。
* **部署请求**（Deployment Request: 在生产环境零停机且不锁表合并模式变更的安全机制）：当分支验证通过后，通过发起部署请求，底层在线 DDL 机制会在后台完成数据同步与影子表构建，在业务全量运行且**零停机**（Zero Downtime）的前提下无缝切换生产结构。
* **一键无损撤销**（One-Click Revert: 模式变更发生异常时秒级回滚至历史结构且不丢失新增数据的防御能力）：倘若新结构上线后发现意外缺陷，平台提供了一键撤销能力，系统能够瞬间安全回退到先前的模式状态，且在此期间生产环境产生的任何业务数据均完好保留、绝无丢失。

这一系列高可用原语不仅革新了人类工程师的运维体验，更通过完整的 API 与 CLI 命令行接口向 AI Agent 彻底开放。Agent 在自动化编写代码、拉取分支、发起合并的同时，能够同步在数据库层创建镜像分支、验证模式变更并提交部署请求。无论团队是处于严格的**人机协同**（Human-in-the-loop: 由人类工程师审核把关 AI 变更提案的协作模式）阶段，还是迈向高度自动化的无人值守交付，底层均具备了现成的安全防线。真正的**开发者体验**（Developer Experience）绝不仅限于暗黑主题切换或语法高亮等表面细节，其实质是为背负企业基础设施重任的工程师提供根本性的防错与治理原语。历经多年磨砺所沉淀出的高可用基石，最终在 AI 时代成为了让 Agent 安全、可靠地驾驭数据库并实现弹性扩展的最高准则。

<details>
<summary>Original English Source</summary>

Uh, and finally, one more thing I want to talk about, and I know I'm showing the PlanetScale interface here, but it's not even about PlanetScale itself, it's about the philosophy of how we do these things with agents, which is— most developers are used to using a Git-like process during development. And that also applies to your agents, right? You have a master branch, you create branches, make changes to the code, merge them, and deploy it dynamically to where your application is deployed. What we did, and this was long before agents, was we wanted to take that same UX and replicate it for your database, because often when you build new features in an application, you also make changes to the schema. You add tables, columns, delete items, add indexes, you do all of this to your database to keep it in sync with the codebase.

So what we give you, using the same Vitess that we mentioned earlier, is the ability to create branches of a database schema, make changes to that schema in an isolated environment, and then merge that back into the production environment using what we call a deployment request, all without downtime. And not only that, but also the ability, you can see it down here, the ability, if you've deployed a schema change and you see a problem, we give you a one-click ability to undo it and go back to the previous state of your database without losing any data. Uh, and so that's something that's been great for people, but we also have an API and a CLI to allow agents to automate this. So when they do things, automate code, create branches, do merge requests, and check in code, there can be an actual mirrored state of the database that works in sync with all of these things, right? And it can be either fully automated or semi-automated. Obviously, many of us are operating in a “human in the loop” mode, where humans are still checking all these changes that AI agents are making, and that’s a good thing. But we already have ready-made primitives for building these systems.

There are still a lot of things I didn't have time to talk about, but the main summary I want to make is: we are a company, and I know many are trying to focus on the developer experience right now. And when I say “developer experience,” I don't just mean dark or light theme toggles, convenient keys, or anything like that, but a real-world experience: are we giving the developer responsible for the company’s database or infrastructure the tools to avoid mistakes, deploy systems safely, speed up the database, and improve its performance? We've been building these things for years, and it turns out that when you focus on the developer experience, you end up with great primitives that allow AI to work with the database safely and reliably and help it scale. Since we provide access to many of these tools through command-line interfaces, there are of course debates about which is better for working with AI, but by opening these capabilities to both sides, it provides a great experience for managing the database and interacting with AI agents. So, that's all I wanted to say. Thank you to everyone who came. I'm Ben, and I wish you a wonderful rest of the conference.

</details>