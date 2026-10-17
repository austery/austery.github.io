---
author: AI Engineer
date: '2026-07-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=kRkcNOsRyYg
speaker: AI Engineer
tags:
  - agnostic-model
  - graph-representation
  - lakehouse-architecture
  - tool-calling
title: 基于湖仓一体的 AI 数据模型与智能体构建
summary: 本文介绍了一种基于湖仓一体架构的 AI 解决方案，核心在于通过不可知数据模型来处理结构化和非结构化数据的融合。文章探讨了在大型数据集上如何利用图技术解决全局性问题（如模式发现、否定命题）以及如何通过工具调用历史来验证智能体的准确性。
insight: ''
draft: true
series: ''
category: data-engineering
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models: []
media_books: []
status: evergreen
---
<!-- chunk 1/12 -->

### 课程介绍与环境设置

**Zach Blumenfeld**: 大家好。欢迎各位今天来参加 AIE 的入门培训。在这里有一些入门步骤。大概 10 分钟前我已经讲过了，不过简单来说，我们今天要进行的研讨会是基于一个名为 GraphAcademy 的网站。如果你扫描左边的第一个二维码，就会进入该网站。你需要使用电子邮件进行注册。然后，如果你往下看到设置环境的部分，那里有一个代码空间（codespace），里面一切都已设置好，你现在就可以启动它。这大概需要五分钟左右。然后你也可以同时获取你的凭证。那里有一个 Anthropic API 密钥。如果你有自己的 Claude 密钥或你自己的订阅，请随意使用。否则，我们已经为你提供了一个。另外还有一个用于读取 BigQuery 数据表的密钥。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: Hello everyone. Welcome today to get started on AIE. So right here, there's some steps for getting started. I went over this around 10 minutes ago, but basically our workshop that we're going to take today is driven by a website called GraphAcademy. And if you go to that first QR code there to the left, that'll take you there. You have to enroll with your email. And then if you go down to set up your environment, there's a codespace there with everything set up and you can get that rolling now. It'll take maybe about five minutes or so, and you can grab your credentials then as well. There's an Anthropic API key. If you have your own Claude key or your own subscription, please feel free to use that. Otherwise, we provided one for you. And then there's another key there for reading from BigQuery tables.

</details>

**Zach Blumenfeld**: 所以，考虑到这一点，我们将开始探讨基于湖仓一体（lakehouse）的 AI，它的核心在于以上下文形态而非仅仅是查询的方式来提供信息。今天你们的团队将由我来带领。我叫扎克·布鲁门菲尔德（Zach Blumenfeld），我是 Neo4j 的 AI 研究工程师。在后面那里还有本·斯夸尔（Ben Squire），他是我们的高级开发者布道师；以及坐在中间的瑞恩（Ryan），他是我们的合作伙伴架构师，负责帮助客户搭建和运行这些系统。所以，当你们有任何问题时——虽然我没有为你们准备麦克风，但可以直接举手。我会在每个自然段落间的自然休息时间，大概每 10 到 15 分钟停下来回答一些问题。但同时，如果你在执行某些步骤时遇到困难，不知如何设置，也请向本和瑞恩示意，他们会帮助你解决问题。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: So with that in mind, we'll go ahead and get started with AI on your lakehouse, which is about context coming in shapes and not necessarily queries. So today your team will be myself. My name is Zach Blumenfeld. I am an AI research engineer at Neo4j. We also have Ben Squire over there in the back who is our senior developer advocate, as well as Ryan here in the center who is our partner architect helping customers get this stuff up and running. So, as you have questions, I don't have a mic set up for you, but go ahead and raise your hand. I'll take time around every 10-15 minutes during natural breaks and I can take some questions, but also flag Ben and Ryan as well if you're going through some steps and you're having some trouble setting things up. And they can help get you unblocked.

</details>

### 湖仓一体的挑战与 Autofix 场景

**Zach Blumenfeld**: 因此，我们今天要讨论的内容，实际上是关于当你们开始使用湖仓一体时，显然会面临两个层面。一方面是数据仓库（warehouse），也就是你的结构化数据和数据表；另一方面是数据湖（data lake）部分，即你所有的非结构化文档。通常情况下，当你拿到像 text-to-SQL 和向量搜索（vector search）这样的工具时——如今我们在访问这些数据上其实已经没有太大困难了。但有时依然存在一些挑战：你如何为你的智能体（agent）提供正确类型的上下文？它们是否能以所需的方式查看到所有的数据？以及如何准确切取数据片段来回答特定类型的问题？所以我们在今天的课程中为大家准备的是一个不可知的数据模型（agnostic data model），它不仅能够基于你的数据仓库（即结构化的一面）创建一个图表示（graph representation），还能为你的一些文档提供结构化支持，从而让你可以利用它完成许多有用的工作。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: So what we're going to talk about today is really about when you start using a lakehouse, right, there's sort of two sides obviously. There's a warehouse which is your structured data and your tables, and then there's the data lake part which is all of your unstructured documents. And oftentimes what can happen is you're given these tools like text-to-SQL and vector search, and nowadays we don't really have trouble accessing that data. But sometimes there are still some challenges around how do you give your agent the right type of context, whether or not they can see all the data in the way that they need, and really take a slice to answer the right type of question. And so what we've put together today inside of our course is an agnostic data model that basically creates a graph representation both from the structured side, your warehouse, but then also provides structure for some of your documents, and then allows you to do a lot of useful stuff with that.

</details>

**Zach Blumenfeld**: 我们这里准备了一个将要讲解的场景。我们虚构了一个叫做 Autofix Group 的组织，你可以把它想象成类似 Pep Boys Auto 那样的全国性汽车维修连锁店。他们有很多维修车间。他们拥有各种车辆的维修手册库、安全公告、召回通知，还有一个记录了他们所有历史维修数据的数据仓库。同时，你们也有车间技师，对吧？也就是这里列出的像丹尼（Danny）这样的人，当汽车停在车间里时，他们需要提出一些问题。而该组织的领导层则希望创建一个 Copilot（智能副驾驶）来协助这些在车间里工作的技师。然后显然，还有像山姆（Sam）这样的人——也就是我们自己，负责实际构建这个工具的 AI 工程师。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: We do have a scenario here that we're going to go over. We've created a fictional Autofix group, which is, think of it like a Pep Boys Auto or something. It's a national auto repair chain. And they have all of these bays. They have these libraries of manuals on vehicles, as well as safety bulletins and recalls, and then a warehouse of all of the repairs that they've logged. And you have sort of your floor technicians, right? These are the Dannys that are listed here where they have the cars inside of the bay and they're going to need to ask some questions. You have leadership at this organization that wants to create a copilot to be able to assist these technicians on the floor. And then obviously you have people like Sam who are us, the AI engineers who actually have to build the thing.

</details>

### 解决全局性数据问题与三种核心形态

**Zach Blumenfeld**: 因此，如果他们的数据已经存放在数据仓库中，我们今天要看的就是基于 BigQuery 的例子。想象一下，你把文档存放在云存储中，然后使用 BigQuery 作为你的数据仓库；不过这些模式同样也可以扩展到 Databricks 以及 Snowflake。本质上，如果他们仅仅在 BigQuery 和他们现有数据的基础之上构建一个 Copilot，它虽然能够正确拉取数据，但有时候它也会“自信地犯错”。基本上，它可以通过向量搜索从文档中提取内容，也能在少数几张表上执行 text-to-SQL。但是，当这些数据表变得极其庞大，当你拥有数百张表，或者当你拥有包含成百上千万份文档的大型文档存储库时，信息很容易丢失或者被遗漏。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: And so if they already have their data in a warehouse, what we're going to be looking at today is the example on BigQuery. So imagine, right, you have your documents inside of cloud storage and then you have BigQuery as your data warehouse, but these patterns are also extendable to Databricks as well as Snowflake. And essentially if they just create a copilot on top of BigQuery and the data that they have, it can pull the data correctly, but sometimes it can be confidently wrong. Basically it could pull stuff with vector search from documents and it can do text-to-SQL on just a few tables. But when those tables become massive and you get hundreds of tables, or when you have large document stores where you have hundreds and thousands and millions of documents, things can get lost and fall through the cracks.

</details>

**Zach Blumenfeld**: 而图（graph）技术真正在这些数据形态上能发挥作用的地方，不仅在于回答某些人可能提出的单一问题，比如“我有一个坏掉的零件需要更换，我该如何修理这辆车”，而且往往在于回答那些全局层面（estate level）的问题。例如：“我们遗漏了什么？” 或者“也许我们缺少了哪些文档，无法覆盖所有进店维修的不同车型？” 抑或“有哪些文档是我们根本没有利用起来的？” 所以这有点像是在“证明一个否定命题”，这在使用语义搜索（semantic search）等技术时会非常困难，因为语义搜索只能匹配相似的内容，对吧？它无法真正找出一个反例。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: And really where graph can come in to help with these shapes is not only in these single questions that someone might have about how, you know, I have a broken part that I need to replace and how do I repair this vehicle, but oftentimes it's going to be on these estate level questions. So things like, for example, what are we missing? Like what documentation maybe do we not have to cover all of the different cars that are coming in or what documentation maybe are we not leveraging at all. So this is sort of like proving a negative which can be very hard with something like semantic search, which can only match similar things, right? It can't really find a negative example.

</details>

**Zach Blumenfeld**: 我们还会遇到一些问题，需要跨越所有数据来寻找模式。比如你可能会问：“我们常见的模式类型有哪些？有没有什么是我们一再未能修复的？” 或者，“是否有不同类型的召回事件呈现出特定的聚类并不断出现？” 针对这类问题，你真的需要遍历整个数据集。另外一个问题则是询问在大型 SQL 存储中，记录之间是如何关联的。当你拥有一个非常庞大的、模式看起来都很相似的架构，里面有许多相似的表时，你如何理解怎样将它们正确地连接在一起？

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: There's also questions that we have where we want patterns across everything. So say, you might want to ask, well, what are the common types of patterns that we see? Is there anything that we're failing to fix over and over again? Or are there specific groupings of different types of recalls that are popping up and things of this nature where you really need to traverse the entire dataset. And then the other one is just asking how records relate inside of a large SQL store. And when you have one big lookalike schema where you have lots of similar tables, how do you understand how to join those together correctly?

</details>

**Zach Blumenfeld**: 所以，今天我们将向大家介绍三种具体的数据形态。第一种我们称之为“目录（Table of Contents）”，它有点像树状结构，但在节点之间也存在不同类型的链接。稍后你会看到它是如何运作的。它将应用于非结构化数据。同样在非结构化数据方面，我们还有一种叫做“主题（Themes）”的形态。主题的作用是呈现你数据中隐藏的全局模式，这些模式可能并不明显，或者你事先并不知晓。也就是用来揭示未知的模式和分组。第三种形态，在进入课程后我们实际上会最先讲解，就是这个“连接（Connection）”形态，它本质上是位于你的数据仓库之上的一个语义层。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: And so there's going to be three concrete shapes that we'll introduce you to today. So the first one we're going to call Table of Contents and it's somewhat like a tree structure, but with also different types of links between them. You'll see how it works. This is going to be used on the unstructured data. On the unstructured data side as well, we have something called Themes. And what Themes does is it surfaces global patterns inside of your data that might not be apparent or you might not know about beforehand. So uncovering unknown patterns and groupings. And then the third one which, when we take the course we're actually going to go over first, is this Connection shape, which is essentially a semantic layer on top of your data warehouse.

</details>

### Neo4j 基础概念

**Zach Blumenfeld**: 那么，在座有多少人，请举手示意一下，熟悉图（graph）和图检索增强生成（GraphRAG）？好的，有相当一部分人。那么在座有多少人以前使用过 Neo4j？好的。也有大概 30% 或 40% 左右。看来这个房间里的人对图的基本概念还是相当熟悉的，但我还是在这里快速地过一遍。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: And so how many people, just a show of hands here, are familiar with like graph and GraphRAG? Okay, so a fair number of you. Then how many people in here have used Neo4j before? Okay. Also like maybe 30, 40% something like that. So this room seems like you know fairly familiar with graph basics, but I'll go over it just here really quick.

</details>

