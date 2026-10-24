---
author: How I AI
date: '2026-10-19'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=UF08V1XIUmw
speaker: How I AI
tags:
  - video-editing
  - terminal-workflow
  - content-creation
  - automation
  - short-form-video
title: Claude Code 剪辑实战：告别时间线与剪辑软件，用终端打造短视频帝国
summary: TikTok 20万粉博主 Brooke Lacey 做客节目，深度拆解如何用 Claude Code 代替传统剪辑软件进行全自动短视频创作。从终端指令自动跳剪、TSV时间轴控制、镜头景别切换，到本地音视频处理与结合评论区自动生成爆款脚本，展示了创作者工作流的全新范式。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Brooke Lacey
  - Claire Val
companies_orgs:
  - Anthropic
products_models:
  - Claude Code
media_books: []
status: evergreen
---
### 序幕：没有时间线的 AI 视频剪辑

**克莱尔 (Claire Val)**: 没有时间线，没有工程文件，甚至没有视频剪辑软件。你找到了一种利用 **Claude Code** 进行编码剪辑的方法，完美契合了短视频这种内容形态。视频文件全都在本地电脑里，根本不需要上传到任何云端。整个过程唯一发生的，就是拉取指令，然后电脑在后台自动完成所有的操作。

<details>
<summary>Original English</summary>

**Claire Val**: No timeline, no project file, no editor. You figured out a way to use Claude code to encode editing that really fits the form, which is short-form content. The file's in the computer, it doesn't upload anywhere. The only thing that's happening is the instructions [music] are being pulled and it's doing all of the things. It's just running the computer.

</details>

**布鲁克 (Brooke Lacey)**: 不仅如此，它在监听音频时还会说：“噢，我刚才听到你说‘把那段剪掉’。”而且它还会说：“这句话你重复录了几次，我挑了其中节奏最好的那一版。”我当时整个人都惊了：“什么？它到底是怎么做到的？”

<details>
<summary>Original English</summary>

**Brooke Lacey**: And [music] not only that, but it's listening and goes, "Oh, I just heard you say cut that out." And then it also was like, "You repeated this a couple of times and I took the one that was the best cadence." And I was like, "What?"

</details>

**克莱尔 (Claire Val)**: 刚才发生的事情就是：Claude 直接降临在我们的视频文件上，完成了自动剪辑。它调出原始素材，然后生成了一段剪辑极其利落的竖屏短视频，节奏完全契合 **TikTok** 的步调。而你整个过程完全双手脱离键盘。

<details>
<summary>Original English</summary>

**Claire Val**: And what just happened is Claude descended upon our videos and cut them. [music] It just pulled up the raw video. There was a really well-clipped vertical short-form video, perfect to TikTok cadence. And you did it with no hands.

</details>

**布鲁克 (Brooke Lacey)**: 没错，我的所有操作全都是在终端（Terminal）里完成的。我更喜欢终端，因为它对系统所有资源的访问权限要大得多。所以只要对它说：“好了哥们，我准备好向观众展示奇迹了。”瞧，双手完全不用碰。在过去的六个月里，这大概是我第15次还是第16次被惊艳到整个人目瞪口呆了。

<details>
<summary>Original English</summary>

**Brooke Lacey**: So, literally, I do everything in the terminal. I like it better. It just has way more access to everything. So, let's say, "Okay, my dude, I'm ready to show the audience the magic." And look, no hands. This is probably the 15th or 16th time in the last 6 months that I literally like fell to the floor.

</details>

**克莱尔 (Claire Val)**: 刚才到底发生了什么？！

<details>
<summary>Original English</summary>

**Claire Val**: What just happened?

</details>

### 欢迎来到 How I AI

**克莱尔 (Claire Val)**: 欢迎回到《How I AI》。我是 **Claire Val**，产品负责人，也是一名 AI 痴迷者。我的使命就是帮助大家利用这些新工具更好地进行构建。今天我们请到了 **Brooke Lacey**，她将带领我们深入了解她使用 Claude Code 进行视频剪辑的完整工作流。她在 TikTok 上拥有超过20万粉丝，并且成功摸索出如何让 Claude 剪辑出幽默风趣、跳剪节奏准确的视频，甚至能自动生成新内容的脚本，真正理解她的语调、氛围和个人风格。

<details>
<summary>Original English</summary>

**Claire Val**: Welcome back to How I AI. I'm Claire Val, product leader and AI obsessive, here on a mission to help you build better with these new tools. Today we have Brooke Lacey and she is going to walk us through her Claude code for video editing flow. She has over 200,000 followers on TikTok and she's figured out how to get Claude to edit her videos to be funny and have the right jump cuts, create scripts for new content, and generally understand her cadence, her vibe, and her style. Let's get to it.

