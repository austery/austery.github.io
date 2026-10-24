---
author: Anthropic
date: '2026-08-27'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=P1zBiAQU1IA
speaker: Anthropic
tags:
  - lab-automation
  - hardware-control
  - scientific-research
  - closed-loop-experimentation
title: 连接物理世界：模型硬件标准（MHS）与 AI 驱动的科学实验革命
summary: 本文探讨了由 Anthropic 开发的“模型硬件标准”（Model Hardware Standard），该标准允许大语言模型 Claude 直接与显微镜、机械臂等物理实验设备交互并进行控制。通过与神经科学家 Arco Bast、仪器制造商丹纳赫（Danaher）以及基因泰克（Genentech）的合作，展示了 AI 在神经科学成像、闭环实验和药物研发中加速物理科学实验的巨大潜力。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Arco Bast
companies_orgs:
  - Anthropic
  - Danaher
  - Genentech
products_models:
  - Claude
  - Model Hardware Standard
media_books: []
status: evergreen
---
### 策略性重构：物理实验的痛点与 MHS 标准的诞生

在科学研究中，提出理论只是第一步，更为关键且耗时的是通过物理测量设备和实验来验证这些理论。通常情况下，科学家有高达 **80% 的时间**消耗在非直接科学研究的日常事务中，例如设备搭建、硬件调试以及软件编写。这些繁琐的工作虽然是科学运转的基石，但也极大拉长了科研周期。为了打破这一效率瓶颈，**Anthropic** 与神经科学家 **Arco Bast** 展开了深度合作。Arco 在实时观测大脑记忆形成过程的实验中，面临着复杂且极其敏感的定制显微镜系统对齐问题，以及不同硬件设备接口语言不通的痛点。

针对这一问题，团队联合开发了通用的**模型硬件标准**（Model Hardware Standard: 旨在为 AI 模型与物理实验设备提供统一接口的通信标准，简称 MHS）。这一标准打破了各硬件厂商接口协议的壁垒，使大语言模型能够直接与物理设备进行无缝交互。通过这一标准，AI 模型可以直接向激光源、机械臂等物理设备发送指令并获取状态反馈，从而将繁琐的系统调试和设备配置时间从数年缩短至数月，让科学家能够专注于核心的生物学与物理学命题。

<details><summary>Original English Source</summary>

Scientists come up with theories about how the world works. But just coming up with a theory isn't good enough. And so we have to build experiments, physical measurement devices, to test our theories. That process of building the experiment takes maybe 80% of a scientist's time. They're building devices, they're setting things up, they're debugging hardware, debugging software. These are things that aren't really related to doing science, but it's what makes science actually work.

When I joined Anthropic, I had a vision for using AI to accelerate running scientific experiments, But I thought it was a pie in the sky, crazy idea, until I saw the work of neuroscientist Arco Bast, who studies how memories are formed in the brain in real time.

I'm in the lab for a year now, and I'm setting up a very difficult experiment. So the stuff is over here. That's a custom -built microscope. You see the laser beam in here. That's actually what's happening when you're imaging in the brain, that you have this laser beam that scans and moves. It's really, really important that everything is precisely aligned. There are so many components, and I just want to have them talk to each other in a seamless way. The problem is that each device has a different language that it speaks, and getting the devices to talk to each other in their languages is very difficult. But Arco figured out a way to do this that could work between any two devices.

Set beam one to 50% power. Yeah, we got a beam. And the beam is there.

When I was standing in that room watching him run his experiment, I had kind of an epiphany in that moment. what he had built wasn't just applicable to this lab. This idea could be used to have AI run any science experiment in the world. I was basically speechless.

Is this ours? I believe everything on the table is ours. We've got to start putting this together. So Arco and I started working together to create a general way for AI to interact with devices, which we're calling Model Hardware Standard. Look, with a very sophisticated microscope, and this microscope has so many degrees of freedom, you should see it moving now, right? Yay, moved. It moved. It did. Yes, I think everything looks good. Okay. Okay.

</details>

### 自主决策与迭代演进：安全边界与高精度显微交互

为了验证 MHS 协议的跨设备通用性，研发团队在多种物理实体设备上进行了系统化测试。首先是在机械臂控制中定义了清晰的物理安全边界。实验证明，当尝试引导 AI 模型 **Claude** 执行超出限制的安全范围移动时，MHS 的底层安全机制能立即拒绝执行，这确立了模型在物理世界运行的底层安全防线。在后续的零样本测试中，Claude 在无预定义脚本的情况下，自主规划并成功在数分钟内完成了物体的物理抓取任务。

随后，团队与科学仪器制造商**丹纳赫**（Danaher）合作，将 Claude 连接到旗下的**徕卡**（Leica）精密显微镜上。在此过程中，AI 展现出了卓越的**闭环迭代与风险感知能力**：它不仅能够通过实时的视觉与数据反馈逐步调整焦距与色彩通道，获取清晰的木质化细胞壁图像，还表现出清晰的物理环境感知——即当被要求切换至更高放大倍率时，能自主识别显微镜镜头可能碰撞并损坏样品的物理风险，并采取规避动作。这种迭代适应性使得高难度物理设备的操作难度大幅降低。

<details><summary>Original English Source</summary>

Once we had a working prototype, we had to test this on other devices to see how it worked beyond just neuroscience.

