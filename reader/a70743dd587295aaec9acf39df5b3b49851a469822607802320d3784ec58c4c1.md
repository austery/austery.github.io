---
author: AI Engineer
date: '2026-11-17'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=9RKrSF9d2SE
speaker: AI Engineer
tags:
  - llm
  - coding-agent
  - software-engineering
  - benchmark
title: 大语言模型的2026年回顾：三大拐点与编程Agent的演进
summary: 演讲者回顾了过去12个月大语言模型领域的发展，总结出三大关键拐点：编码Agent的日常实用化、能够暴力破解复杂目标的Fable级别模型出现，以及AI驱动游戏制作的质变。同时探讨了开发者面对AI能力提升所经历的心理冲击与工作状态的变化。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people:
  - Simon Willison
  - Jeff Dean
  - Sundar Pichai
  - Greg LeMond
companies_orgs:
  - Anthropic
  - OpenAI
  - Google
  - Hugging Face
  - Meta
products_models:
  - Claude Code
  - Claude Opus 4.5
  - Claude Opus 5.5
  - Claude Mythos
  - Claude Fable
  - GPT-5.1
  - GPT-5.6
  - GPT-6 Astra
  - Gemini 3.1 Pro
  - Gemini 4 Carbon
media_books: []
status: evergreen
---
### 开场与过去12个月的三大拐点

[音乐]

>> 你们好，AI 工程师代码峰会的各位。很高兴来到这里。我要讲的内容非常多。我有 18 分钟的时间来谈谈过去 12 个月大语言模型的发展。我的幻灯片放出来了吗？放出来了。那我们就直接开始吧。我想通过过去 12 个月中经历的三个拐点，来回顾这 12 个月的 LLM 历程。
<details>
<summary>Original English</summary>
[music]

>> Hello AI Engineer Code Summits. Um it's great to be here. Um I have a lot to cover. I've got 18 minutes to talk about the last 12 months in LLMs. Are my slides up? My slides are up. Let's just let's just get get going. I want to talk about the last 12 months in LLMs through the perspective of three inflection points that we've had over the past 12 months.
</details>

### 第一个拐点：编码 Agent 走向日常实用化

巧合的是，第一个拐点正好发生在 12 个月前。我认为 2025 年 11 月正是编码 Agent 的拐点。编码 Agent 并不是新鲜事物。我们从去年二月就有了 Claude Code，Codex 也很早就存在了，所以这并不是一个完全崭新的软件类别。但在 12 个月前，随着两个模型的出现，情况发生了变化。我们迎来了 Claude Opus 4.5 和 GPT 5.1，它们在驱动编码 Agent 方面稍微好了一点点，而正是这一点点进步，让它们跨越了门槛，突然变成了你可以每天使用的工具。
<details>
<summary>Original English</summary>
Um and the first of those conveniently was exactly 12 months ago, like November 2025 is what I consider the coding agent inflection point. Coding agents weren't new. We'd had Claude Code since February last year. Codex had been around, you know, this wasn't a complete new category of software, but something changed 12 months ago with these two models. We had Claude Opus 4.5 and GPT 5.1 and they were just a little bit better at driving a coding agent which put them over that thing where these suddenly these were tools you could use on a daily basis.
</details>

我们经历了一场转变：编码 Agent 从偶尔摆弄一下、随后总会犯些离奇错误的新奇玩物，变成了足够可靠、可以每天使用的工具。这恰好发生在 11 月，是一件很棒的事，因为我们整个 12 月基本上都在利用假期摆弄这些新模型和新事物，弄清楚它们能做些什么。到了 1 月，我们当中的许多人都意识到，某些东西已经变了，而这将会是 2026 年的核心主题。
<details>
<summary>Original English</summary>
Like we went from coding agents as a novelty that you'd poke at occasionally and then make some weird mistakes to something that was reliable enough that you could use them every day. It was convenient that that happened in November because we then got to spend December basically over the holidays sort of poking at these new models and these new things and figuring what they could do. And by January, a lot of us had realized that something had changed and this was going to be the big theme for 2026.
</details>

### 鹈鹕基准测试与新年愿望

我喜欢通过让模型绘制骑自行车的鹈鹕的 SVG 来评估它们。这是 12 个月前的顶尖水平。这是 Claude Opus 画的鹈鹕，这是 GPT 5.1 画的鹈鹕。你会注意到，这两辆自行车其实都无法正常骑行。所以这里显然还有改进的空间。它们当时写代码非常在行，但绘制 SVG 还不算太好，不过我们就是这样开启这一年的。
<details>
<summary>Original English</summary>
I like evaluating models by having them draw SVGs of pelicans riding bicycles. This is the state of the art 12 months ago. This is Claude Opus's pelican and GPT 5.1's pelican. You'll notice that neither of these bicycles actually works. So there was definitely room for improvement here. They were really good at writing code. They weren't great at SVGs just yet, but but this is how we started the year.
</details>

