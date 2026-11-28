---
author: AI Engineer
date: '2026-11-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=ntVpbyDTYaQ
speaker: AI Engineer
tags:
  - admission-control
  - llm-inference
  - load-shedding
  - agentic-traffic
  - benchmarking
title: 自托管大模型推理的准入控制与拒绝机制
summary: Audible 的 Hershel 与 SAP 的 Perv 探讨自托管大模型在应对编程智能体高频突发流量时的准入控制问题。演讲分析了在推理引擎前置准入层的必要性、策略设计维度及评估指标，并开源基准评测工具 admit-perf。
insight: ''
draft: true
series: ''
category: architecture
area: tech-engineering
project: []
people:
  - Hershel Jan
  - Perv
companies_orgs:
  - Audible
  - SAP
  - OpenAI
products_models:
  - admit-perf
  - agentship
  - vLLM
  - SGLang
media_books: []
status: evergreen
---
### 演讲背景与动机：为什么需要准入控制

**Hershel Jan**: 大家早上好。我叫 Hershel Jan，身边这位是 Pearl。今天我们要探讨的是“学会说不”，也就是所谓的准入控制（admission control）。当编码智能体发送的海量请求压垮你自己托管的 LLM 时，系统如何决定放行哪些请求。

在继续之前，我们先做一个简短的自我介绍。我是 Audible 的资深软件工程师，负责那里的部分机器学习/人工智能基础设施。同时我也在撰写一本名为《大规模 LLM 推理》（LLM inference at scale）的开源手册，目前已经收获了 300 多个 star。此外，我还在维护一个名为 agentship 的开源框架，帮助大家以极快的速度交付可靠且安全的智能体运行时（agentic harnesses）。Perv，你要自我介绍一下吗？
<details><summary>Original English</summary>
**Hershel Jan**: Good morning everyone. My name is Hershel Jan and I have here with me Pearl. Today we are going to talk about saying no. It's called as admission control. How our system decides which request to get in when your coding agents overwhelm the LLMs you host yourself.

Uh before we move on a quick intro about us.

So I am a senior software engineer at Audible where I lead some of the MLAI infrastructure.

Uh I am also writing an open-source handbook called as LLM inference at scale. It has received over 300 plus stars by now.

I am also maintaining an open-source framework called agentship which helps you ship reliable and secure agentic harnesses in an ultra fast speed. Uh perv would you like to introduce yourself?
</details>

>> 当然可以。大家好，我是 Perv。我是 SAP 的资深软件开发工程师，主要负责云应用与 LLM 基础设施。我编写过一份 LLM 微调指南，也是 agentship 的贡献者。目前我正在构建 task tracker，这是一个面向你和你的智能体的本地任务看板。

除了这些之外，如果你想与我们建立联系，幻灯片上附有我们的 LinkedIn 二维码。现在把麦克风交还给 Hershel。
<details><summary>Original English</summary>
>> Sure. Hi everyone. I'm Perv. I'm a senior software developer at SAP. I work on like cloud application and LLM infrastructure. I wrote an LLM fine-tune guide. I contribute to agentship and I'm like building a task tracker which is a local post task board for you and your agent.

Uh apart from this if you would like to connect with us our LinkedIn QR codes are right there on this slide. Now back to you Hershel.
</details>

**Hershel Jan**: 太好了。这是我们今天的议程：首先，我们会从动机讲起，剖析为什么任何服务技术栈接纳流量的能力都是有限的；其次，我们将深入探讨准入控制，看看“说不”的决策位于何处以及它需要读取哪些信号；第三，我们将梳理一些经过验证的成熟策略，即系统做出准入决策的各种不同方式；第四，我们将深入基准测试（benchmarking），带大家学习如何证明你的准入策略是否真的有效。

那么，让我们从动机开始。为了讲清这一点，今天所有的事情都围绕推理过程展开，因此我们先来理解一下什么是推理。今天讨论的一切，本质上都发生在推理期间。简单来说，推理就是有人向模型发送一个提示词（prompt），并获取模型返回答案的这一过程。

第一步，用户的提示词进入系统。这是一串词语序列，例如“修复一个报错的测试”。运行在 GPU 上的模型会逐个 token 地写出答案。正如我提到的，一个 token 大致相当于一个词。模型写出第一个词，然后基于这个词生成第二个词，再结合前两个词生成第三个词，以此类推。它无法一次性写出所有词，因为每个词都依赖于前一个词。所有词生成完毕后，便会流式传输回发起请求的用户端。发送提示词并收到完整回答的整个过程，就构成了一次请求。

现在请大家记住一个小细节：模型在生成结束前，根本不知道这个答案最终会有多长。它只有在写出最后一个 token 时才知道。请牢记这一点，几分钟后它会变得非常重要。

模型从不会直接暴露在公网之上。每个请求都会经过一条简短的流水线：请求始于你的应用程序或智能体，随后到达 API 网关。网关负责校验 API 密钥，并统计你发送的请求数量；接着，路由器会选取一个副本（replica，即模型的一个运行中实例）；最后，请求落地到推理引擎。常见的推理引擎包括 vLLM、SGLang、TensorRT 等。引擎才是真正托管模型的核心组件。它实际负责模型服务，并将模型权重加载进 GPU。它将多个请求打包成一个批次（batch），以确保 GPU 始终处于忙碌状态。并且对于每一个请求，引擎都会维护一个称为 KV cache 的东西。通俗地说，KV cache 就是请求在生成回答过程中不断累积占用的内存。回答越长，这部分内存消耗就越大。

请在脑海中保留这幅架构图。这里的每一个模块都会做出某些决策，但其中缺失了一个关键决策，我们稍后就会揭晓。
<details><summary>Original English</summary>
**Hershel Jan**: Great. So here is the plan. We are going to start with understanding the motivation why any serving stack can admit so much of a traffic.

Second, we try to dive into admission control where the decision to say no lives and what it needs to see. Third, we will go through some of the proven strategies, the different ways a system can actually make the admission decision. And fourth, we will try to dive into the benchmarking where you will learn how to prove that your policy for admission is working or it's not working.

So let's get started with the motivation. Um and for this everything today uh let's try to understand what is inference. Everything today happens during this inference itself. So inference is simply a moment when someone sends a prompt to the model and gets back an answer.

So the step one is like a user prompt comes in. It's a sequence of words. Uh for example, it could be like failing a fix a failing test. The model which is running on your GPUs writes the answer one token at a time. A token is roughly like a word as I mentioned. Uh it writes the first word then uses that word to pick the second uh then it uses both to pick the third and it keeps on continuing like that and it cannot write all of them at once because every word depends on the previous one. So those once all the words are generated they stream back to the user uh who ask for the result and that volt prompt and the answer out is like that one request. Now I want you to hold on to one small detail like model has no idea how long this answer is going to be. It only finds out whether it writes when it only finds out when it writes the first last token.

Keep that in mind. It will matter in the few minutes.

So a model never sits on the internet itself. Every request travels through a short pipeline. It starts in your app or your agent. Then it reaches your API gateway which checks your API key counts how many requests you are sending. Then a router picks a replica which which is just one running copy of the model and finally the requests land on the inference engine. The common some of the common inference engines are the VLMs, SGLAN, Tensor RT etc. engine is what actually hosts your model.

It actually serves your model uh and it loads the model weights into your GPUs. It groups many requests into one batch so the GPU stays busy and for every request it keeps something called as a KV cache. In plain words, the KV cache is the memory the request builds up when it try when its answer is being written. Longer the answer, bigger this memory gets.

Keep this picture in your head. Every box here makes some decision but one decision is missing and we will find it out in the few minutes.
</details>

