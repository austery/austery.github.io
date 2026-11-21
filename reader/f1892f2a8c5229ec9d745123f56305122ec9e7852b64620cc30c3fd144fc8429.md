---
author: AI Engineer
date: '2026-07-18'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3ySF0I5iE_0
speaker: AI Engineer
tags:
  - graph-database
  - entity-resolution
  - path-finding
  - subgraph-matching
title: 图数据结构与算法实战：构建更智能、经济且可靠的 AI 系统
summary: 本文基于专家实践经验，系统解析了如何通过图数据结构与算法优化 AI 应用。文章详述了利用架构模式进行高保真图谱提取的方法，深入探讨了个性化 PageRank、最短路径及子图匹配等经典算法在召回增强、上下文优化与模式识别中的落地场景与效用。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs: []
products_models:
  - HippoRAG
media_books: []
status: evergreen
---
### 突破幻觉：重构图谱的理性价值

虽然**图数据库**（Graph Database: 以节点、边和属性存储并查询图结构数据的非关系型数据库）与可视化关系图谱在视觉上极具吸引力，但在实际的工程落地中，开发者往往难以在初期获得预期的投资回报，甚至会陷入令人沮丧的**“幻灭谷”**。这种挫败感主要源于盲目推行复杂的 **GraphRAG**（Graph Retrieval-Augmented Generation: 结合知识图谱检索与大语言模型的检索增强生成技术）或对已有系统进行过度重构。要越过这一低谷，关键在于深入理解底层图数据结构与算法的运作机理。在 AI 时代，许多关于信息检索、模式识别及语义理解的核心痛点，正是图算法的天然优势所在。通过将经典的图原生算法与大语言模型进行**混合治理**，我们能够在不增加计算开销的前提下，显著提升 AI 应用的决策精度与运行效率。

在明确了图的应用方向并避开盲目狂热的泥潭后，我们首先要面对的是如何从非结构化文本中构建高质量图谱的基础挑战。

<details>
<summary>Original English Source</summary>
Hi, I'm Tim Angers from The Good Collective and welcome to AI Engineer's presentation, a practitioner's guide to graphs, how to make your AI applications smarter, cheaper, and more reliable. Graphs have always been a powerful foundation of computer science and they look beautiful. But sometimes they're genuinely not the right tool for the job. We've all felt the wonder of a mesmerizing data science graph or ogled the graph view of our Obsidian vault. It can be tempting to rush into something like GraphRAG or rebuilding our e-commerce shop with a graph database. But often we don't see the instant payoff we might have expected. In frustration, many journeys end here in the dust at the bottom of the valley of despair and disillusionment. What's on the other side of the valley and how do we get there? That's exactly the question that sparked the idea for this talk. Have I nailed all of the answers? Definitely not. But what I'm finding is that the more I learn about the fundamentals of graph data structures and algorithms, the more interesting opportunities seem to present themselves. Many of these graph native use cases or good fits for graphs are also a lovely complement to many of the search, pattern recognition, retrieval, or knowledge-based problems that are ripe for solving in the AI age. Now, just a quick disclaimer. This talk isn't going to go into GraphRAG or agent memory graphs. Not because I'm throwing shade on those patterns and products, but partly because there'll be many other talks covering each of those single topics. But more importantly, this talk is for AI builders and I'd like to focus on the underlying patterns, which may just help you come up with your next big graph-powered AI application. Today, we're going to speed run the basics of graphs. Then we'll walk through some tips and tricks for building better graphs to get better results. And then we'll look at graph native algorithms that leverage a graph and the benefits that they deliver. At each step of the way, we'll open with a principle, look at an easy example and some code, and then finally, we'll reference some real-world examples with real-world benefits.
</details>

### 架构先导：模式与本体工程定义

