---
author: Money or Life 美股频道
date: '2026-05-16'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=6LUZVFIRItg
speaker: Money or Life 美股频道
tags:
  - optical-communication
  - co-packaged-optics
  - silicon-photonics
  - ai-infrastructure
  - semiconductor-investment
title: 光通讯全解析：AI 时代的‘电转光’革命与投资抄答案
summary: Ace 为大家深度解析光通讯（Optical Communication）的核心概念，从‘电转光再转电’的物理基础出发，拆解传统可插拔、CPO 及 OCS 等技术路径，并对比 InP 与硅光 PIC 的材料优劣。通过对 Lumentum、Tower Semiconductor 等核心标的的深度复盘，揭示 NVIDIA 在 AI 基础设施中的布局逻辑与确定性机会。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - NVIDIA
  - Lumentum
  - Tower Semiconductor
  - Soitec
  - Sivers Semiconductors
  - Hon Hai
  - TSMC
products_models:
  - CPO
  - OCS
  - EML
  - DFB
  - InP
media_books: []
status: evergreen
---
### 物理极限：为什么 AI 必须“光进铜退”

光通讯（Optical Communication）在当前的 AI 基础设施建设中扮演着至关重要的角色，甚至在投资价值上相较于目前价位的存储芯片具有更多的选择和确定性。理解光通讯的核心逻辑，首先要明白一个最基本的问题：为什么我们不再单纯依赖铜线通讯？这就是所谓的**光进铜退**。

在数据中心内部，特别是芯片级 PCB 及机柜内，传统上一直使用铜线传输信号。然而，随着 AI 算力需求的激增，铜线遭遇了物理极限。在单通道 100Gbps 以上的高速电信号传输中，铜线一旦距离稍长就会产生严重的信号失真和散热问题。因此，跨机柜、跨建筑的海量数据流动必须通过**光电转换**来实现。光通讯的本质非常简单，即**电信号转光信号，再转回电信号**（Electric-Optical-Electric: 简称电-光-电）。这一过程涉及从最底层的原材料到顶层的光交换机等多个层级的技术协作。在 AI 基础设施快速扩张的当下，高速互联已成为刚需，这正是光通讯行业才刚刚开始爆发的底层驱动力。

### 架构演化：从可插拔模块到 CPO 的路径选择

在光通讯的技术路线中，最核心的争议点在于**模块封装形态**。这直接回答了“光接口应该离主芯片多近”的问题。目前市场存在两条主流路径：**传统可插拔**（Pluggable）和 **CPO**（Co-Packaged Optics: 共封装光学）。

**传统可插拔路径**类似于常见的插头，具有极高的灵活性，模块坏了可以随时更换，且供应链最为成熟。它的结构是光引擎、数字信号处理器（DSP）以及 ASIC 交换芯片分别进行独立封装。然而，这种灵活性的代价是电信号传输损耗较大，功耗相对偏高。

相比之下，**CPO（共封装光学）**则是 NVIDIA 等巨头目前押注的未来路线。其核心在于将光模块与主芯片（如 ASIC 或 GPU）深度集成，并列封装在同一个基板上。由于电路径被压缩到最短，CPO 具备带宽高、密度大、延迟极低且功耗显著降低的优势。虽然它目前面临散热高度集中和系统耦合过深（一旦损坏维护成本极高）的挑战，但其能效比优势使其成为大模型算力集群的必然选择。介于两者之间的则是 **NPO（Near Packaged Optics: 近封装光学）**，它在性能与可维护性之间寻找平衡点。在实际应用场景中，科技大厂往往不会进行单一的“宗教式选择”，而是根据不同优化目标混合使用这三种方案。

### 芯片底层：InP 与硅光 PIC 的材料博弈

除了封装形态，另一个维度是**光引擎衬底路线**，主要分为 **磷化铟**（InP: 一种三五族化合物半导体材料）和 **硅光 PIC**（Silicon Photonics: 基于硅基材料的光子集成电路）。

