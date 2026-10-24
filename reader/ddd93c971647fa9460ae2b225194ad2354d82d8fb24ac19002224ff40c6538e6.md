---
layout: post.njk
source: https://yage.ai/share/ai-news-digest-20260914.html
speaker: yage.ai
title: |-
  本周四条 AI 新闻：司法部站队 fair use、DeepSeek
  押注昇腾、OpenClaw 转向团队、员工对 AI 情绪转冷
date: '2026-09-11'
summary: 本文探讨了当前AI行业面临的四大核心张力：司法部对AI训练数据的版权立场、国产芯片在AI推理中的部署计划、开源Agent从个人助理向团队基础设施的演变，以及员工对AI带来的职业不安全感和情绪变化。文章分析了司法部对fair use的论证、DeepSeek在昇腾芯片上的推理部署策略，以及OpenClaw从个人助理到团队Agent OS的定位转变，并引用Glassdoor数据揭示了员工对AI的负面情绪和裁员风险。
area: tech-engineering
category: ai-application
tags:
  - ai-legal
  - chip-deployment
  - agent-os
  - work-related
people: []
companies_orgs:
  - OpenAI
  - DeepSeek
  - Huawei
products_models:
  - DeepSeek
  - OpenClaw
media_books: []
draft: true
status: evergreen
---

这周有几条新闻值得单独拿出来说。这四条没有统一主题，但都触碰到了 AI
行业此刻最真实的张力：训练数据到底算不算侵权、国产芯片能不能撑起推理规模、开源
Agent 能否变成团队基础设施、以及被 AI
波及的员工到底怎么想。四条各自成立，下面分开讲。

## 美国司法部正式站队：用版权作品训练
AI 属于 fair use

美国司法部在 AI 版权纠纷里明确表了态。9 月 1
日，它向纽约南区联邦法院提交了一份 Statement
of Interest（利益陈述书），在合并审理的 OpenAI 版权诉讼（In re
OpenAI，MDL No. 25-md-3143，主审法官 Sidney H.
Stein）中主张，把受版权保护的作品用于训练大模型不构成侵权，属于
transformative fair use。案件覆盖纽约时报 2023 年底对 OpenAI
与微软的起诉，以及并入同一程序的所有出版方与作者诉讼。

先把定性说清楚：这是一份依据 28 U.S.C. § 517
提交的政府法律立场文件，不是立法，也不是裁决，对法院没有约束力，Stein
法官可以采信也可以无视。它之所以重要，是因为行政分支正式把赌注押在了 AI
行业一边，这会成为后续所有同类诉讼和国会立法讨论的参照。

司法部的核心论证分三层。第一，把训练和输出拆开看：训练阶段整本书被复制但从未公开，输出阶段”often
if not always lack substantial
similarity”（经常（若非总是）与原作缺乏实质性相似），因此应分开用 fair
use 分析。第二，训练是”extraordinarily transformative”，援引 Google
Books 案 和 Google v. Oracle
的先例，并指出训练不会产出替代原作的文本，市场影响因子同样倾向 fair
use。第三是政策与国安框架，原文这样写：让美国发展强大 AI
产业变得困难的法律规则”threaten national security and give a competitive
advantage to foreign
adversaries”（会威胁国家安全，并给不受此类约束的国外对手以竞争优势）。

司法部主张把训练阶段与输出阶段分开分析：训练阶段整本复制但从不公开，输出阶段与原作缺乏实质性相似

司法部还直接攻击了自家版权局。它在陈述书中称，前版权登记官 Shira
Perlmutter 在 2025 年 5 月报告中拒绝给 AI 训练开 blanket fair
use，其判断”does not warrant
deference”（不值得遵从）、分析”threadbare”（单薄）。Perlmutter
在报告发布后不久被特朗普政府解职，目前正在挑战解职。司法部这份陈述书明确回避了一个问题：它不讨论训练盗版材料是否算
fair use。这意味着 Anthropic 今年 7 月获批的 $1.5B 和解（覆盖约 48
万本从盗版书库下载的图书）所指向的盗版语料合法性，仍悬而未决。

纽约时报立即拒绝。《Politico》记录其发言人
Graham James 的回应：政府站队”a handful of trillion-dollar AI
companies”（一小撮万亿美元 AI 公司），损害”countless American creators
whose work they
stole”（作品被窃取的无数创作者）。到目前为止，仍没有任何上诉法院对 AI
训练 fair use 做出实质裁决，第一个巡回法院的判决才会真正定调。

## DeepSeek
计划部署 16 万颗华为昇腾芯片，但只做推理

据 Bloomberg
9 月 4 日报道（基于匿名知情人士），DeepSeek 计划在其内蒙古乌兰察布约
1 GW 规模的数据中心部署至少 16 万颗华为下一代昇腾 950DT
芯片。这是目前已知最大的昇腾单一集群，规模接近 xAI Colossus 一期（约 20
万 GPU）的 80%。

先给足限定：这是 Bloomberg 单一信源，DeepSeek
与华为双方至今都未回应或官宣，Reuters、FT、财新也还没有第二家一线信源跟进。因此它是一份”计划”，不是既成事实。TechTimes
按市场价每颗约 ¥111,000 推算订单面值约 ¥177.6 亿（约
$2.64B），但这是推算价，不是合同披露价。

