---
author: AI Engineer
date: '2026-05-01'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=sPUjIBH5Cwg
speaker: AI Engineer
tags:
  - ai-agents
  - interactive-canvas
  - collaborative-ai
  - user-interface-design
  - developer-tools
title: 'AI Agents on the Canvas: Exploring Collaborative Interfaces with tldraw'
summary: This talk by Steve Ruiz from tldraw explores the evolution of AI in creative tools, from single-shot generation (Make Real) to collaborative agents on interactive canvases. He demonstrates tldraw's advancements, including multi-agent systems ('Fairies') and the integration of AI into desktop applications for enhanced interactivity and safety. The discussion highlights the challenges and future possibilities of AI as a collaborator in creative and development workflows.
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Teal Draw
  - Replet
  - Luba AI
  - Stitch
  - OpenAI
products_models:
  - Make Real
  - Agent Canvas
  - OpenClaw
media_books: []
status: evergreen
---
### tldraw介绍与AI的早期尝试

**史蒂夫·鲁伊斯**: 大家好。抱歉，我们今天开始得有点晚。我是**Steve Ruiz**，来自**Teal Draw**。有人知道Teal Draw吗？

<details>
<summary>Original English</summary>

**Steve Ruiz**: Hello. Hey, I'm gonna I'm gonna kick off. Uh, sorry, we're starting a little bit late here. >> I am Steve Ruiz from Teal Draw. Does anyone know Teal Draw?

</details>

**史蒂夫·鲁伊斯**: 哇，有粉丝！如果你们不认识Teal Draw，它其实是两样东西。Teal Draw 是一个在线白板，你们可以去用，它是免费的，而且非常好用。我这次演讲的幻灯片就是用它做的。Teal Draw 也是一个初创公司，我们总部在伦敦。Teal Draw 同时也是一个 SDK，你可以用它来构建其他产品。比如，如果你用过 **Replet** 的新 Agent Canvas，那是用我们的 Canvas 构建的。如果你用过 **Luba AI** 的新 Canvas，那也是用我们的 Canvas 构建的。如果你用过 **Stitch** 的新 Canvas，那不是用我们的 Canvas 构建的。

<details>
<summary>Original English</summary>

**Steve Ruiz**: >> Yes. >> Hey. All right. fans fans in the room. Uh if you don't know Teal Draw, Teal Draw is kind of kind of a couple of things. Tildraw is a online whiteboard. You can go to it. It's free. It's really nice. Um I'm going to be using it for my slides. Uh Telra is also a startup. We're based here in London. And Telra is also an SDK, something that you can use to build other products. So, if you've used uh Replet's new um uh agent canvas, then that's built with our canvas. If you've used uh um Luba AI's new canvas, that's built with our canvas. If you've used Stitch's new canvas, that's not built with our canvas.

</details>

**史蒂夫·鲁伊斯**: 但如果你进入这个“注解模式”，这实际上就是我们的 Canvas。所以我们就在里面。它是一个 Angular 应用。总之，Teal Draw 是一家生产白板和白板 SDK 的公司。做 SDK 的初衷之一是你可以用它来构建很酷的东西，这意味着我的工作就是用 SDK 构建酷东西来证明它。最近，我们做的很多东西都涉及到了 AI，对吧？ hackable canvas runtime，用 React 构建的。事实上，Canvas 本身也只是 React 组件。所以，组件、组件、组件。这意味着你可以做一些很酷的事情。好了，第一个演示，我可能要听天由命了，因为要依赖演示之神、网络和其他一切。请多包涵。大家还记得这个 App 叫 Make Real 吗？也许还记得 2023 年视觉模型刚出来时，关于 Make Real 的这条推特？

<details>
<summary>Original English</summary>

**Steve Ruiz**: But if you go into this like kind of uh um annotate mode, this actually is our canvas. So we're in there somewhere. It's a Angular app, you know. Uh so anyway, um Deal Draw is again company makes a whiteboard makes a whiteboard SDK. Part of the idea with the SDK is that you can build cool things with uh with the SDK, which means it's part of my job to build cool things with the SDK to prove it. Um and a lot of those things recently have have involved AI, right? hackable canvas runtime built with React. In fact, the canvas is also just React components. So, component component component. Um, which means you can do some pretty cool stuff. Uh, first one, I'm going to be at the mercy of the demo gods here in the the internet and and other things. So, uh, bear with me here. Um, does anyone remember this app, Make Real? Maybe maybe this tweet uh about Make Real. Did anyone do anyone remember seeing this tweet back in 2023 when the vision models came out?

