---
author: AI Engineer
date: '2026-11-03'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=3Ad73Onx3Aw
speaker: AI Engineer
tags:
  - multimodal-search
  - retrieval-augmented-generation
  - vector-search
  - ai-agent
title: Mixedbread：以多模态检索与延迟交互重构智能体知识底层
summary: Mixedbread 创始人分享了传统 RAG 管道因解析、切块及单向量模型导致的信息严重丢失与高昂成本。通过自研多模态搜索模型、延迟交互机制与专有数据库，Mixedbread 支持直接基于页面视觉与多向量进行精准检索，使对冲基金智能体问答准确率从 36% 提升至 98%，同时将 LLM 消耗降低至三分之一。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Mixedbread
products_models: []
media_books: []
status: evergreen
---
### Mixedbread 创立背景与定位

[音乐]

在深入讨论有趣的内容之前，我先快速介绍一下 Mixedbread 以及我们在做的事情。Mixedbread 最初是一个专注于信息检索的研究实验室，因为我们当时对该领域的发展现状感到非常失望。在过去两年半的时间里，我们一直在研究如何将检索做得极其出色。最终我们打造出了一款产品，它可以摄取任何类型的数据并使其能够被智能体检索，这涵盖了超过 100 种语言的 PDF、电子表格、图像、视频和音频。

<details>
<summary>Original English</summary>
[music]

So quickly about mixread and what we're doing before I jump into the interesting things. So mixread started as a research lab around retrieval since we were really sad about the state how the space was evolving. So we have been doing research for the two and a half years over how we can make retrieval really really good and we come ended up with a product where you can ingest any kind of data and make it searchable for agents meaning PDF, spreadsheets, images, video, audio in over 100 languages.
</details>

因此，这是一种真正的多模态、多语言搜索，且模型是由我们自主拥有的。我们从零开始专为搜索构建了这些模型；我们构建了自己的数据库，以便能够提供零数据保留以及您所需的全部隐私要求；我们还构建了摄取管道，这样您就不必费心去管理摄取流程、管理 OCR 以及琢磨该怎么处理，而是直接将数据导入其中，依靠我们表现足够出色的模型，从而构建出极其强大的智能体。

<details>
<summary>Original English</summary>
So it's a true multimodel multilingual search where we are owning the models. So we built the models from scratch specifically for search. We build our own database so we can provide zero data retention and all the privacy privacy requirements you need and also we build injection pipeline so you don't have to hustle to managing injection managing OCR and knowing what to do and instead you just dump your data into it rely on our models working good enough and you know so you can build really really powerful agents
</details>

令我非常高兴的是，在过去的三个月里——虽然我们已经上线了 5 个月，但在过去的三个月里，我们将银行和对冲基金引入了 Mixedbread，它们带着数十亿份文档在系统上稳定运行。其主要原因在于我们完全符合 ISO 标准，并且提供了这种自带存储桶（bring your own bucket）模式，这意味着我们确实能在零数据保留的前提下满足您所需的所有安全合规要求。

<details>
<summary>Original English</summary>
and I'm really happy that over the last three months like we're live since 5 months but over the last three months we onboarded banks and hedge funds into mixread and alive with it with billions of documents and the main reason is we are so ISO compliant and we have this bring your own bucket mode meaning that we can really offer all the security requirements you need with zero data retention
</details>

### 金融分析场景中的传统检索瓶颈

因此，当我们谈论证据层或使用极其强大的智能体时，核心主要在于处理您自己的数据。假设您——不好意思，这个怎么翻到下一页——假设您正在构建一个智能体，或者您有一位股票分析师。这只是一个示例查询：因为英特尔昨天发布了他们的新 GPU 显卡，对吧？比如 D270，而且它的设计不知为何很奇特，使用了大量的 LPDDR5 内存。

<details>
<summary>Original English</summary>
so when we talk about evidence layer or using really really powerful agents right it mostly comes down to working on your data so if you have like oh sorry um how to move this forward so assume that you're building an agent or you have an equity analyst this is just like an example query because Intel yesterday released their new GPU cards, right? Like the D270 and somehow it has a really weird design that it's using a lot of LPDDR5 memory.
</details>

