---
author: AI Engineer
date: '2026-10-07'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=oWTEiYpxl80
speaker: AI Engineer
tags:
  - ai-agent
  - sandbox-environment
  - multimodal-api
  - server-side-state
  - tool-use
title: Google DeepMind：为什么 AI Agent 应当拥有专属沙盒与 Interactions API 详解
summary: Google DeepMind 的 Philipp Schmid 介绍了针对 Gemini 模型与 Agent 的 Interactions API 与 Managed Agents 架构。该方案通过服务端状态管理与持久化云端沙盒环境，让 Agent 能够原生执行代码、管理文件与调用多模态模型，简化全托管智能体的构建流程。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Philipp Schmid
companies_orgs:
  - Google DeepMind
products_models:
  - Gemini
  - Google AI Studio
  - Interactions API
  - Antigravity Agent
media_books: []
status: evergreen
---
### 开场与近期发布背景
欢迎大家来到本次分享，主题是为什么智能体应该拥有属于自己的沙盒。我是 Philipp，来自 Google DeepMind，主要负责 AI Studio 和 Gemini API 相关工作。今天现场人数不多，所以我会尽量缩短枯燥的内容，多留时间展示激动人心的 Demo，并在最后回答大家的问题。大家可以往前坐一点，这样我能听清大家提问。

<details>
<summary>Original English</summary>
[Speaker 1]:  so everyone welcome to why agcishould should their own sandandbox。
[Speaker 1]:  i'm philip。
[Speaker 1]:  i'm part of google deep piinty，
[Speaker 1]:  mostly working on AI studio and generina api。
[Speaker 1]:  i have have a small roup，
[Speaker 1]:  so i tried to keep the boring stuff short and like the exciting demo stuff long，
[Speaker 1]:  and we can also ask some questions。
[Speaker 1]:  i guess，
[Speaker 1]:  at the end，
[Speaker 1]:  maybe you need to see a little bit at the front，
[Speaker 1]:  so i can understand you。
</details>

我想先介绍一点背景。不知道大家以前是否见过这张幻灯片，在 Google 内部演讲中这是一张很常见的胶片，用来展示过去两年里我们在 Gemini 模型以及 Gemma 开源模型系列上取得的进展。不过，这张幻灯片截至昨天就已经过时了。昨天我们发布了全新的图像生成模型 Nano Banana Light，生成速度极快且价格非常便宜，生成一张图片大约只需 4 美分。同时，我们还在 Interactions API 上推出了 Veo Flash，大家现在可以通过编程方式使用 Veo 进行视频生成与剪辑，构建端到端的媒体应用。

<details>
<summary>Original English</summary>
[Speaker 1]:  and so i want to start with a little bit of a background。
[Speaker 1]:  i'm not sure if you have seen that life，
[Speaker 1]:  but that's a very popular slide when you do like google presentations and to show a little bit um what we have achieved in the last two year with like the german models，
[Speaker 1]:  but also our open models with jamma and slide is already outdated since yesterday。
[Speaker 1]:  so yesterday，
[Speaker 1]:  we ship nano banana light，
[Speaker 1]:  uh，
[Speaker 1]:  which is our new image generation model。
[Speaker 1]:  super fast。
[Speaker 1]:  sorry，
[Speaker 1]:  super fast，
[Speaker 1]:  uh super jeep。
[Speaker 1]:  um it's like four cent per image。
[Speaker 1]:  and then also，
[Speaker 1]:  we shipped only flash on the interactions api，
[Speaker 1]:  so you can now programmdically use only to create videos to edit videos to yet built ent media applications。
</details>

### 大模型演进：从文本补全到长时间目标驱动 Agent
简单回顾一下历史。我想大家都听过智能体和大语言模型，但我们可以快速梳理一下这一路的发展历程。大约在 2018 到 2019 年，伴随最初的 BERT 和 GPT 模型登场，大家感到非常兴奋，因为模型能够续写句子了。我们给出开头的几个词，模型就能生成诗歌，连贯地补全文本。这虽然很酷，但在当时对我们构建实际应用并没有太大帮助。

<details>
<summary>Original English</summary>
[Speaker 1]:  and to give it a bit of a brief history。
[Speaker 1]:  II assume everyone has heard about agent has heard about large language models，
[Speaker 1]:  but to really quickly reflect so where we are coming from。
[Speaker 1]:  so i think around two thousand eighty nineteen with the first first spurd models and GVT models，
[Speaker 1]:  we were super excited because we could continue sentces，
[Speaker 1]:  right？
[Speaker 1]:  we were able to generate poems without uh with providing like a first few words。
[Speaker 1]:  and then the model of hear rently continued a text which was nice，
[Speaker 1]:  but not very useful or helpful for anyone of us to build something。
</details>

随后我们进入了指令遵循时代。此前我们使用的是仅能续写文本的预训练模型；有了指令遵循后，我们实质上训练模型来回答问题。我们向模型提问，模型给出切题的回答。接着随着 ChatGPT 的出现，局面彻底改变，很多人大概都是从那时开始接触大模型的。我们进入了基于轮次的用户-模型对话模式：用户输入、模型输出、用户再输入、模型再输出。

<details>
<summary>Original English</summary>
[Speaker 1]:  then we removed into the the instruction away before we had three drain models，
[Speaker 1]:  which could continue text。
[Speaker 1]:  and then with instruction following，
[Speaker 1]:  we basically drain models to answer questions more or less。
[Speaker 1]:  so we told the ask a question and the model correctly responded。
[Speaker 1]:  and then with with judg PT，
[Speaker 1]:  everything changed a little bit。
[Speaker 1]:  i think most of the people probably got started with that。
[Speaker 1]:  and we went into this user model turn base conversation where we had a user input，
[Speaker 1]:  a model，
[Speaker 1]:  input，
[Speaker 1]:  a user input，
[Speaker 1]:  a model output。
</details>

