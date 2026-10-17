---
author: All-In Podcast
date: '2026-06-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=gH4FTjDm9FQ
speaker: All-In Podcast
tags:
  - ai-safety
  - model-governance
  - political-elections
title: Anthropic Fable 模型反弹、AI 治理、加州选举与选票收集争议
summary: 本期播客讨论了 Anthropic 最新模型 Fable 5 的发布及其引发的隐私和数据使用争议，探讨了企业级 AI 模型审查和单点故障风险。随后，内容转向了加州地方选举中的拉票策略与政治操作。
insight: ''
draft: true
series: ''
category: ai-ml
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
  - Palo Alto Networks
products_models:
  - Fable 5
  - Opus
media_books: []
status: evergreen
---
### Anthropic 的 Fable 模型与隐私争议

**[Host]**: 各位好。欢迎回到世界排名第一的播客。这是你们最爱的播客，也是你们的播客主最爱的播客。这是那个所有人都喜欢抄袭 50 集然后就放弃的播客。但 All-In 播客不会放弃。我们与最初的四人组一起加倍努力。这周大家都在，有非常多重要的辩论，我们必须从 **Anthropic** 开始。

**Anthropic** 发布了一个神话级别的模型，带有一些有趣的护栏，并且看起来 Daario 又开始写博客了。好的，这个模型叫做 **Fable 5**。不知道他们为什么要叫这个名字，它在周二发布，并在几乎所有的基准测试中拔得头筹。然而，它的 token 成本是 **Opus** 的 4.8 倍，但总体来说它使用的 token 应该会更少，因为理论上它确实好得多。

目前还不清楚这是否能缓解一些关于 token 成本的担忧，但你们还记得在四月份，**Anthropic** 著名的没有发布神话模型，因为公开来说，它具有很强的黑客能力。所以他们把它交给了几个人，我们有 Palo Alto Networks 的 CEO Nesh，他说：“嘿，神话模型是真材实料。”并且他们用它来修复了他们内部的一些漏洞。显然，这个新模型对生物武器、黑客攻击等话题很敏感，这些都在其中被封锁了。但他们遭到了开发者的强烈抵制，我解释完这个之后再听听你们的反馈。

在使用 **Fable** 时，**Anthropic** 会把你输入的所有提示词数据至少保存 30 天。所以这有点隐私问题。而且如果 **Fable 5** 检测到你在做前沿 AI 研究，换句话说，使用他们的模型来制造一个更好、更有竞争力的模型，他们就会给你降级，但他们并没有告诉你。这被深深埋在了一份 319 页的文件里。所以这在 X 上引起了轩然大波和恐慌，但他们后来在 Wired 上稍稍收回了这一做法。他们说：“我们正在改变 **Fable 5** 针对前沿 LLM 开发的护栏，使其变得更加可见。”

我就说到这里。Chamath，你对 **Anthropic** 和他们不断发布的这些非凡模型有什么看法？以及他们是如何处理这些模型的发布的？他们是考虑周全，还是小题大做？还是两者兼有？你站在哪一边？你知道，在听了 Nesh 的反馈并看到最新模型发布之后，你玩过它了吗？8090 和软件工厂在对它进行基准测试方面进展如何？

<details>
<summary>Original English</summary>

**[Host]**: All right, everybody. Welcome back to the number one podcast in the world. It's your favorite podcast. It's your podcasters' favorite podcast. It's the podcast that everybody likes to rip off for 50 episodes and then they quit. But the All-In podcast is not quitting. We're doubling down with the original quartet. Everybody's here for a big big week, lots of debates, and we got to start with Anthropic. 

Anthropic released a mythos level model with some interesting guardrails and uh seems as though Daario is back to blogging. Okay, the model's called Fable 5. No idea why they're calling it that or released on Tuesday and it tops every benchmark nearly every benchmark. The tokens, however, cost twice as much as Opus 4.8, but it should use less tokens overall because it's theoretically that much better. 

Unclear if this is going to alleviate some of the hand ringing around the cost of tokens, but you remember in April Anthropic famously did not release Mythos because publicly uh it had some strong hacking capabilities. So they gave it to some folks and we had um the CEO of Nesh of Palo Alto Networks who said, "Hey, Mythos was the real deal." and that they used it to seal up some vulnerabilities inside their shop. Obviously, this new model is sensitive uh to topics like boweapons, hacking, all that stuff are blocked in it. But they got a big developer backlash and then I'll get your feedback after I explain this. 

