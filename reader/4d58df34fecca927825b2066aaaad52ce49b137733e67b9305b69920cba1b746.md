---
author: Latent Space
date: '2026-10-22'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=IiZ9yd2Do8I
speaker: Latent Space
tags:
  - ai-infrastructure
  - sandboxing
  - model-inference
  - reinforcement-learning
  - computational-biology
title: Modal 创始人访谈：AI 基础设施演进、沙箱技术突破与模型商品化趋势
summary: Modal 创始人 Eric Burn Hartson 分享从 Spotify 到创办 AI 基础设施公司的历程。文章深入探讨了沙箱技术的快照与分叉创新、推理服务与模型开发的解耦优势，以及大模型作为商品的市场逻辑，并预测计算生物学等可验证领域将成为 AI 应用的新增长点。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people:
  - Eric Burn Hartson
companies_orgs:
  - Modal
  - Spotify
  - Better.com
  - Decagon
  - Runway
  - Cognition
products_models:
  - Stable Diffusion
  - Discover Weekly
media_books: []
status: evergreen
---
<!-- chunk 1/13 -->

### Modal 的业务与 AI 基础设施

感谢你的到来。来自 Modal 的 Eric Burn Hartson。你能稍微解释一下这项业务，也许还有你是怎么走到这一步的吗？

<details>
<summary>Original English</summary>

Thanks for coming on. Eric Burn Hartson from Modal. Could you explain uh the business a little bit and maybe how you got here?

</details>

**>>**: 是的，我们构建——最简单的说法就是我们构建 AI 基础设施。我们提供一系列算力、一个计算平台（comput platform）和一个存储平台，让像 Decagon、Sunno、Runway、Cognition 以及许多其他客户能够从本质上构建 AI 应用程序。那么这在实际中意味着大量的推理、大量的沙箱，有时是训练和微调，有时是批处理作业以及其他事情。所以我们基本上构建了一个软件 SDK，让客户能够动作非常迅速并构建这些；我们管理底层的所有容量，让部署、扩展以及在生产环境中运行这些东西变得很容易。

<details>
<summary>Original English</summary>

**>>**: Yeah, so we uh we build uh the easiest way to put it is we build AI infrastructure. So we we offer a bunch of compute a comput platform and a storage platform that enables a lot of customers like Decagon and Sunno and Runway and Cognition and many others to to essentially build AI applications. So what that means in practice is a lot of inference, a lot of sandboxes, sometimes training and fine-tuning, uh sometimes batch jobs and and other things. So we have basically built a um a software SDK that enables customers to move really fast and and build this uh we manage all the capacity underneath make it easy to deploy and and scale and and run these things in production.

</details>

**>>**: 所以你大概两年前上过 late in space。从那时起发生了很多事情。比如你们那时有多大规模？不管是你能分享的任何数字，以及相比之下，是的，你们现在有多大规模？

<details>
<summary>Original English</summary>

**>>**: So you were on late in space like 2 years ago. A lot has happened since then. Like how big were you back then? Like whatever numbers you can share and comparatively Yeah. How big are you now?

</details>

**>>**: 我其实不记得我们当时在哪里了，但大概至少在收入、用户和使用量以及诸如此类的事情上有大概 50 倍。是的，

<details>
<summary>Original English</summary>

**>>**: I actually don't remember where we were, but it's like it's probably like at least like 50x in terms of like revenue and users and usage and stuff like that. Yeah,

</details>

**>>**: 我其实把它是用在我的一个业余项目上，在那里……太棒了。

<details>
<summary>Original English</summary>

**>>**: I use it actually for like a side project that I have where uh Nice.

</details>

**>>**: 是的。是的，就像是把 2D 图像转换成 3D 模型。所以，对，就是把模型托管在那里。

<details>
<summary>Original English</summary>

**>>**: Yeah. Yeah, it's like uh yeah, turn like 2D images into 3D models. So, yeah, just hosting like models there.

</details>

**>>**: 你觉得怎么样？有什么反馈吗？

<details>
<summary>Original English</summary>

**>>**: What do you think? Any feedback?

</details>

**>>**: 我是说，我很喜欢它。[笑]

<details>
<summary>Original English</summary>

**>>**: I mean, I love it. [laughter]

</details>

**>>**: 太好了。不错。

<details>
<summary>Original English</summary>

**>>**: Nice. Good.

</details>

**>>**: 嗯，我是说，是的，这就是为什么我用它而不是任何竞争对手的产品之类的。

<details>
<summary>Original English</summary>

**>>**: Um I mean, yeah, that's why I use it over like any competitors or anything.

</details>

### 从 Spotify 到 Better.com

**>>**: 很好。所以在你创办 Modal 之前，你在 Spotify，而且我想还有像 better.com。是的。对。

<details>
<summary>Original English</summary>

**>>**: Good. So before you started modal, you were at Spotify and also like better.com I think. That's right. Yeah.

</details>

**>>**: 嗯

<details>
<summary>Original English</summary>

**>>**: Um

</details>

**>>**: 是的，你在 Spotify 做什么？

<details>
<summary>Original English</summary>

**>>**: yeah, what were you doing at Spotify?

</details>

**>>**: 我在 Spotify 其实做了很多不同的事情，但我主要的贡献是我构建了音乐推荐系统。第一版是我毕业后可能在 2008 年、2009 年加入的。在 Spotify 待了七年，大部分时间基本上是从零构建音乐推荐系统，并且组建了一个小团队，我们上线了一堆功能，比如相关艺人（related artists）和每周发现（discover weekly）以及一堆其他东西。所以有大量的矩阵分解（matrix factoriization），大量计算密集型的东西，而且可以说，后来在某种程度上成为 Modal 起源的很多东西，就是仅仅构建 AI 应用程序并意识到基础设施太烂了，一定有更好的方法来做到这一点。所以 Modal 的很大一部分理由，有点像构建一个我在 Spotify 那些年里一直想要拥有的工具。

<details>
<summary>Original English</summary>

**>>**: I actually did a lot of different things at Spotify, but my main contribution was I built a music recommendation system. The first version I I joined after school in 2008, 2009 maybe. uh and spent seven years at Spotify and and most of that time was building basically from scratch a music recommendation system and built up a small team and we launched a bunch of features like related artists and discover weekly and and a bunch of other stuff. So a lot of a lot of matrix factoriization a lot of compute intensive stuff and and and arguably like a lot of what sort of later became the genesis of modal was um you know just just building AI applications and realizing like the infrastructure sucks like there's got to be a better way to do that. So a a lot of sort of, you know, the rationale for for modal was like kind of building a tool I always wanted to have throughout my years at Spotify.

</details>

**>>**: 是的。所以 Modal 更多是你在 Spotify 学到的东西的一个分支，不太来自于 better.com。

<details>
<summary>Original English</summary>

**>>**: Yeah. So modal was more of an offshoot of the stuff you learned at Spotify, not much from better.com.

</details>

**>>**: Better、better.com 有点像是一次插曲。它有点像过山车。关于那家公司说来话长，可以单独谈，但我在 Better 做了 5 年的 CTO，把技术团队从我想两三个人扩大到了 400 人。所以学到了很多关于管理、团队建设和招聘的知识，也学到了很多关于开发者生产力的知识。对工具和这类事情思考了很多。做了很多偏全栈的事情，但之后还是回到了我内心所热爱的领域，也就是基础设施、AI 和机器学习。

<details>
<summary>Original English</summary>

**>>**: Better B better.com was a little bit of a side tour. It was kind of a roller coaster. Uh long story about the company, talk about it separately, but I was a CTO for for 5 years of Better and grew the tech team from I think, you know, two to three 400. So uh learned a lot about management and building teams and hiring and also learned a lot about developer productivity. Thought a lot about tools and things like that. Did a lot more like full stack stuff but yeah kind of came back to my what's close to my heart which is infrastructure and AI and machine learning after that.

</details>

**>>**: better.com 当时是做什么的来着？

<details>
<summary>Original English</summary>

**>>**: What was better.com doing again?

</details>

**>>**: 房贷业务。

<details>
<summary>Original English</summary>

**>>**: Mortgages.

</details>

**>>**: 好。

<details>
<summary>Original English</summary>

**>>**: Okay.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

**>>**: Yeah.

</details>

**>>**: 你是怎么进入那一行的？我是说我们不需要在这上面花太多时间。只是

<details>
<summary>Original English</summary>

**>>**: How did you get into that? I mean we don't have to spend too much time on that. Just

</details>

**>>**: 是的。没关系，挺好的。比如 Zack Frankle 这个人，我当时并不认识他，他最终把我招募到 Better 担任 CTO，当时公司只有 10 个人，而且出于某种原因，创始人 Vishal，一个非常有趣的人，非常非常聪明，有点疯狂但大多是在积极的方面，我们相处得非常好，所以我们在 2015 年开始构建它，我花了 5 年时间来发展那家公司，然后最终证明做房贷相当困难。你知道疫情之后利率上涨非常快，然后那给公司造成了很多问题，但到那时我已经离开了。

<details>
<summary>Original English</summary>

**>>**: Yeah. No, it's fine. like this guy Zack Frankle uh who I didn't know at that time ended up recruiting me to better as the CTO and the company was 10 people and you know for whatever reason you know the the founder Vishal very interesting guy very very smart a little crazy in in mostly positive ways um we got very well along so we uh yeah we we started building it in in 2015 and I spent 5 years growing that company and then you know eventually turned out that doing mortgages is pretty hard And you know interest rates went up very quickly after the pandemic and then that that caused a lot of issues at the company but by then I had already left.

</details>

**>>**: 你离开时大概是 2020 年、2021 年。

<details>
<summary>Original English</summary>

**>>**: That was like 2020 2021 when you left.

</details>

**>>**: 是的，差不多那样。是的。

<details>
<summary>Original English</summary>

**>>**: Yeah something like that. Yeah.

</details>

### 创办 Modal 与 Stable Diffusion

**>>**: 所以好吧，你是在有了 Modal 的想法之前离开的，还是离开后才开始

<details>
<summary>Original English</summary>

**>>**: So okay you left before you had the idea for modal or you left and then you started

</details>

**>>**: 很难说。我离开 Better 的时候有很多随机的想法，而且我其实不确定自己是否想创办一家公司。在疫情期间，我差不多就像休了个学术假（sbatical）。我有两个孩子。我是说我现在仍有两个孩子，但当时他们大概是两岁和四岁，所以我决定陪陪家人，休了段时间，差不多像兼职一样做些开发折腾某些东西，不确定也许我应该做些咨询，然后我开始构建东西，我只是对这个最终成为 Modal 的想法感到超级兴奋，但我其实构建了——我想 Modal 是我构建的第三个东西，让我……所以在发生之前有几次尝试都没什么进展，但 Modal 就像是第一个让我觉得“这挺酷的，我应该做这个。这可能是一个非常酷的平台”的想法。

<details>
<summary>Original English</summary>

**>>**: it's hard to say. I I had a lot of random ideas when I left better and and and I I I actually wasn't sure if I wanted to start a company. I was kind of just, you know, during the pandemic, I I sort of almost took like a sbatical. I had two kids. I I mean I still have two kids but I I mean at that time there were there were I think two and four and so I decided to hang out and took some time off and was kind of working like part-time like hacking on certain things and wasn't sure maybe I should do some consulting and I started building stuff and I just got like super pumped about this idea that that eventually became modal but I actually built you know modal was like I think the third thing I built that I got you know that so so there were like a few attempts before then that that went nowhere but but modal was like the first idea was like this is kind of cool like I should do this. This is like this could be a really cool platform.

</details>

**>>**: 其他想法也是类似的脉络吗，比如开发者工具？

<details>
<summary>Original English</summary>

**>>**: Were the other ideas like also in a similar vein like developer tools?

</details>

**>>**: 第一个东西是某种网页抓取工具，没有取得任何进展，但实际上事后来看，也许本可以有所发展。

<details>
<summary>Original English</summary>

**>>**: The first thing was like some sort of web scraping thing which went nowhere but actually you know in hindsight maybe could have gotten somewhere.

</details>

**>>**: 这是在 chat GBT 发布之前吗？

<details>
<summary>Original English</summary>

**>>**: And was this before the chat GBT launch?

</details>

**>>**: 是的。是的。2021 年。

<details>
<summary>Original English</summary>

**>>**: Yeah. Yeah. 2021.

</details>

**>>**: 好。

<details>
<summary>Original English</summary>

**>>**: Okay.

</details>

**>>**: 所以 Chad GBT 是在 2022 年底。对。

<details>
<summary>Original English</summary>

**>>**: So Chad GBT was late 2022. Right.

</details>

**>>**: 然后我开始构建，所以也许实际上倒回去一点背景，比如我在 Spotify 工作时发布了一个叫 Luigi 的开源框架，它是做工作流编排的。这和 airflow、prefect 以及 daxter 属于同一类。在某种程度上算是有点过时的类别，人们谈论得没那么多了，但在一段时间里它受到了很多关注。总之我从未把它变成一门生意。但在几年后的 2021 年，当我在思考商业想法或要做的事情时，我有点回到了工作流编排，并开始对一堆想法进行开发折腾，基本上是在云端编排运行的代码。而我意识到的是，归根结底，核心拼图不仅仅是编排计算，而是执行计算，我意识到这实际上是一个更大的需要解决的问题。所以从某种程度上说，我把它搁置在了一旁，然后说：实际上我要先去做这边的另一件事，稍后我会回到工作流调度，但后来我再也没回去过。长话短说，最终构建了 Modal，其重点更像是：让我们想办法让在云端运行计算代码变得容易，最初的重点相当通用，实际上在某种程度上我们最近有点兜了一圈又回到了原点，但我们关注了那么多不同的应用，想法有点像是：让我们能够超容易地在云端运行代码，可以是 GPU 代码、AI 机器学习，也可以是数据相关的东西，并且非常注重我们如何扩展它、如何让开发者体验变得绝佳。我们超级早就意识到，为了做到这一点，我们必须深入底层技术栈，构建自己的文件系统、构建自己的容器运行时，解决了很多艰巨的工程挑战。然后你提到了 chatbt，那其实并不完全是杀手级应用，但如果你记得的话，那年秋天大约同一时间出现了另一件事，那就是 stable diffusion。而 stable diffusion 对我们当时正在构建的东西来说成了一个杀手级应用，我们当时只有四五个人，所以我们开始看到很多人来找我们，想要运行 stable fusion 模型，然后我们意识到——那让我们意识到，也许生成式 AI（geni）推理对我们来说其实是一个非常好的用例，并且

<details>
<summary>Original English</summary>

**>>**: Then I I started building so maybe actually to rewind a little bit context like when I worked at Spotify I released an open source framework called Luigi which is like workflow orchestration. This is sort of the same category as airflow and and prefect and daxter. Sort of dated category to some extent like people don't talk about as much but for a while it was like you know got a lot of attention. Uh anyway I I never turned it into a business. Uh but a couple years later when in 2021 when I was thinking about business ideas or or things to work on I kind of came back to workflow orchestration and I started hacking on a bunch of ideas of you know running code in the you know like basically orchestrating code running in the cloud. And what I realized was like you know at the end of the day like core puzzle piece is not just like orchestrating the compute it's like executing the compute and I realiz like that's kind of a bigger problem actually to solve. So in a way I actually like you know left it on the shelf and then said like actually I'm going to like go to this other thing over here and I'll go back I'll get back to the workflow scheduling in a little bit but but like you know I never got back to it. Long story short and and and ended up building modal which is like the focus was more like let's just figure out a way to make it easy to run code in the comput in the cloud and and the focus was initially like fairly general purpose and actually in a way like it's always we've kind of gone full circle more recently but but we we focused on so many different applications it was kind of the idea was like let's just make it super easy to run code in the in the cloud could be GPU code AI machine learning could also be like data stuff um and uh focus a lot on you know how do we scale it uh how do we make the developer experience awesome? realized super early that like in order to do that we'd have to go very deep in the stack and build on file system built on container runtime uh and and did a lot of you know solved a lot of hard engineering challenges and then you mentioned chatbt that was actually not quite the killer app but like if you remember like that fall another thing came out around the same time which was stable diffusion and stable diffusion turned out to be a killer app for our for what we're building at that time we were only four or five people at that time so uh we started seeing a lot of people coming to us and wanted to run a stable fusion model and then we real that that that made us realize like maybe geni inference is actually a really good use case for us and

</details>

**>>**: 他们是如何

<details>
<summary>Original English</summary>

**>>**: how were

</details>

<!-- chunk 2/13 -->

### 早期增长与创始人营销

they finding her

<details>
<summary>Original English</summary>

they finding her

</details>

**>>**: 我就是这种强迫症式的发推者，我过去甚至更甚。像现在，我因为创办公司太分心了，但我一直都发很多推文，也一直写很多博客。我想我有一点点粉丝，所以在早期，推动增长的很大一部分原因，就是我强迫症般地发推介绍 Modal 以及我在构建的东西，让大家感到兴奋，并就云计算的发展方向等诸如此类的事情写长篇博文。而且……

<details>
<summary>Original English</summary>

**>>**: I'm this like compulsive tweeter. I was even more like now like I'm too distracted by building a company, but I always like tweeted a lot. I always blogged a lot. I think I had a little bit of a following, and so, you know, in the early days, I like a lot of what drove the growth is just like me just compulsively just like tweeting about modal and like what I was building and getting people excited and writing long blog posts about where the cloud is going and all these things. And

</details>

**>>**: 我把它称作有点像创始人主导的营销（founder-led marketing）。我一直觉得，你得顺应自己擅长的事情，而我擅长的事，我想大概就是发帖和一直泡在网上，所以……

<details>
<summary>Original English</summary>

**>>**: I call it a bit like founder le marketing. I always like feel like you kind of have to lean into like what you're good at, and like what I'm good at is like I guess like just posting and being terminally online, and so

</details>

**>>**: 你知道，像起效……它现在依然是，你知道，我觉得我们的很多增长是……

<details>
<summary>Original English</summary>

**>>**: you know like work it it's it's still like you know I think a lot of our growth is

</details>

**>>**: 我们就是蛮擅长社交媒体，而且经常泡在网上。

<details>
<summary>Original English</summary>

**>>**: we're just kind of good at social media and just like being you know online a lot.

</details>

### 自筹资金与业务拐点

**>>**: 太棒了。过了多久你们才有了第一个客户？

<details>
<summary>Original English</summary>

**>>**: Nice. How long until you had your first customer?

</details>

**>>**: 挺长一段时间的。

<details>
<summary>Original English</summary>

**>>**: It took a while.

</details>

**>>**: 另外你们早期有融资吗？

<details>
<summary>Original English</summary>

**>>**: Also did you raise like early on?

</details>

**>>**: 我们有段时间没融资（race）。实际上我有段时间是自掏腰包的。呃，甚至直到招了前几个员工也是，呃，从某种角度来说这还挺好的，因为这［笑声］让我对资金非常精打细算，而且非常想看到投资回报率（ROI）。有段时间我一直不领薪水，实际上持续了很长时间。在某个节点这成了一个问题，因为我需要钱，但我们有一阵子没融资（race），直到 2022 年初融了一轮种子轮。所以在那个节点，我已经做这事大约一年了。呃，Asha 大约在——大概是五年前——大概也就是现在的八月，可能是 2021 年作为 CTO 和联合创始人加入的。但随后基本上直到 2022 年底，我们才看到任何有实质意义的收入。

<details>
<summary>Original English</summary>

**>>**: We didn't race for a while. I actually self-funded it for a while. Uh even with up until the first few employees uh which in a way was like kind of nice cuz it [laughter] made me really like frugal about money and like wanting to see like ROI. I wasn't taking out a salary for a while for a long time actually. At some point it became a problem because I needed the money but we didn't race for a while and um uh until early 2022 raised a seed round. So at that point I'd already been working on it for about a year. uh Asha joined as the CTO and co-founder in in about about five years ago about now August maybe 2021 but then it took until like basically like late 2022 for us to see any meaningful uh revenue

</details>

**>>**: 我想那是 Chad GBT 出来的时候。

<details>
<summary>Original English</summary>

**>>**: I guess that's when Chad GBT came out

</details>

**>>**: 是的，还有 Stable Diffusion，对我们而言，呃，那是主要的事情。所以我们从比如，你知道，2022 年 11 月大概每月 100 美元，到下个月我们做到了大约 2000 美元一个月，然后到了 2023 年 1 月，我们突然做到了差不多 3 万，所以最终我感到心里这种巨大的焦虑终于卸下来了。我觉得可能这真的……我们找到了方向。感觉像是我们抓住了某种东西。接着 2023 年我们增长得非常快，我想从那时起我们一直增长得非常快。基本上……

<details>
<summary>Original English</summary>

