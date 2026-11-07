---
author: AI Engineer
date: '2026-05-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ns9f1fjLD7Y
speaker: AI Engineer
tags:
  - generative-ai
  - multimodal-models
  - prompt-engineering
  - open-source-models
  - agentic-workflow
  - ai-studio
  - model-deployment
title: 提示到管道：使用 Google 生成式媒体堆栈进行构建
summary: 本次访谈深入探讨了 Google DeepMind 在生成式 AI 领域的最新进展，重点介绍了 Gemini 系列模型、Genie 3 世界模型、Nano Banana 2 图像生成、LIA 3 音乐生成以及 Gemma 4 开源模型。演讲者们演示了 AI Studio 中视频分析、图像编辑、应用构建和实时对话功能，并展示了如何利用这些模型为书籍生成插图、视频和配乐。此外，还探讨了 Gemma 模型在本地设备和云端的部署与代理式工作流应用，强调了多模态能力和成本效益，并分享了开发实用 AI 应用的技巧。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Google DeepMind
  - OpenAI
  - Cloudera
  - GitHub
  - Chevron
  - World Labs
  - Augment Code
  - Project Gutenberg
products_models:
  - Gemini
  - Gemini 3.1 Flash Live
  - Gemini 3.1 Pro
  - Gemini 3.1 Flashlight
  - Nano Banana 2
  - Embedded 2.0
  - LIA 3
  - Genie 3
  - Gemma 4
  - VO3.1 light
  - TensorFlow
  - Numpy
  - SciPy
  - Matplotlib
  - Scikit-learn
  - Spark
  - VS Code
  - C-pilot
  - Palm 2
  - MedLM
  - MedPalm
  - LIA real time
  - LM Studio
  - Ollama
  - VLM
  - SG Lang
  - Open Duck
  - Android Studio
  - ADK
media_books:
  - The Wind in the Willows
  - Infinite Jest
status: evergreen
---
### 嘉宾介绍与职业发展

**Paige**: 我叫 **Paige**。我很久以前就开始做机器学习了，大概在 2009 年到 2010 年左右。主要从事一些工作，虽然感觉是很久以前的事了，我最近才和一个朋友聊起这个。在 2009 年到 2010 年，当时公司甚至会信任开源软件来做业务关键型工作，这有点疯狂。所以我当时为 **Numpy**、**SciPy**、**Matplotlib**（它现在用起来依然痛苦不堪）、**Scikit-learn** 等项目做贡献，这些都是科学计算堆栈的早期阶段。后来我开始做工程师。我的本科背景是地球物理学和应用数学，研究生是计算机科学和碳酸盐岩地质学。所以我从 **Chevron** 开始，从事地下地球科学工作，做了很多像速度建模、钻井优化之类的事情，使用的是非常非常基础的机器学习模型，还有一些大规模计算。所以，如果现场的观众也有像我一样的白头发，你们可能还记得 **Cloudera**，它是第一批提供开源框架和工具供财富 100 强公司使用的公司之一。像 **Spark** 这样的东西，很多 **Databricks** 团队都来自 **Cloudera**。我当时就在那里搭建机器集群。后来 **TensorFlow** 在 2015 年底左右开源发布了，我开始为其做贡献。地球科学领域对 **GPU** 的需求非常大，甚至在机器学习领域之前就已经在使用 **GPU** 了。所以我当时有使用 **CUDA** 以及所有相关工具的经验。**TensorFlow** 最初发布时只支持 **CPU**，我不确定这是否广为人知，但它当时是跨 **CPU** 的分布式深度学习，他们需要有人帮助让 **GPU** 与 **TensorFlow** 协同工作。这也是为什么最初的 **TensorFlow 1** 框架中有三种不同的代码路径，因为他们必须彻底改造后端，为 **CPU**、**GPU** 和 **TPU** 分别进行替换，包括单节点和跨多节点的分布式计算。所以基本上就是这样。我的整个职业生涯都归功于开源软件和开源模型。我就是因为这个原因被 **Google** 聘用的。然后我离开去了 **GitHub** 工作了大约一年，负责 **VS Code**（它也是开源的）和 **C-pilot** 的早期用户体验测试，之后又回到 **Google** 负责我们的大型模型。所以我是最初的 **Palm 2**、**Gemini** 和 **Gemma** 团队的成员。是的，这就是我的经历。我不确定，就像我说的，我不确定这是否有趣。

<details>
<summary>Original English</summary>

**Paige**: My name is Paige. I started doing machine learning a long time ago. Um around 2009 2010. Um was primarily working with um though it feels like forever ago. I was just talking with a friend about this recently. Um, back in 2009 2010, it was kind of wild that companies would even trust open source software to do business critical work. Um, and so I was contributing to things like Numpy, SciPy, like little like little antenna these microphones. Um, yeah. Sure. Cool. Cool. Um so Numpy, SciPy, uh Matplotlib, which is still just as excruciatingly painful to use. Um uh Scikit-learn, kind of the early days of the scientific computing stack. Um and eventually started working as an engineer. Um my background is geophysics and applied math for undergrad and then computer science and carbonate geology for grad school. And so I started at Chevron doing work in subsurface geosciences um doing a lot of things like velocity modeling, drilling optimization using very very basic machine learning models um and uh also some large scale compute. So, if folks in the audience um also have gray hair like me, you might remember Cloudera uh which was one of the first companies that made some of the open- source uh frameworks and tools available um for consumption of like Fortune 100 companies. Um so things like Spark um a lot of the Databricks team came from the Cloudera world. Um and so I was spinning up clusters of machines there. Um eventually TensorFlow got released in the open source world around 2015 towards the end of it. Um and I started contributing to that. Um the geosciences world is really big into GPUs. They were even into GPUs before um the machine learning world and um so so I had experience working with CUDA and and all of the the associated tools and TensorFlow when it was first released um only supported CPUs. I'm not sure how broadly that's known, but uh but it was like distributed deep learning across CPUs and they needed somebody to help with like getting GPUs um to to work with TensorFlow. Um that's also why there are three different code paths in the original TensorFlow 1 framework um because they had to like gut the backend and replace it for CPUs, for GPUs, and for TPUs both for single node and for distributed computation across multiple nodes. Um, so that's basically it. Like I owe my entire career to open source software um, and open source models. And I I got hired at Google for specifically that reason. Um, and then I left to go work at GitHub for about a year on VS Code, which is also open source, um, and early user experience testing for C-pilot, and then came back to work on our large models. Um, and so I was part of the original Palm 2, Gemini, and Gemma teams. Yep. So that is journey. I'm not sure. Like I said, I'm not sure. It's interesting.

</details>

**Paige**: 没错。**Guillaume** 会在这里。然后我们的同事 **Ian** 也可能会来。

<details>
<summary>Original English</summary>

**Paige**: Yep. And Gon will be here. And then also potentially uh potentially our colleague Ian will come to uh will come as well.

</details>

**Paige**: 是的。如果你好奇的话，开源是一个很好的方式，可以和团队一起工作，看看你是否想和他们一起工作，然后确保你的公开...

<details>
<summary>Original English</summary>

**Paige**: Yeah. Like if you're if anybody's curious like open source is a great way to like work with the team to figure out if you would want to work with them and then also make sure that your public

</details>

**Paige**: 猜猜你得了多少颗星。

<details>
<summary>Original English</summary>

**Paige**: guess how many stars you got.

</details>

**Paige**: 哇，太棒了，干得好。

<details>
<summary>Original English</summary>

**Paige**: Wow. Excellent. Good job.

</details>

**Paige**: 我正在追赶你们。对吧？就像他们，通常如果你看到每个人都在争先恐后地做同一件事，那很可能就错了。所以，就像，或者说模型最终会具备这种能力。所以，我最喜欢的一个例子是，当模型首次发布时，它们的上下文窗口只有 8000 个 token，16000 个 token，所以每个人都在争先恐后地构建 **向量数据库**，因为他们觉得“哦，我们必须解决模型上下文窗口很小的这个限制”，然后，你知道，随着时间的推移，这个限制显然已经扩大了。还有一个很好的例子是，每个人都在争先恐后地构建模型的 **微调版本** 来支持不同的语言。不过现在模型已经支持多种语言了。如果你今天一直在听 **Google DeepMind** 的一些会议，你就会看到这一点。而且我们的许多竞争对手模型也支持多种语言。所以我觉得，我们当时也看到每个人都在争先恐后地构建 **代理框架**，而现实是，我认为所有这些最终都可能会被模型吸收。而且每个人都在争先恐后地构建 **MCP 服务器** 之类的东西，而现在大多数人已经不再使用 **MCP 服务器**，而是采用 **技能**，这只是一些花哨的 Markdown 文件。然后显然从长远来看，你可以想象，哦，我只是想要一个小小的监听器，它能观察我所做的一切，然后自动在幕后为我创建可用的技能。我们正在开始。是的，是的。

<details>
<summary>Original English</summary>

**Paige**: right? Like they're um usually if you see everybody sprinting to do the same thing, that's a great indication that it's the wrong thing. Um and so so like as or or like a thing that eventually the model will will have that capability to do. Um so so one of my favorite examples of this is that um you know when the models were first released they had context windows of like 8,000 tokens 16,000 tokens and so everybody was sprinting to build a vector database um because they were like oh well we have to work around this constraint that the models have this very small context window um and then you know obviously that's expanded over time. Um there's another great uh example of you know everybody sprinting to build fine-tunes of models to support different languages. Um though now models support a variety of languages. If you've been uh kind of listening along for some of the Google DeepMind sessions today, you've seen that in action. And then also many of our competitor models also support multiple languages. And so I think like we we also saw everybody sprinting to build an agent framework when the reality is I think that the m like all of that will probably be absorbed into the model eventually. Um and also everybody sprinting towards things like building MCP servers whereas now mostly people have kind of moved away from MCP servers and are adopting skills which are just fancy markdown files. Um, and then obviously longer term you could imagine like, oh hey, I just want a little listener um, watching everything that I do and it will automatically create skills behind the scenes for me to use. And we're starting. Yep. Yep.

</details>

**Audience**: 我要说的是，我不一定同意，因为你们总是会满足大多数应用的需求，但对于非常非常具体的应用，比如我正在从事的领域，**Google** 不会去开发。所以那些类型的...

<details>
<summary>Original English</summary>

**Audience**: I was going to say I do not necessarily agree because you guys will always cater the most applications but very very specific ones like for instance which is where I'm working Google is not going to work on that. So those kind of

</details>

**Paige**: 所以，所以反例是，我们第一次实现 **Palm 2** 和 **Gemini** 时，我们不得不进行微调，一个叫做 **MedLM**，一个叫做 **MedPalm**，以支持医疗用例。现在我们看到，所有以前需要依赖这些微调的人，都直接使用开箱即用的 **Gemini**，通过检索或自定义提示，因为我们用于这些微调的所有数据都已整合到 **Gemini** 本身中。

<details>
<summary>Original English</summary>

**Paige**: so so counter counter example um our first implementation of Palm 2 and our first implementation of Gemini we had to have a fine-tune one called MedLM and one called MedPalM to support medical use cases. Um, now we see that all of the people who had previously needed to rely on those fine-tunes are just using Gemini out of the box with either retrieval or with a custom prompt because all of the data that we used for those fine tunes is just incorporated into Gemini itself.

</details>

**Audience**: 但你面临可复现性问题。你不会得到相同的结果。你会遇到很多...后果。

<details>
<summary>Original English</summary>

**Audience**: But you have the issue of reproducibility. You're not going to have the same results. You're going to have a lot of consequence.

</details>

**Paige**: 所以，所以没有大型语言模型是确定性的。所以无论如何这都会是一个问题。但我确实同意，我认为很多魔力将来自于对用例有非常明确的看法，并能够直接与客户合作解决他们的问题。所以，这完美地引出了今天的会议。大家好，感谢大家勇敢地回来。我知道今天早上我们的一些会议有很多人无法参加。所以，请举手示意一下，今天下午回来的有多少人早上没来，或者，嗯，太棒了，很好。所以，我们今天为大家准备了一份大礼。对于我们之前进行的会议，我们基本上会做一个回顾。所以，我们会逐一讲解所有例子。你们不会觉得错过了什么。我会在 **AI Studio** 和 Anti-Gravity 中做一些演示。然后我的同事 **Guillaume**，你也可以看到我的一个代理正在用电脑和浏览做它的事情。嗯，我将断开连接一秒钟，这样我们就不会不小心看到一些可能不应该分享的东西。然后，我将直接进入幻灯片视图。

<details>
<summary>Original English</summary>

**Paige**: So so no large language model is deterministic. Um so so that will be a problem regardless. Um but I but I do agree like there there are um you know I think a lot of the magic is going to come from having like a very opinionated view of use cases um and being able to work directly with customers and solve their problems. Um so with that and that's a perfect segue into uh into the session today. So greetings everyone. Thank you for being brave and for coming back. Um I know that there were a lot of people who were uh unable to to join us earlier this morning um for some of the sessions that we had. Um so just show of hands how many folks came back this afternoon were not here this morning or uh like were uh cool cool. Excellent. So uh we have a treat for you today. Um for the sessions that we delivered earlier um we're going to do basically a recap of them. So, we'll be walking through all of the all of the examples. Um, you won't have uh you won't uh uh kind of walk away feeling like you've missed anything. Um, and uh I'll be doing some within AI Studio and anti-gravity. Um, and then my colleague uh my colleague Gom and you can also see one of my agents that's kind of doing its thing with computer use and browsing. Um uh the uh I'm going to disconnect for a second so we don't accidentally see something that perhaps should not be shared. Um and then uh going to go straight into slideshow view.

</details>

### Google DeepMind 最新模型发布

**Paige**: 太棒了。大家好，我叫 **Paige**。我今天能来到这里感到非常兴奋。我特别高兴能向大家展示过去一年，嗯，过去六个月，我们在 **Google DeepMind** 所做的一切。这是一段疯狂的旅程，在我的职业生涯中，我从未如此兴奋能成为一名在这个领域工作的机器学习工程师。就在过去一个半月里，感觉有点像急转弯。我们发布了大量不同的东西。比如 **Gemini 3.1 Flash Live**，我们稍后会看一眼，它让你能够与模型进行实时对话。**Gemini 3.1 Pro** 和 **Flashlight** 分别是我们最大和非常小但能力很强的模型。它们也非常经济高效，性能也很好。**Augment Code**，如果你听说过他们，他们是湾区的一家公司。他们最近刚刚重新规划了整个代理基础设施，默认使用 **Gemini 3.1 Pro**，正是因为其性能和成本比。它能以非常低的成本完成很多非常好的工作。还有 **Nano Banana 2** 用于图像生成、图像编辑，包括反向图像搜索，我们稍后也会看一眼。你们会从我的同事 **Guillaume** 那里听到更多，他是我们生成式媒体的专家。我们的 **Embedded 2.0** 模型允许你在同一个嵌入空间中嵌入视频、音频、图像、代码和文本。所以你可以说“给我看所有与羊驼相关的东西”，然后你就会看到从毛绒羊驼到羊驼图片，再到羊驼视频，以及羊驼发出声音是什么样的，因为我不知道，但模型 somehow 知道。**LIA 3** 用于音乐生成，**Genie 3** 用于世界模型构建，我们的全栈运行时 **AI Studio** 允许你集成数据库 **OOTH**。如果你想使用其他服务，还可以自定义 **API 密钥** 和许多其他功能。**Gemma 4** 用于开源模型。我们上周刚刚以 **Apache 2 许可证** 发布了它，如果你关心开源模型，这非常令人兴奋。然后还有 **VO3.1 light** 用于视频生成。所以，我们在广泛的领域发布了大量产品。部分原因是因为 **Gemini** 在行业中有几个独特之处。其中之一是它天生就是多模态的。所以它能同时理解视频、图像、音频、文本和代码，以及以上所有。但它也能输出多种模态。所以它能输出文本，能输出代码，就像市场上所有其他竞争对手一样。但它也能输出图像，能编辑图像，能交错输出图像和文本，还能输出音频 token。所以，嗯，用例非常引人注目。但我认为亲眼看到它比听我滔滔不绝地赞美它更有趣。为此，我将快速进入 **AI Studio**。我们将看看 **Gemini** 能做些什么。

<details>
<summary>Original English</summary>

**Paige**: Awesome. So uh greetings everyone. My name is Paige. Um so I I am really excited to be here today. Um, and I am especially excited to show you all of the things that we've been doing at Google DeepMind over the course of the last year, um, last, uh, six months. Uh, it's been a wild ride and never in my career have I been more excited to be a machine learning engineer working in this space. Um, just over the last month and a half, uh, it feels a little bit like whiplash. Um, we've released a ton of different things. Um, so Gemini 3.1 Flash Live, um, which we'll take a look at in a second, uh, which gives you the ability to have a real-time conversation with the model. Um, Gemini 3.1 Pro and Flash Light, um, respectively, our largest and our very, very small but very capable model. Um, that are also very coste effective, very performant. Um, Augment Code, if you've heard of them, they're a company over in the Bay Area. They've just recently replatted their entire agent infrastructure to default to Gemini 3.1 Pro specifically because of performance and cost ratios. Um it can do a lot of really good work in a very like um small number of pennies. Uh also Nano Banana 2 for image generation, image editing, including reverse image search, which we'll also take a look at in a second. Um and you'll be hearing about from my colleague Guom, who's our expert in generative media. um our embedded 2.0 model which allows you to embed video, audio, images, code, and text in the same embedding space. Um so you can say like show me everything you have related to llamas and you will see everything from um like stuffed llamas to pictures of llamas to videos of llamas to things of like what does it sound like when a llama makes noises cuz I don't know but like the model the model somehow does. Um, LIA 3 for music generation, Genie3 for world model building, um, our full stack runtime with AI studio which allows you to incorporate database OOTH. Um, a custom API keys if you want to use other services and a whole bunch of other things. GIMA 4 for open models. Um, we just released it last week under an Apache 2 license which is really exciting if you care about open models. And then also VO3.1 light for video generation. Um so massive number of things across a broad spectrum of surfaces. Um and part of the reason for this is because Gemini is kind of unique in the industry in a couple of ways. One of which is that it's natively multimodal. So it can understand video and images and audio and text and code and all of the above all at once. Um but it can also output multiple modalities. So it can output text, it can output code just like all of the other competitors on the market. Um, but it can also output images, it can edit images, it can output images and text interleaved and it can also output audio tokens. Um, so uh, so pretty pretty compelling use cases. Um, but I think it's a lot more interesting to see it rather than to just have me waxing poetic about it. Um, and for that I am going to go into AI studio real quick. Um, and we're going to take a look at some of the things that Gemini can do.

</details>

### AI Studio 视频分析演示

**Paige**: 首先，有多少人用过 **AI Studio**？太棒了。我很高兴所有的 DeepMinder 都举手了。但是，对于那些没用过的人，**AI Studio** 是第一时间获取 **DeepMind** 模型发布的最佳平台。我们有一个 Playground 功能。我们还有一个 Build 功能，我们稍后会看到，它与 vzero.dev 或 Lovable 非常相似。你可以在右侧选择不同的模型。所以你可以看到，如果我点击模型名称，我们会看到一些选项，从 **Gemini** 到实时功能，图像生成、视频生成、音频生成和音乐，然后还有我们的 **Gemma** 开源模型家族，我们稍后也会看一眼。你可以选择不同的模型，为了速度，我选择了 **Gemini 3.1 Flashlight Preview**。我还在我的个人 **AI Studio** 实例上，这是为了降低成本。所以 **Gemini 3.1 Flashlight** 分析每百万 token 大约 25 美分。这非常好。比我们的 **Gemini 3.1 Pro** 模型低了几乎一个数量级。它仍然可以分析视频、音频等。它只是更轻量级，这意味着你可能无法总是获得同样出色的功能。但它通常做得很好。你可以做从分析图像到分析视频的各种事情。所以，举个例子，如果我要查找一个恐龙 YouTube 视频。我们之前已经用过这个小霸王龙 Rexy 了。所以我知道它能用。但是，我将找到，也许是这个，Carnotaurus，它看起来是一个非常非常长的视频，大约一个小时。我们可能会稍微剪辑一下。但是如果你点击这个加号，你可以看到你可以添加不同的文件。所以你可以从 **Drive** 添加文件，从文本文件到 PDF。你可以直接上传文件。你可以实时录制音频。添加摄像头素材。添加 YouTube 视频链接，我们现在就来做。所以我粘贴了 YouTube 视频的链接。我将开始时间设为 0 秒，结束时间设为大约 300 秒。它以每秒一帧的速度采样。然后你看到的是，这是 30,000，嗯，30,900 个 token。我将确保在右侧打开 **Google 搜索** 基础功能。然后我会说：“请创建一个表格，包含视频中所有恐龙种类的时间戳。确保包含每种恐龙的一个有趣事实。”对于房间里所有其他的恐龙专家，嗯，像业余恐龙专家，你们可能已经注意到它说的是 Carnotaurus。我怀疑那是不是一种真正的恐龙。所以，嗯，我们拭目以待。但是，幕后发生的事情是，模型正在接收这个 YouTube 视频进行推理。它不仅仅是 YouTube 视频相关的元数据，它还是逐帧的视频本身。

