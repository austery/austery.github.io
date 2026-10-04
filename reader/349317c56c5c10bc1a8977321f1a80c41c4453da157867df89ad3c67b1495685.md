---
author: AI Engineer
date: '2026-07-21'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=Cz4v1WHVyZc
speaker: AI Engineer
tags:
  - video-generation
  - html-to-video
  - agentic-workflow
  - declarative-motion
title: HTML即画布：用网页技术栈重构AI智能体视频生成
summary: HeyGen Hyperframes 技术负责人 James Russo 分享了为何 HTML/CSS/JS 是 AI 智能体生成视频的最佳媒介。由于大语言模型天然熟悉网页代码，Hyperframes 采用极简的 HTML 封装，并通过冻结时钟、逐帧渲染等机制解决浏览器异步加载问题，实现了确定性的高画质视频输出。项目已开源并支持人机协同微调，致力于降低产品发布视频的制作门槛。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - HeyGen
products_models:
  - Hyperframes
media_books: []
status: evergreen
---
### 解构视频画幅：从AI分身到全要素合成的演进

**HeyGen** 联合创始人兼 **Hyperframes** 技术负责人 **James Russo** 在演讲中指出，虽然 AI 编程智能体极大降低了软件开发的门槛，使任何人都能轻松构建出自己脑海中的产品，但如何将产品或功能成功推向市场——制作一段高质量的发布视频（launch video）——依然是开发者面临的一大痛点。**HeyGen** 最初的使命是通过视频解决沟通问题，并由此打造了行业领先的 **AI 虚拟人**（AI Avatar: 模拟真人外貌与声音进行播报的 AI 系统）技术。然而，单一的虚拟人镜头仅仅构成了视频的 **主镜头**（A-roll: 视频中的主线叙事或人物镜头），一段引人入胜的优秀视频还需要丰富的 **辅助镜头**（B-roll: 插入的演示画面、静态图片等多媒体素材）、动感的动画特效、清晰的字幕以及背景音乐。

段落之间必须包含逻辑衔接句。为了让智能体有能力自主生成并合成所有这些视觉与听觉图层，业界急需一种能够整合上述要素的统一画布。传统的视频剪辑和渲染工具对智能体并不友好，而在尝试了多种技术路线后，**HeyGen** 将筹码压在了 **HTML**（HyperText Markup Language: 网页标记语言）上。

<details>
<summary>Original English Source</summary>

Since we're talking about generative media, I thought starting with a video might be good. That video was made completely by an agent in a single shot, all utilizing HTML. My name is James Russo. I am the co-creator and tech lead of hyperframes at HeyGen. Today, we're going to be talking about why we think HTML is all your agents need to create great videos. Show of hands here who finds creating that launch post or that launch video harder than actually building now with coding agents. All right. Some hands up there. Coding agents have democratized building, made it incredibly easy for anyone to create anything that comes to their minds. However, we think that launching your product or your feature, getting it out into the world, is still quite hard. And we at HeyGen have been trying to close that gap. If you're not familiar with HeyGen, our mission is to solve communication through video. We started by creating the best AI avatar on the market. You can think of this as the A-roll, the footage you see here on the left side of the screen. It's the narrator, the character, the main subject of the video. However, it's kind of plain, and great videos have a lot more pieces to them. They have B-roll, which is the images and the other pieces of media and assets. They have animations, they have captions, they have music. All of this is needed to create a great video. And for us, it's important that we nail every layer, not just the avatar, to solve communication through video and give agents the right canvas to create great videos. So, how do you give agents the ability to generate all these layers and build up this composition needed to create great video? Our bet is on HTML.

</details>

### 母语级表达：大模型在网页技术栈的天然优势

在确立了以网页代码为画布的方向后，具体的研发实践证明，**HTML**、**CSS** 和 **JavaScript** 是大语言模型（LLM）的 **天然母语**。这是因为互联网上几乎所有的网页数据最终都是由这三者构成的，LLM 在预训练阶段已经吞噬了海量的网页代码。如果强制模型去学习一种全新的 **领域特定语言**（Domain-Specific Language: 用于特定应用领域的专用计算机语言）或自定义的 JSON 结构，就如同要求莎士比亚用中文或日文写诗，即使提供大量示例，也难以获得最顶尖的创作输出。

