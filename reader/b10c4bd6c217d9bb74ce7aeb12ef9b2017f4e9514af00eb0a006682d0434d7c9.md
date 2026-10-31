---
layout: post.njk
source: https://yage.ai/share/tpu-vs-cuda-attack-defense-20260425.html
speaker: yage.ai
title: TPU 与 CUDA 的攻防战：Cloud Next 2026 之后的判断
date: '2026-04-25'
summary: Google Cloud Next 2026 发布了 TPU v8、TorchTPU 及对 Anthropic 的巨额投资，旨在挑战 NVIDIA 的 CUDA 生态。文章分析了 Google 在芯片、软件、系统和供应链上的策略，指出 vLLM 是非 NVIDIA 推理层的关键杠杆。尽管 NVIDIA 短期内仍具优势，但 TPU 在推理市场的价格影响力将受削弱。 Anthropic 是非 NVIDIA 阵营的核心推动者，其商业成功对承诺兑现有重要影响。对于开发者，建议关注推理层抽象和长上下文功能，并重新思考成本模型。
area: tech-engineering
category: tech-trends
tags:
  - tpu
  - cuda
  - ai-silicon
  - ai-ecosystem
  - inference
people:
  - Jensen Huang
  - Dwarkesh Patel
  - Amin Vahdat
  - Jonathan Ross
companies_orgs:
  - Google
  - NVIDIA
  - Anthropic
  - Broadcom
  - TSMC
  - Meta
  - Amazon
  - Microsoft
  - SemiAnalysis
products_models:
  - TPU v8
  - TPU v8 Sunfish
  - TPU v8 Zebrafish
  - TPU v7
  - TPU v6e
  - TPU v4i
  - CUDA
  - PyTorch
  - TorchTPU
  - vLLM
  - NVIDIA Vera Rubin
  - NVIDIA A5X
  - Llama 3.1-70B
  - Claude API
media_books: []
draft: true
status: evergreen
---

## Google Cloud Next
官宣的三件事

Google Cloud Next 2026 期间（4 月 22 日到 24 日），Google
官宣了三件互相关联的事。

芯片：TPU
第八代第一次拆成两颗独立产品。8t 代号 Sunfish，由 Broadcom
物理设计，做训练；8i 代号 Zebrafish，由 MediaTek
物理设计，做推理。两颗都瞄准 TSMC 2nm，2027 年下半年量产。8i 真正的
capacity 提升在 HBM：从 192GB 提到 288GB，带宽
8.6 TB/s 反而高于 8t 的 6.5 TB/s，full KV cache 仍然装在 HBM
里。on-chip SRAM 同时三倍扩容到 384MB（8t
是 128MB），但 384MB 装不下整段 long-context KV cache（Llama 3.1-70B
128K context 即使 INT4 量化也要约 10GB），它的作用是放 attention
计算正在处理的 active working set，减少 HBM 与 compute
之间的反复搬运。Cloud
blog 说 hosting massive KV Caches entirely on silicon
这句话是市场措辞，technical
deep dive 页面实际写的是 host a larger KV Cache entirely on silicon,
significantly reducing the idle time of the cores during long-context
decoding，是更准确的表述。Boardfly 拓扑专为 reasoning
模型的高并发推理设计（Hyperframe
Research 的架构解读 比官方表述更克制）。

软件：TorchTPU
在 4 月 24 日官宣，让 PyTorch 工作负载直接在 TPU 上跑，不再走
PyTorch/XLA 那一套累积了多年技术债的桥接层。底层 OpenXLA / StableHLO /
PJRT / libtpu 完全沿用，新的主要是前端翻译层和「避免 SPMD 限制 + 减
recompilation + 预编译 kernel 库」这套 roadmap。Google 第一次把 PyTorch
on TPU 当一等公民来配人配资源。Reuters
12 月就报道 Meta 在和 Google 密切协作。

需求：4 月 24 日宣布的 Google
对 Anthropic 投资协议。结构是即刻投入 $10B、可追加至 $40B、估值锁在
$350B、配 5GW TPU 算力。这是在 4
月 6 日 Broadcom 宣布的 3.5GW 之上的新增量。Anthropic 同时与 Amazon
签了 $100B / 10 年 / 5GW 协议，与微软+NVIDIA 签了 $30B
Azure compute / 1GW Vera Rubin。

