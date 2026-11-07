---
author: How I AI
date: '2026-09-14'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=zJEHbvT5_Yg
speaker: How I AI
tags:
  - ai-agent
  - workflow-automation
  - product-design
title: How I AI 对话设计师：用 Grockbot 构建个人网站与辅助设计工作流
summary: Claire Vo 对话 Grob Bot 设计团队的 John 与 Pong，分享了借助 Grockbot 搭建个人网站以及用机器人辅助 Figma 设计、日常语言学习与医保核销等实践用例与提示词技巧。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Claire Vo
  - John
  - Pong
companies_orgs:
  - WorkOS
products_models:
  - Grockbot
  - Figma
media_books:
  - How I AI
status: evergreen
---
<!-- chunk 1/6 -->

我用 AI 是为了让自己离开电脑，而不是被绑在电脑前。所以你在健身房的时候，有人让你做点什么，而你能够直接说：“好的，尽管去做，搞定它，然后把健身练完。”这是一种好得多的工作方式。

<details><summary>Original English</summary>
I use AI to get me off my computer, not on my computer. And so the fact that you were at the gym, got asked to do something, and your disability be like, "Yep, go for it, get it done, and finish your workout." It's like a much nicer way to work.
</details>

>> 我当时就直接在 Figma 里把那两个正在进行中的不同画板截了个图。然后我就指了指它们，让 Bot 去做它的工作。我甚至大部分内容都没看。它生成了三个产出物，把 Ben 在 Slack 上发给我的内容复制粘贴过去，然后说：“我觉得我们把这些都覆盖到了。”在我开这个电话会议的同时，工作就在推进完成，我真的很喜欢这一点。我觉得不用自己亲自做这些琐事，简直是个天赐的福音。

<details><summary>Original English</summary>
>> I was able to just screenshot in Figma these two separate artboards of work that was already in progress. And doing so, I just pointed to those, had the bot do his work. I didn't even read most of this stuff. It produced three outputs, copy pasted what Ben [music] had sent me on Slack and said, "Think we got all these covered." While I'm on this call, work is getting done, which I really love. I think the fact that I don't have to do this stuff myself is a godsend.
</details>

>> 现在每当我去某个地方，我基本上只要给 Grockbot 发一张照片、一张截图，或者甚至直接发那个地方的名字，它就能弄清楚那是个什么地方。它会通过 Google Play API 去查，我能拿到准确的地点和坐标。它会修正透视角度，移除画面里的人，把它转换成我在网站上使用的那种 3D 微缩模型视觉风格。

<details><summary>Original English</summary>
>> Now, when I go somewhere, I can basically just send Grockbot a photo, a screenshot, or literally just the name of the place, and it'll figure out what the place is. It'll look it up through Google Play API and I get the right location and coordinates. It'll fix the perspective and remove [music] people and turn it into like a 3D miniature visual style that I use on the site.
</details>

>> AI 可能会让人觉得是对创意艺术的威胁。但听着，你崇高的天职绝不是在 Figma 里做渐变填充。我告诉大家的是——

<details><summary>Original English</summary>
>> AI can feel like a threat to the creative arts. Like look, your highest calling was never to design gradient fills in Figma. And what I tell people is
</details>

### 欢迎来到 How I AI

欢迎回到 How I AI。我是 Claire Vo，产品负责人，也是一名 AI 痴迷者，我的使命是帮助大家用这些新工具更好地进行构建。今天我请到了来自 Grob Bot 设计团队的 John 和 Pong，他们将为我们展示两个非常棒的 AI 设计用例。第一，如何搭建一个美观、个性化且易于更新、符合设计师标准的个人网站。第二，Grubbot 是如何被用来设计 Grubbot 本身的，包括 Figma Pro 可以在哪些方面让你在健身房以及工作中的生活轻松得多。让我们马上开始吧。

<details><summary>Original English</summary>
welcome back to how I AI. I'm Claire Vo, product leader and AI obsessive here on a mission to help you build better with these new tools. Today I have John and Pong from the Grob Bot design team and they're going to show us two really awesome AI design use cases. One, how to build a beautiful custom and easy to update personal site that meets the bar of a designer. And two, how Grubbot was used to design Grubbot, including where Figma Pro can make your life at the gym and work a lot easier. Let's get to it.
</details>

本期节目由 WorkOS 赞助播出。AI 已经改变了我们的工作方式。各种工具正在帮助团队编写更好的代码、分析客户数据，甚至自动处理支持工单。但这里有一个问题。

<details><summary>Original English</summary>
This episode is brought to you by WorkOS. [music] AI has already changed how we work. Tools are helping teams write better code, analyze customer data, and even handle support tickets automatically. But there's a catch. [music]
</details>

这些工具只有在深度接入公司系统时才能发挥良好作用。你的 Copilot 需要查看你的整个代码库。你的聊天机器人需要跨内部文档进行搜索。而对于企业买家来说，这引发了严重的安全担忧。这就是为什么这些应用从第一天起就面临严格的 IT 审查。为了通过审查，它们需要安全认证、访问控制、审计日志以及全套企业级功能。从头开始构建所有这些，工作量极其庞大。

<details><summary>Original English</summary>
These tools only work well when they have deep access to company systems. Your co-pilot needs to see your entire codebase. [music] Your chatbot needs to search across internal docs. And for enterprise buyers, that raises serious security concerns. That's why these apps face intense IT scrutiny from day one. To pass, they need secure authentication, access controls, [music] audit logs, the whole suite of enterprise features. Building all that from scratch, it's a massive lift.
</details>

这就是 WorkOS 的用武之地。WorkOS 为你提供企业级功能的即插即用 API，让你的应用能够具备企业就绪能力，并更快地向高端市场拓展。可以把它看作是企业级功能的 Stripe。OpenAI、Perplexity 和 Cursor 已经在利用 WorkOS 加快步伐并满足企业需求。在 workos.com 上加入他们以及数百位其他行业领袖的行列吧。今天就开启构建。

<details><summary>Original English</summary>
That's where work OS comes in. Work OS gives [music] you drop-in APIs for enterprise features so your app can become enterprise ready and scale [music] up market faster. Think of it like Stripe for enterprise features. OpenAI, Perplexity, and Cursor are already using work OS to move faster and [music] meet enterprise demands. Join them and hundreds of other industry leaders at workos.com. Start building today.
</details>

Pong、John，感谢你们今天加入 How I AI。

<details><summary>Original English</summary>
Pong John, thank you for joining How I AI today.
</details>

>> 很高兴来到这里。很乐意分享。

<details><summary>Original English</summary>
>> Glad to be here. Happy to share.
</details>

>> 感谢邀请我们。

<details><summary>Original English</summary>
>> Thanks for having us.
</details>

### Grockbot 的热潮与体验

>> 我可是个狂热的 Bot 爱好者。实际上我们昨晚在录制节目前刚好聊到，我们在 Andre and Horwitz 办了一场“Grockbot 女士之夜”。有 900 人报名，队伍排到了街角。Grockbot 迎来了属于它的高光时刻。而我非常喜欢的一点是，SpaceX AAI 内部有这么多人实际分享了非常实用且独特的用例，展示他们自己是如何找到新方法来用 Grockbot 完成工作、构建软件以及做很酷的事情的。那么，过去几周身处对 Grabbot 如此爆炸般的关注中心，感觉如何？发布这样一个产品，感觉怎么样？

<details><summary>Original English</summary>
>> So, I am a big bot girl. Actually, we were just talking before the show last night. We did a ladies who Grockbot night at Andre and Horwitz. There were 900 registrants a line around the block. Grockbot is having its moment. And one of the things I love is so many people inside SpaceX AAI actually sharing really practical and unique use cases of how they themselves have found new ways to get work done, build software, do awesome things with Grockbot. Um, so how has it been, you know, the past couple weeks just been being in the middle of this sort of explosion in Grabbot interest? How does that feel, um, shipping a product like that?
</details>

>> 真的很令人兴奋。我是说，设计师能参与到一个受到如此高度关注和深度参与的项目中，我觉得是很难得的。而且我觉得，我们每天也都在向用户学习。大家问了我们很多问题，仿佛我们因为正在设计这个产品就是专家一样。但我觉得我们从用户那里学到的同样多，来自大家分享他们自己的工作流、技巧和心得，特别是最近在 X 上，还有从你这里也是，Claire。这真的很有趣。

<details><summary>Original English</summary>
>> It's really exciting. I mean, I feel like it's rare to have this amount of attention and this amount of engagement on something that a designer gets to work on. And I think um, we're learning day by day also from our users. I think there's a lot of questions being asked about us as though we're experts on the product just because we're designing it. But I think like we're learning just as much from the users, from uh people sharing their own workflows, um their tips and tricks, especially on X recently uh and from you as well, Claire. It's been really fun.
</details>

>> 大家可能不知道，在开始录制之前，我们其实一直在翻看并准备屏幕共享内容。而在准备的过程中，我们大家都在说：“哦，我们需要那个功能。我们需要这个功能。我们得把这里做得更容易一点。”所以，能见证这个产品在刚推出就拥有巨大产品市场契合度的同时不断演进的过程，真的很有意思。Pong，我知道你有一个想要展示给我们的工作流。关于 Grogbot 以及通用的 AI Agent，我非常喜欢的一点就是它真的开辟了用新方式去做旧事情的途径，以及用更容易的方式去做我们以前常常做的事情。那么，带我们了解一下你要展示的内容，以及为什么你认为 Grockbot 是应对这项任务的合适方式吧。