</details>

**克莱尔 (Claire Val)**: 本期节目由 **Firecrawl** 赞助播出。Firecrawl 能为你的 AI Agent 提供来自全网及更广阔领域的数据支撑。你的智能体不仅可以搜索和抓取网页，还能通过单一接口接入 Alexander 迅速扩张的数据库——包含超过1亿个索引数据源和200多家数据提供商。把 Firecrawl 接入 **ChatGPT** 或 Claude，无论是查找联系人工作邮箱、挑选梦幻橄榄球阵容，还是为下一次营销活动分析行业趋势，都能轻松实现。Firecrawl 正在为超级智能构建数字图书馆，把全世界的知识融入你已经在用的工具中。立即访问 firecrawl.dev/howia 开启体验。Brooke，非常感谢你能来参加《How I AI》！

<details>
<summary>Original English</summary>

**Claire Val**: This episode is brought to you by Firecrawl, which gives your AI agents data [music] from the web and beyond. Your agents can search and scrape the web while accessing Alexander's rapidly expanding [music] library of over 100 million indexed sources and more than 200 data providers all through one connection. Connect Firecrawl to ChatGPT or Claude to find people and their work emails, pick your fantasy football lineup, or analyze trends for your next marketing campaign. Firecrawl is building the library for superintelligence, bringing more of the world's knowledge into the tools you already use. Go to firecrawl.dev/howia to get started. Brooke, thanks for joining How I AI.

</details>

**布鲁克 (Brooke Lacey)**: 我太兴奋了！我想你肯定是知道的，但我也想让你的观众知道，我其实是你超级铁杆的粉丝。我非常喜欢你做的一切，今天能来这里真的太激动了。

<details>
<summary>Original English</summary>

**Brooke Lacey**: I'm so excited. I think that you know, but I would like your audience to know that I'm like the biggest fangirl. I really love what you do, and I'm just so excited to be here.

</details>

**克莱尔 (Claire Val)**: 我也非常喜欢你做的事情！今天之所以邀请你来，就是因为你打造了一套利用 Claude Code 进行视频剪辑、构建社媒影响力的全套技术栈，我必须要把它偷师过来。因为在录制之前我们还在聊，前不久我也一度在 TikTok 上小有名气，但后来作为一个内容创作者，我实在太累了。在长视频里你可以畅所欲言，但在短视频里，你得花无数个小时把“嗯”、“啊”的废话全剪掉，还要做跳剪、字幕、调音等等。所以当你发推特说“我完全用 Claude Code 剪视频”的时候，我简直疯了，心想：“这绝对不可能，不可能做到！”

<details>
<summary>Original English</summary>

**Claire Val**: Well, I love what what you do, and so we're going to talk about why I got you on this podcast, which is you have a Claude code video editing social empire building stack that I I need to steal cuz before we got on, we were talking about how a little while ago I was like on my way to being a big deal on TikTok, and then I a girl gets tired and like long form video you can talk forever, short form video you got to spend so many hours cutting out the ums and the ahs and the jump cuts and the auto captions and the and the music. And so when you tweeted, "I'm literally editing using Claude code," I lost it and I was like, "No way, no way, no way."

</details>

### 短视频痛点与终端的破局

**布鲁克 (Brooke Lacey)**: 让我先从背景说起吧。制作短视频和做直播，我已经干了很长时间了。在 Facebook 推出视频功能之前，我就已经上过电视新闻了，视频内容对我来说一点也不新鲜。但大约在2020年我进入 TikTok 时，短视频真正成为了一门挑战，而其中的关键就在于跳剪（Jump cuts）。这种剪辑难度非常大。我经常做很多搞笑内容，以前我因为对着光膀子伐木工人犯花痴这类搞笑段子而走红，后来我也聊很多科技内容。

但我从来不是一个视频剪辑师。我从来没学会过 **Final Cut Pro** 或者 **Adobe Premiere** 那些复杂的软件，甚至在很长一段时间里我都不会用 **CapCut**，因为我不喜欢在手机上操作。而且我从来记不住那些花哨的快捷键。后来我学会了用 **Descript**，但它很贵，而且每次导出视频都要在云端渲染老半天。