再后来，我们引入了函数调用，因为我们希望模型能够替我们执行操作。如今，我们正步入一个由目标驱动思考与函数结合的黑盒阶段，在此阶段我们不再仅仅等待模型单次响应。我们给模型设定一个目标，告诉它如何验证该目标、如何进行部署，并期望它能自主运行数小时甚至数天，最终返回结果。这正是我们想要实现的目标。

<details>
<summary>Original English</summary>
[Speaker 1]:  then afterwards，
[Speaker 1]:  we combine that we're function calling because we want of the model to take actions for us an hour。
[Speaker 1]:  we are in like dispblack box with gold thinking and functions where we no longer trust from the model。
[Speaker 1]:  we basically give a goal to the model，
[Speaker 1]:  tell them how to verify its goal，
[Speaker 1]:  how to like deploy it。
[Speaker 1]:  and like hopefully，
[Speaker 1]:  have it running for multiple hours or even days days come back with the results。
[Speaker 1]:  ts want to achieve um so if you haven't use german API or yeah studio before，
[Speaker 1]:  you can go to a idol studio or to a idol depth。
</details>

如果大家之前没有使用过 Gemini API 或 Google AI Studio，可以直接访问 aistudio.google.com 或 ai.google.dev，短网址非常方便，可以直接获取自己的 API 密钥。如果带了电脑并希望稍后跟着实际操作演练近期上线的功能，完全可以现场体验。该服务无需复杂配置，使用 Gmail 账号即可开始实验；如果需要使用更大的模型或更高的用量，只需绑定信用卡。我们对此做了大量优化，大家不再需要离开 AI Studio 转跳到 Google Cloud 控制台，在 AI Studio 内部就能完成所有操作并设置预算，防止费用失控。

<details>
<summary>Original English</summary>
[Speaker 1]:  so very quick，
[Speaker 1]:  very short，
[Speaker 1]:  you're else get your own APIT。
[Speaker 1]:  so if you have your computer with you，
[Speaker 1]:  and if you want to follow along a little bit later，
[Speaker 1]:  ter，
[Speaker 1]:  like trying out out few things，
[Speaker 1]:  things have shipped recently，
[Speaker 1]:  you can do that。
[Speaker 1]:  um no set up required can use your gmail account。
[Speaker 1]:  um can start start experimenting if you want to use bigger models，
[Speaker 1]:  more usage，
[Speaker 1]:  enter your credit card。
[Speaker 1]:  and we improve that a lot。
[Speaker 1]:  so you don't need to leave a studio anymore to go into the good cloud。
[Speaker 1]:  you can do everything inside of AS dio o。
[Speaker 1]:  you can set up your bubudgets that nothing gets out of control。
</details>

### Interactions API 架构设计
接下来我想谈谈 Interactions API，这是我们针对 Gemini 模型和 Gemini Agent 推出的全新 API。屏幕上展示了一些代码片段。如果大家从未了解过 Interactions API，可以把它理解为我们对类似 OpenAI Responses API 的回应。它更加以开发者为中心、更简洁、更友好。大家可以从屏幕上的两段代码片段看出，无论调用像 Gemini 这样的底层模型，还是调用类似 Antigravity 的智能体，其调用接口完全一致。并且该接口适用于 Gemini 支持的所有模态。

<details>
<summary>Original English</summary>
[Speaker 1]:  and i want to start about or talk about the interrections api，
[Speaker 1]:  which is our new uh API for geri models and germini agents。
[Speaker 1]:  and on the right side for your left side，
[Speaker 1]:  we have some codes，
[Speaker 1]:  a bits。
[Speaker 1]:  so if you never have heard about the interactions api，
[Speaker 1]:  you can think a little bit about。
[Speaker 1]:  that's our answers to like to response api from open eye。
[Speaker 1]:  it is much more developful focused，
[Speaker 1]:  much more simpler，
[Speaker 1]:  much more developer friendly。
[Speaker 1]:  and you can already tell and like the two snippers here to call a model like gmini or to call an agent helike like the antigravity ation。
[Speaker 1]:  it's like literally the same interface。
[Speaker 1]:  and this works for all of the modalities german i offer。
</details>

在调用中，你指定一个模型或智能体，提供一个输入。输入可以是普通字符串，也可以是多模态数据。然后你配置工具或环境——这正是我感到非常兴奋的部分，也是我们稍后要深入讨论为什么每个模型或智能体都应该拥有自己沙盒的原因。在 Interactions API 中，我们引入了服务端状态管理，因此如果你不想在客户端维护状态，可以直接交由服务端托管。同时我们支持长时间运行任务，即异步请求。例如使用 Veo 进行视频生成通常耗时较长，开发者可能不希望一直保持 HTTP 连接开启；此时你只需发起请求并拿回一个 ID，既可以建立流式连接，也可以异步轮询直到生成完成。此外，它在构建操作和工具调用方面做了很多简化，支持将 Google 搜索等内置工具与自定义函数调用组合使用。

