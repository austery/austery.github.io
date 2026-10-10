---
author: Latent Space
date: '2026-07-10'
guest: ''
layout: post.njk
source: https://www.youtube.com/watch?v=bIOCKXcxloQ
speaker: Latent Space
tags:
  - ai-engineering
  - agent-lab
  - frontier-model
  - compute-efficiency
  - ai-regulation
title: 对话 Swyx 与 Matthew Berman：AI 工程师的黄金时代、智能体实验室的崛起与模型路由的博弈
summary: 在本次深度访谈中，AI Engineer Summit 发起人 Swyx 与知名技术播主 Matthew Berman 探讨了 AI 工程师大会的起源、Claude 3.5 Sonnet 与 OpenAI 5% 股权赠予政府的传闻，并剖析了芯片推理、世界模型、智能体实验室（Agent Labs）以及模型路由与 All-in 战略的商业取舍。
insight: ''
draft: true
series: ''
category: tech-trends
area: tech-engineering
project: []
people: []
companies_orgs:
  - OpenAI
  - Anthropic
  - Cognition
  - Etched
products_models:
  - GPT-4o
  - Claude 3.5 Sonnet
media_books: []
status: evergreen
---
### AI 工程师大会的起源与演变

**Matthew Berman**: 我甚至都不知道该怎么开始这个话题。你只有30分钟时间对吧？

<details>
<summary>Original English</summary>

**Matthew Berman**: I don't even know how to start this. You have 30 minutes, right?

</details>

**Swyx**: 是的，没错。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. Yeah.

</details>

**Matthew Berman**: 这一次的 **AI Engineer Summit**（AI 工程师峰会）简直太不可思议了。这里的人非常多。我想从源头开始聊起。你最开始是怎么想到要创办一个专门面向 AI 工程师的工程大会的？这个想法是怎么诞生的？

<details>
<summary>Original English</summary>

**Matthew Berman**: This conference is incredible. There are so many people here. I want to start with the origin. How did you think to start an AI engineering conference? How did it come about?

</details>

**Swyx**: 好啊。在这之前我做了很多年的技术演讲者，我也曾见证过人们抓住那些标志着整个行业发生结构性转变的瞬间。在我看来，这种趋势在当时已经非常明晰了。我曾经亲眼目睹了**前端工程**（Front-end engineering）如何演变成一个高度专业化的独立领域，拥有了自己专属的技术会议、垂直领域的意见领袖、独立的技术栈以及一整套生态体系。随后，我又在**云原生工程**（Cloud engineering）和**数据工程**（Data engineering）的发展中看到了完全相同的演进轨迹。因此，我当时就想，这件事情毫无疑问也必然会发生在 AI 领域。于是，我当机立断买下了 **AI.engineer** 这个域名，开始筹划这场大会，并撰写了相关的博客文章。而当 **Andre Karpathy**（前特斯拉 AI 总监、OpenAI 联合创始人）也在社交媒体上公开转发并表示赞同和支持时，这个项目真正开始爆发了。我认为，随着时间的推移，AI 工程师作为一个独立职业角色的定位已经变得越来越真实和不可或缺，这也正是我最希望看到的行业演进方式。虽然 **Gartner** 在两年前就已经将这个概念置于其技术成熟度曲线（Hype Cycle）的炒作顶点，但时至今日，它的热度依然居高不下，而且整个生态仍在蓬勃发展。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. I've been a speaker for many years before that and I also had seen people seize a moment where you can see like an industry shift. And I thought it was pretty clear. I had seen basically front-end engineering become its own professionalized field with dedicated conferences, dedicated influencers and tech stacks and all those things and I seen the same thing for cloud engineering and data engineering and all that and I was like it's very obviously going to happen to AI. So I bought the domain AI.engineer and planned this conference and I wrote the blog post and it really kicked off when Andre Karpathy also endorsed it and I think it's gotten more true over time which is the kind of way I like to see it. Gartner put it at the peak of its hype cycle two years ago. It's still hypy, still going.

</details>

**Matthew Berman**: 在这之前你曾经创办或组织过大型的技术会议吗？还是说，你当时只是单纯地觉得“好吧，我觉得这个时机对了，我就直接动手去做了”？

<details>
<summary>Original English</summary>

**Matthew Berman**: Had you started a conference before? Had you ever done a conference before? You were just like okay I'm just going to do it?

</details>

**Swyx**: 我其实并不是一个人在孤军奋战。我与一位在这方面有着非常丰富的大会组织经验的朋友达成了合作。基本上，我从自己多年的会议演讲生涯中吸取了经验，把我去过的所有优秀会议中最好、最闪光的元素全部提取了出来。而我的合伙人 **Ben** 之前一直在运营 **Reactathon**，这是美西地区公认最棒的 React 开发者大会。因此，我邀请他来负责 AI 工程师大会的线下运营与物流保障，而我则全力以赴专注于内容侧的策划与把控。我们就是这样一路配合走过来的。

<details>
<summary>Original English</summary>

**Swyx**: Well I didn't do it alone. I partnered with a friend who had done previous conferences. So basically from my conference speaking career, I just took the best of every conference I had been to prior and Ben was running Reactathon which is the best React conference on the West coast. So I just had him start AIE and I would do the content, he would do the logistics and that's how it goes.

</details>

**Matthew Berman**: 那么，在举办第一届 AI 工程师大会以及现在这一届的过程中，你觉得最困难的挑战分别是什么？

<details>
<summary>Original English</summary>

**Matthew Berman**: What was the most difficult part during your first AIE and then this one?

</details>

**Swyx**: 是的，我觉得在办第一届大会时，最大的难点在于如何说服大家这个会议是值得他们花时间专门买票来参加的。因为作为任何事物的“第一次”，你没有任何历史记录可以向外界证明你的价值。而现在，我们已经积累了极佳的用户口碑，拥有了活跃的 **YouTube** 渠道，所有事情都步入了正轨。但在最开始的时候，你手里一无所有，人们完全是基于一种信任的跃迁——仅仅因为我个人的声誉和 Ben 办会的声誉走到了一起，觉得“好吧，这两个人聚在一起可能会鼓捣出一些有意思的东西”，他们才决定过来看一看。而且在第一届的时候，在技术层面其实并没有现在这么多花样。当时大多数人讨论的还只是提示词工程框架，顶多再加上一点点 **RAG**（检索增强生成）技术，但那时候根本没有任何**智能体**（Agents）的概念。在那个时候，一切技术形态都显得非常原始。除此之外，另一个巨大的难点在于如何邀请到行业内顶尖的 Frontier Labs（前沿大模型实验室）来参会。对我们来说，当时的突破口是邀请到了当时还在 OpenAI 负责开发者关系的 **Logan Kilpatrick**。而我认为，我们现在最大的核心价值定位之一，就是能够让所有这些顶尖的大模型实验室聚集在一个中立的平台上，让他们在相同的规则下同台竞技，这不仅对所有的软件工程师来说是最大化的利好，对于大模型实验室本身也是最具良性竞争意义的。事实证明，这些实验室也很喜欢这种方式。他们渴望在这样一个公平竞技的舞台上赢得开发者的心，而这种中立的生态环境，你在任何单一厂商的开发者大会（如 OpenAI DevDay）或者特定的产品推广活动中都是绝对无法体验到的。

<details>
<summary>Original English</summary>

**Swyx**: Yeah, I think the first one was just convincing people that this is even worth showing up to because like a first of anything like you don't have any history. Like people now people have word of mouth, they have the YouTube channel, it's all it's all good. The very first one you got nothing and the people just have to take a leap of faith of like well my reputation Ben's reputation come together do let's do something interesting I don't know right and it was also down not that much in terms of like the tech right like at mostly we were still talking about prompt frameworks and maybe a bit of RAG but there just weren't any agents like it it was very very primitive at the time. I think also the last thing was getting a big lab to come. And for us it was Logan at OpenAI at the time. And I think a big part of our value proposition now is that we can get all these labs to show up at a neutral place where they all compete on the same grounds, which is maximally beneficial for engineers and most competitive for the labs. And it turns out the labs like it. They like winning on a in on sort of like an even playing field. But you're just not going to get that in like a dev day or Code with Claude.

</details>

---

### 芯片之争：Etched、MatX 与显卡推理的未来

**Matthew Berman**: 你知道吗，我非常赞赏这里的一点在于，你这里展现了整个 AI 技术栈的复杂性。从极其贴近日常、务实的普通用户标准应用，到技术细节极深、非常硬核的底层探索，无所不包。

<details>
<summary>Original English</summary>

**Matthew Berman**: You know, you know what I really appreciate? There seems to be the entire stack of complexity here. Everything from kind of really practical everyday user kind of standard user and then all the way down to highly technical deep in the weeds.

</details>

**Swyx**: 我刚刚主持完一场长达一小时的底层芯片专题讨论会，对话的嘉宾是 **Etched** 团队，他们本周刚刚宣布结束隐身模式正式亮相。

<details>
<summary>Original English</summary>

**Swyx**: I just did a 1hour chip session with Etched which just came out of stealth this week.

</details>

**Matthew Berman**: 太棒了。是的，我刚才也注意到这个新闻了。关于 Etched，你有什么看法？他们未来真的有希望颠覆或解构 **Nvidia**（英伟达）在芯片领域的绝对统治地位吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: So good. Yeah. Yeah. I just saw that. What do you think about etched and are they going to disrupt Nvidia?

</details>

