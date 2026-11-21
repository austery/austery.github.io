---
layout: post.njk
source: https://blog.qiaomu.ai/google-ai-power-game-neon-deepmind
web_feed:
  articleId: cmwo75u6500028yedieqjz127
  feedSourceId: cmoynk2ty0000yeud307bv9ji
  guid: https://blog.qiaomu.ai/google-ai-power-game-neon-deepmind
  sourceUrl: https://blog.qiaomu.ai/google-ai-power-game-neon-deepmind
speaker: 向阳乔木
title: 元素周期表上的权力游戏：谷歌 AI 帝国的裂变与重生 · 乔木博客
date: '2026-11-19'
summary: 谷歌在2026年发布了Gemini 4系列模型，以化学元素命名，引发了关于模型命名和能力排序的混乱。文章探讨了谷歌内部在DeepMind与Google Brain合并过程中出现的文化冲突、人才流失、模型发布延迟以及与军事合同相关的道德风暴。核心讨论了AI模型迭代、组织重组、产品追赶以及内部竞争的复杂局面，并以Gemini 4 Neon模型作为案例，展示了谷歌AI在技术发展与组织整合中的多重挑战。
area: tech-engineering
category: architecture
tags:
  - ai-application
  - tech-trends
  - software-development
  - deployment
  - debugging
people:
  - Koray Kavukcuoglu
  - Sundar Pichai
  - Sergey Brin
  - Jeff Dean
  - Noam Shazeer
  - John Jumper
companies_orgs:
  - Google
  - DeepMind
  - Alphabet
  - OpenAI
  - Anthropic
products_models:
  - Gemini 4 Neon
  - Argon
  - Carbon
  - Hydrogen
  - Neon
  - Gemini 3.5 Pro
  - Antigravity
media_books: []
draft: true
status: evergreen
---

元素周期表上的权力游戏：谷歌 AI 帝国的裂变与重生 · 乔木博客

乔木博客

全部

AI工具

AI教程

AI生成

AI资讯

健脑房

播客解读

论文学习

# 元素周期表上的权力游戏：谷歌 AI 帝国的裂变与重生

AI资讯

·

2026年11月19日

·

28 次阅读

·

约 35 分钟

© 2026

·

向阳乔木

一个土耳其航空工程师、一个国际象棋神童、一个 27 年老兵，和一张元素周期表。

这是 2026 年硅谷最戏剧性的权力交接故事。

## 一、一张元素周期表，藏着多少混乱

2026 年 11 月 18 日，谷歌发布了一个叫做 Gemini 4 Neon 的模型。

这是谷歌在不到两个月内推出的第四个 Gemini 4 系列模型——先是 Argon（10 月 13 日），再是 Carbon（11 月 10 日），然后是 Hydrogen（11 月 12 日），最后是 Neon（11 月 18 日）。四个模型，全部以化学元素命名。

开发者社区立刻炸锅了。

"谷歌到底是在命名模型，还是在重写化学课本？"一位用户在 X 上写道。另一位更直接："Argon、Carbon、Hydrogen、Krypton、Neon、Oxygen——他们雇了一张元素周期表来做产品经理吗？"

混乱不只是命名。Carbon 的原子序数是 6，Neon 是 10，Argon 是 18，Hydrogen 是 1——但在能力排序上，Carbon 是最强的旗舰，Neon 次之，Argon 再次，Hydrogen 最轻量。原子序数和模型能力之间毫无关联。The Register 的记者直接写道："谷歌显然意识到需要澄清模型排名，但他们的解释并没有真正解决问题。"

更荒诞的是，Neon 在 Artificial Analysis 智能指数上得了 61 分，反而比 Carbon 的 60 分还高——但谷歌仍然把 Carbon 定位为"最强旗舰"。Simon Willison 在博客里算了一笔账：Neon 定价每百万 token 输入 3 美元，而 Carbon 因为还在促销期，只要 2 美元——这意味着 Neon 发布的那一刻，它比"旗舰"Carbon 还贵。

这种混乱，不是偶然的产品失误。它是一家巨型公司内部长达数年的组织撕裂在产品层面的投影。

## 二、那个从航空工程转行的人

要理解 Gemini 4 Neon 为什么能做出来，必须先理解签署发布博客的那个人：Koray Kavukcuoglu，现任谷歌 DeepMind SVP 兼谷歌首席 AI 架构师。