<details>
<summary>Original English</summary>
[Speaker 1]:  so you have a model or natand。
[Speaker 1]:  you have an input。
[Speaker 1]:  the input can be a basic string or can be multimodile data。
[Speaker 1]:  and then you have ttools or environment，
[Speaker 1]:  which um i'm very excited and why which we are going to talk about later why every model or agent should have its own box。
[Speaker 1]:  um new new the interrection apapi，
[Speaker 1]:  you have seversisite state management。
[Speaker 1]:  so if you don't want to manage the state on the client，
[Speaker 1]:  you can hand it over to you deserver。
[Speaker 1]:  we we have long operation，
[Speaker 1]:  so asing requests。
[Speaker 1]:  basically，
[Speaker 1]:  you start something if we talk about only video generation ation kes quite ite long long time，
[Speaker 1]:  and you might not want to keep your HTTP connection open。
[Speaker 1]:  so you send a request，
[Speaker 1]:  get back and ID can set up streaming is completely wait ununtil。
[Speaker 1]:  the generation is completed。
[Speaker 1]:  and then um it comes with a lot of simplifications for building actions and to ll use。
[Speaker 1]:  so you can comine builbuiltools like function calling with custom function calling and to look at some coding example。
</details>

来看一些代码示例。对于服务端状态管理，它的形式非常直观。如果用过 Responses API 会觉得很眼熟，但我们将其命名为 Interactions，因为我们不再只是单纯获取单次响应，而是在与模型及 Agent 进行持续交互。你发起一次输入；如果要进行后续交互轮次，只需提供新的输入并传入上一轮的交互 ID。随后在服务端，我们会把各次输入拼接串联起来，确保模型能完整感知之前的上下文。该机制贯穿所有模态。

<details>
<summary>Original English</summary>
[Speaker 1]:  so for servsides state，
[Speaker 1]:  it looks very similar。
[Speaker 1]:  if you have used to responses api，
[Speaker 1]:  we call it interactions because we just not get a response anymore。
[Speaker 1]:  we interact with models and agents。
[Speaker 1]:  you send an input。
[Speaker 1]:  and if you want to do a photo up turn，
[Speaker 1]:  you provide a new input and basically trust the ID from the previous turn。
[Speaker 1]:  and then on to server，
[Speaker 1]:  we um concatdinate all of light to different inputs。
[Speaker 1]:  and make sure that the model really reseize what has been done so far and this goes for all modality。
</details>

在音频生成场景中，我们指定模型为 Gemini TTS 模型，传入输入；由于需要返回音频而非文本，我们把响应模态定义为音频，并配置所需的生成参数（如选择音色）。同样的模式也适用于图像生成：指定图像生成模型（例如 Nano Banana）、传入提示词、设置生成配置，即可直接获取生成的图片。

<details>
<summary>Original English</summary>
[Speaker 1]:  so for all of your generation，
[Speaker 1]:  we have a model，
[Speaker 1]:  we have our german ITTS model。
[Speaker 1]:  we have our input。
[Speaker 1]:  and since we want audio back，
[Speaker 1]:  not text，
[Speaker 1]:  you define a response modality with audio and some generation configuration，
[Speaker 1]:  which wise you，
[Speaker 1]:  for example，
[Speaker 1]:  want to use the same pattern works for image generation。
[Speaker 1]:  so our iimage generation model um not a banana here，
[Speaker 1]:  our input song generation generation conflict，
[Speaker 1]:  and then you get back your image and for tool use。
</details>

在工具使用方面，体验也有了很大提升。以往开发者只需声明工具（例如 Google Search、URL 上下文或自定义函数），然后发起请求，模型自行决定是先执行 Google 搜索还是调用函数。屏幕上展示的这段代码，已经足以构建一个非常轻量简洁的 CVE 漏洞排查 Agent，用于检测 React 当前是否存在相关 CVE 漏洞。该 Agent 结合使用 Google 搜索检索信息、利用 URL 上下文访问具体网页，再通过函数调用将数据结构化，以便存入数据库或进行后续查询。

<details>
<summary>Original English</summary>
[Speaker 1]:  um also much better。
[Speaker 1]:  i would say，
[Speaker 1]:  and previously，
[Speaker 1]:  you justify your tools with like google search，
[Speaker 1]:  you are al context，
[Speaker 1]:  or your own custom function，
[Speaker 1]:  and then you send your request and a model besides on it on its own。
[Speaker 1]:  do i first first need to like run google search or cled a function？
[Speaker 1]:  and all of the code you see here is basically enough to create a very simple，
[Speaker 1]:  small CVE agent to detect if they're like any CVE um for react in this case。
[Speaker 1]:  and unlike it uses google search，
[Speaker 1]:  it uses your are le context to visit those debsites and and function calling to a basically give structure to it。
[Speaker 1]:  so you can like save it in your database。
[Speaker 1]:  all look it up，
[Speaker 1]:  for example，
</details>

### 从轮次抽象转向步骤时间线
与其它模型供应商相比，我们做了一项重大变革：彻底摒弃了原有的“用户-模型轮次（turn-based）”原则。在以往使用其它 LLM 供应商或开源模型构建应用时，系统总是遵循“用户输入、模型输出”的轮次概念。这种模式在一两年前还行得通，因为当时模型只负责返回内容。但随着 Agent 和推理机制的发展，这一切都被打破了。如今模型往往会经历长时间的思考，可能直接暴露内部思维，也可能仅输出签名；函数调用实际上并不是一种用户角色。在传统的旧版 API 中，开发者必须伪造一个 user 角色来传回函数的执行结果，这在逻辑上显得非常别扭，因为这一输入或输出明明来自执行环境而非人类用户。