**Swyx**: 我并不认为他们的直接目标是颠覆英伟达。更合理的行业观察视角是：大模型**推理**（Inference）的市场体量在未来实在是太过于庞大了，以至于为推理任务设计专用的 **ASIC**（专用集成电路）芯片成为了一种必然趋势。英伟达未来显然会继续主导并制造通用 GPU 芯片，但推理专用芯片必定会切走一块巨大的蛋糕。

<details>
<summary>Original English</summary>

**Swyx**: I don't think they want to disrupt Nvidia. I think the better framing is that all of inference is just so goddamn big that of course you're going to have ASICs for inference. You're going to and Nvidia is going to continue to build GPUs.

</details>

**Matthew Berman**: 那在定位上，Etched 是更类似于 **Groq** 还是 **Cerebras**？

<details>
<summary>Original English</summary>

**Matthew Berman**: Is it is etched more akin to a Groq or a Cerebras?

</details>

**Swyx**: 是的，我一直在向身边的朋友们把他们框定为“下一代的 Cerebras”或“下一代的 Groq”。要知道，Cerebras 创立于十多年前，如今已经走到了准备 IPO 的阶段，他们的硬件形态和商业逻辑相对来说已经非常成熟和确立了。而 Etched、**MatX** 以及其他新一代芯片公司在做的事情，是更加彻底地针对 Transformer 架构以及后 GPT 时代所确立的算法工作负载进行极致的硬件级优化。这完全合乎逻辑，因为在十多年前 Cerebras 刚起步的时候，Transformer 架构甚至都还没有诞生，他们当时自然无法针对这一特定的计算模式进行预先的硬件优化。

<details>
<summary>Original English</summary>

**Swyx**: Yeah, I I have been pitching them as or or not pitching but framing them to friends as next generation Cerebras next generation Groq. Cerebras started 10 plus years ago. Now they're IPOed. That process in form factor is relatively well established. What Etched and Madrona (MatX) and the other new gen chips are doing are much more dedicated to basically everything that we know post transformers post RGBT (GPT) and optimizing for that workload. So it completely makes sense that the Cerebras of the world didn't optimize for it because it didn't exist back then.

</details>

**Matthew Berman**: 确实如此。但是，当你选择制造这种强绑定的定制化专用芯片时，你也必须承担极大的技术路线风险——如果未来大模型的底层架构发生颠覆性的技术变革，你设计的芯片可能在一夜之间就会被淘汰，不是吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah. So, you know, when you when you make custom chips, you run the risk that the model architecture changes drastically due to some kind of innovation, right?

</details>

**Swyx**: 他们其实对此完全不在乎。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. They don't care.

</details>

**Matthew Berman**: 他们完全不在乎？

<details>
<summary>Original English</summary>

**Matthew Berman**: They don't care.

</details>

**Swyx**: 是的。因为从 GPT-3.5 时代开始，主流模型的底层架构在过去这几年时间里基本上没有发生什么实质性的变化。这是一场赢面非常大的赌注。即便在未来的某个时间点，真的诞生了全新的、完全不同于 Transformer 的模型架构，目前各大企业和开发者基于现有模型（例如 **GPT-4o**）所建立的生产环境工作负载也依然会长期存在。因为在商业世界上，一旦一套复杂的生产系统能够稳定运转，企业是绝对不愿意轻易去触碰或重构它的。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. The GPT 3.5ish architecture has mostly stayed the same this entire time. It's a pretty good bet, man. Like even if there is a new model sometime in the future, the current workloads on existing models like 4o is still being used right by some folks cuz you just don't move. Like once the thing works, it works. Like don't touch it.

</details>

---

### 体验 Claude 3.5 Sonnet 与大模型算力限制

**Matthew Berman**: 好的，让我们换个新话题。你这周显然非常忙碌，不过 Anthropic 最近刚刚发布了全新的 **Claude 3.5 Sonnet**（在访谈中被称为 Fable 3.5）。你有机会亲自去测试或者把玩一下它吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: Well, all right. I want to talk about something new and you've been obviously quite busy this week, but Fable 5 (Claude 3.5) is now back. Have you had a chance to...

</details>

**Swyx**: 事实上，他们几乎可以说是专门为了我们的大会而在这个时间点发布它的。

<details>
<summary>Original English</summary>

**Swyx**: They released it for us.

</details>

**Matthew Berman**: 确实，他们挑的时机太巧妙了。那么，你已经尝试过它了吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: They did. They released it just for you. Have you even had a chance to...

</details>

**Swyx**: 是的，体验过了。甚至在我们的官网上，还有一个由 Fable（即 Claude 3.5 Sonnet 的 Artifacts 功能）完全生成的互动彩蛋，那是一个有趣的小游戏。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. Yeah. So, there's a there's an Easter egg on the website that is built by Fable. It's a game that lets you...

</details>

**Matthew Berman**: 是在 AI.engineer 的网站上吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: AIE engineer.

</details>

**Swyx**: 没错。

<details>
<summary>Original English</summary>

**Swyx**: Yeah.

</details>

**Matthew Berman**: 好的，你能给广大读者提供一些线索，提示一下大家应该怎么去寻找这个彩蛋吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: Okay. You want to give any hints as to what to look for for the Easter egg?

</details>

**Swyx**: 寻找一个地球仪图标，当你把鼠标悬停在上面时，它会开始上下跳动。

<details>
<summary>Original English</summary>

**Swyx**: Look for a globe icon that bounces when you hover over it.

</details>

**Matthew Berman**: 好的。那么你既然已经深入使用过了，你觉得目前的 Claude 3.5 Sonnet 体验，和它刚发布的那头几天相比是否一致？因为最近在社交平台 X 上，有很多声音都在抱怨和质疑，认为这款模型已经被 Anthropic 进行了暗中的“削弱”（Nerfed）。

<details>
<summary>Original English</summary>

**Matthew Berman**: All right. So, you have you've played around with it. Do does it feel the same as those couple of days when it was first released? Because a lot of people are talking about it being, you know, nerfed and there's a kind of a lot of floating around on X right now.

</details>

**Swyx**: 我理解。人们在面对 Anthropic 时总是非常乐于去抱怨。我手头没有硬性的基准测试数据，所以无法妄言它在发布后是否真的被削弱了。但我确实知道，当前模型的“误拒绝”（False refusals，即模型因过度安全对无害提示词拒绝回答）依然非常频繁地发生，当你在写代码时突然碰到这种情况，确实会让人非常恼火。还有就是，当服务负载过高时，它有时候会自动将请求降级路由到较旧的底层模型。不过，降级的情况目前在我的使用中还没有碰到过一次。

<details>
<summary>Original English</summary>

**Swyx**: I see. I see. Um, yeah, people are very quick to complain and about Anthropic. I don't know if it's nerfed since the first Fable launch. I don't have hard numbers on that. I know that false refusals happen and still happen a lot and those are really annoying when they happen. The downgrades to Opus (older models). I haven't had that happen to me once.

</details>

**Matthew Berman**: 好的。

<details>
<summary>Original English</summary>

**Matthew Berman**: Okay.

</details>

**Swyx**: 我的模型调用路由还从来没有发生过一次被自动降级的情况，这说明后台的算力供给还是比较充沛的。

<details>
<summary>Original English</summary>

**Swyx**: I haven't had a reroute happen to me once yet.

</details>

**Matthew Berman**: 那也可能是因为你测试的提示词还不够“辛辣”，没有触发它的降级安全阈值。

<details>
<summary>Original English</summary>

**Matthew Berman**: Maybe you're not spicy enough.

</details>

**Swyx**: 也许吧。但我绝对是一个 Token 消耗大户，如果这种降级在大规模调用中很普遍，我应该会遇到才对。

<details>
<summary>Original English</summary>

**Swyx**: Maybe I'm definitely ripping tokens though. So if it were going to happen, it would be there.

</details>

**Matthew Berman**: 也许你需要尝试在输入里夹杂一些关于化学武器之类的话题，这时候应该就能测出它的降级限制和安全逻辑了。

<details>
<summary>Original English</summary>

**Matthew Berman**: But maybe you need to talk about chemical weapons or something and then it'll go.

</details>

**Swyx**: 我的开发项目里显然不需要这方面的测试内容。

<details>
<summary>Original English</summary>

**Swyx**: Not a lot of my projects need that.

</details>

**Matthew Berman**: 确实如此。

<details>
<summary>Original English</summary>

**Matthew Berman**: Exactly.

</details>

**Swyx**: 我觉得当这款模型能够正常发挥作用的时候，它表现得极其聪明，极具智慧。但同时它也确实非常慢。我显然不会把它当成我所有日常开发任务的唯一选择，正是因为它的响应延迟太高了。你只会在遇到真正的复杂和高难度问题时才会调用它，这其实也是 Anthropic 官方最希望看到的用户行为。

<details>
<summary>Original English</summary>

**Swyx**: So no I think like look when it works it is extremely smart. But it's also very slow and I think definitely I don't see myself using it for everything because of that right like you only use it for the smart problems and that's probably the way they want it anyway.

</details>

**Matthew Berman**: 我觉得另一个被广泛讨论的焦点在于，大约在一个月前，行业里有一种声音，认为 Anthropic 在硬件芯片和计算资源上面临着极为严峻的瓶颈，这也是他们为什么推迟发布更高版本的核心原因。但从现在的实际情况来看，这个说法显然是站不住脚的。

<details>
<summary>Original English</summary>

**Matthew Berman**: I think I think maybe the other part about you know there was a narrative like a month ago where like people were like oh like Anthropic is limited on chips limited on compute capacity that's why they're not rolling out mythos (Opus) and fable (Sonnet). That's clearly not true.

