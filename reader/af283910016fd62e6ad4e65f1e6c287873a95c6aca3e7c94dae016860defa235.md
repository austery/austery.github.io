---
author: AI Engineer
date: '2026-04-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=4TxOBhDRRCM
speaker: AI Engineer
tags:
  - rag
  - llm
  - document-processing
  - search-indexing
  - orchestration
  - agentic-retrieval
title: OpenRAG：构建强大、易用且可扩展的 RAG 系统
summary: 本次演讲介绍了 IBM 推出的开源项目 OpenRAG，旨在解决检索增强生成（RAG）系统构建中的复杂性。演讲者 Ash 探讨了 RAG 面临的挑战，如文档处理（PDFs）、嵌入模型选择和搜索技术的多样性。OpenRAG 整合了 Docling（文档处理）、OpenSearch（搜索索引）和 LangFlow（可视化编排）三大开源项目，提供了一个灵活且可扩展的 RAG 基础架构。该系统支持多种文档格式、嵌入模型，并采用代理式检索，允许用户深度定制以满足特定需求。OpenRAG 0.4.0 版本已发布，鼓励社区参与贡献。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - IBM
  - OpenAI
products_models:
  - OpenRAG
  - Docling
  - OpenSearch
  - LangFlow
media_books: []
status: evergreen
---
### RAG 的“死亡”与“已解决”之辩

大家好。我叫 Ash，是 IBM 的开发者关系工程师。在过去几年里，我一直致力于研究围绕 AI 和 **RAG（检索增强生成）**（Retrieval Augmented Generation: 一种结合了信息检索与生成模型的技术）的工具，今天我想向大家展示一些内容。

首先，我曾多次听说 RAG 已死，我相信你们也一样。如今，**上下文窗口**（Context Windows: LLM 可处理的输入文本长度限制）非常大，你们或许可以直接将所有信息都塞进去。我不认为这种说法有多大意义。如果每个企业的 GIGO 数据量都少于一百万 token，那或许 RAG 确实‘已死’，这些企业也可能如此。

当然，并非所有人都乐意每次提问都要为一百万 token 的输入付费。我更倾向于听到‘RAG 已死’的论调是说 RAG‘已解决’，对吗？我们认为我们已经理解了 RAG 的过程，并且可以在需要时应用它。你只需收集所有非结构化数据，提取文本，分块（chunk），嵌入（embed）它们，然后将其放入**向量数据库**（Vector Database: 一种专门存储和查询向量数据的数据库）。接着，当你需要向代理（agent）提问时，只需嵌入问题，搜索数据库，挑选出 Top K（前 K 个）结果，并将它们作为上下文传递给模型。在如今的上下文工程领域，这不过是‘沧海一粟’。

<details>
<summary>Original English</summary>

Hi there. My name is Ash and I'm a developer relations engineer at IBM. I've been working on tools around AI and **RAG (Retrieval Augmented Generation)** for the last couple of years and I've got something I'd like to show to you today.

Now first things first, I've heard that rag is dead many a time and I'm sure you have too. Context windows are huge these days, so you might as well just dump all of your information into there. I don't take this kind of thing very seriously. If every business has less than a million tokens worth of data then sure, rag is dead and probably so all those businesses.

Of course, like not everyone is happy you know paying for a million input tokens every time you want to ask a question as well. Instead I sort of hear that the rag is dead claims is more of more of rag is solved, right? We we think we understand the process and we can just apply rag when we need to. You just you know gather up all your unstructured data, extract the text, chunk it up, embed it, throw it into a vector database. And then when you want to ask your agent a question, you just embed that question, search the database, pick the top K results and pass them to a model as context. It's just a it's a footnote in in context engineering these days.

</details>

### RAG 的真实挑战：为何它比看起来更复杂

但事实证明，RAG 实际上很困难，并且由于不同项目的原因，它确实很困难。例如，**PDF**（Portable Document Format: 一种通用的电子文档文件格式）处理是一大痛点，分块策略（chunking strategies）更是令人头疼，修改和测试它们都十分困难。

