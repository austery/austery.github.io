---
author: AI Engineer
date: '2026-07-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Q0VkgCyNVUg
speaker: AI Engineer
tags:
  - graph-rag
  - agent-memory
  - vector-database
  - knowledge-graph
title: CrabRAG：为什么智能体需要图记忆而非更多 Token
summary: Neo4j 的 Steven Chin 阐述了 AI 智能体在记忆和工具调用上面临的瓶颈。通过对比传统的 Markdown 文件和向量数据库，他展示了结合向量检索与图遍历的 Graph RAG 架构如何为智能体提供更精确、可解释且可审计的长期记忆，并通过家庭实验室数字化双胞胎的实战 Demo 证明了图谱在复杂多跳查询和安全检测中的压倒性优势。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Neo4j
  - Anthropic
  - Cognite
products_models:
  - OpenClaw
  - Goose
  - Claude
  - pgvector
  - LanceDB
media_books:
  - 'Graph RAG: The Definitive Guide'
status: evergreen
---
### CrabRAG：为什么智能体需要图记忆而非更多 Token

### 文本记忆：智能体的效率瓶颈
在构建更具自主性的 AI 智能体时，我们都在寻找能够获取更准确回答和更好结果的方法。然而，现有的底层工具往往与我们的目标背道而驰。以智能体助理 **Crab D** 为例，它面临着一个致命的痛点——非常糟糕的长期记忆。它每天醒来，其记忆文件都会被重置，从而遗忘了前一天发生的所有事情。这导致用户每天都必须重新训练它以执行相同的任务。

目前大多数智能体工具（例如 **OpenClaw**）的**上下文窗口**（Context Window: 模型一次性处理文本的最大容量）和记忆系统都是基于普通的 Markdown 文件构建的。虽然 Markdown 文件易于人类阅读和维护，但对于智能体而言，这会消耗大量的 **Token**。智能体在每一轮对话中，为了确保能够加载到有用的信息，往往会将所有 Markdown 文件都加载进上下文，这导致单次运行的 Token 消耗量轻松突破 100k。这种重复且低效的机制在小规模应用中尚能勉强工作，但在面对大规模应用时则完全无法扩展。

即使是像 **Goose**（一个由 **Anthropic** 支持、属于智能体 AI 基金会的新项目）这样前沿的自动化工具，也依然面临着相同的底层记忆瓶颈。虽然 Goose 引入了**模型上下文协议**（Model Context Protocol / MCP: 连接 AI 模型与外部数据源的开放协议），将记忆系统视为一个可插拔的 MCP 服务，但其本质上依然是在磁盘上读取和操作 Markdown 文本文件，这无法从根本上解决 Token 浪费和工具误选的问题。

<details>
<summary>Original English</summary>

My name's Steven Chin. I run the developer relations team here at Neo4j. And I'm excited to talk to you about something we've all come to love, our crustacean friends. So, we have OpenClaw mascot. We have a bunch of other crustaceans. And we're going to focus on one member of the crustacean family. I love crab. So, our little boy, Crab D. And I think in the journey to figure out how to apply agents, how to do things which are more autonomous, we're all looking for ways where we can get better results, more accurate answers, and to actually capture all of this. But the tools kind of work against us. So, here's our friend Crab D. He's a personal assistant, very happy, very eager. He wants to help us out with our lives, maybe to help us to code, to help us to manage our email, to do different things. But he's got a problem. And our poor boy Krabby D has a very bad memory. He wakes up every day and his memory file flips and now it's a new day and he forgets everything from yesterday. Has this happened to you where you wake up and you're using OpenClaw and suddenly it's on a new set of memory files and remembers nothing that you actually did the previous day. He's got a lot of tools at his disposal. I mean, we love giving our agents tools, but sometimes he doesn't pick the right tool for the job. I don't think either of these are going to help him drink his bowl of soup. So, that's not the tool which he was looking to reach for. And he is a little bit forgetful at times. So, you know, I think I don't remember everybody I meet, but I'm pretty good at faces. Like, if I've met you before, I recognize faces. It's like, pleased to meet you. Crab D is not as good at that. So, very forgetful. It's like you're retaching it every day to do the same sort of tasks. And we want agents which are more helpful, which are able to do more for us.