</details>

**Swyx**: 嗯，至少从现在的发布来看确实不是这样了。

<details>
<summary>Original English</summary>

**Swyx**: Well now it's not true right I mean they...

</details>

**Matthew Berman**: 我认为即便在一个月前，那个关于缺算力的传言大概率也不是真实的。大模型开发路线图的变化不会在极短时间内发生剧烈逆转，他们其实一直对自己的研发进度有着明确的规划。

<details>
<summary>Original English</summary>

**Matthew Berman**: It probably wasn't true a month ago. It didn't change that much like they know their road map.

</details>

**Swyx**: 他们此前与 AWS 达成了极为紧密的深度战略合作，从而鎖定了庞大的芯片供给和计算带宽资源。这让他们在算力层面有了充足的底气。

<details>
<summary>Original English</summary>

**Swyx**: They just partnered with I think it was AWS and they landed a bunch of chip deals a bunch of compute bandwidth deals.

</details>

**Matthew Berman**: 但你难道不认为这些庞大的算力采购和合作计划，在他们正式向公众推介的前几个月、甚至更长时间就已经完全规划好了吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: But you you think they like weren't planning these for like months before like...

</details>

**Swyx**: 他们当然对这一切了如指掌。

<details>
<summary>Original English</summary>

**Swyx**: They knew this.

</details>

**Matthew Berman**: 我当时的意思是……

<details>
<summary>Original English</summary>

**Matthew Berman**: I was saying like...

</details>

**Swyx**: **xAI** 那时候高调宣布购入大量算力，也是当时行业里的一件大事。

<details>
<summary>Original English</summary>

**Swyx**: xAI that was the big one right.

</details>

**Matthew Berman**: 总之，我想说的是，算力中心的建设和模型部署绝不是一夜之间就能完成的事情。此前 Sonnet 版本的限量推迟，核心原因其实是出于安全对齐（Safety-related）的红队测试与风险评估，而不是因为外界所阴谋论的“算力紧缺不得不进行配给”。

不过，我依然认为他们在特定阶段确实面临着计算带宽的硬性限制。因为如果你当时去仔细观察他们的用户 API Quota 限制政策，以及他们频繁缩减单次对话 Token 额度的做法，这种迹象非常明显。虽然现在算力紧张的情况改善了很多，但在两个月前，你往往在短短几分钟内就会耗尽你所有的 API 使用限额。即便在如今的 3.5 Sonnet 上，这种现象依然在发生，因为它在输出更长思考链（COT）时需要消耗多得多的 Token 资源。

<details>
<summary>Original English</summary>

**Matthew Berman**: Anyway I'm just saying like these things don't happen just overnight and like they probably were already like the Sonnet rollout was genuinely safety related. That's why it was like limited. It wasn't because there's some secret conspiracy to like limit or ration compute.
I still do think they were bandwidth limited or they were compute limited because if you look at their quota and how aggressive in reducing it and using it. It's gotten much better but especially two months ago, I mean you would burn through your quota in a matter of minutes. Um it's happening again to be fair with Claude 3.5 because it just uses so many more tokens. two months ago. It just seems like they they could not get enough compute to serve the models that they have.

</details>

**Swyx**: 哈哈，好吧，这背后的真实情况恐怕只有他们自己内部的人才说得清了。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. Well, only only they know.

</details>

---

### OpenAI 5% 股权赠予美国政府的传闻与主权 AI

**Matthew Berman**: 好的，让我们来聊聊另一个前沿实验室。让我们来谈谈 OpenAI。我今天早上刚醒来，就看到了一条重磅的传闻。我虽然还没来得及对这个消息进行更深度的信息溯源和阅读，但传闻称 OpenAI 正在考虑向美国政府直接赠予其 5% 的股权。你对这件事情怎么看？这背后到底在酝酿着什么？

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah. All right, let's talk about the other frontier lab. Okay. Let's talk about OpenAI. I woke up I think it was this morning to the news, I guess rumored. I haven't I got to actually read more deeply into it, but OpenAI's offering 5% equity stake to the US government. Like what do you think is going on there?

</details>

**Swyx**: 我也看到了这个新闻标题。对于这个消息的具体信源以及真实度，我目前还无法做出判断。但我个人觉得，这完全是在情理之中的，并不是什么天方夜谭的疯狂点子。从事实层面来看，OpenAI 确实比其他任何 Frontier Labs 都展现出了对白宫和联邦政府更具建设性、更加友好的政治姿态。

<details>
<summary>Original English</summary>

**Swyx**: I saw that headline. Uh I don't know where I don't know anything about the sources or anything. I I think it kind of tracks like it's not within the outside range of possible things to do. I think OpenAI has been relatively more friendly with the White House than with other Frontier Labs. That's that's like factual to say.

</details>

**Matthew Berman**: 是的。而且从更宏观的社会契约角度来看，当一个国家孕育出了可能彻底改变人类社会图景的超级前沿智能时，这个国家的全体国民也理应通过政府持有某种形式的收益权或话语权。否则，未来的技术奇点将不可避免地导致社会阶级的急剧分化，催生出一个被技术垄断巨头彻底剥夺的永久性社会底层阶级，从而引发剧烈的社会动荡。

我自己此前也设想过一种名为“Universal Basic AI”（通用基本智能）的概念，即让每个公民都免费享有国家资助的 Chat Pro 订阅服务。但相比之下，让美国政府直接持有 OpenAI 5% 的股份，使国家利益与这家主导全球 AI 竞争的龙头实验室的成功深度绑定，这似乎在逻辑上更加自洽。

而且，我来自新加坡，在我们的国家，这种“国家资本注入战略性领头企业”的做法是非常正常且历史悠久的。新加坡的**淡马锡**（Temasek）和 **GIC**（新加坡政府投资公司）持有国家经济中大量关键企业的核心股份，整体运转得非常好。我们新加坡人的养老金、国民储蓄、商业保险资金，在很大程度上都投资在了政府控股的这些事关国计民生的支柱企业里。美国如果也这样做，又会有什么本质的不同呢？还是说，你认为美国政府在未来会更倾向于将 OpenAI 视作一种国家基础公用事业（Utility）来监管？

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah. Yeah. Yeah. Yeah. And um I also but I also just generally do think the people of the United States or the people of any country where um you know like all such like frontier in intelligence is created they do need to have a share or a say in some upside otherwise you have like a permanent underclass in significant social distress and I don't know you know I've played around with the idea of like universal basic AI like everyone gets like a chat pro subscription or something but like giving the government 5% to have the government in have a stake in the success of OpenAI as a leading lab in the US does tend to make sense. Uh I come from a country where this is normal. I'm from Singapore. Temasek and GIC own significant portions of the Singapore economy and it works just fine. And actually a lot of our pensions and our savings and our insurance and whatever is all invested in governments the like nationally critical important companies where the government owns the stake. What's so different? Do you think they're going to treat it more like a utility? Because there's like a few different flavors of how this plays out. The government owns 5%. they give out distributions to US citizens or maybe they treat it much more like a utility and they start heavily regulating and can step in at any time. What do you think is most likely to happen?

</details>

**Swyx**: 我认为，当前的 AI 技术和模型演进速度实在是太过于动荡且具有高度的波动性了，在现阶段将其当成类似于电力或自来水一样的稳定公用事业进行监管，是极不现实的。想象一下，如果当年**爱迪生**（Thomas Edison）在实验室里刚刚发明电灯和构建早期的直流电网时，政府就立刻跳出来，试图用繁琐的公用事业法案去限制和规范它，那会发生什么？显然，你必须先让这个行业自由发展和演进个 50 年。所以在 2025 年，也就是 **ChatGPT** 诞生仅仅三四年之后，就宣称“我们要像监管传统垄断性公用事业一样去彻底限死它，只允许它按成本加成的微薄利润运营，因为它不再会有颠覆性的创新空间了”，这种想法是不符合技术发展客观规律的。我们离那个阶段还差着几十年。

<details>
<summary>Original English</summary>

**Swyx**: I think this thing is too volatile to treat it as a utility, right? Like imagine if like Edison was like, you know, working on his like electrical stuff and light and lighting and all that and he immediately tried to regulate it. Like no, you'll probably wait 50 years first. So it's like a little unfair to [laughter] like in 2025, you know, like four 3 four years after ChatGPT to be like no, like we should regulate it now like a utility because it's there's no more innovation to be had and you should just leave it to natural monopolies and charge like cost plus like I don't think that's we're there yet. I think we need to wait another few decades.

</details>

**Matthew Berman**: 那么，OpenAI 提出这个股权出让计划的真实动机是什么？是某种形式的“付费以求生存”？还是向公权力“低头俯首”？亦或是希望通过向政府出让 5% 的商业权益，换取政府在安全评估和模型发布准许审批上的绿灯，从而跳过或延缓即将出台的强力监管法案？Swyx，请跟我一起合理地推测一下。

<details>
<summary>Original English</summary>

**Matthew Berman**: So what what is it? Is it pay to play? Is it bend the knee? Is it hey, we're going to give you 5% and you're going to allow us to release our our models more quickly? You're going to step back on regulation? Speculate with me, Swyx.

</details>

**Swyx**: 作为一个非美国公民，在谈论美国的政治话题时我向来比较谨慎。但我确实认为，从商业战略的角度来思考这个问题是非常有意思的。企业在制定长期战略时，必须考虑他们是在为哪一届政府的施政纲领做优化，而美国每四年就会迎来一次总统大选。这意味着这实际上是一场长期的“多轮博弈游戏”（Multi-turn game），而不是毕其功于一役的单轮博弈。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. So, like I'm not a citizen, so I do tend to be careful about what I say politically. Um, I do think that uh it is interesting to think through people optimizing for this administration versus well, there's an election every four years and like actually this is a multi-turn game, not a single turn game.

