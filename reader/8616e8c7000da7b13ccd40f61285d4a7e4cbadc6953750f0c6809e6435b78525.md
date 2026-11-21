---
author: AI Engineer
date: '2026-06-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zDGHt0LB-dA
speaker: AI Engineer
tags:
  - serverless-computing
  - gpu-infrastructure
  - cloud-deployment
  - developer-tools
  - workflow-orchestration
title: 不离开 IDE 的 GPU 云端部署：RunPod Serverless 与 Flash SDK 实战
summary: 在本次演讲中，RunPod 的 Audrey 展示了如何使用 Flash Python SDK 在本地 IDE 中直接进行 GPU 云端部署和测试。通过生动的图像生成案例，她解释了 RunPod Serverless 如何简化开发者的迭代流程，并介绍了其灵活的工作流编排与秒级计费的云基础设施优势。
insight: ''
draft: true
series: ''
category: deployment
area: tech-engineering
project: []
people: []
companies_orgs:
  - RunPod
  - Nvidia
  - Google
products_models:
  - Flash SDK
  - Stable Diffusion XL Turbo
  - DreamShaper
  - Qwen 3
  - Gemini Nano 2
media_books: []
status: evergreen
---
### 认识 RunPod 与用户交流

**Audrey**: 大家好。我是 Audrey。我在 **RunPod** 工作。你们中有谁参加了我早上的那场分享吗？好的，很好。因为接下来的开场白是一样的，但我随后要展示的内容会有一点不同。有人听说过 RunPod 或者以前使用过 RunPod 吗？你用过？你介意我问问你是如何使用我们的产品，或者以前是怎么听说我们的吗？

<details>
<summary>Original English</summary>

[music]

**Audrey**: Hey everyone. I'm Audrey. Um I work at RunPod. Have Were any of you in my earlier session? Okay, good. Cuz then I'm going to sit This intro is the same, but what I'm going to show is a little bit different. Has anyone heard of RunPod or used RunPod before? You have? Do you Do you mind if I ask you um how you've used us or heard about us before?
</details>

**Yunus**: 我想到了大学。我们有一些 RunPod 的额度，所以我把它用来做模型训练，以及大语言模型（LLM）的训练。

<details>
<summary>Original English</summary>

**Yunus**: I thought about university. We have some RunPod credits, so I I use this as a yeah for better than training and LLM training.
</details>

**Audrey**: 好的，在你的大学里？你在哪所大学就读呢？

<details>
<summary>Original English</summary>

**Audrey**: Okay, at your university? And where do you go to uni?
</details>

**Yunus**: 牛津大学（Oxford）。

<details>
<summary>Original English</summary>

**Yunus**: Uh you Oxford.
</details>

**Audrey**: 牛津大学。我曾经在那边度过一个暑假的海外交流。那里非常棒。好的，很喜欢。那么，你的名字是？

<details>
<summary>Original English</summary>

**Audrey**: Oxford. I did a study abroad there one summer. It's awesome there. Okay, love it. Okay, and your name is?
</details>

**Yunus**: Yunus。

<details>
<summary>Original English</summary>

**Yunus**: Yunus.
</details>

### RunPod 解决的基础设施痛点

**Audrey**: Yunus。好的，所以 Yunus 可能对这些已经有一点了解了，但我还是会给大家做一个简短的介绍。我们是做什么的呢？我们是一家 AI 云基础设施公司。我们的使命是为开发者构建能够扩展其 AI 工作负载的底层平台。基本上，这意味着我们提供硬件，我们提供 GPU 和计算能力。我们让大家能够非常轻松地带上自己的代码、带上自己的模型，并尽可能快地进行部署。我们不希望你们把时间花在配置基础设施和思考如何进行容量扩展（scaling）这样的事情上。

<details>
<summary>Original English</summary>