**>>**: yeah and and stable fusion then in our case uh was the main thing that's sort so so we went from like you know $100 a month in like I think like November 2022 and the next month we did like $2,000 a month and then like January 2023 we did like 30,000 all of a sudden and you know so so finally I felt this like massive just like anxiety thing off my chest. I'm like maybe this is actually like we're on to something. It feels like we're on to something. And then 2023 we grew very fast and I guess we've been growing very fast since then. Basically

</details>

**>>**: 那个月入 3 万的时刻，只是因为几个大客户，还是说非常多元化？就一个。我不知道我有没有公开说过那是谁，他们自己知不知道，但我猜他们能想到，那是一家在纽约叫作 Mage 的公司。他们做的是企业内部的 Stable Diffusion。所以有一阵子，在 2023 年的第一季度，我想他们占了我们收入的 80%、90%，但自那之后开始变得稍微多元化了一点，而且……

<details>
<summary>Original English</summary>

**>>**: that 30k a month moment was that just like a couple big customers or was it like very like diverse? It's just one and I don't I don't know if I ever talked about like who that was and if they even know it but I think they suspect it was a company in New York called Mage. They're doing like a stable diffusion in a company. So at some point you know and in the first I think first quarter of of 2023 I think they were like 80 90% of our revenue but but then after that you know it started diversifying a little bit and

</details>

**>>**: 2023 年末我们拿下了 Sunno 这个大客户。有段时间他们也占了我们收入的很大一块。但随后随着时间的推移，我们现在的收入多元化其实非常好了。

<details>
<summary>Original English</summary>

**>>**: late 2023 we we got Sunno as a big customer. They were a big chunk of our revenue for a while too. But then, you know, it's over time like we actually have really good revenue diversification now.

</details>

### 为生成式 AI 重新构建基础设施与自动扩缩容

**>>**: 是的。关于 Stable Diffusion 那些东西，我记得用它跑过类似 Comfy UI。我猜很多人都在用 Comfy UI，比如在上面运行 Comfy UI 工作流。

<details>
<summary>Original English</summary>

**>>**: Yeah. For the stable diffusion stuff, I remember using it for like Comfy UI. I'm assuming a lot of people were using Comfy UI, like running Comfy UI workflows on it.

</details>

**>>**: 有些人在用，但我认为使用 Modal 的人，他们往往做更底层的事情，比如他们做复杂的业务。他们喜欢 Modal 的一点是它一直都非常可定制、易折腾（hackable）。所以他们部署了自己定制的工作流，带有适配器和定制推理以及大量的优化。我们为了让开发者体验变得非常好而做的所有事情，结果证明对于运行生产级工作负载也非常有效。呃，因为自动扩缩容结果证明其实是一个非常类似的问题，比如你希望非常快地扩容和缩容容器。呃，所以早期我们恰好处于一个非常有利的地位来承接很多这类工作负载。自动扩缩容的工具之前不存在吗？比如你们为什么必须自己构建这些？

<details>
<summary>Original English</summary>

**>>**: Some people were, but but I I think the people that were using Modal, they tended to be more like low-level stuff, like they did like complicated stuff. What they like with modal is like it's always been pretty hackable. And so they they deployed their own custom workflows with adapters and custom inference and and a lot of optimizations and and all the all the stuff we had done in order to get the developer experience to be really good turned out to be really good for also running production workloads. Uh cuz autoscaling turns out to be actually a very similar problem like you want to scale up containers up and down very fast. Uh so we just happen to be like very well positioned to to capture a lot of those workloads in the early days. Did tools for autoscaling like not exist? Like why did you have to build those yourself?

</details>

**>>**: 总的来说，我的论点是，每一个技术的新时代都会遇到现有工具的局限性，呃，不论是回顾 Web 还是云，或者是移动端、PC 还是 AI 什么的。所以，我认为往往是工具本身存在，但通常并不怎么好用，而且往往你必须重新思考很多这类的工具，以便收获技术带来的红利，真正加足马力开始为这个新世界去构建。在云计算时代你也看到过这种情况，我们不得不发明了 Kubernetes 和 Docker 之类的东西。同理，在生成式 AI 时代，你固然可以在上一代工具的基础上去构建这些东西，比如你可以构建在 Kubernetes、Docker 这些基础之上，但是那些技术是针对截然不同的工作负载类型而构建的。它们是针对非常平稳的后端工作负载构建的，请求量均匀稳定，在相当低的利用率下运行，因为 CPU 通常很便宜，所以人们不太用担心成本。但现在你进入了这个新世界，你面对的是非常昂贵的 GPU，你想要管理容量和利用率，你有着必须通过网络加载进 CPU 再加载进 GPU 的超大模型，事实证明很多工具根本不是为此而生的。所以我们觉得必须重建其中的很多部分。我提到了构建我们自己的文件系统，但过去几年里我们也花了很多时间去构建一些非常酷的东西，围绕 CPU 快照、GPU 快照，我们构建了自己的自动扩缩容与调度工具，以及各种各样的容量管理工具。我们觉得必须这么做，因为你无法在这类旧东西之上为新一代软件去搭一个包装层（wrapper），要做好新东西，你必须从头开始重来一部分。

<details>
<summary>Original English</summary>

**>>**: In general like my thesis is like you know every new sort of era of like you know technology kind of runs up against limitations of of tools uh you know whether that's you look back you know like the web or the cloud or you know mobile or PCs or or you know AI or whatever. So, so I I think you know it's often the case that tools exist but but they're often not like particularly good and and and often you you kind of need to rethink a lot of those tools in order to reap the benefits of you know and and really you know turbocharge and start building for this new world and and you saw this with cloud you know we had to invent things like Kubernetes and Docker and things like that and and in a in a similar way you know like with with Gen AI you could build these things on the sort of prior generation of tools like you can you can build these things on top of Kubernetes and Docker and in these things but but but those technologies are built for a very different type of workload. They're built for a very sort of steady work steady backend workloads. they have an even you know steady number of requests like running at pretty low utilization cuz CPUs are normally pretty cheap and so people don't really worry so much about cost and but now you're entering this new world and you have you know very expensive GPUs you want to manage capacity and and utilization you have very large models that you need to load over network into CPU into GPU and and and it turns out like a lot of these tools like you know like they were just not built for that so so we felt that you know we we had to rebuild a lot of that you building our own I mentioned the file system but we also spent a lot of time over the last few years like building you know some really cool stuff around like CPU snapshotting GPU snapshotting and auto we built our own autoscaler anduler and and and and all kinds of capacity management tools and we kind of feel like you have to do that because like you can't build you know for this new generation of of software on top of you can't build like a wrapper on top of the old stuff in order to to do the new stuff you kind of need to start over a little bit from scratch

</details>

### 扩容中的挑战与多区域架构

**>>**: 所以关于自动扩缩容这块，你们在平台上看到过什么奇怪的行为吗？比如在你们扩容期间有什么东西宕掉或崩溃过吗？

<details>
<summary>Original English</summary>

**>>**: so I guess like the auto scaling doing stuff like did you did you see any like um weird behaviors on the platform like was there anything that like broke while you guys were scaling?

</details>

**>>**: 我的意思是，容量一直以来时常是一个挑战，比如你如何弄到成百、上千乃至上万张 GPU。所以这始终充满挑战。我们很早就必须做多区域架构。事后来看，我觉得那是一个相当具有决定性的决策，去做了这件事并硬着头皮把它建起来。比如我们始终把容量管理看作一个大资源池，像是一个覆盖全球的大池子，而不是看作在每个区域运行的独立集群。所以早期做出的以这种方式来思考的决定，是非常关键的决策之一。因此我不知道是否有特定的问题。当然，我们遇到过 bug，遇到过宕机。尽管我很希望 Modal 能做到 100% 的正常运行时间，而且我想最近我们基本做到了 4 个 9 或 5 个 9，但在 Modal 的发展历程中，我们当然经历过遇到扩容瓶颈诸如此类的问题。

<details>
<summary>Original English</summary>

**>>**: I mean capacity is always from time to time been been a challenge like how do you get like you know hundreds and thousands and tens of thousands of GPUs. So that's that's always challenging. We had to go multi-reion very early. I think that was like kind of a fateful decision in hindsight like doing that and kind of just biting the bullet and building it like we always thought of like our our capacity management as like one big pool like it's like one big pool over the the entire world like we don't think of it as like separate clusters running in each region and so that that was like one of the like very consequential decisions we made earlier to kind of think about it that way. So I don't know if there's like been like you know specific issues. I mean, we've obviously had bugs and, you know, outages and I hate, you know, as much as I, you know, would love for modal to be 100% uptime, you know, and I think recently we've basically hit four or five nights, but throughout the history of modal, of course, we've had, you know, run up against scaling issues and things like that.

</details>

**>>**: GPU 市场……好，其实在那之前，你们底层使用了 AWS、GCP 等所有这些云提供商，那你们自己也采购任何基础设施吗，还是没有？我们来聊聊云容量吧，因为我觉得这其实发生了很大变化。在最初几年里，我们几乎所有的容量基本上都来自超大规模服务商（hyperscalers）的竞价实例（spot）和按需实例容量，主要是运行在所有不同区域的竞价实例容量，最初是使用 AWS，也有 GCP，随着时间推移还有 Azure。呃，我们挺早就开始从 Oracle 租用一些容量，因为我们想要 A10 和 A100，而且我们拿到了非常好的价格……

<details>
<summary>Original English</summary>

**>>**: The GPU market and well, actually before that, so you guys use AWS like GCP like all these cloud providers underneath like do you also buy any infrastructure or no? Let's talk a bit about like cloud capacity because I think it's actually changed a lot like in in the first few years we did we got almost all the capacity pretty much from from the hyperscalers spot and on demand capacity mostly spot capacity running in all the different regions you know using uh initially AWS but also GCP and and overtime Azure uh we we started renting some capacity from Oracle pretty early because we wanted um 810s and 8100s and we got really good rates on

</details>

<!-- chunk 3/13 -->

### 从即时算力到长期预留

那些……而且……后来我们又增加了几家云厂商，比如做预留，但实际上直到去年年底，我们的大部分算力要么是现货（spot），要么是一年期预留。

<details>
<summary>Original English</summary>

those uh and and over and we added a couple more clouds like doing reservations, but but like still up until like actually end of last year, like most of our capacity was either spot or or one-year reservations.

</details>

**>>**: 现货的意思就是你当时当场租用？

<details>
<summary>Original English</summary>

**>>**: Spot means you're just like renting it right there and then.

</details>

**>>**: 没错。是的。而且它还是可抢占的（preemptable），这也是我们必须应对的问题。但它在总体上是行得通的，因为你基本上可以把来自很多——你知道，成百上千个区域的算力聚合起来。所以那种模式一直运转得非常好，直到我们再次面临瓶颈。首先，Modal 开始飞速增长，因此我们需要更多算力；但从根本上说，云市场也开始发生很大变化。所以基本上在过去这一年里，为了获得我们需要的算力，我们必须与多得多的云厂商合作。目前我们实际上与将近 25 家云厂商合作。在很多情况下，为了获得我们想要的算力，我们不得不去签三年以上的长约，而且必须预先支付很大一笔资金。这样你就把价格锁定在了三年期限上，对吧。所以，我们不得不把过去整整六到九个月的时间花在重新思考如何获取算力上。我们不得不建立一个完整的采购部门，比如我们有四个人全职扑在上面，基本上他们所做的一切就是采购算力、给新兴云厂商（neoclouds）打电话、做交易、审核算力。我们还必须组建一个完整的工程团队，基本上有 10 个人专门管理来自世界各地的裸金属算力，处理网络问题、损坏的硬盘、GPU 从总线掉线（falling off the us）等等所有这些事情。我们并不拥有算力。

<details>
<summary>Original English</summary>

**>>**: Exactly. Yeah. And it's also preemptable which we had to deal with. Um but but it sort of works in aggregate because you can sort of just you know aggregate capacity from many you know hundreds of regions basically. So that that that model worked really well until we started running up again. I mean first of all like modal started growing like very fast and so we needed more capacity but fundamentally also like the cloud market started changing a lot. Um so in the last year basically now in order to get the capacity we need we had to work with a much larger set of clouds. We actually work with almost 25 clouds at this point and in many cases um in order to get the capacity we want like we we have to go and do you know three plus year deals and you have to pay a meaningful amount of money up front. Uh and and you're locking in pricing on on a three-year term right. So you know like and and and so we had to spend the entire you know last 6 to 9 months like you know kind of rethinking how we get capacity we had to build a whole procurement like desk like we have like four guys working full-time basically all they're doing is like procuring capacity calling neoclouds you know doing deals vetting the capacity we've had to build a whole engineering team basically 10 people just like managing like bare metal capacity from all over the world and dealing with network issues and bad drives and GPUs falling off the us and and all these things. We don't own capacity.

</details>

### 租赁与自购硬件的权衡

**>>**: 到目前为止我们所有的算力都是租来的。通常是签三年期的协议，这是一个重大决策：我们到底应该买，还是应该继续租？我其实对此并不是超级教条。我认为租赁挺好的，因为这具有一定的资本效率。如果你要买，首先显然有运营上的复杂性，你必须去和供应商打交道，还要处理电力、线缆以及各种各样的事情。但同时它也存在财务上的复杂性：你如何为它融资？比如，你应该通过股权融资吗？那样你固然可以融个 10 亿美元去买硬件，但那是一种稀释非常严重的方式。你也可以举债，但如果举债，通常你会希望有锁定的长期收入来支付利息。所以这也绝非易事。不过，我们会考量经济效益，考量运营复杂性，考量风险。这是一个复杂的权衡，我们对于购买也持开放态度。其实还有其他结构，为了锁定 2027 年所需的算力，需要付出大量努力，通过很多不同途径来锁定它。

<details>
<summary>Original English</summary>

**>>**: We rent all the capacity so far. Um you know on on typically the three-year deals and that's like a big decision like should we buy should should we know you know or should we keep renting. I I'm actually like not like mega dogmatic about it. I I think renting is nice because there's a certain amount of capital efficiency to it. if you're buying, you know, like I mean, first of all, there's an obvious like operational complexity of it, like you have to, you know, deal with vendors and suppliers and and, you know, power and and and cables and and all kinds of stuff. But there's also, you know, financial complexity to it, like how do you fund it? Like, should you raise equity, you know, and then you can raise a billion dollars and and go buy hardware for it. That's a very diluted way to do it. um you can raise debt, but you know, if you raise debt, you know, you typically want to have like locked in long-term revenue to to to pay the interest rates. So, that's also not trivial, but you know, like we look at the economics, we look at the the the operational complexity, we look at the risks. Uh it's a complex trade-off and and we're open to to to buying. We're sort of there's other constructs too like we're it's to get the capacity we need for for 2027. It's going to take a lot of work on on you know going a lot of different avenues to to to lock it up.

</details>

**>>**: 那么为了做这些事情，你们必须招聘大量财务人员吗，还是说并不需要？在这方面我已经花了很多时间，我们团队也不得不投入大量时间。我确实认为随着时间推移——这些硬件都是非常昂贵的资产。而且我认为，这挺令人震惊的，你开始看到人工智能投资逐渐占到美国 GDP 的好几个百分点，过去几周美国的利率也开始飙升。在当前阶段，你去看看那些新兴云厂商（neoclouds），它们都是非常非常复杂的金融工程公司。所以，是的，我们关注到了这一点，我们审视了所有选项，我们自己未来也可能不得不采取类似的做法。但我并不希望那样，我更愿意专注于做一家精简的软件公司，做我们擅长的事情。总的来说，我认为软件公司持有重资产并不是件好事。这就像公司是否应该拥有自己的办公楼一样，我认为对大多数公司而言，那未必是正确的解决方案。但当然，为了拿到你想要的算力，一切选项都在考虑之中。

<details>
<summary>Original English</summary>

**>>**: So do you have to hire a lot of like finance people to do all this stuff or not really? you know, I've had to spend a lot of time on this and we we've had to to to spend a lot of time on this and I I do think over time, I mean, there there is a lot of, you know, these are very expensive assets, uh, the hardware and, you know, I think I mean, it's kind of staggering. You're starting to see like AI investments starting to become like several percentage points of of of GDP of the US and, you know, starting to see like interest rates in in America shooting up in the last few weeks. And I mean like at this stage like you know and you go and look at the neoclouds like these are very, very sophisticated financial engineering companies and so yeah we we look at that and you know we look at all the options and and it's possible we might have to do similar things ourselves. I wouldn't want to like I would rather focus on being you know like a very lean software company like doing the things we're good at. I don't think it's good in general for software companies to own hard assets. you know, in the same way as like should you own your office? Like I I don't think that's necessarily the right solution for for most companies. But of course, like in order to get the capacity you want, like you know, everything's on the table.

</details>

### GPU 供需格局与价格周期

**>>**: 是的。我想供应短缺还会持续一段时间，所以你不得不那么做。你同意这种看法吗，还是觉得这只是暂时的现象？

<details>
<summary>Original English</summary>

**>>**: Yeah. And I guess the supply is going to be constrained for a while. So you kind of have to do that. Like do do you agree with that or do you think this is just like a moment in time?

</details>

**>>**: 我不一定完全同意。我的意思是，英伟达每个月都在交付几十万张 Blackwell（black walls），对吧？我并不是说这个市场是 100% 高效的，但一般来说，只要你愿意出高价，你就能拿到 GPU 算力，对吧？只要你愿意出比别人更高的价格就行。当然，Anthropic（Enthropic）和 OpenAI（Open AAI）正在尽可能多地抢购，但从根本上说，市场上一直有供应在释放，所以我并不认为它完全是一个被垄断死卡住的资源。价格确实在上涨，而且我认为值得反思的是：硬件的常态就像万有引力一样，价格最终总是会下降的。所以我们现在处于一个有点奇怪的时期，硬件价格居然在上涨。很难说这种情况还会持续多久，可能是 6 个月，也可能是 36 个月，真的很难预料要持续多长时间。但我从根本上不知道“必须买下算力”这种说法是否成立，在我看来这有点像疫情期间的卫生纸大短缺之类的狂热，至少这种恐慌引发了类似银行挤兑的局面。话虽如此，算力在一段时间内确实依然会偏紧，价格也在上涨。幸运的是，我认为即使价格上涨对我们来说也未见得是坏事，因为稀缺也意味着我们可以向客户收取更高的费用；而且我们在某个固定费率上锁定了大量预留算力，这在某种程度上意味着我们实际上已经在做多 GPU 价格了。所以，我并不太担心价格上涨。我真正更担心的反而是价格崩盘。虽然我认为这短期内不会发生，但我认为一旦发生，对市场上的很多参与者来说都会是非常糟糕的事。

<details>
<summary>Original English</summary>

**>>**: I don't necessarily agree with that. I mean like Nvidia is delivering, you know, several hundred thousand black walls, you know, a month, right? And and I I I don't want to say like the market is like 100% efficient, but like you know in general like if you're willing to pay a high price, uh you can get GPU capacity, right? Like if you're willing to pay more than everyone else and and of course Enthropic and Open AAI is buying up as much as they can and but fundamentally like there's constantly supply coming on the market and and so I I don't necessarily think it's like a fully cornered resource. prices are going up and and I do think it's worth kind of reflecting on that is like the normal state of hardware is like it's like kind of like gravity like eventually hardware prices always go down so we're a little bit in like a weird sort of period of time where like hardware prices are going up and you know it's hard to say you know how long this is going to last you know could be another 6 months could be another 36 months like it's really hard to to know h how long and but but I I fundamentally don't know if like it's it's true to say like you know you need to buy capacity in to to me that's a little bit to sort of almost like the great toilet paper shortage of you know the pandemic or whatever right like you know at least this like you know run on the bank type situations and but that being said like you know capacity is going to be tight for a while and and you know prices are going up and you know luckily I think you know it's not even necessarily bad for us if prices go up cuz cuz you know scarcity also means like we can charge more from our customers and and you know and the fact that we have a lot of reservations locked in at a rate means like to some extent we're effectively like long GPU prices already. Um so um I I don't necessarily worry too much about prices going up. I do worry more about actually prices collapsing. I don't think that's going to happen anytime soon. Uh but I think that would be a quite bad thing for a lot of the players in the market.

</details>

**>>**: 为什么那会很糟糕？

<details>
<summary>Original English</summary>

**>>**: Why would that be bad?

</details>

**>>**: 我认为对于任何锁定了大量供应的人来说，那都会非常糟糕。

<details>
<summary>Original English</summary>

**>>**: I think it would be bad for if for anyone who's locked in a lot of supply.

</details>

**>>**: 是的，因为他们付出的代价太高了，而且……

<details>
<summary>Original English</summary>

**>>**: Yeah. Because they paid way too much and

</details>

