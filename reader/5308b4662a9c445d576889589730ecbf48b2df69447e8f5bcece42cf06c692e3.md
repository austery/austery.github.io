---
layout: post.njk
source: https://yage.ai/share/ds4-deepseek-v4-flash-mac-20260522.html
speaker: yage.ai
title: |-
  如何在 Mac 上本地运行 DeepSeek V4 Flash：DS4
  引擎深度解读
date: '2026-05-22'
summary: 文章介绍了通过 DwarfStar 4 (ds4) 引擎在 Mac 上本地高效运行 DeepSeek V4 Flash 的方案。该引擎通过垂直架构优化、KV cache 磁盘持久化和精准的工具调用原话回放，解决了大模型在消费级硬件上的部署难题，并兼容主流 coding agent 工作流。
area: tech-engineering
category: ai-application
tags:
  - deepseek-v4-flash
  - local-llm
  - kv-cache
  - inference-engine
  - activation-steering
people:
  - antirez
companies_orgs:
  - deepseek
products_models:
  - deepseek-v4-flash
  - dwarfstar-4
media_books: []
draft: true
status: evergreen
---

DeepSeek V4 Flash 是目前开源模型里最接近 frontier 水平的一个。284B
总参数，13B 激活（MoE），100 万 token 上下文窗口。在 thinking mode
下，它的推理链条比同级别的模型短得多——经常只有五分之一——而且长度和问题复杂度成比例，不会在小问题上想半天。它在
GPQA Diamond 和 AIME 2025 上的表现已经逼近 GPT-5
系列，中英文写作也都拿得出手。如果你有一台 96GB 以上内存的
Mac，这很可能是你现在能跑的最好的模型。

然后问题就来了：macOS 上目前没有一个主流通用推理引擎能跑它。llama.cpp
主线不支持——V4 Flash 的 FP4+FP8 混合精度权重、hash MoE
routing、compressed sparse attention 这些新架构和传统 GGUF runner
的兼容距离太大，issue 开了，社区在尝试，但当前连 converter
都没有。Ollama 底层是 llama.cpp，同样跑不了，只支持 cloud proxy。vLLM 和
SGLang 有完整支持但仅限 CUDA，在 Mac 上没有意义。

就在这个空档里，antirez 发布了一个专门为 DeepSeek V4 Flash
写的引擎：DwarfStar 4（ds4）。纯 C 写成，Metal 优先，一个
make 编译出五个 binary。它不是 llama.cpp 的 fork，也不依赖
GGML——从 tokenizer 到 HTTP server 到 coding
agent，全部从零实现，只服务这一个模型。antirez 在 README
里公开说明这个项目是在 GPT-5.5 的强辅助下完成的——“humans leading the
ideas, testing, and debugging”——代码里也看得出来 AI
参与的痕迹：干净、结构化、边界情况处理得很细致。

## 怎么用：一条命令启动
server，接上你已经在用的 agent

ds4 的用法从 ds4-server 开始。编译后启动：

```
<code class="sourceCode bash"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a><span class="ex">./ds4-server</span> <span class="at">--ctx</span> 100000 <span class="at">--kv-disk-dir</span> /tmp/ds4-kv <span class="at">--kv-disk-space-mb</span> 8192</span></code>
```

它同时支持 OpenAI、Anthropic、Codex 三种 API
协议。也就是说，你已经在用的 coding agent
可以直接接上来——不需要换工具，不需要学新东西。

Claude Code：设好 ANTHROPIC_BASE_URL=http://127.0.0.1:8000，ANTHROPIC_MODEL=deepseek-v4-flash，Claude Code 就把它当成本地 Claude 来用。

Codex CLI：走 Responses API，完整支持 streaming 和 function-call 事件。

opencode / Pi：走标准 OpenAI chat completions。

这里有一个容易被漏掉但代价很高的问题：工具调用的翻译损耗。DeepSeek V4
Flash 调用工具时用的是它自己的 DSML 格式（类似 XML 的标签语言），但
Claude Code、Codex 这些 agent 只懂 JSON。当 agent 把模型的 DSML
工具调用转成 JSON
下次再发回来时，即使只是格式上的细微差异，也可能让模型认不出自己上一轮说了什么——于是它需要从头重新理解整段对话。