**Audrey**: Yunus. Okay, so Yunus might know a little bit about this already, but I'll I'll I'll talk you guys through a little intro. Um what do we do? We're a AI cloud infrastructure company. Um and our mission is to build the foundational platform for developers to scale their AI workloads. And basically what that means is um we bring the hardware, we bring the GPUs and the compute. Um we make it easy for you guys to bring your code, bring your models, and deploy as quickly as possible. We don't want you spending time um configuring infrastructure and thinking about things like um scaling.
</details>

**Audrey**: 这就是 RunPod 存在的原因。我们交谈过的许多团队，他们都在应对同样的挑战——他们在基础设施上花费的时间，比在模型上花的时间还要多。比如对齐 **CUDA** 版本，搞清楚哪些版本的 **PyTorch** 能够完美兼容运行。还有哪些新的 GPU 型号（SKUs）已经被测试过，以及需要不断去排查那里的系统漏洞（bugs）。我们试图接管大部分这样的配置难题，这样你们就可以完全专注于训练模型或者构建应用程序。

<details>
<summary>Original English</summary>

**Audrey**: Why RunPod exists. A lot of teams that we've talked to, they're all wrestling with the same thing that infrastructure They're spending more time with the infrastructure than then they are with the models. So things like CUDA version um alignment, like what versions of PyTorch run well together. Um which which uh new the GPU uh SKUs like have been tested and like keep figuring out the bugs there. So a lot of that is are things that we try to take that um configuration problem away from you guys, so you guys can just feel um focus on training your model or building your apps.
</details>

### 公司创立背景与惊人的发展里程碑

**Audrey**: 讲一点关于我们公司的小背景。这是 Zenin 和 Pradeep，我们的两位创始人。他们在 2022 年创立了 RunPod。他们曾经有过一次失败的加密货币挖矿创业经历，因此他们在地下室里闲置了一堆 GPU。他们构建了一个原型系统，而这正是今天 RunPod 的雏形。他们仅仅是在 Reddit 上发了个帖子问：“有人想要用一些免费的 GPU 来换取反馈吗？”这正是我们公司最初的起步方式。从那时起，我们就一直在公开的社区环境中进行建设。

<details>
<summary>Original English</summary>

**Audrey**: And a little bit of a backstory about our company. So this is Zenin and Pradeep are two founders. Um they started RunPod in 2022. They had a failed crypto mining venture, so they had a bunch of spare GPUs in their basement. Um they built a prototype of what is the foundation of RunPod today. And they just posted on Reddit and said, "Does Does anyone want some free GPUs um in exchange for feedback?" And that is literally how our company started. And ever since then we've been building with in public with the community.
</details>

**Audrey**: 因此，我们从公司成立的最早阶段就开始创造收入了。这在业内是非常、非常罕见的。而到了今天，我们的平台上大约有 **500 名开发者**（译注：此处应为 50 万，语音识别误差）。我们在横跨 10 个国家的 30 多个数据中心提供服务。在欧洲，这包括法国、罗马尼亚、冰岛（如果冰岛算作欧洲一部分的话）。另外还有亚太地区。最近，我们达成了一个相当大的里程碑，那就是 **1.2 亿美元的年度经常性收入（ARR）**。

<details>
<summary>Original English</summary>

**Audrey**: Um so we've been revenue generating from the very beginning. Um which is very very rare. Um and even today we have around 500 developers on our platform. We're in 30-plus data centers across 10 countries. Um in Europe that includes France, Romania, Iceland, if that's part of Europe. Uh Asia Pacific. Um and we recently hit um a pretty big milestone of 120 million in annual recurring revenue.
</details>

**Audrey**: 快速浏览一下我们拥有的一些客户。你可能会有些惊讶地发现，其中一些是 AI 原生公司，同时也有一些大型企业。他们共同的底线在于，他们都需要灵活且可靠的 GPU 基础设施。所以我绝对会说，我们正在跨越自身的重量级，去挑战更大的市场。

<details>
<summary>Original English</summary>