在将非结构化文本转化为图数据的过程中，最常见的反面教材是采用无约束的“主-谓-宾”**三元组**（Triple: 包含主语、谓语、宾语的图数据最小单元）进行粗暴提取。这种缺乏约束的提取方式会导致节点类型混杂、关系定义模糊，使图谱无法被有效检索。为了解决这一问题，我们必须为提取器提供明确的**模式定义**（Schema: 规定节点类型、边类型以及属性结构的元数据模板）。以菜谱为例，通过引入明确的菜谱架构，定义成分（Ingredient）、数量（Quantity）和烹饪步骤（Steps），大语言模型便能以结构化输出的方式生成极具逻辑一致性的图谱。此外，我们还需要构建细致的**本体工程**（Ontology: 描述特定领域内概念、实体及其相互关系的规范化模型），指导 AI 统一度量衡（如公制单位标准化）并规范实体命名。这不仅能净化图谱的拓扑结构，更赋予了关系网络极高的可查询性。

仅有规范的架构依然无法完全避免现实数据中的多义与冗余问题，因此必须引入更高级的节点归一化机制。

<details>
<summary>Original English Source</summary>
All right, let's speed run the basics. What's a graph? A graph is something that has nodes, also called vertices, and edges, which I sometimes call relationships, that connect the nodes together. That's it. That is the most basic definition of a graph. We can have different types of nodes and edges, which convey more meaning. Uh we can also put labels on edges and nodes and have properties. And of course, edges can have direction. Now that we've speed run that, a really, really important part of getting good value out of graphs is how we build good graphs. Today, we're going to focus on extracting graphs from unstructured text, cuz that's a pretty common use case and a pretty popular one at the moment. So, in this example, we've defined a very basic data structure for our graph, a triple, that has a subject, a predicate, and an object, or a node that somehow relates to another node. And we say to our agent, "Hey, go and pull the key information out of this thing as subject, predicate, and object triples. You figure it out." And then we give it a wrap pancake recipe. It's done an all right job. We've got a graph. But, we wouldn't get very far with this graph. It's got some problems, so we'll talk through that next. One of the key principles about building better graphs is giving the extractor a schema to fill. In this case, if we say, "Instead of using triples, use a recipe. And a recipe has ingredients, and ingredients have a quantity. If we give this to an agent with its structured outputs, what we get back is instantly way more meaningful than the graph we had before, and a lot tidier. So, the benefit here is that with consistent node and edge types, relationships become meaningful and something that we can interrogate or query. Let's take this a little bit further to say that a recipe has ingredients, but it also has steps, and each step is the application of a cooking technique. Now, we've got a graph with structure that's starting to look a bit interesting.
</details>

### 实体对齐：向量嵌入的混合治理

在图谱构建中，如何解决**“实体同物异名”**（如“大蒜瓣”与“碎蒜”、“植物油”与“食用油”被误识别为多个独立节点）是维护拓扑完整性的核心瓶颈。传统的去重策略往往依赖前置定义的字典进行暴力映射，但这要求开发者必须提前预知所有可能出现的实体，在面对动态演进的真实场景时显得极为僵化。现代的解决方案是引入**向量嵌入模型**（Embedding Model: 将文本或实体转化为高维连续稠密向量的语义表征模型），实现动态的**实体解析**（Entity Resolution: 识别并合并指向现实世界同一物理实体的不同节点的过程）。通过将图拓扑关系与语义向量进行杂交，系统能够在不需要先验词表的情况下，以极高的鲁棒性完成动态节点的对齐与融合。这种混合方法不仅能精简图规模，更通过多边聚类增强了关联路径的拓扑强度。

完成了高质量图谱的构建与实体清洗后，我们便拥有了进行深度关系查询的基石，首当其冲的便是图查询与经典排序算法的组合。

<details>
<summary>Original English Source</summary>
Now that we have a well-defined schema and a nicely structured graph, we need to add detail to our ontology. The ontology describes how to extract information into our graph, or precisely what to put into that structure. In our case, we want to provide instructions to our agent to standardize the formatting of ingredient names and to standardize units on the metric system to make matching and conversion easier. These extra instructions are just as important to the title model as the schema is. And boom, there we go. We've got lowercase ingredients and metric units. We know that the best prompt in the world isn't bulletproof, though. So, we'll look next at how to make sure we really do standardize our units. Here's an example where we have a couple of ingredients that probably shouldn't be represented by multiple nodes. We've got garlic cloves and minced garlic, cumin and cumin seeds, vegetable oil and oil. We've also got plain old garlic down there as well. So, in our first attempt at solving the potato, potato problem, we can see that by taking a naive approach to mapping these, we can eliminate the duplication, which unifies the nodes, but it also strengthens the relationships between the different recipes that have common ingredients. We'll explain why this is helpful later. The problem with this naive approach is that we've applied it retrospectively. And for this to work well, we'd have to know all of the ingredients ahead of time. Of course, these days, we have embedding models, which take the pain out of this sort of problem. And by using an embedding model here, we have not only more flexible matching, but we also have the ability to match on terms that we don't need to know in advance. This is a good example of where graph techniques and AI techniques working in hybrid give us the best result. So, now that we have a well-structured graph, we have nicely curated information put into that graph, and we've done extra work to make sure that the nodes are matched or the entities are matched before we create new nodes. Let's start talking about what we can do with our graph.
</details>

