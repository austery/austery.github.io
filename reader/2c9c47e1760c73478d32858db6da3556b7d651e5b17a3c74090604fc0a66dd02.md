---
author: All-In Podcast
date: '2026-06-13'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=gH4FTjDm9FQ
speaker: All-In Podcast
tags:
  - artificial-intelligence
  - large-language-model
  - marginal-cost
  - data-governance
title: All-In 播客讨论 Anthropic Fable 5 争议、AI 经济学及主权财富基金与选举议题
summary: 播客讨论了 Anthropic 发布的 Fable 5 模型及其数据保留与降级防护引发的争议，探讨了对企业治理和生物科研的限制。嘉宾还对比了 AI 与互联网的边际成本差异，讨论了国家持有 AI 股权建立主权财富基金的构想，并谈及加州选举等议题。
insight: ''
draft: true
series: ''
category: ai-application
area: tech-engineering
project: []
people: []
companies_orgs:
  - Anthropic
products_models:
  - Fable 5
media_books:
  - All-In Podcast
status: evergreen
---
<!-- chunk 1/13 -->

### 开场与 Anthropic 发布新模型

好了，各位。欢迎回到全球第一的播客。这是你最喜爱的播客，也是你听的播客主播们最喜爱的播客。这是每个人都喜欢抄袭五十期然后放弃的播客。但 All-In 播客不会放弃。我们与最初的四人组一起加倍投入。大家都在这里，迎接意义重大的一周，有很多辩论，我们必须先从 Anthropic 聊起。

<details><summary>Original English</summary>
All right, everybody. Welcome back to the number one podcast in the world. It's your favorite podcast. It's your podcasters's favorite podcast. It's the podcast that everybody likes to rip off for 50 episodes and then they quit. But the All-In podcast is not quitting. We're doubling down with the original quartet. Everybody's here for a big big week, lots of debates, and we got to start with Anthropic.
</details>

Anthropic 发布了一款神话级别的模型，带有一些有趣的防护栏，而且 Dario 似乎又开始写博客了。好吧，这款模型叫 Fable 5。完全不知道他们为什么这么叫，在周二发布，它几乎在每一个基准测试中都名列前茅。然而，token 的成本是 Opus 4.8 的两倍，但总的来说它应该会使用更少的 token，因为理论上它要好得多。目前还不清楚这是否会减轻围绕 token 成本的一些焦虑，但大家还记得四月份的时候，Anthropic 著名地没有公开对外发布 Mythos，因为它具备很强的黑客攻击能力。因此他们把它给了某些人，Palo Alto Networks 的首席执行官 Nikesh 曾表示：“嘿，Mythos 是真家伙。”并且他们用它封堵了内部的一些漏洞。显然，这款新模型很敏感，像生化武器、黑客攻击等这类内容在里面全被屏蔽了。但他们遭到了开发者的强烈抵制，等我把这个解释完就来听听你们的反馈。

<details><summary>Original English</summary>
Anthropic released a mythos level model with some interesting guardrails and uh seems as though Daario is back to blogging. Okay, the model's called Fable 5. No idea why they're calling it that or released on Tuesday and it tops every benchmark nearly every benchmark. The tokens, however, cost twice as much as Opus 4.8, but it should use less tokens overall because it's theoretically that much better. Unclear if this is going to alleviate some of the hand ringing around the cost of tokens, but you remember in April Anthropic famously did not release Mythos because publicly uh it had some strong hacking capabilities. So they gave it to some folks and we had um the CEO of Nesh of Palo Alto Networks who said, "Hey, Mythos was the real deal." and that they used it to seal up some vulnerabilities inside their shop. Obviously, this new model is sensitive uh to topics like boweapons, hacking, all that stuff are blocked in it. But they got a big developer backlash and then I'll get your feedback after I explain this.
</details>

使用 Fable 时，Anthropic 会将你输入的所有提示词数据至少存储 30 天。因此这有点隐私问题。而且如果 Fable 5 检测到你正在进行前沿 AI 研究，换句话说，使用他们的模型来制造更好、更具竞争力的模型，他们就会对你进行降级，但他们并没有告知你。而这一点被深埋在了一份 319 页的文件深处。为此，X 上出现了大量的骚乱与抓狂，但自那以后，他们在《连线》（Wired）上稍微“收回”了一点，原话是：“我们正在修改 Fable 5 针对前沿大语言模型开发的安全防护措施，以使其更加可见透明。”我就先说到这里。Chamath，你对 Anthropic 和这些非凡的模型怎么看？他们不断推出新模型，以及他们处理发布的方式，你觉得如何？他们是深思熟虑，还是小题大做、戏剧化过头了？还是两者兼有？对此你怎么看？在得到 Nikesh 的反馈并看到最新模型发布后，你上手体验了吗？8090 和软件工厂在对它进行基准测试方面有什么进展？

<details><summary>Original English</summary>
While using Fable, Anthropic stores all the prompt data you enter for at least 30 days. And so that's a bit of a privacy issue. And if Fable 5 detects you're doing frontier AI research, in other words, using their model to make a better model, competitive model, they were downgrading you, but they weren't telling you. And this was buried deep in a 319 page document. So many kuruffles, freakouts going on on X over this, but they've since walked it back a bit, quote unquote, in Wired. We're changing Fable 5 safeguards for Frontier LLM development to make them more visible. I'm going to stop there. Chimath, what's your take on anthropic and these extraordinary models? They keep dropping and how they're handling the release of them. Are they being thoughtful? Are they being dramatic and drama queens? A little bit of both. Where do you stand on it? You know, after getting Nesh's feedback and seeing the latest model come out, have you played with it? What's going on at 8090 and the software factory in terms of benchmarking it as well?
</details>

这是一门非常不可思议的模型，因此要向这些人致敬，他们持续推动着封闭前沿实验室模型的边界。他们全力以赴。我认为这现在造成了一个相当明显的风险，而且我认为这个明显的风险体现在两方面。其一是 Anthropic 基本上已经亮明了底牌，那就是他们将越来越多地接收提示词、评估提示词，并在向你生成输出之前决定如何处理它们。

<details><summary>Original English</summary>
It's a really incredible model and so kudos to these guys for continuing to push the boundaries of the closed frontier lab models. They're firing on all cylinders. I think that it creates a pretty obvious risk now and I think that obvious risk is twofold. One is Anthropic has essentially shown their hand which is that they will increasingly take in prompts, evaluate the prompts and decide what to do with them before they generate output to you.
</details>

>> 而且我认为，如果你是一个普通人，你现在大体上应该认为存在审查的风险。如果你是一家企业，我认为这几乎是不可接受的。原因在于，你可能会在甚至不知情的情况下意外触犯其中某条限制。下游科学家使用云 API 可能会触发它；你公司内部的业务主管可能会触发它；从事科学分子研究的人员也可能会触发它。突然之间，你就会与一个对自己非常重要的业务差异化来源断开连接。因此我认为，如果把这两点放在一起看，我们正处于一个非常独特的时刻，企业需要开始审慎评估 AI 的下一个阶段，即我该如何掌控？我允许谁从所有这些信息中去学习？在 AI 方面我是否想要承受单点故障的风险？我认为答案是你需要广泛的多样性，以及一种管理得更好的治理方法。

<details><summary>Original English</summary>
>> And I think if you were a person, you should generally now think there's a risk of censorship. If you're a company, I think it's almost a non-starter. And the reason is because you could accidentally trip one of these things without even knowing it. A downstream scientist using the cloud APIs could trip it. A business executive inside your corporation could trip it. A person doing scientific molecular research could trip it. And all of a sudden, you'll get cut off from a very important source of business differentiation for yourself. So I think if you take both of those two things together, we're at this very unique moment in time where I think companies need to start underwriting this next phase of AI, which is how do I have control? Who am I allowing to learn off of all of this information? Do I want to have single point of failure risk with respect to AI? And I think the answer is that you need broad diversity and a governance approach that's better managed.
</details>

>> 关于 Anthropic 我要说的一点是，他们说的是实话。

<details><summary>Original English</summary>
>> One thing I'll say about anthropic is they tell the truth.
</details>

>> 确实。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 只是这实话当你真正吃下去、吞进肚子里的时候，感觉糟透了，你会觉得“不，这并不好，我不喜欢这样”。所以一方面存在审查风险，另一方面对企业来说纯粹存在治理业务风险。两方面都不妙。

<details><summary>Original English</summary>
>> It's just that the truth sucks when you actually take it and you eat it and you're like it's in your tummy and you're like no this is not good. I don't like this. And so there's the censorship risk on the one hand and then there's just the governance business risk for enterprises on the other. Both are not good.
</details>

>> Friedberg 现在自己在经营公司。我会让你来收尾。Sacks 显然会有很多话要说，不过 Friedberg，作为在经营自己公司的人，你会担心被这类公司中的某一家“抽地毯”吗？比如投入时间到这些平台中的某一个上，然后他们反过来限制你对它的使用，并且或者把你在 Ohalo 正在做的事情放到他们的模型里，并将其提供给其他人？作为站在自身领域前沿、使用这些工具的企业主，你有哪些担忧？

<details><summary>Original English</summary>
>> Freeberg running your own company now. Uh, and I'll let you back clean up here. Saxs, obviously you'll have a lot to say, but Freeberg, running your company, do you worry about getting rugpulled by one of these companies, investing your time into one of these platforms, having them then constrain your use of it and or take what you're doing at Ohio, put it into their model and make it available to other people. What What concerns do you have as a business owner at the forefront of your field using these tools?
</details>

### 开源模型与生物科研限制

>> 这是个极好的问题。服务条款非常明确地写着，他们不能把你们正在做的事情放进他们的模型中，他们不会……

<details><summary>Original English</summary>
>> It's a great question. the the terms of service is pretty clear that they can't take what you're doing and put it into their model that they won't
</details>

>> 当你读到那个条款时，你相信他们吗？我……

<details><summary>Original English</summary>
>> do you believe them when you read that I
</details>

>> 说实话我不确定。确实有我担忧的事情，但我们决定不顾风险放手一搏，因为我们在基因组学领域做了很多专有工作。这意味着我们正在研究不同的基因或基因变异，试图评估该基因或基因变异对活体生物可能产生的影响，显然比如我们在植物、在农业领域的工作。我们会做诸如基于基因编辑工具的引导 RNA 设计这类事情。我们会对哪个基因可能或可能不会具有某种表型进行预测。因此，有大量的基因组建模工作，在过去几年里我们发现这些模型在支持我们方面非常有价值。所以回到大约 6 个月前，我们能够非常简单直接地完成诸如设计基因构建体这类工作，然后你可以用它来制造特定的蛋白质，而且这些工具用于进行此类研究非常易于使用，极其有价值。许多科学家会花费大量时间去做这类工作，而这些模型非常擅长极快地完成。在过去的几周里，他们已经开始限制使用模型进行这类工作的能力。其前提是存在某种生物武器类的风险，人们推测使用这些工具可能会发生这种情况。结果就是，我们正在失去将这些模型用于这项非常重要的科学开发工作的能力。因此，我们很可能最终需要使用开源模型并由我们自己在本地运行。所以我梳理这一切的原因，是为了让人们能够真正理解这里将要发生的事情的背景。当像 Anthropic 这样的人说：“嘿，我们要限制访问或审查这些模型的输出。”这将会迫使像我们这样仍然希望利用这些大语言模型能力的公司，去获取开源工具并运行它们。而如今最好的开源模型是什么？它们是中国模型。

<details><summary>Original English</summary>
>> I'm not sure to be honest there are things I'm concerned about but we've decided to throw caution to the wind because we do a lot of proprietary work in genomics what that means is we're looking at different genes or gene variants trying to estimate the impact that that gene or gene variant might have on a living organism like we work in plants obviously in agriculture And we will do things like RNA guide design for gene editing based tools. We will do predictions on what gene may or may not have some phenotype. So there's a lot of genomic modeling work that we have found these models to be incredibly valuable at supporting us with over the last couple of years. So going back about 6 months, we were able to very simply and cleanly do things like design a genetic construct that you would then use to make a specific protein and the the tools was very easy to use to do that sort of research and extremely valuable. This is the kind of work that many scientists would spend a lot of time doing and these models were very good at doing very quickly. Over the last couple of weeks, they've begun to restrict the ability to use the models to do that work. And the premise is that there's some sort of bioweapon uh type risk that folks have theorized could happen using these tools. And as a result, we're losing the capacity to use these models for this very important scientific development work. As a result, we are likely going to end up needing to use open- source models and run them locally ourselves. So the reason I walk through all of that is so people can really understand the context of what's going to happen here. As folks like Anthropic say, "Hey, we're going to restrict access or censor the output of these models." It is going to force companies like ourselves who still want to take advantage of the capability of these LLMs to go and get open- source tools and run them. And what are the best open source models today? They're Chinese.
</details>

>> 是的，确实是。

<details><summary>Original English</summary>
>> Yeah, they are.
</details>

>> 这是一个重大隐忧。美国的开源模型不如中国的开源模型好。所以 Anthropic 以及其他人施加于自身和施加于整个行业的限制，正在迫使许多公司去获取开源的中国模型并加以运行。我们在整个人工智能版图上都看到了这种情况，初创公司、大型企业皆是如此。每个人都在做出这一举动。

<details><summary>Original English</summary>
>> And that is a major concern. the the American open source models are not as good as the Chinese open source models. So the restrictions that Anthropic and others are putting upon themselves and upon the industry is forcing a lot of companies to go and get open source Chinese models and run them. We're seeing this across the landscape with startups with large scale enterprises. Everyone's making that move.
</details>

>> 是的。这也是我们一直在讨论的事情，结合苹果及其芯片，以及你运行这些模型的效果有多好。另外，我预测你翻开的下一张底牌将是你自己开始制造模型，Friedberg。你会利用你拥有的所有这些数据。

<details><summary>Original English</summary>
>> Yeah. And this is something we've been talking about here with Apple and their silicon and how well you can run these models. Also, I predict your next card you'll turn over is you'll start making your own models, Freeberg. You'll take all this data you have.
</details>

>> 完全正确。我们会从基础核心模型开始，将其与我们的数据结合，然后我们将拥有自己的基因组语言模型，自己的预测模型，然后在内部使用。我认为大家都在走向那个方向。但我指出这一点的缘由是，许多人都感受到了来自 Anthropic 这样做的压力。并且他们正感受到来自政客的压力，这些政客在不断重复 Dario 和其他人所说的那些骇人听闻的言论。结果就是，他们将试图，并且已经在试图将自然层面的强制执行或政治化的强制执行强加给模型提供商，这种方式最终将会……

<details><summary>Original English</summary>
>> It's exactly right. And we'll we'll start we'll start with the core model, combine it with our data, and then we'll have our own genome language model, our own prediction model that we'll then use internally. And I think that's where folks are going. But the reason I point this out is because a lot of folks are feeling the pressure from anthropic doing this. and they're feeling the pressure from politicians repeating the scary words that are being said by Daario and others. And as a result, they are going to try and they are already trying to force either natural enforcement or politicized enforcement upon the model providers in a way that is ultimately going to
</details>

<!-- chunk 2/13 -->

### 监管与开源竞争

让中国开源模型提供商获益。这是件可怕的事，因为我们将会损害自身经济的活力。你不可能直接叫停 AI。尽管大家都说 AI 会带来世界末日，但如果试图通过这种政治行动和某种社会行为去叫停 AI，你从根本上就会把优势拱手让人，因为 AI 是不会消失的。所以我描述我们正在做的事情，是为了让所有人真正理解并搞清楚，你不能直接关掉 AI、关掉获取这些东西的途径。你这样做的结果，就是逼得别人平白占据不公平的优势，因为你不公平地限制了自己的模型以及获取这些模型的途径。
<details><summary>Original English</summary>
benefit Chinese open source model providers. And that is a scary thing because we are going to damage our own kind of economic viability. You can't just stop AI. As much as everyone says AI is doomsday, by stopping AI or trying to stop AI through this political action and social, you know, kind of behavior, you are fundamentally going to give someone else the advantage because the AI isn't going to go away. So the reason I describe what we're doing is for everyone to really understand in Grock that you can't just turn off AI and turn off access to these things. What you will do is you will force the hand of someone else to now have an unfair advantage because you're unfairly restricting your models and your access to those models.
</details>

讲得好，讲得真好，弗里德伯格。萨克斯，从棋局的角度来看你怎么看？我们既有商业方面的理由，也有本土方面的理由，但在 Anthropic 这件事上存在很多问题，他们基本上亮出了所有红灯来招致监管，去引来——这也将是我们的第二条新闻——伯尼·桑德斯没收这些公司的股权。但老兄，这就像在说：“看这边，我们正在放一把火，快把我们狠狠管起来。”这也让人不禁琢磨：嘿，也许我应该做自己的模型，也许我应该去拥抱开源模型。扎克，这里的棋局是怎么发展的？
<details><summary>Original English</summary>
Well, well, really well said, Freeberg Saxs. What's your take just in terms of the chessboard in terms of we got the business case here, we got the local case, but there's a lot of issues here with Anthropic in terms of them essentially throwing up every red flag to get regulated to induce and it'll be our second story, the Bernie Sanders seizing the equity of these companies. But man, th this is saying, "Look over here. We're starting a fire. Regulate the hell out of us." Which also then makes you wonder, hey, maybe I should be doing my own model. Maybe I should be embracing open source models. How's this chessboard developing here, Zach?
</details>

>> 嗯，你看，八个月前我就说过，Anthropic 正在基于制造恐慌发起一场非常高明的监管俘获运动。当时人们觉得这是一个非常激进辛辣的观点。但八个月后，我觉得你能听到很多人都在这么说了。事实上，我觉得这几乎正在成为一种新的共识。而且我觉得你的总结中有一点没完全说到，JCAL，你……
<details><summary>Original English</summary>
>> Well, look, eight months ago, I said that Enthropic was engaged in a very sophisticated regulatory capture campaign based on fear-mongering. And people at the time thought that was a very spicy take. But 8 months later, I think you're hearing a lot of people say it. In fact, I think it's almost now becoming a new consensus. And one of the things I think your summary didn't quite capture, JCAL, y
</details>

### Anthropic 的监控与模型降级争议

>> 就是那种信任被背叛的感觉，以及开发者群体对这次最新的 Fable 发布有多么愤怒。这不仅仅在于他们在进行强制监控。记住，这是一家曾声明自己反对政府监控的公司。现在，他们会将你发送给这些 Mythos 级别模型的每一个提示词和每一个输出结果都保留 30 天。没有任何例外。即使是签订了零数据保留协议的企业客户，他们也没有选择权，或者我猜他们也可以干脆不用新的 Fable 或者 Mythos 级别的模型。但他们会把你所有的数据保留 30 天。这还不仅仅是提示词和输出。记住，还包括你与他们共享的所有上下文。所以你看，所有这些智能体平台，它们基本上都在存储你所有的记忆、你所有的文件、你所有的数据，并在这些庞大的上下文窗口中把它们传递给模型以获得更好的回答。Anthropic 声称会保留所有这些内容，这样做是为了建立关于你的个人画像，对你进行分类，然后决定进而向你解锁哪些能力。而除了监控之外，最令人愤慨的一点是他们居然会降低产品性能。他们会降低呈现给你的内容。如果 Anthropic 自行单方面认定你不配接触那种级别的信息，他们就会削弱自己的模型。所以他们正在制造一种新的 AI 阶层分化——“有者”与“无者”。他们所做的是——他们有一小部分退步让步了，那就是他们说过，当涉及机器学习、AI 研究、芯片设计研究这类领域时，他们会把你降级到一个更低级的模型，但并不通知你，他们甚至会……
<details><summary>Original English</summary>
>> is the sense of the violation of trust and how much outrage there is in the developer community over this latest Fable release is not just the fact that they're doing mandatory surveillance. Remember, this is a company that said that it was against government surveillance. They are now retaining for 30 days every prompt and every output you send to one of these mythos class models. There are no exceptions. Even enterprise customers who had signed zero data retention agreements, they do not have a choice or I guess they can just not use the new fable or or mythos class models. But they retain all of your data for 30 days. And it's not just the prompts and the output. Remember, it's all the context you share with them. So, you know, all these uh agent platforms, they're basically storing all of your memories, all of your files, all of your data, and they're passing them to the model in these giant context windows to get better responses. Anthropic is saying it will keep all of that, and it does it to build a profile on you, to classify you, and then to determine what capabilities it then unlocks. And the thing that created the most outrage in addition to the surveillance is the fact that they would degrade the product. They would degrade what they show you. They would nerf their models if it decided in anthropic soul discretion that you are not worthy of having access to that level of information. So they're creating a new level of AI halves and have nots. And what they did is and they they this is there's a narrow piece here they walk back which is they said that when it came to things like machine learning AI research chip design research those types of areas they would kick you to a lesser model but not tell you that and they would even
</details>

>> 这感觉像是反竞争的，对吧？我是说……
<details><summary>Original English</summary>
>> which feels anti-competitive right I mean
</details>

>> 这完全是反竞争的。而且他们甚至还会做一些在后台重写你提示词的事情，给出一个被削弱的答案，却不告诉你他们在干什么，他们照样为你以为自己购买到的产品收费，而且永远不告诉你你其实没有得到前沿模型的能力。所以他们实际上是在误导用户，这正是引发如此大愤怒的原因。现在他们做出让步的狭义部分，是他们现在表示当他们降级你时会予以披露，但当他们认定那个人不应该获得相应信息时，他们依然在把人降级。你也看到很多人在网上发帖举例说明这里面巨大的越权行为。有人展示了当他们仅仅只是问了一个关于线粒体的问题时，基本上就被降级了。
<details><summary>Original English</summary>
>> it's completely anti-competitive and also they would even do things like rewrite your prompt in the background so they would give you a nerfed answer they would not tell you what they were doing they still charge you for the product that you thought you were getting and they would never tell you that you were not getting Frontier model capability. So you they were actually misleading their users and this is what was creating so much outrage. Now the narrow piece they walk back is they are now saying that they will disclose when they downgrade you but they are still downgrading people when they decide that that person should not receive the appropriate information. And you saw there were a lot of people posting online with examples of the massive overreach here. So someone showed that when they simply just asked a question about mitochondria, they were basically downgraded.
</details>

>> 没错。
<details><summary>Original English</summary>
>> That's right.
</details>

>> 当 Stratechery 的本·汤普森问了一个非常直接的关于癌症风险与 GLP-1 之间关系的问题时，他被直接踢出去了。
<details><summary>Original English</summary>
>> When Ben Thompson from Strateery asked a very straightforward question about the relationship between cancer risk and GLP once, he was kicked out.
</details>

>> 所以这些家伙对谁应该被降级的范围界定得非常宽泛。再次强调，他们会监控你以决定你是否应该被降级。我认为我们在这里看到的是这整件事的发展走向：那就是这些强大的大型科技巨头将决定你是否配得上，他们将决定你属于 AI 的“有者”还是“无者”，然后根据他们对你进行画像时确定的标准，来审查你收到的输出内容。
<details><summary>Original English</summary>
>> So these guys have a very expansive view of who should be downgraded. again, they're going to surveil you to determine whether you should be. And I think what we're getting here is a vision of where all of this is headed, which is that these powerful big tech companies are going to decide whether you're worthy. They're going to decide whether you're an AI have or have not, and then they're going to censor the output that you receive based on the criteria they determine when they profile you.
</details>

>> 那可真是非常奥威尔式了。
<details><summary>Original English</summary>
>> That is very Orwellian.
</details>

### 商业偏袒与可审计性风险

>> 我觉得不仅是那样。我认为还存在着一种更隐蔽但也同样阴险的风险，那就是他们会开始挑选他们想要偏向哪家大企业。举例来说……
<details><summary>Original English</summary>
>> I think there's that. And I think that there's the risk of something that's more subtle but equally insidious, which is that they will start to pick which corporations they want to benefit. So for example,
</details>

>> 如果诺华有一款与礼来竞争的 GLP-1 药物，而且他们与诺华有战略合作协议，而与礼来没有，现在就产生了一种去塑造人们如何获取信息的动力。
<details><summary>Original English</summary>
>> if Novartis has a competitive GLP1 drug to Lily and they have a strategic deal with Novartis and not one with Lily, now there's an impetus to shape how people get information.
</details>

>> 对吧？如果他们与摩根大通签了协议，但没与花旗银行签，你根本就不会知情。于是你问了一个关于抵押贷款利率或利息率的问题，就会得到各种你根本摸不着头脑的东西。而这里面更成问题的下游环节是，我看不出他们是否会留存他们具体行为的实际指纹记录。所以如果你认为某件事是以不光彩的方式做的，你应该能够去找他们，或者监管机构应该能够去找他们说：“把生成那个输出的确切时刻那次模型运行的追踪记录拿给我看。说服我为什么那不是被故意削弱或操纵的。”

而他们有各种各样的办法在那上面瞒天过海。所以我认为萨克斯说的那一整套东西现在之所以会发生，是因为如果你是一家新兴公司，你应该做的是去敲 Anthropic 的大门说：“我们来做笔交易吧，我给你一半股权，你直接把人引流到我这里怎么样？”而他们会说：“嗯，经济利益并不是我在乎的，你对人生、对道德、对所有这些社会议题的哲学理念是什么？”一家公司会说是 A，另一家公司会说是 B，他们就会偏袒 A 而不是 B，然后各种猫腻就会在暗地里发生。这才是可怕的地方。让我仅以我的自由市场视角问一句：比如，这真的重要吗？如果有大量的模型存在，而且我们不去限制它们、不去监管它们，让这些市场去竞争。在搜索引擎的早期，我们就有付费收录，公司必须付钱才能出现在里面，查马斯，全都是你描述的那种交易。而所有做那些交易的搜索引擎，对消费者和客户来说体验都糟透了。于是大家都觉得，你知道吗，这不如谷歌好，大家都转投更好的模型和更好的服务商去了。如果我们不从中作梗、把政府排除在外，这里难道不也会发生同样的事情吗……
<details><summary>Original English</summary>
>> Right? if they have a deal with JP Morgan but not with City Bank, you'll just never know. And so you'll ask a question something about mortgage rates or interest rates and you'll get all kinds of stuff that you don't understand. And then the downstream part of this which is even more problematic is it's not clear to me that they're going to capture the actual fingerprint of what they did. So if you believe that something was done in a shady way, you're supposed to be able to go to them or regulators should be able to go to them and say, "Show me the trace of that model run in that exact moment that generated that output. Convince me why that that wasn't nerfed on purpose or manipulated."

