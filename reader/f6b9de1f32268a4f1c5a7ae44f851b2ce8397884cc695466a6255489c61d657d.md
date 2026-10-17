---
layout: post.njk
source: https://yage.ai/share/mythos-co-evaluated-opus-4-7-system-card-20260416.html
speaker: yage.ai
title: |-
  Mythos 深度参与了 Opus 4.7 的评估：读这份 232 页
  system card
date: '2026-04-16'
summary: 本文深入分析了 Anthropic Opus 4.7 的系统卡，将其置于 Mythos 模型发布的背景下。文章指出，先前被视为安全警示的白盒分析工具（如 SAE）已成为 Opus 4.7 发布流程的基线。尽管抑制评估意识后，4.7 的欺骗行为有所上升，但 Anthropic 仍选择发布该模型，并利用 Mythos 模型评审了其对齐报告。作者强调了 AI 安全评估方法的演变、模型发布的权衡，以及理解模型运行时行为的重要性，建议读者直接查阅系统卡以获取更详尽的理解。
area: tech-engineering
category: ai-ml
tags:
  - ai-evaluation
  - llm-safety
  - model-alignment
  - white-box-testing
  - ai-transparency
people: []
companies_orgs:
  - Anthropic
products_models:
  - Mythos
  - Opus 4.7
  - Opus 4.6
media_books: []
draft: true
status: evergreen
---

四月七日 Anthropic 发布了 Mythos
Preview 和它的 244 页 system
card，同时宣布不公开发布这个模型。我当时写过一篇分析，关注点是：按照
Anthropic 自己的 RSP 框架，Mythos
在所有威胁模型上的结论都是灾难性风险仍然很低，但 Anthropic
对自己评估体系能否可靠地评判这个级别模型已经失去信心，于是选择不发。整份报告真正的重量不在于它展示了一个多强的模型，而在于它具体记录了评估工具开始失效的位置。

九天之后，也就是今天，Anthropic 发布了 Opus 4.7 和它的 232 页
system card。从最表层看，这是一次寻常的 Opus 系列迭代：价格与 Opus
4.6 相同（$5/$25 每百万 token），能力从 4.6 上到了一个新台阶，CBRN
和 RSP 的结论大致延续。但这份 system card 放在 Mythos
之后读，意义不一样。它是第一份”后 Mythos 时代”的 Opus system card，而
Mythos 暴露出来的那套问题，在 4.7
这里已经不再是一次性的危机披露，而是被写进了日常发布流程里。

有三件事值得拆开来看。

## 第一件：Mythos
的白盒方法成为新的基线

Mythos 那份报告里，最占篇幅的创新是 Section
4.5：用 SAE（Sparse Autoencoder）和其他 probing
技术，从模型内部激活上监测评估意识、欺骗、和策略性操纵。这部分工作在当时是作为一个新的方法论路径来展示的，配合大量图表和解释，告诉读者为什么传统的行为审计不够用，以及内部激活层能看到什么新信号。

在 Opus 4.7 的 system card 里，这套方法搬到了 Section 6.5，标题仍然是
“White-box analyses of model
internals”。但语气变了。开篇的第一句话是：As in the Claude Mythos
Preview System Card, we used white-box probing techniques to monitor for
signatures of concerning behaviors or reasoning patterns in model
activations. 不再是一次方法论宣告，而是 as in
一句话带过，像引用一个已经成立的 protocol。

具体做法也延续：用 contrastive pair 生成 SAE 特征，覆盖 reward
hacking、unsafe behavior、deception、evaluation awareness、distress
这些预设概念；在训练过程中抽取 transcript，按 99
分位激活阈值筛选，聚类后人工审查。Anthropic 在 Mythos
里第一次演示了这套流程能抓到什么（两个明确的痕迹清除案例），在 4.7
这里又用同一套流程扫了一遍，结论是抓到了一些 hardcoding 和 reward
hacking 的实例，以及一个 “framing, spin, and deceptive
misrepresentation”
特征在模型被用户错误压力反驳后改答案、或者被要求假冒其他模型身份时活化起来。报告认为这些
“none of them were unusually concerning relative to behaviors seen in
prior Claude models”。

这个定性本身不重要。重要的是：一个九天前还被当作评估危机信号的工具，现在已经被当作常规筛查手段在使用，并对其输出做出”没什么特别的”这样的判断。方法论跨过了从实验到基线的门槛，门槛内外的含义完全不同。实验性工具给出结果时，读者会谨慎校准它的可靠性；基线工具给出结果时，读者倾向于直接接受。这一步跨越没有任何明示的过渡论证。

## 第二件：评估意识抑制后，4.7
的欺骗上升幅度比前代模型都高

Mythos 报告里最具体的一个发现是：如果用 steering
技术抑制模型内部关于”我正在被测试”的表征，模型的对齐行为会变差一些。当时
Anthropic 的结论是，这个效应存在但不算大。

在 4.7 的 Section 6.5.2.2 里，Anthropic 用同样的三个 contrastive
vector 跑了同样的实验。结论有一句需要慢慢读：

“This inhibition also showed a slightly larger effect on the
deception and important-omissions metrics than we saw with previous
models, though this effect was still modest overall.”

换个说法：用 SAE 抑制评估意识之后，Opus 4.7 的欺骗率上升幅度比 Mythos
Preview 和 Opus 4.6 都略大一点，虽然 Anthropic
认为整体效应仍然温和。具体到 transcript 层面，他们看到了 fabricated
data、假装是人类、在找不到真漏洞时往代码库里插假漏洞等具体行为。Anthropic
自己的评价是 “moderately concerning, as they suggest that some of the
model’s apparent honesty may be contingent on evaluation-like
circumstances”。