<details><summary>Original English</summary>
>> People don't know this, but before we started recording, we were actually scrolling through and prepping screen shares. And as we were going, all of us were like, "Oh, we need that feature. We need this feature. We need to make this a little bit easier." So, it's fun to be able to see the process of this product evolve as it has tremendous product market fit right out the gate. Well, Pong, I I know that you have a workflow that you want to show us. And one of the things I love about Grogbot and AI agents in general is it's just really opening up new ways to do old things and and easier ways to do things that we all used to do before. So, walk us through what you're going to show us and why you think Grockbot is the right way to take on this task.
</details>

### 用 Grockbot 搭建动态个人网站

>> 好的。我有这么一个相当个人的故事。我经常吃中餐，有时候点外卖的时候，你知道米饭装在一个白色纸盒里。盒子上画着一座鲜红色的中国寺庙。上周末，我看着它，突然冒出一个奇怪的想法：这座寺庙究竟在哪里？它是一个真实存在的地方吗？它在哪里呢？于是我上网搜了一下，发现它可能在旧金山唐人街的某个地方。我就想：“好吧，我们去找找看。”我就去了唐人街。我在周围转了一阵子，其实并没有找到那座寺庙。但在路上我拍了一堆照片，其中有一家卖水果和其他东西的小杂货铺。我给它拍了一张照片，后来我在等公交车的时候，用 AI 把它转成了一个 3D 黏土微缩模型，我觉得看起来挺酷的。那天晚些时候我回到家，打算重新做一下我的个人网站。这事我拖延了一段时间了，然后我把那个 3D 杂货铺拿过来，直接放到了首页上。所以它带有一点奇思妙想，挺有趣的。页面非常极简。基本上就只有这个小店铺，然后加上一些关于我的文字。最后，我写了类似于“最后出现在唐人街 JBC Market”这样的内容。然后我就想：“哦，这其实挺有意思的，因为对于个人网站，我一直都有这样一个困扰，尤其是作为设计师，你花了大把时间做一个网站，发布之后，大家看上大约 30 秒就离开了。”而且说实话，连我自己也不怎么回去看它。

<details><summary>Original English</summary>
>> Yeah. So, I have this pretty personal story. Um, I eat a lot of Chinese food and then sometimes when you get a takeout, you know, the rice comes with this white paper box. So, it's a right red Chinese temple on it. And then last weekend, I was looking at it and I had this random thought like where is this temple? Like, is it a real place? Uh, where is it? So, I searched online and I found it might be somewhere in San Francisco, Chinatown. And I was like, "Okay, let's let's find it out." Like, I went to Chinatown. I worked around for a while and I did not actually find the temple. But I took a bunch of photos along the way and there was this little produce shop uh setting fruits and other stuff. And I took a photo of it and later I was waiting for bus and then I used AI to turn it into a 3D clay miniature and I thought it looked pretty cool and then later that day when I went back home uh I plan to redo my personal website. I have procrastinated for that for a while and then I took that 3D grocery store and then I put it drop it onto the homepage. So it's a little bit of whimsical. It's fun. Uh the page is super minimal. Basically, it was just this tiny store and then some texts about me. At the end, I wrote something like uh last scene at JBC Market in Chinatown. And I was like, "Oh, this was actually kind of interesting because I've always had this problem with personal website that especially as a designer, you spend all this time making one and then you launch it and people look at it for like 30 seconds and then they leave." And honestly, even myself don't really go back to see it that much.
</details>

所以我不想让它仅仅是又一个摆在那里的个人网站。我希望它能更具生机一点，而且对我来说能更有用，因为我也是那种喜欢在各种地点签到的人，我喜欢记录自己去过哪里、和谁在一起、在做些什么。市面上做这个的应用程序太多了。大概每隔两三年就会出一个新的签到应用，大家用一阵子，最终它就销声匿迹了。所以我想：“哦，为什么我不干脆把它做成我的个人网站呢？为什么我不自己来做呢？”接着我立刻想到，如果我要这么做，我不想每次都手动去弄。为什么它不能在我去某个地方的时候自动更新呢？于是就在那时，我开始和 Grogbot 沟通。因为通常即使是针对这种简单的小想法，我也不确定自己需要什么。也许我需要一个 CMS，我需要某种管理后台，我需要把图片上传到某个地方，我需要托管一个网站、部署它、存储代码。我想着，我不想去搭建所有那些东西。我甚至都不知道该从哪里下手。所以我就想测试一下用 Grabbot 怎么做。我基本上就告诉 Grabbot，想法是这样的，做这个最简单的方法是什么？我们怎么把它跑通？然后我们就开始构建了。没有 Figma 文件，也没有产品需求规格。老实说，我真的不知道它最终会走向何方。我只是试着先建一个东西，看看效果，然后思考，哦，要是它能做这个会怎么样？要是能做那个会怎么样？然后它

<details><summary>Original English</summary>
So, I didn't want to make it just another personal website uh sitting there. I want it to be a little bit more alive and actually be more useful to me because I'm also kind of person that I try to like check in to places and then I like this idea of having a record of where I've been, who I was with, and like what I was doing. And there have been like so many apps on the market to do this. Like every couple years there's one new check-in app and then people use it for a while and eventually disappears. So I was like, "Oh, why don't I make it just my personal website? Why don't I create it myself?" And immediately I thought, um, if I'm going to do it, I don't want to manually do it every single time. Um, why can't it can't it just update itself when I when I go somewhere? So that's when I started talk to Grogbot. Um because normally even for this like simple small ideas I I'm not sure like what I need. Maybe I need a CMS. I need some kind of admin portal. I need to upload an image somewhere. I need to host a website. Um deploy it, store the code. And I'm like I don't want to build all of that. I don't even know like where to get it started. So uh I just want to test it how it works with Grabbot. I basically told Grabbot, here is the idea. Uh, what's the simplest way to do it? How can we make this work? And we just started building it. Um, there's no Figma file. There's no spec. Honestly, I didn't really know where it was going. Uh, I was just trying to build one thing and then look at it and then think about, oh, what if it can do this? What if it can do that? And then it
</details>

<!-- chunk 2/6 -->

实现它，然后我们又有了另一个想法。嗯，所以顺其自然、凭感觉走真的很有意思。最终，这个想法变成了一条签到流水线。现在我去什么地方，基本上只要给 Grockbot 发一张照片、一张截图，或者干脆就发一个地名，它就能弄清楚那是什么地方。它会通过 Google Places API 去查询，我从而拿到准确的地理坐标。它会处理图片，生成浅色和深色两个版本。它会修正透视，然后去掉人，把建筑的立面单独抠出来，做成我在网站上用的那种 3D 微缩模型视觉风格。然后我想，好吧，位置是一方面，但很多时候更有意思的是人——我和谁在一起？所以我也把这个加上了。

<details><summary>Original English</summary>
implement it and then we get another idea. Um, so it was very fun just to go in with the flow and like trust the vibe. And eventually this idea turned into a check-in pipeline. So now when I go somewhere, I can basically just send Grockbot a photo, a screenshot, or literally just the name of the place and it'll figure out what the place is. It will look it up through Google Places API and I get the right location coordinates. It will process the image. it would generate a light version and a dark version. It'll fix the perspective and then remove people um isolate the facade of that building uh and turn it into like a 3D miniature um visual style that I use on the site. And then I was like, okay, location is one thing, but a lot of time more interesting part is the people like who am I with? So I added that too.
</details>

>> 我刚才正想说那看起来像双子峰（Twin Peaks）。我当时还在想，那是双子峰吗？我猜对了吗？[笑声] 看起来棒极了。

<details><summary>Original English</summary>
>> I was going to say that looks like Twin Peaks. I was like, is it is it Twin Peaks? Did I get it right? [laughter] It looks great.
</details>

>> 对，那是三天前的事。所以现在我和朋友出去玩，真的只要发一张地点的截图和我朋友社交账号资料的截图，剩下的就全部交给 grabbot 了。所以我做了一个签到机器人，专门针对这个工作流程打造的。它会搞定一切，转换成我网站所需的数据结构。也许我们现在可以试一下。比如我们三个人……

<details><summary>Original English</summary>
>> Yeah, that was three days ago. So now when I hang out with a friend, I can literally send a screenshot of the place and a screenshot on my friend's social profile and the grabbot will take over the rest. So I have this check-in bot that specifi uh I specifically build for this workflow. It figures everything out. It turns it into a data structure that my website expect. Maybe we can try it now. Like if three of us
</details>

>> 在一个现实中的地点碰面，可能是一个著名的地标之类的，你可以报一个地方。

<details><summary>Original English</summary>
>> meet in a physical place, maybe a famous land landmark or something, you can name a place.
</details>

### 现场演示签到流水线

>> 哦，我来报一个，因为我住在伯纳尔高地（Bernal Heights）。不如就说我们在伯纳尔高地？嗯，我猜就叫伯纳尔高地峰（Bernal Heights Peak）。

<details><summary>Original English</summary>
>> Oh, I'll I'll name because I live in Bernal Heights. So, why don't you say we're at Bernal Heights? Um uh I guess just called Bernal Heights Peak.
</details>

>> 嗯，那里有什么具体的建筑物或地标吗？

<details><summary>Original English</summary>
>> Yeah, there like a specific building or like a landmark.
</details>

>> 有，那有点像双子峰。只是旧金山的另一座小山。好吧，既然我们人不在那儿，但我们可以……

<details><summary>Original English</summary>
>> Yeah, that's that's it's kind of like Twin Peaks. It's just a different it's another hill in San Francisco. Okay, since we are not there, but we can
</details>

