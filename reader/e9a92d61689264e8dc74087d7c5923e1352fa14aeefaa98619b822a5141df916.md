---
author: AI Engineer
date: '2026-07-08'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=HsxQICTLF84
speaker: AI Engineer
tags:
  - agent-client-protocol
  - ai-coding-agent
  - json-rpc
  - file-system-proxy
  - bootstrapping
title: 实战演练：在 15 分钟内构建 ACP 兼容的 AI 编程智能体
summary: 本文基于 Zed 团队 Bennett Fenner 的 Live Coding 演练，深入解析了 Agent Client Protocol (ACP) 的核心理念与架构设计。文章详细拆解了如何使用 ACP SDK 改造无状态智能体，实现实时 Token 流式传输、工具状态同步、虚拟文件系统代理，并展示了智能体如何通过 ACP 读写自身源码，动态新增终端工具以实现“自我进化”。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Zed
  - Anthropic
products_models:
  - Opus
media_books: []
status: evergreen
---
### ACP 协议的诞生背景与核心定位

随着 AI 编程智能体（AI coding agents）和终端用户界面（如 Claude Code, Codex, Gemini CLI 等）的爆发，**Zed** 团队（一个用 Rust 编写的高性能 AI 代码编辑器）开始思考如何让用户将自己选择的智能体无缝带入编辑器中，并享受统一的高质量交互体验。为了打破编辑器与不同智能体之间的生态壁垒，他们推出了**代理客户端协议**（Agent Client Protocol: 允许 AI 智能体与代码编辑器无缝对接的标准接口，简称 ACP）。ACP 类似于 LSP（Language Server Protocol）或 MCP（Model Context Protocol），是一个基于 **JSON-RPC**（JSON Remote Procedure Call: 基于 JSON 格式的轻量级远程过程调用协议）的开放协议。它为 AI 智能体与客户端（如编辑器、IDE 等）搭建了标准化的通信桥梁。目前，ACP 已获得 Open Code、Cursor 等 CLI 智能体，以及 JetBrains、Obsidian、Zed 等多个主流客户端的生态支持。

<details>
<summary>Original English Source</summary>

I'm Bennett. I work at Zed and we built like an AI code editor all written in Rust. And last year was kind of as you probably all know the rise of the uh AI coding agent terminal user interfaces with every major model provider like building Claude code, Codex, Gemini CLI, and so on. And so at Zed, we asked ourselves like how can we let users bring their agent of choice to our tool and enjoy like a nice interface that is unified across all of them. And so that's why we decided we need some kind of type of protocol uh called agent client protocol, uh which is similar to like MCP or uh LSP. It's a JSON RPC based protocol. And the idea is basically that uh agents and clients can talk to each other through through a unified interface. And uh yeah, the it's yeah, online. It's open source. Uh you can contribute if you want. Um at this point we have a wide variety of agents already supporting this either by like an adapter that kind of like translates um the agent's native language to the ACP one. Uh and then we have like for example open code and co- uh and cursor uh having like ACP mode built into their like CLI agents. And we also have a bunch of uh clients at this point up to 40 that uh implement this including open claw for example. Like open claw itself is a client and a server actually like a client and an agent. Um and JetBrains and Obsidian and other people are supporting this. Um Great. So, um I'm going to do a live coding session. Let's see how well that goes. Um So,

</details>

### 极简 AI 智能体的架构基础与局限

在进行 ACP 兼容性改造之前，一个基础的 AI 编程智能体需要具备最核心的交互环路。对于底层的模型 API 来说，其本身是**无状态的**（Stateless: 每次请求独立，不保留历史上下文的特性）。因此，客户端在每次调用像 **Anthropic** 这样的模型接口时，都必须完整附加当前对话的历史记录。智能体的核心循环主要由两个基础工具驱动：**读取文件**（Read File: 获取指定路径文件的内容）和**编辑文件**（Edit File: 定位并替换文件中的目标文本块）。在运行过程中，智能体调用模型接口，接收到模型输出或工具调用请求。若是工具请求，则在本地执行对应的读写操作，收集反馈结果并再次发送给模型。然而，这种传统的直接调用方式极度依赖本地文件系统，且无法直接向编辑器的 UI 界面同步实时的状态和执行细节。

<details>
<summary>Original English Source</summary>

