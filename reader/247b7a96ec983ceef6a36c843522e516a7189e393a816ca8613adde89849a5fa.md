---
author: How I AI
date: '2026-03-09'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=2RD3FP5iWJY
speaker: How I AI
tags:
  - midjourney
  - brand-identity
  - style-reference
  - ai-creative-direction
  - visual-language
title: 玩转 Midjourney：无需复杂提示词，打造高一致性的品牌视觉系统
summary: 本期访谈邀请了 AI 创意总监 Jamie Gannon，深入探讨如何利用 Midjourney 的“视觉语言”而非复杂提示词来构建高品质品牌资产。Jamie 分享了从 Pinterest 情绪板到风格参考（SREF），再到利用个人化代码和 Nanobanana 进行后期精修的完整高保真工作流。她强调了“懒人提示法”的核心在于利用参考图引导模型，而非编写冗长的代码，从而实现专业且具有灵魂的创意产出。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Jamie Gannon
companies_orgs:
  - Midjourney
  - Vanta
  - Lovable
  - Pinterest
  - Cosmos
products_models:
  - Midjourney v6
  - Nanobanana
  - MacBook Pro
media_books: []
status: evergreen
---
### 品牌视觉的高一致性秘诀

**Jamie**: 这一切都归结为一个非常严密且精细的过程。值得庆幸的是，我在 **Midjourney** 和 **Nanobanana** 等工具上投入了无数时间，才摸索出这套流程，让你不必整天为写提示词而抓狂。

<details>
<summary>Original English</summary>

**Jamie**: It all comes down to having a very tight and manicured process, which thankfully I have spent my 10 gajillion hours in Midjourney and Nanobanana and everything to figure out exactly what that is so you're not pulling your hair out prompting all day.

</details>

**Claire**: 我最欣赏情绪板（Mood Board）的一点是，它是一种解释你意图的**视觉语言**。图片胜过千言万语，对于大语言模型来说，一张图真的抵得上千言万语。提到像 **Vogue**、高级时装甚至特定艺术家的名字，是告诉模型大量信息的绝佳方式，而无需实际描述细节。

<details>
<summary>Original English</summary>

**Claire**: One of the things I like about the mood board is it's a visual language to explain to Midjourney what you're trying to do. The picture is worth a thousand words. Like literally a picture to an LLM is worth a thousand words. Mentioning like Vogue or high fashion or even like a different artist name is a great way to tell the model a ton of stuff without actually having to tell a ton of stuff.

</details>

**Jamie**: 过去，品牌创意总监或机构会给你这些照片，然后说：“好了，想要更多照片时再联系我们。”我喜欢的是，现在你可以告诉客户：“看，我为你做了这些前置工作，定义了空间，提供了代码和参考图，现在你可以自己去做了。”这是一种完全不同的服务模式，能在客户和创意总监之间建立非常积极的协作关系。

<details>
<summary>Original English</summary>

**Jamie**: In the past, brand and creative directors or agencies will give you these photos and be like, cool, call us and reup when you want more photos. What I love is that you're like, look, you're going to value me for all this upfront work that I'm going to do to find the space, give you these codes, really give you reference images, and then now you can go do this for yourself. It's just like a very different model of providing service and I think it creates a really positive collaboration between the client and the creative director.

</details>

### AI 创意工作流初探

**Claire**: 欢迎来到 *How I AI*。我是 Claire，AI 狂热者，致力于帮助大家利用这些新工具更好地进行创作。今天我们要和 **Jamie Gannon** 一起聊聊审美，她是一位 **AI 创意总监**，将向我们展示如何使用 **Midjourney**、**Nanobanana** 和 **Flora** 创建一致且独特的品牌资产。

<details>
<summary>Original English</summary>

**Claire**: Welcome to How I AI. I'm Clarvo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today we have an aesthetic episode with Jamie Ganon who is an AI creative director and is going to show us how to create consistent, beautiful, and unique brand assets using Midjourney, Nanobanana, Flora, and more.

</details>

**Jamie**: 很多人在使用 AI 时会感到挫败，如果你只是直接在 Midjourney 里输入文字，结果可能看起来还行，但如果你是为客户工作，或者追求品牌风格的高度统一，你就必须诚实面对：这真的符合那种氛围吗？通常是不符合的。所以我们需要一种更好的方法。

<details>
<summary>Original English</summary>

