---
author: Dwarkesh Patel
date: '2025-02-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=itkvrQUSJC0
speaker: Dwarkesh Patel
tags:
  - quantum-computing
  - majorana-zero-modes
  - topological-qubit
  - fault-tolerance
  - computational-physics
title: 微软马约拉纳芯片：量子计算的“晶体管时刻”与百万比特愿景
summary: 微软 CEO Satya Nadella 揭秘了量子计算的重大物理突破——马约拉纳零能模（Majorana zero modes）的成功实现。这一进展被视为量子计算的“晶体管时刻”，标志着从理论走向可扩展、实用化规模（Utility Scale）的关键转折。通过马约拉纳 1 芯片，微软计划在 2027-2029 年间构建容错量子计算机，并展示了量子计算与 AI、高性能计算（HPC）协同运作的未来混合架构。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Satya Nadella
companies_orgs:
  - Microsoft
products_models:
  - Majorana 1
media_books: []
status: evergreen
---
### 马约拉纳零能模：量子计算的“晶体管时刻”

在量子计算的发展史中，如何从实验室原型迈向**实用化规模**（Utility Scale）一直是行业核心痛点。微软 CEO Satya Nadella 展示了其最新研发的 **Majorana 1** 芯片，并将其定义为量子计算领域的“晶体管时刻”。这一突破的核心在于利用了 1930 年代理论化的**马约拉纳零能模**（Majorana zero modes），通过在一种全新的物质相——**拓扑相位**（Topological phase）中运行，成功实现了量子信息的可靠隐藏与测量。

相比于其他路径，这种物理层面的突破解决了量子位（Cubit）高度敏感、易受干扰的顽疾。通过这种**基础制造技术**（Foundational fabrication technique），微软能够在指甲盖大小的芯片上集成多达一百万个物理量子比特，并在此基础上产生数千个经过**纠错**（Error corrected）的逻辑量子比特。这不仅是数量级的跃迁，更是从“实验演示”向“实际应用”的质变，使得构建一台真正的实用规模量子计算机在物理架构上变得触手可及。

<details><summary>Original English Source</summary>
I believe this is it right here... to think of the fact that we were able to build a million Cubit quantum computer in a thing of this size is just unbelievable... the vision that we've always had is you need a physics breakthrough in order to build a utility scale quantum computer that works. And so we took that path... to bet on a physical property that by definition is more reliable and that's kind of what led us to those Majorana zero modes... which was theorized in the 1930s. Effectively, we now finally have existence proof and a physics breakthrough of a Majorana zero modes in a new phase of matter effectively. So this is why I think we like the analogy of thinking of this as the transistor moment of quantum Computing where we effectively have a new phase which is the topological phase where we can even now reliably hide the quantum information and measure it. And so now that we have it, we feel like with that core foundational fabrication technique out of the way, we can start building a Majorana chip, that Majorana one which I think is going to basically be the first chip that will be capable of a million cubits physical and then on that thousands of logical cubits error corrected. And then it's game on.
</details>

### 容错之路：从原子级模拟到 2029 落地时间表

随着底层物理突破的完成，量子计算的演进逻辑将遵循一种类似“摩尔定律”的指数级增长。Nadella 预测，首台**容错量子计算机**（Fault-tolerant quantum computer）有望在 2027 至 2029 年间问世。这一进程中最具吸引力的特征是量子计算的“自我加速”属性：由于量子计算机在模拟自然界的原子级构造方面具有天然优势，第一代量子计算机的首要任务将是辅助设计更为先进、更易制造的下一代量子门和量子电路。

目前的挑战已从基础物理发现转向了**集成电路**（Integrated circuit）的大规模工程化。将单一的量子门封装进集成电路，再将这些电路组装成完整的计算机系统，是未来三年的核心路线图。这标志着量子计算正从物理学家的实验台，全面进入电气工程与计算机科学的系统集成阶段，为未来通过 API 提供量子算力铺平道路。

<details><summary>Original English Source</summary>
I wish we had a quantum computer because by the way, the first thing the quantum computer will allow us to do is build quantum computers because it's going to be so much easier to simulate atom by atom construction of these new Quantum Gates essentially. But in any case, to me I think the next real thing is now that we have the fabrication technique, let us go build that first fault tolerant quantum computer... I would say now I can say oh maybe 27, 28, 29 we will be able to actually build this. So now that we have this one gate, can I put the thing into an integrated circuit and then actually put these integrated circuits into a real computer, that I think is where the next logical step is.
</details>

### 协同演化：AI 模拟器与量子仿真器的深度融合

量子计算并不会取代传统经典计算（Classical computing），而是与其形成互补的混合架构。Nadella 提出了一个深刻的洞察：**AI 是仿真器的模拟器**（AI is an emulator of the simulator）。量子计算本质上是自然界的**仿真器**（Simulator），特别擅长处理“数据轻量、状态重型”的探索任务，例如化学、物理和生物领域中涉及**指数级状态空间**（Exponential states）的分子结构模拟。

在这种新架构中，**人工智能**（AI）将作为**仿真引擎**（Emulation engine）发挥作用。未来的工作流将是：利用量子计算机生成反映自然界真实物理规律的**合成数据**（Synthetic data），再用这些高精度数据训练 AI 模型，从而让 AI 掌握模拟化学反应或物理过程的深层规律。这种由**高性能计算**（HPC）、AI 与量子计算构成的“三位一体”栈，将彻底重塑科研与工业开发的范式，使得人类能够在数字世界中完整地模拟和理解现实世界的物质属性。

<details><summary>Original English Source</summary>
The breakthrough we had maybe two years ago was to sort of think of this HPC stack and AI stack and Quantum together. In fact, if you think about it, AI is like an emulator of the simulator... Quantum is like a simulator of nature. Quantum is not going to replace classical; Quantum is going to be fantastic for anything that is not data heavy but it's got more exploration heavy in terms of the state space. Data light but exponential states that you want to explore, and simulation is a great one... chemical, physics, biology. One of the things that we've started doing is really using AI as the emulation engine. If you have AI plus Quantum, maybe you'll use quantum to generate synthetic data that then gets used by AI to train better models that know how to model something like chemistry or physics. And these two things will get used together. I hope to replace some of the HPC pieces with quantum computers.
</details>