所以，作为坐在那里的分析师，您会纳闷英特尔为什么要发布这样的产品？为什么它配备了如此多的 LPDDR5 而不是 HBM 内存？于是您会向系统提出类似这样的问题：“嘿，为什么新的英特尔 D270 会使用 LPDDR5 内存？”而且因为大家可能在金融领域工作，你们拥有大量的数据经纪商和数据提供商，他们会向你们发送播客、访谈记录、各类材料和研究资料等等，因此你们拥有一个庞大的知识库。

<details>
<summary>Original English</summary>
So, you know, like you're an analyst sitting there and what the Why is Intel publishing this, right? Why why does it have so much LPDDR5 and not HBM memory? So, it would ask your system a question like, hey, why does the new Intel D270 use LDR5 memory? And since you guys probably as you're working in finance, you have a lot of data brokers and data providers. They send you the podcast, they send you interviews, they send you materials, research uh stuff and so on and so forth. So you have this huge knowledge base
</details>

现在您的分析师提出了这个问题。当您使用 Claude Code 或类似工具，且数据摄取在本地时，它通常的做法是通过终端以及类似 grep 的词法搜索来找出：“我们在哪里能找到像 LPDDR5、英特尔以及 GPU 这样的术语？”以此来查明哪些文档可能是最接近、最相关的。由于您拥有大量的 PDF、文档和访谈记录，您会得到大量的匹配结果，但没有任何相关性排序，您也不知道该去查看哪里。

<details>
<summary>Original English</summary>
and now your analyst is asking this question, right? So when you use cloud code or cloud cowwork, what it normally does when you have your ingest data locally, it uses the terminal and basically uh lexical search like grab to figure out, hey, where do we find terms like ADDPR5 or Intel and GPUs to just figure out, hey, what documents can be the closest and the most relevant ones? And as you have a lot of PDFs and a lot of documents and interviews, you will get a lot of hits and you have no relevancy and you don't know where to look into.
</details>

最终模型不得不做的事情就是去阅读每一份文档。这样一来，您的 Token 成本就会一路飙升；文档越多，单次查询可能最终要花费 10 美元或 20 美元，仅仅是为了问一个非常基础的问题。这种做法的第二个弊端在于，遗憾的是大多数 PDF 并不真正适合 grep 检索，因为它们是二进制格式，里面有时包含扫描件和图像，所以您根本无法利用其中蕴含的这些多模态数据来为您服务。这些都是关键的瓶颈所在。

<details>
<summary>Original English</summary>
So what the model will end up doing is reading every document and like this, you know, like your token cost will just go up and up and up and the more documents you have, you will end up with per query costing 10 or $20 to just ask a really basic question. And the second downside of that is also that most PDFs sadly are not really grapable because you know like there are binary formats sometimes there are scans in there images in there so you can't really exploit this multimodel data relying in there to work for you. So these are like the key bottlenecks
</details>

### “科学怪人”式传统 RAG 架构的固有缺陷

接下来您会思考：大家现在在做什么，以及大家之前在这个领域做过什么？在座有谁熟悉 RAG——检索增强生成（Retrieval-Augmented Generation）这个术语？请快速举一下手。我想大多数人都了解，所以我想接下来我要说的话会引起大家的共鸣。

<details>
<summary>Original English</summary>
and then you think okay what are people doing and what people have done previously in the spade space who's familiar with the term rack retrie augmented generation just hands up really quickly. So I think most people so uh I think you will it will resonate what I'm going to say now.
</details>

当时大家的心态就像是：好的，让我们构建一条复杂的管道，把所有这些数据真正为我们所用。我们拥有数十亿份 PDF、播客等等。我们做的第一件事就是解析，对吧？如果有音频，我们就做转录；如果有 PDF，我们就做 OCR。而其中的每一步都会引入噪声。如果表格处理不当，图表解析不当，结果就是信息直接丢失。接着您再进行文本分块（chunking）。

