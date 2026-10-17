---
author: a16z
date: '2026-07-28'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=-tabaM5l3s0
speaker: a16z
tags:
  - spatial-intelligence
  - world-model
  - real-to-sim-to-real
  - embodied-ai
  - robot-learning
title: 重构具身智能生态：空间智能与真实到模拟（Real-to-Sim-to-Real）的双向闭环
summary: 本文探讨了空间智能（Spatial Intelligence）与大世界模型（World Models）在具身智能中的核心作用。通过将真实物理环境数字化，World Labs 构建了高保真的 Real-to-Sim-to-Real 数据与评估飞轮，打破了机器人训练数据稀缺的瓶颈。结合对 Scenix 的收购，World Labs 将学术前沿与工业实践结合，以“具身解耦”与“模型泛化”的平台化架构，加速了机器人在半结构化环境中的商业化落地。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Fei-Fei Li
  - Yunu
companies_orgs:
  - World Labs
  - Scenix
  - a16z
products_models:
  - Marble
media_books: []
status: evergreen
---
### 空间智能：大世界模型与具身智能的新前沿

**空间智能**（Spatial Intelligence: AI 系统理解、推理、生成物理或虚拟空间并与之交互的能力）是人工智能发展的下一个重要前沿。作为一家前沿模型实验室，**World Labs** 自创立以来的核心愿景就是通过构建**大世界模型**（Large World Models: 能够对物理世界的几何结构、物理规律和时间演变进行三维一致性建模的基座模型）来实现空间智能。对于机器人而言，感知、空间推理以及在空间中采取行动的能力是其核心。

在过去，人们普遍认为让机器人在物理空间中进行交互与行动是一个极其遥远的未来课题。然而，通过将空间智能模型与实际机器人系统相结合，这一进程正在显著加速。**大世界模型**能够将图像、文本等输入转化为几何一致的 3D 物理世界，为机器人的学习和评估提供了根本性的基础设施，这也是迈向通用具身智能的关键一步。

<details>
<summary>Original English Source</summary>
We are building the next frontier of AI which is what we call spatial intelligence. Spatial intelligence is about creating AI that has the ability to generate, understand, reason with, and interact with spaces whether it's physical or virtual. And of course, a means to an end towards spatial intelligence is building large world models. And that's what World Labs is mostly focused on.

Perceive and reason about spaces and act on spaces... I always had the assumption that the acting on spaces was some like longist future thing but now you're acquiring a robotics company and so maybe talk a little bit about the timeliness of this...

First of all, it doesn't just take robotics to act within spaces or to interact, right? I mean, look at the creative field, whether it's VFX or gaming and or design. Many use cases, you can create and act within virtual spaces. World Labs' thesis has always been that the world we live in can be multiverse that we create technology to allow people, builders, developers to act within different spaces. Having said that, the ability to act within the physical space is one of the most exciting and most profoundly important capability of the future AI world. So robotics is very much that.
</details>

### Real-to-Sim-to-Real：打破机器人训练的数据瓶颈

在机器人学和**机器人学习**（Robot Learning: 利用机器学习方法使机器人自主获取新技能的领域）中，最核心的痛点在于数据极度匮乏，这与互联网上拥有海量文本数据的语言模型有着本质区别。为了让机器人技术解锁**缩放定律**（Scaling Law: 模型性能随计算量、数据集规模和参数量呈指数级增长的经验法则），业界必须找到一种大规模获取有效训练数据的方法。

**Scenix** 团队（由哥伦比亚大学助理教授 **Yunu**、图形学与模拟专家 Changi Jan 以及工程领袖 Sunonny 创立）的加入为 World Labs 带来了独特的解决方案——**Real-to-Sim-to-Real** 管道（Real-to-Sim-to-Real Pipeline: 将真实世界场景高保真重建为数字模拟环境，在模拟中训练和评估机器人，再将策略部署回真实世界的闭环流程）。通过捕捉环境的外观、几何结构以及动作施加后的动态演变，这一管道能够生成高保真的数字世界。在此基础上，World Labs 的三维重建模型（如其发布的首个生成式空间模型 **Marble**，能够将单张或多张图像及文本转化为几何一致的 3D 高斯泼溅或网格）能够极其高效地进行环境数字化，从而用低成本、可扩展且安全的数字模拟数据替代昂贵且危险的物理世界数据收集。

