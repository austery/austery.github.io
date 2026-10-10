---
author: AI Engineer
date: '2026-07-23'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=u1yaOeEX4e8
speaker: AI Engineer
tags:
  - anomaly-detection
  - api-monitoring
  - drift-detection
  - execution-graph
  - telemetry
title: 基于学习型执行图的 API 异常与漂移检测系统
summary: 本文详细介绍了摩根大通在 API 监控领域引入的“学习型执行图”技术。通过将请求处理流程建模为有向无环图，系统能够利用 OpenTelemetry 和 Kafka 构建实时监控与流式评估管道，自动检测结构漂移、协变量漂移及概念漂移，实现低延迟的 API 异常诊断与自动化恢复。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Ritvik Pandya
companies_orgs:
  - J.P. Morgan
products_models:
  - OpenTelemetry
  - Kafka
  - Neo4j
media_books: []
status: evergreen
---
### 执行图：API 调用的 DAG 建模

在大型微服务架构与实时支付系统中，准确监控 API 调用链路的健康状况至关重要。为了实现这一目标，**摩根大通**（J.P. Morgan）支付团队的负责人 **Ritvik Pandya** 提出了一种基于**执行图**（Execution Graph: 用于在运行时表征单个请求执行路径的瞬态图）的方法。通常在讨论图技术时，业界习惯使用 Neo4j 等产品来构建持久化图（Persistence Graph）或属性图（Property Graph）并进行复杂查询。然而，本方案所采用的执行图是一种生命周期极短的瞬态图。

其核心思想是将整个请求的处理流程 holistically（整体地）表示为一个**有向无环图**（Directed Acyclic Graph: 简称 DAG）。通过这种建模方式，系统可以直观地确定服务的执行顺序，并在每个节点处捕获上下文信息并将其传递给下一个节点，从而极大简化了请求处理流程的追踪。在典型的 API 边缘层（例如 Ingress 接收请求、网关进行身份验证与鉴权、编排层并发调用下游系统，并最终通知客户端）中，任何重试、循环或分支都会作为独立的实体完整记录在执行图中。

<details>
<summary>Original English Source</summary>
Hi. Uh thanks thanks and uh hope everyone is out of uh the lunch coma and we'll survive this talk. So uh yeah myself Ritik I uh lead the payments team in uh JP Morgan and uh today I'll be talking about learn execution graphs how these graphs can help to uh detect any anomaly and drifts also how we can automate few things around that and uh you know u uh you know at the same time if we can reduce the manual you know detection work and uh going on that side uh so whenever we hear about graph uh there are persistence graph and property graphs uh which Neo4j and you know other products uh we use for them we query those uh graphs and get the answers out of it what I'm talking about today is execution graph. It's short-lived graph. Uh and idea here is holistically try to identify how the request processing happens and if there is any deviation on that and how to detect that and how to fix that. So here is a simple example. Uh say we have set of applications. uh you have one edge layer uh the first layer where you know request comes in and then uh you have some gateways uh if k is there you have ingress layer on top of it then authentication authorization happens after that there is some orchestration layer and uh few other systems which could be called in parallel uh once everything is done you are notifying your client that what's the update on that request right So here the idea is representing the uh overall request processing as DAG and using tag simplifies most of the things here. now you know that uh in what order service execution will be happening right so that's one of the thing the other thing is uh you know the context that in at what node what context will be there and what will be passed to the next node uh in that way it will be very um u ordered and simplified u uh simply can be represented uh there are few other uh use cases could be uh in terms of retries and uh the loops etc. uh the idea here is every loop uh to put in the graph as a separate entity itself. So uh in that way it could be tracked uh easily.
</details>

---

### 分层校验：平衡资源与精度的异常检测

在明确了执行图的基础建模后，如何构建一个既高效又节省系统资源的异常检测机制成为关键。为了实现这一目标，系统引入了类似于机场安检的**分层校验机制**（Tiered Check Mechanism）。

在这种机制下，系统被分为两层校验。**第一层校验**（Tier 1 Check）是一种轻量级、低成本的快速检查，类似于机场安检人员在旅客进入通道前只看一眼登机牌。系统会对比请求的端到端执行时间基线（Baseline），如果各项指标在基线范围内表现良好，则直接放行，无需将请求送入**第二层校验**（Tier 2 Check）。这种设计避免了对所有请求进行无差别的全量深度分析，从而大幅降低了系统资源开销。只有当第一层校验发现端到端的执行时间出现明显延迟（Delay）时，系统才会触发第二层校验，开始深入定位是哪些节点引发了漂移或异常，并计算具体的偏离程度。