**Hershel Jan**: 首先，一个引擎到底能承载多少负荷？每一次部署都有其上限，这源于三个相互拉扯的目标：质量（Quality，即模型规模的大小与精确度）、延迟（Latency，即首个 token 及后续每个 token 的到达速度），以及吞吐量（Throughput，即 GPU 同时能服务的请求数量）。常言道“多快好省，三者不可兼得，你只能选其二”，这里也是一样的道理。你无法同时兼顾或优先考虑全部三项目标，因此每个产品都必须做出取舍。例如，对于交互式聊天，你会倾向于选择质量和延迟，因为用户对此更加敏感，如果质量下滑或延迟飙升，用户立刻就能察觉；对于异步智能体，你则希望获得更高的吞吐量与质量，因为若质量不达标，你就必须重新执行任务，而对于这类后台异步任务来说，重试的代价非常高昂；至于自动补全这种大流量实时系统，则往往倾向于兼顾延迟和吞吐量而牺牲质量，因为运行自动补全并不需要昂贵的大模型。

但无论你放弃哪一个维度，在满足服务水平目标（SLO）的前提下，系统能承载的最大负载始终是有限的。假设在当前的部署中，这个上限是并发 8 个请求。在平常的时间里，你可能根本注意不到这个限制；但现在试想一下，如果 40 个请求在短短 2 秒内同时涌入，那将是极大的负载冲击。

这绝非凭空假设，世界上顶级的模型提供商都经历过类似事故。这里列举了相隔两年的两份公开复盘报告：2023 年 11 月 8 日，OpenAI 在经历了一整天的异常高流量冲击后（可能远不止 40 个请求，而是数百万级别），其路由服务器内存耗尽，健康检查相继失败。他们尝试增加副本，但随后不得不进行回滚，最终的脱困方案是切断进流并逐步缓慢放量。2026 年 1 月 21 日，Anthropic 的 Sonnet 3.5 层级先是变慢，随后在约 90 分钟的时间内频繁报错，官方给出的原因很简单：算力不足以支撑需求。

现在我们来看看两家团队在事后制定的下一步改进措施。没有任何一方表示“我们需要更快的推理引擎”。OpenAI 的后续改进是做优雅的降级丢载（graceful load shedding），Anthropic 的则是更早地检测容量上限。两者的核心思想完全一致，只是措辞不同：更早地对请求做出裁决，以确定放行哪些请求。我们在附录中链接了更多相关事故报告，有兴趣的观众务必深入阅读。
<details><summary>Original English</summary>
**Hershel Jan**: First, how much an engine can actually hold.

Every deployment has a ceiling and it comes from the three targets that pull against each other. Quality is how big your and precise your model is. Latency is how fast the first token arrives and every token after it. Throughput is how many requests your GPUs can serve at a same time. You know the old saying good, fast, cheap, but you have to pick two. It's the same here. You cannot pick all the three. You cannot prioritize all the three. So you can't So every product has to pick two. For an example like an interactive chat, you would want to go with the quality and the latency because users are more sensitive to that. It's quite obvious to the users if the quality is down or the latency is high. For something like an async agents, you would want to go with a higher throughput as well as quality. If quality is less, you will have to redo the task and redoing is very very expensive because these are the background and the asynchronous tasks. And the high volume real-time systems such as the autocompletes they would try to favor latency as well as and the throughput in favor of the quality because you don't need an expensive model for doing the autocompletes for you. But whichever corner you give up there is still a maximum load you can carry while hitting your SLO your service level objective. Let's say that on this deployment it's eight requests at once. In a normal minute, you never notice that limit. Now, picture the 40 requests arriving in the same two seconds.

It's such a high load.

And this is not like hypothetical. It has happened to like biggest providers in the world. Here are the two public postmortms two years apart.

On November 8, 2023, OpenAI after a day of unusual heavy traffic, maybe not 40 requests, it would be some million requests, their routing servers ran out of the memory. They started failing their health checks. They added more replicas, then had to roll them back. The way out was to cut incoming traffic and ramp it up slowly. In January 21 2026 enthropic the sonnet 4.5 tire gear got slow first then it started returning errors over about 90 minutes. The cause they gave was simple not enough compute for the demand.

And now let's look at what each team decided as their next set of the action item. Neither of them says we need a faster engine.

Open AI's followup is graceful load shedding. Enthropics is detecting capacity limits earlier.

It's the same idea in the different words which is decide on your request sooner

to make sure which request gets in. And there are more incidents which we have linked in the appendix. If you are interested definitely go and read through them.
</details>

**Hershel Jan**: 如果从这些后续措施逆推，它们全都指向同一个位置：系统的前门（front door）。我们再次展示这条流水线，并将缺失的环节补齐：现在我们有了客户端、准入层（admit layer）、队列路由器（Q router），然后才是引擎。客户端绝不能直接与引擎对话，也不能直接与队列对话，中间必须有一个准入阶段。

准入是在请求消耗任何 GPU 显存之前做出的决策，它只有三种可能的结果：立即启动；暂缓请求（接受该请求但让其等待）；拒绝（即现在不行，可以在此时抛出如 429 等不同类型的错误，我们在第二部分会更深入地讲解）。这就是我们流水线中此前缺失的决策。

为什么它必须发生在到达引擎之前？如果真的盲目接纳了请求，那句“好的（yes）”会付出什么代价？我们来看一下推理的两个阶段：预填充（prefill）和解码（decode）。首先是预填充，这是引擎读取提示词并构建请求 KV cache 的过程；接着是解码，引擎逐个 token 写出答案。每生成一个 token，cache 就会增大一点，而所有这些显存都会被持续锁定，直到请求完成。因此，一声“好的”绝不仅仅代表一个瞬间，它是一项贯穿请求整个生命周期的承诺。

看这个例子：有请求 A 和请求 B。如果你接纳了属于短回答的请求 A，随后接纳了属于长回答的请求 B；此时当你要接纳同样是短回答的请求 C 时，我们根本无法预测它需要耗时多久，因为显存中已经驻留了一个长耗时请求。我们到底该不该接纳请求 C？因此，接纳每个请求都是有代价的，因为随意放行仍然可能导致 SLO 违约。

除了对 SLO 的影响，显存也是重灾区。以下是它对 GPU 造成的后果：每个正在运行的请求在生成文本时都会不断消耗 cache，总显存占用持续攀升。当显存饱和时，引擎只有三种应对方式：要么直接丢弃请求，要么将其置于等待状态（即进行显存置换 swap），要么干脆报错表明无法提供服务。这当中的每一种方式都会在请求处理过程中造成不可避免的延迟，不仅再次破坏 SLO，还会浪费显存。

为什么这成了我们的问题？OpenAI、Anthropic 等成熟团队都在为其推理基础设施构建自己的专用服务栈。但之所以我们也会面临这一挑战，是因为许多团队出于隐私考量，希望在自己的 GPU 上托管专属模型；或者出于成本效益的考虑选择自建，同时又必须防止自建 GPU 算力被过度消耗，因此他们必须在自身的推理生态中有效地决策到底服务哪些请求。

此外，抵达前门的流量特征也发生了根本性的变化。以往是人类在聊天，用户一次只发送一个请求，每次提问之间会有数秒的阅读停顿，回答速度较慢也可以接受。但现在编码智能体接管了这一切：它们会发送海量的调用，伴随着重试、暂停以及回滚撤销等操作。集群必须处理如此压倒性的海量流量，这意味着集群有责任做出明智的决策，决定接纳哪些请求、拒绝哪些请求。

这就是具体的场景还原：你让智能体“修复一个报错的测试”。它会尝试触发多次工具调用，比如读取约 14 个文件、运行约 10 个测试，单次上层任务最终可能会组合出 40 到 50 次模型调用。而所有这 40 多次请求都需要打到 LLM 并获取响应。在这些请求中，有些是长耗时请求，有些是短提示词请求，我们必须有效地决定放行哪些、搁置哪些。这就是为什么我们必须关注准入控制，关注如何在整个推理生态中以正确的方式处置流量。
<details><summary>Original English</summary>
**Hershel Jan**: So if you walk backward from those follow-ups, they both point at the same place, the front door. Here is the pipeline again with the missing step filled in.