<details>
<summary>Original English Source</summary>
Really what Scenix team is doing is trying to solve this extremely difficult problem in robotics which is the lack of data. The lack of data in training, the lack of data in evaluation. This is very, very different from language models where data is abundant on the internet. And we know that in order for robotics to work, we have to somehow unlock the power of scaling law. But where does that come from? This is something that is a profound problem that everybody's battling with in robotics.

We are developing what we call a real to sim to real pipeline. We want to map the real environments into the digital world that has the best alignments with the real environments. By alignments, we mean that whatever happens in the digital world is also going to happen in the real environments, such that we can replace all the data, all the evaluation we need in the real environment by using the data that can generate at a scalable way in our digital world. So that is how everything started in Scenix... trying to build this real-to-sim-to-real stack to solve some of the key bottlenecks.

In any sense, as Scenix, what we have been doing is real to sim to real, is to do this reconstruction of the environment. So we capture the appearance of the environment, geometry of the environments, and also the dynamics of the environment, meaning how the environment is going to change when you apply actions. So this tensor reconstruction right now is still a little bit on the heavier side and what World Labs right now has been doing involves a lot of profound capabilities around sparse reconstruction and generations. So we see a lot of opportunities of leveraging like Marble and other capabilities as World Labs in order to do very efficient reconstructions and modeling of the environments.
</details>

### 多模态具身基座模型与反事实模拟

在这一背景下，未来的机器人基座模型必将是一个多模态的**统一基座模型**（Omni-model/Foundation Model: 支持图像、深度图、文本、动作等多模态输入输出的通用模型）。如果将动作作为输入，它将表现为一个**前向模拟器**（Forward Simulator: 根据当前状态和动作预测未来环境状态的物理或神经网络模型），预测环境如何因机器人的动作而改变；如果将动作作为输出，它则是一个**策略模型**（Policy Model: 根据当前感知状态和目标任务预测机器人最优动作的决策模型）。

与单纯使用视频模型进行动作预测的方案不同，大世界模型强调物理和空间的三维一致性，这避免了视频模型在预测时物体“凭空消失”或违反物理常律的现象。更重要的是，模拟环境为机器人提供了**反事实推理**（Counterfactual Reasoning: 对“如果采取了不同的行动，结果会如何”进行模拟和推理的心理与计算过程）的能力。正如人类大脑会通过模拟来规划行为、规避风险一样，机器人必须通过在一致的数字世界中进行大量“假设性”的对抗性探索，才能在面对未曾经历的边缘场景时保持鲁棒性。

<details>
<summary>Original English Source</summary>
World Labs is building a foundation model. As you know, Martin, we're building a base model and as the technology has been evolving, some of the most exciting base models are omnimodels, right? They take multimodal input, they have multimodal outputs. And what is a foundation model for robotics? It's very likely going to involve actions... the output of actions in addition to the state of the world.

For the foundation models, it essentially needs to be a multimodal model. So it has to take into account frame, text, image, depth and different kind of modalities, and action is a very, very important part of that modalities. So if you think about frame, actions as inputs, that is essentially a forward simulator that is going to predict how the environment is going to change when you apply a specific action. When the action is output, this is essentially a policy model that is trying to predict given a specific goal, what should be the action you take in the real environment to get you closer to that goal.

In order to create worlds where the robot can learn... one of the very important necessary requirements for those worlds will be consistency... Imagine if a robot push an object forwards, the object just magically disappear, which has been a problem of many of the existing video prediction models. This won't provide good enough signal for the robot to know what is the right thing to do.