下面三个问题决定了这三件事的真实分量。

## 一、目标是否靠谱：能不能成为另一套
NVIDIA

Google 这一波动作的真实野心，不是补齐 TPU 短板，而是重建一套和 CUDA
平行的算力栈。这个目标是否靠谱，要看 NVIDIA 这套护城河的本质是什么，以及
TPU 是否在每一层都有可行答案。

NVIDIA 这套护城河有四层：CUDA 软件 +
开发者习惯、PyTorch/vLLM/TensorRT 的事实标准框架、rack-scale
系统集成（NVL72/NVL576）、上游 supply chain（TSMC 先进节点 + CoWoS +
HBM3E 的多年锁定）。过去十年市场把它简称为「CUDA moat」，但 Jensen
自己已经悄悄换了说法。Cloud Next 之前一周他在 Dwarkesh Patel 的
podcast 上、4 月 GTC keynote 上反复强调的是 supply chain moat 和
rack-scale system，而不是 CUDA。这是一个很值得记的语调切换。NVIDIA
自己已经把单点护城河叙事让位给一组复合护城河，等于公开承认 CUDA
这一层不再是充分条件。

TPU 在每一层都有了答案，但每一层的答案都还有具体的不确定性。

软件层 TorchTPU 是一等公民支持，技术方向对，但没有任何公开的
head-to-head benchmark。Google 自己只用 perf/$ 和 cost-per-token
说话，从不放 raw throughput 对照。第三方能引到的最佳数据是 Trelis Research 2025 年
5 月在 Gemma 3 27B 上的对照：8x TPU v6e vs 1x H200，TTFT
略快，throughput 略输，cost per million tokens NVIDIA 反而便宜 4-5
倍。Amin Vahdat 自己宣称下一代 vLLM TPU backend 比 prototype 快
2-5x，意味着差距压缩到 1-2x 量级，但仍未独立验证。报告写「TPU 性能不输
GPU」这一句话时必须加 claim 而非 verified 的标注。

系统层 Google 有 Boardfly + ICI + Collectives Acceleration
Engine，rack-scale 一直是 Google 的强项。SemiAnalysis
在 InferenceX v2 里 直接说，目前只有 Trainium、TPU、NVIDIA
三家有真正 rack-scale 系统部署，AMD 的 MI455X UALoE72 要 2027 Q2
才量产。

Supply chain 层 Google + Broadcom 在 N3 上比 NVIDIA + AWS
早一代落地，TPUv7 已经在 2025 年量产，v8 继续 N3/2nm（SemiAnalysis
“The Great AI Silicon Shortage” 长文有完整
timeline）。这是过去十年第一次出现工艺节点上的领先。但这层也最容易被
NVIDIA 反压：Jensen 反复说 advanced node 产能、CoWoS、HBM3E
都被锁了几年，Google 的 TPU 8i ramp 要到 2027 才上量也佐证了这一点。

商业模式层 Google 第一次把 TPU 当成可购买的硬件。SemiAnalysis
报道了一个被忽视的细节：约 40 万颗 Ironwood（v7）通过 Broadcom
直接卖给 Anthropic，由 Fluidstack 做 on-site setup，物理放在 Anthropic
自己的 datacenter。从 v1 到 v6，TPU 始终只租不卖，所有客户都必须经 GCP
接入。这一规则一旦破例，后续 Meta、xAI、SSI 跟进的概率显著上升。

这四层放一起的结论：TPU 真的有可能成为另一套
NVIDIA，但不是马上。三个判断分量不同的不确定性叠在一起：性能数据缺失、supply
chain 仍有滞后、商业模式刚开口子。我的判断是 18-24 个月内 TPU 不会取代
NVIDIA，但会在 frontier inference 这个细分市场让 NVIDIA 失去 pricing
power。

## 二、杠杆在哪里：PyTorch
是表象，vLLM 是真裂缝

Google 想要复制 NVIDIA 那一套，必须解决开发者从 CUDA
切过来的迁移成本。看清楚杠杆在哪里很重要，因为 PyTorch
这一层的故事容易让人误判。