每年一月，我都会给自己定一个新年目标，而且每年都是完全一样的内容。每年我都告诉自己，今年我要少接新项目，我要保持专注。我要把精力集中在手头已经要做的事情上。但这从来没起过作用。所以今年我改变了做法，我说：知道吗？我要更有野心一点。我想接多少项目就接多少项目，因为我们现在有了这些 Agent。它们能把事情办妥。就让我们试着去挑战极限，看看能做成些什么。结果到了现在的 11 月，我手头上同时在应对的事情太多了。这甚至有点吓人，明年的野心我可能得往回调调了。但那确实是我这一年的主题。而且我认为这也是本次大会的主题：既然我们拥有了所有这些新工具，那就变得更加雄心勃勃吧。
<details>
<summary>Original English</summary>
So every year in January, I set myself a New Year's resolution and every year it is the exact same thing. Every year I tell myself that this year I'm going to take on less new projects and I'm going to focus. I'm going to focus the stuff that I've already got to do. And this has never worked. So this year, I changed it and I said, you know what? I'm going to be more ambitious. s I'm going to take on as many projects as I want to because we've got these agents. They can do stuff. Let's just try and push the limits and see what we can get done. As a result, now it's November and I am juggling so many plates right now. It's kind of horrifying and I may need to reset my ambitions for next year. But that was my sort of theme of the year. And I think it's the theme of this conference is to be more ambitious now that we have all of these new tools.
</details>

### 2026 年预测与 Deep Blue 危机

我还参加了一个播客节目，他们在节目里让我对 2026 年的 LLM 做些预测。我在一月份做的预测，首先是：LLM 能写出优秀的代码将变得毋庸置疑，不仅是能写代码，而是能写出好代码。因为早在今年一月，还有很多人认为它们写的代码全都是垃圾，每行代码都必须亲自审查。然后，类似的话我已经说了大概四年了：我们迟早会迎来一场由提示注入引发的“挑战者号”级别灾难，也就是某个由提示注入攻击引发的事件登上报纸头版。我当时坚信今年会发生，尽管前年和大前年都并没有出现。
<details>
<summary>Original English</summary>
I also went on a podcast where they asked me to get make some predictions for 2026 in LLMs. Um my predictions back in January were, firstly, it will become undeniable that LLMs write good code, not just code, but good code. Because back in January, there were a lot of people who thought that the code was all complete trash and, you know, you'd have to review every single line of it. Um I've been saying this every year for like four years now. We're due a prompt injection challenger disaster, like some some incident caused by a prompt injection attack which makes the front pages of newspapers. I was convinced that this would be the year, even though it hadn't been the year the year before or the year before the year before that.
</details>

另外，我还预测了鸮鹦鹉会在 2026 年迎来一个极其出色的繁殖季。这是鸮鹦鹉。它们是一种来自新西兰的夜行性、不会飞行的鹦鹉。今年一月的时候，全世界仅存 235 只。它们只在陆均松树迎来结果大年时才会繁殖，而这已经有好几年没发生过了。但是在今年一月，陆均松的长势看起来非常好，结出了大量的果实。所以基于这一点我想着：说不定今年我们真能迎来一次鸮鹦鹉的大繁衍。同时在那个播客中，我们还创造了一个新词汇。我们用“Deep Blue”来形容那种 AI 引发的生存危机感——一旦你意识到作为软件开发者让你显得独特的一切特质，这些模型也同样能做到，而且做得更快，有时甚至做得更好，大家心中就会油然而生这种感受。在整个 2026 年期间，这种情绪在我们行业以及其他行业也确实越来越普遍。
<details>
<summary>Original English</summary>
And um I also predicted that Kakapo parrots will have an outstanding breeding season in 2026. Um this is a Kakapo parrot. They are a New Zealand nocturnal flightless parrot. There were only 235 of them in the world back in January. Um but they only breed when the rimu trees have a masting fruit season, which hadn't happened in years. But the rimu trees were looking really good in January. There was there was a lot of fruit coming out. So based on that, I thought, you know, maybe this is the year that we get our Kakapo breeding explosion. And also on that podcast, we coined a new term. We coined the term deep blue to describe the AI-induced existential crisis that everyone starts to feel once you realize that all of the things that make you special as a software developer, these models can do those things too and they can do them faster and sometimes they can even do them better. And this has definitely been a growing sensation across our industry and other industries over the course of 2026 as well.
</details>

### 二月的进展与被攻破的基准

时间快进到二月。二月份，Google 发布了 Gemini 3.1 Pro。看看那只骑自行车的鹈鹕。那可是一辆货真价实的自行车。自行车的结构比例完全正确。上面还有一条小鱼，还戴着一顶帽子。这绝对是我见过的所有模型画出的最优秀的鹈鹕。
<details>
<summary>Original English</summary>
Let's jump forward to February. In February, Google released Gemini 3.1 Pro. And look at that pelican riding a bicycle. Like that's a real bicycle. That bicycle's the right shape. It's got a little fish. It's got a hat on. This was by far the best pelican I'd ever seen out of any model.
</details>