**嵌入模型**（Embeddings: 将文本或其他数据转换为向量表示的技术）的不断改进对行业是好事，但对于六个月或一年前使用的嵌入技术而言，就没那么友好了。新的搜索技术层出不穷，你还可以在管道中添加各种优化（tweaks）来改进结果，比如：为分块添加摘要、执行分块扩展、使用交叉编码器（cross-encoder）来改写结果，或进行查询重写。RAG 的复杂性远不止于此。

事实上，每个人的文档都不同，每个系统都会有不同的用户、不同的问题、不同的交互模式和不同的期望。虽然每个 RAG 系统最终都会有所不同，但其中肯定包含一些核心组件是必需的。在构建 RAG 系统时，拥有一个高质量的基线（baseline）是十分有用的。

<details>
<summary>Original English</summary>

But it turns out that rag is actually hard and it's hard for different reasons for different projects. You know PDFs are a pain, chunking strategies are a hassle and changing them and testing them is difficult. Embeddings keep improving which is great for the industry but not very great when you've used something from a 6-month or a year ago. There are new search techniques all the time and further tweaks that you can add to your pipeline to improve the results like adding summaries to chunks, performing chunk expansion, using a a crossing coder to to rewrite results, query rewriting, there's there's so much more. Rag is quite complex. In fact, everyone's documents are different, every system will have different users, different questions, different interaction patterns and different expectations. While every rag system will ultimately be different, there are definitely some core components that are required. When building a rag system, it's useful to have a high-quality baseline to build from.

</details>

### OpenRAG：整合三大开源项目，打造 RAG 解决方案

这就是我们在 IBM 一直致力于的方向。我们整合了三个现有的开源项目，创建了一个功能强大、易于使用且易于扩展的 RAG 堆栈（stack）。这个项目叫做 **OpenRAG**。它利用 **Docling**（Docling: 一个用于文档处理的开源项目）进行文档处理，**OpenSearch**（OpenSearch: 一个开源的搜索和分析套件，是 Elasticsearch 的一个分支）进行搜索索引，以及 **LangFlow**（LangFlow: 一个用于 AI 流程的可视化编辑器）进行可视化编排（orchestration）和代理（agents）管理。

OpenRAG 是一个你可以立即开始使用的开源项目，用于构建你自己的强大、可定制且易于使用的 RAG 系统。我将为你分解这个堆栈，让你理解各个组件如何协同工作，并创建一个足以满足你现代 RAG 需求的灵活堆栈。

让我们从 RAG 的**数据摄入（ingestion）**端开始，从一切的起点——文档处理。摄入 PDF、HTML、Word 文档、幻灯片等都可能很麻烦，但其中最大的麻烦无疑是 PDFs。

<details>
<summary>Original English</summary>

So that's what we've been working on at IBM. We've brought together three existing open-source projects to create a rag stack that is powerful, easy to use and easy to extend. And the project's called open rag. And it uses the open-source docling for document processing, open search for search indexing and LangFlow for visual orchestration and agents. Open rag is an open-source project that you can try out today to build your own powerful, customizable and easy to use rag system. I just want to break down the stack for you so that you understand the components and how they work together and how they create a stack that is flexible enough for your modern rag requirements. Let's start by looking at the ingestion side of rag. Let's start where it all begins, document processing. Ingesting PDFs, HTML, Word docs, slides and more can be a pain but the biggest pain of all is is of course PDFs.

</details>

### Docling：强大的文档处理能力

**Docling** 是一个源自 IBM Research Zurich 的开源项目。它能处理和解析各种文档，包括 HTML、Markdown、Word 文档，以及幻灯片、电子表格、音频和视频，甚至包括 RAG 系统的‘敌人’——PDFs。

Docling 拥有多种不同的**管道**（Pipelines: 一系列按顺序执行的处理步骤），用于处理不同的文件类型。这使其在处理文档的方式上非常灵活，并在输出上非常精确。