所以我一直在想：“到底要怎么解决这个问题？”其实很多创作者一直在尝试把这些环节拆解开。随着我越来越深入地使用终端，我意识到，终端里不仅有类似 ffmpeg 这样的强大工具，最关键的是现在的 Claude 拥有极强的推理和执行能力。我试着对 Claude 说：“你能直接帮我把这段视频剪一下吗？”它回答说：“当然可以，把文件给我。”随后它就打开视频，我当时惊呼：“什么？！”

更不可思议的是，它在分析音频时能自动识别出我说“这段剪掉”并把它剔除；如果我同一句话重复讲了两三遍，它会自动挑出语调和节奏最好的那一遍留下来。我当时坐在椅子上，这真的是过去半年里第十五、六次让我直接震惊到从椅子上滑落到地上。我整个人都懵了：“这刚才到底发生了什么？”

<details>
<summary>Original English</summary>

**Brooke Lacey**: Let me just start this. Like video short form video and like like little live stream stuff it has not I've been doing that for a long time. Like before Facebook even had, you know, video stuff, I was on the news. Like video content is not new for me. The short form was kind of a big deal when I got on Tik Tok like 2020 and the trick there is those jump cuts. They're very difficult. I do a lot of funny stuff. I was known for ogling shirtless lumberjacks and like doing some funny stuff and then also did tech stuff.

And so I'm not a video editor. I never learned Final Cut Pro or Premiere, none of that. I didn't even know CapCut for a long time cuz I don't like doing it on my phone. And shortcuts and all that, I can never remember. So I learned Descript, which is great, but it's expensive, takes forever to download and wait on, you know, their rendering.

And so I was like, "How do we do this?" And you have people kind of trying to do this. And so the more and more I worked in the terminal, the more I was like, "Wait, they're they're doing that with terminal tools and with the LLM. Why can't I just say, 'Hey, dude, cut this video?'" And then so I did, and he was like, "Yeah, give it to me." And opens the video and I'm like, "What?" And then, not only that, but it's listening and goes, "Oh, I just heard you say cut that out." And then it also was like, "You repeated this a couple of times and I took the one that was the best cadence." And I was like, "What?" "What did you do?" And I mean, sat back, this is probably the 15th or 16th time in the last 6 months that I literally like fell to the floor. Like, I'm so dramatic anyway, but I was like, "What just happened?" Like, [laughter] what?

</details>

**克莱尔 (Claire Val)**: 刚才发生的事情就是 Claude 直接掌控了视频素材并完成了剪辑！快给我们展示一下吧。我虽然也尝试过类似的做法，但你的系统显然比我好得多，今天我就坐在这里好好向你学习，快展示给我们看看！

<details>
<summary>Original English</summary>

**Claire Val**: And what just happened is Claude descended upon our videos and cut them. So, let's let's show it because I have been doing this a little bit, but I think you have a much better system than me. So, I'm just going to sit here and and learn it. So, show us.

</details>

**布鲁克 (Brooke Lacey)**: 再次说明一下，这东西之所以好玩，全靠我把它讲得绘声绘色，因为单看底层技术它其实枯燥得要命，真的很无聊！但当然，你和我都会觉得这太不可思议了，希望你的观众也会喜欢。

<details>
<summary>Original English</summary>

**Brooke Lacey**: again, it's only going to be fun because of the way I'm talking about it cuz it's really, really freaking boring. Like, it's just boring. But of course, you and I think it's amazing and hopefully your audience will too.

</details>

**克莱尔 (Claire Val)**: 必须展示！这就是我们《How I AI》的精髓。我们会让你写出的 Markdown 和 Python 代码显得无比性感和迷人，尽情展示吧！

<details>
<summary>Original English</summary>

**Claire Val**: Yes. Let's show it. This is the how AI vibe. We will make your markdown and Python look like the sexiest things on planet Earth, so show it.

</details>

### 实机演示：一行命令触发自动剪辑

**布鲁克 (Brooke Lacey)**: 太爱你了！好，我们开始。它是怎么运作的呢？我所有的工作几乎都在终端里进行，已经坚持很多年了。因为我认为在终端里可以拥有对整个系统最大程度的掌控。现在我就输入这句：“好了哥们，我准备好向观众展示奇迹了。”回车执行。

<details>
<summary>Original English</summary>

**Brooke Lacey**: I love you. Okay. Here Here we go. So, how does it work? Okay. So, literally I do everything in the terminal. I have for a long time. I I like it better. It just has way more access to everything in my opinion. So, let's say, "Okay, my dude, I'm ready to show the audience the magic." Go again.

</details>

**克莱尔 (Claire Val)**: 你是预先配置好了一个 Claude Skill 还是一个完整的 Prompt？

<details>
<summary>Original English</summary>

**Claire Val**: And did you prepopulate this with a skill or with a prompt? Oh.