<details>
<summary>Original English</summary>

**Paige**: Um, so first off, how many people have used AI Studio before? Um, excellent. I'm very very glad that all of the Deep Minders have raised their hands. Um, but, uh, for folks who have not, uh, AI Studio is kind of the best place to go to get access to DeepMind's models as soon as they're released. Um, we have a playground feature. We also have a build feature, which we'll see in a second, which is very similar to vzero.dev or lovable. Um, you can select different models here off to the right. Um so you can see if I click on the model name um we see some pills um everything from Gemini to live capabilities um image uh image uh generation video generation audio generation and music um and then also our Gemma open model family which we'll also take a look at in a second. Um you can select different models for the purposes of speed I am selecting Gemini 3.1 flashlight preview. I am also on my personal instance of AI Studio and this is an attempt to drive down costs. Um so Gemini uh 3.1 flashlight is around 25 cents per million tokens analyzed. Um which is really really good. Uh almost an order of magnitude lower than our Gemini 3.1 Pro model. Um and it can still analyze video, audio, etc. um uh it's just uh a lot more lightweight, which means that you might not always get the the same great capabilities. Um but it usually does a pretty good job. Um and you can do everything from analyzing images to analyzing video. So if I as an example um was going to look up a was going to look like a dinosaur YouTube video. Um we already used this Rexy the the little T-Rex before. Um so I know it works. Um but uh but I am going to find um maybe this one uh carnado uh which is

</details>

**Audience**: 呃，就像，呃，还有其他人有，呃，还有其他人有看不到设置的问题吗？或者说，呃，我们能，我们能改变一下灯光吗？哦，这样好些了吗？

<details>
<summary>Original English</summary>

**Audience**: um like uh does anyone else have uh does anyone else have issues with seeing the settings or like uh could we could we change the lighting? Oh, is this better?

</details>

**Paige**: 哦，太棒了。很好。嗯，所以，所以，谢谢你的要求。就像，我，我确实能在我的屏幕上完美地看到它。通常我的眼睛会被亮色模式刺激到，但只要这样好些就行。所以，嗯，它接收了视频。它识别了它看到的各种恐龙。它说这个名字的意思是“调解公牛”。提到了 **三角龙**。然后还提到 **翼龙** 不一定是恐龙，它们是一群会飞的爬行动物。然后，如果我想获取用于生成这种体验的代码，并且我想在自己的应用程序中复制它，我所要做的就是点击“获取代码”，它就会自动配置模型。它会配置我输入的 URL，视频的偏移量，我使用的提示，而且它是用 **TypeScript**、**Python** 或你喜欢的任何语言编写的。所以，TLDR（太长不看）就是，如果你能在 **AI Studio** 中让它工作，你就能让它在你的应用程序中工作。你所要做的就是点击“获取代码”按钮。

<details>
<summary>Original English</summary>

**Paige**: Oh, excellent. Awesome. Um, so so that's uh thank you for thank you for the request. Like it's I I did I can see it perfectly on my screen. Usually my eyes get a little irritated by light mode, but this is um as long as it's better. And so um so it took in the video. Um it defined the different dinosaurs that it sees. Um it says that the name means mediating bull. Um mentioned triceratops. Um, and then also mentioned that pyranodons are not necessarily dinosaurs. They're a group of flying reptiles. Um, and then if I wanted to uh if I wanted to get the code that was used to generate this experience um and I wanted to replicate it in my own app, all I have to do is click get code and it automatically configures the model. Um it configures the uh the URL that I have inputed um the kind of the offset for the video the the prompt that I used um and it's in Typescript, Python or whatever your favorite language might be. So the TLDDR is that if you can get it working in AI Studio, you can get it working as part of your app. All you have to do is click the get code button. Um

</details>

### AI Studio 图像分析与代码执行

**Paige**: 所以，这就是用于分析视频的 **Gemini 3.1 Flashlight**。你也可以用它来分析图像，并结合其他内置工具。如果我们看右边，可以看到结构化输出、代码执行、函数调用等功能，甚至可以用于自定义函数。还有一些像 URL 上下文之类的东西。所有这些都非常特别，但如果你想在 **API** 中使用它们，它们也只是一行代码。所以举个例子，如果我打开代码执行，我将看到 **Gemini 3.1 Flashlight** 被选中，我将进入比较模式。所以我想将它与 **Gemini 3 Flash Preview** 进行比较，也打开代码执行。我将寻找一张乐高积木的图片。这张。然后复制图片。现在我们处于比较模式。所以我正在比较两个不同的模型，都打开了相同的工具。然后说一些类似“使用 **Python** 在所有绿色乐高积木周围绘制 **边界框**”的话。确保，或者显示带有边界框的图像。代码执行就像是赋予 **Gemini** 建立一个沙盒化的临时 **Python** 环境的能力，使用大量预装的数据科学库，并将其作为工具调用来调用，就像编写代码并整合你可能分享的任何内容一样。所以，我分享了这张图片，而且非常非常快，我不确定你是否看到了有多快，但它能够围绕绿色乐高积木绘制边界框，你也可以要求 **分割掩码**。更令人兴奋的是，**Gemini 3 Flash** 仍在努力工作。但是如果你看看绘制边界框的成本，你也可以问一些问题，比如“告诉我有多少个绿色乐高积木”或者“告诉我乐高积木的方向是什么”。“告诉我，呃，有多少个，你知道它们叫什么吗？那些有趣的小兔子，Laboo。告诉我你在这个视频的所有帧中看到了多少个？”以及在什么时间戳，这些都是可以通过沙盒环境调用的工具。而且，再次强调，使用 **Gemini 3.1 Flashlight** 并打开代码执行来完成这项工作，成本非常低。而且只需一行代码就可以建立那个沙盒 **Python** 环境，**Gemini** 可以利用它来完成这项工作。

<details>
<summary>Original English</summary>

**Paige**: so that is a Gemini 3.1 flashlight for analyzing video. Um, you can also use it to analyze images with a couple of other bakedin tools. Um, and if we look over to the right, we can see structured outputs, code execution, things like function calling, even for custom functions. Um, also some things like URL context. Um, and all of these are very very special, but they're also just oneliners if you want to use them as part of your API. Um, so as an example, if I turn on code execution, um, I'm going to see a Gemini 3.1 flashlight selected, um, I'm going to go into compare mode. So I want to compare it, um, with maybe the Gemini 3 flash preview, also with code execution turned on. Um, and I'm going to look for a picture of Lego bricks. Um, this one. And copy the image. Uh, and right now we're in compare mode. So I'm comparing two different models, both with the same tool turned on. Um, and say something to the effect of draw bounding boxes around all of the green Lego bricks uh using Python. Um, make sure uh or display the image with bounding boxes. And code execution is sort of giving Gemini the ability to uh to sort of stand up a makeshift Python environment that's sandboxed um use a whole bunch of data science libraries that are pre-installed um and use those invoke them as tool calls um kind of like writing the code and incorporating anything that you might share in. So, I shared in um this image uh and very very quickly, I'm not sure if you saw how quickly um but it was able to draw bounding boxes around the the green Lego bricks, you could also ask for segmentation masks. Um and even more excitingly, so Gemini 3 Flash is still plugging along. Um, but if you look at how much this cost um to do to define the bounding boxes, you could have also asked for things like um tell me how many green Legos there are or tell me uh um you know what are the orientations of the Lego bricks. Tell me uh how many uh you know what are they called? The little funny rabbit things, laboo. Tell me how many of those you see in all of the frames of this video. um and at what time stamp like those those are the kinds of tools that can be invoked um via the sandbox environment. Um and again like very very inexpensive in order to do this work with Gemini 3.1 flashlight and code execution turned on. Um and it's just a oneliner to stand up that sandbox Python environment um with compute that Gemini can use to do that work.

</details>

**Paige**: 酷。看起来 **Gemini 3 Flash Preview** 能够完成这项工作。它正在检查它的工作。所以这是它一路走来的迭代过程。它得到了第一个结果，然后说：“好的，我要仔细检查并验证我做得是否正确。”它绘制了分割掩码，以定义它在图像中看到的所有绿色光谱。然后它验证了这些坐标是否正确。而且，如果我仍然看，验证的成本明显更高，但仍然是几美分的数量级，用于绘制边界框。它只是花费了更多的时间，也调用了更多的工具。所以我强烈强烈建议你尝试使用 **Gemini 3.1 Flashlight** 来处理你的用例，特别是如果你之前依赖的是 **Gemini 2.0 Flash** 或 **2.5 Flash**。

<details>
<summary>Original English</summary>

**Paige**: Cool. And it looks like the uh it looks like the Gemini 3 flash preview was able to do it. It was checking its work. So that was the iteration that it was going through along the way. So it got this first result and it said, "All right, I want to double check and verify that what I did was right. It drew the segmentation mask with uh to like define all of the the like green spectrums um that it saw in the image. Uh and then it kind of verified that those were the correct coordinates. Um and still if I look um it's significantly more cost with the verification but still on the order of pennies in order to draw the bounding boxes. It just took a little bit more time and also a lot more tool calls to invoke. Um so I strongly strongly recommend um playing around with Gemini 3.1 flashlight for your use cases especially if previously you were relying on Gemini 2.0 flash or 2.5 flash.

</details>

### AI Studio 应用构建演示

**Paige**: 酷。嗯，我们还有一个叫做 **Build** 的功能。**Build** 再次类似于 v0ero.dev 或 Lovable，如果你以前玩过的话。嗯，我们最近添加了一个功能，你可以在 **Build** 中为你的应用程序添加数据库和身份验证。所以今天举个例子，如果我想点击这个，然后说一些类似“创建一个应用程序，让用户能够上传他们书架的图片”的话。书架上应该有很多书，可以看到书脊。嗯，比如书名和作者名。我希望你使用 **Google 搜索** 基础功能来填补书本的空白信息。所以确保你有关于书名、作者名、书籍描述，以及它可能属于哪种类型的信息。我希望你把所有这些都保存到数据库中。所以用户用他们的 **Google 账户** 登录。他们上传一张他们书架的图片。然后它将他们所有的书保存成这种数据库格式。这样他们就知道自己有什么书，而且这些书都绑定到他们的账户上，这是一个很高的要求。所以，嗯，它已经定义了这项工作。我选择了 **3.1 Pro Preview**。我将使用默认设置，希望能快一点。然后我将点击 **Build**。幕后发生的事情是，我们进入了一个类似 **IDE** 的环境，在那里你可以看到模型正在进行思考过程，弄清楚它需要做什么来规划任务，构建计划，以及它工作了多长时间。你也可以上传文件。所以你可以上传你可能有的文件，比如 PDF 或你想要创建的应用程序的规范，然后把它们也提供给模型。你可以连接到你的 **Drive** 实例。嗯，我们还在右侧有一个设置部分，你可以在其中定义自定义密钥。所以现在我有一个预先添加的 **Gemini API 密钥**。但你也可以添加像 **Superbase API 密钥** 或 **NADEN** 的 **API 密钥**，或者你喜欢的任何类型。嗯，你可以看到新的版本历史，如果你以前玩过 **AI Studio**，这绝对是一个非常受欢迎的功能。然后还有集成。比如 **OOTH**，以及 **GitHub**，这样你就可以同步到公共或私有仓库。但是当它工作的时候，我将继续展示一个叫做 **Genie 3** 的东西。或者实际上在那之前，我将快速展示 **Gemini Live**。以防有人没见过。嗯，有多少人听说过 **Gemini Live**？几个人举手。酷，酷，酷。嗯，我们正好也有 **Gemini Live** 的专家。**Ian**，请过来。**Ian** 是我之前提到的 **Gemma 4** 团队成员，他将进行一些实时模型演示，这让我非常兴奋。

<details>
<summary>Original English</summary>

**Paige**: Cool. Um, so we also have a feature called build. Um, build again is kind of similar to v0ero.dev or uh or lovable if you've played with that before. Um, uh, we've recently added a feature where you can add database and off to your apps within build. Um, and so as an example today, if I wanted to click this guy, um, and say something to the effect of um, create an app that gives the user the ability to upload an image of their bookshelf. Um, the bookshelf should have a whole bunch of books on it with uh, so we can see their spines. Um, uh, things like titles and author names. Um, I want you to use Google search grounding to uh to fill in the blanks uh for for the books. Um, so make sure that you have information about the title, um, the author name, the description of the book, and then also what kind of genre uh, it might be. Um, and I want you to save it all to a database. Um, so the user logs in with uh with their Google account. Um, they upload a picture of uh of their bookshelf. Um, and it saves all of their books uh in like this database format. Um, so they know what books they have and it's attached to their account which is a tall ask. Um, so so it's uh kind of defined that work. I'm going to I've got 3.1 Pro Preview selected. I'm going to do the default instead in the hopes that it might be a little bit faster. Um, and I'm going to click build. And what happens behind the scenes is we get um we get put into this IDE like environment um where you can see the the model kind of going through the thinking process figuring out what it would need to do in order to spec out the assignment um build the plan how long it's working. Um you can also upload files. So you can upload uh files that you might have like PDFs or specs for apps that you would like to create um and give them to the model as well. you can connect to your drive instance. Um, and we also have a settings section off to the right where you can define custom secrets. So, right now I have a Gemini API key that I've pre uh pre-added. Um, but you could also add like a Superbase API key or um an API key for NADEN or whatever your favorite flavor might be. Um, you can see a new version history which if you've played with AI Studio before is definitely uh something that is much appreciated. Um, and then also integrations. So things like OOTH, um, as well as GitHub, so you can sync to a public or a private repository. Um, but while this is working, um, I'm going to go ahead and show off, uh, something called, uh, Genie 3. Um, or actually before that, I'm going to show off Gemini Live real quick. Um, just in case folks haven't seen it. Um, so how many people have heard of Gemini Live? Few hands. Cool, cool, cool. Um, uh, we also happen to have the expert for Gemini Live. Uh, Ian, come on down. Uh, Ian is the, uh, the Gemma the Gemma 4, uh, team member that I had mentioned, uh, that I had mentioned before, and he'll be doing some live model demos, which makes me really excited. Um,

</details>

### Gemini Live 实时对话演示

**Paige**: 但是，**Gemini Live** 让你能够以多种语言与模型进行对话。你还可以共享视频源，共享你的屏幕。所有这些都堆叠在一个语音转文本、**LLM** 理解和文本转语音的管道中。所以举个例子，嗯，我们仍然打开着乐高积木的图片，所以我可以共享我的屏幕，然后说：

<details>
<summary>Original English</summary>

**Paige**: but, uh, Gemini live gives you the ability to have a conversation with the model in a variety of languages. Um, but you can also share video feeds, you can share your screen. Um, and all of this is kind of stacked together in one speechtoext LLM understanding and texttospech pipeline. Um, so as an example, um, uh, we've still got our Lego bricks and pieces pulled up so I can share my screen to say,

</details>

**Paige**: 嗨，**Gemini**。你在屏幕上看到了什么？

<details>
<summary>Original English</summary>

**Paige**: uh, hey there Gemini. Uh, what do you see on the screen?

</details>

**Gemini**: 我看到一个 **Google** 搜索，内容是乐高积木。有图像结果显示各种乐高积木、套装和不同颜色组合。右侧有一个更大的预览，展示了来自 **Freepick** 的一些色彩鲜艳的乐高积木插图。你在找什么特定的东西吗？有人说英语以外的语言吗？

<details>
<summary>Original English</summary>

**Gemini**: I see a Google search for Lego bricks and pieces. There are image results showing various kinds of Lego pieces, sets, and different color combinations. On the right, there's a larger preview of some brightly colored Lego brick illustrations from Freepick. Anything specific you're looking for? Does anybody speak a language other than English?

</details>

**Audience**: 希腊语。

<details>
<summary>Original English</summary>

**Audience**: Seek.

</details>

**Paige**: 希腊语？哦，太棒了。所以，我将要求你核实一些事情。嗯，还要检查拼写。嗯，所以只用希腊语回复用户。对吗？

<details>
<summary>Original English</summary>

**Paige**: See? Oh, excellent. So, so I'm going to I'm going to ask for you to factcheck something. Um, and also spellch checkck something. Um, so only respond to the user in seek. Is that correct?

</details>

**Audience**: 我是说西班牙语。

<details>
<summary>Original English</summary>

**Audience**: I meant Spanish.

</details>

**Paige**: 哦，抱歉。哦，明白了。所以是西班牙语。是的。哦，有了。嗯，只用西班牙语。太棒了。嗯，我刚才想说我不知道那种语言，或者我以前没遇到过。但是只回复...

<details>
<summary>Original English</summary>

**Paige**: Oh, sorry. The Oh, gotcha. So, Spanish and Yep. Oh, there we go. Uh, only uh Spanish. Excellent. Um, and then I was about to say I don't know that language or I haven't had that before. Um, but only response

</details>

**Audience**: 西班牙语。

<details>
<summary>Original English</summary>

**Audience**: Spanish.

</details>

**Paige**: 我会说西班牙语。我在德克萨斯州长大，所以会说西班牙语是必备条件。但是，嗯，我将再次分享。

<details>
<summary>Original English</summary>

**Paige**: I know I know Spanish. Like I grew up in Texas, so it's kind of like prerequisite to know Spanish. Uh but the uh but I'm going to share again. Um

</details>

**Paige**: 嗨，**Gemini**，你能告诉我你在屏幕上看到了什么吗？或者希望...让我看看。不，我想我不需要再点击麦克风了。

<details>
<summary>Original English</summary>

**Paige**: hey Gemini, could you tell me what you see on the screen? Or hopefully let me see. No, I don't think to click the microphone again.

</details>

**Audience**: 哦，就是那个。看，所以，你可以做的一件事是，你看到我修改了系统指令。但是，嗯，你会说特定的西班牙语方言吗？卡斯蒂利亚西班牙语。

<details>
<summary>Original English</summary>

**Audience**: Oh, it's the There you go. Like the uh So, one of the things one of the things that you can do so you see that I've modified the system instructions. Um but uh like do you speak a specific dialect of Spanish? Castellian Spanish. Okay,

</details>

**Paige**: 太棒了。所以，嗯，我移除了系统指令，我应该能够在对话中完成这个操作。嗯，所以，

<details>
<summary>Original English</summary>

**Paige**: excellent. So, um I removed the system instructions and I should be able to do this just within the span of conversation. Um so,

</details>

**Paige**: 嗨，**Gemini**，你能告诉我你在屏幕上看到了什么，但请用卡斯蒂利亚西班牙语说吗？

<details>
<summary>Original English</summary>

**Paige**: hey Gemini, could you tell me what you see on the screen, but could you do it in Castellian Spanish?

</details>

**Gemini**: 好的。在屏幕上，我看到一个 **Google** 搜索，内容是乐高积木。有各种乐高积木、套装和不同颜色组合的图片结果。右侧有一个更大的预览，展示了来自 **Freepick** 的一些色彩鲜艳的乐高积木插图。你在找什么特定的东西吗？

<details>
<summary>Original English</summary>

**Gemini**: Claro. En la pantalla veo una búsqueda de Google de "Lego bricks and pieces". Hay resultados de imágenes que muestran varios tipos de piezas de Lego, sets y diferentes combinaciones de colores. A la derecha, hay una vista previa más grande de algunas ilustraciones de ladrillos de Lego de colores brillantes de Freepick. ¿Hay algo específico que estés buscando?

</details>

**Paige**: 太棒了。所以，你可以，你可以在对话中提问。你可以修改系统指令来选择不同的语言或不同的方言。然后，如果你点击“获取代码”，它会给你你需要用来复制你刚才所做的一切的代码。所以模型名称、任何配置设置，以及你可能调用的任何工具。它适用于共享你的屏幕。你可以在共享屏幕时与屏幕进行交互。但它也适用于视频源。所以你可以说，嗯，

<details>
<summary>Original English</summary>

**Paige**: Excellent. Yep. Awesome. So, so you can uh you can ask within the span of the conversation. You can um modify the system instructions to select different languages or different dialects. Um, and then again the same thing if you click get code, um, it gives you the code that you would need to use to replicate whatever you just did. Um, so the model name, any configuration settings, um, as well as any tool calls that you might invoke. Um, and it works with sharing your screen. Um, you can kind of interact with your screen as you share it. Um, but it also works with video feeds. So you can say um

</details>

**Paige**: 嗨，**Gemini**，我举起了几根手指？另外，为我写一首诗。

<details>
<summary>Original English</summary>

**Paige**: hey Gemini, how many fingers am I holding up? And also compose a poem about me.

</details>