While using Fable, Anthropic stores all the prompt data you enter for at least 30 days. And so that's a bit of a privacy issue. And if Fable 5 detects you're doing frontier AI research, in other words, using their model to make a better model, competitive model, they were downgrading you, but they weren't telling you. And this was buried deep in a 319 page document. So many kuruffles, freakouts going on on X over this, but they've since walked it back a bit, quote unquote, in Wired. We're changing Fable 5 safeguards for Frontier LLM development to make them more visible. 

I'm going to stop there. Chimath, what's your take on anthropic and these extraordinary models? They keep dropping and how they're handling the release of them. Are they being thoughtful? Are they being dramatic and drama queens? A little bit of both. Where do you stand on it? You know, after getting Nesh's feedback and seeing the latest model come out, have you played with it? What's going on at 8090 and the software factory in terms of benchmarking it as well?

</details>

### AI 模型审查与企业治理风险

**[Chamath]**: 这是一个非常不可思议的模型，所以要称赞这些人，他们不断推动闭源前沿实验室模型的边界。他们现在是火力全开。我认为它现在带来了一个非常明显的风险，我认为这个明显的风险是双重的。首先是 **Anthropic** 已经基本上亮出了他们的底牌，也就是他们将越来越多地接收提示词，评估这些提示词，并决定如何处理它们，然后再向你生成输出。

我认为如果你是一个个人，你现在应该普遍认为存在审查的风险。如果你是一家公司，我认为这几乎是不可接受的。原因是因为你可能会在不知不觉中触发这些机制中的某一个。下游使用云 API 的科学家可能会触发它。你公司内部的业务主管可能会触发它。做科学分子研究的人可能会触发它。然后突然之间，你就会被切断，失去对你来说非常重要的业务差异化来源。

所以我认为如果你把这两件事放在一起看，我们现在处于一个非常独特的历史时刻，我认为公司需要开始为 AI 的下一阶段做准备，那就是我如何获得控制权？我允许谁来从所有这些信息中学习？我是否希望在 AI 方面存在单点故障风险？我认为答案是你需要广泛的多样性和一种管理得更好的治理方法。

<details>
<summary>Original English</summary>

**[Chamath]**: It's a really incredible model and so kudos to these guys for continuing to push the boundaries of the closed frontier lab models. They're firing on all cylinders. I think that it creates a pretty obvious risk now and I think that obvious risk is twofold. One is Anthropic has essentially shown their hand which is that they will increasingly take in prompts, evaluate the prompts and decide what to do with them before they generate output to you. 

And I think if you were a person, you should generally now think there's a risk of censorship. If you're a company, I think it's almost a non-starter. And the reason is because you could accidentally trip one of these things without even knowing it. A downstream scientist using the cloud APIs could trip it. A business executive inside your corporation could trip it. A person doing scientific molecular research could trip it. And all of a sudden, you'll get cut off from a very important source of business differentiation for yourself. 

So I think if you take both of those two things together, we're at this very unique moment in time where I think companies need to start underwriting this next phase of AI, which is how do I have control? Who am I allowing to learn off of all of this information? Do I want to have single point of failure risk with respect to AI? And I think the answer is that you need broad diversity and a governance approach that's better managed.

</details>

**[Host]**: 关于 **Anthropic** 我想说的一点是，他们会说实话。

<details>
<summary>Original English</summary>

**[Host]**: One thing I'll say about anthropic is they tell the truth.

</details>

**[Chamath]**: 是的。

<details>
<summary>Original English</summary>

**[Chamath]**: Yes.

</details>

**[Host]**: 只是当真相摆在面前，你真的接受并消化它时，真相会让人觉得很糟糕，它就像在你的肚子里翻江倒海，你会觉得“不，这不好。我不喜欢这个”。因此，一方面存在审查风险，另一方面企业面临的治理和业务风险也是如此。两者都不好。

Freeberg 现在正在经营你自己的公司。呃，我会让你在这里收尾。Saxs，显然你会有很多话要说，但是 Freeberg，在经营你的公司时，你是否担心被这些公司中的某一家给“扯地毯”（坑了），把你的时间投入到这些平台之一，然后让他们限制你的使用，或者拿着你在俄亥俄州做的事情，把它放到他们的模型中，然后提供给其他人使用？作为一位在行业前沿使用这些工具的企业主，你有什么担忧？

<details>
<summary>Original English</summary>