<details>
<summary>Original English</summary>
[Speaker 1]:  and something new and maybe different to other model providers is that we moved away from this user model term principal。
[Speaker 1]:  so if you build an application with another eleen provider or with open models，
[Speaker 1]:  you have always this uh user model user model turn concept。
[Speaker 1]:  so us a user provide input and expect a model to return an output。
[Speaker 1]:  this worked until like one or two years ago，
[Speaker 1]:  i would say where we just got back responses from those models，
[Speaker 1]:  but with agents and with reasoning，
[Speaker 1]:  all of that change right models。
[Speaker 1]:  now think for a very long time，
[Speaker 1]:  with it might expose some thoughts directly or might trust expose the signature function calling is not very a user role，
[Speaker 1]:  right with normal or like with previous aps，
[Speaker 1]:  you would need to use the user turn to return some function output，
[Speaker 1]:  which，
[Speaker 1]:  for me，
[Speaker 1]:  always felt little it weird，
[Speaker 1]:  because the output or the new input is coming from the environment and not from the user。
</details>

因此，我们将对话轮次重构为了“步骤（steps）”，即按时间线排列的步骤序列。每一个具体操作或生成过程都有独立的类型定义。这不仅便于未来扩展全新功能与特性，而且使用起来非常清晰直接，能够明确界定模型究竟执行了何种动作。如果你构建一个函数调用 Agent，返回的就是明确的函数执行结果类型，而不是一个塞入函数结果的 user 角色对象。

<details>
<summary>Original English</summary>
[Speaker 1]:  so that's why we moved away from that。
[Speaker 1]:  those turns into steps or like to like synchronous timeline of steps where every action or generation is its own type，
[Speaker 1]:  which makes it very easy to extend to new features and capabilities，
[Speaker 1]:  which might come in the future，
[Speaker 1]:  but also makes it so like very simple to use because you really define what it has done。
[Speaker 1]:  so if you build a function calling agent，
[Speaker 1]:  you return a function result and not like a user，
[Speaker 1]:  a role user with some content，
[Speaker 1]:  which might be a function result or not。
</details>

### Antigravity Agent 与持久化沙盒环境
在 Google，我们推出了自带沙盒环境的 Antigravity Agent。Gemini API 内部托管的 Antigravity 远程 Agent，底层正是由驱动 Antigravity 产品的同一个 Agent Harness 提供支持。如果大家使用过 Antigravity IDE、全新的 Antigravity 2.0 或其 CLI，可能已经接触过该 Harness。需要特别强调的是，我们所说的 Harness 指的是智能体的底层后端框架，并不等同于具体某个 Agent 实例本身。在不同产品形态中，它的具体表现可能有所不同：例如 Antigravity IDE 侧重于代码编写，拥有不同的工具集或不同的系统指令；而 Gemini API 中的 Antigravity Agent 则略有差异，但二者基于相同的 Harness。这意味着只要我们在该 Harness 上改进 Gemini 模型的能力，Antigravity 产品和 Gemini API 都将同步受益。

<details>
<summary>Original English</summary>
[Speaker 1]:  and at google eywe shipped the antigravity agent，
[Speaker 1]:  which comes with its own sandbox。
[Speaker 1]:  so the antii gravity remote agent in the side，
[Speaker 1]:  the cherman IPI is powered by the same agent honest，
[Speaker 1]:  which is used with the anti gravity product。
[Speaker 1]:  so if you have used the IDE or the new anti gravity to that，
[Speaker 1]:  oh，
[Speaker 1]:  or ACI，
[Speaker 1]:  you might have used that honus already very important here。
[Speaker 1]:  when we talk about honus，
[Speaker 1]:  we don't mean the same agent。
[Speaker 1]:  the honus is basically the baggain of our agent，
[Speaker 1]:  but it might be different between different products。
[Speaker 1]:  so the antigravity IDE is a coding agent，
[Speaker 1]:  so it might have a little bit of different tools or a little bit of a different system instruction。
[Speaker 1]:  then the anani gravity agent we have in the geri API，
[Speaker 1]:  but it's still the same haronless。
[Speaker 1]:  meaning if we improve chmini to become better with that honewe benefit ininanani gravity，
[Speaker 1]:  but we also benefit inside of the gerina api in with that new agent。
</details>

伴随这款全新 Agent，我们引入了 `environment` 字段。当设置为远程环境时，该 API 调用会分配一个由我们完全托管的专属沙盒。这意味着在请求发出后，后端会自动拉起一个云端沙盒，Agent 可以在其中执行代码、创建与写入文件、安装依赖、安装自定义工具乃至调用外部 API。这一切在服务端完全托管，对用户而言是无状态的直接调用，无需自行运维底层基础设施。

<details>
<summary>Original English</summary>
[Speaker 1]:  we also introduced this an environment field，
[Speaker 1]:  an environment here。
[Speaker 1]:  remote is basically for that api call，
[Speaker 1]:  your agent gets uh sandbox manage by us。
[Speaker 1]:  meaning，
[Speaker 1]:  if you send a request，
[Speaker 1]:  our began starts as cloud sandbox，
[Speaker 1]:  radiation can run code can create files，
[Speaker 1]:  riite files um install dependencies，
[Speaker 1]:  install your own tools or maybe call your own aps。
[Speaker 1]:  and it's all managed and stateless on our site，
[Speaker 1]:  meaning that you just send the api request，
[Speaker 1]:  you don't need to manage the infrastructure and those environments stay persistent。
</details>

更为关键的是，这些沙盒环境具备持久性。在多轮对话中，如果你让 Agent 调研最新的科技资讯并生成一个文件，随后发起下一轮交互时，可以直接复用上一轮的环境。同时，这也意味着多个 Agent 之间可以共享环境：三个 Agent 在同一环境中协同工作时，可以直接通过文件系统共享上下文；甚至可以通过子智能体来直接接替前序 Agent 已完成的工作成果。