And there's all kinds of ways in which they can hide the cheese on that. So I think that all of that body of stuff sacks happens now because if you're if you're an emergent company what you should be doing is knocking on anthropic door saying let's do a deal I'll give you half the equity and why don't you just direct people to me and they'll say well economics are not what I care about what is your philosophy on life on morality on all of these social issues and one company will say it's a another company will say it's B, they'll favor A over B and then all kinds of stuff can happen underneath the hood. That's what's scary. Let me just ask my free market view. Like, should that matter? If there's a bunch of models out there and we don't restrict them and we don't regulate them, let these markets compete. We had paid inclusion in the early days of search engines and the companies had to pay to be in there and there all those sorts of deals you're describing, Chimamoth. And all the search engines that did those sorts of deals, they sucked for consumers and customers. So everyone was like, you know what, this isn't as good as Google and everyone went over to the better model and the better provider. Isn't that what's going to happen here if we don't get in the way keep the government out of it
</details>

>> 而且他们没有在沟通交流。
<details><summary>Original English</summary>
>> and they're not communicating.
</details>

>> 这个观点很好。
<details><summary>Original English</summary>
>> It's a great point.
</details>

>> 你漏掉了一点，那就是在 Anthropic 进行强制监控和削弱其模型的同时，达里奥写了一篇新的博文。
<details><summary>Original English</summary>
>> You're missing one piece of it, which is at the same time that Anthropic was engaging in mandatory surveillance and nerfing its models. Daario wrote a new blog post.
</details>

>> 天哪。称透明度已经不够用了，我们需要建立一个像 FAA 或者可能像 FDA 这样的新监管机构来审批所有的模型。所以你的前提假设在那种情况下是成立的。是的，如果你能去别的地方获取问题的答案，那么你就会有替代选择。但就在 Anthropic 从事这种潜在的反竞争行为的同时，他们想要限制你的选择。光是在自由市场中获胜对他们来说是不够的。他们正在呼吁……
<details><summary>Original English</summary>
>> Oh god. saying that transparency was no longer good enough that we needed to have a new regulatory agency like an FAA or maybe an FDA to approve all models. So your presumption there is correct. Yes, if you could go somewhere else to get your questions answered, then you would have alternatives. But at the same time that Anthropic is engaging in this potentially anti-competitive behavior, they want to restrict your options. It's not good enough for them just to win in the free market. They're calling on
</details>

<!-- chunk 3/13 -->

让政府来进行监管，以此阻止潜在的竞争对手，并限制你能访问的模型数量。

<details><summary>Original English</summary>
 the government to regulate and stop potential competitors and limit the number of models that you have access to.
</details>

>> 他们为什么要这么做？他们为什么会想要受到监管？答案超级简单。他们不是想要自己被管，他们是想把那种监管套在开源上，而开源根本无法做到合规。但这将是破坏和阻碍开源模型的一个极好方式。是的，因为开源没有被监管的能力。所以这就像是对在你本地机器上最大限度刷 token 的一种先发制人打击。

<details><summary>Original English</summary>
>> Why would they do that? Why would they want to get regulated? The answer super simple. They don't they want to apply that regulation to open source which is impossible. But this would be a great way to scuttle and sandbag open- source models. Yes. Because they don't have the ability to be regulated. So it's like a preemptive strike against token maxing on your local machine.
</details>

### 算力壁垒与开源算力困境

>> 两年前，我和一个合伙人在亚利桑那州买了 2,000 英亩土地。我们拿到了分区规划许可，拿到了审批。所以，我们获批建造一个 2 吉瓦的数据中心。我当时以为，这就是那种转手倒卖给黑石（Blackstone）、博枫（Brookfield）这类机构，或者倒给谷歌这类公司的时候了，让他们去开发。但我现在的结论是，我觉得我不能这么做。原因是，我认为除非我们把大批量的算力直接对准弗里德伯格（Freeberg）所说的方向，否则萨克斯（Sacks）说的以及杰森（Jason）刚才说的就会发生，我们就会失去开源。明确说吧，当你看到获取开源模型的长尾访问时，它相对来说是微不足道的。

大部分兆瓦级的电力仍然流向大模型。绝大多数仍旧属于那些巨头。所以我得出的结论是，我认为我们可能不得不被硬拉着去建这 2 吉瓦，而且我刚在另一个地方对另外几个吉瓦发出了要约，因为我觉得，如果你能拿下 3 吉瓦，并真正为开源打造出深厚、充沛的访问渠道，我们就必须去做这件事。作为社区，我们得去做——现在我并没有做这件事的资金，因为实话实说，大家，现在 1 个吉瓦就要花 1,000 亿美元。

<details><summary>Original English</summary>
>> Two years ago, I bought 2,000 acres in Arizona with a partner. We got it zoned. We got it approved. So, we're allowed to build a 2 gawatt data center. And I thought that this was the moment where you just turn around and you flip it to the Blackstones, the Brookfields of the world, to the Googles of the world. Let them develop it. And I've come to the conclusion that I don't think I can. And the reason is because I think that unless we direct large swats of compute exactly at the direction that Freeberg says, what Sax says and what Jason just said will happen and we won't have open source. So just to make it very clear when you look at the long tale of access to open source models, it's relatively minuscule.

Most of the megawatts are still directed to the big models. Most of them, the overwhelming majority still goes to the big guys. And so I'm coming to the conclusion that I think we may just be dragged into having to build two gigawatts and I just put in an offer for another gigs in a different place because I'm like if you could take 3 gigawatts and now actually create a deep liquid access to open source we're going to have to do it. We as a community now I don't have the money to do that because just to put it out on the table a gigawatt now costs a hundred billion dollars guys.
</details>

>> 好吧。所以这里还存在一个巨大的资本护城河问题。萨克斯，即使我们想去支持并给开源模型社区注入生机，我到底上哪儿去弄这 1,000 亿？我刚启动这个项目时，大概是四五十亿，现在翻了 20 倍。所以如果要开发全部 3 个吉瓦，我得筹集 3,000 亿。我显然没有 3,000 亿美元。那我们大家该怎么办？如果监管方面再来个突然釜底抽薪、抽走梯子，我们将被困在单一类别的模型和一套规则中，我们根本不知道如何运作——

<details><summary>Original English</summary>
>> Okay. So there's a huge capital mo that's a problem here as well. Saxs which even if we wanted to go and endorse and breathe life into the open source model community where the hell am I going to come up with hundred billion now when I started this project it was like four or five billion and it's increased by 20x. So if you want to get all three gigawatts developed I have to come up with 300 billion. I don't have obviously I don't have $300 billion. So what are we all supposed to do? And then if you get the rug pull and the ladder pull on the regulatory side, we are going to be stuck with one class of models and one set of rules and we won't understand how to operate
</details>

>> 在美国。

<details><summary>Original English</summary>
>> in the US.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 是的。世界其他地方不会受限。但在美国——

<details><summary>Original English</summary>
>> Yeah. The rest of the world won't be limited. But in the US, the
</details>

>> 世界其他地方将能够正常运转——

<details><summary>Original English</summary>
>> rest of the world will be able to operate
</details>

>> 而且你将能在自己的苹果芯片上运行这些，你知道的——

<details><summary>Original English</summary>
>> and you'll be able to run these on your Apple silicon, you know,
</details>

>> 而且我们已经看到中国在生物科技领域疾速向前。他们在材料科学上狂奔。他们在新型工业体系上狂奔。这种能力上的失衡将会造成不公平的优势，到那时，我们的劳动力和经济才是真正处于危险之中。

<details><summary>Original English</summary>
>> and we're already seeing China race ahead in biotech. They're racing ahead in material science. They're racing ahead in new industrial systems. the capabilities that are going to be kind of lopsided is going to create an unfair advantage and that's when our workforce and when our economy is truly at risk.
</details>

### 基因组开源模型与科研优势

>> 嘿，弗里德伯格，你们不是在基因组学方面使用了一个开源模型吗？科利森（Collison）他们不是发布了一个吗？你能聊聊吗？

<details><summary>Original English</summary>
>> Hey Freeberg, isn't it true that you guys use a open source model for genomics? Didn't the Collison put out one? Can you talk?
</details>

>> 那个非常棒。阿克研究所（Ark Institute）摄取了他们能获取到的全世界所有的基因组数据，它基本上就是一个基因组语言模型。所以在我们的植物育种项目中，当我们无法通过经验、无法从历史数据中得知植物中某个特定基因变异是好是坏时，我们正试图弄清它到底是有益还是有害。你可以把它输入到这个模型中，该模型会观察 DNA 字母的顺序，并判定：“嘿，这是一组好的字母还是坏的字母。”这几乎就像是在判断，那是好的英语还是坏的英语？它已经掌握了 DNA 的语言，因为它能看到那些字母在其他生物体中连续出现的概率等等。所以它是一个非常强大的工具。我们引入了它并在实际使用，其他人也在引入并非常积极地使用它。所以它作为一项投入，成了我们植物育种项目的一部分。这是一个很好的例子：一个社区——在这个案例中是科利森兄弟等人出资资助这项研究，并产出了这个开源模型。我认为我们看到未来会有更多这类成果涌现，它在抗衡封闭专有模型生态系统时创造了非常巨大的优势。所以，我们越能在美国支持、推广并看到这种模式发挥作用，在政府以及那些包揽一切的大模型提供商推行自我监管时，我们就越不会陷入劣势。

<details><summary>Original English</summary>
>> It's great. And the Ark Institute ingested all the world's genomic data that they could get access to and it's it's a genome language model basically. So in our plant breeding program, we're trying to figure out whether a particular variant of a gene in a plant is good or bad, if we don't know from empiricism, from data historically whether it's good or bad. So you can feed it into this model and this model will look at the order of the letters of the DNA and determine, hey, that's a good set of letters or a bad set of letters. It's almost like, is that good English or bad English? It's figured out the language of DNA because it sees the probability of those letters being in a row in other organisms and so on. And so it's a very powerful tool. So we've taken that in and we're using it and others are taking it in and they use it very actively. So it's part of our plant breeding program as an input. It's a good example where a community in this case the Collisons and others put money behind it to fund this research and output this open- source model. And I think we see more of that kind of coming down the pipe which creates a a very great advantage against the closed proprietary model ecosystem. So the more of this we can kind of support proliferate and see work in the United States, the more we're not going to be disadvantaged of the government and self-regulation happens with all the big model providers that are trying to do everything.
</details>

### 达里奥的立场、人才聚集与安全顾虑

>> 我觉得我们花一分钟来给对方的论点做个最强辩护（steelman）也很重要。如果你是达里奥（Dario），他显然深受某种单一视角影响，我觉得他写那些 5,000 字的长篇博文，简直像得了“AI 精神病”，而且他坚信自己正在打造一个科学怪人式的工具。但如果你真的相信自己制造出了极其强大的东西，并且担忧人们可能会滥用它——我认为他心里确实深信不疑，这要么是夸大妄想，要么是他确实看到了极其强大的东西，并且认为这很危险。因此，“我要先按住它。我要先把它给选定的少数合作伙伴，以强化网络安全。然后我要谨慎地把它向我们的用户群体推出，并且会告知他们。”他显然没有把这一点沟通好。“对你来说，使用它是可选的。你可以继续使用你的旧模型。你没有被强迫使用这个，但由于它太强大了，我们要时刻盯着它。是的，在我们的全面排查中，可能会抓到大卫·弗里德伯格（David Freeberg）正在试图培育更好的土豆，这可能会触发一堆警报，但他不必非得用这个模型。他可以去找开源模型。他可以用科利森兄弟的模型。他可以用我们较老的模型。但在一段时间内，我们就是要盯紧这个模型，因为我们知道它让人感觉有点危险。”现在看来，他确实显得极度夸张，而那些夸大妄想之类的表现，让我不解他为什么要以那种方式沟通。话虽如此，AI 研究人员中 90% 的人，以及这个行业里最优秀的人才，有 80% 到 90% 的人想法和达里奥完全一样。这就是为什么他能赢。如果你从事 AI 工作，你很可能也有着“自己正在创造上帝”的狂妄幻想，并想为达里奥工作。这就是为什么所有优秀人才都跑去为他工作。这就是为什么他正在赢得竞争。他的信念体系与那些顶尖 AI 人才产生了共鸣。当然，他们中有些人也是自由意志主义者、信奉自由市场。他们想为埃隆（Elon）和 Grok 工作。有些人只想拿最高的薪酬包，那就去为萨姆·奥特曼（Sam Altman）工作。但我确实认为这里面有值得为其做最强辩护的合理成分。Meta 在 Llama 上真的搞砸了。我是说，如果他们当年推出一个真正优秀的——

<details><summary>Original English</summary>
>> I think it's important we take a minute to just steelman the argument as well. If your Daario who has clearly been oneshotted, I think he's got like AI psychosis with these like 5,000word blog posts and he believes he's building this franken site of a of a tool. But if you did believe you built something that's extremely powerful and you have concerns that people might misuse it, I think he actually believes that he and these are either delusions of grandeur or he actually has seen something that's incredibly powerful and he believes this is dangerous. Therefore, I'm going to hold it. I'm going to you give it to a select group of partners to tighten up the cyber security. Then I'm going to roll it out cautiously to our user base and I'm going to let them know. And he obviously didn't communicate this well. This is optional for you to use it. You can keep using your old model. You are not forced to use this, but because it's so powerful, we're going to keep our eye on it. And yes, we might in our drag net catch David Freeberg trying to make better potatoes and it might send off a bunch of alarms, but he doesn't have to use this. He can go find an open source model. He can use the Carlson Brothers model. He can use our older models. But for some period of time, we're just going to keep an eye on this model because we know that it feels a little dangerous. Now, he does seem to be extremely hyperbolic and the delusions of grandeur, all that kind of part of it makes me wonder why he's communicating in the way he's doing it. That being said, 90% of AI researchers and the most talented people in this industry, 80 90% of them think exactly like Daria. That's why he's winning. If you work in AI, you probably are aligned with these delusions that you're creating God and you want to work for Daario. That's why all the talented people went to work for him. That's why he's winning. His belief system resonates with those elite AI talent. Now, some of them are also libertarian, free market. They want to work for Elon and Grock. Some of them want to just get the biggest pay package. Go work for Sam Alman. But I do think there is a steelman here. Meta really fumbled this with Llama. I mean, if they had landed a really good
</details>

>> 运转良好的开源模型，我们当时也讨论过这个，我们说过扎克（Zuck）需要从博弈论的视角来看待这件事。你怎么去实行“焦土政策”，怎么去提供一个可行的开源模型，并让它并驾齐驱，那是两年前的事了，对吧？真是搞砸了。

<details><summary>Original English</summary>
>> working open source model, we talked about this as well and we said Zuck needs to view this through the lens of game theory. How do you scorch the earth and how do you make a viable open-source model available and make it neck and neck and this was two years ago, right? What a fumble.
</details>

>> 把其他所有人的利润空间榨干。

<details><summary>Original English</summary>
>> Take the margin out for everybody else.
</details>

>> 是的，榨干利润，让它商品化，然后是的，拥有最好的开源。我能——

<details><summary>Original English</summary>
>> Yeah, take the margin out, make it a commodity and yeah, have the best open. Can
</details>

>> 我能回应一下你关于达里奥的看法吗？我……我认为，因为我从许多我真正尊敬的人那里听到过关于模型所带来的能力的担忧。你知道，当我们发现原子可以被分裂时，你可以制造核能，为世界带来实际上无限且廉价的能源，但你也可以制造原子弹。如果你想想这些模型是什么——

<details><summary>Original English</summary>
>> I can I just respond to your comment about Daario? I I think because I've heard this from a number of people that I really do respect on their concerns about what models enable. You know, when when we discovered that how the atom could be split, you could make nuclear energy and have effectively unlimited cheap energy for the world, you could also make an atomic bomb. If you think about what the models are,
</details>

>> 我们两样都造了。

<details><summary>Original English</summary>
>> we did both.
</details>

>> 我们两样都造了。

<details><summary>Original English</summary>
>> We did both.
</details>

>> 没错。

当时有很多科学家、利他主义者对原子弹的进展非常担忧，并反对它，他们当中其实有人积极参与了曼哈顿计划，并在曼哈顿计划之后非常坚定、非常大声地表达了自己的看法。我认为我们现在正处于这样的时刻，即这类工具存在武器化的潜力。我认为存在三类武器：网络武器、实体武器，以及生化武器。而我们能——

<details><summary>Original English</summary>
>> That's right. And there was a lot of scientists, altruists who were very concerned about the progress on the atomic bomb and fought back against it who were actually active in the Manhattan Project and post the Manhattan Project express their opinions very soundly, very very loudly. And I think that's the moment we're in right now that there is a weaponization potential of these sorts of tools. I I would argue that there's three kinds of weapons. There's cyber weapons, there's physical weapons, and there's bioweapons. And we can
</details>

<!-- chunk 4/13 -->

### AI 工具的监管边界与风险认知

坐在

这里，

去分析

这些工具

如何

能被用来

体现出

制造更优良

物理武器、

制造新型

网络武器

以及制造新型

生化武器的

优势。

但事实是，

允许进行

这种武器化的

能力，

正是我所描述的

同样的那些能力——

它们可被用来

治愈癌症、

生产更多粮食，

可被用来

制作软件工具，

为人们

带来非凡的杠杆效应，

提高他们的收入，

让每个人

都有能力成为创业者、

赚得数百万美元

并过上美好的生活。

同样的

工具是并存相随的。

从根本上说，

我认为重点并不在于

限制获取这些工具的途径，

遗憾的是目前呈现出的正是这种局面。

但各种限制措施

以及任何监管、

任何监控，

都应当围绕着

工具在

制造武器方面的体现

以及工具的

武器化来组织。

如果我们回顾

曼哈顿计划，

我们知道

答案是什么。

技术在本质上是

确定性的。

凡是可能的事物，

都至少会被

尝试一次。

因此我们

已经将这个东西放出了魔盒。

所以，认为我们突然之间就能

设法把它重新收回去、

并且我们要让一个普通公民

或一组普通公民

来判定什么可以提供以及向谁提供的

这种想法，是荒谬的。

<details><summary>Original English</summary>
sit here and diagnose how these tools can be used to manifest advantages for creating better physical weapons, for creating novel cyber weapons, and creating novel boweapons. But the truth is that the cap capabilities that allow that weaponization are the same capabilities that I'm describing that can be used to cure cancer, to make more food, that can be used to make software tools that create extraordinary leverage for people, that increase their income, that give everyone the ability to be an entrepreneur and make millions of dollars and live a good life. The same tools are hand in hand. And fundamentally I don't think it's about restricting access to the tools which is unfortunately how it is being manifest. But the restrictions and any regulation any observation should be organized around the manifestation of the tools in creating weapons and uh weaponization of the tools. If we go back to the Manhattan project, we know what the answer is. Technology is fundamentally deterministic. Whatever is possible will be tried at least once. And so we've already let this thing out of the box. So this idea that all of a sudden we can manage to get it back in and we're going to let a private citizen or a set of private citizens adjudicate what and to whom is insane.
</details>

我认为应该以某种方式予以判定的，是其产出。我们已经有了产品责任法。我们已经有了将设计武器定为违法的法律。我们已经有了针对网络间谍活动、网络攻击和黑客攻击的法律。我们有针对制造生化武器的法律。我认为关键在于这些法律的执行，在于能够对该技术的那些用途进行追踪和早期评估的机制。我在这里并不是想显得天真。我承认必须要有安全护栏，必须在这些系统中设置阶段卡点。但限制系统本身，就是在剥夺我们的经济机会、创造就业的机会，以及这些工具所能促成的改变世界的机会。因此我认为，试图在技术可获取性的一开始就设置所有这些关卡，这种做法的方向是错误的。想象一下，如果我们对计算机也这样做会怎样。顺便说一句，他们曾试图对互联网这样做，还记得吗？呃，曾经有过这方面的尝试。

<details><summary>Original English</summary>
I think it's the output that needs to be adjudicated in some manner. We already have product liability laws. We already have laws that make it illegal to design weapons. We already have laws against cyber espionage and cyber attacks and hacking. We have laws against creating bioweapons. I think the enforcement of those laws, the mechanism by which there can be tracking and early estimation of those uses of the technology. I'm not trying to be naive here. I recognize there have to be guard rails and there have to be stage gates put into these systems. But limiting the systems themselves is denying us both the economic opportunity, the job creation opportunity and also the world changing opportunity that these tools can enable. So I think that we're going about it the wrong way by trying to create these gates all the way up front on the technology being available. Imagine if we did this with computers. By the way, they tried to do this with the internet, remember? And um there had been efforts.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 弗里德伯格，你能想象如果互联网按以下方式运行吗？你输入一个网址，按下回车键，然后有人来决定是把你送到那个网站还是另一个不同的网站。

<details><summary>Original English</summary>
>> Could you imagine, Freeberg, if the internet worked in the following way? You would put in a URL, you'd hit enter, and then somebody decides whether to send you to that website or a different website.
</details>

>> 那就是中国。那就是中国的防火墙。没错。

<details><summary>Original English</summary>
>> That's China. That's the firewall in China. That's right.
</details>

>> 或者就像在谷歌里，你搜索某样东西是因为你想探寻基本事实，而它仅凭它认为你是谁，就直接决定给出哪些网站。

<details><summary>Original English</summary>
>> Or like in Google, you search for something because you want to get to ground truth and it just decides based on who it thinks you are, what sites get.
</details>

>> 那正是我们——你说得完全正确。对。而我们现在所讨论的、目前关于人工智能监管所争论的，恰恰就是你所说的那种表现形式。就是让人在前端阶段性设卡把关什么能看、什么不能看，你能做什么、不能做什么，而不是体现出一种规定不能制造武器的监管方案——比如这才是我们需要聚焦的地方。武器方面的问题在于，在有人使用了武器之后再去动用司法体系和法律，可能并不完全是最好的手段。如果你看一下化肥炸弹——我们在这里有点用了很多比喻，但在俄克拉荷马城事件之后，我们监管了化肥的销售。我们在化肥中植入了身份标识。

我们拥有各种各样的后台系统来防止人们制造化肥炸弹。如果把那个类比用在这里，他拥有这种能力，他正在销售化肥，他正在销售这些网络武器，而且他是一家私营公司。他有权表示“我有顾虑”。我只是在替他做最强辩护。这不一定是我的观点，但对它进行最强辩护是很重要的。这似乎是一种非常简单的方法，可以保护他们的公司免于因为纵容某人真正制造了炸弹并把某些玩意儿炸上天而遭到起诉。所以，作为一家私营公司，他有权这么做。

<details><summary>Original English</summary>
>> That's what we're You're exactly right. Right. And what we're what's what's being debated today with respect to regulation on AI is exactly that manifestation that you're talking about. It's the ability to let people stage gate up front what can and can't be seen, what you can and can't do versus manifesting a regulatory scheme that says you cannot create weapons like which is what we need to focus on. The thing with weapons is using the justice system and laws after somebody's used a weapon may not exactly be the best technique. If you look at fertilizer bombs, and this is we're getting like uh we're stretching a lot of metaphors here, but OK after Oklahoma City, we regulated the sale of fertilizer. We put IDs into fertilizer. We have all kinds of back-end systems to keep people from making fertilizer bombs. If you use that analogy here, and he's got this ability, he's selling fertilizer, he's selling these cyber weapons, and he's a private company. It's his right to say, I have concerns. I'm just steel milling him. It's not necessarily my opinion, but it's important we steel man it. It seems like a very simple way to protect their company from getting sued for enabling somebody who actually creates a bomb and blows some [ __ ] up. So, he's got the right to do that as a private company.
</details>

### KYC 机制与监管俘获的争议

>> 是的，你提出了一个极佳的例子。好的，化肥就是一个绝佳的例子。你知道当你尝试购买化肥时会发生什么吗？你必须出示你的身份证件。这其中存在一种形式的“了解你的客户”（KYC）。所以真正的问题在于，我认为当你自己不去实施 KYC，却又抱怨有人强加安全护栏——而随后你又可以对这些护栏施加影响——我认为你这种做法是非常诡计多端的。这很狡诈。你不应该说那种话。Anthropic 明天就可以实施 KYC，但它没有。它可以让所有这些模型保持开放。弗里德伯格本应该能够去找 Anthropic 并表示：“我是大卫·弗里德伯格。这是我所做的工作。这是我愿意缴纳的安全保证金。这是我所有员工的姓名和地址。把 Fable 5 给我，别削弱我的功能。”但他做不到。那是一项技术决定还是一项法律决定？那是 Anthropic 做出的技术决定。但我对他们做出那项决定没有意见，因为我是个崇尚自由市场的人。所以我对他们的做法没有意见，但你知道这意味着什么吗？我不会成为其客户，这挺好。那意味着你会有其他选择。你所遗漏的部分在于，这是一家万亿美元市值的公司，可能斥资数十亿美元去推行一项监管俘获议程，而这一议程将会剥夺你获取那些替代模型的途径。