**[Host]**: It's just that the truth sucks when you actually take it and you eat it and you're like it's in your tummy and you're like no this is not good. I don't like this. And so there's the censorship risk on the one hand and then there's just the governance business risk for enterprises on the other. Both are not good. 

Freeberg running your own company now. Uh, and I'll let you back clean up here. Saxs, obviously you'll have a lot to say, but Freeberg, running your company, do you worry about getting rugpulled by one of these companies, investing your time into one of these platforms, having them then constrain your use of it and or take what you're doing at Ohio, put it into their model and make it available to other people. What concerns do you have as a business owner at the forefront of your field using these tools?

</details>

**[Freeberg]**: 这是一个很好的问题。服务条款非常清楚，他们不能拿你正在做的事情放到他们的模型里，他们不会这么做的。

<details>
<summary>Original English</summary>

**[Freeberg]**: It's a great question. the the terms of service is pretty clear that they can't take what you're doing and put it into their model that they won't 

</details>

**[Host]**: 当你读到那些条款时，你相信他们吗？

<details>
<summary>Original English</summary>

**[Host]**: do you believe them when you read that I 

</details>

**[Freeberg]**: 我不确定。我认为你需要严谨一些。

<details>
<summary>Original English</summary>

**[Freeberg]**: I'm not sure to a minute myself. I because I I think you do need to be rigorous.

</details>

### 加州选举的拉票机器与策略

**[Speaker A]**: 你先说。是的。我唯一能想到的是她的地面运作更加成熟，因为他们比 Spencer Pratt 做的更久，而他没有这种地面运作机制，因为他是一个非传统的首次参选候选人。这是我唯一能想到的事情。

<details>
<summary>Original English</summary>

**[Speaker A]**: You go ahead first. Yeah. The the only thing I can think of is her ground game is more sophisticated because they've been at it longer than Spencer Pratt and he didn't have a ground game that took this in since he's a non-traditional firsttime candidate. That's the only thing I can think of.

</details>

**[Speaker B]**: “成熟”只是一个暗语，意思是说他没有去贿赂 Skid Row 的流浪汉。

<details>
<summary>Original English</summary>

**[Speaker B]**: Sophisticated a coded word for he wasn't bribing Skidro homeless judge.

</details>

**[Speaker A]**: 不，他只是拥有这个。他没有一个选举机器去收集选票，而收集选票是合法的。这就是问题所在。

<details>
<summary>Original English</summary>

**[Speaker A]**: No, he just has it. He doesn't have an election machine to collect ballots and collecting ballots is legal. That's the That's the question.

</details>

**[Speaker B]**: 她有一个更好的作弊操作。显然，

<details>
<summary>Original English</summary>

**[Speaker B]**: She had a better cheating operation. Obviously,

</details>

**[Speaker A]**: 我们说的是同一件事。我们其实没有说任何不同的东西。

<details>
<summary>Original English</summary>

**[Speaker A]**: we're saying the same thing. We're not actually saying anything different.

</details>

**[Speaker C]**: Twitter 上的评论是，人们在等待，因为有太多人非常反对 Spencer Pratt，但他们想确保自己把票投给了正确的候选人，不管是 Ramen 还是 Bass。所以那些把选票保留最久的人看到了民调数据，显示 Bass 会赢。这就是为什么他们都在最后一刻把票投给 Ramen，试图提升她，以确保...

<details>
<summary>Original English</summary>

**[Speaker C]**: The Twitter commentary was that people were waiting because there's so many people that are so against Spencer Pratt, but they wanted to be sure that they voted for the right candidate, whether it's Ramen or Bass. And so the people that held their ballots the longest saw the polling data that Bass was going to win. That's why they all voted for Ramen last minute was to try and promote her to make sure

</details>

**[Speaker A]**: ...被安排了，因为你可以有两个民主党人占据选票的头两名。

<details>
<summary>Original English</summary>

**[Speaker A]**: has been shipped because of the you could have two Democrats at the top of the ticket.

</details>

**[Speaker C]**: 没错。他们不想让 Spencer Pratt 有机会进入大选。顺便说一下，你知道，我的意思是，如果你看了我对 Spencer Pratt 的采访，他说 Ramen 在截止日期前一小时注册，而且她是 Bass 的朋友，整个目的就是为了阻止他真正进入大选名单。所以人们在脑海中做的一些协调就像是，我们必须确保把票投给这两位民主党人，然后他们会弄清楚，嘿，这有问题吗？让我们直接把他挡在外面。