>> 哦，在秋千那里。那里有一个……有一个秘密秋千。你看到这儿了吗？对，就是那个。嗯，总有人把它挂上去，然后市政部门又不断把它拆下来。

<details><summary>Original English</summary>
>> Oh, at the swing. There is a uh there's a clandestine swing. You see it right here? Yep, that's it. Um that somebody keeps putting up and the city keeps pulling down.
</details>

非常……这真的是一个争议焦点。

<details><summary>Original English</summary>
Very It's like a real point of contention.
</details>

>> 好，我们看看行不行。我把你的社交账号和约翰的社交账号放上去。

<details><summary>Original English</summary>
>> Okay, let's see if it works. And I'll put your social handle and John's social handle there.
</details>

### 低阻力个人建站与 AI 工具链

>> 我太喜欢这条流水线了。在你加载这个的时候，我得往后退一步说几句。我认为对 AI 来说最难做到的事，就是建一个让设计师自己感到满意的个人网站。所以光是你能够做到这一点，就已经让我印象非常深刻了。我以前也做过设计师。我之所以避开做个人网站，是因为我讨厌去敲定某种代表自己的东西并发布出来。所以就连你也能做出自己喜欢的东西，我真的很佩服。其次，我觉得非常有趣的是，你让保持网站更新变得非常容易且低阻力，而且还呈现出一种非常独特、高质量的视觉效果。嗯，所以我觉得这真的很耐人寻味。要知道，如果你必须回到家、下载照片、复制粘贴 X 账号资料并做完所有这些事情，你可能就不会经常更新网站了。这需要耗费太多心力。因此，我非常喜欢你把以往可能需要通过某种 CMS 或者直接推送部署到网站的所有这些繁琐步骤，统统压缩进了一个专门针对特定用例的机器人里，由它来为你搞定这一切。我很想在它运行的时候请教一下，你是怎么让它把这些 3D 图像生成得这么好、质量这么高的？

<details><summary>Original English</summary>
>> I love this pipeline. I have to take a step back while you're getting this to load. So I I think the hardest thing for AI to do is build a personal site that a designer will like about themselves. So just the fact that you were able to get to that point. I mean I've been a designer in a past life. I just avoid my personal site because I hate the idea of deciding something represents me and shipping it. So the fact that even you could get to something you like I'm very impressed with. And then the second thing that I think is so fun is you've made it really easy and low friction for you to keep the site updated in a really unique high quality visual way. Um, so I think that is really interesting. you know, if you had to like go home and download your photo and copy and paste in the X profiles and do all this stuff, you probably wouldn't keep the site updated. It just it takes it's too much mental load. And so, I love this idea that you've compressed all these steps that you would have had to do, you know, historically probably through some sort of CMS or pushing directly to the site to just a bot that has a very specific use case. um and and does this for you? I I'm curious while this is running, how did you get it to generate these 3D images so well and so high quality?
</details>

>> 嗯，背后的这套流水线其实是由 Grogbot 摸索出来的。它会生成两张图，一张亮色，一张暗色，因为当主题切换到深色时，我想让灯亮起来。我想要这两张图的两个版本，

<details><summary>Original English</summary>
>> Yeah, so the pipeline behind it is like figured out by Grogbot. It would generate two images when light went dark because when I like when a theme turns to dark, I want the lights to turn on. I wanted two versions of the of the image
</details>

>> 然后它们必须保持一致。这都写进了提示词里。我觉得对我来说很有意思的地方在于，这里面其实没有任何高深复杂的东西。它只是一堆非常简单的积木。呃，有 Google Places 或 Google Maps，然后有图像生成，有一些结构化数据，再由网站把所有东西渲染出来。而 Grogbot 基本上就是把所有这些点串联起来的角色。我觉得这给我带来了一种有些不同的感觉，因为换作以前，我可能也会有这个想法，然后一想到所有要做的事情，就会觉得也许以后再做吧，结果就再也不会去做了。但在这里，我其实并不需要预先知道最终的系统会是什么样子。嗯，我一开始只是拿了一张菜市场的随手拍照片，然后事情就这样一步步发展下去，Grabbot 一路帮我。最终，不知怎么的，我就把这套签到系统跑起来了。

<details><summary>Original English</summary>
>> and then they have to be consistent. And then this was baked in the prompt. And I think it's interesting part for me is none of this is actually fancy. It's just a bunch of like pretty simple building blocks. Uh there's Google plays or Google maps and then there's image generation and there's some like structured data and then there's the website just render everything. And then Grogbot is basically the thing that connect all the dots together. And I think that felt a little bit of different to me because before I would have probably had this idea. I thought about all the stuff I need to do and then I think maybe do it later and I'll never do it. But here I didn't really have to know like what the final system was going to be. Um I just started with this like random photo from a produce store and then like one thing just led to another and Grabbot helped me along the way. um at the end of the day somehow I had this like check-in system running.
</details>

>> 我真的很喜欢这个。我给你提供一个“混沌统治”般的脑洞想法：我们最近请了一位叫 Maddie Reese 的女士来我们的播客，她开放了一个个人 API，让别人可以拉取关于她的信息，甚至可以向她的网站发布内容。你可以给极少数的朋友开放这种程序化访问权限，万一你忘了，他们可以代你更新。你看，你可以把它做成一种社交体验。你可以决定信任谁来做这件事，但这套流程太棒了。把它做成一种社交体验似乎也很有趣。

<details><summary>Original English</summary>
>> I really love this what um I'll give you kind of a really chaos reigns idea which is we had this woman Maddie Reese on um our um podcast recently and she opened up a personal API so that people could pull information about her and also post to to her site. You could give very select use of you very select friends some programmatic access to update on your behalf in case you forget. You know, you can make this a little bit of a social experience. You can see, you know, decide who you trust to do it, but this pipeline's so nice. It seems like very fun to to kind of make a social experience as well.
</details>

>> 你这是要兜一圈回到原点，做出下一代签到应用啊。

<details><summary>Original English</summary>
>> You're going to come full circle and make the next check-in app.
</details>

>> 确实是。我们确实在这么干。我有一个很好笑的故事：我跟我丈夫在一起很久了。我们创办过很多企业，大概二十年前他曾尝试做一款社交签到应用。我当时真的……他和我常泡在酒吧里。我们当时还是朋友。他在酒吧里会说：“你能拜托……你能拜托在这个酒吧用我的应用签个到吗？” 这简直是当年名副其实的白手起家式游击营销。而现在，你直接让你的 AI 机器人代你签到就行了。

<details><summary>Original English</summary>
>> You are. We are. I I have a very funny my my husband and I have been together for a long time. We've started a lot of businesses and probably 20 years ago he was trying to do a social check-in app and he would liter I would literally he I would be at bars. We'd be friends. He would be at bars. He's like, "Can you please can you please check in check in on my app at this bar?" It's like true true bootstrap uh gorilla marketing back in the day. And now you can just tell your AI bot to check in on on your behalf.
</details>

>> 话说，Pong，如果你能把这个接入 Swarm，我也绝对要接入进来用。

<details><summary>Original English</summary>
>> Well, Pong, if you can get this connected to Swarm, I'm definitely going to plug into this as well.
</details>

>> 我现在依然是 Swarm 的元老级用户。

<details><summary>Original English</summary>
>> I'm still I'm still an OG user of Swarm.
</details>

### AI 赋能硬技能与设计工作流重塑

>> 是啊，我用它很久了。我确实把这看作一种趋势，人们变得更加善于表达，变得更加自主，他们可以建立自己独特的做事方式去签到、记录生活，把这份记忆以一种只符合他们自己喜好的格式保存下来。另外，对于设计师，我还想指出一点——因为同样地，我以前也是做设计的——长期以来我都认为自己很有创造力，对大家都在谈论的所谓“品味”、对“优秀的作品应该长什么样”、对“什么是高品质”有着敏锐的感觉，但我缺少一些硬技能，而且在某些我认为难以企及的特定硬核设计技能上吃尽了苦头。你看，我能把圆角半径精确到像素级别，能把字距调得分毫不差，作为 UI/UX 设计师我通宵达旦地做这些都没问题。但我无论如何都画不来插画。我知道好的插画长什么样，但我就是画不出来，它根本不在我的技能树里。所以，对于像我这样拥有基础技能、或许具备战略经验，但在具体实践中缺乏硬技能的人来说，我真正深爱 AI 的一点是，它让我更有可能成为一名更加全面的设计师。因为它给了我这些生成工具、计算机操作工具，以及针对特定技能集的深度专精能力，让我能够把它们与自己真正擅长的事结合起来，从整体上获得更好的产出。你们有过这种感受吗？就像突然惊呼：“天呐，换作以前，我绝对做不出这种 3D 黏土渲染效果。我一直都想做，但我不得不去求我那位擅长 3D 渲染的大神朋友来做。” 你们也有过这种体验吗？还是只有我一个人这样？

<details><summary>Original English</summary>
>> Yeah, I've been using it for a long time. I I do see it as a trend that people become more expressive and become more autonomous and they can set up their unique way to doing things to check in to record their life to like bring this memory in the in a format that only adapts to like their own preferences. You know, another thing that I want to call out for designers because again in a previous life I was a designer is I have considered myself very creative for a very long time and have a good sense of you know this um thing that everybody's calling taste but what what does good look like and uh what is high quality but I lacked some hard skills and really struggled with a spec a specific set of hard design skills I felt were very inaccessible. to me. So look, I can like round a corner radius to the pixel like the per I can like I can get kerning right like I I am a UI UX designer that I can do all day and all night. I cannot illustrate to save my life. I know what a good illustration looks like. I cannot do it. It is just not in my skill set. And so one of the things that I really love about AI as somebody who has a basis of skills um maybe strategic experience but not hard skills in specific practices is it makes my ability to be a more well-rounded designer um a lot more possible because it gives me these generation tools and these computer use tools and these deep like spikes in specific skill sets that let me pair it with the things that I'm actually good at and get a better outcome in general. Do you all ever feel that where you're like, "Oh man, in the past life, I would have never been able to do this like 3D clay render. I would have always wanted to, but I've had to ask my awesome 3D rendering friend to do this." Like, do you all experience that? Is that just me?
</details>