他的履历有一种奇特的跨度感。1994 年，他在土耳其中东技术大学读航空工程学士，随后又读了航空工程硕士。然后，他转了方向，去纽约大学读计算机科学硕士，再读博士——导师是 Yann LeCun，深度学习三巨头之一，卷积神经网络的奠基人。

在 LeCun 门下，Kavukcuoglu 研究稀疏编码、卷积特征层级，以及如何让神经网络从图像中自动学习特征。他参与构建了早期的 Torch 机器学习库，帮助推动了硬件加速卷积网络的实现。这些工作在今天看来是基础设施级别的贡献，但在 2008 年前后，它们是真正的前沿。

2011 年，他加入 NEC 实验室做研究员。2012 年，他加入了一家刚刚在伦敦成立两年的小公司——DeepMind。那时候，DeepMind 还没有被谷歌收购，只是一个由国际象棋神童 Demis Hassabis 创立的、相信可以用神经网络实现通用人工智能的小团队。

2013 年，Kavukcuoglu 和 Volodymyr Mnih、David Silver 等人一起，写出了一篇改变 AI 历史的论文：《Playing Atari with Deep Reinforcement Learning》。他们用一个卷积神经网络，只输入原始像素，让 AI 自己学会玩 Atari 游戏——在七款游戏中，超越了此前所有方法，并在三款游戏中超越了人类专家。这篇论文在 2015 年以《Human-level control through deep reinforcement learning》的形式发表在 Nature 上，至今引用量超过 43,000 次。

这就是 DQN，深度强化学习的奠基之作。

2016 年，他又是 WaveNet 的核心作者之一。WaveNet 是一个逐样本生成原始音频波形的神经网络，人类听众评价其语音自然度远超当时最好的参数化和拼接式语音合成系统。经过蒸馏加速后，WaveNet 被部署进了 Google Assistant、Google Maps 导航、Google Voice Search 和 Cloud Text-to-Speech——每天被数亿人听到，却几乎没有人知道它的名字。

同年，他还是 AlphaGo 论文的共同作者。

这三件事——DQN、WaveNet、AlphaGo——构成了 DeepMind 早期最重要的三个里程碑。Kavukcuoglu 都在其中。

此后，他逐步走向管理：2018 年成为研究总监，2019 年成为研究副总裁，并在这个职位上创立了 DeepMind 的深度学习团队。2024 年 1 月，他成为 Google DeepMind 的 CTO。2025 年 6 月，Sundar Pichai 任命他为谷歌首席 AI 架构师，职责是"加速将世界领先的模型整合进谷歌产品"。

他还是 BYOL（Bootstrap Your Own Latent）、IMPALA、Spatial Transformer Networks 等重要论文的共同作者。他的 Google Scholar 页面显示 h-index 为 90，总引用量 34.9 万次。

这是一个从像素里训练出来的人。他理解模型，也理解工程，也理解产品。这种三位一体的能力，在 AI 领域极为罕见。

## 三、国际象棋神童与搜索引擎帝国的十年冷战

但在 Kavukcuoglu 走上前台之前，这家公司经历了一场旷日持久的内部战争。

2014 年，谷歌以约 5 亿美元收购 DeepMind。Hassabis 谈判时争取到了相当程度的自治权——DeepMind 可以保持独立的研究文化，不必完全服从谷歌的商业节奏。这个安排在最初几年运转良好：AlphaGo 赢了李世石，AlphaFold 预测了蛋白质结构，DeepMind 成为全球最受尊敬的 AI 研究机构之一。

但 ChatGPT 在 2022 年 11 月横空出世，一切都变了。

谷歌内部的紧迫感骤然升级。Pichai 需要的不是发表在 Nature 上的论文，而是能与 GPT-4 正面竞争的产品。2023 年 4 月，谷歌将 DeepMind 与 Google Brain 合并，成立 Google DeepMind，由 Hassabis 担任 CEO。

但合并本身就是一场文化冲突的开始。

Google Brain 是工程师文化：快速迭代，快速发布，以产品为导向。DeepMind 是学术文化：严谨验证，长期研究，以论文为导向。两种文化的人现在要共用同一个代码库、同一批计算资源、同一个发布日历。

据 Fortune 报道，三名现任和一名前任 DeepMind 工程师描述了内部的紧张气氛。计算资源的分配、发布审批的权力、谁的技术路线主导 Gemini 的训练——这些问题在每一次模型迭代中都会重新爆发。一名匿名工程师告诉 Fortune："合并本应简化我们的工作，但实际上我们花了更多时间在内部政治和调试合并后的代码库上，而不是训练模型。"