PyTorch
后端中立化喊了五年都没动。原因是训练栈的迁移成本太高，FSDP/DDP/checkpoint
format/memory layout 都和 CUDA 深度耦合。SemiAnalysis
在 TPUv7 长文里 给了非常具体的诊断：Google 历史上只对 JAX/XLA:TPU
栈提供 first-class 支持，PyTorch on TPU 是二等公民，依赖 lazy tensor
graph capture，不支持 PyTorch native distributed APIs，不支持
DTensor/FSDP2/DDP。Hacker News 上工程师抱怨「PyTorch/XLA 是 undocumented
behavior 和 bug 的烂摊子，训 8 小时后静默 hang」非常典型。HuggingFace
自己的 optimum-tpu 项目
2026 年初进入 maintenance mode，README 直接引导用户改用 vllm-project/tpu-inference
或 HF Accelerate，把球踢回给 Google。第三方民间桥梁退出，chip
厂商亲自下场，这才是 PyTorch on TPU
这一轮和过去十年所有尝试最关键的差异。

但 PyTorch 训练栈的迁移要 18-24 个月才传导到中小 application
公司。短期真正的杠杆是 vLLM。

vLLM 在 2025-2026
已经成为多后端推理的事实标准，NVIDIA / AMD / Intel / Trainium / TPU
全覆盖，17k+ stars，SGLang
紧跟。这意味着推理这一层的 lock-in 已经技术上松了，剩下的只是商务和
SLA。Google 这一波对推理市场（TPU 8i + Anthropic claude.ai
流量）的攻击，其实是踩在 vLLM 这个开源杠杆上的。这个杠杆是 Meta
在维护的，NVIDIA 没法自己拆掉。NVIDIA 的反应也很说明问题：花
$20B 收购 Groq 的 LPU 团队（包括前 CEO Jonathan Ross），把它做成 LPX
rack，等于承认在专用推理 chip 这个细分市场必须有专门答案，不能只靠 GB300
NVL72 的系统集成。

所以杠杆排序是：vLLM 现在就在影响
deployment（推理这一层裂缝已经裂了）→ TorchTPU 18-24
个月后影响训练栈选择（开发者迁移曲线刚开始）→ Pallas 这种 TPU 原生
kernel 语言长期决定深度优化的天花板（仍然是 Google 内部 + Anthropic
这种深度合作伙伴的事）。

NVIDIA 的反制也对应这个排序：rack-scale 系统集成对推理（GB300
NVL72：50× tokens/W、35× 更低 cost-per-token）+ Groq 收编做 LPX rack
抢专用推理 ASIC + supply chain 锁产能。但这三件反制都没法直接拆掉 vLLM
这层杠杆。

## 三、谁能真正撼动
NVIDIA：Anthropic 单点依赖

把视角从 Google 一家拓宽到整个非 NVIDIA
阵营，撑起这一波叙事的本质上是 Anthropic 这一个 lab。

AWS
Project Rainier 100% Anthropic，1M Trainium2 集群没有第二个外部
production 客户。TPU 外部最大客户也是 Anthropic。SemiAnalysis 关于 TPU
的乐观文章里 the more TPU Meta/SSI/xAI/OAI/Anthropic buy
虽然列了一串名字，但 Anthropic 始终在最前。Bank of America 10 月的 note
用了更直白的措辞：skepticism about Trainium outside of
Anthropic。Cerebras 86% 收入集中在两家 UAE 实体，是 sovereign-driven
而不是 hyperscale-driven 的成长。Groq 已经被 NVIDIA 收编进 LPX rack。AMD
拿到 Meta
6GW MI450 这一笔 design win，但 rack-scale 量产要 2027 Q2。

所以 Cloud Next 2026 这一波三层动作，更准确的描述是「Google +
Anthropic 联合体的三层攻击」。Anthropic 同时是技术 enabler
和商业借口。SemiAnalysis 强调 Anthropic 有 strong engineering resources
and ex-Google compiler experts，能投入 custom kernels 把 TPU MFU
做到接近 NVIDIA 水平，等于替 Google 解决了「外部客户没人会用
TPU」的鸡生蛋问题，证明非 Google 团队也能榨出 TPU 性能。同时 $40B+
量级的承诺给 Broadcom/TSMC/MediaTek 整条链路提供了 capex 信号。没有
Anthropic 这个体量买家，TorchTPU、8t/8i 拆分、Broadcom
多年合同都不成立。