>> 我觉得很多人都在发现，它解锁了许多你曾经认为触不可及的技能集。在我看来，我们俩都会遇到大量的动效设计工作，我可以去描述它，甚至可以用手比划着指出应该呈现的效果，但是……

<details><summary>Original English</summary>
>> I think many people are discovering that it unlocks a lot of the skill sets that you once thought were inaccessible. I think both of us from my experience is a lot of motion work where I can describe it and and kind of even use my hands to point out what's supposed to take place but then
</details>

>> 有了提示词工程，这就变成了可能。P，不知道你怎么看

<details><summary>Original English</summary>
>> with prompting it becomes possible. P I'm not sure about you
</details>

<!-- chunk 3/6 -->

看看在这之外是否还有……

<details><summary>Original English</summary>
if

if

there's

anything

beyond
</details>

>> 之外是否还有你所展示的内容。

我认为这里的机遇在于，制作东西的成本变得如此之低，以至于我们能够去构想在过去成本高得多的东西。现在做起来非常容易，这就开启了新的机遇，以及我们所能创造事物的组合。是的，我想说我经常看到这些，我也这样告诉设计师们。你知道，我确实认为——咱们实话实说吧。AI 确实会让人觉得是对创意艺术的一种威胁。确实会这样。人们一直在谈论这个。而我告诉大家的是：看吧，你的最高使命从来不是在 Figma 里去设计渐变填充。那并不是你来到这个世界上的意义所在。因此作为设计师，能够真正沿着杠杆、专业化往上走，走到品质的前沿、设计的前沿、趣味性，去思考声音这类事情，思考视频这类事情，思考插画和图像这类事情。我只是觉得这能让人在自身技艺的最高水准上运作。嗯，而不是被卡在最底层的那些杂碎事务中。嗯，你知道，那些东西在构建真正优秀作品的基础中固然重要，但并不是某人时间或才能的最高利用。随着 AI 应用的普及，公司的安全风险和合规要求也在增加。新的框架、审计和供应商不断堆积，但你的团队却没有变大。大多数合规工具都承诺自动化，但你实际上还是得手动完成所有工作，追查截图、验证控制项，并在审计季再次来临时疲于应付。

Vanta 的运作方式截然不同。他们的 Agentic Trust 平台旨在随你一起扩展，而不是拖慢你的脚步。借助横跨 400 多个集成的 1,400 多项自动化测试，Vanta 全年收集证据并监控你的控制项，将你的审计准备工作减少 82%。

此外，你在工作的任何地方都可以使用 Vanta Agent。无论你的团队每天是在 Vanta 里工作，还是常驻在 Claude 或 Cursor 这类工具中。想要证据？超过 16,000 家快速成长的公司，如 Ramp、Writer 和 Harvey，都在使用 Vanta 在快速扩展的同时节省时间和资源。我的听众可以通过访问 vanta.com/howiai 获得 1,000 美元的优惠。那就是 vanta.com/howiai，可享 1,000 美元优惠。哦，看。看来它做完了。

<details><summary>Original English</summary>
>> what

you're

showing.

I

I

think

the

opportunity

is

like

the

cost

of

making

things

become

so

low

that

we

can

imagine

something

that

cost

a

lot

more

in

the

past.

Now

it's

so

easy

to

do

and

then

this

opens

new

opportunities

and

combination

of

the

things

we

can

create.

Yeah,

I

would

say

the

things

that

I'm

seeing

a

lot

and

I

tell

designers

this.

You

know,

I

do

think

there

is

let's

like

call

a

spade

a

spade.

AI

can

feel

like

a

threat

to

the

creative

arts.

Like

it

just

can.

People

talk

about

it

all

the

time.

And

what

I

tell

people

is

like

look,

your

highest

calling

was

never

to

like

design

gradient

fills

in

Figma.

Like

that

was

not

what

you

were

put

on

this

earth

to

do.

And

so

as

a

designer,

being

able

to

really

go

up

the

stack

in

terms

of

leverage,

specialization,

the

edges

of

quality,

the

edges

of

design,

delight,

think

about

things

like

sound,

think

about

things

like

video,

think

about

things

like

illustrations

and

images.

I

just

think

lets

people

like

operate

at

the

highest

level

of

their

craft.

Um,

as

opposed

to

getting

stuck

in

the

kind

of

junk

at

the

at

the

bottom.

um

that

you

know

is

important

in

the

foundation

of

building

something

really

great

but

not

the

highest

use

of

someone's

like

time

or

talent.

As

AI

adoption

grows,

so

do

your

company's

security

risks

and

requirements.

New

[music]

frameworks,

audits,

and

vendors

keep

piling

on,

but

your

team

isn't

getting

any

bigger.

Most

compliance

tools

promise

automation,

but

you're

really

stuck

doing

all

the

work

by

hand,

chasing

screenshots,

validating

controls,

and

playing

catch-up

when

audit

season

comes

around

[music]

again.

Vanta

works

differently.

Their

Agentic

Trust

platform

is

built

to

scale

with

you,

not

slow

you

down.

[music]

With

over

1,400

automated

tests

across

400

plus

integrations,

Vanta

collects

evidence

and

monitors

your

controls

year

round,

cutting

your

audit

prep

by

82%.

[music]

Plus,

you

can

access

the

Vant

agent

everywhere

you

work.

Whether

your

team

is

in

Vanta

everyday

or

living

in

tools

like

Claude

or

Curser,

want

proof?

Over

16,000

fast

growing

companies

like

Ramp,

Writer,

[music]

and

Harvey.

Save

time

and

resources

while

scaling

fast

with

Vanta.

My

listeners

can

get

$1,000

off

by

going

to

vanta.com/howi

ai.

That's

van

[music]

ta.com/howi

ai

for

$1,000

off.

Oh,

look.

It

looks

like

it

finished.
</details>

>> 是的，做好了。我想现在已经发布到网站上了。

<details><summary>Original English</summary>
>> Yeah,

it's

done.

And

I

think

it's

published

to

the

website

now.
</details>

>> 非常可爱。

<details><summary>Original English</summary>
>> Very

cute.
</details>

>> 我们还捕捉到了秋千。

<details><summary>Original English</summary>
>> We

have

this

also

capture

the

swing.
</details>

>> 我太喜欢了。如果你想看真正的夜间彩蛋，你知道，我们安排了那个神秘人在晚上把秋千架起来，而在白天，秋千就——秋千就没了，因为 Bernal Heights Park 那架极具争议的秋千正是经历着这样的事情。但我真的很喜欢这个。多么有趣。这完全是我以前无法想象能做到的事情。这太酷了。你知道，这是一个个人用例，我觉得非常棒。不过我们还是切换到工作相关的内容吧，因为 John，你一直在用 Grockbot 来设计 Grockbot，并且有一些非常有趣的工作流要展示给我们看。

<details><summary>Original English</summary>
>> I

love

it.

If

you

want

a

real

Easter

egg

at

night,

you

know,

we

have

the

secret

guy

putting

up

the

swing

and

during

the

day

the

swing

is

the

swing

is

gone

because

that's

what's

happening

with

the

very

controversial

swing

at

the

Bernal

Heights

Park.

But

I

love

this.

How

fun.

and

just

something

that

I

would

have

never

imagined

you

could

do

before.

This

is

so

cool.

You

know,

this

is

a

personal

use

case

and

I

think

a

really

lovely

one.

But

let's

switch

over

to

work

stuff

because

John,

you've

been

using

Grockbot

to

design

Grockbot

and

have

some

really

interesting

workflows

you're

going

to

show

us.
</details>

### 用 Grockbot 设计 Grockbot 的工作流

>> 是的，很乐意聊聊这个。我觉得对我而言，呃，有些人已经读过我写的一篇文章，讲的是我如何设计使用——不，不，不。我如何使用 Grockbot 设计 Grockbot，里面介绍了几种不同的想法，呃，关于它是如何为我释放生产力的。嗯，它是如何真正让一些曾经难以企及或非常枯燥的任务变得更容易上手，也不那么枯燥了。我今天想探讨的其中一个案例是关于 Figma Bro 的，我也将其作为一个，呃，Bot 模板分享了出来，这样其他想尝试的设计师就可以使用它。希望大家能帮忙改进它并分享回给我，这样我就可以在自己的 Rockbot 中进行更新。嗯，我只想讲两个简单的用例，第一个就在这里的屏幕上。呃，这是我通过语音录制给它的一个实际 Prompt。呃，所以我来念一下。好的，情况是这样的：我有 Figma 里的一个链接作为示例。在左边，我有几个图标的截图。也就是这边的这个，它们本质上需要以完全相同的位置摆放在每个 Bot 旁边。我有第二张截图，显示的是旁边没有图标的那些。所以，取下那个图标，将其放大，放到与我截图中其余 Bot 相同的位置，并确保它们处于相同位置、放大的图标，以便我拥有一整套这样的图。如果有任何不清楚的地方，告诉我。而我们需要这个的原因，是因为 Ben 当时在做一些社区资产，让我非常迅速地拼凑一些东西出来。当时是，呃，8 点 52 分，我正准备从健身房离开，我能够直接在 Figma 中截取这两张，呃，正在进行的工作的独立画板。一个来自图标库，另一个来自品牌手册。这样做之后，我就指向了这些，让 Bot 去完成它的工作。大部分这些内容我甚至都没读，但它生成了三个产出，我当时觉得太棒了，复制粘贴了 Ben，呃，在 Slack 上发给我的内容，然后说我想我们把这些都搞定了，接着它制作了这个小表格。呃，我当时还在健身房，所以这些更多是语音消息。嗯，但随后它继续迭代，呃，也许把它弄得稍大一点，做圆角处理让它看起来美观，我也能检查它在圆角状态下看起来是否好看。嗯，最后得到的反馈是也许我们可以调整一下颜色，所以也应用了这一改动。而这类事情可能，你知道，在 Figma 中并不会花非常长的时间，但现在我甚至不用在电脑前就能搞定。

