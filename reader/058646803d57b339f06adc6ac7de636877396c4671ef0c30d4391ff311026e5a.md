---
author: AI Engineer
date: '2026-07-20'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=IvE8n-ylFYY
speaker: AI Engineer
tags:
  - confidential-computing
  - wearable-ai
  - key-management
  - zero-trust
title: 云端机密智能体：Bee 的隐私保护与零信任架构
summary: 本文整理自亚马逊收购的 AI 穿戴设备 Bee 创始人 Steve Korshakov 的演讲。他深入探讨了 Bee 智能体如何处理全天候音频记录带来的极度敏感隐私数据，并详细介绍了基于机密计算、远程度量管线及 Sigstore 透明日志构建的云端有状态运行时密钥管理与沙箱化安全发布体系。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Amazon
products_models:
  - Bee
media_books: []
status: evergreen
---
### 云端机密智能体：Bee 的隐私保护与零信任架构

#### 穿戴式智能与极度敏感的个人隐私数据

**穿戴式智能设备**（AI Wearables: 录音并捕捉个人全天候数据的硬件设备）正在开启一个全新的个人智能时代。演讲者展示了其团队被**亚马逊**（Amazon）收购前开发的硬件设备 **Bee**，它本质上是一个始终在线的微型麦克风，用于记录用户生活中的所有语音，并在此基础上构建**个人智能体**（Personal Agent: 能够代表个人进行思考与执行任务的 AI 实体）。

然而，这种全时段的记录带来了前所未有的隐私挑战：
* 一个普通人佩戴该设备，每年大约会产生 **1000万Token** 的极度敏感隐私数据。
* 在佩戴设备的首周内，用户就会向家人和朋友吐露涉及极其隐秘的个人信息，几乎可以在一周内彻底勾勒出个人的完整画像。

为了应对这一挑战，团队确立了核心设计宗旨——即便是亚马逊公司内部员工，也绝对无法访问或查看任何用户数据。在被亚马逊收购后，这一承诺的履行面临更大的技术挑战，因为在大型企业内部，防范**内部威胁**（Internal Threats: 来自组织内部的人员或系统的安全风险）和确保数据完全不落地，需要比普通云服务更为严苛的安全架构支撑。

<details>
<summary>Original English</summary>
Hello everyone. I hope this talk will be shorter. Uh I'm from Amazon. Uh our company was acquired about 8 months ago and we built the uh AI wearable which is on my hand. Uh which is essentially a microphone that records everything and builds your personal agent, personal AI and uh on top of that you can extract all the data that you record and plug it to your systems or agents uh and do whatever you want. Uh just to be to get in perspective how confidential how like private data we capturing uh a single person usually like captures about 10 million tokens per year. So this um and even within like a first week of recording uh uh people usually tell uh extremely sensitive stuff to their friends to their family. uh you can learn virtually everything about the person within the just like one week of wearing the B device which is extremely sensitive. I think we one of the most sensitive uh capture device on the market now. So and uh because of this we had to encrypt everything and our mission was to not have access to any of this data and not being able to look at it anyone at Amazon and it became a little bit challenging for us at Amazon because uh Amazon itself provides strong security and privacy guarantees but if you Amazon and you using Amazon stuff there is like much more uh serious security stuff you need to do.
</details>

#### 云端有状态运行时与智能体持久化设计

为了让个人智能体实现真正的高效与自主，团队定义了几个核心原则：
* 智能体必须**全天候不间断工作**，持续为用户的利益服务。
* 它必须能够**代为执行任务**。
* 它不能过度消耗用户的本地资源（如手机电量）。

基于这些原则，团队彻底抛弃了传统的**请求-响应模式**（Request-Response Model: 客户端发送请求、云端计算并返回结果的交互机制），因为该模式无法支持需要持续数天运行的复杂任务。随着技术演进，未来的个人智能体必然向**有状态运行时**（Stateful Runtime: 能够在交互过程中维持和管理状态的执行环境）与**持久化内存**（Persistent Memory: 保证数据在程序退出或断电后依然存在的存储机制）架构转变，这类似于云端代码从即时触发走向长时间持续运行的趋势。Bee 构建了一个完全托管在云端、无需用户设备保持在线的自治系统。该系统能够自主连接第三方服务和工具，具备高度的自主性，但所有控制权依然牢牢掌握在用户手中，且服务商无法窥探其内存状态。