**Audrey**: This is just a quick glance of some of the customers that we have. You might be surprised seeing that some of these are AI native companies um and some large enterprises as well. And kind of the bottom line of what they have in common is that they need flexible and reliable GPU infrastructure. So um I definitely would say we're punching above our weight class.
</details>

### RunPod 四大核心产品线

**Audrey**: 我快速地从高层次介绍一下，根据你试图完成的任务，在 RunPod 上有不同的构建方式。如果你需要一个更具持久性的虚拟机（VM）环境，那么 **Pods** 是一个很好的选择。你可以按需租用一个 Pod，按秒计费，一旦你完成工作，你可以把它完全销毁，然后重新开始。Pods 适用于你需要预留 GPU 的情况。只要你的 Pod 在运行，那个 GPU 就是你的，没有人能把它从你那里拿走。

<details>
<summary>Original English</summary>

**Audrey**: Really quick high level um there's different ways to build on RunPod depending on what you're trying to do. Um so if you need a more persistent um VM environment, then pods is a great use case. Um if you you can rent a pod on demand, um pay by the second, and once you're done you can tear it all down um and start again. Pods are if you need um reserved GPU. So as long as your pod is running, then the GPU is yours and no one can take it away from you.
</details>

**Audrey**: **Serverless** 模式则适用于当你已经准备好部署某些东西，并且你更关注扩容能力时——也就是说你的工作负载在频率和负载方面非常多变。我们会帮你自动扩展（auto scale）工作节点，并在没有请求发生时再把它们缩减下来，这样你就不用为任何空闲时间付费。**Clusters（集群）** 是多节点训练的绝佳场景。最后，**Hub** 也是一个你可以部署我们已经为流行模型预先审核过的开源 AI 仓库的地方，比如 **ComfyUI**、**Stable Diffusion**、**vLLM**。如果你只是处于探索阶段，这种方式让你只需点击几下就能极快地上手。

<details>
<summary>Original English</summary>

**Audrey**: Um serverless, if you have if you're ready to deploy something and you and and you care more about scaling, so your workloads are more variable in terms of um frequency and load, um we help you auto scale um your workers for you and scale them back down when you don't have any requests happening, so you don't pay for um any idle time. Um clusters, great use case for training, multi-node. And then hub is also um a place where you can deploy already uh open source AI repos that have already been pre-vetted by us for popular models um like ComfyUI, um stable diffusion, um vLLM. Um and that's one way if you're just exploring uh to just click around and get started really quickly.
</details>

### Flash SDK：打破传统开发迭代的死循环

**Audrey**: 今天我主要讲讲 Serverless。也就是我们刚推出的新产品。我现在要再次快速切换一下显示器，以便镜像我的屏幕。对开发者来说，一个巨大的痛点是：如果他们仍处于迭代或开发阶段，通常当你在编写关于推理模型的代码并且你还在进行测试时，你必须提交一次 commit，将其推送到 GitHub，构建你的 Docker 镜像，从容器注册表把它拉取下来，再将它加载到一台服务器上，并在上面分配好 GPU，然后你才能测试它，看看它是否符合你的预期工作。如果不行，你必须一遍又一遍地重复整个过程，直到它准备就绪。

<details>
<summary>Original English</summary>

**Audrey**: Uh I'm going to talk about serverless um today. And the product that we just And I'm going to switch my displays again here really really quick so we can mirror my screen. So one of the things that is a huge pain for developers is if they're still in the iteration or the development phase. So normally um when you are working on let's say some some code around your um inference model, and you're still testing things out you have to make a commit, push it to GitHub, um build your Docker image, um pull it down from the container registry, um and then load it onto uh a server, and then allocate a GPU on it, and then you get to test it and see if it's working as you expect it. And then you do that all over again until until you're ready.
</details>