Right. Uh basically, we have some pre-existing code. So, this is Zed. Uh here I have some TypeScript code. Also, bear with me. I'm I'm a Rust developer. I have basically zero clue about TypeScript. So, if you see anything that you don't do in TypeScript, tell me afterwards. Um but yeah, like here's a very minimal coding agent that just doesn't support ACP, but it's kind of the bare minimum you need to like build a coding agent. So, all it has is really like two tools. One to read a file and one to edit an existing file. Um Yeah, this is like pretty basic. It provides the model has to provide a path. Then it has to provide an old text that is like then just replaced with new text and that's kind of everything. And then we have uh in this case like I'm using Anthropic. Uh there's a way to prompt the agent um uh with yeah, the user can prompt the agent, which is the function that we will going to call here. And then we enter the agent loop and that is kind of like the way all agents basically work is the model APIs are stateless. So, you just attach some like conversation up to this point. You call the endpoint. In this case it's like the Anthropic API. And then we um yeah, we get like a message from the model and either it can be like a end turn. That means like the model decided to uh yeah, just output some text and do nothing or it can call a tool. And in this case it would be like a read or a write uh tool call. And then in the case of a tool call, we like run the for example the edit file tool call locally, um collect the result, and then send it up to the model again. That's where this this loop um And then we call the API again with the conversation up to that point and that's kind of everything. And then we have like these this like handle tool call function here, which yeah, handles like read and write uh tool calls, which does what you expect. We get the path. We read it from the file system and we return some some uh result.

</details>

### 实现 ACP 协议的四大核心接口

要让一个非 ACP 智能体转变为 ACP 兼容智能体，必须通过 SDK 实现 ACP 规范中定义的四个核心生命周期函数：**初始化**（Initialize）、**会话管理**（Sessions）、**提示词处理**（Prompt）以及**任务取消**（Cancellation）。`Initialize` 用于向客户端宣告智能体所支持的协议版本和能力范围。`Sessions` 对应客户端（如 Zed 里的每个讨论线程）发起的每一个会话，智能体通过生成唯一的随机会话 ID 并绑定工作目录来隔离上下文。`Prompt` 接口则处理客户端发来的消息块数组，调度底层的智能体环路，并将非文本（如图像）等当前版本不支持的媒体类型进行过滤。通过在客户端配置中指向 `node agent.js` 启动命令，智能体即可与 Zed 编辑器建立 ACP 通信，并在编辑器的 debug 视角中清晰观测到 JSON-RPC 消息交互。

<details>
<summary>Original English Source</summary>

Right. So, now the question is how do we make this thing ACP compatible? And hopefully we can do it in 10 minutes. So, let's see. Um so, yeah, I have some boilerplate here. Uh in this case I'm using the TypeScript SDK as I said. Um and the way this works, you implement uh the agent interface provided by this uh library. And then you have to at minimum implement these three uh four functions. So, the first one that we're looking at is kind of this initialize here. Um all we really have to do here is like respond with the protocol version we support, which in this case is just the latest. There's also like some capabilities like client and uh the agent can itself advertise capabilities of stuff it supports, but we're building a very minimal coding agent, so we don't support anything outside that's necessary, I guess. Um then for us like authentication is irrelevant since it's just using my API key from an env var. And then there's this concept of sessions in ACP. So, basically every time you start a thread in Zed or in a different editor or client, uh you you call a new session. And in a session you can prompt and then yeah, from there on you can like get get your output. So, all we really do here is like we generate a random ID. Um then we um instantiate uh this coding agent with the current working directory, which we get from the client. Um we store it in our internal map and then just return the ID to the client so that the client knows um yeah, knows the ID and that is kind of then used inside prompt. Um because what prompt does in this case, um it like prompt the prompt request, if we go to the definition here, all this is kind of doing is uh it provides a prompt, which is an array of content blocks that can be like text, images, whatever, the session ID for reference. And so all we kind of have to do here is yeah, we look it up in our internal state. We get the relevant agent uh for that uh current session. And then I have a help helper function here, which just in this case ignores everything that's not a text because we don't support images and stuff like this. Um and then we call this like prompt function I showed earlier, which then uh runs tool calling loop. And so then just like as a nice to have uh feature, we also support cancellation. Uh that's also pretty pretty simple. So, these are kind of like the four minimal things we have to implement. And I have this hooked up in Zed just by there's no special code. All I have is kind of like I tell Zed there's some ACP compatible agent and you can run it with node and then my path to that agent.js file. Um so, when I uh let's do that in here as well. So, when I run, I'm going to build. Um I'm going to build, right? And then I'm going to restart uh yeah, launch a new ACP demo agent. And you can see if I ask it for something, you can see wait indicator. And now it's done. So, nothing.

</details>

### 实时 Token 流式传输的机制实现