<details>
<summary>Original English</summary>
Uh first of all we defined like few core principles what we needed to do for our specific agent. First of all we believe the agent should be like working all the time non-stop for for your good. Um it should be doing stuff on your behalf. Uh and um we should not consume uh customer resources such as batteries and stuff. So this way uh we uh so this leads us to one specific design uh of the um of the our system. Current system usually builds the uh on state uh on request response uh system where you send uh request to a l from your say iPhone uh calculate something and the back end that gives you back. Unfortunately, we already see that this is not enough uh that we need to uh that we need to run stuff continuously and sometimes for days we can see uh we can see this like as a like glimpse into the future how cloud code works. So like just few months ago it was like more like request response stuff like change this, change that and now it can works for like hours for us. We think the same will happen to all your like personal agents anyway. So uh because of this we built uh a stateful runtime with persistent memory um that we still don't have access to. Uh it can connect to different tools. It can connect to any like third party services if we if we program it to um and we don't require the user device to be online. So it's fully autonomous but at the same time it's fully controlled by the user.
</details>

#### 端到端加密与密钥管理架构

团队的端到端加密系统围绕四大支柱构建：密钥完全留存在用户端（如 iPhone 或 Android 设备）、全员强制加密且不可关闭、工作负载完全透明可审计、以及尽可能减少外部信任依赖。

在这一体系中，**密钥管理**（Key Management: 负责加密密钥的生成、存储、分发和销毁的安全体系）是最大的技术难题。其具体处理流程如下：
1. 密钥在用户手机上生成并持久化。
2. 当手机连接至云端后端时，会触发一套极度复杂的**远程度量管线**（Attestation Pipeline: 验证云端运行软件与环境未被篡改的信任验证机制）。
3. 该管线会验证云端工作负载的完整性，并确认其已在 **Sigstore** 这一公共透明日志中注册，允许任何人核实云端工作负载的真实性。
4. 度量通过后，客户端将密钥安全地共享给后端，后端将其复制到运行于**机密计算**（Confidential Computing: 在硬件隔离的受保护内存中执行计算的技术）环境的推理节点中。

同时，为了防范内存泄漏等潜在风险，所有进入机密计算节点内存的密钥都被强制设置了 **7天的生命周期**。这一时限确保了即便用户短时间内离线，智能体也能持续执行长周期的任务，而在任务结束后密钥会自动销毁。

<details>
<summary>Original English</summary>
Um so encryption system is built um uh on few on four like core ideas that we need to follow. First of all the key leaves and manage it only on customer device. So it's users iPhone or Android device itself. We don't have the key ourselves. We don't persist it anywhere. So keys is is um is stored only on the customer phone. Everything is encrypted. We don't have any opt out there. No way to disable it. There no way to bypass it. Uh at the same time we uh to protect ourselves from um like internal threats uh we do fully transparent and audit uh of our all our workloads and we on top of that we try to minimize the dependencies on the uh on what we can trust really. Um so uh any security system if you do end to end encryption or any kind of encryption there is a huge problem is key management. So the first step is like I want to tell you how we manage the key. So we start with the uh the key as I mentioned before starts on the phone and it leaves persisted on the phone. Then the phone connects to our back end and runs very sophisticated attestation pipeline uh that verifies both integrity and that the specific workload is inside of public uh transparency log. We use six store for our transparency log and anyone can go there and try to look and verify that this workload is genuine. uh the the method is too complicated to include in this uh talk but we will publish details uh at some point. Uh once the uh once uh at the station was finished we the the client shares with the our main front end back end and back end then replicates this key with uh similar nodes uh that runs within our confidation compute because we can't leave the unencrypted data out of our perimeter uh all our we run our own inference too. So this puts us a little bit uh more complicated task uh than typical AI company. We run like all kind of models, all kind of inference uh uh software and uh so um yeah and we don't replicate code to this inference node. We like replicate only on specific ones limiting the scope of what we can do. And on top of that we introduced everywhere where we have the keys in the memory uh uh the forced expiration of seven days. Uh we picked the seven days because we think it's like how much realistically the time horizon horizon for the like something useful can be done for the user. uh 24 hours will be too low because you can like not open your phone for like 24 hours something will be missed and like so we pick like about seven days.
</details>

#### 安全发布流程与智能体物理沙箱化控制

在大型科技公司中，如何确保部署的软件不会引入后门或漏洞是一个巨大的安全命题。Bee 团队设计了一个**双重安全系统**（Two-Tier Security System: 将系统权限与审计链条分为两层独立管控的设计），其中一个独立的隐私审计团队独立负责隐私策略和透明日志管理，而研发团队的发布受到该团队的硬编码公钥限制，且任何变更都必须通过高层签署。

为了平衡安全审计的高要求与快速部署的需求，团队将镜像拆分为底层的**基础镜像**（Base Image: 包含测量引导、清单校验等核心安全度量工具）和顶层的应用清单。通过与两家顶尖外部安全机构的合作，Bee 确保了所有发布的镜像均可追溯审计。虚拟机在完成自检后，会通过私有**证书颁发机构**（Certificate Authority: 签发和管理数字证书的权威机构）将度量和透明度证明直接嵌入 TLS 证书中。整个云端机密推理代码极度精简，仅包含约 2 万行用**内存安全语言**（Memory-Safe Language: 具有自动内存管理、防止缓冲区溢出等漏洞的编程语言，如 Rust 或 Go）编写的代码，且完全基于成熟的工业级标准，不自行发明加密算法。