</details>

**史蒂夫·鲁伊斯**: 好的，没问题。这是最早打破 AI 限制的项目之一。我们现在要切换到我的手机。

<details>
<summary>Original English</summary>

**Steve Ruiz**: All right, cool. Uh, this was one of the first projects to kind of like break containment uh in um in AI. Don't we're going to go to my phone.

</details>

**史蒂夫·鲁伊斯**: 这本身可能就是一场灾难。Make Real 的基本想法是，你可以用 Canvas 画一个东西，然后把它发送给一个模型，让它变成一个可工作的原型。在 2026 年听起来可能很老套，但在 2023 年，这可是轰动一时，因为当时还没有 Vibe Coding 这个说法，甚至还没被创造出来。所以，这是最早让非技术人员无需编码或查看代码就能制作技术产品的项目之一。再次强调，我们得看网络之神的脸色。我们拭目以待。我将让它运行一会儿。冒着泄露 API 密钥的风险，我会尝试切换到一个更快的模型。哦不，它来了。也许我给了它一个很难处理的东西。我们看看。等一下。基本想法，就是那样。是的，那里有我的 API 密钥。每次做这个演示，我都得悲伤地轮换它们。看看在结束演讲之前，会花掉多少钱。这是一个非常简单的提示，就是“让它变得可交互”。这…这不是我想要的，但我们看看。

<details>
<summary>Original English</summary>

**Steve Ruiz**: [ __ ] this. Um, which which may may itself be a disaster. Uh so the the basic idea with make real was that you could um use a canvas draw this and then send that to a a model and and have it make it into a working prototype which sounds very very quaint in 2026 but in 2023 it was all the rage because there was no lovable there was no kind of vibe coding hadn't been termed or coined as a as a term. Uh and so this was one of the first projects where nontechnical people could make technical stuff without having to code or to look at code. And so again, we are at the mercy of the the several [ __ ] various internet uh internet gods. So So we'll see. I'm gonna I'm going to let this go for a minute. Um but at the risk of leaking my API keys, I will try and switch to a faster model. Oh no, it's coming. All right. Maybe I just gave it something hard to uh hard to work on. We'll see. Hang on a second. Basic idea. Something like that. Uh yeah, there there there's my API keys. I always got to rotate them every time I uh do this demo, sadly. Uh we'll see how much how much gets spent before I get done with the talk. Um but it's a very simple prompt. It's just like go make this interactive. This is uh this is not what I asked for, but we'll see.

</details>

**史蒂夫·鲁伊斯**: 好的，不错。酷。这是一个可以工作的应用，这很棒。它就是一个简单的 HTML，但你也可以在上面注解。你可以说，比如，嘿，actually，让这个变成绿色，为什么我们不使用这些颜色？我要把它变成红色、黑色。使用这些颜色，对吧？你就在这里构建一个提示，包括之前的网站。现在只有 **Google Stitch** 提到了，我之前也提到了。这个想法……它根本没按我的要求做，演示太糟糕了。我们要继续了。过去几年，情况已经发生了变化。不过，还有另一个，Teal Draw Computer，我实际上不会深入讲，但这是关于一系列提示的，但最终我们想，“嘿，Canvas 上的 AI 也许会很有趣。也许我们应该让 AI 像一个协作者一样工作，和你一起在 Canvas 上协作。”

<details>
<summary>Original English</summary>