在基础的 ACP 通信跑通后，智能体虽然能通过 Anthropic API 获取响应，但如果不进行流式更新的对接，编辑器界面就无法呈现平滑的输入反馈。ACP 协议通过**会话更新**（Session Update: 智能体向客户端发送的异步非阻塞通知）机制来解决这个问题。会话更新不同于传统的“请求-响应”模式，它可以由智能体在任意时间节点主动推送到客户端。我们通过在 Anthropic SDK 的文本流事件中监听模型输出，每次收到一个新的文本分块（Chunk），就向 ACP 连接中发送一个类型为 `agent-message-chunk` 的会话更新，并携带当前会话的随机 ID。通过这种方式，Zed 编辑器能够实时流式渲染模型返回的每一部分字符，极大地提升了用户交互的即时感知。在实际测试中，**Opus** 模型所流式输出的文本成功顺畅地在编辑器窗口中展出。

<details>
<summary>Original English Source</summary>

Which is what we expect, right? Because like what we can see here, if I go over Oops. Um If I go over here, we have some kind of like ACP debug view in Zed. So, to make it easier for us to develop. And you can see like Zed sends a session new request. We respond with a session ID and as soon as I type in something, we get prompt. And now we got a stop reason, right? So, these red arrows come from the uh from the from the adapter that we are building from the agent. But it's not outputting tokens, right? Like behind the scenes it's obviously like Anthropic is giving us tokens, but how do we make them show up in Zed? So, that's the next thing that we uh yeah, want to focus on. So, the first thing that we kind of need to do, like our coding agent itself uh needs to have a way to um send something over to the connection. So, what we're going to do here is like the coding agent is going to take the ACP connection and then also the session ID. And then inside here, we have to provide this uh connection and the ID. And then if we go Okay, I'm just going to close this. Right. If we go back here, now inside of uh prompt, Anthropic like this is the Anthropic SDK. So, in this case like in Oops. You can just use um this like stream on uh Yeah, that's like a Anthropic SDK. Like you can react to a text event. So, every time we basically get a chunk, uh we send this kind of what ACP calls a session update. As I said, a session is like a single thread or a conversation. And then you can send updates kind of like notifications to the client that are not like a usual request response, right? It can happen at any time and the client reacts to it. And so here we are associating with the session update with a session ID. And then this like There's a type of session updates. There are multiple. We will see more in a second. But this agent message chunk is just like, "Okay. Hey, here's some new output from the model." And so if we build again, uh we go back to Zed. I'm going to have to restart the agent. I go here and I say, "Hello." Hello. Hello. Well, here's Opus talking, right? You can see like we're streaming in these individual uh chunks, right? Right, that we got from Anthropic. So, so far so good.

</details>

### 工具状态同步与虚拟文件系统代理

智能体在执行读写等工具调用时，传统的静默执行会导致编辑器 UI 无法感知当前步骤。在 ACP 协议下，智能体需要在工具启动时向客户端发送一个状态为“进行中”（In Progress）的 `tool-call` 类型的会话更新，展示相应的图标和标题；并在执行完成后发送 `tool-call-update` 提交最终的执行状态和内容。此外，ACP 引入了强大的**文件系统代理**（File System Proxy: 允许智能体通过客户端读取未保存缓存的机制）能力。相较于直接使用 Node.js 的 `fs.readFile` 读取磁盘物理文件，通过 ACP 连接的 `readTextFile` 接口可以读取编辑器内存中尚未保存到磁盘的临时修改（Unsaved Changes），确保 AI 智能体始终基于开发者眼前的最新代码视态进行推理与编辑。

<details>
<summary>Original English Source</summary>

Let's hope the demo gods uh stay with us. Um Right. So, that's one piece. The next thing though is like I want to like it's a coding agent, right? It's supposed to edit code. So, I can actually tell it already because we have tool support, right? I can tell it to read, for example, this like helpers .ts file and it's going to give me if the Wi-Fi isn't too slow, it's giving me a description of what this file actually contains. Like if you look here, that's basically the description of the file, but again, you don't see it in the UI, right? So, now we need to emit more session updates, similar to like what we did for text. So, if we actually go towards the read file, kind of what we need to do here is like the way it works usually in ACP, like you emit an initial tool call update, uh which I'm going to paste in here. So, yeah, again we're emitting a session update in this in this case, it's uh type of tool call. And then there are multiple properties we can specify, for example, like the title, kind of some kind of data um that Z uses, for example, for like yeah, using some icons and stuff like this. And then we indicate that the status is in progress, and you can also like associate tool calls with like actual uh locations. And so, now we signaling over ACP that something is in progress, right? This tool call. But then we also want to at the end, like once the tool call has finished, like at the bottom here, we kind of want to send another update. And in this case it's not tool call itself, but it's a tool call update. So, you have to emit on the agent, you have to emit like a tool call, like session update of type tool call, and then once once the client knows about it, uh you can emit updates for that. Uh and this is the way that we set the status, and we can also return the content. Um and then one additional thing that I'm going to do here is the um instead of like if you can see here, we're calling, I guess it's a bit hard to see, but like here we're calling fs.readFile, right? So, we're just using the native file system APIs. But MC uh ACP actually proxies the file system too. Like the client can provide a uh a file system capability, and if it does, um we can like proxy those uh file system tool calls over ACP. And it kind of makes sense, for example, for an editor, right? You want to um if I have unsafe changes in my buffer, they're not actually on the file system, but the agent should still see them. So, that's why we call this like uh read text file um over ACP. And so, now if we go back here