这里要理解一个前提：模型处理多轮对话时，不会每次都从头计算全部历史。它会缓存之前算好的注意力状态（KV
cache），新 token
只需要和缓存交互。这个缓存完全由之前输出的精确文本决定——文本对不上，缓存失效，就得重新处理整段历史。

打个比方：你用中文写了一封邮件，对方用英文回了，你把英文翻译回中文再发回去——翻译前后的措辞不可能一模一样。模型也一样，它发现回来的文本和自己当时说出去的对不上，就只能重新读一遍全部上下文。在
100K token 的对话里，这个重新计算可能要几十秒。

ds4 的做法是记住模型的原话。每次模型生成一个工具调用，ds4
给它一个唯一 ID 并保存原始文本。下次 agent 带着这个 ID 回来时，ds4
直接把当时的原话塞回去——模型看到的是自己一字不差的输出，直接接着往下想。只有在这个
ID 丢了的情况下（比如 server 重启且没开 KV cache 持久化），ds4
才启用后备方案，把 JSON 重新翻译成 DSML。

还有另一个优化：生成工具调用的结构部分（标签、参数名、JSON
标点）时，ds4
强制用确定性采样——因为这部分必须精确，不能容忍任何偏差。但参数内容（文件内容、编辑文本）仍然用正常采样——因为长文本上强制确定性会导致重复。

除了 server mode，ds4 还有一个 alpha 阶段的 native
agent（ds4-agent）。它的思路更进一步：彻底取消 server
这个中间层，推理和 agent 在同一个进程里运行。因为没有 HTTP
边界，它的响应是即时的（prefill 时有实时进度条），用
/switch 在不同 coding session 之间切换也是即时的——恢复一个
session 就是加载一个文件。它内置了 9
个工具（bash、read、write、edit、search 等），所有工具都针对 V4 Flash 的
DSML 格式垂直适配。当前仍然是 alpha
质量，但它探索的是一个有意思的方向。

## 为什么 284B
参数能在笔记本上跑

这里要引入一个所有大模型推理都绕不开的概念：KV cache。

大模型生成文本时，每输出一个 token，都要关注之前所有的
token。如果每次都从头算一遍，100 万 token 的上下文会让每个 token
的生成时间变成天文数字。所以所有推理引擎都会把之前算好的”注意力状态”缓存下来——这个缓存就是
KV cache。新的 token
只需要处理自己和缓存里已有状态的交互，不需要把整个历史重跑一遍。

KV cache 的大小直接决定了能在多大上下文里跑模型。标准 transformer 的
KV cache 和 token 数量成正比：100 万 token 的上下文需要大约 180GB
来存——这还没算模型本身。这就是为什么 1M context
的模型，大多数人的硬件根本跑不起来。

DeepSeek V4 Flash 把这个问题从架构层面重新定义了。它用的 Multi-head
Latent Attention（MLA）不是存每一个 token
的完整注意力状态，而是在对话进行中持续做分层压缩：前几层保留最近的 128
个 token
完整状态（处理眼前发生的事），后面的层按不同压缩比做长程摘要——有些层存四分之一，有些层存一百二十八分之一。这个设计的动机来自
agent 场景的特殊需求：agent
需要在十几轮工具调用中反复回看旧日志和工具返回结果，不是做一次性的长文档问答。我在之前的文章中详细分析过
V4 Flash 的三层注意力架构（HCA 全局粗看、CSA 索引细查、sliding window
近处全看），这里不再展开。结果是从 2048 token 到 65536 token，KV cache
从 52MB 增长到 926MB，每 1000 token 增加约 14MB。外推到 100 万 token 约
13.4GB——比标准 transformer 压缩了 13 倍。

ds4 在 MLA 压缩的基础上做了三件事，把 KV cache
从一个临时的运行时结构升级成了可持久化、可跨 session 复用的系统。