**Steve Ruiz**: All right, good job. Cool. And this is a this is a working working thing, which is great. It's like a real little bit of HTML, but you could also annotate on top of it. You could say like, hey, uh actually make this green, and why don't we use these colors? I'm going to make this red and uh and and black. Um use these colors, right? And so you're kind of constructing a prompt here, even the prompt that includes the old uh website. And uh there's not many apps that have actually like kind of used this only now. Only like the the Google Stitch that I mentioned before. Uh this idea of well, it didn't do anything that I asked it for. Terrible demo. We're gonna we're going to move on. Things have changed in the last couple years. Anyway, uh there was another one, teal draw computer, which I'm actually not going to go into, but this was uh a couple of like chains of prompts, but eventually we we were like, "Hey, AI on the canvas actually might be pretty cool. Maybe we should um have the AI kind of work as a collaborator, like work with you on the canvas."

</details>

**史蒂夫·鲁伊斯**: 所以，第一个想法相当直接：你可以说，比如说，“画一只猫。”你可以做任何事。你可以说“给我画个图表”，“完成我的幻灯片”，“完成我正在做的图表”等等。和像**Diffusion Models**这样的图像模型不同，它不是在构建图像，而是利用结构化的文本输出来制作我能做的同样的东西。我有很多工具，有圆圈、形状等等。看到这些东西的变化真是……太悲伤了。但其中有趣的在于，这是一个探索模型及其知识和行为方式的途径。比如，“让猫吹灭蜡烛”。这很酷。你也可以做类似“画一只老鼠”这样的事情。同时在不同部分使用多个提示。即使我没有告诉它蜡烛是什么，应用也不知道蜡烛是什么。我也不确定猫会不会吹气，但它正确地解读了这一点，并将其融入了设计。而且细节非常丰富。依然令人难过。所以，这很有趣，因为它解决了许多可能不显而易见的问题，比如文本模型在处理结构化数据时遇到的问题。第一，文本训练数据比图像少得多。第二，很多训练数据存在文本模型不会遇到的冲突。其他类型的模型不会。例如，笛卡尔坐标图上的 y 轴，向上数值就增大，对吧？0、1、2、3、4、5。在网页上，y 轴是向下增加的，对吧？左上角是零。这里的左上角是零，但向下移动时，y 就会增加。有左右之分，对吧？有你的左、舞台左，等等。这些在语言和图像中存在冲突。所以，训练模型使其行为可预测并产生类似这样的东西，非常棘手，但很有趣。

<details>
<summary>Original English</summary>

**Steve Ruiz**: So, the first one of those was pretty pretty straightforward idea where you could say like, you know, draw a cat. You could do anything. you could say um draw me a diagram you know finish my slides complete this graph that I'm working on things like that uh and unlike maybe image models uh like diffusion models and things like that it's not building an image it is using text structured outputs to to make the same things that I could make right so I have I have tools I have like circles and shapes and like this uh and it's funny to see how these things have changed over to oh it's sad Um uh but uh the uh you know the fun of of this is as a way of exploring the model and and what the model knows and how it can comport all that stuff. Uh make the cat blow out the candle. Um it's pretty cool. You can also do something like draw a mouse. So multiple um multiple prompts at the same time on different parts. And so even though I didn't tell it what a candle was, then I certainly like the application doesn't know what a candle is. Uh and I'm not even sure that cats can like blow, but it's correctly interpreted that and kind of incorporated into the into the design. So uh with incredible detail as well. Still sad. Uh so the um this was really fun because this is like solving a lot of problems that might not be obvious like like vision models when it comes to to structured data. Um number one there's much less vision training data than there is for text. Number two a lot of that training data like conflicts in ways that text does not. Other other types of things don't. So for example the the y-axis on a on a cartisian graph as you go up that number goes up right? So 0, one, two, three, four, five. Uh, on the web, the y- axis goes up in this direction, right? The top left corner is zero. Your top left corner here, but as you go down, the y goes up. There's left, right? Like there's your left, there's stage left, there's all sorts of uh uh things that that conflict within language uh and within images. So, um, training the model to kind of behave predictably and and produce things like this is, uh, was really tricky, but this was fun. Um, but we felt like it it didn't go really far enough

</details>

### 从单次生成到代理循环

**史蒂夫·鲁伊斯**: 因为它只是一次性生成。我想做一个代理。这是 **Cursor** 在 2025 年左右的样子，我做了这个。画一个蝴蝶的生命周期图。它进入了一种类似代理循环的模式，就像你们可能在别处看到的那样，我相信你们现在每天都要和它互动很多次，它会产生一个输出，然后审查输出，并不断迭代，直到它认为完成为止。我们确实努力遵循当时代理编码的惯例，这些代理循环最常见，有很多子特性，比如拒绝，看到它的思考过程，看到它是如何工作的。