**Gemini**: 嗯，我看到你举起了两根手指，就像和平手势。这是为你写的一首小诗：金发碧眼，心胸开阔，你来学习，扮演你的角色。镜头聚焦，精彩瞬间，一个创造性的灵魂，一件艺术品。怎么样？那非常甜美。谢谢你。

<details>
<summary>Original English</summary>

**Gemini**: Well, I see two fingers up like the peace sign. And here's a little poem for you. With golden hair and an open heart, you come to learn, to play your part. The cameras focus, moments start, a creative spirit, a work of art. How was that? That was very sweet. Thank you.

</details>

**Paige**: 所以，模型能够交互，能够查看视频源，能够查看屏幕。你可以在自己的项目中将它们组合起来。我只是看了一眼。我将快速启用 **Firebase**。所以它应该正在为我们正在构建的那个应用程序设置数据库。然后我想展示的另一件事是一个叫做 **Genie** 的东西。所以如果你以前没听说过 **Genie**，这是 **DeepMind** 创建的一个世界模型。它实际上是模型的组合。所以 **Nano Banana**、**VO**，以及大量用于提示的 **Gemini**。它被组合成一个系统，让你能够描述一些东西，比如一个游戏，一个带有角色的环境，你可以与它互动，你可以玩这个游戏，并且逐像素地进行。所以它不会生成 **Unity** 环境。它不会为 **Unreal Engine** 生成环境。它只是为你能想象的任何东西生成这种逐帧的体验。所以它可能看起来像这样的火山景观，你用方向键驾驶一辆小漫游车。或者像这样的水上摩托，你撞到一个灯，感觉物理效果正在发生，或者说物理效果正在真实地响应。如果你把那个灯撞到水里，然后绕回来，它会在你 60 秒的实验中一直存在。但是幕后没有物理引擎。然后甚至像在佛罗里达经历飓风这样的事情，你可以从一张静态图像或一张家庭照片开始。然后看看这些东西是如何被创建的。但是为此，我将回到我的另一个浏览器。我将打开 **Project Genie**。我将点击“立即探索”。

<details>
<summary>Original English</summary>

**Paige**: The And so the uh the models are able to to kind of interact uh to view video feeds to to view the the screens. Um and you can stitch them together in your own projects. Um just taking a look. I'm going to enable Firebase real quick. Um so it should be setting up the database for that app that we were building. And then the other thing that I wanted to show is something called Genie. Um, so if you haven't heard of Genie before, this is a world model that DeepMind has created. Um, it's actually a composition of models. Um, so Nano Banana, VO, a bunch of Gemini used for prompting. Um, and it's stitched together into a system that allows you to describe something um like a a game, an environment with a character um that you can interact with that you can uh play this game uh and and sort of do it pixel by pixel. So it doesn't generate a Unity environment. It doesn't generate an environment for Unreal Engine. Um it just generates this uh kind of frame by frame experience um for anything that you can imagine. And co. So it could look something like this volcanic landscape where you're navigating with a little rover um with your arrow keys. Um or something like this jet ski where like you hit a light um and it feels like the physics is happening or like the physics is uh like responding in a real way. Um if you knocked that light into the water and then circled back around, it would persist throughout the duration of your 60-second experiment. Um but there's no physics engine behind the scenes. Um, and then even things like experiencing a hurricane in Florida, you can start with a static image or like a family photo. Um, and see how uh see how some of these things get created. Um, but for this, I am going to go back to my other browser. Um, I'm going to pull up Project Genie. I'm going to click explore now.

</details>

### Genie 3 世界模型演示

**Paige**: 然后我将说一些类似“一个世界”的话。嗯，也许是一个阳光明媚的 **摄政运河**。嗯，但是运河里有海豚游泳，而且所有的船都有海盗旗，希望这不属于训练数据的一部分。然后，嗯，角色的描述将是，嗯，你知道，再次是一些不寻常的东西，也许是一只粉色闪闪发光的松鼠，嗯，嗯，带着，嗯，一只粉色闪闪发光的松鼠，带着紫色，嗯，紫色的脚和，嗯，一顶海盗帽。然后创建草图。然后应该发生的是，它使用 **Nano Banana** 来构思第一帧。它会向我们展示，以确保它与我们描述的一致。嗯，嗯，显然 **摄政运河** 正在被戴着海盗帽的粉色闪闪发光的松鼠占领。然后我们应该看到的是第一次迭代，然后是一个可玩的世界，我们可以互动 60 秒，至少对于我们向公众发布的第一版实现是这样。在世界某些地区，你可以通过 **Ultra** 订阅来访问 **Genie 3**。嗯，不是所有地区。但是，嗯，希望，希望我没有超额预订我的 **GPU** 或 **TPU** 配额。

<details>
<summary>Original English</summary>

**Paige**: Then I'm going to say something like uh a world. Um maybe a Regent's Canal on a sunny um day. Um but with dolphins uh swimming in the canal and uh all of the boats have pirate flags, um which is hopefully not part of the training data. And then uh the the uh sort of character description would be um you know something again kind of atypical maybe a pink sparkly squirrel um uh with um a pink sparkly squirrel with a purple um purple feet and um a pirate hat. uh and then create the sketch. And what should happen is that it uses Nano Banana to to kind of ideate on that first frame. It'll show it to us to to make sure that it looks consistent with what we had described. Um uh clearly like Regent's Canal is getting overtaken by pink sparkly squirrels with pirate hats. Um, and then what uh what we should see is kind of this first iteration and then a playable world that we can interact with for just 60 seconds, at least for the um at least for the first implementation that we've released to the public. You're able to access Genie 3 through an ultra subscription in some parts of the world. um not every part um but uh but hopefully hopefully I haven't over booked my uh my GPU or TPU aotment or allocation

</details>

**Paige**: 嗯，如果我们有，我们可以回头看看，嗯，我们可以回头看看书架扫描。看起来模型正在为我们创建 **Firestore** 规则。哦，有了。所以，粉色闪闪发光的松鼠，嗯，海盗帽，摄政运河，海豚。看起来很不错。嗯，那我们来创建这个世界吧。你可以使用方向键移动，呃，或者 **WD 键** 移动，然后使用方向键改变视角。嗯，然后我们应该也可以使用空格键跳跃。嗯，但是我们看看。我们看看这怎么运作。

<details>
<summary>Original English</summary>

**Paige**: um if we have uh we can take a look back at the um we can take a look back at shelf scan. It looks like the model is doing the work of creating the creating the fire store rules for us. Oh, there we go. So, pink sparkly squirrel, um, pirate hat, regions canal, dolphins. That looks pretty good. Um, so let's go ahead and create this world. Um, you can use the arrow keys to move around the, uh, or the WD keys to move around and then the arrow keys to change the perspective. Um, and then we should also be able to use the space bar to jump. Um, but let's see. Let's see how this works.

</details>

**Paige**: 呃，哦天哪。哇。哇。哇。松鼠。嗯，所以看起来松鼠在水上行走。嗯，或者说，呃，跳来跳去。嗯，你也可以跳。嗯，所以跳到船上。呃，你可以看到小自行车。嗯，你可以看到路上的一些人。嗯，看起来 **摄政运河** 上的所有这些船都有海盗旗，呃，还有海豚，嗯，它们目前没有移动，这很奇怪。嗯，然后如果我点击空格键，你可以看到松鼠跳起来。嗯，看起来它没有意识到 **摄政运河** 的水很深，所以我可能应该在我的提示中指定这一点。嗯，然后你也可以看到它尝试跳。嗯，尝试跳到人行道上，然后做它的工作。嗯，所以能够看到你创造的东西，嗯，你能够构建的不同体验，这很疯狂。而且，再次强调，对我来说更疯狂的是，当你移动方向键时，它的每个部分都是动态生成的。嗯，所以它会在最后创建一个视频，你可以下载，你可以，呃，查看和回顾，并与之互动。嗯，这再次只是使用了 **Genie 3** 和这种模型组合，而不是单一模型。其他世界模型构建公司，比如 **World Labs**，嗯，那是 **Fei-Fei Li** 的公司，他们采取了稍微不同的方法。他们正在构建实际的 **Unity** 环境或 **Unreal Engine** 环境。嗯，这些东西都没有作为 3D 游戏资产存储。嗯，它们只是像原始像素一样，嗯，被整合到体验中。

<details>
<summary>Original English</summary>

**Paige**: Uh, oh gosh. Whoa. Whoa. Whoa. squirrel. Um, and so it looks like it's walking on water, the squirrel. Um, or like uh hopping along. Um, you can also jump. Um, so jump on top of the boats. Uh, you can see the the little bicycles. Um, you can see some of the people along the way. Um, and it does look like all of these boats on Regent's Canal um have uh have pirate flags uh and dolphins um that are not currently moving, which is which is pretty wild. Um, and then if I click uh spacebar, you can see the squirrel jump. Um, it looks like it doesn't realize that Regent's Canal has pretty deep water, so I probably should have specified that in my prompt. Um, and then you can also see it uh attempt to jump. um uh attempt to jump into the uh onto the sidewalk uh and do do its work. Um so it's wild to be able to see the things that you can create. Um the different uh the different experiences that you can construct. Um and again, it's even more bonkers to me um that each part of this is being generated dynamically um as you're moving your arrow keys around. Um so it creates a video at the very end that you can download that you can uh kind of see and review and interact with. Um and uh this is again just using Gen3 and this composition of models as opposed to a singular model. Um other world model building companies so things like World Labs um that's Fe Lee's company are taking a slightly different approach. They're they're building out actual Unity environments or Unreal Engine environments. Um, none of these things are stored as 3D game assets. Um, they're just kind of like raw pixels um that are incorporated into the into the experience.

</details>

### AI Studio 书架扫描应用

**Paige**: 酷。所以，回到 **AI Studio**，看起来应用程序还在，呃，还在构建中。嗯，让我，呃，希望，希望我们能看到它。通常，当它开始处理配置文件时，就意味着它快完成了。嗯，我也非常喜欢查看它，看看，嗯，它构建 **Firestore** 规则的方法是什么。嗯，它提示模型的方法可能是什么。嗯，看起来它正在确认应用程序。嗯，然后，呃，一旦完成，它应该会发出一点点声音，嗯，来，呃，来讲解，嗯，讲解应用程序本身。嗯，所以看起来它正在请求允许我的摄像头。嗯，所以我将允许。

<details>
<summary>Original English</summary>

**Paige**: Cool. So, going back to AI Studio, it looks like the app is still getting uh the app is still getting cooked. Um, let me uh and hopefully hopefully we'll be able to see it. Usually, whenever it starts working on config files, that means that it's almost done. Um, I also really love looking through it to see um like what its approach towards the the construction of the fire store rules were. Um, what its approach towards prompting the model might be. Um, it looks like it's confirming the app. Um, and then uh once it's done, it should make a little bitty noise um to uh to talk through um to talk through the the app itself. Um, so it looks like it's ask asking to allow my camera. Um, so I'm going to allow.

</details>

**Paige**: 嗯，我们有这个书架扫描 **AI** 体验。我将用我的个人账户登录 **Google**。我们可以看到它已连接到 **Firestore**。嗯，我将很快找到一个上面有书的书架。

<details>
<summary>Original English</summary>

**Paige**: Um, we have this shelf scan AI experience. I'm going to sign in with Google with my personal account. We can see that it's connected to Fire Store. Um, I'm going to find very quickly a bookshelf um with books on it.

</details>

**Paige**: 让我看看。那些看起来不像真书，因为它们很多都像悬浮在书架下面。嗯，像 **AI** 图像生成让它变得困难。但这个看起来还不错。所以，我们保存这张图片。嗯，看起来有人有很多烹饪书。呃，我将上传照片。所以这张像素照片，嗯，希望它能理解，呃，希望它能理解网页或 **WP**，嗯，或者格式。嗯，它正在通过 **Google 搜索** 收集数据。嗯，然后书本应该会填充到图书馆中，希望能成功。如果不行，我们可以尝试用 **JPEG**。

<details>
<summary>Original English</summary>

**Paige**: Let's see. Those don't look like real books because many of them are hanging like suspended uh below the shelf. Um like AI AI image generation makes it hard. But this is uh this one looks decent. So like let's save this image. Um looks like somebody has a whole bunch of cooking books. Uh I'm going to upload the photo. So this pixel photo um and hope that it can understand uh hope that it can understand web pages orwp um rather format. Um it's gathering data via Google search. Um and then the books should be populated in the library hopefully. If not we can try with a JPEG.

</details>

**Paige**: 但它的品牌形象确实不错。嗯，它似乎识别出了七本书。嗯，或者至少它识别出了这些书。让我再试一次，但这次只用 **JPEG** 图像。嗯，所以我将截个图。还是同一张图片，只是以截图的形式保存。

<details>
<summary>Original English</summary>

**Paige**: But it does have pretty good branding. Um, it was able to identify the seven books it looks like. Um, or at least like it identified the books. Let me try uh let me try again but just with a JPEG image. Um, so I'm going to just take a screenshot. So same image just stored as a screenshot.

</details>

**Paige**: 我会在这里找到。所以，桌面截图，在 4:17。然后识别书籍。如果不行，我们也可以尝试修复错误，看看哪里出了问题。

<details>
<summary>Original English</summary>

**Paige**: I'll find in here. So, desktop screenshot at 417. Then identify books. And if not, we can try fixing the errors as well um to see what might have been going wrong.

</details>

**Paige**: 哦，所以，所以看起来，呃，保存到 **Firestore** 的权限不足。嗯，所以，呃，所以看起来它正在修复这些问题。但是当它修复时，你也可以看到你可以登录、登出、分享应用程序。嗯，所以你可以指定谁有权访问它，全屏分享。嗯，我非常非常喜欢 **AI Studio** 的一点是，它正在找出应该修改哪些文件来做出这些改变。嗯，所以它正在找出验证逻辑。它正在找出，呃，大小可能就是问题所在，嗯，所以图像 URL 大小，嗯，然后它正在找出需要修改哪里才能，呃，才能做出那个改变。嗯，所以看起来它在 **Firestore** 规则中。嗯，**AI Studio** 的 **Build** 功能还有一些其他不错的地方，就是我们有一个应用程序画廊。所以如果你需要为使用我们模型的一些应用程序寻找灵感，你可以查看它们。从 **LIA** 音乐生成到，嗯，多人游戏体验。所以你可以看到这个多人霓虹蛇或这个 Mandelbulb 探索器。嗯，你可以看到用 **Nano Banana** 设计的东西。所以像能够改变和修改图像。嗯，你可以看看 **Sik Media Pipe** 示例。嗯，它让你能够玩这个游戏，你的手会被检测到。嗯，但是你拿着这个小，呃，每个人都会发现我玩这个游戏玩得很烂。嗯，呃，如何，呃，呃，移动一个小小的，一个小小的弹珠。

<details>
<summary>Original English</summary>

**Paige**: Oh, so so it looks like the uh there are insufficient permissions um for saving in fire store. Um so uh so it looks like it's going ahead and fixing fixing those issues. Um but as it does um you can also see that you can log in, you can log out, you can share the app. Um so you can specify who has access to it, share full screen. Um and one of the things that I also really really love about AI Studio um is that uh it's figuring out uh where the files should be modified in order to make those changes. Um so it's figuring out the validation logic. It's figuring out that the that the size um might have been the corporate um so the the image URL size um and then it's figuring out where it would need to modify in order to uh in order to make that change. Um so it looks like it's in the fire store rules. Um some of the other nice things about AI Studios build feature is that we have um an app gallery. So if you need to get inspired for some of the apps uh that are using our models, you can kind of review them. Everything from LIA for music generation to um multiplayer experiences with games. So you can see this multiplayer neon snake or this mandal bulb explorer. Um you can see a design with nano banana. So like being able to change and modify images. Um, you can take a look at the sik uh media pipe example. Um, which allows you to to kind of play this game where your hand is detected. Um, but you take this little uh and everybody can find out that I play this game really poorly. Um, uh, how to uh, uh, move one of the little one of the little marble deals.

</details>

**Paige**: 哦天哪，我玩这个游戏真是太烂了。嗯，但是，呃，然后听起来另一个应用程序也创建完成了。嗯，时机完美。嗯，但是如果我，如果我上传图片，我们再试着识别一下书。祈祷成功。

<details>
<summary>Original English</summary>

**Paige**: oh gosh, I am really horrible at this game. Um, but the uh and then it also sounds like the other app uh finished getting created. Um, perfect timing. Um, but if I if I sort of upload the image, let's try to identify the book again. Fingers crossed.

</details>

**Paige**: 是的。然后它会自动填充所有书籍。所以它们都被编目了，包括日期、书籍类型、相关详细信息、书名、作者，尽管其中一些在上传的书脊上并没有。嗯，如果我登出然后重新登录，嗯，它会保留我添加的所有书籍。嗯，如果我想和你们所有人分享这个，因为我显然想知道你们书架上都有什么书。嗯，我可以复制这个链接，然后生成一个 **QR 码**。

<details>
<summary>Original English</summary>

**Paige**: Yep. And then it automatically populates all of the books. So they all got uh they got all got cataloged with the date, the the type of book, the details associated, um the name of the book, the author, even though some of those were not uh available in the in the spines of the books that I uploaded. Um, if I log out and then log back in, um, it keeps all of the the books that I had added persisted. Um, and if I wanted to share this with all of you because clearly I want to know what all of y'all have on your bookshelves. Um, I could copy this link and then do a QR code generator.

</details>

**Paige**: 嗯，呃，如果你使用这个 **QR 码**，你应该能够访问我刚刚创建的应用程序，上传你自己的书架图片，然后将它们编目到你自己的应用程序中。嗯，下一个功能可能是找到一种方法让我的朋友能够请求借书。嗯，因为每次我给朋友一本书，他们都有保留它的倾向，我理解，但这也令人筋疲力尽。我有很多本 **《无尽的玩笑》** 流落在外。嗯，但是，呃，这只是对 **AI Studio** 中你可以做的一些事情，我们添加的一些新功能，以及我们可用的新模型的一次旋风式演示。嗯，接下来我将欢迎我的同事 **Guillaume**，他将向大家介绍我们的生成式媒体模型。所以从音乐生成到图像创建、图像编辑再到视频生成。嗯，这应该会很有趣。嗯，非常感谢。谢谢大家前来。

<details>
<summary>Original English</summary>

**Paige**: Um, and uh, if you use this QR code, you should be able to access the app that I just created, upload your own bookshelf images, and then have them cataloged um, to your own uh, to your own apps. Um, next feature would be like finding a way to give my friends the ability to request them. Um because every time I give my friends a book um they they have a tendency to keep it which I understand but is also like exhausting. I have so many copies of Infinite Jest out in the world. Um but the uh but this is the um like uh just kind of a whirlwind tour of some of the things that you can do in AI studio some of the new features that we've added the new models that we have available. Um and with that I am going to welcome my colleague Guiam um who is going to tell you all about our generative media models. So everything from music generation to image creation, image editing to video generation. Um and it should be a fun time. Um so thank you so much. Thank you for coming.

</details>

**Guillaume**: 大家好。

<details>
<summary>Original English</summary>

**Guillaume**: Hello everybody.

</details>

**Guillaume**: 你需要向上，这是正确的。

<details>
<summary>Original English</summary>

**Guillaume**: You will need the up and this is the right one.

</details>

**Audience**: 你会很棒的。然后我把东西放哪了？

<details>
<summary>Original English</summary>

**Audience**: You're going to be awesome. And then do I have where did I leave?

</details>

**Guillaume**: 你现在可以展示我的屏幕了。好的，很好。嗯，正如 **Paige** 所说，我们将进行我今天早上做过的相同演讲，相同的研讨会。呃，我们的时间稍微少一点。所以我会在某些地方讲得快一点，也许不会实时运行所有东西。但是你们，我将展示的内容在这个链接上。所以如果你打开它，你可以同时自己运行它。嗯，所以，呃，我将谈论生成式媒体。嗯，生成式媒体是关于创建图像、视频、文本、口语文本以及类似的东西。我想我也会把 **Genie** 归入生成式媒体。嗯，所以是的，我们在 **DeepMind** 有很多这样的模型。所以让我来介绍一下它们。嗯，所以很快地，我叫 **Guillaume**。呃，我已经在 **Google** 工作六年了。在 **DeepMind** 做了两年开发者倡导。呃，主要是在大多数 **Gemini** 模型上，直到去年，今年我更专注于生成式媒体模型，因为那是最好玩的模型。嗯，我以前在视频游戏行业工作过。嗯，我就是这样最初加入 **Google** 的。

<details>
<summary>Original English</summary>

**Guillaume**: You can you can show my screen now. Okay, good. Um, so as as P said, we are it's going to be the same talk as I did this morning, the same workshop. Uh, we have slightly less time. So I'm going to go faster on some things and maybe not run things uh in real time. But you like the the content I'm going to show is on this uh this link. So if you just you can you can just open it and and run it yourself at the same time. Um, so uh I'm going to talk about generative media. Um generative media is everything about creating um images, videos uh text uh um like spoken text and uh and things like that. I think I would I would fit Jenny into gen media as well. Um so yeah and we have plenty of models like that at deep mind. So let me let me go through all of them. Um so very quickly my name is Guom. Uh I've been at Google for six years now. Two years at Divine doing uh developer advocacy. Uh mainly most on most of the Gemini model until last year and since and this year I'm focusing more on the on the gen media models because that's the funniest model to play with. Um I've been I've been working in the video game industry before. Um and that's how I joined Google initially.

