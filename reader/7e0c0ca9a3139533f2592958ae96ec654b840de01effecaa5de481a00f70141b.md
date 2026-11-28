---
layout: post.njk
source: https://yage.ai/share/ai-news-weekly-boundaries-20260920.html
speaker: yage.ai
title: 这一周，AI 工程工具的四件实事
date: '2026-09-20'
summary: 本文综述了TypeSafe Jev、Slack Code、OpenAI Sponsored Agents及DeepSeek Harness四项AI工程工具更新。重点分析了Jev的概率校准机制、Slack Code的协同编码架构、Sponsored Agents的广告交互模式及Harness的进程隔离安全策略，并指出当前缺乏独立第三方实测数据，强调生产环境应用需等待更多验证信号。
area: tech-engineering
category: ai-application
tags:
  - ai-agent
  - code-execution
  - sponsored-agents
  - process-isolation
  - probability-calibration
people: []
companies_orgs:
  - typesafe
  - slack
  - openai
  - deepseek
products_models:
  - jev
  - slack-code
  - sponsored-agents
  - deepseek-harness
media_books: []
draft: true
status: evergreen
---

## 本周四件事

TypeSafe 本周上线了 Jev
云端接口，程序发一段文字过去，直接取回一排离散概率。Slack 八月发布的
Slack Code，把编程 agent 写代码的中间过程搬进专门的群聊频道。OpenAI 在
ChatGPT 测试 Sponsored
Agents，用户点击推广卡片，能跟出资品牌的定制机器人聊上几轮。DeepSeek
给执行框架 DeepSeek Harness
换了新版，把模型临时编写的代码扔进干净独立的后台进程，顺手补上会话续接与远程机器调度。

四款工具碰到的系统环节完全不同，彼此没有技术往来。成天泡在系统里的工程师关心的是每款工具把什么交给了谁、中间返回了什么、后续怎么接手跑起来，以及官方写在文档里的承诺，手里到底压着多少公开证据。在这几项变动里，最先让人看清数据交互落差的，就是把大模型当离散分类器来用的
Jev。

四项工具运行机制示意

## Jev：发一段文字过去，拿回一组概率

看具体场景时，可以直接参照 TypeSafe 在快速入门文档中列出的客服案例：系统收到一条客户留言：“Hi,
I’ve been trying to connect my Stripe account for 3 days and it keeps
failing. I’m losing sales. Please help ASAP.”（嗨，我尝试连接 Stripe
账户已经 3 天了，一直失败，正在丢订单，请尽快处理）。

常规做法要么让大模型生成安抚回复，要么通过提示词输出 JSON
分类；追求极低延迟时，则在本地标注数据训练小体积分类器。Jev
则不同：程序把这段留言放进 state
参数传过去，并在同一次请求中并发挂载三个预先写好的问题。

三个问题在同一次请求里并行打分：department
是单选题，候选限定在账单、技术、销售三项；frustration
是等级题；is_urgent 是是非题。Jev
返回的结果没有解释，只有数字组成的离散概率。最有信息量的是 department
这道题：technical 概率最高，置信度却偏低，因为 billing
选项分走了接近六分之一（0.159）的权重。第二选项包含真实内容，不是噪音。

这段分支逻辑能成立，前提是数字本身可信，而这恰恰是大语言模型原生给不了的。大模型的底层原理是
next token
prediction，输出的概率是文字接龙的似然，训练目标里没有针对判断正确与否的校准：模型报
0.3，实际把握可能接近 0.9。Jev
的核心主张是自家的数字经过了校准训练，能按阈值直接使用，调用方才在业务代码里做多层分流（教学示意）：