与此同时，DeepMind 和 Google Cloud 之间也存在长期摩擦。DeepMind 想快速把模型推向市场，以获得用户反馈；Cloud 需要稳定可靠的企业级产品，不愿意冒险。AI Studio 的开发曾经在 DeepMind 和 Cloud 之间来回拉锯，最终才被并入 DeepMind。NotebookLM 在发布前，Workspace 团队甚至试图将其扼杀，因为他们认为它会与 Google Docs 竞争。

Hassabis 本人，据 Sebastian Mallaby 2026 年出版的传记《The Infinity Machine》描述，与 Pichai 之间存在持续的张力。Pichai 希望 DeepMind 的能力更快地整合进谷歌的消费者和云产品；Hassabis 则认为这种速度在科学上是不负责任的。据 USA Business Times 援引知情人士的说法，Hassabis 曾强烈反对将一个未经充分测试的 DeepMind 推理模块整合进 Google Search，因为安全评估尚未完成。

"他建立 DeepMind 的理念是：要么做对，要么不做。谷歌是一家以快为建立基础的公司。"一名知情人士告诉 USA Business Times。

## 四、那个消失的模型

2026 年 5 月，在谷歌 I/O 大会上，Pichai 亲口宣布：Gemini 3.5 Pro 将在六月发布。

六月过去了，没有发布。

七月，Pichai 在财报电话会议上说："Gemini 3.5 Pro 目前正在测试中，我们的团队已经在构建下一代模型。"

八月，还是没有。

九月，DeepMind 官网上仍然写着"3.5 Pro coming soon"，这行字已经挂了数月。

据 Bloomberg 报道，延迟的核心原因是：编程能力没有达到内部预期，尤其是与 Anthropic 的 Claude 和 OpenAI 的模型相比，差距明显。据 Fortune 报道，内部有工程师直接指出，问题在于公司没有优先投入 AI 编程能力的资源——而这恰恰是 2026 年最关键的战场。

2026 年 10 月 1 日，谷歌告诉路透社：Gemini 3.5 Pro 不会发布了。

一个在 I/O 大会上被 CEO 亲口承诺的旗舰模型，就这样悄无声息地被放弃。它的位置，被 Gemini 4 Argon 取代。

这是谷歌 AI 历史上最尴尬的时刻之一。

## 五、六月的那一周

2026 年 6 月，在 Gemini 3.5 Pro 迟迟未能发布的同一个月，谷歌经历了它历史上最密集的人才流失周。

6 月 17 日，Noam Shazeer 宣布离开谷歌，加入 OpenAI。

Shazeer 是 Transformer 论文的共同作者之一，是现代大语言模型架构的奠基人。他曾在 2021 年离开谷歌，与 Daniel De Freitas 共同创立了 Character.AI。2024 年 8 月，谷歌以一笔据报道高达 27 亿美元的交易将他买回，作为 Gemini 的技术联合负责人。不到两年，他又走了——这次去了竞争对手 OpenAI。

几乎同一天，John Jumper 宣布加入 Anthropic。Jumper 是 AlphaFold 的共同发明人，与 Hassabis 一起获得了 2024 年诺贝尔化学奖。随后，AlphaFold 的另外两名核心研究员 Jonas Adler 和 Alexander Pritzel 也跟随 Jumper 去了 Anthropic。

据 Fortune 援引英国人才数据公司 Zeki 的数据：在过去 12 个月离开 DeepMind 的人中，25% 去了 Anthropic，21% 去了 Meta，14% 去了 OpenAI。DeepMind 在欧洲、中东和非洲地区的研究和高级工程人才招聘市场份额，从 2022-23 年的 49% 暴跌至 2025-26 年的 18.6%——这是 Zeki 记录的任何主要 AI 实验室在任何地区最大的市场份额跌幅。

DeepMind 的人才到达/离开比率，从 2023 年第二季度的约 12:1，跌至 2026 年第三季度的约 2:1。相比之下，Anthropic 的比率是 22:1。

## 六、8 月 5 日，那个改变一切的星期三

2026 年 8 月 5 日，谷歌发布了一则公告。

Demis Hassabis 将不再担任 Google DeepMind 的 CEO，转任 Google DeepMind 董事长兼 Alphabet 首席科学家，同时继续领导 Isomorphic Labs。

Koray Kavukcuoglu 将成为 Google DeepMind 的 SVP，直接向 Sundar Pichai 汇报，负责 Gemini 模型开发、前沿 AI 研究，以及 Gemini 应用和开发者团队。