**Audrey**: 所以 **Flash** 试图解决的问题——Flash 是我们的 Python SDK——就是我们希望消除所有那种冗长的迭代周期，让你能够直接从本地开发环境中将你的函数部署在 GPU 上。我很快放大一下屏幕。关于 Flash，你需要知道的一切都在这小小的一段话里：你只需要有一个常规的异步 Python 函数，加上我们的 `@flash.endpoint` 装饰器，它就会自动将你函数内部的所有内容打包并部署到 GPU 云端。而在其周围的一切，比如你的主函数、你写的任何辅助函数，依然全部运行在你本地的开发环境中。但如果你需要用到 GPU 计算，那部分则可以在云端无缝运行。

<details>
<summary>Original English</summary>

**Audrey**: So the problem that Flash is trying to solve here, and Flash is our Python SDK, is that we want to eliminate all of that iteration cycle so that you can um deploy your function on a GPU right from your local development environment. And I'll zoom in here really quick. So this is all you need to know about Flash in one little paragraph. Is it's you have a regular async Python function, you add our flash endpoint decorator, and it's going to deploy and package everything inside your function onto a GPU cloud. Everything around it, your um main function, any helper functions that you have, those all run on your local development environment, but if you need GPU compute, that that can run um on the cloud.
</details>

**Audrey**: 并且我们支持热加载文件重载（hot file reload）。所以如果你在应用程序的任何地方更改了任何内容，它就会立即被重新打包并推送到云端，你可以极其快速地进行测试和迭代。我马上就给大家展示一个具体的例子。

<details>
<summary>Original English</summary>

**Audrey**: And you can we have hot mod uh file reload. So if you change anything in your application anywhere, then it gets repackaged and pushed up immediately and you can test and iterate super quickly. And I'm just going to show an example of this.
</details>

### Flash 现场代码演示与图像生成

**Audrey**: 好的。在这里我有一个叫做 `generate_image` 的函数。逻辑很简单，我正在加载 PyTorch。我正在加载一个预训练的 Stable Diffusion 模型：**Stable Diffusion XL Turbo**。它非常适合快速生成图像，生成后我会将图像保存下来，并以 base64 编码的形式将其返回。我现在就可以在这里运行它。我已经安装好了我所有的依赖项。我已经启动了一个 Flash 项目。我要运行 `flash run image_generation.py`。实际上我要做的是使用一个微小的 `flash run` 脚本。这个 `flash run` 会在此处启动一个本地开发服务器。它本质上只是一个 FastAPI 服务器。然后我就可以向这个端点发送请求了。

<details>
<summary>Original English</summary>

**Audrey**: Okay. So I have a function here, generate image. Simply I'm loading PyTorch. I'm loading a pre-trained stable diffusion model, stable diffusion XL Turbo, really great for fast uh generation of images, and I'm going to save the image down and that going to return it base64 encoded. So I can run this right now here. I've already um installed all my dependencies. I already have a flash project going. I'm going to flash run uh image generation.py. And what I'm going to actually do is I have a little flash flash run. So flash run spins up a local development server here. Uh it's just a fast API server. And I can send my request here to this endpoint.
</details>

**Audrey**: 我会非常快地完成这个操作。直接进入我的项目。这只是一个小的辅助脚本，它将发送一个 POST 请求，然后解码返回的图像，这样你们就能实实在在地看到它生成出来的样子了。端点地址是 `image_generation_async`。好了。让我们传给它一个提示词。能请现场观众帮个忙吗？我们今天想生成什么图像？无论什么都可以。随便说点什么。

<details>
<summary>Original English</summary>

**Audrey**: And I'm going to do that really quickly. Just get to to my project. And this is just a little helper script that's going to send a post request to it and then um decode that image so that you guys get actually get to see what it looks like once it's generated. And it was image generation async. Here we go. And let's pass a prompt to it. Can I get a help from the audience? What do we want to generate today? Literally anything. Anything random.
</details>

**Audience**: 飞在天空中的猫（Cats flying in the sky）。

<details>
<summary>Original English</summary>

**Audience**: Cats flying in the sky.
</details>

**Audrey**: 好的。飞在天空中的猫。天空看起来什么样？现在是一天中的什么时候？

