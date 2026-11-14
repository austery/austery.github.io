---
author: AI Engineer
date: '2026-06-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UM6sFg_jdlE
speaker: AI Engineer
tags:
  - agentic-search
  - rag-evolution
  - semantic-search
  - cache-compute
title: RAG已死？重塑“智能体检索”的底层架构
summary: 针对“RAG已死”的行业争议，Turbopuffer工程师指出传统向量检索正向迭代式的智能体检索演进。通过对比Cursor预索引技术与Cloud Code实时查找模式，本文深度解析了“算力即缓存”的架构价值，并强调在万亿上下文时代，轻量级阶段性检索仍是精准定位信息的刚需。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Cursor
  - Turbopuffer
  - Google
products_models:
  - Cloud Code
  - Composer
  - Gemini
media_books: []
status: evergreen
---
### 舆论背离：重构检索认知

演讲开场直击痛点，揭示了社交网络上关于“RAG已死”的流行叙事与真实技术趋势之间的巨大反差。

社交媒体上（特别是2025年底至2026年初期间）充斥着“RAG已死，我们只需要智能体文件搜索（Agentic File Search）”的断言。然而，Google的真实搜索指数却给出了截然不同的反馈：在经历2024年的平缓期后，关于RAG的搜索热度在2025年中期迎来了爆发式增长。这背后的核心原因在于，行业对RAG的理解过于狭隘——大众往往将RAG等同于单一的**向量搜索**（Vector Search），并将**智能体检索**（Agentic Search）粗暴地理解为单纯的文件系统Grep。但从**Turbopuffer**（全文本与向量搜索引擎）的工程实践来看，真正的RAG是一个多维组合，它不仅涵盖向量匹配，还包括BM25全文搜索、Glob匹配以及正则表达式。智能体检索的本质，是赋予AI一套丰富的工具集，使其能够渐进、迭代地定位并推理上下文，从而将碎片化的“查找”升级为具备认知深度的“探索”。

<details><summary>Original English Source</summary>
All right, welcome everyone. Thanks for coming out. I see it's a full room, so I appreciate everyone coming out. So welcome to the talk about rag is dead, right? So my name is Kuba. I'm deployed engineer at Turbo puffer. So for those that don't know what Turbo puffer is, we are a full text search and vector search database built from first principles on top of object storage. If you would love to learn more, I'll just come find me after the talk if you have any questions. So let's get started. So this talk I get is up sorry about how rag is dead, how hybrid tool tool rich retrieval is becoming a default for serious agentic search. 

So you guys have been on Twitter or other social media platforms or I guess X they call it now, you might have seen a lot of tweets like this about how rag is dead. You can see there's lots of tweets especially in the last you know in end of 2025 and in the early of this year about how you know rag is dead, agentic file search is all we need and there's kind of a a lot of tweet and a lot of kind of content about this now. But you know interestingly if you're to look at something like the Google Google search volume over the last 2 years or last couple years you can see that you know in 2023 kind of like AI starts we have the kind of this this you know increase kind of caps out a little bit in 2024 settles down for about a year and then about midway through 2025 we hit this new inflection point where search volume just goes through the roof. So take that Twitter.

So let's clarify first what is rag and what is agentic search. These are kind of the two terms a lot of people are throwing out these days. So rag what a lot of people think rag is is just simple vector search. They just think that this is just simply you know embedding a bunch of you know a corpus of contents passing an embedding vector and getting it back passing it through your LLM. And what I Turbo puffer what we think this actually means, you know if you break down rag into retrieval augmented generation, you know retrieval is not just vector search. It's a lot of different things. It could be vector search full text search using stuff like BM25, grepping, globbing, using regex, using other just basic filters. And the augmented generation is obviously just passing it into your LLM of choice.

And then agentic search. This is kind of the terms people are throwing out a lot these days. And generally when people start talking about agentic search what they usually talk about is essentially just file system grep. So if you guys are familiar with something like Cloud Code and kind of that's what Cloud Code Codex you know a lot of people call this agentic search and this just essentially is grepping through your file system and this is kind of why these terms are so correlated. And what we actually believe it is and you know kind of the definition we want to we want to give it is it's really giving the agents a set of tools to kind of progressively and iteratively find and reason over context. So with Cloud Code you can you know if you guys have are familiar with it it can read your file you start grepping through your file system read a file decide that it hasn't found what it needed what it what it needed to actually complete the task and it will you know find something again and then keep doing this until it's happy you know it's reached a happy state where it can continue on with the task.
</details>

### 架构博弈：算力即缓存

在打破刻板印象后，我们需要通过真实的工程案例，对比预先索引与实时遍历在系统架构与商业效率上的本质差异。

