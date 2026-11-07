---
author: The MAD Podcast with Matt Turck
date: '2026-10-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=74X0DJOVEc8
speaker: The MAD Podcast with Matt Turck
tags:
  - database-systems
  - ai-agents
  - vector-search
  - data-modeling
  - db-automation
title: 智能体时代的数据库：从向量检索到自主管理的演进与挑战
summary: 本文探讨了数据库在AI智能体时代的演变，指出向量数据库已融入主流系统，智能体开始自主创建和管理数据库。文章分析了DBA角色的转变，强调数据建模的重要性，并讨论了ClickHouse等厂商在生态建设上的竞争策略。
insight: ''
draft: true
series: ''
category: data-engineering
area: tech-engineering
project: []
people:
  - Andy Pavlo
  - Matt Turk
companies_orgs:
  - ClickHouse
  - Carnegie Mellon University
  - Databricks
  - Snowflake
  - Neon
products_models:
  - PostgreSQL
  - Linux
  - FreeBSD
media_books:
  - MAD Podcast
status: evergreen
---
<!-- chunk 1/11 -->

### 狂野西部：当 AI 智能体闯入数据库世界

**Andy Pavlo**：文件系统到底是什么？它其实就是一个数据库，对吧？世间万物归根结底都是数据库。现在每个月都能听到这样的新闻：某家公司的生产环境数据库直接被删没了，只因为 AI 智能体删错了东西。对于那些不懂数据库演进历史的人来说，现在的局面简直就是一片法外之地的“狂野西部”。这就像是给一只猎豹灌了一大堆可卡因，然后把它塞进一辆法拉利跑车里一样疯狂。人们开发和推进这些技术的速度实在是太骇人听闻了。

<details>
<summary>Original English</summary>

**Andy Pavlo**: What is a file system? It's a database, right? Everything is a database. Every month there's a story where someone lost their production database because the agent deleted something. It's the wild west for people that don't know the history of databases. It's just like, you know, taking a cheetah, giving a bunch of cocaine, and putting in a Ferrari. Like, the amount of speed that people are developing these things is insane.

</details>

**Matt Turk**：刚才那番话出自 Andy Pavlo。在数据库的世界里，Andy 的地位可以说是无限接近于“神”一般的存在。作为卡耐基梅隆大学（Carnegie Mellon University）的教授，他的数据库课程不仅教会了整整一代软件工程师，事实证明，如今连各大 AI 模型也是学着他的课长大的。前不久，Andy 宣布加入 ClickHouse 并创立 ClickHouse Labs，在业界掀起了不小的波澜。就在不久前，人们谈到数据库与 AI 的交集，指的还只是向量检索和 RAG（检索增强生成）；然而在今天，智能体已经能够自主创建数据库、写入数据，甚至有时候还会把数据库给删了。欢迎收听《智能体时代的数据库》。我是 Matt Turk，这里是 MAD Podcast。Andy，欢迎来到节目！

<details>
<summary>Original English</summary>

**Matt Turk**: That is Andy Pavlo. In the world of databases, Andy is about as close to a god as it gets. The Carnegie Mellon professor whose courses taught an entire generation of engineers about databases and, as it turns out, the AI models too. Andy recently made some waves by joining ClickHouse to found ClickHouse Labs. Now not long ago databases in AI meant vector search and RAG, but today agents create databases, write to them, and sometimes even delete them. Welcome to databases in the age of agents. I'm Matt Turk and this is the MAD Podcast. Andy, welcome.

</details>

**Andy Pavlo**：嘿，Matt。你好啊，兄弟！

<details>
<summary>Original English</summary>

**Andy Pavlo**: Hey, Matt. How are you doing, man?

</details>

**Matt Turk**：我很好。对于接下来要聊的一切话题，我都无比兴奋——AI、智能体、数据库，还有 Larry Ellison。我们必须聊聊他。当然还有武当派（Wu-Tang Clan）。

<details>
<summary>Original English</summary>

**Matt Turk**: Good. I'm excited to talk about all things AI, agents, databases, Larry Ellison. We have to. And then Wu-Tang Clan.

</details>

**Andy Pavlo**：武当派肯定是要聊的。呃，不过我们真的一上来就要聊 Larry Ellison 吗？我的意思是，一开场就拿他开刀是不是有点太早了？虽然他确实挺有喜感的，因为在数据库领域里，他就像个超级大反派一样，甚至还在夏威夷买下了一整座岛屿。

<details>
<summary>Original English</summary>

**Andy Pavlo**: We definitely do Clan. Uh, do we have something about Larry Ellison? I mean, it's like a little early to come out of the gate. Although, he is hilarious cuz he's like the super villain with databases. Like he owns a Hawaiian island.

</details>

**Matt Turk**：好吧，看来这套作风对他来说还挺奏效的。

<details>
<summary>Original English</summary>

**Matt Turk**: Well, that seems to be working out for him.

</details>

**Andy Pavlo**：确实如此。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yes.

</details>

**Matt Turk**：好的。那我们可以把关于 Larry Ellison 的讨论留到播客后面一些。

<details>
<summary>Original English</summary>

**Matt Turk**: All right. Well, we can graduate uh to talking about Larry Ellison later in the conversation.

</details>

**Andy Pavlo**：不过我得先声明一下，我跟 ClickHouse 签的合同里确实允许我公开调侃 Larry Ellison，我敢肯定合同里白纸黑字写着这一条。

<details>
<summary>Original English</summary>

**Andy Pavlo**: I will say my contract with ClickHouse does allow me to talk about Larry Ellison. I'm pretty sure that was in writing.

</details>

### 从向量检索与 RAG 到智能体时代

**Matt Turk**：太棒了！那我想先从最基础的脉络切入。大约两年前，“数据库与 AI”这一话题刚刚成为焦点。当时掀起了一股专用向量数据库的热潮，大家都在谈论必须配合聊天机器人的检索需求去做 RAG。那差不多是两年前的光景。我认为很多人对于数据库和 AI 结合的心智模型，基本上就停留在了那个阶段。但显然，我们如今已经步入了智能体（Agent）的时代。这与之前究竟有什么不同？它又带来了怎样的改变？

<details>
<summary>Original English</summary>

**Matt Turk**: All right. Awesome. I want to take it from uh the the top. So um two years ago the topic of databases and AI uh came up. Uh there was a whole era of vector databases and this whole idea that uh you need to do RAG in connection with chatbot searches. That was kind of two years ago. I think a lot of people's mental models kind of like stopped there in terms of like this intersection of databases and AI. Clearly, we are in the age of agents now. Uh how is that different? What does that change?

</details>

**Andy Pavlo**：说到专用向量数据库，虽然你说得没错，如果仅从它们进入大众视野、成为 AI 与数据库领域的时代思潮（Zeitgeist）来看，RAG 和向量数据库确实是在两年前左右才彻底火起来的。但实际上，很多向量数据库本身早在 2016 年左右就已经诞生了。只是到了那个节点，它们的用武之地才突然变得显而易见，因为人们可以用它们来强化和提升聊天机器人的表现。

<details>
<summary>Original English</summary>

**Andy Pavlo**: I mean the vector databases although you're right that like the in terms of being in the zeitgeist of AI and databases. Yeah. Probably two years ago is when the RAG vector data sort of came into play. But the vector databases themselves like a lot of them were around since like 2016. It's just now that like the the use for them became obvious because you can use them to to to to enhance and improve uh you know a agents doing things.

</details>

**Andy Pavlo**：因此我认为向量数据库市场非常有意思。虽然它们在该领域布局很早，并且极力鼓吹这种理念——即用户需要的是基于高维向量或嵌入（Embedding）进行近似相似度搜索（Approximate Similarity Search），而不是传统数据库系统一直以来做的那种精确匹配检索。这种搜索在处理自然语言时确实极具优势，因为在自然语言语境下，你所要寻找或查询的目标语义往往无法被精确形式化定义。比如你想查询：“帮我找出纽约市所有涉及某种特定行为题材的歌手专辑。”你很难用精确的条件去定义这究竟是什么；而向量数据库中近似最近邻检索（ANN Search）或向量嵌入检索的神奇之处就在于，你可以完全依据查询目标的语义含义去检索，整个过程自然而然就跑通了，因为你根本不需要做精确的关键词匹配。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So I think the the vector database market is interesting because they were early in the in the space but but they were really pushing the idea that you want to do this you know a the approximate similarity search on vectors or embeddings instead of doing an exact search that database systems have traditionally done. And this helps too when you're dealing with natural languages that where the the semantics maybe what you're trying to look for or query against isn't you can't precisely define like find me all the the albums in in you know from from artists in New York City that talk about doing you know certain certain kind of activities right it's very hard to define exactly what that is and the the the magic of approximate nearest neighbor search or these vector embedding searches in a vector database is that you can you can look up things based on the semantics of of the thing you're looking for and just sort of it works out that way because you're not trying to do exact keyword searches.

</details>

**Andy Pavlo**：所以到了 2023、2024 年聊天机器人爆发之时，当所有人都突然意识到这项技术的存在时，向量数据库恰好处在绝佳的时间窗口，因为它们可以直接用来增强和改进这些聊天机器人。然而，向量数据库所谓的“护城河”其实并没有那么深，因为归根结底，向量检索本质上只是一种索引技术。不到一年时间，几乎所有现有的传统数据库厂商都在自己的产品中内置了专用的向量索引。如今，支持向量索引已经变成了整个行业的标准和准入门槛——我们正在使用的每一个现代数据库系统几乎都配备了自己的向量索引能力。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So when you know chatbot 2024 2023 when again when everyone became aware that this is this is now a technology that exists um the vector databases were in the right position at the right time because they they could augment and improve these these chatbots but like the the moat if you will wasn't that big because the end of the day it's just an index and within a year pretty much every single database vendor had their own vector index and now it's become sort of standard table stakes like every database system that we're using has their own vector index.

</details>

**Andy Pavlo**：当然，这并不是说专门的独立向量数据库在某些特定场景下就不能比传统数据库做得更出色。但现状是，通用的基础向量检索功能现在大家全都具备了。因此我认为，在当下的技术实践中，你依然会使用向量搜索来增强和改进聊天机器人或现在的智能体；只不过，你不再需要专门为了这一项功能而单独引入一个只能做向量检索的独立专用数据库了。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Um, now it doesn't say that the vector databases can't do certain things better than what the, you know, a traditional database system could do. It's just now that everyone has the that basic functionality. So I think that you still use vector searches to enhance and improve the the chat bots or the agents now. It's just the you don't need to have a specialized one database that that that can only do that.

</details>

### 智能体不仅读取，更在创建与分支数据库

**Matt Turk**：而现在的智能体不仅能使用数据库，它们甚至还会自主创建数据库，并对数据库进行修改。比如大概一年前 Databricks 收购 Neon 时，就曾披露过这样一组统计数据：由智能体自主创建的 Neon 数据库比例，直接从 30% 飙升到了 80%——

<details>
<summary>Original English</summary>

**Matt Turk**: and agents uh now uh create databases, use databases, can make changes to databases. So maybe a year ago when Databricks acquired Neon, there was this stat uh that I believe said that uh the number or the percentage of agents creating neon databases went from 30% to 80%

</details>

**Andy Pavlo**：——甚至可以说，由智能体创建的数据库数量已经彻底压倒了其他所有人类创建的规模。

<details>
<summary>Original English</summary>

**Andy Pavlo**: or the databases created by agents was like was larger than everything else.

</details>

**Matt Turk**：请帮我们深入拆解一下这个现象。这意味着什么？智能体创建数据库究竟代表着什么？或者换个角度问，智能体到底为什么首先需要去创建一个数据库？

<details>
<summary>Original English</summary>

**Matt Turk**: Unpack that for us. What what does that mean? an agent creating a database or why does an agent need to create a database in the first place?

</details>

**Andy Pavlo**：这里有两种情况：一种是从零创建全新的数据库，另一种则是对已有数据库进行分支（Branching）。我认为当时公布的那个统计指标，主要指的其实是由智能体创建的数据库“分支”。那么，数据库分支到底是什么意思呢？分支指的是，当你拥有一个现有的数据库时，你可以对它进行某种写时复制（Copy-on-Write）的快照操作，使其在外部看来就像是两个完全独立的数据库一样。

<details>
<summary>Original English</summary>

**Andy Pavlo**: The creation of a database and then there's branching of an existing database and I think the database metric was about like the the branches being created by agents. Um so so what does branching mean? So branching is when you have a you have you have a database system or sorry a database and you want to make a sort of copy on write snapshot of that that the database and have it look like two unique databases.

</details>

**Andy Pavlo**：你之所以想要这样做，是因为你线上运行着支撑业务与应用程序的生产数据库——那是所有业务记录的核心系统，所有真实数据变更都汇聚于此。但与此同时，你希望人类开发者或者 AI 智能体能够开始尝试新功能、对应用程序进行代码迭代。并且你强烈希望他们能在真实的数据库环境上进行操作和验证。因为在以往传统的开发流程中，你通常只能对数据库做数据转储备份，或者搞一个缩水版的小型抽样数据库，因为全量复制成本实在太高了。以往大家只能在暂存环境（Staging）或开发环境数据库中验证，然后祈祷这些变更推到生产环境并面对大规模数据时一切顺利。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Um, and the reason why you want to do that is you could have your production database that's running your your business, your application, like where all your your you know the system of record, all your changes are going into, but then you want to have either a human developer or an agent be able to start trying out new things, make changes to the application and you want them to operate on the real database because often times traditionally you would make copies of the database or have a smaller version of of the database like a sample what would already exist there because it's just too expensive to to copy things around. So you have like a staging or development uh uh database and then you would then hopefully apply your changes to the production database and hope things that once you go to the larger scale everything works out.

</details>

**Andy Pavlo**：而数据库分支能力带来的改变在于：它允许你直接对真实的生产数据库创建一个轻量快照，你接下来所做的所有修改都只会写入到该快照中，完全不会影响生产数据库本体。一旦你在该快照上充分验证了所有的变更——通常重点不是验证数据本身，而是验证数据库 Schema 结构模式或应用层代码——确认一切无误后，你就可以放心地把这些变更正式发布并部署到生产数据库中。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So what branching allows you to do is allows you to make a snapshot of the real database have all the changes that you make go to the snapshot and not affect the production database. And once you're okay with the changes you've made, maybe not necessarily with the data, but usually for like the schema or the application code, once you know you've vetted on the snapshot, then you can put it live in the production database.

</details>

**Andy Pavlo**：如今有了这些智能体之后，人们正在大规模拉起编程智能体（Coding Agents）来编写新功能、重构应用程序的各个模块。写代码这件事已经不再由人类亲力亲为了。既然人们希望这些智能体去迭代代码，就必然希望智能体能在数据库副本上验证自己的修改结果，因此你就可以为它们创建数据库分支。此外，这在自动化测试场景中也非常普遍。很多时候，这些分支都是在 GitHub Actions 运行 PR 流程或自动化测试套件时动态拉起的。你显然希望测试代码是在独立的数据库副本而非线上环境里运行。因此，这种分支能力目前主要用于开发和测试流程。人们正借助智能体编写巨量的代码，因此必须为它们提供完全隔离的沙盒环境去运行，为数据库创建快照并分支的能力在这一场景下自然变得极其重要。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So now with these agents, uh people are spinning up um these coding agents to write new features, write new new parts of their application. It's not something humans are doing anymore. And now you want to have these agents, you know, they want to they want to vet their changes on a copy of the database. So you can create branches on those things. often just shows up when you're running testing as well. Like a lot of the times the the the branches are created by um you know PR is running in GitHub actions or testing things like that. So you want to run your tester code on a copy of the database rather than the live one. So it's mostly being this branching capability is used for development. So agents are people are using agents to write a lot of new code and so you want them to run in their own sandbox. You make a snapshot of the database. So the branching capability is super useful for that.

</details>

**Matt Turk**：是的。如果退回到一个更本质、更朴素的层面上来看：智能体之所以需要创建数据库，是因为智能体是要对真实物理世界采取行动的；而如果你让一个智能体去凭空构建一个应用程序，那么应用程序归根结底仍然必须依赖数据库来存储状态。

<details>
<summary>Original English</summary>

**Matt Turk**: Yep. even more sort of simpler level an agent needs to create a database because agents take actions on the world and if you ask an agent to create an application an application at the end of the day still a database.

</details>

**Andy Pavlo**：没错。所以毫无疑问，如果你要求从头开始构建一个应用，你给编程智能体一个 Prompt，告诉它：“给我构建一个能够实现某某功能的应用”，那么它肯定会当场为你创建一个全新的数据库。不过在当下，被大量创建出来的数据库分支，或者说新数据库（如果你愿意这么称呼的话），绝大多数还是为了服务于这种开发和测试迭代。但不管怎么说，无论好坏，现在的智能体确实已经具备了自主创建数据库的能力。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yeah. So, so certainly like if you say like if you create a database from scratch then yes your your coding agent you give it the promise say a billion application does this then yes it will create create a database right away but most of the most of the branches or new databases if you want to call it that being created are for this development but yes the agents can now create databases for better words

</details>

<!-- chunk 2/11 -->

### AI Agent 与数据库安全：删库事件与历史教训

**Speaker A**: 你甚至可能让它们把数据库给删了。人们经常在这上面惹出麻烦，因为 Agent 会去执行那些根本不应该做的事情。

<details>
<summary>Original English</summary>

**Speaker A**: You can have them drop databases. People often get in trouble with this because it's doing things they shouldn't be doing.

</details>

**Speaker B**: 没错，去年就有过类似的事……

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, there was last year as well, um...

</details>

**Speaker A**: 每年都会有这种故事发生。

<details>
<summary>Original English</summary>

**Speaker A**: Every year there's some story.

</details>

**Speaker B**: 比如之前发生过一起非常耐人寻味的事故，在 X（Twitter）上也引发了相当广泛的关注。当时有人试图用 Replit 构建一些应用，结果 Replit 的 Agent 直接进入数据库删除了大量文件。随后 Replit 迅速做出了相应修正。显然，现在这一切还处于“蛮荒西部”（Wild West）阶段，大家都在摸着石头过河，犯错在所难免。

<details>
<summary>Original English</summary>

**Speaker B**: There was some incident that was very interesting and got pretty widely publicized on X for what it's worth. Levin that was trying to build something with Replit, and I think the Replit agent went into the database and deleted a lot of files, which then subsequently Replit made the right adjustments. Obviously all of this is the Wild West and people are learning as they go, and mistakes will be made.

</details>

**Speaker A**: 但这所谓的“蛮荒西部”，只是对那些不了解数据库发展史的人而言。多年以来，我们早就拥有完备的技术手段去防止人们做出违规操作——比如像删表、删记录这种愚蠢的举动。这些访问控制机制早就存在了，只是如今人人都想重新发明轮子，大家非要吃尽苦头才学会遵循过去已有的成熟做法。

<details>
<summary>Original English</summary>

**Speaker A**: It's the Wild West for people that don't know the history of databases. For years we've had the capabilities to make sure people don't do things they shouldn't be, like stupid things like dropping a table or deleting records. Those controls exist. It's just everyone wants to reinvent the wheel, and people learn the hard way of just doing what's already been done in the past.

</details>

### 为 Agent 设立护栏：权限、沙箱与防护机制

**Speaker B**: 我们深入聊聊这一点。这意味着什么？在面向 Agent 的数据库世界里，目前还缺失什么、需要建立什么？

<details>
<summary>Original English</summary>

**Speaker B**: Let's expand on that point. What does that mean? What needs to exist in the agentic world for databases that is not currently in place?

</details>

**Speaker A**: 护栏（Guardrails），对吧？就像你家里有了一个刚学会走路的幼童，你不可能不在楼梯口装上防护栏任由他们摔下楼梯，或者任由他们把手指插进插座里，对吧？对这些 Agent 也是同一个道理。你可以把它们看作幼童——虽然稍微复杂一些，但你绝不能让它们在数据库里为所欲为、随意折腾。

