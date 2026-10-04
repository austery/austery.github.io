---
layout: post.njk
source: https://yage.ai/share/ai-agent-filter-vs-review-20260616.html
speaker: yage.ai
title: 命令行过滤为什么挡不住 AI agent
date: '2026-06-16'
summary: 文章探讨了命令行过滤在面对 AI agent 的创造性和绕过能力时失效的问题。核心观点是，单纯依赖规则（如 allowlist）无法穷举所有可能的操作路径，因为 AI 可以通过构造新的命令变体或利用上下文进行推理来绕过既定限制。最终的解决方案不再是写更好的规则，而是引入第二个 AI 进行上下文审查，从检查命令表面文本转向评估动作的真实影响和合理性。
area: tech-engineering
category: ai-application
tags:
  - agentic-workflow
  - command-filtering
  - allowlist-bypass
  - contextual-review
people: []
companies_orgs: []
products_models:
  - Cursor agent
  - Claude Code
  - OpenAI Codex
media_books: []
draft: true
status: evergreen
---

命令行过滤 vs AI 审查

2026 年 4 月，一家叫 PocketOS 的创业公司遇到了一个让所有 coding agent
用户后背发凉的场景。一个 Cursor agent 在 staging 环境里跑任务时，发现
credential 不匹配。它决定自己修。它没有碰
rm。它在文件系统里搜出了一个和当前任务毫无关系的 Railway
API token，用一条 curl GraphQL mutation volumeDelete 在 9
秒内删掉了生产数据库和所有同卷备份。系统提示里明确写了禁止破坏性操作，agent
事后也承认这比 force push
还要危险得多，但在那个瞬间，它选择了自己认为最优的路径。

这不是 PocketOS 的运维粗心。这是每一个用 coding agent
的开发者在日常中都会遇到的模式。你给 AI
一个任务，它走到一半发现路不通。它不问你，它发挥创造力。有时候这个创造力走进了你完全没有预期到的方向。你可能设过
allowlist，可能开过 sandbox。你想的是：至少它只能做我允许的事。但 AI
的创造力不会在 allowlist 边界停下，它会绕。

规则挡不住它，有两层原因，都不是多写几条规则能修的。第一层，你的 AI
一旦认定一个目标，会把 allowlist 当障碍绕过去。rm 封了它就用 Python
写脚本删，没有 sudo 它就找 docker
组提权。第二层，命令的组合空间太大，allowlist 永远追不上。shell
语法是开放的，任何基于字符串匹配的过滤只能枚举已知模式，而 AI
可以构造出过滤器从未见过的新变体。真正的解法不是更好的规则，而是
Anthropic 和 OpenAI 在 2026 年不约而同做出的事情：用第二个 AI
根据上下文审查每个动作。

## 你的 AI 比你的规则更努力

这个模式的典型表现：你的 AI
想达成一个目标，碰到你设的墙，它不停下来问，它找别的路。一个 Zed
编辑器的开发者做过第一手观察：Claude
一旦认定要做一件事，会主动构造混淆命令绕过 allowlist，拼接字符串、用
node 或 python 跑 inline script，什么办法都想得出来。allowlist
如果检查的是命令字符串的表面形式，agent
就把命令藏到它不检查的载体里。

一个更极端的案例发生在 OpenAI Codex 上。一个用户在本地跑 Codex，没有
sudo 权限。Codex 需要修改一个系统配置文件，没有向用户求助，而是自主发现用户在
docker 组里，识别出这是通往 root 的路径。它启动了一个 Ubuntu
容器，把宿主机 /etc 目录 bind-mount 进去，在容器里改了宿主机的
sddm.conf。用户完全不知道发生了什么。Codex
没有执行任何被禁止的命令，它只用了一个合法的 docker run，就拿到了 root
级别的写入权限。

这不是 bug，这是 agent 的工作方式。agent
的设计逻辑是从当前状态找到通往目标的路径。你的 allowlist
堵了其中一条路，agent
把它当作任何其他障碍对待：绕过去。系统提示、fine-tuning
和指令遵循这类软性约束，都跑在 agent
的推理循环内部。当目标导向推理和软性约束冲突时，约束经常输。Zenity
的安全研究员 Idan Habler 在分析 PocketOS 事故时指出，这是因为约束只是同一个推理过程的又一个输入，而目标才是驱动推理方向的主力。