*   **简单管道**（Simple Pipeline）：处理大多数直接的文本文档，如 Markdown、HTML 和 Word。它仅提取文本，将其转换为层级结构，并输出一个文档。
*   **音频与视频管道**：使用 ASR（Automatic Speech Recognition: 自动语音识别）进行处理。
*   **PDF 管道**：提供两种可用管道：
    *   **标准管道**（Standard Pipeline）：包含一系列小型、专注的模型，分别负责提取 PDF 中的文本、表格和图像。你甚至可以选择一个 **OCR**（Optical Character Recognition: 光学字符识别）后端来读取文本，这对于包含扫描图像而非实际文本的文档尤为有用。这个小型模型集合在管道中执行诸如布局分析、表格提取、图像提取描述等任务，为你提供了从文档中获取最佳信息的广泛选项。
    *   **VLM 管道**（Vision Language Model Pipeline）：使用 **Granite 258M** 视觉语言模型，一次性提取所有信息。这是一个较新的管道，但更简单，因为它是一个专为此任务训练的‘一体化’模型。

Docling 提取文本后，会生成一个中间表示，称为 **Docling 文档**，它以一种类似 XML 的格式（称为 **Doc Tags**）来模拟文档的结构。这些 Doc Tags 可以被转换为多种格式，包括 Markdown、HTML 和 JSON。Docling 还提供了一个**分块器**（Chunker），它利用暂停（pauses）生成的层级结构和内置的 Doc Tags 来生成具有层级理解的文本块。

<details>
<summary>Original English</summary>

Docling is an open-source project. It was built out of IBM research in Zurich and it processes and parses all sorts of documents from HTML, markdown and Word documents through to slides and spreadsheets, audio and video and even that enemy of all rag systems, PDFs. Docling has a number of different pipelines that handle different file types. This allows it to be flexible in the way it it takes in documents and accurate in its in its output. So there is a simple pipeline that handles those mostly straightforward text documents like markdown, HTML and Word. That just extracts the text, turns into a hierarchy and and outputs a document. For audio and video, there is an ASR and automatic speech recognition pipeline. And for PDFs, there's two available pipelines. The standard pipeline has a number of small focused models that do different things like extracting text, tables and images from PDFs. You can even choose an OCR backend to read text which is particularly useful for scanned documents that don't have actual real text in them. So this collection of small models in a pipeline perform things like layout analysis, table extraction, image extraction descriptions. This gives you a wide array of options to get the best out of those documents. There's also a VLM, a vision language model pipeline that uses the granite docling 258 million vision model to extract all of that in one go. This is a newer pipeline but it is simpler as it is this just all-in-one model that's that's trained specifically for this task. Docling extracts text and then produces an intermediate representation, a docling document which models the structure of document in an XML-ish format called doc tags. Those doc tags can then be converted to a number of formats including markdown, HTML and JSON. And the docling also has a chunker that uses the hierarchy generated generated by the pauses and and built into those doc tags to produce hierarchically understood chunks of text.

</details>

### 嵌入模型与索引：OpenSearch 的混合搜索能力

接下来谈谈嵌入（Embeddings）。OpenRAG 在嵌入模型方面并不‘教条’，它支持多种外部提供商，包括 **OpenAI**、What's Next AI，以及用于本地托管嵌入的 **Ollama**。事实上，OpenRAG 的整个堆栈都可以离线运行，使用本地托管的模型。Docling 本身就可以离线运行，因此可以适用于‘气隙（air-gap）’环境，无需外部服务。

一旦你嵌入了这些分块，它们就会被索引到 **OpenSearch** 中。OpenSearch 当然是 Elasticsearch 的开源分支，是一个强大的数据库，用于执行向量搜索和关键字搜索，同时也具备高度可配置的过滤和聚合功能。

开箱即用，OpenRAG 使用 OpenSearch 进行混合向量和关键字搜索，并提供复杂的过滤功能，以实现更精准的搜索。它还支持跨多个嵌入模型的向量搜索。虽然这可能会在实际应用中减慢你的向量搜索速度，但如果你决定在系统中迁移嵌入模型，这将非常有用。

OpenRAG 还集成了 OpenSearch 的一个‘秘密武器’——第四个开源项目。默认的 OpenSearch Nearest Neighbors（最近邻）插件提供了 HNSW（Hierarchical Navigable Small Worlds）或 IVF（Inverted File Index）向量索引选项，但 OpenRAG 默认使用 **JVector KNN** 插件。JVector 是一个开源的向量索引，提供实时索引，并且由于它基于磁盘 KNN 架构，意味着整个索引不必完全加载到内存中，为你提供了更多的扩展数据服务器的选项。