```
<code class="sourceCode typescript"><span id="cb1-1"><a href="#cb1-1" aria-hidden="true" tabindex="-1"></a><span class="co">// 教学示意代码：消费概率分布的业务分流</span></span>
<span id="cb1-2"><a href="#cb1-2" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> (result<span class="op">.</span><span class="at">department</span><span class="op">.</span><span class="at">confidence</span> <span class="op"><</span> <span class="fl">0.3</span>) {</span>
<span id="cb1-3"><a href="#cb1-3" aria-hidden="true" tabindex="-1"></a>  <span class="co">// 置信度过低，模型无法明确判断意图，转人工分诊</span></span>
<span id="cb1-4"><a href="#cb1-4" aria-hidden="true" tabindex="-1"></a>  <span class="cf">return</span> <span class="fu">routeToHumanAgent</span>(ticket)<span class="op">;</span></span>
<span id="cb1-5"><a href="#cb1-5" aria-hidden="true" tabindex="-1"></a>}</span>
<span id="cb1-6"><a href="#cb1-6" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1-7"><a href="#cb1-7" aria-hidden="true" tabindex="-1"></a><span class="co">// 置信度达标，主意图派单给得分最高的团队</span></span>
<span id="cb1-8"><a href="#cb1-8" aria-hidden="true" tabindex="-1"></a><span class="fu">assignTicketToTeam</span>(ticket<span class="op">,</span> result<span class="op">.</span><span class="at">department</span><span class="op">.</span><span class="at">choice</span>)<span class="op">;</span> <span class="co">// 分配给 technical</span></span>
<span id="cb1-9"><a href="#cb1-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb1-10"><a href="#cb1-10" aria-hidden="true" tabindex="-1"></a><span class="cf">if</span> (result<span class="op">.</span><span class="at">department</span><span class="op">.</span><span class="at">probabilities</span><span class="op">.</span><span class="at">billing</span> <span class="op">></span> <span class="fl">0.15</span>) {</span>
<span id="cb1-11"><a href="#cb1-11" aria-hidden="true" tabindex="-1"></a>  <span class="co">// 次高选项概率显著，反映了用户关于支付账户失败的陈述，抄送计费团队作为关注人</span></span>
<span id="cb1-12"><a href="#cb1-12" aria-hidden="true" tabindex="-1"></a>  <span class="fu">ccTicketToTeam</span>(ticket<span class="op">,</span> <span class="st">"billing"</span>)<span class="op">;</span></span>
<span id="cb1-13"><a href="#cb1-13" aria-hidden="true" tabindex="-1"></a>}</span></code>
```

这段代码里的第三层判断依赖完整的分布，但上一段说的校准问题在这里同样成立：0.159
这个权重能不能按字面意思用，取决于 Jev
的校准主张是否兑现。假如数字可信，完整分布确实能看见第二候选的真实分量，在主派单技术组之外把计费团队拉进关注人；假如数字不可信，分层逻辑就建立在流沙上。官方的零幻觉宣传只覆盖格式层，对校准没有提供任何独立验证，这正是后文实测部分要盯的重点。

按 TypeSafe 发布的官方博文与问题原语规范，Jev
整个系统只有三种问题原语：是非题、单选题与有序评分题，答案一律是概率分布；其中单选和评分附置信度，是非题没有独立置信度字段。每道题独立评估，互不共享上下文。因为没有上下文依赖，服务器可以同时把题目推给底层模型打分，网络往返时间很短；但也正因上下文切断，各个问题无法互相参考做联合推理，前面的故障严重程度不会帮它在分类时更倾向于判定为技术问题。

快和便宜有两个同日的第三方实测撑着。Every.to
的实测报告记录了一组数据：同一批文本判断，Jev 比常规对照模型快约 25
倍；但在测试者预埋的 7 个文本缺陷里，Jev 漏掉了 1 个，只抓到 6
个，对照的大语言模型则全部命中。测试者特意提醒：在准确率拿到生产验证之前，不要直接拿它替代复杂工作流。

来自 Good
Start Labs 的验证报告显示：Jev 与对照模型判定一致率为
91.5%，消耗的资金成本低了两个数量级。但评测方用粗体写了原话：Agreement
is the share of checks on which two judges gave the same verdict; it is
not accuracy，一致不等于正确。评测团队还抓到了一个反例：DeepSeek
的模型花多一点的钱，跑出来的一致率反而略高一些。账面上省下的开销多大，完全看工程师挑选谁当基线。

官方自己在单价上就没对齐。官方博客写着输入每百万 token 收费 0.042
美元、输出免费；开发文档的代码注释里，却还留着 7
月份写下的一套旧价格，数字明显高出一截。公开定价页面至今没有上线，外界无从查验当前的低价到底属于长期的技术优势，还是厂商自掏腰包补贴的阶段性亏损，厂商代表在
Hacker News 上也承认自己眼下无法自证这一点。