<details>
<summary>Original English</summary>

**Audrey**: Okay. Cats flying in the sky. What does the sky look like? What time of day is it?
</details>

**Audience**: 多云的。在伦敦。是的。

<details>
<summary>Original English</summary>

**Audience**: Cloudy. Um in London. Yeah.
</details>

**Audrey**: 在一个多云的日子里，飞行在伦敦某处的天空中。我的参数传得没错。他（指前排观众）看得好仔细。他在帮我进行现场除错（live debug）。我太喜欢这样了。谢谢你。

<details>
<summary>Original English</summary>

**Audrey**: Flying in Flying on a cloudy day in the sky somewhere in London. And I passed it correctly. He's He's looking at it so closely. He's helping me debug live. I love it. Thank you.
</details>

**Audience**: [笑声]

<details>
<summary>Original English</summary>

**Audience**: [laughter]
</details>

**Audrey**: 在深色模式下确实有点难看清，但我确实传递了 URL。

<details>
<summary>Original English</summary>

**Audrey**: It's kind of hard to see in dark mode, but uh I passed URL and that's true.
</details>

**Audience**: 你是不是把参数写到 localhost 后面就停了？是不是我的 HTTP 写错了？

<details>
<summary>Original English</summary>

**Audience**: Did you stop after localhost? Uh Is it my HTTP?
</details>

**Audrey**: 好的，搞定了。好的，回到本地开发服务器。它已经接收到了请求。它启动了任务。它已经将任务排队了。我们只需等上几秒钟，看看它是否顺利完成。

<details>
<summary>Original English</summary>

**Audrey**: Okay, there we go. Okay, going back to the local dev server. It sees the request. It started the job. It's queued it. And we're just going to wait for a second to see if it finishes.
</details>

### 装饰器的高级参数与热切换模型

**Audrey**: 趁着它在运行，让我再次将大家的注意力带回代码上。为你们放大一点。这个 `endpoint` 装饰器，正是所有魔法发生的地方。我为我的端点传递了一个名称。我指定了一个 GPU 家族（GPU family）。所以这里用到的是 **Ada 80 pros**，这其实是 Nvidia H100 显卡的各类变体。我能够将我的最大工作节点数（max number of workers）指定为 5，意味着我可以让最多 5 个节点并发运行。我在这里配置了一个活跃节点（active worker），这意味着总会有一个实例保持一直运行，时刻待命。

<details>
<summary>Original English</summary>

**Audrey**: And so while that's happening, let me bring your attention back to Make it bigger for you guys. Um, the endpoint decorator. So this is where all the magic happens. I have passed a name for my endpoint. I specify a GPU family. Um, so the Ada 80 pros, these are different variations of Nvidia H100 cards. Um, I can specify my max number of workers to be five, so I can have at max five of them running at once. Um, I just put one active worker, so this is one that's always going to be running and always on.
</details>

**Audrey**: 然后这里出现了一条报错（a dragon）。它没有接收到我的提示词，大概是因为我没有把它作为一个命令标志（flag）传递进去。加上 `--prompt`。这就对了。好的，现在它肯定在生成飞行的猫了。

<details>
<summary>Original English</summary>

**Audrey**: And that's definitely a dragon. And it didn't take my prompt probably because I didn't I not pass it as a I didn't pass it as a flag. Prompt. There we go. Okay, now it's definitely generating cats flying.
</details>

**Audience**: [哼笑声]

<details>
<summary>Original English</summary>

**Audience**: [snorts]
</details>

**Audrey**: 好的，我们回到 `endpoint` 装饰器。除此之外，它还有其他各种不同的配置项，比如可以配置超时时间（timeout），即一个 worker 处于空闲状态多久后会被回收。好了，结果出来了。好的，各位，这看起来太糟糕了。

<details>
<summary>Original English</summary>

**Audrey**: >> Okay, back to the endpoint decorator. Um, and then there's other different configurations for timeout, which is how long um, a worker is idle. Here we go. Okay, this looks terrible, guys.
</details>