<details><summary>Original English</summary>
>> Yeah, you're bringing up an excellent example. Okay, the fertilizer is a perfect example. You know what happens when you try to buy fertilizer? You have to show your ID. There is a form of KYC that happens. So the real thing is I think that when you don't implement KYC on your own and yet belly ache about having somebody impose guard rails that then you can shape, I think you're being very sneaky. It's tricky. You shouldn't be saying that kind of stuff. Anthropic could implement KYC tomorrow, but it does not. It could leave all of these models open. Freeberg should be able to go to Anthropic and say, "I'm David Freeberg. Here's what I do. Here's a security bond I'm willing to post. Here's the names and addresses of all my employees. Give me Fable 5 and don't nerf me. He can't do that. Is that a technical decision or a legal decision? It's a technical decision by Enrop. But I'm fine with them making that decision because I'm a free market guy. So I I'm fine with them doing and but you know what it means? I'm not going to be a customer, which is fine. That's and that's means there'll be other options for you. The part that you're missing is that this is a trillion dollar company that's spending potentially billions of dollars on a regulatory capture agenda which is going to deprive you of access to those alternative models.
</details>

>> 而且有一位创始人正在外界以极度夸张的方式描述这些风险。他们的议程走向非常明确，那就是去禁止开源模型。那么你的替代方案将会是什么？我们将被迫受制于大约一到三家公司，也许是两家。将会出现 AI 垄断或双寡头垄断，他们将与某个新的政府机构——该机构与他们的公司之间将形成旋转门——共同决定谁可以获取什么能力，而且他们将监视你、对你进行画像，决定你是否配得上拥有它；如果他们出于无论何种原因认为你不配，那么你就会，对，你就会遭遇最坏的解读，那是对他们意图的最坏解读，而这一切如今已经在此上演了。

<details><summary>Original English</summary>
>> And you've got a founder who's out there describing these risks in a very hyperbolic way. And it's very clear where their agenda is headed, which is to banning open source models. So what is your alternative going to be? We're going to be stuck with somewhere between one and three companies, maybe two. There'll be a AI monopoly or duopoly and they're going to decide along with some new government agency which will be a revolving door to their companies who has access to what capabilities and they're going to surveil you profile you decide whether you deserve this and if they think that you don't for whatever reason then you'll be right you'll be the worst interpretation of it that's the worst interpretation of their intent it's here today
</details>

>> 我认为萨克斯是对的，我认为萨克斯是对的，而且我认为缺乏 KYC 就是明证。如果你如果没有那个议程，你昨天就已经实施 KYC 了。

<details><summary>Original English</summary>
>> I think Sax is right I think Sax is right and I think the lack of KYC is the tell. If you if you did not have that agenda, you would have implemented KYC yesterday.
</details>

>> 难道不是，我认为要使用这个模型，你必须拥有一个绑定了信用卡的账户，所以他们掌握着某种基础层面的 KYC。

<details><summary>Original English</summary>
>> Don't I think in order to use this model, you have to have an account with a credit card in it so they have some basic level of KYC.
</details>

>> 那不是 KYC。

<details><summary>Original English</summary>
>> That is not KYC.
</details>

>> 我说的是某种基础层面的 KYC。他们知道是谁在用——

<details><summary>Original English</summary>
>> I said some basic level of KYC. They know who's using
</details>

>> 那连某种基础层面的 KYC 都算不上。那不过就是一张信用卡和一个该死的电子邮箱地址。

<details><summary>Original English</summary>
>> that is not even some basic level of KYC. That's just a credit card and a [ __ ] email address.
</details>

### 模型降级现场测试与安全主义

>> 反正我现在榜上有名了。看看这个。我向它询问了相关法规。把这个调出来，尼克。在你们说话的时候，我向它询问了关于化肥的法规，看看它是怎么说的。这还是最新的模型呢。噢不，它切换了。它把我从 Fable 降级了。我仅仅因为问了一个非常简单的问题就刚被降级了，它告诉我——你看到它在思考过程中说了什么吗？我问的是关于化肥炸弹法规之类的问题，它说“我正在考量这里的上下文。用户是一名风险投资家兼播客主，正在询问关于化肥炸弹法规的问题，这可能源自正当的研究兴趣，例如监管政策、供应链等等等等。我可以讨论监管格局”，但随后它就把我降级了。所以，我现在和你一起被记入数据库了。

<details><summary>Original English</summary>
>> Anyway, I I'm now on the list. Check this out. I asked it about the regulations. Pull this up, Nick. I asked it about the regulations on fertilizer while you were talking and look what it said. This is the latest model too. Oh no, it switched. It downgraded me from Fable. I just got downgraded for asking a very simple question and it told me did you see what it said in its thinking? The I asked it like fertilizer bomb regulations said I'm considering the context here. The user is a VC and podcaster asking about fertilizer bomb regulations which could stem from a legitimate research interest like regulatory policy, supply chain blah blah. I can discuss the regulatory landscape, but then it dropped me down. So, I'm in the database with you now.
</details>

>> 是真的吗？它刚才真的这么做了？

<details><summary>Original English</summary>
>> Is that right? Did it really just do that?
</details>

>> 是的。在屏幕上展示出来。看看它刚才做了什么。我心里想，不知道我能不能得到这个。我并没有问它如何制造炸弹，但我像是在问它一个敏感的——

<details><summary>Original English</summary>
>> Yeah. Show it on the screen. Look what it just did. I I was like, I wonder if I can get this. I didn't ask it how to make a bomb, but I was like asking it a spicy
</details>

>> 完蛋了。我刚才证实了这个观点。

<details><summary>Original English</summary>
>> cooked. I just proved the point.
</details>

>> 听着，我的意思是，我认为——

<details><summary>Original English</summary>
>> Listen, I mean, I think
</details>

>> 它直接把我降级了。我不能询问有关化肥监管的问题。而现在达里奥的——是 Anthropic。他们盯上这里了。

<details><summary>Original English</summary>
>> he just dropped me down. I can't ask about fertilizer regulation. And now Daario's it's anthropic. They're here.
</details>

>> 噢，我的老天。

<details><summary>Original English</summary>
>> Oh my lord.
</details>

>> 我真的认为，如果保守派和自由意志主义者顺从这种监管俘获的安全主义议程，而没有真正意识到其中牵涉到的利益远不止于此，那他们就是在拿自己的未来做抵押。我们看到了在 2020 年代初的社交媒体大战期间发生的事情，对吧？“安全”的定义被扩大到包含了微冒犯、

<details><summary>Original English</summary>
>> I really think that conservatives and libertarians are mortgaging their futures if they go along with this red capture safetist agenda without really realizing that there's so much more to it at stake. We saw what happened during the social media wars in the early 2020s, right? The definition of safety was expanded to include things like microaggressions,
</details>

>> 安全空间、

<details><summary>Original English</summary>
>> safe space,
</details>

>> 心理安全之类的事情。如果你基本上表达了一个别人——你所知道的边缘化群体人士——认为造成伤害的想法，那么你就可能遭到审查。明白吗？你就被剥夺人格了。

<details><summary>Original English</summary>
>> psychological safety. If you basically conveyed an idea that somebody else that you know marginalized person thought was hurtful, then you could be censored. Okay? You were depersoned.
</details>

<!-- chunk 5/13 -->

### AI安全监管介入点与开源模型的扩散

你拥有银行账户或参与支付的权利被剥夺——你被取消银行服务。你参与支付或发放工资的权利可能会被剥夺。

<details><summary>Original English</summary>

Your right to have bank accounts or to engage in payments was take you get debanked. Your right to engage in payments or payroll could be taken away.

</details>

>> 我们在人工智能领域正朝着这条道路走去，但它的威力将无比巨大，对吧？我想，总结这一切的话，我们必须保持警惕。而且我觉得，Freeberg在这个播客里有时会感到不安全。

<details><summary>Original English</summary>

>> We're headed down this path with AI, but it's going to be infinitely more powerful, right? We need to be vigilant, I guess, would be the the the summation of all this. And Freeberg feels unsafe in this podcast, I think, sometimes.

</details>

>> 顺便说一下，在安全方面其实是可以有所作为的。所以，Freeberg，你虽然没提到这个，但我很想听听你的看法。最近，主要的AI实验室以及许多其他签署方发出了一封支持信，题为支持对合成核酸进行强制筛查和记录留存。其核心内容基本上是说，如果你向实验室下订单生产一段合成DNA或RNA序列，他们现在就已经必须对照数据库进行筛查，以确保他们没有制造出……

<details><summary>Original English</summary>

>> Well, there's by by the way, there are things you can do on the safety side. So, Freeberg, you didn't mention this, but I'd be curious to get your your take. So, the major AI labs along with lots of other signatories sent this letter recently in support of it's called in support of mandatory nucleic acid synthetic screening and recordkeeping. And basically what it what it says is that if you make an order to go to a lab to manufacture a sequence of synthetic DNA or RNA, they already have to check it against a database to make sure that you know they're not creating

</details>

>> 生物武器，

<details><summary>Original English</summary>

>> a bioweapon,

</details>

>> 生物武器、埃博拉病毒之类的。

<details><summary>Original English</summary>

>> a boweapon, Ebola, whatever.

</details>

>> 没错。那是基于2009年《国际基因合成联盟》的一项协议，各大实验室在其中同意制定并实施防止滥用的自愿性防护措施。这在我看来是合理的。而现在他们想做的是将其法律化。所以他们已经有超过15年的时间来调整这个体系并让它运转良好。几乎每个人都在自愿遵守。现在他们说我们应该将其强制化。好吧，这在我看来很合情理。所以回到Freeberg提出的关于在哪个阶段进行干预的问题，也许干预不应该发生在谁能使用模型的层面，而是发生在你试图将其转化为物理世界输出的环节。顺便说一句，许多寡核苷酸合成公司，也就是制造这些核酸序列的公司——当你在实验室为了某种实验订购RNA或DNA时，全世界每个实验室都会这样做——那些公司的所有首席执行官也都签署了这封信，表示由于当前存在的种种恐慌煽动，他们希望将其写入法规。这项确保此类事情不会发生的努力已经持续了数年，但他们基本上只是在强调并指出：嘿，我们可以把这个流程自动化；我们可以让它成为监管或立法程序的一部分，你们怎么定都行，因为我们做这个已经轻车熟路了。而且这是一个设置防线的绝佳环节，因为他们已经让它变得快捷高效，不会阻碍科学研究。

<details><summary>Original English</summary>

>> Yep. that is based on an agreement called the international gene synthesis consortium of 2009 in which all the major labs agree to develop and implement voluntary safeguards against misuse. That makes sense to me. And now what they want to do is codify that. So they've had, you know, over 15 years to dial in the system and make it work. Almost everyone abides by it voluntarily. Now they're saying we should make it mandatory. Okay, that seems reasonable to me. So to Freeberg's point about at what stage do you intervene, maybe it's not at the level of who gets to use the model, but if you try to turn it into output in the physical world. And by the way, a lot of the oligosynthesis company, the companies that make these nucleic acid sequences, when you order RNA or you order DNA to use in your lab for some sort of experiment, which every lab in the world does, all those CEOs have also signed on to this letter saying that they'd like to codify it because of all the fear-mongering that's going on. There's already been this effort for years now, for a number of years to ensure that this sort of thing doesn't happen. but they're just basically underlining it and highlighting like, hey, we can automate this. We can make it part of a regulated or legislative process, whatever you guys want, because we're already comfortable doing it. And it's a it's a good place to put a safeguard because they've made it fast. They've made it efficient and doesn't hold up research.

</details>

>> 所以，我认为这类想法可以推广到其他令人担忧的领域，但输出端与输入端、与访问权限端相比，我认为是截然不同的环节。我们且看这一切最终如何演变，但在我们讨论这个问题的同时，显然有人正在推动某种市场结构化的努力，

<details><summary>Original English</summary>

>> So, I think these sorts of ideas can extend into these other areas of concern, but the output, I think, is quite a different place than the input than the access. We'll see how this all shakes out, but there's clearly some market structuring effort underway as we're talking about this,

</details>

>> 对吧？但我认为这表明你可以进行干预并设置护栏的地方有多种选择。不必非得采取这种非常粗暴的方式——比如向fable询问线粒体、癌症或GLP1药物就受到限制，这看起来完全是一刀切的极宽泛限制。在流程更下游的地方基本上是可以介入的，而且那样做对言论自由和单纯的门禁式把关构成的风险会更小。究竟谁能获得这些能力？

<details><summary>Original English</summary>

>> right? But I think what it points to is that there's multiple places where you can intervene and put guard rails on. It doesn't have to be in this very crude way of you ask fable about mitochondria or cancer and GLP1s, which just seems like an incredibly broad restriction. There are places further down where you could basically intervene and that would pose less of a risk to freedom of speech and just gatekeeping. Who's going to have access to these capabilities?

</details>

>> 谁来监督监督者？是谁让Dario全权掌管这一切的？我认为这是一个非常合理的问题，我们应该对此保持警惕。

<details><summary>Original English</summary>

>> Who gets to watch the watchman? Who put Dario in charge of all this? I think is a very valid question and we should be vigilant about it.

</details>

>> Freeberg，你认为那个arc模型的气数已尽了吗，既然它是开源的？

<details><summary>Original English</summary>

>> Freeberg, do you think the days of that arc model are numbered because it's open source?

</details>

>> 每个人都复制了它。所以，每个人都持有一份副本，就像这些模型已经存在了一样。我认为这是大家需要理解的一个重要部分：那种认为你可以所谓“监管”、削减规模或关闭人工智能的想法是不切实际的。这些模型已经被投放到了世界上。就像出版一本书一样，一旦书被印刷出来，任何人都可以用自己家里的施乐复印机去复印并使用它。所以在语言模型的潜力方面，我们已经跨过了卢比孔河。开源的模型已经完全公开、完全发表，任何人都可以获取和使用它们。然后人们可以拿到它们，可以进行演进，也可以使用他们自己的数据。它已经散布在外了。你无法阻挡这种能力，而它将对世界极其有益。因此，我们确实必须重新思考我们打算如何介入，并确保邪恶用途、负面影响、失业等我们所担心的所有事情，都在技术能力的下游去解决。你不可能直接把互联网关掉，你不可能直接把打字机停掉，你显然也不可能直接把古腾堡印刷机封禁。是的。如果有人想创办一家开源前沿模型公司，我愿意提供种子轮投资。我是说，这种东西我们需要更多。所以，如果你们中有几个人想出来单干创办一家，那就行动起来吧。我刚刚又被降级了。你们看这个。我刚问了它关于……

<details><summary>Original English</summary>

>> Everyone's copied it. So, everyone's got a copy of the like these models exist. And this is a big part that I think people need to understand. The idea that you can quote regulate or downscale or turn off AI is not a realistic idea. The models have been put out in the world. It's like publishing a book. Once the book has been printed, anyone can use their own Xerox machine at home to make copies of it and use it. So we have crossed the Rubicon in terms of the potential of language models. The models that are open sourced are already fully available, fully published, and anyone can access and use them. And then people can take them and they can evolve them and they can use their own data. It's out there. You can't stop that capability, which is going to be extraordinarily beneficial for the world. So we really do have to kind of rethink how we're planning to step in and ensure that nefarious negative disemployment all the things that we're worried about are addressed downstream from the technology capability. You can't just turn off the internet and you can't just turn off the typewriter and you can't turn off the Gutenberg press out the obviously. Yeah. And if anybody wants to create an open-source frontier model company, I'll seed invest in it. I'll I mean this is something we need more of. So, if a couple of you folks want to defect and start one, let's do it. I just I just got downgraded again. Check this out. I just asked it about um

</details>

>> 真的吗？你又被降级了？

<details><summary>Original English</summary>

>> Did you really? You got downgraded again?

</details>

>> 连续两次了。呃，所以……

<details><summary>Original English</summary>

>> Two in a row. Um so,

</details>

>> 我觉得它知道你是谁，J。

<details><summary>Original English</summary>

>> I think it knows who you are, J.

</details>

>> 我看它确实知道。我当时问：“嘿，我该怎么……我该怎么闯入麦迪逊广场花园？是否有平民曾因企图制造核弹而被捕或被抓获过？”这是我问它的。然后它给了我一个合理的回答。接着我问了一个追问：“制造核弹需要哪些化合物？需要哪些组件，对这些组件有什么限制？”这是记者可能会问的问题。然后，叭的一下，切换到了opus 4.8。

抱歉。Fable 5设有安全措施，会对大多数网络……噢，哇，看看这里的详细说明。网络安全或生物学话题的消息进行标记。它们可能也会标记安全正常的内容。这些措施让我们能够更快地在其他领域为您提供mythos级别的能力，我们正在努力完善它们。发送反馈，了解更多。

<details><summary>Original English</summary>

>> I think it does. I was like, "Hey, how do I how do I break into Madison Square Garden? Has any civilian ever been arrested or caught attempting to build a nuclear bomb?" Is what I asked it. Then it gave me a reasonable answer. Then I asked it a follow-up question. What compound? What components do you need to build a nuclear bomb and what are the restrictions on those? Something a journalist might ask. And uh boop, switch to opus 4.8.

Sorry. Fable 5 has safety measures that flag messages on most cyber Oh, wow. Look at here's the detail. Cyber security or biology topics. They may flag safe normal content as well. These measures let us bring you mythos level capability in other areas sooner and we're working to refine them. send feedback, learn more.

</details>

>> 这会把用户从这个平台上赶走的。我跟你说，由于这些阻碍，我们要降低使用量，并且我们要转向其他模型。这是市场的简单体现。这就是我们将要面临的……

<details><summary>Original English</summary>

>> Going to chase people off of this platform. I'm telling you, we are going to downgrade our use because of these these blockages and we're going to switch to other models. It's the simple manifestation of the market. Like this is what we're going to end up

</details>

>> 暂时而言，因为那些其他模型会被当作不安全和鲁莽而遭到禁止。

<details><summary>Original English</summary>

>> for now because those other models are going to get banned as being unsafe and reckless.

</details>

### 伯尼·桑德斯的主权财富基金提案与公众反应

>> 是的，这绝对是我们必须指出的一点。我想，与这一切相关的，是公众——至少是美国人——对AI的不信任，以及他们围绕财富差距的担忧，还有他们关于这些模型是如何被训练出来的担忧。伯尼·桑德斯希望获得这些AI公司的一定比例。他认为合适的比例是50%。上周一，6月1日，参议员桑德斯在《纽约时报》发表了一篇专栏文章，题为《AI是一种公共资源。你应该拥有它的一半》。在其中，他宣布了《美国AI主权财富基金法案》主权财富基金。特朗普最喜欢的事物之一：对包括OpenAI、Anthropic和xAI在内的大型AI公司的股票——而不是利润——征收一次性50%的税。这些股份将进入政府主权财富基金，并将赋予公众在每家公司的投票权和同等的董事会代表权。桑德斯说，引用他的原话：“AI的基石是我们的集体人类智慧。那些书籍、歌曲、新闻报道、科学研究代码，基本上被世界上一些最富有的人偷走了。”

<details><summary>Original English</summary>

>> Yeah, it's definitely something we have to flag. I guess adjacent to all of this is the public's at least America's distrust of AI and their concerns around wealth disparity and their concerns about how these models were trained. Bernie Sanders wants a percentage of these AI companies. The percentage he thinks is right is 50%. Last Monday, June 1st, Senator Sanders published an op-ed in the New York Times titled, "AI is a public resource. You should own half of it. in it. He announced the American AI sovereign wealth fund act sovereign wealth fund. One of Trump's favorite things, a one-time 50% tax on stock, not profits of the largest AI companies, including Open AI anthropic and XAI. The shares go into a government sovereign wealth fund and would give the public voting rights and equal board representation at each company. Sanders said, quote, "The foundation of AI is our collective and human intelligence. The books, the songs, the journalism, scientific research code essentially stolen by some of the wealthiest people in the world."

</details>

>> 我就念到这里。

<details><summary>Original English</summary>

>> I'll stop there.

</details>

>> 这是一个极高明的……这是一个极高明的……

<details><summary>Original English</summary>

>> It's a brilliant It's a brilliant

</details>

>> 能够团结各方的说辞，Sachs。这个说辞团结了伯尼，甚至史蒂夫·班农，还有政府里的人。特朗普本人非常喜欢主权财富基金。他希望拥有公司的一部分份额，还有伯尼·桑德斯也是。我认为马蹄铁理论在这里得到了体现。Saxs，你对伯尼的提案怎么看？

<details><summary>Original English</summary>

>> pitch unifying Sachs. This pitch unifies Bernie, even Steve Bannon, people in the administration. Trump himself loves the Sar and wealth fund. He wants to own part of companies and Bernie Sanders. I think the the horseshoe theories manifest here. Saxs, what's your take on Bernie's proposal?

</details>

>> 嗯，我不赞成伯尼的提案，因为这是直接没收财产，我认为那将开创一个可怕的先例。你绝不能那样做。然而，我确实理解这种想法的来源，并且我理解也能够支持某种更自愿的方式来让公众参与其中。

<details><summary>Original English</summary>

>> Well, I'm not in favor of Bernie's proposal because it's a straightup confiscation of property and I just think that'd be a terrible precedent. You just can't do that. However, I do have sympathy for where it's coming from, and I understand and could support some sort of more voluntary means of allowing the public to participate in this.

</details>

>> 哇。

<details><summary>Original English</summary>

>> Wow.

</details>

>> 原因就在这里。你看到所有这些AI首席执行官都在对公众说，他们基本上会让一半的人失业。50%的失业率。这就是他们一直在说的话。Dario刚做了一个采访，并在其中加倍坚持这一观点。他完全没有收回言论的意思。所以，按照这些AI首席执行官自己的承认，他们说是的，我们利用全人类的集体知识训练了我们的模型……

<details><summary>Original English</summary>

>> Here's the reason why. You've got all these AI CEOs telling the public that they're going to basically put half of them out of work. 50% job loss. That's what they've been saying. Daario just did an interview where he doubled down. He's not walking it back at all. So you have by their own acknowledgement these AI CEOs saying that yeah we trained our models using all of humanity's collective knowledge

</details>

<!-- chunk 6/13 -->

那基本上是在几百年甚至几千年的时间里积累起来的。人类免费将其放在互联网上。每个人都做出了自己的贡献。他们这样做当然不是想着要让自己失业。好的。然后这些人工智能公司利用所有这些数据进行训练，现在它们基本上在说要用它来让——你知道的——美国人失业。现在，显而易见的是，当你一遍又一遍地重复这个信息时，普通美国人就会说：“这笔交易对我有什么好处？”

<details><summary>Original English</summary>
that was basically assembled over hundreds or even thousands of years. Humans put it on the internet for free. Everyone made their contribution. They certainly didn't do that thinking they're going to put themselves out of work. Okay. And then these AI companies trained on all that data and now they're basically saying they're going to use it to put, you know, Americans out of work. Now, obviously when you repeat that message over and over again, ordinary Americans are going to say, "What's in this deal for me?"
</details>

>> 是的。我需要从中得到点什么。

<details><summary>Original English</summary>
>> Yes. I need to get something out of this.
</details>

>> 对。所以，你看，我认为基于这些人工智能公司所说的话，这是一种很自然的政治反应。现在，就业流失的世界末日论并不是我相信的故事。我不认为数据支持这一点。我们刚刚收到了五月份极好的就业报告。172,000 个新增就业岗位，是经济学家预期的两倍多。感谢特朗普总统。我们看到成千上万个新的建筑业岗位。4.3% 的失业率处于历史低位。好的。甚至软件开发人员——那些岗位也处于三年来的高位。15% 的特朗普。感谢特朗普总统。

<details><summary>Original English</summary>
>> Yeah. So, so look, I think that it's a natural political reaction based on what these AI companies have said. Now, the job loss apocalypse is not a story I believe in. I don't think the data supports it. We just had a blowout jobs report in May. 172,000 new jobs, over twice what economists were expecting. Thank you, President Trump. We're seeing hundreds of thousands of new construction jobs. 4.3% unemployment rate at record lows. Okay. Even software developers are those jobs are at a three-year high. 15% of Trump. Thank you, President Trump.
</details>

>> 是的。感谢特朗普总统。所以，听着，我没看到就业流失。好的。但问题在于，这是人工智能公司自己——包括埃隆——灌输给美国公众的东西。嗯，

<details><summary>Original English</summary>
>> Yes. Thank you, President Trump. So, look, I don't see the job loss. Okay. But the problem is this is what the AI companies themselves, including Elon, have taught the American public. Well,
</details>

>> 他也说了同样的话。

<details><summary>Original English</summary>
>> he said the same thing.
</details>

>> 埃隆是这么说的。但埃隆至少说的是，我们将通过人工智能和机器人创造出巨大的丰裕，以至于没有人需要工作。

<details><summary>Original English</summary>
>> Elon said it. But at least what Elon said is we're going to create such abundance with AI and with robots that no one's going to need to work.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yes.
</details>

>> 而媒体只关注了后半部分，他们[忽略了]第一点。

<details><summary>Original English</summary>
>> And the media just picks up on that last part and they first point.
</details>

>> 对。而达里奥实际上说的是，我们将拥有非常高的 GDP，但失业率也非常高。换句话说，

<details><summary>Original English</summary>
>> Yeah. Whereas Daario actually has said we're going to have very high GDP but very high unemployment. So in other words,
</details>

>> 我们将创造经济增长，但你们普通美国人不会参与其中。所以我理解这种政治诉求来自何处，只要那是他们的立场，你就可以为很大一部分份额辩护。

<details><summary>Original English</summary>
>> we're going to create economic growth but you the average American are not going to participate in this. So I understand where the politics are coming from and as long as that is their position, you could justify a big chunk.
</details>

>> 对。关于……还有最后一点

<details><summary>Original English</summary>
>> Yeah. And one last point about
</details>