当然，你可以坐在那里时刻盯着它（babysit），像在 Claude Code 之类的工具里那样一遍遍手动点击“批准、批准、批准”；但这样你就无法实现规模化，根本没法让成百上千个 Agent 同时去执行任务。因此，你必须配置合理的权限和访问控制，防止它们跑进生产数据库删掉不该删的表；同样，也不要让它们去读取那些根本没必要访问的数据。

如果你设置了恰当的护栏，无论通过数据库分支（branching）还是其他方式构建出隔离沙箱，就能彻底避免灾难。要知道，现在每个月都会出现某人因为 Agent 删除了某些东西、做了不该做的事而导致生产数据库报废的新闻。只要设置好了护栏，你完全可以确保这种事故不会发生。然而现实中人们往往偷懒，整个公司所有部门全用同一套密码，接着又把这套密码直接丢给 Agent，最后却纳闷为什么 Agent 会做出出格的事。

<details>
<summary>Original English</summary>

**Speaker A**: Guardrails, right? You wouldn't have a new toddler and just not put up the guardrail so they don't fall down the stairs or put their finger in the socket, right? It's the same kind of thing for these agents. Think of them as like toddlers. A little more sophisticated than that, but you don't let them run wild or do whatever they want on a database.

Now you could sit and babysit it and just say approve, approve, approve, like in Claude Code or whatever, but of course then you can't scale and have hundreds of agents trying to do things at the same time. So you want to set the right permissions and controls so that they can't go into the production database and drop tables that they shouldn't be. And likewise you don't have to go read things they maybe necessarily wouldn't want to read as well.

So if you have the right guardrails, and through branching or whatever means you want to create these sandboxes, you can avoid disasters. Every month there's a story where someone lost their production database because the agent deleted something or did something they shouldn't do. With the right guardrails in place, you can assure that these things don't happen. People get lazy, they use the same password across an entire company organization, and then they give the same password to the agent and wonder why the agent started doing things they shouldn't do.

</details>

**Speaker B**: 这些护栏应该和现有的防护机制完全一样吗？

<details>
<summary>Original English</summary>

**Speaker B**: Should those be the same guardrails as what currently exists?

</details>

**Speaker A**: 是的。更核心的问题或许是：至少在现阶段，Agent 的行为模式真的与人类有本质不同吗？除了能够 24 小时全天候运行之外，我还没看到任何证据表明它们开发软件的方式或者操作不准确数据的方式与人类有什么差别。

归根结底，数据系统对外暴露的能力终究是有限的，暴露给你的就是那套 API。只要你能通过这些 API 去约束人类的行为，你也同样可以用它们来约束 Agent。至于这些护栏的高级程度——除了单纯禁止对某张表执行 `DELETE` 或 `UPDATE` 之外——护栏究竟能做到多精密，很大程度上取决于你使用的是哪款数据库产品。

在这里我得说一句：我虽然热爱开源数据库，但那些企业级、商业化的传统数据库早已在历史上为人类开发者做足了这类功课，它们已经具备了你所期望的大多数保护机制，现在只需把同样的能力开放给 Agent 即可。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So maybe the larger question is: do agents, at least now, behave differently than humans? Other than just being able to run 24/7, I haven't seen anything that would suggest the fact that they don't develop software the same way or inaccurate data the same way that humans do, right? At the end of the day, the data system only exposes so much different capabilities, and that's the API that gets exposed to you. So as long as you can constrain those things for a human using those APIs, you could do the same thing for agents.

And the level of sophistication of what those guardrails could be, beyond just like "don't run delete or update on a table," the level of sophistication really matters on what sort of product you're using. And I will say, this is something where, I like open source databases, but the enterprise commercial legacy databases, if you will, they've already done all this for humans in the past, so they have a lot of the protection mechanisms you would want and just expose that to agents as well.

</details>

### 数据库发展史的四个阶段与 Agent 带来的流量激增

**Speaker B**: 明白了。那比起人类操作，是否存在任何本质上的区别？比如你刚才提到的请求吞吐量（volume）与可扩展性（scalability），未来可能会有数十亿个 Agent 同时执行操作，这是否会彻底改变一切以及它们与数据库的交互方式？

<details>
<summary>Original English</summary>

**Speaker B**: Understood. Is there anything that's fundamentally different compared to humans? I think you alluded to volume and scalability. Does that change everything? The fact that you have possibly billions of agents taking actions and how they interact with databases?

</details>

**Speaker A**: 实话实说，我目前也没有确切答案。现在下结论还为时过早。但吞吐量肯定会发生剧变，因为 Agent 能够以人类无法企及的方式 24 小时全天候运转。

不过在数据库的发展历史上，我们以前也见过类似的吞吐量暴涨模式。我认为迄今为止大致经历了三个时代，而我们现在正迈入第四个时代：

第一个时代是数据库刚出现的初期。当时各组织终于可以摆脱纸笔记录，将信息录入系统、执行事务并集中存储数据。大概在 20 世纪 70 年代和 80 年代，数据库需要承载的流量出现了一次显而易见的激增。但在那个时代，主要是在工作岗位上的员工与数据库交互；下班回家后几乎没人使用，因为 80 年代普通人家里根本没有计算机，至少绝没有达到现在的普及程度。这是流量增长的第一个时代。

到了 20 世纪 90 年代和 2000 年代初，互联网横空出世，每个人都可以在家中通过网站和互联网与数据库进行交互。于是我们看到了那个层级的流量峰值，这是第二个时代。

接下来的第三个时代是智能手机移动端。任何时候，每个人的手机里都在运行着各种各样的 App，他们通过 App 与网站交互，不断向数据库写入和读取数据。这是第三个时代。

我认为 Agent 正是这段历史的下一个新篇章：现在不仅是每个人都拥有一部手机，而且每个人还可能拥有成百上千个代表他们行事的 Agent。这些 Agent 会代表用户在数据库中读取和写入数据。归根结底，任何应用程序的底层必然都有数据库作为支撑，这必然会导致应用程序频繁读写信息与数据。

我认为目前我们还没完全进入这一阶段，因为显然不是每个人都已经拥有数百个 24 小时常驻运行的 Agent。但值得关注的潜在演变在于：当人类使用手机或笔记本电脑访问网站或应用程序时，他们基本上只有在醒着的时候才会去操作，而且一个人一次只能做一件事。我不可能一手拿着手机、一手操作电脑，在同一时间内并发做两件事，人类的能力本身就存在物理限制。

但你可以设想这样一个世界：成千上万个 Agent 24 小时永不停歇地运行，模拟人类的行为与外部系统持续交互，这带来的流量规模将出现极其显著的爆发式增长。

不仅如此，与普通的 Web 应用不同——你可能会问：“这些 Agent 和现在的物联网（IoT）设备或智能手机到底有什么区别？” 物联网设备通常只是把采集到的传感器读数单向流式写入；而手机 App 通常以读数据为主；但你可以预见，这些 Agent 将会执行更为复杂的操作，是读与写的紧密结合，这使得访问流量的形态变得更加复杂多变。

因此，我认为击中数据库的查询请求量（query volume）很可能会迎来 10 到 100 倍的爆发式增长。虽然我们目前尚未达到那种极致规模，但我从工业界的朋友那里已经得知，他们开始看到这种势头了，我们在 ClickHouse 也观察到了同样的苗头。

不过我目前尚不确定的是，这种交互的复杂程度究竟会比人类现有的交互更复杂还是更简单。我已经听到一些人分析说，Agent 生成的 SQL 查询类型实际上可能反而更浅显，因为它通常只是试图一次读取一两张表来弄清楚具体状况……

<details>
<summary>Original English</summary>

**Speaker A**: I got to be honest, I don't know the answer, right? It's still early to say. I mean the volume, of course, yet, right, because agents are running 24/7 in a way that humans cannot. But we've seen similar patterns in databases before where we've seen increase in volume.

And I would sort of say there's been three eras, and we're now in the fourth one:

The first one was at the very beginning of just having a database in general, that you can now start putting in information and run transactions and store things for your organization in a way you couldn't before when it was all pencil on paper. So probably like the 70s and 80s, there was an obvious increase in the volume of traffic you need to handle in a database. But in that era it was mostly humans interacting with the database, but at their jobs, because no one would go home and no one had a computer necessarily in like the 80s, certainly not the level we have now. So that was one era where we had an increase in volume.

Then in the 1990s and early 2000s, the internet comes along, and now everyone can interact with databases through websites and through the internet at home. So you saw a spike in volume at that level.

Then the next era would be mobile phones. So now everyone at any given time has various apps running. They can interact with websites, put things and read things from databases. So I would say that would be the third era.

So now agents, I think, is the next chapter in the story, where now every human not only has a cell phone, but now they also can have maybe hundreds of agents interacting on their behalf that are then reading and writing data from a database. At the end of the day, an application is always going to be backed by a database, so that's going to cause the application to read and write information, read and write data.

I don't think we're there yet, because every human obviously doesn't have hundreds of agents running 24/7. But what's interesting about what could happen is, when you think of a human interacting with their cell phone or their laptop on a website or an application, they're kind of really only doing it when they're awake, right? You can only do one thing at a time. Like I can't sit with my one cell phone in one hand and laptop in the other hand and do things at the same time. You're kind of only limited to what the human can actually do.

But you can imagine a world where these agents are just 24/7 always running and acting as if they were humans and interacting with things. So the volume would increase quite significantly.

And then furthermore, unlike a web app, you could argue, "How's this agent really different than IoT devices or cell phones now?" With IoT devices, you're just streaming inserts of "here's the measurements I'm getting." With cell phone apps, you're usually reading data, right? But you can imagine these agents do more complex operations where it is a combination of read and writes, and then that makes the traffic more interesting.

So I think there's going to be potentially a 10 to 100x increase in volume and the number of queries that are going to hit up against databases. I don't think we're at that level yet, but I definitely heard from my friends in industry that they're seeing that sort of thing. We've seen the same thing at ClickHouse.

What I don't know yet, though, is whether the sophistication of the interactions are more or less than what humans can currently do. I've seen some people say the type of queries that the agent would generate, or SQL queries the agent would generate, is actually more shallow because it's just trying to maybe read one or two tables at a time try to figure out...

</details>

<!-- chunk 3/11 -->

### Agent 访问数据库的模式与遥测挑战

**Andy Pavlo**: 数据库里的数据模式，对比比如有人使用仪表板或像 Tableau、MicroStrategy 这样的商业智能（BI）工具，可能会在不同数据表之间执行非常复杂的连接操作（joins）。我目前还不清楚 Agent 是不是已经达到了这种水平，还是说它们只是以更简单的方式尝试对数据库读取数据。

你刚才的问题是：Agent 会改变现状吗？我认为答案是肯定的。目前最明显的改变绝对体现在查询体量上，而且我认为未来还会进一步增长。当然，现在当这些 Agent 运行时，它们自己也在生成专属的遥测数据（telemetry）。因此你必须把这些遥测数据存储起来并加以分析理解，这本身又是另一个挑战。但就它们实际操作的数据访问模式到底有多大不同而言，目前仍有待观察。这也是我自己正在尝试深入研究的课题。

<details>
<summary>Original English</summary>

**Andy Pavlo**: ...what's in there versus like if someone uses like a dashboard or like a BI tool like Tableau or MicroStrategy and maybe doing like very complex joins across the different tables. I don't know yet whether agents are at that level or whether they're kind of going at it reading trying to read data against the database in more simple terms.

So I mean so your question is like are agents going to change things? I think yes. Right now definitely in volume and I think that's going to increase even further. And of course now when the agents are running they're generating their own telemetry. So that you have to store that and make sense of that and that's another challenge. But in terms of like whether the actual patterns of what they're doing how different is that yet? That remains to be seen. This is something I'm trying to research as well.

</details>

### Agent 记忆之争：文件系统还是数据库？

**Host**: 这里面有几个非常棒的点，我等会儿想回过头来继续探讨。不过眼下关于“Agent 记忆”（agent memory）这个概念似乎成了一个交锋激烈的战场：一边主张使用文件系统，另一边则倾向于数据库。对此你怎么看？

<details>
<summary>Original English</summary>

**Host**: Yeah, some fantastic stuff in there that I want to go back to in a minute. But there is a concept of agent memory that seems to be a little bit of a battleground right now with on the one hand file systems and on the other hand databases. What is your view?

</details>

**Andy Pavlo**: 哎，文件系统本质上是什么？它本身就是一个数据库，对吧？世间万物都是数据库。你有一个目录，里面存了一堆 Excel 文件，那就是一个数据库；你拿出一个笔记本、一支铅笔和一张纸，那也是一个数据库。就像我女儿大概三岁的时候，我试图教她数据库的重要性，我就让她写下来——或者说我们一起做——每天把气温记录在一个带横线的小笔记本里，然后她合上本子喊一声“commit”（提交）来保存数据。你看，那就是个数据库，对吧？

归根结底，这取决于你现在想给 Agent 提供的输入或上下文究竟是什么形式。据我所知，目前它们接收的全部都是人类可读的文本。所以，无论这些人类可读文本是来自你目录里的一堆 JSON 文件，还是从某个能将其转换为正确输入格式的数据库系统中提取出来的，到头来本质上其实没什么分别。

但我认为，当你使用一个能够保护数据安全的数据系统时，显然能获得巨大的优势和安全保证。比如 SQLite 在这方面就声名显赫。既然如此，你为什么还要用裸文件系统，自己费尽心思去管理写操作是否正确、安全，以及如何管理多次变更并提交呢？而 SQLite 天生就能把这些事情处理得妥妥当当。所以说到最后，每个人其实都应该把所有东西放进数据库系统里。甚至像 WinFS 这样的某些文件系统，掀开底层来看，它也是个数据库系统。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Oh, what is a file system? It's a database, right? Everything is a database, right? You have a directory of a bunch of Excel files. That's a database, right? You have a notebook, a pencil and paper, that's a database. Like when my daughter was like three, we would—I was trying to teach her, you know, the importance of databases and I would make her write down, well, we'd do it together. We'd write down the temperature every day, you know, in a little lined notebook and then she'd close it and go "commit" to save the data. That's a database, right?

It really comes down to what the form of the input or the context you want to provide to your agents are now. And as far as I know, it's all human readable text, right? So whether or not that human readable text comes from a bunch of JSON files you have in your directory or it's extracted from a database system that can then convert that into the correct input form, at the end of the day, it doesn't matter.

I think that there's obviously advantages and safety guarantees you can get when you use a data system that can protect data. Like SQLite is famous for this. Why would you want to use a file system and try to manage whether you're writing things correctly and safely and that you can handle multiple changes and commit this, versus like SQLite just does it right. So like at the end of the day, everybody should be putting everything in a database system, right? Even some file systems like WinFS underneath the covers, it's a database system, right?

</details>

**Host**: 是的。之前有篇文章也在网上疯传过，如果没记错的话，标题好像就叫《我不小心重新发明了一个数据库》，里面探讨的就是用文件系统做数据存储的问题。

<details>
<summary>Original English</summary>

**Host**: Yeah. There was a piece that also like went viral at some point. I think that was entitled "I recreated a database by accident", talking about like file systems.

</details>

### 多 Agent 协同与共享状态的存储选择

**Host**: 好的，这很有意思。那么多 Agent、子 Agent 以及 Agent 集群（agent swarms）的世界，是否对数据库有更高的刚性需求？我的意思是，它们在计算感知上显得非常复杂，因此在另一端配备一个极其重型的后端系统似乎顺理成章？

<details>
<summary>Original English</summary>

**Host**: Okay. Interesting. Does the world of like multi-agents, sub-agents, agent swarms, does that require more of a database? Meaning like they feel computationally very complex and therefore having something that's extremely heavy duty on the other side seems to make sense.

</details>

**Andy Pavlo**: 归根结底，如果你需要在多台机器或者这些 Agent 的多个实例之间共享状态——无论它们是不是跑在同一台物理机上——数据库管理系统（DBMS）再次提供了这种核心能力，也就是你可以让多个并发读取者共同访问这一共享状态，对吧？

到目前为止，我还没见过在 Agent 的记忆检索过程中，会把过滤条件（filter）等计算逻辑直接下推（push down）到数据库里执行的场景。通常情况下，这些信息都是直接作为上下文打包喂给模型的。这又回到了 RAG（检索增强生成）或者向量数据库那一套做法：你根据此前在数据库文件或数据库自身记忆中检索到的内容，把相关上下文拼装出来。

因此，按照我的理解，目前输入到模型上下文的接口依然只是人类可读的纯文本。这些文本究竟是来自文件系统还是数据库系统，在形式上并没有本质区别；但数据库系统提供了一系列文件系统无法给你的保障和便利，而跨多个 Agent 的共享状态管理，正是其中最核心的优势之一。

<details>
<summary>Original English</summary>

**Andy Pavlo**: In the end of the day, if you need to share state across multiple machines or instances of these agents, whether they're running on the same box or not, like again, a database management system provides that capability is that you could have multiple readers reading the shared state, right?

I haven't seen anything where like agent as part of its memory lookup is you're pushing down like filters and things like that into the database. Usually that's provided as part of the context. Again, this going back to the RAG or the vector database stuff like you provide the context based on what you've already looked up in against your memory in the database files or the database itself.

So again from my understanding is that the API for the input to the context is just human readable text and whether that comes from a file system or a database system it doesn't matter, but the data system provides certain guarantees and luxuries if you will that a file system cannot provide, and shared state is one of them across multiple agents.

</details>

### Agent 生态中的数据库选型与预训练倾向

**Host**: 你有没有观察到 Agent 领域开始向某种特定类型的数据库收敛？我指的是比如用作记忆存储，或者当 Agent 自己编写构建应用程序时，会不会更偏好选择某一个具体的数据系统？

<details>
<summary>Original English</summary>

**Host**: Have you seen the agent world converge towards a specific type of database? I mean asking like in terms of like using it as for memory or having an agent choose one particular data system over another when they build an application?

</details>

**Andy Pavlo**: 更多的是……其实两者都有。

<details>
<summary>Original English</summary>

**Andy Pavlo**: More the—actually both.

</details>

**Host**: 那先聊聊后者吧。

<details>
<summary>Original English</summary>

**Host**: So maybe the latter.

</details>

**Andy Pavlo**: 关于后者，很显然，大模型是用人类写过的海量公开内容预训练出来的。所以，如果你对它说“我正在开发一个新的应用程序”，十有八九它在这个阶段大概率会直接向你推荐 PostgreSQL。

<details>
<summary>Original English</summary>

**Andy Pavlo**: The latter one it obviously they're fed on—the models are trained on what people are writing about and so you know if I say if I'm building a new application chances are it's probably going to recommend Postgres at this point...

</details>

**Host**: 因为预训练语料里全都是这个。

<details>
<summary>Original English</summary>

**Host**: Because that's what in the pre-training.

</details>

**Andy Pavlo**: 确实如此。顺便说一句，具体名字我不能透露，但确实已经有两家数据库商业公司跑来问我：究竟该怎么做，才能让 AI Agent 在推荐数据库时优先推荐他们的产品，而不是首推 PostgreSQL？

我的回答是：首先，这根本不是我的研究领域，这不属于学术科研范畴；其次，别来找我，你们应该去联系那些训练基础大模型的团队。显然他们才是有话语权的人。这本质上就类似于大模型时代的搜索引擎优化（SEO）——你怎么教导 Agent 形成“嘿，我应该使用某个特定数据库 X 而不是 PostgreSQL”的认知偏好？

<details>
<summary>Original English</summary>

**Andy Pavlo**: And I will say—I can't say who—I've had two database companies ask me how to get their database to be recommended first by an agent over Postgres and I was like: that's not first of all that's not what I do, that's not research; and two, like don't talk to me, go talk to the guys building the models. Like that's clearly something that you know they could have sway in. It's basically like SEO: how do you get the agent to learn like "Hey, I should use my database X instead of Postgres"?