</details>

### 生成式媒体模型概述

**Guillaume**: 所以，呃，是的，打开你的手机。一切都是媒体。我之前已经说过了。基本上，**Paige** 谈到了一点我们对世界模型的愿景。我对世界模型的定义是，它能够摄取尽可能多的模态并理解它们，就像我们的五种感官一样，并且能够以不同的模态进行交流或输出。所以这确实一直是 **DeepMind** 对生成式 **AI** 愿景的核心。呃，第一代 **Gemini** 模型，虽然只有两年前，但感觉已经很老了，它当时只是一个文本到文本的模型，但实际上在幕后它已经是一个多模态模型了，因为你可以向它发送图像，但它被阻止了。他们出于测试原因这样做了。我不记得为什么，但基本上他们在模型中通过后训练阻止了它。然后几个月后发布时，我们发布了 1.5 版本。这个新颖之处在于它是第一个多模态模型。呃，有时当你给它一张图片时，它会回答“抱歉，我只是一个 **LLM**。我无法处理图像”，因为一些训练仍然存在。嗯，但基本上是的，我们希望创建那些能够从视频、音频以及所有这些中理解世界所有物理的模型。呃，我们之所以有这么多不同的模型，唯一的原因是，发布一个只做视频的模型，一个只做图像的模型，一个只做文本的模型，比拥有一个什么都做的模型更容易。然后每次我们想更新一个功能时，就必须发布一个全新的模型，每个人都必须转换等等。所以这只是原因。嗯，每个人都因为 **Gemini** 模型而认识我们，我们还有很多其他模型，我暂时跳过。嗯，快速，嗯，快速的时间线。呃，我们一直在发布新东西。呃，我想 **Paige** 之前说过，平均每五天我们就会发布一个新模型或新功能。呃，这只是生成式媒体模型。呃，除此之外还有所有其他模型。如果你加上我们在 **AI Studio** 中所做的所有更改，所有定价之类的东西，比如这里和那里的小功能，我们每周都会发布两到三个新东西。嗯，所以，是的，所以基本上，跟踪所有我们必须提供的东西很难，甚至对我们来说也很难。所以我知道对于像你这样的人来说更难，因为你还必须关注竞争对手在做什么。嗯，所以这也是我们进行这些，嗯，这些演讲的原因。很快，呃，**Nano Banana** 的更新。我们几个月前发布了 **Nano Banana 2**，嗯，在一月底，二月初。呃，主要的事情是你可以输出不同的纵横比和尺寸。嗯，它有搜索基础功能。所以这就是我如何做到的，你现在看不到我的屏幕了。为什么？

<details>
<summary>Original English</summary>

**Guillaume**: So uh yeah, open your phones. Everything is a media. I already said that. Basically, um Paige talked a bit about our vision of what um world models are. My definition of a world model is something that can uh ingest as many modalities as as it as it can and understand them kind of for five senses and to to also talk or output things in different modalities as well. So that really has been at the core of the deep mind vision of what uh generative AI should be. Uh the the first gen Gemini model like it was only two years ago but it seems old but it was only a text to text uh to textto text model but actually behind the scenes it was already a multimodel model because and that and you could have been sending it images but it was blocked. They did for testing reasons. I don't I don't remember why but basically they blocked it in the model with with post training and then when it released a few months afterwards we released 1.5. This one the new the novelty was that it was uh the first multimodel model. Uh sometimes when you were giving it a picture it was it was answering I'm sorry I'm just LLM. I can't do anything with images because some of the that training was still still in there. Um but basically yes we we want to create those models that can understand all of the physics of the world from videos audios and and all of that. Uh and the only reason why we have so many different models is that it's easier to ship one models that only does video and one models that only does images and one models that only text than to have like one models that does everything. And then it it becames a problem. every time we want to update one of the feature we have to release a whole new model and everybody has to to convert and all. So that's that's just the reason for that. Um everybody knows us for the Gemini models we have lots of other models I will go over like I will skip that for now. Um quick um quick timeline. Uh we release things all the time. Uh I think Paige says it said it earlier on on average we are releasing a new model or new capabilities every five days. Uh that's just the gen media models. Uh there's all of the other models on top of that. And if you add all of the changes we are doing in AI studio, all of the pricing things like small features here and there we are releasing like two to three new new things every week. Um and um so yeah, it's so it's basically it's it's hard to keep track and like it's even hard for us to keep track of everything we have to offer. So I know that's that for people like uh like you it's even harder because you also have to look at what the the competition is doing. Um so that's also why we are doing those those um those talks very quickly. uh the the updates on Nano Banana. We released Nano Banana 2 a few months ago um in end of January, the beginning of February. Uh the main thing is that you can output different uh as aspect ratio and u sizes. Um it has search grounding. So that's basically how I do you don't see my screen anymore. Why?

</details>

**Guillaume**: 好的，想象一下，这就是媒体广告的作用。嗯，所以，关于 **Nano Banana Pro** 的主要事情是它添加了搜索基础功能。所以你可以让它搜索互联网，我就是这样制作这张图片的。就像“只搜索你在 **Google** 上能找到的关于我的足迹，然后为我制作一张图片”，这在某种程度上有点吓人。嗯，但是 **Neo Banana 2** 的新功能是你可以用图像运行做同样的事情。所以你可以谈论一个特定的地方，一个特定的桥梁，然后它会从网上寻找一张图片，然后基于这张图片创建图像。所以这是没有运行和没有基础功能的。所以你可以看到它看起来比普通的构建更像。

<details>
<summary>Original English</summary>

**Guillaume**: Okay, just imagine in your head that's that's what media ads are for. Um, so the the main thing about Oh, thank you. Nano Banana uh Pro was that it it add search grounding. So you could ask it to search for the internet and that's how I made this image. Like just look for what you can find about my footprint on Google and make an image about me which is kind of scary in a way. Um and but the new things with Neo Banana 2 is that you can do the same thing with image running. So it can you can uh talk about a specific places a specific like bridge like that and it will look for for an image on on the web and then create image based on that. So that's without running and that's without grounding. So you can see that it's looks a bit more than the uh than the normal building.

</details>

**Guillaume**: 我们还有 **VO**。快速说一下 **VO**，过去一周的主要新颖之处在于我们上周发布了 **VO 3.1 light**，这是我们拥有的最便宜的视频生成模型。所以每张图片只需 5 美分。这比一年前的 **V3** 便宜得多。所以你可以用它来原型设计、测试你的提示等等。然后如果你想要更好的质量，就可以转向更好的模型。

<details>
<summary>Original English</summary>

**Guillaume**: We also have VO. Very quickly on VO the main novelty in the past uh week is that we released V 3.1 light last week uh which is the cheapest model for generating video we have. So it's only 5 cent per per image. So it's which is way way cheaper than what V3 was a year ago. So the idea that you can use that to prototype, test your prompts and so on. And then if you want better quality then you can move to the to the better models.

</details>

**Guillaume**: 呃，然后 **LIA 3** 是今年最酷的模型。呃，它是一个音乐生成模型。呃，所以你可以生成 30 秒的歌曲或三分钟的完整歌曲，包括歌词等等。我稍后会给你看一些演示。嗯，据我所知，我们是第一个通过 **API** 提供这种音乐生成模型的公司。所以这对于任何代理式或你可能有的任何工作流程来说都非常酷。所以如果你想每天早上被一首关于最新新闻的歌曲唤醒，你可以做到。

<details>
<summary>Original English</summary>

**Guillaume**: Uh and then LA 3 is the the the coolest model this year. Uh it's all music generation model. Uh so you can either generate uh 30 seconds songs or full songs of three minutes uh with the lyrics and all of that. And I will I will show you some demos afterwards. Um and I've as far as I know we are the first one to offer such uh music generation models through API. So that's really cool for any kind of uh agentic or whatever workflow you you might have. So if you want to be waken up with a song about the latest news every morning, you can do it.

</details>

**Guillaume**: 嗯，还有一个我喜欢但没人知道的，就是我们实际上还有另一个 **LIA** 模型，叫做 **LIA real time**，这个基本上是一个实时模型。所以它会无限期地创作音乐，你可以用不同的提示来改变它。所以它会实时改变它正在生成的音乐类型，就像一个 **DJ**。所以玩起来很有趣，但是，呃，一些老派的人不知道它。嗯，就像我说的，我将，因为它是一个研讨会。所以想法是你们自己测试。呃，所以，你可以打开这个链接，它会向你展示我准备的内容。嗯，当你们拍照的时候，呃，只是一个免责声明，它是生成式媒体模型。所以它们都是付费模型。所以它们，运行这个笔记本实际上会花费一些钱。嗯，视频，视频生成将是最昂贵的部分。所以你可以记住这一点。呃，其余的都很便宜。所以我认为你可以运行整个笔记本，大概花费一美元。所以应该没问题。但我只是想，呃，向大家说明清楚。

<details>
<summary>Original English</summary>

**Guillaume**: Um, and also another one very quickly that I love but nobody knows about is that we have actually another LIA model that is LA real time and this one is basically a live model. So it's creating music uh indefinitely and and you can just prompt it differently. So it's just going to change what you are uh the kind of music it's generating in real real time like a DJ. So, it's it's pretty fun to play with, but uh some old like people don't know about it. Um as I said, I'm going to because it's it's meant to be a workshop. So, the idea is that you test things yourself. Uh so, you can open this uh this link and that will show you the the content I prepared. Um while you take pictures and all uh just one disclaimer, it's gen media models. So, they are all paid models. So they like running the notebook actually costs a bit of money. Um the video the the the video generation is going to be the most expensive thing. So you can just keep that. Uh the rest is pretty cheap. So I think you can run the wall the wall notebook for something like one one. So it should be should be fine. But just I prefer to to be uh to be clear with everybody.

</details>

**Guillaume**: 那么，我们开始吧。

<details>
<summary>Original English</summary>

**Guillaume**: So let's let's move to it. So

</details>

### 生成式媒体工作坊：书籍插图

**Guillaume**: 那么这个工作坊的目的是什么？这个想法是展示所有生成式媒体模型，以这个例子为例：我们将拿一本书，我们将从一个开源图书馆拿一本书。所以我们被允许使用它，然后我们将创建图像来插图角色是什么样子，以及每个章节中发生了什么。然后我们将转向其他生成式媒体模型。所以创建关于章节的视频，然后创建音乐，并让 **Gemini** 告诉我们章节中发生了什么。所以这只是设置。你需要安装 **SDK**。你需要一个 **API 密钥**。我想你可能已经猜到了。我正在初始化客户端。我最近才知道的一件事是，你实际上在初始化客户端时有一种方法可以实现一些 **重试系统**。所以这在现在非常有用，当你使用 **Nano Banana 2** 时，因为，呃，特别是当美国醒来时，要从中获取一些东西变得更难了。呃，我们正在努力，是的，我们正在努力获得更多容量，但仍然，呃，拥有某种重试系统总是有帮助的。

<details>
<summary>Original English</summary>

**Guillaume**: what's the idea of this workshop? So the the idea was to showcase all of the gen media models with this uh this example of we're going to take a book uh and I'm going we are going to take a book from an an open-source library. So uh we are allowed to use it and then we are going to create images to illustrate uh what the characters look like what the and what's happening in each chapter and then we are going to move to the other gen media models. So creating videos uh about uh about the chapter and then creating music and having Gemini uh tell us about uh what's happening in the in the chapter. So this is just setup. You need to install the SDK. You need an API key. I guess you can you could have guessed that. Uh I'm initializing the client. And something that uh I didn't know about until recently is that you actually have a way when initializing the client to uh implement some retry system. So which is kind of uh very useful uh nowadays with whenever you use nano banana too because uh especially when the US wakes up it's becoming harder to uh to get to uh to get something out of it. uh and we're working all of yeah we're working on getting more capacity but still uh it's having some kind of retry system al always helps

</details>

**Guillaume**: 嗯，所以导入，然后我们选择模型。我通常在为付费模型创建内容时，会有一个复选框，如果你打开它，它已经被选中了，它不应该被选中，但我昨天晚上犯了一个错误，因为我不想让人们运行模型并付费，呃，特别是像 **VO** 笔记本，运行一次大约要 20 美元，所以我不想让任何人不小心运行它。嗯，仅仅为了演示，我还限制了我们创建的角色图像和章节图像的数量，只是为了让它运行得更快。所以这本书是 **Kenneth Grahame** 的 **《柳林风声》**，我从 **Project Gutenberg** 图书馆获取的，这是一个开源图书馆，你可以在那里下载开源书籍。出于某种原因，自从我在英国以来它就不能用了。所以肯定有什么关于这个图书馆在英国不可用的问题。嗯，但是如果你运行笔记本，它应该能用，因为它很可能服务器在另一个国家。所以它能够恢复这本书。嗯，所以，我正在做的就是在这里下载这本书，就像我用一个 **get URL** 一样。嗯，我没有说过，**Paige** 也没有说过。所以，呃，很快地，呃，因为每个人总是问我们这个问题。我们在 **Google** 有一个特点，就是我们总是创建多个做同样事情的项目，多个产品，我们也在做，我们对消息应用程序也这样做了。我们对 **Gemini** 也这样做了。所以这可能会有点令人困惑。所以很快地澄清一下，嗯，所以如果你看图表，基本上我们有消费者应用程序。所以左边是面向所有人的应用程序。你可以用它们做很多事情。你可以，呃，你可以向 **Gemini** 提出任何问题。你可以生成图像等等。但作为开发者，我想在座的每个人，你可能会有点沮丧，因为你无法真正访问参数，选择正在运行的确切模型，你不知道它很可能正在进行很酷的工具调用，但你不知道它正在进行哪些工具调用，所以这对大众来说很好，但对我们来说就不太好了。嗯，另一方面，我们有 **Vertex AI**，这是我们的企业级产品，它恰恰相反。你有很多控制权。你可以决定你的提示将在哪个数据中心运行。所以特别是在欧洲，很多人都希望确保数据不会离开欧洲。所以，嗯，这在这方面很方便。但它也伴随着巨大的责任。所以设置起来有点困难。所以我通常只建议人们在已经使用 **GCP** 的情况下，或者如果他们有一个 **DevOps** 团队可以为他们进行设置的情况下，才开始使用 **Vertex AI**。在中间地带，我们有 **AI Studio** 和我们为开发者提供的开发者 **API**，但基本上，它的想法是尽可能容易地开始玩模型并做事情，只需创建一个 **API 密钥** 然后使用它。嗯，而且尽可能容易。

<details>
<summary>Original English</summary>

**Guillaume**: um so import and then we are selecting the models and I usually when when I create content for that are using paid models I usually have some kind of checkbox that uh you can if you if you're opening it's already checked it should be it should not be but I made a mistake yesterday evening uh because I don't want people to run the models and have to pay uh especially the the VO the VO notebook for example example like cost something like $20 to run so I don't want anybody to run it by mistake um just for the sake of the of the demo I'm also limiting the number of characters images and chapters images we are creating just so that it's it's faster to run and all so the book is uh named the wind of the willows from Kenneth Graham and I'm I took it from the project Gutenberg libraries which is an open-source library where you can download open source books. For some reason it doesn't work uh since I've been in the UK. So there has to be something about this library not being available in the UK. Um but if you run the notebook it should work because it's very likely the server is in in another country. So it will be able to recover the book. Um so so what I'm doing is that I'm just downloading this uh this book here like I like with a with a get uh URL and um I didn't say I didn't talk about that and page neither. So uh very quickly uh because everybody's always asking that question to us. We have a specialty at Google is that we are always creating multiple projects that are doing the same thing multiple products and we are doing we did the same with messaging apps. We are doing the same with uh with Gemini. So that's can that can be a bit confusing. So just very quickly to uh to clarify things um so if you if you look at the graph like basically we have the consumers apps. So on the on the on the left it's the apps that are for everybody. You can do plenty of things with them. You can uh you can ask any question to Gemini. you can generate the images and all but as a developer like I guess everybody in the room you can be kind of frustrated because you don't uh you can't really access the parameters select the exact model that is doing you can't it you know that it's it's likely doing cool tool cool cool tool calls but you don't know which one it's doing so that's uh that's nice for the for the broad public but it's uh it's not really for us um on the other end we have Vertex AI which is our enterprise ized uh offer that's the exact opposite. You have a lot of control. You can decide in which data center your your prompts are going to be run. So especially in Europe, a lot of people are looking to be certain that that the data is not going to to leave Europe. So that's um that's kind of convenient for that. But it comes with uh like great responsibilities as well. So it's kind of hard to set up. So I usually only recommend people to start with Vert.Ex text if they are already using GCP or if they have a team of devops who can do the setup for them and and in the middle ground we have AI studio and the developer APIs that we made for developers but basically the idea that it's as easy as possible to start to play with the model and and do stuff by just creating an API key and then using it um and as part as easy as possible

</details>

**Guillaume**: 呃，是的，尽可能简单，我们有这个客户端文件上传 **API**，它基本上是一种无需设置存储文件的存储桶的方法。呃，我将在本例中使用它，这样我们就可以在幕后将其上传。它正在创建一个存储桶，但你只需，想法是你不必担心它是如何工作的。你只需上传文件，然后你就可以在你的 **Gemini** 提示中使用了。

<details>
<summary>Original English</summary>

**Guillaume**: uh Yeah, as part as easy as possible, we have this uh client file upload API that is basically a way to not have to set up buckets to store your your files. And uh we are going to I'm using it in this example so that we are uploading it to this behind the scenes. It's creating a bucket, but you just the idea is that you don't have to bother with how it works. You just upload the file and then you can use it in your in your Gemini prompts afterwards.

</details>

**Guillaume**: 嗯，我还会使用结构化输出，因为我想确保模型具体会做什么，因为我将让它生成大量的提示。所以我希望确切地知道它只返回提示，而不是一些介绍或文本之类的东西，比如“哦，是的，当然我可以做到”，然后你就很难解析。所以这就是为什么我使用这种结构化输出，我正在使用聊天模式，这基本上是一种将请求链接到模型的方式，这样你就可以，它基本上会保存历史记录并重新发送历史记录，这样模型就知道之前发生了什么，这在这种情况下非常方便，因为我们不想一直上传这本书。我们只是希望这本书在历史记录和上下文中，这样模型就可以提出新问题并生成关于这本书的新提示。对于图像，通过使用这个系统，我们将拥有所有以前的图像，这些图像将存储在内存中。所以模型将更好地保持角色的一致性，并更好地保持风格的一致性。

<details>
<summary>Original English</summary>

**Guillaume**: Um, I'm also going to use uh structured outputs because I want to be certain about what exactly the model is going to to do because I I'm going to have it uh to to ask it uh to generate a lot of prompts. So I want to know exactly that uh it's just returning the prompt and not some like uh introduction or um text or something like like the oh yes sure I can do that and then you it's hard to pass. So that's why we are I'm having this uh this structured output and I'm using chat mode which is basically a way to uh u to chain request to uh to the model so that you can uh it's it basically saves the history and resend history so that the models knows what happens before which is quite convenient in this case because we don't want to upload the book all the time. We just want to the the book to be in the history and in the in the context so the models can ask uh can answer new questions and generate new prompts about the book. And for the images, it's going to be quite the same by by using this system. We will have all the previous images that are going to be in memory. So the model will be better at uh keeping the consistency of the characters and better and the consistency of the style.

</details>

**Guillaume**: 所以，呃，我只是把书给它。这是用 **Nano Banana** 绘制插图的书。就这样。然后我定义一种风格。所以我让它，你可以什么都不做，模型就会想出一种风格。但后来我想尝试一些别的东西。所以它将是一种黑暗奇幻风格，黑白背景和彩色角色。嗯，基本上我还为 **Nano Banana** 添加了一些系统指令，因为，呃，根据我之前的测试，我认为 **Nano Banana 2** 和 **Pro** 效果更好。但是对于第一个 **Nano Banana**，嗯，每当我要求它生成关于肖像格式书籍的图像时，它总是倾向于生成我想要的书籍封面。所以它总是添加标题之类的东西。所以我不得不添加一些系统指令，以确保我不想有边框。我不想有标题。我不想有描述。我保持家庭友好，这可能不太符合黑暗奇幻的风格，我想。嗯，呃，也不要面板，因为我不想，呃，我不想一本漫画书。我只想为每一章生成一张图片。然后基本上我将使用那个聊天来要求模型描述每个主要角色。呃，我最初只写了成年人，但因为在某些时候 **Nano Banana** 在欧洲无法生成儿童图像，但现在已经不是这样了。所以我们可以删除那部分。