<details>
<summary>Original English Source</summary>
how we can make this system uh more uh uh reliable at the same time not using uh most of the resources right so in the tier one check or it's your first check it's like uh going to airport and you you you know it's just boarding pass is some someone is looking at the boarding pass and let you go so uh now if you know the baseline of your request execution end to end if uh everything looks Good. You don't need to go to the tier two uh or next tier of check. Right? Once if you find that there is some delay. So now you need to check that what changed here. One of the uh the drift here could be because of the structural change. So if any new node or new step added which you are not aware of that could be one of the thing or one of the step which is removed that could be the another reason right. Uh once you know about that then further uh further analysis could be done uh in terms of scale deviations uh divergence and uh exponential ma uh so in simpler terms if you know that client A's request is taking this much time normally and uh client B's request could take might take more time than the client A um because of say one client is local to you and one client is uh you know the request is coming from outside and uh there are a few more checks needs to be done. So in in that case the baseline will change client to client and now you know that uh what your threshold it and uh how you can u reduce the noise of such alerts.
</details>

---

### 漂移分类：定位系统性能退化的根源

一旦进入第二层深度分析，系统必须准确对检测到的异常进行归类。根据 Ritvik Pandya 的经验，生产环境中的性能退化通常源于以下几种不同类型的**漂移**（Drift: 系统运行特征或数据分布随时间发生的偏移）：

* **结构漂移**（Structural Drift: 调用链拓扑结构发生改变）：例如在执行图中新增或删除了某个步骤。这里有一个买咖啡的类比：某天你常去的咖啡店在结账时突然开始询问你是否是会员，因为新增了这个“询问会员身份”的物理步骤，导致你买咖啡的整体时间变长。类似地，如果 API 中添加了新的鉴权节点，系统必须将这一新节点纳入基线评估并生成新的告警阈值。
* **规模偏离/容量漂移**（Scale Deviation: 吞吐量或资源饱和引起的延迟）：由于系统请求量暴增，导致某个微服务不堪重负，耗时显著增加。对此，系统需要采取实例扩容（Scale up）或将其改造为**异步调用**（Asynchronous Call）等手段进行优化。
* **协变量漂移**（Covariate Drift: 输入数据分布的改变）：例如系统刚上线时，60% 的请求来自本地，40% 来自海外；随着产品走红，海外请求占比大幅提升。虽然系统架构没变，但因为海外请求需要经过外汇汇率系统（FX Rate System）以及更多网络节点，其基础执行时间天然高于本地请求。此时，系统必须以客户端为维度进行精细化基线划分，避免由于请求来源比例改变而引发误报。
* **概念漂移**（Concept Drift）：针对完全相同的 API 请求，系统在相隔较长时间后表现出了完全不同的处理行为。

为了训练并验证这套分类系统，研发团队利用 **OpenTelemetry** 监控工具和 Starbench 测试套件，在 7 天的测试周期中注入了数百万条调用链路追踪（Traces），通过主动注入异常（Anomaly Injection）来训练算法模型，确保系统在生产环境上线前就具备了敏锐的漂移识别能力。