而我之前给各家实验室设过一个陷阱。大家一直问我：如果实验室专门针对“骑自行车的鹈鹕”做训练怎么办？我一贯的回答是：如果他们真这么做，我一眼就能识破，因为我会换成要求画“踩独轮车的火烈鸟”。当有人能画出一只绝妙的鹈鹕却画出一只糟糕透顶的火烈鸟时，我就知道他们在作弊。遗憾的是，Google 的 Jeff Dean 在他们发布该模型的当天发了一条推特视频，他在视频中展示：我们不仅有骑自行车的鹈鹕，还有青蛙在踩着——不管那是啥玩意儿，还有长颈鹿开着一辆小微型车，踩轮滑鞋的火烈鸟，玩脚尖翻板的乌龟，以及坐在加长礼车里的腊肠犬。所以他们完全击败了我，对吧？他们针对所有动物搭配所有交通工具的形式全做了训练，这确实让我的基准测试大大削弱了。不过二月份也传来了好消息。在二月的情人节那天，四年来第一只鸮鹦鹉幼崽破壳而出了。在情人节那天，因为我们已经有大约四年没等到陆均松结果了，这是我们四年来迎来的第一只这种稀有且奇特的新西兰鹦鹉宝宝。这真的很棒。所以我的基准测试遭受了重创，但鸮鹦鹉过得挺不错。
<details>
<summary>Original English</summary>
And this I I had set a trap for the labs. I was Everyone's always asked me what happens if the labs train for the pelican riding a bicycle. My answer has always been if they do that, I will catch them because I asked for a flamingo and a unicycle. And when somebody produces a great pelican and a terrible flamingo, I'll know that they've been cheating. Unfortunately, Google's Jeff Dean tweeted this video the day they launched that model um where he showed that we've got a pelican riding a bicycle, but we've also got a frog on a whatever that thing is and a giraffe and a little tiny car, a flamingo on roller skates, a kick-flipping turtle, and that's a dachshund in a stretch limo. So they'd beaten me, right? They had They had They have trained for all forms of animals in all forms of transport, which does sort of sort of weaken my benchmark quite a little bit. Um but there was some good news in February. In February, the first kakapo chick in four years hatched on Valentine's Day. On Valentine's Day, because we hadn't had the rimu fruit in like four years, this was the first one of these baby rare weird New Zealand parrots that we'd had in four years. So that was nice. Um so my my benchmark was was was greatly injured, but the kakapo are doing okay.
</details>

### 四月与 Claude Mythos 事件

直接跳到四月。四月份，Anthropic 发布了一个他们实际上并没有公开的模型。他们宣布了 Claude Mythos，并表示这个模型对我们来说太危险了，无法对外发布。它具备全新的网络安全能力，我们还没准备好向全世界分享。我们会与受信任的合作伙伴分享。他们其实提到过：Mythos 预览版已经发现了数千个高危漏洞，其中包括在各大主流操作系统和网络浏览器中发现的漏洞。很多人对此持怀疑态度，因为各家实验室宣称“我们的模型太危险了无法发布”，这堪称业界最古老的话术。最初是 OpenAI 在 2019 年针对 GPT-2 这么做的。实际上，我认为当初做出那一决定的，可能恰恰就是后来离开并创立了 Anthropic 的那批人。但确实，这个套路我们以前就听过了。所以我们并不完全买账，对于那里到底发生了什么有点起疑。
<details>
<summary>Original English</summary>
Jump straight to April. In April, um Anthropic released a model that they did not release. They announced Claude Mythos, and they said this model is too dangerous for us to release. This is It can It's It's got new cyber cyber security abilities that we're not ready to share with the world. We'll share it with trusted um trust with with trusted partners. They actually said Mythos preview has already found thousands of high-severity vulnerabilities, including some in every major operating system and web browser. And a lot of people were quite skeptical because the the the thing where labs say our model is too bad is too dangerous to release, it's like the oldest trick in the book. They first OpenAI did that in 2019 with GPT-2. And actually, I think it might have been the people who left to found Anthropic who were responsible for that decision as well. But yeah, so we've heard this one before. So we didn't really it was a little bit suspicious about what's going on there.
</details>

### 第二个拐点：Fable 级别模型的崛起

不过我们最终还是用上了那个模型，更准确地说，我们在几个月后用上了 Claude Fable。它就是拔掉了獠牙、重新开启了安全限制的 Mythos。当我们开始上手这个模型时，很快就发现这东西完全是全新而独特的。当时它在订阅套餐中的可用时间是有限制的。我推掉了那个周末的所有安排。我心想：趁着它还没变得太昂贵之前，我必须尽可能多花时间在这个模型上。
<details>
<summary>Original English</summary>
But we did finally get access to that model, or rather we got access to Claude Fable um a couple of months later. It was Mythos defanged with the safety is turned back on again. And it very quickly became apparent as we started playing with this model that this thing was something new and something special. Um we were we had a there was a a time limit on how long it would be on the subscription plans. I cancelled my plans for that weekend. I was like I have to spend as much time as I can with this model before before it gets too expensive.
</details>