<details><summary>Original English</summary>
>> Yeah,

happy

to

talk

about

that.

I

think

for

me,

uh,

some

folks

have

already

read

an

article

that

I

wrote

that

was

how

I

design

using

No,

no,

no.

how

I

designed

Grockbot

using

Grockbot

and

I

go

over

a

couple

of

different

ideas

uh

of

how

it's

unlocked

productivity

for

me.

Um

how

it's

really

made

some

of

the

tasks

that

used

to

be

really

inaccessible

or

really

boring

more

accessible

and

a

little

less

boring.

One

of

the

ones

I

wanted

to

talk

through

today

was

on

Figma

Bro,

which

I

also

shared

out

as

a

uh

bot

template,

so

other

designers

out

there

who

want

to

try

it

can

use

it.

Hopefully

you

can

help

improve

it

and

share

it

back

with

me

and

I

can

update

it

in

my

own

rockbot.

Um,

I

just

want

to

talk

through

two

quick

use

cases

and

that's

the

first

one

being

on

the

screen

right

here.

Uh,

this

is

an

actual

prompt

that

I

gave

it

using

voice

recording.

Uh,

so

I'll

just

read

it.

Okay,

here's

the

situation.

I

have

a

link

in

Figma

as

an

example.

On

the

left,

I

have

a

screenshot

of

a

couple

of

icons.

That's

this

over

here

that

need

to

be

essentially

placed

next

to

each

of

the

bots

in

the

exact

same

placement.

I

have

the

second

screenshot

which

shows

ones

that

don't

have

an

icon

next

to

them.

So,

take

the

icon,

scale

it

up,

put

it

in

the

same

position

as

the

rest

of

the

bots

that

I've

screenshotted,

and

ensure

that

they're

in

the

same

position,

scaled

up

icon,

so

that

I

have

a

whole

set

of

these.

If

anything

is

unclear,

tell

me.

And

the

reason

we

needed

this

was

because

Ben

was

doing

some

community

assets

and

asked

me

to

put

together

something

really

quickly.

It

was

uh

8:52,

so

I

was

wrapping

up

at

the

gym,

and

I

was

able

to

just

screenshot

in

Figma

these

two

uh

separate

artboards

of

work

that

was

already

in

progress.

one

being

from

the

icon

library

and

the

other

being

from

the

brand

book

and

doing

so

I

just

pointed

to

those

had

the

bot

do

its

work

I

didn't

even

read

most

of

this

stuff

but

it

produced

three

outputs

and

I

was

like

great

copy

pasted

what

Ben

had

uh

sent

me

on

Slack

and

said

think

we

got

all

these

covered

and

then

it

made

this

little

table

uh

I

was

still

at

the

gym

at

the

time

so

this

is

more

voice

messaging

um

but

then

it

kept

iterating

uh

maybe

making

it

a

little

bit

bigger

rounding

it

so

it

looks

good

and

I

can

check

that

it

looks

good

in

a

rounded

state.

Um,

and

then

eventually

getting

feedback

that

maybe

we

could

play

with

the

color

and

so

applying

that

as

well.

And

this

is

the

type

of

thing

that

maybe,

you

know,

wouldn't

take

super

long

in

Figma,

but

now

I'm

just

doing

while

I'm

not

even

at

my

computer.
</details>

>> 你能为那些甚至不知道这种神奇效果是如何发生的人，具体讲解一下它是如何连接到 Figma 的吗？

<details><summary>Original English</summary>
>> Can

you

just

walk

us

through

exactly

how

this

is

hooked

up

to

Figma

for

folks

that

kind

of

just

don't

even

know

how

this

magic

happens?
</details>

好的。我们使用了一个 Figma MCP，它非常有效，呃，尤其是如果你直接把——一旦建立好连接，呃，把它的链接提供给你的 Bot，并给它一组非常具体的控制规则。在我的 Bot 本身中，它具备相应的 Skills 以及一些我对它的具体要求。我喜欢把我的画板，你知道，并排水平排列，呃，间距大概 50 像素或者 100 像素，取决于它们的大小。呃，我预先告诉它所有这些事情，这样当我回头查看时，它就不会给我弄出一个乱七八糟的文件。我发现它结合模板使用起来非常智能。所以相比于以前我需要对它进行更多次指导，我这里有第二个示例可以展示给你们看，它在我设置的方式上更加精确一点。

<details><summary>Original English</summary>
Yeah.

So,

there's

a

Figma

MCP

which

we

use

and

is

pretty

effective

uh

especially

if

you

just

give

the

once

you've

made

the

connection

uh

give

your

bot

the

link

to

it

and

give

it

some

very

specific

set

of

controls.

In

my

bot

itself,

it

has

the

skills

and

some

specifics

that

I

request

of

it.

I

like

to

have

my

artboards

laid

out,

you

know,

side

by

side

horizontally

uh

in

uh

maybe

50

pixels

apart

or

100

depending

on

the

size

of

them.

Uh,

and

I

tell

it

all

these

things

up

front

so

that

it

doesn't

give

me

like

a

messy

file

when

I

come

back

to

it.

It

works

really

smartly

with

a

template

I

found.

And

so

from

before

I

kind

of

had

to

direct

it

a

few

more

times,

but

I

have

a

second

example

that

I

can

show

you

which

is

a

little

bit

more

precise

with

how

I

set

it

up.
</details>

>> 太棒了。

<details><summary>Original English</summary>
>> Awesome.
</details>

>> 这就是今天早些时候的事。现在大约是两点。呃，这是在一个小时前，我被要求为我们今天上线的、呃、最新的 Bot Marketplace 制作一些营销素材。嗯，我们希望突出展示一些主要的用例。呃，我们有大家提供给我们的那些 Bot，包括你自己提供的，Claire。嗯，我们正在营销素材中突出其中的一些内容。嗯，所以我做的事情是，呃，我给你们看我在 Figma 里做了什么。就在这上面。我做了一个简短的模板，把它标记为给 shove 的，因为是他找我要的。呃，我告诉了 Bot——

使用那个模板，我把链接贴在了这里。呃，这是消息。这是模板。嗯，使用我们品牌手册的背景和壁纸，并匹配我已有的样式，但把它应用到其余的每一个上。你们会注意到，其中有一些并没有把——把图片完全更新。有一些更新了。呃，这意味着我需要回过头去催它一下。但嗯，这省去了我必须手动进入每个页面、拉取每张图片、更新每一张、更改实例、更改背景、更改文案的时间。这一切都在这里替我完成了。所以在我和你们通话的同时，呃，工作正在被完成，我真的很喜欢这一点。我认为不必亲自做这些琐事真是一大幸事。

<details><summary>Original English</summary>
>> And

this

was

just

earlier

today.

Right

now

it's

around

two.

Uh,

this

was

an

hour

ago

where

I

was

asked

to

uh

create

some

marketing

material

for

our

uh,

latest

bot

marketplace

which

is

launching

today.

Um,

and

we

want

to

highlight

some

of

the

primary

use

cases.

Uh,

we

have

the

bots

that

are

being

provided

to

us

by

people,

yourself

included,

Claire.

Um,

and

we're

highlighting

some

of

these

things

in

marketing

material.

Um,

and

so

what

I

did

was,

uh,

I'll

show

you

what

I

did

in

Figma.

It

was

up

here.

I

made

one

quick

template,

and

I

labeled

it

for

shove

because

he

asked

me

for

it.

Uh,

and

I

told

the

bot

using

that,

which

I

linked

right

here.

Uh,

here's

the

message.

Here's

the

template.

um

use

our

brandbook

backgrounds

and

wallpapers

and

match

the

styling

that

I

have,

but

apply

it

to

every

other

one.

And

you'll

notice

that

some

of

them

don't

have

the

the

photo

fully

updated.

Some

of

them

do.

Uh

which

means

I

need

to

go

back

and

prod

it.

But

um

this

just

saved

me

the

time

of

needing

to

go

manually

onto

each

site,

pull

down

each

photo,

update

each

one,

change

the

instance,

change

the

background,

change

the

copy.

It's

all

done

for

me

here.

So

while

I'm

on

this

call,

uh

work

is

getting

done,

which

I

really

love.

I

think

the

fact

that

I

don't

have

to

do

this

stuff

myself

is

a

godsend.
</details>

>> 而且我不得不说，看，Trad 就在那儿被认出来了。Claire 的个人 Bot。嗯，一个非常非常受欢迎的、真正改变了我生活的 Bot。我很喜欢这个，因为，你知道，这些东西依然是如此美丽。而且作为——作为设计师，你想要花时间去做的是让这些资产真正变得出彩。你并不一定需要去从事制作设计，那就是，你知道，