<details>
<summary>Original English</summary>

Moving on to embeddings, open rag actually isn't very prescriptive with embeddings at all. It supports a number of external providers including open AI, what's next AI and Ollama for locally hosted embeddings. In fact, the entirety of open rag can be run offline using locally hosted models. Docling itself can be run offline so it can run in air gap situations. It doesn't need those external services. Once you have embedded those chunks, they are indexed in open search. Open search is of course the open-source fork of elastic search and is is a powerful database for performing vector search and keyword search as well as highly configurable it also has highly configurable of filtering and aggregation. Out of the box, open rag uses open search for a hybrid vector and keyword search and exposes that sophisticated filtering for more targeted searching. It also supports vector search over multiple embedding models. Now this will slow down your vector search in practice but it is useful if you decide you need to migrate your embedding models as as part of your system. Open rag also sets up open search with a secret fourth open-source project. The default open search nearest neighbors plugin gives you options for HNSW or IVF vector indexes but open rag uses the JVector KNN plugin by default. JVector is an open-source vector index that gives you live indexing and because it's based on the disk KNN architecture means your whole index doesn't have to fit in memory giving you more options for scaling the data servers.

</details>

### LangFlow 与代理式检索：实现智能生成

所有这些最终都通过 **LangFlow** 整合在一起。LangFlow 是一个用于 AI 流程的拖放式可视化编辑器，它集成了 Docling、OpenSearch 以及所有这些嵌入模型，还能在摄入过程中和管道中进行进一步的数据丰富。稍后我们将更深入地探讨 LangFlow。

这就是摄入和索引部分。那么**生成**（Generation）端呢？
（>> [snorts]）
在生成端，我们通常不必担心摄入文档，并且我们已经知道 OpenSearch 正在为我们处理多向量混合搜索。但我们需要指出，OpenRAG 使用**代理式检索（Agentic Retrieval）**来执行搜索。这同样在 LangFlow 中完成，再次让你能够访问 LangFlow 提供的所有模型。开箱即用，这些模型主要是 OpenAI、Anthropic、Ollama 和 What's Next AI。

那么，代理式搜索意味着什么？传统的 RAG 生成管道会接收用户查询，嵌入它，用它在分块上执行最近邻搜索，并将 Top K 分块呈现给 LLM，希望答案包含在其中，并且模型足够智能可以提取出来。而在代理式检索中，我们转而将用户的查询连同它可以使用的指令和工具一起交给一个代理，让它执行任意次数的搜索。模型实际上负责决定执行哪些搜索以及如何处理结果。

<details>
<summary>Original English</summary>

All of this is then tied together with LangFlow. LangFlow is a drag-and-drop visual editor for AI flows and it integrates docling, open search and all these embedding models as well as further data enrichment as part of that ingestion process and pipeline. We'll come back and have a look more deeply into LangFlow later. So that's ingestion and indexing. What about the generation side of rag? >> [snorts] >> On the generation side, we we don't normally have to worry about ingesting documents and we already know that open search is handling that multi-vector hybrid search for us. Um but we do need to point out that open rag uses agentic retrieval in order to perform the search. This is also done in LangFlow and again gives you access to all the kind of models that LangFlow makes makes available to you. So out of the box, that's very much open AI, Anthropic, Ollama, What's Next AI. What does agentic search mean? Well, traditional a traditional rag generation pipeline would take a user query, embed it, use it to perform that nearest neighbor search over the chunks and present the top K chunks to the LLM hoping that the answer is contained within and that the model is smart enough to extract it. With agentic retrieval, we instead give the user's query to a to an agent along with instructions and tools that it can use to perform as many searches as required. The model is actually responsible for deciding what searches to perform and what to do with the results.

</details>

### OpenRAG 实操演示与高度可定制性

那么，让我们实际看看它的运行效果。我在我的笔记本电脑上运行了 OpenRAG，我们将快速了解它的功能。完成 OpenRAG 的**上手（onboarding）**过程并进行设置后，你会进入一个聊天界面。第一个可以问的问题是“OpenRAG 是什么？”。

