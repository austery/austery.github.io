---
layout: post.njk
source: https://baoyu.io/blog/a-conversation-with-dario-amodei-daniela-amodei
speaker: baoyu.io
title: Anthropic 兄妹 Dario Amodei 和 Daniela Amodei 最新对话：Claude 为什么一直限速？ | 宝玉的分享
date: '2026-05-06'
summary: 文章探讨了 Anthropic 爆炸式增长（年化 80 倍）带来的算力瓶颈与 Claude 限速问题。强调开发者是 AI 经济影响的先行指标，并展望了组织级 AI 及 AI 在安全、代码审查等主观任务上的突破。Anthropic 奉行“光影并举”原则，平衡快速发布与负责任 AI。对话还涉及 AI 驱动的创业模式演变和多样化用户用例，并以 Amdahl 定律分析 AI 加速下的瓶颈转移。
area: tech-engineering
category: ai-application
tags:
  - anthropic
  - claude
  - compute-bottleneck
  - organizational-ai
people:
  - Dario Amodei
  - Daniela Amodei
companies_orgs:
  - Anthropic
  - SpaceX
products_models:
  - Claude
  - Claude Code
  - Mythos
  - Project Glasswing
media_books: []
draft: true
status: evergreen
---

宝玉的分享

Menu

See all posts

Published on 2026-05-06

# Anthropic 兄妹 Dario Amodei 和 Daniela Amodei 最新对话：Claude 为什么一直限速？

作者：

宝玉

在 5 月 6 日的 Code with Claude 旧金山场上，Anthropic 兄妹 Dario Amodei 和 Daniela Amodei 一起坐到了台上。这是 Anthropic 第二届开发者大会，同一天，Anthropic 刚刚宣布与 SpaceX 签下 Colossus 1 数据中心的全部算力（超过 300 MW、22 万张 NVIDIA GPU）。

主持这场对话的是 Anthropic 首席产品官 Ami Vora（2026 年 1 月接替转去 Labs 的 Mike Krieger）。话题从“指数曲线上的体感”开始，覆盖开发者生态、模型训练逻辑的下一步、Anthropic 在能力释放上的取舍，一直聊到未来六个月最让 Dario 兴奋的能力变化。

下面是这场约半小时对话的整理，原视频来自 Anthropic 官方 Code with Claude 系列。

原始视频：https://www.youtube.com/watch?v=7xco5Qd2Oo8

## 要点速览

一，Anthropic 原本按“每年 10 倍”准备算力，但 2026 年第一季度的实际增速年化下来约为 80 倍，这是 Claude 一直在限速的直接原因。Dario 直说希望增速回到 10 倍，“80 倍太疯狂了，扛不住”。

二，Dario 一年前在去年的 Code with Claude 上对 Mike Krieger 说，2026 年会出现第一家“一人估值 10 亿美元”的公司。如今离 2026 年结束还有七八个月，目前的最新进展是：已经出现两人估值 10 亿美元的 AI 公司，以及单人估值数亿美元的案例。

三，软件工程师是 AI 在整个经济中扩散的“先行指标”。开发者怎么用 Claude，预示了其他行业未来怎么用。

四，编码能力进步快，是因为它“可验证”（跑单测就知道行不行）。下一个真正难啃的，是安全、设计质量、code review 这些没法用单测自动判定的“主观”能力。Anthropic 正在训练模型攻克这些，也会反哺写作和科研。

五，“光与影并举”（Hold light and shade）是 Anthropic 的内部文化原则。最新案例是最强模型 Mythos：因为它能识别和利用软件漏洞，公司没有公开发布，而是走 Project Glasswing 的限定路径，发给 50 多家机构去强化防御。

六，Dario 最期待未来六个月的能力变化，是组织级 AI。AI 不再只是替一个人做完很多人的事，而是在一群人组成的组织里把这件事重复做很多次。

## 【1】80 倍的年化增速，是什么体感

Ami 一开场就抛出了个灵魂拷问：你们俩是真正切身感受这条指数曲线的人，这种增长是什么感觉？

Daniela 接话先用了一个公司内部的梗。Anthropic 的 Slack 里有一个“过山车”的表情包，斜率突然垂直拉起来的那种。她说自己和 Dario 像分别坐在车头和车尾，“看你坐哪头，得到的鞭甩感不一样”。她接着补了一句让台下笑出声的话：