</details>

**布鲁克 (Brooke Lacey)**: 瞧，完全不用碰手！好的，屏幕上这个是没有经过任何剪辑的原始素材。哎呀我真笨，抱歉，你可以看到……

<details>
<summary>Original English</summary>

**Brooke Lacey**: And look, no hands. Okay, so this one is the this one is like the non-edited. I'm so [laughter] dumb. Sorry. Okay, you can like

</details>

**克莱尔 (Claire Val)**: 这就是创作者的真实日常。

<details>
<summary>Original English</summary>

**Claire Val**: it's like to be a creator.

</details>

**布鲁克 (Brooke Lacey)**: 真不好意思。

<details>
<summary>Original English</summary>

**Brooke Lacey**: I'm so sorry.

</details>

**素材音频 (Video Audio)**: “办公室里每个人聊起 AI 时，都好像你理所当然应该已经掌握它了一样，而你只能跟着点头、微笑并点头……”

<details>
<summary>Original English</summary>

**Video Audio**: Everyone at work talks about AI as if you're already supposed to know how to use it. And you just nod along, smile and nod along.

</details>

**素材音频 (Video Audio 重复录制)**: “办公室里每个人聊起 AI 时，都好像你理所当然应该已经……”

<details>
<summary>Original English</summary>

**Video Audio**: Everyone at work talks about AI as if you're already supposed to know

</details>

**素材音频 (Video Audio 结尾)**: “这是我自己做的一个叫 **Jayla** 的应用，前三个完全免费，网址是 jayla.app，我们在里面见！”

<details>
<summary>Original English</summary>

**Video Audio**: It's an app I built called Jayla. The first three are free. It's jayla.app. I'll see you in there.

</details>

**克莱尔 (Claire Val)**: 等一下，快速暂停一下！向那些只在听音频播客而不是看视频画面的听众解释一下：Brooke 刚才只在终端敲了一句“好了哥们，咱们开始吧”，我推测这在后台调用了某种预设 Skill。等下你可以详细拆解下 Prompt 是怎么写的。紧接着，Claude 就调出了未剪辑的原始录像。大概仅仅过了4秒钟，一段剪辑极佳、符合竖屏短视频规格、完全卡准 TikTok 节奏的成品视频就呈现在了眼前！而且你自始至终没有动过鼠标！

<details>
<summary>Original English</summary>

**Claire Val**: Wait. Quick pause. Okay, so for people that are listening, not watching, she said, "Okay, my dude, let's go." I'm presuming that called some sort of skill on on the back and maybe you can walk us through exactly how the prompt works. It just pulled up the raw video and then approximately 4 seconds later there was a really well-clipped vertical short-form video, perfect to TikTok cadence. And you did it with no hands.

</details>

### 解构剪辑黑盒：TSV 时间轴与镜头景别

**布鲁克 (Brooke Lacey)**: 是的！我对他说：“给我一步步展示你正在做的事，老兄，你现在可是面对全网观众直播呢。”然后它列出了处理流程：首先分析手机一镜到底的原片——也就是我刚才给你们看的粗剪素材，如果你们能看到我的鼠标的话。

紧接着，它在时间线上放置了8处剪辑切点，这些切点完全提取自它自动生成的 **TSV**（制表符分隔值）文件。文件的每一行都包含一个片段的开始时间、结束时间、镜头景别（Shot size）以及标签。我可以把那个文件展示给你看，但其实结构很简单，每一行就是一个时间区间、景别和描述标签。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Yeah, he I said, "Walk us through what you're doing, you're live online, my guy." And it said one phone take, which is what I was telling you before, was actually the one that um that I showed you, let's just see, this one right here, if you see my mouse, that was the, you know, the rough cut. Yeah. Then place the cuts, so eight of them picked from its own TSV file. Each row is a start and end, a shot size, which I could show you that file, but it's literally just cut, you know, it's just a folder or it's it's just a Yeah. Um it's got every row has a start and end, a shot size, a label.

</details>

**布鲁克 (Brooke Lacey)**: 这意味着你只需要在终端输入文字，它就能完成所有剪辑。Claude 一直在告诉我这个理念，我才恍然大悟：“原来这个纯文本文件就代表了整部视频的剪辑工程！”

不仅如此，它还会自动插入应用界面的屏幕录屏。我直接对它说：“去把那个应用的录屏素材找出来。”顺便提一句，我那个应用现在改名了，不叫 Jayla，改叫 **Zosha** 了，因为之前名字重名我不得不改名。总之，Claude 会自动搜寻我的文件夹，找到对应的屏幕录屏，把它们裁切好，精准插入到需要展示界面的切点处。同时它还会自动完成音频清理、自动生成字幕、加入背景音乐，并且把所有这些元素合成导出！