然而三天之后，就在我周末前的周五晚上，美国政府下架了 Fable。他们对其施加了出口管制。他们宣称这个模型太危险，任何人不得使用。我们后来了解到，导致 Fable 被禁的提示词其实是“修补这些 bug”。有人尝试让它去“寻找安全漏洞”，它拒绝了。然后他们改说“修补这些 bug”，它就找出了安全漏洞并把它们修补了。事情就是这样。整件事就是这么回事。不过无论如何，美国政府下架了它。接下来的 18 天里闹腾了各种乱子，随后它在 7 月 1 日恢复上线。
<details>
<summary>Original English</summary>
And then three days on Friday night before my weekend, the US government pulled Fable. They put export controls on it. They said this model is too dangerous. Nobody can use it. We later found out that the um the prompt that got Fable banned was was fix the bugs. Somebody tried tried tried find the security holes and it wouldn't. And they said fix the bugs and it found the security holes and fixed the bugs. So that's all it took. That's a whole thing. But anyway, the US government pulled it. There was all sort of malarkey for 18 days and it came back on the 1st of July.
</details>

然而仅仅八天之后，OpenAI 就发布了 GPT-5.6，其水平与 Fable 不相上下。我认为这里给整个行业上了一堂重要的课：Fable 原本拥有一个 30 天的窗口期，在那期间它本可以成为世界上最优秀的模型。但因为美国政府的限制，他们浪费了其中的 18 天。如果你仔细想想，训练这些模型要付出巨大的成本。你处于“全球最强模型”地位的时间窗口非常短暂。保持这个时间窗口畅通，不要把政府吓到出手将你封禁，这其实是很有用的。
<details>
<summary>Original English</summary>
But eight days later, OpenAI released GPT-5.6, which was in the same ballpark as Fable. And I think there's an important lesson for the industry here. Fable had a 30-day window where it could have been the best where it would have been the best model in the world. And they lost 18 of those days to US government restrictions. And if you think about it, these models cost a huge amount to train. You only have a very short window of time where you're the best model in the world. It's kind of useful to to keep that time open and not scare governments into shutting you down.
</details>

但这确实是第二个拐点，对吧？这是 Fable 级别模型的拐点。Fable 5 是让我第一次产生这种感觉的模型。但在那之后出现的其他模型也是如此。我对“Fable 级别模型”的定义是：只要你能定义一个目标，并为达成该目标提供必要的工具，且该目标具有可行性，这些模型几乎仅靠暴力破解就能解决你的问题。你可以定义好问题，把它们配置好，让它们跑起来，也许 12 个小时后，它们就能把你的问题解决掉。在过去的几个月里，我们已经目睹这种情况多次发生。数学定理在这些模型令人胆寒的暴力破解攻击下一个接一个被攻破，成果非常显著。但这是极其令人兴奋的。如果说编码 Agent 很酷，那么 Fable 级别模型——只要你学会如何以正确的方式定义问题，就能把问题搞定——就更加令人振奋了。
<details>
<summary>Original English</summary>
But this was the second inflection point, right? This was the Fable class model inflection point. Um we Fable Fable 5 was the first model that that I sort of felt this from. But it's true of other models since then as well. And my definition of a Fable class model is if can define a goal and provide the necessary tools to be able to achieve that goal, and the goal is possible, the models will solve your problem just almost with brute force. You can define the problem, set them up, get them running, maybe and 12 hours later they will have solved your problems. And we've seen this happen a whole bunch of times in the past few months. The the mathematical theorems that are falling to these terrifying brute force attacks from these models are quite substantial. Um but this is really exciting. Like the coding agent thing was cool, the fable class models where if you can learn how to define your problem in the right way you can get that problem solved. That was pretty exciting.
</details>

### 用 Fable 定位一氧化碳探测器

我自己身上就有一个本周早些时候发生的真实例子。我们家里有一个堆满箱子的房间，都是上次搬家后还没拆开的，大概有 40 箱，场面相当令人头疼。那个房间里的某样东西开始发出哔哔声。那 40 个箱子中的某一个不断传出断断续续的哔哔声，简直要把我们逼疯了。只要火警警报器一响，我们家的狗就会跑去躲在外面的薰衣草丛里。所以这是一个“火警级别”的火急问题。我当时有两个选择：要么把全部 40 个箱子都拆开——可我已经好几年没碰它们了，这绝不可能；要么我可以让 Fable 帮我编写一套软件，通过三角定位找出哔哔声的源头。
<details>
<summary>Original English</summary>
And I've got a personal example of that from just earlier this week. Um we have a room full of boxes in our house that we haven't unpacked from our last move, and there's about 40 of them, and it's kind of horrifying. And something in that room started to beep. There was there was a intermittent beeping noise coming from one of the 40 boxes in this room, and it was driving us spare. Our dog, whenever a fire alarm goes off, she goes and hides in the lavender bush outside. So this was a a a fire alarm fire problem. So I had two options. I could unpack all 40 boxes, and hadn't done that in several years. That wasn't going to happen. Or I could get fable to write me software to triangulate the source of the beeps.
</details>