So, let's dig into how CrabD actually works. So it's basically a memory loop, right? So we're prompting, we're thinking about the response, maybe calling tools, observing what happens. But the hard part is the memory. The hard part is what you put in context, what you're recalling from. And the way you have memory structured in most tools, this is an example of how OpenClaw structures things is you have a folder for your agent's memory. You have maybe memory files, you have different tool files, you have daily memory files. Now, if you look at this, there's one thing which is in common with all of these. They're just markdown files. So, markdown files are great. That's easy for us to read. Like, we can look through it. We can quickly figure out what's not needed and compact them. They're intentionally small for agents because you have a limited context window and also you need to keep the right things at the top of the context. But if your whole memory is a bunch of markdown files, you're wasting a lot of tokens. So, my average agents are loading up at least 100k in tokens for each round. They're doing a lot of skills. They're adding a lot of things into the context constantly. It's very repetitive because they basically load up everything in the hopes that something will be useful in the context. At small scale that works where you get the results you want with a high quality model. It doesn't work at large scale and I'm going to show a demo of large scale where we take OpenClaw and we let it run loose on my home lab. So high demo risk but a lot of fun and a classic digital twin scenario. So I think we'll have a lot of fun here. Anybody use Hermes agent at all? Okay. I'm a big fan of Hermes agent. I think it's got a much better memory system. It kind of at the end of each task it goes and it reflects and it adds back in new skills or new things which it needs. So it's a really powerful system and again we're relying a lot on markdown files. Skills are just basically markdown files. But we can teach the agent to do a lot of things with skills and it can get the right skill if it gets loaded up and then good things happen. But sometimes we don't get the right skill loaded up. So our poor boy CrabD here is not going to get that clam. He just doesn't have the open clamshell skill. Lots of shrimp, no clams. Maybe you picked the wrong skill for the job and suddenly you're jet skiing on the beach, right? This is not going to get him very far. And sometimes you might get that clam open, but then you don't have the skill to eat them. So skills, you need to have the right skills, the right chain of skills. Actually we have an awesome project by one of the Neo4j folks which is just bananas as an arXiv paper which is a graph for skills. So that's an exciting way of figuring out what the right skills are but maybe we can do better. So Goose is a project that's part of the agentic AI foundation, a new foundation which MCP is part of. Anthropic is backing this. We're also a member of this. So, it's a great automation tool for a lot of enterprise workflows. You can also use it kind of like a personal assistant. It relies heavily on MCP as the layer, over 70 MCP extensions. And what it does is it treats memory just like another MCP server. So, this is great, right? It's pluggable. You can call different commands on it to retrieve memories, remember memories, forget memories. Memories are just plain files on disks. So now you can manipulate them. So same great idea, same fundamental problem. We're storing the memory of agents as markdown files on disks. And again, you end up with what if you pick the wrong tool for the job, the wrong paddle? Now, in this case, if you pick the wrong paddle, you're a genius because you've invented the most, the fastest rising sport in the US, which is pickleball. Actually, the origin of pickleball was a family wanted to create a new game and they just took what they had around the house, a badminton court, and made up the rules along the way. So, creation can be good when you have the wrong tools. Maybe you remember everything, but it's too much weight because you can't actually solve the problem. So our poor friend Goose here is encumbered by too many notes, too many memories, or most dangerously now you have MCP tools. You're one step away from calling the forget command and just wiping out your own memory.

</details>

### 向量缺陷：相似不等于关联
为了解决 Markdown 文件的效率瓶颈，人们开始采用**向量数据库**（Vector Database: 专门用于存储 and 检索高维向量数据的系统）。我们可以将所有记忆和知识转化为**向量嵌入**（Vector Embeddings: 将离散数据映射为连续实数向量的技术），从而存储整个知识库。

使用向量数据库后，我们可以执行**相似性检索**（Similarity Search: 基于向量距离寻找相似内容的技术）来拉取相关信息，这让智能体拥有了更大的知识库。例如，OpenClaw 默认支持 **pgvector**，同时 **LanceDB** 也是一个非常优秀的选择。

然而，向量检索面临着一个核心挑战：**向量空间中的相似性并不等于客观世界中的真实关系**。当面对复杂的多跳推理场景时，仅依赖向量相似性进行检索极易导致模型产生**幻觉**（Hallucinations），且难以建立长链条的逻辑推理。此外，在传统的关系型数据库中执行此类复杂查询，其计算成本也是极其高昂的。在实际应用中，智能体极易因为“看起来相似”的信息而做出错误的决策，这就像是从更衣室拿错了非常相似却完全不属于自己的外壳。