<details>
<summary>Original English</summary>

**Guillaume**: So uh I'm just giving it the book. Here's the booku to illustrate with nano banana. That's all. Then I'm defining a style. So I went I I made it so that you can just do nothing and the the model will come up with the style. But then I wanted to try something else earlier. So it's going to be a dark fantasy style with black and white background and colored characters. Um, and basically I also adding some system instructions for for Nano Banana because I uh from my earlier test I think it's better with Nano Banana 2 and Pro. But with the first Nano Banana um whenever I was asking it images about books that were in the portrait um format, it it tend to to book covers that I wanted. So it it was always adding titles and things like that. So I had to add some system instructions to make sure that I I don't want borders. I don't want titles. I don't want description. I stay family friendly which is likely to not be very aligned with dark fantasy I guess. Um and uh and no panels as well because I don't want uh I don't want a comic book. I want just an image for for each chapter. And then basically I will use that chat to ask the model to describe each of the main characters. Uh I initially wrote only the adults but because at some points Nano Banana could not generate uh kids images in Europe but that's not the case anymore. So we could remove that part

</details>

**Guillaume**: 我正在获取这个角色列表以及每个角色的提示。然后我就可以逐一处理每个提示，并要求 **Nano Banana** 创建一个图像来插图那个提示。所以我就是这样初始化图像图表的。所以它将是一个单独的图表。嗯，然后我将所有提示发送出去，以便创建。所以我们可以看到，呃，那是主要角色。所以，呃，正如所要求的，背景是黑白的，角色是彩色的。嗯，不太像黑暗奇幻，但还行。嗯，那是水鼠。那是蟾蜍。呃，獾。是的，獾。

<details>
<summary>Original English</summary>

**Guillaume**: and I I'm getting this this list of characters and a prompt for each of them. And then I can just go over uh each of the each of the prompts and ask Nano Banana to create an image that to illustrate that um that that prompt. So that's how I initial I initialize the image chart. So it's going to be a separate chart. Um and then I'm sending all of the all of the uh the prompts to create to to be created. So we can see that uh so that's that's small the main character. So, uh, as as requested, the background is black and white, and the character has colored. Um, not very dark fantasy, but yeah. Um, that's uh the water rat. That's the toad. Uh, the the badger. The Yeah, the badger.

</details>

**Guillaume**: 嗯，目前就这些。然后我将再次做同样的事情，就像，呃，现在你的历史记录中有了整本书。所以给我每个章节的提示来插图它们。所以我得到了每个章节的提示，然后我正在为每个提示创建图像。

<details>
<summary>Original English</summary>

**Guillaume**: And, uh, that's that's it for now. And then I'm going to do the same thing again like uh now you you have the full book in your in your history. So give me prompts for each chapter to illustrate them. So up I get a prompt for each of those uh chapter and I'm creating images for for each of the prompt.

</details>

**Guillaume**: 所以这里我们有角色在河边野餐。然后另一个在路上，发生了什么。嗯，这里在森林里，那是第一章。如果你仔细看，你会发现这里有一个问题，因为蟾蜍没有使用我们之前创建的角色图像来表示。嗯，很可能是因为提示没有明确说明它就是同一个角色。嗯，所以这就是为什么我有第二种方法来做，这种方法实际上更清晰。如果你要大规模地做，我就会这样做。嗯，我正在创建另一种结构化输出，它是一个章节，它有一个名称和提示，但也有一个应该出现在图像中的角色列表。所以我正在运行，我再次要求模型提出一些东西，但这次它给我的是角色列表。这样我就可以，嗯，基本上在这里，嗯，对于我将创建的每个图像，也提供角色应该是什么样子的参考图像。所以它只在上下文中包含这些图像，而不是包含我们之前做的所有可能的图像。在这种情况下，我们有大约五个角色。所以没问题。但是如果你在一本有 40 个角色的真实书中，那样期望模型完美地管理所有上下文是不可持续的。嗯，老实说，如果我要大规模地做，我想我甚至会为每个角色创建不止一张图像。也许一张正面图像，一张背面图像，一张侧面图像。这样我就可以在这种情况下准确地传递我需要的图像。所以我们可以看到图像看起来差不多，但是，呃，这次蟾蜍是正确的。

<details>
<summary>Original English</summary>

**Guillaume**: So here we have the the characters having a picnic next to the river. Then another one's on the road and something's happening. Um, and here in the forest, that's that's the first chapter. And if you look closely, you can see that there's there was a problem here because the toad was not uh represented using the uh the character uh the the images that we we created before. Um likely because the prompt was not clear that it was exactly the same character. Um and so which is why I I have a second way of doing it which is actually cleaner. And if you were to do that to do that at scale, that's that's how I would do it. Um, and in I'm creating another type of structured output which is which is a chapter which is which has a name and the prompt as well, but also list of characters that that are meant to appear in the in the image. And so I'm I'm running I'm asking again the model to to come up with something, but this time is it's giving me the list of the character. And that way I can um basically here um for each for each image that I'm going to create also give the reference images of what the character should be looking like. So that's it only has that those images in in its context instead of having all of the possible images that we did before. In this case we have something like five five characters. So it's okay. But if you are in a real book with like 40 characters, that that wouldn't be sustainable to uh to expect the models to actually manage all of the all of the context perfectly. Um and and and honestly, if I was to to do it at scale, I think I would even create more than one image for each character. Maybe one one image from the front, one from the back, one from each side. So that and and then I would pass exactly the one that I that I need in the in this case. So we can see that the image are looks kind of the same but uh this time the the toad is the right one.

</details>

**Guillaume**: 呃，是的，这个看起来真的很像。嗯，所以现在我们可以进入下一步，我们可以使用 **VO** 来根据这些图像创建小视频。所以我正在使用 **VO**，最大的模型，因为，呃，因为说实话我不用付费，否则我就会用最小的模型。嗯，但基本上我们将做同样的事情。我们将要求模型使用视图模型生成视频。呃，我将使用与生成图像相同的提示。我将传递最后生成的图像作为起始帧。然后我想要肖像模式，我想要 720p，因为它会更小。呃，我们开始吧。所以我实际上还没有检查声音听起来怎么样，因为我...

<details>
<summary>Original English</summary>

**Guillaume**: Uh yeah this one really look like um so now we can move uh to the next step and we can use VO to create like small videos based on those images. So I'm I'm using the the VO the largest model because it's uh because I don't have to pay honestly honest otherwise I would use the smallest one. Um but basically we are going to do the same thing. We are going to ask the model to generate a video using the view model. Uh the prompt I'm going to use the same prompt as the one that we used to to generate the image. And I'm I'm passing the last generated image as uh as a starting um frame. And then I want to portrait and I want 720p because it's going to be smaller. Uh and here we go. So I actually haven't checked what the sounds looks like because I

</details>

**VO 模型**: 退后！你不得通过！离开这里，小家伙们。你们不属于这里。

<details>
<summary>Original English</summary>

**VO 模型**: stand back. You shall not pass. Leave this place little ones. You don't belong here.

</details>

**Guillaume**: 我觉得还不错。嗯，但有时效果不太好，因为模型不喜欢，提示只是关于创建静态图像，而且我想，模型不知道之后会发生什么。所以更好的方法是重用聊天，要求模型提供一些关于图像之后发生的事情的解释，我还会再次传递图像，这样它就知道我们正在谈论章节的哪个部分，这样它就能想出正确的提示。嗯，所以它想出了这个提示：“鼹鼠颤抖着，恐惧地抓紧围巾，等等等等。水鼠勇敢地拔出玻璃，向前一步保护他。”所以我们可以看看效果如何。

<details>
<summary>Original English</summary>

**Guillaume**: I think it's quite good. Um but sometime it's not not very good because the model doesn't like the the prompt was just about creating the steel image and the and I think and the model doesn't know what's exactly is expected to be happening afterwards. So a better way of doing it is actually to reuse the chat the chat to ask the model to come up with the um with the uh with some explanations about what's happening after the image and I'm also passing it the image again so that it knows exactly which part of the of the chapter we are talking about so that it can come up with the with the right prompt. Um and so it like it came up with this uh this prompt mold shivers and clutters his scarfs in terror blah blah blah. Uh water brats bravely draws it glass and step forward to protect him. So up we can see how it goes

</details>

**Guillaume**: 有些，哦，就像，在这种情况下，结果不太好。呃，是的，每次我做的测试，不知何故，当我使用相同的提示时，它会添加文本，而不是当它生成另一个提示时，但这应该没有任何影响，因为在这两种情况下，我只是给出了一个提示和一张图片，但我不知道为什么会这样。

<details>
<summary>Original English</summary>

**Guillaume**: and some oh like it's like the the like in this case the results are not really as good. uh and uh yeah and every time every every test I've done somehow when I use the same prompt it's it add it's add text and and not when I when when it generates another another prompt but but it should not have any impact because in both cases I'm just giving a prompt and giving an image but I don't know why it's happening like that um

</details>

### LIA 3 音乐生成与文本转语音

**Guillaume**: 嗯，然后我们可以使用我们上周发布的新 **LIA** 模型，呃，为每个模型创建歌曲。所以仍然是同样的技巧。我们将要求模型创建提示。呃，然后我们将使用 **LIA** 模型生成内容，呃，要求它根据章节提示创作歌曲，基本上就是这样。所以我们来看看第一首，呃，第一首歌应该是管弦乐、原声民谣音乐，平静流畅的原声吉他和长笛二重奏。我们来看看。

<details>
<summary>Original English</summary>

**Guillaume**: um and then we can use the new LIA model that we generated like that we um shipped last week uh to uh to create songs for each model. So still the same the same trick again. We are going to ask the model to create the the prompts for that. Uh and then I'm going we are going to use generate content with the laya model uh ask it to create uh song uh thanks to the chap the the prompt and that's basically it. So let's see the first uh the first song should be orchestral acoustic folk music peaceful flowing acoustic guitar and and flute duets. Let's see.

</details>

**LIA 模型**: (播放音乐)

<details>
<summary>Original English</summary>

**LIA 模型**: (Music plays)

</details>

**Guillaume**: 我觉得很合适。然后第二首，“开阔的道路”是，呃，充满冒险精神，有节奏感，带有小提琴和原声贝斯。然后最后一首是悬疑、诡异的旋律，带有断奏拨弦。

<details>
<summary>Original English</summary>

**Guillaume**: I think it fits. Then the second one, the open road is uh jy adventurous rhythmic with fiddle and acoustic bus. And then the last one is suspenseful creepy melody with stacato pizzicato strings.

</details>

**LIA 模型**: (播放音乐)

<details>
<summary>Original English</summary>

**LIA 模型**: (Music plays)

</details>

**Guillaume**: 我觉得也很合适。老实说，我觉得这个模型真的很棒，因为你很少能在不实际检查结果的情况下做这种演示，因为我之前运行过这个笔记本，但我没有检查音乐会是什么样子。到目前为止，它每次都成功了。嗯，我忘了说的一件事是，我们内部训练模型的方式是，很多生成式媒体模型的训练数据实际上是使用 **Gemini** 制作的。所以这就是为什么 **Gemini** 在为生成式媒体模型生成这些提示方面表现出色，因为它已经接受过理解 **Gemini** 要求的训练。所以这就是 **Gemini** 在生成这些提示方面表现出色的原因。然后，呃，我想展示的最后一个模型是文本转语音模型。所以我很确定你们都听说过这个，因为，呃，每个人都喜欢 **Notebook LM** 中的集成，你可以在其中根据你的文档创建播客。这基本上是同一个模型，呃，你可以创建，你可以让它说话，呃，阅读你给它的文本，你可以让两个角色拥有不同的声音等等。这就是它听起来很棒的原因。但我想向你展示的是，实际上有一些技巧可以拥有不止两种声音。嗯，呃，原因在于，呃，我想 **Paige** 之前展示过一点，但你可以，呃，当你使用文本转语音或实时语音时，你实际上可以在提示中做很多事情，让它以不同的方式说话，带有不同的口音等等。我们将利用这一点，基本上在同一个生成中拥有不止两种声音。所以我所做的，因为我很懒，我不会那样做。我当时想大规模地做，但我基本上要求它从书中提取一段对话，然后将其改写成剧本的剧本，并将角色的名字替换为旁白，如果那只是一个旁白在说话的话，而所有其他角色都只会被命名为角色，但每个角色都有特定的风格，如果同一个角色再次出现，它就会重用相同的风格，这样同一个角色就会以相同的方式说话，拥有相同的声音。

<details>
<summary>Original English</summary>

**Guillaume**: And I think it fits as well. And I I honestly I think the the model is really good because I it's not very often that you can do those kind of demos without actually checking what's what it's going to be because I run the the notebook before, but I didn't check what the what the music were going to be looking like. And that's uh so far it worked all the time. Um one of the things that I s I forgot to say about all of that is that the way we are training our model internally is that a lot of the training data for the gen media models is actually made using Gemini. So that's the reason why Gemini is quite good at generating those prone for the gen the generative media models because it's already trained on uh on understanding what Gemini is asking for. So that's uh that's what makes the Gemini very good at at generating those um uh those prompts. And then uh the last the last model that I wanted to show is the texttospech model. So I'm pretty certain that you all have heard of this one because uh everybody loved the uh integration in Notbook LM where you could create a um um a podcast based on on your documents. And that's basically the same model that uh you can create you can ask it to to talk uh to tell read and what the text you you give it and you can have it you can have two characters with different voices and and so on. That's that's what makes it uh like nice to listen to. But what I wanted to show you is that there are actually tricks to um to have more than two voices actually. Um and uh and the reason for that is uh I think Paige showed that a bit but you can uh when you're using text to speech or live you can actually do a lot in the prompting to make it speak in in different ways with different accents with uh uh and so on and we are going to use that to our advantage to basically have more than more than two voices in in the same um in the same generation. So what I did because I was lazy I would not do that. it it was I wanted to do that at scale but I basically asked it to extract one of the dialogue from the book and then to rewrite it as as a transcript of of a play and to replace the name of the character by nar narrator if that's just a narrator talking and for all of the others is are just going to be named character but with a specific style for each of them and if the same character comes back it's it's going to reuse the same style style so that it's going like the same characters are going to have to to speak the same way and have the same voices.

</details>

**Guillaume**: 嗯，然后我正在定义声音。所以旁白将使用 **Sulafat** 的声音，无论那是什么。然后所有其他角色都将共享 **Fener** 的声音。嗯，然后我只是要求它，呃，生成内容。这里有一个关于 **TTS** 模型的小技巧，你总是必须以“阅读这个”或“告诉我这个”或任何其他方式开始。如果你只是发送文本，它会因为某种原因忽略它。所以，呃，你需要一直提示它阅读文本。但这也是你可以添加一些上下文的地方，就像系统指令的等价物，比如“以一种可怕的方式阅读这个”或者“角色非常兴奋”。所以你可以在那里添加这些细节。嗯，所以你可以看到我们得到的文本是旁白在说，然后第一个角色将以非常快的节奏，带着英国口音和积极的口音说话，嗯，然后等等。我们可以看到相同的说话方式经常出现。所以当两个角色来回对话时。所以我们来看看效果如何。

<details>
<summary>Original English</summary>

**Guillaume**: Um, and then I'm defining the voices. So the nar narrator is going to use Sulafat voice whatever it is. And then the the all of the others are going to share the fener voice. Um, and then I'm just asking it to uh to uh to generate the thing. And just one trick here with the TTS model, you always have to start with read this or uh tell me this or whatever. If you just send the text, it's it's going to ignore it for some reason. So, uh you you need to prompt it to read the text all the time. And but that's also where you can add some uh some context and like equivalent of what would be a system instructions like read this in a scary way or the characters are very excited. So that's where you can you can add those details as well. Um and so you can see the the the text that we got is narrator is saying that then the first characters is going to talk very fast-paced and with a British accent and posit accent um and then and so on and we can see that the same uh the same way of speaking is is coming often. So it's when the two characters uh going back and forth. So let's see how it goes.

</details>

**TTS 模型**: 小巧整洁的耳朵，浓密柔滑的毛发，两只动物谨慎地站着，互相打量。

<details>
<summary>Original English</summary>

**TTS 模型**: small, neat ears and thick, silky hair, the two animals stood and regarded each other cautiously.

</details>

**TTS 模型**: “你好，你好。你想过来吗？”

<details>
<summary>Original English</summary>

**TTS 模型**: "Hello, hello. Would you like to come over?"

</details>

**TTS 模型**: “哦，哦，说起来容易。”他有点不耐烦地说，因为他刚来到河边和河岸生活，还不习惯这里的一切。第二只动物什么也没说，只是弯下腰，解开一根绳子，握住它，然后轻巧地跳进一艘小船，这艘船之前没有被注意到。它外面漆成蓝色，里面是白色，大小刚好够两只动物乘坐，第一只动物的心立刻就被它吸引了，尽管他还不完全明白它的用途。划船的人熟练地划过河，系好船。然后他举起前爪，让他的客人小心翼翼地走下来。

<details>
<summary>Original English</summary>

**TTS 模型**: "Oh, oh, it's all very well to talk." He spoke rather pettishly, being new to a river and riverside life and its ways. The second animal said nothing, but stooped and unfassened a rope and hold on it, then lightly stepped into a little boat which had not been observed. It was painted blue outside and white within, and was just the size for two animals, and the first animal's whole heart went out to it at once, even though he did not yet fully understand its uses. The rower sculled smartly across and made fast. Then he held up his forpaw as his guest stepped gingerely down.

</details>

**TTS 模型**: 现在靠着那个。然后轻快地走。

<details>
<summary>Original English</summary>

**TTS 模型**: Lean on that now. Then step lively.

</details>

**TTS 模型**: 令他惊讶和狂喜的是，他发现自己真的坐在了一艘真正的船的船尾。这是多么美好的一天啊。你知道吗，我这辈子从没坐过船。

<details>
<summary>Original English</summary>

**TTS 模型**: To his surprise and rapture, he found himself actually seated in the stern of a real boat. This has been a wonderful day. Do you know I've never been in a boat before in all my life.

</details>

**TTS 模型**: 什么？从没坐过船？你从没？好吧，我，你一直在做什么呢？他很乐意相信这一点，因为他靠在座位上，打量着坐垫、船桨、桨架和所有迷人的配件，感受着船在他身下轻轻摇晃。有那么好吗？好？这是唯一的事情。相信我，我的年轻朋友，没有什么，绝对没有什么，比简单地在船上瞎玩更值得做的事了。简单地在船上瞎玩。

<details>
<summary>Original English</summary>

**TTS 模型**: What? Never been in a You never Well, I What have you been doing then? He was quite prepared to believe it as he lent back in his seat and surveyed the cushions, the oes, the rollocks, and all the fascinating fittings, and felt the boat sway lightly under him. Is it so nice as all that? Nice? It's the only thing. Believe me, my young friend, there is nothing, absolute nothing, half so much worth doing as simply messing about in boats. simply messing messing about in boats messing.

</details>

**TTS 模型**: 往前看。太晚了。船撞上了。

<details>
<summary>Original English</summary>

**TTS 模型**: Look ahead. It was too late. The boat struck

</details>

**Guillaume**: 基本上你猜不到它实际上对这两个角色使用了相同的声音。它们是如此不同。所以这真的是一种很酷的方式，可以创建多角色对话。所以你可以使用它。呃，最后一件事是，呃，正如我们所说，**Gemini** 模型默认是多模态的。所以我当时正在使用一本书，呃，但你也可以发送有声书或电影，或者一些不太长的电影，但你可以做同样的事情，呃，使用所有多模态输入可能性，呃，让 **Gemini** 创建东西，呃，来插图其他，嗯，其他模态。嗯，我们还有多少时间？嗯。

<details>
<summary>Original English</summary>

**Guillaume**: basically you couldn't guess that it's actually using the same voice for the two characters. They are so much different. And so that's that's that's that's really actually a really cool way of like uh creating those discussions with multiple characters. So I can use it. And uh the last thing is that uh as we said like the Gemini models are multimodel by by default. So I was I was using a book uh but you can also send an audio book or movie or some like not too long movie but you could you could do the same things with uh with using all of the multimodel input possibilities to uh to have Gemini create things uh for to illustrate other um other kind of modalities as well. Um how much time do we have? Um

</details>

### AI Studio 与 LIA 实时音乐演示

**Guillaume**: 我说过我要给你们看，呃，实时模型。所以这是一个非常好的，非常酷的例子，哦不，停。我先给你们看一些东西。呃，**Paige** 制作了一些可以在 **ICO** 中构建的酷炫示例。所以我想尝试的一件事基本上是做我在笔记本中做的事情，这有点冗长和复杂。所以我所做的就是基本上复制粘贴了它。你能构建一个应用程序，它使用生成式媒体模型来插图一本书，就像这个 **Python** 笔记本中描述的那样吗？我只是粘贴了笔记本的所有内容，然后构建它，我们看看效果如何。