**InP 路线**是目前的传统领导者，几乎所有的传统光芯片（激光器、调制器等）都做在 InP 衬底上。代表性公司如 **Lumentum (LITE)** 和 **Coherent (COHR)**，其核心产品是 **电吸收调制激光器**（EML: 集成了激光器与调制器的化合物芯片）。而 **硅光 PIC 路线** 则使用了与 CPU/GPU 相同的硅基材料。它的做法是将调制器、探测器等集成在硅基芯片上。由于硅本身不发光，激光器通常需要外置或通过混合集成的方式接入。

值得注意的是，在 CPO 架构中，硅光 PIC 几乎是必选项。而在传统路径中，它则是一个可选项。相关产业链中，法国的 **Soitec (SOI)** 提供了绝缘体上硅晶圆（SOI）衬底，而以色列的 **Tower Semiconductor (TSEM)** 则是硅光 PIC 的主要代工厂。这两种材料路径在未来 5 到 10 年内将长期共存，并非简单的替代关系。

### 垂直拆解：光电转换的四层物理架构

为了更透彻地理解光通讯，我们可以将其拆解为从零到三的四个物理层级。

*   **第零层：原材料与衬底。** 这是光通讯的物理起点，包括 InP 衬底和 SOI 衬底。
*   **第一层：电芯片与光芯片。** 这是最基础也最重要的层级。**电芯片** 负责电信号处理，包括负责纠错的 **DSP**（Digital Signal Processor: 数字信号处理器），以及 Driver（驱动器）和 TIA（跨阻放大器）。**光芯片** 则负责光源生成与调制，核心器件是 **激光器**（Laser: 光源头）和 **调制器**（Modulator: 将 01 数据转化为光表达的开关）。目前 LITE 和 Sivers Semiconductors (SIVE) 都是该领域的重要玩家。
*   **第二层：光引擎与光模块。** 这是一个打包整合的过程。光引擎将光芯片与部分电芯片封装，而光模块则将光引擎、DSP 及标准接口集成为一个独立单元。
*   **第三层：光路交换机。** 这一层涉及传统交换机、CPO 交换机，以及最具颠覆性的 **OCS**（Optical Circuit Switch: 光路交换机）。OCS 通过物理镜面反射实现光与光的直接交换，跳过了中间的电光电转换过程，从而极大提高了效率，但也对封装工艺提出了极高的要求。

### 确定性博弈：光通讯标的的投资逻辑

在投资实操层面，Ace 提出了一个光通讯“小小 ETF”的概念，包含四支核心标的：**LITE、TSEM、SIVE 和 SOI**。

**Lumentum (LITE)** 是全能型选手，在传统可插拔 EML 激光器领域处于领导地位，同时在 CPO 路线的外置激光器（ELS）和 OCS 领域均有深度布局，具备极高的确定性。**Tower Semiconductor (TSEM)** 则是硅光代工领域的“台积电”，在 1.6T 高端光模块代工中占据约 85% 的份额。它与台积电的区别在于：台积电负责集成先进制程逻辑节点的 CPO 旗舰产品，而 TSEM 则深耕大规模出货的硅光可插拔产品。

**Soitec (SOI)** 作为 TSEM 的上游衬底供应商，护城河极高，基本与 TSEM 形成“一荣俱荣”的绑定关系。而 **Sivers Semiconductors (SIVE)** 则是一个极具想象力的挑战者，其 DFB（分布式反馈激光器）技术专注于 CPO 路线的外置光源，虽然目前投机性较高，但其在 NVIDIA Spectrum-X 等 CPO 产品中的潜力不容小觑。对于投资者而言，光通讯并非一个短期炒作的概念，而是 AI 硬件底层必须夯实的物理支柱，其确定性正在随着英伟达全光 CPO 交换机提前出货等新闻得到持续印证。