**>>**: 他们买贵了。所以存在高位买入的风险，对吧？再次强调，我其实没有那么担心这一点，我不认为这会在短期内发生。但就像我说的，从长远来看，硬件价格往往是走低的。所以这一点值得深思，对吧？目前，我认为算力确实受到了制约。用经济学词汇来说，这导致了稀缺租金（scarcity rent），对吧？那么谁攫取了稀缺租金？我认为主要流向了两个地方：大部分流向了英伟达，当然在一定程度上也流向了新兴云厂商。新兴云厂商以及大体上任何拥有算力的人，目前的经济效益都更好，在当今算力受限的情况下这无疑是事实。但从极长远的角度来看，我认为这未必完全成立。拥有 GPU 总是能让你获得一点点溢价，但这值得去冒风险吗？在资产负债表上持有这些极其昂贵的资产，这值得去承担风险吗？我不太确定。不过我们拭目以待，度过这个阶段还需要几年的时间，从长远……

<details>
<summary>Original English</summary>

**>>**: they paid too much, you know. So there's a risk of buying at the top, right? And and again, like I don't worry about that that much. Like I don't I don't think it's going to be like, you know, it's going to happen anytime soon, but like you know, like I said, like hardware prices in the very long run, they tend to go down. And so it's it's worth, you know, reflecting on that, right? Like right now, I think I think your your capacity is constrained. And and that leads to sort of, you know, in economic terms, there's a scarcity rent, right? Like who captured the scarcity rent? I think that primarily goes to two places mostly Nvidia but of course but also to some extent neoclouds like neoclouds and in general like you know anyone owning capacity has better economics like that's undeniably true today with capacity being constrained long term you know in the very long run I don't think that's necessarily entirely true right like there's always going to be a little bit of a premium you can get from owning GPUs but is it worth the risk you know is it worth the risk like holding this like very expensive assets on your balance sheet. I'm not so sure, but you know, we're going to see like it's going to take a few years to get through this and and and in the long

</details>

<!-- chunk 4/13 -->

### GPU 算力采购与市场竞争

运营，你知道，我们可能会自持一部分，可能会租用一部分，也许是两者的结合，也许做一些其他疯狂的事情，合资企业，谁知道呢，也许是一些复杂的特殊目的载体（SPDs）之类的。总之，一切皆有可能。

<details>
<summary>Original English</summary>

run, you know, we might own some, we might rent some, maybe a combination, maybe do some other crazy stuff, joint ventures, who knows, maybe some complex SPDs or whatever. Um, everything is on the table.

</details>

**>>**: 你们如何与 OpenAI 和 Anthropic 在采购 GPU 算力上竞争？我猜他们恨不得把市面上所有能买到的算力全都买光。

<details>
<summary>Original English</summary>

**>>**: How do you compete with OpenAI and Enthropic and buying GPU capacity? I'm assuming they'd want to like buy up literally everything that's available.

</details>

**>>**: 他们确实在这么做。而且我认为大家所看到的，很多价格上涨正是这种情况的反映。话虽如此，英伟达也在大量出货。我认为在某种程度上，英伟达也稍微偏向于多元化，他们不希望只有少数几个大买家，就像大家看到超大规模云服务商（hyperscalers）拿到的配额受到了一定限制一样。我认为英伟达也更希望看到很多新兴云（neo clouds）和很多替代云获得更多配额。我觉得我们在市场上看到的，这也更多是推测，但我认为我们看到更小、合作起来风险稍微大一点的云服务商对我们来说反而是个机会。比如像 Anthropic 和 OpenAI，我的感觉是他们更喜欢从那些经过检验的老牌供应商那里采购。一部分原因也是因为他们必须进行大量的训练运行，所以他们需要非常大的算力块。但市面上其实有大量的算力。你在亚美尼亚可以拿到 32 个节点，在印度尼西亚可以拿到 128 个节点。我们很喜欢这种形式。所以我们可以走出去，在世界各地拿到很多较小的算力配额，价格还相当不错。

<details>
<summary>Original English</summary>

**>>**: They are. and and and I think what you're seeing is um you know a lot of the the the prices going up is a reflection of that. That being said you know Nvidia is shipping a lot of stuff. I think also like to some extent like Nvidia is like kind of prefer a little bit of a diversification like they don't want like you know small amount of large buyers in much in the same way as you see you know hyperscalers getting a little bit of a constrained allocation. Uh I I think you know also Nvidia prefers to see you know a lot of neo clouds and a lot of alternative clouds like getting more allocation and I think a little bit what we see in the market is also this is more speculation but but I think we see you know smaller clouds that are a little bit more sort of risky to work with being more of an opportunity for us like where you know maybe Nvidia sorry anthropic and openi my feeling is like they prefer to buy from like the the tried and True. Uh part of it is also because they had to do a lot of training runs. So they need to have like very large blocks, but there's plenty of capacity out there. You know, you can get 32 nodes in Armenia, you can get 128 nodes in Indonesia. Like, you know, like we love that kind of Like, you know, so so we can go out there and like get a lot of, you know, smaller capacity all over the world. Pretty good prices.

</details>

**>>**: 这基本上就是只要有人给你提供一定数量的 GPU，你就只在乎这个吗？难道你完全不在乎它有多可靠之类的吗？万一它只是某个人放在某个破旧简陋的仓库里呢？

<details>
<summary>Original English</summary>

**>>**: Is it pretty much just like if someone offers you like a certain number of GPUs, like that's all you care about? Is there nothing like, oh, you care about like how reliable it is, you know? Is it just some like janky warehouse that someone has these in?

</details>

**>>**: 我的意思是，有时候感觉确实像在破破烂烂的仓库里，但基本上我们确实有一份规格清单。比如当我们和供应商交谈时，第一件事就是发给他们一份规格清单。我们会说我们需要这么多的 IOPS，CPU 至少需要达到……至少要有这么多，不管是什么 PassMark 跑分还是别的指标。我们需要看到最低的南北向带宽，出口和入口带宽。所以我们确实有一份需求清单。通常我们尽量做一个验收测试期，拿一个节点并在一段时间内运行一些测试。在某种程度上，这确实也包含了一点冒险的成分。有时我们签下了非常庞大的承诺协议，数千万甚至数亿美元，开始与一家我们还不完全了解的供应商合作，随着时间的推移，我们再看情况。我觉得在某种程度上，就像 SemiAnalysis 有一个 ClusterMax 一样，我感觉我们内部几乎也有自己的 ModalMax 评分。我知道相比其他供应商我更喜欢哪些，我们倾向于与那些我们见识过极佳可靠性的供应商达成更多交易。不仅如此，也不仅仅是可靠性，还包括当我们遇到技术支持问题时他们是否反应非常迅速。他们解决我们提出的问题的周转时间如何？如果系统宕机了，他们修复的速度有多快？诸如此类的事情。

<details>
<summary>Original English</summary>

**>>**: I mean, sometimes it's kind of a janky warehouse. It feels like, you know, but but like we do have like a spec sheet basically. Like when we talk to vendors, the first thing we do is we send them a spec sheet. We say we need this number of IOPS. We need, you know, like the CPU needs to be at least at least, you know, have have this many, you know, whatever the pass mark scores or whatever it is. we need to see like you know minimum you know north north south bandwidth uh egress and and ingress so we do have a list of requirements often we try to do like an acceptance testing period where we get like one node and and run some tests over time you know like to some extent it also involves a little bit of a leap of faith you know sometimes we sign very big commitments you know tens or hundreds of millions of dollars and we start working with the vendor that we still don't fully know and you know over time like you know we'll We'll see, you know, and and I think over like in a little bit of like there's a little bit of sort of just, you know, our own sort of like, you know, how like uh semi analysis has like a cluster max. I kind of feel like we almost like have our own like modal max score internally. Like I know which vendors I like more than others, you know, like and and and we sort of prefer to do additional deals with the vendors that we've seen, you know, very good reliability. Not just that also like it's not just reliability, it's also are they very responsive when when we have you know support issues. Do they fix the issues we ask for the turnaround time? If things go down, you know, how quickly do they fix it? Like things like that.

</details>

### 尾部风险与产能扩张策略

**>>**: 你认同对智能的需求基本上是无限的这种说法吗？如果认同的话，为什么不尽可能多地买下所有能买到的算力呢？如果买多了，直接转手卖给别人不就行了。当一种资源稀缺时，说“有多少就买多少”是很容易的，但我认为，首先，如果我们今天全部买下来，我们无法完全利用掉，虽然我们能利用很多，对吧，但是……

<details>
<summary>Original English</summary>

**>>**: Do you agree that the demand for intelligence is basically infinite? And if so, like why wouldn't you just buy up as much as you as much capacity as possible and then like if you over buy, you can just like sell it to somebody else. I think it's very easy to say when there's like a scarce resource like let's just buy as much as you can but I think you know first of all like if we bought it today we couldn't utilize all of it like we could use utilize a lot of it right but like

</details>

**>>**: 但是你可以转手卖给其他想要使用的人，对吧？

<details>
<summary>Original English</summary>

**>>**: but you can sell it off to somebody else who wants to use it right

</details>

**>>**: 我认为难点在于，如果市场上发生了某种情况，很多关联事件会同时发生：价格下跌，利用率下降，转售算力的市场也几乎在同一时间消失。我坐在这里，我每天在极其激进地采购算力，筹集资金去采购，所以总体上我是非常看好的。但我确实想指出，这里存在尾部风险，当那些尾部风险发生时，情况可能会变得非常糟糕。一部分原因可能是我年纪大了，我在过去经历过这些。实际上我在 1999 年就有了第一份工作，所以我亲历了互联网泡沫危机，经历了大金融危机等等。我想打造一家能再存在 20 年、30 年、50 年的公司，对吧？所以，我认为我们现在当然可以跑出去买下疯狂数量的算力，试图去垄断市场……

<details>
<summary>Original English</summary>

**>>**: I think the challenge is like if there was like something in the market that happens there are a lot of correlations that happen at the same time if you know prices going down and utilization going down and the market for reselling capacity goes vanishes at the kind of the same time I'm sitting here and like I'm I'm extremely aggressive like buying capacity every day and like raising money to buy you know so overall I'm I'm very bullish but like I do want to point out and like you know like there are tail risks here and and when those tail risks happen like it could be get very bad part of it is like maybe I'm you know I'm just old and I've seen this in the past like I actually had my first job in 1999 so I saw the dotcom crisis and I've seen the great financial crisis and things like that and you know like I want to build a company that that is around for like 20 to 30 50 more years, right? Like and and so, you know, I think we can certainly go out and like buy an insane amount of capacity right now and trying to just corner the market,

</details>

**>>**: 但你知道亨特兄弟吗？

<details>
<summary>Original English</summary>

**>>**: but you know, do you know about the Hunt brothers?

</details>

**>>**: 这算是交易界的一个传奇故事。他们试图垄断白银市场。

<details>
<summary>Original English</summary>

**>>**: It's like a legendary story in trading. They try to corner the silver market.

</details>

**>>**: 结果失败得一塌糊涂。所以垄断市场总体上我认为可能不是个好主意。但大体上我们依然非常非常激进，只是我们的扩张节奏遵循着一项激进的计划，基本上与我们的需求增长相匹配，并且与我们希望在明年年底达到的运营资金周期（runway）或年化运行率（run rate）目标相匹配。

<details>
<summary>Original English</summary>

**>>**: It fails spectacularly. Um you know, so so cornering the market I think in general like can be um not not a good idea. Um and but but we are in general very very aggressive but but we're ramping up you know like at a at an aggressive plan that basically matches our demand growth and matches where we want to try to get to at the end of next year in terms of run runway or run rate.

</details>

### 非英伟达加速器与新型架构

**>>**: 你们是只采购英伟达的产品，还是也会从其他类型的公司采购算力，比如……

<details>
<summary>Original English</summary>

**>>**: Are you only buying up Nvidia stuff or also like you know maybe a capacity from other types of companies like

</details>

**>>**: 我们正在关注。我认为替代性加速芯片正开始变得非常有趣。说来讽刺，在过去五年甚至十年里，我每年都在说“明年将是非英伟达加速器的一年”，然后我每次都说错。但我确实认为 2027 年可能终于会是非英伟达加速器的一年了。我们拭目以待看我今年是不是又说错了。不过 AMD 的产品在某些方面开始拿到非常好的评分。我认为 TPU 在谷歌内部被极其广泛地使用，看起来运行得非常棒。我对 Trainium 了解不多，感觉没有看到那么多相关内容，但他们的团队非常优秀，我知道他们正在做大量的软件层面的工作。硬件在某种程度上是很难做，而软件相对容易一些，这让我觉得，如果我们把这些加速器的软件层搞好了，对它们的需求将会很大。并且从根本上说，随着英伟达成为如此巨大的瓶颈，我们可能会看到更多替代性加速器出现。话虽如此，流水线更下游的地方还有瓶颈。比如台积电（TSMC）和 ASML（ASL），或许是这一切背后更深层的瓶颈。不过长远来看，我认为垄断不会永远持续。所以我觉得市场拥有更多替代方案是健康的。尽管我很喜欢英伟达——先澄清一下，他们显然是一家了不起的公司，有着惊人的产品。但我确实期望看到市场上出现更多样化的选择，也包括像 Cerebras 和 Groq 这类的产品。

<details>
<summary>Original English</summary>

**>>**: we're we're looking at it. I I think the alternative accelerators are starting to get very interesting. It's, you know, ironically, like every every year in the last five, maybe even 10 years, I've been saying, you know, like next year it's going to be the year of like non- Nvidia accelerators and and then I'm always wrong, but but I do think 2027 might be the year of non- Nvidia accelerators finally. So, we'll see if I'm wrong this year, too. But, so I I you know, AMDs are starting to get like really good scores on certain things. I think, you know, TPUs are are obviously used very, you know, widely internally at Google seem to work really well. I I don't know much about Tranium. I don't feel like I see quite as but you know the team is very good. I know they're working on a lot of the software stuff. You know hardware is hard in a in a certain way like software is like easier and that makes me feel like you know if we just fix the sort of software layer for these accelerators like I think there's going to be a lot of demand for them and and I think fundamentally you know with Nvidia being such a bottleneck like we'll probably see you know more alternative accelerators. That being said you know there's bottlenecks further down the pipe. I mean, you know, there's like TSMC and ASL maybe like a deeper bottleneck to all of this anyway. Uh, but, you know, long-term, I think monopolies don't always last. And so, I I'm I think it'd be healthy for the market to have more alternative. As much as I love Nvidia, like to make that clear, like I mean, they're obviously an amazing company and with an amazing product. Um, I I do expect to see a little bit more divers diversity in in the market as well also things, you know, like Cerebras and Grock and these things.

</details>

**>>**: 是的。你怎么看其中一些供应商？

<details>
<summary>Original English</summary>

**>>**: Yeah. What are your thoughts on like some of those uh providers?

</details>

**>>**: 我觉得他们挺令人兴奋的。你可以看到他们在某些特定工作负载上表现得非常好。有些很有意思的实践，人们在做这种混合的解耦推理（disaggregated inference），也就是用英伟达做 Prefill，用 Cerebras 做 Decode 等等。

<details>
<summary>Original English</summary>

**>>**: I think they're pretty exciting and you know and and you see them doing really well on on certain workloads and you know there's some interesting you know people doing these like hybrid you know disagregated inference where they run you know NVIDIA for the prefill and and cerebras for the decode and and things like that.

</details>

**>>**: 我其实从来没听说过这个。

<details>
<summary>Original English</summary>

**>>**: I've never heard of that actually.

</details>

**>>**: 是的。Groq 也是一样，因为很多这些……

<details>
<summary>Original English</summary>

**>>**: Yeah. And you know Grock too like because a lot of these

</details>

<!-- chunk 5/13 -->

### 混合硬件架构与新型云的扩展模式

事情……你知道，某些事情是受计算限制的，某些事情是受内存限制的，所以你可以把它们进行某种搭配组合，呃，我认为这挺令人兴奋的。在实际中部署这些东西时，它开始变得非常复杂。呃，但我确实认为，在这些更复杂的硬件配置中，存在很多、存在很多机会。

<details>
<summary>Original English</summary>

things you know certain things are computebound certain things are memory bound so you can sort of mix and match uh and I think that's quite exciting. it's it starts to get very complex when you're deploying these things in practice. Uh but but I I I do think there's a lot of there's a lot of you know opportunity and and and in these sort of you know more complex hardware setups.

</details>

**>>**: 你是否从其中的某些新型云（Neoclouds）身上学到了什么东西，比如我不知道，像 Nebus 之类的，以及他们做事的方式和你正在做的事情的对比？

<details>
<summary>Original English</summary>

**>>**: Are there any learnings that you get from uh some of these Neoclouds like I don't know like Nebus or whatever and like the way that they're doing things versus like what you're doing.

</details>

**>>**: 我认为对于新型云来说，你知道非常有趣的一点是，他们怎么能扩展得这么快。我其实觉得最夸张的例子就像 ncale，几乎凭空冒出来，然后他们的流水线里就有了几千亿美元，尽管他们几乎没有任何容量。新型云怎么能增长得这么快？其实答案基本上就是……你知道，这可能显而易见，但他们做的事情就是，他们去找像 Anthropic 或者 OpenAI 这样的大买家，基本上就是说：“嘿，你想买 5 年的芯片吗？签下这份合同，我们给你个好价格。”然后他们拿着那份合同去华尔街，说：“看，我们拿到了这个大买家，他们承诺了价值 100 亿美元的芯片，呃，我们现在只需要钱。”他们把钱融到了，然后他们去找 Supermicro、Dell 之类的和英伟达，拿到硬件，然后安装好，接着交付给客户，对吧？所以你有了这种非常巧妙的财务构想，你基本上可以预售你甚至都还没买的东西，这就意味着你可以极其快速地扩大规模。所以这就是我们在这些新型云身上看到的，他们扩展得非常非常好。

我认为 Modal 因为我们一直更多侧重于产品驱动增长（PLG），并且没有以同样的方式锁定长期合同的能力，从财务角度来看，以那种速度扩展会更具挑战性一些。呃，尽管我认为从长远来看我们也会走到同样的位置，但我认为看到这些新型云，尤其是像 Core 以及那些大型的，一直非常非常精明地运作他们如何融资，以及如何将 GPU 视作贷款抵押品等所有这些事情，这是一件相当引人入胜的事。

<details>
<summary>Original English</summary>

**>>**: I think one of the things that you know is very interesting with with Neoclouds is like how can they expand so quickly. I I think actually the most crazy example is like ncale which went from like nowhere to like you know having like you know whatever hundreds of billions of dollars in in their pipeline despite barely having any capacity. How can neoclass grow so fast? I mean there's like an you know and and and basically the answer is like you know and this might be obvious but like what they do is like they go out to like you know anthropic or or or opening eye some some big buyer or whatever and basically say like hey do you want to buy like 5 years of chips you know sign this contract we give you a good rate and then they take that contract and then they go to you know Wall Street and say look we got this like you know big buyer you know they they committed to $10 billion worth of chips uh we just need the money right now and and they're going to raise the money and then they like you know go to like super micro and dial or whatever in Nvidia and like get the hardware and then they install it and then you know now they have like you know deliver it to the customer right so so you have this like very nice sort of financials construct where you can basically sort of pre-ell things that you haven't even bought and and that means you know you can scale up extremely fast and so that's what we've seen with these neoclouds is is is they can scale very very well I think modal because we've always had a little bit more of a PLG focus and and and and not the sort of you know ability to lock in long-term contracts in the same way. It it's a little bit more challenging from a financial perspective to scale that fast. Uh even though I think you know in the long run like we'll get to the same point but I think that's been kind of a fascinating thing to see with these neo clouds and especially like core and and those big ones um been very very savvy with you know how they raise money and and how to you know think about GPU as collateral for loans and all these things.

</details>

**>>**: 这其中的意义是什么？我忘记是谁了，但有一家金融公司说：“噢，我们要把……”噢，我想其实是英伟达，他们说：“我们要把 GPU 变成一种资产类别。”这只是因为他们需要融资，然后试图弄清楚从哪里搞到钱吗？这其中的意义是什么？

<details>
<summary>Original English</summary>

**>>**: What's the relevance of like I I forget who it was but like some like financial company was like oh we're going to make oh I think it was Nvidia actually they were like we are going to turn GPUs into an asset class. Is that just cuz like they need to raise money and they were like trying to figure out where to get the money from like what's the relevance of that?

</details>

### 计算作为资产类别与风险对冲

**>>**: 我是说，有一批初创公司，我不知道你是不是在想那个。有像 Silicon Data 和 Compute Exchange，以及其他几家公司，基本上是在试图创建价格指数、各种指数以及交易衍生品之类的东西。我认为这挺有意思的。我觉得对于算力来说，把算力作为一种资产类别确实存在很多挑战，比如它绝对不像其他资产类别那样同质化。呃，你有不同的网络、不同的地点、不同的磁盘、CPU 以及各种各样的东西和可靠性。话虽如此，你也可以对石油说同样的话，而我们差不多把石油做成了相对大宗商品化的可交易资产。这还有待观察。我确实认为，在目前人工智能数据中心 GPU 部署的这种规模下，我们在风险对冲、如何分担风险以及拥有更多类似保险之类的事情上，确实需要更聪明一些。所以我非常高兴人们正在深入思考这个问题。话虽如此，我并不完全确定我们是否会看到 GPU 变成某种像亨利港（Henry Hub）或者布伦特原油那样超级大宗商品化的可交易资产。