> 我们是有点不太确定，开过山车的那个操作员，是不是一个心智状态可疑的、暑假来打工的 15 岁小孩。
> （“We're not totally sure that the operator of the roller coaster isn't like a 15 year old who's doing a summer job of like questionable level of sound mind.”）

Dario 的回答更“理科”。他说自己和几位联合创始人十多年前就是通过 scaling laws（规模化定律，即模型能力随训练算力呈可预测的增长）写下了这条曲线，预测过“先花 1000 美元一个月，然后 1 万、10 万，一直到几千亿，模型在这个任务和那个任务上会做到什么程度”。所以从纸面上看，眼前发生的一切其实是预测之内。

> 注： Dario Amodei 2014 年在百度研究院参与 Deep Speech 2 项目时首次观察到“规模越大、性能越好”的规律，2020 年在 OpenAI 合著发表了影响深远的规模定律论文。Anthropic 的七位联合创始人中多人参与了这项研究。这也是他说“十多年前就预测了这条曲线”的背景。

但他说，把曲线写在纸上和亲眼看见这条曲线变成现实，是两回事。他用了《星际穿越》里那个著名的场景做类比：飞船降落在一个靠近黑洞的星球，星球上的浪有 2000 英尺高。

> 我以前是物理学家，广义相对论里物质能被剪切到什么程度，公式我都懂。但你真的在人类尺度上看见这一幕，是另一种深层的、令人不安的怪。Anthropic 内部每一年都是这种感觉。
> （“I was a physicist, I know the math, the general relativity, how much things can be sheared. But actually seeing it on human scale, there's something deeply, it's kind of deeply strange and unsettling about seeing it actually happen.”）

Dario 接着把“指数曲线”具象化到了三个数字上。

第一，今年是公司历史上第一次，Claude 让 Anthropic 内部 PR（pull request，代码合并请求）的数量出现了曲线向上的拐点。Claude 写代码的速度，超过了人加进来的速度。

第二，公司的外部增长，今年第一次“超过了指数”。Anthropic 原本按“每年 10 倍”做算力规划，做了从“几乎不增长”到“涨 10 倍”的多版本预案。但 2026 年第一季度，如果按当季度速度年化，营收和使用量是 80 倍。

> 注： Dario 在表述时用了“if you were to annualize it”的限定语，这意味着 80 倍是将单季度爆发外推至全年的数字。实际全年增速不太可能维持在这个水平，但即便打折，这个数字仍然远超公司的 10 倍规划弹性。

第三，这就是为什么 Anthropic 一直在限速。Dario 用了“道歉式”的语气：

> 80 倍太疯狂了，是真的扛不住，我希望它能回到正常一点的数字，比如就 10 倍。
> （“I hope the 80x growth doesn't continue 'cause that's just crazy and it's too hard to handle. I hope for some more normal numbers, a mere 10x.”）

他随后把话题接到了今天的另一条新闻：

> 你们今天看到 SpaceX 的算力交易了，我们在尽全力把更多算力拿到手，会在我们能力允许的范围内尽快传递给你们。
> （“As you saw today with the SpaceX compute deal, we're working as quickly as possible to provide more compute than we have in the past.”）

> 注： Anthropic 在 5 月 6 日同步公布的新闻是，与 SpaceX 签订协议，使用 Colossus 1 数据中心（位于田纳西州孟菲斯，原属 Elon Musk 旗下的 xAI）的全部算力，“一个月内”上线超过 300 MW、22 万张以上 NVIDIA GPU。Anthropic 的其他算力交易包括：与 Amazon 高达 5 GW 的协议（其中近 1 GW 在 2026 年底前上线）、与 Google + Broadcom 的 5 GW 协议（2027 年开始上线）、与 Microsoft + NVIDIA 的 300 亿美元 Azure 算力战略合作。Musk 此前曾多次公开批评 Anthropic 和 Dario，但在 5 月 6 日同步发推称，自己上周和 Anthropic 高层接触后“留下了好印象”。这桩交易公告本身就是这场访谈“算力是真实瓶颈”叙事的最直接背书。

## 【2】为什么 Anthropic 把开发者放在用户金字塔最上面