**Audience**: [大笑]

<details>
<summary>Original English</summary>

**Audience**: [laughter]
</details>

**Audrey**: 它们确实是猫。但它们是非常抽象的猫。并且，我不是伦敦人，但或许有人能告诉我，这看上去像不像一个伦敦风味的烟囱？也许吧。好的，总之我不喜欢……我不喜欢刚才生成的效果。所以接下来我们要做的，就是把我们的模型换掉。

<details>
<summary>Original English</summary>

**Audrey**: They are cats. They're abstract cats. Um, and I'm not from London, but maybe someone can tell me if this looks like a London chimney. Maybe. Okay, so I don't I don't I don't like I don't like what just happened. So what we're going to do instead is we're going to switch out our model.
</details>

**Audrey**: 我打算直接将这里的这行代码注释掉。然后在这下面，我们将模型替换为 **DreamShaper**，这是一款基于 Stable Diffusion 1.5 微调的模型。考虑到 Stable Diffusion XL Pro 更多是为了最极致的生成速度而优化的，我认为这一个（DreamShaper）能为我们生成出质量好得多的图像。并且它在处理更偏向艺术和插画的风格上表现得特别出色。我已经更改了里面的部分参数。它的推理步骤（inference steps）会多一些。我们把它设为 25。高度和宽度设为 10x24，没问题。让我们再把相同的请求发一次。我们看看会发生什么。会有什么不同呢？

<details>
<summary>Original English</summary>

**Audrey**: So I'm just going to comment out this code here. And then down here let's swap in DreamShaper, which is a fine-tuned um model based off of Stable Diffusion 1.5. Um, so this one is while where Stable Diffusion XL Pro is um, more optimized for just quick generation, I think this one is going to generate a more uh a better quality image for us. And it's specifically better for kind of like more art and illustrator styles. So I've changed some of the parameters in it. It's going to have a few more um, inference steps to it. We're going to set that to 25. Height and width 10 by 24, that's fine. And let's just send the same request again. And let's see what happens. What's different?
</details>

**Audrey**: 再次强调，让这一切变得如此迅速的原因在于，我并没有去修改代码后提交代码、重新构建 Docker 镜像、把它上传到远端仓库，然后再次分配 GPU 基础设施；相反，所有这些操作都完全发生在这个本地的 IDE 当中，我永远都不需要切出屏幕。这种体验很赞，对吧？大家喜欢这种方式吗？好的。

<details>
<summary>Original English</summary>

**Audrey**: So again, what made this really fast is instead of making a code change, committing it, rebuilding my Docker, uploading it somewhere, and then allocating GPU infrastructure, all of this is happening right here from my IDE and I never have to leave. This is good, right, guys? We like this one? Okay.
</details>

### 用大语言模型重构图像生成管线

**Audrey**: 还有最后一件我想展示给大家的事，为我们今天的演示画个圆满的句号。我认为当你在尝试部署时，像 Flash 这样的开发者工具能发挥巨大差异的场景在于，你通常不会只简单地向单个模型发起一次请求。一切的核心都在于围绕模型构建的 **编排代码（orchestration code）**，对吧？所以我在这里提前准备好了一整套生成管线（pipeline）。

<details>
<summary>Original English</summary>

**Audrey**: So one more one last thing that I'm just going to show you guys to round things out is I think where um, using a developer tool like Flash makes a big difference is when you're trying to um not just like make one single call to one model. It's It's all about all the orchestration code around it, right? So I have here a pipeline that I've pre-prepared.
</details>

**Audrey**: 这个管线的作用是，它不再由我亲自去构思并写下每一个提示词，而是将请求发送给一个早已托管在公共端点上的 **Qwen 3**（译注：语音识别拼作 Gwen 3）。Qwen 3 会全权替我生成那些丰富细致的提示词。然后在这之后，它会将请求转发到正在我们自己端点上运行的 DreamShaper 里去。再往后，还会经历最后一道工序：它会将请求发送给 **Gemini Nano 2**（译注：此处语音被误识别为 Nano Banana 2，系指代谷歌的 Premium 级模型），这是一款非常擅长将照片拼合与重新构图（composing）的高级谷歌模型。我希望我能组合出几张非常酷的创始人照片，并在演示结束后发给他们。好的。