在这一背景下，研发团队评估了现有视频制作框架在“输出质量”与“智能体友好度”两个维度上的表现：
* **After Effects** 与 **Premiere Pro**：创意设计的行业黄金标准，能输出极高质量的作品，但对自主智能体极其不友好，目前只能作为人类辅助工具。
* **Lottie** 与 **Rive**：基于 JSON 或自定义 XML 格式的动画描述语言，虽然质量不错，但其底层代码不可控且不易编辑，缺乏智能体所需的控制力层。
* **Remotion**：基于 React 编写视频的优秀框架，但由于智能体需要专门学习该框架的语法和规则，从而在一定程度上限制了模型的创造力。

随着 **Gemini 1.5 Flash** 等新一代模型的推出，智能体在代码编写上实现了步进式提升。当向它们展示期望的视频效果时，模型会自然而然地倾向于直接输出 HTML、CSS 和 JavaScript 代码。因此，最合理的策略是顺应模型本能，让它们用自己的“母语”来进行视频创作。

<details>
<summary>Original English Source</summary>

HTML, CSS, and JavaScript are the native languages of LLMs. Most of their training data, every webpage that gets scraped at the end of day is essentially just HTML, CSS, and JavaScript under the hood. When you try to teach a model a new DSL or even your own custom JSON structure, it's forcing it to speak another language. We like to think of this as trying to ask Shakespeare to write a poem in Japanese or Chinese. Even if you give them a bunch of examples and teach them a bunch of things, you will not get the best output from them because it's not their native tongue. So, why not let the LLMs and agents talk in their native tongue when creating videos? We're not the only ones saying this. Over the last few months, Tarik, Andrej Karpathy have been talking a lot about how HTML is a new markdown. It's a great output for LLMs to give you visual representation. For what's it's worth, I submitted this talk before both of these tweets came out. I can show you proof later if you're curious, but we all kind of came to the same conclusion here, which is that let LLMs talk in their native language and you can get better output from them. It wasn't necessarily an easy thing. We've been working on this for over a year now and tried a bunch of things along the way. There's a bunch of different frameworks and tools to help create great videos. And we like to think about them on this axis of quality of results and agent-friendly. For us, After Effects, Premiere Pro, these are kind of like the gold standards of creatives. They create great output, but they're not very agent-friendly. And even with the more recent connectors into it, it's more of a co-pilot or something that can help you facilitate things you already know how to do. It doesn't give it creative output. We tried things like Lottie and Rive, which are coding languages in JSON or custom XML formats. And they can get you pretty good output, but agent-friendly isn't necessarily true for those because they're not their native tongue and they aren't as editable or controllable, which is a big thing for us is that controllability layer. We played around with Remotion quite a bit and honestly thought it was a great example of what LLMs and agents could do with coding. However, we noticed that we had to teach them the framework. We had to teach them the language and give them a bunch of examples on how to write code properly, which ultimately took away a lot of the creativity of it. Then we have HTML, which around November of last year when Gemini 3 and the latest models came out, we saw a step function improvement in what LLMs could do. When we just gave them examples of what the output we wanted was, they naturally gravitated toward HTML, CSS, and JavaScript and gave us great output. And we decided, let's not fight the model, but find a way where we can let them talk in their native tongue.

</details>

### 时钟冻结与帧级渲染：Hyperframes 的确定性机制

为了解决智能体视频生成的代码架构问题，团队开发了开源的 **Hyperframes** 框架。在开发初期，他们选择以轻量级模型 **Gemini 1.5 Flash** 作为主要的设计伙伴。实验证明，最薄的封装层效果最好——即纯 HTML，加上少量的 **数据属性**（data attributes）作为时间线与系统同步的元数据。

在打通了代码编写后，下一个核心挑战是如何将动态的网页转化为确定性的 **MP4 视频**。因为现代浏览器在设计上是 **异步加载**（Asynchronous Loading: 资源在后台非阻塞加载以提升体验的机制）的，这在视频渲染中会导致字体、图像在播放过程中突然改变或缺失。为了确保视频的确定性，**Hyperframes** 引入了以下底层渲染机制：
* **时钟冻结**：冻结浏览器内部的时间，使其不再随系统真实时间流逝。
* **确定性逐帧寻轨**：精确跳转到每一个视频帧的时刻。
* **屏幕截图合成**：在每一个寻轨时刻，等待网页上的所有资源 100% 加载就绪后，截取当前浏览器的像素，进而连续编码合成最终视频。