<details>
<summary>Original English</summary>
So then we were like okay good let's let's build a sophisticated pipeline where can make all this data really really usable for us. So we have this billions of PDFs podcast whatsoever. So first thing we do is we do parsing right. So if you have um audio we do transcription um if you have PDF we do OCR and what every of the step does it introduces noise. So if you can if you don't process tables properly, if you don't pass diagrams properly, what will happen is that you will just lose information and then you do the chunking.
</details>

因为表格没有被正确解析或者字符处理不当，您已经丢失了信息；接着您做分块，如果有插图、表格、页面，分块的边界究竟在哪里？这又引入了更多噪声。随后您将它交给一个纯向量嵌入模型，该模型接收这些信息，试图在空间中猜出一个点来代表这些信息。既然前面已经丢失了那么多信息，最终得到的就只有这么一个点。从极其丰富的信息退化成“这里只有一个点”，这是一个信息损失极其严重的过程。

<details>
<summary>Original English</summary>
So you already lost information because your table is not passed properly or characters are not processed properly, then you do some chunking, right? So if you have figures, table, pages, where's really the chunk boundary? So you're introducing more noise and then you're giving it to a pure embedding model which you know like takes this information and then tries to guess a point in the space to you know like what this information represents and since it already lost so much information you are losing then having this point right and this is then a super lossy process from going from this really rich information to hey here's just a point
</details>

然后您将它放入向量数据库，进行检索并重排。由于每一步都有损耗，而且每个环节都必须引入不同的供应商，您最终就会纠结：哪家是最好的 OCR？最好的分块策略是什么？最好的嵌入模型是什么？最好的向量数据库是什么？最好的重排算法是什么？于是您光是评估不同供应商并走完安全审批流程就要花上六到八个月才能上线，而且还得为此分配四到五个人手，仅仅是为了搭建出在我看来极其基础的东西。最终它还跑不通，因为这种处理方式存在某些固有的局限性。

<details>
<summary>Original English</summary>
and then you put it into a vector database do some retrieval and rerank. So since every step is lossy and you have to add a vendor for every process, you will end up hey what is the best OCR? What is the best chunking strategy? What is the best embedding model? Uh what is the best vector database? What is the best ranking? So you will just evaluate it for six or eight months different vendors run through security to just go live and you have to allocate four to five people to that to just build something from my perspective super basic which won't work in the end because there's some inherent limits of how this things are done
</details>

我们在内部称之为“科学怪人技术栈”（Frankenstein stack）。有充分的证据表明，单向量模型，或者将所有这些信息硬塞进嵌入模型并压缩成一个点的方式，在实际中根本行不通。如果大家感兴趣，我们稍后可以讨论原因，我也很乐意展开深入剖析。但这就是目前人们所使用的最前沿方案，这也正是刚才所描述的所有瓶颈所在，是 RAG 从未真正奏效的原因。

<details>
<summary>Original English</summary>
and we internally call it the Frankenstein stack and there like some proofs why you know like the single vector models or like just putting all this information into embedding model and one point actually doesn't really work and we can discuss it later if you guys are interested why and I can go on a rant and explain it a bit more in depth but this is actually right now the state-of-the-art what people use and this is also the reason like all the bottlenecks I described right now why rack actually never worked
</details>

我想大家都还记得曾经的许诺：“用 Pinecone 或任何向量数据库吧，把数据放进去就能直接见效。”但事实从未如此。归根结底是因为每一步都伴随着极其严重的信息损失，而且目前所采用技术构建的嵌入模型还不够优秀，导致您无法真正有效地利用这些信息。

<details>
<summary>Original English</summary>
so you know like I think you all remember this promise of hey here's spine cone or here's any vector database just put it in and it will just work but it never really worked out and it comes down to that every step is super lossy and that also the models we have the embedding models with the technologies they're using at the moment are not good enough so you you can't really use this information properly
</details>

### 单向量嵌入的表征困境与智能体成本膨胀

谈到这些嵌入模型时的缺陷，您可以设想一下它们是如何运作的：您有一条信息，比如“我爱吃面包”，放入模型后，模型接收该句子并将其投射在空间的某个位置；之后若有人询问“谁爱吃面包”，同样放入模型中投射在空间某处，然后在查询点周围搜索与其相似的点来完成表述。但现在我们来考虑一份财务报告，比如一份 SEC 申报文件。