We have a client, we have an admit layer, the Q router, and then the engine.

It's never the client talking directly to your engine or client talking to your queue directly. There is an admission phase in between.

Admission is a decision made before a request takes any GPU memory and it only has three possible answers.

Admission decides whether to start now or you want to hold the request. You want to accept it but make it wait. Third is the reject. That means not right now. It can throw different amount of errors here such as 429s and we will dive into this bit more deeper in the second part.

this that is the decision that was missing from our pipeline.

So why does it have to happen before the engine and what would happen if you will actually accept the request what would be the cost of that yes so let's try to take a look at this like two phases of the inference like prefill and the decode. So first comes the prefill. That's the engine reading the W prompt, building the request KV cache. And then comes the decode. That's the engine writing the answer one token at a time. With every token, the cash grows a little more. All of that memory stays reserved until the request finishes.

So a yes is not a moment. It's a commitment that lasts the request whole life. And here you can look at the example.

There is a request A, there is a request B. Once you admit a request A which is a short answer request and then you admit a request B which is a long answer request. Now when you admit a request C which is again a short answer request, we don't know how longer it would take because there is a longer request which was already in the memory. Should we even take that request C or should we not even take the request C. So there is a cost associated of like admitting every request because admission could still result in missing out your SLOs's.

Another impact apart from the SLOs's is your memory.

Here is what it does to your GPU. So every running request it keeps growing your cache as it writes. So your total memory keeps climbing. When the memory gets to the full engine has three ways to cut. Either it will aait or like throw away your request. Either it will put it to your waiting state that means it will swap or it will just say okay I won't be able to serve and I I will probably return you an error. Every one of those throws I mean every one of those causes a certain delay in processing of the request. and missing out your SLOs's again while also wasting your memory.

So why is it like our problem like we have con servers from open AI anthropic bold teams which are serving their own infrastructure for the inference.

So it's a problem for us because there are teams who want privacy. They want to have their own models hosted on their own GPUs and they want it to be hosted on their own GPUs due to the cost perspectives but they have to also protect the burndown on those GPUs.

So they need to effectively decide which request to serve across their inference ecosystem.

On top of and on top of that like the traffic arriving at the door has also changed. Earlier there used to be a person that was chatting. He would send one request at a time. There would be a seconds of reading in between and then there would be a slow answer. But now coding agents they have taken over. There are tons of calls that these coding agents they send along with the retries, pauses, um like the undo calls as well and it there is such a overwhelming traffic that your cluster has to handle and what that means is cluster has a responsibility to take a wise decision of which requests to accept and which uh requests to reject.

And this is exactly that visualization. You ask your agent that fix an o test. It runs all your it tries to run multiple tool calls that is reading of the files like around there could be like 14 files. There could be like around 10 tests that it has to run and it would combine together to make 40 50 calls for just one request and all these 40 requests they require like reaching out to the LLM getting back the response. Uh and in between some of these requests would be long running some of the requests would be short prompt request. So we need to decide effectively where which one to pick and which one not to pick.

Yeah. And that was the like reason why we need to worry about admission control. Why we need to worry about handling the traffic right way across our infancy ecosystem.
</details>

---

### 准入控制的核心机制：位置、信号与三类动作

>> 好的，接下来进入准入控制的具体细节。在第 18 张幻灯片中，我们将探讨三个核心问题：
1. 决定接纳还是拒绝请求的裁决点究竟应该放在技术栈的什么位置？
2. 它需要观测哪些信息才能做出合理的判断？
3. 它应该给客户端返回什么？

我们再次审视这条流水线，并把每一层的职责明确写出来：智能体只能看到自己的调用，并决定何时重试；网关能看到 API 密钥和请求频次，负责执行基于各客户端的速率限制；路由器能观察到各个副本的健康状态，并决定调度给哪一个；而引擎则能看到当前的 KV cache 和正在运行的批次，负责决定请求的运行顺序以及何时执行驱逐与抢占。

每一层都在做决策。但现在如果我们向其中的每一层抛出同一个问题：“系统还有没有余量来接纳这个请求？”
智能体会说：“这不是我的工作”；网关会说：“我看不到系统内部状态”；路由器会说：“这不归我管”；而引擎则会表示：“我只有在已经答应接纳（say yes）之后，才能发现装不装得下”。这就是为什么我们流水线中间缺失了一个专门的准入模块。
<details><summary>Original English</summary>
>> Okay. So this brings us to the admission control.

Uh now moving on to the next slide. Uh that is slide number 18. So in this slide we will be covering three questions. Where does this decision from? which request to admit and which to reject sits back at your stack and the another question is what does it need to see to make a good call or judgment on the request and what does it returns back to the client. Moving on to the next slide. So here uh we see the pipeline again which each layer's jobs is written out. The agent sees its own call and decides when to retry.

The gateway sees API key and request count and enforces a rate limit rate limiter for each and the router which sees replicas or healthy and which one to pick. Now the engine sees its KV cache and the current batch and decides the order of request to run and what to evict and print.

So every layer decides something. Now ask each of them one question. Is the room for this request?

The agent says not my job. The gateway says I cannot see it. And the router say not my job and the engine says I only find out when I have already said yes.

The admission box is missing in in between.
</details>

>> 把这个决策点放置在何处，会改变它所能获取的视野以及系统运行的成本。业界有三个可选的位置：
第一个位置是引擎正前方的入口层（Ingress）。在这里，策略既能观察到请求本身的属性，也能读取引擎暴露的各项指标。你只需要一个代理（proxy）或网关，引擎本身无需做任何修改，保持原生状态。
第二个位置是队列边界（Queue boundary）。此时决策发生在引擎调度器内部，由它在挑选下一个执行批次时做出判断。
第三个位置是解码过程中（during decoding）。此时调度器可以在回答生成到一半时暂停请求，或者收回其 cache。

后两个位置确实能拥有更深度的运行时视野，但这意味着你必须修改引擎调度器。也就是说，你需要维护一套自行魔改的 vLLM 或 SGLang 分支，并且要在上游官方每次发布更新时疲于同步。因此，只有入口层（ingress）能够直接与完全原生的官方引擎配合工作。这也是我们今天接下来的分享所聚焦的位置。
<details><summary>Original English</summary>
>> So now moving on to the next slide. Um so where to put this decision change what it can see and what it cost you to run. So there are three possible moments. The first is an invoice right in front of the engine. Here the policy sees the request itself plus whatever metrics the engine exposes. All you need is proxy or gateway. The engine stays exactly as it is. The second one is the Q boundary. Now the decision happens inside the engineuler as it picks the next batch to run. The third is during decoding when the scheduleuler can pause a request or take back its cache halfway through an answer. Those later movement can see more but they mean changing the engineuler.

That means keeping your own modified copy of BLLM or SG lang and updating it every time original changes forever. So an ingress is the only movement that works with the engine exactly as it ships.

So that's where we will stay for the rest of the talk. So now moving on to the next slide.
</details>

>> 那么，入口层里到底运行着什么？你可以把它抽象为一个函数：它输入已知关于该请求的元数据以及系统的当前状态，然后返回三种结果之一：
1. **Admit（准入）**：请求立即进入引擎，此时显存正式被承诺锁定。
2. **Defer（暂缓）**：附带等待时间告知客户端暂且稍等，过一段时间再来。
3. **Reject（拒绝）**：携带错误码明确拒绝，并告知拒绝的具体原因。

在策略裁决放行（admit）之前，该请求不会产生任何成本，完全不占用任何 GPU 显存。