这种机制带来了极大的技术红利，任何能在浏览器中正常渲染的内容，均可无缝转化为视频画面。这使得 **Three.js**、动态图表、**SVG** 矢量图、**着色器**（Shaders: 控制 3D 物体表面材质与光影的 GPU 程序）、WebGL、WebGPU 乃至 Lottie 动画，都能在视频中完美重现。

<details>
<summary>Original English Source</summary>

So, how we did this was starting with a very small model, Gemini 3 Flash, as our design partner. We knew that if the smaller models could author workable code in a framework, then the larger models and these coding agents could 100% do it as well. We tried with a bunch of different wrappers around HTML, CSS, and JavaScript, adding in a lot of context, and making our system prompts bigger, adding in skills. But to our surprise, the thinnest wrapper ultimately won, which is essentially just HTML at the end of the day with a few data attributes as metadata to let the agent know, and to let us know about timing and things like that. Our thinking was very simple. If this smaller model could get it, as the models got better, it would continue to improve. They would naturally understand it more as well as training data came into the picture. And this is when we knew the format of what we were building was right. Here's a little bit more detailed example of what a video looks like in hyperframe. So, here is on the left just HTML with a few attributes, and on the right, the web page that it renders. The preview and the render are all done in the browser. The same pixels that the browser sees is ultimately what your video is going to see. And anything any web page that your LLM or agent knows how to write, it can now write into a video. This gave us hyperframes, our open-source framework that turns your agent's HTML into video. So, now that we had the HTML and the language part of it, the next hard part was how do we actually turn this into a deterministic MP4 video that anyone can post or utilize. And this was a lot harder because browsers are async on purpose. They have a different set of requirements and concerns to video rendering. They need to work across a bunch of different networks and a bunch of different constraints. But, that's not true for video. So, on the left you can kind of see here what a browser render might do. It's okay to loading things asynchronously like fonts. So, as the page loads in, the font and style of the text might change. Images and videos and other assets can load in asynchronously as well. So you might not see them initially on the page, but they'll come in at some point. Whereas for video, we need everything on the page 100% of the time so that we can show you exactly what you expect in the video. How we do this in hyperframes is essentially freezing the clock and seeking frame by frame. For those who aren't super familiar with video, basically a video is a series of frames or images strung together to create motion across an entire video. So we took this insight of ours and basically applied it to our rendering of HTML as well. We freeze the clock in the browser and then we seek deterministically to every single moment in time or every single frame, wait for everything to load on the page, ensure that it's loaded and ready to go, and then we take a screenshot and move on to the next frame, and do that over and over again until we get all of the necessary frames to encode that into a video. So the same input that is previewed in the browser is also rendered into the video. Hence the name hyperframes. The power of this is that anything you can render in a browser essentially can now be in your video. Things like 3.js, charts, SVGs, shaders, WebGL, WebGPU, Lottie, all of these are renderable in the browser, and therefore all of them are renderable in hyperframes. This is a big part of how we create a lot of our videos is finding inspiration on the internet, taking these as examples, tweaking them to our needs, and then putting them into our videos.

</details>

### 人机协同与创意微调：Hyperframes 的规模化实践

虽然智能体在编写基础 HTML 代码方面表现优异，但要实现精美、有创意的视频，依然需要人类的 **工匠精神**（craftsmanship）与审美把关。这与 AI 编程开发类似：通过单次生成（single-shot）可以得到一个可工作的粗糙版本，但顶尖的品质需要迭代和精心雕琢。为了支撑专业级创作，**Hyperframes** 不仅开源了底层渲染框架，还搭配了一款强大的 **编辑器**（Studio Editor: 用于对智能体生成视频进行精细化调整的可视化编辑界面），支持高级动效设计师所需的 **关键帧**（Keyframes: 标记动画关键状态的帧，用以计算中间过渡效果）管理，支持手动拖拽、多轨编辑，保证人类始终处于主导地位（human-in-the-loop）。

目前，**Hyperframes** 已在产业中得到规模化应用验证：
* 在过去 90 天内，开源社区用户已累计渲染了超过 **130 万支视频**。
* 超过 **26.7 万名创作者** 进行了使用尝试，每日有约 **1.5 万支视频** 诞生。
* 项目在 GitHub 上已收获超过 **3.2 万颗星**。