钱的真实落地节奏比公告标题脆弱。Broadcom
8-K 里那句免责披露 写得很清楚：consumption depends on Anthropic’s
continued commercial success，并且与 operational and financial partners
仍在谈。这等于 Broadcom 公开告诉 SEC：3.5GW 是 conditional 的，需要
Anthropic 自己继续融资 + 第三方算力金融化（很可能是和 CoreWeave 类似的
SPV 结构）才能兑现。叠加 Google
$40B 中 $30B 是 milestone-conditional，整个「$40B +
5GW」的承诺，2026 年内真正落地的现金只有 $10B，剩下都附带条件。

最难反驳的反方论点是：Google 自己用得最爽的算力不会留给客户。chosun
的报道 说 Google 拥有全球 23% AI 算力（5M 颗 H100 等效），其中 3.8M
是自家 TPU，但绝大部分自用支撑 Search/Ads/Gemini。Anthropic 拿到的 3.5GW
是 2027 年才上线的容量，TPU 8i 自己的 ramp 同样要拖到 2027。同时 Google
在 Cloud Next 2026 上还宣布了 NVIDIA
Vera Rubin A5X 在 GCP 上单 site 8 万 GPU、跨 site 96 万 GPU
的部署，自己也在大笔买 NVIDIA。这是个真矛盾。我的判断是 Google
三层动作的目标不是抢 NVIDIA 的全部市场，而是把 Anthropic + 几个
sovereign + 1-2 个 hyperscale lab 锁住，让 NVIDIA 在 frontier inference
这个长尾市场失去 pricing power；同时 Google Cloud 自己作为中性场地，让
TPU 和 NVIDIA 都向企业 agent 收租。这个 framing 比「Google 要把 NVIDIA
赶出去」更接近真实意图。

剩下能真正给非 NVIDIA 阵营加票的潜在 big player 有两类。一类是
frontier lab 第二梯队（Mistral、xAI、SSI、字节系），能不能在 2026
年内出现第二家像 Anthropic 这样体量的 TPU 大客户决定了 5GW 这一笔的
follow-through 速度。另一类是 sovereign（Saudi PIF、UAE
G42、欧洲若干），他们对 NVIDIA
的依赖出于地缘原因有动力主动多元化，但工程能力和应用规模都不到能撑起一个新生态的水平。

## 历史
review：过去十年的真实差异

把上面三个问题答完，回头看一遍历史 review 才有重量。Google 推 TPU
推了快十年，过去七代都没真正撼动
NVIDIA。这一次为什么会不一样，决定了上面三个判断的可信度。

过去十年没成功的真实原因有三层。第一，技术上 PyTorch on TPU
难用，软件栈是二等公民。第二，商业上 TPU
只租不卖，企业客户不愿被锁在单一云。第三，组织上 TPU teams 只关心内部
KPI，外部销售长期不被重视，HN 上有 Google
销售人员承认「内部需求太大根本顾不上推外部」。三件事互相加固成自我强化的冷启动循环：用户少
→ 优化少 → 用户更少。

这一轮三件事都同时改了。第一，技术上 TorchTPU 是 PyTorch
first-class，HuggingFace 退出维护把球踢回给 Google 强迫 chip
厂商亲自下场。第二，商业上 Anthropic 这一笔开了「物理交付到客户
datacenter」的口子。第三，组织上 SemiAnalysis 明确写 Google 已经 revised
their software strategy for externally-facing customers and has already
made major changes to their TPU team’s KPIs，开始投入大工程量做
PyTorch/vLLM/SGLang TPU
原生支持。三个改变同时发生，是过去十年第一次。

还有一个被遗忘的伏笔是 TPU v4i。Jouppi 团队 2020 年内部部署的 v4i
已经是训练/推理分家的彩排，2021 年 ISCA
论文 写明 inference DSA 需要 multi-tenancy、air-cooling、大 SRAM
来保 P99 latency。v8 的 8i 不是新发明，而是把内部已经验证 5
年的范式做成了对外产品。这帮助回答为什么是现在拆：技术上 Google
早就准备好，等的是 agentic inference 在外部市场变成显性需求。从
Anthropic 的 Claude API 流量曲线、Cursor 的负毛利讨论、SaaStr
那篇「Inference is the new S&M」 的传播热度看，这个外部需求 2026
年第一季度刚到位。