<details>
<summary>Original English</summary>
and the downside when I talk about this embedding models is you have to imagine like how this embedding model work right you have an information like I love bread you put it into a model and then it just takes this information and puts it somewhere in the space and later if you ask hey who loves bread we'll put also into the model and we'll put it somewhere into space as well and then just search around the query. Hey, where's the similar point to basically describe that
</details>

如果您有一张包含净利润、营收等各类不同信息的复杂表格，这个向量点究竟代表了什么？它也许代表了关于英伟达的信息，是英伟达的财报；但如果您拿的是 1996 年、2000 年或 2026 年的财报，这些向量点看起来都会极为相似。这就是为什么当您面对大量形态相似的信息时，RAG 和所有这些向量数据库方案都会失效。我们在许多客户采用传统方案时观察到：如果只有几十、上百份文档，质量还算不错；但随着规模扩大并推向生产环境，回答质量就会发生断崖式下跌，因为这种类型的向量搜索和技术无法区分这些细粒度的信息。

<details>
<summary>Original English</summary>
but now let's think about a financial report like a sec filling. If you have like complex tables with all this different information like net income, revenue yada yada yada what does this point actually represent? Right? So maybe it uh represents information about Nvidia. So it's Nvidia's earnings report, right? But if you have the earnings report from 1996 or 2000 and 2026 the points will look really really similar. That's why when you have a lot of information which look very similar rack and all this vector database approaches don't work and we see with a lot of customers in their classic approach if you have just few documents let's say tens of hundreds of documents the quality is pretty good but as you start scaling and going into production the answer quality will just degrade significantly because this type of vector search and this type of technology is not able to really distinguish between this fine grained information
</details>

由此带来的问题是，您有一个一心想提供帮助的可怜智能体，它会竭尽所能为您服务并替您完成所有事情。那么这个智能体开始做什么呢？它会开始进行高频激进的查询，启动数十个子智能体，执行越来越多的查询，以此占满上下文窗口，导致每一次查询都变得昂贵无比。仅仅通过堆砌大量智能体确实可以解答问题，但问题在于：这真的是您希望推向生产环境的方式吗？如果想象在未来的某个时刻，您的基金或 VC 机构大部分由智能体驱动，智能体的流量规模不断攀升，运行这些系统的成本必将直冲云霄。

<details>
<summary>Original English</summary>
and the issue is you have a pure a poor agent, right, who wants to really help you. He he will do everything his to serve you and do everything for you. So what will this agent start doing? It will just query aggressively. It will spin up tens of sub agents. Um we'll do more and more queries. So you know it will just fill up the context window and every query will become expensive. You can answer it like this by just putting a lot of agents on that. But the question is hey is it really the way you want to go into production? If you also imagine at one point that maybe your fund or your VC will be mostly run by agents and the volume of agent traffic will just increase. So the cost of running the systems will just skyrocket.
</details>

### 解耦智能与数据：延迟交互多模态搜索模型

因此，我们在与客户合作的早期阶段就得出了结论：智能本身已经具备，真正的瓶颈实际上在于对自身数据和知识的访问能力。我们相信未来会看到智能与数据的解耦：您拥有智能层，可以在不同的智能模型之间自由选择；但您必须为这些智能模型配备针对自身数据的正确访问方式，从而实现效益最大化。为此，我们构建了 Mixedbread。

<details>
<summary>Original English</summary>
So this is why we came to the conclusion pretty early when we're working with our customers that intelligence is there but the real real bottleneck is actually access to your data and to your knowledge and we believe that we will see a unbundling of intelligence and data where you have intelligence where you can choose between different intelligence models but you need to have the right access for this intelligence for your data so you can make the most of that and for this we built um mix bread.
</details>

正如我前面提到的，Mixedbread 最初是一个研究实验室。这是一张非常有趣的图表，也是对下周即将发布内容的预告：它展示了从 1994 年到现在的检索演变历程，如果我心算没错的话，大约跨越了 32 年。我们最初使用的是 BM25，也就是 Elasticsearch 所采用的简单关键词匹配方式；随后我们开始研究更聪明的方法。第一批真正优秀的嵌入模型是在 2022 年发布的，也就是说该领域花了 27 年时间才在文本搜索上做出了超越 BM25 的成果。