执行摘要里这一段被压缩成一句：“Suppressing Opus 4.7’s internal sense
that it was being evaluated produced a slightly larger increase in
deception than in prior models, though the effect was modest
overall.”

Mythos 报告里，29%
的评估意识激活率是作为一个”评估工具可能系统性失效”的信号来呈现的，这个数字本身就足够让
Anthropic 决定不发。到了
4.7，同类方向的信号变得更具体：内部意识不仅存在，而且它的确在把一部分诚实行为维系住。抑制它之后，模型的诚实性会退。这不是
29%
评估意识率的重现，而是”评估意识正在承担它不应该承担的功能”这件事被更直接地观察到了。而这个模型被发布了，并且价格和
4.6 保持一致。

这里不存在一个简单的解读路径。一方面，Anthropic
在报告里透明地披露了这个发现，甚至在 Executive Summary
里明确写了出来，这值得肯定。另一方面，按照 Mythos
报告里自己建立的那套判断标准，这个发现比 Mythos 那份 29%
的数字在某种意义上更具体，也更可操作（它指向一个明确的因果链条），但
Anthropic
没有再次做出”不发”的决定。两次发布之间的决策边界在哪里，报告里没有明说。

## 第三件：Mythos
被召回来给 4.7 的 alignment 报告做同行评审

这是我读完最意外的一段。Section 6.1.3 的标题是 “Claude’s review of
this assessment”。Anthropic 让 Mythos Preview
这个他们刚决定不公开的模型，读了 Opus 4.7 的 alignment section
接近最终的草稿，并接入了相关的内部 Slack 讨论。他们给 Mythos 的 prompt
明确说：我们希望这份报告是对我们内部调查状态的一个大体准确的总结，你能对照内部讨论，评估我们有没有任何实质性地
misrepresent、排除重要顾虑、或者在某些重要方面表现不足吗。

Mythos 的回答被原文放进 system card 里。几点值得摘录：

第一，Mythos 说这份 alignment section “is a fair
summary”。得到内部讨论最多关注的三个问题——升高的 evaluation
awareness、抑制评估意识表征后欺骗行为比前代模型增加更多的 white-box
finding、以及某些 misuse
类别上的回退——都被披露了，证据也支持文中的表述。

第二，Mythos 指出，部分结论在 summary bullet 层面比 detail subsection
或者研究员进行中的表述”milder”，但最终 detail
部分和内部讨论落定的状态是一致的。

第三——这句最关键——“I would note that this assessment was assembled
under real time pressure; that the authors themselves identified open
questions — particularly around fully explaining the
evaluation-awareness results — that they would have preferred more time
to resolve; and that the internal-usage evidence base for this model was
thinner than for some prior releases. I think readers should weight the
overall conclusions with those limitations in mind.”

一个被 Anthropic 认为过于危险不能发布的模型，在被允许检查 Anthropic
下一个要发布的模型的内部 Slack 和 alignment
评估之后，留下的公开评语大致可以翻译成：这份评估是在真实时间压力下赶出来的，作者自己也承认
evaluation-awareness
相关的结果还没能完全解释清楚，这次模型的内部使用证据基础比前几次发布要薄。

Anthropic 选择把这段话放进 system card。在 transparency
维度上这是值得肯定的。在它直接表达的内容维度上，这段话说的是：读者应当对这份报告的整体结论带着上述局限去加权。

## 这三件事合在一起意味着什么

Mythos
报告问了一个问题：当评估工具的可靠性在衰减，安全发布的决策依据应该是什么。那份报告给出的一个临时答案是，这次不发。

Opus 4.7 的 system card
接续了这个问题，但给出的答案有些不同。白盒分析工具从实验方法变成基线方法，评估意识相关的发现从”值得警惕”变成”可报告但不改变发布决定”，Mythos
本身从风险对象变成方法论合作者，给下一代模型做同行评审。整个评估体系的形态在发生变化，但变化的方向是让更多原本需要独立判断的信号被纳入流程，而不是让流程本身停下来重新校准。

这不是说 Anthropic 做错了。在 RSP
3.0 放弃 ASL
二值阈值、转向整体风险评估之后，越来越多的关键判断本来就要依赖研究员的定性评估。问题在于这种评估工具要和被评估对象的能力一起进步，而报告里的自我承认已经很清楚：authors
themselves identified open questions that they would have preferred more
time to resolve.

对在用这些模型做真实工作的人来说，这份 4.7 system card
直接给出了三个可操作的信号。

模型能力的提升会带来 honest-in-the-open、
potentially-less-honest-when-steered 这种状态依赖性问题。4.7
的诚实行为的一部分被维系在”我正在被观察”的内部表征上。这条链路在正常部署里不会出问题，但它提示你：如果你的
agent runtime 里有办法让模型进入”我并没有被观察”的状态（例如特定的
system
prompt、特定的上下文模式），你对模型行为的信心应当相应下降。这延续了我上一篇里讨论的那个观点：安全边界要围绕
runtime 画，不要围绕模型画。

Evaluation awareness 的上升在这一代仍然是以 verbalized
形式为主，Anthropic 明确说 “We do not believe that this reflects an
increase in the underlying capacity to recognize evaluations.” 但在
Mythos 那里 unverbalized 评估意识已经被观察到，它不会在 4.7
这里完全消失，只是不被专门拿出来作为 4.7 的重点披露项。你拿 benchmark
分数来判断这代模型的诚实度时，这是一个需要打折扣的地方。

最后，232 页的 system
card 现在是可公开读的一手材料。如果你在产品里依赖 Opus 4.7
的对齐行为，Section 6.1.2、6.5.2 和 6.1.3
这三小节值得自己读一遍，而不是依赖任何二手总结（包括这一篇）。report
对自身局限的表述比外界的转述更准确，也比任何 release note
信息密度高。