为了做出高质量的裁决，策略需要同时拥有两个维度的视野：请求维度的视野与引擎维度的视野。
在请求侧，需要了解：输入的长度、发起调用的客户端或租户标识、请求所属的智能体执行会话（session），以及截止时间（deadline）。
在引擎侧，需要了解：KV cache 的剩余容量、最老请求在队列中的等待时长、提示词命中的前缀缓存比例（cached prefix），以及各个副本池的负载水位。
回顾刚才的技术栈：网关只掌握左侧（请求）的信息，引擎只掌握右侧（运行时）的信息，两者都无法通盘掌握，这就是为什么准入必须作为一个独立的层级存在。
<details><summary>Original English</summary>
>> Uh so what actually sits in ingress, right? Uh so you you you can think of it as a function. It can take in what it knows about the request and current state of the system and it returns one of the three answers like if we have to admit the request. So the admit is the request enters the engine now and memory is committed for this moment. If it's deferred with a time we can call toao hold on like uh hold on and come back after some time and there is another decision which is with uh reject with a code that no here is the reason why and until the policy says admit the request cost you nothing. It holds no GPU memory at all.

Now moving on to the next slide.

uh to make the call well the policy needs two views at the same time from the request and from the engine. So from the request how long the input is, which client or tenant sends it, which agent session it belongs to, and a deadline. And from the engine point of view, how long uh KV cache is, how long the oldest request has been waiting in the queue, how often the prompt is already cached, and how how loaded each pool of replica is. Now look back at the ST. The gateway has left side and the engine has the right side. Nobody has the both.

And that's really why admission has to be its own layer. Now moving on to the next slide.
</details>

>> 这里我们将这 8 种信号转化为清晰的规则。每一项信号都会与阈值进行比较，一旦跨过阈值，就会触发对应的动作：
- **来自请求侧的规则**：
  - 如果输入长度过大，超过了显存的冗余空间（headroom），直接暂缓（defer）；
  - 如果某一客户端或租户超出了其配额份额，返回 429 予以拒绝（reject）；
  - 如果单个智能体会话中有过多的在途（in-flight）并发调用，附带等待时间进行暂缓（defer）；
  - 如果继续排队等待必然会导致该请求错过截止时间（deadline），直接拒绝（reject）。
- **来自引擎侧的规则**：
  - 当 KV cache 水位低于高水位线（high water mark）时，予以放行（admit）；
  - 当最老请求的等待时间超过目标阈值时，执行暂缓（defer）；
  - 如果提示词已经命中缓存，优先放行（admit），因为它的服务成本极低；
  - 当所有副本池均已饱和时，返回 529 拒绝（reject）。

这里有一条经验法则：优先挑选能在“秒级”发生变化的动态信号（例如队列排队时长），而不要依赖一分钟的平均值。因为编码智能体可以在 2 秒内打出 40 次调用，一分钟平均值在面临这种瞬时冲击时根本来不及反应。
<details><summary>Original English</summary>
>> Here are those eight signals turned into simple rule. Each one is compared to threshold and when it crosses it pushes towards the outcome in the colored pale from the request side.

If the input is too big to fit in the memory headroom just refer it. If a client or tenant is over it share reject it with 429. If one agent session has too many calls in flight defer with extras. If waiting would make a request miss its deadline anyway reject it from the engine side. Uh you can see at the bottom half of bottom half side. While KB cache is under high water mark admit it. When the oldest request has waited longer than your target defer it. If the prompt is already cached admit it first because it's cheap to serve. And when every pool is full, reject it with 529. One rule of thumb, pick the signal that changes in second, like a QH, not a one minute average. A coding agent sends 40 calls in 2 seconds. A minute average won't even notice. So that's what the policy reads. Now what does it say back? Now moving on to the next slide.
</details>

>> 我们逐一解析这三类反馈结果，并分别从服务端行为和客户端应对两个视角进行拆解。

**第一种：放行（Yes）**。服务端返回 200，并开始流式传输响应。在此瞬间，引擎内部会发生三件事：为完整提示词分配锁定 KV cache；该请求加入当前运行的批次；在后续的每一步解码中与其他请求并行生成 token。这部分显存会被持续锁定，直到请求完成或客户端断开连接。这正是我们在第一部分提到的承诺，它以 HTTP 响应的形式确立，因此准入决策必须在返回 200 之前做出，绝不能在此之后。

在智能体客户端层面，处理 200 的方式是：关注流本身，而非单纯看状态码。
1. **计时起点要合理**：应将超时计时器的起点设定在“收到首个 token 时”，而非“发出请求时”。在高负载情况下，光是预填充（prefill）阶段就可能耗费数秒；
2. **放弃时务必关闭连接**：如果你决定中途放弃请求，必须主动且彻底地关闭连接。因为服务端只有在请求正常完成或客户端断开连接时才会释放 KV cache。智能体端单方面超时却保持连接未释放，依然会霸占 GPU 显存；
3. **应对流中断**：数据流完全可能在传输中途断开，而且此时没有任何 HTTP 错误码，你只能拿到残缺不全的部分回答，必须在业务层决定是重试还是继续。简言之，200 只是开始的承诺，绝不是顺利完成的保证。

**第二种：暂缓（Defer）**。本质含义是“现在还不行”。服务端返回 503 并携带 `Retry-After` 头，告知客户端需要等待的秒数。策略会根据引擎当前状态来计算这个数值，例如当前运行批次还需多久结束并释放足够的 cache。
暂缓适用于容量有望很快恢复的场景，针对的是短期突发而非长期瓶颈。例如队列排队时间有所上升但系统整体尚未饱和。如果容量短时间内无法恢复，暂缓只会拖延问题，此时应当诚实地直接拒绝。

在客户端侧，处理暂缓非常直接：按照 `Retry-After` 的时间进行睡眠，并附带少量随机抖动（jitter），随后重新发起重试。抖动的意义在于引入微小的随机额外延迟，避免所有客户端在完全相同的时刻集体杀回。试想一下服务端在没有 `Retry-After` 时的遭遇：如果 10 个客户端各选重试延迟（通常默认为 0），它们就会同一时间并发重试，这就是原本 40 次请求演变成 80 次雪崩的过程；而配合 `Retry-After` 和抖动，重试流量就会被均匀摊平在服务端期望的时间窗口内。

**第三种：拒绝（Reject）**。即返回 429 或 529，明确表示“不行”。这两个状态码对应两种截然不同的根因：
- **429（Too Many Requests）**：表明该客户端或智能体所占用的资源超过了其应得的配额，问题出在调用方。策略观测到了单客户端超载、并发数过高或配额耗尽；
- **529（Site is overloaded）**：表明服务提供商整体过载（Anthropic 即采用该状态码），所有副本均已跑满，当前没有任何新请求能够进入。此时问题出在后端资源池，而非调用方。

针对拒绝，智能体的处理方式应当是：
- 收到 429 时，智能体必须主动自降负载，限制自身在途并发调用的数量；
- 收到 529 时，盲目加大力度重试只会让局势雪上加霜。此时应该延长等待时间、切换至其他备用模型提供商，或者直接将当前任务挂起留待后延。
- 无论面对哪一种拒绝，都必须设立重试预算（retry budget），采用指数退避（exponential backoff）加抖动机制；若连续多次尝试均告失败，则应如实告知最终用户当前状况。因为收到拒绝后依然全速重试，正是我们在开篇提及的那些系统复盘事故的罪魁祸首。
<details><summary>Original English</summary>
>> We will take the three answers one at a time and look at each from both sides. What the server sends and what your agent should do with it. First, yes, the server sends back a 200 and the response starts streaming. At that moment, three things happens inside the engine. It commits KV cache from the whole prompt and the request joins the running batch and decode one token per step alongside everyone else and it holds that memory until it finishes or until the client disconnects.

That's the commitment from part one just in the form of an HTTP response which is why the admission decision has to happen before 200 never after it.