</details>

**Matthew Berman**: 没错，企业绝不能仅仅把眼光放在眼前的这一个政治回合上。

<details>
<summary>Original English</summary>

**Matthew Berman**: So, maybe don't only think in one turn.

</details>

**Swyx**: 是的。

<details>
<summary>Original English</summary>

**Swyx**: Yeah.

</details>

---

### 监管红线与《交易的艺术》

**Matthew Berman**: 让我们沿着这个思路再深入探讨一下。在过去的几周时间里，我们能明显感觉到政府的力量在模型发布和合规性审查上变得非常强势，甚至直接插手决定哪些前沿大模型被允许公开对外开放，以及它们的具体发布时间。举例来说，GPT-5 虽然已经有了实质性的发布宣告，但据称他们必须等待数周时间通过政府的安全联席审查后才能真正推向市场。你觉得这在未来会成为整个大模型行业的新常态吗？联邦政府目前是否在急于为所有的 AI Labs 确立一套具有高度一致性和强制力的国家级安全评测监管框架？

<details>
<summary>Original English</summary>

**Matthew Berman**: Um, okay. So, then like let's continue down this track a little bit. The government, especially in the last few weeks, has been very hands-on deciding what models are publicly available, the timing of models, right? So, GPT 5.6 (5) was just announced, but they have to wait a few weeks to actually release it. Like, do you think this is the new standard? Do you think they're kind of scrambling to come up with a framework that's consistent across all of the AI labs? What do you think's going on?

</details>

**Swyx**: 我认为白宫方面确实倾向于制定一套全国统一的政策标准，在他们看来，这总好过一年前美国各个州政府（例如加州备受争议的 **SB 1047** 法案）各自为战、出台五花八门的地方法规去强行限制 AI 行业。

<details>
<summary>Original English</summary>

**Swyx**: I think the White House thinks it is consistent and uh it is probably better than what the states tried to do themselves a year plus ago with SB 1047 (SB47) all those things.

</details>

**Matthew Berman**: 我完全同意。与其让各州出台割裂的法案，不如在联邦层面进行统一的规则确立。

<details>
<summary>Original English</summary>

**Matthew Berman**: So yeah, I mean yes on the national level do it.

</details>

**Swyx**: 此外，我认为对于这整套政治层面的博弈，我们其实不需要感到大惊小怪，这并不是什么史无前例的新型政治手腕。这就是经典的**《交易的艺术》**（The Art of the Deal）。

<details>
<summary>Original English</summary>

**Swyx**: Um and beyond that I think the best I best I can say about this is this isn't new in terms of tactics in politics and this is the art of the deal.

</details>

**Matthew Berman**: 哈哈，确实是这样。听你这么一说，我都忍不住想把那本书找出来重新读一遍了。

<details>
<summary>Original English</summary>

**Matthew Berman**: [laughter] Yeah, it's Yeah. Honestly, I want to read the book and it's

</details>

**Swyx**: 这是一种经典的谈判策略：在最初的博弈阶段，抛出一个极其极端、甚至看起来有些蛮横的初始要价（Initial gambit），然后在随后的谈判博弈中逐步做出让步和妥协，最终将结果导向你真正满意的真实底线。

<details>
<summary>Original English</summary>

**Swyx**: an initial gambit that is quite extreme, then you roll it back, but you

</details>

**Matthew Berman**: 是的，这正是特朗普在三十多年前的书里所阐述的交易策略。

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah. I mean, it's literally he wrote about 40 years ago, however long it was, 30 years.

</details>

**Swyx**: 而且非常有效。

<details>
<summary>Original English</summary>

**Swyx**: It works.

</details>

**Matthew Berman**: 确实屡试不爽。

<details>
<summary>Original English</summary>

**Matthew Berman**: It works.

</details>

**Swyx**: 那么……

<details>
<summary>Original English</summary>

**Swyx**: And

</details>

**Matthew Berman**: 如果最终拯救人类文明、让我们免于被 **Skynet**（天网）所毁灭的终极救星，不是什么复杂的超级数学公式和安全对齐算法，而是一本《交易的艺术》所确立的博弈论商业逻辑，那这绝对是人类历史上最幽默的讽刺了。

<details>
<summary>Original English</summary>

**Matthew Berman**: would it be funny if like this is actually how humanity is saved from Skynet

</details>

**Swyx**: 毕竟，在资本主义框架下，除了政府的资本控股和强力商业约束外，我们似乎也找不到其他更好的机制来对这些庞大的跨国科技巨头实施有效的实质性控制了。

但你觉得现在的决策者在开会讨论时，他们真正极度焦虑的究竟是科幻小说里的“天网觉醒”，还是更加现实和迫在眉睫的国家安全红线——比如其他竞争对手国家通过蒸馏（Distillation）技术窃取主流大模型的知识产权、通过网络攻击黑进实验室，亦或是将前沿模型直接作为高科技赛博战争的网络武器？你觉得哪一个是他们的心头大患？

<details>
<summary>Original English</summary>

**Swyx**: is the art is the art of the deal? Because there was no other uh there's no other mechanism under capitalism to control companies. But there do you think the government is more worried about Skynet or do you think they're more worried about other countries doing distillation hacking uh or using the model for cyber warfare themselves? What do you think?

</details>

**Swyx**: 我觉得这其中存在着多个维度的考量，而且非常巧合的是，这些考量在最终的方向上都达成了高度的一致。

<details>
<summary>Original English</summary>

**Swyx**: I think there's there's there's multiple reasons that all align. So

</details>

**Matthew Berman**: 当所有的安全担忧和地缘政治考量都汇聚到同一个交汇点时，你确实很难剥离出哪一个是他们最原始的出发点，因为它们最终都指向了相同的政策结果。

<details>
<summary>Original English</summary>

**Matthew Berman**: when they when they all align it's hard to tell motivations because they all point to the same answer.

</details>

**Swyx**: 是的。所以去争论它们之间的重要性排名并没有太大的实际意义。

不过在对待“AI 灭绝论”（pdoom）这个问题上，我可能相比于很多同行会显得更加悲观（Doomer）一些。我遇到过不少在这个行业里工作的顶尖科学家，他们认为大模型导致人类毁灭的概率（pdoom）几乎是零，或者至少是小于 1%。而我个人的悲观指数，如果放在人类未来 50,000 年的漫长时间尺度上去衡量的话，我认为这个概率非常接近 90%。我觉得任何对于 pdoom 的严肃讨论，都必须绑定一个具体的时间线（Timeline）才有意义。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. So like there's no like there's no point ranking them because they're all aligning. Um well I I am I am I am a doomer in like in terms of like people talking about pdoom of like le I've met people with pdoom of zero pdoom of less than 1% mine is like closer to 90 on a scale of 50,000 years um I I think people pdoom should be attached to timeline

</details>

**Matthew Berman**: 五万年……

<details>
<summary>Original English</summary>

**Matthew Berman**: um and so I think 50,000 years

</details>

**Swyx**: 50,000 年，这大致对应了智人（Homo sapiens）在地球上繁衍至今的进化时间跨度。我们在地球上存在的历史也就在 50,000 到 400,000 年之间。在大自然的演进史中，人类并没有任何先天的特权去宣称自己拥有绝对的、永久的生存权，就像在我们之前灭绝的无数物种一样。而如果我们今天正在亲手孕育并接生一种全新的、具有自我进化能力的智能生命形式，那么根据简单的物种竞争和博弈常识，人类在这种更高级生命形式面前表现得力不从心甚至被逐渐边缘化，是一个极具合理性的演进推论。

我们可以看看大自然里的森林和树木在面对高度发达的人类文明时是什么处境。而我们和树木的演化速度差距，就如同未来的超级人工智能和人类的进化速度差距一样，甚至要更加夸张。这绝对是一个值得人类去深刻反思的终极命题。

<details>
<summary>Original English</summary>

**Swyx**: which is the rough approximate time of the homo sapiens right 50,000 to 400,000 is is our span and like you know like we don't have a right to exist anymore than anything else that went existing before us and if we're birthing a new life form um it is reasonable to expect that by accident you know we we wouldn't we may not do so well compared to it um I mean how are trees doing versus human civilization and like when we move much faster than trees these things move much much much faster than us I think it absolutely bears some thought

</details>

**Matthew Berman**: 确实，这意味着从长远来看，人类将这些模型完全引向安全和与人类利益绝对一致的概率是非常低的。

<details>
<summary>Original English</summary>

**Matthew Berman**: yeah I mean I mean what you're saying is basically the chance of actually aligning these models in the long run is very low.

</details>

**Swyx**: 没错，我认为我们默认的理性假设就应该是这种对齐的成功率极低。只有抱着这样的敬畏和危机感去开展工作，即使我们最后在方向上出现了偏差，我们也是在向着更加偏向安全防范的保守方向上偏离。

<details>
<summary>Original English</summary>

**Swyx**: I think our default assumption should be that it's low and if we miss in the right direction, we will have missed in the safe direction. Anyway,

</details>

**Matthew Berman**: 这是一个非常务实且合理的观点。

<details>
<summary>Original English</summary>

**Matthew Berman**: yeah, that's fair.

</details>

---

### AI 工程师的自我定位与 e/acc、安全学派的融合