<details>
<summary>Original English</summary>

**Brooke Lacey**: And that just means that like you can type it out and it'll edit. It Claude kept telling me that and I was like, "Okay, so the file is the whole edit." So, drop in the app screens. I literally just said, "Go find the By the way, my app is not called Jayla anymore, it's called Zosha. I had to rename it because of anyway. Um, but so go find the screen recordings, crop them, drop them in, clean the audio, add the captions, add the music, render and play. And that's what it did.

</details>

**克莱尔 (Claire Val)**: 你是否曾经问过你最喜欢的 AI 伙伴，你正在构建的东西是否足够好、足够安全、足够值得信赖？你敢完全相信它的回答吗？**Auros** 为你的团队连接了一个由超过760万名经过严格验证的人类专家组成的网络。这些专家具备你的自动化评估体系无法捕捉到的品味、判断力和细微感知。无论你是在训练大模型、微调智能体，还是将 AI 部署到高风险行业，Auros 都能提供至关重要的人类专业智能，让你可以自信地进行构建。让你的 AI 经受全球顶尖专家的严格检验，立即访问 auros.ai 开启评估。

<details>
<summary>Original English</summary>

**Claire Val**: Have you ever asked your favorite AI partner whether what you're building is good or safe or trustworthy? Did you believe what it told you? Auros connects your team to a network of over 7.6 million verified human experts. The specialists who bring the taste, judgment, and nuance your evals can't capture. Whether you're training a frontier model, fine-tuning an agent, or deploying into high-stakes industries, Auros delivers the human expertise you need to build with confidence. Put your AI to the test with the world's best minds at auros.ai.

</details>

### 短视频的剪辑法则与算法调优

**克莱尔 (Claire Val)**: 如果你只是简单对它说：“亲爱的 Claude，给我做个搞笑视频。”这绝对行不通，原因正是你刚才提到的。

<details>
<summary>Original English</summary>

**Claire Val**: Okay, just I'm like, "Dear Claude, make a funny video." And it doesn't work because of exactly what you're talking about.

</details>

**布鲁克 (Brooke Lacey)**: 没错，完全不行。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Correct.

</details>

**克莱尔 (Claire Val)**: 作为一个经常刷 TikTok 的创作者，我太有同感了。你知道我有多少次坐在剪辑软件前抓狂地调切点吗？“把这里剪掉，停在这里，这里要紧凑一点……”

<details>
<summary>Original English</summary>

**Claire Val**: I I also just have to empathize as a TikTok girly. Do you know how often I'm sitting in CapCut being like, "Cut it right like right here like

</details>

**布鲁克 (Brooke Lacey)**: 是的，就是那样。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Correct.

</details>

**克莱尔 (Claire Val)**: 因为我们凭直觉就知道什么样的节奏听起来才是好笑和吸引人的。但我希望观众能注意到的是，你实际上把“什么是优秀的短视频剪辑”做成了一套极其严谨的结构化规则：
1. 语句停顿之间的跳剪必须精确卡到字词（Clip to words）；
2. 镜头的三种构图切换：我以前只会简单地想“好笑的地方就放大镜头（Zoom in）”，但我非常喜欢你设定的广角与特写切换理念。如果大家不了解的话，在短视频里保持画面动态变化能够持续抓住观众的眼球；
3. 自动生成字幕；
4. 最关键的是，人们没有意识到这一切都可以依靠你本地电脑现有的命令行工具和文件极速运行！但我敢肯定，把这套流程调试到如此丝滑，一定花了不少心血吧？

<details>
<summary>Original English</summary>

**Claire Val**: cuz I know what funny sounds like. But just a couple things that I want people to know is you've actually really structured what a good short-form edit looks like. Jump cuts between times, clip to words. I love this idea of three frames. I was like, "Just zoom in when it's funny." But I like this idea of like frame wide and close cut because if you all don't know, keeping things moving keeps people's eyes engaged. And then uh the auto captions and what people don't understand is that can all run with existing tools and files on your computer really well. But I I have to imagine this took some zhuzhing to get right.

</details>

**布鲁克 (Brooke Lacey)**: 是的。我想对正在观看和收听节目的观众重申一点，虽然我之前说过，但我确实做视频内容很久了。我虽然不是专业剪辑师，但我之所以被迫去掌握剪辑，是因为很久以前我创办过一家企业。当时我很穷，请不起制作公司帮我做视频，所以我不得不自己拿相机拍、自己研究怎么剪。