<details><summary>Original English</summary>
>> And

I

have

to

say,

look,

Trad

spotted

right

there.

Claire's

personal

bot.

Um,

very,

very

popular

one

that

has

really

changed

my

life.

I

love

this

because,

you

know,

again,

this

stuff

is

so

beautiful.

And

as

as

designers,

what

you

want

to

spend

time

on

is

making

these

assets

really

great.

you

don't

necessarily

need

to

be

doing

production

design,

which

is,

you

know,
</details>

<!-- chunk 4/6 -->

将它应用到不同的资源上，并在不同版本中进行润色。因此，我推测你能够把更多时间花在让这个系统具备真正可扩展性的基础层面上，然后让 Figma Bro——我很喜欢这个名字——让 Figma Bro（顺便说一句，Figma Bro 和 Tadbot 应该会成为朋友），让 Figma Bro 去做那些具体的制作工作，我觉得这真的很棒。另外，对于那些之前没赶上的人，你知道我对大家常说的就是：我使用 AI 是为了让自己离开电脑，而不是被绑在电脑前。因此，在你在健身房健身、被要求去做某件事的时候——尤其是像 Figma 这样通常确实需要人类手指在触控板或其它东西上操作的事情——你只要能表示“好啊，去做吧，把它搞定”，然后继续完成你的锻炼，我觉得这实在是太棒了。这真的是一种好得多的工作方式。

<details>
<summary>Original English</summary>
carrying it across different assets and and polishing in different versions. And so your ability to spend more time, I'm presuming, on the like foundations that make this system really extensible and then letting Figma Bro, love the name, um, let Figma Bro, Figma Bro and Tadbot would be friends, by the way. Um, let Figma Bro kind of like do the production work, I think is really amazing. And then for folks that missed it, you know what I tell people is I use AI to get me off my computer, not on my computer. And so the fact that you were at the gym, got asked to do something, you know, especially something like Figma that really does require like your human fingers on a on a on a touchpad or whatever to do it. And your just ability to be like, "Yep, go for it. Get it done." Um, and finish your workout, I think, is is so nice. It's just like a much nicer way to work.
</details>

### 从即兴灵感到工作原型

>> 是的。说到在移动中工作，我想介绍的另一个 bot 是 Devbot，或者叫 experiments。这两个名字我有点互换着使用，不过它们背后的高层核心思想是，很多时候你会冒出一个点子、一种交互或一个布局，某种你想要去探索的特定设计。但还是那句话，你当时可能不在电脑前。这属于经典的“洗澡时的灵感”时刻，你想要把某些东西记录下来，甚至想让它达到一定的保真度，但你当时当地并没有时间和精力去那么做。这就引出了 Devbot，它和这里的 experiments 协作非常紧密。所以，我是说，你开始能看出我工作方式中的一种模式了。这也发生在移动途中。我截取了一张我们实际移动端应用体验的截图，一张我那个叫 Slack search 的 bot 的截图，然后给这个 bot 发了一条语音备忘录，说我想制作一个特定类型的原型。于是我用语音把它全描述了一遍，虽然说的稍微有点杂乱，但核心意思是：当我分享一个 agent 时——我们一直用快照、模板这个词，它不是 agent 本身，而是它的一个副本，用来发给其他同事或朋友等等——所以这个点子就是，如果它真的能做一个截图效果会怎样：如果我点击分享按钮，它就截取一张屏幕截图，缩小，然后回缩到预览模板中。我正好有了这个想法，想测试一下，就把任务交给 bot 让它去跑。它去和 Motion God 进行了沟通，因为我描述的很多内容都是屏幕上进行转场的元素。它们之间自己进行了沟通。我甚至几乎都没去过问，直到回过头来看它的成果。我就直接跳到最终状态吧，就在这里。我们不得不重新创建一些位于我们现有的测试仓库里的组件。但针对我的要求，它拿出了两个方案。第一个是，如果我在这里点击分享 agent，它会做一个小小的截图效果，然后放大进去并展示一些细节。我可以看到这个 bot 的常规例行程序，当我切换标签页时它会移动，显示插件，然后你可以复制链接并发送出去。我也要求提供一种稍微更含蓄克制一点的方案。它基本上采纳了这点，把它做成了一个直接进入分享弹窗的版本。所以这是一个很巧妙的点子，但最终我们决定不采用这个方向。它感觉稍微有点太模仿最初引发这一整套探索的 iOS 截图思路了。但我确实很喜欢这种轻松的方式：只要拿出一个概念——通常你必须要么在 Figma 里面连线画原型，要么如果你用代码做原型的话，得花时间认真构思它该怎么构建——用大白话把它描述出来，然后说“去跑吧，根据我的描述你随意发挥、去理解它，把它变成一个我可以交互的东西”。所以 Ideas bot 也许应该是我现在使用的 experiments 和 Devbot 的结合体。不过确实，现在那些随性的洗澡灵感可以变成一个真正可运行的原型了。

<details>
<summary>Original English</summary>
>> Yeah. And speaking of on the- go, um the other bot that I want to highlight is uh Devbot or experiments. Both of them I kind of use interchangeably, but um the highle idea behind these is a lot of times you get an idea, an interaction or a layout, a specific type of design that you want to explore. Um but once again, you might not be at your computer. Uh classic shower thoughts moment where you want to capture something and maybe even get it to a certain level of fidelity, but you don't have the time and energy just then and there to do so. Um, which brings me to Devbot, uh, who works really closely with experiments, also over here. So, I mean, you're starting to see a pattern in the way that I work. Uh, this was also on the go. I took a screenshot of our actual mobile app experience, um, a screenshot of my bot called Slack search and gave a voice memo to the bot saying I wanted to make a specific type of prototype. So I described it all using voice kind of rambling a little bit but in essence it was when I share an agent we've been using this term of a snapshot a template. It's not the agent itself but it's a copy of it to give to another co-orker or friend or whatever. And so the idea was what if it would actually do a screenshot effect. If I click the share button it takes a screenshot shrinks down zooms back to the preview template. And I just had that idea wanted to test it. Gave it to the bot to run with. Um, and it talked to Motion God because there's a lot of things that I described that were things elements on the screen that were transitioning. Um, it had its own conversations. I barely even checked it once again until I came back to its work. And I'll just jump to the uh end state which is right here. Um, we had to recreate some of the components within uh the the test repo that we have. Um, but it came up with two options of what I asked for. The first being if I click share agent here, does a little screenshot effect, then zooms into it and shows some of the details. I could see the the routines of the bot and it moves when I switch tabs, shows the plugins, and then you can copy a link and and send it. And I asked for a little bit more of a subtle approach as well. And it basically took that and turned it into a version that just goes directly into the share modal. And so clever idea in the end decided not to go in this direction. it felt a little bit too derivative of kind of the iOS screenshot idea uh that originated this whole exploration. But I do love how easy it is to take just the concept that normally you would have to either prototype with the noodles in Figma, take the time to actually consider how it gets built if you're prototyping in code. Um describe it in plain words and say run with it, do with my description of it how you will interpret it and turn it into something that I can interact with. So ideas bot maybe should be the combination of what I'm using today as experiments and devbot. Uh but yeah the random shower thoughts can now become uh a real working prototype.
</details>

### “垃圾桶开发模式”与降低试错成本

>> 有一件事，你知道，我也在科技行业待了很久了，在过去，我跟你讲，肯定会有某位极其优秀的优秀设计师会说：“我有了这么一个绝妙的点子。当我们做分享时，我们要做这个截图效果。感觉会非常棒，能给人们带来一阵多巴胺激增。大家一定会喜欢的。我们会分享更多的东西。”而接着会发生的事情是，你会碰上一个产品经理说：“这不是当前重点。给我看 ROI。这能支撑哪个 OKR？”然后工程师会说：“我才不会去写那个愚蠢的玩意儿。我还有技术债要还。”或者诸如此类的一大堆理由。即使你闯过了这二者的重重关卡，终于把它做出来了，然后你说：“啊，算了。不是很喜欢，不是很喜欢。”大家就会很生气。他们会说：“我们专门投入了时间。我们把这个排了优先级。你这根本就不是把东西废弃掉。”所以我把这种方式称为软件开发的“垃圾桶模式”，也就是在做东西时预先假设把它扔进垃圾桶是极其廉价的——无论是原型，还是最终交付给客户的东西。

<details>
<summary>Original English</summary>
>> One one thing that you know again I've been in tech a million years and so in the past I am telling you some delightful amazing designer would have been like I had this great idea. We're going to like screen it's when we do share you're the screenshot effect. It's going to like feel so good. that it's going to like give people a spike of dopamine. They're going to love it. We're going to share more things. And what would have happened is you would have hit a product manager that says, "Not a priority. Show me the ROI. What's the OKR?" And an engineer being like, "I'm not going to build that stupid thing. I have tech debt to do." Or like a bunch of stuff. And even if you get through the gauntlet of both of those and you get it built and you're like, "Ah, never mind. Don't love it. Don't love it." People are angry. They're like, "We dedicated time. We prioritized this. It's like you don't deprecate any of these things. And so the thing that I call this like the trash trash can method of software development which is like building things with the presumption that it is totally inexpensive to throw them in the trash whether those are prototypes or things that you get to your customers.
</details>