<details>
<summary>Original English</summary>

**Steve Ruiz**: because it was just oneshotting, right? I wanted to do an agent. So, this is what cursor looked like back in uh, 2025 or something like that when I did this. um draw a diagram uh of the life cycle of a butterfly. So this put it into a kind of like agentic loop like you might have seen seen elsewhere um that I'm sure you you interact with dozens of times a day by by now for this crowd um where you have it produce an output and then review the output and kind of iterate until it thinks it's done. Um and we really tried to hue to the conventions at the time of um you know coding agents that were where these agents um this agent loop was seen most most often where yeah there's kind of like a lot of sub features like rejection you know seeing its thinking seeing how it works. Um

</details>

**史蒂夫·鲁伊斯**: 很棒，现在 Canvas 上有了蝴蝶的生命周期图。非常酷。然而，这仍然不够。因为就像这个一样酷，它仍然感觉像是，我不知道，像是把我的键盘交给了另一个 AI，而不是一个与我协作的伙伴。虽然这个模型在很多使用 Teal Draw 的设计应用中都得到了很好的应用，比如 Love Art 或 Magic Path，尤其是在教育领域，那里有一种类似辅导老师的“帮我写作业”或者“帮我填我的……哦，天哪，我能即兴来个吗？Steve Ruiz，班级，年龄，随便什么。”你可以让它完成我的 D&D 角色卡。它会接上你的思路，填入表格，做这些有趣的事情。也许我稍后会回来讲。但我真正想要的是把代理从侧边栏移到 Canvas 本身里。哦，我是一个战士。太好了。我接受。所以，我们做到了，而且我们是用“ fairies（小精灵）”做的，也许你们看到过，也许没有。这些是 Canvas 上的小家伙们。你可以随便扔它们。它们不喜欢被长时间拿着。它们会开始恐慌。是的。好的。

<details>
<summary>Original English</summary>

**Steve Ruiz**: great and now we have the uh the butterfly life cycle on the canvas. Pretty cool. However, this was still not really enough because as as cool as this was, it still felt like I don't know, it felt like I was handing my keyboard to some some other AI rather than someone collaborating with me. Um although this model has been used really well in uh a lot of design apps that use teal draw uh things like love art or magic path. Um and in in education especially where you have this kind of tutor of like help me with my homework and help me fill out my um you know uh oh gosh let's see if I can do this on the fly. Steve Ruiz uh class you know age whatever. Um, and you can kind of ask it to like uh complete my D&D character sheet. All right. And it'll it'll kind of pick up what you're doing and fill out forms and do do fun stuff like this. Maybe I'll come back to that as it as it kind of chooches along.

</details>

**史蒂夫·鲁伊斯**: 你可以做同样的事情，比如画一只猫。同时在多个地方使用多个提示。现在，把代理放到 Canvas 上有很多有趣的事情。你可以看到代理的状态，对吧？这是我正在运行的多个代理。用编程术语来说，这些就是多个终端窗口或者什么东西。或者这是 Composer 里的东西，但你可以看到它们在做什么。我缩得太远了。我所有的精灵图都是自己做的。你不仅能看到它的思考过程，还能看到它的行动。还能看到它在项目的哪个位置相对于其他代理进行操作。这些其他代理可以看到彼此在做什么。所以，如果我让这个在猫身上画一顶帽子，而我画了猫的脖子。我们错过了脖子。它们会开始工作，对吧？它们能够同时处理彼此的东西。但我们也可以让它们一起工作。比如，我抓起这三个小精灵，Ferris、Helen 和 Joan。画些别的动物。其中一个会被选为主导者。所以，这个是领导者，它会去侦察 Canvas 上发生了什么，然后创建一个待办事项列表，并将该列表委托给其他代理。我们在去年 10 月、12 月就开始做这个了。我们和很多人同时在研究代理编排。这种想法，即“好吧，我们如何给它们共享状态？我们如何拥有领导者-追随者模式？或者我们如何管理这些东西本质上是盲目的，同时又防止它们在做的事情上重叠？”所以，你可以看到这里的领导者并没有做任何工作，但它正在观察。哦不，那是领导者。那是领导者。它正在观察、判断，并确定这是否完成，以及是否正确完成。