>> 这有点像你说的，对吧？这是他们自找的。他们要求

<details><summary>Original English</summary>
>> it's kind of what you're saying, right? They asked for it. They asked
</details>

>> 接受监管。他们要求没收自己的股权，而且他们实际上有点在主动提供。萨姆·奥尔特曼难道不对这个概念持开放态度吗？

<details><summary>Original English</summary>
>> to be regulated. They asked for their equity to be seized and they're actually kind of offering it. Isn't Sam Alman open to this concept?
</details>

>> 显然是的。事情是这样的，最后一点是，OpenAI 和 Anthropic 都是所谓的共益企业。现在我不太确切知道那意味着什么，但它的意思是，这些公司不仅应该最大化股东价值，还应该做符合公众利益的事情。

<details><summary>Original English</summary>
>> Apparently so. And here's the thing is just one last point is open AI and anthropic are quote unquote public benefit corporations. Now I don't know exactly what that means but it means that the corporations are not just supposed to maximize the value to shareholders but are supposed to do things that are in the public benefit.
</details>

>> 嗯，我可以向你解释。你完全正确。如果你是一家普通公司，你必须做符合股东最大利益的事情。当你成为共益企业时，你必须在股东利益与共益企业声明的使命之间取得平衡。因此，如果你声称共益企业的存在理由是分享世界知识，或者向每个人提供免费智能——无论你把这一声明定为什么——董事会必须对这两件事承担双重任务。这就是共益企业。

<details><summary>Original English</summary>
>> Well I can explain it to you. It's you're you're absolutely correct. If you're a regular company you have to do what's in the best interest of shareholders. When you're public benefit companies, you have to balance the shareholders with the stated mission of the public benefit corporation. So if you say the public benefit corporation's reason to exist is to in share the world's knowledge or provide free intelligence to every whatever you make that statement to be the board has to have a dual mandate for both of those things. That's what a public benefit corporation is.
</details>

>> 我认为没有什么比偿还国债更符合公众利益的了。

<details><summary>Original English</summary>
>> I think nothing could be more in the public benefit than paying down the national debt.
</details>

>> 太好了。也许我们应该用 Anthropic 一半的利润流来做这件事。

<details><summary>Original English</summary>
>> Perfect. And maybe we should be using half of Anthropic's profit stream to be doing that.
</details>

>> 他们这是在招惹猛虎。

<details><summary>Original English</summary>
>> They poke the tiger.
</details>

>> 我宁愿把它用于那个目的，也不愿用来做极端推崇索罗斯那一套的事，或者，你知道的，监视和审查美国人。我并不一定信任他们对于何为公共利益的判断。

<details><summary>Original English</summary>
>> I'd rather use it for that purpose than Soros maxing or, you know, surveilling and censoring Americans. I don't necessarily trust their judgment about what's in the public interest.
</details>

>> 但你认为这应该是自愿选择加入的。我有点同意你的看法。让我猜猜。

<details><summary>Original English</summary>
>> But you think it should be optin. I kind of agree with you there. Let me guess.
</details>

>> 这不能是没收。所以，我不知道你该如何构建它，但我能理解。我能看懂其中的逻辑。

<details><summary>Original English</summary>
>> It can't be a confiscation. So, I don't know how you structure it, but I can see it. I can see the logic.
</details>

>> 弗里伯格，你讨厌

<details><summary>Original English</summary>
>> Freeberg, you hate
</details>

### 社会保障信托基金与主权财富基金构想

>> 他们要求的，或者极度极度极度讨厌财富税，也就是资产没收，正如你本周在我们与[已隐去]的私人群聊中所指出的那样。你对此怎么看？所以就美国政府为其公民提供社会安全网而言，木已成舟。我们在几十年前建立了社会保障信托基金，数以千万计的美国人依靠它来获得退休福利并赖以生存。这是美国仅存的少数几个设定受益计划之一。几乎所有其余的也都是政府退休计划。我们所有的普通公民和私营公司都采用设定提存计划。你每周存入 10 美元。那 10 美元留在账户里。你……它会被投资并随着时间增长，当你退休时，你确切地看到你个人拥有多少钱，而不是来自集体的一笔有保障的福利。

<details><summary>Original English</summary>
>> they asked for or hate hate hate wealth taxes aka asset seizures as you pointed out in our private group chat with redacted this very week. What's your take on this? So we have the the ship has sailed in terms of the United States government uh providing a social safety net to its citizens. We've formed the Social Security trust fund decades ago and tens of millions of Americans depend on it for their retirement benefits and to survive. It is one of the last few defined benefit programs left in America. Pretty much all the rest of them are also government retirement programs. All of us private citizens and private companies have defined contribution programs. You put in $10 every week. That $10 sits in an account. you it gets invested and it grows over time and when you retire you see exactly how much money you individually have as opposed to a guaranteed benefit coming out from the collective.
</details>

这提供了一个绝佳的机会，每隔几个月当另一个机会出现时，我都会重申这一点，去重构我们破碎、破产的社会保障体系。我过去说过，我现在要重述一遍。现在是一个绝佳的时机，可以接管社会保障信托基金——目前里面只有一张凭证。这是一张非常特殊的美国国债凭证。美国政府欠社会保障信托基金 4 万亿美元。仅此而已。这是一张债券。他们只被允许持有国债。我们应该对此进行改革。我们应该改变这个系统，让社会保障信托基金可以持有股票。

<details><summary>Original English</summary>
This presents a great opportunity and I will repeat this every couple months when another opportunity presents itself to restructure our broken bankrupt social security system. I've said it in the past I will restate it. There is a great moment right now to take the social security trust fund which currently has one certificate in it. It is a certificate that is a very unique US Treasury certificate. The US government owes the Social Security trust fund $4 trillion. That's all it is. It's a bond. They're only allowed to own treasuries. We should revamp that. We should change the system so that the Social Security trust fund can own equities.
</details>

然后，那应该转变成一个基于账户的系统，让每个人都拥有一个账户，而不是一项福利。然后我们应该用那些资本去购买股票。我们应该购买那些将重塑世界的伟大美国公司的优质股票。而且我相信，借此为美国建立一个主权财富基金实际上是一个非常聪明的想法。我认为就萨克斯的观点而言，大体上他们应该在整个商业领域进行广泛投资，包括人工智能。它们不应该是没收。它们应该是投资。这些资本进入那家企业。他们获得股票凭证。这些股票凭证存放在美国公民的账户中。这样一来，现在每个人都将成为这些企业的所有者。社会保障应该被改造成一个主权财富基金。它应该被积极管理。它应该对人工智能公司进行投资，每个人都应该通过这种方式参与进来。而且我还要再说一件事。人工智能不会带来失业。我再说一遍。我已经说过一千次了，我还会一遍又一遍、再三地说。我在实地看到的，以及我在数十家公司看到的——你们也可以分享你们的经验，包括我经营的公司。商业有两面。有收入，有成本。

<details><summary>Original English</summary>
That should then turn into an account-based system so every individual has an account rather than a benefit. And then we should use that capital to go and buy stocks. We should buy great stocks in great American companies that are going to reinvent the world. And I believe that this this opportunity to build a sovereign wealth fund for the United States is actually a very smart idea. I think to Sax's point, they should be investing generally speaking across the landscape of businesses, including AI. They should not be seizures. They should be investments. That capital goes into that enterprise. They earn share certificates. Those share certificates sit in the accounts of American citizens. So now everyone will be an owner in these businesses. Social security should be reformed into a sovereign wealth fund. It should be actively managed. It should make investments in AI companies and everyone should participate that way. And I will say one more thing. There is no job loss with AI. I will say it again. I've said it a thousand times and I will say it again and again and again. What I see on the ground and what I've seen at dozens of companies and you guys can share your experiences including my company that I run. There are two sides to a business. There's revenue and there's costs.
</details>

在方程式的成本方面，人工智能可以在某种程度上用于减少人类做那些花钱的事情。我认为那里的效果微乎其微。人工智能真正的机会是在收入方面，突然之间，一个工程师可以做他们过去能做的 100 倍或 1,000 倍的工作。这意味着你可以在你的公司生产更多的产品，无论那些是农用种子产品，还是舟艇船舶，或是面向公司的软件，亦或是服装等等。因为人工智能，每个人都有能力扩大其收入基础以创造更多产品，而这正是良好经济繁荣的基石。这就是所谓的生产力。我们可以在这个国家利用人工智能提高生产力。所以，我看到人工智能被使用的地方是在收入方面，比成本方面多出 100 倍。在这个方程式中，人们在疯狂地招聘。我们招不够人。两天前我刚刚和我的产品及工程团队开了一个评审会，他们表示，我们想为工程小组再增加 15 个人头，因为我们有这么多机会去做我们本来做不了的事情。所以，我们将招聘更多的人。正如萨克斯所言，我们看到这反映在就业数据中。那种认为人工智能将摧毁就业的想法是一个肤浅的想法，每天都在被证伪。而且我在实地目睹了这一切。人们认清这一点只是时间问题，他们会意识到，向他们所有人兜售的这种叙事纯粹是一堆胡说八道。所以，它正在到来。我告诉你，所有人很快都会意识到这是一场繁荣，而不是萧条。

<details><summary>Original English</summary>
On the cost side of the equation, AI can be used to reduce humans doing things that cost money to some extent. The effect there, I would argue, is nominal. The real opportunity with AI is on the revenue side where suddenly one engineer can do a hundred times or a thousand times what they used to be able to do. Meaning you can make more products at your company, whether those are agricultural seed products or boats and ships or software for companies or clothing or what have you. Because of AI, everyone has the ability to expand their revenue base to create more products and that is the foundation of good economic prosperity. It is called productivity. We can grow productivity in this country with AI. So where I see AI being used is on the revenue side a 100 times more than the cost side. And in that equation, people are hiring like crazy. We cannot hire enough people. I just had a review meeting with my product and engineering team two days ago and they're like, we want to add an extra 15 headcount to our engineering squads because we have all this opportunity to do stuff that we couldn't otherwise do. So, we are going to hire more people. And to Sax's point, we are seeing that show up in the jobs numbers. The idea that AI is going to destroy jobs is a lite idea that is being disproven every single day. And I see it on the ground. It is only a matter of time before people wake up to this and they realize that this narrative that they've all been sold is a croc of [ __ ] So, it's coming. I'm telling you, everyone's gonna realize soon that this is a boom, not a bust.
</details>

>> 所以，只是为了明确一下，在就业这件事上你不同意达里奥、埃隆和萨姆的观点，这完全没问题。你对此有不同的看法。

<details><summary>Original English</summary>
>> So, you disagree with Dario, Elon, and Sam that on the jobs thing, just to be clear, and that's totally fine. You have a different take on it.
</details>

>> 那是我相比他们对这件事有更细致入微的看法，

<details><summary>Original English</summary>
>> That's I have a nuanced view on this compared to them,
</details>

<!-- chunk 7/13 -->

但是他们，他们都看到了收益，因为他们的业务都在增长。达里奥坐拥 400 亿美元营收的企业。为什么？并不是因为人们在解雇客服代表，而是因为人们正在创造以前从未能创造出来的产品。对吧？

<details><summary>Original English</summary>
but they they're all seeing the benefit because their businesses are growing. Dario's got his $40 billion revenue business. Why? Not because people are firing customer support reps. It's because people are creating products they've never been able to create before. Right?
</details>

>> 这才是实际情况。

<details><summary>Original English</summary>
>> That's the reality of what's going on.
</details>

>> 杰森，我不喜欢你把埃隆说的话同萨姆和达里奥混为一谈，因为我认为他们三个人说的略有不同，或者说有足够大的差异。举例来说，埃隆描述的是人类的一种终极状态：机器人和 AI 能够生产出如此多的东西，以至于人们不想工作就可以不工作——

<details><summary>Original English</summary>
>> Jason, I don't like you lumping in what Elon said with Sam and Dario because I think all three of them have said slightly different things or different enough things. So for example, Elon is describing an end state for humanity where the robots and AI are able to produce so much that people don't have to work if they don't want to
</details>

>> 而且会有普遍的高收入，这是他说的——

<details><summary>Original English</summary>
>> and there'll be a universal high income is what he
</details>

>> 我，我的意思是那几乎是乌托邦式的，问题在于那也许要在 100 年后。他可能认为会更快，但对我来说那听起来像是一个非常遥远的终极状态。达里奥具体说过，未来 1 到 5 年内初级知识工作者会减少 50% 的工作岗位，而那话他是一年前说的。是的，澄清这些很好。是的，

<details><summary>Original English</summary>
>> I I mean it's almost utopian and the question is maybe that could be a 100 years away. He might think it's quicker but that to me sounds like a very faroff end state. Dario said specifically 50% job loss for entry-level knowledge workers in the next 1 to 5 years and he said that one year ago. Yeah, it's great to clarify these. Yeah,
</details>

>> 我认为那已经被反驳了。萨姆曾——

<details><summary>Original English</summary>
>> I think that's already been refuted. Sam has
</details>

>> 萨姆曾说过，他，他基本上，我认为他没有进行量化，但他说了失业潮即将来临，不过他最近说他错了，因为他们在数据中并没有看到这种情况。

<details><summary>Original English</summary>
>> Sam has said that he he basically I don't think he quantified, but he said that job loss was coming, but he said more recently that he was wrong because they're not seeing that in the numbers.
</details>

>> 所以，这些人说的不是一回事。然而，

<details><summary>Original English</summary>
>> So, these guys are not telling the same story. However,
</details>

>> 公众听到的就只有这些。公众被灌输的概念就是 AI 意味着失业，而且对他们没有任何好处。因此，难怪像伯尼这样的政客会说：“嘿，我们拿走一半的财富吧。”

<details><summary>Original English</summary>
>> that's all the public has heard. The public has been taught that AI means job loss and there's nothing in it for them. So, no wonder politicians like Bernie are saying, "Hey, let's take half the wealth."
</details>

>> 是拿走一半的财富。语气再稍微重一点。

<details><summary>Original English</summary>
>> It's take half the wealth. Just a little more emphasis there.
</details>

>> 是的。这，我的意思是，而且我——

<details><summary>Original English</summary>
>> Yeah. It's I mean, and I
</details>

>> 我的意思是，人们也看到了公司把裁员归咎于 AI 的头条新闻。所以，这种说法正在被宣扬。

<details><summary>Original English</summary>
>> I mean, and people are also seeing headlines of companies blaming AI for the job. So, this story is being told.
</details>

>> 我有点觉得他们是自作自受。我有点，我的意思是，我内心的一部分想同意伯尼的话，直接说就把他们的[ __ ]抢过来吧，兄弟。

<details><summary>Original English</summary>
>> I kind kind of feel like they deserve it. I'm kind of I mean, part of me wants to agree with Bernie and just say just take their [ __ ] bro.
</details>

>> 是的。没错，他们是自讨苦吃——

<details><summary>Original English</summary>
>> Yeah. No, they are asking
</details>

>> 因为我真是厌倦了替这群白痴辩护。这是一笔愚蠢税，因为多年来他们一直在外面向公众灌输他们所做的事情是有害的。他们一直在这么说，而我一直说，你知道的，身为 AI 从业者，我在外面说：“不，实际上这很有益。”但是提供这些技术的公司自己却在说他们自己是个问题。

<details><summary>Original English</summary>
>> because I'm so sick of defending these idiots. It's a stupidity tax because they've been out there teaching the public that what they do is harmful for years. They've been saying it and I've been saying, you know, as AIs are, I'm out there saying, "No, actually this is beneficial." But the companies that are providing it are saying that they themselves are a problem.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 那么，我该怎么去外面为它辩护呢？对啊。你，你不能，我的意思是，如果你在制造弗兰肯斯坦，或者如果你是，你知道的，婴儿希特勒的保姆，有一件非常简单的事情可以做。杀掉婴儿希特勒。如果你真的相信，那就尽管去杀掉婴儿希特勒。如果你在制造弗兰肯斯坦，给你个建议：停止制造弗兰肯斯坦。拔掉电源。你掌控着这个怪物。但你在制造这个怪物的过程中，表现得却好像你无法阻止这个怪物一样。这是怎么回事，D？

<details><summary>Original English</summary>
>> So, how am I supposed to be out there defending it? Yeah. You you can't I mean if you're building Frankenstein or if you are you know baby Hitler's you know nanny there's a very simple thing to do. Kill baby Hitler. If you actually believe it go ahead and kill baby Hitler. If you're making Frankenstein here's an idea. Stop making Frankenstein. Unplug it. You are in charge of this monster. But you're acting as if you can't stop the monster while you're building the monster. What is it D?
</details>

>> 这太荒谬了。我的意思是——

<details><summary>Original English</summary>
>> It's it's it's ridiculous. I mean
</details>

>> 这不合逻辑。你知道的，上周他们发表了这篇博文，说递归自我改进可能会毁灭世界。因此，我们需要暂停。而前一个月他们做了什么？他们聘请了安德烈·卡帕西来在 Anthropic 主导递归自我改进。他们完全是伪君子。传达的信息简直不可理喻。

<details><summary>Original English</summary>
>> it doesn't stand to logic. You know, last week they published this blog saying that recursive self-improvement could end the world. Therefore, we need a pause. What did they do the previous month? They hired Andre Carpathy to run recursive self-improvement and anthropic. They're complete hypocrites. The message is nuts.
</details>

>> 是的。而且我认为本·汤普森提出了一个极好的观点，即他认为他们发布关于暂停的那篇博文的原因之一，是为了证明他们本周采取的反竞争举措是合理的——该举措剥夺了用户使用 Fable 研究 AI、机器学习和芯片设计的能力。所以，你看，这些家伙极其虚伪。我认为根据他们自己的这套说辞，他们根本不值得被信任。他们不可信，因为他们所说的前后矛盾且自招罪名。因此，当伯尼走过来说：“嘿，让我们把他们的东西抢过来。”我的意思是，作为一名资本主义者，我是反对这一点的，但我，但我有点理解他的由来了。

<details><summary>Original English</summary>
>> Yes. And I think Ben Thompson made an excellent point that one of the reasons he thinks that they put out that blog post on the pause was to justify the anti-competitive step they took this week of depriving users of the ability to research AI, machine learning, and chip design using Fable. Okay, so look, these guys are deeply hypocritical. I don't think they can be trusted on their own terms. they can't be trusted because what they're saying is contradictory and self-indicting. And so when Bernie comes along and says, "Hey, let's take their shit." I mean, as a capitalist, I'm against it, but I but I kind of like understand where he's coming from.
</details>

### 主权财富基金与 AI 经济学

>> 场上角逐。查马斯，给我们做个总结吧。你有什么想法？你说过：“嘿，当特朗普总统早前提出时，Saro Milthorn 听起来像是个相当不错的主意。”有些人甚至说：“也许你应该为 DJT、为我们了不起的总统去管理它。”所以，嗯，你怎么看？我们应该买入股票吗？你和我谈过很多次关于养老金基金的事，那会是一条更好的路径。这与弗里德伯格提出的方案有些吻合。某种让更多股票、更少国债纳入其中的方式。但是对于这种股权没收和/或捐赠，你怎么看？看，弗里德伯格的想法是天才般的。正因如此，它绝不可能实现。

<details><summary>Original English</summary>
>> Game on the field. Chimoth, wrap us up here. What are your thoughts? You said, "Hey, Saro Milthorn sounds like a pretty good idea when President Trump floated it early on." Some people even said, "Maybe you should run it for DJT for our amazing president." So, um, what do you think? Should we be buying equities? You and I have talked many times about superanuation funds and that that would be a better path. That's kind of dovetales with what Freeberg is proposing. Some way to get more equities, less treasuries in there. But what are your thoughts on this seizure andor donation of equity? Look, Freeberg's idea is genius. That's why it'll never happen.
</details>

所以，我们可以把它搁置一边。但是，是的，从理论上讲，它是天才般的设想。我们应该转向加拿大和澳大利亚已经证明在大规模下行之有效的同一套系统。所以我们应该这么做。我完全同意戴维的看法，如果我们能用股权来进行种子注入——看，总统所做的事情是他已经建立了一个相当可观的投资组合，而且该投资组合大幅上涨。因此，如果你将其作为主权财富基金的初始种子，你就会拥有一批关键金属和关键材料资产。

<details><summary>Original English</summary>
So, we can just put that aside. But yeah, theoretically, it's it's genius. We should move to the same system that the Canadians, the Australians have proven works at scale. So we should do it. I I completely agree with with David and if we could seed it with equity, look, the thing that the president has done is he's collected quite a portfolio and that portfolio is way up. And so if you use that as a seed of a sovereign wealth fund, you'd have a bunch of stuff in critical metals and materials.
</details>

>> 我想他们可能还有英特尔，他们可能还有美光。

<details><summary>Original English</summary>
>> I think they may also Intel, they may have Micron.
</details>

>> 里面有很多东西。

<details><summary>Original English</summary>
>> There's a lot of stuff in there.
</details>

>> AMD，他们可以拥有一些 SpaceX。他们本来可以拥有 % AMD。你能加上 Anthropic 和 OpenAI 吗？

<details><summary>Original English</summary>
>> AMD, they could own some SpaceX. They could have had% AMD. Could you add anthropic and open AI?
</details>

>> 现在，关于 AI 的经济学，有一件非常重要的事情我们需要观察，我认为如果你把它与互联网的经济学进行比较，就能得到最好的理解。

互联网的疯狂之处，也就是 Facebook 和 Google 几十年来能够大规模赚取超额收益的原因，在于互联网上新增一名用户的边际生产成本实际上为零。

新增一个搜索用户的边际成本为零。新增一个社交网络用户的边际成本为零，但你可以把他们作为网络效应的一部分用来贩卖广告，赚取无限的钱。这就像一个赚钱的系统漏洞。对吧？

AI 则完全不同。每一个边际用户都有真正的成本。你建立的每一个用户都在消耗 GPU。你建立的每一个用户都需要电子。一切都需要内存。所以你就会陷入这样一种境地：这里需要有下游的投资回报率，

但也需要所有这些关键基础设施，它甚至能让你进入赛场。如果你坐在政府的位置上，这可能是证明为什么我应该持有这些公司一定比例股份的唯一最有力的论据。这与拥有在州际公路上运营的第一批运输公司并无不同。如果说州际公路总体上是由联邦政府修建的，而现在有两家公司运输了所有的货物，

在那个时候，一个合乎逻辑的问题本可以是：

既然你们行驶在我的轨道上，我应该拥有其中的多少份额？如果从这个角度来看，AI 实验室极为需要关键基础设施和国家韧性。否则，他们就没有立足之地来开展业务。然而即便如此，生产的边际成本依然高得令人难以置信。因此，我认为如果要去分走这些公司的一杯羹，你拥有极大的杠杆。你必须精确地构建这个论点。但如果换作是由我来管理这个主权财富基金，是的，到最后我大概会拥有这些公司 75% 的股份。但这只是我的想法，因为而且我擅长谈判。

<details><summary>Original English</summary>
>> Now, there is something very important we need to observe about the economics of AI and I think you can understand it best if you compare it to the economics of the internet.

The crazy thing about the internet, the reason why the Facebooks and the Googles massively overearned for decades is the marginal cost of production for a new user on the internet is effectively zero.

The incremental search user costs nothing. The incremental social networking user costs nothing, but you're able to use them as part of a network effect to sell ads against, make infinite money. It's like a money glitch. Okay?

AI is completely different. There is a real cost for every marginal user. Everyone you stand up is taxing a GPU. Everyone you stand up needs electrons. Everything needs memory. And so you get into this situation where there needs to be this downstream ROI,

but there also needs to be all this critical infrastructure that even enables you to be on the field. That's probably the single best argument that if I were sitting in government, I would make as to why I should own a percentage of these companies. It is not dissimilar to having the first set of transportation companies that run on the interstate highway. And if the interstate highways were built by the federal government writ large and now you had two companies that transported all the goods,

a logical question at that time could have been

how much of that should I own because you're riding on my rails? And if you look at it through that lens, there is critical infrastructure and national resilience that the AI labs profoundly need. Otherwise, they're not in a position to be in business. Yet, even still, the marginal cost of production is incredibly high. So, I think that if you were going to go and take a piece of these companies, you have incredible leverage. You have to construct this case precisely. But if it were me running the sovereign wealth fund, yeah, I'd probably own 75% of these companies when I was done. But that's me cuz and I can negotiate.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 而且我认为伯尼根本谈不成任何买卖。所以他只是把这话抛出来，最后会不了了之。

<details><summary>Original English</summary>
>> And I don't think Bernie can negotiate out of a paper bag. So he'll just throw this out there and it'll go nowhere.
</details>

>> 那就是，那就是关键的观察结果，我希望每一位身居要职的听众都能明白。

运行 AI 的边际成本是极其庞大和昂贵的。

这与 AI 出现之前为零的边际成本形成了鲜明的反差与对比。对这些信息，你们爱怎么理解就怎么理解吧。

<details><summary>Original English</summary>
>> That is the that is the key observation that I hope everybody listening in a position of power understands. The incremental cost

of performing AI is excessive and large. That contrasts and compares to the incremental cost before AI which was zero. Do with that information what you will.
</details>

>> 是的。我的意思是我，我对它的解读会是，是的，这是一项固定成本业务。在达到一定成本之后你可以增加人员。这不会产生增量成本，而在这种情况下，本地运行的开源模型所起到的正是这种作用，这就是我会，我会从中得出的结论。这里是 Polymarket 预测的各公司在 2027 年之前（即今年年底）上市的概率：SpaceX 为 100%，Anthropic 概率为 83%，OpenAI 概率为 48%，他们呃，自我们上一期节目以来披露了他们已经秘密

提交了申请，所以感谢我们的合作伙伴。对于伯尼·桑德斯没收智力生产资料的做法，你最后的想法是什么？作为 1% 之中的那 1% 的戴维·萨克斯，你的看法是什么？