</details>

### 检索自引用的困扰与数据库推荐机制

**Host**: 我猜你的文章和著作在各大搜索引擎里被极其高频地索引收录，因此找你“公关”，某种意义上也是在向大模型做定向输出。

<details>
<summary>Original English</summary>

**Host**: I would suspect that your writing is highly indexed by the search engines and therefore pitching you is a way of pitching the model.

</details>

**Andy Pavlo**: 这完全属于典型的“凡尔赛式幸福烦恼”（first world problem），我真不是故意要凡尔赛或者炫耀。但我确实遇到了一个很头疼的问题：每当我向 AI 提问有关数据库的问题时，它总是把我自己的话引用回给我看，因为我所有的课程资料都在网上……

<details>
<summary>Original English</summary>

**Andy Pavlo**: So this is a very much a first world problem and I'm not trying to say like a humble brag, but like one problem I do have is when I ask questions about databases it cites me back to myself cuz all my course materials...

</details>

**Host**: 这从某种角度看，应该还挺有成就感的吧？

<details>
<summary>Original English</summary>

**Host**: Which has to be somewhat satisfying.

</details>

**Andy Pavlo**: 算是吧……但其实并不！因为比如以前我在卡内基梅隆大学教数据库课程时，我会提示它：“我想了解有哪些数据系统实现了某类特定索引机制”，我现在的提问必须变成：“我已经知道哪些系统实现了这个特性，请列出那些‘没有’实现特性的系统。”接着我还得特意补上一句：“不要引用……”

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yes. Well, no, but it's like no because like say when I was teaching database courses, I would say, you know, "Show me I want to learn about data systems that do this version of it kind of index people" or whatever and I would say, so now I have to say like: "I already know which ones do this. So show me the ones that don't do this." And then I have to say also: "Don't cite..."

</details>

**Host**: “不要引用 Andy Pavlo 或者任何卡内基梅隆大学的资料。”但问题在于我们的……

<details>
<summary>Original English</summary>

**Host**: "Don't cite Andy Pavlo or Carnegie Mellon." But then the problem is that our...

</details>

**Andy Pavlo**: 它根本不理会这套。ChatGPT 甚至会回答说：“我知道你就是 Andy，对吧？”它真的会说类似“我知道你是谁”这样的话；不过 Perplexity 倒不会这样。

但更让人头疼的是，我们所有的课程讲义课件全部都是开源的，任何人都可以直接拿去用。所以当我限制它“不要引用卡内基梅隆大学（CMU）”之后，它就会说：“好的，那我不引用 CMU，让我引用另一所大学的资料吧。”然而那其实只是另一所大学在自己的课堂上直接套用了我的 PPT 课件！所以我现在必须把过滤条件写得极其严苛，精准指定哪些内容绝不能返回给我。

回到你最初的问题。我认为对于 OLTP（在线事务处理）场景，虽然我有一段时间没专门测试了，但通常只要你一问，它吐出来的默认建议基本上都是“你应该使用 PostgreSQL”。除非你给出了极具特异性的约束条件，比如“我要在嵌入式设备上运行”，这时它才会转而推荐 DuckDB 或 SQLite；或者你说“我只在乎键值存储性能”，它可能会推荐 RocksDB。但就一般性通用场景而言，它几乎百分之百都会推荐 PostgreSQL，随后如果继续深入对话，它可能会进一步追问你是否需要云托管托管版本。

而对于 OLAP（在线分析处理）场景，看看模型之间是否存在某种排名机制会非常有趣，这确实是个好点子，说不定已经有人在做这类测评了。在分析型场景下，模型的回答会有更多变数，你往往需要进一步细化提示词，比如说明“我的工作负载特征是这样，我的数据规模是这样”，这样它能给出更细致入微的建议。我大概有一年左右没专门测过这个了，但之前我经常能看到它会问：“你有充足的预算吗？如果有，你可以选择 Snowflake 或 Databricks；如果没有预算，你可以考虑 DuckDB；或者如果你需要本地私有化部署，你可以选用 ClickHouse”等等诸如此类。

至于你的第二个问题，关于 Agent……

<details>
<summary>Original English</summary>

**Andy Pavlo**: ...doesn't reply. You know, "I know you're Andy, right?" Yeah, actually says like: "I know who you are." It says I've said something like that, but Perplexity doesn't do this.

But the problem is also too is like says our all our course material is open source so anybody can just take and use it. So then it says: "Okay, well you can't cite Carnegie Mellon University. Let me cite another university." But it's just my slides being reused at another course. So I gotta be like very specific about what not to return back to me.

So I think that, I mean to your original question, like I think for OLTP, I haven't tried this in a while, but usually it spits back: "Hey, we should use Postgres", unless you say something like very specific like, you know, "Oh, I'm going to run on embedded devices", then it'll say use DuckDB or SQLite or something like that. Or "I only care about key values", it might come back and say like use RocksDB. But in terms of general use it almost always says use Postgres, and then it might recommend like "Do you want a hosted version or not?", right, if you have further chats.

For OLAP, it'd be interesting to see if there's any kind of ranking on this. It's actually not a bad idea, maybe somebody's already done this. But like that one it definitely would come back and maybe you have to refine it further and say like: "My workload looks like this, my data looks like this", and then I think it can give a more nuanced answer. I haven't tried this for about a year or so, but I've definitely seen before like it say: "Oh, you know, do you have any money? Yes, okay, you could use Snowflake or Databricks. Do you have no money? Okay, you could use DuckDB. Or you know, do you want to run on-prem? You could use ClickHouse", things like that.

And then your second question was about agents...

</details>

**Host**: 那么究竟该推荐哪一款呢？这就是关键所在……

<details>
<summary>Original English</summary>

**Host**: Well, which one should they recommend? So that's the...

</details>

<!-- chunk 4/11 -->

### 图数据库与上下文层的选型考量

**嘉宾**：……关于他们究竟推荐哪一个的答案，不过……

<details>
<summary>Original English</summary>

**Guest**: ...answer to which one they do recommend, uh, but uh...

</details>

**主持人**：那我应该推荐哪一个呢？对，我之所以问到这里，部分原因在于——你知道，关于速度的问题，而这正是 ClickHouse 大显身手的地方，我们稍后会更详细地讨论 ClickHouse。此外，可能还有关于上下文层（Context Layer）和本体（Ontology）的概念，目前似乎都在朝着图数据库（Graph Databases）的方向推进。图数据库真的合适吗？到底什么样的方案才合理？

<details>
<summary>Original English</summary>

**Host**: Which one should I recommend? Yeah, and where I'm going with this partly is, you know, this question of speed, and that's where ClickHouse shines, and we'll talk about ClickHouse more later. This perhaps a concept of, you know, context layer ontology, which seems to be pushing towards graph databases. Are they... you know, what makes sense?

</details>

**嘉宾**：我对图数据库有非常强烈的个人看法。我认为大家根本不需要图数据库。据我所知，至今没有任何基准测试表明，原生的专用图数据库在性能上能超越关系型数据库系统——前提是这些关系型数据库在 SQL 或 API 中具备正确的构造支持，允许你在服务端完成所有的图遍历操作，而不是在客户端和服务端之间来回频繁交互。

<details>
<summary>Original English</summary>

**Guest**: I mean, I have strong opinions about graph databases. I don't think you need one. I think that can be... I have not seen any benchmarks that show native graph databases outperform relational database systems when those relational systems have the right constructs in SQL or the API so that you can do graph traversal all on the server side, not go back and forth.

</details>

**嘉宾**：实际上，SQL 标准在 2023 年（SQL:2023）就已经加入了对属性图查询（Property Graph Queries）的支持。Oracle 已经支持该标准。PostgreSQL 原本计划在今年提供支持，预计会在 PostgreSQL 19 之后的版本推出，但我听说这项功能被推迟或者回滚了，具体原因我并不清楚。不过无论如何，这都是后话了。

<details>
<summary>Original English</summary>

**Guest**: SQL—the SQL standard in 2023 added support for property graph queries. Oracle supports it. Postgres was supposed to support it this year. It's coming out post-19, but I think it got delayed or rolled back. I don't know why. But anyway, that's beside the point.

</details>

**嘉宾**：我认为对于上下文层来说，归根结底还是要取决于你的具体需求：你拥有多少个智能体（Agent）？有多少数据状态？多个智能体之间是否存在共享状态？对于 OLTP（在线事务处理）场景中的大多数此类需求，PostgreSQL 往往都应该作为首选方案。当然，如果你做的是分析型任务（Analytics），那就是完全另一回事了。

<details>
<summary>Original English</summary>

**Guest**: No, I think that... I mean, the context layer, again, depending on the requirements of what the... how many agents you have, how much... whether you have shared state or not across multiple agents. Postgres often is, you know, should be the first choice for many of these things for OLTP. If you're doing analytics, that's a whole another story.

</details>

### Text-to-SQL 的演进与企业落地瓶颈

**主持人**：我们再来聊聊 MCP（模型上下文协议，Model Context Protocol）吧。

<details>
<summary>Original English</summary>

**Host**: Let's talk about MCP.

</details>

**嘉宾**：好的。

<details>
<summary>Original English</summary>

**Guest**: Yes.

</details>

**主持人**：在过去大约一年的时间里，似乎每家数据库厂商都在自己的产品中增加了 MCP 服务器。对此你怎么看？比如它有哪些优缺点？因为在我看来，大概一两年前，市场上兴起过一股 Text-to-SQL（文本转 SQL）的浪潮，每个人都试图让大语言模型直接运行在数据库之上，尤其用于分析目的，但当时的效果并不理想。我们现在真的走到那一步了吗？

<details>
<summary>Original English</summary>

**Host**: So over the last year or so, it seems like everybody, every database provider added an MCP server to their offering. Thoughts on that, like pros and cons? And I'm coming from... you know, a year or two ago there was this whole Text-to-SQL kind of movement where everybody was trying to make LLMs work on top of databases, especially for analytical purposes, and that sort of didn't work. Are we there now?

</details>

**嘉宾**：所谓的 Text-to-SQL，本质上就是自然语言转 SQL。这其实是人们从 20 世纪 70 年代起就一直在尝试做的事情，对吧？每隔一段时间，自然语言处理领域出现某种突破时，人们就会说：“好吧，现在终于能实现了。”但事实是一直没有真正做成——直到大语言模型（LLM）的出现。

<details>
<summary>Original English</summary>

**Guest**: So Text-to-SQL is like natural language to SQL. So that this is something people have been trying to do since the '70s, right? And every so often there's, you know, maybe a breakthrough in natural language processing. People say, "Okay, now finally it can happen, right?" It hasn't happened except for LLMs.

</details>

**嘉宾**：对于学术文献以及关于各种 Text-to-SQL 框架的研究论文，我一直持怀疑态度。因为这些论文里的基准测试往往使用的都是 Spider 以及其他几个知名数据集，而这些都是模型预训练时就已经见过的基准测试集。因此，模型能够直接复读出正确答案自然不足为奇。

<details>
<summary>Original English</summary>

**Guest**: I've been skeptical of the academic literature and research publications on various frameworks that do Text-to-SQL, because often times the benchmarks are showing Spider and a couple of other ones. Like, these are well-known benchmarks that, you know, the models are trained on. So of course they regurgitate the correct answer.

</details>

**嘉宾**：昨天我刚好和一家特大型银行的人聊过，他们表示内部现在已经上线了 Text-to-SQL 接口。但是在最初的实现中，他们使用的是现成的开箱即用方案，随后在内部做了一些进一步的微调和精简，但准确率大概只有 60% 左右——也就是说，大语言模型或智能体只有 60% 的概率能够生成正确的 SQL 查询并给出正确答案。这与我之前在其他报告中看到的情况大致吻合。

<details>
<summary>Original English</summary>

**Guest**: I actually was talking to somebody from a very large bank yesterday who said they now have a Text-to-SQL interface. But in the initial implementation of it, they were doing something off the shelf, and then they further refined it a little bit further in-house, but it was about 60% accuracy, meaning the LLM or the agent could produce the right SQL query, produce the right answer 60% of the time, right? And that's roughly what I think I've seen before in some other reportings.

</details>

**嘉宾**：但他们提到，通过在多年时间里投入数百万美元构建更丰富的语义层（Semantic Layer）和上下文层，他们成功把准确率提升到了大约 95% 左右，这简直令人难以置信。我认为这证明了一条可行路径：如果你愿意投入足够的时间去搭建正确的语义层并提供完备的上下文信息，使智能体拥有充分的信息来根据你提出的问题推导出正确的 SQL 查询，这在今天确实是可行的。

<details>
<summary>Original English</summary>

**Guest**: But they said through providing a more rich semantic layer, a context layer over multiple years and millions of dollars to make this work, they were able to get it up to like 95%, which is insane. I think that is a viable thing now if you invest the time to have the right semantic layer and the context information you need, so the agent has enough information to derive the right SQL query from the question you're asking.

</details>

**嘉宾**：不过我要再次强调，这是一家资金极其雄厚的大型银行才做成的事。如果普通人现在只是从网上随便下载一个现有工具，就会发现它们的熟练度和准确度根本达不到那种水准。但这并不意味着我们未来无法达到。

<details>
<summary>Original English</summary>

**Guest**: I think again that's a large bank with infinite money and they pulled this off. I think if you just download something now, a random person will find that these existing tools are not going to be at that level of proficiency and accuracy. But it doesn't mean we can't get there, right?

</details>

### 模型上下文协议（MCP）的定位与安全防线

**嘉宾**：现在回到 MCP（模型上下文协议，Model Context Protocol）。我非常理解他们推出 MCP 的初衷。这个协议最初出自 Anthropic，随后几乎所有人都在迅速跟进，将其视作事实标准。尽管 Hacker News 上隔三差五就会冒出一篇声称“MCP 已死”之类的帖子，但我认为它绝不会消失。

<details>
<summary>Original English</summary>

**Guest**: Now in terms of MCP, the Model Context Protocol, like, I get why they did it. Like, I think this came out of Anthropic, and then everyone sort of quickly adopted it as the standard. And every so often there's a Hacker News post saying like "MCP's dead" or whatever. Like, I don't think it's going away.

</details>

**嘉宾**：MCP 的本质实际上就是一个 REST 接口，对吧？它提供了一种标准化的方式，用来规范智能体向后端数据系统发出的请求格式。接收到该 MCP 请求的数据系统，其职责就是将该请求转化为对应的 API 调用，从而检索出所需的数据；对于数据库系统而言，这个过程就是编写 SQL 查询并获取数据。

<details>
<summary>Original English</summary>

**Guest**: It's basically a REST interface, right? A standard way to specify what you want the request to be from the agent to whatever data system you have. And then that data system that receives the MCP request, it's their job to convert it into whatever the correct API calls is to get the data you need. And in the case of database systems, it's writing the SQL query to go get the data you need.

</details>

**嘉宾**：但通常情况下，这往往只是对传入内容的严格映射与直译，而不需要去过度推导 MCP 请求背后的深层语义含义，因为 MCP 请求本身在定义上就已经相对明确了。我对 MCP 没有任何异议。它并不是包治百病、能解决世界上所有问题的灵丹妙药，但它确实是一个数字化的接口标准，让不同的智能体和不同系统之间能够相互协作并收集所需数据。我非常支持它，因为这促进了数据的有效使用，而不是让每个人都去造一套私有的轮子。所以它确实非常棒。

<details>
<summary>Original English</summary>

**Guest**: But usually it's a strict translation of what is being passed to you, and not like trying to derive the semantic meaning of the MCP request, because the MCP request has to be somewhat well-defined. I have no problem with MCP. I think that it's not this magic bullet that solves all the world's problems. It's just a digital interface, right, that you can now interpose or interoperate these different agents and different systems to collect data you need. So I'm all for it because you're using the data more rather than some homegrown thing. So yeah, fantastic, it's great.

</details>

**嘉宾**：它还能改进吗？当然可以。我认为它在效率上还有欠缺，因为你是在通过网络传输人类可读的纯文本来检索数据。显然，如果采用二进制协议（Binary Protocols），会有更高效的实现手段。但归根结底，它在现阶段已经足够用了，而且它似乎已经成为大家公认的通用标准。

<details>
<summary>Original English</summary>

**Guest**: Could it be improved? I mean, like, I think it's inefficient because you're sending human-readable text over the network to go retrieve data. There's obviously better ways to do this with binary protocols, but at the end of the day, it's good enough, right? And it seems to be the standard everyone's using.

</details>

**主持人**：那它是否应该承担起你刚才提到的安全层（Security Layer）的职责呢？

<details>
<summary>Original English</summary>

**Host**: Should it be that security layer that you were alluding to earlier?

</details>

**嘉宾**：是的，完全可以。但从本质上讲，这与传统的应用程序客户端通过 JDBC 或 ODBC 等网络协议及终端向数据库发送 SQL 请求并无二致。无论请求来自于传统接口还是通过 MCP 发送的 REST 请求，底层逻辑完全相同。归根结底，系统在接收到请求后都要搞清楚：是谁在发起请求？他们请求执行什么操作？以及他们是否应该被允许执行该操作？因此，我们之前讨论的那些安全护栏，不论请求是以 SQL 形式进来，还是以 MCP 形式进来，要求都是完全一样的。

<details>
<summary>Original English</summary>

**Guest**: Yeah. So it's no different than if the request came from SQL from a traditional application client using JDBC or ODBC, like the network protocols or terminals for these different data systems. It's no different if it comes from that versus, you know, a REST request over with MCP. The end of the day, like, "Okay, I got this request. I need to understand who's asking for it. What are they asking to do, and should they be allowed to do it?" So the guards we were talking about before, they're the same if it's coming in as SQL versus same as coming in MCP.

</details>

### AI 构建数据库内核的潜力与现实

**主持人**：好的，这构成了我们前半部分讨论的核心：将数据库作为智能体的记忆层或执行层。现在让我们把讨论反转过来：AI 能为数据库本身做些什么？显而易见，我们生活在一个 AI 几乎能编写任何代码的时代。这对数据库系统开发来说也同样成立吗？

<details>
<summary>Original English</summary>

**Host**: Okay. So that's one part of the conversation, that's databases as a memory layer or execution layer for agents. Let's flip the discussion into what AI can do for databases. So clearly we live in a world where AI can code just about anything. Is that true of databases as well?

</details>

**嘉宾**：确实如此。这里可以分享一个亲身经历：我在卡内基梅隆大学（Carnegie Mellon University）教授数据库系统课程。就在一年前，AI 智能体还无法独立完成我们的整套课程大作业。我们布置的大作业通常是提供一个数据库系统的基础框架，要求学生去实现索引、查询引擎等核心模块。当时的模型能完成其中一部分，但无法完成全部。

<details>
<summary>Original English</summary>

**Guest**: Yes. So to give one anecdote, I teach a course on database systems at Carnegie Mellon University. A year ago, the agents couldn't do our entire project. So the projects would be like we give you a scaffolding with database system and you have to implement, you know, the indexes, the query engine, and things like that. It could do some of it, not all of it.

</details>

**嘉宾**：但自从去年 Anthropic 发布了 Claude Opus 之后，整个局面彻底被打开了。现在的智能体几乎可以在极少提示词的情况下完成我们所有的课程作业。当然，这其中很大一部分原因在于存在海量的训练数据，因为我们所有的作业项目都是开源的，全部托管在 GitHub 上；不仅卡内基梅隆大学的学生在使用，校外的其他学生也可以自由使用，因此模型拥有大量实现这些功能的训练语料。

<details>
<summary>Original English</summary>