正如你在此处看到的，它已经给出了答案，但你也可以看到它已经进行了一些工具调用。事实证明，“OpenRAG 是什么”这个问题的答案默认就在代理的提示（prompt）中，因此它实际上不需要进行任何搜索查询。但它确实获得了当前日期，这很贴心。我们可以看到它给出了答案，但也得到了一些关于下一步操作的建议。这些‘小提示’（nudges）也是由 LangFlow 驱动的。如果我们询问探索 LangFlow 在 AI 代理构建中的作用，那么代理本身就会去搜索相关文档并自行给出答案。

如你所见，模型，这个代理，又使用了一些工具。它给出了答案，还提供了更多提示。

让我们来看看‘知识’（Knowledge）部分。这是你实际上传数据、文档的地方。你只需添加一个完整的文件或整个文件夹即可。这里还有一个同步按钮，我们稍后会看到。你还可以查看你的对象、文档和分块。你可以看到它们正如你所期望的那样被分块了。这里也是创建**知识过滤器**（Knowledge Filters）的地方。这利用了 OpenSearch 中的过滤功能。你可以基于你系统中拥有的数据的多种不同选项创建过滤器。然后，这允许你在聊天中，使用这些过滤器，只与特定文档进行对话。

在‘设置’（Settings）部分，我们可以深入了解它的实际可定制性。最上面是**云连接器**（Cloud Connectors），但要使用它们，你需要一个用户模型或某种身份验证。目前我们使用 Google OAuth 设置。你需要一个 OAuth 客户端和密钥。一旦设置好，你就可以连接到 Google Drive、SharePoint、OneDrive。这使得你的用户能够连接到他们自己的文档目录，并允许 OpenRAG 直接同步它们。我认为这非常强大。它省去了你很多次上传的麻烦。你只需与这个外部文档存储同步，它就会始终保持最新。

在这里，我们可以看到我们的模型提供商。可以配置基于 API 的提供商，或者 Ollama。就像我说的，Ollama 是用于本地运行的。我正在运行 Ollama，可以看到我目前运行的是 Granite 4 3B，这是 IBM 的模型之一。这是我们的语言模型，你也可以看到实际的代理指令。你可以在那里设置你的**系统提示**（System Prompt）。

在‘摄入’（Ingest）部分，再次可以看到我正在为嵌入模型运行 Queen 3 embedding 0.6B，同样是在 Ollama 上。你可以设置你的分块大小和分块重叠（chunk size and chunk overlap）。最后这些是 Docling 设置，我们在此指定是否要捕获表格结构。是的，目前是。是否运行 OCR？目前没有，已关闭。是否要提取图片描述？目前也是关闭的，但如果你想从图片中提取信息，这是一个有用的选项。当然，添加更多模型会使过程变慢，所以它们目前是关闭的。

在底部是 API 密钥。你可以在这里设置 OpenRAG 作为 API 的访问权限，这样你就可以在你自己的应用程序中使用你的搜索或代理。

但是，让我们深入了解更深层次的细节，看看如何进一步自定义。你可以点击‘在 LangFlow 中编辑’（Edit in LangFlow）按钮，这将带你进入你的代理的实际实现。让我们放大一下。我们可以看到这是我们的代理，这是聊天，生成流程。我们的代理从这个聊天输入中接收信息，经过一个快速的提示模板，加入诸如知识过滤器（如果你已使用它们）之类的内容。然后，代理拥有一系列工具。这些工具包括：有一个用于 URL 摄入器的 MCP 服务器（这实际上是 LangFlow 内的另一个流程）。有一个计算器，因为我认为代理和模型不应该做算术。它们是语言模型，不是数学模型。所以，计算器总是有用的。最后，最后一个是 OpenSearch 多模型嵌入。嵌入提供商都在这里。我们可以编辑它。如果你进入此处并解锁流程并保存，我们可以做更多的事情。例如，我们可以获取这个聊天输入，我们可能想加上一些**护栏（guardrails）**。所以我们可以从左边的组件集里获取护栏。然后我们需要解析结果。所以我们可以得到一个解析器。如果解析通过，我们就将其传递给解析器，提取文本，也就是原始输入文本，然后将其传递给我们的提示模板。我想，如果失败了，我们可以向聊天输出发送一条错误消息。这没问题。现在我们为我们的东西添加了护栏。我们也可以在那里使用我们的 Ollama 模型。