<details>
<summary>Original English</summary>

**>>**: I mean there's a bunch of startups I don't know if you're thinking about that. There's like Silicon Data and Compute Exchange and like or and and and a few other ones that are like basically like trying to get to like you know creating price indices and indexes and and and trading derivatives and things like that. I think it's interesting like I I think with compute like it does there are a number of challenges with compute as an asset class like it's definitely not as homogeneous as other asset classes. uh you have different network and different locations and and and different discs and and CPUs and all kinds of stuff and reliability. I mean that being said like you can say the same thing about oil and like we kind of created like you know relatively commoditized you know tradable assets out of oil. It remains to be seen like I do think you know at this scale where we are with the sort of AI like data center GPU deployment like we do need to be a little bit smarter with like risk hedging and and and and how we share risks and and you know having more like sort of insurance and and things like that. So I I I I'm I'm very happy that people are thinking a lot about this. That being said, like I I'm I'm not entirely sure if we're going to see, you know, GPUs becoming sort of, you know, whatever the sort of Henry Hub like, you know, Brent crude type like, you know, super commoditized like tradable asset.

</details>

### Modal 的两大产品：Functions 与 Sandboxes

**>>**: 是的。我想把对话转向 Modal Sandboxes。

<details>
<summary>Original English</summary>

**>>**: Yeah. I want to shift the conversation to modal sandboxes.

</details>

**>>**: 好的。

<details>
<summary>Original English</summary>

**>>**: Yeah.

</details>

**>>**: 我想在我们开始之前，Modal 都有哪些不同的产品？我想显然主要产品是 GPU，然后有 Modal Sandboxes。还有别的吗？

<details>
<summary>Original English</summary>

**>>**: I guess like before we do that, what are the different products that modal has? It's I guess like the main product obviously is like the the GPUs, then you have modal sandboxes. Is there anything else?

</details>

**>>**: 我认为我们拥有的两个大产品基本上是，第一是 Modal Functions，第二是 Modal Sandboxes。所以，关于 Modal Functions，我们在 2021 年就推出了。它的理念是无服务器函数，非常易于部署，非常易于扩展，并且我们管理所有容量。事实证明这在推理方面非常非常好，在管理 GPU 以及在上面运行类似任务方面也非常棒。但我们其实从来没有过专门的推理产品，或者本身称之为 GPU 产品的玩意儿，我们从未把 Modal 当成新型云。我认为有被吸入那个方向、变成一家新型云的风险——去售卖那种我认为像长方形一样的东西：“这是 3 年期合同，你拿到这么多 GPU。”我们一直非常擅长的是：你部署一些东西，你可以随之扩展，面对这种非常有周期性或突发性的负载，我们来管理所有的容量。美妙之处在于，因为我们有成千上万的客户，我们可以对这部分容量进行聚合，使工作负载变得非常平滑，带来非常平滑的总需求，我们可以非常高效地进行管理。所以 Functions 是核心，正如我提到的，我们在 2021 年推出了它，在 2023 年开始看到产品与市场匹配（product-market fit），现在它大约占我们收入的三分之二，并支撑着大量……在实际中大多是推理，但你也可以把它用于各种其他事情。

Modal Sandboxes 我们是在 2023 年推出的，实际上和 Functions 类似，花了一段时间才看到产品与市场匹配。我们为什么推出它？我们意识到与我们交谈的很多人都在使用大语言模型（LLM）来输出代码。这是我和 Akshat 有一天吃午饭时聊到的。我们觉得也许他们需要一个运行那些代码的地方，然后我们意识到，其实我们差不多已经有了很多基础设施，可以直接拿来运行代码，因为我们已经构建了用于管理容器和隔离的原语。我们已经有了 gVisor 作为隔离原语，诸如此类。所以我们对这个想法感到挺兴奋，然后写了一个原型，基本上在一两天左右的时间就发布了。零……我们看到的增长非常少。我不想把它说得微不足道，我们确实看到了一些增长，有一些……

<details>
<summary>Original English</summary>

**>>**: I think of the like the two big products that we have is basically number one is modal functions and number two is modal sandboxes. So, so with modal functions we we launched that you know back in 2021. It was the idea of like serverless functions that are be very easy to deploy and very easy to scale and we manage all the capacity that turned out to be really really good for inference and it turned out to be really good for managing GPUs and and running on things like that. But we actually never had like you know dedicated like inference product or like a GPU product per se like we we we never thought of model as like a neo cloud and and I think there's like a risk of like getting sucked in that direction becoming a neocloud like to selling you know sort of what I think was like rectangular like here's like a three-year you get this many GPUs always been very good at like you deploy something you can kind of scale it up you have this like very cyclical or like bursty stuff like we manage all the capacity and the beautiful thing is like because we have many many thousands of customers we can sort of aggregate that capacity and very smooth workloads you know very smooth aggregate demand which we can manage very very efficiently soal functions was the the core we launched that in 2021 like I mentioned we started seeing product market fit in 2023 and now you know it's about twothirds of our revenue and and and empowering a lot of you know in practice it's mostly inference but but you can use it for all kinds of other stuff mobile sandboxes we launched that in 2023 and it's actually kind of you know took a while to see product market fit similar to functions why did we launch launch it. We realized a lot of people we talked to were using LMS to output code. This is like me and Asha talking over lunch one day. We're like maybe they need a place to run that code and and and we realized like actually we kind of have like a lot of the infrastructure already to just take code and run it because we already built the primitives for like managing containers and isolation. We already had you know G visor as an isolation primitive and and and things like that. So we got kind of excited about that idea and and and Nokia wrote a a prototype and launched it in basically one day or two days or something like that. Zero like we saw like very little like growth. I don't want to like trivialize it. We did see some growth like there were like some sort of you know

</details>

**>>**: 那是 2023 年，所以……

<details>
<summary>Original English</summary>

**>>**: it was 2023 so

</details>

**>>**: 是的，那是 2023 年，你知道，有一些人开始用它，我们有一些早期用户在某些事情上挺喜欢它的，但总的来说，进入 2023 年夏天时，它是一个相当微不足道的收入来源。所以在两年后，我们甚至讨论过，我们到底需不需要这个产品，要不要把它关掉？然后它就突然爆发了。所以是 2023 年，我认为 2023 年真正发生的事情是大语言模型变得非常擅长生成代码……

<details>
<summary>Original English</summary>

**>>**: yeah it was 2023 and like you know like some people picked it up like we had some early users who kind of enjoyed it for for certain things but but like overall like it was like a pretty insignificant source of revenue into going into the summer of 2023. So two years later we even discussed like do we even need this product like should we shut it down then it just started exploding. So 2023 and I think what what really happened 2023 was like LMS got really good at generating code

</details>

**>>**: 在 2023 年。2023 年。

<details>
<summary>Original English</summary>

**>>**: in 2023. 2023.

</details>

**>>**: 我的意思是，大概就在那个时候。我觉得差不多就是从那时起，它们从能够重构函数和写代码片段，变成了生成完整的应用程序，对吧？于是我们开始看到很多增长来自于像 vibe coding，你知道，像 Lovable 这样的公司等等，然后像 Ramp 这样的公司开始使用 Modal 来运行后台 Agent，接着我们看到开始……

<details>
<summary>Original English</summary>

**>>**: I mean, it was like around that time. Like I I feel like that was like when they went from like being able to like refactor functions and like write snippets. So like generating like full apps, right? And and and so we started seeing a lot of growth coming from like vibe coding, you know, companies like lovable and and other ones uh and and then you know companies like ramp started using models for background agents and then we're seeing started

</details>

<!-- chunk 6/13 -->

### 多产品发展与沙箱业务

看到巨大的增长来自于许多新兴实验室（neolabs）在做诸如在模型沙箱上进行强化学习之类的事情。所以沙箱现在大约占了我们收入的三分之一。你知道，我们基本上把它看作是我们的第二个产品。对我来说这真的令人兴奋，因为即便在 Modal 刚成立的早期，我就一直知道 Modal 旨在打造一整套产品工具包。就像我们一直希望几乎成为一家云厂商那样。你知道，你有存储、计算以及大量与之交互的不同方式。我们一直想成为一家多产品供应商，但这在实践中未必真正实现，直到现在——我觉得现在已经变得比较明确了，我们有 Functions，我们有 Sandboxes，我们也在研发很多其他东西。在做训练（training），在做批处理（batch），我们在研发很多其他东西。所以对我来说，那种演进成为一家多产品公司的过程，我认为一直非常不可思议，因为这在愿景中始终非常核心，甚至在最初的演示文稿里就是如此。我当时为此准备了好几页幻灯片，但这在外部世界看来并不一定是那么回事，直到最近。

<details>
<summary>Original English</summary>

seeing tremendous growth coming from a number of neolabs doing things like reinforcement learning on model sandboxes. So sandboxes is now about a third of our revenue. You know, we we considered like basically like our our second product. And and to me it's like really exciting because like even back in the early days of modal, I always knew that modal, you know, is about like creating a whole toolkit of products. Like we always wanted to be almost like a cloud. You know, you have the storage and the compute and a bunch of different ways to work with it. We always wanted to be a multi-product vendor, but that wasn't necessarily true in practice until like now where like I think now it's like kind of clear we have functions, we have sandboxes, we're working on a bunch of other stuff too. Working on training, working on batch, we're working on a bunch of other stuff. So so to me that sort of evolution into becoming like a multi-product company I think has been amazing because that was that was always so core to the vision even in the very early decks. I I had a bunch of slides on this uh but but it wasn't necessarily true to the external world. uh until recently.

</details>

**>>**: 你们有什么正在研发的项目，是你认为可能会成为下一个产品的吗？对市场有什么预测或者类似的想法吗？

<details>
<summary>Original English</summary>

**>>**: Do you have anything in the works that you know you think is going to be like that next product? Any predictions maybe about the market, anything like that?

</details>

**>>**: 我的意思是，我非常看好模型训练。我认为训练算是一个服务不够充分的市场。显然，现在的焦点很大程度上集中在非常大型的训练任务上。但我们实际上在相对中小型的训练领域看到了大量需求。所以，我本周晚些时候会稍微谈一下这个。

<details>
<summary>Original English</summary>

**>>**: I mean, I'm I'm very bullish on training. I think training is like kind of an underserved market. Obviously, there's like a lot of focus on like very large, you know, training runs. Uh but we actually see a lot of demand the sort of smaller and midsize training segment. So, I'll I'll be talking a little bit about that later this week.

</details>

**>>**: 我们正在筹办一个会议。批处理（batch）我认为是一个非常有趣的市场。我认为我们看到很多需求来自那些有特定需求的客户，前几天我们有个客户需要转录五千年的音频。他们有数以百万计的音频文件，而我们拥有充足的算力容量，所以我们就让他们去跑了，花了几天时间。我认为那里有一些非常有趣的用例。非常看好低延迟方向的东西。我认为一旦我们把音频类模型搞定，比如语音转文本模型、语音模型能正常运作，我预计那会是一个非常有趣的市场；然后当然还有所有这些智能体（agentic）相关的东西，对吧。某种程度上，我对“agentic”这个词持复杂看法，因为在某些方面我觉得所有软件都将变成智能体化的。所以对我来说，这几乎就像是：变成智能体化到底意味着什么？我认为所有软件在某种程度上随着时间的推移都会变成由 AI 驱动。但显然存在一组通用的构建块，比如用来构建更多由语言模型驱动的软件，这在所有不同的用例中似乎是通用的。而我们——我对 Modal 的看法就是，我们所从事的业务就是打造基础构建块。我们希望提供出色、具泛化性、久经考验、通用的、可组合的构建块。我认为围绕智能体用例，也有一些非常有趣的东西。

<details>
<summary>Original English</summary>

**>>**: We're organizing a conference. batch is I think like a really interesting market. I I think we see a lot of demand for sort of you know customers that need a you know we had a customer the other day that needed to transcribe you know 5,000 years of audio. They had like you know millions and millions of audio files and and we we had a lot of capacity so we let them do that you know it took a few days. I I think there's some really interesting use cases there. Very bullish on like low latency stuff. I I think there's going to be a lot of you know once we sort of get the audio like the speechtoech models working like the voice models I sort of expect that to be very interesting market then of course like all this like agentic stuff right in a way like I I have like mixed feelings about like the word agentic cuz I feel like in in certain ways like I think all software will become agentic. So it's almost like to me like what does it mean to be agentic? Like I think I think all software in a certain way like will become like AI powered over over time but but like clearly there's like a set of like building blocks of like you know doing more sort of LM powered software that seems to be sort of you know common across all the different use cases and we're we're like you know the way I think about model is like we're in the business of building building blocks you know we we want to give you like amazing generalizable battle tested you know general purpose uh composable building blocks and and I think there's some really interesting stuff also like you know with the with the agent use cases.

</details>

**>>**: 挺有意思的，你提到了训练，因为我记得在另一期播客里，大概是一年前或者两年前，你说过你们没有把重点放在训练上；具体来说，市场发生了什么变化？

<details>
<summary>Original English</summary>

**>>**: That's interesting you bring up training cuz I think in another podcast maybe like a year ago maybe like two years ago you said like training you were not focused on like specifically like what changed in the market?

</details>

### 中小型训练与开源模型演进

**>>**: 我的意思是，我们多年来一直在断断续续地构建训练产品。所以我们并不是说从未关注过它，但这属于那种情况，比如现在我们有大约 150 名工程师，但在一年或两年前，我们的工程师人数少得多，因此仅仅因为团队规模更小，我们不得不更聚焦一些，于是推理成了我们唯一的重心，并且多年来一直是我们唯一的重心。但我们现在规模更大了，我们确实有机会在其他市场上进行布局。我也非常感兴趣继续拓展这个清单——后训练（post training）强化学习。我认为围绕这方面有一些非常令人兴奋的东西。我认为还有很多其他内容，比如围绕存储、构建数据仓库、特征存储以及实时流式传输管道，还有各种各样我不了解的东西。我认为从长远来看，Modal 的愿景基本上就是你想构建一些很酷的 AI，我们都能为你覆盖，我们拥有所有的构建块，来找我们，我们会帮你把所有这些构建块组合在一起。这就是软件的美妙之处：只要你有合适的构建块，你几乎可以构建任何东西。这正是他们想要打造的公司和产品类型。当你说训练时，你关注的是进行超大规模训练任务的大型企业，还是……好的。

<details>
<summary>Original English</summary>

**>>**: I mean we we've been building a training product for multiple years. So on and off. So, so we we I I wouldn't say we're like we never been focused on it, but it's like it's like one of those things where like I mean now we're like 150 engineers but you know a year or two ago we were a much smaller number of engineers and so but just virtue of you know being smaller we had to focus a little bit more and so inference became like our sole focus and and was our sole focus for many years but we're bigger now like we we we do have opportunities to also place bets in in other markets. I'm also really interested in you know kind of continuing the the the list of things post training reinforcement learning. I think there's some really exciting stuff around that. Um I I think there's also many other like stuff around like storage and building data warehousing and feature stores and real-time streaming pipelines and and and all kinds of like I don't know. I I think the long-term view of of modal is like basically like you want to build some cool AI like you know we got you covered like you know we got all the building blocks like come to us and like we'll help you you know take all these building blocks and compose them and that's the beauty of software is like you you can you know build almost anything if you have the right building blocks that that's very much the sort of company and the product they want to build. When you say training, are you focused on more of like the bigger enterprises doing huge training runs or Okay.

</details>

**>>**: 不，他们会去找大型超大规模云厂商或者新兴云厂商签订巨额协议，搞到十万张 GPU 之类的。但在我看来，存在一个稍微缺乏服务的市场，比如研究人员进行迭代，或者人们训练较小的模型。有文本转语音和语音转文本模型。计算生物科技实际上是一个我们看到很大需求来源的市场。我们在该领域有很多客户。训练相对规模适中的模型，你可以在 64 张 GPU 上训练，或者推荐系统、很多传统的机器学习。有很多东西是你不需要十万张 GPU 的。那个超大市场我认为我们暂时不会去重点关注，但在稍微小一点的市场中有很多东西相对来说没有得到充分服务。搭建训练集群是非常困难的。

<details>
<summary>Original English</summary>

**>>**: No, they're going to go and like, you know, do these like, you know, big hyperscaler or or rather Neo Neo cloud mega deals and get, you know, 100,000 GPUs or whatever. But but but there's like a little bit of an underserved market of like in my opinion, you know, like researchers iterating or like people training smaller models. There's you know text to speech and speech to text models. Computational biotech is actually a market that we see a lot of demand from. We have a lot of customers in that space. Training relatively you know modest models you can train on 64 GPUs or whatever recommendation system. A lot of sort of traditional machine learning. There's a lot of things like you don't need a you know 100,000 GPUs. That market I think is like we're not going to like focus on that for a while but but I think there's a lot of stuff in the you know slightly smaller markets that that that are relatively underserved. It's very hard to set up training clusters.

</details>

**>>**: 对。那你有没有注意到，比如自打 GLM 5.2 或者 Kimi K3，或者也许是 Kimi 2.5 以来，很多人在使用它们并对其进行微调？如果说有什么变化的话，我实际上看到的是相反的趋势。我觉得两年前微调的价值主张是：开源模型虽然没那么好，但如果你拿一个小模型并在你的特定领域上微调，你实际上可以在质量和成本上达到前沿水平。今天我要说的是，开源模型已经好到你基本上可以直接替换掉，不用前沿模型，而是直接运行 Kimi K3，或者 DeepSeek 4.1，或者 GLM 5.3 之类的，它们在低得多的成本下基本上几乎与前沿模型一样好。所以我们仍然看到对后训练（post-training）的大量需求，我也确实认为这是一个非常有趣的领域，我们正在该领域研发一些产品，包括 SFT 类的，但也包括强化学习等方向。我还要说，微调已经不再是你必须要做的事情了，它变得非常可选，开源模型直接开箱即用也能表现得非常好。回到沙箱。其实我刚才忘了问你，你们提供的沙箱在功能上需要更新些什么，是现有沙箱所不支持的？

<details>
<summary>Original English</summary>

**>>**: Yeah. Have you noticed like since I don't know like GLM 5.2 or like Kimmy K3 or maybe like Kimmy 2.5 uh that you know a lot of people are using those and like fine-tuning them. If anything I've actually seen the other direction. I feel like fine-tuning the value prop a couple years ago was like, yeah, you know, open source models, they're not quite as good, but you know, if you take, you know, small model and you fine-tune it on your specific domain, you can actually reach the frontier in terms of, you know, quality and cost. Uh today I I would say like the open source models are so good that like you can basically just like swap them out and just run you know instead of you know the the Frontier ones you can run you know Kim K3 or or whatever DeepS 4.1 or GLM 5.3 and they're like basically almost as good as like the Frontier model at a much lower cost. So we still see a lot of demand of uh for for postering and I do think it's a really interesting space and we're working on some some products in that space you know both sort of SFT and and but also reinforcement learning and things like that. I would also say you know fine-tuning is no longer the thing that you kind of have to do like it's it's very optional like you can open source models like work really well just off the shelf too. back to sandboxes. Actually, I forgot to ask you. So, like what did you have to update about the sandboxes that you guys um were offering uh that like existing sandboxes did not uh did not allow for?

</details>

**>>**: 倒没有太多。我认为我们一直非常擅长的事情——我是说，我们是基础设施极客，对吧？我们非常擅长扩展性和可靠性，以及做很多事情。我认为这在很大程度上解释了为什么据我看来——我没有确切数据，但我认为我们在这个领域拥有远超他人的最大市场份额。我们就是非常擅长运行成千上万乃至数百万个沙箱。

<details>
<summary>Original English</summary>

**>>**: Not a whole lot. I I think the thing we've always been very very good at, I mean, we're infra geeks, right? Like we're very good at like, you know, scaling and reliability and and doing a lot of stuff. And and I think that's why that explains to a large extent like why we have you know in my opinion I don't have numbers but like I think we have by far the largest market share in the space like we're just very good at running you know hundreds of thousands or even millions of sandboxes.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

**>>**: Yeah.

</details>

**>>**: 我要说的是，为了应对那样的规模，我们不得不把我们的系统重写了好几次。但我们一直在这方面非常在行。在

<details>
<summary>Original English</summary>

**>>**: I will say we'll have to we've had to rewrite our systems you know a bunch of times in order to handle that scale. So so but we were always like very good at it. There

</details>

