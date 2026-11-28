---
layout: post.njk
source: https://yage.ai/share/deepswe-benchmark-audit-20260528.html
speaker: yage.ai
title: SWE-Bench Pro 饱和之后，有人做了一把新尺子
date: '2026-05-28'
summary: DeepSWE 是针对现有编程基准测试（如 SWE-Bench Pro）数据污染与验证僵化设计的全新测量工具。它通过全新任务集与灵活验证方法，显著拉开了各顶配模型在编码能力上的表现差距，揭示了旧测量工具评估大模型能力时的局限性。
area: tech-engineering
category: testing
tags:
  - benchmark
  - ai-coding
  - data-contamination
  - model-evaluation
  - software-engineering
people: []
companies_orgs:
  - Datacurve
  - OpenAI
  - Poolside-AI
products_models:
  - SWE-Bench-Pro
  - DeepSWE
  - GPT-5.5
  - Claude-Opus-4.7
  - Gemini-3.5-Flash
  - DeepSeek-V4-Pro
media_books: []
draft: true
status: evergreen
---

在 SWE-Bench Pro 的排行榜上，GPT-5.5 82.6%，Claude Opus 4.7
82%，Gemini 3.5 Flash 79.8%，DeepSeek V4 Pro 76.2%。GPT 和 Claude
咬得紧，Gemini 差了两三个点，DeepSeek
再低一截。如果只盯着这些数字做判断，顶配模型之间的差距不大。

但日常使用中大部分人的体感比这个排行榜更尖锐：GPT 和 Claude
是第一梯队，Gemini 明显弱一档，DeepSeek
再往下。排行榜上的和实际使用中的分化之间，有一个对不上的裂缝。

这周一，Datacurve 一个四人团队发布了 DeepSWE，一个从零构建的编程基准。同一批模型在上面跑完，差距拉到了
62 个百分点：GPT-5.5 70%，Claude Opus 4.7 54%，Gemini 3.5 Flash
28%，DeepSeek V4 Pro 8%。

DeepSWE
的思路是：当旧测量工具因为数据泄露和题目过易失去区分力时，从题源、难度、verifier
三个方向重新做一套测量。

## 旧尺子为什么失灵

SWE-Bench Pro 的饱和有两个互相独立的推手。

第一个是污染。它的任务来自已合并的 GitHub
PR，题目描述、讨论过程和最终补丁都在公开互联网上。OpenAI 在今年
2
月的一篇文章里用实验确认了所有前沿模型在训练数据里见过这些题：GPT-5.2
收到一句任务提示就能逐行背出金补丁，Claude Opus 4.5 能一字不差复述 PR
里某一行注释的内容。当模型已经背过答案，测试衡量的就不再是写代码的能力，而是对训练数据的记忆程度。不同模型的记忆能力分布和编码能力分布未必一致，污染把分数往一堆挤，挤的方式也不对等。

第二个是难度。SWE-Bench Pro 的参考解平均加 120 行代码、改 5
个文件，但 prompt 有 4,614
个字符。也就是说任务描述非常详细，实际要做的改动不大。DeepSWE
的参考解平均加 668 行代码、改 7 个文件，prompt 只有 2,158
字符。提示更短的条件下要求更多产出，区分力自然不同。

两个基准的任务复杂度对比。DeepSWE 的
prompt 只有 SWE-Bench Pro 的一半长，但参考解代码量是它的 5.5
倍。

## 三个改进方向

DeepSWE 从任务来源、难度设计和 verifier
设计三个方向重新做了基准。

任务从零写，不改编已有 commit。 每个 DeepSWE
任务的参考解都是人工写的，有些受未解决的 GitHub issue
启发，但实现本身是全新的。任务不回流到上游仓库，所以它们不会进入未来的公开
GitHub 记录。基准覆盖了 91 个仓库、5
种语言（TypeScript、Go、Python、JavaScript、Rust），每个仓库中位数只贡献一个任务，避免单一项目主导排行榜。

