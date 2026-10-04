---
layout: post.njk
source: https://yage.ai/share/codex-subagent-transparency-20260715.html
speaker: yage.ai
title: |-
  Codex 仍然开源，但父 agent 给子 agent
  说了什么，现在看不见了
date: '2026-07-15'
summary: OpenAI 在 Codex 开源仓库中合并了一项改动，导致主 agent 发送给子 agent 的任务指令不再以明文形式保存在本地会话记录中，而是被加密为密文。这使得用户在排错时，无法直接看到具体任务的上下文，仅能看到密文。这种变化反映了模型内部状态（如 reasoning 和 compaction）与外部交互信息之间的透明度边界正在向更深层、更受保护的方向移动。
area: tech-engineering
category: ai-application
tags:
  - multiagent-v2
  - task-encryption
  - agent-workflow
  - model-transparency
people: []
companies_orgs:
  - OpenAI
products_models:
  - Codex
media_books: []
draft: true
status: evergreen
---

2026 年 6 月 5 日，OpenAI 在 Codex
的开源仓库里合并了一项改动。改动落地后，你再回头看 Codex
留在本地的会话记录，会少掉一段关键内容。前后对比很直观。

更新前，主 agent 给 sub-agent
派任务时，本地记录里能看到具体指令：

```
<code class="sourceCode json"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a><span class="fu">{</span><span class="dt">"message"</span><span class="fu">:</span><span class="st">"Review the authentication changes and report regressions."</span><span class="fu">}</span></span></code>
```

更新后，同一句指令在本地只剩下密文：

```
<code class="sourceCode json"><span id="cb2-1"><a href="#cb2-1" aria-hidden="true" tabindex="-1"></a><span class="fu">{</span><span class="dt">"message"</span><span class="fu">:</span><span class="st">"<ciphertext>"</span><span class="fu">}</span></span></code>
```

sub-agent
仍然会在云端拿到明文任务并执行。少掉的是你回头查看这句话的能力：主 agent
当时究竟让它做了什么，本地记录不再告诉你。

麻烦出在排错的时候。Codex
会在你的电脑上读写文件、运行终端命令，也会把执行记录保存在本地。如果
sub-agent 后来做错了，你首先要分清：是主 agent 派错了任务，还是
sub-agent 自己理解错了？GitHub issue
#28058 里，开发者追问的就是这个问题。

Codex 从来不是完全透明的。不过，主 agent 发给 sub-agent
的这句任务过去至少还能看到，现在也看不到了。本地的 CLI、SDK 和 App
Server 依然开源，具体范围可以看官方说明；只是开源客户端已经不足以还原这段完整的任务链。

## 以前能看见什么，现在看不见了

遇到复杂的编程任务，主 agent 往往会把工作拆开，再开几个 sub-agent
分头处理。比如，一个负责修改接口定义，另一个负责补单元测试，最后由主
agent 汇总结果。

过去，这些任务消息会以明文留在本地会话里。GitHub issue
#25458
里就有一份早期记录，其中的任务参数可以直接阅读。排错时，开发者至少能看到每个
sub-agent 收到了哪一句任务。

6 月 5 日合并的加密 PR #26210
改了 MultiAgentV2
传递这类消息的方式。spawn_agent、send_message
和 followup_task
里的任务文本，不再以明文交给本地客户端，而是变成了 Responses API
生成的密文。

加密只碰了这些任务消息，并没有把 sub-agent
的整个运行过程藏起来。你仍然能看到它调用了什么工具、跑了哪些命令、产生了什么输出、改了哪些代码，以及最后返回了什么结果。PR
也明确保留了 MultiAgentV1，没有改动旧通道。

## 加密发生在 OpenAI
的服务端边界

这串密文从哪里来？主 agent 通过 Responses API 分发任务时，API
会先在云端加密任务文本，再把密文发给本地的 Codex。

Codex 收到后不会把它解开，只会先保存下来。等到启动 sub-agent
时，客户端再把同一段密文原样发回 Responses
API。云端在那里解密，然后把明文任务交给
sub-agent。现在的开源客户端没有恢复明文的路径，所以你翻本地记录时，只能看到那段密文。

还有一处代码改动把这件事说得更明白。开发者专门提交了 “Clear
encrypted agent task
previews”，清掉了加密任务的预览。换句话说，本地看不到明文不是界面漏显示了，而是代码就不再显示它。

MultiAgentV2 加密前后：以前 Codex
本地记录能看到任务明文；现在本地只保存密文，OpenAI Responses
在子模型侧解密

OpenAI 没有在 PR
里解释为什么要这样做。外界有几种猜测：可能是为了保护任务拆分和编排用的提示词，可能是不想公开类似
chain of thought 的分解过程，也可能与消息完整性或云端多 agent
服务的统一有关。这些都只是猜测。现在能确定的是，本地排错少了一条原本可读的线索。

## Codex 以前也不是全透明

这并不是 Codex 第一次把一部分状态留在云端。模型给出可见答案前会产生
reasoning，这部分内容返回本地时已经是密文。你能看到最后的回答，却不能从日志里读出它中间具体想了什么。OpenAI
在 2025 年 5 月 11 日发布的推理手册里说明了这种做法。

长对话还有另一块看不见的状态。会话快要碰到上下文限制时，云端会把前面的内容压缩成一个
encrypted_content 密文块。Codex
不知道里面具体保留了什么，只负责在下一次请求时原样传回去。OpenAI 在拆解
Codex agent loop 的技术文章里把这套机制称为
compaction。

所以，“云端读得懂，本地只负责转发”并不是这次才出现的。区别在于，此前看不见的主要是
reasoning
和压缩后的会话状态；普通用户消息、工具参数、终端命令、执行结果，以及
agent 之间派发的任务，大多仍能在本地记录里找到。

## 这次跨过了一条不同的边界

reasoning、compaction
和这次的任务加密，技术路径看起来很像：云端生成一段状态，本地拿到密文，再把它传回云端。但它们藏起来的东西并不一样。

reasoning 记录的是模型自己怎样走向一个答案。主 agent 发给 sub-agent
的任务，则是在告诉另一个 agent
接下来要做什么。前者留在单个模型的内部，后者会让另一个执行者开始行动。

这一区别到了排错时就很实际。假设 sub-agent
删除了不该删的文件，或者运行了一条错误命令。你需要知道，它是不是照着一条错误任务做的，还是拿到正确任务后自己做错了。

现在你仍然看得到 sub-agent
何时被创建，也看得到它后来运行了哪些命令、改了哪些文件。偏偏中间那句“你去做什么”只剩下一串密文。这样一来，人和本地审计工具都少了一块关键证据，也没法在命令执行前检查这次委派本身是否合理。

## 透明度边界正在往外移动

把这几次变化放在一起看，方向就很清楚了。Codex 原本就不展示
reasoning，也不展示 compaction 压缩后的内容；MultiAgentV2
又把不透明的范围扩到了 agent 之间的任务消息。

这不等于 Codex 的开源部分失去了价值。CLI、SDK 和 App Server
仍然公开，本地的工具调用、命令、输出和代码改动也仍然可查。但开源客户端能告诉你的，越来越不等于整个
agent 系统实际经历的全部过程。

真正需要追问的是：一段隐藏内容只是在帮助模型自己思考，还是已经在指挥另一个
agent 行动？当 sub-agent
越来越多、任务链越来越长，这两类信息不能再用同一条“内部状态”边界简单带过。我们还能审计到哪一步，会越来越取决于服务商愿意让本地看到什么。