最关键的事实是用途：这批芯片只用于推理，不用于训练。DeepSeek
训练下一代模型仍依赖英伟达硬件。彭博此前的报道指出，DeepSeek
在昇腾上的训练尝试多次失败后已切回英伟达。按这一计划，国内芯片将承担商业变现层（API
推理），但核心研发层（训练）的依赖没有改变。这正好呼应 DeepSeek
创始人梁文锋在 2026 年 7 月一份泄露的投资者电话里的评估：“four Huawei
GPUs equal one Nvidia GPU, and it’s two years behind”（4 颗华为 GPU 等效
1 颗英伟达 GPU，落后两年，Hello
China Tech 收录的泄露电话记录）。

DeepSeek
的国产替代只覆盖推理层：推理用昇腾 950DT，训练仍依赖英伟达

交付是硬约束。昇腾 950DT 采用华为自研的 144GB HiZQ 2.0
HBM，而高端存储短缺让华为今年的 950DT
产量被限制在”几十万颗量级的低端”，还要平衡其他客户。彭博据此称，完成这笔订单可能需要一年以上，部分产能希望
2027 年底或 2028 年初投运。国产 HBM 的爬坡速度（长鑫 CXMT 的 HBM3E
目前仍是 risk production）直接决定华为能否按时交付。另外，DeepSeek
同期正在洽谈数十亿美元融资以扩充基础设施。

## OpenClaw
2.0：从个人助理转向团队 Agent OS

开源 Agent 平台 OpenClaw 发布了 2.0 版本（即 v2026.8.1，官方 blog +
GitHub
release）。这是项目史上最大单次发布：16,000+ PR、933 名贡献者（其中
569 人是首次贡献）；据第三方统计，它约占项目历史全部合并 PR 的一半。9
月初实测仓库约 389k stars。

三个 headline 特性。一是简化安装：onboarding 会检测已有的
ChatGPT/Claude 订阅、API key 和本地模型，先验证连通性再保存，甚至能导入
Claude Code、Codex、Hermes 的记忆。二是重写的浏览器 Control
UI，性能有提升。三是 multiplayer，即 shared cloud sessions，支持
view/suggest/contribute
三级权限分级。官方称这源于团队自举需求：他们自己开发 2.0
时想拉同事进同一个工作会话，发现 OpenClaw 之前做不到。

这条消息的重点在定位转变，不在功能本身：2.0 把 OpenClaw 从”个人 AI
助理”推向”团队协作基础设施”。伴随而来的是权限与信任问题。项目在 v2026.9.2（9
月发布的
fast-follow）的升级说明里直接给出警告：当相关设置被省略时，“agents with
session tools can now read and search other agents’ conversations,
including other users’ transcripts”（带会话工具的 agent
现在可以读取并搜索其他 agent
的对话，包括其他用户的记录），要求管理员设置显式可见性和 agent
限制，互不信任的用户需要独立 Gateway。这坐实了 The Register
等第三方对共享会话权限边界的质疑：多人共享一个带
shell、邮箱和浏览器权限的
agent，一次误操作的爆炸半径远大于单人使用。

社区反应同样值得留意。升级路径仍然半生不熟，r/openclaw 里一边倒建议
clean install 而非 upgrade，v2026.9.2
发布后仍有用户报告升级卡死。此外许可证仍存疑：GitHub API 返回
NOASSERTION，而多数媒体写的是 MIT。

## 员工对 AI
的情绪在雇主评价里转向负面

雇主评价数据给出了一组直观的信号。Glassdoor 经济研究团队 8 月 27
日发布报告 《How
workers feel about AI in
2026》，分析了美国全职与兼职雇员的雇主评价。核心数字：AI 提及量 2026
年 5 月同比上升 240%；提及 AI 的评价中，正面比例从 2019 年的 81% 降到
2026 年的 43%，负面占 53%。

Glassdoor 数据显示员工对 AI 的正面情绪从
2019 年的 81% 降到 2026 年的 43%，且提及 AI
为负面者提到裁员的概率是基准的 6 倍

情绪和裁员、倦怠高度相关。在”cons”里提到 AI
的雇员，提及裁员的可能性是基准的 6.0 倍，提及倦怠或职业不安全感是 3.7
倍；25% 在 cons 提 AI 的评价同时提到裁员。职业分化很极端：保险理赔员对
AI 的负面率达 98%，作家、记者、会计、客服、设计师、IT
也高度负面；反之公司领导层最正面（67% 的 AI 提及落在
pros）。科技行业提及 AI 的频率是基准的 3.6 倍，但没有一个行业的 AI
评价是整体正面的，最正面的法律行业也只有 50%。

需要说明方法：这份报告不是问卷调查，而是评价文本分析。被标记为 AI
提及的标准是文本含 AI、LLM(s)、GPT(s)、Artificial Intelligence 或 OpenAI
等独立词，按”pros/cons”分区判断正负，是描述性相关而非因果结论。

它和”裁员后回聘”的叙事正好形成互补。匹兹堡大学教授 Mark Ma 等在 The
Conversation 的研究（基于数百万条 Glassdoor 评价与约 10,000
份财报电话记录）提出机制解释：AI
驱动的裁员和由此产生的职业不安全感正在”actively destroying the very
conditions needed for AI to make workers more efficient”（主动破坏让 AI
提升效率所需的条件），而管理层在财报电话中的乐观言论与实际生产力无关。对做
AI
产品的人来说，这份数据提醒的是：工具被采用的速度，受制于使用它的人对它的恐惧，而不只是工具本身的效果。