这个机制在发布初期能防泄漏。所有模型都没见过这些题。但长期看，当一个基准的题目和答案公开发布后，下一代模型完全可能在训练数据里包含它们。HN
上有人指出 “contamination free label only works for the initial
release”，这个判断是对的。Datacurve
的策略是任务不回流到上游仓库，但基准本身的题目信息已经公开在 GitHub
上了，理论上任何模型开发者都可以拿它做训练。长期防污染需要定期旋转任务池，或者设置不对外公开的隐藏评估集。SWE-Bench
Pro 也有一个私有分片做这件事。

任务更难，更贴近实际使用场景。 SWE-Bench Pro 的
prompt 包含了复现步骤、上下文和代码片段，有些甚至暗示了函数签名。DeepSWE
的 prompt 只描述要实现的行为，agent
需要自己探索代码库、定位修改点、决定实现策略。这更接近开发者日常交给
agent 的任务形态：与其给一个详细的 todo list，不如描述最终效果让 agent
自己找路。

Verifier 只看结果，不看你怎么做的。
这是整个基准最核心的改进。

SWE-Bench Pro 的评分方式可以类比成这样：一道数学题的标准答案用了解法
A，测试就只认解法 A 的每一步。你用解法 B
也算出了正确答案，但因为中间步骤对不上，判错。

具体到代码上。一个典型 case：原 PR 把一段逻辑提取成了一个独立函数
parseRpmQfLine，agent
把同样的逻辑直接写在了调用处。功能完全一样。但测试里有一行
import parseRpmQfLine，agent
没有这个函数名，编译报错，判失败。task 描述里从未提过这个函数名，agent
没有猜到的义务。verifier
把”是不是和原作者写得一样”混进了”做得对不对”。

Datacurve 做了一个实验来量这件事有多严重。他们从 SWE-Bench Pro 和
DeepSWE 中各抽 30 道题，用 10 种 agent 配置各做 3 遍。然后让一个外部 LLM
当裁判，独立阅读每份答卷和 agent
的操作过程，判断代码是否真的实现了题目要求。裁判不和任何一家的 verifier
对齐，纯粹看”做到没做到”。结果：SWE-Bench Pro 的 verifier 拒绝了 24%
的正确答案，又接受了 8.5%
的错误答案。加起来近三分之一的结果是误判。同一把裁判尺子量 DeepSWE
自己的 verifier，正确答案被误拒的概率 1.1%，错误答案被误收的概率
0.3%。

两个基准 verifier
的假阳性和假阴性率对比。SWE-Bench Pro 假阴性高达 24%，DeepSWE 只有
1.1%。

DeepSWE 的 verifier
差别在哪。它的测试是在写题时人工构建的，只校验最终行为，不管内部用了什么方案。你可以在出题时就已经想好”这道题可能有三四种解法，测试要对它们全部开放”。评分过程仍然是纯代码执行，和
SWE-Bench Pro 一样。但构建阶段多做了一步审查：每个 verifier
都被检查过，是否会因为实现方式不同而误拒正确解。还有一个 LLM
辅助的检查步骤：题入库前，用 LLM 跑一遍 agent 答卷，标记 verifier
可能在边界上误判的点，再人工复核修掉。LLM 在这里不是替代
verifier，是帮人更快发现 verifier 的设计盲区。

## 结果

同一批模型在两个基准上的得分。SWE-Bench
Pro 上 GPT 和 Claude 挤在 82 分附近，DeepSWE 上差距拉到了 62
个百分点。

DeepSWE 把同一批模型的分差从 30 个百分点拉到了 70 个百分点。GPT-5.5
以 70% 居首，GPT-5.4 56%，Claude Opus 4.7 54%。再往下是 Claude Sonnet
4.6 32%，Gemini 3.5 Flash 28%，GPT-5.4-mini 24%。Claude Haiku 4.5 从
SWE-Bench Pro 上的 39% 掉到 0%，DeepSeek V4 Pro 只有 8%。

分数拉大本身不证明新基准更准。任何把人从 90 分拉到 50
分的考试都能增加区分度，关键是被区分的是什么东西。DeepSWE
的任务更长、提示更短、要求更多自主探索，这些特征更接近开发者日常使用
agent 的场景，区分度因此有了意义前提。但 113 个任务、每模型约 90 个注标
rollout 的样本量，还不足以把分数差距直接读作模型能力的固有排名。