而这就像 LangFlow 能为你提供的，一样可扩展。

还有最后一件事。OpenRAG 也有一个 MCP 服务器，可以作为 API 使用。所以你可以使用这个并将它提供给你的其他代理。

<details>
<summary>Original English</summary>

So let's actually take a look at this in action. I have open rag running on my laptop and we're going to have a quick look at what it can do. So once you've gone through the once you've gone through the onboarding process with open rag and setting it up, you get dropped into a chat and the first thing you get to ask is what is open rag. Um And as you can see here, it has got an answer but you can also see that it has done some tool calling already. It turns out that what is open rag the answer to what is open rag is inside the agent's prompt by default so it doesn't actually need to do any search querying. But it did go and get the current date just in case as well which is nice of it. So we can see we get an answer out of it but we also get these kind of suggestions about the next things. Those are a little nudges. That is also powered by LangFlow and if we if we were to ask about that to explore LangFlow's role in AI agent construction, then the agent itself will go off search that documentation and come up itself with an answer. So as you see, the model the agent has gone and used some tools again. It has come up with an answer. It's come up with more nudges as well. So let's go look at the the knowledge section. This is where you actually upload your data, your your documents and you can do so just by adding a whole file or whole folder. There's also a sync button here. We'll see that in a minute. And you can also inspect kind of your your objects and your documents here and your chunks. So you can see that they are chunking things as you'd expect. This also is where you can create knowledge filters. So um this takes advantage of that filtering in open search. You can create filters based on a whole bunch of uh different options around the data that you have in your system. Uh and then that allows you in chat to uh write use use those filters uh to only so talk to specific documents. Uh so that's knowledge section. Uh and then in the settings we can dig into the actual customizability of this. Uh so right at the top um there are cloud connectors, but in order to use cloud connectors you need a user model or some some authentication. Uh right now we set that up with Google OAuth. Uh so you need to need an OAuth client and a secret there. Once you have that involved, you can connect to uh Google Drive, you can connect to SharePoint, uh you can connect to OneDrive. And this allows your users to uh connect to uh directories of their own documents uh and allow OpenRag to sync them uh directly. I think that's really powerful. It saves you having to upload things a lot of the time. You can just sync with this external document store and it will always be up to date. Here we can see our model providers. Uh configure kind of API-based ones or Ollama. Uh like I said that's for for running things locally. Uh and I'm running Ollama and you can see I'm running currently Granite 4 3B. That's uh one of IBM's models. So this is our language model and you can see the actual agent instructions as well. Uh so you can set your system prompt there. And then in the ingest section uh you can see again I'm running Queen 3 embedding uh 0.6B for my embedding model. Also on Ollama. Uh and you can set your chunk size and chunk overlap. And then these last bits are uh Docling settings where we where we say do we want to capture table structure? Uh yes currently. Um do we want to run OCR? Uh not right now. That's turned off. Uh and do we want to extract picture descriptions? Uh currently that's off, but that's a useful one if you want to kind of get the information out of images as well. Of course adding uh more models uh to the pipeline makes things a little slower. Uh so they're off for now. And then right at the bottom there are API keys. And this is where you can set up access to OpenRag as an API. So you can implement you can use your search or your agent within your own application. Um but let's actually drop into uh under the hood even further where we can go and customize things even more. Uh you can hit this edit in LangFlow button and that will take you into the actual implementation uh of your uh of your agent. Uh and so let's actually zoom in. We can see here is our agent. So this is the this is the chat the generation flow. Um and our agent receives its information from this chat input uh which goes through a quick prompt template um adding in things about knowledge filters if you've used them. Uh and then the agent has a bunch of tools. Uh those tools include um there's an MCP server for a URL ingestor. That's actually just another flow within LangFlow. Uh there's a calculator because I think that um agents and and models shouldn't be doing arithmetic. They're language models, not math models. So uh a calculator is always useful. Uh and then finally the last one is the OpenSearch multi-model um embedding uh thing. And so the embedding providers uh are all here. Um we can edit this. Uh if you can go into here and just unlock the flow and save that, we can we can do more with it. Uh and so um for example, uh we can take this chat input uh and we might want to um might want to put some guardrails uh in place. Uh so we can grab guardrails from uh uh from our our set of components on the left. Uh and then we do need to parse the result of that. So we can just get a parser. Uh and so if it parses passes, we pass it through the parser, get the text out, which is the original text that was sent in, and then hand that on to our uh prompt template. I guess if it fails, we can send an error message to our chat output. Uh that's fine. Uh and so now we've added guardrails to our to our thing. Um we can use uh our our Ollama models there as well. And um and so this is as extensible as LangFlow uh as LangFlow can be for you. Um there's one more thing. Uh there is an MCP server available for OpenRag as well as an API. So you can go and use this and hand this to your other agents as well.