Ami 接着把话题转向开发者社区。这一天的会场坐的几乎全是开发者，她想听 Dario 和 Daniela 怎么定位这个群体。

Daniela 说得很直接：在很多意义上，开发者就是 Claude 最重要的用户。这里面有几层原因：

首先，Anthropic 自己内部就以开发者为主，他们对自己造出来的工具最敏感。

其次，开发者社区给的反馈是真诚的。做过产品的人都明白这有多稀缺：

> 你做出一个产品，看几个数字觉得“还不错”，但开发者社区跟你互动的那种实在感，完全是两码事。
> （“You build a product and you're like I see some numbers like those are nice but...the genuineness with which the developer community I think engages with us is something that is so special.”）

最后，Anthropic 从第一天起就“主要为开发者和企业”做产品，Daniela 觉得这在 AI 圈里其实不太常见。

她列出 Claude 已经渗透进的领域，包括医学、软件开发、金融服务，几乎每个行业都有以开发者为核心的公司在用 Claude 重塑业务。她把这种关系描述成“既是特权也是责任”。

Dario 从另一个角度补充。他说，技术在经济里不会均匀扩散，软件工程师永远是最快采用新技术的那群人。所以这场行业聚光灯都打在编程上不是偶然，“它是接下来整个经济会怎么被 AI 改造的微缩预演”。

## 【3】“一个人 10 亿美元公司”的赌局，还剩七八个月

Dario 接着把“开发者”这条线引向一个具体赌局。他说大约一年前，也就是 2025 年的 Code with Claude，Mike Krieger 当面问过他：

> 第一家估值 10 亿美元、只有一个人的公司，会在哪一年出现？

Dario 当时的回答是 2026 年。如今还剩七八个月。台下笑了。Dario 半开玩笑半认真地补充：

> 在指数曲线上，七八个月已经是一辈子了。
> （“That's eternity on the exponential.”）

他透了个底：已经出现两人估值 10 亿美元、用 AI 起家的公司，也出现单人估值数亿美元的案例，但严格意义上“一个人 10 亿美元”还没兑现。在他看来，这件事真正的含义不是“省人工成本”，而是单个有想法的个体或极小团队，第一次有可能用几年才能积累起来的资源量级，去做出他们想象中的事。

> 我们已经从“模型在帮我们写代码”，走到“模型在帮我们把软件工程当成一个任务来思考”，再走到“模型在帮我们把整个商业单元、整个经济单元当成一个任务来思考”。

> 注： Mike Krieger 是 Instagram 联合创始人，2024 年加入 Anthropic 任首席产品官，2026 年 1 月转去新成立的 Anthropic Labs 担任技术员，专注实验性产品孵化（最有名的当下项目就是后文提到的 Mythos），由 Ami Vora 接任 CPO。Dario 在那场对话里给出的概率是“70%-80% 会发生”。这场赌局的终点是 2026 年 12 月 31 日。不过他没有给出“两人公司十亿美元”的具体案例名称，这个说法目前无法独立验证。

## 【4】单 Agent 走向多 Agent，下一个瓶颈是验证

Ami 顺势问 Dario，开发者使用 Claude 的方式接下来会怎么变。Dario 给出几条相互咬合的趋势。

第一条，从单 Agent 走向多 Agent。一个开发者手上不再是一个 Claude，而是一群 Claude，可能还构成层级关系，上层 Claude 把任务再分包给下层 Claude。Dario 用了一个他经常用的比喻：

> 我们正在朝“数据中心里的天才之国”走。现在还在“一屋子聪明人”这个阶段，正在往上爬。
> （“We're gradually making our way to the country of geniuses in the data center. We're starting with a team of smart people in a room or something.”）

第二条，Claude Code 目前主要在帮“个人”提效，但 Anthropic 越来越多在思考“整个团队、整个组织”的提效，让一群人加上一群 Claude 的整体产出超过简单相加。

第三条，也是 Dario 反复强调的：要看 Amdahl's law（阿姆达尔定律）。当某一段被加速到极限时，瓶颈会跳到没被加速的那一段。

> 你提到 PR 数量，如果你在一个组织里，能写 3-4 倍的 PR，你会立刻意识到，原来还有一堆别的东西在拖着你。如果只把这一段跑得飞快，其他没跟上，反而会出事。
> （“If you're living in a world where you can, within an organization, write three or four times as many PRs as you could previously, you start to understand there are all these other things that are holding you back or that will go wrong if you speed up just that and not everything else.”）