<details>
<summary>Original English</summary>
[Speaker 1]:  so if you have multitturon conversation where the ancient um you set news er input，
[Speaker 1]:  i don't know like researarch the latest taken news and create a file。
[Speaker 1]:  and then you want to do like a photoshop interaction，
[Speaker 1]:  you can like use the same environment from your previous term。
[Speaker 1]:  with that new interaction，
[Speaker 1]:  but also this means that you can share environments between different agents。
[Speaker 1]:  so if you have like free agents working inside the same environment，
[Speaker 1]:  they can share context through the file system，
[Speaker 1]:  or you can like even use subagents to basically pick up a work。
[Speaker 1]:  uh not agent has been done。
</details>

### 数据源、技能（Skills）与 Agents API
虽然环境本身功能强大，但模型仍需要正确的上下文、信息和工具才能在沙盒内顺畅运作。因此，你可以为环境挂载数据源（sources），包括 GCS 存储桶、GitHub 代码仓库或内联文件。这一机制非常契合技能（Skills）的集成。可以说 Antigravity Agent 是技能优先且文件系统原生的：如果将技能存放在 `skills/` 目录下，系统启动时会自动扫描识别并直接并入系统指令；如果环境中存在既有编码 Agent 的 `AGENTS.md` 文件，它同样会被自动追加到系统指令中。

<details>
<summary>Original English</summary>
[Speaker 1]:  and then，
[Speaker 1]:  of course，
[Speaker 1]:  environments are very good，
[Speaker 1]:  but the model needs the right context and the right information or the right tools to work inside those environment。
[Speaker 1]:  so you can provide sources。
[Speaker 1]:  sources can be um CCS buckets，
[Speaker 1]:  skittaberic，
[Speaker 1]:  postories or inline files。
[Speaker 1]:  it's very useful if you want to integrate skills。
[Speaker 1]:  so the antii gravity agent is skills or filosystem native。
[Speaker 1]:  i would say so if you store skills inside the skills directer，
[Speaker 1]:  it will all to be immedally picpicked up and um be included into the system instruction。
[Speaker 1]:  but also，
[Speaker 1]:  if you have an agents empy five from your coding agents or from your existing agents，
[Speaker 1]:  it will also be automatically appended to the system instruction。
</details>

尽管通过单次请求配置完整环境非常灵活，但如果需要团队间共享或交付给下游团队使用呢？为此，我们推出了 Agents API。开发者可以定义基础智能体（即底层核心模型）、预设系统指令并指定环境配置。这里的环境可以是一个包含初始数据源的空环境，也可以直接指向一个既有的已预置环境。例如，你可以让某个脚手架 Agent 先行运行，在环境中安装 GitHub CLI、配置技能并执行完整性校验；该 Agent 执行完毕后会返回一个环境 ID，你便可利用该 ID 创建新的 Agent。后续每次调用该新 Agent 时，它都将直接基于这一份预加载、预配置的环境启动。整个过程无需编写 Terraform 脚本，无需管理 Kubernetes 微服务、Firecracker 容器或复杂的基础设施。

<details>
<summary>Original English</summary>
[Speaker 1]:  and then um you can create an agent because like sending a request is nice and having all of the configuration sttelacis also very good。
[Speaker 1]:  but what if you want to share it？
[Speaker 1]:  or what if team one builds in asian team two wants to use？
[Speaker 1]:  um therefore，
[Speaker 1]:  we created the agents api where you can define the base agents。
[Speaker 1]:  so what's the underlying prain so to speak？
[Speaker 1]:  you can define instruction，
[Speaker 1]:  and then also the uh environment um and environment can be raw environment，
[Speaker 1]:  like with sourources，
[Speaker 1]:  or you can use an existing environment。
[Speaker 1]:  so you can think about，
[Speaker 1]:  i have some kind of a skeffolding to do where i need to install，
[Speaker 1]:  like the kitpsc alive uh at some skills and maybe do some like senanity checks。
[Speaker 1]:  i can use the age to create its own environment。
[Speaker 1]:  and after the agent is done，
[Speaker 1]:  i get back an environment。
[Speaker 1]:  IDI can use that environment id to create the new agent。
[Speaker 1]:  and every time i called this new agent，
[Speaker 1]:  it will start from that already preloaded preconfigured environment。
[Speaker 1]:  and so it's like very easy for you to use agents to build their own environments and then like to create agents out of them，
[Speaker 1]:  which you can share with your users or with your customers without writing any terlephone without thinking about cubonates microservices，
[Speaker 1]:  fie cricker or anything else and to make it easier for you。
</details>

为了方便开发者及各类编码 Agent 调用，我们为 Gemini API 开发了专用的 CLI 工具。需要说明的是，它本身不是一个编程智能体（不是 Gemini CLI），而是供你的 Agent 用于调用 Gemini API 的 CLI 工具。借助该 CLI，Agent 可以调用 Nano Banana 或 Veo 生成媒体资产，也可以用于创建、迭代和优化 Agent 自身。扫描屏幕上的二维码可跳转至对应的 GitHub 仓库；如果大家稍后想动手尝试，我们还提供了专门针对 Interactions API 和 Agents API 的开发技能。