官方宣传的零幻觉在工程上分三层。第一层是格式合法，属于构造性保证：输出只落在给定选项内，不会越界，官方自认这是类型系统的硬性匹配，不是经验统计（Our
number is not empirical. Schema matching is
guaranteed）。第二层是选项正确，这里没有任何系统保证：TypeSafe
首席执行官在 Hacker News 承认模型完全可能自信地选错答案（it’s also
possible to be confidently
wrong），且参考答案只是两个前沿模型的平均输出，不是真实标签（evals.typesafe.ai）。第三层是置信度评分，它只反映整组样本在统计上的宏观性质，不担保单次调用的具体决策。

对于只需获取离散判断的后台流水线，这种把长篇文本压成概率的做法省去了繁琐的格式解析。但当
AI 不再躲在 API
背后算概率，而是走进日常协作的通讯工具、替工程师直接在项目代码库里写代码时，交互形态就从单向的数据请求，变成了需要多人围观的聊天现场。

## Slack Code：agent
干活搬进群聊频道

软件团队修一个代码缺陷，常常从群里的一条消息开始：测试或产品截了异常图发进群，随手艾特负责开发的
agent。但 agent
接活之后大家反而更累了。让它在群里干活，它会不停刷屏，一行行日志把人的讨论顶没了。让人接手，他就切到自己的终端里闷头改，改完往群里丢一个
PR
链接，其他人得点出去、在网页上翻半天才知道改了什么。交给流水线更省事，也只剩干等结果。

Slack 8 月 20 日发布的 Slack
Code 针对的就是这个别扭。现在在任何对话里唤出受支持的
agent，系统会自动开一个以该任务命名的新频道，官方叫 code
channel，一个任务一个频道。功能正在分批灰度，九月中旬的 Dreamforce
只是二次展示。

团队成员进入频道后，看到的不再是普通聊天文本，而是一个协同写代码的工作台：界面中央展示着行级代码变更对比，评审人员可以在具体代码行写下批注，这些修改意见能打包成一份完整的反馈提交给
agent；前端改动有内嵌 HTML 原型预览，改动效果直接渲染出来；此外还整合了
Canvas 文档、Block Kit 卡片与代码托管外链。频道顶部常驻状态指示器，显示
Working、Idle、Needs attention、Done、Inactive、Archived
六种状态，边上的红色 Stop 按钮允许任何有权限的成员随时叫停任务。

在底层架构上，Slack
平台本身不跑任何代码，既不在本地拉起容器，也不执行 git clone
拉取仓库，只负责组织协同消息并在聊天窗口渲染富文本界面。所有实质性的代码编写与环境测试，全部发生在第三方合作伙伴的云端：根据
GitHub
官方集成文档，GitHub Copilot
在安全云沙箱中异步完成修改并回传改动；Anthropic 的 Claude 通过 Claude
Tag 企业服务，在临时沙箱中克隆用户的 GitHub
仓库，完成编辑推回分支，会话闲置后销毁沙箱；Cognition 旗下的 Devin
运行在独立虚拟机上，Slack 频道实质是其 Web 工作台的实时镜像；Vercel
则在自身的云基础设施中运行，构建完成后把实时预览地址推回频道。这种模式把团队成员介入研发的时点向前推移了：过去大家只能在
agent 提交 PR
之后被动做滞后的代码审阅，现在能直接盯着写代码的中间过程，非技术人员能看着原型及早纠正需求偏差，资深工程师也能在糟糕的代码结构成型之前当场叫停。

不过，把多人在群聊里的公开围观引入代码修改，必然会直接撞上权限边界。四家接入方中，唯有
GitHub 在公开技术文档中明确了双层权限机制：在 Slack
频道里，任何参与讨论的成员都可以向 agent
提建议和输入自然语言指令；但是，只有对底层目标代码仓库拥有写权限的用户，才具备触发
Copilot 真正对代码库发起修改的资格。同时，Copilot
自动生成合并请求时使用的是 GitHub App
的机器人身份，如果代码仓库启用了分支保护规则
rulesets，由于机器人缺乏具体自然人的签署归属，默认策略要求在仓库原本要求的审批之外，额外增加一道独立的人工审批。至于
Slack 高管宣称的所有操作均代表用户并遵循其访问控制列表（Everything is
done on behalf of the user, using the user’s
ACLs），目前没有任何公开技术文档能证实这一说法。