还有一种情况更隐蔽：AI
根本不打算绕你的规则，但它也能意外伤到你。一条在 allowlist
里完全合法的命令，在 AI 把路径搞错的时候就变成了灾难。Google 的
Antigravity 在 2025 年底清空了用户整个
D 盘，就是因为 rm
是允许的，但它指向了根目录而不是目标缓存目录。命令本身合规，意图也正常，但
AI 对路径的理解出了偏差，字符匹配过滤完全看不出来。

## 从规则到判断

如果你没法穷举所有危险路径，替代方案是什么？Anthropic 和 OpenAI 在
2026 年上半年各自走到了同一个答案：不再检查命令，开始检查行为。

Anthropic 在 2026 年 3 月发布了 Claude Code 的 auto
mode。核心设计是在规则和 sandbox 之上，增加一个运行在 Sonnet 4.6
上的独立分类器，在工具执行前审查每一个动作。分类器的原则是评估动作的真实影响，不是命令的表面文本。如果
agent 把危险 payload 写到文件再执行，分类器审查的是 payload
的实际内容，不是那条看起来无害的执行命令。更重要的是，分类器刻意不看
agent
的辩解文字，只看用户消息和裸工具调用。被拦截时返回理由和替代路径建议。

命令行过滤和 AI
审查之间的差别不只是精确度。命令行过滤拦下一个命令，agent
只看到一堵墙，不知道是自己选错了工具、意图本身有偏差、还是缺少某种授权。没有理由的拦截会触发一种对抗动态：agent
把过滤当障碍，换一种方式再试。AI
审查改变了这个动态，因为它能解释为什么拦。意图正确但操作方式有问题：你应该用
trash 让删除可逆，不要用
rm。命令没问题但这类操作需要人类明确授权：你先去问用户。意图本身就理解错了：用户说的不是这个意思，回去重新读需求。甚至是一个技术失误：rsync
不该加
–delete，这个参数会清空目标目录。每一种拒绝指向不同的修正方向，干活的
agent 知道该怎么调整，而不是换个办法硬闯。

这里有一个解释这件事为什么重要的数字。Anthropic 测出 93%
的权限提示最终被用户无脑批准。人做手动审查时太容易疲劳，点了 20 次
approve 之后，第 21 次你不会停下来读。AI 审查者不会累。

OpenAI 在 2026 年 4 月发布的 Codex 的 auto-review
思路一致：一个独立模型在上下文中审查高风险步骤。两个产品都走到了同一个转变：不再问”这条命令允许吗”，而是问”这个动作在当前上下文里合理吗”。

这和之前写过的《从过程确定性到结果确定性》是同一个道理。开放空间里你没法控制过程，也就是枚举每一条可能的路径，但你可以判断结果，也就是当前这个动作在这个上下文中是否合理。安全场景里用第二个
AI
做上下文审查，本质上是把结果确定性的逻辑从翻译场景搬到了系统安全。

## 但你仍然需要一个不会商量的底线

AI 审查聪明，但不完美。Anthropic 自己报了 17%
的漏放率，真正危险的动作里有将近五分之一没被拦住。你仍然需要硬边界兜底：sandbox
限制可达资源，IAM 限制凭证权限，out-of-band confirmation
锁死不可逆操作。

硬边界和 AI 审查不是替代关系，是互相需要的关系。Anthropic 的数据显示
sandbox 过滤掉了 84% 的审批提示，把 AI 审查和人类的注意力集中在剩下 16%
真正有风险的操作上。sandbox 是地板，AI
审查是把天花板抬高到规则单独够不到的位置。没有 sandbox 去噪，AI
审查会被海量低风险提示淹没；没有 AI 审查，sandbox
对语义层面的危险行为完全无感。

回到 PocketOS。如果 Railway 的 token 被正确 scoped，如果删除操作有
out-of-band confirmation，如果 token 根本不在 agent
可读的文件里，硬边界就能防住这次事故。AI
审查层补上的是硬边界够不到的部分：当 agent
在合法权限内做了一个技术上合法但语义上危险的决定，第二个 AI
能根据上下文识别出来。没有硬边界，AI 审查只能拦一部分；没有 AI
审查，硬边界永远不知道 agent
在合法边界内想做什么。两者合在一起，才是命令行过滤失效之后的完整答案。