**Guest**: I think it was Opus or whatever Anthropic put out last year, then that just opened the floodgate. The agent basically do all our assignments, right, with very little prompting. And of course there is a lot of training data for it because all our projects are open source, they're all on GitHub—not just students at Carnegie Mellon University, but also students outside of the university we let them use it. So there's a lot of training data for them to implement things.

</details>

**嘉宾**：因此，我认为现在的智能体基本上可以实现你构建一个数据库系统所需要的任何组件。当然，前提是你必须以正确的方式编写提示词，步步引导，确保生成的架构设计符合要求，并促使它严格按照你预期的架构去产出具体代码实现。但归根结底，我认为如今的智能体已经完全具备了胜任这项工作的强大能力。

<details>
<summary>Original English</summary>

**Guest**: And so I think agents basically could implement anything, you know, you would want to build a database system. Now, obviously you have to prompt it the right way and hold its hand and make sure you generate the right design, or it produces the implementation based on the design that you want. At the end of the day, I think these agents are very capable to be able to do this.

</details>

**主持人**：这么说来，智能体甚至能凭空构建出一整套完整的数据库？因为作为一名风险投资人，根据我过往在数据库投资领域的经验，打造一款数据库是一段长达十年的痛苦旅程：前三年往往毫无实质性进展，汇聚了世界上最顶尖的一批聪明大脑共同攻坚，而每一次面对的问题看起来都像是不可逾越的天堑。所以我们现在是在说——

<details>
<summary>Original English</summary>

**Host**: So they could build an entire database? Because my experience of building database as a venture investor is that it's a 10-year journey of pain where nothing much happened for 3 years, and you have some of the smartest people in the world getting together to solve what seems each time like insurmountable problems. So we're now saying that—

</details>

<!-- chunk 5/11 -->

### AI 驱动的数据库开发与开源追踪

**Andy Pavlo**: 他可以构建整个系统。

<details>
<summary>Original English</summary>

**Andy Pavlo**: He can build the whole thing.

</details>

**主持人**: 是的。

<details>
<summary>Original English</summary>

**Host**: Yeah.

</details>

**Andy Pavlo**: 数据系统领域有一句老话：打造一个数据系统需要耗费十年时间，你可以在前三年里完成最初的 90%，但剩下的 10% 却要花上接下来的七年甚至更久。所以，我认为智能体确实非常有能力——当然，前提是要有足够的 token 以及足够的人工引导，人们完全可以通过“氛围编程”（vibe coding）搭建出完整的数据系统。如今确实已经有公司在这么做了，而且几乎每家公司都在利用智能体来辅助开发。

说到这里，我再次重申，我非常热爱数据库。我的业余项目之一就是“数据库的数据库”——dbdb.io。我们现在做的一件事，就是追踪我所知道的每一个数据系统。对于开源系统，我们每天晚上都会从 GitHub 拉取所有最新的提交记录，然后追踪并分析哪些提交实际上是由 Claude、Codex 之类的工具协同署名（co-signed）完成的。显然，有些人会关闭这个署名功能，那样你就无法确知代码是否真的是生成的。但大多数人并不会特意去关掉它。目前来看，我认为开源数据库系统中已经有超过 60% 的系统，其提交代码里包含来自智能体的贡献。

<details>
<summary>Original English</summary>

**Andy Pavlo**: The old adage from data systems is that it takes 10 years, but a data system you can build the first 90% in 3 years and then the remaining 10% takes the next 70 years or seven years. So yeah, I think that the agents are very capable, with enough tokens of course, and then with enough guidance people can vibe code entire database systems. And there's certainly companies that are doing this now, and pretty much every single company is using agents to help develop things.

So again, I love databases. One of my side projects is the Database of Databases, dbdb.io. And one of the things we do now is we keep track of every single data system that I know about. And for the open source ones, every single night we pull down all the latest commits on GitHub, and then we track to see which ones are actually being co-signed by Claude or Codex and things like that. Obviously, people turn that feature off, and you don't know whether it's actually been generated, but most people don't do that. And at this point, I think over 60% of the open source database systems have commits coming from agents.

</details>

### 从自动调优到大模型驱动的自动驾驶数据库

**主持人**: 那么除了写代码之外，这是否也适用于数据库的日常运行？也就是回到“自动驾驶数据库”（self-driving database）的概念。据我所知，这大概在十年前就是你的一个重大研究项目了。

<details>
<summary>Original English</summary>

**Host**: And so does that, beyond the writing, also apply to the running of it? Going to that self-driving database concept, that's something that was a big project of yours 10 years ago, I believe.

</details>

**Andy Pavlo**: 没错。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yeah.

</details>

**主持人**: 是的，请带我们回顾一下那段历程吧。当年有哪些事情是做不到的，而如今却变成了可能？

<details>
<summary>Original English</summary>

**Host**: Yes. So walk us through that journey. What was not possible then that has become possible today?

</details>

**Andy Pavlo**: 好。当年我刚入职卡耐基梅隆大学（Carnegie Mellon University）时，我在最初几年里做的一件事就是走访各家企业，实地了解他们在数据库方面面临着什么样的挑战。我一次又一次看到的核心共性问题，就是运行、维护和调优这些系统简直是一场巨大的挣扎。

对我来说，这其实算不上什么惊天动地的新发现。几十年来大家一直在努力解决这个问题。我的意思是，自从 20 世纪 70 年代关系模型与关系型数据诞生以来，人们就一直试图对索引、分区键、分片键以及各类调优旋钮进行自动化调优。例如微软研究院在 2000 年代初期开展了 AutoAdmin 项目的大量工作，他们开发了一系列工具来尝试自动管理和优化数据系统。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yeah. So when I started at Carnegie Mellon University, one of the things I did in my first years was I would go visit companies and sort of see what sort of challenges they were facing with databases. And the overarching theme I saw over and over again was like just running these systems, maintaining them, and optimizing them was a huge struggle.

And this is not a huge revelation for me, people have been trying to do this for decades. I mean since the creation of the relational model and relational data in the 1970s, people have been trying to do autotuning for indexes, partitioning keys, sharding keys, and tuning knobs and so forth. Microsoft Research did a lot of work in the early 2000s in this AutoAdmin project; they had a bunch of tools allow you to manage and optimize data systems automatically.

</details>

**主持人**: 补充一个背景，这是因为一个数据库内部可能存在成千上万种潜在的配置组合。

<details>
<summary>Original English</summary>

**Host**: And for context of this, because there's thousands and thousands of possible configuration of a database.

</details>

**Andy Pavlo**: 没错。比如“我的表中到底应该建哪些索引来加速查询？”显而易见，如果你建了太多索引，写入性能就会下降，磁盘空间也会被耗尽。此外，还有各种各样控制系统运行时行为的配置旋钮（knobs）：比如给某个内存池分配多少内存、给索引缓存分配多少内存等等。这些复杂性早已超出了任何单个人类大脑的推理和推导极限。如果你进一步面对拥有成千上万个数据库的场景，任何人都不可能靠纯手工把它们管理过来。

因此，我们当时花了不少时间研究如何利用机器学习——也就是现在大家口中的 AI，但在当时是通过自动化方法与机器学习技术——来实现调优的自动化。我们大体上探索了两条研究路线：一条路线是将数据库系统视为“不透明黑盒”，前提是我们无法修改数据库内部源码，仅凭该数据库暴露出的现有 API，我们能做些什么？也就是说，如何自动调优 MySQL、PostgreSQL、Oracle 等既有的现有数据库；另一条研究路线则是：如果你从零开始构建一个全新的数据系统，并预设它将完全由机器学习工具（也就是今天所说的智能体）来控制与接管，那么你在系统架构设计上会有何不同？我们在尝试调优 MySQL 和 Postgres 过程中总结出的许多经验教训，最终都被我们吸收并实现进了我们自主研发的数据库系统中。

当时这些自动化工具始终面临的一大挑战，就是缺乏足够的生产环境真实数据库训练数据。你很难将在优化某一个特定部署环境时学到的模式，顺利迁移并应用到另一个环境上。就像我之前提到的，大多数团队通常拥有暂存（staging）或开发环境，同时拥有生产（production）数据库。你显然不敢在生产数据库上随意尝试各种随机操作，因为在摸索如何调优的过程中，这可能导致数据库变慢、性能出现严重倒退。因此，你只能在暂存环境上验证这些调整，然后再尝试推向生产环境。但很多时候，两边的硬件配置完全不同，承载的工作负载也截然不同。所以，无法获取足够丰富的训练数据来喂给模型，从而在生产数据库上做出明智决策，一直是我们面临的核心难题。

随后大语言模型（LLM）横空出世，这彻底改变了我们应对该问题的方式。因为大模型本质上吸收了互联网上公开的所有博客文章、技术文档以及最佳实践指南，它们通读了关于如何调优这些数据库的海量经验。在科研层面，我们的研究发现，LLM 在某些配置项的调优上甚至能直接帮你搞定 85% 的工作。当然，对于极其怪异的边缘极端情况，专门定制的定制算法依然不可或缺。但是，我们原先的模型通常需要花费数小时进行训练（前提是你还得拥有足够的训练数据），才能推导出极致完美的最佳配置；而大语言模型却可以在短短 15 分钟内给出一个“足够好”的方案，而对绝大多数人来说，“足够好”就已经完全能满足需求了。

那么，我们现在达到这一步了吗？我们是否已经身处一个数据库在很大程度上能够自我调优、自我优化的世界？答案是肯定的，但这当然取决于你究竟追求多大程度的性能提升。正如我所言，大模型能够带你走到 80% 到 85% 的位置，但系统是否永远存在继续挤出更多性能的空间？是的，而且总会有一部分人对那极少数的极致性能极度在乎，对于他们来说，我们过去构建的那套深度自动化方法依然至关重要。但对于大多数人而言——事实上，当初我们创办 startup 尝试为 Postgres 和 MySQL 做自动调优产品时，最令我吃惊的一点就是……

<details>
<summary>Original English</summary>

**Andy Pavlo**: Right. So there's what indexes should I have in my table to speed up queries. And obviously if you have too many indexes, the writes go slower and you run out of disc space. There's the various knobs that control the runtime behavior of the system: how much memory you use for one memory pool versus for indexes, and so forth, right? This is beyond the capabilities of any one human to reason about. And then if you have thousands of databases, it's just not possible for anybody to manage these things.

So we spent some time looking how to build automated tools using machine learning—what you may call AI now, but using automated methods, machine learning techniques—to automate this. And we sort of had two research tracks. We had one where we took an opaque box view of the database system, where we said we can't change the internals, what can we do just with what the APIs that this system exposed. So basically, how do you optimize automatically existing databases—MySQL, Postgres, Oracle, and so forth? And then another track of research was: if you build a database from scratch assuming it was going to be controlled by machine learning tools, or now what we call agents, how would you design the system slightly different? And a lot of things we learned from trying to optimize MySQL and Postgres, we end up building in our own system.

The challenge always was then for these automation tools was just having enough training data of production databases, and being able to take the things you learn optimizing maybe one deployment and apply it to another. As I was saying before, most people have a staging or development environment and then they have the production database. And so you obviously don't want to try random things on the production database that may cause you to slow down and degrade performance while you're trying to figure out how to tune it. So you would vet things on the staging database and then try to apply to the production one. But often times it's never the same hardware, never the same workload. So that was a big challenge we were always facing, just getting enough training data to feed into the models that you can then make good decisions on the production databases.

And then the LLMs showed up, and that really changed how you can approach the problem, because they are basically trained on blog articles, documentation, best practice guides that are all available on the internet of how to tune these databases. And so on the research side, what we found is the LLMs can get you maybe 85% of the way there in tuning certain things. And obviously there's weird corner cases bespoke algorithm can handle those. But our models often time would take hours and hours to train, assuming you had enough training data, to produce the pristine optimal configuration. But the LLMs can come in like in 15 minutes, produce something that was good enough, and that's good enough for most people.

So are we there yet? Are we in a world where database can largely be sort of self-tuned, self-optimized? I mean the answer is yes, but of course it depends on how much improvement you actually want. Like I'm saying, the LLMs can get you 80-85% of the way there. Is there always more performance to squeak out? Yes, and some people are always going to care about that, and therefore the automated methods we built in the past would matter a lot more. But for most people, actually one of the things I was surprised so much was when we had the startup and trying to do this auto tuning stuff for Postgres and MySQL is how many...

</details>

**主持人**: 那个项目叫 OtterTune。

<details>
<summary>Original English</summary>

**Host**: That was OtterTune.

</details>

**Andy Pavlo**: 没错，OtterTune。最让我惊讶的是，竟然有那么多人直接使用亚马逊（AWS）或谷歌云（GCP）等云平台开箱即用的默认配置直接在跑。他们甚至会跟我们讲：“啊，我们还以为亚马逊已经在后台帮我们把调优搞定了呢。”事实是：完全没有！所以，有海量用户实际上都跑在一个极其糟糕的默认配置上，我们通常的第一反应就是“千万别直接用默认参数跑”。在这种情况下，大语言模型完全能够切入进来，迅速摘下这些唾手可得的低垂果实（low-hanging fruit），在极短的时间内为人们带来切实而显著的性能改善。

<details>
<summary>Original English</summary>

**Andy Pavlo**: OtterTune, yes. Was how many people were running with the out-of-the-box configuration from Amazon or Google in their cloud platforms, and they would tell us, "Oh, we thought Amazon was tuning this for us." Like, no they're not, right? So there's enough people that are maybe running with a default configuration, which is just terrible, don't do that, where an LLM could come in and take care of some low hanging fruit and provide some meaningful improvements for people in a short amount of time.

</details>

### AI 时代下数据库核心知识的价值

**主持人**: 在整个软件开发领域，我们已经看到开发人员的工作本质发生了极其深远的变化。如果今天有一名卡耐基梅隆大学的学生，对数据库领域充满热情——当然，他们未来可以选择去 ClickHouse 或者 CockroachDB 这样的专业数据库公司工作；但抛开这些专业厂商不谈，在未来的世界里，如果智能体将全面负责调用与运维数据库，而数据库自身也将实现高度的自动驾驶，那么今天还有哪些工作岗位依然需要对数据库有极其深入的底层认知？

<details>
<summary>Original English</summary>

**Host**: So in the rest of the software world we've seen the nature of the job of a developer profoundly change. If you're a student at CMU today and you're super excited about the world of databases, yes, you can work for the ClickHouse or CockroachDBs of the world. But outside of that, what is the job today that requires deep knowledge of databases if we're in a world where agents are going to be calling them, managing them, and then the database themselves will be self-driving?

</details>

**Andy Pavlo**: 我一直以来对上我课程的学生都是这么说的：在我的课堂上，即便你未来不打算成为一名专门的数据系统工程师——也就是不去深入参与 ClickHouse、CockroachDB 或 PostgreSQL 这类系统的内核底层研发——归根结底，每个人在日常工作中终究都要与数据系统打交道。如果你能理解它们的内部工作机理、知晓它们是如何被工程实现的、明白数据系统在面对特定查询时到底在尝试做什么或故意避免做什么，你就会在整个技术栈的大环境以及现代技术世界中处于更有利的地位，深刻看懂全局正在发生的一切。

那么，你是否必须非得通过上我的课才能搞懂这些呢？答案是否定的。如果我非要说“必须上我的课不可”，那就未免太天真了。因为智能体已经吸收并消化了我所有的教学内容，它们完全可以把我能传授的所有知识原封不动地重新复述出来……

<details>
<summary>Original English</summary>

**Andy Pavlo**: So what I would tell my students always was like, for my courses, even if you're not going to go off and become a database system engineer—go work on the internals of ClickHouse or Cockroach or Postgres—at the end of the day everyone's going to interact with the database system. And if you understand the internals of them, how they're implemented, what the data system is trying to do or not do for you for given queries, you're just going to be in a better position to understand what's going on in the world in tech stacks. And now do you need my course to figure that out? No. I'd be naive to think so, that the agents have sucked all my stuff in so they can regurgitate everything I would teach.

</details>

<!-- chunk 6/11 -->

### 理解数据系统的底层逻辑：为何人类在AI时代仍不可或缺

**Andy Pavlo**：总之，无论你是通过传统的大学课程学习，还是完全自学，亦或是让大语言模型来教授你知识，归根结底，只要你理解了一个数据系统究竟想要实现什么，它在很大程度上就能消除绝大多数的迷茫与困惑。这能帮助你真正搞清楚自己的应用程序内部究竟在发生什么——为什么查询会跑得慢，或者为什么不会慢。你能够站在一个更有利的视角去洞察全局。因此，如果你攻读了计算机科学或工程学位，并专注于数据库系统，我并不认为……我认为如果觉得“你未来还要完全靠自己从零开始手写一个系统”的想法未免太天真了，那个时代已经翻篇了。但在最终层面上，各大数据库公司依然在大量招募人才来从事这些研发工作，因为必须有人去理解AI智能体（agents）究竟在底层做些什么，并对其合理性进行推敲与解释。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Anyway. So, but at the end of the day, again, whether you're learning it from a traditional university course or self-taught or having an LLM teach you things. If you understand what a data system is trying to do, then it sort of removes most of the mysteries and it helps you understand like what's going on in your application. Why are queries running slow or not running slow, you're in a better position to understand what's going on. And so if you pursued a computer science degree or engineering degree and focus on database systems, I think the era of like you're going to write a system from scratch by yourself, I'd be naive to think that's still going to be around. But at the end of the day, the database companies are still hiring people to work on these things because someone needs to understand what the agents are actually doing and make sense of it.

</details>

**Host**：但如果要追根究底的话，我们是否正在迈入一个在数据库的管理与部署方式上完全实现“无人在环”（no humans in the loop）的全新时代？

<details>
<summary>Original English</summary>

**Host**: But to fully ask the question, like are we in an era where there's going to be just no humans in the loop in the way databases are managed and deployed?

</details>

**Andy Pavlo**：我认为，我们过去所熟知的传统数据库管理员（DBA）角色将会被逐渐边缘化，其中相当大一部分工作完全可以实现自动化。但这并不必然意味着这些岗位会彻底消失。他们现在只是能够腾出手来，去从事层次更高、更具思考深度的核心工作，比如数据建模——这一环永远都至关重要。诚然，智能体在数据建模方面也能分担不少工作，但你终究还是需要有人去深刻理解并把关：“这个数据模型是否真正精准地刻画了我们机构或业务希望在数据库中所表达的实体与逻辑？”这些核心层面的判断依旧超级重要。至于像调整底层参数旋钮、或者为某张数据表挑选具体的索引这类琐碎工作，我认为这部分职责完全会剥离出去，你根本不再需要人工介入，智能体完全能把这一切处理得非常漂亮。

<details>
<summary>Original English</summary>

**Andy Pavlo**: I would say that the traditional role of a DBA as we've known in the past, I think that's going to be relegated and a lot of that can be automated. Doesn't necessarily mean those roles go away. They just now get to pursue more higher minded activities like data modeling, always important. And again, agents can do a lot of that too, but you still need someone to understand like, yes, does this data model capture what our organization or business is trying to represent in the database? All those things are super important still. Just like, does someone need to be tuning the knobs or picking exact indexes for tables? I think that ships out, you don't—an agent can do all that.

</details>

### 从CMU公开课到硬核教学风格

**Host**：太棒了。换个话题，数据库领域的绝大多数人想必都对您的工作非常熟悉，但对于那些还不太了解的人来说：您曾长期在卡耐基梅隆大学（CMU）担任终身教授，开设过备受追捧的经典明星课程。我认为您所做的一件极具格局且美好的事情，就是把您在CMU亲自教授的大量课程录像全部免费公开上传到了网络上。

<details>
<summary>Original English</summary>

**Host**: Great. To switch topics, a lot of people in the database world, I assume pretty much anyone is very familiar with your work, but for people who are not: so you have been a tenured professor at CMU. You have had very popular classes. I think part of the one beautiful thing that you did is that you took a lot of CMU courses that you were teaching and then you put them online for free.

</details>

