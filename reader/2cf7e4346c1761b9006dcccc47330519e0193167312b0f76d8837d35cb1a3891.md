---
author: AI Engineer
date: '2026-05-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=F1DYkY1BlfM
speaker: AI Engineer
tags:
  - containerization
  - ai-agent
  - kubernetes
  - podman
  - security
title: 容器化 OpenClaw：从本地 Podman 到大规模 K8s 的 AI 智能体部署实践
summary: Red Hat 工程师 Sally Ann O'Malley 分享了将 AI 智能体 OpenClaw 容器化的核心优势与实战经验。文章涵盖了利用 Podman 管理 API 密钥安全性、通过容器实现环境一致性，以及在 Kubernetes 和 OpenShift 上进行大规模部署的愿景，旨在构建可重现、安全且可扩展的 AI 工作流标准。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Sally Ann O'Malley
companies_orgs:
  - Red Hat
  - OpenAI
  - NVIDIA
products_models:
  - OpenClaw
  - Podman
  - OpenShift
  - Kubernetes
  - Gemma
  - Anthropic
media_books: []
status: evergreen
---
### 转型之路：从基础设施安全到 AI 智能体实验室

作为在 Red Hat 深耕十年的资深工程师，Sally 的职业生涯见证了从基础容器安全、Kubernetes 到 OpenShift 的技术演进。然而，过去几年的 AI 浪潮彻底改变了她的工作重心，使她从传统产品线转入了更具探索性的**新兴技术部门**（Emerging Tech Org）。在这里，工作不再受限于单一产品，而是围绕着 Python、Markdown 以及无数的聊天机器人展开。

当她初次在 GitHub 上遇到遵循 MIT 协议的 **OpenClaw** 时，其作为 AI 智能体的潜力立即引发了她的兴趣。尽管在企业内部，引入此类工具曾一度面临“安全噩梦”的质疑，但 Sally 坚持认为，容器技术的本质就是为了安全地运行任何应用程序。这不仅是 Red Hat 的核心价值，更是展示如何在大规模生产环境中安全管控 AI 负载的绝佳契机。

<details>
<summary>Original English Source</summary>

Hey, um I'm Sally. I work at Red Hat. I've been there for about 10 years and uh the first 7 years, awesome, totally cool. I was working on containers and uh Linux security stuff and Kubernetes. Um in OpenShift. That's what I did for the first 7 years. And then uh about 3 years ago, well about 5 years ago, I moved to the emerging tech org and that was awesome, too, because now I'm not totally tied to a product. I get to just work on what I want. I get to just try out new things. Awesome. And then about 3 years ago it was like all AI all the time, everything AI. I know not I knew there was a data science team at Red Hat. I had no idea what they did. Machine learning something something. Um so, I, you know, started doing AI and uh yeah, it was a lot of Python and markdown. Every single thing was like, "Okay, another chatbot, more python, more markdown." Um but uh here we are today and what a what a crazy awesome world we're in. Um so, the first time the first time I came across OpenClaw, I was home for a week on a like a staycation, took a few days off and uh a malt book happened and I was like, "What the What is this? I'm totally trying this." And so, I went and found it on GitHub. The first thing I do is I look at the license. Uh MIT, awesome. Uh OpenClaw, I'm like, "I'm so going to install this on OpenShift right now." And so, for the next few days I just kind of built the image, um ran it locally in a container, put it on OpenShift, just played around with it. Went back to work and like, "Guys, check out OpenClaw. This is so cool." And a couple people on Slack are like, "It's a security nightmare. Do not use OpenClaw. Don't put it on the work laptop." I'm like, "Guys, what have I What have I been doing the past 10 years? Is I'm We're We can take any application and run it securely. Like that's what rel is. Like if we can't take an application and run it securely, like come on. This is our golden opportunity to show everyone." And so, Red Hat's coming around to that.

</details>

### 容器化原语：重构 AI 开发的洁净度与安全性

将 AI 智能体（如 OpenClaw）封装在容器中并非仅仅为了时髦，而是基于**可重现性**、**秘密隔离**（Secret Isolation）以及**跨基础设施的可移植性**。Sally 强调，直接在宿主机上运行代码是“肮脏”的，会留下大量难以清理的依赖碎片。