### 关系拓扑：图查询与个性化排序

相比于传统的关系型 SQL 查询，图形查询语言如 **Cypher**（Cypher: 专为图数据库设计的声明式图形查询语言）在处理多层关系遍历时具有压倒性的表达力优势。当查询深度达到 5 层以上时，SQL 的嵌套连接会导致性能雪崩且代码极难维护，而图查询则能以符合直觉的路径描述轻松解决。在此基础上，通过引入**个性化PageRank**（Personalized PageRank: 限制在特定起始节点进行随机游走的图排序算法），我们能够精准度量复杂网络中各节点与特定起点之间的相对紧密程度。该算法通过模拟“随机游走者”在标记节点后以一定概率传送回起点的机制，使与起点关系更深的节点脱颖而出。这种基于图拓扑的推荐模式已被广泛应用于 Pinterest 的 Pixie 系统以及最新的 **HippoRAG**（HippoRAG: 模拟人脑海马体记忆检索机制的图检索增强生成框架）中。以司法判例检索为例，即便某地标案卷未被直接引用，算法也能通过多级关联图谱自动识别其作为核心判例的权威地位。

除了评估节点之间的相对重要性之外，在复杂的系统网络中，探寻两个明确目标之间的具体通路也是一项极具实用价值的任务。

<details>
<summary>Original English Source</summary>
The very first thing we're going to do is just do a simple query to see which recipes contain the ingredient garlic. We've got the Cypher or graph database query on top, and the relational SQL query below just for comparison. Here we can see all the recipes that have garlic and their ingredients, which we print to the if they're fit on the slide. I think if you look at this example, you can see how out of hand the SQL query might get if we wanted to traverse 5, 10, 20 edges to find the nodes that we're looking for. In a graph query, not only is it a little bit easier and more natural to write, but traversing relationships like that is where the graph data structures start to inherently excel. Stepping things up a notch, the next graph algorithm we've got is the personalized PageRank algorithm. This is a variant on vanilla PageRank, which was made famous by a certain Brin and Page back in 1998. It works by having a little dude run around the graph, and he marks each node as he passes. After a certain amount of hops around the graph, he'll teleport back to the starting node. And that's the bit that makes it personalized. It's personalized to our starting node. By repeating this process until he's completely worn out, some nodes will emerge with more marks on them than others. These are the nodes that have a stronger relationship with the starting node than those around them. A really common and popular reference point for personalized PageRank is the Pinterest Pixie paper. How's that for some alliteration? Um that showed how PPR could be used for Pinterest recommendations. But, an even more contemporary one is Hippo Rag, uh which uses some other cool graph techniques as well to link memories to questions and answers. In the presentation pack, you'll find links and references to different variants and how they can be used. So, it looked a bit obvious in that last example. But, algorithms like this really shine when we have dense clusters of nodes and relationships, and it isn't that easy to infer which ones are the most important. Another real-world example is taking a real-world US Supreme Court case and being able to find the authoritative landmark cases upon which it relies. In this example, Miranda v. Arizona is not cited in the Canvas v. Sheba case. It's purely through the relationships in the citation graph that we are able to find it. Not only to find it, but to be able to return a string of citations that show how it is related to this existing case through another.
</details>

### 结构路由：最短路径与子图匹配