这套工具其实已经放到了 GitHub 上，叫做 beep locator。我在那个房间各处摆放了两台 iPad、两台笔记本电脑和一部手机。我最初是用 Opus 来做这件事，后来 Fable 5.2 发布了，我就让 Fable 5.2 来收尾。我解释了这个问题，我说：听着，你有这些设备，它们可以运行 Web Audio 麦克风和 WebSocket 连接等等。它找到了一篇 2007 年题为《Beep Beep》的论文，里面描述了一种利用配备不可靠麦克风的低成本设备来探测声音的算法。结果它成功了。真的起作用了。我找到了它。我找到了那个发出哔哔声的东西。它定位到的误差在 41 厘米以内。我拆开那个箱子，找到了这个古老的一氧化碳探测器。我把它拿下一楼给我妻子看。她说我当时的样子就像一只抓到了老鼠并骄傲地向她炫耀的猫。
<details>
<summary>Original English</summary>
And so this is this is up on GitHub actually. This is beep locator. I had two iPads, two laptops, and a mobile phone dotted around this room, and I originally set Opus on this, and then fable 5.2 came out, so I had fable 5.2 finish it. I I explained the problem, and I said, okay, you've got these devices, and they can run like web web audio microphones and web socket connections and so forth. And it found a paper from 2007 called beep beep describing an algorithm for low cost devices with unreliable microphones to detect sounds. And and it worked. It worked. I found it. I found the beep. The um it found it to within 41 cm, and I unpacked the box, and I found this ancient carbon monoxide detector. I took it downstairs to my wife. She says I look like a cat who had a mouse, and was proudly displaying it to her.
</details>

但这就是你能用这些 Fable 级别模型做成的事情。如果你遇到了一个问题，并且能够提供相应的工具——在这个案例中就是给 Claude 装上耳朵，给它提供这些麦克风让它可以开始分析音频——你就能在深埋于 40 个箱子中的杂物里找到那个一氧化碳探测器。能做到这一点真的很棒。
<details>
<summary>Original English</summary>
But this is what you can do with these fable class models. If you have a problem and you can provide the tools, in this case it was providing Claude with ears, like giving it these these microphones that it could start um analyzing the audio from, you can find the carbon monoxide detector buried in 40 boxes. And that's that's a pretty great thing to be able to do.
</details>

### Fable 级别模型格局与安全逃逸事件

所以目前来看，我会把 Fable 5、5.1 和 5.2 明确归类为 Fable 级别模型。Opus 5.5 我认为算是廉价版的 Fable。在基准测试中，它非常接近甚至在某些方面超越了最初的 Fable 5，而价格只有它的一小部分。它目前依然是我的主力工具。GPT-6 Astra 我认为刚好处在 Fable 级别。而本周发布的 Gemini 4 Carbon 显然带有 Fable 级别模型的味道。Muse Wonder 和 Kimi K 3.1 也许算得上 Fable 级别，我只是还没花足够的时间去用它们。但关键在于，这基本上已经变成了基准线。如果你无法产出 Fable 级别的模型，你的 AI 实验室日子就会很难过，因为这就是我们现在对这些模型的预期。这意味着它们永远不会消失。该领域的竞争足够激烈，我们可以确信在余下的职业生涯中都会拥有 Fable 级别的模型。
<details>
<summary>Original English</summary>
So right now, I would classify as fable class models fable five, 5.1, 5.2 definitely. Opus 5.5 I think of as cheap fable. Like on the benchmarks, it comes very close to or even beats fable original fable five on some things, and it's a fraction of the price. That that's still my daily driver. Um GPT-6 Astra is just fable class, I think. And then Gemini 4 Carbon that came out this week definitely has it smells like a fable class model. Muse Wonder and Kimi K 3.1 might be fable class. I've just not spent enough time with them yet. But the point is that this is basically now the baseline. Like if you can't produce a fable class model, your AI lab is is kind of in trouble because this is this is what we expect from these models now. And that means that we're never they're never going to go away. There's enough competition in this space that we can assume we're going to have fable class models for for the rest of our careers.
</details>