Jeff Dean，谷歌第 30 号员工，在谷歌工作了 27 年的传奇人物，宣布离职，与 Sanjay Ghemawat、Oriol Vinyals、Quoc Le 共同创立 Discovery Loop。

这四个人的离开，是谷歌 AI 历史上最沉重的一次人才流失。Oriol Vinyals 在 X 上写道："十三年前，Jeff Dean 的一封邮件把我带到了谷歌。在 Brain、DeepMind 和 Google DeepMind 的难忘旅程之后，我要说再见了。"

Alphabet 股价当天下跌约 4-5%。

路透社的独家报道揭示了更多细节：Gemini 的多位项目负责人之间存在分歧，导致编程等关键领域获得的资源不足。一些向已离职高管汇报的团队，享有相当程度的自由去追求与 Gemini 训练无直接关系的研究——而这种自由，在新的架构下将不复存在。

8 月 6 日的全员大会上，Hassabis 和 Kavukcuoglu 告诉员工：一些非技术团队将从 DeepMind 迁移到谷歌的企业汇报结构中。这意味着 DeepMind 的自治空间，正在被进一步压缩。

一名知情人士告诉 The Verge："我在过去十年里从未见过谷歌内部有这么多围绕 AI 产品的内部竞争。"

## 七、军事合同与工会

就在这一切发生的同时，DeepMind 还在经历另一场风暴。

2026 年 4 月，谷歌与五角大楼签署协议，允许美国国防部在机密网络中使用 Gemini 模型，用于"任何合法的政府目的"。

超过 600 名谷歌员工签署了一封公开信，要求 Pichai 重新考虑。数名 DeepMind 研究员公开辞职，其中包括伦敦研究工程师 Sofia Liguori，她告诉 BBC："意识到我的公司正在越来越多地将 AI 系统推向军事行动，让我感到羞耻。"

2026 年 5 月，DeepMind 伦敦员工发起工会组建投票，98% 的 CWU 成员支持。这将是全球第一个前沿 AI 实验室的工会。

与此同时，Washington Post 披露，DeepMind 英国员工的劳动合同中包含终身禁止批评公司的条款——即使离职后也不能公开批评谷歌。员工在内部讨论中贴出了"1984"的表情包。

这场道德风暴，与模型延迟、人才流失、组织重组交织在一起，构成了 2026 年夏天谷歌 AI 部门最混乱的图景。

## 八、Sergey Brin 的备忘录

在这一切的背后，有一个人越来越频繁地出现在内部消息中：Sergey Brin，谷歌联合创始人。

据 The Information 报道，2026 年 4 月，Brin 向 DeepMind 的工程师和研究员发送了一份内部备忘录，措辞罕见地直接："为了赢得最后的冲刺，我们必须紧急弥合在 agentic 执行方面的差距，并将我们的模型变成代码的主要开发者。"

他还说，每一位 Gemini 工程师都必须被强制使用内部 AI 智能体来完成复杂的多步骤任务。

与此同时，谷歌组建了一支专门的"编程突击队"（coding strike team），由 DeepMind 研究工程师 Sebastian Borgeaud 领导，Kavukcuoglu 和 Brin 本人直接参与。目标只有一个：追上 Anthropic 的 Claude Code。

据 Bloomberg 报道，2026 年 4 月，谷歌内部有工程师更喜欢用 Anthropic 的 Claude Code 而不是谷歌自己的工具。这对于一家拥有全球最强 AI 研究团队的公司来说，是一种难以言说的讽刺。

Brin 在 2025 年 2 月就曾在备忘录中告诉 Gemini 员工："每周 60 小时是生产力的最佳点。"他正在以一种越来越像创业公司创始人的方式，介入这家他已经离开日常运营多年的公司。

## 九、Antigravity 的困境

谷歌的 AI 编程工具 Antigravity，是这场内部混乱最直接的产品体现。

它的概念是好的：一个以 AI 智能体为核心的 IDE，支持多智能体并行、Manager View 看板、原生浏览器调试、多模态输入。在某些维度上，它确实领先于竞争对手——比如原生的 Chrome 集成、比如 Antigravity 2.11.0 引入的生成式 UI。

但用户的反馈是残酷的。

在官方论坛上，一名付费 Ultra 用户（每月 250 美元）写道：他完成了不到 10 个任务——五个前端测试、三个内容创作测试、一个逆向工程测试——就耗尽了整个五小时配额，并消耗了 27% 的周配额。"这是 2026 年 10 月，它给我的 HTML 文件只是一个展开的 HTML 代码块，我必须自己复制？？？"