<details>
<summary>Original English</summary>
[Speaker 1]:  and for your coding actions，
[Speaker 1]:  we created AC al，
[Speaker 1]:  i for the chimmini AIS。
[Speaker 1]:  so it's it's not a coding agcient。
[Speaker 1]:  it's not gmini CI。
[Speaker 1]:  it's really in ACI that your agent can use to call the germini api，
[Speaker 1]:  meaning it can call none of banana，
[Speaker 1]:  or only if you want to generate some assets，
[Speaker 1]:  but you can also use it to create those agents iterate on those agents and improve those agent。
[Speaker 1]:  the QR code should bring you to like the getaabrepository。
[Speaker 1]:  and then also，
[Speaker 1]:  we have dedicated skills for working with the interactions api and the agents api，
[Speaker 1]:  if you want to to play around with it later。
</details>

### 演示一：AI Talk Radio 托管智能体与音频播放
现在进入演示环节。我当前处于 Google AI Studio 的“AI Talk Radio”界面中。如果大家观看了此前 Google I/O 的开发者主题演讲，可能已经见过这个功能。它实际上是构建在 Managed Agents 之上的一个前端界面。我们稍后会剖析其 Agent 的底层结构，从业务逻辑上看，它是一个能够调用各类 Gemini 模型的脱口秀电台 Agent：它可以生成节目缩略图、合成语音、生成背景音乐，并执行联网调研，相当于一个一键式的电台内容生成器。

<details>
<summary>Original English</summary>
[Speaker 1]:  and now let's let's do some someday。
[Speaker 1]:  most。
[Speaker 1]:  so i'm in AI studio inside。
[Speaker 1]:  i talk radio if you have seen or attended the google IO developer canote，
[Speaker 1]:  you might have seen uh this already。
[Speaker 1]:  um that's just a simple UI on top of manage agents。
[Speaker 1]:  we managagents。
[Speaker 1]:  we are going to look at the agent in a little bit，
[Speaker 1]:  but it's basically a talks show radio，
[Speaker 1]:  and that talks show um agent has access to all of the different chaerman i model，
[Speaker 1]:  so it can generate thup nail。
[Speaker 1]:  it can generate um speech。
[Speaker 1]:  it can generate music。
[Speaker 1]:  it can do research。
[Speaker 1]:  and it's basically a one short radio generator，
[Speaker 1]:  and we give it a try。
</details>

我们来现场试一下：我希望生成一期讨论“披萨上到底该不该放菠萝”的电台节目。这项功能免费开放，大家后续访问该 Applet 时，每天都可以免费生成属于自己的 AI 电台节目。整个运行过程如下：第一步，系统启动沙盒环境，随后模型开始规划并拆解任务步骤；接下来它在沙盒中安装 Python 依赖项、读取配置好的技能，并持续往下推进。

<details>
<summary>Original English</summary>
[Speaker 1]:  and i want a talk show radio on whether pineapples belong on a pizza or not，
[Speaker 1]:  and it's free to use。
[Speaker 1]:  so if you go to the airpllet later，
[Speaker 1]:  you can like have free day ily，
[Speaker 1]:  use it to create your own ei talks，
[Speaker 1]:  show radio and what happens。
[Speaker 1]:  it's like first step，
[Speaker 1]:  we start our environment and then the model start thinking on what it needs to do。
[Speaker 1]:  and then the first step is like it installs our python dependencies，
[Speaker 1]:  and it reads our skills and and it continues to work since this will take a little bit。
</details>

由于生成完整节目需要几分钟时间，我提前预跑了一期关于“麦片应该先放还是牛奶应该先放”的节目。这个脱口秀电台最有趣的地方在于，它不像常规的单人播客，而是模拟了多位嘉宾各抒己见、进行推理论辩的互动场景。我们来听一下片段：

<details>
<summary>Original English</summary>
[Speaker 1]:  i already ran a talxial radio on whether we should put in cereal first or look first。
[Speaker 1]:  and the very interesting part about a talxial radio。
[Speaker 1]:  it's not like a podcast。
[Speaker 1]:  you ll listen to。
[Speaker 1]:  it's really you have multiple um people like reasoning and like sharing their opinions on it，
[Speaker 1]:  and we give it a quick listen。
</details>

>> [Speaker 2]: 准备早餐麦片碗是否存在正确的物理顺序？还是说我们正在与烹饪界的混乱玩火？欢迎收听 AI Talk Radio，我是 Paul，正在伦敦演播室为您直播。今天我们将探讨这场伟大的早餐辩论：先倒麦片还是先倒牛奶？我们将客观剖析两种方式的优缺点。接通听众热线，第一位是来自波士顿的 David。David，请讲。
>> [Speaker 2]: 好的，谢谢 Paul。听着，必须得先倒麦片。这是基本的逻辑，对吧？麦片是自变量。你把它倒进碗里，能直观看到它的体积，然后再加入牛奶进行补充。而且，如果直接把干燥的麦片倒进盛有牛奶的碗里，牛奶会溅得到处都是，彻底一团糟。这就像土豆泥的比喻：你绝不会先把肉汁倒进盘子里，再往上面扔一团土豆。
>> [Speaker 2]: 形象的比喻，David。清洁度与分量控制确实是很有力的论据。我们来听听反方观点。热线上是来自悉尼的 Sarah。Sarah，欢迎你。
>> [Speaker 2]: 嗨，Paul。听我说，David 完全搞错了。先倒牛奶对口感把控而言是彻底的颠覆……