<details>
<summary>Original English</summary>

So vector databases, right? So we can store everything. We can create embeddings for it. Now we actually have a database. We can store it in a vector database. So this is great. I mean you have to pick the right vector database. And then now you can do similarity searches. So you can pull back information which is relevant. So we're doing much better. We have a larger repository of knowledge. We can pull back related information. OpenClaw comes with pgvector out of the box. Given embedding, you can just start using this. LanceDB is a great option. I'm going to use both of those in my demo. But the challenge here is similar what vectors give you, which is similarity in vector space is not the same as actual relationships. And so you get hallucinations. You get a lot of problems when you're relying solely on vector lookup as the answer. And it compounds with more complex scenarios when you're doing things like I'm going to show you an example of a digital twin. When you're doing things which are very complex, they just don't scale and you make silly mistakes like this obviously is not what poor Crab D wanted to munch into and it's a very expensive lunch for him. Also, it's sometimes impossible to get to the answer even though you have all the facts because those large multihop reasoning chains don't work on similarity searches. They're also very expensive on traditional relational databases. And often things look similar, but they're not exactly the same. And this is one of the problems with the responses you get from a vector database is you suffer from getting facts which are related in some way and they're not your shell and you don't want to take the wrong shell out of the locker room. That's very unfortunate.

</details>

### 图谱升维：融合检索打破幻觉
为了克服向量数据库的缺陷，我们引入了**知识图谱**（Knowledge Graph: 由节点和带有属性的边构成的网状关系数据结构）。图谱是映射真实世界关系、识别实体和建立完整逻辑链的最佳方式，天生为处理高度关联的数据而设计。

在图谱中，**节点**（Nodes）和**边**（Edges）作为一等公民，能够直接存储对象及其关系，并在图的上方配置属性信息。现代图数据库还支持在图中直接存储向量嵌入，这使得开发者可以将向量与图谱完美融合。

在本系统的架构中，我们采用了一种创新的混合检索设计：
1. **向量检索**：首选用向量相似性搜索快速定位初始的**种子节点**（Seed Nodes）。
2. **图遍历**：以此节点为起点，进行**图遍历**（Graph Traversal: 沿着图 of 节点和边寻找关联路径的过程），拉取其最近邻居节点。
3. **关系排序**：根据节点间的真实关联强度对结果进行排序，最终将最相关的上下文送入模型。

这种**图检索增强生成**（Graph RAG: 结合知识图谱与检索增强生成的技术）架构赋予了智能体处理复杂多跳查询的能力，从而解决更难、更具行业针对性的业务问题。此外，它具有极高的**可解释性**与**可审计性**，开发者可以清晰地追溯图遍历的路径，找出模型回答的数据来源。如果你不是图谱或 **Cypher** 查询语言的专家，**Claude** 等大语言模型也可以极其高效地帮助你编写查询、抽取实体并构建知识图谱。

<details>
<summary>Original English</summary>

So enter graphs. Graphs are a great way of finding the relationships, finding those identities, mapping out the paths, getting that full chain and they're built for this sort of connected data. So now that you have first class nodes which are the circles, edges, those are the relationships between different objects and then you can put properties on top of graphs to store information. You can also store embeddings in your graph and that gives you a way to both use vectors and graphs together. Architecturally the demo I'm going to show you is both a vector search and a graph search. So it uses the vector search to get the seed nodes where it starts the traversal and then it uses a graph search pulling the nearest neighbors and then ranking those by how related they are. And this gives you this complex multihop queries to solve more difficult more domain specific problems and to figure out where that reef is that we want to get to with all the tasty junk food across the ocean. And graphs are they're accurate so they give you very precise information. Explainable because you can look at the graph which got returned and auditable because now you can actually say this is the context. This is the part of the graph which resulted in that answer. So it's very powerful and it gives you more tools as a developer where if you're not getting the right answer, you know where it's coming from. You can actually see and introspect the graph and you can change how you're doing extraction. You can reduce duplicate nodes in the graph and then you can get to and converge very quickly on a great answer. If you're not a graph expert, guess what Claude is. Claude can write Cypher better than I can. Claude can extract build entity extractors and it can do pretty much everything you need to do to get started with graphs today as long as you know the basic kind of model for what you want to accomplish. That's what I'm going to cover in the demo. So, we're going to have Claude action into the graph as he works. We're going to follow up by traversing, not rereading it. And then in a fresh session, we will get the results we want to get out.