**Jamie**: I think where a lot of people that are starting to use AI get kind of tripped up is like if you've ever just like raw dogged generated something in like Midjourney... this might be like great to you and like some of these images stand alone are really cool to me but if we're working for like a client or we're trying to be consistent with the brand style we need to be like really really honest with ourselves on like does this actually look like that vibe and truthfully it does not. So, I think that there's going to be a better approach to get things going.

</details>

### 第一步：构建情绪板与 SREF

**Jamie**: 第一步，我总是在 **Pinterest** 或 **Cosmos** 中开始。我会创建一个情绪板来确定大方向。对于这次演示，我想要一种粉嫩可爱但又不失酷感、带有互联网审美风格的视觉效果。我喜欢在 AI 创作中做“并置”（Juxtaposition），比如一个打着耳洞的橙子，或者电脑前的一只荧光色水果狗。

<details>
<summary>Original English</summary>

**Jamie**: So, first thing that I always do is I'm going to start in either Pinterest or Cosmos. And I'm going to create a mood board that is the general vibe of what I want. So, for this exercise, I wanted to have like a very pink and cute but still kind of like not super girly, very internet kind of coded aesthetic. I like especially with AI doing like juxiposition. I think that's really fun. So, we have like an orange with piercing. We have like a fluorescent fruit dog on a computer.

</details>

**Jamie**: 在 Midjourney 中使用这些图片有两种方式：你可以直接复制粘贴图片，或者将它们作为 **SREF（风格参考）**。SREF 会告诉 Midjourney 提取整体风格、配色、镜头处理和氛围并应用。在“创作阶段”，我并不追求完美，我只是想快速生成，看看 AI 提取到了什么信息。

<details>
<summary>Original English</summary>

**Jamie**: I will either go in with a mood board in Midjourney. And you can basically just copy and paste your images in or you can start by adding them as SRFs as you can see here. So SREFs basically are style references and they kind of do exactly what they sound like. It just tells Midjourney to take the overall style and coloring and camera treatment and vibe if you will and it like tells it to apply that.

</details>

### 调试与直觉：移除干扰元素

**Jamie**: 比如在测试中，结果显得太绿了。这就是直觉发挥作用的地方。我在 Midjourney 浸淫了三年，我意识到如果我移除那张带有绿色眼影的参考图，问题就能解决。移除后，色调变得更中性，人像也更像我想要的方向了。

<details>
<summary>Original English</summary>

**Jamie**: And you can tell we're definitely getting better contrast... but it's pulling really really green for me. Um, so what I ended up doing is I just removed that green eye SREF. Um, this is something that comes with intuition. You know, I've been using Midjourney for like 3 years, so I kind of can like understand like where... the LLM is pulling certain things. And I knew that if I removed this green, it would solve a lot of my problems.

</details>

**Claire**: 我注意到你并不是在使用那些复杂的 SREF 代码，而是直接把图片拖进 UI。这种方式有时比单纯依赖通用的情绪板效果更好。

<details>
<summary>Original English</summary>

**Claire**: So instead of the SRF codes that a lot of people and we've talked about in the past, you're using literally the UI to just drag in images as style references and that for you sometimes gets you better results than just using the general mood board process.

</details>

### 进阶：个人化代码 (Personalization Codes)

**Jamie**: 下一步是“迭代”，我们会带入**个人化代码**（Personalization codes）。这在底层是如何运作的仍然有点神秘，但基本上 Midjourney 会让你在一系列图片中进行二选一或跳过，以此告诉它你的审美偏好。你可以拥有多个配置文件。

<details>
<summary>Original English</summary>

**Jamie**: And that's where we're going to start like getting a little bit more specific with our process, maybe slightly more technical... I'm going to start to bring in some personalization codes and other mood boards. Now personalization codes, again, it's kind of like a little bit of a mystery how it works exactly under the hood, but when you're creating a personalization code, Mag is going to put you through this like endless flop matrix of images... basically it you're just telling it what you like.

</details>

**Jamie**: 对于这组作品，我使用了一个名为“2025 年底审美”的代码，追求的是更现代、更有质感的效果，你可以看到皮肤的质感变好了。我建议在投票时要中庸，只有遇到真正喜欢的风格才选择，否则会出现风格“渗漏”（Style bleeding）。

<details>
<summary>Original English</summary>

**Jamie**: So what ended up helping me get these results is um my personalization code that I call late 2025 aesthetic. Um... I tend to skip like a medium amount and only pick things that I would like if I generated it. Um but I do find there's kind of like style bleeding.

</details>

### 懒人提示法：利用行业术语