Now the client side if we are writing the agent here is how to handle 200. Watch the stream not the status code. First time is properly start your timeout clock when the first token arrives not when you send the request under the heavy load prefill alone can take few seconds. Second, if you decide to give up, actually close the connection. The server only frees the KV cache when the request finishes or the client disconnects. An agent that times out but leaves the connection open is still holding the GPU memory. And the third one, uh, a stream can fail halfway through, right? And that that's no status for that, right? and you're you're left with partial answer and you have to decide whether to retry or carry on. In short, 200 promise to start. It's not a promise to finish. Right?

The second answer is dipper which basically means not yet. The server sends back 503 with retry header. The header tells the client how many seconds to wait. The policy picks that number from the engine. For example, how long until the running batch finishes and freeze the enough cash and you differ when capacity is coming back soon? It's a burst, not so not a trend, right? And for example, like if you think about it like Q age is rising but the system isn't saturated.

If the capacity isn't coming back anytime soon, a dipper just kicks kicks the can down the road, right? And in that case, we can just reject it with the honest answer.

Moving on to the next slide. On the agent side, handling a defer is simple. Sleep for retry after time and a little random jitter, then retry again. The jitter just means a small random extra delay. So client don't like don't call or like don't at all come back at the exact same moment. They will have to wait.

Look what the server sees from 10 retries without retry after every agent picks its own delay. And that's usually that's usually zero. So they all come back at once. That's how 40 calls turns into 80.

With retry after and jitter the retry spreads out across the window serves asked for.

Okay. So if if we see the uh reject reject returns 429 or 529 the third answer is no. Uh and there there are two different codes for it because there are two different reasons. A 429s means too many requests. This particular client or agent session is using more than its share. The policy saw something like per client load, the number of concurrent calls or a kota. The problem is the caller and then the 529 means the provider is overloaded. Enthropic uses this code. Every replica is sold. So nobody is getting in right now.

The problem is pool not the caller.

Now uh handling a reject. So how should agent react on 429? Reduce your own load. Cap how many calls that agent has in flight at once.

And on 529 retrying harder only makes this worse. Waiting longer switching to different model provider or park the task for later. and one either and on either one keep a retry budget. Use expansion exponential back off with jitter which means waiting longer after each failed try and after few tries tell the user what's going on because a reject that gets retrieded at full speed is how you end up in one of the postmodm from the talk at we described at the starting.

Now over to you Hershel
</details>

---

### 准入策略分类与决策树构建

**Hershel Jan**: 谢谢 Perv。在第三模块中，我们将学习业界已经落地的不同准入控制策略。到目前为止我们已经发现，现有技术栈中没有任何一层会过问“系统是否还有余量”，这一层需要我们自己去补齐，而现在我们要赋予它一个智能大脑。我们会分析为什么单纯统计请求次数是远远不够的；把策略拆解为四个维度选项；回顾四篇顶会论文分别做出了怎样的选择；最后给出一个你可以直接应用于自身生态系统的决策树。

我们先从大多数团队已经具备的做法讲起：计数，即统计请求数量。最简单的思路是在网关处做速率限制，为每个 API 密钥分配预先设定好的固定配额。这对于维持客户端之间、租户之间的公平性非常有效，但对于保护 GPU 毫无帮助，因为它完全不随 GPU 或集群上正在发生的实际负载动态调整。

在代理层设置固定在途并发上限（fixed cap）会稍微近一步，它统计每个副本上正在处理的在途请求数。但问题在于，一个简短的提取任务和一个长耗时的复杂规划工具调用，在计数器里被等同视之；然而 GPU 的实际承载能力在每一个批次中都在动态变化。因此在实践中，这种做法大多会导致队列积压，最终全凭客户端超时来被动拒绝。无论是网关还是代理，都不知道打进来的 40 次调用到底是轻量级还是昂贵消耗。而具备成本感知（cost-aware）的策略则能结合引擎当前的实时状态，预估每个请求在 KV 显存与 token 上的真实成本，在请求真正侵占显存之前果断说不。一言以蔽之：数量（count）并不等同于成本（cost）。
<details><summary>Original English</summary>
**Hershel Jan**: three.

Thank you P. Uh so this is the module three where we will try to learn about the different strategies uh that have been rolled out for the admission control. So far we have seen that no layer in the today's stack asks where uh whether there is a room and that layer is ours to add and now we give it a brain. So we will look at why counting requests isn't enough. Breaking a policy down into four different choices. See what four different research paper chose and finish with a decision tree that you can use onto your own ecosystem.

So let's start with what most team already have which is counting. Yes. Counting the number of the requests. A simple idea is to rate limit at the gateway which gives API key a fixed allowance set in advance. It's great for keeping the clients fair, keeping your tenants fair with each other, but it does nothing to protect your GPUs because it doesn't change with the load that is happening onto your GPUs or your cluster. A fixed cap at the proxy gets closer. It counts how many requests are in flight on each replica. The problem is that the quick crep and a long planning to call count exactly the same while the real capacity of the GPU changes with every batch. So in practice it mostly cues and clients timeout ends up doing the refusing.

Neither one knows whether our 40 calls are cheap or expensive.

The cost of air policy does though and it estimates each request will actually cost what each request will cost in the KV memory and the tokens using the live state from your engine. And it says no before the request actually takes up the memory. So the short version is count is not a cost.
</details>

**Hershel Jan**: 如何构建你自己的策略？这里包含四个选择维度：
1. **裁决粒度（Unit）**：你接纳的对象到底是什么？是单个请求（single request）、整个智能体执行会话（agent session），还是一个租户（tenant）？
2. **观测信号（Signal）**：策略依据什么指标来做出准入裁决？这可以简单到内存压力（KV pressure），也可以是队列深度（queue depth），或者是截止时间松弛度（deadline slack，即评估请求是否还能满足 SLO）。无论选用什么指标，它必须在系统变忙时产生实质变动；
3. **裁决规则（Rule）**：信号如何转化为决策。从耗时仅数微秒的简单阈值对比，到耗时数秒的全局运筹优化器（optimizer）；
4. **执行动作（Action）**：一旦规则给出了裁决，你对请求采取什么动作，客户端将受到何种影响。这就是 Perv 刚才讲到的 Admit、Defer 和 Reject。每一个选择都会制约下一个选择，例如只有当请求本身携带截止时间时，截止时间松弛度信号才能发挥作用。

我们重点看前三个维度。

**选择一：按单个请求准入，还是按整个会话准入？**
假设有两个智能体任务，各包含 20 次模型调用，而系统当前的容量只够接纳约一半的调用量。如果按单个请求准入，两个任务各自有一半的请求被放行，但由于双方都卡在那些未被接纳的后半截调用上，导致两个任务都无法完成。系统耗尽了全部算力，产出却为零；如果按整个会话准入，会话 A 的全部调用均获放行并顺利完成，而会话 B 得到明确答复“稍后再试”。这生动地说明：智能体的 40 次调用构成的是一个有机整体的会话，智能体发送的是会话级工作流，然而绝大多数公开发表的论文策略却依然停留在单请求准入的维度。

**选择二：面对具体问题，该观测哪项指标？**
- 想要防止 Cache 显存溢出：必须监测 **KV cache 压力（KV pressure）**；
- 想要避免无效的重复计算：必须监测 **KV 使用率配合 Cache 命中率**（只要能被高频复用，满载的 cache 并无大碍）；
- 想要压低排队等待时长：必须监测 **队列深度（Queue depth）**；
- 想要满足延迟目标：必须监测 **截止时间松弛度（Deadline slack）**；
- 需要应对超长输出：必须引入对 **输出长度的预测**。

请特别留意“失效条件”（fails when）这一栏，它指出了各项信号在何种场景下会失灵。看第一行：当显存根本未被打满时，KV 压力信号就会彻底失效。请记住这一点，在第四部分它会展现致命的盲区。