<details>
<summary>Original English</summary>

**Steve Ruiz**: The what I really wanted is like to bring the agent out of the sidebar and into the the canvas itself. Um, oh, I'm a fighter. Nice. Nice. All right, I'll take that. Uh, and so we did and we did it with fairies, which maybe maybe you saw, maybe not. Um, these are like little little guys on on the canvas. You can kind of throw them around. Uh, they don't like to be held for very long. They'll start freaking out. Yeah. Okay. So, uh, and, uh, but you can do the same thing like, you know, draw a cat or something like that. Now putting the agents on the canvas have a whole bunch of interesting things. You can see the state of the agent, right? These are multiple agents that I'm kind of running in in coding terms. These would be multiple terminal windows or something like that. Or this would be in composer, but you can kind of see what they're doing in a way that uh uh hang on. I'm zoomed way out. I did all the sprites myself. Um and you know, not only can you kind of see its thinking, but you can see its action. And you can see where it where in the project it's sort of like acting relative to the other um other agents. So, and you know these other agents can can see each other of what they're doing. So, if I ask this one to draw um a hat on the cat uh and I draw this one draw the cat's neck. We missed we missed the neck. uh they'll they'll they'll get to work, right? And they're they're able to kind of work with each other's stuff at the same time. Um but we could also ask them to work together. So if I grab all three of these uh these fairies, Ferris, Helen, and Joan, um draw some more animals. Uh one of them will be elected leader. So, this one is is the leader, and it's going to go scout kind of what's going on on the canvas, and then it's going to create a to-do list, and it's going to delegate that to-do list to the other agents, right? Um, this is all like we were doing this in like December, October of last year. Uh, and we're figuring this stuff out at the same time that that a lot of people were figuring out agent orchestration. This idea of like, okay, how do we give them shared state? How do we uh, you know, have a leader follower? or like how do we manage the fact that these things are essentially blind while they're working and prevent them from kind of overlapping uh in terms of like what they're doing. And so you can kind of see the the the the leader here isn't doing any of the work. Uh but it is going to kind of observe. Oh no, that's the leader. That's the leader. Um it's observing uh and uh and and judging and and establishing whether this is like done or not and and whether it's done correctly. Um,

</details>

### 从 Canvas 代理到桌面应用安全

**史蒂夫·鲁伊斯**: 还是不够，对吧？小精灵很有趣。如果你想玩这个，顺便说一句，网址是 fairies.taljar.com。就像 Make Real 是 AI 的一个很好的入门一样，Draw 某个东西，点击一个按钮。小精灵是谈论多个代理如何协同工作的绝佳方式。它们可以做真正的工作。让我试着抓取一个，这是一个关于电子书或其他什么的长的描述。如果我召唤我的小精灵，让它们为这个应用制作线框图。好的。我将让它们边工作边继续聊天。我迟到了 10 分钟。我还有五分钟再结束。下一步是给代理更多地访问 Canvas。我们开始遇到安全方面的障碍，比如，对用户来说，什么才算安全？我们有一个运行时 API，你可以直接用代码调用它，对吧？AI 非常擅长编码。所以也许我们可以做一些沙盒化的事情，但不行，因为我们需要 DOM，我们需要浏览器来观察情况。我们需要能够生成截图，所有这些。所以我们决定改用我们的桌面应用。在假期期间，我整理了一个 Electron 包装器，包装了 Teal Draw。我开了一个端口。我说，“好吧，Claude（此处指代AI），做一个小的 HTTP 服务器，然后开放一个端点，任何发布到那个端点的内容，都当作 JavaScript 来处理并运行。”这是个糟糕的主意，真的不该这样做。但在一个离线桌面应用中，一个基于文件的应用，最坏的情况是什么？你可能会伤害自己，我猜，但你不会伤害到我们其他人。

<details>
<summary>Original English</summary>