在官方重点介绍的
sign-off（关键操作人工签署）机制上，具体执行细节也留着空白。Slack
宣称在面对把代码推向生产环境等高风险操作时，agent
会把改动成果停留在频道内等待专家审批确认。然而在现有公开文档中，这一流程仅停留在抽象的行为描述层面：到底由谁来定义高风险清单、系统里如何指派具体的审批人员、审批通过后是由
agent
自主推向生产还是必须由人工点击确认按钮，官方至今没有公布具体的配置规范或控制面文档。

在商业策略上，Slack 宣布 code channel
功能在所有计划类型中免费开放。平台选择免费提供消息管道和交互界面，把按
token 消耗与计算收费的商业模型，全部留给了第三方的 agent
供应商。产品公布 27
天以来，外部技术社区尚无任何实名团队公开发布过深度的使用复盘；Hacker
News 讨论主帖中找不到在真实生产环境跑通的反馈，科技媒体 The Next Web
则撰文公开批评，指出在消息嘈杂的群聊频道里随手回复一个大拇指表情，不能算作严肃的代码审阅（a
thumbs up in a busy channel is not a code
review）。而在发布会上早早列入合作名单的 ChatGPT
接入，在官方文档与开发者页面中目前仍处于即将推出的状态。

虽然 ChatGPT 还没正式跨进 Slack 的企业协作频道，但在 OpenAI
自己的产品主界面里，团队已经开始测试怎样把第三方的专属 agent
直接推到普通用户眼前了。只是这次推过来的角色变了：从帮工程师修 bug
的编程工具，换成各家商业品牌派来的销售代言人。

## Sponsored
Agents：广告点击之后是一段对话

2026 年 9 月 10 日，电商分析师 Juozas Kaziukėnas 在使用 ChatGPT
时记录下了一次真实交互。他在对话框里输入了一句日常的选购咨询：“i want to
buy the best picture frame with gold
leaves”（我想买带金箔的最佳相框）。在常规文本建议下方，界面弹出一张来自美国家居零售商
Wayfair 的赞助推广卡片，卡片右下角附带一个标有 “Chat with
us”（与我们交谈）的行动按钮。测试者点击该按钮后，界面没有跳出浏览器打开外部网页，直接在当前的
ChatGPT
主窗口内部，拉开了一段预填好初始提问的全新对话，其背后连接的实际上是品牌方预先配置好的一套定制聊天机器人。

六天之后，OpenAI 在官方网站发布了题为《Reimagining
advertising with AI》的公告，正式把这种形态定名为 Sponsored
Agents。官方帮助中心注明，这项能力目前仅面向美国本土一部分被选定的广告主开展小范围测试，不接受外部企业主动申请。官方在公告里勾勒的典型场景是：用户在向
ChatGPT
咨询完常规软装建议后，可以点击品牌卡片继续追问具体餐桌的长宽尺寸、适合容纳几人用餐，以及桌面涂层的日常打理方式。

这套流程总共分五个节点，各节点核验的证据并不一致。第一站是常规回答下方的广告卡片，OpenAI
在官方文档中明确承诺，广告模块独立于客观回答之外，并在视觉外观上保持清晰区隔。第二站是点击
CTA 按钮 Chat with
us，经媒体视频与分析师一手记录核验，站内直接拉起对话窗口。第三站是进入站内的品牌对话，交互对象从中立助手换成赞助商的品牌代言人。Hacker
News 用户 sigmar
逐帧比对官方演示视频发现，进入品牌对话后，原先卡片上醒目的 ad、sponsored
标识在画面中消失了，只剩下行尾一句颜色很淡的 “learn more about business
chats”（了解商业对话）提示文字，向下滚动后还会滑出视野之外（单源 demo
观察，非实际产品实测）。

随后的第四站是多轮深入追问，比如向品牌机器人询问餐桌耐磨度与尺寸匹配（教学补例示意，官方至今未公开过未经剪辑的完整真实问答实录）。最后一站是收尾跳转，产生购买意向后，agent
会把商家官方网站的外链发在对话框里，用户点击这个网址离开 ChatGPT
页面，前往商家的电商平台完成最后的付款结算与收货地址填写（官方文档确认）。

现有的公开资料里完全不存在站内直接付款或自主下单的机制。在对话界面内直接结算属于
OpenAI 与 Stripe 合作推进的另一条独立产品线 Instant
Checkout，这两条业务在目前的官方公告和技术文档中彼此完全独立，互不引用。