另一名用户在 2.6.0 更新后写道："谷歌刚刚用这次更新杀死了 Antigravity……新 UI 看起来像一盘混合水果，乱七八糟。"

权限提示疲劳、配额不透明、GitHub 认证在更新后断开、Settings 无法搜索、没有反馈按钮——这些问题在论坛上反复出现。

Gergely Orosz，知名开发者博主，直接说："谁在谷歌之外用它？"他指出 Antigravity 默认使用的是 Anthropic 的 Claude Sonnet 和 Opus 4.6，而不是谷歌自己的 Gemini 模型——"这对于谷歌的旗舰开发工具来说很奇怪。"

这种奇怪，有其深层原因。Gemini 在编程任务上的能力，在相当长的时间里确实落后于 Claude。谷歌不得不在自己的产品里用竞争对手的模型来维持竞争力。这是一种结构性的尴尬，不是产品团队能够独立解决的问题。

## 十、元素周期表的逻辑

回到那张元素周期表。

Gemini 4 的命名混乱，表面上是产品决策失误，深层是一个正在高速转型的组织的真实写照。

在不到两个月里发布四个模型，这本身是一种胜利——它证明了 Kavukcuoglu 接手后，谷歌的发布节奏确实在加速。Gemini 4 Argon 于 10 月 13 日发布，Carbon 于 11 月 10 日，Hydrogen 于 11 月 12 日，Neon 于 11 月 18 日。这种密度，在谷歌历史上前所未有。

Neon 的性能数据是真实的：在 Artificial Analysis 智能指数上得分 61，超过 Carbon 的 60；在 Vals Index 上排名第二（70.9%）；在 Artificial Analysis 编程智能体指数上排名第一（58.6）；在 Legal Research Bench、Tax Agent Bench、Zapier AutomationBench 上均排名第一。它比 Carbon 快三倍，成本低 60%，同时将幻觉率降至 DeepMind 内部测试的历史最低点。

这是一个真正强大的模型。

但它的命名让人困惑，它的定价在发布时比"旗舰"Carbon 还贵，它所在的产品 Antigravity 仍然充满 UX 问题，它的发布博客由一个三个月前才刚刚接手整个组织的人署名。

这就是 2026 年的谷歌 AI：模型越来越强，组织仍在愈合，产品仍在追赶，人才仍在流失，而那个从航空工程转行的土耳其人，正在用他在 LeCun 门下学到的第一性原理，试图把这一切拼在一起。

## 尾声：那个 27 年老兵的新公司

Jeff Dean 离开谷歌后，Discovery Loop 的估值在一个月内从 100 亿美元飙升至 500 亿美元。

他在斯坦福大学的一次演讲中说，他们已经有大约 20 个自动改进循环在运行——AI 智能体提出实验、执行实验、从结果中学习，然后决定下一步测试什么。

Alphabet 是 Discovery Loop 的创始投资人，并为其提供第一年的计算资源。

谷歌投资了那个离开谷歌的人，让他去做谷歌内部做不到的事情。

这或许是整个故事里最深刻的反转。

## 参考来源

Google Blog, "Introducing Gemini 4 Neon," Koray Kavukcuoglu, Nov 18, 2026 — blog.google

Google Cloud Docs, "Developer's guide to Gemini 4 Neon," docs.cloud.google.com

The Register, "Google continues model chemistry experiment with Neon," Nov 19, 2026 — theregister.com

VentureBeat, "Google launches Gemini 4 Neon with Opus 5.5-level coding performance," venturebeat.com

Interesting Engineering, "Gemini 4 Neon brings 3x faster performance to complex coding tasks," interestingengineering.com

CNBC, "Google DeepMind: Koray Kavukcuoglu takes over in frontier AI push," Aug 12, 2026 — cnbc.com

Reuters, "Exclusive: Inside the Google executive moves that led to its big AI reshuffle," Aug 12, 2026 — reuters.com

The Model Press, "Google DeepMind leadership change and Jeff Dean's exit," themodelpress.com

FourWeekMBA, "Kavukcuoglu Now Leads Gemini as Sole SVP Reporting to Pichai — With Brin Deeply Hands-On" — fourweekmba.com

Recatools, "Google DeepMind Reorganises: Kavukcuoglu Reports to Pichai" — recatools.com

GitHub, koraykavukcuoglu/koray-kavukcuoglu — github.com

Frontier Minds, "Koray Kavukcuoglu, Google DeepMind" — frontierminds.ai