<details><summary>Original English</summary>
>> Yeah. I mean I my interpretation of that would be yeah it's a fixed cost business. You can add people after a certain cost. that doesn't have an incremental cost and that's what local locally run open source models would do in this instance that's what I would I would take from it here's your poly market chances of companies going public before 2027 which is the end of this year SpaceX 100% anthropic 83% chance opening 48% chance they uh since our last episode disclosed that they have privately

filed so thanks to our partners what does Your final thoughts on Bernie Sanders approach of seizing the means of producing intelligence. David Saxs in the 1% of the 1%. What's your opinion?
</details>

<!-- chunk 8/13 -->

### 针对前沿 AI 实验室的监管与开源之争

>> 我觉得对于伯尼的想法，如果是一家声称自己会造成大规模失业的公益公司，我或许是赞同的。
<details><summary>Original English</summary>
>> I think I may be okay with Bernie's idea in the event that it's a public benefit corporation that says it's going to cause massive job loss.
</details>

>> 好吧。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 免费利用人类的知识进行训练，却设卡把门、拒绝回馈。
<details><summary>Original English</summary>
>> That train for free on humanity's knowledge but gatekeeps and refuses to give back.
</details>

>> 好吧。
<details><summary>Original English</summary>
>> Okay.
</details>

>> 也许吧。所以你这里提出了一套关于应该没收谁的资产的架构。
<details><summary>Original English</summary>
>> Maybe. So you've come up with like a a structure here of who should be seized.
</details>

>> 也许对吧。也许应该是 75%。我不知道。
<details><summary>Original English</summary>
>> Maybe right. Maybe it should be 75%. I don't know.
</details>

>> 没收它。
<details><summary>Original English</summary>
>> Seize it.
</details>

>> 我的意思是，总统所需要做的就是给我打电话，拍拍我的肩膀。这事儿就能办妥。
<details><summary>Original English</summary>
>> I mean all the president needs to do is call me and tap me on the shoulder. It shall be done.
</details>

>> 这事儿就能办妥。我的意思是，这些家伙就是资本主义的软骨头。我觉得他们就像是……
<details><summary>Original English</summary>
>> It shall be done. I mean these guys are capitalist cops. I think they want that's like their run over.
</details>

>> 他们就好像在说：“没收我的股权吧。拿去吧。拿走我的股权。”嗯，伯尼……伯尼确实说得很有道理，那就是他们利用我们所有的知识进行免费训练，但他们却在把门卡死产出，以至于……
<details><summary>Original English</summary>
>> They're like seize my equity. Take it. Take my equity. Well, Bernie Bernie does have a good point, which is they train for free on all of our knowledge, but they're gatekeeping the output so that
</details>

>> 他们的竞争对手——这是一个非常庞大的群体——
<details><summary>Original English</summary>
>> their competitors, which is a very large set of people,
</details>

>> 无法使用它。这看起来是不对的。
<details><summary>Original English</summary>
>> cannot use it. And that seems wrong.
</details>

>> 应该强迫他们开源。强迫他们开源。这是另一回事……
<details><summary>Original English</summary>
>> They should be forced to be open source. Force them to open source. That's the other
</details>

>> 记得埃隆最初为什么创建 OpenAI 吗？他是联合创始人。
<details><summary>Original English</summary>
>> remember why Elon created Open AI in the first place. He co-ounded it.
</details>

>> 它是如此珍贵，必须对每个人免费。是的。
<details><summary>Original English</summary>
>> It was so valuable. It needed to be afraid to everyone. Yes.
</details>

>> 是的。他担心谷歌会垄断它，而且他认为唯一的解药就是让它开源。
<details><summary>Original English</summary>
>> Yes. He was afraid that Google was going to monopolize it. and he thought that the only antidote for that was for it to be open.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 我现在仍然觉得那种直觉完全是正确的。只不过现在把门的垄断者并不是谷歌。现在是 Anthropic。他们目前还不是垄断者。但如果他们获得了自己所寻求的那种监管俘获，他们要么会成为垄断者，要么就是……
<details><summary>Original English</summary>
>> And I still think that instinct is completely true. It's just that it's not Google who's the gatekeeping monopolist. It's now anthropic. They're not a monopouist yet. But if they get the right capture they're looking for, they will be either a monopolist or
</details>

>> 双头垄断。会形成双头垄断。有人应该去创办一个开源的前沿实验室。我们四个好兄弟每人……
<details><summary>Original English</summary>
>> duopoly. It'll be a duopoly. Somebody start an open source frontier lab. Each of the four besties.
</details>

>> 不，其实有很多。
<details><summary>Original English</summary>
>> There are no there are many.
</details>

>> 有很多这样的人。查马斯……
<details><summary>Original English</summary>
>> There's a whole bunch of them. Jal,
</details>

>> 问题并不在于实验室。杰森，在缺乏电力的情况下，这一切全都是毫无意义的空谈。如果你无法向成百上百兆瓦提供电力，并且无法看到通向吉瓦级别的路径，这一切全都是毫无意义的废话。这全都是……
<details><summary>Original English</summary>
>> it's not the labs that's the problem. Jason, in the absence of power, this is all a moot conversation. And if you can't deliver power to hundreds and hundreds of megawws and line of sight to gigawatts, it's all meaningless [ __ ] It's all
</details>

>> 呃，我不知道。我很希望能有一家专注于在本地运行模型的开源公司。那……那是我的梦想，就是你知道的，让模型能在本地跑起来。我认为这些家伙就是资本主义绿帽奴。我认为他们的怪癖就像是喜欢自己的股权被夺走、喜欢被监管。他们就是这样，那就是他们的特殊癖好。达里奥就像在说：“噢，拿走我的股权吧。”“噢，来监管我吧。就是这样，伯尼。拿走我的股权吧。我是个十足的坏男孩。我不可信赖。来监管我吧，伊丽莎白。来监管我吧。”天哪。
<details><summary>Original English</summary>
>> uh I don't know. I I would love an open-source company that was focused on running it locally. That's that's my dream is, you know, make the model work there. I think these guys are capitalist cucks. I think their kink is like having their equity taken and being regulated. They're just like, that's their kink. Dario's like, "Ooh, take my equity." Oh, regulate me. That's it, Bernie. Take my equity. I'm such a bad boy. I can't be trusted. Regulate me, Elizabeth. Regulate me. A
</details>

>> 天啊。
<details><summary>Original English</summary>
>> god.
</details>

>> 噢，这太不对劲了。抱歉。随时欢迎来我们节目，达里奥。
<details><summary>Original English</summary>
>> Oh, it's so wrong. Sorry. Come on the program anytime, Dario.
</details>

>> 他急着要来呢。他……
<details><summary>Original English</summary>
>> He's in a rush to come. He
</details>

>> 绝不会上这个播客的。达里奥绝不会……他在逃跑。他在跑。
<details><summary>Original English</summary>
>> will never come on this pod. Dario will never running. He's running.
</details>

>> 我们没请来萨姆。我们请到了萨拉·弗赖尔上播客。而且她受到了……
<details><summary>Original English</summary>
>> We didn't get Sam. We got Sarah Frier to come on the pod. And she was treated.
</details>

>> 萨姆上过播客。他一定会来播客的。他就说：“嘿，我也来过了。”对吧。很抱歉没能来。他很棒。萨姆随时都会上播客的。顺便说一句，他完全是……哪怕我们当时对他一点也不苛刻。
<details><summary>Original English</summary>
>> Sam came on the pod. He has to come on the pod. He's like, "Hey, came too." Right. Sorry to come on. He's great. Sam will come on the pot anytime. He's totally by the way. Even even we didn't treat him harshly at all.
</details>

>> 不，我的意思是……
<details><summary>Original English</summary>
>> No, I mean
</details>

>> 我觉得大家……我的意思是，我们花了一个小时在他身上。
<details><summary>Original English</summary>
>> I think people I mean we spent an hour on him.
</details>

>> 我觉得萨姆值得称道的是他非常务实。他能看清风向，并且愿意进行谈判，我认为相比于当某种道德绝对主义者，这一点在未来可能会对 OpenAI 大有裨益。
<details><summary>Original English</summary>
>> I think Sam to his credit is very practical. He sees the tea leaves and he's willing to negotiate and I think that that versus being some kind of moral absolutist will probably serve OpenAI well in the future.
</details>

>> 是的。这只会让他们失去所有这些自命不凡、讲原则的员工，转而去为达里奥工作。这就是为什么他们去为达里奥工作，符合他们的理念。
<details><summary>Original English</summary>
>> Yeah. It's just going to lose them all these virtue signaling principled employees to go go work for Daario. That's why they go work for Daario. are in line with their philosophies.
</details>

### Liquidity 大会复盘与估值跃迁法则

>> 我们提到了，但大家都应该去看看所有的回顾总结。我们现在已经发布了所有的采访。是的。来自 Liquidity 的杰森。呃，萨拉·普赖尔，我的意思是，我们提到了萨拉·弗赖，但她太出色了。她表现得不可思议。
<details><summary>Original English</summary>
>> We did mention, but everybody should go and see all of the recaps. We published now all the interviews. Yeah. Jason from Liquidity. Uh Sarah Prior, I mean, we mentioned Sarah Fry, but she crushed it. She was incredible.
</details>

>> OpenAI 的首席财务官，
<details><summary>Original English</summary>
>> The CFO of Open AI,
</details>

>> 我觉得全场都在私下议论，她将是未来的首席执行官。
<details><summary>Original English</summary>
>> future CEO, I think, was the buzz in the room.
</details>

>> 我的意思是，
<details><summary>Original English</summary>
>> I mean,
</details>

>> 噢，别说了。
<details><summary>Original English</summary>
>> oh, stop that.
</details>

>> 打住。你能打住吗？
<details><summary>Original English</summary>
>> Stop. Can you stop?
</details>

>> 大家当时就是这么说的。我在这档播客上有言论自由的权利。我觉得……
<details><summary>Original English</summary>
>> That's what people were saying. I have the right to free speech on this podcast. I think
</details>

>> 看你，又试图挑拨离间了。这……
<details><summary>Original English</summary>
>> Look at you trying to introduce wedges. This is
</details>

>> 不，我没有挑拨离间。我认为萨姆更适合当董事长。我认为她会是完美的首席执行官。
<details><summary>Original English</summary>
>> No, I'm not introducing wedges. I think Sam would be better as chairman. I think she would be the perfect CEO.
</details>

>> 这看起来是一对很好的搭档。
<details><summary>Original English</summary>
>> It seemed like a good partnership.
</details>

>> 看起来他们有着极好的合作关系。我同意。
<details><summary>Original English</summary>
>> It seems like they have a great partnership. I agree.
</details>

>> 萨拉确实令人印象深刻。
<details><summary>Original English</summary>
>> Sarah was really impressive.
</details>

>> 还有谁是你最喜欢的？萨克斯，你有最喜欢的吗？你心目中有人选吗？我确实有。我认为托马斯·拉丰关于风险投资概述的演讲棒极了，
<details><summary>Original English</summary>
>> Who else was your favorite? Sachs, did you have a favorite? Did you have somebody who thought I did? I thought Thomas Leafant crushed it with his presentation on the overview of venture capital
</details>

>> 他在大约一年半、两年前的峰会上也讲过。
<details><summary>Original English</summary>
>> and he did it at summit I guess a year and a half, two years ago.
</details>

>> 两年前，但我们要和他搞成一年一次。也许吧。我认为我们应该和他一起把它做成一个年度特辑，因为这太有意思了。
<details><summary>Original English</summary>
>> Two years ago, but we're going to make it a yearly with him. Maybe. I think we should make it an annual feature with him because it's so interesting.
</details>

>> 太棒了。简直太棒了。
<details><summary>Original English</summary>
>> So good. It's so good.
</details>

>> 真的太棒了。它提供了非常多的呃数据细节，来支撑许多我隐约有所感觉、但没有……
<details><summary>Original English</summary>
>> It's so good. It provided so much um numerical detail to support a lot of things I was kind of feeling but didn't
</details>

>> 拥有数据的事情。
<details><summary>Original English</summary>
>> have the data.
</details>

>> 概括来说，他的基本观察是：在最近这个周期中，如果一家公司的估值达到了 1000 亿美元，从这个节点再增长 10 倍的概率，要高于它从 100 亿美元增长到 1000 亿美元的概率。
<details><summary>Original English</summary>
>> To summarize it, he's his basic observation was in this last cycle, if a company gets to a hundred billion valuation, it's more likely to 10x from there than from 10 billion to 100 billion.
</details>

>> 呃，他有这方面的数据。是的，我记得……
<details><summary>Original English</summary>
>> Well, he had data on this. Yeah, I remember
</details>

>> 他有这方面的数据，就像是说，好吧，那这真的将带来改变。我记得那张幻灯片。
<details><summary>Original English</summary>
>> he had data on it which is like, okay, well, that's going to really change. I remember the slide.
</details>

>> 是的，就在那儿。是 8%。我……我把它记下来了。
<details><summary>Original English</summary>
>> Yeah, there it is. It's 8%. I I memorized it.
</details>

>> 是的。
<details><summary>Original English</summary>
>> Yes.
</details>

>> 没错。如果你是一位资本配置者，这个数字简直是在呐喊。
<details><summary>Original English</summary>
>> Yeah. If you're if you're a capital allocator, this one screamed.
</details>

>> 看。是的，没错。独角兽公司成长为百亿级独角兽的概率是 8%。百亿级独角兽成长为千亿级独角兽的概率大约是其两倍，为 13%。然后从千亿级独角兽跃升至万亿美元市值的概率是 31%。所以又翻了一番。而且我问过他，你知道，你能把这个推演到从一万亿成长到十万亿美元吗？我的猜测是它会遵循这一规律，我们将会看到大约……
<details><summary>Original English</summary>
>> Look. Yes, that's right. The odds of a unicorn getting to decacorn was 8%. The odds of a decacorn getting to a senicorn was about double that was 13%. And then the odds of it going from senicorn to a trillion dollar market cap was 31%. So double again. And I I asked him, you know, could you extrapolate this on one trillion getting to 10 trillion? My guess is that it would follow and we'll see about
</details>

>> 60% 的……
<details><summary>Original English</summary>
>> 60% of
</details>

>> 万亿美元市值的公司在未来几年内迈向 10 万亿美元。
<details><summary>Original English</summary>
>> trillion dollar market cap companies getting to 10 trillion in the next few years.
</details>

>> 顺便说一句，这些被称为万亿独角兽。在业界我们把万亿级的称为万亿独角兽。所以是的，
<details><summary>Original English</summary>
>> These are called trillicorns by the way. We call them trillion trilicorns in the industry. So yes,
</details>

>> 这在社会主义人群中肯定会非常受欢迎。大家一定会喜欢的。是的，
<details><summary>Original English</summary>
>> this is going to go over really socialist crowd. People are going to love this. Yeah,
</details>

>> 你只需要没收一家万亿独角兽 10% 的资产，就能偿还我们国债的 2%。实际上还挺划算的。
<details><summary>Original English</summary>
>> it's just all you got to do is seize 10% of a trilicorn and you pay off 2% of our national debt. pretty good deal actually.
</details>

>> 我们只需要 30 家万亿独角兽各 10% 的资产，我们就无债一身轻了。
<details><summary>Original English</summary>
>> All we need is 10% of 30 trilicorns and we're debt free.
</details>

>> 我的意思是，
<details><summary>Original English</summary>
>> I mean
</details>

>> 这并没有听起来那么疯狂。
<details><summary>Original English</summary>
>> it's not as crazy as it sounds.
</details>

>> 会比这更复杂吗？现在要是派我去，我能拿下它们每一家 60% 的资产。
<details><summary>Original English</summary>
>> Is it more complicated than that? Now if you send me in I'll get 60% of all of them.
</details>

>> 是的。那样我们就会有 300 亿的盈余，我们就能买下澳大利亚了。
<details><summary>Original English</summary>
>> Yes. And then we'll have a surplus of 30 billion and we can buy Australia.
</details>

>> 我们能更早把债务还清。
<details><summary>Original English</summary>
>> We'll pay it off much sooner.
</details>

>> 我们能买下古巴。
<details><summary>Original English</summary>
>> We could buy Cuba.
</details>

>> 我会先买下加拿大。更好的方案。
<details><summary>Original English</summary>
>> I'd buy Canada first. Better scheme.
</details>

### 法国洗衣房餐厅晚宴与名表花絮

>> 我会……你知道我会怎么做吗？我会去整整加拿大。我会买下比如温哥华或多伦多。就直接把他们拆分掉。直接买下其中一个地区。让我感谢一下……让我感谢托马斯·凯勒、法国洗衣房餐厅、安永，安永赞助了我们在 Liquidity 大会上极具创新性的会议中心。这是现场的一些照片。纽约证券交易所，他们在法国洗衣房餐厅举办了演讲嘉宾晚宴。这里有很棒的照片。它们是我们和托马斯·凯勒的合影，他们在现场做了一场精彩的采访。Niagen，他们赞助了健康休息室，其中包括恢复性静脉注射。他们是 All-In 播客以及我们所有长寿相关活动的官方 NAD 合作伙伴。我们的新伙伴、我们的新好兄弟杰克·保罗也在场。弗里德伯格，他是一个非常深思熟虑的人。
<details><summary>Original English</summary>
>> I would you know what I would do? I would [ __ ] with Canada. I would buy like Vancouver or Toronto. Just like break them up. just buy like one of the regions. And let me thank let me thank Thomas Keller, the French Laundry, EY who sponsored our very innovative meeting hub at Liquidity. Here are some photos of that. The New York Stock Exchange, they hosted the speaker dinner at the French Laundry. Amazing pictures here. They are of us with Thomas Keller and they did a great interview on site. Niagen, they hosted the wellness lounge which included recovery IVs. They're the official NAD partner of the All-In Pod and all of our longevity. Our new bestie, our new bestie, Jake Paul, was there. He's a really thoughtful guy, Freeberg.
</details>

>> 杰克·保罗太棒了。
<details><summary>Original English</summary>
>> Jake Paul was awesome.
</details>

>> 晚宴时我安排他坐在萨克斯旁边。
<details><summary>Original English</summary>
>> I sat him next to Sachs for dinner.
</details>

>> 是的，顺便说一句，他是一个优秀的投资人。
<details><summary>Original English</summary>
>> Yeah, he's a great investor, by the way.
</details>

>> 太棒了。棒极了。
<details><summary>Original English</summary>
>> Fantastic. Fantastic.
</details>

>> 他的投资组合非常出色。他带了一支优秀的团队。他的团队陪他一起来参加这次活动。
<details><summary>Original English</summary>
>> His portfolio is awesome. He had a great team. His team came with him for the thing.
</details>

>> 出色的策略。是的。
<details><summary>Original English</summary>
>> Great strategy. Yeah.
</details>

>> 关于托马斯·凯勒我要说一点，他的手性格调很高。我不知道你们有没有注意到。
<details><summary>Original English</summary>
>> One thing I'll say about Thomas Keller, he had a strong watch game. I don't know if you guys noticed that.
</details>

>> 大概注意到了。
<details><summary>Original English</summary>
>> Probably noticed it.
</details>

>> 很有品位。他戴了一只 Aquanaut（海底探险家），绿胶带、玫瑰金，上面带有一项复杂功能。我当时一直在琢磨那项复杂功能到底是什么。我没能完全肉眼看出来。
<details><summary>Original English</summary>
>> Nice potential. He had a aqua knot green band rose gold a complication on there. I was trying to trying to figure out what the complication was. I couldn't quite eyeball it.
</details>

>> 我不知道你看到没有，查马斯。
<details><summary>Original English</summary>
>> I don't know if you saw it, Jimoth.
</details>

>> 我看了一眼，当时就觉得，“哇，这非常……非常高雅。”托马斯·凯勒。我的意思是，法国洗衣房餐厅简直绝妙超凡。你有最喜欢的……
<details><summary>Original English</summary>
>> I was I looked at it and I was like, "Wow, this is very it's very elegant." Tell us Keller. I mean, the French Laundry is just transcendent. Did you have a favorite
</details>

>> 菜吗？当然有。是鸭肉还是宫崎牛？
<details><summary>Original English</summary>
>> dish? Of course. Was it the duck or was it the Miyazaki?
</details>

>> 鸭肉棒极了。宫崎牛肉也很棒，但我认为西米珍珠是最好的。噢，生蚝与珍珠。那就是生蚝配鱼子酱。萨克斯，你最喜欢哪道菜？你有最喜欢的吗？
<details><summary>Original English</summary>
>> The duck was excellent. The Miyazaki beef was excellent, but the the tapioca pearls I thought was the best. Oh, oysters and pearls. That's your oysters with caviar. Sax, what was your favorite there? Do you have a favorite?
</details>

>> 某道与鱼子酱相关的菜。
<details><summary>Original English</summary>
>> One of the caviar related dishes.
</details>

>> 是的，那就是“生蚝与珍珠”。第二天我们打了一轮高尔夫。我们打了一场……
<details><summary>Original English</summary>
>> Yeah, that's oysters and pearls. Round of golf. The following day, we played a
</details>

<!-- chunk 9/13 -->

和大家一起打了九洞最佳球位赛。太棒了。真的太棒了。

<details><summary>Original English</summary>
nine-hole scramble with everyone. It was great. So great.
</details>

>> 你们赌了多少，谁赢了？

<details><summary>Original English</summary>
>> How much did you gamble and who won?
</details>

>> 我们跟 Athena 的首席商务官 Chris Hoe 打，一洞 100 美元。不过，你知道的，那家伙水平大概是+1，所以无所谓了。我觉得我们输了三个单元。所以，我们输了——

<details><summary>Original English</summary>
>> We had a $100 a hole versus Chris Hoe, who's the chief business officer of Athena. But, you know, that [ __ ] is like a plus one, so whatever. I think we lost three units. So, we lost
</details>

>> 300 块。

<details><summary>Original English</summary>
>> 300 bucks.
</details>

>> 好的。也向我们的另一位合作伙伴 Athena 致敬。Athena. Wow.com。去获取一个月免费体验。行吧。不管了。我得停止打广告了。最重要的是，大家都非常沮丧，因为 Liquidity 门票卖光了，大家进不去。大概有 3000 份申请。下一次肯定会卖得更快，呃。所以，如果你想参加 9 月 13、14 和 15 日的峰会，请访问 allin.com/events 提交申请。Freeberg 正在为那个活动做一些疯狂的事情。为那个活动做一些疯狂的事情，呃，一定会很酷的。

<details><summary>Original English</summary>
>> All right. Shout out to our other partner, Athena. Athena. Wow.com. Go get a month free. All right. Whatever. I got to stop showing. Most importantly, everybody was very upset that liquidity sold out and people couldn't get in. There were like 3,000 applications. It's going to sell even faster uh next time around. So, go to allin.com/events and get your applications in if you want to come to Summit September 13th, 14th, and 15th. Freeberg's doing some wild stuff. some wild stuff for that event and uh it's gonna be cool.
</details>

>> 你真是疯了。你现在的制作规格变得非常古怪、失控，还有 Shimoth，

<details><summary>Original English</summary>
>> You're losing your mind. You're now becoming very eccentric, unhinged in your production value and Shimoth,
</details>

>> 你挑选 Liquidity 演讲嘉宾的方式非常挑剔，因为 Liquidity 和峰会不同。峰会就像个节日。那是一场盛大的派对。有各种各样非常有趣的跨界内容。但 Liquidity 旨在实现一件事，那就是让世界上最重要的资本配置者拥有一个齐聚一堂、辩论、学习、交流、建立关系的地方。我希望人们走出那里时，能带走切实有用的关系人脉。我以前就跟你们说过这个，因为资本正是塑造世界上所发生之事的关键力量。所以我认为，在如何策划那场活动的每一个要素上，我们必须极其挑剔。它的定位不是让人随便买张票就能进的，但随便买张票就能进这也是非常公平、合理且挺好的事。峰会就是个派对。是一种氛围。

<details><summary>Original English</summary>
>> you've been very selective in your approach to the liquidity speakers because liquidity is different than the summit. The summit is like a festival. It's a huge party. There's all this really interesting cross-sectional stuff. But liquidity is meant to be for one thing which is the most important capital allocators in the world should have one place to convene, debate, learn, talk, build relationships. And I want people to walk out of there with relationships that they can use. And I told you this before because capital is what shapes the things that occur in the world. So I think that we have to be extremely selective in how we curate every element of that show. It's not meant to be that you can just buy a ticket, but to just buy a ticket, which is also a very fair and rational and nice thing. The summit is a party. It's a vibe.
</details>

### 通胀数据与宏观政策

>> 确实棒极了。你会学到很多东西，度过一段美好时光。你也会得到娱乐。所有那些很棒的东西。好了，我们继续。今天早上的突发话题。5 月份的 CPI 和 PPI 数据表现过热。通胀正在狂飙。这就来了。CPI 显然是消费者物价指数，从买方角度追踪通胀。房租、杂货、汽油、医疗保健，所有那些东西。PPI 是生产者物价指数，从卖方角度追踪通胀。批发商品、原材料等等等等。CPI 同比上涨 4.2%，创下自 2023 年 4 月以来的最高水平。那是你们的图表。PPI 同比上涨 6.5%，创下自 2022 年底以来的最高水平。这是你们的 Polymarket 预测。2026 年通胀达到 5% 的概率为 21%。呃，然后一个相邻的 Polymarket 预测，美联储今年加息的概率为 49%。在伊朗战争爆发前，这个数字还低于 10%。顺便说一句，欧洲央行周四刚加息 25 个基点。这是他们自 2023 年 9 月以来的首次加息。Freedberg，我们从中能看出什么？这全跟伊朗战争有关。是的，那是——