**Swyx**: 所以，我认为有一点我平常极少公开评论，那就是我们代表的 **AI 工程师（AIE）**群体，在对待技术的态度上，到底处于 **e/acc**（有效加速主义）学派与安全对齐学派（Decels / DEL 运动）之间的什么位置？

答案是：我们恰恰处于这两者的正中间。我在上一届大会的主题演讲中专门阐述过这个政治和行业立场——我们倡导务实的技术乐观主义（Pragmatic Optimism），但我们坚决反对那种毫无边界限制、甚至带有一丝盲目和疯狂的无约束加速主义（Unconstrained Optimism），那正是极端的 e/acc 所宣扬的。

<details>
<summary>Original English</summary>

**Swyx**: So, I think um one thing that I often don't comment about is where AIE is in relation with EAC (e/acc) and the the DEL (alignment/decel) movement and um it's like right in the middle. So I I talked about this at the last WS fair keynote where politically we want to be pragmatic. You want to be optimistic, but you also don't want to be unconstrained optimistic, which is what EA (e/acc) is.

</details>

**Matthew Berman**: 我懂了。

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah.

</details>

**Swyx**: 这也就是为什么在工程实践中，构建模型护栏（Guardrails）、评估系统设计、对模型实施微调（Fine-tuning）以及搭建科学的**评估基准**（Evals）是如此的举足轻重。在一个真正的 AI 工程师看来，如果你只是像极端的加速主义者那样整天躺在办公桌前空谈 AGI 什么时候会降临、它的终极时间线是什么，那这对于解决现实世界的工程问题毫无裨益。

我确实坚信，让富有工程实操经验的软件工程师去掌握技术的实际控制权，在日常开发中密切监视和观察模型的推理行为，并实时监控它们的思维链（Chain of Thought）表现，这才是引领人类走向安全和技术可控的最正确道路。我们作为目前在可观测宇宙中所知道的唯一智能生命形态，生命本身是极其脆弱的。如果没有工程师在底层的代码和系统设计中去精细化地设计和保障这一秩序，我们绝对不能想当然地认为人类文明可以一直延续下去。

<details>
<summary>Original English</summary>

**Swyx**: Um and that's why putting guard rails and systems and fine-tuning and um doing eval are important and an AIE versus with an EAC, you just talk about Agi timelines all day long, right? Because you don't care. Um I do think that some measure of having the engineers in control of things, watching things, monitoring change of thought probably is the right path for humanity. So like the lyon of like you know we live as far as you know we're the only life form in the in the observable universe. Uh it it's life is very fragile and like we shouldn't assume that by default we get the right to continue existing unless you engineer it.

</details>

**Matthew Berman**: 如果我们要把这个长达数万年的宏大时间尺度拉回到眼前，如果让你给出一个具体的预测，你觉得在未来 10 年和 50 年这两个时间节点上，人类面临 AI 导致的生存危机的概率（pdoom）分别是多少？

<details>
<summary>Original English</summary>

**Matthew Berman**: If you had to shrink the timeline from 50,000 to let let's get your pdoom on 10 years and 50 years.

</details>

**Swyx**: 在未来的 10 年尺度上，这个危机发生的概率极低，几乎可以忽略不计。

<details>
<summary>Original English</summary>

**Swyx**: Oh yeah. I mean pdoom in 10 years is is near zero. Uh

</details>

**Matthew Berman**: 听你这么说这真的让人松了一口气。

<details>
<summary>Original English</summary>

**Matthew Berman**: well that's good. That's good.

</details>

**Swyx**: 是的。而 50 年这个时间点，基本上就标志着我们这一代人生命周期的终点了。在这个尺度上，如果让我粗略给出一个预估……之前我随口说过一个 10% 的概率，但回过头来想一想，10% 还是太高了，可能在 5% 左右吧。

我倾向于从更长远的宏观历史视角来看待这个问题，就像科幻神作**《基地》**（Foundation）或《沙丘》（Dune）里所描绘的宏大史诗一样。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. 50 is like that's like the end of our lifetimes. Um and like I think I don't know. I'm I'm just throw out 10. No, 10's too high. Five%. Um and uh again I I think on the timelines more of what you see in Foundation, you know the TV show.

</details>

**Matthew Berman**: 那确实是一部极其精彩的美剧。

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah. Great show. Great show.

</details>

**Swyx**: 当你把视线拉长到千百万年的生命演化和文明史长河中时，你就不会把所有的注意力都局限在眼前这极其短暂的几年甚至几十年里。因为我们完全有理由去推测，目前主流的基于 Transformer 架构的大模型研发范式在未来的某个节点可能会撞上物理和算法的红线，从而迎来新一轮长达数十年的 AI 寒冬。直到人类发现全新的算法范式，或者是经历了数千代人的迭代，真正的通用人工智能（AGI）才可能降临。我们怎么能自大到认为，人类文明正好就活在那个万物走向终结的特定转折点上呢？这种“末日恰好降临在我这一代”的想法，多少带有一些狂妄的自我主角光环色彩。

<details>
<summary>Original English</summary>

**Swyx**: Um or Dune. I think um when you when you think about the long evolution of life forms and history, you shouldn't be so sort of near-term focused because yeah, probably LMS are going to run out at some point and they're not AGI and okay, we have maybe another 30 years of AI winter or something and then like the next paradigm really is actually the thing or it takes another 3,000 generations like what like you know who are we to say that we happen to live in the exact moment that everything ends. Like that's very that's very egotistical like you're the main character really

</details>

**Matthew Berman**: 确实，对于未来千百年后的人类而言，也许我们现在所处的时代，仅仅只是他们眼中的原始史前文明阶段罢了。

<details>
<summary>Original English</summary>

**Matthew Berman**: like you know who's to say you're not like you know in prehistory right now as far as the future people are concerned.

</details>

**Swyx**: 没错。

<details>
<summary>Original English</summary>

**Swyx**: Yeah.

</details>

---

### 从“苦涩的教训”到数据效率与全新世界模型

**Matthew Berman**: 那么，你认为大语言模型（LLMs）现有的迭代路径，真的足以通过**自我迭代改善**（Recursive Self-Improvement，RSI）的逻辑自我演进，最终量变引起质变催生出 AGI，还是说我们必须依赖底层架构上的全新突破？

<details>
<summary>Original English</summary>

**Matthew Berman**: Do do you think uh large language models are are enough to lead to recursive self-improvement thus leading to some next architecture that might be AGI.

</details>

**Swyx**: 这是一个非常有深度且需要细化讨论的复杂问题。我个人的答案是：不，我认为仅仅依靠现有大模型架构的 RSI 是不够的。

没错，大语言模型确实在技术上使自我迭代改善（RSI）成为了可能，我们的模型目前也确实在很多开发任务中扮演着自我迭代的角色。我们大会昨天还专门开设了一个关于自动化学术研究（Auto-research）的专题论坛，里面深入探讨了这些技术。但是，这种单纯依靠现有数据的自我迭代，其天花板是非常明显的。因为模型在自我递归时，往往只是在人类已经探索和确立的现有知识分布区间里进行穷尽和组合，它无法真正跳出这个已知的框架。

<details>
<summary>Original English</summary>

**Swyx**: Oh I see that is a very nuanced question. I think actually my answer is no on that one. Um we yes LLM enable RSI. RSI is really just like is it recursing and yes it is recursing on it's we have a whole auto research track yesterday covering that stuff. Um but it is limited in its recursion because it probably just explores things that have been explored before. So it's like not that far off from like the dist distribution of stuff we already know.

</details>

**Matthew Berman**: 是的，它无法自主去发现那些真正的“未知的未知”（Unknown unknowns）。

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah.

</details>

**Swyx**: 想要发现宇宙中真正的未知规律，实现颠覆性的科学创新，并构建出能真实映射物理规律的物理世界模型（World Models），这依然属于学术研究的最前沿攻坚领域。仅仅依靠现有的数据蒸馏和参数微调是远远不够的，我们必然需要引入全新的算法范式。我们这次大会也设立了关于**世界模型**（World Models）的讨论专题，虽然它目前在应用层面还处于非常初级的萌芽阶段，大家都心知肚明这一点，但它绝对是一个必须被全力攻坚的核心方向。因为正如知名科技播主 Dwarkesh Patel 所指出的那样，目前大模型的学习效率问题是硬伤。

<details>
<summary>Original English</summary>

**Swyx**: So discovering true unknown unknowns uh having real real innovation having a real sense of world models that is still the domain of research and yeah we probably need something else. We did have a world models track here. It is not very well developed. Everyone knows it but clearly this needs to be fleshed out more because the stuff that Dorcash (Dwarkesh) is saying is absolutely right. Uh we like learn current learning paradigms.

</details>

**Matthew Berman**: 哪一部分的效率问题？

<details>
<summary>Original English</summary>

**Matthew Berman**: What part?

</details>

**Swyx**: **数据效率**（Data efficiency）是横在人类面前的下一个巨大阻碍。

我们这次的底层数据专题也探讨了完全相同的话题。目前的大模型为了达到接近人类水平的劳动力输出，必须在长达数万亿（Trillions）Token 的庞大语料库上进行高强度的预训练。这从计算和能耗效率的角度来看，相比于人类脑细胞的学习机制，简直是低效到了极点。人类只需要接收百万到十亿级别的信息 Token，就足以成长为一个能够独立思考、创造巨大商业社会价值的合格成年劳动者。

那么，我们为什么非得强行把大语言模型那恐怖的、动辄吞噬整个互联网数据的算力怪兽，套进人类大脑的狭隘框架里去进行对比呢？难道仅仅因为机器的学习机制和人类不同，我们就要全盘否定它的演进方向吗？