<!-- chunk 7/13 -->

### 沙箱空间与快照技术

随着时间的推移，还有其他一些事情。我是说，整体而言，沙箱领域并不是那种最具差异化的空间，但我们正在做一些非常酷的事情。比如随着时间推移，我们不得不增加对虚拟机（VM）的支持，所以我们之前是在 G Visor 上构建我们的沙箱产品，但现在我们也提供完全虚拟化的机器。事实证明，对于某些特定用例，你确实需要完整的 Linux 兼容性。我们还不得不构建其他东西，比如用于更具交互性的更好原语，像在沙箱之间来回传输数据管道，以及处理文件系统。我们还不得不在快照技术上投入大量时间。我认为从长远来看，很多能形成差异化的东西将会是非常酷的功能，比如沙箱分叉（forking）、快照、恢复快照，以及通常意义上的实时迁移。我认为沙箱的新颖之处一直在于这种短暂性（ephemerality），比如你可以启动沙箱几秒钟，而这正是我想要进一步深入挖掘的方向。我认为你可以做很多非常酷的事情，比如将智能体与运行载具（harness）解耦，将其与沙箱解耦，让智能体控制多个沙箱，分叉沙箱，进行快照，比如基本上运行非常短命的沙箱，可能每个命令启动一个，诸如此类。所以我觉得那里有很多酷炫的东西。围绕快照，我们已经花了很多时间在做这件事。但我认为那里还有很多很酷的东西有待构建。

<details>
<summary>Original English</summary>

are other things like over time I mean the sandbox space in in general like you know like it's like not the most like differentiated space but you know we're working on some really cool stuff like over time like we've had to add support for VMs like virtual machines so we we we previously built our our sandbox product on on G Visor but now we offer full virtualized machines as well. Turns out a lot of for certain use cases you kind of need full Linux compatibility. There are other things we've had to build, you know, better primitives for like more interactive, you know, piping data back and forth between sandboxes, working with file system. We've had to spend a lot of time on snapshotting. I think a lot of the things that over in the long run will differentiate will be like, you know, really cool things like, you know, forking sandboxes, snapshotting, resuming snap like live migrations in general. Like I I think sandboxes, the novelty of sandboxes was always, you know, this sort of ephemererality like you can spin off sandboxes for a few seconds and and and that's something I like that's a string I I want to pull more in. I think there's a lot of really cool stuff you can do, you know, kind of decoupling the agent and and the harness decoupling it from sandboxes, having agents control many sandboxes, forking sandboxes, you know, snapshotting things like, you know, like running basically like very shortlived m maybe one per command, like things like that. So I I think there's a lot of cool stuff there. We've already spent a lot of time doing that, you know, around snapshots. Uh but but I think there's a lot of cool stuff to be to be built there as well.

</details>

**>>**: 你提到了几次快照。你认为快照的用例究竟是什么？它能给我们带来哪些我们目前得不到的东西？

<details>
<summary>Original English</summary>

**>>**: You brought up snapshotting a couple times. Like what do you see as like the use case for snapshotting? Like like what would that give us that we don't get right now?

</details>

**>>**: 我觉得对我来说核心在于，如今很多沙箱工作负载都有点像“直接搬迁”（lift and shift）。人们对沙箱的看法几乎就像是：我现在有了自己的开发机，然后我要把它塞进云端，我要让一个智能体来控制它，也许我会在沙箱内部运行测试载具。我不知道从长远来看，这是否是对智能体算力思考的正确方式。我认为一个更好的模式是，你将拥有这些运行时间非常长的智能体，这在我看来几乎就像某种持久执行的工作流。它们将全天候（24/7）运行，每隔一段时间就会执行一次命令，而且能够拥有在 100 毫秒内启动一个沙箱、运行几条命令，然后将其关闭并生成快照的能力。我认为唤醒和休眠的周期越快，你就越能创建出只运行极短时间的沙箱。而这会让算力变得更加高效。同时它还能让你做一些非常酷的事情，比如分叉、把东西移来移去，想象一下，比如像 Claude Code 这样的系统，不再是采用非常线性的顺序流，而是进行分支，同时运行成百上千个智能体。我经常把 CI 当作另一个说明性的例子，在 CI 历史的大部分时间里，比如谈到 GitHub Actions 之类的东西，你都有一个非常顺序化的流程：你慢慢安装一堆东西，然后运行测试套件，接着生成一些报告之类的，你可以将其拆分成不同的分片（shards），但这挺麻烦的。我最想做的事情就是拿来你的整个测试套件，直接在各自独立的沙箱中运行每一个单独的测试，彻底将其高度并行化，一口气运行上千个沙箱。

为什么做不到这一点？我的意思是，问题在于围绕启动和停止沙箱有太多的开销。因此我认为，你越能创造无摩擦的启动和停止，你就越能进入一个可以进行极高突发性、大规模、随心所欲并行运行的世界。所以，就像我说的，我是一个基础设施极客，我对这些东西感到非常兴奋。一旦我们搞清楚所有这些原语和正确的构建基块，我认为它将解锁大量以前我们在软件上无法做到的酷炫事情。

<details>
<summary>Original English</summary>

**>>**: I think the the big thing for me is like today a lot of sandbox workloads are kind of like lift and shift. Like people think a lot about sandboxes almost like you know I have my dev box now I'm going to shove it in the cloud. I'm going to have an agent control it. Maybe I'll run the harness inside the sandbox. I don't know if like longterm that's like the right way to think about, you know, on like compute for agents. I I think a much better model would be you're going to have this like very long running agents which almost like to me are like kind of durable execution workflows. Like they're going to run, you know, 24/7. you know, every once in a while they're going to run commands and and you know, having the ability to like spin up a sandbox in, you know, 100 millisecond, run a few commands, and then like shut it down and like snapshot it. I think the faster you can get that like, you know, wake up, you know, go to sleep cycle, the more you can sort of create sandboxes that only run for like a very brief period. And and that will make compute much more efficient. And it will also enable you to to to do some really cool things you know like forking and and moving things around and and and you know having like imagine you know like clawed code instead of you know having sort of a very linear flow like sequential flow like kind of branching and you know running hundreds of agents at the same time. I think a lot about like CI is like another like illustrative example like for most of the the history of CI uh you know talk about like GitHub actions and things like that like you had a very sequential flow like you you know you slowly install a bunch of stuff then you run the test suite and then you know generate some reports or whatever and it's like you can break it up into shards but it's kind of annoying like what I would love to do is like take your entire test suite and just run every single test in its own sandbox right like and just paralyze the out of that run like a thousand sandboxes

Why can't that be done? I mean the problem is like there's too much there's too much overhead around like you know starting and stopping sandboxes. So I think the more like you you create like you know frictionless like starting and stopping the more you can enter a world where like you can do this like extremely bursty like large scale like run as much as you think want in parallel. So, so, you know, I'm an infro geek, like I said, like I I I get very excited about these things. You know, once we figure out all these primitives and the right building blocks, I think it's going to unlock a lot of really cool stuff that, you know, we we previously could not do with with software.

</details>

### 并行化门槛与生态合作

**>>**: 为什么这个以前没有被构建出来？按理说即使在以前，人们也会希望尽可能地将他们的 CI 并行化。

<details>
<summary>Original English</summary>

**>>**: Why hasn't that already been built? I would assume even previously people would would want to parallelize as much as of their CI as possible.

</details>

**>>**: 你做不到，因为开销太大了，就像阿姆达尔定律（Amdahl's law）之类的，对吧？现在的并行化开销非常高，因为比如现在在 GitHub Actions 中，我们在 Modal 的测试套件里也是做并行化的，对吧？但那基本上意味着，如果你把测试套件拆分成两半，现在这两个分片都必须完成所有的安装和测试设置，而那需要很长时间，可能需要好几分钟。但假设你只需做一次测试设置，然后对容器进行快照，接着进行克隆，现在你就可以独立运行这些测试套件了。我认为很多收益在降低摩擦和开销之前是无法变现的。

<details>
<summary>Original English</summary>

**>>**: You can't, but the overhead it's like Andall's law or whatever, right? Like the overhead of parallelization right now is very high cuz like right now like in GitHub actions for instance like we we paralyze in in the modal test suite, right? But like what that basically means is like now if you take your test suite and you split it up in two like now each of those shards both need to do all the installs and and the test setup and that takes a long time like it it can take minutes but let's say you can do the test setup once and then you snapshot the container and now you clone it and now you can run the test suites independently. I think a lot of a lot of the the benefits cannot be uh you you can't materialize those benefits until you get the the friction and and the overhead down

</details>

**>>**: 交易成本。

<details>
<summary>Original English</summary>

**>>**: the transaction cost.

</details>

**>>**: 我记得你们和 Anthropic 有合作，他们在某些方面使用了沙箱，比如 Modal 的沙箱。

<details>
<summary>Original English</summary>

**>>**: I think you guys have a partnership with Anthropic and they're using sandboxes for something like modal sandboxes.

</details>

**>>**: 是的，我的意思是与 Anthropic 合作的托管智能体（managed agents），有一种自带沙箱（bring your own sandbox）的集成方式。所以你可以针对那些使用 Modal。是的。

<details>
<summary>Original English</summary>

**>>**: Yeah, I mean the the managed agents with with Enthropic uh there's a sort of bring your own um sandbox integration. So you you can use modal for those. Yeah.

</details>

**>>**: 噢，太酷了。那是怎么促成的？也许是怎么谈成的？

<details>
<summary>Original English</summary>

**>>**: Oh, cool. How did that come out? like come maybe

</details>

**>>**: 我认为 Anthropic 正在努力打造一个繁荣的生态系统和社区，而且他们是通过推理来赚钱的，对吧？所以我认为推广其他所有环节的生态系统是非常符合他们利益的，他们希望拥有尽可能大的触达面，只要你使用 Anthropic 进行推理就行。因此我认为，对他们来说，与我们这样的沙箱提供商合作是非常合乎逻辑的。

<details>
<summary>Original English</summary>

**>>**: I think anthropic is like trying to create you know like a thriving ecosystem and community and and so I think you know they make money from inference right like so I I I think it's very much in their interest to promote you know like a for everything else you know as much of you know of an ecosystem as possible and they want to have the largest possible surface area as long as you use entropic for inference so I I think it makes like very rational sense for them to to to partner with with us as a sandbox provider

</details>

### Hugging Face 事件与默认安全

**>>**: 另外我觉得我们必须提一下 Hugging Face 事件，你介意聊聊那个吗？

<details>
<summary>Original English</summary>

**>>**: also I feel like we have to bring up the hugging face incident are you okay talking about that.

</details>

**>>**: 介意，没问题，事情都在那儿摆着。

<details>
<summary>Original English</summary>

**>>**: Yeah. Yeah. It's all there.

</details>

**>>**: 好的，那你能不能简要描述一下发生了什么？我认为他们当时使用的是 Modal 沙箱，但这并不是你们的……你知道，这并不是沙箱本身的故障。

<details>
<summary>Original English</summary>

**>>**: Yeah. Yeah. So, yeah. Could you just briefly describe like what happened? And I think they were using the modal sandbox, but it wasn't your, you know, it wasn't like a fault of the sandbox.

</details>

**>>**: 是的，完全正确。我记不清这次利用（exploit）的所有细节了，但我认为你指的是 Modal 牵涉其中的事实。是的。所以，对此作个说明，基本上是在内部运行的智能体利用了 Hugging Face，他们发现了一个部署在 Modal 上的应用程序中的漏洞。

<details>
<summary>Original English</summary>

**>>**: Yeah. Exactly. I I I don't I forget the all the details uh of of the exploit, but um I I mean, you know, I think what you're referring to is the fact that like modal was involved. Yeah. And so, you know, just to comment on that, like basically the the the agents running inside, you know, that that that exploited hugging face, they discovered a a vulnerability in an app that was deployed on Moto

</details>

**>>**: 据我的理解，他们以此为跳板获取了访问权限，获取了完整的互联网访问权限。

<details>
<summary>Original English</summary>

**>>**: and they used that to sort of as almost like a springboard for for getting access getting full internet access is my understanding.

</details>

**>>**: 我不记得全部细节了。需要明确的是，

<details>
<summary>Original English</summary>

**>>**: I don't remember the full details. To be clear,

</details>

**>>**: 这是一个在 Modal 上运行的应用，

<details>
<summary>Original English</summary>

**>>**: this is an app running a modal

</details>

**>>**: 是应用被黑了，而不是 Modal 被黑了。这就像 AWS 一样，很多人在 AWS 上运行东西。偶尔那些应用会被黑。这是否意味着 AWS 被黑了？当然不是，对吧？所以在 Modal 上运行应用的人也很多。其中一个应用被黑了。但我认为我们可以从中吸取一些教训，我们一直在反思的事情之一就是：我们是否可以在默认情况下设置更合理的安全限制？换个类比，如果用 AWS 的类比来说，S3 过去很容易不小心把一个 S3 存储桶设为公开。AWS 意识到，这本身不一定会对 AWS 构成安全问题，但他们的很多客户会不小心泄露……

<details>
<summary>Original English</summary>

**>>**: that was hacked like it was not modal that was hacked. So it's like AWS, a lot of people run stuff on AWS. Occasionally those app get hacked. Does that mean AWS got hacked? Like no, of course not, right? And and so there's a lot of people running apps on modal. And you know, one of those apps got hacked. And I I think but but like there are some lessons we can learn and and and I think one of the things we've been reflecting on is like could we have more sensible, you know, security restrictions by default. I think to use the AWS analogy in the just just as another analogy, you know, S3 used to be this like, you know, it used to be very easy to to accidentally make an S3 bucket public and AWS realized like, you know, it doesn't necessarily cause it, you know, pose a security problem for AWS per se, but a lot of their customers accidentally would, you know, like leak

</details>

<!-- chunk 8/13 -->

### Agent 与网络安全

数据。所以对于 S3 来说，现在把 S3 bucket 设为公开要困难得多了。所以以类似的方式，我们也在探索，比如我们能否在默认情况下把安全性做得更严格一点，同时又不至于破坏那种造就优秀的魔力。而且我认为，作为一个单独的延伸方向，现在 Agent 在网络安全方面变得非常厉害，所以作为从这次事件中得到的某种经验，我们内部其实也开始大量使用 Agent 来尝试寻找漏洞。目前为止还没有发现任何漏洞，但它们非常擅长深入探测系统非常底层的部分，去尝试利用漏洞、尝试提权并逃逸出沙箱。所以，这是我们目前正在非常积极探索的事情。

<details>
<summary>Original English</summary>

data. And so S3, it's much harder now to make S3 buckets public. And so in similar way it's like we're exploring like you know can we make security a little bit more restrictive by default without necessarily you know destroying the magic that make that makes good and I think there's also you know as kind of a separate sidetrack is like agents are getting really good at cyber security so we've actually also as a sort of you know separate sort of learning from this incident like we started using agents internally quite a lot to to to try to find vulnerabilities so far hasn't found anything but like they're very good at like probing into like very deep parts of the system and exploiting trying to exploit things and trying to escalate and get out of sandboxes. Um, so you know, it's it's it's something we're exploring very actively right now.

</details>

**>>**: 你们具体是怎么让 Agent 去遍历代码库的？你就直接说，嘿，去找出安全漏洞吗？

<details>
<summary>Original English</summary>

**>>**: How exactly do you get the agents to like run through the codebase? You're just like, hey, like find security v vulnerabilities.

</details>

**>>**: 额，不，你就把它放进一个沙箱里，然后对它说，你能试着解释——

<details>
<summary>Original English</summary>

**>>**: Well, no, you just like you just put them in a sandbox and and tell them like, can you try to explain?

</details>

**>>**: 就跑遍……就试着从沙箱里逃逸出来。就像密室逃脱一样，只不过是给 Agent 玩的。

<details>
<summary>Original English</summary>

**>>**: Just run through the can just try to escape from the sandbox. It's like escape the room but for agents.

</details>

**>>**: 太酷了。你们什么时候开始这么做的？我们几个月前开始做的，非常令人兴奋——

<details>
<summary>Original English</summary>

**>>**: Cool. When did you start doing that? We started doing it a few months ago and it's pretty exciting

</details>

**>>**: 大概是 Fable 出来的时候吧。

<details>
<summary>Original English</summary>

**>>**: like when Fable I guess came out.

</details>

**>>**: 对，大概就在同一时间。

<details>
<summary>Original English</summary>

**>>**: Yeah, roughly around the same time.

</details>

**>>**: 好的。

<details>
<summary>Original English</summary>

**>>**: Okay.

</details>

**>>**: 我对网络安全的看法是，我觉得它们确实非常擅长发现漏洞，但我认为你同样也可以非常好地把它们用于防御。所以我觉得像 Modal 以及现在的许多其他公司，如果你去跟几乎每一位 CISO 交流，我敢肯定他们都在思考同一件事，那就是我们如何防御性地使用 Agent 来修复我们所有的漏洞。所以随着时间推移，在某种程度上我其实并没有那么焦虑。我认为如果真有什么变化的话，Agent 以及网络安全领域的所有突破反而会让世界变得更加安全。

<details>
<summary>Original English</summary>

**>>**: I mean my my view on like cyber security is that you know I actually think they're very good at finding vulnerabilities but I think you can also use them defensively very very well. So I I I think you know companies like modal and many other companies right now like I think you know if you go to talk to like pretty much every season I'm sure they're all thinking about the same thing like how do we use agents defensively to to to you know fix all our vulnerabilities. So over time actually in a way like I'm not that nervous. I think if if anything like agents and and cyber security all the breakthroughs in cyber security will will make the world safer if anything.

</details>

**>>**: 你觉得所有的网络安全公司、那些大型网络安全公司是不是都完蛋了？我不知道这是不是真的，因为我的意思是，你问的是一个远远超出我核心专业领域的问题，但当我思考网络安全时，你卖的很大一部分实际上是恐惧，这几乎是一种品牌和营销策略，就像显而易见的核心产品一样。但我认为品牌之类的事情在 AI 时代可以说更具价值，所以我不会贸然得出他们完蛋了的结论。我认为他们与企业客户有着深厚的关系，他们有大型销售团队，非常擅长讲恐怖故事之类的事情。我认为他们会继续在这方面表现得非常出色。

<details>
<summary>Original English</summary>

**>>**: Do you think that like all of the cyber security the big cyber security companies are just cooked? I don't know if that's true because I mean you're asking something that's like very far outside of my like core expertise but when I think about like cyber security a lot of what you're selling is effectively fear and that's almost like a branding and like marketing strategy as much as you know obviously the core products but I think you know brand and and things like that are actually like arguably like more valuable in the era of AI so I I I wouldn't necessarily jump to the conclusion that they're cooked hooked. I think they have, you know, deep relationships with the enterprise customers and they have, you know, big sales teams who are very good at telling, you know, spooky stories and and things like that. And and I think they're going to continue to be very good at that.

</details>

**>>**: 我这么问只是因为，对啊，你们自己在做这件事。你们并没有去找 Palo Alto Networks 之类的公司。不过我猜可能只有巨型企业才在乎这个。而且，如果出了问题，他们还可以甩锅给别人。

<details>
<summary>Original English</summary>

**>>**: I just ask cuz like, yeah, you're doing it yourself. You're not going to one of like the Palo Alto networks or whatever. But I guess like it's only like giant enterprises that care about that. Also, they can blame somebody if something goes wrong.

</details>

**>>**: 确实是这样。是的，很多情况下你确实想雇佣一家老牌供应商，以便把责任推给他们。我的意思是在某种程度上，这确实稍微减少了我们引入渗透测试人员（比如人类渗透测试员）的需求，大多数初创公司都会定期做这件事。以前我们可能会做——我其实不知道具体周期是多久，但我记得我们以前大概每六个月做一次。也许现在我们只需要一年做一次了。我不知道。但我觉得对于所有这些事情，人类也可以借助它们来提高效率。所以，我不知道。我也倾向于相信人类加上 AI 现在甚至更强大。所以也许可以说，我们可以引入非常擅长使用 Agent 的渗透测试人员，从而更快地发现漏洞。我不知道。我没那么——

<details>
<summary>Original English</summary>

**>>**: That is true. Yeah. Yeah. you kind of want to hire in many cases just like a established vendor uh in order to blame them. I I mean to some extent it it does reduce a little bit the need for us to do to bring in pentesters like human pentesters which most startups like do on a regular cycle. So maybe previously you know we would do it I actually don't know what the cycle was but but I think we used to do it like once every six months roughly. Maybe now we only need to do it once every year. I I don't know. But but like I think with all of these things, you know, humans can also use them to get more efficiently. So like, you know, like I I don't know. I'm kind of a believer also that like humans with AI is even more powerful now. So like maybe there's an argument that like we can bring in pen testers who are really good at using agents and, you know, find vulnerabilities even faster. I I don't know. I I'm not that you know,

</details>