Latent Space Wiki, "Koray" — latent.space

AIWiki, "Koray Kavukcuoglu" — aiwiki.ai

AlphaXiv, Koray Kavukcuoglu papers — alphaxiv.org

CitationMap, "koray kavukcuoglu — h-index 90, 349K citations" — citationmap.com

Mnih et al., "Playing Atari with Deep Reinforcement Learning," arXiv 2013

Mnih et al., "Human-level control through deep reinforcement learning," Nature 2015

van den Oord et al., "WaveNet: A Generative Model for Raw Audio," arXiv 2016

Silver et al., "Mastering the game of Go with deep neural networks and tree search," Nature 2016

Fortune, "How stalled models, missed deadlines, and staff burnout led to the unraveling of Google's DeepMind," Aug 10, 2026 — fortune.com

Fortune, "Google DeepMind is losing its grip on elite AI talent," Aug 27, 2026 — fortune.com

The Verge, "The messy politics behind Google's big AI shakeup" — theverge.com

Morning Star / MarketWatch, "A decade of internal AI battles is finally catching up to Google," Aug 15, 2026

USA Business Times, "Google's DeepMind Exodus: The AI Talent War Nobody Saw Coming" — usabusinesstimes.com

USA Business Times, "The Google DeepMind Exodus Nobody Is Supposed to Know About" — usabusinesstimes.com

Michael Parekh Substack, "AI: Google's internal AI competitions. RTZ #636" — michaelparekh.substack.com

Google Blog, "Building for our AI future," Apr 2024 — blog.google

Google Blog, "The next chapter of our AI momentum," Aug 5, 2026 — blog.google

FourWeekMBA, "Google DeepMind's Coding Strike Team Reorg" — fourweekmba.com

TechRadar, "'We must urgently bridge the gap': Google's Sergey Brin says Gemini is behind Claude" — techradar.com

Android Authority, "Google uses AI for half its code, and it's pushing for much more" — androidauthority.com

The Verge, "Sergey Brin said Google needs to catch up to Anthropic on AI coding agents" — theverge.com

CNBC, "Google Gemini co-lead Noam Shazeer leaves for OpenAI," Jun 18, 2026 — cnbc.com

Wired, "4 of Google's Top AI Brains Are Leaving—and Launching Their Own AI Startup" — wired.com

TechCrunch, "Jeff Dean and other top AI researchers are leaving Google to launch their own startup," Aug 5, 2026 — techcrunch.com

Jeff Dean on X, Aug 5, 2026 — x.com/JeffDean

Oriol Vinyals on X, Aug 5, 2026 — x.com/OriolVinyalsML

Business Insider, "Former Google chief scientist Jeff Dean is raising again for his new AI startup, seeking around a $50 billion valuation" — businessinsider.com

Fortune, "Google shipped four Gemini Flash models in 106 days. Yet its Gemini 3.5 Pro is still AWOL," Sep 3, 2026 — fortune.com

Mashable, "Where is Gemini 3.5 Pro? The case of the missing AI model" — mashable.com

Codersera, "Gemini 3.5 Pro Release Date: Cancelled (Oct 2026 Update)" — codersera.com

Fortune, "A new Google AI deal with the Pentagon has sparked employee backlash," May 4, 2026 — fortune.com

Fortune, "Google DeepMind workers vote to unionize over military AI contracts," May 5, 2026 — fortune.com

The Verge, "Google DeepMind workers are unionizing over AI military contracts" — theverge.com

The Intercept, "Google DeepMind Engineer Resigns in Protest of Pentagon Contract," Oct 21, 2026 — theintercept.com

BBC, "Google staff resign in backlash over its AI contracts with military" — bbc.co.uk

Washington Post, "Google researchers are fighting to tell the world what they know about AI," Nov 3, 2026 — washingtonpost.com

Google Antigravity Community Forum, multiple threads — discuss.ai.google.dev

Daily.dev, "Google's Antigravity launch convinced nobody, and Gemini isn't helping" — daily.dev

The Register, "Google is speedrunning the periodic table to name Gemini 4" — theregister.com

Simon Willison's Blog, "Releases" — simonwillison.net

Hacker News, "Gemini 4 Neon" discussion — news.ycombinator.com

BIT, "Google DeepMind: AlphaFold, Nobel Prize, and the Pivot" — bit.com

AIWiki, "Google DeepMind" — aiwiki.ai

DeepMind Strategy Chief joins Anthropic, Chosun Biz, Nov 17, 2026 — biz.chosun.com