**选择三：将信号转化为决策的四种机制（成本由低到高）：**
1. **静态阈值（Threshold）**：直接将单个数值与预设上限对比。例如 2026 年提出的 FluidWeight 策略，每次裁决仅耗时数十微秒；
2. **双重门禁（Dual gate）**：需要两个信号同时满足才触发动作。例如 Conqueror 论文，在 100 微秒内同时比对 KV 使用量与 Cache 命中率；
3. **全局优化器（Optimizer）**：将所有队列状态统一建模为一个大型规划问题进行求解。例如 QLM，考虑周全，但每次决策需耗费约 5 秒；
4. **形式化边界（Formal bound）**：针对最坏情况进行数学边界推导，计算该请求是否仍能赶上截止时间。例如 Chronos，利用首字延迟（TTFT）推导，开销在微秒级别。

现在对比一下成本与我们的场景：智能体在 2 秒内打出 40 次调用，耗时 5 秒的优化器在排队决策还没算完时，现场早就过时了。
<details><summary>Original English</summary>
**Hershel Jan**: How do you build your own policy? So there are four choices here. The first is the unit which tells you what you are actually admitting. Are you admitting a single request? Are you admitting an agent session or are you admitting a tenant? The two second is the signal which means what is that the policy is watching for taking an admission decision. This could be as simple as your memory pressure which is your KB pressure. It could be your Q depth. It could be your deadline slack. That means whether your request is able to meet your SLOs's or not.

And whatever it is, it has to actually move when the system gets busy. So three is the rule which means how does the signal gets turned into a decision. So rule is used for that and that can be anything from a simple threshold that takes microscond to a full optimizer that takes seconds.

Fourth is the action. Once you have the rule that gives you a decision what do you do with it? What does your how does your client gets impacted through those actions? That's the admit defer and the reject that per just talked about in the module two. Each choice limits the next one. For example, a deadline signal only works if your request actually carry the deadlines. So let's go through the first three.

Choice one. Do you admit a single request or do you admit a poll sessions? Say you have two agent task 20 calls each room for almost half of them. You can uh point you can see the top row. So if you admit per request about half of each task gets in but neither task can finish because each one is stuck waiting on the calls that didn't make it. You have used all the capacity and completed nothing. If you admit per session, session A gets all of its call and finishes. Session B gets one clear answer. Come back later. And this picture is illustrative, but the logic holds.

Our 40 calls are one session. Coding agents send sessions and yet most published policies admit only the single requests.

So which metric do you watch for what particular problem? This is the question that we are trying to answer. It depends on the problem that you are trying to prevent. If you are if you want to keep the cash from overflowing, you definitely have to watch your KV pressure.

If you want to avoid your wasted recomputee, you have to watch out the KV used together with the cash hit rate. A full cache is fine if it's being reused.

If you want to keep your weights to be shorter, you have to watch for your queue depth and you have to take actions based on that. If you want to meet your latency targets, you need to watch your deadline slack. Take actions based on that. If you need to plan for your long answers, you need to predict for the output length.

And look at the last column fails when it tells you when each signal stops working. Look at the first row. KV pressure fails when the cache never fills up.

Remember that row? It comes back to bite someone in the part four.

So what are the four ways to take that decision?

That is how do you convert your signal into a decision from the cheapest to the most expensive. Here are the ways a threshold just compares one number to the one limit. Example is a policy named clued weight that was uh created somewhere in 2026. It takes tens of microsconds per decision.

Second is a dual gate which needs two signals to agree before it acts. Example is a paper called concour uh which checks like KVUs and the cash hits under 100 microsconds.

Third is an optimizer which solves like one big planning problem across all the cues at once. Example is a QLM. It's thorough but it takes about 5 seconds per decision.

And the fourth is the formal bound uh which does the math on the worst case. Can this request still meets its deadline? The example is the Kronos on which uses the like time to first token and it uh provides you like a microcond level latency.

And now hold that cost column up against our agent. It sends 40 calls in 2 seconds. A 5-second decision shows up after every party is over.
</details>

**Hershel Jan**: 来看这四篇学术论文的具体做法：
- **FluidWeight**：单请求准入，对 KV 使用率设定阈值，报告了 10% 到 25% 的性能提升；
- **Conqueror**：面向会话级准入，采用双重门禁机制，报告了 4 倍于 SGLang 的吞吐提升，但该方案仅在离线环境下完成测试；
- **QLM**：单请求准入，跨批次全局规划，报告了 40% 到 90% 的收益，但每次决策开销高达 5 秒；
- **Chronos**：依据截止时间松弛度采用形式化边界准入，将超时率从 99% 降至零，成果斐然。

需要声明的是，每篇论文测试所用的模型、推理引擎和工作负载截然不同，切勿将此当作统一排行榜来看待。对于在座各位来说，真正核心的问题是：**这些现有方案中，有任何一个能完美契合编码智能体的工作负载吗？答案是否定的。**

我们将这些论文映射在两个坐标轴上：一个坐标轴是其优化目标（按截止时间还是按吞吐量），另一个坐标轴是其裁决粒度（单请求还是会话级）。编码智能体需要的是一种能够支持会话级准入、能够在线处理实时动态流量、且无需修改原生引擎源码的策略。目前没有任何现有论文成果能够完整覆盖这些诉求（Conqueror 虽无需修改引擎，但仅在离线环境验证过）。

因此在实际工程中，你需要挑选最接近的方案来自研策略。以下是选择策略形态的决策树：
1. **你的请求是否携带明确的截止时间？**
   - 如果是，针对截止时间设立形式化边界计算，此方案具备微秒级判定延迟；
2. **如果没有截止时间要求，那么在峰值负载下 KV cache 是否会被打满？**
   - 如果峰值时 KV cache 会被打满，你需要能够感知 Cache 前缀复用情况的机制，可选用双重门禁或 KV 阈值机制；
   - 如果峰值负载下 KV cache 并未被打满，你应当转向在队列深度（Queue depth）上设立阈值规则。

这自然引出了第四部分：当你拥有了一套策略后，该如何进行严谨的基准评测？接下来交还给 Perv。
<details><summary>Original English</summary>
**Hershel Jan**: So what the four papers did as the complete policy fluid weight admits single request uses the threshold on your KV use and reports 10 to 25% improvement. Conqueror is the one that admits your VO agents. It uses your dual gate and reports four to 4x uh the throughput of the SG lang but it was tested offline. Uh QLM admits the request plans across the W feed and reports 40 to 90% gains at about 5 seconds per decision. Kronos admits requests against their deadline slack with a formal bound and takes deadline misses from 99% down to zero. Definitely very amazing accomplishments.

So each purper used a different model engine and a workload. So please don't read this as a leaderboard.

The question that matters for this room is does any of them fit a coding agent and the answer is no. We placed every paper on the two axises. One axis is what it optimizes deadlines or the throughputs. Other is what it admits single request or the VO agent sessions. A coding agent needs a policy that admits bold sessions, works online with live traffic and runs engine you haven't fought and nothing sits there cleanly. Conc doesn't need a for but it was only tested offline.

So in practice you will pick the closest match and build just build your own. And here is how you can choose which polic like which kind of a policy you want to try it out.

So here is that decision tree.

First the question that you have to answer is does your request carry any deadlines? If yes, set up a some sort of a formal bound on that deadline. This will take some microsconds level of latency.

If there is no deadline requirement, the second question that you can ask is does the KV cache fill at the peak load? If your KV cache fills at the peak load, then you would want something like a way to detect the cache prefixes used. So you can use some sort of a dual gate mechanism or a KV threshold mechanism. Um and then if your KV cache gets filled at the peak load, it does not gets filled at the peak load, then you what you could do is you can set up a Q level of threshold on it.