他点出这些“其他东西”具体是什么：安全、验证、code review、设计质量。Anthropic 接下来要做的，不是单点再提速，而是把这一整圈瓶颈一起抬起来，让加速能“平稳、可靠地”释放出来。

> 注： Amdahl's law 出自 1967 年计算机科学家 Gene Amdahl 提出的并行计算公式，原本说的是：一个程序里如果只有部分能被并行加速，另一部分必须串行，那么整体能跑多快受限于那段串行的部分。Dario 把它借来描述工程组织的协作瓶颈，这是他这场对话里反复回到的核心分析框架，后面讨论产品和模型训练时还会再用。

## 【5】训练模型的方式也得跟着变

Ami 追问：这些趋势会不会反过来改变 Anthropic 训练模型的方式？

Dario 的回答有两层。

第一层是已经在发生的事：Anthropic 正在用 Claude 加速 Claude 自己的开发。

第二层更有意思。Dario 说，软件工程之所以是 AI 进步最快的领域，是因为它有一个特殊性：可验证。给模型一段代码任务，它写出来，跑单元测试就能立刻判定对不对。这个反馈回路简单粗暴有效，所以训练效率特别高。

但软件工程里还有一大块东西不可验证：

> 这段代码“真的对吗”？能不能找到错误？有没有安全问题？这些就没那么容易验证了。
> （“Is this thing really right? Can we find errors? Are there security issues? Not quite as verifiable.”）

这里面的道理很直接：训练效率取决于验证的容易程度。代码能跑测试，对错一目了然，所以训练进步快；安全分析和设计判断没有这种自动验证机制，进步就慢。一旦 Anthropic 在这些“半主观”任务的训练上取得突破，受益的就不只是软件工程，写作、科研等领域也会跟着受益。

他用 Amdahl 定律重新概括了这件事：在软件工程内部，那些“软的、主观的”能力，因为是当前的瓶颈段，反而会变得不成比例地重要。

## 【6】使命：在快速发布和负责任发布之间走钢丝

Ami 转向使命这个话题。Anthropic 体量在变大，整个行业的赌注也越来越高，外界最该了解 Anthropic 的到底是什么？

Daniela 给了两根支柱。

一根是“如何把这项有变革性的技术做好，让它对所有人都有益”。Claude 是一个工具，能放大人创造的野心和能力，这是机会的一面。

另一根是承认风险：劳动力被冲击的风险、技术发布是否安全、对人是否真的有益。

Daniela 说，Anthropic 想做的事，是把这两端“等量齐观”地处理。她引出了一个公司内部的文化关键词：“Hold light and shade”，光和影并举。

她举了刚发布不久的“Mythos 和 Glasswing”作为例子：

> Mythos 这种能力级别的模型，能用它做出的事情潜力巨大。但因为存在一些安全方面的脆弱点，我们想在发布上稍微小心一点。

她这样总结这种纠结：

> 我们这种平衡其实挺微妙的。我们想尽快把东西发出来、做最好的产品、发布最强的模型，但我们也想做得负责任一点。我们大多数决策的出发点，都是在这两个支柱之间来回校准。

> 注： Claude Mythos Preview 是 Anthropic 2026 年 4 月发布的预览版模型，在网络安全任务上展现了跨代能力，在多个主流操作系统和浏览器中发现了大量零日漏洞。Project Glasswing 是配套的防御安全联盟，联合数十家关键基础设施组织使用 Mythos 扫描和修复漏洞。正因为这些安全风险，Mythos 被限制在极小范围内发布。转录稿中的“Glassman”疑为“Glasswing”的语音识别错误。

## 【7】指数曲线下的产品观：为 AI 做产品 vs. 用 AI 做产品

谈到产品，Daniela 先调侃了一下 Ami。她说“你刚刚说我和 Dario 在产品上'leaned in a lot'，翻译成人话就是：你俩天天插手我业务，能不能让我安静干活”。

但她话锋一转，承认两人确实在产品上很较真，因为产品就是 Anthropic 想做的事的对外呈现。她还说了一个比较少听到的视角：在 Anthropic 内部，“产品”和“研究”是两条互相牵引的输入。有时候你会觉得“我们应该建一个更好用的工具”，但更多时候，“产品创新是被模型涌现出来的新能力推着走的”。