通过容器化，智能体获得了一个自然的**沙盒**（Sandbox），开发者必须显式地定义其对宿主机资源的访问权限。此外，容器与卷（Volumes）的结合为**备份与恢复**（Backup and Recovery）提供了完美的叙事：所有的运行时状态和历史记忆都可以被持久化并定期备份。在实际应用中，Sally 甚至为她的个人智能体（她称之为 Forever Claw）配置了类似 Systemd 的定时备份机制。容器还允许将工具、技能（Skills）和 **MCP 服务器**（Model Context Protocol Servers）统一打包在一个目录中并挂载到镜像内，确保智能体在启动瞬间即具备完整的作战能力。

<details>
<summary>Original English Source</summary>

Um but yeah, so uh this talk is about me running in containers. And so, I wanted to get a list of uh So, I wanted to get a list of why running in containers is the way to go. I run everything in containers. It's kind of foreign to me to take to just run something natively. It's messy. It just puts stuff on my computer that I have to clean up later. I don't like it. Um so, that's one one one thing. Uh and I asked her, you know, why should we run you in container? And uh she said all of that if you were reading, but it's reproducible, you can isolate your secrets, it's portable across infra, I can run on my laptop, I can run it on my X86, I can run it on my Mac, I can run it in Kubernetes. Um backed by volumes, which gives a really nice story for backup and recovery. Uh cuz I love my forever claw and I I back her up every night with uh with uh um like a system D service, whatever it's called on Mac. And um and and you just get that natural uh you just get that natural sandbox when you run something in a container. It's it's, you know, that's that's what it is and you have to be very explicit about what you um give access to, you know, from the host. And so, this Yes, I she loves running in a container. So, that's that's all you need to know. Um it gives her a clean, predictable environment, doesn't have to worry about the OS quirks, stale dependencies. This is literally the definition of why you should run everything in containers. Another another thing that containers do is you can set up a whole agent directory with maybe you run some tools, some skills, some some MCP servers. Uh you can keep those in a directory and mount that whole thing into your container uh and so, when at startup everything's just up and running. So, I do that as well.

</details>

### 凭据防御：Podman Secrets 与 OpenClaw 的双重锁定

在处理 AI 负载时，API 密钥的安全管理是核心挑战。Sally 倾向于使用 **Podman** 而非 Docker，主要得益于其独特的 **Podman Secrets** 功能。这种机制允许将 API 密钥保存为受控的加密对象，而不是暴露在环境变量中。

更进一步，OpenClaw 自身支持 **Secret Reference**（加密引用）特性。这意味着智能体内部使用的密钥实际上只是指向容器外层 Secret 的指针。这种“双重引用”机制能有效防止 API 密钥意外出现在日志或控制台输出中。同样，在生产环境的 **Kubernetes** 中，这种模式可以无缝衔接为 K8s Secrets 引用环境变量的标准化流程。这种架构设计不仅提升了安全性，也为未来大规模、自动化的智能体部署奠定了信任基础。

<details>
<summary>Original English Source</summary>

Oh, no, let's talk about secrets. So, I run everything with Podman, not Docker. Um but in theory you can do anything with Podman and Docker. Except, Podman has this really cool feature called Podman secrets. And you can save your API keys. I'll show that I'll I'll show it off the sides later. You can save your API keys to a Podman secret. And then you mount that secret into the container. And so, it just gives the separation. Your your secrets, your API keys are then just a ref back to the secret. And with OpenClaw, what's really cool is there's like a double that because in OpenClaw there's a secret ref feature and I also use that. So, my API keys are pointer to a secret ref to the outside secret. And uh that's not perfect, but it gives me some peace of mind that I don't I'm not going to be showing my API keys in the logs and everything. And then very similarly, Kubernetes has Kubernetes secrets and same thing, instead of just a straight env var, you have a secret a secret ref to an env var.

</details>

### 愿景与规模化：AI 智能体作为团队标准件

展望未来，AI 智能体将不再是个人的玩具，而是企业工作流中的标准组件。Sally 提到，NVIDIA 的团队已经在利用 OpenClaw 运行 **模型评估**（Model Evals），每位工程师都在 Kubernetes 中运行自己的智能体实例。这使得小团队能够承担起相当于六倍人力的工作量，让工程师能够从繁琐的代码编写中解放出来，专注于更具创意和“跳出框框”的任务。

她构想了一种**企业级智能体分发模式**：新员工入职时，不再需要自行拼凑环境，而是直接获取一个公司预配置的 **OpenClaw 基准镜像**。该镜像预装了公司审核通过的 MCP 服务器、身份认证插件以及特定团队所需的工具链（如 Google Drive 访问权限）。这种基于容器和 K8s 的架构，不仅实现了环境的**可重现入职**（Reproducible Onboarding），更建立了一套跨团队的开发标准。

