---
layout: post.njk
source: https://yage.ai/share/deepseek-vision-workaround-20260815.html
speaker: yage.ai
title: 给性价比最高的推理引擎装一双眼睛
date: '2026-08-15'
summary: 文章探讨了在缺乏原生多模态能力的情况下，如何通过感知层与推理层分离的架构来构建高效的AI系统。核心思想是利用轻量级模型（如3B VLM）在本地进行快速、低延迟的感知任务，并将结构化的感知结果传递给强大的推理模型（如DeepSeek V4）在云端进行复杂推理，从而在延迟、隐私和成本之间实现最佳平衡，并强调这种分工架构的持久价值。
area: PAI
category: ai-workflow
tags:
  - model-architecture
  - vision-language-model
  - latency-optimization
  - cost-aware-routing
  - cascade-architecture
people: []
companies_orgs:
  - DeepSeek
  - Liquid AI
products_models:
  - DeepSeek V4
  - DeepSeek-VL2
  - LFM2.5-VL-3B
media_books: []
draft: true
status: evergreen
---

感知层与推理层分离架构示意

## 性价比最高的推理引擎，没有眼睛

DeepSeek V4 在 2026 年 4 月发布，两个模型：V4-Pro，1.6T 总参数，49B
激活；V4-Flash，284B 总参数，13B 激活。两个都原生支持 100 万 token
上下文，支持三级推理模式，从快速直接回答到逐步推理到最大推理努力，还支持
function calling。V4-Flash 定价每百万 token 输入 $0.14、输出
$0.28，大约比 Claude Opus 5 便宜 36 倍。能力上 V4 落后闭源前沿约 3 到 6
个月，价格是几十分之一。8 月 16 日 DeepSeek 切换到峰谷定价，V4-Flash
峰时涨到 $0.44/$1.32，谷时 $0.22/$0.66，大致是原来的 1.6 到 4.7
倍。涨了之后 V4-Flash 仍然是市面上最便宜的推理 API 之一，Claude Opus 5
的输出价格仍然是 V4-Flash 峰时输出价格的 19 倍。

这不是某一版的运气。DeepSeek 从 V2 起就贴着效率走。V2 的论文标题就叫
“A Strong, Economical, and Efficient Mixture-of-Experts Language
Model”。它提出的 Multi-head Latent Attention 把 KV cache
压缩进一个低维潜在向量，DeepSeekMoE 用细粒度专家分割把训练成本降下来。V3
延续这条路线，671B 总参数但每 token 只激活 37B。训练花了 557
万美元，能力与 GPT-4 级模型可比。V4-Pro 的 CSA+HCA 混合注意力把百万
token 推理的计算量压到 V3.2 的 27%，KV cache 压到 10%。

向这个引擎发送 image_url 字段，返回一行 JSON
反序列化报错：

> Failed to deserialize the JSON body into the target type:
> messages[0]: unknown variant ‘image_url’, expected ‘text’

请求还没进推理引擎就挡住了。API schema 里没有图片输入这个选项。模型
catalog 列出 11 个 DeepSeek 模型，modality 全部是 text。

DeepSeek 不是做不了视觉。2024 年 12 月它发布过独立的视觉模型 DeepSeek-VL2，在
OCRBench 上拿 834 分，发布时超过 GPT-4o。2026 年 7 月，一位 DeepSeek
研究员在 GitHub 上短暂公开了一篇名为 “Thinking with Visual Primitives”
的论文，4 小时后撤下，原始 repo 已经 404，只剩社区镜像和解读视频。论文把
bounding box 和 point 直接编织进推理链，在迷宫导航任务上做到 66.9%，同期
GPT-5.4 约
49-51%。但论文撤回了，权重从未发布，官方只说未来集成到基础模型，没有时间表。VL2
的上下文窗口只有 4096 tokens，没有 function
calling，发布后几乎没迭代。这些视觉能力都没进商用 API。

不做多模态是当前的产品选择，不是技术限制。DeepSeek
有视觉研究线和前沿论文，可能在未来某个时间点加入原生多模态。那个时间点是什么时候，不知道。

## 在它长出眼睛之前

2026 年 8 月 12 日，Liquid AI 发布
LFM2.5-VL-3B，一个 3.1B
参数的视觉语言模型。模型卡有一段少见的明确声明：推荐它做单轮、高吞吐、低延迟的任务，比如实时目标检测、批量
OCR、菜单路牌翻译。然后写明不推荐用于长上下文或重推理任务，比如视觉网页设计或回答蓝图的技术问题。大多数小
VLM 想证明自己什么都能做。这个模型卡反过来写明自己不擅长什么。

LFM2.5-VL-3B 把 3.1B 参数塞进 3.3 GB 内存，在 Apple M5 Max 上跑
228 tokens/s，在 Galaxy S26 Ultra 手机上跑 20
tokens/s。厂商横评里，屏幕定位 ScreenSpot-v2 拿 80.7 分，物体定位
RefCOCO 87.9 分，ToolSandbox 59.5 分。这些数字在 3B
级别领先，部分指标接近 5B 模型。全部来自 Liquid AI
自己的横评，目前没有独立复现。Reddit 上有人专门发帖问有没有外部
benchmark，没有找到。