Think about human intelligence. We do a lot of simulation in our head. Why? There's a very important role simulation plays that real world data doesn't play which is counterfactual reasoning... that you play out events that hasn't happened or cannot happen or you don't have enough data to make it happen in real world. And while you play it out, you learn how to act in it. Humans do this all the time... simulation, the role simulation plays is counterfactual reasoning. And that's really important in robotics because we just do not have, cannot possibly have enough real world data for that. Waymo has officially said they use billions of hours of simulation... and actually Waymo is more simulation-heavy than just real world data heavy.
</details>

### 系统性评估：工业级机器人的落地衡量标准

在机器人技术向工业界落地的过程中，**系统评估**（Evaluations/Evals: 衡量模型在特定基准测试中的性能、成功率及鲁棒性的系统化测试流程）往往是被研究人员忽视但对客户至关重要的环节。对于非 AI 领域的工业客户而言，他们关心的不是前沿技术本身的学术指标，而是机器人系统运行的**可靠性**（Reliability）与**效率**（Efficiency）。

在真实的物理环境中进行模型迭代极为缓慢且危险。在现实中区分一个成功率为 90% 的模型 checkpoint 与一个 92% 的 checkpoint，需要耗费数天甚至数周的实操测试，且伴随着昂贵的硬件磨损风险。而通过在具备“高对齐度”的数字孪生环境中进行模拟评估，开发人员可以在数字世界中进行并行化、超常速的系统性评测。由于模拟环境能够进行光照、摩擦力、几何形态以及物理参数的系统性**随机扰动**（Domain Randomization: 在模拟中随机改变物理和视觉属性以增强模型泛化能力的训练技术），它不仅能够为机器人提供全面覆盖的测试，还能够在极短的时间内给出置信度极高的性能反馈，极大地缩短了研发飞轮的迭代周期。

<details>
<summary>Original English Source</summary>
There are essential like two specific use cases especially around both training and also around evaluations. Starting from the evaluations... evaluation is something like people often overlooked in the robotics but if you are tuning like robotic models you have to know how well it works and that is the only source of information for you to iterate.

What I mean by evaluation is you'll be able to understand for this specific checkpoints how well does it perform? Does it perform for example 95% of the time or 99.9% of the time? And the key criteria people use in industry is how long does it take? How long in walk-clock time does it take for you to distinguish between a checkpoint that is 90% from a checkpoint that is 92 points. And if you only do that in the real environment, that's just takes so long for you to do the distinguishment. The iteration speeds is multiple orders of magnitude slower than iterations of those language models.

At the same time the speed is also like multiple orders of magnitudes like slower. So some of our clients actually needs this digital environment that's can be used to evaluate their robotic systems, and because our digital environment has proven alignments with the real world... If a checkpoint is working better in the simulation is also highly likely to also work better in the real environments.

With simulation, you can do systematic randomizations and control and the variations of lighting, frictions, geometries, object types and also all different kind of physical parameters to making sure you have sufficient coverage of the state space. So this is what can give the robotic systems reliability. Second is about efficiency. Right now many people are doing teleoperation... collecting the data at a speed that is actually slower than human actually doing the task. But for many of our clients, human speed to them is not good enough. They want faster than human speeds. But in simulation, you can do systematic speed up of the robots behaviors to train the robots such that it considers all the dynamics changes of the environments.
</details>

### 解耦与通用化：构建具身无关的机器人大脑

World Labs 与 Scenix 联合构建的平台展现出了一种极为先进的**架构理念**——**具身解耦**（Embodiment Agnostic: 软件算法与具体的机器人硬件外形、自由度和传感器配置无关的普适性设计）与**模型泛化**（Model Agnostic: 独立于下游具体神经网络架构或训练方式的通用基础设施架构）。

该平台并不生产具体的硬件，也不拘泥于某一种特定的机器人形态。无论是单臂、双臂、固定底座还是移动底座的**机械臂**（Manipulator: 用于抓取、移动和操作物体的多关节机器人手臂），平台都可以无缝接入。这种架构将“世界的物理规则和状态表征”与下游的“具体控制动作”进行了解耦。通过将物理环境重建为高度一致的世界模型，客户既可以直接利用生成的数据对各种模型（如 **VLA 模型**（Vision-Language-Action Model: 将视觉、语言和动作统一建模，直接输出控制指令的具身智能模型））进行从头训练或微调，也可以在模拟环境中直接运行并评估现有的控制策略。