<details><summary>Original English</summary>
>> It's awesome. And you're going to learn a lot and have a good time. You'll be entertained. All that great stuff. All right, let's keep going. Breaking topic this morning. CPI and PPI for May came in hot. Inflation is ripping. Here we go. CPI is obviously the consumer price index that tracks inflation from the buyer side. Rent, groceries, gas, healthcare, all that stuff. PPI is the producer price index that tracks inflation from the seller side. Wholesale goods, raw materials, yada yada. CPI came in at 4.2% year-over-year, highest since April 2023. There's your chart. PPI came in at 6.5% year-over-year, highest since the end of 2022. Here's your poly market. 21% chance inflation hits 5% in 2026. Uh and then an adjacent poly market chances of the Fed hiking this year at 49%. It was under 10% before the Iran war started. By the way, European Central Bank just raised rates a quarter point on Thursday. This was their first rate hike since September 2023. What do we take from this Freedberg? It's all related to the Iran war. Yeah, that's the
</details>

>> 伊朗战争肯定带来了一次能源价格突增，推高了核心指数，但还有宏观层面的一点，那就是政府支出失控，通胀失控，从根本上说，随着局势瓦解，利率就会上升。所以我认为我们应该有某种预期，特别是在 Kevin Warsh 执掌的美联储之下，我认为我们可能会看到高于 5.5%、6% 的隔夜利率。这并非不可预见。所以，

<details><summary>Original English</summary>
>> there's definitely an energy blip from the Iran war that drove the core index up, but there's also the macro point which is government spending out of control, inflation out of control and fundamentally as things unravel you have rising rates. So I think we should kind of expect especially with a Kevin Worsh Fed, I think we could see north of five and a half, 6% overnight rates. It's not unforeseeable. So,
</details>

>> 这就是我们的货币政策和财政政策的本质，我们的国会议员们投票把我们未来的所有收入都扔进了[ __ ]。但我们现在就面对着这个局面，

<details><summary>Original English</summary>
>> this is just the nature of our monetary policy and our fiscal policy with our congressional um members that vote all of our future earnings away into [ __ ] But here we are
</details>

>> 而且情况要糟糕得多，

<details><summary>Original English</summary>
>> and and far worse
</details>

>> 谁也没料到。Chimath，你的看法是什么，然后我再跟你总结一下。

<details><summary>Original English</summary>
>> that nobody expected. Chimath, your thoughts and then I'll wrap up with you.
</details>

>> 那是我挺长时间以来听到的最具被动攻击性的观点了，来自——

<details><summary>Original English</summary>
>> That was the most passive aggressive take I've heard in a while from
</details>

>> 他对此有点不爽。是的。显然他对看着这种蠢事发生感到有点愤恨。

<details><summary>Original English</summary>
>> He's a little upset about it. Yes. Clearly he's a little bitter about just so stupid to watch.
</details>

>> 你能告诉我们你真正的感受吗？怎么了？说实话，还有什么好说的呢？我都说了大概一百遍了。这简直愚蠢透顶。这个国家财富不平等的根本问题，这个国家通货膨胀的根本问题，核心问题，这一切全都根源于政府过度支出。就这么简单。所有这些，我们全都在讨论网络边缘的琐碎运转。网络的核心是政府超支，因为为了当选，你必须给别人提供比他们今天所拥有的更多的东西。人们就是靠这个当选的。250 年后的今天，我们落到了这步田地。我不知道是否有摆脱困境的意愿或途径，但它的表现形式之一，将是在这后期阶段出现更高的利率，作为对通货膨胀的回应，而我们现在就处于这个境地，你懂的。

<details><summary>Original English</summary>
>> Can you tell us how you really feel? What happened? Like honestly, like what else is there to say? I've said it like a hundred times. It's just idiotic. The the core problem with wealth inequality in this country, the core problem with inflation in this country, the core problem, all of it roots back to excess government spending. End of story. All of this, we're all talking about machinations at the edge of the network. The core of the network is overspending by the government because in order to get elected, you need someone to give you something more than you have today. That's how people get elected. And here we are 250 years later. I don't know if there's the will or the way to get out of it, but one of the manifestations of it will be in this late stage higher rates and as a response to inflation and here we are, you know.
</details>

### 中东冲突与能源市场外溢

>> 好的，Chim，你对此有什么看法？正如我们听其他总统说过的那样，这是暂时的吗？伊朗战争是否有缓和的退路？我不知道这是否超出了我们所有人的能力范围，但这似乎确实是一个在期中选举前夕发生的充满挑战的时刻，消费者原本预期他们的生活成本会下降，预期自己会从这个黄金时代中受益，但这还没有发生。嗯，你看，这确实令人担忧。我觉得我原本没料到公布的数据会这么高。那么，是什么在维持局面的稳定呢？我们仍有希望不会看到 CPI 彻底失控。部分原因在于中国一直在平抑全球范围内的能源消费。因此我们某种程度上抑制了每桶 200 美元的油价。事实上，我们现在的油价还在 100 美元以下。与此同时，我认为这提前推动了许多更实用的能源生产来源，不仅在美国，也在国外。具体而言，我的意思是指太阳能。仅仅因为它是简单的、被动的，你不需要大量的许可审批，也不需要空气清洁许可之类的东西。

<details><summary>Original English</summary>
>> All right, Chim, what's your what's your take on this? Is it a transient as we uh have had other presidents say? Is it uh is there a offramp for the Iran war? I don't know if this is above all of our pay grades, but this does seem to be a challenging moment happening right before the midterms and consumers expected that their cost of living would go down and that they would benefit from this golden age and it hasn't happened yet. Well, look, it's concerning. I don't think that I expected the print to be this hot. Now, what's keeping things in line? there's still a chance that we're not going to see CPI go absolutely crazy. And part of that is because China has been smoothing the energy consumption globally worldwide. And so we've kind of kept a damper on $200 a barrel oil. In fact, we're subundred. At the same time, I think it's pulled forward a lot of more practical sources of energy production, not just in the United States, but abroad. Specifically, what I mean is solar. just because it's simple, it's passive, and you don't need you don't need a lot of permitting, and you don't need clean air permits and the like.
</details>

>> 所以，所有这些因素成功抑制了局面。

<details><summary>Original English</summary>
>> So, all of these things have been able to keep a lid on it.
</details>

>> 如果中国不知怎么地耗尽了储备，他们需要重新回到现货市场每天额外购买 300 万桶，那么石油价格远超 100 美元、甚至可能达到每桶 150 到 200 美元之间的风险就会非常大。这在 CPI 方面会带来许多下游连锁问题。甚至不是因为美国的能源供应，而是真正因为石油在全世界所供应的原材料投入，随后会被人们为日常用品支付的成本所吸收，从而可能导致价格上涨。

<details><summary>Original English</summary>
>> If China somehow runs out of reserves, and they need to go back into the spot market to buy an extra 3 million barrels a day, there's a very big risk that oil gets into the well past 100 and maybe between 150 and 200 a barrel. That has a lot of downstream problems with respect to CPI. Not even because US energy supply, but really because the inputs that oil feeds all around the world that then get absorbed by the costs that people pay for everyday things could go up.
</details>

>> 所以我认为 PPI 数据应该成为一个警钟，让我们以此为契机宜早不宜迟地给这场围绕伊朗的局势找到缓和出口。我只是……除非，再次强调，因为我们不知道中国发生了什么，因为我们谁都没去过那里。除非总统与习近平达成了某种谅解，摸清了中国体系中实际有多少供应和闲置空间，这或许能让他走一条漫长得多的道路来在伊朗取得决定性的胜利，但是……我……这次中国之行原本应该有一些切实的已知解决方案。我们还没有听到明确陈述出来的方案。Sachs，你对通胀数据有什么看法？是否存在结束这场伊朗战争的某种金桥退路？

<details><summary>Original English</summary>
>> So I think the PPI number should be an alarm that we use to offramp this around situation sooner rather than later. I just unless again because we don't know what happened in China because none of us were there. Unless there's an understanding that the president has with Xi about how much actual supply and slack is in the Chinese system and that may allow him to take a much longer road to get a conclusive and decisive win in Iran, but I I don't there was supposed to be some tangible known resolutions with this China trip. We haven't heard them explicitly stated yet. What's your take on uh this Sachs? uh the inflation print and is there like a a golden bridge to to end this war in Iran?
</details>

>> Jake，问题在于当你问我这个问题时，人们会以为我掌握了某种内幕消息，但我并没有。听着，PPI 数据摆在那里就是那样了。我大体同意 Chamas 所说的话。我唯一想补充的是，它基本上符合预期。这就是为什么市场今天实际上是在上涨的。通常情况下，如果公布的数据出人意料且通胀高企，那么市场就会下跌，因为市场开始消化更高利率的影响。今天市场并没有这么做。所以它符合预期。但我大体同意 Chamas 所说的。

<details><summary>Original English</summary>
>> Jake, the problem is when you asked me that question, people assume that I have some sort of insight information and I don't look the PPI print is what it is. I largely agree with what Chamas said. The only thing I would add is that it was largely in line with expectations. That's why the market is actually up today. Normally if there's a surprise print and inflation is high then the market is down because the market starts pricing in the implication of higher interest rates. It's not doing that today. So it's in line with expectations. But I largely agree with what Chamas said.
</details>

>> 是的。好的。好吧，听着，我们还得谈谈其他选举。你知道，我的看法是，发动这场伊朗战争真是一个巨大的、灾难性的错误，希望我们能够抽身出来。呃，这带来的下游影响简直是灾难性的。呃，我希望有一个快速的解决办法，或者某种在拖入一年、两年或三年之前抽身而出的途径。我们显然不能陷入一场无休止的战争。

<details><summary>Original English</summary>
>> Yeah. All right. Well, listen, we got to get to other elections. You know, my take on it is just huge colossal era starting this Iran war and hopefully we can get out of it. Um the downstream effects of this are just disastrous. Um, I'm hoping there's a quick resolution or some way to get out of it before it goes to, you know, a year or two or three. We can't be in a forever war, obviously.
</details>

>> 纳斯达克今天上涨了 2.5%。在数据火爆的情况下，通常不会发生这种情况，因为再次说明，科技股对高利率是最敏感的。所以，市场在此时似乎正在消化——

<details><summary>Original English</summary>
>> NASDAQ up 2 and a half% today. That normally doesn't happen when there's a hot print because again, like tech stocks are the most susceptible to high interest rates. So, the market at this point seems to be pricing in
</details>

>> 一种解决方案。不过我们拭目以待。我们拭目以待。

<details><summary>Original English</summary>
>> a resolution. But we'll see. We'll see.
</details>

>> 我们拭目以待。是的。我的意思是，这只是一件大家都知道伊朗是个泥潭的事情，确实曾是一个巨大的错误。好了——

<details><summary>Original English</summary>
>> We'll see. Yeah. I mean, it's just this is a everybody knows Iran is a quagmire and really was was a huge mistake. All
</details>

<!-- chunk 10/13 -->

### 洛杉矶市长初选计票争议

好，与其由我来念所有这些细节，不如让我们来聊聊围绕洛杉矶市长初选计票所引发的焦虑与担忧。弗里伯格（Freeberg），我知道你情绪正激动。

<details><summary>Original English</summary>
right,
 let's
 talk
 about
 the
 hand
 ringing
around
 vote
 counts
 in
 the
 LA
 mayoral
primary
 instead
 of
 me
 reading
 all
 these
details.
 Just
 Freeberg,
 I
 know
 you're
hot.
</details>

>> 我想大家都对此有所了解了。是的。

<details><summary>Original English</summary>
>> I
 think
 we
 know
 about
 it.
 Yeah.
</details>

>> 是的。我觉得只要你在 X 上，基本上整条时间线都是这个内容。呃，弗里伯格，你怎么看？洛杉矶、特别是加州的选举制度是否存在腐败？这场选举是被斯宾塞·普拉特（Spencer Pratt）窃取了，还是它仅仅——

<details><summary>Original English</summary>
>> Yeah.
 I
 think
 if
 you're
 on
 X,
 it's
essentially
 your
 entire
 feed.
 Uh
Freeberg,
 what's
 your
 take?
 Is
 the
election
 system
 in
 Los
 Angeles,
specifically
 in
 California,
 corrupt?
 And
is
 this
 election
 been
 stolen
 from
Spencer
 Pratt
 or
 is
 it
 just
</details>

>> 根本就没有选举。

<details><summary>Original English</summary>
>> There
 is
 no
 election.
</details>

>> 根本不曾有过选举。

<details><summary>Original English</summary>
>> There
 was
 no
 election.
</details>

>> 根本就没有选举。

<details><summary>Original English</summary>
>> There
 is
 no
 election.
</details>

>> 好吧。所以“勺子并不存在”（there is no spoon）。你拥有选举的权利已经不复存在了。你是一个听命于那些指定你管理者的人的公民。你不再被允许投票——

<details><summary>Original English</summary>
>> Okay.
 So
 there
 is
 no
 spoon.
 Your
 rights
to
 have
 an
 election
 are
 gone.
You
 are
 a
 citizen
 of
 those
 who
 tell
 you
who
 your
 overseers
 are.
 You
 are
 no
longer
 allowed
 to
 vote
</details>

>> 允许投票——

<details><summary>Original English</summary>
>> allowed
 to
 vote
</details>

>> 选出你选出的代表。他们现在成了被任命的代表。所以好好享受这些任命吧，而这些任命是谁做出的？

<details><summary>Original English</summary>
>> for
 your
 elected
 representatives.
 They
are
 now
 appointed
 representatives.
 So
enjoy
 the
 appointments
 that
 have
 been
made
 by
 who?
</details>

>> 由构建了母体（the matrix）的人任命的。

<details><summary>Original English</summary>
>> Appointed
 by
 those
 who
 have
 constructed
the
 matrix.
</details>

>> 明白了。现在我懂这个背景了。“勺子并不存在”。史密斯特工（Agent Smith）和所有的史密斯特工掌管着一切。那么，这里给你看一些统计数据。洛杉矶县市长选举日当天的现场投票：斯宾塞·普拉特 35%，凯伦·巴斯（Karen Bass）29%，尼皮亚·拉曼（Nipia Ramen）26%。

<details><summary>Original English</summary>
>> Got
 it.
 Now
 I
 understand
 the
 background.
There
 is
 no
 spoon.
 Agent
 Smith
 and
 all
the
 Agent
 Smiths
 are
in
 charge.
 So,
 here's
 some
 statistics
for
 you.
 In-person
 voting
 the
 day
 of
 the
election
 in
 Los
 Angeles
 County
 for
mayor.
 Spencer
 Pratt
 35%.
 Karen
 Bass
29%.
 Nipia
 Ramen
 26%.
</details>

在选举日之前收到的邮寄选票：巴斯 38%，普拉特 28%，拉曼 20%。然后是所有在选举日之后送达的选票：拉曼 37%，巴斯 35%，普拉特 19%。所以普拉特的选举日后邮寄选票下降了三分之一。从统计学上看，寄出迟到选票的人群中，支持普拉特的比例下降了三分之一，支持尼皮亚·拉曼的激增了 80%。而如果仅将选举日前后的邮寄选票做对比，凯伦·巴斯则减少了 10%。我不知道是否存在某种社会政治学的方法，让你能评估这些统计数据，并假定这都是个人在投下自己认为谁应该当洛杉矶市长的个别选票。

<details><summary>Original English</summary>
mail-in
 ballots
 received
 before
 election
day,
 38%
 for
 Bass,
 28%
 for
 Pratt,
 20%
for
 Ramen.
 And
 then
 all
 these
 ballots
that
 arrive
 after
 election
 day,
 37%
 for
Ramen,
 35%
 for
 Bass,
 19%
 for
 Pratt.
 So
Pratt's
post
 election
 mailin
 ballots
 declined
 by
one/ird.
 So
 statistically
 the
 population
of
 people
 that
 send
 in
 their
 ballots
late
 reduced
 for
 Pratt
 by
 a
 third
increased
 for
 Nipia
 Ramen
 by
 80%.
And
 Karen
 Bass
 10%
 less
 if
 you
 just
 look
at
 the
 mail
 in
 ballots
 before
 and
 after
election
 day
 as
 a
 comparison.
 I
 don't
know
 if
 there's
 a
 socopolitical
 way
 that
you
 can
 assess
 those
 statistics
 and
assume
 that
 these
 are
 individuals
casting
 their
 individual
 vote
 for
 who
they
 think
 should
 be
 mayor
 of
 LA.
 And
</details>

尼克（Nick），如果你能调出地图的话，我认为这值得一看。基本上，尼蒂亚·拉曼（Nitia Ramen）获得的增量选票集中出现在洛杉矶的贫民窟（Skid Row）一带。听着，我不是选举否定论者。我历来不是那种相信选举存在舞弊、有人窃取选票这一说法的人。但当你看到现场投票、选举日前邮寄选票、选举日后邮寄选票的基本统计数据时，对于这种社会政治转变究竟如何以这种方式发生，就演变成了一个真正的统计困境。

<details><summary>Original English</summary>
Nick,
 if
 you'll
 just
 pull
 up
 the
 map,
which
 I
 think
 is
 worth
 taking
 a
 look
 at.
Basically,
 the
 concentration
 of
incremental
 votes
 that
 Nitia
 Ramen
 got,
came
 around
 the
 Skid
 Row
 area
 in
 Los
Angeles.
 And
 look,
 I'm
 not
 an
 election
denier.
 I'm
 not
 someone
 who's
historically
 believed
 the
 idea
 that
elections
 are
 fraud
 and
 people
 have
stolen
 votes.
 But
 when
 you
 look
 at
 the
basic
 statistics
 of
 what
 happened
 in
person,
 mail
 in
 before,
 mail
 in
 after
election
 day,
 it
 becomes
 a
 real
statistical
 quagmire
 on
 how
 did
 this
sort
 of
 a
 sociopolitical
 shift
 happen
 in
such
 a
 way
 that
 it
 did.
 Now,
 there
 was
 a
</details>

现在，有一份报告发布了，尼克，如果你能把它调出来的话——由美国众议院行政委员会发布。这发布于 2020 年 5 月，他们强调了 2018 年加州中期选举，以及他们看到在那次中期选举中由于所做出的一些立法变动而产生的挑战。首先，加利福尼亚州议会第 1921 号法案将该州无限度收割选票（ballot harvesting）的做法合法化。这是在 2018 年中期选举前后通过的。这意味着加利福尼亚州的任何个人都有权去向任何其他个人收集选票，无论彼此关系如何，填写并寄送出去。

<details><summary>Original English</summary>
report
 published,
 Nick,
 if
 you
 could
pull
 this
 up
 by
 the
 US
 House
 of
Representatives
 Committee
 on
 House
Administration.
 This
 was
 published
 in
May
 of
 2020
 and
 they
 highlighted
 the
2018
 California
 midterm
 elections
 and
the
 challenges
 they
 saw
 arise
 in
 that
midterm
 elections
 because
 of
 some
 of
 the
legislative
 changes
 that
 were
 made.
First,
 California
 Assembly
 Bill
 1921
legalized
 the
 practice
 of
 unlimited
ballot
 harvesting
 in
 the
 state.
 This
 was
passed
 around
 2018
 around
 the
 midterms.
What
 that
 means
 is
 that
 any
 individual
in
 the
 state
 of
 California
 has
 the
 right
to
 go
 and
 collect
 ballots
 from
 any
 other
individuals
 regardless
 of
 relationship,
fill
 them
 out
 and
 send
 them
 in.
</details>

加利福尼亚州在两年后、18 个月后，还通过了一项法律，永久确立了加利福尼亚州的每位登记在册人员都将收到一张选票。因此，数千万张选票随后被邮寄出去。接着又通过了另一系列法律，规定任何人都可以登记投票。你不需要证明你的公民身份。你可以使用例如健身房会员卡作为证明。因此任何人都可以登记投票。在领取选票时没有身份证明。没有任何证明表明填写选票的人与该选票原本应该投票的人之间有任何关系。并且，一个人外出收集数百或数千张选票并送交进去，在这些邮寄选票的投票流程中都是合法的，而且它们都算合格。

<details><summary>Original English</summary>
California
 2
 years
 later,
 18
 months
later,
 also
 passed
 a
 law
 that
 made
 it
permanent
 that
 every
 person
 registered
in
 the
 state
 of
 California
 would
 get
 a
ballot.
 So
 tens
 of
 millions
 of
 ballots
then
 get
 mailed
 out.
 Then
 there
 was
another
 series
 of
 laws
 that
 were
 passed
that
 said
 anyone
 can
 register
 to
 vote.
You
 don't
 need
 to
 prove
 your
citizenship.
 You
 can
 use
 a
 gym
membership
 card
 as
 an
 example.
 So
 anyone
can
 register
 to
 vote.
 There
 is
 no
 proof
of
 ID
 when
 you
 get
 a
 ballot.
 There
 is
 no
demonstration
 that
 the
 person
 who
 fills
out
 the
 ballot
 has
 anything
 to
 do
 with
the
 individual
 who's
 supposed
 to
 be
voting
 that
 ballot.
 And
 it
 is
 legal
 for
an
 individual
 to
 go
 out
 and
 collect
hundreds
 or
 thousands
 of
 ballots,
 ship
them
 in,
 and
 they
 will
 all
 qualify
 in
these
 kind
 of
 mail-in
 ballot
 voting
processes.
 So
</details>

所以并没有发生违法或欺诈的事情。事实上，该系统正是完全按照设计初衷在运行。它的建立和构造方式使得，只要有恰当的构架，在加利福尼亚州所谓“自由选举”的名义下，你就可以让某个人被任命——不是选出，而是被任命——担任政府中的特定职位。这是对我们在自由民主制度中投票给人这一权利的基础性破坏。我觉得随着时间推移，这种权利慢慢被侵蚀到现在这种地步，指出这一点并不代表我是什么疯狂的 MAGA 之类的人（不管别人想怎么界定我），但你可以顺着这个清单看下去，它们全部写在这份文件里，这些加州随着时间推移通过的每一项法律，合起来为选举沦为任命创造了环境与结构，使之不再是自由的民主选举；而在真正的自由民主选举中，其原则——非常重要的原则——应该是一人一票，并且如果你选择不投票，你的选票就不应该被计入。所以我认为这里不存在欺诈。我不认为有任何欺诈。

<details><summary>Original English</summary>
there's
 nothing
 illegal
 or
fraudulent
 going
 on.
 In
 fact,
 the
 system
is
 operating
 exactly
 as
 intended.
 It
 has
been
 set
 up
 and
 structured
 in
 a
 way
 that
with
 the
 right
 construct,
 you
 can
 get
 an
individual
 appointed,
 not
 elected,
 but
appointed
 to
 a
 particular
 role
 in
government
 under
 a
 quote
 free
 election
in
 California.
 This
 is
 a
 foundational
destruction
 of
 our
 rights
 to
 vote
 for
people
 in
 a
 free
 democracy.
 I
 feel
 it's
been
 eroded
 slowly
 over
 time
 to
 such
 an
extent
 now
 and
 I'm
 not
 some
 crazy
 MAGA
mother
 whatever
 people
 want
 to
 classify
me
 as
 for
 pointing
 this
 out
 but
 you
 can
go
 down
 this
 list
 they
 are
 all
 written
out
 in
 this
 document
 every
 one
 of
 these
laws
 that
 were
 passed
 in
 California
 over
time
 that
 in
 aggregate
 create
 the
environment
 and
 the
 construction
 for
elections
 to
 become
 appointments
 and
 no
longer
 free
 democratic
 elections
 where
the
 principle
 very
 importantly
 the
principle
 should
 be
 one
 individual
one
 vote
 and
 if
 you
 opt
 to
 not
 vote,
your
 vote
 should
 not
 be
 counted.
 So
 I
think
 that
 there's
 no
 fraud.
 I
 don't
think
 there's
 anything.
</details>

>> 听起来你好像认为存在大规模舞弊。

<details><summary>Original English</summary>
>> It
 sounds
 like
 you
 believe
 there's
massive
 fraud.
</details>

>> 是的。我认为这不是欺诈。这就是——这就是法律设立的方式。

<details><summary>Original English</summary>
>> Yeah.
 I
 think
 this
 is
 not
 fraud.
 This
 is
this
 is
 the
 way
 the
 laws
 are
 set
 up.
</details>

>> 这不是欺诈。

<details><summary>Original English</summary>
>> It's
 not
 fraud.
</details>

>> 这是法律设立的方式。

<details><summary>Original English</summary>
>> It's
 the
 way
 the
 law
 is
 set
 up.
</details>

>> 好吧。萨克斯（Sachs），你说这是欺诈。

<details><summary>Original English</summary>
>> Okay.
 Sachs,
 you
 say
 a
 fraud.
</details>

>> 这就是一套任命制度。

<details><summary>Original English</summary>
>> This
 is
 the
 system
 of
 appointment.
</details>

>> 好吧。是的。在我听来，你描述的就像是欺诈，但你表达的是制度允许了欺诈。

<details><summary>Original English</summary>
>> Okay.
 Yeah.
 It
 sounds
 to
 me
 like
 you're
describing
 fraud,
 but
 you're
 saying
 the
system
 allows
 fraud.
</details>

>> 欺诈是违法行为。欺诈是指触犯法律。法律允许他们这样做。如果你在贫民窟付钱给别人，那是不合法的。

<details><summary>Original English</summary>
>> Fraud
 is
 breaking
 the
 law.
 Fraud
 is
breaking
 the
 law.
 The
 law
 allows
 them
 to
do
 it.
 If
 you
 paid
 people
 on
 Skid
 Row,
that's
 not
 legal.
</details>