</details>

### 双胞胎实战：图谱的安全优势
为了测试该系统在真实场景下的表现，我们构建了一个**数字化双胞胎**（Digital Twin: 实体系统在数字世界中的虚拟映射）的测试环境。我们将包含几台电脑的个人**家庭实验室**（Home Lab）建模为知识图谱，并配置了两个完全独立的测试环境：环境 A 使用纯向量数据库检索（**pgvector** 与 **LanceDB**），环境 B 使用搭载 **Neo4j** 后端的 **Cognite** 图存储系统。我们在路由器上划分了隔离的 VLAN，断开网络连接，让智能体仅能从离线记忆中寻找答案。

在现场演示中，我们对这两个环境进行了两轮安全检测问题的对比测试：

* **测试一：检测网络中暴露的生命周期结束（EOL）软件**。
  在测试网络中，运行着女儿的 Minecraft 服务器虚拟机 `tinsterland`，其操作系统是早已停止维护的 **Debian Jessie**。
  - **向量记忆响应**：由于缺乏对网络拓扑和关联关系的感知，向量检索无法找到具体细节，只返回了因策略限制无法提供精确信息的无用回答。
  - **图记忆响应**：智能体自动生成并运行了 Cypher 语言进行图遍历，以向量检索出的 `tinsterland` 作为种子节点，成功沿着依赖路径找出了其运行的过期系统版本，给出了非常精准且可操作的漏洞报告。

* **测试二：检测暴露在公网（WAN）的管理端口**。
  网络中实际将 **HAProxy** 和 **OpenVPN** 的管理端口暴露给了互联网，这在安全规范中是极其危险的。
  - **向量记忆响应**：向量数据库仅检索到了宽泛的防火墙规则配置，并给出敷衍的回答，要求用户“自己去检查 **pfSense** 路由器的规则”。
  - **图记忆响应**：图检索呈现出了完全不同的拓扑形状。智能体顺着 pfSense 路由器的节点，直接沿着网络连接关系定位到了暴露在 WAN 上的 HAProxy 和 OpenVPN 服务，并精准识别出了这两个存在安全隐患的端口。

<details>
<summary>Original English</summary>

Now, what I did for this high stakes demo is over the past week or two, I took my home lab as the demo environment, did a full digital twin as a graph, and I have two separate environments built off the same original markdown files. One is a vector database store, that's our A test, and the second is a graph store, that's our B test. And the graph store is built on top of Cognite. So I'm using Cognite which is a startup. They do amazing stuff in the memory space. They have a Neo4j backend. This is the structure. So we have a bunch of Proxmox servers in my home lab. It's really a couple computers around my desk and I built a separate VLAN for the demo. So it's segmented off my real network. So it was trained on real network for my network. But now it's cut off. It can only answer from memory. It can't actually look up the hosts and get dynamic information. So, let's see how it does in a live demo. Okay. So, all right. Here we have our crab rag cockpit. And I have five different questions queued up with schematics. You can see this is the same home lab schematic that you saw earlier in the slides and let's start with this one. So exposed end of life software. So we're going to try to find out if there's anything on my network which is exposed to the internet, the WAN, that's running out of date software which put my home lab at risk. So if somebody can attack the home lab, and you can see here that there is some servers, tinsterland, which is my daughter's Minecraft server, it's running, oh my god, Debian Jessie, and let's see how the two agents did in looking this up. Okay, so we got the vector response back. Couldn't find specific details, excluded by policy for more precise information, yada yada yada, source it separately. Okay, that's not very helpful. Now, on the graph side, it's done a bunch of Cypher queries. Here are the Cypher queries it's fired off. This is the graph traversal. And the color coding on the graph traversal is these blue guys. These are the seed nodes. So this came from a vector lookup and a ranking. But it didn't stop there. It does the one hop traversals. Those are all the gray nodes. Some of the nodes get highlighted in green and those are the ones which won and got into context. And you can see the answer here. So guest name tinsterland exactly as expected. OS version out of date and it's flagging. So it gives us very precise actionable information. And so that's the difference between same exact data. One is a vector store, one is a graph store. And you can see the difference where the vector store is having a lot of trouble pulling the relevant information out. Okay, let's try another one just for fun. Let's see. Expose 0.0.0.0 management ports. That's bad. So, basically, you don't want your management ports on the network exposed to the world. And there's a bunch of these. So, I have a new matrix server I set up, and also HAProxy, which are exposed to the internet. That's bad. The rest of these, like my Cognite demo, my OpenClaw instance, those are inside the LAN. You need to get into the LAN to access them. That's what you want. Okay. And let's see how the two agents did in identifying this. So the memory search returns some information and it's telling me check services configuration expect PFSense rule. So it told me to go do the job for it. Okay, and then the graph memory side found an open port exposed to WAN HAProxy and OpenVPN which are the two we expected. Now this you can see the shape of this graph is entirely different from the previous one. And what it did is it actually found the node for my router, the PFSense router, and it was able to follow that directly to all of the results which related to it and then give us a very precise answer. All right. So, now we've seen our little boy Crab D with his certified Neo4j developer t-shirt is able to do a lot more. Right now he's able to follow that full chain, crack, eat, do the next thing. So, he's getting his clams. He's helping me fix all the security holes in my network. Um, oh, by the way, I patched all those security holes after the demo. So this was good for me too. It found a bunch of security holes in my home lab and then I went and patched them later.