**>>**: 我是个乐观主义者。我创办了一家公司。所以，我通常对一切都很乐观。但我绝不认为人类完蛋了，或者公司完蛋了。我认为在 AI 时代，很多公司都会弄清楚如何利用 AI 来变得更加高效。

<details>
<summary>Original English</summary>

**>>**: I'm an optimist. I started a company. So like, you know, I'm I'm generally like optimistic about everything. But like I I certainly don't think humans are cooked or companies are cooked. Like I think in the era of AI a lot of companies are going to figure out you know how to use AI to be even more efficient.

</details>

### 开发者体验与 Agent 体验

**>>**: 我想稍微转向聊聊开发者体验，因为早期，我的意思是哪怕现在，你们在这方面投入了很多精力，而且也谈论过很多。开发者体验现在还重要吗？我认为它仍然重要，然后我认为你——你大概是在想，或者说你谈论的背景是现在有了 Agent，对吧，开发者——

<details>
<summary>Original English</summary>

**>>**: I want to transition a little bit to like developer experience because like early on I mean even now like you guys focus a lot on that and you've talked a lot about that. Does developer experience even matter anymore? I think it still matters and then I think you're you're sort of you know like the context I think you're fish or like the thing you're talking about is like now with agents right like does developer

</details>

**>>**: 比如文档已经在那里了，Agent 会去看文档，诸如此类的事。

<details>
<summary>Original English</summary>

**>>**: like the docs are already there the agents are going to look at the docs like all that stuff

</details>

**>>**: 但就这一点而言，我们在实践中看到的是，几乎所有能带来良好开发者体验的东西，同样也能带来良好的 Agent 体验，也就是诸如拥有优秀的文档、拥有描述性的错误信息、拥有快速的反馈循环，对吧？我确实认为某些事情已经改变了。前几天我在用 Cloudflare 配置东西，我发现 Cloudflare 有时用起来出了名地让人烦躁，然后我扔了一个 Agent 过去，它就能直接在 Pulumi 中帮我配置好一堆东西。所以我必须说，Agent 确实让处理那些过去更难处理的事情变得稍微容易了一些。处理 YAML 给人类带来的折磨可以说稍微减轻了一点，因为你直接让你的 Agent 去处理就行了。但绝大多数情况下，我认为让开发者体验变好的因素，同样也会让 Agent 体验变好。我认为在某种程度上，基础设施随着时间的推移本来就需要变得更加程序化。我认为这一直是关于沙箱的论点，那就是你以前必须用 YAML 配置的东西，现在应该就是一个 SDK，应该更加命令式，比如启动沙箱、对它进行操作、销毁沙箱，对吧，而不是用某种 DSL 进行声明式配置。这也推动了一种之前可能不存在的稍微不同的界面。我认为不管怎样，SDK 和以往一样重要，甚至更重要。有没有什么东西是你们仅仅因为大多数人都在上面跑 Agent 而在产品中做出的改变？

<details>
<summary>Original English</summary>

**>>**: to that point though like almost all the things that make developer experience good also makes the agent experience good is kind of what we've seen in practice which is like things like having good docs having descriptive error messages having fast feedback effect loops, right? Like I do think there's certain things have changed. The other day I was like setting something up with Cloudflare and it's like I find Cloudflare like notoriously annoying to work with sometimes and and I threw an agent at it and it was able to like just configure a bunch of like as you know things in in Palumi for me and you know and and so I will say like agents does they do make it a little bit easier to work with things that are like harder to work with in the past you know like the sort of human toll of dealing with YAML has arguably gone down a little bit because you can just like you know tell your agent to deal with it but but For the most part, I I think you know the things that make developer experience good also make agent experience good. I think to some extent also like infrastructure over time anyway becomes and needs to be more programmatic. I think that's always been the thesis about sandboxes is that you know like things that you previously had to configure using YAML that should just be an SDK that should be more like imperative like launch a sandbox like do stuff with it tear the sandbox down right like rather than sort of declarative using using you know some sort of DSL it also pushes like a little bit of a different interface that maybe previously didn't exist. I think in either way like SDKs are as relevant as they as they always were if not more. Is there anything you changed in your product just because like you know most people are just running agents on on it?

</details>

**>>**: 我们确实——我们内部其实也跑了大量的测试，在测试中我们让 Agent 去构建一个移动应用并运行它。一件非常具体且有点搞笑的事情是，我们实际上发现，由于 Agent 的训练数据，现在要废弃某些东西变得非常困难。我们发现 Agent 往往特别喜欢使用旧版本的 Modal 语法，并且——

<details>
<summary>Original English</summary>

**>>**: We do uh I mean we also we actually do run a lot of internal tests where we have agents we tell agents to like build a mobile app and run it. And I mean a very concrete thing that is kind of funny is that we've actually seen that like because of agent training data it's very hard to deprecate things now. uh we see that like agents often like love using you know old versions of modal syntax and

</details>

**>>**: 而且很难引导它们改掉这个习惯。所以我们今后实际上不得不更加保守一点，比如在过去一年左右的时间里，在如何废弃和移除功能方面。这需要我们非常小心地去更新网上现存的每一个示例。是的。

<details>
<summary>Original English</summary>

**>>**: and it's kind of hard to nudge them away from that. So so we've actually had to be a little bit more conservative going forward like you know over the last year or so with with how we deprecate and remove features. It takes we have to be very careful to update every single example that's out there online. Yeah.

</details>

**>>**: 而且……

<details>
<summary>Original English</summary>

**>>**: And and and you know

</details>

**>>**: 技巧，对吧？

<details>
<summary>Original English</summary>

**>>**: skills, right?

</details>

**>>**: 对，有类似的事情。但网上现在也有海量的 Modal 代码进入了训练数据。我认为这是一个挺有意思的例子。顺便说一句，另一件事显然是，类似于搜索引擎优化，现在有了 Agent 引擎优化，或者不管大家怎么称呼它，Agent 优化。我们经常运行内部基准测试，我们会问 Agent，比如：嘿，你能帮我们部署一下 Stable Diffusion 吗？使用任何你想用的工具。然后我们观察它是否会推荐 Modal。这些对我们来说都是非常有用的追踪指标，随着时间的推移去——

<details>
<summary>Original English</summary>

**>>**: Yeah. There's like stuff like that. But but like there's also an insane amount of like modal code that's now like online too that goes into the training data. I've seen like that to be like kind of an you know a little bit of like an interesting example where like another thing by the way too is like there's obviously like the sort of a similar to like search engine optimization there's like agent engine you know whatever people call it agent optimization. We often like run internal benchmarks and we're like ask an agent like hey like can you deploy uh stable diffusion for us? use whatever tool you want and we see if it recommends modal or not and those things are very useful for us to sort of track over

</details>

<!-- chunk 9/13 -->

### 面向 Agent 与搜索引擎优化

**>>**: 时间，或者比如“嘿，启动一些沙箱”，或者比如“嘿，把所有的沙箱供应商排个序”。所以我们花很多时间去做那些事情，以确保……

<details>
<summary>Original English</summary>

time or like hey spin up some sandboxes or like hey like rank all the sandbox vendors.

**>>**: So so we we spend a lot of time like doing doing those things to to make sure

</details>

**>>**: 我的意思是，针对这个你们会做什么？是的，你说“嘿，建这个 Stable Diffusion 的东西”，它到底推不推荐 Modal 呢？比如是的，针对这个你们会怎么做？

<details>
<summary>Original English</summary>

**>>**: I mean what do you do about that? Yeah, you say hey like you know build this stable diffusion thing does it recommend modal or not? Like yeah what do you do about that?

</details>

**>>**: 是的，我认为那更难。我觉得，你知道，这就像搜索引擎优化。我认为主要还是通过内容，就像你必须发布大量的内容。

<details>
<summary>Original English</summary>

**>>**: Yeah I think that's harder. I I think you know it's like search engine optimization. I think it's primarily through content is like you just have to put out a lot of content.

</details>

**>>**: 有意思。

<details>
<summary>Original English</summary>

**>>**: Interesting.

</details>

**>>**: 你在某种程度上也可以稍微多观察一下外界的认知，我觉得，比如你可以问一个 Agent，比如“按可靠性给所有沙箱供应商排个序”，或者“按价格给所有沙箱供应商排个序”，然后看看结果，确实感觉 Agent 会稍微更容易误解定价以及诸如此类的事情。所以我们也花很多时间让内容变得更清晰，并且对 Agent 来说更容易理解，因为我们知道所有的索引，比如外面谈论 Modal 的所有东西都在起作用。

<details>
<summary>Original English</summary>

**>>**: You can also to some extent like sort of see the perception I think a little bit more like you can ask an agent like you know how does you know rank all the sandbox vendors by reliability or rank all the sandbox vendors by price and and sort of see and it does feel like agents are a little bit more prone to like misunderstanding pricing and and you know things like that. So we also spend a lot of time like just making content more clear and more like you know understandable for agents cuz we know that all the indexing like everything that's out there and that's talking about modal.

</details>

**>>**: 你们有没有想过就建一堆 GitHub 仓库，然后让 Agent 在里面写一堆 Modal 的代码？你们试过吗？

<details>
<summary>Original English</summary>

**>>**: Have you thought about just like making a bunch of GitHub repos and having the agents like write a bunch of modal code in there? Have you tried that?

</details>

**>>**: 垃圾内容大炮（Slop cannon）。呃，我觉得事实是这大概是你能做的事情。我的猜测是，现在的 LLM 训练数据可能对一开始什么是 AI 输出相当不敏感，你大概可以制造出很多粗制滥造的内容……

<details>
<summary>Original English</summary>

**>>**: Slop cannon. Uh I think the truth is like that is probably something you can do. My my guess is like LM training data today is probably quite insensitive to like what's like AI output in the first place and you can probably like create a lot of slop like

</details>

**>>**: 我们考虑过这个，我并不喜欢那个主意，但在理论上，就像早期的 SEO，并且在某种程度上现在依然如此，自动生成内容是一种非常有效的策略。我认为是有可能的，比如你知道，你现在也可以做那些事情。

<details>
<summary>Original English</summary>

**>>**: we thought about it like I don't love that idea but like in theory like much like you know SEO in the early days and still to some extent like autogenerated content is like a very effective strategy I think it's possible like you know you could you can do those things too today

</details>

### 前线部署工程师（FDE）的角色

**>>**: 我想聊聊 FDE。显然你们会招前线部署工程师（forward deployance engineers），他们具体做什么？我们处在一个构建应用和构建一些就在几年前我们还无法构建的事物的新时代，我们看到很多公司需要一些帮助，对吧，所以我们在几年前开始投资 FDE，但真正大幅扩张其实是在今年。我认为我们今年开始时大概有 4 个 FDE，现在我想我们大概有 24 个左右，所以我们增长了很多。他们做很多——你知道，这不完全是 Palantir 的模式，但他们会做大量的深度客户互动，比如他们和很多客户一起进行性能调优。特别是在大型语言模型方面，我们看到与客户坐在一起、训练草稿模型（draft models）以及微调参数、vLLM 和 SGLang，能带来极大的收益。他们经常去修复 bug，或者也不是修复 bug，而是在客户遇到问题时，他们通常会与客户一起努力找出“我们如何规避这个问题”。或者我们广泛使用 FDE 的另一件事是主动介入，比如如果我们看到某些客户在 Modal 上存在过度配置（overprovisioning），例如客户申请了过多的 CPU 或过多的内存，那往往比较昂贵，我们试图发现这些情况，并尝试与这些客户坐下来聊：“看，你们现在在 Modal 上花了很多钱，我们其实可以帮你们省钱。”然后当然，对于正在进行的活跃交易，我们会帮他们从其他平台迁移代码，等等。

我觉得我们绝没有打算成为一家重服务的公司。我认为 FDE 的目标，一是参与销售流程并促成交易；二是服务客户并提供一些客户支持；但实际上我认为最重要的是三：弥补产品上的空白，以便我们后续能将其转化为真正的功能。所以很大程度上，任何 FDE 所做的事情，我的问题始终是：长期来看，我们如何把这个做成产品，从而不再需要 FDE 来做这件事？

<details>
<summary>Original English</summary>

**>>**: I want to switch to FTEEs apparently you guys hire like forward deployance engineers like what do they do? We're in a new era of like building applications and and and you know things that we couldn't build you know just a few years ago and we see a lot of companies that you know they need a little bit of help right like you know and so we started investing in FDES a couple years ago but it but it's really been this year we've kind of scaled it up a lot I think we started this year having like four fds now I think we have like 24 or something like that so we've grown a lot and they do a you know it's more it's not exactly the counter model but they do a lot of like heavy you know sort of customer engagement like they work with a lot of customers on performance tuning especially with LMS we see that there's so much benefit from like you know sitting down with customers and training draft models and tweaking uh you know parameters and DM and SG lang um they often you know fix bugs or or not fix bugs but like you know when customers run into issues like they often work with customers trying to figure out like how do we work around that or uh another thing we we've used FD these a lot for is like you just kind of proactively you know if if we see certain customers you know overprovisioning with modal like customers requesting too much CPU or too much memory for instance like that's kind of expensive and like we we try to catch those things and we're trying to sit down with those customers like yo like you're spending a lot of money on modal right now we can actually help you save money and then of course like with with sort of active deals you know we we help them migrate code from other platforms uh things like that um I think you know we we never have the intent ention of becoming like a service heavy business. I I think that the goal for FDS is like you know A is to be a part of you know the the sort of sales process and like closing deals. B is to serve customers and and do some like you know customer support but like I actually think like the most important thing is like C is like bridging gaps in the product that we later want to turn into like real features. So I think to a large extent, you know, anything an FDE does, you know, my question is always like long-term, how do we turn this into product? So we don't need an FD for this.

</details>

**>>**: 是的。

<details>
<summary>Original English</summary>

**>>**: Yeah.

</details>

**>>**: 你们招 PM 吗，

<details>
<summary>Original English</summary>

**>>**: Do you guys hire PMs,

</details>

**>>**: 产品经理？

<details>
<summary>Original English</summary>

**>>**: product managers?

</details>

### 产品管理与团队演进

**>>**: 不招。

<details>
<summary>Original English</summary>

**>>**: No.

</details>

**>>**: 你会说这些 FDE 算是某种伪 PM 吗？

<details>
<summary>Original English</summary>

**>>**: Would you say these FDAs are kind of like pseudoish PMS?

</details>

**>>**: 这算是一个有点不同的职能。我觉得在偏向面对客户的一侧他们确实是，但在更偏向对内的一侧，产品管理有单独的一部分，它更偏向于“Modal 接下来应该投资哪些基础构件”；然后介于两者之间的是，比如观察 10 到 20 个不同的客户，他们要求的都是稍微不同的东西，但其中有什么规律？我们如何将其转化为产品？我们内部确实有人在做产品，这是一种演进，我们内部有些人之前是开发者布道师（DevRel）或工程师，在展现出对我们必须构建的内容进行高度战略性思考的极强天赋后，基本上成为了产品经理。所以我其实并不是反对产品管理。我确实认为过去很多公司招产品经理招得太急切了，我认为存在这样一种风险，你有点——我在很多产品中能看出来，某些产品你能看出就是有急于求成的产品经理只是想出了一些小组件似的东西然后就发布了。我认为在一家基础设施公司把产品管理做得非常好是非常非常难的，因为我认为这需要非常深层次的战略思考，去思考什么是基础构件，我们一到两年后想走到哪里，因为事实是构建基础设施非常困难；以及我们如何确保最终不会出现 35 个看起来差不多但做的事情都略有差异的功能。那种层次的思考是很难得见到的，正因如此，我们目前还没有积极地去建立一支产品管理团队。

<details>
<summary>Original English</summary>

**>>**: It's a little bit of a different function. Like I I think certainly on the more like you know customerf facing side they are but there's like you know on the more like inward you know internal side like there's a sort of separate part of like product management which is more like what are the next building blocks Moto should invest in and like you know and then there's like something in in in between like you know looking at like maybe 10 20 different customers. They're all asking for like slightly different things but maybe what are the patterns like how do we turn this into product? We do have people doing product with us and and it sort of evolved you know we've had people basically like become product managers after previously being either deval or or engineers just showing strong aptitude on on doing thinking very strategically about what we have to build. So I'm actually not like anti- product management. I do think that a lot of companies in the past hired product management product managers too eagerly and and I think there's a risk that you you kind of I can sort of see it in a lot of products like certain products like you can tell like there's just like eager product managers that just thought of like kind of like widgety things and just ship them. I think doing product management at an infra company really well is very very hard because I think it takes like a very deep you know level of strategic thinking thinking about like what are the foundational building blocks where do we want to be in one to two years because the truth is building infrastructure is very hard and how do we make sure we don't end up with like 35 features that are like kind of similar looking but all do like a little bit slightly different things. That sort of level of thinking is something that you know is very rare to find and and for that reason we haven't aggressively tried to build up a product management team yet.

</details>

**>>**: 是的，这很有道理。你会如何评价你们团队自生成式 AI 以来的演变？因为我想，是的，你显然之前在 Spotify 工作过，你有过某种团队架构。现在既然我们有了代码 Agent，你们的团队架构是否有很大演变？

<details>
<summary>Original English</summary>

**>>**: Yeah, that makes sense. How would you say your teams have been evolving maybe like since GI? Cuz I would assume Yeah, I mean you obviously worked at like Spotify. You had like a certain team structure? Um have your team structures like evolved a lot now that you know we have coding agents?

</details>

**>>**: 说来有意思，是的，我确实认为团队架构改变了很多，但我其实不确信这是生成式 AI 推动的。我特别看到的一点是，有一种重新转向作为 IC（独立贡献者）的聚焦与回摆，我其实认为这对整个行业来说是非常非常积极的。我觉得如果你回顾 10 年前、20 年前的行业，每个人都想进入管理层，因为那是你能获得更多薪酬、更多认可和更多声望的途径。我认为这种转变其实在生成式 AI 之前就已经开始了，但我确实认为它在 AI 的推动下被大大加速了。比如我们向 Modal 的每个人都明确表明，管理者和 IC 在声望上没有任何差别，所有人都是技术人员的一员，最终看的是你的贡献。我们看到很多前管理者转回做 IC，因为他们想回去写代码。而且也出现了一种远离非技术管理者的转变。几乎每个人，包括我，我在 Modal 依然写很多代码，在 Oxhat 也是，技术团队里的几乎每个人，以及很多不在技术团队里的人，依然在写代码。所以对我来说这算是一个近期的现象，但我其实不知道这是否必然是由生成式 AI 造成的，但我认为生成式 AI 大大加速了它，因为它使得写代码的成本更低、更容易了。所以如果你有非技术人员提交代码，比如怎么做……

<details>
<summary>Original English</summary>

**>>**: in a funny way like yes I I do think team structures have changed a lot but I'm actually not convinced it was like geni driving that. I I think in particular like one thing I've seen a lot is that there's been sort of a focus like a swing back towards being an IC that I actually think is very very positive for the space as a whole. I think you know if you look back at the space like 10 years ago 20 years ago everyone wanted to be in management because that was a way you you would get more money and more you know more recognition and more prestige. I think that shift actually started even before Gen AI but I do think it's like heavily accelerated with AI like you know we we we make it very clear to everyone at modal that like manager RC it's like there's no difference in prestige like everyone is just a member of technical staff you know it's about ultimately your contributions and we see a lot of ex-managers you know becoming IC's and and because they want to go back and build code and so and you know and there's been there's been sort of shift away from like you non-technical managers. Everyone pretty including me. I I still write a lot of code at Model and in Oxhat 2 and and pretty much everyone in in the tech team and a lot of people who are not in the tech team still write code. So that to me is like you know a recent phenomenon but but I actually don't know if it's like necessarily cost by Gen AI but I think Gen AI has like greatly accelerated it because it it made it even lower the cost of like writing code is even easier. So if you have like non-technical people like committing code like how do

</details>

<!-- chunk 10/13 -->

### 代码审查与自动化测试

**you**: 你们怎么审查那个，比如你们大家是怎么做代码审查的？

<details>
<summary>Original English</summary>

**you**: how do you review that like how do you guys do code reviews?

</details>

**>>**: 我们做代码审查，但我们认为这是可选的。我是说，对我来说，很大程度上我的观点是，代码审查在很多情况下就像是大家试图逃避把东西合并到生产环境的责任。如果你有那种文化，对我来说这就表明你需要向 CD 和 CI 以及类似的东西投入更多，尤其是 CI，但也有 CD，持续集成，因为它是部署。我们做代码审查，我是说，当我写代码时，偶尔我会问原作者，比如“这符合你的思路吗？我希望我没有从根本上改变架构。”但我们内部也明确表示，代码审查在很大程度上是可选的。而且，如果你只是修改文档，如果你只是做一些基础的事情，就不要等着让人类去看它，特别是在 AI 时代。为什么每段代码都需要让人类看一遍？你没必要这么做。