<details>
<summary>Original English</summary>

**[Speaker C]**: That's right. And they didn't want Spencer Pratt to have a shot at the general. And that by the way, you know, I mean, if you saw my interview with Spencer Pratt, he said Ramen registered one hour before the deadline and she's friends with Bass and that the whole point was to keep him from actually making it onto the general ballot. So that some of the coordination that people were making in their minds was like, we got to make sure we vote for the two Democrats and then they'll figure out, hey, is it wrong? Let's just box him out.

</details>

**[Speaker B]**: 是的。

<details>
<summary>Original English</summary>

**[Speaker B]**: Yeah.

</details>

**[Speaker A]**: 明白了。这就是为什么他们都等到最后一刻才投票。

<details>
<summary>Original English</summary>

**[Speaker A]**: Got it. Which is like why they all waited till the last minute to vote for to vote for

</details>

**[Speaker B]**: 你怎么协调这样的事情呢？这总是我对这些事情的疑问... 

<details>
<summary>Original English</summary>

**[Speaker B]**: how do you coordinate something like that? That that's always the question I have with these like

</details>

**[Speaker C]**: 这些人都是绝顶天才。这是成千上万绝顶天才搞出来的。

<details>
<summary>Original English</summary>

**[Speaker C]**: these people are all brilliant geniuses. It's it's hundreds of thousands of brilliant geniuses row that out.

</details>

**[Speaker B]**: 是的，有个聊天群。我的意思是，这并不复杂。

<details>
<summary>Original English</summary>

**[Speaker B]**: Yeah, there's a chat group. I mean, it's not that complicated.

</details>

**[Speaker A]**: 选票收集者做到了。Freeberg 刚才说的确实发生了。只不过是选票收集者做的，显然不是真正的选民。

<details>
<summary>Original English</summary>

**[Speaker A]**: Alan Harvesters did it. what Freeberg said just happened. It's just that the ballot harvesters did it, not the actual voters, obviously.

</details>

**[Speaker B]**: 选票收集是合法的，但这很可疑，也许如果这里面有选票收集者，我认为特朗普和司法部能抓住这些人。怎么可能有人出去收集别人的选票，填好后再寄出去是合法的？这对我来说太疯狂了。

<details>
<summary>Original English</summary>

**[Speaker B]**: And ballot harvesting is legal, but it's sketchy and maybe they And if there are ballot harvesters, I think that Trump and the DOJ can catch these people. How the is it legal that someone can go out and collect other people's ballots and fill them out and send them in? It's the craziest to me.

</details>

**[Speaker C]**: 目前没有欺诈的证据。统计数据看起来不太好。唐纳德·J·特朗普，你控制着司法部。去调查一下吧。

<details>
<summary>Original English</summary>

**[Speaker C]**: No evidence of fraud right now. Statistics don't look good. Donald J. Trump, you control the Department of Justice. Go investigate it.

</details>

### 尾声

**[Speaker B]**: 好的。我爱你们大家，但我饿了。我得走了。这真是一集精彩的 All-In 播客。拜拜。

<details>
<summary>Original English</summary>

**[Speaker B]**: Okay. I love you guys, but I'm hungry. I got to go. This has been an amazing episode of the Allin Podcast. Bye-bye.

</details>

**[Speaker C]**: 爱你们兄弟们。拜拜。让你们的赢家继续飞奔。

<details>
<summary>Original English</summary>

**[Speaker C]**: Love you boys. Byebye. Let your winners ride.

</details>

**[Speaker A]**: 我们把它开源给了粉丝们，他们玩得简直要疯了。兄弟们走了。那是我家狗在你车道上做记号呢。哦老兄，我的裁缝会把我打扮好的。我们应该直接开个房，然后来一场大群P，因为他们都没用。就像这种性张力，我们需要以某种方式释放出来。让你的脚沾点水。我们需要让 Mercy 全力以赴。我要全力以赴。

<details>
<summary>Original English</summary>

**[Speaker A]**: We open sourced it to the fans and they've just gone crazy with it. Besties are gone. That is my dog taking a notice in your driveway. Oh man, my habitasher will meet me up. We should all just get a room and just have one big huge orgy cuz they're all just useless. It's like this like sexual tension that we just need to release somehow. Wet your wet feet. We need to get Mercy's going all in. I'm going all in.

</details>