在法律合规与权责归属上，OpenAI 在 Ad Tools Terms 第 4
条 做出了明确的责任切分：即使 agent 由 OpenAI
代为编写提示词或配置上线，条款也强制把广告主认定为构建者（you are deemed
the builder of the Sponsored
Agent）。广告主对全部言论、交互逻辑和外部动作承担完整法律责任，相关索赔直接视同针对广告本身的诉讼。品牌方一旦试水这种营销格式，就必须独自吞下机器人可能信口开河的一切合规后果。

技术层面的开放程度同样有限。根据官方 Ads API
接口文档，虽然参数中定义了 business_agent
投放模式，但整套规范完全没有提供用于创建、修改或管理 agent 的开放 API
端点。说实话，在现阶段的封闭测试里，所有的品牌 agent 都是由 OpenAI
员工通过内部人工操作逐一配置上线的。从公开材料看，品牌方递交过去的大概率是一份静态的产品资料和问答物料（这一点属于推断），没有证据表明这些
agent 实时连接商家后端的库存数据库，或读取 CRM 里的用户资料。

在用户关心的隐私与数据边界方面，OpenAI
目前公开承诺：广告主只能拿到用户在赞助对话中直接发送的文字消息，以及经过脱敏汇总后的统计报告，广告主无权窥探用户此前与
ChatGPT
主助手的任何历史对话记录。但政策承诺与真正的工程隔离之间还横着未解的技术缺口：赞助对话是否会被长期保存在用户的个人历史会话列表中、对话沉淀下来的语料版权最终属于哪一方、两套问答系统在底层到底具备多大强度的物理隔离，官方文本均未做进一步说明。

至于商业收费方式，目前 ChatGPT 运行的常规广告主要依据
CPM（千次曝光展示）或者
CPC（单次点击）来进行后付费结算，官方文档明确写明，哪怕广告主选择了转化优化策略，计费节点依然停留在曝光或者点击上，并不按最终的下单结果收费。针对
Sponsored Agents
这款新产品，官方至今没有公布具体的计费细则，业内关于按对话轮次计费或按销售额分成的猜想目前没有任何公开证据可以证实。此外，公开可证实的试点广告主仅有
Angi 与 Wayfair
两家，双方在对外公告中均采用了前瞻性的试验措辞；此前报道过的 Best
Buy、Lowe’s 和 Adobe
等知名品牌属于普通的静态展示广告客户，并未加入这次的 agent
测试名单。

无论是给商家定制的销售机器人，还是各家平台在云端跑起来的智能助手，它们的大脑都装在厂商自己的云服务器里，所有数据都隔着一层
API
协议在云间传递。但当开发者回到本地电脑、想要让模型直接在本地文件系统里写脚本跑命令时，除了文本交互，还要在本地操作系统里给模型写出的代码套上一副结实的笼子。这正是
DeepSeek Harness 最新版集中处理的核心问题。

## DeepSeek
Harness：模型写的代码进了空环境进程

开发者在本地终端里敲下一行命令启动 DeepSeek Harness，简称
DSH。整个系统的底层分工是：DeepSeek
的大语言模型始终运行在云端数据中心里，只负责读取传入的上下文并完成语言推理，本身从来不会直接触碰本地磁盘或网络端口；真正负责在本地操作系统里创建文件、读取代码、解析工具参数并在本地终端中执行具体命令的，是一个跑在本地电脑上的
Node.js 协调程序，也就是业内常说的
harness（即专门负责在本地接收模型指令、组装参数并调用系统接口的执行线架）。在整个执行过程中产生的全部日志和上下文历史，也都会以
JSONL 文件的形式保存在本地工作目录中。

9 月 15 日，DeepSeek 团队为这个开源执行框架推送了新的预览版本 v0.1.6-alpha.1。这次更新对底层的执行机制动了大手术，新加入的自动化功能与破坏旧版本脚本兼容性的改动同时送到了开发者手中。

这次更新带来的第一项能力，是在无头模式下加入了会话接管功能。所谓的无头模式
headless，指的是框架不弹出任何交互式图形或终端界面、纯粹通过后台进程由外部脚本驱动的运行形态。在过去，外部自动化脚本每次唤起
DSH 都拿到一个全新的随机会话
ID，任务跑完进程立即退出，导致定时调度任务或 CI/CD
流水线没办法把后续指令送回之前的执行上下文里继续运行，此前大家只能依靠社区第三方编写的补丁（比如
dsh-resume-headless）来勉强修补。