Go to the left boundary first. One of the first things that I did was to define the safe range of this arm. How far is it allowed to go out of the table? And so if we ask Claude to maybe intentionally move out of the safety range, you can kind of see that this motion, this movement was refused by MHS. Oh, that's incredible. Can it grab anything right now? Oh, great question. We've never asked Claude to do this from scratch, and so I have no idea what it'll cook up for us. There are turns that I need to... Oh. Wow. Oh. Wait, wait, wait, what? What? Oh my God. Okay, that was sick. That was really cool. The mere fact that I was able to build this from scratch today and it achieved it in a matter of minutes. That's insane.

And of course, we also have to work with the manufacturers and the vendors who build the devices. So we started working with Danaher to get Claude to connect with their Leica microscope. We have to remind ourselves that Claude has never seen anything related to this application before. It will make mistakes. So we can think about this as an iterative process. You have to imagine that I as a scientist spent weeks making this sample alive to this point of view and I spent thousands of dollars in ingredients. I see. Okay. If you break them, your experiment is gone.

You can even see how it's thinking. It's now brightly trying to change settings of the microscope to get an image. and I think we need to help it. What's interesting here is you can see that when I asked it to switch to a higher magnification, it is very aware of going to a higher mag can crash it into the sample. It's amazing. It knows how to operate a microscope. Do you think we're at a point now, I could enter a bunch of commands and get a focused image and query what is the image and add false color and all that type of stuff? We should try it. That's incredible. That's awesome. What is the different colors right now? Could we ask it? Magenta red slash pink. Lignified cell walls. These things are the cell walls. That's great.

</details>

### 实时闭环与药物研发：AI 驱动物理世界的历史性突破

在物理世界的动态追踪实验中，以往科学家需要长时间甚至数小时守候以追踪快速移动的活体样本（如藻类）。Claude 通过自主编写控制脚本，并在短时间内构建出直观的可视化用户界面（UI），成功实现了对水中藻类运动轨迹的稳定自主追踪。这一成果证明了 MHS 系统不仅适用于静态配置，还能实现低延迟的动态任务响应。

在更为宏大的商业化场景中，这一技术正被引入**基因泰克**（Genentech）的自动化制药流程。药物研发需要筛选数十万甚至数百万个分子，而移液孔板中因气泡产生的液体转移误差是影响实验准确性的长期痛点。通过引入 Claude 与 MHS，系统首次实现了物理层面的**闭环实验优化**（Closed-loop Experimentation: 自动执行实验、提取并解读数据反馈、微调执行参数并重复实验的循环过程）。模型可在运行期间自主检测是否存在气泡干扰，并自适应调整吸液参数以减少气泡生成，从而显著提升分子筛选的成功率。这标志着 AI 在药物化学与物理世界交互领域的里程碑式突破，为生物制药、量子计算、核聚变等前沿领域的快速试错带来了巨大空间。

<details><summary>Original English Source</summary>

What we accomplished in a day is pretty transformative. Claude walked in. We told him nothing. He's just trying to figure it out. Tomorrow I think we should try to give it, you know, treat it as a colleague.

Oh, there's a lot going on in there. Let's say a scientist wanted to look at this, they would have to sit and wait and keep tracking it. Correct. For like hours. Correct. Yeah, I had a nice one, but it swam away. I'm wondering if Claude can write a program that can track that. Claude is almost done with the initial script to do the tracking. That's off. Oh, shoot. Yeah. Yeah, damn. I actually think it needs to build a UI so we can see what it is doing because just running a script in the background is not acceptable. This looks good. Yo, that's awesome. It's doing what it should. Yeah, it is. It's tracking. It's tracking. Three minutes, four minutes. It's been tracking for a few minutes. No way. We've just been watching it. Chasing algae. Amazing that we managed that. It managed it.

This is a prototyping system somehow, or a very dynamic system where you can create something very quickly. Maybe it's even good enough for some science applications. The PhD can do his PhD work faster because he doesn't need to spend two years to get it running. He only needs two months. And then he can focus on biological questions, which is what our goal is. I still can't believe it. We're very impressed.

I think Model Hardware Standard opens the door for a lot of new types of science. The obvious example is in pharmaceuticals. Here at Genentech, we make medicines for patients with serious and even life-threatening diseases. It takes many, many iterations to make a drug. We will test thousands or even hundreds of thousands or even millions of molecules to find the right molecule that will really help patients. So we are going to start an experiment where Claude will run a series of operations and then interpret the data. If you aspirate out of a well that has bubbles, you're not getting the correct transfer amount. If we were trying to aspirate out of this, we're going to get the proper amounts in the wells with no bubbles and then improper amounts in the ones with the bubbles.

With Claude, we could potentially check during the production runs for these bubbles to see if they are happening, and hopefully it has the context and knowledge to make adjustments. Claude will do some execution, take the reading and then change the parameters of the execution slightly to see if it can improve the experiment overall in a closed loop. Speeding up this loop means we are just able to make more shots on the goal and can get to the answers faster.

This is fewer bubbles. It's got bubbles in two, but not the rest. So this is better. This is really the first time in history where we are enabling AI to interact with the physical world in drug discovery. It's definitely historic, yeah.

I think it's very difficult for us to predict how AI and model hardware standard will affect the world 30, 50 years in the future. These are the best moments when there's something I couldn't do before and now I can do it. Something I couldn't see before and now I can see it. That's the drive. I want to understand things we don't understand right now. Imagine what we'll see in drug development, in quantum computing, in nuclear fusion, in big technologies that could change the world when scientists have access to this technology.

</details>