第一，磁盘持久化。大多数推理引擎把 KV cache 当 GPU
显存里的临时数据——session 结束，记忆清空。ds4 把它写成文件。cache key
是对话文本前缀的 SHA1，文件包含三部分：文本前缀、token IDs、完整的 graph
state。下次你重启
server、继续同一段对话时，模型直接从磁盘加载这个文件，不需要从头处理那
25K token 的 Claude Code system prompt。文件用普通 I/O 读写而不是
mmap（模型本身已经 mmap 了 80GB+，再给每个 cache 文件加 mmap
会耗尽虚拟内存空间）。checkpoint 在四个时刻自动保存：prompt 结束后、每约
10K token、被新 session 替换前、server
退出时。保存时还做了两个细节处理：裁掉末尾 32 个 token、对齐到 2048
token 边界——这是避免下次恢复时 tokenizer 在边界上把同一个词拆成不同
token 导致匹配失败。

第二，工具调用的上下文保持。这一层把 KV cache 和前面 server
部分讲到的 exact replay 串了起来。模型的工具调用原话映射也会写入 KV
cache 文件。server 重启后加载 cache
时，同时恢复对话记忆和原话映射——模型继续对话时看到的是自己一字不差的上一轮输出，不需要
canonicalization 来近似还原。

第三，session 切换。对于 ds4-agent，/switch 切换 session
就是加载一个 .kv 文件——恢复就是恢复，没有 prefill。这是 KV
cache 成为”磁盘一等公民”之后自然获得的能力：如果内存里的 KV
状态随时可以存盘和恢复，session 就不再是一个独占资源。

在这些设计之下，benchmark 数据显示：M4 Max（q2 量化）上 prefill 344
t/s 到 205 t/s（从 2K 到 65K context），generation 稳定在 23-27 t/s。M3
Ultra 512GB 上 prefill 84-468 t/s，generation 27-37 t/s。antirez 在
Hacker News 上说他的 M3 Max 满速生成时峰值功耗只有 50W。

## 额外能力：调一个参数就能改变模型的说话风格

ds4 支持 activation
steering——不重新训练模型，只在推理时修改它的内部激活值，就能改变行为倾向。操作上就是一个参数：--dir-steering-ffn -1
让回答更简洁，--dir-steering-ffn 2 让回答更啰嗦。

我在之前的文章《一行代码越狱任何开源模型：Abliteration
技术、情绪向量与 AI
安全的同源困境》中详细讨论过这个技术背后的原理。概括起来：模型的内部是一个高维空间，某些有意义的概念（拒绝回答、啰嗦程度、正式程度）各自对应空间里的一个方向。找到了这个方向，推一下，行为就变了——就像音响上的均衡器，fader
推左少一点人声，推右多一点人声，但底下的音乐本身没变。

ds4 的 steering 是运行时生效、不修改模型权重。这和社区里更出名的
abliteration（直接改权重文件）有一个关键区别：因为不动权重，模型的确定性不变——前面说的工具调用原话回放机制能正常工作。同时你可以在不同
session 用不同强度，甚至同一个 session 里切换。

方向向量的生成完全在本地完成：一个 Python 脚本调用本地 ds4，对两组
prompt
分别跑推理，抓取每层的内部激活值，做差、归一化，得到一个方向文件。项目里带了一个例子，100
对 prompt 构建简洁 vs 啰嗦的方向。同一个问题 “Explain why databases use
indexes.”，-1 输出 67 词，默认 136 词，2 输出
171 词的分段展开。

这个方法可以用于其他维度：调低编程倾向（让你的客服 chatbot
少答技术问题）、调高正式程度、实验特定行为。但它有边界——粗粒度的风格和倾向调控效果稳定，精确的事实性或复杂推理能力不受影响。

## 小结

ds4 的思路是窄下注：一个模型，一个引擎，端到端打磨。从定制量化到
Metal compute graph 到 KV cache
的磁盘持久化到精确的工具调用上下文保持——每一层都只为一个模型服务。

一个月前 V4 Flash 发布了，两个多星期前 ds4
发布了。它们合在一起，让一台 96GB 内存的 MacBook 能跑一个接近 frontier
质量的模型，而且能用 Claude Code、Codex、opencode 这些你已经在用的 agent
去调用它——不需要换工作流，不需要学新工具。

项目仍然是 beta 质量，ds4-agent 是
alpha。但它底下的方向是清楚的：让一个模型在你的硬件上从头到尾可用，不只是能跑
token。