<details>
<summary>Original English</summary>

**Audrey**: Um, and what it's going to do is instead of me generating and writing out every prompt, um, it's going to send a request to Gwen that's already hosted on a public endpoint. Um, and Gwen is Gwen 3 is going to generate all the prompts for me. Um, and then after that it's going to send that to our um, DreamShaper running on our endpoint. And then um, after that there's one more pipeline that it goes through. It's going to send the request to Nano Banana 2, which is a premium Google model that's really good at composing photos together. Um, and I'm hoping that I can compose some cool pictures of our founders and I can send them to them after this demo is done. Okay.
</details>

**Audrey**: 现在我们运行一下这个完整的管线。核对一下配置。好的。提示词：两个男人走在伦敦的街上，今天是个阴天。阴天里他们俩面部的特写镜头。对于这两个男人，大家还有任何其他的要求吗？他们长什么样？或者他们正在做什么事情？

<details>
<summary>Original English</summary>

**Audrey**: Um Now let's run the whole pipeline here. Check. Okay. Prompt two men walking in London on a It is cloudy today. Cloudy day close-up of their faces. Um, any other requests for these two men? Um, how do they look? Like are they doing something?
</details>

**Audience**: 戴着眼镜，对。

<details>
<summary>Original English</summary>

**Audience**: Glasses, yeah. Okay.
</details>

**Audrey**: 好的。两个戴着眼镜的男人的面部特写。好的，让我们进行生成。我们先生成三张这种照片，然后再利用管道把它们组合到一起。好的。

<details>
<summary>Original English</summary>

**Audrey**: Two men with glasses close-up of their faces. Okay, and let's generate. Let's generate three of those and let's compose it together. Okay.
</details>

### Serverless 模式的具体计费规则

**Audience**: 那么，它在定价和计费方面到底是如何运作的呢？

<details>
<summary>Original English</summary>

**Audience**: So So how does it work in terms of pricing?
</details>

**Audrey**: 定价，当然可以聊聊。对于发送给端点的每个请求，你仅仅只需要为该请求实际运行的时间段付费。我之前承诺过这场分享全部都会在终端里进行，但我现在要切回网页控制台，只为了让你们看看幕后究竟有什么正在运行。

<details>
<summary>Original English</summary>

**Audrey**: Pricing, sure. Um, so every request that we send to it, you're only charged for how long that request is running. So let's see. I'm going to I said this whole session was going to be only in the terminal, but I'm going to go back into the console just to show you what's what's running.
</details>

**Audrey**: 让我们看看。这是我们从终端创建的那个端点（endpoint）。这是正在执行任务的 workers。我想我们之前设定了最多 5 个 worker，所以这里大概配给了五到六个。其中有三个正在运行，因为我请求生成三张照片。你看，这就是 **正常运行时间（uptime）**。而这也正是向你计费的依据所在。让我查一下目前一块 H100 显卡的成本，是 **每秒 0.00116 美分（cents per second）**。

<details>
<summary>Original English</summary>

**Audrey**: Let's see. This is the endpoint that we created from the terminal. Um, here are the workers. I think we said like five workers, so we have about five or six here that are provisioned. Um, three of them are running cuz I asked for three photos. Um And so this is uptime. This is what you're being charged for. And let me see the cost of an H100 right now is 0.00116 cents per second.
</details>

**Audience**: 这种定价跟 Pod 是一样的吗？还是说这两者的价格会有一些不同？

<details>
<summary>Original English</summary>

**Audience**: Is it the same as for a pod or is it or is is the pricing a bit
</details>