她举的例子是编程：Anthropic 一开始并没有从第一天就立志做一个编程产品。是某个时间点，团队发现模型已经能写出“还不错、不完美”的代码，又观察到很多深度用户本身就是开发者，自然萌生出“我们应该给这个群体做点什么”的念头，最后才有了 Claude Code。

Dario 接着把这个话题拆得更具体。他说有两件事要分开来看：在 AI 时代做产品（building products for AI）、用 AI 做产品（building products with AI）。

先说前者。他给出了 AI 时代做产品最关键的几条规律。

第一，AI 时代做产品的特点是技术底盘在飞速变化。2010 年代的产品时代，技术底图按部就班，偶尔有一个新框架。在 AI 时代，能力台阶每跨一档，原本死活做不出来的产品突然“亮起来”。所以内部要持续做实验，“哪怕这个东西现在做不出来，过几个月再回来试一次”。

他给了一个亲历的例子：

> 我们 2022 年其实试过类似 Claude Code 的东西。当时挺挫败的，理念是对的，但模型太傻，根本榨不出价值。我从 2015 年开始就在训练这些模型，他们是真的，是真的傻。
> （“If we had tried to do Claude Code in 2022, it wouldn't have worked because the models wouldn't have been strong enough...I've been training these models since 2015. They were really dumb.”）

第二，AI 时代里，产品的饱和点是被模型变得太强而推到的。Dario 说 chatbot 形态已经接近饱和，市场仍然很大，但模型继续变聪明，对 chatbot 形态的边际增益已经不明显。今天每一档新能力，更多体现在 Claude Code 这种 agentic（智能体）形态上。

第三，API 这个市场永远不会消失。因为新产品永远在出现，Anthropic 内部如此，外部更是如此。code 之外，写代码的人在做的医疗、法律、金融应用，每多一档模型能力就会多出一批新应用空间。

第四（也是回到 Amdahl 定律），用 AI 做产品时，他在公司内部观察到一个现象：发布速度被加速了 2 倍、4 倍、5 倍，但接下来“系统性的债”开始浮现。

> 用 AI 加速发布，是真的可以做到一年前做不到的产能；但你也会以惊人的速度积累技术债。然后你被迫问：能不能也用 AI 来还这些债，或者至少帮我们盯住债是什么？再然后你会发现，团队不得不用一种完全不同的方式协作。这些事每个月都会冒出新的认知。
> （“It's possible to accumulate an extraordinary amount of internal technical debt when you ship that fast. And so then you have to say, well, can we also use the AI models to undo that technical debt or keep track of what it is that we're doing?”）

也因此，AI 时代不只是发布节奏更快，“连'你怎么做事'本身都被迫高频升级”。

Ami 借这个话题加了一句自己的体感：问题本身是不会变得那么快的，人始终是人。但你必须保持“用新眼光看技术”，并且接受“你每天的工作内容也在变，因为瓶颈每隔一段就跳到新的地方”。

## 【8】未来六个月，最让 Dario 兴奋的能力

Ami 让 Dario 用一句话回答：未来六个月，模型能力上最让你兴奋的是什么？

Dario 给了个跨维度的答案：从“个人级 AI”跃迁到“组织级 AI”。

> 让我兴奋的是这个想法：AI 不只是替一个老板做完很多人的事，而是 AI 在一群人组成的组织里，把很多人的事重复做很多次。
> （“AI is not just doing the work of many people working for one person, but that it does the work of many people many times over by operating within an organization of humans.”）

他把这条线索和“一个人 10 亿美元公司”的赌局连了起来：那个赌局可能反而被低估了。真正会发生的更可能是“一群人加上 AI，把以前几百几千人的工作做完”，而不是“一个人独立创业撑起一个 10 亿”。

## 【9】最打动他们的 Claude 用例

最后 Ami 把话题切给 Daniela：让你最有触动的用户用例是哪些？

Daniela 举了几个反差极大的例子。

第一个是全球南方的移动医生项目。某些地区想见到一个真正的医生很难，要走几十英里土路才能到最近的城市。但当地人仍然有疾病和健康问题。开发者用 Claude 做出“问诊式”的接口，给出经过把关的医疗建议，把模型能力翻译成在低资源场景里能落地的工具。