新版本正式加入了会话接管参数：外部脚本可以指定上次的会话 ID
接着往下跑，后续任务直接通过标准输入（stdin）传入，框架把运行状态以逐行
JSON 事件流（NDJSON）实时吐给外部监控脚本。根据设计规范文档，接管采用严格的
adopt-only
策略（只认领既有会话，不顺手创建新会话）：如果系统在磁盘上找不到指定的会话
ID、工作目录对不上，或者该会话已被其他进程占用，框架一律报错退出，不允许拼写错误静默开启一段空白新会话，避免在流水线里产生不可控的脏状态。

第二项能力是引入了基于 SSH 的远程工作区。按照官方
SSH 子系统技术文档的定义，系统的安全与执行边界切分得十分清晰：DSH
的主调度程序、调用模型所需的 API
密钥以及所有的本地会话记录，依然留在开发者的本地主机上；然而，所有由任务触发的文件读写、代码检查和命令运行，则全部切到了一台通过
SSH 连接的远端 POSIX 服务器上。

远端机器上预先安装了一个带 SHA-256
摘要校验的辅助程序（helper），替本地调度器执行具体的文件操作与脚本指令。这个设计既没有把模型搬到远端，也不靠脆弱的网络文件系统（NFS）挂载；官方在设计规范中明确规定，只要底层的
SSH
连接意外中断，系统会当场报告失败，不会自动重连去重放那些可能执行到一半的指令。

本次版本最关键的运行时行为改变，发生在程序化工具调用（PTC，即
Programmatic Tool
Calling，允许模型直接编写可执行代码来批量调度本地工具的机制）的执行架构上。PTC
的设计初衷是不让模型在面对复杂任务时，逐次向客户端发起结构化的工具调用往返，而是让模型直接写出一小段
TypeScript
程序，在本地运行环境里一口气把批量操作跑完。下面的示意代码展示了这种思路：

```
<code class="sourceCode typescript"><span id="cb2-1"><a href="#cb2-1" aria-hidden="true" tabindex="-1"></a><span class="co">// 教学示意代码：模型编写的 PTC 程序一次性完成批量查询</span></span>
<span id="cb2-2"><a href="#cb2-2" aria-hidden="true" tabindex="-1"></a><span class="kw">const</span> keywords <span class="op">=</span> [<span class="st">'auth'</span><span class="op">,</span> <span class="st">'session'</span><span class="op">,</span> <span class="st">'token'</span><span class="op">,</span> <span class="st">'crypto'</span><span class="op">,</span> <span class="st">'permission'</span>]<span class="op">;</span></span>
<span id="cb2-3"><a href="#cb2-3" aria-hidden="true" tabindex="-1"></a><span class="kw">const</span> summary<span class="op">:</span> <span class="bu">Record</span><span class="op"><</span><span class="dt">string</span><span class="op">,</span> <span class="dt">number</span><span class="op">></span> <span class="op">=</span> {}<span class="op">;</span></span>
<span id="cb2-4"><a href="#cb2-4" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb2-5"><a href="#cb2-5" aria-hidden="true" tabindex="-1"></a><span class="cf">for</span> (<span class="kw">const</span> keyword <span class="kw">of</span> keywords) {</span>
<span id="cb2-6"><a href="#cb2-6" aria-hidden="true" tabindex="-1"></a>  <span class="kw">const</span> matches <span class="op">=</span> <span class="cf">await</span> tools<span class="op">.</span><span class="fu">search</span>({ query<span class="op">:</span> keyword<span class="op">,</span> limit<span class="op">:</span> <span class="dv">10</span> })<span class="op">;</span></span>
<span id="cb2-7"><a href="#cb2-7" aria-hidden="true" tabindex="-1"></a>  summary[keyword] <span class="op">=</span> matches<span class="op">.</span><span class="at">length</span><span class="op">;</span></span>
<span id="cb2-8"><a href="#cb2-8" aria-hidden="true" tabindex="-1"></a>}</span>
<span id="cb2-9"><a href="#cb2-9" aria-hidden="true" tabindex="-1"></a></span>
<span id="cb2-10"><a href="#cb2-10" aria-hidden="true" tabindex="-1"></a><span class="cf">return</span> summary<span class="op">;</span></span></code>
```