**Steve Ruiz**: still not enough, right? Fairies are fun. If you want to play with this, by the way, this is at fairies.taljar.com. Um, in the same way that make real was a really good introduction to um to just AI at all, right? Draw something, click a button. Um, fairies is a great way to talk about like multiple agents kind of working together. Uh, and they can do real work. Let me try and grab a like this is a big description of like an ebook or something like that. And if I summon my fairies uh uh make this make the make make the wireframes for this app. Cool. And I'll I'll just kind of let them let them get to work while we keep talking. Um the started 10 minutes late. I'm going to I'm going to take another five minutes before I jump. Uh the next step for this one is to to kind of give more access to the canvas to the agents. Um and there's really we started to kind of run into the barriers of of safety like what is actually safe to to do with our hackable thing for for users. Um because we have a runtime API, you could just code against it, right? and AI is really good at coding. So maybe we could do some sandboxed, you know, stuff, but no, because we need the DOM, we need the kind of the browser as a way to see what's going on. We need to be able to generate screenshots, all this stuff. Um, so we decided to use our uh our desktop app instead. So I over the holidays, I threw together a um an app that Electron wrapper that wrapped Teal Draw uh and I opened a port essentially. I said, you know, okay, Claude, like make a little HTTP server and and open a put up an endpoint and anything that gets posted to that endpoint, uh, treat it as JavaScript and run it, which is a terrible idea. Not a good idea. Like, don't don't do that on on your app.

</details>

**史蒂夫·鲁伊斯**: 看，它们正在工作。构建我的电子书阅读器。太棒了。谢谢，小精灵们。那么，这给了我们什么呢？我将跳过那个演示。你可以想象，我可以这样说，“将此代码可视化，绘制一张图表。”好的。然后，我将更改图表，更新代码以匹配图表。很简单，对吧？我们可以选择我们想要的抽象级别。但更令人惊讶的是，我当时想，“嗯，好吧，看看这个。我要画一个用户界面，或者别的什么。”对吧？我希望它是“腿长”的，我希望它是“T恤颜色”。即使 TL Draw 实际上并没有……我们没有“鼠标悬停”或“点击”的原语，它不是一个完整的……这个东西可以针对编辑器编写代码。所以，比如，让它变得交互式。我们来看看它会发展到什么程度。到目前为止，这方面的结果非常酷，但也很奇怪和令人不安。因为 AI 就像，“当然，让我们进行脚本注入，对吧？”它记录自己的方式就是“这是你应该这样做的”。它根本不介意更改你桌面上的任何东西。如果你曾经想……比如，我们的团队成员 Max 说，“我不想在 Spotify 里放播客了。我想从我的 Spotify 应用里移除播客。”Claude，你能做到吗？它说，“当然，让我看看那个压缩过的代码，那个东西的包，然后把它撕掉。”它很乐意这样做。让他们开心。他们很喜欢。哦，那是什么？我甚至不知道你做了什么。你创建了一个 HTML？

<details>
<summary>Original English</summary>

**Steve Ruiz**: However, for an an offline desktop app that is file-based, like what's the worst that could happen? You could hurt yourself, I guess, but you're not going to hurt the rest of me. Uh, and look at them. Look at them going. Building my little ebook reader. That's fantastic. Thank you, fairies. Uh, so so what does that what does that give us, though? Um, I'm going to I'm going to skip the demo where uh, as you can imagine, I could I could say, hey, visualize this code. Make a diagram. Cool. All right. I'm going to change the the diagram, update the code to match the diagram. Easy, right? you can have these kind of like let's pull up the the level of abstraction that we want. Um, but the the more surprising stuff was actually where I was like, you know, okay, like check this out. Uh, I'm going to draw a little user interface or whatever, right? And I want this to be a leg length and I want this to be a t-shirt color. Uh, and even though TL Draw doesn't really have the ability to, we don't have like primitives for on hover or on click or it's not like it's not a fully thing. This thing can write code against the editor. So like uh make it interactive and and we'll see we'll see where it gets to. Um, so far the results on this have been like really really cool in ways that are super strange and disturbing. Uh, because like asking like the AIS are like sure let's do some script script injection, right? Like that's the way that it documents itself is like this is how you you should do this. Um, it has no qualms at all by the way changing stuff that's on your desktop on your computer. If you've ever wanted to like for example like we uh one of our team Max was like you know what I don't like podcasts in my Spotify. I want to get rid of podcast in my Spotify app. Claude can you just do that?