她也提到了生物医学研究领域的加速，这是她一直关注的方向。

后面两个更私人。一位开发者用 Claude 把一段已经损坏的硬盘里的婚礼照片救了回来。还有一个人用 Claude 跟踪自家花园里番茄的生长情况。

Daniela 被番茄那个例子逗乐了：“我这辈子都不会想到这种用法。但是，你有摄像头直播吗？我想订阅。”

AI 能用来干什么这个问题，用户的想象力永远比产品经理的规划跑得快。

## 末尾 Q&A 速览

Q：今天 Anthropic 增长有多快？

第一季度按当季速度年化是 80 倍（Dario 用了“if you were to annualize it”的限定语，这是短期爆发外推的数字）。原本按 10 倍准备算力，所以一直在限速。

Q：SpaceX 算力交易解决了什么？

接下来一个月内会上线 300 MW、22 万张以上 NVIDIA GPU。Anthropic 会尽快把算力转化为更高的限额传给开发者。

Q：“一个人 10 亿美元的公司”赌局现在到哪了？

已经有两人 10 亿美元、单人数亿美元的案例（Dario 未给出具体名称，无法独立验证）。Dario 在 2025 年 Code with Claude 上给的时间窗是 2026 年，置信度 70%-80%。距离窗口结束还有七八个月。

Q：未来六个月模型能力上最让 Dario 兴奋的是什么？

组织级 AI。AI 不再只是替一个人做完很多人的事，而是在一个由人组成的组织里把这件事重复做很多次。

Q：Anthropic 在能力释放上是怎么做取舍的？

公司内部叫“光与影并举”。Mythos 模型因为安全风险没有公开发布，改用 Project Glasswing 限量发到数十家机构去做防御侧的强化。

## 最后

这场对话透出的核心看点，是 Anthropic 试图兼顾两种极端定位时，那种“左右互搏”的矛盾感。

一方面，它是增长最快的 AI 公司。80 倍年化增速（即使这个数字有选择性计算的成分），SpaceX 算力合作，Claude Code 让内部 PR 数量出现了向上拐点。Dario 在台上承认 80 倍扛不住，希望回到 10 倍，同一天就把全行业最难搞定的合作之一签了下来。这是“能找的算力我们都找了”的最强证据。

另一面，它又是最谨慎的 AI 公司。Mythos 这种跨代模型仅仅因为安全风险就被限制发布，“光与影并举（Hold light and shade）”成了反复提及的保命符。面对一个如此强大的模型，Anthropic 等于主动放弃了把它直接推向市场的速度。

要同时端平这两碗水，真实情况绝对比 Dario 和 Daniela 在台上说的难得多。80 倍增长意味着恐怖的交付压力，技术债“以惊人速度积累”可是 Dario 的原话。在这种推背感极强的速度下，还要踩刹车做安全评估、坚持负责任发布，靠的不仅是几句原则，更是每天资源排期里拳拳到肉的现实博弈。

Dario 关于 Amdahl 定律的反复引用，是整场对话的关键分析框架。它指向了一个比“AI 让一切变快”更实际的问题：加速之后，瓶颈会转移到哪里。对开发者来说，这个问题比“模型又变强了”更值得认真想。

两个值得持续追踪的信号：Colossus 1 上线后，限额是不是真的明显放宽，5 小时限额翻番但是周限额不变更像是文字游戏，Amazon、Google、Microsoft 那些动辄 GW 级的承诺到年底有多少能转化成用户可用的算力；Mythos 何时从预览版走出 Glasswing，在什么条件下走。前者考验 Anthropic 作为产品公司的基础设施能力，后者考验“光与影并举”这个原则在商业压力下能撑多久。

至于“一人 10 亿美元公司”的赌局，距离 2026 年结束还有七八个月。Dario 在台上已经在修正它：真正的命题可能是“一群人加上 AI 干以前几百人的活”。如果这个修正是对的，“一人独角兽”反而会成为这个故事里相对没意思的一部分。

原视频来源：Anthropic Code with Claude 旧金山场，2026 年 5 月 6 日，“A conversation with Dario Amodei & Daniela Amodei”。

See all posts

Built by 宝玉.  RSS . 本站原创内容，独家授权赛博禅心公众号发布。

Toggle theme