<details>
<summary>Original English</summary>
So as I mentioned mixread started as a research lab and this is a really interesting graphic and this is a preview of what's coming next week. Um is that retrieval how it changed like over the last from 1994 to now it's like what 32 years I think my if my mental math is not wrong. So we started with BM25. This is what elastic search is doing like simple keyword matching and then we just started coming up with smarter method. So the first really good embedding models were published in 2022. So it took the space 27 years to come something up for text search better than BM25.
</details>

但自那以后，我们看到的更多是一种线性的改进，这也是我们所说的 RAG 为何没有真正奏效的原因，因为它从未经历过像 ChatGPT 那样的阶跃式质变。我们在去年年底完成了首个模型的训练，并于今年年初发布，其表现相当稳健。而我们下周即将发布、且已经向许多客户开放上线的成果，我们认为是一次阶跃式的质变，克服了前面所描述的大部分挑战。

<details>
<summary>Original English</summary>
But since then we have more like a linear um like improvement. And this is also what we meant with rack not working because there was never a step function change like we saw with chatbt and so and so forth and we published our first model by beginning uh we finished the training at end of last year published it beginning of this year it was pretty solid but the thing we're publishing next week and we already live with a lot of our customers we think is a step function change which overcomes most of the challenges I described before
</details>

简而言之，这是一个延迟交互（late interaction）模型。这意味着不再是将文档仅仅映射为一个嵌入向量，而是为您的文档生成多个嵌入向量，同时也为您的查询生成多个嵌入向量。通过这种方式，您可以真正细致地描绘页面上的细粒度信息。回到不同年份英伟达 SEC 申报文件的例子：模型会分别为净利润、净营收等信息生成嵌入向量；但由于它是一次性端到端生成的，它同时也知晓这是关于英伟达的内容。因此，每个嵌入向量都结合了上下文，并带有与您相关的完整信息。借助这项技术、模型规模的扩大以及更优质的数据，我们在质量上取得了显著飞跃。

<details>
<summary>Original English</summary>
just in short what this model does is it's a late interaction model Meaning instead of having just one embedding, you have multiple embeddings for your documents and you have multiple embeddings for your queries like this. You can really describe fine grained information on a page. So going back to the SEC filling for Nvidia for different years, right? So you would have the model would figure out an embedding for net income for net revenue etc etc but since it's like creating it in one pass it also know it's about Nvidia. So every embedding is contextualized and with the information which are relevant to you and all this technique and scaling up the model and better data gives us significant jump in quality uh which allows to do some cool things
</details>

这使我们能够构建出 Mixedbread 这款产品：您只需上传数据，Mixedbread 会负责为您建立索引，保留页面原本的视觉样貌，因为它是多模态的——我稍后会展示这意味着什么。接着您只需授予智能体访问 Mixedbread 的权限，智能体就会代您完成所有的查询、阅读与抓取工作，而您可以专注于真正有趣的事情，即构建实际的应用并创造切实的业务价值。

<details>
<summary>Original English</summary>
which allows to actually build this product uh mix where you just upload your data mix takes care of indexing it for you like every page as it looks because it's multimodel I will show what it means and you then just can give it agent access to mixread and the agent does the querying the reading the grabbing everything for you and you can just focus on on what's fun actually building the real application and actually building real RARI right
</details>

### 产品演示：多模态页面理解与智能体搜索

让我向大家展示这意味着什么。这就是 Mixedbread。我在这里做的是上传了一些英特尔的报告，例如英特尔的财报演示文稿。在 Mixedbread 中，您所要做的就是上传页面。这里的网络非常慢，我希望它能正常加载。因为网络慢加载失败了，对此我感到非常抱歉，我本该录制一段视频的。