为了验证智能体检索的工程价值，我们可以解构**Cursor**（知名AI代码编辑器）与早期**Cloud Code**的两种技术路线。Cloud Code的早期架构依赖于基于会话的实时检索循环（即“Grep文件-阅读-评估”的无限重复），这导致了一个严重的问题：如果有10名开发者在10天里向AI询问同一个业务逻辑（例如“元数据过滤机制”），系统将被迫为每个会话重复执行完全相同的全量文件扫描与解析。这种高频重复的底层检索，极大地消耗了Token与算力资源。Boris Cherney（Cloud Code的奠基人）也曾提到，他们在早期确实尝试过基于本地向量数据库的RAG方案，但发现效果并不理想，才转向了这种文件抓取模式。

相比之下，Cursor采用了一种将“嵌入计算视为缓存”（Cache Compute）的先进工程策略。当开发者打开代码库时，Cursor会预先完成底层解析、分块（Chunk）和内容嵌入。更巧妙的是，他们引入了**默克尔树**（Merkle Trees: 一种基于加密哈希的树状结构）来精准计算团队内代码库的相似度。既然100人团队中99%的时间都在处理同一套代码，系统便能安全地复制和复用哈希一致的数据，仅对发生增量变更的文件进行重新计算。这种“一次性投入”换来了模型运行时的极速响应与轻量化查询，帮助其Composer模型在内部基准测试中实现了12.5%到24%的问答准确率飞跃；同时通过在线A/B测试证实了引入**语义搜索**（Semantic Search）能有效提高大型代码库的用户留存率（+2.6%）并降低不满意请求反馈（-2.2%）。正因如此，许多Turbopuffer内部原本使用Cloud Code的员工，都因为Cursor的极致速度和精准度选择了阵营转换。

<details><summary>Original English Source</summary>
So we're going to take a step back and talk about one of the companies that use Turbo puffer that we believe is doing an excellent job with agentic search. This is a company called Cursor you might have heard of them. Fun fact they're actually one of Turbo puffer's very first customers. And they have this excellent blog post that came out in the beginning of 2026 about how they index code bases. So for those unaware when you open up a new code base or new branch in Cursor what happens is that Cursor will start embedding your code base. So what they'll do is you know chunk out you parse chunk and embed your code base and make it available for semantic search. And this blog post goes into an excellent kind of excellent technical detail of how they do this. Just to give you the gist essentially the cool thing they do is that they found that you know most people working in a team let's say there's 100 engineers when they open up code bases they're normally the same code base you know 99% of the time because you have a team of 100 people most of the time working on one two maybe a few code bases, right? And it's really expensive to have to like re-chunk re-embed and re-upload these code bases every single time. So they essentially use like Merkle trees which essentially is this crypto hash tree to calculate similarities between code bases people open on the same team. And if they're similar enough they will essentially copy over the data and then only update the and re-chunk and re-embed the files that have changed and use Turbo puffer in order to make sure this is done securely. 

And yeah it's just excellent blog post. They they do some really cool stuff. And you may think like this is a lot of work. Why do they do this? Well the reason they do this is also covered in a in a different blog post about how they use semantic search. Again they use Turbo puffer Turbo puffer for this. And what they find is on average across models I think it's like a 12 and a half or 13 and a half percent increase in answer accuracy. This is in cross across their internal Cursor context benchmark. So you know not not a public benchmark but you can trust the numbers they give us. And you can see on on the right side their composer model so it's this this is before composer two they had a almost a 24% increase in answer accuracy. So giving semantic search to these tools and to these models is really can drive real performance gains. And you can see on on the bottom right this is from an online AB test they did which is also covered in their thing in in their blog post about how it's almost like a 2.6% retention code retention in large code bases and there's a 2.2% decrease in dissatisfied user request. And you may be thinking like oh well these numbers aren't that big like 2.6% 2.2% not that large but they also covered that semantic search isn't used in every single query. So in their online AB test you know if you give it if you give this tool to 100 query 100 random queries not every 100 query will actually benefit from the existence of a semantic search tool so that's why these numbers look kind of small.