从那时起，我就建立了一套关于“什么能吸引用户眼球”的敏锐感知。比如：不要把镜头拉得太近让大脸占满屏幕，留一点边距；要有空间感；注意画面的构图规则；节奏要利落；最重要的是，如果你在说话间隙停顿了半秒钟，用户就会立刻划走！在短视频里，哪怕仅仅半秒钟的卡顿，他们就离开你了。

所以，我在 Prompt 里不仅告诉它“帮我剪视频”，而是把这些年沉淀下来的硬核规则全写进去了：“当出现某种语义停顿时，切到特写；在句子节奏点上做快速跳剪；如果有重复的表述，对比音频能量和节奏，保留最有表现力的一版。”

<details>
<summary>Original English</summary>

**Brooke Lacey**: And I do I to tell your audience watching listening I know I said it before but video content is not new to me. So, I'm not a video editor. It was just by way of I had to do it because I was starting a business a long time ago. I didn't have money to hire a video production company, so I got the camera, I figured out how to do it.

And so I already had that visual, you know, what what catches people's eyes? Don't zoom in all the way to your nose, give it some margin, you know, do these different things. Give it some breathing room, look at the rule of thirds, keep the pacing tight. And above all, if you pause for half a second, they're gone! In short form, half a second of silence and the viewer swipes away.

So, when I wrote the instructions, I didn't just say "cut my video." I baked in all those rules: cut tightly to words, switch shot sizes between wide and tight on specific cadence shifts, and if there are duplicate takes, compare the cadence and pick the punchiest one.

</details>

### 从评论区挖掘爆款灵感

**素材音频 (Video Audio)**: “……从事科技行业25年了，我从来没有像现在这样为普通人感到担忧。一位 AI 创始人刚刚在 Twitter 上对4000万人说……”

<details>
<summary>Original English</summary>

**Video Audio**: for 25 years and I've never been this scared for people. An AI founder just told 40 million people on Twitter

</details>

**布鲁克 (Brooke Lacey)**: 这段视频里我提到的是 **Andrej Karpathy** 的那句名言，他说他现在基本上都不怎么亲自写代码了，科技的发展速度快到让人难以跟上。那段视频其实是我播放量最高的爆款之一。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Okay. So, what I'm saying in the video is that Andre Karpathy quote that it was like, you know, he doesn't um code anymore. He just like doesn't even know how to keep up. Um that was actually one of the biggest videos that I've had.

</details>

**克莱尔 (Claire Val)**: 好的，让我们为没有看画面的听众梳理一下背后的逻辑。我理解这里的整个工作流是：你在手机上把所有发布过的 TikTok 视频下载下来，放到 Google Drive 或者本地文件夹里，对吗？

<details>
<summary>Original English</summary>

**Claire Val**: Okay, yeah. So, just to walk people through if they're not watching. I think what what is happening here is you went on your phone and you downloaded all your Tik Tok videos and you put them in Google Drive or a local folder, is that right?

</details>

**布鲁克 (Brooke Lacey)**: 没错。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Correct. Cuz

</details>

**克莱尔 (Claire Val)**: 然后这些视频下面都有大量的粉丝评论，对吧？

<details>
<summary>Original English</summary>

**Claire Val**: one has all these comments, right?

</details>

**布鲁克 (Brooke Lacey)**: 没错！

<details>
<summary>Original English</summary>

**Brooke Lacey**: Yep.

</details>

**布鲁克 (Brooke Lacey)**: 比如有一条评论写道：“我想知道医院以后会不会开始用 AI 来处理医疗账单和编码？”你看，在手机 TikTok 上，你可以直接点击评论并“用视频回复”。我把这些评论数据提取出来，让 Claude 分析。我希望用这种方式抓住观众的注意力，事实证明，Claude 完全理解了这一点，而且执行得非常漂亮。

<details>
<summary>Original English</summary>

**Brooke Lacey**: And yep, and it says like, I wonder if hospitals are going to start using AI for the billing and coding. Okay, cool. Um well, on the phone, you can reply with a video. And then, you know, see, it like Is that I'm trying to get people's attention that way. Figure that out. And it it did. He did.

</details>

**克莱尔 (Claire Val)**: 我来帮大家总结一下这个超酷的闭环：除了把原视频素材下载到本地供 Claude 检索引用、结合评论生成后续视频之外，你实际上还教会了 Claude 深刻理解什么是好故事——如何铺陈引子？如何制造悬念？如何在故事中建立情绪高潮？Claude 不仅掌握了所有这些知识来优化视频剪辑点，还能反向利用这些知识为你源源不断地撰写新的短视频脚本！