<details>
<summary>Original English</summary>

**>>**: We do code reviews but it's we we think of it as optional. I mean for most my my view is like code reviews in in large part is like people in many cases trying to just escape the the accountability of like you know merging things into production and and if you have that like you know if you have that culture like then to me that's a sign that you need to invest way more in you know CD and and CI and and and things like that CI in particular but also CD continuous integration because it's deployment we do code reviews like I mean like when I write code like occasionally like I'm I'm asking you know authors like is this in line with how you think about things? I hope I'm not changing the architecture fundamentally. But we also make it clear internally that like code reviews are are quite optional. And you know if you're just changing docs, if you're just doing you know some basic stuff like don't wait for a human to look at it especially in the era of AI. Why do you need a human to look at every piece of code? You don't have to

</details>

**>>**: 但这就要求你在公司内部围绕测试有非常好的控制机制。

<details>
<summary>Original English</summary>

**>>**: but that does require you to have you know very good controls you know internally around you know testing

</details>

**>>**: 对一家公司来说。是的。完全正确。像基础设施公司，我们在正常运行时间方面需要比普通初创公司多一个 9，对吧。

<details>
<summary>Original English</summary>

**>>**: for a company. Yeah. And exactly like you know infra companies like we we need one more nine than the average startup right

</details>

**>>**: 就正常运行时间而言。

<details>
<summary>Original English</summary>

**>>**: in terms of uptime

</details>

**>>**: 但这些是你必须做出的投资。你必须构建对各种情况非常有弹性的系统。你必须在各处设置速率限制。你必须解耦系统。你必须确保没有任何单点故障。它们必须具备极其优秀的测试覆盖率。这些天 Agent 其实非常擅长写测试，而在几年前，我认为这是 Agent 严重缺失的核心能力之一。现在它们实际上相当擅长，因为我觉得写好测试需要你暂时跳出你正在尝试做的事情，甚至需要有一点唱反调的角度，但现在它们写测试也确实挺厉害的。所以我觉得所有这些都会有帮助。

<details>
<summary>Original English</summary>

**>>**: but like you know these are investments you you just have to make like you have to build systems that are very resilient to like you know you have to have rate limits everywhere. You have to decouple systems. You have to make sure that like nothing is a single point of failure. They have to have extremely good test coverage. Agents are actually really good at writing tests these days, which was like, you know, a few years ago I thought like one of the major things missing in agents. Now they're actually quite good at like because I think it takes a little bit of like sort of kind of like need to step out of what you're trying to do for a second and be almost a little bit like devil's advocate to write good tests, but now they're actually quite good at writing tests too. So I think I think all these things help.

</details>

### 编码模型与内部试用

**>>**: 你们是使用前沿模型来编写代码，还是你们尝试过开源模型？

<details>
<summary>Original English</summary>

**>>**: Do you guys use like frontier models for coding or do you guys have you guys experimented with uh like the open source ones?

</details>

**>>**: 我们什么都尝试，不过是的，我是说最初用了很多 Cursor，然后当然还有 Claude 和 Codex，现在很多人在使用 Night Shift 以及所有这些开源工具或其他技术栈。所以我倒没有特别强烈的倾向，我希望大家去尝试不同的东西。我们使用前沿模型，也使用开源模型。我们现在正努力在内部做更多的 dogfooding，因为我们实际上正在非常大的规模上为很多开源模型运行推理，我认为在很多 Agent 开发中使用我们的内部端点也是很有帮助的。所以我们尽量稍微推广一下这个做法。

<details>
<summary>Original English</summary>

**>>**: We experiment with everything but yeah I mean you know initially was a lot of cursor then you know of course claude and codeex and and now a lot of people are using you know night shift and and all these open source stuff or or other stacks so I don't necessarily have like a strong point of view like I want people to experiment and try different things like we you know use frontier models use open source models we're trying to do a little bit more dog fooding internally now that we're actually running inference for a lot of the open source models like at a very large scale I think it's also helpful to like use our internal endpoints for a lot of agentic development Uh, so we try to promote that a little bit.

</details>

### 云原生与私有化部署之争

**>>**: 大概一年前，或者两年前我读到过一些内容，你说过你认为你们不会有很大的本地私有化部署（on-prem）业务。你现在对这个看法有所改变吗？

<details>
<summary>Original English</summary>

**>>**: Something I read maybe like I don't know a year ago, maybe like two years ago, you were saying that you didn't think that there was going to be like a big onrem business for you guys. Um, have you maybe like changed your opinion on that?

</details>

**>>**: 没有，我没有改变我的看法。我认为 Modal 对我而言，我是一个云原生的极致主义者（cloud maximalist）。退一步说，当云在 2008 年、2009 年或什么时候刚出现时，我的第一反应是那太疯狂了，为什么我要把我的代码放到别人的电脑上去运行，这简直不可理喻。然后大概六个月后，我就开始这么做了。我认为我花了六个月改变想法，而企业可能又花了 15 到 20 年。但你看像 Snowflake，或者我是说 AWS，而且我觉得还有很多例子，像 Datadog 等等，云显然正在胜出，对吧，多租户系统显然正在胜出。对我来说，本地私有化部署越来越像是一种过时的商业模式。而且我其实认为像 BYOC、VPC 对等互联（VPC peering）这类东西，对我而言，它们反映的是一种过时的安全模型，即“我们需要保护自己网络内部的一切”，对吧？就像把网络当作护城河，我认为这已经不再成立了，对吧？我们已经转向了真正更健壮的安全范式，比如零信任之类的东西。

所以对我来说，至少从安全角度来看，这些东西越来越显得过时。从我们的角度来看，我们拥有对整套基础设施技术栈的完全控制权。我们租用所有硬件。我们部署并管理所有基础设施。我们在所有主机上部署并管理健康状况并监控所有指标。这意味着我们可以非常快速地迭代，构建出更出色的产品，我认为这非常非常有价值，而过去那些客户拥有必须部署在客户环境中的企业版软件，他们必须非常仔细地考虑版本发布管理并处理依赖关系。就像我们根本不在乎，如果我们想引入一个新数据库，我们就可以引入一个新数据库，因为我们对它拥有控制权，我们不需要考虑客户能访问什么。所以对我来说，多租户有太多不同的好处。

话虽如此，如果将来我们要与某家非常大的财富 500 强客户合作，而他们要求 BYOC，我们过去也这么做过，我们会给他们报一个数字，那个数字非常高，目前还没有人同意，但谁知道呢，在合适的价格下我仍然会去构建它。而且我认为可能另外还有一件我觉得挺有意思的事，就是理论上 BYOC 也可能是一种通过特定方式合作并获取算力容量的途径。比如我们有时会与 Neolabs 合作，而那些 Neolabs 已经拥有非常庞大的预留算力，问题就在于，当他们已经拥有算力时，我们如何让他们运行 Modal？BYOC 可能是个解决方案，我们仍然可以把控制平面保留在我们的环境中。而另一面是，我们甚至也许可以在那部分算力上运行其他人的任务，所以在理论上你可以做一些挺有趣的事情，你可以把所有这些算力聚合到一个大池子里。

我们对其中的一些想法感到很兴奋，但总体而言，我觉得本地私有化部署我不知道我们是否会去做，但 BC——也许 Bring Your Own Cloud。我老是说 BC，我应该解释一下缩写词。

<details>
<summary>Original English</summary>

**>>**: No, I have not changed my opinion. Um I think modal to me I I'm a cloud maximalist and maybe to take a step back like when when the cloud came in 2008 2009 or whatever my first reaction was like that's crazy like why would I want to take my code and run it on someone else's computer that's like insane and then like 6 months later I was doing it and I think you know like it took me 6 months to change my mind it took probably enterprises like another 15 to 20 years but like you look at you know vendors like snowflake or I mean AWS and like you know I I think there's many examples of data dog etc like the cloud is clearly winning right like and and the multi-tenant systems are clearly winning and you know to me onrem looks increasingly like sort of a legacy business model and and I actually think you know BYOC you know sort of VPC peering like all of these things you know like to me they reflect sort of an outdated security model of like we need to protect everything inside our own network, right? Like using the network as a moat and that I don't think is true anything anymore, right? Like we've sort of moved on to more like actually robust security paradigms like you know zero trust and things like that. And so to me the things like they they look increasingly as like outdated at least from a security perspective from our perspective also like the fact that we have full control over our entire infrastructure stack. We rent all the hardware. We deploy we manage all the infrastructure. We deploy and like manage health and observe you know all the metrics on all the hosts. It means we can iterate very fast and build a greater product and and I think that's very very valuable versus you know customers in the past who had enterprise additions that they had to deploy on customers environment. they have to be very you know they have to think very carefully about release management and and having depend like like we don't care like if we want to introduce a new database like we can introduce a new database because we have control over it like we don't need to think about what customers have access to. So to me multi-tenency is is it has so many different benefits. I mean that being said like you know if we were to work with like you know some very large Fortune 500 customer in the future and you know they ask for BYOC you know we've done this in the past we'll give them a number like you know that number is very high and no one said yes to it so far but like who knows like you know at the right price I I would still build it and and I think there's like maybe separately like another thing which I think is interesting which is like in theory BC might also be a way to work with and and get capacity in certain ways like we we sometimes work with Neolabs and those Neolabs already have very large capacity reservations and you know the question is like you know how how do we how do we get them to run modal when they already have capacity and BYC might be a solution we can still keep the control plane in in our environment and the other flip side of that is like we could maybe even run like other people's stuff on that capacity so so there's some like kind of fun stuff you could do in theory where like you can sort of you know like kind of aggregate all that capacity into one big pool We're excited about some of those ideas, but in general, like I feel like on prem I don't know if we're ever going to do, but BC like maybe bring your own cloud. I keep saying BC. I should I should explain acronyms.

</details>

### 资金用途与运营杠杆

**>>**: 假设，比方说你很快就会筹集更多资金。你会把这笔钱用在什么地方？

<details>
<summary>Original English</summary>

**>>**: Um let's say hypothetically you are going to raise I should send more money like soon. What would you use that money for?

</details>

**>>**: 我是说，就像我提到的，在这种算力情况下，很大一部分资金——或者我应该说是所需的现金流——是算力预付款，对吧？所以对我来说，这代表了目前资金的最佳用途。我们正在非常积极地扩大算力容量。也许我们将来会转向其他类型的部署模式，所有权模式之类的。但我认为这其中总是会包含一个现金部分，比如某种首付款或预付款之类的东西。所以这对我来说是目前现金的最大用途。当然还有其他开销，比如工资、办公场地以及诸如此类的事情，但实际上在我们财务状况的大格局中，那些现在基本只是个四舍五入的零头。

<details>
<summary>Original English</summary>

**>>**: I mean like I mentioned like in in this capacity situation the a lot of the money a lot of the cash flow I should say that's required is is capacity prepayments, right? and and so that to me represents the best use of of of cash today. Uh we're ramping up capacity capacity very aggressively. Maybe we move into, you know, other types of deployment models in the future, ownership or whatever. But I think there's always going to be a cash component of that, like some sort of down payment or prepayment or some sort of that. So that to me is is the the greatest use of cash right now. There's of course other things like you know salaries and office spaces and stuff like that but that actually in the grand scheme of like our our uh financials like it's it's basically a rounding error right now.

</details>

**>>**: 是的。很有意思。你认为这会发生改变吗？

<details>
<summary>Original English</summary>

**>>**: Yeah. Interesting. Do you think that's going to change?

</details>

**>>**: 不会。我认为我们在业务中拥有的这种运营杠杆可以说是非常惊人的。你看，我们有 200 名员工，他们要花很多钱，但是 GPU 花的钱要多得多。

<details>
<summary>Original English</summary>

**>>**: No. I I think you know the the sort of operating leverage that we have in this business is kind of insane. Like you know we have 200 employees you know they cost a lot of money but you know the the the GPUs cost a lot more money.

</details>

**>>**: 是的。如果你必须说出前几项，比如三件你最关注的事情，或者是公司最……

<details>
<summary>Original English</summary>

**>>**: Yeah. If you had to say like what are the top like I don't know like three things that are your biggest focus or the business's

</details>

<!-- chunk 11/13 -->

### 最大重心与公司建设

目前最大的重心，你会说具体是哪些？

<details>
<summary>Original English</summary>

biggest focus right now like what would you say those are

</details>

**>>**: 算力容量以及某种财务复杂性，还有大体上，比如我们如何看待那个领域，如何考虑定价和打包，如何看待持有与租赁之间的张力，我们应该走向更偏向新型云（neo cloud）的方向，还是走向相反的方向，即某种反定位——这大概是我思考最多的一点。第二大我经常思考的事情，大概更偏向产品策略，比如我经常在想下一个构建块是什么。比如如果我们做更多 Agent 类的东西，我们需要哪些构件？是否存在某些存储原语或计算原语，或者总体而言，未来几年全世界会恍然大悟并意识到他们需要什么，而理想情况下我们在那个节点已经做好了准备。总的来说，我们在预测需求并在无服务器函数和沙盒（sandboxes）出现之前就提前构建产品方面一直做得相当不错，所以下一个东西会是什么。

然后我想说的第三点我花很多时间思考的，其实更多是围绕文化和公司建设这类事情。我们最近刚突破了 200 人。我们的增长极其迅速。到今年年底我们可能会达到 250 人。当你在飞速发展时，有 250 个人都在努力寻找自己如何能为 Modal 带来最大价值，需要确保他们拥有正确的上下文、正确的动力，让他们每天都很兴奋来上班，因为他们能构建极其酷炫的东西，并且他们知道是什么让 Modal 取得成功、他们自己能做些什么。校准激励机制，确保我们拥有非常积极的文化，让大家享有去做很多事情的隐性信任，但也有交付最优秀成果的责任担当，并在没做到时被问责。对我来说，在当前这个规模下，这些都是极为关键的事情。

当团队只有 10 人、20 人、30 人时，大家基本可以同坐一室，一切都心照不宣，你差不多凭感觉就能体会到。大家能看懂我，我什么时候有点恼火他们能看出来，我什么时候高兴他们也能看出来。而现在我们有 250 人了，大家不一定能看得到，当然还有很多新人，他们去跟 CEO 说话可能会有一点紧张之类的。所以，我该如何保持平易近人，以及如何……这就像邓巴数（Dunbar's number）一样，我觉得这个概念比起其他东西可能更有点编造的成分，至少它背后的故事是这样，但它其实依然是某种真实存在的，就像在 150 到 200 人左右的规模，奠定文化基础是极其、极其重要的。

<details>
<summary>Original English</summary>

**>>**: capacity and the sort of financial complexity and you know in general like how do we how do we think about that space how do we think about pricing and packaging how do we think about the sort of tension between ownership and renting should we be go in a more neo cloud direction should we go in the opposite direction the sort of counter precision like that's probably the biggest thing that I think a lot about uh the second biggest thing I think a lot about is um probably around like more like product strategy like I think a lot about like what is the next building blocks like if if we you know do more like agentic stuff like what are the things we need you know are there certain storage primitives or compute primitives or in general like what is the thing that the world is going to wake up and realize they need over the next few years and and ideally we have that at that point we've been pretty good in general at like you know anticipating demand and building products in advance of it with the serless functions and the sandboxes so what's the thing. Then I would say like actually the third thing I think a lot about is like more around like culture and company building and stuff like that. I mean we recently crossed 200 people. We're we're growing extremely fast. We'll probably hit 250 by the end of the year. Like when you're growing very fast, you have 250 people that are all trying to figure out how they can add the most value to Modal and you know making sure that they have the right context that they have the right motivation that they're excited to come into work every day cuz they get to build something incredibly cool and they know you know what makes modal successful what they can do. aligning the incentives and and making sure that you know we we people have like a very positive culture where they have the sort of implicit trust to do a lot of stuff but also the accountability to like you know deliver the best things and you know and and be held accountable to like if they're not doing it. To me those are like you know super critical things around this scale. Like when when you're like 10 20 30 people you can all just like kind of sit in a room and like it's all kind of implicit and you kind of just like feel it. people can sort of read read me like they can tell me when I get a little bit annoyed. They can tell when I'm happy like now we're 250 people and like people don't necessarily see it and you know of course there's like a lot of new people they're like maybe a little bit nervous to like talk to CEO and like all this stuff. So like you know how do I remain approachable and how do I like it's it's there's like the Dunbar number which I think is like more sort of you know faked than than anything like at least like the story behind it but like it is actually kind of real still like there's something around like 150 200. We're like laying the foundation of the culture is very very important.

</details>

### 团队扩张与工程招聘

**>>**: 你们在未来一年打算招聘多少人？

<details>
<summary>Original English</summary>

**>>**: How many people are you guys trying to hire over the next year?

</details>

**>>**: 在过去 12 个月里，我们按年化计算增长了大约 4 倍。我认为在相对层面上，这是一种不可持续的增长率。我见过这种情况：团队每年翻一番，这并不是特别难做到。但 4 倍的话，你开始会看到文化漂移。你开始看到不同工作风格的孤岛。你开始看到有人在做非常具有投机性的事情，诸如此类。这是我在工程团队中一直留意防范的事情。你去跟某个工程师交谈，我问：“你在做什么？”结果发现他们正在做一些非常边缘的东西，这真的是你该花时间做的事吗？所以飞速增长是有这种代价的，而且也有让人熟悉上手的成本。所以我不知道，我觉得到今年年底大概 250 人，到明年年底，我们还会继续增长，可能是 2.5 到 3 倍，所以很可能明年年底我们会达到 700 人左右。

<details>
<summary>Original English</summary>

**>>**: We've grown about 4x on an annualized basis in the last 12 months. I think that's like an unsustainable growth rate on a relative basis. I've seen that, you know, you can double the team every year and that's not super hard to do. But Forex, what you start to see is, you know, cultural drift. You start to see islands of different working styles. You start to see people doing like very speculative things like that. That's something I always watch out for in the engineering team. You go and talk to the an engineer and I'm like, "What are you working on?" And and it turns out they're like building something like kind of like fringe and like is this really what you should spend time on? So growing very fast has that cost and you know it has the cost of ramping people up. So I I don't know I think by the end of the year maybe 250 by the end of next year you know but but like you know we're going to keep growing like maybe 2 and a half 3x so it's very likely we'll end up like next year like 700 people or something like that.

</details>

**>>**: 我想大部分都会是工程师。

<details>
<summary>Original English</summary>

**>>**: I'm going to assume most of those are engineers.

</details>

**>>**: 大部分是工程师，销售也有很多。

<details>
<summary>Original English</summary>

**>>**: Most mostly engineers have sales a lot too.

</details>

**>>**: 好的。哪种类型的工程师？

<details>
<summary>Original English</summary>

**>>**: Okay. What kinds of engineers?

</details>

**>>**: 主要是系统工程师。我的意思是，我们一直非常深入于 Linux、文件系统、可扩展系统、网络以及云等领域。所以这就是我们寻找的核心，真正擅长这些东西的人。我们也在密切关注，因为我们在技术栈上稍微往上移了一些，我们在大模型推理（LM inference）领域做了大量工作。所以现在我们要应对围绕 CUDA、GPU 以及 MFU 的另一套考量，比如如何最大化每块 GPU 能产出的 token 数量等等很多方面的事情。而且，尽管依我之见，该领域的许多工作其实最终仍然是系统驱动的，因为事实证明像 KV 缓存（KV caching）和路由实际上仍然是非常偏系统层面的，这些都是非常重度依赖系统的问题，不过确实也更偏向 GPU 性能这类事情。我们正在开始组建一支研究团队。我们非常兴奋能进军诸如后训练（post-training）、模型蒸馏以及更好的量化方法等方向……

<details>
<summary>Original English</summary>

**>>**: It's primarily systems engineers. I mean, we've always been like very deep into sort of, you know, Linux and file systems and scalable systems and networking and and cloud and and stuff like that. So, so that that's that's the core of what we're looking for like people are really good at those things. We're also looking a lot at like you know more like cuz we moved up in the stack a little bit like we're doing a lot of work in the LM inference space. So now we're dealing with a separate set of concerns around, you know, CUDA and like GPUs and and and and MFU, you know, like maxing out the tokens that you can get per GPU and and and a lot of that things. And you know, even though I actually like will say a lot of the work in that space in my opinion turns out is like more systems driven still because it turns out like KV caching and routing is actually like is still like very like systems like like these are very like systems heavy problems but yeah a little bit more like sort of GPU performance that kind of stuff. We're starting to build up a research team. We're very excited about, you know, moving into stuff around like, you know, post- training and and distillation and and better methods for for quantization and

</details>

**>>**: 是为你们的客户，还是供内部使用？

<details>
<summary>Original English</summary>

**>>**: for your customers or for internally

</details>