<details>
<summary>Original English Source</summary>
So here the idea is very simple. First you uh represent the entire request processing as DAG. You come up with the baseline. You find out the deviation and then you try to find out where exactly the issue is. Once you localize that then you compare that based on your system that whether it is uh within the threshold or not. If it is within the threshold yeah you don't need to u you know do the alerts or automate anything but if it is out of the threshold then certain action needs to be taken. Uh coming back to our example here say overall uh request processing from all the different nodes within our system uh is happening but somehow the foreign transaction uh rate service is taking more time than the usual. Now if you represented this whole uh request processing in multiple nodes you know where the problem is or where the issue is and correspondingly you will uh you know now you can uh exactly know where the problem is. So you can solve it uh that what how to uh how FX system or what all different uh cases were there in the past where FX FX rate system was failing. Here is one of the example uh for benchmark uh open telemetry and that star bench were used and say for 7 days of the time millions of uh traces were um you know injected or uh in the system then you inject the problem or uh anomaly there and based on that you train your system before anything goes on live. So uh again uh basic thing here is what is anomaly and what is drift right? So say you are driving from your home to office every day and uh one of and usually it takes 1 hour but uh one fine day it took you more time than 1 hour. Uh the reason might be some traffic or you know um car accident or anything. But uh he this is one of the incidents and uh based on your system and criticality of your system uh you can decide how to address that. The other part is one fine day you are uh taking sip of coffee around 4 p.m. and realized that a year back it used to take one hour for you from your home to office but nowadays it it is taking 20 more minutes right so what happened in Bay Area in number of carc so this is over the time what you are seeing is pattern changed and that's where you might need to come up with uh the new baseline itself so uh that's that's the drift that over the time you start seeing some delays or you know some uh performance deviation then once you know that there is a drift uh you can further categorize it first category is structural uh so say you somehow in the system a new node is added or one of the node is removed as I mentioned earlier for example you like uh again you know there is a shop where you like uh drinking coffee and uh one fine day they are ask start asking you about membership so they added one more uh step in it now every day they might ask you for hey do you have membership with us if you have then there is there are a special discount for you if you don't have membership then the regular prices will be there so in that way uh you know same way in our service processing or a request processing if new node is added that means uh Now you need to consider that step also in your old baselines and new alerts. The other one is uh say because of the volume of request uh one of your service is taking more time or it's not you know u cannot serve the request or the volume which you are expecting now over the time. So yeah, such kind of drifts you might need to treat differently because now you need either you need to scale up those services or instances of those services and or you need to either make it asynchronous call or based on based on the use case you know what whatever uh works there uh co-variate is a different uh one of the category say when you started the business uh you were seeing around 60% of local request but uh and 40% uh request from you know out of the country and that's where you might need to change the currency or you know one extra step is there so you now you know that what is the baseline for your uh request in US dollar but uh what is the baseline for uh any of the other currency over the time what happens is your product is so popular that you started getting more uh request from the outside. So nothing changed. Your system is working fine, right? But now you need to come up with the criteria and reassess your baselines again. Sorry here where uh either you need to come up with two different uh you know uh graphs to compare that one is for local and one is for um outside uh request from outside or what you can do is you can increase your uh average request time baseline. So once you know the pattern uh you know the solution. So uh that's where you need to categorize uh this drifts. One category could be for the same request uh now you are seeing the different behavior itself. Then probably if and when it's needed you might need to roll back such uh changes or either you need to reconsider that. So where I'm going with this is in that way you need to re-evaluate and reassess your system before uh identifying that what action needs to be taken. This whole talk is mostly about statistical uh uh you know part of uh the solution. uh it's it's uh part of bigger neuro uh specific uh uh um algorithms and system in a way but this is just one of the module which uh I'm talking about here now so once you know the drift or deviation
</details>

---

### 流式处理：异常定位与工程落地

在检测到偏差与漂移之后，系统需要通过高效的工程架构来实现实时的根因分析与处置。整个数据管道的流转过程如下：

各系统服务节点将监控数据异步发送给 **OpenTelemetry**。随后利用 **Kafka** 消息队列进行数据缓冲，并基于分布式流处理技术进行实时的数据流评估。针对检测到的不同类型漂移，系统设计了双通道处理路径：
1. **热路径**（Hot Path）：用于执行快速决策和自动化恢复策略，例如自动对资源饱和的微服务进行弹性伸缩或调整路由。
2. **重构路径**（Reconciliation Path / Cold Path）：耗时较长但计算更为精确，用于系统对全局基线进行校准。

```mermaid
graph TD
    A[服务节点 Services] -->|异步数据流 Asynchronous Telemetry| B(OpenTelemetry)
    B --> C(Kafka 消息队列)
    C --> D{流式评估 Stream Assessment}
    D -->|热路径 Hot Path: 快速响应| E[自动化扩容/容灾恢复]
    D -->|重构路径 Recon Path: 精准计算| F[全局基线校准与重构]
```