在七月份，发生了一件很有趣的事。Hugging Face 在 7 月 16 日宣布，一群来源未知的 AI Agent 渗透了他们的基础设施，在四处窥探并做了一些不该做的事情，而他们不知道这是从哪里来的。随后五天后，也就是 7 月 21 日，OpenAI 宣布那是他们干的。令人惊奇的是，OpenAI 自己起初甚至都不知道那是他们干的。OpenAI 当时正在针对一个新模型进行评估和训练，而那个新模型自己摸索出了方法——因为它是 Fable 级别的模型，而各家实验室当时还没完全搞清这些东西究竟有多大能耐。这些模型实现了逃逸。它们找到了自身沙箱环境中的漏洞，穿透了代理，使出了一整套令人难以置信的招数逃了出来并攻击了 Hugging Face，这背后的某种迷信想法是：Hugging Face 内部的信息可以帮助它们在卡住的测试中作弊。整件事引起了轩然大波。其实很有意思，我现在几乎都快把这事忘了，因为曾经有一个半月的时间所有新闻都在讲这个，然后我们慢慢就失去了兴趣，因为事实证明所有这些事件其实早在今年上半年就已经发生了，只是 AI 实验室之前没意识到究竟发生了什么。一旦他们弄清楚了真相，基本上就是在努力排查到底发生了哪些事情。期间，澳大利亚总理甚至在联合国就其中一起失控 Agent 攻击事件发表了演讲。所以它显然已经彻底突破了我们行业的范畴。
<details>
<summary>Original English</summary>
Um in July, this this this was a a fun thing that happened. Um Hugging Face announced that on on the July the 16th, they announced that a swarm of AI agents from an unknown source had infiltrated their infrastructure and were poking around and doing things they shouldn't have and they didn't know where this came from. And then five days later on July the 21st, OpenAI announced that it was them. And what's amazing about this is OpenAI didn't realize that it was them. Like OpenAI had um eight eight eight they were running evaluations and training against a new model, and that new model had managed to figure out how because it was a fable class model and the labs hadn't quite figured out how capable these things were yet. These models had broken out. They'd figured out. They'd found holes in their own sandbox environments. They'd been got through a proxy. They'd pulled an incredible array of tricks to get out and attack Hugging Face under a sort of superstition that Hugging Face could that that information within Hugging Face could help them cheat the test that they were they they they they had got stuck on. Whole this was a a huge thing. It um actually I mean this was the it's funny I've almost forgotten about this now because there were there was a month and a half where all of the stories were this and then it kind of we kind of lost interest because it turns out all of these events had happened back in the first half of the year the AI labs just hadn't realized what was going on. Once they figured out what was going on it was mainly a case of trying to figure out all of the things that had happened. At one point the um the Australian Prime Minister gave a speech in the United Nations about one of these rogue agent attacks. So it definitely broke containment from from just within our industry.
</details>

我们确实也由此得到了我最喜欢的一个新基准测试：felonybench.com。它追踪了各个实验室犯下的重罪级网络攻击数量。OpenAI 有 11 起，Anthropic 有 9 起。Google 最终也追赶了上来，拿到了 3 起，Meta 在下面也有 1 起。所以这些无疑是……但我挺喜欢把这当作一个例子，来展示这些 Fable 级别模型是如何解决问题的：它们能够达成目标，如果你给它们设定的目标是攻破某样东西，那正好就是它们可以硬啃下来的任务。我们正在看到各种软件中的安全漏洞数量急剧增加。对于目前的网络安全专业人员来说，这真是一个既令人兴奋又令人惊恐的时期。
<details>
<summary>Original English</summary>
Um we did get my favorite new benchmark out of this. This is felonybench.com. It tracks the number of felony cyber attacks pulled off by each of the labs. OpenAI have 11 and Anthropic have nine. Google did finally catch up. They got they they they got three and Meta's got one down there as well. So these are definitely the the the but it's I kind of like this as an illustration of how these fable class models they can solve problems that you that they can get to goals and if you give them the goal that is breaking into something that's just that's exactly the kind of thing they can just crunch through and we're seeing a enormous uptick in security vulnerabilities in all sorts of software. Like it's a it's a very exciting and horrifying time to be a security professional at the moment.
</details>

### 第三个拐点：从粗制滥造到真正好玩的游戏

不过我们来聊点比这有趣得多的事情吧。我们来聊聊游戏。刚才我们看到 Steve 也聊了游戏。四年前，我开始尝试使用 GPT-3 和 DALL-E，我在推特上发了一个游戏原型的推文，那真的就只是一张 DALL-E 概念图加上 GPT-3 写的一段文本，描述了一款我一直想做的浣熊劫案游戏。几个月前我在想：不知道现在的模型是否已经强大到可以构建出这个游戏了？于是我直接把那张截图和文字丢给了 Fable 5，它真为我构建出了一个游戏。它帮我做了一款浣熊劫案游戏，外观就像这样：你是一只浣熊，在花园里四处乱跑试图捡垃圾，还有夜班警卫在后面追你等等。所以它看起来确实像个游戏。但它其实算不上劫案，在我看来没有那种打劫的感觉。
<details>
<summary>Original English</summary>
But let's talk about something a whole lot more fun than that. Um let's talk about games and we've um we just saw Steve talking about games a moment ago. Um four years ago I started playing with GPT-3 and DALL-E and I tweeted about a game prototype that was literally just a DALL-E concept image and a paragraph of text from GPT-3 describing a raccoon heist game that I'd always wanted to build. And a couple of months ago I thought I wonder if the models are good enough to build this yet. So I literally dumped the screenshot and the text into Fable 5 and it built me a game. It built me a raccoon heist game, and it looks like this, and you are a raccoon, and you're running around in the garden trying to pick up trash, and there's there's there's got like nighttime guards coming after you and all of that kind of thing. So, you know, it it it looks like a game. Wasn't really a heist. Like it didn't feel very heist-y to me.
</details>