<details>
<summary>Original English</summary>

**Claire Val**: So, just to kind of like repeat for people, in addition to downloading these videos, and so they can be referenced and and um combined with comments to come out videos. You actually taught Claude to understand storytelling. How do I hook people? How do I create a peak in a story? All that kind of stuff. And then it's using all that knowledge not only to make your cuts better, but also give you scripts.

</details>

**布鲁克 (Brooke Lacey)**: 没错！正如我刚刚在屏幕上展示的。我有一套标志性的视频栏目叫做《这到底是个啥》（WTF even is）。我之前经常用这种风格给不同产品做解说。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Correct, which I just brought up on the screen. And this was I you know, not to get into the whole whole story, but there's a a style of video that I do WTF even is. And I was doing it for um some companies.

</details>

### 高龄技术人的时代红利与创作哲学

**克莱尔 (Claire Val)**: 哈哈，大家请一定去点赞订阅我之前用 **Gemini** 制作数字分身的那期节目，在里面我生成了一个极其搞笑的、扮演“传统家庭主妇”（Tradwife）的 AI 版自己来录视频。所以永远别说不可能！不过这也太强大了。

<details>
<summary>Original English</summary>

**Claire Val**: I mean, please please like and subscribe to my create your digital avatar with Gemini episode where I created very hilarious uh tradwife AI versions of myself and do videos. Uh so, never say never, but this is so cool.

</details>

**布鲁克 (Brooke Lacey)**: 听到这里大家可别生气，其实我现在的更新频率并不高，但我依然拥有粘性极高、互动极其热烈的粉丝群体。因为前几年我已经打下了非常扎实的基础，付出了很多努力，很多优质内容至今仍在持续带来长尾流量。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Okay, so don't be mad, but I don't really have to post that often to still have a really good engaged audience. Um I did the work. I put in the work for quite a few years, and a lot of my content still performs.

</details>

**克莱尔 (Claire Val)**: 你甚至都不需要亲自动手剪辑了。

<details>
<summary>Original English</summary>

**Claire Val**: You don't even know.

</details>

**布鲁克 (Brooke Lacey)**: 哈哈，因为我现在把这些脏活累活全甩给 Claude 搞定了！

<details>
<summary>Original English</summary>

**Brooke Lacey**: know how I don't [laughter] cuz I just do this. Claude's business.

</details>

**克莱尔 (Claire Val)**: Brooke，作为一个平时做长视频内容、极度想重返短视频领域但苦于没有大把时间耗在剪辑上的创作者，我发誓我一定要把你的整套方法全偷学过来！顺便说一句，我也想向更有资历、更有经验的资深技术专家们呼吁：请多来这些新平台上分享你们的真知灼见吧！我们非常需要这种“老练深刻的阅历”与短视频“放手一搏（YOLO）的活力”碰撞在一起的化学反应。

<details>
<summary>Original English</summary>

**Claire Val**: Um, Brooke, I love this as a as a creator um who does long form that like needs to get back in short form but it just doesn't have the hours to do editing. I'm going to go steal all of this. I would like to make a plea for more experienced technologists to share their knowledge on these new platforms, pretty please. We need that combination of like wizened experience and yolo energy, especially right now.

</details>

**布鲁克 (Brooke Lacey)**: 我非常乐意！我已经年过五十了，刚刚满50岁。我经历过个人电脑普及、互联网兴起、移动互联网爆发，当年大家甚至担心“烤面包机会不会突然联网攻击人类”。而现在大家都在担忧 AI。因为见证过一次又一次的技术浪潮更迭，当 AI 浪潮来临时，我毫不犹豫：“我加入！我全盘拥抱！这绝对会像之前的技术一样彻底改变我的生活。”所以朋友们，赶紧跳进来吧，这里的水正暖和呢！

<details>
<summary>Original English</summary>

**Brooke Lacey**: I'm happily in my 50s. All right, just 50. [laughter] Just turned 50. Yeah. Oh, I love this and I wish we had hours and hours and maybe you'll have me back. Everyone's worried about AI. Well, back then we were worried about toasters! And so you know I had the same experience as you which is I have seen technology shift after technology shift. So this one happened I was like I see it. I'm in. I'm in. It is going to change my life like these previous ones have. And so, um jump on in. Water's warm.

</details>

### 如何驯服你的 AI：系统级指令与角色设定