**Andy Pavlo**：当年我刚加入卡耐基梅隆大学时，我是那里唯一一位专注于数据系统方向的教授。系里虽然还有另一位教授，但他的研究方向更多偏向图挖掘和数据挖掘领域。2013年我入职时，心里就想着：好吧，我得想办法拿下终身教职（tenure）。虽然用“竞争”这个词可能并不完全准确，但我当时实际上是在跟麻省理工（MIT）、斯坦福（Stanford）以及加州大学伯克利分校（Berkeley）这帮顶级强校暗中较劲，而CMU这边研究数据库系统的却只有我光杆司令一个。于是我想：行吧，那我就把所有的教学内容全部免费公开到互联网上。这样做一方面有助于推广宣传我们的学术研究和攻坚方向；另一方面，它还产生了一个意想不到的积极副作用——这倒逼着我必须对每一堂课做更充分的准备。并不是说我以前会敷衍了事，而是我知道这些视频都会被录制下来公开传播，为了避免在镜头前口误说错话，我必须严阵以待、把内容打磨得极其扎实。同时，我在讲台上也会表现得更加专业、克制，少讲一些天马行空的疯话。听到我这么说大家往往很震惊，因为即便在今天，外界依然觉得我的课程风格已经被“稀释修饰”过了，甚至连学生们都觉得这很不可思议。所以，这件事带来的好处是非常显而易见的：并非所有人都有机会进入卡耐基梅隆大学深造，它学费昂贵，毕竟是一所私立名校，门槛极高，不是人人都能被录取的。但为什么如此优质的教育资源要对大众藏着掖着呢？这本身又不需要我额外掏什么钱，我只要把视频上传到YouTube上，让全球每一个人都能无门槛获取即可。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So when I started at Carnegie Mellon, I was the only data systems professor there. There was another professor there, but he does more like graph mining, data mining stuff. And so when I started in 2013, I was like, okay, well, I got to figure out how to get tenure. And competition is not the right word, but I'm competing against MIT, Stanford, and Berkeley. And I'm the only database person there. So like, all right, we'll just put everything for free on the internet. And that helped promote our research, what we're trying to do. It also had the side effect of like I would end up being more prepared for classes because, not that I was a phoning it in anyway, but like I was make sure I had my stuff together because I knew it was going to be recorded and watched because I don't want to say the wrong thing. And I would be more professional, I'd say less crazy things, which people are like shocked when I say this that my course even now is considered watered down, like even for them that's bizarre. So yeah, obviously the benefit is like not everyone can go to Carnegie Mellon University. It's not cheap, it's a private school, not everyone can get in. But why should that education be held back from other people? So it doesn't cost me anything. I just put it on YouTube and make everything available to everyone else.

</details>

### 课堂现场打碟与武当派期末考传奇

**Host**：我们在这次访谈开场时还开玩笑聊到了武当派乐队（Wu-Tang Clan）。我记得曾在哪里听说或读到过，您在课前居然请过一位专属DJ在讲台边现场打碟播放武当派的嘻哈音乐，这背后到底有什么好玩的故事？

<details>
<summary>Original English</summary>

**Host**: And we were joking about Wu-Tang Clan at the beginning of this conversation. I think I heard or read somewhere that you had a DJ spinning Wu-Tang Clan at the beginning of class. What is that story?

</details>

**Andy Pavlo**：那是从2019年开始的。当时我想：“好吧，既然要讲课，不如玩点有意思的。”大家都知道，每次在教室架设录像机机位、连接线路的时候，肯定会耗费一段准备时间——就像我们今天录制这期播客一样，也是要提前调试设备布线的，这需要花时间。当时就会出现一段非常尴尬的死寂：台下的学生们陆陆续续走进来，大家都愣愣地盯着你看，现场没有任何动静，也没人开口说话。于是我就琢磨：“得嘞，那我干脆请个DJ直接坐在我旁边，在课前全程给我现场打节拍、放音乐，气氛不就活跃起来了吗？”然后，在讲课间隙你就会跟DJ闲聊互动，结果发现他们的个人生活经历极其精彩：比如有一个哥们儿，身边有一堆前女友排着队想跟他复合；另一个家伙，则把一大笔钱借给了一些根本不该借的人。我们就这样在课堂上堂而皇之地八卦聊这些奇闻轶事，然后再接着讲数据库。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So it started in 2019. I was like, "All right, well, let's have fun with this." And you know, when you set up the cameras and things like that for the lectures, there's obviously time to set things up, the wires. You know, we had to set all this up, too, right? There's time. So, I'm like, "All right, well, there's this awkward silence where the students are coming in, they're staring at you. There's nothing really going on. There's nobody saying anything. So, like, let me get a DJ to sit next to me and just play beats and play music next to me the whole time, right?" And then you start talking to them during the lecture and you find out like they live pretty interesting lives. Like, one guy had a bunch of ex-girlfriends trying to hook up with him. One guy would loan a bunch of money to people he shouldn't be loaning to. So, just like we just talk about it in the class, plus databases.

</details>

**Host**：完全符合你一贯的硬核作风。

<details>
<summary>Original English</summary>

**Host**: As one does.

</details>

**Andy Pavlo**：哈哈，确实如出一辙！另外有一年，我还跟学生们开过一个经典的小玩笑：顶级的数据库学术会议往往集中在学期初或者学期末举行，所以我经常得外出参会出差。开学第一周我往往就得动身去参加学术会议，但你肯定不想把开学第一课直接取消，因为第一周对学生来说至关重要，他们需要了解这门课的具体定位和教学内容，以此决定最终是否选课。于是我就采取远程录制视频的方式授课。那一年我在洛杉矶开会，把讲座录完后，在视频的最末尾我一本正经地说道：“对了，关于数据库，你们必须掌握的最重要知识点是……”接着我就一口气列出了武当派首张专辑里的所有成员名字，顺带加上了当时还在坐牢的Cappadonna。我对着镜头郑重其事地说：“这就是你们学习数据库必须掌握的最核心知识。”结果等到了学期末的期末考试，试卷上的第一道题目赫然就是：请列出武当派在《Enter the Wu-Tang (36 Chambers)》专辑中的所有成员名字，以及当时谁在坐牢；而且拼写必须分毫不差。如果有人做对了这道题，整张期末试卷直接给满分100分！

<details>
<summary>Original English</summary>

**Andy Pavlo**: As one does. Yes. And then I think one year we had—I did a little joke where oftentimes the top database conferences are always at the beginning of the semester or at the end of the semester. So I have to travel. So the first week of classes I'll be traveling to go to a conference. So you don't want to cancel class because it's super important for students to know what the course is going to be about the first week because they're trying to figure out classes they want to take. So I would film it remotely. So one year I was in LA for a conference and then at the very end of the lecture, cuz I filmed it, I was like, "Oh, by the way, the most important things you need to know about databases." And I just listed all the members of the Wu-Tang Clan on the first album plus Cappadonna who was in jail at the time. And I said, "This is the most important thing you have to know about the databases." And then when it came at the end of the semester, the final exam, the very first question was list all the members of the Wu-Tang Clan on the 36 Chambers plus who was in jail. And you have to get exact spelling. And if they got that question right, they would have got 100% correct on the exam.

</details>

**Host**：哈哈，拼写稍有差池就前功尽弃了，这题简直是致命绝杀。

<details>
<summary>Original English</summary>

**Host**: Yeah. Not killer, but killer.

</details>

**Andy Pavlo**：没错！确实有人在这上面栽了跟头，他们在该写‘H’的地方给漏掉了。所以事实上从来没有任何一个学生真正拿到过那道题的满分。而且显然我以后也不能再搞这招了，因为学生们早就对此有所防备和预期了。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yes. Right. So, someone got that wrong. They missed the H when they should have had it. So, no one actually has ever got that. And obviously I can't do it again because students are expecting it.

</details>

### 转战工业界：创立ClickHouse Labs背后的考量

**Host**：太神了。好，这也正好引出了我们接下来的话题——ClickHouse以及ClickHouse Labs。您最近正式加入了ClickHouse并牵头创立了ClickHouse Labs。

<details>
<summary>Original English</summary>

**Host**: Okay. Amazing. All right. So, that takes us in some way to ClickHouse and ClickHouse Labs. You joined ClickHouse recently to start ClickHouse Labs.

</details>

**Andy Pavlo**：是的。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yes.

</details>

**Host**：那么，为什么选择在一家商业公司内部创立实验室，而不是继续留在学术界深耕呢？

<details>
<summary>Original English</summary>

**Host**: So, why start a lab in a commercial company versus doing that in academia?

</details>

**Andy Pavlo**：我的意思是，抛开复杂的政治因素不谈，如今在高校里做前沿学术研究的整体大环境确实非常艰难。美国目前的科研基金资助规模早已大不如前。此外，还有一个更宏观、更深刻的时代拷问：在智能体已经能够搞定大量事情的今天，继续招收培养一名博士生究竟意味着什么？当智能体本身就能产出高质量成果、并且能直接作为科研搭档协助我这个教授撰写高水平论文时，你真的还需要带那么多博士生来做基础研究吗？当然，我依然深信教书育人具有不可替代的价值，我也非常热爱教学，但我当时实在想不明白，我究竟该怎样才能筹集到足够的科研经费去招收我心仪数量的博士生。在此期间，其实陆续有好几家商业公司主动联系过我，探询意向：“嗨，你有没有兴趣休假离岗，来我们这里一起做点有意思的大事情？”但他们开出的岗位往往偏向于“来我们这儿当个普通的软件工程师”，或者是在科研主导权上大打折扣的妥协方案，根本无法满足我在前沿系统研究层面的追求。而后来当我与ClickHouse团队深入交流时，一切好得甚至让我觉得有些不真实。因为我跟他们开门见山地说，他们提出：“来和我们一起做纯粹的研究吧。”我反问：“好的，但你们真正明白严肃的前沿科研意味着什么吗？”他们斩钉截铁地回答：“明白，放手去做吧。”我又追问：“那你们清楚很多科学探索最终很可能会失败、未必能百分百取得预期成果吗？这毕竟是未知的探索，我无法打包票。”他们依然极其坚定地说：“完全理解，太棒了，尽管去探索、放手去干吧！”这简直令人难以置信，因为如你所知，他们并非一家普通的……

<details>
<summary>Original English</summary>

**Andy Pavlo**: I mean, without going too much into politics, the nature of research in university is kind of tough right now. The funding in the United States is not what it used to be. There's also a larger question of like what does it mean now to have a PhD student when an agent can kind of do a lot of things, right? Do you need to have as many PhD students working on stuff when like an agent can produce things and work with me as the professor to write papers and things like that? So I still—I mean, still there's certainly value still educating students and I like doing that, but just wasn't clear to me like how would I raise money to have many students that I would want. So I had end up had some companies reached out to me about like, "Hey, can you—interested in going leave and doing some interesting things with us?" But it was always a bit more like, "Hey, you want to come be an engineer with us?" Or kind of watered down versions of what I wanted to do on the research side. And then when I talked to the ClickHouse people, it almost seemed too good to be true because I was like, they're like, "Hey, come do research with us." I'm like, "Okay, this is what research is. You understand this?" They're like, "Yeah, yeah, go do this." I'm like, "Okay, do you understand like things might not always pan out correctly because this research? I don't know." Like, "Yeah, great. Do it, do this." And it's insane because they're, as you know, they're not an

</details>

<!-- chunk 7/11 -->

### 加入初创团队与产研结合的直接影响力

**研究员**：虽然他们已经度过了早期初创阶段，但仍然是一家创业公司，并不是上市公司。通常来说，至少在数据库领域，你只有在企业已经站稳脚跟、建立起成熟地位之后，才会看到他们去设立研究院，对吧？而对于他们而言，愿意承担这样的风险，或者说有这样的从容度让我这样的人加入去从事纯粹的同行研究，这确实令人不可思议，而且他们对此的态度非常认真。所以，这个机会甚至好得有点让人难以置信。到目前为止，我入职已经两个月了，一切运转得都很顺利。我现在正处于一个观察期，逐步深入梳理和理解他们迄今为止构建的成果，因为他们之前并没有真正系统性地发表论文或著书立说来介绍自己的工作。他们写过一些博客文章，那些文章固然非常引人入胜，但他们其实已经完成了许多极其出色的工作——当然，这些工作的功劳绝不能归于我，因为他们自己早就做出了惊人的成果——而我目前的工作，正是协助他们将这些成果整理成学术出版物，让我们能够向全世界传播和分享。同时，我们也开始筹划更具长期性、更具探索性的研究方向。

我想特别说明的是，即便当年我在大学任教期间，我在数据库系统领域的研究也一直是非常偏向应用落地的。我并不是在做那种全世界可能只有十个人能看懂、且与现实发生的一切毫无直接关联的纯理论研究。我想做的事情，与 ClickHouse 想要推进的目标是直接契合的。这不仅关乎 ClickHouse 系统本身，还因为他们现在推出了 PostgreSQL 相关的产品服务。我们在过去围绕 Postgres 做过大量的研究积累，而现在我们能够直接接触到真实的数据，尝试将其中一些技术部署到真实的生产工作负载中去，帮助人们真正将成果投入应用。因此，对我来说，能够产生这种立竿见影的直接影响是非常令人兴奋的——我不再是写一篇论文然后寄希望于未来有人看到并采用我们的技术，而是能够在真实的生产系统和真实的工作负载上开展研究，直接评估某个想法究竟可行与否。如果证明确实有效，我们就能在极短的时间内将其推向市场。正因如此，这个机会对我而言具有极大的吸引力。

<details>
<summary>Original English</summary>

**Researcher**: early stage startup, uh, but they're a startup. They're not a public company. And normally you only see companies, at least in the database world, set up research labs when they already get established, right? And for them to take, you know, this kind of risk or have the the luxury of having someone like me come in to do peer research, uh, is is is amazing. and they're they're very serious about it. Um, so like the opportunity almost seemed good too good to be true and so far, you know, it's I'm I'm two months into this and it seems to be working out. I'm sort of in this observation period now where I'm going through and understanding the stuff that they built so far because they haven't really published it published or written about what they've done. They have some blog articles which are super interesting, but they've done some amazing work that I think uh, you know, I certainly can't take credit for for doing, but like they've done some amazing work and my job right now is sort of helping them turn those into publications. we we can disseminate and put out into the world as well as start ramping up longer term more explor exploratory things and be very clear like even when I was at the university you know in database systems my work is very much applied so it's not like I'm doing theory work that has no one you know only 10 people in the world can understand it's not directly related to anything that's going on um the click house you know the the the kind of stuff I want to do is directly uh relevant to what click house wants to do um not just on the click system itself but also now they have a postgress offering there's a bunch of stuff we've done in the past on postgress and now we can start getting looking at real data trying to put some of these things in production workloads and help people you know put things out there so that to me that's like super exciting to have like direct impact of like instead of me writing the paper and then hoping someone comes along and like takes it and adopts what we're doing we we can do the research and evaluate whether it's a good idea or not on real workloads on real production systems And if it does make sense, then we can push it out in a short amount of time. So that part is super uh um super seductive to me that like that I had this opportunity.

</details>

### 初见 ClickHouse：从怀疑是虚假宣传到开源突破

**投资人兼主持人**：太棒了。既然聊到这里，我们不妨更深入地探讨一下 ClickHouse。在此做个利益披露，我们 FirstMark 非常自豪能成为该公司的投资方。我记得在什么地方读到过，你在 2016 年的时候曾一度担心 ClickHouse 可能是某种“雾件”（vaporware，空头支票），因为它听起来好得有些脱离现实了。你能为我们详细拆解一下这背后的原委吗？

<details>
<summary>Original English</summary>

**Host / Investor**: Okay. Fantastic. While we're at it, let's talk about click house a little bit in which uh for for disclosure, we are very proud investors here at First Mark. I think I read somewhere that uh in 2016 you were concerned that clickaus was possibly vaporware because it was a little too good to be true. Yeah. Can you unpack that for us?

</details>

**研究员**：好的。正如大家所知，正如我刚才提到的，数据库就是我的专业领域。我认为作为一名研究人员，我的职责就是时刻去了解业界还有哪些其他探索。数据库是一个极其引人入胜的研究领域，因为不仅我——这里请允许我宽泛地使用“竞争”这个词，绝无贬义，但事实就是在某种程度上你确实在与其他研究者竞争，争取率先提出理念并将其发表——因此，你不仅要与其他大学的研究人员竞争，还要与业界的科技巨头竞争，比如微软、谷歌和亚马逊等等。此外，还有所有那些拥有自己数据系统的初创公司。正如作为投资人的你所知，市面上并没有太多做操作系统的初创公司，但做数据系统的初创公司却数不胜数。

因此，我的工作就是在每当有新系统发布时去搞清楚：他们在做的事情与我的研究有什么不同？他们哪些地方做得更出色？我能从他们解决问题的方法中汲取到什么经验？所以，当 2016 年 ClickHouse 发布并正式亮相时，我的第一反应是：我深知构建一个数据系统有多么困难，而这个系统凭空冒出来，居然同时具备了所有这些特性——比如向量化执行、列式存储机制、压缩特性、数据压实（compaction）等等。这几乎好得令人难以置信，或者它可能是基于某个已有开源项目的分支改造。但在 2016 年那个时间节点上，根本就没有任何一款开源的 OLAP 引擎能够同时兼备所有这些能力，对吧？所以那让我大为震惊，我当时心想：这大概是假的吧。然而事实证明，它显然是真实存在的，而且带来了巨大的收益。

<details>
<summary>Original English</summary>

**Researcher**: Yeah. So, so as you know like I mentioned like you know my database databases my job I think as a researcher trying to understand what else is out there because database is a really interesting research area because not only am I again using the term competing loosely I don't mean that in a in a in a pjorative sense but like you know but you are in kind of competition with other researchers try to get ideas out and published. So not only am I competing with other researchers at other universities, uh you're also competing against the the the big tech companies, the Microsofts, the Google's and Amazon of the world. Plus there's all these startups that have their own data systems. Like there's not there's not a lot of operating system startups. There's a lot of data system startups as you know in as an investor. So my job is try to figure out when when a new system gets announced to see like what are they doing that's differently than than my own research? What are they doing better? what can I learn from from uh how they approach the problems that they're trying to solve? And so when the the announcement of or the release the unveiling of Click Alice in 2016 came out, I was like I know how hard it is to build a data system and for this thing to appear from nowhere out of nowhere and have like have all these capabilities like the vectorzed execution, the columner stuff, the compression things, the compaction stuff like it it almost seemed too good to be true or it's a fork of something that already exists. But at the time in 2016, there wasn't an OLAP engine that was open source that would have all these capabilities, right? So, so that threw me for a loop to I was like, oh, so I just assumed it was fake and then sure enough, it's real obviously uh and has a lot of benefit.

</details>

### ClickHouse 的核心架构与技术渊源

**投资人兼主持人**：那么，具体来说它有哪些优势呢？它非常快，具有极高的实时性，对吧？这是如何实现的？为什么传统数据库尤其是分析型数据库往往在这方面表现吃力？而 ClickHouse 又是凭借什么做到这一点的呢？

<details>
<summary>Original English</summary>

**Host / Investor**: So, what what are some of those benefits in particular? Uh it's it's very fast, right? It's very real time. Uh why is that possible? Why do databases uh typically struggle with that, especially analytical databases? and why are they able to do that?

</details>

**研究员**：我想说的是，从 2026 年的标准来看，ClickHouse 的核心基础架构已经谈不上新颖了，但在 2016 年确实非常具有开创性。其架构本质在于：首先，你把数据存储在列式布局中。也就是说，不同于行存储将单个元组（tuple）的所有列属性值连续存放，列存储是将单列中的所有属性和数据连续紧凑地存放在一起；其次，在 CPU 上利用向量化指令（SIMD），在单条指令周期内并发处理多个数据片段，而不是使用效率低下的 for 循环逐个跑指令；再者，它内置了高效的压缩机制；此外，它采用了日志结构存储（LSM 类似的追加写入机制），先将大量变更追加写入以保证尽可能快地摄取数据，然后在后台异步进行数据压实合并，并以更高效率的格式存放。