</details>

**史蒂夫·鲁伊斯**: 嗯？就像，它创建了一个新的 HTML 网站。这是指针。它甚至不是一个滑块。不，我想要它在 Teal Draw 里。好的。是的，我们喜欢它。它还在闪烁，你们注意到了吗？拜托，做吧。是的，看，它来了。我们看看能不能…来吧。是的，所以，嗯，你可以在桌面应用中做很多事情，它很乐意这样做。我几乎可以感觉到它很想对网站这样做。就像，让我把爪子伸进去。好吧，拜托。拜托。还没成功。我们得……我们得……我们得设置一下交互性。拜托。这会很有趣。我认为我们将要发布它。我们……它已经发布了，但你只需要……我喜欢本地优先的应用。我喜欢文件优先于应用的理念。这些想法直到现在都只是好奇心。等等。哦，拜托。太令人失望了。我们得以后再谈。我会让它奏效的。但现在，一个本地基于文件的东西，能够暴露自己给云端和本地的代理，本质上进行脚本注入，这驱动了许多以前只停留在想法中的事情。如果你真的想最大化代理的效力，以最大化它的作用，并且承担风险，那么你基本上只需要把它交给用户，然后说“祝你好运”。我认为 **OpenClaw** 做得很好，但这些都是锋利的工具。玩得开心。我的“Canvas 上的代理”演讲结束了。工作仍在继续。如果你想玩小精灵，我强烈推荐，因为它非常有趣，你会发现一些让你惊喜的事情，也让我感到惊讶。它们也有 IRC。我看看。是的。总之，如果你想关注 Teal Draw 的动态，我们在 Twitter X 上是 @Teal Draw，我在 @Steve。我会发布很多关于这些东西的内容。谢谢大家。

<details>
<summary>Original English</summary>

**Steve Ruiz**: And it's like sure let me go through the minified code of the bundle of the thing and let me just rip and tear. Uh and it's happy to do it. It makes them happy. Uh they like it. Um oh what the [ __ ] was that? Um, I don't even know what you did. You made a uh an HTML What the >> What? Like it it created a new HTML site out of this. And this is the pointer. It's not even a slider. No, I want I wanted it in in the teal draw. All right. Yeah, we we we love it. It's blinking as well. I don't know if you caught that. Come on, do it. Yeah, there we go. Let's see if it can come on. Let's go. Um, so yeah, like there's really like uh no limit to what what what it can do with the desktop app and it's happy to do it in a way that um I can almost tell that it it it uh would love to do this to websites. Like it would love like just let me just get my get my claws in there. Um all right, come on. Come on. Still not working. We're gonna we're gonna we're g we're gonna go set up the interactivity. Come on. Um this is gonna be really fun. I think we're going to just release this. Uh we're the um I mean the it is released, but the uh the notion that you can take like I love local first apps. I love file over app. I love there's all these ideas that up to now have kind of been curiosities and uh almost like hang on. Oh, come on. Oh, that's such a such a disappointment. We're going to have to catch me later. I'll make it work. Uh but now actually the like the idea of a local file-based thing that is is able to expose itself to to um to to cloud and agents like locally in order to to essentially script inject kind of motivates a lot of that that stuff which previously was idealistic into like well that's the only way that you could do this. If you really want to maximize the agency in order to maximize what it can do and take the risk uh and take on that risk, then you kind of just need to hand that to the user and say good luck. Um I think OpenClaw does this pretty well, but like this these are sharp tools. Have fun, you know. Anyway, uh that is my agents on the canvas talk. Uh work continues. If you want to play with the fairies, I highly recommend it because it's super fun and you will find things that surprise you that have surprised me. Uh they have IRC as well. Let me see. Yeah. Anyway, uh and if you want to follow along with Teal Draw, we are on Twitter X at Teal Draw and then I'm at Steve and post a lot about this stuff. So, uh thank you for coming. Cheers.

</details>