**Jamie**: 我现在的提示词不再只是“女人”或“宇航员”。我会加入一些审美思考，比如 **"Dazed editorial photo shoot"**。**Dazed** 是一本非常前卫的杂志，这种术语能立即告诉模型高对比度、前卫的质感。这和“图片胜过千言万语”是一个道理，不用写长篇大论，直接引用 **Vogue** 或特定相机型号。

<details>
<summary>Original English</summary>

**Jamie**: These prompts are no longer just like woman or astronaut. They are actually starting to give some like aesthetic thought. So, one prompt... it's Dazed editorial photo shoot. So, doing stuff like that, like mentioning like Vogue or high fashion or even like a different artist name is again a great way... to tell the model a ton of stuff without actually having to tell a ton of stuff.

</details>

**Jamie**: 我还会使用 **Sony RX100** 这样的相机作为快捷方式。我并不太懂光圈之类的技术参数，但我知道这款相机会带来 90 年代数码相机的质感。再比如，描述场景时使用 **"Luxury"** 一个词，AI 就会自动联想到高层建筑、昂贵的金属材质和落地窗，这比描述“位于高层公寓的四楼”要高效得多。

<details>
<summary>Original English</summary>

**Jamie**: I barely know what aperture means. Um, so sometimes when I just want to try changing up the vibe or make things more realistic... I'll just paste in like a camera, um, that mimics that. Um, so the Sony RX100... one word luxury just gives us everything that we need to know about the scene which is very fun.

</details>

### 后期处理：Nanobanana 作为 AI Photoshop

**Jamie**: Midjourney 经常会生成奇怪的手，或者在复古审美中给你一个奇怪的旧电脑。这时我会把图片带入 **Nanobanana**。你可以把它看作是可以对话的 **Photoshop**。

<details>
<summary>Original English</summary>

**Jamie**: For some of the images in Mid Journey, I'm sure you have all seen the terrible hands... So something I do a lot of the time... I'll take my Midjourney images and I'll take them into uh, Flora uh, or Hicksfield sometimes and I'll just use Nano Banana as Photoshop. Nano Banana uh, literally is just Photoshop.

</details>

**Jamie**: 我会对它说：“把她正在打字的电脑换成 **2026 款午夜黑 MacBook Pro**。不要改变其他任何东西，保持电脑的位置和大小完全一致。”Nanobanana 具有推理能力，它知道这些现实世界中的物体长什么样。处理后的图片分辨率也会大大提升，可以直接用于社交媒体。

<details>
<summary>Original English</summary>

**Jamie**: I just said replace the computer she's typing on on a 2026 Midnight Black MacBook Pro... I also usually mention like don't change anything else. I say keep the position and the size of the computer exactly the same... it's going to be like 4,000 x 4,000 versus like 800 by 800.

</details>

### AI 创意总监的自我练习

**Claire**: 很多人并没有有意识地培养自己的视觉品味和语言。除了 Pinterest，你还有哪些获取灵感的渠道？

<details>
<summary>Original English</summary>

**Claire**: I feel like people aren't cultivating their visual taste and language enough. So, what are some of your, you know, other than Pinterest, what are your some of your sources where you're um continually improving your language and your aesthetic taste?

</details>

**Jamie**: 我建议每个人都在 **Twitter (X)** 上建立一个列表。现在依然有很多类似 Tumblr 风格的账号在发布极具美感的图片。我会关注很多时尚账号。此外，我也在 **Maven** 上推出了我的 AI 课程《AI 创意总监》，教大家如何通过练习实现专业级别的产出。

<details>
<summary>Original English</summary>

**Jamie**: One thing that I recommend to everyone is to start a list on Twitter. There's tons of like basically Tumblr accounts still to this day that post like really aesthetic images... Also, I have an AI course coming out. It's called, um, the AI creative director. It's on Maven.

</details>

**Jamie**: 最后，如果 AI 没能给出你想要的东西，**先停下来休息一下**。不要陷入其中反复纠缠。当你走开再回来时，你会更能看清问题所在：是风格太杂乱了？还是某个颜色干扰了全局？保持**绝对的诚实**，理解 AI 的运作方式，而不是强迫它按你的想法走。

<details>
<summary>Original English</summary>

**Jamie**: Firstly, take a break always. like you're never gonna be able to like see properly if you're kind of like in it... walking away and then... be like okay what is actually the problem? Like for some of these generations I'm like it's just too busy... brutal honesty on like what's going on and trying to like not... make AI work the way you want it to work and actually understanding how it works in general.

</details>