作为一款完全免费的开源工具，**Hyperframes** 能无缝集成于 **Cursor** 等任何能编写 HTML/CSS/JS 的 AI 编程智能体中。此外，为了进一步提升生成质量，**HeyGen** 团队正致力于建立 **代码转视频基准测试**（Code-to-video Benchmark: 评估 AI 智能体根据代码生成视频质量的行业测试标准），与各大主流模型实验室和开发者携手合作，共同提升视频智能体生成的质量下限。

<details>
<summary>Original English Source</summary>

The next part outside of the actual framework and rendering is how do you get great or good output out of the agents. And a big part of this is the skills that we couple with our framework. Our skill is focused on taste and video aspects because the LLMs and agents already know how to write HTML and CSS and JavaScript, we don't have to teach them the language, we just teach them how to create good videos. This is a big difference between other frameworks where if you look at certain skills, it's really just like how do you write something in that framework? This allows us to focus on the important parts of what makes a great video and a big part of this is constantly evaling and using agents to improve them. This allows us to raise the floor of videos and ensure that the base output of a single shot prompt gets you pretty good results. Here's an example I'm going to show of a single shot utilizing our website to video skill. All you have to do is give it a website. We tell it how to get to that website, retrieve all the assets and information it needs to create that design and theming and branding using DesignMD or FrameMD in our case. And then from there we just teach the LLM basic motion examples and things like that of great videos that you can then go ahead and get good output like this. However, great output takes craft. Similar to AI coding, you can get decent output by just giving a single prompt and having something that works for your needs, but getting great output from agents requires craft, taste, the same principles of any software engineer before AI coding as well. Breaking the problem up into individual pieces and working iteratively. The same is true for getting great output for HyperFrames videos. We want to make sure our power users have full control over this and the same way we created videos before HyperFrames is how we create them with HyperFrames. We think about the narrative and the vision and the mission of this video. We storyboard it frame by frame and think about what each frame needs to do. We then move that into adding motion frame by frame utilizing HTML, CSS, and JavaScript, merging it into one cohesive video, and then utilizing our studio that we released with Hyperframes for that last mile editing. Ensuring that humans are always in the loop and have access to do anything that they would do in their normal video editor within the open-source framework's editor so that you can manually drag, tweak, etc. And that gets you output that looks like this. We actually just released this today, keyframes in Hyperframes, which is a big aspect of what makes great videos for motion designers, and it allows you to basically coordinate all of this different motion frame by frame or keyframe by keyframe in our studio and make sure that you can do anything that a professional motion designer might be able to do in After Effects. So, it's not just a demo. We've been we released Hyperframes a couple months ago. It's been running at scale in our opinion. Over 1.3 million videos have been rendered by open-source users of Hyperframes in the last 90 days. 267,000 creators have tried it. We have about 15,000 videos every single day being rendered utilizing the open-source framework and 32,000 GitHub stars. But this is only just the start for us. As I mentioned already, it's open-source, free forever. Anyone can go ahead and use Hyperframes right now. It works with any coding agent that you have, Cloud Code, Codex, Cursor, any number of other ones up here, any ones I'm not aware of even. If your agent knows how to write HTML, CSS, and JavaScript, it knows how to create a Hyperframes video. Now, with this, the same agent that is helping you create your product can also help you make your launch video. The one honest thing that we're going to say here is that the models still aren't good at creative work. We spend a lot of time evaling and trying to improve this in our skills and push it even further. But we think there's something at a higher level that needs to change here, which is why we started to work on a code to video benchmark where we are trying to work with the LLM labs, any creators who are working on video agents to ensure that we can raise the floor of videos for everyone. If anyone is interested in this space or working on this, we'd be happy to be collaborators, talk more about this. Feel free to find me or any member wearing a Hyperframes t-shirt in the crowd afterwards. Love to chat to you guys more. And one more thing, some of you may have seen the AI engineer Warfare showcase video. We collaborated heavily with the team to create this with them utilizing Hyperframes as a little surprise of what it can do. Here's a great example of the motion graphics and designing that you can do with HTML, CSS, and JavaScript. So yeah, agents are made building incredibly easy. Launching is still quite hard. We think HTML is all your agents need in order to make great videos and launch your product into the world. Here is a link to Hyperframes, the project, the open source repo. Feel free to check it out, star it, download the skills. You can reach me on X at Reems_Juso, and thank you for attending. I'll be outside if anyone wants to chat.

</details>