<details>
<summary>Original English</summary>

**Swyx**: Uh data efficiency is the next problem. um we had a data track on the same thing. Um and you know like learning over a trillions of tokens in order to get to some form of human equivalent labor is very very inefficient versus what humans do. Humans learn on the order of like millions and they can already do like very useful things billions and you're a full working adult. So, do we have to try to fit large language models, the compute that it requires into kind of the human box? Why does it have to be well, if it's not exactly how humans learn, then it's not the right way?

</details>

**Matthew Berman**: 不，我完全赞同你的看法。我把这种人类中心主义的对比称为**“苦涩的教训”**（The Bitter Lesson）。每当我们试图用人类生物学的运作逻辑和类比去强行套在冰冷的硅基机器上时，我们往往会迎来惨痛的挫败。因为硅基机器的演进和自我繁衍路径，注定是与碳基人类截然不同的。

<details>
<summary>Original English</summary>

**Matthew Berman**: No, I I absolutely agree with what you're saying there, which I call this a sour (bitter) lesson, right? Like every time you try to make a human analogy to machines, you you probably fail because machines develop very differently from humans.

</details>

**Swyx**: 没错，我完全同意。即便未来的智能表现出一种非常非人的、冰冷而陌生的异类高效学习机制，那又有什么关系呢？这并不妨碍它成为一种强大的智能。我们目前唯一确定的是，现有的动辄消耗数万亿 Token 的训练方式确实在商业上是非常低效且昂贵的，这确实是一个需要被攻克的硬性缺点。

<details>
<summary>Original English</summary>

**Swyx**: Uh so, no, I agree. I I agree with that. And I also think that it can still be an alien form of more efficient learning. Doesn't matter. We just know that it's super inefficient like that. That is something that we know is a unmitigated negative.

</details>

**Matthew Berman**: 所以我们必须想方设法提升它的数据和算力效率。

<details>
<summary>Original English</summary>

**Matthew Berman**: So let's make it more efficient and better. Uh

</details>

**Swyx**: 没错。这意味着在未来，如果我们能从需要 2000 个示范样本才能让模型学会一个特定任务，优化到只需要 20 个样本，甚至缩短到 2 个样本的 **Few-shot** 极简学习，那整个技术的商业化落地规模将呈指数级扩张。这意味着我们可以实现真正的**持续学习**（Continual learning），让部署在客户端的智能体能够根据用户的实时反馈自主微调，构建出对物理现实世界的真实认知模型。否则，我们就会被永远困在目前“预训练-后训练”（Pre-train & Post-train）这一繁琐且昂贵的旧范式里，而这个旧范式目前在边际效益上已经开始显露出遭遇物理和算力天花板的迹象了。

<details>
<summary>Original English</summary>

**Swyx**: and that means that you know if in order instead of 2,000 examples to learn one thing, what about 20 examples, what about two examples? Um and that scales a lot more. Um, and that means, you know, we can we can get we can actually get to a point with continual learning that we can actually have uh agents that adapt and and build up a real world model. Otherwise, we're always stuck to the pre-train postra (post-train) paradigm that is probably hitting some kind of limit right now.

</details>

**Matthew Berman**: 是的。

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah.

</details>

**Swyx**: 我个人确实倾向于认为，Claude 3.5 Sonnet 这一代模型可能标志着当前这一轮大语言模型单纯靠规模（Scaling Law）粗暴堆叠时代的终点。因为正如我刚才所提到的，它的响应延迟和运行速度慢得令人发指。你也同意目前 Claude 3.5 Sonnet 运行起来非常慢这一点，对吧？

<details>
<summary>Original English</summary>

**Swyx**: Like it like I genuinely do expect Fable (Claude 3.5 Sonnet) to be the end of this era of LMS because you can't like I already told you about the slowness. Do you agree with the slowness by the way that Fable's (Sonnet) slow?

</details>

**Matthew Berman**: 我最近一直在 **Cursor** 这个 AI 编程神器里高频使用它，感觉它的响应速度和它刚发布的那头几天相比稍微快了一点点。但它确实依然非常慢，这是不争的事实。

<details>
<summary>Original English</summary>

**Matthew Berman**: I I've actually so I' I've been using it in cursor and it's it feels a little bit faster than when it first came out a couple weeks ago. Um but it is slow. It is slow.

</details>

**Swyx**: 我知道 Anthropic 的工程团队目前正在全力以赴攻克推理端的延迟优化。但不可否认，由于它现在的延迟硬伤，很多对实时响应要求极高的日常开发场景是根本无法使用它的。

<details>
<summary>Original English</summary>

**Swyx**: I mean look at topic (Anthropic) is working on better inference. Yeah. No train through straight but it is slow and like therefore you just won't use it for some things that you know

</details>

**Matthew Berman**: 没错，你确实不需要在所有的琐碎开发任务里都去支付如此高昂的推理成本和等待时间。

<details>
<summary>Original English</summary>

**Matthew Berman**: don't require Fable (Claude 3.5 Sonnet). Yeah. [laughter] You also don't want to pay Fable (Sonnet) prices for everything. Why would

</details>

**Swyx**: 虽然在很多人的设想中，我们未来会生活在一个算力无限、Token 成本无限接近于零的理想世界里。但在现实的工程和商业世界中，最奢侈、最无法被无限挥霍的终极预算，其实是用户的时间。这是每个人和每个企业头顶最坚硬的硬约束限制。即使你是在全球最顶尖的 Frontier Lab 里工作的顶尖科学家，你也无法避开时间维度上的物理局限。

所以，如果未来一个参数量达到 20 万亿级的超级模型就是当前架构的极限，而由于物理极限和算力成本的制约，我们无法在商业上部署 200 万亿甚至千万亿参数规模的模型，那在现有的 Transformer 推理范式下，我们基本上就已经走到了实用性天花板的边缘。因此，我们迫切需要完全不同的底层技术，无论是目前被寄予厚望的**思考机**（Thinking machines）长推理链技术，还是像 Together AI 团队正在极力推进的全新 **SSM**（状态空间模型）架构。虽然这些新技术目前在商业化成熟度上还差得很远。

<details>
<summary>Original English</summary>

**Swyx**: like even like I'm trying to live in an infinite budget world but the the budget I don't have is time, right? like this the this is the limiting budget that everyone has. I don't care if you're working at a frontier lab, you still you still have time as a as a as a as a limiter. So, um yeah, if that's like if a 20 trillion model is it, there's no 200 trillion, there's no quadrillion scale model, then that's kind of it as far as usability is concerned living in an infinite budget environment. So therefore, you just need something different. whatever is maybe it's like thinking machines stuff maybe it's together AI is SSM stuff whatever it is we don't have it yet

</details>

---

### 智能体实验室的崛起与应用层创业的破局之道

**Matthew Berman**: 我最近也在深刻反思这个问题。我认为在当前的行业中，“模型能力悬崖”（Capability Overhang，即大模型在许多领域的潜在能力远未被现有工具和应用开发完全榨干）依然是一个非常显著且真实的产业现状。即使是面对上一代的 **Claude 3 Opus** 或 GPT-4，开发者和企业真正能够通过工程手段从这些模型中安全、稳定提取出来的商业应用价值，也依然只是冰山一角。而现在，随着新一代大模型的疯狂迭代，这个能力悬崖只会变得越来越深。对此你有什么看法？作为应用开发者，我们是否应该继续把所有的精力放在围绕这些现有模型去拼命构建更加完善的外围工程工具链上？

<details>
<summary>Original English</summary>

**Matthew Berman**: I've I've seen I've seen a lot and I've thought a lot about this the the model capability overhang still seems very real even from the previous generation Opus uh GPT 5.5 (GPT-4) the the amount of value that can be extracted from those models still seems at least to me to be uh uh critical and and now we have a whole new uh generation of models that we're even going to get more model overhang from what do you do you agree with that do you think need to keep building the tools around

</details>

**Swyx**: 我完全赞同。事实上，**AI 工程师（AI Engineer）**这个全新职业之所以诞生，其生存空间恰恰就存在于“模型顶尖研究能力”与“将这些能力安全落地并部署到各行各业的复杂生产环境”之间的巨大白色区域里。

模型研究团队在实验室里不断攻克新的能力顶峰，但这并不等同于这些前沿能力能够自动、均匀地分布并赋能于各行各业的软件产品中。只要这个“能力与落地的鸿沟”一直存在，应用层工程师和开发团队就永远不用担心失业，我们会一直有做不完的商业化落地项目。所以我对应用层工程的未来持极度乐观的态度。

当然，在这个过程中，我们也必须经历周期性的“技术债大扫除”（Spring cleaning）。在模型能力不断躍迁的过程中，你之前为了弥补模型能力的缺陷而不得不写下的成千上万行复杂的工程外围封装代码，可能在下一代模型发布后，只需要一个简单的单句 System Prompt 就能被模型原生替代了。这时候你必须毫不留情地把之前的代码全部扔进垃圾桶。这种事情在日常开发中非常普遍，我们需要在上一代模型的特定限制假设下构建系统，然后当限制不复存在时主动重构它们。我们绝不能对自己写下的代码产生任何盲目的情感依赖。在商业世界的终局，我们所有人唯一的共同目标，就是以更便宜的成本、更快的交付速度、更便捷的体验去服务好客户。

<details>
<summary>Original English</summary>