And now let's talk a little bit about Cloud Code. So Cloud Code doesn't use vector search as covered by the tweet from Boris Cherney. So those unfamiliar with Boris he's essentially the founding father of Cloud Code. And he says that in early iterations of Cloud Code they actually did use rag in their local vector DB but they found that it just didn't really work out for them. But this is something that is important to understand is something we like we've kind of like taken on a lot internally understanding um here at Turbo puffer is this idea that like embeddings and semantic search are kind of cash compute. And you may be thinking like cash compute like kind of throwing out a lot of terms at me right now. Like I don't know exactly what that means. And I think it's like best to walk through an example of essentially almost like a Cloud Code looking trace and a Cursor looking trace. Of how how these agents will understand your code base. So on the left is kind of a per session discovery of Cloud Code. So for example if we're to ask the agent to understand how metadata filtering works what it have to do is grep read assess and repeat and try to find the files it needs in order to gain this understanding on a per session basis. So what this means is you could have you know 10 agents on 10 different days across 10 developers and you they can be asking the same question multiple times you know in day every day every time the agent's going to have to repeat these same exact steps to gain the kind of like same understanding of this code base. And this could you know cost quite a few tokens. You know 6,000 doesn't seem like a lot here but just remember this is like one sub step of an agent.

And then on the right is kind of like a more Cursor looking trace where there's this upfront cost of indexing but then we're able to allow for this like lightweight tool to help the agent kind of retrieve this information at runtime. So obviously there's this like upfront cost of parsing a code base embedding it and making it available but this is like a one-time cost and then at runtime the agent can just query something like how is metadata filtered? It can get some simple results and it would save a lot of tokens a lot of time and just a lot of money. And this just helps the agent to become a lot faster. You know a lot of people on the team now that maybe were big Cloud Code users here at Turbo puffer they've you know they've actually started switching to Cursor just because of how fast it's becoming especially with their composer two models and also this semantic understanding it's just become we're finding really really good.
</details>

### 终局跃迁：定位正确的百万

综合上述架构演进，我们最终会发现，无论是升级检索工具还是扩展模型窗口，其终极目标都是为了实现更高效的阶段性计算收敛。

当下的技术演进清晰地表明，2023年那种粗放式的“单次向量匹配后直接丢入提示词”的简单RAG确实正在走向终结。然而，那些更高级的客户并没有抛弃检索引擎，而是全面进化到了多步迭代的**智能体检索**（Agentic Retrieval）。在这个技术循环中，AI Agent会根据任务的实际需要，动态地执行语义检索或全文匹配，它们不再是机械地抓取文本，而是“为了深化理解而不断展开迭代搜索”。

Google的**Jeff Dean**（分布式计算及AI模型领军人物）在讨论**Gemini**（大规模多模态大模型）的超大上下文窗口时，曾一针见血地指出：无论你的系统是否拥有高达万亿级别的上下文窗口，你永远都需要**阶段性检索**（Stage Retrieval）。这是一种极其关键的轻量级过滤机制，它存在的意义不在于让大语言模型一次性吞咽下全部记录，而在于将这万亿规模的数据池，精确地收敛过滤到“**正确的那个百万**”（the right million）。这也正是构建现代底层数据库的核心哲学——当面对海量代码或语料时，真正产生体验护城河的，不再是你存下了多少TB的数据，而是你能否在微秒级别抽取出那十万、百万量级的高价值切片，为大模型的逻辑推理提供最核心的火力支援。

<details><summary>Original English Source</summary>
So from rag to agentic retrieval. Um So what we're finding now is that a lot of people are no longer doing the simple rag you know the the Twitter quote unquote rag of just doing vector search once and throwing it into the context windows. What we're finding is that this worked you know back in 2023 early 2024 at kind of the beginnings of AI but a lot of the more sophisticated customers are doing agentic search and it's giving like real real big performance gains and kind of unlocking like new products. Um And what we're finding is you know they're doing a ton of calls they're reasoning these agents are reasoning through several steps. They're searching semantically or through full text etc. as needed and they're only fetching what's needed for that specific specific use case but the important thing to know is that you know retrieval is no longer just this like simple one-time call to vector DB. It's becoming super iterative and these agents are really understanding what they're searching and searching to understand more in a sense. It's kind of like interesting loop. 

You know Google's Jeff Dean he went on a I forget if it was a show or podcast or whatever and he had this really good quote that we like to use that we also we thought was super interesting. He was talking a little bit about I believe about how Gemini's models were kind of having these really big context windows. Uh, I forgot the exact question the the host asked them, uh, but he was saying, you know, big context windows, it doesn't matter if you get to a trillion context window size, what you really need is stage retrieval, like a lightweight mechanism to narrow down these trillion tokens into essentially millions at a time. And like the exact quote is you don't need a trillion at once, you need the right million. Um, this is something we think a lot about Turbo here at Turbo Buffer. Um, you know, we have customers that embed, you know, have trillions of tokens inside Turbo Buffer, and as we see like the really important part is just getting down to this right 100,000, right 10,000, right million in order to pass into these context windows. Uh, that's about it for the talk. Um, if you have any questions about any specifics, I'd love to, you know, either have them ask now or you can find me after the talk. Uh, but appreciate you guys coming out.
</details>