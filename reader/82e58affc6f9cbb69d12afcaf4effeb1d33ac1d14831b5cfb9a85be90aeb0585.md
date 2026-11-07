---
layout: post.njk
source: https://yage.ai/share/fable5-export-control-impact-20260702.html
speaker: yage.ai
title: |-
  定量分析：Fable 5 禁窗 18 天，Anthropic
  的蛋糕被谁吃掉了
date: '2026-07-02'
summary: 文章通过对 Fable 5 发布禁窗期间 Anthropic 的市场份额变化进行定量分析，揭示了竞争对手 GLM-5.2 在流量和社区情绪上的快速崛起。研究发现，尽管整体模型蛋糕在变大，但 Anthropic 的份额正在缩小，主要被 GLM 模型抢占。同时，文章还探讨了政策风险如何影响开发者社区的信任格局，以及新一代开源模型的迭代速度对行业生态的影响。
area: tech-engineering
category: ai-application
tags:
  - model
  - traffic-analysis
  - market-share
  - policy-risk
people: []
companies_orgs:
  - Anthropic
  - GLM
products_models:
  - Fable 5
  - GLM-5.2
media_books: []
draft: true
status: evergreen
---

2026 年 6 月 9 日，Anthropic 发布了 Fable 5，一个被社区称为”beast”的
Mythos-class 编码模型。三天后，商务部下达出口管制令，Fable 5
被迫全球下线。7 月 1 日全面解除，7 月 3 日恢复访问。Anthropic 在 18
天里经历了一个戏剧性的反转：先发布了世界上最强的编码模型，然后被自己国家的政府拔了网线。

这件事对 Anthropic
到底是好事还是坏事？直觉上有两种相反的判断。一种认为禁窗让 Fable 5
获得了全球曝光，政府替它盖章”这是真正的前沿”，解禁后需求会报复性反弹。另一种认为禁窗让竞争对手趁虚而入，开发者一旦迁移就不会回来。我们用半定量的方法做了两个角度的观察：客观角度通过
OpenRouter API 逐日拉取所有模型的 token 流量数据，主观角度追踪 HN 和
Reddit 上的社区情绪演变。两套信号指向同一个结论：蛋糕在变大，但
Anthropic 的份额在缩小，被 GLM 吃掉了。

## 蛋糕在变大，但 Anthropic
的份额在缩小

OpenRouter 上可追踪的模型有 446 个。我们把它们按厂商分组，用逐日 API
数据计算每周各厂商的 prompt token 总量和份额。

OpenRouter 的总流量在 6 月持续增长。6 月第一周（6/2-6/8）总量约
24T，第二周（6/9-6/15，Fable 5 发布周）跳到
29T，第三周（6/16-6/22，GLM-5.2 开源周）到
32T，第四周（6/23-6/29）持平在
32T。蛋糕确实在变大，但这不意味着所有厂商都在受益。

Anthropic 的份额在持续下降。6 月第一周占 19.1%，第二周升到
20.7%（Fable 5 发布带动），第三周降到 17.7%，第四周继续降到
17.6%。从峰值到低谷，两周内丢了 3.1 个百分点。

GLM 是最大的受益者。6 月前两周 GLM（主要是 GLM-5.1）在 OpenRouter
上只有约 1.2% 到 1.8% 的份额，几乎不被注意。第三周（GLM-5.2 发布周）跳到
7.7%，第四周维持在 7.4%。GLM 的份额在两周内翻了四倍，从边缘玩家变成
OpenRouter 上排名第四的厂商。

其他中国模型也在增长。Xiaomi 从 12.3% 升到 15.1%，DeepSeek 从 24.5%
先升后降到 22.1%。OpenAI 在 OpenRouter 上有小幅增长，从 3.4% 到
4.5%。Google 在下降，从 10.5% 到 7.3%。

关键结论是：Anthropic 流失的 3.1 个百分点，主要被 GLM 吃掉了。但 GLM
的增长（6.7pp）大于 Anthropic 的流失（3.1pp），说明 GLM
还从其他厂商那里也抢了份额，尤其是 DeepSeek 和 Google。蛋糕在变大，但
Anthropic 没有参与这场增长，它的绝对流量从第二周的 5.95T 降到第四周的
5.63T，在增长的市场里逆势缩水。

## 逐日数据暴露了一个诡异的中间态

周度数据告诉我们”谁吃了谁”，但把视角切换到逐日之后，出现了一个初看很难理解的现象，它揭示了迁移是怎么发生的。

GLM-5.1 是 GLM-5.2 的前代，在 6 月前半月日均流量只有
63B，已经是个快要被遗忘的老模型。禁令后的周末正常下降到 43B。但 6 月 16
日（周二）它突然冲到 231B，6 月 17 日冲到 345B，是基线的 4 到 5
倍。这两天 GLM-5.2 刚发布，流量还很小。GLM-5.1 的流量反而比 GLM-5.2
还高。然后 6 月 19 日 GLM-5.1 崩塌到 67B，之后稳定在 30B
水平，只有基线的一半。GLM-5.2 同时接管了每天 250-390B 的流量。