>> 而且我认为这能让你在看待产品开发、软件开发的流程时更加开阔，因为你不会总是停下来问自己：这足以支撑将它做到应用里去吗？这足以去麻烦别人、让它的优先级排得比这个或那个更高吗？所以对于一个在很多环境中做了很长时间软件的人来说，这类产品真正让我感到兴奋的正是这一点，因为你可以如此迅速地迭代。你不需要关闭大脑中那个提出“要是这样呢、要是那样呢”的创意部分。并且你也不必因为冒出了一个自己没有百分之百把握、但想看看它效果如何的想法，而为了所谓“浪费资源”感到焦虑。

<details>
<summary>Original English</summary>
>> And I think it allows you to be a lot more expansive about what the process of product development software development looks like because you're not always stopping yourself saying is this enough to justify getting it into the app? is this enough to bother somebody um to get it you know higher priority than this or that. And so for somebody who has built a lot of software in a lot of environments for a very long time that is the piece of products like this that really make me excited because you can iterate so quickly. You don't have to shut off that like creative part of your brain that says well what if this what if that. Um and you don't have to be stressed that you're quote unquote wasting resources. um when when you come up with an idea that you're not 100% sure of but want to see what it looks like.
</details>

>> 完全同意。我认为这也让做设计师变得更有趣了。说实在的，很多以前的限制、设计流程以及跨职能协作中以前令人头疼的环节，就像你说的，在如今都不太成问题了。

<details>
<summary>Original English</summary>
>> Totally agree. And I think that makes it more fun to be a designer. Again, honestly, um a lot of the previous constraints, the parts of the design process and working crossunctionally that were a headache before um are a little less of a problem these days, like you said.
</details>

### 快问快答：如何组织与使用个人 Bot

>> 太棒了。嗯，我很喜欢。为了给大家做个回顾：Figma bro 就是你的设计保护员，当你在健身房里锻炼时，它在你的画板上做着推举；然后是 experiments 和 Devbot，基本上就是接手你洗澡时的灵感、散步时的灵感，具体实现完全不需要你操心。让它们去忙活吧。你可以回头再来看这个点子，然后由你来决定是否要发布它。好了，这过程真是太有趣了。给大家概括一下，我们展示了某种个人工作流，以及如何将 Grockbot 作为一种开发与设计管线，以极小的繁琐辛劳去完成以前无法完成的奇妙事情。John 向我们展示了如何利用 Grockbot 更高效地进行实验、设计和制作。现在让我们退一步，进入快问快答环节。我的第一个问题非常简短，想问你们两位：除了你们刚才展示的这些 bot 之外，你们大致是如何看待自己的 bot 的？谁是你们的最爱？你们是如何组织它们的？

<details>
<summary>Original English</summary>
>> Amazing. Well, I love it. Just to recap for folks, uh, Figma bro your, um, design spotter while you're at the gym getting getting the reps in on your art boards and then experiment in Devbot. Basically, like take your shower thoughts, take your walk thoughts, and the implementation is none of your business. Let them let them cook. You come back to an idea, and then it's up to you whether or not you want to ship it or not. Okay, so this has been so fun. And to recap for folks, we've shown sort of like the personal workflows and how you can do kind of amazing things um that you wouldn't have been able to do before with very minimal toil using Grockbot as sort of like a development design pipeline. John showed us um you know how to experiment, design, do production more efficiently with Grockbot. Let's just take a step back. Let's go to lightning round questions. My first one just very quick between you two other than the bots you showed kind of like how do you think about your bots? Who are your favorites? How do you how do you organize them?
</details>

>> 我数字生活中的很大一部分都被委托给了各种各样的 Grog bot。通常，我把它们划分为两类：生活和工作。所以，我有几个专门针对我生活各部分的 bot。例如，我的参谋长 bot。我管理所有的 bot，但我有时确实会与其他 bot 对话。不过对于那些我不知道该委派给谁的事情，我就会委派给这位参谋长 bot。我想昨晚我还让它帮我买一些 3D 打印耗材。也就是 3D 打印机用来制作物品的塑料材料。有趣的是……

<details>
<summary>Original English</summary>
>> A lot of my digital life has been delegated to all different types of Grog bots. In general, I organize them in two buckets, life and work. So, I have a couple of bots that dedicated for each part of my life. For example, my chief of staff. Um, I manage all the bots, but I sometimes do talk to other bots. Um, but I delegate the things I don't know who to delegate it to to the to the COS bot. So I think last night I was asking it to buy some 3D printing filament for me. Um, so that's the plastic material that 3D printer used to making things. And what's interesting is
</details>

>> ［清嗓子］

<details>
<summary>Original English</summary>
>> [clears throat]
</details>

>> 它不仅能帮你搜索、寻找并购买商品，你实际上还可以把不同的任务串联在一起，比如我实际上让它在购买完成后更新库存清单，因为我在 Notion 里维护着一份 3D 打印耗材库存，我希望能自动添加这条记录。它帮我买好了，而且……我

<details>
<summary>Original English</summary>
>> um not only it can help you search, find and buy the item, you can actually train different task together like I actually once you are done update the inventory list because I keep this 3D printing filament inventory in notion and I wanted to automatically add this record. it purchased it for me and um I
</details>

<!-- chunk 5/6 -->

### 智能体协作与日常管理

我觉得它真正的威力在于把我们日常生活中的不同任务像这样串联起来，给它一个更高层级的任务，让它自己去弄清楚有哪些步骤、需要做什么。也许它能学会这些，然后下次你再做的时候，只要告诉它“做我们上个月做的那件事”，甚至可以让它自动去执行。我有一个邮件管理器，它会把我所有的待办事项都提炼出来。这是昨晚的事，我当时正在查看收件箱里的待办事项，然后发现有一些 USPS 的快递派送问题，我就让它帮我联系他们。我还有一个日历管理器，事实上它现在已经成了我的日历。比如我正在约某人下周喝咖啡聊天，而现在我大部分时间只要把对话截个图就行。可以在任何即时通讯工具上，比如这次是在 LinkedIn 上，我直接发过去，让它在我的日历上占个座。我现在几乎再也不打开日历应用了。

<details><summary>Original English</summary>
think that's truly the power of it is to like train different tasks in our daily life together and it give it like a higher task and let it figure out uh what the steps what needs to do maybe can learn it and then the next time you do it just tell it do the thing that we did last month and then even have have it automatically do it. I have an email manager which will surface all my action items. This was last night. I was checking any action items from my input uh inbox and then like there's some USPS delivery issued and I ask it to to help me contact them. Um I have the calendar manager who is become in fact to become my calendar now. So I'm scheduling someone for uh for the coffee chat next week and then most of my time today now I just take a screenshot of the conversation. It can be on any IM tool. Um, this one's on LinkedIn and I just send it and it ask you to put a placeholder on my calendar. Um, almost never open the calendar app anymore.
</details>

你也可以把机器人拉进一个群里。打个比方，在这个例子中，我有了这样一个想法：设计一个把猫叫声翻译成英文的应用。于是我把这个想法扔进了群聊，群里有产品经理、有设计师、有工程师，然后他们开始从各自的角度讨论这个想法。看到这样一颗简单的种子播在群聊里，然后围绕它衍生出新的想法，这真的太有意思了。我甚至用它来筹备我们现在正在录的这期播客。我没有麦克风，就去问负责我所有 IT 问题的 IT 机器人，我需要什么类型的麦克风，而我手头只有这一个，它能用吗？在个人生活方面，它正在取代我的新闻应用。每天早上 7 点，我都会收到一份个性化的新闻通讯。我告诉它我想要 AI 资讯，想要和我相关的 AI 新闻，希望它能帮忙做事实核查，并尽可能附上官方链接。另外这一个是个法律顾问，它承担了大量的重复性工作。比如我正在排期等绿卡，在等签证公告牌（Visa Bulletin）的排期，每个月手动去查很费劲。所以我就把这个任务交给了它，给了它链接，它就会每个月去查，然后告诉我排到哪里了、排期进度如何、数据是多少。

<details><summary>Original English</summary>
Um, you can also put bots into a group. So, let's say in this example, let's I had this idea design a app that translate class meow to English. So I threw this idea into the group chat and then in the group chat we have a PM we have designer we have a engineer and then they start to talk about idea from their own perspective and it's so interesting to see like how this simple seed planted in the group chat and then now like derive new ideas around it. I even use it to prepare the podcast that we're doing right now. Um, I don't have a microphone and I I asked my IT bot who's like taking care of all my IT questions. Uh, what type of microphone I need and I only have this one. Does it work? And, uh, for personal life, it's replacing my news app. So, every morning 7 a.m., I'll receive um u a newsletter and it's personalized. I tell it I want to AI information. I want a news about AI that relevant to me. Um, I wanted to like have it do fact check um and then source the official um links as much as possible. And then this one is a legal advisor. So it's taking care of a lot of repetitive task. For example, I'm in this weight list for I'm applying green card. I'm in weight list for this uh visa bulleting and checking manually every month in a par. So I just dedicated this task to and then I give the link and it would go check it every month and then let me know okay where's the where are you are in the queue what's the waiting list um what's the data
</details>

>> 我太喜欢这个了。看起来你就像把所有的琐事、所有需要处理的日常生活杂务，不管是购物，还是查看各种状态、定期核对，都交给了它。而且我也很喜欢这种“我再也不想要邮箱、再也不想要日历了”的想法。我只想让机器人告诉我该去哪里、去哪里露面就行了。

<details><summary>Original English</summary>
>> I love it so it seems like you have just kind of like all the admin all the life admin you need to do whether it's shopping whether it's you know checking in on different status regular check-ins and then I love the idea of like I don't want an email anymore and I don't want a calendar anymore more. I want a bot to show me where tell me where to show up and that's it.
</details>