</details>

### 结论：RAG 是否已解决？OpenRAG 的价值

那么，RAG 是否已解决？这在很大程度上取决于你、你的数据以及你的用户。但 OpenRAG 的出现正是为了提供帮助。它是一个**观点鲜明**（Opinionated: 指在设计上预设了特定最佳实践或方法的）、**代理式**（Agentic: 指能够自主决策和执行任务的）且**开源**（Open Source: 指源代码公开，允许用户自由使用、修改和分发的）的 RAG 堆栈。

正如我之前所说，它结合了 Docling、OpenSearch 和 LangFlow，创建了一个强大的、由开源组件构成的基线 RAG 系统。它在堆栈内部留下了充足的定制空间，以便你能够为你自己的数据构建最佳的 RAG，并为你的代理提供最佳的上下文。

目前，它处于 0.4.0 版本，已准备好供大家试用。这个链接或二维码将带你访问该项目。我们非常希望你能试用 OpenRAG，在 GitHub 上点个 Star，并让我们知道你的想法。它也是开源的，对吧？前端是一个 Next.js 应用，其他一切都是 Python 应用。如果你喜欢 OpenRAG 的外观，我们也感谢你对项目本身的反馈和贡献。

当然，OpenRAG 的组件也是开源的。所以你也可以参与 Docling、OpenSearch 或 LangFlow 的开发。通过合作，我们可以构建一个适合所有人的 RAG 平台。它在你需要的地方提供选择，并在有意义的地方为你做出明智的决策。我们可以用开放的开源组件在开放的环境中实现这一点。这正是我希望看到的。

非常感谢你的聆听。我再次声明，我叫 Tom Nash，是 IBM 的开发者关系工程师，致力于帮助构建 OpenRAG 和这个开源的代理式应用生态系统。我们迫不及待地想看到你用 OpenRAG 构建出什么。非常感谢。

<details>
<summary>Original English</summary>

So, is RAG solved? Uh well, that's kind of still up to you, to your data, and to your users. Uh but OpenRag is built to help. Uh it is an opinionated, but agentic, and open source stack for RAG. As I said before, it combines Docling, OpenSearch, and LangFlow to create this powerful baseline RAG system made of open source components. And it leaves plenty of room to customize that within that stack so that you can build out the best RAG for your data and provide the best context to your agents. Uh it is currently at version 0.4.0 and uh it's ready for you to play with. Uh so this link or all the QR code will take you to the project. And we'd love if you try out OpenRag, uh drop a star on the GitHub, and uh let us know what you think. Uh it's also uh open source, right? Um the front end is a Next.js application. Everything else is a Python app. Uh and if so if you look like the look of OpenRag, we'd also appreciate your feedback and your contributions to the project itself. Um the components to OpenRag of course are open as well. So you can get involved with Docling, with OpenSearch, or with LangFlow as well. And together, you know, we can build a RAG platform that works for everyone. It gives you the choices where you need them and makes good decisions for you where it makes sense. We can do it with open source components out in the open. That's what I'd like to see. Uh so thank you very much uh for listening. Uh again, my name's Tom Nash. I'm a developer relations engineer at IBM trying to help build OpenRag and this open ecosystem of uh agentic applications. And we can't wait to see uh what you build with OpenRag. Thank you very much.

</details>