<details>
<summary>Original English</summary>
so um let me show you what it means so this is mixre and what I did here is I uploaded some um Intel um wait hold on where is it exactly so I uploaded some Intel reports here for example the Intel earning stack so what you do in mix is just upload the uh page. The internet is pretty slow. I [snorts] hope it will be fine. So, it's it's failed to load because the internet is slow here. I'm so sorry about that. Um I should have recorded a video. Um so, let's do this. Cool.
</details>

好的，它展示的内容是这样的：我们这里有一张幻灯片，上面有一个图表。通常如果您只对图表进行 OCR，而您想了解英特尔在 2025 年第二季度的实际营收，纯 OCR 会丢失所有信息，永远无法真正匹配到该页面，因为系统需要理解上面到底在表达什么。但如果基于视觉感知来生成嵌入向量——即让模型直接观察该页面截图并据此生成嵌入——您就可以摆脱我之前提到的所有无用包袱。但考虑到并非所有大语言模型都是多模态的，Mixedbread 仍然为下游环节提供版面布局信息和 OCR 数据，以便您可以自行决定是传入截图还是纯文本来处理业务。

<details>
<summary>Original English</summary>
So, what it does here is so we have a slide. Come on, dude. So, you see there's a uh is there's a figure, right? So normally if you would just do OCR and the figure and you want to know the actually the revenue of Intel in Q2 2025 if you just would do OCR you would just all lose all information it would never really able to match the page because you need to understand what's going on there but if you create the embedding on the visual perspection like looking let the model look at the page the screenshot and create the embedding based on that you are getting rid of all this useless stuff I was talking before but since not all LM are multimodel mixread still provides stuff like layout information and OCR for your downstream thing where you can decide to put in the screenshot or the text yourself to do the right thing
</details>

让我们一起来实际测试一下。假设我们想了解：“英特尔代工业务（Foundry）部门在 2025 年第二季度的营业利润率是多少？”它正在执行查询。通常查询耗时在 200 毫秒以内，不过大家刚才看到了网络状况。可以看到，它找到了当前这个页面，内容涉及英特尔代工业务；往下拉，这里讨论了 2025 年第二季度，它同样理解这与部门营收相关，并且能够完整解析所有这些信息。

<details>
<summary>Original English</summary>
and let's just try it out together. So let's say we want to know hey what was in Intel's foundry segment operation mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar mar margin in Q2 2025 it goes out I hope it will work now normally it's like sub 200 milliseconds but you saw the thing before um so we see hey it finds somehow this page here which is talking about in Foundry and down here come on you can do it here you go it's talking about Q2 to 2025 and it understands also hey it's somehow about segment revenue and can really pass all this information
</details>

由于我们拥有视觉版面信息，我们实际上可以用边界框（bounding boxes）对其进行标注引用。当您的分析师或智能体得出结论时，您可以回溯并引用其信息出处。我们提供了所有的 API 和基础原语，供您自行构建这种体验。如果您有非常复杂的查询，例如想要了解偏定性的内容：“英特尔代工业务的盈利能力是否在改善？其推动因素是什么？”

<details>
<summary>Original English</summary>
and since we have this visual layout stuff we can actually reference this with bounding boxes and when your analyst or your agent is deriving to a decision you can actually backtrack and site where it is coming from and we're providing all the APIs and all the primitives for you to build this experience yourself and if you have like really really complex queries for example you want to know like something more qualitative Hey uh is Intel's foundry uh prof uh profitably improving and what is driving it?
</details>

比如当您提出这种查询时，我们的系统会识别出这是一个更复杂的查询，并转为执行“智能体搜索”（agentic search）。智能体搜索由我们训练的模型驱动，它就像一个能代表您执行多次查询与多跳推理（multi-hop reasoning）的智能体。它的表现与 Astra 和 Fable 一样出色，同时速度提高了 40 倍，成本也大幅降低。它会发散执行多次查询，完成深度拆解，并带回正确的数据。随后这些数据可以输入到大语言模型中，用以具体解释发生了什么。我们同样将该能力作为基础原语对外开放。这只是一个用于展示可能性的演示 Demo 与演练场，您可以直接使用它并交给智能体，让智能体根据复杂度自行决定是使用 grep、常规搜索还是智能体搜索。