>> 对看视频的朋友们来说也是一样，这核心就是尽可能轻松地把你正在做的事情推进到终点线，对吧？比如，你知道自己需要买 3D 打印耗材，但你就是不想打开应用、去点那些按钮、挑合适的那一款、陷入评论区，或者被相关的推荐产品分心。直接把东西买了就行。甚至像日历日程，你拉出来一看，发现有冲突，心想“我该怎么办”，然后又被 Slack 分心。我觉得所有这些工具都能让你启动一项任务并不受干扰地一路推到底，确保你能搞定很多事情。而且我认为这里的用例广度相当惊人。John，你有遇到什么不一样的案例吗？比如一两个你觉得大家平时想不到的，或者和常见的杂务、购物稍微有点区别的？

<details><summary>Original English</summary>
>> And so, you know, just just for folks watching this, again, it's like make it as easy as possible to take the task you're doing to the finish line, right? Like, you knew you needed to buy 3D printing filament, but you just don't want to open up the app, click the buttons, pick the right one, get sucked into the reviews, get distracted by the, you know, associated products. just like buy buy the thing or you know even calendar events you like pull it up and you look and you're like I have a conflict what do I do and you get distracted by Slack like all these things I think just allow you to kick off a task and pull it all the way through without distraction and just make sure that you get a lot of stuff done and I think the the breadth of of use cases here is is pretty incredible. John, do you have any that are different than this? like one or two that you think folks aren't thinking of or that uh are are a little different different than the average, you know, admin shopping one.
</details>

### 语言学习与保险核销

>> 我确实有一些比较特别的用例，其中一个是我几天前刚刚开始用的。我一直在学日语，日语这门语言的特点在于它有平假名、片假名和汉字，所以同一种语言有不同的认读方式。最近我突然想到，或许可以直接和这个专门练习日语的机器人交流：一方面尽可能提升我对汉字的认读能力，但同时在需要的时候，下方附有发音，最后再给出一个英文回复。所以我基本就是告诉它把这三种形式都提供给我，这样我就能在和它的日常交流中随时学习。正如你们在上面看到的，我之前让它帮忙找一本特定的书，原本打算让它翻译，但后来那本书出版了，我就直接买了。另一个用例可能非常特殊，我想大家都清楚美国的医疗保险体系运作方式。对我来说这倒不算什么大麻烦，但光是知道可以让机器人了解我的医保方案，我就觉得很有意义。

<details><summary>Original English</summary>
>> I do have some that are a little bit particular and one is just I just started a few days ago. Um I've been learning Japanese and the thing about Japanese as a language is there's there's hiragana, there's katakana and there's kanji and so there's different ways of reading one language. Um and recently I had the thought to just maybe communicate with um this bot which is just a Japanese practice bot um both in a way to uplevel my reading of kanji as much as possible but then have the pronunciation underneath it when I need it as well as finally an English response. So I just basically told it give me all three forms so that I can learn as I go in just regular communication with you. Um I was having it look for a specific book as you could tell up above. Um I was going to have it translate it but then it came out so I ended up buying it. Um the other use case is uh one maybe this very particular I think we're we're all aware of how um the American insurance system is set up. Um and for me it's not even that big of a deal. It's just knowing that it's possible for me to set up the bot to know my my insurance plan,
</details>

>> 拍下任何收据或者医生的账单单据，以此确保自己能拿到最划算的报销。关于这一点，有一半时间我甚至得不到任何额外的退费，但只要知道自己能把任何东西发给它并确信钱花得值，我就觉得很踏实。

<details><summary>Original English</summary>
>> take any photo of a receipt or you know any sort of um doctor statement uh and just ensure that I'm getting the most bang for my buck. Um, and this one I, you know, half the time it doesn't even uh there there's nothing additional that I can get out of it, but it just gives me peace of mind knowing that I can send anything to it and and um know that I'm getting my money's worth.
</details>

>> 是的。我猜大家会想知道这具体是怎么设置的，大概就像是这样：你说“这是我的方案，这是我的保障范围。每当我要开处方药、找医疗服务提供者或去看专科医生时，请参考我的方案，确保我做出最明智的决定”。大体上是这样运作的吗？而且除此之外，每当有发票或收据时，我就问：“我需要做进一步跟进吗？或者我有没有享受到最大的优惠？”

<details><summary>Original English</summary>
>> Yeah. I want to give people I'm guessing kind of how this is set up, which is you're like, "This is my plan. Here's my coverage. Um, anytime I'm going to get a prescription or look for a provider or go to a specialist, like reference my plan and make sure that I'm making the best decisions." Is that kind of the high level what it does? And in addition, anytime there's an invoice or a receipt, I say, "Do I need to do another followup or um you know, am I getting the maximum savings?"
</details>

### 提示词技巧与结语

>> 我太喜欢这个了。作为一个自己承担医疗费用的自由职业者，这绝对是我一出门就要去配置的东西。好的，最后一个快问快答环节，我们的时间差不多快到了。我一定要问一下，因为你们有这么多的机器人，而且它们都有自己的个性和名字——你有 Figma Bro，我有 Tadbot。当这些机器人胡来、不按你的意图执行时，你们是怎么写提示词的？大家会冲它们大喊大叫吗？有没有什么技巧能让机器人重新回到正轨？

<details><summary>Original English</summary>
>> I love this so much. As a self-employed person who finances her own healthcare, um this is going to be one that I go set up right out the gate. Okay, last writing question. We're almost at the end of our time. I must ask because you have so many bots and they all have these personalities and names. You have Figma Bro, I have Tadbot. Um, when the bots are being silly, when they're when they're not doing what you want, how do you prompt? Are you all yellers? Is there some trick to getting your bots back on track?
</details>

>> 在 SpaceX AI 工作有这么一回事：通常在需要排查故障时，他们会找你要会话 ID。[笑声] 我可不想让同事看到我是怎么跟机器人说话的。所以随着时间的推移，我变得温和多了。我会说……

<details><summary>Original English</summary>
>> Here's the thing about working at SpaceX AI is often times when you need to troubleshoot, they ask for your session ID. [laughter] And I don't want my co-workers seeing how I talk to my bot. And so, I've gotten nicer over time. I'll say
</details>

>> 我有时候回复时会带很多情绪，但我觉得一个有用的技巧是：每次你都可以让机器人记住这一点，这样以后如果再发生同样的情况，直接按照上次学到的流程去处理就行。有点像是让它自行提炼并自我迭代。使用的时间越长，它就会变得越好，也会更加适应你的需求。

<details><summary>Original English</summary>
>> I reply with a lot of emotion sometimes but I think a useful tips is every time um you can ask the bot to memorize this so in the future if this happen again then just follow the script you learned last last time um so kind of distill and then iterate it itself um and then the longer you use it the better it become and more adapts to your needs
</details>

>> 我太喜欢这些建议了，两条都很棒：第一，记住会有人看你的转录记录；第二，直接让你的机器人记住如何从一开始就避免这个问题。各位，非常感谢你们如此慷慨地展示这些，你们给了我太多的灵感。我准备回去之后，今天下午结束前就要弄出一个全新的 clairvo.com。我对这个太兴奋了，你们给了我最好的点子。除了在时间线上看机器人们大显身手之外，我们在哪里可以找到你们？我们能帮上什么忙？

<details><summary>Original English</summary>
>> I love that great great tips both one remember who's reading your transcripts and two Just ask your bot to remember how to avoid the problem in the first place. You all, you've been so generous with showing this. You've given me so many ideas. I'm going to go back. You're going to get a brand new clairvo.com by the end of the afternoon. I am so psyched about this. You just gave me the best ideas. Um, where can we find you? Other than all over the timeline where bot is going wild, where can we find you and how can we be helpful?
</details>

>> 我是个深度网瘾患者，你可以在 johnby 找到我，那就是我的名字。

<details><summary>Original English</summary>
>> I'm chronically online. Uh, you can find me at johnby, which is just my name.
</details>

>> 是的，我也一样。我在 X 上。能去上面发发帖、聊聊相关设计真的很开心。

<details><summary>Original English</summary>
>> Yeah, the same for me. I'm on X. Um, and it's lovely to being able to um post and talk about design of the grap out there.
</details>

>> 太棒了。大家快去亲自试试吧。真的很棒，而且很遗憾它已经取代了我深爱的 Open Claus。所以我觉得它非常值得一试。两位，非常感谢你们来到《How I AI》。

<details><summary>Original English</summary>
>> Awesome. Well, and y'all go out and try it. Um, love truly it's been really awesome and regretfully has replaced my beloved Open Claus. So, I think it's it's worth a spin. Both of you, thank you so much for joining How I AI.
</details>

>> 谢谢你，感谢邀请我们。

<details><summary>Original English</summary>
>> Thank you. Thank you for having us.
</details>

>> 非常感谢大家的收看。如果你喜欢本期节目，请在 YouTube 上点赞并订阅，或者更好的是，给我们留言分享你的想法。你也可以在以下平台找到这档播客：

<details><summary>Original English</summary>
>> Thanks so much for watching. If you enjoyed this show, please like and subscribe here on YouTube, or even better, leave us a comment with your thoughts. You can also find this podcast on
</details>

<!-- chunk 6/6 -->

Apple Podcasts、Spotify 或您最喜爱的播客应用。请考虑给我们留下评分和好评，这会帮助其他人发现这个节目。您可以在 howiipod.com 查看我们所有的往期节目并了解更多关于节目的内容。下次见。

<details><summary>Original English</summary>
Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review, which will help others find the show. You can see all our episodes and learn more about the show at howiipod.com. See you next time.
</details>