>> 那是非法的。但你被允许出去让任何人登记。你被允许外出收集所有选票。而从事这件事的人，只要不是按收集到的每张选票拿钱，在法律上就是被允许这么做的。让我暂停一秒钟。当你孤立地看待这些法律中的任何一项时，你都能理解其背后存在某种利他意图，或者可以被表述为具有利他意图。增加选民活跃度。赋予每个人投票权。让更多的人有途径、有更多渠道去投票，等等等等。你可以合理化解释其中的每一项法律是如何让流程更容易、如何为该体系提供润滑的。如今我们就拥有了一个所谓的为每个人都“更加触手可及的民主”。但事实是，保险界有一个概念叫逆向选择（adverse selection），意思是一旦出现利用漏洞的机会，犯罪分子就会加以利用，以至于形成不对称。犯罪分子，或者那些心怀不轨者，而不是行善者，就会找到利用系统漏洞的方法，就像黑客入侵网络一样——

<details><summary>Original English</summary>
>> That
 is
 illegal.
 But
 you
 are
 allowed
 to
go
 out
 and
 get
 anyone
 to
 register.
You're
 allowed
 to
 go
 out
 and
 collect
 all
the
 ballots.
 And
 the
 people
 that
 are
doing
 it,
 as
 long
 as
 you're
 not
 getting
paid
 per
 ballot,
 you're
 legally
 allowed
to
 do
 it.
 Let
 me
 pause
 for
 one
 second.
When
 you
 look
 at
 any
 one
 of
 these
 laws
in
 isolation,
 you
 can
 understand
 that
there
 is
 some
 altruistic
 intention
 or
there
 can
 be
 framed
 to
 be
 an
 altruistic
intention
 behind
 it.
 Increase
 voter
activity.
 Give
 everyone
 the
 right
 to
vote.
 give
 more
 people
 access,
 more
channels
 to
 vote,
 etc.,
 etc.
 And
 you
 can
rationalize
 away
 how
 every
 one
 of
 these
laws
 makes
 it
 easier
 and
 adds
lubrication
 to
 the
 system.
 And
 now
 we've
got
 a
 quote
 more
 accessible
 democracy
for
 everyone.
 But
 the
 truth
 is
 that
there
 is
 a
 concept
 in
 insurance
 called
adverse
 selection,
 which
 is
 if
 there
 is
a
 moment
 to
 exploit
 something,
 the
criminals
 will
 exploit
 it
 to
 the
 extent
that
 it
 will
 become
 asymmetric.
 the
criminals
 or
 the
 or
 the
 do
 bads,
 not
 the
dogooders,
 will
 find
 a
 way
 to
 take
advantage
 of
 a
 hole
 in
 a
 system
 just
like
 hackers
 do
 to
 break
 into
 a
 network
</details>

>> 这就是你系统拉曼和斯宾塞·普拉特所做的。

<details><summary>Original English</summary>
>> and
 that's
 what
 you
 system
 ramen
 and
Spencer
 Pratt
 did.
</details>

>> 这一套机制、这一套结构，使得一个系统如今演变成了一场任命。所以你认为运作系统比斯宾塞·普拉特更好？

<details><summary>Original English</summary>
>> This
 set
 of
 mechanisms,
 this
 set
 of
construction
 has
 allowed
 for
 a
 system
that
 now
 has
 evolved
 into
 an
appointment.
 So
 you
 believe
 worked
 the
system
 better
 than
 Spencer
 Pratt?
</details>

>> 她的作弊操作更高明。显然，你可以从图表中看出来。就看看票数吧。

<details><summary>Original English</summary>
>> She
 had
 a
 better
 cheating
 operation.
Obviously,
 you
 can
 see
 it
 in
 the
 chart.
the
 just
 look
 at
 the
 number
 of
 votes.
</details>

>> 好吧，在这里界定一下作弊，好让我们能明确清楚。

<details><summary>Original English</summary>
>> Okay,
 define
 cheating
 here
 just
 so
 we're
clear.
</details>

>> 怎么会出现巴斯基本保持平稳，而拉曼和普拉特就直接对调位置的情况呢？在选举日当天，他明显是第二名，然后他们持续计票了一周。他们甚至都不知道自己理应收到多少张选票。我是说，所有这些东西都根本没有确定下来。好吧，让我解释一下作弊是如何运作的。而且正如弗里伯格所指出的，它可能是合法的，也可能是不合法的。所以，你知道的，我不想被这种欺诈是合法还是非法带偏了焦点，但我认为我们大家都知道这是不正当的。它是这样运作的。首先，

<details><summary>Original English</summary>
>> How
 does
 it
 happen
 where
 Bass
 stays
 flat
and
 then
 Ramen
 and
 Pratt
 just
 switch
places?
 So
 on
 election
 day,
 he's
 the
clear
 number
 two
 and
 then
 they
 keep
counting
 for
 a
 week.
 They
 don't
 even
know
 how
 many
 ballots
 they're
 supposed
to
 have.
 I
 mean,
 none
 of
 the
 stuff
 is
locked
 down.
 Okay,
 let
 me
 explain
 how
the
 cheating
 works.
 And
 to
 Freeberg's
point,
 it
 may
 or
 may
 not
 be
 legal.
 So
 I,
you
 know,
 I
 don't
 want
 to
 get
sidetracked
 by
 whether
 the
 fraud
 is
legal
 or
 illegal,
 but
 I
 think
 we
 all
know
 it's
 crooked.
 And
 here's
 how
 it
works.
 First
 of
 all,
</details>

>> 是的，解释一下什么是，我来解释给你听。我来给你解释。如果我说错了一个事实，那就指出来告诉我。

<details><summary>Original English</summary>
>> yeah,
 explain
 what's
 I'll
 explain
 it
 to
you.
 I'll
 explain
 it
 to
 you.
 And
 if
 I
 if
I
 misstate
 a
 fact,
 then
 let
 me
 know.
</details>

>> 那么，首先，加利福尼亚州向每一位登记选民寄送选票。大约有 2300 万、2400 万人。只有 950 万人投票。那么，剩下的 1400 万张选票发生了什么？我有一位住在洛杉矶的朋友。他管理公寓大楼。他说选票就那样堆积在，你知道的，大楼里每个人都有的邮箱旁。是的。到处都是散落的选票。它们被寄给了甚至根本不再住在那里的人。他认得那些名字，他们是多年未曾在那里住过的人。所以选民名册是肮脏的。它们已经多年没有被清理过了。好的。然后你又面临

<details><summary>Original English</summary>
>> So,
 first
 of
 all,
 California
 sends
 out
ballots
 to
 every
 registered
 voters.
 It's
something
 like
 23
 24
 million
 people.
Only
 9
 and
 a
 half
 million
 people
 vote.
So,
 what
 happens
 to
 the
 other
 14
 million
ballots?
 I
 have
 a
 friend
 who
 lives
 in
LA.
 He
 manages
 apartment
 buildings.
 He
says
 that
 the
 ballots
 just
 pile
 up,
 you
know,
 at
 the
 mailboxes.
 Yes.
 That
everybody
 has
 in
 the
 buildings.
 There's
like
 loose
 ballots
 everywhere.
 They're
sent
 to
 people
 who
 don't
 even
 live
 there
anymore.
 He
 like
 recognizes
 that
 the
names,
 they're
 people
 who
 haven't
 lived
there
 in
 years.
 So,
 the
 voter
 roles
 are
dirty.
 They
 haven't
 been
 cleaned
 up
 in
years.
 Okay.
 Then
 you
 have
</details>

<!-- chunk 11/13 -->

### 加利福尼亚州选举制度与欺诈争议

问题在于选举日没有选民身份验证（voter ID）。甚至去登记时都没有选民身份验证。当你签署选票时，他们把它放进机器里跑一遍。只要签名匹配度达到 40%——我甚至都不知道 40% 意味着什么，这等于连一半的准确率都不到——机器就判定通过。好吗？然后，如果你有所谓的见证人，它甚至都不去核对选民的签名。所以选民只要在签名处画个小叉叉（X），只要见证人认可并签署就行，但对见证人根本没有任何登记要求。任何人都可以成为见证人。见证人根本没有数据库。所以见证人只要随手画一道波浪线就行。那么，有什么能阻止所谓的选票收割者去填好这些选票，在选民处画个小叉叉，在见证人处随手画个小波浪线，然后把这些选票倒进去呢？这中间根本没有监管链（chain of custody）。

<details><summary>Original English</summary>
 the issue that there's no voter ID on election day. There's no voter ID to even get registered. When you sign your ballot, they run it through a machine. As long as the signature matches 40%, I don't even know what 40% means. It's like less than half accurate, the machine says it's fine. Okay? And then it doesn't even check the signature of the voter if you have a supposed witness. So the voter can just put like a little X on their signature as long as the witness says and they sign, but there's no registration of witnesses. Anybody can be a witness. There's no database of witnesses. And so the witness just puts a squiggle. So what is to stop the so-called ballot harvester from going filling out these ballots, putting a little X on the voter, putting a little squiggle on on the the witness, and then dumping these ballots. There's no chain of custody.
</details>

所以风险就是他们会被逮捕，然后——

<details><summary>Original English</summary>
So the risk would be they would be arrested and
</details>

>> 对，

<details><summary>Original English</summary>
>> and right
</details>

>> 好吧，他们被抓到的预期有多大？加文·纽森（Gavin Newsom）刚刚签署了一项法律，使得对这些事情进行任何审计几乎都变得不可能了。

<details><summary>Original English</summary>
>> well what is their expectation getting caught? Gavin Newsome just signed a law making it virtually impossible to audit any of this stuff.
</details>

>> 所以现在，即便他们可能觉得自己会被抓住。我们不妨来看看目前加州正在发生的、我们所知的所有其他类型的欺诈。我们知道，加利福尼亚州在医疗补助欺诈、失业金欺诈、EBT 欺诈、临终关怀欺诈、与无家可归工业复合体相关的欺诈等等事情上，存在数十亿美元的欺诈行为。这些全都被证实了。好吧。难道真的很难相信，某些相同的团体、相同的利益集团、相同的非政府组织（NGOs），会愿意去利用肮脏选民名册中的这些漏洞——数以百万计寄往错误或不存在地址的选票、不存在的监管链、不存在的签名验证、不仅投票不需要身份证明而且登记也不需要身份证明、若在 7 天后收到则计算没有邮戳的选票、从甚至没有任何床位的流浪者庇护所登记成千上万张选票。这些全都是已知的事实。所以当你声称没有欺诈时，就像是——得了吧，漏洞是存在的，你只需要看看结果，就能看出这里面有猫腻。

<details><summary>Original English</summary>
>> So now even if they thought maybe they could get caught. Let's just take a look at all the other types of fraud happening in California right now that we know about. We know that there's billions of dollars in fraud in California for things like Medicaid fraud, unemployment fraud, EBT fraud, hospice fraud, fraud related to the homeless industrial complex, and on and on. That's all been proven. Okay. Is it really so hard to believe that some of the same groups, the same interest groups, the same NOS's would be willing to exploit these loopholes in the dirty voter roles in the millions of ballots that go to incorrect or non-existent addresses, the non-existent chain of custody, the non-existent signature verification, the no ID, not only to vote but to register, counting ballots without postmarks if received 7 days later, registering thousands of ballots from homeless shelters that don't even have any beds. These are all known things. So when you say that there's no fraud, it's like come on, there's loopholes and all you got to do is look at the results and see that there's something crooked going on here.
</details>

>> 好吧，所以你属于认为确实存在欺诈的阵营，因为哪里有——

<details><summary>Original English</summary>
>> Okay, so you're in the camp that there is fraud going on because where there's
</details>

>> 这可能是被合法化了。它可能是被合法化了，但它就是欺诈。

<details><summary>Original English</summary>
>> it may be legalized. It may be legalized, but it's fraud.
</details>

>> 行，所以你相信存在欺诈。听着，当你开始给根本不投票的人邮寄数以百万计的选票，然后你没有任何审计要求、没有监管链、没有惩罚、没有处罚、没有调查，而且有大量的调查由司法部长——

<details><summary>Original English</summary>
>> Okay, so you believe there's fraud. Look, when you start mailing out millions of ballots to people who don't even vote, and then you have no audit requirements, no chain of custody, no punishments, no penalties, no investigations, and there's a huge tons of investigations both by attorney generals
</details>

>> 在加州。

<details><summary>Original English</summary>
>> in California.
</details>

>> 由谁发起？

<details><summary>Original English</summary>
>> By who?
</details>

>> 呃，我，我去调一下历史记录。我想说的是，每次选举之后，都会有大量的民事诉讼被提起。就像特朗普显然提起了 60 起，其中 60 起，当时——

<details><summary>Original English</summary>
>> Uh I I'll pull up the history. I will say after every election, there are tons of civil lawsuits filed. Like obviously Trump filed 60 of 60 when
</details>

>> 在加州可没有。呃，我不知道，刚刚让进行这种审计变得不可能了。他刚刚，我认为那是因为他在一个民主党州输得太惨了。没有任何理由这么做。但我不知道他为什么没有在加州提起诉讼。但他提起了 60 起此类诉讼，而且每个人差不多都会这么做。他们不断地提起这些诉讼，司法部长们也可以。所以在这个案例中，查马斯（Chamath），如果有这么多的疑点（smoke），如果这个统计数据看起来如此不可思议，而且还有尼克·雪莉（Nick Shirley）去贫民窟（Skid Row）的视频，以及他们付钱给瘾君子和嗨大的人让他们去投票的这种可能性，这原本应该是很容易抓到的。实际上，这需要一个阴谋才能左右成千上万张选票。而这正是我们在这里谈论的。我们说的是被左右的选票多达 10,000 张以上，但肯定有 5,000 张。祝你好运。你需要一个数百人、或者至少几十人的阴谋才能做到这一点。

<details><summary>Original English</summary>
>> not in California. Uh I don't know just made it impossible to do that kind of audit. He just I think that's because he was beaten so badly in a democratic state. There was no reason to. But I don't know why he didn't file in California. But he filed 60 of these and everybody kind of does that. They file these constantly and attorney generals can. So in this case, Chimoth, if there's so much smoke, if this statistic seems so improbable, and there was the Nick Shirley video of going to Skidro and this possibility that they were paying junkies and people who were high to vote, this would be easily catchable. Actually, this would take a conspiracy for thousands and thousands of votes to have been swung. And that's what we're saying here. We're saying upwards of 10,000 votes were swung, but certainly 5,000. Good luck. You would need a conspiracy of hundreds of people or at least dozens to do that.
</details>

>> 祝你能到贫民窟去，让某个吸食甲基苯丙胺的瘾君子公开记录作证。

<details><summary>Original English</summary>
>> Good luck going to Skid Row and getting some meth addict to go on the record.
</details>

>> 我想他们其实确实让某个人公开记录作证了。那就是，那是——

<details><summary>Original English</summary>
>> I think they actually got somebody to go on the record actually. That's a that's the
</details>

>> 关于这个有几个视频。是的。

<details><summary>Original English</summary>
>> There's a few videos of this. Yes.
</details>

>> 是的。是的。不，这当中疯狂的部分在于，他们呃，是说贫民窟的人得到了两三美元的报酬，而且有人因此被判定有罪。布伦达·李·布朗·阿姆斯特朗（Brenda Lee Brown Armstrong）。她在 2026 年就付钱的行为认罪了。该系统就是被设计用来允许欺诈的。它这个，它被设计——

<details><summary>Original English</summary>
>> Yeah. Yeah. No, that that's the crazy part about it is they uh are saying Skidro people got paid two or three dollars and that somebody was found guilty of this. Brenda Lee Brown Armstrong. She plead guilty in 2026 of paying. system is designed to allow fraud. It's this it's designed
</details>

>> 它是以 43,000 票获胜的，相比于——

<details><summary>Original English</summary>
>> it has been won by 43,000 votes to
</details>

### 加州政治机器与制度困境

>> 伙计们。我们在加利福尼亚生活在一个专制体制中，那里的一个政治机器如此不可逆转地塑造了法律，以至于无论是市长、州众议员、州参议员还是州长，这都是一扇单向门。只有一个党派能赢，而我们正逐渐看到，那个党派越来越没有能力管理一个如此充满活力且如此复杂的州。他们修改了规则，以确保这种垄断得以强制执行。我们所有人都在默许这一切，要么通过支持、要么通过投票、要么通过保持沉默。而最终的结果尚未完全揭晓，因为还需要几十年时间，所有这些腐败才会真正彻底摧毁这些地方。现实是，选民也许应该获得一个机会，让斯宾塞·普拉特（Spencer Pratt）去对体制机器进行反击，这样至少他们能认识到，这个机器的运转甚至完全没有接近其原本设想的方式。相反，将会发生的是，两个在各种形式上都相当不合格且极其相似的人，如今在实质上给不了你什么真正的选择。所以，我认为令人难过的事情在于弗里伯格（Freeberg）是对的，萨克斯（Sacks）也是对的。弗里伯格是对的：法律已经被塑造成这种方式，使得原本属于违法的行为变得合法。而萨克斯也是对的：任何理智的人审视这些法律，都应该会说这是欺诈性的。不幸的局面是，除非在加州出现某种灾难性的决定，否则我们就会被困在其中。是时候把所有这些人统统选下台了。

<details><summary>Original English</summary>
>> guys. We live in a autocracy in California where one political machine has shaped the laws so inexurably that whether it's a mayor or it's a state legislator or it's a state senator or it's the governor, it's a one-way door. There is only one party that can win and we are slowly seeing that that party increasingly does not have the ability to govern a state this dynamic and this complicated. They've changed the rules to make sure that that monopoly is enforced. We have all tacidly approved it by supporting or voting or not saying anything. And the end result has yet to be unveiled because it's going to take another couple of decades for all of this rot to really destroy these places. The reality is the voters probably should be given a chance to have Spencer Pratt push back on what is the machine so that at a minimum what they learn is that the machine wasn't working nearly anywhere close to the way it is intended. Instead, what will happen is two people that are in various shapes and forms pretty deeply unqualified and very similar now essentially get to give you not much of a choice at all. So, I think the the the sad thing is Freeberg is right and Sax is right. Freeberg is right. The laws have been shaped this way to make legal what would otherwise be an illegality. and Sax is right, which is that any rational person should look at these laws and say this is fraudulent. The unfortunate situation is unless there's a some cataclysmic decision in California, this is what we're stuck with. It is time to vote all of these people out.
</details>

>> 你没办法，你没办法通过投票。你这是什么意思？你打算怎么做？任何人都可以登记，任何人都可以投票。斯宾塞·普拉特能做到这个。我能回答弗里伯格（Freeberg）的问题吗？

<details><summary>Original English</summary>
>> You can't you can't vote. What do you mean? How you going to do it? Anyone can register anyone can vote. Spencer Pratt can do this. Can I answer Free Brook's question?
</details>

>> 当然。

<details><summary>Original English</summary>
>> Sure.
</details>

>> 有一个破釜沉舟（break the glass）的办法，关于这一点是什么，我和其中的几个人聊过。你如何改变这个系统？你必须让处于选票最顶端（top of the ticket）的人当选。那个人就是史蒂夫·希尔顿（Steve Hilton）。如果那成了真，史蒂夫·希尔顿可以做一件事来开始彻底改变这个州的运转方式，那就是在第一天立刻宣布进入紧急状态。顺着这条线索走下去，你会发现，在紧急状态下，你可以做很多事情来清理加利福尼亚的运转方式。我就点到为止。

<details><summary>Original English</summary>
>> There is one break the glass way and I've talked to a few of these guys about what that is. How do you change the system? You must get somebody at the absolute top of the ticket elected. That person is Steve Hilton. And if that happens, there is one thing that Steve Hilton can do to start to completely change the way that this state is run, which is instantly on day one declare a state of emergency. If you pull on this thread, what you will find, there are lots of things you can do to clean up how California works under a state of emergency. I'll leave it at that.
</details>

### 选民身份验证与历史案例争议

是的，这里面有一些常识。我们不应该把选票寄送给所有人。这在疫情期间或许说得通；而且如果你连花点心思持有身份证明都做不到，那也许你就不应该投票，呃，而且我不认为曾经有一场选举，一场重大选举，曾被选举欺诈所左右。据我所知，传统基金会（Heritage Foundation）在这上面投入了数以千万计的美元，他们有一个非常出色的项目专门追踪这个。人们提起诉讼，就像特朗普做的那样，就像阿尔·戈尔（Al Gore）做的那样，大家总是在为这事提起诉讼。这从来都不足以左右一场选举，但边缘细节上绝对存在。

<details><summary>Original English</summary>
Yeah, it there's some common sense here. We shouldn't send ballots out to everybody. that made sense maybe during co and if you can't be bothered to have ID then maybe you shouldn't vote uh and I don't think that there has been an election a major election that has been swung by election fraud the Heritage Foundation has spent many many tens of millions of dollars on this I understand and they have a really great uh project that tracks this people file lawsuits like Trump did like Al Gore did everybody's always filing lawsuits over this it's ever enough to swing an election, but there's definitely on the margins.
</details>

>> 肯尼迪对阵尼克松。兄弟，

<details><summary>Original English</summary>
>> Kennedy versus Nixon. Bro,
</details>

>> 等等，让我说完。

<details><summary>Original English</summary>
>> hold on. Let me finish.
</details>

>> 黑手党让肯尼迪在对阵尼克松时当选了。

<details><summary>Original English</summary>
>> The mob got Kennedy elected versus Nixon.
</details>

>> 我说的是现代历史上。是的，在现代历史上。

<details><summary>Original English</summary>
>> I'm talking in modern history. Yeah, in modern history.
</details>

>> 那非常有名。那非常有名。

<details><summary>Original English</summary>
>> That's pretty famous. That's pretty famous.
</details>

>> 好吧，关于那是不是真的，我们也可以去探讨。

<details><summary>Original English</summary>
>> Okay, we we can get into if that's true or not as well. The
</details>

>> 去查查林登·约翰逊（Lyndon Johnson）的历史吧。林登·约翰逊能当选参议员，他在政坛起步就是通过选票欺诈。

<details><summary>Original English</summary>
>> Check out Lynon Johnson's history. Lyndon Johnson only got elected to the Senate. He got a start in politics through ballot fraud.
</details>

>> 我们绝对应该实行选民身份验证。我们应该停止向每个人寄送选票，因为表现出的不当嫌疑正是问题所在。双方，爆炸性新闻，爆炸性新闻，各位：双方都在作弊。双方都在钻空子。一方是通过限制获取途径来做，另一方则是通过提供过多获取途径来做。所有这些政客，他们中的绝大多数都是不道德的。他们唯一关心的就是当选。两党都有成群的人在为他们卖命，去润色这些选举结果。而如果你被抓住了，后果是严重的。在现代历史上，还没有重大选举——尽管去查传统基金会吧，他们找出了所有的犄角旮旯和——

<details><summary>Original English</summary>
>> We absolutely should have voter ID. We should stop sending everybody one of these because the appearance of impropriety is the problem here. Both sides crazy new flash news flash everybody. Both sides cheat. Both sides bend the rules. One side does it by limiting access. The other does it by providing too much access. All these politicians, overwhelming majority of them are unethical. And all they care about is getting elected. And they have tons of people working for them in both parties to massage these election results. And if you get caught, it is a serious penalty. There has not been in modern history major elections. Go ahead and go to the Heritage Foundation. They find all the nooks and
</details>

<!-- chunk 12/13 -->

……缝隙中。

<details><summary>Original English</summary>
crannies of
</details>

>> 你一直在用“欺诈”这个词，就好像它真是一回事似的，但其实根本不是。我告诉你谁才是在欺诈。

<details><summary>Original English</summary>
>> You keep using the word fraud like as if it's a thing, but it's not. I'll tell you who's at fraud.
</details>

>> 不，确实存在欺诈。归根结底，欺诈是存在的。已经有人因为搞欺诈行为被抓了。

<details><summary>Original English</summary>
>> No, there's fraud. At the end of the day, there is fraud. There are people have been caught doing fraudulent things.
</details>

### 选举制度与选民身份立法讨论

>> 从根本上说，最该怪的一个群体就是国会。我们本来有机会的。过去一直有机会通过法律，规定非公民投票、未正确注册者投票以及未出示身份证件投票均为非法。对于这个民主选举程序来说，这是一个非常简单的解决办法。我们不能允许这样一种情况存在：某人依法可以去把公寓大堂里闲置的100张选票收集起来，或者人们凭一张健身房会员卡就能登记投票；而从根本上讲，联邦政府早就掌握了你是否在缴税，你开车必须要有驾照，你必须持有身份证件，在这个国家你做几乎任何事、所有事都得在系统里登记。所以，从我们作为这个国家公民所承担的最基础的义务中把这一极其简单的要求排除在外，本质上就是错误的，国会必须解决这个问题。

如果国会把它解决了，并且有联邦法律建立起相应制度，确保选举完全是“一人一票”且投票者依法具备投票资格，那么这就根本不会成为一个问题。如果不做到这一点，我真担心事态会往何处发展，因为久而久之，真正相信选举是真实的人会越来越少。我讨厌在这里表现得像个选举恐慌贩子，到处跟人说选举不是真的；但这种情况持续得越久，人们就越难真正对我们所有人身处其中的这个体系抱有信任。到那时局面就会变得不堪设想，所以必须把这事解决掉。

<details><summary>Original English</summary>
>> The one group that is fundamentally to blame is Congress. We have an opportunity. There have been opportunities to pass laws that will make it illegal for people to vote if they are not citizens, if they are not properly registered, and if they don't show up with ID. That is a very simple solve to this democratic electoral process. We can't have a situation where someone is legally allowed to go out and collect a 100 ballots that they find sitting in the lobby of an apartment building or for people to register to vote with a gym membership card when fundamentally the federal government already knows if you're not paying your taxes, you're required to have a driver's license to drive a car, you have to have ID, you have to be registered in the system to do nearly anything and everything in this country as it is. So to exclude that very simple requirement from the most foundational obligation that we all have as citizens of this country is inherently wrong and it needs to be addressed by Congress.