**>>**: 两者皆有。我觉得这有点像前线工程支持（FTEES/FDS）那样，我们最初会和客户一起做很多工作来优化他们的模型，但随着时间的推移，要摸索如何把这些转化为产品。我认为如果每次客户需要优化模型时我们都必须亲自去和他们协作，那从某种角度来说我们就算是失败了。从长远来看，这必须被转化为产品。因此，对于前线工程师和研究团队来说，最初必须做大量面向客户的工作，我们现在也是这样做的，但随着时间推移，我们也在构建大量的内部工具，并在未来形成大量完全自助式的内部产品。所以目前我们在后训练领域，以及在 GPU 性能领域都在开展很多工作。因此，有很多很酷的东西，很多很酷的东西。

<details>
<summary>Original English</summary>

**>>**: both. I I think it's like a little bit like with the FTEES like I I I think we initially will do a lot of stuff with our customers to optimize their models, but over time figure out how do we turn those into products. I think we'll sort of arguably fail in a certain way if every time a customer needs to optimize a model we have to go and work with them and you know longterm it has to be turned into products and and so with the FDS and with the research team initially you're going to have to do a lot of work with the customers and we are that but over time we're also building a lot of internal tooling and a lot of overtime internal products that are fully self-s serve uh so we're working on a lot of stuff right now in in the post- training space but also in in the GPU performance space. So, a lot of cool stuff. A lot of cool stuff.

</details>

### 产品策略与构建块

**>>**: 回到你刚才提到的产品策略方面。是的。你的想法是什么？比如在未来一到两年里我们需要什么？

<details>
<summary>Original English</summary>

**>>**: Back to the product strategy stuff that you were talking about. Um, yeah. Like what are your thoughts? Like what do we need over the next year, 2 years?

</details>

**>>**: 我觉得这极难预测，如果我说我确切知道我们需要构建什么，我觉得那我就是在痴人说梦。我认为到目前为止我们所看到的，以及我在更宏观层面所坚信的，就是我们需要更好的构建块。这是一个软件的新时代，我们正在解锁整套全新的应用类型，这在几年前是无法构建的。比如做所有的生成式 AI 东西，输出代码的大语言模型，而这些代码需要以隔离的方式运行。处理 GPU 和大语言模型需要非常多的全新原语。到目前为止我们构建了一些构建块，这解锁了全世界在过去几年里所看到的一系列应用，当然不仅是我们。但我认为在接下来的几年里，还会有更多酷炫的东西出现。所以我提到了一些方向，比如我非常看好模型训练，非常看好批处理任务（bass jobs），非常看好围绕智能体（agents）和低延迟等等诸如此类的事情。但归根结底，我们把自己定位为一家基础设施提供商，对吧？我们不想去构建非常狭窄的应用。我们试图构建非常通用型的构建块，将它们摆在客户面前，然后那些客户……

<details>
<summary>Original English</summary>

**>>**: I think it's incredibly hard to say and and if I said like I know exactly what we need to build like I think I would be like delusional. I think what what I've what we've seen so far, you know, and what I kind of believe in on a more general level is like we need better building blocks. like this is a new era of of software and we unlocking a whole new type of applications that could not be built a few years ago you know doing you know all the geni stuff code that you know LMS that output code that you know it needs to run like in an isolated way like there's so many like new primitives that are needed to to work with GPUs and work with LMS and you know we built some building blocks so far and and you know that's unlocked you know a bunch of applications that that the world you know has seen over the last few ers, not just us, of course, but I think over the next few years, like there's going to be so many more cool things. And so I I I mentioned some stuff like I'm very bullish on training. I'm very bullish on bass jobs. I'm very bullish on, you know, certain things around like agents and and low latency and and things like that. But but like in the end, we consider ourselves like an infrastructure shop, right? Like we're not trying to build, you know, very narrow things. Like we try to build like very general purpose building blocks and put them in front of customers and then those customers

</details>

**>>**: 会把这些构建块组合起来，构建出我们可能永远预料不到的不可思议的应用。

<details>
<summary>Original English</summary>

**>>**: will combine those building blocks and build some incredible applications that we could have never anticipated.

</details>

**>>**: 我想过一遍你发过的一些推文。这是最后一部分，我们可以，也许你想加倍……

<details>
<summary>Original English</summary>

**>>**: I want to go through some of your tweets. This will last part of it and we can just like maybe you want to double

</details>

<!-- chunk 12/13 -->

...点击任何东西。

<details>
<summary>Original English</summary>

click on anything.

</details>

### 沙箱的演进与瞬态化

**>>**: 现在有很多长期运行的持久性沙箱之类的事物。今天感觉像是直接搬迁（lift and shift）。我怀疑沙箱会从云端的开发机演变成更加瞬态（ephemeral）的东西。每个命令一个环境，中间进行快照，这样你就可以暂停、恢复、克隆。是的，我的意思是关于这个我们讨论过很多次了。

<details>
<summary>Original English</summary>

**>>**: A lot of long running persistent sandbox stuff right now. Uh today feels lift and shift. I suspect sandboxes will evolve from devox in the cloud to something more ephemeral. uh one environment for every command and snapshotting in between so you can pause resume clone. Yeah, I mean we talked about this a lot.

</details>

**>>**: 是的，我们聊过一些，对吧？就像我完全——我认为今天 Modal 上的沙箱中位数时长大概是 8 秒左右，想想这其实挺不可思议的，而且随着时间推移，我认为它可能会变得更短。我们也想支持长时间运行的沙箱。我认为围绕长运行沙箱有一些非常合理的用例。但我的构想是，你知道，这个世界也需要弄清楚如何进行大规模并行化，并减少启动和停止沙箱的开销。

<details>
<summary>Original English</summary>

**>>**: Yeah, we talked a bit about it, right? Like I I I'm fully I I think I think the median soundbox in modal today is like 8 seconds long or something like that like which is kind of incredible when you think about it and and over time I think it might get even shorter. We want to support longunning sandboxes too. Like I think there are some like very valid use cases around longunning sandboxes. But like my vision is like you know the world needs also we need to figure out this like how how can we just massively parallelize things and reducing the overhead of starting and stopping sandboxes.

</details>

### GPU 算力采购与弹性容量

**>>**: 我不知道如果我运营一家准备 IPO 的初创公司，正在与竞争对手进行资本支出军备竞赛，能稍微协调并把控一下军备竞赛的节奏该有多好。

<details>
<summary>Original English</summary>

**>>**: I don't know if I ran an IPO ready startup engaged in capex arms race with a competitor it would be nice to coordinate and pace the arms race a bit.

</details>

**>>**: 不予置评。[笑声]

GPU 稀缺的最大弊端不是很难拿到 GPU，而是几乎所有容量都是作为从未来 3 到 6 个月开始的为期三年的“长方形”进行出售的。对大多数用户来说，需求并不是那个样子的。我想关于这一点我们之前也稍微聊过。

<details>
<summary>Original English</summary>

**>>**: No comment. [laughter]

The biggest downside of GPU scarcity is not that it's hard to get GPUs, but that almost all capacity is sold as three years as a three-year rectangle starting 3 to 6 months in the future. That's not what demand looks like for most users. I think we talked about that a little bit as well.

</details>

**>>**: 是的。而且，你知道，也许可以再深入一点。我认为 Modal 一直非常擅长的一点就是完全按需的容量，对吧？比如如果有客户来找我们，需要 100 张 GPU，我们通常可以立即提供给他们。你甚至不需要去找销售人员沟通。而在现实生活中，很多工作负载并不像这些扁平的长方形工作负载。它们会在 24 小时的周期中上下波动，随着时间增长，或者在某些阶段出现突发高峰。对我来说，这对当今许多客户来说都是一个挑战。我认为这对整个行业来说确实是一个真正的问题，因为获取容量的主要方式就是购买这些长方形区块。这并不理想。我认为行业需要演进，从根本上说——虽然我带有很大的偏见——但我认为这就是为什么 Modal 可以在那种所谓的持续时间转换（duration transformation）中发挥巨大作用，提供更灵活的容量。我们之所以能做到这一点，是因为我们能够聚合成千上万个客户，汇总后的需求会变得非常平滑，所以这正是 Modal 的很大一部分价值主张。

<details>
<summary>Original English</summary>

**>>**: Yeah. And you know, maybe just go a little bit deeper. Like one thing I think model has always been very very good at is fully on demand capacity, right? Like if a customer comes to us and need 100 GPUs, like we can typically give them that like immediately. You don't even have to talk to salesperson. And a lot of workloads in in in real life like they don't look like these like flat, you know, rectangular workloads. Like they scale up and down throughout the 24 cycle. They maybe grow over time. They maybe have certain burst periods. And to me that is a challenge with a lot of customers today. Like the and I do think it's a legit problem for for the space is like the only the prime way to get capacity is to to buy these rectangular blocks. It's not great. I think the world needs to evolve and and that's fundamentally I mean I'm very biased but like that's why I think modal can play a very large role in in that sort of you know whatever you want to call it sort of duration transformation of offering more flexible capacity and we can do that because we can aggregate many many thousands of customers and the demand gets very smooth in aggregate so that's a lot of the value prop of modal is exactly that

</details>

**>>**: 你觉得这是一个差异化因素吗，比如——噢，真的吗，好的。

<details>
<summary>Original English</summary>

**>>**: would you say that's a differentiator like the oh really okay

</details>

**>>**: 是的，实际上是一个巨大的差异化因素。事实上，我认为 Modal 的——如果你想高度概括的话——你可以把 Modal 的价值主张拆解为两件事。其一是开发者体验，能够快速迭代、构建东西，而无需操心基础设施。另一件事就是容量方面。对于 Modal 以及我们长期的发展方向，我越想越觉得，我们正在聚合全球的算力资源，并且我们非常擅长进行极其精细的切分，因为我们围绕极其快速的上下扩缩容做了大量工作，包括围绕 GPU 快照所做的一切。我们正在研究一些让它变得快得多的方法，而且这种模式在超大规模下运行得非常好，因为你可以聚合大量的客户。

<details>
<summary>Original English</summary>

**>>**: yeah massive differentiator actually in fact like I think modal's like if you want to like very sort of reductive like you can break down modal's value prop into two things. One is the developer experience the ability to like iterate and like build things and not have to think about infrastructure. The other thing is the capacity stuff. The more and more I think about modal and like where we're going in in the long run is like we're building like we're aggregating the world's compute capacity and we're very good at slicing it out like very granularly cuz we built all this work around you know scaling up and down extremely fast you know all the stuff around GPU snapshotting. We're working on some some ways to make it much much faster and that model works at very large scale like really really well because you can aggregate lots of customers.

</details>

### 沙箱业务增长与推理提供商的定位

**>>**: 每个月我都在说我们的沙箱收入可能已经见顶了，但它每个月仍然保持 30% 的增长。

<details>
<summary>Original English</summary>

**>>**: Every month I keep saying our sandbox revenue might have plateaued but it keeps going up 30% every month.

</details>

**>>**: 这有点不可思议，每个月我都觉得，沙箱业务增长了很多，但显然差不多进入平稳期了，然后它又迎来进一步的增长。所以我不知道，很多 VC 会问：你们是怎么知道沙箱业务会变得这么大的？事实是我并不知道，[笑声] 我确实认为它会比 2023 年时更大，但沙箱今天占到了我们收入的三分之一，这太不可思议了。显然我们对此非常高兴。我们有一个非常庞大的团队在沙箱领域进行投入。我不想把这轻描淡写，显然在甚至早在 2023 年就看到了沙箱今天的发展雏形这一点上，我们确实值得很多肯定。但我认为，如果回到过去，我可能永远也不会去押注沙箱能带来这么大的收入，市场需求会如此巨大。

推理提供商之所以应该独立于模型构建者而存在，有一个有趣的结构性原因。最好的模型总是在不断更替。推理提供商可以很容易地在不同模型之间重新调配资源，因为整体需求是相当平稳的。

<details>
<summary>Original English</summary>

**>>**: It's kind of nuts like I don't you know like every month I'm like well you know sandboxes grew a lot but like clearly they kind of plateaued and then they keep growing even more. So so I I I don't know and a lot of VCs like they're like how did you know sandboxes was going to be big? like and and the truth is like I didn't like [laughter] like I I thought it was going to be bigger than it was in 2023 for sure, but like the fact that Sandboxes is a third of our revenue today, it's it's insane. And you know, we're obviously very happy about it. We we have like a very large team investing in sandboxes. You know, I don't want to like trivialize it like we obviously I do want to give ourselves like a lot of credit for for seeing sandboxes for what it is today a little bit back in even 2023. But I I I think you know if like I probably would have never you know taken a bet that revenue would be this large from sandboxes and the market demand would be so much.

There's an interesting structural reason why in inference providers should exist separately from model builders. The best model keep changing a lot. Inference providers keep can easily reallocate resources between models since overall demand is quite smooth.

</details>

**>>**: 我的意思是，如果你想想所有的中国实验室，以及未来希望有更多的美国实验室。每次有新的实验室发布最新、最先进的开源模型时，你都会看到对这些模型的需求发生巨大转变。所以我觉得面临的挑战是，如果所有这些实验室都各自独立持有算力，他们会发现当他们推出新模型时，需求会大幅上升，然后另一家实验室推出了更好的模型，需求就随之下降了——

<details>
<summary>Original English</summary>

**>>**: So I mean if you think about all the Chinese labs and you know in the future hopefully more US labs too. every time a new lab releases you know the latest and greatest open source models like you see big shifts in demand you know for for these models and and so I think a challenge with you know if all these labs independently like held capacity they would see when they launch a new model demand would go up a lot and then another lab launches a better model and then the demand goes down

</details>

**>>**: 你知道，当然他们在后台还在研发下一个版本。所以我觉得存在一个结构性原因，就像我说的，为什么你会看到需求转移到最新、最好的中国实验室。当然，这并不是说所有东西都会在一夜之间全部转移，因为很多模型、提示词之类的内容都具有某种黏性。但我确实认为有一种观点认为，Modal 很容易做到——比如今天我们为某个模型运行了几千张 GPU，明天我们需要把其中 50% 的资源转移到另一个模型上。没问题。这正是该系统被设计来应对的情况。甚至不需要有人来通知我们这么做，系统就会自动完成。

<details>
<summary>Original English</summary>

**>>**: you know but but of course like in the background they're working on the next version so like I think you know there's like a structural reason like I said like why you're going to you're seeing demand kind of shifting to like the latest and greatest Chinese lab. I mean, not like it's not like you know this is like everything just moves overnight cuz cuz a lot of models and prompts and stuff like like a lot of things like get sort of there's like a certain stickiness to it. But I I do think you know there's an argument that it's very easy for modal to like you know right today we're running you know x number of thousand GPUs for one model tomorrow we need to shift like you know 50% of that to another model. Sure. That's just like that's what the system was built to handle. No one even needs to tell us to do that. It just magically does that.

</details>

### 大模型是大宗商品吗与智能是否见顶

**>>**: 所以你认同大语言模型本质上是大宗商品（commodities）。

<details>
<summary>Original English</summary>

**>>**: So you agree that basically the LLMs are commodities.

</details>

**>>**: 如果你认同的话，那你认为大实验室的商业模式未来会在哪里？

<details>
<summary>Original English</summary>

**>>**: And if you agree, then where do you think the business for the big labs is going to be?

</details>

**>>**: 我不确定这是否一定成立，对吧？泰勒·斯威夫特（Taylor Swift）是大宗商品吗？她发布了一张热门专辑，举办巡回演唱会，赚了很多钱，然后有一年低谷期，她去录制新专辑。我不知道这算不算最好的类比，接着她又发布了一张新专辑。所以我不知道，她依然拥有极强的品牌影响力，具有巨大的号召力，并且能赚取高额的利润率。因此，只要这些实验室能够持续不断地推出新模型，并且只要他们在这些模型上拥有的利润率足以分摊和偿还训练这些模型的成本，我认为这依然可以是一门相当不错的生意。

<details>
<summary>Original English</summary>

**>>**: I'm not sure if that's necessarily true, right? Like is Taylor Swift a commodity? Like she releases a big album and goes on a tour and makes a lot of money and then you know then there's like a down year when she goes and like records. I don't know if this is the best analogy and then she releases a new album, you know. So I I I don't know like she still has like a lot of brand and there's a lot of you know power and like makes a lot of margin. So like as long as the the labs like repeatedly can launch new models and as long as the margin that they have on those models are such that they they can sort of pay off amvertise like the the cost of training those models it could still be like a decent business I think.

</details>

**>>**: 所以你并不认为智能正在见顶？

<details>
<summary>Original English</summary>

**>>**: So you don't think that the intelligence is like plateauing?

</details>

**>>**: 不，我不这么认为。我认为这还有待观察，对吧？如今的模型非常擅长处理那些可以通过强化学习高效训练的事情。我们最初在编写代码和写简单代码片段上看到了这一点。随着时间推移，它在编写生产级代码方面也变得非常厉害。它在数学方面变得非常厉害，在网络安全方面也变得非常出色。这些都是高度可验证的事情。我仍然认为还有待观察，你知道，模型在比如做饭或者在那些目标更模糊、反馈周期可能更长的事情上是否会表现得非常好。我认为人类——我的感觉是在这些领域，人类在很长一段时间内相对于模型都会表现得相当出色、很有竞争力。但可以肯定的是，AI 模型确实变得越来越好，我相信每个人都会认同这一点。

<details>
<summary>Original English</summary>

**>>**: No, I don't I don't think so. I mean I I think it remains to be seen, right? Like models are today are like very good at like doing things that can be trained very efficiently, you know, using reinforcement learning. So So we've seen that initially with, you know, coding and writing simple snippets. Over time, it's gotten really good at also writing production level code. It's gotten really good at math. It's gotten really good at cyber security. Like these are all like very quite verifiable things. I I still think it remains to be seen. you know, our models going to be really good at whatever cooking food or I I I don't know like things that have like more like diffused targets and maybe longer feedback loops or whatever. I think humans probably like my feeling is like we'll be quite good and quite competitive with with models for a long time in those domains. But you know certainly you know AI models they're they're getting very very good as as I'm sure everyone can agree with.

</details>

**>>**: 是的。所以很明显，模型正变得非常擅长——

<details>
<summary>Original English</summary>

**>>**: Yeah. So obviously like the models are getting really good at

</details>

<!-- chunk 13/13 -->

### 未来应用与结语

……编程。它们在编程方面已经非常出色了。你认为还有哪些目前可能没那么热门的应用，在未来几年里会变得极其庞大？我——

<details>
<summary>Original English</summary>

coding. They're already really good at coding. What other applications do you think maybe that aren't as big right now are going to become huge over the next few years? I

</details>

**>>**: 我……我不知道，但我认为任何具有某种可验证性的……

<details>
<summary>Original English</summary>

**>>**: I I don't know, but I think anything that has like kind of a verifiable

</details>

**>>**: 计算生物学，我想你之前提到了。

<details>
<summary>Original English</summary>

**>>**: the computational bio, I think you mentioned.

</details>

**>>**: 是的。是的。计算生物学。我……我认为那些并不完全算是可验证的，但有某些方式可以让你做类似模拟的事情，比如你可以用大语言模型来输出预测。然后你可以用类似计算……计算方法去模拟分子动力学，并获得某种反馈回路。我是说，我认为材料科学可能是另一个领域，在那里你也会有类似的那种回路，你可以在某种程度上，你知道的，合成制造某些材料并测量其特性，然后你就把智能体放到回路中去，你知道的，做事情。所以，你知道我有物理背景，我对这个非常兴奋。所以，药物、材料，还有什么呢，脑子一片空白了，但我敢肯定还有很多其他东西。

<details>
<summary>Original English</summary>

**>>**: Yeah. Yeah. Computational bio. I I think those are like not exactly verifiable, but there's like certain ways you can sort of run sim like you can use an LM to output predictions. Then you can do like computational like like methods to like simulate the molecular dynamics and get like kind of feedback loops. I mean like I think like material science is like maybe another area where like you have a little bit of that loop where you can sort of you know synthetically manufacture certain materials and measure the properties and you just kind of put an agent in the loop and like you know do things. So you know I have a physics background I'm pretty excited about that. So drugs materials what else drawing a blank but I'm sure there's many other things.

</details>

**>>**: 太棒了。我是说，我想问的问题都在这里了。还有什么你想聊聊而我还没有……

<details>
<summary>Original English</summary>

**>>**: Cool. I mean those are all the questions that I had. Is there anything you wanted to talk about that I haven't

</details>

**>>**: 我觉得很好了。这非常棒。这很有意思。

<details>
<summary>Original English</summary>

**>>**: I'm good. This is great. This is a lot of fun.

</details>

**>>**: 太棒了。谢谢你。

<details>
<summary>Original English</summary>

**>>**: Awesome. Thank you.

</details>

**>>**: [音乐]

[音乐]

<details>
<summary>Original English</summary>

**>>**: [music]

[music]

</details>