<details>
<summary>Original English Source</summary>

I think we're heading to a world where these agents, these AI workloads, whatever, are going to be running everywhere. I hope we all can see that. And so, imagine my vision is for uh everybody's OpenClaws to be uh running everywhere and communicating with each other. And uh when and especially in for like business use cases, real real things, not astrology and and Bruins. Uh that opens up the need that the same need to run any application uh in that way is security and and how to do it at scale. And that's what Kubernetes gives you. And you can What I always do is develop something locally and then lift it to Kubernetes. And so, the same story holds for AI workloads or OpenClaw. And I was at PyTorch Con yesterday and um my friend from Nvidia said I could share this. They are running their model evals with OpenClaw. They have about 10 engineers. They each have their OpenClaws running in Kubernetes and uh periodically just checking in with the model evals. And it works so well for them. He said it was like, you know, doing the job of six engineers uh in with with himself. What that is enabling for his team is they get to do fun stuff, interesting stuff. They get to do creative things. And this is what AI is giving me and my team is we can focus on those like outside the box crazy things and you don't have to do the tedious code anymore. This this would be my vision of workplace setup for Open Claw where you maybe have your nice curated baseline Open Claw that as a new hire you you just you get your your base. And what does that have in it? It has your list of company approved MCP servers, your authentication that is approved through your company. It has all of your these skills that are very specific to your team, maybe access to your Google Drive. Like all these things uh that you use every day at work. You can take that and just fan it out across your whole team. And then you can personalize it as as the individual. And that's what this what this setup allows. And so yeah, team standards, portable environments, reproducible onboarding. That's my vision for like Open Claw in the workplace in the future.

</details>

### 实战演示：两秒钟启动生产级智能体实例

在演示环节，Sally 展示了她开发的本地安装工具，只需几秒钟即可通过 Podman 启动一个新的智能体容器。安装过程高度模块化，用户可以自定义容器名称、端口映射、Secret 映射（如 OpenRouter API 密钥），并选择 **Gemma** 或 **Anthropic** 作为主/备用模型。

特别值得注意的是，该工具支持集成 **OpenTelemetry** 和 **Jaeger** 进行可观测性监控，并支持配置 **SSH Sandbox**，让智能体在受控的远程工作空间中执行命令。对于 Mac 用户，Sally 提醒道，由于 macOS 上的容器实际上运行在虚拟机中，因此在容器内嵌套启动容器（Docker-in-Docker）会比 Linux 系统复杂得多。尽管如此，通过预定义的 YAML 和安装脚本，从本地 Podman 开发环境平滑迁移到 Kubernetes 集群（如 Kind 或 OpenShift）已成为现实。

<details>
<summary>Original English Source</summary>

So in order to run this local installer here which I think I have here. Yeah. It's just a NPM run dev. Now The one thing I don't like about this is when I'm on my Mac I can't run this in a container. Containers only run on Linux. So when you're running a container on your Mac, you are always running in a virtual machine. So it gets a little tricky when you want to take a container and spawn another container from it. But anyways, here we go. So if I wanted to run a local instance and I have a couple running now. Spin up Joe. All I all I do to set up my pod is I just give it a name. These Podman secret mappings I want to show you here. So you can see I have these set up already. They're just on my system. They're like envars, but they're not envars cuz they're contained. Um these are my API keys. And what happens with this installer is it takes If you're on Docker, this should work with Docker. It's got Podman written all over it, but I've designed it to work with Docker, too. For every current credential, create a secret ref. It creates that separation of uh running your secret within Open Claw or kind of just a pointer to it. And then uh your providers. So I'm going to start with Open Router cuz I have been playing with Gemma. And then as a fallback I'll use Anthropic. And then because I do observability at work uh I was like, "I'm going to give the option to set up an Open Telemetry collector with Jaeger." Another feature is SSH sandbox here we'll deploy. The SSH sandbox in Open Claw is super cool. You give it SSH keys and known hosts to to wherever you want and it it runs all of its commands in that workspace. So look, I just spun up a Podman container. People say it's hard to spin up Open Claw. It took 2 seconds and I was babbling through the whole way. It could have taken 1 second. Kubernetes. And you can do the same thing with Kubernetes just as easy. It just, uh, it it's connected right now to my kind cluster. And if I go over, I can access my Kubernetes claw very easily as well.

</details>