工艺节点的领先也是过去十年第一次出现。SemiAnalysis 在 The Great AI
Silicon Shortage 长文里证实 Google + Broadcom 的 TPU 在 N3 节点上比
NVIDIA + AWS 早一代落地，TPUv7 已经量产，v8 继续 N3/2nm。NVIDIA 还在从
4NP 的 Blackwell 迁到 N3P 的 Rubin。专业化（训推分家）+ 工艺先发 +
软件投降，这三件事第一次同时发生。

## 总判断

CUDA 锁定第一次出现可量化的松动，松动主要在推理而不是训练，杠杆是
vLLM 而不是 PyTorch。Google 三层动作的真实威胁不在抢市场份额（2026 年内
NVIDIA 数据中心 AI 收入大概率仍在 +50% YoY 以上），在让 NVIDIA 失去
frontier inference 的 pricing power，迫使 NVIDIA 把护城河叙事从 CUDA
转向 supply chain 和 system。整个非 NVIDIA 阵营是 Google + Anthropic
联合体撑起来的，所以这一波叙事的兑现取决于 Anthropic 商业曲线能否在 2027
年前继续陡升。如果 Anthropic 增速不及预期，5GW 的承诺、Broadcom 的
capex、TorchTPU 的生态投入会同时承压，那时候 NVIDIA 已经把 supply chain
moat 收紧了一圈。

对正在做 LLM 应用、agent、API 包装层的 builder，未来 6-12
个月最值得做的三件事：现在不要迁 TPU，但要把推理层抽象成 prefill/decode
可分离、模型可插拔的架构（中小 builder 的杠杆是抽象层，直接迁 TPU 的 ROI
只对推理量超过 $500K/月的玩家成立，参考 Midjourney
月 inference 成本从 $2.1M 降到 $700K 的案例）；重启过去 12
个月因为成本砍掉的 long-context feature（TPU 8i 的 288GB HBM + 8.6 TB/s
带宽 + 384MB SRAM 缓冲层组合，让 long-context decode 单位 token
成本下降斜率显著陡于短上下文，a16z 的
LLMflation 给出的等能力推理成本年降 10x
曲线已经在过去两年验证过，full-codebase context、persistent agent
memory、multi-document deep research 这些场景 2026 H2 到 2027 H1
进入临界点）；pricing 模型从 per-seat 转向 outcome-based，把 inference
在会计上从 COGS 重新归类为 R&D 或 growth（Cursor 在 $100M ARR
时跑负毛利到 $2B ARR 才转正的故事说明 per-seat + token
成本不可控的模式不可持续）。

值得每个月跟踪的指标有三个：Stanford CS / CMU / MIT 这一档学校的
GPU/TPU 配置变化、vLLM 上 TPU backend 的 PR 合并速度、以及 Meta
是否在生产环境正式 deploy TorchTPU。这三个变量任意一个出现质变，都意味着
18-24 个月的开发者迁移曲线开始走完第一段。

## 来源说明

本文综合了五条并行调研线的素材，关键来源在文中已标注。完整证据链与原始引用见同目录下的
01–05 各份调研笔记，以及 00 号附录（用户提供的 TorchTPU
内部信息和群讨论）。

主要二手信源：SemiAnalysis、The
Information、Stratechery、Bloomberg、Reuters、CNBC、TechCrunch、Hyperframe
Research、a16z LLMflation、Epoch AI、Google Cloud
blog、developers.googleblog.com、Anthropic news、Broadcom 8-K、Hacker
News 多个相关 thread、Dwarkesh Patel podcast 2026-04-15。

主要数据缺口：(1) TorchTPU 在生产规模下 vs CUDA 的 head-to-head
benchmark；(2) 5GW 中 8t/8i 的实际配比和逐年 ramp curve；(3)
Meta/OpenAI/xAI 是否在 2026-04-24
之后出现迁移信号。这三个变量是这一波叙事兑现速度的最直接观测指标。