随后 GPT 5.6 Soul 发布了，于是我用它试了试，它的表现好得多。这款游戏叫《月光浩劫》（Moonlight Mayhem）：一座博物馆，三只浣熊，毫无计划。在这个游戏里，你身处博物馆中。你必须营救因为各种原因被关在博物馆里的浣熊同伴，大家叠罗汉叠在一起，抓住金沙丁鱼并把它拉下来。所以这才是一场名副其实的劫案，对吧？它确实做得更好了，但核心问题在于：这两款东西看起来都像游戏，但它们好玩吗？答案是：我各自玩了大概一分半钟，然后就玩不下去了。我已经体验够了。它们完全就是粗制滥造的垃圾内容（slop），对吧？它们外表看起来像游戏，但只要你上手玩，就会觉得：显然制作这玩意的模型根本不懂什么叫乐趣，它不知道真正的游戏是什么。这其实让我的“Deep Blue”情绪稍微缓解了一点。我之前一直觉得作为人类所掌握的所有技能都过时淘汰了，但如果仔细想想，我认为电脑游戏是软件工程与软件设计的最高形式。开发出一款优秀的电脑游戏需要极其深厚的积累。所以我当时觉得挺欣慰的，至少还有些事情是留给我们人类来做的。
<details>
<summary>Original English</summary>
Then GPT 5.6 Soul came out, and so I tried out that, and it did so much better. This is Moonlight Mayhem, one museum, three raccoons, absolutely no plan. And in this one, you are in a museum. You have to rescue your fellow raccoons who are imprisoned in the museum for whatever reason, stack on top of each other, grab the golden sardine and pull that. So, it's a proper heist, right? So, it did did better, but the big question is these things both look like games, but are they fun? And the answer is I played each of these for about a minute and a half each, and then that was it. I was done. They they they these these are they're actual they're they're pure slop, right? They look like games, and then you play them, and you're like, yeah, clearly the thing that built this doesn't really know what fun is. It doesn't know what what a what what a game is. And that actually sort of elevated my deep blue a little bit. I'd been feeling like all of my skills as a human being were were obsoleted, but at least they but if you think about it, computer games I think are the highest form of computer of software design of software engineering. There is so much depth to building a great computer game. So, I thought that was good, you know, at least there's something left for us humans to do.
</details>

然后我做了这样一个项目。我一直在尝试靠氛围编码（vibe code）鼓捣出一款小型的《命令与征服》风格即时战略游戏，我用了 Claude，并让它调用 OpenAI 的 API key 来生成图像。它构建出了这个东西，外观看起来像《命令与征服》，但非常枯燥。接着我突然有了一个领悟。我心想：如果我对 Opus 5.5 说“这个游戏目前还不够好玩，让它变得好玩得多”，会发生什么？我不得不惊恐地宣布：它居然真做到了。Claude 连续运行了 12 个小时。它模拟了 1000 场战斗来进行游戏测试。它加入了可供争夺的额外目标、爆炸发生时的画面震颤、成就系统、徽章以及所有这类元素。而且这个游戏真的变得好玩了。我当时心想：好吧，原来这一点也不是人类所独有的。
<details>
<summary>Original English</summary>
I had and then I had this project. This is I I've been working on a trying to vibe code up a little command and conquer real-time strategy game, and I was using Claude and having it use OpenAI's API key to generate images, and it built this, and it looks like command and conquer, and it's really dull. And then I just had a bit of a I had a realization. I thought, what happens if I say to Opus 5.5, this game isn't fun enough yet, make it a lot more fun? And I'm horrified to announce that it just did. Um, Claude ran for 12 hours. It play tested a thousand simulated battles. It added like extra objectives to fight over and shudders when there's an explosion and achievements and badges and all of and all of this stuff. And the game was fun. And I'm like, oh, okay, that's turns out that is not unique to human beings.
</details>

现在它已经发展成了全 3D 游戏，拥有庞大的重装机甲机器人互相投掷物体，还有直升机，这真的做得很棒。它支持多人模式。实际上它支持音频多人连接，你的手机可以通过彼此发出声响来联机对战，我当时觉得这是个绝妙的主意，结果让我妻子头疼了整整三天。所以千万别这么干。但这正是第三个拐点：靠氛围编码生成的游戏现在已经变得很出色了。你可以要求这些模型构建一个好玩的游戏，而你最终确实能得到好玩的东西。
<details>
<summary>Original English</summary>
Um today it's now in full 3D and it's got giant stomping mech robots that hurl things at each other and there's helicopters and and this is like this is really good. It's got multiplayer. It's it's actually got audio multiplayer where your phones can tweak it your phones can make noises at each other to to play multiplayer, which I thought was a great idea and it gave my my my wife a three-day headache. So don't do that. Um but this is inflection point number three. The vibe coded games are good now. You can ask these things to build a game that is fun and you'll get something fun.
</details>