<details>
<summary>Original English</summary>

**Guillaume**: I I said I was going to show you the uh realtime model. So this is a very good a very cool example that Oh no stop. I'm going to show you something be before. Uh Paige made some example of cool things that you can build in ICO. So one of the thing I wanted to try was basically to do the same thing as what I do in the in the notebook which is kind of lengthy and quite complicated stuff. So what I did is I basically copy paste it. Can you build an app that that illustrates a book using gen media models as described in this Python notebook and I just paste all of the content of the notebook and and build it and we'll see how it goes.

</details>

**Guillaume**: 嗯，这可能需要很长时间，就像之前花了 15 分钟，所以你可能不想等那么久，但是，呃，我可以在这期间给你们看 **Space DJ**。所以，呃，正如我所说，模型会实时生成音乐，这是一个演示，他们制作了一个像星星一样的宇宙，行星就是提示。所以如果我们靠近一些行星，它应该会开始播放音乐。

<details>
<summary>Original English</summary>

**Guillaume**: um it can take quite a long time like earlier it took 15 minutes so we you might not want to wait for that but uh we I can show you space DJ in the meantime. So uh as I said the model generates uh music in real time and this is uh this is a a demo where they made a a star like universe of stars and the the planets are prompts. So if we go closer to some planets it should start playing music.

</details>

**LIA 模型**: (播放音乐)

<details>
<summary>Original English</summary>

**LIA 模型**: (Music plays)

</details>

**Guillaume**: 然后如果你慢慢地去别的地方。是的。我们，是的。我想在中间区域。看，呃，我真的很惊讶，人们没有用这个模型做更多的事情，因为它太有趣了。

<details>
<summary>Original English</summary>

**Guillaume**: And then if you slowly somewhere else Yeah. We Yeah. I guess in the middle uh area. See you. Uh I'm really surprised like people are not doing more things with this model because it's it's so funny to go

</details>

**Guillaume**: 而且有自动驾驶功能，所以你可以让它自己移动 10 分钟，然后，呃，听音乐实时变化。嗯，这很酷。嗯，我们看看这里怎么样。是的，它正在思考。但让我给你们看看我之前运行它时它做了什么。哦，我让我的笔记本电脑开着半个小时，只是为了让它不要那样做并刷新页面。所以，我想我输了。嗯，但基本上它之前就是这样做的，嗯，就像你看到的，只是提示，没有别的。一个非常长的提示。

<details>
<summary>Original English</summary>

**Guillaume**: and there's an autopilot so you can just let it move around for for 10 minutes and then uh listen to the music changing in real time. Um that's kind of cool. Up. Let's see how it goes here. Like, yeah, it's thinking. But let me show you what it what it did before when I ran it. Oh, and I I kept my laptop open for half an hour just so that it would not do that and refresh the page. So, I guess I lost. Um, but that's basically what it did in uh in uh like earlier just uh as you can see just the prompt and nothing more. a very long prompt

</details>

**Guillaume**: 呃，呃，它花了大约一千秒，也就是 15 分钟，如果我没记错的话，嗯，来创建这个应用程序，但它基本上做的完全一样，所以我可以选择文件并上传它，这会花一些时间，但基本上，相信我，它做的完全一样，呃，就像笔记本所做的那样，这真的很令人印象深刻，它第一次就成功了。嗯，最后，我做的一件事是，当我在进行 **vibe coding** 时，呃，当它工作时，我总是会有那些，呃，关于如何让它生成小程序或应用程序的说明。呃，其中一个原因是我希望应用程序尽可能容易地供我审查，因为我想避免像 **Paige** 之前发生的那样，有些东西不工作，然后你需要找出问题所在，并要求模型修复它。嗯，所以我的一个关键技巧是，我要求模型为每个功能创建不同的文件，这样，呃，每当我需要审查一些东西时，我就可以快速检查，比如我要求它修改这个功能，它却更新了一些与此无关的东西。所以我从一开始就知道那里有问题，我会在我的审查中更加注意。还有一些说明，我不明白为什么任何 **vibe coding** 工具默认都没有，那就是添加日志，因为当你需要，呃，当你需要调试时，你只知道错误消息是不够的。你需要知道之前发生了什么，以及正在发生什么，因为你知道你需要知道它发生在哪里。所以，呃，我真的建议你，呃，在你进行 **vibe coding** 时使用这些类型的指导方针，我们现在可以看看效果如何。哦，还有一些东西。我想 **Paige** 没有展示，但如果你愿意付费，你可以在这里添加一个 **API 密钥**，然后当你使用 **AI Studio** 进行 **vibe coding** 时，你将拥有更多的配额来使用 **Gemini**。

<details>
<summary>Original English</summary>

**Guillaume**: up uh and uh it took something like like a thousand seconds so like 15 minutes if I'm not wrong um to create the app but that's basically doing exactly the same thing so I can choose the file and upload it and it's going to take some times but basic like trust me it's doing exactly the same thing uh as as what the notebook was doing and that's really like quite impressive that It's doing that uh on the first try right away. Um and just to finish I one of the thing I'm doing when I'm vibe cutting uh while it's working is that I always have those uh instructions on how to get uh to get it to generate um applets or apps. Uh, and one of the reason for that is that I want the apps to be as easy for me as to review as possible because I want to avoid exactly what happened to page earlier that something was not working and then you you need to figure out what it is and ask the model to fix it. Um so one of one of my key tricks is that I'm asking the model to create different files for each uh each feature so that uh whenever I need to review something I can quickly check like I ask it to modify this feature it's it's updating something that has nothing to to do with it. So I know from the start that there's something wrong going there and I will be more for in the in my in my reviews and all. And also some instructions that I I don't understand why it's not by default in any vibe coding uh tool which is add logs because when you need to uh when you need to debug you you just know the error message is not enough. You need to know what's happening before and what's happening like because you know you need to know where where it's happening. So that's uh I really recommend you to uh to to use those kinds of of guidelines whenever you you vodit things and we can see how it goes now. Oh, and something there. I don't think Paige showed it, but if you are if you're willing to pay, you can add an API key here and then you are going to have more uh more kota to use Gemini when when you are vi coding on on AI studio.

</details>

**Guillaume**: 呃，我想我只会让你展示你的演示，也许我之后可以展示它看起来怎么样。

<details>
<summary>Original English</summary>

**Guillaume**: Uh I think I will just let you show your demos and maybe I can show you afterwards how it looks uh after.

</details>

**Audience**: 是的，当然。对于视频模型，当你生成视频时。它是否使用你的模型来生成，还是只是...

<details>
<summary>Original English</summary>

**Audience**: Yeah, sure. for the video model when you generated the video. Is it using your models to generate that or is it just

</details>

**Guillaume**: 是的，目前只是 **VO**。有没有办法编排所有模型并将它们组合起来，还是你必须只使用这些来生成？

<details>
<summary>Original English</summary>

**Guillaume**: Yeah, it's just view at the moment. Is there a way to orchestrate all the models and put them together or do you have to just use those generate?

</details>

**Guillaume**: 哦，如果你想在 **VO** 视频中使用 **LIA** 生成的音乐，例如。呃，不，你没有办法做到。这更多是因为模型的限制，**VO3** 生成并非旨在能够摄取音频文件。所以，呃，这就是为什么它受到限制。呃，但我猜未来是，我们希望每个模型都能摄取所有模态，这样你就可以做到。呃，同样，我想，呃，即使对于 **LIA** 模型，能够摄取音频模型也是有意义的，这样它就可以用作参考，或者即使你想进行多轮对话，然后说“好的，我喜欢你的歌，但结尾有点，呃，不够史诗，所以让它更史诗一点”，这样它也许只会更新结尾。所以是的，目前不可能，但这是它发展的方向。呃。

<details>
<summary>Original English</summary>

**Guillaume**: Oh, if if you want to use the music generated by Lia in the V the video video for example. Uh no, you don't have a way to do that. It's it's more it's more because of the model limitations that the VO3 generation was not meant to be able to uh to ingest audio files. So uh so that's why it's it's limiting. Uh but I guess like the future is that we want every model to be able to ingest all modalities so that we you can you can do that. Uh same thing I think uh it would make sense even for Laria model to be able to uh ingest audio models that it can so that it can be used as references as well or even if you want to do multi-turn and say okay I love I love your song but the the ending was a bit uh uh not not epic enough so make it make it more epic so that it would maybe just just update the the end of it. So yeah, it's not possible at the moment, but that's the direction it's it's going. Uh

</details>

**Audience**: 性能真的对 **Ven** 中的音乐很特别吗？

<details>
<summary>Original English</summary>

**Audience**: performance really specific for the music in Ven.

</details>

**Guillaume**: 不，我不会尝试用 **VO** 来制作任何类型的音乐，就像，呃，背景音乐的训练数据可能非常少，因为它总是做那种非音乐的东西。嗯，所以，呃，不，但再次强调，所有这些模型或多或少都是一起训练的，并共享一些训练数据。所以我相信下一代 **VO** 会在这方面做得更好。只是当前这一代是一年前发布的，一年前我们还没有音乐生成模型，就像我们之前谈到的视频中的文本一样，呃，一年前 **Nano Banana** 甚至不叫 **Nano Banana**，它叫 **Gemini 1.5 Image**。**2.0 Image**，呃，生成之类的，而且它，呃，它在文本方面没有那么好。所以，呃，是的，这只是一个模型代际的问题。

<details>
<summary>Original English</summary>

**Guillaume**: No, I I wouldn't try VO for for any kind of music like I the the the training data for for the background music and like is very is likely very light because it's always doing the same kind of non-m music things. Um so uh no but once again all of those models are trained more or less together uh and share some training data. So I'm sure the next generation of VO is going to be better at that. It's just that the current one it it shipped a year ago and a year ago there was pl like we didn't have music generation models like we talked earlier about text in videos and uh and like a year ago nano nano banana was not even called nano banana it was Gemini 1.5 image. 2.0 image uh generation something uh and it was uh it was not as good at as as text. So that's uh yeah it's just uh just a question of of generation of models uh there.

</details>

**Guillaume**: 哦，我忘了说一些事情，呃，当它工作时，嗯，如果你想运行笔记本，呃，因为你也必须删除它。嗯，这里，这里当我开始时，是的，我创建了聊天，我添加了这一行，上面写着“服务层优先级”。这实际上是我们上周发布的东西。嗯，这是一种指示方式，当你提示模型时，如果你想要，呃，如果它不那么重要，你不在乎延迟，但你在乎价格。所以有一个服务层叫做 **flex**，它基本上说，呃，请求可能需要几分钟才能通过，但它会是异步的。所以这有点像使用批处理 **API**。另一方面，因为我想确保它今天能通过，你可以说这是一个优先级请求。所以它会有稍微高一点的优先级，而且，呃，它应该不会，呃，它会更可靠，但你要支付两倍的价格。所以，呃，如果你自己运行它，你可能想删除那一行以节省一点。嗯，我们可以看看这里怎么样。哦，你看，就像我说的，这个模型需求量很大。所以，是的，嗯，我很抱歉。它，它是一个，模型太，呃，太，太好了，每个人都想用它，我们没有足够的容量。所以如果你有，如果你有任何多余的 **TPU** 可以分享，嗯，我们可以做个交易。你有一个问题。

<details>
<summary>Original English</summary>

**Guillaume**: Oh and I forgot something to uh while it work um if you want to run the to run the notebook uh because you will have to remove it as well. Um here here when I started yeah I created the chat I I added this line that says service tier priority. It's actually something that we shipped last week. Um and that's a way for to indicate when you are prompting the models to if you want uh if it's not that important you don't you you don't care about the latency but but you but you care about price. So there's uh a service tier that is called flex and basically that says uh the the request can take a few minutes to go through but it's going to be alic. So it's kind of the same thing as uh as using the batch API. And on the other end, because I wanted to be sure that certain that it would go through today, you can you can say that it's a priority request. So it's going to have slightly higher priority and that uh it should not uh it's it's going to be more reliable, but you're going to pay twice the price. So uh if you're running it by yourself, you might want to remove that line to save a bit. Um and we can see how it goes here. Oh, and see as I said like this model is in high demand. So yeah, that's um I'm I'm sorry about that. It's it's a the model is too uh to uh too too good people everybody wants to use it and we don't have enough capacity. So if you have if you have any spare TPU to uh to share um we can make a deal. You have a question.

</details>

**Audience**: 你们计划将这个模型的变体开源吗？比如通用的，但用于艺术。

<details>
<summary>Original English</summary>

**Audience**: Do you plan to put like variations of this model open like general but for art.

</details>

**Guillaume**: 嗯，所以问题是，呃，对于视频，问题是是否会有任何开源的生成式媒体模型，基本上。

<details>
<summary>Original English</summary>

**Guillaume**: Um so the question like for the video for the question is will will there be any open weight gen media model basically

</details>

**Guillaume**: 嗯，所以我不认为图像和视频生成会开源，呃，老实说。嗯，我看到的一个原因就是所有，嗯，不是安全，而是，嗯，当你生成图像或视频时，我们会对你要求的内容以及实际生成的内容进行大量检查，我们正在阻止一些不符合我们愿景的东西，我觉得当你有一个开源模型时，它更像是开放酒吧，你可以让它生成任何你想要的东西，所以我想这会是我们的，呃，我们的公司价值观会限制我们。嗯，话虽如此，例如对于音乐，开源是有意义的，呃，特别是如果你想要实时，它在设备上运行会更快。所以这可能在某个时候会出现。嗯，酷。是的，我想我们会在 **Gemma** 演示之后看看它是否表现更好。嗯，是的，希望它有趣。

<details>
<summary>Original English</summary>

**Guillaume**: um so I don't think so for image and video generation uh to be honest um one one of the reason I see behind that is all of the um not sec like security but like the um when when you when you generate images or videos um we do a lot of checks about what you are asking for and what what is actually being generated afterwards and we are blocking a a couple of things that are not aligned with our our visions and I I feel like whenever you have an open weight model for that it's it's more like open bar and you can you can have it generate whatever you want so that's I think that's that's going to be where our uh our company values are going to be uh to be limiting us um that said for example for music it would make sense to uh like especially if you want real time, it would make sense to be uh to be uh to be on device so that it's it's it's doing it faster. So that that's something that might come at some point. Um cool. Yeah, I think we'll see after the Gemma demos if uh if it works better. Um yeah, hope it was interesting.

</details>

**Audience**: 谢谢你。

<details>
<summary>Original English</summary>

**Audience**: Thank you.

</details>

### Gemma 4 开源模型介绍

**Guillaume**: 所以，呃，**Ian** 基本上是我的，我的对应方。我只从事生成式媒体模型的工作。**Ian** 从事 **Gemma** 模型的工作，他将向你们展示，呃，上周最大的发布是 **Gemma 4**，他将向你们展示这个模型有多酷。

<details>
<summary>Original English</summary>

**Guillaume**: And so uh Ian is uh basically my my counterpart. I work only on gen media model. Ian is working on Gemma models and he's going to like the biggest release of last week was Gemma 4 and he's going to show you how cool the model is.

</details>

**Ian Valentine**: 谢谢你。

<details>
<summary>Original English</summary>

**Ian Valentine**: Thank you.

</details>

**Ian Valentine**: 是的。正如 **Guillaume** 所说，我叫 **Ian Valentine**。我是一名开发者关系工程师，从事 **Gemma** 模型的工作。这是一次即兴演讲。呃，我们显然因为今天发生的一切，呃，我们已经完成了 **Paige** 提到的，我们将进行两场会议，只是快速过一遍大量内容。我们本周还有一些 **Gemma** 的演讲。呃，我相信 **Omar** 将在周五做一个主题演讲，他将涵盖很多关于 **Gemma** 是什么以及为什么你应该感兴趣的内容。所以我会快速讲解那一部分。嗯，我们明天还有另一个演讲，关于我们称之为“主权逃逸速度”的东西。所以就像你如何掌控 **AI** 并在你的设备上或你自己的云上或手机上运行东西，希望我在这里谈到的一些内容能实现其中的一部分。所以这更多是关于“为什么”。我只是想向你展示“它是什么”。这样说得通。所以我们插上电源吧。我需要哪个？抱歉。

<details>
<summary>Original English</summary>

**Ian Valentine**: Yes. So as G mentioned, my name is Ian Valentine. I'm a developer relations engineer working on the gem models and this is an impromptu talk. Uh we obviously because of everything that's happened today uh we've done Paige mentioned that we've we're going to do two sessions just kind of go through a whole load of stuff. We have a number of Gemma talks for the rest of the week as well. Uh Omar is going to do a keynote on Friday I believe which is going to cover a lot of like the what gem is and why you should be interested. So I'm going to like speedrun that section. Um and we have another talk tomorrow on uh what we've called sovereign escape velocities. So like how you take ownership of AI and run things on your device or on your own cloud or on phones and hopefully some of what I talk about here is going to be like a realization of some of that. So that's a little bit more about like the why. I'm just going to show you the what it is. That makes sense. So let's get plugged in while we do that. Which one do I need? Sorry for

</details>

**Audience**: 这个神奇的。是的。只要我能看到视频。

<details>
<summary>Original English</summary>

**Audience**: this magic one. Yep. soon as I get a video in.

</details>

**Ian Valentine**: 你有音频吗？

<details>
<summary>Original English</summary>

**Ian Valentine**: You have any audio?

</details>

**Audience**: 呃，没有。我们先不带音频。

<details>
<summary>Original English</summary>

**Audience**: Uh, no. Let's go with no.

</details>

**Ian Valentine**: 我们会先尝试展示没有音频的。呃，好的。所以，正如我所说，这是非常即兴的，所以我们只能随机应变。呃，但我会讲一些内容，当我们屏幕亮起来的时候，我会展示一些东西。哦，你需要我把它移到一边吗？还是我可以镜像？

<details>
<summary>Original English</summary>

**Ian Valentine**: We'll try and show the ones without audio first of all. Uh, okay. So, as I mentioned, this is super impromptu, so we're going to go with whatever we get. Uh, but I will go through I'll just show you a couple bits when we get the screen up. Oh, do you need me to move it to one side? Or can I do a mirror?

</details>

**Audience**: 我们镜像吧。

<details>
<summary>Original English</summary>

**Audience**: Let's do mirror.

</details>

**Ian Valentine**: 我们镜像吧。呃，哪里？是的，你来吧。

<details>
<summary>Original English</summary>

**Ian Valentine**: Let's do mirror. Uh, where? Yeah, you go for it.

</details>

**Ian Valentine**: 完美。是的。所以，我希望向你们展示一点的是，呃，你知道 **Gemma** 模型可以在哪些设备上运行。我会非常简要地谈谈不同大小的 **Gemma** 模型，呃，我们上周在 **Gemma 4** 中发布了什么，因为它刚刚发布。嗯，希望能让你们感受到，现在你们可以在本地或在单个 **GPU** 上运行的那种功能，这在六个月前可能还做不到。好了，来了。完美。嗒哒。所以，**Gemma 4**。万岁。呃，这是上周四发布的。嗯，它是一个由四个模型组成的家族。所以我们有所谓的有效模型，**E2B** 和 **E4B** 模型。这些模型设计用于在手机、**Raspberry Pi**、**Jets** 和 **Nanos** 等非常小的低端硬件上运行。呃，其中的 **E** 部分是我们总是被问到的问题。有效是因为模型架构具有逐层嵌入结构，这意味着嵌入实际上不需要作为模型的一部分加载。所以你可以在闪存上运行它们，然后你可以在模型需要时分页加载嵌入。所以我们所描述的模型的大脑大约是 20 亿参数，大约 40 亿参数，但如果你将所有这些都加载到 **RAM** 中，它会比这更大一些。它更像是 50 亿和 80 亿参数的模型。嗯，所以这就是为什么它被称为 **Effective 2B**。呃，我们还有一个 **26B**，它是一个混合专家模型，激活了 40 亿参数，我们还有一个 310 亿参数的密集模型，这是我们的旗舰大型模型。嗯，两个更大的模型，**26B** 和 **31B**，都设计用于在笔记本电脑和台式机上运行，或者根据你需要的精度和量化，在单实例 **GPU** 云上运行。所以，我不会深入探讨这一点，但你可以想象，你现在可以做的很多功能，你可以在一台拥有足够 **RAM** 的 **MacBook** 上，或者，你知道，一块 5090 或类似的东西上完成。这就是我们现在所处的位置。嗯，为什么这些对我们来说令人兴奋和有趣？因为有了这些模型，我们专注于代理方面。所以它们现在内置了思考能力。它们是多模态的，所以它们可以理解图像、音频、视频。顺便说一下，音频只适用于两个较小的模型。在手机上运行的有效模型可以理解音频，但其余模型可以理解图像和视频。我们看到模型的性能比参数大小大 10 倍的模型还要好。所以以前可能需要集群才能完成的工作，现在你可以在单个 **GPU** 上完成类似的功能。所以这正是我们看到一些创新的地方。嗯，我将直接跳到演示部分。哦，我将展示这张幻灯片。我喜欢这张。这张幻灯片很好地解释了我们从何而来。所以，**Gemma 2** 模型，你可以看到，在中间，我们，你知道，特别擅长创意写作，但，呃，在其他不同能力方面分布不那么均匀。随着我们经历了 **Gemma 3**，然后现在是 **Gemma 4**，我们已经平衡了模型的整体能力。我们在编码、函数调用方面做得更好，行动执行都内置在模型架构的设计中，而不是依赖于，呃，像强大的指令遵循能力，我们发现这对于更大的模型更重要。所以这些模型从一开始就设计了这些功能。所以，呃，我们来看看，呃，这些都是 **Omar** 演讲的剧透。所以我要直接跳到这里的演示部分。我将向你展示这个。