And that gets us to the benchmarking like once you have a policy, how do you benchmark?

So I will be handing it over to pop.
</details>

---

### 基准评测方法学与开源工具 admit-perf

>> 谢谢。现在进入第四部分：基准评测（benchmarking）。正如刚才所见，现有公开的论文策略无法直接满足编码智能体的需求，你必须改造现有策略或自行构建新策略，接着你就必须拿出证据，证明它是否真正有效。

要对策略进行测试，你需要四项要素：
1. **集群基线（Cluster）**：首先在完全没有准入控制的前提下，测出集群自身的真实极限承载力。后续的所有负载水平均以该基线数值的倍数来表达；
2. **策略定义（Policy）**：明确策略读取哪些信号、采用何种阈值限制，以及在说“不”时执行什么动作；
3. **真实轨迹（Trace）**：记录真实生产流量并在测试中进行回放，使用包含智能体特征的流量，将负载从基线容量的 0.5 倍逐步爬升至 2 倍；
4. **评分机制（Score）**：将同一份轨迹在有准入策略与无准入策略下各跑一次，对比结果。

很多团队往往在评分机制上陷入误区。我们推荐的评分指标称为：**准入约束下的有效吞吐（Goodput under admission）**。其计算公式如下：
- **分子**：达到 SLO 延迟目标的请求总数（即回答按时启动，且生成过程中 token 之间从未发生过长停顿）；
- **分母**：抵达系统的所有请求总数，**包含被拒绝的请求**。

为什么分母必须包含被拒绝的请求？试想一下极端情况：拒绝掉 95% 的流量，只把剩下的 5% 伺候得极其完美。如果你只统计被接纳的请求，你的 SLO 达标率高达 100%，看起来令人惊叹，仿佛可以直接上线；然而在“准入约束下的有效吞吐”指标下，实际得分只有 5%。如果只计算保留下来的请求，丢载（shedding）看起来毫无代价，但事实并非如此。
<details><summary>Original English</summary>
>> Thank you. So now moving on to part four which is benchmarking. As we just saw no publish policy fit a coding agent cleanly. So you are going to adopt one or you you will have to build your own and then you have to prove if it's actually working or not. So to now moving on to the next slide you would have to test your policies right so for that you need four things first is your cluster your policy and trace and score. So let's dig deeper into each. So your cluster of the first measure it it is capacity with no admission control at all. The load your replica can sustain on their own. Every load level at after this is described as multiple of your number like multiple of that number and uh about the policy u which signals it reads what limit it uses and what it does when it says no. The third one is trace which is a record of real traffic that you replay using code coding agent traffic ramping from half your capacity up to twice your capacity.

Four is a score. Then they run the same trace twice. Once with the policy and once without and then you can compare your result. The score is where the most people go wrong. So let's look look at that. Now moving on to the next slide which is uh how how you score. The score we recommend is called goodput under admission. So you can see the formula on the screen. The top of the fraction is the request that met their SLO their latency target. That means the answer started on time and it never stalled for too long between tokens.

The bottom of the fraction is every request that arrived including the one which got rejected. Why does the bottom matter so much?

So try this. Uh refuse 95% of your traffic and serve the remaining 5% perfectly. If you only count what you admitted, your SLO attainment is 100%. Looks amazing, right? Just ship it. But no like good put under admission says 5%. Shedding looks three when you only account the request you kept. It isn't.
</details>

>> 第二个必须做对的事情是工作负载（workload）。基准测试只有在尽可能贴近真实流量特征时才有参考价值：
- 回放真实的智能体轨迹，保留其扇出调用（fan-out）、重试行为及会话上下文，而不是使用均匀随机到达的合成流量；
- 将负载强度定义为所测得的基础容量的倍数，在 0.5 倍到 2 倍容量之间进行扫描压测；
- 将延迟目标（guideline）设定为空载延迟的倍数；
- 切记：一个从不超出系统极限容量的基准测试，根本无法检验策略的有效性，因为策略从不需要说“不”。必须确保施压达到超载点。

每一份严谨的准入评测报告，都必须公开以下七项关键要素：
1. 以测得容量的倍数形式公开实际施加的负载；
2. 相对空载基线延迟设定的截止时间；
3. 信号有效性检测（Signal liveness，目前尚无论文主动披露过该指标）；
4. 运行重复次数及结果的方差波动（而非仅展示单次侥幸的最优数据）；
5. 各项参数的来源（是在当前环境下调优所得、借用自他处，还是沿用默认值）；
6. Goodput 的分母中是否明确计入了被拒绝的请求；
7. 完整的环境配置清单（模型、引擎、版本、硬件、工作负载、SLO 定义及对比基线）。

这并不是要求大家推翻评估体系，而是要求大家坦诚透明地记录自己的测试条件。我们在阅读学术论文以及评测自身策略时，都应将其作为检查清单。手工逐项记录这七点极为繁琐，因此我们打造了一款默认自动记录全部七项要素的开源工具：**admit-perf**。
<details><summary>Original English</summary>
>> So moving on to slide 42.

The second thing to get right is the workload. A benchmark only tell you something if it looks like your real traffic.

So replay agent traces with their fan out retries session not uniform random arrival.

Describe load as multiple of the capacity you measured and sweep from half of it to double it.

Set your guideline as multiple of your latency with no load. And remember a benchmark that never goes past capacity never actually tests the policy because the policy never has to say no. So you have to make sure that you reach at that point.

Now move moving on to the seven uh seven things every admission result should disclose.

Signal liess is one of the seven things every admission result should disclose. Here is the full full list that you can see on your screen.

The load as a multiple of measured capacity deadline sets relative to latency with no load.

Signal liveless which is no paper report.

How many times you repeated the run and how much the result varied not one lucky run. Where each parameters comes from, turned on this setup, borrowed from somewhere else or left at the default.

Whether the rejected request count in a good put denominator and the full configuration and the full configuration is model, engine, version, hardware, workload, SLOs's and baseline. None of this ask anyone to change how they evaluate. It just ask them to say what they did. Use it as a checklist when you read on on a paper and when your benchmark and when you benchmark your own policy. Doing all seven by hand is painful. So we built a tool that records all of this uh as as a default.
</details>

>> **admit-perf** 是集成在同一个代码库中的双模工具：
在生产环境中，它是一个置于 vLLM 或 SGLang 之前的中间件库，负责对每个请求做出 Admit、Defer 或 Reject 裁决，对应第二部分讲到的入口层；在基准测试中，它是一个可以在真实 GPU 上驱动真实引擎压测任意策略、并统计策略运行开销的测试框架。
两端调用完全相同的核心函数：`policy.decide()`。因此，你在基准测试中验证的策略代码，与你最终推向生产的代码完全一致。我们之所以开发它，是因为在查阅的 16 篇论文中，没有任意两篇采用相同的基准、引擎、工作负载或 SLO，而 admit-perf 让面对面的对齐基准评测成为可能。

使用 admit-perf 仅需五条核心指令：
1. `infra up`：在真实 GPU 上拉起原生的 vLLM 实例；
2. `infra smoke`：冒烟测试，确认服务正常运行；
3. `bench`：针对每项策略重复运行多次压测；
4. `bench compare`：对比各策略表现，明确胜出策略及其领先幅度；
5. `infra down`：彻底关停基础设施以停止计费（这是我最喜欢的命令）。

我们将资源置备与基准测试特意拆分为独立命令。因为加载模型需要数分钟，所有策略必须在完全相同的部署环境下面对检验。如果在切换策略时重新置备环境，就会引入环境变量干扰。部署环境保持恒定，策略才是唯一的变量。
<details><summary>Original English</summary>
>> So uh the tool is admin perf and it's it it's two things in one repository. So in production if you see it's a library you put in front of VLLM or SG lang it decides admit defer or reject for every request that's ingress layer from part two.