</details>

### 智能体自我进化：动态终端工具的引导与实现

当 AI 智能体具备了通过 ACP 代理读写本地代码的能力后，它甚至能实现**自我引导**（Bootstrapping: 智能体读取自身源码并编写新功能以升级自身的过程）。在 live coding 演示中，通过给智能体提供 ACP 终端控制的 API 格式信息，并下达向自身添加终端工具的指令，智能体成功读取了自身的 TypeScript 源码，自动生成了终端管理工具代码，并直接写回自己的源文件中。编译重启后，基于客户端提供的终端管理能力，智能体成功在底层沙箱中拉起了一个运行 `sleep 5 && ls` 任务的终端并实时渲染其输出。这套 ACP 架构目前完全基于**标准输入输出**（Standard I/O: 智能体与编辑器之间进程级的数据通信管道）运行，而 JetBrains 团队正致力于实现更具拓展性的远程传输协议（Remote Transport），为 ACP 的跨平台和远程协作生态铺平道路。

<details>
<summary>Original English Source</summary>

and hit npm run build, and then go back here, restart, and say read uh this file. Oops, not the rust. Then we should be seeing um Yeah, so now we see read tool calls, right? Okay, something is going wrong because everything is duplicated. Um yeah, but like here you can see the output um of the actual file. And because I think I'm low on time, um we're we're going to basically going to do the same for edit file. Um and I'm going to compile again. And if I again restart, and say add a comment at the top of agent source agent.typescript, then you're going to see um uh hello world is good. Hopefully, clo- uh Opus is going to decide to add hello world at the top of the file, and we actually get a diff here because the over ACP we send like a diff of the file. Okay. Yeah, I think there's something going wrong with the connection. I'm yeah, yeah, no time to debug right now. Sorry. Uh am I out of time or do I still have Okay, maybe like we can see. So, now that Okay, just another minute. Um now that the coding agent supports reading and writing files, we can actually Oh, great. Uh okay, then I don't need to rush. Um now we can kind of bootstrap the agent itself, right? Like the coding agent supports reading and writing files. I can just ask it, I prepared a prompt here, to add a terminal tool to itself, right? Let's see how this works out with like the duplication we're seeing. Uh but basically I'm telling it some something about the ACP um APIs, and there's some there's some APIs in ACP which also, that's another like capability of the client, where the client can um advertise that it supports creating terminal and managing terminals for the agent. Like the agent can also do it itself, of course. Um but it's a nice way uh for us to add some more interactivity. And so, the agent here decided to add a new tool description. Now it yeah, I'm live coding basically this terminal tool. Um and let's see if it actually builds. It does. Well, that's good. Um and then again, I'm going to going to restart the agent. I'm going to run our demo agent, and I'm going to ask it to run sleep five ls. Let's see. There you go. You can see a terminal running, sleeping 5 seconds. There is the output. And there's Yeah, and that's it, basically. Thank you. Yeah, so that's how you kind of build an ACP compatible coding agent in 15 minutes or so. Um yeah, if you want to uh check it out, just go to agentclientprotocol.com. Um in case anyone wants the demo code, but please don't use it in production. It's all agent generated. Um it's not upload it yet, but it it's an empty repository. I'm going to upload it in a second. Uh yeah, thank you for listening. Happy to answer questions. That's it. YEAH. UH THE DIFFS UH YEAH, WE HAVE LIKE IN in ACP there are multiple content types, and one content type is diff, and so the agent sends old text, new text, and then Z does the diffing for you. Yeah. Yeah. Cool. Do I need to go or can I Okay, one more question. Yes. Yeah, the connection works over standard IO. Uh there are some folks well, I think from the JetBrains people are working on like remote uh transport, uh which we're going to have soon, I think. So, yeah. But right now it works over standard IO. Yeah.

</details>