<details>
<summary>Original English</summary>

**Ian Valentine**: Perfect. Yeah. So, what I'm hoping to show you a little bit is uh you know some of the things that uh some of the devices that Gemma models can run on. Like I'll talk very briefly about the different size of Gemma model uh what we released in Gemma for last week because it's brand spanking new. Um and hopefully show you give you kind of a feel of like the kind of capabilities that you can now do either locally or that you can run on like a single GPU that maybe you couldn't like six months ago. There you go. Here we go. Perfect. Tada. So, Gemma 4. Hooray. Uh, so this was released last uh Thursday. Um, it's a family of four models. So, we have what we call the effective models, the E2B and the E4B models. And these are models designed to run like on mobile phones, Raspberry Pies, Jets, and Nanos, kind of like very small low-end hardware. Uh, the E part of it is the question we always get asked. The effective is uh because the model architecture has a per layer embedded structure which means that the embeddings actually don't need to be loaded as part of the model. So you can have them running on flash um and then you can page in uh the embeddings as they're needed for the model. So the actual what we kind of describe as like the brain of the model is about a two billion parameter about four billion parameter but if you put all of it in RAM it's a bit bigger than that. It's kind of more like a five and an 8 billion parameter model. Um so that's why it's called effective 2B. Uh we also have a 26B which is a mixture of experts model with 4 billion activated and we have a 31 billion parameter dense model which is our like our flagship kind of big model. Um and both of the two bigger models the 26 and the 31 are designed to be able to run on like laptops and desktops or like single instance GPU clouds depending on like the precision and quantization you need. So, not going to get into that, but just imagine that a lot of the capabilities you can do right now, you could do on like a MacBook with, you know, enough RAM or a, you know, a 5090 or something like that. That's kind of where we're sitting right now. Um, why are these kind of exciting and interesting to us? Because with these models, we're focusing kind of on the agentic side. So, they now have thinking built in. They are multimodal, so they can understand image, audio, video. Uh audio by the way is just for the two smaller models. The effective models that run on the phone can understand audio but the rest can understand image and video. And we're seeing uh performances offer models that are in the range of like 10x bigger than it in terms of parameter size. So what might have required a cluster now you could do same kind of capabilities for uh for a single GPU. So that's kind of really where we're seeing um some innovation here. Um, and what I'm going to jump straight into is I want to show you the demo section. Oh, I I'll show you this one slide. I I like this one. This is quite kind of explains a little bit where where we've come. So, the Gemma 2 models, you can see like right in the middle, we're kind of, you know, particularly good at creative writing, but uh uh not so kind of evenly spread amongst amongst other different capabilities. And as we've kind of gone through Gemma 3 and then now through Gemma 4, we've kind of evened out the overall capabilities of the model. We've got things that are much better at coding, much better at function calling, action taking is all kind of built into the design of the architecture of the model rather than relying on uh like strong um instruction following capabilities which we find with bigger models is is kind of more important. So the models are designed with that from the ground up. So uh let's go over to uh this is all spoilers from Omar's talk. So I'm going to go straight to the demo section here. I'll show you this one. So,

</details>

### Gemma 4 手机端代理技能演示

**Ian Valentine**: 这是 **Google AI Edge Gallery** 应用程序。呃，有人试过这个应用程序吗？呃，有，呃，一两个，好吧，少数几个人。所以，你可以在 **Play Store**、**App Store** 上下载这个应用程序。嗯，它可以在 **Android** 和 **iOS** 上运行。嗯，它是一个让你测试和尝试模型的方式。所以，我们发布了一个新功能叫做 **Agent Skills**。**Agent Skills** 允许你为在手机上物理运行的模型设置技能。所以这个模型，这是 **E2B** 模型，它实际上运行在，呃，一个 **Pixel** 手机上，我想是这样。你可以提示它，你可以测试不同的功能。所以它有效地获得了一组，嗯，技能，这些技能定义了像 **Android intents** 这样的东西，你可以实际触发和调用其他应用程序，或者你可以编写自己的 **JavaScript** 技能，或者运行一个 **web view**，呃，你可以指示模型，它会决定如何实际触发这些。所以你可以让它，例如，将东西添加到这个研究追踪器中，或者你可以向研究追踪器提问，它会调用正确的函数来拉取数据。所以，我们已经从只能在手机上聊天，到现在你可以给它一些更模糊的输入，它能够决定，呃，调用哪些函数。呃，下一个，如果它播放的话。是的。所以，在这个例子中，我们有许多不同的，我最后再展示那个。好了。呃，许多不同的技能，你可以尝试。所以从，你知道，在地图中加载位置，到，呃，像，呃，呃，使用 **API** 和其他服务。嗯，所以你可以自己构建这些东西，或者你也可以只使用一些预加载的来尝试理解它能做什么。这就像我们进行这种操作的游乐场。然后最后我想展示的是，呃，这是左侧的 **2B** 模型。所以你可以，你也可以尝试在设备上进行 **vibe coding**。这个模型实际上非常擅长做这个。你不会构建一个，你知道，大型架构系统，但它可以做，你知道，小的网络应用程序，可以理解许多不同的语言。呃，你可以用 **Python**、**HTML**、**TypeScript** 编写东西。呃，它可以验证一些东西，而且，你知道，你可以构建一些可以在手机上运行的小应用程序。所以你基本上可以在你的手掌中拥有整个反馈循环。所以这个，他们只是生成了一个非常简单的计算器，重要的是它实际上支持除以零并正确给出错误。所以它甚至能够推理这些类型的事情，并且，呃，添加，我想目前它是在关闭思考功能的情况下，但如果你打开思考功能，我们会看到输出质量会有一个提升，呃，在模型实际能够推理的方面，因为它在实际执行之前添加了那个规划步骤。

<details>
<summary>Original English</summary>

**Ian Valentine**: So, this is the uh Google AI Edge Gallery app. Uh has anybody tried this app yet? Uh have uh one, two, okay, like a handful of people. So, you can download this on Play Store, App Store. Um it works on Android and iOS. And uh what it is is it's uh it's a way that you can test and try the models. So, we released a new feature called agent skills. And what agent skills allows you to do is it allows you to set up skills for the models that run physically on the phone. So this model, this is the E2B model is running literally on uh a pixel I believe in this case. And you can prompt it and you can test out the different capabilities. So it's effectively given a set of um uh skills that define things like Android intents where you can actually trigger and call other apps or you can write your own JavaScript skills or like run like a web view and uh you can instruct the model and it will make a decision about how to actually trigger these. So you can get it to for instance add things to this uh research tracker or you can ask it questions about the research tracker and it will call the correct function to pull that data back. So, we've gone from like a world of just being able to chat with it on your phone to now that you can give it some more ambiguous input and it's able to make a decision about uh what functions to call. Uh the next one if it plays. Yeah. So, in this uh in this example, we've got a number of different I'll show you that one last. There we go. Uh a number of different skills that you can try out. So everything from just like you know loading locations in maps to uh like uh uh using APIs and other services. Um so you can build these things yourself or you can just use some of the pre-loaded ones to try and understand what it's kind of capable of. And this is like our playground for kind of doing so. And then lastly I wanted to show that uh this is the 2B model on the left hand side. So you can you could also try things like vibe coding on device. The model's actually quite capable of doing this. You're not going to build like you know a big architectural system but it can do you know small like web apps that understands lots of different languages. Uh you can write things in Python, HTML, TypeScript. Uh it can validate some of the stuff and uh you know you could build like little apps that can run on the on the phone itself. So you kind of got the whole feedback loop just on in the palm of your hand basically. So this one they just generated like a really simple calculator and importantly it does actually support divide by zero and gives an error correctly. So it's even able to reason about those kind of things and to uh to kind of add I think this at the moment it's got with thinking turned off but if you add thinking turned on we see that you get a bump in terms of the quality of the output in term uh in terms of what the model's actually able to reason about because it adds that planning step before it actually does the execution.

</details>

### Gemma 4 本地模型与多代理协作

**Ian Valentine**: 好的。所以，接下来我将向你们展示一个在设备上运行的演示。嗯，这里有多少人使用过或正在使用 **LM Studio** 或 **Ollama** 或任何这类工具？好的，大概三四个人。嗯，所以这实际上很有用。所以，当我们构建这些模型时，对我们来说非常重要的一件事是使其与生态系统中的许多工具兼容。所以我们与像 **Ollama**、**LM Studio**、**VLM**、**SG Lang** 这样的公司合作，以确保我们的模型能够很好地与它们配合，并且能够高效地部署。嗯，**LM Studio** 有点像一个用于运行本地模型实例的工具。所以在这个例子中，我只是让 **26B** 模型在我的设备上运行，你可以，呃，你可以从这里加载它，目前这个模型已配置。这个模型目前需要大约，呃，它说 7-18 GB，但如果你添加足够的内存来处理你正在寻找的上下文，它可能需要大约 22 GB 的 **RAM**。这是一个 **M4 Mac**，所以显然它有统一内存，所以你可以运行它，但如果你想要完全的性能，你需要有一个足够 **RAM** 的 **GPU** 才能运行整个模型。正如我所说，**26B** 模型是一个混合专家模型。所以它实际上只需要，呃，40 亿激活参数。所以它比 **31B** 模型快得多，但它比一个只有 40 亿参数的模型更智能。所以，呃，关于这个模型的一个很酷的地方是，有了这些模型，你可以在本地机器上通过兼容的端点来提供服务。所以，呃，就像 **OpenAI** 兼容的端点或 **Anthropic** 兼容的端点。然后你可以将它们与其他应用程序一起使用。所以我要在这里做的是，我将在这个端口 1234 上提供这个模型，然后我可以使用其他应用程序直接调用这个模型的聊天完成 **API**。所以做这个的代码就像 **OpenAI**，呃，**Open Chat Completions**，然后指向这个服务器，这相当于只是使用你的本地机器，而不是使用云机器。所以我将在这里运行一个终端。我将做 **demo SVG space**。所以，我要做的是，我将创建一个协调器实例，然后我将创建 10 个子代理，它们将为我生成 **SVG**。所以，它们被告知要做的一切，呃，实际上让我确保我关闭思考功能，以确保它超级快。呃，很高兴我记住了这一点。好的。所以，这里的每个终端都是一个独立的代理。你可以看到协调器就是这个。呃，所以它将这些决策分配给所有不同的子代理，每个子代理都被赋予了不同的绘制任务。所以你可以看到，这对于你在本地机器上进行某种快速原型设计来说是一个非常好的方法。呃，你不需要互联网来做这个。角落里的吞吐量是每个单独的子代理正在完成的组合 token 生成量。所以当它们最终将所有东西组合在一起时，协调器将把这些编译成一个页面，你就会得到一个由它们生成的不同 **SVG** 组成的可爱数组。所以你可以想象这可以是任何你想要在你的机器上完成的代理任务。你知道，整理文件，实现代码片段，进行细分研究，分析数据，诸如此类。嗯，你可以给它们分配非常不同的任务来完成。所以有些已经完成了。这很好。所以希望很快就会出现一些东西。好了。所以这些就是我的 **SVG**。所以，哦，它们还不错，对吧？正如我所说，哦，这个是动画的。一个旋转的行星。所以它不知何故弄清楚了如何让它看起来像是动画的，这很酷。是的。而且这是关闭思考功能的情况。所以如果我打开思考功能，它会在规划阶段进行更多的思考，你通常会得到更好的 **SVG**。就像花更多时间思考会产生更好的 **SVG**。

<details>
<summary>Original English</summary>

**Ian Valentine**: Okay. So, next I'm going to show you a demo running on the device. Um, who here has used or uses LM Studio or uh Olama or any of those kind of tools? Okay, so like maybe like three or four people. Um, so actually this is useful. So, one thing that's really important to us when we build these models is making it compatible with a lot of the tools in the ecosystem. So we partner with uh folks like Alama, LM Studio, VLM, SG lang to make sure our models kind of like work really well with them and that they can be deployed efficiently. Um LM Studio is kind of like uh a tool for running local model instance. So in this case, I'm just got the 26B model running on my device and you can uh you can load it from here and at the moment this one is configured. This one will take about uh at the moment it says seven 18 gigabytes but if you add for instance the uh enough memory to do the kind of context you're looking at be like 22 GB uh of uh RAM required to do it. This is an M4 Mac so obviously has unified memory so you can you can run that but you would need if you wanted like full performance you'd need to have a GPU with enough RAM to be able to run the whole model. And as I mentioned, the 26B model is a mixture of experts. So it uh actually only needs uh 4 billion activated parameters. So it's much quicker than the 31B model, but it is more intelligent than just a 4 billion parameter model would be. So uh one cool thing about this is that with these models, you can serve them uh on your local machine uh via a compatible endpoint. So uh like an OpenAI compatible endpoint or an anthropic compatible endpoint. and then you can use them with other apps. So what I'm going to do here is I'm just going to serve this model uh on port 1 2 3 4 and then I can use other apps to call uh the chat completions API directly on this one. So the code to do this would be like open AI uh open chat completions and then point it at this server and it would be the equivalent of just using your local machine rather than using a cloud machine. So I'm going to run a uh terminal here. I'm gonna do demo SVG space. So, what I'm going to do is I'm going to create uh one orchestrator instance and then I'm going to create 10 sub aents and they're going to generate SVGs for me. So, all they're going to be told to do uh actually let me make sure I turn thinking off to make sure it's super fast. Uh glad I remembered that. Right. So, each of these terminals here is a separate agent. And you can see the one the orchestrator is this one right here. Uh so it's farming out those decisions to all the different sub aents and each of those sub aents has begin been given a different thing to draw. So you can see this will be like a very good way for you to do some kind of quick prototyping on your local machine. Uh you don't need the internet to do this. And the throughput in the corner up there is how much combined token generation is being done by each individual um sub aent. So when they finally put it all together, the orchestrator will just compile this into a page and you get like a lovely array of different SVGs that they've generated. So you can imagine this being any kind of aentic task that you want to be able to do on your machine. You know, sorting out files, implementing bits of code, doing like subdividing research, analyzing data, that kind of stuff like that. Um, and you can give them all very different jobs to do this. So some of them have finished already. That's good. So something hopefully will pop up in a second. There you go. So there are my SVGs. So Oh, they're not too bad, are they? And as I mentioned, oh, this one's animated. A spinning planet. So it's somehow fig figured out how to make that look as though it's u animated, which is quite cool. Yeah. And this is the thinking turned off. So if I had thinking turned on, it does a little bit more thought in the planning stage, and you generally get better SVGs out. Like more time spent thinking about it results in better SVGs.

</details>

### Gemma 4 与 Open Code 集成

**Ian Valentine**: 嗯，所以接下来我想向你们展示的是，呃，我将跳到这里，**Open Code**。所以，正如我所说，呃，你可以使用任何可以使用 **OpenAI** 兼容接口的应用程序。所以，如果你有一个编程环境，呃，你基本上可以把它指向那个，然后你可以尝试模型，看看它表现如何。所以，在这个特定的例子中，你所要做的就是配置 **Open Code**，我将在这里关闭所有我的终端。再见。

<details>
<summary>Original English</summary>

**Ian Valentine**: Um, so the next thing I wanted to show you is, uh, I'm going to jump over here to open code. So, as I mentioned, uh, you can use any application that can use an open AI compatible interface. So, if you've got like a programming environment, uh, you can just basically point it at that and you can try the model out to just see how well it performs. So, in this particular example, the all you do to configure this in open code is you just I'm going to kill all my terminals here. by goodbye.

</details>

**Ian Valentine**: 我们把这些都删掉。如果你去，有一个文件。如果我输入 **vim.config**，**open code config.json**，然后我向下滚动到，它在哪里？就是这里这个部分。这就是你需要指定的所有内容。所以你给出提供商的名称，**schema** 是什么，你想要暴露的模型，呃，以及你需要的任何额外的端点参数，然后你只需字面上把它指向一个 **URL**，在这个例子中就是我的本地机器。这就是你需要做的一切。我还有另一个例子。我现在不打算运行它，但我们有一个指南，说明如何在 **Cloud Run** 或云提供商上部署 **Gemma 4**。所以如果你没有足够的 **RAM** 来运行你想要的量化，你可以把它扔到单个 **GPU** 上，然后你就会得到这个命令，就是这里这个，**beta cloud deploy**，它会将模型部署到 **RTX Pro 6000** 上。所以如果你只是想测试一下，这是你可以测试你微调或自己运行的任何模型的一种方式。我们还有另一种访问它的方式。如果你去 ai.dev，**Paige** 和 **Guillaume** 已经向你们展示过了。我们也有 **Gemma** 模型可用。所以如果你只是想提示它们，我们有两个大型模型，你可以在那里测试它们，它们支持，你知道，视频和文件上传，以及与搜索的基础功能，所有这些都内置在其中。所以你也可以单独测试它们的性能。所以真的没有理由，无论你有没有硬件，呃，你都可以尝试一下。呃，是的，我想向你们展示的是，我，呃，生成了一个小游戏的规范。呃，它在哪里？好的，我制作了一个叫做 **Nebula Drift** 的游戏。所以我所做的是，我使用了 310 亿参数模型来给我一个游戏的规范，然后我将把它交给我的本地模型去实现。所以如果我输入 **implement spec**。

<details>
<summary>Original English</summary>

**Ian Valentine**: Let's get rid of these. If you go to there is a single file. If I go vim.config open code config.json and I scroll down to where is it? This section here. This is all you need to specify. So you give the name of the provider, what the schema is, the models that you want to expose, uh, and any additional parameters that you need for the endpoint, and then you just literally point it at a URL, which in this case is just my local machine. And that's all you need to do. And I have another example. I'm not going to run this right now, but we have a guide for how you deploy Gemma for on say something like Cloudr Run or like a cloud provider. So if you don't have enough RAM to run the the quantization that you want, you can just throw it up to a single GPU and you get this this single command here, this one right here, the beta cloud deploy, and this will put the model on a an RTX Pro 6000. So you can just if you just want to test it out, that's one way that you can test whatever model that you fine-tuned or run yourself. And we have another way to access it as well. If you go to ai.dev, dev that uh Paige and Gim have been showing you. We've also got the Gemma models are available here. So if you just want to prompt them, we've got the two big models and you can test them out there and they support like you know video and file uploads, grounding with search is all kind of built into that too. So you can test to see how they perform in isolation as well. So really there's no reason whether you have the hardware or don't have the hardware uh for you to be able to give it a shot. Uh yeah, what I wanted to show you was that I had uh generated a spec for uh a little game. Uh where is it? Okay, so I made a game called Nebula Drift. So what I did is I used the 31 billion parameter model to give me just like a spec for a game and I'm just going to give it to my local model to go and implement. So if I go implement spec.

</details>

**Ian Valentine**: 呃，然后我只是给它这个文件，确保它是正确的模型，然后我们确保重新打开思考功能，这样它也能实际推理。

<details>
<summary>Original English</summary>

**Ian Valentine**: uh and then I just give it the file this one and uh sure it's the right model and let's make sure we turn thinking back on so that it's going to actually reason about it too.

</details>

**Ian Valentine**: 呃，好了。呃，我们来运行它。那么为什么这很有趣呢？因为我们根本没有改变 **Open Code** 的任何东西。我们只是字面上把模型给它，让它在本地机器上尝试，在 **Open Code** 规范中，它将给它所有它需要的不同工具，以便能够运行 **Open Code** 并在那个环境中运行。所以它应该会思考它需要完成的任务，然后它需要查看文件系统，要么从文件系统读取文件，要么向文件系统写入文件，如果它出错了，我可以像任何编码工具一样，我可以提示它说“哦，你检查过这个了吗？”或者“我能把错误反馈给你，让你去推理吗？”所以这只是它遵循这些指令。所以是的，它决定创建一个目录。所以它将直接使用那个目录中的 shell。所以，如果你使用过任何编码工具，这应该不会太陌生，但也许你使用过其他模型。也许你没有使用过本地模型或在你的硬件上运行的开源模型。所以，我只是想向你展示这是可能的。哦，是的。好了。它已经创建了一个索引文件。那很快。嗯，如果它正确读取规范，它应该会生成另外两个文件。它应该会生成一个 **JavaScript** 文件和一个 **CSS** 文件。呃，然后我们要做的就是尝试看看它根据规范制作出了什么游戏。嗯，为了给你们一个概念，它应该是一个无限赛车游戏，你需要躲避一些小行星。所以，如果它完成了代码，嗯，好了。我们试试看怎么样？看起来它确实做了一些正确的事情。