So if you also see we on the right side uh it's uh in in a benchmark it's a harness that runs any policy against a real engine on a real GPU and reports what the policy cost both sides calls the same function policy decide. So the policy you benchmark is exactly the policy you deploy.

We build it because across those 16 paper no two share the same baseline engine workload or SLO admitf makes a head-to-head comparison possible.

Now moving on to the next slide.

So using its pive command. So you can see on the screen we have five commands. So infra up starts a real VLM on a real GPU. Infra smoke checks that it's actually serving. Then we have bench runs every policy several times each. Then we have bench computer tell you which policy won and how by how much. And then we have infraown which which basically means it should shuts all all off so you stop paying. And that's my favorite one.

Uh and so now provisioning and benchmarking are separate commands on purpose. Loading a model takes minutes and every policy has to face exactly same deployment.

If you are reprovisioned between policy, you would change the very thing you are trying to hold a constant.

The deployment is constant. The policy is variable.
</details>

>> 此外，策略必须显式声明它所读取的信号，这是 admit-perf 破解前面提到的盲区陷阱的方式。
例如，某基于 KV cache 阈值的策略声明需要 `kv_used_fraction`（当前使用的 KV cache 比例）。如果引擎无法上报该信号，测试框架会在启动阶段直接报错中断。因为如果没有这一校验，缺失的信号往往会被静默读取为 0；而一个始终读到 0 的 KV 阈值策略会把所有请求全部放行，它就在不知不觉中退化成了毫无准入控制的默认基线，而表面上测试结果看起来却完全正常。因此，无法读取有效信号的策略必须明确报错（fail loudly），绝不能静默失败（fail silently）。

系统中的每一次决策都会连同其观测到的上下文状态被完整记录。每次运行都会生成一个包含四个核心 JSON 文件的可审查目录：`manifest.json`、`summary.json`、`decision.json` 和 `outcome.json`，运行后可以深入排查。

现在来看实测结果：**丢弃 37% 的超载流量，换取长尾延迟的大幅削减**。
以下是在真实 GPU 上的实测数据：测试环境选用 A10 GPU 运行 Qwen 2.5 0.5B 小模型，引擎并发限制为 4 个序列，施加每秒 14 个请求、总量 8 次调用的压力，重复测试两次。
- 在没有任何准入控制的第一组对照中，P95 首字延迟（TTFT）约为 2.5 秒（即 95% 的请求快于该耗时），且存在约 700 毫秒的上下波动；
- 在排队上限设为最多允许 2 个请求等待的队列策略下，放行了 63% 的请求，P95 延迟暴跌至约 1 秒——性能提升了 2.5 倍，同时有效吞吐（goodput）完全持平。

最发人深省的是接下来这个结果：**观测信号的选择，比具体的阈值数值更加致命**。
在完全相同的测试运行中，KV cache 的占用峰值仅有 0.5%，而排队深度却高达 24 个请求。因为在小型模型上，相对于 4 个短序列而言，显存空间极其充裕，KV cache 根本没有被填满的可能，所有的瓶颈压力全部积压在队列之中。在此场景下，如果使用基于 KV cache 压力的准入策略，它看到的监控曲线将是一条水平死线，从而将全部请求照单全收。这就是刚才提到的第二类失效场景。

大家今天就可以直接上手体验 admit-perf，无需拥有昂贵 GPU。代码库内置了一个轻量级的仿真引擎（fake engine），它完整实现了生产所需的三个接口，在承受负载时能够模拟真实运行负载。你可以直接在笔记本电脑上完成整个流程的测试。如果你将自研策略打包成独立模块，admit-perf 会自动发现并加载，无需改动工具库本身。欢迎大家踊跃贡献新的策略实现、工作负载模型、引擎适配器或指标定义。
<details><summary>Original English</summary>
>> So now uh here a policy must declare the signal it reads. This is how admit perf deals with the trap I just showed you. Every policy has to declare the signal it needs. This KV cache threshold policy says I require KV used correction which is the share of the KV cache in use. If the engine cannot report that signal, the run stops at the startup with an error. You can actually read without the check a missing signal reads as a zero and KV cache threshold that always sees zero admits everything. It's quietly turned into the no admit baseline while your results looks completely normal. So policy that cannot see its signal should fail loudly and not just fail silently.

Um so here what we did is every decision is recorded with the state it saw. Every run leaves behind a folder you can open inspect. There would be four files as you can see on the screen. Those are manifest JSON summary JSON decision JSON and uh out outcome JSON. So what each does is uh you can take a look deeply once you run the results. Now we we will be looking at the shading cut. So shade shading 37% cut tail latency. So here are the four results how they will look like on a real GPU. The setup small model we used quen 2.5 uh and it's a half billion model on a A10 GPU. The engine was kept out at four sequ sequences at a time. Eight request at 14 per second two repeats.

If you look at the first row with no admission control, the P95 time to first token was about two two and two and a half around 2 and a half seconds and P 45 sorry P95 means 95% of the requests were faster than that and it swung by about 700 milliseconds either way. Now the last row if you see with a queue up policy that allows at most two request waiting 60 63% of requests were admitted and the P95 dropped to about around 1 second that's 2.5 times better with the exact the good same put now if we look at the signal matter more than the threshold but this This is the result I love most. Same run. KV cache usage peaked at half a percent. The queue got 24 requests deep on a small model. KV cache is huge compared to the four short sequences. So it never comes close to filling. All of the pressure showed up in the queue. Instead, a KV cache pressure policy would have botched a flat line and admitted everything. that that's the row of choice from two. So

now here and you you can try it today. You don't need a GPU. There is a small fake engine that speaks the three endpoints admit puff uses and it gets busy under load just like a real one. So you can test the whole setup on your laptop. If your right policy is your own package, admit perf discovers it automatically. No change to the repo and contribute contributions are very welcome. New policies, workload, engine adapter or matrices.
</details>

---

### 总结收尾

**Hershel Jan**: 好的。如果今天整场演讲你只想记住一张幻灯片，请务必记住这一句：当你在推理集群中接纳请求时，必须建立一套前置的“拒绝”机制。它应当置于入口层，在向请求承诺“好的”之前、在请求打入 GPU 之前、在请求侵占你宝贵的显存之前，果断做出裁决。

正如 Perv 刚才强调的，准入策略会返回对应的错误码，客户端也必须能够正确处理这些请求状态与错误。

最后，进入总结环节。非常感谢大家的耐心与宝贵时间。这里附上了我们的两个开源项目。这一切始于我们在编写《大规模 LLM 推理》手册时的思考，在调研行业现状时发现了这些空白，进而打造了 admit-perf。上面附有源码链接，欢迎大家亲自体验、提交 issue、贡献代码。核心目标在于帮助大家构建准入策略、完成科学基准评测，并确保推理集群长治久安。谢谢大家。
<details><summary>Original English</summary>
**Hershel Jan**: Okay.

So if you want to remember like one slide just make it this one that when you are accepting the request in your inference clusters you need to have a mechanism to say no early something that works at the ingress something before saying yes to the request before that request goes into the GPU before that request takes up your memory.

and per added clearly. There are a couple of error codes that your admission policies return. You need to handle those requests and those errors.

And with that we would like to come to the closure. We would like to thank you all for your patience, for your time. And here are like two of our projects. It all started as part of the LLM inference at scale handbook. We and when we were doing the survey, we found the gaps and we prepared admit puff. So here is the source code for it. Feel free to go to it and like experiment with it. Raise the issues, contribute to it. idea is to build your admission policies, benchmark them and be confident that it uh helps you keep your cluster stable. Yeah.
</details>

>> 谢谢大家。
<details><summary>Original English</summary>
>> Thank you everyone.
</details>

>> 谢谢大家。
<details><summary>Original English</summary>
>> Thank you everyone.
</details>