**Swyx**: AI engineer exists in the white surface area between the peak capability and deploying it everywhere else right so the more model research peaks and spikes capabilities in one domain but it's not evenly distributed in all products yet that's where engineers have a job forever basically Um, so I'm very pro that. Um, I I I think capability overhang will exist for a long time. I think it does keep have waves of consolidation where you're like actually all this stuff I build out, I don't need it anymore because the next model has got it from just a single prompt. So I'm going to throw it out. But we do spring cleaning every now and then, like that's normal. And we build it up on previous gen model assumptions that then go away. And I don't think we should feel any attachment to the code. At the end of the day, we're all just trying to like serve customers better, do work cheaper, faster, easier.

</details>

**Matthew Berman**: 让我们就这个话题深入聊一聊，因为我对此感同身受。我自己之前兴致勃勃地开发过许多非常炫酷的、针对特定单点痛点的 AI 小项目。然而，当下一代更加强悍的大模型发布后，我看着自己的项目，不得不无奈地感叹：“好吧，这套复杂的工程封装现在看起来完全是多此一举了，这个项目彻底失效了。”

同时我们也看到，像 Anthropic 这样的模型巨头，目前正在疯狂地沿着技术栈向上蔓延，直接吞噬应用层。面对这种大厂的降维打击，如果你是一个准备入局的创业公司创始人，你会给他们什么建议？应用层创业公司应该把精力投放在哪里？他们如何才能在模型能力不断野蛮生长的夹缝中，找到自己真正稳固的商业护城河？

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah. Let's let's talk about that a little bit because I've built a bunch of cool kind of one-off projects that one model generation later I was like, "Oh, well, that's kind of useless now." And then you you know, you have anthropic moving in different directions. They're moving up the stack to the application layer. If you're a founder, what are you know, what advice would you give to founders who are trying to build at the application layer? Where should they be spending their time? How should they think about the expanding model capabilities in each subsequent generation of model?

</details>

**Swyx**: 我的核心建议非常简单，可以用两个词来概括：**智能体实验室（Agent Labs）**。

我个人非常钟爱这种高度凝练、直击痛点的双字解决方案。就像我当年提出并推广了“AI 工程师（AI Engineer）”这个词一样，我认为未来应用层创业的终极归宿是“智能体实验室（Agent Labs）”。对于这套商业逻辑，我之前在 Latent Space 博客上撰写过一篇深度的行业剖析文章（地址是 `laten.space/agentlabs`），感兴趣的朋友可以去详细阅读。

智能体实验室的核心商业逻辑在于：你必须永远在特定的垂直赛道上，扮演那个最懂客户需求、能够为客户解决最后十公里技术落地痛点的“AI 专家”。在创业时，**千万不要选择去跟风炒作某一个特定的模型技术方案，而要深度锚定并绑定你所服务的特定客户的核心业务问题**。如果你能向你的客户（无论是牙医、律师、金融分析师、还是软件开发人员）提供无微不至的专属服务，向他们承诺：“无论未来的前沿大模型如何演进、技术潮流怎么变，我们都会确保把全球最顶尖、最适合的 AI 工具，以最无缝、最契合你们业务工作流的方式，打包落地进你们的实际业务系统里。”那么你就构建起了无法被模型巨头轻易颠覆的品牌忠诚度与商业护城河。

<details>
<summary>Original English</summary>

**Swyx**: Yeah, I my answer to this is two words. Agent lab. I like I like the two-word solutions. I like AI engineer. I like agentlab. Um so I have a piece on this if people want to see. Uh it's on where they find it laten.space/agentlabs. Um and basically the idea is that you always want to be the AI guys for your customers. Actually don't pick the solution, pick the problem. And if you're like okay I'm like whatever it is in AI whatever the hot thing is whatever the new trend is what the new model is I will be the AI guy for dentists or for lawyers or for finance people uh or for coders whatever. Um then you will just be build that lasting brand of we like we will build the products that do the last mile for you and fold in all the new functionalities and features that people discover into that. That is the sustainable thing.

</details>

**Matthew Berman**: 但这种商业模式，在本质上难道不是在赌前沿模型永远无法实现跨行业的彻底通用化（Generalization），并赌赢那些大模型实验室永远无法将他们的触角完美伸向所有细分垂直行业吗？这听起来是不是多少有点在和技术趋势唱反调？

<details>
<summary>Original English</summary>

**Matthew Berman**: Isn't that isn't that isn't that isn't that betting against the generalization of the models and the capability of the labs frankly?

</details>

**Swyx**: 不，我并不这么认为。当然，在某种程度上也许是的。在现有的技术周期中，这背后的博弈确实非常微妙。我们必须承认，模型的通用化能力在每一次升级中都确实会抹杀掉很多之前看似坚固的单点工具型应用（Wrapper apps）分类。

但关键的商业认知在于：如果你成功在垂直领域（例如律师行业）建立起了强大的商业壁垒，向客户表明“我们就是最懂法务工作流的技术团队，是你们可以完全信赖的外包 AI 技术顾问”。那么，即使我们之前的某套基于旧模型的法务文本检索技术架构被新一代的通用模型碾压了，那也无伤大雅。我们会立刻利用新一代模型所释放出来的全新能力悬崖，为我们的法务客户以最快速度构建出一套体验强上十倍的全新法务智能系统。你真正在赌的，是**“未来大模型的能力悬崖（Capability Overhang）将永远存在”**这一颠扑不破的行业常识。而我认为，这是一个几乎不可能输的稳健赌注。

<details>
<summary>Original English</summary>

**Swyx**: Uh no. Yeah. So let me think about this. So no but maybe yes. So I I don't know where I stand with regards to your question because the models do generalize and sometimes wipe out entire product categories. But I do think that if you are smart enough to like I literally I like I am the AI layer for lawyers. I'm your outsource tech team for lawyers. Okay, that my my old business model is gone. Fine. I'll make a new one with like whatever new capability overhang is created. What you're betting against is capability overhangs ever existing in the future. And I think that's a pretty safe bet to make.

</details>

**Matthew Berman**: 确实如此。

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah.

</details>

**Swyx**: 没错，模型的能力悬崖在可见的未来将是常态，它们虽然会不断发生位置上的飘移，但绝对不会凭空消失。这意味着作为一个敏捷、nimble 的应用层开发团队，你必须保持高度的行业敏感度和架构弹性。

你可以看看当今 AI 行业的标杆企业：做智能体座席的 **Sierra**、做大模型软件工程助手的 **Cognition**（智能软件工程师 Devin 的开发商）、代码编辑领域的顶流 **Cursor**，以及专门赋能特定业务流程的 **Decagon** 和 **Harvey**。它们在本质上全都是各自垂直细分领域最典型的“智能体实验室（Agent Labs）”。它们成为了各自行业客户心中最值得信赖的技术品牌，客户相信它们会源源不断地把最前沿的 AI 技术转化为可直接商用的产品。

大模型实验室的研发团队虽然强大，但他们绝不可能有精力和意愿去雇佣 200 多个销售与技术支持团队，整天坐在高盛集团（Goldman Sachs）的办公室里现场待命，事无巨细地贴身服务他们：“好的，老板，你们需要把系统接入微软 Teams？没问题，我们立刻给你们开发定制接口。什么？你们公司内部没有使用标准的 GitHub 托管，而是用了一套很多年前从 Atlassian Bitbucket 开源版本里强行 Fork 出来的、充满历史包袱的古怪内部代码库？交给我们，我们来帮你们搞定适配。”

像 Anthropic 或 OpenAI 这样追求万亿参数、通用智能的实验室，是绝对不可能低下头来做这些琐碎而不可或缺的定制化工程脏活累活的。

<details>
<summary>Original English</summary>

**Swyx**: Um so like there will always be capability overhangs. They may not stay still. And so you got to be nimble. But the Sierras of the world, the Cognitions of the world, the cursors of the world, the decagons and um Harveys, these are all agent labs for their field. They can be trusted brand names to always apply the latest AI to their thing. And maybe they're a little bit behind the the frontier labs on like the the latest models, but in terms of solving user customer feedback, you know, I've I've been inside of cognition for the last six months. Um there's no one else. the the labs do not have 200 people dedicated to like you know being on call with you with Goldman Sachs going like okay guys what do you need we got it you you need the Microsoft team zero integration got it you don't use GitHub you use this like weird org thing that is like a fork of Elastian's Bitbucket when it was open source got it claw's (Claude's) not going to do that

</details>

---

### 模型路由还是 All-in 单一模型？

**Matthew Berman**: 让我们沿着这个话题继续深入聊聊。你在 Cognition 团队工作了六个月。根据你在那里的实地观察，如果把他们的员工伙食水准（Food bench）作为一个评估指标，他们能在基准测试上拿到多少分？

<details>
<summary>Original English</summary>

**Matthew Berman**: I mean let's continue on that so you've you've been at uh Cognition for 6 months and you had the food it scores well on food bench

</details>

**Swyx**: 哈哈，在伙食和员工福利这个维度上，他们的表现极其优异，绝对在 Food Bench 基准测试中名列前茅。

<details>
<summary>Original English</summary>

**Swyx**: it is a very good food bench high on food bench benchmark. Um

</details>

**Matthew Berman**: 确实，虽然他们在其他很多高难度的算法基准测试上还需要继续努力攻坚，但至少在伙食水平这个基准上，他们已经有了一个完美的起点。

<details>
<summary>Original English</summary>

**Matthew Berman**: we need we need to score better on other benchmarks but but food is a good start.

</details>

**Swyx**: 是的，你下次如果再去访问他们，记得一定要让他们邀请你共进午餐。这样你就能亲自在脑海中为这个基准跑分了。