这个模型专做感知不碰推理，DeepSeek V4 专做推理不碰感知。在 DeepSeek
原生支持多模态之前，这两个模型可以拼成一条 pipeline：LFM2.5-VL-3B
在边缘做视觉感知，输出结构化文本（门开了，画面中有车），DeepSeek V4
在云端做推理（这是主人的车还是异常？应该触发什么通知？）。

LFM2.5-VL-3B 发布后，我在家里的 garage
摄像头数据上跑了一组评估。验证集 280
张图片，人工标注了车库门开或关，任何可见开口都算开，只有完全关闭才算关。LFM2.5-VL-3B
从没见过任何 garage 画面。零样本跑下来，准确率 94.3%，开门 recall
92.6%。和专门在这个任务上训练过的小模型比，差距大概 3 到 5
个百分点。一个 3B 的通用 VLM 没用任何 garage
数据训练，在明确的单问题判断上接近了专用模型。

但如果把任务换成多类别物体检测，从 13
类里找有没有车、有没有人，recall 掉到 66.2%，空场景误报率为 47%。零样本
VLM 做简单的 binary
判断够用，做精细多类别检测还不够。这个差距不影响分工架构的价值，因为感知层不需要替代专用
CNN 做所有事。

感知层做第一层判断：门开了吗？有人吗？这一层用通用 VLM
零样本就够。检测到异常，把结构化的感知结果发给 DeepSeek V4
做推理。感知在本地 1.5 秒完成，推理在云端再花 1 到 3
秒。对于只在异常时触发、不需要每帧判断的场景，这个延迟可以接受。

## 不只是临时的凑合

分离架构有原生多模态给不了的东西。

第一是延迟。感知在本地 1.5
秒完成，不依赖网络。如果把视觉和推理放在同一个云端多模态模型里，图片上传、视觉编码、推理生成加起来
3 到 5 秒起步，还要算上网络往返。1.5 秒的本地感知和 3 到 5
秒的云端推理之间的延迟差是物理限制，不是优化空间。任何软件升级都消不掉它。

第二是隐私。感知在本地完成，图片不出设备。只有结构化文本上传云端。对于家庭监控、医疗文档、财务表单这类场景，图片本身不上传是一个独立的安全属性，和模型能力无关。

第三是成本。高频感知用 3B
模型在本地跑，边际成本为零。只有检测到异常时才调用 DeepSeek
API。如果用一个多模态大模型每帧都跑云端推理，成本会高几个数量级。

业界已经按这个方向在做了。viso.ai 在
2026 年 7 月把生产级视觉 AI
的架构分成三层：感知模型捕获场景，视觉语言模型解释场景，行动层关闭回路。他们写了一句关键约束：感知层决定整个
agent workflow
的节奏。检测结果到达推理层太慢或不准确，所有下游决策都会退化。Moondream
是一个 2B 参数的小型 VLM，有开发者把它和大 LLM
组合使用，大模型做规划，Moondream 做 UI 理解，比直接用 Computer Use API
更快更可靠。vLLM
项目 在 2026 年 1 月发布了 Semantic
Router，一个位于用户和模型之间的路由层。RouteLLM 的数据显示维持 95%
的质量同时可以降低 45-85% 的成本。Apple Intelligence 约 85%
请求在设备本地处理，12% 走 Private Cloud Compute，3%
走合作伙伴云端。苹果按部署位置分层，但思路一样：按需升级，cost-aware
routing。

DeepSeek 可能明天就发布 V4-VL，把视觉能力加进
API。即使如此，上面三个优势仍然成立。1.5 秒的本地感知和 3 到 5
秒的云端推理之间的延迟差，任何软件升级都消不掉。图片不出设备的隐私属性不会因为模型变强就不再重要，高频感知用
3B 本地跑的成本优势不会因为 API
降价就消失。一个模型同时做视觉和推理，不意味着应该在同一层做。

## 还缺什么

从概念成立到生产可用之间还有一个缺口。cascade 架构需要一个 confidence
signal 来决定什么时候从感知层升级到推理层。LFM2.5-VL-3B
输出的是自然语言，不是概率分数。怎么从自然语言里提取一个可靠的置信度信号，是这套架构从
LLM cascade 迁移到 VLM cascade 的过程中需要人补的环节。TMLS 的
model routing 报告 指出了这一点：在 LLM 域已经验证的 cascade
方法论，向多模态迁移的核心障碍是 confidence signal
的校准。这是一个需要工程解决的问题，不是等待模型能力提升就能消失的问题。

DeepSeek
什么时候加视觉不知道。它有视觉研究线，有前沿论文，有技术储备。可能下个版本，可能明年，可能更久。分离架构的价值不依赖那个时间点。在
DeepSeek 长出眼睛之前，用一个 3B 模型做感知、DeepSeek
做推理，是一个现在就能跑的
workaround。跑通后积累的工程经验，怎么桥接感知输出和推理输入、怎么校准
confidence、怎么设计 escalation
逻辑，在原生多模态来了之后也不会浪费。物理层面的分工优势，比任何一家公司的产品线都持久。