GLM-5.1、GLM-5.2 与 Fable 5 每日 prompt
token 流量：6/16 GLM-5.1 出现异常 spike，6/19 后被 GLM-5.2
替代

这个流量形状说明，GLM-5.1 在 GLM-5.2 发布当天先接住了一波流量，48
小时后被 GLM-5.2 替代。至于是 agent
工具链的自动降级路由，还是开发者手动尝试后切换，我们目前没有日志或开发者自述来区分这两种可能。能确认的是：替代发生在
48 小时内，GLM-5.1 的 spike 和崩塌与 GLM-5.2 的发布时间精确对应。

## HN 和 Reddit
上的情绪走了两条相反的弧线

网关流量震荡的背后，是开发者社区信任格局的位移。在 HN 和 Reddit
上，禁窗期间的情绪走了两条方向相反的弧线。

第一条是对政府的愤怒，6 月 12 日禁令下达当天达到峰值。HN 上 Anthropic
的禁令声明帖热度超过三天前的发布帖，官方在
X 上的声明拿到 1330 万次浏览。这时的 Anthropic
是受害者，社区对它的同情达到整个事件期间的最高点。但这条弧线从此开始下行，对政府的愤怒在两周内逐步递减。

第二条弧线是对 Anthropic 自身的信任崩塌，从 6 月 14 日开始升温，到 7
月 2 日超过了前者。转折点是一个在 HN
上拿到高赞的类比：假设有一家叫”末日装置公司”的企业，天天宣传自己的末日装置是最好的、最强大的，同时又说末日装置太危险了应该被监管。Meta
首席 AI 科学家 Yann LeCun 公开嘲讽：“对 AI
的恐惧宣传终于迎来了惩罚，自食其果。”（Business
Insider KOL 汇编）社区开始用”Feeble”来嘲讽预期中回归后被阉割的
Fable。

真正的转折在 7 月 1 日解禁当天。回归的 Fable 5
带着三个条件：编码和调试任务自动回退到 Opus 4.8、每周用量限制在 50%、7
月 7 日后转为 credits 计费。HN 上的反应是 bait and switch。当天 HN
上的重新部署帖只拿到
60 points 和 12 条评论，和两周前的万众瞩目形成残酷对比。到 7 月 2 日，对
Anthropic 商业策略的负面情绪已经超过了对政府的愤怒。

社区情绪双弧线：对政府的愤怒在 6/12
达峰后递减，对 Anthropic 的信任崩塌从 6/14 升温到 7/2
超过前者

## 竞品定位与总结

GLM-5.2 在这场替代潮中的角色，不只体现在 OpenRouter
的流量数据上。它在 16 天内从 HN 技术帖升级到了 Reuters、NYT、CNBC、ABC
News 的主流议程，这个叙事升级本身就是信号。

GLM-5.2 发布于 6 月 16 日，恰好在 Fable 5 被禁后一天。MIT
许可证，定价是 Fable 5 的十分之一。在 Semgrep 的独立安全测试中，GLM-5.2
的漏洞发现 F1 得分超过 Claude Code，这篇测试报告上了 HN 首页拿到 1099
points。Polylabs
给出的定位是：“如果不算 Fable，GLM-5.2 是目前最好的编码模型。”VentureBeat
报道它在多项长周期编码基准上击败了 GPT-5.5，成本只有六分之一。Cline 和
Kilo Code 在发布当天就完成了集成。

主流媒体在 16
天内形成了一个高度一致的叙事框架：美国自缚手脚，中国趁虚而入，开源模型逼近闭源。NYT
DealBook 把它放在面向资本市场决策者的栏目里而不是科技版，Reuters 在 Z.ai
北京总部采访后把 GLM-5.2 和 Fable 被禁写在同一句话里，David Sacks 在
All-In 播客上说”just a tick below Opus 4.8”，Marc Andreessen 说”first
Chinese AI model to match and often beat the American big lab”。Reuters
还引了 RAND 数据：DeepSeek R1 发布后两个月内，中国 LLM 全球市场份额从 3%
跳到 13%。（Reuters
6/25、Reuters
7/2）

GLM-5.2 vs Fable 5 vs GPT-5.6
定位矩阵：价格、编码能力、可用性、管制风险四维对比

但叙事升级到主流议程不等于生态锁定已经发生。HN
上的讨论比主流媒体更诚实。有开发者说用 GLM-5.2 一个周末花 $20完成了
matrix bot 和 Rust agent，“nothing felt off”。但也有人说 GLM-5.2 的推理
trace 像”anxiety disorder
患者的内心独白”，跑圈、自我怀疑、幻觉支线任务。一个被主流媒体忽略的技术细节是：GLM-5.2
的 per-token 价格低，但 token 消耗量约 42k，和 Opus 4.8 的 41k 相当，而
GPT-5.5 只需 16k。task-level 的成本优势没有 headline
价格差那么大。Reuters 第二篇里 Poe Zhao 的判断更接近实际：“partial
routing, not overnight replacement”，开发者会把 GLM-5.2
作为路由选项之一，而不是全面替换。