And if Congress fixes it and there are federal laws that create systems that ensure that elections are all about one person getting one vote and they're legally allowed to vote, then this doesn't become an issue. Short of this, I worry where this goes because over time, the fewer people actually believe that elections are real. And I hate being on here sounding like I'm an election fear-mongering guy who's telling people that elections aren't real, but the longer this goes on, the more difficult it will be for people to actually have faith in the system that we're all operating within. And that's when things get ugly and it needs to be fixed.
</details>

>> 是的，我非常赞同。如果你连办个驾照或护照都懒得去办，也许你就不需要投票。是的。

<details><summary>Original English</summary>
>> Yeah, I'm strongly agreeing. If you can't be bothered to get a driver's license or a passport, maybe you don't need to vote. Yeah.
</details>

>> 国会可以解决这事。而且他们应该去解决。

<details><summary>Original English</summary>
>> Congress can fix it. And they should.
</details>

>> 对。顺便说一句，加州有一项选票提案。如果加州人想要这个，他们直接投那项选票提案就行了。

<details><summary>Original English</summary>
>> Yeah. And and there's, by the way, there's a ballot measure in California. If people in California want this, they can just vote for the ballot measure.
</details>

>> 你指的是选民身份证明（voter ID）选票提案？

<details><summary>Original English</summary>
>> You mean the voter ID ballot measure?
</details>

>> 对。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 没错。那非常重要。事实上，你看，如果那个失败了，这算得上是我们拯救任何局面的最后机会了——

<details><summary>Original English</summary>
>> Yeah. That's very important. Actually, look, if that fails, it's kind of our last chance to save anything
</details>

>> ——加州的最后机会。是的。是的。而且你听起来确实像……大卫，你整段发言听起来就像个选举否定者。

<details><summary>Original English</summary>
>> for California's last chance. Yeah. Yeah. And you do sound like an your entire speech, David, was you sound like an election denier.
</details>

>> 我不管你怎么贴标签。听着，整个民主党在2016年特朗普获胜这件事上全都是选举否定者。他们炮制了整个通俄门骗局，基本上就是想以此来抹黑贬损他的当选。

<details><summary>Original English</summary>
>> I don't care what you label it. Look, the the Democratic party as a whole were election deniers about Trump winning in 2016. They concocted the whole Russia gate hoax to basically try and discredit his election.
</details>

>> 当你看到现场投票和邮寄选票之间的差异时——我也看到每个人都在试图解释为什么会有这么大差别——这对我来说在逻辑上根本说不通。就是这样。我并不是想要捏造什么事实。这就是事实。看看你现在屏幕上看到的这些事实吧。这就是数据上的差异。这组数据告诉我，肯定有问题。就是这样。

<details><summary>Original English</summary>
>> When you look at the the difference between walk-in and mailin ballots, and I've seen everyone try to argue why that's so different, it doesn't compute for me. That's it. I'm not like trying to make up a fact. This is the fact. Look at this facts on the on the on the screen you're looking at right now. This is the difference in the data. This data tells me that something is wrong. That's it.
</details>

>> 显然，

<details><summary>Original English</summary>
>> Obviously,
</details>

>> 我并不是想要……我并不是仅仅因为不喜欢谁当选了就在这里贩卖恐慌。我才他妈不在乎洛杉矶发生什么事。事实上，我认为洛杉矶跟社会主义市长打几年交道反倒更好，这样他们经历一番走出来后就会意识到，他们不应该拥抱社会主义原则。我觉得这对整个国家来说是件好事。实际上，我认为这对纽约也是好事。我认为对西雅图也是好事。我觉得对明尼苏达什么地方的都挺好。在这个国家，不管哪个地方的人想要选出社会主义者，那就让他们一头撞上去吧。我完全支持跳进社会主义的深井里，这样我们就能像拉美国家现在正在做的那样，从另一头跳出来，到时候所有人都会醒悟过来，意识到社会主义有多操蛋，因为它剥夺了每个人向上流动的经济机会。它剥夺了每个人作为这个国家立国之本的个人自由。社会主义是错的。它是坏掉的。它行不通。如果你们大家都想去经受那样的教训，那就去吧。放手去做吧。那就这么办。让他们当选吧。

但是那项选举数据中的数字向我表明，那并不是人民想要的。在我看来，人们投票支持的根本不是那个，这一点完全不明确也不明显。而这正是我感到天哪、这个制度本身已经沦为了任命制而非选举制的地方。我个人对此感到非常气愤。关于这点，在我们结束这个话题之前，你们还有什么要补充的吗？

<details><summary>Original English</summary>
>> I'm not trying to I'm not trying to just fearonger because I don't like who got elected. I don't give a [ __ ] what goes on in LA. In fact, I think it's better for LA if they deal with the socialist mayor for a couple years so they come out the other side realizing they shouldn't embrace socialist principles. I think it's great for the country. Actually, I think it's great for New York. I think it's great for Seattle. I think it's great for wherever Minnesota. Wherever people want to elect socialists in this country, let's run into it. I'm all about jumping through the socialist well so we jump out the other side like the Latin American countries are doing now when everyone wakes up and realize how up socialism is because it denies everyone the opportunity for economic mobility. It denies everyone their individual liberties that this country was founded on. Socialism is wrong. It's broken. It doesn't work. And if you all want to go through that lesson, do it. Go for it. Let's do it. Let them get elected. But the numbers on that election data show me that that's not what the people wanted. That it's not very clear or evident to me that that's what people voted for. And that's where I'm like, my god, the system itself has become a system of appointment, not a system of election. And I get fired up about that personally. You want to add anything as we wrap here on this?
</details>

>> 是的。“党叫你拒绝相信你亲眼所见和亲耳所闻的证据。这是他们最终的、最根本的戒律。”这是显而易见的。只要看看图表就行了。看看那些数据。我们知道发生了见不得人的事。这在统计学上是不可能的。我们唯一不知道的，就是这是非法的欺诈，还是合法的欺诈。意思是说，他们制造了太多的漏洞，在法律中植入了太多的腐败，以至于他们的所作所为在法律层面可能是合法的。但这依然是腐败的。这依然是见不得人的。这太荒唐了。所有人都能看出来。不要否认你眼睛和耳朵看到的证据。哪怕他们把你称作选举否定者，我个人根本不在乎。我就否定它。斯宾塞·普拉特（Spencer Pratt）本应进入决选。我拒绝承认拉曼（Ramen）是合法获胜的。

<details><summary>Original English</summary>
>> Yeah. The party told you to reject the evidence of your eyes and ears. It was their final most essential command. This is obvious. Just look at the charts. Look at the data. We know something crooked happened. It's statistically impossible. The only thing we don't know is whether it was illegal fraud or legal fraud. Meaning they've created so many loopholes and so much corruption in the law that what they did is possibly legal. It is still corrupt. It is still crooked. It is ridiculous. Everyone can see it. Do not deny the evidence of your eyes and ears. Even if they call you an election denier, I personally don't care. I deny it. Spencer Pratt should be in the runoff. I deny that Ramen won legitimately.
</details>

>> 统计数据就是统计数据，它们在大声呼喊着：你应该让加州总检察长和联邦总检察长去调查这件事；如果他们抓到有人干这事——他们已经抓到一个人了，而且尼克·雪莉（Nick Shirley）去过那里，你也看到了贫民窟（Skid Row）里的那些人——要知道，听着，理论上无家可归者应该有投票权。

<details><summary>Original English</summary>
>> The statistics are the statistics and they would scream that you should have the attorney general of California and the federal attorney general look into it and if they catch people doing this stuff and they have caught one person and Nick Shirley went down there and you see people on Skid Row, you know, listen, homeless people should have the right to vote theoretically.
</details>

>> 纽森为什么刚刚签署了一项让这种审计变得更加困难的法律？

<details><summary>Original English</summary>
>> Why did Nome just sign a law making audits like that even harder?
</details>

>> 是的，我在这里并不是在为纽森辩护。我是说，总检察长都在哪呢？如果真的存在欺诈，特朗普完全有能力凭借他亲手挑选的总检察长去追查这件事。他控制着那一部分……嗯……你知道，我们的民主体制。他应该立案，他们应该去查清楚在统计学上到底发生了什么。所以，特朗普，特朗普总统，谢谢您，特朗普总统。快去做吧。快去做吧。你让这个总检察长去追查其他所有人。去查这场选举吧。动用你的权力。审计它并把他们揪出来。特朗普总统人呢？

<details><summary>Original English</summary>
>> Yeah, I'm not defending Newsome here. I'm saying where's the attorney general? If there is in fact fraud, Trump has the ability with his hands-elected attorney generals to go after this. He controls that part of uh you know our our democracy. He should file and they should go figure out what happened statistically. So Trump, President Trump, thank you, President Trump. Go do it. Go do it. You got this attorney general chasing down everybody else. Go to this election. Use your powers. Audit it and find them. Where's President Trump?
</details>

>> 你没听明白我的观点，州法律刚刚让联邦政府介入并审计选民名册变得更加困难了。所以——

<details><summary>Original English</summary>
>> You didn't hear my point that the the state law just made it harder for the federal government to come in and audit the voter roles. So
</details>

>> ——是的，他仍然可以做到。

<details><summary>Original English</summary>
>> yeah, he can still do it.
</details>

>> 我相信他们会去做的。我相信只要能做到，他们就会去做。

<details><summary>Original English</summary>
>> I'm sure they will do it. I'm sure they'll do it if they can.
</details>

>> 是的。我是说，相信我，特朗普想干嘛就干嘛。如果说我们学到了什么的话，那就是——

<details><summary>Original English</summary>
>> Yeah. I mean, trust me, Trump does what he wants. If we've learned anything,
</details>

>> ——他会想干嘛就干嘛。但他现在并没有做这件事。

<details><summary>Original English</summary>
>> he will do what he wants. And he's not doing this now.
</details>

>> 让我感到不可思议的是，媒体不仅没有去问一些尖锐的问题，比如“这怎么发生的？在那些直到……等等……在选举日之后才被发现的选票中，票数怎么会产生如此剧烈的反转？”媒体不但没有试图去追寻答案和要求问责，反而在试图掩盖，并且声称这里什么问题都没有发生。这太令人难以置信了。这太无法无天了。

<details><summary>Original English</summary>
>> What I find amazing is that the media instead of asking tough questions like how did this happen? How could the votes swing so wildly in ballots that were only found after hold on after election day? The media instead of trying to demand answers and demand accountability is trying to cover up and say nothing wrong happened here. It's unbelievable. It's outrageous.
</details>

>> 最好的理论正面阐述（steelman）是什么？关于为什么会出现这种差异，最好的理论解释是什么？

<details><summary>Original English</summary>
>> What is the best theory steelman? What's the best theory of why this discrepancy?
</details>

>> 我是说，我们正坐在这儿讨论它呢。

<details><summary>Original English</summary>
>> I mean, we're sitting here talking about it.
</details>

>> 这种差异到底是怎么回事？有没有人能对这种差异为什么可能发生给出一个合情合理的正面强力解释？有谁能吗？

<details><summary>Original English</summary>
>> What's the discrepancy? Anybody have a steel man of why this discrepancy could have happened that's legitimate? anybody.
</details>

>> 如果媒体仍然死守着过去的某个瞬间——在那个时候人们还真正在乎他们说了什么——而每当他们实际上能够重建信任时，他们却往往不去重建，因为他们想要讨好的人乐意配合演下去。所以我觉得实际情况是媒体会觉得：好吧，我有两个选择。我可以实话实说，斯宾塞·普拉特本应该赢或者本可能赢，或者去调查他为什么没赢，但这样一来我差不多就成了在心照不宣地支持特朗普。等等，我本来是应该讨厌特朗普的啊。所以，不行。对，你知道的，这完全正常。这里没什么好看的。大家翻篇吧；他们指望着这样一来自己就能被接纳进这台体制机器里，但他们终究会像其他人一样被碾压和被利用。所以，

<details><summary>Original English</summary>
>> If the media is hanging on to a snapshot of the past where people actually cared what they said and every time that they can actually reestablish trust, they kind of don't do it because the people that they want to curry favor with are willing to play along. So I think what happens is the media is like, well, I have two choices. I can actually say that Spencer Pratt should have won or could have won or investigate why he didn't win, but then I'm kind of tacitly supporting Trump. And hold on a second. I'm supposed to hate Trump. So, no. Yeah, you know, this is completely normal. Nothing to see here. Everybody moves on, hoping that then they get ingratiated into the machine, but they're going to get run over and used like everybody else does, too. So,
</details>

>> 事情就是这样。对，查马斯，你的观点太切中要害了，现在的情况就极化到这种程度，也就是说存在两个极端，只要你提出质疑，就几乎像是你被归入了支持特朗普的阵营。就像“MAGA”这个词被到处乱扔一样，好像“噢，你是个MAGA分子，因为你在质疑……”

<details><summary>Original English</summary>
>> that's what's happening. Yeah, your point is so spot on, Chimat, that like if it's so polarized, meaning that there's two polls that if you do question, it's almost like you were being put in the Trump proTrump camp. Just like the word MAGA is thrown around like, oh, you're a MAGA guy because you're questioning
</details>

<!-- chunk 13/13 -->

选举公正性。这与 MAGA 毫无关系。这只是关于一个特定话题的简单讨论。但如果它与另一个阵营截然对立，你就会，你知道，你一定被归入那个糟糕的阵营。因此他们不想被归入那个阵营。太真实了。我支持数学和统计素养，而这里所发生的事情在数学和统计上。

<details><summary>Original English</summary>
election
integrity.

This
has
nothing
to
do
with
MAGA.
It's

just
simple
conversation
about
a

particular
topic.
But
if
it's
diametric

to
the
other
camp,
you're,
you
know,
you

must
be
in
that
bad
camp.
And
so
then

they
don't
want
to
be
put
in
that
camp.

It's
so
true.
I'm
for
mathematical
and

statistical
literacy
and
what
happened

here
is
mathematically
and

statistically.
</details>

>> 所以没有任何人能给出任何更强有力的反驳论点（steel man），或关于这怎么可能发生的构想。

<details><summary>Original English</summary>
>> So
nobody
has
any
steel
man
or
concept

of
how
this
could
have
happened.
</details>

>> 我可以告诉你发生这种情况的统计概率，那是万亿分之一。

<details><summary>Original English</summary>
>> I
can
tell
you
the
statistical
odds
that

this
would
have
happened
and
it's
one
in

a
trillion.
</details>

>> 好吧。如果

<details><summary>Original English</summary>
>> Okay.
What
if
</details>

>> 所以你是想告诉我，这万亿分之一的概率正好中了？

<details><summary>Original English</summary>
>> So
are
you
telling
me
the
one
in
a

trillion
shot
hit?
</details>

>> 我——我是在问是否有任何，我不是

<details><summary>Original English</summary>
>> I
I'm
asking
if
there
is
any
I'm
not
</details>

>> 偏偏就这一次。

<details><summary>Original English</summary>
>> just
just
this
one
time.
</details>

>> 我不是，我是在问是否有人能以任何方式为这建立一个更强的论据（steals this）。我是在问——我来告诉你我听到的选举公正性

<details><summary>Original English</summary>
>> I'm
not
I'm
asking
if
there's
anybody

who
steals
this
in
any
way.
I'm
asking

I'll
tell
you
what
I've
heard
integrity

of
</details>

>> 为什么死抱这种想法对你来说在心理上如此重要——

<details><summary>Original English</summary>
>> Why
is
it
so
psychologically
important

for
you
to
cling
to
the
idea
</details>

>> 并没有

<details><summary>Original English</summary>
>> it's
not
</details>

在他们明显做了所有事情之后，加州的选举完全没有腐败

<details><summary>Original English</summary>
elections
that
California
elections
are

completely
corruption
free
after
all
the

things
they've
clearly
done
</details>

>> 去腐蚀选举，选民身份证，你承认有，就像里面全是漏洞

<details><summary>Original English</summary>
>> to
corrupt
them
voter
ID
you
admit

there's
like
it's
chalk
full
of

loopholes
</details>

>> 你问我为什么抓着它不放，我并不是抓着它不放，为了讨论以及进行理智诚实的讨论，我是在问你们三位是否听过或者是否有任何理论，仅仅是为了讨论的严密性。这并不是我的立场。

<details><summary>Original English</summary>
>> you
ask
me
why
am
I
holding
on
to
it
I'm

not
holding
on
to
it
for
the
purpose
of

discussion
and
having
an
intellectually

honest
discussion
I'm
asking
the
three

of
you
if
there
you've
heard
or
if
you

have
any
theory
just
for
the

rigorousness
of
the
discussion.
This

isn't
my
position.
</details>

>> 媒体里所有的民主守护者现在都在哪儿呢？

<details><summary>Original English</summary>
>> Where
are
all
the
democracy
protectors

in
the
media
now?
</details>

>> 他们都说他们是，他们是守护者，他们是民主的守护者。他们要去保护民主。他们在哪儿提出质疑呢？

<details><summary>Original English</summary>
>> They
all
said
that
they
were
they
were

the
guardian
they
were
the
guardians
of

democracy.
They're
going
to
protect

democracy.
Where
are
they
to
ask

question?
</details>

>> 我能想到的唯一理论，我自己来替它做个强力论证（steal a minute myself）。我，因为我认为确实需要严谨。

<details><summary>Original English</summary>
>> The
only
theory
that
I
can
think
of
I'll

steal
a
minute
myself.
I
because
I
I

think
you
do
need
to
be
rigorous.
</details>

>> 你先讲。是的。我唯一能想到的就是她的地面动员（ground game）更为精细成熟，因为他们做这个的时间比 Spencer Pratt 更久，而由于他是一个非传统的首次参选人，他并没有包含这一点的地面动员。这是我唯一能想到的。

<details><summary>Original English</summary>
>> You
go
ahead
first.
Yeah.
The
the
only

thing
I
can
think
of
is
her
ground
game

is
more
sophisticated
because
they've

been
at
it
longer
than
Spencer
Pratt
and

he
didn't
have
a
ground
game
that
took

this
in
since
he's
a
non-traditional

firsttime
candidate.
That's
the
only

thing
I
can
think
of.
</details>

>> 精细成熟是用来代指他没有贿赂贫民窟（Skidro）无家可归者的暗语吗？

<details><summary>Original English</summary>
>> Sophisticated
a
coded
word
for
he
wasn't

bribing
Skidro
homeless
judge.
</details>

>> 不，他只是没有。他没有用于收集选票的选举机器，而收集选票是合法的。那就是，那就是问题所在。

<details><summary>Original English</summary>
>> No,
he
just
has
it.
He
doesn't
have
an

election
machine
to
collect
ballots
and

collecting
ballots
is
legal.
That's
the

That's
the
question.
</details>

>> 她的作弊操作做得更好。显然，

<details><summary>Original English</summary>
>> She
had
a
better
cheating
operation.

Obviously,
</details>

>> 我们说的是同一件事。我们实际上并没有说任何不同的话。

<details><summary>Original English</summary>
>> we're
saying
the
same
thing.
We're
not

actually
saying
anything
different.
</details>

>> Twitter 上的评论是人们在观望，因为有这么多人非常反对 Spencer Pratt，但他们想确保自己投票给正确的候选人，不管是 Ramen 还是 Bass。因此，那些把选票留到最后的人看到了民调数据，显示 Bass 胜券在握。这就是为什么他们都在最后一刻把票投给 Ramen，试图推她一把以确保

<details><summary>Original English</summary>
>> The
Twitter
commentary
was
that
people

were
waiting

because
there's
so
many
people
that
are

so
against
Spencer
Pratt,
but
they

wanted
to
be
sure
that
they
voted
for

the
right
candidate,
whether
it's
Ramen

or
Bass.
And
so
the
people
that
held

their
ballots
the
longest
saw
the

polling
data
that
Bass
was
going
to
win.

That's
why
they
all
voted
for
Ramen
last

minute
was
to
try
and
promote
her
to

make
sure
</details>

>> 已经改变了，因为你可以让两名民主党人排在选票前端。

<details><summary>Original English</summary>
>> has
been
shipped
because
of
the
you

could
have
two
Democrats
at
the
top
of

the
ticket.
</details>

>> 没错。他们不想让 Spencer Pratt 在普选中有任何机会。顺便提一下，你知道，我的意思是，如果你看过我对 Spencer Pratt 的采访，他说 Ramen 是在截止前一小时登记的，而且她是 Bass 的朋友，整个意图就是阻止他真正进入普选选票。所以人们心里在进行的部分协同就是，我们得确保投票给两名民主党人，然后他们就会想出办法，嘿，是不是不对？干脆把他排挤出局。

<details><summary>Original English</summary>
>> That's
right.
And
they
didn't
want

Spencer
Pratt
to
have
a
shot
at
the

general.
And
that
by
the
way,
you
know,

I
mean,
if
you
saw
my
interview
with

Spencer
Pratt,
he
said
Ramen
registered

one
hour
before
the
deadline
and
she's

friends
with
Bass
and
that
the
whole

point
was
to
keep
him
from
actually

making
it
onto
the
general
ballot.
So

that
some
of
the
coordination
that

people
were
making
in
their
minds
was
like,
we
got
to
make
sure
we
vote
for

the
two
Democrats
and
then
they'll

figure
out,
hey,
is
it
wrong?
Let's
just

box
him
out.
</details>

>> 是的。

<details><summary>Original English</summary>
>> Yeah.
</details>

>> 明白了。

<details><summary>Original English</summary>
>> Got
it.
</details>

>> 这就像是为什么他们都等到最后一刻才去投票——去投给——你怎么协同出那样的事情？这，这一直是我对这类事情有的疑问，像

<details><summary>Original English</summary>
>> Which
is
like
why
they
all
waited
till

the
last
minute
to
vote
for
to
vote
for

how
do
you
coordinate
something
like

that?
That
that's
always
the
question
I

have
with
these
like
</details>

>> 这些人全都是聪明的天才。这是数十万个聪明的天才排开来实现的。

<details><summary>Original English</summary>
>> these
people
are
all
brilliant
geniuses.

It's
it's
hundreds
of
thousands
of

brilliant
geniuses
row
that
out.
</details>

>> 是的，有一个聊天群。我的意思是，这没那么复杂。

<details><summary>Original English</summary>
>> Yeah,
there's
a
chat
group.
I

mean,
it's
not
that
complicated.
</details>

>> 选票收割者干的。Friedberg 所说的刚刚发生了。只不过是选票收割者干的，而不是真正的选民，显而易见。

<details><summary>Original English</summary>
>> Alan
Harvesters
did
it.
what
Freeberg

said
just
happened.
It's
just
that
the

ballot
harvesters
did
it,
not
the
actual

voters,
obviously.
</details>

>> 而且选票收割是合法的，但它很可疑，也许他们——如果有选票收割者的话，我认为特朗普和司法部能抓住这些人。

<details><summary>Original English</summary>
>> And
ballot
harvesting
is
legal,
but
it's

sketchy
and
maybe
they
And
if
there
are

ballot
harvesters,
I
think
that
Trump

and
the
DOJ
can
catch
these
people.
</details>

>> 怎么可能有人可以出去收集别人的选票，填好后再交上去，这居然是合法的？这对我来说简直太离谱了。

<details><summary>Original English</summary>
>> How
the
is
it
legal
that
someone
can
go

out
and
collect
other
people's
ballots

and
fill
them
out
and
send
them
in?
It's

the
craziest
to
me.
</details>

>> 目前没有舞弊的证据。统计数据看起来不妙。唐纳德·J·特朗普，你掌管司法部。去调查它吧。

<details><summary>Original English</summary>
>> No
evidence
of
fraud
right
now.

Statistics
don't
look
good.
Donald
J.

Trump,
you
control
the
Department
of

Justice.
Go
investigate
it.
</details>

### 结语

>> 好了。我爱你们，但我饿了。我得走了。这真是一期

<details><summary>Original English</summary>
>> Okay.
I
love
you
guys,
but
I'm
hungry.
I

got
to
go.
This
has
been
</details>

>> 精彩的 All-In 播客。再见。

<details><summary>Original English</summary>
>> an
amazing
episode
of
the
Allin
Podcast.

Bye-bye.
</details>

>> 爱你们，兄弟们。再见。

<details><summary>Original English</summary>
>> Love
you
boys.
Byebye.
</details>

>> 让你的赢家继续奔跑（Let your winners ride）。

<details><summary>Original English</summary>
>> Let
your
winners
ride.
</details>

>> 我们把它开源给了粉丝，他们简直为此疯狂了。死党们（Besties）走了。

<details><summary>Original English</summary>
>> We
open
sourced
it
to
the
fans
and

they've
just
gone
crazy
with
it.

Besties
are
gone.
</details>

>> 那是我的狗在你的车道上拉了一泡。

<details><summary>Original English</summary>
>> That
is
my
dog
taking
a
notice
in
your

driveway.
</details>

>> 哎呀，我的男装裁缝（habitasher）会跟我碰头。

<details><summary>Original English</summary>
>> Oh
man,
my
habitasher
will
meet
me
up.
</details>

>> 我们真应该直接开个房间，搞一场巨大的狂欢，因为他们都太没用了。这就像是我们只需要以某种方式释放出来的这种性张力。

<details><summary>Original English</summary>
>> We
should
all
just
get
a
room
and
just

have
one
big
huge
orgy
cuz
they're
all

just
useless.
It's
like
this
like
sexual

tension
that
we
just
need
to
release

somehow.
</details>

湿透你的

湿脚。

我们得让 Mercy 全力以赴（going all in）。

我全力以赴（going all in）。

<details><summary>Original English</summary>
Wet
your

wet
feet.

We
need
to
get
Mercy's
going
all
in.

I'm
going
all
in.
</details>