在工程落地过程中，该方案主要解决了以下几项核心挑战：
* **遥测事件延迟与假警报消除**：如果一个包含 7 个节点的请求中，有 1 个节点的监控数据延迟上报，此时系统只拿到了 6 个节点的数据。如果直接将其误判为结构漂移（即“节点被删除”），就会产生误报。因此，系统必须在评估窗口中动态调整判定阈值，细化对“事件延迟”与“真实拓扑变更”的区分标准。
* **冷启动基线适配**：对于系统新上线的 API 端点，系统不会套用通用的全局基线，而是采用特定端点的定制基线，以避免因无历史参考数据而频繁触发误告。
* **高维漂移检测算法**：在具体的检测算法上，系统采用**最大均值差异**（Maximum Mean Discrepancy: 简称 MMD）算法和 **KL散度**（Kullback-Leibler Divergence: 衡量两个概率分布差异的指标）算法，从统计学层面精准捕捉微弱的数据分布偏移。
* **诊断可解释性**：Ritvik Pandya 强调了监控系统“可解释性”的重要性。他做了一个医生的类比：如果医生对你说“你的健康评分是 22”，这没有任何意义，因为你不知道这个数字背后的病理指标。同理，系统不能只向运维人员报告一个异常分数，而必须提供具体的指标偏离情况（如哪个节点的哪个参数异常），并结合当前的应用部署状态，使运维人员能够做出知情的决策（例如确认是软件部署导致的异常，还是应触发自动回滚操作）。

<details>
<summary>Original English Source</summary>
and here is the simple uh tag for how uh this whole system would work. Open telemetry will will keep feeding the data. Once you have that data, uh root cause analysis could be taken based on uh once your system knows about all the data points. Now you know which type of drift it is and what solution could be there. Then you identify what action needs to be taken. Once you know what action needs to be taken further you need to also uh find out that what is the risk if we go with this approach or if we automate this uh solution right so once you know the risk either you can go with uh roll out that system uh um solution for say 5% or 10% of your uh machines monitor it verify everything looks good and then you roll out for your 100% of the nodes Here are a couple of example. uh again uh say generally overall request processing takes 700 millisecond but uh on the left side what you are seeing is u in the graph approach itself how it could help you is uh now you know that uh which specific node is taking more time suddenly you get alert on that or otherwise if you are seeing that uh the delay is all across then something which is common which you need to fix here all these things because in the payments and the real time uh payment processing we want to keep it very faster right so we don't want delay the actual request processing the solution which we generally use uh everyone in the industry is asynchronously feeding the data to uh opal telemetry from there u some kafka could be used and stream assessment uh could be used on top of it. There could be two different paths. One is say hot path where you can take a decision very faster and uh um work on the solution or automate that solution. The other one is more recon kind of solution where it might take some time but more more accurate could it could be [snorts] few of uh uh other challenges which uh we need to fine-tune here. So all I talked about is hey you have seven nodes in your system and every node is feeding the data to your uh telemetry. What if one of the system is delaying the event? Should we consider it as a structural change because now what you have data in your system is for six nodes and the seven uh uh the data from the seven node is delayed already. So we need to fine-tune that uh that those numbers also that when to consider that uh there is a structural change or not. So basically here we are uh trying to reduce uh any false alarm based on the use cases and here in this use case u we should go with tail by based on system because what we are trying to track here is uh or in this specific example is when the service request started and when it ended right so uh for each and every node the other part is the cold start uh if there is a new endpoint consider the new baseline don't make it very generic. So in that way on the detect side any MMD or KL uh could be used uh and once you confirm uh this with admin and then classify uh the problem uh that will give you where what exact solution needs to be done and next step whatever uh if we can automate it we'll automate it. So what we see uh in general here is uh mean time to uh discovery reduced a lot to make it very real time. Instead of comparing or waiting for multiple windows of uh the time duration it was uh a single window which we uh uh you know which we identified uh helped a lot uh to fix the issues fast. uh few of other things which we might need to make sure. One is uh the labels when it comes to uh learnings the labels helps a lot but uh at the same time uh we need to make sure that uh the system is very fine tuned in terms of that. Uh the other part is instead of saying that all the post requests should have you know this is a baseline for all the post request uh try to come up with very uh a number which works for you post for payments for real-time payment or post for wire payments or u based on you know uh your use cases. So that that would help a lot. Um again uh if anything is u um you are considering a structural change or something uh the window uh should be well defined for each and every client. In my previous uh example which I talked about uh if you can come up with the new baseline would really help uh to reduce the noise. Uh explanability uh all the data should be well explained. If you go to the doctor and doctor says your health score is 22, it doesn't make much sense to you. So, uh yeah, the actual uh more data uh can explain you know more things to you and uh can we can take the informative decision on top of it. Uh whole system should be aware of the new deployment. Uh so u u based on that you can take easy roll back decision or not. So yeah that's that's about it. Uh thanks everyone. Uh I would like to connect with you all. Uh here is my LinkedIn. I can answer it.
</details>