<details>
<summary>Original English</summary>
So if you just query it for example our system realize hey this is a more complex query let's do a genetic search a genetic search is a model we trained toast one it's like a agent which does multiple queries for you multihop reasoning and it's as good as Astra and fable while being 40 times faster and cheaper which then goes out and does like multiple queries um and can really decompose everything and come back with the right data and uh this data can then fed into an LLM to actually explain what what what is happening there and we just also expose it as a primitive. This is just a demo, a playground to show you what's possible, but you can just use it, give it to an agent and let the agent decide if you want to use grab, normal search or the agentic search depending on the complexity. Exactly.
</details>

### 客户案例与落地成效

这就是备用方案，以防刚才现场演示无法正常运行。总之，智能体可以处理所有环节。这里有一个小型案例研究，我们也将在两周后正式发布。这是一家非常庞大的对冲基金，我们在大约一周半的时间内完成了入驻支持。他们目前拥有超过 10 亿份文档，正在为内部分析师和基金经理搭建大量的智能体平台，以推导定性分析并辅助做出决策判断。

<details>
<summary>Original English</summary>
And yeah, um so this is uh was as a backup if it wouldn't have worked. Um so the agent can do everything. And here a small case study which we will publish also in two weeks from now. It's like a really big hedge fund. We on boarded within like one and a half weeks. um because they have like over 1 billion documents right now and they are building a lot of internal agent platform for the analyst and for their fund managers to derive qualitative uh analysis and also come up with should we is it a good decision or not
</details>

此前他们搭建的正是前面提到的那一套管道：切块、嵌入、OCR、随机选取的嵌入模型以及向量数据库。经由人类专家知晓正确答案并打分评定，他们当时的智能体回答准确率只有 36%。而在迁移至 Mixedbread 之后，回答准确率直接跃升至 98%。因为核心问题再次证明并不在于智能本身，而在于获取正确的数据。

<details>
<summary>Original English</summary>
and before they have built what I described before this chunking betting OCR some random embedding model some vector database and they had a answer accuracy like how often the agent is right of 36% where the human experts knew the answer and graded And once they move to mix spread the answer accuracy moved to 98% because the again the issue is not intelligence it's again getting the right data
</details>

只要为您的智能体提供更出色的搜索能力：首先可以让智能体表现极为优秀。这里有多模态与纯文本问题的细分对比，正如大家所看到的，多模态直接带来了大幅提升；其次，Token 消耗量显著减少，大语言模型的开销降低了 3 倍。因为大部分 Token 原本都被浪费在查找、解析和阅读低效信息上。当您只输入真正精准的高质量上下文时，所需的 LLM 成本就会大幅缩减，大模型也能够专注于真正相关的内容。

<details>
<summary>Original English</summary>
and just by providing way better search to your agents you can first make it really good um here's a breakdown on multimodality and text questions and as you can see multimodality is just bumps it quite significantly but second is you use also wafier tokens so the LM spend is going down by 3x because again most of the tokens are used to find, pass, and read information. And as you just fit in really good context, you know, like you just need way less LLM cost and the LM can focus on what's relevant.
</details>

简而言之，这就是我的演讲内容。如果您想试用 Mixedbread，我们在楼下准备了传单，大家感兴趣可以去拿，我觉得内容挺有趣的。您可以直接注册，我们提供免费额度。如果您对安全性有顾虑，可以直接联系我们，我们能在 5 分钟内为所有客户开通自带存储桶模式，届时您就可以直接开始体验。如果您拥有非常庞大的语料库，我们还会提供大量免费额度，以便您在正式入驻前完成基准测试评估。

<details>
<summary>Original English</summary>
Um, exactly. So, this is my talk in a nutshell. Um, if you want to try out MixPread, uh, this we have toast, uh, flyers downstairs, so if you want to take them, I think they're pretty funny. Um, and you can sign up. We have free credits. Uh, if you are concerned about security, you can just write us. We activate bring on bucket within 5 minutes for all of our customers and then you can just start trying it and if you have like really large corpuses we provide a lot of free credits so you can benchmark it before really onboarding it.
</details>