</details>

### 规模化未来：构建企业图记忆
从家庭实验室扩展到大型企业级场景，数据量将呈指数级增长。无论是大型数据中心、海量的客户记录还是高频的金融业务，其数据复杂度都远远超出了单次会话的上下文限制。即使现代大模型已经拥有百万级别的上下文窗口，如果仅仅把原始的 Markdown 文件或者非结构化文本塞进 context，其高昂的 Token 成本和极低的检索精确度依然会导致系统崩溃。大型智能体系统必须转向以知识图谱为核心的结构化记忆系统。

为了帮助开发者掌握这一前沿技术，Steven Chin 与合著者 **Michael Hunger** 以及 **Osus Barasa** 共同撰写了新书 **《Graph RAG：权威指南》**（Graph RAG: The Definitive Guide，已在 early release 早期发布阶段）。该书不仅涵盖了 Graph RAG 的基础原理，还深入剖析了如何在各种垂直行业应用中为 AI 智能体构建高效的图记忆系统和端到端的图谱应用程序架构。

此外，Neo4j 还面向全球开发者提供了免费的在线学习资源——**图谱学院**（Graph Academy: dev.neo4j.com/graph-rag），其中包含关于智能体长期记忆、上下文图谱构建等一系列实战课程，帮助开发者快速上手并将 Graph RAG 技术应用到真实的生产环境中。

<details>
<summary>Original English</summary>

And now we have an agent which actually can do interesting things. Now, if you can imagine like I have a three or four node home lab at home. If you have a big enterprise which has a huge data center, if you're doing things in financial services where you have like a huge set of companies and customer records you're trying to do, if you're doing anything at large scale where it doesn't fit into the 1 million context window of the modern models, you really need a better memory system than just throwing things in markdown files. Our little boy Krabby knows his whole crew, all the Crustacean friends and he's read the book. So we just finished my co-authors and I Michael Hunger and Osus Barasa finished Graph Ragg the definitive guide. The full book is out on early release. It'll be published in a couple months once they finish the editorial process. But super excited about this. It's got information not only on graph rag but also on building memory on different industry vertical use cases on agents. So it's kind of the whole umbrella if you're building on top of graph solutions how you need to build applications the technologies you need end to end. And then finally, a great free resource which everybody in this room can take advantage of is Neo4j's Graph Academy. So it's free online training, dev.neo4j.com/graph-rag. And we have courses on doing agent memory, doing context graphs and everything you need to get know to get started and to do some of the amazing stuff which I showed you on stage today. So thank you so much for coming to the kickoff talk for the graph track. You're in the right place for all of the content from graph experts. Andreas Kollegger, my colleague and I crafted a great set of speakers from industry experts, people who really know about graph technology. So hang out here, find out more and then you can see me in the Neo4j booth. Thank you.

</details>