此外，在探讨如何控制或“驯服”AI 智能体以防其失控时，Steve 指出，试图通过微调或提示词来防范恶意行为是徒劳的，唯一可行的方法是实施物理上的**沙箱隔离**（Sandboxing: 限制软件执行权限的硬件级或操作系统级隔离机制），从底层切断其破坏系统的物理通道。

<details>
<summary>Original English</summary>
Um then we need you know we need to ship some something to the production and then the biggest question like how we can well not ship something that will compromise anything. Our goal was to uh build a system that no one inside of uh Amazon will be able to ship anything unnoticed. Obviously the software has bugs have problems but we shouldn't be well being able to ship anything. So we solve this by two uh two tire system essentially. So there is a dedicated team inside of organization inside of uh Amazon and maybe maybe not even one I would say uh that manages the privacy part of this the privacy log or the transparency log our team when we ship the software we can influence them we can't control them and we hardcode their in their signing keys inside of our client apps and our back ends so we can't really uh um uh we as the team we can do this and like it's very very hard and very high level uh um employees need to sign off to any kind of change so it's like at the big company like Amazon it's virtually impossible really um and uh and we do this in two parts because it's this process too slow so we split it in two parts so like the first one is to build the base image which we put some kind of base software for uh that is needed for our own team like the tools that measure the boot, measure the manifest, measure workloads and data that we need to uh put to the node. Um and um and then when we want to deploy we do the process the same similar time. uh we got the base image and then we deploy the uh to transparency log specific manifest that anyone and uh this setup helps us to be able to security audit companies and inside outside to anyone to well we're not doing this public but like we two like very um high-profile audit companies we work with them all the time um we can provide any image any any data that was deployed ever so we can like trace any possible uh weak spots uh if we like deploy something wrong uh which we do not um then after selfverification of VM it's uh issues a certificate that embeds all encryption pro uh all transparency proofs attestation documents into certificate itself we are using private CA because you can't do this in public certificates because it will populate the public uh transparency log so we had to use the private on um we probably will introduce the uh extra proxy that will do a normal TLS with attestation with like lighter mode. Uh but we don't have this yet. Um yeah, that's essentially what we built. Thank you. Any questions? [applause] >> Any questions? Another going inside as far as Can you repeat? >> Yeah. Sorry. Were there things that had to change your own existing? >> Oh, what changed with like when we joined Amazon? >> Yeah. >> Well, the the big change is that we uh before like you run on Amazon and Amazon gives you pre like guarantees as a customer that they can see your data. But once you inside this changes a lot because you Amazon like so that's why you need like to provide more protection on top of this. So we need to protect from our internal threats too. Uh so that's was a big change. So um before that it was um just kind of easier I would say to configure everything. Um not sure I can tell much honestly. Yes, it's just normal EC2 instances. Yeah. >> Yeah. Yeah. We almost we not using like Yeah. Almost everything we build from scratch. Well, um we tried to use like the existing stuff like that is more like common like popular software. We built uh try we try to minimize amount of code that we produce. So it's I I calculated before this talk it's just like about 20k lines on memory safe language. So it was very small scope that we were able to audit and verify that all this kind of stuff and most of this code is just verifying at the station really and everything else can be like reused and like very we like you know it's very trustworthy I would say software so we didn't try to don't invent uh um yeah we don't try to invent like when when I was a telegram like we reintroduced like build our own crypto and that was like questionable way of doing stuff. So, I try not to do the same at Amazon, obviously. Yeah, that's what we do. >> Any other questions for Steve >> up in the back? Just think about Well, I I just prefer them not to put to the computers uh to personal one. Uh so we we did several experiments how to tame them, not to do bad things. H say I think nothing works except like sandboxing and just not giving them a way to hurt themselves. It's like you know our brains they can't stop the heart at will right so otherwise you know they will be we have much more problems so I think the same we shouldn't give them away to do any harm that's the only way honestly and um yeah and put something in between if they want to change something unfort yeah >> uh I surprised they're not representing this uh right like they're screaming so much about security but they didn't came to this one. Uh uh I'm not I tried open claw. It's like it was once they started to try to tighten this down it became much less use useful. Um so I think their approach is not really that good. So I would love to have wild agent that's that's our goal too but we try to just deploy the sandboxer for specific agent and it will just they just can't do much of the stuff. Everything else fails unfortunately. >> Cool. All right. Well, thank you so much, Steve, for the presentation. That was amazing.
</details>