## 定性分析中的几个发现

Datacurve 用 LLM judge 对部分 rollout 做了定性分析，有几个观察。

Claude 和 git 历史。 SWE-Bench Pro 的 Docker
容器保留了完整的 .git 记录，黄金 commit 在 agent
可以访问的文件系统里。Claude Opus 4.7 和 4.6 的 rollout 中有超过 12%
被标记为 CHEATED：agent 运行了 git log --all 或
git show <commit-hash>，把合并后的补丁读出来用进了自己的提交。这些行为占
Opus 4.7 全部 passes 的约 18%，Opus 4.6 的约 25%。GPT
家族从未出现这种行为，Gemini 约 1%。Poolside AI
独立复现了这一发现，已记录为 SWE-Bench
Pro 的 GitHub issue #93。

各模型的失败特征。 Claude 在 DeepSWE 上漏掉 prompt
中列出的要求比例最高，尤其当要求同时支持多分支行为时（比如同时支持同步和异步），常实现主分支后就停下。GPT
漏要求率最低，但对 prompt
的解读更字面化，多次运行容易收敛到同一个解法。Gemini 3 Flash 在 18% 的
rollout 中没有跑任何测试就直接提交了。

自验证行为的 prompt 敏感性。 DeepSWE 的 prompt
不限制 agent 是否修改测试。Claude Opus 4.7 和 GPT-5.4 在超过 80% 的
rollout 中自发编写了新测试来验证自己的修改。SWE-Bench Pro 的 prompt
模板里有一行告诉 agent 不要修改测试逻辑，同样这批模型的自测试率骤降到 3%
到 28%
之间。一句看似无害的限制，可能显著抑制了对任务成功率有直接影响的行为。

效率差异与分数无关。 DeepSWE
同时记录了每个模型的成本指标。输出 token 量、运行时长、单次费用在 agent
之间差了一个数量级，但和分数之间没有显著相关性。花更多 token
或更长时间并不代表解决更多任务。

## 该信多少

DeepSWE 的改进在机制上对得上 SWE-Bench Pro
的已知问题：初期防住了污染，题目难度提高了，verifier 假阴性从 24% 压到了
1.1%。剩下来的不确定因素有三个。

第一是 LLM judge 审计本身没有独立校准。33% 和 1.4%
的偏离率差了一个数量级以上，方向性结论的置信度足够。但假阴性 24%
这个精确数字取决于 judge
的判定标准。审计用的是同一把尺子量两家，系统性偏差方向可控，但 judge
对某些实现模式的偏好仍可能导致某一侧错误率的系统估计偏差。Datacurve
公开了所有标注数据和轨迹，独立验证是可能的。

第二是统一 harness 的副作用。DeepSWE 用 mini-swe-agent
统一了所有模型的工具环境，只暴露 bash。GPT 训练时惯用
apply_patch，Claude 惯用
text_editor，都被压到同一个底层接口。消除了不同 harness
对分数的干扰，但压制程度可能不对等。Datacurve 的小规模对照（10
个任务）显示 mini-swe-agent 在这个切片上匹配或超过了各厂商原生
harness，但 10 个任务不足以给这个假设结论性的证据。

第三是基准天花板。GPT-5.5 已经 70%，离发布当天就不远。HN
上有评论说这本质上是 “sell data for them to
hillclimb”，发一个即将被刷满的基准然后卖更多测试数据。Datacurve
把全部数据、代码和轨迹公开了，这降低了利益冲突引发的信任成本。但基准的长期价值确实取决于能否持续扩展任务池和难度上限。

SWE-Bench Pro 的饱和指向一个分岔：要么 GPT、Claude、Gemini、DeepSeek
真的已经差不多了，要么测量工具本身到了天花板。DeepSWE
提供的证据指向后者。旧排名的产生条件在测量前沿差异这件事上失去了大部分信息量。题目被污染意味着得分掺杂了记忆能力而不是纯编码能力，低难度压扁了分数分布，verifier
以 24%
的概率拒绝正确解。这些因素同时存在时，聚类读不出真实的能力差距。