<details>
<summary>Original English</summary>

**Ian Valentine**: Uh there we go. Uh and we'll run that. And so why is this interesting? Because we haven't changed anything about open code at all. We've just literally given it the model to try on the local machine and in the open code spec it's going to give it all the different tools that it needs to be able to run open code and to behave in that environment. So it should think about uh the task it needs to do and then it needs to look at the file system to either read files from the file system or write files to the file system and if it goes wrong I can similar like to any coding harness I can just prompt it and say oh did you check this or can I feed the error back into you and have it kind of reason through it. So this is just it following these instructions. So yeah it's decided to make a directory. So it's going to use the shell directly directory from that. So, if you've used any coding tools, this shouldn't be too uh unfamiliar, but maybe you've used it with another model. Maybe you haven't used it with a local model or an open model um like running on your hardware. So, I just want to show you that this is kind of possible. Oh, yeah. There you go. It's already created an index file. That was quick. Um it's going to create, if it reads the spec correctly, it should generate two more files. It should generate a JavaScript one and a CSS one. Uh and then what we'll do is we'll just try to see what game it managed to make from the spec. Um, and to kind of give you an idea, it should be like a an infinite racing game where you've got to avoid some asteroids. So, if it finishes off the code, um, there we go. Should we give that a shot? That looks like it's actually done something correctly.

</details>

**Ian Valentine**: 所以，如果我运行它，它写在哪里了？它叫什么？**Nebula**。哦，**Nebula Drift** 带下划线。它决定了。哦，我想它甚至在我看的时候试图改变文件路径。它试图进行编辑。停。停止编辑。嗯，所以我们试着运行它。好的，我们有一个游戏。

<details>
<summary>Original English</summary>

**Ian Valentine**: So, if I go run that, where did it write it? What was it called? Nebula. Oh, Nebula drift with an underscore. decided. Oh, I think it's even trying to change the file path as I look at it right here. It's trying to make edits to it. Stop. Stop editing. Um, so let's just try and run that. Okay, we have a game.

</details>

**Ian Valentine**: 呃，哦，它不运行。好的，这很有趣。所以，我们可以做的是，如果我们只是去，呃，我们再试着运行一次。啊，所以有一个语法问题。所以如果我只是字面上复制这个。所以想象一下，在大多数工具中，你都会有一个反馈循环，你可以直接把它反馈到编码中。但我只是手动操作，看看它能否发现自己的错误。我，呃，停。我发现了一个错误。我们检查一下。你真的读了吗？还是没有？我们再试一次。

<details>
<summary>Original English</summary>

**Ian Valentine**: Uh, oh, it doesn't run. Okay, so this is interesting. So, what we can do is if we just go uh let's try and run that again. Ah, so there's a syntax problem. So if I say if I just literally copy this. So imagine in most harnesses you'd have a feedback loop where you could feed it back straight into the coding. But I'm just going to do it manually and see if it can spot its own error. I uh stop. I found an error. Let's check that. Did you actually read that or not? Let's try again.

</details>

**Ian Valentine**: 好的，所以现在它应该，现在它应该，呃，进行一些调查。所以可能会重新读取文件，看看它能否发现拼写错误或问题所在，然后它应该会尝试编辑或修复它。所以实际上在 **Open Code** 中，他们给你两个工具。一个可以编辑单行，一个可以重写文件。所以它甚至可以决定使用哪个工具来完成。呃，所以希望它能正确编辑。嗯，然后把它写回去。所以它更新了 **game.js** 文件，它正在编辑，呃，你在编辑什么别的东西吗？哦，嗯，它也可以启动子代理。所以如果你给它一个特定的技能或任务，它基本上可以，呃，运行子代理。呃，**31B** 在这方面做得很好。**26B** 取决于任务。有时它理解要调用哪个子代理，有时你需要给它更多的提示。但类似地，在这样的环境中，你可以暴露 **MCP 服务器**，你可以创建技能，你可以做各种各样的事情来帮助指导模型。嗯，我们看看这是否修复了什么？

<details>
<summary>Original English</summary>

**Ian Valentine**: Okay, so now it should now it should uh do some investigation. So probably reread the files, see if it can spot what the typo is or what the problem is and then it would should try and edit it or fix it. So actually in open code they give you two tools. One which can edit like individual lines and one that can just like rewrite the file. So it it can even make a decision about which one of those it needs to use to do it. Uh so hopefully it's going to edit it correctly. Um and then write that back out. So it's updated the game jet.js and it's editing uh what are you editing something else? Oh um it can also kick off sub aents too. So if you give it like a specific skills or task to do, it can basically uh run sub aents. Uh the 31B is pretty good at that. The 26B depends like on the task. Sometimes it understands like what sub aents to call and sometimes you have to give it a bit more prompting. But similarly with an environment like this, you can expose MCP servers, you can create skills, you can do all sorts of stuff to kind of like help guide the model. Um, should we see whether that's fixed anything?

</details>

**Ian Valentine**: 好了。我甚至没看到。它刷新了吗？不，还没。它正在尝试编辑游戏文件。必须完全匹配。所以，好的。所以它正在尝试编辑文件的一部分。我也可以说，呃，空。好的。我想它可能被卸载了。我们把它放回去。我们重新加载它。

<details>
<summary>Original English</summary>

**Ian Valentine**: There we go. I don't even see. Did that refresh? Nope, not yet. It's trying to edit the game file. Must match exactly. So, okay. So, it's trying to edit a part of the file. I could also just say like, uh, null. Okay. I think it probably got unloaded. Let's put that back in. Let's load that back up.

</details>

**Ian Valentine**: 再试一次，**Gemma**。好的。所以，如果我让它再次输出 **game.js** 的完整文件。

<details>
<summary>Original English</summary>

**Ian Valentine**: Try again, Gemma. Right. So, if I tell it just output the full file again for game.js. Uh,

</details>

**Ian Valentine**: 它放在哪里了？它在那一个里面。所以你可以告诉它具体应该读取和写入哪个文件。所以希望它能听我的，然后，呃，重新生成那个文件。

<details>
<summary>Original English</summary>

**Ian Valentine**: where did it put it? It was in that one. So you can tell it like specifically which file it should be reading and writing to. So hopefully it should listen to what I say and then uh regenerate that file.

</details>

**Ian Valentine**: 在我们等待的时候，有人有其他游戏制作的想法吗？**Paige** 对粉色松鼠很着迷，所以你可以尝试那个方向的东西。有什么游戏想法吗？

<details>
<summary>Original English</summary>

**Ian Valentine**: While we're waiting, does anybody have any other ideas for a game to to make? Paige is obsessed with like pink squirrels, but like so you could try something in that vein. Any any ideas for a game?

</details>

**Audience**: 一个你可以自己构建游戏的游戏。

<details>
<summary>Original English</summary>

**Audience**: A game where you can build your own game.

</details>

**Ian Valentine**: 哇。我们试试看。所以，我将使用一个游戏。

<details>
<summary>Original English</summary>

**Ian Valentine**: Whoa. Let's try it. So, I'm gonna use a game.

</details>

**Audience**: 是的。

<details>
<summary>Original English</summary>

**Audience**: Yeah.

</details>

**Ian Valentine**: 好的。我们来问问。我们问大模型。所以，如果我，呃，好的。写一个游戏的规范，你可以在游戏里构建自己的游戏，并以此作为参考。所以，我们先构建一个规范。呃，我们就在这里，我们将使用，是的，我们将使用另一个的规范作为参考。

<details>
<summary>Original English</summary>

**Ian Valentine**: Right. Let's go ask. We'll ask the big model. So, if I go uh Okay. Write a spec for a game where you can build your own game inside the game and use this as a reference. So, we're going to build a spec first. Uh let's just go here and we'll use Yeah, we'll use we'll use the spec for the other one as a reference.

</details>

**Ian Valentine**: 我们试着运行它，同时看看我们的 **Open Code** 怎么样了。

<details>
<summary>Original English</summary>

**Ian Valentine**: Let's try and run that while we see what's going on with our open code.

</details>

**Ian Valentine**: 这看起来它正在编辑文件。

<details>
<summary>Original English</summary>

**Ian Valentine**: This looks like it's editing the file right now.

</details>

**Ian Valentine**: 是的，你可以看到它正在处理 token。

<details>
<summary>Original English</summary>

**Ian Valentine**: Yeah, you can see it's processing the tokens right there.

</details>

**Ian Valentine**: 如果我去看这个，**OmniForge**。所以，我在这里所做的是，我告诉它遵循一个特定的规范。呃，所以它保持相同的模式。所以，比如，如果我有一个它需要遵循的格式，它非常擅长遵循这些指令并保持这种记录。如果你在 2026 年使用过任何模型，除了知道它可以在家里运行之外，这可能不会令人印象深刻。对我来说，这才是最有趣的部分，你知道，所有顶级模型都能做到这一点。呃，但是，是的，直到最近，你还不能自己运行。所以，呃，我们让它在那里做它的事情吧。它修复我的文件了吗？它做了更多的编辑。我们可以去看看它改变了什么。所以它正在开始。

<details>
<summary>Original English</summary>

**Ian Valentine**: If I go to this one, OmniForge. So, what it's what I've done here is I've told it to follow a particular spec. Uh, so it keeps the same pattern. So, like for instance, if I had like a format that I needed it to do in, it's pretty good at following those instructions and kind of keeping to that uh that record. This may not be impressive if you've used any model in 2026 other than to know that it's something that you can actually run at home. That's for me is the interesting part of this like the you know all the top models can do this. Uh but yeah up until recently not not that you could run yourself. So uh let's leave that doing its thing there. Has it fixed my file yet? It's made more edits. We can go and see what it changed. So it's starting

</details>

**Ian Valentine**: 哦，它添加了一些更多的 **delta time**。哦，它正在改变输入。好的。好的。嗯，你可以看到它在这里生成了什么。就像它有这些小的玩家案例和各种各样的东西。我们看看它是否再次运行？呃，在我们等待的时候，对吗？

<details>
<summary>Original English</summary>

**Ian Valentine**: Oh, it added some more delta time. Oh, it's changing the input. Okay. Okay. Well, you can see what it's generating here. Like it's got like these little player cases and all sorts of stuff. Should we see if it runs again? Uh, while we're waiting for that, right?

</details>

**Ian Valentine**: 你要运行了吗？啊，我能做的就是，我可以说，嗯，呃，我们说，按下按钮游戏没有开始。重新生成文件。希望它能把它们写回去。我们这样做吧。

<details>
<summary>Original English</summary>

**Ian Valentine**: Are you going to run yet? Ah, you what I could do is I could just say to it, um, uh, let's say, pressing the button doesn't start the game. Regenerate the files. And hopefully it's just going to write them back out. Let's do that.

</details>

**Ian Valentine**: 好的，正在思考。看看我们的规范进展如何。所以，我们来获取 **31B**。你能实现这个规范，呃，但作为一个单一的 **index.html**，包含 **CSS** 和 **JavaScript** 吗？看看它能否做到。

<details>
<summary>Original English</summary>

**Ian Valentine**: Okay, thinking about it. See how our spec is getting on. So, let's just get 31B. Can you just implement this spec uh but as a single index.html with the CSS and JavaScript included. See that it can do that.

</details>

**Ian Valentine**: 好的。呃，还有一件事我想给你们看。我们将并行进行。**AI.dev**。模型实际上非常擅长做的一件事是，作为多模态模型，它能理解给定输入的上下文。所以，我例如可以截取一个网站的截图，比如，呃，如果我去了 **Gemma for DeepMind**。我们去这个。如果我只是，呃，我只是抓取这个，然后我可以直接去模型，呃，将这个网页实现为一个单一的 **index.html**。如果我只是上传那个文件，那个。好了。然后尝试运行这个。

<details>
<summary>Original English</summary>

**Ian Valentine**: Okay. Uh, and there's one other thing I want to show you. We'll do that in parallel. AI.dev. One thing that the model is actually quite good at doing being multimodal is to understand um the context of the input that it's given. So I could for instance take uh a screenshot of a website like uh if I go to Gemma for deep mind. Let's go to this one. And if I just go like uh I just grab this and I could just go to the model uh implement this web page web page as a single index.html. If I just upload that file that one. There you go. and try and run this.

</details>

**Ian Valentine**: 是的。我们的 **Open Code** 怎么样了？所以，它已经写好了游戏文件，希望没有错误。写好了样式文件，希望也写好了索引文件。所以，我们再试一次。

<details>
<summary>Original English</summary>

**Ian Valentine**: Yeah. How's our open code getting on? So, it's written the game file hopefully with no mistakes. Written the style file and hopefully written the index file. So, let's give that another whirl.

</details>

**Ian Valentine**: 好了。所以，这是我们的游戏，除了我没看到任何小行星。

<details>
<summary>Original English</summary>

**Ian Valentine**: Right. There we go. So, there's our game except I don't see any asteroids.

</details>

**Ian Valentine**: 好的，我们有一个星空和一艘可移动的飞船。所以，再次强调，这只是模型想出来的。你可以不断迭代它。你可以添加东西。呃，我不会，我可以让它生成更多小行星，但我想我们已经完成了这个。呃，我们看看其他的怎么样了。所以，这是，这是关于制作游戏的游戏。我真的很好奇它会怎么做，因为那会非常疯狂。然后这个，这个正在生成，哦，是的。这个正在生成重新创建的网页。所以，呃，这一切都可以免费玩。嗯，所以，请注意，在使用共享所有权方面有一些使用限制。嗯，但你可以用它来测试东西，非常容易。呃，这就是为什么它比，嗯，**Gemini** 模型慢一点，因为，呃，只有一个可怜的 **Gemma** 模型在为所有人服务。嗯，我们看看。这个完成了吗？还在进行中。我不知道。也许它制作了一个非常史诗般的冒险。我想它可能就是，你知道，一旦完成就发布。

<details>
<summary>Original English</summary>

**Ian Valentine**: Okay, we've got a starfield and we've got a movable ship. So, again, this is just what the model has come up with. You could just iterate on this. You could kind of add to it. Uh I'm not going to I could ask it for more asteroids, but I think we're done with this one. Uh let's see how the other ones are getting on. So, this is the this is the game about making a game. I'm really curious just to see how what it does for this because that's going to be pretty nuts. And then this one, this is generating the Oh, yeah. This is generating the recreated web page. So, uh this is all free to to play around with. Um so, just be aware there's like usage limits in terms of like like shared ownership. Um but you can just use it like to test stuff out pretty easy. Uh that's why it's a little bit slower than the um the Gemini models because it's the uh there's only one poor Gemma model serving everybody. Um let's see. Is this one done yet? Still going. I don't know. Maybe it's made like a really epic adventure. I think it might just be this might be, you know, ship it as soon as this is done.

</details>

### Gemma 4 机器人模拟与 Android 应用集成

**Ian Valentine**: 呃，我还想给你们看什么？哦，好的。在我们做这个的时候，我想给你们看这个很酷的演示。所以，我们团队中的一个人，呃，非常喜欢机器人。所以他们，呃，他们制作了一个版本，如果你用过任何机器人模拟工具。所以这个叫做 **Open Duck**，它只是一个鸭子的小模拟器，你可以向它提问，或者你可以通过，呃，在浏览器中运行的 **E2B** 模型与它对话。所以当它告诉它执行这些动作时，**Gemma** 正在解释它要求模型做什么。它查看机器人能做什么，并指示它，如果你仔细看，你可以看到它说“执行动作”的地方。是的。在它实际执行动作之前，它会告诉你它正在尝试触发什么命令。所以你可以想象这实际上运行在设备上，或者在这个例子中是在模拟器中，只是为了，你知道，证明这一点。嗯，所以这很酷。另一个，呃，我想给你们看的是，呃，**Android Studio** 团队已经将其集成到制作 **Android** 应用程序中。所以你旁边有一个小聊天窗口，你可以，呃，从那里构建应用程序。所以他们再次有一个小代理构建器设置。呃，所以如果你只是构建手机应用程序，你可以，嗯，使用模型。我想他们再次使用了 **26B**。是的，他们为那个使用了 **26B**。然后，呃，我们还让它与，嗯，**ADK** 协同工作。所以我们的代理开发工具包再次暴露了不同的功能。它有一个思考循环。它有一个反馈系统。所以你可以给它更长时间运行的任务，它可以决定，比如拉取信息之类的。所以所有这些不同的环境你都可以运行它。我们看看我们的发现怎么样了？好的，这个完成了。所以，这将是我们的网页。

<details>
<summary>Original English</summary>

**Ian Valentine**: Uh what else I want to show you? Oh, okay. While we're doing that, I want to show you this cool demo. So, one of our team uh is really into their robotics. So, they uh they made a version if you've ever used um any of the robot simulation tools. So, this is called Open Duck uh which is just like a little simulator of duck and you can ask it questions or you can talk to it via a uh the E2B model which is running in the browser. So, it's you don't you actually download the model and it runs in web GPU straight in the browser page. So when it tells it to do these actions, Gemma is interpreting like what it's asked the model to do. It looks at what the the robot can do and instructs it to, if you look really carefully, you can see where it says perform action. Yeah. Before it actually does the action, it tells you what command it's trying to trigger. So you can imagine this actually running embedded on the device or in this case is in the simulator to just like kind of like prove the point. Um, so that's quite a cool one. The other one uh I want to show you was uh the Android Studio team have integrated it into making Android apps. So you've got like a little chat window at the side and you can uh build the apps from there. So they again they have like a little aentic builder setup. Uh so if you were just building phone apps, you can um use the model. I think they're using the 26B again. Yep, they're using the 26B for that one. And then uh we also have it working with um the uh ADK. So our agent development kit again it exposes like different functionality. It's got a thinking loop. It's got like a like a feedback system. So you can give it more longer running task and it can make decisions about like pulling information and stuff like that. So all these different environments that you can kind of run it in. Should we see how our find? Okay, this one is done. So, this is going to be this will be our web page.

</details>

**Ian Valentine**: 哦，这还不错。看起来挺好的。我猜这些按钮不会跳转到任何地方，但是，呃，有什么新功能。哦，它们，我以为它真的制作了一个视频。那会有点，那会有点激烈。但是，是的，但你可以看到，即使只是从布局来看，它也相当接近。它正确匹配了字体。对实际页面的理解非常好。这只是一次性完成的。所以，把它指向随机网页，看看它能构建什么。我们看看这个怎么样。我现在真的对这个游戏很感兴趣。我们看看这个是否真的能运行。

<details>
<summary>Original English</summary>

**Ian Valentine**: Oh, that's not bad. That looks pretty good. I don't imagine these buttons go anywhere, but for uh what's new. Oh, they I thought I literally thought it had made a video. That would have been a bit in that would have been a bit intense. But yeah, but you can see even just from like the layout, it's pretty close. It's kind of matched the font correctly. The understanding of the actual page is pretty good. And this is just kind of oneshotted. So, point it at random web pages and see what it can build. And let's see whether this I'm I am now really interested in this game. Let's see whether this actually works.

</details>

**Ian Valentine**: 哦天哪。好的。这是，哦，我有一个完整的编辑器。所以，我可以构建一个小的，哦，我喜欢那个。

<details>
<summary>Original English</summary>

**Ian Valentine**: Oh my gosh. Right. Is this Oh, I've got like a full editor. So, I can build like a little Oh, I like that.

</details>

**Ian Valentine**: 所以，一个目标。我能运行游戏吗？呃，我可以放东西进去。哦天哪。请告诉我。哦，是的。三角形移动了。哦，我喜欢它。为什么？

<details>
<summary>Original English</summary>

**Ian Valentine**: So, a goal. Can I run the game? Uh, I can put things in. Oh my gosh. Please tell me that. Oh, yes. The triangle moves. Oh, I love it. Why?

</details>

**Ian Valentine**: 好的，就这样吧，我想这是一个很好的结束点。所以，是的，呃，**Gemma** 模型，呃，你知道，它们可以在你的手机上运行，它们可以在你的笔记本电脑上运行，它们可以在 **GPU** 上运行。呃，去试试它们吧，如果你想探索，可以试试 **AI Gallery**。呃，我今天和明天都会在这里，如果你有任何问题，呃，但是，是的，很高兴与你们分享这些，呃，祝你们会议愉快。

<details>
<summary>Original English</summary>

**Ian Valentine**: Okay, there you go. That's that's a good point to end on, I think. So, yeah, uh Gemma models, uh you know, they run on your phone, they run on your laptops, they run on GPUs. Uh go try them out, try the AI gallery if you want to explore. Uh I'll be around today and tomorrow if you have any questions about how uh but yeah, uh really excited to share that with you and uh enjoy the rest of the conference.

</details>