<details>
<summary>Original English</summary>

**Swyx**: You just have to invite me back. That's how you got to run the benchmark again. Um do you do you think um uh sorry I lost my train of thought. Um

</details>

**Matthew Berman**: 哈哈，没问题。噢，我想起来我刚才要问什么了。

最近行业里关于“Token 预算”（Token budget）以及如何榨干长文本极限（Token maxing）的话题讨论得非常热烈。对于绝大多数中小企业和普通开发者来说，在日常开发中无约束地去挥霍长上下文的 Token 成本是根本不可承受之重。你认为这是否在客观上为非大模型实验室的、以 Cursor 和 Cognition 为代表的应用层 Agent Lab 创业公司，提供了一个极其关键的商业生存支点？

因为这些 Agent Lab 本质上是完全 Model Agnostic（大模型无知论/模型中立）的，他们有着极强的内在商业动力，去把不同大模型之间的智能调度和模型路由（Model Routing）做到极致，以此来帮用户精打细算省下每一分 Token 钱。而专注于研发单一模型的顶尖实验室，由于利益冲突，是绝对不可能去主动做这种跨厂商模型路由和成本优化的。你认为模型中立与智能路由技术，会成为未来这批应用层公司的核心护城河吗？

<details>
<summary>Original English</summary>

**Matthew Berman**: oh yeah so a lot of discussion lately has been around token budget and and really token maxing being unattainable to most people. Do you think that's actually a huge value to the nonfrontier lab uh agent lab companies? So the cursors, the cognitions of the fact (factories) of the world are isn't this kind of like prime time for them because first of all they're model agnostic. They actually have incentive to do model routing really well whereas the frontier labs don't. Do you think this is the era of uh kind of the the uh model agnostic companies?

</details>

**Swyx**: 是的。我承认你刚才推导出来的这个结论在逻辑上听起来非常自洽，也完全合乎情理。

但我必须诚实地指出：虽然这个逻辑目前是行业内几乎所有人都在随波逐流、挂在嘴边的流行叙事，但我个人对此其实持保留态度。

因为如果你去仔细复盘云计算时代的技术演进史，你会发现真正笑到最后并攫取了最大商业蛋糕的赢家，往往并不是那些自诩中立、在各个云服务商之间进行流量路由的中间件公司，而是那些坚定不移地选择 **All-in**（全情投入）某一个特定云计算巨头生态的先驱者。

在上一轮云浪潮中，我们见证了无数标榜多云管理、宣称可以通过中间件和 Terraform 帮你无缝在 AWS、谷歌云（GCP）或微软 Azure 之间进行多云备份和智能流量调度的创业公司。然而，这背后有一个极为残酷的商业现实：如果你在技术架构上刻意追求“多云中立”和“智能路由”，你就势必要在底层接口的设计上做出妥协，去适配所有云服务商之间的最小公分母（Lowest common denominator）。这直接导致你的应用永远无法去深度榨干和调用 AWS 或其他任何一家云服务商所提供的、最前沿、最具差异化优势的独家底层高级功能。

<details>
<summary>Original English</summary>

**Swyx**: Yeah, I think that is a reasonable conclusion to make which doesn't mean that I think it. I think that is a lot is that is currently what everyone is saying because of this current debate. Uh I do observe that in general the the big big wins have just been going all in on one thing. Um, and I'm old enough in tech to know have seen this before with the cloud wave where there have been companies that were all in on AWS or all in on GCP. And there have been other companies that were multicloud there always, you know, like I'll use the the the Terraform, the whatever. And the simple argument is that if you route, if you pride yourself on routing, you will never exploit the full capabilities of one because you're not all in on one. You're not. Right.

</details>

**Matthew Berman**: 确实如此。这种为了路由而路由的做法，往往是以牺牲对最前沿特性的深度集成和探索为惨痛代价的，最终只能拿出一个极其平庸、毫无竞争力的同质化产品。

<details>
<summary>Original English</summary>

**Matthew Berman**: So it's a really good way to be lowest common denominator of every model out there and completely miss all capability.

</details>

**Swyx**: 没错。而且你作为多云中间商，也永远无法享受到像 AWS 这样掌控了从底层芯片、物理机房到应用软件整套全栈生态的科技巨头通过规模效应（Economies of scale）所带来的极致成本优势。

<details>
<summary>Original English</summary>

**Swyx**: You also don't have the economies of scale that an AWS has going all in owning the entire stack.

</details>

**Matthew Berman**: 是的。

<details>
<summary>Original English</summary>

**Matthew Berman**: Yeah. Yeah.

</details>

**Swyx**: 事实上，现在的顶级 Agent Labs 凭借其庞大的 Token 消耗体量，完全可以从每一个底层大模型提供商那里拿到极具诱惑力的定制化 API 折扣价格。

这就产生了一个非常有趣的商业博弈现象：当人们在社交平台上拿 Anthropic 官方给普通开发者提供的公共 API 报价，去和那些直接与大模型实验室建立深度定制化商业合作的头部 Agent Labs 实际拿到的“内部友情底价”进行粗暴的对比时，他们往往会得出很多完全脱离真实商业生态的错误结论。

总之，我想表达的核心观点是：目前很多创业公司所宣扬的“模型智能路由”概念，在很大程度上只是一套用来敷衍投资人和进行市场公关的营销说辞（Marketing line）。你千万不能盲信它。

当你真正坐下来，去和这个行业里最顶尖的那些智能体开发者（Agent builders）进行闭门交流时，你会发现他们脑子里整天想的，绝对不是如何在 100 个不同的模型之间进行 superficial（肤浅）的文本请求路由。他们所有的精力，都聚焦在如何针对某一款特定的主力旗舰模型，去掘地三尺般地探索和榨干其提示词空间的每一个像素级潜能、进行极致的上下文缓存（Context caching）算法优化、打通底层的工具调用（Tool use），以及设计精妙的并发工程架构。

<details>
<summary>Original English</summary>

**Swyx**: So so yeah, Asian (Agent) labs get discounts from every model provider. And that's also very interesting when people compare public pricing of like a discounted cloud code (Claude) from Anthropic versus what Anthropic does with model labs. Oh, with with agent labs and I think like that's also an interesting discussion on that front too. Um anyway, all all which to say I do think that this routing thing is is a marketing line. I wouldn't necessarily believe it so much as when I talked to the top tier agent builders because they're all about maximizing and fully exploring like the complete prompt surface area and optimization area and tool use and caching and god knows what else in there, right? Like like exploit everything they give you

</details>

**Matthew Berman**: 没错。你是希望浅尝辄止地在一百个平庸的模型之间做最简单的聊天交互，还是希望全情投入去深度压榨旗舰大模型的所有终极潜力？这两种路线在构建智能体系统时的胜率高下立判。

<details>
<summary>Original English</summary>

**Matthew Berman**: or do you want to just stay superficial and only do chat completions across a 100 different models? Yeah. Right. Which is more likely to win as an agent lab.

</details>

**Swyx**: 确实如此。

<details>
<summary>Original English</summary>

**Swyx**: Yeah. Right. Which

</details>

**Matthew Berman**: 好的。Swyx，非常感谢你今天能抽出时间接受我的采访，这是一场极具启发性的深度对话。

<details>
<summary>Original English</summary>

**Matthew Berman**: All right. Well, uh, Swix, I want to say thank you very much. I appreciate the conversation.

</details>

**Swyx**: 和你聊天总是非常愉快。我也很高兴你今天能够来到现场，见证我创办的这场大会迎来它历史性的巅峰时刻。我想你之前应该只是在远程的技术播客录制、或者在我们的办公室等日常环境里见过我。今天你终于见到了我作为一名狂热的技术社区发起人和线下布道者的真实一面。

<details>
<summary>Original English</summary>

**Swyx**: It's good to chat, man. I'm glad you could see me and on my biggest day on my biggest show. I think you've seen me in like the podcast, the the office and all those things. This is I I'm an inerson real community guy.

</details>

**Matthew Berman**: 我必须由衷地赞叹你今天在这里所构建的一切。这里挤满了无数对技术充满狂热与探索欲的优秀工程师，他们不仅在这里奉献了极其精彩的演讲，更在这个社区里汲取到了海量的技术养分。

<details>
<summary>Original English</summary>

**Matthew Berman**: I I am genuinely impressed with what you built here. You have a bunch of great excited, enthusiastic people, not only giving talks, but also learning a ton.

</details>

**Swyx**: 没错，在这里，他们不仅能学到最前沿的技术，更能结识未来的合伙人，建立起深厚的技术纽带。对了，我还期待着你未来在我们的 YouTube 频道和媒体建设上提供一些宝贵的专业建议和帮助呢。

<details>
<summary>Original English</summary>

**Swyx**: and and uh yeah, making connections, getting co-founders. Um I need your help on our YouTube, our YouTube stuff.

</details>

**Matthew Berman**: 没问题，随时奉陪，让我们一起把它做大。

<details>
<summary>Original English</summary>

**Matthew Berman**: Let's do it.

</details>

**Swyx**: 是的，技术仍在狂飙，还有太多有价值的东西等待着我们去探索。

<details>
<summary>Original English</summary>

**Swyx**: Uh so yeah, lots lots of learning uh to be had.

</details>

**Matthew Berman**: 再次感谢你，Swyx。

<details>
<summary>Original English</summary>

**Matthew Berman**: Thanks, Swix.

</details>

**Swyx**: 谢谢，非常棒的交流。

<details>
<summary>Original English</summary>

**Swyx**: Thanks. Very nice.

</details>