这些核心架构理念的很大一部分，实际上源自 Snowflake 所做的工作；而在 Snowflake 之前，还有一个名为 VectorWise 的系统——准确地说是 MonetDB/X100，后来商业化为 VectorWise，出自 CWI（荷兰国家数学与计算机科学研究中心），也就是后来诞生 DuckDB 的同一个学术摇篮。因此，学术界与工业界在列存系统、分析型系统以及实时分析系统上积累的许多理念，其实是一路脉络相承、传承下来的。但是在 2016 年，至少据我所知，还没有任何开源项目能够集这些技术之大成。

因此，当 ClickHouse 横空出世并宣称：“看，我们基于前人所有的这些研究成果实现了整套系统”，这确实让人叹为观止。从那以后，DuckDB 实现了类似的机制，阿姆斯特丹团队开发的 Polars 也是如此；Firebolt 最初是基于 ClickHouse 的分支并重写了内部许多模块，如今也具备了这些特性；Databricks 也推出了他们自己的执行引擎。所以现在每个人都采用了这种建立在 Snowflake 和 VectorWise 工作基础上的经典架构。在 2016 年这极其新潮，而今天它已经变成了行业准入门槛（table stakes）。我认为 ClickHouse 多年来做得格外优秀的一点，就是在此基础上持续将性能推向极致，并不断拓宽其能够承载的工作负载边界。

<details>
<summary>Original English</summary>

**Researcher**: So, so I would say the architecture of click house the the the the core fundamentals uh is by 2026 standards is not novel by 2016 certainly was um the the nature of like you're going to store data in this columnar layout. So instead you know storing all the attributes all the data for for a single column together continuously versus like in a row store you store all the values for all the columns of of a single tuple continuously like storing things like that manner using uh vectorzed instructions on CPUs to to process mult multiple pieces of data at the same time within uh you know one single instruction versus like having to do four loops and and run things uh less efficiently. um the the built-in compression mechanisms, the uh the way they doing a log structure storage where you're appending a bunch of changes and then because you want to ingest as fast as possible then eventually in the background you'll compact it and store it in a more efficient manner. A lot of that those ideas uh of the core architecture come from the work done at at snowflake and prior to snowflake there was another system called vector-wise or x100 sorry the monb x100 which then became commercialized as vector-wise uh from CWI which is the same school where ductb was was built so a lot of the ideas that people have been developed for these column store systems and analytical systems and and real time analytical systems have been sort of floating down. Um, but nothing was open source in 2016 at least as far as I know that did all these things. So when click house came out of the game like hey we have all this stuff based on all this research that that people have done before. It was amazing right and since then you know ductb has something similar polers from the guys in in Amsterdam firebolt started off as a fork at click house and they rewrote a bunch of stuff inside and now they have all these things like data bricks has their own version engine. So everyone has this sort of this this architecture that is predicated or based upon the work done from snowflake and and the vector wise but now but again 2016 that was super novel now it's sort of table stakes and one of the things I think click house has done really well over the years is just keep improving the performance even further and expanding what workloads they can actually can support

</details>

### 核心应用场景与产品版图扩张

**投资人兼主持人**：从内部视角来看，你目前看到了 ClickHouse 的哪些典型用例？客户通常在用它做什么？

<details>
<summary>Original English</summary>

**Host / Investor**: and what what use cases are you seeing for click house from the inside what do you see customers do.

</details>

**研究员**：回到刚才谈到的话题，AI 智能体（Agent）相关的场景看起来也格外引人注目。人们正在利用 ClickHouse 来监控和观测这些智能体产生的遥测数据与运行信息，并且能够实时对其做出响应并进行即时查询。此外，在金融市场领域也有大量的应用，例如欺诈检测等场景——任何需要以极高速度摄取海量数据，随后能对数据提出极其复杂的问题，并在毫秒级而不是秒级内迅速获得查询结果的场景。我认为将这两者（高速摄取与毫秒级复杂查询）结合在一起的能力，让 ClickHouse 处于一个非常独特而有利的地位。

<details>
<summary>Original English</summary>

**Researcher**: So I think the going back to the agent stuff, the agent stuff seems really interesting too that like people are using this to observe the information uh the telemetry that these agents are generating and be able to react in them in real time and ask questions about them. There's a bunch of stuff done on the financial markets as well, fraud detection, anything where you want to be able to ingest data very quickly and then ask questions about it, complex questions about it very very quickly and get back things in in milliseconds rather than seconds like that. I think the combination of doing those two things uh is puts click house I think in a unique position

</details>

**投资人兼主持人**：ClickHouse 一直在拓展其产品版图的演进之路上，对吧？它最初是一个极其强大的实时 OLAP 分析型数据库，而现在通过收购 Langfuse 进军可观测性领域，还收购了其他业务。作为内部人员，你如何理解这一演化进程？所有这些拼图是如何有机结合在一起的？

<details>
<summary>Original English</summary>

**Host / Investor**: and click house has been on a journey uh to expand its product offering right so it started with this very powerful OLAP analytical realtime database and now it does it bought langu observability it bought um other things like how do you from the inside understand this evolution I mean does it all fit together.

</details>

**研究员**：其实有人问过我：你当初为什么选择加入 ClickHouse？再次说明……

<details>
<summary>Original English</summary>

**Researcher**: I mean, somebody asked me like why why did I join Click House? Uh, again,

</details>

<!-- chunk 8/11 -->

### 加入 ClickHouse 的商业逻辑与多领域扩展

**Guest**: 我才刚加入两个月，这感觉有点像你刚结婚，然后有人问你：“你为什么选你妻子或丈夫？”就像是回答：“噢，因为他们选择了我，对吧？”但实际情况远不止如此。坦白说，在我决定加入 ClickHouse 之前，他们在商业层面上所做的战略布局——这里指的是 ClickHouse 公司（ClickHouse Incorporated），而不是单纯指 ClickHouse 这个开源系统本身——如果换作是我来经营一家数据初创公司，我也会在商业层面采取完全相同的策略。比如，他们推出了托管 PostgreSQL 服务，而不仅仅是固守一个性能出色的单一 OLAP 引擎；他们没有直接从竞争白热化的 OLTP 领域起步；同时他们还构建了完整的监控、可视化和可观测性技术栈，不仅服务于传统的商业智能（BI）或传统数据分析，现在还全面延伸到了 AI Agent 和大语言模型（LLM）的场景。他们正在全方位拓展不同的垂直业务领域，让各种工作负载都能基于自身平台去构建。在我看来，所有这些商业举措都完全合乎逻辑，节奏非常合拍。

<details>
<summary>Original English</summary>

**Guest**: I'm only two months into this and it's kind of like asking like, you know, like you just got married and somebody asked you why did you choose your wife or husband? Like, oh, because they chose me, right? Like, uh, it's a bit more than that. No, like honestly, before I decided to join Click House, they were doing things at the business level—like so this is Click House Incorporated, not Click House the system. They would do things at the business level that I would have done if I was running a data startup. Like they were having a Postgres offering, not just a single, you know, OLAP engine that's really good; not starting in the OLTP space; having the monitoring, the visualization, the observability stack, not just for traditional BI or traditional data, but also now the agents and the LLMs. Like they're doing all the things to expand out different verticals that build on their platform. All that to me, they all make sense in tracks.

</details>

### 数据库市场的融合趋势：OLAP 与 OLTP 是否走向统一？

**Host**: 顺着这个话题，我们或许可以探讨一下当前数据库市场的格局。我们前面已经多次提及这个话题，但现在不妨把它们串联起来综合看一下。正如你刚才提到的，ClickHouse 所做的一项重要举措就是增加了一项托管 PostgreSQL 服务。这显然是一个非常明确的行业趋势：Databricks 收购了 Neon，我想 Snowflake 去年也完成了一笔收购……

<details>
<summary>Original English</summary>

**Host**: Maybe segueing into the state of the database market in 2024. We've alluded to a bunch of this already, but like to put it all together. So one thing that ClickHouse has done, as you mentioned, was adding a Postgres service, a managed Postgres service. It seems that it's a clear trend. So Databricks bought Neon, I think Snowflake made an acquisition—

</details>

**Guest**: 去年收购了 Crunchy Data。

<details>
<summary>Original English</summary>

**Guest**: Crunchy last year.

</details>

**Host**: 分析型数据库（OLAP）与事务型数据库（OLTP）的这种走向融合，究竟是不是未来的大势所趋？这种融合主要是出于商业驱动，为了向同一批客户推销更多产品，还是说它背后本身就有着非常明确的工业级产品内在逻辑？

<details>
<summary>Original English</summary>

**Host**: That convergence of analytical databases and transactional databases, is that the future? Is that driven by commercial and business reasons so you can sell more to the same customer, or is there an industrial sort of product logic to it?

</details>

**Guest**: 这里其实包含两个层面的问题。首先，一家数据库公司是否应该同时提供 OLTP（事务型/操作型数据系统）和 OLAP（分析型系统）？至于它们在底层究竟应该是两个独立的系统，还是融为一个系统，那是一个更宏大、更值得深入探讨的话题。但一家公司是否应该兼备这两者？答案是肯定的。

回过头来看 AI Agent 带来的能力提升：维护这些复杂的系统固然仍然是一大挑战，但是如今推出并部署一套 PostgreSQL 托管服务的门槛，确实已经被大大降低了。

我脑海中还有一个猜想：对于一家初创公司而言，究竟是从分析型数据库（OLAP）起步、后续再增加 OLTP 事务型产品更好，还是从 OLTP 起步、后续再增加 OLAP 产品更好？

我知道我说这话可能带有偏见，毕竟我现在人在 ClickHouse。但你看 Databricks 的路径，再看 ClickHouse 的路径，在我看来，这显然是更正确的发展路径：如果你想创办一家全新的数据初创公司，先从分析领域切入，在分析场景中建立起足够的用户吸引力和市场份额，然后再顺势推出 OLTP 产品。虽然我无法从纯理论上严格证明原因，但单从商业运作和市场竞争的角度来看，这似乎是明智得多的打法。

接下来核心问题就变成了：你究竟应该提供一个统一的 API、统一的界面或单一的逻辑端点，让用户感知上是在一个单一数据库实例上同时运行事务与分析，还是应该把它们作为完全独立的服务来提供？

ClickHouse 目前的做法是提供独立的服务，但他们提供了一条极其高效的高速通道，能将数据快速从 PostgreSQL 事务端同步到 ClickHouse 分析端。而 Databricks 今年公布的方案则是针对其 Lakebase 的 HTAP/混合事务与分析路线：你可以在 PostgreSQL（Lakebase / Neon）上运行日常事务，然后分析型引擎能够直接读取底层数据，这样你就不需要像 ClickHouse 或其他系统那样去额外维护两份完全独立的数据拷贝。

其实，“拥有两个计算引擎但只保留一份统一数据拷贝”的思路并不是什么新鲜事物。早在 2010 年代，就有一家名为 Splice Machine 的初创公司。我当时其实担任过他们的顾问，因为他们的创始人是卡耐基梅隆大学（CMU）的校友，他特意邀请我去做顾问。当时他们的架构是基于 HBase 加 Spark SQL，但底层只维护一份行存储（Row Store）的数据副本。

事实上，从数据库诞生之初，人们就一直梦寐以求想要这种 HTAP 系统（混合事务与分析处理系统）。然而，其核心难点和工程挑战始终在于：你该如何调和某些数据仍然停留在行存储中、而另一些数据已经转换进入列存储（Column Store）之间的状态差异？大型商业数据库厂商（比如 Oracle、SQL Server）的做法通常是在内部存储两份数据拷贝——一份行存、一份列存，这被称为分形镜像（fractured mirror）方案——并在内部设计专门的机制来实时同步两者。

但是，这种混合架构方案之所以在历史上从未真正大获成功，核心阻碍在于不同业务场景背后的组织利益相关者始终想要各自领域里“最极致”的产品。负责支撑核心业务应用程序的 OLTP 团队，根本不想要一个“处理业务事务尚可、做做分析也马马虎虎”的中庸系统；他们要的是业界最顶级的操作型数据系统。无论好坏，目前在操作型领域这个无可争议的最佳选择就是 PostgreSQL。而且这里所谓的“最佳”并不单指执行性能，它涵盖了生态、稳定性和广泛认同度等多重考量。

分析团队也是同理。你绝不想要一个“分析凑合能用、还能顺带兼顾事务”的妥协型系统，分析人员唯一想要的就是市面上最优秀的专业分析系统。正因如此，这种组织割裂和诉求差异，一直是阻碍 HTAP 混合系统在商业化落地和市场推广（GTM）上面临的最大现实挑战。

不过，我认为 Databricks 现在可能处于一个非常有利的破局位置，完全有机会把这件事做成。因为他们已经在分析侧建立了庞大的市场壁垒——从机器学习到现代数据仓库，他们已经牢牢占据了分析领域的生态高地，现在他们只是往里面补充 OLTP 能力。同样，ClickHouse 也有潜力沿着类似的轨迹去推进这一目标。

虽然这些讨论已经深入到了数据系统架构的微观细节，但不可否认，所有人一直以来都想要这样的终极系统。然而现实中的核心瓶颈往往并不仅仅是纯粹的工程实现难题，很多时候更是由组织架构分工和人性诉求所决定的客观阻力。

<details>
<summary>Original English</summary>

**Guest**: But there's two things: like should a database company offer both an OLTP transactional operational data system and an OLAP system, or at least whether or not they're separate systems or not, that's up for larger discussion. Should you do that? Yes. I mean going back to what agents allow you to do, like obviously maintaining these things is still a challenge, but the bar of entry of deploying a Postgres offering has certainly been reduced.

Another conjecture I have in my mind is like, is it better for an analytical company, a startup that starts with an analytical database, to then later on add an OLTP offering, versus an OLTP company then later add an OLAP offering? I think—again, I realize I'm saying this and I'm biased because of ClickHouse, but like you look at what Databricks did, you look at what ClickHouse has done, to me that appears that's the right path to do this. Like if you want to start a new data startup, start doing analytics first, get traction there, then you can add the OLTP offering. But I can't prove why, just from the business perspective it seems to be the smarter play.

Now the question is like, okay, should you have a single API, single interface, or a single logical endpoint that allows people to run transactions and analytics on what is perceived as a single database instance, or should they sort of be separate services? ClickHouse right now is separate services, but they have a fast path to get the data out of the OLTP side from Postgres into ClickHouse.

What Databricks announced this year was their HTAP engine or HTAP story for their Lakebase, where you can run your transactions on Postgres or Lakebase or Neon and then have the OLAP engine be able to read that data directly, so that you don't have to make two copies of it in the way ClickHouse does or other systems do.

So that idea is not new, to have like this sort of two engines but like one copy of the data. There was a previous startup in the 2010s called Splice Machine, which actually I was an adviser for, because the founder was a CMU alumni and he asked me to be an adviser for them. But they were running HBase plus Spark SQL, but they had a single copy of the data that was a row store.

I mean people have been wanting these HTAP systems or these hybrid systems since the very beginning. The challenge has always been like how do you reconcile the fact that like some of the data might be still in the row store versus the column store. And like the major commercial vendors like Oracle, SQL Server, they'll store two copies—one the row store and the column store, it's called fractured mirror approach—and they have an internal mechanism to synchronize these things.

But the challenge has always been, why this sort of hybrid approach has never taken off, is because the stakeholders at organizations or companies for these two different sort of categories of workloads have always wanted their own best thing. Like the OLTP team, the people running the applications operational side, they don't want something that kind of does okay at operations and can do okay analytics; they want the best operational data system. For better or worse, that's Postgres now, right? And best is not always in terms of performance, could be a variety of reasons why it's considered the best. And same thing for analytics: you don't want a system that kind of does okay in analytics and does okay on operational workloads. I want the best analytical system.

And so that's always been the business challenge, the go-to-market challenge for these hybrid systems. I think though Databricks might be in a good position to potentially pull this off because they already have that sort of market from the analytical side, machine learning side, and the data warehouse side, and now you're just adding in this OLTP side. And so ClickHouse could potentially pursue the same thing. That's getting kind of in the weeds of data system architectures. But I think everyone has always wanted this. The challenge though often isn't always just pure engineering; there might be the organizational reasons or human reasons why you can't achieve this.

</details>

**Host**: 是的，这非常引人深思。如果我们把这个逻辑梳理一遍：在对外呈现上，你完全可以对最终用户屏蔽掉背后的复杂性——这意味着你可以使用一个大语言模型（LLM）来翻译用户的查询意图，充当一个智能路由器的角色。然而，从底层架构的角度来看，把它们合二为一极其困难；而从企业组织分工的角度来看，强行融合往往也行不通，因为用户始终想要的是各自领域最顶尖的最佳选择（Best-of-breed），而不是……

<details>
<summary>Original English</summary>

**Host**: Yeah, super interesting. So to play it back, you could abstract away the complexity to the user, meaning that you could have presumably an LLM that translates your query into—yeah, exactly, a router. However, from a fundamental architecture perspective, it's very hard to combine, and from an organizational perspective, it may not make sense because people want the best of breed, not—

</details>

### 向量数据库的行业前景：消亡还是进化？

**Guest**: 但在许多场景下，PostgreSQL 本身就已经成为了公认的最佳选择。因此，如果你的前端形态直接押注在 PostgreSQL 上，提供一个完全兼容 PostgreSQL 的部署环境，或许就能克服这个阻力。

接下来谈谈数据库市场的其他细分领域，比如我们之前聊到的向量数据库。你对向量数据库未来的发展前景怎么看？是看好（Thumbs up）还是看衰（Thumbs down）？

<details>
<summary>Original English</summary>

**Guest**: But Postgres is the best of breed now in many cases. So betting on your front end as a Postgres deployment that is compatible with Postgres, that might overcome that issue. So to talk about other parts of the database market, we talked about vector databases. So is that thumbs up or thumbs down?

</details>

**Host**: 这里的“看好还是看衰”，是指它值不值得投资，还是指……？

<details>
<summary>Original English</summary>

**Host**: What is thumbs up, thumbs down? Like in terms of like is that a good business to get invest in, or like—

</details>

**Guest**: 是指在如今人人都具备向量检索能力的大背景下，这批纯向量数据库公司究竟还能不能继续生存下去。

过去在大学当教授的时候，我经常能通过各种渠道听到各种八卦和风声，了解哪家公司发展得好、哪家经营得不好——这些消息往往来自投资人、离职员工，或者是去各大公司实习、面试归来的学生。通过从各方拼凑而来的点滴零散信息，大致就能勾勒出整个数据行业的技术版图。

而现在加入 ClickHouse 之后，我几乎能看清全局的所有细节，正如作为一名投资人一样能洞悉行业全貌。

据我所知，目前有一家向量数据库公司发展得非常出色，那就是 Turbopuffer。他们在向量检索领域做到了极度的专注与特化，并且提供了远超竞争对手的极致性价比。

因此，我认为独立的向量数据库绝不会轻易消亡。相反，我认为它们未来会沿着两条路径演化：

其一，它们必须演变为类似 PostgreSQL 或 MySQL 那样通用的完整数据系统，成为核心业务的权威记录系统（System of Record）——也就是说，系统不仅要存储向量索引，还要直接持久化存储原始的数据元组（Tuple）记录……

<details>
<summary>Original English</summary>

**Guest**: Are they going to be around now that, you know, everybody else and their brother has a vector search capability?

One of the things that happened before when I was a professor is like, I would always get—you always hear rumors about who's doing well, not doing well, through a combination of either the investors or former employees, or students that maybe go to internships or interview some places and they come back. So you get sort of bits of information from everyone to kind of piece together what the data landscape looks like. The problem is now, being in ClickHouse, now I see everything, like as an investor you see everything too.