<details>
<summary>Original English</summary>
[Speaker 2]:  is there a correct physical order to preparing your breakfast bowl？
[Speaker 2]:  or are we frting with colonary chaos？
[Speaker 2]:  welcome to AI talk radio？
[Speaker 2]:  i'm paul broadcasting from our london studio today。
[Speaker 2]:  we are exploring the great breakfast debate cereal first versus milk。
[Speaker 2]:  first，
[Speaker 2]:  we will objectively break down the proson comes of both methods。
[Speaker 2]:  let's go to our lines。
[Speaker 2]:  we have david calling from boston。
[Speaker 2]:  david，
[Speaker 2]:  you're on the air。
[Speaker 2]:  yeah，
[Speaker 2]:  thanks，
[Speaker 2]:  paul。
[Speaker 2]:  look it。
[Speaker 2]:  it's gotto be serial first。
[Speaker 2]:  it's basic logic c right？
[Speaker 2]:  cereal is the indedent dent vable。
[Speaker 2]:  able you pour it，
[Speaker 2]:  you see the volume，
[Speaker 2]:  then you add note the compliment plus like if you pour drive syrial into a ball or milk，
[Speaker 2]:  it's rashes everywhere。
[Speaker 2]:  it's a total mess。
[Speaker 2]:  and the msh potato analogy，
[Speaker 2]:  you wouldn't grave in AA band and drop a lump potatoes on top。
[Speaker 2]:  ate a striking analogy。
[Speaker 2]:  david cleaniness and porcean control are certainly strong arguments。
[Speaker 2]:  let's hear the counterpoint。
[Speaker 2]:  we have sarah on the line from sydney。
[Speaker 2]:  sarah，
[Speaker 2]:  welcome，
[Speaker 2]:  hi，
[Speaker 2]:  paul。
[Speaker 2]:  i get look，
[Speaker 2]:  david。
[Speaker 2]:  has it all wrong milk first。
[Speaker 2]:  is it a total guin chchof a texture go？
</details>

大家如果想自行体验，可以访问 aistudio.google.com。在左侧导航栏的“Build”区域中有一个“Gallery”（案例库），汇集了针对 Gemini 预先构建的应用案例。向下滚动就能看到全新的构建体验，其中就包含刚才展示的 Talk Show Radio。点击进入该 Applet 后支持进行“Remix”（二次创作与调整）。如果不喜欢脱口秀电台，想改成纯粹的播客应用，可以非常方便地借助 Gemini 按需调整。

<details>
<summary>Original English</summary>
[Speaker 1]:  so if you want to play around with with yourself，
[Speaker 1]:  self can go go a iidot studio。
[Speaker 1]:  and on the idol studio，
[Speaker 1]:  you have that built section on the left side，
[Speaker 1]:  and there is a gallery，
[Speaker 1]:  and gallery is basically prebuild applets use cases for gmini。
[Speaker 1]:  and if you scrolled down to it，
[Speaker 1]:  you have new build experience with，
[Speaker 1]:  and they re's the talxture radio。
[Speaker 1]:  if you click on it，
[Speaker 1]:  you will find the applet。
[Speaker 1]:  you can can remimix it，
[Speaker 1]:  meaning。
[Speaker 1]:  you can like adjusted。
[Speaker 1]:  so if you don't like talxture radios，
[Speaker 1]:  and you would rather have，
[Speaker 1]:  i don't know some real podcaast application。
[Speaker 1]:  you can like very easily together with chermini attrusted to your own needs。
</details>

这些 Applet 的底层代码全部开源，我们可以快速看一下 Agent 的具体构成。实质上它全由文件组成：在运行环境中包含一个 `AGENTS.md` 文件，当环境启动时该文件会被加载并并入系统指令中。这是一个非常基础的文本文件，涵盖了 Agent 所需执行的全部操作指令：先进行调研、为不同角色编写台词脚本、生成音乐与语音，最后合成完整音频。为了支持上述步骤，我们为它配置了相应的技能。例如在语音生成（TTS）方面，包含一个说明如何执行的 skill 规范和一个 Python 脚本。该脚本让沙盒内的 Gemini Agent 能够反向调用 Gemini 模型，通过 Interactions API 生成所需语音片段。这就构成了 Agent 的全部逻辑。如果想把该 Agent 从前端 UI 迁移至后端服务，只需直接复制这批文件、通过 API 创建 Agent 即可调用。

<details>
<summary>Original English</summary>
[Speaker 1]:  and since applets are all open in terms of code，
[Speaker 1]:  we can also take a quick look on like how our agent ruliis and our agent this just files。
[Speaker 1]:  so we have an agents md file inside our n environment。
[Speaker 1]:  that file will be loaded on environment start up，
[Speaker 1]:  which is then included into the system instruction，
[Speaker 1]:  very basic agand，
[Speaker 1]:  m and defile。
[Speaker 1]:  it has all of like the instructions for our age ing to do so。
[Speaker 1]:  it should do some research，
[Speaker 1]:  right？
[Speaker 1]:  some scripts for the different people generate music，
[Speaker 1]:  generate a speech mikes，
[Speaker 1]:  everything together。
[Speaker 1]:  and to do all of those works，
[Speaker 1]:  we have skills for it。
[Speaker 1]:  so if we look into like the TDS generation，
[Speaker 1]:  we have a school and how to run it，
[Speaker 1]:  we have a python file that python file itself allows the germiniation to call out a gmini model。
[Speaker 1]:  so it uses the interrections api to generate some speech，
[Speaker 1]:  which we can then use。
[Speaker 1]:  and that that's all takes far agent。
[Speaker 1]:  and if you want to take that agent from the ui to like a beagand，
[Speaker 1]:  it's really you just need to copy that file and create the agent and then use it。
</details>