**Audrey**: Serverless 与 Pods 在定价上确实有少许不同，因为如果你选用 Pods，你是享受不到任何与之匹配的自动扩容能力的。所以在 Serverless 上会有一定程度的溢价（premium）。因此我们通常的建议是，如果你仍处于实验摸索阶段，那么要么就只配置一个非常低的 worker 数量，要么直接从 Pods 起步，对吗？因为当你在做实验时，你可能只需要极为有限的 GPU，每次一张，或者每次两张。而 Serverless 专为如下场景设计：你需要数百个 worker 跑在数百张 GPU 上，并且你希望它们能够跨越不同数据中心呈分布式部署，以此获取极高的可用性。

<details>
<summary>Original English</summary>

**Audrey**: Pricing is a little bit different for serverless versus pods because pods um, you don't get any of the scaling with it. So there's a little bit of a premium for serverless. So what we usually recommend is if you're still um, experimenting then either start with a very low worker count or start with pods, right? Cuz when you're experimenting you might only need limited number of GPUs, one GPU at a time, two GPUs at a time. Um, serverless for when you need hundreds of workers running on hundreds of GPUs and you want them distributed for a better availability across different data centers.
</details>

### 输出最终作品

**Audience**: [笑声]

<details>
<summary>Original English</summary>

**Audience**: [laughter]
</details>

**Audrey**: 好的各位，结果出来了，这就是我们最终要展示的作品。这是我们最初粗糙的提示词：两名 [轻笑] 戴着眼镜的男子，在阴天里行走于伦敦，面部特写。请看左侧，这是基于 Qwen 3 帮我们重写的“提示词工程”后，由 DreamShaper 生成的画面。所以它远比我随手输入的提示词要精妙得多。它提供了大量非常优秀的提示细节，因为我知道你们看得不是很清楚，我可以把这段描述念给你们听：

<details>
<summary>Original English</summary>

**Audrey**: >> Okay, guys, here's here's the here's our final presentation. So this was our original prompt. Two [snorts] men with glasses walking in London on a cloudy day, close-up of their faces. So on the left, this is what um, DreamShaper generated based off of the um, prompt engineering that Gwen 3 did for us. So it's a lot better of a prompt than what I sent in. It has a lot better cues about notes on like I can read it out to you since I know it's hard to see.
</details>

**Audrey**: “若有所思的表情与饱经风霜的脸庞，背景中柔焦的云层，点缀着灰色与深蓝色的柔和城市色调，极其标准的阴天光线。” 然后在屏幕右侧，则是最终合成后的照片。这……这是一张 Pradeep 非常帅气的面部照片。而不知何故，旁边生成了一张看起来非常有年代感的 Zed 的老照片。我会往下滚动一点来展示，这是我发给它做参照底图的照片。

<details>
<summary>Original English</summary>

**Audrey**: Um, thoughtful expressions and weathered faces, soft focus on background clouds, muted urban palette with grays and deep blues, overcast lighting. Um, and then on the right is the final composed photo um, of This This is a hand This is a very handsome picture of Pradeep. And this is somehow a very old photo of Zed. And I'm just going to scroll down to show you that this is the reference photo that I sent it.
</details>

**Audrey**: 但总的来说，是的，我只是想向大家展示一下，这就是让你能多快实现功能部署的方式。你可以安心地在本地开发环境中完成这一切。你可以使用开源模型。你同样也可以引入专属于你自己的私有模型。实机操作起来真的充满了乐趣。所以，谢谢大家今天抽出时间来听我的分享。

<details>
<summary>Original English</summary>

**Audrey**: Um, but overall um Overall, yeah, I just wanted to show you guys like this is how you can get started really quickly. Um, you can start in your local development environment. You can use open-sourced models. You can use bring your own model, private model. Um, and this was really fun to do. So, thank you guys for hanging out with me.
</details>

**Audience**: [热烈的掌声]

<details>
<summary>Original English</summary>

**Audience**: >> [applause]
[music]
</details>