The one vector database company that I know is doing very well is Turbopuffer. And they are hyper-specialized in doing vector search and at a cost-performance ratio that's much better than everyone else.

So I don't think that the vector databases are going to go away. I think that they'll evolve in two ways: they'll have to become either a sort of general-purpose system like a Postgres, like a MySQL, where they become the system of record where you're storing the original tuples plus—

</details>

<!-- chunk 9/11 -->

### 专用向量检索的定位：外挂系统与“Postgres 将死”的伪命题

**Andy Pavlo**：……为它们生成嵌入向量，或者转变成类似 Elasticsearch 的形态——在那里存在一个独立的系统，持有一份从业务运行侧（OLTP 侧）同步过来的数据副本。在那种情况下，它们可以非常惬意地作为一种附加的外挂组件而存在。如果你追求向量搜索极致的原始性能，那么在某些场景下，你可能确实不得不求助于这些专门的独立系统。因此，我认为这种系统并不会消失。我只是不赞同外界的某些极端论调——我曾看到过类似“Postgres 将会被向量数据库彻底消灭”这样的预测。这是根本不可能发生的，对吧，绝对不会发生。

<details>
<summary>Original English</summary>

**Andy Pavlo**: ...the embeddings or the vectors for them or they become like an Elasticsearch where there's like a separate system, they have a copy of the data that's being pulled from the operational side. And in that case they can live sort of comfortably as being this additional thing you add on, and if you want the raw best performance of vector search, in some cases you may have to go to one of these specialized systems. So I don't think that's going to go away. I just don't think—I've seen predictions of like, "oh Postgres is going to die at the hands of a vector database." That's not happening, right, that's not happening.

</details>

**Matt Turk**：情况其实恰恰相反，对吧。完全是反过来的。

<details>
<summary>Original English</summary>

**Matt Turk**: Very much the opposite, right. Yes.

</details>

### 图数据库的真实处境：Hacker News 赌局与 SQL 属性图的降维打击

**Matt Turk**：我们在一开始也提到了图数据库。你知道的，虽然并不是要故意针对他们，但比如像 Neo4j 这样的图数据库，问世至今已经有整整二十年了。

<details>
<summary>Original English</summary>

**Matt Turk**: Graph databases we mentioned at the beginning. So, you know, not to pick on them, but like Neo4j has been around for 20 years now.

</details>

**Andy Pavlo**：确实是这样，是的。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Sure. Yes.

</details>

**Matt Turk**：而且大家都曾以为，随着 AI 的爆发，图数据库的高光时刻终于要到来了，对吧？那么，图数据库领域现在到底发生着什么？

<details>
<summary>Original English</summary>

**Matt Turk**: And this was supposed to be the moment, right, for graph databases, AI. So, what's happening there?

</details>

**Andy Pavlo**：我想说的是，我和 Hacker News 上的某个人还有一个悬而未决的赌局。那个人声称，到 2030 年，图数据库的市场规模将会超越体量更庞大的关系型数据库市场。如果这个预言真的成真，那我就会穿上一件印着“我爱图数据库”字样的 T 恤，并且用那张照片作为我驾照上的证件照、作为我的大学教职员工 ID 卡照片，而且我会把它挂在我的个人网站上，直到我死的那一天。你觉得呢？对此我感觉非常从容笃定。现在已经是 2026 年了，我们只剩下四年时间了。这根本不可能发生。

<details>
<summary>Original English</summary>

**Andy Pavlo**: I say I have an outstanding bet with somebody on Hacker News where they said that by the year 2030 the graph database market was going to overcome the larger relational database market. And if this becomes true, then I will wear a shirt that says "I love graph databases" and I will use that as my driver's license, my university ID. I'll put on my website till the day I die, right? I'm pretty comfortable. It's 2026. We got four years to go. This is not happening.

</details>

**Andy Pavlo**：不，图数据库一直以来都只是一个小众市场。我认为之所以如此，是因为站在我的学术研究视角来看，研究表明只要你在实现执行引擎时采用某些特定的技术——ClickHouse 确实做到了这一点，DuckDB 也实现了一部分——只要你做好了这些特定的底层优化，就能够极其高效地执行图的遍历。而图遍历在本质上不过就是在单张表上不断做自身连接（Self-Join）而已。你可以把这些连接操作实现得非常非常高效，并且可以轻而易举地在性能上击败 Neo4j。说实话，跟 Neo4j 比性能就像是在胜之不武地欺负人——说自己比 Neo4j 快，就好比说自己比一个坐轮椅的人跑得还要快一样，这完全是一种不体面的打击。

<details>
<summary>Original English</summary>

**Andy Pavlo**: No, it's always been a niche market. And I think that because my perspective on the research side, the research shows that if you do certain things in implementing the engine—which ClickHouse does do, DuckDB does some of this as well—there's things you can do that allow you to do the traversals of graphs, which essentially just joins, self-joins on a table. You can implement those things very, very efficiently, and you can easily outperform Neo4j. And that's kind of like—saying you're faster than Neo4j is like saying I'm faster than somebody that's in a wheelchair, right? You can run fast, that's a low blow.

</details>

**Andy Pavlo**：所以，我只是想说明，纵观所有的图数据库，我认为哪怕是其中做得最好的一批，面对一个集成了大量学术界前沿优化策略的现代系统（而这些优化策略现在已经陆续出现在某些现代系统中了），专用图数据库也是根本毫无胜算的。你唯一可能输给图数据库的情形，就是你在客户端和服务器端之间来回往返去搞图遍历——意思是说，“我得在客户端算出来我下一步想去查看哪个节点，然后再发回给客户端，由客户端决定接下来去遍历下一个什么节点”。如果你是在客户端和服务器端之间这样一趟趟来回折腾，是的，那专用图数据库确实能把你打得落花流水。但正如我刚才所说的，现在的 SQL 标准本身已经原生支持属性图查询（Property Graph Queries, SQL/PGQ）了。比如 Oracle 就具备这个能力，对吧？他们是这项 SQL 扩展的巨大推动者。这允许你直接在服务器端内部完成整套图遍历。因此，依我看，搞专用的独立图数据库就是一个非常糟糕的想法，根本没有任何理由让任何人真正想要去使用它们。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So, but I was just saying like all the graph databases, I think like even the best ones, you're just not going to—a system that has a bunch of these optimizations that are in the research and actually appearing in some of these systems now, you're just going to lose. What you will lose against a graph database is if you're doing the graph traversal with the client side and the server side, meaning like, "I've got to figure out what the next node I want to go look at, and go back to the client, and that decides the next node to go traverse." If you're doing that back and forth, yeah, they'll beat you guys. But like I said, the SQL standard now supports property graph queries. Oracle has this, right? They were a big pusher of this extension of SQL allows you to do that traversal on the server side. So like graph databases, I think a horrible idea. There's no reason why anyone would actually want to use them.

</details>

### GPU 数据库的复兴与现实挑战：英伟达收购潮与算力经济学

**Matt Turk**：那么 GPU 数据库呢？

<details>
<summary>Original English</summary>

**Matt Turk**: GPU databases.

</details>

**Andy Pavlo**：是的。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yes.

</details>

**Matt Turk**：我知道你在这个领域有着特殊的浓厚兴趣。过去曾经经历过一个周期：第一代产品横空出世，随后又烟消云散了。如今似乎正在迎来一场复兴。究竟什么是 GPU 数据库？对此你的预测又是什么？

<details>
<summary>Original English</summary>

**Matt Turk**: I know you have a special interest there. There was a cycle when the generation appeared then went away. There seems to be a renewal. What is a GPU database and what is your prediction?

</details>

**Andy Pavlo**：所谓 GPU 数据库，是一种部署在数据中心里的系统，其中查询的底层执行端完全被卸载（Offload）到 GPU 上运行——无论这个 GPU 是通过 PCIe 总线连接，还是安装在同一台机器内，抑或是运行在另一台专门的计算节点里。人们试图为数据系统打造专用硬件加速器的历史，实际上可以一直追溯到数据系统诞生之初。在 20 世纪 70 年代，它们被称为“数据库机”（Database Machines）。当时人们会制造专用的专用硬件来专门跑排序和各种查询执行算子。然而到了 20 世纪 80 年代初，这种做法显然彻底消亡了。因为等你费尽心机完成专用硬件的设计、流片和制造时，英特尔（Intel）或摩托罗拉（Motorola）早就推出了下一代通用 CPU，通用硬件性能大幅提升，你千辛万苦获得的加速优势瞬间荡然无存。因此，针对数据库的专用硬件加速器在 20 世纪 80 年代基本上就死透了。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So GPU database is a data center system where the execution end for queries is all offloaded to a GPU running on PCIe or running in you know in the same box or another box. Um so I mean the the history of people trying to build accelerators for data systems goes back to the beginning of data systems. The 1970s they were called database machines. So people would build specialized hardware to run sorting and and query execution operators. And that obviously died out in the early 1980s because by the time it take you to like design and fab new specialized hardware, you know, Intel or Motorola put out the next CPU or the hardware got better and just the gains you were getting went away. So hardware accelerators for databases basically died out in the 1980s.

</details>

**Andy Pavlo**：在 90 年代和 2000 年代，这个方向并没有太多动静。到了后来，你看到有人开始尝试用 FPGA 来做数据库加速，而且时至今日这种想法每隔一段时间还会重新冒头。一些云厂商确实在做一点这方面的尝试，但他们通常只是把硬件加速用于网卡（NIC）上的数据包过滤，放在进来的网络侧做一些前置处理。至于 GPU 数据库，在 2010 年代曾经涌现出一大批初创系统在这方面进行尝试。我们当时在大学里还专门组织过一系列研讨会，邀请了所有做 GPU 数据库的团队过来做演讲，分享他们的实践、他们的架构，以及为什么他们能比现有的传统系统跑得更快。

<details>
<summary>Original English</summary>

**Andy Pavlo**: There wasn't a lot of activity in the 90s, 2000s. You saw sort of the rise of people trying to do FPGAs for databases and every so often that comes back now. Some of the cloud vendors do a little bit of these things, but usually like to filter things on the NIC, on the network side of things coming in. So where GPU databases—again, there was a bunch of systems in the 2010s that were trying this. We did a seminar series at the university. We invited all the GPU database guys come and give talks about you know what they were doing, how they were you know why they were faster than existing systems.

</details>

**Andy Pavlo**：但在那个时候，这些系统面临的致命挑战在于，你必须把整个数据库完整地放进 GPU 的显存内部。因为如果必须通过 PCIe 总线在主机内存和显卡之间来回倒腾数据，速度简直慢得令人发指。后来那一批初创公司大都在挣扎中逐渐销声匿迹了，其中只有少数几家坚持活了下来，但它们基本上退守到了专门处理数据可视化的细分利基市场。然后就在过去这一年左右的时间里，英伟达（Nvidia）基本上把一批在苦苦挣扎的 GPU 数据库初创公司给大举吞并收购了。我曾经担任过其中一家名为 Voltron 的公司的顾问；英伟达不仅收了它们，还顺手把 HeavyDB 也给收购拿下了。所以，英伟达现在可以说是全方位、毫不保留地在这个方向全力押注。

<details>
<summary>Original English</summary>

**Andy Pavlo**: And the big challenge at the time was like with those systems you had to put the entire database on the inside the memory of the GPU, because if you had to go back up through PCIe it was just way too slow. And a bunch of those startups sort of fizzled out; some of them are still around, but they're sort of specialized for doing visualizations. And then there was in the last year or so, Nvidia's basically gobbled up a bunch of these GPU database companies that were kind of like struggling along. And I was an adviser for one of them called Voltron. But they also picked up HeavyDB, and so Nvidia is going all in on this now.

</details>

**Andy Pavlo**：因此，长远来看，构建纯基于 CPU 的数据库系统的理念是否依然稳固如初，目前仍有待观察。不过我听到的依然是毁誉参半的各方反馈：比如微软（Microsoft）已经在公有云中推出了能够利用 GPU 进行分析加速的云数据系统方案，这是完全公开的信息；但另一家主流数据库巨头公司——我不能透露他们的具体名字——他们在评估了使用 GPU 的经济成本模型后，直接得出结论认为这根本不划算。我以前指导过的一位博士生，现在是威斯康星大学（University of Wisconsin）的教授，目前正处于学术休假状态在英伟达工作。他们正在做一个名为 Cirrus DB 的项目，它严格来说并不算是一个全新打造的数据系统，而是充当现有系统与底层 C 语言/执行层之间的一个中间层。它的作用比如是直接拦截并接管 DuckDB 的查询，然后把计算下推到 GPU 上去运行。我认为他们这套机制在 Apache Doris、StarRocks 以及 DataFusion 上同样行得通。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So it remains to be seen whether like the idea that you're going to build a CPU-only database system long-term whether that's going to still hold. I've heard again mixed reports: like this is public, Microsoft has offerings now in the cloud that can be accelerated for your data system, can be accelerated by GPUs for analytics. Another major database company—I can't say who they are—they looked at the economics of GPUs and decided it wasn't worth it. So one of my former students now is a professor at University of Wisconsin. They're now on leave at Nvidia. They have a project called Cirrus DB, which is not necessarily a new data system, but it's a layer in between an existing system and like the C, and so it supports taking DuckDB queries and running that down on the GPU. I think they can do this in Doris or StarRocks and DataFusion.

</details>

**Andy Pavlo**：因此在 ClickHouse 内部，我们最近也一直在深入调研并关注这个方向，但这目前依然处于前沿研究阶段。我倒不是排斥它，只是这其中有许多耐人寻味的课题需要弄清楚：比如在 ClickHouse 预期的数据格式与 CUDA 所要求的数据内存布局之间，到底需要做多少格式转换开销？又该如何在这些不同的异构计算组件之间组织内存或高效共享内存？这套方案到底是否具备真正的商业与技术合理性，目前依然有待验证（TBA）。但这背后无疑凝聚着巨大的学术研究力量。而在公开层面上我也完全可以说：英伟达之所以如此卖力地力推这一切，显然是因为这样能帮他们卖出更多的 GPU，对吧？毕竟现在想采购到新的 CPU 已经足够困难了，所有人都受制于计算瓶颈，内存也变得极难买到。现在的各种计算硬件不仅极其昂贵而且极度紧缺，而在所有的硬件中，GPU 偏偏又是最难搞到、价格最昂贵的存在。现在你居然跑来跟我说，你的一整套数据库底座都要全盘跑在 GPU 之上？我不知道至少在短期内这到底是否合乎算力经济学的常理。但如果带来的性能飞跃确实极其显著——正如一部分科研成果所展示的那样——那么它或许真能行得通。

<details>
<summary>Original English</summary>

**Andy Pavlo**: And so at ClickHouse we've been potentially looking at this as well, but it's research. It's interesting to see how much you have to do translation between how ClickHouse expects things and how CUDA wants things to be—the data layout and so forth. How do you organize memory or share memory between these different components? TBA, remains to be seen whether this actually makes sense, but certainly there's a lot of research energy behind this. And publicly I can say this: like Nvidia is obviously pushing this because it'll sell more GPUs, right? Because it's hard enough to get new CPUs. Everyone's compute-bound or memory is hard to get. I said the computing hardware is very expensive, hard to get now, and GPUs of all the things is the most expensive hardware to get, and now you're going to say your entire database is going to run off GPU. I don't know if that makes sense at least in the short term. But if the performance improvements are quite significant, and some of the research shows that, maybe it makes sense.

</details>

### 新兴硬件利基与教训：Intel Optane 的黄昏与内存计算的探索

**Matt Turk**：在数据库领域中，是否存在某个正在崭露头角的新兴类别，或者在某个已有类别中，是否存在一个人们至今还没给予足够讨论的利基方向？

<details>
<summary>Original English</summary>

**Matt Turk**: Is there an emerging category or maybe a niche somewhere within a category that people don't talk about enough yet—

</details>

**Andy Pavlo**：是指数据库层面的吗？

<details>
<summary>Original English</summary>

**Andy Pavlo**: —of databases?

</details>

**Matt Turk**：对，没错。

<details>
<summary>Original English</summary>

**Matt Turk**: Yeah.

</details>

**Andy Pavlo**：我的意思是，你永远可以为了崭新的新型硬件去构建全新的数据系统。但是，在这个方向上我以往的历史记录可以说是相当糟糕的。就拿我们在实验性硬件上做过的一大堆科研项目来说，那些硬件项目几乎无一例外最后都被厂商直接砍掉了；甚至有些硬件其实都算不上多么具有实验性。比如英特尔之前推出来的 Optane 傲腾非易失性持久化内存（Persistent Memory）产品线。我和我的实验室曾围绕着为那种新型内存构建数据系统做过大量的深入研究。因为你想想看，一旦你假定你的 DRAM 内存变成了持久化的——意思就是哪怕你把电源插头直接拔掉，内存里的任何数据也绝不会丢失——这将会从最根本的核心层面彻底颠覆你构建数据系统的基本范式。我们围绕着这一特性倾注了大量心血，展开了极其深入的系统研发工作。然而结果呢？英特尔转头就把整个傲腾产品线给彻底砍掉了。此外，我们当时还在开展另一项关于内存内计算（Processing-in-Memory, PIM）的前沿研究……

<details>
<summary>Original English</summary>

**Andy Pavlo**: I mean you can always build new data systems for new hardware, but my track record on this is terrible in terms of like, we've done a bunch of research on experimental hardware and it always gets canceled. Or like it's even not that experimental. It's like you know Intel had this Optane persistent memory stuff. We did a bunch of research on building systems for that, because like if you assume now your DRAM is persistent—you know like, you pull the plug, you don't lose anything—that changes how you fundamentally build a data system. We did a bunch of work on that, and then Intel killed that product line. We were doing another research on processing-in-memory...

</details>

<!-- chunk 10/11 -->

### 硬件演进与近内存计算的尝试

**Speaker B**：……硬件。你可以想象这样一种场景：DRAM 内存条上直接集成了 CPU 核心，就位于 DIMM 内存模组之上。这样一来，数据系统就可以做出改变：以往我们需要把数据从内存拉取出来，加载到 CPU 缓存中，然后再在 CPU 上进行计算；而现在，我们可以直接把查询请求下发到 DIMM 内存条本身，并在那里就地执行。

<details>
<summary>Original English</summary>

**Speaker B**: ...hardware. So think of like DRAM sticks with CPU cores directly on the DIMM. So the data system now can say, okay, instead of pulling things from memory, bringing them into my CPU caches, and then computing things on them, I'll just send the query down to the DIMM itself and run it there.

</details>

**Speaker B**：我们之前围绕这项技术做过大量工作，涉及一家名为 Upmem（原误作 opm）的公司，但该公司后来被高通收购，并在去年被砍掉了。所以那个方向最终没有成功。总之，围绕数据系统或新型硬件，总能开展大量的研究和工程工作。

<details>
<summary>Original English</summary>

**Speaker B**: We were doing a bunch of work on this, on this thing called Upmem that got bought by Qualcomm and got killed last year. So that didn't work out. So there's always a bunch of work you can do on data systems or new hardware.

</details>

**Speaker B**：不过我想说的是，其实我现在也没有确切的答案。这也是我目前在 ClickHouse 努力想要弄清楚的问题之一。正如我们在最开始讨论过的那样：AI 智能体（Agentic）的工作负载，是否与人类或现有应用程序当前的运行方式有着显著的不同？如果是，究竟为什么不同、如何不同？我们是否能针对这一点，对数据系统的开发架构做出调整，以便更好地利用这一特性？目前这仍有待观察，具体会如何发展尚无定论。

<details>
<summary>Original English</summary>