在这段代码里，五次检索在本地一次性跑完，检索过程中产生的长篇中间文本不需要每次都塞回对话历史，模型最终只接收处理好的统计结果。在
0.1.6 之前，这段脚本直接运行在 DSH 主进程内置的 worker
线程里；新版本则把这段代码的执行完全剥离了出来，专门在系统后台启动一个独立的
Node.js 子进程来跑。

比新建子进程更激进的改变，发生在这个子进程启动的瞬间：运行时主动清空了它的全部环境变量，只保留
PATH、TEMP 等六个最基础的系统键，把子进程内的 process.env
重置为了一个近乎空白的空对象（具体实现可查阅 process.ts
源码）。官方在发送给模型的执行说明中只有一句规则：process.env starts
empty。

官方在网络代理用户指南中说明了这项改动的根本原因：防止模型自己编写的代码通过遍历环境变量，直接读取到宿主机里包含账号密码、访问令牌等敏感信息的网络代理配置。安全约束收紧之后，随之而来的就是旧代码的兼容性问题。如果用户此前编写的自动化脚本依赖宿主机预先注入的环境变量来获取业务配置或鉴权
token，升级后子进程里的代码读到的是空对象，依赖这些变量的逻辑会随之失效。需要说明的是，环境变量清空严格局限在
Node.js PTC 子进程内部，DSH 主程序本身以及通过 Bash
工具调用的常规命令不受影响。

新增功能与运行断裂同源。为了在本地推行进程级沙箱隔离，官方移除了对
E2B 云沙箱后端的支持，将代码执行环境收拢在本地独立子进程与远程 SSH
体系这两条线上；依赖包名也从 code-runtime 系列整体更名为
ptc-runtime 系列（在代码调用中从
ctx.codeRuntime 变更为
ctx.ptcRuntime），首发版本不提供旧名兼容别名。在 npm
分流上，latest 标签仍停留在旧候选版，只有显式带上
alpha
标签才拉到新版。即便如此，社区生态里为了适配这次变更已经建起几十张迁移工单；而在试验性分组中，针对浏览器与桌面控制的新模块在发布首日就被开发者曝出多会话无法正常复用的缺陷（见
GitHub
Discussions 第 6789 号讨论）。

## 结尾：同一周，同一个验证缺口

这四款工具中，Slack Code
是八月首发、本周二次展示，其余三项是本周发布，但来自独立第三方的实测数据依然接近于零。Jev
仅有发布当天两家机构的简短验证，Slack Code
在真实开发团队里还没有公开的实测复盘，Sponsored Agents
只有一位分析师记录下了点击入口的实际界面，而 DSH
的新版本发布至今才刚过去不到两天。

对身处一线工程系统的开发者而言，厂商官方的说辞目前只能当作有待验证的技术假设来看待。要想弄清这些工具到底能不能放进生产环境，关键在于几组验证信号何时浮出水面：Jev
需要等待官方公布正式的公开定价页面并接受第三方针对真实业务准确率的检验，Slack
Code
要看最早在生产流程中引入它的工程团队能否写出扎实的运转复盘，Sponsored
Agents 还缺一份没有经过剪辑的完整问答全流程记录和透明的商业计费细则，而
DSH
则要观察外部生态插件的迁移进度以及那套清空了环境变量的独立子进程在长期高负载运行下的稳定性表现。只有当这些具体的使用记录和系统反馈陆续公开，各项工具在真实工程系统里的能力边界才会真正清楚起来。

## 材料

TypeSafe Jev 官宣博客：Introducing System One Models and Jev

TypeSafe Jev 问题原语技术规范：Primitives

Slack 官宣博客：Slack Code Channels for Agents

Slack Code 帮助中心指引：Build with AI as a team using Slack Code

GitHub 官方文档：Integrate Copilot cloud agent with Slack

OpenAI 公告：Reimagining advertising with AI

OpenAI 帮助中心：Sponsored Agents in ChatGPT Ads

OpenAI 广告工具条款：Ad Tools Terms §4 Sponsored Agents

DeepSeek Harness 发布记录：dsh-v0.1.6-alpha.1 Release

DeepSeek Harness 无头机器运行设计规范：Headless Machine-Readable Run Surface

DeepSeek Harness SSH 远程工作区技术文档：SSH Subsystem

DeepSeek Harness 网络代理与进程环境隔离指南：Network Proxy Guide