西方高端模型陷入了自我设限的困境。GPT-5.6 同样被政府要求限制发布（CNBC）。Sam
Altman 公开批评：“我不喜欢政府来挑选客户。”但 OpenAI 还是配合了。AI
benchmarker Chris 的判断浇了冷水：“GPT-5.6 will be an incremental/solid
improvement over GPT-5.5, not a Fable killer.”（ExplainX）OpenAI
技术员工 Ryan Brewer
的表态最能代表开发者共识：“如果美国政府继续这个方向，你最终只能在湾区几栋楼里接触到前沿智能。”社区没有把
GPT-5.6 视为 Fable 的替代品，而是视为同样被 gate
的另一个美国前沿模型。

其他竞品的替代能力有限。Sakana AI 推出 Fugu 模型，HN 上拿到 247
points，但它是 7B 参数的 coordinator LLM，技术体量和 Fable/Mythos
不在一个层级。中国 360 推出 Tulongfeng，创始人周鸿祎称之为”中国版
Mythos”（Reuters），但西方开发者社区的讨论集中在地缘层面，它没有进入
coding agent 工具链。

这次禁窗风波给全球产业留下了三层教训。

第一，多模型热备从降本手段变成了生存底线。TrueFoundry
的表述最精确：“当你依赖一个供应商的一个模型，你就接受了好几个你控制不了的失败模式。”OpenRouter
推出 Fusion
API 提供”一半价格达到 Fable 级别”的编排路线。

第二，政策风险正式超越技术指标，成为架构设计的首要变量。Cloud
Security Alliance 把事件定性为”监管 kill-switch
从理论变为操作事实”，建议企业采购流程加入出口管制合规审查。

第三，Forrester
判断，因为 Fable 5 存活仅 72
小时，企业集成尚未深化，直接存量损失有限。但 OpenRouter
的数据指向的是另一种损失：禁窗让 GLM-5.2
在禁令次日切入了一个它本来不在的位置，GLM 的份额从 1.8% 翻到 7.4%，而
Anthropic 从 20.7% 降到 17.6%。蛋糕在变大，但 Anthropic
是唯一没有参与增长的大厂。18
天的禁窗本身结束了，但蛋糕的切法已经变了。

## 这组数据的局限

OpenRouter 虽然是最大的开放 API
聚合平台，但它漏掉了所有第一方订阅流量。Anthropic 的 Claude.ai
订阅、OpenAI 的 ChatGPT Plus、Google 的 Gemini Advanced 都不走
OpenRouter，这部分数据我们拿不到。OpenRouter 捕捉的是开发者和 agent 的
API 调用层，不是消费者聊天层。

另外，我们观察到的是时间联系，不是因果联系。严谨地说，不是”GLM 吃掉了
Anthropic 的流量”。更准确的描述是：Fable 5
的发布和随后的禁令引发了市场关注，整体蛋糕在变大，变大的这部分主要被 GLM
接住了，同时 GLM
还蚕食了一些已有流量。这两件事在时间上高度重合，但因果链不是简单的”A
被禁所以 B 受益”。

这也不是一个完全公平的对比。Fable 5 的定价是 $10/$50，GLM-5.2 是
$0.93/$3，价差超过十倍。同样的预算在 GLM 上可以跑十倍的
token，流量数字自然更大。直接比 token 量会高估 GLM 的实际市场份额。

但综合以上，OpenRouter
的数据分析仍然是有意义的。它至少用比较扎实的方式提出了一个现象：GLM-5.2
相比于 GLM-5.1
是一个跃变，不论是从媒体报道还是从流量数据来看，它都有非常鲜明的进步，并且和前沿模型的差距在急剧缩小。

## 附录

### 厂商周度份额

厂商

6/2-6/8

6/9-6/15

6/16-6/22

6/23-6/29

Anthropic

19.1%

20.7%

17.7%

17.6%

GLM/Z.ai

1.2%

1.8%

7.7%

7.4%

DeepSeek

28.9%

24.5%

25.3%

22.1%

OpenAI

3.4%

2.9%

4.3%

4.5%

Google

10.5%

8.7%

7.7%

7.3%

Xiaomi

12.3%

14.3%

14.3%

15.1%

MiniMax

12.0%

15.6%

11.6%

11.3%

Tencent

13.6%

13.2%

11.3%

10.6%

### GLM-5.1 与 GLM-5.2 逐日
prompt tokens（B）

日期

星期

GLM-5.1

GLM-5.2

GLM 合计

备注

6/2-6/12

~63/天

0

~63/天

基线

6/13

Sat

41.9

0

41.9

周末

6/14

Sun

35.7

0

35.7

6/15

Mon

50.1

0

50.1

6/16

Tue

231.5

30.2

261.7

GLM-5.2 公布

6/17

Wed

345.5

254.8

600.3

GLM-5.2 开源

6/18

Thu

224.0

296.7

520.7

6/19

Fri

66.8

265.0

331.9

GLM-5.1 崩塌

6/20

Sat

30.8

202.8

233.5

6/22-6/30

~30/天

~300/天

~330/天

新稳态