**Speaker B**: I would say that actually I don't know the answer right now. This is one of the things I'm trying to figure out at ClickHouse: like, and we talked about this in the very beginning, are agentic workloads significantly different than what humans or what existing applications do now? And if so, why or how, and could you—how would you change maybe the development of a data system to take better advantage of this? That remains to be seen how that works.

</details>

**Speaker B**：我认为查询优化领域始终存在很多非常有趣且极具挑战性的问题，那至今依然是数据系统中最困难的部分。增量物化视图也是另一大核心挑战。当然，这些并不是没有人思考过的新鲜事物，数十年来人们一直试图解决这些难题。因此，我认为当前对我而言最有趣、也最紧密相关的课题，还是智能体负载（agentic stuff）相关的探索——面对这些全新的应用模式，系统架构究竟需要发生怎样的改变？老实说，我目前还没有确切答案，因为我们还未真正见证这一模式的完全成型。

<details>
<summary>Original English</summary>

**Speaker B**: I think there's always a bunch of problems in query optimization that are interesting. That remains the hardest part about data systems. Incremental materialized views is another big challenge. Again, these are not things that no one else has thought of; people have been trying to do these things for decades. So I think the agentic stuff is probably the most interesting and relevant thing to me right now: like what changes with these in system architecture? And to be honest, I don't know the answer, I just haven't seen it yet.

</details>

### 数据库市场的历史周期与 AI 时代的“停滞”假象

**Speaker A**：我之所以问这个问题，是因为普遍感觉数据库市场当前正处于其发展历史中的一个非常特殊的时刻。在 2010 年代，这个领域曾经历过爆发式的创新和繁荣——有 SQL 与 NoSQL 的激烈交锋和演进，随后又崛起了 Databricks、Snowflake，以及现在的 ClickHouse。但在这种爆发之后，感觉整个行业在颠覆性突破方面似乎放缓了脚步，甚至有人会觉得有些停滞不前……

<details>
<summary>Original English</summary>

**Speaker A**: I'm asking because it generally feels like the database market is at a specific moment in its history, meaning that there was an explosion of activity in the 2010s. There's SQL versus NoSQL, that whole evolution, then there was the emergence of Databricks, Snowflake, now ClickHouse. But it seems that things have slowed down a little bit in terms of explosion, I guess—you know, stagnant, maybe?

</details>

**Speaker B**：对，但实际上我们以前也经历过完全相同的历史周期。在 20 世纪 70 年代和 80 年代，关系型数据库领域涌现出了大量的创新与活力；然而到了 90 年代，市场格局又逐渐稳固下来，围绕着几家大型核心企业形成了垄断，比如 Oracle、IBM 以及 Teradata。在那个时期，如果你仅仅从这些成熟巨头的视角来观察数据库领域，它看起来同样像是停滞了整整许多年。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah, no, but we've been through this trend before, right? There was a lot of activity in relational databases in the 1970s, 1980s, and then in the 1990s again, the market sort of solidified around these major enterprises: the Oracles, the IBMs, Teradatas. And then if your only viewpoint of databases were from those kind of companies, then yeah, it looked like it was been stagnant for years.

</details>

**Speaker B**：正如你所指出的，在 2000 年代到 2010 年代之间，数据库领域确实爆发了大量的新动向。但要是拿它跟当下的 AI 相比，那么世间的一切事物看起来都显得停滞不前。因为在整个计算机科学的历史长河中，从来没有出现过任何技术能像如今的 AI 这般迅猛——这感觉就像是给一头猎豹喂足了可卡因，再把它塞进一辆法拉利跑车里一样！人们研发和推动这些技术的迭代速度简直令人瞠目结舌，以至于相比之下，其他所有领域在表面上看起来都像是放缓、死气沉沉或是陷入了停滞。

<details>
<summary>Original English</summary>

**Speaker B**: But as you said, a lot of activity in the 2000s, 2010s. I mean, relative to AI, then everything looks stagnant, because in the history of computer science there's been nothing like that before. It's just like taking a cheetah, giving it a bunch of cocaine, and putting it in a Ferrari—like the amount of speed that people are developing these things is insane, so that everything looks slow or dead or stagnant at the bat.

</details>

**Speaker B**：但归根结底，我认为数据的体量依然至关重要。一个非常值得关注的核心问题正如你之前提到的成本与效率：如何在现有的硬件条件下压榨出极致的性能，以及如何竭尽全力降低这些基础设施的运行成本。这始终是一个值得不断探索和攻关的迷人挑战。

<details>
<summary>Original English</summary>

**Speaker B**: But at the end of the day, I think the volume is going to matter a lot. I think that one interesting question is, to your point, like cost and efficiency: like squeaking out the best performance you can get for the hardware that you have, trying to reduce that cost. That's always an interesting challenge that we could pursue.

</details>

**Speaker B**：但在根本层面上，我认为数据形态并不会发生翻天覆地的剧烈变革，以至于迫使我们把数十年来积累的所有数据库理论与知识全盘推翻。这就像我们绝不会发明出一套全新的算术或数学体系去推翻“1 + 1 = 2”一样。关系模型本身就是人类表示和组织数据的坚实基石，我们所做的一切无非是在不同的具体实现机制上进行探索和权衡。

<details>
<summary>Original English</summary>

**Speaker B**: But like at the end of the day, I don't think there's going to be a massive change in what data looks like that requires us to throw everything away that we've known about databases, in the same way like you wouldn't come up with a new notion of arithmetic or mathematics to replace 1 plus 1 equals 2. The relational model itself is the foundation of how you want to represent data, and it's just you can vary the implementations of that.

</details>

**Speaker B**：为了让这些系统在面向全新场景时更加高效，无疑还有大量的工程工作要做。但我并不认为我们会全盘抛弃现有体系，更不认为 AI 智能体需要某种人类此前完全无法想象的全新数据系统架构——归根结底，那种凭空重造轮子的想法是站不住脚的。因此，我认为最底层的数据本质并不会发生改变。

<details>
<summary>Original English</summary>

**Speaker B**: And so there's certainly a lot of work to make these systems more efficient for this. But I don't think you're going to throw everything away and like, you know, the agents need some kind of data system that you've never even conceived about. At the end of the day, it doesn't make sense. So I don't think that part changes.

</details>

### SQL 的未来地位与超专用数据系统的可能性

**Speaker B**：正如我之前所言，硬件总在推陈出新；同时在 SQL 本身的设计和执行层面，也肯定存在许多可以继续改进的地方。市场上总会有人试图取代 SQL，但我认为这可能是一场注定徒劳的尝试。不过，SQL 未来的存在形式可能会发生演变——就像现在几乎没有人再直接编写汇编语言一样，SQL 可能也会变成类似的底层抽象，因为 Text-to-SQL（自然语言转 SQL）的效果已经变得如此出色。

<details>
<summary>Original English</summary>

**Speaker B**: I think, as I said, always new hardware. I think there's certainly improvements that can be done for SQL. There's always going to be people trying to replace SQL; I think that might be a lost cause. Although SQL could end up being like how, in the same way that people don't write assembly anymore, SQL might end up being like that because text-to-SQL works so well.

</details>

**Speaker B**：我认为智能体方向超级有意思，而且不断追求并榨取更高的性能，至少在我看来，始终是一个非常值得去攻克的令人兴奋的挑战。你甚至可以设想一个极端的未来世界：我们不再为每一个应用都使用一个通用的数据系统，而是通过“Vibe Coding”直接针对某一个具体业务场景生成并量身定制一套专用数据系统，使其在该任务上达到超高度的专业化（hyper-specialized）。其实现在我们在某些查询层面上已经开始通过代码生成（code generation）或即时编译（JIT compilation）做类似的事情了，像 ClickHouse、PostgreSQL 以及德国团队开发的 Umbra 都有所实践。但在未来，如何实现更深层次的极致专用化，并确保这种超专用系统的可持续维护，或许会是一个更为宏大的研究课题。

<details>
<summary>Original English</summary>

**Speaker B**: I think the agent is super interesting, and I think getting better performance is always going to be, at least from my perspective, a fun challenge, things we can pursue. You can imagine a crazy world where you say, "I don't need a general-purpose data system anymore for every single application. I want to vibe-code exactly a data system that does this for this one thing, and can then be hyper-specialized." You kind of do this now with code generation or just-in-time compilation for some aspects of queries, and some systems do that—ClickHouse, Postgres, Umbra out of the Germans. But hyperspecialization and making that be sustainable might be a bigger research question going forward.

</details>

### 数据基础设施的不可替代性与行业格局

**Speaker A**：所以这是一种看似矛盾的局面：一方面，从演进与创新的角度来看，这个行业目前似乎显得有些平静甚至停滞；但与此同时，正如我们在刚才的交流中达成共识的那样，数据这一底层基础架构本身却比以往任何时候都更加举足轻重。这也正是为什么你的朋友拉里·埃里森（Larry Ellison）能够成为或一度成为全球首富的原因之一……

<details>
<summary>Original English</summary>

**Speaker A**: So it's this—I don't know if it's a paradoxical kind of situation, but on the one hand it's a bit of a stagnant industry right now in terms of evolution. At the same time, as we've hopefully established through the conversation, the layer itself is as important as ever, which is one of the reasons why your friend Larry Ellison is close to the richest man in the world—or was.

</details>

**Speaker B**：他曾经是，不过截至今天他的排名有所下滑了。

<details>
<summary>Original English</summary>

**Speaker B**: He was; he's down as of today.

</details>

**Speaker A**：我的意思是，Oracle 如今的发展早已远远超越了一家单纯的数据库公司，但拉里依然是这家企业的核心象征。

<details>
<summary>Original English</summary>

**Speaker A**: I mean, Oracle is a lot more than just a database company, but he's still the corporate...

</details>

**Speaker B**：就连他们公司的总部大楼外观都被设计成了一个数据库磁盘的圆柱造型！所以你看……

<details>
<summary>Original English</summary>

**Speaker B**: I mean, the headquarters is the shape of a database. So, like...

</details>

**Speaker A**：没错，确实如此！哪怕不提别的，单单这一点就足以体现出数据库在整个计算世界中具有多么不可撼动的根本重要性。

<details>
<summary>Original English</summary>

**Speaker A**: Yes, yeah, yes, yes, yes. But if nothing else, that shows the fundamental importance of databases in the...

</details>

**Speaker B**：我想说的是，你看现在的操作系统领域，几乎没有人会去认真尝试推翻并取代 Linux，对吧？当然，针对不同的特殊运行环境、特殊硬件等，市面上确实存在一些小众的分支操作系统。但绝对没有人试图去大规模构建一套彻底替代 Linux 的全新操作系统。比如 FreeBSD，它源于加州大学伯克利分校的 BSD，历史比 Linux 还要悠久，所以它至今依然存在。而在数据库领域，人们总会涌现出新的想法，或者总是坚信自己能比别人做得更出色。

<details>
<summary>Original English</summary>

**Speaker B**: I would say, like, no one is trying to make a serious attempt to replace Linux, right? I mean, yes, there's niche operating systems for different environments, different hardware, and things like that, but no one's trying to build a significant-scale replacement for Linux entirely. Like FreeBSD, that predates Linux from the BSD or from Berkeley, so that's why it's still around. But for databases, there's always new ideas, or people think they can do things better than others.

</details>

**Speaker B**：因此，我并不认同数据库行业处于停滞状态。我只能说，在短期内，行业里很大一部分精力都会高度聚焦在 PostgreSQL 上，我们确实可以在 PostgreSQL 之上做很多优化与提升。与此同时，我坚信各类专用引擎依然会不断涌现。虽然我无法预测下一代主流工作负载会是什么——正如我刚才所说，目前我还不确定智能体工作负载是否会有根本性的颠覆，因为它们在建模应用行为时，许多底层操作依然是相似的，比如向量检索（Vector Lookups），它真的和过去的系统有质的差别吗？你只需要增加额外的执行算子和专用索引来支撑即可。但无论如何，下一代全新的负载必然会出现，这在历史上从未缺席过。

<details>
<summary>Original English</summary>

**Speaker B**: So like I wouldn't say it's stagnant. I would just say that a lot of the energy is going to be focused on Postgres in the short term, and there's certain things we can do to improve it. Meanwhile, I still think there will be these sort of specialized engines, and I don't know what the next workload is. Again, it's not clear to me agentic workloads are significantly different, right? Because they're modeling things that are how humans design applications. Like the vector lookups—are they significantly different than what was in the past? You needed additional operators; you didn't need entirely different concepts, you just needed additional indexes to do those things. It's not clear what the next thing is, but there will be something. There always is.

</details>

### 未来五年的竞争：核心引擎与周边生态的深水区

**Speaker A**：那么，或许我们可以以此来作为总结。放眼未来的五年，我们目前未必能看清具体会变成什么样。但在这过渡期间，这是否意味着像 ClickHouse 这样的现存头部公司只需不断迭代变强并巩固阵地即可？毕竟根本性的业务需求始终存在，而不会再轻易爆发一波颠覆它们的小型初创公司浪潮？

<details>
<summary>Original English</summary>

**Speaker A**: So maybe to finish on that: for the next five years, we don't know necessarily what that looks like. But in the meantime, does it mean the current companies, the ClickHouses of the world, just keep getting better and established because the fundamental need exists, and there's not a new wave of smaller startups?

</details>

**Speaker B**：当你提到“变好”（better）时，其实这个概念包含两个不同的维度。第一种“变好”是指：现有的查询能不能跑得更快？答案是肯定的，ClickHouse 在这方面确实还有进一步提升的空间，我们能够让它变得更快，其他数据库产品也可以做到这一点。

<details>
<summary>Original English</summary>

**Speaker B**: When you say "better", though, there's two notions of better. There's like: can existing queries run faster? Yes, ClickHouse has room for improvement, we can improve that; other stuff can do the same thing.

</details>

**Speaker B**：但正如我前面所讲，从高层架构来看，ClickHouse 目前所走的技术路线，与 Snowflake 在 2013 年所做的探索是非常相似的；而 Databricks 基本上也是在借鉴融合已有的成熟架构思想。至少在分析型（Analytics）场景下，各家大体上都在做着殊途同归的事情。因此，真正决定胜负的关键，也是 Snowflake 当年之所以取得巨大成功的重要秘诀之一，恰恰在于数据系统本身周边的全套体验——例如用户界面、开发者体验等等……

<details>
<summary>Original English</summary>

**Speaker B**: But like I said, the architecture at a high level or what ClickHouse is doing is similar to what Snowflake did in 2013; Databricks is basically copying some of the existing ideas as well. Like, everyone is kind of doing the same thing, at least for analytics. And what really matters, and one of the things that Snowflake did right as part of its success, is the stuff around the data system—like the user interface, developer experience, and so on.

</details>

<!-- chunk 11/11 -->

### 数据库周边生态与基础架构的价值

**Andy Pavlo**: 比如构建用于摄取数据、并与其他系统互操作的能力，这部分他们做得非常出色。所以，这就像是围绕基础数据库管理系统周边的脚手架和辅助设施，其实起着至关重要的作用。ClickHouse 正在做的一件事，虽然在我看来这并不算前沿学术研究，但这确实是他们随着时间推移越做越好的方面之一，这也帮助扩展了该系统的适用场景与覆盖范围。

<details>
<summary>Original English</summary>

**Andy Pavlo**: ...building to ingest data, interoperate with other things, that part they did really well. So it's almost like the things around, the scaffolding of the foundational, of a database management system that actually matters a lot. And one of the things that ClickHouse is actually—you know, to me it's not research, but this is one of the things they are doing better over time, and helps expand the reach of what you can use the system for.

</details>

**Andy Pavlo**: 因此，系统最核心的内核固然还有可以改进的空间，但从最底层的本质来看，ClickHouse 所做的事情与其他系统相比其实非常相似。然而，围绕在核心之外的周边配套生态却极其重要。我认为 ClickHouse 在某些方面做得很好，在另一些方面还有提升空间；Snowflake 也是某些方面表现优异、某些方面可以做得更好；Databricks 以及其他厂商同样也是如此。

<details>
<summary>Original English</summary>

**Andy Pavlo**: So the core kernels of the system like that certainly be improved, but the fundamentals of what ClickHouse is doing versus other systems at the smallest level, they're pretty similar. But the stuff around it matters a lot. And I think ClickHouse does some things certainly well, things can do better; Snowflake does some things well, can do things better; same Databricks and the other guys.

</details>

### 嘻哈比喻与加入 ClickHouse 的新角色

**Matt Turk**: 好吧，非常感谢你抽出时间和我们交流。祝贺你开启了这份新工作！我记得你还在一篇博文里用了一个嘻哈音乐的比喻来形容这次合作，对吧？具体是怎么说的来着？

<details>
<summary>Original English</summary>

**Matt Turk**: Well, thanks for spending time with us. Congrats on the newish job that you also described in a hip-hop analogy, right? What was it?

</details>

**Andy Pavlo**: 我的意思是，就像你看 Run the Jewels 这个组合一样——就好比把 El-P 和 Killer Mike 组合在一起。他们两个人各自本来就已经成名立万、极具影响力；但把他们放到一起，就像是人们第一次把花生酱和果酱抹在一起做成果酱三明治一样奇妙，对吧？所以，我乐意把我和 Alexey 的联手合作看作是这样一种强强联合。

<details>
<summary>Original English</summary>

**Andy Pavlo**: I mean, it's like when you look at Run the Jewels, it's like taking El-P and Killer Mike—like those guys were established on their own. You put them together, you know, it's like people putting peanut butter and jelly together for the first time, right? So like, I like to think me and Alexey getting together is like that.

</details>

**Matt Turk**: 明白了。好吧，现在这期节目正式创下了 MAD Podcast 历史上提及嘻哈文化引用最多的纪录。

<details>
<summary>Original English</summary>

**Matt Turk**: Okay. Well, this is now officially on the record the most hip-hop reference-heavy episode of the MAD Podcast.

</details>

**Andy Pavlo**: 我很高兴你注意到了博客文章里的那个细节。那不是我在故意测试什么，那是我在写博文时顺便抛出来试探一下，看看 ClickHouse 团队能接受多大尺度的个性化表达。显然我可不想搞得像拉里·埃里森（Larry Ellison）那样张扬，但你也想借机观察一下：嘿，你们既然找了 Andy 过来，就得做好接受他身上自带的这些个人色彩与特质的准备。

<details>
<summary>Original English</summary>

**Andy Pavlo**: I'm glad you found that in the blog article. That wasn't a test. That was my—because, you know, I wrote the blog article, I was floating it out there to see what ClickHouse would be okay with. Obviously I didn't want Larry Ellison in there, but like, you know, want to see like, hey, you know, if you get Andy, you're also getting other baggage.

</details>

### 尾声与致谢

**Matt Turk**: 太棒了，Andy，这次对谈精彩绝伦。非常感谢你的到来！

<details>
<summary>Original English</summary>

**Matt Turk**: All right, Andy, this was fantastic. Thank you so much.

</details>

**Andy Pavlo**: 好的，也谢谢 Matt 的招待与帮助。

<details>
<summary>Original English</summary>

**Andy Pavlo**: Yes. Thanks Matt for the helping.

</details>

**Matt Turk**: 大家好，我是 Matt Turk。再次感谢收听本期 MAD Podcast。如果您喜欢这一期内容，如果您还没有订阅，我们将非常感激您能订阅本节目，或者在您收听、观看本节目的任何平台上留下好评或留言。这对我们持续打造这档播客节目、邀请更多优秀的嘉宾非常有帮助。谢谢大家，我们下期节目再见！

<details>
<summary>Original English</summary>

**Matt Turk**: Hi, it's Matt Turk again. Thanks for listening to this episode of the MAD Podcast. If you enjoyed it, we'd be very grateful if you would consider subscribing if you haven't already, or leaving a positive review or comment on whichever platform you're watching or listening to this episode from. This really helps us build the podcast and get great guests. Thanks, and see you at the next episode.

</details>