**Zach Blumenfeld**: 对于 Neo4j，我们是一个图智能平台。我们的核心是一个图数据库。基本上，当我们讨论什么是“图”时，我们是从属性图数据模型（property graph data model）的角度来谈论的。所以，在我们的数据库和分析平台中，所有东西都被建模为三种不同类型的元素：首先是代表人物、地点和事物的节点（nodes）；其次是代表这些事物之间的动词或关联的联系（relationships）。比如“人拥有车”、“人驾驶车”、“人与另一个人有亲属关系”。最后，我们还有属性（properties），这些属性既可以附加在联系（有时我们称之为边）上，也可以附加在节点（有时被称为顶点）上。这些属性可以是字符串、数字、日期、向量，可以是各种各样的形式。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: So Neo4j, we're a graph intelligence platform. We have a graph database at the heart of it, right. And basically when we talk about what a graph is, we're talking about it from a property graph data model perspective. And so everything inside of our database and our analytics platform is modeled to these three different types of elements, which is nodes that represent people, places and things; relationships which are the verbs or associations between those things. So like person owns car, person drives car, person is related to other person. And then we have properties that go on these, both the relationships (or sometimes we'll call those edges) and the nodes (which are sometimes called vertices). And those can be anything from strings, they can be numbers, they can be dates, they can be vectors, all sorts of things.

</details>

**Zach Blumenfeld**: 因此，图的基本理念就是，当你开始向其中添加数据时，它几乎就像是一堆预先连接好的数据表，所有的东西都已经相互关联，你可以非常轻松地在所有节点之间跳跃查询。这带来了极大的优势，我们会在课程的后半部分看到。所以，带着这样的概念，大家不妨现在就开始动手，进入这些操作——如果你以前没听过的话，我其实可以马上在这里快速演示给你们看。

<details>
<summary>Original English</summary>

**Zach Blumenfeld**: And so the basic idea with a graph, right, is as you start adding data to it, it's almost like a bunch of pre-joined tables and everything's already interconnected and you can hop between all the nodes very easily. And that provides a ton of benefits that we'll see later in the course. So, with that in mind, why don't you go ahead and get started and go over into these, if you haven't heard before, and I'll actually just show you here really quick.

</details>

<!-- chunk 2/12 -->

### 启动环境与课程概览

**Instructor**: 在 Workshop Lakehouse 里，我已经在这里打开了。我可能得赶快重启一下这家伙，启动我的代码库。基本上，它应该会带你来到这个页面。如果这是你第一次访问，它不会显示“继续课程”（continue course），而是会显示“注册课程”（enroll to take the course）。所以你需要先通过那个流程来注册课程。之后这里的整个过程，基本上就是我带着你们过一遍这个课程，并向你们展示我们能做的各种不同的事情。这里大概有 17 节课。我们按不同的形态（shapes）对它进行了划分。

<details>
<summary>Original English</summary>

**Instructor**: inside of the workshop lakehouse, have it open here. I should probably restart this guy really quick. Start my code base. Um, but basically it should take you to this page. Um, this shouldn't wouldn't say continue course for you if you if it's your first time going to it. It would say enroll to take the course. So, you have to go through that path to enroll to take the course. Um, and then basically the whole thing from here on out is just going to be me guiding you through this course and kind of showing you all the different uh things that we can do. Um, there's about 17 lessons in here. We've broken it up by the different shapes.

</details>

**Instructor**: 基本上只要你进入课程，就可以在里面点着看。我会稍微讲一下这个场景。不过在讲之前，我觉得你们应该先跳转到“环境”（environment）这个部分。也就是直接拉到最下面，找到你的环境部分，从这里你可以选择“打开 Codespace”。事实上，我也会在这里开一个新 Codespace，这样我就能和你们同步走一遍。是的，当然可以。回到这边，大家不妨把那个捕捉（capture）一下？好的。

<details>
<summary>Original English</summary>

**Instructor**: Um, but basically if you go into the course, you can kind of click through here. I go over the scenario a little bit. But while I'll do that, I think what you should do is jump to this environment section. So basically, you go down to the bottom here. go to your environment and um from here you can say open code space and in fact I will open a new code space here just so that I can I can walk through it uh live with you as well. Yeah, of course. Um, go back to here. Why don't you all go ahead and capture that? Yes.

</details>

**Instructor**: 它可以选择在你自己的 GitHub 仓库里创建一个 Codespace。里面也有仓库的链接，所以你也可以在本地运行。不过请记住，我们的设置是让它在 Codespace 中自动启动。如果你想在本地运行，这里还有另一个 bash 脚本可以执行，它会帮你把一切都配置好。但这一定程度上取决于你的本地环境，你必须确保已经安装了 Claude Code 等等这些东西。所以，如果你们觉得没问题的话，我们更推荐使用 Codespace。我以前也经常在本地跑它。

<details>
<summary>Original English</summary>

**Instructor**: So it'll create a code space in your own GitHub if you want. There's a link to the repository. You could run it locally. Um just keep in mind that we've set it up so that it will auto start in the code space. So there's another um bash script that you can run to run it locally and it will it will set everything up for you. Um but it it depends a little bit on your local environment. You have to make sure you have cloud code installed um and all these sorts of things. So, we'd recommend that you use a Code Space one if if you're comfortable doing it locally. I I I've run it locally all the time before, too.

</details>

### 配置密钥与数据库

**Instructor**: 好了，大家都扫了那个二维码吧。我再等个十秒左右，然后我就切回去了。对，如果你们没有拿到的话，Ben 和 Ryan 可以帮你们。好的，当你启动时，这里有一些 Workshop 的凭证。课程结束后我会把这些密钥公开销毁。我会先让它们留一会儿。基本上，给它一点时间启动。一旦启动成功，你接下来要做的就是进入这里的环境配置文件（environment file）。也许我可以把字调大一点，方便你们看清。你需要把你的 Anthropic 密钥和 BigQuery 密钥放进这里面。

<details>
<summary>Original English</summary>

**Instructor**: All right, everyone's everyone's copied the uh QR code. I'll give it another 10 seconds or so and then I'll I'll move back over. Yep. Ben and Ryan can help you out if if you don't have this one. Okay. So, when you start up as well, there's some workshop credentials here. Uh I'll I'll be uh blasting these keys uh a after the course. I'll leave them up for just a little bit. Um but basically, give it some time to start up. Uh- once it once it does, what you'll do is you'll go into your environment file here. And maybe I can make this just a little bit bigger so it's easier to see. You will place your anthropic key in here as well as the uh the BigQuery key.

</details>

**Instructor**: 如果回到课程页面往下看，你还需要放入另一个东西，那就是应该提供给你的 Neo4j 凭证。这个是用来访问我们的图数据库的。它们都已经预先分配好了，所以每个人的凭证都不一样，你会拿到属于你的那一个。从你的屏幕上把它复制下来，然后一样把它放进这个环境配置文件里。这需要花点时间，就像你看到我的屏幕一样，环境配置文件还没完全弹出来。所以这一切跑完可能需要几分钟。我们会给它一点时间启动。希望不会花太久。

<details>
<summary>Original English</summary>

**Instructor**: The other thing that you're going to want to place in uh if you go back to the course um is down here, it should give you a um Neo Forj credential. So, this is accessing our graph database. They've been all pre-provisioned, so it's going to be different for each one of you. You're going to have a different one. So, copy the one from your screen. Um, and you're going to put it inside of this environment file as well. Um, and it it will take a while, like you see with mine, the environment file hasn't uh quite popped up yet. So, it can take a few minutes for that all to go through. Um, so we'll we'll give that a little bit of time to start up. Hopefully, it won't take too long here.

</details>

**Instructor**: 趁着它还在运行，我先简单介绍一下我们下一步要做什么。基本上，一旦我们把它设置好，并让 Claude 跑起来，我们将一起过一遍我们今天的第一个形态（shape），也就是这个“连接语义层（connection semantic layer）”的形态。之后，我们会接着讲刚刚提到的“目录（table of contents）”形态和“社区（communities）”形态。所以，我们会先处理结构化数据，然后再进入非结构化的部分。

<details>
<summary>Original English</summary>

**Instructor**: While that's running, I'll I'll give a little bit of an overview here of what we're going to do in the next step. So, basically, once we get this set up and and we get Claude up and running, um we're going to walk through um the first shape for our day, which is this connection semantic layer shape. And then after that we'll follow it with the table of contents one that we were talking about and the communities one. So we'll be working with the structured data first and then moving into the into the unstructured bits.

</details>

### 使用 Claude Code 与 MCP 服务器

**Instructor**: 已经加载好环境的同学，基本上你的终端就在下面这里。你可以直接去调用 Claude。我们会通过 Claude Code 来作为我们的 Agent。这会儿网速也有点慢，在跑这个的过程中是可以预见的。我应该……哦，出来了。我马上配置好给你们演示一下这是什么样子。填好 Anthropic 密钥和 BigQuery 的。好的，完美。如果出现这种情况，它试图让你订阅，你只要点加号（plus）打开一个新的终端窗口，然后它这里应该会给你选择 Anthropic 密钥的选项。直接一路回车就行，是的。接下来你想用这边的 MCP 服务器，所以选择“yes”。我跳过导览（tour）。然后我就可以问那个问题，只是为了确认它能连上 Neo4j。对我来说，因为我用的是上次课程已经缓存好的图数据，所以我里面已经有一些节点（nodes）了。但对你们来说，它刚出现时会是一个空的沙盒（sandbox）。

<details>
<summary>Original English</summary>

**Instructor**: Um once for those of you who do have it loaded basically you have your terminal down here. You can go ahead and call Claude. Um, we'll be working through Claude Code as our agent. Um, the internet is a little bit slow too, which is expected as you go through with this as well. I should um Oh, here we go. We'll set up show you what this looks like here in a second. Anthropic key as well as BigQuery one. All right, perfect. And if it does this where it's trying to get you to do a subscription, basically what you do is you'll go plus, open up a new terminal window, and then it should here give you the option to select the enthropic key. Just go through and press enter. Yes. And then you want to use the MCP server here. So you're going to select yes. And I'm going to skip the tour. And then I can ask that question just to make sure it can connect to Neo4j. And for me, I already have some nodes in because I'm working with um a graph that's been cached already for my previous course. Um for you, it will it will come up as an empty sandbox.

</details>

### Agent 式编码与 Cypher 查询

**Instructor**: 有一件事我想要在这里强调一下，就是关于我们将如何使用 Neo4j 以及它的图查询语言 Cypher。我觉得我们现在已经到了这样的阶段：很多人不再一行一行地手写自己的代码了。显然，我们正在利用 Agent 来帮助我们构建东西。所以在这个 Workshop 中也是一样的。基本上我们会使用一个叫 Neo4j CLI 的命令行工具，它允许你的 Agent 直接对着数据库运行查询。刚才我在 Claude 里面操作时，你们看到它跑了一下。它还附带了一个 Neo4j Cypher 技能（skill）。这让 Agent 能够以最现代的方式来组合查询，它还有一个叫 GDS 技能的东西，GDS 代表图数据科学（graph data science）。当我们讲到“主题（theme）”那部分的时候，我们会用它来运行一些算法，主要就是帮助我们做 Agent 式编码（agentic coding）。所以，我不会让你们大家真的去手写任何 Cypher 查询代码。我会在这个 Workshop 的过程中展示如何利用 Agent 帮你根据创建好的需求规范（specs）写出那些代码。希望这对你们的日常工作会更有用，不管以后你们是否决定使用 Cypher，或者是否搭配 Neo4j。

<details>
<summary>Original English</summary>

**Instructor**: So, one thing that uh I want to note here too in terms of how we're going to be working with Neo forj and with cipher, which is our graph query language. I think we've come to a point now where a lot of us aren't h hand typing uh our own code line by line anymore. We're using agents to help us build things obviously. And so in this workshop it's going to be the same thing. Basically we're going to be using something called the Neo Forj CLY um which is a CLY tool that will allow your agent to run uh queries directly against the database. When I was working inside of Claude, you saw it running there for a second. And that also ships with a Neoraj cipher skill. Um, that allows the agent to sort of leverage how to put queries together in the most modern way, as well as something called a GDS skill, which stands for graph data science. And we'll use that for some of the algorithms when we get to the theme section. Um, in terms of just helping us do agentic coding. So, I'm not going to have you guys handw write really any um cipher query code. I'm going to show you throughout this workshop how to use an agent to help you write that with with specs that are created. Um and hopefully that'll be useful for you more on on the day-to-day if you ever decide to use uh cipher um whether it be with Neo forj or not.

</details>

### 问答与代码库结构

**Instructor**: 好了，大家现在进度怎么样了？我先在这里停一下。有问题的话请举手。或者大家都弄好了？那边有个问题。

<details>
<summary>Original English</summary>

**Instructor**: Um, so how is everybody doing now? I I'll take a second here to stop. Go ahead and raise your hand if you have any questions here. Or are we all good? I have one question over there.

</details>

**Audience Member**: 对。那个问题是，我能用 Cursor 吗？答案是应该可以。是的。我没有亲自测试过，但如果你拉到最上面，应该有一个我们正在使用的仓库的链接。如果没有的话，当你点击打开代码（open code）时，对，你可以把仓库克隆下来。如果你顺着那个链接，你可以把代码克隆到本地。然后你会看到这里有说明。有一个你可以运行的 shell 文件，它会帮你配置好一切。你可以看一眼里面都有什么，都是一堆基础的东西。好的。太棒了。是的。

<details>
<summary>Original English</summary>

**Audience Member**: >> Yeah. So the question is, can I use cursor? And so the answer to that is you should be able to. Yes. I haven't personally tested it, but if you go up to the top, there should be a link to the repository that we're using. Um if not, when you go to open code, yeah, you can clone the repository here. So if you follow that link, you could clone it. You can get it locally. Um and then you'll see here there's directions. There's a shell file that you can run that will set everything up. You can take a look at what's in there. It's it's a bunch of basic stuff. Okay. Awesome. Yeah.

</details>

**Instructor**: 稍微讲一下这个东西的结构。我忘了提了，这个工作区里面有很多东西。显然在 Claude 里面，我们有我们的技能（skills）文件。我已经提前写好了一个技能，它基本上涵盖了我们将要做的很多事情。另外在这里面，有一个叫 outline 以及 search 和 theme 的文件。这些就是我们将要处理的形态。要查询 BigQuery 的话，这里只有一个非常小的……不过这其实是一个数据库查询文件，但这个名为 run SQL 的文件专门用来查 BigQuery，就是一种非常简单地去调用 BigQuery 并用简单的 SQL 命令来执行的方式。正如我们稍后会看到的，在这些文件里面，有留给填入 spec（规范说明）的地方。那就是我们要进行 Agent 式编码的地方。但如果你想自己把这些数据加载进 BigQuery，这里面的任何东西都有对应的操作说明。如果你想在 Databricks 上运行它，这里也有教你怎么把它加载到 Databricks 里面，并在那里使用 Genie 和 AI 搜索来进行对比的说明。然后这个只是一个软链接，连回到那些 Claude 文件。这里有解决方案……

<details>
<summary>Original English</summary>

**Instructor**: And just a little bit about the structure of this thing. I forgot to mention um there's a lot of stuff inside of the uh inside of uh the the workspace here. Um obviously inside of Cloud we have our skills file. Um, so I've gone ahead and pre-written a skill here. Um, that covers basically a lot of what we're going to do. Uh, inside of here as well, there's uh a file called uh outline and search and theme. So, these are going to be the shapes that we'll be working with. um to query BigQuery there's just a very small um well that this is actually a a database query file but the run SQL one this one for querying bigquery just a very simple um um basically way of uh reaching out to BigQuery and just calling it with a uh with um a simple SQL command. Um and inside of these files as we'll see later there's there's places to fill in a spec. So that's going to be where we do some of our agentic coding. Um, but everything in here, if you wanted to like load this into BigQuery yourself, there's something for that. Um, if you want to go ahead and run this on data bricks, there's directions here to like load it into into data bricks and use Genie and AI search there if you want to compare. Um, and then this is just a sim link over back to the uh cloud files. Um, there's solution

</details>

<!-- chunk 3/12 -->

### 获取资源与查看原始数据

**Speaker A**: 这里也有脚本。另外，如果你遇到困难，比如说由于某种原因，编码 Agent 无法生成正确的查询，你可以从那里复制相关内容。此外，用于创建结构化和非结构化数据的所有源数据都在这里，包括我们的 PDF 源文件。所以如果你进入这里，我们有各种公告、手册以及所有相关资料。现在这里展示的是原始 PDF 文件。但是，如果我转到语料库（也就是 Markdown 版本），你就能实际读取其中的内容了。

<details>
<summary>Original English</summary>

**Speaker A**: scripts as well. Also if you get stuck for example where for some reason the coding agent can't you know create the right query um you you can copy stuff from there. Um and then all of the source data too for creating both the structured and unstructured data is in here um including our uh PDF sources. So if you go in here we have our bulletins and our manuals and everything. Um this is showing you the uh the raw PDF. But if I go to the corpus, which is the the markdown version, uh you'd be able to to actual re actually read the contents inside of them.

</details>

**Speaker A**: 总之，了解了这些之后，我们将继续前进，进入这里的第一个部分，也就是连接（connections）。

<details>
<summary>Original English</summary>

**Speaker A**: Um so anyway, with all of that, we'll go ahead and hop along to our first section here, which is going to be connections.

</details>

### 数据架构与语义层

**Speaker A**: 所以，我们目前的数据基本上都在 BigQuery 中。事实上，如果我回到概览页面，只是为了快速向你们展示一下它的样子，这就是我们所用的 schema（模式）。为了这个课程，我们保持了非常简单的结构。显然，在现实世界中，你们的 schema 会比这庞大得多。但我们有工单（work orders），它有点像这个模式的中心或者星型结构的中心。你还有车辆（vehicles）、不同的 DTC 代码、维修程序（procedures）、工单零件（work order parts），然后是零件本身（parts）。它们通过非常简单的“主键-外键”模式连接在一起。我们稍后会在课程中涉及文档部分，它基本上就是一个装满 PDF 文件的大桶。

<details>
<summary>Original English</summary>

**Speaker A**: So, we have basically our data inside of BigQuery right now. And in fact, if I go back to my overview, just to show you what it looks like really quick. This is the uh schema. Uh so, we've kept it very simple for this course. Obviously, in the real world, you'd have a much bigger schema than this. Um but we have our work orders, uh which is sort of like the middle or the star of the scheme. you have your vehicles, um the different uh DTC codes, procedures, uh work order parts, and then the parts themselves. Um and they join together in a very simple primary foreign key pattern. Um we'll get into our documents later in the course. It's just basically a a big bucket of of PDF files.

</details>

**Speaker A**: 因此，为了帮助我们的 Agent 能够有效地将所有内容连接在一起，我们要在这里做的是为它提供一个语义层的图表示（graph representation）。为了构建这个语义层，我们将使用一个名为 NeoCarta 的工具。NeoCarta 是一个实验室项目（labs project）。在 Neo4j，我们有核心工程部门，负责诸如我们的云 SaaS 平台、图分析等所有核心功能。但我们也有一些能让我们行动得更快的实验室项目。在这个实验室项目中，我们创建了这个 NeoCarta。它的作用是创建一个元数据图（metadata graph）。另外，尽管我们在这里没有使用这个功能，但你其实可以将业务术语、业务流程以及大量其他内容添加到图结构中。如果你仔细想想，“本体（ontology）”和“语义层（semantic layer）”这些词最近被频繁提及，尤其是在这个夏天。因此，我用来思考这些概念的基本思维范式是：本体帮助某个主体解释和推理数据，而语义层帮助某个主体理解一致同意的术语是什么，以便它可以准确地查询数据。此外，在 Neo4j 我们还有其他东西，比如虚拟图（virtual graph）。课程里提供了一个链接，它能让你以联邦图视图（federated graph view）的方式来查看 SQL 数据，你可以直接使用 Cypher 查询它。我们在这里不会用到它，但有时候，提供一个 schema 的图视图是很有价值的。总之，正如我们将在下一节看到的，NeoCarta 将会发挥它的作用，它基本拥有一个 MCP 服务器，它会从 BigQuery 中提取所有数据——仅仅是元数据——并创建这个图。

<details>
<summary>Original English</summary>

**Speaker A**: And so what we want to do here is to help our agent be able to effectively join everything together, we're going to give it a graph representation of a semantic layer. And to build that semantic layer, we're going to use something called Neoarta. Um Neoarta is a labs project. So at Neo Forj, we have our core engineering, which is like our, you know, cloud SAS platform, um our graph analytics stuff and all of that. But we also have labs projects where we move a little bit faster. Um, and inside of that labs project, we created this neocarta. Um, and what it does is it creates a metadata graph. Um, also although we're not leveraging it here, you can add business terminology and business processes and a whole bunch of other things into a graph structure. Um, and if you think about it, people, you know, these words ontology and semantic layer and all these things are kind of they're thrown around a lot lately, especially this summer. And so the the basic uh mental paradigm that I use to kind of think through these is an ontology helps something interpret and reason about the data. A semantic layer helps something understand what the consistent agreed upon terms are so it can query the data accurately. Um and then at Neo Forj we have other things like virtual graph. There's a link in here in the course which will actually give you a sort of a a federated graph view of your SQL data that you can um that you can query over directly with cipher. We won't be using that here, but there there is um sometimes uh value in in giving sort of a graph view of the schema. Um but anyway, what Neo Carter will do is it we'll see in this next section um uh it has an MCP server basically that will sort of suck all the data in from the um from BigQuery just the metadata and it will create this graph.

</details>

### 创建图并查询

**Speaker A**: 这就是你在下一节要做的。所以，我直接跳转到那里。我已经运行过这个脚本了。但基本上，当你看到这个脚本时，你需要复制它。然后你转到这里，打开你的终端。我喜欢打开一个新窗口，而不是用我的云窗口。你要允许粘贴，然后直接运行它。我已经运行过了，所以我就不再演示了，尽管它应该是幂等的。但基本上，一旦你运行了它，它就会创建这 6 个表以及这 5 条参考连接路径。完成这些后，你可以回到这里，甚至只运行这个来检查一下。它看起来很酷，这就是它在图数据库里的样子。基本上你会看到，中间有这样一个节点，它代表你的数据库，接着是你的 schema（模式），如果你顺着它往外看，会有“包含表（has table）”，然后你会看到你的表，接着是你的列。而且，这些列上面还可以选择性地带有这些代表性的值。

<details>
<summary>Original English</summary>

**Speaker A**: Um and that's what you do in the next section. So, I'll go ahead and jump to there. And I've already run this script. But basically, when you see this script, what you're going to do is you're going to copy it. And then you're going to go over to here. And then, um, you're going to bring up your terminal, which our terminal. And then, uh, I like to just open a new window. That's not my cloud window. Um, and you're going to allow paste. And then you're going to go ahead and run that. I've I've already run it. Um so I won't do it again, although it should be item potent. Um but basically once you run that, uh it'll create this um these six tables with these five reference join paths. And once you've done that, you can come back in here and even just run this to check. And it's kind of cool what it looks like. Um this is this is what it looks like inside of the graph database. And basically what you'll see is you have this uh this node in the middle that represents your um your well first your database and then your schema and then if you follow that out it'll be has table and then you'll have your table and then you have your columns. Um and those can also optionally have these representative values on top of them.

</details>

**Speaker A**: 因此这些连接路径，基本上当 Agent 读取它时——如果我往下走尝试一下，我在这里准备了一个示例提示，我回到我的窗口并返回给 Claude，我可以问这样的问题：“哪辆车收到了零件 IC 2042？” 在这种情况下，我会告诉它使用 MCP 服务器和仓库模式等，去获取所有信息，然后使用 Python 脚本。在这个技能（skill）本身里面也包含有相应的说明。你将看到它所做的操作是调用针对 NeoCarta 的那个 MCP 服务器，然后它会读取我们在 Neo4j 中的元数据语义层图。所以，如果你注意的话，我们在这里真正在做的并不是使用图来复制数据过去，没有像 ETL 那样的数据导入过程。我们做的是把图用作一个语义层。因此，我们只是提取关于列、行以及所有这些东西的元数据，我们将利用这些元数据来引导一个“文本转 SQL（text-to-SQL）”的查询生成，一旦它决定在此执行的话。

<details>
<summary>Original English</summary>

**Speaker A**: Um, and so these join paths, basically when the agent reads that, um, if I was to go down here and try, so I have, um, a little example prompt down here and I can go into my window and go back to Claude and I can ask a question like this. Which vehicle received part IC 2042? And I in this case I'm going to tell it to use the the MCP server and the warehouse schema and all this to to go and grab everything then use the Python script. Um inside of the skill itself it it has directions for this as well. Um, but what you'll see it'll do of this. It'll call that MCP server for Neo Carta and it's it's going to read that metadata semantic layer graph that we have in Neo forj. And so if you notice the thing that we're doing here really is we're not using the graph to copy the data over. There's not like an ETL into graph. What we're doing is we're using the graph as a semantic layer. So we're just pulling metadata about the columns and the rows and all of these things and we're going to use that to inform a text to SQL query once it uh decides to go ahead and run here.

</details>

### 回顾操作与环境设置

**Speaker A**: 现在大家用 Claude 的情况如何？是不是发现有些很慢？快吗？是啊，慢。好的，挺有趣的。我在这里多给它一点时间。我不知道它为什么走走停停。有点慢。

<details>
<summary>Original English</summary>

**Speaker A**: How is claude working for everyone right now? Are we seeing a lot of uh slow clouds? Fast. Yeah, slow. Okay. Interesting. I'll give it a little bit of time here. I don't know why it would be go moving. Huh. A little bit slow.

</details>

**Speaker B**: 是的。每个人都……

<details>
<summary>Original English</summary>

**Speaker B**: >> Yeah. Does everyone have

</details>

**Audience**: 有。

<details>
<summary>Original English</summary>

**Audience**: Yes.

</details>

**Speaker A**: 嗯，当然。所以问题是，在等待 Claude 加载时，我能回顾一下我是如何到达这一步的吗？基本上，正在传递的二维码，这里有两个。其中一个是用来报名这门课程的。我正在讲解的这门课程是在线的，它是免费提供的，任何人都可以访问。一旦你进入课程页面，你会在那里看到一个报名的按钮。所以你必须登录并注册该课程。完成后，你点击进入，就会来到这个环境设置（environment）部分。当你这么做的时候，大概需要五分钟左右让所有内容加载和准备好。如果你使用的是 Codespaces，你也可以选择在本地运行它。一旦你完成了这一步，基本上，你就可以进来获取你的凭证（credentials）了，你需要复制 Anthropic 的 API 密钥，以及这边的 BigQuery 密钥。拿到这些后，你就能访问工作坊里的所有资源了。基本上正如你在这里看到的……哦，太好了，我们实际上取得了进展。我们在这里的代码空间（Codespaces）里使用云代码（Cloud Code）。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yeah, sure. So, the question is, can I recount how I got to here while we're we're waiting for Claude to come along? So, basically, um the QR codes that are being passed around, there's two here. uh one of them is uh to enroll in the course. So the course that I'm going through is online. It's freely available so anyone can go uh once once you show up inside of the course basically you'll see a button here to enroll. Um so you have to sign in and enroll in the course. Uh once you do that you'll you'll click through and you'll make it to this environment section. Um, and when you do that, uh, it'll take about five minutes or so for everything to to populate and come up. Um, if you're using code spaces, you have the option to run it locally. Um, but then once you do that, essentially, um, you're going to come in here and you're going to get your credentials and you're going to grab the anthropic API key, um, as well as the, uh, the BigQuery key here. Um, and then once you do that, you'll be able to um access all the things in the workshop. Basically, um, you're using, as you saw here, um, oh, cool. We're actually making progress. Um, we're using cloud code inside of inside of code spaces here.

</details>

**Speaker B**: 不好意思，你能快速重复一下那部分吗？

<details>
<summary>Original English</summary>

**Speaker B**: >> Sorry, can you repeat that really quick?

</details>

**Speaker A**: 好的。关于 Neo4j 沙盒，如果我回到那个“环境”部分，你会看到这里有一个打开 Codespace 的按钮，然后在下面你应该能找到你专属的沙盒凭证。它和我现在展示的不完全一样，因为每个参与者的凭证都是不同的，你需要把它们复制下来。一旦进入这里，你会看到一个环境（environment）文件。在你填入 Anthropic 和 BigQuery 密钥的那个环境文件里，你也需要把 Neo4j 的凭证填进去。如果你没看到环境文件，或者只看到了 `.env.example` 文件，那它可能只需要花点时间来生成。后台还有其他程序在运行，它正在执行另一个 shell 脚本来为你创建所有内容并生成各种文件。所以，我的直觉是——如果我说错了大家可以指正——如果 Anthropic 现在这么慢，那多半是 Anthropic 自己系统的问题，而不一定是某个个人账户的问题。如果情况持续恶化，我可能会尝试提供另一个账户的密钥，但我其实认为问题并不在于此。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yes. The Neo Forj sandbox is um if I if I were to go back to that environment section um you see the button here to open code space and then you should have down here um your own sandbox credentials. So, it won't be these exact ones because it's it's different for every participant, but you'll go ahead and copy those. And then once you're in here, uh you'll be able to um you have your environment file. And inside of your environment file where you put your anthropic and your BigQuery key, you'll also put the Neo Forj ones. If you don't see a environment file and you see nothing or you see the end.example, example, it just takes it a while to populate that. There's other things that are running. It's running another shell script to kind of create everything for you and um populate all the different files. So, my my hunch, and someone can scream at me if I'm wrong, is that if Anthropics this slow right now, it's more of a anthropic problem and not necessarily a one person's account problem. Um, if it continues being bad, I might try to provide another key from a different account, but I don't actually think that that's what the problem is. I

</details>

<!-- chunk 4/12 -->

### 网络与环境问题

**Speaker A**: 觉得是……是……

<details>
<summary>Original English</summary>

**Speaker A**: think it's it's

</details>

**Speaker B**: 对。嗯，是的，但这应该也是远程运行的，对吧？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Well, yeah, but this should also be running remotely, right?

</details>

**Speaker C**: 是……仅仅是 Wi-Fi 的问题吗？好吧。

<details>
<summary>Original English</summary>

**Speaker C**: Is it Is it just the Wi-Fi? Okay.

</details>

**Speaker A**: 是的。嗯，有趣的是，我原本认为在……算了，没关系。我不知道。它是在 Codespaces 中运行的，但也许 Code Spaces 仍然在使用本地的……呃，本地的 Wi-Fi。嗯，好吧。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Well, the funny thing is I would think in Well, never mind. I don't know. It's running in Codespaces, but maybe Code Spaces is still using the the local uh the local Wi-Fi. Um, okay.

</details>

### 元数据图与语义层

**Speaker A**: 那么，我们回到这里。基本上，它为了获取这个列表所做的操作是，嗯，它遍历并基本上读取了，嗯，那个元数据图（metadata graph），嗯，然后它创建了，嗯，它想要运行的不同的，呃，查询。你可以看到它运行了那个小型的 SQL，呃，Python 文件，嗯，并且它执行了所有的 select（选择）和 join（连接）操作，以便能够把，呃，这些表整合在一起，这些表基本上列出了，嗯，对那个问题的答案。

<details>
<summary>Original English</summary>

**Speaker A**: So, so we're back here. Basically, what basically what it did to grab this list is um it it went through and it it basically read um that metadata graph um and then it created the um the different uh queries that it wanted to run. You can see it ran that the small SQL uh Python file um and it it did all of its selects and it joins to be able to to pull together uh these tables that list out um the the answer to that question essentially.

</details>

**Speaker A**: 嗯，如果我倒回去看的话，这里的问题是，呃，我们要问什么？回到连接结构（connection shape）。嗯，是的，哪些车辆接收了，你知道的，这边的这些不同的零件。嗯，然后它，它通过品牌（make）显然，嗯，在下面这里提供了那个列表，然后是车辆数量（vehicle count）。

<details>
<summary>Original English</summary>

**Speaker A**: Um if I was to go back the question here was uh what would we ask? Go back to the connection shape. Um yeah, which vehicles received, you know, these these separate parts over here. Um and and it it provided that list um down here by by make apparently um and then vehicle count.

</details>

**Speaker A**: 嗯，所以这就是这第一个结构的基础。你可以想象，随着你的数据开始增长，并且你开始拥有越来越多的表，拥有这个语义层（semantic layer），嗯，然后本质上帮助指导一切如何连接在一起，是非常有用的。呃，在这个例子中，它使用了，呃，BigQuery 内部的 information schema 中的主外键，呃，关系来强制执行这一点。NeoCarta 也可以使用像查询日志（query logs）之类的东西，或者你可以手动将你希望事物如何与其他术语和指标连接在一起的方式组合起来。嗯，关于我们正在处理的这个第一种连接图语义层结构，有什么，呃，问题吗？

<details>
<summary>Original English</summary>

**Speaker A**: Um so that's the basics of this first shape. And you can imagine that as your data starts to grow and you start to get more and more tables, it's very useful to have this semantic layer um to then help essentially guide how everything joins together. Uh in this case, it used a primary foreign key uh relationship inside of the information schema inside of BigQuery uh to enforce that. Neoarta can also use things like query logs or you can sort of manually put together how you want things to join with other terminology and metrics. Um, are there any uh questions about this first sort of connections graph semantic layer shape that we're working with?

</details>

### Neo4j 战略方向与虚拟图

**Speaker B**: 是的，我这里有一个。关于 Neo4j 的。那么问题是，你能不能给我们提供更多关于 Neo4j 近期规划的背景信息，比如我们在战略上正在做什么？

<details>
<summary>Original English</summary>

**Speaker B**: Yes, I have one over here. Neo for you. So the question was can you give us more context into the Neo Forj near quarter like what we're doing strategically

</details>

**Speaker A**: 嗯，关于 Neo4j 在战略上正在做什么，这就在这里，所以作为一家公司，Neo4j，对吧，很长一段时间以来，你都能够将数据导入到我们的数据库中，并以图（graph）的形式表示事物，如果你试图运行这些图特定的查询，这是非常有用的，对吧。所以，如果你有一个供应链的例子，你需要找到从 A 点到 B 点的最佳路线，并且你必须进行这些，比如变长（variable length）、你知道的，最短路径（shortest path）类型的计算。图数据库非常擅长做这个。

<details>
<summary>Original English</summary>

**Speaker A**: um so what Neo Forj is doing strategically and this right here so Neo forj as a company right we're for a long time you've been able to import data into our database and represent things as a graph which is very useful if you're trying to run these graph specific queries right so if you have a supply chain for example and you need to find an optimal route from point A to B and you have to do these like variable length, you know, shortest path type of calculations. A graph database is very good for that.

</details>

**Speaker A**: 但是，图数据库真正擅长做的另一件事，不仅仅是让那些复杂的查询运行得更快，而是实际上提供一种数据的视图或表示形式，允许代理（agent）理解表之间可能存在的相互关系。这样一来，即使最终的连接可能只是一个三跳或四跳（hop）的连接，你也可能必须了解数百个表或类似数量的表才能得出那个结论。

<details>
<summary>Original English</summary>

**Speaker A**: But the other thing that a graph database is really great at doing is not just making those complicated queries run faster, but actually providing a view or a representation of the data that allows an agent to understand how tables might interrelate. So that even though the end join it might only be a three or four hop join, you might have had to understand hundreds of tables or something to be able to arrive at that conclusion.

</details>

**Speaker A**: 所以我们现在把很多精力集中在本体（ontologies）和语义层这些概念上，以及我们称之为虚拟图（virtual graph）的东西上。重点不仅仅是将数据 ETL 进去，而是关于，好吧，也许你想把数据留在原地，并且你仍然想使用 SQL 并在，在你一直使用的方式中访问它，但你需要某种方式来，某种程度上，指导代理以便能够正确地做到这一点。

<details>
<summary>Original English</summary>

**Speaker A**: And so we're focused a lot right now on these concepts of ontologies and semantic layers and what we're calling virtual graph where the focus isn't only just etling data in but about okay maybe you want to keep your data where it is and you still want to use SQL and and access it in in the ways you have been but you need some way to sort of guide the agent to be able to do that correctly.

</details>

**Speaker A**: 嗯，所以 NeoCarta 是一个实验室项目（labs project）。我们还，呃，就在最近，嗯，在预览版中发布了，呃，一个叫作虚拟图的东西，它会很相似，但它本质上为你提供了，嗯，几乎就像这些下推的 Cypher 查询（push down cipher queries）。所以它为你提供了你的，你的数据库的一个图模式（graph schema），然后它允许你直接运行 Cypher，嗯，这可能很有用，因为那样你就可以在查询接口层获得视图，而不仅仅是在元数据语义层。所以，前面的部分中，嗯，有一张表在某种程度上解释了那个，但希望这有帮助，这样你就能明白我们的发展方向。

<details>
<summary>Original English</summary>

**Speaker A**: Um so Neo Carta is a labs project. We also uh just recently um in preview have released uh something called virtual graph which will be similar but it essentially gives you um almost like these push down cipher queries. So it gives you a graph schema of your of your database and then it allows you to run cipher directly um which can be useful because then you sort of have the view down at the query interface level and not just at the metadata semantic layer level. So, there was a table in there um in the previous section that was kind of explaining that, but hopefully that's helpful so you understand kind of where where we're going with things.

</details>

**Speaker C**: 是的。对。图，然后是的。而且我们也在上下文图（context graphs）内部做大量的工作，以及，以及，嗯，以及所有那些层。对。好的。太棒了。嗯，还有其他问题吗？好的，我这里有一个问题。

<details>
<summary>Original English</summary>

**Speaker C**: Yeah. Yep. Grap and Yes. And we're doing a ton of stuff inside of context graphs as well and and and um and all of those layers. Yep. All right. Awesome. Um any other questions? Okay, I have one question over here.

</details>

### OLTP 数据迁移与图数据库的权衡

**Speaker B**: 是的。所以，所以问题是，嗯，为什么我们不拿我们的 OLTP 数据（现在它是一个车辆订单等信息的仓库），然后直接迁移，或者或者它的某个子集。我们为什么不直接把它推入图中呢？

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So, so the question is um why would we not take our OOLTP data which is right now is this warehouse of vehicle orders and and stuff and just migr or or some subset of it. Why wouldn't we just push that into the graph?

</details>

**Speaker A**: 嗯，我认为在很多情况下这说起来容易做起来难，对吧？因为如果你考虑很多生产环境的用例，你可能会有 TB 级的数据，这些数据正在不断地被更新。所以，对吧，如果你必须把这些数据放入图中，你随后将不得不找到某种方法在你把一切移进去的同时同步它。嗯，并且可能会有很多额外的属性或者你需要构建自定义 ETL 的东西，其中有些东西你可能不希望放入图中。

<details>
<summary>Original English</summary>

**Speaker A**: Well, I think in a lot of cases that's easier said than done, right? Because if you think about a lot of production use cases, you can have terabytes of data which gets updated continuously. And so, right, if you had to put that into the graph, you would then have to find some way of syncing that while you move everything in. Um, and there's might be a lot of extra properties or things that you might need to build a custom ETL where there's some things that you might not want in the graph.

</details>

**Speaker A**: 然后很多时候，人们直到陷入这些情况才真正理解的是安全态势（security posture）。因为如果你在一个系统中有敏感数据，即使你在物理上能够把它移进去，出于安全原因，你可能实际上无法获取那些数据并直接把它移到另一个数据库中。嗯，所以，所以有各种各样的原因导致你可能不一定想把你的数据移过去。

<details>
<summary>Original English</summary>

**Speaker A**: And then a lot of times what people end up not really understanding until they get in those situations is the security posture. Because if you have sensitive data that's in one system, it might not even though you could physically move it in, you you might not actually be able to for security reasons take that data and just move it into another database. Um so so there's various reasons why you might not necessarily want to move your data over.

</details>

**Speaker A**: 呃，相比于仅仅这种元数据和语义层图，你能在哪里获得 ETL 的优势呢？那就是如果你有需要那种性能的图查询，对吧？比如我之前举的那个供应链的例子，比如如果你正在进行这些非常庞大的递归连接（recursive joins），并且你需要它们非常快速地发生，或者你需要运行图算法，也许你需要生成图嵌入（graph embeddings），或者你需要进行某种聚类或类似操作，在那种情况下，将数据引入要合理得多。

<details>
<summary>Original English</summary>

**Speaker A**: Uh where you do get an advantage of the ETL over just this metadata and semantic layer graph is if you have graph queries that need that performance, right? So like that supply chain case that I had earlier like if you're doing these really large recursive joins and you need them to happen very quickly or you need to run graph algorithms maybe you need to produce graph embeddings or you need to do some sort of clustering or something in that case it makes a lot more sense to to bring the data in.

</details>

**Speaker A**: 嗯，然后正如我们将在接下来的部分中看到的，当你的数据已经是无结构的时候，呃，将它引入图中是有好处的，因为那样你就能赋予它一个图的结构。好的。我看到这边还有一个问题。是的。

<details>
<summary>Original English</summary>

**Speaker A**: Um and then as we'll see in the next sections when your data is already unstructured uh there's benefits to bringing it into a graph because then you can give it a graph structure. All right. I saw one other question over here. Yes.

</details>

### NeoCarta 图构建机制

**Speaker B**: 所以，所以这个问题是，每次你初始化 NeoCarta 时它会重建图吗？

<details>
<summary>Original English</summary>

**Speaker B**: So the the question is does it rebuild the graph every time you initialize Neo Carta?

</details>

**Speaker A**: 那个问题的答案是不会。它基本上会做的是，当，呃，我们，我们运行那个构建连接脚本时，嗯，它继续执行并运行了一个导入数据的 MCP 服务器函数，嗯，然后一旦它被摄取到 NeoCarta 中，仅仅是元数据，那么它就会留在那里。所以比如对我来说，我没有重新运行那个构建连接，对吧，因为我昨晚刚上了这门课。

<details>
<summary>Original English</summary>

**Speaker A**: And the answer to that question is no. What it will do is basically when uh we we ran that build connection script um it went ahead and ran an MCP server function that ports the data in um and then once it's ingested into Neoarta just the metadata then that stays there. So like for me I didn't rerun that build connections right because I just took the course last night.

</details>

**Speaker A**: 嗯，所以像我这样，我，而且我可能本来是可以运行的，因为我，我认为这是一个幂等（idempotent）加载，但我就是不想去处理它。所以，它就在那里供我使用了，然后我只是在它之上运行了查询。是的。好的。还有其他任何问题吗？在末尾那里还有一个问题。是的。是的。你……

<details>
<summary>Original English</summary>

**Speaker A**: Um so like for me I and I probably could have because I I think it's an item pot and load but I just didn't want to deal with it. So, it was there for me and then I just ran the queries on top of it. Yep. All right. Any any other questions? I have one over here at the end. Yes. Yes. You

</details>

### Neo4j Cypher Skill 与 CLI 工具

**Speaker B**: 是关于，关于 Neo4j Cypher skill。

<details>
<summary>Original English</summary>

**Speaker B**: the the Neo Forj cipher skill.

</details>

**Speaker A**: 嗯，所以我不知道我是否能够，呃，马上快速抓取到它。嗯，我可以给你展示 Neo4j Cypher skill。但这，这些都是由我们的团队在内部开发的。所以如果你去这里，实际上是通过 Neo4j CLI，你可以下载大量这样的 skills。如果你看这里，这有，有 Cypher 的那一个，但随后我们也有不同的 skills，比如针对代理记忆（agent memory）、针对云基础设施、针对不同的驱动程序，比如如果你在使用 Java 或 Go 或者或者所有那些东西。

<details>
<summary>Original English</summary>

**Speaker A**: Um, so I don't know if I might be able to uh grab it really quick. Um, I can show you Neo forj cipher skill. But this is these are all developed internally by our team. So if you go here actually through the Neo Forj CL, you can download a ton of these skills. So if you see here, there's there's the cipher one, but then we also have the different ones for like agent memory, for cloud infrastructure, for different drivers, like if you're using Java or Go or or all those things.

</details>

**Speaker A**: 嗯，所以我不能一定确切地说我们是如何在这个特定的 skill MD 上落地的，但我会告诉你的是，它是由我们和我们的内部团队创建的，他们像是，始终保持更新到最新的，你知道的，Cypher 25、26。嗯，所以，所以它，它拥有所有最新的内容。所以，我，我鼓励你去使用 Neo4j CLI，因为它可以基本上，你可以加载这些 skills 中的一个或多个，并且你将获得那里的最新知识，因为否则它，它将要做的是去互联网上获取大约四五六年前的 Stack Overflow 问题，并且它将给你提供过时的糟糕的 Cypher，基本上就是这样。

<details>
<summary>Original English</summary>

**Speaker A**: Um, so I can't necessarily say exactly how we landed on this particular skill MD, but what I will tell you is it was created by us and our internal teams who are like always up to date on the latest, you know, cipher 2526. Um, so so it it it has all of the latest. So I' I'd encourage you to use the Neo Forj CLI because it will basically you can load one or multiple of these skills and you'll get the latest knowledge there because it otherwise what what it's going to do is it's going to go on the internet and get the Stack Overflow questions from like four or five or six years ago and it's going to give you outdated bad cipher basically.

</details>

**Speaker B**: 那个 CLI（工具）？

<details>
<summary>Original English</summary>

**Speaker B**: CLI

</details>

**Speaker A**: 它是。是的，它被加载进去了。并且呃如果你看看嗯我们在 dev container 内部使用的那个 install 文件，呃你会看到嗯我们在哪里安装了 Neo4j agent client、那个 skill。所以那里面的那些命令，嗯，那，那基本上允许你去那么做。好了，我要拿……

<details>
<summary>Original English</summary>

**Speaker A**: it is. Yes, it is loaded in. And uh if you look at the um the install file that we use inside of dev container, uh you'll see um where we installed the Neo Forj agent client, the skill. So the commands in there um that that basically allowed you to do that. All righty, I'll take

</details>

<!-- chunk 5/12 -->

### 问答环节与 Neo Carta

**Speaker A**: 还有一个问题，然后我想我必须进入下一个部分了，除非没有其他问题了。好的，请说，就是那边的朋友。

<details>
<summary>Original English</summary>

**Speaker A**: one more question and then I think I'll have to move on to the next section unless there isn't another one. Yes, right there.

</details>

**Speaker A**: 嗯，关于 Bronze 层，就像不同的 Delta 表那样，所以我的意思是，我们基本上正在探索传统的、类似于 SQL 的结构化数据仓库。而 Neo Carta 对我们来说真的是由客户需求所驱动的。它是由我们的现场团队开发的。所以，当客户走进来，他们对缺乏结构化或者较少结构化的数据有疑问时，甚至像文档这类东西也已经被考虑纳入 Neo Carta，因此现在正形成这样一个不断增长的待办事项列表（backlog）。一切发展得都非常快。我想，我的意思是，Ryan 应该就在这个房间里的某个地方，他或许能够详细谈谈 Neo Carta 的下一步是什么。但我知道我们现在正在开发一个 Databricks 连接器，可能还会推出一些指标视图以及其他各种新功能。

<details>
<summary>Original English</summary>

**Speaker A**: um bronze so like the different like delta tables where um so I mean we're we're exploring basically um the traditional like SQL structured data warehouse and then NeoAR Carta is really customer-driven for us. It was made by our field team. So as customers come in and they have questions about less un less structured data um and even things like documents have been considered for Neo Carta and so there's this backlog that's forming right now. Everything's moving very fast. I think I mean Ryan is is somewhere in the room and he might be able to to speak on sort of what's what's the next thing for Neo Carta, but I know we're working right now on a data bricks connector um and maybe some metric views and other things.

</details>

**Speaker A**: 好的，太棒了。所以讲座之后大家可以去和 Ryan 交流，我想在 YouTube 上观看直播的每个人之后也可以去和 Ryan 交流，不过到那时候，我们就会拥有一个非常出色且令人惊叹的 Neo Carta 了。好吧。为了节省时间，我得继续往下进行了，因为我们马上就要到达 15 分钟的进度，也就是过半的时间点，而且在中途的某个时刻休息几分钟，让我们自己稍微喘口气、调整一下，也许是个很不错的主意。所以现在我要直接跳到下一个部分。

<details>
<summary>Original English</summary>

**Speaker A**: >> All right, awesome. So meet with uh with Ryan afterwards and then everyone watching on YouTube I guess can meet with Ryan afterwards but by then we'll we'll have we'll have an amazing Neil Carta. So all righty. So so let me go ahead and move on for sake of time because we're coming 15 minutes on the halfway point and it might be nice to take a few minute break at some point in the middle just to just to give ourselves a little bit of a breather. So now I'm going to jump to the next section.

</details>

### 处理非结构化数据：文档与图谱表示

**Speaker A**: 刚才我们处理的是结构化数据，现在我想探讨并处理非结构化数据了。这将是关于文档的部分。大家如果来看一下我们这里关于源数据的一些内容。在这个例子中，我打算在本地读取并加载它们。不过你要知道，无论是从云存储中读取，还是在本地磁盘读取，通常并没有巨大的差别。基本上，我们的这些公告是 PDF 格式的。我们还有篇幅要长得多的操作手册。然后我们也有车辆召回通知。因为现在的视图给我呈现出一种有些奇怪的显示效果，所以我也把它们放在了这个原始语料库（raw corpus）中，也就是在这些 Markdown 文件里。但是大体上，存在着这些包含多个部分的复杂文档。并且你会在这里清晰地看到，它们会进行这种跳转链接，以便导航到其他文档中的不同部分。所以，当它们相互引用时，它们都在某种程度上紧密地交织、关联在了一起。

<details>
<summary>Original English</summary>

**Speaker A**: And so that was working with structured data and now I want to work with unstructured data. And this is going to be the documents part. So we have if we go over to our little uh our little uh source data stuff here. So in this case I'm going to read them locally to load them. Um but you know it's reading from cloud storage reading locally. Um there there often isn't a huge difference. Um basically we have these bulletins in PDFs. Um we have manuals which are considerably longer. Um and then we have recalls as well. And because it's giving me this funky view, I also have them in uh in this raw corpus where they're they're inside of um these uh markdown files here. Um, but basically, uh, there are these multi-section documents. Um, and you'll see here that they have, uh, this linking that they do to go over to different sections in other documents. So, they're all kind of interlin together as they refer to one another.

</details>

**Speaker A**: 举个例子，就在这本具体的系统手册里面，它讨论了用于这个 ABS 系统的不同的平台代码，以及相关的诊断故障排除方法，对吧？然后它会通过超链接直接跳转到那里。顺便说一句，这里所有的这些数据都是我自己模拟出来的。它们并非商业敏感数据或任何类似的东西。但它的目的是模拟某种真实的现实世界系统环境，在这个系统中，你拥有所有这些不同型号车辆的详尽手册、安全公告和召回通知。

<details>
<summary>Original English</summary>

**Speaker A**: Um, so, for example, right inside of inside of this manual, um, it talks about these different platform codes for this ABS system, um, and diagnostic troubleshooting, right? and it will link over to there. All of this data, by the way, is I simulated. It's not sensitive or or anything like that. Um, but it's meant to simulate kind of a real world uh system where you have these manuals and bulletins and recalls of all these different vehicles.

</details>

**Speaker A**: 我们希望通过这个实现的基本目标，简单来说，就是我们想给我们的智能代理（agent）提供一个目录（table of contents）。我说的目录，是指看起来像屏幕上展示的这个东西一样的结构。所以，我希望允许代理在这里执行的操作不仅仅局限于搜索关键术语。我们当然也会赋予它强大的搜索能力，但我不知道是否有人听说过像 Page Index（页面索引）这样的东西？有人知道他们是谁或做什么的吗？也许你们中的一些人听说过。所以，有一种关于在你的各种文档中进行导航的理念，它基本上就像人类阅读实体书里的目录一样直观。我不想称之为大纲（outline）。我将其准确地称为目录（table of contents）。我确实需要把这些术语对齐得更好一些。但这里的核心想法是，你可以去阅读这些缩进层级，你可以清楚地看到你有一个文档，或者在这个例子中是一个知识库（library）。你有一个名为“公告（bulletins）”的文件夹，它是一个子文件夹。然后在这个子文件夹下面有这些具体的文档。因此你就拥有了这种层次分明的包含关系树（containment tree）。除了给你提供所有这些部分的包含关系树之外，你还有可以带你直接跳转进入不同文档的这些内部链接。所以它远远不仅仅是一个向下延伸的树状目录那么简单。它还有这些网状链接，对吧？而且这些链接，以及这里面的基本上所有实体元素，都有一个唯一的 URI。

<details>
<summary>Original English</summary>

**Speaker A**: And um what we want to accomplish with this basically is we want to give our agent a table of contents. And and by a table of contents, I mean something that looks like this thing. So, what I want to allow the agent to do here is not just search for key terms. We'll give it search too, but I don't know if has anyone heard of like page index? Anyone know who they are? Maybe some of you. So, there's so there's this idea of navigation through your documents where basically almost like a human if you look at the table of contents inside of a book and not I'll call this outline. I'll call it table of contents. I need to get the terminology a little bit better aligned. But the idea here is that you can sort of read the indentations and you can see how you have a document or in this case a library. You have the bulletins which is a subfolder. Then you have these documents underneath. And so you have this containment tree. And then in addition to that containment tree that gives you all these sections, you also have these links that'll take you to a different document. So it's more than just a table of contents that's a tree that goes down. It also has these links, right? And these links and basically everything in here have a URI.

</details>

**Speaker A**: 我们的构想是，如果我们能想出一个优秀的图谱（graph）数据表示方法，我们就可以让这些层级化的 URI 发挥巨大的作用。所以你会看到，比如你在这里拥有一个完整的技术库（technical library），对吧？然后其下级是斜杠 bulletins（/bulletins）。因此，如果我深入到这个底层的 TSB 召回通知节点，我就知道它是“公告（bulletins）”的一部分，或者更准确地说是安全公告，而不是召回通知，并且它最终是整体技术库的一部分，就像它在这里也链接到了一本相关操作手册一样。你可以看到手册的名称，然后它位于手册（manual）的子文件夹中。如果我有了那个特定的 URI，我就可以提取它，把它输入到系统中，实际上我就可以直接从图谱中抓取一个节点，该节点包含了原始文本，甚至可能是一个直接指向原始文本的链接。所以，如果我把这个输入进去，稍后我们将看看它如何与大纲配合工作，我实际上可以获取这些完整的数据子树，这样我就可以深入钻研、挖掘这些不同的内容片段。这就是这项工作背后的大致想法。因此，这赋予代理的能力不仅仅是像传统的向量搜索（vector search）或词法搜索（lexical search）那样的检索功能，而是在某种意义上真正地穿梭、智能地导航于这些错综复杂的文档之中。

<details>
<summary>Original English</summary>

**Speaker A**: And the idea is that if we can come up with a good graph representation, we can basically make it so that these URIs which are hierarchical. So you see like you have your technical library here, right? And then slashbulletins. So, like if I'm down in, you know, this TSB recall notice, I know that it's part of bulletins, um, or safety bulletin, rather, not a recall, and it's part of a technical library, just like it's also linking to a manual here. Um, and you can see the name of the manual, then it's inside of the manual subfolder. Um, and if I have that, I can take that and I can plug it in and I can actually grab a node from the graph that has like the raw text or or even a link to the raw text. And so, and then if I uh plug this in and we'll see how this works with outline later, I can actually get these sub trees so I can like dig in and drill down on these different pieces of content. Um, that's the general idea with this. And so what this gives the agent to do is not just search like vector search or or lexical search but actually kind of traverse through the documents in a sense.

</details>

### GraphRAG 与图谱构建过程

**Speaker A**: 在这个具体的例子中，我们要使用的数据模型，实际上需要我们把原始数据导入到图谱（graph）数据库中。我有一个快速的问题要问在座的大家。大家这里都熟悉 GraphRAG 的概念。当你们想到 GraphRAG 时，也许有人可以举一下手，我来挑个人简单互动一下。我想让你们告诉我，你们认为构建 GraphRAG 的图谱过程是怎样的？我不知道是否有人足够熟悉并且愿意自告奋勇。你要举手了吗？

<details>
<summary>Original English</summary>

**Speaker A**: Um and the data model that we're going to use in this case we're actually going to import the data into graph. Um I have a I have a quick question for everyone. So, everyone here is knows Graphrag. When they think of Graphrag, and maybe someone can raise your hand and I'll I'll pick on someone for a second. I want you to tell me what you think like the pro the the building the graph process is for Graph Frag. So, I don't know if anyone wants to wants to volunteer if they're familiar. You're going to raise your hand.

</details>

**Speaker B**: 是的。对。他们根据数据构建，构建那些关联链接……从……

<details>
<summary>Original English</summary>

**Speaker B**: >> Yes. Yeah. And they build they build the they build the links from from the

</details>

**Speaker A**: 构建的方法有很多种不同的方式，对吧？我没记错的话，当你谈到创建一个图谱时，你提到过你是从散布在文档内部的数据中构建这些链接的，对吗？所以在使用 GraphRAG 时，我们通常也会有一个复杂的实体抽取（entity extraction）环节作为其中的一部分。我们可以使用大语言模型（LLM）向它发出指令说，嘿，从图谱中提取出不同的独立部分、不同的车辆信息模型，让它们成为图谱中单独的实体节点，然后让这些生成的链接精准地指向原始的文档数据块以及所有这些相关联的内容。这种做法非常棒，而且在实际应用中效果非常好。

<details>
<summary>Original English</summary>

**Speaker A**: So there's different ways, right? And and you said I think in in your when you talk about creating um a graph, you build the links from the data that's inside of the documents, right? And so graph rag oftentimes we have an entity extraction piece to it as well. So we can use an LLM to kind of say hey like extract the different parts the different vehicles from the from the graph and have them be separate entities and then have those links to like the original document chunks and all all of this stuff. And that's great and that works really well.

</details>

### 确定性图谱构建的优势与应用

**Speaker A**: 但在这里，我将要向你们展示的是一种量级轻得多的、更为简便的方法，而且我想这也许正契合你刚才所要表达的观点，我们实际上要使用一种确定性的加载方式（deterministic loading）。大家可以看看屏幕上，这里的图谱结构的工作方式是，你首先会有一个顶层资料库，然后你会有一个准确反映我们刚才所见层级关系的包含关系树。这一切真正在做的事情其实就是进行结构拆解，你会清晰地看到文件夹层级、文档层级，然后这些文档内部又有各个段落部分（sections），它们可能包含多个不同部分，并且这些部分也会在不同的层级结构上相互深度嵌套。

<details>
<summary>Original English</summary>

**Speaker A**: Um here what I'm going to show you is something that's much more lightweight and I think maybe to the point that you were making um we're actually going to use a deterministic loading. So if you see here the way that this graph structure is going to work is you're going to have your library and then you're going to have this containment tree that reflects what we saw. And all this is really doing is it's breaking down, you see the folders, the document, and then these documents have sections and they can have multiple sections that will also nest underneath each other at different section levels.

</details>

**Speaker A**: 然后你会有指向下一个逻辑部分的链接（next section links）。这样一来，你不仅获得了一个严格的排序概念，而且还明确了链接的指向目标。在这个具体的案例中，我们使用的是这些命名链接，有点像你可能在个人知识管理软件 Obsidian 的知识库中经常看到的那种双向链接机制，但你完全也可以使用标准的超链接（hyperlinking）或其他技术方案来实现，这完全取决于你的底层数据长什么样。所以，无论是严谨的包含关系树，还是各个部分的阅读顺序以及内部链接，一切操作都是确定性的。采用这种确定性加载方式（deterministic load）的巨大好处在于，第一，它在数学和程序逻辑上是幂等的（idempotent），即多次执行结果一致。因此，在初始的加载和构建阶段你根本不需要依赖昂贵且不可预测的大语言模型（LLM）。通常这种做法在执行速度上也会快得多。所以，如果你手头已经有了一些自带大量内在层级结构和大量人工或者机器生成的相互链接的系统文档，有时候为了能够快速启动项目并让系统运行起来，采用这种直接的图谱构建方式会非常有利、非常高效。我倾向于说，这更像是一个专注于词法解析或文档目录结构的图谱，而不是那种依赖完整的实体提取（entity extraction）复杂流水线所创建出来的语义图谱。

<details>
<summary>Original English</summary>

**Speaker A**: Um, and then you'll have um next section links. So you get a concept of ordering as well as linked to which uses in this case we're using um these named links uh sort of like you might see inside of an Obsidian vault a little bit um but you can also do it with hyperlinking and other things depending on depending on what your data looks like. So, it's all deterministic with the containment tree for one and then the ordering of the sections as well as the links. Um, and the benefits of having a deterministic load like this is number one, it's going to be item potent. Um, so like you're not relying on an LLM in the beginning. Um, it's often going to be a little bit faster. Um and so if you already have documents which have a lot of inherent structure to them and a lot of interlinking um sometimes just to get something up and running quickly it can be very beneficial to approach a graph like this where I'd say it's more of a lexical or document structure graph rather than like a full like entity uh you know extraction type of pipeline to create a graph.

</details>

**Speaker A**: 这里的文档内容详细解释了我刚才说明的不同的内部链接类型。正如我之前所强调的那样，这些 URL 本身就承载着一种严格的树状层级结构。比如，图中的每一个节点，就像资料库顶部的那个核心头节点（head node），会获得它的根 URI；如果是下级的手册（manuals），就会在那个根 URI 的基础上加上反斜杠 manuals（/manuals），以此类推，不断向更深层级延伸。

<details>
<summary>Original English</summary>

**Speaker A**: Um and it it explains here what I just said with the different link types. Um and then and and like I said before these URLs carry a hierarchy. So every node for example that that head node at the top here for the library will get its URI manuals will have that plus back slashmanuals um going down sort of the

</details>

<!-- chunk 6/12 -->

### 脚本与图谱构建

**Speaker**: 包含关系树一直延伸到文件名以及不同的部分，这就是你需要复制并加载进来的脚本。所以基本上，你同样要拿着这个，来到这边。你会打开你的 Bash 终端。我相信我已经执行过这个操作了，所以我不会再运行一遍，尽管我很确定它是幂等的。不过基本上，一旦你运行了它，你最终得到的结果就是——我来确认一下它确实在图谱中。对我来说是的。你最终会得到我们刚刚看到的那个模型。这应该只需要——嗯，如果 Wi-Fi 慢的话可能会花点时间，虽然我觉得应该不会。但是，它会为你创建这个图谱，在这里你再次看到了位于顶部的文件夹结构，也就是我们的技术库（technical library）以及文件夹，然后你可以看到我们的文档在上方跟进，划分到不同的部分中。如果我在这里放大，你会看到我们在下一部分有“has links（包含链接）”，但随后我们也有具体的链接。我可以进去点击这些节点，你就能大致看出整个东西是如何生长的，以及所有内容是如何相互链接的。

<details>
<summary>Original English</summary>

**Speaker**: containment tree to the to the file name and then the different sections and um this is the script you're going to copy to load it in. So basically again you'll take this, you'll go over to here. Um you'll open your bash terminal. Now I believe I've already done this so I'm not going to run it again even though I I'm pretty sure it's item potent. Um but basically once you run that um what you'll end up getting is and I'll just make sure it's actually in the graph. It is for me. You'll end up getting that uh that model that we just saw. It should only take Well now it might take a while if the Wi-Fi is slow. although I don't think it should. Um, but it'll create this graph for you where you have again your top of the folder structure which is our technical library, our folders, and then you can see we have our documents followed up here into our different sections. And if I were to zoom in here, um, you'll see we have the has links in the next section, but then we also have the links too. And I can go in and click on these and you can see kind of how the thing grows and everything kind of links to each other.

</details>

**Speaker**: 既然我们已经有了这个，那么基本上在下一部分，我们就可以着手构建我们的工具了。基本上，与我们创建的自定义自动修复（autofix）技能相配套的脚本，实际上是为了创建我们一开始看到的那个大纲形状，也就是要交给智能体的目录。所以如果我进入下一部分，再次重申，就像我说过的那样，我在这里想做的是直接复制这个。这就是提示词（prompt）。如果我把它喂给我的 Claude，它应该就会开始工作。因为我知道这会花一些时间，所以我会让它在这里开始运行。但它在过这一遍时实际上在做的是，如果我进入并查看我的技能（skills），你会看到我在里面留下了这个连接查询。这就是它需要创建的查询，以便能够生成那个大纲的形状。我在这里的自然语言中指示它使用 Neo4j Cypher 技能，并参考一个采用文档大纲格式（doc outline format.md）的规范（spec）。这就是我编写更复杂的 Cypher 查询和更复杂的图查询时通常喜欢采用的方式：我会为它写一个规范。

<details>
<summary>Original English</summary>

**Speaker**: And now that we have that, um, basically in the next section, we can go ahead and build our tool. Um, basically the script that goes along with our our custom autofix skill that we've created uh to um to actually like create that outline shape that we saw in the beginning, the table of contents to hand our agent. And so if I go ahead to that next section, um, and again, like I said, what I want to do here is I'm going to go ahead and copy this. This is the this is the prompt. Um, where if I go ahead and feed that to my claude, it should go ahead and get to work. And because I know that's going to take a while, I'm going to have it start running here. But basically, what it's doing as it goes through um is if I go under and I look at my skills, um you'll see that I left inside of here um this wired query. This is this is the query that it needs to create um to be able to create that outline shape. And I've instructed it inside of the language here to use the Neo Forj cippher skill and reference a spec in doc outline format.m MD. So this is generally how I like to write more complicated cipher queries, more complicated graph queries is I'll write a spec for it.

</details>

**Speaker**: 那么如果我进入 docs 文件夹，你会看到我把规范都放在了这里，我有一个大纲格式的规范，我在里面声明“这就是形状，对吧？”。然后它在这里讨论了它需要具备良好的人类可读性，并且，是的，我们允许你进行编辑，以及它需要包含的一些可选参数。因为很多时候我们有的就像是伪代码，我们并不确切知道如何将其组合在一起。在这种情况下，我确实给了它关于使用变长路径查询（variable length path query）的提示，基本上是为了把所有东西按顺序排列好。然后当它完成时它会说一声。所以基本上，你从中得到的结果是，如果我回到这里，它会稍微讨论一下——你会在文件中看到，实现这个的关键之一是它执行了这个包含边的操作，你可以看到这个 `*0..25`，它实际上是在查询内部被参数化的。就像，如果我回到修改发生的地方，如果我回到这里，它是在这个字符串中被参数化的。所以这就给你提供了一个选项，让你决定想要遍历多深。这也就体现了在拼凑这个目录时的图性质。这里还有第二个查询，它简单得多，只是在那之后抓取链接。

<details>
<summary>Original English</summary>

**Speaker**: Um, and so if I go to my docs folder, you'll see I'll have my specs in here and I have my outline format spec where I say this is the shape, right? And then it it talks here about how it needs to be human readable and uh yes, we will allow you to edit and um and some of the optional arguments it needs to have. So, right, because oftent times it's like pseudo code that we'll have and we don't know exactly how to put it together. Um, um, in this case, I did give it the hint about having a variable length path query uh to basically put everything uh put everything in order. [snorts] And then it will say when it's done. And so basically what you'll get out of that is if I go back here and it will talk a little bit about like one of the keys to this you'll see in the file is it does this thing here which it goes has which is that containment edge and you see this star 0.25 it's actually parameterized inside of the inside of the query. So like uh if I go back to my um me go to where it changed um if I go back to here it's it's parameterized inside of this string. So it gives you like an option to how deep you want to traverse. Um and that that's sort of the graphy nature of kind of putting together this table of contents. There's there's a second query in here too which is much simpler which just grabs the links after that.

</details>

**Speaker**: 基本上，一旦那个步骤完成，我就可以去运行整个脚本了。如果你只是运行这个脚本，而不带任何深度（depth）参数，或者没有指定的 URI，它就会返回图谱中的所有内容。因此，如果是面对一个更大的图谱，我就不会用这种方式运行它。我们在这里能行得通，是因为我们只有几百个文档。所以在这个情况下我可以这么蒙混过关。但如果我那样运行它，它会返回大量的数据。不过，你大概可以在这里看到，缩小一点看。所以，你可以看到，对吧，它给我返回了这个。你可以看到很多这样的文档，重申一遍，这不仅仅是结构，而是它在提供所有文档之间的链接。然后利用这个你可以做的是，你可以给它提供一个可选的深度参数。举个例子，如果我只说 `depth=1`。你不喜欢清理到底部，那么我指定深度为 1。如果我这样做了，它就会继续执行并只往下走一层。

<details>
<summary>Original English</summary>

**Speaker**: Um so that basically uh once that's done I can go ahead and um copy I'll run the whole thing. If if you just run the script without any depth parameter or without a specific URI, it's going to return everything in the graph. So it wouldn't be the way that I'd I'd run it with with a larger graph here. We end up with because we only have a couple hundred documents. Um so I can get away with it here. Um, but if I ran that, um, it'll it'll bring back a ton. And, but you can kind of see here, um, zoom out. So, you can see, right, that it gave me this. And you can see how a lot of these documents again, it's not just the structure, it's like the links between all of them that it's that it's providing. Um and then what you can do with this right is you can give it an optional depth parameter. So for example, if I just said depth equals one. Uh go you don't like clearing to the bottom and I say depth one. Then if I did that um it'll go ahead and just go one down.

</details>

**Speaker**: 然后它还有另一个很酷的地方，那就是你可以为它提供一个特定的 URI。所以如果我在这里看到一个我想要交给它的特定 URI，那么它基本上就会从那个 Falcon 2.0 节点文档开始。就像，如果我现在在这里说：“好吧，其实我想执行它，但我想针对我在上面看到的某个东西来执行，比如也许链接到了这个线圈识别（coil identification）的东西。”我可以去把那个 URI 抓取过来，然后把它放到脚本里，接着它基本上就会把那个文档以及它链接到的所有内容都返回给我。所以你可以看到，智能体现在是如何去遍历、抓取这些 URI 并穿梭于整个图谱之中，从而为自己提供这些层次化和带有链接的视图的。好的，对，我们花点时间来提问吧。我们中间这里有一位。好吧，所以，在课程的后半部分，我会在这里的研讨会上的最后几个问题中，指示智能体准确说出它遵循了哪些步骤。你有看到它使用过什么不同的东西吗？

<details>
<summary>Original English</summary>

**Speaker**: And then the other cool thing with this too is you can provide it a specific URI. So if I saw you know a specific URI here that I wanted to give it um then it will basically start at that Falcon 2.0 no document just like you know if I um if I was here now and say okay well actually you know I want to do um I want to do it but I want to do it for something that I see up above like maybe this links to you know this um coil identification thing I can go ahead and snag that URI and then I can put it in the script and then it will basically give me you know that document and everything it links to. So you can say see how an agent can go through now and sort of grab these URIs and kind of traverse all through the through the graph and give itself these hierarchical and and linked views. Um the okay yeah why don't we why don't we take a second for questions. So we have one in the middle here. Um well so later in the course I'll in the workshop here for some of the last questions I do instruct the agent to say exactly what steps it followed. Um are you seeing it use something different?

</details>

### 工具调用与验证

**Audience Member**: 对的。

<details>
<summary>Original English</summary>

**Audience Member**: Right.

</details>

**Speaker**: 是的。所以这应该在工具调用历史（tool call history）中是显而易见的。所以你可以查看它所进行的不同工具调用，因为在比如说 connection（连接）的情况下，它正在调用一个 MCP 服务器。所以那些信息应该在你的工具调用记录里。顺便说一下，为了让大家都清楚，如果你们刚才没听到的话，那个问题就是：“你怎么知道智能体是否真的在调用它应该调用的东西呢？” 对，所以以 Cloud Code 为例，你可以查看工具调用历史，在这个课程中，我非正式的做法是，对于某些提示词，我会直接指示它：“嘿，请清楚地说明你使用了哪些步骤和逻辑才能够回答这个问题。” 显然，如果是对于生产系统，你会去查看日志等内容，但在这里为了学习，我会以这种方式将其暴露出来。那么，关于树和概要，大家还有没有其他问题？

<details>
<summary>Original English</summary>

**Speaker**: Yeah. So it should be apparent in the tool call history. Um so you can you can look at the different tool calls that it made because in the case for example of connections it's calling an MCP server. So those should be inside of your tool calls. And the question by the way for everyone if if you couldn't hear um it was just how do you know that the agent's actually calling the things that it's supposed to right yeah so so for cloud code for example you can look at the tool call history um and informally what I'll do in this course is for some of the prompts I'll I'll just direct it to say like hey like clearly like say like what steps and logic you use to be able to to answer this question. Um, you know, obviously for a production system, you would you would want to look at the logs and everything, but for here and for learning, I I that's how I'll I'll expose it. Um, is there are there any other questions about uh trees outlines?

</details>

**Audience Member**: 是的。这边有一个。

<details>
<summary>Original English</summary>

**Audience Member**: Yes. One right here.

</details>

**Audience Member**: 是的。

<details>
<summary>Original English</summary>

**Audience Member**: Yeah.

</details>

**Speaker**: 是的。所以，嗯，它所有的代码应该都在……噢，对了，我们需要重启一下。噢，那是一个不同的代码库。谢天谢地。好的。是的，在 load 内部，如果你查看 `load documents`，这只是 Cypher 查询。然后你在这里的下方有你的解析语料库（parse corpus）。所以，是的，它基本上只是在这里使用正则表达式来尝试寻找正确的内容。在这种情况下，文档已经具有相当好的结构了，对吧？所以具体效果可能会因你的文档源而异。在这个场景下，如果你有大量的手册，并且它们的结构通常是一致的，那你就可以用正则表达式和简单的 NLP 技术来应付。如果它更加杂乱，你可能就需要使用，比如，你知道的，gler 或者不同类型的 looms 工具，应对这种情况会存在不同的复杂程度阶段。好的。是的，我们这边有个问题。

<details>
<summary>Original English</summary>

**Speaker**: Yeah. So, um it is uh all the code for that should be in uh oh yeah, we'll need to restart. Um oh, that was a different codebase. Thank Thank goodness. All right. Um yes, inside of load, if you go to load documents, this is this is just the cipher queries. And then you have your parse corpus um down here. So yeah, it's basically just using regx in here to try to find, you know, the the right stuff. In this case, the documents are already fairly well structured, right? So mileage may vary depending on what your document sources are. In this case, right, if you have a lot of manuals that are often structured the same way, then you can get away with sort of regex and plain NLP techniques. If it's messier, you might have to use like um you know, gler or different types of looms and there's stages of complexity for that. All right. Yes, we have a question over here.

</details>

### 模型兼容性

**Audience Member**: 是的。

<details>
<summary>Original English</summary>

**Audience Member**: Yes.

</details>

**Speaker**: 是的。它可以和任何模型一起工作。唯一的一点是，NeoCarta 以及这些工具中的任何一个——好吧，我先从 NeoCarta 说起。NeoCarta 真正负责的是创建那个语义层元数据图谱，并为你提供一个 MCP 端点。所以，只要你能访问那个 MCP 服务器，它就是与模型无关的（model agnostic）。好的，所以刚才那个问题是关于“我们这里使用的是 Opus 4.8，那我们可以使用任何其他类型的模型吗？” 那个问题的答案是，是的，我们正在使用……

<details>
<summary>Original English</summary>

**Speaker**: Yep. Can be done with any model. The only thing that Neoarta and any of these tools well neo I'll start with neocarta neocarta is really responsible for creating that semantic layer metadata graph and providing you an MCP endpoint right so as long as you can access that MCP server it's model agnostic okay so that was that was a question about basically we're using opus 4.8 here and can we use any other type of model and the answer to that question is is yes we're using a

</details>

<!-- chunk 7/12 -->

### 决定关系命名与图数据库建模

**Presenter**: 技能框架（skills framework），然后对于 Neo Carta，我们有 MCP。Neo Carta 也有一个 CLI，所以还有其他方式可以访问它。好的，最后排那里有一个问题。所以这个问题是，如果我没理解错的话，你是问如何决定如何命名你的关系（relationships），它们需要多具描述性，以及由谁来命名这些关系。

<details>
<summary>Original English</summary>

**Presenter**: skills framework and then in and then for Neo Carta we have MCP um Neo Carta also has a CLI so there's there's other ways to access it too um I have one question all the way in back there So the question is around if if I'm understanding correctly, how do you decide what to name your relationships and how descriptive they have to be and who is naming the relationships.

</details>

**Presenter**: 在当前情况下，我们的负载是非常确定性的。所以我们会提前决定如何命名我们的关系。这在一定程度上是个人偏好或者判断的问题，对吧？我试图在这里保持简单，“has”（拥有/包含）就非常简单。这是一个包含关系。我也知道我需要多层次的包含关系。因此，我可能希望为所有这些层级使用一个通用的名称，因为如果我使用像“has_folder”（包含文件夹）、“has_document_section”（包含文档部分）这样的命名，会让 Cypher 查询变得复杂。这就是为什么我把命名保持得非常简短的原因。

<details>
<summary>Original English</summary>

**Presenter**: So in this case, we have a very deterministic load. So we're deciding ahead of time what to name our relationships. Um, and that is a bit of a a taste or a judgment call, right? Uh, I tried to keep it simple here where has is very simple. It's a containment relationship. I also know that I'm going to want containment going multiple levels. So, I probably want a common name for all of those because if I have like has folder, has document section, it makes the cipher complicated. Um, so that's sort of why I kept that naming very short.

</details>

**Presenter**: 对于链接（links）也是如此。你在命名上越细化，你的智能体（agent）和终端工具在构建查询时基本上就可以越详细。但是，这样一来，你的数据模型就会变得越复杂。所以，这是你需要去权衡和管理的事情，因为如果你最终进入一个生产环境场景，在其中你有数百种不同类型的关系，那么在上下文窗口中管理这些关系可能会变得很困难，这可能会导致模型在构建那些 Cypher 查询时不太顺利。

<details>
<summary>Original English</summary>

**Presenter**: Same with links too. Um the more granular you get with naming um basically the more sort of detailed uh your agent can be and your end tools can be in putting a query together. But then the more complicated your data model becomes. And so it's a little bit of a thing that you have to manage because if you end up in like a production scenario where you have hundreds of different types of relationships um that might get hard to manage inside of a context window and it can lead to models maybe not having the easiest time putting those cipher queries together

</details>

**Audience Member**: 比如如果是用像 Neo4j CLI 这样的工具或者人类来操作的话，对吧？也就是当我们试图去编写我们自己的参数化查询时。

<details>
<summary>Original English</summary>

**Audience Member**: with something like the Neo Forj CL or humans, right? When we're trying to, you know, write our own uh sort of parameterized queries.

</details>

**Presenter**: 是的，这也是事实。我们也看到了这一点，这也是数据仓库端关于语义层（semantic layer）的完整论点：你可以拥有这些指标视图（metrics views）和其他使用业务术语的东西，它们可能与你拥有的物理数据模型不同，对吧？所以，这也是为什么我们需要这些元数据图（metadata graphs）的部分原因——为了帮助管理它们之间的这种差异（delta）。我再回答几个问题，然后我们继续。请讲。

<details>
<summary>Original English</summary>

**Presenter**: Yep. Yeah, that's true too. Um, and we see that right that that's the whole semantic layer argument too with on the warehouse side is you can have these metrics views and other things which use business terminology that might be different from sort of the the physical data model that you have, right? Um, and so that's that's part of the reason why we have these metadata graphs to to help manage that sort of different or that delta between them. I'll take a couple more questions and then we'll we can move on. Yep.

</details>

### 图检索与语义搜索的互补性

**Presenter**: 这是一个有趣的问题。（你问这是否是语义搜索的替代品，）我认为称其为替代品未免太天真了，因为我看到大多数使用这项技术的人最终都会结合某种混合向量检索或全文搜索。在这类工作中，我至少会使用全文搜索。所以，我不认为它是一个替代品，但正如我们在课程后面讲到一些宏观（estate level）问题时会看到的那样，有些问题语义搜索并不擅长回答，它们真的需要文档导航来理解所有的东西是如何连接在一起的，对吧？

<details>
<summary>Original English</summary>

**Presenter**: >> Yeah, that's an interesting question. Um, I think it would be naive to call it a replacement because most of the people that I see using this will eventually incorporate some sort of hybrid vector retrieval or full text search work I do. I use at least full text search um, with this sort of stuff. So, I don't think it's a replacement, but as we'll see later in the course when we get to some of the estate level questions. Um, there's certain things that semantic search is not as great at answering that really require document navigation to understand how like everything connects together, right?

</details>

**Presenter**: 一个很大的例子就是证明某个东西不存在。你如何用语义搜索做到这一点呢？或者理解，比如说，某些特定文档可能关联着不同部分之类的。理论上，你可以做大量的向量查询来不断提取段落，但是有更大的几率出错，你可能抓取不到正确的文档等等。所以，刚才的问题是它是否是语义搜索的替代品，我认为不是的。不是。好的，后面还有一个问题。

<details>
<summary>Original English</summary>

**Presenter**: Um, so big examples would be like proving something doesn't exist. Like how do you do that with semantic search, right? or understanding um even like how you know there might be different parts related to a specific document or something. You know, you could in theory do like a bunch of vector queries to keep pulling passages, but there's more, you know, chance for error that you might not catch the right document and all this sort of stuff. Um so yeah, not the question was if it's a replacement for semantic search and I don't think it is. No. Um, one more in uh back there.

</details>

**Presenter**: 这个问题是，我们是否要重新定义节点的类型以及关系，所以这是一个关于如何决定节点标签（node labels）应该是什么的问题吗？是的。同样，这也是一个数据建模的问题，对吧？比如可能会有这样一种情况，我们看看刚才讲过的数据模型。嗯，不在这里，在我的上一个幻灯片里。当我观察那个结构，稍微缩小一点来看，也许有一个实际的“部件（parts）”节点什么的会很有用，对吧？在这个用例中，我让智能体（agent）来推断部件并从文档中提取它们，然后用它去元数据图中查找内容并查询 SQL，反之亦然。

<details>
<summary>Original English</summary>

**Presenter**: So, um the question is do we redefine the types of nodes um as well as the relationships and so is this a question of like how do you decide what the node labels should be? Um, yeah. And again, it's it's again, it's a data modeling question, right? Like there could be a situation where we're looking at the data model that we just went over. Um, well, it's not it's not here. It's in my uh it's in my last one. um when I look at the uh when I look at the shape um zoom out of that a little bit where it might be useful to have like an actual parts node or something right um here for this type of use case I'm letting the agent kind of infer parts and extract them from the documents and then use that to go find something from the metadata graph and query SQL or the or the other way around.

</details>

**Presenter**: 这对我很管用。所以，随着事物的发展，如果是在两年前，我可能会说你需要那个额外的节点。但现在看来，智能体似乎已经足够聪明了，也许你不必每次都这么做了。但在某些用例中，比如我们在生命科学领域看到的，存在着关于不同类型分子、药物等非常具体的本体论（ontologies），你真的需要在图结构中表示出这些内容，否则你的推理就没有意义。所以我很不想说“这取决于具体的用例”，我不想成为总是给这种回答的人，但在某种意义上确实如此。好的。噢，好的。让我继续往下讲，因为我们的课程进度刚过一半，后面还有很多内容要讲。

<details>
<summary>Original English</summary>

**Presenter**: Um, and that works for me. So, you know, it's still as as things evolved, like two years ago, I probably would have said you would need that like additional node. Now, it seems like agents are smart enough where maybe you don't all the time anymore. Um and but for some use cases, you know, especially like we see this in life sciences for example, where there's these really specific ontologies around, you know, different types of molecules and medications and things and you you really do need that represented in the graph or else it just your inference isn't going to make sense. So I hate to say it depends on use case. I don't want to be that person, but it it sort of does in a sense. All right. Um, oh, okay. Yeah, let me let me move on only because we're a little bit over halfway through and I have some more course to to get through here.

</details>

### 构建全文搜索索引与过滤

**Presenter**: 现在，让我们进入... 刚才那些内容我们都讲过了。哦，对了。我们需要构建我们的搜索查询。类似于我们刚刚做过的，也回应那边那位先生提出的问题，我们希望能够构建某种搜索来辅助增强。所以，这个搜索文件会简单得多。基本上，我只会使用一个 Lucene 风格的索引。而我这里不会使用向量搜索。Neo4j 本身有一个 Lucene 全文搜索索引。你们在这里可以看到，它基本上做了同样的事情，我有一个需要填充的参数绑定，它会使用一个 Cypher 技能来完成。在它运行的同时，你们可以编辑它... 我们不妨等它运行完。好了，它马上就要完成了。

<details>
<summary>Original English</summary>

**Presenter**: So, um, let's go to So, we went over all of this stuff. Um, oh yes. So, we need to build our uh search query. So, similar to what we just did and to the the question that the gentleman had over here, uh we want to be able to um we want to be able to build um some sort of search as well to help augment this. So, um this is going to be much more simple, this search uh file. Um basically, I'm just going to use a lucine style index. _ A, and I I'm not going to use vector search here. It's the Neo Forj itself has um a lucine full text search index, but and I'm going to do and if you see here, it's basically doing the same thing where I have the uh this this wire that it has to fill in. Um, and it's going to use a cipher skill to do that. While it's it's running there, you're allowed to edit. Um, we might as well wait till it's done. All right, it's going to finish up.

</details>

**Presenter**: 基本上，它的工作原理是调用全文索引。它在文档和部分节点上进行索引。所以每个包含文本的节点都会被索引，像文件夹我们就不会放进这个 Lucene 索引。然后它会给你一个评分。并且因为我们将所有内容都以那些 URI 格式存储，我们还可以通过子树（subtree）来限定范围，基本上使用“starts with”（以...开头）的过滤器。因此，如果我回到这个文件，看这个查询的运行方式，我有一个 WHERE 语句。

<details>
<summary>Original English</summary>

**Presenter**: So, basically, uh, if you see here, it's the way this works is you call the full text index. Um, it's indexed on the document and the section nodes. Uh, so every node that has text in it, like we don't put folders through through this lucine index. Um, and then it will give you a score. Um and then because we have everything in those URI format um we can also scope it by subtree um basically with like a starts with filter. Uh so if I was to go back into this uh file um and I looked at the way that this query run I have this wear statement.

</details>

**Presenter**: 我主要将它作为后置过滤器应用，也就是说我先执行全文搜索。然后，我通过 URI 对其进行过滤。所以我可以说“只在手册的这一部分下搜索”。这只是通过那些层级化的 URI 帮助我稍微优化一下搜索结果。我所做的另一件事是，因为在我的研究岗位上，我使用这么多不同的 AI 模型和不同的平台，你可能想象不到，但在向量检索方面要去选择和配置以适应六个不同供应商，其实是挺困难的。所以我经常使用的做法是“语义扩展（semantic expansion）”。

<details>
<summary>Original English</summary>

**Presenter**: Um, so I'm applying this as a post filter basically where I'm doing the full text search first. Um, and then I am filtering it by the URI. So I can say like only search under like this section of the manuals basically. Um, so it just helps me refine my my search a little bit with those hierarchical URIs. Uh, and the other thing that I do, um, and and I do this because I work like in in the the research role that I have, I work with so many different AI models and on so many different platforms. Like you wouldn't think about it, but like choosing like and wiring like options to be like work with like six different vendors for vectors is kind of tough. So what I often do for this is I'll use something called semantic expansion.

</details>

**Presenter**: 基本上它的作用就是指示 AI 模型说：“嘿，运用你的世界知识，如果有人询问‘引擎抖动’（engine shuttering），那可能也是‘缺火’（misfire）或者其他原因。”而且因为这是一个 Lucene 索引，我可以这样做。比如，我可以说“缺火或者怠速不稳（misfire or rough idle）”，它就会搜索其中任何一个词。如果我回到我的 bash 脚本并运行它，现在那个占位符已经被填好了，你会看到它会给出文档以及针对不同结果的评分。

<details>
<summary>Original English</summary>

**Presenter**: Um and basically what it does is it it instructs the AI model to say hey like use your world knowledge if someone asks for you know an engine shuttering that it might be a misfire or something else too. So it and because this is a lucine index um I can do that. So for example right I can say like misfire or rough idle and it will search for either of those. Um, if I go back to my bash script and I run that now that the uh thing's filled it in and then you'll see it'll give me my uh documents with with the scoring for for the different ones.

</details>

**Presenter**: 就像我之前说的，我也可以在特定范围内搜索召回信息。所以我可以仅在“召回（recall）”子文件夹库中搜索“线圈（coils）”。这就是这个想法的核心。你可以看到它仍然在利用那种层级包含结构，即那个树形结构，但是它是通过 URI ID 结构来实现的，这样它就不必做太多的图遍历。它只是简单地将结果向下过滤到子层级的事物。好的，太棒了。关于这里，大家还有什么简短的问题吗？

<details>
<summary>Original English</summary>

**Presenter**: And it I can also search as I was saying before under recall. So I can search for coils under just the recall uh subfolder library. So that would be the idea here. Um, so you can see it's still leveraging uh that hierarchical containment shape, the tree, um, but it's doing it through the URI um, ID structure so that it doesn't have to do as much graph reversal. It just sort of filters down to to things underneath. Um, all righty. Awesome. Um, are there any quick questions just around the

</details>

<!-- chunk 8/12 -->

### Lucene Search Query 演示与问答

**Speaker**: 刚才说到搜索那部分是吧？关于 Lucene 搜索。我们这边有一个问题。

<details>
<summary>Original English</summary>

**Speaker**: search piece there? The lucine search. We have one question over here.

</details>

**Audience Member 1**: 是的。问题是，我们刚刚把文档加载到了 Lucene 中，然后我们要在不同的部分（相应的合适部分）下面进行搜索。

<details>
<summary>Original English</summary>

**Audience Member 1**: Yeah. So the question is we just loaded the documents into the into lucine and then we're searching underneath different sections appropriate sections.

</details>

**Speaker**: 对。所以，基本上如果我们实际看一看我们正在运行的这个查询，可能会更容易理解。那么这就是——我把它放大一点。这就是那个 Cypher 查询，我会在这里空出一行，这样你们能看得更清楚。我们有一个已经设置好的 Lucene 索引，我们在加载图数据（graph）的时候就设置好了。我们在文档（document）节点和部分（section）节点上设置了它。所以，每次我调用这个 `index full text query nodes` 时，它就会命中这个名为 `content search` 的索引，然后这个 `lucine` 参数就是我用那个脚本传入的任何内容。这就完成了我们的初步过滤，把范围缩小到一堆文档和部分，因为我们将每个节点的 ID 都构建为了分层结构的 URI。如果我知道我只想在召回通知（recall notices）下进行搜索，我可以把那个 URI 传给它，它就会说，只返回那些 URI 以该内容开头的节点。所以，如果这能说得通的话，它是在之后应用那个后置过滤器。

<details>
<summary>Original English</summary>

**Speaker**: Yeah. So basically if it might make more sense if we actually took a look at the the query that we're running here. So here's the I'll make it this big. Um so here's here's the cipher query and I'll I'll create a space here so you can kind of see it better. So we have a lucine index that we've set and we set it when we loaded the graph. We set it on the document and the section nodes. So every time that I call this index full text query nodes, it's going to hit the name of the index which is content search and then this parameter lucine is whatever I've fed it in with that script. And so that's going to do our initial filter to just a bunch of documents and sections because we've structured our IDs for every node as a URI that's hierarchical. If I know that I only want to search underneath recall notices, I can hand it that URI and it will say only nodes whose URI starts with that thing. So it's applying that post filter afterwards if that makes sense.

</details>

**Audience Member 1**: 好的。对。

<details>
<summary>Original English</summary>

**Audience Member 1**: >> Yeah. Yep.

</details>

**Speaker**: 你有一个问题。

<details>
<summary>Original English</summary>

**Speaker**: You have a question.

</details>

**Audience Member 2**: 问题是，假设你已经有了一个图（graph），并且你还没有创建你的 Lucene 索引，你能不能提示 Claude Code 让它基本上帮你完成这个操作？

<details>
<summary>Original English</summary>

**Audience Member 2**: So the question is if say you already have a graph and you haven't created your lucine index yet, could you prompt claude code to basically do this for you?

</details>

**Speaker**: 嗯，老实说，我觉得可以。我最初在做这个课程的时候，可能就是那么做的。我可能真的让 Claude 去做过。我记不清了，因为我已经用几种不同的方式重建过这个项目了。不过，我认为答案是肯定的，尽管具体效果可能取决于你的数据（your mileage may vary）。很多时候，当你设置一个 Lucene 索引时，特别是在 Neo4j 里面，它非常灵活。也就是说，你可以把它设置在一个节点或多个节点上，也可以设置在一个节点上的多个属性，或者多个节点之间的多个属性上。所以，你知道，这有很多选项。当你要求一个 AI 模型来做这件事时，这种灵活性也可能成为一个小小的软肋（Achilles heel），因为它可能不理解所有这些不同的选项。但总的来说，是的，你可以使用代理编码（agentic coding）来帮你把它组合起来。

<details>
<summary>Original English</summary>

**Speaker**: Um so I I think yes to be honest I might have done that with this course initially. I might have actually had Claude do it. I can't remember because I' I've rebuilt this in in a in a few different ways. Um, but I think the answer to that is yes, your mileage may vary depending on your data. A lot of times with when you set up a lucine index too, it's like especially it's very flexible inside of Neo forj. So it's like you can set it up on top of one node or multiple nodes, multiple properties on one node, multiple properties between multiple nodes. So, you know, there there's a lot that flexibility can also be a little bit of an Achilles heel too when you ask an AI model to do because it might not understand, you know, all those various options. But in general, yes, you you can have um you can use agentic coding to to help put this together for you.

</details>

### 文档命名与知识库管理

**Audience Member 3**: 嗯，是的，中间这位。所以问题是，对于智能体（agent）来说，文档命名的准确性对它有效遍历文档有多重要？

<details>
<summary>Original English</summary>

**Audience Member 3**: >> Um yes, in the middle there So the question is how important is it that the name of the documents be accurate for the agent to traverse it effectively?

</details>

**Speaker**: 嗯，我认为它会很重要的。是的。如果你的文档命名得不是很好，并且你有那个大纲视图（outline view），那么智能体在尝试遍历时，就没有多少可以依据的信息了。所以，它可能会误解某个文档的含义，对吧？这就是为什么在它旁边进行搜索增强（search augmentation）是有用的，因为它实际可以查看文档内部。关于这些事情，我所看到的情况是——因为我自己实际上也把这个用于我自己的知识库管理。我有一个自己的开源库，里面就使用了这些工具。最大的问题是当你的文档过时或发生漂移（drifted）的时候，对吧？

所以我想过，也许我们需要添加一个类似“最后更新日期”之类的东西，或者……一个文档是否应该是权威的，对吧？而且，文档命名确实很重要。另外，链接的命名也很重要。所以如果你有这样的链接……如果你有一些链接，它们没有像……我忘了它叫什么了，但在 Obsidian 里面，你可以给它命名，你可以给它提供一个……呃，同义词之类的东西，对吧？当你在那里对链接进行那样命名时，如果它存在的话，那可能会非常有帮助。因为那样它就相当于在说，“哦，我确切地知道为什么我要链接到另一个东西”。所以，这就是有时候如果你没有那个信息的话，在摄取（ingest）过程中使用一个语言模型可能会有好处的地方。是的，这边请说。

<details>
<summary>Original English</summary>

**Speaker**: Um, >> I think I think it would. Yeah. If if your documents weren't named very well and you had that outline view, then the agent doesn't have as much to go off of when it's trying to traverse. So, it might misinterpret what a document means, right? Um that's why having the search augmentation alongside of it is useful because it can actually look in the document. Um with these things what I've seen because I use this actually for my own knowledgebased management. I have my own open source library that I use which has these tools. Um the biggest problem is when you have documents that are outdated or drifted, right? Um, so I've thought about, well, maybe we need to add like a last updated date or something or like um whether or not a document should be authoritative, right? Um, and the document naming is actually important. Um, and link naming as well is important too. Um, so if you're if you have links that um don't have like um I forget what it's called, but like in Obsidian, you can sort of you can name the you can give it um uh a synonym or something, right? where you name the link like that can be very helpful if that's there right because then it's like oh I know exactly why I'm linking out to this other thing um so that's when sometimes using like a language model inside of the ingest if you don't have that could could be beneficial um yes over here

</details>

### 数据更新与图的部分同步

**Audience Member 4**: 那么当有一个新文档进来的时候……

<details>
<summary>Original English</summary>

**Audience Member 4**: so when you get a new document that comes in um

</details>

**Speaker**: 所以，这件事的好处在于它是一个完全幂等（idempotent）的加载过程，这意味着，假设你整个图明天都不见了，只要你的文档没有变，如果你去加载它们，你还会得到完全相同的图。所以最坏的情况是，是的，你将不得不重新加载整个图，但这个加载过程是确定性的（deterministic）。现在，你也可以——我在我其他的一些工作中也尝试过这个——你可以说：“哦，好吧，我只有一个文档改变了，我只想更新那一个节点。” 你只需要意识到它会链接到其他东西这个事实。所以就变成了，如果你更新了这边的这个文档，如果你改了它的名字，那么你必须考虑，你其他的文档是否也更新了对那个文档的 URL 引用？所以这里有一些你需要去处理的边缘情况（edge cases）。但是，如果你能够做到这一点，也许我们之后可以谈谈，我可以向你展示一下。你可以只给树的这一部分进行添加，并清理树的那一部分，这样你就可以进行部分同步（partial syncing）。是的。好的。后面那位的举手了吗？你只是在挠头。好吧。那么我猜这边还有一个问题。

<details>
<summary>Original English</summary>

**Speaker**: so the nice thing about this is that it's all an item potent load which means that say your entire graph went away tomorrow as long as your documents didn't change if you load them you'll get the same graph so worst case scenario yes you would have to reload the whole graph but this load is deterministic now you can also and I've experimented with this again in some of my other um work is you can say oh well I have one document that changed and I just want to update that one node. You just have to be aware of the fact that it links to other things. So it's like well if you got if you changed if you updated this document over here um if you changed its name then you have to you know did your other documents also update like the URL reference to that document. So there's little edge cases there that you have to work through. But um if you're able to do that maybe we can talk after and I can show you. You can have like just add to like this part of the tree and clean up this part of the tree so you can do like partial sinking. Yep. All righty. Um is do you have your hand up back there? You're just scratching your head. All right. Um then I guess we have one question here.

</details>

**Audience Member 5**: 对吧？像页面索引（page index）之类的东西，其后的默认操作应该就是搜索（search）了。

<details>
<summary>Original English</summary>

**Audience Member 5**: right? the default after something like page index would be search.

</details>

**Speaker**: 是的。对。所以我认为这个问题基本上是说……就智能体（agent）推理它的方式而言，它会首先调用大纲（outline），然后再使用像搜索（search）那样的功能。

<details>
<summary>Original English</summary>

**Speaker**: >> Yeah. Yeah. So I think the question is the question basically like um for the way that the agent reasons about it that it would call outline first to then use like search.

</details>

**Audience Member 5**: 是的。

<details>
<summary>Original English</summary>

**Audience Member 5**: Yeah.

</details>

**Speaker**: 是的。它可以按那种方式工作。它也可以以某种方式工作，也就是它首先进行搜索以找到相关的文档，然后再尝试去寻找那个文档链接到的所有内容。在那种情况下，它就是完全相反的方式了。

<details>
<summary>Original English</summary>

**Speaker**: Yeah. It it could work that way. It could work some way where it will search first to find a relevant document and then try to find everything it links to. In which case, it would be the opposite way around.

</details>

### 主题发现与图社区检测

**Speaker**: 好的，太棒了。让我们继续往下讲，以确保我们有时间回答大家所有的问题。那么，我们在这里做什么呢？这只是要求进行更多的全文搜索（full text search）。因为现在已经是 39 分了，我们为什么不……我觉得我们实际上已经有效地讲过了这里的很多材料。这些内容中，有一部分是被设计为让你之后回过头来看时，能够过度记录（overdocuments）我所讲的内容的。因此，这些步骤以及一些可选的练习将帮助你更好地理解 Cypher。并帮助你确切地了解所有的部分是如何组合在一起的。但鉴于我们目前的进度，我不如直接跳到我们的主题（themes）部分。所以我打算跳过这里的可选实践课程，我将直接进入主题。

这将是我们今天的第三个、也是最后一个形式。这个想法是，如果你运行它——这个 Cypher 查询基本上是加载一个图数据，而我只关注文档之间的“链接到（links to）”关系。所以当你有一些包含大量相互链接的文档时，考虑使用图总是一件好事。因为这个结构……基本上它在这里的意思是，对吧，我们有这些手册（manuals）、这些召回通知（recalls）以及这些简报（bulletins），它们彼此链接和引用。因此，你可以看到，例如这个指南（guide）——这是一本手册——被所有这些不同的维修程序所链接。

如果你拉远视角（zoom out），结果会发生什么呢？你会得到各种自然形成的聚类（clusters）。这种情况在那些 Karpathy 风格的知识库中也经常发生，你会看到各种概念会自然而然地开始组合在一起，而图可以帮助你将这些主题（themes）、这些你以前实际上不知道其存在的东西浮现出来。所以我们要使用一种叫做“社区检测（community detection）”的东西。请举手表决，这个房间里有多少人熟悉什么是图数据科学（graph data science）？嗯，是的。好的。所以，不是太多人。有多少人知道图中的社区检测是什么？好的。所以，我们有几位了解。

那么，社区检测的理念就在于，如果我有这个图——并且你可以看到，如果我拉远视角，尤其是如果你在本地运行它，你可以看到存在这些自然的、像小聚类一样的节点群，它们之间高度互联。因此，我们的想法是：“好吧，如果我们能够尝试给这些聚类贴上标签，使得在聚类内的事物都是高度互联的，会怎么样呢？” 就像这一小团节点变成了一个聚类，然后这一团变成了一个聚类，还有下面这个也是。并且如果我们可以做到这一点，我们就能……

<details>
<summary>Original English</summary>

**Speaker**: All right, awesome. Let's um let's move on here then to make sure that we have time for all of our questions. Um so what are we doing here? This is just more asking more full text search. Why don't we because we're at 39. Well, I think we already effectively went over a lot of this material here. Um, some of this is designed so that if you come back to it later, it kind of overdocuments what I'm talking about. So these steps and some of the optional work will help you understand cipher a little bit better. Um and kind of exactly how exactly how all the pieces fit together. But given given the pace that we're moving at, why don't I go ahead and jump over to our um theme section. So I'm going to skip over the optional practice lesson here and I'm going to go right into into themes. So this is going to be our third and uh last shape of today. The the idea with this is if you run so this cipher query is basically going to be loading a graph and I'm just looking at that links to relationship between the documents. So when you have documents that have a lot of interlinking um it's always nice to think about using a graph because this structure basically what it's saying here is right we have these manuals these recalls and these bulletins and they link and they refer to each other. Um, so you can see like this, you know, um, uh, this this this guide here that's a um that's a manual is being linked to by all of these different repair procedures. And if if you zoom out, what ends up happening is you'll get natural clusters of things. And this also happens a lot like in these kaparthy style like knowledge bases where you'll see that like concepts will naturally start grouping together and a graph can help you surface those themes those things that you didn't actually know existed before. And so we're going to use something called lien community detection. By a show of hands, how many people in this room are familiar with what graph data science is? Well, yes. Okay. So, so not too many of you. Do how many people know what community detection in a graph is? Okay. So, we we have some of you. So, so community detection is this idea where right if if I have this graph um and you can kind of see if I zoom out if you if especially if you're running it locally you can see that there's these like natural little like clusters right of nodes that are highly interlin together and so the idea is like well what if we can like try to label these clusters such that within a cluster things are highly interconnected so like this little globule of nodes becomes a cluster cluster, then this globule becomes a cluster and this one down here. Um, and and if if we can do that, we can

</details>

<!-- chunk 9/12 -->

### Global Scale Data and Leiden Algorithm

**Speaker A**: 开始很好地理解我们在全球范围内的数据。所以，这也像最初的微软 Graph RAG 理念，关于全局搜索与局部搜索的对比，对吧？我们在这里做的事情非常相似，但我们正在以一种非常轻量级的方式进行，我们并没有真正做任何大语言模型（LLM）的提取。我们完全是基于文档本身的结构来做的。

<details>
<summary>Original English</summary>

**Speaker A**: start understanding our data at a global scale really well. So, this is like that initial like Microsoft graph rag idea too of like of global versus local search, right? We're doing something very similar here, but we're doing it in a very lightweight way where we're not really doing any LLM extraction. We're just going off of literally the structure of the documents.

</details>

**Speaker A**: 我们将用于该标记的算法称为 Leiden，它类似于 Louvain，如果你谈论社区发现，Louvain 经常会被提及。我几乎把 Leiden 看作是它的下一步。它在运行方式上稍微更高效一些。并且它使用了 Neo4j 的图数据科学（Graph Data Science）库。

<details>
<summary>Original English</summary>

**Speaker A**: The algorithm that we're going to use for that labeling is called Leiden, which is similar to Louane, which if you talk about community detection, Luane will come up a lot. Leiden is I almost see it as like a um the sort of next step. It's a little bit more efficient um in in the way that it runs. And um it it's using Neo Forj's graph data science library.

</details>

**Speaker A**: 所以基本上我们要做的，或者说我们为了让它具有很高性能所做的，就是除了拥有数据库之外，我们还有另一个投影（projection），我们将图的一部分放入内存中，然后在它的基础上运行这些高并发算法。这样一来，如果你有一个包含数百万或数十亿个节点的图，我们就可以开始执行这种聚类，然后基本上识别出不同的相互连接的社区和这些集群。

<details>
<summary>Original English</summary>

**Speaker A**: So basically what we have to do or what what we do to make it very performant is in addition to just having the database we have this other um projection where we'll take a part of the graph into memory um and then we'll run these high concurrency algorithms on top of that so that if you have a graph that has say millions or billions of nodes we can start performing this clustering and then identifying um basically the different interconnected communities. and um these clusters.

</details>

### Document Themes and Conductance Metric

**Speaker A**: 如果我继续往下看，基本上我们要在这里采用的格式，即我们要向我们的智能体展示的视图，就是这个。因为这是一个滑动窗口，所以看起来有点困难，但基本上我们将拥有我们称之为“主题”（themes）的东西。这些主题将会是这些文档的桶（buckets）。我们将利用电导率（conductance）这一指标，来感知它们的相互链接是紧密还是松散。这基本是一个衡量集群内节点互连程度与它们在集群外部连接程度对比的指标。所以我们可以说某些东西是紧密互连的，或者是松散互连的。

<details>
<summary>Original English</summary>

**Speaker A**: If I um keep going down, basically the the format that we're going to go for here, sort of the view that we're going to show our agent is this one. And so it's a little bit hard to see because it's a sliding window, but basically we'll have what are what we're calling themes. And these themes are going to be these buckets of documents. we'll have a sense of how tightly or loosely they're interlin using um this conduance metric. It's basically like going to be this metric around like how interconnected the nodes inside cluster are versus how much they um are connected outside of the cluster. So we can say something's tightly interlin or loosely interlin.

</details>

**Speaker A**: 我们将使用链接上的标签作为热门共享目标，并且我们会讨论链接最多的文档，即它们每个内部具有最高中心性的文档。因此，我们最终得到的结果，在没有任何人工智能或语言模型进行任何类型标记或标注的情况下，仅仅通过文档结构，我们就可以看出第一个是关于 BCM、总线（bus）以及所有这些类似的东西。然后如果我往下走，比如下一个集群将是关于刹车、转子垫（rotor pads）和液压管路的。所以全是刹车相关的东西。所以你最终会得到这些非常自然出现的集群。

<details>
<summary>Original English</summary>

**Speaker A**: um we'll use the labels on the links as the top shared targets and we will um talk about the most linked docs and so so the highest centrality docs inside each of them and so what we end up with without any sort of um tagging or labeling by AI or a language model um is just simply from the document structure we can tell that this first one um is about you know um BCM um and and bus and all these sorts of things. And then if if I go down like this next cluster is going to be about brakes um and rotor pads and um hydraulic lines. So it's all braking stuff. So you end up with these very natural sort of clusters that come up.

</details>

**Speaker A**: 因此，这对于整个数据资产级别的问题非常有用，因为你可以在你的数据中开始理解所有事物是如何分组和聚集在一起的。所以我们构建它的方式类似于我们之前所做的，我们有那个脚本，我们也有我们的规范（spec）。这里折叠了这些部分，这里稍微讨论了一下，我想给我们留出最后半个小时来过一遍最后的问题。所以我将稍微加速一下，但基本上当我们创建这个投影时，我就直接去复制这个东西。

<details>
<summary>Original English</summary>

**Speaker A**: And so this is very useful from sort of a whole estate wide question because you can start to understand in your data kind of how everything kind of groups and clusters together. Uh and so the way that we build that is similar to what we were doing before where we have that script and we have our um our spec as well. Um, so collapsing the sections and it talks a little bit here and I I kind of want to give us the last half an hour to go through the final questions. So I'll speedrun this a little bit, but basically when we create this projection and I'll just go ahead and and copy this thing.

</details>

### Running the Projection Script

**Speaker A**: 也许我先处理这个脚本。就像我们之前做的那样，在这里面，如果我查看我的 themes.py 文件，我已经为这个投影连接好了那部分，就是我们把图提取到内存中的那一部分。这里实际的 Leiden 算法，我只是在调用图数据科学（Graph Data Science）库中的算法。理论上你可以让智能体来编写所有这些代码，但我自己来做这一个。哦，这不太好。我希望能确保我复制了正确的内容。所以，和之前类似，我们有我们的……确保我刚给它的是对的东西。是的。所以，我们告诉它使用 Cypher 技能和 GDS 技能来把这些组合起来。如果你进入我们的文档，你会看到主题格式，它会赋予它我们想要的形状等所有东西。它会告诉我们想要怎样格式化所有的标题和内容。所以我们将继续，让它为我创建那个。

<details>
<summary>Original English</summary>

**Speaker A**: Maybe I'll I'll do this script thing first. So like we did before, um, inside of here, uh, if I look inside of my themes.py file I I have this wire for this for the projection that piece where we take the graph and put it into memory. Um the actual liiden algorithm here I'm just calling it with that graph data science library. Um so in theory you can you can kind of agent code all of these. Um but I'll just do this one. Um oh that's not good. I want to be able to make sure I copy the right thing. So, similar to before, um, we have our, um, sure that the right thing that I just gave it. Yeah. So, we're telling it to use a cipher skill and the GDS skill to put this together. If you went inside of our docs, you have the uh, theme format one, which will give it the the shape that we want and everything. Um, and it will tell us kind of how we want all the headers and things to be formatted. Um, and so we'll go ahead and um create that create that for me.

</details>

**Speaker A**: 在它创建的时候，我稍微谈谈这个投影。我们进行了一些图操作，以便有效地将其引入投影中。基本上我们会在 URI 上折叠这些关系，这样如果我们有相互链接的各个部分，比如一个文档的某一部分链接到另一个子部分，我们就直接将所有这些关系聚合到文档层级。这为我们的文档如何链接在一起创造了一种更清晰的解释，而不是仅仅保留所有单独的部分，通过这种方式我们也能更容易地提取出社区。

<details>
<summary>Original English</summary>

**Speaker A**: And while it's creating that, I'll talk a little bit about the projection. So there's some graph manipulation that we do to bring it efficiently into a projection. Um, basically we collapse the relationships on the URI so that the if we have sections that interlink with each other like one section of a doc interlinks to another subsection, we just aggregate that all to the document level. Um, and that creates kind of a cleaner interpretation to how our documents link together rather than just all our individual sections and we can get out the communities um, easier that way as well.

</details>

**Speaker A**: 好了。所以，看起来进展顺利。是的。好的。它已经继续为我们创建了那个。当我们得到结果后，我可以直接复制它刚刚帮我创建的脚本，并在我的终端中运行它。让我新建一个终端。所以，我可以直接调用我们刚刚编辑的那个主题脚本。然后它将执行社区发现。你会在这里看到我将得到那个视图。所以我有了我的……你可以看到比如这个关于电路的，我把所有不同的文档都分组在了一起，我现在对我的文档涉及的车辆的所有不同领域有了更深入的了解。

<details>
<summary>Original English</summary>

**Speaker A**: All righty. So, that looks like it's coming along. Yes. Okay. So, it went ahead and created that for us. Um, and then once we get that back, uh, I can go ahead and copy the script that it just helped me create and I can run that inside of my terminal. Let me just make a new terminal. So, I can go ahead and and call that theme script that we just edited. And then it will do that community detection. And you'll see here that I'll get that view. Um so I have my you can see like the this you know circuit you know one I have all my different uh documents that are that are grouped together and I kind of understand now um all the different areas of the vehicles that that my documents go over.

</details>

### Tuning Hyperparameters and Application

**Speaker A**: 你可以为它提供其他的参数。举个例子，我们有一个 Gamma 参数，它基本上会告诉算法将所有内容拆分成多少份。这是我们暴露出来的一个参数。如果你去查看图数据科学的文档，还有很多其他参数。比如我在这里运行它得到了 13 个分组。如果我尝试将其变得更精细，将 Gamma 设置为 2，默认是 1，它会给我，我认为在这种情况下是 14 个分组。所以它基本上将其拆分为更多的组。因为很多这些社区发现算法也是层级化的，所以你可以选择你想要的粒度级别。基本上，随着工作的推进和你对自己语料库理解的加深，你可能想要调整其中的一些超参数。这给了我们 14 个不同的主题。

<details>
<summary>Original English</summary>

**Speaker A**: Um there's other parameters that you can feed this. Um so for example we have a gamma parameter and basically what that will do is uh basically tells it kind of um how how much to split everything into. So it's one parameter that we're exposing. If you went to the graph data science documentation there's many others. Um but like I got 13 groups running it here. If I if I try to make it more refined with gamma equal to two. So it's one by default. it will give me I think in this case 14. Um so it basically splits it up into more groups. A lot of these community detection algorithms also because they're hierarchical you can choose to sort of you can choose your level of granularity that you want. Basically um as you go along and you start to understand your corpus better, you may want to tune some of these hyperparameters. Um and this gave us 14 different themes.

</details>

**Speaker A**: 让我们看看这里有什么。是的。它实际上从来没有真正为一个主题命名，这也是它的重点所在。所以你得到的一切都是直接来自文档的。如果我看看这里的主题、链接的名称、读取的热门文件的名称，所有这些东西都直接来源于数据。然后由于你获取了 URI，即其中一些文档的 ID，你就可以开始执行这样的操作：你可以回到大纲形状或搜索形状，然后你可以在所有这些内容下方进行搜索。所以，这赋予了智能体在这种多个工具之间跳转的能力。

<details>
<summary>Original English</summary>

**Speaker A**: Um, let's see what we have here. Yeah. And it never really names a theme is sort of the point of this. So like everything that you get um is just directly from the document. If I was to look at like the the theme here, the names of the links, the the names of the the top files that were read, all of those things are just directly from the data. And then because you get the URIs, the IDs of some of these documents, you can start doing the thing where you can go back to the outline shape or the search shape and you can like search underneath all of these things. So, it gives the agent the ability to kind of jump between multiple tools like this.

</details>

**Speaker A**: 因此，这类功能对于处理这些数据资产级别的问题非常有用。比如这些问题：问题集中在哪里？哪里缺乏文档？为了添加更多数据，刚引入的关于某种其他不同主题的新文档可能属于哪里？好了。这就到了主题部分的结尾，我们大约还剩 27 分钟。大家对于这个主题算法还有什么快速的问题吗？

<details>
<summary>Original English</summary>

**Speaker A**: Um and so this the these sorts of things are good for these estate level questions. So things like where are issues concentrated? Where's documentation thing thin? Where does new documentation possibly belong on some other different type of subject that just came in for adding more data. Um all righty. So that brings us to the end of themes and we have 27 minutes about left. Are there any questions around this themes uh algorithm that anyone has really quickly?

</details>

**Speaker B**: 啊，有的。

<details>
<summary>Original English</summary>

**Speaker B**: Uh yes.

</details>

**Speaker A**: 说吧。

<details>
<summary>Original English</summary>

**Speaker A**: >> Yep.

</details>

**Speaker A**: 是的。所以这是一个很好的问题，问题是，一旦你获得了这些主题，所有 Leiden 算法要做的就是为这些不同的组分配一个 ID 对吧，然后你在这之后做的事情就取决于你的选择了。而你的问题是，你只是从数据中提取并直接把它放在那里，还是说你随后会进行某种推理来给不同的组打上标签？在这里我们做的是前者。我们只是获取数据中的内容并将其展示给你。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. So that's a good question and the question is once you get the themes so all the line algorithm will do is assign an ID to these different groups right and then what you do after that is sort of your choice and your question is are you just sort of taking from the data and just putting that there or are you making some sort of inference afterward to label the different groups. Here we're doing the former. We're just taking what's in the data and we're just showing it to you.

</details>

**Speaker A**: 这样做的优势在于，每次我运行它时，只要数据保持不变，结果就会是相同的。如果数据发生变化，它也会随之改变以反映数据。所以，它非常稳定。它的缺点可能是，如果你文档中的链接以及正在被提取的标题之类的东西，因为……

<details>
<summary>Original English</summary>

**Speaker A**: Um, and the advantage of that is every time I run it, it'll be the same as long as the data stays the same. If the data changes, it will change to reflect the data. So, it's very stable. The disadvantage to it would be if your links in your documents um, and the titles and things that are being scooped up, because

</details>

<!-- chunk 10/12 -->

### Document and Link Metadata Limitations

**Speaker A**: 这实际上基本上只是在查看文档元数据和链接元数据。如果这些东西没有被很好地标记，那么这个视图可能一开始就不会提供太多信息。这就是为什么，你看，像微软提出的 GraphRAG 方法，他们做了大量繁重的实体提取，因为这会提供一种……然后他们会做层级摘要，对吧？所以在他们得到 Leiden 社区（也就是他们使用的相同算法）之后，他们会在每个主题之上做一个由 LLM 驱动的摘要。这确实是可行的。但这显然需要花费更多资金，速度更慢，而且如果你运行两次，它可能不会返回相同的结果。所以每种方法之间都存在权衡。我向你们展示的是一种更轻量级、更简单的方法。只是因为它更快，而且如果你刚刚开始接触这个，从这里开始可能会更容易。我们还有时间，也许可以再提一两个问题。好的。

<details>
<summary>Original English</summary>

**Speaker A**: This is really only looking basically at document metadata and link metadata. Um, if those things aren't already well labeled, this view might not be super informative right off the bat. That's why you have, you know, with like the the GraphRAG methods that Microsoft came up with, they do a lot of heavy entity extraction because then what that will give is this sort of—and they'll do um hierarchical level summaries, right? So after they get the Leiden community, which is the same algorithm that they use, they'll do a summary that'll be LLM driven on top of each theme. Um, so that's possible to do. Um, but then obviously it costs more money, it's slower, and if you run it twice, it might not return the same thing. So there's trade-offs between uh each way of doing it. I'm showing you the sort of lighter way of doing it and the easier way. Um, just because it's faster and if you're just getting started with this, it might be easier to to start there. Um, may we have time for maybe one, maybe two more questions. Um, yes.

</details>

**Speaker B**: 时间序列数据（Temporal data）。

<details>
<summary>Original English</summary>

**Speaker B**: Temporal data.

</details>

**Speaker A**: 是的。我是说，我见过客户……基本上每次都是这样，因为 Leiden 的工作方式是，它确实是这样一种算法，它会把一切都吸收到一个投影中。它会创建它的标签，然后它会平息下来，然后就会消失。所以，如果你的数据在不断更新，你可以重新创建你的 ID，而且你可以拥有类似不同主题 ID 的时间序列，例如。然后如果你愿意，你可以在它们存在时的快照处创建摘要，或者你可以看到它们随着时间的推移是如何演变的。但这确实是一个非常常见的用例，很多人实际上甚至在 AI 之前就会用到这个，他们会将其用于欺诈检测等领域。比如查看信用卡拒付欺诈，或者一些反洗钱类的工作，去查看集群。为了做到这一点，他们必须在时间维度上进行操作，比如他们必须持续运行它，以观察事物随时间的变化，然后预测未来。对。所以它们也用于那些场景。是的。好了。也许再来一个问题，然后我就得继续了。好的。可以。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I mean, um, I've seen customers, you know, basically every time because because the way Leiden works is it's it really is this algorithm that where it will suck everything into a projection. It will create its labels and it'll it'll die down and then it will go away. So if your data is being updated constantly, um, you can recreate your IDs, um, and you can have almost like a time series of of different theme IDs, for example. Um, and then you can, if you want, create summaries sort of at the snapshot of when they existed or you can see how they evolved over time. Um, but it's a very common use case. A lot of people will actually use this even before AI. They'll use this for things like um fraud detection, so like looking at um like credit chargeback fraud or like some of these other like um anti-money laundering type of stuff to look at clusters. And for that they'll have to do it temporally, like they have to keep running it, um, to kind of see how things change over time and then predict the future. Right. So they're used in those scenarios too. Yep. All right. One more maybe and then I'm gonna have to move on. All right. I Okay. Yes.

</details>

### Managing Large Graphs for AI Models

**Speaker C**: 问题是，如果你有一个非常大的图，你如何将发送给 AI 模型的这个视图变得可控？

<details>
<summary>Original English</summary>

**Speaker C**: So the question is if you have a really big graph, how do you take this view that's being sent to the AI model and make it manageable?

</details>

**Speaker A**: 是的。所以对于这个视图，我认为它显示了大概 14 个主题。你可以设置一些截断值。比如，你可以说，对于小于 X 阈值的社区，你没必要突出显示它们。有时小社区非常重要，这就是为什么那个支撑着“紧密链接、松散链接”的电导（conductance）指标，你也可以把它作为一个截断值。所以，如果我没有理解错你的问题的话，这有点像是把信息量过滤下来，在较大的图上只把最重要的展示给 AI 模型。我理解得对吗？

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. Um, so for this view I think it's showing like 14 themes. So there are cutoffs that you can make. So for example, you can say like for communities that are smaller than X threshold, like you don't necessarily need to highlight them. Sometimes small communities are very important, which is why that conductance metric, which is powering that tightly interlinked loosely interlinked, you can also make that a cutoff. So if I'm interpreting your question correctly, it's sort of filtering down kind of the amount of information to what's most important to show the AI model on a larger graph. Do I understand that correctly?

</details>

**Speaker C**: （我的意思是）以确保节点上的关系是正确的。所以是的。

<details>
<summary>Original English</summary>

**Speaker C**: To make sure that the relationships on the nodes are correct. And um so yeah.

</details>

**Speaker A**: 是的。我的意思是，所以在这种场景下，我们实际上是在某种程度上信任（数据），我们基本上是对源数据信以为真，对吧？如果某个东西链接到一个文档，它就是链接到该文档，对吧？如果它错误地链接到一个文档，或者有一部分的格式不正确，我们不一定能发现。但是我想，像大纲形状这样的东西的一个好处是，你可以让你的智能体自动遍历它，而不需要你把它切成小块来查看，而且它可能会发现其中的一些问题，对吧？所以我想它确实为你提供了一种导航方式，让你能够让智能体去监督这个图，并理解格式错误的数据或一直存在问题的数据。但这是一个好问题。我不知道我们是否有完美的解决方案。清理和处理杂乱的数据一直都是个问题。是的。好了。我们继续往下进行，因为我只剩下 20 分钟了，而且我预计最后一个部分会是，这是内容最丰富的一个部分。所以希望我们有足够的时间来完成它，特别是因为 Claude 一直很慢。所以祈祷吧，因为这部分可能是对 Claude 使用最重的地方。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah. I mean, so in this scenario, we're really sort of trusting, we're taking the source data kind of at its word, right? If something links to a document, it links to the document, right? If it's erroneously linking to a document or there's a section that's malformatted, um, we wouldn't necessarily catch that. But I suppose a good thing about something like an outline shape is that you can have your agent traverse it um automatically without you necessarily seeing it in small pieces and it might be able to catch some of those things, right? Um so I suppose it does give you that navigation would give you a way to kind of have an agent supervise the graph and understand like malformed data or data that's been a problem. Um but it's a good question. I don't know if we have a perfect solution to it. It's cleaning and cleaning messy data has always been a, you know, a thing. Yep. All righty. Let's go ahead and and move on because I only have 20 minutes left and I anticipate this last uh section will be, this is the the meatiest one. So hopefully we'll have enough time to go through it especially because Claude has been slow. So cross your fingers um because this one is probably the heavier use of claude.

</details>

### Neo4j CLI and Custom Cypher Queries

**Speaker A**: 这里有一节是关于仅使用 Neo4j CLI 的，因为我们才讲了 20 分钟。我可能会在最后讲，我不会详细过一遍，但我会花几分钟谈谈它。Neo4j CLI 是一个命令行工具。所以我可以在命令行中运行它。所以比如在这里，如果我打开一个终端窗口，我可以把它复制进去，它会为我运行一个查询，而且它还有获取图模式（graph schema）的功能。这使我能够做的基本上是了解图中有什么，然后基于此编写查询。如果你有自己的智能体，在这种情况下，因为我们使用的是代码智能体，它可以访问 Neo4j CLI，这赋予了它进行图推理、读取模式然后执行灵活查询的能力。所以这非常有用，如果你遇到了一个你没有预料到的问题，而智能体需要在各种形态之间将信息拼接起来，对吧？它必须编写自己的自定义 Cypher 查询。它可以非常高效地完成。而且我已经看到了结合技能使用这个工具带来的很多改进。比我们之前经历过的文本到 Cypher（text-to-Cypher）体验要好得多，甚至比一年前或六个月前还要好。如果你要编写 Cypher，或者使用智能体进行任何文本到 Cypher 的操作，我强烈建议使用 Neo4j CLI。以及我们刚刚介绍的 Cypher 和 GDS 技能。考虑到这一点，我将继续进入我们的，在这种情况下的最后一个部分。如果你想在会后查看，它后面还有其他提供信息的部分。

<details>
<summary>Original English</summary>

**Speaker A**: So there is a section here around just using the Neo4j CLI because we're just 20 minutes in. Um, I'm probably end, I'm not going to go through it all the way but I'll talk about it for a couple minutes. The Neo4j CLI is a a CLI tool. So I can run it in the command line. So here for example, um, if I opened up a terminal window I can go ahead and copy it in and it will run a uh query for me and it also has the ability here to grab the graph schema. Um, and what that enables me to do is um basically understand what's in the graph and then write a query based on that. And if you have your agent, which in this case because we're using a coding agent it can access the Neo4j CLI, it gives it the ability to do this graph reasoning, read the schema and then do flexible queries. So this is very useful if you have a question that you didn't anticipate and the agent's sort of gluing things together between the shapes, right? It has to write its own custom Cypher query. It can do that very efficiently. Um, and I've seen a lot of improvements using this along with the skills. So much better than the text to Cypher experience that we've had like even as as soon as a year ago or six months ago. Um, if you are going to be writing Cypher or doing anything text to Cypher with an agent, I'd highly recommend using the Neo4j CLI. Um, as well as the Cypher and GDS skills that we were just going over. So, with that in mind, I'll go ahead and take it on to our, in this case, our last section. If you were to take this offline, there's other informational sections that come after it.

</details>

### Auto Repair Shop Use Case

**Speaker A**: 基本上我们要开始问一些问题。我们要问它的第一个问题，我将直接切入主题，因为其中很多文档我们之前已经看过了。如果你还记得一开始，我们有不同的角色，对吧？我们有所谓的“丹尼（Danny）”，即车间技师，对吧？他们可能会遇到这样的问题：嘿，对于这个具有我收到的特定故障码的 VIN（车辆识别码），我们在类似车辆上做了什么修复措施来解决这个问题？其背后的动机是，作为一个汽车修理厂，你想尽量减少返工率，这基本上是指客户不得不因为维修无效而重新返回的次数，对吧？因此，这些数据，尤其是在数据仓库端，将显示一些历史记录，结合有关实际零部件、召回和公告的文档。所以，我在这里所做的与之前那位先生提出的问题类似，我让它解释用于不同形态的步骤。你可以看到它正在加载汽车服务器技能（auto server skill）。这是我们这里有的技能，其中也包含我们一直在使用的所有脚本。所以，它同样可以访问大纲搜索（outline search）和主题脚本（theme script），以及运行 SQL（run SQL）和 MCP 服务器（MCP server）。这就是我们之前讨论过的那个技能。我已经为此提前写好了。如果你们愿意，可以阅读一下，但它基本上提供了一些关于如何访问数据仓库以及在命令界面中处理不同形态的一般指导。你们将在这里看到它会做什么。它会查找文档代码。它会进行全文搜索。它会在这里使用树形结构（tree shape）来查找交叉链接和原因。然后它会获取连接路径（join paths）。并且它实际上会对 VIN 进行查询。当它这样做了以后，它将返回基本上需要更换的零件编号。在这个案例中，有一个被修订过的旧点火线圈需要被替换。所以，如果你看一下，它首先进行了全文搜索，通过正确的代码在某种程度上对文档进行了定位（ground）。所以它查找了代码，以及缺火（misfire）或怠速不稳（rough idle）。它找到了热门匹配结果，也就是这个发动机——

<details>
<summary>Original English</summary>

**Speaker A**: Um but basically we're going to start asking um some questions. Uh the first question that we're going to ask it and I will jump right to it because a lot of this documentation we've already went over is if you remember from the beginning we had our different personas, right? We had sort of our our who we called our Danny, which is the floor technician, right? And they might have a question like, "Hey, for this VIN with this specific code that I'm getting, what fix, what have we done that has fixed this on similar vehicles?" Um, and the motivation behind this, right, and behind a lot of the data is as an auto repair shop, you want to minimize your um, comeback ratio, which is basically how many times a customer has to come back because, you know, the fix didn't work, right? Um, and so the data, especially on the warehouse side, will show um some of that history combined with the documentation on the actual parts and the recalls and the bulletins. So, what I've done here is similar to the gentleman's questions before, I uh I have it explain the steps that it used for the different shapes. You can see it's loading um the auto server skill. So that was the um the skill that we have here where we've also contains all of the scripts we've been working with. So the outline search and theme script it has access to as well as the run SQL and the MCP server. Um that was this skill that we were talking about before. So I've pre-written that for this. You can read it um if you like, but it basically gives it um some general guidance on how to access the warehouse and also deal with the different shapes in the command interface. And you'll see what it will do here. Um it will look for the document code. It'll do a full text search. It'll use the tree shape here to find cross links and causes. Um and then it will get the join paths. Um, and it will actually do the query for the VIN. Um, and when it does that, it will go ahead and come back with basically the part number that needs to be replaced. And in this case, there was like an old ignition coil that got revised that it had to replace it with. Um, so if you look right, it at first it did full text search to sort of ground uh the document with the right code. Um so it looked for the code and also the misfire or rough idle. Um it found uh the uh top hit which is this engine

</details>

<!-- chunk 11/12 -->

### Vector Search vs Graph Databases for Global Patterns

**Speaker A**: 类型的查找。它确认了它的信息基础和依据。所以它展示了从那个，呃，手册到这些不同程序步骤的链接。然后从那里，它执行了一个联合路径的操作。嗯，它基本上查看了包含该零件DTC代码的所有工作单。嗯，然后它能够带回我们关心的最终问题，也就是，你知道，从所有被更换的零件以及我们如何处理该代码的历史记录来看，它去数据仓库中抓取了该信息。所以你可以看到，这是一个相对简单的问题。因此，如果你使用的是向量搜索，比如Genie（比如他们的AI智能搜索和Genie）以及类似Databricks的平台，你也是可以做到这一点的，但通常会发生的情况是，为了基本上找到在那种树状层次结构上进行链接所需的内容，系统将不得不执行多得多的向量命中查询，而这其中的每一次查询都是一个可能遇到问题的机会，对吧，系统可能会找不到正确的文档，或者可能会产生幻觉（hallucinate）并在一次误判中获取到也许与该特定零件完全无关的内容。但是，因为它的信息是牢牢建立在树状结构等基础之上的，所以它能够获取正确的信息，然后将该信息准确地链接回数据表格中。嗯，因此它确实可能会有所帮助，并在处理这些较小、较具体的问题时有助于提高整体的查询效率。

<details>
<summary>Original English</summary>

**Speaker A**: type. It confirmed its grounding. So it shows the links from that uh manual over to these different procedures. And then from there it did a join path. Um it basically looked at all the work orders um with that DTC code uh for that part. Um and then it was able to bring back the ultimate question which is like you know from all the parts that were replaced and how we dealt with that code it went to the warehouse to grab that information. So you can see like this is a simple question. So if you were using vector search and like Genie, like their AI search and Genie and like data bricks, you could do this, but what often happens is to to basically find what it would need to do that linking on that tree shape, it would have to do much more vector hits, which each of those is is a chance, right, for this to run into an issue and not find the right document or potentially hallucinate and get something on a misfire that maybe wasn't n't related to that specific part, but because it grounded in the tree shape and everything, it was able to to get the right information and then link that back to the table. Um, and so it can be helpful and it can help with efficiency in these smaller questions.

</details>

### Estate Level Questions and Mismatches

**Speaker A**: 嗯，但是接下来可能会发生的情况是，当你遇到资产级别（即全局级别、宏观层面）的问题时，情况就会变得非常有趣了。所以，我现在打算直接复制这个问题，然后我将让系统开始运行它。嗯，看起来Claude模型现在运行得更快了，这是一件好事，但我会在它运行的时候详细谈谈它的运作机制。这是一个关于我们记录在案的程序步骤与我们在现场实际看到的问题之间是否存在不匹配（mismatches）的查询问题，以及我们缺少了哪些相关文档。或者说，从另一个角度来看，在我们的数据仓库数据中，有哪些文档是我们完全没有利用到的，对吧，因为我们有大量的文档在告诉我们有关车辆召回、服务公告以及所有这类事情的信息，嗯，还有各种手册，但是同时我们也有来自数据仓库的大量工作单历史记录，所以这是一个担任主管角色的人或者担任数据分析角色的人可能会非常感兴趣的问题，对吧？因为这有点，它有点像是在试图证明一个否定命题或证明一种不匹配状态，因为你有点像是在说，你知道，我不知道我具体在找什么具体的案例。但我确实是在寻找一个文档和实际操作之间的缺口（gap）。你可以想象一下，如果使用像向量搜索这样的工具，这将是一个非常困难的问题，因为相似性搜索或任何类型的相似性或词法搜索（lexical search）都很难应对，因为如果你只单单做这些搜索，根据定义，你的搜索……你无法真正去搜索一个不存在的否定事物。你必须搜索那里切实存在的东西。嗯，因此我发现，并且我认为作为一家公司，我们也发现了，当您开始遇到这些更具全局性质的类型的问题，即那些您想问的宏观资产级别的问题时，知识图谱（graphs）会变得非常有用，特别是如果它们与您可能甚至还不知道自己到底要寻找什么规律的模式相关时。

<details>
<summary>Original English</summary>

**Speaker A**: Um, but then what can happen is when you get to the estate level questions is where it can get really interesting. So, I'm going to go ahead and just copy this question and I'm going to let it start running. Um it seems like claude is moving faster now which is good but I'll talk about it as it's running. So this is a question around hey are there mismatches between our documented procedures and problems that we're seeing in the field and what documents are missing or sort of on the other half like what documentations are we not leveraging at all inside of our warehouse data right because we have our documents which tell us about like the recalls and the bulletins and and all this sort of stuff um and the manuals but then we also have the work order history from our warehouse and so this is a question that someone in a supervisor role or someone in an analytics role might be interested in, right? Because it's sort and it's sort of like proving a negative or a mismatch because you're you're sort of saying like, you know, I I don't know what I'm looking for. I'm looking for a gap though. And you can imagine that with a tool like vector search, this would be a very hard question because sim or any type of similarity or lexical search because like if you're just doing that alone by definition, you're search you can't really search for a negative. You have to search for things that are there. Um, and so what I found and I think what we found as a company is that graphs can be very useful when you start having these more global types of questions, these estate level questions that you want to ask, particularly if they're around patterns where you might not even know what you're looking for yet.

</details>

**Speaker B**: 是的。

<details>
<summary>Original English</summary>

**Speaker B**: Yes.

</details>

### Advanced Queries and Neo4j CLI

**Speaker A**: 所以这个查询运行起来确实需要一点时间，因为在这里的某个特定节点，它确实必须获取并处理大量的代码，并将一些数据相互连接在一起。嗯，但你会在这里的最后看到，它会，它会有点，呃，一点一点地把结果渗透出来，而且它会，它会详细告诉你它是如何去寻找和处理所有东西的。嗯，而且很多时候你在这些查询中看到的是，它会，它会使用一些带有特定形状（结构）的文档数据，然后它会返回去，它会回到数据仓库并从那里执行进一步的查询。嗯，在这里运行并筛选许多不同的东西。嗯，另一件事，就在它努力处理那个问题的时候我想顺便提一下，我为了清楚起见，确实在这里向系统下达了指令，要求它暂时不要使用 Neo4j CLI。我把它配置在这里的原因是，为了让你能直观地看到它使用，嗯，不同的形状（结构）。嗯，仅仅是为了让你了解不同的形状是如何彼此组合在一起并协同运作的。一旦你把 Neo4j CLI 权限交给了你的 AI 代理，嗯，它就会变得极其强大，因为它可以自动开始编写自定义的 Cypher 数据库查询，并且在某些特定的情况下，它会更喜欢这种直接编写查询的方式，而不是使用我们某些预设好的前缀形状。嗯，我想说的是，随着我们，某种类似自然语言转 Cypher（Text-to-Cypher）能力的不断增强，以及随着我们不断为它构建更多的可用技能，它将开始更频繁地、大大增加地偏好使用更自由形式的 Neo4j CLI 操作。而且，这个过程有时可能真的需要一点时间才能彻底完成。所以，我会再多给它大约 20 秒钟左右的时间。或者也许在我们等待的间隙，我甚至可以开放时间回答大家几个问题。就在我们等待这个查询完成的时候。

<details>
<summary>Original English</summary>

**Speaker A**: And so this one takes a while to run because it at at a certain point here, it does have to take a large number of codes and join some data together. Um, but you'll see at the end here, it'll it'll kind of uh trickle in and it it'll it'll tell you how it went about finding everything. Um, and oftent times what you see with these, it'll it'll use some of the document data with some shapes and then it will go back and it will go back to the warehouse and query from there. um run through a lot of different things here. Um, another thing just to just while it's working on that, I did tell it here for sake of clarity to not use the near forjly. And the reason that I I have that here is so that you can see it using the um the different shapes. Um, just for sake of understanding how the different shapes kind of fit together and work. Once you hand your agent the Neo Forj CLY um it becomes very powerful because it can start writing custom cipher queries and there will be instances where it'll prefer doing that over some prefix shape. Um, and I'd say that as our sort of Texas cipher capabilities and as we keep building up more skills, it'll start to prefer more free form Neo forj Cly stuff uh much more frequently. And this one can sometimes take a little while to work through. So, I'll give it a another 20 seconds or so. Or maybe I can even open it up to a few questions while we're here. While we're waiting for this one.

</details>

**Speaker B**: 好的。

<details>
<summary>Original English</summary>

**Speaker B**: Yep.

</details>

### Analyzing Mismatches and Semantic Expansion

**Speaker A**: 所以，基本上它接下来要做的就是去查看，嗯，好吧，我其实得等它返回最终结果来提醒我它具体是，嗯，它是怎么完整进行这个过程的。嗯，但基本上你能从工作单上看到系统已经处理了什么内容，对吧，然后你就可以从那里提取相关的代码，看看它一直在使用哪些特定的文档。嗯，然后我们还会看到因为使用了某些错误零件而导致的高返工率历史记录。所以你会有这样一种整体的看法，好吧，这里有很多文档我们可能根本没有查阅到，因为我们收到了所有这些返工记录，原因比如可能是使用了错误的零件。嗯，所以这是问题的一半，然后还有一些我们确实拥有的，嗯，文档，嗯，只是完全没有被覆盖到，因为我们正在使用的 DTC 代码在数据仓库里面根本就没有相应的记录。所以我们会清楚地知道，比如某些重要的文档完全没有被触及过。嗯，所以在这里它实际上花了稍微多一点的时间来进行，嗯，而且有时它确实会这样做。在这里它使用了语义扩展（semantic expansion）功能。嗯，所以它实际上深入进去并进行了一个更加全面的，嗯，语义扩展搜索。在这种特定情况下，它本应该使用预设的大纲（outline）。我认为正是因为有了层级化的 URI 结构，嗯，它可能能够把这部分工作做得稍微更好一点。嗯，但是如果我往回滚动找一下，嗯，它在哪里显示的结果？嗯，是的，它，好吧，它能够在这里基本上显示出它遗漏掉的现场代码（field codes）。所以，嗯，基本上有两个现场代码，嗯，得到了一个，嗯，是的，标题不匹配的报错，或者被诊断出使用了错误的维修程序。嗯，所以基本上客观存在这种不匹配的情况，嗯，在知识库文档中有几个这样特定的零件。

<details>
<summary>Original English</summary>

**Speaker A**: So, basically what it's going to do is it's going to look at the um well, I actually have to have it come back and remind me exactly how it um how it goes through. Um but basically what you can see from the work orders what has been worked on right and then you can sort of take the codes from there and see what documents it has been using. Um and then there's also going to be high comeback history on using some of the wrong parts. And so you sort of get this view of okay well there's a bunch of documentation that we're maybe not hitting because we're getting all these comebacks from like using potentially the wrong part. Um so then there's that half of it and then there's some um documentation that we have um that's just not covered because we're using DTC codes that's just not covered inside of the warehouse. So we'll know that like certain documentation hasn't really been hit at all. Um, so here it actually took a little bit more of a um, and it will do this sometimes. Here it used semantic expansion. Um, so it actually went in and did a much more comprehensive um, semantic expansion search. It's supposed to in this case use the outline. I think because it had the hierarchical URI um, it was probably able to do this a little bit better. Um but if I go back up um where did it show? Um yeah it well it was able to show here the field codes essentially um that it was missing. So um there was basically two field codes um that got a um yeah the headline mismatch or diagnosed with the wrong procedure. Um, so there's basically this mismatch um where a couple of these parts on the library document.

</details>

**Speaker B**: 对。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah.

</details>

**Speaker A**: 所以在那个地方，基本上根本没有提及正确的维修方法。嗯，这就给数据仓库的分析带来了一个严峻的问题。嗯，然后还有其他一些在维修现场实际发生的，嗯，DTC 代码。

<details>
<summary>Original English</summary>

**Speaker A**: So there where the correct repair isn't um referred to basically. Um and that's causing a problem for the warehouse. Um and then there's other um DTC codes that occur in the field.

</details>

**Speaker B**: 完全正确。

<details>
<summary>Original English</summary>

**Speaker B**: Exactly.

</details>

### High-level Themes and Correlation

**Speaker A**: 有两个代码，嗯，没有任何代码级别的文档说明，就是这特别的两个。所以确实有一些正在发生的实际代码，它能够发现这些代码基本上根本没有被记录在案。嗯，这里非常遗憾它没有使用大纲，它原本是应该那样做的，因为基本上当它使用大纲结构时，它能够更有效地遍历整个结构并找到所有的对应链接。如果是那样，在这种情况下，它就不会进行耗费了它不少时间的全面全文搜索抓取了。嗯，但即使在这里，由于有了层级化的 URI 路径以及对，嗯，全文搜索的语义扩展功能，它最终还是能够成功找到它。嗯，但这是一个很好的经验教训，即当它确实正确使用了大纲时，它返回结果的速度会快得多，因为它可以在各种不同的链接上快速遍历出去。嗯，这里的另一件事，也是我将要运行的最后一个演示，因为我们只剩下八分钟的演示时间了。嗯，我这就把它复制到这里来运行。嗯，而且这个主要，如果我直接复制它，嗯，将要利用我们的，呃，主题形状（theme shape）。所以，嗯，这是一个正在询问我们所有技术公告和召回事件中的常见规律模式的查询，嗯，以及每种模式大概分别影响了多少辆汽车。所以，我们在我们的，呃，数据仓库里面存放着我们的工作单历史记录。而且，呃，基本上我们想要找出的结果是，比如哪些，你知道，我们所拥有的那种主题分类与，嗯，我们的实际工作单历史记录是如何产生关联的。嗯，为了做到这一点，系统会运行那个特定的主题模式，以便能够从海量数据中提取高层级的主题，然后将其紧密地关联回我们的工作单中。因此这本质上是一个数据覆盖率的问题。所以你可以清楚地看到它会运行主题，然后，嗯，最终在这里它会继续带回，嗯，所有的，所有相关的重要信息。但是基本上它所做的核心工作是，它，它正在寻找潜在的主题。它将去提取并分类它在工作单历史记录中拥有的那些修复操作的类型，然后它将执行某种形式的连接（join）操作，大概是把它们准确地归类到正确的主题类别下。在这个后台运行的过程中，大家还有没有其他关于这个主题形状或任何相关方面的问题？我知道其他……

<details>
<summary>Original English</summary>

**Speaker A**: that have two um that have no code level documentation which are these two. So there's codes that are occurring which basically aren't documented that it was able to find. Um it's a shame here that it didn't use the outline it's supposed to do that because basically when it uses the outline it's able to traverse through and find all of the links a little bit more efficiently. It wouldn't have done the comprehensive full text search crawl that took it a while in this case. Um, but even here because it had the hierarchical URIs and that semantic expansion on the um, full text search, it was able to eventually find it. Um, but it's a good lesson that when it does use the outline, it can come back faster because it can traverse out on the different links. Um, the other thing here, the last one that I'll run because we only have eight minutes left. Um, I'll go ahead and copy it here. Um, and this one is primarily, if I go ahead and copy it, um, is going to leverage our, uh, theme shape. So, um, this is asking for common patterns across all our bulletins and recalls um, and how many of the cars sort of each affects. So, we have our work order history inside of our uh, warehouse. And uh basically what we want to find out is like which you know how does the sort of themes that we have correlate with um our work order history. Um and to do that it runs that theme pattern to be able to pull out the highle themes and then correlate it back to our work orders. And so it's a coverage question. So you can see it'll run the themes and then um eventually here it will go ahead and bring back um all of the all the relevant information. But basically what it's doing is it's it's finding the themes. It's going to go and pull sort of the types of fixes that it has in the work order history and then it's going to do a join of sorts to kind kind of group them under the right theme. While this is running, are there any other questions about this theme shape or anything? I know other

</details>

<!-- chunk 12/12 -->

### 图构建过程与数据模型

**Speaker A**: 是的。请继续。

<details>
<summary>Original English</summary>

**Speaker A**: Yes. Go ahead.

</details>

**Speaker B**: 抱歉。请再说一遍。在图构建过程中是怎样的。

<details>
<summary>Original English</summary>

**Speaker B**: Sorry. Say that one more time. how during the graph construction.

</details>

**Speaker A**: 嗯。

<details>
<summary>Original English</summary>

**Speaker A**: Yeah.

</details>

**Speaker B**: 对。所以我设计的这些形状实际上是在我们的规范中定义的。所以，如果你看这里，我们的轮廓形状，也就是我们在文档里的规范。所以这个定义的初衷，更多是考虑到我们希望它在代理（agent）看来是什么样的。一旦我们定义好了，我们就会想出我们想要的查询结构，然后用它来指导我们的数据模型。所有的文档基本上都被加载到了我在课程开始前一个半小时左右讲过的那个数据模型中。那个数据模型有一个包含所有文档之间链接的包含树。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. So the shapes that I that I are actually defined inside of our specs. So if you go here, our outline shape um our specs in our docs. So this was defined more thinking through like here's what we want it to look like for the agent. And then once we define that, we come up with sort of the query structure that we want and we use that to inform our data model. Um, and all of the documents were loaded essentially um into that data model that I went over about an hour and a half before towards the beginning of the course. Um, it's that has containment tree with all the links between it.

</details>

**Speaker B**: 并且你可以在这里看到，它会返回它所使用的主题（themes）。它没有使用搜索（search）。然后它也查询了，如果我往上滑到这里，你可以看到受影响的汽车。所以，它基本上是用那个连接形状去了仓库，然后能够将它们分门别类地归入不同的主题类型之下。所以，就像那个主题，我们有的不同主题类型，然后按百分比将汽车和工单分组在下面。嗯，是的，请这边的这位提问。

<details>
<summary>Original English</summary>

**Speaker B**: Um, and you can see here it'll um it'll bring back the um that it used themes. it didn't use search. Um, and then it uh also uh queried the um if I go up here, you can see the cars affected. So, it basically went to the warehouse with that connection shape um and it was able to sort of group them under um the different uh theme types. So, it's like that theme, the different theme types um that we have and then kind of with the cars and the work orders grouped underneath by percentages. Um yes, over here.

</details>

### 系统准确性与知识库扩展

**Speaker C**: 对，哪一个都行。我能知道当知识库扩展时，这些工具的准确度如何吗？

<details>
<summary>Original English</summary>

**Speaker C**: Yeah, either one. Do do I have a sense of accuracy of how well these do when the knowledge bases expand?

</details>

**Speaker B**: 嗯，关于这一点，我还没有就我今天向你们展示的确切内容运行过任何特定的基准测试。但我会说，当我们有客户运行这些工具时，他们通常会提出自己的自定义本体（ontologies），然后他们会运行基准测试，这些测试基本上会说明这种查询模式相对于普通的向量搜索等方法有多有效，并且你们会用它在特定类型的数据集上进行验证。对于本课程而言，这更多是概念性的，为了让大家理解可以用来帮助基础化你的数据的不同形状。当然，在如何构建这项技能方面，它总是需要不断完善的，对吧？以确保它能引导出正确的结果，从而确保它基本上能高效地使用每一个步骤。

<details>
<summary>Original English</summary>

**Speaker B**: Um, for this I haven't run any specific benchmarking on like exactly what I've shown you today. But I will say that when we do have customers that run these, they'll often come up with their own custom ontologies and then they will run benchmarks uh that will basically say like how effective is this query pattern against you know ordinary vector search for example and you would use that to prove it out on on a specific type of data set. Here for this course this is more conceptual to understand kind of like the different shapes that you would use to help ground your data. Um, and it can always use work in terms of how you were to like build the skill, right? To make sure it guides through the right thing so it uses, you know, each step efficiently essentially.

</details>

**Speaker B**: 还有其他问题吗？

<details>
<summary>Original English</summary>

**Speaker B**: Are there any other questions?

</details>

**Speaker D**: 有的。是的。嗯，也许我还没有完全理解。所以，你有一个连接点，在什么之间？在……之间，对吧。

<details>
<summary>Original English</summary>

**Speaker D**: Yep. Yeah. Well, maybe I don't fully understand. So, you have um a connection point between between what? Between Yeah.

</details>

**Speaker B**: 对。是的。不，我们现在还没有。所以，现在我理解你的问题了，问题是，连接的结构化数据图和非结构化数据图之间是否存在链接？答案是没有。在这种情况下，它们是完全未连接（unlinked）的，代理有点像在提取，你知道，从其中一个提取一部分，或者它在提取一个类似代码的东西，对吧？然后再参考回文档。所以，它是在利用这个机制来实时进行自己的表连接（join）。你可以创建那种链接，这对于更确定性的映射会很有价值。嗯，在这里我们没有这么做，我没有这么做的主要原因实际上是为了能够快速上手，因为我确实有点想提供既简单又与模型无关（model agnostic）的代码。嗯，就是这样，如果你以后想创建那些连接或链接，你也是可以做的。

<details>
<summary>Original English</summary>

**Speaker B**: Yeah. Yeah. No, we do not have so right now. So, now that I understand your question, the question is, is there a link between the connection structured data graph and the unstructured one? And there is not. In this case, it's they're completely unlin and the agent is sort of extracting, you know, a part from one or it's extracting like um yeah, basically like a code, right? And then referring back to the document. So, it's it's using that to kind of do its own join in real time. You could create that linking and that could be valuable for more deterministic mapping. Um here we didn't do it and the main reason I didn't do it was really for speed of getting started because I did kind of want to provide code that would be easy and also model agnostic. Um and this is that and then if you wanted to later create those connections or those links you could.

</details>

### 课程结语与资源说明

**Speaker B**: 还有其他问题吗？好的。嗯，感谢大家。希望这些内容对你们有帮助。如果你想复习，这个研讨会是在线提供的，你可以去参加。我最终将不得不撤下 Anthropic 的密钥和 BigQuery。我会让 BigQuery 保持开启一段时间，但 Anthropic 的密钥我最终必须撤下。所以，遗憾的是，你们需要提供自己的密钥，但除此之外，你们应该能够顺利地进行这个研讨会。嗯，我想我要讲的就是这些了。所以，我把时间留给我的下一位嘉宾。希望你们有足够的时间准备进入你们的下一个环节。

<details>
<summary>Original English</summary>

**Speaker B**: Um any other questions? All righty. Well, thank you everyone. Hopefully that was uh informative. If you want to go back, the the workshop's available for you to take, it's it's online. I am going to have to take the anthropic key and the big query down eventually. I'll I'll leave the BigQuery one up uh for a while, but the anthropic one I'll have to eventually take down. So, unfortunately, you will need to provide your own key, but other than that, you should be able to take it just fine. Um, and I think that's all I have. So, I'll leave it for my next guest. Hopefully you guys have enough time to jump into your next session.

</details>

**Speaker B**: [音乐]

<details>
<summary>Original English</summary>

**Speaker B**: [music]

</details>