<details>
<summary>Original English Source</summary>
What we have been building you can imagine is a infrastructure like with the softwares around this infrastructures for people for them build worlds such that robot can learn and evaluate, and this infrastructures is naturally model agnostic and embodiment agnostic. From what you said that's not building a robot, it's building an environment which another company can place their robot brain to navigate and to learn.

Yeah. So for our customers right now they have all different kind of robots. Some are using for them single robot arm, some are using bio, some are using a fixed arm. Some are using like a mobile manipulators. Some using grippers, some are using some more elaborate versions of the end factors. So our platform right now is just naturally embodiment agnostic. We can very easily integrate different kind of robotic embodiment be able to put them into the worlds we generated with digitalized such as we will be able to give those individual robots capabilities of doing the right tasks.

And we are also for example model agnostic. So we can just using the data generated by our worlds to train different models either from scratch or doing post training of existing foundation models like vision language action models or world action models. So to us it doesn't matter, we just want to making sure we have the infrastructure we have all the worlds such as the robot can work reliably in the real environment.
</details>

### 理性乐观：半结构化环境中的渐进式落地

在关于**人形机器人**（Humanoids: 具有类人身体结构和运动机能的通用机器人）的发展前景上，业界目前需要保持一种“理性的乐观”。人类身体是数百万年进化为了适应完全**无结构化环境**（Unstructured Environments: 没有任何先验约束、物理布局随机多变的日常环境，如人类家庭）而产生的极致泛化器。但从商业与技术的落地难度来看，直接挑战无结构化的家庭环境是极其困难的。

因此，更具可行性的商业路径是从**全结构化环境**（Fully Structured Environments: 物理布局和任务流程完全固定且受控的工业环境，如汽车制造装配线）逐步过渡到**半结构化环境**（Semi-structured Environments: 布局存在先验约束，但具体物体、环境动态有一定随机性的环境，如物流仓库、酒店和餐厅）。在这种环境中，通过在模拟中训练具备高可靠性的空间推理和操纵策略，机器人能够更稳健地部署落地。World Labs 目前的战略重点正是与这部分处于临近部署阶段的客户紧密合作，在具体的垂直领域（如仓储自动化和工业装配）建立“灯塔级客户”样本，通过真实的商业价值推动数据与算法飞轮的良性运转。

<details>
<summary>Original English Source</summary>
If you look at for example all the progressions of robotic applications in the real environments it has always followed the trend from going from fully structured environments into semi-structured environments and then into unstructured environments. For fully structured environments... you have knowledge and control over all the configurations within the environments, like factories or for car manufacturing... those has been automated for decades. And then you have for example semi-structured environments which you have certain controls over the environments for example like the Amazon warehouses or for example like restaurants, hotels... but there are obviously many other like objects... those are the object you don't have control. And then for the unstructured environments it's like your home...

Humanoids mimics human body and evolution has optimized human body for unstructured environment... But from a business point of view, from a pragmatic technology point of view, that this unstructured environment and a generalized body is actually the hardest problem to solve... We specialize... to solve a narrower problem. But the challenge for Scenix is to be more body agnostic so that their infrastructure can serve different bodies and different semi-structured environments.

To achieve for example human level efficiency and capabilities it will take longer. Martin, the hardest thing in today's AI is to have the right measured optimism, right? LLM does not have human brain efficiency. Human brain operates on 30 watts. So we are far from that. But performance to power it may be close, right? in narrow task like software... I don't think we're anywhere close when it comes to robotics.

We are very happy that Scenix team and World Labs team will have validated customers in a small number of important vertical use cases where our system, our infrastructure has proven to be truly beneficial to their automation needs. And these customers became our lighthouse examples to scale our business.
</details>