**克莱尔 (Claire Val)**: 最后一个问题：在你的心目中，你把 Claude 当作一个“男孩子”，这很有意思。但当他在终端里表现不佳、掉链子、没有按你的预期产出结果时，你通常会如何 Prompt 他？

<details>
<summary>Original English</summary>

**Claire Val**: Okay, last question. You're you're so lovely. And I like that Claude is a boy for you. That's very nice. When he is a disappointment, when he's not doing what you want, how do you prompt him?

</details>

**布鲁克 (Brooke Lacey)**: 这也是一个很长的故事，但我尽量简明扼要地讲。前几天有人写了一篇关于他们 Prompt 架构的文章，起名叫什么“香蕉”之类的，我记不清了，好像叫 Petunia。我把它拿来跟我自己搭建的操作系统做了对比。

我和我的 Claude 共同开发了一套名为 **Lane OS** 的工作系统，它深度整合在我的系统配置和各种指令别名中。在这个系统里，Claude 拥有极其清晰的角色定义。

当他犯蠢或者偏离轨道时，我绝对不会客客气气地说“请帮我修改一下”。我会在终端里直接大喝一声：“**兄弟，集中注意力！**（Dude, pay attention!）”或者直接质问他：“你到底在搞什么鬼？看看你刚才输出的那堆东西，立刻给我退回去，按照我们第一阶段制定的规则重新跑一遍！”相信我，当你给予他非常具体、严厉且边界清晰的上下文修正时，他会立刻重新进入状态，精准完成任务。

<details>
<summary>Original English</summary>

**Brooke Lacey**: Okay, so also [clears throat] a very long story, but I will keep it concise. The Grok Bot person wrote an article the other day about their P stack. I can't remember the name. It was like banana something. Her [laughter] was it was Petunia or something. Um and I ran it against my OS. So, what I built a while ago with my dear Claude is this lane operating system that is really built into my dotfiles and aliases.

And so when he's messing up, I don't sit there and be polite like "could you please fix this?" I literally go into the terminal and go, "Dude, pay attention! What are you doing? Look at what you just output. Go back and re-read the stage one spec and run it again." And he immediately snaps back into line and gets it right.

</details>

**克莱尔 (Claire Val)**: 太棒了！今天这期对话太开心了，观众一定能感受到我们聊得多尽兴。Brooke，大家可以在哪里关注你，我们怎样才能支持你的项目？

<details>
<summary>Original English</summary>

**Claire Val**: I love it. I love it. Brooke, this has been I don't know if the audience can tell we're having a good time. We're having a good time today. This has been a good one. Um where can we find you and how can we be helpful?

</details>

**布鲁克 (Brooke Lacey)**: 在各大社交平台上都可以通过 **@BrookeJLacey** 找到我。TikTok 是我最主要的阵地，上面有很多能让你开怀大笑的内容。另外我在 Twitter 上也非常活跃。同时欢迎大家体验我打造的一款名为 **Zosha** 的移动端 AI 学习应用，它完全免费，让你在手机上就能轻松掌握 AI。

<details>
<summary>Original English</summary>

**Brooke Lacey**: I am at Brooke J. Lacey on every platform. I've been around a long time. Um Tik Tok is definitely my biggest audience. There's a lot of funny stuff that hopefully makes you laugh. I am a lot more on Twitter and I have a really cool app called Zosha that I built and it's just learning AI and you're kind of doing it on your phone and it's free.

</details>

**克莱尔 (Claire Val)**: 太精彩了。感谢你做客《How I AI》！

<details>
<summary>Original English</summary>

**Claire Val**: Amazing. Well, thank you for joining How I AI.

</details>

**布鲁克 (Brooke Lacey)**: 感谢你的邀请！

<details>
<summary>Original English</summary>

**Brooke Lacey**: Thank you for having me.

</details>

**克莱尔 (Claire Val)**: 非常感谢大家的收看。如果你喜欢本期节目，请在 YouTube 上点赞、订阅，更欢迎在评论区留下你的思考与心得。你也可以在 Apple Podcasts、Spotify 或任何你常用的播客平台收听本节目。请考虑为我们留下评分和好评，这能帮助更多人发现这个节目。访问 howiaipod.com 可以查看过往所有节目并获取更多资讯。我们下期再见！

<details>
<summary>Original English</summary>

**Claire Val**: Thanks so much for watching. If you enjoyed the show, please like and subscribe here on YouTube or even better leave us a comment with your thoughts. You can also find this podcast on Apple Podcasts, Spotify, or your favorite podcast app. Please consider leaving us a rating and review which will help others find the show. You can see all our episodes and learn more about the show at howiaipod.com. See you next time.

</details>