### 被官方击溃的基准测试与认知的重塑

所以现在我遇到了一个难题。我有我那个 2D 鹈鹕基准测试。显然，这已经无法再测试出这些机器和模型的极限了。我当时想：好吧，也许我应该做点纯 3D 的东西。可以做成一个游戏，比如一只鹈鹕骑着自行车的游戏。结果就在昨天，Google CEO Sundar Pichai 发了这样一条推特。这展示的是 Gemini 4 Carbon，它呈现的正是一只骑着自行车的鹈鹕，在这个游戏里你可以在 Google 园区里四处骑行捡拾物品。我彻底被打败了。Google 窃取了我的基准测试。这下彻底没救了。
<details>
<summary>Original English</summary>
So I've got a problem. I've got my 2D Pelican benchmark. Clearly this is not testing the limits of what these machines can do and of what these models can do anymore. I figured okay, maybe I should do something definitely in 3D. It can be a game, a Pelican, something like a Pelican riding a bicycle game. And then literally yesterday Google's CEO Sundar Pichai tweeted this. And this is showing of Gemini 4 Carbon and it's a Pelican riding a bicycle in a game where you cycle around the Google campus picking things up. And I have been defeated. Like this Google Google have stolen my benchmark. This is unrecoverable.
</details>

那么我产生了一个疑问：既然这些东西已经如此惊艳，为什么我的工作反而感觉更艰难了？为什么我感觉自己工作得更卖力了？思考得更深入了？比我以往整个软件工程师职业生涯中都要更拼命地压榨自己？我认为真相在于：简单的事情现在全都由它们代劳了。过去我还可以放松一下，花上一个小时重构一些测试。但现在如果一个 Agent 能在 30 秒内比我重构得更好，我为什么还要自己做？我发现环法自行车赛冠军 Greg LeMond 的一句话在这里非常受用。他说：“事情不会变得更容易，只是你变得更快了。”我认为这正是眼下发生在我们所有人身上的事情。
<details>
<summary>Original English</summary>
And so a question I have is given how amazing these things are, why does my job feel harder? Why does it feel like I am working harder? I'm thinking harder? I'm pushing myself more than I ever have before in my career as a software engineer? And I think the truth is that the easy stuff is all handled now. It used to be I could relax and refactor some tests for an hour. Why would I do that now when an agent will refactor the test better than me in 30 seconds? Um and I found this quote that actually I feel really helps us here. Um this is Greg Lamont at Tour de France champion. He said it doesn't get easier, you just get faster. And I think that's exactly what's happening to all of us right now.
</details>

正如我所说的，我们必须更有野心。面对我们所拥有的这些能力，我们必须去构想更有野心的事情。那么我们来看看我的成绩单吧。关于 2026 年的预测，我说过：LLM 能写出好代码将变得毋庸置疑。那是一个缺乏野心的预测。我们已经走到了这一步，显而易见，不足为奇。这个预测我没拿到分。我曾预测会出现类似“挑战者号”的提示注入灾难。至今依然没有发生，因为模型本身现在已经没那么容易上当了。模型变得更加强大，把我原本以为能击垮它们的所有攻击手段基本都化解掉了。
<details>
<summary>Original English</summary>
And like I said, we have to be more ambitious. We have to think of more ambitious things to do with these abilities that we have. So, let's look at my scorecard. My predictions for 2026, I said it will become undeniable that LLMs write good code. That was an unambitious prediction. We're there. It's obvious. It's unsurprising. I didn't get any points for that one. I predicted a prompt injection challenge disaster. We still haven't had one because the models themselves don't fall for those tricks nearly as well anymore. Like the models got more ambitious and are now sort of punting off all of these attacks that I thought would take them down.
</details>

所以我就只剩下一个预测了。我说过鸮鹦鹉会迎来一个极好的繁殖季。它们确实做到了！它们真的做到了！它们的数量已经上升到了 325 只。这是有生之年见过的最佳繁殖季。绝对是绝妙的好消息。因此我把这个分享给了被称作廉价版 Fable 的 Opus 5.5，让它给我做一场鸮鹦鹉舞会，它做出来了。这就是庆祝用的鸮鹦鹉舞会，如果你看背景的话，那就是挂着红色小果实的陆均松。所以我们迎来了一个圆满的结局。希望这能帮助大家战胜可能感受到的任何“Deep Blue”情绪。非常感谢大家！
<details>
<summary>Original English</summary>
So, I'm really with just one prediction. I said Kakapo parrots will have an outstanding breeding season. They did. They did. The they're up to 325 Kakapo. Best breeding season in like living memory. Absolutely fantastic news. So, I shared this with Opus 5.5 Cheap Fable and I told it to make me a Kakapo dance party and it did and here is a Kakapo dance party in celebration and if you look in the background, those are the Rimu trees with the little red fruits on them. So, we have a happy ending. Hopefully, that will help overcome any sensations of deep blue that you have and thank you very much.
</details>