### 演示二：Playground 内探查沙盒底层环境
如果大家想在 Playground 内部直接体验 Agent 自身，我们在模型选择器中新增了 Agent 模块。如果想测试深度研究（Deep Research）可以直接选择体验；这里也集成了 Antigravity Agent。在 Antigravity Agent 下，我们提供了 6 款不同的智能体模板，供大家挑选并观察其实际运作逻辑。我们选择其中一个通用模板进行演示。我最喜欢做的一件事就是让 Agent 自行探测其运行环境。输入提示词后，首次请求启动沙盒环境大约需要 7 到 10 秒；随后便能看到 Agent 展开工作：显示其推理思考过程，以及它在沙盒中执行的具体 Bash 命令。它依次检查了操作系统版本、CPU 核心数与内存大小。

<details>
<summary>Original English</summary>
[Speaker 1]:  and if you want to play around with the agent itself inside the playground，
[Speaker 1]:  we have uh inside the model pickers，
[Speaker 1]:  a new agent section。
[Speaker 1]:  so if you want to test deep research，
[Speaker 1]:  go test deep research，
[Speaker 1]:  but as also the antigravity agent，
[Speaker 1]:  and on the anti gravity agent，
[Speaker 1]:  we have six different agent templates，
[Speaker 1]:  uh，
[Speaker 1]:  which you can like very easily test，
[Speaker 1]:  select and and see how it works。
[Speaker 1]:  we go into like the the sun of one。
[Speaker 1]:  and what i really like to do is like exploiting environment，
[Speaker 1]:  like let's see what the agent finds out about the where it is running。
[Speaker 1]:  we sent our prompt。
[Speaker 1]:  and now it's not the environment should take for the first request like seven to ten seconds。
[Speaker 1]:  and then we see the agent like doing its work。
[Speaker 1]:  so we have some reasoning，
[Speaker 1]:  we have so on best commandds it runs。
[Speaker 1]:  so kid checks，
[Speaker 1]:  uh，
[Speaker 1]:  russian west watasi'm。
[Speaker 1]:  i'm running on what cpu memory i have。
</details>

Agent 返回了检测结果：它运行在 Ubuntu 系统上，配备 8 核心 vCPU、16GB 内存，并已预装 Python 与 pip。随后你可以继续追问，比如询问“环境中是否安装了 Node.js？”。它可以直接根据上下文继续跟进执行。此外，界面右侧还提供了下载整个环境的选项；如果 Agent 在运行中生成了文件，你可以直接打包下载，或者通过对应的专属 API 提取。

<details>
<summary>Original English</summary>
[Speaker 1]:  and and we get back a response from our agent that is gruns on a buntu。
[Speaker 1]:  um has eight BCPU sixteen gagive about mememory python installed pip instaland。
[Speaker 1]:  then you can like really continue。
[Speaker 1]:  well，
[Speaker 1]:  well，
[Speaker 1]:  let's see um，
[Speaker 1]:  do you do we have node installed？
[Speaker 1]:  um so you can like very easily photo up，
[Speaker 1]:  and it just continues based on like my prompt。
[Speaker 1]:  and and also，
[Speaker 1]:  you have the option on the right side to download the environment。
[Speaker 1]:  so if your agent has created some files，
[Speaker 1]:  you want to extract out of the environment and share it can very easily download it，
[Speaker 1]:  or there's an api for it as well。
</details>

### 总结与问答
我把界面放大再快速梳理一下整体运行机制：当客户端发起请求时，服务端启动沙盒并加载全部配置文件，整个 Agent 执行循环完全在我们的服务端内部运行。在此之前，开发者构建智能体通常需要在客户端管理函数调用（解析模型输出的函数调用、在本地执行后再把结果传回模型）；而使用托管的 Managed Agents 后，只需一次 API 请求，所有操作均在远程沙盒内部闭环完成。它支持挂载远程 MCP 服务，也可以在沙盒环境内部运行本地 MCP 服务。如果大家感兴趣，Gemini API 官方文档中的 Agents 板块提供了快速入门指南，详细介绍了如何发送首个请求并构建属于自己的 Agent；同时也可以安装编程相关技能，利用 Claude Code 或其他模型来辅助构建。非常感谢大家的参与，如果现场有疑问，我很乐意解答。

<details>
<summary>Original English</summary>
[Speaker 1]:  and then um what else to quickly show you again，
[Speaker 1]:  how it works，
[Speaker 1]:  i can make that a little bit bigger。
[Speaker 1]:  so when you when we send the request，
[Speaker 1]:  um we like stoart the sandbox and it loads all of our files。
[Speaker 1]:  and then we have like this agent loop completely on our server。
[Speaker 1]:  so when you build agents，
[Speaker 1]:  normally a lot of times you need to manage the function calling on your client，
[Speaker 1]:  right？
[Speaker 1]:  you need to pass the function call，
[Speaker 1]:  run it on somewhere and then send back the function result。
[Speaker 1]:  and with the managed agents，
[Speaker 1]:  it's really trust a single API call and everything runs inside that remote and box。
[Speaker 1]:  you can also connect remote MCP service hole，
[Speaker 1]:  run uh local MCP service inside of the environment。
[Speaker 1]:  and um yeah，
[Speaker 1]:  really get started ted。
[Speaker 1]:  if you 're interesrested about um we have cregreat documentation onside of jerina API under agents with a quick start，
[Speaker 1]:  which walks you through how to set your first request，
[Speaker 1]:  build your first age and and get started。
[Speaker 1]:  and then，
[Speaker 1]:  of course，
[Speaker 1]:  uh，
[Speaker 1]:  installed the coding skills to have cloud cotex or whatever model you use to to help you get started。
[Speaker 1]:  and thank you for for coming。
[Speaker 1]:  if you have some questions。
[Speaker 1]:  i'm like here。
[Speaker 0]:  the。
</details>