当我们需要在已知的两个节点之间寻找逻辑纽带时，**最短路径算法**（Shortest Path Algorithm: 寻找图网络中两点间距离最短或权重最低路径的经典算法）能提供极佳的上下文线索。在复杂的代码依赖网络中，当购物车（basket）构造函数变更导致结账（checkout）逻辑异常时，最短路径分析能够精准提取它们之间的依赖调用链路，并将其作为高价值上下文喂给大语言模型。实验表明，在 .NET 代码库的重构评估中，这一技术成功帮助 AI 代理减少了 40% 的代码搜索工具调用次数。不仅如此，利用**子图匹配**（Subgraph Matching: 在大图中寻找与给定模式图同构的子图的查询技术），我们可以在完全不知道具体实例标识的情况下，仅凭关系的“逻辑形状”（例如：两个类共同实现同一个接口且存在包裹关系的装饰器模式）检索出目标结构。这种基于拓扑形态的搜索方式在检测安全反模式、金融恶意交易流以及复杂法律论证链路中具有不可替代的价值。

综上所述，通过巧妙结合路径规划与拓扑匹配等底层图算法，开发者能够显著优化 AI 的上下文检索效率。展望未来，图的边界还将向更深层次的动态聚类与相似度预测延展。

<details>
<summary>Original English Source</summary>
Shortest path algorithm is another good way to look at the relationships between two nodes in a graph. In this case where we know both nodes in advance and we don't understand the relationships, we can look at the most direct route between them. In this case, if we say the checkout code broke after we changed the basket constructor, but I have no idea why, we can traverse the edges between those two nodes in the code graph and return either the symbols or the text or a summary as context. In this case, the shortest path is highly useful, but we might want the K shortest paths or the shortest path that passes through a particular node or the cheapest path if the edges are weighted. So, there are multiple variants and they're all very useful at telling us what nodes and edges might help explain the relationship between two other nodes on the graph. One of the benefits of this, being able to retrieve a subgraph as context, is that we wouldn't have found these intermediate nodes by doing vector search or even by doing individual symbol and reference lookups and the process of figuring that out for ourselves would have been slow. In one particular evaluation where we used this technique on a .NET code base, we saw a 40% reduction in tool calls for code search where we used techniques like this to identify the context we needed to give the agent. This is another eShop example. The one thing I like about this particular example is that instead of starting with a node or a set of nodes and navigating our way through the graph, we're querying entirely on relationships. We could specify a node type or a node ID in this query and it would still be a subgraph match. However, in In case, we're searching for code in a certain shape, not knowing anything specific about the code we're looking for or any symbols up front. We'll search for a decorator pattern in the eShop example, which is commonly used to enhance an existing class. So, what we're looking for is a class that wraps its target class or consumes methods from its target class, where both the wrapper and the target class implement the same interface. Boom. There we go. In our eShop code base, we found a catalog view model service and a cached version that calls the same class and implements the same API. If we knew we were looking for caching classes, we could have searched on that. But, if we're looking for a specific pattern or if we were looking for an anti-pattern or a particular type of security issue, a malicious transaction pattern, or legal arguments in a big corpus, sometimes it's really important to be able to look for the shape of something without knowing the specific instance or node details themselves. The benefits of subgraph matching, where you have the opportunity to use it, I think are quite unique. It's not so much an optimization problem as like a big enabling algorithm. It's something that's just not easy to do uh with other tools.

All right. So, we've covered a lot of ground. Thanks for bearing with me. We've looked at navigating paths, at ranking how important things are, and finding patterns. We've skipped over some of the traditional flow and cost and search algorithms that you might find often used in modeling dependencies or networks, and there's heaps of use cases of those, but I think probably a little bit more run-of-the-mill. In the presentation back, we'll also include some notes about some of the things that we couldn't get to today like prediction, similarity, and clustering. These are now edging into some of the graph rag, building dynamic graphs, or schema-less graph kind of territory that we deliberately didn't want to go into today, but it is also where things get super interesting as well. We'll have some references and some pointers in the presentation pack. Otherwise, you can go and explore some of those things on your own. So, I hope that some of these concepts will have given you some insight or inspired you and that you can take them and either use graph native algorithms or hybrid algorithms to help make smarter, cheaper, and more reliable AI applications. Thank you.
</details>